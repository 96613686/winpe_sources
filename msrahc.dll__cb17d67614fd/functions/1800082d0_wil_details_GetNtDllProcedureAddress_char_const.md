# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1800082d0`
- end: `0x1800082f0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800034e0`
- `0x180006380`
- `0x1800063c0`
- `0x1800084d4`
- `0x180008534`
- `0x1800085ac`
- `0x180008638`

## callees

- `0x1800082a0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800082e9`

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
0x1800082d0  push    rbx
0x1800082d2  sub     rsp, 20h
0x1800082d6  mov     rbx, rcx
0x1800082d9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1800082de  mov     rcx, rax
0x1800082e1  mov     rdx, rbx
0x1800082e4  add     rsp, 20h
0x1800082e8  pop     rbx
0x1800082e9  jmp     cs:__imp_GetProcAddress
```
