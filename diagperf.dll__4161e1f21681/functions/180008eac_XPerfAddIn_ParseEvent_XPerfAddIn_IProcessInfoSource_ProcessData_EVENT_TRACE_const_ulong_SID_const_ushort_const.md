# XPerfAddIn::ParseEvent(XPerfAddIn::IProcessInfoSource::ProcessData &,_EVENT_TRACE const *,ulong,_SID const * *,ushort const * *,ulong *)

- ea: `0x180008eac`
- end: `0x1800091c3`
- name: `?ParseEvent@XPerfAddIn@@YAJAEAUProcessData@IProcessInfoSource@1@PEBU_EVENT_TRACE@@KPEAPEBU_SID@@PEAPEBGPEAK@Z`
- size: `791`
- prototype: `__int64 __fastcall(XPerfAddIn *__hidden this, struct XPerfAddIn::IProcessInfoSource::ProcessData *, const struct _EVENT_TRACE *, unsigned int, const struct _SID **, const unsigned __int16 **, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800089b0`
- `0x18006ae90`

## callees

- `0x180008eac`

## import_xrefs

- `msvcrt!malloc` at `0x180009004`
- `msvcrt!malloc` at `0x180009004`
- `msvcrt!_wcsdup` at `0x180009135`
- `msvcrt!_wcsdup` at `0x18000919b`
- `msvcrt!_wcsdup` at `0x180009135`
- `msvcrt!_wcsdup` at `0x18000919b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000902b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000902b`

## pseudocode

```c

```
