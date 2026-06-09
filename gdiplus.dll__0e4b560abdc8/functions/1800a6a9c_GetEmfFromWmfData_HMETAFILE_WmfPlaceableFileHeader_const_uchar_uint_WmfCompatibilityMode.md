# GetEmfFromWmfData(HMETAFILE__ *,WmfPlaceableFileHeader const *,uchar *,uint,WmfCompatibilityMode)

- ea: `0x1800a6a9c`
- end: `0x1800a7236`
- name: `?GetEmfFromWmfData@@YAPEAUHENHMETAFILE__@@PEAUHMETAFILE__@@PEBUWmfPlaceableFileHeader@@PEAEIW4WmfCompatibilityMode@@@Z`
- size: `1946`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800a68e4`
- `0x18010c470`

## callees

- `0x18001f950`
- `0x1800a6a9c`
- `0x1800dec48`
- `0x1800e1120`
- `0x1800e5044`
- `0x1800e9380`
- `0x1800ea080`
- `0x1801740cc`

## import_xrefs

- `USER32!GetDC` at `0x1800a6c2a`
- `USER32!GetDC` at `0x1800a6c2a`
- `USER32!ReleaseDC` at `0x1800a71c0`
- `USER32!ReleaseDC` at `0x1800a71c0`
- `GDI32!CloseEnhMetaFile` at `0x1800a7191`
- `GDI32!CloseEnhMetaFile` at `0x1800a7191`
- `GDI32!PlayMetaFile` at `0x1800a7176`
- `GDI32!PlayMetaFile` at `0x1800a7176`
- `GDI32!CreateEnhMetaFileA` at `0x1800a6f62`
- `GDI32!CreateEnhMetaFileA` at `0x1800a6f62`
- `GDI32!SetEnhMetaFileBits` at `0x1800a6c0b`
- `GDI32!SetEnhMetaFileBits` at `0x1800a6c0b`
- `GDI32!DeleteEnhMetaFile` at `0x1800a71ac`
- `GDI32!DeleteEnhMetaFile` at `0x1800a71ac`
- `GDI32!SetViewportExtEx` at `0x1800a707e`
- `GDI32!SetViewportExtEx` at `0x1800a707e`
- `GDI32!SetViewportOrgEx` at `0x1800a6ffa`
- `GDI32!SetViewportOrgEx` at `0x1800a6ffa`
- `GDI32!SetWindowExtEx` at `0x1800a7160`
- `GDI32!SetWindowExtEx` at `0x1800a7160`
- `GDI32!SetWindowOrgEx` at `0x1800a70ec`
- `GDI32!SetWindowOrgEx` at `0x1800a70ec`
- `GDI32!SetMapMode` at `0x1800a6f82`
- `GDI32!SetMapMode` at `0x1800a6f82`
- `GDI32!GetDeviceCaps` at `0x1800a6c41`
- `GDI32!GetDeviceCaps` at `0x1800a6c5a`
- `GDI32!GetDeviceCaps` at `0x1800a6c73`
- `GDI32!GetDeviceCaps` at `0x1800a6c89`
- `GDI32!GetDeviceCaps` at `0x1800a6c41`
- `GDI32!GetDeviceCaps` at `0x1800a6c5a`
- `GDI32!GetDeviceCaps` at `0x1800a6c73`
- `GDI32!GetDeviceCaps` at `0x1800a6c89`

## pseudocode

```c
HENHMETAFILE __fastcall GetEmfFromWmfData(HMETAFILE a1, __int16 *a2, __int64 a3, unsigned int a4, int a5)
{
  HMETAFILE v6; // r14
  const BYTE *v7; // r12
  unsigned int *v8; // rbx
  unsigned int v9; // r15d
  __int16 *v10; // r8
  unsigned int v11; // r9d
  unsigned int v12; // r9d
  __int16 v13; // cx
  __int16 v14; // ax
  UINT v15; // r14d
  unsigned int v16; // esi
  unsigned int v17; // eax
  unsigned __int64 v18; // rdi
  HENHMETAFILE v19; // rbx
  HDC DC; // r15
  __m128i v21; // xmm11
  __m128i v22; // xmm14
  int DeviceCaps; // ebx
  int v24; // eax
  float v25; // xmm11_4
  float v26; // xmm6_4
  float v27; // xmm0_4
  BOOL v28; // ebx
  float v29; // xmm7_4
  __m128 v30; // xmm8
  __m128 v31; // xmm9
  float v32; // xmm12_4
  float v33; // xmm14_4
  float v34; // xmm13_4
  float v35; // xmm1_4
  __m128 v36; // xmm0
  __m128 v37; // xmm0
  bool v38; // di
  __m128 v39; // xmm0
  int v40; // eax
  float v41; // xmm0_4
  __m128 v42; // xmm1
  int v43; // eax
  __m128 v44; // xmm0
  int v45; // eax
  float v46; // xmm0_4
  __m128 v47; // xmm1
  int v48; // eax
  int v49; // edi
  HDC EnhMetaFileA; // rax
  HDC v51; // rbx
  bool v52; // di
  int v53; // esi
  int v54; // edx
  bool v55; // di
  float v56; // xmm6_4
  __m128 v57; // xmm1
  int v58; // esi
  float v59; // xmm7_4
  __m128 v60; // xmm1
  int v61; // edx
  bool v62; // di
  int v63; // esi
  int v64; // edx
  bool v65; // di
  __m128 v66; // xmm1
  int v67; // esi
  __m128 v68; // xmm1
  int v69; // edx
  HENHMETAFILE v70; // rax
  __int128 v72; // [rsp+28h] [rbp-A1h] BYREF
  __int64 v73; // [rsp+38h] [rbp-91h]
  HMETAFILE v74; // [rsp+40h] [rbp-89h] BYREF
  int v75; // [rsp+48h] [rbp-81h]
  int v76; // [rsp+4Ch] [rbp-7Dh]

  v74 = a1;
  v6 = a1;
  if ( !a3 || !a1 || a4 < 0x12 )
    return 0;
  v7 = 0;
  if ( a4 > 0x3E )
  {
    v8 = (unsigned int *)(a3 + 18);
    v9 = a4 - 18;
    if ( (unsigned int)IsMetaEscapeEnhancedMetafile((struct _META_ESCAPE_ENHANCED_METAFILE *)(a3 + 18)) )
    {
      if ( !v8[6] )
      {
        v12 = v11 >> 1;
        v13 = 0;
        if ( !v12 )
          goto LABEL_10;
        do
        {
          v14 = *v10++;
          v13 += v14;
          --v12;
        }
        while ( v12 );
        v6 = v74;
        if ( !v13 )
        {
LABEL_10:
          v15 = v8[10];
          if ( v15 )
          {
            v7 = (const BYTE *)GpMallocEx(v15, 0);
            if ( v7 )
            {
              v16 = 0;
              while ( 1 )
              {
                v17 = v8[8];
                if ( v17 + v16 < v16 )
                  break;
                if ( v17 + v16 > v15 )
                  break;
                v18 = 2LL * *v8;
                if ( v18 > 0xFFFFFFFF || (unsigned int)v18 > v9 || v17 >= 0xFFFFFFD4 || v17 + 44 > (unsigned int)v18 )
                  break;
                memcpy_0((void *)&v7[v16], v8 + 11, v17);
                v16 += v8[8];
                v9 -= v18;
                v8 = (unsigned int *)((char *)v8 + (unsigned int)v18);
                if ( v9 < 0x2C
                  || !(unsigned int)IsMetaEscapeEnhancedMetafile((struct _META_ESCAPE_ENHANCED_METAFILE *)v8) )
                {
                  if ( v16 == v15 )
                  {
                    v19 = SetEnhMetaFileBits(v15, v7);
                    if ( v19 )
                      goto LABEL_90;
                  }
                  break;
                }
              }
            }
          }
          v6 = v74;
        }
      }
    }
  }
  DC = GetDC(0);
  v21 = _mm_cvtsi32_si128(GetDeviceCaps(DC, 8));
  v22 = _mm_cvtsi32_si128(GetDeviceCaps(DC, 10));
  DeviceCaps = GetDeviceCaps(DC, 4);
  v24 = GetDeviceCaps(DC, 6);
  LODWORD(v25) = _mm_cvtepi32_ps(v21).m128_u32[0];
  if ( !DeviceCaps )
    DeviceCaps = 320;
  if ( !v24 )
    v24 = 240;
  v26 = 0.0;
  v27 = (float)DeviceCaps;
  v28 = 0;
  v29 = 0.0;
  v30 = 0;
  v31 = 0;
  v32 = (float)(v25 / v27) / 100.0;
  v33 = _mm_cvtepi32_ps(v22).m128_f32[0];
  v34 = (float)(v33 / (float)v24) / 100.0;
  if ( a2 )
  {
    v31 = 0;
    v30 = 0;
    v35 = (float)a2[7];
    v31.m128_f32[0] = (float)((float)((float)a2[3] * v32) * 2540.0) / v35;
    v30.m128_f32[0] = (float)((float)((float)a2[4] * v34) * 2540.0) / v35;
    v29 = (float)((float)((float)((float)a2[5] * v32) * 2540.0) / v35) - v31.m128_f32[0];
    v26 = (float)((float)((float)((float)a2[6] * v34) * 2540.0) / v35) - v30.m128_f32[0];
    if ( v29 > 20.0 )
      v28 = v26 > 20.0;
  }
  if ( !v28 )
  {
    v73 = 0;
    v72 = 0;
    if ( (a5 == 2 || !a5 && Globals::g_UseWmfSizeHeuristic)
      && (unsigned int)FScanMetaFileRecord(v6, (struct METAFILEINFO *)&v72) )
    {
      v29 = (float)SHIDWORD(v72);
      v31 = (__m128)COERCE_UNSIGNED_INT((float)SDWORD1(v72));
      v30 = (__m128)COERCE_UNSIGNED_INT((float)SDWORD2(v72));
      v26 = (float)(int)v73;
      if ( (float)SHIDWORD(v72) < 0.0 )
      {
        v36 = (__m128)COERCE_UNSIGNED_INT((float)SHIDWORD(v72));
        LODWORD(v29) ^= _xmm;
        v36.m128_f32[0] = v36.m128_f32[0] + v31.m128_f32[0];
        v31 = v36;
      }
      if ( v26 < 0.0 )
      {
        v37 = (__m128)COERCE_UNSIGNED_INT((float)(int)v73);
        LODWORD(v26) ^= _xmm;
        v37.m128_f32[0] = v37.m128_f32[0] + v30.m128_f32[0];
        v30 = v37;
      }
      v28 = 1;
    }
    else
    {
      v31 = 0;
      v29 = v25;
      v30 = 0;
      v26 = v33;
    }
  }
  v38 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
  v39 = v31;
  v39.m128_f32[0] = (float)(v31.m128_f32[0] / v32) + 0.5;
  if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
    v40 = (int)_mm_round_ss(v39, v39, 9).m128_f32[0];
  else
    v40 = (int)floor(v39.m128_f32[0]);
  LODWORD(v74) = v40;
  v41 = (float)((float)((float)(v29 + v31.m128_f32[0]) - 1.0) / v32) + 0.5;
  if ( v38 )
  {
    v42 = 0;
    v42.m128_f32[0] = v41;
    v43 = (int)_mm_round_ss(v42, v42, 9).m128_f32[0];
  }
  else
  {
    v43 = (int)floor(v41);
  }
  v75 = v43;
  v44 = v30;
  v44.m128_f32[0] = (float)(v30.m128_f32[0] / v34) + 0.5;
  if ( v38 )
    v45 = (int)_mm_round_ss(v44, v44, 9).m128_f32[0];
  else
    v45 = (int)floor(v44.m128_f32[0]);
  HIDWORD(v74) = v45;
  v46 = (float)((float)((float)(v26 + v30.m128_f32[0]) - 1.0) / v34) + 0.5;
  if ( v38 )
  {
    v47 = 0;
    v47.m128_f32[0] = v46;
    v48 = (int)_mm_round_ss(v47, v47, 9).m128_f32[0];
  }
  else
  {
    v48 = (int)floor(v46);
  }
  v76 = v48;
  v49 = 0;
  EnhMetaFileA = CreateEnhMetaFileA(DC, 0, (const RECT *)((unsigned __int64)&v74 & -(__int64)v28), 0);
  v51 = EnhMetaFileA;
  if ( EnhMetaFileA )
  {
    if ( !SetMapMode(EnhMetaFileA, 8) )
      goto LABEL_85;
    v52 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
    v30.m128_f32[0] = v30.m128_f32[0] + 0.5;
    v53 = Feature_GdiPlusOptimizations_Misc_IsEnabled
        ? (int)_mm_round_ss(v30, v30, 9).m128_f32[0]
        : (int)floor(v30.m128_f32[0]);
    v31.m128_f32[0] = v31.m128_f32[0] + 0.5;
    v54 = v52 ? (int)_mm_round_ss(v31, v31, 9).m128_f32[0] : (int)floor(v31.m128_f32[0]);
    if ( !SetViewportOrgEx(v51, v54, v53, 0) )
      goto LABEL_85;
    v55 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
    v56 = v26 + 0.5;
    if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
    {
      v57 = 0;
      v57.m128_f32[0] = v56;
      v58 = (int)_mm_round_ss(v57, v57, 9).m128_f32[0];
    }
    else
    {
      v58 = (int)floor(v56);
    }
    v59 = v29 + 0.5;
    if ( v55 )
    {
      v60 = 0;
      v60.m128_f32[0] = v59;
      v61 = (int)_mm_round_ss(v60, v60, 9).m128_f32[0];
    }
    else
    {
      v61 = (int)floor(v59);
    }
    if ( !SetViewportExtEx(v51, v61, v58, 0) )
      goto LABEL_85;
    v62 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
    v63 = Feature_GdiPlusOptimizations_Misc_IsEnabled
        ? (int)_mm_round_ss(v30, v30, 9).m128_f32[0]
        : (int)floor(v30.m128_f32[0]);
    v64 = v62 ? (int)_mm_round_ss(v31, v31, 9).m128_f32[0] : (int)floor(v31.m128_f32[0]);
    if ( !SetWindowOrgEx(v51, v64, v63, 0) )
      goto LABEL_85;
    v65 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
    if ( Feature_GdiPlusOptimizations_Misc_IsEnabled )
    {
      v66 = 0;
      v66.m128_f32[0] = v56;
      v67 = (int)_mm_round_ss(v66, v66, 9).m128_f32[0];
    }
    else
    {
      v67 = (int)floor(v56);
    }
    if ( v65 )
    {
      v68 = 0;
      v68.m128_f32[0] = v59;
      v69 = (int)_mm_round_ss(v68, v68, 9).m128_f32[0];
    }
    else
    {
      v69 = (int)floor(v59);
    }
    if ( !SetWindowExtEx(v51, v69, v67, 0) || (v49 = 1, !PlayMetaFile(v51, v6)) )
LABEL_85:
      v49 = 0;
  }
  v70 = CloseEnhMetaFile(v51);
  v19 = v70;
  if ( !v49 )
  {
    if ( v70 )
    {
      DeleteEnhMetaFile(v70);
      v19 = 0;
    }
  }
  ReleaseDC(0, DC);
  if ( v7 )
LABEL_90:
    GpFree(v7);
  return v19;
}

