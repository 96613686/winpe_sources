# appinfosvc_get_process_list(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800845e4`
- end: `0x180084869`
- name: `?appinfosvc_get_process_list@@YA?AV?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z`
- size: `645`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18007e3c0`

## callees

- `0x1800210fc`
- `0x18005236c`
- `0x180082c14`
- `0x1800845e4`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800846e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800846fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800846e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800846fa`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18008472b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18008472b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008477d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008477d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008467c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008467c`
- `msvcp_win!_Mtx_unlock` at `0x18008482a`
- `msvcp_win!_Mtx_unlock` at `0x18008482a`

## pseudocode

```c

```
