# OException::OException(OException::tag_t,et::exceptionType,uint,wchar_t const (&)[73],std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180134868`
- end: `0x180134943`
- name: `??$?0$0EJ@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V01@@OException@@QEAA@Utag_t@0@W4exceptionType@et@@IAEAY0EJ@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@3@Z`
- size: `219`
- prototype: `__int64 __fastcall(__int64, int, __int64, int, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180134f78`

## callees

- `0x180006ef0`
- `0x18000adf0`
- `0x18003e690`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1801348cc`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180134910`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1801348cc`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180134910`

## string_xrefs

- `0x1801348c0`: `ORegistryKey.DeleteSubKeyTree failure: Cannot delete Registry Key %s\%s.`
- `0x1801348e0`: `ORegistryKey.DeleteSubKeyTree failure: Cannot delete Registry Key %s\%s.`

## pseudocode

```c

```
