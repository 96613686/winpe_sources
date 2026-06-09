# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180005950`
- end: `0x1800059c0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005950`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1800059aa`
- `KERNEL32!FormatMessageW` at `0x1800059aa`
- `KERNEL32!GetModuleHandleW` at `0x18000597a`
- `KERNEL32!GetModuleHandleW` at `0x18000597a`

## string_xrefs

- `0x180005973`: `ntdll.dll`

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
0x180005950  mov     [rsp+arg_0], rbx
0x180005955  mov     [rsp+arg_8], rsi
0x18000595a  push    rdi
0x18000595b  sub     rsp, 40h
0x18000595f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005966  mov     ebx, r8d
0x180005969  mov     rdi, rdx
0x18000596c  mov     esi, ecx
0x18000596e  test    rax, rax
0x180005971  jnz     short loc_180005987
0x180005973  lea     rcx, ModuleName; "ntdll.dll"
0x18000597a  call    cs:__imp_GetModuleHandleW
0x180005980  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005987  mov     [rsp+48h+Arguments], 0; Arguments
0x180005990  mov     r9d, 400h; dwLanguageId
0x180005996  mov     [rsp+48h+nSize], ebx; nSize
0x18000599a  mov     r8d, esi; dwMessageId
0x18000599d  mov     rdx, rax; lpSource
0x1800059a0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1800059a5  mov     ecx, 1A00h; dwFlags
0x1800059aa  call    cs:__imp_FormatMessageW
0x1800059b0  mov     rbx, [rsp+48h+arg_0]
0x1800059b5  mov     rsi, [rsp+48h+arg_8]
0x1800059ba  add     rsp, 40h
0x1800059be  pop     rdi
0x1800059bf  retn
```
