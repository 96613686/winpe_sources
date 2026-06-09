# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x14000e99c`
- end: `0x14000e9bc`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140012ff0`
- `0x140013030`
- `0x140017b04`
- `0x140018254`
- `0x140018380`
- `0x1400187a4`
- `0x14001881c`

## callees

- `0x140005a40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e9b5`

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
0x14000e99c  push    rbx
0x14000e99e  sub     rsp, 20h
0x14000e9a2  mov     rbx, rcx
0x14000e9a5  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x14000e9aa  mov     rcx, rax
0x14000e9ad  mov     rdx, rbx
0x14000e9b0  add     rsp, 20h
0x14000e9b4  pop     rbx
0x14000e9b5  jmp     cs:__imp_GetProcAddress
```
