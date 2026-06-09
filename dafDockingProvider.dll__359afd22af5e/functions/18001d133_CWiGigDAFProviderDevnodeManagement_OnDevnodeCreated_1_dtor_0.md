# _CWiGigDAFProviderDevnodeManagement::OnDevnodeCreated_::_1_::dtor$0

- ea: `0x18001d133`
- end: `0x18001d13f`
- name: `_CWiGigDAFProviderDevnodeManagement::OnDevnodeCreated_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d4b0`

## pseudocode

```c
__int64 __fastcall CWiGigDAFProviderDevnodeManagement::OnDevnodeCreated_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return DAFPtr<unsigned short>::~DAFPtr<unsigned short>(a2 + 88);
}

```

## disassembly

```asm
0x18001d133  lea     rcx, [rdx+58h]
0x18001d13a  jmp     ??1?$DAFPtr@G@@QEAA@XZ; DAFPtr<ushort>::~DAFPtr<ushort>(void)
```
