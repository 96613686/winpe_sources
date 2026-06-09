# [thunk]:ATL::CComObject<CIsoBurn>::AddRef`adjustor{8}' (void)

- ea: `0x1400042e0`
- end: `0x1400042e9`
- name: `?AddRef@?$CComObject@VCIsoBurn@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400042b0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIsoBurn>::AddRef(__int64 a1)
{
  return ATL::CComObject<CIsoBurn>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x1400042e0  sub     rcx, 8
0x1400042e4  jmp     ?AddRef@?$CComObject@VCIsoBurn@@@ATL@@UEAAKXZ; ATL::CComObject<CIsoBurn>::AddRef(void)
```
