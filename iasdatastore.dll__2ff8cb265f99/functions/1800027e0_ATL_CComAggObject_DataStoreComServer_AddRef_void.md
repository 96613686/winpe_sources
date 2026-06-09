# ATL::CComAggObject<DataStoreComServer>::AddRef(void)

- ea: `0x1800027e0`
- end: `0x180002809`
- name: `?AddRef@?$CComAggObject@VDataStoreComServer@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800027e0`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<DataStoreComServer>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 8);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x1800027e0  mov     r9d, 7FFFFFFFh
0x1800027e6  jmp     short loc_1800027F6
0x1800027e8  lea     edx, [r8+1]
0x1800027ec  mov     eax, r8d
0x1800027ef  lock cmpxchg [rcx+8], edx
0x1800027f4  jz      short loc_180002801
0x1800027f6  mov     r8d, [rcx+8]
0x1800027fa  cmp     r8d, r9d
0x1800027fd  jnz     short loc_1800027E8
0x1800027ff  jmp     short loc_180002805
0x180002801  lea     r9d, [r8+1]
0x180002805  mov     eax, r9d
0x180002808  retn
```
