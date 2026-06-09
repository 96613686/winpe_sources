# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18003667c`
- end: `0x18003669c`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180035020`
- `0x180035060`
- `0x18003696c`
- `0x1800369cc`
- `0x180036a44`
- `0x180036ad0`
- `0x180036b3c`

## callees

- `0x18003664c`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180036695`

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
0x18003667c  push    rbx
0x18003667e  sub     rsp, 20h
0x180036682  mov     rbx, rcx
0x180036685  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18003668a  mov     rcx, rax
0x18003668d  mov     rdx, rbx
0x180036690  add     rsp, 20h
0x180036694  pop     rbx
0x180036695  jmp     cs:__imp_GetProcAddress
```
