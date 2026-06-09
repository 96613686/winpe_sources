# MFCreateDrmNetNDSchemePlugin

- ea: `0x18002dc90`
- end: `0x18002dcbb`
- name: `MFCreateDrmNetNDSchemePlugin`
- size: `43`
- prototype: `__int64 __fastcall(IID *riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002dca9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002dca9`

## pseudocode

```c
HRESULT __fastcall MFCreateDrmNetNDSchemePlugin(IID *riid, LPVOID *ppv)
{
  return CoCreateInstance(&stru_18006F2A8, 0, 1u, riid, ppv);
}

```

## disassembly

```asm
0x18002dc90  sub     rsp, 38h
0x18002dc94  mov     [rsp+38h+ppv], rdx; ppv
0x18002dc99  mov     r9, rcx; riid
0x18002dc9c  xor     edx, edx; pUnkOuter
0x18002dc9e  lea     rcx, stru_18006F2A8; rclsid
0x18002dca5  lea     r8d, [rdx+1]; dwClsContext
0x18002dca9  call    cs:CoCreateInstance
0x18002dcb0  nop     dword ptr [rax+rax+00h]
0x18002dcb5  add     rsp, 38h
0x18002dcb9  retn
```
