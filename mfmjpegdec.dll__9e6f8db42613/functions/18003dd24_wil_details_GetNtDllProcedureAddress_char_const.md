# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18003dd24`
- end: `0x18003dd5f`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `59`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18003d2c0`

## callees

- `0x18003dd24`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003dd58`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003dd40`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003dd40`

## string_xrefs

- `0x18003dd39`: `ntdll.dll`

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
0x18003dd24  push    rbx
0x18003dd26  sub     rsp, 20h
0x18003dd2a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003dd31  mov     rbx, rcx
0x18003dd34  test    rax, rax
0x18003dd37  jnz     short loc_18003DD4D
0x18003dd39  lea     rcx, ModuleName; "ntdll.dll"
0x18003dd40  call    cs:__imp_GetModuleHandleW
0x18003dd46  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003dd4d  mov     rdx, rbx
0x18003dd50  mov     rcx, rax
0x18003dd53  add     rsp, 20h
0x18003dd57  pop     rbx
0x18003dd58  jmp     cs:__imp_GetProcAddress
```
