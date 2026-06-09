# ATL::SafeDecrementReferenceMultiThread(long volatile *)

- ea: `0x1800031f0`
- end: `0x180003212`
- name: `?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `34`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003130`
- `0x1800031a0`
- `0x180003880`

## callees

- `0x1800031f0`

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
0x1800031f0  mov     r9d, 7FFFFFFFh
0x1800031f6  jmp     short loc_180003205
0x1800031f8  lea     edx, [r8-1]
0x1800031fc  mov     eax, r8d
0x1800031ff  lock cmpxchg [rcx], edx
0x180003203  jz      short loc_18000320D
0x180003205  mov     r8d, [rcx]
0x180003208  cmp     r8d, r9d
0x18000320b  jnz     short loc_1800031F8
0x18000320d  lea     eax, [r8-1]
0x180003211  retn
```
