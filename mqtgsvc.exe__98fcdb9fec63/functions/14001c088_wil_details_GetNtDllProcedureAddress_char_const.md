# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x14001c088`
- end: `0x14001c0a9`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `33`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400172b0`
- `0x14001a3e0`
- `0x14001a420`
- `0x14001aabc`
- `0x14001c3d4`
- `0x14001c434`
- `0x14001c4ac`

## callees

- `0x14001c058`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14001c09c`
- `KERNEL32!GetProcAddress` at `0x14001c09c`

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
0x14001c088  push    rbx
0x14001c08a  sub     rsp, 20h
0x14001c08e  mov     rbx, rcx
0x14001c091  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x14001c096  mov     rcx, rax; hModule
0x14001c099  mov     rdx, rbx; lpProcName
0x14001c09c  call    cs:__imp_GetProcAddress
0x14001c0a2  nop
0x14001c0a3  add     rsp, 20h
0x14001c0a7  pop     rbx
0x14001c0a8  retn
```
