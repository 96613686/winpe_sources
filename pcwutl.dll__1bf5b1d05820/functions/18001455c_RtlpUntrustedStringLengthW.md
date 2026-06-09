# RtlpUntrustedStringLengthW

- ea: `0x18001455c`
- end: `0x1800145ba`
- name: `RtlpUntrustedStringLengthW`
- size: `94`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800139e4`
- `0x18001417c`
- `0x18001446c`

## callees

- `0x18001455c`

## pseudocode

```c
__int64 __fastcall RtlpUntrustedStringLengthW(_WORD *a1, unsigned __int64 a2, unsigned __int64 a3)
{
  __int64 v3; // r9
  _WORD *v4; // rax
  _WORD *v5; // rdx

  v3 = 0;
  if ( a3 >= 2 && a1 && a2 && ((unsigned __int8)a1 & 1) == 0 && (unsigned __int64)a1 >= a2 && a2 + a3 >= a2 )
  {
    v4 = a1;
    v5 = (_WORD *)(a3 + a2 - (a3 & 1));
    if ( a1 < v5 )
    {
      while ( *v4 )
      {
        if ( ++v4 >= v5 )
          goto LABEL_10;
      }
      return v4 - a1;
    }
LABEL_10:
    if ( v4 != v5 )
      return v4 - a1;
  }
  return v3;
}

```

## disassembly

```asm
0x18001455c  xor     r10d, r10d
0x18001455f  mov     r9d, r10d
0x180014562  cmp     r8, 2
0x180014566  jb      short loc_1800145B6
0x180014568  test    rcx, rcx
0x18001456b  jz      short loc_1800145B6
0x18001456d  test    rdx, rdx
0x180014570  jz      short loc_1800145B6
0x180014572  test    cl, 1
0x180014575  jnz     short loc_1800145B6
0x180014577  cmp     rcx, rdx
0x18001457a  jb      short loc_1800145B6
0x18001457c  lea     rax, [rdx+r8]
0x180014580  cmp     rax, rdx
0x180014583  jb      short loc_1800145B6
0x180014585  mov     rax, r8
0x180014588  and     eax, 1
0x18001458b  sub     rdx, rax
0x18001458e  mov     rax, rcx
0x180014591  add     rdx, r8
0x180014594  cmp     rcx, rdx
0x180014597  jnb     short loc_1800145A8
0x180014599  cmp     [rax], r10w
0x18001459d  jz      short loc_1800145AD
0x18001459f  add     rax, 2
0x1800145a3  cmp     rax, rdx
0x1800145a6  jb      short loc_180014599
0x1800145a8  cmp     rax, rdx
0x1800145ab  jz      short loc_1800145B6
0x1800145ad  mov     r9, rax
0x1800145b0  sub     r9, rcx
0x1800145b3  sar     r9, 1
0x1800145b6  mov     rax, r9
0x1800145b9  retn
```
