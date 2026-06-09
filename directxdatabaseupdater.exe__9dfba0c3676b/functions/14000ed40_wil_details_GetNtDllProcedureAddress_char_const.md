# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x14000ed40`
- end: `0x14000ed60`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000a510`
- `0x14000a550`
- `0x14000d7b0`
- `0x14000f090`
- `0x14000f0f0`
- `0x14000f168`
- `0x14000f1f4`
- `0x14000f260`

## callees

- `0x14000ed10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000ed59`

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
0x14000ed40  push    rbx
0x14000ed42  sub     rsp, 20h
0x14000ed46  mov     rbx, rcx
0x14000ed49  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x14000ed4e  mov     rcx, rax
0x14000ed51  mov     rdx, rbx
0x14000ed54  add     rsp, 20h
0x14000ed58  pop     rbx
0x14000ed59  jmp     cs:__imp_GetProcAddress
```
