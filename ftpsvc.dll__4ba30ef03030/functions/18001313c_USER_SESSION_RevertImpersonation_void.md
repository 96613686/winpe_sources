# USER_SESSION::RevertImpersonation(void)

- ea: `0x18001313c`
- end: `0x180013262`
- name: `?RevertImpersonation@USER_SESSION@@AEAAXXZ`
- size: `294`
- prototype: `void __fastcall(USER_SESSION *__hidden this)`
- caller_count: `10`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000ed00`
- `0x18000f370`
- `0x18000f560`
- `0x18000f7a0`
- `0x18000f930`
- `0x1800101a0`
- `0x180010370`
- `0x1800113d0`
- `0x1800123a0`
- `0x180012c90`

## callees

- `0x18001313c`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800131f9`
- `KERNEL32!GetLastError` at `0x1800131f9`
- `ADVAPI32!RevertToSelf` at `0x1800131ef`
- `ADVAPI32!RevertToSelf` at `0x1800131ef`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x1800131e9`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x1800131e9`
- `iisutil!PuDbgPrintError` at `0x18001323f`
- `iisutil!PuDbgPrintError` at `0x18001323f`

## string_xrefs

- `0x180013226`: `USER_SESSION::RevertImpersonation`

## pseudocode

```c

```
