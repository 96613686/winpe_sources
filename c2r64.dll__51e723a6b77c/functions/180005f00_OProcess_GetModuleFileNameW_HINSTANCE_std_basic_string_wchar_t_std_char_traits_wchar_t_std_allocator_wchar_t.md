# OProcess::GetModuleFileNameW(HINSTANCE__ *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180005f00`
- end: `0x180006073`
- name: `?GetModuleFileNameW@OProcess@@SAXPEAUHINSTANCE__@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `371`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180019848`
- `0x180047640`
- `0x180138d68`

## callees

- `0x180005f00`
- `0x180006074`
- `0x1800081bc`
- `0x18002e43c`
- `0x18003e690`
- `0x1800409e0`
- `0x180044444`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005f93`
- `KERNEL32!GetLastError` at `0x180005f93`
- `KERNEL32!GetModuleFileNameW` at `0x180005f87`
- `KERNEL32!GetModuleFileNameW` at `0x180005f87`

## string_xrefs

- `0x180005f99`: `Failed to retrieve process path`
- `0x18000604b`: `Module file name is longer than MAX_PATH`

## pseudocode

```c

```
