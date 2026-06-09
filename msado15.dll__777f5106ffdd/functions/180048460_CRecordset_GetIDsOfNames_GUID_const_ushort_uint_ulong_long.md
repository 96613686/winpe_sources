# CRecordset::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x180048460`
- end: `0x1800485d9`
- name: `?GetIDsOfNames@CRecordset@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `377`
- prototype: `__int64 __fastcall(CRecordset *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned int, unsigned int, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18006b4b0`
- `0x18006b4c0`

## callees

- `0x180048460`
- `0x1800aa988`
- `0x1800c8f34`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800484e2`
- `msvcrt!_wcsicmp` at `0x1800484e2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180048482`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180048482`

## string_xrefs

- `0x180048524`: `<CStdComObjectRoot::FindIdsOfNames|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x1800485bb`: `<CStdComObjectRoot::FindIdsOfNames|ADO|ERR> 0x%08x{HRESULT} line %d\n`

## pseudocode

```c

```
