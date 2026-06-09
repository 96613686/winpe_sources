# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180014cb0`
- end: `0x180014ceb`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `59`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180013130`

## callees

- `0x180014cb0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014ccc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014ccc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014ce4`

## string_xrefs

- `0x180014cc5`: `ntdll.dll`

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
0x180014cb0  push    rbx
0x180014cb2  sub     rsp, 20h
0x180014cb6  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014cbd  mov     rbx, rcx
0x180014cc0  test    rax, rax
0x180014cc3  jnz     short loc_180014CD9
0x180014cc5  lea     rcx, ModuleName; "ntdll.dll"
0x180014ccc  call    cs:__imp_GetModuleHandleW
0x180014cd2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014cd9  mov     rdx, rbx
0x180014cdc  mov     rcx, rax
0x180014cdf  add     rsp, 20h
0x180014ce3  pop     rbx
0x180014ce4  jmp     cs:__imp_GetProcAddress
```
