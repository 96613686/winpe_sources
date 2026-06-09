# CRDPETWTracingSession::EventTracingRegister(_GUID const *,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *),void *)

- ea: `0x18006f62c`
- end: `0x18006f6de`
- name: `?EventTracingRegister@CRDPETWTracingSession@@AEAAKPEBU_GUID@@P6AX0KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z3@Z`
- size: `178`
- prototype: `unsigned int __fastcall(CRDPETWTracingSession *__hidden this, const struct _GUID *, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *), void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1801113b4`

## callees

- `0x18006f62c`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006f655`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006f655`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006f66d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006f682`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006f69b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006f66d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006f682`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006f69b`

## string_xrefs

- `0x18006f663`: `EventWrite`
- `0x18006f64e`: `advapi32.dll`

## pseudocode

```c

```
