# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180004fe0`
- end: `0x180005050`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004fe0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000500a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000500a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000503a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000503a`

## string_xrefs

- `0x180005003`: `ntdll.dll`

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
0x180004fe0  mov     [rsp+arg_0], rbx
0x180004fe5  mov     [rsp+arg_8], rsi
0x180004fea  push    rdi
0x180004feb  sub     rsp, 40h
0x180004fef  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004ff6  mov     ebx, r8d
0x180004ff9  mov     rdi, rdx
0x180004ffc  mov     esi, ecx
0x180004ffe  test    rax, rax
0x180005001  jnz     short loc_180005017
0x180005003  lea     rcx, ModuleName; "ntdll.dll"
0x18000500a  call    cs:__imp_GetModuleHandleW
0x180005010  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005017  mov     [rsp+48h+Arguments], 0; Arguments
0x180005020  mov     r9d, 400h; dwLanguageId
0x180005026  mov     [rsp+48h+nSize], ebx; nSize
0x18000502a  mov     r8d, esi; dwMessageId
0x18000502d  mov     rdx, rax; lpSource
0x180005030  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180005035  mov     ecx, 1A00h; dwFlags
0x18000503a  call    cs:__imp_FormatMessageW
0x180005040  mov     rbx, [rsp+48h+arg_0]
0x180005045  mov     rsi, [rsp+48h+arg_8]
0x18000504a  add     rsp, 40h
0x18000504e  pop     rdi
0x18000504f  retn
```
