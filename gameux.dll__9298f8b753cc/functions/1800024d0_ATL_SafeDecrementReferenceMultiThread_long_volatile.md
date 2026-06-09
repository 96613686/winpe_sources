# ATL::SafeDecrementReferenceMultiThread(long volatile *)

- ea: `0x1800024d0`
- end: `0x1800024f2`
- name: `?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `34`
- prototype: `unsigned int __fastcall(volatile int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002360`
- `0x180002400`
- `0x180002480`

## callees

- `0x1800024d0`

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
0x1800024d0  mov     r9d, 7FFFFFFFh
0x1800024d6  jmp     short loc_1800024E5
0x1800024d8  lea     edx, [r8-1]
0x1800024dc  mov     eax, r8d
0x1800024df  lock cmpxchg [rcx], edx
0x1800024e3  jz      short loc_1800024ED
0x1800024e5  mov     r8d, [rcx]
0x1800024e8  cmp     r8d, r9d
0x1800024eb  jnz     short loc_1800024D8
0x1800024ed  lea     eax, [r8-1]
0x1800024f1  retn
```
