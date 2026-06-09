# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180008db8`
- end: `0x180008dd9`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `33`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800037c8`
- `0x180006e90`
- `0x180006ed0`
- `0x1800076fc`
- `0x180008fe0`
- `0x180009040`
- `0x1800090b8`

## callees

- `0x180008d88`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180008dcc`
- `KERNEL32!GetProcAddress` at `0x180008dcc`

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
0x180008db8  push    rbx
0x180008dba  sub     rsp, 20h
0x180008dbe  mov     rbx, rcx
0x180008dc1  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180008dc6  mov     rcx, rax; hModule
0x180008dc9  mov     rdx, rbx; lpProcName
0x180008dcc  call    cs:__imp_GetProcAddress
0x180008dd2  nop
0x180008dd3  add     rsp, 20h
0x180008dd7  pop     rbx
0x180008dd8  retn
```
