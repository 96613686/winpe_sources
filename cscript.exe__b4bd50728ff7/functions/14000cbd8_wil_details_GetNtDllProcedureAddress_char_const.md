# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x14000cbd8`
- end: `0x14000cc13`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `59`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000cc4c`

## callees

- `0x14000cbd8`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000cc0c`
- `KERNEL32!GetModuleHandleW` at `0x14000cbf4`
- `KERNEL32!GetModuleHandleW` at `0x14000cbf4`

## string_xrefs

- `0x14000cbed`: `ntdll.dll`

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
0x14000cbd8  push    rbx
0x14000cbda  sub     rsp, 20h
0x14000cbde  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000cbe5  mov     rbx, rcx
0x14000cbe8  test    rax, rax
0x14000cbeb  jnz     short loc_14000CC01
0x14000cbed  lea     rcx, ModuleName; "ntdll.dll"
0x14000cbf4  call    cs:__imp_GetModuleHandleW
0x14000cbfa  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000cc01  mov     rdx, rbx
0x14000cc04  mov     rcx, rax
0x14000cc07  add     rsp, 20h
0x14000cc0b  pop     rbx
0x14000cc0c  jmp     cs:__imp_GetProcAddress
```
