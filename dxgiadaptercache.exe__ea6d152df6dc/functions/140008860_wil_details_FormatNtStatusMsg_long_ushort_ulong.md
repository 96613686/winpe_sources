# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140008860`
- end: `0x1400088d0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140008860`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000888a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000888a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400088ba`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400088ba`

## string_xrefs

- `0x140008883`: `ntdll.dll`

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
0x140008860  mov     [rsp+arg_0], rbx
0x140008865  mov     [rsp+arg_8], rsi
0x14000886a  push    rdi
0x14000886b  sub     rsp, 40h
0x14000886f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008876  mov     ebx, r8d
0x140008879  mov     rdi, rdx
0x14000887c  mov     esi, ecx
0x14000887e  test    rax, rax
0x140008881  jnz     short loc_140008897
0x140008883  lea     rcx, ModuleName; "ntdll.dll"
0x14000888a  call    cs:__imp_GetModuleHandleW
0x140008890  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008897  mov     [rsp+48h+Arguments], 0; Arguments
0x1400088a0  mov     r9d, 400h; dwLanguageId
0x1400088a6  mov     [rsp+48h+nSize], ebx; nSize
0x1400088aa  mov     r8d, esi; dwMessageId
0x1400088ad  mov     rdx, rax; lpSource
0x1400088b0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1400088b5  mov     ecx, 1A00h; dwFlags
0x1400088ba  call    cs:__imp_FormatMessageW
0x1400088c0  mov     rbx, [rsp+48h+arg_0]
0x1400088c5  mov     rsi, [rsp+48h+arg_8]
0x1400088ca  add     rsp, 40h
0x1400088ce  pop     rdi
0x1400088cf  retn
```
