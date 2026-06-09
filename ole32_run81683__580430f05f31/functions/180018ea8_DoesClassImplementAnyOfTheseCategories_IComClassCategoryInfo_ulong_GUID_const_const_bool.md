# DoesClassImplementAnyOfTheseCategories(IComClassCategoryInfo *,ulong,_GUID const * const,bool &)

- ea: `0x180018ea8`
- end: `0x1800190aa`
- name: `?DoesClassImplementAnyOfTheseCategories@@YAJPEAUIComClassCategoryInfo@@KQEBU_GUID@@AEA_N@Z`
- size: `514`
- prototype: `HRESULT __fastcall(IComClassCategoryInfo *classCategoryInfo, unsigned int categoriesCount, const _GUID *categories, bool *implementsAny)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180018bc4`

## callees

- `0x1800185ec`
- `0x180018ea8`
- `0x180019c4c`
- `0x18001b0e4`
- `0x180052390`
- `0x1800573ec`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001904f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001908e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001904f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001908e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180018fad`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180018fad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019003`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019003`

## string_xrefs

- `0x180018f49`: `com\ole32\inc\CatalogCategoryHelpers.hpp`
- `0x180019060`: `com\ole32\inc\CatalogCategoryHelpers.hpp`
- `0x180019095`: `onecore\internal\com\inc\combase\ComGuid.hpp`

## pseudocode

```c

```
