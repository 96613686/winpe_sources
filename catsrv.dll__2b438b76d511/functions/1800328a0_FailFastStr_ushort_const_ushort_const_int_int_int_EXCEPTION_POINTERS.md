# FailFastStr(ushort const *,ushort const *,int,int,int,_EXCEPTION_POINTERS *)

- ea: `0x1800328a0`
- end: `0x18003294b`
- name: `?FailFastStr@@YAXPEBG0HHHPEAU_EXCEPTION_POINTERS@@@Z`
- size: `171`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, int, int, int, struct _EXCEPTION_POINTERS *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009098`

## callees

- `0x180031fd0`
- `0x1800328a0`
- `0x180032f34`
- `0x180033234`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180032921`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180032921`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180032913`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180032913`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800328ca`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800328ca`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800328fb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800328fb`

## string_xrefs

- `0x1800328dd`: `COM+ Failfast:  Unable to allocate memory for stack trace!`

## pseudocode

```c

```
