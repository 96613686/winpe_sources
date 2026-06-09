# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180003840`
- end: `0x1800038b0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003840`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000386a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000386a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000389a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000389a`

## string_xrefs

- `0x180003863`: `ntdll.dll`

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
0x180003840  mov     [rsp+arg_0], rbx
0x180003845  mov     [rsp+arg_8], rsi
0x18000384a  push    rdi
0x18000384b  sub     rsp, 40h
0x18000384f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003856  mov     ebx, r8d
0x180003859  mov     rdi, rdx
0x18000385c  mov     esi, ecx
0x18000385e  test    rax, rax
0x180003861  jnz     short loc_180003877
0x180003863  lea     rcx, ModuleName; "ntdll.dll"
0x18000386a  call    cs:__imp_GetModuleHandleW
0x180003870  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003877  mov     [rsp+48h+Arguments], 0; Arguments
0x180003880  mov     r9d, 400h; dwLanguageId
0x180003886  mov     [rsp+48h+nSize], ebx; nSize
0x18000388a  mov     r8d, esi; dwMessageId
0x18000388d  mov     rdx, rax; lpSource
0x180003890  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180003895  mov     ecx, 1A00h; dwFlags
0x18000389a  call    cs:__imp_FormatMessageW
0x1800038a0  mov     rbx, [rsp+48h+arg_0]
0x1800038a5  mov     rsi, [rsp+48h+arg_8]
0x1800038aa  add     rsp, 40h
0x1800038ae  pop     rdi
0x1800038af  retn
```
