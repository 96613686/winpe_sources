# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180012410`
- end: `0x180012430`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000b580`
- `0x180010aa0`
- `0x180010af0`
- `0x180012828`
- `0x180012954`
- `0x180012a3c`
- `0x180012ab4`
- `0x180012c98`

## callees

- `0x1800123e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012429`

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
0x180012410  push    rbx
0x180012412  sub     rsp, 20h
0x180012416  mov     rbx, rcx
0x180012419  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18001241e  mov     rcx, rax
0x180012421  mov     rdx, rbx
0x180012424  add     rsp, 20h
0x180012428  pop     rbx
0x180012429  jmp     cs:__imp_GetProcAddress
```
