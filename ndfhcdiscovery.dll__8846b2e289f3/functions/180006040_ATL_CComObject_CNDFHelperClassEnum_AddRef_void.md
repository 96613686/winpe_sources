# ATL::CComObject<CNDFHelperClassEnum>::AddRef(void)

- ea: `0x180006040`
- end: `0x180006069`
- name: `?AddRef@?$CComObject@VCNDFHelperClassEnum@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006040`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CNDFHelperClassEnum>::AddRef(__int64 a1)
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
0x180006040  mov     r9d, 7FFFFFFFh
0x180006046  jmp     short loc_180006056
0x180006048  lea     edx, [r8+1]
0x18000604c  mov     eax, r8d
0x18000604f  lock cmpxchg [rcx+8], edx
0x180006054  jz      short loc_180006061
0x180006056  mov     r8d, [rcx+8]
0x18000605a  cmp     r8d, r9d
0x18000605d  jnz     short loc_180006048
0x18000605f  jmp     short loc_180006065
0x180006061  lea     r9d, [r8+1]
0x180006065  mov     eax, r9d
0x180006068  retn
```
