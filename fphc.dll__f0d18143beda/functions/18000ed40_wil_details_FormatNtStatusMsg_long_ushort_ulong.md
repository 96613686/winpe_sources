# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x18000ed40`
- end: `0x18000edb0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000ed40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ed6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ed6a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000ed9a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000ed9a`

## string_xrefs

- `0x18000ed63`: `ntdll.dll`

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
0x18000ed40  mov     [rsp+arg_0], rbx
0x18000ed45  mov     [rsp+arg_8], rsi
0x18000ed4a  push    rdi
0x18000ed4b  sub     rsp, 40h
0x18000ed4f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ed56  mov     ebx, r8d
0x18000ed59  mov     rdi, rdx
0x18000ed5c  mov     esi, ecx
0x18000ed5e  test    rax, rax
0x18000ed61  jnz     short loc_18000ED77
0x18000ed63  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000ed6a  call    cs:__imp_GetModuleHandleW
0x18000ed70  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ed77  mov     [rsp+48h+Arguments], 0; Arguments
0x18000ed80  mov     r9d, 400h; dwLanguageId
0x18000ed86  mov     [rsp+48h+nSize], ebx; nSize
0x18000ed8a  mov     r8d, esi; dwMessageId
0x18000ed8d  mov     rdx, rax; lpSource
0x18000ed90  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18000ed95  mov     ecx, 1A00h; dwFlags
0x18000ed9a  call    cs:__imp_FormatMessageW
0x18000eda0  mov     rbx, [rsp+48h+arg_0]
0x18000eda5  mov     rsi, [rsp+48h+arg_8]
0x18000edaa  add     rsp, 40h
0x18000edae  pop     rdi
0x18000edaf  retn
```
