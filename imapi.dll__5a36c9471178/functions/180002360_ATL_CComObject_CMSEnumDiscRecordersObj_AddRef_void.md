# ATL::CComObject<CMSEnumDiscRecordersObj>::AddRef(void)

- ea: `0x180002360`
- end: `0x180002389`
- name: `?AddRef@?$CComObject@VCMSEnumDiscRecordersObj@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002360`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSEnumDiscRecordersObj>::AddRef(__int64 a1)
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
0x180002360  mov     r9d, 7FFFFFFFh
0x180002366  jmp     short loc_180002376
0x180002368  lea     edx, [r8+1]
0x18000236c  mov     eax, r8d
0x18000236f  lock cmpxchg [rcx+8], edx
0x180002374  jz      short loc_180002381
0x180002376  mov     r8d, [rcx+8]
0x18000237a  cmp     r8d, r9d
0x18000237d  jnz     short loc_180002368
0x18000237f  jmp     short loc_180002385
0x180002381  lea     r9d, [r8+1]
0x180002385  mov     eax, r9d
0x180002388  retn
```
