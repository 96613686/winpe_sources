# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x18000bbd0`
- end: `0x18000bc40`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000bbd0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000bbfa`
- `KERNEL32!GetModuleHandleW` at `0x18000bbfa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000bc2a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000bc2a`

## string_xrefs

- `0x18000bbf3`: `ntdll.dll`

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
0x18000bbd0  mov     [rsp+arg_0], rbx
0x18000bbd5  mov     [rsp+arg_8], rsi
0x18000bbda  push    rdi
0x18000bbdb  sub     rsp, 40h
0x18000bbdf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bbe6  mov     ebx, r8d
0x18000bbe9  mov     rdi, rdx
0x18000bbec  mov     esi, ecx
0x18000bbee  test    rax, rax
0x18000bbf1  jnz     short loc_18000BC07
0x18000bbf3  lea     rcx, ModuleName; "ntdll.dll"
0x18000bbfa  call    cs:__imp_GetModuleHandleW
0x18000bc00  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bc07  mov     [rsp+48h+Arguments], 0; Arguments
0x18000bc10  mov     r9d, 400h; dwLanguageId
0x18000bc16  mov     [rsp+48h+nSize], ebx; nSize
0x18000bc1a  mov     r8d, esi; dwMessageId
0x18000bc1d  mov     rdx, rax; lpSource
0x18000bc20  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18000bc25  mov     ecx, 1A00h; dwFlags
0x18000bc2a  call    cs:__imp_FormatMessageW
0x18000bc30  mov     rbx, [rsp+48h+arg_0]
0x18000bc35  mov     rsi, [rsp+48h+arg_8]
0x18000bc3a  add     rsp, 40h
0x18000bc3e  pop     rdi
0x18000bc3f  retn
```
