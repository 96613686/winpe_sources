# ATL::SafeIncrementReferenceMultiThread(long *)

- ea: `0x18000ca34`
- end: `0x18000ca5b`
- name: `?SafeIncrementReferenceMultiThread@ATL@@YAKPEAJ@Z`
- size: `39`
- prototype: `unsigned int __fastcall(int *)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ac60`
- `0x180014150`
- `0x180018f00`
- `0x180018fe0`
- `0x180019660`

## callees

- `0x18000ca34`

## pseudocode

```c
__int64 __fastcall ATL::SafeIncrementReferenceMultiThread(int *a1)
{
  signed __int32 v1; // r8d

  do
  {
    v1 = *a1;
    if ( *a1 == 0x7FFFFFFF )
      return 0x7FFFFFFF;
  }
  while ( v1 != _InterlockedCompareExchange(a1, v1 + 1, v1) );
  return (unsigned int)(v1 + 1);
}

```

## disassembly

```asm
0x18000ca34  mov     r9d, 7FFFFFFFh
0x18000ca3a  jmp     short loc_18000CA49
0x18000ca3c  lea     edx, [r8+1]
0x18000ca40  mov     eax, r8d
0x18000ca43  lock cmpxchg [rcx], edx
0x18000ca47  jz      short loc_18000CA56
0x18000ca49  mov     r8d, [rcx]
0x18000ca4c  cmp     r8d, r9d
0x18000ca4f  jnz     short loc_18000CA3C
0x18000ca51  mov     eax, r9d
0x18000ca54  retn
0x18000ca56  lea     eax, [r8+1]
0x18000ca5a  retn
```
