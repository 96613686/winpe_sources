# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180006f20`
- end: `0x180006f90`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006f20`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180006f4a`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180006f4a`
- `api-ms-win-core-misc-l1-1-0!FormatMessageW` at `0x180006f7a`
- `api-ms-win-core-misc-l1-1-0!FormatMessageW` at `0x180006f7a`

## string_xrefs

- `0x180006f43`: `ntdll.dll`

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
0x180006f20  mov     [rsp+arg_0], rbx
0x180006f25  mov     [rsp+arg_8], rsi
0x180006f2a  push    rdi
0x180006f2b  sub     rsp, 40h
0x180006f2f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006f36  mov     ebx, r8d
0x180006f39  mov     rdi, rdx
0x180006f3c  mov     esi, ecx
0x180006f3e  test    rax, rax
0x180006f41  jnz     short loc_180006F57
0x180006f43  lea     rcx, ModuleName; "ntdll.dll"
0x180006f4a  call    cs:__imp_GetModuleHandleW
0x180006f50  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006f57  mov     [rsp+48h+Arguments], 0; Arguments
0x180006f60  mov     r9d, 400h; dwLanguageId
0x180006f66  mov     [rsp+48h+nSize], ebx; nSize
0x180006f6a  mov     r8d, esi; dwMessageId
0x180006f6d  mov     rdx, rax; lpSource
0x180006f70  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180006f75  mov     ecx, 1A00h; dwFlags
0x180006f7a  call    cs:__imp_FormatMessageW
0x180006f80  mov     rbx, [rsp+48h+arg_0]
0x180006f85  mov     rsi, [rsp+48h+arg_8]
0x180006f8a  add     rsp, 40h
0x180006f8e  pop     rdi
0x180006f8f  retn
```
