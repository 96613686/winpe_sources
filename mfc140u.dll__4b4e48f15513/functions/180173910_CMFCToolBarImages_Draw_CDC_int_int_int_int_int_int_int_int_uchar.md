# CMFCToolBarImages::Draw(CDC *,int,int,int,int,int,int,int,int,uchar)

- ea: `0x180173910`
- end: `0x1801742c9`
- name: `?Draw@CMFCToolBarImages@@QEAAHPEAVCDC@@HHHHHHHHE@Z`
- size: `2489`
- prototype: `int __fastcall(CMFCToolBarImages *this, CDC *pDCDest, int xDest, int yDest, int iImage, int bHilite, int bDisabled, int bIndeterminate, int bShadow, int bInactive, unsigned __int8 alphaSrc)`
- caller_count: `18`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001d920`
- `0x180021980`
- `0x180092000`
- `0x18009c9c0`
- `0x18009d3e0`
- `0x1800ebd20`
- `0x1800ef160`
- `0x1800f33b0`
- `0x180118810`
- `0x18012dd80`
- `0x180135e00`
- `0x1801635a0`
- `0x1801647c0`
- `0x1801660c0`
- `0x180166f70`
- `0x1801742d0`
- `0x180176330`
- `0x18017b650`

## callees

- `0x180009844`
- `0x18001d090`
- `0x180058f20`
- `0x18006cab0`
- `0x1801735a0`
- `0x180173910`
- `0x180176b80`
- `0x1802aee30`
- `0x1802aee60`
- `0x1802aef40`
- `0x1802af110`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802b0b50`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!FillRect` at `0x180173cce`
- `USER32!FillRect` at `0x180173d10`
- `USER32!FillRect` at `0x180173cce`
- `USER32!FillRect` at `0x180173d10`
- `USER32!IsRectEmpty` at `0x180173a5c`
- `USER32!IsRectEmpty` at `0x180173a7b`
- `USER32!IsRectEmpty` at `0x180173a5c`
- `USER32!IsRectEmpty` at `0x180173a7b`
- `GDI32!CreateDIBSection` at `0x180173b7f`
- `GDI32!CreateDIBSection` at `0x180173b7f`
- `GDI32!BitBlt` at `0x180173c2e`
- `GDI32!BitBlt` at `0x180173f10`
- `GDI32!BitBlt` at `0x180174096`
- `GDI32!BitBlt` at `0x18017411b`
- `GDI32!BitBlt` at `0x1801741f2`
- `GDI32!BitBlt` at `0x180173c2e`
- `GDI32!BitBlt` at `0x180173f10`
- `GDI32!BitBlt` at `0x180174096`
- `GDI32!BitBlt` at `0x18017411b`
- `GDI32!BitBlt` at `0x1801741f2`
- `GDI32!GetPixel` at `0x180173d58`
- `GDI32!GetPixel` at `0x180173d58`
- `GDI32!SelectObject` at `0x180173bdd`
- `GDI32!SelectObject` at `0x180173e25`
- `GDI32!SelectObject` at `0x18017404a`
- `GDI32!SelectObject` at `0x1801740a3`
- `GDI32!SelectObject` at `0x1801740d5`
- `GDI32!SelectObject` at `0x180174128`
- `GDI32!SelectObject` at `0x180173bdd`
- `GDI32!SelectObject` at `0x180173e25`
- `GDI32!SelectObject` at `0x18017404a`
- `GDI32!SelectObject` at `0x1801740a3`
- `GDI32!SelectObject` at `0x1801740d5`
- `GDI32!SelectObject` at `0x180174128`
- `GDI32!CreateCompatibleDC` at `0x180173bc3`
- `GDI32!CreateCompatibleDC` at `0x180173bc3`
- `MSIMG32!AlphaBlend` at `0x180173e08`
- `MSIMG32!AlphaBlend` at `0x180173eba`
- `MSIMG32!AlphaBlend` at `0x180173e08`
- `MSIMG32!AlphaBlend` at `0x180173eba`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMFCToolBarImages::Draw(
        CMFCToolBarImages *this,
        CDC *pDCDest,
        unsigned int xDest,
        unsigned int yDest,
        int iImage,
        int bHilite,
        int bDisabled,
        int bIndeterminate,
        int bShadow,
        int bInactive,
        unsigned __int8 alphaSrc)
{
  CSize m_sizeImageDest; // rax
  int m_bStretch; // ecx
  int v15; // eax
  int v16; // eax
  int v17; // eax
  unsigned int m_clrTransparent; // r15d
  CDC *p_m_dcMem; // rsi
  int cx; // r12d
  int cy; // r13d
  int v22; // ebx
  int v23; // edx
  __int64 v25; // rbx
  int v26; // r12d
  HBITMAP v27; // rax
  HDC CompatibleDC; // rax
  HGDIOBJ v29; // rax
  unsigned int v30; // eax
  __int64 v31; // rcx
  unsigned int *v32; // rax
  CSize m_sizeImage; // rax
  int m_bInitialized; // eax
  int v35; // ecx
  __int64 v36; // r8
  unsigned int *v37; // rax
  BOOL v38; // ebx
  void *m_hObject; // rdx
  HGDIOBJ v40; // rax
  int v41; // r12d
  CDC *v42; // rax
  HDC hdcSrc; // rcx
  CMFCVisualManager *Instance; // rax
  unsigned int v45; // ebx
  unsigned int clrBtnFace; // r9d
  HGDIOBJ v47; // rbx
  HGDIOBJ v48; // rbx
  CFont *v49; // rbx
  int v50; // ebx
  int v51; // eax
  HDC__ *m_hDC; // rcx
  HDC__ *v53; // rcx
  _BLENDFUNCTION pixelblend; // [rsp+60h] [rbp-A0h]
  _BLENDFUNCTION pixelblenda; // [rsp+60h] [rbp-A0h]
  unsigned int yoriginDest; // [rsp+64h] [rbp-9Ch]
  unsigned int xoriginDest; // [rsp+68h] [rbp-98h]
  int wSrc; // [rsp+6Ch] [rbp-94h]
  unsigned int *pBits; // [rsp+70h] [rbp-90h] BYREF
  COLORREF Pixel; // [rsp+78h] [rbp-88h]
  CBitmap bmpMem; // [rsp+80h] [rbp-80h] BYREF
  int left; // [rsp+90h] [rbp-70h]
  int yoriginSrc; // [rsp+94h] [rbp-6Ch]
  int v64; // [rsp+98h] [rbp-68h]
  int nYDest; // [rsp+9Ch] [rbp-64h]
  int nXDest; // [rsp+A0h] [rbp-60h]
  CSize sizeDest; // [rsp+A8h] [rbp-58h]
  int v68; // [rsp+B0h] [rbp-50h]
  CDrawingManager dm; // [rsp+B8h] [rbp-48h] BYREF
  CDC *v70; // [rsp+C8h] [rbp-38h]
  CDC dcMem; // [rsp+D0h] [rbp-30h] BYREF
  CGdiObject *v72; // [rsp+F0h] [rbp-10h]
  CRect rectImage; // [rsp+F8h] [rbp-8h] BYREF
  tagBITMAPINFO bi; // [rsp+108h] [rbp+8h] BYREF

  nYDest = yDest;
  nXDest = xDest;
  v70 = pDCDest;
  if ( iImage < 0 || iImage >= this->m_iCount )
    return 0;
  if ( bShadow )
    return 1;
  m_sizeImageDest = this->m_sizeImageDest;
  bmpMem.__vftable = (CBitmap_vtbl *)__PAIR64__(yDest, xDest);
  LODWORD(bmpMem.m_hObject) = xDest + m_sizeImageDest.cx;
  HIDWORD(bmpMem.m_hObject) = yDest + m_sizeImageDest.cy;
  this->m_rectLastDraw = (CRect)bmpMem;
  m_bStretch = this->m_bStretch;
  v68 = m_bStretch;
  v15 = 0;
  if ( !m_bStretch )
    v15 = bHilite;
  LODWORD(pBits) = v15;
  v16 = 0;
  if ( !m_bStretch )
    v16 = bIndeterminate;
  pixelblend = (_BLENDFUNCTION)v16;
  if ( this->m_nBitsPerPixel == 32 && m_bStretch )
  {
    this->m_bStretch = 0;
    v17 = 0;
    sizeDest = (CSize)16LL;
  }
  else
  {
    sizeDest = 0;
    v17 = m_bStretch;
    if ( this->m_nBitsPerPixel != 32 && !CMFCToolBarImages::m_bIsDrawOnGlass )
    {
      m_clrTransparent = this->m_clrTransparent;
      goto LABEL_13;
    }
  }
  m_clrTransparent = -1;
LABEL_13:
  Pixel = m_clrTransparent;
  if ( !v17 && m_clrTransparent == -1 )
  {
    p_m_dcMem = pDCDest;
LABEL_21:
    xoriginDest = xDest;
LABEL_24:
    yoriginDest = yDest;
    goto LABEL_26;
  }
  p_m_dcMem = &this->m_dcMem;
  if ( !v17 && m_clrTransparent == -1 )
    goto LABEL_21;
  xoriginDest = 0;
  if ( !v17 && m_clrTransparent == -1 )
    goto LABEL_24;
  yoriginDest = 0;
LABEL_26:
  left = this->m_rectSubImage.left;
  yoriginSrc = this->m_rectSubImage.top;
  if ( IsRectEmpty(&this->m_rectSubImage) )
    cx = this->m_sizeImage.cx;
  else
    cx = this->m_rectSubImage.right - this->m_rectSubImage.left;
  wSrc = cx;
  if ( IsRectEmpty(&this->m_rectSubImage) )
    cy = this->m_sizeImage.cy;
  else
    cy = this->m_rectSubImage.bottom - this->m_rectSubImage.top;
  if ( this->m_bStretch || m_clrTransparent != -1 )
  {
    m_sizeImage = this->m_sizeImage;
    rectImage.left = 0;
    *(CSize *)&rectImage.right = m_sizeImage;
    rectImage.top = 0;
    m_bInitialized = afxGlobalData.m_bInitialized;
    if ( m_clrTransparent == -1 )
      goto LABEL_53;
    if ( !afxGlobalData.m_bInitialized )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      m_bInitialized = 1;
      afxGlobalData.m_bInitialized = 1;
    }
    if ( m_clrTransparent == afxGlobalData.clrBtnFace )
    {
LABEL_53:
      if ( !m_bInitialized )
      {
        AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
        afxGlobalData.m_bInitialized = 1;
      }
      FillRect(p_m_dcMem->m_hDC, &rectImage, (HBRUSH)afxGlobalData.brBtnFace.m_hObject);
    }
    else
    {
      CBrush::CBrush((CBrush *)&dm, m_clrTransparent);
      FillRect(p_m_dcMem->m_hDC, &rectImage, (HBRUSH)dm.m_dc);
      dm.__vftable = (CDrawingManager_vtbl *)CBrush::`vftable';
      CGdiObject::~CGdiObject((CGdiObject *)&dm);
    }
    v22 = bDisabled;
    if ( !bDisabled )
      goto LABEL_35;
    if ( !afxGlobalData.m_bInitialized )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      afxGlobalData.m_bInitialized = 1;
    }
    if ( afxGlobalData.m_nBitsPerPixel == 16 )
      Pixel = GetPixel(p_m_dcMem->m_hDC, rectImage.left, rectImage.top);
  }
  else
  {
    v22 = bDisabled;
    if ( !bDisabled )
    {
LABEL_35:
      v23 = 0;
      goto LABEL_36;
    }
  }
  if ( this->m_nBitsPerPixel < 24 )
    goto LABEL_85;
  v22 = 0;
  v23 = 1;
