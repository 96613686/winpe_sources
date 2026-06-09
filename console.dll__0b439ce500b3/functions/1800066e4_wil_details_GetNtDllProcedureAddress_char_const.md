# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1800066e4`
- end: `0x180006709`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `37`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800058d0`
- `0x180005910`

## callees

- `0x1800066ac`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800066fd`

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
0x1800066e4  push    rbx
0x1800066e6  sub     rsp, 20h
0x1800066ea  mov     rbx, rcx
0x1800066ed  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1800066f2  mov     rcx, rax
0x1800066f5  mov     rdx, rbx
0x1800066f8  add     rsp, 20h
0x1800066fc  pop     rbx
0x1800066fd  jmp     cs:__imp_GetProcAddress
```
