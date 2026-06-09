# RtlpUntrustedStringLengthW

- ea: `0x140008514`
- end: `0x140008572`
- name: `RtlpUntrustedStringLengthW`
- size: `94`
- prototype: `__int64 __fastcall(_WORD *, unsigned __int64, unsigned __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140007aec`
- `0x140008134`
- `0x140008424`

## callees

- `0x140008514`

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
0x140008514  xor     r10d, r10d
0x140008517  mov     r9d, r10d
0x14000851a  cmp     r8, 2
0x14000851e  jb      short loc_14000856E
0x140008520  test    rcx, rcx
0x140008523  jz      short loc_14000856E
0x140008525  test    rdx, rdx
0x140008528  jz      short loc_14000856E
0x14000852a  test    cl, 1
0x14000852d  jnz     short loc_14000856E
0x14000852f  cmp     rcx, rdx
0x140008532  jb      short loc_14000856E
0x140008534  lea     rax, [rdx+r8]
0x140008538  cmp     rax, rdx
0x14000853b  jb      short loc_14000856E
0x14000853d  mov     rax, r8
0x140008540  and     eax, 1
0x140008543  sub     rdx, rax
0x140008546  mov     rax, rcx
0x140008549  add     rdx, r8
0x14000854c  cmp     rcx, rdx
0x14000854f  jnb     short loc_140008560
0x140008551  cmp     [rax], r10w
0x140008555  jz      short loc_140008565
0x140008557  add     rax, 2
0x14000855b  cmp     rax, rdx
0x14000855e  jb      short loc_140008551
0x140008560  cmp     rax, rdx
0x140008563  jz      short loc_14000856E
0x140008565  mov     r9, rax
0x140008568  sub     r9, rcx
0x14000856b  sar     r9, 1
0x14000856e  mov     rax, r9
0x140008571  retn
```
