# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180009558`
- end: `0x180009578`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800087c0`

## callees

- `0x180009528`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009571`

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
0x180009558  push    rbx
0x18000955a  sub     rsp, 20h
0x18000955e  mov     rbx, rcx
0x180009561  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180009566  mov     rcx, rax
0x180009569  mov     rdx, rbx
0x18000956c  add     rsp, 20h
0x180009570  pop     rbx
0x180009571  jmp     cs:__imp_GetProcAddress
```
