# III_process_stereo_ms

- ea: `0x18000c5f0`
- end: `0x18000c987`
- name: `III_process_stereo_ms`
- size: `919`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c990`
- `0x18000cc80`
- `0x18000d370`

## callees

- `0x18000c5f0`

## pseudocode

```c
void __fastcall III_process_stereo_ms(__int64 a1, __int64 a2, int a3, int a4, int a5)
{
  __int64 v6; // rdi
  int v7; // r11d
  double v8; // xmm4_8
  __int64 v9; // rax
  __int64 v10; // xmm2_8
  __int64 v11; // xmm3_8
  __int64 v12; // rax
  float v13; // xmm2_4
  float v14; // xmm0_4
  float v15; // xmm2_4
  float v16; // xmm0_4
  float v17; // xmm3_4
  float v18; // xmm0_4
  float v19; // xmm2_4
  float v20; // xmm0_4
  float v21; // xmm2_4
  float v22; // xmm0_4
  float v23; // xmm3_4
  float v24; // xmm0_4
  float v25; // xmm2_4
  float v26; // xmm0_4
  float v27; // xmm2_4
  float v28; // xmm0_4
  float v29; // xmm3_4
  float v30; // xmm0_4
  float v31; // xmm2_4
  float v32; // xmm0_4
  __int64 v33; // rax
  float v34; // xmm2_4
  float v35; // xmm0_4
  float v36; // xmm2_4
  float v37; // xmm0_4
  double v38; // xmm3_8
  int v39; // ecx
  __int64 v40; // rax
  __int64 v41; // rax
  double v42; // xmm1_8
  float v43; // xmm0_4
  float v44; // xmm0_4
  float v45; // xmm0_4
  __int64 v46; // rax

  if ( a5 )
  {
    if ( a3 < a4 )
    {
      if ( (unsigned int)(a4 - a3) < 8 )
        goto LABEL_19;
      *(_QWORD *)&v38 = _mm_load_si128((const __m128i *)&_xmm).m128i_u64[0];
      v39 = a4 - (a4 - a3) % 8;
      do
      {
        v40 = a3;
        a3 += 8;
        *(double *)(a1 + 4 * v40) = COERCE_FLOAT(*(_QWORD *)(a1 + 4 * v40)) * v38;
        *(double *)(a1 + 4 * v40 + 8) = COERCE_FLOAT(*(_QWORD *)(a1 + 4 * v40 + 8)) * v38;
        *(double *)(a1 + 4 * v40 + 16) = COERCE_FLOAT(*(_QWORD *)(a1 + 4 * v40 + 16)) * v38;
        *(double *)(a1 + 4 * v40 + 24) = *(float *)(a1 + 4 * v40 + 24) * v38;
      }
      while ( a3 < v39 );
      if ( a3 < a4 )
      {
LABEL_19:
        if ( a4 - a3 < 4 )
          goto LABEL_25;
        do
        {
          v41 = a3;
          a3 += 4;
          v42 = *(float *)(a1 + 4 * v41 + 4) * 0.7071067811865476;
          v43 = *(float *)(a1 + 4 * v41) * 0.7071067811865476;
          *(float *)(a1 + 4 * v41) = v43;
          v44 = v42;
          LODWORD(v42) = *(_DWORD *)(a1 + 4 * v41 + 8);
          *(float *)(a1 + 4 * v41 + 4) = v44;
          v45 = *(float *)&v42 * 0.7071067811865476;
          LODWORD(v42) = *(_DWORD *)(a1 + 4 * v41 + 12);
          *(float *)(a1 + 4 * v41 + 8) = v45;
          *(float *)(a1 + 4 * v41 + 12) = *(float *)&v42 * 0.7071067811865476;
        }
        while ( a3 < a4 - 3 );
        if ( a3 < a4 )
        {
LABEL_25:
          do
          {
            v46 = a3++;
            *(float *)(a1 + 4 * v46) = *(float *)(a1 + 4 * v46) * 0.7071067811865476;
          }
          while ( a3 < a4 );
        }
      }
    }
  }
  else if ( a3 < a4 )
  {
    if ( (unsigned int)(a4 - a3) < 2 )
      goto LABEL_11;
    v6 = a4 - 1;
    if ( a1 + 4LL * a3 <= (unsigned __int64)(a2 + 4 * v6) && a1 + 4 * v6 >= (unsigned __int64)(a2 + 4LL * a3) )
      goto LABEL_11;
    v7 = (a4 - a3) % 2;
    *(_QWORD *)&v8 = _mm_load_si128((const __m128i *)&_xmm).m128i_u64[0];
    do
    {
      v9 = a3;
      a3 += 2;
      v10 = *(_QWORD *)(a2 + 4 * v9);
      v11 = *(_QWORD *)(a1 + 4 * v9);
      *(double *)(a2 + 4 * v9) = (float)(*(float *)&v11 - *(float *)&v10) * v8;
      *(double *)(a1 + 4 * v9) = (float)(*(float *)&v10 + *(float *)&v11) * v8;
    }
    while ( a3 < a4 - v7 );
    if ( a3 < a4 )
    {
LABEL_11:
      if ( a4 - a3 < 4 )
        goto LABEL_26;
      do
      {
        v12 = a3;
        a3 += 4;
        v13 = *(float *)(a2 + 4 * v12);
        v14 = *(float *)(a1 + 4 * v12) - v13;
        v15 = v13 + *(float *)(a1 + 4 * v12);
        v16 = v14 * 0.7071067811865476;
        *(float *)(a2 + 4 * v12) = v16;
        v17 = *(float *)(a1 + 4 * v12 + 4);
        v18 = v15 * 0.7071067811865476;
        *(float *)(a1 + 4 * v12) = v18;
        v19 = *(float *)(a2 + 4 * v12 + 4);
        v20 = v17 - v19;
        v21 = v19 + v17;
        v22 = v20 * 0.7071067811865476;
        *(float *)(a2 + 4 * v12 + 4) = v22;
        v23 = *(float *)(a1 + 4 * v12 + 8);
        v24 = v21 * 0.7071067811865476;
        *(float *)(a1 + 4 * v12 + 4) = v24;
        v25 = *(float *)(a2 + 4 * v12 + 8);
        v26 = v23 - v25;
        v27 = v25 + v23;
        v28 = v26 * 0.7071067811865476;
        *(float *)(a2 + 4 * v12 + 8) = v28;
        v29 = *(float *)(a1 + 4 * v12 + 12);
        v30 = v27 * 0.7071067811865476;
        *(float *)(a1 + 4 * v12 + 8) = v30;
        v31 = *(float *)(a2 + 4 * v12 + 12);
        v32 = (float)(v29 - v31) * 0.7071067811865476;
        *(float *)(a2 + 4 * v12 + 12) = v32;
        *(float *)(a1 + 4 * v12 + 12) = (float)(v31 + v29) * 0.7071067811865476;
      }
      while ( a3 < a4 - 3 );
      if ( a3 < a4 )
      {
LABEL_26:
        do
        {
          v33 = a3++;
          v34 = *(float *)(a2 + 4 * v33);
          v35 = *(float *)(a1 + 4 * v33) - v34;
          v36 = v34 + *(float *)(a1 + 4 * v33);
          v37 = v35 * 0.7071067811865476;
          *(float *)(a2 + 4 * v33) = v37;
          *(float *)(a1 + 4 * v33) = v36 * 0.7071067811865476;
        }
        while ( a3 < a4 );
      }
    }
  }
}

