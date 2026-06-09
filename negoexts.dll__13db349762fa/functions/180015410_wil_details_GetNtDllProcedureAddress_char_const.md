# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180015410`
- end: `0x180015430`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000e0d0`
- `0x180013cd0`
- `0x180013d10`
- `0x1800146a8`
- `0x1800160bc`
- `0x1800161e8`
- `0x1800165d4`
- `0x18001664c`

## callees

- `0x1800153e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015429`

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
0x180015410  push    rbx
0x180015412  sub     rsp, 20h
0x180015416  mov     rbx, rcx
0x180015419  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18001541e  mov     rcx, rax
0x180015421  mov     rdx, rbx
0x180015424  add     rsp, 20h
0x180015428  pop     rbx
0x180015429  jmp     cs:__imp_GetProcAddress
```
