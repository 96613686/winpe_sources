# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180004620`
- end: `0x18000469d`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `125`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004620`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000464a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000464a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004680`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004680`

## string_xrefs

- `0x180004643`: `ntdll.dll`

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
0x180004620  mov     [rsp+arg_0], rbx
0x180004625  mov     [rsp+arg_8], rsi
0x18000462a  push    rdi
0x18000462b  sub     rsp, 40h
0x18000462f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004636  mov     ebx, r8d
0x180004639  mov     rdi, rdx
0x18000463c  mov     esi, ecx
0x18000463e  test    rax, rax
0x180004641  jnz     short loc_18000465D
0x180004643  lea     rcx, ModuleName; "ntdll.dll"
0x18000464a  call    cs:__imp_GetModuleHandleW
0x180004651  nop     dword ptr [rax+rax+00h]
0x180004656  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000465d  mov     [rsp+48h+Arguments], 0; Arguments
0x180004666  mov     r9d, 400h; dwLanguageId
0x18000466c  mov     [rsp+48h+nSize], ebx; nSize
0x180004670  mov     r8d, esi; dwMessageId
0x180004673  mov     rdx, rax; lpSource
0x180004676  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18000467b  mov     ecx, 1A00h; dwFlags
0x180004680  call    cs:__imp_FormatMessageW
0x180004687  nop     dword ptr [rax+rax+00h]
0x18000468c  mov     rbx, [rsp+48h+arg_0]
0x180004691  mov     rsi, [rsp+48h+arg_8]
0x180004696  add     rsp, 40h
0x18000469a  pop     rdi
0x18000469b  retn
```