LABEL_36:
  bDisabled = v22;
  v64 = v23;
  if ( (_DWORD)pBits )
  {
    if ( !*(_DWORD *)&pixelblend )
    {
LABEL_99:
      if ( !afxGlobalData.m_bInitialized )
      {
        AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
        afxGlobalData.m_bInitialized = 1;
      }
      v49 = CDC::SelectObject(p_m_dcMem, (CFont *)&afxGlobalData.brLight);
      if ( v49 )
      {
        CMFCToolBarImages::CreateMask(this, iImage, pixelblend == 0, bDisabled);
        p_m_dcMem->SetTextColor(p_m_dcMem, 0);
        p_m_dcMem->SetBkColor(p_m_dcMem, 0xFFFFFFu);
        BitBlt(p_m_dcMem->m_hDC, xoriginDest, yoriginDest, cx, cy, hDCMono, 0, 0, 0xE20746u);
        CDC::SelectObject(p_m_dcMem, v49);
      }
      goto LABEL_103;
    }
LABEL_85:
    CMFCToolBarImages::CreateMask(this, iImage, 1, 0);
    p_m_dcMem->SetTextColor(p_m_dcMem, 0);
    p_m_dcMem->SetBkColor(p_m_dcMem, 0xFFFFFFu);
    if ( v22 && CMFCVisualManager::GetInstance()->m_bEmbossDisabledImage )
    {
      if ( !afxGlobalData.m_bInitialized )
      {
        AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
        afxGlobalData.m_bInitialized = 1;
      }
      if ( afxGlobalData.hbrBtnHilite )
      {
        v47 = SelectObject(p_m_dcMem->m_hDC, afxGlobalData.hbrBtnHilite);
        if ( v47 )
        {
          BitBlt(p_m_dcMem->m_hDC, xoriginDest + 1, yoriginDest + 1, cx + 2, cy + 2, hDCMono, 0, 0, 0xB8074Au);
          SelectObject(p_m_dcMem->m_hDC, v47);
        }
      }
    }
    if ( !afxGlobalData.m_bInitialized )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      afxGlobalData.m_bInitialized = 1;
    }
    if ( afxGlobalData.hbrBtnShadow )
    {
      v48 = SelectObject(p_m_dcMem->m_hDC, afxGlobalData.hbrBtnShadow);
      if ( v48 )
      {
        BitBlt(p_m_dcMem->m_hDC, xoriginDest, yoriginDest, cx + 2, cy + 2, hDCMono, 0, 0, 0xB8074Au);
        SelectObject(p_m_dcMem->m_hDC, v48);
      }
    }
    if ( !(_DWORD)pBits && !*(_DWORD *)&pixelblend )
      goto LABEL_103;
    goto LABEL_99;
  }
  if ( this->m_nBitsPerPixel != 32 && !CMFCToolBarImages::m_bIsDrawOnGlass )
  {
LABEL_78:
    BitBlt(
      p_m_dcMem->m_hDC,
      xoriginDest,
      yoriginDest,
      cx,
      cy,
      hDCGlyphs,
      left + this->m_sizeImage.cx * iImage,
      yoriginSrc,
      0xCC0020u);
    if ( v64 )
    {
      dm.__vftable = (CDrawingManager_vtbl *)CDrawingManager::`vftable';
      dm.m_dc = p_m_dcMem;
      Instance = CMFCVisualManager::GetInstance();
      v45 = Instance->GetToolbarDisabledColor(Instance);
      clrBtnFace = Pixel;
      if ( Pixel == -1 )
      {
        if ( !afxGlobalData.m_bInitialized )
        {
          AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
          afxGlobalData.m_bInitialized = 1;
        }
        clrBtnFace = afxGlobalData.clrBtnFace;
      }
      bmpMem.__vftable = (CBitmap_vtbl *)__PAIR64__(yoriginDest, xoriginDest);
      LODWORD(bmpMem.m_hObject) = cx + xoriginDest + 2;
      HIDWORD(bmpMem.m_hObject) = cy + yoriginDest + 2;
      CDrawingManager::GrayRect(&dm, (CRect *)&bmpMem, -1, clrBtnFace, v45);
    }
    goto LABEL_103;
  }
  *(_WORD *)&pixelblenda.BlendOp = 0;
  pixelblenda.AlphaFormat = 1;
  if ( v23 )
    alphaSrc = CMFCToolBarImages::m_nDisabledImageAlpha;
  pixelblenda.SourceConstantAlpha = alphaSrc;
  v25 = *(__int64 *)((char *)&this->m_sizeImage + *(_QWORD *)&sizeDest);
  sizeDest = (CSize)v25;
  if ( this->m_nBitsPerPixel == 32 )
  {
    v41 = left + this->m_sizeImage.cx * iImage;
    v42 = CDC::FromHandle(hDCGlyphs);
    if ( v42 )
      hdcSrc = v42->m_hDC;
    else
      hdcSrc = 0;
    v38 = AlphaBlend(
            p_m_dcMem->m_hDC,
            xoriginDest,
            yoriginDest,
            v25,
            sizeDest.cy,
            hdcSrc,
            v41,
            yoriginSrc,
            wSrc,
            cy,
            pixelblenda);
    cx = wSrc;
    goto LABEL_77;
  }
  bi.bmiHeader.biSize = 40;
  bi.bmiHeader.biWidth = cx;
  bi.bmiHeader.biHeight = cy;
  *(_DWORD *)&bi.bmiHeader.biPlanes = 2097153;
  bi.bmiHeader.biCompression = 0;
  v26 = cx * cy;
  bi.bmiHeader.biSizeImage = wSrc * cy;
  bi.bmiHeader.biXPelsPerMeter = 0;
  bi.bmiHeader.biYPelsPerMeter = 0;
  bi.bmiHeader.biClrUsed = 0;
  bi.bmiHeader.biClrImportant = 0;
  pBits = 0;
  v27 = CreateDIBSection(0, &bi, 0, (void **)&pBits, 0, 0);
  if ( !v27 )
    return 0;
  bmpMem.m_hObject = 0;
  bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
  CGdiObject::Attach(&bmpMem, v27);
  dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
  memset(&dcMem.m_hDC, 0, 20);
  CompatibleDC = CreateCompatibleDC(0);
  CDC::Attach(&dcMem, CompatibleDC);
  v29 = SelectObject(dcMem.m_hDC, bmpMem.m_hObject);
  v72 = CGdiObject::FromHandle(v29);
  BitBlt(dcMem.m_hDC, 0, 0, wSrc, cy, hDCGlyphs, left + this->m_sizeImage.cx * iImage, yoriginSrc, 0xCC0020u);
  v30 = this->m_clrTransparent;
  if ( v30 == -1 )
  {
    if ( v26 > 0 )
    {
      v31 = (unsigned int)v26;
      v32 = pBits;
      do
      {
        *v32 |= 0xFF000000;
        v32 = ++pBits;
        --v31;
      }
      while ( v31 );
    }
  }
  else
  {
    v35 = (LOBYTE(this->m_clrTransparent) << 16) | BYTE2(v30) | (BYTE1(this->m_clrTransparent) << 8);
    if ( v26 > 0 )
    {
      v36 = (unsigned int)v26;
      v37 = pBits;
      do
      {
        if ( *v37 == v35 )
          *v37 = 0;
        else
          *v37 |= 0xFF000000;
        v37 = ++pBits;
        --v36;
      }
      while ( v36 );
    }
  }
  cx = wSrc;
  v38 = AlphaBlend(
          p_m_dcMem->m_hDC,
          xoriginDest,
          yoriginDest,
          v25,
          sizeDest.cy,
          dcMem.m_hDC,
          0,
          0,
          wSrc,
          cy,
          pixelblenda);
  if ( v72 )
    m_hObject = v72->m_hObject;
  else
    m_hObject = 0;
  v40 = SelectObject(dcMem.m_hDC, m_hObject);
  CGdiObject::FromHandle(v40);
  CDC::~CDC(&dcMem);
  bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
  CGdiObject::~CGdiObject(&bmpMem);
LABEL_77:
  if ( !v38 )
    goto LABEL_78;
LABEL_103:
  if ( this->m_bStretch )
  {
    v50 = this->m_sizeImageDest.cy;
    v51 = this->m_sizeImageDest.cx;
    LODWORD(pBits) = v51;
    if ( m_clrTransparent == -1 )
    {
      if ( !afxGlobalData.m_bInitialized )
      {
        AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
        afxGlobalData.m_bInitialized = 1;
        v51 = (int)pBits;
      }
      m_clrTransparent = afxGlobalData.clrBtnFace;
    }
    m_hDC = (HDC__ *)v70;
    if ( v70 )
      m_hDC = v70->m_hDC;
    CMFCToolBarImages::TransparentBlt(m_hDC, nXDest, nYDest, cx, cy, p_m_dcMem, 0, 0, m_clrTransparent, v51, v50);
  }
  else if ( m_clrTransparent != -1 )
  {
    v53 = (HDC__ *)v70;
    if ( v70 )
      v53 = v70->m_hDC;
    CMFCToolBarImages::TransparentBlt(v53, nXDest, nYDest, cx, cy, p_m_dcMem, 0, 0, m_clrTransparent, -1, -1);
  }
  this->m_bStretch = v68;
  return 1;
}

```

## disassembly

```asm
0x180173910  push    rbp
0x180173912  push    rbx
0x180173913  push    rsi
0x180173914  push    rdi
0x180173915  push    r12
0x180173917  push    r13
0x180173919  push    r14
0x18017391b  push    r15
0x18017391d  lea     rbp, [rsp-48h]
0x180173922  sub     rsp, 148h
0x180173929  mov     rax, cs:__security_cookie
0x180173930  xor     rax, rsp
0x180173933  mov     [rbp+80h+var_48], rax
0x180173937  mov     [rbp+80h+nYDest], yDest
0x18017393b  mov     [rbp+80h+nXDest], xDest
0x18017393f  mov     [rbp+80h+var_B8], pDCDest
0x180173943  mov     rdi, this
0x180173946  xor     r14d, r14d
0x180173949  mov     eax, [rbp+80h+arg_20]
0x18017394f  test    eax, eax
0x180173951  js      loc_1801742A7
0x180173957  cmp     eax, [this+8]
0x18017395a  jge     loc_1801742A7
0x180173960  cmp     [rbp+80h+arg_40], r14d
0x180173967  jz      short loc_180173972
0x180173969  lea     eax, [r14+1]
0x18017396d  jmp     loc_1801742A9
0x180173972  mov     rax, [this+78h]
0x180173976  mov     dword ptr [rbp+80h+bmpMem.__vftable], xDest
0x18017397a  lea     ecx, [r8+rax]
0x18017397e  mov     dword ptr [rbp+80h+bmpMem.m_hObject], ecx
0x180173981  mov     dword ptr [rbp+80h+bmpMem.__vftable+4], yDest
0x180173985  shr     rax, 20h
0x180173989  add     eax, yDest
0x18017398c  mov     dword ptr [rbp+80h+bmpMem.m_hObject+4], eax
0x18017398f  movups  xmm0, xmmword ptr [rbp+80h+bmpMem.__vftable]
0x180173993  movdqu  xmmword ptr [rdi+80h], xmm0
0x18017399b  mov     ecx, [rdi+24h]
0x18017399e  mov     [rbp+80h+var_D0], ecx
0x1801739a1  mov     eax, r14d
0x1801739a4  test    ecx, ecx
0x1801739a6  cmovz   eax, [rbp+80h+arg_28]
0x1801739ad  mov     dword ptr [rsp+180h+pBits], eax
0x1801739b1  mov     eax, r14d
0x1801739b4  cmovz   eax, [rbp+80h+arg_38]
0x1801739bb  mov     dword ptr [rsp+180h+pixelblend.BlendOp], eax
0x1801739bf  or      r10d, 0FFFFFFFFh
0x1801739c3  mov     r11d, 20h ; ' '
0x1801739c9  cmp     [rdi+0Ch], r11d
0x1801739cd  jnz     short loc_1801739F8
0x1801739cf  test    ecx, ecx
0x1801739d1  jz      short loc_1801739F8
0x1801739d3  mov     [rdi+24h], r14d
0x1801739d7  mov     eax, r14d
0x1801739da  mov     qword ptr [rbp+80h+sizeDest.cx], 10h
0x1801739e2  mov     r15d, r10d
0x1801739e5  mov     [rsp+180h+var_108], r15d
0x1801739ea  test    eax, eax
0x1801739ec  jnz     short loc_180173A16
0x1801739ee  cmp     r15d, r10d
0x1801739f1  jnz     short loc_180173A16
0x1801739f3  mov     rsi, pDCDest
0x1801739f6  jmp     short loc_180173A23
0x1801739f8  mov     qword ptr [rbp+80h+sizeDest.cx], r14
0x1801739fc  mov     eax, ecx
0x1801739fe  cmp     [rdi+0Ch], r11d
0x180173a02  jz      short loc_1801739E2
0x180173a04  cmp     cs:?m_bIsDrawOnGlass@CMFCToolBarImages@@2HA, r14d; int CMFCToolBarImages::m_bIsDrawOnGlass
0x180173a0b  jnz     short loc_1801739E2
0x180173a0d  mov     r15d, [rdi+0D8h]
0x180173a14  jmp     short loc_1801739E5
0x180173a16  lea     rsi, [rdi+48h]
0x180173a1a  test    eax, eax
0x180173a1c  jnz     short loc_180173A2A
0x180173a1e  cmp     r15d, r10d
0x180173a21  jnz     short loc_180173A2A
0x180173a23  mov     [rsp+180h+xoriginDest], xDest
0x180173a28  jmp     short loc_180173A38
0x180173a2a  mov     [rsp+180h+xoriginDest], r14d
0x180173a2f  test    eax, eax
0x180173a31  jnz     short loc_180173A3F
0x180173a33  cmp     r15d, r10d
0x180173a36  jnz     short loc_180173A3F
0x180173a38  mov     [rsp+180h+yoriginDest], yDest
0x180173a3d  jmp     short loc_180173A44
0x180173a3f  mov     [rsp+180h+yoriginDest], r14d
0x180173a44  lea     rbx, [rdi+90h]
0x180173a4b  mov     eax, [rbx]
0x180173a4d  mov     [rbp+80h+var_F0], eax
0x180173a50  mov     eax, [rdi+94h]
0x180173a56  mov     [rbp+80h+yoriginSrc], eax
0x180173a59  mov     this, rbx; lprc
0x180173a5c  call    cs:__imp_IsRectEmpty
0x180173a62  test    eax, eax
0x180173a64  jz      short loc_180173A6C
0x180173a66  mov     r12d, [rdi+68h]
0x180173a6a  jmp     short loc_180173A73
0x180173a6c  mov     r12d, [rbx+8]
0x180173a70  sub     r12d, [rbx]
0x180173a73  mov     [rsp+180h+wSrc], r12d
0x180173a78  mov     this, rbx; lprc
0x180173a7b  call    cs:__imp_IsRectEmpty
0x180173a81  test    eax, eax
0x180173a83  jz      short loc_180173A8B
0x180173a85  mov     r13d, [rdi+6Ch]
0x180173a89  jmp     short loc_180173A99
0x180173a8b  mov     r13d, [rdi+9Ch]
0x180173a92  sub     r13d, [rdi+94h]
0x180173a99  mov     r14d, 1
0x180173a9f  cmp     dword ptr [rdi+24h], 0
0x180173aa3  jnz     loc_180173C72
0x180173aa9  cmp     r15d, 0FFFFFFFFh
0x180173aad  jnz     loc_180173C72
0x180173ab3  mov     ebx, [rbp+80h+bHiliteShadow]
0x180173ab9  test    ebx, ebx
0x180173abb  jnz     loc_180173D62
0x180173ac1  xor     edx, edx
0x180173ac3  mov     [rbp+80h+bHiliteShadow], ebx
0x180173ac9  mov     [rbp+80h+var_E8], edx
0x180173acc  cmp     dword ptr [rsp+180h+pBits], 0
0x180173ad1  jnz     loc_180173FBE
0x180173ad7  mov     xDest, 20h ; ' '
0x180173add  cmp     [rdi+0Ch], xDest
0x180173ae1  jz      short loc_180173AF0
0x180173ae3  cmp     cs:?m_bIsDrawOnGlass@CMFCToolBarImages@@2HA, 0; int CMFCToolBarImages::m_bIsDrawOnGlass
0x180173aea  jz      loc_180173ECF
0x180173af0  and     word ptr [rsp+180h+pixelblend.BlendOp], 0
0x180173af6  mov     [rsp+180h+pixelblend.AlphaFormat], r14b
0x180173afb  movzx   ecx, [rbp+80h+arg_50]
0x180173b02  movzx   eax, cs:?m_nDisabledImageAlpha@CMFCToolBarImages@@1EA; uchar CMFCToolBarImages::m_nDisabledImageAlpha
0x180173b09  test    edx, edx
0x180173b0b  cmovnz  ecx, eax
0x180173b0e  mov     [rsp+180h+pixelblend.SourceConstantAlpha], cl
0x180173b12  mov     rbx, qword ptr [rbp+80h+sizeDest.cx]
0x180173b16  mov     rbx, [rdi+rbx+68h]
0x180173b1b  mov     qword ptr [rbp+80h+sizeDest.cx], rbx
0x180173b1f  cmp     [rdi+0Ch], xDest
0x180173b23  jz      loc_180173E54
0x180173b29  mov     [rbp+80h+bi.bmiHeader.biSize], 28h ; '('
0x180173b30  mov     [rbp+80h+bi.bmiHeader.biWidth], r12d
0x180173b34  mov     [rbp+80h+bi.bmiHeader.biHeight], r13d
0x180173b38  mov     dword ptr [rbp+80h+bi.bmiHeader.biPlanes], 200001h
0x180173b3f  and     [rbp+80h+bi.bmiHeader.biCompression], 0
0x180173b43  mov     r12d, r13d
0x180173b46  imul    r12d, [rsp+180h+wSrc]
0x180173b4c  mov     [rbp+80h+bi.bmiHeader.biSizeImage], r12d
0x180173b50  and     [rbp+80h+bi.bmiHeader.biXPelsPerMeter], 0
0x180173b54  and     [rbp+80h+bi.bmiHeader.biYPelsPerMeter], 0
0x180173b58  and     [rbp+80h+bi.bmiHeader.biClrUsed], 0
0x180173b5c  and     [rbp+80h+bi.bmiHeader.biClrImportant], 0
0x180173b60  and     [rsp+180h+pBits], 0
0x180173b66  and     dword ptr [rsp+180h+hdcSrc], 0
0x180173b6b  and     qword ptr [rsp+180h+cy], 0
0x180173b71  lea     r9, [rsp+180h+pBits]; ppvBits
0x180173b76  xor     xDest, xDest; usage
0x180173b79  lea     pDCDest, [rbp+80h+bi]; pbmi
0x180173b7d  xor     ecx, ecx; hdc
0x180173b7f  call    cs:__imp_CreateDIBSection
0x180173b85  test    rax, rax
0x180173b88  jz      loc_1801742A7
0x180173b8e  and     [rbp+80h+bmpMem.m_hObject], 0
0x180173b93  lea     this, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x180173b9a  mov     [rbp+80h+bmpMem.__vftable], this
0x180173b9e  mov     pDCDest, rax; hObject
0x180173ba1  lea     this, [rbp+80h+bmpMem]; this
0x180173ba5  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x180173baa  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x180173bb1  mov     [rbp+80h+dcMem.__vftable], rax
0x180173bb5  xorps   xmm0, xmm0
0x180173bb8  movdqu  xmmword ptr [rbp+80h+dcMem.m_hDC], xmm0
0x180173bbd  and     [rbp+80h+dcMem.m_bPrinting], 0
0x180173bc1  xor     ecx, ecx; hdc
0x180173bc3  call    cs:__imp_CreateCompatibleDC
0x180173bc9  mov     pDCDest, rax; hDC
0x180173bcc  lea     this, [rbp+80h+dcMem]; this
0x180173bd0  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180173bd5  mov     pDCDest, [rbp+80h+bmpMem.m_hObject]; h
0x180173bd9  mov     this, [rbp+80h+dcMem.m_hDC]; hdc
0x180173bdd  call    cs:__imp_SelectObject
0x180173be3  mov     this, rax; h
0x180173be6  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x180173beb  mov     [rbp+80h+var_90], rax
0x180173bef  mov     ecx, [rbp+80h+arg_20]
0x180173bf5  imul    ecx, [rdi+68h]
0x180173bf9  add     ecx, [rbp+80h+var_F0]
0x180173bfc  mov     [rsp+180h+rop], 0CC0020h; rop
0x180173c04  mov     eax, [rbp+80h+yoriginSrc]
0x180173c07  mov     [rsp+180h+y1], eax; yoriginSrc
0x180173c0b  mov     [rsp+180h+x1], ecx; xoriginSrc
0x180173c0f  mov     this, cs:hDCGlyphs
0x180173c16  mov     [rsp+180h+hdcSrc], this; hdcSrc
0x180173c1b  mov     [rsp+180h+cy], r13d; cy
0x180173c20  mov     yDest, [rsp+180h+wSrc]; cx
0x180173c25  xor     xDest, xDest; y
0x180173c28  xor     edx, edx; x
0x180173c2a  mov     this, [rbp+80h+dcMem.m_hDC]; hdc
0x180173c2e  call    cs:__imp_BitBlt
0x180173c34  mov     eax, [rdi+0D8h]
0x180173c3a  cmp     eax, 0FFFFFFFFh
0x180173c3d  jnz     loc_180173D76
0x180173c43  test    r12d, r12d
0x180173c46  jle     loc_180173DC7
0x180173c4c  mov     ecx, r12d
0x180173c4f  mov     rax, [rsp+180h+pBits]
0x180173c54  or      dword ptr [rax], 0FF000000h
0x180173c5a  mov     rax, [rsp+180h+pBits]
0x180173c5f  add     rax, 4
0x180173c63  mov     [rsp+180h+pBits], rax
0x180173c68  sub     this, r14
0x180173c6b  jnz     short loc_180173C54
0x180173c6d  jmp     loc_180173DC7
0x180173c72  mov     rax, [rdi+68h]
0x180173c76  and     [rbp+80h+rectImage.left], 0
0x180173c7a  mov     [rbp+80h+rectImage.right], eax
0x180173c7d  and     [rbp+80h+rectImage.top], 0
0x180173c81  shr     rax, 20h
0x180173c85  mov     [rbp+80h+rectImage.bottom], eax
0x180173c88  mov     eax, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized; AFX_GLOBAL_DATA afxGlobalData ...
0x180173c8e  cmp     r15d, 0FFFFFFFFh
0x180173c92  jz      short loc_180173CEA
0x180173c94  test    eax, eax
0x180173c96  jnz     short loc_180173CAD
0x180173c98  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180173c9f  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x180173ca4  mov     eax, r14d
0x180173ca7  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, eax; AFX_GLOBAL_DATA afxGlobalData ...
0x180173cad  cmp     r15d, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrBtnFace; AFX_GLOBAL_DATA afxGlobalData ...
0x180173cb4  jz      short loc_180173CEA
0x180173cb6  mov     edx, r15d; crColor
0x180173cb9  lea     this, [rbp+80h+dm]; this
0x180173cbd  call    ??0CBrush@@QEAA@K@Z; CBrush::CBrush(ulong)
0x180173cc2  mov     r8, [rbp+80h+dm.m_dc]; hbr
0x180173cc6  lea     pDCDest, [rbp+80h+rectImage]; lprc
0x180173cca  mov     this, [rsi+8]; hDC
0x180173cce  call    cs:__imp_FillRect
0x180173cd4  lea     rax, ??_7CBrush@@6B@; const CBrush::`vftable'
0x180173cdb  mov     [rbp+80h+dm.__vftable], rax
0x180173cdf  lea     this, [rbp+80h+dm]; this
0x180173ce3  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180173ce8  jmp     short loc_180173D16
0x180173cea  test    eax, eax
0x180173cec  jnz     short loc_180173D01
0x180173cee  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180173cf5  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x180173cfa  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r14d; AFX_GLOBAL_DATA afxGlobalData ...
0x180173d01  mov     r8, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.brBtnFace.m_hObject; hbr
0x180173d08  lea     pDCDest, [rbp+80h+rectImage]; lprc
0x180173d0c  mov     this, [rsi+8]; hDC
0x180173d10  call    cs:__imp_FillRect
0x180173d16  mov     ebx, [rbp+80h+bHiliteShadow]
0x180173d1c  test    ebx, ebx
0x180173d1e  jz      loc_180173AC1
0x180173d24  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x180173d2b  jnz     short loc_180173D40
0x180173d2d  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180173d34  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x180173d39  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r14d; AFX_GLOBAL_DATA afxGlobalData ...
0x180173d40  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_nBitsPerPixel, 10h; AFX_GLOBAL_DATA afxGlobalData ...
0x180173d47  jnz     short loc_180173D62
0x180173d49  mov     r8, qword ptr [rbp+80h+rectImage.left]
0x180173d4d  shr     r8, 20h; y
0x180173d51  mov     edx, [rbp+80h+rectImage.left]; x
0x180173d54  mov     this, [rsi+8]; hdc
0x180173d58  call    cs:__imp_GetPixel
0x180173d5e  mov     [rsp+180h+var_108], eax
0x180173d62  cmp     dword ptr [rdi+0Ch], 18h
0x180173d66  jl      loc_180173FC9
0x180173d6c  xor     ebx, ebx
0x180173d6e  mov     edx, r14d
0x180173d71  jmp     loc_180173AC3
0x180173d76  movzx   ecx, byte ptr [rdi+0D9h]
0x180173d7d  shl     ecx, 8
0x180173d80  shr     eax, 10h
0x180173d83  movzx   eax, al
0x180173d86  or      ecx, eax
0x180173d88  movzx   eax, byte ptr [rdi+0D8h]
0x180173d8f  shl     eax, 10h
0x180173d92  or      ecx, eax
0x180173d94  test    r12d, r12d
0x180173d97  jle     short loc_180173DC7
0x180173d99  mov     xDest, r12d
0x180173d9c  mov     rax, [rsp+180h+pBits]
0x180173da1  mov     edx, [rax]
0x180173da3  cmp     edx, ecx
0x180173da5  jz      short loc_180173DB1
0x180173da7  or      edx, 0FF000000h
0x180173dad  mov     [rax], edx
0x180173daf  jmp     short loc_180173DB4
0x180173db1  and     dword ptr [rax], 0
0x180173db4  mov     rax, [rsp+180h+pBits]
0x180173db9  add     rax, 4
0x180173dbd  mov     [rsp+180h+pBits], rax
0x180173dc2  sub     r8, r14
0x180173dc5  jnz     short loc_180173DA1
0x180173dc7  mov     eax, dword ptr [rsp+180h+pixelblend.BlendOp]
0x180173dcb  mov     dword ptr [rsp+180h+ftn.BlendOp], eax; ftn
0x180173dcf  mov     [rsp+180h+hSrc], r13d; hSrc
0x180173dd4  mov     r12d, [rsp+180h+wSrc]
0x180173dd9  mov     [rsp+180h+rop], r12d; wSrc
0x180173dde  and     [rsp+180h+y1], 0
  ... truncated ...
```
