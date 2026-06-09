# cpExtensionMatch(_CERT_CONTEXT const *,ushort const *,_CERTFILTERDATA *,int *,int *)

- ea: `0x180016dac`
- end: `0x180016f99`
- name: `?cpExtensionMatch@@YAJPEBU_CERT_CONTEXT@@PEBGPEAU_CERTFILTERDATA@@PEAH3@Z`
- size: `493`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, const unsigned __int16 *, struct _CERTFILTERDATA *, int *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800168e8`

## callees

- `0x1800166c8`
- `0x180016dac`
- `0x1800174f8`
- `0x180017818`

## import_xrefs

- `CRYPT32!CryptFindOIDInfo` at `0x180016e8a`
- `CRYPT32!CryptFindOIDInfo` at `0x180016e8a`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180016ec9`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180016ec9`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180016ef5`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180016f35`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180016f73`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180016ef5`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180016f35`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180016f73`

## pseudocode

```c

```
