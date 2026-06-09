# MFCreateHttpSchemePlugin

- ea: `0x18002def0`
- end: `0x18002df1b`
- name: `MFCreateHttpSchemePlugin`
- size: `43`
- prototype: `__int64 __fastcall(IID *riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002df09`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002df09`

## pseudocode

```c
HRESULT __fastcall MFCreateHttpSchemePlugin(IID *riid, LPVOID *ppv)
{
  return CoCreateInstance(&stru_180070178, 0, 1u, riid, ppv);
}

```

## disassembly

```asm
0x18002def0  sub     rsp, 38h
0x18002def4  mov     [rsp+38h+ppv], rdx; ppv
0x18002def9  mov     r9, rcx; riid
0x18002defc  xor     edx, edx; pUnkOuter
0x18002defe  lea     rcx, stru_180070178; rclsid
0x18002df05  lea     r8d, [rdx+1]; dwClsContext
0x18002df09  call    cs:CoCreateInstance
0x18002df10  nop     dword ptr [rax+rax+00h]
0x18002df15  add     rsp, 38h
0x18002df19  retn
```
