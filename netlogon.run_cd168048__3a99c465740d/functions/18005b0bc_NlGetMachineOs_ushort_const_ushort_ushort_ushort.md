# NlGetMachineOs(ushort const *,ushort * *,ushort * *,ushort * *)

- ea: `0x18005b0bc`
- end: `0x18005b2a7`
- name: `?NlGetMachineOs@@YAJPEBGPEAPEAG11@Z`
- size: `491`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180061b40`
- `0x180062590`

## callees

- `0x180007518`
- `0x18005b0bc`
- `0x18005b980`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005b254`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005b269`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005b27e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005b254`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005b269`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005b27e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18005b12b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18005b12b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005b13b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005b168`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005b13b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005b168`
- `LSASRV!LsaIGetClientOsInfo` at `0x18005b156`
- `LSASRV!LsaIGetClientOsInfo` at `0x18005b156`

## string_xrefs

- `0x18005b211`: `The os for account %ws is "%ws", build "%ws", service pack "%ws"\n`

## pseudocode

```c

```
