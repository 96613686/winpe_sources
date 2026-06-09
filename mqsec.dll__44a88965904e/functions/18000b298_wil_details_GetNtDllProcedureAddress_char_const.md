# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000b298`
- end: `0x18000b2b9`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `33`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005cc8`
- `0x1800098c0`
- `0x180009900`
- `0x18000b4f0`
- `0x18000b550`
- `0x18000b5c8`
- `0x18000b654`

## callees

- `0x18000b268`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000b2ac`
- `KERNEL32!GetProcAddress` at `0x18000b2ac`

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
0x18000b298  push    rbx
0x18000b29a  sub     rsp, 20h
0x18000b29e  mov     rbx, rcx
0x18000b2a1  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000b2a6  mov     rcx, rax; hModule
0x18000b2a9  mov     rdx, rbx; lpProcName
0x18000b2ac  call    cs:__imp_GetProcAddress
0x18000b2b2  nop
0x18000b2b3  add     rsp, 20h
0x18000b2b7  pop     rbx
0x18000b2b8  retn
```
