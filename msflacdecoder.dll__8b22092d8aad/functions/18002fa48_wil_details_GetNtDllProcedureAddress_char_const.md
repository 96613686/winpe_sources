# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18002fa48`
- end: `0x18002fa83`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `59`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002e4c0`

## callees

- `0x18002fa48`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002fa64`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002fa64`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002fa7c`

## string_xrefs

- `0x18002fa5d`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil_details_GetNtDllProcedureAddress(const char *a1)
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
0x18002fa48  push    rbx
0x18002fa4a  sub     rsp, 20h
0x18002fa4e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002fa55  mov     rbx, rcx
0x18002fa58  test    rax, rax
0x18002fa5b  jnz     short loc_18002FA71
0x18002fa5d  lea     rcx, aNtdllDll; "ntdll.dll"
0x18002fa64  call    cs:__imp_GetModuleHandleW
0x18002fa6a  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002fa71  mov     rdx, rbx
0x18002fa74  mov     rcx, rax
0x18002fa77  add     rsp, 20h
0x18002fa7b  pop     rbx
0x18002fa7c  jmp     cs:__imp_GetProcAddress
```
