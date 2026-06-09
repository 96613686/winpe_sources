# MFCreateNSCByteStreamPlugin

- ea: `0x18002e5c0`
- end: `0x18002e5eb`
- name: `MFCreateNSCByteStreamPlugin`
- size: `43`
- prototype: `HRESULT __fastcall(IID *riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e5d9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e5d9`

## pseudocode

```c
HRESULT __fastcall MFCreateNSCByteStreamPlugin(IID *riid, LPVOID *ppv)
{
  return CoCreateInstance(&stru_18006F288, 0, 1u, riid, ppv);
}

```

## disassembly

```asm
0x18002e5c0  sub     rsp, 38h
0x18002e5c4  mov     [rsp+38h+ppv], rdx; ppv
0x18002e5c9  mov     r9, rcx; riid
0x18002e5cc  xor     edx, edx; pUnkOuter
0x18002e5ce  lea     rcx, stru_18006F288; rclsid
0x18002e5d5  lea     r8d, [rdx+1]; dwClsContext
0x18002e5d9  call    cs:CoCreateInstance
0x18002e5e0  nop     dword ptr [rax+rax+00h]
0x18002e5e5  add     rsp, 38h
0x18002e5e9  retn
```
