# ATL::SafeDecrementReferenceMultiThread(long volatile *)

- ea: `0x180006498`
- end: `0x1800064ba`
- name: `?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `34`
- prototype: `unsigned int __fastcall(volatile int *)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004888`
- `0x1800049ac`
- `0x180004ac0`
- `0x180006070`
- `0x180006130`
- `0x1800061a0`
- `0x180006210`
- `0x180006280`

## callees

- `0x180006498`

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
0x180006498  mov     r9d, 7FFFFFFFh
0x18000649e  jmp     short loc_1800064AD
0x1800064a0  lea     edx, [r8-1]
0x1800064a4  mov     eax, r8d
0x1800064a7  lock cmpxchg [rcx], edx
0x1800064ab  jz      short loc_1800064B5
0x1800064ad  mov     r8d, [rcx]
0x1800064b0  cmp     r8d, r9d
0x1800064b3  jnz     short loc_1800064A0
0x1800064b5  lea     eax, [r8-1]
0x1800064b9  retn
```
