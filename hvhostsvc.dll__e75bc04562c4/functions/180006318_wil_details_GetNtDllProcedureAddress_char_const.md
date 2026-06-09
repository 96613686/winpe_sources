# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180006318`
- end: `0x180006338`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005550`

## callees

- `0x1800062e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006331`

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
0x180006318  push    rbx
0x18000631a  sub     rsp, 20h
0x18000631e  mov     rbx, rcx
0x180006321  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180006326  mov     rcx, rax
0x180006329  mov     rdx, rbx
0x18000632c  add     rsp, 20h
0x180006330  pop     rbx
0x180006331  jmp     cs:__imp_GetProcAddress
```
