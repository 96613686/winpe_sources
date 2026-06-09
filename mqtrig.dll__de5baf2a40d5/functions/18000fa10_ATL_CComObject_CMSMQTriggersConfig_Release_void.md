# ATL::CComObject<CMSMQTriggersConfig>::Release(void)

- ea: `0x18000fa10`
- end: `0x18000fa4b`
- name: `?Release@?$CComObject@VCMSMQTriggersConfig@@@ATL@@UEAAKXZ`
- size: `59`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fa60`

## callees

- `0x18000dcbc`
- `0x18000fa10`
- `0x18000fae4`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSMQTriggersConfig>::Release(__int64 a1)
{
  unsigned int v1; // ebx
  CMSMQTriggersConfig *v2; // r10

  v1 = ATL::SafeDecrementReferenceMultiThread((volatile int *)(a1 + 16));
  if ( !v1 )
  {
    _InterlockedIncrement(&dword_18002CFF8);
    if ( v2 )
      ATL::CComObject<CMSMQTriggersConfig>::`scalar deleting destructor'(v2);
    _InterlockedDecrement(&dword_18002CFF8);
  }
  return v1;
}

```

## disassembly

```asm
0x18000fa10  push    rbx
0x18000fa12  sub     rsp, 20h
0x18000fa16  mov     r10, rcx
0x18000fa19  add     rcx, 10h; volatile int *
0x18000fa1d  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000fa22  mov     ebx, eax
0x18000fa24  test    eax, eax
0x18000fa26  jnz     short loc_18000FA43
0x18000fa28  lock inc cs:dword_18002CFF8
0x18000fa2f  test    r10, r10
0x18000fa32  jz      short loc_18000FA3C
0x18000fa34  mov     rcx, r10; Block
0x18000fa37  call    ??_G?$CComObject@VCMSMQTriggersConfig@@@ATL@@QEAAPEAXI@Z; ATL::CComObject<CMSMQTriggersConfig>::`scalar deleting destructor'(uint)
0x18000fa3c  lock dec cs:dword_18002CFF8
0x18000fa43  mov     eax, ebx
0x18000fa45  add     rsp, 20h
0x18000fa49  pop     rbx
0x18000fa4a  retn
```
