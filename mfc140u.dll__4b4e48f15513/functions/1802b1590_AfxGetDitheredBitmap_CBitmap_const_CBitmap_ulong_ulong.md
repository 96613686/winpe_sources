# AfxGetDitheredBitmap(CBitmap const &,CBitmap *,ulong,ulong)

- ea: `0x1802b1590`
- end: `0x1802b1a65`
- name: `?AfxGetDitheredBitmap@@YAXAEBVCBitmap@@PEAV1@KK@Z`
- size: `1237`
- prototype: `void __fastcall(const CBitmap *rSrc, CBitmap *pDest, unsigned int cr1, unsigned int cr2)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1802b5000`

## callees

- `0x18001d090`
- `0x180139950`
- `0x18023d860`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802af220`
- `0x1802af360`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802b0a60`
- `0x1802b1590`
- `0x1802c4640`

## import_xrefs

- `USER32!FillRect` at `0x1802b18af`
- `USER32!FillRect` at `0x1802b18af`
- `GDI32!CreateBitmap` at `0x1802b16a7`
- `GDI32!CreateBitmap` at `0x1802b16dc`
- `GDI32!CreateBitmap` at `0x1802b174d`
- `GDI32!CreateBitmap` at `0x1802b16a7`
- `GDI32!CreateBitmap` at `0x1802b16dc`
- `GDI32!CreateBitmap` at `0x1802b174d`
- `GDI32!DeleteDC` at `0x1802b1a04`
- `GDI32!DeleteDC` at `0x1802b1a21`
- `GDI32!DeleteDC` at `0x1802b1a3e`
- `GDI32!DeleteDC` at `0x1802b1a04`
- `GDI32!DeleteDC` at `0x1802b1a21`
- `GDI32!DeleteDC` at `0x1802b1a3e`
- `GDI32!CreatePatternBrush` at `0x1802b16f4`
- `GDI32!CreatePatternBrush` at `0x1802b16f4`
- `GDI32!BitBlt` at `0x1802b17f2`
- `GDI32!BitBlt` at `0x1802b1837`
- `GDI32!BitBlt` at `0x1802b18fd`
- `GDI32!BitBlt` at `0x1802b1934`
- `GDI32!BitBlt` at `0x1802b1967`
- `GDI32!BitBlt` at `0x1802b17f2`
- `GDI32!BitBlt` at `0x1802b1837`
- `GDI32!BitBlt` at `0x1802b18fd`
- `GDI32!BitBlt` at `0x1802b1934`
- `GDI32!BitBlt` at `0x1802b1967`
- `GDI32!GetPixel` at `0x1802b17ae`
- `GDI32!GetPixel` at `0x1802b17ae`
- `GDI32!DeleteObject` at `0x1802b1734`
- `GDI32!DeleteObject` at `0x1802b1734`
- `GDI32!SelectObject` at `0x1802b1768`
- `GDI32!SelectObject` at `0x1802b1782`
- `GDI32!SelectObject` at `0x1802b1858`
- `GDI32!SelectObject` at `0x1802b1980`
- `GDI32!SelectObject` at `0x1802b1996`
- `GDI32!SelectObject` at `0x1802b19ac`
- `GDI32!SelectObject` at `0x1802b1768`
- `GDI32!SelectObject` at `0x1802b1782`
- `GDI32!SelectObject` at `0x1802b1858`
- `GDI32!SelectObject` at `0x1802b1980`
- `GDI32!SelectObject` at `0x1802b1996`
- `GDI32!SelectObject` at `0x1802b19ac`
- `GDI32!CreateCompatibleDC` at `0x1802b1619`
- `GDI32!CreateCompatibleDC` at `0x1802b1635`
- `GDI32!CreateCompatibleDC` at `0x1802b1651`
- `GDI32!CreateCompatibleDC` at `0x1802b1619`
- `GDI32!CreateCompatibleDC` at `0x1802b1635`
- `GDI32!CreateCompatibleDC` at `0x1802b1651`
- `GDI32!GetObjectW` at `0x1802b1678`
- `GDI32!GetObjectW` at `0x1802b1678`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall AfxGetDitheredBitmap(const CBitmap *rSrc, CBitmap *pDest, unsigned int cr1, unsigned int cr2)
{
  HDC CompatibleDC; // rax
  HDC v9; // rax
  HDC v10; // rax
  HBITMAP Bitmap; // rax
  HBITMAP v12; // rax
  HBRUSH PatternBrush; // rax
  void *m_hObject; // rbx
  CHandleMap *m_pmapHGDIOBJ; // rcx
  HBITMAP v16; // rax
  HGDIOBJ v17; // rax
  CGdiObject *v18; // r15
  HGDIOBJ v19; // rax
  CGdiObject *v20; // rax
  CGdiObject *v21; // rsi
  COLORREF Pixel; // eax
  unsigned int v23; // ebx
  void *v24; // rdx
  HGDIOBJ v25; // rax
  CGdiObject *v26; // r14
  unsigned int v27; // edi
  unsigned int v28; // ebx
  void *v29; // rdx
  HGDIOBJ v30; // rax
  HGDIOBJ v31; // rax
  HGDIOBJ v32; // rax
  HDC v33; // rax
  HDC v34; // rax
  HDC v35; // rax
  CBitmap bmpMask; // [rsp+50h] [rbp-B0h] BYREF
  tagBITMAP bm; // [rsp+60h] [rbp-A0h] BYREF
  CDC dcDest; // [rsp+80h] [rbp-80h] BYREF
  CDC dcSrc; // [rsp+A0h] [rbp-60h] BYREF
  CBrush brChecker; // [rsp+C0h] [rbp-40h] BYREF
  CDC dcMask; // [rsp+D0h] [rbp-30h] BYREF
  RECT rc; // [rsp+F0h] [rbp-10h] BYREF

  dcSrc.__vftable = (CDC_vtbl *)CDC::`vftable';
  memset(&dcSrc.m_hDC, 0, 20);
  dcMask.__vftable = (CDC_vtbl *)CDC::`vftable';
  memset(&dcMask.m_hDC, 0, 20);
  dcDest.__vftable = (CDC_vtbl *)CDC::`vftable';
  memset(&dcDest.m_hDC, 0, 20);
  bmpMask.m_hObject = 0;
  bmpMask.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
  brChecker.m_hObject = 0;
  brChecker.__vftable = (CBrush_vtbl *)CBrush::`vftable';
  CompatibleDC = CreateCompatibleDC(0);
  if ( CDC::Attach(&dcSrc, CompatibleDC) )
  {
    v9 = CreateCompatibleDC(0);
    if ( CDC::Attach(&dcMask, v9) )
    {
      v10 = CreateCompatibleDC(0);
      if ( CDC::Attach(&dcDest, v10) )
      {
        if ( GetObjectW(rSrc->m_hObject, 32, &bm) )
        {
          CGdiObject::DeleteObject(pDest);
          Bitmap = CreateBitmap(bm.bmWidth, bm.bmHeight, bm.bmPlanes, bm.bmBitsPixel, 0);
          if ( CGdiObject::Attach(pDest, Bitmap) )
          {
            v12 = CreateBitmap(8, 8, 1u, 1u, wPat);
            CGdiObject::Attach(&bmpMask, v12);
            PatternBrush = CreatePatternBrush((HBITMAP)bmpMask.m_hObject);
            CGdiObject::Attach(&brChecker, PatternBrush);
            m_hObject = bmpMask.m_hObject;
            if ( bmpMask.m_hObject )
            {
              m_pmapHGDIOBJ = AfxGetModuleThreadState()->m_pmapHGDIOBJ;
              if ( m_pmapHGDIOBJ )
                CMapPtrToWord::RemoveKey((CMapPtrToWord *)&m_pmapHGDIOBJ->m_permanentMap, bmpMask.m_hObject);
              bmpMask.m_hObject = 0;
              DeleteObject(m_hObject);
            }
            v16 = CreateBitmap(bm.bmWidth, bm.bmHeight, 1u, 1u, 0);
            CGdiObject::Attach(&bmpMask, v16);
            v17 = SelectObject(dcSrc.m_hDC, rSrc->m_hObject);
            v18 = CGdiObject::FromHandle(v17);
            v19 = SelectObject(dcMask.m_hDC, bmpMask.m_hObject);
            v20 = CGdiObject::FromHandle(v19);
            v21 = v20;
            if ( v18 && v20 )
            {
              Pixel = GetPixel(dcSrc.m_hDC, 0, 0);
              v23 = CDC::SetBkColor(&dcSrc, Pixel);
              BitBlt(dcMask.m_hDC, 0, 0, bm.bmWidth, bm.bmHeight, dcSrc.m_hDC, 0, 0, 0xCC0020u);
              CDC::SetBkColor(&dcSrc, 0xFFFFFFu);
              BitBlt(dcMask.m_hDC, 0, 0, bm.bmWidth, bm.bmHeight, dcSrc.m_hDC, 0, 0, 0xEE0086u);
              CDC::SetBkColor(&dcSrc, v23);
              v24 = 0;
              if ( pDest )
                v24 = pDest->m_hObject;
              v25 = SelectObject(dcDest.m_hDC, v24);
              v26 = CGdiObject::FromHandle(v25);
              if ( v26 )
              {
                v27 = CDC::SetTextColor(&dcDest, cr1);
                v28 = CDC::SetBkColor(&dcDest, cr2);
                *(_QWORD *)&rc.left = 0;
                rc.right = bm.bmWidth;
                rc.bottom = bm.bmHeight;
                FillRect(dcDest.m_hDC, &rc, (HBRUSH)brChecker.m_hObject);
                CDC::SetTextColor(&dcDest, v27);
                CDC::SetBkColor(&dcDest, v28);
                BitBlt(dcDest.m_hDC, 0, 0, bm.bmWidth, bm.bmHeight, dcSrc.m_hDC, 0, 0, 0x660046u);
                BitBlt(dcDest.m_hDC, 0, 0, bm.bmWidth, bm.bmHeight, dcMask.m_hDC, 0, 0, 0x8800C6u);
                BitBlt(dcDest.m_hDC, 0, 0, bm.bmWidth, bm.bmHeight, dcSrc.m_hDC, 0, 0, 0x660046u);
                v29 = v26->m_hObject;
              }
              else
              {
                v29 = 0;
              }
              v30 = SelectObject(dcDest.m_hDC, v29);
              CGdiObject::FromHandle(v30);
              v31 = SelectObject(dcMask.m_hDC, v21->m_hObject);
              CGdiObject::FromHandle(v31);
              v32 = SelectObject(dcSrc.m_hDC, v18->m_hObject);
              CGdiObject::FromHandle(v32);
            }
          }
        }
      }
    }
  }
  brChecker.__vftable = (CBrush_vtbl *)CBrush::`vftable';
  CGdiObject::~CGdiObject(&brChecker);
  bmpMask.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
  CGdiObject::~CGdiObject(&bmpMask);
  dcDest.__vftable = (CDC_vtbl *)CDC::`vftable';
  if ( dcDest.m_hDC )
  {
    v33 = CDC::Detach(&dcDest);
    DeleteDC(v33);
  }
  dcMask.__vftable = (CDC_vtbl *)CDC::`vftable';
  if ( dcMask.m_hDC )
  {
    v34 = CDC::Detach(&dcMask);
    DeleteDC(v34);
  }
  dcSrc.__vftable = (CDC_vtbl *)CDC::`vftable';
  if ( dcSrc.m_hDC )
  {
    v35 = CDC::Detach(&dcSrc);
    DeleteDC(v35);
  }
}

