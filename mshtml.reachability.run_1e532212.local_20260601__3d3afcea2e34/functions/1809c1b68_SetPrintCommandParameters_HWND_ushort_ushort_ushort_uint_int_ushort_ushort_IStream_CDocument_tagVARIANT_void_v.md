# SetPrintCommandParameters(HWND__ *,ushort *,ushort *,ushort *,uint,int,ushort *,ushort *,IStream *,CDocument *,tagVARIANT *,void *,void *,ushort *,ushort *,ushort *,PRINTTYPE,ushort *)

- ea: `0x1809c1b68`
- end: `0x1809c24ad`
- name: `?SetPrintCommandParameters@@YAPEAUIUnknown@@PEAUHWND__@@PEAG11IH11PEAUIStream@@PEAVCDocument@@PEAUtagVARIANT@@PEAX5111W4PRINTTYPE@@1@Z`
- size: `2373`
- prototype: `struct IUnknown *__high(HWND, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, int, unsigned __int16 *, unsigned __int16 *, struct IStream *, struct CDocument *, struct tagVARIANT *, void *, void *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, enum PRINTTYPE, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1806d4ea8`
- `0x1809c0adc`
- `0x1809c1898`
- `0x1809c2920`

## callees

- `0x1800ea428`
- `0x18021a0ec`
- `0x180402d68`
- `0x1809bf9c4`
- `0x1809c0690`
- `0x1809c1b68`
- `0x180a1f740`
- `0x1810a6e64`
- `0x181104010`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1809c225d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1809c225d`
- `OLEAUT32!__imp_SysAllocString` at `0x1809c1c35`
- `OLEAUT32!__imp_SysAllocString` at `0x1809c1e85`
- `OLEAUT32!__imp_SysAllocString` at `0x1809c1edd`
- `OLEAUT32!__imp_SysAllocString` at `0x1809c1f39`
- `OLEAUT32!__imp_SysAllocString` at `0x1809c1f95`
- `OLEAUT32!__imp_SysAllocString` at `0x1809c1ff1`
- `OLEAUT32!__imp_SysAllocString` at `0x1809c21b7`
- `OLEAUT32!__imp_SysAllocString` at `0x1809c23c1`
- `OLEAUT32!__imp_SysAllocString` at `0x1809c1c35`
- `OLEAUT32!__imp_SysAllocString` at `0x1809c1e85`
- `OLEAUT32!__imp_SysAllocString` at `0x1809c1edd`
- `OLEAUT32!__imp_SysAllocString` at `0x1809c1f39`
- `OLEAUT32!__imp_SysAllocString` at `0x1809c1f95`
- `OLEAUT32!__imp_SysAllocString` at `0x1809c1ff1`
- `OLEAUT32!__imp_SysAllocString` at `0x1809c21b7`
- `OLEAUT32!__imp_SysAllocString` at `0x1809c23c1`
- `OLEAUT32!__imp_VariantInit` at `0x1809c2194`
- `OLEAUT32!__imp_VariantInit` at `0x1809c2194`
- `OLEAUT32!__imp_VariantClear` at `0x1809c1c4b`
- `OLEAUT32!__imp_VariantClear` at `0x1809c1c8b`
- `OLEAUT32!__imp_VariantClear` at `0x1809c1cd8`
- `OLEAUT32!__imp_VariantClear` at `0x1809c1dd6`
- `OLEAUT32!__imp_VariantClear` at `0x1809c1e25`
- `OLEAUT32!__imp_VariantClear` at `0x1809c1e71`
- `OLEAUT32!__imp_VariantClear` at `0x1809c1ec9`
- `OLEAUT32!__imp_VariantClear` at `0x1809c1f21`
- `OLEAUT32!__imp_VariantClear` at `0x1809c1f7d`
- `OLEAUT32!__imp_VariantClear` at `0x1809c1fd9`
- `OLEAUT32!__imp_VariantClear` at `0x1809c2035`
- `OLEAUT32!__imp_VariantClear` at `0x1809c2096`
- `OLEAUT32!__imp_VariantClear` at `0x1809c21fb`
- `OLEAUT32!__imp_VariantClear` at `0x1809c224c`
- `OLEAUT32!__imp_VariantClear` at `0x1809c22b5`
- `OLEAUT32!__imp_VariantClear` at `0x1809c234c`
- `OLEAUT32!__imp_VariantClear` at `0x1809c23a0`
- `OLEAUT32!__imp_VariantClear` at `0x1809c2405`
- `OLEAUT32!__imp_VariantClear` at `0x1809c2464`
- `OLEAUT32!__imp_VariantClear` at `0x1809c2489`
- `OLEAUT32!__imp_VariantClear` at `0x1809c1c4b`
- `OLEAUT32!__imp_VariantClear` at `0x1809c1c8b`
- `OLEAUT32!__imp_VariantClear` at `0x1809c1cd8`
- `OLEAUT32!__imp_VariantClear` at `0x1809c1dd6`
- `OLEAUT32!__imp_VariantClear` at `0x1809c1e25`
- `OLEAUT32!__imp_VariantClear` at `0x1809c1e71`
- `OLEAUT32!__imp_VariantClear` at `0x1809c1ec9`
- `OLEAUT32!__imp_VariantClear` at `0x1809c1f21`
- `OLEAUT32!__imp_VariantClear` at `0x1809c1f7d`
- `OLEAUT32!__imp_VariantClear` at `0x1809c1fd9`
- `OLEAUT32!__imp_VariantClear` at `0x1809c2035`
- `OLEAUT32!__imp_VariantClear` at `0x1809c2096`
- `OLEAUT32!__imp_VariantClear` at `0x1809c21fb`
- `OLEAUT32!__imp_VariantClear` at `0x1809c224c`
- `OLEAUT32!__imp_VariantClear` at `0x1809c22b5`
- `OLEAUT32!__imp_VariantClear` at `0x1809c234c`
- `OLEAUT32!__imp_VariantClear` at `0x1809c23a0`
- `OLEAUT32!__imp_VariantClear` at `0x1809c2405`
- `OLEAUT32!__imp_VariantClear` at `0x1809c2464`
- `OLEAUT32!__imp_VariantClear` at `0x1809c2489`

## string_xrefs

- `0x1809c1c63`: `__IE_TemplateUrl`
- `0x1809c20b1`: `__IE_TemporaryFiles`
- `0x1809c23da`: `__IE_SerializeCommandListOutfile`

## pseudocode

```c

```
