# MotionTurboJpeg::CMJPGMFTDataHandler::DecompressYUV422(MotionTurboJpeg::INSTINFO *,MFBUFFER::CBuffer,tagBITMAPINFOHEADER const * const,__int64,uchar *,MFBUFFER::CBuffer,ulong *,uchar)

- ea: `0x1800206fc`
- end: `0x180020e0c`
- name: `?DecompressYUV422@CMJPGMFTDataHandler@MotionTurboJpeg@@AEAAKPEAUINSTINFO@2@VCBuffer@MFBUFFER@@QEBUtagBITMAPINFOHEADER@@_JPEAE1PEAKE@Z`
- size: `1808`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *, size_t Size, char *Src, unsigned __int64 *, _DWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ff0c`

## callees

- `0x180018fb4`
- `0x18001b380`
- `0x18001c784`
- `0x18001da24`
- `0x1800206fc`
- `0x180020e14`
- `0x180024220`
- `0x180024bf4`
- `0x18003a794`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall MotionTurboJpeg::CMJPGMFTDataHandler::DecompressYUV422(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _DWORD *a4,
        size_t Size,
        char *Src,
        unsigned __int64 *a7,
        _DWORD *a8)
{
  size_t v9; // rsi
  char *v10; // rdi
  __int64 v11; // r12
  unsigned __int64 v12; // rax
  size_t *v13; // r13
  _DWORD *v14; // r14
  unsigned int v15; // ecx
  char v16; // dl
  unsigned __int64 v17; // r12
  char *v18; // r15
  char *v19; // rax
  char *v20; // rdi
  unsigned __int64 *v21; // rsi
  char *v22; // r13
  bool v23; // r8
  unsigned int v24; // edx
  unsigned int v25; // r13d
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // r9
  __int64 v28; // r8
  unsigned __int64 v29; // rsi
  char *v30; // r9
  __int64 v31; // r15
  unsigned __int64 v32; // rdx
  char v33; // di
  unsigned int v34; // r15d
  bool v35; // zf
  unsigned int v36; // ecx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  unsigned __int64 v40; // rdx
  unsigned int v41; // eax
  int v42; // r15d
  int v43; // r14d
  char *v44; // r8
  char *v45; // rdx
  int v46; // ebx
  char *v47; // r8
  char *v48; // rdx
  unsigned int v49; // r8d
  unsigned int v50; // ecx
  char v51; // dl
  int v52; // eax
  int v53; // esi
  char *v54; // rax
  unsigned int v55; // eax
  char *v57; // [rsp+30h] [rbp-D0h] BYREF
  int v58; // [rsp+38h] [rbp-C8h]
  char *v59; // [rsp+40h] [rbp-C0h] BYREF
  int v60; // [rsp+48h] [rbp-B8h]
  unsigned int v61; // [rsp+50h] [rbp-B0h] BYREF
  int v62; // [rsp+58h] [rbp-A8h]
  unsigned int v63; // [rsp+5Ch] [rbp-A4h]
  char *v64; // [rsp+60h] [rbp-A0h]
  size_t v65; // [rsp+68h] [rbp-98h]
  __int64 v66; // [rsp+70h] [rbp-90h]
  char *v67; // [rsp+78h] [rbp-88h]
  size_t v68; // [rsp+80h] [rbp-80h]
  _QWORD v69[18]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v70[18]; // [rsp+120h] [rbp+20h] BYREF

  v9 = Size;
  v10 = Src;
  v68 = Size;
  *a8 = 0;
  v67 = Src;
  v57 = 0;
  v59 = 0;
  if ( !*(_BYTE *)(a2 + 6864) )
    return 4294967294LL;
  v63 = a4[1];
  if ( v63 > 0xFFDC )
    return 4294967294LL;
  v11 = (int)a4[2];
  v62 = v11;
  if ( (unsigned int)v11 > 0xFFDC )
    return 4294967294LL;
  v12 = Size * v11;
  v58 = a4[4];
  v65 = Size * v11;
  if ( v58 == 842094158 )
    v12 = (3 * v12) >> 1;
  v13 = a7;
  if ( v12 > *a7 )
    return 4294967294LL;
  v14 = (_DWORD *)(a2 + 176);
  *(_DWORD *)(a2 + 268) = *(_BYTE *)(a2 + 6866) != 0;
  *(_BYTE *)(a2 + 272) = *(_BYTE *)(a2 + 6865);
  *(_BYTE *)(a2 + 3584) = 1;
  jpeg_start_decompress(a2 + 176);
  v15 = *(_DWORD *)(a2 + 296);
  v16 = *(_BYTE *)(a2 + 1736);
  if ( v16 )
    v15 *= 2;
  if ( v15 > (unsigned int)v11 || *(_DWORD *)(a2 + 292) > v63 )
    return 4294967294LL;
  v60 = 0;
  if ( !v16 )
  {
    *a8 = 0;
    v17 = Size;
LABEL_13:
    v18 = Src;
    v57 = Src;
    goto LABEL_17;
  }
  if ( v16 != 1 )
  {
    *a8 = 2;
    v17 = 2 * Size;
    goto LABEL_13;
  }
  *a8 = 1;
  v17 = 2 * Size;
  v18 = &Src[Size];
  v60 = 1;
  v57 = &Src[Size];
LABEL_17:
  if ( v58 == 842094158 )
    v19 = &v18[v65];
  else
    v19 = 0;
  v64 = v19;
  v59 = v19;
  if ( *(_DWORD *)(a2 + 328) < *(_DWORD *)(a2 + 296) )
  {
    v20 = v64;
    v21 = a7;
    v22 = v64;
    LODWORD(v64) = v58 == 842094158;
    do
    {
      memset_0(v70, 0, 0x88u);
      memset_0(v69, 0, 0x88u);
      v23 = v58 != 842094158 || (unsigned __int64)v22 >= v21[1] && *v21 >= (unsigned __int64)&v22[-v21[1]];
      v24 = 8;
      if ( *(_BYTE *)(a2 + 3584) )
      {
        v24 = *(_DWORD *)(a2 + 556) * *(_DWORD *)(a2 + 560);
        if ( v24 > 0x10 )
          v24 = 16;
      }
      v25 = v24 >> (char)v64;
      v26 = v21[1];
      if ( !(v24 >> (char)v64) )
        v25 = 1;
      if ( (unsigned __int64)v18 < v26 )
        break;
      v27 = *v21;
      if ( *v21 < (unsigned __int64)&v18[-v26] || !v23 )
        break;
      LODWORD(v66) = (_DWORD)v64;
      v28 = 0;
      v29 = v27;
      do
      {
        v30 = &v18[v17 * (unsigned int)v28];
        if ( (unsigned __int64)v30 < v26 )
          break;
        if ( (unsigned __int64)&v30[v17] < v26 )
          break;
        if ( (unsigned __int64)&v30[v17] > v26 + v29 )
          break;
        v70[v28] = v30;
        v28 = (unsigned int)(v28 + 1);
      }
      while ( (unsigned int)v28 < v24 );
      if ( v58 == 842094158 )
      {
        v31 = 0;
        do
        {
          v32 = (unsigned __int64)&v20[v17 * (unsigned int)v31];
          if ( v32 < v26 )
            break;
          if ( v32 + v17 < v26 )
            break;
          if ( v32 + v17 > v26 + v29 )
            break;
          v69[v31] = v32;
          v31 = (unsigned int)(v31 + 1);
        }
        while ( (unsigned int)v31 < v25 );
        v33 = v66;
        v14 = (_DWORD *)(a2 + 176);
        v34 = (_DWORD)v31 << v66;
        if ( (unsigned int)v28 < v34 )
          v34 = v28;
      }
      else
      {
        v33 = v66;
        v34 = v28;
      }
      v21 = a7;
      v35 = *(_DWORD *)(a2 + 456) == 8;
      v61 = 0;
      if ( !v35 )
      {
        *(_DWORD *)(*(_QWORD *)v14 + 40LL) = 15;
        *(_DWORD *)(*(_QWORD *)v14 + 44LL) = v14[70];
        (**(void (__fastcall ***)(_DWORD *))v14)(v14);
      }
      if ( v14[9] != 205 )
      {
        *(_DWORD *)(*(_QWORD *)v14 + 40LL) = 20;
        *(_DWORD *)(*(_QWORD *)v14 + 44LL) = v14[9];
        (**(void (__fastcall ***)(_DWORD *))v14)(v14);
      }
      v36 = v14[38];
      if ( v36 < v14[30] )
      {
        v38 = *((_QWORD *)v14 + 2);
        if ( v38 )
        {
          *(_DWORD *)(v38 + 8) = v36;
          *(_DWORD *)(*((_QWORD *)v14 + 2) + 12LL) = v14[30];
          (**((void (__fastcall ***)(_DWORD *))v14 + 2))(v14);
        }
        v39 = *((_QWORD *)v14 + 65);
        v61 = 0;
        if ( !*(_QWORD *)(v39 + 8) )
        {
          *(_DWORD *)(*(_QWORD *)v14 + 40LL) = 15;
          *(_DWORD *)(*(_QWORD *)v14 + 44LL) = v14[70];
          (**(void (__fastcall ***)(_DWORD *))v14)(v14);
        }
        (*(void (__fastcall **)(_DWORD *, _QWORD *, _QWORD *, unsigned int *, unsigned int))(*((_QWORD *)v14 + 65) + 8LL))(
          v14,
          v70,
          v69,
          &v61,
          v34);
        v37 = v61;
        v14[38] += v61;
      }
      else
      {
        *(_DWORD *)(*(_QWORD *)v14 + 40LL) = 123;
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 0xFFFFFFFFLL);
        v37 = 0;
      }
      v40 = (unsigned int)v37;
      v18 = &v57[v17 * v37];
      v41 = *(_DWORD *)(a2 + 296);
      v57 = v18;
      v20 = &v59[v17 * (v40 >> v33)];
      v22 = v20;
      v59 = v20;
    }
    while ( *(_DWORD *)(a2 + 328) < v41 );
    v10 = v67;
    v9 = v68;
    v13 = a7;
  }
  if ( *(_DWORD *)(a2 + 328) >= *(_DWORD *)(a2 + 296) )
    jpeg_finish_decompress(v14);
  else
    jpeg_abort_decompress(v14);
  if ( !*(_BYTE *)(a2 + 1736) )
    return 0;
  if ( (unsigned int)jpeg_read_header(v14) != 1 )
  {
    v42 = v62;
    v43 = 2;
    v57 = v10;
    v44 = v10;
    if ( v62 >= 2 )
    {
      v45 = v10;
      do
      {
        if ( (unsigned __int64)&v45[v9] >= v13[1] && v9 <= *v13 && *v13 - v9 >= (unsigned __int64)&v45[v9 - v13[1]] )
        {
          memcpy_0(&v45[v9], v45, v9);
          v44 = v57;
        }
        v44 += 2 * v9;
        v43 += 2;
        v57 = v44;
        v45 = v44;
      }
      while ( v43 <= v42 );
    }
    if ( v58 == 842094158 )
    {
      v46 = 4;
      v47 = &v10[v65];
      v59 = &v10[v65];
      if ( v42 >= 4 )
      {
        v48 = &v10[v65];
        do
        {
          if ( (unsigned __int64)&v48[v9] >= v13[1] && v9 <= *v13 && *v13 - v9 >= (unsigned __int64)&v48[v9 - v13[1]] )
          {
            memcpy_0(&v48[v9], v48, v9);
            v47 = v59;
          }
          v47 += 2 * v9;
          v46 += 4;
          v59 = v47;
          v48 = v47;
        }
        while ( v46 <= v42 );
      }
    }
    return 0;
  }
  *(_DWORD *)(a2 + 268) = *(_BYTE *)(a2 + 6866) != 0;
  *(_BYTE *)(a2 + 272) = *(_BYTE *)(a2 + 6865);
  jpeg_start_decompress(v14);
  v49 = *(_DWORD *)(a2 + 296);
  v50 = v49;
  v51 = *(_BYTE *)(a2 + 1736);
  if ( v51 )
    v50 = 2 * v49;
  if ( v50 <= v62 && *(_DWORD *)(a2 + 292) <= v63 )
  {
    switch ( v51 )
    {
      case 0:
        v17 = v9;
LABEL_94:
        v57 = v10;
LABEL_95:
        v53 = v58;
        if ( v58 == 842094158 )
          v54 = &v10[v65];
        else
          v54 = 0;
        v59 = v54;
        v55 = *(_DWORD *)(a2 + 328);
        if ( v55 < v49 )
        {
          while ( (unsigned __int64)v10 >= v13[1] && v17 <= *v13 && *v13 - v17 >= (unsigned __int64)&v10[-v13[1]] )
          {
            jpeg_read_scanlines(v14, &v57, &v59, 1);
            v10 = &v57[v17];
            v57 += v17;
            if ( v53 == 842094158 && (*(_BYTE *)(a2 + 328) & 1) != 0 )
              v59 += v17;
            v55 = *(_DWORD *)(a2 + 328);
            if ( v55 >= *(_DWORD *)(a2 + 296) )
              goto LABEL_110;
          }
        }
        if ( v55 >= *(_DWORD *)(a2 + 296) )
LABEL_110:
          jpeg_finish_decompress(v14);
        else
          jpeg_abort_decompress(v14);
        return 0;
      case 1:
        v52 = v60;
        if ( !v60 )
        {
          v10 += v9;
LABEL_93:
          v17 = 2 * v9;
          goto LABEL_94;
        }
        break;
      case 2:
        goto LABEL_93;
      default:
        v52 = v60;
        break;
    }
    if ( v52 != 1 )
    {
      v10 = v57;
      goto LABEL_95;
    }
    goto LABEL_93;
  }
  return 4294967294LL;
}

```

