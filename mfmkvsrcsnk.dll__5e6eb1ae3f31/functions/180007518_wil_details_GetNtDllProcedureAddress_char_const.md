# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180007518`
- end: `0x180007553`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `59`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006640`

## callees

- `0x180007518`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000754c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007534`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007534`

## string_xrefs

- `0x18000752d`: `ntdll.dll`

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
0x180007518  push    rbx
0x18000751a  sub     rsp, 20h
0x18000751e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007525  mov     rbx, rcx
0x180007528  test    rax, rax
0x18000752b  jnz     short loc_180007541
0x18000752d  lea     rcx, ModuleName; "ntdll.dll"
0x180007534  call    cs:__imp_GetModuleHandleW
0x18000753a  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007541  mov     rdx, rbx
0x180007544  mov     rcx, rax
0x180007547  add     rsp, 20h
0x18000754b  pop     rbx
0x18000754c  jmp     cs:__imp_GetProcAddress
```
