# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180027240`
- end: `0x180027260`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001eaa0`
- `0x1800264d0`
- `0x180026510`
- `0x18002a6c4`
- `0x18002b814`
- `0x18002b940`
- `0x18002bd24`
- `0x18002bd9c`

## callees

- `0x180027210`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027259`

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
0x180027240  push    rbx
0x180027242  sub     rsp, 20h
0x180027246  mov     rbx, rcx
0x180027249  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18002724e  mov     rcx, rax
0x180027251  mov     rdx, rbx
0x180027254  add     rsp, 20h
0x180027258  pop     rbx
0x180027259  jmp     cs:__imp_GetProcAddress
```
