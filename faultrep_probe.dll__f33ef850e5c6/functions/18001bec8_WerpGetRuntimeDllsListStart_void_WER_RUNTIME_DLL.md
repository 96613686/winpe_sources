# WerpGetRuntimeDllsListStart(void *,_WER_RUNTIME_DLL * *)

- ea: `0x18001bec8`
- end: `0x18001bfa7`
- name: `?WerpGetRuntimeDllsListStart@@YAJPEAXPEAPEAU_WER_RUNTIME_DLL@@@Z`
- size: `223`
- prototype: `__int64 __fastcall(void *, struct _WER_RUNTIME_DLL **)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180014c34`
- `0x18002dcdc`

## callees

- `0x180002890`
- `0x180003474`
- `0x180003617`
- `0x18001bad4`
- `0x18001bec8`
- `0x180049280`
- `0x180049304`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x18001bf7b`
- `ntdll!DbgPrintEx` at `0x18001bf7b`

## string_xrefs

- `0x18001bf6d`: `WER/CrashAPI/%u:%u: ERROR Invalid args in call to WerpGetRuntimeDllsListStart.\n`

## pseudocode

```c

```
