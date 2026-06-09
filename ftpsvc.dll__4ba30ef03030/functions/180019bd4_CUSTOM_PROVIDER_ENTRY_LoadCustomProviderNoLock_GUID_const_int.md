# CUSTOM_PROVIDER_ENTRY::LoadCustomProviderNoLock(_GUID const &,int)

- ea: `0x180019bd4`
- end: `0x18001a0e6`
- name: `?LoadCustomProviderNoLock@CUSTOM_PROVIDER_ENTRY@@AEAAJAEBU_GUID@@H@Z`
- size: `1298`
- prototype: `__int64 __fastcall(CUSTOM_PROVIDER_ENTRY *__hidden this, const struct _GUID *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800199d4`
- `0x18001a9ec`

## callees

- `0x180019964`
- `0x180019bd4`
- `0x18001a0ec`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x180019d01`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x180019fac`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x180019d01`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x180019fac`
- `iisutil!PuDbgPrintError` at `0x180019e22`
- `iisutil!PuDbgPrintError` at `0x180019ea8`
- `iisutil!PuDbgPrintError` at `0x180019f13`
- `iisutil!PuDbgPrintError` at `0x18001a01e`
- `iisutil!PuDbgPrintError` at `0x18001a078`
- `iisutil!PuDbgPrintError` at `0x180019e22`
- `iisutil!PuDbgPrintError` at `0x180019ea8`
- `iisutil!PuDbgPrintError` at `0x180019f13`
- `iisutil!PuDbgPrintError` at `0x18001a01e`
- `iisutil!PuDbgPrintError` at `0x18001a078`

## string_xrefs

- `0x180019e84`: `UpdateFtpHost() failed.`
- `0x180019ff6`: `Invalid type or clsid attributes.\n`

## pseudocode

```c

```
