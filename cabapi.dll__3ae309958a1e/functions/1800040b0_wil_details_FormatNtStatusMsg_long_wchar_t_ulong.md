# wil::details::FormatNtStatusMsg(long,wchar_t *,ulong)

- ea: `0x1800040b0`
- end: `0x180004120`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEA_WK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800040b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800040da`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800040da`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000410a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000410a`

## string_xrefs

- `0x1800040d3`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::FormatNtStatusMsg(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)
{
  HMODULE ModuleHandleW; // rax

  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x1800040b0  mov     [rsp+arg_0], rbx
0x1800040b5  mov     [rsp+arg_8], rsi
0x1800040ba  push    rdi
0x1800040bb  sub     rsp, 40h
0x1800040bf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800040c6  mov     ebx, r8d
0x1800040c9  mov     rdi, rdx
0x1800040cc  mov     esi, ecx
0x1800040ce  test    rax, rax
0x1800040d1  jnz     short loc_1800040E7
0x1800040d3  lea     rcx, LibFileName; "ntdll.dll"
0x1800040da  call    cs:__imp_GetModuleHandleW
0x1800040e0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800040e7  mov     [rsp+48h+Arguments], 0; Arguments
0x1800040f0  mov     r9d, 400h; dwLanguageId
0x1800040f6  mov     [rsp+48h+nSize], ebx; nSize
0x1800040fa  mov     r8d, esi; dwMessageId
0x1800040fd  mov     rdx, rax; lpSource
0x180004100  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180004105  mov     ecx, 1A00h; dwFlags
0x18000410a  call    cs:__imp_FormatMessageW
0x180004110  mov     rbx, [rsp+48h+arg_0]
0x180004115  mov     rsi, [rsp+48h+arg_8]
0x18000411a  add     rsp, 40h
0x18000411e  pop     rdi
0x18000411f  retn
```
