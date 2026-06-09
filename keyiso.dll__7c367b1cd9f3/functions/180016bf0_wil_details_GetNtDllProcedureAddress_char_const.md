# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180016bf0`
- end: `0x180016c11`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `33`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000ae6c`
- `0x1800153c0`
- `0x180015400`
- `0x180015cac`
- `0x180016f0c`
- `0x180016f84`

## callees

- `0x180016bc0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016c04`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016c04`

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
0x180016bf0  push    rbx
0x180016bf2  sub     rsp, 20h
0x180016bf6  mov     rbx, rcx
0x180016bf9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180016bfe  mov     rcx, rax; hModule
0x180016c01  mov     rdx, rbx; lpProcName
0x180016c04  call    cs:__imp_GetProcAddress
0x180016c0a  nop
0x180016c0b  add     rsp, 20h
0x180016c0f  pop     rbx
0x180016c10  retn
```
