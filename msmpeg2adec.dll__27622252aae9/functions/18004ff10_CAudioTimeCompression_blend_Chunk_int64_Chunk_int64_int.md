# CAudioTimeCompression::blend(Chunk *,__int64,Chunk *,__int64,int)

- ea: `0x18004ff10`
- end: `0x1800504e6`
- name: `?blend@CAudioTimeCompression@@IEAAXPEAVChunk@@_J01H@Z`
- size: `1494`
- prototype: `void __fastcall(CAudioTimeCompression *__hidden this, struct Chunk *, __int64, struct Chunk *, __int64, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18004f4c0`

## callees

- `0x18004ff10`

## pseudocode

```c
void __fastcall CAudioTimeCompression::blend(
        CAudioTimeCompression *this,
        struct Chunk *a2,
        __int64 a3,
        struct Chunk *a4,
        __int64 a5,
        int a6)
{
  __int64 v6; // r8
  __int64 v7; // r11
  float *v9; // r10
  __m128 *v10; // rdx
  __int64 v11; // r8
  __m128 *v12; // rcx
  int v13; // r9d
  __m128 v14; // xmm6
  int v15; // eax
  __m128 v16; // xmm3
  __m128 v17; // xmm1
  __m128 v18; // xmm3
  __m128 v19; // xmm0
  int v20; // eax
  __m128 v21; // xmm3
  __m128 v22; // xmm1
  __m128 v23; // xmm2
  __m128 v24; // xmm0
  __m128 v25; // xmm1
  __m128 v26; // xmm2
  __m128 v27; // xmm0
  __m128 v28; // xmm1
  __m128 v29; // xmm2
  __m128 v30; // xmm0
  __m128 v31; // xmm1
  __m128 v32; // xmm2
  __m128 v33; // xmm0
  __m128 v34; // xmm1
  __m128 v35; // xmm3
  __m128 v36; // xmm0
  int v37; // r8d
  __m128 v38; // xmm4
  __int64 v39; // rax
  char *v40; // rbx
  __m128 v41; // xmm5
  __m128 v42; // xmm0
  __m128 v43; // xmm2
  __m128 v44; // xmm0
  __m128 v45; // xmm2
  __m128 v46; // xmm0
  float v47; // xmm2_4
  float v48; // xmm0_4
  int v49; // ebx
  __m128 si128; // xmm5
  int v51; // r8d
  __m128 v52; // xmm2
  char *v53; // r9
  __m128 v54; // xmm4
  __m128 v55; // xmm0
  __m128 v56; // xmm1
  __m128 v57; // xmm0
  __m128 v58; // xmm1
  __m128 v59; // xmm0
  float v60; // xmm2_4
  float v61; // xmm0_4

  v6 = a3 - *(_QWORD *)a2;
  v7 = *((unsigned __int16 *)this + 3);
  v9 = (float *)*((_QWORD *)this + 14);
  if ( v6 < 0 || v6 >= *((int *)a2 + 2) )
    v10 = 0;
  else
    v10 = (__m128 *)(*((_QWORD *)a2 + 3) + v6 * *((int *)a2 + 3));
  v11 = a5 - *(_QWORD *)a4;
  if ( v11 < 0 || v11 >= *((int *)a4 + 2) )
    v12 = 0;
  else
    v12 = (__m128 *)(*((_QWORD *)a4 + 3) + v11 * *((int *)a4 + 3));
  if ( !*(_DWORD *)this || ((unsigned __int8)v12 & 0xF) != 0 )
  {
    v49 = 0;
    if ( a6 > 0 )
    {
      si128 = (__m128)_mm_load_si128((const __m128i *)&_xmm);
      do
      {
        v51 = 0;
        if ( (unsigned int)v7 >= 0x10 )
        {
          v52 = _mm_shuffle_ps((__m128)*(unsigned int *)v9, (__m128)*(unsigned int *)v9, 0);
          v53 = &v12->m128_i8[4 * v7 - 4];
          if ( (v12 > (__m128 *)&v10->m128_f32[v7 - 1] || v53 < (char *)v10) && (v12 > (__m128 *)v9 || v53 < (char *)v9) )
          {
            v54 = _mm_sub_ps(si128, v52);
            do
            {
              v51 += 16;
              v55 = v10[1];
              *v12 = _mm_add_ps(_mm_mul_ps(v52, *v10), _mm_mul_ps(*v12, v54));
              v56 = _mm_add_ps(_mm_mul_ps(v52, v55), _mm_mul_ps(v12[1], v54));
              v57 = v10[2];
              v12[1] = v56;
              v58 = _mm_add_ps(_mm_mul_ps(v52, v57), _mm_mul_ps(v12[2], v54));
              v59 = v10[3];
              v10 += 4;
              v12[2] = v58;
              v12[3] = _mm_add_ps(_mm_mul_ps(v52, v59), _mm_mul_ps(v12[3], v54));
              v12 += 4;
            }
            while ( v51 < (v7 & 0xFFFFFFF0) );
          }
        }
        if ( v51 < (int)v7 )
        {
          if ( (int)v7 - v51 < 4 )
            goto LABEL_51;
          do
          {
            v51 += 4;
            v12->m128_f32[0] = (float)((float)(1.0 - *v9) * v12->m128_f32[0]) + (float)(*v9 * v10->m128_f32[0]);
            v12->m128_f32[1] = (float)(*v9 * v10->m128_f32[1]) + (float)((float)(1.0 - *v9) * v12->m128_f32[1]);
            v12->m128_f32[2] = (float)(*v9 * v10->m128_f32[2]) + (float)((float)(1.0 - *v9) * v12->m128_f32[2]);
            v60 = *v9 * v10->m128_f32[3];
            ++v10;
            v12->m128_f32[3] = v60 + (float)((float)(1.0 - *v9) * v12->m128_f32[3]);
            ++v12;
          }
          while ( v51 < (int)v7 - 3 );
          if ( v51 < (int)v7 )
          {
LABEL_51:
            do
            {
              ++v51;
              v61 = *v9 * v10->m128_f32[0];
              v10 = (__m128 *)((char *)v10 + 4);
              v12->m128_f32[0] = (float)((float)(1.0 - *v9) * v12->m128_f32[0]) + v61;
              v12 = (__m128 *)((char *)v12 + 4);
            }
            while ( v51 < (int)v7 );
          }
        }
        ++v9;
        ++v49;
      }
      while ( v49 < a6 );
    }
  }
  else
  {
    v13 = 0;
    v14 = (__m128)_mm_load_si128((const __m128i *)&_xmm);
    if ( (_DWORD)v7 == 2 )
    {
      if ( a6 > 3 )
      {
        v15 = 3;
        do
        {
          v16 = *(__m128 *)v9;
          v9 += 4;
          v15 += 4;
          v13 += 4;
          v17 = _mm_shuffle_ps(v16, v16, 80);
          v18 = _mm_shuffle_ps(v16, v16, 250);
          *v12 = _mm_add_ps(_mm_mul_ps(_mm_sub_ps(v14, v17), *v12), _mm_mul_ps(*v10, v17));
          v19 = v10[1];
          v10 += 2;
          v12[1] = _mm_add_ps(_mm_mul_ps(_mm_sub_ps(v14, v18), v12[1]), _mm_mul_ps(v18, v19));
          v12 += 2;
        }
        while ( v15 < a6 );
      }
    }
    else if ( a6 > 3 )
    {
      v20 = 3;
      do
      {
        v21 = *(__m128 *)v9;
        v9 += 4;
        v20 += 4;
        v13 += 4;
        v22 = _mm_shuffle_ps(v21, v21, 0);
        v23 = _mm_sub_ps(v14, v22);
        v24 = _mm_mul_ps(*v10, v22);
        v25 = _mm_shuffle_ps(v21, v21, 80);
        *v12 = _mm_add_ps(_mm_mul_ps(v23, *v12), v24);
        v26 = _mm_sub_ps(v14, v25);
        v27 = _mm_mul_ps(v10[1], v25);
        v28 = _mm_shuffle_ps(v21, v21, 85);
        v12[1] = _mm_add_ps(_mm_mul_ps(v26, v12[1]), v27);
        v29 = _mm_sub_ps(v14, v28);
        v30 = _mm_mul_ps(v10[2], v28);
        v31 = _mm_shuffle_ps(v21, v21, 170);
        v12[2] = _mm_add_ps(_mm_mul_ps(v29, v12[2]), v30);
        v32 = _mm_sub_ps(v14, v31);
        v33 = _mm_mul_ps(v10[3], v31);
        v34 = _mm_shuffle_ps(v21, v21, 250);
        v35 = _mm_shuffle_ps(v21, v21, 255);
        v12[3] = _mm_add_ps(_mm_mul_ps(v32, v12[3]), v33);
        v12[4] = _mm_add_ps(_mm_mul_ps(_mm_sub_ps(v14, v34), v12[4]), _mm_mul_ps(v10[4], v34));
        v36 = v10[5];
        v10 += 6;
        v12[5] = _mm_add_ps(_mm_mul_ps(_mm_sub_ps(v14, v35), v12[5]), _mm_mul_ps(v36, v35));
        v12 += 6;
      }
      while ( v20 < a6 );
    }
    for ( ; v13 < a6; ++v13 )
    {
      v37 = 0;
      if ( (unsigned int)v7 >= 0x10 )
      {
        v38 = _mm_shuffle_ps((__m128)*(unsigned int *)v9, (__m128)*(unsigned int *)v9, 0);
        v39 = (int)v7 - 1LL;
        v40 = &v12->m128_i8[4 * v39];
        if ( (v12 > (__m128 *)&v10->m128_f32[v39] || v40 < (char *)v10) && (v12 > (__m128 *)v9 || v40 < (char *)v9) )
        {
          v41 = _mm_sub_ps(v14, v38);
          do
          {
            v37 += 16;
            v42 = v10[1];
            *v12 = _mm_add_ps(_mm_mul_ps(*v10, v38), _mm_mul_ps(v41, *v12));
            v43 = _mm_mul_ps(v38, v42);
            v44 = v10[2];
            v12[1] = _mm_add_ps(v43, _mm_mul_ps(v41, v12[1]));
            v45 = _mm_mul_ps(v38, v44);
            v46 = v10[3];
            v10 += 4;
            v12[2] = _mm_add_ps(v45, _mm_mul_ps(v41, v12[2]));
            v12[3] = _mm_add_ps(_mm_mul_ps(v38, v46), _mm_mul_ps(v41, v12[3]));
            v12 += 4;
          }
          while ( v37 < (v7 & 0xFFFFFFF0) );
        }
      }
      if ( v37 < (int)v7 )
      {
        if ( (int)v7 - v37 < 4 )
          goto LABEL_52;
        do
        {
          v37 += 4;
          v12->m128_f32[0] = (float)((float)(1.0 - *v9) * v12->m128_f32[0]) + (float)(*v9 * v10->m128_f32[0]);
          v12->m128_f32[1] = (float)(*v9 * v10->m128_f32[1]) + (float)((float)(1.0 - *v9) * v12->m128_f32[1]);
          v12->m128_f32[2] = (float)(*v9 * v10->m128_f32[2]) + (float)((float)(1.0 - *v9) * v12->m128_f32[2]);
          v47 = *v9 * v10->m128_f32[3];
          ++v10;
          v12->m128_f32[3] = v47 + (float)((float)(1.0 - *v9) * v12->m128_f32[3]);
          ++v12;
        }
        while ( v37 < (int)v7 - 3 );
        if ( v37 < (int)v7 )
        {
LABEL_52:
          do
          {
            ++v37;
            v48 = *v9 * v10->m128_f32[0];
            v10 = (__m128 *)((char *)v10 + 4);
            v12->m128_f32[0] = (float)((float)(1.0 - *v9) * v12->m128_f32[0]) + v48;
            v12 = (__m128 *)((char *)v12 + 4);
          }
          while ( v37 < (int)v7 );
        }
      }
      ++v9;
    }
  }
}

```

