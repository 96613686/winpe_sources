# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140006dc0`
- end: `0x140006e30`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140006dc0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006dea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006dea`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140006e1a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140006e1a`

## string_xrefs

- `0x140006de3`: `ntdll.dll`

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
0x140006dc0  mov     [rsp+arg_0], rbx
0x140006dc5  mov     [rsp+arg_8], rsi
0x140006dca  push    rdi
0x140006dcb  sub     rsp, 40h
0x140006dcf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140006dd6  mov     ebx, r8d
0x140006dd9  mov     rdi, rdx
0x140006ddc  mov     esi, ecx
0x140006dde  test    rax, rax
0x140006de1  jnz     short loc_140006DF7
0x140006de3  lea     rcx, ModuleName; "ntdll.dll"
0x140006dea  call    cs:__imp_GetModuleHandleW
0x140006df0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140006df7  mov     [rsp+48h+Arguments], 0; Arguments
0x140006e00  mov     r9d, 400h; dwLanguageId
0x140006e06  mov     [rsp+48h+nSize], ebx; nSize
0x140006e0a  mov     r8d, esi; dwMessageId
0x140006e0d  mov     rdx, rax; lpSource
0x140006e10  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x140006e15  mov     ecx, 1A00h; dwFlags
0x140006e1a  call    cs:__imp_FormatMessageW
0x140006e20  mov     rbx, [rsp+48h+arg_0]
0x140006e25  mov     rsi, [rsp+48h+arg_8]
0x140006e2a  add     rsp, 40h
0x140006e2e  pop     rdi
0x140006e2f  retn
```
