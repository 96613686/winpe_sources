# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x1400048e0`
- end: `0x14000495d`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `125`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1400048e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000490a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000490a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140004940`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140004940`

## string_xrefs

- `0x140004903`: `ntdll.dll`

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
0x1400048e0  mov     [rsp+arg_0], rbx
0x1400048e5  mov     [rsp+arg_8], rsi
0x1400048ea  push    rdi
0x1400048eb  sub     rsp, 40h
0x1400048ef  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400048f6  mov     ebx, r8d
0x1400048f9  mov     rdi, rdx
0x1400048fc  mov     esi, ecx
0x1400048fe  test    rax, rax
0x140004901  jnz     short loc_14000491D
0x140004903  lea     rcx, ModuleName; "ntdll.dll"
0x14000490a  call    cs:__imp_GetModuleHandleW
0x140004911  nop     dword ptr [rax+rax+00h]
0x140004916  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000491d  mov     [rsp+48h+Arguments], 0; Arguments
0x140004926  mov     r9d, 400h; dwLanguageId
0x14000492c  mov     [rsp+48h+nSize], ebx; nSize
0x140004930  mov     r8d, esi; dwMessageId
0x140004933  mov     rdx, rax; lpSource
0x140004936  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x14000493b  mov     ecx, 1A00h; dwFlags
0x140004940  call    cs:__imp_FormatMessageW
0x140004947  nop     dword ptr [rax+rax+00h]
0x14000494c  mov     rbx, [rsp+48h+arg_0]
0x140004951  mov     rsi, [rsp+48h+arg_8]
0x140004956  add     rsp, 40h
0x14000495a  pop     rdi
0x14000495b  retn
```
