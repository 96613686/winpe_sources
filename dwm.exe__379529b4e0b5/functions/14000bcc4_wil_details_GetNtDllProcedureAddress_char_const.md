# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x14000bcc4`
- end: `0x14000bce4`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000a8a0`
- `0x14000a8e0`
- `0x14000bf74`
- `0x14000c0a0`
- `0x14000c15c`
- `0x14000c1d4`
- `0x14000c3ac`
- `0x14000c410`

## callees

- `0x14000bc94`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000bcdd`

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
0x14000bcc4  push    rbx
0x14000bcc6  sub     rsp, 20h
0x14000bcca  mov     rbx, rcx
0x14000bccd  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x14000bcd2  mov     rcx, rax
0x14000bcd5  mov     rdx, rbx
0x14000bcd8  add     rsp, 20h
0x14000bcdc  pop     rbx
0x14000bcdd  jmp     cs:__imp_GetProcAddress
```
