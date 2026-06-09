# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180005be0`
- end: `0x180005c50`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005be0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005c0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005c0a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005c3a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005c3a`

## string_xrefs

- `0x180005c03`: `ntdll.dll`

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
0x180005be0  mov     [rsp+arg_0], rbx
0x180005be5  mov     [rsp+arg_8], rsi
0x180005bea  push    rdi
0x180005beb  sub     rsp, 40h
0x180005bef  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005bf6  mov     ebx, r8d
0x180005bf9  mov     rdi, rdx
0x180005bfc  mov     esi, ecx
0x180005bfe  test    rax, rax
0x180005c01  jnz     short loc_180005C17
0x180005c03  lea     rcx, ModuleName; "ntdll.dll"
0x180005c0a  call    cs:__imp_GetModuleHandleW
0x180005c10  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005c17  mov     [rsp+48h+Arguments], 0; Arguments
0x180005c20  mov     r9d, 400h; dwLanguageId
0x180005c26  mov     [rsp+48h+nSize], ebx; nSize
0x180005c2a  mov     r8d, esi; dwMessageId
0x180005c2d  mov     rdx, rax; lpSource
0x180005c30  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180005c35  mov     ecx, 1A00h; dwFlags
0x180005c3a  call    cs:__imp_FormatMessageW
0x180005c40  mov     rbx, [rsp+48h+arg_0]
0x180005c45  mov     rsi, [rsp+48h+arg_8]
0x180005c4a  add     rsp, 40h
0x180005c4e  pop     rdi
0x180005c4f  retn
```
