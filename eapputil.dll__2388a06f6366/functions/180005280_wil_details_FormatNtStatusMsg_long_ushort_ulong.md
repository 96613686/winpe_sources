# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180005280`
- end: `0x1800052f0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005280`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800052aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800052aa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800052da`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800052da`

## string_xrefs

- `0x1800052a3`: `ntdll.dll`

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
0x180005280  mov     [rsp+arg_0], rbx
0x180005285  mov     [rsp+arg_8], rsi
0x18000528a  push    rdi
0x18000528b  sub     rsp, 40h
0x18000528f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005296  mov     ebx, r8d
0x180005299  mov     rdi, rdx
0x18000529c  mov     esi, ecx
0x18000529e  test    rax, rax
0x1800052a1  jnz     short loc_1800052B7
0x1800052a3  lea     rcx, ModuleName; "ntdll.dll"
0x1800052aa  call    cs:__imp_GetModuleHandleW
0x1800052b0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800052b7  mov     [rsp+48h+Arguments], 0; Arguments
0x1800052c0  mov     r9d, 400h; dwLanguageId
0x1800052c6  mov     [rsp+48h+nSize], ebx; nSize
0x1800052ca  mov     r8d, esi; dwMessageId
0x1800052cd  mov     rdx, rax; lpSource
0x1800052d0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1800052d5  mov     ecx, 1A00h; dwFlags
0x1800052da  call    cs:__imp_FormatMessageW
0x1800052e0  mov     rbx, [rsp+48h+arg_0]
0x1800052e5  mov     rsi, [rsp+48h+arg_8]
0x1800052ea  add     rsp, 40h
0x1800052ee  pop     rdi
0x1800052ef  retn
```
