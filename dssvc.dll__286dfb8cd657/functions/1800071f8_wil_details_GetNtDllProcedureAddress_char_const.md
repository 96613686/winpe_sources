# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1800071f8`
- end: `0x180007218`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006290`
- `0x1800062d0`
- `0x180006ad0`
- `0x18000ae48`
- `0x18000af74`
- `0x18000b3fc`
- `0x18000b474`
- `0x18000b64c`
- `0x18000b6b8`

## callees

- `0x1800071c8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007211`

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
0x1800071f8  push    rbx
0x1800071fa  sub     rsp, 20h
0x1800071fe  mov     rbx, rcx
0x180007201  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180007206  mov     rcx, rax
0x180007209  mov     rdx, rbx
0x18000720c  add     rsp, 20h
0x180007210  pop     rbx
0x180007211  jmp     cs:__imp_GetProcAddress
```
