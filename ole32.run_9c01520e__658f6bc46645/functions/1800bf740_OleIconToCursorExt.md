# OleIconToCursorExt

- ea: `0x1800bf740`
- end: `0x1800bfbe8`
- name: `OleIconToCursorExt`
- size: `1192`
- prototype: `HICON__ *__fastcall(HINSTANCE__ *hinstExe, HICON__ *hIcon)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800bc080`
- `0x1800bc0e8`
- `0x1800bf740`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x1800bf9a4`
- `KERNELBASE!GlobalAlloc` at `0x1800bf9a4`
- `KERNELBASE!GlobalFree` at `0x1800bfbaf`
- `KERNELBASE!GlobalFree` at `0x1800bfbaf`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800bf7e1`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800bf7e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x1800bf76f`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x1800bf76f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x1800bfad8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x1800bfad8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800bfac4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800bfb9b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800bfac4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800bfb9b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800bf9bf`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800bfae7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800bf9bf`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800bfae7`
- `GDI32!GetDIBits` at `0x1800bfa26`
- `GDI32!GetDIBits` at `0x1800bfa26`
- `GDI32!SetDIBits` at `0x1800bfa8a`
- `GDI32!SetDIBits` at `0x1800bfa8a`
- `GDI32!CreateCompatibleBitmap` at `0x1800bf835`
- `GDI32!CreateCompatibleBitmap` at `0x1800bf835`
- `GDI32!DeleteObject` at `0x1800bfa35`
- `GDI32!DeleteObject` at `0x1800bfb71`
- `GDI32!DeleteObject` at `0x1800bfa35`
- `GDI32!DeleteObject` at `0x1800bfb71`
- `GDI32!CreateBitmap` at `0x1800bfa57`
- `GDI32!CreateBitmap` at `0x1800bfa57`
- `GDI32!GetObjectW` at `0x1800bfaa6`
- `GDI32!GetObjectW` at `0x1800bfaa6`
- `GDI32!SetBitmapBits` at `0x1800bf8d6`
- `GDI32!SetBitmapBits` at `0x1800bf8d6`
- `GDI32!GetBitmapBits` at `0x1800bfafe`
- `GDI32!GetBitmapBits` at `0x1800bfafe`
- `USER32!CreateCursor` at `0x1800bfb46`
- `USER32!CreateCursor` at `0x1800bfb46`
- `USER32!CopyIcon` at `0x1800bfbc8`
- `USER32!CopyIcon` at `0x1800bfbc8`
- `USER32!CopyImage` at `0x1800bf7c9`
- `USER32!CopyImage` at `0x1800bf7c9`
- `USER32!ReleaseDC` at `0x1800bfb87`
- `USER32!ReleaseDC` at `0x1800bfb87`
- `USER32!GetDC` at `0x1800bf80e`
- `USER32!GetDC` at `0x1800bf80e`
- `USER32!GetSystemMetrics` at `0x1800bf79c`
- `USER32!GetSystemMetrics` at `0x1800bf7ad`
- `USER32!GetSystemMetrics` at `0x1800bf79c`
- `USER32!GetSystemMetrics` at `0x1800bf7ad`

## pseudocode

