# DoExtTextOut

- ea: `0x1800c320c`
- end: `0x1800c3baf`
- name: `DoExtTextOut`
- size: `2467`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800c30c0`
- `0x18013f9d0`

## callees

- `0x1800c20c8`
- `0x1800c2194`
- `0x1800c26e4`
- `0x1800c320c`
- `0x1800c3bb8`
- `0x1800c3cc0`
- `0x1800c3da4`
- `0x1800c3f0c`
- `0x1800c4204`
- `0x1800c42f4`
- `0x1800c49e8`
- `0x1800c4b24`
- `0x1800fe680`
- `0x1801440ec`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByteEx` at `0x1800c37e1`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByteEx` at `0x1800c37e1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c3375`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c3468`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c36ad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c3758`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c3375`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c3468`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c36ad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c3758`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c33b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c369a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c3ba4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c33b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c369a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c3ba4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c335f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c3451`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c3792`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c335f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c3451`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c3792`
- `GDI32!GetTextCharset` at `0x1800c332d`
- `GDI32!GetTextCharset` at `0x1800c332d`
- `GDI32!GetCurrentPositionEx` at `0x1800c3549`
- `GDI32!GetCurrentPositionEx` at `0x1800c361a`
- `GDI32!GetCurrentPositionEx` at `0x1800c3b5a`
- `GDI32!GetCurrentPositionEx` at `0x1800c3549`
- `GDI32!GetCurrentPositionEx` at `0x1800c361a`
- `GDI32!GetCurrentPositionEx` at `0x1800c3b5a`
- `GDI32!ExtTextOutA` at `0x1800c368c`
- `GDI32!ExtTextOutA` at `0x1800c3866`
- `GDI32!ExtTextOutA` at `0x1800c368c`
- `GDI32!ExtTextOutA` at `0x1800c3866`
- `GDI32!MoveToEx` at `0x1800c364d`
- `GDI32!MoveToEx` at `0x1800c3b8f`
- `GDI32!MoveToEx` at `0x1800c364d`
- `GDI32!MoveToEx` at `0x1800c3b8f`
- `GDI32!GetTextAlign` at `0x1800c32a0`
- `GDI32!GetTextAlign` at `0x1800c32a0`
- `GDI32!ExtTextOutW` at `0x1800c386e`
- `GDI32!ExtTextOutW` at `0x1800c3b2e`
- `GDI32!ExtTextOutW` at `0x1800c386e`
- `GDI32!ExtTextOutW` at `0x1800c3b2e`
- `GDI32!SetGraphicsMode` at `0x1800c3821`
- `GDI32!SetGraphicsMode` at `0x1800c3885`
- `GDI32!SetGraphicsMode` at `0x1800c3821`
- `GDI32!SetGraphicsMode` at `0x1800c3885`

## pseudocode

