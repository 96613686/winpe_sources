# DoGdiCommentMultiFormats

- ea: `0x18014a9fc`
- end: `0x18014b33e`
- name: `DoGdiCommentMultiFormats`
- size: `2370`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800f6890`

## callees

- `0x1800c790c`
- `0x1800c7e08`
- `0x1800c807c`
- `0x1800c80c8`
- `0x1800c88e8`
- `0x1800e5860`
- `0x1800f8ec4`
- `0x180105d40`
- `0x18014a9fc`
- `0x180172010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18014aec5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18014aec5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18014af5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18014af5a`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18014af3c`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18014af3c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18014acea`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18014ad3a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18014ada2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18014adf2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18014acea`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18014ad3a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18014ada2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18014adf2`
- `GDI32!GetWinMetaFileBits` at `0x18014aeab`
- `GDI32!GetWinMetaFileBits` at `0x18014aef1`
- `GDI32!GetWinMetaFileBits` at `0x18014aeab`
- `GDI32!GetWinMetaFileBits` at `0x18014aef1`
- `GDI32!PlayEnhMetaFile` at `0x18014ae6a`
- `GDI32!PlayEnhMetaFile` at `0x18014ae6a`
- `GDI32!CloseEnhMetaFile` at `0x18014ae79`
- `GDI32!CloseEnhMetaFile` at `0x18014b2eb`
- `GDI32!CloseEnhMetaFile` at `0x18014ae79`
- `GDI32!CloseEnhMetaFile` at `0x18014b2eb`
- `GDI32!CreateEnhMetaFileA` at `0x18014ae0e`
- `GDI32!CreateEnhMetaFileA` at `0x18014ae0e`
- `GDI32!SetEnhMetaFileBits` at `0x18014ab5c`
- `GDI32!SetEnhMetaFileBits` at `0x18014ab5c`
- `GDI32!DeleteEnhMetaFile` at `0x18014b2d7`
- `GDI32!DeleteEnhMetaFile` at `0x18014b302`
- `GDI32!DeleteEnhMetaFile` at `0x18014b2d7`
- `GDI32!DeleteEnhMetaFile` at `0x18014b302`
- `GDI32!SetWorldTransform` at `0x18014ae4b`
- `GDI32!SetWorldTransform` at `0x18014ae4b`
- `GDI32!SetGraphicsMode` at `0x18014ae30`
- `GDI32!SetGraphicsMode` at `0x18014ae30`

## pseudocode

```c
__int64 __fastcall DoGdiCommentMultiFormats(__int64 a1, _DWORD *a2)
{
  unsigned int (__fastcall *v2)(_QWORD, _DWORD *, _QWORD, _QWORD); // r10
  unsigned int v5; // r12d
  unsigned int v6; // r14d
  unsigned int i; // esi
  unsigned int v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // esi
  UINT v11; // r14d
  HDC v12; // rsi
  HENHMETAFILE v13; // r14
  __int64 v14; // rax
  int v15; // r12d
  int v16; // r13d
  int v17; // ecx
  __m128i v18; // xmm1
  int v19; // edx
  float v20; // xmm2_4
  __m128i v21; // xmm2
  __m128i v22; // xmm1
  int v23; // ecx
  int v24; // edx
  int v25; // eax
  int v26; // ebx
  int v27; // eax
  int v28; // esi
  int v29; // r14d
  int v30; // eax
  int v31; // r15d
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  int v36; // eax
  LONG v37; // eax
  int v38; // ebx
  int v39; // esi
  int v40; // r14d
  int v41; // eax
  int v42; // eax
  int v43; // r15d
  int v44; // eax
  int v45; // eax
  int v46; // eax
  int v47; // eax
  int v48; // eax
  LONG v49; // eax
  HDC v50; // rcx
  HDC v51; // rax
  UINT WinMetaFileBits; // eax
  UINT v53; // ebx
  unsigned __int16 *v54; // r15
  unsigned int v55; // ecx
  HLOCAL v56; // rax
  unsigned int v57; // edx
  __int64 v58; // rcx
  int j; // esi
  int v60; // r13d
  unsigned int v61; // esi
  unsigned int k; // ebx
  __int64 v63; // r14
  signed int v64; // ecx
  unsigned int *m; // rbx
  int v66; // edx
  bool v67; // zf
  int v68; // eax
  unsigned __int16 v69; // cx
  unsigned int n; // ebx
  __int64 v71; // r14
  unsigned int v72; // r8d
  int ii; // edx
  int v74; // ecx
  int v75; // eax
  int v76; // eax
  int v77; // eax
  HENHMETAFILE v79; // [rsp+38h] [rbp-71h]
  int nNumerator; // [rsp+40h] [rbp-69h]
  int nDenominator; // [rsp+48h] [rbp-61h]
  HENHMETAFILE hmf; // [rsp+50h] [rbp-59h]
  RECT *lprect; // [rsp+58h] [rbp-51h]
  __int64 v84; // [rsp+60h] [rbp-49h] BYREF
  RECT rc; // [rsp+68h] [rbp-41h] BYREF
  __int128 v86; // [rsp+78h] [rbp-31h] BYREF
  __int64 v87; // [rsp+88h] [rbp-21h]
  XFORM xf; // [rsp+90h] [rbp-19h] BYREF
  int v89; // [rsp+A8h] [rbp-1h] BYREF
  int v90; // [rsp+ACh] [rbp+3h]
  int v91; // [rsp+B0h] [rbp+7h]
  int v92; // [rsp+B4h] [rbp+Bh]
  int v93; // [rsp+B8h] [rbp+Fh]
  int v94; // [rsp+BCh] [rbp+13h]
  int v95; // [rsp+C0h] [rbp+17h]
  int v96; // [rsp+C4h] [rbp+1Bh]

  v2 = (unsigned int (__fastcall *)(_QWORD, _DWORD *, _QWORD, _QWORD))pfnIsValidEnhMetaRecordOffExt;
  v87 = 0;
  v84 = 0;
  v5 = 0;
  memset(&xf, 0, sizeof(xf));
  v86 = 0;
  rc = 0;
  if ( pfnIsValidEnhMetaRecordOffExt )
  {
    if ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, _DWORD *, _QWORD, __int64))pfnIsValidEnhMetaRecordOffExt)(
                          *(_QWORD *)(a1 + 568),
                          a2,
                          0,
                          56) )
      return v5;
    v2 = (unsigned int (__fastcall *)(_QWORD, _DWORD *, _QWORD, _QWORD))pfnIsValidEnhMetaRecordOffExt;
  }
  else if ( a2[1] < 0x38u )
  {
    return v5;
  }
  v6 = 40;
  for ( i = 0; i < a2[9]; ++i )
  {
    v8 = v6 + 16;
    if ( v6 + 16 < v6 )
      return v5;
    v6 += 16;
    if ( v2 )
    {
      if ( !v2(*(_QWORD *)(a1 + 568), a2, 0, v8) )
        return v5;
      v2 = (unsigned int (__fastcall *)(_QWORD, _DWORD *, _QWORD, _QWORD))pfnIsValidEnhMetaRecordOffExt;
    }
    else if ( v8 > a2[1] )
    {
      return v5;
    }
    v9 = i;
    if ( a2[4 * i + 10] == 1179469088 && a2[4 * i + 11] <= 0x10000u )
      goto LABEL_16;
  }
  v9 = i;