## disassembly

```asm
0x18004ff10  mov     [rsp+arg_0], rbx
0x18004ff15  push    rdi
0x18004ff16  sub     rsp, 10h
0x18004ff1a  sub     r8, [rdx]
0x18004ff1d  mov     rbx, rdx
0x18004ff20  movzx   r11d, word ptr [rcx+6]
0x18004ff25  mov     rdi, rcx
0x18004ff28  mov     r10, [rcx+70h]
0x18004ff2c  js      short loc_18004FF45
0x18004ff2e  movsxd  rax, dword ptr [rdx+8]
0x18004ff32  cmp     r8, rax
0x18004ff35  jge     short loc_18004FF45
0x18004ff37  movsxd  rdx, dword ptr [rdx+0Ch]
0x18004ff3b  imul    rdx, r8
0x18004ff3f  add     rdx, [rbx+18h]
0x18004ff43  jmp     short loc_18004FF47
0x18004ff45  xor     edx, edx
0x18004ff47  mov     r8, [rsp+18h+arg_20]
0x18004ff4c  sub     r8, [r9]
0x18004ff4f  js      short loc_18004FF68
0x18004ff51  movsxd  rax, dword ptr [r9+8]
0x18004ff55  cmp     r8, rax
0x18004ff58  jge     short loc_18004FF68
0x18004ff5a  movsxd  rcx, dword ptr [r9+0Ch]
0x18004ff5e  imul    rcx, r8
0x18004ff62  add     rcx, [r9+18h]
0x18004ff66  jmp     short loc_18004FF6A
0x18004ff68  xor     ecx, ecx
0x18004ff6a  cmp     dword ptr [rdi], 0
0x18004ff6d  jz      loc_1800502EC
0x18004ff73  test    cl, 0Fh
0x18004ff76  jnz     loc_1800502EC
0x18004ff7c  mov     edi, [rsp+18h+arg_28]
0x18004ff80  xor     r9d, r9d
0x18004ff83  movaps  [rsp+18h+var_18], xmm6
0x18004ff87  movdqa  xmm6, cs:__xmm@3f8000003f8000003f8000003f800000
0x18004ff8f  cmp     r11d, 2
0x18004ff93  jnz     short loc_180050008
0x18004ff95  cmp     edi, 3
0x18004ff98  jle     loc_1800500F3
0x18004ff9e  mov     eax, 3
0x18004ffa3  nop     dword ptr [rax+00h]
0x18004ffa7  nop     word ptr [rax+rax+00000000h]
0x18004ffb0  movups  xmm3, xmmword ptr [r10]
0x18004ffb4  movaps  xmm2, xmm6
0x18004ffb7  movups  xmm0, xmmword ptr [rdx]
0x18004ffba  add     r10, 10h
0x18004ffbe  add     eax, 4
0x18004ffc1  movaps  xmm1, xmm3
0x18004ffc4  add     r9d, 4
0x18004ffc8  shufps  xmm1, xmm3, 50h ; 'P'
0x18004ffcc  subps   xmm2, xmm1
0x18004ffcf  mulps   xmm0, xmm1
0x18004ffd2  shufps  xmm3, xmm3, 0FAh
0x18004ffd6  movaps  xmm1, xmm6
0x18004ffd9  subps   xmm1, xmm3
0x18004ffdc  mulps   xmm2, xmmword ptr [rcx]
0x18004ffdf  addps   xmm2, xmm0
0x18004ffe2  movups  xmmword ptr [rcx], xmm2
0x18004ffe5  movups  xmm0, xmmword ptr [rdx+10h]
0x18004ffe9  add     rdx, 20h ; ' '
0x18004ffed  mulps   xmm1, xmmword ptr [rcx+10h]
0x18004fff1  mulps   xmm3, xmm0
0x18004fff4  addps   xmm1, xmm3
0x18004fff7  movups  xmmword ptr [rcx+10h], xmm1
0x18004fffb  add     rcx, 20h ; ' '
0x18004ffff  cmp     eax, edi
0x180050001  jl      short loc_18004FFB0
0x180050003  jmp     loc_1800500F3
0x180050008  cmp     edi, 3
0x18005000b  jle     loc_1800500F3
0x180050011  mov     eax, 3
0x180050016  nop     word ptr [rax+rax+00000000h]
0x180050020  movups  xmm3, xmmword ptr [r10]
0x180050024  movaps  xmm2, xmm6
0x180050027  movups  xmm0, xmmword ptr [rdx]
0x18005002a  add     r10, 10h
0x18005002e  add     eax, 4
0x180050031  movaps  xmm1, xmm3
0x180050034  add     r9d, 4
0x180050038  shufps  xmm1, xmm3, 0
0x18005003c  subps   xmm2, xmm1
0x18005003f  mulps   xmm0, xmm1
0x180050042  movaps  xmm1, xmm3
0x180050045  shufps  xmm1, xmm3, 50h ; 'P'
0x180050049  mulps   xmm2, xmmword ptr [rcx]
0x18005004c  addps   xmm2, xmm0
0x18005004f  movups  xmmword ptr [rcx], xmm2
0x180050052  movaps  xmm2, xmm6
0x180050055  movups  xmm0, xmmword ptr [rdx+10h]
0x180050059  subps   xmm2, xmm1
0x18005005c  mulps   xmm0, xmm1
0x18005005f  movaps  xmm1, xmm3
0x180050062  shufps  xmm1, xmm3, 55h ; 'U'
0x180050066  mulps   xmm2, xmmword ptr [rcx+10h]
0x18005006a  addps   xmm2, xmm0
0x18005006d  movups  xmmword ptr [rcx+10h], xmm2
0x180050071  movaps  xmm2, xmm6
0x180050074  movups  xmm0, xmmword ptr [rdx+20h]
0x180050078  subps   xmm2, xmm1
0x18005007b  mulps   xmm0, xmm1
0x18005007e  movaps  xmm1, xmm3
0x180050081  shufps  xmm1, xmm3, 0AAh
0x180050085  mulps   xmm2, xmmword ptr [rcx+20h]
0x180050089  addps   xmm2, xmm0
0x18005008c  movups  xmmword ptr [rcx+20h], xmm2
0x180050090  movaps  xmm2, xmm6
0x180050093  movups  xmm0, xmmword ptr [rdx+30h]
0x180050097  subps   xmm2, xmm1
0x18005009a  mulps   xmm0, xmm1
0x18005009d  movaps  xmm1, xmm3
0x1800500a0  shufps  xmm1, xmm3, 0FAh
0x1800500a4  shufps  xmm3, xmm3, 0FFh
0x1800500a8  mulps   xmm2, xmmword ptr [rcx+30h]
0x1800500ac  addps   xmm2, xmm0
0x1800500af  movups  xmmword ptr [rcx+30h], xmm2
0x1800500b3  movaps  xmm2, xmm6
0x1800500b6  movups  xmm0, xmmword ptr [rdx+40h]
0x1800500ba  subps   xmm2, xmm1
0x1800500bd  mulps   xmm0, xmm1
0x1800500c0  movaps  xmm1, xmm6
0x1800500c3  subps   xmm1, xmm3
0x1800500c6  mulps   xmm2, xmmword ptr [rcx+40h]
0x1800500ca  addps   xmm2, xmm0
0x1800500cd  movups  xmmword ptr [rcx+40h], xmm2
0x1800500d1  movups  xmm0, xmmword ptr [rdx+50h]
0x1800500d5  add     rdx, 60h ; '`'
0x1800500d9  mulps   xmm1, xmmword ptr [rcx+50h]
0x1800500dd  mulps   xmm0, xmm3
0x1800500e0  addps   xmm1, xmm0
0x1800500e3  movups  xmmword ptr [rcx+50h], xmm1
0x1800500e7  add     rcx, 60h ; '`'
0x1800500eb  cmp     eax, edi
0x1800500ed  jl      loc_180050020
0x1800500f3  cmp     r9d, edi
0x1800500f6  jge     loc_1800502DC
0x1800500fc  movss   xmm3, cs:__real@3f800000
0x180050104  xor     r8d, r8d
0x180050107  test    r11d, r11d
0x18005010a  jz      loc_1800501D7
0x180050110  cmp     r11d, 10h
0x180050114  jb      loc_1800501D7
0x18005011a  movss   xmm4, dword ptr [r10]
0x18005011f  movsxd  rax, r11d
0x180050122  shufps  xmm4, xmm4, 0
0x180050126  lea     rbx, [rax-1]
0x18005012a  dec     rax
0x18005012d  lea     rbx, [rcx+rbx*4]
0x180050131  lea     rax, [rdx+rax*4]
0x180050135  cmp     rcx, rax
0x180050138  ja      short loc_180050143
0x18005013a  cmp     rbx, rdx
0x18005013d  jnb     loc_1800501D7
0x180050143  cmp     rcx, r10
0x180050146  ja      short loc_180050151
0x180050148  cmp     rbx, r10
0x18005014b  jnb     loc_1800501D7
0x180050151  mov     eax, r11d
0x180050154  and     eax, 0FFFFFFF0h
0x180050157  movaps  xmm5, xmm6
0x18005015a  subps   xmm5, xmm4
0x18005015d  nop     dword ptr [rax]
0x180050160  movups  xmm0, xmmword ptr [rcx]
0x180050163  add     r8d, 10h
0x180050167  movups  xmm2, xmmword ptr [rdx]
0x18005016a  movaps  xmm1, xmm5
0x18005016d  mulps   xmm1, xmm0
0x180050170  movups  xmm0, xmmword ptr [rdx+10h]
0x180050174  mulps   xmm2, xmm4
0x180050177  addps   xmm2, xmm1
0x18005017a  movaps  xmm1, xmm5
0x18005017d  movups  xmmword ptr [rcx], xmm2
0x180050180  movaps  xmm2, xmm4
0x180050183  mulps   xmm2, xmm0
0x180050186  movups  xmm0, xmmword ptr [rcx+10h]
0x18005018a  mulps   xmm1, xmm0
0x18005018d  movups  xmm0, xmmword ptr [rdx+20h]
0x180050191  addps   xmm2, xmm1
0x180050194  movaps  xmm1, xmm5
0x180050197  movups  xmmword ptr [rcx+10h], xmm2
0x18005019b  movaps  xmm2, xmm4
0x18005019e  mulps   xmm2, xmm0
0x1800501a1  movups  xmm0, xmmword ptr [rcx+20h]
0x1800501a5  mulps   xmm1, xmm0
0x1800501a8  movups  xmm0, xmmword ptr [rdx+30h]
0x1800501ac  add     rdx, 40h ; '@'
0x1800501b0  addps   xmm2, xmm1
0x1800501b3  movaps  xmm1, xmm5
0x1800501b6  movups  xmmword ptr [rcx+20h], xmm2
0x1800501ba  movaps  xmm2, xmm4
0x1800501bd  mulps   xmm2, xmm0
0x1800501c0  movups  xmm0, xmmword ptr [rcx+30h]
0x1800501c4  mulps   xmm1, xmm0
0x1800501c7  addps   xmm2, xmm1
0x1800501ca  movups  xmmword ptr [rcx+30h], xmm2
0x1800501ce  add     rcx, 40h ; '@'
0x1800501d2  cmp     r8d, eax
0x1800501d5  jl      short loc_180050160
0x1800501d7  cmp     r8d, r11d
0x1800501da  jge     loc_1800502CC
0x1800501e0  mov     eax, r11d
0x1800501e3  sub     eax, r8d
0x1800501e6  cmp     eax, 4
0x1800501e9  jl      loc_1800502A0
0x1800501ef  lea     ebx, [r11-3]
0x1800501f3  nop     dword ptr [rax+00h]
0x1800501f7  nop     word ptr [rax+rax+00000000h]
0x180050200  movss   xmm0, dword ptr [r10]
0x180050205  movaps  xmm1, xmm3
0x180050208  subss   xmm1, xmm0
0x18005020c  add     r8d, 4
0x180050210  mulss   xmm0, dword ptr [rdx]
0x180050214  mulss   xmm1, dword ptr [rcx]
0x180050218  addss   xmm1, xmm0
0x18005021c  movss   dword ptr [rcx], xmm1
0x180050220  movaps  xmm1, xmm3
0x180050223  movss   xmm0, dword ptr [r10]
0x180050228  subss   xmm1, xmm0
0x18005022c  movaps  xmm2, xmm0
0x18005022f  mulss   xmm2, dword ptr [rdx+4]
0x180050234  mulss   xmm1, dword ptr [rcx+4]
0x180050239  addss   xmm2, xmm1
0x18005023d  movaps  xmm1, xmm3
0x180050240  movss   dword ptr [rcx+4], xmm2
0x180050245  movss   xmm0, dword ptr [r10]
0x18005024a  subss   xmm1, xmm0
0x18005024e  movaps  xmm2, xmm0
0x180050251  mulss   xmm2, dword ptr [rdx+8]
0x180050256  mulss   xmm1, dword ptr [rcx+8]
0x18005025b  addss   xmm2, xmm1
0x18005025f  movaps  xmm1, xmm3
0x180050262  movss   dword ptr [rcx+8], xmm2
0x180050267  movss   xmm0, dword ptr [r10]
0x18005026c  subss   xmm1, xmm0
0x180050270  movaps  xmm2, xmm0
0x180050273  mulss   xmm2, dword ptr [rdx+0Ch]
0x180050278  add     rdx, 10h
0x18005027c  mulss   xmm1, dword ptr [rcx+0Ch]
0x180050281  addss   xmm2, xmm1
0x180050285  movss   dword ptr [rcx+0Ch], xmm2
0x18005028a  add     rcx, 10h
0x18005028e  cmp     r8d, ebx
0x180050291  jl      loc_180050200
0x180050297  cmp     r8d, r11d
0x18005029a  jge     short loc_1800502CC
0x18005029c  nop     dword ptr [rax+00h]
0x1800502a0  movss   xmm0, dword ptr [r10]
0x1800502a5  movaps  xmm1, xmm3
0x1800502a8  subss   xmm1, xmm0
0x1800502ac  inc     r8d
0x1800502af  mulss   xmm0, dword ptr [rdx]
0x1800502b3  add     rdx, 4
0x1800502b7  mulss   xmm1, dword ptr [rcx]
0x1800502bb  addss   xmm1, xmm0
0x1800502bf  movss   dword ptr [rcx], xmm1
0x1800502c3  add     rcx, 4
0x1800502c7  cmp     r8d, r11d
0x1800502ca  jl      short loc_1800502A0
0x1800502cc  add     r10, 4
0x1800502d0  inc     r9d
0x1800502d3  cmp     r9d, edi
0x1800502d6  jl      loc_180050104
0x1800502dc  movaps  xmm6, [rsp+18h+var_18]
0x1800502e0  mov     rbx, [rsp+18h+arg_0]
0x1800502e5  add     rsp, 10h
0x1800502e9  pop     rdi
0x1800502ea  retn
0x1800502ec  mov     edi, [rsp+18h+arg_28]
0x1800502f0  xor     ebx, ebx
0x1800502f2  test    edi, edi
0x1800502f4  jle     short loc_1800502E0
0x1800502f6  movdqa  xmm5, cs:__xmm@3f8000003f8000003f8000003f800000
0x1800502fe  movss   xmm3, cs:__real@3f800000
0x180050306  nop     word ptr [rax+rax+00000000h]
0x180050310  xor     r8d, r8d
0x180050313  test    r11d, r11d
0x180050316  jz      loc_1800503DE
0x18005031c  cmp     r11d, 10h
0x180050320  jb      loc_1800503DE
0x180050326  movss   xmm2, dword ptr [r10]
0x18005032b  lea     rax, [r11-1]
0x18005032f  lea     rax, [rdx+rax*4]
0x180050333  shufps  xmm2, xmm2, 0
0x180050337  lea     r9, [r11-1]
0x18005033b  lea     r9, [rcx+r9*4]
0x18005033f  cmp     rcx, rax
0x180050342  ja      short loc_18005034D
0x180050344  cmp     r9, rdx
0x180050347  jnb     loc_1800503DE
0x18005034d  cmp     rcx, r10
0x180050350  ja      short loc_18005035B
0x180050352  cmp     r9, r10
0x180050355  jnb     loc_1800503DE
0x18005035b  mov     eax, r11d
0x18005035e  and     eax, 0FFFFFFF0h
0x180050361  movaps  xmm4, xmm5
0x180050364  subps   xmm4, xmm2
0x180050367  nop     word ptr [rax+rax+00000000h]
0x180050370  movups  xmm0, xmmword ptr [rdx]
0x180050373  add     r8d, 10h
  ... truncated ...
```
