# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000faa0`
- end: `0x18000fac1`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `33`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000cc80`
- `0x18000ccc0`
- `0x18000eae0`
- `0x18001af98`
- `0x18001b0c4`
- `0x18001b54c`
- `0x18001b5c4`
- `0x18001b7a0`
- `0x18001b80c`

## callees

- `0x18000fa70`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fab4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fab4`

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
0x18000faa0  push    rbx
0x18000faa2  sub     rsp, 20h
0x18000faa6  mov     rbx, rcx
0x18000faa9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000faae  mov     rcx, rax; hModule
0x18000fab1  mov     rdx, rbx; lpProcName
0x18000fab4  call    cs:__imp_GetProcAddress
0x18000faba  nop
0x18000fabb  add     rsp, 20h
0x18000fabf  pop     rbx
0x18000fac0  retn
```
