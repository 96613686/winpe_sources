# [thunk]:ATL::CComObject<CPnpxPairingHandler>::AddRef`adjustor{16}' (void)

- ea: `0x1800059e0`
- end: `0x1800059e9`
- name: `?AddRef@?$CComObject@VCPnpxPairingHandler@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800059a0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPnpxPairingHandler>::AddRef(__int64 a1)
{
  return ATL::CComObject<CPnpxPairingHandler>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x1800059e0  sub     rcx, 10h
0x1800059e4  jmp     ?AddRef@?$CComObject@VCPnpxPairingHandler@@@ATL@@UEAAKXZ; ATL::CComObject<CPnpxPairingHandler>::AddRef(void)
```
