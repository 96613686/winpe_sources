# MdmLogCollector::ExpandEnvironmentVariable(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18010e684`
- end: `0x18010e755`
- name: `?ExpandEnvironmentVariable@MdmLogCollector@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800f9bb4`
- `0x180108ae0`
- `0x18010b6d4`

## callees

- `0x180019514`
- `0x1800ece3c`
- `0x1800ece5c`
- `0x180107e60`
- `0x18010e684`
- `0x18011129c`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18010e698`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18010e6eb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18010e698`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18010e6eb`

## string_xrefs

- `0x18010e6a9`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010e6fa`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010e720`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`

## pseudocode

```c

```
