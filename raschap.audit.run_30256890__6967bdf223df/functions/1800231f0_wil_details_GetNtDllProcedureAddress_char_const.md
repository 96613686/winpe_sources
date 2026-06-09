# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1800231f0`
- end: `0x180023211`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `33`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000fc14`
- `0x180021ba0`
- `0x180021be0`
- `0x1800222d4`
- `0x1800236ac`
- `0x180023724`

## callees

- `0x1800231c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023204`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023204`

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
0x1800231f0  push    rbx
0x1800231f2  sub     rsp, 20h
0x1800231f6  mov     rbx, rcx
0x1800231f9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1800231fe  mov     rcx, rax; hModule
0x180023201  mov     rdx, rbx; lpProcName
0x180023204  call    cs:__imp_GetProcAddress
0x18002320a  nop
0x18002320b  add     rsp, 20h
0x18002320f  pop     rbx
0x180023210  retn
```
