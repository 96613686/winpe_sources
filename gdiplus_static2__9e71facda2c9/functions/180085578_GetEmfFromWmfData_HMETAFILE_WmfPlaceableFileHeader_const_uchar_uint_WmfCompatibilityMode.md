# GetEmfFromWmfData(HMETAFILE__ *,WmfPlaceableFileHeader const *,uchar *,uint,WmfCompatibilityMode)

- ea: `0x180085578`
- end: `0x180085d60`
- name: `?GetEmfFromWmfData@@YAPEAUHENHMETAFILE__@@PEAUHMETAFILE__@@PEBUWmfPlaceableFileHeader@@PEAEIW4WmfCompatibilityMode@@@Z`
- size: `2024`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180085d9c`
- `0x180122e74`

## callees

- `0x180010bd0`
- `0x180063cd8`
- `0x180085578`
- `0x180085d68`
- `0x1800f0e94`
- `0x180105d40`
- `0x1801066d0`
- `0x180171428`

## import_xrefs

- `USER32!GetDC` at `0x18008564a`
- `USER32!GetDC` at `0x18008564a`
- `USER32!ReleaseDC` at `0x180085a01`
- `USER32!ReleaseDC` at `0x180085a01`
- `GDI32!CloseEnhMetaFile` at `0x1800859e5`
- `GDI32!CloseEnhMetaFile` at `0x1800859e5`
- `GDI32!PlayMetaFile` at `0x1800859c9`
- `GDI32!PlayMetaFile` at `0x1800859c9`
- `GDI32!CreateEnhMetaFileA` at `0x18008582f`
- `GDI32!CreateEnhMetaFileA` at `0x18008582f`
- `GDI32!SetEnhMetaFileBits` at `0x180085b57`
- `GDI32!SetEnhMetaFileBits` at `0x180085b57`
- `GDI32!DeleteEnhMetaFile` at `0x180085d45`
- `GDI32!DeleteEnhMetaFile` at `0x180085d45`
- `GDI32!SetViewportExtEx` at `0x180085909`
- `GDI32!SetViewportExtEx` at `0x180085909`
- `GDI32!SetViewportOrgEx` at `0x1800858a9`
- `GDI32!SetViewportOrgEx` at `0x1800858a9`
- `GDI32!SetWindowExtEx` at `0x1800859af`
- `GDI32!SetWindowExtEx` at `0x1800859af`
- `GDI32!SetWindowOrgEx` at `0x180085959`
- `GDI32!SetWindowOrgEx` at `0x180085959`
- `GDI32!SetMapMode` at `0x18008584f`
- `GDI32!SetMapMode` at `0x18008584f`
- `GDI32!GetDeviceCaps` at `0x180085661`
- `GDI32!GetDeviceCaps` at `0x18008567a`
- `GDI32!GetDeviceCaps` at `0x180085693`
- `GDI32!GetDeviceCaps` at `0x1800856a9`
- `GDI32!GetDeviceCaps` at `0x180085661`
- `GDI32!GetDeviceCaps` at `0x18008567a`
- `GDI32!GetDeviceCaps` at `0x180085693`
- `GDI32!GetDeviceCaps` at `0x1800856a9`

## pseudocode

```c
HENHMETAFILE __fastcall GetEmfFromWmfData(HMETAFILE a1, __int16 *a2, __int64 a3, unsigned int a4, int a5)
{
  unsigned int v5; // esi
  HMETAFILE v8; // r14
  const BYTE *v9; // r15
  unsigned int *v10; // rbx
  __int16 *v11; // r8
  unsigned int v12; // r9d
  __int16 v13; // dx
  unsigned int v14; // ecx
  __int16 v15; // ax
  HDC DC; // r12
  __m128i v17; // xmm10
  __m128i v18; // xmm13
  int DeviceCaps; // ebx
  int v20; // eax
  float v21; // xmm10_4
  float v22; // xmm13_4
  float v23; // xmm11_4
  float v24; // xmm12_4
  int v25; // esi
  __m128 v26; // xmm8
  float v27; // xmm7_4
  __m128 v28; // xmm9
  float v29; // xmm6_4
  bool v30; // bl
  __m128 v31; // xmm1
  int v32; // eax
  __m128 v33; // xmm1
  int v34; // eax
  __m128 v35; // xmm1
  int v36; // eax
  __m128 v37; // xmm1
  int v38; // eax
  int v39; // edi
  HDC EnhMetaFileA; // rax
  HDC v41; // rbx
  bool v42; // di
  int v43; // esi
  int v44; // edx
  bool v45; // di
  float v46; // xmm6_4
  __m128 v47; // xmm0
  int v48; // esi
  float v49; // xmm7_4
  __m128 v50; // xmm0
  int v51; // edx
  bool v52; // di
  int v53; // esi
  int v54; // edx
  bool v55; // di
  __m128 v56; // xmm0
  int v57; // esi
  __m128 v58; // xmm0
  int v59; // edx
  HENHMETAFILE v60; // rax
  HENHMETAFILE v61; // rbx
  float v63; // xmm0_4
  unsigned int v64; // eax
  unsigned __int64 v65; // rdi
  UINT v66; // r14d
  unsigned int v67; // r12d
  __m128 v68; // xmm0
  __int128 v69; // [rsp+28h] [rbp-91h] BYREF
  __int64 v70; // [rsp+38h] [rbp-81h]
  __int128 v71; // [rsp+40h] [rbp-79h] BYREF

  v5 = 0;
  *(_QWORD *)&v71 = a1;
  v8 = a1;
  if ( !a3 || !a1 || a4 < 0x12 )
    return 0;
  v9 = 0;
  if ( a4 > 0x3E )
  {
    v10 = (unsigned int *)(a3 + 18);
    if ( (unsigned int)IsMetaEscapeEnhancedMetafile((struct _META_ESCAPE_ENHANCED_METAFILE *)(a3 + 18)) )
    {
      if ( !v10[6] )
      {
        v13 = 0;
        v14 = v12 >> 1;
        if ( !(v12 >> 1) )
          goto LABEL_78;
        do
        {
          v15 = *v11++;
          v13 += v15;
          --v14;
        }
        while ( v14 );
        v8 = (HMETAFILE)v71;
        if ( !v13 )
        {
LABEL_78:
          v66 = v10[10];
          if ( v66 )
          {
            v9 = (const BYTE *)GpMallocEx(v66, 0);
            if ( v9 )
            {
              v67 = a4 - 18;
              while ( 1 )
              {
                v64 = v10[8];
                if ( v64 + v5 < v5 )
                  break;
                if ( v64 + v5 > v66 )
                  break;
                v65 = 2LL * *v10;
                if ( v65 > 0xFFFFFFFF || (unsigned int)v65 > v67 || v64 >= 0xFFFFFFD4 || v64 + 44 > (unsigned int)v65 )
                  break;
                memcpy_0((void *)&v9[v5], v10 + 11, v10[8]);
                v5 += v10[8];
                v67 -= v65;
                if ( v67 >= 0x2C )
                {
                  v10 = (unsigned int *)((char *)v10 + (unsigned int)v65);
                  if ( (unsigned int)IsMetaEscapeEnhancedMetafile((struct _META_ESCAPE_ENHANCED_METAFILE *)v10) )
                    continue;
                }
                if ( v5 != v66 )
                  break;
                v61 = SetEnhMetaFileBits(v66, v9);
                if ( !v61 )
                  break;
                goto LABEL_67;
              }
            }
          }
          v8 = (HMETAFILE)v71;
        }
      }
    }
  }
  DC = GetDC(0);
  v17 = _mm_cvtsi32_si128(GetDeviceCaps(DC, 8));
  v18 = _mm_cvtsi32_si128(GetDeviceCaps(DC, 10));
  DeviceCaps = GetDeviceCaps(DC, 4);
  v20 = GetDeviceCaps(DC, 6);
  LODWORD(v21) = _mm_cvtepi32_ps(v17).m128_u32[0];
  if ( !DeviceCaps )
    DeviceCaps = 320;
  if ( !v20 )
    v20 = 240;
  v22 = _mm_cvtepi32_ps(v18).m128_f32[0];
  v23 = (float)(v21 / (float)DeviceCaps) / 100.0;
  v24 = (float)(v22 / (float)v20) / 100.0;
  v71 = 0;
  if ( a2
    && (v26 = 0,
        v63 = (float)a2[7],
        v26.m128_f32[0] = (float)((float)((float)a2[3] * v23) * 2540.0) / v63,
        v27 = (float)((float)((float)((float)a2[5] * v23) * 2540.0) / v63) - v26.m128_f32[0],
        v27 > 20.0)
    && (v28 = 0,
        v28.m128_f32[0] = (float)((float)((float)a2[4] * v24) * 2540.0) / v63,
        v29 = (float)((float)((float)((float)a2[6] * v24) * 2540.0) / v63) - v28.m128_f32[0],
        v29 > 20.0) )
  {
    v25 = 1;
  }
  else
  {
    v70 = 0;
    v69 = 0;
    if ( (a5 == 2 || !a5 && Globals::g_UseWmfSizeHeuristic)
      && (unsigned int)FScanMetaFileRecord(v8, (struct METAFILEINFO *)&v69) )
    {
      v27 = (float)SHIDWORD(v69);
      v28 = (__m128)COERCE_UNSIGNED_INT((float)SDWORD2(v69));
      v29 = (float)(int)v70;
      if ( (float)SHIDWORD(v69) >= 0.0 )
      {
        v26 = (__m128)COERCE_UNSIGNED_INT((float)SDWORD1(v69));
      }
      else
      {
        v26 = (__m128)COERCE_UNSIGNED_INT((float)SHIDWORD(v69));
        LODWORD(v27) ^= _xmm;
        v26.m128_f32[0] = v26.m128_f32[0] + (float)SDWORD1(v69);
      }
      if ( v29 < 0.0 )
      {
        v68 = (__m128)COERCE_UNSIGNED_INT((float)(int)v70);
        LODWORD(v29) ^= _xmm;
        v68.m128_f32[0] = v68.m128_f32[0] + v28.m128_f32[0];
        v28 = v68;
      }
      v25 = 1;
    }
    else
    {
      v25 = 0;
      v26 = 0;
      v27 = v21;
      v28 = 0;
      v29 = v22;
    }
  }
  v30 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
  v31 = v26;
  v31.m128_f32[0] = (float)(v26.m128_f32[0] / v23) + 0.5;
  if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
    v32 = (int)_mm_round_ss(v31, v31, 9).m128_f32[0];
  else
    v32 = (int)floor(v31.m128_f32[0]);
  v33 = v26;
  LODWORD(v71) = v32;
  v33.m128_f32[0] = (float)((float)((float)(v26.m128_f32[0] + v27) - 1.0) / v23) + 0.5;
  if ( v30 )
    v34 = (int)_mm_round_ss(v33, v33, 9).m128_f32[0];
  else
    v34 = (int)floor(v33.m128_f32[0]);
  DWORD2(v71) = v34;
  v35 = v28;
  v35.m128_f32[0] = (float)(v28.m128_f32[0] / v24) + 0.5;
  if ( v30 )
    v36 = (int)_mm_round_ss(v35, v35, 9).m128_f32[0];
  else
    v36 = (int)floor(v35.m128_f32[0]);
  DWORD1(v71) = v36;
  v37 = v28;
  v37.m128_f32[0] = (float)((float)((float)(v28.m128_f32[0] + v29) - 1.0) / v24) + 0.5;
  if ( v30 )
    v38 = (int)_mm_round_ss(v37, v37, 9).m128_f32[0];
  else
    v38 = (int)floor(v37.m128_f32[0]);
  HIDWORD(v71) = v38;
  v39 = 0;
  EnhMetaFileA = CreateEnhMetaFileA(DC, 0, (const RECT *)((unsigned __int64)&v71 & -(__int64)(v25 != 0)), 0);
  v41 = EnhMetaFileA;
  if ( EnhMetaFileA )
  {
    if ( !SetMapMode(EnhMetaFileA, 8) )
      goto LABEL_53;
    v42 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
    v28.m128_f32[0] = v28.m128_f32[0] + 0.5;
    v43 = Feature_GdiPlusOptimizations_Misc_IsEnabled
        ? (int)_mm_round_ss(v28, v28, 9).m128_f32[0]
        : (int)floor(v28.m128_f32[0]);
    v26.m128_f32[0] = v26.m128_f32[0] + 0.5;
    v44 = v42 ? (int)_mm_round_ss(v26, v26, 9).m128_f32[0] : (int)floor(v26.m128_f32[0]);
    if ( !SetViewportOrgEx(v41, v44, v43, 0) )
      goto LABEL_53;
    v45 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
    v46 = v29 + 0.5;
    v47 = 0;
    if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
    {
      v47.m128_f32[0] = v46;
      v48 = (int)_mm_round_ss(v47, v47, 9).m128_f32[0];
    }
    else
    {
      v48 = (int)floor(v46);
    }
    v49 = v27 + 0.5;
    v50 = 0;
    if ( v45 )
    {
      v50.m128_f32[0] = v49;
      v51 = (int)_mm_round_ss(v50, v50, 9).m128_f32[0];
    }
    else
    {
      v51 = (int)floor(v49);
    }
    if ( !SetViewportExtEx(v41, v51, v48, 0) )
      goto LABEL_53;
    v52 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
    v53 = Feature_GdiPlusOptimizations_Misc_IsEnabled
        ? (int)_mm_round_ss(v28, v28, 9).m128_f32[0]
        : (int)floor(v28.m128_f32[0]);
    v54 = v52 ? (int)_mm_round_ss(v26, v26, 9).m128_f32[0] : (int)floor(v26.m128_f32[0]);
    if ( !SetWindowOrgEx(v41, v54, v53, 0) )
      goto LABEL_53;
    v55 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
    v56 = 0;
    if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
    {
      v56.m128_f32[0] = v46;
      v57 = (int)_mm_round_ss(v56, v56, 9).m128_f32[0];
    }
    else
    {
      v57 = (int)floor(v46);
    }
    v58 = 0;
    if ( v55 )
    {
      v58.m128_f32[0] = v49;
      v59 = (int)_mm_round_ss(v58, v58, 9).m128_f32[0];
    }
    else
    {
      v59 = (int)floor(v49);
    }
    if ( !SetWindowExtEx(v41, v59, v57, 0) || (v39 = 1, !PlayMetaFile(v41, v8)) )
LABEL_53:
      v39 = 0;
  }
  v60 = CloseEnhMetaFile(v41);
  v61 = v60;
  if ( !v39 )
  {
    if ( v60 )
    {
      DeleteEnhMetaFile(v60);
      v61 = 0;
    }
  }
  ReleaseDC(0, DC);
  if ( v9 )
LABEL_67:
    GpFree(v9);
  return v61;
}

