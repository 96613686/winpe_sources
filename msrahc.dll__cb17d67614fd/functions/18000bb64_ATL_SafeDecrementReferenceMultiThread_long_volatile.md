# ATL::SafeDecrementReferenceMultiThread(long volatile *)

- ea: `0x18000bb64`
- end: `0x18000bb86`
- name: `?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `34`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a0f8`
- `0x18000ba30`
- `0x18000bac0`
- `0x180013cd0`
- `0x180013d50`
- `0x180013db0`

## callees

- `0x18000bb64`

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
0x18000bb64  mov     r9d, 7FFFFFFFh
0x18000bb6a  jmp     short loc_18000BB79
0x18000bb6c  lea     edx, [r8-1]
0x18000bb70  mov     eax, r8d
0x18000bb73  lock cmpxchg [rcx], edx
0x18000bb77  jz      short loc_18000BB81
0x18000bb79  mov     r8d, [rcx]
0x18000bb7c  cmp     r8d, r9d
0x18000bb7f  jnz     short loc_18000BB6C
0x18000bb81  lea     eax, [r8-1]
0x18000bb85  retn
```
