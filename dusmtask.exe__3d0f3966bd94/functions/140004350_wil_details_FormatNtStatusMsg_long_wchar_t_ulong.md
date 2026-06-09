# wil::details::FormatNtStatusMsg(long,wchar_t *,ulong)

- ea: `0x140004350`
- end: `0x1400043c0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEA_WK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140004350`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000437a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000437a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400043aa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400043aa`

## string_xrefs

- `0x140004373`: `ntdll.dll`

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
0x140004350  mov     [rsp+arg_0], rbx
0x140004355  mov     [rsp+arg_8], rsi
0x14000435a  push    rdi
0x14000435b  sub     rsp, 40h
0x14000435f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004366  mov     ebx, r8d
0x140004369  mov     rdi, rdx
0x14000436c  mov     esi, ecx
0x14000436e  test    rax, rax
0x140004371  jnz     short loc_140004387
0x140004373  lea     rcx, ModuleName; "ntdll.dll"
0x14000437a  call    cs:__imp_GetModuleHandleW
0x140004380  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004387  mov     [rsp+48h+Arguments], 0; Arguments
0x140004390  mov     r9d, 400h; dwLanguageId
0x140004396  mov     [rsp+48h+nSize], ebx; nSize
0x14000439a  mov     r8d, esi; dwMessageId
0x14000439d  mov     rdx, rax; lpSource
0x1400043a0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1400043a5  mov     ecx, 1A00h; dwFlags
0x1400043aa  call    cs:__imp_FormatMessageW
0x1400043b0  mov     rbx, [rsp+48h+arg_0]
0x1400043b5  mov     rsi, [rsp+48h+arg_8]
0x1400043ba  add     rsp, 40h
0x1400043be  pop     rdi
0x1400043bf  retn
```
