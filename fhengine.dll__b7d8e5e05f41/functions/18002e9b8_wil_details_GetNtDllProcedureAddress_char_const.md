# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18002e9b8`
- end: `0x18002e9d8`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180027ac8`
- `0x18002cf20`
- `0x18002cf60`
- `0x18002ebbc`
- `0x18002ece8`
- `0x18002f16c`
- `0x18002f1e4`
- `0x18002f3c0`

## callees

- `0x18002e988`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002e9d1`

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
0x18002e9b8  push    rbx
0x18002e9ba  sub     rsp, 20h
0x18002e9be  mov     rbx, rcx
0x18002e9c1  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18002e9c6  mov     rcx, rax
0x18002e9c9  mov     rdx, rbx
0x18002e9cc  add     rsp, 20h
0x18002e9d0  pop     rbx
0x18002e9d1  jmp     cs:__imp_GetProcAddress
```
