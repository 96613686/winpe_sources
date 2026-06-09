# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18002a024`
- end: `0x18002a044`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001ab34`
- `0x180028d80`
- `0x180028dc0`
- `0x18002cc04`
- `0x18002cc7c`
- `0x18002ce54`

## callees

- `0x180029ff4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a03d`

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
0x18002a024  push    rbx
0x18002a026  sub     rsp, 20h
0x18002a02a  mov     rbx, rcx
0x18002a02d  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18002a032  mov     rcx, rax
0x18002a035  mov     rdx, rbx
0x18002a038  add     rsp, 20h
0x18002a03c  pop     rbx
0x18002a03d  jmp     cs:__imp_GetProcAddress
```
