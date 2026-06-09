# ATL::SafeIncrementReferenceMultiThread(long volatile *)

- ea: `0x18000bb8c`
- end: `0x18000bbb3`
- name: `?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `39`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008e00`
- `0x180008e30`
- `0x18000a0f8`

## callees

- `0x18000bb8c`

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
0x18000bb8c  mov     r9d, 7FFFFFFFh
0x18000bb92  jmp     short loc_18000BBA1
0x18000bb94  lea     edx, [r8+1]
0x18000bb98  mov     eax, r8d
0x18000bb9b  lock cmpxchg [rcx], edx
0x18000bb9f  jz      short loc_18000BBAB
0x18000bba1  mov     r8d, [rcx]
0x18000bba4  cmp     r8d, r9d
0x18000bba7  jnz     short loc_18000BB94
0x18000bba9  jmp     short loc_18000BBAF
0x18000bbab  lea     r9d, [r8+1]
0x18000bbaf  mov     eax, r9d
0x18000bbb2  retn
```
