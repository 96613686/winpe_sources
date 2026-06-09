# wil_details_GetNtDllProcedureAddress

- ea: `0x1800236b4`
- end: `0x1800236ef`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180022d18`
- `0x180022e44`

## callees

- `0x1800236b4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800236e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800236d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800236d0`

## string_xrefs

- `0x1800236c9`: `ntdll.dll`

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
0x1800236b4  push    rbx
0x1800236b6  sub     rsp, 20h
0x1800236ba  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x1800236c1  mov     rbx, rcx
0x1800236c4  test    rax, rax
0x1800236c7  jnz     short loc_1800236DD
0x1800236c9  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1800236d0  call    cs:__imp_GetModuleHandleW
0x1800236d6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x1800236dd  mov     rdx, rbx
0x1800236e0  mov     rcx, rax
0x1800236e3  add     rsp, 20h
0x1800236e7  pop     rbx
0x1800236e8  jmp     cs:__imp_GetProcAddress
```
