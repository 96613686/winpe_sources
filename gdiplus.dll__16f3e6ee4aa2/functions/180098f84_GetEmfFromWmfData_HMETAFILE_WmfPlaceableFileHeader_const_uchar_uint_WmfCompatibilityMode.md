# GetEmfFromWmfData(HMETAFILE__ *,WmfPlaceableFileHeader const *,uchar *,uint,WmfCompatibilityMode)

- ea: `0x180098f84`
- end: `0x180099704`
- name: `?GetEmfFromWmfData@@YAPEAUHENHMETAFILE__@@PEAUHMETAFILE__@@PEBUWmfPlaceableFileHeader@@PEAEIW4WmfCompatibilityMode@@@Z`
- size: `1920`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800998a0`
- `0x18011ad50`

## callees

- `0x1800067bc`
- `0x18001ec80`
- `0x180098f84`
- `0x18009970c`
- `0x1800e9990`
- `0x1800fe680`
- `0x1800fefe0`
- `0x180168478`

## import_xrefs

- `USER32!GetDC` at `0x180099056`
- `USER32!GetDC` at `0x180099056`
- `USER32!ReleaseDC` at `0x1800993bb`
- `USER32!ReleaseDC` at `0x1800993bb`
- `GDI32!CloseEnhMetaFile` at `0x1800993a5`
- `GDI32!CloseEnhMetaFile` at `0x1800993a5`
- `GDI32!PlayMetaFile` at `0x180099393`
- `GDI32!PlayMetaFile` at `0x180099393`
- `GDI32!CreateEnhMetaFileA` at `0x18009921d`
- `GDI32!CreateEnhMetaFileA` at `0x18009921d`
- `GDI32!SetEnhMetaFileBits` at `0x180099507`
- `GDI32!SetEnhMetaFileBits` at `0x180099507`
- `GDI32!DeleteEnhMetaFile` at `0x1800996ef`
- `GDI32!DeleteEnhMetaFile` at `0x1800996ef`
- `GDI32!SetViewportExtEx` at `0x1800992e5`
- `GDI32!SetViewportExtEx` at `0x1800992e5`
- `GDI32!SetViewportOrgEx` at `0x18009928b`
- `GDI32!SetViewportOrgEx` at `0x18009928b`
- `GDI32!SetWindowExtEx` at `0x18009937f`
- `GDI32!SetWindowExtEx` at `0x18009937f`
- `GDI32!SetWindowOrgEx` at `0x18009932f`
- `GDI32!SetWindowOrgEx` at `0x18009932f`
- `GDI32!SetMapMode` at `0x180099237`
- `GDI32!SetMapMode` at `0x180099237`
- `GDI32!GetDeviceCaps` at `0x180099067`
- `GDI32!GetDeviceCaps` at `0x18009907a`
- `GDI32!GetDeviceCaps` at `0x18009908d`
- `GDI32!GetDeviceCaps` at `0x18009909d`
- `GDI32!GetDeviceCaps` at `0x180099067`
- `GDI32!GetDeviceCaps` at `0x18009907a`
- `GDI32!GetDeviceCaps` at `0x18009908d`
- `GDI32!GetDeviceCaps` at `0x18009909d`

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
0x180098f84  mov     rax, rsp
0x180098f87  mov     [rax+20h], rbx
0x180098f8b  push    rbp
0x180098f8c  push    rsi
0x180098f8d  push    rdi
0x180098f8e  push    r12
0x180098f90  push    r13
0x180098f92  push    r14
0x180098f94  push    r15
0x180098f96  lea     rbp, [rax-57h]
0x180098f9a  sub     rsp, 0D0h
0x180098fa1  movaps  xmmword ptr [rax-48h], xmm6
0x180098fa5  movaps  xmmword ptr [rax-58h], xmm7
0x180098fa9  movaps  xmmword ptr [rax-68h], xmm8
0x180098fae  movaps  xmmword ptr [rax-78h], xmm9
0x180098fb3  movaps  xmmword ptr [rax-88h], xmm10
0x180098fbb  movaps  [rsp+100h+var_98+8], xmm11
0x180098fc1  movaps  [rsp+100h+var_A8+8], xmm12
0x180098fc7  movaps  [rsp+100h+var_B8+8], xmm13
0x180098fcd  mov     rax, cs:__security_cookie
0x180098fd4  xor     rax, rsp
0x180098fd7  mov     qword ptr [rbp+4Fh+var_B8], rax
0x180098fdb  xor     esi, esi
0x180098fdd  mov     qword ptr [rbp+4Fh+var_C8], rcx
0x180098fe1  mov     edi, r9d
0x180098fe4  mov     r13, rdx
0x180098fe7  mov     r14, rcx
0x180098fea  test    r8, r8
0x180098fed  jz      loc_1800996FD
0x180098ff3  test    rcx, rcx
0x180098ff6  jz      loc_1800996FD
0x180098ffc  cmp     r9d, 12h
0x180099000  jb      loc_1800996FD
0x180099006  mov     r15d, esi
0x180099009  cmp     r9d, 3Eh ; '>'
0x18009900d  jbe     short loc_180099054
0x18009900f  lea     rbx, [r8+12h]
0x180099013  mov     rcx, rbx; struct _META_ESCAPE_ENHANCED_METAFILE *
0x180099016  call    ?IsMetaEscapeEnhancedMetafile@@YAHPEFAU_META_ESCAPE_ENHANCED_METAFILE@@@Z; IsMetaEscapeEnhancedMetafile(_META_ESCAPE_ENHANCED_METAFILE *)
0x18009901b  test    eax, eax
0x18009901d  jz      short loc_180099054
0x18009901f  cmp     [rbx+18h], esi
0x180099022  jnz     short loc_180099054
0x180099024  mov     ecx, r9d
0x180099027  mov     edx, esi
0x180099029  shr     ecx, 1
0x18009902b  jz      loc_18009960A
0x180099031  mov     r14d, 0FFFFFFFFh
0x180099037  movzx   eax, word ptr [r8]
0x18009903b  lea     r8, [r8+2]
0x18009903f  add     dx, ax
0x180099042  add     ecx, r14d
0x180099045  jnz     short loc_180099037
0x180099047  mov     r14, qword ptr [rbp+4Fh+var_C8]
0x18009904b  test    dx, dx
0x18009904e  jz      loc_18009960A
0x180099054  xor     ecx, ecx; hWnd
0x180099056  call    cs:__imp_GetDC
0x18009905c  mov     rcx, rax; hdc
0x18009905f  mov     edx, 8; index
0x180099064  mov     r12, rax
0x180099067  call    cs:__imp_GetDeviceCaps
0x18009906d  mov     edx, 0Ah; index
0x180099072  mov     rcx, r12; hdc
0x180099075  movd    xmm10, eax
0x18009907a  call    cs:__imp_GetDeviceCaps
0x180099080  mov     edx, 4; index
0x180099085  mov     rcx, r12; hdc
0x180099088  movd    xmm13, eax
0x18009908d  call    cs:__imp_GetDeviceCaps
0x180099093  mov     edx, 6; index
0x180099098  mov     rcx, r12; hdc
0x18009909b  mov     ebx, eax
0x18009909d  call    cs:__imp_GetDeviceCaps
0x1800990a3  test    ebx, ebx
0x1800990a5  mov     ecx, 140h
0x1800990aa  cvtdq2ps xmm10, xmm10
0x1800990ae  cmovz   ebx, ecx
0x1800990b1  mov     ecx, 0F0h
0x1800990b6  test    eax, eax
0x1800990b8  cmovz   eax, ecx
0x1800990bb  movd    xmm0, ebx
0x1800990bf  mov     ebx, 1
0x1800990c4  movaps  xmm11, xmm10
0x1800990c8  cvtdq2ps xmm0, xmm0
0x1800990cb  cvtdq2ps xmm13, xmm13
0x1800990cf  divss   xmm11, xmm0
0x1800990d4  movd    xmm0, eax
0x1800990d8  movaps  xmm12, xmm13
0x1800990dc  divss   xmm11, cs:__real@42c80000
0x1800990e5  cvtdq2ps xmm0, xmm0
0x1800990e8  divss   xmm12, xmm0
0x1800990ed  xorps   xmm0, xmm0
0x1800990f0  divss   xmm12, cs:__real@42c80000
0x1800990f9  movups  [rbp+4Fh+var_C8], xmm0
0x1800990fd  test    r13, r13
0x180099100  jnz     loc_180099526
0x180099106  xor     eax, eax
0x180099108  xor     r13d, r13d
0x18009910b  mov     [rsp+100h+var_D0], rax
0x180099110  xorps   xmm0, xmm0
0x180099113  mov     eax, [rbp+4Fh+arg_20]
0x180099116  movups  [rsp+100h+var_E8+8], xmm0
0x18009911b  cmp     eax, 2
0x18009911e  jz      loc_18009966B
0x180099124  test    eax, eax
0x180099126  jnz     short loc_180099135
0x180099128  cmp     cs:?g_UseWmfSizeHeuristic@Globals@@3HA, r13d; int Globals::g_UseWmfSizeHeuristic
0x18009912f  jnz     loc_18009966B
0x180099135  mov     esi, r13d
0x180099138  xorps   xmm8, xmm8
0x18009913c  movaps  xmm7, xmm10
0x180099140  xorps   xmm9, xmm9
0x180099144  movaps  xmm6, xmm13
0x180099148  mov     bl, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x18009914e  movaps  xmm1, xmm8
0x180099152  movss   xmm10, cs:__real@3f000000
0x18009915b  divss   xmm1, xmm11
0x180099160  addss   xmm1, xmm10
0x180099165  test    bl, bl
0x180099167  jnz     loc_180099421
0x18009916d  cvtps2pd xmm0, xmm1; X
0x180099170  call    floor
0x180099175  cvttsd2si eax, xmm0
0x180099179  movss   xmm13, cs:__real@3f800000
0x180099182  movaps  xmm1, xmm8
0x180099186  mov     dword ptr [rbp+4Fh+var_C8], eax
0x180099189  addss   xmm1, xmm7
0x18009918d  subss   xmm1, xmm13
0x180099192  divss   xmm1, xmm11
0x180099197  addss   xmm1, xmm10
0x18009919c  test    bl, bl
0x18009919e  jnz     loc_180099433
0x1800991a4  cvtps2pd xmm0, xmm1; X
0x1800991a7  call    floor
0x1800991ac  cvttsd2si eax, xmm0
0x1800991b0  mov     dword ptr [rbp+4Fh+var_C8+8], eax
0x1800991b3  movaps  xmm1, xmm9
0x1800991b7  divss   xmm1, xmm12
0x1800991bc  addss   xmm1, xmm10
0x1800991c1  test    bl, bl
0x1800991c3  jnz     loc_180099445
0x1800991c9  cvtps2pd xmm0, xmm1; X
0x1800991cc  call    floor
0x1800991d1  cvttsd2si eax, xmm0
0x1800991d5  mov     dword ptr [rbp+4Fh+var_C8+4], eax
0x1800991d8  movaps  xmm1, xmm9
0x1800991dc  addss   xmm1, xmm6
0x1800991e0  subss   xmm1, xmm13
0x1800991e5  divss   xmm1, xmm12
0x1800991ea  addss   xmm1, xmm10
0x1800991ef  test    bl, bl
0x1800991f1  jnz     loc_180099457
0x1800991f7  cvtps2pd xmm0, xmm1; X
0x1800991fa  call    floor
0x1800991ff  cvttsd2si eax, xmm0
0x180099203  mov     dword ptr [rbp+4Fh+var_C8+0Ch], eax
0x180099206  neg     esi
0x180099208  lea     rax, [rbp+4Fh+var_C8]
0x18009920c  mov     rcx, r12; hdc
0x18009920f  sbb     r8, r8
0x180099212  mov     edi, r13d
0x180099215  and     r8, rax; lprc
0x180099218  xor     r9d, r9d; lpDesc
0x18009921b  xor     edx, edx; lpFilename
0x18009921d  call    cs:__imp_CreateEnhMetaFileA
0x180099223  mov     rbx, rax
0x180099226  test    rax, rax
0x180099229  jz      loc_1800993A2
0x18009922f  mov     edx, 8; iMode
0x180099234  mov     rcx, rax; hdc
0x180099237  call    cs:__imp_SetMapMode
0x18009923d  test    eax, eax
0x18009923f  jz      loc_18009941C
0x180099245  mov     dil, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x18009924c  addss   xmm9, xmm10
0x180099251  test    dil, dil
0x180099254  jnz     loc_180099469
0x18009925a  cvtps2pd xmm0, xmm9; X
0x18009925e  call    floor
0x180099263  cvttsd2si esi, xmm0
0x180099267  addss   xmm8, xmm10
0x18009926c  test    dil, dil
0x18009926f  jnz     loc_18009947C
0x180099275  cvtps2pd xmm0, xmm8; X
0x180099279  call    floor
0x18009927e  cvttsd2si edx, xmm0; x
0x180099282  xor     r9d, r9d; lppt
0x180099285  mov     r8d, esi; y
0x180099288  mov     rcx, rbx; hdc
0x18009928b  call    cs:__imp_SetViewportOrgEx
0x180099291  test    eax, eax
0x180099293  jz      loc_18009941C
0x180099299  mov     dil, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x1800992a0  addss   xmm6, xmm10
0x1800992a5  xorps   xmm0, xmm0
0x1800992a8  test    dil, dil
0x1800992ab  jnz     loc_18009948F
0x1800992b1  cvtss2sd xmm0, xmm6; X
0x1800992b5  call    floor
0x1800992ba  cvttsd2si esi, xmm0
0x1800992be  addss   xmm7, xmm10
0x1800992c3  xorps   xmm0, xmm0
0x1800992c6  test    dil, dil
0x1800992c9  jnz     loc_1800994A2
0x1800992cf  cvtss2sd xmm0, xmm7; X
0x1800992d3  call    floor
0x1800992d8  cvttsd2si edx, xmm0; x
0x1800992dc  xor     r9d, r9d; lpsz
0x1800992df  mov     r8d, esi; y
0x1800992e2  mov     rcx, rbx; hdc
0x1800992e5  call    cs:__imp_SetViewportExtEx
0x1800992eb  test    eax, eax
0x1800992ed  jz      loc_18009941C
0x1800992f3  mov     dil, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x1800992fa  test    dil, dil
0x1800992fd  jnz     loc_1800994B5
0x180099303  cvtps2pd xmm0, xmm9; X
0x180099307  call    floor
0x18009930c  cvttsd2si esi, xmm0
0x180099310  test    dil, dil
0x180099313  jnz     loc_1800994C8
0x180099319  cvtps2pd xmm0, xmm8; X
0x18009931d  call    floor
0x180099322  cvttsd2si edx, xmm0; x
0x180099326  xor     r9d, r9d; lppt
0x180099329  mov     r8d, esi; y
0x18009932c  mov     rcx, rbx; hdc
0x18009932f  call    cs:__imp_SetWindowOrgEx
0x180099335  test    eax, eax
0x180099337  jz      loc_18009941C
0x18009933d  mov     dil, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x180099344  xorps   xmm0, xmm0
0x180099347  test    dil, dil
0x18009934a  jnz     loc_1800994DB
0x180099350  cvtss2sd xmm0, xmm6; X
0x180099354  call    floor
0x180099359  cvttsd2si esi, xmm0
0x18009935d  xorps   xmm0, xmm0
0x180099360  test    dil, dil
0x180099363  jnz     loc_1800994EE
0x180099369  cvtss2sd xmm0, xmm7; X
0x18009936d  call    floor
0x180099372  cvttsd2si edx, xmm0; x
0x180099376  xor     r9d, r9d; lpsz
0x180099379  mov     r8d, esi; y
0x18009937c  mov     rcx, rbx; hdc
0x18009937f  call    cs:__imp_SetWindowExtEx
0x180099385  test    eax, eax
0x180099387  jz      loc_18009941C
0x18009938d  mov     rdx, r14; hmf
0x180099390  mov     rcx, rbx; hdc
0x180099393  call    cs:__imp_PlayMetaFile
0x180099399  mov     edi, 1
0x18009939e  test    eax, eax
0x1800993a0  jz      short loc_18009941C
0x1800993a2  mov     rcx, rbx; hdc
0x1800993a5  call    cs:__imp_CloseEnhMetaFile
0x1800993ab  mov     rbx, rax
0x1800993ae  test    edi, edi
0x1800993b0  jz      loc_1800996E3
0x1800993b6  mov     rdx, r12; hDC
0x1800993b9  xor     ecx, ecx; hWnd
0x1800993bb  call    cs:__imp_ReleaseDC
0x1800993c1  test    r15, r15
0x1800993c4  jnz     loc_180099519
0x1800993ca  mov     rax, rbx
0x1800993cd  mov     rcx, qword ptr [rbp+4Fh+var_B8]
0x1800993d1  xor     rcx, rsp; StackCookie
0x1800993d4  call    __security_check_cookie
0x1800993d9  lea     r11, [rsp+100h+var_30]
0x1800993e1  mov     rbx, [r11+58h]
0x1800993e5  movaps  xmm6, xmmword ptr [r11-10h]
0x1800993ea  movaps  xmm7, xmmword ptr [r11-20h]
0x1800993ef  movaps  xmm8, xmmword ptr [r11-30h]
0x1800993f4  movaps  xmm9, xmmword ptr [r11-40h]
0x1800993f9  movaps  xmm10, xmmword ptr [r11-50h]
0x1800993fe  movaps  xmm11, xmmword ptr [r11-60h]
0x180099403  movaps  xmm12, xmmword ptr [r11-70h]
0x180099408  movaps  xmm13, xmmword ptr [r11-80h]
0x18009940d  mov     rsp, r11
0x180099410  pop     r15
0x180099412  pop     r14
0x180099414  pop     r13
0x180099416  pop     r12
0x180099418  pop     rdi
0x180099419  pop     rsi
0x18009941a  pop     rbp
0x18009941b  retn
0x18009941c  mov     edi, r13d
0x18009941f  jmp     short loc_1800993A2
0x180099421  movaps  xmm0, xmm1
0x180099424  roundss xmm0, xmm0, 9
0x18009942a  cvttss2si eax, xmm0
0x18009942e  jmp     loc_180099179
0x180099433  movaps  xmm0, xmm1
0x180099436  roundss xmm0, xmm0, 9
0x18009943c  cvttss2si eax, xmm0
0x180099440  jmp     loc_1800991B0
0x180099445  movaps  xmm0, xmm1
  ... truncated ...
```
