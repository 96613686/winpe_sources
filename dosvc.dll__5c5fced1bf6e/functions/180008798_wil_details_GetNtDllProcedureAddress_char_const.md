# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180008798`
- end: `0x1800087b8`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007a10`

## callees

- `0x180008768`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800087b1`

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
0x180008798  push    rbx
0x18000879a  sub     rsp, 20h
0x18000879e  mov     rbx, rcx
0x1800087a1  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1800087a6  mov     rcx, rax
0x1800087a9  mov     rdx, rbx
0x1800087ac  add     rsp, 20h
0x1800087b0  pop     rbx
0x1800087b1  jmp     cs:__imp_GetProcAddress
```
