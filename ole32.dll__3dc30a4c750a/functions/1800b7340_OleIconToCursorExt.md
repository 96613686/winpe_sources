# OleIconToCursorExt

- ea: `0x1800b7340`
- end: `0x1800b774b`
- name: `OleIconToCursorExt`
- size: `1035`
- prototype: `HICON__ *__fastcall(HINSTANCE__ *hinstExe, HICON__ *hIcon)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800b39f0`
- `0x1800b3a58`
- `0x1800b7340`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x1800b7571`
- `KERNELBASE!GlobalAlloc` at `0x1800b7571`
- `KERNELBASE!GlobalFree` at `0x1800b771f`
- `KERNELBASE!GlobalFree` at `0x1800b771f`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800b73ca`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800b73ca`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x1800b7367`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x1800b7367`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x1800b7672`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x1800b7672`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800b7664`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800b7711`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800b7664`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800b7711`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800b7586`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800b767b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800b7586`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800b767b`
- `GDI32!SetDIBits` at `0x1800b7636`
- `GDI32!SetDIBits` at `0x1800b7636`
- `GDI32!CreateCompatibleBitmap` at `0x1800b741b`
- `GDI32!CreateCompatibleBitmap` at `0x1800b741b`
- `GDI32!GetDIBits` at `0x1800b75e4`
- `GDI32!GetDIBits` at `0x1800b75e4`
- `GDI32!DeleteObject` at `0x1800b75ed`
- `GDI32!DeleteObject` at `0x1800b76f3`
- `GDI32!DeleteObject` at `0x1800b75ed`
- `GDI32!DeleteObject` at `0x1800b76f3`
- `GDI32!CreateBitmap` at `0x1800b7609`
- `GDI32!CreateBitmap` at `0x1800b7609`
- `GDI32!GetObjectW` at `0x1800b764c`
- `GDI32!GetObjectW` at `0x1800b764c`
- `GDI32!SetBitmapBits` at `0x1800b74b5`
- `GDI32!SetBitmapBits` at `0x1800b74b5`
- `GDI32!GetBitmapBits` at `0x1800b768c`
- `GDI32!GetBitmapBits` at `0x1800b768c`
- `USER32!CopyIcon` at `0x1800b7732`
- `USER32!CopyIcon` at `0x1800b7732`
- `USER32!CopyImage` at `0x1800b73b8`
- `USER32!CopyImage` at `0x1800b73b8`
- `USER32!ReleaseDC` at `0x1800b7703`
- `USER32!ReleaseDC` at `0x1800b7703`
- `USER32!GetDC` at `0x1800b73f4`
- `USER32!GetDC` at `0x1800b73f4`
- `USER32!GetSystemMetrics` at `0x1800b7393`
- `USER32!GetSystemMetrics` at `0x1800b73a0`
- `USER32!GetSystemMetrics` at `0x1800b7393`
- `USER32!GetSystemMetrics` at `0x1800b73a0`
- `USER32!CreateCursor` at `0x1800b76ce`
- `USER32!CreateCursor` at `0x1800b76ce`

## pseudocode

