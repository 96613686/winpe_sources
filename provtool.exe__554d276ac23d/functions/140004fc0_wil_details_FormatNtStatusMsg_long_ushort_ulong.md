# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140004fc0`
- end: `0x140005030`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140004fc0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004fea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004fea`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000501a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000501a`

## string_xrefs

- `0x140004fe3`: `ntdll.dll`

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
0x140004fc0  mov     [rsp+arg_0], rbx
0x140004fc5  mov     [rsp+arg_8], rsi
0x140004fca  push    rdi
0x140004fcb  sub     rsp, 40h
0x140004fcf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004fd6  mov     ebx, r8d
0x140004fd9  mov     rdi, rdx
0x140004fdc  mov     esi, ecx
0x140004fde  test    rax, rax
0x140004fe1  jnz     short loc_140004FF7
0x140004fe3  lea     rcx, ModuleName; "ntdll.dll"
0x140004fea  call    cs:__imp_GetModuleHandleW
0x140004ff0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004ff7  mov     [rsp+48h+Arguments], 0; Arguments
0x140005000  mov     r9d, 400h; dwLanguageId
0x140005006  mov     [rsp+48h+nSize], ebx; nSize
0x14000500a  mov     r8d, esi; dwMessageId
0x14000500d  mov     rdx, rax; lpSource
0x140005010  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x140005015  mov     ecx, 1A00h; dwFlags
0x14000501a  call    cs:__imp_FormatMessageW
0x140005020  mov     rbx, [rsp+48h+arg_0]
0x140005025  mov     rsi, [rsp+48h+arg_8]
0x14000502a  add     rsp, 40h
0x14000502e  pop     rdi
0x14000502f  retn
```