```c
HICON__ *__fastcall OleIconToCursorExt(HINSTANCE hinstExe, HICON hIcon)
{
  HICON__ *lpbmi; // r14
  void *v4; // r15
  __int16 Version; // ax
  int SystemMetrics; // ebx
  int v7; // eax
  HICON__ *v8; // rax
  HICON__ *v9; // rsi
  HDC__ *DC; // rax
  HDC__ *v11; // r13
  HBITMAP__ *CompatibleBitmap; // r12
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > *v13; // rax
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > *v14; // rax
  DWORD m_int; // edx
  int v16; // r8d
  int v17; // ebx
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > *v18; // rax
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > *v19; // rax
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > *v20; // rax
  SIZE_T v21; // rcx
  HGLOBAL v22; // rax
  char *v23; // rbx
  HBITMAP Bitmap; // rax
  unsigned int v25; // ebx
  HCURSOR Cursor; // rbx
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > v27; // [rsp+40h] [rbp-98h] BYREF
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > v28; // [rsp+44h] [rbp-94h] BYREF
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > v29; // [rsp+48h] [rbp-90h] BYREF
  HBITMAP__ *hbmTmp; // [rsp+50h] [rbp-88h]
  HDC__ *hdcScr; // [rsp+58h] [rbp-80h]
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > v32; // [rsp+78h] [rbp-60h] BYREF
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > v33; // [rsp+7Ch] [rbp-5Ch] BYREF
  tagBITMAP bmp; // [rsp+80h] [rbp-58h] BYREF
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > tmp; // [rsp+F0h] [rbp+18h] BYREF
  SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException> > result; // [rsp+F8h] [rbp+20h] BYREF

  lpbmi = 0;
  memset(&bmp, 0, sizeof(bmp));
  v4 = 0;
  Version = GetVersion();
  if ( (((unsigned __int8)Version << 8) | (unsigned int)HIBYTE(Version)) < 0x334 )
    return CopyIcon(hIcon);
  SystemMetrics = GetSystemMetrics(14);
  v7 = GetSystemMetrics(13);
  v8 = (HICON__ *)CopyImage(hIcon, 2u, v7, SystemMetrics, 0);
  if ( !v8 )
  {
    v8 = (HICON__ *)LockResource(hIcon);
    v9 = v8;
    if ( v8 )
    {
      if ( *((_BYTE *)v8 + 20) != 1 || *((_BYTE *)v8 + 21) != 1 )
      {
        DC = GetDC(0);
        v11 = DC;
        hdcScr = DC;
        if ( !DC )
          return 0;
        CompatibleBitmap = CreateCompatibleBitmap(DC, *((_DWORD *)v9 + 2), *((_DWORD *)v9 + 3));
        hbmTmp = CompatibleBitmap;
        if ( CompatibleBitmap )
        {
          try
          {
            tmp.m_int = *((_DWORD *)v9 + 2);
            v13 = SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<long>(
                    &tmp,
                    &result,
                    *((unsigned __int8 *)v9 + 21));
            tmp.m_int = (int)(SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<long>(
                                v13,
                                &v27,
                                15)->m_int
                            & 0xFFFFFFF0) >> 3;
            v14 = SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<long>(
                    &tmp,
                    &v28,
                    *((_DWORD *)v9 + 3));
            m_int = SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<long>(
                      v14,
                      &v29,
                      *((unsigned __int8 *)v9 + 20))->m_int;
          }
          catch ( ... )
          {
            v4 = 0;
            lpbmi = 0;
            v11 = hdcScr;
            CompatibleBitmap = hbmTmp;
            goto LABEL_15;
          }
          SetBitmapBits(CompatibleBitmap, m_int, (char *)v9 + *((_DWORD *)v9 + 3) * *((_DWORD *)v9 + 4) + 24);
          v16 = *((unsigned __int8 *)v9 + 20) * *((unsigned __int8 *)v9 + 21);
          tmp.m_int = v16;
          if ( (unsigned __int16)v16 <= 8u )
          {
            v17 = 4 * (1LL << v16);
          }
          else
          {
            LOWORD(v16) = 24;
            tmp.m_int = 24;
            v17 = 0;
          }
          try
          {
            result.m_int = *((_DWORD *)v9 + 2);
            v18 = SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<long>(
                    &result,
                    &v29,
                    (unsigned __int16)v16);
            result.m_int = (SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<long>(
                              v18,
                              &v28,
                              31)->m_int >> 3)
                         & 0xFFFFFFFC;
            v19 = SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<long>(
                    &result,
                    &v27,
                    *((_DWORD *)v9 + 3));
            v20 = SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<long>(
                    v19,
                    &v32,
                    40);
            v21 = SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<long>(
                    v20,
                    &v33,
                    v17)->m_int;
          }
          catch ( ... )
          {
            v4 = 0;
            lpbmi = 0;
            v11 = hdcScr;
            CompatibleBitmap = hbmTmp;
            goto LABEL_15;
          }
          v22 = GlobalAlloc(2u, v21);
          v4 = v22;
          if ( !v22 )
          {
LABEL_15:
            Cursor = 0;
            goto $Error_13;
          }
          lpbmi = (HICON__ *)GlobalLock(v22);
          *(_DWORD *)lpbmi = 40;
          lpbmi[1] = v9[2];
          lpbmi[2] = v9[3];
          *((_WORD *)lpbmi + 6) = 1;
          *((_WORD *)lpbmi + 7) = tmp.m_int;
          *((_QWORD *)lpbmi + 2) = 0;
          *((_QWORD *)lpbmi + 3) = 0;
          *((_QWORD *)lpbmi + 4) = 0;
          v23 = (char *)lpbmi + v17 + 40;
          GetDIBits(v11, CompatibleBitmap, 0, *((_DWORD *)v9 + 3), v23, (LPBITMAPINFO)lpbmi, 0);
          DeleteObject(CompatibleBitmap);
          Bitmap = CreateBitmap(*((_DWORD *)v9 + 2), *((_DWORD *)v9 + 3), 1u, 1u, 0);
          CompatibleBitmap = Bitmap;
          if ( Bitmap )
          {
            SetDIBits(v11, Bitmap, 0, *((_DWORD *)v9 + 3), v23, (const BITMAPINFO *)lpbmi, 0);
            GetObjectW(CompatibleBitmap, 32, &bmp);
            v25 = bmp.bmHeight * bmp.bmWidthBytes;
            GlobalUnlock(v4);
            GlobalReAlloc(v4, v25, 0);
            lpbmi = (HICON__ *)GlobalLock(v4);
            GetBitmapBits(CompatibleBitmap, v25, lpbmi);
            Cursor = CreateCursor(
                       hinstExe,
                       *((_DWORD *)v9 + 2) / 2,
                       *((_DWORD *)v9 + 3) / 2,
                       *((_DWORD *)v9 + 2),
                       *((_DWORD *)v9 + 3),
                       v9 + 6,
                       lpbmi);
$Error_13:
            DeleteObject(CompatibleBitmap);
LABEL_18:
            ReleaseDC(0, v11);
            if ( lpbmi )
              GlobalUnlock(v4);
            if ( v4 )
              GlobalFree(v4);
            return Cursor;
          }
        }
        Cursor = 0;
        goto LABEL_18;
      }
      return CopyIcon(hIcon);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800bf740  mov     rax, rsp
0x1800bf743  mov     [rax+8], hinstExe
0x1800bf747  push    rbx
0x1800bf748  push    rsi
0x1800bf749  push    rdi
0x1800bf74a  push    r12
0x1800bf74c  push    r13
0x1800bf74e  push    r14
0x1800bf750  push    r15
0x1800bf752  sub     rsp, 0A0h
0x1800bf759  mov     r12, hIcon
0x1800bf75c  xor     edi, edi
0x1800bf75e  mov     r14d, edi
0x1800bf761  xorps   xmm0, xmm0
0x1800bf764  movups  xmmword ptr [rax-58h], xmm0
0x1800bf768  movups  xmmword ptr [rax-48h], xmm0
0x1800bf76c  mov     r15d, edi
0x1800bf76f  call    cs:__imp_GetVersion
0x1800bf776  nop     dword ptr [rax+rax+00h]
0x1800bf77b  mov     r8d, eax
0x1800bf77e  shr     eax, 8
0x1800bf781  movzx   ecx, al
0x1800bf784  movzx   eax, r8b
0x1800bf788  shl     eax, 8
0x1800bf78b  or      ecx, eax
0x1800bf78d  cmp     ecx, 334h
0x1800bf793  jb      $ValidCursor
0x1800bf799  lea     ecx, [rdi+0Eh]; nIndex
0x1800bf79c  call    cs:__imp_GetSystemMetrics
0x1800bf7a3  nop     dword ptr [rax+rax+00h]
0x1800bf7a8  mov     ebx, eax
0x1800bf7aa  lea     ecx, [rdi+0Dh]; nIndex
0x1800bf7ad  call    cs:__imp_GetSystemMetrics
0x1800bf7b4  nop     dword ptr [rax+rax+00h]
0x1800bf7b9  mov     [rsp+0D8h+flags], edi; flags
0x1800bf7bd  mov     r9d, ebx; cy
0x1800bf7c0  mov     r8d, eax; cx
0x1800bf7c3  lea     edx, [rdi+2]; type
0x1800bf7c6  mov     hinstExe, r12; h
0x1800bf7c9  call    cs:__imp_CopyImage
0x1800bf7d0  nop     dword ptr [rax+rax+00h]
0x1800bf7d5  test    rax, rax
0x1800bf7d8  jnz     loc_1800BFBD4
0x1800bf7de  mov     hinstExe, r12; hResData
0x1800bf7e1  call    cs:__imp_LockResource
0x1800bf7e8  nop     dword ptr [rax+rax+00h]
0x1800bf7ed  mov     rsi, rax
0x1800bf7f0  test    rax, rax
0x1800bf7f3  jz      loc_1800BFBD4
0x1800bf7f9  mov     eax, 1
0x1800bf7fe  cmp     [rsi+14h], al
0x1800bf801  jnz     short loc_1800BF80C
0x1800bf803  cmp     [rsi+15h], al
0x1800bf806  jz      $ValidCursor
0x1800bf80c  xor     ecx, ecx; hWnd
0x1800bf80e  call    cs:__imp_GetDC
0x1800bf815  nop     dword ptr [rax+rax+00h]
0x1800bf81a  mov     r13, rax
0x1800bf81d  mov     [rsp+0D8h+hdcScr], rax
0x1800bf822  test    rax, rax
0x1800bf825  jz      loc_1800BFBBD
0x1800bf82b  mov     r8d, [rsi+0Ch]; cy
0x1800bf82f  mov     edx, [rsi+8]; cx
0x1800bf832  mov     hinstExe, rax; hdc
0x1800bf835  call    cs:__imp_CreateCompatibleBitmap
0x1800bf83c  nop     dword ptr [rax+rax+00h]
0x1800bf841  mov     r12, rax
0x1800bf844  mov     [rsp+0D8h+hbmTmp], rax
0x1800bf849  test    rax, rax
0x1800bf84c  jz      loc_1800BFB7F
0x1800bf852  mov     eax, [rsi+8]
0x1800bf855  mov     [rsp+0D8h+tmp.m_int], eax
0x1800bf85c  movzx   r8d, byte ptr [rsi+15h]; rhs
0x1800bf861  lea     hIcon, [rsp+0D8h+result]; result
0x1800bf869  lea     hinstExe, [rsp+0D8h+tmp]; this
0x1800bf871  call    ??$?DJ@?$SafeInt@JV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@J@Z; SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<long>(long)
0x1800bf876  mov     r8d, 0Fh; rhs
0x1800bf87c  lea     hIcon, [rsp+0D8h+var_98]; result
0x1800bf881  mov     hinstExe, rax; this
0x1800bf884  call    ??$?HJ@?$SafeInt@JV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@J@Z; SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<long>(long)
0x1800bf889  mov     eax, [rax]
0x1800bf88b  and     eax, 0FFFFFFF0h
0x1800bf88e  sar     eax, 3
0x1800bf891  mov     [rsp+0D8h+tmp.m_int], eax
0x1800bf898  mov     r8d, [rsi+0Ch]; rhs
0x1800bf89c  lea     hIcon, [rsp+0D8h+var_94]; result
0x1800bf8a1  lea     hinstExe, [rsp+0D8h+tmp]; this
0x1800bf8a9  call    ??$?DJ@?$SafeInt@JV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@J@Z; SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<long>(long)
0x1800bf8ae  movzx   r8d, byte ptr [rsi+14h]; rhs
0x1800bf8b3  lea     hIcon, [rsp+0D8h+var_90]; result
0x1800bf8b8  mov     hinstExe, rax; this
0x1800bf8bb  call    ??$?DJ@?$SafeInt@JV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@J@Z; SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<long>(long)
0x1800bf8c0  mov     edx, [rax]; cb
0x1800bf8c2  mov     eax, [rsi+10h]
0x1800bf8c5  imul    eax, [rsi+0Ch]
0x1800bf8c9  movsxd  r8, eax
0x1800bf8cc  add     r8, 18h
0x1800bf8d0  add     r8, rsi; pvBits
0x1800bf8d3  mov     hinstExe, r12; hbm
0x1800bf8d6  call    cs:__imp_SetBitmapBits
0x1800bf8dd  nop     dword ptr [rax+rax+00h]
0x1800bf8e2  movzx   r8d, byte ptr [rsi+15h]
0x1800bf8e7  movzx   eax, byte ptr [rsi+14h]
0x1800bf8eb  imul    r8d, eax
0x1800bf8ef  mov     [rsp+0D8h+tmp.m_int], r8d
0x1800bf8f7  cmp     r8w, 8
0x1800bf8fc  jbe     short loc_1800BF910
0x1800bf8fe  mov     r8d, 18h
0x1800bf904  mov     [rsp+0D8h+tmp.m_int], r8d
0x1800bf90c  mov     ebx, edi
0x1800bf90e  jmp     short loc_1800BF91E
0x1800bf910  mov     cl, r8b
0x1800bf913  mov     ebx, 1
0x1800bf918  shl     rbx, cl
0x1800bf91b  shl     ebx, 2
0x1800bf91e  mov     eax, [rsi+8]
0x1800bf921  mov     [rsp+0D8h+result.m_int], eax
0x1800bf928  movzx   r8d, r8w; rhs
0x1800bf92c  lea     hIcon, [rsp+0D8h+var_90]; result
0x1800bf931  lea     hinstExe, [rsp+0D8h+result]; this
0x1800bf939  call    ??$?DJ@?$SafeInt@JV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@J@Z; SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<long>(long)
0x1800bf93e  mov     r8d, 1Fh; rhs
0x1800bf944  lea     hIcon, [rsp+0D8h+var_94]; result
0x1800bf949  mov     hinstExe, rax; this
0x1800bf94c  call    ??$?HJ@?$SafeInt@JV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@J@Z; SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<long>(long)
0x1800bf951  mov     eax, [rax]
0x1800bf953  sar     eax, 3
0x1800bf956  and     eax, 0FFFFFFFCh
0x1800bf959  mov     [rsp+0D8h+result.m_int], eax
0x1800bf960  mov     r8d, [rsi+0Ch]; rhs
0x1800bf964  lea     hIcon, [rsp+0D8h+var_98]; result
0x1800bf969  lea     hinstExe, [rsp+0D8h+result]; this
0x1800bf971  call    ??$?DJ@?$SafeInt@JV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@J@Z; SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<long>(long)
0x1800bf976  mov     r8d, 28h ; '('; rhs
0x1800bf97c  lea     hIcon, [rsp+0D8h+var_60]; result
0x1800bf981  mov     hinstExe, rax; this
0x1800bf984  call    ??$?HJ@?$SafeInt@JV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@J@Z; SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<long>(long)
0x1800bf989  mov     r8d, ebx; rhs
0x1800bf98c  lea     hIcon, [rsp+0D8h+var_5C]; result
0x1800bf991  mov     hinstExe, rax; this
0x1800bf994  call    ??$?HJ@?$SafeInt@JV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@J@Z; SafeInt<long,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<long>(long)
0x1800bf999  movsxd  hinstExe, dword ptr [rax]
0x1800bf99c  mov     hIcon, hinstExe; dwBytes
0x1800bf99f  mov     ecx, 2; uFlags
0x1800bf9a4  call    cs:__imp_GlobalAlloc
0x1800bf9ab  nop     dword ptr [rax+rax+00h]
0x1800bf9b0  mov     r15, rax
0x1800bf9b3  test    rax, rax
0x1800bf9b6  jz      loc_1800BFB6B
0x1800bf9bc  mov     hinstExe, rax; hMem
0x1800bf9bf  call    cs:__imp_GlobalLock
0x1800bf9c6  nop     dword ptr [rax+rax+00h]
0x1800bf9cb  mov     r14, rax
0x1800bf9ce  mov     dword ptr [rax], 28h ; '('
0x1800bf9d4  mov     eax, [rsi+8]
0x1800bf9d7  mov     [r14+4], eax
0x1800bf9db  mov     eax, [rsi+0Ch]
0x1800bf9de  mov     [r14+8], eax
0x1800bf9e2  mov     word ptr [r14+0Ch], 1
0x1800bf9e9  mov     eax, [rsp+0D8h+tmp.m_int]
0x1800bf9f0  mov     [r14+0Eh], ax
0x1800bf9f5  mov     [r14+10h], rdi
0x1800bf9f9  mov     [r14+18h], rdi
0x1800bf9fd  mov     [r14+20h], rdi
0x1800bfa01  movsxd  rax, ebx
0x1800bfa04  lea     rbx, [r14+28h]
0x1800bfa08  add     rbx, rax
0x1800bfa0b  mov     [rsp+0D8h+usage], edi; usage
0x1800bfa0f  mov     [rsp+0D8h+lpbmi], r14; lpbmi
0x1800bfa14  mov     qword ptr [rsp+0D8h+flags], rbx; lpvBits
0x1800bfa19  mov     r9d, [rsi+0Ch]; cLines
0x1800bfa1d  xor     r8d, r8d; start
0x1800bfa20  mov     hIcon, r12; hbm
0x1800bfa23  mov     hinstExe, r13; hdc
0x1800bfa26  call    cs:__imp_GetDIBits
0x1800bfa2d  nop     dword ptr [rax+rax+00h]
0x1800bfa32  mov     hinstExe, r12; ho
0x1800bfa35  call    cs:__imp_DeleteObject
0x1800bfa3c  nop     dword ptr [rax+rax+00h]
0x1800bfa41  mov     qword ptr [rsp+0D8h+flags], rdi; lpBits
0x1800bfa46  mov     eax, 1
0x1800bfa4b  mov     r9d, eax; nBitCount
0x1800bfa4e  mov     r8d, eax; nPlanes
0x1800bfa51  mov     edx, [rsi+0Ch]; nHeight
0x1800bfa54  mov     ecx, [rsi+8]; nWidth
0x1800bfa57  call    cs:__imp_CreateBitmap
0x1800bfa5e  nop     dword ptr [rax+rax+00h]
0x1800bfa63  mov     r12, rax
0x1800bfa66  test    rax, rax
0x1800bfa69  jz      loc_1800BFB7F
0x1800bfa6f  mov     [rsp+0D8h+usage], edi; ColorUse
0x1800bfa73  mov     [rsp+0D8h+lpbmi], r14; lpbmi
0x1800bfa78  mov     qword ptr [rsp+0D8h+flags], rbx; lpBits
0x1800bfa7d  mov     r9d, [rsi+0Ch]; cLines
0x1800bfa81  xor     r8d, r8d; start
0x1800bfa84  mov     hIcon, rax; hbm
0x1800bfa87  mov     hinstExe, r13; hdc
0x1800bfa8a  call    cs:__imp_SetDIBits
0x1800bfa91  nop     dword ptr [rax+rax+00h]
0x1800bfa96  lea     r8, [rsp+0D8h+bmp]; pv
0x1800bfa9e  mov     edx, 20h ; ' '; c
0x1800bfaa3  mov     hinstExe, r12; h
0x1800bfaa6  call    cs:__imp_GetObjectW
0x1800bfaad  nop     dword ptr [rax+rax+00h]
0x1800bfab2  mov     ebx, [rsp+0D8h+bmp.bmWidthBytes]
0x1800bfab9  imul    ebx, [rsp+0D8h+bmp.bmHeight]
0x1800bfac1  mov     hinstExe, r15; hMem
0x1800bfac4  call    cs:__imp_GlobalUnlock
0x1800bfacb  nop     dword ptr [rax+rax+00h]
0x1800bfad0  mov     edx, ebx; dwBytes
0x1800bfad2  xor     r8d, r8d; uFlags
0x1800bfad5  mov     hinstExe, r15; hMem
0x1800bfad8  call    cs:__imp_GlobalReAlloc
0x1800bfadf  nop     dword ptr [rax+rax+00h]
0x1800bfae4  mov     hinstExe, r15; hMem
0x1800bfae7  call    cs:__imp_GlobalLock
0x1800bfaee  nop     dword ptr [rax+rax+00h]
0x1800bfaf3  mov     r14, rax
0x1800bfaf6  mov     r8, rax; lpvBits
0x1800bfaf9  mov     edx, ebx; cb
0x1800bfafb  mov     hinstExe, r12; hbit
0x1800bfafe  call    cs:__imp_GetBitmapBits
0x1800bfb05  nop     dword ptr [rax+rax+00h]
0x1800bfb0a  mov     r10d, [rsi+0Ch]
0x1800bfb0e  mov     r9d, [rsi+8]; nWidth
0x1800bfb12  lea     hinstExe, [rsi+18h]
0x1800bfb16  mov     eax, r10d
0x1800bfb19  cdq
0x1800bfb1a  mov     r11d, 2
0x1800bfb20  idiv    r11d
0x1800bfb23  mov     r8d, eax; yHotSpot
0x1800bfb26  mov     eax, r9d
0x1800bfb29  cdq
0x1800bfb2a  idiv    r11d
0x1800bfb2d  mov     edx, eax; xHotSpot
0x1800bfb2f  mov     qword ptr [rsp+0D8h+usage], r14; pvXORPlane
0x1800bfb34  mov     [rsp+0D8h+lpbmi], hinstExe; pvANDPlane
0x1800bfb39  mov     [rsp+0D8h+flags], r10d; nHeight
0x1800bfb3e  mov     hinstExe, [rsp+0D8h+hInst]; hInst
0x1800bfb46  call    cs:__imp_CreateCursor
0x1800bfb4d  nop     dword ptr [rax+rax+00h]
0x1800bfb52  mov     rbx, rax
0x1800bfb55  jmp     short $Error_13
0x1800bfb57  jmp     short $+2
0x1800bfb59  xor     edi, edi
0x1800bfb5b  mov     r15d, edi
0x1800bfb5e  mov     r14d, edi
0x1800bfb61  mov     r13, [rsp+0D8h+hdcScr]
0x1800bfb66  mov     r12, [rsp+0D8h+hbmTmp]
0x1800bfb6b  mov     rbx, rdi
0x1800bfb6e  mov     hinstExe, r12; ho
0x1800bfb71  call    cs:__imp_DeleteObject
0x1800bfb78  nop     dword ptr [rax+rax+00h]
0x1800bfb7d  jmp     short loc_1800BFB82
0x1800bfb7f  mov     rbx, rdi
0x1800bfb82  mov     hIcon, r13; hDC
0x1800bfb85  xor     ecx, ecx; hWnd
0x1800bfb87  call    cs:__imp_ReleaseDC
0x1800bfb8e  nop     dword ptr [rax+rax+00h]
0x1800bfb93  test    r14, r14
0x1800bfb96  jz      short loc_1800BFBA7
0x1800bfb98  mov     hinstExe, r15; hMem
0x1800bfb9b  call    cs:__imp_GlobalUnlock
0x1800bfba2  nop     dword ptr [rax+rax+00h]
0x1800bfba7  test    r15, r15
0x1800bfbaa  jz      short loc_1800BFBC0
0x1800bfbac  mov     hinstExe, r15; hMem
0x1800bfbaf  call    cs:__imp_GlobalFree
0x1800bfbb6  nop     dword ptr [rax+rax+00h]
0x1800bfbbb  jmp     short loc_1800BFBC0
0x1800bfbbd  mov     rbx, rdi
0x1800bfbc0  mov     rax, rbx
0x1800bfbc3  jmp     short loc_1800BFBD4
0x1800bfbc5  mov     hinstExe, r12; hIcon
0x1800bfbc8  call    cs:__imp_CopyIcon
0x1800bfbcf  nop     dword ptr [rax+rax+00h]
0x1800bfbd4  add     rsp, 0A0h
0x1800bfbdb  pop     r15
0x1800bfbdd  pop     r14
0x1800bfbdf  pop     r13
0x1800bfbe1  pop     r12
0x1800bfbe3  pop     rdi
0x1800bfbe4  pop     rsi
0x1800bfbe5  pop     rbx
0x1800bfbe6  retn
```
