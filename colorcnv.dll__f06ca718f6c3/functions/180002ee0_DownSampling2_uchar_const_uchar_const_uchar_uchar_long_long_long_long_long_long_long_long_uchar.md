# DownSampling2(uchar const *,uchar const *,uchar *,uchar *,long,long,long,long,long,long,long,long,uchar)

- ea: `0x180002ee0`
- end: `0x180003654`
- name: `?DownSampling2@@YAXPEBE0PEAE1JJJJJJJJE@Z`
- size: `1908`
- prototype: `void __fastcall(const unsigned __int8 *, const unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, int, int, int, int, int, int, int, int, char)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180002a10`
- `0x18001de30`
- `0x18001e110`
- `0x18001e5b0`
- `0x18001f120`
- `0x18001f390`

## callees

- `0x180002ee0`
- `0x18000ab30`
- `0x18000b468`

## pseudocode

```c
void __fastcall DownSampling2(
        const unsigned __int8 *a1,
        const unsigned __int8 *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12,
        char a13)
{
  int v13; // r8d
  int v14; // ecx
  int *v15; // r12
  char *v16; // r15
  int *v17; // r14
  int *v18; // rax
  char *v19; // rsi
  int *v20; // rdi
  char *v21; // rbx
  int v22; // r11d
  int v23; // eax
  __int64 v24; // r10
  int v25; // r13d
  int v26; // edx
  int v27; // r8d
  int v28; // r8d
  int v29; // r8d
  int v30; // r8d
  unsigned __int8 *v31; // rax
  char *v32; // r15
  unsigned __int8 *v33; // r13
  unsigned __int8 *v34; // rdi
  unsigned __int8 *v35; // rbx
  unsigned __int8 *v36; // r9
  unsigned __int8 *v37; // rdx
  unsigned __int8 *v38; // rsi
  int v39; // r14d
  unsigned __int8 *v40; // r15
  unsigned __int8 *v41; // r10
  int v42; // ecx
  int v43; // eax
  int v44; // r12d
  int v45; // r11d
  int v46; // ecx
  int v47; // eax
  int v48; // ecx
  int v49; // ecx
  int v50; // eax
  int v51; // [rsp+24h] [rbp-DCh]
  int v52; // [rsp+28h] [rbp-D8h]
  int v53; // [rsp+2Ch] [rbp-D4h]
  int v54; // [rsp+30h] [rbp-D0h]
  char v55; // [rsp+34h] [rbp-CCh]
  int v56; // [rsp+38h] [rbp-C8h]
  char *v57; // [rsp+40h] [rbp-C0h]
  int *v58; // [rsp+48h] [rbp-B8h]
  int *v59; // [rsp+50h] [rbp-B0h]
  char *v60; // [rsp+58h] [rbp-A8h]
  int *v61; // [rsp+60h] [rbp-A0h]
  char *v62; // [rsp+68h] [rbp-98h]
  int v63; // [rsp+70h] [rbp-90h]
  char *v64; // [rsp+78h] [rbp-88h]
  int *v65; // [rsp+80h] [rbp-80h]
  unsigned __int8 *v68; // [rsp+98h] [rbp-68h]
  unsigned __int8 *v69; // [rsp+A0h] [rbp-60h]
  unsigned __int8 *v72; // [rsp+B8h] [rbp-48h]
  unsigned __int8 *v73; // [rsp+C0h] [rbp-40h]
  unsigned __int8 *v74; // [rsp+C8h] [rbp-38h]
  unsigned __int8 *v75; // [rsp+D0h] [rbp-30h]
  unsigned __int8 *v76; // [rsp+D8h] [rbp-28h]
  __int64 v77; // [rsp+E0h] [rbp-20h]
  unsigned __int8 *v78; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int8 *v79; // [rsp+F8h] [rbp-8h]
  unsigned __int8 *v80; // [rsp+100h] [rbp+0h]
  unsigned __int8 *v81; // [rsp+108h] [rbp+8h]
  unsigned __int8 *v82; // [rsp+110h] [rbp+10h]
  unsigned __int8 *v83; // [rsp+118h] [rbp+18h]
  unsigned __int8 *v84; // [rsp+120h] [rbp+20h]
  unsigned __int8 *v85; // [rsp+128h] [rbp+28h]
  unsigned __int8 *v86; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int8 *v87; // [rsp+138h] [rbp+38h]
  unsigned __int8 *v88; // [rsp+140h] [rbp+40h]
  unsigned __int8 *v89; // [rsp+148h] [rbp+48h]
  unsigned __int8 *v90; // [rsp+150h] [rbp+50h]
  unsigned __int8 *v91; // [rsp+158h] [rbp+58h]
  unsigned __int8 *v92; // [rsp+160h] [rbp+60h]
  unsigned __int8 *v93; // [rsp+168h] [rbp+68h]

  memset_0(&v78, 0, 0x40u);
  memset_0(&v86, 0, 0x40u);
  v13 = 0;
  v51 = a9;
  if ( a13 )
  {
    if ( a13 == 1 )
    {
      v21 = byte_18002FFF0;
      v56 = 4;
      v55 = 11;
      v20 = &dword_18002FFF4;
      v19 = byte_18002FFF8;
      v17 = &dword_18002FFFC;
      v16 = byte_180030000;
      v15 = &dword_180030004;
      v52 = 2 * ((a12 + 1) / 2) - 1;
      v54 = 1024;
      v14 = 2 * a6;
      v64 = byte_180030008;
      v18 = &dword_18003000C;
      goto LABEL_4;
    }
    v14 = a6;
    if ( a13 == 2 )
    {
      v56 = 4;
      v53 = a9 + 1;
      v21 = byte_18002FFD0;
      v20 = &dword_18002FFD4;
      v55 = 11;
      v19 = byte_18002FFD8;
      v17 = &dword_18002FFDC;
      v16 = byte_18002FFE0;
      v52 = 2 * (a12 / 2);
      v15 = &dword_18002FFE4;
      v14 = 2 * a6;
      v54 = 1024;
      v64 = byte_18002FFE8;
      v18 = &dword_18002FFEC;
      goto LABEL_5;
    }
    a13 = 0;
  }
  else
  {
    v14 = a6;
  }
  v15 = &dword_18002F044;
  v52 = a12;
  v16 = byte_18002F040;
  v55 = 8;
  v64 = byte_18002F048;
  v17 = &dword_18002F03C;
  v18 = &dword_18002F04C;
  v54 = 128;
  v19 = byte_18002F038;
  v56 = 2;
  v20 = &dword_18002F034;
  v21 = byte_18002F030;
LABEL_4:
  v53 = a9;
LABEL_5:
  v57 = v21;
  v65 = v18;
  v61 = v15;
  v62 = v16;
  v59 = v17;
  v60 = v19;
  v58 = v20;
  if ( a9 >= a10 )
    return;
  v22 = a11;
  v77 = v14;
  v23 = a5;
  do
  {
    v24 = 0;
    v25 = 0;
    v26 = v51;
    do
    {
      switch ( a13 )
      {
        case 0:
          v27 = v26 - 3;
          if ( v26 - 3 < 0 )
          {
            v27 = 0;
            goto LABEL_12;
          }
LABEL_10:
          if ( v27 < v52 )
          {
LABEL_12:
            v13 = v23 * (v27 - v53);
            break;
          }
LABEL_11:
          v27 = v52 - 1;
          goto LABEL_12;
        case 1:
          v27 = v25 + v51 - 6;
          if ( v27 < 0 )
          {
            v27 = 0;
            goto LABEL_12;
          }
          goto LABEL_10;
        case 2:
          v27 = v25 + v51 - 5;
          if ( v27 < 1 )
          {
            v27 = 1;
            goto LABEL_12;
          }
          if ( v27 < v52 )
            goto LABEL_12;
          goto LABEL_11;
      }
      (&v78)[v24] = (unsigned __int8 *)&a1[v13];
      (&v86)[v24] = (unsigned __int8 *)&a2[v13];
      switch ( a13 )
      {
        case 0:
          v28 = v26 - 2;
          if ( v26 - 2 < 0 )
          {
            v28 = 0;
            goto LABEL_17;
          }
LABEL_15:
          if ( v28 < v52 )
          {
LABEL_17:
            v13 = a5 * (v28 - v53);
            break;
          }
LABEL_16:
          v28 = v52 - 1;
          goto LABEL_17;
        case 1:
          v28 = v25 + v51 - 4;
          if ( v28 < 0 )
          {
            v28 = 0;
            goto LABEL_17;
          }
          goto LABEL_15;
        case 2:
          v28 = v25 + v51 - 3;
          if ( v28 < 1 )
          {
            v28 = 1;
            goto LABEL_17;
          }
          if ( v28 < v52 )
            goto LABEL_17;
          goto LABEL_16;
      }
      (&v79)[v24] = (unsigned __int8 *)&a1[v13];
      (&v87)[v24] = (unsigned __int8 *)&a2[v13];
      switch ( a13 )
      {
        case 0:
          v29 = v26 - 1;
          if ( v26 - 1 < 0 )
          {
            v29 = 0;
            goto LABEL_22;
          }
LABEL_20:
          if ( v29 < v52 )
          {
LABEL_22:
            v13 = a5 * (v29 - v53);
            break;
          }
LABEL_21:
          v29 = v52 - 1;
          goto LABEL_22;
        case 1:
          v29 = v25 + v51 - 2;
          if ( v29 < 0 )
          {
            v29 = 0;
            goto LABEL_22;
          }
          goto LABEL_20;
        case 2:
          v29 = v25 + v51 - 1;
          if ( v29 < 1 )
          {
            v29 = 1;
            goto LABEL_22;
          }
          if ( v29 < v52 )
            goto LABEL_22;
          goto LABEL_21;
      }
      (&v80)[v24] = (unsigned __int8 *)&a1[v13];
      (&v88)[v24] = (unsigned __int8 *)&a2[v13];
      switch ( a13 )
      {
        case 0:
          if ( v26 < 0 )
          {
            v30 = 0;
          }
          else
          {
            if ( v26 >= v52 )
              goto LABEL_26;
            v30 = v26;
          }
          goto LABEL_27;
        case 1:
          v30 = v51 + v25;
          if ( v51 + v25 >= 0 )
          {
            if ( v30 >= v52 )
              goto LABEL_26;
          }
          else
          {
            v30 = 0;
          }
          goto LABEL_27;
        case 2:
          v30 = v25 + v51 + 1;
          if ( v30 < 1 )
          {
            v30 = 1;
            goto LABEL_27;
          }
          if ( v30 < v52 )
            goto LABEL_27;
LABEL_26:
          v30 = v52 - 1;
LABEL_27:
          v13 = a5 * (v30 - v53);
          break;
      }
      v26 += 4;
      v25 += 8;
      (&v81)[v24] = (unsigned __int8 *)&a1[v13];
      (&v89)[v24] = (unsigned __int8 *)&a2[v13];
      v24 = (unsigned int)(v24 + 4);
      v23 = a5;
    }
    while ( (int)v24 < 8 );
    v31 = a3;
    v32 = v62;
    v68 = a3;
    v69 = a4;
    v63 = 0;
    if ( v22 > 0 )
    {
      do
      {
        _mm_lfence();
        v33 = v86;
        v34 = v87;
        v35 = v89;
        v36 = v83;
        v37 = v90;
        v38 = v82;
        v39 = *(_DWORD *)v32;
        v40 = v84;
        v41 = v85;
        v74 = v78;
        v78 += 4;
        v86 += 4;
        v72 = v79;
        v79 += 4;
        v87 += 4;
        v75 = v80;
        v80 += 4;
        v42 = *v88;
        v88 += 4;
        v73 = v81;
        v81 += 4;
        v89 += 4;
        v82 += 4;
        v90 += 4;
        v83 += 4;
        v76 = v36;
        v43 = *v91;
        v91 += 4;
        v44 = *(_DWORD *)v64;
        v84 += 4;
        LODWORD(v36) = *v92;
        v92 += 4;
        v45 = *v65;
        v46 = *v61 * v43 + *(_DWORD *)v60 * v42;
        v47 = *v34;
        LODWORD(v34) = *v58;
        v48 = *(_DWORD *)v57 * *v33 + *v59 * *v35 + *v65 * *v93 + v39 * *v37 + *v58 * v47 + v46;
        v85 += 4;
        LODWORD(v37) = *v76;
        v93 += 4;
        LODWORD(v36) = v48 + v44 * (_DWORD)v36;
        v49 = *(_DWORD *)v57 * *v74 + *v59 * *v73 + v45 * *v41 + v39 * *v38 + (_DWORD)v34 * *v72;
        v50 = *v40;
        v32 = v62;
        v22 = a11;
        *v68++ = (v44 * v50 + v49 + v54 + *(_DWORD *)v60 * *v75 + *v61 * (int)v37) >> v55;
        *v69++ = ((int)v36 + v54) >> v55;
        v63 += 2;
      }
      while ( v63 < a11 );
      v31 = a3;
    }
    a4 += v77;
    a3 = &v31[v77];
    v23 = a5;
    v51 += v56;
  }
  while ( v51 < a10 );
}

```

