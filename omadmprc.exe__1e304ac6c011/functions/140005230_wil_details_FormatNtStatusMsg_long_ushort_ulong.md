# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140005230`
- end: `0x1400052ad`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `125`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140005230`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140005290`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140005290`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000525a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000525a`

## string_xrefs

- `0x140005253`: `ntdll.dll`

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
0x140005230  mov     [rsp+arg_0], rbx
0x140005235  mov     [rsp+arg_8], rsi
0x14000523a  push    rdi
0x14000523b  sub     rsp, 40h
0x14000523f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140005246  mov     ebx, r8d
0x140005249  mov     rdi, rdx
0x14000524c  mov     esi, ecx
0x14000524e  test    rax, rax
0x140005251  jnz     short loc_14000526D
0x140005253  lea     rcx, ModuleName; "ntdll.dll"
0x14000525a  call    cs:__imp_GetModuleHandleW
0x140005261  nop     dword ptr [rax+rax+00h]
0x140005266  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000526d  mov     [rsp+48h+Arguments], 0; Arguments
0x140005276  mov     r9d, 400h; dwLanguageId
0x14000527c  mov     [rsp+48h+nSize], ebx; nSize
0x140005280  mov     r8d, esi; dwMessageId
0x140005283  mov     rdx, rax; lpSource
0x140005286  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x14000528b  mov     ecx, 1A00h; dwFlags
0x140005290  call    cs:__imp_FormatMessageW
0x140005297  nop     dword ptr [rax+rax+00h]
0x14000529c  mov     rbx, [rsp+48h+arg_0]
0x1400052a1  mov     rsi, [rsp+48h+arg_8]
0x1400052a6  add     rsp, 40h
0x1400052aa  pop     rdi
0x1400052ab  retn
```
