# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180007350`
- end: `0x180007370`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005ac0`
- `0x180006fc0`

## callees

- `0x180007320`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180007369`

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
0x180007350  push    rbx
0x180007352  sub     rsp, 20h
0x180007356  mov     rbx, rcx
0x180007359  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000735e  mov     rcx, rax
0x180007361  mov     rdx, rbx
0x180007364  add     rsp, 20h
0x180007368  pop     rbx
0x180007369  jmp     cs:__imp_GetProcAddress
```
