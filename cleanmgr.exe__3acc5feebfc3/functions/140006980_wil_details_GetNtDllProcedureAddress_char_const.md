# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x140006980`
- end: `0x1400069a0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400059f0`
- `0x140005a30`
- `0x1400064b0`
- `0x140006e64`
- `0x14000ad18`
- `0x14000ae44`
- `0x14000b2cc`
- `0x14000b344`
- `0x14000b520`

## callees

- `0x140006950`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006999`

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
0x140006980  push    rbx
0x140006982  sub     rsp, 20h
0x140006986  mov     rbx, rcx
0x140006989  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x14000698e  mov     rcx, rax
0x140006991  mov     rdx, rbx
0x140006994  add     rsp, 20h
0x140006998  pop     rbx
0x140006999  jmp     cs:__imp_GetProcAddress
```
