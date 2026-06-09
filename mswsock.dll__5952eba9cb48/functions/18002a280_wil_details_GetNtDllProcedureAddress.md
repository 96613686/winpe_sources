# wil_details_GetNtDllProcedureAddress

- ea: `0x18002a280`
- end: `0x18002a2c6`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `70`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180029a54`
- `0x180029b50`

## callees

- `0x18002a280`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002a29c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002a29c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a2ba`

## string_xrefs

- `0x18002a295`: `ntdll.dll`

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
0x18002a280  push    rbx
0x18002a282  sub     rsp, 20h
0x18002a286  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18002a28d  mov     rbx, rcx
0x18002a290  test    rax, rax
0x18002a293  jnz     short loc_18002A2AF
0x18002a295  lea     rcx, ModuleName; "ntdll.dll"
0x18002a29c  call    cs:__imp_GetModuleHandleW
0x18002a2a3  nop     dword ptr [rax+rax+00h]
0x18002a2a8  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18002a2af  mov     rdx, rbx
0x18002a2b2  mov     rcx, rax
0x18002a2b5  add     rsp, 20h
0x18002a2b9  pop     rbx
0x18002a2ba  jmp     cs:__imp_GetProcAddress
```
