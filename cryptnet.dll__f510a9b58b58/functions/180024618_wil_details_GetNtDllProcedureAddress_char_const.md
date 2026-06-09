# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180024618`
- end: `0x180024638`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001a800`
- `0x18001aff0`
- `0x1800235b0`
- `0x180024810`
- `0x180024870`
- `0x1800248e8`
- `0x180024974`

## callees

- `0x18001a008`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024631`

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
0x180024618  push    rbx
0x18002461a  sub     rsp, 20h
0x18002461e  mov     rbx, rcx
0x180024621  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180024626  mov     rcx, rax
0x180024629  mov     rdx, rbx
0x18002462c  add     rsp, 20h
0x180024630  pop     rbx
0x180024631  jmp     cs:__imp_GetProcAddress
```
