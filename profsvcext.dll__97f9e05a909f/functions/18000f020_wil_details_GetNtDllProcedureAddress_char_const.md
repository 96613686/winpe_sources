# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000f020`
- end: `0x18000f040`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000e2f0`
- `0x18000e330`
- `0x180011570`
- `0x1800176e4`
- `0x180017810`
- `0x180017c8c`
- `0x180017d04`
- `0x180017ee0`

## callees

- `0x18000eff0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f039`

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
0x18000f020  push    rbx
0x18000f022  sub     rsp, 20h
0x18000f026  mov     rbx, rcx
0x18000f029  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000f02e  mov     rcx, rax
0x18000f031  mov     rdx, rbx
0x18000f034  add     rsp, 20h
0x18000f038  pop     rbx
0x18000f039  jmp     cs:__imp_GetProcAddress
```
