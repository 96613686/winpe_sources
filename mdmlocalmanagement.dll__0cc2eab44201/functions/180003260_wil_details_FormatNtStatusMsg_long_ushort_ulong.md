# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180003260`
- end: `0x1800032dd`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `125`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003260`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000328a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000328a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800032c0`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800032c0`

## string_xrefs

- `0x180003283`: `ntdll.dll`

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
0x180003260  mov     [rsp+arg_0], rbx
0x180003265  mov     [rsp+arg_8], rsi
0x18000326a  push    rdi
0x18000326b  sub     rsp, 40h
0x18000326f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003276  mov     ebx, r8d
0x180003279  mov     rdi, rdx
0x18000327c  mov     esi, ecx
0x18000327e  test    rax, rax
0x180003281  jnz     short loc_18000329D
0x180003283  lea     rcx, ModuleName; "ntdll.dll"
0x18000328a  call    cs:__imp_GetModuleHandleW
0x180003291  nop     dword ptr [rax+rax+00h]
0x180003296  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000329d  mov     [rsp+48h+Arguments], 0; Arguments
0x1800032a6  mov     r9d, 400h; dwLanguageId
0x1800032ac  mov     [rsp+48h+nSize], ebx; nSize
0x1800032b0  mov     r8d, esi; dwMessageId
0x1800032b3  mov     rdx, rax; lpSource
0x1800032b6  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1800032bb  mov     ecx, 1A00h; dwFlags
0x1800032c0  call    cs:__imp_FormatMessageW
0x1800032c7  nop     dword ptr [rax+rax+00h]
0x1800032cc  mov     rbx, [rsp+48h+arg_0]
0x1800032d1  mov     rsi, [rsp+48h+arg_8]
0x1800032d6  add     rsp, 40h
0x1800032da  pop     rdi
0x1800032db  retn
```
