# SetSVerb

- ea: `0x180002a40`
- end: `0x180002f53`
- name: `SetSVerb`
- size: `1299`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180001fe0`
- `0x180007340`

## callees

- `0x180001d6a`
- `0x180001d82`
- `0x180001dc0`
- `0x180002a40`

## pseudocode

```c
__int64 __fastcall SetSVerb(float a1, float a2, float a3, float a4, __int64 a5)
{
  float v5; // xmm4_4
  __m128 v6; // xmm12
  float v7; // xmm3_4
  float v8; // xmm13_4
  float v9; // xmm0_4
  float v10; // xmm15_4
  float v11; // xmm14_4
  int v12; // edi
  float v13; // xmm11_4
  float v14; // xmm7_4
  int v15; // esi
  float v16; // xmm10_4
  int v17; // ebx
  float v18; // xmm6_4
  float v19; // xmm8_4
  float v20; // xmm1_4
  int v21; // ebx
  float v22; // xmm2_4
  float v23; // xmm6_4
  float v24; // xmm7_4
  float v25; // xmm7_4
  float v26; // xmm1_4
  int v27; // ebx
  float v28; // xmm2_4
  float v29; // xmm6_4
  float v30; // xmm8_4
  float v31; // xmm8_4
  float v32; // xmm1_4
  int v33; // ebx
  float v34; // xmm2_4
  __m128 v35; // xmm6
  __m128 v36; // xmm1
  __m128 v37; // xmm7
  float v38; // xmm2_4
  __m128d v39; // xmm1
  double v40; // xmm0_8
  float v41; // xmm8_4
  float v42; // xmm6_4
  __m128 v43; // xmm7
  __m128d v44; // xmm1
  double v45; // xmm0_8
  float v46; // xmm0_4
  __m128d v47; // xmm0
  double v48; // xmm0_8
  float v49; // xmm1_4

  v5 = fminf(0.99900001, a4);
  if ( v5 <= 0.0 )
    v5 = FLOAT_0_001;
  v6 = (__m128)LODWORD(FLOAT_1_0);
  v7 = fmaxf(0.001, a3);
  v8 = fminf(0.0, a1);
  v9 = *(float *)(a5 + 8);
  v10 = (float)(1.0 / v5) - 1.0;
  v11 = fminf(0.0, a2);
  if ( v9 < 1.0 )
  {
    v9 = FLOAT_22050_0;
    *(_DWORD *)(a5 + 8) = 1185694720;
  }
  v12 = *(int *)(a5 + 44) >> 1;
  v13 = -3000.0 / (float)(v7 * v9);
  v14 = pow(10.0, (float)((float)v12 * v13));
  v15 = *(int *)(a5 + 48) >> 1;
  *(float *)(a5 + 60) = v14;
  v16 = pow(10.0, (float)((float)v15 * v13));
  v17 = *(int *)(a5 + 28) >> 2;
  *(float *)(a5 + 68) = v16;
  v18 = pow(10.0, (float)((float)v17 * v13));
  v19 = (float)((float)((float)((float)((float)((float)((float)(v18 * v14) + 1.0) * (float)(v18 * v14)) + 1.0)
                              * (float)(v18 * v14))
                      + 1.0)
              * (float)(v18 * v14))
      + 1.0;
  v20 = pow(10.0, (float)((float)((float)(v17 + v12) * v13) * v10));
  v21 = *(int *)(a5 + 32) >> 2;
  v22 = (float)(1.0 - v20) * 0.5;
  *(float *)(a5 + 84) = v22 * v18;
  *(float *)(a5 + 76) = (float)(1.0 - v22) * v18;
  v23 = pow(10.0, (float)((float)v21 * v13));
  v24 = (float)((float)((float)((float)((float)((float)(v23 * v14) + 1.0) * (float)(v23 * v14)) + 1.0)
                      * (float)(v23 * v14))
              + 1.0)
      * (float)(v23 * v14);
  v25 = (float)((float)(v24 + 1.0) * (float)(v24 + 1.0)) + (float)((float)(v19 * v19) + 0.0);
  v26 = pow(10.0, (float)((float)((float)(v21 + v12) * v13) * v10));
  v27 = *(int *)(a5 + 36) >> 2;
  v28 = (float)(1.0 - v26) * 0.5;
  *(float *)(a5 + 100) = v28 * v23;
  *(float *)(a5 + 92) = (float)(1.0 - v28) * v23;
  v29 = pow(10.0, (float)((float)v27 * v13));
  v30 = (float)((float)((float)((float)((float)((float)((float)(v29 * v16) + 1.0) * (float)(v29 * v16)) + 1.0)
                              * (float)(v29 * v16))
                      + 1.0)
              * (float)(v29 * v16))
      + 1.0;
  v31 = (float)(v30 * v30) + v25;
  v32 = pow(10.0, (float)((float)((float)(v27 + v15) * v13) * v10));
  v33 = *(int *)(a5 + 40) >> 2;
  v34 = (float)(1.0 - v32) * 0.5;
  *(float *)(a5 + 116) = v34 * v29;
  *(float *)(a5 + 108) = (float)(1.0 - v34) * v29;
  v35 = 0;
  v35.m128_f32[0] = pow(10.0, (float)((float)v33 * v13));
  v36 = v35;
  v36.m128_f32[0] = v35.m128_f32[0] * v16;
  v37 = v36;
  v37.m128_f32[0] = (float)((float)((float)((float)((float)((float)(v36.m128_f32[0] + 1.0) * v36.m128_f32[0]) + 1.0)
                                          * v36.m128_f32[0])
                                  + 1.0)
                          * v36.m128_f32[0])
                  + 1.0;
  v36.m128_f32[0] = pow(10.0, (float)((float)((float)(v33 + v15) * v13) * v10));
  v37.m128_f32[0] = (float)(v37.m128_f32[0] * v37.m128_f32[0]) + v31;
  v38 = (float)(1.0 - v36.m128_f32[0]) * 0.5;
  *(float *)(a5 + 132) = v38 * v35.m128_f32[0];
  *(float *)(a5 + 124) = (float)(1.0 - v38) * v35.m128_f32[0];
  v39 = _mm_cvtps_pd(v37);
  if ( v39.m128d_f64[0] < 0.0 )
    v40 = sqrt(v39.m128d_f64[0]);
  else
    *(_QWORD *)&v40 = *(_OWORD *)&_mm_sqrt_pd(v39);
  v41 = v40;
  *(float *)(a5 + 140) = v41;
  v42 = pow(10.0, (float)(v8 * 0.050000001));
  v43 = 0;
  v43.m128_f32[0] = pow(10.0, (float)(v11 * 0.1));
  v6.m128_f32[0] = 1.0 - v43.m128_f32[0];
  v44 = _mm_cvtps_pd(v6);
  if ( v44.m128d_f64[0] < 0.0 )
    v45 = sqrt(v44.m128d_f64[0]);
  else
    *(_QWORD *)&v45 = *(_OWORD *)&_mm_sqrt_pd(v44);
  v46 = v45;
  *(float *)(a5 + 12) = v46 * v42;
  v47 = _mm_cvtps_pd(v43);
  if ( v47.m128d_f64[0] < 0.0 )
    v48 = sqrt(v47.m128d_f64[0]);
  else
    *(_QWORD *)&v48 = *(_OWORD *)&_mm_sqrt_pd(v47);
  v49 = v48;
  *(float *)(a5 + 20) = v49 * (float)((float)(4.0 / v41) * v42);
  return ConvertCoefsToFix(a5);
}

