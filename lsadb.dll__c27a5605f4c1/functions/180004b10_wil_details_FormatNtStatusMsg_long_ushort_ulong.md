# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180004b10`
- end: `0x180004b80`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004b10`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004b6a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004b6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004b3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004b3a`

## string_xrefs

- `0x180004b33`: `ntdll.dll`

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
0x180004b10  mov     [rsp+arg_0], rbx
0x180004b15  mov     [rsp+arg_8], rsi
0x180004b1a  push    rdi
0x180004b1b  sub     rsp, 40h
0x180004b1f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004b26  mov     ebx, r8d
0x180004b29  mov     rdi, rdx
0x180004b2c  mov     esi, ecx
0x180004b2e  test    rax, rax
0x180004b31  jnz     short loc_180004B47
0x180004b33  lea     rcx, ModuleName; "ntdll.dll"
0x180004b3a  call    cs:__imp_GetModuleHandleW
0x180004b40  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004b47  mov     [rsp+48h+Arguments], 0; Arguments
0x180004b50  mov     r9d, 400h; dwLanguageId
0x180004b56  mov     [rsp+48h+nSize], ebx; nSize
0x180004b5a  mov     r8d, esi; dwMessageId
0x180004b5d  mov     rdx, rax; lpSource
0x180004b60  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180004b65  mov     ecx, 1A00h; dwFlags
0x180004b6a  call    cs:__imp_FormatMessageW
0x180004b70  mov     rbx, [rsp+48h+arg_0]
0x180004b75  mov     rsi, [rsp+48h+arg_8]
0x180004b7a  add     rsp, 40h
0x180004b7e  pop     rdi
0x180004b7f  retn
```
