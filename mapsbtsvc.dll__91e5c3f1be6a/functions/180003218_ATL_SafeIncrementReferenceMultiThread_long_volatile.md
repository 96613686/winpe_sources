# ATL::SafeIncrementReferenceMultiThread(long volatile *)

- ea: `0x180003218`
- end: `0x18000323f`
- name: `?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `39`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002bc0`
- `0x180002bd0`

## callees

- `0x180003218`

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
0x180003218  mov     r9d, 7FFFFFFFh
0x18000321e  jmp     short loc_18000322D
0x180003220  lea     edx, [r8+1]
0x180003224  mov     eax, r8d
0x180003227  lock cmpxchg [rcx], edx
0x18000322b  jz      short loc_180003237
0x18000322d  mov     r8d, [rcx]
0x180003230  cmp     r8d, r9d
0x180003233  jnz     short loc_180003220
0x180003235  jmp     short loc_18000323B
0x180003237  lea     r9d, [r8+1]
0x18000323b  mov     eax, r9d
0x18000323e  retn
```
