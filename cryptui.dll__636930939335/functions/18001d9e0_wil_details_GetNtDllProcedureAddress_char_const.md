# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18001d9e0`
- end: `0x18001da01`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `33`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180016b08`
- `0x18001bc00`
- `0x18001bc40`
- `0x18001c29c`
- `0x18001dbd8`
- `0x18001dc38`
- `0x18001dcb0`

## callees

- `0x18001d9b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d9f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d9f4`

## pseudocode

```c
FARPROC __fastcall wil_details_GetNtDllProcedureAddress(LPCSTR lpProcName)
{
  HMODULE NtDllModuleHandle; // rax

  NtDllModuleHandle = wil_details_GetNtDllModuleHandle();
  return GetProcAddress(NtDllModuleHandle, lpProcName);
}

```

## disassembly

```asm
0x18001d9e0  push    rbx
0x18001d9e2  sub     rsp, 20h
0x18001d9e6  mov     rbx, rcx
0x18001d9e9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18001d9ee  mov     rcx, rax; hModule
0x18001d9f1  mov     rdx, rbx; lpProcName
0x18001d9f4  call    cs:__imp_GetProcAddress
0x18001d9fa  nop
0x18001d9fb  add     rsp, 20h
0x18001d9ff  pop     rbx
0x18001da00  retn
```
