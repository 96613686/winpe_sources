# ATL::CComAggObject<CMSMQTriggerSet>::Release(void)

- ea: `0x18000f810`
- end: `0x18000f84b`
- name: `?Release@?$CComAggObject@VCMSMQTriggerSet@@@ATL@@UEAAKXZ`
- size: `59`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000dbf4`
- `0x18000f810`
- `0x18000fae4`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMSMQTriggerSet>::Release(__int64 a1)
{
  unsigned int v1; // ebx
  void *v2; // r10

  v1 = ATL::SafeDecrementReferenceMultiThread((volatile int *)(a1 + 8));
  if ( !v1 )
  {
    _InterlockedIncrement(&dword_18002CFF8);
    if ( v2 )
      ATL::CComAggObject<CMSMQTriggerSet>::`scalar deleting destructor'(v2);
    _InterlockedDecrement(&dword_18002CFF8);
  }
  return v1;
}

```

## disassembly

```asm
0x18000f810  push    rbx
0x18000f812  sub     rsp, 20h
0x18000f816  mov     r10, rcx
0x18000f819  add     rcx, 8; volatile int *
0x18000f81d  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000f822  mov     ebx, eax
0x18000f824  test    eax, eax
0x18000f826  jnz     short loc_18000F843
0x18000f828  lock inc cs:dword_18002CFF8
0x18000f82f  test    r10, r10
0x18000f832  jz      short loc_18000F83C
0x18000f834  mov     rcx, r10; Block
0x18000f837  call    ??_G?$CComAggObject@VCMSMQTriggerSet@@@ATL@@QEAAPEAXI@Z; ATL::CComAggObject<CMSMQTriggerSet>::`scalar deleting destructor'(uint)
0x18000f83c  lock dec cs:dword_18002CFF8
0x18000f843  mov     eax, ebx
0x18000f845  add     rsp, 20h
0x18000f849  pop     rbx
0x18000f84a  retn
```
