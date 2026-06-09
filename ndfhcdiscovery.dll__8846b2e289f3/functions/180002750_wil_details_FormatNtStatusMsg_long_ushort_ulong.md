# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180002750`
- end: `0x1800027cd`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `125`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002750`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1800027b0`
- `KERNEL32!FormatMessageW` at `0x1800027b0`
- `KERNEL32!GetModuleHandleW` at `0x18000277a`
- `KERNEL32!GetModuleHandleW` at `0x18000277a`

## string_xrefs

- `0x180002773`: `ntdll.dll`

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
0x180002750  mov     [rsp+arg_0], rbx
0x180002755  mov     [rsp+arg_8], rsi
0x18000275a  push    rdi
0x18000275b  sub     rsp, 40h
0x18000275f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180002766  mov     ebx, r8d
0x180002769  mov     rdi, rdx
0x18000276c  mov     esi, ecx
0x18000276e  test    rax, rax
0x180002771  jnz     short loc_18000278D
0x180002773  lea     rcx, ModuleName; "ntdll.dll"
0x18000277a  call    cs:__imp_GetModuleHandleW
0x180002781  nop     dword ptr [rax+rax+00h]
0x180002786  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000278d  mov     [rsp+48h+Arguments], 0; Arguments
0x180002796  mov     r9d, 400h; dwLanguageId
0x18000279c  mov     [rsp+48h+nSize], ebx; nSize
0x1800027a0  mov     r8d, esi; dwMessageId
0x1800027a3  mov     rdx, rax; lpSource
0x1800027a6  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1800027ab  mov     ecx, 1A00h; dwFlags
0x1800027b0  call    cs:__imp_FormatMessageW
0x1800027b7  nop     dword ptr [rax+rax+00h]
0x1800027bc  mov     rbx, [rsp+48h+arg_0]
0x1800027c1  mov     rsi, [rsp+48h+arg_8]
0x1800027c6  add     rsp, 40h
0x1800027ca  pop     rdi
0x1800027cb  retn
```
