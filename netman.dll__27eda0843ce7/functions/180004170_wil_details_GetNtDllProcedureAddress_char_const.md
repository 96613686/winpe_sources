# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180004170`
- end: `0x180004190`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003a80`
- `0x180003ac0`
- `0x180008578`
- `0x18001929c`
- `0x1800193c8`
- `0x18001986c`
- `0x1800198e4`
- `0x180019ac0`

## callees

- `0x180004140`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180004189`

## pseudocode

```c
FARPROC __fastcall wil_details_GetNtDllProcedureAddress(const char *a1)
{
  HMODULE NtDllModuleHandle; // rax

  NtDllModuleHandle = wil_details_GetNtDllModuleHandle();
  return GetProcAddress(NtDllModuleHandle, a1);
}

```

## disassembly

```asm
0x180004170  push    rbx
0x180004172  sub     rsp, 20h
0x180004176  mov     rbx, rcx
0x180004179  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000417e  mov     rcx, rax
0x180004181  mov     rdx, rbx
0x180004184  add     rsp, 20h
0x180004188  pop     rbx
0x180004189  jmp     cs:__imp_GetProcAddress
```
