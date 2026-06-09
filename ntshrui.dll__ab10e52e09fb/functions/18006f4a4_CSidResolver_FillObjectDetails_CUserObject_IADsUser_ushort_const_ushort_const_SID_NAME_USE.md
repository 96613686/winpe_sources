# CSidResolver::_FillObjectDetails(CUserObject *,IADsUser *,ushort const *,ushort const *,_SID_NAME_USE)

- ea: `0x18006f4a4`
- end: `0x18006f602`
- name: `?_FillObjectDetails@CSidResolver@@IEAAJPEAVCUserObject@@PEAUIADsUser@@PEBG2W4_SID_NAME_USE@@@Z`
- size: `350`
- prototype: `int(CSidResolver *__hidden this, struct CUserObject *, struct IADsUser *, const unsigned __int16 *, const unsigned __int16 *, enum _SID_NAME_USE)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18006f6a4`

## callees

- `0x180013220`
- `0x1800254e0`
- `0x18006f4a4`
- `0x18006f608`
- `0x180078010`

## import_xrefs

- `SHLWAPI!StrChrW` at `0x18006f530`
- `SHLWAPI!StrChrW` at `0x18006f530`
- `OLEAUT32!__imp_SysFreeString` at `0x18006f5c8`
- `OLEAUT32!__imp_SysFreeString` at `0x18006f5d4`
- `OLEAUT32!__imp_SysFreeString` at `0x18006f5c8`
- `OLEAUT32!__imp_SysFreeString` at `0x18006f5d4`

## pseudocode

```c

```
