# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x14000d810`
- end: `0x14000d830`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140009690`
- `0x1400096d0`
- `0x14000ae40`
- `0x14000e6a0`
- `0x14000e7cc`
- `0x14000e88c`
- `0x14000e904`
- `0x14000eae0`
- `0x14000eb4c`

## callees

- `0x14000d7e0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000d829`

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
0x14000d810  push    rbx
0x14000d812  sub     rsp, 20h
0x14000d816  mov     rbx, rcx
0x14000d819  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x14000d81e  mov     rcx, rax
0x14000d821  mov     rdx, rbx
0x14000d824  add     rsp, 20h
0x14000d828  pop     rbx
0x14000d829  jmp     cs:__imp_GetProcAddress
```
