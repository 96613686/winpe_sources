# DllRegisterServer

- ea: `0x1800079e0`
- end: `0x1800079f5`
- name: `DllRegisterServer`
- size: `21`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `ATL!__imp_AtlModuleRegisterServer` at `0x1800079ee`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  return AtlModuleRegisterServer(&_Module, 1);
}

```

## disassembly

```asm
0x1800079e0  xor     r8d, r8d
0x1800079e3  lea     rcx, ?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x1800079ea  lea     edx, [r8+1]
0x1800079ee  jmp     cs:__imp_AtlModuleRegisterServer
```
