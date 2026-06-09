# wil_details_GetNtDllProcedureAddress

- ea: `0x180023154`
- end: `0x18002319a`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `70`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002293c`
- `0x180022df0`

## callees

- `0x180023154`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002318e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180023170`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180023170`

## string_xrefs

- `0x180023169`: `ntdll.dll`

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
0x180023154  push    rbx
0x180023156  sub     rsp, 20h
0x18002315a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180023161  mov     rbx, rcx
0x180023164  test    rax, rax
0x180023167  jnz     short loc_180023183
0x180023169  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180023170  call    cs:__imp_GetModuleHandleW
0x180023177  nop     dword ptr [rax+rax+00h]
0x18002317c  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180023183  mov     rdx, rbx
0x180023186  mov     rcx, rax
0x180023189  add     rsp, 20h
0x18002318d  pop     rbx
0x18002318e  jmp     cs:__imp_GetProcAddress
```
