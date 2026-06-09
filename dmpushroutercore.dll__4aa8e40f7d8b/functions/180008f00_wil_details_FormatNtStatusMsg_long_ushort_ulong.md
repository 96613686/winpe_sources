# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180008f00`
- end: `0x180008f70`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008f00`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008f5a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008f5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008f2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008f2a`

## string_xrefs

- `0x180008f23`: `ntdll.dll`

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
0x180008f00  mov     [rsp+arg_0], rbx
0x180008f05  mov     [rsp+arg_8], rsi
0x180008f0a  push    rdi
0x180008f0b  sub     rsp, 40h
0x180008f0f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008f16  mov     ebx, r8d
0x180008f19  mov     rdi, rdx
0x180008f1c  mov     esi, ecx
0x180008f1e  test    rax, rax
0x180008f21  jnz     short loc_180008F37
0x180008f23  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180008f2a  call    cs:__imp_GetModuleHandleW
0x180008f30  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008f37  mov     [rsp+48h+Arguments], 0; Arguments
0x180008f40  mov     r9d, 400h; dwLanguageId
0x180008f46  mov     [rsp+48h+nSize], ebx; nSize
0x180008f4a  mov     r8d, esi; dwMessageId
0x180008f4d  mov     rdx, rax; lpSource
0x180008f50  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180008f55  mov     ecx, 1A00h; dwFlags
0x180008f5a  call    cs:__imp_FormatMessageW
0x180008f60  mov     rbx, [rsp+48h+arg_0]
0x180008f65  mov     rsi, [rsp+48h+arg_8]
0x180008f6a  add     rsp, 40h
0x180008f6e  pop     rdi
0x180008f6f  retn
```
