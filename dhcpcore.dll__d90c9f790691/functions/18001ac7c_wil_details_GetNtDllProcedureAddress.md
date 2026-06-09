# wil_details_GetNtDllProcedureAddress

- ea: `0x18001ac7c`
- end: `0x18001acb7`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180015080`
- `0x1800449e8`

## callees

- `0x18001ac7c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ac98`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ac98`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001acb0`

## string_xrefs

- `0x18001ac91`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil_details_GetNtDllProcedureAddress(const CHAR *a1)
{
  HMODULE ModuleHandleW; // rax

  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = (__int64)ModuleHandleW;
  }
  return GetProcAddress(ModuleHandleW, a1);
}

```

## disassembly

```asm
0x18001ac7c  push    rbx
0x18001ac7e  sub     rsp, 20h
0x18001ac82  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18001ac89  mov     rbx, rcx
0x18001ac8c  test    rax, rax
0x18001ac8f  jnz     short loc_18001ACA5
0x18001ac91  lea     rcx, ModuleName; "ntdll.dll"
0x18001ac98  call    cs:__imp_GetModuleHandleW
0x18001ac9e  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18001aca5  mov     rdx, rbx
0x18001aca8  mov     rcx, rax
0x18001acab  add     rsp, 20h
0x18001acaf  pop     rbx
0x18001acb0  jmp     cs:__imp_GetProcAddress
```
