# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140009e00`
- end: `0x140009e7d`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `125`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140009e00`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x140009e60`
- `KERNEL32!FormatMessageW` at `0x140009e60`
- `KERNEL32!GetModuleHandleW` at `0x140009e2a`
- `KERNEL32!GetModuleHandleW` at `0x140009e2a`

## string_xrefs

- `0x140009e23`: `ntdll.dll`

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
0x140009e00  mov     [rsp+arg_0], rbx
0x140009e05  mov     [rsp+arg_8], rsi
0x140009e0a  push    rdi
0x140009e0b  sub     rsp, 40h
0x140009e0f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009e16  mov     ebx, r8d
0x140009e19  mov     rdi, rdx
0x140009e1c  mov     esi, ecx
0x140009e1e  test    rax, rax
0x140009e21  jnz     short loc_140009E3D
0x140009e23  lea     rcx, ModuleName; "ntdll.dll"
0x140009e2a  call    cs:__imp_GetModuleHandleW
0x140009e31  nop     dword ptr [rax+rax+00h]
0x140009e36  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009e3d  mov     [rsp+48h+Arguments], 0; Arguments
0x140009e46  mov     r9d, 400h; dwLanguageId
0x140009e4c  mov     [rsp+48h+nSize], ebx; nSize
0x140009e50  mov     r8d, esi; dwMessageId
0x140009e53  mov     rdx, rax; lpSource
0x140009e56  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x140009e5b  mov     ecx, 1A00h; dwFlags
0x140009e60  call    cs:__imp_FormatMessageW
0x140009e67  nop     dword ptr [rax+rax+00h]
0x140009e6c  mov     rbx, [rsp+48h+arg_0]
0x140009e71  mov     rsi, [rsp+48h+arg_8]
0x140009e76  add     rsp, 40h
0x140009e7a  pop     rdi
0x140009e7b  retn
```
