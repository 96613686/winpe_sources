# wil_details_GetNtDllProcedureAddress

- ea: `0x180019a54`
- end: `0x180019a8f`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001620c`
- `0x18001ba18`

## callees

- `0x180019a54`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019a70`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019a70`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019a88`

## string_xrefs

- `0x180019a69`: `ntdll.dll`

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
0x180019a54  push    rbx
0x180019a56  sub     rsp, 20h
0x180019a5a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180019a61  mov     rbx, rcx
0x180019a64  test    rax, rax
0x180019a67  jnz     short loc_180019A7D
0x180019a69  lea     rcx, ModuleName; "ntdll.dll"
0x180019a70  call    cs:__imp_GetModuleHandleW
0x180019a76  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180019a7d  mov     rdx, rbx
0x180019a80  mov     rcx, rax
0x180019a83  add     rsp, 20h
0x180019a87  pop     rbx
0x180019a88  jmp     cs:__imp_GetProcAddress
```
