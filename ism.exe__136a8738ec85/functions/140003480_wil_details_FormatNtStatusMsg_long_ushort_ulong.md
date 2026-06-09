# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140003480`
- end: `0x1400034f0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140003480`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400034da`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400034da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400034aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400034aa`

## string_xrefs

- `0x1400034a3`: `ntdll.dll`

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
0x140003480  mov     [rsp+arg_0], rbx
0x140003485  mov     [rsp+arg_8], rsi
0x14000348a  push    rdi
0x14000348b  sub     rsp, 40h
0x14000348f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140003496  mov     ebx, r8d
0x140003499  mov     rdi, rdx
0x14000349c  mov     esi, ecx
0x14000349e  test    rax, rax
0x1400034a1  jnz     short loc_1400034B7
0x1400034a3  lea     rcx, ModuleName; "ntdll.dll"
0x1400034aa  call    cs:__imp_GetModuleHandleW
0x1400034b0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400034b7  mov     [rsp+48h+Arguments], 0; Arguments
0x1400034c0  mov     r9d, 400h; dwLanguageId
0x1400034c6  mov     [rsp+48h+nSize], ebx; nSize
0x1400034ca  mov     r8d, esi; dwMessageId
0x1400034cd  mov     rdx, rax; lpSource
0x1400034d0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1400034d5  mov     ecx, 1A00h; dwFlags
0x1400034da  call    cs:__imp_FormatMessageW
0x1400034e0  mov     rbx, [rsp+48h+arg_0]
0x1400034e5  mov     rsi, [rsp+48h+arg_8]
0x1400034ea  add     rsp, 40h
0x1400034ee  pop     rdi
0x1400034ef  retn
```
