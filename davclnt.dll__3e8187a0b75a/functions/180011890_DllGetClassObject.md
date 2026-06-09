# DllGetClassObject

- ea: `0x180011890`
- end: `0x18001189d`
- name: `DllGetClassObject`
- size: `13`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  *ppv = 0;
  return -2147221231;
}

```

## disassembly

```asm
0x180011890  mov     qword ptr [r8], 0
0x180011897  mov     eax, 80040111h
0x18001189c  retn
```
