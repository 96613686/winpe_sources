# DoExtTextOut

- ea: `0x1800b0428`
- end: `0x1800b0e26`
- name: `DoExtTextOut`
- size: `2558`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, LPCWCH lpWideCharStr, int cchWideChar, INT *, int iMode, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800b02e0`
- `0x1801406e0`

## callees

- `0x1800afb24`
- `0x1800b0128`
- `0x1800b01e8`
- `0x1800b0428`
- `0x1800b0e2c`
- `0x1800b0e94`
- `0x1800b0ff0`
- `0x1800b1ee8`
- `0x1800b2080`
- `0x1800b2190`
- `0x1800b2910`
- `0x1800d4f9c`
- `0x1800e9380`
- `0x180146d74`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByteEx` at `0x1800b0c44`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByteEx` at `0x1800b0c44`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b0588`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b076c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b0941`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b0bb9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b0588`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b076c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b0941`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b0bb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b0664`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b08fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b0e15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b0664`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b08fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b0e15`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800b056c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800b0750`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800b0bf8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800b056c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800b0750`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800b0bf8`
- `GDI32!GetTextCharset` at `0x1800b0539`
- `GDI32!GetTextCharset` at `0x1800b0539`
- `GDI32!GetCurrentPositionEx` at `0x1800b06d2`
- `GDI32!GetCurrentPositionEx` at `0x1800b0859`
- `GDI32!GetCurrentPositionEx` at `0x1800b0dc5`
- `GDI32!GetCurrentPositionEx` at `0x1800b06d2`
- `GDI32!GetCurrentPositionEx` at `0x1800b0859`
- `GDI32!GetCurrentPositionEx` at `0x1800b0dc5`
- `GDI32!ExtTextOutA` at `0x1800b08d8`
- `GDI32!ExtTextOutA` at `0x1800b09d1`
- `GDI32!ExtTextOutA` at `0x1800b08d8`
- `GDI32!ExtTextOutA` at `0x1800b09d1`
- `GDI32!MoveToEx` at `0x1800b0891`
- `GDI32!MoveToEx` at `0x1800b0e01`
- `GDI32!MoveToEx` at `0x1800b0891`
- `GDI32!MoveToEx` at `0x1800b0e01`
- `GDI32!GetTextAlign` at `0x1800b04bb`
- `GDI32!GetTextAlign` at `0x1800b04bb`
- `GDI32!ExtTextOutW` at `0x1800b09df`
- `GDI32!ExtTextOutW` at `0x1800b0d93`
- `GDI32!ExtTextOutW` at `0x1800b09df`
- `GDI32!ExtTextOutW` at `0x1800b0d93`
- `GDI32!SetGraphicsMode` at `0x1800b0983`
- `GDI32!SetGraphicsMode` at `0x1800b09f8`
- `GDI32!SetGraphicsMode` at `0x1800b0983`
- `GDI32!SetGraphicsMode` at `0x1800b09f8`

## pseudocode

```c
__int64 __fastcall DoExtTextOut(
        __int64 a1,
        int a2,
        int a3,
        UINT a4,
        RECT *a5,
        const CHAR *lpWideCharStr,
        unsigned int cchWideChar,
        INT *a8,
        int iMode,
        int a10)
{
  __int64 v10; // rbx
  const WCHAR *v11; // rsi
  __int64 v12; // r12
  LONG c; // r13d
  HDC *v14; // rdi
  bool v15; // zf
  LONG v16; // eax
  const WCHAR *v17; // r8
  UINT v18; // edi
  unsigned int cbMultiByte; // esi
  CHAR *lpMultiByteStr; // rax
  int v21; // esi
  unsigned int v22; // edi
  HDC v24; // rcx
  int v25; // edi
  INT *v26; // rdx
  LONG *v27; // rcx
  __int64 v28; // r8
  int v29; // eax
  unsigned __int16 v30; // di
  HDC v31; // rcx
  _WORD *v32; // rdx
  __int64 v33; // r9
  _WORD *v34; // r8
  __int16 v35; // ax
  __int64 v36; // rdi
  HDC v37; // rcx
  BOOL v38; // eax
  unsigned int v39; // ebx
  unsigned __int16 v40; // di
  unsigned int v41; // r14d
  unsigned int v42; // esi
  LONG v43; // eax
  unsigned int v44; // edi
  __int64 v45; // r8
  __int64 v46; // r8
  __int64 v47; // rdx
  WCHAR v48; // cx
  unsigned __int64 v49; // rcx
  CHAR *v50; // rax
  INT *v51; // rcx
  __int64 v52; // rdi
  INT *v53; // r14
  int v54; // edx
  int v55; // eax
  int v56; // esi
  __int64 v57; // rcx
  __int64 v58; // r14
  LONG v59; // edi
  unsigned __int16 *v60; // rsi
  unsigned __int16 v61; // [rsp+50h] [rbp-91h]
  int v62; // [rsp+54h] [rbp-8Dh]
  LONG y; // [rsp+5Ch] [rbp-85h]
  LONG x; // [rsp+60h] [rbp-81h]
  int v66; // [rsp+64h] [rbp-7Dh]
  unsigned __int16 TextAlign; // [rsp+68h] [rbp-79h]
  const WCHAR *lpString; // [rsp+70h] [rbp-71h]
  INT *lpDx; // [rsp+78h] [rbp-69h]
  WCHAR *hMem; // [rsp+80h] [rbp-61h]
  UINT CodePage; // [rsp+88h] [rbp-59h]
  int v72; // [rsp+8Ch] [rbp-55h]
  __int64 v73; // [rsp+90h] [rbp-51h] BYREF
  RECT *lprect; // [rsp+98h] [rbp-49h]
  LONG v75; // [rsp+A0h] [rbp-41h] BYREF
  LONG v76; // [rsp+A4h] [rbp-3Dh]
  HLOCAL v77; // [rsp+A8h] [rbp-39h]
  __int64 v78; // [rsp+B0h] [rbp-31h]
  int v79[4]; // [rsp+B8h] [rbp-29h] BYREF
  struct tagPOINT pt; // [rsp+C8h] [rbp-19h] BYREF
  __int64 v81; // [rsp+D0h] [rbp-11h]

  v73 = 0;
  v77 = 0;
  v10 = a1;
  v11 = (const WCHAR *)lpWideCharStr;
  v12 = 0;
  c = cchWideChar;
  v14 = (HDC *)(a1 + 40);
  v61 = a4;
  v66 = 0;
  v15 = (*(_BYTE *)(a1 + 4) & 8) == 0;
  v78 = a1;
  y = a3;
  x = a2;
  lprect = a5;
  lpString = (const WCHAR *)lpWideCharStr;
  lpDx = a8;
  v79[0] = a2;
  v79[1] = a3;
  hMem = 0;
  v72 = 0;
  if ( v15 )
  {
    TextAlign = GetTextAlign(*v14);
    if ( (TextAlign & 1) == 0 )
    {
      v16 = y;
      goto LABEL_4;
    }
    v24 = *v14;
    pt = 0;
    if ( !GetCurrentPositionEx(v24, &pt) )
      goto LABEL_10;
    if ( pfnSetVirtualResolution || (unsigned int)bXformWorkhorse(&pt, 1, v10 + 108) )
    {
      if ( !(unsigned int)bValidateMetaFileCP(v10, (unsigned int)pt.x, (unsigned int)pt.y) )
        goto LABEL_10;
      x = pt.x;
      v16 = pt.y;
      y = pt.y;
LABEL_4:
      v75 = x;
      v76 = v16;
      if ( (unsigned int)bXformWorkhorse(&v75, 1, v10 + 228) )
      {
        if ( (v61 & 6) == 0 )
          goto LABEL_6;
        v15 = (*(_BYTE *)(v10 + 4) & 4) == 0;
        *(RECT *)v79 = *lprect;
        if ( v15 )
        {
          if ( !(unsigned int)bXformWorkhorse(v79, 2, v10 + 228) )
            goto LABEL_10;
          LOWORD(v73) = v79[0];
          WORD1(v73) = v79[1];
          WORD2(v73) = v79[2];
          HIWORD(v73) = v79[3];
LABEL_6:
          v62 = a10;
          if ( a10 == 84 )
          {
            v18 = GetCodePage(*(_QWORD *)(v10 + 40));
            CodePage = v18;
            if ( GetTextCharset(*(HDC *)(v10 + 40)) == 2 )
            {
              v36 = cchWideChar;
              v77 = LocalAlloc(0, 2LL * cchWideChar);
              v17 = (const WCHAR *)v77;
              if ( !v77 )
                goto LABEL_10;
              if ( cchWideChar )
              {
                v47 = 0;
                do
                {
                  v48 = v11[v47];
                  if ( (unsigned __int16)(v48 - 32) <= 0xDFu )
                    v48 -= 4096;
                  v17[v47++] = v48;
                  --v36;
                }
                while ( v36 );
              }
              v18 = CodePage;
              v11 = v17;
              lpString = v17;
            }
            cbMultiByte = WideCharToMultiByte(v18, 0, v11, cchWideChar, 0, 0, 0, 0);
            if ( cbMultiByte == cchWideChar )
            {
              lpMultiByteStr = (CHAR *)LocalAlloc(0, cchWideChar);
              hMem = (WCHAR *)lpMultiByteStr;
              v11 = (const WCHAR *)lpMultiByteStr;
              *(_QWORD *)v79 = lpMultiByteStr;
              if ( !lpMultiByteStr )
                goto LABEL_10;
              WideCharToMultiByte(v18, 0, lpString, cchWideChar, lpMultiByteStr, cchWideChar, 0, 0);
            }
            else
            {
              if ( cbMultiByte + 3 < cbMultiByte )
                goto LABEL_10;
              v49 = ((cbMultiByte + 3) & 0xFFFFFFFC) * ((a4 & 0x2000) != 0 ? 9LL : 5LL);
              if ( v49 > 0xFFFFFFFF )
                goto LABEL_10;
              v50 = (CHAR *)LocalAlloc(0x40u, (unsigned int)v49);
              hMem = (WCHAR *)v50;
              if ( !v50 )
                goto LABEL_10;
              v62 = 83;
              WideCharToMultiByte(v18, 0, lpString, cchWideChar, v50, cbMultiByte, 0, 0);
              c = cbMultiByte;
              v51 = a8;
              lpString = hMem;
              *(_QWORD *)v79 = hMem;
              pt.x = cbMultiByte;
              if ( a8 )
              {
                v52 = 0;
                v53 = (INT *)((char *)hMem + ((cbMultiByte + 3) & 0xFFFFFFFC));
                if ( cbMultiByte )
                {
                  do
                  {
                    v53[v52] = v51[v12];
                    if ( IsDBCSLeadByteEx(CodePage, *((_BYTE *)hMem + v52)) )
                    {
                      v52 = (unsigned int)(v52 + 1);
                      v53[v52] = 0;
                    }
                    v51 = a8;
                    v52 = (unsigned int)(v52 + 1);
                    v12 = (unsigned int)(v12 + 1);
                  }
                  while ( (unsigned int)v52 < cbMultiByte );
                  v10 = v78;
                  c = pt.x;
                }
                v11 = *(const WCHAR **)v79;
                lpDx = v53;
              }
              else
              {
                v11 = hMem;
              }
            }
            hMem = (WCHAR *)v11;
          }
          else
          {
            *(_QWORD *)v79 = v11;
          }
          v25 = c + 1;
          v12 = (__int64)LocalAlloc(0, 8LL * (unsigned int)(c + 1));
          if ( !v12 )
          {
LABEL_47:
            v21 = v62;
LABEL_11:
            if ( (a4 & 4) != 0 && (v61 & 4) == 0 )
              DoRestoreDC(v10, 0xFFFFFFFFLL, v17);
            v22 = v72;
            if ( !v72 || (TextAlign & 1) == 0 )
              goto LABEL_14;
            pt = 0;
            if ( !pfnSetVirtualResolution && GetCurrentPositionEx(*(HDC *)(v10 + 40), &pt) )
            {
              v22 = bXformWorkhorse(&pt, 1, v10 + 108);
              if ( !v22 )
              {
LABEL_14:
                if ( hMem )
                  LocalFree(hMem);
                if ( v12 )
                  LocalFree((HLOCAL)v12);
                if ( v77 )
                  LocalFree(v77);
                return v22;
              }
              MoveToEx(*(HDC *)(v10 + 40), pt.x, pt.y, 0);
            }
            v31 = *(HDC *)(v10 + 40);
            if ( v21 == 83 )
              ExtTextOutA(v31, x, y, a4, lprect, (LPCSTR)lpString, c, lpDx);
            else
              ExtTextOutW(v31, x, y, a4, lprect, lpString, c, lpDx);
            v15 = pfnSetVirtualResolution == 0;
            *(_DWORD *)(v10 + 360) = 0x7FFFFFFF;
            *(_DWORD *)(v10 + 364) = 0x7FFFFFFF;
            if ( v15 )
            {
              if ( GetCurrentPositionEx(*(HDC *)(v10 + 40), &pt) )
              {
                v22 = bXformWorkhorse(&pt, 1, v10 + 84);
                if ( v22 )
                  MoveToEx(*(HDC *)(v10 + 40), pt.x, pt.y, 0);
              }
            }
            goto LABEL_14;
          }
          *(_DWORD *)v12 = x;
          *(_DWORD *)(v12 + 4) = y;
          if ( v25 > 1LL )
          {
            v26 = lpDx;
            v27 = (LONG *)(v12 + 12);
            v28 = v25 - 1LL;
            do
            {
              v29 = *v26++ + *(v27 - 3);
              *(v27 - 1) = v29;
              *v27 = y;
              v27 += 2;
              --v28;
            }
            while ( v28 );
          }
          if ( (*(_BYTE *)(v10 + 4) & 4) != 0 )
          {
            v30 = TextAlign;
            v54 = 0;
            v55 = TextAlign & 6;
            if ( v55 == 2 )
            {
              v56 = 1;
              v66 = 1;
              v54 = *(_DWORD *)v12 - *(_DWORD *)(v12 + 8LL * (unsigned int)c);
            }
            else if ( v55 == 6 )
            {
              v56 = 1;
              v66 = 1;
              v54 = (*(_DWORD *)v12 - *(_DWORD *)(v12 + 8LL * (unsigned int)c)) / 2;
            }
            else
            {
              v56 = 0;
            }
            if ( c + 1 > 0 )
            {
              v57 = 0;
              do
                *(_DWORD *)(v12 + 8 * v57++) += v54;
              while ( v57 < c + 1 );
            }
            if ( !(unsigned int)bXformWorkhorse(v12, (unsigned int)(c + 1), v10 + 228) )
              goto LABEL_46;
            if ( v56 && !(unsigned int)bW16Emit1(v10, 302, TextAlign & 0xFFF9) )
              goto LABEL_115;
            v58 = *(_QWORD *)v79;
            v59 = 0;
            v60 = (unsigned __int16 *)v12;
            while ( v59 < c )
            {
              if ( !(unsigned int)bEmitWin16ExtTextOut(v10, *v60, v60[2], v61, 0, v58 + v59, 1, 0) )
                goto LABEL_45;
              ++v59;
              v60 += 4;
            }
          }
          else
          {
            if ( !(unsigned int)bXformWorkhorse(v12, (unsigned int)(c + 1), v10 + 228) )
              goto LABEL_47;
            if ( c > 0 )
            {
              v32 = (_WORD *)v12;
              v33 = (unsigned int)c;
              v34 = (_WORD *)v12;
              do
              {
                v35 = v34[4] - *v34;
                v34 += 4;
                *v32++ = v35;
                --v33;
              }
              while ( v33 );
            }
            if ( !(unsigned int)bEmitWin16ExtTextOut(
                                  v10,
                                  (unsigned __int16)v75,
                                  (unsigned __int16)v76,
                                  v61,
                                  (__int64)&v73,
                                  (__int64)v11,
                                  c,
                                  v12) )
              goto LABEL_47;
          }
          v72 = 1;
LABEL_45:
          v30 = TextAlign;
LABEL_46:
          if ( !v66 )
            goto LABEL_47;
LABEL_115:
          bW16Emit1(v10, 302, v30);
          goto LABEL_47;
        }
        v40 = v61;
        if ( (v61 & 2) != 0 )
        {
          v41 = *(_DWORD *)(v10 + 436);
          v42 = *(_DWORD *)(v10 + 440);
          if ( (unsigned int)DoSelectObject(v10, 2147483656LL, v17) )
          {
            v43 = *(_DWORD *)(v10 + 428);
            v44 = *(_DWORD *)(v10 + 412) - 21;
            pt.x = 0;
            v81 = 0;
            pt.y = v43;
            if ( (unsigned int)DoCreateBrushIndirect(v10, v44, &pt) )
            {
              if ( (unsigned int)DoSelectObject(v10, v44, v45) )
              {
                if ( (unsigned int)bConicCommon(
                                     v10,
                                     (unsigned int)v79[0],
                                     (unsigned int)v79[1],
                                     (unsigned int)v79[2],
                                     v79[3],
                                     0,
                                     0,
                                     0,
                                     0,
                                     43) )
                  v61 &= ~2u;
                DoSelectObject(v10, v42, v46);
              }
              DoDeleteObject(v10, v44);
            }
            DoSelectObject(v10, v41, v45);
            v40 = v61;
          }
          if ( (v40 & 2) != 0 )
            goto LABEL_10;
          v11 = (const WCHAR *)lpWideCharStr;
        }
        if ( (v40 & 4) == 0 )
          goto LABEL_6;
        if ( (unsigned int)DoSaveDC(v10) )
        {
          v61 = v40 & 0xFFFB;
          if ( (unsigned int)DoClipRect(v10, v79[0], v79[1], v79[2], v79[3], 30) )
            goto LABEL_6;
        }
      }
LABEL_10:
      v21 = a10;
      goto LABEL_11;
    }
    return 0;
  }
  if ( iMode != 2 )
  {
    SetGraphicsMode(*v14, iMode);
    a3 = y;
    a2 = x;
  }
  if ( !pfnSetVirtualResolution )
  {
    if ( !(unsigned int)bXformWorkhorse(v79, 1, v10 + 84) )
      return 0;
    a3 = v79[1];
    a2 = v79[0];
  }
  v37 = *v14;
  if ( a10 == 83 )
    v38 = ExtTextOutA(v37, a2, a3, a4, lprect, lpWideCharStr, cchWideChar, a8);
  else
    v38 = ExtTextOutW(v37, a2, a3, a4, lprect, (LPCWSTR)lpWideCharStr, cchWideChar, a8);
  v39 = v38;
  if ( iMode != 2 )
    SetGraphicsMode(*v14, 2);
  return v39;
}

