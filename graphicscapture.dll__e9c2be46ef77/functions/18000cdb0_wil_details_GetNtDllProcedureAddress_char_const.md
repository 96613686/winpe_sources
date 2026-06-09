# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000cdb0`
- end: `0x18000cdd0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000b1b0`
- `0x18000b1f0`
- `0x18000d0cc`
- `0x18000d1f8`
- `0x18000d2bc`
- `0x18000d334`
- `0x18000d510`
- `0x18000d57c`

## callees

- `0x18000cd80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cdc9`

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
0x18000cdb0  push    rbx
0x18000cdb2  sub     rsp, 20h
0x18000cdb6  mov     rbx, rcx
0x18000cdb9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000cdbe  mov     rcx, rax
0x18000cdc1  mov     rdx, rbx
0x18000cdc4  add     rsp, 20h
0x18000cdc8  pop     rbx
0x18000cdc9  jmp     cs:__imp_GetProcAddress
```
