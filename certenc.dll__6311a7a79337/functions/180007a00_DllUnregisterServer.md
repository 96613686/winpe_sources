# DllUnregisterServer

- ea: `0x180007a00`
- end: `0x180007a1a`
- name: `DllUnregisterServer`
- size: `26`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `ATL!__imp_AtlModuleUnregisterServer` at `0x180007a0d`
- `ATL!__imp_AtlModuleUnregisterServer` at `0x180007a0d`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  AtlModuleUnregisterServer(&_Module, 0);
  return 0;
}

```

## disassembly

```asm
0x180007a00  sub     rsp, 28h
0x180007a04  xor     edx, edx
0x180007a06  lea     rcx, ?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x180007a0d  call    cs:__imp_AtlModuleUnregisterServer
0x180007a13  xor     eax, eax
0x180007a15  add     rsp, 28h
0x180007a19  retn
```
