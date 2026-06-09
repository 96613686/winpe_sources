# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18001d960`
- end: `0x18001d981`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `33`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001cf10`
- `0x18001cf50`
- `0x1800233d0`
- `0x180026f08`
- `0x180026f68`
- `0x180026fe0`
- `0x18002706c`

## callees

- `0x18001d930`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d974`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d974`

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
0x18001d960  push    rbx
0x18001d962  sub     rsp, 20h
0x18001d966  mov     rbx, rcx
0x18001d969  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18001d96e  mov     rcx, rax; hModule
0x18001d971  mov     rdx, rbx; lpProcName
0x18001d974  call    cs:__imp_GetProcAddress
0x18001d97a  nop
0x18001d97b  add     rsp, 20h
0x18001d97f  pop     rbx
0x18001d980  retn
```
