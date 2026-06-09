# FailFastStr(ushort const *,ushort const *,int,int,int,_EXCEPTION_POINTERS *)

- ea: `0x180043a58`
- end: `0x180043b03`
- name: `?FailFastStr@@YAXPEBG0HHHPEAU_EXCEPTION_POINTERS@@@Z`
- size: `171`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, int, int, int, struct _EXCEPTION_POINTERS *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005944`

## callees

- `0x180043188`
- `0x180043a58`
- `0x180043fa0`
- `0x1800442a0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180043ab3`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180043ab3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180043a82`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180043a82`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180043ad9`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180043ad9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180043acb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180043acb`

## string_xrefs

- `0x180043a95`: `COM+ Failfast:  Unable to allocate memory for stack trace!`

## pseudocode

```c

```
