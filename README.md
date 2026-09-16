# Satellite1 ESPHOME Firmware - OpenAI realtime 2 Fork

This is a modification of the [Satellite1-ESPHome](https://github.com/FutureProofHomes/Satellite1-ESPHome) firmware to make it act as a websocket client towards [ha-openai-realtime](https://github.com/xandervanerven/ha-openai-realtime)

## Installation
Take the original Satellite1 ESPHome configuration and change the following lines:
```
packages:
  FutureProofHomes.Satellite1:
    url: &repo_url https://github.com/vincentwolsink/Satellite1-ESPHome
    ref: &repo_ref main
```

Add to `substitutions` if your Home Assistant is not reachable on `homeassistant.local`:
```
  va_url: "ws://your_home_assistant_url_or_ip:8080"
```

## Known limitations

- **No voice timers or alarms yet** — every other Assist action (lights, switches,
  scenes, climate) and online questions work.
- **A brief reconnect about once an hour** (OpenAI's 60-minute session cap; the
  add-on refreshes proactively during a quiet moment, so it rarely interrupts).

## Credits
- Original firmware: https://github.com/FutureProofHomes/Satellite1-ESPHome
- Home Assistant Voice PE websocket modification: https://github.com/xandervanerven/home-assistant-voice-pe
