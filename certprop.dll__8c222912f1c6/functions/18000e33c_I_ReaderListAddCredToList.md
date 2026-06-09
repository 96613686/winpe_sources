# I_ReaderListAddCredToList

- ea: `0x18000e33c`
- end: `0x18000e387`
- name: `I_ReaderListAddCredToList`
- size: `75`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int16 *, __int64 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b09c`
- `0x18001f548`
- `0x18001f9ec`
- `0x1800205c4`

## callees

- `0x18000e33c`

## pseudocode

```c
__int64 __fastcall I_ReaderListAddCredToList(_QWORD *a1, unsigned __int16 *a2, __int64 *a3)
{
  __int64 v3; // rax
  int v4; // r10d
  int v5; // r9d
  __int64 result; // rax

  if ( !a2 || !*a1 )
    goto LABEL_13;
  v3 = *a1 - (_QWORD)a2;
  do
  {
    v4 = *(unsigned __int16 *)((char *)a2 + v3);
    v5 = *a2 - v4;
    if ( v5 )
      break;
    ++a2;
  }
  while ( v4 );
  if ( !v5 )
  {
    result = *a3;
    a1[13] = *a3;
    *a3 = (__int64)a1;
  }
  else
  {
LABEL_13:
    while ( 1 )
    {
      result = *a3;
      if ( !*a3 )
        break;
      a3 = (__int64 *)(result + 104);
    }
    *a3 = (__int64)a1;
    a1[13] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000e33c  test    rdx, rdx
0x18000e33f  jz      short loc_18000E377
0x18000e341  mov     rax, [rcx]
0x18000e344  test    rax, rax
0x18000e347  jz      short loc_18000E377
0x18000e349  sub     rax, rdx
0x18000e34c  movzx   r9d, word ptr [rdx]
0x18000e350  movzx   r10d, word ptr [rdx+rax]
0x18000e355  sub     r9d, r10d
0x18000e358  jnz     short loc_18000E363
0x18000e35a  add     rdx, 2
0x18000e35e  test    r10d, r10d
0x18000e361  jnz     short loc_18000E34C
0x18000e363  test    r9d, r9d
0x18000e366  jnz     short loc_18000E377
0x18000e368  mov     rax, [r8]
0x18000e36b  mov     [rcx+68h], rax
0x18000e36f  mov     [r8], rcx
0x18000e372  retn
0x18000e373  lea     r8, [rax+68h]
0x18000e377  mov     rax, [r8]
0x18000e37a  test    rax, rax
0x18000e37d  jnz     short loc_18000E373
0x18000e37f  mov     [r8], rcx
0x18000e382  mov     [rcx+68h], rax
0x18000e386  retn
```
