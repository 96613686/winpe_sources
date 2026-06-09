# ndisBindGetProtocolDriver(_UNICODE_STRING *,bool,bool)

- ea: `0x14015cf80`
- end: `0x14015d17b`
- name: `?ndisBindGetProtocolDriver@@YA?AV?$KRef@UNDIS_BIND_PROTOCOL_DRIVER@@@@PEAU_UNICODE_STRING@@_N1@Z`
- size: `507`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400b7730`
- `0x1400b7b60`
- `0x14015b820`

## callees

- `0x140055150`
- `0x14014bac8`
- `0x14015c390`
- `0x14015cf80`
- `0x14015d190`
- `0x14015df00`
- `0x14015e2a0`
- `0x14016a020`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015d094`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015d094`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14015cfb2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14015cfb2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14015cfc8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14015cfc8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14015d088`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14015d088`
- `ntoskrnl!_wcsnicmp` at `0x14015d05b`
- `ntoskrnl!_wcsnicmp` at `0x14015d05b`

## pseudocode

```c

```
