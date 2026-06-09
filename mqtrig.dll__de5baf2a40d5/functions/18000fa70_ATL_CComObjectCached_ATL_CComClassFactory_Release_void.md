# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x18000fa70`
- end: `0x18000faab`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `59`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000dce4`
- `0x18000fa70`
- `0x18000fae4`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(__int64 a1)
{
  unsigned int v1; // ebx
  void *v2; // r10

  v1 = ATL::SafeDecrementReferenceMultiThread((volatile int *)(a1 + 8));
  if ( v1 )
  {
    if ( v1 == 1 )
      _InterlockedDecrement(&dword_18002CFF8);
  }
  else if ( v2 )
  {
    ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(v2);
  }
  return v1;
}

```

## disassembly

```asm
0x18000fa70  push    rbx
0x18000fa72  sub     rsp, 20h
0x18000fa76  mov     r10, rcx
0x18000fa79  add     rcx, 8; volatile int *
0x18000fa7d  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000fa82  mov     ebx, eax
0x18000fa84  test    eax, eax
0x18000fa86  jnz     short loc_18000FA97
0x18000fa88  test    r10, r10
0x18000fa8b  jz      short loc_18000FAA3
0x18000fa8d  mov     rcx, r10; Block
0x18000fa90  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x18000fa95  jmp     short loc_18000FAA3
0x18000fa97  cmp     ebx, 1
0x18000fa9a  jnz     short loc_18000FAA3
0x18000fa9c  lock dec cs:dword_18002CFF8
0x18000faa3  mov     eax, ebx
0x18000faa5  add     rsp, 20h
0x18000faa9  pop     rbx
0x18000faaa  retn
```
