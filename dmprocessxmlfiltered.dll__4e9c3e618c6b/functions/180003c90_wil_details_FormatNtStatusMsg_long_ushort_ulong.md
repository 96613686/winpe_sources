# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180003c90`
- end: `0x180003d00`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003c90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003cba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003cba`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003cea`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003cea`

## string_xrefs

- `0x180003cb3`: `ntdll.dll`

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
0x180003c90  mov     [rsp+arg_0], rbx
0x180003c95  mov     [rsp+arg_8], rsi
0x180003c9a  push    rdi
0x180003c9b  sub     rsp, 40h
0x180003c9f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003ca6  mov     ebx, r8d
0x180003ca9  mov     rdi, rdx
0x180003cac  mov     esi, ecx
0x180003cae  test    rax, rax
0x180003cb1  jnz     short loc_180003CC7
0x180003cb3  lea     rcx, ModuleName; "ntdll.dll"
0x180003cba  call    cs:__imp_GetModuleHandleW
0x180003cc0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003cc7  mov     [rsp+48h+Arguments], 0; Arguments
0x180003cd0  mov     r9d, 400h; dwLanguageId
0x180003cd6  mov     [rsp+48h+nSize], ebx; nSize
0x180003cda  mov     r8d, esi; dwMessageId
0x180003cdd  mov     rdx, rax; lpSource
0x180003ce0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180003ce5  mov     ecx, 1A00h; dwFlags
0x180003cea  call    cs:__imp_FormatMessageW
0x180003cf0  mov     rbx, [rsp+48h+arg_0]
0x180003cf5  mov     rsi, [rsp+48h+arg_8]
0x180003cfa  add     rsp, 40h
0x180003cfe  pop     rdi
0x180003cff  retn
```
