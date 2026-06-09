# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x1400030a0`
- end: `0x140003110`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1400030a0`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1400030fa`
- `KERNEL32!FormatMessageW` at `0x1400030fa`
- `KERNEL32!GetModuleHandleW` at `0x1400030ca`
- `KERNEL32!GetModuleHandleW` at `0x1400030ca`

## string_xrefs

- `0x1400030c3`: `ntdll.dll`

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
0x1400030a0  mov     [rsp+arg_0], rbx
0x1400030a5  mov     [rsp+arg_8], rsi
0x1400030aa  push    rdi
0x1400030ab  sub     rsp, 40h
0x1400030af  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400030b6  mov     ebx, r8d
0x1400030b9  mov     rdi, rdx
0x1400030bc  mov     esi, ecx
0x1400030be  test    rax, rax
0x1400030c1  jnz     short loc_1400030D7
0x1400030c3  lea     rcx, ModuleName; "ntdll.dll"
0x1400030ca  call    cs:__imp_GetModuleHandleW
0x1400030d0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400030d7  mov     [rsp+48h+Arguments], 0; Arguments
0x1400030e0  mov     r9d, 400h; dwLanguageId
0x1400030e6  mov     [rsp+48h+nSize], ebx; nSize
0x1400030ea  mov     r8d, esi; dwMessageId
0x1400030ed  mov     rdx, rax; lpSource
0x1400030f0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1400030f5  mov     ecx, 1A00h; dwFlags
0x1400030fa  call    cs:__imp_FormatMessageW
0x140003100  mov     rbx, [rsp+48h+arg_0]
0x140003105  mov     rsi, [rsp+48h+arg_8]
0x14000310a  add     rsp, 40h
0x14000310e  pop     rdi
0x14000310f  retn
```