```

## disassembly

```asm
0x180002a40  mov     rax, rsp
0x180002a43  push    rbx
0x180002a44  push    rbp
0x180002a45  push    rsi
0x180002a46  push    rdi
0x180002a47  sub     rsp, 0C8h
0x180002a4e  movss   xmm4, cs:__real@3f7fbe77
0x180002a56  movaps  xmmword ptr [rax-38h], xmm6
0x180002a5a  minss   xmm4, xmm3
0x180002a5e  movss   xmm3, cs:__real@3a83126f
0x180002a66  movaps  xmmword ptr [rax-48h], xmm7
0x180002a6a  movaps  xmmword ptr [rax-58h], xmm8
0x180002a6f  movaps  xmmword ptr [rax-68h], xmm9
0x180002a74  xorps   xmm9, xmm9
0x180002a78  comiss  xmm9, xmm4
0x180002a7c  movaps  xmmword ptr [rax-78h], xmm10
0x180002a81  movaps  [rsp+0E8h+var_88], xmm11
0x180002a87  movaps  [rsp+0E8h+var_98], xmm12
0x180002a8d  movaps  [rsp+0E8h+var_A8], xmm13
0x180002a93  movaps  [rsp+0E8h+var_B8], xmm14
0x180002a99  movaps  [rsp+0E8h+var_C8], xmm15
0x180002a9f  jb      short loc_180002AA4
0x180002aa1  movaps  xmm4, xmm3
0x180002aa4  movss   xmm12, cs:__real@3f800000
0x180002aad  maxss   xmm3, xmm2
0x180002ab1  mov     rbp, [rsp+0E8h+arg_20]
0x180002ab9  movaps  xmm15, xmm12
0x180002abd  divss   xmm15, xmm4
0x180002ac2  xorps   xmm13, xmm13
0x180002ac6  xorps   xmm14, xmm14
0x180002aca  minss   xmm13, xmm0
0x180002acf  movss   xmm0, dword ptr [rbp+8]
0x180002ad4  comiss  xmm12, xmm0
0x180002ad8  subss   xmm15, xmm12
0x180002add  minss   xmm14, xmm1
0x180002ae2  jbe     short loc_180002AF3
0x180002ae4  movss   xmm0, cs:__real@46ac4400
0x180002aec  mov     dword ptr [rbp+8], 46AC4400h
0x180002af3  movss   xmm11, cs:__real@c53b8000
0x180002afc  mov     edi, [rbp+2Ch]
0x180002aff  movsd   xmm6, cs:__real@4024000000000000
0x180002b07  mulss   xmm3, xmm0
0x180002b0b  xorps   xmm0, xmm0
0x180002b0e  sar     edi, 1
0x180002b10  divss   xmm11, xmm3
0x180002b15  cvtsi2ss xmm0, edi
0x180002b19  mulss   xmm0, xmm11
0x180002b1e  cvtps2pd xmm1, xmm0; Y
0x180002b21  movaps  xmm0, xmm6; X
0x180002b24  call    pow
0x180002b29  mov     esi, [rbp+30h]
0x180002b2c  xorps   xmm7, xmm7
0x180002b2f  cvtsd2ss xmm7, xmm0
0x180002b33  sar     esi, 1
0x180002b35  xorps   xmm0, xmm0
0x180002b38  cvtsi2ss xmm0, esi
0x180002b3c  movss   dword ptr [rbp+3Ch], xmm7
0x180002b41  mulss   xmm0, xmm11
0x180002b46  cvtps2pd xmm1, xmm0; Y
0x180002b49  movaps  xmm0, xmm6; X
0x180002b4c  call    pow
0x180002b51  mov     ebx, [rbp+1Ch]
0x180002b54  xorps   xmm10, xmm10
0x180002b58  cvtsd2ss xmm10, xmm0
0x180002b5d  sar     ebx, 2
0x180002b60  xorps   xmm0, xmm0
0x180002b63  cvtsi2ss xmm0, ebx
0x180002b67  movss   dword ptr [rbp+44h], xmm10
0x180002b6d  mulss   xmm0, xmm11
0x180002b72  cvtps2pd xmm1, xmm0; Y
0x180002b75  movaps  xmm0, xmm6; X
0x180002b78  call    pow
0x180002b7d  xorps   xmm6, xmm6
0x180002b80  lea     eax, [rbx+rdi]
0x180002b83  cvtsd2ss xmm6, xmm0
0x180002b87  xorps   xmm0, xmm0
0x180002b8a  cvtsi2ss xmm0, eax
0x180002b8e  movaps  xmm1, xmm6
0x180002b91  mulss   xmm1, xmm7
0x180002b95  mulss   xmm0, xmm11
0x180002b9a  movaps  xmm8, xmm1
0x180002b9e  addss   xmm8, xmm12
0x180002ba3  mulss   xmm0, xmm15
0x180002ba8  mulss   xmm8, xmm1
0x180002bad  addss   xmm8, xmm12
0x180002bb2  mulss   xmm8, xmm1
0x180002bb7  addss   xmm8, xmm12
0x180002bbc  mulss   xmm8, xmm1
0x180002bc1  cvtps2pd xmm1, xmm0; Y
0x180002bc4  movsd   xmm0, cs:__real@4024000000000000; X
0x180002bcc  addss   xmm8, xmm12
0x180002bd1  mulss   xmm8, xmm8
0x180002bd6  addss   xmm8, xmm9
0x180002bdb  call    pow
0x180002be0  movss   xmm9, cs:__real@3f000000
0x180002be9  xorps   xmm1, xmm1
0x180002bec  mov     ebx, [rbp+20h]
0x180002bef  movaps  xmm2, xmm12
0x180002bf3  cvtsd2ss xmm1, xmm0
0x180002bf7  sar     ebx, 2
0x180002bfa  subss   xmm2, xmm1
0x180002bfe  movaps  xmm1, xmm12
0x180002c02  mulss   xmm2, xmm9
0x180002c07  movaps  xmm0, xmm2
0x180002c0a  subss   xmm1, xmm2
0x180002c0e  mulss   xmm0, xmm6
0x180002c12  movss   dword ptr [rbp+54h], xmm0
0x180002c17  xorps   xmm0, xmm0
0x180002c1a  cvtsi2ss xmm0, ebx
0x180002c1e  mulss   xmm1, xmm6
0x180002c22  mulss   xmm0, xmm11
0x180002c27  movss   dword ptr [rbp+4Ch], xmm1
0x180002c2c  cvtps2pd xmm1, xmm0; Y
0x180002c2f  movsd   xmm0, cs:__real@4024000000000000; X
0x180002c37  call    pow
0x180002c3c  xorps   xmm6, xmm6
0x180002c3f  cvtsd2ss xmm6, xmm0
0x180002c43  movaps  xmm1, xmm6
0x180002c46  mulss   xmm1, xmm7
0x180002c4a  xorps   xmm0, xmm0
0x180002c4d  lea     eax, [rbx+rdi]
0x180002c50  cvtsi2ss xmm0, eax
0x180002c54  movaps  xmm7, xmm1
0x180002c57  addss   xmm7, xmm12
0x180002c5c  mulss   xmm0, xmm11
0x180002c61  mulss   xmm0, xmm15
0x180002c66  mulss   xmm7, xmm1
0x180002c6a  addss   xmm7, xmm12
0x180002c6f  mulss   xmm7, xmm1
0x180002c73  addss   xmm7, xmm12
0x180002c78  mulss   xmm7, xmm1
0x180002c7c  cvtps2pd xmm1, xmm0; Y
0x180002c7f  movsd   xmm0, cs:__real@4024000000000000; X
0x180002c87  addss   xmm7, xmm12
0x180002c8c  mulss   xmm7, xmm7
0x180002c90  addss   xmm7, xmm8
0x180002c95  call    pow
0x180002c9a  mov     ebx, [rbp+24h]
0x180002c9d  xorps   xmm1, xmm1
0x180002ca0  cvtsd2ss xmm1, xmm0
0x180002ca4  sar     ebx, 2
0x180002ca7  movaps  xmm2, xmm12
0x180002cab  subss   xmm2, xmm1
0x180002caf  movaps  xmm1, xmm12
0x180002cb3  mulss   xmm2, xmm9
0x180002cb8  movaps  xmm0, xmm2
0x180002cbb  subss   xmm1, xmm2
0x180002cbf  mulss   xmm0, xmm6
0x180002cc3  movss   dword ptr [rbp+64h], xmm0
0x180002cc8  xorps   xmm0, xmm0
0x180002ccb  cvtsi2ss xmm0, ebx
0x180002ccf  mulss   xmm1, xmm6
0x180002cd3  mulss   xmm0, xmm11
0x180002cd8  movss   dword ptr [rbp+5Ch], xmm1
0x180002cdd  cvtps2pd xmm1, xmm0; Y
0x180002ce0  movsd   xmm0, cs:__real@4024000000000000; X
0x180002ce8  call    pow
0x180002ced  xorps   xmm6, xmm6
0x180002cf0  lea     eax, [rbx+rsi]
0x180002cf3  cvtsd2ss xmm6, xmm0
0x180002cf7  xorps   xmm0, xmm0
0x180002cfa  cvtsi2ss xmm0, eax
0x180002cfe  movaps  xmm1, xmm6
0x180002d01  mulss   xmm1, xmm10
0x180002d06  mulss   xmm0, xmm11
0x180002d0b  movaps  xmm8, xmm1
0x180002d0f  addss   xmm8, xmm12
0x180002d14  mulss   xmm0, xmm15
0x180002d19  mulss   xmm8, xmm1
0x180002d1e  addss   xmm8, xmm12
0x180002d23  mulss   xmm8, xmm1
0x180002d28  addss   xmm8, xmm12
0x180002d2d  mulss   xmm8, xmm1
0x180002d32  cvtps2pd xmm1, xmm0; Y
0x180002d35  movsd   xmm0, cs:__real@4024000000000000; X
0x180002d3d  addss   xmm8, xmm12
0x180002d42  mulss   xmm8, xmm8
0x180002d47  addss   xmm8, xmm7
0x180002d4c  call    pow
0x180002d51  mov     ebx, [rbp+28h]
0x180002d54  xorps   xmm1, xmm1
0x180002d57  cvtsd2ss xmm1, xmm0
0x180002d5b  sar     ebx, 2
0x180002d5e  movaps  xmm2, xmm12
0x180002d62  subss   xmm2, xmm1
0x180002d66  movaps  xmm1, xmm12
0x180002d6a  mulss   xmm2, xmm9
0x180002d6f  movaps  xmm0, xmm2
0x180002d72  subss   xmm1, xmm2
0x180002d76  mulss   xmm0, xmm6
0x180002d7a  movss   dword ptr [rbp+74h], xmm0
0x180002d7f  xorps   xmm0, xmm0
0x180002d82  cvtsi2ss xmm0, ebx
0x180002d86  mulss   xmm1, xmm6
0x180002d8a  mulss   xmm0, xmm11
0x180002d8f  movss   dword ptr [rbp+6Ch], xmm1
0x180002d94  cvtps2pd xmm1, xmm0; Y
0x180002d97  movsd   xmm0, cs:__real@4024000000000000; X
0x180002d9f  call    pow
0x180002da4  xorps   xmm6, xmm6
0x180002da7  cvtsd2ss xmm6, xmm0
0x180002dab  lea     eax, [rbx+rsi]
0x180002dae  xorps   xmm0, xmm0
0x180002db1  cvtsi2ss xmm0, eax
0x180002db5  movaps  xmm1, xmm6
0x180002db8  mulss   xmm1, xmm10
0x180002dbd  movsd   xmm10, cs:__real@4024000000000000
0x180002dc6  mulss   xmm0, xmm11
0x180002dcb  movaps  xmm7, xmm1
0x180002dce  addss   xmm7, xmm12
0x180002dd3  mulss   xmm0, xmm15
0x180002dd8  mulss   xmm7, xmm1
0x180002ddc  addss   xmm7, xmm12
0x180002de1  mulss   xmm7, xmm1
0x180002de5  addss   xmm7, xmm12
0x180002dea  mulss   xmm7, xmm1
0x180002dee  cvtps2pd xmm1, xmm0; Y
0x180002df1  movaps  xmm0, xmm10; X
0x180002df5  addss   xmm7, xmm12
0x180002dfa  call    pow
0x180002dff  xorps   xmm1, xmm1
0x180002e02  mulss   xmm7, xmm7
0x180002e06  cvtsd2ss xmm1, xmm0
0x180002e0a  movaps  xmm2, xmm12
0x180002e0e  addss   xmm7, xmm8
0x180002e13  subss   xmm2, xmm1
0x180002e17  movaps  xmm1, xmm12
0x180002e1b  mulss   xmm2, xmm9
0x180002e20  subss   xmm1, xmm2
0x180002e24  movaps  xmm0, xmm2
0x180002e27  mulss   xmm0, xmm6
0x180002e2b  mulss   xmm1, xmm6
0x180002e2f  movss   dword ptr [rbp+84h], xmm0
0x180002e37  xorps   xmm0, xmm0
0x180002e3a  movss   dword ptr [rbp+7Ch], xmm1
0x180002e3f  cvtps2pd xmm1, xmm7
0x180002e42  ucomisd xmm0, xmm1
0x180002e46  ja      short loc_180002E4E
0x180002e48  sqrtpd  xmm0, xmm1
0x180002e4c  jmp     short loc_180002E56
0x180002e4e  movaps  xmm0, xmm1; X
0x180002e51  call    sqrt
0x180002e56  mulss   xmm13, cs:__real@3d4ccccd
0x180002e5f  xorps   xmm8, xmm8
0x180002e63  cvtsd2ss xmm8, xmm0
0x180002e68  cvtps2pd xmm1, xmm13; Y
0x180002e6c  movaps  xmm0, xmm10; X
0x180002e70  movss   dword ptr [rbp+8Ch], xmm8
0x180002e79  call    pow
0x180002e7e  mulss   xmm14, cs:__real@3dcccccd
0x180002e87  xorps   xmm6, xmm6
0x180002e8a  cvtsd2ss xmm6, xmm0
0x180002e8e  cvtps2pd xmm1, xmm14; Y
0x180002e92  movaps  xmm0, xmm10; X
0x180002e96  call    pow
0x180002e9b  xorps   xmm7, xmm7
0x180002e9e  cvtsd2ss xmm7, xmm0
0x180002ea2  xorps   xmm0, xmm0
0x180002ea5  subss   xmm12, xmm7
0x180002eaa  cvtps2pd xmm1, xmm12
0x180002eae  ucomisd xmm0, xmm1
0x180002eb2  ja      short loc_180002EBA
0x180002eb4  sqrtpd  xmm0, xmm1
0x180002eb8  jmp     short loc_180002EC2
0x180002eba  movaps  xmm0, xmm1; X
0x180002ebd  call    sqrt
0x180002ec2  cvtsd2ss xmm0, xmm0
0x180002ec6  xorps   xmm1, xmm1
0x180002ec9  mulss   xmm0, xmm6
0x180002ecd  movss   dword ptr [rbp+0Ch], xmm0
0x180002ed2  cvtps2pd xmm0, xmm7; X
0x180002ed5  ucomisd xmm1, xmm0
0x180002ed9  ja      short loc_180002EE1
0x180002edb  sqrtpd  xmm0, xmm0
0x180002edf  jmp     short loc_180002EE6
0x180002ee1  call    sqrt
0x180002ee6  xorps   xmm1, xmm1
0x180002ee9  mov     rcx, rbp
0x180002eec  cvtsd2ss xmm1, xmm0
0x180002ef0  movss   xmm0, cs:__real@40800000
0x180002ef8  divss   xmm0, xmm8
0x180002efd  mulss   xmm0, xmm6
0x180002f01  mulss   xmm1, xmm0
0x180002f05  movss   dword ptr [rbp+14h], xmm1
0x180002f0a  movaps  xmm13, [rsp+0E8h+var_A8]
0x180002f10  lea     r11, [rsp+0E8h+var_20]
0x180002f18  movaps  xmm6, xmmword ptr [r11-18h]
0x180002f1d  movaps  xmm7, xmmword ptr [r11-28h]
0x180002f22  movaps  xmm8, xmmword ptr [r11-38h]
0x180002f27  movaps  xmm9, xmmword ptr [r11-48h]
0x180002f2c  movaps  xmm10, xmmword ptr [r11-58h]
0x180002f31  movaps  xmm11, xmmword ptr [r11-68h]
0x180002f36  movaps  xmm12, xmmword ptr [r11-78h]
0x180002f3b  movaps  xmm14, [rsp+0E8h+var_B8]
0x180002f41  movaps  xmm15, [rsp+0E8h+var_C8]
0x180002f47  mov     rsp, r11
0x180002f4a  pop     rdi
0x180002f4b  pop     rsi
0x180002f4c  pop     rbp
0x180002f4d  pop     rbx
  ... truncated ...
```
