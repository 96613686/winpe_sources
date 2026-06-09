# wil::details::FormatNtStatusMsg(long,wchar_t *,ulong)

- ea: `0x1800060c0`
- end: `0x180006130`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEA_WK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800060c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800060ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800060ea`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000611a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000611a`

## string_xrefs

- `0x1800060e3`: `ntdll.dll`

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
0x1800060c0  mov     [rsp+arg_0], rbx
0x1800060c5  mov     [rsp+arg_8], rsi
0x1800060ca  push    rdi
0x1800060cb  sub     rsp, 40h
0x1800060cf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800060d6  mov     ebx, r8d
0x1800060d9  mov     rdi, rdx
0x1800060dc  mov     esi, ecx
0x1800060de  test    rax, rax
0x1800060e1  jnz     short loc_1800060F7
0x1800060e3  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1800060ea  call    cs:__imp_GetModuleHandleW
0x1800060f0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800060f7  mov     [rsp+48h+Arguments], 0; Arguments
0x180006100  mov     r9d, 400h; dwLanguageId
0x180006106  mov     [rsp+48h+nSize], ebx; nSize
0x18000610a  mov     r8d, esi; dwMessageId
0x18000610d  mov     rdx, rax; lpSource
0x180006110  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180006115  mov     ecx, 1A00h; dwFlags
0x18000611a  call    cs:__imp_FormatMessageW
0x180006120  mov     rbx, [rsp+48h+arg_0]
0x180006125  mov     rsi, [rsp+48h+arg_8]
0x18000612a  add     rsp, 40h
0x18000612e  pop     rdi
0x18000612f  retn
```
