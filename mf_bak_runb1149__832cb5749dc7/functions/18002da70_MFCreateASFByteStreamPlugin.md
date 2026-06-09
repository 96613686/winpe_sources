# MFCreateASFByteStreamPlugin

- ea: `0x18002da70`
- end: `0x18002da9b`
- name: `MFCreateASFByteStreamPlugin`
- size: `43`
- prototype: `__int64 __fastcall(IID *riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002da89`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002da89`

## pseudocode

```c
HRESULT __fastcall MFCreateASFByteStreamPlugin(IID *riid, LPVOID *ppv)
{
  return CoCreateInstance(&stru_18006F248, 0, 1u, riid, ppv);
}

```

## disassembly

```asm
0x18002da70  sub     rsp, 38h
0x18002da74  mov     [rsp+38h+ppv], rdx; ppv
0x18002da79  mov     r9, rcx; riid
0x18002da7c  xor     edx, edx; pUnkOuter
0x18002da7e  lea     rcx, stru_18006F248; rclsid
0x18002da85  lea     r8d, [rdx+1]; dwClsContext
0x18002da89  call    cs:CoCreateInstance
0x18002da90  nop     dword ptr [rax+rax+00h]
0x18002da95  add     rsp, 38h
0x18002da99  retn
```
