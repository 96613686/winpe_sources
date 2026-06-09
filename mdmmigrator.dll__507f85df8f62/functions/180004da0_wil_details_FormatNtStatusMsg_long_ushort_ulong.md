# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180004da0`
- end: `0x180004e10`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004da0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004dca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004dca`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004dfa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004dfa`

## string_xrefs

- `0x180004dc3`: `ntdll.dll`

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
0x180004da0  mov     [rsp+arg_0], rbx
0x180004da5  mov     [rsp+arg_8], rsi
0x180004daa  push    rdi
0x180004dab  sub     rsp, 40h
0x180004daf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004db6  mov     ebx, r8d
0x180004db9  mov     rdi, rdx
0x180004dbc  mov     esi, ecx
0x180004dbe  test    rax, rax
0x180004dc1  jnz     short loc_180004DD7
0x180004dc3  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180004dca  call    cs:__imp_GetModuleHandleW
0x180004dd0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004dd7  mov     [rsp+48h+Arguments], 0; Arguments
0x180004de0  mov     r9d, 400h; dwLanguageId
0x180004de6  mov     [rsp+48h+nSize], ebx; nSize
0x180004dea  mov     r8d, esi; dwMessageId
0x180004ded  mov     rdx, rax; lpSource
0x180004df0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180004df5  mov     ecx, 1A00h; dwFlags
0x180004dfa  call    cs:__imp_FormatMessageW
0x180004e00  mov     rbx, [rsp+48h+arg_0]
0x180004e05  mov     rsi, [rsp+48h+arg_8]
0x180004e0a  add     rsp, 40h
0x180004e0e  pop     rdi
0x180004e0f  retn
```
