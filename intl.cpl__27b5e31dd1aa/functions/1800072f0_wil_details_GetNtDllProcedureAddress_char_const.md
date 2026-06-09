# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1800072f0`
- end: `0x180007310`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005cf0`
- `0x180005d30`
- `0x1800067f0`
- `0x18001d8c8`
- `0x18001d9f4`
- `0x18001de7c`
- `0x18001def4`
- `0x18001e0d0`
- `0x18001e13c`

## callees

- `0x1800072c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007309`

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
0x1800072f0  push    rbx
0x1800072f2  sub     rsp, 20h
0x1800072f6  mov     rbx, rcx
0x1800072f9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1800072fe  mov     rcx, rax
0x180007301  mov     rdx, rbx
0x180007304  add     rsp, 20h
0x180007308  pop     rbx
0x180007309  jmp     cs:__imp_GetProcAddress
```
