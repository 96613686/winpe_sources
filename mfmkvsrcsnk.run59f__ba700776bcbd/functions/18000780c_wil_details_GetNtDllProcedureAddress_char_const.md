# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000780c`
- end: `0x180007852`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `70`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006860`

## callees

- `0x18000780c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007846`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007828`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007828`

## string_xrefs

- `0x180007821`: `ntdll.dll`

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
0x18000780c  push    rbx
0x18000780e  sub     rsp, 20h
0x180007812  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007819  mov     rbx, rcx
0x18000781c  test    rax, rax
0x18000781f  jnz     short loc_18000783B
0x180007821  lea     rcx, ModuleName; "ntdll.dll"
0x180007828  call    cs:__imp_GetModuleHandleW
0x18000782f  nop     dword ptr [rax+rax+00h]
0x180007834  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000783b  mov     rdx, rbx
0x18000783e  mov     rcx, rax
0x180007841  add     rsp, 20h
0x180007845  pop     rbx
0x180007846  jmp     cs:__imp_GetProcAddress
```
