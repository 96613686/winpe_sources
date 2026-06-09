# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140004910`
- end: `0x140004980`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140004910`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000493a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000493a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000496a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000496a`

## string_xrefs

- `0x140004933`: `ntdll.dll`

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
0x140004910  mov     [rsp+arg_0], rbx
0x140004915  mov     [rsp+arg_8], rsi
0x14000491a  push    rdi
0x14000491b  sub     rsp, 40h
0x14000491f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004926  mov     ebx, r8d
0x140004929  mov     rdi, rdx
0x14000492c  mov     esi, ecx
0x14000492e  test    rax, rax
0x140004931  jnz     short loc_140004947
0x140004933  lea     rcx, ModuleName; "ntdll.dll"
0x14000493a  call    cs:__imp_GetModuleHandleW
0x140004940  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004947  mov     [rsp+48h+Arguments], 0; Arguments
0x140004950  mov     r9d, 400h; dwLanguageId
0x140004956  mov     [rsp+48h+nSize], ebx; nSize
0x14000495a  mov     r8d, esi; dwMessageId
0x14000495d  mov     rdx, rax; lpSource
0x140004960  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x140004965  mov     ecx, 1A00h; dwFlags
0x14000496a  call    cs:__imp_FormatMessageW
0x140004970  mov     rbx, [rsp+48h+arg_0]
0x140004975  mov     rsi, [rsp+48h+arg_8]
0x14000497a  add     rsp, 40h
0x14000497e  pop     rdi
0x14000497f  retn
```
