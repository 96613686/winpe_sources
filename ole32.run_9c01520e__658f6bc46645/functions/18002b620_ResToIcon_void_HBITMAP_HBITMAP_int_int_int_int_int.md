# _ResToIcon(void *,HBITMAP__ * *,HBITMAP__ * *,int,int,int,int,int)

- ea: `0x18002b620`
- end: `0x18002be3c`
- name: `?_ResToIcon@@YAPEAUHICON__@@PEAXPEAPEAUHBITMAP__@@1HHHHH@Z`
- size: `2076`
- prototype: `HICON__ *__fastcall(void *hRes, HBITMAP__ **phbmpXor, HBITMAP__ **phbmpAnd, int xHot, int yHot, int xSize, int ySize, int fCursor)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a6d4`

## callees

- `0x1800205a0`
- `0x18002b620`
- `0x18002be44`
- `0x18002c6a0`
- `0x18002c6c8`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x18002ba5d`
- `KERNELBASE!GlobalAlloc` at `0x18002bc4d`
- `KERNELBASE!GlobalAlloc` at `0x18002ba5d`
- `KERNELBASE!GlobalAlloc` at `0x18002bc4d`
- `KERNELBASE!GlobalFree` at `0x18002bd26`
- `KERNELBASE!GlobalFree` at `0x18002bd5c`
- `KERNELBASE!GlobalFree` at `0x18002be05`
- `KERNELBASE!GlobalFree` at `0x18002bd26`
- `KERNELBASE!GlobalFree` at `0x18002bd5c`
- `KERNELBASE!GlobalFree` at `0x18002be05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002be18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002be18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b689`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b689`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18002b6ba`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18002b6ba`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002bd0f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002bd3f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002bdf6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002bd0f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002bd3f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002bdf6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002b6a8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002ba7b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002bc6b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002b6a8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002ba7b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002bc6b`
- `GDI32!CreateCompatibleBitmap` at `0x18002b94c`
- `GDI32!CreateCompatibleBitmap` at `0x18002b94c`
- `GDI32!StretchDIBits` at `0x18002ba00`
- `GDI32!StretchDIBits` at `0x18002bc08`
- `GDI32!StretchDIBits` at `0x18002ba00`
- `GDI32!StretchDIBits` at `0x18002bc08`
- `GDI32!DeleteObject` at `0x18002bd9a`
- `GDI32!DeleteObject` at `0x18002bdb1`
- `GDI32!DeleteObject` at `0x18002bd9a`
- `GDI32!DeleteObject` at `0x18002bdb1`
- `GDI32!CreateBitmap` at `0x18002b931`
- `GDI32!CreateBitmap` at `0x18002bac4`
- `GDI32!CreateBitmap` at `0x18002b931`
- `GDI32!CreateBitmap` at `0x18002bac4`
- `GDI32!GetObjectW` at `0x18002ba18`
- `GDI32!GetObjectW` at `0x18002bc22`
- `GDI32!GetObjectW` at `0x18002ba18`
- `GDI32!GetObjectW` at `0x18002bc22`
- `GDI32!GetBitmapBits` at `0x18002ba95`
- `GDI32!GetBitmapBits` at `0x18002bc88`
- `GDI32!GetBitmapBits` at `0x18002ba95`
- `GDI32!GetBitmapBits` at `0x18002bc88`
- `GDI32!SelectObject` at `0x18002b96b`
- `GDI32!SelectObject` at `0x18002bae7`
- `GDI32!SelectObject` at `0x18002b96b`
- `GDI32!SelectObject` at `0x18002bae7`
- `USER32!CreateCursor` at `0x18002bcc1`
- `USER32!CreateCursor` at `0x18002bcc1`
- `USER32!CreateIcon` at `0x18002bce0`
- `USER32!CreateIcon` at `0x18002bce0`
- `USER32!ReleaseDC` at `0x18002bde7`
- `USER32!ReleaseDC` at `0x18002bde7`
- `USER32!GetDC` at `0x18002b900`
- `USER32!GetDC` at `0x18002b900`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
HICON__ *__fastcall _ResToIcon(
        void *hRes,
        HBITMAP__ **phbmpXor,
        HDC__ **phbmpAnd,
        int xHot,
        int yHot,
        int xSize,
        int ySize,
        int fCursor)
{
  void *v8; // r12
  HBITMAP v9; // r14
  HDC__ *v10; // r13
  __int64 v11; // rsi
  unsigned int *lpbmi; // rdi
  SIZE_T v13; // r15
  unsigned int *v14; // rcx
  char *v15; // rax
  unsigned __int64 v16; // r9
  int v17; // eax
  unsigned int v18; // r10d
  __int16 v19; // cx
  __int64 v20; // r11
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rbx
  unsigned __int64 v23; // rdx
  unsigned int v24; // r10d
  __int64 v25; // r11
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // rcx
  int v28; // r8d
  unsigned int v29; // ecx
  unsigned __int64 v30; // rbx
  unsigned __int64 v31; // r9
  __int64 v32; // r11
  __int64 v33; // rax
  unsigned int *v34; // rcx
  char *v35; // r12
  HDC DC; // rax
  HBITMAP Bitmap; // rax
  HBITMAP__ *v38; // r15
  unsigned int *v39; // r13
  unsigned __int64 v40; // rdx
  unsigned __int64 v41; // rcx
  HGLOBAL v42; // rax
  HDC__ *v43; // rax
  HBITMAP__ *v44; // rax
  _DWORD *v45; // rcx
  unsigned __int64 v46; // rax
  unsigned __int64 v47; // rdx
  unsigned __int64 v48; // r9
  unsigned __int64 v49; // r10
  char *v50; // r8
  unsigned __int64 v51; // rdi
  HGLOBAL v52; // rax
  const void *v53; // rsi
  unsigned __int64 v54; // rbx
  HCURSOR Cursor; // rax
  bool v56; // zf
  HGLOBAL v57; // rbx
  unsigned __int64 v58; // rdi
  HGLOBAL v59; // rbx
  unsigned __int64 pResult; // [rsp+78h] [rbp-90h] BYREF
  HDC__ *hdcMem; // [rsp+80h] [rbp-88h]
  unsigned __int64 cbTotalSize; // [rsp+88h] [rbp-80h] BYREF
  HGLOBAL hMem; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int64 nSafe; // [rsp+98h] [rbp-70h]
  unsigned __int64 cbitsWidth; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int64 pullResult; // [rsp+A8h] [rbp-60h] BYREF
  HGLOBAL v68; // [rsp+B0h] [rbp-58h]
  _BYTE bmpXOR[72]; // [rsp+B8h] [rbp-50h] OVERLAPPED BYREF

  cbTotalSize = 0;
  v8 = hRes;
  nSafe = 0;
  hdcMem = 0;
  v9 = 0;
  v68 = 0;
  v10 = 0;
  memset(bmpXOR, 0, sizeof(bmpXOR));
  v11 = 0;
  EnterCriticalSection(&g_sys.m_critDCBusy);
  SysInfo::GetHdc(&g_sys, (HDC__ **)&cbTotalSize);
  lpbmi = (unsigned int *)GlobalLock(v8);
  v13 = GlobalSize(v8);
  v14 = lpbmi + 10;
  v15 = (char *)lpbmi + v13;
  cbitsWidth = (unsigned __int64)lpbmi + v13;
  if ( v13 < 0x28 )
    goto LABEL_8;
  if ( *lpbmi != 40 )
    goto LABEL_8;
  v16 = v15 - (char *)v14;
  pResult = v15 - (char *)v14;
  if ( (int)lpbmi[1] <= 0 )
    goto LABEL_8;
  v17 = lpbmi[2];
  if ( !v17 || v17 < 0 && lpbmi[4] && lpbmi[4] != 3 )
    goto LABEL_8;
  if ( *((_WORD *)lpbmi + 6) != 1 )
    goto LABEL_8;
  v18 = lpbmi[8];
  if ( v18 > 0x100 && *((_WORD *)lpbmi + 7) == 8 )
    goto LABEL_8;
  if ( lpbmi[4] == 3 && ((*((_WORD *)lpbmi + 7) - 16) & 0xFFEF) != 0 )
    goto LABEL_8;
  if ( !v18 )
  {
    v19 = *((_WORD *)lpbmi + 7);
    if ( (unsigned __int16)(v19 - 1) <= 7u )
      v18 = 1 << v19;
  }
  v20 = 12;
  if ( lpbmi[4] != 3 )
    v20 = 0;
  hMem = 0;
  v21 = 4LL * v18;
  v22 = v21;
  if ( !is_mul_ok(v18, 4u) )
    goto LABEL_8;
  v23 = v21 + v20;
  if ( v21 + v20 < v21 )
    goto LABEL_8;
  if ( v16 < v23 )
    goto LABEL_8;
  if ( SizeTSub(v16, v23, &pResult) < 0 )
    goto LABEL_8;
  v26 = *lpbmi;
  v27 = v22 + v26;
  if ( v22 + v26 < v26 )
    goto LABEL_8;
  if ( v27 + v25 < v27 )
    goto LABEL_8;
  if ( v13 < v27 + v25 )
    goto LABEL_8;
  v28 = (int)lpbmi[2] / 2;
  lpbmi[2] = v28;
  if ( !v28 )
    goto LABEL_8;
  v29 = lpbmi[4];
  v30 = 0;
  hMem = 0;
  if ( !v29 || v29 == 3 )
  {
    pullResult = 0;
    if ( v28 < 0 && v28 == 0x80000000 )
      goto LABEL_8;
    if ( ULongLongMult((int)lpbmi[1], *((unsigned __int16 *)lpbmi + 7), &pullResult) < 0 )
      goto LABEL_8;
    if ( pullResult + 31 < pullResult )
      goto LABEL_8;
    if ( ULongLongMult(v31, v32 & ((pullResult + 31) >> 3), (unsigned __int64 *)&hMem) < 0 )
      goto LABEL_8;
    v30 = (unsigned __int64)hMem;
    if ( pResult < (unsigned __int64)hMem )
      goto LABEL_8;
    v29 = lpbmi[4];
    if ( v29 )
    {
      if ( lpbmi[5] && (unsigned __int64)hMem > lpbmi[5] )
        goto LABEL_8;
    }
  }
  if ( pResult >= lpbmi[5] )
    goto LABEL_41;
  if ( v29 )
  {
LABEL_8:
    v11 = 0xFFFF;
    goto LABEL_99;
  }
  lpbmi[5] = 0;
LABEL_41:
  if ( lpbmi[8] )
  {
    v33 = lpbmi[8];
LABEL_46:
    v34 = &lpbmi[v33];
    goto LABEL_47;
  }
  if ( *((_WORD *)lpbmi + 7) != 24 )
  {
    v33 = v24;
    goto LABEL_46;
  }
  v34 = lpbmi;
LABEL_47:
  v35 = (char *)(v34 + 10);
  if ( v34 + 10 < lpbmi + 10 || v35 >= (char *)lpbmi + v13 )
  {
    v11 = 0xFFFF;
  }
  else
  {
    DC = GetDC(0);
    nSafe = (unsigned __int64)DC;
    if ( fCursor )
      Bitmap = CreateBitmap(xSize, ySize, 1u, 1u, 0);
    else
      Bitmap = CreateCompatibleBitmap(DC, xSize, ySize);
    v9 = Bitmap;
    if ( Bitmap )
    {
      v38 = (HBITMAP__ *)SelectObject((HDC)cbTotalSize, Bitmap);
      if ( lpbmi[4] && lpbmi[4] != 3 )
      {
        if ( !lpbmi[5] )
        {
          v11 = 0xFFFF;
          goto LABEL_92;
        }
        v30 = lpbmi[5];
      }
      v39 = (unsigned int *)&v35[v30];
      if ( &v35[v30] < v35 || v39 < lpbmi + 10 || (unsigned __int64)v39 > cbitsWidth )
      {
        v10 = hdcMem;
        v11 = 0xFFFF;
      }
      else
      {
        StretchDIBits(
          (HDC)cbTotalSize,
          0,
          0,
          xSize,
          ySize,
          0,
          0,
          lpbmi[1],
          lpbmi[2],
          v35,
          (const BITMAPINFO *)lpbmi,
          0,
          0xCC0020u);
        GetObjectW(v9, 32, &bmpXOR[8]);
        v40 = *(unsigned int *)&bmpXOR[16] * (unsigned __int64)*(unsigned int *)&bmpXOR[20];
        if ( v40 > 0xFFFFFFFF
          || (v41 = (unsigned int)v40 * (unsigned __int64)*(unsigned __int16 *)&bmpXOR[24], v41 > 0xFFFFFFFF) )
        {
          v10 = 0;
        }
        else
        {
          pullResult = (unsigned int)v41;
          v42 = GlobalAlloc(2u, (unsigned int)v41);
          hMem = v42;
          if ( v42 )
          {
            pResult = (unsigned __int64)GlobalLock(v42);
            GetBitmapBits(v9, pullResult, (LPVOID)pResult);
            _RestoreBitmap((HDC__ *)cbTotalSize, v38);
            v43 = (HDC__ *)CreateBitmap(xSize, ySize, 1u, 1u, 0);
            hdcMem = v43;
            if ( v43 )
            {
              v44 = (HBITMAP__ *)SelectObject((HDC)cbTotalSize, v43);
              v45 = lpbmi + 10;
              *((_WORD *)lpbmi + 7) = 1;
              lpbmi[8] = 0;
              v38 = v44;
              if ( (unsigned __int64)(lpbmi + 10) >= cbitsWidth || cbitsWidth - (unsigned __int64)v45 < 6 )
              {
                v11 = 0xFFFF;
              }
              else
              {
                *v45 = -16777216;
                *((_WORD *)lpbmi + 22) = -1;
                v46 = (int)lpbmi[1];
                if ( v46 + 31 < v46
                  || (v47 = (int)lpbmi[2],
                      cbitsWidth = ((v46 + 31) >> 3) & 0x1FFFFFFFFFFFFFFCLL,
                      ULongLongMult(cbitsWidth, v47, &cbitsWidth) < 0)
                  || (unsigned int *)((char *)v39 + cbitsWidth) < v39
                  || (v50 = (char *)v39 + cbitsWidth,
                      (unsigned __int64)v50 < v49
                   || (unsigned __int64)v50 > v48
                   || (StretchDIBits(
                         (HDC)cbTotalSize,
                         0,
                         0,
                         xSize,
                         ySize,
                         0,
                         0,
                         lpbmi[1],
                         lpbmi[2],
                         v39,
                         (const BITMAPINFO *)lpbmi,
                         0,
                         0xCC0020u),
                       GetObjectW(hdcMem, 32, &bmpXOR[40]),
                       v51 = *(unsigned int *)&bmpXOR[48] * (unsigned __int64)*(unsigned int *)&bmpXOR[52],
                       v51 > 0xFFFFFFFF)) )
                {
                  v11 = 0xFFFF;
                }
                else
                {
                  v52 = GlobalAlloc(2u, (unsigned int)v51);
                  v68 = v52;
                  if ( v52 )
                  {
                    *(_QWORD *)bmpXOR = GlobalLock(v52);
                    v53 = *(const void **)bmpXOR;
                    GetBitmapBits((HBITMAP)hdcMem, v51, *(LPVOID *)bmpXOR);
                    v54 = pResult;
                    if ( fCursor )
                      Cursor = CreateCursor(g_hinstDLL, xHot, yHot, xSize, ySize, v53, (const void *)pResult);
                    else
                      Cursor = CreateIcon(
                                 g_hinstDLL,
                                 xSize,
                                 ySize,
                                 bmpXOR[24],
                                 bmpXOR[26],
                                 (const BYTE *)v53,
                                 (const BYTE *)pResult);
                    v11 = (__int64)Cursor;
                    goto $Error_0;
                  }
                }
              }
            }
            v54 = pResult;
$Error_0:
            v56 = v54 == 0;
            v57 = hMem;
            if ( !v56 )
              GlobalUnlock(hMem);
            v58 = nSafe;
            GlobalFree(v57);
            v59 = v68;
            if ( *(_QWORD *)bmpXOR )
            {
              GlobalUnlock(v68);
              nSafe = v58;
            }
            v10 = hdcMem;
            if ( v59 )
              GlobalFree(v59);
            goto LABEL_92;
          }
          v10 = 0;
        }
      }
LABEL_92:
      if ( v38 )
        _RestoreBitmap((HDC__ *)cbTotalSize, v38);
      if ( !v11 )
      {
        DeleteObject(v9);
        v9 = 0;
        if ( v10 )
        {
          DeleteObject(v10);
          v10 = 0;
        }
      }
    }
  }
  v8 = hRes;
LABEL_99:
  *phbmpXor = v9;
  *phbmpAnd = v10;
  if ( nSafe )
    ReleaseDC(0, (HDC)nSafe);
  GlobalUnlock(v8);
  GlobalFree(v8);
  LeaveCriticalSection(&g_sys.m_critDCBusy);
  return (HICON__ *)v11;
}

```

