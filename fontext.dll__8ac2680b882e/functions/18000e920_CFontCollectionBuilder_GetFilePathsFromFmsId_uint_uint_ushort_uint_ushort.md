# CFontCollectionBuilder::_GetFilePathsFromFmsId(uint,uint,ushort *,uint,ushort *)

- ea: `0x18000e920`
- end: `0x18000eb28`
- name: `?_GetFilePathsFromFmsId@CFontCollectionBuilder@@AEAAJIIPEAGI0@Z`
- size: `520`
- prototype: `int(CFontCollectionBuilder *__hidden this, unsigned int, unsigned int, unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18000e144`
- `0x18000f6b8`
- `0x18000fc40`

## callees

- `0x180006668`
- `0x180008aec`
- `0x180008ed8`
- `0x18000a830`
- `0x18000ae20`
- `0x18000e920`
- `0x18000f518`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `msvcrt!wcschr` at `0x18000ea5c`
- `msvcrt!wcschr` at `0x18000ea5c`
- `fms!FmsGetFontProperty` at `0x18000e9f1`
- `fms!FmsGetFontProperty` at `0x18000ea3a`
- `fms!FmsGetFontProperty` at `0x18000e9f1`
- `fms!FmsGetFontProperty` at `0x18000ea3a`

## string_xrefs

- `0x18000e95d`: `_GetFilePathsFromFmsId`
- `0x18000e98b`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`

## pseudocode

```c

```
