# [thunk]:ATL::CComObject<CRAHelperClass>::AddRef`adjustor{8}' (void)

- ea: `0x180008e10`
- end: `0x180008e19`
- name: `?AddRef@?$CComObject@VCRAHelperClass@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `unsigned int __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008e00`

## pseudocode

```c
unsigned int __fastcall ATL::CComObject<CRAHelperClass>::AddRef(__int64 a1)
{
  return ATL::CComObject<CRAHelperClass>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180008e10  sub     rcx, 8
0x180008e14  jmp     ?AddRef@?$CComObject@VCRAHelperClass@@@ATL@@UEAAKXZ; ATL::CComObject<CRAHelperClass>::AddRef(void)
```
