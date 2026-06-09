# DeltaFrameC

- ea: `0x180002ee8`
- end: `0x1800031d1`
- name: `DeltaFrameC`
- size: `745`
- prototype: `__int64 __fastcall(_DWORD *, unsigned __int8 *, _BYTE *, __int64, unsigned int, int, int, __int64, unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800035d8`

## callees

- `0x180002ee8`
- `0x180003288`

## pseudocode

```c
__int64 __fastcall DeltaFrameC(
        _DWORD *a1,
        unsigned __int8 *a2,
        _BYTE *a3,
        __int64 a4,
        unsigned int a5,
        int a6,
        int a7,
        __int64 a8,
        unsigned int a9,
        int a10)
{
  int v10; // r13d
  int v12; // r9d
  _DWORD *v13; // rbp
  unsigned __int8 *v15; // r12
  int v16; // ebx
  unsigned int v17; // r15d
  int v18; // esi
  __int64 v19; // r14
  unsigned int v20; // ecx
  _WORD *v21; // rax
  int v22; // esi
  int v23; // r15d
  int v24; // r14d
  int v25; // r9d
  int v26; // edx
  int v27; // ebx
  unsigned __int8 *v28; // r8
  _BYTE *i; // r11
  __int64 v30; // rax
  int v31; // ecx
  int v32; // ebx
  __int64 v33; // rdx
  unsigned int v34; // r9d
  int v35; // eax
  int v36; // eax
  __int64 v37; // rcx
  __int64 result; // rax
  int v39; // [rsp+40h] [rbp-48h]
  unsigned int v41; // [rsp+98h] [rbp+10h]

  v10 = a6;
  v12 = a1[1];
  v13 = a1;
  v39 = a4;
  v15 = a2;
  v16 = a1[2];
  v17 = (v12 + 3) & 0xFFFFFFFC;
  v41 = v17;
  if ( (unsigned int)(a6 - 1) > 0xFE )
    v10 = 255;
  if ( !a2 )
  {
    if ( v16 > 0 )
    {
      v18 = a10;
      v19 = a8;
      v20 = a5;
      while ( 1 )
      {
        v21 = (_WORD *)EncodeFragment((_DWORD)a3, v13[1], a4, v20, (__int64)&a5, v19, v18, v10);
        if ( !v21 || a5 < 2 )
          return 0;
        v20 = a5 - 2;
        *v21 = 0;
        --v16;
        a4 = (__int64)(v21 + 1);
        LODWORD(a3) = v17 + (_DWORD)a3;
        a5 = v20;
        if ( v16 <= 0 )
          goto LABEL_40;
      }
    }
    goto LABEL_39;
  }
  if ( v16 <= 0 )
  {
LABEL_39:
    v20 = a5;
LABEL_40:
    if ( v20 < 2 )
      return 0;
    *(_WORD *)a4 = 256;
    result = 1;
    v13[4] = 1;
    v13[5] = a4 - v39 + 2;
    return result;
  }
  v22 = 0;
  v23 = 0;
  a6 = 0;
  while ( 1 )
  {
    v24 = 0;
    if ( v12 > 0 )
      break;
LABEL_38:
    ++v23;
    v22 -= v24;
    v37 = (int)(v41 - v12);
    v15 += v37;
    a3 += v37;
    if ( ++a6 >= v13[2] )
      goto LABEL_39;
  }
  while ( 1 )
  {
    v25 = v12 - v24;
    v26 = 0;
    v27 = 0;
    v28 = v15;
    for ( i = a3; v27 < v25; ++v27 )
    {
      v30 = *v28;
      if ( *i == (_BYTE)v30
        || (v13 = a1, *(_DWORD *)(a8 + 4 * (v30 + ((unsigned __int64)(unsigned __int8)*i << 8))) <= a9) )
      {
        ++v26;
      }
      else
      {
        if ( v26 >= a7 )
          goto LABEL_22;
        v26 = 0;
      }
      ++i;
      ++v28;
    }
    if ( v26 >= a7 )
    {
LABEL_22:
      v32 = v27 - v26;
      v31 = v26;
    }
    else
    {
      v31 = 0;
      v32 = v25;
    }
    if ( v32 )
      break;
    v22 += v31;
    v33 = v31;
    v32 = v31;
LABEL_37:
    v12 = v13[1];
    a3 += v33;
    v24 += v31;
    v15 += v32;
    if ( v24 >= v12 )
      goto LABEL_38;
  }
  v34 = a5;
  if ( v22 < 0 )
  {
    if ( a5 < 2 )
      return 0;
    v34 = a5 - 2;
    *(_WORD *)a4 = 0;
    v22 = v24;
    a4 += 2;
    a5 = v34;
    --v23;
  }
  if ( !(v23 + v22) )
  {
LABEL_35:
    a4 = EncodeFragment((_DWORD)a3, v32, a4, v34, (__int64)&a5, a8, a10, v10);
    if ( !a4 )
      return 0;
    v31 = v32;
    v33 = v32;
    goto LABEL_37;
  }
  while ( v34 >= 4 )
  {
    *(_WORD *)a4 = 512;
    v35 = v22;
    if ( v22 > 255 )
      v35 = 255;
    v22 -= v35;
    *(_BYTE *)(a4 + 2) = v35;
    v36 = v23;
    if ( v23 > 255 )
      v36 = 255;
    v34 -= 4;
    v23 -= v36;
    *(_BYTE *)(a4 + 3) = v36;
    a4 += 4;
    a5 = v34;
    if ( !(v23 + v22) )
      goto LABEL_35;
  }
  return 0;
}

```

