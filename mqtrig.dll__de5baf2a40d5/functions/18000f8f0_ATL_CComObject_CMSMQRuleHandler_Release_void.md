# ATL::CComObject<CMSMQRuleHandler>::Release(void)

- ea: `0x18000f8f0`
- end: `0x18000f92b`
- name: `?Release@?$CComObject@VCMSMQRuleHandler@@@ATL@@UEAAKXZ`
- size: `59`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f940`

## callees

- `0x18000dc44`
- `0x18000f8f0`
- `0x18000fae4`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSMQRuleHandler>::Release(__int64 a1)
{
  unsigned int v1; // ebx
  CMSMQRuleHandler *v2; // r10

  v1 = ATL::SafeDecrementReferenceMultiThread((volatile int *)(a1 + 16));
  if ( !v1 )
  {
    _InterlockedIncrement(&dword_18002CFF8);
    if ( v2 )
      ATL::CComObject<CMSMQRuleHandler>::`scalar deleting destructor'(v2);
    _InterlockedDecrement(&dword_18002CFF8);
  }
  return v1;
}

```

## disassembly

```asm
0x18000f8f0  push    rbx
0x18000f8f2  sub     rsp, 20h
0x18000f8f6  mov     r10, rcx
0x18000f8f9  add     rcx, 10h; volatile int *
0x18000f8fd  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000f902  mov     ebx, eax
0x18000f904  test    eax, eax
0x18000f906  jnz     short loc_18000F923
0x18000f908  lock inc cs:dword_18002CFF8
0x18000f90f  test    r10, r10
0x18000f912  jz      short loc_18000F91C
0x18000f914  mov     rcx, r10; Block
0x18000f917  call    ??_G?$CComObject@VCMSMQRuleHandler@@@ATL@@QEAAPEAXI@Z; ATL::CComObject<CMSMQRuleHandler>::`scalar deleting destructor'(uint)
0x18000f91c  lock dec cs:dword_18002CFF8
0x18000f923  mov     eax, ebx
0x18000f925  add     rsp, 20h
0x18000f929  pop     rbx
0x18000f92a  retn
```
