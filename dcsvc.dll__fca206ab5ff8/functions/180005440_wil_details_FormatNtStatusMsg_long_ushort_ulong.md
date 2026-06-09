# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180005440`
- end: `0x1800054b0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005440`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000549a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000549a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000546a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000546a`

## string_xrefs

- `0x180005463`: `ntdll.dll`

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
0x180005440  mov     [rsp+arg_0], rbx
0x180005445  mov     [rsp+arg_8], rsi
0x18000544a  push    rdi
0x18000544b  sub     rsp, 40h
0x18000544f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005456  mov     ebx, r8d
0x180005459  mov     rdi, rdx
0x18000545c  mov     esi, ecx
0x18000545e  test    rax, rax
0x180005461  jnz     short loc_180005477
0x180005463  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000546a  call    cs:__imp_GetModuleHandleW
0x180005470  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005477  mov     [rsp+48h+Arguments], 0; Arguments
0x180005480  mov     r9d, 400h; dwLanguageId
0x180005486  mov     [rsp+48h+nSize], ebx; nSize
0x18000548a  mov     r8d, esi; dwMessageId
0x18000548d  mov     rdx, rax; lpSource
0x180005490  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180005495  mov     ecx, 1A00h; dwFlags
0x18000549a  call    cs:__imp_FormatMessageW
0x1800054a0  mov     rbx, [rsp+48h+arg_0]
0x1800054a5  mov     rsi, [rsp+48h+arg_8]
0x1800054aa  add     rsp, 40h
0x1800054ae  pop     rdi
0x1800054af  retn
```
