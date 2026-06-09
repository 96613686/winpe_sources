# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180005970`
- end: `0x1800059e0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005970`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000599a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000599a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800059ca`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800059ca`

## string_xrefs

- `0x180005993`: `ntdll.dll`

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
0x180005970  mov     [rsp+arg_0], rbx
0x180005975  mov     [rsp+arg_8], rsi
0x18000597a  push    rdi
0x18000597b  sub     rsp, 40h
0x18000597f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005986  mov     ebx, r8d
0x180005989  mov     rdi, rdx
0x18000598c  mov     esi, ecx
0x18000598e  test    rax, rax
0x180005991  jnz     short loc_1800059A7
0x180005993  lea     rcx, ModuleName; "ntdll.dll"
0x18000599a  call    cs:__imp_GetModuleHandleW
0x1800059a0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800059a7  mov     [rsp+48h+Arguments], 0; Arguments
0x1800059b0  mov     r9d, 400h; dwLanguageId
0x1800059b6  mov     [rsp+48h+nSize], ebx; nSize
0x1800059ba  mov     r8d, esi; dwMessageId
0x1800059bd  mov     rdx, rax; lpSource
0x1800059c0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1800059c5  mov     ecx, 1A00h; dwFlags
0x1800059ca  call    cs:__imp_FormatMessageW
0x1800059d0  mov     rbx, [rsp+48h+arg_0]
0x1800059d5  mov     rsi, [rsp+48h+arg_8]
0x1800059da  add     rsp, 40h
0x1800059de  pop     rdi
0x1800059df  retn
```
