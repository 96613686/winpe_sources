# ATL::SafeDecrementReferenceMultiThread(long volatile *)

- ea: `0x180003894`
- end: `0x1800038b6`
- name: `?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `34`
- prototype: `unsigned int __fastcall(volatile int *)`
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002504`
- `0x180003800`
- `0x180004220`
- `0x180005f70`
- `0x180006988`
- `0x180008220`
- `0x180009b78`
- `0x180009c6c`
- `0x180009d90`
- `0x180009e88`
- `0x18000b410`
- `0x18000b480`

## callees

- `0x180003894`

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
0x180003894  mov     r9d, 7FFFFFFFh
0x18000389a  jmp     short loc_1800038A9
0x18000389c  lea     edx, [r8-1]
0x1800038a0  mov     eax, r8d
0x1800038a3  lock cmpxchg [rcx], edx
0x1800038a7  jz      short loc_1800038B1
0x1800038a9  mov     r8d, [rcx]
0x1800038ac  cmp     r8d, r9d
0x1800038af  jnz     short loc_18000389C
0x1800038b1  lea     eax, [r8-1]
0x1800038b5  retn
```
