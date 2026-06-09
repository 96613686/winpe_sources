# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x14000faf0`
- end: `0x14000fb60`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x14000faf0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000fb1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000fb1a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000fb4a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000fb4a`

## string_xrefs

- `0x14000fb13`: `ntdll.dll`

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
0x14000faf0  mov     [rsp+arg_0], rbx
0x14000faf5  mov     [rsp+arg_8], rsi
0x14000fafa  push    rdi
0x14000fafb  sub     rsp, 40h
0x14000faff  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000fb06  mov     ebx, r8d
0x14000fb09  mov     rdi, rdx
0x14000fb0c  mov     esi, ecx
0x14000fb0e  test    rax, rax
0x14000fb11  jnz     short loc_14000FB27
0x14000fb13  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x14000fb1a  call    cs:__imp_GetModuleHandleW
0x14000fb20  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000fb27  mov     [rsp+48h+Arguments], 0; Arguments
0x14000fb30  mov     r9d, 400h; dwLanguageId
0x14000fb36  mov     [rsp+48h+nSize], ebx; nSize
0x14000fb3a  mov     r8d, esi; dwMessageId
0x14000fb3d  mov     rdx, rax; lpSource
0x14000fb40  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x14000fb45  mov     ecx, 1A00h; dwFlags
0x14000fb4a  call    cs:__imp_FormatMessageW
0x14000fb50  mov     rbx, [rsp+48h+arg_0]
0x14000fb55  mov     rsi, [rsp+48h+arg_8]
0x14000fb5a  add     rsp, 40h
0x14000fb5e  pop     rdi
0x14000fb5f  retn
```
