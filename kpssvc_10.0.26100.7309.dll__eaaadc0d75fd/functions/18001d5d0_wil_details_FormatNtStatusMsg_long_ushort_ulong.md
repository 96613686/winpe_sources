# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x18001d5d0`
- end: `0x18001d64a`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `122`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001d5d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d5fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d5fa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001d62d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001d62d`

## string_xrefs

- `0x18001d5f3`: `ntdll.dll`

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
0x18001d5d0  mov     [rsp+arg_0], rbx
0x18001d5d5  mov     [rsp+arg_8], rsi
0x18001d5da  push    rdi
0x18001d5db  sub     rsp, 40h
0x18001d5df  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001d5e6  mov     ebx, r8d
0x18001d5e9  mov     rdi, rdx
0x18001d5ec  mov     esi, ecx
0x18001d5ee  test    rax, rax
0x18001d5f1  jnz     short loc_18001D60D
0x18001d5f3  lea     rcx, ModuleName; "ntdll.dll"
0x18001d5fa  call    cs:__imp_GetModuleHandleW
0x18001d601  nop     dword ptr [rax+rax+00h]
0x18001d606  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001d60d  and     [rsp+48h+var_18], 0
0x18001d613  mov     r9d, 400h; dwLanguageId
0x18001d619  mov     [rsp+48h+nSize], ebx; nSize
0x18001d61d  mov     r8d, esi; dwMessageId
0x18001d620  mov     rdx, rax; lpSource
0x18001d623  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18001d628  mov     ecx, 1A00h; dwFlags
0x18001d62d  call    cs:__imp_FormatMessageW
0x18001d634  nop     dword ptr [rax+rax+00h]
0x18001d639  mov     rbx, [rsp+48h+arg_0]
0x18001d63e  mov     rsi, [rsp+48h+arg_8]
0x18001d643  add     rsp, 40h
0x18001d647  pop     rdi
0x18001d648  retn
```
