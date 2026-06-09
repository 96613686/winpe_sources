# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000bd6c`
- end: `0x18000bd8c`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000bd30`
- `0x18000ca58`
- `0x180011480`
- `0x1800156b0`
- `0x180015e0c`
- `0x180015f38`
- `0x180015ffc`
- `0x180016074`

## callees

- `0x18000bd94`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bd85`

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
0x18000bd6c  push    rbx
0x18000bd6e  sub     rsp, 20h
0x18000bd72  mov     rbx, rcx
0x18000bd75  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000bd7a  mov     rcx, rax
0x18000bd7d  mov     rdx, rbx
0x18000bd80  add     rsp, 20h
0x18000bd84  pop     rbx
0x18000bd85  jmp     cs:__imp_GetProcAddress
```
