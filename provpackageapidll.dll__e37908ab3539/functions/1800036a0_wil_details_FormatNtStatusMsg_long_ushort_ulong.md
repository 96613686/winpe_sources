# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x1800036a0`
- end: `0x180003710`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800036a0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800036ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800036ca`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800036fa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800036fa`

## string_xrefs

- `0x1800036c3`: `ntdll.dll`

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
0x1800036a0  mov     [rsp+arg_0], rbx
0x1800036a5  mov     [rsp+arg_8], rsi
0x1800036aa  push    rdi
0x1800036ab  sub     rsp, 40h
0x1800036af  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800036b6  mov     ebx, r8d
0x1800036b9  mov     rdi, rdx
0x1800036bc  mov     esi, ecx
0x1800036be  test    rax, rax
0x1800036c1  jnz     short loc_1800036D7
0x1800036c3  lea     rcx, ModuleName; "ntdll.dll"
0x1800036ca  call    cs:__imp_GetModuleHandleW
0x1800036d0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800036d7  mov     [rsp+48h+Arguments], 0; Arguments
0x1800036e0  mov     r9d, 400h; dwLanguageId
0x1800036e6  mov     [rsp+48h+nSize], ebx; nSize
0x1800036ea  mov     r8d, esi; dwMessageId
0x1800036ed  mov     rdx, rax; lpSource
0x1800036f0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1800036f5  mov     ecx, 1A00h; dwFlags
0x1800036fa  call    cs:__imp_FormatMessageW
0x180003700  mov     rbx, [rsp+48h+arg_0]
0x180003705  mov     rsi, [rsp+48h+arg_8]
0x18000370a  add     rsp, 40h
0x18000370e  pop     rdi
0x18000370f  retn
```