```

## disassembly

```asm
0x1802b1590  push    rbp
0x1802b1592  push    rbx
0x1802b1593  push    rsi
0x1802b1594  push    rdi
0x1802b1595  push    r12
0x1802b1597  push    r13
0x1802b1599  push    r14
0x1802b159b  push    r15
0x1802b159d  lea     rbp, [rsp-18h]
0x1802b15a2  sub     rsp, 118h
0x1802b15a9  mov     rax, cs:__security_cookie
0x1802b15b0  xor     rax, rsp
0x1802b15b3  mov     [rbp+50h+var_50], rax
0x1802b15b7  mov     r13d, cr2
0x1802b15ba  mov     r12d, cr1
0x1802b15bd  mov     rdi, pDest
0x1802b15c0  mov     rsi, rSrc
0x1802b15c3  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x1802b15ca  mov     [rbp+50h+dcSrc.__vftable], rax
0x1802b15ce  xorps   xmm0, xmm0
0x1802b15d1  movdqu  xmmword ptr [rbp+50h+dcSrc.m_hDC], xmm0
0x1802b15d6  xor     r14d, r14d
0x1802b15d9  mov     [rbp+50h+dcSrc.m_bPrinting], r14d
0x1802b15dd  mov     [rbp+50h+dcMask.__vftable], rax
0x1802b15e1  movdqu  xmmword ptr [rbp+50h+dcMask.m_hDC], xmm0
0x1802b15e6  mov     [rbp+50h+dcMask.m_bPrinting], r14d
0x1802b15ea  mov     [rbp+50h+dcDest.__vftable], rax
0x1802b15ee  movdqu  xmmword ptr [rbp+50h+dcDest.m_hDC], xmm0
0x1802b15f3  mov     [rbp+50h+dcDest.m_bPrinting], r14d
0x1802b15f7  mov     [rsp+150h+bmpMask.m_hObject], r14
0x1802b15fc  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x1802b1603  mov     [rsp+150h+bmpMask.__vftable], rax
0x1802b1608  mov     [rbp+50h+brChecker.m_hObject], r14
0x1802b160c  lea     rax, ??_7CBrush@@6B@; const CBrush::`vftable'
0x1802b1613  mov     [rbp+50h+brChecker.__vftable], rax
0x1802b1617  xor     ecx, ecx; hdc
0x1802b1619  call    cs:__imp_CreateCompatibleDC
0x1802b161f  mov     pDest, rax; hDC
0x1802b1622  lea     rSrc, [rbp+50h+dcSrc]; this
0x1802b1626  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x1802b162b  test    eax, eax
0x1802b162d  jz      loc_1802B19BB
0x1802b1633  xor     ecx, ecx; hdc
0x1802b1635  call    cs:__imp_CreateCompatibleDC
0x1802b163b  mov     pDest, rax; hDC
0x1802b163e  lea     rSrc, [rbp+50h+dcMask]; this
0x1802b1642  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x1802b1647  test    eax, eax
0x1802b1649  jz      loc_1802B19BB
0x1802b164f  xor     ecx, ecx; hdc
0x1802b1651  call    cs:__imp_CreateCompatibleDC
0x1802b1657  mov     pDest, rax; hDC
0x1802b165a  lea     rSrc, [rbp+50h+dcDest]; this
0x1802b165e  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x1802b1663  test    eax, eax
0x1802b1665  jz      loc_1802B19BB
0x1802b166b  lea     r8, [rsp+150h+bm]; pv
0x1802b1670  lea     edx, [r14+20h]; c
0x1802b1674  mov     rSrc, [rsi+8]; h
0x1802b1678  call    cs:__imp_GetObjectW
0x1802b167e  test    eax, eax
0x1802b1680  jz      loc_1802B19BB
0x1802b1686  mov     rSrc, rdi; this
0x1802b1689  call    ?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x1802b168e  movzx   cr2, [rsp+150h+bm.bmBitsPixel]; nBitCount
0x1802b1694  movzx   cr1, [rsp+150h+bm.bmPlanes]; nPlanes
0x1802b169a  mov     [rsp+150h+lpBits], r14; lpBits
0x1802b169f  mov     edx, [rsp+150h+bm.bmHeight]; nHeight
0x1802b16a3  mov     ecx, [rsp+150h+bm.bmWidth]; nWidth
0x1802b16a7  call    cs:__imp_CreateBitmap
0x1802b16ad  mov     pDest, rax; hObject
0x1802b16b0  mov     rSrc, rdi; this
0x1802b16b3  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1802b16b8  test    eax, eax
0x1802b16ba  jz      loc_1802B19BB
0x1802b16c0  lea     rax, wPat
0x1802b16c7  mov     [rsp+150h+lpBits], rax; lpBits
0x1802b16cc  lea     r15d, [r14+1]
0x1802b16d0  mov     cr2, r15d; nBitCount
0x1802b16d3  mov     cr1, r15d; nPlanes
0x1802b16d6  lea     ecx, [r14+8]; nWidth
0x1802b16da  mov     edx, ecx; nHeight
0x1802b16dc  call    cs:__imp_CreateBitmap
0x1802b16e2  mov     pDest, rax; hObject
0x1802b16e5  lea     rSrc, [rsp+150h+bmpMask]; this
0x1802b16ea  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1802b16ef  mov     rSrc, [rsp+150h+bmpMask.m_hObject]; hbm
0x1802b16f4  call    cs:__imp_CreatePatternBrush
0x1802b16fa  mov     pDest, rax; hObject
0x1802b16fd  lea     rSrc, [rbp+50h+brChecker]; this
0x1802b1701  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1802b1706  mov     rbx, [rsp+150h+bmpMask.m_hObject]
0x1802b170b  test    rbx, rbx
0x1802b170e  jz      short loc_1802B173A
0x1802b1710  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x1802b1715  mov     rSrc, [rax+40h]
0x1802b1719  test    rSrc, rSrc
0x1802b171c  jz      short loc_1802B172C
0x1802b171e  add     rSrc, 28h ; '('; this
0x1802b1722  mov     pDest, [rsp+150h+bmpMask.m_hObject]; key
0x1802b1727  call    ?RemoveKey@CMapPtrToWord@@QEAAHPEAX@Z; CMapPtrToWord::RemoveKey(void *)
0x1802b172c  mov     [rsp+150h+bmpMask.m_hObject], r14
0x1802b1731  mov     rSrc, rbx; ho
0x1802b1734  call    cs:__imp_DeleteObject
0x1802b173a  mov     [rsp+150h+lpBits], r14; lpBits
0x1802b173f  mov     cr2, r15d; nBitCount
0x1802b1742  mov     cr1, r15d; nPlanes
0x1802b1745  mov     edx, [rsp+150h+bm.bmHeight]; nHeight
0x1802b1749  mov     ecx, [rsp+150h+bm.bmWidth]; nWidth
0x1802b174d  call    cs:__imp_CreateBitmap
0x1802b1753  mov     pDest, rax; hObject
0x1802b1756  lea     rSrc, [rsp+150h+bmpMask]; this
0x1802b175b  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1802b1760  mov     pDest, [rsi+8]; h
0x1802b1764  mov     rSrc, [rbp+50h+dcSrc.m_hDC]; hdc
0x1802b1768  call    cs:__imp_SelectObject
0x1802b176e  mov     rSrc, rax; h
0x1802b1771  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1802b1776  mov     r15, rax
0x1802b1779  mov     pDest, [rsp+150h+bmpMask.m_hObject]; h
0x1802b177e  mov     rSrc, [rbp+50h+dcMask.m_hDC]; hdc
0x1802b1782  call    cs:__imp_SelectObject
0x1802b1788  mov     rSrc, rax; h
0x1802b178b  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1802b1790  mov     rsi, rax
0x1802b1793  test    r15, r15
0x1802b1796  jz      loc_1802B19BB
0x1802b179c  test    rax, rax
0x1802b179f  jz      loc_1802B19BB
0x1802b17a5  xor     cr1, cr1; y
0x1802b17a8  xor     edx, edx; x
0x1802b17aa  mov     rSrc, [rbp+50h+dcSrc.m_hDC]; hdc
0x1802b17ae  call    cs:__imp_GetPixel
0x1802b17b4  mov     edx, eax; crColor
0x1802b17b6  lea     rSrc, [rbp+50h+dcSrc]; this
0x1802b17ba  call    ?SetBkColor@CDC@@UEAAKK@Z; CDC::SetBkColor(ulong)
0x1802b17bf  mov     ebx, eax
0x1802b17c1  mov     [rsp+150h+rop], 0CC0020h; rop
0x1802b17c9  mov     [rsp+150h+y1], r14d; y1
0x1802b17ce  mov     [rsp+150h+x1], r14d; x1
0x1802b17d3  mov     rSrc, [rbp+50h+dcSrc.m_hDC]
0x1802b17d7  mov     [rsp+150h+hdcSrc], rSrc; hdcSrc
0x1802b17dc  mov     ecx, [rsp+150h+bm.bmHeight]
0x1802b17e0  mov     dword ptr [rsp+150h+lpBits], ecx; cy
0x1802b17e4  mov     cr2, [rsp+150h+bm.bmWidth]; cx
0x1802b17e9  xor     cr1, cr1; y
0x1802b17ec  xor     edx, edx; x
0x1802b17ee  mov     rSrc, [rbp+50h+dcMask.m_hDC]; hdc
0x1802b17f2  call    cs:__imp_BitBlt
0x1802b17f8  mov     edx, 0FFFFFFh; crColor
0x1802b17fd  lea     rSrc, [rbp+50h+dcSrc]; this
0x1802b1801  call    ?SetBkColor@CDC@@UEAAKK@Z; CDC::SetBkColor(ulong)
0x1802b1806  mov     [rsp+150h+rop], 0EE0086h; rop
0x1802b180e  mov     [rsp+150h+y1], r14d; y1
0x1802b1813  mov     [rsp+150h+x1], r14d; x1
0x1802b1818  mov     rax, [rbp+50h+dcSrc.m_hDC]
0x1802b181c  mov     [rsp+150h+hdcSrc], rax; hdcSrc
0x1802b1821  mov     eax, [rsp+150h+bm.bmHeight]
0x1802b1825  mov     dword ptr [rsp+150h+lpBits], eax; cy
0x1802b1829  mov     cr2, [rsp+150h+bm.bmWidth]; cx
0x1802b182e  xor     cr1, cr1; y
0x1802b1831  xor     edx, edx; x
0x1802b1833  mov     rSrc, [rbp+50h+dcMask.m_hDC]; hdc
0x1802b1837  call    cs:__imp_BitBlt
0x1802b183d  mov     edx, ebx; crColor
0x1802b183f  lea     rSrc, [rbp+50h+dcSrc]; this
0x1802b1843  call    ?SetBkColor@CDC@@UEAAKK@Z; CDC::SetBkColor(ulong)
0x1802b1848  test    rdi, rdi
0x1802b184b  mov     pDest, r14
0x1802b184e  jz      short loc_1802B1854
0x1802b1850  mov     pDest, [rdi+8]; h
0x1802b1854  mov     rSrc, [rbp+50h+dcDest.m_hDC]; hdc
0x1802b1858  call    cs:__imp_SelectObject
0x1802b185e  mov     rSrc, rax; h
0x1802b1861  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1802b1866  mov     r14, rax
0x1802b1869  test    rax, rax
0x1802b186c  jz      loc_1802B1976
0x1802b1872  mov     edx, r12d; crColor
0x1802b1875  lea     rSrc, [rbp+50h+dcDest]; this
0x1802b1879  call    ?SetTextColor@CDC@@UEAAKK@Z; CDC::SetTextColor(ulong)
0x1802b187e  mov     edi, eax
0x1802b1880  mov     edx, r13d; crColor
0x1802b1883  lea     rSrc, [rbp+50h+dcDest]; this
0x1802b1887  call    ?SetBkColor@CDC@@UEAAKK@Z; CDC::SetBkColor(ulong)
0x1802b188c  mov     ebx, eax
0x1802b188e  xor     r12d, r12d
0x1802b1891  mov     qword ptr [rbp+50h+rc.left], r12
0x1802b1895  mov     ecx, [rsp+150h+bm.bmWidth]
0x1802b1899  mov     [rbp+50h+rc.right], ecx
0x1802b189c  mov     ecx, [rsp+150h+bm.bmHeight]
0x1802b18a0  mov     [rbp+50h+rc.bottom], ecx
0x1802b18a3  mov     r8, [rbp+50h+brChecker.m_hObject]; hbr
0x1802b18a7  lea     pDest, [rbp+50h+rc]; lprc
0x1802b18ab  mov     rSrc, [rbp+50h+dcDest.m_hDC]; hDC
0x1802b18af  call    cs:__imp_FillRect
0x1802b18b5  mov     edx, edi; crColor
0x1802b18b7  lea     rSrc, [rbp+50h+dcDest]; this
0x1802b18bb  call    ?SetTextColor@CDC@@UEAAKK@Z; CDC::SetTextColor(ulong)
0x1802b18c0  mov     edx, ebx; crColor
0x1802b18c2  lea     rSrc, [rbp+50h+dcDest]; this
0x1802b18c6  call    ?SetBkColor@CDC@@UEAAKK@Z; CDC::SetBkColor(ulong)
0x1802b18cb  mov     ebx, 660046h
0x1802b18d0  mov     [rsp+150h+rop], ebx; rop
0x1802b18d4  mov     [rsp+150h+y1], r12d; y1
0x1802b18d9  mov     [rsp+150h+x1], r12d; x1
0x1802b18de  mov     rax, [rbp+50h+dcSrc.m_hDC]
0x1802b18e2  mov     [rsp+150h+hdcSrc], rax; hdcSrc
0x1802b18e7  mov     eax, [rsp+150h+bm.bmHeight]
0x1802b18eb  mov     dword ptr [rsp+150h+lpBits], eax; cy
0x1802b18ef  mov     cr2, [rsp+150h+bm.bmWidth]; cx
0x1802b18f4  xor     cr1, cr1; y
0x1802b18f7  xor     edx, edx; x
0x1802b18f9  mov     rSrc, [rbp+50h+dcDest.m_hDC]; hdc
0x1802b18fd  call    cs:__imp_BitBlt
0x1802b1903  mov     [rsp+150h+rop], 8800C6h; rop
0x1802b190b  mov     [rsp+150h+y1], r12d; y1
0x1802b1910  mov     [rsp+150h+x1], r12d; x1
0x1802b1915  mov     rax, [rbp+50h+dcMask.m_hDC]
0x1802b1919  mov     [rsp+150h+hdcSrc], rax; hdcSrc
0x1802b191e  mov     eax, [rsp+150h+bm.bmHeight]
0x1802b1922  mov     dword ptr [rsp+150h+lpBits], eax; cy
0x1802b1926  mov     cr2, [rsp+150h+bm.bmWidth]; cx
0x1802b192b  xor     cr1, cr1; y
0x1802b192e  xor     edx, edx; x
0x1802b1930  mov     rSrc, [rbp+50h+dcDest.m_hDC]; hdc
0x1802b1934  call    cs:__imp_BitBlt
0x1802b193a  mov     [rsp+150h+rop], ebx; rop
0x1802b193e  mov     [rsp+150h+y1], r12d; y1
0x1802b1943  mov     [rsp+150h+x1], r12d; x1
0x1802b1948  mov     rax, [rbp+50h+dcSrc.m_hDC]
0x1802b194c  mov     [rsp+150h+hdcSrc], rax; hdcSrc
0x1802b1951  mov     eax, [rsp+150h+bm.bmHeight]
0x1802b1955  mov     dword ptr [rsp+150h+lpBits], eax; cy
0x1802b1959  mov     cr2, [rsp+150h+bm.bmWidth]; cx
0x1802b195e  xor     cr1, cr1; y
0x1802b1961  xor     edx, edx; x
0x1802b1963  mov     rSrc, [rbp+50h+dcDest.m_hDC]; hdc
0x1802b1967  call    cs:__imp_BitBlt
0x1802b196d  mov     pDest, [r14+8]
0x1802b1971  xor     r14d, r14d
0x1802b1974  jmp     short loc_1802B197C
0x1802b1976  xor     r14d, r14d
0x1802b1979  mov     edx, r14d; h
0x1802b197c  mov     rSrc, [rbp+50h+dcDest.m_hDC]; hdc
0x1802b1980  call    cs:__imp_SelectObject
0x1802b1986  mov     rSrc, rax; h
0x1802b1989  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1802b198e  mov     pDest, [rsi+8]; h
0x1802b1992  mov     rSrc, [rbp+50h+dcMask.m_hDC]; hdc
0x1802b1996  call    cs:__imp_SelectObject
0x1802b199c  mov     rSrc, rax; h
0x1802b199f  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1802b19a4  mov     pDest, [r15+8]; h
0x1802b19a8  mov     rSrc, [rbp+50h+dcSrc.m_hDC]; hdc
0x1802b19ac  call    cs:__imp_SelectObject
0x1802b19b2  mov     rSrc, rax; h
0x1802b19b5  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1802b19ba  nop
0x1802b19bb  lea     rax, ??_7CBrush@@6B@; const CBrush::`vftable'
0x1802b19c2  mov     [rbp+50h+brChecker.__vftable], rax
0x1802b19c6  lea     rSrc, [rbp+50h+brChecker]; this
0x1802b19ca  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1802b19cf  nop
0x1802b19d0  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x1802b19d7  mov     [rsp+150h+bmpMask.__vftable], rax
0x1802b19dc  lea     rSrc, [rsp+150h+bmpMask]; this
0x1802b19e1  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1802b19e6  nop
0x1802b19e7  lea     rbx, ??_7CDC@@6B@; const CDC::`vftable'
0x1802b19ee  mov     [rbp+50h+dcDest.__vftable], rbx
0x1802b19f2  cmp     [rbp+50h+dcDest.m_hDC], r14
0x1802b19f6  jz      short loc_1802B1A0B
0x1802b19f8  lea     rSrc, [rbp+50h+dcDest]; this
0x1802b19fc  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1802b1a01  mov     rSrc, rax; hdc
0x1802b1a04  call    cs:__imp_DeleteDC
0x1802b1a0a  nop
0x1802b1a0b  mov     [rbp+50h+dcMask.__vftable], rbx
0x1802b1a0f  cmp     [rbp+50h+dcMask.m_hDC], r14
0x1802b1a13  jz      short loc_1802B1A28
0x1802b1a15  lea     rSrc, [rbp+50h+dcMask]; this
0x1802b1a19  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1802b1a1e  mov     rSrc, rax; hdc
0x1802b1a21  call    cs:__imp_DeleteDC
0x1802b1a27  nop
0x1802b1a28  mov     [rbp+50h+dcSrc.__vftable], rbx
0x1802b1a2c  cmp     [rbp+50h+dcSrc.m_hDC], r14
0x1802b1a30  jz      short loc_1802B1A45
0x1802b1a32  lea     rSrc, [rbp+50h+dcSrc]; this
0x1802b1a36  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1802b1a3b  mov     rSrc, rax; hdc
0x1802b1a3e  call    cs:__imp_DeleteDC
0x1802b1a44  nop
0x1802b1a45  mov     rSrc, [rbp+50h+var_50]
0x1802b1a49  xor     rSrc, rsp; StackCookie
0x1802b1a4c  call    __security_check_cookie
0x1802b1a51  add     rsp, 118h
0x1802b1a58  pop     r15
0x1802b1a5a  pop     r14
  ... truncated ...
```
