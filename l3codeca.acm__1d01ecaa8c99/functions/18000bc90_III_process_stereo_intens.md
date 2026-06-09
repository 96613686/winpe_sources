# III_process_stereo_intens

- ea: `0x18000bc90`
- end: `0x18000c429`
- name: `III_process_stereo_intens`
- size: `1945`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c990`
- `0x18000cc80`
- `0x18000d370`

## callees

- `0x18000bc90`

## pseudocode

```c
__int64 __fastcall III_process_stereo_intens(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        int a5,
        int a6,
        __int64 a7,
        int a8)
{
  __int64 result; // rax
  __m128 v10; // xmm2
  __m128 v11; // xmm3
  __int64 v12; // rbp
  __m128 v13; // xmm2
  __m128 v14; // xmm3
  int v15; // r11d
  __m128 v16; // xmm0
  __m128 v17; // xmm0
  __m128 v18; // xmm0
  __m128 v19; // xmm0
  float v20; // xmm2_4
  float v21; // xmm3_4
  float v22; // xmm0_4
  float v23; // xmm0_4
  float v24; // xmm0_4
  float v25; // xmm0_4
  float v26; // xmm0_4
  __m128 si128; // xmm2
  int v28; // ecx
  int v29; // edi
  __int64 v30; // r14
  __m128 v31; // xmm1
  __m128 v32; // xmm1
  int v33; // r11d
  __m128 v34; // xmm0
  __m128 v35; // xmm0
  __m128 v36; // xmm0
  __m128 v37; // xmm0
  float v38; // xmm1_4
  __int64 v39; // rcx
  int v40; // eax
  int v41; // eax
  __int64 v42; // rcx
  int v43; // edi
  __int64 v44; // r14
  __m128 v45; // xmm1
  __m128 v46; // xmm1
  int v47; // r11d
  float v48; // xmm2_4
  int v49; // ecx
  __m128 v50; // xmm2
  __m128 v51; // xmm2
  __int64 v52; // rcx
  float v53; // xmm3_4
  __m128 v54; // xmm2
  __m128 v55; // xmm2
  float v56; // xmm3_4

  result = a7;
  if ( *(_BYTE *)(a7 + 32) )
  {
    if ( a8 )
    {
      if ( a3 < a4 )
      {
        if ( (unsigned int)(a4 - a3) < 0x10 )
          goto LABEL_20;
        si128 = (__m128)_mm_load_si128((const __m128i *)&_xmm);
        v28 = a4 - (a4 - a3) % 16;
        do
        {
          result = a3;
          a3 += 16;
          *(__m128 *)(a1 + 4 * result) = _mm_mul_ps(si128, *(__m128 *)(a1 + 4 * result));
          *(__m128 *)(a1 + 4 * result + 16) = _mm_mul_ps(si128, *(__m128 *)(a1 + 4 * result + 16));
          *(__m128 *)(a1 + 4 * result + 32) = _mm_mul_ps(si128, *(__m128 *)(a1 + 4 * result + 32));
          *(__m128 *)(a1 + 4 * result + 48) = _mm_mul_ps(*(__m128 *)(a1 + 4 * result + 48), si128);
        }
        while ( a3 < v28 );
        if ( a3 < a4 )
        {
LABEL_20:
          if ( a4 - a3 < 4 )
            goto LABEL_64;
          do
          {
            result = a3;
            a3 += 4;
            *(__m128 *)(a1 + 4 * result) = _mm_mul_ps(*(__m128 *)(a1 + 4 * result), (__m128)_xmm);
          }
          while ( a3 < a4 - 3 );
          if ( a3 < a4 )
          {
LABEL_64:
            do
            {
              result = a3++;
              *(float *)(a1 + 4 * result) = *(float *)(a1 + 4 * result) * 0.5;
            }
            while ( a3 < a4 );
          }
        }
      }
    }
    else if ( a3 < a4 )
    {
      if ( (unsigned int)(a4 - a3) < 0x10 )
        goto LABEL_10;
      v10 = (__m128)(unsigned int)dword_180014370[a5];
      v11 = (__m128)(unsigned int)dword_180014390[a5];
      v12 = a4 - 1;
      v13 = _mm_shuffle_ps(v10, v10, 0);
      v14 = _mm_shuffle_ps(v11, v11, 0);
      if ( a2 + 4LL * a3 <= (unsigned __int64)(a1 + 4 * v12) && a2 + 4 * v12 >= (unsigned __int64)(a1 + 4LL * a3) )
        goto LABEL_10;
      v15 = (a4 - a3) % 16;
      do
      {
        result = a3;
        a3 += 16;
        v16 = *(__m128 *)(a1 + 4 * result);
        *(__m128 *)(a2 + 4 * result) = _mm_mul_ps(v16, v14);
        *(__m128 *)(a1 + 4 * result) = _mm_mul_ps(v16, v13);
        v17 = *(__m128 *)(a1 + 4 * result + 16);
        *(__m128 *)(a2 + 4 * result + 16) = _mm_mul_ps(v17, v14);
        *(__m128 *)(a1 + 4 * result + 16) = _mm_mul_ps(v17, v13);
        v18 = *(__m128 *)(a1 + 4 * result + 32);
        *(__m128 *)(a2 + 4 * result + 32) = _mm_mul_ps(v18, v14);
        *(__m128 *)(a1 + 4 * result + 32) = _mm_mul_ps(v18, v13);
        v19 = *(__m128 *)(a1 + 4 * result + 48);
        *(__m128 *)(a2 + 4 * result + 48) = _mm_mul_ps(v19, v14);
        *(__m128 *)(a1 + 4 * result + 48) = _mm_mul_ps(v19, v13);
      }
      while ( a3 < a4 - v15 );
      if ( a3 < a4 )
      {
LABEL_10:
        v20 = *(float *)&dword_180014370[a5];
        v21 = *(float *)&dword_180014390[a5];
        if ( a4 - a3 < 4 )
          goto LABEL_65;
        do
        {
          result = a3;
          a3 += 4;
          v22 = *(float *)(a1 + 4 * result);
          *(float *)(a1 + 4 * result) = v22 * v20;
          *(float *)(a2 + 4 * result) = v22 * v21;
          v23 = *(float *)(a1 + 4 * result + 4);
          *(float *)(a1 + 4 * result + 4) = v23 * v20;
          *(float *)(a2 + 4 * result + 4) = v23 * v21;
          v24 = *(float *)(a1 + 4 * result + 8);
          *(float *)(a1 + 4 * result + 8) = v24 * v20;
          *(float *)(a2 + 4 * result + 8) = v24 * v21;
          v25 = *(float *)(a1 + 4 * result + 12);
          *(float *)(a1 + 4 * result + 12) = v25 * v20;
          *(float *)(a2 + 4 * result + 12) = v25 * v21;
        }
        while ( a3 < a4 - 3 );
        if ( a3 < a4 )
        {
LABEL_65:
          do
          {
            result = a3++;
            v26 = *(float *)(a1 + 4 * result);
            *(float *)(a1 + 4 * result) = v26 * v20;
            *(float *)(a2 + 4 * result) = v26 * v21;
          }
          while ( a3 < a4 );
        }
      }
    }
  }
  else if ( a8 )
  {
    if ( a3 < a4 )
    {
      if ( (unsigned int)(a4 - a3) < 0x10 )
        goto LABEL_56;
      v49 = a4 - (a4 - a3) % 16;
      v50 = (__m128)(unsigned int)dword_1800142F0[16 * a6 + a5];
      v51 = _mm_mul_ps(_mm_add_ps(_mm_shuffle_ps(v50, v50, 0), (__m128)_xmm), (__m128)_xmm);
      do
      {
        result = a3;
        a3 += 16;
        *(__m128 *)(a1 + 4 * result) = _mm_mul_ps(v51, *(__m128 *)(a1 + 4 * result));
        *(__m128 *)(a1 + 4 * result + 16) = _mm_mul_ps(v51, *(__m128 *)(a1 + 4 * result + 16));
        *(__m128 *)(a1 + 4 * result + 32) = _mm_mul_ps(v51, *(__m128 *)(a1 + 4 * result + 32));
        *(__m128 *)(a1 + 4 * result + 48) = _mm_mul_ps(v51, *(__m128 *)(a1 + 4 * result + 48));
      }
      while ( a3 < v49 );
      if ( a3 < a4 )
      {
LABEL_56:
        v52 = a5 + 16LL * a6;
        v53 = *(float *)&dword_1800142F0[v52];
        if ( a4 - a3 < 4 )
          goto LABEL_60;
        v54 = (__m128)(unsigned int)dword_1800142F0[v52];
        v54.m128_f32[0] = (float)(v53 + 1.0) * 0.5;
        v55 = _mm_shuffle_ps(v54, v54, 0);
        do
        {
          result = a3;
          a3 += 4;
          *(__m128 *)(a1 + 4 * result) = _mm_mul_ps(*(__m128 *)(a1 + 4 * result), v55);
        }
        while ( a3 < a4 - 3 );
        if ( a3 < a4 )
        {
LABEL_60:
          v56 = (float)(v53 + 1.0) * 0.5;
          do
          {
            result = a3++;
            *(float *)(a1 + 4 * result) = v56 * *(float *)(a1 + 4 * result);
          }
          while ( a3 < a4 );
        }
      }
    }
  }
  else if ( (a5 & 1) != 0 )
  {
    if ( a3 < a4 )
    {
      v29 = (a5 + 1) >> 1;
      if ( (unsigned int)(a4 - a3) < 0x10 )
        goto LABEL_34;
      v30 = a4 - 1;
      v31 = (__m128)(unsigned int)dword_1800142F0[16 * a6 + v29];
      v32 = _mm_shuffle_ps(v31, v31, 0);
      if ( a1 + 4LL * a3 <= (unsigned __int64)(a2 + 4 * v30) && a1 + 4 * v30 >= (unsigned __int64)(a2 + 4LL * a3) )
        goto LABEL_34;
      v33 = (a4 - a3) % 16;
      do
      {
        result = a3;
        a3 += 16;
        v34 = *(__m128 *)(a1 + 4 * result);
        *(__m128 *)(a2 + 4 * result) = v34;
        *(__m128 *)(a1 + 4 * result) = _mm_mul_ps(v34, v32);
        v35 = *(__m128 *)(a1 + 4 * result + 16);
        *(__m128 *)(a2 + 4 * result + 16) = v35;
        *(__m128 *)(a1 + 4 * result + 16) = _mm_mul_ps(v35, v32);
        v36 = *(__m128 *)(a1 + 4 * result + 32);
        *(__m128 *)(a2 + 4 * result + 32) = v36;
        *(__m128 *)(a1 + 4 * result + 32) = _mm_mul_ps(v36, v32);
        v37 = *(__m128 *)(a1 + 4 * result + 48);
        *(__m128 *)(a2 + 4 * result + 48) = v37;
        *(__m128 *)(a1 + 4 * result + 48) = _mm_mul_ps(v37, v32);
      }
      while ( a3 < a4 - v33 );
      if ( a3 < a4 )
      {
LABEL_34:
        v38 = *(float *)&dword_1800142F0[16 * a6 + v29];
        if ( a4 - a3 < 4 )
          goto LABEL_66;
        do
        {
          v39 = a3;
          a3 += 4;
          *(_DWORD *)(a2 + 4 * v39) = *(_DWORD *)(a1 + 4 * v39);
          v40 = *(_DWORD *)(a1 + 4 * v39 + 4);
          *(float *)(a1 + 4 * v39) = v38 * *(float *)(a1 + 4 * v39);
          *(_DWORD *)(a2 + 4 * v39 + 4) = v40;
          v41 = *(_DWORD *)(a1 + 4 * v39 + 8);
          *(float *)(a1 + 4 * v39 + 4) = v38 * *(float *)(a1 + 4 * v39 + 4);
          *(_DWORD *)(a2 + 4 * v39 + 8) = v41;
          result = *(unsigned int *)(a1 + 4 * v39 + 12);
          *(float *)(a1 + 4 * v39 + 8) = v38 * *(float *)(a1 + 4 * v39 + 8);
          *(_DWORD *)(a2 + 4 * v39 + 12) = result;
          *(float *)(a1 + 4 * v39 + 12) = v38 * *(float *)(a1 + 4 * v39 + 12);
        }
        while ( a3 < a4 - 3 );
        if ( a3 < a4 )
        {
LABEL_66:
          do
          {
            v42 = a3++;
            result = *(unsigned int *)(a1 + 4 * v42);
            *(_DWORD *)(a2 + 4 * v42) = result;
            *(float *)(a1 + 4 * v42) = v38 * *(float *)(a1 + 4 * v42);
          }
          while ( a3 < a4 );
        }
      }
    }
  }
  else if ( a3 < a4 )
  {
    v43 = a5 >> 1;
    if ( (unsigned int)(a4 - a3) < 0x10 )
      goto LABEL_46;
    v44 = a4 - 1;
    v45 = (__m128)(unsigned int)dword_1800142F0[16 * a6 + v43];
    v46 = _mm_shuffle_ps(v45, v45, 0);
    if ( a2 + 4LL * a3 <= (unsigned __int64)(a1 + 4 * v44) && a2 + 4 * v44 >= (unsigned __int64)(a1 + 4LL * a3) )
      goto LABEL_46;
    v47 = (a4 - a3) % 16;
    do
    {
      result = a3;
      a3 += 16;
      *(__m128 *)(a2 + 4 * result) = _mm_mul_ps(*(__m128 *)(a1 + 4 * result), v46);
      *(__m128 *)(a2 + 4 * result + 16) = _mm_mul_ps(*(__m128 *)(a1 + 4 * result + 16), v46);
      *(__m128 *)(a2 + 4 * result + 32) = _mm_mul_ps(*(__m128 *)(a1 + 4 * result + 32), v46);
      *(__m128 *)(a2 + 4 * result + 48) = _mm_mul_ps(*(__m128 *)(a1 + 4 * result + 48), v46);
    }
    while ( a3 < a4 - v47 );
    if ( a3 < a4 )
    {
LABEL_46:
      v48 = *(float *)&dword_1800142F0[16 * a6 + v43];
      if ( a4 - a3 < 4 )
        goto LABEL_67;
      do
      {
        result = a3;
        a3 += 4;
        *(float *)(a2 + 4 * result) = v48 * *(float *)(a1 + 4 * result);
        *(float *)(a2 + 4 * result + 4) = v48 * *(float *)(a1 + 4 * result + 4);
        *(float *)(a2 + 4 * result + 8) = v48 * *(float *)(a1 + 4 * result + 8);
        *(float *)(a2 + 4 * result + 12) = v48 * *(float *)(a1 + 4 * result + 12);
      }
      while ( a3 < a4 - 3 );
      if ( a3 < a4 )
      {
LABEL_67:
        do
        {
          result = a3++;
          *(float *)(a2 + 4 * result) = v48 * *(float *)(a1 + 4 * result);
        }
        while ( a3 < a4 );
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000bc90  push    rbx
0x18000bc92  push    rbp
0x18000bc93  push    rsi
0x18000bc94  push    rdi
0x18000bc95  mov     rax, [rsp+20h+arg_30]
0x18000bc9a  mov     r10, rcx
0x18000bc9d  movsxd  rdi, [rsp+20h+arg_20]
0x18000bca2  cmp     byte ptr [rax+20h], 0
0x18000bca6  jz      loc_18000BFA0
0x18000bcac  cmp     [rsp+20h+arg_38], 0
0x18000bcb1  jnz     loc_18000BEAC
0x18000bcb7  cmp     r8d, r9d
0x18000bcba  jge     loc_18000C176
0x18000bcc0  mov     r11d, r9d
0x18000bcc3  lea     rbx, __ImageBase
0x18000bcca  sub     r11d, r8d
0x18000bccd  cmp     r11d, 10h
0x18000bcd1  jb      loc_18000BDBA
0x18000bcd7  movss   xmm2, ds:rva dword_180014370[rbx+rdi*4]
0x18000bce0  lea     eax, [r9-1]
0x18000bce4  movss   xmm3, ds:rva dword_180014390[rbx+rdi*4]
0x18000bced  movsxd  rbp, eax
0x18000bcf0  movsxd  rsi, r8d
0x18000bcf3  shufps  xmm2, xmm2, 0
0x18000bcf7  shufps  xmm3, xmm3, 0
0x18000bcfb  lea     rax, [r10+rbp*4]
0x18000bcff  lea     rcx, [rdx+rsi*4]
0x18000bd03  cmp     rcx, rax
0x18000bd06  ja      short loc_18000BD19
0x18000bd08  lea     rcx, [r10+rsi*4]
0x18000bd0c  lea     rax, [rdx+rbp*4]
0x18000bd10  cmp     rax, rcx
0x18000bd13  jnb     loc_18000BDBA
0x18000bd19  and     r11d, 8000000Fh
0x18000bd20  jge     short loc_18000BD2C
0x18000bd22  dec     r11d
0x18000bd25  or      r11d, 0FFFFFFF0h
0x18000bd29  inc     r11d
0x18000bd2c  mov     ecx, r9d
0x18000bd2f  sub     ecx, r11d
0x18000bd32  nop     dword ptr [rax+00h]
0x18000bd36  nop     word ptr [rax+rax+00000000h]
0x18000bd40  movsxd  rax, r8d
0x18000bd43  add     r8d, 10h
0x18000bd47  movups  xmm1, xmmword ptr [r10+rax*4]
0x18000bd4c  movaps  xmm0, xmm1
0x18000bd4f  mulps   xmm1, xmm3
0x18000bd52  mulps   xmm0, xmm2
0x18000bd55  movups  xmmword ptr [rdx+rax*4], xmm1
0x18000bd59  movups  xmmword ptr [r10+rax*4], xmm0
0x18000bd5e  movups  xmm1, xmmword ptr [r10+rax*4+10h]
0x18000bd64  movaps  xmm0, xmm1
0x18000bd67  mulps   xmm1, xmm3
0x18000bd6a  mulps   xmm0, xmm2
0x18000bd6d  movups  xmmword ptr [rdx+rax*4+10h], xmm1
0x18000bd72  movups  xmmword ptr [r10+rax*4+10h], xmm0
0x18000bd78  movups  xmm1, xmmword ptr [r10+rax*4+20h]
0x18000bd7e  movaps  xmm0, xmm1
0x18000bd81  mulps   xmm1, xmm3
0x18000bd84  mulps   xmm0, xmm2
0x18000bd87  movups  xmmword ptr [rdx+rax*4+20h], xmm1
0x18000bd8c  movups  xmmword ptr [r10+rax*4+20h], xmm0
0x18000bd92  movups  xmm1, xmmword ptr [r10+rax*4+30h]
0x18000bd98  movaps  xmm0, xmm1
0x18000bd9b  mulps   xmm1, xmm3
0x18000bd9e  mulps   xmm0, xmm2
0x18000bda1  movups  xmmword ptr [rdx+rax*4+30h], xmm1
0x18000bda6  movups  xmmword ptr [r10+rax*4+30h], xmm0
0x18000bdac  cmp     r8d, ecx
0x18000bdaf  jl      short loc_18000BD40
0x18000bdb1  cmp     r8d, r9d
0x18000bdb4  jge     loc_18000C176
0x18000bdba  movss   xmm2, ds:rva dword_180014370[rbx+rdi*4]
0x18000bdc3  mov     eax, r9d
0x18000bdc6  movss   xmm3, ds:rva dword_180014390[rbx+rdi*4]
0x18000bdcf  sub     eax, r8d
0x18000bdd2  cmp     eax, 4
0x18000bdd5  jl      loc_18000BE80
0x18000bddb  lea     ecx, [r9-3]
0x18000bddf  nop
0x18000bde0  movsxd  rax, r8d
0x18000bde3  add     r8d, 4
0x18000bde7  movss   xmm1, dword ptr [r10+rax*4]
0x18000bded  movaps  xmm0, xmm1
0x18000bdf0  mulss   xmm1, xmm3
0x18000bdf4  mulss   xmm0, xmm2
0x18000bdf8  movss   dword ptr [r10+rax*4], xmm0
0x18000bdfe  movss   dword ptr [rdx+rax*4], xmm1
0x18000be03  movss   xmm1, dword ptr [r10+rax*4+4]
0x18000be0a  movaps  xmm0, xmm1
0x18000be0d  mulss   xmm1, xmm3
0x18000be11  mulss   xmm0, xmm2
0x18000be15  movss   dword ptr [r10+rax*4+4], xmm0
0x18000be1c  movss   dword ptr [rdx+rax*4+4], xmm1
0x18000be22  movss   xmm1, dword ptr [r10+rax*4+8]
0x18000be29  movaps  xmm0, xmm1
0x18000be2c  mulss   xmm1, xmm3
0x18000be30  mulss   xmm0, xmm2
0x18000be34  movss   dword ptr [r10+rax*4+8], xmm0
0x18000be3b  movss   dword ptr [rdx+rax*4+8], xmm1
0x18000be41  movss   xmm1, dword ptr [r10+rax*4+0Ch]
0x18000be48  movaps  xmm0, xmm1
0x18000be4b  mulss   xmm1, xmm3
0x18000be4f  mulss   xmm0, xmm2
0x18000be53  movss   dword ptr [r10+rax*4+0Ch], xmm0
0x18000be5a  movss   dword ptr [rdx+rax*4+0Ch], xmm1
0x18000be60  cmp     r8d, ecx
0x18000be63  jl      loc_18000BDE0
0x18000be69  cmp     r8d, r9d
0x18000be6c  jge     loc_18000C176
0x18000be72  nop     dword ptr [rax+00h]
0x18000be76  nop     word ptr [rax+rax+00000000h]
0x18000be80  movsxd  rax, r8d
0x18000be83  inc     r8d
0x18000be86  movss   xmm1, dword ptr [r10+rax*4]
0x18000be8c  movaps  xmm0, xmm1
0x18000be8f  mulss   xmm1, xmm3
0x18000be93  mulss   xmm0, xmm2
0x18000be97  movss   dword ptr [r10+rax*4], xmm0
0x18000be9d  movss   dword ptr [rdx+rax*4], xmm1
0x18000bea2  cmp     r8d, r9d
0x18000bea5  jl      short loc_18000BE80
0x18000bea7  pop     rdi
0x18000bea8  pop     rsi
0x18000bea9  pop     rbp
0x18000beaa  pop     rbx
0x18000beab  retn
0x18000beac  cmp     r8d, r9d
0x18000beaf  jge     loc_18000C176
0x18000beb5  mov     eax, r9d
0x18000beb8  sub     eax, r8d
0x18000bebb  cmp     eax, 10h
0x18000bebe  jb      short loc_18000BF38
0x18000bec0  and     eax, 8000000Fh
0x18000bec5  jge     short loc_18000BECE
0x18000bec7  dec     eax
0x18000bec9  or      eax, 0FFFFFFF0h
0x18000becc  inc     eax
0x18000bece  movdqa  xmm2, cs:__xmm@3f0000003f0000003f0000003f000000
0x18000bed6  mov     ecx, r9d
0x18000bed9  sub     ecx, eax
0x18000bedb  nop     dword ptr [rax+rax+00h]
0x18000bee0  movsxd  rax, r8d
0x18000bee3  movaps  xmm1, xmm2
0x18000bee6  add     r8d, 10h
0x18000beea  movups  xmm0, xmmword ptr [r10+rax*4]
0x18000beef  mulps   xmm1, xmm0
0x18000bef2  movups  xmmword ptr [r10+rax*4], xmm1
0x18000bef7  movaps  xmm1, xmm2
0x18000befa  movups  xmm0, xmmword ptr [r10+rax*4+10h]
0x18000bf00  mulps   xmm1, xmm0
0x18000bf03  movups  xmmword ptr [r10+rax*4+10h], xmm1
0x18000bf09  movaps  xmm1, xmm2
0x18000bf0c  movups  xmm0, xmmword ptr [r10+rax*4+20h]
0x18000bf12  mulps   xmm1, xmm0
0x18000bf15  movups  xmmword ptr [r10+rax*4+20h], xmm1
0x18000bf1b  movups  xmm0, xmmword ptr [r10+rax*4+30h]
0x18000bf21  mulps   xmm0, xmm2
0x18000bf24  movups  xmmword ptr [r10+rax*4+30h], xmm0
0x18000bf2a  cmp     r8d, ecx
0x18000bf2d  jl      short loc_18000BEE0
0x18000bf2f  cmp     r8d, r9d
0x18000bf32  jge     loc_18000C176
0x18000bf38  movaps  xmm2, cs:__xmm@3f0000003f0000003f0000003f000000
0x18000bf3f  mov     eax, r9d
0x18000bf42  sub     eax, r8d
0x18000bf45  cmp     eax, 4
0x18000bf48  jl      short loc_18000BF80
0x18000bf4a  lea     ecx, [r9-3]
0x18000bf4e  xchg    ax, ax
0x18000bf50  movsxd  rax, r8d
0x18000bf53  add     r8d, 4
0x18000bf57  movups  xmm0, xmmword ptr [r10+rax*4]
0x18000bf5c  mulps   xmm0, xmm2
0x18000bf5f  movups  xmmword ptr [r10+rax*4], xmm0
0x18000bf64  cmp     r8d, ecx
0x18000bf67  jl      short loc_18000BF50
0x18000bf69  cmp     r8d, r9d
0x18000bf6c  jge     loc_18000C176
0x18000bf72  nop     dword ptr [rax+00h]
0x18000bf76  nop     word ptr [rax+rax+00000000h]
0x18000bf80  movsxd  rax, r8d
0x18000bf83  inc     r8d
0x18000bf86  movss   xmm0, dword ptr [r10+rax*4]
0x18000bf8c  mulss   xmm0, xmm2
0x18000bf90  movss   dword ptr [r10+rax*4], xmm0
0x18000bf96  cmp     r8d, r9d
0x18000bf99  jl      short loc_18000BF80
0x18000bf9b  pop     rdi
0x18000bf9c  pop     rsi
0x18000bf9d  pop     rbp
0x18000bf9e  pop     rbx
0x18000bf9f  retn
0x18000bfa0  cmp     [rsp+20h+arg_38], 0
0x18000bfa5  movsxd  rsi, [rsp+20h+arg_28]
0x18000bfaa  jnz     loc_18000C2E3
0x18000bfb0  mov     [rsp+20h+arg_0], r14
0x18000bfb5  test    dil, 1
0x18000bfb9  jz      loc_18000C17B
0x18000bfbf  cmp     r8d, r9d
0x18000bfc2  jge     loc_18000C171
0x18000bfc8  inc     edi
0x18000bfca  lea     rbx, __ImageBase
0x18000bfd1  mov     r11d, r9d
0x18000bfd4  sar     edi, 1
0x18000bfd6  sub     r11d, r8d
0x18000bfd9  cmp     r11d, 10h
0x18000bfdd  jb      loc_18000C0A2
0x18000bfe3  movsxd  rax, edi
0x18000bfe6  mov     rcx, rsi
0x18000bfe9  shl     rcx, 4
0x18000bfed  add     rcx, rax
0x18000bff0  movsxd  rbp, r8d
0x18000bff3  lea     eax, [r9-1]
0x18000bff7  movsxd  r14, eax
0x18000bffa  movss   xmm1, ds:rva dword_1800142F0[rbx+rcx*4]
0x18000c003  lea     rcx, [r10+rbp*4]
0x18000c007  shufps  xmm1, xmm1, 0
0x18000c00b  lea     rax, [rdx+r14*4]
0x18000c00f  cmp     rcx, rax
0x18000c012  ja      short loc_18000C025
0x18000c014  lea     rcx, [rdx+rbp*4]
0x18000c018  lea     rax, [r10+r14*4]
0x18000c01c  cmp     rax, rcx
0x18000c01f  jnb     loc_18000C0A2
0x18000c025  and     r11d, 8000000Fh
0x18000c02c  jge     short loc_18000C038
0x18000c02e  dec     r11d
0x18000c031  or      r11d, 0FFFFFFF0h
0x18000c035  inc     r11d
0x18000c038  mov     ecx, r9d
0x18000c03b  sub     ecx, r11d
0x18000c03e  xchg    ax, ax
0x18000c040  movsxd  rax, r8d
0x18000c043  add     r8d, 10h
0x18000c047  movups  xmm0, xmmword ptr [r10+rax*4]
0x18000c04c  movups  xmmword ptr [rdx+rax*4], xmm0
0x18000c050  mulps   xmm0, xmm1
0x18000c053  movups  xmmword ptr [r10+rax*4], xmm0
0x18000c058  movups  xmm0, xmmword ptr [r10+rax*4+10h]
0x18000c05e  movups  xmmword ptr [rdx+rax*4+10h], xmm0
0x18000c063  mulps   xmm0, xmm1
0x18000c066  movups  xmmword ptr [r10+rax*4+10h], xmm0
0x18000c06c  movups  xmm0, xmmword ptr [r10+rax*4+20h]
0x18000c072  movups  xmmword ptr [rdx+rax*4+20h], xmm0
0x18000c077  mulps   xmm0, xmm1
0x18000c07a  movups  xmmword ptr [r10+rax*4+20h], xmm0
0x18000c080  movups  xmm0, xmmword ptr [r10+rax*4+30h]
0x18000c086  movups  xmmword ptr [rdx+rax*4+30h], xmm0
0x18000c08b  mulps   xmm0, xmm1
0x18000c08e  movups  xmmword ptr [r10+rax*4+30h], xmm0
0x18000c094  cmp     r8d, ecx
0x18000c097  jl      short loc_18000C040
0x18000c099  cmp     r8d, r9d
0x18000c09c  jge     loc_18000C171
0x18000c0a2  movsxd  rax, edi
0x18000c0a5  mov     rcx, rsi
0x18000c0a8  shl     rcx, 4
0x18000c0ac  add     rcx, rax
0x18000c0af  mov     eax, r9d
0x18000c0b2  sub     eax, r8d
0x18000c0b5  movss   xmm1, ds:rva dword_1800142F0[rbx+rcx*4]
0x18000c0be  cmp     eax, 4
0x18000c0c1  jl      loc_18000C150
0x18000c0c7  lea     r11d, [r9-3]
0x18000c0cb  nop     dword ptr [rax+rax+00h]
0x18000c0d0  movsxd  rcx, r8d
0x18000c0d3  movaps  xmm0, xmm1
0x18000c0d6  add     r8d, 4
0x18000c0da  mov     eax, [r10+rcx*4]
0x18000c0de  mov     [rdx+rcx*4], eax
0x18000c0e1  mulss   xmm0, dword ptr [r10+rcx*4]
0x18000c0e7  mov     eax, [r10+rcx*4+4]
0x18000c0ec  movss   dword ptr [r10+rcx*4], xmm0
0x18000c0f2  movaps  xmm0, xmm1
0x18000c0f5  mov     [rdx+rcx*4+4], eax
0x18000c0f9  mulss   xmm0, dword ptr [r10+rcx*4+4]
0x18000c100  mov     eax, [r10+rcx*4+8]
0x18000c105  movss   dword ptr [r10+rcx*4+4], xmm0
0x18000c10c  movaps  xmm0, xmm1
0x18000c10f  mov     [rdx+rcx*4+8], eax
0x18000c113  mulss   xmm0, dword ptr [r10+rcx*4+8]
0x18000c11a  mov     eax, [r10+rcx*4+0Ch]
0x18000c11f  movss   dword ptr [r10+rcx*4+8], xmm0
0x18000c126  movaps  xmm0, xmm1
0x18000c129  mov     [rdx+rcx*4+0Ch], eax
0x18000c12d  mulss   xmm0, dword ptr [r10+rcx*4+0Ch]
0x18000c134  movss   dword ptr [r10+rcx*4+0Ch], xmm0
0x18000c13b  cmp     r8d, r11d
0x18000c13e  jl      short loc_18000C0D0
0x18000c140  cmp     r8d, r9d
0x18000c143  jge     short loc_18000C171
0x18000c145  nop     word ptr [rax+rax+00000000h]
0x18000c150  movsxd  rcx, r8d
0x18000c153  movaps  xmm0, xmm1
0x18000c156  inc     r8d
0x18000c159  mov     eax, [r10+rcx*4]
0x18000c15d  mov     [rdx+rcx*4], eax
0x18000c160  mulss   xmm0, dword ptr [r10+rcx*4]
0x18000c166  movss   dword ptr [r10+rcx*4], xmm0
  ... truncated ...
```
