# [thunk]:ATL::CComObject<CL2TPDiagHelper>::AddRef`adjustor{8}' (void)

- ea: `0x180006210`
- end: `0x180006219`
- name: `?AddRef@?$CComObject@VCL2TPDiagHelper@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800061e0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CL2TPDiagHelper>::AddRef(__int64 a1)
{
  return ATL::CComObject<CL2TPDiagHelper>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180006210  sub     rcx, 8
0x180006214  jmp     ?AddRef@?$CComObject@VCL2TPDiagHelper@@@ATL@@UEAAKXZ; ATL::CComObject<CL2TPDiagHelper>::AddRef(void)
```