```

## disassembly

```asm
0x1800b0428  push    rbp
0x1800b042a  push    rbx
0x1800b042b  push    rsi
0x1800b042c  push    rdi
0x1800b042d  push    r12
0x1800b042f  push    r13
0x1800b0431  push    r14
0x1800b0433  push    r15
0x1800b0435  lea     rbp, [rsp-7]
0x1800b043a  sub     rsp, 0E8h
0x1800b0441  mov     rax, cs:__security_cookie
0x1800b0448  xor     rax, rsp
0x1800b044b  mov     [rbp+3Fh+var_48], rax
0x1800b044f  and     [rbp+3Fh+var_90], 0
0x1800b0454  mov     eax, r9d
0x1800b0457  and     [rbp+3Fh+var_78], 0
0x1800b045c  mov     rbx, rcx
0x1800b045f  mov     rsi, [rbp+3Fh+lpWideCharStr]
0x1800b0463  xor     r12d, r12d
0x1800b0466  mov     r15, [rbp+3Fh+arg_38]
0x1800b046d  mov     r13d, [rbp+3Fh+cchWideChar]
0x1800b0471  mov     [rsp+120h+options], eax
0x1800b0475  lea     rdi, [rbx+28h]
0x1800b0479  mov     [rsp+120h+var_D0], ax
0x1800b047e  xor     eax, eax
0x1800b0480  and     [rbp+3Fh+var_BC], eax
0x1800b0483  test    byte ptr [rbx+4], 8
0x1800b0487  mov     [rbp+3Fh+var_70], rcx
0x1800b048b  mov     rcx, [rbp+3Fh+arg_20]
0x1800b048f  mov     [rsp+120h+y], r8d
0x1800b0494  mov     [rsp+120h+x], edx
0x1800b0498  mov     [rbp+3Fh+lprect], rcx
0x1800b049c  mov     [rbp+3Fh+lpString], rsi
0x1800b04a0  mov     [rbp+3Fh+var_A8], r15
0x1800b04a4  mov     [rbp+3Fh+var_68], edx
0x1800b04a7  mov     [rbp+3Fh+var_68+4], r8d
0x1800b04ab  mov     [rbp+3Fh+hMem], rax
0x1800b04af  mov     [rbp+3Fh+var_94], eax
0x1800b04b2  jnz     loc_1800B0621
0x1800b04b8  mov     rcx, [rdi]; hdc
0x1800b04bb  call    cs:__imp_GetTextAlign
0x1800b04c2  nop     dword ptr [rax+rax+00h]
0x1800b04c7  lea     r15d, [r12+1]
0x1800b04cc  mov     dword ptr [rbp+3Fh+var_B8], eax
0x1800b04cf  lea     r14d, [r12+2]
0x1800b04d4  test    r15b, al
0x1800b04d7  jnz     loc_1800B06C7
0x1800b04dd  mov     eax, [rsp+120h+y]
0x1800b04e1  mov     ecx, [rsp+120h+x]
0x1800b04e5  lea     rdi, [rbx+0E4h]
0x1800b04ec  mov     [rbp+3Fh+var_80], ecx
0x1800b04ef  mov     r8, rdi
0x1800b04f2  lea     rcx, [rbp+3Fh+var_80]
0x1800b04f6  mov     [rbp+3Fh+var_7C], eax
0x1800b04f9  mov     edx, r15d
0x1800b04fc  call    bXformWorkhorse
0x1800b0501  test    eax, eax
0x1800b0503  jz      loc_1800B05A8
0x1800b0509  test    byte ptr [rsp+120h+var_D0], 6
0x1800b050e  jnz     loc_1800B0675
0x1800b0514  mov     eax, [rbp+3Fh+arg_48]
0x1800b051a  mov     [rsp+120h+var_CC], eax
0x1800b051e  cmp     eax, 54h ; 'T'
0x1800b0521  jnz     loc_1800B0975
0x1800b0527  mov     rcx, [rbx+28h]
0x1800b052b  call    GetCodePage
0x1800b0530  mov     rcx, [rbx+28h]; hdc
0x1800b0534  mov     edi, eax
0x1800b0536  mov     [rbp+3Fh+CodePage], eax
0x1800b0539  call    cs:__imp_GetTextCharset
0x1800b0540  nop     dword ptr [rax+rax+00h]
0x1800b0545  cmp     eax, r14d
0x1800b0548  jz      loc_1800B0934
0x1800b054e  and     [rsp+120h+lpDx], r12
0x1800b0553  mov     r9d, r13d; cchWideChar
0x1800b0556  and     qword ptr [rsp+120h+c], r12
0x1800b055b  mov     r8, rsi; lpWideCharStr
0x1800b055e  and     [rsp+120h+cbMultiByte], r12d
0x1800b0563  xor     edx, edx; dwFlags
0x1800b0565  and     [rsp+120h+lpMultiByteStr], r12
0x1800b056a  mov     ecx, edi; CodePage
0x1800b056c  call    cs:__imp_WideCharToMultiByte
0x1800b0573  nop     dword ptr [rax+rax+00h]
0x1800b0578  mov     esi, eax
0x1800b057a  cmp     eax, r13d
0x1800b057d  jnz     loc_1800B0B73
0x1800b0583  mov     rdx, r13; uBytes
0x1800b0586  xor     ecx, ecx; uFlags
0x1800b0588  call    cs:__imp_LocalAlloc
0x1800b058f  nop     dword ptr [rax+rax+00h]
0x1800b0594  mov     [rbp+3Fh+hMem], rax
0x1800b0598  mov     rsi, rax
0x1800b059b  mov     qword ptr [rbp+3Fh+var_68], rax
0x1800b059f  test    rax, rax
0x1800b05a2  jnz     loc_1800B0731
0x1800b05a8  mov     esi, [rbp+3Fh+arg_48]
0x1800b05ae  test    byte ptr [rsp+120h+options], 4
0x1800b05b3  mov     r14d, 2
0x1800b05b9  movzx   eax, [rsp+120h+var_D0]
0x1800b05be  setnz   cl
0x1800b05c1  bt      ax, r14w
0x1800b05c6  setnb   al
0x1800b05c9  test    al, cl
0x1800b05cb  jnz     loc_1800B08E9
0x1800b05d1  mov     edi, [rbp+3Fh+var_94]
0x1800b05d4  xor     r14d, r14d
0x1800b05d7  test    edi, edi
0x1800b05d9  jnz     loc_1800B083A
0x1800b05df  mov     rax, [rbp+3Fh+hMem]
0x1800b05e3  test    rax, rax
0x1800b05e6  jnz     short loc_1800B0661
0x1800b05e8  test    r12, r12
0x1800b05eb  jnz     loc_1800B08F9
0x1800b05f1  mov     rax, [rbp+3Fh+var_78]
0x1800b05f5  test    rax, rax
0x1800b05f8  jnz     loc_1800B0E12
0x1800b05fe  mov     eax, edi
0x1800b0600  mov     rcx, [rbp+3Fh+var_48]
0x1800b0604  xor     rcx, rsp; StackCookie
0x1800b0607  call    __security_check_cookie
0x1800b060c  add     rsp, 0E8h
0x1800b0613  pop     r15
0x1800b0615  pop     r14
0x1800b0617  pop     r13
0x1800b0619  pop     r12
0x1800b061b  pop     rdi
0x1800b061c  pop     rsi
0x1800b061d  pop     rbx
0x1800b061e  pop     rbp
0x1800b061f  retn
0x1800b0621  mov     esi, [rbp+3Fh+iMode]
0x1800b0627  mov     r14d, 2
0x1800b062d  cmp     esi, r14d
0x1800b0630  jnz     loc_1800B097E
0x1800b0636  cmp     cs:pfnSetVirtualResolution, r12
0x1800b063d  jnz     loc_1800B09A4
0x1800b0643  lea     r8, [rbx+54h]
0x1800b0647  mov     edx, 1
0x1800b064c  lea     rcx, [rbp+3Fh+var_68]
0x1800b0650  call    bXformWorkhorse
0x1800b0655  test    eax, eax
0x1800b0657  jnz     loc_1800B099D
0x1800b065d  xor     eax, eax
0x1800b065f  jmp     short loc_1800B0600
0x1800b0661  mov     rcx, rax; hMem
0x1800b0664  call    cs:__imp_LocalFree
0x1800b066b  nop     dword ptr [rax+rax+00h]
0x1800b0670  jmp     loc_1800B05E8
0x1800b0675  test    byte ptr [rbx+4], 4
0x1800b0679  mov     rax, [rbp+3Fh+lprect]
0x1800b067d  movups  xmm0, xmmword ptr [rax]
0x1800b0680  movdqu  xmmword ptr [rbp+3Fh+var_68], xmm0
0x1800b0685  jnz     loc_1800B0A0B
0x1800b068b  mov     r8, rdi
0x1800b068e  lea     rcx, [rbp+3Fh+var_68]
0x1800b0692  mov     edx, r14d
0x1800b0695  call    bXformWorkhorse
0x1800b069a  test    eax, eax
0x1800b069c  jz      loc_1800B05A8
0x1800b06a2  movzx   eax, word ptr [rbp+3Fh+var_68]
0x1800b06a6  mov     word ptr [rbp+3Fh+var_90], ax
0x1800b06aa  movzx   eax, word ptr [rbp+3Fh+var_68+4]
0x1800b06ae  mov     word ptr [rbp+3Fh+var_90+2], ax
0x1800b06b2  movzx   eax, word ptr [rbp+3Fh+var_68+8]
0x1800b06b6  mov     word ptr [rbp+3Fh+var_90+4], ax
0x1800b06ba  movzx   eax, word ptr [rbp+3Fh+var_68+0Ch]
0x1800b06be  mov     word ptr [rbp+3Fh+var_90+6], ax
0x1800b06c2  jmp     loc_1800B0514
0x1800b06c7  mov     rcx, [rdi]; hdc
0x1800b06ca  lea     rdx, [rbp+3Fh+pt]; lppt
0x1800b06ce  and     qword ptr [rbp+3Fh+pt.x], r12
0x1800b06d2  call    cs:__imp_GetCurrentPositionEx
0x1800b06d9  nop     dword ptr [rax+rax+00h]
0x1800b06de  test    eax, eax
0x1800b06e0  jz      loc_1800B05A8
0x1800b06e6  cmp     cs:pfnSetVirtualResolution, r12
0x1800b06ed  jnz     short loc_1800B0707
0x1800b06ef  lea     r8, [rbx+6Ch]
0x1800b06f3  mov     edx, r15d
0x1800b06f6  lea     rcx, [rbp+3Fh+pt]
0x1800b06fa  call    bXformWorkhorse
0x1800b06ff  test    eax, eax
0x1800b0701  jz      loc_1800B065D
0x1800b0707  mov     r8d, [rbp+3Fh+pt.y]
0x1800b070b  mov     rcx, rbx
0x1800b070e  mov     edx, [rbp+3Fh+pt.x]
0x1800b0711  call    bValidateMetaFileCP
0x1800b0716  test    eax, eax
0x1800b0718  jz      loc_1800B05A8
0x1800b071e  mov     eax, [rbp+3Fh+pt.x]
0x1800b0721  mov     [rsp+120h+x], eax
0x1800b0725  mov     eax, [rbp+3Fh+pt.y]
0x1800b0728  mov     [rsp+120h+y], eax
0x1800b072c  jmp     loc_1800B04E1
0x1800b0731  and     [rsp+120h+lpDx], r12
0x1800b0736  mov     r9d, r13d; cchWideChar
0x1800b0739  and     qword ptr [rsp+120h+c], r12
0x1800b073e  xor     edx, edx; dwFlags
0x1800b0740  mov     r8, [rbp+3Fh+lpString]; lpWideCharStr
0x1800b0744  mov     ecx, edi; CodePage
0x1800b0746  mov     [rsp+120h+cbMultiByte], r13d; cbMultiByte
0x1800b074b  mov     [rsp+120h+lpMultiByteStr], rax; lpMultiByteStr
0x1800b0750  call    cs:__imp_WideCharToMultiByte
0x1800b0757  nop     dword ptr [rax+rax+00h]
0x1800b075c  mov     [rbp+3Fh+hMem], rsi
0x1800b0760  lea     edi, [r13+1]
0x1800b0764  xor     ecx, ecx; uFlags
0x1800b0766  mov     edx, edi
0x1800b0768  shl     rdx, 3; uBytes
0x1800b076c  call    cs:__imp_LocalAlloc
0x1800b0773  nop     dword ptr [rax+rax+00h]
0x1800b0778  mov     r12, rax
0x1800b077b  test    rax, rax
0x1800b077e  jz      loc_1800B0831
0x1800b0784  mov     eax, [rsp+120h+x]
0x1800b0788  mov     r9d, [rsp+120h+y]
0x1800b078d  movsxd  r8, edi
0x1800b0790  mov     [r12], eax
0x1800b0794  mov     [r12+4], r9d
0x1800b0799  cmp     r8, r15
0x1800b079c  jle     short loc_1800B07C2
0x1800b079e  mov     rdx, [rbp+3Fh+var_A8]
0x1800b07a2  lea     rcx, [r12+0Ch]
0x1800b07a7  dec     r8
0x1800b07aa  mov     eax, [rcx-0Ch]
0x1800b07ad  add     eax, [rdx]
0x1800b07af  lea     rdx, [rdx+4]
0x1800b07b3  mov     [rcx-4], eax
0x1800b07b6  mov     [rcx], r9d
0x1800b07b9  lea     rcx, [rcx+8]
0x1800b07bd  sub     r8, r15
0x1800b07c0  jnz     short loc_1800B07AA
0x1800b07c2  test    byte ptr [rbx+4], 4
0x1800b07c6  jnz     loc_1800B0C8A
0x1800b07cc  lea     r8, [rbx+0E4h]
0x1800b07d3  mov     rcx, r12
0x1800b07d6  lea     edx, [r13+1]
0x1800b07da  call    bXformWorkhorse
0x1800b07df  test    eax, eax
0x1800b07e1  jz      short loc_1800B0831
0x1800b07e3  test    r13d, r13d
0x1800b07e6  jg      loc_1800B090D
0x1800b07ec  movzx   r9d, [rsp+120h+var_D0]
0x1800b07f2  lea     rax, [rbp+3Fh+var_90]
0x1800b07f6  movzx   r8d, word ptr [rbp+3Fh+var_7C]
0x1800b07fb  mov     rcx, rbx
0x1800b07fe  movzx   edx, word ptr [rbp+3Fh+var_80]
0x1800b0802  mov     [rsp+120h+lpDx], r12
0x1800b0807  mov     word ptr [rsp+120h+c], r13w
0x1800b080d  mov     qword ptr [rsp+120h+cbMultiByte], rsi
0x1800b0812  mov     [rsp+120h+lpMultiByteStr], rax
0x1800b0817  call    bEmitWin16ExtTextOut
0x1800b081c  test    eax, eax
0x1800b081e  jz      short loc_1800B0831
0x1800b0820  mov     [rbp+3Fh+var_94], r15d
0x1800b0824  mov     edi, dword ptr [rbp+3Fh+var_B8]
0x1800b0827  cmp     [rbp+3Fh+var_BC], 0
0x1800b082b  jnz     loc_1800B0D7D
0x1800b0831  mov     esi, [rsp+120h+var_CC]
0x1800b0835  jmp     loc_1800B05AE
0x1800b083a  test    byte ptr [rbp+3Fh+var_B8], r15b
0x1800b083e  jz      loc_1800B05DF
0x1800b0844  cmp     cs:pfnSetVirtualResolution, r14
0x1800b084b  mov     qword ptr [rbp+3Fh+pt.x], r14
0x1800b084f  jnz     short loc_1800B089D
0x1800b0851  mov     rcx, [rbx+28h]; hdc
0x1800b0855  lea     rdx, [rbp+3Fh+pt]; lppt
0x1800b0859  call    cs:__imp_GetCurrentPositionEx
0x1800b0860  nop     dword ptr [rax+rax+00h]
0x1800b0865  test    eax, eax
0x1800b0867  jz      short loc_1800B089D
0x1800b0869  lea     r8, [rbx+6Ch]
0x1800b086d  mov     edx, r15d
0x1800b0870  lea     rcx, [rbp+3Fh+pt]
0x1800b0874  call    bXformWorkhorse
0x1800b0879  mov     edi, eax
0x1800b087b  test    eax, eax
0x1800b087d  jz      loc_1800B05DF
0x1800b0883  mov     r8d, [rbp+3Fh+pt.y]; y
0x1800b0887  xor     r9d, r9d; lppt
0x1800b088a  mov     edx, [rbp+3Fh+pt.x]; x
0x1800b088d  mov     rcx, [rbx+28h]; hdc
0x1800b0891  call    cs:__imp_MoveToEx
0x1800b0898  nop     dword ptr [rax+rax+00h]
0x1800b089d  mov     rax, [rbp+3Fh+var_A8]
0x1800b08a1  mov     rcx, [rbx+28h]; hdc
0x1800b08a5  mov     r9d, [rsp+120h+options]; options
0x1800b08aa  mov     r8d, [rsp+120h+y]; y
0x1800b08af  mov     edx, [rsp+120h+x]; x
0x1800b08b3  mov     [rsp+120h+lpDx], rax; lpDx
0x1800b08b8  mov     rax, [rbp+3Fh+lpString]
0x1800b08bc  mov     [rsp+120h+c], r13d; c
0x1800b08c1  mov     qword ptr [rsp+120h+cbMultiByte], rax; lpString
0x1800b08c6  mov     rax, [rbp+3Fh+lprect]
0x1800b08ca  mov     [rsp+120h+lpMultiByteStr], rax; lprect
0x1800b08cf  cmp     esi, 53h ; 'S'
0x1800b08d2  jnz     loc_1800B0D93
0x1800b08d8  call    cs:__imp_ExtTextOutA
0x1800b08df  nop     dword ptr [rax+rax+00h]
0x1800b08e4  jmp     loc_1800B0D9F
  ... truncated ...
```
