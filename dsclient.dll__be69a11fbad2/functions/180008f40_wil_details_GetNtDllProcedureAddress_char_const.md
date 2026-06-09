# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180008f40`
- end: `0x180008f60`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004954`
- `0x180007970`
- `0x1800079b0`
- `0x180009144`
- `0x180009270`
- `0x18000932c`
- `0x1800093a4`
- `0x18000957c`

## callees

- `0x180008f10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008f59`

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
0x180008f40  push    rbx
0x180008f42  sub     rsp, 20h
0x180008f46  mov     rbx, rcx
0x180008f49  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180008f4e  mov     rcx, rax
0x180008f51  mov     rdx, rbx
0x180008f54  add     rsp, 20h
0x180008f58  pop     rbx
0x180008f59  jmp     cs:__imp_GetProcAddress
```
