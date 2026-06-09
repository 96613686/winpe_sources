# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180006b70`
- end: `0x180006b90`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800060a0`
- `0x1800060e0`
- `0x1800068a0`
- `0x180010064`
- `0x1800128ac`
- `0x18001290c`
- `0x180012984`
- `0x180012a10`

## callees

- `0x180006b40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006b89`

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
0x180006b70  push    rbx
0x180006b72  sub     rsp, 20h
0x180006b76  mov     rbx, rcx
0x180006b79  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180006b7e  mov     rcx, rax
0x180006b81  mov     rdx, rbx
0x180006b84  add     rsp, 20h
0x180006b88  pop     rbx
0x180006b89  jmp     cs:__imp_GetProcAddress
```
