# DllMain

- ea: `0x18000fa84`
- end: `0x18000fc38`
- name: `DllMain`
- size: `436`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800063f4`

## callees

- `0x180001418`
- `0x180007018`
- `0x18000af90`
- `0x18000f5cc`
- `0x18000f618`
- `0x18000fa84`
- `0x18000fd48`
- `0x18000fd80`
- `0x1800100c8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000fb98`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000fb98`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18000fbca`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18000fbca`
- `WppRecorderUM!WppAutoLogStop` at `0x18000fbea`
- `WppRecorderUM!WppAutoLogStop` at `0x18000fbea`

## pseudocode

```c

```