## disassembly

```asm
0x180002ee8  mov     r11, rsp
0x180002eeb  mov     [r11+18h], rbx
0x180002eef  mov     [r11+8], rcx
0x180002ef3  push    rbp
0x180002ef4  push    rsi
0x180002ef5  push    rdi
0x180002ef6  push    r12
0x180002ef8  push    r13
0x180002efa  push    r14
0x180002efc  push    r15
0x180002efe  sub     rsp, 50h
0x180002f02  mov     r13d, [rsp+88h+arg_28]
0x180002f0a  mov     r10, r9
0x180002f0d  mov     r9d, [rcx+4]
0x180002f11  mov     rbp, rcx
0x180002f14  mov     ecx, 0FFh
0x180002f19  mov     qword ptr [rsp+88h+var_48], r10
0x180002f1e  mov     rdi, r8
0x180002f21  mov     r12, rdx
0x180002f24  lea     eax, [r13-1]
0x180002f28  mov     ebx, [rbp+8]
0x180002f2b  lea     r15d, [r9+3]
0x180002f2f  and     r15d, 0FFFFFFFCh
0x180002f33  cmp     eax, 0FEh
0x180002f38  mov     [rsp+88h+arg_8], r15d
0x180002f40  cmova   r13d, ecx
0x180002f44  test    rdx, rdx
0x180002f47  jnz     loc_180002FD5
0x180002f4d  test    ebx, ebx
0x180002f4f  jle     loc_18000318A
0x180002f55  mov     esi, [rsp+88h+arg_48]
0x180002f5c  mov     r14, [rsp+88h+arg_38]
0x180002f64  mov     ecx, [r11+28h]
0x180002f68  mov     edx, [rbp+4]
0x180002f6b  lea     rax, [rsp+88h+arg_20]
0x180002f73  mov     [rsp+88h+var_50], r13d
0x180002f78  mov     r9d, ecx
0x180002f7b  mov     [rsp+88h+var_58], esi
0x180002f7f  mov     r8, r10
0x180002f82  mov     [rsp+88h+var_60], r14
0x180002f87  mov     rcx, rdi
0x180002f8a  mov     [rsp+88h+var_68], rax
0x180002f8f  call    EncodeFragment
0x180002f94  mov     r10, rax
0x180002f97  test    rax, rax
0x180002f9a  jz      loc_180003196
0x180002fa0  mov     ecx, [rsp+88h+arg_20]
0x180002fa7  cmp     ecx, 2
0x180002faa  jb      loc_180003196
0x180002fb0  xor     eax, eax
0x180002fb2  add     ecx, 0FFFFFFFEh
0x180002fb5  mov     [r10], ax
0x180002fb9  dec     ebx
0x180002fbb  movsxd  rax, r15d
0x180002fbe  add     r10, 2
0x180002fc2  add     rdi, rax
0x180002fc5  mov     [rsp+88h+arg_20], ecx
0x180002fcc  test    ebx, ebx
0x180002fce  jg      short loc_180002F68
0x180002fd0  jmp     loc_180003191
0x180002fd5  test    ebx, ebx
0x180002fd7  jle     loc_18000318A
0x180002fdd  xor     esi, esi
0x180002fdf  xor     r15d, r15d
0x180002fe2  mov     [rsp+88h+arg_28], esi
0x180002fe9  xor     r14d, r14d
0x180002fec  test    r9d, r9d
0x180002fef  jle     loc_180003158
0x180002ff5  sub     r9d, r14d
0x180002ff8  xor     edx, edx
0x180002ffa  xor     ebx, ebx
0x180002ffc  mov     r8, r12
0x180002fff  mov     r11, rdi
0x180003002  test    r9d, r9d
0x180003005  jle     short loc_180003053
0x180003007  movzx   eax, byte ptr [r8]
0x18000300b  cmp     [r11], al
0x18000300e  jz      short loc_180003044
0x180003010  mov     ebp, [rsp+88h+arg_40]
0x180003017  movzx   ecx, byte ptr [r11]
0x18000301b  shl     rcx, 8
0x18000301f  add     rcx, rax
0x180003022  mov     rax, [rsp+88h+arg_38]
0x18000302a  cmp     [rax+rcx*4], ebp
0x18000302d  mov     rbp, [rsp+88h+arg_0]
0x180003035  jbe     short loc_180003044
0x180003037  cmp     edx, [rsp+88h+arg_30]
0x18000303e  jge     short loc_180003063
0x180003040  xor     edx, edx
0x180003042  jmp     short loc_180003046
0x180003044  inc     edx
0x180003046  inc     r11
0x180003049  inc     r8
0x18000304c  inc     ebx
0x18000304e  cmp     ebx, r9d
0x180003051  jl      short loc_180003007
0x180003053  cmp     edx, [rsp+88h+arg_30]
0x18000305a  jge     short loc_180003063
0x18000305c  xor     ecx, ecx
0x18000305e  mov     ebx, r9d
0x180003061  jmp     short loc_180003067
0x180003063  sub     ebx, edx
0x180003065  mov     ecx, edx
0x180003067  test    ebx, ebx
0x180003069  jnz     short loc_180003077
0x18000306b  add     esi, ecx
0x18000306d  movsxd  rdx, ecx
0x180003070  mov     ebx, ecx
0x180003072  jmp     loc_18000313F
0x180003077  mov     r9d, [rsp+88h+arg_20]
0x18000307f  test    esi, esi
0x180003081  jns     short loc_1800030A9
0x180003083  cmp     r9d, 2
0x180003087  jb      loc_180003196
0x18000308d  xor     eax, eax
0x18000308f  add     r9d, 0FFFFFFFEh
0x180003093  mov     [r10], ax
0x180003097  mov     esi, r14d
0x18000309a  add     r10, 2
0x18000309e  mov     [rsp+88h+arg_20], r9d
0x1800030a6  dec     r15d
0x1800030a9  lea     eax, [r15+rsi]
0x1800030ad  test    eax, eax
0x1800030af  jz      short loc_1800030FB
0x1800030b1  mov     edx, 0FFh
0x1800030b6  cmp     r9d, 4
0x1800030ba  jb      loc_180003196
0x1800030c0  cmp     esi, edx
0x1800030c2  mov     word ptr [r10], 200h
0x1800030c8  mov     eax, esi
0x1800030ca  cmovg   eax, edx
0x1800030cd  sub     esi, eax
0x1800030cf  mov     [r10+2], al
0x1800030d3  cmp     r15d, edx
0x1800030d6  mov     eax, r15d
0x1800030d9  cmovg   eax, edx
0x1800030dc  add     r9d, 0FFFFFFFCh
0x1800030e0  sub     r15d, eax
0x1800030e3  mov     [r10+3], al
0x1800030e7  add     r10, 4
0x1800030eb  mov     [rsp+88h+arg_20], r9d
0x1800030f3  lea     eax, [r15+rsi]
0x1800030f7  test    eax, eax
0x1800030f9  jnz     short loc_1800030B6
0x1800030fb  mov     eax, [rsp+88h+arg_48]
0x180003102  mov     r8, r10
0x180003105  mov     [rsp+88h+var_50], r13d
0x18000310a  mov     edx, ebx
0x18000310c  mov     [rsp+88h+var_58], eax
0x180003110  mov     rcx, rdi
0x180003113  mov     rax, [rsp+88h+arg_38]
0x18000311b  mov     [rsp+88h+var_60], rax
0x180003120  lea     rax, [rsp+88h+arg_20]
0x180003128  mov     [rsp+88h+var_68], rax
0x18000312d  call    EncodeFragment
0x180003132  mov     r10, rax
0x180003135  test    rax, rax
0x180003138  jz      short loc_180003196
0x18000313a  mov     ecx, ebx
0x18000313c  movsxd  rdx, ebx
0x18000313f  mov     r9d, [rbp+4]
0x180003143  add     rdi, rdx
0x180003146  movsxd  rax, ebx
0x180003149  add     r14d, ecx
0x18000314c  add     r12, rax
0x18000314f  cmp     r14d, r9d
0x180003152  jl      loc_180002FF5
0x180003158  mov     eax, [rsp+88h+arg_8]
0x18000315f  inc     r15d
0x180003162  sub     eax, r9d
0x180003165  sub     esi, r14d
0x180003168  movsxd  rcx, eax
0x18000316b  mov     eax, [rsp+88h+arg_28]
0x180003172  add     r12, rcx
0x180003175  inc     eax
0x180003177  add     rdi, rcx
0x18000317a  mov     [rsp+88h+arg_28], eax
0x180003181  cmp     eax, [rbp+8]
0x180003184  jl      loc_180002FE9
0x18000318a  mov     ecx, [rsp+88h+arg_20]
0x180003191  cmp     ecx, 2
0x180003194  jnb     short loc_18000319A
0x180003196  xor     eax, eax
0x180003198  jmp     short loc_1800031B9
0x18000319a  mov     word ptr [r10], 100h
0x1800031a0  mov     eax, 1
0x1800031a5  sub     r10d, [rsp+88h+var_48]
0x1800031aa  add     r10d, 2
0x1800031ae  mov     dword ptr [rbp+10h], 1
0x1800031b5  mov     [rbp+14h], r10d
0x1800031b9  mov     rbx, [rsp+88h+arg_10]
0x1800031c1  add     rsp, 50h
0x1800031c5  pop     r15
0x1800031c7  pop     r14
0x1800031c9  pop     r13
0x1800031cb  pop     r12
0x1800031cd  pop     rdi
0x1800031ce  pop     rsi
0x1800031cf  pop     rbp
0x1800031d0  retn
```
