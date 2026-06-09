# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18001c438`
- end: `0x18001c45d`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `37`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000e610`
- `0x1800137b8`
- `0x18001a8b0`
- `0x18001b5a0`
- `0x18001c640`
- `0x18001c76c`
- `0x18001c830`
- `0x18001c8a8`
- `0x18001ca88`

## callees

- `0x18000c1b4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c451`

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
0x18001c438  push    rbx
0x18001c43a  sub     rsp, 20h
0x18001c43e  mov     rbx, rcx
0x18001c441  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18001c446  mov     rcx, rax
0x18001c449  mov     rdx, rbx
0x18001c44c  add     rsp, 20h
0x18001c450  pop     rbx
0x18001c451  jmp     cs:__imp_GetProcAddress
```
