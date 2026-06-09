# ATL::SafeIncrementReferenceMultiThread(long volatile *)

- ea: `0x18000ee90`
- end: `0x18000eeb7`
- name: `?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `39`
- prototype: `unsigned int __fastcall(volatile int *)`
- caller_count: `25`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005bf8`
- `0x180005dd4`
- `0x180005ea4`
- `0x18000b480`
- `0x18000cb10`
- `0x18000e100`
- `0x18000e110`
- `0x18000f278`
- `0x180016140`
- `0x180016150`
- `0x1800163e0`
- `0x18001649c`
- `0x180016f10`
- `0x180017910`
- `0x1800179cc`
- `0x180025020`
- `0x180028208`
- `0x18002de28`
- `0x1800327e8`
- `0x1800378e8`
- `0x18003c3b0`
- `0x18003cc58`
- `0x18003cd90`
- `0x18003ce6c`
- `0x1800432c0`

## callees

- `0x18000ee90`

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
0x18000ee90  mov     r9d, 7FFFFFFFh
0x18000ee96  jmp     short loc_18000EEA5
0x18000ee98  lea     edx, [r8+1]
0x18000ee9c  mov     eax, r8d
0x18000ee9f  lock cmpxchg [rcx], edx
0x18000eea3  jz      short loc_18000EEAF
0x18000eea5  mov     r8d, [rcx]
0x18000eea8  cmp     r8d, r9d
0x18000eeab  jnz     short loc_18000EE98
0x18000eead  jmp     short loc_18000EEB3
0x18000eeaf  lea     r9d, [r8+1]
0x18000eeb3  mov     eax, r9d
0x18000eeb6  retn
```
