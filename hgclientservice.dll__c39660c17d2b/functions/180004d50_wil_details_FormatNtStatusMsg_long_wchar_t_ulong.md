# wil::details::FormatNtStatusMsg(long,wchar_t *,ulong)

- ea: `0x180004d50`
- end: `0x180004dc0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEA_WK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004d50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004d7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004d7a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004daa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004daa`

## string_xrefs

- `0x180004d73`: `ntdll.dll`

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
0x180004d50  mov     [rsp+arg_0], rbx
0x180004d55  mov     [rsp+arg_8], rsi
0x180004d5a  push    rdi
0x180004d5b  sub     rsp, 40h
0x180004d5f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004d66  mov     ebx, r8d
0x180004d69  mov     rdi, rdx
0x180004d6c  mov     esi, ecx
0x180004d6e  test    rax, rax
0x180004d71  jnz     short loc_180004D87
0x180004d73  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180004d7a  call    cs:__imp_GetModuleHandleW
0x180004d80  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004d87  mov     [rsp+48h+Arguments], 0; Arguments
0x180004d90  mov     r9d, 400h; dwLanguageId
0x180004d96  mov     [rsp+48h+nSize], ebx; nSize
0x180004d9a  mov     r8d, esi; dwMessageId
0x180004d9d  mov     rdx, rax; lpSource
0x180004da0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180004da5  mov     ecx, 1A00h; dwFlags
0x180004daa  call    cs:__imp_FormatMessageW
0x180004db0  mov     rbx, [rsp+48h+arg_0]
0x180004db5  mov     rsi, [rsp+48h+arg_8]
0x180004dba  add     rsp, 40h
0x180004dbe  pop     rdi
0x180004dbf  retn
```
