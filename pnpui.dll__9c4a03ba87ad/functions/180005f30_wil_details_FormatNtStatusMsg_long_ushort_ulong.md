# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180005f30`
- end: `0x180005fa0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005f30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005f5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005f5a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005f8a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005f8a`

## string_xrefs

- `0x180005f53`: `ntdll.dll`

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
0x180005f30  mov     [rsp+arg_0], rbx
0x180005f35  mov     [rsp+arg_8], rsi
0x180005f3a  push    rdi
0x180005f3b  sub     rsp, 40h
0x180005f3f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005f46  mov     ebx, r8d
0x180005f49  mov     rdi, rdx
0x180005f4c  mov     esi, ecx
0x180005f4e  test    rax, rax
0x180005f51  jnz     short loc_180005F67
0x180005f53  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180005f5a  call    cs:__imp_GetModuleHandleW
0x180005f60  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005f67  mov     [rsp+48h+Arguments], 0; Arguments
0x180005f70  mov     r9d, 400h; dwLanguageId
0x180005f76  mov     [rsp+48h+nSize], ebx; nSize
0x180005f7a  mov     r8d, esi; dwMessageId
0x180005f7d  mov     rdx, rax; lpSource
0x180005f80  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180005f85  mov     ecx, 1A00h; dwFlags
0x180005f8a  call    cs:__imp_FormatMessageW
0x180005f90  mov     rbx, [rsp+48h+arg_0]
0x180005f95  mov     rsi, [rsp+48h+arg_8]
0x180005f9a  add     rsp, 40h
0x180005f9e  pop     rdi
0x180005f9f  retn
```
