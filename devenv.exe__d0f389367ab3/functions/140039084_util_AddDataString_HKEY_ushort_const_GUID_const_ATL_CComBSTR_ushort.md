# util_AddDataString(HKEY__ *,ushort const *,_GUID const &,ATL::CComBSTR &,ushort * *)

- ea: `0x140039084`
- end: `0x140039248`
- name: `?util_AddDataString@@YAHPEAUHKEY__@@PEBGAEBU_GUID@@AEAVCComBSTR@ATL@@PEAPEAG@Z`
- size: `452`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpValueName@<rdx>, const struct _GUID *@<r8>, struct ATL::CComBSTR *@<r9>, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140039248`

## callees

- `0x140001020`
- `0x140001040`
- `0x140002190`
- `0x140004a98`
- `0x140008ec4`
- `0x140033ab0`
- `0x140039084`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1400390d4`
- `ADVAPI32!RegQueryValueExW` at `0x140039153`
- `ADVAPI32!RegQueryValueExW` at `0x1400390d4`
- `ADVAPI32!RegQueryValueExW` at `0x140039153`
- `OLEAUT32!__imp_SysAllocString` at `0x140039189`
- `OLEAUT32!__imp_SysAllocString` at `0x140039189`
- `OLEAUT32!__imp_SysFreeString` at `0x1400391cd`
- `OLEAUT32!__imp_SysFreeString` at `0x140039213`
- `OLEAUT32!__imp_SysFreeString` at `0x1400391cd`
- `OLEAUT32!__imp_SysFreeString` at `0x140039213`
- `OLEAUT32!__imp_SysStringLen` at `0x1400391a3`
- `OLEAUT32!__imp_SysStringLen` at `0x1400391a3`
- `OLEAUT32!__imp_VarBstrCat` at `0x1400391be`
- `OLEAUT32!__imp_VarBstrCat` at `0x1400391be`

## pseudocode

```c

```
