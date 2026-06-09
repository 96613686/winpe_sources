# ATL::SafeDecrementReferenceMultiThread(long volatile *)

- ea: `0x180004fd4`
- end: `0x180004ff6`
- name: `?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `34`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800037e8`
- `0x180004d90`
- `0x180004e20`
- `0x180004e90`

## callees

- `0x180004fd4`

## pseudocode

```c
__int64 __fastcall ATL::SafeDecrementReferenceMultiThread(volatile int *a1)
{
  signed __int32 v1; // r8d

  do
    v1 = *a1;
  while ( *a1 != 0x7FFFFFFF && v1 != _InterlockedCompareExchange(a1, v1 - 1, v1) );
  return (unsigned int)(v1 - 1);
}

```

## disassembly

```asm
0x180004fd4  mov     r9d, 7FFFFFFFh
0x180004fda  jmp     short loc_180004FE9
0x180004fdc  lea     edx, [r8-1]
0x180004fe0  mov     eax, r8d
0x180004fe3  lock cmpxchg [rcx], edx
0x180004fe7  jz      short loc_180004FF1
0x180004fe9  mov     r8d, [rcx]
0x180004fec  cmp     r8d, r9d
0x180004fef  jnz     short loc_180004FDC
0x180004ff1  lea     eax, [r8-1]
0x180004ff5  retn
```
