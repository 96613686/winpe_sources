# FailFastStr(ushort const *,ushort const *,int,int,int,_EXCEPTION_POINTERS *)

- ea: `0x18007de24`
- end: `0x18007debc`
- name: `?FailFastStr@@YAXPEBG0HHHPEAU_EXCEPTION_POINTERS@@@Z`
- size: `152`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, int, int, int, struct _EXCEPTION_POINTERS *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000792c`
- `0x18007d44c`

## callees

- `0x18007d554`
- `0x18007de24`
- `0x18007e30c`
- `0x18007e5ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007de97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007de97`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18007dea5`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18007dea5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18007de4e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18007de4e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007de7f`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18007de7f`

## string_xrefs

- `0x18007de61`: `COM+ Failfast:  Unable to allocate memory for stack trace!`

## pseudocode

```c

```
