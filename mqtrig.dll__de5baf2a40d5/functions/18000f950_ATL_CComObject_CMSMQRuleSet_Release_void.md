# ATL::CComObject<CMSMQRuleSet>::Release(void)

- ea: `0x18000f950`
- end: `0x18000f98b`
- name: `?Release@?$CComObject@VCMSMQRuleSet@@@ATL@@UEAAKXZ`
- size: `59`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f9a0`

## callees

- `0x18000dc6c`
- `0x18000f950`
- `0x18000fae4`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSMQRuleSet>::Release(__int64 a1)
{
  unsigned int v1; // ebx
  CMSMQRuleSet *v2; // r10

  v1 = ATL::SafeDecrementReferenceMultiThread((volatile int *)(a1 + 16));
  if ( !v1 )
  {
    _InterlockedIncrement(&dword_18002CFF8);
    if ( v2 )
      ATL::CComObject<CMSMQRuleSet>::`scalar deleting destructor'(v2);
    _InterlockedDecrement(&dword_18002CFF8);
  }
  return v1;
}

```

## disassembly

```asm
0x18000f950  push    rbx
0x18000f952  sub     rsp, 20h
0x18000f956  mov     r10, rcx
0x18000f959  add     rcx, 10h; volatile int *
0x18000f95d  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000f962  mov     ebx, eax
0x18000f964  test    eax, eax
0x18000f966  jnz     short loc_18000F983
0x18000f968  lock inc cs:dword_18002CFF8
0x18000f96f  test    r10, r10
0x18000f972  jz      short loc_18000F97C
0x18000f974  mov     rcx, r10; Block
0x18000f977  call    ??_G?$CComObject@VCMSMQRuleSet@@@ATL@@QEAAPEAXI@Z; ATL::CComObject<CMSMQRuleSet>::`scalar deleting destructor'(uint)
0x18000f97c  lock dec cs:dword_18002CFF8
0x18000f983  mov     eax, ebx
0x18000f985  add     rsp, 20h
0x18000f989  pop     rbx
0x18000f98a  retn
```
