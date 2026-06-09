# DllRegisterServer

- ea: `0x1800069e0`
- end: `0x1800069f8`
- name: `DllRegisterServer`
- size: `24`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, installer_update`

## import_xrefs

- `ADVPACK!RegInstallW` at `0x1800069f1`

## string_xrefs

- `0x1800069e7`: `RegDll`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  return RegInstallW(g_hinst, L"RegDll", 0);
}

```

## disassembly

```asm
0x1800069e0  mov     rcx, cs:g_hinst
0x1800069e7  lea     rdx, aRegdll; "RegDll"
0x1800069ee  xor     r8d, r8d
0x1800069f1  jmp     cs:__imp_RegInstallW
```
