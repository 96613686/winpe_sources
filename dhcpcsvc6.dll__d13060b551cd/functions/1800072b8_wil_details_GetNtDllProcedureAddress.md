# wil_details_GetNtDllProcedureAddress

- ea: `0x1800072b8`
- end: `0x1800072f3`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `59`
- prototype: `FARPROC __fastcall(const CHAR *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800071bc`

## callees

- `0x1800072b8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800072ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800072d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800072d4`

## string_xrefs

- `0x1800072cd`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil_details_GetNtDllProcedureAddress(const CHAR *a1)
{
  HMODULE ModuleHandleW; // rax

  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  return GetProcAddress(ModuleHandleW, a1);
}

```

## disassembly

```asm
0x1800072b8  push    rbx
0x1800072ba  sub     rsp, 20h
0x1800072be  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x1800072c5  mov     rbx, rcx
0x1800072c8  test    rax, rax
0x1800072cb  jnz     short loc_1800072E1
0x1800072cd  lea     rcx, ModuleName; "ntdll.dll"
0x1800072d4  call    cs:__imp_GetModuleHandleW
0x1800072da  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x1800072e1  mov     rdx, rbx
0x1800072e4  mov     rcx, rax
0x1800072e7  add     rsp, 20h
0x1800072eb  pop     rbx
0x1800072ec  jmp     cs:__imp_GetProcAddress
```
