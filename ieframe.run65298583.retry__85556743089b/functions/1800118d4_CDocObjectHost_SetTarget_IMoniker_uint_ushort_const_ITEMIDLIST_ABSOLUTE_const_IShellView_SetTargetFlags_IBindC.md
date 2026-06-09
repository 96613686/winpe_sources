# CDocObjectHost::SetTarget(IMoniker *,uint,ushort const *,_ITEMIDLIST_ABSOLUTE const *,IShellView *,SetTargetFlags,IBindCtx *,int *)

- ea: `0x1800118d4`
- end: `0x180012137`
- name: `?SetTarget@CDocObjectHost@@QEAAJPEAUIMoniker@@IPEBGPEBU_ITEMIDLIST_ABSOLUTE@@PEAUIShellView@@W4SetTargetFlags@@PEAUIBindCtx@@PEAH@Z`
- size: `2147`
- prototype: `__int64 __fastcall(__int64, struct IMoniker *, int, const WCHAR *, const ITEMIDLIST *pidl, struct IShellView *, char, struct IBindCtx *, int *)`
- caller_count: `2`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003d7f8`
- `0x1800f9f1c`

## callees

- `0x180011390`
- `0x1800118d4`
- `0x180012140`
- `0x180012170`
- `0x180012310`
- `0x1800131c0`
- `0x18002320c`
- `0x180024180`
- `0x18004a080`
- `0x18005bc40`
- `0x18006ff5c`
- `0x18007479c`
- `0x180090244`
- `0x180090938`
- `0x1800957dc`
- `0x1800babd4`
- `0x1800c122c`
- `0x180137b48`
- `0x180138b24`
- `0x18013ab34`
- `0x180144cd0`
- `0x180197bf4`
- `0x1804f1db4`
- `0x18054e286`
- `0x18054e310`
- `0x18054e3d0`
- `0x180550010`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x180011a30`
- `KERNEL32!GlobalFree` at `0x180011a30`
- `KERNEL32!GetTickCount` at `0x180011e41`
- `KERNEL32!GetTickCount` at `0x180011e41`
- `KERNEL32!LocalFree` at `0x1800119e8`
- `KERNEL32!LocalFree` at `0x180011a49`
- `KERNEL32!LocalFree` at `0x1800119e8`
- `KERNEL32!LocalFree` at `0x180011a49`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x1800119f1`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x1800119f1`
- `ole32!CreateBindCtx` at `0x180011eb0`
- `ole32!CreateBindCtx` at `0x180011eb0`
- `OLEAUT32!__imp_SysAllocString` at `0x180011d5b`
- `OLEAUT32!__imp_SysAllocString` at `0x180011d5b`
- `OLEAUT32!__imp_SysFreeString` at `0x180011d96`
- `OLEAUT32!__imp_SysFreeString` at `0x180011d96`
- `OLEAUT32!__imp_VariantClear` at `0x180011beb`
- `OLEAUT32!__imp_VariantClear` at `0x180011beb`
- `SHELL32!__imp_ILClone` at `0x18001197c`
- `SHELL32!__imp_ILClone` at `0x18001197c`
- `SHELL32!__imp_ILFree` at `0x180011973`
- `SHELL32!__imp_ILFree` at `0x180011973`
- `iertutil!CreateUri` at `0x180011c64`
- `iertutil!CreateUri` at `0x180011c64`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180011d51`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180011d51`
- `urlmon!CreateAsyncBindCtxEx` at `0x180011fb6`
- `urlmon!CreateAsyncBindCtxEx` at `0x180011fb6`

## string_xrefs

- `0x180011f26`: `__DISABLE_NATIVEXML_PARSING`

## pseudocode

```c

```