```c
HICON__ *__fastcall OleIconToCursorExt(HINSTANCE hinstExe, HICON hIcon)
{
  __int16 Version; // ax
  int SystemMetrics; // ebx
  int v5; // eax
  HICON__ *v6; // rax
  HICON__ *v7; // rsi
  _BYTE *v8; // rbx
  HDC__ *DC; // rax
  HDC__ *v10; // r13
  HICON__ *lpbmi; // r14
  void *v12; // r15
  HBITMAP__ *CompatibleBitmap; // r12
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > *v14; // rax
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > *v15; // rax
  DWORD m_int; // edx
  unsigned __int16 v17; // ax
  int v18; // edx
  int v19; // ebx
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > *v20; // rax
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > *v21; // rax
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > *v22; // rax
  SIZE_T v23; // rcx
  HGLOBAL v24; // rax
  char *v25; // rbx
  HBITMAP Bitmap; // rax
  unsigned int v27; // ebx
  HCURSOR Cursor; // rbx
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > v29; // [rsp+40h] [rbp-98h] BYREF
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > v30; // [rsp+44h] [rbp-94h] BYREF
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > v31; // [rsp+48h] [rbp-90h] BYREF
  HBITMAP__ *hbmTmp; // [rsp+50h] [rbp-88h]
  HDC__ *hdcScr; // [rsp+58h] [rbp-80h]
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > v34; // [rsp+78h] [rbp-60h] BYREF
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > v35; // [rsp+7Ch] [rbp-5Ch] BYREF
  tagBITMAP bmp; // [rsp+80h] [rbp-58h] BYREF
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > tmp; // [rsp+F0h] [rbp+18h] BYREF
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > result; // [rsp+F8h] [rbp+20h] BYREF

  memset(&bmp, 0, sizeof(bmp));
  Version = GetVersion();
  if ( (((unsigned __int8)Version << 8) | (unsigned int)HIBYTE(Version)) < 0x334 )
    return CopyIcon(hIcon);
  SystemMetrics = GetSystemMetrics(14);
  v5 = GetSystemMetrics(13);
  v6 = (HICON__ *)CopyImage(hIcon, 2u, v5, SystemMetrics, 0);
  if ( !v6 )
  {
    v6 = (HICON__ *)LockResource(hIcon);
    v7 = v6;
    if ( v6 )
    {
      v8 = (char *)v6 + 21;
      if ( *((_BYTE *)v6 + 20) != 1 || *v8 != 1 )
      {
        DC = GetDC(0);
        v10 = DC;
        hdcScr = DC;
        if ( !DC )
          return 0;
        lpbmi = 0;
        v12 = 0;
        CompatibleBitmap = CreateCompatibleBitmap(DC, *((_DWORD *)v7 + 2), *((_DWORD *)v7 + 3));
        hbmTmp = CompatibleBitmap;
        if ( CompatibleBitmap )
        {
          try
          {
            tmp.m_int = *((_DWORD *)v7 + 2);
            v14 = SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<long>(
                    &tmp,
                    &result,
                    (unsigned __int8)*v8);
            tmp.m_int = (SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<long>(
                           v14,
                           &v29,
                           15)->m_int >> 3)
                      & 0xFFFFFFFE;
            v15 = SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<long>(
                    &tmp,
                    &v30,
                    *((_DWORD *)v7 + 3));
            m_int = SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<long>(
                      v15,
                      &v31,
                      *((unsigned __int8 *)v7 + 20))->m_int;
          }
          catch ( ... )
          {
            v12 = 0;
            lpbmi = 0;
            v10 = hdcScr;
            CompatibleBitmap = hbmTmp;
            goto LABEL_16;
          }
          SetBitmapBits(CompatibleBitmap, m_int, (char *)v7 + *((_DWORD *)v7 + 3) * *((_DWORD *)v7 + 4) + 24);
          v17 = *((unsigned __int8 *)v7 + 20) * (unsigned __int8)*v8;
          if ( v17 <= 8u )
          {
            v18 = v17;
            v19 = 4 * (1LL << v17);
          }
          else
          {
            v18 = 24;
            v19 = 0;
          }
          tmp.m_int = v18;
          try
          {
            result.m_int = *((_DWORD *)v7 + 2);
            v20 = SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<long>(
                    &result,
                    &v31,
                    (unsigned __int16)v18);
            result.m_int = (SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<long>(
                              v20,
                              &v30,
                              31)->m_int >> 3)
                         & 0xFFFFFFFC;
            v21 = SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<long>(
                    &result,
                    &v29,
                    *((_DWORD *)v7 + 3));
            v22 = SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<long>(
                    v21,
                    &v34,
                    40);
            v23 = SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<long>(
                    v22,
                    &v35,
                    v19)->m_int;
          }
          catch ( ... )
          {
            v12 = 0;
            lpbmi = 0;
            v10 = hdcScr;
            CompatibleBitmap = hbmTmp;
            goto LABEL_16;
          }
          v24 = GlobalAlloc(2u, v23);
          v12 = v24;
          if ( !v24 )
          {
LABEL_16:
            Cursor = 0;
            goto LABEL_17;
          }
          lpbmi = (HICON__ *)GlobalLock(v24);
          *(_DWORD *)lpbmi = 40;
          lpbmi[1] = v7[2];
          lpbmi[2] = v7[3];
          *((_WORD *)lpbmi + 6) = 1;
          *((_WORD *)lpbmi + 7) = tmp.m_int;
          *((_QWORD *)lpbmi + 2) = 0;
          *((_QWORD *)lpbmi + 3) = 0;
          *((_QWORD *)lpbmi + 4) = 0;
          v25 = (char *)lpbmi + v19 + 40;
          GetDIBits(v10, CompatibleBitmap, 0, *((_DWORD *)v7 + 3), v25, (LPBITMAPINFO)lpbmi, 0);
          DeleteObject(CompatibleBitmap);
          Bitmap = CreateBitmap(*((_DWORD *)v7 + 2), *((_DWORD *)v7 + 3), 1u, 1u, 0);
          CompatibleBitmap = Bitmap;
          if ( Bitmap )
          {
            SetDIBits(v10, Bitmap, 0, *((_DWORD *)v7 + 3), v25, (const BITMAPINFO *)lpbmi, 0);
            GetObjectW(CompatibleBitmap, 32, &bmp);
            v27 = bmp.bmHeight * bmp.bmWidthBytes;
            GlobalUnlock(v12);
            GlobalReAlloc(v12, v27, 0);
            lpbmi = (HICON__ *)GlobalLock(v12);
            GetBitmapBits(CompatibleBitmap, v27, lpbmi);
            Cursor = CreateCursor(
                       hinstExe,
                       *((_DWORD *)v7 + 2) / 2,
                       *((_DWORD *)v7 + 3) / 2,
                       *((_DWORD *)v7 + 2),
                       *((_DWORD *)v7 + 3),
                       v7 + 6,
                       lpbmi);
LABEL_17:
            DeleteObject(CompatibleBitmap);
LABEL_19:
            ReleaseDC(0, v10);
            if ( lpbmi )
              GlobalUnlock(v12);
            if ( v12 )
              GlobalFree(v12);
            return Cursor;
          }
        }
        Cursor = 0;
        goto LABEL_19;
      }
      return CopyIcon(hIcon);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800b7340  mov     rax, rsp
0x1800b7343  mov     [rax+8], hinstExe
0x1800b7347  push    rbx
0x1800b7348  push    rsi
0x1800b7349  push    rdi
0x1800b734a  push    r12
0x1800b734c  push    r13
0x1800b734e  push    r14
0x1800b7350  push    r15
0x1800b7352  sub     rsp, 0A0h
0x1800b7359  mov     r14, hIcon
0x1800b735c  xorps   xmm0, xmm0
0x1800b735f  movups  xmmword ptr [rax-58h], xmm0
0x1800b7363  movups  xmmword ptr [rax-48h], xmm0
0x1800b7367  call    cs:__imp_GetVersion
0x1800b736d  mov     r8d, eax
0x1800b7370  shr     r8d, 8
0x1800b7374  movzx   r9d, r8b
0x1800b7378  movzx   eax, al
0x1800b737b  shl     eax, 8
0x1800b737e  or      r9d, eax
0x1800b7381  cmp     r9d, 334h
0x1800b7388  jb      $ValidCursor
0x1800b738e  mov     ecx, 0Eh; nIndex
0x1800b7393  call    cs:__imp_GetSystemMetrics
0x1800b7399  mov     ebx, eax
0x1800b739b  mov     ecx, 0Dh; nIndex
0x1800b73a0  call    cs:__imp_GetSystemMetrics
0x1800b73a6  xor     edi, edi
0x1800b73a8  mov     [rsp+0D8h+flags], edi; flags
0x1800b73ac  mov     r9d, ebx; cy
0x1800b73af  mov     r8d, eax; cx
0x1800b73b2  lea     edx, [rdi+2]; type
0x1800b73b5  mov     hinstExe, r14; h
0x1800b73b8  call    cs:__imp_CopyImage
0x1800b73be  test    rax, rax
0x1800b73c1  jnz     loc_1800B7738
0x1800b73c7  mov     hinstExe, r14; hResData
0x1800b73ca  call    cs:__imp_LockResource
0x1800b73d0  mov     rsi, rax
0x1800b73d3  test    rax, rax
0x1800b73d6  jz      loc_1800B7738
0x1800b73dc  lea     rbx, [rax+15h]
0x1800b73e0  mov     eax, 1
0x1800b73e5  cmp     [rsi+14h], al
0x1800b73e8  jnz     short loc_1800B73F2
0x1800b73ea  cmp     [rbx], al
0x1800b73ec  jz      $ValidCursor
0x1800b73f2  xor     ecx, ecx; hWnd
0x1800b73f4  call    cs:__imp_GetDC
0x1800b73fa  mov     r13, rax
0x1800b73fd  mov     [rsp+0D8h+hdcScr], rax
0x1800b7402  test    rax, rax
0x1800b7405  jz      loc_1800B7727
0x1800b740b  mov     r14, rdi
0x1800b740e  mov     r15, rdi
0x1800b7411  mov     r8d, [rsi+0Ch]; cy
0x1800b7415  mov     edx, [rsi+8]; cx
0x1800b7418  mov     hinstExe, rax; hdc
0x1800b741b  call    cs:__imp_CreateCompatibleBitmap
0x1800b7421  mov     r12, rax
0x1800b7424  mov     [rsp+0D8h+hbmTmp], rax
0x1800b7429  test    rax, rax
0x1800b742c  jz      loc_1800B76FB
0x1800b7432  mov     ecx, [rsi+8]
0x1800b7435  mov     [rsp+0D8h+tmp.m_int], ecx
0x1800b743c  movzx   r8d, byte ptr [rbx]; rhs
0x1800b7440  lea     hIcon, [rsp+0D8h+result]; result
0x1800b7448  lea     hinstExe, [rsp+0D8h+tmp]; this
0x1800b7450  call    ??$?DJ@?$SafeInt@JV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@J@Z; SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<long>(long)
0x1800b7455  mov     r8d, 0Fh; rhs
0x1800b745b  lea     hIcon, [rsp+0D8h+var_98]; result
0x1800b7460  mov     hinstExe, rax; this
0x1800b7463  call    ??$?HJ@?$SafeInt@JV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@J@Z; SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<long>(long)
0x1800b7468  mov     eax, [rax]
0x1800b746a  sar     eax, 3
0x1800b746d  and     eax, 0FFFFFFFEh
0x1800b7470  mov     [rsp+0D8h+tmp.m_int], eax
0x1800b7477  mov     r8d, [rsi+0Ch]; rhs
0x1800b747b  lea     hIcon, [rsp+0D8h+var_94]; result
0x1800b7480  lea     hinstExe, [rsp+0D8h+tmp]; this
0x1800b7488  call    ??$?DJ@?$SafeInt@JV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@J@Z; SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<long>(long)
0x1800b748d  movzx   r8d, byte ptr [rsi+14h]; rhs
0x1800b7492  lea     hIcon, [rsp+0D8h+var_90]; result
0x1800b7497  mov     hinstExe, rax; this
0x1800b749a  call    ??$?DJ@?$SafeInt@JV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@J@Z; SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<long>(long)
0x1800b749f  mov     edx, [rax]; cb
0x1800b74a1  mov     eax, [rsi+10h]
0x1800b74a4  imul    eax, [rsi+0Ch]
0x1800b74a8  movsxd  r8, eax
0x1800b74ab  add     r8, 18h
0x1800b74af  add     r8, rsi; pvBits
0x1800b74b2  mov     hinstExe, r12; hbm
0x1800b74b5  call    cs:__imp_SetBitmapBits
0x1800b74bb  movzx   eax, byte ptr [rbx]
0x1800b74be  movzx   edx, byte ptr [rsi+14h]
0x1800b74c2  imul    eax, edx
0x1800b74c5  cmp     ax, 8
0x1800b74c9  jbe     short loc_1800B74D4
0x1800b74cb  mov     edx, 18h
0x1800b74d0  mov     ebx, edi
0x1800b74d2  jmp     short loc_1800B74E4
0x1800b74d4  movzx   edx, ax
0x1800b74d7  mov     ecx, eax
0x1800b74d9  mov     ebx, 1
0x1800b74de  shl     rbx, cl
0x1800b74e1  shl     ebx, 2
0x1800b74e4  mov     [rsp+0D8h+tmp.m_int], edx
0x1800b74eb  mov     eax, [rsi+8]
0x1800b74ee  mov     [rsp+0D8h+result.m_int], eax
0x1800b74f5  movzx   r8d, dx; rhs
0x1800b74f9  lea     hIcon, [rsp+0D8h+var_90]; result
0x1800b74fe  lea     hinstExe, [rsp+0D8h+result]; this
0x1800b7506  call    ??$?DJ@?$SafeInt@JV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@J@Z; SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<long>(long)
0x1800b750b  mov     r8d, 1Fh; rhs
0x1800b7511  lea     hIcon, [rsp+0D8h+var_94]; result
0x1800b7516  mov     hinstExe, rax; this
0x1800b7519  call    ??$?HJ@?$SafeInt@JV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@J@Z; SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<long>(long)
0x1800b751e  mov     eax, [rax]
0x1800b7520  sar     eax, 3
0x1800b7523  and     eax, 0FFFFFFFCh
0x1800b7526  mov     [rsp+0D8h+result.m_int], eax
0x1800b752d  mov     r8d, [rsi+0Ch]; rhs
0x1800b7531  lea     hIcon, [rsp+0D8h+var_98]; result
0x1800b7536  lea     hinstExe, [rsp+0D8h+result]; this
0x1800b753e  call    ??$?DJ@?$SafeInt@JV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@J@Z; SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<long>(long)
0x1800b7543  mov     r8d, 28h ; '('; rhs
0x1800b7549  lea     hIcon, [rsp+0D8h+var_60]; result
0x1800b754e  mov     hinstExe, rax; this
0x1800b7551  call    ??$?HJ@?$SafeInt@JV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@J@Z; SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<long>(long)
0x1800b7556  mov     r8d, ebx; rhs
0x1800b7559  lea     hIcon, [rsp+0D8h+var_5C]; result
0x1800b755e  mov     hinstExe, rax; this
0x1800b7561  call    ??$?HJ@?$SafeInt@JV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@J@Z; SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<long>(long)
0x1800b7566  movsxd  hinstExe, dword ptr [rax]
0x1800b7569  mov     hIcon, hinstExe; dwBytes
0x1800b756c  mov     ecx, 2; uFlags
0x1800b7571  call    cs:__imp_GlobalAlloc
0x1800b7577  mov     r15, rax
0x1800b757a  test    rax, rax
0x1800b757d  jz      loc_1800B76ED
0x1800b7583  mov     hinstExe, rax; hMem
0x1800b7586  call    cs:__imp_GlobalLock
0x1800b758c  mov     r14, rax
0x1800b758f  mov     dword ptr [rax], 28h ; '('
0x1800b7595  mov     ecx, [rsi+8]
0x1800b7598  mov     [rax+4], ecx
0x1800b759b  mov     ecx, [rsi+0Ch]
0x1800b759e  mov     [rax+8], ecx
0x1800b75a1  mov     word ptr [rax+0Ch], 1
0x1800b75a7  mov     eax, [rsp+0D8h+tmp.m_int]
0x1800b75ae  mov     [r14+0Eh], ax
0x1800b75b3  mov     [r14+10h], rdi
0x1800b75b7  mov     [r14+18h], rdi
0x1800b75bb  mov     [r14+20h], rdi
0x1800b75bf  movsxd  rax, ebx
0x1800b75c2  lea     rbx, [r14+28h]
0x1800b75c6  add     rbx, rax
0x1800b75c9  mov     [rsp+0D8h+usage], edi; usage
0x1800b75cd  mov     [rsp+0D8h+lpbmi], r14; lpbmi
0x1800b75d2  mov     qword ptr [rsp+0D8h+flags], rbx; lpvBits
0x1800b75d7  mov     r9d, [rsi+0Ch]; cLines
0x1800b75db  xor     r8d, r8d; start
0x1800b75de  mov     hIcon, r12; hbm
0x1800b75e1  mov     hinstExe, r13; hdc
0x1800b75e4  call    cs:__imp_GetDIBits
0x1800b75ea  mov     hinstExe, r12; ho
0x1800b75ed  call    cs:__imp_DeleteObject
0x1800b75f3  mov     qword ptr [rsp+0D8h+flags], rdi; lpBits
0x1800b75f8  mov     eax, 1
0x1800b75fd  mov     r9d, eax; nBitCount
0x1800b7600  mov     r8d, eax; nPlanes
0x1800b7603  mov     edx, [rsi+0Ch]; nHeight
0x1800b7606  mov     ecx, [rsi+8]; nWidth
0x1800b7609  call    cs:__imp_CreateBitmap
0x1800b760f  mov     r12, rax
0x1800b7612  test    rax, rax
0x1800b7615  jz      loc_1800B76FB
0x1800b761b  mov     [rsp+0D8h+usage], edi; ColorUse
0x1800b761f  mov     [rsp+0D8h+lpbmi], r14; lpbmi
0x1800b7624  mov     qword ptr [rsp+0D8h+flags], rbx; lpBits
0x1800b7629  mov     r9d, [rsi+0Ch]; cLines
0x1800b762d  xor     r8d, r8d; start
0x1800b7630  mov     hIcon, rax; hbm
0x1800b7633  mov     hinstExe, r13; hdc
0x1800b7636  call    cs:__imp_SetDIBits
0x1800b763c  lea     r8, [rsp+0D8h+bmp]; pv
0x1800b7644  mov     edx, 20h ; ' '; c
0x1800b7649  mov     hinstExe, r12; h
0x1800b764c  call    cs:__imp_GetObjectW
0x1800b7652  mov     ebx, [rsp+0D8h+bmp.bmWidthBytes]
0x1800b7659  imul    ebx, [rsp+0D8h+bmp.bmHeight]
0x1800b7661  mov     hinstExe, r15; hMem
0x1800b7664  call    cs:__imp_GlobalUnlock
0x1800b766a  mov     edx, ebx; dwBytes
0x1800b766c  xor     r8d, r8d; uFlags
0x1800b766f  mov     hinstExe, r15; hMem
0x1800b7672  call    cs:__imp_GlobalReAlloc
0x1800b7678  mov     hinstExe, r15; hMem
0x1800b767b  call    cs:__imp_GlobalLock
0x1800b7681  mov     r14, rax
0x1800b7684  mov     r8, rax; lpvBits
0x1800b7687  mov     edx, ebx; cb
0x1800b7689  mov     hinstExe, r12; hbit
0x1800b768c  call    cs:__imp_GetBitmapBits
0x1800b7692  mov     r10d, [rsi+0Ch]
0x1800b7696  mov     r9d, [rsi+8]; nWidth
0x1800b769a  lea     hinstExe, [rsi+18h]
0x1800b769e  mov     eax, r10d
0x1800b76a1  cdq
0x1800b76a2  mov     r11d, 2
0x1800b76a8  idiv    r11d
0x1800b76ab  mov     r8d, eax; yHotSpot
0x1800b76ae  mov     eax, r9d
0x1800b76b1  cdq
0x1800b76b2  idiv    r11d
0x1800b76b5  mov     edx, eax; xHotSpot
0x1800b76b7  mov     qword ptr [rsp+0D8h+usage], r14; pvXORPlane
0x1800b76bc  mov     [rsp+0D8h+lpbmi], hinstExe; pvANDPlane
0x1800b76c1  mov     [rsp+0D8h+flags], r10d; nHeight
0x1800b76c6  mov     hinstExe, [rsp+0D8h+hInst]; hInst
0x1800b76ce  call    cs:__imp_CreateCursor
0x1800b76d4  mov     rbx, rax
0x1800b76d7  jmp     short loc_1800B76F0
0x1800b76d9  jmp     short $+2
0x1800b76db  xor     edi, edi
0x1800b76dd  mov     r15d, edi
0x1800b76e0  mov     r14d, edi
0x1800b76e3  mov     r13, [rsp+0D8h+hdcScr]
0x1800b76e8  mov     r12, [rsp+0D8h+hbmTmp]
0x1800b76ed  mov     rbx, rdi
0x1800b76f0  mov     hinstExe, r12; ho
0x1800b76f3  call    cs:__imp_DeleteObject
0x1800b76f9  jmp     short loc_1800B76FE
0x1800b76fb  mov     rbx, rdi
0x1800b76fe  mov     hIcon, r13; hDC
0x1800b7701  xor     ecx, ecx; hWnd
0x1800b7703  call    cs:__imp_ReleaseDC
0x1800b7709  test    r14, r14
0x1800b770c  jz      short loc_1800B7717
0x1800b770e  mov     hinstExe, r15; hMem
0x1800b7711  call    cs:__imp_GlobalUnlock
0x1800b7717  test    r15, r15
0x1800b771a  jz      short loc_1800B772A
0x1800b771c  mov     hinstExe, r15; hMem
0x1800b771f  call    cs:__imp_GlobalFree
0x1800b7725  jmp     short loc_1800B772A
0x1800b7727  mov     rbx, rdi
0x1800b772a  mov     rax, rbx
0x1800b772d  jmp     short loc_1800B7738
0x1800b772f  mov     hinstExe, r14; hIcon
0x1800b7732  call    cs:__imp_CopyIcon
0x1800b7738  add     rsp, 0A0h
0x1800b773f  pop     r15
0x1800b7741  pop     r14
0x1800b7743  pop     r13
0x1800b7745  pop     r12
0x1800b7747  pop     rdi
0x1800b7748  pop     rsi
0x1800b7749  pop     rbx
0x1800b774a  retn
```
