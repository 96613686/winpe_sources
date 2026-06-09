# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18001de78`
- end: `0x18001de9d`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `37`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800105ec`
- `0x18001b9e0`
- `0x18001ba20`
- `0x18001c7b4`
- `0x18001ce40`
- `0x18001e224`
- `0x18001e29c`

## callees

- `0x18001de40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001de91`

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
0x18001de78  push    rbx
0x18001de7a  sub     rsp, 20h
0x18001de7e  mov     rbx, rcx
0x18001de81  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18001de86  mov     rcx, rax
0x18001de89  mov     rdx, rbx
0x18001de8c  add     rsp, 20h
0x18001de90  pop     rbx
0x18001de91  jmp     cs:__imp_GetProcAddress
```
