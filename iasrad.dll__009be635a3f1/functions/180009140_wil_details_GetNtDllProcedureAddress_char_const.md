# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180009140`
- end: `0x180009160`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003394`
- `0x180006fe0`
- `0x180007020`
- `0x1800079b4`
- `0x1800096d0`
- `0x1800097fc`
- `0x1800098bc`
- `0x180009934`

## callees

- `0x180009110`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180009159`

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
0x180009140  push    rbx
0x180009142  sub     rsp, 20h
0x180009146  mov     rbx, rcx
0x180009149  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000914e  mov     rcx, rax
0x180009151  mov     rdx, rbx
0x180009154  add     rsp, 20h
0x180009158  pop     rbx
0x180009159  jmp     cs:__imp_GetProcAddress
```
