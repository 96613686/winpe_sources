# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180005350`
- end: `0x1800053ca`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `122`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005350`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000537a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000537a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800053ad`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800053ad`

## string_xrefs

- `0x180005373`: `ntdll.dll`

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
0x180005350  mov     [rsp+arg_0], rbx
0x180005355  mov     [rsp+arg_8], rsi
0x18000535a  push    rdi
0x18000535b  sub     rsp, 40h
0x18000535f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005366  mov     ebx, r8d
0x180005369  mov     rdi, rdx
0x18000536c  mov     esi, ecx
0x18000536e  test    rax, rax
0x180005371  jnz     short loc_18000538D
0x180005373  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000537a  call    cs:__imp_GetModuleHandleW
0x180005381  nop     dword ptr [rax+rax+00h]
0x180005386  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000538d  and     [rsp+48h+var_18], 0
0x180005393  mov     r9d, 400h; dwLanguageId
0x180005399  mov     [rsp+48h+nSize], ebx; nSize
0x18000539d  mov     r8d, esi; dwMessageId
0x1800053a0  mov     rdx, rax; lpSource
0x1800053a3  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1800053a8  mov     ecx, 1A00h; dwFlags
0x1800053ad  call    cs:__imp_FormatMessageW
0x1800053b4  nop     dword ptr [rax+rax+00h]
0x1800053b9  mov     rbx, [rsp+48h+arg_0]
0x1800053be  mov     rsi, [rsp+48h+arg_8]
0x1800053c3  add     rsp, 40h
0x1800053c7  pop     rdi
0x1800053c8  retn
```
