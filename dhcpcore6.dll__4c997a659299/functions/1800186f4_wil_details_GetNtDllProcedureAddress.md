# wil_details_GetNtDllProcedureAddress

- ea: `0x1800186f4`
- end: `0x18001873a`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `70`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000f2a8`
- `0x18002d580`

## callees

- `0x1800186f4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018710`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018710`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001872e`

## string_xrefs

- `0x180018709`: `ntdll.dll`

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
0x1800186f4  push    rbx
0x1800186f6  sub     rsp, 20h
0x1800186fa  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180018701  mov     rbx, rcx
0x180018704  test    rax, rax
0x180018707  jnz     short loc_180018723
0x180018709  lea     rcx, ModuleName; "ntdll.dll"
0x180018710  call    cs:__imp_GetModuleHandleW
0x180018717  nop     dword ptr [rax+rax+00h]
0x18001871c  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180018723  mov     rdx, rbx
0x180018726  mov     rcx, rax
0x180018729  add     rsp, 20h
0x18001872d  pop     rbx
0x18001872e  jmp     cs:__imp_GetProcAddress
```
