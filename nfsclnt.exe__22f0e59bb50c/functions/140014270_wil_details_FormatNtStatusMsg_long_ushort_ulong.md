# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140014270`
- end: `0x1400142e0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140014270`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14001429a`
- `KERNEL32!GetModuleHandleW` at `0x14001429a`
- `KERNEL32!FormatMessageW` at `0x1400142ca`
- `KERNEL32!FormatMessageW` at `0x1400142ca`

## string_xrefs

- `0x140014293`: `ntdll.dll`

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
0x140014270  mov     [rsp+arg_0], rbx
0x140014275  mov     [rsp+arg_8], rsi
0x14001427a  push    rdi
0x14001427b  sub     rsp, 40h
0x14001427f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140014286  mov     ebx, r8d
0x140014289  mov     rdi, rdx
0x14001428c  mov     esi, ecx
0x14001428e  test    rax, rax
0x140014291  jnz     short loc_1400142A7
0x140014293  lea     rcx, ModuleName; "ntdll.dll"
0x14001429a  call    cs:__imp_GetModuleHandleW
0x1400142a0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400142a7  mov     [rsp+48h+Arguments], 0; Arguments
0x1400142b0  mov     r9d, 400h; dwLanguageId
0x1400142b6  mov     [rsp+48h+nSize], ebx; nSize
0x1400142ba  mov     r8d, esi; dwMessageId
0x1400142bd  mov     rdx, rax; lpSource
0x1400142c0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1400142c5  mov     ecx, 1A00h; dwFlags
0x1400142ca  call    cs:__imp_FormatMessageW
0x1400142d0  mov     rbx, [rsp+48h+arg_0]
0x1400142d5  mov     rsi, [rsp+48h+arg_8]
0x1400142da  add     rsp, 40h
0x1400142de  pop     rdi
0x1400142df  retn
```