## disassembly

```asm
0x18002b620  mov     rax, rsp
0x18002b623  mov     [rax+20h], xHot
0x18002b627  mov     [rax+18h], phbmpAnd
0x18002b62b  mov     [rax+10h], phbmpXor
0x18002b62f  mov     [rax+8], hRes
0x18002b633  push    rbp
0x18002b634  push    rbx
0x18002b635  push    rsi
0x18002b636  push    rdi
0x18002b637  push    r12
0x18002b639  push    r13
0x18002b63b  push    r14
0x18002b63d  push    r15
0x18002b63f  lea     rbp, [rax-48h]
0x18002b643  sub     rsp, 108h
0x18002b64a  xor     ebx, ebx
0x18002b64c  xorps   xmm0, xmm0
0x18002b64f  xorps   xmm1, xmm1
0x18002b652  mov     [rbp+40h+cbTotalSize], rbx
0x18002b656  mov     r12, hRes
0x18002b659  mov     [rbp+40h+nSafe], rbx
0x18002b65d  lea     hRes, ?g_sys@@3USysInfo@@A.m_critDCBusy; lpCriticalSection
0x18002b664  mov     [rsp+140h+hdcMem], rbx
0x18002b669  mov     r14d, ebx
0x18002b66c  mov     [rbp+40h+var_98], rbx
0x18002b670  mov     r13d, ebx
0x18002b673  mov     qword ptr [rbp+40h+bmpXOR.bmType], rbx
0x18002b677  movups  xmmword ptr [rbp+40h+bmpXOR.bmHeight], xmm0
0x18002b67b  mov     esi, ebx
0x18002b67d  movups  xmmword ptr [rbp+40h+bmpXOR.bmBits], xmm0
0x18002b681  movups  xmmword ptr [rbp+40h+bmpAND.bmHeight], xmm1
0x18002b685  movups  xmmword ptr [rbp+40h+bmpAND.bmBits], xmm1
0x18002b689  call    cs:__imp_EnterCriticalSection
0x18002b690  nop     dword ptr [rax+rax+00h]
0x18002b695  lea     phbmpXor, [rbp+40h+cbTotalSize]; phdc
0x18002b699  lea     hRes, ?g_sys@@3USysInfo@@A; this
0x18002b6a0  call    ?GetHdc@SysInfo@@QEAAJPEAPEAUHDC__@@@Z; SysInfo::GetHdc(HDC__ * *)
0x18002b6a5  mov     hRes, r12; hMem
0x18002b6a8  call    cs:__imp_GlobalLock
0x18002b6af  nop     dword ptr [rax+rax+00h]
0x18002b6b4  mov     hRes, r12; hMem
0x18002b6b7  mov     rdi, rax
0x18002b6ba  call    cs:__imp_GlobalSize
0x18002b6c1  nop     dword ptr [rax+rax+00h]
0x18002b6c6  mov     r15, rax
0x18002b6c9  lea     hRes, [rdi+28h]
0x18002b6cd  add     rax, rdi
0x18002b6d0  mov     [rbp+40h+cbitsWidth], rax
0x18002b6d4  cmp     r15, 28h ; '('
0x18002b6d8  jb      short loc_18002B703
0x18002b6da  cmp     dword ptr [rdi], 28h ; '('
0x18002b6dd  jnz     short loc_18002B703
0x18002b6df  mov     r9, rax
0x18002b6e2  sub     r9, hRes
0x18002b6e5  mov     [rsp+140h+pResult], r9
0x18002b6ea  cmp     [rdi+4], ebx
0x18002b6ed  jle     short loc_18002B703
0x18002b6ef  mov     eax, [rdi+8]
0x18002b6f2  test    eax, eax
0x18002b6f4  jz      short loc_18002B703
0x18002b6f6  jns     short loc_18002B70D
0x18002b6f8  cmp     [rdi+10h], ebx
0x18002b6fb  jz      short loc_18002B70D
0x18002b6fd  cmp     dword ptr [rdi+10h], 3
0x18002b701  jz      short loc_18002B70D
0x18002b703  mov     esi, 0FFFFh
0x18002b708  jmp     loc_18002BDCB
0x18002b70d  mov     edx, 1
0x18002b712  cmp     [rdi+0Ch], dx
0x18002b716  jnz     short loc_18002B703
0x18002b718  mov     r10d, [rdi+20h]
0x18002b71c  cmp     r10d, 100h
0x18002b723  jbe     short loc_18002B72C
0x18002b725  cmp     word ptr [rdi+0Eh], 8
0x18002b72a  jz      short loc_18002B703
0x18002b72c  cmp     dword ptr [rdi+10h], 3
0x18002b730  jnz     short loc_18002B744
0x18002b732  movzx   eax, word ptr [rdi+0Eh]
0x18002b736  mov     ecx, 0FFEFh
0x18002b73b  sub     ax, 10h
0x18002b73f  test    cx, ax
0x18002b742  jnz     short loc_18002B703
0x18002b744  test    r10d, r10d
0x18002b747  jnz     short loc_18002B75F
0x18002b749  movzx   ecx, word ptr [rdi+0Eh]
0x18002b74d  movzx   eax, cx
0x18002b750  sub     ax, dx
0x18002b753  cmp     ax, 7
0x18002b757  ja      short loc_18002B75F
0x18002b759  mov     r10d, edx
0x18002b75c  shl     r10d, cl
0x18002b75f  cmp     dword ptr [rdi+10h], 3
0x18002b763  mov     r11d, 0Ch
0x18002b769  mov     ecx, r10d
0x18002b76c  mov     eax, 4
0x18002b771  cmovnz  r11, rbx
0x18002b775  mov     [rbp+40h+hMem], rbx
0x18002b779  mul     hRes
0x18002b77c  mov     rbx, rax
0x18002b77f  test    phbmpXor, phbmpXor
0x18002b782  jnz     loc_18002B703
0x18002b788  lea     phbmpXor, [rax+r11]; Subtrahend
0x18002b78c  cmp     phbmpXor, rax
0x18002b78f  jb      loc_18002B703
0x18002b795  cmp     r9, phbmpXor
0x18002b798  jb      loc_18002B703
0x18002b79e  lea     phbmpAnd, [rsp+140h+pResult]; pResult
0x18002b7a3  mov     hRes, r9; Minuend
0x18002b7a6  call    ?SizeTSub@@YAJ_K0PEA_K@Z; SizeTSub(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002b7ab  test    eax, eax
0x18002b7ad  js      loc_18002B703
0x18002b7b3  mov     eax, [rdi]
0x18002b7b5  lea     hRes, [rbx+rax]
0x18002b7b9  cmp     hRes, rax
0x18002b7bc  jb      loc_18002B703
0x18002b7c2  lea     rax, [hRes+r11]
0x18002b7c6  cmp     rax, hRes
0x18002b7c9  jb      loc_18002B703
0x18002b7cf  cmp     r15, rax
0x18002b7d2  jb      loc_18002B703
0x18002b7d8  mov     eax, [rdi+8]
0x18002b7db  mov     ecx, 2
0x18002b7e0  cdq
0x18002b7e1  idiv    ecx
0x18002b7e3  movsxd  phbmpAnd, eax
0x18002b7e6  xor     eax, eax
0x18002b7e8  mov     [rdi+8], r8d
0x18002b7ec  test    r8d, r8d
0x18002b7ef  jz      loc_18002B703
0x18002b7f5  mov     ecx, [rdi+10h]
0x18002b7f8  mov     ebx, eax
0x18002b7fa  mov     [rbp+40h+hMem], rax
0x18002b7fe  mov     r11, 1FFFFFFFFFFFFFFCh
0x18002b808  test    ecx, ecx
0x18002b80a  jz      short loc_18002B815
0x18002b80c  cmp     ecx, 3
0x18002b80f  jnz     loc_18002B8A8
0x18002b815  mov     [rbp+40h+pullResult], rax
0x18002b819  mov     r9, phbmpAnd
0x18002b81c  test    r8d, r8d
0x18002b81f  jns     short loc_18002B836
0x18002b821  mov     eax, r8d
0x18002b824  neg     eax
0x18002b826  movsxd  r9, eax
0x18002b829  cmp     r8d, 80000000h
0x18002b830  jz      loc_18002B703
0x18002b836  movzx   edx, word ptr [rdi+0Eh]; ullMultiplier
0x18002b83a  lea     phbmpAnd, [rbp+40h+pullResult]; pullResult
0x18002b83e  movsxd  hRes, dword ptr [rdi+4]; ullMultiplicand
0x18002b842  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002b847  test    eax, eax
0x18002b849  js      loc_18002B703
0x18002b84f  mov     rax, [rbp+40h+pullResult]
0x18002b853  lea     phbmpXor, [rax+1Fh]
0x18002b857  cmp     phbmpXor, rax
0x18002b85a  jb      loc_18002B703
0x18002b860  shr     phbmpXor, 3
0x18002b864  lea     phbmpAnd, [rbp+40h+hMem]; pullResult
0x18002b868  and     phbmpXor, r11; ullMultiplier
0x18002b86b  mov     hRes, r9; ullMultiplicand
0x18002b86e  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002b873  test    eax, eax
0x18002b875  js      loc_18002B703
0x18002b87b  mov     rbx, [rbp+40h+hMem]
0x18002b87f  cmp     [rsp+140h+pResult], rbx
0x18002b884  jb      loc_18002B703
0x18002b88a  mov     eax, [rdi+10h]
0x18002b88d  xor     r11d, r11d
0x18002b890  mov     ecx, eax
0x18002b892  test    eax, eax
0x18002b894  jz      short loc_18002B8A8
0x18002b896  cmp     [rdi+14h], r11d
0x18002b89a  jz      short loc_18002B8A8
0x18002b89c  mov     eax, [rdi+14h]
0x18002b89f  cmp     rbx, rax
0x18002b8a2  ja      loc_18002B703
0x18002b8a8  mov     eax, [rdi+14h]
0x18002b8ab  cmp     [rsp+140h+pResult], rax
0x18002b8b0  jnb     short loc_18002B8C1
0x18002b8b2  xor     eax, eax
0x18002b8b4  test    ecx, ecx
0x18002b8b6  jnz     loc_18002B703
0x18002b8bc  mov     [rdi+14h], eax
0x18002b8bf  jmp     short loc_18002B8C3
0x18002b8c1  xor     eax, eax
0x18002b8c3  cmp     [rdi+20h], eax
0x18002b8c6  jz      short loc_18002B8CD
0x18002b8c8  mov     eax, [rdi+20h]
0x18002b8cb  jmp     short loc_18002B8DC
0x18002b8cd  cmp     word ptr [rdi+0Eh], 18h
0x18002b8d2  jnz     short loc_18002B8D9
0x18002b8d4  mov     hRes, rdi
0x18002b8d7  jmp     short loc_18002B8E0
0x18002b8d9  mov     eax, r10d
0x18002b8dc  lea     hRes, [rdi+rax*4]
0x18002b8e0  lea     r12, [hRes+28h]
0x18002b8e4  lea     rax, [rdi+28h]
0x18002b8e8  cmp     r12, rax
0x18002b8eb  jb      loc_18002BDC2
0x18002b8f1  lea     rax, [r15+rdi]
0x18002b8f5  cmp     r12, rax
0x18002b8f8  jnb     loc_18002BDC2
0x18002b8fe  xor     ecx, ecx; hWnd
0x18002b900  call    cs:__imp_GetDC
0x18002b907  nop     dword ptr [rax+rax+00h]
0x18002b90c  xor     ecx, ecx
0x18002b90e  mov     [rbp+40h+nSafe], rax
0x18002b912  cmp     [rbp+40h+arg_38], ecx
0x18002b918  jz      short loc_18002B93F
0x18002b91a  mov     edx, [rbp+40h+nHeight]; nHeight
0x18002b920  lea     eax, [hRes+1]
0x18002b923  mov     [rsp+140h+lpBits], hRes; lpBits
0x18002b928  mov     xHot, eax; nBitCount
0x18002b92b  mov     ecx, [rbp+40h+nWidth]; nWidth
0x18002b92e  mov     r8d, eax; nPlanes
0x18002b931  call    cs:__imp_CreateBitmap
0x18002b938  nop     dword ptr [rax+rax+00h]
0x18002b93d  jmp     short loc_18002B958
0x18002b93f  mov     r8d, [rbp+40h+nHeight]; cy
0x18002b946  mov     hRes, rax; hdc
0x18002b949  mov     edx, [rbp+40h+nWidth]; cx
0x18002b94c  call    cs:__imp_CreateCompatibleBitmap
0x18002b953  nop     dword ptr [rax+rax+00h]
0x18002b958  mov     r14, rax
0x18002b95b  test    rax, rax
0x18002b95e  jz      loc_18002BDC7
0x18002b964  mov     hRes, [rbp+40h+cbTotalSize]; hdc
0x18002b968  mov     phbmpXor, rax; h
0x18002b96b  call    cs:__imp_SelectObject
0x18002b972  nop     dword ptr [rax+rax+00h]
0x18002b977  mov     r15, rax
0x18002b97a  xor     eax, eax
0x18002b97c  cmp     [rdi+10h], eax
0x18002b97f  jz      short loc_18002B993
0x18002b981  cmp     dword ptr [rdi+10h], 3
0x18002b985  jz      short loc_18002B993
0x18002b987  cmp     [rdi+14h], eax
0x18002b98a  jz      loc_18002BBA1
0x18002b990  mov     ebx, [rdi+14h]
0x18002b993  lea     r13, [rbx+r12]
0x18002b997  cmp     r13, r12
0x18002b99a  jb      loc_18002BD6A
0x18002b9a0  lea     rax, [rdi+28h]
0x18002b9a4  cmp     r13, rax
0x18002b9a7  jb      loc_18002BD6A
0x18002b9ad  cmp     r13, [rbp+40h+cbitsWidth]
0x18002b9b1  ja      loc_18002BD6A
0x18002b9b7  mov     eax, [rdi+8]
0x18002b9ba  xor     ebx, ebx
0x18002b9bc  mov     hRes, [rbp+40h+cbTotalSize]; hdc
0x18002b9c0  xor     r8d, r8d; yDest
0x18002b9c3  mov     dword ptr [rsp+60h], 0CC0020h; rop
0x18002b9cb  xor     edx, edx; xDest
0x18002b9cd  mov     [rsp+140h+iUsage], ebx; iUsage
0x18002b9d1  mov     [rsp+140h+lpbmi], rdi; lpbmi
0x18002b9d6  mov     [rsp+140h+var_F8], r12; lpBits
0x18002b9db  mov     r12d, [rbp+40h+nHeight]
0x18002b9e2  mov     [rsp+140h+SrcHeight], eax; SrcHeight
0x18002b9e6  mov     eax, [rdi+4]
0x18002b9e9  mov     [rsp+140h+SrcWidth], eax; SrcWidth
0x18002b9ed  mov     [rsp+140h+ySrc], ebx; ySrc
0x18002b9f1  mov     [rsp+140h+xSrc], ebx; xSrc
0x18002b9f5  mov     ebx, [rbp+40h+nWidth]
0x18002b9f8  mov     xHot, ebx; DestWidth
0x18002b9fb  mov     dword ptr [rsp+140h+lpBits], r12d; DestHeight
0x18002ba00  call    cs:__imp_StretchDIBits
0x18002ba07  nop     dword ptr [rax+rax+00h]
0x18002ba0c  lea     phbmpAnd, [rbp+40h+bmpXOR.bmHeight]; pv
0x18002ba10  mov     edx, 20h ; ' '; c
0x18002ba15  mov     hRes, r14; h
0x18002ba18  call    cs:__imp_GetObjectW
0x18002ba1f  nop     dword ptr [rax+rax+00h]
0x18002ba24  mov     edx, dword ptr [rbp+40h+bmpXOR+14h]
0x18002ba27  mov     r8d, 0FFFFFFFFh
0x18002ba2d  mov     eax, dword ptr [rbp+40h+bmpXOR.bmPlanes]
0x18002ba30  imul    phbmpXor, rax
0x18002ba34  cmp     phbmpXor, phbmpAnd
0x18002ba37  ja      loc_18002BD76
0x18002ba3d  movzx   ecx, word ptr [rbp+40h+bmpXOR.bmBits]
0x18002ba41  mov     eax, edx
0x18002ba43  imul    hRes, rax
0x18002ba47  cmp     hRes, phbmpAnd
0x18002ba4a  ja      loc_18002BD76
0x18002ba50  mov     eax, ecx
0x18002ba52  mov     edx, ecx; dwBytes
0x18002ba54  mov     ecx, 2; uFlags
0x18002ba59  mov     [rbp+40h+pullResult], rax
0x18002ba5d  call    cs:__imp_GlobalAlloc
0x18002ba64  nop     dword ptr [rax+rax+00h]
0x18002ba69  xor     edx, edx
0x18002ba6b  mov     [rbp+40h+hMem], rax
0x18002ba6f  test    rax, rax
0x18002ba72  jz      loc_18002BD7B
0x18002ba78  mov     hRes, rax; hMem
0x18002ba7b  call    cs:__imp_GlobalLock
0x18002ba82  nop     dword ptr [rax+rax+00h]
0x18002ba87  mov     edx, dword ptr [rbp+40h+pullResult]; cb
0x18002ba8a  mov     hRes, r14; hbit
0x18002ba8d  mov     phbmpAnd, rax; lpvBits
0x18002ba90  mov     [rsp+140h+pResult], rax
  ... truncated ...
```
