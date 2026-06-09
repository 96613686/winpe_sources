# ATL::CComAggObject<CDpSearchProtocol>::AddRef(void)

- ea: `0x180003690`
- end: `0x1800036b9`
- name: `?AddRef@?$CComAggObject@VCDpSearchProtocol@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003690`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CDpSearchProtocol>::AddRef(__int64 a1)
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
0x180003690  mov     r9d, 7FFFFFFFh
0x180003696  jmp     short loc_1800036A6
0x180003698  lea     edx, [r8+1]
0x18000369c  mov     eax, r8d
0x18000369f  lock cmpxchg [rcx+8], edx
0x1800036a4  jz      short loc_1800036B1
0x1800036a6  mov     r8d, [rcx+8]
0x1800036aa  cmp     r8d, r9d
0x1800036ad  jnz     short loc_180003698
0x1800036af  jmp     short loc_1800036B5
0x1800036b1  lea     r9d, [r8+1]
0x1800036b5  mov     eax, r9d
0x1800036b8  retn
```
