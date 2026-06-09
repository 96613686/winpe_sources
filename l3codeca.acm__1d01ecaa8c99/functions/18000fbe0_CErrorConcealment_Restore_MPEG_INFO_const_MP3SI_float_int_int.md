# CErrorConcealment::Restore(MPEG_INFO const &,MP3SI &,float *,int,int)

- ea: `0x18000fbe0`
- end: `0x180010148`
- name: `?Restore@CErrorConcealment@@IEAAXAEBUMPEG_INFO@@AEAUMP3SI@@PEAMHH@Z`
- size: `1384`
- prototype: `void __usercall(CErrorConcealment *__hidden this@<rcx>, const struct MPEG_INFO *@<rdx>, struct MP3SI *@<r8>, float *@<r9>, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180004da0`
- `0x18000f870`

## callees

- `0x180001cbc`
- `0x180001cd4`
- `0x18000fbe0`
- `0x180010150`
- `0x180010440`

## pseudocode

```c
void __fastcall CErrorConcealment::Restore(
        CErrorConcealment *this,
        const struct MPEG_INFO *a2,
        struct MP3SI *a3,
        float *a4,
        int a5,
        int a6)
{
  __int64 v7; // r12
  __int64 v9; // r14
  const struct MPEG_INFO *v10; // r9
  int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // r14
  int v15; // edx
  __int64 i; // r8
  __int64 v17; // rax
  int v18; // r13d
  __int64 v19; // r15
  double v20; // xmm4_8
  __int64 v21; // rcx
  __int64 v22; // r12
  int v23; // ebp
  int v24; // ebx
  double v25; // xmm3_8
  float v26; // xmm0_4
  __int64 v27; // rax
  float v28; // xmm2_4
  __int64 v29; // rcx
  float v30; // xmm0_4
  int v31; // eax
  int v32; // eax
  double v33; // xmm3_8
  float v34; // xmm0_4
  int v35; // eax
  int v36; // eax
  double v37; // xmm3_8
  float v38; // xmm0_4
  int v39; // eax
  int v40; // eax
  double v41; // xmm3_8
  float v42; // xmm0_4
  int v43; // eax
  int v44; // eax
  __int64 v45; // rcx
  float v46; // xmm0_4
  int v47; // eax
  int v48; // eax
  double v49; // xmm4_8
  double v50; // xmm0_8
  __m128 v51; // xmm2
  __m128 v52; // xmm3
  __int64 v53; // rax
  __int64 v54; // rax
  float v55; // xmm1_4
  float v56; // xmm0_4
  float v57; // xmm1_4
  __int64 v58; // rax
  __int64 v59; // [rsp+20h] [rbp-78h]
  char *v60; // [rsp+28h] [rbp-70h]
  __int64 v61; // [rsp+A0h] [rbp+8h]
  __int64 v63; // [rsp+B0h] [rbp+18h]

  v7 = *((int *)a2 + 1);
  v9 = 12544LL * a6;
  v10 = a2;
  v12 = (*(_DWORD *)((char *)this + v9) + 3) % 4;
  if ( !*(_DWORD *)((char *)this + v9 + 12540) )
  {
    CErrorConcealment::predictEnergies(this, a2, (CErrorConcealment *)((char *)this + v9));
    v10 = a2;
  }
  v59 = 232LL * a6;
  v13 = v9 + 2508LL * v12;
  v60 = (char *)a3 + 108 * a5;
  v14 = 0;
  v63 = v7;
  *(_OWORD *)&v60[v59 + 24] = *(_OWORD *)((char *)this + v13 + 4);
  *(_OWORD *)&v60[v59 + 40] = *(_OWORD *)((char *)this + v13 + 20);
  *(_OWORD *)&v60[v59 + 56] = *(_OWORD *)((char *)this + v13 + 36);
  *(_OWORD *)&v60[v59 + 72] = *(_OWORD *)((char *)this + v13 + 52);
  *(_OWORD *)&v60[v59 + 88] = *(_OWORD *)((char *)this + v13 + 68);
  *(_OWORD *)&v60[v59 + 104] = *(_OWORD *)((char *)this + v13 + 84);
  *(_OWORD *)&v60[v59 + 116] = *(_OWORD *)((char *)this + v13 + 96);
  v15 = 0;
  for ( i = v7; v15 < *((_DWORD *)&sfBandIndex + 74 * *((int *)v10 + 6) + 37 * v7 + 37 * *((int *)v10 + 6)); a4[v17] = 0.0 )
    v17 = v15++;
  v18 = 0;
  v19 = 3136LL * a6;
  v61 = 0;
  do
  {
    v20 = *((float *)this + v19 + v14 + 3112);
    v21 = v14 + 37 * (i + 2LL * *((int *)v10 + 6) + *((int *)v10 + 6));
    v22 = *((int *)&sfBandIndex + v21);
    v23 = *((_DWORD *)&sfBandIndex + v21 + 1);
    v24 = *((_DWORD *)&sfBandIndex + v21);
    if ( v20 <= 0.0 )
    {
      if ( (int)v22 < v23 )
      {
        do
          ++v24;
        while ( v24 < v23 );
        memset_0(&a4[v22], 0, 4LL * (v23 - (int)v22));
      }
    }
    else if ( (int)v22 < v23 )
    {
      v25 = 0.0;
      if ( v18 )
      {
        do
        {
          v26 = CErrorConcealment::ran3(this, (int *)this + 6331);
          v27 = v24++;
          v28 = v26 - 0.5;
          a4[v27] = v28;
          v25 = v25 + (float)(v28 * v28);
        }
        while ( v24 < v23 );
        v14 = v61;
      }
      else
      {
        if ( v23 - (int)v22 >= 4 )
        {
          do
          {
            v29 = v24;
            v30 = *((float *)this + v19 + v24 + 2536);
            v31 = *((_DWORD *)this + 6333);
            if ( v31 >= 0 )
            {
              v32 = 2 * v31;
              LODWORD(v30) ^= _xmm;
            }
            else
            {
              v32 = (2 * (v31 ^ 9)) | 1;
            }
            *((_DWORD *)this + 6333) = v32;
            a4[v24] = v30;
            v33 = v25 + (float)(v30 * v30);
            v34 = *((float *)this + v19 + v24 + 2537);
            v35 = *((_DWORD *)this + 6333);
            if ( v35 >= 0 )
            {
              v36 = 2 * v35;
              LODWORD(v34) ^= _xmm;
            }
            else
            {
              v36 = (2 * (v35 ^ 9)) | 1;
            }
            *((_DWORD *)this + 6333) = v36;
            a4[v24 + 1] = v34;
            v37 = v33 + (float)(v34 * v34);
            v38 = *((float *)this + v19 + v24 + 2538);
            v39 = *((_DWORD *)this + 6333);
            if ( v39 >= 0 )
            {
              v40 = 2 * v39;
              LODWORD(v38) ^= _xmm;
            }
            else
            {
              v40 = (2 * (v39 ^ 9)) | 1;
            }
            *((_DWORD *)this + 6333) = v40;
            a4[v24 + 2] = v38;
            v41 = v37 + (float)(v38 * v38);
            v42 = *((float *)this + v19 + v24 + 2539);
            v43 = *((_DWORD *)this + 6333);
            if ( v43 >= 0 )
            {
              v44 = 2 * v43;
              LODWORD(v42) ^= _xmm;
            }
            else
            {
              v44 = (2 * (v43 ^ 9)) | 1;
            }
            *((_DWORD *)this + 6333) = v44;
            v24 += 4;
            a4[v29 + 3] = v42;
            v25 = v41 + (float)(v42 * v42);
          }
          while ( v24 < v23 - 3 );
        }
        for ( ; v24 < v23; v25 = v25 + (float)(v46 * v46) )
        {
          v45 = v24;
          v46 = *((float *)this + v19 + v24 + 2536);
          v47 = *((_DWORD *)this + 6333);
          if ( v47 >= 0 )
          {
            v48 = 2 * v47;
            LODWORD(v46) ^= _xmm;
          }
          else
          {
            v48 = (2 * (v47 ^ 9)) | 1;
          }
          *((_DWORD *)this + 6333) = v48;
          ++v24;
          a4[v45] = v46;
        }
      }
      if ( v25 != 0.0 )
      {
        v49 = v20 / v25;
        v50 = v49 < 0.0 ? sqrt(v49) : sqrt(v49);
        v51 = 0;
        v51.m128_f32[0] = v50;
        v24 = v22;
        v52 = _mm_shuffle_ps(v51, v51, 0);
        if ( (unsigned int)(v23 - v22) < 0x10 )
          goto LABEL_37;
        do
        {
          v53 = v24;
          v24 += 16;
          *(__m128 *)&a4[v53] = _mm_mul_ps(*(__m128 *)&a4[v53], v52);
          *(__m128 *)&a4[v53 + 4] = _mm_mul_ps(*(__m128 *)&a4[v53 + 4], v52);
          *(__m128 *)&a4[v53 + 8] = _mm_mul_ps(v52, *(__m128 *)&a4[v53 + 8]);
          *(__m128 *)&a4[v53 + 12] = _mm_mul_ps(*(__m128 *)&a4[v53 + 12], v52);
        }
        while ( v24 < v23 - (v23 - (int)v22) % 16 );
        if ( v24 < v23 )
        {
LABEL_37:
          if ( v23 - v24 < 4 )
            goto LABEL_51;
          do
          {
            v54 = v24;
            v24 += 4;
            v55 = v51.m128_f32[0] * a4[v54 + 1];
            a4[v54] = v51.m128_f32[0] * a4[v54];
            v56 = v51.m128_f32[0] * a4[v54 + 2];
            a4[v54 + 1] = v55;
            v57 = v51.m128_f32[0] * a4[v54 + 3];
            a4[v54 + 2] = v56;
            a4[v54 + 3] = v57;
          }
          while ( v24 < v23 - 3 );
          if ( v24 < v23 )
          {
LABEL_51:
            do
            {
              v58 = v24++;
              a4[v58] = v51.m128_f32[0] * a4[v58];
            }
            while ( v24 < v23 );
          }
        }
      }
    }
    v10 = a2;
    i = v63;
    ++v18;
    v61 = ++v14;
  }
  while ( v18 < 22 );
  if ( v24 < 576 )
    memset_0(&a4[v24], 0, 4LL * (576 - v24));
  *(_DWORD *)&v60[v59 + 100] = *((_DWORD *)&sfBandIndex + 74 * *((int *)a2 + 6) + 37 * v63 + 37 * *((int *)a2 + 6) + 22);
  *(_DWORD *)&v60[v59 + 128] = 22;
}

```

