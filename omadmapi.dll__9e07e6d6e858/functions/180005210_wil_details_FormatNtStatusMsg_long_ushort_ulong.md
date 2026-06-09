# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180005210`
- end: `0x18000528d`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `125`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005210`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000523a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000523a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005270`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005270`

## string_xrefs

- `0x180005233`: `ntdll.dll`

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
0x180005210  mov     [rsp+arg_0], rbx
0x180005215  mov     [rsp+arg_8], rsi
0x18000521a  push    rdi
0x18000521b  sub     rsp, 40h
0x18000521f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005226  mov     ebx, r8d
0x180005229  mov     rdi, rdx
0x18000522c  mov     esi, ecx
0x18000522e  test    rax, rax
0x180005231  jnz     short loc_18000524D
0x180005233  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000523a  call    cs:__imp_GetModuleHandleW
0x180005241  nop     dword ptr [rax+rax+00h]
0x180005246  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000524d  mov     [rsp+48h+Arguments], 0; Arguments
0x180005256  mov     r9d, 400h; dwLanguageId
0x18000525c  mov     [rsp+48h+nSize], ebx; nSize
0x180005260  mov     r8d, esi; dwMessageId
0x180005263  mov     rdx, rax; lpSource
0x180005266  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18000526b  mov     ecx, 1A00h; dwFlags
0x180005270  call    cs:__imp_FormatMessageW
0x180005277  nop     dword ptr [rax+rax+00h]
0x18000527c  mov     rbx, [rsp+48h+arg_0]
0x180005281  mov     rsi, [rsp+48h+arg_8]
0x180005286  add     rsp, 40h
0x18000528a  pop     rdi
0x18000528b  retn
```
