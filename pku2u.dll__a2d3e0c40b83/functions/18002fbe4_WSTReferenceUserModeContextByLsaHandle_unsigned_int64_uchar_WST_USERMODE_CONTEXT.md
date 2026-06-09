# WSTReferenceUserModeContextByLsaHandle(unsigned __int64,uchar,_WST_USERMODE_CONTEXT * *)

- ea: `0x18002fbe4`
- end: `0x18002fca0`
- name: `?WSTReferenceUserModeContextByLsaHandle@@YAJ_KEPEAPEAU_WST_USERMODE_CONTEXT@@@Z`
- size: `188`
- prototype: `int(unsigned __int64, unsigned __int8, struct _WST_USERMODE_CONTEXT **)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180023fb0`
- `0x180024460`
- `0x180024570`
- `0x180024900`
- `0x180024a10`
- `0x180024b90`
- `0x18002f1fc`
- `0x18002f468`

## callees

- `0x18002fbe4`
- `0x180043d78`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002fc71`
- `ntdll!RtlLeaveCriticalSection` at `0x18002fc71`
- `ntdll!RtlEnterCriticalSection` at `0x18002fc42`
- `ntdll!RtlEnterCriticalSection` at `0x18002fc42`

## pseudocode

```c

```
