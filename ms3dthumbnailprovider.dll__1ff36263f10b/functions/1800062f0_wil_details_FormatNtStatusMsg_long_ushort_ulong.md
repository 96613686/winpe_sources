# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x1800062f0`
- end: `0x180006360`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800062f0`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18000634a`
- `KERNEL32!FormatMessageW` at `0x18000634a`
- `KERNEL32!GetModuleHandleW` at `0x18000631a`
- `KERNEL32!GetModuleHandleW` at `0x18000631a`

## string_xrefs

- `0x180006313`: `ntdll.dll`

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
0x1800062f0  mov     [rsp+arg_0], rbx
0x1800062f5  mov     [rsp+arg_8], rsi
0x1800062fa  push    rdi
0x1800062fb  sub     rsp, 40h
0x1800062ff  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006306  mov     ebx, r8d
0x180006309  mov     rdi, rdx
0x18000630c  mov     esi, ecx
0x18000630e  test    rax, rax
0x180006311  jnz     short loc_180006327
0x180006313  lea     rcx, ModuleName; "ntdll.dll"
0x18000631a  call    cs:__imp_GetModuleHandleW
0x180006320  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006327  mov     [rsp+48h+Arguments], 0; Arguments
0x180006330  mov     r9d, 400h; dwLanguageId
0x180006336  mov     [rsp+48h+nSize], ebx; nSize
0x18000633a  mov     r8d, esi; dwMessageId
0x18000633d  mov     rdx, rax; lpSource
0x180006340  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180006345  mov     ecx, 1A00h; dwFlags
0x18000634a  call    cs:__imp_FormatMessageW
0x180006350  mov     rbx, [rsp+48h+arg_0]
0x180006355  mov     rsi, [rsp+48h+arg_8]
0x18000635a  add     rsp, 40h
0x18000635e  pop     rdi
0x18000635f  retn
```
