# ATL::SafeDecrementReferenceMultiThread(long volatile *)

- ea: `0x18000fae4`
- end: `0x18000fb06`
- name: `?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `34`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e2a0`
- `0x18000e388`
- `0x18000e488`
- `0x18000e570`
- `0x18000f7c0`
- `0x18000f810`
- `0x18000f8f0`
- `0x18000f950`
- `0x18000f9b0`
- `0x18000fa10`
- `0x18000fa70`

## callees

- `0x18000fae4`

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
0x18000fae4  mov     r9d, 7FFFFFFFh
0x18000faea  jmp     short loc_18000FAF9
0x18000faec  lea     edx, [r8-1]
0x18000faf0  mov     eax, r8d
0x18000faf3  lock cmpxchg [rcx], edx
0x18000faf7  jz      short loc_18000FB01
0x18000faf9  mov     r8d, [rcx]
0x18000fafc  cmp     r8d, r9d
0x18000faff  jnz     short loc_18000FAEC
0x18000fb01  lea     eax, [r8-1]
0x18000fb05  retn
```
