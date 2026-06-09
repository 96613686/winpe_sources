# ATL::SafeIncrementReferenceMultiThread(long volatile *)

- ea: `0x1800064c0`
- end: `0x1800064e7`
- name: `?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `39`
- prototype: `unsigned int __fastcall(volatile int *)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800039a0`
- `0x180003a00`
- `0x180003a20`
- `0x180004888`
- `0x1800049ac`
- `0x180004ac0`

## callees

- `0x1800064c0`

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
0x1800064c0  mov     r9d, 7FFFFFFFh
0x1800064c6  jmp     short loc_1800064D5
0x1800064c8  lea     edx, [r8+1]
0x1800064cc  mov     eax, r8d
0x1800064cf  lock cmpxchg [rcx], edx
0x1800064d3  jz      short loc_1800064DF
0x1800064d5  mov     r8d, [rcx]
0x1800064d8  cmp     r8d, r9d
0x1800064db  jnz     short loc_1800064C8
0x1800064dd  jmp     short loc_1800064E3
0x1800064df  lea     r9d, [r8+1]
0x1800064e3  mov     eax, r9d
0x1800064e6  retn
```
