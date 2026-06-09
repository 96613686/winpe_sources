# MFCreateNetSchemePlugin

- ea: `0x18002e600`
- end: `0x18002e62b`
- name: `MFCreateNetSchemePlugin`
- size: `43`
- prototype: `HRESULT __stdcall(const IID *const riid, LPVOID *ppvHandler)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e619`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e619`

## pseudocode

```c
HRESULT __stdcall MFCreateNetSchemePlugin(const IID *const riid, LPVOID *ppvHandler)
{
  return CoCreateInstance(&stru_180070060, 0, 1u, riid, ppvHandler);
}

```

## disassembly

```asm
0x18002e600  sub     rsp, 38h
0x18002e604  mov     [rsp+38h+ppv], rdx; ppv
0x18002e609  mov     r9, rcx; riid
0x18002e60c  xor     edx, edx; pUnkOuter
0x18002e60e  lea     rcx, stru_180070060; rclsid
0x18002e615  lea     r8d, [rdx+1]; dwClsContext
0x18002e619  call    cs:CoCreateInstance
0x18002e620  nop     dword ptr [rax+rax+00h]
0x18002e625  add     rsp, 38h
0x18002e629  retn
```