LABEL_16:
  if ( i >= a2[9] )
    return v5;
  v10 = a2[4 * v9 + 13] + 12;
  if ( a2[4 * v9 + 13] >= 0xFFFFFFF4 )
    return v5;
  v11 = a2[4 * v9 + 12];
  if ( v2 )
  {
    if ( !v2(*(_QWORD *)(a1 + 568), a2, v10, v11) )
      return v5;
  }
  hmf = SetEnhMetaFileBits(v11, (const BYTE *)a2 + v10);
  if ( !hmf )
    return v5;
  v12 = 0;
  v13 = 0;
  if ( pfnGetTransform )
  {
    if ( !(unsigned int)pfnGetTransform(*(_QWORD *)(a1 + 40), 516, &xf) )
      goto LABEL_175;
  }
  else
  {
    xf = *(XFORM *)&xformIdentity;
  }
  v14 = *(_QWORD *)(a1 + 8);
  v15 = *(_DWORD *)(a1 + 76);
  v16 = *(_DWORD *)(a1 + 68);
  v17 = *(_DWORD *)(a1 + 80);
  v18 = _mm_cvtsi32_si128(*(_DWORD *)(v14 + 80));
  v19 = *(_DWORD *)(a1 + 72);
  v20 = (float)*(int *)(v14 + 72);
  *(_QWORD *)((char *)&v86 + 4) = 0;
  nDenominator = v17;
  nNumerator = v19;
  *(float *)&v86 = (float)((float)v15 / (float)v16) / (float)(v20 / _mm_cvtepi32_ps(v18).m128_f32[0]);
  v21 = _mm_cvtsi32_si128(*(_DWORD *)(v14 + 76));
  v22 = _mm_cvtsi32_si128(*(_DWORD *)(v14 + 84));
  v87 = 0;
  *((float *)&v86 + 3) = (float)((float)v17 / (float)v19)
                       / (float)(_mm_cvtepi32_ps(v21).m128_f32[0] / _mm_cvtepi32_ps(v22).m128_f32[0]);
  if ( !(unsigned int)bCombineTransform(&xf, &xf, &v86) )
    goto LABEL_180;
  v23 = a2[6];
  v24 = a2[5];
  lprect = (RECT *)(a2 + 5);
  v91 = a2[7];
  v93 = v91;
  v25 = a2[8];
  v89 = v24;
  v90 = v23;
  v92 = v23;
  v95 = v24;
  v94 = v25;
  v96 = v25;
  if ( !(unsigned int)bXformWorkhorse(&v89, 4, &xf) )
  {
LABEL_180:
    v5 = 0;
    goto LABEL_175;
  }
  v26 = v91;
  v27 = v91;
  v28 = v89;
  v29 = v93;
  if ( v89 < v91 )
    v27 = v89;
  if ( v27 >= v93 )
  {
    v30 = v93;
  }
  else
  {
    v30 = v91;
    if ( v89 < v91 )
      v30 = v89;
  }
  v31 = v95;
  if ( v30 >= v95 )
  {
    v33 = v95;
  }
  else
  {
    v32 = v91;
    if ( v89 < v91 )
      v32 = v89;
    if ( v32 >= v93 )
    {
      v33 = v93;
    }
    else
    {
      v33 = v91;
      if ( v89 < v91 )
        v33 = v89;
    }
  }
  rc.left = MulDiv(100 * v33, v16, v15);
  v34 = v26;
  if ( v28 > v26 )
    v34 = v28;
  if ( v34 <= v29 )
  {
    v35 = v29;
  }
  else
  {
    v35 = v26;
    if ( v28 > v26 )
      v35 = v28;
  }
  if ( v35 <= v31 )
  {
    v26 = v31;
  }
  else
  {
    v36 = v26;
    if ( v28 > v26 )
      v36 = v28;
    if ( v36 <= v29 )
    {
      v26 = v29;
    }
    else if ( v28 > v26 )
    {
      v26 = v28;
    }
  }
  v37 = MulDiv(100 * v26, v16, v15);
  v38 = v92;
  v39 = v90;
  v40 = v94;
  rc.right = v37;
  v41 = v92;
  if ( v90 < v92 )
    v41 = v90;
  if ( v41 >= v94 )
  {
    v42 = v94;
  }
  else
  {
    v42 = v92;
    if ( v90 < v92 )
      v42 = v90;
  }
  v43 = v96;
  if ( v42 >= v96 )
  {
    v45 = v96;
  }
  else
  {
    v44 = v92;
    if ( v90 < v92 )
      v44 = v90;
    if ( v44 >= v94 )
    {
      v45 = v94;
    }
    else
    {
      v45 = v92;
      if ( v90 < v92 )
        v45 = v90;
    }
  }
  rc.top = MulDiv(100 * v45, nNumerator, nDenominator);
  v46 = v38;
  if ( v39 > v38 )
    v46 = v39;
  if ( v46 <= v40 )
  {
    v47 = v40;
  }
  else
  {
    v47 = v38;
    if ( v39 > v38 )
      v47 = v39;
  }
  if ( v47 <= v43 )
  {
    v38 = v43;
  }
  else
  {
    v48 = v38;
    if ( v39 > v38 )
      v48 = v39;
    if ( v48 <= v40 )
    {
      v38 = v40;
    }
    else if ( v39 > v38 )
    {
      v38 = v39;
    }
  }
  v49 = MulDiv(100 * v38, nNumerator, nDenominator);
  v50 = *(HDC *)(a1 + 48);
  rc.bottom = v49;
  v51 = CreateEnhMetaFileA(v50, 0, &rc, 0);
  v12 = v51;
  if ( !v51 || !SetGraphicsMode(v51, 2) || !SetWorldTransform(v12, &xf) )
  {
    v13 = 0;
LABEL_174:
    v5 = 0;
    goto LABEL_175;
  }
  PlayEnhMetaFile(v12, hmf, lprect);
  v13 = CloseEnhMetaFile(v12);
  v79 = v13;
  v12 = 0;
  WinMetaFileBits = GetWinMetaFileBits(v13, 0, 0, 8, *(HDC *)(a1 + 48));
  v53 = WinMetaFileBits;
  if ( !WinMetaFileBits )
    goto LABEL_174;
  v54 = (unsigned __int16 *)LocalAlloc(0, WinMetaFileBits);
  if ( !v54 )
    goto LABEL_174;
  v5 = 0;
  if ( v53 != GetWinMetaFileBits(v13, v53, (LPBYTE)v54, 8, *(HDC *)(a1 + 48)) )
    goto LABEL_102;
  if ( v54[5] )
  {
    v5 = *(_DWORD *)(a1 + 408);
    v55 = v5 + v54[5];
    if ( v55 > 0xFFFF )
    {
LABEL_101:
      v5 = 0;
      goto LABEL_102;
    }
    *(_DWORD *)(a1 + 408) = v55;
    v56 = LocalReAlloc(*(HLOCAL *)(a1 + 416), 32 * v55, 2u);
    if ( !v56 )
    {
      *(_DWORD *)(a1 + 408) = v5;
      goto LABEL_101;
    }
    v57 = v5;
    for ( *(_QWORD *)(a1 + 416) = v56; v57 < *(_DWORD *)(a1 + 408); *(_QWORD *)(v58 + *(_QWORD *)(a1 + 416) + 8) = 0 )
    {
      v58 = v57++;
      v58 *= 32;
      *(_DWORD *)(v58 + *(_QWORD *)(a1 + 416)) = 1;
    }
  }
  for ( j = *(_DWORD *)(a1 + 408) - 1; j >= 0; --j )
  {
    if ( *(_DWORD *)(32LL * (unsigned int)j + *(_QWORD *)(a1 + 416)) != 1 )
      break;
  }
  v60 = j;
  v61 = j + 1;
  for ( k = 0; k < v61; ++k )
  {
    v63 = 32LL * k;
    if ( *(_DWORD *)(v63 + *(_QWORD *)(a1 + 416)) == 1 )
    {
      if ( !(unsigned int)bEmitWin16CreateBrushIndirect(a1, &v84) )
      {
LABEL_170:
        v12 = 0;
LABEL_171:
        v13 = v79;
        v5 = 0;
        goto LABEL_102;
      }
      *(_DWORD *)(v63 + *(_QWORD *)(a1 + 416)) = 9;
    }
  }
  v64 = v61 + v54[5] - 1;
  if ( v64 > *(_DWORD *)(a1 + 500) )
    *(_DWORD *)(a1 + 500) = v64;
  if ( !(unsigned int)bW16Emit0(a1, 30) )
    goto LABEL_172;
  for ( m = (unsigned int *)(v54 + 9); ; m = (unsigned int *)((char *)m + 2 * *m) )
  {
    v66 = *((unsigned __int16 *)m + 2);
    if ( !(_WORD)v66 )
      break;
    if ( (unsigned __int16)v66 > 0x20Bu )
    {
      if ( v66 == 524 )
        continue;
      if ( v66 == 552 )
        goto LABEL_149;
      if ( v66 != 564 )
      {
        if ( v66 != 1065 )
        {
          if ( v66 == 1574
            && *m > 0x16
            && *((_WORD *)m + 3) == 15
            && *(unsigned int *)((char *)m + 10) == 1128680791
            && *(unsigned int *)((char *)m + 14) == 1 )
          {
            continue;
          }
          goto LABEL_132;
        }
LABEL_149:
        v67 = (_WORD)v61 + *((_WORD *)m + 4) == 0;
        *((_WORD *)m + 4) += v61;
        if ( v67 || (unsigned int)*((unsigned __int16 *)m + 4) >= *(_DWORD *)(a1 + 408) )
          goto LABEL_172;
        *(_DWORD *)(32LL * *((unsigned __int16 *)m + 4) + *(_QWORD *)(a1 + 416)) = 8;
      }
LABEL_127:
      v67 = (_WORD)v61 + *((_WORD *)m + 3) == 0;
      *((_WORD *)m + 3) += v61;
      if ( v67 || (unsigned int)*((unsigned __int16 *)m + 3) >= *(_DWORD *)(a1 + 408) )
        goto LABEL_172;
      v68 = 1;
      if ( *((_WORD *)m + 2) != 496 )
        v68 = 8;
      *(_DWORD *)(32LL * *((unsigned __int16 *)m + 3) + *(_QWORD *)(a1 + 416)) = v68;
      goto LABEL_132;
    }
    if ( (_WORD)v66 == 523 )
      continue;
    switch ( v66 )
    {
      case 295:
        break;
      case 298:
      case 299:
        goto LABEL_127;
      case 300:
        if ( *((_WORD *)m + 3) )
        {
          v67 = *((_WORD *)m + 3) + (_WORD)v61 == 0;
          v69 = *((_WORD *)m + 3) + v61;
          *((_WORD *)m + 3) = v69;
          if ( v67 || (unsigned int)v69 >= *(_DWORD *)(a1 + 408) )
            goto LABEL_172;
          *(_DWORD *)(32LL * v69 + *(_QWORD *)(a1 + 416)) = 8;
        }
        break;
      case 301:
      case 496:
        goto LABEL_127;
    }
LABEL_132:
    if ( !(unsigned int)bEmit(a1, m, 2 * *m) )
      goto LABEL_172;
    vUpdateMaxRecord(a1, m);
  }
  if ( !(unsigned int)bW16Emit1(a1, 295, 0xFFFF) )
  {
LABEL_172:
    v12 = 0;
    goto LABEL_171;
  }
  for ( n = 0; n < v61; ++n )
  {
    v71 = 32LL * n;
    if ( *(_DWORD *)(v71 + *(_QWORD *)(a1 + 416)) == 9 )
    {
      if ( !(unsigned int)bW16Emit1(a1, 496, (unsigned __int16)n) )
        goto LABEL_170;
      *(_DWORD *)(v71 + *(_QWORD *)(a1 + 416)) = 1;
    }
  }
  if ( v54[5] )
  {
    v72 = *(_DWORD *)(a1 + 408);
    for ( ii = 0; v61 < v72; ii = v76 )
    {
      v74 = *(_DWORD *)(32LL * v61 + *(_QWORD *)(a1 + 416));
      v75 = v61;
      if ( v74 == 1 )
        v75 = v60;
      v60 = v75;
      v76 = ii + 1;
      if ( v74 == 1 )
        v76 = ii;
      ++v61;
    }
    v77 = ii + v5;
    if ( ii + v5 <= v60 + 1 )
      v77 = v60 + 1;
    *(_DWORD *)(a1 + 408) = v77;
  }
  v12 = 0;
  v5 = 1;
  v13 = v79;
