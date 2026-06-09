# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000a118`
- end: `0x18000a138`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800084c0`
- `0x180008500`
- `0x180009840`
- `0x18000a424`
- `0x18000a550`
- `0x18000a9ec`
- `0x18000aa64`
- `0x18000ac3c`
- `0x18000aca8`

## callees

- `0x18000a0e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a131`

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
0x18000a118  push    rbx
0x18000a11a  sub     rsp, 20h
0x18000a11e  mov     rbx, rcx
0x18000a121  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000a126  mov     rcx, rax
0x18000a129  mov     rdx, rbx
0x18000a12c  add     rsp, 20h
0x18000a130  pop     rbx
0x18000a131  jmp     cs:__imp_GetProcAddress
```
