# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x140005464`
- end: `0x140005484`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140004a00`

## callees

- `0x140005434`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000547d`

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
0x140005464  push    rbx
0x140005466  sub     rsp, 20h
0x14000546a  mov     rbx, rcx
0x14000546d  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x140005472  mov     rcx, rax
0x140005475  mov     rdx, rbx
0x140005478  add     rsp, 20h
0x14000547c  pop     rbx
0x14000547d  jmp     cs:__imp_GetProcAddress
```
