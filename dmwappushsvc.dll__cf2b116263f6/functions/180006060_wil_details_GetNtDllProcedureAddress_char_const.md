# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180006060`
- end: `0x180006080`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005740`
- `0x180005780`
- `0x1800079e0`
- `0x18000b698`
- `0x18000d574`
- `0x18000d6a0`
- `0x18000da84`
- `0x18000dafc`

## callees

- `0x180006030`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006079`

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
0x180006060  push    rbx
0x180006062  sub     rsp, 20h
0x180006066  mov     rbx, rcx
0x180006069  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000606e  mov     rcx, rax
0x180006071  mov     rdx, rbx
0x180006074  add     rsp, 20h
0x180006078  pop     rbx
0x180006079  jmp     cs:__imp_GetProcAddress
```
