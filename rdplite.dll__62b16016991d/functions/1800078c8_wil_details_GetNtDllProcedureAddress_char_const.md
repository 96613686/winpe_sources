# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1800078c8`
- end: `0x180007903`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `59`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006aa0`
- `0x180006ae0`

## callees

- `0x1800078c8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800078e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800078e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800078fc`

## string_xrefs

- `0x1800078dd`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil_details_GetNtDllProcedureAddress(const char *a1)
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
0x1800078c8  push    rbx
0x1800078ca  sub     rsp, 20h
0x1800078ce  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800078d5  mov     rbx, rcx
0x1800078d8  test    rax, rax
0x1800078db  jnz     short loc_1800078F1
0x1800078dd  lea     rcx, ModuleName; "ntdll.dll"
0x1800078e4  call    cs:__imp_GetModuleHandleW
0x1800078ea  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800078f1  mov     rdx, rbx
0x1800078f4  mov     rcx, rax
0x1800078f7  add     rsp, 20h
0x1800078fb  pop     rbx
0x1800078fc  jmp     cs:__imp_GetProcAddress
```
