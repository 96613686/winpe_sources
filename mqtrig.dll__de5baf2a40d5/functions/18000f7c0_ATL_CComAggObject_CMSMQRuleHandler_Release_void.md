# ATL::CComAggObject<CMSMQRuleHandler>::Release(void)

- ea: `0x18000f7c0`
- end: `0x18000f7fb`
- name: `?Release@?$CComAggObject@VCMSMQRuleHandler@@@ATL@@UEAAKXZ`
- size: `59`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000dbcc`
- `0x18000f7c0`
- `0x18000fae4`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMSMQRuleHandler>::Release(__int64 a1)
{
  unsigned int v1; // ebx
  void *v2; // r10

  v1 = ATL::SafeDecrementReferenceMultiThread((volatile int *)(a1 + 8));
  if ( !v1 )
  {
    _InterlockedIncrement(&dword_18002CFF8);
    if ( v2 )
      ATL::CComAggObject<CMSMQRuleHandler>::`scalar deleting destructor'(v2);
    _InterlockedDecrement(&dword_18002CFF8);
  }
  return v1;
}

```

## disassembly

```asm
0x18000f7c0  push    rbx
0x18000f7c2  sub     rsp, 20h
0x18000f7c6  mov     r10, rcx
0x18000f7c9  add     rcx, 8; volatile int *
0x18000f7cd  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000f7d2  mov     ebx, eax
0x18000f7d4  test    eax, eax
0x18000f7d6  jnz     short loc_18000F7F3
0x18000f7d8  lock inc cs:dword_18002CFF8
0x18000f7df  test    r10, r10
0x18000f7e2  jz      short loc_18000F7EC
0x18000f7e4  mov     rcx, r10; Block
0x18000f7e7  call    ??_G?$CComAggObject@VCMSMQRuleHandler@@@ATL@@QEAAPEAXI@Z; ATL::CComAggObject<CMSMQRuleHandler>::`scalar deleting destructor'(uint)
0x18000f7ec  lock dec cs:dword_18002CFF8
0x18000f7f3  mov     eax, ebx
0x18000f7f5  add     rsp, 20h
0x18000f7f9  pop     rbx
0x18000f7fa  retn
```
