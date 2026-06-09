# wil_details_GetNtDllProcedureAddress

- ea: `0x180003c34`
- end: `0x180003c6f`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003b3c`
- `0x1800105e0`

## callees

- `0x180003c34`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetModuleHandleW` at `0x180003c50`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetModuleHandleW` at `0x180003c50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003c68`

## string_xrefs

- `0x180003c49`: `ntdll.dll`

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
0x180003c34  push    rbx
0x180003c36  sub     rsp, 20h
0x180003c3a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180003c41  mov     rbx, rcx
0x180003c44  test    rax, rax
0x180003c47  jnz     short loc_180003C5D
0x180003c49  lea     rcx, ModuleName; "ntdll.dll"
0x180003c50  call    cs:__imp_GetModuleHandleW
0x180003c56  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180003c5d  mov     rdx, rbx
0x180003c60  mov     rcx, rax
0x180003c63  add     rsp, 20h
0x180003c67  pop     rbx
0x180003c68  jmp     cs:__imp_GetProcAddress
```
