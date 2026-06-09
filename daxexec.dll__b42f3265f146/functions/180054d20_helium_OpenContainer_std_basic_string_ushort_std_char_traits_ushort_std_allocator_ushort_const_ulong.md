# helium::OpenContainer(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x180054d20`
- end: `0x180054e9a`
- name: `?OpenContainer@helium@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `378`
- prototype: `HANDLE *__fastcall(HANDLE *, __int64, ACCESS_MASK)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180042520`
- `0x180056a70`

## callees

- `0x180004f70`
- `0x180013510`
- `0x180021118`
- `0x18005431c`
- `0x180054d20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054e13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054e13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054df4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054df4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054e05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054e3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054e05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054e3d`
- `ntdll!NtOpenJobObject` at `0x180054dcb`
- `ntdll!NtOpenJobObject` at `0x180054dcb`
- `ntdll!RtlInitUnicodeString` at `0x180054d71`
- `ntdll!RtlInitUnicodeString` at `0x180054d71`

## pseudocode

```c

```
