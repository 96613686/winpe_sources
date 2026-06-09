# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000dd70`
- end: `0x18000dd90`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800047a8`
- `0x18000b280`
- `0x18000b2c0`
- `0x18000bc2c`
- `0x18000e778`
- `0x18000e8a4`
- `0x18000e96c`
- `0x18000e9e4`

## callees

- `0x18000dd40`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000dd89`

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
0x18000dd70  push    rbx
0x18000dd72  sub     rsp, 20h
0x18000dd76  mov     rbx, rcx
0x18000dd79  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000dd7e  mov     rcx, rax
0x18000dd81  mov     rdx, rbx
0x18000dd84  add     rsp, 20h
0x18000dd88  pop     rbx
0x18000dd89  jmp     cs:__imp_GetProcAddress
```
