# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000a380`
- end: `0x18000a3a0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002dac`
- `0x180008ba0`
- `0x180008be0`
- `0x1800094c8`
- `0x18000a62c`
- `0x18000a6ac`
- `0x18000a724`

## callees

- `0x18000a350`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a399`

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
0x18000a380  push    rbx
0x18000a382  sub     rsp, 20h
0x18000a386  mov     rbx, rcx
0x18000a389  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000a38e  mov     rcx, rax
0x18000a391  mov     rdx, rbx
0x18000a394  add     rsp, 20h
0x18000a398  pop     rbx
0x18000a399  jmp     cs:__imp_GetProcAddress
```
