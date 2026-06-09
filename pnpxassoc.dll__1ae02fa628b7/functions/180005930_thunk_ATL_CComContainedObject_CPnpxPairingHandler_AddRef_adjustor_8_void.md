# [thunk]:ATL::CComContainedObject<CPnpxPairingHandler>::AddRef`adjustor{8}' (void)

- ea: `0x180005930`
- end: `0x180005939`
- name: `?AddRef@?$CComContainedObject@VCPnpxPairingHandler@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005910`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CPnpxPairingHandler>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<CPnpxPairingHandler>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180005930  sub     rcx, 8
0x180005934  jmp     ?AddRef@?$CComContainedObject@VCPnpxPairingHandler@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CPnpxPairingHandler>::AddRef(void)
```
