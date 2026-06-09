# ATL::SafeIncrementReferenceMultiThread(long volatile *)

- ea: `0x1800038bc`
- end: `0x1800038e3`
- name: `?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `39`
- prototype: `unsigned int __fastcall(volatile int *)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002200`
- `0x180002504`
- `0x180004220`
- `0x180006988`
- `0x1800090d0`
- `0x180009b78`
- `0x180009c6c`
- `0x180009d90`
- `0x180009e88`

## callees

- `0x1800038bc`

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
0x1800038bc  mov     r9d, 7FFFFFFFh
0x1800038c2  jmp     short loc_1800038D1
0x1800038c4  lea     edx, [r8+1]
0x1800038c8  mov     eax, r8d
0x1800038cb  lock cmpxchg [rcx], edx
0x1800038cf  jz      short loc_1800038DB
0x1800038d1  mov     r8d, [rcx]
0x1800038d4  cmp     r8d, r9d
0x1800038d7  jnz     short loc_1800038C4
0x1800038d9  jmp     short loc_1800038DF
0x1800038db  lea     r9d, [r8+1]
0x1800038df  mov     eax, r9d
0x1800038e2  retn
```
