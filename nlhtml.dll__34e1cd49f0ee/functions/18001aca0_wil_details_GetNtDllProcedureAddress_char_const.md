# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18001aca0`
- end: `0x18001acc0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001617c`
- `0x180019460`
- `0x1800194a0`
- `0x18001af34`
- `0x18001b060`
- `0x18001b11c`
- `0x18001b194`
- `0x18001b370`

## callees

- `0x18001ac70`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001acb9`

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
0x18001aca0  push    rbx
0x18001aca2  sub     rsp, 20h
0x18001aca6  mov     rbx, rcx
0x18001aca9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18001acae  mov     rcx, rax
0x18001acb1  mov     rdx, rbx
0x18001acb4  add     rsp, 20h
0x18001acb8  pop     rbx
0x18001acb9  jmp     cs:__imp_GetProcAddress
```