```

## disassembly

```asm
0x1800a6a9c  mov     rax, rsp
0x1800a6a9f  mov     [rax+20h], rbx
0x1800a6aa3  push    rbp
0x1800a6aa4  push    rsi
0x1800a6aa5  push    rdi
0x1800a6aa6  push    r12
0x1800a6aa8  push    r13
0x1800a6aaa  push    r14
0x1800a6aac  push    r15
0x1800a6aae  lea     rbp, [rax-57h]
0x1800a6ab2  sub     rsp, 0E0h
0x1800a6ab9  movaps  xmmword ptr [rax-48h], xmm6
0x1800a6abd  movaps  xmmword ptr [rax-58h], xmm7
0x1800a6ac1  movaps  xmmword ptr [rax-68h], xmm8
0x1800a6ac6  movaps  xmmword ptr [rax-78h], xmm9
0x1800a6acb  movaps  xmmword ptr [rax-88h], xmm10
0x1800a6ad3  movaps  xmmword ptr [rax-98h], xmm11
0x1800a6adb  movaps  [rsp+110h+var_A8+8], xmm12
0x1800a6ae1  movaps  [rsp+110h+var_B8+8], xmm13
0x1800a6ae7  movaps  [rsp+110h+var_C8+8], xmm14
0x1800a6aed  mov     rax, cs:__security_cookie
0x1800a6af4  xor     rax, rsp
0x1800a6af7  mov     qword ptr [rbp+4Fh+var_C8], rax
0x1800a6afb  xor     edi, edi
0x1800a6afd  mov     qword ptr [rsp+110h+var_D8], rcx
0x1800a6b02  mov     r13, rdx
0x1800a6b05  mov     r14, rcx
0x1800a6b08  test    r8, r8
0x1800a6b0b  jz      loc_1800A71DE
0x1800a6b11  test    rcx, rcx
0x1800a6b14  jz      loc_1800A71DE
0x1800a6b1a  cmp     r9d, 12h
0x1800a6b1e  jb      loc_1800A71DE
0x1800a6b24  mov     r12d, edi
0x1800a6b27  cmp     r9d, 3Eh ; '>'
0x1800a6b2b  jbe     loc_1800A6C28
0x1800a6b31  lea     rbx, [r8+12h]
0x1800a6b35  mov     rcx, rbx; struct _META_ESCAPE_ENHANCED_METAFILE *
0x1800a6b38  lea     r15d, [r9-12h]
0x1800a6b3c  call    ?IsMetaEscapeEnhancedMetafile@@YAHPEFAU_META_ESCAPE_ENHANCED_METAFILE@@@Z; IsMetaEscapeEnhancedMetafile(_META_ESCAPE_ENHANCED_METAFILE *)
0x1800a6b41  test    eax, eax
0x1800a6b43  jz      loc_1800A6C28
0x1800a6b49  cmp     [rbx+18h], edi
0x1800a6b4c  jnz     loc_1800A6C28
0x1800a6b52  shr     r9d, 1
0x1800a6b55  movzx   ecx, di
0x1800a6b58  jz      short loc_1800A6B7E
0x1800a6b5a  mov     r14d, 0FFFFFFFFh
0x1800a6b60  movzx   eax, word ptr [r8]
0x1800a6b64  lea     r8, [r8+2]
0x1800a6b68  add     cx, ax
0x1800a6b6b  add     r9d, r14d
0x1800a6b6e  jnz     short loc_1800A6B60
0x1800a6b70  mov     r14, qword ptr [rsp+110h+var_D8]
0x1800a6b75  test    cx, cx
0x1800a6b78  jnz     loc_1800A6C28
0x1800a6b7e  mov     r14d, [rbx+28h]
0x1800a6b82  test    r14d, r14d
0x1800a6b85  jz      loc_1800A6C23
0x1800a6b8b  mov     ecx, r14d
0x1800a6b8e  xor     edx, edx
0x1800a6b90  call    GpMallocEx
0x1800a6b95  mov     r12, rax
0x1800a6b98  test    rax, rax
0x1800a6b9b  jz      loc_1800A6C23
0x1800a6ba1  mov     esi, edi
0x1800a6ba3  mov     eax, [rbx+20h]
0x1800a6ba6  lea     ecx, [rax+rsi]
0x1800a6ba9  cmp     ecx, esi
0x1800a6bab  jb      short loc_1800A6C23
0x1800a6bad  cmp     ecx, r14d
0x1800a6bb0  ja      short loc_1800A6C23
0x1800a6bb2  mov     edi, [rbx]
0x1800a6bb4  mov     ecx, 0FFFFFFFFh
0x1800a6bb9  add     rdi, rdi
0x1800a6bbc  cmp     rdi, rcx
0x1800a6bbf  ja      short loc_1800A6C23
0x1800a6bc1  cmp     edi, r15d
0x1800a6bc4  ja      short loc_1800A6C23
0x1800a6bc6  lea     ecx, [rax+2Ch]
0x1800a6bc9  cmp     ecx, 2Ch ; ','
0x1800a6bcc  jb      short loc_1800A6C23
0x1800a6bce  cmp     ecx, edi
0x1800a6bd0  ja      short loc_1800A6C23
0x1800a6bd2  mov     ecx, esi
0x1800a6bd4  lea     rdx, [rbx+2Ch]; Src
0x1800a6bd8  add     rcx, r12; void *
0x1800a6bdb  mov     r8d, eax; Size
0x1800a6bde  call    memcpy_0
0x1800a6be3  add     esi, [rbx+20h]
0x1800a6be6  sub     r15d, edi
0x1800a6be9  mov     eax, edi
0x1800a6beb  add     rbx, rax
0x1800a6bee  cmp     r15d, 2Ch ; ','
0x1800a6bf2  jb      short loc_1800A6C00
0x1800a6bf4  mov     rcx, rbx; struct _META_ESCAPE_ENHANCED_METAFILE *
0x1800a6bf7  call    ?IsMetaEscapeEnhancedMetafile@@YAHPEFAU_META_ESCAPE_ENHANCED_METAFILE@@@Z; IsMetaEscapeEnhancedMetafile(_META_ESCAPE_ENHANCED_METAFILE *)
0x1800a6bfc  test    eax, eax
0x1800a6bfe  jnz     short loc_1800A6BA3
0x1800a6c00  cmp     esi, r14d
0x1800a6c03  jnz     short loc_1800A6C23
0x1800a6c05  mov     rdx, r12; pb
0x1800a6c08  mov     ecx, r14d; nSize
0x1800a6c0b  call    cs:__imp_SetEnhMetaFileBits
0x1800a6c12  nop     dword ptr [rax+rax+00h]
0x1800a6c17  mov     rbx, rax
0x1800a6c1a  test    rax, rax
0x1800a6c1d  jnz     loc_1800A71D1
0x1800a6c23  mov     r14, qword ptr [rsp+110h+var_D8]
0x1800a6c28  xor     ecx, ecx; hWnd
0x1800a6c2a  call    cs:__imp_GetDC
0x1800a6c31  nop     dword ptr [rax+rax+00h]
0x1800a6c36  mov     rcx, rax; hdc
0x1800a6c39  mov     edx, 8; index
0x1800a6c3e  mov     r15, rax
0x1800a6c41  call    cs:__imp_GetDeviceCaps
0x1800a6c48  nop     dword ptr [rax+rax+00h]
0x1800a6c4d  mov     edx, 0Ah; index
0x1800a6c52  mov     rcx, r15; hdc
0x1800a6c55  movd    xmm11, eax
0x1800a6c5a  call    cs:__imp_GetDeviceCaps
0x1800a6c61  nop     dword ptr [rax+rax+00h]
0x1800a6c66  mov     edx, 4; index
0x1800a6c6b  mov     rcx, r15; hdc
0x1800a6c6e  movd    xmm14, eax
0x1800a6c73  call    cs:__imp_GetDeviceCaps
0x1800a6c7a  nop     dword ptr [rax+rax+00h]
0x1800a6c7f  mov     edx, 6; index
0x1800a6c84  mov     rcx, r15; hdc
0x1800a6c87  mov     ebx, eax
0x1800a6c89  call    cs:__imp_GetDeviceCaps
0x1800a6c90  nop     dword ptr [rax+rax+00h]
0x1800a6c95  test    ebx, ebx
0x1800a6c97  mov     ecx, 140h
0x1800a6c9c  cvtdq2ps xmm11, xmm11
0x1800a6ca0  cmovz   ebx, ecx
0x1800a6ca3  test    eax, eax
0x1800a6ca5  mov     ecx, 0F0h
0x1800a6caa  cmovz   eax, ecx
0x1800a6cad  movd    xmm0, ebx
0x1800a6cb1  xorps   xmm10, xmm10
0x1800a6cb5  movaps  xmm12, xmm11
0x1800a6cb9  xorps   xmm6, xmm6
0x1800a6cbc  cvtdq2ps xmm0, xmm0
0x1800a6cbf  xor     ebx, ebx
0x1800a6cc1  xorps   xmm7, xmm7
0x1800a6cc4  lea     edi, [rbx+1]
0x1800a6cc7  xorps   xmm8, xmm8
0x1800a6ccb  xorps   xmm9, xmm9
0x1800a6ccf  divss   xmm12, xmm0
0x1800a6cd4  movd    xmm0, eax
0x1800a6cd8  divss   xmm12, cs:__real@42c80000
0x1800a6ce1  cvtdq2ps xmm14, xmm14
0x1800a6ce5  cvtdq2ps xmm0, xmm0
0x1800a6ce8  movaps  xmm13, xmm14
0x1800a6cec  divss   xmm13, xmm0
0x1800a6cf1  divss   xmm13, cs:__real@42c80000
0x1800a6cfa  test    r13, r13
0x1800a6cfd  jz      loc_1800A6DA0
0x1800a6d03  movss   xmm0, cs:__real@451ec000
0x1800a6d0b  xorps   xmm7, xmm7
0x1800a6d0e  movsx   eax, word ptr [r13+0Eh]
0x1800a6d13  xorps   xmm6, xmm6
0x1800a6d16  xorps   xmm9, xmm9
0x1800a6d1a  xorps   xmm8, xmm8
0x1800a6d1e  xorps   xmm1, xmm1
0x1800a6d21  cvtsi2ss xmm1, eax
0x1800a6d25  movsx   eax, word ptr [r13+6]
0x1800a6d2a  cvtsi2ss xmm9, eax
0x1800a6d2f  movsx   eax, word ptr [r13+0Ah]
0x1800a6d34  cvtsi2ss xmm7, eax
0x1800a6d38  movsx   eax, word ptr [r13+8]
0x1800a6d3d  cvtsi2ss xmm8, eax
0x1800a6d42  movsx   eax, word ptr [r13+0Ch]
0x1800a6d47  cvtsi2ss xmm6, eax
0x1800a6d4b  mulss   xmm7, xmm12
0x1800a6d50  mulss   xmm6, xmm13
0x1800a6d55  mulss   xmm7, xmm0
0x1800a6d59  mulss   xmm6, xmm0
0x1800a6d5d  mulss   xmm9, xmm12
0x1800a6d62  mulss   xmm8, xmm13
0x1800a6d67  mulss   xmm9, xmm0
0x1800a6d6c  mulss   xmm8, xmm0
0x1800a6d71  movss   xmm0, cs:__real@41a00000
0x1800a6d79  divss   xmm9, xmm1
0x1800a6d7e  divss   xmm7, xmm1
0x1800a6d82  divss   xmm6, xmm1
0x1800a6d86  divss   xmm8, xmm1
0x1800a6d8b  subss   xmm7, xmm9
0x1800a6d90  subss   xmm6, xmm8
0x1800a6d95  comiss  xmm7, xmm0
0x1800a6d98  jbe     short loc_1800A6DA0
0x1800a6d9a  comiss  xmm6, xmm0
0x1800a6d9d  cmova   ebx, edi
0x1800a6da0  xor     r13d, r13d
0x1800a6da3  test    ebx, ebx
0x1800a6da5  jnz     loc_1800A6E4E
0x1800a6dab  xor     eax, eax
0x1800a6dad  xorps   xmm0, xmm0
0x1800a6db0  mov     [rsp+110h+var_E0], rax
0x1800a6db5  mov     eax, [rbp+4Fh+arg_20]
0x1800a6db8  movups  [rsp+110h+var_F8+8], xmm0
0x1800a6dbd  cmp     eax, 2
0x1800a6dc0  jz      short loc_1800A6DCF
0x1800a6dc2  test    eax, eax
0x1800a6dc4  jnz     short loc_1800A6E3E
0x1800a6dc6  cmp     cs:?g_UseWmfSizeHeuristic@Globals@@3HA, r13d; int Globals::g_UseWmfSizeHeuristic
0x1800a6dcd  jz      short loc_1800A6E3E
0x1800a6dcf  lea     rdx, [rsp+110h+var_F8+8]; struct METAFILEINFO *
0x1800a6dd4  mov     rcx, r14; hmf
0x1800a6dd7  call    ?FScanMetaFileRecord@@YAHPEAUHMETAFILE__@@PEAUMETAFILEINFO@@@Z; FScanMetaFileRecord(HMETAFILE__ *,METAFILEINFO *)
0x1800a6ddc  test    eax, eax
0x1800a6dde  jz      short loc_1800A6E3E
0x1800a6de0  movd    xmm7, dword ptr [rsp+110h+var_E8+4]
0x1800a6de6  movd    xmm9, dword ptr [rsp+110h+var_F8+0Ch]
0x1800a6ded  movd    xmm8, dword ptr [rsp+110h+var_E8]
0x1800a6df4  movd    xmm6, dword ptr [rsp+110h+var_E0]
0x1800a6dfa  movss   xmm1, dword ptr cs:__xmm@80000000800000008000000080000000
0x1800a6e02  cvtdq2ps xmm7, xmm7
0x1800a6e05  cvtdq2ps xmm9, xmm9
0x1800a6e09  comiss  xmm10, xmm7
0x1800a6e0d  cvtdq2ps xmm8, xmm8
0x1800a6e11  cvtdq2ps xmm6, xmm6
0x1800a6e14  jbe     short loc_1800A6E25
0x1800a6e16  movaps  xmm0, xmm7
0x1800a6e19  xorps   xmm7, xmm1
0x1800a6e1c  addss   xmm0, xmm9
0x1800a6e21  movaps  xmm9, xmm0
0x1800a6e25  comiss  xmm10, xmm6
0x1800a6e29  jbe     short loc_1800A6E3A
0x1800a6e2b  movaps  xmm0, xmm6
0x1800a6e2e  xorps   xmm6, xmm1
0x1800a6e31  addss   xmm0, xmm8
0x1800a6e36  movaps  xmm8, xmm0
0x1800a6e3a  mov     ebx, edi
0x1800a6e3c  jmp     short loc_1800A6E4E
0x1800a6e3e  xorps   xmm9, xmm9
0x1800a6e42  movaps  xmm7, xmm11
0x1800a6e46  xorps   xmm8, xmm8
0x1800a6e4a  movaps  xmm6, xmm14
0x1800a6e4e  mov     dil, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x1800a6e55  movaps  xmm0, xmm9
0x1800a6e59  movss   xmm10, cs:__real@3f000000
0x1800a6e62  divss   xmm0, xmm12
0x1800a6e67  addss   xmm0, xmm10
0x1800a6e6c  test    dil, dil
0x1800a6e6f  jz      short loc_1800A6E80
0x1800a6e71  movaps  xmm1, xmm0
0x1800a6e74  roundss xmm1, xmm1, 9
0x1800a6e7a  cvttss2si eax, xmm1
0x1800a6e7e  jmp     short loc_1800A6E8C
0x1800a6e80  cvtps2pd xmm0, xmm0; X
0x1800a6e83  call    floor
0x1800a6e88  cvttsd2si eax, xmm0
0x1800a6e8c  movss   xmm11, cs:__real@3f800000
0x1800a6e95  movaps  xmm0, xmm7
0x1800a6e98  mov     [rsp+110h+var_D8], eax
0x1800a6e9c  addss   xmm0, xmm9
0x1800a6ea1  subss   xmm0, xmm11
0x1800a6ea6  divss   xmm0, xmm12
0x1800a6eab  addss   xmm0, xmm10
0x1800a6eb0  test    dil, dil
0x1800a6eb3  jz      short loc_1800A6EC8
0x1800a6eb5  xorps   xmm1, xmm1
0x1800a6eb8  movss   xmm1, xmm0
0x1800a6ebc  roundss xmm1, xmm1, 9
0x1800a6ec2  cvttss2si eax, xmm1
0x1800a6ec6  jmp     short loc_1800A6ED5
0x1800a6ec8  cvtss2sd xmm0, xmm0; X
0x1800a6ecc  call    floor
0x1800a6ed1  cvttsd2si eax, xmm0
0x1800a6ed5  mov     [rsp+110h+var_D0], eax
0x1800a6ed9  movaps  xmm0, xmm8
0x1800a6edd  divss   xmm0, xmm13
0x1800a6ee2  addss   xmm0, xmm10
0x1800a6ee7  test    dil, dil
0x1800a6eea  jz      short loc_1800A6EFB
0x1800a6eec  movaps  xmm1, xmm0
0x1800a6eef  roundss xmm1, xmm1, 9
0x1800a6ef5  cvttss2si eax, xmm1
0x1800a6ef9  jmp     short loc_1800A6F07
0x1800a6efb  cvtps2pd xmm0, xmm0; X
0x1800a6efe  call    floor
0x1800a6f03  cvttsd2si eax, xmm0
0x1800a6f07  mov     [rsp+110h+var_D4], eax
0x1800a6f0b  movaps  xmm0, xmm6
0x1800a6f0e  addss   xmm0, xmm8
0x1800a6f13  subss   xmm0, xmm11
0x1800a6f18  divss   xmm0, xmm13
0x1800a6f1d  addss   xmm0, xmm10
0x1800a6f22  test    dil, dil
0x1800a6f25  jz      short loc_1800A6F3A
0x1800a6f27  xorps   xmm1, xmm1
0x1800a6f2a  movss   xmm1, xmm0
0x1800a6f2e  roundss xmm1, xmm1, 9
0x1800a6f34  cvttss2si eax, xmm1
0x1800a6f38  jmp     short loc_1800A6F47
0x1800a6f3a  cvtss2sd xmm0, xmm0; X
0x1800a6f3e  call    floor
0x1800a6f43  cvttsd2si eax, xmm0
  ... truncated ...
```
