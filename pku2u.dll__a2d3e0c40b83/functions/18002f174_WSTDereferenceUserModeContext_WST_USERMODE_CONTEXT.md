# WSTDereferenceUserModeContext(_WST_USERMODE_CONTEXT *)

- ea: `0x18002f174`
- end: `0x18002f1f6`
- name: `?WSTDereferenceUserModeContext@@YAXPEAU_WST_USERMODE_CONTEXT@@@Z`
- size: `130`
- prototype: `void __fastcall(struct _WST_USERMODE_CONTEXT *)`
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180023fb0`
- `0x180024260`
- `0x180024460`
- `0x180024570`
- `0x180024900`
- `0x180024a10`
- `0x180024b90`
- `0x18002f1fc`
- `0x18002f468`
- `0x18002f560`

## callees

- `0x18002f174`
- `0x18002f384`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002f1d4`
- `ntdll!RtlLeaveCriticalSection` at `0x18002f1d4`
- `ntdll!RtlEnterCriticalSection` at `0x18002f1c5`
- `ntdll!RtlEnterCriticalSection` at `0x18002f1c5`

## pseudocode

```c

```
