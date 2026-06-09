# wil::details::FormatNtStatusMsg(long,wchar_t *,ulong)

- ea: `0x1800054b0`
- end: `0x180005520`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEA_WK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800054b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800054da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800054da`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000550a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000550a`

## string_xrefs

- `0x1800054d3`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::FormatNtStatusMsg(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)
{
  HMODULE ModuleHandleW; // rax

  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  FormatMessageW(0x1A00u, ModuleHandleW, dwMessageId, 0x400u, lpBuffer, nSize, 0);
}

```

## disassembly

```asm
0x1800054b0  mov     [rsp+arg_0], rbx
0x1800054b5  mov     [rsp+arg_8], rsi
0x1800054ba  push    rdi
0x1800054bb  sub     rsp, 40h
0x1800054bf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800054c6  mov     ebx, r8d
0x1800054c9  mov     rdi, rdx
0x1800054cc  mov     esi, ecx
0x1800054ce  test    rax, rax
0x1800054d1  jnz     short loc_1800054E7
0x1800054d3  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800054da  call    cs:__imp_GetModuleHandleW
0x1800054e0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800054e7  mov     [rsp+48h+Arguments], 0; Arguments
0x1800054f0  mov     r9d, 400h; dwLanguageId
0x1800054f6  mov     [rsp+48h+nSize], ebx; nSize
0x1800054fa  mov     r8d, esi; dwMessageId
0x1800054fd  mov     rdx, rax; lpSource
0x180005500  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180005505  mov     ecx, 1A00h; dwFlags
0x18000550a  call    cs:__imp_FormatMessageW
0x180005510  mov     rbx, [rsp+48h+arg_0]
0x180005515  mov     rsi, [rsp+48h+arg_8]
0x18000551a  add     rsp, 40h
0x18000551e  pop     rdi
0x18000551f  retn
```
