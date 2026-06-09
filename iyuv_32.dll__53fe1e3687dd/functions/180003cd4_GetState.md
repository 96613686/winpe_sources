# GetState

- ea: `0x180003cd4`
- end: `0x180003d1a`
- name: `GetState`
- size: `70`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002710`

## callees

- `0x180003cd4`

## pseudocode

```c
__int64 __fastcall GetState(__int64 a1, _OWORD *a2, unsigned int a3)
{
  _OWORD *v4; // rax

  if ( a2 )
  {
    if ( a3 < 0x60 )
      return 0;
    v4 = *(_OWORD **)(a1 + 8);
    *a2 = *v4;
    a2[1] = v4[1];
    a2[2] = v4[2];
    a2[3] = v4[3];
    a2[4] = v4[4];
    a2[5] = v4[5];
  }
  return 96;
}

```

## disassembly

```asm
0x180003cd4  test    rdx, rdx
0x180003cd7  jz      short loc_180003D14
0x180003cd9  cmp     r8d, 60h ; '`'
0x180003cdd  jnb     short loc_180003CE2
0x180003cdf  xor     eax, eax
0x180003ce1  retn
0x180003ce2  mov     rax, [rcx+8]
0x180003ce6  movups  xmm0, xmmword ptr [rax]
0x180003ce9  movups  xmmword ptr [rdx], xmm0
0x180003cec  movups  xmm1, xmmword ptr [rax+10h]
0x180003cf0  movups  xmmword ptr [rdx+10h], xmm1
0x180003cf4  movups  xmm0, xmmword ptr [rax+20h]
0x180003cf8  movups  xmmword ptr [rdx+20h], xmm0
0x180003cfc  movups  xmm1, xmmword ptr [rax+30h]
0x180003d00  movups  xmmword ptr [rdx+30h], xmm1
0x180003d04  movups  xmm0, xmmword ptr [rax+40h]
0x180003d08  movups  xmmword ptr [rdx+40h], xmm0
0x180003d0c  movups  xmm1, xmmword ptr [rax+50h]
0x180003d10  movups  xmmword ptr [rdx+50h], xmm1
0x180003d14  mov     eax, 60h ; '`'
0x180003d19  retn
```
