# ATL::CComObject<CPersistDSO>::Release(void)

- ea: `0x180019c70`
- end: `0x180019c9e`
- name: `?Release@?$CComObject@VCPersistDSO@@@ATL@@UEAAKXZ`
- size: `46`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180019cb0`
- `0x180019cc0`
- `0x180019cd0`
- `0x180019cf0`
- `0x180019d10`
- `0x180019d30`
- `0x180019d50`
- `0x180019d60`
- `0x180019d70`

## callees

- `0x18000ca08`
- `0x180018eb0`
- `0x180019c70`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPersistDSO>::Release(__int64 a1)
{
  unsigned int v1; // ebx
  void *v2; // r10

  v1 = ATL::SafeDecrementReferenceMultiThread((int *)(a1 + 48));
  if ( !v1 && v2 )
    ATL::CComObject<CPersistDSO>::`scalar deleting destructor'(v2);
  return v1;
}

```

## disassembly

```asm
0x180019c70  push    rbx
0x180019c72  sub     rsp, 20h
0x180019c76  mov     r10, rcx
0x180019c79  add     rcx, 30h ; '0'; int *
0x180019c7d  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPEAJ@Z; ATL::SafeDecrementReferenceMultiThread(long *)
0x180019c82  mov     ebx, eax
0x180019c84  test    eax, eax
0x180019c86  jnz     short loc_180019C95
0x180019c88  test    r10, r10
0x180019c8b  jz      short loc_180019C95
0x180019c8d  mov     rcx, r10; void *
0x180019c90  call    ??_G?$CComObject@VCPersistDSO@@@ATL@@QEAAPEAXI@Z; ATL::CComObject<CPersistDSO>::`scalar deleting destructor'(uint)
0x180019c95  mov     eax, ebx
0x180019c97  add     rsp, 20h
0x180019c9b  pop     rbx
0x180019c9c  retn
```
