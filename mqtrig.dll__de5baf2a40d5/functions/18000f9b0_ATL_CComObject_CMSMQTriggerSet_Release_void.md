# ATL::CComObject<CMSMQTriggerSet>::Release(void)

- ea: `0x18000f9b0`
- end: `0x18000f9eb`
- name: `?Release@?$CComObject@VCMSMQTriggerSet@@@ATL@@UEAAKXZ`
- size: `59`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000fa00`

## callees

- `0x18000dc94`
- `0x18000f9b0`
- `0x18000fae4`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSMQTriggerSet>::Release(__int64 a1)
{
  unsigned int v1; // ebx
  CMSMQTriggerSet *v2; // r10

  v1 = ATL::SafeDecrementReferenceMultiThread((volatile int *)(a1 + 16));
  if ( !v1 )
  {
    _InterlockedIncrement(&dword_18002CFF8);
    if ( v2 )
      ATL::CComObject<CMSMQTriggerSet>::`scalar deleting destructor'(v2);
    _InterlockedDecrement(&dword_18002CFF8);
  }
  return v1;
}

```

## disassembly

```asm
0x18000f9b0  push    rbx
0x18000f9b2  sub     rsp, 20h
0x18000f9b6  mov     r10, rcx
0x18000f9b9  add     rcx, 10h; volatile int *
0x18000f9bd  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000f9c2  mov     ebx, eax
0x18000f9c4  test    eax, eax
0x18000f9c6  jnz     short loc_18000F9E3
0x18000f9c8  lock inc cs:dword_18002CFF8
0x18000f9cf  test    r10, r10
0x18000f9d2  jz      short loc_18000F9DC
0x18000f9d4  mov     rcx, r10; Block
0x18000f9d7  call    ??_G?$CComObject@VCMSMQTriggerSet@@@ATL@@QEAAPEAXI@Z; ATL::CComObject<CMSMQTriggerSet>::`scalar deleting destructor'(uint)
0x18000f9dc  lock dec cs:dword_18002CFF8
0x18000f9e3  mov     eax, ebx
0x18000f9e5  add     rsp, 20h
0x18000f9e9  pop     rbx
0x18000f9ea  retn
```