## disassembly

```asm
0x1800206fc  mov     [rsp-8+arg_0], rbx
0x180020701  push    rbp
0x180020702  push    rsi
0x180020703  push    rdi
0x180020704  push    r12
0x180020706  push    r13
0x180020708  push    r14
0x18002070a  push    r15
0x18002070c  lea     rbp, [rsp-0C0h]
0x180020714  sub     rsp, 1C0h
0x18002071b  mov     rax, cs:__security_cookie
0x180020722  xor     rax, rsp
0x180020725  mov     [rbp+0F0h+var_40], rax
0x18002072c  mov     r15, [rbp+0F0h+arg_38]
0x180020733  mov     rbx, rdx
0x180020736  mov     rsi, [rbp+0F0h+Size]
0x18002073d  xor     edx, edx
0x18002073f  mov     rdi, [rbp+0F0h+Src]
0x180020746  mov     [rbp+0F0h+var_170], rsi
0x18002074a  mov     [r15], edx
0x18002074d  mov     [rsp+1F0h+var_178], rdi
0x180020752  mov     [rsp+1F0h+var_1C0], rdx
0x180020757  mov     [rsp+1F0h+var_1B0], rdx
0x18002075c  cmp     [rbx+1AD0h], dl
0x180020762  jz      loc_180020DDD
0x180020768  mov     eax, [r9+4]
0x18002076c  mov     ecx, 0FFDCh
0x180020771  mov     [rsp+1F0h+var_194], eax
0x180020775  cmp     eax, ecx
0x180020777  ja      loc_180020DDD
0x18002077d  movsxd  r12, dword ptr [r9+8]
0x180020781  mov     [rsp+1F0h+var_198], r12d
0x180020786  cmp     r12d, ecx
0x180020789  ja      loc_180020DDD
0x18002078f  mov     ecx, [r9+10h]
0x180020793  mov     rax, r12
0x180020796  imul    rax, rsi
0x18002079a  mov     [rsp+1F0h+var_1B8], ecx
0x18002079e  mov     [rsp+1F0h+var_188], rax
0x1800207a3  cmp     ecx, 3231564Eh
0x1800207a9  jnz     short loc_1800207B2
0x1800207ab  lea     rax, [rax+rax*2]
0x1800207af  shr     rax, 1
0x1800207b2  mov     r13, [rbp+0F0h+arg_30]
0x1800207b9  cmp     rax, [r13+0]
0x1800207bd  ja      loc_180020DDD
0x1800207c3  cmp     [rbx+1AD2h], dl
0x1800207c9  lea     r14, [rbx+0B0h]
0x1800207d0  mov     eax, edx
0x1800207d2  mov     rcx, r14
0x1800207d5  setnz   al
0x1800207d8  mov     [r14+5Ch], eax
0x1800207dc  mov     al, [rbx+1AD1h]
0x1800207e2  mov     [rbx+110h], al
0x1800207e8  mov     byte ptr [rbx+0E00h], 1
0x1800207ef  call    jpeg_start_decompress
0x1800207f4  mov     ecx, [rbx+128h]
0x1800207fa  mov     dl, [rbx+6C8h]
0x180020800  test    dl, dl
0x180020802  lea     eax, [rcx+rcx]
0x180020805  cmovnz  ecx, eax
0x180020808  cmp     ecx, r12d
0x18002080b  ja      loc_180020DDD
0x180020811  mov     eax, [rsp+1F0h+var_194]
0x180020815  cmp     [rbx+124h], eax
0x18002081b  ja      loc_180020DDD
0x180020821  mov     [rsp+1F0h+var_1A8], 0
0x180020829  mov     eax, 2
0x18002082e  test    dl, dl
0x180020830  jnz     short loc_180020846
0x180020832  mov     dword ptr [r15], 0
0x180020839  mov     r12, rsi
0x18002083c  mov     r15, rdi
0x18002083f  mov     [rsp+1F0h+var_1C0], rdi
0x180020844  jmp     short loc_18002087A
0x180020846  mov     ecx, 1
0x18002084b  cmp     dl, cl
0x18002084d  jnz     short loc_180020865
0x18002084f  mov     [r15], ecx
0x180020852  lea     r12, [rsi+rsi]
0x180020856  lea     r15, [rdi+rsi]
0x18002085a  mov     [rsp+1F0h+var_1A8], ecx
0x18002085e  mov     [rsp+1F0h+var_1C0], r15
0x180020863  jmp     short loc_18002087A
0x180020865  xor     r12d, r12d
0x180020868  cmp     dl, al
0x18002086a  jb      short loc_180020875
0x18002086c  mov     [r15], eax
0x18002086f  lea     r12, [rsi+rsi]
0x180020873  jmp     short loc_18002083C
0x180020875  mov     r15, [rsp+1F0h+var_1C0]
0x18002087a  mov     ecx, [rsp+1F0h+var_1B8]
0x18002087e  mov     edx, 3231564Eh
0x180020883  cmp     ecx, edx
0x180020885  jz      short loc_18002088B
0x180020887  xor     eax, eax
0x180020889  jmp     short loc_180020893
0x18002088b  mov     rax, [rsp+1F0h+var_188]
0x180020890  add     rax, r15
0x180020893  mov     [rsp+1F0h+var_190], rax
0x180020898  mov     [rsp+1F0h+var_1B0], rax
0x18002089d  mov     eax, [rbx+128h]
0x1800208a3  cmp     [rbx+148h], eax
0x1800208a9  jnb     loc_180020B87
0x1800208af  mov     rdi, [rsp+1F0h+var_190]
0x1800208b4  xor     eax, eax
0x1800208b6  mov     rsi, [rbp+0F0h+arg_30]
0x1800208bd  cmp     ecx, edx
0x1800208bf  mov     r13, rdi
0x1800208c2  setz    al
0x1800208c5  mov     dword ptr [rsp+1F0h+var_190], eax
0x1800208c9  xor     edx, edx; Val
0x1800208cb  lea     rcx, [rbp+0F0h+var_D0]; void *
0x1800208cf  mov     r8d, 88h; Size
0x1800208d5  call    memset_0
0x1800208da  xor     edx, edx; Val
0x1800208dc  lea     rcx, [rbp+0F0h+var_160]; void *
0x1800208e0  mov     r8d, 88h; Size
0x1800208e6  call    memset_0
0x1800208eb  cmp     [rsp+1F0h+var_1B8], 3231564Eh
0x1800208f3  jnz     short loc_18002090E
0x1800208f5  cmp     r13, [rsi+8]
0x1800208f9  jb      short loc_180020904
0x1800208fb  sub     r13, [rsi+8]
0x1800208ff  cmp     [rsi], r13
0x180020902  jnb     short loc_18002090E
0x180020904  xor     r8b, r8b
0x180020907  mov     eax, 1
0x18002090c  jmp     short loc_180020916
0x18002090e  mov     eax, 1
0x180020913  mov     r8b, al
0x180020916  cmp     byte ptr [rbx+0E00h], 0
0x18002091d  mov     edx, 8
0x180020922  jz      short loc_18002093B
0x180020924  mov     edx, [rbx+230h]
0x18002092a  mov     ecx, 10h
0x18002092f  imul    edx, [rbx+22Ch]
0x180020936  cmp     edx, ecx
0x180020938  cmova   edx, ecx
0x18002093b  mov     r10d, dword ptr [rsp+1F0h+var_190]
0x180020940  mov     r13d, edx
0x180020943  mov     ecx, r10d
0x180020946  shr     r13d, cl
0x180020949  mov     rcx, [rsi+8]
0x18002094d  cmp     r13d, eax
0x180020950  cmovb   r13d, eax
0x180020954  cmp     r15, rcx
0x180020957  jb      loc_180020B77
0x18002095d  mov     r9, [rsi]
0x180020960  mov     rax, r15
0x180020963  sub     rax, rcx
0x180020966  cmp     r9, rax
0x180020969  jb      loc_180020B77
0x18002096f  test    r8b, r8b
0x180020972  jz      loc_180020B77
0x180020978  mov     dword ptr [rsp+1F0h+var_180], r10d
0x18002097d  xor     r8d, r8d
0x180020980  mov     rsi, r9
0x180020983  mov     r9d, r8d
0x180020986  imul    r9, r12
0x18002098a  add     r9, r15
0x18002098d  cmp     r9, rcx
0x180020990  jb      short loc_1800209B1
0x180020992  lea     r10, [r9+r12]
0x180020996  cmp     r10, rcx
0x180020999  jb      short loc_1800209B1
0x18002099b  lea     rax, [rcx+rsi]
0x18002099f  cmp     r10, rax
0x1800209a2  ja      short loc_1800209B1
0x1800209a4  mov     [rbp+r8*8+0F0h+var_D0], r9
0x1800209a9  inc     r8d
0x1800209ac  cmp     r8d, edx
0x1800209af  jb      short loc_180020983
0x1800209b1  cmp     [rsp+1F0h+var_1B8], 3231564Eh
0x1800209b9  jnz     short loc_180020A09
0x1800209bb  xor     r15d, r15d
0x1800209be  mov     r14, rsi
0x1800209c1  mov     edx, r15d
0x1800209c4  imul    rdx, r12
0x1800209c8  add     rdx, rdi
0x1800209cb  cmp     rdx, rcx
0x1800209ce  jb      short loc_1800209EF
0x1800209d0  lea     r9, [rdx+r12]
0x1800209d4  cmp     r9, rcx
0x1800209d7  jb      short loc_1800209EF
0x1800209d9  lea     rax, [rcx+r14]
0x1800209dd  cmp     r9, rax
0x1800209e0  ja      short loc_1800209EF
0x1800209e2  mov     [rbp+r15*8+0F0h+var_160], rdx
0x1800209e7  inc     r15d
0x1800209ea  cmp     r15d, r13d
0x1800209ed  jb      short loc_1800209C1
0x1800209ef  mov     rdi, [rsp+1F0h+var_180]
0x1800209f4  lea     r14, [rbx+0B0h]
0x1800209fb  mov     ecx, edi
0x1800209fd  shl     r15d, cl
0x180020a00  cmp     r8d, r15d
0x180020a03  cmovb   r15d, r8d
0x180020a07  jmp     short loc_180020A11
0x180020a09  mov     rdi, [rsp+1F0h+var_180]
0x180020a0e  mov     r15d, r8d
0x180020a11  mov     rsi, [rbp+0F0h+arg_30]
0x180020a18  xor     r13d, r13d
0x180020a1b  cmp     dword ptr [rbx+1C8h], 8
0x180020a22  mov     [rsp+1F0h+var_1A0], r13d
0x180020a27  jz      short loc_180020A4E
0x180020a29  mov     rax, [r14]
0x180020a2c  mov     dword ptr [rax+28h], 0Fh
0x180020a33  mov     rcx, [r14]
0x180020a36  mov     eax, [r14+118h]
0x180020a3d  mov     [rcx+2Ch], eax
0x180020a40  mov     rcx, r14
0x180020a43  mov     rax, [r14]
0x180020a46  mov     rax, [rax]
0x180020a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a4e  cmp     dword ptr [r14+24h], 0CDh
0x180020a56  jz      short loc_180020A7A
0x180020a58  mov     rax, [r14]
0x180020a5b  mov     dword ptr [rax+28h], 14h
0x180020a62  mov     rcx, [r14]
0x180020a65  mov     eax, [r14+24h]
0x180020a69  mov     [rcx+2Ch], eax
0x180020a6c  mov     rcx, r14
0x180020a6f  mov     rax, [r14]
0x180020a72  mov     rax, [rax]
0x180020a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a7a  mov     ecx, [r14+98h]
0x180020a81  cmp     ecx, [r14+78h]
0x180020a85  jb      short loc_180020AAB
0x180020a87  mov     rax, [r14]
0x180020a8a  or      edx, 0FFFFFFFFh
0x180020a8d  mov     rcx, r14
0x180020a90  mov     dword ptr [rax+28h], 7Bh ; '{'
0x180020a97  mov     rax, [r14]
0x180020a9a  mov     rax, [rax+8]
0x180020a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020aa3  mov     eax, r13d
0x180020aa6  jmp     loc_180020B38
0x180020aab  mov     rax, [r14+10h]
0x180020aaf  test    rax, rax
0x180020ab2  jz      short loc_180020AD1
0x180020ab4  mov     [rax+8], ecx
0x180020ab7  mov     rcx, [r14+10h]
0x180020abb  mov     eax, [r14+78h]
0x180020abf  mov     [rcx+0Ch], eax
0x180020ac2  mov     rcx, r14
0x180020ac5  mov     rax, [r14+10h]
0x180020ac9  mov     rax, [rax]
0x180020acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ad1  mov     rax, [r14+208h]
0x180020ad8  mov     [rsp+1F0h+var_1A0], r13d
0x180020add  cmp     [rax+8], r13
0x180020ae1  jnz     short loc_180020B08
0x180020ae3  mov     rax, [r14]
0x180020ae6  mov     dword ptr [rax+28h], 0Fh
0x180020aed  mov     rcx, [r14]
0x180020af0  mov     eax, [r14+118h]
0x180020af7  mov     [rcx+2Ch], eax
0x180020afa  mov     rcx, r14
0x180020afd  mov     rax, [r14]
0x180020b00  mov     rax, [rax]
0x180020b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b08  mov     rax, [r14+208h]
0x180020b0f  lea     r9, [rsp+1F0h+var_1A0]
0x180020b14  lea     r8, [rbp+0F0h+var_160]
0x180020b18  mov     [rsp+1F0h+var_1D0], r15d
0x180020b1d  lea     rdx, [rbp+0F0h+var_D0]
0x180020b21  mov     rcx, r14
0x180020b24  mov     rax, [rax+8]
0x180020b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b2d  mov     eax, [rsp+1F0h+var_1A0]
0x180020b31  add     [r14+98h], eax
0x180020b38  mov     r15, [rsp+1F0h+var_1C0]
0x180020b3d  mov     cl, dil
0x180020b40  mov     rdi, [rsp+1F0h+var_1B0]
0x180020b45  mov     edx, eax
0x180020b47  imul    rax, r12
0x180020b4b  shr     rdx, cl
0x180020b4e  add     r15, rax
0x180020b51  mov     eax, [rbx+128h]
0x180020b57  imul    rdx, r12
0x180020b5b  mov     [rsp+1F0h+var_1C0], r15
0x180020b60  add     rdi, rdx
0x180020b63  mov     r13, rdi
0x180020b66  mov     [rsp+1F0h+var_1B0], rdi
0x180020b6b  cmp     [rbx+148h], eax
0x180020b71  jb      loc_1800208C9
0x180020b77  mov     rdi, [rsp+1F0h+var_178]
0x180020b7c  mov     rsi, [rbp+0F0h+var_170]
0x180020b80  mov     r13, [rbp+0F0h+arg_30]
0x180020b87  mov     eax, [rbx+128h]
0x180020b8d  mov     rcx, r14
0x180020b90  cmp     [rbx+148h], eax
0x180020b96  jnb     short loc_180020B9F
0x180020b98  call    jpeg_abort_decompress
0x180020b9d  jmp     short loc_180020BA4
0x180020b9f  call    jpeg_finish_decompress
0x180020ba4  cmp     byte ptr [rbx+6C8h], 0
0x180020bab  jz      loc_180020DC7
0x180020bb1  mov     rcx, r14
  ... truncated ...
```