```c
__int64 __fastcall DoExtTextOut(
        __int64 a1,
        int a2,
        int a3,
        UINT a4,
        RECT *a5,
        const WCHAR *lpString,
        unsigned int cchWideChar,
        INT *a8,
        int iMode,
        int a10)
{
  __int64 v10; // rbx
  int v11; // r13d
  int v12; // eax
  char v13; // di
  bool v14; // zf
  HDC *v15; // rsi
  HDC v16; // rcx
  __int64 v17; // r14
  int v18; // ecx
  int v19; // eax
  __int64 v20; // r8
  __int64 v21; // r9
  LONG CodePage; // eax
  HDC v23; // rcx
  UINT v24; // edi
  const WCHAR *v25; // rax
  unsigned int v26; // eax
  unsigned int cbMultiByte; // esi
  CHAR *lpMultiByteStr; // rax
  WCHAR *v29; // rsi
  char v30; // di
  UINT v31; // r12d
  unsigned int v32; // ebx
  int v34; // edi
  int v35; // edx
  int v36; // r8d
  INT *v37; // r9
  __int64 v38; // rcx
  __int64 k; // rdx
  LONG v40; // r12d
  HDC v41; // rcx
  HDC *v42; // rdi
  HDC v43; // rcx
  const WCHAR *v44; // r10
  __int64 v45; // r8
  __int64 v46; // rdi
  unsigned __int64 v47; // rcx
  CHAR *v48; // rax
  INT *v49; // r8
  __int64 v50; // rdi
  __int64 v51; // rbx
  __int64 v52; // r12
  UINT v53; // r13d
  BOOL v54; // eax
  HDC v55; // rcx
  BOOL v56; // eax
  unsigned int v57; // esi
  int v58; // eax
  unsigned int v59; // edi
  __int64 v60; // r8
  __int64 v61; // r9
  __int64 v62; // r8
  __int64 v63; // r9
  unsigned __int16 v64; // di
  LPCWCH v65; // r9
  WCHAR v66; // ax
  int v67; // eax
  int v68; // ecx
  __int64 i; // rdx
  int j; // edi
  unsigned __int16 v71; // [rsp+50h] [rbp-A1h]
  int v72; // [rsp+54h] [rbp-9Dh]
  struct tagPOINT pt; // [rsp+58h] [rbp-99h] BYREF
  WCHAR *v74; // [rsp+60h] [rbp-91h]
  int y; // [rsp+68h] [rbp-89h]
  int x; // [rsp+6Ch] [rbp-85h]
  UINT options; // [rsp+70h] [rbp-81h]
  int v78; // [rsp+78h] [rbp-79h] BYREF
  int v79; // [rsp+7Ch] [rbp-75h]
  struct tagPOINT v80; // [rsp+80h] [rbp-71h] BYREF
  LPCWCH lpWideCharStr; // [rsp+88h] [rbp-69h]
  INT *lpDx; // [rsp+90h] [rbp-61h]
  UINT TextAlign; // [rsp+98h] [rbp-59h]
  int v84; // [rsp+9Ch] [rbp-55h]
  __int64 v85; // [rsp+A0h] [rbp-51h] BYREF
  RECT *lprect; // [rsp+A8h] [rbp-49h]
  HLOCAL hMem; // [rsp+B0h] [rbp-41h]
  __int64 v88; // [rsp+B8h] [rbp-39h]
  RECT v89; // [rsp+C0h] [rbp-31h] BYREF
  __int128 v90; // [rsp+D0h] [rbp-21h] BYREF

  v10 = a1;
  v11 = cchWideChar;
  v12 = a3;
  v88 = a1;
  v13 = a4;
  v14 = (*(_BYTE *)(a1 + 4) & 8) == 0;
  v15 = (HDC *)(a1 + 40);
  options = a4;
  y = a3;
  x = a2;
  lprect = a5;
  lpWideCharStr = lpString;
  lpDx = a8;
  v85 = 0;
  v78 = a2;
  v79 = a3;
  if ( !v14 )
  {
    if ( iMode != 2 )
    {
      SetGraphicsMode(*v15, iMode);
      v12 = y;
      a2 = x;
    }
    if ( !pfnSetVirtualResolution )
    {
      if ( !(unsigned int)bXformWorkhorse(&v78, 1, v10 + 84) )
        return 0;
      v12 = v79;
      a2 = v78;
    }
    v55 = *v15;
    if ( a10 == 83 )
      v56 = ExtTextOutA(v55, a2, v12, options, lprect, (LPCSTR)lpString, cchWideChar, a8);
    else
      v56 = ExtTextOutW(v55, a2, v12, options, lprect, lpString, cchWideChar, a8);
    v32 = v56;
    if ( iMode != 2 )
      SetGraphicsMode(*v15, 2);
    return v32;
  }
  v16 = *v15;
  v17 = 0;
  hMem = 0;
  v71 = a4;
  v74 = 0;
  v72 = 0;
  TextAlign = GetTextAlign(v16);
  v80.x = TextAlign & 1;
  if ( (TextAlign & 1) == 0 )
  {
    v18 = y;
    v19 = x;
LABEL_4:
    v78 = v19;
    v79 = v18;
    if ( (unsigned int)bXformWorkhorse(&v78, 1, v10 + 228) )
    {
      if ( (v13 & 6) == 0 )
        goto LABEL_6;
      v14 = (*(_BYTE *)(v10 + 4) & 4) == 0;
      v89 = *lprect;
      if ( v14 )
      {
        if ( (unsigned int)bXformWorkhorse(&v89, 2, v10 + 228) )
        {
          LOWORD(v85) = v89.left;
          WORD1(v85) = v89.top;
          WORD2(v85) = v89.right;
          HIWORD(v85) = v89.bottom;
          goto LABEL_6;
        }
      }
      else
      {
        if ( (v13 & 2) != 0 )
        {
          v57 = *(_DWORD *)(v10 + 440);
          pt.x = *(_DWORD *)(v10 + 436);
          v90 = 0;
          if ( (unsigned int)DoSelectObject(v10, 2147483656LL, v20, v21) )
          {
            v58 = *(_DWORD *)(v10 + 428);
            v59 = *(_DWORD *)(v10 + 412) - 21;
            LODWORD(v90) = 0;
            DWORD1(v90) = v58;
            *((_QWORD *)&v90 + 1) = 0;
            if ( (unsigned int)DoCreateBrushIndirect(v10, v59, &v90) )
            {
              if ( (unsigned int)DoSelectObject(v10, v59, v60, v61) )
              {
                if ( (unsigned int)bConicCommon(
                                     v10,
                                     (unsigned int)v89.left,
                                     (unsigned int)v89.top,
                                     (unsigned int)v89.right,
                                     v89.bottom,
                                     0,
                                     0,
                                     0,
                                     0,
                                     43) )
                  v71 = options & 0xFFFD;
                DoSelectObject(v10, v57, v62, v63);
              }
              DoDeleteObject(v10, v59);
            }
            DoSelectObject(v10, (unsigned int)pt.x, v60, v61);
          }
          v64 = v71;
          if ( (v71 & 2) != 0 )
            goto LABEL_62;
        }
        else
        {
          v64 = v71;
        }
        if ( (v64 & 4) == 0
          || (unsigned int)DoSaveDC(v10)
          && (v71 = v64 & 0xFFFB,
              (unsigned int)DoClipRect(
                              v10,
                              (unsigned int)v89.left,
                              (unsigned int)v89.top,
                              (unsigned int)v89.right,
                              v89.bottom,
                              30)) )
        {
LABEL_6:
          v84 = a10;
          if ( a10 != 84 )
          {
            v29 = (WCHAR *)lpWideCharStr;
LABEL_29:
            v34 = v11 + 1;
            v17 = (__int64)LocalAlloc(0, 8LL * (unsigned int)(v11 + 1));
            if ( v17 )
            {
              v35 = 1;
              v36 = y;
              *(_DWORD *)v17 = x;
              *(_DWORD *)(v17 + 4) = v36;
              pt.x = 0;
              if ( v34 > 1 )
              {
                v37 = lpDx;
                do
                {
                  v38 = (unsigned int)v35++;
                  *(_DWORD *)(v17 + 8 * v38) = v37[v38 - 1] + *(_DWORD *)(v17 + 8 * v38 - 8);
                  *(_DWORD *)(v17 + 8 * v38 + 4) = v36;
                }
                while ( v35 < v34 );
              }
              if ( (*(_BYTE *)(v10 + 4) & 4) != 0 )
              {
                v67 = TextAlign & 6;
                if ( v67 == 2 )
                {
                  v40 = 1;
                  v68 = *(_DWORD *)v17 - *(_DWORD *)(v17 + 8LL * (unsigned int)v11);
                }
                else
                {
                  v68 = 0;
                  if ( v67 == 6 )
                  {
                    v40 = 1;
                    v68 = (*(_DWORD *)v17 - *(_DWORD *)(v17 + 8LL * (unsigned int)v11)) / 2;
                  }
                  else
                  {
                    v40 = 0;
                  }
                }
                for ( i = 0; (int)i < v34; i = (unsigned int)(i + 1) )
                  *(_DWORD *)(v17 + 8 * i) += v68;
                if ( !(unsigned int)bXformWorkhorse(v17, (unsigned int)v34, v10 + 228) )
                {
LABEL_39:
                  if ( !v40 )
                    goto LABEL_40;
LABEL_119:
                  bW16Emit1(v10, 302, (unsigned __int16)TextAlign);
                  goto LABEL_40;
                }
                if ( v40 && !(unsigned int)bW16Emit1(v10, 302, (unsigned __int16)TextAlign & 0xFFF9) )
                  goto LABEL_119;
                for ( j = 0; j < v11; ++j )
                {
                  if ( !(unsigned int)bEmitWin16ExtTextOut(
                                        v10,
                                        *(unsigned __int16 *)(v17 + 8LL * j),
                                        *(unsigned __int16 *)(v17 + 8LL * j + 4),
                                        v71,
                                        0,
                                        (__int64)v29 + j,
                                        1,
                                        0) )
                    goto LABEL_39;
                }
LABEL_38:
                v72 = 1;
                goto LABEL_39;
              }
              if ( (unsigned int)bXformWorkhorse(v17, (unsigned int)v34, v10 + 228) )
              {
                for ( k = 0; (int)k < v11; k = (unsigned int)(k + 1) )
                  *(_WORD *)(v17 + 2 * k) = *(_WORD *)(v17 + 8 * k + 8) - *(_WORD *)(v17 + 8 * k);
                v30 = v71;
                if ( !(unsigned int)bEmitWin16ExtTextOut(
                                      v10,
                                      (unsigned __int16)v78,
                                      (unsigned __int16)v79,
                                      v71,
                                      (__int64)&v85,
                                      (__int64)v29,
                                      v11,
                                      v17) )
                {
                  v29 = v74;
                  goto LABEL_12;
                }
                v40 = pt.x;
                goto LABEL_38;
              }
            }
LABEL_40:
            v29 = v74;
            goto LABEL_11;
          }
          CodePage = GetCodePage(*(_QWORD *)(v10 + 40));
          v23 = *(HDC *)(v10 + 40);
          v24 = CodePage;
          pt.x = CodePage;
          if ( GetTextCharset(v23) == 2 )
          {
            hMem = LocalAlloc(0, 2LL * cchWideChar);
            v44 = (const WCHAR *)hMem;
            if ( !hMem )
              goto LABEL_57;
            v45 = 0;
            if ( cchWideChar )
            {
              v65 = lpWideCharStr;
              do
              {
                v66 = v65[v45] - 4096;
                if ( (unsigned __int16)(v65[v45] - 32) > 0xDFu )
                  v66 = v65[v45];
                v44[v45] = v66;
                v45 = (unsigned int)(v45 + 1);
              }
              while ( (unsigned int)v45 < cchWideChar );
            }
            v25 = v44;
            lpWideCharStr = v44;
          }
          else
          {
            v25 = lpWideCharStr;
          }
          v26 = WideCharToMultiByte(v24, 0, v25, cchWideChar, 0, 0, 0, 0);
          cbMultiByte = v26;
          if ( v26 == cchWideChar )
          {
            lpMultiByteStr = (CHAR *)LocalAlloc(0, cchWideChar);
            v29 = (WCHAR *)lpMultiByteStr;
            if ( !lpMultiByteStr )
            {
LABEL_11:
              v30 = v71;
LABEL_12:
              v31 = options;
              if ( (options & 4) != 0 && (v30 & 4) == 0 )
                DoRestoreDC(v10, 0xFFFFFFFFLL);
              if ( v72 && v80.x )
              {
                v42 = (HDC *)(v10 + 40);
                v80 = 0;
                if ( !pfnSetVirtualResolution && GetCurrentPositionEx(*v42, &v80) )
                {
                  v72 = bXformWorkhorse(&v80, 1, v10 + 108);
                  if ( !v72 )
                  {
                    v32 = 0;
                    goto LABEL_15;
                  }
                  MoveToEx(*v42, v80.x, v80.y, 0);
                }
                v43 = *v42;
                if ( v84 == 83 )
                  ExtTextOutA(v43, x, y, v31, lprect, (LPCSTR)lpWideCharStr, v11, lpDx);
                else
                  ExtTextOutW(v43, x, y, v31, lprect, lpWideCharStr, v11, lpDx);
                v14 = pfnSetVirtualResolution == 0;
                *(_DWORD *)(v10 + 360) = 0x7FFFFFFF;
                *(_DWORD *)(v10 + 364) = 0x7FFFFFFF;
                if ( v14 && GetCurrentPositionEx(*v42, &v80) )
                {
                  v32 = bXformWorkhorse(&v80, 1, v10 + 84);
                  if ( v32 )
                    MoveToEx(*v42, v80.x, v80.y, 0);
                  goto LABEL_15;
                }
              }
              v32 = v72;
LABEL_15:
              if ( v29 )
                LocalFree(v29);
              if ( v17 )
                LocalFree((HLOCAL)v17);
              if ( hMem )
                LocalFree(hMem);
              return v32;
            }
            WideCharToMultiByte(v24, 0, lpWideCharStr, cchWideChar, lpMultiByteStr, cchWideChar, 0, 0);
            goto LABEL_28;
          }
          if ( v26 + 3 >= v26 )
          {
            v46 = (v26 + 3) & 0xFFFFFFFC;
            v47 = v46 * ((options & 0x2000) != 0 ? 9LL : 5LL);
            if ( v47 <= 0xFFFFFFFF )
            {
              v48 = (CHAR *)LocalAlloc(0x40u, (unsigned int)v47);
              *(_QWORD *)&v90 = v48;
              if ( !v48 )
              {
                v29 = 0;
                goto LABEL_11;
              }
              v84 = 83;
              WideCharToMultiByte(pt.x, 0, lpWideCharStr, cchWideChar, v48, cbMultiByte, 0, 0);
              v11 = cbMultiByte;
              lpWideCharStr = (LPCWCH)v90;
              LODWORD(v74) = cbMultiByte;
              if ( lpDx )
              {
                *(_QWORD *)&v89.left = lpDx;
                v49 = (INT *)(v46 + v90);
                v50 = 0;
                lpDx = v49;
                if ( cbMultiByte )
                {
                  v51 = *(_QWORD *)&v89.left;
                  v52 = v90;
                  v53 = pt.x;
                  do
                  {
                    v49[v50] = *(_DWORD *)(v51 + 4 * v17);
                    v54 = IsDBCSLeadByteEx(v53, *(_BYTE *)(v50 + v52));
                    v49 = lpDx;
                    if ( v54 )
                    {
                      v50 = (unsigned int)(v50 + 1);
                      lpDx[v50] = 0;
                    }
                    v50 = (unsigned int)(v50 + 1);
                    v17 = (unsigned int)(v17 + 1);
                  }
                  while ( (unsigned int)v50 < cbMultiByte );
                  v10 = v88;
                  v11 = (int)v74;
                }
                v29 = (WCHAR *)v90;
              }
              else
              {
                v29 = (WCHAR *)v90;
              }
LABEL_28:
              v74 = v29;
              goto LABEL_29;
            }
          }
LABEL_57:
          v29 = 0;
          goto LABEL_11;
        }
      }
    }
LABEL_62:
    v84 = a10;
    goto LABEL_57;
  }
  v41 = *v15;
  pt = 0;
  if ( !GetCurrentPositionEx(v41, &pt) )
    goto LABEL_62;
  if ( pfnSetVirtualResolution || (unsigned int)bXformWorkhorse(&pt, 1, v10 + 108) )
  {
    if ( !(unsigned int)bValidateMetaFileCP(v10, (unsigned int)pt.x, (unsigned int)pt.y) )
      goto LABEL_62;
    v19 = pt.x;
    v18 = pt.y;
    x = pt.x;
    y = pt.y;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x1800c320c  push    rbp
0x1800c320e  push    rbx
0x1800c320f  push    rsi
0x1800c3210  push    rdi
0x1800c3211  push    r12
0x1800c3213  push    r13
0x1800c3215  push    r14
0x1800c3217  push    r15
0x1800c3219  lea     rbp, [rsp-7]
0x1800c321e  sub     rsp, 0F8h
0x1800c3225  mov     rax, cs:__security_cookie
0x1800c322c  xor     rax, rsp
0x1800c322f  mov     [rbp+3Fh+var_50], rax
0x1800c3233  mov     r14, [rbp+3Fh+lpString]
0x1800c3237  mov     rbx, rcx
0x1800c323a  mov     r15, [rbp+3Fh+arg_38]
0x1800c3241  xor     r12d, r12d
0x1800c3244  mov     r13d, [rbp+3Fh+cchWideChar]
0x1800c3248  mov     eax, r8d
0x1800c324b  mov     [rbp+3Fh+var_78], rcx
0x1800c324f  mov     edi, r9d
0x1800c3252  test    byte ptr [rbx+4], 8
0x1800c3256  lea     rsi, [rbx+28h]
0x1800c325a  mov     rcx, [rbp+3Fh+arg_20]
0x1800c325e  mov     [rsp+130h+options], r9d
0x1800c3263  mov     [rsp+130h+y], eax
0x1800c3267  mov     [rsp+130h+x], edx
0x1800c326b  mov     [rbp+3Fh+lprect], rcx
0x1800c326f  mov     [rbp+3Fh+lpWideCharStr], r14
0x1800c3273  mov     [rbp+3Fh+lpDx], r15
0x1800c3277  mov     [rbp+3Fh+var_90], r12
0x1800c327b  mov     [rbp+3Fh+var_B8], edx
0x1800c327e  mov     [rbp+3Fh+var_B4], eax
0x1800c3281  jnz     loc_1800C33F1
0x1800c3287  mov     rcx, [rsi]; hdc
0x1800c328a  mov     r14d, r12d
0x1800c328d  mov     [rbp+3Fh+hMem], r12
0x1800c3291  mov     [rsp+130h+var_E0], di
0x1800c3296  mov     [rsp+130h+var_D0], r12
0x1800c329b  mov     [rsp+130h+var_DC], r12d
0x1800c32a0  call    cs:__imp_GetTextAlign
0x1800c32a6  lea     r15d, [r12+1]
0x1800c32ab  mov     [rbp+3Fh+var_98], eax
0x1800c32ae  and     eax, r15d
0x1800c32b1  mov     [rbp+3Fh+var_B0.x], eax
0x1800c32b4  jnz     loc_1800C353C
0x1800c32ba  mov     ecx, [rsp+130h+y]
0x1800c32be  mov     eax, [rsp+130h+x]
0x1800c32c2  mov     word ptr [rbp+3Fh+var_B8], ax
0x1800c32c6  lea     rsi, [rbx+0E4h]
0x1800c32cd  sar     eax, 10h
0x1800c32d0  mov     r8, rsi
0x1800c32d3  mov     word ptr [rbp+3Fh+var_B8+2], ax
0x1800c32d7  mov     edx, r15d
0x1800c32da  mov     eax, ecx
0x1800c32dc  mov     word ptr [rbp+3Fh+var_B4], cx
0x1800c32e0  sar     eax, 10h
0x1800c32e3  lea     rcx, [rbp+3Fh+var_B8]
0x1800c32e7  mov     word ptr [rbp+3Fh+var_B4+2], ax
0x1800c32eb  call    bXformWorkhorse
0x1800c32f0  test    eax, eax
0x1800c32f2  jz      loc_1800C36FD
0x1800c32f8  mov     r12d, 2
0x1800c32fe  test    dil, 6
0x1800c3302  jnz     loc_1800C35A7
0x1800c3308  mov     eax, [rbp+3Fh+arg_48]
0x1800c330e  mov     [rbp+3Fh+var_94], eax
0x1800c3311  cmp     eax, 54h ; 'T'
0x1800c3314  jnz     loc_1800C3712
0x1800c331a  mov     rcx, [rbx+28h]
0x1800c331e  call    GetCodePage
0x1800c3323  mov     rcx, [rbx+28h]; hdc
0x1800c3327  mov     edi, eax
0x1800c3329  mov     [rsp+130h+pt.x], eax
0x1800c332d  call    cs:__imp_GetTextCharset
0x1800c3333  cmp     eax, r12d
0x1800c3336  jz      loc_1800C36A5
0x1800c333c  mov     rax, [rbp+3Fh+lpWideCharStr]
0x1800c3340  xor     ecx, ecx
0x1800c3342  mov     r9d, r13d; cchWideChar
0x1800c3345  mov     [rsp+130h+lpUsedDefaultChar], rcx; lpUsedDefaultChar
0x1800c334a  mov     r8, rax; lpWideCharStr
0x1800c334d  mov     [rsp+130h+lpDefaultChar], rcx; lpDefaultChar
0x1800c3352  xor     edx, edx; dwFlags
0x1800c3354  mov     [rsp+130h+cbMultiByte], ecx; cbMultiByte
0x1800c3358  mov     [rsp+130h+lpMultiByteStr], rcx; lpMultiByteStr
0x1800c335d  mov     ecx, edi; CodePage
0x1800c335f  call    cs:__imp_WideCharToMultiByte
0x1800c3365  mov     esi, eax
0x1800c3367  cmp     eax, r13d
0x1800c336a  jnz     loc_1800C371B
0x1800c3370  mov     rdx, r13; uBytes
0x1800c3373  xor     ecx, ecx; uFlags
0x1800c3375  call    cs:__imp_LocalAlloc
0x1800c337b  mov     rsi, rax
0x1800c337e  test    rax, rax
0x1800c3381  jnz     loc_1800C3432
0x1800c3387  movzx   edi, [rsp+130h+var_E0]
0x1800c338c  mov     r12d, [rsp+130h+options]
0x1800c3391  test    r12b, 4
0x1800c3395  jnz     loc_1800C3B14
0x1800c339b  xor     eax, eax
0x1800c339d  cmp     [rsp+130h+var_DC], eax
0x1800c33a1  jnz     loc_1800C35F9
0x1800c33a7  mov     ebx, [rsp+130h+var_DC]
0x1800c33ab  test    rsi, rsi
0x1800c33ae  jz      short loc_1800C33B9
0x1800c33b0  mov     rcx, rsi; hMem
0x1800c33b3  call    cs:__imp_LocalFree
0x1800c33b9  test    r14, r14
0x1800c33bc  jnz     loc_1800C3697
0x1800c33c2  mov     rax, [rbp+3Fh+hMem]
0x1800c33c6  test    rax, rax
0x1800c33c9  jnz     loc_1800C3BA1
0x1800c33cf  mov     eax, ebx
0x1800c33d1  mov     rcx, [rbp+3Fh+var_50]
0x1800c33d5  xor     rcx, rsp; StackCookie
0x1800c33d8  call    __security_check_cookie
0x1800c33dd  add     rsp, 0F8h
0x1800c33e4  pop     r15
0x1800c33e6  pop     r14
0x1800c33e8  pop     r13
0x1800c33ea  pop     r12
0x1800c33ec  pop     rdi
0x1800c33ed  pop     rsi
0x1800c33ee  pop     rbx
0x1800c33ef  pop     rbp
0x1800c33f0  retn
0x1800c33f1  mov     edi, [rbp+3Fh+iMode]
0x1800c33f7  mov     r12d, 2
0x1800c33fd  cmp     edi, r12d
0x1800c3400  jnz     loc_1800C381C
0x1800c3406  cmp     cs:pfnSetVirtualResolution, 0
0x1800c340e  jnz     loc_1800C383A
0x1800c3414  lea     r8, [rbx+54h]
0x1800c3418  mov     edx, 1
0x1800c341d  lea     rcx, [rbp+3Fh+var_B8]
0x1800c3421  call    bXformWorkhorse
0x1800c3426  test    eax, eax
0x1800c3428  jnz     loc_1800C3834
0x1800c342e  xor     eax, eax
0x1800c3430  jmp     short loc_1800C33D1
0x1800c3432  mov     r8, [rbp+3Fh+lpWideCharStr]; lpWideCharStr
0x1800c3436  mov     r9d, r13d; cchWideChar
0x1800c3439  mov     [rsp+130h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x1800c343e  xor     edx, edx; dwFlags
0x1800c3440  mov     [rsp+130h+lpDefaultChar], r14; lpDefaultChar
0x1800c3445  mov     ecx, edi; CodePage
0x1800c3447  mov     [rsp+130h+cbMultiByte], r13d; cbMultiByte
0x1800c344c  mov     [rsp+130h+lpMultiByteStr], rax; lpMultiByteStr
0x1800c3451  call    cs:__imp_WideCharToMultiByte
0x1800c3457  mov     [rsp+130h+var_D0], rsi
0x1800c345c  lea     edi, [r13+1]
0x1800c3460  xor     ecx, ecx; uFlags
0x1800c3462  mov     edx, edi
0x1800c3464  shl     rdx, 3; uBytes
0x1800c3468  call    cs:__imp_LocalAlloc
0x1800c346e  mov     r14, rax
0x1800c3471  test    rax, rax
0x1800c3474  jz      loc_1800C3532
0x1800c347a  mov     eax, [rsp+130h+x]
0x1800c347e  mov     edx, r15d
0x1800c3481  mov     r8d, [rsp+130h+y]
0x1800c3486  mov     [r14], eax
0x1800c3489  mov     [r14+4], r8d
0x1800c348d  mov     [rsp+130h+pt.x], 0
0x1800c3495  cmp     edi, r15d
0x1800c3498  jle     short loc_1800C34BA
0x1800c349a  mov     r9, [rbp+3Fh+lpDx]
0x1800c349e  mov     ecx, edx
0x1800c34a0  add     edx, r15d
0x1800c34a3  mov     eax, [r14+rcx*8-8]
0x1800c34a8  add     eax, [r9+rcx*4-4]
0x1800c34ad  mov     [r14+rcx*8], eax
0x1800c34b1  mov     [r14+rcx*8+4], r8d
0x1800c34b6  cmp     edx, edi
0x1800c34b8  jl      short loc_1800C349E
0x1800c34ba  test    byte ptr [rbx+4], 4
0x1800c34be  jnz     loc_1800C3A1F
0x1800c34c4  lea     r8, [rbx+0E4h]
0x1800c34cb  mov     edx, edi
0x1800c34cd  mov     rcx, r14
0x1800c34d0  call    bXformWorkhorse
0x1800c34d5  test    eax, eax
0x1800c34d7  jz      short loc_1800C3532
0x1800c34d9  xor     edx, edx
0x1800c34db  test    r13d, r13d
0x1800c34de  jg      loc_1800C36C7
0x1800c34e4  movzx   edi, [rsp+130h+var_E0]
0x1800c34e9  lea     rax, [rbp+3Fh+var_90]
0x1800c34ed  movzx   r8d, word ptr [rbp+3Fh+var_B4]
0x1800c34f2  movzx   r9d, di
0x1800c34f6  movzx   edx, word ptr [rbp+3Fh+var_B8]
0x1800c34fa  mov     rcx, rbx
0x1800c34fd  mov     [rsp+130h+lpUsedDefaultChar], r14
0x1800c3502  mov     word ptr [rsp+130h+lpDefaultChar], r13w
0x1800c3508  mov     qword ptr [rsp+130h+cbMultiByte], rsi
0x1800c350d  mov     [rsp+130h+lpMultiByteStr], rax
0x1800c3512  call    bEmitWin16ExtTextOut
0x1800c3517  test    eax, eax
0x1800c3519  jz      loc_1800C3708
0x1800c351f  mov     r12d, [rsp+130h+pt.x]
0x1800c3524  mov     [rsp+130h+var_DC], r15d
0x1800c3529  test    r12d, r12d
0x1800c352c  jnz     loc_1800C3AFD
0x1800c3532  mov     rsi, [rsp+130h+var_D0]
0x1800c3537  jmp     loc_1800C3387
0x1800c353c  mov     rcx, [rsi]; hdc
0x1800c353f  lea     rdx, [rsp+130h+pt]; lppt
0x1800c3544  mov     qword ptr [rsp+130h+pt.x], r12
0x1800c3549  call    cs:__imp_GetCurrentPositionEx
0x1800c354f  test    eax, eax
0x1800c3551  jz      loc_1800C36FD
0x1800c3557  cmp     cs:pfnSetVirtualResolution, r12
0x1800c355e  jnz     short loc_1800C3579
0x1800c3560  lea     r8, [rbx+6Ch]
0x1800c3564  mov     edx, r15d
0x1800c3567  lea     rcx, [rsp+130h+pt]
0x1800c356c  call    bXformWorkhorse
0x1800c3571  test    eax, eax
0x1800c3573  jz      loc_1800C342E
0x1800c3579  mov     r8d, [rsp+130h+pt.y]
0x1800c357e  mov     rcx, rbx
0x1800c3581  mov     edx, [rsp+130h+pt.x]
0x1800c3585  call    bValidateMetaFileCP
0x1800c358a  test    eax, eax
0x1800c358c  jz      loc_1800C36FD
0x1800c3592  mov     eax, [rsp+130h+pt.x]
0x1800c3596  mov     ecx, [rsp+130h+pt.y]
0x1800c359a  mov     [rsp+130h+x], eax
0x1800c359e  mov     [rsp+130h+y], ecx
0x1800c35a2  jmp     loc_1800C32C2
0x1800c35a7  test    byte ptr [rbx+4], 4
0x1800c35ab  mov     rcx, [rbp+3Fh+lprect]
0x1800c35af  movups  xmm0, xmmword ptr [rcx]
0x1800c35b2  movdqu  [rbp+3Fh+var_70], xmm0
0x1800c35b7  jnz     loc_1800C3890
0x1800c35bd  mov     r8, rsi
0x1800c35c0  lea     rcx, [rbp+3Fh+var_70]
0x1800c35c4  mov     edx, r12d
0x1800c35c7  call    bXformWorkhorse
0x1800c35cc  test    eax, eax
0x1800c35ce  jz      loc_1800C36FD
0x1800c35d4  movzx   eax, word ptr [rbp+3Fh+var_70]
0x1800c35d8  mov     word ptr [rbp+3Fh+var_90], ax
0x1800c35dc  movzx   eax, word ptr [rbp+3Fh+var_70+4]
0x1800c35e0  mov     word ptr [rbp+3Fh+var_90+2], ax
0x1800c35e4  movzx   eax, word ptr [rbp+3Fh+var_70+8]
0x1800c35e8  mov     word ptr [rbp+3Fh+var_90+4], ax
0x1800c35ec  movzx   eax, word ptr [rbp+3Fh+var_70+0Ch]
0x1800c35f0  mov     word ptr [rbp+3Fh+var_90+6], ax
0x1800c35f4  jmp     loc_1800C3308
0x1800c35f9  cmp     [rbp+3Fh+var_B0.x], eax
0x1800c35fc  jz      loc_1800C33A7
0x1800c3602  cmp     cs:pfnSetVirtualResolution, rax
0x1800c3609  lea     rdi, [rbx+28h]
0x1800c360d  mov     qword ptr [rbp+3Fh+var_B0.x], rax
0x1800c3611  jnz     short loc_1800C3653
0x1800c3613  mov     rcx, [rdi]; hdc
0x1800c3616  lea     rdx, [rbp+3Fh+var_B0]; lppt
0x1800c361a  call    cs:__imp_GetCurrentPositionEx
0x1800c3620  test    eax, eax
0x1800c3622  jz      short loc_1800C3653
0x1800c3624  lea     r8, [rbx+6Ch]
0x1800c3628  mov     edx, r15d
0x1800c362b  lea     rcx, [rbp+3Fh+var_B0]
0x1800c362f  call    bXformWorkhorse
0x1800c3634  mov     [rsp+130h+var_DC], eax
0x1800c3638  test    eax, eax
0x1800c363a  jz      loc_1800C3B9A
0x1800c3640  mov     r8d, [rbp+3Fh+var_B0.y]; y
0x1800c3644  xor     r9d, r9d; lppt
0x1800c3647  mov     edx, [rbp+3Fh+var_B0.x]; x
0x1800c364a  mov     rcx, [rdi]; hdc
0x1800c364d  call    cs:__imp_MoveToEx
0x1800c3653  cmp     [rbp+3Fh+var_94], 53h ; 'S'
0x1800c3657  mov     r9d, r12d; options
0x1800c365a  mov     rax, [rbp+3Fh+lpDx]
0x1800c365e  mov     r8d, [rsp+130h+y]; y
0x1800c3663  mov     edx, [rsp+130h+x]; x
0x1800c3667  mov     rcx, [rdi]; hdc
0x1800c366a  mov     [rsp+130h+lpUsedDefaultChar], rax; lpDx
0x1800c366f  mov     rax, [rbp+3Fh+lpWideCharStr]
0x1800c3673  mov     dword ptr [rsp+130h+lpDefaultChar], r13d; c
0x1800c3678  mov     qword ptr [rsp+130h+cbMultiByte], rax; lpString
0x1800c367d  mov     rax, [rbp+3Fh+lprect]
0x1800c3681  mov     [rsp+130h+lpMultiByteStr], rax; lprect
0x1800c3686  jnz     loc_1800C3B2E
0x1800c368c  call    cs:__imp_ExtTextOutA
0x1800c3692  jmp     loc_1800C3B34
0x1800c3697  mov     rcx, r14; hMem
0x1800c369a  call    cs:__imp_LocalFree
0x1800c36a0  jmp     loc_1800C33C2
0x1800c36a5  mov     rdx, r13
0x1800c36a8  xor     ecx, ecx; uFlags
0x1800c36aa  add     rdx, rdx; uBytes
0x1800c36ad  call    cs:__imp_LocalAlloc
0x1800c36b3  mov     [rbp+3Fh+hMem], rax
0x1800c36b7  mov     r10, rax
0x1800c36ba  test    rax, rax
  ... truncated ...
```
