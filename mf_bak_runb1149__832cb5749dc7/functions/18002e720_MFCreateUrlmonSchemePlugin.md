# MFCreateUrlmonSchemePlugin

- ea: `0x18002e720`
- end: `0x18002e74b`
- name: `MFCreateUrlmonSchemePlugin`
- size: `43`
- prototype: `__int64 __fastcall(IID *riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e739`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e739`

## pseudocode

```c
HRESULT __fastcall MFCreateUrlmonSchemePlugin(IID *riid, LPVOID *ppv)
{
  return CoCreateInstance(&stru_180070020, 0, 1u, riid, ppv);
}

```

## disassembly

```asm
0x18002e720  sub     rsp, 38h
0x18002e724  mov     [rsp+38h+ppv], rdx; ppv
0x18002e729  mov     r9, rcx; riid
0x18002e72c  xor     edx, edx; pUnkOuter
0x18002e72e  lea     rcx, stru_180070020; rclsid
0x18002e735  lea     r8d, [rdx+1]; dwClsContext
0x18002e739  call    cs:CoCreateInstance
0x18002e740  nop     dword ptr [rax+rax+00h]
0x18002e745  add     rsp, 38h
0x18002e749  retn
```
