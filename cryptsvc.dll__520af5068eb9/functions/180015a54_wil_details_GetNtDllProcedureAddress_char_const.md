# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180015a54`
- end: `0x180015a74`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000ce00`
- `0x18000daa0`
- `0x180014970`
- `0x180015c74`
- `0x180015da0`
- `0x18001621c`
- `0x180016294`
- `0x18001646c`

## callees

- `0x180015a24`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015a6d`

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
0x180015a54  push    rbx
0x180015a56  sub     rsp, 20h
0x180015a5a  mov     rbx, rcx
0x180015a5d  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180015a62  mov     rcx, rax
0x180015a65  mov     rdx, rbx
0x180015a68  add     rsp, 20h
0x180015a6c  pop     rbx
0x180015a6d  jmp     cs:__imp_GetProcAddress
```
