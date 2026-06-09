# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140006a50`
- end: `0x140006ac0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140006a50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006a7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006a7a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140006aaa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140006aaa`

## string_xrefs

- `0x140006a73`: `ntdll.dll`

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
0x140006a50  mov     [rsp+arg_0], rbx
0x140006a55  mov     [rsp+arg_8], rsi
0x140006a5a  push    rdi
0x140006a5b  sub     rsp, 40h
0x140006a5f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140006a66  mov     ebx, r8d
0x140006a69  mov     rdi, rdx
0x140006a6c  mov     esi, ecx
0x140006a6e  test    rax, rax
0x140006a71  jnz     short loc_140006A87
0x140006a73  lea     rcx, ModuleName; "ntdll.dll"
0x140006a7a  call    cs:__imp_GetModuleHandleW
0x140006a80  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140006a87  mov     [rsp+48h+Arguments], 0; Arguments
0x140006a90  mov     r9d, 400h; dwLanguageId
0x140006a96  mov     [rsp+48h+nSize], ebx; nSize
0x140006a9a  mov     r8d, esi; dwMessageId
0x140006a9d  mov     rdx, rax; lpSource
0x140006aa0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x140006aa5  mov     ecx, 1A00h; dwFlags
0x140006aaa  call    cs:__imp_FormatMessageW
0x140006ab0  mov     rbx, [rsp+48h+arg_0]
0x140006ab5  mov     rsi, [rsp+48h+arg_8]
0x140006aba  add     rsp, 40h
0x140006abe  pop     rdi
0x140006abf  retn
```
