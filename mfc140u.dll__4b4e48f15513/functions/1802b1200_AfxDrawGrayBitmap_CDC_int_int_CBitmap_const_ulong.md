# AfxDrawGrayBitmap(CDC *,int,int,CBitmap const &,ulong)

- ea: `0x1802b1200`
- end: `0x1802b158f`
- name: `?AfxDrawGrayBitmap@@YAXPEAVCDC@@HHAEBVCBitmap@@K@Z`
- size: `911`
- prototype: `void __fastcall(CDC *pDC, int x, int y, const CBitmap *rSrc, unsigned int crBackground)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18001d090`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802af110`
- `0x1802af220`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802b0b50`
- `0x1802b1200`
- `0x1802b25f0`
- `0x1802c7020`

## import_xrefs

- `USER32!GetSysColor` at `0x1802b1268`
- `USER32!GetSysColor` at `0x1802b127f`
- `USER32!GetSysColor` at `0x1802b1268`
- `USER32!GetSysColor` at `0x1802b127f`
- `GDI32!CreateBitmap` at `0x1802b130f`
- `GDI32!CreateBitmap` at `0x1802b130f`
- `GDI32!DeleteDC` at `0x1802b1549`
- `GDI32!DeleteDC` at `0x1802b1567`
- `GDI32!DeleteDC` at `0x1802b1549`
- `GDI32!DeleteDC` at `0x1802b1567`
- `GDI32!BitBlt` at `0x1802b13b8`
- `GDI32!BitBlt` at `0x1802b13fd`
- `GDI32!BitBlt` at `0x1802b1478`
- `GDI32!BitBlt` at `0x1802b14ba`
- `GDI32!BitBlt` at `0x1802b13b8`
- `GDI32!BitBlt` at `0x1802b13fd`
- `GDI32!BitBlt` at `0x1802b1478`
- `GDI32!BitBlt` at `0x1802b14ba`
- `GDI32!GetPixel` at `0x1802b1376`
- `GDI32!GetPixel` at `0x1802b1376`
- `GDI32!SelectObject` at `0x1802b1331`
- `GDI32!SelectObject` at `0x1802b134a`
- `GDI32!SelectObject` at `0x1802b14e5`
- `GDI32!SelectObject` at `0x1802b1331`
- `GDI32!SelectObject` at `0x1802b134a`
- `GDI32!SelectObject` at `0x1802b14e5`
- `GDI32!CreateCompatibleDC` at `0x1802b129e`
- `GDI32!CreateCompatibleDC` at `0x1802b12c5`
- `GDI32!CreateCompatibleDC` at `0x1802b129e`
- `GDI32!CreateCompatibleDC` at `0x1802b12c5`
- `GDI32!GetObjectW` at `0x1802b12ec`
- `GDI32!GetObjectW` at `0x1802b12ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall AfxDrawGrayBitmap(CDC *pDC, int x, int y, const CBitmap *rSrc, unsigned int crBackground)
{
  DWORD SysColor; // eax
  DWORD v10; // eax
  HDC__ *m_hDC; // rcx
  HDC CompatibleDC; // rax
  HDC__ *v13; // rcx
  HDC v14; // rax
  HBITMAP Bitmap; // rax
  HGDIOBJ v16; // rax
  CGdiObject *v17; // rbx
  HGDIOBJ v18; // rax
  CGdiObject *v19; // rax
  CGdiObject *v20; // r14
  COLORREF Pixel; // eax
  unsigned int v22; // edi
  CFont *v23; // rbx
  HGDIOBJ v24; // rax
  HDC v25; // rax
  HDC v26; // rax
  tagBITMAP bm; // [rsp+50h] [rbp-59h] BYREF
  CDC dcMask; // [rsp+70h] [rbp-39h] BYREF
  CDC dcMem; // [rsp+90h] [rbp-19h] BYREF
  CBitmap bmpMask; // [rsp+B0h] [rbp+7h] BYREF
  CBrush brShadow; // [rsp+C0h] [rbp+17h] BYREF
  CBrush brHighLight; // [rsp+D0h] [rbp+27h] BYREF

  dcMem.m_hDC = (HDC__ *)CDC::`vftable';
  *(_OWORD *)&dcMem.m_hAttribDC = 0;
  LODWORD(bmpMask.__vftable) = 0;
  dcMask.m_hDC = (HDC__ *)CDC::`vftable';
  *(_OWORD *)&dcMask.m_hAttribDC = 0;
  LODWORD(dcMem.__vftable) = 0;
  brShadow.__vftable = 0;
  bmpMask.m_hObject = (void *)CBitmap::`vftable';
  SysColor = GetSysColor(20);
  CBrush::CBrush((CBrush *)&brHighLight.m_hObject, SysColor);
  v10 = GetSysColor(16);
  CBrush::CBrush((CBrush *)&brShadow.m_hObject, v10);
  if ( pDC )
    m_hDC = pDC->m_hDC;
  else
    m_hDC = 0;
  CompatibleDC = CreateCompatibleDC(m_hDC);
  if ( CDC::Attach((CDC *)&dcMem.m_hDC, CompatibleDC) )
  {
    v13 = pDC ? pDC->m_hDC : 0LL;
    v14 = CreateCompatibleDC(v13);
    if ( CDC::Attach((CDC *)&dcMask.m_hDC, v14) )
    {
      if ( GetObjectW(rSrc->m_hObject, 32, &bm.bmHeight) )
      {
        Bitmap = CreateBitmap(bm.bmWidthBytes, *(int *)&bm.bmPlanes, 1u, 1u, 0);
        if ( CGdiObject::Attach((CGdiObject *)&bmpMask.m_hObject, Bitmap) )
        {
          v16 = SelectObject(dcMem.m_hAttribDC, rSrc->m_hObject);
          v17 = CGdiObject::FromHandle(v16);
          v18 = SelectObject(dcMask.m_hAttribDC, brShadow.__vftable);
          v19 = CGdiObject::FromHandle(v18);
          v20 = v19;
          if ( v17 )
          {
            if ( v19 )
            {
              Pixel = GetPixel(dcMem.m_hAttribDC, 0, 0);
              v22 = CDC::SetBkColor((CDC *)&dcMem.m_hDC, Pixel);
              BitBlt(
                dcMask.m_hAttribDC,
                0,
                0,
                bm.bmWidthBytes,
                *(int *)&bm.bmPlanes,
                dcMem.m_hAttribDC,
                0,
                0,
                0xCC0020u);
              CDC::SetBkColor((CDC *)&dcMem.m_hDC, 0xFFFFFFu);
              BitBlt(
                dcMask.m_hAttribDC,
                0,
                0,
                bm.bmWidthBytes,
                *(int *)&bm.bmPlanes,
                dcMem.m_hAttribDC,
                0,
                0,
                0x1100A6u);
              CDC::FillSolidRect(pDC, x, y, bm.bmWidthBytes, *(int *)&bm.bmPlanes, crBackground);
              pDC->SetBkColor(pDC, 0xFFFFFFu);
              v23 = CDC::SelectObject(pDC, (CFont *)&brHighLight.m_hObject);
              BitBlt(
                pDC->m_hDC,
                x + 1,
                y + 1,
                bm.bmWidthBytes,
                *(int *)&bm.bmPlanes,
                dcMask.m_hAttribDC,
                0,
                0,
                0xE20746u);
              CDC::SelectObject(pDC, (CFont *)&brShadow.m_hObject);
              BitBlt(pDC->m_hDC, x, y, bm.bmWidthBytes, *(int *)&bm.bmPlanes, dcMask.m_hAttribDC, 0, 0, 0xE20746u);
              CDC::SelectObject(pDC, v23);
              pDC->SetBkColor(pDC, v22);
              v24 = SelectObject(dcMask.m_hAttribDC, v20->m_hObject);
              CGdiObject::FromHandle(v24);
            }
          }
        }
      }
    }
  }
  brShadow.m_hObject = (void *)CBrush::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)&brShadow.m_hObject);
  brHighLight.m_hObject = (void *)CBrush::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)&brHighLight.m_hObject);
  bmpMask.m_hObject = (void *)CBitmap::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)&bmpMask.m_hObject);
  dcMask.m_hDC = (HDC__ *)CDC::`vftable';
  if ( dcMask.m_hAttribDC )
  {
    v25 = CDC::Detach((CDC *)&dcMask.m_hDC);
    DeleteDC(v25);
  }
  dcMem.m_hDC = (HDC__ *)CDC::`vftable';
  if ( dcMem.m_hAttribDC )
  {
    v26 = CDC::Detach((CDC *)&dcMem.m_hDC);
    DeleteDC(v26);
  }
}

