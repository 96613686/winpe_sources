# FailFastStr(ushort const *,ushort const *,int,int,int,_EXCEPTION_POINTERS *)

- ea: `0x180089378`
- end: `0x180089410`
- name: `?FailFastStr@@YAXPEBG0HHHPEAU_EXCEPTION_POINTERS@@@Z`
- size: `152`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, int, int, int, struct _EXCEPTION_POINTERS *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000a7c0`
- `0x180088948`

## callees

- `0x180088aa8`
- `0x180089378`
- `0x180089860`
- `0x180089b60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800893f9`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800893f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800893eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800893eb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800893d3`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800893d3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800893a2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800893a2`

## string_xrefs

- `0x1800893b5`: `COM+ Failfast:  Unable to allocate memory for stack trace!`

## pseudocode

```c

```
