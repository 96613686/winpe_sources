# DoGdiCommentMultiFormats

- ea: `0x180142038`
- end: `0x18014290d`
- name: `DoGdiCommentMultiFormats`
- size: `2261`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800ef6e0`

## callees

- `0x1800c3bb8`
- `0x1800c4088`
- `0x1800c42f4`
- `0x1800c4340`
- `0x1800c4ac4`
- `0x1800e0c5c`
- `0x1800f21ec`
- `0x1800fe680`
- `0x180142038`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801424bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801424bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180142542`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180142542`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18014252a`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18014252a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180142320`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18014236a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1801423cc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180142416`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180142320`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18014236a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1801423cc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180142416`
- `GDI32!GetWinMetaFileBits` at `0x1801424ab`
- `GDI32!GetWinMetaFileBits` at `0x1801424e5`
- `GDI32!GetWinMetaFileBits` at `0x1801424ab`
- `GDI32!GetWinMetaFileBits` at `0x1801424e5`
- `GDI32!PlayEnhMetaFile` at `0x180142476`
- `GDI32!PlayEnhMetaFile` at `0x180142476`
- `GDI32!CloseEnhMetaFile` at `0x18014247f`
- `GDI32!CloseEnhMetaFile` at `0x1801428c7`
- `GDI32!CloseEnhMetaFile` at `0x18014247f`
- `GDI32!CloseEnhMetaFile` at `0x1801428c7`
- `GDI32!CreateEnhMetaFileA` at `0x18014242c`
- `GDI32!CreateEnhMetaFileA` at `0x18014242c`
- `GDI32!SetEnhMetaFileBits` at `0x180142198`
- `GDI32!SetEnhMetaFileBits` at `0x180142198`
- `GDI32!DeleteEnhMetaFile` at `0x1801428b9`
- `GDI32!DeleteEnhMetaFile` at `0x1801428d8`
- `GDI32!DeleteEnhMetaFile` at `0x1801428b9`
- `GDI32!DeleteEnhMetaFile` at `0x1801428d8`
- `GDI32!SetWorldTransform` at `0x18014245d`
- `GDI32!SetWorldTransform` at `0x18014245d`
- `GDI32!SetGraphicsMode` at `0x180142448`
- `GDI32!SetGraphicsMode` at `0x180142448`

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
0x180142038  mov     [rsp-8+arg_10], rbx
0x18014203d  push    rbp
0x18014203e  push    rsi
0x18014203f  push    rdi
0x180142040  push    r12
0x180142042  push    r13
0x180142044  push    r14
0x180142046  push    r15
0x180142048  lea     rbp, [rsp-27h]
0x18014204d  sub     rsp, 0D0h
0x180142054  mov     rax, cs:__security_cookie
0x18014205b  xor     rax, rsp
0x18014205e  mov     [rbp+57h+var_38], rax
0x180142062  mov     r10, cs:pfnIsValidEnhMetaRecordOffExt
0x180142069  xor     eax, eax
0x18014206b  xor     r13d, r13d
0x18014206e  mov     qword ptr [rbp+57h+xf.eDx], rax
0x180142072  mov     [rbp+57h+var_78], rax
0x180142076  xorps   xmm0, xmm0
0x180142079  mov     [rbp+57h+var_A0], r13
0x18014207d  xorps   xmm1, xmm1
0x180142080  mov     rbx, rdx
0x180142083  mov     rdi, rcx
0x180142086  mov     r12d, r13d
0x180142089  movups  xmmword ptr [rbp+57h+xf.eM11], xmm0
0x18014208d  movups  [rbp+57h+var_88], xmm1
0x180142091  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x180142095  test    r10, r10
0x180142098  jz      short loc_1801420C1
0x18014209a  mov     rcx, [rcx+238h]
0x1801420a1  lea     r9d, [rax+38h]
0x1801420a5  mov     rax, r10
0x1801420a8  xor     r8d, r8d
0x1801420ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801420b0  test    eax, eax
0x1801420b2  jz      loc_1801428DE
0x1801420b8  mov     r10, cs:pfnIsValidEnhMetaRecordOffExt
0x1801420bf  jmp     short loc_1801420CB
0x1801420c1  cmp     dword ptr [rdx+4], 38h ; '8'
0x1801420c5  jb      loc_1801428DE
0x1801420cb  mov     r14d, 28h ; '('
0x1801420d1  mov     esi, r13d
0x1801420d4  cmp     esi, [rbx+24h]
0x1801420d7  jnb     short loc_18014213F
0x1801420d9  lea     eax, [r14+10h]
0x1801420dd  cmp     eax, r14d
0x1801420e0  jb      loc_1801428DE
0x1801420e6  mov     r14d, eax
0x1801420e9  test    r10, r10
0x1801420ec  jz      short loc_180142117
0x1801420ee  mov     rcx, [rdi+238h]
0x1801420f5  mov     r9d, eax
0x1801420f8  mov     rax, r10
0x1801420fb  xor     r8d, r8d
0x1801420fe  mov     rdx, rbx
0x180142101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180142106  test    eax, eax
0x180142108  jz      loc_1801428DE
0x18014210e  mov     r10, cs:pfnIsValidEnhMetaRecordOffExt
0x180142115  jmp     short loc_180142120
0x180142117  cmp     eax, [rbx+4]
0x18014211a  ja      loc_1801428DE
0x180142120  mov     eax, esi
0x180142122  add     rax, rax
0x180142125  mov     ecx, esi
0x180142127  cmp     dword ptr [rbx+rax*8+28h], 464D4520h
0x18014212f  jnz     short loc_18014213B
0x180142131  cmp     dword ptr [rbx+rax*8+2Ch], 10000h
0x180142139  jbe     short loc_180142141
0x18014213b  inc     esi
0x18014213d  jmp     short loc_1801420D4
0x18014213f  mov     ecx, esi
0x180142141  cmp     esi, [rbx+24h]
0x180142144  jnb     loc_1801428DE
0x18014214a  mov     rax, rcx
0x18014214d  add     rax, rax
0x180142150  mov     esi, [rbx+rax*8+34h]
0x180142154  add     esi, 0Ch
0x180142157  cmp     esi, 0Ch
0x18014215a  jb      loc_1801428DE
0x180142160  lea     rax, [rcx+3]
0x180142164  add     rax, rax
0x180142167  mov     r14d, [rbx+rax*8]
0x18014216b  test    r10, r10
0x18014216e  jz      short loc_180142190
0x180142170  mov     rcx, [rdi+238h]
0x180142177  mov     r9d, r14d
0x18014217a  mov     r8d, esi
0x18014217d  mov     rdx, rbx
0x180142180  mov     rax, r10
0x180142183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180142188  test    eax, eax
0x18014218a  jz      loc_1801428DE
0x180142190  mov     edx, esi
0x180142192  mov     ecx, r14d; nSize
0x180142195  add     rdx, rbx; pb
0x180142198  call    cs:__imp_SetEnhMetaFileBits
0x18014219e  mov     [rbp+57h+hmf], rax
0x1801421a2  test    rax, rax
0x1801421a5  jz      loc_1801428DE
0x1801421ab  mov     rax, cs:pfnGetTransform
0x1801421b2  mov     rsi, r13
0x1801421b5  mov     r14, r13
0x1801421b8  test    rax, rax
0x1801421bb  jz      short loc_1801421D9
0x1801421bd  mov     rcx, [rdi+28h]
0x1801421c1  lea     r8, [rbp+57h+xf]
0x1801421c5  mov     edx, 204h
0x1801421ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801421cf  test    eax, eax
0x1801421d1  jz      loc_1801428B5
0x1801421d7  jmp     short loc_1801421F1
0x1801421d9  movaps  xmm0, xmmword ptr cs:xformIdentity
0x1801421e0  movsd   xmm1, qword ptr cs:xformIdentity+10h
0x1801421e8  movups  xmmword ptr [rbp+57h+xf.eM11], xmm0
0x1801421ec  movsd   qword ptr [rbp+57h+xf.eDx], xmm1
0x1801421f1  mov     rax, [rdi+8]
0x1801421f5  lea     r8, [rbp+57h+var_88]
0x1801421f9  mov     r12d, [rdi+4Ch]
0x1801421fd  mov     r13d, [rdi+44h]
0x180142201  mov     ecx, [rdi+50h]
0x180142204  movd    xmm2, dword ptr [rax+48h]
0x180142209  movd    xmm1, dword ptr [rax+50h]
0x18014220e  mov     edx, [rdi+48h]
0x180142211  cvtdq2ps xmm2, xmm2
0x180142214  mov     qword ptr [rbp+57h+var_88+4], rsi
0x180142218  mov     [rbp+57h+nDenominator], ecx
0x18014221b  mov     [rbp+57h+nNumerator], edx
0x18014221e  cvtdq2ps xmm1, xmm1
0x180142221  movd    xmm3, r12d
0x180142226  cvtdq2ps xmm3, xmm3
0x180142229  divss   xmm2, xmm1
0x18014222d  movd    xmm0, r13d
0x180142232  cvtdq2ps xmm0, xmm0
0x180142235  divss   xmm3, xmm0
0x180142239  movd    xmm0, edx
0x18014223d  lea     rdx, [rbp+57h+xf]
0x180142241  divss   xmm3, xmm2
0x180142245  cvtdq2ps xmm0, xmm0
0x180142248  movss   dword ptr [rbp+57h+var_88], xmm3
0x18014224d  movd    xmm2, dword ptr [rax+4Ch]
0x180142252  movd    xmm1, dword ptr [rax+54h]
0x180142257  movd    xmm3, ecx
0x18014225b  lea     rcx, [rbp+57h+xf]
0x18014225f  cvtdq2ps xmm3, xmm3
0x180142262  mov     [rbp+57h+var_78], rsi
0x180142266  cvtdq2ps xmm2, xmm2
0x180142269  cvtdq2ps xmm1, xmm1
0x18014226c  divss   xmm3, xmm0
0x180142270  divss   xmm2, xmm1
0x180142274  divss   xmm3, xmm2
0x180142278  movss   dword ptr [rbp+57h+var_88+0Ch], xmm3
0x18014227d  call    bCombineTransform
0x180142282  test    eax, eax
0x180142284  jz      loc_180142908
0x18014228a  mov     ecx, [rbx+18h]
0x18014228d  lea     rax, [rbx+14h]
0x180142291  mov     edx, [rax]
0x180142293  lea     r8, [rbp+57h+xf]
0x180142297  mov     [rbp+57h+lprect], rax
0x18014229b  mov     eax, [rbx+1Ch]
0x18014229e  mov     [rbp+57h+var_50], eax
0x1801422a1  mov     [rbp+57h+var_48], eax
0x1801422a4  mov     eax, [rbx+20h]
0x1801422a7  mov     [rbp+57h+var_58], edx
0x1801422aa  mov     [rbp+57h+var_54], ecx
0x1801422ad  mov     [rbp+57h+var_4C], ecx
0x1801422b0  lea     rcx, [rbp+57h+var_58]
0x1801422b4  mov     [rbp+57h+var_40], edx
0x1801422b7  mov     edx, 4
0x1801422bc  mov     [rbp+57h+var_44], eax
0x1801422bf  mov     [rbp+57h+var_3C], eax
0x1801422c2  call    bXformWorkhorse
0x1801422c7  test    eax, eax
0x1801422c9  jz      loc_180142908
0x1801422cf  mov     ebx, [rbp+57h+var_50]
0x1801422d2  mov     eax, ebx
0x1801422d4  mov     esi, [rbp+57h+var_58]
0x1801422d7  cmp     esi, ebx
0x1801422d9  mov     r14d, [rbp+57h+var_48]
0x1801422dd  cmovl   eax, esi
0x1801422e0  cmp     eax, r14d
0x1801422e3  jge     short loc_1801422EE
0x1801422e5  cmp     esi, ebx
0x1801422e7  mov     eax, ebx
0x1801422e9  cmovl   eax, esi
0x1801422ec  jmp     short loc_1801422F1
0x1801422ee  mov     eax, r14d
0x1801422f1  mov     r15d, [rbp+57h+var_40]
0x1801422f5  cmp     eax, r15d
0x1801422f8  jge     short loc_180142314
0x1801422fa  cmp     esi, ebx
0x1801422fc  mov     eax, ebx
0x1801422fe  cmovl   eax, esi
0x180142301  cmp     eax, r14d
0x180142304  jge     short loc_18014230F
0x180142306  cmp     esi, ebx
0x180142308  mov     eax, ebx
0x18014230a  cmovl   eax, esi
0x18014230d  jmp     short loc_180142317
0x18014230f  mov     eax, r14d
0x180142312  jmp     short loc_180142317
0x180142314  mov     eax, r15d
0x180142317  imul    ecx, eax, 64h ; 'd'; nNumber
0x18014231a  mov     r8d, r12d; nDenominator
0x18014231d  mov     edx, r13d; nNumerator
0x180142320  call    cs:__imp_MulDiv
0x180142326  mov     [rbp+57h+rc.left], eax
0x180142329  cmp     esi, ebx
0x18014232b  mov     eax, ebx
0x18014232d  cmovg   eax, esi
0x180142330  cmp     eax, r14d
0x180142333  jle     short loc_18014233E
0x180142335  cmp     esi, ebx
0x180142337  mov     eax, ebx
0x180142339  cmovg   eax, esi
0x18014233c  jmp     short loc_180142341
0x18014233e  mov     eax, r14d
0x180142341  cmp     eax, r15d
0x180142344  jle     short loc_18014235E
0x180142346  cmp     esi, ebx
0x180142348  mov     eax, ebx
0x18014234a  cmovg   eax, esi
0x18014234d  cmp     eax, r14d
0x180142350  jle     short loc_180142359
0x180142352  cmp     esi, ebx
0x180142354  cmovg   ebx, esi
0x180142357  jmp     short loc_180142361
0x180142359  mov     ebx, r14d
0x18014235c  jmp     short loc_180142361
0x18014235e  mov     ebx, r15d
0x180142361  imul    ecx, ebx, 64h ; 'd'; nNumber
0x180142364  mov     r8d, r12d; nDenominator
0x180142367  mov     edx, r13d; nNumerator
0x18014236a  call    cs:__imp_MulDiv
0x180142370  mov     ebx, [rbp+57h+var_4C]
0x180142373  mov     esi, [rbp+57h+var_54]
0x180142376  cmp     esi, ebx
0x180142378  mov     r14d, [rbp+57h+var_44]
0x18014237c  mov     [rbp+57h+rc.right], eax
0x18014237f  mov     eax, ebx
0x180142381  cmovl   eax, esi
0x180142384  cmp     eax, r14d
0x180142387  jge     short loc_180142392
0x180142389  cmp     esi, ebx
0x18014238b  mov     eax, ebx
0x18014238d  cmovl   eax, esi
0x180142390  jmp     short loc_180142395
0x180142392  mov     eax, r14d
0x180142395  mov     r15d, [rbp+57h+var_3C]
0x180142399  cmp     eax, r15d
0x18014239c  jge     short loc_1801423B8
0x18014239e  cmp     esi, ebx
0x1801423a0  mov     eax, ebx
0x1801423a2  cmovl   eax, esi
0x1801423a5  cmp     eax, r14d
0x1801423a8  jge     short loc_1801423B3
0x1801423aa  cmp     esi, ebx
0x1801423ac  mov     eax, ebx
0x1801423ae  cmovl   eax, esi
0x1801423b1  jmp     short loc_1801423BB
0x1801423b3  mov     eax, r14d
0x1801423b6  jmp     short loc_1801423BB
0x1801423b8  mov     eax, r15d
0x1801423bb  mov     r12d, [rbp+57h+nDenominator]
0x1801423bf  mov     r8d, r12d; nDenominator
0x1801423c2  mov     r13d, [rbp+57h+nNumerator]
0x1801423c6  mov     edx, r13d; nNumerator
0x1801423c9  imul    ecx, eax, 64h ; 'd'; nNumber
0x1801423cc  call    cs:__imp_MulDiv
0x1801423d2  mov     [rbp+57h+rc.top], eax
0x1801423d5  cmp     esi, ebx
0x1801423d7  mov     eax, ebx
0x1801423d9  cmovg   eax, esi
0x1801423dc  cmp     eax, r14d
0x1801423df  jle     short loc_1801423EA
0x1801423e1  cmp     esi, ebx
0x1801423e3  mov     eax, ebx
0x1801423e5  cmovg   eax, esi
0x1801423e8  jmp     short loc_1801423ED
0x1801423ea  mov     eax, r14d
0x1801423ed  cmp     eax, r15d
0x1801423f0  jle     short loc_18014240A
0x1801423f2  cmp     esi, ebx
0x1801423f4  mov     eax, ebx
0x1801423f6  cmovg   eax, esi
0x1801423f9  cmp     eax, r14d
0x1801423fc  jle     short loc_180142405
0x1801423fe  cmp     esi, ebx
0x180142400  cmovg   ebx, esi
0x180142403  jmp     short loc_18014240D
0x180142405  mov     ebx, r14d
0x180142408  jmp     short loc_18014240D
0x18014240a  mov     ebx, r15d
0x18014240d  imul    ecx, ebx, 64h ; 'd'; nNumber
0x180142410  mov     r8d, r12d; nDenominator
0x180142413  mov     edx, r13d; nNumerator
0x180142416  call    cs:__imp_MulDiv
0x18014241c  mov     rcx, [rdi+30h]; hdc
0x180142420  lea     r8, [rbp+57h+rc]; lprc
  ... truncated ...
```
