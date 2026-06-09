# ATL::SafeIncrementReferenceMultiThread(long volatile *)

- ea: `0x18000fb0c`
- end: `0x18000fb33`
- name: `?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `39`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000dd60`
- `0x18000ddd0`
- `0x18000ddf0`
- `0x18000e2a0`
- `0x18000e388`
- `0x18000e488`
- `0x18000e570`

## callees

- `0x18000fb0c`

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
0x18000fb0c  mov     r9d, 7FFFFFFFh
0x18000fb12  jmp     short loc_18000FB21
0x18000fb14  lea     edx, [r8+1]
0x18000fb18  mov     eax, r8d
0x18000fb1b  lock cmpxchg [rcx], edx
0x18000fb1f  jz      short loc_18000FB2B
0x18000fb21  mov     r8d, [rcx]
0x18000fb24  cmp     r8d, r9d
0x18000fb27  jnz     short loc_18000FB14
0x18000fb29  jmp     short loc_18000FB2F
0x18000fb2b  lea     r9d, [r8+1]
0x18000fb2f  mov     eax, r9d
0x18000fb32  retn
```