```

## disassembly

```asm
0x1802b1200  mov     rax, rsp
0x1802b1203  mov     [rax+8], rbx
0x1802b1207  mov     [rax+10h], rsi
0x1802b120b  mov     [rax+18h], rdi
0x1802b120f  mov     [rax+20h], r13
0x1802b1213  push    rbp
0x1802b1214  push    r14
0x1802b1216  push    r15
0x1802b1218  lea     rbp, [rax-57h]
0x1802b121c  sub     rsp, 0E0h
0x1802b1223  mov     rbx, rSrc
0x1802b1226  mov     r15d, y
0x1802b1229  mov     r13d, x
0x1802b122c  mov     rsi, pDC
0x1802b122f  lea     rdi, ??_7CDC@@6B@; const CDC::`vftable'
0x1802b1236  mov     [rbp+4Fh+dcMem.m_hDC], rdi
0x1802b123a  xorps   xmm0, xmm0
0x1802b123d  movdqu  xmmword ptr [rbp+4Fh+dcMem.m_hAttribDC], xmm0
0x1802b1242  and     dword ptr [rbp+4Fh+bmpMask.__vftable], 0
0x1802b1246  mov     [rbp+4Fh+dcMask.m_hDC], rdi
0x1802b124a  movdqu  xmmword ptr [rbp+4Fh+dcMask.m_hAttribDC], xmm0
0x1802b124f  and     dword ptr [rbp+4Fh+dcMem.__vftable], 0
0x1802b1253  and     [rbp+4Fh+brShadow.__vftable], 0
0x1802b1258  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x1802b125f  mov     [rbp+4Fh+bmpMask.m_hObject], rax
0x1802b1263  mov     ecx, 14h; nIndex
0x1802b1268  call    cs:__imp_GetSysColor
0x1802b126e  mov     x, eax; crColor
0x1802b1270  lea     pDC, [rbp+4Fh+brHighLight.m_hObject]; this
0x1802b1274  call    ??0CBrush@@QEAA@K@Z; CBrush::CBrush(ulong)
0x1802b1279  nop
0x1802b127a  mov     ecx, 10h; nIndex
0x1802b127f  call    cs:__imp_GetSysColor
0x1802b1285  mov     x, eax; crColor
0x1802b1287  lea     pDC, [rbp+4Fh+brShadow.m_hObject]; this
0x1802b128b  call    ??0CBrush@@QEAA@K@Z; CBrush::CBrush(ulong)
0x1802b1290  nop
0x1802b1291  test    rsi, rsi
0x1802b1294  jnz     short loc_1802B129A
0x1802b1296  xor     ecx, ecx
0x1802b1298  jmp     short loc_1802B129E
0x1802b129a  mov     pDC, [rsi+8]; hdc
0x1802b129e  call    cs:__imp_CreateCompatibleDC
0x1802b12a4  mov     rdx, rax; hDC
0x1802b12a7  lea     pDC, [rbp+4Fh+dcMem.m_hDC]; this
0x1802b12ab  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x1802b12b0  test    eax, eax
0x1802b12b2  jz      loc_1802B14FA
0x1802b12b8  test    rsi, rsi
0x1802b12bb  jnz     short loc_1802B12C1
0x1802b12bd  xor     ecx, ecx
0x1802b12bf  jmp     short loc_1802B12C5
0x1802b12c1  mov     pDC, [rsi+8]; hdc
0x1802b12c5  call    cs:__imp_CreateCompatibleDC
0x1802b12cb  mov     rdx, rax; hDC
0x1802b12ce  lea     pDC, [rbp+4Fh+dcMask.m_hDC]; this
0x1802b12d2  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x1802b12d7  test    eax, eax
0x1802b12d9  jz      loc_1802B14FA
0x1802b12df  lea     r8, [rbp+4Fh+bm.bmHeight]; pv
0x1802b12e3  mov     x, 20h ; ' '; c
0x1802b12e8  mov     pDC, [rbx+8]; h
0x1802b12ec  call    cs:__imp_GetObjectW
0x1802b12f2  test    eax, eax
0x1802b12f4  jz      loc_1802B14FA
0x1802b12fa  and     qword ptr [rsp+0F0h+cy], 0
0x1802b1300  mov     y, 1; nPlanes
0x1802b1306  mov     r9d, y; nBitCount
0x1802b1309  mov     x, dword ptr [rbp+4Fh+bm.bmPlanes]; nHeight
0x1802b130c  mov     ecx, [rbp+4Fh+bm.bmWidthBytes]; nWidth
0x1802b130f  call    cs:__imp_CreateBitmap
0x1802b1315  mov     rdx, rax; hObject
0x1802b1318  lea     pDC, [rbp+4Fh+bmpMask.m_hObject]; this
0x1802b131c  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1802b1321  test    eax, eax
0x1802b1323  jz      loc_1802B14FA
0x1802b1329  mov     rdx, [rbx+8]; h
0x1802b132d  mov     pDC, [rbp+4Fh+dcMem.m_hAttribDC]; hdc
0x1802b1331  call    cs:__imp_SelectObject
0x1802b1337  mov     pDC, rax; h
0x1802b133a  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1802b133f  mov     rbx, rax
0x1802b1342  mov     rdx, [rbp+4Fh+brShadow.__vftable]; h
0x1802b1346  mov     pDC, [rbp+4Fh+dcMask.m_hAttribDC]; hdc
0x1802b134a  call    cs:__imp_SelectObject
0x1802b1350  mov     pDC, rax; h
0x1802b1353  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1802b1358  mov     r14, rax
0x1802b135b  test    rbx, rbx
0x1802b135e  jz      loc_1802B14FA
0x1802b1364  test    rax, rax
0x1802b1367  jz      loc_1802B14FA
0x1802b136d  xor     y, y; y
0x1802b1370  xor     x, x; x
0x1802b1372  mov     pDC, [rbp+4Fh+dcMem.m_hAttribDC]; hdc
0x1802b1376  call    cs:__imp_GetPixel
0x1802b137c  mov     x, eax; crColor
0x1802b137e  lea     pDC, [rbp+4Fh+dcMem.m_hDC]; this
0x1802b1382  call    ?SetBkColor@CDC@@UEAAKK@Z; CDC::SetBkColor(ulong)
0x1802b1387  mov     edi, eax
0x1802b1389  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x1802b1391  and     [rsp+0F0h+var_B8], 0
0x1802b1396  and     [rsp+0F0h+var_C0], 0
0x1802b139b  mov     pDC, [rbp+4Fh+dcMem.m_hAttribDC]
0x1802b139f  mov     [rsp+0F0h+hdcSrc], pDC; hdcSrc
0x1802b13a4  mov     ecx, dword ptr [rbp+4Fh+bm.bmPlanes]
0x1802b13a7  mov     [rsp+0F0h+cy], ecx; cy
0x1802b13ab  mov     r9d, [rbp+4Fh+bm.bmWidthBytes]; cx
0x1802b13af  xor     y, y; y
0x1802b13b2  xor     x, x; x
0x1802b13b4  mov     pDC, [rbp+4Fh+dcMask.m_hAttribDC]; hdc
0x1802b13b8  call    cs:__imp_BitBlt
0x1802b13be  mov     ebx, 0FFFFFFh
0x1802b13c3  mov     x, ebx; crColor
0x1802b13c5  lea     pDC, [rbp+4Fh+dcMem.m_hDC]; this
0x1802b13c9  call    ?SetBkColor@CDC@@UEAAKK@Z; CDC::SetBkColor(ulong)
0x1802b13ce  mov     [rsp+0F0h+rop], 1100A6h; rop
0x1802b13d6  and     [rsp+0F0h+var_B8], 0
0x1802b13db  and     [rsp+0F0h+var_C0], 0
0x1802b13e0  mov     rax, [rbp+4Fh+dcMem.m_hAttribDC]
0x1802b13e4  mov     [rsp+0F0h+hdcSrc], rax; hdcSrc
0x1802b13e9  mov     eax, dword ptr [rbp+4Fh+bm.bmPlanes]
0x1802b13ec  mov     [rsp+0F0h+cy], eax; cy
0x1802b13f0  mov     r9d, [rbp+4Fh+bm.bmWidthBytes]; cx
0x1802b13f4  xor     y, y; y
0x1802b13f7  xor     x, x; x
0x1802b13f9  mov     pDC, [rbp+4Fh+dcMask.m_hAttribDC]; hdc
0x1802b13fd  call    cs:__imp_BitBlt
0x1802b1403  mov     eax, [rbp+4Fh+clr]
0x1802b1406  mov     dword ptr [rsp+0F0h+hdcSrc], eax; clr
0x1802b140a  mov     eax, dword ptr [rbp+4Fh+bm.bmPlanes]
0x1802b140d  mov     [rsp+0F0h+cy], eax; cy
0x1802b1411  mov     r9d, [rbp+4Fh+bm.bmWidthBytes]; cx
0x1802b1415  mov     y, r15d; y
0x1802b1418  mov     x, r13d; x
0x1802b141b  mov     pDC, rsi; this
0x1802b141e  call    ?FillSolidRect@CDC@@QEAAXHHHHK@Z; CDC::FillSolidRect(int,int,int,int,ulong)
0x1802b1423  mov     rax, [rsi]
0x1802b1426  mov     x, ebx
0x1802b1428  mov     pDC, rsi
0x1802b142b  mov     rax, [rax+68h]
0x1802b142f  call    cs:__guard_dispatch_icall_fptr
0x1802b1435  lea     rdx, [rbp+4Fh+brHighLight.m_hObject]; pFont
0x1802b1439  mov     pDC, rsi; this
0x1802b143c  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x1802b1441  mov     rbx, rax
0x1802b1444  lea     y, [r15+1]; y
0x1802b1448  lea     x, [r13+1]; x
0x1802b144c  mov     [rsp+0F0h+rop], 0E20746h; rop
0x1802b1454  and     [rsp+0F0h+var_B8], 0
0x1802b1459  and     [rsp+0F0h+var_C0], 0
0x1802b145e  mov     rSrc, [rbp+4Fh+dcMask.m_hAttribDC]
0x1802b1462  mov     [rsp+0F0h+hdcSrc], rSrc; hdcSrc
0x1802b1467  mov     r9d, dword ptr [rbp+4Fh+bm.bmPlanes]
0x1802b146b  mov     [rsp+0F0h+cy], r9d; cy
0x1802b1470  mov     r9d, [rbp+4Fh+bm.bmWidthBytes]; cx
0x1802b1474  mov     pDC, [rsi+8]; hdc
0x1802b1478  call    cs:__imp_BitBlt
0x1802b147e  lea     rdx, [rbp+4Fh+brShadow.m_hObject]; pFont
0x1802b1482  mov     pDC, rsi; this
0x1802b1485  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x1802b148a  mov     [rsp+0F0h+rop], 0E20746h; rop
0x1802b1492  and     [rsp+0F0h+var_B8], 0
0x1802b1497  and     [rsp+0F0h+var_C0], 0
0x1802b149c  mov     rax, [rbp+4Fh+dcMask.m_hAttribDC]
0x1802b14a0  mov     [rsp+0F0h+hdcSrc], rax; hdcSrc
0x1802b14a5  mov     eax, dword ptr [rbp+4Fh+bm.bmPlanes]
0x1802b14a8  mov     [rsp+0F0h+cy], eax; cy
0x1802b14ac  mov     r9d, [rbp+4Fh+bm.bmWidthBytes]; cx
0x1802b14b0  mov     y, r15d; y
0x1802b14b3  mov     x, r13d; x
0x1802b14b6  mov     pDC, [rsi+8]; hdc
0x1802b14ba  call    cs:__imp_BitBlt
0x1802b14c0  mov     rdx, rbx; pFont
0x1802b14c3  mov     pDC, rsi; this
0x1802b14c6  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x1802b14cb  mov     rax, [rsi]
0x1802b14ce  mov     x, edi
0x1802b14d0  mov     pDC, rsi
0x1802b14d3  mov     rax, [rax+68h]
0x1802b14d7  call    cs:__guard_dispatch_icall_fptr
0x1802b14dd  mov     rdx, [r14+8]; h
0x1802b14e1  mov     pDC, [rbp+4Fh+dcMask.m_hAttribDC]; hdc
0x1802b14e5  call    cs:__imp_SelectObject
0x1802b14eb  mov     pDC, rax; h
0x1802b14ee  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1802b14f3  lea     rdi, ??_7CDC@@6B@; const CDC::`vftable'
0x1802b14fa  lea     rbx, ??_7CBrush@@6B@; const CBrush::`vftable'
0x1802b1501  mov     [rbp+4Fh+brShadow.m_hObject], rbx
0x1802b1505  lea     pDC, [rbp+4Fh+brShadow.m_hObject]; this
0x1802b1509  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1802b150e  nop
0x1802b150f  mov     [rbp+4Fh+brHighLight.m_hObject], rbx
0x1802b1513  lea     pDC, [rbp+4Fh+brHighLight.m_hObject]; this
0x1802b1517  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1802b151c  nop
0x1802b151d  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x1802b1524  mov     [rbp+4Fh+bmpMask.m_hObject], rax
0x1802b1528  lea     pDC, [rbp+4Fh+bmpMask.m_hObject]; this
0x1802b152c  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1802b1531  nop
0x1802b1532  mov     [rbp+4Fh+dcMask.m_hDC], rdi
0x1802b1536  cmp     [rbp+4Fh+dcMask.m_hAttribDC], 0
0x1802b153b  jz      short loc_1802B1550
0x1802b153d  lea     pDC, [rbp+4Fh+dcMask.m_hDC]; this
0x1802b1541  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1802b1546  mov     pDC, rax; hdc
0x1802b1549  call    cs:__imp_DeleteDC
0x1802b154f  nop
0x1802b1550  mov     [rbp+4Fh+dcMem.m_hDC], rdi
0x1802b1554  cmp     [rbp+4Fh+dcMem.m_hAttribDC], 0
0x1802b1559  jz      short loc_1802B156E
0x1802b155b  lea     pDC, [rbp+4Fh+dcMem.m_hDC]; this
0x1802b155f  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1802b1564  mov     pDC, rax; hdc
0x1802b1567  call    cs:__imp_DeleteDC
0x1802b156d  nop
0x1802b156e  lea     r11, [rsp+0F0h+var_10]
0x1802b1576  mov     rbx, [r11+20h]
0x1802b157a  mov     rsi, [r11+28h]
0x1802b157e  mov     rdi, [r11+30h]
0x1802b1582  mov     r13, [r11+38h]
0x1802b1586  mov     rsp, r11
0x1802b1589  pop     r15
0x1802b158b  pop     r14
0x1802b158d  pop     rbp
0x1802b158e  retn
```
