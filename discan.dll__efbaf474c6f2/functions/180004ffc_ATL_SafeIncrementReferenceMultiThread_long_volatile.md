# ATL::SafeIncrementReferenceMultiThread(long volatile *)

- ea: `0x180004ffc`
- end: `0x180005023`
- name: `?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `39`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003480`
- `0x1800034b0`
- `0x1800034c0`
- `0x1800037e8`

## callees

- `0x180004ffc`

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
0x180004ffc  mov     r9d, 7FFFFFFFh
0x180005002  jmp     short loc_180005011
0x180005004  lea     edx, [r8+1]
0x180005008  mov     eax, r8d
0x18000500b  lock cmpxchg [rcx], edx
0x18000500f  jz      short loc_18000501B
0x180005011  mov     r8d, [rcx]
0x180005014  cmp     r8d, r9d
0x180005017  jnz     short loc_180005004
0x180005019  jmp     short loc_18000501F
0x18000501b  lea     r9d, [r8+1]
0x18000501f  mov     eax, r9d
0x180005022  retn
```
