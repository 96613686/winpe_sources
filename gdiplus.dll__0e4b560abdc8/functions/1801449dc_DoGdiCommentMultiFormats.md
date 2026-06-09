# DoGdiCommentMultiFormats

- ea: `0x1801449dc`
- end: `0x18014535a`
- name: `DoGdiCommentMultiFormats`
- size: `2430`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18013fd60`

## callees

- `0x1800b1ee8`
- `0x1800b2190`
- `0x1800b21dc`
- `0x1800b2a98`
- `0x1800b2aec`
- `0x1800d33e0`
- `0x1800e82b8`
- `0x1800e9380`
- `0x1801449dc`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180144ebb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180144ebb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180144f4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180144f4c`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180144f2f`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180144f2f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180144ce2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180144d32`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180144d9a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180144dea`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180144ce2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180144d32`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180144d9a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180144dea`
- `GDI32!GetWinMetaFileBits` at `0x180144ea1`
- `GDI32!GetWinMetaFileBits` at `0x180144ee7`
- `GDI32!GetWinMetaFileBits` at `0x180144ea1`
- `GDI32!GetWinMetaFileBits` at `0x180144ee7`
- `GDI32!PlayEnhMetaFile` at `0x180144e64`
- `GDI32!PlayEnhMetaFile` at `0x180144e64`
- `GDI32!CloseEnhMetaFile` at `0x180144e73`
- `GDI32!CloseEnhMetaFile` at `0x180145304`
- `GDI32!CloseEnhMetaFile` at `0x180144e73`
- `GDI32!CloseEnhMetaFile` at `0x180145304`
- `GDI32!CreateEnhMetaFileA` at `0x180144e06`
- `GDI32!CreateEnhMetaFileA` at `0x180144e06`
- `GDI32!SetEnhMetaFileBits` at `0x180144b4f`
- `GDI32!SetEnhMetaFileBits` at `0x180144b4f`
- `GDI32!DeleteEnhMetaFile` at `0x1801452f0`
- `GDI32!DeleteEnhMetaFile` at `0x18014531b`
- `GDI32!DeleteEnhMetaFile` at `0x1801452f0`
- `GDI32!DeleteEnhMetaFile` at `0x18014531b`
- `GDI32!SetWorldTransform` at `0x180144e45`
- `GDI32!SetWorldTransform` at `0x180144e45`
- `GDI32!SetGraphicsMode` at `0x180144e2a`
- `GDI32!SetGraphicsMode` at `0x180144e2a`

## pseudocode

```c
__int64 __fastcall DoGdiCommentMultiFormats(__int64 a1, _DWORD *a2)
{
  unsigned int (__fastcall *v2)(_QWORD, _DWORD *, _QWORD, _QWORD); // r10
  unsigned int v5; // r13d
  HDC v6; // r15
  HENHMETAFILE v7; // r12
  unsigned int v8; // r14d
  unsigned int i; // esi
  unsigned int v10; // eax
  UINT v11; // r14d
  unsigned int v12; // esi
  unsigned int *v13; // rax
  int v14; // r12d
  int v15; // r13d
  int v16; // ecx
  __m128i v17; // xmm2
  __m128i v18; // xmm1
  int v19; // edx
  __m128i v20; // xmm2
  __m128i v21; // xmm1
  int v22; // ecx
  int v23; // edx
  int v24; // eax
  int v25; // edi
  int v26; // eax
  int v27; // esi
  int v28; // r14d
  int v29; // eax
  int v30; // r15d
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  LONG v36; // eax
  int v37; // edi
  int v38; // esi
  int v39; // r14d
  int v40; // eax
  int v41; // eax
  int v42; // r15d
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int v46; // eax
  int v47; // eax
  LONG v48; // eax
  HDC v49; // rcx
  HDC v50; // rax
  UINT WinMetaFileBits; // eax
  UINT v52; // edi
  unsigned __int16 *v53; // r15
  unsigned int v54; // edi
  unsigned int v55; // ecx
  HLOCAL v56; // rax
  unsigned int v57; // edx
  __int64 v58; // rcx
  int j; // edi
  int v60; // r13d
  unsigned int v61; // esi
  unsigned int v62; // edi
  __int64 v63; // r14
  signed int v64; // ecx
  unsigned int *k; // rsi
  __int16 v66; // cx
  bool v67; // zf
  unsigned __int16 v68; // cx
  unsigned __int16 v69; // cx
  unsigned __int16 v70; // cx
  int v71; // eax
  int *v72; // rcx
  unsigned __int16 v73; // ax
  unsigned int m; // esi
  __int64 v75; // r14
  unsigned int v76; // r8d
  int n; // edx
  int v78; // ecx
  int v79; // eax
  int v80; // eax
  int v81; // ecx
  unsigned int v83; // [rsp+40h] [rbp-69h]
  int nDenominator; // [rsp+44h] [rbp-65h]
  int nNumerator; // [rsp+48h] [rbp-61h]
  HENHMETAFILE hmf; // [rsp+50h] [rbp-59h]
  RECT *lprect; // [rsp+58h] [rbp-51h]
  __int64 v88; // [rsp+60h] [rbp-49h] BYREF
  RECT rc; // [rsp+68h] [rbp-41h] BYREF
  __int128 v90; // [rsp+78h] [rbp-31h] BYREF
  __int64 v91; // [rsp+88h] [rbp-21h]
  XFORM xf; // [rsp+90h] [rbp-19h] BYREF
  int v93; // [rsp+A8h] [rbp-1h] BYREF
  int v94; // [rsp+ACh] [rbp+3h]
  int v95; // [rsp+B0h] [rbp+7h]
  int v96; // [rsp+B4h] [rbp+Bh]
  int v97; // [rsp+B8h] [rbp+Fh]
  int v98; // [rsp+BCh] [rbp+13h]
  int v99; // [rsp+C0h] [rbp+17h]
  int v100; // [rsp+C4h] [rbp+1Bh]

  v2 = (unsigned int (__fastcall *)(_QWORD, _DWORD *, _QWORD, _QWORD))pfnIsValidEnhMetaRecordOffExt;
  v91 = 0;
  v83 = 0;
  v5 = 0;
  v6 = 0;
  v88 = 0;
  v7 = 0;
  memset(&xf, 0, sizeof(xf));
  v90 = 0;
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
  v8 = 40;
  for ( i = 0; i < a2[9]; ++i )
  {
    v10 = v8 + 16;
    if ( v8 + 16 < v8 )
      return v5;
    v8 += 16;
    if ( v2 )
    {
      if ( !v2(*(_QWORD *)(a1 + 568), a2, 0, v10) )
        return v5;
      v2 = (unsigned int (__fastcall *)(_QWORD, _DWORD *, _QWORD, _QWORD))pfnIsValidEnhMetaRecordOffExt;
    }
    else if ( v10 > a2[1] )
    {
      return v5;
    }
    if ( a2[4 * i + 10] == 1179469088 && a2[4 * i + 11] <= 0x10000u )
      break;
  }
  if ( i < a2[9] )
  {
    v11 = a2[4 * i + 12];
    v12 = a2[4 * i + 13] + 12;
    if ( v12 >= 0xC && (!v2 || v2(*(_QWORD *)(a1 + 568), a2, v12, v11)) )
    {
      hmf = SetEnhMetaFileBits(v11, (const BYTE *)a2 + v12);
      if ( hmf )
      {
        if ( pfnGetTransform )
        {
          if ( !(unsigned int)pfnGetTransform(*(_QWORD *)(a1 + 40), 516, &xf) )
            goto LABEL_172;
        }
        else
        {
          xf = *(XFORM *)&xformIdentity;
        }
        v13 = *(unsigned int **)(a1 + 8);
        v14 = *(_DWORD *)(a1 + 76);
        v15 = *(_DWORD *)(a1 + 68);
        v16 = *(_DWORD *)(a1 + 80);
        v17 = _mm_cvtsi32_si128(v13[18]);
        v18 = _mm_cvtsi32_si128(v13[20]);
        v19 = *(_DWORD *)(a1 + 72);
        *(_QWORD *)((char *)&v90 + 4) = 0;
        nDenominator = v16;
        nNumerator = v19;
        *(float *)&v90 = (float)((float)v14 / (float)v15)
                       / (float)(_mm_cvtepi32_ps(v17).m128_f32[0] / _mm_cvtepi32_ps(v18).m128_f32[0]);
        v20 = _mm_cvtsi32_si128(v13[19]);
        v21 = _mm_cvtsi32_si128(v13[21]);
        v91 = 0;
        *((float *)&v90 + 3) = (float)((float)v16 / (float)v19)
                             / (float)(_mm_cvtepi32_ps(v20).m128_f32[0] / _mm_cvtepi32_ps(v21).m128_f32[0]);
        if ( !(unsigned int)bCombineTransform(&xf, &xf, &v90) )
          goto LABEL_177;
        v22 = a2[6];
        v23 = a2[5];
        lprect = (RECT *)(a2 + 5);
        v95 = a2[7];
        v97 = v95;
        v24 = a2[8];
        v93 = v23;
        v94 = v22;
        v96 = v22;
        v99 = v23;
        v98 = v24;
        v100 = v24;
        if ( !(unsigned int)bXformWorkhorse(&v93, 4, &xf) )
          goto LABEL_177;
        v25 = v95;
        v26 = v95;
        v27 = v93;
        v28 = v97;
        if ( v93 < v95 )
          v26 = v93;
        if ( v26 >= v97 )
        {
          v29 = v97;
        }
        else
        {
          v29 = v95;
          if ( v93 < v95 )
            v29 = v93;
        }
        v30 = v99;
        if ( v29 >= v99 )
        {
          v32 = v99;
        }
        else
        {
          v31 = v95;
          if ( v93 < v95 )
            v31 = v93;
          if ( v31 >= v97 )
          {
            v32 = v97;
          }
          else
          {
            v32 = v95;
            if ( v93 < v95 )
              v32 = v93;
          }
        }
        rc.left = MulDiv(100 * v32, v15, v14);
        v33 = v25;
        if ( v27 > v25 )
          v33 = v27;
        if ( v33 <= v28 )
        {
          v34 = v28;
        }
        else
        {
          v34 = v25;
          if ( v27 > v25 )
            v34 = v27;
        }
        if ( v34 <= v30 )
        {
          v25 = v30;
        }
        else
        {
          v35 = v25;
          if ( v27 > v25 )
            v35 = v27;
          if ( v35 <= v28 )
          {
            v25 = v28;
          }
          else if ( v27 > v25 )
          {
            v25 = v27;
          }
        }
        v36 = MulDiv(100 * v25, v15, v14);
        v37 = v96;
        v38 = v94;
        v39 = v98;
        rc.right = v36;
        v40 = v96;
        if ( v94 < v96 )
          v40 = v94;
        if ( v40 >= v98 )
        {
          v41 = v98;
        }
        else
        {
          v41 = v96;
          if ( v94 < v96 )
            v41 = v94;
        }
        v42 = v100;
        if ( v41 >= v100 )
        {
          v44 = v100;
        }
        else
        {
          v43 = v96;
          if ( v94 < v96 )
            v43 = v94;
          if ( v43 >= v98 )
          {
            v44 = v98;
          }
          else
          {
            v44 = v96;
            if ( v94 < v96 )
              v44 = v94;
          }
        }
        rc.top = MulDiv(100 * v44, nNumerator, nDenominator);
        v45 = v37;
        if ( v38 > v37 )
          v45 = v38;
        if ( v45 <= v39 )
        {
          v46 = v39;
        }
        else
        {
          v46 = v37;
          if ( v38 > v37 )
            v46 = v38;
        }
        if ( v46 <= v42 )
        {
          v37 = v42;
        }
        else
        {
          v47 = v37;
          if ( v38 > v37 )
            v47 = v38;
          if ( v47 <= v39 )
          {
            v37 = v39;
          }
          else if ( v38 > v37 )
          {
            v37 = v38;
          }
        }
        v48 = MulDiv(100 * v37, nNumerator, nDenominator);
        v49 = *(HDC *)(a1 + 48);
        rc.bottom = v48;
        v50 = CreateEnhMetaFileA(v49, 0, &rc, 0);
        v6 = v50;
        if ( !v50 || !SetGraphicsMode(v50, 2) || !SetWorldTransform(v6, &xf) )
        {
LABEL_177:
          v7 = 0;
          v5 = 0;
          goto LABEL_172;
        }
        PlayEnhMetaFile(v6, hmf, lprect);
        v7 = CloseEnhMetaFile(v6);
        v6 = 0;
        WinMetaFileBits = GetWinMetaFileBits(v7, 0, 0, 8, *(HDC *)(a1 + 48));
        v52 = WinMetaFileBits;
        if ( WinMetaFileBits )
        {
          v53 = (unsigned __int16 *)LocalAlloc(0, WinMetaFileBits);
          if ( v53 )
          {
            if ( v52 == GetWinMetaFileBits(v7, v52, (LPBYTE)v53, 8, *(HDC *)(a1 + 48)) )
            {
              if ( !v53[5] )
              {
LABEL_103:
                for ( j = *(_DWORD *)(a1 + 408) - 1; j >= 0; --j )
                {
                  if ( *(_DWORD *)(32LL * j + *(_QWORD *)(a1 + 416)) != 1 )
                    break;
                }
                v60 = j;
                v61 = 0;
                v62 = j + 1;
                if ( v62 )
                {
                  do
                  {
                    v63 = 32LL * v61;
                    if ( *(_DWORD *)(v63 + *(_QWORD *)(a1 + 416)) == 1 )
                    {
                      if ( !(unsigned int)bEmitWin16CreateBrushIndirect(a1, &v88) )
                      {
LABEL_168:
                        v5 = 0;
                        goto LABEL_100;
                      }
                      *(_DWORD *)(v63 + *(_QWORD *)(a1 + 416)) = 9;
                    }
                    ++v61;
                  }
                  while ( v61 < v62 );
                }
                v64 = v62 + v53[5] - 1;
                if ( v64 > *(_DWORD *)(a1 + 500) )
                  *(_DWORD *)(a1 + 500) = v64;
                if ( !(unsigned int)bW16Emit0(a1, 30) )
                  goto LABEL_169;
                for ( k = (unsigned int *)(v53 + 9); ; k = (unsigned int *)((char *)k + 2 * *k) )
                {
                  v73 = *((_WORD *)k + 2);
                  if ( !v73 )
                  {
                    if ( (unsigned int)bW16Emit1(a1, 295, 0xFFFF) )
                    {
                      for ( m = 0; m < v62; ++m )
                      {
                        v75 = 32LL * m;
                        if ( *(_DWORD *)(v75 + *(_QWORD *)(a1 + 416)) == 9 )
                        {
                          if ( !(unsigned int)bW16Emit1(a1, 496, (unsigned __int16)m) )
                            goto LABEL_168;
                          *(_DWORD *)(v75 + *(_QWORD *)(a1 + 416)) = 1;
                        }
                      }
                      if ( v53[5] )
                      {
                        v76 = *(_DWORD *)(a1 + 408);
                        for ( n = 0; v62 < v76; n = v80 )
                        {
                          v78 = *(_DWORD *)(32LL * v62 + *(_QWORD *)(a1 + 416));
                          v79 = v62;
                          if ( v78 == 1 )
                            v79 = v60;
                          v60 = v79;
                          v80 = n + 1;
                          if ( v78 == 1 )
                            v80 = n;
                          ++v62;
                        }
                        v81 = n + v83;
                        if ( n + v83 <= v60 + 1 )
                          v81 = v60 + 1;
                        *(_DWORD *)(a1 + 408) = v81;
                      }
                      v5 = 1;
LABEL_100:
                      LocalFree(v53);
                      v6 = 0;
LABEL_172:
                      DeleteEnhMetaFile(hmf);
                      if ( v6 )
                        v7 = CloseEnhMetaFile(v6);
                      if ( v7 )
                        DeleteEnhMetaFile(v7);
                      return v5;
                    }
LABEL_169:
                    v5 = 0;
                    goto LABEL_100;
                  }
                  if ( v73 > 0x20Bu )
                    break;
                  switch ( v73 )
                  {
                    case 0x20Bu:
                      continue;
                    case 0x127u:
                      break;
                    case 0x12Au:
                    case 0x12Bu:
                      goto LABEL_142;
                    case 0x12Cu:
                      v66 = *((_WORD *)k + 3);
                      if ( v66 )
                      {
                        v67 = (_WORD)v62 + v66 == 0;
                        v68 = v62 + v66;
                        *((_WORD *)k + 3) = v68;
                        if ( v67 || (unsigned int)v68 >= *(_DWORD *)(a1 + 408) )
                          goto LABEL_169;
                        *(_DWORD *)(32LL * v68 + *(_QWORD *)(a1 + 416)) = 8;
                      }
                      break;
                    case 0x12Du:
                    case 0x1F0u:
                      goto LABEL_142;
                  }
LABEL_147:
                  if ( !(unsigned int)bEmit(a1, k, 2 * *k) )
                    goto LABEL_169;
                  vUpdateMaxRecord(a1, k);
LABEL_149:
                  ;
                }
                if ( v73 == 524 )
                  goto LABEL_149;
                if ( v73 != 552 )
                {
                  if ( v73 == 564 )
                  {
LABEL_142:
                    v67 = *((_WORD *)k + 3) + (_WORD)v62 == 0;
                    v70 = *((_WORD *)k + 3) + v62;
                    *((_WORD *)k + 3) = v70;
                    if ( v67 || (unsigned int)v70 >= *(_DWORD *)(a1 + 408) )
                      goto LABEL_169;
                    v71 = 1;
                    v72 = (int *)(*(_QWORD *)(a1 + 416) + 32LL * v70);
                    if ( *((_WORD *)k + 2) != 496 )
                      v71 = 8;
                    *v72 = v71;
                    goto LABEL_147;
                  }
                  if ( v73 != 1065 )
                  {
                    if ( v73 == 1574
                      && v73 == 1574
                      && *k > 0x16
                      && *((_WORD *)k + 3) == 15
                      && *(unsigned int *)((char *)k + 10) == 1128680791
                      && *(unsigned int *)((char *)k + 14) == 1 )
                    {
                      goto LABEL_149;
                    }
                    goto LABEL_147;
                  }
                }
                v67 = *((_WORD *)k + 4) + (_WORD)v62 == 0;
                v69 = *((_WORD *)k + 4) + v62;
                *((_WORD *)k + 4) = v69;
                if ( v67 || (unsigned int)v69 >= *(_DWORD *)(a1 + 408) )
                  goto LABEL_169;
                *(_DWORD *)(32LL * v69 + *(_QWORD *)(a1 + 416)) = 8;
                goto LABEL_142;
              }
              v54 = *(_DWORD *)(a1 + 408);
              v55 = v54 + v53[5];
              v83 = v54;
              if ( v55 <= 0xFFFF )
              {
                *(_DWORD *)(a1 + 408) = v55;
                v56 = LocalReAlloc(*(HLOCAL *)(a1 + 416), 32 * v55, 2u);
                if ( !v56 )
                {
                  *(_DWORD *)(a1 + 408) = v54;
                  goto LABEL_99;
                }
                v57 = v54;
                for ( *(_QWORD *)(a1 + 416) = v56;
                      v57 < *(_DWORD *)(a1 + 408);
                      *(_QWORD *)(v58 + *(_QWORD *)(a1 + 416) + 8) = 0 )
                {
                  v58 = v57++;
                  v58 *= 32;
                  *(_DWORD *)(v58 + *(_QWORD *)(a1 + 416)) = 1;
                }
                goto LABEL_103;
              }
            }
LABEL_99:
            v5 = 0;
            goto LABEL_100;
          }
          v6 = 0;
        }
        v5 = 0;
        goto LABEL_172;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1801449dc  mov     [rsp-8+arg_10], rbx
0x1801449e1  push    rbp
0x1801449e2  push    rsi
0x1801449e3  push    rdi
0x1801449e4  push    r12
0x1801449e6  push    r13
0x1801449e8  push    r14
0x1801449ea  push    r15
0x1801449ec  lea     rbp, [rsp-27h]
0x1801449f1  sub     rsp, 0D0h
0x1801449f8  mov     rax, cs:__security_cookie
0x1801449ff  xor     rax, rsp
0x180144a02  mov     [rbp+57h+var_38], rax
0x180144a06  mov     r10, cs:pfnIsValidEnhMetaRecordOffExt
0x180144a0d  xor     eax, eax
0x180144a0f  xorps   xmm0, xmm0
0x180144a12  mov     qword ptr [rbp+57h+xf.eDx], rax
0x180144a16  mov     rdi, rdx
0x180144a19  mov     [rbp+57h+var_78], rax
0x180144a1d  xor     edx, edx
0x180144a1f  xorps   xmm1, xmm1
0x180144a22  mov     [rbp+57h+var_C0], edx
0x180144a25  mov     rbx, rcx
0x180144a28  mov     [rbp+57h+var_D0], edx
0x180144a2b  mov     r13d, edx
0x180144a2e  mov     [rbp+57h+var_C8], rdx
0x180144a32  mov     r15d, edx
0x180144a35  mov     [rbp+57h+var_A0], rdx
0x180144a39  mov     r12d, edx
0x180144a3c  movups  xmmword ptr [rbp+57h+xf.eM11], xmm0
0x180144a40  movups  [rbp+57h+var_88], xmm1
0x180144a44  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x180144a48  test    r10, r10
0x180144a4b  jz      short loc_180144A79
0x180144a4d  mov     rcx, [rcx+238h]
0x180144a54  lea     r9d, [rdx+38h]
0x180144a58  mov     rdx, rdi
0x180144a5b  xor     r8d, r8d
0x180144a5e  mov     rax, r10
0x180144a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144a66  xor     edx, edx
0x180144a68  test    eax, eax
0x180144a6a  jz      loc_180145327
0x180144a70  mov     r10, cs:pfnIsValidEnhMetaRecordOffExt
0x180144a77  jmp     short loc_180144A83
0x180144a79  cmp     dword ptr [rdi+4], 38h ; '8'
0x180144a7d  jb      loc_180145327
0x180144a83  mov     r14d, 28h ; '('
0x180144a89  mov     esi, edx
0x180144a8b  cmp     [rdi+24h], edx
0x180144a8e  jbe     short loc_180144AF9
0x180144a90  lea     eax, [r14+10h]
0x180144a94  cmp     eax, r14d
0x180144a97  jb      loc_180145327
0x180144a9d  mov     r14d, eax
0x180144aa0  test    r10, r10
0x180144aa3  jz      short loc_180144AD0
0x180144aa5  mov     rcx, [rbx+238h]
0x180144aac  mov     r9d, eax
0x180144aaf  mov     rax, r10
0x180144ab2  xor     r8d, r8d
0x180144ab5  mov     rdx, rdi
0x180144ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144abd  xor     edx, edx
0x180144abf  test    eax, eax
0x180144ac1  jz      loc_180145327
0x180144ac7  mov     r10, cs:pfnIsValidEnhMetaRecordOffExt
0x180144ace  jmp     short loc_180144AD9
0x180144ad0  cmp     eax, [rdi+4]
0x180144ad3  ja      loc_180145327
0x180144ad9  mov     eax, esi
0x180144adb  add     rax, rax
0x180144ade  cmp     dword ptr [rdi+rax*8+28h], 464D4520h
0x180144ae6  jnz     short loc_180144AF2
0x180144ae8  cmp     dword ptr [rdi+rax*8+2Ch], 10000h
0x180144af0  jbe     short loc_180144AF9
0x180144af2  inc     esi
0x180144af4  cmp     esi, [rdi+24h]
0x180144af7  jb      short loc_180144A90
0x180144af9  cmp     esi, [rdi+24h]
0x180144afc  jnb     loc_180145327
0x180144b02  mov     ecx, esi
0x180144b04  lea     rax, [rcx+3]
0x180144b08  add     rcx, rcx
0x180144b0b  add     rax, rax
0x180144b0e  mov     esi, [rdi+rcx*8+34h]
0x180144b12  mov     r14d, [rdi+rax*8]
0x180144b16  add     esi, 0Ch
0x180144b19  cmp     esi, 0Ch
0x180144b1c  jb      loc_180145327
0x180144b22  test    r10, r10
0x180144b25  jz      short loc_180144B47
0x180144b27  mov     rcx, [rbx+238h]
0x180144b2e  mov     r9d, r14d
0x180144b31  mov     r8d, esi
0x180144b34  mov     rdx, rdi
0x180144b37  mov     rax, r10
0x180144b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144b3f  test    eax, eax
0x180144b41  jz      loc_180145327
0x180144b47  mov     edx, esi
0x180144b49  mov     ecx, r14d; nSize
0x180144b4c  add     rdx, rdi; pb
0x180144b4f  call    cs:__imp_SetEnhMetaFileBits
0x180144b56  nop     dword ptr [rax+rax+00h]
0x180144b5b  xor     r14d, r14d
0x180144b5e  mov     [rbp+57h+hmf], rax
0x180144b62  test    rax, rax
0x180144b65  jz      loc_180145327
0x180144b6b  mov     rax, cs:pfnGetTransform
0x180144b72  test    rax, rax
0x180144b75  jz      short loc_180144B93
0x180144b77  mov     rcx, [rbx+28h]
0x180144b7b  lea     r8, [rbp+57h+xf]
0x180144b7f  mov     edx, 204h
0x180144b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144b89  test    eax, eax
0x180144b8b  jz      loc_1801452EC
0x180144b91  jmp     short loc_180144BAB
0x180144b93  movups  xmm0, xmmword ptr cs:xformIdentity
0x180144b9a  movsd   xmm1, qword ptr cs:xformIdentity+10h
0x180144ba2  movups  xmmword ptr [rbp+57h+xf.eM11], xmm0
0x180144ba6  movsd   qword ptr [rbp+57h+xf.eDx], xmm1
0x180144bab  mov     rax, [rbx+8]
0x180144baf  lea     r8, [rbp+57h+var_88]
0x180144bb3  mov     r12d, [rbx+4Ch]
0x180144bb7  mov     r13d, [rbx+44h]
0x180144bbb  mov     ecx, [rbx+50h]
0x180144bbe  movd    xmm2, dword ptr [rax+48h]
0x180144bc3  movd    xmm1, dword ptr [rax+50h]
0x180144bc8  mov     edx, [rbx+48h]
0x180144bcb  and     dword ptr [rbp+57h+var_88+4], r14d
0x180144bcf  and     dword ptr [rbp+57h+var_88+8], r14d
0x180144bd3  cvtdq2ps xmm2, xmm2
0x180144bd6  mov     [rbp+57h+nDenominator], ecx
0x180144bd9  mov     [rbp+57h+nNumerator], edx
0x180144bdc  cvtdq2ps xmm1, xmm1
0x180144bdf  movd    xmm3, r12d
0x180144be4  cvtdq2ps xmm3, xmm3
0x180144be7  divss   xmm2, xmm1
0x180144beb  movd    xmm0, r13d
0x180144bf0  cvtdq2ps xmm0, xmm0
0x180144bf3  divss   xmm3, xmm0
0x180144bf7  movd    xmm0, edx
0x180144bfb  lea     rdx, [rbp+57h+xf]
0x180144bff  divss   xmm3, xmm2
0x180144c03  cvtdq2ps xmm0, xmm0
0x180144c06  movss   dword ptr [rbp+57h+var_88], xmm3
0x180144c0b  movd    xmm2, dword ptr [rax+4Ch]
0x180144c10  movd    xmm1, dword ptr [rax+54h]
0x180144c15  and     dword ptr [rbp+57h+var_78], r14d
0x180144c19  and     dword ptr [rbp+57h+var_78+4], r14d
0x180144c1d  movd    xmm3, ecx
0x180144c21  lea     rcx, [rbp+57h+xf]
0x180144c25  cvtdq2ps xmm3, xmm3
0x180144c28  cvtdq2ps xmm2, xmm2
0x180144c2b  cvtdq2ps xmm1, xmm1
0x180144c2e  divss   xmm3, xmm0
0x180144c32  divss   xmm2, xmm1
0x180144c36  divss   xmm3, xmm2
0x180144c3a  movss   dword ptr [rbp+57h+var_88+0Ch], xmm3
0x180144c3f  call    bCombineTransform
0x180144c44  test    eax, eax
0x180144c46  jz      loc_180145352
0x180144c4c  mov     ecx, [rdi+18h]
0x180144c4f  lea     rax, [rdi+14h]
0x180144c53  mov     edx, [rax]
0x180144c55  lea     r8, [rbp+57h+xf]
0x180144c59  mov     [rbp+57h+lprect], rax
0x180144c5d  mov     eax, [rdi+1Ch]
0x180144c60  mov     [rbp+57h+var_50], eax
0x180144c63  mov     [rbp+57h+var_48], eax
0x180144c66  mov     eax, [rdi+20h]
0x180144c69  mov     [rbp+57h+var_58], edx
0x180144c6c  mov     [rbp+57h+var_54], ecx
0x180144c6f  mov     [rbp+57h+var_4C], ecx
0x180144c72  lea     rcx, [rbp+57h+var_58]
0x180144c76  mov     [rbp+57h+var_40], edx
0x180144c79  mov     edx, 4
0x180144c7e  mov     [rbp+57h+var_44], eax
0x180144c81  mov     [rbp+57h+var_3C], eax
0x180144c84  call    bXformWorkhorse
0x180144c89  test    eax, eax
0x180144c8b  jz      loc_180145352
0x180144c91  mov     edi, [rbp+57h+var_50]
0x180144c94  mov     eax, edi
0x180144c96  mov     esi, [rbp+57h+var_58]
0x180144c99  cmp     esi, edi
0x180144c9b  mov     r14d, [rbp+57h+var_48]
0x180144c9f  cmovl   eax, esi
0x180144ca2  cmp     eax, r14d
0x180144ca5  jge     short loc_180144CB0
0x180144ca7  cmp     esi, edi
0x180144ca9  mov     eax, edi
0x180144cab  cmovl   eax, esi
0x180144cae  jmp     short loc_180144CB3
0x180144cb0  mov     eax, r14d
0x180144cb3  mov     r15d, [rbp+57h+var_40]
0x180144cb7  cmp     eax, r15d
0x180144cba  jge     short loc_180144CD6
0x180144cbc  cmp     esi, edi
0x180144cbe  mov     eax, edi
0x180144cc0  cmovl   eax, esi
0x180144cc3  cmp     eax, r14d
0x180144cc6  jge     short loc_180144CD1
0x180144cc8  cmp     esi, edi
0x180144cca  mov     eax, edi
0x180144ccc  cmovl   eax, esi
0x180144ccf  jmp     short loc_180144CD9
0x180144cd1  mov     eax, r14d
0x180144cd4  jmp     short loc_180144CD9
0x180144cd6  mov     eax, r15d
0x180144cd9  imul    ecx, eax, 64h ; 'd'; nNumber
0x180144cdc  mov     r8d, r12d; nDenominator
0x180144cdf  mov     edx, r13d; nNumerator
0x180144ce2  call    cs:__imp_MulDiv
0x180144ce9  nop     dword ptr [rax+rax+00h]
0x180144cee  mov     [rbp+57h+rc.left], eax
0x180144cf1  cmp     esi, edi
0x180144cf3  mov     eax, edi
0x180144cf5  cmovg   eax, esi
0x180144cf8  cmp     eax, r14d
0x180144cfb  jle     short loc_180144D06
0x180144cfd  cmp     esi, edi
0x180144cff  mov     eax, edi
0x180144d01  cmovg   eax, esi
0x180144d04  jmp     short loc_180144D09
0x180144d06  mov     eax, r14d
0x180144d09  cmp     eax, r15d
0x180144d0c  jle     short loc_180144D26
0x180144d0e  cmp     esi, edi
0x180144d10  mov     eax, edi
0x180144d12  cmovg   eax, esi
0x180144d15  cmp     eax, r14d
0x180144d18  jle     short loc_180144D21
0x180144d1a  cmp     esi, edi
0x180144d1c  cmovg   edi, esi
0x180144d1f  jmp     short loc_180144D29
0x180144d21  mov     edi, r14d
0x180144d24  jmp     short loc_180144D29
0x180144d26  mov     edi, r15d
0x180144d29  imul    ecx, edi, 64h ; 'd'; nNumber
0x180144d2c  mov     r8d, r12d; nDenominator
0x180144d2f  mov     edx, r13d; nNumerator
0x180144d32  call    cs:__imp_MulDiv
0x180144d39  nop     dword ptr [rax+rax+00h]
0x180144d3e  mov     edi, [rbp+57h+var_4C]
0x180144d41  mov     esi, [rbp+57h+var_54]
0x180144d44  cmp     esi, edi
0x180144d46  mov     r14d, [rbp+57h+var_44]
0x180144d4a  mov     [rbp+57h+rc.right], eax
0x180144d4d  mov     eax, edi
0x180144d4f  cmovl   eax, esi
0x180144d52  cmp     eax, r14d
0x180144d55  jge     short loc_180144D60
0x180144d57  cmp     esi, edi
0x180144d59  mov     eax, edi
0x180144d5b  cmovl   eax, esi
0x180144d5e  jmp     short loc_180144D63
0x180144d60  mov     eax, r14d
0x180144d63  mov     r15d, [rbp+57h+var_3C]
0x180144d67  cmp     eax, r15d
0x180144d6a  jge     short loc_180144D86
0x180144d6c  cmp     esi, edi
0x180144d6e  mov     eax, edi
0x180144d70  cmovl   eax, esi
0x180144d73  cmp     eax, r14d
0x180144d76  jge     short loc_180144D81
0x180144d78  cmp     esi, edi
0x180144d7a  mov     eax, edi
0x180144d7c  cmovl   eax, esi
0x180144d7f  jmp     short loc_180144D89
0x180144d81  mov     eax, r14d
0x180144d84  jmp     short loc_180144D89
0x180144d86  mov     eax, r15d
0x180144d89  mov     r12d, [rbp+57h+nDenominator]
0x180144d8d  mov     r8d, r12d; nDenominator
0x180144d90  mov     r13d, [rbp+57h+nNumerator]
0x180144d94  mov     edx, r13d; nNumerator
0x180144d97  imul    ecx, eax, 64h ; 'd'; nNumber
0x180144d9a  call    cs:__imp_MulDiv
0x180144da1  nop     dword ptr [rax+rax+00h]
0x180144da6  mov     [rbp+57h+rc.top], eax
0x180144da9  cmp     esi, edi
0x180144dab  mov     eax, edi
0x180144dad  cmovg   eax, esi
0x180144db0  cmp     eax, r14d
0x180144db3  jle     short loc_180144DBE
0x180144db5  cmp     esi, edi
0x180144db7  mov     eax, edi
0x180144db9  cmovg   eax, esi
0x180144dbc  jmp     short loc_180144DC1
0x180144dbe  mov     eax, r14d
0x180144dc1  cmp     eax, r15d
0x180144dc4  jle     short loc_180144DDE
0x180144dc6  cmp     esi, edi
0x180144dc8  mov     eax, edi
0x180144dca  cmovg   eax, esi
0x180144dcd  cmp     eax, r14d
0x180144dd0  jle     short loc_180144DD9
  ... truncated ...
```
