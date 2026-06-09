# DllGetClassObject

- ea: `0x18000d0c0`
- end: `0x18000d0d7`
- name: `DllGetClassObject`
- size: `23`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## import_xrefs

- `ATL!__imp_AtlModuleGetClassObject` at `0x18000d0d0`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  return AtlModuleGetClassObject(&_Module, rclsid, riid, ppv);
}

```

## disassembly

```asm
0x18000d0c0  mov     r9, r8
0x18000d0c3  mov     r8, rdx
0x18000d0c6  mov     rdx, rcx
0x18000d0c9  lea     rcx, ?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x18000d0d0  jmp     cs:__imp_AtlModuleGetClassObject
```
