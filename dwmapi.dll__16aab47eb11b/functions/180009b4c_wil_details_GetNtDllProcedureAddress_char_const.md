# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180009b4c`
- end: `0x180009b6c`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800088fc`
- `0x180009b10`
- `0x18000ff20`
- `0x1800101bc`
- `0x180010d0c`
- `0x180010e38`
- `0x180010efc`
- `0x180010f74`

## callees

- `0x180009b74`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009b65`

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
0x180009b4c  push    rbx
0x180009b4e  sub     rsp, 20h
0x180009b52  mov     rbx, rcx
0x180009b55  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180009b5a  mov     rcx, rax
0x180009b5d  mov     rdx, rbx
0x180009b60  add     rsp, 20h
0x180009b64  pop     rbx
0x180009b65  jmp     cs:__imp_GetProcAddress
```
