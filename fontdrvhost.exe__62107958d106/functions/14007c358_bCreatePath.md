# bCreatePath

- ea: `0x14007c358`
- end: `0x14007c7a5`
- name: `bCreatePath`
- size: `1101`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400476e4`

## callees

- `0x140051d78`
- `0x140051e28`
- `0x140075de0`
- `0x14007c358`

## pseudocode

```c
__int64 __fastcall bCreatePath(char *a1, char *a2, __int64 a3, PATHOBJ *a4, int a5)
{
  PATHOBJ *v5; // rdi
  char *v7; // r11
  int v9; // eax
  __int64 v10; // r15
  __int64 v11; // rdx
  float v12; // xmm6_4
  int v13; // r9d
  float v14; // xmm8_4
  float v15; // xmm9_4
  float v16; // xmm7_4
  int v17; // r10d
  __int64 v18; // rbx
  int v19; // r8d
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // r14d
  int v28; // esi
  int v29; // eax
  char *v30; // rdx
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // rdx
  int v34; // r8d
  float v35; // xmm0_4
  float v36; // xmm0_4
  int v37; // r9d
  float v38; // xmm2_4
  float v39; // xmm1_4
  int v40; // r11d
  int v41; // r10d
  int v42; // edi
  __int64 v43; // rcx
  int v44; // edi
  char *v45; // rdx
  __int64 v46; // rcx
  int v47; // eax
  unsigned int v48; // [rsp+28h] [rbp-B1h]
  int v49; // [rsp+2Ch] [rbp-ADh]
  int v50; // [rsp+30h] [rbp-A9h]
  int v51; // [rsp+38h] [rbp-A1h]
  int v52; // [rsp+3Ch] [rbp-9Dh]
  int v54; // [rsp+48h] [rbp-91h]
  char *v55; // [rsp+50h] [rbp-89h]
  __int64 v57; // [rsp+68h] [rbp-71h]
  int v58; // [rsp+70h] [rbp-69h]
  int v59[9]; // [rsp+74h] [rbp-65h]
  POINTFIX ptfx; // [rsp+98h] [rbp-41h]
  POINTFIX pptfx; // [rsp+A0h] [rbp-39h] BYREF

  v5 = a4;
  v55 = a1;
  v7 = a2;
  if ( a1 == a2 )
    return 1;
  v9 = *(_DWORD *)(a3 + 120);
  LODWORD(v10) = 0;
  v11 = *(_QWORD *)(a3 + 8);
  v12 = *(float *)(a3 + 16);
  v13 = v9 & 2;
  v14 = *(float *)(a3 + 20);
  v15 = *(float *)(a3 + 24);
  v16 = *(float *)(a3 + 28);
  v17 = *(__int16 *)(v11 + 62);
  v18 = *(_QWORD *)(a3 + 80);
  v54 = v9 & 1;
  v19 = v9 & 4;
  v48 = 1;
  v49 = v17;
  v52 = v13;
  v51 = v19;
  v20 = (v9 & 0xFF0) - 16;
  if ( !v20 )
  {
    v28 = a5 - 16;
    goto LABEL_21;
  }
  v21 = v20 - 16;
  if ( !v21 )
  {
    v28 = a5 - 16;
    v27 = *(_DWORD *)(a3 + 32) - 16;
    goto LABEL_22;
  }
  v22 = v21 - 32;
  if ( !v22 )
  {
    v28 = -16;
    v27 = *(_DWORD *)(a3 + 32) - 16;
    goto LABEL_22;
  }
  v23 = v22 - 64;
  if ( !v23 )
  {
    v28 = -16;
LABEL_21:
    v27 = -16 - *(_DWORD *)(a3 + 36);
    goto LABEL_22;
  }
  v24 = v23 - 128;
  if ( !v24 )
  {
    v28 = -16 - *(_DWORD *)(a3 + 36);
    goto LABEL_16;
  }
  v25 = v24 - 256;
  if ( !v25 )
  {
    v27 = -16;
    v28 = -16 - *(_DWORD *)(a3 + 36);
    goto LABEL_22;
  }
  v26 = v25 - 512;
  if ( !v26 )
  {
    v28 = *(_DWORD *)(a3 + 32) - 16;
LABEL_16:
    v27 = a5 - 16;
    goto LABEL_22;
  }
  if ( v26 == 1024 )
  {
    v27 = -16;
    v28 = *(_DWORD *)(a3 + 32) - 16;
  }
  else
  {
    v27 = 0;
    v28 = 0;
  }
LABEL_22:
  v29 = -*(__int16 *)(v11 + 60);
  v58 = 0;
LABEL_23:
  v59[0] = v29;
  while ( a1 <= v7 )
  {
    if ( a1 != v7 && *a1 != (char)0x80 )
    {
      if ( (unsigned int)v10 < 5 )
      {
        v30 = a1 + 1;
        if ( (_DWORD)v10 )
        {
          v59[2 * (unsigned int)v10 - 1] = *a1 + v59[2 * (unsigned int)(v10 - 1) - 1];
          if ( v30 == v7 )
            return 0;
          v31 = v59[2 * (unsigned int)(v10 - 1)] + *v30;
          v17 = v49;
        }
        else
        {
          v58 = *a1;
          if ( v30 == v7 )
            return 0;
          v31 = *v30;
        }
        v59[2 * (unsigned int)v10] = v31;
        LODWORD(v10) = v10 + 1;
        goto LABEL_63;
      }
LABEL_35:
      v10 = (unsigned int)(v10 - 1);
      v57 = (unsigned int)v10;
      v50 = v59[2 * v10 - 1];
      if ( v13 )
      {
        v32 = 0;
        do
        {
          v59[2 * v32 - 1] += (v17 - v59[2 * v32]) >> 1;
          v32 = (unsigned int)(v32 + 1);
        }
        while ( (unsigned int)v32 <= (unsigned int)v10 );
      }
      v33 = 0;
      if ( v19 )
      {
        do
        {
          v34 = (int)(float)((float)v59[2 * v33 - 1] * v12);
          v35 = (float)v59[2 * v33];
          *(&ptfx.x + 2 * v33) = v34;
          v36 = v35 * v16;
          *(&ptfx.y + 2 * v33) = (int)v36;
          if ( (int)v36 > v27 )
            *(&ptfx.y + 2 * v33) = v27;
          if ( v34 > v28 )
            *(&ptfx.x + 2 * v33) = v28;
          v33 = (unsigned int)(v33 + 1);
        }
        while ( (unsigned int)v33 <= (unsigned int)v10 );
      }
      else
      {
        v37 = *(_DWORD *)(a3 + 120) & 0xFF0;
        do
        {
          v38 = (float)v59[2 * v33];
          v39 = (float)v59[2 * v33 - 1];
          v40 = (int)(float)(v39 * v12) + (int)(float)(v38 * v15);
          *(&ptfx.x + 2 * v33) = v40;
          v41 = (int)(float)(v39 * v14) + (int)(float)(v38 * v16);
          *(&ptfx.y + 2 * v33) = v41;
          if ( v37 )
          {
            if ( v41 > v27 )
              *(&ptfx.y + 2 * v33) = v27;
            if ( v40 > v28 )
              *(&ptfx.x + 2 * v33) = v28;
          }
          v33 = (unsigned int)(v33 + 1);
        }
        while ( (unsigned int)v33 <= (unsigned int)v10 );
      }
      v42 = v48 & PATHOBJ_bMoveTo(v5, ptfx);
      v48 = v42 & PATHOBJ_bPolyLineTo(a4, &pptfx, v10);
      if ( v54 )
      {
        v43 = 0;
        do
        {
          *(&ptfx.x + 2 * v43) += v18;
          *(&ptfx.y + 2 * v43) += HIDWORD(v18);
          v43 = (unsigned int)(v43 + 1);
        }
        while ( (unsigned int)v43 <= (unsigned int)v10 );
        v44 = v48 & PATHOBJ_bMoveTo(a4, ptfx);
        v48 = v44 & PATHOBJ_bPolyLineTo(a4, &pptfx, v10);
      }
      a1 = v55;
      v7 = a2;
      if ( v55 != a2 && *v55 != (char)0x80 )
      {
        LODWORD(v10) = 1;
        v5 = a4;
        v19 = v51;
        v13 = v52;
        v17 = v49;
        v58 = v50;
        v29 = v59[2 * v57];
        goto LABEL_23;
      }
      v5 = a4;
      v17 = v49;
      v59[2 * v10 - 1] = v50;
      goto LABEL_60;
    }
    if ( (unsigned int)v10 > 1 )
      goto LABEL_35;
LABEL_60:
    v45 = a1 + 1;
    if ( a1 + 1 == v7 )
      return 0;
    v46 = (unsigned int)v10;
    v47 = v59[2 * (unsigned int)v10 - 1] + *v45;
    v30 = v45 + 1;
    v58 = v47;
    if ( v30 == v7 )
      return 0;
    LODWORD(v10) = 1;
    v59[0] = v59[2 * v46] + *v30;
LABEL_63:
    v19 = v51;
    a1 = v30 + 1;
    v13 = v52;
    v55 = v30 + 1;
  }
  return v48;
}

