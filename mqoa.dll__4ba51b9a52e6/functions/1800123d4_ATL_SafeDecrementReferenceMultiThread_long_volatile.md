# ATL::SafeDecrementReferenceMultiThread(long volatile *)

- ea: `0x1800123d4`
- end: `0x1800123f6`
- name: `?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `34`
- prototype: `unsigned int __fastcall(volatile int *)`
- caller_count: `16`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011c20`
- `0x180011c70`
- `0x180011cc0`
- `0x180011d60`
- `0x180011db0`
- `0x180011e00`
- `0x180011e50`
- `0x180011ea0`
- `0x180011ef0`
- `0x180011f40`
- `0x180011f90`
- `0x180012160`
- `0x1800121c0`
- `0x1800122e0`
- `0x180012360`
- `0x180026140`

## callees

- `0x1800123d4`

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
0x1800123d4  mov     r9d, 7FFFFFFFh
0x1800123da  jmp     short loc_1800123E9
0x1800123dc  lea     edx, [r8-1]
0x1800123e0  mov     eax, r8d
0x1800123e3  lock cmpxchg [rcx], edx
0x1800123e7  jz      short loc_1800123F1
0x1800123e9  mov     r8d, [rcx]
0x1800123ec  cmp     r8d, r9d
0x1800123ef  jnz     short loc_1800123DC
0x1800123f1  lea     eax, [r8-1]
0x1800123f5  retn
```
