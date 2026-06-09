# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180004670`
- end: `0x1800046e0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004670`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000469a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000469a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800046ca`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800046ca`

## string_xrefs

- `0x180004693`: `ntdll.dll`

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
0x180004670  mov     [rsp+arg_0], rbx
0x180004675  mov     [rsp+arg_8], rsi
0x18000467a  push    rdi
0x18000467b  sub     rsp, 40h
0x18000467f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004686  mov     ebx, r8d
0x180004689  mov     rdi, rdx
0x18000468c  mov     esi, ecx
0x18000468e  test    rax, rax
0x180004691  jnz     short loc_1800046A7
0x180004693  lea     rcx, ModuleName; "ntdll.dll"
0x18000469a  call    cs:__imp_GetModuleHandleW
0x1800046a0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800046a7  mov     [rsp+48h+Arguments], 0; Arguments
0x1800046b0  mov     r9d, 400h; dwLanguageId
0x1800046b6  mov     [rsp+48h+nSize], ebx; nSize
0x1800046ba  mov     r8d, esi; dwMessageId
0x1800046bd  mov     rdx, rax; lpSource
0x1800046c0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1800046c5  mov     ecx, 1A00h; dwFlags
0x1800046ca  call    cs:__imp_FormatMessageW
0x1800046d0  mov     rbx, [rsp+48h+arg_0]
0x1800046d5  mov     rsi, [rsp+48h+arg_8]
0x1800046da  add     rsp, 40h
0x1800046de  pop     rdi
0x1800046df  retn
```