```

## disassembly

```asm
0x14007c358  mov     rax, rsp
0x14007c35b  mov     [rax+8], rbx
0x14007c35f  mov     [rax+10h], rsi
0x14007c363  push    rbp
0x14007c364  push    rdi
0x14007c365  push    r13
0x14007c367  push    r14
0x14007c369  push    r15
0x14007c36b  lea     rbp, [rax-57h]
0x14007c36f  sub     rsp, 100h
0x14007c376  movaps  xmmword ptr [rax-38h], xmm6
0x14007c37a  movaps  xmmword ptr [rax-48h], xmm7
0x14007c37e  movaps  xmmword ptr [rax-58h], xmm8
0x14007c383  movaps  xmmword ptr [rax-68h], xmm9
0x14007c388  mov     rax, cs:__security_cookie
0x14007c38f  xor     rax, rsp
0x14007c392  mov     [rbp+4Fh+var_68], rax
0x14007c396  mov     [rsp+120h+ppo], r9
0x14007c39b  mov     rdi, r9
0x14007c39e  mov     [rbp+4Fh+var_C8], rdx
0x14007c3a2  mov     r13, r8
0x14007c3a5  mov     [rsp+120h+var_D8], rcx
0x14007c3aa  mov     r11, rdx
0x14007c3ad  mov     qword ptr [rsp+120h+var_F8], 0
0x14007c3b6  cmp     rcx, rdx
0x14007c3b9  jnz     short loc_14007C3C5
0x14007c3bb  mov     eax, 1
0x14007c3c0  jmp     loc_14007C769
0x14007c3c5  mov     eax, [r8+78h]
0x14007c3c9  xor     r15d, r15d
0x14007c3cc  mov     rdx, [r8+8]
0x14007c3d0  mov     r9d, eax
0x14007c3d3  movss   xmm6, dword ptr [r8+10h]
0x14007c3d9  and     r9d, 2
0x14007c3dd  movss   xmm8, dword ptr [r8+14h]
0x14007c3e3  movss   xmm9, dword ptr [r8+18h]
0x14007c3e9  movss   xmm7, dword ptr [r8+1Ch]
0x14007c3ef  mov     r8d, eax
0x14007c3f2  movsx   r10d, word ptr [rdx+3Eh]
0x14007c3f7  and     r8d, 1
0x14007c3fb  mov     rbx, [r13+50h]
0x14007c3ff  mov     dword ptr [rsp+120h+var_E0], r8d
0x14007c404  mov     r8d, eax
0x14007c407  and     r8d, 4
0x14007c40b  mov     dword ptr [rsp+120h+var_100], 1
0x14007c413  and     eax, 0FF0h
0x14007c418  mov     dword ptr [rsp+120h+var_100+4], r10d
0x14007c41d  mov     dword ptr [rsp+120h+var_F0+4], r9d
0x14007c422  mov     dword ptr [rsp+120h+var_F0], r8d
0x14007c427  mov     [rsp+50h], rbx
0x14007c42c  sub     eax, 10h
0x14007c42f  jz      loc_14007C4CF
0x14007c435  sub     eax, 10h
0x14007c438  jz      loc_14007C4BF
0x14007c43e  sub     eax, 20h ; ' '
0x14007c441  jz      short loc_14007C4B0
0x14007c443  sub     eax, 40h ; '@'
0x14007c446  jz      short loc_14007C4A9
0x14007c448  sub     eax, 80h
0x14007c44d  jz      short loc_14007C496
0x14007c44f  sub     eax, 100h
0x14007c454  jz      short loc_14007C485
0x14007c456  sub     eax, 200h
0x14007c45b  jz      short loc_14007C47C
0x14007c45d  cmp     eax, 400h
0x14007c462  jnz     short loc_14007C471
0x14007c464  mov     esi, [r13+20h]
0x14007c468  lea     r14d, [r15-10h]
0x14007c46c  sub     esi, 10h
0x14007c46f  jmp     short loc_14007C4DF
0x14007c471  mov     r14d, [rsp+120h+var_F4]
0x14007c476  mov     esi, [rsp+120h+var_F8]
0x14007c47a  jmp     short loc_14007C4DF
0x14007c47c  mov     esi, [r13+20h]
0x14007c480  sub     esi, 10h
0x14007c483  jmp     short loc_14007C49F
0x14007c485  mov     esi, 0FFFFFFF0h
0x14007c48a  mov     r14d, 0FFFFFFF0h
0x14007c490  sub     esi, [r13+24h]
0x14007c494  jmp     short loc_14007C4DF
0x14007c496  mov     esi, 0FFFFFFF0h
0x14007c49b  sub     esi, [r13+24h]
0x14007c49f  mov     r14d, [rbp+4Fh+arg_20]
0x14007c4a3  add     r14d, 0FFFFFFF0h
0x14007c4a7  jmp     short loc_14007C4DF
0x14007c4a9  mov     esi, 0FFFFFFF0h
0x14007c4ae  jmp     short loc_14007C4D5
0x14007c4b0  mov     r14d, [r13+20h]
0x14007c4b4  mov     esi, 0FFFFFFF0h
0x14007c4b9  sub     r14d, 10h
0x14007c4bd  jmp     short loc_14007C4DF
0x14007c4bf  mov     esi, [rbp+4Fh+arg_20]
0x14007c4c2  mov     r14d, [r13+20h]
0x14007c4c6  add     esi, 0FFFFFFF0h
0x14007c4c9  sub     r14d, 10h
0x14007c4cd  jmp     short loc_14007C4DF
0x14007c4cf  mov     esi, [rbp+4Fh+arg_20]
0x14007c4d2  add     esi, 0FFFFFFF0h
0x14007c4d5  mov     r14d, 0FFFFFFF0h
0x14007c4db  sub     r14d, [r13+24h]
0x14007c4df  movsx   eax, word ptr [rdx+3Ch]
0x14007c4e3  neg     eax
0x14007c4e5  mov     [rbp+4Fh+var_B8], r15d
0x14007c4e9  mov     [rbp+4Fh+var_B4], eax
0x14007c4ec  cmp     rcx, r11
0x14007c4ef  ja      loc_14007C765
0x14007c4f5  jz      short loc_14007C55B
0x14007c4f7  cmp     byte ptr [rcx], 80h
0x14007c4fa  jz      short loc_14007C55B
0x14007c4fc  cmp     r15d, 5
0x14007c500  jnb     short loc_14007C565
0x14007c502  movsx   r9d, byte ptr [rcx]
0x14007c506  lea     rdx, [rcx+1]
0x14007c50a  mov     r8d, r15d
0x14007c50d  test    r15d, r15d
0x14007c510  jz      short loc_14007C53D
0x14007c512  lea     eax, [r15-1]
0x14007c516  mov     ecx, [rbp+rax*8+4Fh+var_B8]
0x14007c51a  add     ecx, r9d
0x14007c51d  mov     r10d, eax
0x14007c520  mov     [rbp+r8*8+4Fh+var_B8], ecx
0x14007c525  cmp     rdx, r11
0x14007c528  jz      loc_14007C761
0x14007c52e  movsx   eax, byte ptr [rdx]
0x14007c531  add     eax, [rbp+r10*8+4Fh+var_B4]
0x14007c536  mov     r10d, dword ptr [rsp+120h+var_100+4]
0x14007c53b  jmp     short loc_14007C54E
0x14007c53d  mov     [rbp+r8*8+4Fh+var_B8], r9d
0x14007c542  cmp     rdx, r11
0x14007c545  jz      loc_14007C761
0x14007c54b  movsx   eax, byte ptr [rdx]
0x14007c54e  mov     [rbp+r8*8+4Fh+var_B4], eax
0x14007c553  inc     r15d
0x14007c556  jmp     loc_14007C749
0x14007c55b  cmp     r15d, 1
0x14007c55f  jbe     loc_14007C71B
0x14007c565  dec     r15d
0x14007c568  mov     eax, r15d
0x14007c56b  mov     [rbp+4Fh+var_C0], rax
0x14007c56f  mov     eax, [rbp+r15*8+4Fh+var_B8]
0x14007c574  mov     [rsp+120h+var_F8], eax
0x14007c578  test    r9d, r9d
0x14007c57b  jz      short loc_14007C593
0x14007c57d  xor     edx, edx
0x14007c57f  mov     eax, r10d
0x14007c582  sub     eax, [rbp+rdx*8+4Fh+var_B4]
0x14007c586  sar     eax, 1
0x14007c588  add     [rbp+rdx*8+4Fh+var_B8], eax
0x14007c58c  inc     edx
0x14007c58e  cmp     edx, r15d
0x14007c591  jbe     short loc_14007C57F
0x14007c593  xor     edx, edx
0x14007c595  test    r8d, r8d
0x14007c598  jz      short loc_14007C5E2
0x14007c59a  movd    xmm0, [rbp+rdx*8+4Fh+var_B8]
0x14007c5a0  cvtdq2ps xmm0, xmm0
0x14007c5a3  mulss   xmm0, xmm6
0x14007c5a7  cvttss2si r8d, xmm0
0x14007c5ac  movd    xmm0, [rbp+rdx*8+4Fh+var_B4]
0x14007c5b2  cvtdq2ps xmm0, xmm0
0x14007c5b5  mov     [rbp+rdx*8+4Fh+ptfx.x], r8d
0x14007c5ba  mulss   xmm0, xmm7
0x14007c5be  cvttss2si eax, xmm0
0x14007c5c2  mov     [rbp+rdx*8+4Fh+ptfx.y], eax
0x14007c5c6  cmp     eax, r14d
0x14007c5c9  jle     short loc_14007C5D0
0x14007c5cb  mov     [rbp+rdx*8+4Fh+ptfx.y], r14d
0x14007c5d0  cmp     r8d, esi
0x14007c5d3  jle     short loc_14007C5D9
0x14007c5d5  mov     [rbp+rdx*8+4Fh+ptfx.x], esi
0x14007c5d9  inc     edx
0x14007c5db  cmp     edx, r15d
0x14007c5de  jbe     short loc_14007C59A
0x14007c5e0  jmp     short loc_14007C658
0x14007c5e2  mov     r9d, [r13+78h]
0x14007c5e6  and     r9d, 0FF0h
0x14007c5ed  movd    xmm3, [rbp+rdx*8+4Fh+var_B8]
0x14007c5f3  movd    xmm2, [rbp+rdx*8+4Fh+var_B4]
0x14007c5f9  cvtdq2ps xmm3, xmm3
0x14007c5fc  cvtdq2ps xmm2, xmm2
0x14007c5ff  movaps  xmm1, xmm3
0x14007c602  mulss   xmm3, xmm8
0x14007c607  movaps  xmm0, xmm2
0x14007c60a  mulss   xmm1, xmm6
0x14007c60e  mulss   xmm0, xmm9
0x14007c613  cvttss2si eax, xmm1
0x14007c617  cvttss2si r11d, xmm0
0x14007c61c  mulss   xmm2, xmm7
0x14007c620  add     r11d, eax
0x14007c623  cvttss2si eax, xmm3
0x14007c627  mov     [rbp+rdx*8+4Fh+ptfx.x], r11d
0x14007c62c  cvttss2si r10d, xmm2
0x14007c631  add     r10d, eax
0x14007c634  mov     [rbp+rdx*8+4Fh+ptfx.y], r10d
0x14007c639  test    r9d, r9d
0x14007c63c  jz      short loc_14007C651
0x14007c63e  cmp     r10d, r14d
0x14007c641  jle     short loc_14007C648
0x14007c643  mov     [rbp+rdx*8+4Fh+ptfx.y], r14d
0x14007c648  cmp     r11d, esi
0x14007c64b  jle     short loc_14007C651
0x14007c64d  mov     [rbp+rdx*8+4Fh+ptfx.x], esi
0x14007c651  inc     edx
0x14007c653  cmp     edx, r15d
0x14007c656  jbe     short loc_14007C5ED
0x14007c658  mov     rdx, qword ptr [rbp+4Fh+ptfx.x]; ptfx
0x14007c65c  mov     rcx, rdi; ppo
0x14007c65f  call    PATHOBJ_bMoveTo
0x14007c664  mov     rcx, [rsp+120h+ppo]; ppo
0x14007c669  lea     rdx, [rbp+4Fh+pptfx]; pptfx
0x14007c66d  mov     edi, eax
0x14007c66f  mov     r8d, r15d; cptfx
0x14007c672  and     edi, dword ptr [rsp+120h+var_100]
0x14007c676  call    PATHOBJ_bPolyLineTo
0x14007c67b  and     eax, edi
0x14007c67d  cmp     dword ptr [rsp+120h+var_E0], 0
0x14007c682  mov     dword ptr [rsp+120h+var_100], eax
0x14007c686  jz      short loc_14007C6C7
0x14007c688  mov     edx, [rbp+4Fh+var_CC]
0x14007c68b  xor     ecx, ecx
0x14007c68d  add     [rbp+rcx*8+4Fh+ptfx.x], ebx
0x14007c691  add     [rbp+rcx*8+4Fh+ptfx.y], edx
0x14007c695  inc     ecx
0x14007c697  cmp     ecx, r15d
0x14007c69a  jbe     short loc_14007C68D
0x14007c69c  mov     rdx, qword ptr [rbp+4Fh+ptfx.x]; ptfx
0x14007c6a0  mov     rcx, [rsp+120h+ppo]; ppo
0x14007c6a5  call    PATHOBJ_bMoveTo
0x14007c6aa  mov     rcx, [rsp+120h+ppo]; ppo
0x14007c6af  lea     rdx, [rbp+4Fh+pptfx]; pptfx
0x14007c6b3  mov     edi, eax
0x14007c6b5  mov     r8d, r15d; cptfx
0x14007c6b8  and     edi, dword ptr [rsp+120h+var_100]
0x14007c6bc  call    PATHOBJ_bPolyLineTo
0x14007c6c1  and     eax, edi
0x14007c6c3  mov     dword ptr [rsp+120h+var_100], eax
0x14007c6c7  mov     rcx, [rsp+120h+var_D8]
0x14007c6cc  mov     r11, [rbp+4Fh+var_C8]
0x14007c6d0  cmp     rcx, r11
0x14007c6d3  jz      short loc_14007C708
0x14007c6d5  cmp     byte ptr [rcx], 80h
0x14007c6d8  jz      short loc_14007C708
0x14007c6da  mov     rax, [rbp+4Fh+var_C0]
0x14007c6de  mov     r15d, 1
0x14007c6e4  mov     edx, [rsp+120h+var_F8]
0x14007c6e8  mov     rdi, [rsp+120h+ppo]
0x14007c6ed  mov     r8d, dword ptr [rsp+120h+var_F0]
0x14007c6f2  mov     r9d, dword ptr [rsp+120h+var_F0+4]
0x14007c6f7  mov     r10d, dword ptr [rsp+120h+var_100+4]
0x14007c6fc  mov     [rbp+4Fh+var_B8], edx
0x14007c6ff  mov     eax, [rbp+rax*8+4Fh+var_B4]
0x14007c703  jmp     loc_14007C4E9
0x14007c708  mov     edx, [rsp+120h+var_F8]
0x14007c70c  mov     rdi, [rsp+120h+ppo]
0x14007c711  mov     r10d, dword ptr [rsp+120h+var_100+4]
0x14007c716  mov     [rbp+r15*8+4Fh+var_B8], edx
0x14007c71b  lea     rdx, [rcx+1]
0x14007c71f  cmp     rdx, r11
0x14007c722  jz      short loc_14007C761
0x14007c724  movsx   eax, byte ptr [rdx]
0x14007c727  mov     ecx, r15d
0x14007c72a  add     eax, [rbp+rcx*8+4Fh+var_B8]
0x14007c72e  inc     rdx
0x14007c731  mov     [rbp+4Fh+var_B8], eax
0x14007c734  cmp     rdx, r11
0x14007c737  jz      short loc_14007C761
0x14007c739  movsx   eax, byte ptr [rdx]
0x14007c73c  mov     r15d, 1
0x14007c742  add     eax, [rbp+rcx*8+4Fh+var_B4]
0x14007c746  mov     [rbp+4Fh+var_B4], eax
0x14007c749  mov     r8d, dword ptr [rsp+120h+var_F0]
0x14007c74e  lea     rcx, [rdx+1]
0x14007c752  mov     r9d, dword ptr [rsp+120h+var_F0+4]
0x14007c757  mov     [rsp+120h+var_D8], rcx
0x14007c75c  jmp     loc_14007C4EC
0x14007c761  xor     eax, eax
0x14007c763  jmp     short loc_14007C769
0x14007c765  mov     eax, dword ptr [rsp+120h+var_100]
0x14007c769  mov     rcx, [rbp+4Fh+var_68]
0x14007c76d  xor     rcx, rsp; StackCookie
0x14007c770  call    __security_check_cookie
0x14007c775  lea     r11, [rsp+120h+var_20]
0x14007c77d  mov     rbx, [r11+30h]
0x14007c781  mov     rsi, [r11+38h]
0x14007c785  movaps  xmm6, xmmword ptr [r11-10h]
0x14007c78a  movaps  xmm7, xmmword ptr [r11-20h]
0x14007c78f  movaps  xmm8, xmmword ptr [r11-30h]
0x14007c794  movaps  xmm9, xmmword ptr [r11-40h]
0x14007c799  mov     rsp, r11
0x14007c79c  pop     r15
0x14007c79e  pop     r14
0x14007c7a0  pop     r13
0x14007c7a2  pop     rdi
0x14007c7a3  pop     rbp
0x14007c7a4  retn
```
