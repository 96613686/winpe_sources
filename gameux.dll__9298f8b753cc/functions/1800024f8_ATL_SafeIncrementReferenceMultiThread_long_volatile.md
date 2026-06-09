# ATL::SafeIncrementReferenceMultiThread(long volatile *)

- ea: `0x1800024f8`
- end: `0x18000251f`
- name: `?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `39`
- prototype: `unsigned int __fastcall(volatile int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001d90`
- `0x180001dd0`
- `0x180001df0`

## callees

- `0x1800024f8`

## pseudocode

```c
__int64 __fastcall ATL::SafeIncrementReferenceMultiThread(volatile int *a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *a1;
    if ( *a1 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange(a1, v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x1800024f8  mov     r9d, 7FFFFFFFh
0x1800024fe  jmp     short loc_18000250D
0x180002500  lea     edx, [r8+1]
0x180002504  mov     eax, r8d
0x180002507  lock cmpxchg [rcx], edx
0x18000250b  jz      short loc_180002517
0x18000250d  mov     r8d, [rcx]
0x180002510  cmp     r8d, r9d
0x180002513  jnz     short loc_180002500
0x180002515  jmp     short loc_18000251B
0x180002517  lea     r9d, [r8+1]
0x18000251b  mov     eax, r9d
0x18000251e  retn
```
