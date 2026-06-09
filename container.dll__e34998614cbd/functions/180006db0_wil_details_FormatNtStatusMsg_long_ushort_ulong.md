# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180006db0`
- end: `0x180006e2d`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `125`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006db0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006dda`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006dda`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006e10`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006e10`

## string_xrefs

- `0x180006dd3`: `ntdll.dll`

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
0x180006db0  mov     [rsp+arg_0], rbx
0x180006db5  mov     [rsp+arg_8], rsi
0x180006dba  push    rdi
0x180006dbb  sub     rsp, 40h
0x180006dbf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006dc6  mov     ebx, r8d
0x180006dc9  mov     rdi, rdx
0x180006dcc  mov     esi, ecx
0x180006dce  test    rax, rax
0x180006dd1  jnz     short loc_180006DED
0x180006dd3  lea     rcx, ModuleName; "ntdll.dll"
0x180006dda  call    cs:__imp_GetModuleHandleW
0x180006de1  nop     dword ptr [rax+rax+00h]
0x180006de6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006ded  mov     [rsp+48h+Arguments], 0; Arguments
0x180006df6  mov     r9d, 400h; dwLanguageId
0x180006dfc  mov     [rsp+48h+nSize], ebx; nSize
0x180006e00  mov     r8d, esi; dwMessageId
0x180006e03  mov     rdx, rax; lpSource
0x180006e06  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180006e0b  mov     ecx, 1A00h; dwFlags
0x180006e10  call    cs:__imp_FormatMessageW
0x180006e17  nop     dword ptr [rax+rax+00h]
0x180006e1c  mov     rbx, [rsp+48h+arg_0]
0x180006e21  mov     rsi, [rsp+48h+arg_8]
0x180006e26  add     rsp, 40h
0x180006e2a  pop     rdi
0x180006e2b  retn
```