```

## disassembly

```asm
0x180085578  mov     rax, rsp
0x18008557b  mov     [rax+20h], rbx
0x18008557f  push    rbp
0x180085580  push    rsi
0x180085581  push    rdi
0x180085582  push    r12
0x180085584  push    r13
0x180085586  push    r14
0x180085588  push    r15
0x18008558a  lea     rbp, [rax-57h]
0x18008558e  sub     rsp, 0D0h
0x180085595  movaps  xmmword ptr [rax-48h], xmm6
0x180085599  movaps  xmmword ptr [rax-58h], xmm7
0x18008559d  movaps  xmmword ptr [rax-68h], xmm8
0x1800855a2  movaps  xmmword ptr [rax-78h], xmm9
0x1800855a7  movaps  xmmword ptr [rax-88h], xmm10
0x1800855af  movaps  [rsp+100h+var_98+8], xmm11
0x1800855b5  movaps  [rsp+100h+var_A8+8], xmm12
0x1800855bb  movaps  [rsp+100h+var_B8+8], xmm13
0x1800855c1  mov     rax, cs:__security_cookie
0x1800855c8  xor     rax, rsp
0x1800855cb  mov     qword ptr [rbp+4Fh+var_B8], rax
0x1800855cf  xor     esi, esi
0x1800855d1  mov     qword ptr [rbp+4Fh+var_C8], rcx
0x1800855d5  mov     edi, r9d
0x1800855d8  mov     r13, rdx
0x1800855db  mov     r14, rcx
0x1800855de  test    r8, r8
0x1800855e1  jz      loc_180085D59
0x1800855e7  test    rcx, rcx
0x1800855ea  jz      loc_180085D59
0x1800855f0  cmp     r9d, 12h
0x1800855f4  jb      loc_180085D59
0x1800855fa  mov     r15d, esi
0x1800855fd  cmp     r9d, 3Eh ; '>'
0x180085601  jbe     short loc_180085648
0x180085603  lea     rbx, [r8+12h]
0x180085607  mov     rcx, rbx; struct _META_ESCAPE_ENHANCED_METAFILE *
0x18008560a  call    ?IsMetaEscapeEnhancedMetafile@@YAHPEFAU_META_ESCAPE_ENHANCED_METAFILE@@@Z; IsMetaEscapeEnhancedMetafile(_META_ESCAPE_ENHANCED_METAFILE *)
0x18008560f  test    eax, eax
0x180085611  jz      short loc_180085648
0x180085613  cmp     [rbx+18h], esi
0x180085616  jnz     short loc_180085648
0x180085618  mov     ecx, r9d
0x18008561b  mov     edx, esi
0x18008561d  shr     ecx, 1
0x18008561f  jz      loc_180085C60
0x180085625  mov     r14d, 0FFFFFFFFh
0x18008562b  movzx   eax, word ptr [r8]
0x18008562f  lea     r8, [r8+2]
0x180085633  add     dx, ax
0x180085636  add     ecx, r14d
0x180085639  jnz     short loc_18008562B
0x18008563b  mov     r14, qword ptr [rbp+4Fh+var_C8]
0x18008563f  test    dx, dx
0x180085642  jz      loc_180085C60
0x180085648  xor     ecx, ecx; hWnd
0x18008564a  call    cs:__imp_GetDC
0x180085651  nop     dword ptr [rax+rax+00h]
0x180085656  mov     rcx, rax; hdc
0x180085659  mov     edx, 8; index
0x18008565e  mov     r12, rax
0x180085661  call    cs:__imp_GetDeviceCaps
0x180085668  nop     dword ptr [rax+rax+00h]
0x18008566d  mov     edx, 0Ah; index
0x180085672  mov     rcx, r12; hdc
0x180085675  movd    xmm10, eax
0x18008567a  call    cs:__imp_GetDeviceCaps
0x180085681  nop     dword ptr [rax+rax+00h]
0x180085686  mov     edx, 4; index
0x18008568b  mov     rcx, r12; hdc
0x18008568e  movd    xmm13, eax
0x180085693  call    cs:__imp_GetDeviceCaps
0x18008569a  nop     dword ptr [rax+rax+00h]
0x18008569f  mov     edx, 6; index
0x1800856a4  mov     rcx, r12; hdc
0x1800856a7  mov     ebx, eax
0x1800856a9  call    cs:__imp_GetDeviceCaps
0x1800856b0  nop     dword ptr [rax+rax+00h]
0x1800856b5  test    ebx, ebx
0x1800856b7  mov     ecx, 140h
0x1800856bc  cvtdq2ps xmm10, xmm10
0x1800856c0  cmovz   ebx, ecx
0x1800856c3  mov     ecx, 0F0h
0x1800856c8  test    eax, eax
0x1800856ca  cmovz   eax, ecx
0x1800856cd  movd    xmm0, ebx
0x1800856d1  mov     ebx, 1
0x1800856d6  movaps  xmm11, xmm10
0x1800856da  cvtdq2ps xmm0, xmm0
0x1800856dd  cvtdq2ps xmm13, xmm13
0x1800856e1  divss   xmm11, xmm0
0x1800856e6  movd    xmm0, eax
0x1800856ea  movaps  xmm12, xmm13
0x1800856ee  divss   xmm11, cs:__real@42c80000
0x1800856f7  cvtdq2ps xmm0, xmm0
0x1800856fa  divss   xmm12, xmm0
0x1800856ff  xorps   xmm0, xmm0
0x180085702  divss   xmm12, cs:__real@42c80000
0x18008570b  movups  [rbp+4Fh+var_C8], xmm0
0x18008570f  test    r13, r13
0x180085712  jnz     loc_180085B7C
0x180085718  xor     eax, eax
0x18008571a  xor     r13d, r13d
0x18008571d  mov     [rsp+100h+var_D0], rax
0x180085722  xorps   xmm0, xmm0
0x180085725  mov     eax, [rbp+4Fh+arg_20]
0x180085728  movups  [rsp+100h+var_E8+8], xmm0
0x18008572d  cmp     eax, 2
0x180085730  jz      loc_180085CC1
0x180085736  test    eax, eax
0x180085738  jnz     short loc_180085747
0x18008573a  cmp     cs:?g_UseWmfSizeHeuristic@Globals@@3HA, r13d; int Globals::g_UseWmfSizeHeuristic
0x180085741  jnz     loc_180085CC1
0x180085747  mov     esi, r13d
0x18008574a  xorps   xmm8, xmm8
0x18008574e  movaps  xmm7, xmm10
0x180085752  xorps   xmm9, xmm9
0x180085756  movaps  xmm6, xmm13
0x18008575a  mov     bl, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x180085760  movaps  xmm1, xmm8
0x180085764  movss   xmm10, cs:__real@3f000000
0x18008576d  divss   xmm1, xmm11
0x180085772  addss   xmm1, xmm10
0x180085777  test    bl, bl
0x180085779  jnz     loc_180085A71
0x18008577f  cvtps2pd xmm0, xmm1; X
0x180085782  call    floor
0x180085787  cvttsd2si eax, xmm0
0x18008578b  movss   xmm13, cs:__real@3f800000
0x180085794  movaps  xmm1, xmm8
0x180085798  mov     dword ptr [rbp+4Fh+var_C8], eax
0x18008579b  addss   xmm1, xmm7
0x18008579f  subss   xmm1, xmm13
0x1800857a4  divss   xmm1, xmm11
0x1800857a9  addss   xmm1, xmm10
0x1800857ae  test    bl, bl
0x1800857b0  jnz     loc_180085A83
0x1800857b6  cvtps2pd xmm0, xmm1; X
0x1800857b9  call    floor
0x1800857be  cvttsd2si eax, xmm0
0x1800857c2  mov     dword ptr [rbp+4Fh+var_C8+8], eax
0x1800857c5  movaps  xmm1, xmm9
0x1800857c9  divss   xmm1, xmm12
0x1800857ce  addss   xmm1, xmm10
0x1800857d3  test    bl, bl
0x1800857d5  jnz     loc_180085A95
0x1800857db  cvtps2pd xmm0, xmm1; X
0x1800857de  call    floor
0x1800857e3  cvttsd2si eax, xmm0
0x1800857e7  mov     dword ptr [rbp+4Fh+var_C8+4], eax
0x1800857ea  movaps  xmm1, xmm9
0x1800857ee  addss   xmm1, xmm6
0x1800857f2  subss   xmm1, xmm13
0x1800857f7  divss   xmm1, xmm12
0x1800857fc  addss   xmm1, xmm10
0x180085801  test    bl, bl
0x180085803  jnz     loc_180085AA7
0x180085809  cvtps2pd xmm0, xmm1; X
0x18008580c  call    floor
0x180085811  cvttsd2si eax, xmm0
0x180085815  mov     dword ptr [rbp+4Fh+var_C8+0Ch], eax
0x180085818  neg     esi
0x18008581a  lea     rax, [rbp+4Fh+var_C8]
0x18008581e  mov     rcx, r12; hdc
0x180085821  sbb     r8, r8
0x180085824  mov     edi, r13d
0x180085827  and     r8, rax; lprc
0x18008582a  xor     r9d, r9d; lpDesc
0x18008582d  xor     edx, edx; lpFilename
0x18008582f  call    cs:__imp_CreateEnhMetaFileA
0x180085836  nop     dword ptr [rax+rax+00h]
0x18008583b  mov     rbx, rax
0x18008583e  test    rax, rax
0x180085841  jz      loc_1800859E2
0x180085847  mov     edx, 8; iMode
0x18008584c  mov     rcx, rax; hdc
0x18008584f  call    cs:__imp_SetMapMode
0x180085856  nop     dword ptr [rax+rax+00h]
0x18008585b  test    eax, eax
0x18008585d  jz      loc_180085A69
0x180085863  mov     dil, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x18008586a  addss   xmm9, xmm10
0x18008586f  test    dil, dil
0x180085872  jnz     loc_180085AB9
0x180085878  cvtps2pd xmm0, xmm9; X
0x18008587c  call    floor
0x180085881  cvttsd2si esi, xmm0
0x180085885  addss   xmm8, xmm10
0x18008588a  test    dil, dil
0x18008588d  jnz     loc_180085ACC
0x180085893  cvtps2pd xmm0, xmm8; X
0x180085897  call    floor
0x18008589c  cvttsd2si edx, xmm0; x
0x1800858a0  xor     r9d, r9d; lppt
0x1800858a3  mov     r8d, esi; y
0x1800858a6  mov     rcx, rbx; hdc
0x1800858a9  call    cs:__imp_SetViewportOrgEx
0x1800858b0  nop     dword ptr [rax+rax+00h]
0x1800858b5  test    eax, eax
0x1800858b7  jz      loc_180085A69
0x1800858bd  mov     dil, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x1800858c4  addss   xmm6, xmm10
0x1800858c9  xorps   xmm0, xmm0
0x1800858cc  test    dil, dil
0x1800858cf  jnz     loc_180085ADF
0x1800858d5  cvtss2sd xmm0, xmm6; X
0x1800858d9  call    floor
0x1800858de  cvttsd2si esi, xmm0
0x1800858e2  addss   xmm7, xmm10
0x1800858e7  xorps   xmm0, xmm0
0x1800858ea  test    dil, dil
0x1800858ed  jnz     loc_180085AF2
0x1800858f3  cvtss2sd xmm0, xmm7; X
0x1800858f7  call    floor
0x1800858fc  cvttsd2si edx, xmm0; x
0x180085900  xor     r9d, r9d; lpsz
0x180085903  mov     r8d, esi; y
0x180085906  mov     rcx, rbx; hdc
0x180085909  call    cs:__imp_SetViewportExtEx
0x180085910  nop     dword ptr [rax+rax+00h]
0x180085915  test    eax, eax
0x180085917  jz      loc_180085A69
0x18008591d  mov     dil, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x180085924  test    dil, dil
0x180085927  jnz     loc_180085B05
0x18008592d  cvtps2pd xmm0, xmm9; X
0x180085931  call    floor
0x180085936  cvttsd2si esi, xmm0
0x18008593a  test    dil, dil
0x18008593d  jnz     loc_180085B18
0x180085943  cvtps2pd xmm0, xmm8; X
0x180085947  call    floor
0x18008594c  cvttsd2si edx, xmm0; x
0x180085950  xor     r9d, r9d; lppt
0x180085953  mov     r8d, esi; y
0x180085956  mov     rcx, rbx; hdc
0x180085959  call    cs:__imp_SetWindowOrgEx
0x180085960  nop     dword ptr [rax+rax+00h]
0x180085965  test    eax, eax
0x180085967  jz      loc_180085A69
0x18008596d  mov     dil, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x180085974  xorps   xmm0, xmm0
0x180085977  test    dil, dil
0x18008597a  jnz     loc_180085B2B
0x180085980  cvtss2sd xmm0, xmm6; X
0x180085984  call    floor
0x180085989  cvttsd2si esi, xmm0
0x18008598d  xorps   xmm0, xmm0
0x180085990  test    dil, dil
0x180085993  jnz     loc_180085B3E
0x180085999  cvtss2sd xmm0, xmm7; X
0x18008599d  call    floor
0x1800859a2  cvttsd2si edx, xmm0; x
0x1800859a6  xor     r9d, r9d; lpsz
0x1800859a9  mov     r8d, esi; y
0x1800859ac  mov     rcx, rbx; hdc
0x1800859af  call    cs:__imp_SetWindowExtEx
0x1800859b6  nop     dword ptr [rax+rax+00h]
0x1800859bb  test    eax, eax
0x1800859bd  jz      loc_180085A69
0x1800859c3  mov     rdx, r14; hmf
0x1800859c6  mov     rcx, rbx; hdc
0x1800859c9  call    cs:__imp_PlayMetaFile
0x1800859d0  nop     dword ptr [rax+rax+00h]
0x1800859d5  mov     edi, 1
0x1800859da  test    eax, eax
0x1800859dc  jz      loc_180085A69
0x1800859e2  mov     rcx, rbx; hdc
0x1800859e5  call    cs:__imp_CloseEnhMetaFile
0x1800859ec  nop     dword ptr [rax+rax+00h]
0x1800859f1  mov     rbx, rax
0x1800859f4  test    edi, edi
0x1800859f6  jz      loc_180085D39
0x1800859fc  mov     rdx, r12; hDC
0x1800859ff  xor     ecx, ecx; hWnd
0x180085a01  call    cs:__imp_ReleaseDC
0x180085a08  nop     dword ptr [rax+rax+00h]
0x180085a0d  test    r15, r15
0x180085a10  jnz     loc_180085B6F
0x180085a16  mov     rax, rbx
0x180085a19  mov     rcx, qword ptr [rbp+4Fh+var_B8]
0x180085a1d  xor     rcx, rsp; StackCookie
0x180085a20  call    __security_check_cookie
0x180085a25  lea     r11, [rsp+100h+var_30]
0x180085a2d  mov     rbx, [r11+58h]
0x180085a31  movaps  xmm6, xmmword ptr [r11-10h]
0x180085a36  movaps  xmm7, xmmword ptr [r11-20h]
0x180085a3b  movaps  xmm8, xmmword ptr [r11-30h]
0x180085a40  movaps  xmm9, xmmword ptr [r11-40h]
0x180085a45  movaps  xmm10, xmmword ptr [r11-50h]
0x180085a4a  movaps  xmm11, xmmword ptr [r11-60h]
0x180085a4f  movaps  xmm12, xmmword ptr [r11-70h]
0x180085a54  movaps  xmm13, xmmword ptr [r11-80h]
0x180085a59  mov     rsp, r11
0x180085a5c  pop     r15
0x180085a5e  pop     r14
0x180085a60  pop     r13
0x180085a62  pop     r12
0x180085a64  pop     rdi
  ... truncated ...
```
