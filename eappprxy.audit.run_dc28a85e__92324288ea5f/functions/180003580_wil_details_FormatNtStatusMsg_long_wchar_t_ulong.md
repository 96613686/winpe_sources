# wil::details::FormatNtStatusMsg(long,wchar_t *,ulong)

- ea: `0x180003580`
- end: `0x1800035fd`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEA_WK@Z`
- size: `125`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003580`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800035e0`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800035e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800035aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800035aa`

## string_xrefs

- `0x1800035a3`: `ntdll.dll`

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
0x180003580  mov     [rsp+arg_0], rbx
0x180003585  mov     [rsp+arg_8], rsi
0x18000358a  push    rdi
0x18000358b  sub     rsp, 40h
0x18000358f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003596  mov     ebx, r8d
0x180003599  mov     rdi, rdx
0x18000359c  mov     esi, ecx
0x18000359e  test    rax, rax
0x1800035a1  jnz     short loc_1800035BD
0x1800035a3  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800035aa  call    cs:__imp_GetModuleHandleW
0x1800035b1  nop     dword ptr [rax+rax+00h]
0x1800035b6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800035bd  mov     [rsp+48h+Arguments], 0; Arguments
0x1800035c6  mov     r9d, 400h; dwLanguageId
0x1800035cc  mov     [rsp+48h+nSize], ebx; nSize
0x1800035d0  mov     r8d, esi; dwMessageId
0x1800035d3  mov     rdx, rax; lpSource
0x1800035d6  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1800035db  mov     ecx, 1A00h; dwFlags
0x1800035e0  call    cs:__imp_FormatMessageW
0x1800035e7  nop     dword ptr [rax+rax+00h]
0x1800035ec  mov     rbx, [rsp+48h+arg_0]
0x1800035f1  mov     rsi, [rsp+48h+arg_8]
0x1800035f6  add     rsp, 40h
0x1800035fa  pop     rdi
0x1800035fb  retn
```
