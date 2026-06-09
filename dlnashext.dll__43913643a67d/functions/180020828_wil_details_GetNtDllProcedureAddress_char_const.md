# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180020828`
- end: `0x180020863`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `59`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001fa90`

## callees

- `0x180020828`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002085c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020844`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020844`

## string_xrefs

- `0x18002083d`: `ntdll.dll`

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
0x180020828  push    rbx
0x18002082a  sub     rsp, 20h
0x18002082e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180020835  mov     rbx, rcx
0x180020838  test    rax, rax
0x18002083b  jnz     short loc_180020851
0x18002083d  lea     rcx, aNtdllDll; "ntdll.dll"
0x180020844  call    cs:__imp_GetModuleHandleW
0x18002084a  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180020851  mov     rdx, rbx
0x180020854  mov     rcx, rax
0x180020857  add     rsp, 20h
0x18002085b  pop     rbx
0x18002085c  jmp     cs:__imp_GetProcAddress
```
