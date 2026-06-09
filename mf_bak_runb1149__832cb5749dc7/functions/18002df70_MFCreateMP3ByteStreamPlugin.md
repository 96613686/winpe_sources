# MFCreateMP3ByteStreamPlugin

- ea: `0x18002df70`
- end: `0x18002df9b`
- name: `MFCreateMP3ByteStreamPlugin`
- size: `43`
- prototype: `__int64 __fastcall(IID *riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002df89`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002df89`

## pseudocode

```c
HRESULT __fastcall MFCreateMP3ByteStreamPlugin(IID *riid, LPVOID *ppv)
{
  return CoCreateInstance(&stru_18006F268, 0, 1u, riid, ppv);
}

```

## disassembly

```asm
0x18002df70  sub     rsp, 38h
0x18002df74  mov     [rsp+38h+ppv], rdx; ppv
0x18002df79  mov     r9, rcx; riid
0x18002df7c  xor     edx, edx; pUnkOuter
0x18002df7e  lea     rcx, stru_18006F268; rclsid
0x18002df85  lea     r8d, [rdx+1]; dwClsContext
0x18002df89  call    cs:CoCreateInstance
0x18002df90  nop     dword ptr [rax+rax+00h]
0x18002df95  add     rsp, 38h
0x18002df99  retn
```
