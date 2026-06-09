# wil_details_GetNtDllProcedureAddress

- ea: `0x18003689c`
- end: `0x1800368d7`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18003614c`
- `0x180036278`

## callees

- `0x18003689c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800368b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800368b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800368d0`

## string_xrefs

- `0x1800368b1`: `ntdll.dll`

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
0x18003689c  push    rbx
0x18003689e  sub     rsp, 20h
0x1800368a2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x1800368a9  mov     rbx, rcx
0x1800368ac  test    rax, rax
0x1800368af  jnz     short loc_1800368C5
0x1800368b1  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1800368b8  call    cs:__imp_GetModuleHandleW
0x1800368be  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x1800368c5  mov     rdx, rbx
0x1800368c8  mov     rcx, rax
0x1800368cb  add     rsp, 20h
0x1800368cf  pop     rbx
0x1800368d0  jmp     cs:__imp_GetProcAddress
```
