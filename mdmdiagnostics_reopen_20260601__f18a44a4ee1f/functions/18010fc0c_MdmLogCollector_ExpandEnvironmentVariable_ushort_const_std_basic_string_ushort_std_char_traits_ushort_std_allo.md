# MdmLogCollector::ExpandEnvironmentVariable(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18010fc0c`
- end: `0x18010fcea`
- name: `?ExpandEnvironmentVariable@MdmLogCollector@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `222`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800fabb4`
- `0x180109e70`
- `0x18010cb20`

## callees

- `0x180019594`
- `0x1800ed44c`
- `0x1800ed46c`
- `0x180109140`
- `0x18010fc0c`
- `0x18011273c`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18010fc20`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18010fc79`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18010fc20`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18010fc79`

## string_xrefs

- `0x18010fc37`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010fc8e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010fcb4`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`

## pseudocode

```c

```
