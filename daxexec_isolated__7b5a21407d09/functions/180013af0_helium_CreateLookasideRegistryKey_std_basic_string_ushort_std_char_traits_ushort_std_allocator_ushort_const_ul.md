# helium::CreateLookasideRegistryKey(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x180013af0`
- end: `0x180013be5`
- name: `?CreateLookasideRegistryKey@helium@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `245`
- prototype: `HKEY *__fastcall(HKEY *, const WCHAR *, REGSAM samDesired)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800137e8`

## callees

- `0x180013af0`
- `0x180014e74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013ba8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013ba8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013b9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013b9a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013b59`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013b59`

## string_xrefs

- `0x180013bd3`: `onecore\base\appmodel\execmodel\desktopappx\lib\lookaside.cpp`

## pseudocode

```c

```
