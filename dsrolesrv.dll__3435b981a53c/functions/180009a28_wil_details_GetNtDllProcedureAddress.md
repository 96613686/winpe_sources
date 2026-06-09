# wil_details_GetNtDllProcedureAddress

- ea: `0x180009a28`
- end: `0x180009a63`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800090cc`
- `0x1800091f8`

## callees

- `0x180009a28`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009a5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009a44`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009a44`

## string_xrefs

- `0x180009a3d`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil_details_GetNtDllProcedureAddress(const CHAR *a1)
{
  HMODULE ModuleHandleW; // rax

  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = (__int64)ModuleHandleW;
  }
  return GetProcAddress(ModuleHandleW, a1);
}

```

## disassembly

```asm
0x180009a28  push    rbx
0x180009a2a  sub     rsp, 20h
0x180009a2e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180009a35  mov     rbx, rcx
0x180009a38  test    rax, rax
0x180009a3b  jnz     short loc_180009A51
0x180009a3d  lea     rcx, ModuleName; "ntdll.dll"
0x180009a44  call    cs:__imp_GetModuleHandleW
0x180009a4a  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180009a51  mov     rdx, rbx
0x180009a54  mov     rcx, rax
0x180009a57  add     rsp, 20h
0x180009a5b  pop     rbx
0x180009a5c  jmp     cs:__imp_GetProcAddress
```
