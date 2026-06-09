# CStream::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x180048720`
- end: `0x180048899`
- name: `?GetIDsOfNames@CStream@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `377`
- prototype: `__int64 __fastcall(CStream *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned int, unsigned int, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18009e1e0`
- `0x18009e1f0`

## callees

- `0x180048720`
- `0x1800bdac8`
- `0x1800c8f34`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800487a2`
- `msvcrt!_wcsicmp` at `0x1800487a2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180048742`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180048742`

## string_xrefs

- `0x1800487e4`: `<CStdComObjectRoot::FindIdsOfNames|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x18004887b`: `<CStdComObjectRoot::FindIdsOfNames|ADO|ERR> 0x%08x{HRESULT} line %d\n`

## pseudocode

```c

```
