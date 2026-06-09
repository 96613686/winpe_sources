# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x14007bce0`
- end: `0x14007bd00`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400755f8`
- `0x14007a630`
- `0x14007a670`
- `0x14007b310`
- `0x14007bf68`
- `0x14007bfe0`
- `0x14007c06c`

## callees

- `0x14007bcb0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14007bcf9`

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
0x14007bce0  push    rbx
0x14007bce2  sub     rsp, 20h
0x14007bce6  mov     rbx, rcx
0x14007bce9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x14007bcee  mov     rcx, rax
0x14007bcf1  mov     rdx, rbx
0x14007bcf4  add     rsp, 20h
0x14007bcf8  pop     rbx
0x14007bcf9  jmp     cs:__imp_GetProcAddress
```
