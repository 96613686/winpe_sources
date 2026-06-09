# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140004d20`
- end: `0x140004d90`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140004d20`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x140004d7a`
- `KERNEL32!FormatMessageW` at `0x140004d7a`
- `KERNEL32!GetModuleHandleW` at `0x140004d4a`
- `KERNEL32!GetModuleHandleW` at `0x140004d4a`

## string_xrefs

- `0x140004d43`: `ntdll.dll`

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
0x140004d20  mov     [rsp+arg_0], rbx
0x140004d25  mov     [rsp+arg_8], rsi
0x140004d2a  push    rdi
0x140004d2b  sub     rsp, 40h
0x140004d2f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004d36  mov     ebx, r8d
0x140004d39  mov     rdi, rdx
0x140004d3c  mov     esi, ecx
0x140004d3e  test    rax, rax
0x140004d41  jnz     short loc_140004D57
0x140004d43  lea     rcx, aNtdllDll; "ntdll.dll"
0x140004d4a  call    cs:__imp_GetModuleHandleW
0x140004d50  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004d57  mov     [rsp+48h+Arguments], 0; Arguments
0x140004d60  mov     r9d, 400h; dwLanguageId
0x140004d66  mov     [rsp+48h+nSize], ebx; nSize
0x140004d6a  mov     r8d, esi; dwMessageId
0x140004d6d  mov     rdx, rax; lpSource
0x140004d70  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x140004d75  mov     ecx, 1A00h; dwFlags
0x140004d7a  call    cs:__imp_FormatMessageW
0x140004d80  mov     rbx, [rsp+48h+arg_0]
0x140004d85  mov     rsi, [rsp+48h+arg_8]
0x140004d8a  add     rsp, 40h
0x140004d8e  pop     rdi
0x140004d8f  retn
```
