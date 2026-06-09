# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x1800097a0`
- end: `0x180009810`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800097a0`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1800097fa`
- `KERNEL32!FormatMessageW` at `0x1800097fa`
- `KERNEL32!GetModuleHandleW` at `0x1800097ca`
- `KERNEL32!GetModuleHandleW` at `0x1800097ca`

## string_xrefs

- `0x1800097c3`: `ntdll.dll`

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
0x1800097a0  mov     [rsp+arg_0], rbx
0x1800097a5  mov     [rsp+arg_8], rsi
0x1800097aa  push    rdi
0x1800097ab  sub     rsp, 40h
0x1800097af  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800097b6  mov     ebx, r8d
0x1800097b9  mov     rdi, rdx
0x1800097bc  mov     esi, ecx
0x1800097be  test    rax, rax
0x1800097c1  jnz     short loc_1800097D7
0x1800097c3  lea     rcx, aNtdllDll; "ntdll.dll"
0x1800097ca  call    cs:__imp_GetModuleHandleW
0x1800097d0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800097d7  mov     [rsp+48h+Arguments], 0; Arguments
0x1800097e0  mov     r9d, 400h; dwLanguageId
0x1800097e6  mov     [rsp+48h+nSize], ebx; nSize
0x1800097ea  mov     r8d, esi; dwMessageId
0x1800097ed  mov     rdx, rax; lpSource
0x1800097f0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1800097f5  mov     ecx, 1A00h; dwFlags
0x1800097fa  call    cs:__imp_FormatMessageW
0x180009800  mov     rbx, [rsp+48h+arg_0]
0x180009805  mov     rsi, [rsp+48h+arg_8]
0x18000980a  add     rsp, 40h
0x18000980e  pop     rdi
0x18000980f  retn
```
