# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180023df0`
- end: `0x180023e60`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180023df0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180023e1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180023e1a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180023e4a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180023e4a`

## string_xrefs

- `0x180023e13`: `ntdll.dll`

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
0x180023df0  mov     [rsp+arg_0], rbx
0x180023df5  mov     [rsp+arg_8], rsi
0x180023dfa  push    rdi
0x180023dfb  sub     rsp, 40h
0x180023dff  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180023e06  mov     ebx, r8d
0x180023e09  mov     rdi, rdx
0x180023e0c  mov     esi, ecx
0x180023e0e  test    rax, rax
0x180023e11  jnz     short loc_180023E27
0x180023e13  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180023e1a  call    cs:__imp_GetModuleHandleW
0x180023e20  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180023e27  mov     [rsp+48h+Arguments], 0; Arguments
0x180023e30  mov     r9d, 400h; dwLanguageId
0x180023e36  mov     [rsp+48h+nSize], ebx; nSize
0x180023e3a  mov     r8d, esi; dwMessageId
0x180023e3d  mov     rdx, rax; lpSource
0x180023e40  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180023e45  mov     ecx, 1A00h; dwFlags
0x180023e4a  call    cs:__imp_FormatMessageW
0x180023e50  mov     rbx, [rsp+48h+arg_0]
0x180023e55  mov     rsi, [rsp+48h+arg_8]
0x180023e5a  add     rsp, 40h
0x180023e5e  pop     rdi
0x180023e5f  retn
```