## disassembly

```asm
0x180002ee0  push    rbp
0x180002ee2  push    rbx
0x180002ee3  push    rsi
0x180002ee4  push    rdi
0x180002ee5  push    r12
0x180002ee7  push    r14
0x180002ee9  push    r15
0x180002eeb  lea     rbp, [rsp-80h]
0x180002ef0  sub     rsp, 180h
0x180002ef7  mov     rax, cs:__security_cookie
0x180002efe  xor     rax, rsp
0x180002f01  mov     [rbp+0B0h+var_40], rax
0x180002f05  mov     [rbp+0B0h+var_128], r8
0x180002f09  mov     r8d, 40h ; '@'; Size
0x180002f0f  mov     [rbp+0B0h+var_108], rdx
0x180002f13  xor     edx, edx; Val
0x180002f15  mov     [rbp+0B0h+var_100], rcx
0x180002f19  lea     rcx, [rbp+0B0h+var_C0]; void *
0x180002f1d  mov     [rbp+0B0h+var_120], r9
0x180002f21  call    memset_0
0x180002f26  xor     edx, edx; Val
0x180002f28  lea     rcx, [rbp+0B0h+var_80]; void *
0x180002f2c  mov     r8d, 40h ; '@'; Size
0x180002f32  call    memset_0
0x180002f37  movzx   eax, [rbp+0B0h+arg_60]
0x180002f3e  xor     r8d, r8d
0x180002f41  mov     r9d, [rbp+0B0h+arg_40]
0x180002f48  mov     ecx, eax
0x180002f4a  mov     [rsp+1B0h+var_18C], r9d
0x180002f4f  test    al, al
0x180002f51  jnz     loc_18000340B
0x180002f57  mov     ecx, [rbp+0B0h+arg_28]
0x180002f5d  mov     eax, [rbp+0B0h+arg_58]
0x180002f63  lea     r12, dword_18002F044
0x180002f6a  mov     [rsp+1B0h+var_188], eax
0x180002f6e  lea     r15, byte_18002F040
0x180002f75  lea     rax, byte_18002F048
0x180002f7c  mov     [rsp+1B0h+var_17C], 8
0x180002f84  mov     [rsp+1B0h+var_138], rax
0x180002f89  lea     r14, dword_18002F03C
0x180002f90  lea     rax, dword_18002F04C
0x180002f97  mov     [rsp+1B0h+var_180], 80h
0x180002f9f  lea     rsi, byte_18002F038
0x180002fa6  mov     [rsp+1B0h+var_178], 2
0x180002fae  lea     rdi, dword_18002F034
0x180002fb5  lea     rbx, byte_18002F030
0x180002fbc  mov     [rsp+1B0h+var_184], r9d
0x180002fc1  mov     [rsp+1B0h+var_170], rbx
0x180002fc6  mov     [rbp+0B0h+var_130], rax
0x180002fca  mov     [rsp+1B0h+var_150], r12
0x180002fcf  mov     [rsp+1B0h+var_148], r15
0x180002fd4  mov     [rsp+1B0h+var_160], r14
0x180002fd9  mov     [rsp+1B0h+var_158], rsi
0x180002fde  mov     [rsp+1B0h+var_168], rdi
0x180002fe3  cmp     r9d, [rbp+0B0h+arg_48]
0x180002fea  jge     loc_1800033C5
0x180002ff0  mov     r11d, [rbp+0B0h+arg_50]
0x180002ff7  movsxd  rax, ecx
0x180002ffa  mov     [rbp+0B0h+var_D0], rax
0x180002ffe  mov     eax, [rbp+0B0h+arg_20]
0x180003004  mov     [rsp+1B0h+arg_0], r13
0x18000300c  nop     dword ptr [rax+00h]
0x180003010  mov     edi, [rsp+1B0h+var_18C]
0x180003014  xor     r10d, r10d
0x180003017  mov     r12d, [rsp+1B0h+var_188]
0x18000301c  xor     r13d, r13d
0x18000301f  movzx   r15d, [rbp+0B0h+arg_60]
0x180003027  mov     edx, edi
0x180003029  mov     r14d, [rsp+1B0h+var_184]
0x18000302e  mov     rsi, [rbp+0B0h+var_108]
0x180003032  mov     rbx, [rbp+0B0h+var_100]
0x180003036  test    r15b, r15b
0x180003039  jnz     loc_18000351E
0x18000303f  lea     r8d, [rdx-3]
0x180003043  test    r8d, r8d
0x180003046  js      loc_1800033E3
0x18000304c  cmp     r8d, r12d
0x18000304f  jl      short loc_180003056
0x180003051  lea     r8d, [r12-1]
0x180003056  sub     r8d, r14d
0x180003059  imul    r8d, eax
0x18000305d  movsxd  rcx, r8d
0x180003060  lea     rax, [rcx+rbx]
0x180003064  mov     [rbp+r10*8+0B0h+var_C0], rax
0x180003069  lea     rax, [rcx+rsi]
0x18000306d  mov     [rbp+r10*8+0B0h+var_80], rax
0x180003072  test    r15b, r15b
0x180003075  jnz     loc_180003569
0x18000307b  lea     r8d, [rdx-2]
0x18000307f  test    r8d, r8d
0x180003082  js      loc_1800033EB
0x180003088  cmp     r8d, r12d
0x18000308b  jl      short loc_180003092
0x18000308d  lea     r8d, [r12-1]
0x180003092  sub     r8d, r14d
0x180003095  imul    r8d, [rbp+0B0h+arg_20]
0x18000309d  movsxd  rcx, r8d
0x1800030a0  lea     rax, [rcx+rbx]
0x1800030a4  mov     [rbp+r10*8+0B0h+var_B8], rax
0x1800030a9  lea     rax, [rcx+rsi]
0x1800030ad  mov     [rbp+r10*8+0B0h+var_78], rax
0x1800030b2  test    r15b, r15b
0x1800030b5  jnz     loc_1800035B4
0x1800030bb  lea     r8d, [rdx-1]
0x1800030bf  test    r8d, r8d
0x1800030c2  js      loc_1800033F3
0x1800030c8  cmp     r8d, r12d
0x1800030cb  jl      short loc_1800030D2
0x1800030cd  lea     r8d, [r12-1]
0x1800030d2  sub     r8d, r14d
0x1800030d5  imul    r8d, [rbp+0B0h+arg_20]
0x1800030dd  movsxd  rcx, r8d
0x1800030e0  lea     rax, [rcx+rbx]
0x1800030e4  mov     [rbp+r10*8+0B0h+var_B0], rax
0x1800030e9  lea     rax, [rcx+rsi]
0x1800030ed  mov     [rbp+r10*8+0B0h+var_70], rax
0x1800030f2  test    r15b, r15b
0x1800030f5  jnz     loc_1800035FF
0x1800030fb  test    edx, edx
0x1800030fd  js      loc_1800033FB
0x180003103  cmp     edx, r12d
0x180003106  jl      loc_180003403
0x18000310c  lea     r8d, [r12-1]
0x180003111  sub     r8d, r14d
0x180003114  imul    r8d, [rbp+0B0h+arg_20]
0x18000311c  movsxd  rcx, r8d
0x18000311f  add     edx, 4
0x180003122  add     r13d, 8
0x180003126  lea     rax, [rcx+rbx]
0x18000312a  mov     [rbp+r10*8+0B0h+var_A8], rax
0x18000312f  lea     rax, [rcx+rsi]
0x180003133  mov     [rbp+r10*8+0B0h+var_68], rax
0x180003138  add     r10d, 4
0x18000313c  mov     eax, [rbp+0B0h+arg_20]
0x180003142  cmp     r10d, 8
0x180003146  jl      loc_180003036
0x18000314c  mov     rax, [rbp+0B0h+var_128]
0x180003150  mov     rcx, [rbp+0B0h+var_120]
0x180003154  mov     r15, [rsp+1B0h+var_148]
0x180003159  mov     [rbp+0B0h+var_118], rax
0x18000315d  mov     [rbp+0B0h+var_110], rcx
0x180003161  mov     [rsp+1B0h+var_190], r8d
0x180003166  mov     [rsp+1B0h+var_140], 0
0x18000316e  test    r11d, r11d
0x180003171  jle     loc_18000338C
0x180003177  nop     word ptr [rax+rax+00000000h]
0x180003180  lfence
0x180003183  mov     r13, [rbp+0B0h+var_80]
0x180003187  mov     rdi, [rbp+0B0h+var_78]
0x18000318b  mov     rbx, [rbp+0B0h+var_68]
0x18000318f  mov     rax, [rbp+0B0h+var_C0]
0x180003193  mov     r9, [rbp+0B0h+var_98]
0x180003197  mov     rcx, [rbp+0B0h+var_70]
0x18000319b  mov     rdx, [rbp+0B0h+var_60]
0x18000319f  mov     rsi, [rbp+0B0h+var_A0]
0x1800031a3  mov     r14d, [r15]
0x1800031a6  lea     r8, [r9+4]
0x1800031aa  mov     r15, [rbp+0B0h+var_90]
0x1800031ae  mov     r10, [rbp+0B0h+var_88]
0x1800031b2  mov     [rbp+0B0h+var_E8], rax
0x1800031b6  add     rax, 4
0x1800031ba  mov     [rbp+0B0h+var_C0], rax
0x1800031be  lea     rax, [r13+4]
0x1800031c2  mov     [rbp+0B0h+var_80], rax
0x1800031c6  mov     rax, [rbp+0B0h+var_B8]
0x1800031ca  mov     [rbp+0B0h+var_F8], rax
0x1800031ce  add     rax, 4
0x1800031d2  mov     [rbp+0B0h+var_B8], rax
0x1800031d6  lea     rax, [rdi+4]
0x1800031da  mov     [rbp+0B0h+var_78], rax
0x1800031de  mov     rax, [rbp+0B0h+var_B0]
0x1800031e2  mov     [rbp+0B0h+var_E0], rax
0x1800031e6  add     rax, 4
0x1800031ea  mov     [rbp+0B0h+var_B0], rax
0x1800031ee  lea     rax, [rcx+4]
0x1800031f2  movzx   ecx, byte ptr [rcx]
0x1800031f5  mov     [rbp+0B0h+var_70], rax
0x1800031f9  mov     rax, [rbp+0B0h+var_A8]
0x1800031fd  mov     [rbp+0B0h+var_F0], rax
0x180003201  add     rax, 4
0x180003205  mov     [rbp+0B0h+var_A8], rax
0x180003209  lea     rax, [rbx+4]
0x18000320d  mov     [rbp+0B0h+var_68], rax
0x180003211  lea     rax, [rsi+4]
0x180003215  mov     [rbp+0B0h+var_A0], rax
0x180003219  lea     rax, [rdx+4]
0x18000321d  mov     [rbp+0B0h+var_60], rax
0x180003221  mov     rax, [rbp+0B0h+var_58]
0x180003225  mov     [rbp+0B0h+var_98], r8
0x180003229  mov     [rbp+0B0h+var_D8], r9
0x18000322d  mov     r9, [rbp+0B0h+var_50]
0x180003231  lea     r8, [rax+4]
0x180003235  movzx   eax, byte ptr [rax]
0x180003238  mov     [rbp+0B0h+var_58], r8
0x18000323c  mov     r8, [rsp+1B0h+var_138]
0x180003241  mov     r12d, [r8]
0x180003244  lea     r8, [r15+4]
0x180003248  mov     [rbp+0B0h+var_90], r8
0x18000324c  lea     r8, [r9+4]
0x180003250  movzx   r9d, byte ptr [r9]
0x180003254  mov     [rbp+0B0h+var_50], r8
0x180003258  mov     r8, [rbp+0B0h+var_130]
0x18000325c  mov     r11d, [r8]
0x18000325f  mov     r8, [rsp+1B0h+var_158]
0x180003264  imul    ecx, [r8]
0x180003268  mov     r8, [rsp+1B0h+var_150]
0x18000326d  imul    eax, [r8]
0x180003271  mov     r8, [rsp+1B0h+var_168]
0x180003276  add     ecx, eax
0x180003278  movzx   eax, byte ptr [rdi]
0x18000327b  mov     edi, [r8]
0x18000327e  mov     r8, [rbp+0B0h+var_48]
0x180003282  imul    eax, edi
0x180003285  add     ecx, eax
0x180003287  movzx   eax, byte ptr [rdx]
0x18000328a  imul    eax, r14d
0x18000328e  add     ecx, eax
0x180003290  movzx   eax, byte ptr [r8]
0x180003294  imul    eax, r11d
0x180003298  add     ecx, eax
0x18000329a  movzx   eax, byte ptr [rbx]
0x18000329d  mov     rbx, [rsp+1B0h+var_160]
0x1800032a2  imul    eax, [rbx]
0x1800032a5  add     ecx, eax
0x1800032a7  movzx   eax, byte ptr [r13+0]
0x1800032ac  mov     r13, [rsp+1B0h+var_170]
0x1800032b1  imul    eax, [r13+0]
0x1800032b6  add     ecx, eax
0x1800032b8  mov     rdx, [rbp+0B0h+var_D8]
0x1800032bc  lea     rax, [r10+4]
0x1800032c0  mov     [rbp+0B0h+var_88], rax
0x1800032c4  add     r8, 4
0x1800032c8  mov     rax, [rbp+0B0h+var_F8]
0x1800032cc  imul    r9d, r12d
0x1800032d0  movzx   edx, byte ptr [rdx]
0x1800032d3  mov     [rbp+0B0h+var_48], r8
0x1800032d7  add     r9d, ecx
0x1800032da  movzx   ecx, byte ptr [rax]
0x1800032dd  movzx   eax, byte ptr [rsi]
0x1800032e0  mov     rsi, [rsp+1B0h+var_158]
0x1800032e5  imul    eax, r14d
0x1800032e9  imul    ecx, edi
0x1800032ec  add     ecx, eax
0x1800032ee  movzx   eax, byte ptr [r10]
0x1800032f2  mov     r10, [rbp+0B0h+var_118]
0x1800032f6  imul    eax, r11d
0x1800032fa  mov     r11d, [rsp+1B0h+var_180]
0x1800032ff  add     ecx, eax
0x180003301  mov     rax, [rbp+0B0h+var_F0]
0x180003305  movzx   eax, byte ptr [rax]
0x180003308  imul    eax, [rbx]
0x18000330b  add     ecx, eax
0x18000330d  mov     rax, [rbp+0B0h+var_E8]
0x180003311  movzx   eax, byte ptr [rax]
0x180003314  imul    eax, [r13+0]
0x180003319  add     ecx, eax
0x18000331b  movzx   eax, byte ptr [r15]
0x18000331f  mov     r15, [rsp+1B0h+var_148]
0x180003324  imul    eax, r12d
0x180003328  mov     r12, [rsp+1B0h+var_150]
0x18000332d  imul    edx, [r12]
0x180003332  add     ecx, eax
0x180003334  mov     rax, [rbp+0B0h+var_E0]
0x180003338  movzx   eax, byte ptr [rax]
0x18000333b  imul    eax, [rsi]
0x18000333e  add     eax, r11d
0x180003341  add     eax, ecx
0x180003343  mov     ecx, [rsp+1B0h+var_17C]
0x180003347  add     edx, eax
0x180003349  lea     eax, [r9+r11]
0x18000334d  mov     r11d, [rbp+0B0h+arg_50]
0x180003354  sar     eax, cl
0x180003356  sar     edx, cl
0x180003358  mov     rcx, [rbp+0B0h+var_110]
0x18000335c  mov     [r10], dl
0x18000335f  inc     r10
0x180003362  mov     [rbp+0B0h+var_118], r10
0x180003366  mov     [rcx], al
0x180003368  inc     rcx
0x18000336b  mov     eax, [rsp+1B0h+var_140]
0x18000336f  add     eax, 2
0x180003372  mov     [rbp+0B0h+var_110], rcx
0x180003376  mov     [rsp+1B0h+var_140], eax
0x18000337a  cmp     eax, r11d
0x18000337d  jl      loc_180003180
0x180003383  mov     r8d, [rsp+1B0h+var_190]
0x180003388  mov     rax, [rbp+0B0h+var_128]
0x18000338c  mov     rcx, [rbp+0B0h+var_D0]
0x180003390  mov     r9d, [rsp+1B0h+var_18C]
0x180003395  add     rax, rcx
0x180003398  add     r9d, [rsp+1B0h+var_178]
0x18000339d  add     [rbp+0B0h+var_120], rcx
0x1800033a1  mov     [rbp+0B0h+var_128], rax
0x1800033a5  mov     eax, [rbp+0B0h+arg_20]
0x1800033ab  mov     [rsp+1B0h+var_18C], r9d
0x1800033b0  cmp     r9d, [rbp+0B0h+arg_48]
0x1800033b7  jl      loc_180003010
0x1800033bd  mov     r13, [rsp+1B0h+arg_0]
0x1800033c5  mov     rcx, [rbp+0B0h+var_40]
0x1800033c9  xor     rcx, rsp; StackCookie
  ... truncated ...
```