LABEL_102:
  LocalFree(v54);
LABEL_175:
  DeleteEnhMetaFile(hmf);
  if ( v12 )
    v13 = CloseEnhMetaFile(v12);
  if ( v13 )
    DeleteEnhMetaFile(v13);
  return v5;
}

```

## disassembly

```asm
0x18014a9fc  mov     [rsp-8+arg_10], rbx
0x18014aa01  push    rbp
0x18014aa02  push    rsi
0x18014aa03  push    rdi
0x18014aa04  push    r12
0x18014aa06  push    r13
0x18014aa08  push    r14
0x18014aa0a  push    r15
0x18014aa0c  lea     rbp, [rsp-27h]
0x18014aa11  sub     rsp, 0D0h
0x18014aa18  mov     rax, cs:__security_cookie
0x18014aa1f  xor     rax, rsp
0x18014aa22  mov     [rbp+57h+var_38], rax
0x18014aa26  mov     r10, cs:pfnIsValidEnhMetaRecordOffExt
0x18014aa2d  xor     eax, eax
0x18014aa2f  xor     r13d, r13d
0x18014aa32  mov     qword ptr [rbp+57h+xf.eDx], rax
0x18014aa36  mov     [rbp+57h+var_78], rax
0x18014aa3a  xorps   xmm0, xmm0
0x18014aa3d  mov     [rbp+57h+var_A0], r13
0x18014aa41  xorps   xmm1, xmm1
0x18014aa44  mov     rbx, rdx
0x18014aa47  mov     rdi, rcx
0x18014aa4a  mov     r12d, r13d
0x18014aa4d  movups  xmmword ptr [rbp+57h+xf.eM11], xmm0
0x18014aa51  movups  [rbp+57h+var_88], xmm1
0x18014aa55  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x18014aa59  test    r10, r10
0x18014aa5c  jz      short loc_18014AA85
0x18014aa5e  mov     rcx, [rcx+238h]
0x18014aa65  lea     r9d, [rax+38h]
0x18014aa69  mov     rax, r10
0x18014aa6c  xor     r8d, r8d
0x18014aa6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014aa74  test    eax, eax
0x18014aa76  jz      loc_18014B30E
0x18014aa7c  mov     r10, cs:pfnIsValidEnhMetaRecordOffExt
0x18014aa83  jmp     short loc_18014AA8F
0x18014aa85  cmp     dword ptr [rdx+4], 38h ; '8'
0x18014aa89  jb      loc_18014B30E
0x18014aa8f  mov     r14d, 28h ; '('
0x18014aa95  mov     esi, r13d
0x18014aa98  cmp     esi, [rbx+24h]
0x18014aa9b  jnb     short loc_18014AB03
0x18014aa9d  lea     eax, [r14+10h]
0x18014aaa1  cmp     eax, r14d
0x18014aaa4  jb      loc_18014B30E
0x18014aaaa  mov     r14d, eax
0x18014aaad  test    r10, r10
0x18014aab0  jz      short loc_18014AADB
0x18014aab2  mov     rcx, [rdi+238h]
0x18014aab9  mov     r9d, eax
0x18014aabc  mov     rax, r10
0x18014aabf  xor     r8d, r8d
0x18014aac2  mov     rdx, rbx
0x18014aac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014aaca  test    eax, eax
0x18014aacc  jz      loc_18014B30E
0x18014aad2  mov     r10, cs:pfnIsValidEnhMetaRecordOffExt
0x18014aad9  jmp     short loc_18014AAE4
0x18014aadb  cmp     eax, [rbx+4]
0x18014aade  ja      loc_18014B30E
0x18014aae4  mov     eax, esi
0x18014aae6  add     rax, rax
0x18014aae9  mov     ecx, esi
0x18014aaeb  cmp     dword ptr [rbx+rax*8+28h], 464D4520h
0x18014aaf3  jnz     short loc_18014AAFF
0x18014aaf5  cmp     dword ptr [rbx+rax*8+2Ch], 10000h
0x18014aafd  jbe     short loc_18014AB05
0x18014aaff  inc     esi
0x18014ab01  jmp     short loc_18014AA98
0x18014ab03  mov     ecx, esi
0x18014ab05  cmp     esi, [rbx+24h]
0x18014ab08  jnb     loc_18014B30E
0x18014ab0e  mov     rax, rcx
0x18014ab11  add     rax, rax
0x18014ab14  mov     esi, [rbx+rax*8+34h]
0x18014ab18  add     esi, 0Ch
0x18014ab1b  cmp     esi, 0Ch
0x18014ab1e  jb      loc_18014B30E
0x18014ab24  lea     rax, [rcx+3]
0x18014ab28  add     rax, rax
0x18014ab2b  mov     r14d, [rbx+rax*8]
0x18014ab2f  test    r10, r10
0x18014ab32  jz      short loc_18014AB54
0x18014ab34  mov     rcx, [rdi+238h]
0x18014ab3b  mov     r9d, r14d
0x18014ab3e  mov     r8d, esi
0x18014ab41  mov     rdx, rbx
0x18014ab44  mov     rax, r10
0x18014ab47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ab4c  test    eax, eax
0x18014ab4e  jz      loc_18014B30E
0x18014ab54  mov     edx, esi
0x18014ab56  mov     ecx, r14d; nSize
0x18014ab59  add     rdx, rbx; pb
0x18014ab5c  call    cs:__imp_SetEnhMetaFileBits
0x18014ab63  nop     dword ptr [rax+rax+00h]
0x18014ab68  mov     [rbp+57h+hmf], rax
0x18014ab6c  test    rax, rax
0x18014ab6f  jz      loc_18014B30E
0x18014ab75  mov     rax, cs:pfnGetTransform
0x18014ab7c  mov     rsi, r13
0x18014ab7f  mov     r14, r13
0x18014ab82  test    rax, rax
0x18014ab85  jz      short loc_18014ABA3
0x18014ab87  mov     rcx, [rdi+28h]
0x18014ab8b  lea     r8, [rbp+57h+xf]
0x18014ab8f  mov     edx, 204h
0x18014ab94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ab99  test    eax, eax
0x18014ab9b  jz      loc_18014B2D3
0x18014aba1  jmp     short loc_18014ABBB
0x18014aba3  movups  xmm0, xmmword ptr cs:xformIdentity
0x18014abaa  movsd   xmm1, qword ptr cs:xformIdentity+10h
0x18014abb2  movups  xmmword ptr [rbp+57h+xf.eM11], xmm0
0x18014abb6  movsd   qword ptr [rbp+57h+xf.eDx], xmm1
0x18014abbb  mov     rax, [rdi+8]
0x18014abbf  lea     r8, [rbp+57h+var_88]
0x18014abc3  mov     r12d, [rdi+4Ch]
0x18014abc7  mov     r13d, [rdi+44h]
0x18014abcb  mov     ecx, [rdi+50h]
0x18014abce  movd    xmm2, dword ptr [rax+48h]
0x18014abd3  movd    xmm1, dword ptr [rax+50h]
0x18014abd8  mov     edx, [rdi+48h]
0x18014abdb  cvtdq2ps xmm2, xmm2
0x18014abde  mov     qword ptr [rbp+57h+var_88+4], rsi
0x18014abe2  mov     [rbp+57h+nDenominator], ecx
0x18014abe5  mov     [rbp+57h+nNumerator], edx
0x18014abe8  cvtdq2ps xmm1, xmm1
0x18014abeb  movd    xmm3, r12d
0x18014abf0  cvtdq2ps xmm3, xmm3
0x18014abf3  divss   xmm2, xmm1
0x18014abf7  movd    xmm0, r13d
0x18014abfc  cvtdq2ps xmm0, xmm0
0x18014abff  divss   xmm3, xmm0
0x18014ac03  movd    xmm0, edx
0x18014ac07  lea     rdx, [rbp+57h+xf]
0x18014ac0b  divss   xmm3, xmm2
0x18014ac0f  cvtdq2ps xmm0, xmm0
0x18014ac12  movss   dword ptr [rbp+57h+var_88], xmm3
0x18014ac17  movd    xmm2, dword ptr [rax+4Ch]
0x18014ac1c  movd    xmm1, dword ptr [rax+54h]
0x18014ac21  movd    xmm3, ecx
0x18014ac25  lea     rcx, [rbp+57h+xf]
0x18014ac29  cvtdq2ps xmm3, xmm3
0x18014ac2c  mov     [rbp+57h+var_78], rsi
0x18014ac30  cvtdq2ps xmm2, xmm2
0x18014ac33  cvtdq2ps xmm1, xmm1
0x18014ac36  divss   xmm3, xmm0
0x18014ac3a  divss   xmm2, xmm1
0x18014ac3e  divss   xmm3, xmm2
0x18014ac42  movss   dword ptr [rbp+57h+var_88+0Ch], xmm3
0x18014ac47  call    bCombineTransform
0x18014ac4c  test    eax, eax
0x18014ac4e  jz      loc_18014B339
0x18014ac54  mov     ecx, [rbx+18h]
0x18014ac57  lea     rax, [rbx+14h]
0x18014ac5b  mov     edx, [rax]
0x18014ac5d  lea     r8, [rbp+57h+xf]
0x18014ac61  mov     [rbp+57h+lprect], rax
0x18014ac65  mov     eax, [rbx+1Ch]
0x18014ac68  mov     [rbp+57h+var_50], eax
0x18014ac6b  mov     [rbp+57h+var_48], eax
0x18014ac6e  mov     eax, [rbx+20h]
0x18014ac71  mov     [rbp+57h+var_58], edx
0x18014ac74  mov     [rbp+57h+var_54], ecx
0x18014ac77  mov     [rbp+57h+var_4C], ecx
0x18014ac7a  lea     rcx, [rbp+57h+var_58]
0x18014ac7e  mov     [rbp+57h+var_40], edx
0x18014ac81  mov     edx, 4
0x18014ac86  mov     [rbp+57h+var_44], eax
0x18014ac89  mov     [rbp+57h+var_3C], eax
0x18014ac8c  call    bXformWorkhorse
0x18014ac91  test    eax, eax
0x18014ac93  jz      loc_18014B339
0x18014ac99  mov     ebx, [rbp+57h+var_50]
0x18014ac9c  mov     eax, ebx
0x18014ac9e  mov     esi, [rbp+57h+var_58]
0x18014aca1  cmp     esi, ebx
0x18014aca3  mov     r14d, [rbp+57h+var_48]
0x18014aca7  cmovl   eax, esi
0x18014acaa  cmp     eax, r14d
0x18014acad  jge     short loc_18014ACB8
0x18014acaf  cmp     esi, ebx
0x18014acb1  mov     eax, ebx
0x18014acb3  cmovl   eax, esi
0x18014acb6  jmp     short loc_18014ACBB
0x18014acb8  mov     eax, r14d
0x18014acbb  mov     r15d, [rbp+57h+var_40]
0x18014acbf  cmp     eax, r15d
0x18014acc2  jge     short loc_18014ACDE
0x18014acc4  cmp     esi, ebx
0x18014acc6  mov     eax, ebx
0x18014acc8  cmovl   eax, esi
0x18014accb  cmp     eax, r14d
0x18014acce  jge     short loc_18014ACD9
0x18014acd0  cmp     esi, ebx
0x18014acd2  mov     eax, ebx
0x18014acd4  cmovl   eax, esi
0x18014acd7  jmp     short loc_18014ACE1
0x18014acd9  mov     eax, r14d
0x18014acdc  jmp     short loc_18014ACE1
0x18014acde  mov     eax, r15d
0x18014ace1  imul    ecx, eax, 64h ; 'd'; nNumber
0x18014ace4  mov     r8d, r12d; nDenominator
0x18014ace7  mov     edx, r13d; nNumerator
0x18014acea  call    cs:__imp_MulDiv
0x18014acf1  nop     dword ptr [rax+rax+00h]
0x18014acf6  mov     [rbp+57h+rc.left], eax
0x18014acf9  cmp     esi, ebx
0x18014acfb  mov     eax, ebx
0x18014acfd  cmovg   eax, esi
0x18014ad00  cmp     eax, r14d
0x18014ad03  jle     short loc_18014AD0E
0x18014ad05  cmp     esi, ebx
0x18014ad07  mov     eax, ebx
0x18014ad09  cmovg   eax, esi
0x18014ad0c  jmp     short loc_18014AD11
0x18014ad0e  mov     eax, r14d
0x18014ad11  cmp     eax, r15d
0x18014ad14  jle     short loc_18014AD2E
0x18014ad16  cmp     esi, ebx
0x18014ad18  mov     eax, ebx
0x18014ad1a  cmovg   eax, esi
0x18014ad1d  cmp     eax, r14d
0x18014ad20  jle     short loc_18014AD29
0x18014ad22  cmp     esi, ebx
0x18014ad24  cmovg   ebx, esi
0x18014ad27  jmp     short loc_18014AD31
0x18014ad29  mov     ebx, r14d
0x18014ad2c  jmp     short loc_18014AD31
0x18014ad2e  mov     ebx, r15d
0x18014ad31  imul    ecx, ebx, 64h ; 'd'; nNumber
0x18014ad34  mov     r8d, r12d; nDenominator
0x18014ad37  mov     edx, r13d; nNumerator
0x18014ad3a  call    cs:__imp_MulDiv
0x18014ad41  nop     dword ptr [rax+rax+00h]
0x18014ad46  mov     ebx, [rbp+57h+var_4C]
0x18014ad49  mov     esi, [rbp+57h+var_54]
0x18014ad4c  cmp     esi, ebx
0x18014ad4e  mov     r14d, [rbp+57h+var_44]
0x18014ad52  mov     [rbp+57h+rc.right], eax
0x18014ad55  mov     eax, ebx
0x18014ad57  cmovl   eax, esi
0x18014ad5a  cmp     eax, r14d
0x18014ad5d  jge     short loc_18014AD68
0x18014ad5f  cmp     esi, ebx
0x18014ad61  mov     eax, ebx
0x18014ad63  cmovl   eax, esi
0x18014ad66  jmp     short loc_18014AD6B
0x18014ad68  mov     eax, r14d
0x18014ad6b  mov     r15d, [rbp+57h+var_3C]
0x18014ad6f  cmp     eax, r15d
0x18014ad72  jge     short loc_18014AD8E
0x18014ad74  cmp     esi, ebx
0x18014ad76  mov     eax, ebx
0x18014ad78  cmovl   eax, esi
0x18014ad7b  cmp     eax, r14d
0x18014ad7e  jge     short loc_18014AD89
0x18014ad80  cmp     esi, ebx
0x18014ad82  mov     eax, ebx
0x18014ad84  cmovl   eax, esi
0x18014ad87  jmp     short loc_18014AD91
0x18014ad89  mov     eax, r14d
0x18014ad8c  jmp     short loc_18014AD91
0x18014ad8e  mov     eax, r15d
0x18014ad91  mov     r12d, [rbp+57h+nDenominator]
0x18014ad95  mov     r8d, r12d; nDenominator
0x18014ad98  mov     r13d, [rbp+57h+nNumerator]
0x18014ad9c  mov     edx, r13d; nNumerator
0x18014ad9f  imul    ecx, eax, 64h ; 'd'; nNumber
0x18014ada2  call    cs:__imp_MulDiv
0x18014ada9  nop     dword ptr [rax+rax+00h]
0x18014adae  mov     [rbp+57h+rc.top], eax
0x18014adb1  cmp     esi, ebx
0x18014adb3  mov     eax, ebx
0x18014adb5  cmovg   eax, esi
0x18014adb8  cmp     eax, r14d
0x18014adbb  jle     short loc_18014ADC6
0x18014adbd  cmp     esi, ebx
0x18014adbf  mov     eax, ebx
0x18014adc1  cmovg   eax, esi
0x18014adc4  jmp     short loc_18014ADC9
0x18014adc6  mov     eax, r14d
0x18014adc9  cmp     eax, r15d
0x18014adcc  jle     short loc_18014ADE6
0x18014adce  cmp     esi, ebx
0x18014add0  mov     eax, ebx
0x18014add2  cmovg   eax, esi
0x18014add5  cmp     eax, r14d
0x18014add8  jle     short loc_18014ADE1
0x18014adda  cmp     esi, ebx
0x18014addc  cmovg   ebx, esi
0x18014addf  jmp     short loc_18014ADE9
0x18014ade1  mov     ebx, r14d
0x18014ade4  jmp     short loc_18014ADE9
0x18014ade6  mov     ebx, r15d
0x18014ade9  imul    ecx, ebx, 64h ; 'd'; nNumber
0x18014adec  mov     r8d, r12d; nDenominator
  ... truncated ...
```
