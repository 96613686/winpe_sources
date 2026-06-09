# CMdct::cos_t_h_short(float *,float *,float const *)

- ea: `0x18000e3e0`
- end: `0x18000eacb`
- name: `?cos_t_h_short@CMdct@@IEAAXPEAM0PEBM@Z`
- size: `1771`
- prototype: `void __fastcall(CMdct *__hidden this, float *, float *, const float *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000de50`

## callees

- `0x18000e3e0`

## pseudocode

```c
void __fastcall CMdct::cos_t_h_short(CMdct *this, float *a2, float *a3, const float *a4)
{
  double v6; // xmm2_8
  double v7; // xmm1_8
  double v8; // xmm3_8
  double v9; // xmm0_8
  double v10; // xmm3_8
  double v11; // xmm9_8
  double v12; // xmm0_8
  double v13; // xmm8_8
  double v14; // xmm9_8
  double v15; // xmm3_8
  double v16; // xmm4_8
  double v17; // xmm5_8
  double v18; // xmm7_8
  double v19; // xmm8_8
  double v20; // xmm6_8
  double v21; // xmm9_8
  double v22; // xmm4_8
  double v23; // xmm4_8
  double v24; // xmm1_8
  double v25; // xmm3_8
  double v26; // xmm0_8
  double v27; // xmm3_8
  double v28; // xmm2_8
  double v29; // xmm9_8
  double v30; // xmm0_8
  double v31; // xmm8_8
  double v32; // xmm9_8
  double v33; // xmm3_8
  double v34; // xmm4_8
  double v35; // xmm5_8
  double v36; // xmm7_8
  double v37; // xmm9_8
  double v38; // xmm8_8
  double v39; // xmm6_8
  double v40; // xmm4_8
  double v41; // xmm2_8
  double v42; // xmm1_8
  double v43; // xmm3_8
  double v44; // xmm0_8
  double v45; // xmm3_8
  double v46; // xmm9_8
  double v47; // xmm0_8
  double v48; // xmm8_8
  double v49; // xmm9_8
  double v50; // xmm3_8
  double v51; // xmm4_8
  double v52; // xmm5_8
  double v53; // xmm7_8
  double v54; // xmm8_8
  double v55; // xmm6_8
  double v56; // xmm9_8
  int v57; // r8d
  double v58; // xmm4_8
  float *v59; // r9
  float *v60; // rcx
  __int64 v61; // rax
  __m128 v62; // xmm1
  __int64 v63; // rcx
  __int64 v64; // rcx

  *(_OWORD *)this = 0;
  *((_OWORD *)this + 1) = 0;
  *((_OWORD *)this + 2) = 0;
  *((_OWORD *)this + 3) = 0;
  *((_OWORD *)this + 4) = 0;
  *((_OWORD *)this + 5) = 0;
  *((_OWORD *)this + 6) = 0;
  *((_OWORD *)this + 7) = 0;
  *((_OWORD *)this + 8) = 0;
  v6 = a3[15];
  v7 = a3[12] - v6;
  v8 = a3[9] - v7;
  v9 = a3[6] - v8;
  v10 = v8 - v6;
  v11 = a3[3] - v9;
  v12 = v9 * 1.732050776481628;
  v13 = *a3 - v11;
  v14 = v11 - v10;
  v15 = v10 * 1.732050776481628;
  v16 = v14 + v6;
  v17 = v13 + v7 - v12;
  v18 = v13 + v7 + v12;
  v19 = v13 - (v7 + v7);
  v20 = (v14 + v6 + v15) * 1.931851625442505;
  v21 = (v14 - (v6 + v6)) * 1.414213538169861;
  v22 = (v16 - v15) * 0.517638087272644;
  *(float *)&v7 = v20 + v18;
  *((float *)this + 14) = (float)(*(float *)&v7 * a4[8]) + *((float *)this + 14);
  *((float *)this + 15) = (float)(*(float *)&v7 * a4[9]) + *((float *)this + 15);
  *(float *)&v7 = v21 + v19;
  *((float *)this + 13) = (float)(*(float *)&v7 * a4[7]) + *((float *)this + 13);
  *((float *)this + 16) = (float)(*(float *)&v7 * a4[10]) + *((float *)this + 16);
  *(float *)&v7 = v22 + v17;
  *((float *)this + 12) = (float)(*(float *)&v7 * a4[6]) + *((float *)this + 12);
  *((float *)this + 17) = (float)(*(float *)&v7 * a4[11]) + *((float *)this + 17);
  *(float *)&v7 = v17 - v22;
  *((float *)this + 6) = (float)(*(float *)&v7 * *a4) + *((float *)this + 6);
  *((float *)this + 11) = (float)(*(float *)&v7 * a4[5]) + *((float *)this + 11);
  *(float *)&v7 = v19 - v21;
  *((float *)this + 7) = (float)(*(float *)&v7 * a4[1]) + *((float *)this + 7);
  *((float *)this + 10) = (float)(*(float *)&v7 * a4[4]) + *((float *)this + 10);
  *(float *)&v7 = v18 - v20;
  *((float *)this + 8) = (float)(*(float *)&v7 * a4[2]) + *((float *)this + 8);
  *((float *)this + 9) = (float)(*(float *)&v7 * a4[3]) + *((float *)this + 9);
  v23 = a3[16];
  v24 = a3[13] - v23;
  v25 = a3[10] - v24;
  v26 = a3[7] - v25;
  v27 = v25 - v23;
  v28 = v23 + v23;
  v29 = a3[4] - v26;
  v30 = v26 * 1.732050776481628;
  v31 = a3[1] - v29;
  v32 = v29 - v27;
  v33 = v27 * 1.732050776481628;
  v34 = v23 + v32;
  v35 = v31 + v24 - v30;
  v36 = v31 + v24 + v30;
  v37 = (v32 - v28) * 1.414213538169861;
  v38 = v31 - (v24 + v24);
  v39 = (v34 + v33) * 1.931851625442505;
  v40 = (v34 - v33) * 0.517638087272644;
  *(float *)&v28 = v39 + v36;
  *((float *)this + 20) = (float)(*(float *)&v28 * a4[8]) + *((float *)this + 20);
  *((float *)this + 21) = (float)(*(float *)&v28 * a4[9]) + *((float *)this + 21);
  *(float *)&v28 = v37 + v38;
  *((float *)this + 19) = (float)(*(float *)&v28 * a4[7]) + *((float *)this + 19);
  *((float *)this + 22) = (float)(*(float *)&v28 * a4[10]) + *((float *)this + 22);
  *(float *)&v28 = v40 + v35;
  *((float *)this + 18) = (float)(*(float *)&v28 * a4[6]) + *((float *)this + 18);
  *(float *)&v24 = v35 - v40;
  *((float *)this + 23) = (float)(*(float *)&v28 * a4[11]) + *((float *)this + 23);
  *((float *)this + 12) = (float)(*(float *)&v24 * *a4) + *((float *)this + 12);
  *((float *)this + 17) = (float)(*(float *)&v24 * a4[5]) + *((float *)this + 17);
  *(float *)&v24 = v38 - v37;
  *((float *)this + 13) = (float)(*(float *)&v24 * a4[1]) + *((float *)this + 13);
  *((float *)this + 16) = (float)(*(float *)&v24 * a4[4]) + *((float *)this + 16);
  *(float *)&v24 = v36 - v39;
  *((float *)this + 14) = (float)(*(float *)&v24 * a4[2]) + *((float *)this + 14);
  *((float *)this + 15) = (float)(*(float *)&v24 * a4[3]) + *((float *)this + 15);
  v41 = a3[17];
  v42 = a3[14] - v41;
  v43 = a3[11] - v42;
  v44 = a3[8] - v43;
  v45 = v43 - v41;
  v46 = a3[5] - v44;
  v47 = v44 * 1.732050776481628;
  v48 = a3[2] - v46;
  v49 = v46 - v45;
  v50 = v45 * 1.732050776481628;
  v51 = v41 + v49;
  v52 = v48 + v42 - v47;
  v53 = v48 + v42 + v47;
  v54 = v48 - (v42 + v42);
  v55 = (v41 + v49 + v50) * 1.931851625442505;
  v56 = (v49 - (v41 + v41)) * 1.414213538169861;
  v57 = 0;
  v58 = (v51 - v50) * 0.517638087272644;
  *(float *)&v41 = v55 + v53;
  *((float *)this + 26) = (float)(*(float *)&v41 * a4[8]) + *((float *)this + 26);
  *((float *)this + 27) = (float)(*(float *)&v41 * a4[9]) + *((float *)this + 27);
  *(float *)&v41 = v56 + v54;
  *((float *)this + 25) = (float)(*(float *)&v41 * a4[7]) + *((float *)this + 25);
  *((float *)this + 28) = (float)(*(float *)&v41 * a4[10]) + *((float *)this + 28);
  *(float *)&v41 = v58 + v52;
  *((float *)this + 24) = (float)(*(float *)&v41 * a4[6]) + *((float *)this + 24);
  *(float *)&v42 = v52 - v58;
  *((float *)this + 29) = (float)(*(float *)&v41 * a4[11]) + *((float *)this + 29);
  *((float *)this + 18) = (float)(*(float *)&v42 * *a4) + *((float *)this + 18);
  *((float *)this + 23) = (float)(*(float *)&v42 * a4[5]) + *((float *)this + 23);
  *(float *)&v42 = v54 - v56;
  *((float *)this + 19) = (float)(*(float *)&v42 * a4[1]) + *((float *)this + 19);
  *((float *)this + 22) = (float)(*(float *)&v42 * a4[4]) + *((float *)this + 22);
  *(float *)&v47 = v53 - v55;
  *((float *)this + 20) = (float)(*(float *)&v47 * a4[2]) + *((float *)this + 20);
  *(float *)&v42 = *(float *)&v47 * a4[3];
  v59 = (float *)((char *)this + 140);
  *((float *)this + 21) = *(float *)&v42 + *((float *)this + 21);
  v60 = a2 + 17;
  if ( a2 <= v59 && v60 >= (float *)this || a2 <= a3 + 17 && v60 >= a3 || a3 <= v59 && a3 + 17 >= (float *)this )
    goto LABEL_17;
  v61 = 0;
  do
  {
    v57 += 4;
    v62 = _mm_add_ps(*(__m128 *)((char *)this + 4 * v61), *(__m128 *)&a2[v61]);
    *(_OWORD *)&a2[v61] = *(_OWORD *)((char *)this + 4 * v61 + 72);
    *(__m128 *)&a3[v61] = v62;
    v61 += 4;
  }
  while ( v57 < 16 );
  if ( v57 >= 18 )
    return;
  if ( 18 - v57 >= 4 )
  {
LABEL_17:
    do
    {
      v63 = v57;
      v57 += 4;
      a3[v63] = *((float *)this + v63) + a2[v63];
      a2[v63] = *((float *)this + v63 + 18);
      a3[v63 + 1] = *((float *)this + v63 + 1) + a2[v63 + 1];
      a2[v63 + 1] = *((float *)this + v63 + 19);
      a3[v63 + 2] = *((float *)this + v63 + 2) + a2[v63 + 2];
      a2[v63 + 2] = *((float *)this + v63 + 20);
      a3[v63 + 3] = *((float *)this + v63 + 3) + a2[v63 + 3];
      a2[v63 + 3] = *((float *)this + v63 + 21);
    }
    while ( v57 < 15 );
  }
  if ( (unsigned int)v57 < 0x12 )
  {
    v64 = (unsigned int)v57;
    do
    {
      ++v57;
      a3[v64] = *((float *)this + v64) + a2[v64];
      a2[v64] = *((float *)this + v64 + 18);
      ++v64;
    }
    while ( v57 < 18 );
  }
}

```