```

## disassembly

```asm
0x18000c5f0  sub     rsp, 8
0x18000c5f4  cmp     [rsp+8+arg_20], 0
0x18000c5f9  mov     r10, rcx
0x18000c5fc  jnz     loc_18000C830
0x18000c602  cmp     r8d, r9d
0x18000c605  jge     loc_18000C82B
0x18000c60b  mov     r11d, r9d
0x18000c60e  mov     [rsp+8+arg_0], rbx
0x18000c613  sub     r11d, r8d
0x18000c616  mov     [rsp+8+var_8], rdi
0x18000c61a  cmp     r11d, 2
0x18000c61e  jb      loc_18000C6BA
0x18000c624  lea     eax, [r9-1]
0x18000c628  movsxd  rbx, r8d
0x18000c62b  movsxd  rdi, eax
0x18000c62e  lea     rcx, [rcx+rbx*4]
0x18000c632  lea     rax, [rdx+rdi*4]
0x18000c636  cmp     rcx, rax
0x18000c639  ja      short loc_18000C648
0x18000c63b  lea     rcx, [rdx+rbx*4]
0x18000c63f  lea     rax, [r10+rdi*4]
0x18000c643  cmp     rax, rcx
0x18000c646  jnb     short loc_18000C6BA
0x18000c648  and     r11d, 80000001h
0x18000c64f  jge     short loc_18000C65B
0x18000c651  dec     r11d
0x18000c654  or      r11d, 0FFFFFFFEh
0x18000c658  inc     r11d
0x18000c65b  mov     ecx, r9d
0x18000c65e  sub     ecx, r11d
0x18000c661  movdqa  xmm4, cs:__xmm@3fe6a09e667f3bcd3fe6a09e667f3bcd
0x18000c669  nop     dword ptr [rax+00000000h]
0x18000c670  movsxd  rax, r8d
0x18000c673  add     r8d, 2
0x18000c677  movsd   xmm0, qword ptr [r10+rax*4]
0x18000c67d  movsd   xmm2, qword ptr [rdx+rax*4]
0x18000c682  movaps  xmm3, xmm0
0x18000c685  subps   xmm0, xmm2
0x18000c688  addps   xmm2, xmm3
0x18000c68b  cvtps2pd xmm1, xmm0
0x18000c68e  mulpd   xmm1, xmm4
0x18000c692  cvtpd2ps xmm0, xmm1
0x18000c696  movsd   qword ptr [rdx+rax*4], xmm0
0x18000c69b  cvtps2pd xmm0, xmm2
0x18000c69e  mulpd   xmm0, xmm4
0x18000c6a2  cvtpd2ps xmm0, xmm0
0x18000c6a6  movsd   qword ptr [r10+rax*4], xmm0
0x18000c6ac  cmp     r8d, ecx
0x18000c6af  jl      short loc_18000C670
0x18000c6b1  cmp     r8d, r9d
0x18000c6b4  jge     loc_18000C822
0x18000c6ba  movsd   xmm4, cs:__real@3fe6a09e667f3bcd
0x18000c6c2  mov     eax, r9d
0x18000c6c5  sub     eax, r8d
0x18000c6c8  cmp     eax, 4
0x18000c6cb  jl      loc_18000C7E0
0x18000c6d1  lea     ecx, [r9-3]
0x18000c6d5  nop     word ptr [rax+rax+00000000h]
0x18000c6e0  movsxd  rax, r8d
0x18000c6e3  add     r8d, 4
0x18000c6e7  movss   xmm2, dword ptr [rdx+rax*4]
0x18000c6ec  movss   xmm3, dword ptr [r10+rax*4]
0x18000c6f2  movaps  xmm0, xmm3
0x18000c6f5  subss   xmm0, xmm2
0x18000c6f9  addss   xmm2, xmm3
0x18000c6fd  cvtps2pd xmm1, xmm0
0x18000c700  mulsd   xmm1, xmm4
0x18000c704  cvtpd2ps xmm0, xmm1
0x18000c708  movss   dword ptr [rdx+rax*4], xmm0
0x18000c70d  movss   xmm3, dword ptr [r10+rax*4+4]
0x18000c714  cvtps2pd xmm0, xmm2
0x18000c717  mulsd   xmm0, xmm4
0x18000c71b  cvtpd2ps xmm0, xmm0
0x18000c71f  movss   dword ptr [r10+rax*4], xmm0
0x18000c725  movaps  xmm0, xmm3
0x18000c728  movss   xmm2, dword ptr [rdx+rax*4+4]
0x18000c72e  subss   xmm0, xmm2
0x18000c732  addss   xmm2, xmm3
0x18000c736  cvtps2pd xmm1, xmm0
0x18000c739  mulsd   xmm1, xmm4
0x18000c73d  cvtpd2ps xmm0, xmm1
0x18000c741  movss   dword ptr [rdx+rax*4+4], xmm0
0x18000c747  movss   xmm3, dword ptr [r10+rax*4+8]
0x18000c74e  cvtps2pd xmm0, xmm2
0x18000c751  mulsd   xmm0, xmm4
0x18000c755  cvtpd2ps xmm0, xmm0
0x18000c759  movss   dword ptr [r10+rax*4+4], xmm0
0x18000c760  movaps  xmm0, xmm3
0x18000c763  movss   xmm2, dword ptr [rdx+rax*4+8]
0x18000c769  subss   xmm0, xmm2
0x18000c76d  addss   xmm2, xmm3
0x18000c771  cvtps2pd xmm1, xmm0
0x18000c774  mulsd   xmm1, xmm4
0x18000c778  cvtpd2ps xmm0, xmm1
0x18000c77c  movss   dword ptr [rdx+rax*4+8], xmm0
0x18000c782  movss   xmm3, dword ptr [r10+rax*4+0Ch]
0x18000c789  cvtps2pd xmm0, xmm2
0x18000c78c  mulsd   xmm0, xmm4
0x18000c790  cvtpd2ps xmm0, xmm0
0x18000c794  movss   dword ptr [r10+rax*4+8], xmm0
0x18000c79b  movaps  xmm0, xmm3
0x18000c79e  movss   xmm2, dword ptr [rdx+rax*4+0Ch]
0x18000c7a4  subss   xmm0, xmm2
0x18000c7a8  addss   xmm2, xmm3
0x18000c7ac  cvtps2pd xmm1, xmm0
0x18000c7af  mulsd   xmm1, xmm4
0x18000c7b3  cvtpd2ps xmm0, xmm1
0x18000c7b7  movss   dword ptr [rdx+rax*4+0Ch], xmm0
0x18000c7bd  cvtps2pd xmm0, xmm2
0x18000c7c0  mulsd   xmm0, xmm4
0x18000c7c4  cvtpd2ps xmm0, xmm0
0x18000c7c8  movss   dword ptr [r10+rax*4+0Ch], xmm0
0x18000c7cf  cmp     r8d, ecx
0x18000c7d2  jl      loc_18000C6E0
0x18000c7d8  cmp     r8d, r9d
0x18000c7db  jge     short loc_18000C822
0x18000c7dd  nop     dword ptr [rax]
0x18000c7e0  movsxd  rax, r8d
0x18000c7e3  inc     r8d
0x18000c7e6  movss   xmm2, dword ptr [rdx+rax*4]
0x18000c7eb  movss   xmm3, dword ptr [r10+rax*4]
0x18000c7f1  movaps  xmm0, xmm3
0x18000c7f4  subss   xmm0, xmm2
0x18000c7f8  addss   xmm2, xmm3
0x18000c7fc  cvtps2pd xmm1, xmm0
0x18000c7ff  mulsd   xmm1, xmm4
0x18000c803  cvtpd2ps xmm0, xmm1
0x18000c807  movss   dword ptr [rdx+rax*4], xmm0
0x18000c80c  cvtps2pd xmm0, xmm2
0x18000c80f  mulsd   xmm0, xmm4
0x18000c813  cvtpd2ps xmm0, xmm0
0x18000c817  movss   dword ptr [r10+rax*4], xmm0
0x18000c81d  cmp     r8d, r9d
0x18000c820  jl      short loc_18000C7E0
0x18000c822  mov     rbx, [rsp+8+arg_0]
0x18000c827  mov     rdi, [rsp+8+var_8]
0x18000c82b  add     rsp, 8
0x18000c82f  retn
0x18000c830  cmp     r8d, r9d
0x18000c833  jge     short loc_18000C82B
0x18000c835  mov     eax, r9d
0x18000c838  sub     eax, r8d
0x18000c83b  cmp     eax, 8
0x18000c83e  jb      loc_18000C8C7
0x18000c844  and     eax, 80000007h
0x18000c849  jge     short loc_18000C852
0x18000c84b  dec     eax
0x18000c84d  or      eax, 0FFFFFFF8h
0x18000c850  inc     eax
0x18000c852  movdqa  xmm3, cs:__xmm@3fe6a09e667f3bcd3fe6a09e667f3bcd
0x18000c85a  mov     ecx, r9d
0x18000c85d  sub     ecx, eax
0x18000c85f  nop
0x18000c860  movsxd  rax, r8d
0x18000c863  add     r8d, 8
0x18000c867  cvtps2pd xmm2, qword ptr [r10+rax*4]
0x18000c86c  mulpd   xmm2, xmm3
0x18000c870  cvtpd2ps xmm0, xmm2
0x18000c874  movsd   qword ptr [r10+rax*4], xmm0
0x18000c87a  cvtps2pd xmm2, qword ptr [r10+rax*4+8]
0x18000c880  mulpd   xmm2, xmm3
0x18000c884  cvtpd2ps xmm0, xmm2
0x18000c888  movsd   qword ptr [r10+rax*4+8], xmm0
0x18000c88f  cvtps2pd xmm2, qword ptr [r10+rax*4+10h]
0x18000c895  mulpd   xmm2, xmm3
0x18000c899  cvtpd2ps xmm0, xmm2
0x18000c89d  movsd   qword ptr [r10+rax*4+10h], xmm0
0x18000c8a4  cvtps2pd xmm2, qword ptr [r10+rax*4+18h]
0x18000c8aa  mulpd   xmm2, xmm3
0x18000c8ae  cvtpd2ps xmm0, xmm2
0x18000c8b2  movsd   qword ptr [r10+rax*4+18h], xmm0
0x18000c8b9  cmp     r8d, ecx
0x18000c8bc  jl      short loc_18000C860
0x18000c8be  cmp     r8d, r9d
0x18000c8c1  jge     loc_18000C82B
0x18000c8c7  movsd   xmm2, cs:__real@3fe6a09e667f3bcd
0x18000c8cf  mov     eax, r9d
0x18000c8d2  sub     eax, r8d
0x18000c8d5  cmp     eax, 4
0x18000c8d8  jl      loc_18000C960
0x18000c8de  lea     ecx, [r9-3]
0x18000c8e2  movsxd  rax, r8d
0x18000c8e5  add     r8d, 4
0x18000c8e9  movss   xmm0, dword ptr [r10+rax*4]
0x18000c8ef  movss   xmm1, dword ptr [r10+rax*4+4]
0x18000c8f6  cvtps2pd xmm1, xmm1
0x18000c8f9  cvtps2pd xmm0, xmm0
0x18000c8fc  mulsd   xmm1, xmm2
0x18000c900  mulsd   xmm0, xmm2
0x18000c904  cvtpd2ps xmm0, xmm0
0x18000c908  movss   dword ptr [r10+rax*4], xmm0
0x18000c90e  cvtpd2ps xmm0, xmm1
0x18000c912  movss   xmm1, dword ptr [r10+rax*4+8]
0x18000c919  movss   dword ptr [r10+rax*4+4], xmm0
0x18000c920  cvtps2pd xmm1, xmm1
0x18000c923  mulsd   xmm1, xmm2
0x18000c927  cvtpd2ps xmm0, xmm1
0x18000c92b  movss   xmm1, dword ptr [r10+rax*4+0Ch]
0x18000c932  movss   dword ptr [r10+rax*4+8], xmm0
0x18000c939  cvtps2pd xmm1, xmm1
0x18000c93c  mulsd   xmm1, xmm2
0x18000c940  cvtpd2ps xmm0, xmm1
0x18000c944  movss   dword ptr [r10+rax*4+0Ch], xmm0
0x18000c94b  cmp     r8d, ecx
0x18000c94e  jl      short loc_18000C8E2
0x18000c950  cmp     r8d, r9d
0x18000c953  jge     loc_18000C82B
0x18000c959  nop     dword ptr [rax+00000000h]
0x18000c960  movsxd  rax, r8d
0x18000c963  inc     r8d
0x18000c966  movss   xmm0, dword ptr [r10+rax*4]
0x18000c96c  cvtps2pd xmm0, xmm0
0x18000c96f  mulsd   xmm0, xmm2
0x18000c973  cvtpd2ps xmm0, xmm0
0x18000c977  movss   dword ptr [r10+rax*4], xmm0
0x18000c97d  cmp     r8d, r9d
0x18000c980  jl      short loc_18000C960
0x18000c982  add     rsp, 8
0x18000c986  retn
```
