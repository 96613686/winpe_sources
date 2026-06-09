# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x18000c2e0`
- end: `0x18000c350`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c2e0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000c30a`
- `KERNEL32!GetModuleHandleW` at `0x18000c30a`
- `KERNEL32!FormatMessageW` at `0x18000c33a`
- `KERNEL32!FormatMessageW` at `0x18000c33a`

## string_xrefs

- `0x18000c303`: `ntdll.dll`

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
0x18000c2e0  mov     [rsp+arg_0], rbx
0x18000c2e5  mov     [rsp+arg_8], rsi
0x18000c2ea  push    rdi
0x18000c2eb  sub     rsp, 40h
0x18000c2ef  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c2f6  mov     ebx, r8d
0x18000c2f9  mov     rdi, rdx
0x18000c2fc  mov     esi, ecx
0x18000c2fe  test    rax, rax
0x18000c301  jnz     short loc_18000C317
0x18000c303  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000c30a  call    cs:__imp_GetModuleHandleW
0x18000c310  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c317  mov     [rsp+48h+Arguments], 0; Arguments
0x18000c320  mov     r9d, 400h; dwLanguageId
0x18000c326  mov     [rsp+48h+nSize], ebx; nSize
0x18000c32a  mov     r8d, esi; dwMessageId
0x18000c32d  mov     rdx, rax; lpSource
0x18000c330  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18000c335  mov     ecx, 1A00h; dwFlags
0x18000c33a  call    cs:__imp_FormatMessageW
0x18000c340  mov     rbx, [rsp+48h+arg_0]
0x18000c345  mov     rsi, [rsp+48h+arg_8]
0x18000c34a  add     rsp, 40h
0x18000c34e  pop     rdi
0x18000c34f  retn
```