## disassembly

```asm
0x18000e3e0  sub     rsp, 58h
0x18000e3e4  xorps   xmm0, xmm0
0x18000e3e7  movaps  [rsp+58h+var_18], xmm6
0x18000e3ec  movups  xmmword ptr [rcx], xmm0
0x18000e3ef  mov     r11, r8
0x18000e3f2  mov     r10, rcx
0x18000e3f5  movups  xmmword ptr [rcx+10h], xmm0
0x18000e3f9  movups  xmmword ptr [rcx+20h], xmm0
0x18000e3fd  movups  xmmword ptr [rcx+30h], xmm0
0x18000e401  movups  xmmword ptr [rcx+40h], xmm0
0x18000e405  movups  xmmword ptr [rcx+50h], xmm0
0x18000e409  movups  xmmword ptr [rcx+60h], xmm0
0x18000e40d  movups  xmmword ptr [rcx+70h], xmm0
0x18000e411  movups  xmmword ptr [rcx+80h], xmm0
0x18000e418  movss   xmm2, dword ptr [r8+3Ch]
0x18000e41e  movss   xmm1, dword ptr [r8+30h]
0x18000e424  movss   xmm3, dword ptr [r8+24h]
0x18000e42a  movss   xmm0, dword ptr [r8+18h]
0x18000e430  cvtps2pd xmm0, xmm0
0x18000e433  cvtps2pd xmm1, xmm1
0x18000e436  movaps  [rsp+58h+var_28], xmm7
0x18000e43b  movaps  [rsp+58h+var_38], xmm8
0x18000e441  movaps  [rsp+58h+var_48], xmm9
0x18000e447  movaps  [rsp+58h+var_58], xmm13
0x18000e44c  movss   xmm9, dword ptr [r8+0Ch]
0x18000e452  movss   xmm8, dword ptr [r8]
0x18000e457  movsd   xmm13, cs:__real@3ffbb67ae0000000
0x18000e460  cvtps2pd xmm9, xmm9
0x18000e464  cvtps2pd xmm2, xmm2
0x18000e467  cvtps2pd xmm3, xmm3
0x18000e46a  subsd   xmm1, xmm2
0x18000e46e  cvtps2pd xmm8, xmm8
0x18000e472  subsd   xmm3, xmm1
0x18000e476  subsd   xmm0, xmm3
0x18000e47a  subsd   xmm3, xmm2
0x18000e47e  subsd   xmm9, xmm0
0x18000e483  mulsd   xmm0, xmm13
0x18000e488  subsd   xmm8, xmm9
0x18000e48d  subsd   xmm9, xmm3
0x18000e492  mulsd   xmm3, xmm13
0x18000e497  movaps  xmm5, xmm8
0x18000e49b  addsd   xmm5, xmm1
0x18000e49f  movaps  xmm4, xmm9
0x18000e4a3  addsd   xmm1, xmm1
0x18000e4a7  addsd   xmm4, xmm2
0x18000e4ab  addsd   xmm2, xmm2
0x18000e4af  movaps  xmm7, xmm5
0x18000e4b2  subsd   xmm5, xmm0
0x18000e4b6  addsd   xmm7, xmm0
0x18000e4ba  subsd   xmm8, xmm1
0x18000e4bf  movaps  xmm6, xmm4
0x18000e4c2  addsd   xmm6, xmm3
0x18000e4c6  subsd   xmm9, xmm2
0x18000e4cb  subsd   xmm4, xmm3
0x18000e4cf  mulsd   xmm6, cs:__real@3ffee8dd40000000
0x18000e4d7  mulsd   xmm9, cs:__real@3ff6a09e60000000
0x18000e4e0  mulsd   xmm4, cs:__real@3fe0907dc0000000
0x18000e4e8  movaps  xmm0, xmm6
0x18000e4eb  addsd   xmm0, xmm7
0x18000e4ef  cvtpd2ps xmm1, xmm0
0x18000e4f3  movaps  xmm0, xmm1
0x18000e4f6  mulss   xmm0, dword ptr [r9+20h]
0x18000e4fc  addss   xmm0, dword ptr [rcx+38h]
0x18000e501  movss   dword ptr [rcx+38h], xmm0
0x18000e506  movaps  xmm0, xmm9
0x18000e50a  mulss   xmm1, dword ptr [r9+24h]
0x18000e510  addsd   xmm0, xmm8
0x18000e515  addss   xmm1, dword ptr [rcx+3Ch]
0x18000e51a  movss   dword ptr [rcx+3Ch], xmm1
0x18000e51f  cvtpd2ps xmm1, xmm0
0x18000e523  movaps  xmm0, xmm1
0x18000e526  mulss   xmm0, dword ptr [r9+1Ch]
0x18000e52c  addss   xmm0, dword ptr [rcx+34h]
0x18000e531  movss   dword ptr [rcx+34h], xmm0
0x18000e536  movaps  xmm0, xmm4
0x18000e539  mulss   xmm1, dword ptr [r9+28h]
0x18000e53f  addsd   xmm0, xmm5
0x18000e543  addss   xmm1, dword ptr [rcx+40h]
0x18000e548  movss   dword ptr [rcx+40h], xmm1
0x18000e54d  cvtpd2ps xmm1, xmm0
0x18000e551  movaps  xmm0, xmm1
0x18000e554  mulss   xmm0, dword ptr [r9+18h]
0x18000e55a  addss   xmm0, dword ptr [rcx+30h]
0x18000e55f  subsd   xmm8, xmm9
0x18000e564  subsd   xmm5, xmm4
0x18000e568  subsd   xmm7, xmm6
0x18000e56c  movss   dword ptr [rcx+30h], xmm0
0x18000e571  mulss   xmm1, dword ptr [r9+2Ch]
0x18000e577  addss   xmm1, dword ptr [rcx+44h]
0x18000e57c  movss   dword ptr [rcx+44h], xmm1
0x18000e581  cvtpd2ps xmm1, xmm5
0x18000e585  movaps  xmm0, xmm1
0x18000e588  mulss   xmm0, dword ptr [r9]
0x18000e58d  addss   xmm0, dword ptr [rcx+18h]
0x18000e592  movss   dword ptr [rcx+18h], xmm0
0x18000e597  mulss   xmm1, dword ptr [r9+14h]
0x18000e59d  addss   xmm1, dword ptr [rcx+2Ch]
0x18000e5a2  movss   dword ptr [rcx+2Ch], xmm1
0x18000e5a7  cvtpd2ps xmm1, xmm8
0x18000e5ac  movaps  xmm0, xmm1
0x18000e5af  mulss   xmm0, dword ptr [r9+4]
0x18000e5b5  addss   xmm0, dword ptr [rcx+1Ch]
0x18000e5ba  movss   dword ptr [rcx+1Ch], xmm0
0x18000e5bf  mulss   xmm1, dword ptr [r9+10h]
0x18000e5c5  addss   xmm1, dword ptr [rcx+28h]
0x18000e5ca  movss   dword ptr [rcx+28h], xmm1
0x18000e5cf  cvtpd2ps xmm1, xmm7
0x18000e5d3  movaps  xmm0, xmm1
0x18000e5d6  mulss   xmm0, dword ptr [r9+8]
0x18000e5dc  addss   xmm0, dword ptr [rcx+20h]
0x18000e5e1  movss   dword ptr [rcx+20h], xmm0
0x18000e5e6  mulss   xmm1, dword ptr [r9+0Ch]
0x18000e5ec  addss   xmm1, dword ptr [rcx+24h]
0x18000e5f1  movss   dword ptr [rcx+24h], xmm1
0x18000e5f6  movss   xmm2, dword ptr [r8+40h]
0x18000e5fc  movss   xmm1, dword ptr [r8+34h]
0x18000e602  movss   xmm3, dword ptr [r8+28h]
0x18000e608  movss   xmm0, dword ptr [r8+1Ch]
0x18000e60e  movss   xmm9, dword ptr [r8+10h]
0x18000e614  movss   xmm8, dword ptr [r8+4]
0x18000e61a  cvtps2pd xmm2, xmm2
0x18000e61d  cvtps2pd xmm1, xmm1
0x18000e620  movaps  xmm4, xmm2
0x18000e623  subsd   xmm1, xmm2
0x18000e627  cvtps2pd xmm0, xmm0
0x18000e62a  cvtps2pd xmm9, xmm9
0x18000e62e  cvtps2pd xmm3, xmm3
0x18000e631  cvtps2pd xmm8, xmm8
0x18000e635  subsd   xmm3, xmm1
0x18000e639  subsd   xmm0, xmm3
0x18000e63d  subsd   xmm3, xmm2
0x18000e641  addsd   xmm2, xmm2
0x18000e645  subsd   xmm9, xmm0
0x18000e64a  mulsd   xmm0, xmm13
0x18000e64f  subsd   xmm8, xmm9
0x18000e654  subsd   xmm9, xmm3
0x18000e659  mulsd   xmm3, xmm13
0x18000e65e  movaps  xmm5, xmm8
0x18000e662  addsd   xmm5, xmm1
0x18000e666  addsd   xmm4, xmm9
0x18000e66b  subsd   xmm9, xmm2
0x18000e670  addsd   xmm1, xmm1
0x18000e674  movaps  xmm7, xmm5
0x18000e677  subsd   xmm5, xmm0
0x18000e67b  movaps  xmm6, xmm4
0x18000e67e  addsd   xmm7, xmm0
0x18000e682  mulsd   xmm9, cs:__real@3ff6a09e60000000
0x18000e68b  addsd   xmm6, xmm3
0x18000e68f  subsd   xmm8, xmm1
0x18000e694  subsd   xmm4, xmm3
0x18000e698  mulsd   xmm6, cs:__real@3ffee8dd40000000
0x18000e6a0  mulsd   xmm4, cs:__real@3fe0907dc0000000
0x18000e6a8  movaps  xmm0, xmm6
0x18000e6ab  addsd   xmm0, xmm7
0x18000e6af  cvtpd2ps xmm2, xmm0
0x18000e6b3  movaps  xmm0, xmm9
0x18000e6b7  movaps  xmm1, xmm2
0x18000e6ba  mulss   xmm1, dword ptr [r9+20h]
0x18000e6c0  addss   xmm1, dword ptr [rcx+50h]
0x18000e6c5  movss   dword ptr [rcx+50h], xmm1
0x18000e6ca  mulss   xmm2, dword ptr [r9+24h]
0x18000e6d0  addss   xmm2, dword ptr [rcx+54h]
0x18000e6d5  movss   dword ptr [rcx+54h], xmm2
0x18000e6da  addsd   xmm0, xmm8
0x18000e6df  subsd   xmm8, xmm9
0x18000e6e4  subsd   xmm7, xmm6
0x18000e6e8  cvtpd2ps xmm2, xmm0
0x18000e6ec  movaps  xmm0, xmm4
0x18000e6ef  addsd   xmm0, xmm5
0x18000e6f3  movaps  xmm1, xmm2
0x18000e6f6  mulss   xmm1, dword ptr [r9+1Ch]
0x18000e6fc  subsd   xmm5, xmm4
0x18000e700  addss   xmm1, dword ptr [rcx+4Ch]
0x18000e705  movss   dword ptr [rcx+4Ch], xmm1
0x18000e70a  mulss   xmm2, dword ptr [r9+28h]
0x18000e710  addss   xmm2, dword ptr [rcx+58h]
0x18000e715  movss   dword ptr [rcx+58h], xmm2
0x18000e71a  cvtpd2ps xmm2, xmm0
0x18000e71e  movaps  xmm1, xmm2
0x18000e721  mulss   xmm1, dword ptr [r9+18h]
0x18000e727  addss   xmm1, dword ptr [rcx+48h]
0x18000e72c  movss   dword ptr [rcx+48h], xmm1
0x18000e731  mulss   xmm2, dword ptr [r9+2Ch]
0x18000e737  cvtpd2ps xmm1, xmm5
0x18000e73b  addss   xmm2, dword ptr [rcx+5Ch]
0x18000e740  movaps  xmm0, xmm1
0x18000e743  movss   dword ptr [rcx+5Ch], xmm2
0x18000e748  mulss   xmm0, dword ptr [r9]
0x18000e74d  addss   xmm0, dword ptr [rcx+30h]
0x18000e752  movss   dword ptr [rcx+30h], xmm0
0x18000e757  mulss   xmm1, dword ptr [r9+14h]
0x18000e75d  addss   xmm1, dword ptr [rcx+44h]
0x18000e762  movss   dword ptr [rcx+44h], xmm1
0x18000e767  cvtpd2ps xmm1, xmm8
0x18000e76c  movaps  xmm0, xmm1
0x18000e76f  mulss   xmm0, dword ptr [r9+4]
0x18000e775  addss   xmm0, dword ptr [rcx+34h]
0x18000e77a  movss   dword ptr [rcx+34h], xmm0
0x18000e77f  mulss   xmm1, dword ptr [r9+10h]
0x18000e785  addss   xmm1, dword ptr [rcx+40h]
0x18000e78a  movss   dword ptr [rcx+40h], xmm1
0x18000e78f  cvtpd2ps xmm1, xmm7
0x18000e793  movaps  xmm0, xmm1
0x18000e796  mulss   xmm0, dword ptr [r9+8]
0x18000e79c  addss   xmm0, dword ptr [rcx+38h]
0x18000e7a1  movss   dword ptr [rcx+38h], xmm0
0x18000e7a6  mulss   xmm1, dword ptr [r9+0Ch]
0x18000e7ac  addss   xmm1, dword ptr [rcx+3Ch]
0x18000e7b1  movss   dword ptr [rcx+3Ch], xmm1
0x18000e7b6  movss   xmm2, dword ptr [r8+44h]
0x18000e7bc  movss   xmm1, dword ptr [r8+38h]
0x18000e7c2  movss   xmm3, dword ptr [r8+2Ch]
0x18000e7c8  movss   xmm0, dword ptr [r8+20h]
0x18000e7ce  movss   xmm9, dword ptr [r8+14h]
0x18000e7d4  movss   xmm8, dword ptr [r8+8]
0x18000e7da  cvtps2pd xmm2, xmm2
0x18000e7dd  cvtps2pd xmm3, xmm3
0x18000e7e0  cvtps2pd xmm9, xmm9
0x18000e7e4  cvtps2pd xmm8, xmm8
0x18000e7e8  cvtps2pd xmm1, xmm1
0x18000e7eb  movaps  xmm4, xmm2
0x18000e7ee  subsd   xmm1, xmm2
0x18000e7f2  cvtps2pd xmm0, xmm0
0x18000e7f5  subsd   xmm3, xmm1
0x18000e7f9  subsd   xmm0, xmm3
0x18000e7fd  subsd   xmm3, xmm2
0x18000e801  addsd   xmm2, xmm2
0x18000e805  subsd   xmm9, xmm0
0x18000e80a  mulsd   xmm0, xmm13
0x18000e80f  subsd   xmm8, xmm9
0x18000e814  subsd   xmm9, xmm3
0x18000e819  mulsd   xmm3, xmm13
0x18000e81e  movaps  xmm5, xmm8
0x18000e822  addsd   xmm5, xmm1
0x18000e826  addsd   xmm4, xmm9
0x18000e82b  addsd   xmm1, xmm1
0x18000e82f  subsd   xmm9, xmm2
0x18000e834  movaps  xmm7, xmm5
0x18000e837  subsd   xmm5, xmm0
0x18000e83b  movaps  xmm6, xmm4
0x18000e83e  addsd   xmm7, xmm0
0x18000e842  addsd   xmm6, xmm3
0x18000e846  subsd   xmm8, xmm1
0x18000e84b  mulsd   xmm6, cs:__real@3ffee8dd40000000
0x18000e853  mulsd   xmm9, cs:__real@3ff6a09e60000000
0x18000e85c  subsd   xmm4, xmm3
0x18000e860  xor     r8d, r8d
0x18000e863  movaps  xmm0, xmm6
0x18000e866  addsd   xmm0, xmm7
0x18000e86a  subsd   xmm7, xmm6
0x18000e86e  mulsd   xmm4, cs:__real@3fe0907dc0000000
0x18000e876  cvtpd2ps xmm2, xmm0
0x18000e87a  movaps  xmm0, xmm9
0x18000e87e  addsd   xmm0, xmm8
0x18000e883  movaps  xmm1, xmm2
0x18000e886  mulss   xmm1, dword ptr [r9+20h]
0x18000e88c  subsd   xmm8, xmm9
0x18000e891  addss   xmm1, dword ptr [rcx+68h]
0x18000e896  movss   dword ptr [rcx+68h], xmm1
0x18000e89b  mulss   xmm2, dword ptr [r9+24h]
0x18000e8a1  addss   xmm2, dword ptr [rcx+6Ch]
0x18000e8a6  movss   dword ptr [rcx+6Ch], xmm2
0x18000e8ab  cvtpd2ps xmm2, xmm0
0x18000e8af  movaps  xmm0, xmm4
0x18000e8b2  addsd   xmm0, xmm5
0x18000e8b6  movaps  xmm1, xmm2
0x18000e8b9  mulss   xmm1, dword ptr [r9+1Ch]
0x18000e8bf  subsd   xmm5, xmm4
0x18000e8c3  addss   xmm1, dword ptr [rcx+64h]
0x18000e8c8  movss   dword ptr [rcx+64h], xmm1
0x18000e8cd  mulss   xmm2, dword ptr [r9+28h]
0x18000e8d3  addss   xmm2, dword ptr [rcx+70h]
0x18000e8d8  movss   dword ptr [rcx+70h], xmm2
0x18000e8dd  cvtpd2ps xmm2, xmm0
0x18000e8e1  movaps  xmm1, xmm2
0x18000e8e4  mulss   xmm1, dword ptr [r9+18h]
0x18000e8ea  addss   xmm1, dword ptr [rcx+60h]
0x18000e8ef  movss   dword ptr [rcx+60h], xmm1
0x18000e8f4  mulss   xmm2, dword ptr [r9+2Ch]
0x18000e8fa  cvtpd2ps xmm1, xmm5
0x18000e8fe  addss   xmm2, dword ptr [rcx+74h]
0x18000e903  movaps  xmm0, xmm1
0x18000e906  movss   dword ptr [rcx+74h], xmm2
0x18000e90b  mulss   xmm0, dword ptr [r9]
0x18000e910  addss   xmm0, dword ptr [rcx+48h]
0x18000e915  movss   dword ptr [rcx+48h], xmm0
0x18000e91a  mulss   xmm1, dword ptr [r9+14h]
0x18000e920  addss   xmm1, dword ptr [rcx+5Ch]
0x18000e925  movss   dword ptr [rcx+5Ch], xmm1
0x18000e92a  cvtpd2ps xmm1, xmm8
0x18000e92f  movaps  xmm0, xmm1
0x18000e932  mulss   xmm0, dword ptr [r9+4]
0x18000e938  addss   xmm0, dword ptr [rcx+4Ch]
0x18000e93d  movss   dword ptr [rcx+4Ch], xmm0
0x18000e942  mulss   xmm1, dword ptr [r9+10h]
0x18000e948  addss   xmm1, dword ptr [rcx+58h]
0x18000e94d  movss   dword ptr [rcx+58h], xmm1
0x18000e952  cvtpd2ps xmm1, xmm7
0x18000e956  movaps  xmm0, xmm1
0x18000e959  mulss   xmm0, dword ptr [r9+8]
  ... truncated ...
```
