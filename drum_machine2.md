~~~ruby
use_bpm 65

live_loop :drums do
  sample :drum_heavy_kick
  sleep 1
  sample :sn_dolf
  sleep 1
end

live_loop :sample do
  sync :drums
  sample :loop_compus, beat_stretch: 8
  sleep 8
end

live_loop :bass do
  sync :drums
  use_synth :chipbass
  sample :bd_sone, amp: 3
  play chord(:c2, :minor).choose, sustain: 7, amp: 0.7
  sleep 8
end

live_loop :effects do
  sync :drums
  sample choose([:elec_filt_snare, :elec_mid_snare, :elec_twip, :elec_twang, :elec_pop, :elec_blup, :elec_blip2, :elec_beep, :elec_ping])
  sleep 2
end
~~~
