# MFCreateSAMIByteStreamPlugin

- ea: `0x18002e680`
- end: `0x18002e6ab`
- name: `MFCreateSAMIByteStreamPlugin`
- size: `43`
- prototype: `HRESULT __fastcall(IID *riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e699`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e699`

## pseudocode

```c
HRESULT __fastcall MFCreateSAMIByteStreamPlugin(IID *riid, LPVOID *ppv)
{
  return CoCreateInstance(&stru_18006F278, 0, 1u, riid, ppv);
}

```

## disassembly

```asm
0x18002e680  sub     rsp, 38h
0x18002e684  mov     [rsp+38h+ppv], rdx; ppv
0x18002e689  mov     r9, rcx; riid
0x18002e68c  xor     edx, edx; pUnkOuter
0x18002e68e  lea     rcx, stru_18006F278; rclsid
0x18002e695  lea     r8d, [rdx+1]; dwClsContext
0x18002e699  call    cs:CoCreateInstance
0x18002e6a0  nop     dword ptr [rax+rax+00h]
0x18002e6a5  add     rsp, 38h
0x18002e6a9  retn
```
