# ATL::CComObject<CMSMQTriggerSet>::AddRef(void)

- ea: `0x18000ddd0`
- end: `0x18000ddd9`
- name: `?AddRef@?$CComObject@VCMSMQTriggerSet@@@ATL@@UEAAKXZ`
- size: `9`
- prototype: `unsigned int __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000dde0`

## callees

- `0x18000fb0c`

## pseudocode

```c
unsigned int __fastcall ATL::CComObject<CMSMQTriggerSet>::AddRef(__int64 a1)
{
  return ATL::SafeIncrementReferenceMultiThread((volatile int *)(a1 + 16));
}

```

## disassembly

```asm
0x18000ddd0  add     rcx, 10h; volatile int *
0x18000ddd4  jmp     ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
```
