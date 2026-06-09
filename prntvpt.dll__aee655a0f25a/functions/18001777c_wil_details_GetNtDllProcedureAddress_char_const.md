# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18001777c`
- end: `0x18001779c`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d82c`
- `0x180016000`
- `0x180016040`
- `0x180016714`
- `0x180017974`
- `0x180017aa0`
- `0x180017d08`
- `0x180017d80`

## callees

- `0x18001774c`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180017795`

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
0x18001777c  push    rbx
0x18001777e  sub     rsp, 20h
0x180017782  mov     rbx, rcx
0x180017785  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18001778a  mov     rcx, rax
0x18001778d  mov     rdx, rbx
0x180017790  add     rsp, 20h
0x180017794  pop     rbx
0x180017795  jmp     cs:__imp_GetProcAddress
```
