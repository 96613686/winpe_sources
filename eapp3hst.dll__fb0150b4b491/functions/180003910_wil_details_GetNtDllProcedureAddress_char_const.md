# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180003910`
- end: `0x180003930`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003210`
- `0x180003250`
- `0x18000c058`
- `0x18000c184`
- `0x18000c60c`
- `0x18000c684`
- `0x18000c860`
- `0x18000c8cc`

## callees

- `0x1800038e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003929`

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
0x180003910  push    rbx
0x180003912  sub     rsp, 20h
0x180003916  mov     rbx, rcx
0x180003919  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000391e  mov     rcx, rax
0x180003921  mov     rdx, rbx
0x180003924  add     rsp, 20h
0x180003928  pop     rbx
0x180003929  jmp     cs:__imp_GetProcAddress
```
