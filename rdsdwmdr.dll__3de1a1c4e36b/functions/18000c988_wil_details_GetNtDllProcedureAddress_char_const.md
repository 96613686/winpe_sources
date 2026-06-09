# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000c988`
- end: `0x18000c9c3`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `59`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000bd80`

## callees

- `0x18000c988`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c9bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c9a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c9a4`

## string_xrefs

- `0x18000c99d`: `ntdll.dll`

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
0x18000c988  push    rbx
0x18000c98a  sub     rsp, 20h
0x18000c98e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c995  mov     rbx, rcx
0x18000c998  test    rax, rax
0x18000c99b  jnz     short loc_18000C9B1
0x18000c99d  lea     rcx, ModuleName; "ntdll.dll"
0x18000c9a4  call    cs:__imp_GetModuleHandleW
0x18000c9aa  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c9b1  mov     rdx, rbx
0x18000c9b4  mov     rcx, rax
0x18000c9b7  add     rsp, 20h
0x18000c9bb  pop     rbx
0x18000c9bc  jmp     cs:__imp_GetProcAddress
```