## disassembly

```asm
0x18000fbe0  mov     [rsp+arg_18], rbx
0x18000fbe5  mov     [rsp+arg_8], rdx
0x18000fbea  push    rbp
0x18000fbeb  push    rsi
0x18000fbec  push    rdi
0x18000fbed  push    r12
0x18000fbef  push    r13
0x18000fbf1  push    r14
0x18000fbf3  push    r15
0x18000fbf5  sub     rsp, 60h
0x18000fbf9  movsxd  rbp, [rsp+98h+arg_28]
0x18000fc01  mov     r15, r8
0x18000fc04  movsxd  r12, dword ptr [rdx+4]
0x18000fc08  mov     rsi, r9
0x18000fc0b  imul    r14, rbp, 3100h
0x18000fc12  movaps  [rsp+98h+var_48], xmm6
0x18000fc17  movaps  [rsp+98h+var_58], xmm7
0x18000fc1c  movaps  [rsp+98h+var_68], xmm8
0x18000fc22  mov     ebx, [r14+rcx]
0x18000fc26  lea     r8, [r14+rcx]; struct CErrorConcealment::tagSPECTRUM_DATA *
0x18000fc2a  add     ebx, 3
0x18000fc2d  mov     r9, rdx
0x18000fc30  mov     rdi, rcx
0x18000fc33  and     ebx, 80000003h
0x18000fc39  jge     short loc_18000FC42
0x18000fc3b  dec     ebx
0x18000fc3d  or      ebx, 0FFFFFFFCh
0x18000fc40  inc     ebx
0x18000fc42  cmp     dword ptr [r8+30FCh], 0
0x18000fc4a  jnz     short loc_18000FC59
0x18000fc4c  call    ?predictEnergies@CErrorConcealment@@IEAAXAEBUMPEG_INFO@@PEAUtagSPECTRUM_DATA@1@@Z; CErrorConcealment::predictEnergies(MPEG_INFO const &,CErrorConcealment::tagSPECTRUM_DATA *)
0x18000fc51  mov     r9, [rsp+98h+arg_8]
0x18000fc59  movsxd  rax, [rsp+98h+arg_20]
0x18000fc61  lea     r10, ?sfBandIndex@@3QAY02$$CBU_unnamed_type_SF_BAND_INDEX_@@A; _unnamed_type_SF_BAND_INDEX_ const (near * sfBandIndex)[3]
0x18000fc68  imul    rdx, rbp, 0E8h
0x18000fc6f  imul    r8, rax, 6Ch ; 'l'
0x18000fc73  movsxd  rax, ebx
0x18000fc76  imul    rcx, rax, 9CCh
0x18000fc7d  add     r8, r15
0x18000fc80  mov     [rsp+98h+var_78], rdx
0x18000fc85  add     rcx, r14
0x18000fc88  mov     [rsp+98h+var_70], r8
0x18000fc8d  xor     r14d, r14d
0x18000fc90  mov     [rsp+98h+arg_10], r12
0x18000fc98  movups  xmm0, xmmword ptr [rcx+rdi+4]
0x18000fc9d  movups  xmmword ptr [rdx+r8+18h], xmm0
0x18000fca3  movups  xmm1, xmmword ptr [rcx+rdi+14h]
0x18000fca8  movups  xmmword ptr [rdx+r8+28h], xmm1
0x18000fcae  movups  xmm0, xmmword ptr [rcx+rdi+24h]
0x18000fcb3  movups  xmmword ptr [rdx+r8+38h], xmm0
0x18000fcb9  movups  xmm1, xmmword ptr [rcx+rdi+34h]
0x18000fcbe  movups  xmmword ptr [rdx+r8+48h], xmm1
0x18000fcc4  movups  xmm0, xmmword ptr [rcx+rdi+44h]
0x18000fcc9  movups  xmmword ptr [rdx+r8+58h], xmm0
0x18000fccf  movups  xmm1, xmmword ptr [rcx+rdi+54h]
0x18000fcd4  movups  xmmword ptr [rdx+r8+68h], xmm1
0x18000fcda  movups  xmm0, xmmword ptr [rcx+rdi+60h]
0x18000fcdf  movups  xmmword ptr [rdx+r8+74h], xmm0
0x18000fce5  movsxd  rcx, dword ptr [r9+18h]
0x18000fce9  mov     edx, r14d
0x18000fcec  mov     r8, r12
0x18000fcef  lea     rax, [r12+rcx*2]
0x18000fcf3  add     rcx, rax
0x18000fcf6  imul    rax, rcx, 94h
0x18000fcfd  cmp     [rax+r10], edx
0x18000fd01  jle     short loc_18000FD24
0x18000fd03  movsxd  rax, edx
0x18000fd06  inc     edx
0x18000fd08  mov     [rsi+rax*4], r14d
0x18000fd0c  movsxd  rcx, dword ptr [r9+18h]
0x18000fd10  lea     rax, [r12+rcx*2]
0x18000fd14  add     rcx, rax
0x18000fd17  imul    rax, rcx, 94h
0x18000fd1e  cmp     edx, [rax+r10]
0x18000fd22  jl      short loc_18000FD03
0x18000fd24  movss   xmm6, cs:__xmm@80000000800000008000000080000000
0x18000fd2c  mov     r13d, r14d
0x18000fd2f  movsd   xmm7, cs:__real@3fe0000000000000
0x18000fd37  xorps   xmm8, xmm8
0x18000fd3b  imul    r15, rbp, 0C40h
0x18000fd42  mov     [rsp+98h+arg_0], r14
0x18000fd4a  nop     word ptr [rax+rax+00h]
0x18000fd50  movsxd  rcx, dword ptr [r9+18h]
0x18000fd54  lea     rax, [r8+rcx*2]
0x18000fd58  add     rcx, rax
0x18000fd5b  lea     rax, [r15+r14]
0x18000fd5f  movss   xmm4, dword ptr [rdi+rax*4+30A0h]
0x18000fd68  imul    rcx, 25h ; '%'
0x18000fd6c  cvtps2pd xmm4, xmm4
0x18000fd6f  add     rcx, r14
0x18000fd72  comisd  xmm4, xmm8
0x18000fd77  movsxd  r12, dword ptr [r10+rcx*4]
0x18000fd7b  mov     ebp, [r10+rcx*4+4]
0x18000fd80  mov     ebx, r12d
0x18000fd83  jbe     loc_180010068
0x18000fd89  cmp     r12d, ebp
0x18000fd8c  jge     loc_18001008B
0x18000fd92  movaps  xmm3, xmm8
0x18000fd96  test    r13d, r13d
0x18000fd99  jz      short loc_18000FDE4
0x18000fd9b  nop     dword ptr [rax+rax+00h]
0x18000fda0  lea     rdx, [rdi+62ECh]; int *
0x18000fda7  mov     rcx, rdi; this
0x18000fdaa  call    ?ran3@CErrorConcealment@@IEAAMPEAJ@Z; CErrorConcealment::ran3(long *)
0x18000fdaf  xorps   xmm1, xmm1
0x18000fdb2  movsxd  rax, ebx
0x18000fdb5  cvtss2sd xmm1, xmm0
0x18000fdb9  inc     ebx
0x18000fdbb  subsd   xmm1, xmm7
0x18000fdbf  cvtpd2ps xmm2, xmm1
0x18000fdc3  movss   dword ptr [rsi+rax*4], xmm2
0x18000fdc8  mulss   xmm2, xmm2
0x18000fdcc  cvtps2pd xmm0, xmm2
0x18000fdcf  addsd   xmm3, xmm0
0x18000fdd3  cmp     ebx, ebp
0x18000fdd5  jl      short loc_18000FDA0
0x18000fdd7  mov     r14, [rsp+98h+arg_0]
0x18000fddf  jmp     loc_18000FF4F
0x18000fde4  mov     eax, ebp
0x18000fde6  sub     eax, r12d
0x18000fde9  cmp     eax, 4
0x18000fdec  jl      loc_18000FF05
0x18000fdf2  lea     edx, [rbp-3]
0x18000fdf5  nop     word ptr [rax+rax+00000000h]
0x18000fe00  movsxd  rcx, ebx
0x18000fe03  lea     rax, [r15+rcx]
0x18000fe07  movss   xmm0, dword ptr [rdi+rax*4+27A0h]
0x18000fe10  mov     eax, [rdi+62F4h]
0x18000fe16  test    eax, eax
0x18000fe18  jns     short loc_18000FE24
0x18000fe1a  xor     eax, 9
0x18000fe1d  add     eax, eax
0x18000fe1f  or      eax, 1
0x18000fe22  jmp     short loc_18000FE29
0x18000fe24  add     eax, eax
0x18000fe26  xorps   xmm0, xmm6
0x18000fe29  mov     [rdi+62F4h], eax
0x18000fe2f  lea     rax, [r15+rcx]
0x18000fe33  movss   dword ptr [rsi+rcx*4], xmm0
0x18000fe38  mulss   xmm0, xmm0
0x18000fe3c  cvtss2sd xmm0, xmm0
0x18000fe40  addsd   xmm3, xmm0
0x18000fe44  movss   xmm0, dword ptr [rdi+rax*4+27A4h]
0x18000fe4d  mov     eax, [rdi+62F4h]
0x18000fe53  test    eax, eax
0x18000fe55  jns     short loc_18000FE61
0x18000fe57  xor     eax, 9
0x18000fe5a  add     eax, eax
0x18000fe5c  or      eax, 1
0x18000fe5f  jmp     short loc_18000FE66
0x18000fe61  add     eax, eax
0x18000fe63  xorps   xmm0, xmm6
0x18000fe66  mov     [rdi+62F4h], eax
0x18000fe6c  lea     rax, [r15+rcx]
0x18000fe70  movss   dword ptr [rsi+rcx*4+4], xmm0
0x18000fe76  mulss   xmm0, xmm0
0x18000fe7a  cvtss2sd xmm0, xmm0
0x18000fe7e  addsd   xmm3, xmm0
0x18000fe82  movss   xmm0, dword ptr [rdi+rax*4+27A8h]
0x18000fe8b  mov     eax, [rdi+62F4h]
0x18000fe91  test    eax, eax
0x18000fe93  jns     short loc_18000FE9F
0x18000fe95  xor     eax, 9
0x18000fe98  add     eax, eax
0x18000fe9a  or      eax, 1
0x18000fe9d  jmp     short loc_18000FEA4
0x18000fe9f  add     eax, eax
0x18000fea1  xorps   xmm0, xmm6
0x18000fea4  mov     [rdi+62F4h], eax
0x18000feaa  lea     rax, [r15+rcx]
0x18000feae  movss   dword ptr [rsi+rcx*4+8], xmm0
0x18000feb4  mulss   xmm0, xmm0
0x18000feb8  cvtss2sd xmm0, xmm0
0x18000febc  addsd   xmm3, xmm0
0x18000fec0  movss   xmm0, dword ptr [rdi+rax*4+27ACh]
0x18000fec9  mov     eax, [rdi+62F4h]
0x18000fecf  test    eax, eax
0x18000fed1  jns     short loc_18000FEDD
0x18000fed3  xor     eax, 9
0x18000fed6  add     eax, eax
0x18000fed8  or      eax, 1
0x18000fedb  jmp     short loc_18000FEE2
0x18000fedd  add     eax, eax
0x18000fedf  xorps   xmm0, xmm6
0x18000fee2  mov     [rdi+62F4h], eax
0x18000fee8  add     ebx, 4
0x18000feeb  movss   dword ptr [rsi+rcx*4+0Ch], xmm0
0x18000fef1  mulss   xmm0, xmm0
0x18000fef5  cvtss2sd xmm0, xmm0
0x18000fef9  addsd   xmm3, xmm0
0x18000fefd  cmp     ebx, edx
0x18000feff  jl      loc_18000FE00
0x18000ff05  cmp     ebx, ebp
0x18000ff07  jge     short loc_18000FF4F
0x18000ff09  movsxd  rcx, ebx
0x18000ff0c  lea     rax, [r15+rcx]
0x18000ff10  movss   xmm0, dword ptr [rdi+rax*4+27A0h]
0x18000ff19  mov     eax, [rdi+62F4h]
0x18000ff1f  test    eax, eax
0x18000ff21  jns     short loc_18000FF2D
0x18000ff23  xor     eax, 9
0x18000ff26  add     eax, eax
0x18000ff28  or      eax, 1
0x18000ff2b  jmp     short loc_18000FF32
0x18000ff2d  add     eax, eax
0x18000ff2f  xorps   xmm0, xmm6
0x18000ff32  mov     [rdi+62F4h], eax
0x18000ff38  inc     ebx
0x18000ff3a  movss   dword ptr [rsi+rcx*4], xmm0
0x18000ff3f  mulss   xmm0, xmm0
0x18000ff43  cvtss2sd xmm0, xmm0
0x18000ff47  addsd   xmm3, xmm0
0x18000ff4b  cmp     ebx, ebp
0x18000ff4d  jl      short loc_18000FF09
0x18000ff4f  ucomisd xmm3, xmm8
0x18000ff54  jp      short loc_18000FF5C
0x18000ff56  jz      loc_18001008B
0x18000ff5c  divsd   xmm4, xmm3
0x18000ff60  xorps   xmm0, xmm0
0x18000ff63  ucomisd xmm0, xmm4
0x18000ff67  ja      short loc_18000FF72
0x18000ff69  xorps   xmm0, xmm0
0x18000ff6c  sqrtsd  xmm0, xmm4
0x18000ff70  jmp     short loc_18000FF7A
0x18000ff72  movaps  xmm0, xmm4; X
0x18000ff75  call    sqrt
0x18000ff7a  xorps   xmm2, xmm2
0x18000ff7d  mov     eax, ebp
0x18000ff7f  cvtsd2ss xmm2, xmm0
0x18000ff83  sub     eax, r12d
0x18000ff86  mov     ebx, r12d
0x18000ff89  movaps  xmm3, xmm2
0x18000ff8c  shufps  xmm3, xmm3, 0
0x18000ff90  cmp     eax, 10h
0x18000ff93  jb      short loc_18000FFF7
0x18000ff95  and     eax, 8000000Fh
0x18000ff9a  jge     short loc_18000FFA3
0x18000ff9c  dec     eax
0x18000ff9e  or      eax, 0FFFFFFF0h
0x18000ffa1  inc     eax
0x18000ffa3  mov     ecx, ebp
0x18000ffa5  sub     ecx, eax
0x18000ffa7  nop     word ptr [rax+rax+00000000h]
0x18000ffb0  movsxd  rax, ebx
0x18000ffb3  movaps  xmm1, xmm3
0x18000ffb6  add     ebx, 10h
0x18000ffb9  movups  xmm0, xmmword ptr [rsi+rax*4]
0x18000ffbd  mulps   xmm0, xmm3
0x18000ffc0  movups  xmmword ptr [rsi+rax*4], xmm0
0x18000ffc4  movups  xmm0, xmmword ptr [rsi+rax*4+10h]
0x18000ffc9  mulps   xmm0, xmm3
0x18000ffcc  movups  xmmword ptr [rsi+rax*4+10h], xmm0
0x18000ffd1  movups  xmm0, xmmword ptr [rsi+rax*4+20h]
0x18000ffd6  mulps   xmm1, xmm0
0x18000ffd9  movups  xmmword ptr [rsi+rax*4+20h], xmm1
0x18000ffde  movups  xmm0, xmmword ptr [rsi+rax*4+30h]
0x18000ffe3  mulps   xmm0, xmm3
0x18000ffe6  movups  xmmword ptr [rsi+rax*4+30h], xmm0
0x18000ffeb  cmp     ebx, ecx
0x18000ffed  jl      short loc_18000FFB0
0x18000ffef  cmp     ebx, ebp
0x18000fff1  jge     loc_18001008B
0x18000fff7  mov     eax, ebp
0x18000fff9  sub     eax, ebx
0x18000fffb  cmp     eax, 4
0x18000fffe  jl      short loc_180010050
0x180010000  lea     ecx, [rbp-3]
0x180010003  movsxd  rax, ebx
0x180010006  movaps  xmm0, xmm2
0x180010009  movaps  xmm1, xmm2
0x18001000c  add     ebx, 4
0x18001000f  mulss   xmm0, dword ptr [rsi+rax*4]
0x180010014  mulss   xmm1, dword ptr [rsi+rax*4+4]
0x18001001a  movss   dword ptr [rsi+rax*4], xmm0
0x18001001f  movaps  xmm0, xmm2
0x180010022  mulss   xmm0, dword ptr [rsi+rax*4+8]
0x180010028  movss   dword ptr [rsi+rax*4+4], xmm1
0x18001002e  movaps  xmm1, xmm2
0x180010031  mulss   xmm1, dword ptr [rsi+rax*4+0Ch]
0x180010037  movss   dword ptr [rsi+rax*4+8], xmm0
0x18001003d  movss   dword ptr [rsi+rax*4+0Ch], xmm1
0x180010043  cmp     ebx, ecx
0x180010045  jl      short loc_180010003
0x180010047  cmp     ebx, ebp
0x180010049  jge     short loc_18001008B
0x18001004b  nop     dword ptr [rax+rax+00h]
0x180010050  movsxd  rax, ebx
0x180010053  movaps  xmm0, xmm2
0x180010056  inc     ebx
0x180010058  mulss   xmm0, dword ptr [rsi+rax*4]
0x18001005d  movss   dword ptr [rsi+rax*4], xmm0
0x180010062  cmp     ebx, ebp
0x180010064  jl      short loc_180010050
0x180010066  jmp     short loc_18001008B
0x180010068  cmp     r12d, ebp
0x18001006b  jge     short loc_18001008B
0x18001006d  nop     dword ptr [rax]
0x180010070  inc     ebx
0x180010072  cmp     ebx, ebp
0x180010074  jl      short loc_180010070
  ... truncated ...
```
