# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x1800043f0`
- end: `0x180004460`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800043f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000441a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000441a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000444a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000444a`

## string_xrefs

- `0x180004413`: `ntdll.dll`

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
0x1800043f0  mov     [rsp+arg_0], rbx
0x1800043f5  mov     [rsp+arg_8], rsi
0x1800043fa  push    rdi
0x1800043fb  sub     rsp, 40h
0x1800043ff  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004406  mov     ebx, r8d
0x180004409  mov     rdi, rdx
0x18000440c  mov     esi, ecx
0x18000440e  test    rax, rax
0x180004411  jnz     short loc_180004427
0x180004413  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000441a  call    cs:__imp_GetModuleHandleW
0x180004420  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004427  mov     [rsp+48h+Arguments], 0; Arguments
0x180004430  mov     r9d, 400h; dwLanguageId
0x180004436  mov     [rsp+48h+nSize], ebx; nSize
0x18000443a  mov     r8d, esi; dwMessageId
0x18000443d  mov     rdx, rax; lpSource
0x180004440  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180004445  mov     ecx, 1A00h; dwFlags
0x18000444a  call    cs:__imp_FormatMessageW
0x180004450  mov     rbx, [rsp+48h+arg_0]
0x180004455  mov     rsi, [rsp+48h+arg_8]
0x18000445a  add     rsp, 40h
0x18000445e  pop     rdi
0x18000445f  retn
```
