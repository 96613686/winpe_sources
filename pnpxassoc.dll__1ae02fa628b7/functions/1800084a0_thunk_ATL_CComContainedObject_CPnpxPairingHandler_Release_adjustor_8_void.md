# [thunk]:ATL::CComContainedObject<CPnpxPairingHandler>::Release`adjustor{8}' (void)

- ea: `0x1800084a0`
- end: `0x1800084a9`
- name: `?Release@?$CComContainedObject@VCPnpxPairingHandler@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008480`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CPnpxPairingHandler>::Release(__int64 a1)
{
  return ATL::CComContainedObject<CPnpxPairingHandler>::Release(a1 - 8);
}

```

## disassembly

```asm
0x1800084a0  sub     rcx, 8
0x1800084a4  jmp     ?Release@?$CComContainedObject@VCPnpxPairingHandler@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CPnpxPairingHandler>::Release(void)
```
