# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x10007690`
- end: `0x100076b6`
- name: `?wil_details_GetNtDllProcedureAddress@@YGP6GHXZPBD@Z`
- size: `38`
- prototype: `int (__stdcall *__cdecl(const char *))()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x10007710`

## callees

- `0x10007690`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x100076ae`
- `KERNEL32!GetProcAddress` at `0x100076ae`
- `KERNEL32!GetModuleHandleW` at `0x100076a1`
- `KERNEL32!GetModuleHandleW` at `0x100076a1`

## string_xrefs

- `0x1000769c`: `ntdll.dll`

## pseudocode

```c
FARPROC __thiscall wil_details_GetNtDllProcedureAddress(const CHAR *this)
{
  HMODULE ModuleHandleW; // eax

  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  return GetProcAddress(ModuleHandleW, this);
}

```

## disassembly

```asm
0x10007690  mov     eax, ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x10007695  push    esi
0x10007696  mov     esi, ecx
0x10007698  test    eax, eax
0x1000769a  jnz     short loc_100076AC
0x1000769c  push    offset ModuleName; "ntdll.dll"
0x100076a1  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x100076a7  mov     ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A, eax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x100076ac  push    esi; lpProcName
0x100076ad  push    eax; hModule
0x100076ae  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x100076b4  pop     esi
0x100076b5  retn
```
