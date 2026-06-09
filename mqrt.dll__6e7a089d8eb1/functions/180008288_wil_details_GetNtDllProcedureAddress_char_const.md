# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180008288`
- end: `0x1800082a9`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `33`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006880`
- `0x1800068c0`
- `0x180008890`
- `0x1800088f0`
- `0x180008968`
- `0x1800089f4`
- `0x180008a60`

## callees

- `0x180008258`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000829c`
- `KERNEL32!GetProcAddress` at `0x18000829c`

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
0x180008288  push    rbx
0x18000828a  sub     rsp, 20h
0x18000828e  mov     rbx, rcx
0x180008291  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180008296  mov     rcx, rax; hModule
0x180008299  mov     rdx, rbx; lpProcName
0x18000829c  call    cs:__imp_GetProcAddress
0x1800082a2  nop
0x1800082a3  add     rsp, 20h
0x1800082a7  pop     rbx
0x1800082a8  retn
```
