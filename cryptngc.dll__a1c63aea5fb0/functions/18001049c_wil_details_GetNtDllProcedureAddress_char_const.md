# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18001049c`
- end: `0x1800104d7`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `59`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `10`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000fcc0`
- `0x18000fdec`
- `0x180010190`
- `0x180010460`
- `0x180027edc`
- `0x180028584`
- `0x18002b114`
- `0x18002ce68`
- `0x180030d90`
- `0x180031d58`

## callees

- `0x18001049c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800104d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800104b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800104b8`

## string_xrefs

- `0x1800104b1`: `ntdll.dll`

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
0x18001049c  push    rbx
0x18001049e  sub     rsp, 20h
0x1800104a2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800104a9  mov     rbx, rcx
0x1800104ac  test    rax, rax
0x1800104af  jnz     short loc_1800104C5
0x1800104b1  lea     rcx, ModuleName; "ntdll.dll"
0x1800104b8  call    cs:__imp_GetModuleHandleW
0x1800104be  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800104c5  mov     rdx, rbx
0x1800104c8  mov     rcx, rax
0x1800104cb  add     rsp, 20h
0x1800104cf  pop     rbx
0x1800104d0  jmp     cs:__imp_GetProcAddress
```
