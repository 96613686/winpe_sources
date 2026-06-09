# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180009fb8`
- end: `0x180009fdd`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `37`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008e60`
- `0x180008ea0`
- `0x18000e45c`
- `0x18000e588`
- `0x18000e650`
- `0x18000e6c8`
- `0x18000e8a8`
- `0x18000e914`

## callees

- `0x180009f80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009fd1`

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
0x180009fb8  push    rbx
0x180009fba  sub     rsp, 20h
0x180009fbe  mov     rbx, rcx
0x180009fc1  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180009fc6  mov     rcx, rax
0x180009fc9  mov     rdx, rbx
0x180009fcc  add     rsp, 20h
0x180009fd0  pop     rbx
0x180009fd1  jmp     cs:__imp_GetProcAddress
```
