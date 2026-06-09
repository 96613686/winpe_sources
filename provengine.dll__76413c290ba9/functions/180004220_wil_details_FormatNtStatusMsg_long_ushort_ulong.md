# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180004220`
- end: `0x180004290`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004220`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000424a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000424a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000427a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000427a`

## string_xrefs

- `0x180004243`: `ntdll.dll`

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
0x180004220  mov     [rsp+arg_0], rbx
0x180004225  mov     [rsp+arg_8], rsi
0x18000422a  push    rdi
0x18000422b  sub     rsp, 40h
0x18000422f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004236  mov     ebx, r8d
0x180004239  mov     rdi, rdx
0x18000423c  mov     esi, ecx
0x18000423e  test    rax, rax
0x180004241  jnz     short loc_180004257
0x180004243  lea     rcx, ModuleName; "ntdll.dll"
0x18000424a  call    cs:__imp_GetModuleHandleW
0x180004250  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004257  mov     [rsp+48h+Arguments], 0; Arguments
0x180004260  mov     r9d, 400h; dwLanguageId
0x180004266  mov     [rsp+48h+nSize], ebx; nSize
0x18000426a  mov     r8d, esi; dwMessageId
0x18000426d  mov     rdx, rax; lpSource
0x180004270  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180004275  mov     ecx, 1A00h; dwFlags
0x18000427a  call    cs:__imp_FormatMessageW
0x180004280  mov     rbx, [rsp+48h+arg_0]
0x180004285  mov     rsi, [rsp+48h+arg_8]
0x18000428a  add     rsp, 40h
0x18000428e  pop     rdi
0x18000428f  retn
```
