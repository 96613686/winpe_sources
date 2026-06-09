# DoExtTextOut

- ea: `0x1800c6ed0`
- end: `0x1800c7904`
- name: `DoExtTextOut`
- size: `2612`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800c6d80`
- `0x1801481c0`

## callees

- `0x1800c5cd8`
- `0x1800c5db4`
- `0x1800c6354`
- `0x1800c6ed0`
- `0x1800c790c`
- `0x1800c7a1c`
- `0x1800c7b0c`
- `0x1800c7c8c`
- `0x1800c7f84`
- `0x1800c807c`
- `0x1800c87fc`
- `0x1800c8944`
- `0x180105d40`
- `0x18014cc50`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByteEx` at `0x1800c7500`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByteEx` at `0x1800c7500`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c704b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c7151`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c73ba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c746b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c704b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c7151`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c73ba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c746b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c708f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c73a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c78f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c708f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c73a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c78f3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c702f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c7134`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c74ab`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c702f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c7134`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c74ab`
- `GDI32!GetTextCharset` at `0x1800c6ff7`
- `GDI32!GetTextCharset` at `0x1800c6ff7`
- `GDI32!GetCurrentPositionEx` at `0x1800c7238`
- `GDI32!GetCurrentPositionEx` at `0x1800c730f`
- `GDI32!GetCurrentPositionEx` at `0x1800c789d`
- `GDI32!GetCurrentPositionEx` at `0x1800c7238`
- `GDI32!GetCurrentPositionEx` at `0x1800c730f`
- `GDI32!GetCurrentPositionEx` at `0x1800c789d`
- `GDI32!ExtTextOutA` at `0x1800c738d`
- `GDI32!ExtTextOutA` at `0x1800c7591`
- `GDI32!ExtTextOutA` at `0x1800c738d`
- `GDI32!ExtTextOutA` at `0x1800c7591`
- `GDI32!MoveToEx` at `0x1800c7348`
- `GDI32!MoveToEx` at `0x1800c78d8`
- `GDI32!MoveToEx` at `0x1800c7348`
- `GDI32!MoveToEx` at `0x1800c78d8`
- `GDI32!GetTextAlign` at `0x1800c6f64`
- `GDI32!GetTextAlign` at `0x1800c6f64`
- `GDI32!ExtTextOutW` at `0x1800c759f`
- `GDI32!ExtTextOutW` at `0x1800c786b`
- `GDI32!ExtTextOutW` at `0x1800c759f`
- `GDI32!ExtTextOutW` at `0x1800c786b`
- `GDI32!SetGraphicsMode` at `0x1800c7546`
- `GDI32!SetGraphicsMode` at `0x1800c75bc`
- `GDI32!SetGraphicsMode` at `0x1800c7546`
- `GDI32!SetGraphicsMode` at `0x1800c75bc`

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
  LONG v53; // r13d
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
0x1800c6ed0  push    rbp
0x1800c6ed2  push    rbx
0x1800c6ed3  push    rsi
0x1800c6ed4  push    rdi
0x1800c6ed5  push    r12
0x1800c6ed7  push    r13
0x1800c6ed9  push    r14
0x1800c6edb  push    r15
0x1800c6edd  lea     rbp, [rsp-7]
0x1800c6ee2  sub     rsp, 0F8h
0x1800c6ee9  mov     rax, cs:__security_cookie
0x1800c6ef0  xor     rax, rsp
0x1800c6ef3  mov     [rbp+3Fh+var_50], rax
0x1800c6ef7  mov     r14, [rbp+3Fh+lpString]
0x1800c6efb  mov     rbx, rcx
0x1800c6efe  mov     r15, [rbp+3Fh+arg_38]
0x1800c6f05  xor     r12d, r12d
0x1800c6f08  mov     r13d, [rbp+3Fh+cchWideChar]
0x1800c6f0c  mov     eax, r8d
0x1800c6f0f  mov     [rbp+3Fh+var_78], rcx
0x1800c6f13  mov     edi, r9d
0x1800c6f16  test    byte ptr [rbx+4], 8
0x1800c6f1a  lea     rsi, [rbx+28h]
0x1800c6f1e  mov     rcx, [rbp+3Fh+arg_20]
0x1800c6f22  mov     [rsp+130h+options], r9d
0x1800c6f27  mov     [rsp+130h+y], eax
0x1800c6f2b  mov     [rsp+130h+x], edx
0x1800c6f2f  mov     [rbp+3Fh+lprect], rcx
0x1800c6f33  mov     [rbp+3Fh+lpWideCharStr], r14
0x1800c6f37  mov     [rbp+3Fh+lpDx], r15
0x1800c6f3b  mov     [rbp+3Fh+var_90], r12
0x1800c6f3f  mov     [rbp+3Fh+var_B8], edx
0x1800c6f42  mov     [rbp+3Fh+var_B4], eax
0x1800c6f45  jnz     loc_1800C70D4
0x1800c6f4b  mov     rcx, [rsi]; hdc
0x1800c6f4e  mov     r14d, r12d
0x1800c6f51  mov     [rbp+3Fh+hMem], r12
0x1800c6f55  mov     [rsp+130h+var_E0], di
0x1800c6f5a  mov     [rsp+130h+var_D0], r12
0x1800c6f5f  mov     [rsp+130h+var_DC], r12d
0x1800c6f64  call    cs:__imp_GetTextAlign
0x1800c6f6b  nop     dword ptr [rax+rax+00h]
0x1800c6f70  lea     r15d, [r12+1]
0x1800c6f75  mov     [rbp+3Fh+var_98], eax
0x1800c6f78  and     eax, r15d
0x1800c6f7b  mov     [rbp+3Fh+var_B0.x], eax
0x1800c6f7e  jnz     loc_1800C722B
0x1800c6f84  mov     ecx, [rsp+130h+y]
0x1800c6f88  mov     eax, [rsp+130h+x]
0x1800c6f8c  mov     word ptr [rbp+3Fh+var_B8], ax
0x1800c6f90  lea     rsi, [rbx+0E4h]
0x1800c6f97  sar     eax, 10h
0x1800c6f9a  mov     r8, rsi
0x1800c6f9d  mov     word ptr [rbp+3Fh+var_B8+2], ax
0x1800c6fa1  mov     edx, r15d
0x1800c6fa4  mov     eax, ecx
0x1800c6fa6  mov     word ptr [rbp+3Fh+var_B4], cx
0x1800c6faa  sar     eax, 10h
0x1800c6fad  lea     rcx, [rbp+3Fh+var_B8]
0x1800c6fb1  mov     word ptr [rbp+3Fh+var_B4+2], ax
0x1800c6fb5  call    bXformWorkhorse
0x1800c6fba  test    eax, eax
0x1800c6fbc  jz      loc_1800C7410
0x1800c6fc2  mov     r12d, 2
0x1800c6fc8  test    dil, 6
0x1800c6fcc  jnz     loc_1800C729C
0x1800c6fd2  mov     eax, [rbp+3Fh+arg_48]
0x1800c6fd8  mov     [rbp+3Fh+var_94], eax
0x1800c6fdb  cmp     eax, 54h ; 'T'
0x1800c6fde  jnz     loc_1800C7425
0x1800c6fe4  mov     rcx, [rbx+28h]
0x1800c6fe8  call    GetCodePage
0x1800c6fed  mov     rcx, [rbx+28h]; hdc
0x1800c6ff1  mov     edi, eax
0x1800c6ff3  mov     [rsp+130h+pt.x], eax
0x1800c6ff7  call    cs:__imp_GetTextCharset
0x1800c6ffe  nop     dword ptr [rax+rax+00h]
0x1800c7003  cmp     eax, r12d
0x1800c7006  jz      loc_1800C73B2
0x1800c700c  mov     rax, [rbp+3Fh+lpWideCharStr]
0x1800c7010  xor     ecx, ecx
0x1800c7012  mov     r9d, r13d; cchWideChar
0x1800c7015  mov     [rsp+130h+lpUsedDefaultChar], rcx; lpUsedDefaultChar
0x1800c701a  mov     r8, rax; lpWideCharStr
0x1800c701d  mov     [rsp+130h+lpDefaultChar], rcx; lpDefaultChar
0x1800c7022  xor     edx, edx; dwFlags
0x1800c7024  mov     [rsp+130h+cbMultiByte], ecx; cbMultiByte
0x1800c7028  mov     [rsp+130h+lpMultiByteStr], rcx; lpMultiByteStr
0x1800c702d  mov     ecx, edi; CodePage
0x1800c702f  call    cs:__imp_WideCharToMultiByte
0x1800c7036  nop     dword ptr [rax+rax+00h]
0x1800c703b  mov     esi, eax
0x1800c703d  cmp     eax, r13d
0x1800c7040  jnz     loc_1800C742E
0x1800c7046  mov     rdx, r13; uBytes
0x1800c7049  xor     ecx, ecx; uFlags
0x1800c704b  call    cs:__imp_LocalAlloc
0x1800c7052  nop     dword ptr [rax+rax+00h]
0x1800c7057  mov     rsi, rax
0x1800c705a  test    rax, rax
0x1800c705d  jnz     loc_1800C7115
0x1800c7063  movzx   edi, [rsp+130h+var_E0]
0x1800c7068  mov     r12d, [rsp+130h+options]
0x1800c706d  test    r12b, 4
0x1800c7071  jnz     loc_1800C7851
0x1800c7077  xor     eax, eax
0x1800c7079  cmp     [rsp+130h+var_DC], eax
0x1800c707d  jnz     loc_1800C72EE
0x1800c7083  mov     ebx, [rsp+130h+var_DC]
0x1800c7087  test    rsi, rsi
0x1800c708a  jz      short loc_1800C709B
0x1800c708c  mov     rcx, rsi; hMem
0x1800c708f  call    cs:__imp_LocalFree
0x1800c7096  nop     dword ptr [rax+rax+00h]
0x1800c709b  test    r14, r14
0x1800c709e  jnz     loc_1800C739E
0x1800c70a4  mov     rax, [rbp+3Fh+hMem]
0x1800c70a8  test    rax, rax
0x1800c70ab  jnz     loc_1800C78F0
0x1800c70b1  mov     eax, ebx
0x1800c70b3  mov     rcx, [rbp+3Fh+var_50]
0x1800c70b7  xor     rcx, rsp; StackCookie
0x1800c70ba  call    __security_check_cookie
0x1800c70bf  add     rsp, 0F8h
0x1800c70c6  pop     r15
0x1800c70c8  pop     r14
0x1800c70ca  pop     r13
0x1800c70cc  pop     r12
0x1800c70ce  pop     rdi
0x1800c70cf  pop     rsi
0x1800c70d0  pop     rbx
0x1800c70d1  pop     rbp
0x1800c70d2  retn
0x1800c70d4  mov     edi, [rbp+3Fh+iMode]
0x1800c70da  mov     r12d, 2
0x1800c70e0  cmp     edi, r12d
0x1800c70e3  jnz     loc_1800C7541
0x1800c70e9  cmp     cs:pfnSetVirtualResolution, 0
0x1800c70f1  jnz     loc_1800C7565
0x1800c70f7  lea     r8, [rbx+54h]
0x1800c70fb  mov     edx, 1
0x1800c7100  lea     rcx, [rbp+3Fh+var_B8]
0x1800c7104  call    bXformWorkhorse
0x1800c7109  test    eax, eax
0x1800c710b  jnz     loc_1800C755F
0x1800c7111  xor     eax, eax
0x1800c7113  jmp     short loc_1800C70B3
0x1800c7115  mov     r8, [rbp+3Fh+lpWideCharStr]; lpWideCharStr
0x1800c7119  mov     r9d, r13d; cchWideChar
0x1800c711c  mov     [rsp+130h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x1800c7121  xor     edx, edx; dwFlags
0x1800c7123  mov     [rsp+130h+lpDefaultChar], r14; lpDefaultChar
0x1800c7128  mov     ecx, edi; CodePage
0x1800c712a  mov     [rsp+130h+cbMultiByte], r13d; cbMultiByte
0x1800c712f  mov     [rsp+130h+lpMultiByteStr], rax; lpMultiByteStr
0x1800c7134  call    cs:__imp_WideCharToMultiByte
0x1800c713b  nop     dword ptr [rax+rax+00h]
0x1800c7140  mov     [rsp+130h+var_D0], rsi
0x1800c7145  lea     edi, [r13+1]
0x1800c7149  xor     ecx, ecx; uFlags
0x1800c714b  mov     edx, edi
0x1800c714d  shl     rdx, 3; uBytes
0x1800c7151  call    cs:__imp_LocalAlloc
0x1800c7158  nop     dword ptr [rax+rax+00h]
0x1800c715d  mov     r14, rax
0x1800c7160  test    rax, rax
0x1800c7163  jz      loc_1800C7221
0x1800c7169  mov     eax, [rsp+130h+x]
0x1800c716d  mov     edx, r15d
0x1800c7170  mov     r8d, [rsp+130h+y]
0x1800c7175  mov     [r14], eax
0x1800c7178  mov     [r14+4], r8d
0x1800c717c  mov     [rsp+130h+pt.x], 0
0x1800c7184  cmp     edi, r15d
0x1800c7187  jle     short loc_1800C71A9
0x1800c7189  mov     r9, [rbp+3Fh+lpDx]
0x1800c718d  mov     ecx, edx
0x1800c718f  add     edx, r15d
0x1800c7192  mov     eax, [r14+rcx*8-8]
0x1800c7197  add     eax, [r9+rcx*4-4]
0x1800c719c  mov     [r14+rcx*8], eax
0x1800c71a0  mov     [r14+rcx*8+4], r8d
0x1800c71a5  cmp     edx, edi
0x1800c71a7  jl      short loc_1800C718D
0x1800c71a9  test    byte ptr [rbx+4], 4
0x1800c71ad  jnz     loc_1800C775C
0x1800c71b3  lea     r8, [rbx+0E4h]
0x1800c71ba  mov     edx, edi
0x1800c71bc  mov     rcx, r14
0x1800c71bf  call    bXformWorkhorse
0x1800c71c4  test    eax, eax
0x1800c71c6  jz      short loc_1800C7221
0x1800c71c8  xor     edx, edx
0x1800c71ca  test    r13d, r13d
0x1800c71cd  jg      loc_1800C73DA
0x1800c71d3  movzx   edi, [rsp+130h+var_E0]
0x1800c71d8  lea     rax, [rbp+3Fh+var_90]
0x1800c71dc  movzx   r8d, word ptr [rbp+3Fh+var_B4]
0x1800c71e1  movzx   r9d, di
0x1800c71e5  movzx   edx, word ptr [rbp+3Fh+var_B8]
0x1800c71e9  mov     rcx, rbx
0x1800c71ec  mov     [rsp+130h+lpUsedDefaultChar], r14
0x1800c71f1  mov     word ptr [rsp+130h+lpDefaultChar], r13w
0x1800c71f7  mov     qword ptr [rsp+130h+cbMultiByte], rsi
0x1800c71fc  mov     [rsp+130h+lpMultiByteStr], rax
0x1800c7201  call    bEmitWin16ExtTextOut
0x1800c7206  test    eax, eax
0x1800c7208  jz      loc_1800C741B
0x1800c720e  mov     r12d, [rsp+130h+pt.x]
0x1800c7213  mov     [rsp+130h+var_DC], r15d
0x1800c7218  test    r12d, r12d
0x1800c721b  jnz     loc_1800C783A
0x1800c7221  mov     rsi, [rsp+130h+var_D0]
0x1800c7226  jmp     loc_1800C7063
0x1800c722b  mov     rcx, [rsi]; hdc
0x1800c722e  lea     rdx, [rsp+130h+pt]; lppt
0x1800c7233  mov     qword ptr [rsp+130h+pt.x], r12
0x1800c7238  call    cs:__imp_GetCurrentPositionEx
0x1800c723f  nop     dword ptr [rax+rax+00h]
0x1800c7244  test    eax, eax
0x1800c7246  jz      loc_1800C7410
0x1800c724c  cmp     cs:pfnSetVirtualResolution, r12
0x1800c7253  jnz     short loc_1800C726E
0x1800c7255  lea     r8, [rbx+6Ch]
0x1800c7259  mov     edx, r15d
0x1800c725c  lea     rcx, [rsp+130h+pt]
0x1800c7261  call    bXformWorkhorse
0x1800c7266  test    eax, eax
0x1800c7268  jz      loc_1800C7111
0x1800c726e  mov     r8d, [rsp+130h+pt.y]
0x1800c7273  mov     rcx, rbx
0x1800c7276  mov     edx, [rsp+130h+pt.x]
0x1800c727a  call    bValidateMetaFileCP
0x1800c727f  test    eax, eax
0x1800c7281  jz      loc_1800C7410
0x1800c7287  mov     eax, [rsp+130h+pt.x]
0x1800c728b  mov     ecx, [rsp+130h+pt.y]
0x1800c728f  mov     [rsp+130h+x], eax
0x1800c7293  mov     [rsp+130h+y], ecx
0x1800c7297  jmp     loc_1800C6F8C
0x1800c729c  test    byte ptr [rbx+4], 4
0x1800c72a0  mov     rcx, [rbp+3Fh+lprect]
0x1800c72a4  movups  xmm0, xmmword ptr [rcx]
0x1800c72a7  movdqu  [rbp+3Fh+var_70], xmm0
0x1800c72ac  jnz     loc_1800C75CD
0x1800c72b2  mov     r8, rsi
0x1800c72b5  lea     rcx, [rbp+3Fh+var_70]
0x1800c72b9  mov     edx, r12d
0x1800c72bc  call    bXformWorkhorse
0x1800c72c1  test    eax, eax
0x1800c72c3  jz      loc_1800C7410
0x1800c72c9  movzx   eax, word ptr [rbp+3Fh+var_70]
0x1800c72cd  mov     word ptr [rbp+3Fh+var_90], ax
0x1800c72d1  movzx   eax, word ptr [rbp+3Fh+var_70+4]
0x1800c72d5  mov     word ptr [rbp+3Fh+var_90+2], ax
0x1800c72d9  movzx   eax, word ptr [rbp+3Fh+var_70+8]
0x1800c72dd  mov     word ptr [rbp+3Fh+var_90+4], ax
0x1800c72e1  movzx   eax, word ptr [rbp+3Fh+var_70+0Ch]
0x1800c72e5  mov     word ptr [rbp+3Fh+var_90+6], ax
0x1800c72e9  jmp     loc_1800C6FD2
0x1800c72ee  cmp     [rbp+3Fh+var_B0.x], eax
0x1800c72f1  jz      loc_1800C7083
0x1800c72f7  cmp     cs:pfnSetVirtualResolution, rax
0x1800c72fe  lea     rdi, [rbx+28h]
0x1800c7302  mov     qword ptr [rbp+3Fh+var_B0.x], rax
0x1800c7306  jnz     short loc_1800C7354
0x1800c7308  mov     rcx, [rdi]; hdc
0x1800c730b  lea     rdx, [rbp+3Fh+var_B0]; lppt
0x1800c730f  call    cs:__imp_GetCurrentPositionEx
0x1800c7316  nop     dword ptr [rax+rax+00h]
0x1800c731b  test    eax, eax
0x1800c731d  jz      short loc_1800C7354
0x1800c731f  lea     r8, [rbx+6Ch]
0x1800c7323  mov     edx, r15d
0x1800c7326  lea     rcx, [rbp+3Fh+var_B0]
0x1800c732a  call    bXformWorkhorse
0x1800c732f  mov     [rsp+130h+var_DC], eax
0x1800c7333  test    eax, eax
0x1800c7335  jz      loc_1800C78E9
0x1800c733b  mov     r8d, [rbp+3Fh+var_B0.y]; y
0x1800c733f  xor     r9d, r9d; lppt
0x1800c7342  mov     edx, [rbp+3Fh+var_B0.x]; x
0x1800c7345  mov     rcx, [rdi]; hdc
0x1800c7348  call    cs:__imp_MoveToEx
0x1800c734f  nop     dword ptr [rax+rax+00h]
0x1800c7354  cmp     [rbp+3Fh+var_94], 53h ; 'S'
0x1800c7358  mov     r9d, r12d; options
0x1800c735b  mov     rax, [rbp+3Fh+lpDx]
0x1800c735f  mov     r8d, [rsp+130h+y]; y
0x1800c7364  mov     edx, [rsp+130h+x]; x
0x1800c7368  mov     rcx, [rdi]; hdc
0x1800c736b  mov     [rsp+130h+lpUsedDefaultChar], rax; lpDx
0x1800c7370  mov     rax, [rbp+3Fh+lpWideCharStr]
0x1800c7374  mov     dword ptr [rsp+130h+lpDefaultChar], r13d; c
0x1800c7379  mov     qword ptr [rsp+130h+cbMultiByte], rax; lpString
0x1800c737e  mov     rax, [rbp+3Fh+lprect]
0x1800c7382  mov     [rsp+130h+lpMultiByteStr], rax; lprect
0x1800c7387  jnz     loc_1800C786B
0x1800c738d  call    cs:__imp_ExtTextOutA
0x1800c7394  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
