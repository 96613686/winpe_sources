# CWinHttpSessionManager::WinHttpCloseInternal(std::shared_ptr<std::tuple<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong,ulong>> &)

- ea: `0x1800f2b28`
- end: `0x1800f2c54`
- name: `?WinHttpCloseInternal@CWinHttpSessionManager@@AEAAXAEAV?$shared_ptr@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@@std@@@Z`
- size: `300`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x1800f0230`
- `0x1800f0628`

## callees

- `0x18000ffb0`
- `0x180028df8`
- `0x1800303d0`
- `0x180063814`
- `0x1800d1094`
- `0x1800d10b8`
- `0x1800d113c`
- `0x1800d1154`
- `0x1800f2b28`
- `0x1800f305c`
- `0x1800f32f0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800f2be6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800f2be6`
- `WINHTTP!WinHttpCloseHandle` at `0x1800f2bb2`
- `WINHTTP!WinHttpCloseHandle` at `0x1800f2bb2`

## string_xrefs

- `0x1800f2c14`: `Attempting to call close on something not present`

## pseudocode

```c

```
