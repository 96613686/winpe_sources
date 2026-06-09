# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000891c`
- end: `0x180008941`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `37`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007c70`

## callees

- `0x1800088e4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008935`

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
0x18000891c  push    rbx
0x18000891e  sub     rsp, 20h
0x180008922  mov     rbx, rcx
0x180008925  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000892a  mov     rcx, rax
0x18000892d  mov     rdx, rbx
0x180008930  add     rsp, 20h
0x180008934  pop     rbx
0x180008935  jmp     cs:__imp_GetProcAddress
```
