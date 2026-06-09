# wil_details_GetNtDllProcedureAddress

- ea: `0x180010268`
- end: `0x1800102a3`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000f9b0`
- `0x18000fadc`

## callees

- `0x180010268`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001029c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010284`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010284`

## string_xrefs

- `0x18001027d`: `ntdll.dll`

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
0x180010268  push    rbx
0x18001026a  sub     rsp, 20h
0x18001026e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180010275  mov     rbx, rcx
0x180010278  test    rax, rax
0x18001027b  jnz     short loc_180010291
0x18001027d  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180010284  call    cs:__imp_GetModuleHandleW
0x18001028a  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180010291  mov     rdx, rbx
0x180010294  mov     rcx, rax
0x180010297  add     rsp, 20h
0x18001029b  pop     rbx
0x18001029c  jmp     cs:__imp_GetProcAddress
```
