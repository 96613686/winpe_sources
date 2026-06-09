# CDrawingManager::HighlightRect(CRect,int,ulong,int,ulong)

- ea: `0x1800584a0`
- end: `0x180058b1e`
- name: `?HighlightRect@CDrawingManager@@QEAAHVCRect@@HKHK@Z`
- size: `1662`
- prototype: `int __fastcall(CDrawingManager *this, CRect rect, int nPercentage, unsigned int clrTransparent, int nTolerance, unsigned int clrBlend)`
- caller_count: `12`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18001d800`
- `0x18009d3e0`
- `0x18018c410`
- `0x18018c670`
- `0x1801914a0`
- `0x180193cf0`
- `0x180194340`
- `0x180194a80`
- `0x180194dc0`
- `0x1801b93b0`
- `0x1801bb630`
- `0x1801c19a0`

## callees

- `0x18001d090`
- `0x180058150`
- `0x1800584a0`
- `0x18005d270`
- `0x18006cab0`
- `0x180174720`
- `0x180231d70`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802b09a0`
- `0x1802b09d0`

## import_xrefs

- `KERNEL32!MulDiv` at `0x180058934`
- `KERNEL32!MulDiv` at `0x180058952`
- `KERNEL32!MulDiv` at `0x180058973`
- `KERNEL32!MulDiv` at `0x180058991`
- `KERNEL32!MulDiv` at `0x1800589af`
- `KERNEL32!MulDiv` at `0x1800589cf`
- `KERNEL32!MulDiv` at `0x180058934`
- `KERNEL32!MulDiv` at `0x180058952`
- `KERNEL32!MulDiv` at `0x180058973`
- `KERNEL32!MulDiv` at `0x180058991`
- `KERNEL32!MulDiv` at `0x1800589af`
- `KERNEL32!MulDiv` at `0x1800589cf`
- `api-ms-win-crt-utility-l1-1-0!abs` at `0x1800586f2`
- `api-ms-win-crt-utility-l1-1-0!abs` at `0x18005870c`
- `api-ms-win-crt-utility-l1-1-0!abs` at `0x18005872a`
- `api-ms-win-crt-utility-l1-1-0!abs` at `0x1800586f2`
- `api-ms-win-crt-utility-l1-1-0!abs` at `0x18005870c`
- `api-ms-win-crt-utility-l1-1-0!abs` at `0x18005872a`
- `GDI32!DeleteDC` at `0x180058ab5`
- `GDI32!DeleteDC` at `0x180058af3`
- `GDI32!DeleteDC` at `0x180058ab5`
- `GDI32!DeleteDC` at `0x180058af3`
- `GDI32!BitBlt` at `0x18005868f`
- `GDI32!BitBlt` at `0x180058a57`
- `GDI32!BitBlt` at `0x18005868f`
- `GDI32!BitBlt` at `0x180058a57`
- `GDI32!CreateCompatibleBitmap` at `0x1800585bf`
- `GDI32!CreateCompatibleBitmap` at `0x1800585bf`
- `GDI32!DeleteObject` at `0x180058a7b`
- `GDI32!DeleteObject` at `0x180058a7b`
- `GDI32!SelectObject` at `0x1800585f7`
- `GDI32!SelectObject` at `0x18005864b`
- `GDI32!SelectObject` at `0x180058a69`
- `GDI32!SelectObject` at `0x1800585f7`
- `GDI32!SelectObject` at `0x18005864b`
- `GDI32!SelectObject` at `0x180058a69`
- `GDI32!CreateCompatibleDC` at `0x180058588`
- `GDI32!CreateCompatibleDC` at `0x180058588`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDrawingManager::HighlightRect(
        CDrawingManager *this,
        CRect *rect,
        int nPercentage,
        unsigned int clrTransparent,
        int nTolerance,
        unsigned int clrBlend)
{
  int v6; // r14d
  CRect *v8; // rdi
  CDrawingManager *v9; // r13
  HDC__ *v10; // r12
  int v12; // esi
  int cy; // r15d
  CDC *m_dc; // rcx
  HDC m_hDC; // rcx
  HDC CompatibleDC; // rax
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v18; // rax
  HBITMAP__ *v19; // rax
  CDC *v20; // rcx
  HDC hdcSrc; // rax
  int v22; // edi
  unsigned int v23; // esi
  BOOL v24; // eax
  int m_bInitialized; // r8d
  int v26; // r14d
  unsigned __int8 v27; // r9
  unsigned int v28; // r15d
  int v29; // r14d
  unsigned int v30; // r14d
  int v31; // esi
  unsigned int v32; // edx
  unsigned int v33; // ecx
  int v34; // eax
  int v35; // r14d
  int v36; // r15d
  int v37; // r13d
  int v38; // esi
  unsigned __int8 v39; // r12
  unsigned __int8 v40; // r14
  unsigned __int8 v41; // al
  HGDIOBJ v42; // rax
  HDC v43; // rax
  HDC v44; // rax
  unsigned int v45; // [rsp+50h] [rbp-79h]
  CSize size; // [rsp+58h] [rbp-71h] BYREF
  CDC dcMem; // [rsp+60h] [rbp-69h] BYREF
  unsigned int *pBits; // [rsp+80h] [rbp-49h] BYREF
  CBitmap bmpMem; // [rsp+88h] [rbp-41h] BYREF
  int nNumerator; // [rsp+98h] [rbp-31h]
  int v51; // [rsp+9Ch] [rbp-2Dh]
  int v52; // [rsp+A0h] [rbp-29h]
  CRect *v53; // [rsp+A8h] [rbp-21h]
  CDrawingManager *v54; // [rsp+B0h] [rbp-19h]
  CGdiObject *v55; // [rsp+B8h] [rbp-11h]
  HGDIOBJ ho; // [rsp+C0h] [rbp-9h]

  v6 = clrTransparent;
  v45 = clrTransparent;
  nNumerator = nPercentage;
  v8 = rect;
  v53 = rect;
  v9 = this;
  v54 = this;
  if ( nPercentage != 100 )
  {
    v10 = 0;
    if ( rect->bottom - rect->top > 0 && rect->right - rect->left > 0 )
    {
      if ( !afxGlobalData.m_bInitialized )
      {
        AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
        afxGlobalData.m_bInitialized = 1;
      }
      if ( afxGlobalData.m_nBitsPerPixel <= 8 )
      {
        CMFCToolBarImages::FillDitheredRect(v9->m_dc, v8);
        return 1;
      }
      if ( clrBlend != -1 && nPercentage > 100 )
        return 0;
      v12 = v8->right - v8->left;
      v51 = v12;
      cy = v8->bottom - v8->top;
      v52 = cy;
      dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
      memset(&dcMem.m_hDC, 0, 20);
      m_dc = v9->m_dc;
      if ( m_dc )
        m_hDC = m_dc->m_hDC;
      else
        m_hDC = 0;
      CompatibleDC = CreateCompatibleDC(m_hDC);
      if ( CDC::Attach(&dcMem, CompatibleDC) )
      {
        bmpMem.m_hObject = 0;
        bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
        CompatibleBitmap = CreateCompatibleBitmap(v9->m_dc->m_hDC, v12, cy);
        if ( !CGdiObject::Attach(&bmpMem, CompatibleBitmap) )
        {
          bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
          CGdiObject::~CGdiObject(&bmpMem);
          goto LABEL_71;
        }
        v18 = SelectObject(dcMem.m_hDC, bmpMem.m_hObject);
        v55 = CGdiObject::FromHandle(v18);
        if ( !v55 )
          AfxThrowInvalidArgException();
        size.cx = v12;
        size.cy = cy;
        v19 = CDrawingManager::CreateBitmap_32(&size, (void **)&pBits);
        ho = v19;
        if ( v19 )
        {
          v10 = (HDC__ *)pBits;
          size = (CSize)pBits;
          if ( pBits )
          {
            SelectObject(dcMem.m_hDC, v19);
            v20 = v9->m_dc;
            if ( v20 )
              hdcSrc = v20->m_hDC;
            else
              hdcSrc = 0;
            BitBlt(dcMem.m_hDC, 0, 0, v12, cy, hdcSrc, v8->left, v8->top, 0xCC0020u);
            if ( v6 != -1 )
            {
              v6 = ((unsigned __int8)v6 << 16) | BYTE2(v6) | v6 & 0xFF00;
              v45 = v6;
            }
            if ( v12 * cy <= 0 )
            {
LABEL_67:
              BitBlt(v9->m_dc->m_hDC, v8->left, v8->top, v12, cy, dcMem.m_hDC, 0, 0, 0xCC0020u);
              v42 = SelectObject(dcMem.m_hDC, v55->m_hObject);
              CGdiObject::FromHandle(v42);
              DeleteObject(ho);
              bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
              CGdiObject::~CGdiObject(&bmpMem);
              dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
              if ( dcMem.m_hDC )
              {
                v43 = CDC::Detach(&dcMem);
                DeleteDC(v43);
              }
              return 1;
            }
            pBits = (unsigned int *)(unsigned int)(v12 * cy);
            v22 = nNumerator;
            while ( 1 )
            {
              v23 = *(_DWORD *)v10;
              if ( nTolerance <= 0 )
              {
                v24 = v23 == v6;
              }
              else
              {
                if ( abs((unsigned __int8)v23 - (unsigned __int8)v6) < nTolerance
                  && abs(BYTE1(v23) - BYTE1(v6)) < nTolerance
                  && abs(BYTE2(v23) - BYTE2(v6)) < nTolerance )
                {
                  goto LABEL_65;
                }
                v24 = 0;
              }
              if ( !v24 )
              {
                if ( v22 == -1 )
                {
                  m_bInitialized = afxGlobalData.m_bInitialized;
                  if ( !afxGlobalData.m_bInitialized )
                  {
                    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
                    m_bInitialized = 1;
                    afxGlobalData.m_bInitialized = 1;
                  }
                  v26 = 2 * (unsigned __int8)v23;
                  v27 = BYTE2(afxGlobalData.clrBtnHilite);
                  if ( (int)((v26 + (unsigned int)BYTE2(afxGlobalData.clrBtnHilite)) / 3) <= 255 )
                  {
                    if ( !m_bInitialized )
                    {
                      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
                      m_bInitialized = 1;
                      afxGlobalData.m_bInitialized = 1;
                      v27 = BYTE2(afxGlobalData.clrBtnHilite);
                    }
                    v28 = (v26 + (unsigned int)v27) / 3;
                  }
                  else
                  {
                    LOBYTE(v28) = -1;
                  }
                  if ( !m_bInitialized )
                  {
                    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
                    afxGlobalData.m_bInitialized = 1;
                  }
                  v29 = 2 * BYTE1(v23);
                  if ( (int)((v29 + (unsigned int)BYTE1(afxGlobalData.clrBtnHilite)) / 3) <= 255 )
                    v30 = (v29 + (unsigned int)BYTE1(afxGlobalData.clrBtnHilite)) / 3;
                  else
                    LOBYTE(v30) = -1;
                  v31 = 2 * BYTE2(v23);
                  if ( (int)((v31 + (unsigned int)LOBYTE(afxGlobalData.clrBtnHilite)) / 3) <= 255 )
                    v32 = (v31 + (unsigned int)LOBYTE(afxGlobalData.clrBtnHilite)) / 3;
                  else
                    LOBYTE(v32) = -1;
                  v33 = ((v32 | 0xFFFFFF00) << 16) | ((unsigned __int8)v30 << 8);
                  v34 = (unsigned __int8)v28;
                  goto LABEL_64;
                }
                if ( clrBlend != -1 )
                {
                  v35 = (unsigned __int8)v23;
                  v36 = BYTE1(v23);
                  v37 = BYTE2(v23);
                  v38 = BYTE2(clrBlend) - (unsigned __int8)v23;
                  if ( v35 + MulDiv(v38, v22, 100) <= 255 )
                    v39 = v35 + MulDiv(v38, v22, 100);
                  else
                    v39 = -1;
                  if ( v36 + MulDiv(BYTE1(clrBlend) - v36, v22, 100) <= 255 )
                    v40 = v36 + MulDiv(BYTE1(clrBlend) - v36, v22, 100);
                  else
                    v40 = -1;
                  if ( v37 + MulDiv((unsigned __int8)clrBlend - v37, v22, 100) <= 255 )
                    v41 = v37 + MulDiv((unsigned __int8)clrBlend - v37, v22, 100);
                  else
                    v41 = -1;
                  v33 = (v40 << 8) | ((v41 | 0xFFFFFF00) << 16);
                  v34 = v39;
                  v10 = (HDC__ *)size;
LABEL_64:
                  v6 = v45;
                  *(_DWORD *)v10 = v34 | v33;
                  goto LABEL_65;
                }
                *(_DWORD *)v10 = CDrawingManager::PixelAlpha(
                                   v23,
                                   (double)v22 * 0.01,
                                   (double)v22 * 0.01,
                                   (double)v22 * 0.01)
                               | 0xFF000000;
              }
LABEL_65:
              size = (CSize)++v10;
              pBits = (unsigned int *)((char *)pBits - 1);
              if ( !pBits )
              {
                v8 = v53;
                v12 = v51;
                cy = v52;
                v9 = v54;
                goto LABEL_67;
              }
            }
          }
        }
        bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
        CGdiObject::~CGdiObject(&bmpMem);
      }
LABEL_71:
      dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
      if ( dcMem.m_hDC != v10 )
      {
        v44 = CDC::Detach(&dcMem);
        DeleteDC(v44);
      }
      return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800584a0  push    rbp
0x1800584a2  push    rbx
0x1800584a3  push    rsi
0x1800584a4  push    rdi
0x1800584a5  push    r12
0x1800584a7  push    r13
0x1800584a9  push    r14
0x1800584ab  push    r15
0x1800584ad  lea     rbp, [rsp-0Fh]
0x1800584b2  sub     rsp, 0D8h
0x1800584b9  mov     r14d, clrTransparent
0x1800584bc  mov     [rbp+47h+var_C0], clrTransparent
0x1800584c0  mov     esi, nPercentage
0x1800584c3  mov     [rbp+47h+nNumerator], nPercentage
0x1800584c7  mov     rdi, rect
0x1800584ca  mov     [rbp+47h+var_68], rect
0x1800584ce  mov     r13, this
0x1800584d1  mov     [rbp+47h+var_60], this
0x1800584d5  cmp     nPercentage, 64h ; 'd'
0x1800584d9  jz      loc_180058AFF
0x1800584df  mov     eax, [rect+0Ch]
0x1800584e2  sub     eax, [rect+4]
0x1800584e5  xor     r12d, r12d
0x1800584e8  test    eax, eax
0x1800584ea  jle     loc_180058AFF
0x1800584f0  mov     eax, [rect+8]
0x1800584f3  sub     eax, [rect]
0x1800584f5  test    eax, eax
0x1800584f7  jle     loc_180058AFF
0x1800584fd  lea     ebx, [r12+1]
0x180058502  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r12d; AFX_GLOBAL_DATA afxGlobalData ...
0x180058509  jnz     short loc_18005851D
0x18005850b  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180058512  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x180058517  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, ebx; AFX_GLOBAL_DATA afxGlobalData ...
0x18005851d  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_nBitsPerPixel, 8; AFX_GLOBAL_DATA afxGlobalData ...
0x180058524  jg      short loc_180058539
0x180058526  mov     rect, rdi; rect
0x180058529  mov     this, [r13+8]; pDC
0x18005852d  call    ?FillDitheredRect@CMFCToolBarImages@@SAXPEAVCDC@@AEBVCRect@@@Z; CMFCToolBarImages::FillDitheredRect(CDC *,CRect const &)
0x180058532  mov     eax, ebx
0x180058534  jmp     loc_180058B04
0x180058539  cmp     [rbp+47h+arg_28], 0FFFFFFFFh
0x18005853d  jz      short loc_18005854B
0x18005853f  cmp     esi, 64h ; 'd'
0x180058542  jle     short loc_18005854B
0x180058544  xor     eax, eax
0x180058546  jmp     loc_180058B04
0x18005854b  mov     esi, [rdi+8]
0x18005854e  sub     esi, [rdi]
0x180058550  mov     [rbp+47h+var_74], esi
0x180058553  mov     r15d, [rdi+0Ch]
0x180058557  sub     r15d, [rdi+4]
0x18005855b  mov     [rbp+47h+var_70], r15d
0x18005855f  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x180058566  mov     [rbp+47h+dcMem.__vftable], rax
0x18005856a  xorps   xmm0, xmm0
0x18005856d  movdqu  xmmword ptr [rbp+47h+dcMem.m_hDC], xmm0
0x180058572  mov     [rbp+47h+dcMem.m_bPrinting], r12d
0x180058576  mov     this, [r13+8]
0x18005857a  test    this, this
0x18005857d  jnz     short loc_180058584
0x18005857f  mov     this, r12
0x180058582  jmp     short loc_180058588
0x180058584  mov     this, [this+8]; hdc
0x180058588  call    cs:__imp_CreateCompatibleDC
0x18005858e  mov     rect, rax; hDC
0x180058591  lea     this, [rbp+47h+dcMem]; this
0x180058595  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x18005859a  test    eax, eax
0x18005859c  jnz     short loc_1800585A3
0x18005859e  jmp     loc_180058AD6
0x1800585a3  mov     [rbp+47h+bmpMem.m_hObject], r12
0x1800585a7  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x1800585ae  mov     [rbp+47h+bmpMem.__vftable], rax
0x1800585b2  mov     this, [r13+8]
0x1800585b6  mov     nPercentage, r15d; cy
0x1800585b9  mov     edx, esi; cx
0x1800585bb  mov     this, [this+8]; hdc
0x1800585bf  call    cs:__imp_CreateCompatibleBitmap
0x1800585c5  mov     rect, rax; hObject
0x1800585c8  lea     this, [rbp+47h+bmpMem]; this
0x1800585cc  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1800585d1  test    eax, eax
0x1800585d3  jnz     short loc_1800585EF
0x1800585d5  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x1800585dc  mov     [rbp+47h+bmpMem.__vftable], rax
0x1800585e0  lea     this, [rbp+47h+bmpMem]; this
0x1800585e4  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1800585e9  nop
0x1800585ea  jmp     loc_180058AD6
0x1800585ef  mov     rect, [rbp+47h+bmpMem.m_hObject]; h
0x1800585f3  mov     this, [rbp+47h+dcMem.m_hDC]; hdc
0x1800585f7  call    cs:__imp_SelectObject
0x1800585fd  mov     this, rax; h
0x180058600  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x180058605  mov     [rbp+47h+var_58], rax
0x180058609  test    rax, rax
0x18005860c  jz      loc_180058B18
0x180058612  mov     [rbp+47h+size.cx], esi
0x180058615  mov     [rbp+47h+size.cy], r15d
0x180058619  lea     rect, [rbp+47h+pBits]; pBits
0x18005861d  lea     this, [rbp+47h+size]; size
0x180058621  call    ?CreateBitmap_32@CDrawingManager@@SAPEAUHBITMAP__@@AEBVCSize@@PEAPEAX@Z; CDrawingManager::CreateBitmap_32(CSize const &,void * *)
0x180058626  mov     [rbp+47h+ho], rax
0x18005862a  test    rax, rax
0x18005862d  jz      loc_180058AC1
0x180058633  mov     r12, [rbp+47h+pBits]
0x180058637  mov     qword ptr [rbp+47h+size.cx], r12
0x18005863b  test    r12, r12
0x18005863e  jz      loc_180058AC1
0x180058644  mov     rect, rax; h
0x180058647  mov     this, [rbp+47h+dcMem.m_hDC]; hdc
0x18005864b  call    cs:__imp_SelectObject
0x180058651  mov     edx, [rdi+4]
0x180058654  mov     nPercentage, [rdi]
0x180058657  mov     this, [r13+8]
0x18005865b  test    this, this
0x18005865e  jnz     short loc_180058664
0x180058660  xor     eax, eax
0x180058662  jmp     short loc_180058668
0x180058664  mov     rax, [this+8]
0x180058668  mov     [rsp+110h+rop], 0CC0020h; rop
0x180058670  mov     [rsp+110h+y1], edx; y1
0x180058674  mov     [rsp+110h+x1], nPercentage; x1
0x180058679  mov     [rsp+110h+hdcSrc], rax; hdcSrc
0x18005867e  mov     [rsp+110h+cy], r15d; cy
0x180058683  mov     clrTransparent, esi; cx
0x180058686  xor     nPercentage, nPercentage; y
0x180058689  xor     edx, edx; x
0x18005868b  mov     this, [rbp+47h+dcMem.m_hDC]; hdc
0x18005868f  call    cs:__imp_BitBlt
0x180058695  cmp     r14d, 0FFFFFFFFh
0x180058699  jz      short loc_1800586C1
0x18005869b  movzx   edx, r14w
0x18005869f  and     edx, 0FFFFFF00h
0x1800586a5  mov     eax, r14d
0x1800586a8  shr     eax, 10h
0x1800586ab  movzx   ecx, al
0x1800586ae  or      edx, ecx
0x1800586b0  movzx   eax, r14b
0x1800586b4  shl     eax, 10h
0x1800586b7  mov     r14d, edx
0x1800586ba  or      r14d, eax
0x1800586bd  mov     [rbp+47h+var_C0], r14d
0x1800586c1  mov     eax, r15d
0x1800586c4  imul    eax, esi
0x1800586c7  test    eax, eax
0x1800586c9  jle     loc_180058A26
0x1800586cf  mov     ecx, eax
0x1800586d1  mov     [rbp+47h+pBits], this
0x1800586d5  mov     r13d, 0FFh
0x1800586db  mov     edi, [rbp+47h+nNumerator]
0x1800586de  mov     esi, [r12]
0x1800586e2  cmp     [rbp+47h+arg_20], 0
0x1800586e6  jle     short loc_18005873D
0x1800586e8  movzx   eax, r14b
0x1800586ec  movzx   ecx, sil
0x1800586f0  sub     ecx, eax; Number
0x1800586f2  call    cs:__imp_abs
0x1800586f8  cmp     eax, [rbp+47h+arg_20]
0x1800586fb  jge     short loc_180058739
0x1800586fd  movzx   eax, r14w
0x180058701  shr     eax, 8
0x180058704  movzx   ecx, si
0x180058707  shr     ecx, 8
0x18005870a  sub     ecx, eax; Number
0x18005870c  call    cs:__imp_abs
0x180058712  cmp     eax, [rbp+47h+arg_20]
0x180058715  jge     short loc_180058739
0x180058717  mov     eax, r14d
0x18005871a  shr     eax, 10h
0x18005871d  movzx   edx, al
0x180058720  mov     eax, esi
0x180058722  shr     eax, 10h
0x180058725  movzx   ecx, al
0x180058728  sub     ecx, edx; Number
0x18005872a  call    cs:__imp_abs
0x180058730  cmp     eax, [rbp+47h+arg_20]
0x180058733  jl      loc_180058A05
0x180058739  xor     eax, eax
0x18005873b  jmp     short loc_180058745
0x18005873d  xor     eax, eax
0x18005873f  cmp     esi, r14d
0x180058742  setz    al
0x180058745  test    eax, eax
0x180058747  jnz     loc_180058A05
0x18005874d  cmp     edi, 0FFFFFFFFh
0x180058750  jnz     loc_1800588D7
0x180058756  mov     nPercentage, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized; AFX_GLOBAL_DATA afxGlobalData ...
0x18005875d  test    nPercentage, nPercentage
0x180058760  jnz     short loc_180058777
0x180058762  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180058769  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18005876e  mov     nPercentage, ebx
0x180058771  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, ebx; AFX_GLOBAL_DATA afxGlobalData ...
0x180058777  movzx   r14d, sil
0x18005877b  add     r14d, r14d
0x18005877e  movzx   clrTransparent, byte ptr cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrBtnHilite+2; AFX_GLOBAL_DATA afxGlobalData ...
0x180058786  lea     ecx, [r14+r9]
0x18005878a  mov     eax, 0AAAAAAABh
0x18005878f  mul     ecx
0x180058791  shr     edx, 1
0x180058793  cmp     edx, r13d
0x180058796  jle     short loc_18005879D
0x180058798  mov     r15d, r13d
0x18005879b  jmp     short loc_1800587D2
0x18005879d  test    nPercentage, nPercentage
0x1800587a0  jnz     short loc_1800587BE
0x1800587a2  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x1800587a9  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1800587ae  mov     nPercentage, ebx
0x1800587b1  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, ebx; AFX_GLOBAL_DATA afxGlobalData ...
0x1800587b7  mov     r9b, byte ptr cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrBtnHilite+2; AFX_GLOBAL_DATA afxGlobalData ...
0x1800587be  movzx   ecx, r9b
0x1800587c2  add     ecx, r14d
0x1800587c5  mov     eax, 0AAAAAAABh
0x1800587ca  mul     ecx
0x1800587cc  mov     r15d, edx
0x1800587cf  shr     r15d, 1
0x1800587d2  test    nPercentage, nPercentage
0x1800587d5  jnz     short loc_1800587EC
0x1800587d7  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x1800587de  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1800587e3  mov     nPercentage, ebx
0x1800587e6  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, ebx; AFX_GLOBAL_DATA afxGlobalData ...
0x1800587ec  movzx   r14d, si
0x1800587f0  shr     r14d, 8
0x1800587f4  add     r14d, r14d
0x1800587f7  movzx   clrTransparent, byte ptr cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrBtnHilite+1; AFX_GLOBAL_DATA afxGlobalData ...
0x1800587ff  lea     ecx, [r14+r9]
0x180058803  mov     eax, 0AAAAAAABh
0x180058808  mul     ecx
0x18005880a  shr     edx, 1
0x18005880c  cmp     edx, r13d
0x18005880f  jle     short loc_180058816
0x180058811  mov     r14d, r13d
0x180058814  jmp     short loc_18005884B
0x180058816  test    nPercentage, nPercentage
0x180058819  jnz     short loc_180058837
0x18005881b  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180058822  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x180058827  mov     nPercentage, ebx
0x18005882a  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, ebx; AFX_GLOBAL_DATA afxGlobalData ...
0x180058830  mov     r9b, byte ptr cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrBtnHilite+1; AFX_GLOBAL_DATA afxGlobalData ...
0x180058837  movzx   ecx, r9b
0x18005883b  add     ecx, r14d
0x18005883e  mov     eax, 0AAAAAAABh
0x180058843  mul     ecx
0x180058845  mov     r14d, edx
0x180058848  shr     r14d, 1
0x18005884b  test    nPercentage, nPercentage
0x18005884e  jnz     short loc_180058865
0x180058850  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180058857  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18005885c  mov     nPercentage, ebx
0x18005885f  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, ebx; AFX_GLOBAL_DATA afxGlobalData ...
0x180058865  shr     esi, 10h
0x180058868  movzx   esi, sil
0x18005886c  add     esi, esi
0x18005886e  movzx   clrTransparent, byte ptr cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrBtnHilite; AFX_GLOBAL_DATA afxGlobalData ...
0x180058876  lea     ecx, [rsi+r9]
0x18005887a  mov     eax, 0AAAAAAABh
0x18005887f  mul     ecx
0x180058881  shr     edx, 1
0x180058883  cmp     edx, r13d
0x180058886  jle     short loc_18005888D
0x180058888  mov     edx, r13d
0x18005888b  jmp     short loc_1800588BA
0x18005888d  test    nPercentage, nPercentage
0x180058890  jnz     short loc_1800588AB
0x180058892  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180058899  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18005889e  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, ebx; AFX_GLOBAL_DATA afxGlobalData ...
0x1800588a4  mov     r9b, byte ptr cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrBtnHilite; AFX_GLOBAL_DATA afxGlobalData ...
0x1800588ab  movzx   ecx, r9b
0x1800588af  add     ecx, esi
0x1800588b1  mov     eax, 0AAAAAAABh
0x1800588b6  mul     ecx
0x1800588b8  shr     edx, 1
0x1800588ba  movzx   ecx, r14b
0x1800588be  shl     ecx, 8
0x1800588c1  movzx   eax, dl
0x1800588c4  or      eax, 0FFFFFF00h
0x1800588c9  shl     eax, 10h
0x1800588cc  or      ecx, eax
0x1800588ce  movzx   eax, r15b
0x1800588d2  jmp     loc_1800589FB
0x1800588d7  cmp     [rbp+47h+arg_28], 0FFFFFFFFh
0x1800588db  jnz     short loc_180058908
0x1800588dd  movd    xmm1, edi
0x1800588e1  cvtdq2pd xmm1, xmm1
0x1800588e5  mulsd   xmm1, cs:__real@3f847ae147ae147b; percentR
0x1800588ed  movaps  xmm3, xmm1; percentB
0x1800588f0  movaps  xmm2, xmm1; percentG
0x1800588f3  mov     ecx, esi; srcPixel
0x1800588f5  call    ?PixelAlpha@CDrawingManager@@SAKKNNN@Z; CDrawingManager::PixelAlpha(ulong,double,double,double)
0x1800588fa  or      eax, 0FF000000h
0x1800588ff  mov     [r12], eax
0x180058903  jmp     loc_180058A05
  ... truncated ...
```
