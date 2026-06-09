# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x18000ddf0`
- end: `0x18000de0e`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `30`
- prototype: `unsigned int __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000ddf0`
- `0x18000fb0c`

## pseudocode

```c
unsigned int __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(__int64 a1)
{
  unsigned int result; // eax

  result = ATL::SafeIncrementReferenceMultiThread((volatile int *)(a1 + 8));
  if ( result == 2 )
    _InterlockedIncrement(&dword_18002CFF8);
  return result;
}

```

## disassembly

```asm
0x18000ddf0  sub     rsp, 28h
0x18000ddf4  add     rcx, 8; volatile int *
0x18000ddf8  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x18000ddfd  cmp     eax, 2
0x18000de00  jnz     short loc_18000DE09
0x18000de02  lock inc cs:dword_18002CFF8
0x18000de09  add     rsp, 28h
0x18000de0d  retn
```
