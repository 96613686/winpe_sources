# wil_details_GetNtDllProcedureAddress

- ea: `0x180008d34`
- end: `0x180008d6f`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800083f4`
- `0x1800084ec`

## callees

- `0x180008d34`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008d50`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008d50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008d68`

## string_xrefs

- `0x180008d49`: `ntdll.dll`

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
0x180008d34  push    rbx
0x180008d36  sub     rsp, 20h
0x180008d3a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180008d41  mov     rbx, rcx
0x180008d44  test    rax, rax
0x180008d47  jnz     short loc_180008D5D
0x180008d49  lea     rcx, ModuleName; "ntdll.dll"
0x180008d50  call    cs:__imp_GetModuleHandleW
0x180008d56  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180008d5d  mov     rdx, rbx
0x180008d60  mov     rcx, rax
0x180008d63  add     rsp, 20h
0x180008d67  pop     rbx
0x180008d68  jmp     cs:__imp_GetProcAddress
```
