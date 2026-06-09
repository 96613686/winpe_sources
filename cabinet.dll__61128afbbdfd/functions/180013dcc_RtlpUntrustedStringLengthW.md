# RtlpUntrustedStringLengthW

- ea: `0x180013dcc`
- end: `0x180013e2a`
- name: `RtlpUntrustedStringLengthW`
- size: `94`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800134a0`
- `0x180013530`
- `0x180013624`

## callees

- `0x180013dcc`

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
0x180013dcc  xor     r10d, r10d
0x180013dcf  mov     r9d, r10d
0x180013dd2  cmp     r8, 2
0x180013dd6  jb      short loc_180013E26
0x180013dd8  test    rcx, rcx
0x180013ddb  jz      short loc_180013E26
0x180013ddd  test    rdx, rdx
0x180013de0  jz      short loc_180013E26
0x180013de2  test    cl, 1
0x180013de5  jnz     short loc_180013E26
0x180013de7  cmp     rcx, rdx
0x180013dea  jb      short loc_180013E26
0x180013dec  lea     rax, [rdx+r8]
0x180013df0  cmp     rax, rdx
0x180013df3  jb      short loc_180013E26
0x180013df5  mov     rax, r8
0x180013df8  and     eax, 1
0x180013dfb  sub     rdx, rax
0x180013dfe  mov     rax, rcx
0x180013e01  add     rdx, r8
0x180013e04  cmp     rcx, rdx
0x180013e07  jnb     short loc_180013E18
0x180013e09  cmp     [rax], r10w
0x180013e0d  jz      short loc_180013E1D
0x180013e0f  add     rax, 2
0x180013e13  cmp     rax, rdx
0x180013e16  jb      short loc_180013E09
0x180013e18  cmp     rax, rdx
0x180013e1b  jz      short loc_180013E26
0x180013e1d  mov     r9, rax
0x180013e20  sub     r9, rcx
0x180013e23  sar     r9, 1
0x180013e26  mov     rax, r9
0x180013e29  retn
```
