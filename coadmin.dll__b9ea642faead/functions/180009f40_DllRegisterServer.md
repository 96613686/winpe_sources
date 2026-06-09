# DllRegisterServer

- ea: `0x180009f40`
- end: `0x180009f4c`
- name: `DllRegisterServer`
- size: `12`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000f998`

## string_xrefs

- `0x180009f40`: `InstallComponent`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  const unsigned __int16 *v0; // rcx

  return CallRegisterComponent(v0, "InstallComponent");
}

```

## disassembly

```asm
0x180009f40  lea     rdx, aInstallcompone; "InstallComponent"
0x180009f47  jmp     ?CallRegisterComponent@@YAJPEBGPEAD@Z; CallRegisterComponent(ushort const *,char *)
```
