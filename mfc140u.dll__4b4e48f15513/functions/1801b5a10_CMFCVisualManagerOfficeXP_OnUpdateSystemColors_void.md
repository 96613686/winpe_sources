# CMFCVisualManagerOfficeXP::OnUpdateSystemColors(void)

- ea: `0x1801b5a10`
- end: `0x1801b6351`
- name: `?OnUpdateSystemColors@CMFCVisualManagerOfficeXP@@MEAAXXZ`
- size: `2369`
- prototype: `void __fastcall(CMFCVisualManagerOfficeXP *this)`
- caller_count: `3`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180199f60`
- `0x1801b5720`
- `0x1801c0d20`

## callees

- `0x18005d1d0`
- `0x18005d270`
- `0x18005d5b0`
- `0x18005d820`
- `0x18006cab0`
- `0x1801b5a10`
- `0x1802b09d0`
- `0x1802b0a60`
- `0x1802c7020`

## import_xrefs

- `GDI32!CreatePen` at `0x1801b62e2`
- `GDI32!CreatePen` at `0x1801b6330`
- `GDI32!CreatePen` at `0x1801b62e2`
- `GDI32!CreatePen` at `0x1801b6330`
- `GDI32!CreateSolidBrush` at `0x1801b6223`
- `GDI32!CreateSolidBrush` at `0x1801b623e`
- `GDI32!CreateSolidBrush` at `0x1801b6259`
- `GDI32!CreateSolidBrush` at `0x1801b6274`
- `GDI32!CreateSolidBrush` at `0x1801b628f`
- `GDI32!CreateSolidBrush` at `0x1801b62aa`
- `GDI32!CreateSolidBrush` at `0x1801b62c1`
- `GDI32!CreateSolidBrush` at `0x1801b62f9`
- `GDI32!CreateSolidBrush` at `0x1801b6223`
- `GDI32!CreateSolidBrush` at `0x1801b623e`
- `GDI32!CreateSolidBrush` at `0x1801b6259`
- `GDI32!CreateSolidBrush` at `0x1801b6274`
- `GDI32!CreateSolidBrush` at `0x1801b628f`
- `GDI32!CreateSolidBrush` at `0x1801b62aa`
- `GDI32!CreateSolidBrush` at `0x1801b62c1`
- `GDI32!CreateSolidBrush` at `0x1801b62f9`

## pseudocode

```c
void __fastcall CMFCVisualManagerOfficeXP::OnUpdateSystemColors(CMFCVisualManagerOfficeXP *this)
{
  int m_bInitialized; // eax
  unsigned int v3; // ebx
  unsigned int clrBarFace; // esi
  int v5; // ebp
  int v6; // r12d
  int v7; // r15d
  int v8; // r13d
  int clrBarFace_low_high; // r14d
  int clrBarFace_low; // ebx
  unsigned int v11; // ecx
  double v12; // xmm2_8
  double v13; // xmm4_8
  double v14; // xmm1_8
  double v15; // xmm2_8
  unsigned int v16; // ecx
  unsigned int v17; // eax
  unsigned int v18; // ebp
  unsigned int clrHilite; // ebx
  int v20; // r14d
  int v21; // r15d
  int v22; // esi
  unsigned int v23; // ebx
  unsigned int v24; // eax
  unsigned int v25; // eax
  int v26; // ecx
  int m_clrMenuLight_low; // r8d
  int v28; // ebx
  unsigned int clrBarShadow; // esi
  COLORREF clrBtnShadow; // ebp
  COLORREF v31; // ebx
  int v32; // eax
  unsigned int v33; // eax
  unsigned int clrBtnFace; // eax
  unsigned int v35; // eax
  int v36; // eax
  int v37; // eax
  unsigned int clrBtnDkShadow; // eax
  HBRUSH SolidBrush; // rax
  HBRUSH v40; // rax
  HBRUSH v41; // rax
  HBRUSH v42; // rax
  HBRUSH v43; // rax
  HBRUSH v44; // rax
  HBRUSH v45; // rax
  HPEN Pen; // rax
  HBRUSH v47; // rax
  HPEN v48; // rax
  COLORREF color; // [rsp+70h] [rbp+8h]
  double L; // [rsp+78h] [rbp+10h] BYREF
  double S; // [rsp+80h] [rbp+18h] BYREF
  long double H; // [rsp+88h] [rbp+20h] BYREF

  CGdiObject::DeleteObject(&this->m_brBarBkgnd);
  CGdiObject::DeleteObject(&this->m_brMenuRarelyUsed);
  CGdiObject::DeleteObject(&this->m_brMenuLight);
  CGdiObject::DeleteObject(&this->m_brHighlight);
  CGdiObject::DeleteObject(&this->m_brHighlightDn);
  CGdiObject::DeleteObject(&this->m_brHighlightChecked);
  CGdiObject::DeleteObject(&this->m_brFloatToolBarBorder);
  CGdiObject::DeleteObject(&this->m_penSeparator);
  CGdiObject::DeleteObject(&this->m_brTabBack);
  m_bInitialized = afxGlobalData.m_bInitialized;
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    m_bInitialized = 1;
    afxGlobalData.m_bInitialized = 1;
  }
  if ( afxGlobalData.m_nBitsPerPixel > 8 )
  {
    if ( !m_bInitialized )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      m_bInitialized = 1;
      afxGlobalData.m_bInitialized = 1;
    }
    if ( !afxGlobalData.m_bIsWhiteHighContrast && !afxGlobalData.m_bIsBlackHighContrast )
    {
      v3 = this->GetWindowColor(this);
      if ( !afxGlobalData.m_bInitialized )
      {
        AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
        afxGlobalData.m_bInitialized = 1;
      }
      clrBarFace = afxGlobalData.clrBarFace;
      v5 = BYTE2(v3);
      v6 = BYTE2(afxGlobalData.clrBarFace);
      v7 = BYTE1(v3);
      v8 = (unsigned __int8)v3;
      clrBarFace_low_high = HIBYTE(LOWORD(afxGlobalData.clrBarFace));
      clrBarFace_low = LOBYTE(afxGlobalData.clrBarFace);
      v11 = afxGlobalData.clrBarFace;
      this->m_clrMenuLight = (unsigned __int8)((219 * v8 + 36 * (unsigned int)LOBYTE(afxGlobalData.clrBarFace)) / 0xFF)
                           | ((unsigned __int8)((219 * v5 + 36 * (unsigned int)BYTE2(afxGlobalData.clrBarFace)) / 0xFF) << 16)
                           | ((unsigned __int8)((219 * v7 + 36 * clrBarFace_low_high) / 0xFFu) << 8);
      CDrawingManager::RGBtoHSL(v11, &H, &S, &L);
      if ( S >= 0.1 )
      {
        v15 = DOUBLE_1_0;
        v14 = S * 2.0;
        v13 = fmin(1.0, L * 0.5 + 0.5);
      }
      else
      {
        v12 = 0.0;
        v13 = fmin(1.0, (1.0 - L) * 0.5 + L);
        if ( S == 0.0 )
        {
LABEL_15:
          color = CDrawingManager::HLStoRGB_ONE(H, v13, v12);
          v16 = (unsigned __int8)((215 * clrBarFace_low + 40 * v8) / 0xFFu)
              | ((unsigned __int8)((215 * v6 + 40 * v5) / 0xFFu) << 16)
              | ((unsigned __int8)((215 * clrBarFace_low_high + 40 * v7) / 0xFFu) << 8);
          this->m_clrBarBkgnd = v16;
          this->m_clrMenuRarelyUsed = CDrawingManager::PixelAlpha(v16, 94);
          v17 = CDrawingManager::PixelAlpha(clrBarFace, 55);
          this->m_clrInactiveTabText = v17;
          v18 = v17;
          if ( !afxGlobalData.m_bInitialized )
          {
            AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
            afxGlobalData.m_bInitialized = 1;
          }
          clrHilite = afxGlobalData.clrHilite;
          CDrawingManager::RGBtoHSL(afxGlobalData.clrHilite, &H, &S, &L);
          v20 = BYTE2(clrHilite);
          v21 = (unsigned __int8)clrHilite;
          v22 = BYTE1(clrHilite);
          v23 = (unsigned __int8)((77 * (unsigned __int8)clrHilite + 178 * (unsigned int)LOBYTE(this->m_clrMenuLight))
                                / 0xFF)
              | ((unsigned __int8)((77 * BYTE2(clrHilite) + 178 * (unsigned int)BYTE2(this->m_clrMenuLight)) / 0xFF) << 16)
              | ((unsigned __int8)((77 * v22 + 178 * (unsigned int)BYTE1(this->m_clrMenuLight)) / 0xFF) << 8);
          if ( L <= 0.8 )
          {
            v25 = CDrawingManager::PixelAlpha(v23, 102);
            this->m_clrHighlight = v25;
            this->m_clrHighlightDn = CDrawingManager::PixelAlpha(v25, 87);
            if ( !afxGlobalData.m_bInitialized )
            {
              AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
              afxGlobalData.m_bInitialized = 1;
            }
            v24 = afxGlobalData.clrHilite;
          }
          else
          {
            this->m_clrHighlight = CDrawingManager::PixelAlpha(v23, 91);
            this->m_clrHighlightDn = CDrawingManager::PixelAlpha(v23, 98);
            if ( !afxGlobalData.m_bInitialized )
            {
              AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
              afxGlobalData.m_bInitialized = 1;
            }
            v24 = CDrawingManager::PixelAlpha(afxGlobalData.clrHilite, 84);
          }
          v26 = BYTE1(this->m_clrMenuLight);
          m_clrMenuLight_low = LOBYTE(this->m_clrMenuLight);
          this->m_clrMenuItemBorder = v24;
          this->m_clrHighlightChecked = CDrawingManager::PixelAlpha(
                                          (unsigned __int8)((v21 + 4 * m_clrMenuLight_low + m_clrMenuLight_low) / 6u)
                                        | ((unsigned __int8)((v22 + 4 * v26 + v26) / 6u) << 8)
                                        | ((unsigned __int8)((v20
                                                            + 4 * BYTE2(this->m_clrMenuLight)
                                                            + (unsigned int)BYTE2(this->m_clrMenuLight))
                                                           / 6) << 16),
                                          100);
          if ( !afxGlobalData.m_bInitialized )
          {
            AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
            afxGlobalData.m_bInitialized = 1;
          }
          this->m_clrSeparator = CDrawingManager::PixelAlpha(afxGlobalData.clrBarFace, 0.86, 0.86, 0.86);
          if ( !afxGlobalData.m_bInitialized )
          {
            AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
            afxGlobalData.m_bInitialized = 1;
          }
          this->m_clrPaneBorder = afxGlobalData.clrBarShadow;
          this->m_clrMenuBorder = v18;
          v28 = afxGlobalData.m_bInitialized;
          if ( !afxGlobalData.m_bInitialized )
          {
            AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
            v28 = 1;
            afxGlobalData.m_bInitialized = 1;
          }
          clrBarShadow = afxGlobalData.clrBarShadow;
          clrBtnShadow = CDrawingManager::PixelAlpha(afxGlobalData.clrBarShadow, 0.85, 0.85, 0.85);
          if ( !v28 )
          {
            AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
            clrBarShadow = afxGlobalData.clrBarShadow;
            afxGlobalData.m_bInitialized = 1;
          }
          v31 = color;
          this->m_clrGripper = CDrawingManager::PixelAlpha(clrBarShadow, 110);
          goto LABEL_73;
        }
        v14 = S + 0.1;
        v15 = DOUBLE_1_0;
      }
      v12 = fmin(v15, v14);
      goto LABEL_15;
    }
  }
  if ( !m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    afxGlobalData.m_bInitialized = 1;
  }
  this->m_clrMenuLight = afxGlobalData.clrWindow;
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    afxGlobalData.m_bInitialized = 1;
  }
  this->m_clrBarBkgnd = afxGlobalData.clrBtnFace;
  v32 = afxGlobalData.m_bInitialized;
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    v32 = 1;
    afxGlobalData.m_bInitialized = 1;
  }
  if ( afxGlobalData.m_bIsBlackHighContrast )
  {
    if ( !v32 )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      afxGlobalData.m_bInitialized = 1;
    }
    v33 = afxGlobalData.clrHilite;
    this->m_clrHighlight = afxGlobalData.clrHilite;
    this->m_clrHighlightDn = v33;
    this->m_clrHighlightChecked = v33;
    if ( !afxGlobalData.m_bInitialized )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      afxGlobalData.m_bInitialized = 1;
    }
    clrBtnFace = afxGlobalData.clrBtnFace;
  }
  else
  {
    if ( !v32 )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      afxGlobalData.m_bInitialized = 1;
    }
    v35 = afxGlobalData.clrBtnFace;
    this->m_clrHighlight = afxGlobalData.clrBtnFace;
    this->m_clrHighlightDn = v35;
    if ( !afxGlobalData.m_bInitialized )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      afxGlobalData.m_bInitialized = 1;
    }
    this->m_clrHighlightChecked = afxGlobalData.clrWindow;
    if ( !afxGlobalData.m_bInitialized )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      afxGlobalData.m_bInitialized = 1;
    }
    clrBtnFace = afxGlobalData.clrBarLight;
  }
  this->m_clrMenuRarelyUsed = clrBtnFace;
  v36 = afxGlobalData.m_bInitialized;
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    v36 = 1;
    afxGlobalData.m_bInitialized = 1;
  }
  v31 = afxGlobalData.clrBtnFace;
  if ( !v36 )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    afxGlobalData.m_bInitialized = 1;
  }
  this->m_clrInactiveTabText = afxGlobalData.clrBtnDkShadow;
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    afxGlobalData.m_bInitialized = 1;
  }
  this->m_clrSeparator = afxGlobalData.clrBtnShadow;
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    afxGlobalData.m_bInitialized = 1;
  }
  this->m_clrGripper = afxGlobalData.clrBtnShadow;
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    afxGlobalData.m_bInitialized = 1;
  }
  this->m_clrPaneBorder = afxGlobalData.clrBtnShadow;
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    afxGlobalData.m_bInitialized = 1;
  }
  this->m_clrMenuBorder = afxGlobalData.clrBtnDkShadow;
  v37 = afxGlobalData.m_bInitialized;
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    v37 = 1;
    afxGlobalData.m_bInitialized = 1;
  }
  clrBtnShadow = afxGlobalData.clrBtnShadow;
  if ( !v37 )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    afxGlobalData.m_bInitialized = 1;
  }
  if ( afxGlobalData.m_bIsWhiteHighContrast || afxGlobalData.m_bIsBlackHighContrast )
    clrBtnDkShadow = afxGlobalData.clrBtnDkShadow;
  else
    clrBtnDkShadow = afxGlobalData.clrHilite;
  this->m_clrMenuItemBorder = clrBtnDkShadow;
LABEL_73:
  SolidBrush = CreateSolidBrush(this->m_clrBarBkgnd);
  CGdiObject::Attach(&this->m_brBarBkgnd, SolidBrush);
  v40 = CreateSolidBrush(this->m_clrMenuRarelyUsed);
  CGdiObject::Attach(&this->m_brMenuRarelyUsed, v40);
  v41 = CreateSolidBrush(this->m_clrMenuLight);
  CGdiObject::Attach(&this->m_brMenuLight, v41);
  v42 = CreateSolidBrush(this->m_clrHighlight);
  CGdiObject::Attach(&this->m_brHighlight, v42);
  v43 = CreateSolidBrush(this->m_clrHighlightDn);
  CGdiObject::Attach(&this->m_brHighlightDn, v43);
  v44 = CreateSolidBrush(this->m_clrHighlightChecked);
  CGdiObject::Attach(&this->m_brHighlightChecked, v44);
  v45 = CreateSolidBrush(v31);
  CGdiObject::Attach(&this->m_brTabBack, v45);
  Pen = CreatePen(0, 1, this->m_clrSeparator);
  CGdiObject::Attach(&this->m_penSeparator, Pen);
  v47 = CreateSolidBrush(clrBtnShadow);
  CGdiObject::Attach(&this->m_brFloatToolBarBorder, v47);
  this->m_clrPressedButtonBorder = -1;
  CGdiObject::DeleteObject(&this->m_penMenuItemBorder);
  v48 = CreatePen(0, 1, this->m_clrMenuItemBorder);
  CGdiObject::Attach(&this->m_penMenuItemBorder, v48);
}

```

## disassembly

```asm
0x1801b5a10  push    rbx
0x1801b5a12  push    rbp
0x1801b5a13  push    rsi
0x1801b5a14  push    rdi
0x1801b5a15  push    r12
0x1801b5a17  push    r13
0x1801b5a19  push    r14
0x1801b5a1b  push    r15
0x1801b5a1d  sub     rsp, 28h
0x1801b5a21  mov     rdi, this
0x1801b5a24  add     this, 160h; this
0x1801b5a2b  call    ?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x1801b5a30  lea     this, [rdi+170h]; this
0x1801b5a37  call    ?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x1801b5a3c  lea     this, [rdi+180h]; this
0x1801b5a43  call    ?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x1801b5a48  lea     this, [rdi+1A0h]; this
0x1801b5a4f  call    ?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x1801b5a54  lea     this, [rdi+1B0h]; this
0x1801b5a5b  call    ?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x1801b5a60  lea     this, [rdi+1C0h]; this
0x1801b5a67  call    ?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x1801b5a6c  lea     this, [rdi+1D0h]; this
0x1801b5a73  call    ?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x1801b5a78  lea     this, [rdi+1E0h]; this
0x1801b5a7f  call    ?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x1801b5a84  lea     this, [rdi+190h]; this
0x1801b5a8b  call    ?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x1801b5a90  mov     eax, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized; AFX_GLOBAL_DATA afxGlobalData ...
0x1801b5a96  lea     r14, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; AFX_GLOBAL_DATA afxGlobalData
0x1801b5a9d  xor     esi, esi
0x1801b5a9f  mov     r15d, 1
0x1801b5aa5  test    eax, eax
0x1801b5aa7  jnz     short loc_1801B5ABA
0x1801b5aa9  mov     this, r14; this
0x1801b5aac  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1801b5ab1  mov     eax, r15d
0x1801b5ab4  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, eax; AFX_GLOBAL_DATA afxGlobalData ...
0x1801b5aba  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_nBitsPerPixel, 8; AFX_GLOBAL_DATA afxGlobalData ...
0x1801b5ac1  jle     loc_1801B5FB7
0x1801b5ac7  test    eax, eax
0x1801b5ac9  jnz     short loc_1801B5ADC
0x1801b5acb  mov     this, r14; this
0x1801b5ace  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1801b5ad3  mov     eax, r15d
0x1801b5ad6  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, eax; AFX_GLOBAL_DATA afxGlobalData ...
0x1801b5adc  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bIsWhiteHighContrast, esi; AFX_GLOBAL_DATA afxGlobalData ...
0x1801b5ae2  jnz     loc_1801B5FB7
0x1801b5ae8  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bIsBlackHighContrast, esi; AFX_GLOBAL_DATA afxGlobalData ...
0x1801b5aee  jnz     loc_1801B5FB7
0x1801b5af4  mov     rax, [rdi]
0x1801b5af7  mov     this, rdi
0x1801b5afa  mov     rax, [rax+630h]
0x1801b5b01  call    cs:__guard_dispatch_icall_fptr
0x1801b5b07  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, esi; AFX_GLOBAL_DATA afxGlobalData ...
0x1801b5b0d  mov     ebx, eax
0x1801b5b0f  jnz     short loc_1801B5B20
0x1801b5b11  mov     this, r14; this
0x1801b5b14  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1801b5b19  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r15d; AFX_GLOBAL_DATA afxGlobalData ...
0x1801b5b20  mov     esi, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrBarFace; AFX_GLOBAL_DATA afxGlobalData ...
0x1801b5b26  mov     r9d, 80808081h
0x1801b5b2c  mov     eax, ebx
0x1801b5b2e  movzx   r15d, bx
0x1801b5b32  shr     eax, 10h
0x1801b5b35  movzx   ebp, al
0x1801b5b38  mov     eax, esi
0x1801b5b3a  shr     eax, 10h
0x1801b5b3d  movzx   r12d, al
0x1801b5b41  shr     r15d, 8
0x1801b5b45  imul    eax, r15d, 0DBh
0x1801b5b4c  movzx   r13d, bl
0x1801b5b50  movzx   r14d, si
0x1801b5b54  shr     r14d, 8
0x1801b5b58  movzx   ebx, sil
0x1801b5b5c  lea     ecx, [r14+r14*8]
0x1801b5b60  lea     edx, [rax+this*4]
0x1801b5b63  mov     eax, r9d
0x1801b5b66  mul     edx
0x1801b5b68  imul    eax, ebp, 0DBh
0x1801b5b6e  lea     ecx, [r12+r12*8]
0x1801b5b72  shr     edx, 7
0x1801b5b75  movzx   r8d, dl
0x1801b5b79  shl     r8d, 8
0x1801b5b7d  lea     edx, [rax+this*4]
0x1801b5b80  mov     eax, r9d
0x1801b5b83  mul     edx
0x1801b5b85  imul    ecx, r13d, 0DBh
0x1801b5b8c  shr     edx, 7
0x1801b5b8f  movzx   eax, dl
0x1801b5b92  shl     eax, 10h
0x1801b5b95  or      r8d, eax
0x1801b5b98  lea     eax, [rbx+rbx*8]
0x1801b5b9b  lea     edx, [this+rax*4]
0x1801b5b9e  mov     eax, r9d
0x1801b5ba1  mul     edx
0x1801b5ba3  lea     r9, [rsp+68h+L]; L
0x1801b5ba8  mov     ecx, esi; rgb
0x1801b5baa  shr     edx, 7
0x1801b5bad  movzx   eax, dl
0x1801b5bb0  lea     rdx, [rsp+68h+H]; H
0x1801b5bb8  or      r8d, eax
0x1801b5bbb  mov     [rdi+110h], r8d
0x1801b5bc2  lea     r8, [rsp+68h+S]; S
0x1801b5bca  call    ?RGBtoHSL@CDrawingManager@@SAXKPEAN00@Z; CDrawingManager::RGBtoHSL(ulong,double *,double *,double *)
0x1801b5bcf  movsd   xmm5, cs:__real@3fb999999999999a
0x1801b5bd7  movsd   xmm1, [rsp+68h+S]
0x1801b5be0  comisd  xmm5, xmm1
0x1801b5be4  jbe     short loc_1801B5C20
0x1801b5be6  movsd   xmm3, cs:__real@3ff0000000000000
0x1801b5bee  xorps   xmm2, xmm2
0x1801b5bf1  ucomisd xmm1, xmm2
0x1801b5bf5  movaps  xmm0, xmm3
0x1801b5bf8  movaps  xmm4, xmm3
0x1801b5bfb  subsd   xmm0, [rsp+68h+L]
0x1801b5c01  mulsd   xmm0, cs:__real@3fe0000000000000
0x1801b5c09  addsd   xmm0, [rsp+68h+L]
0x1801b5c0f  minsd   xmm4, xmm0
0x1801b5c13  jp      short loc_1801B5C17
0x1801b5c15  jz      short loc_1801B5C51
0x1801b5c17  addsd   xmm1, xmm5
0x1801b5c1b  movaps  xmm2, xmm3
0x1801b5c1e  jmp     short loc_1801B5C4D
0x1801b5c20  movsd   xmm3, [rsp+68h+L]
0x1801b5c26  mulsd   xmm3, cs:__real@3fe0000000000000
0x1801b5c2e  movsd   xmm2, cs:__real@3ff0000000000000
0x1801b5c36  mulsd   xmm1, cs:__real@4000000000000000
0x1801b5c3e  movaps  xmm4, xmm2
0x1801b5c41  addsd   xmm3, cs:__real@3fe0000000000000
0x1801b5c49  minsd   xmm4, xmm3
0x1801b5c4d  minsd   xmm2, xmm1; S
0x1801b5c51  movsd   xmm0, [rsp+68h+H]; H
0x1801b5c5a  movaps  xmm1, xmm4; L
0x1801b5c5d  call    ?HLStoRGB_ONE@CDrawingManager@@SAKNNN@Z; CDrawingManager::HLStoRGB_ONE(double,double,double)
0x1801b5c62  mov     [rsp+68h+color], eax
0x1801b5c66  lea     ecx, [r15+r15*4]
0x1801b5c6a  mov     r10d, 80808081h
0x1801b5c70  imul    edx, r14d, 0D7h
0x1801b5c77  mov     eax, r10d
0x1801b5c7a  lea     r8d, [rdx+this*8]
0x1801b5c7e  mul     r8d
0x1801b5c81  lea     ecx, ds:0[rbp*4]
0x1801b5c88  mov     eax, r10d
0x1801b5c8b  shr     edx, 7
0x1801b5c8e  add     ecx, ebp
0x1801b5c90  movzx   r9d, dl
0x1801b5c94  imul    edx, r12d, 0D7h
0x1801b5c9b  shl     r9d, 8
0x1801b5c9f  lea     r8d, [rdx+this*8]
0x1801b5ca3  imul    ecx, ebx, 0D7h
0x1801b5ca9  mul     r8d
0x1801b5cac  shr     edx, 7
0x1801b5caf  movzx   eax, dl
0x1801b5cb2  shl     eax, 10h
0x1801b5cb5  or      r9d, eax
0x1801b5cb8  lea     eax, ds:0[r13*4]
0x1801b5cc0  add     eax, r13d
0x1801b5cc3  lea     edx, [this+rax*8]
0x1801b5cc6  mov     eax, r10d
0x1801b5cc9  mul     edx
0x1801b5ccb  shr     edx, 7
0x1801b5cce  movzx   eax, dl
0x1801b5cd1  mov     edx, 5Eh ; '^'; percent
0x1801b5cd6  or      r9d, eax
0x1801b5cd9  mov     ecx, r9d; srcPixel
0x1801b5cdc  mov     [rdi+108h], r9d
0x1801b5ce3  call    ?PixelAlpha@CDrawingManager@@SAKKH@Z; CDrawingManager::PixelAlpha(ulong,int)
0x1801b5ce8  mov     edx, 37h ; '7'; percent
0x1801b5ced  mov     [rdi+10Ch], eax
0x1801b5cf3  mov     ecx, esi; srcPixel
0x1801b5cf5  call    ?PixelAlpha@CDrawingManager@@SAKKH@Z; CDrawingManager::PixelAlpha(ulong,int)
0x1801b5cfa  xor     r12d, r12d
0x1801b5cfd  mov     [rdi+114h], eax
0x1801b5d03  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r12d; AFX_GLOBAL_DATA afxGlobalData ...
0x1801b5d0a  lea     r13, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; AFX_GLOBAL_DATA afxGlobalData
0x1801b5d11  mov     ebp, eax
0x1801b5d13  jnz     short loc_1801B5D27
0x1801b5d15  mov     this, r13; this
0x1801b5d18  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1801b5d1d  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x1801b5d27  mov     ebx, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrHilite; AFX_GLOBAL_DATA afxGlobalData ...
0x1801b5d2d  lea     r9, [rsp+68h+L]; L
0x1801b5d32  mov     ecx, ebx; rgb
0x1801b5d34  lea     r8, [rsp+68h+S]; S
0x1801b5d3c  lea     rdx, [rsp+68h+H]; H
0x1801b5d44  call    ?RGBtoHSL@CDrawingManager@@SAXKPEAN00@Z; CDrawingManager::RGBtoHSL(ulong,double *,double *,double *)
0x1801b5d49  movsd   xmm0, [rsp+68h+L]
0x1801b5d4f  mov     eax, ebx
0x1801b5d51  shr     eax, 10h
0x1801b5d54  mov     r8d, 80808081h
0x1801b5d5a  movzx   r14d, al
0x1801b5d5e  movzx   eax, byte ptr [rdi+111h]
0x1801b5d65  imul    ecx, eax, 0B2h
0x1801b5d6b  movzx   esi, bx
0x1801b5d6e  movzx   r15d, bl
0x1801b5d72  shr     esi, 8
0x1801b5d75  imul    eax, esi, 4Dh ; 'M'
0x1801b5d78  add     ecx, eax
0x1801b5d7a  mov     eax, r8d
0x1801b5d7d  mul     ecx
0x1801b5d7f  imul    ecx, r14d, 4Dh ; 'M'
0x1801b5d83  movzx   eax, byte ptr [rdi+112h]
0x1801b5d8a  shr     edx, 7
0x1801b5d8d  movzx   ebx, dl
0x1801b5d90  imul    edx, eax, 0B2h
0x1801b5d96  mov     eax, r8d
0x1801b5d99  shl     ebx, 8
0x1801b5d9c  add     edx, ecx
0x1801b5d9e  mul     edx
0x1801b5da0  mov     eax, r8d
0x1801b5da3  shr     edx, 7
0x1801b5da6  movzx   ecx, dl
0x1801b5da9  shl     ecx, 10h
0x1801b5dac  or      ebx, ecx
0x1801b5dae  movzx   ecx, byte ptr [rdi+110h]
0x1801b5db5  imul    edx, ecx, 0B2h
0x1801b5dbb  imul    ecx, r15d, 4Dh ; 'M'
0x1801b5dbf  add     edx, ecx
0x1801b5dc1  mul     edx
0x1801b5dc3  shr     edx, 7
0x1801b5dc6  movzx   eax, dl
0x1801b5dc9  or      ebx, eax
0x1801b5dcb  comisd  xmm0, cs:__real@3fe999999999999a
0x1801b5dd3  mov     ecx, ebx; srcPixel
0x1801b5dd5  jbe     short loc_1801B5E26
0x1801b5dd7  mov     edx, 5Bh ; '['; percent
0x1801b5ddc  call    ?PixelAlpha@CDrawingManager@@SAKKH@Z; CDrawingManager::PixelAlpha(ulong,int)
0x1801b5de1  mov     edx, 62h ; 'b'; percent
0x1801b5de6  mov     [rdi+118h], eax
0x1801b5dec  mov     ecx, ebx; srcPixel
0x1801b5dee  call    ?PixelAlpha@CDrawingManager@@SAKKH@Z; CDrawingManager::PixelAlpha(ulong,int)
0x1801b5df3  mov     [rdi+11Ch], eax
0x1801b5df9  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r12d; AFX_GLOBAL_DATA afxGlobalData ...
0x1801b5e00  jnz     short loc_1801B5E14
0x1801b5e02  mov     this, r13; this
0x1801b5e05  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1801b5e0a  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x1801b5e14  mov     ecx, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrHilite; srcPixel
0x1801b5e1a  mov     edx, 54h ; 'T'; percent
0x1801b5e1f  call    ?PixelAlpha@CDrawingManager@@SAKKH@Z; CDrawingManager::PixelAlpha(ulong,int)
0x1801b5e24  jmp     short loc_1801B5E69
0x1801b5e26  mov     edx, 66h ; 'f'; percent
0x1801b5e2b  call    ?PixelAlpha@CDrawingManager@@SAKKH@Z; CDrawingManager::PixelAlpha(ulong,int)
0x1801b5e30  mov     edx, 57h ; 'W'; percent
0x1801b5e35  mov     [rdi+118h], eax
0x1801b5e3b  mov     ecx, eax; srcPixel
0x1801b5e3d  call    ?PixelAlpha@CDrawingManager@@SAKKH@Z; CDrawingManager::PixelAlpha(ulong,int)
0x1801b5e42  mov     [rdi+11Ch], eax
0x1801b5e48  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r12d; AFX_GLOBAL_DATA afxGlobalData ...
0x1801b5e4f  jnz     short loc_1801B5E63
0x1801b5e51  mov     this, r13; this
0x1801b5e54  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1801b5e59  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x1801b5e63  mov     eax, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrHilite; AFX_GLOBAL_DATA afxGlobalData ...
0x1801b5e69  movzx   ecx, byte ptr [rdi+111h]
0x1801b5e70  mov     r10d, 0AAAAAAABh
0x1801b5e76  movzx   r8d, byte ptr [rdi+110h]
0x1801b5e7e  mov     [rdi+138h], eax
0x1801b5e84  lea     eax, [rsi+this*4]
0x1801b5e87  add     ecx, eax
0x1801b5e89  mov     eax, r10d
0x1801b5e8c  mul     ecx
0x1801b5e8e  mov     eax, r10d
0x1801b5e91  shr     edx, 2
0x1801b5e94  movzx   r9d, dl
0x1801b5e98  movzx   edx, byte ptr [rdi+112h]
0x1801b5e9f  shl     r9d, 8
0x1801b5ea3  lea     ecx, [r14+rdx*4]
0x1801b5ea7  add     edx, ecx
0x1801b5ea9  mul     edx
0x1801b5eab  mov     eax, r10d
0x1801b5eae  shr     edx, 2
0x1801b5eb1  movzx   ecx, dl
0x1801b5eb4  lea     edx, [r15+r8*4]
0x1801b5eb8  add     r8d, edx
0x1801b5ebb  shl     ecx, 10h
0x1801b5ebe  mul     r8d
0x1801b5ec1  or      ecx, r9d
0x1801b5ec4  shr     edx, 2
0x1801b5ec7  movzx   eax, dl
0x1801b5eca  mov     edx, 64h ; 'd'; percent
0x1801b5ecf  or      ecx, eax; srcPixel
0x1801b5ed1  call    ?PixelAlpha@CDrawingManager@@SAKKH@Z; CDrawingManager::PixelAlpha(ulong,int)
0x1801b5ed6  mov     [rdi+120h], eax
0x1801b5edc  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r12d; AFX_GLOBAL_DATA afxGlobalData ...
0x1801b5ee3  jnz     short loc_1801B5EFC
0x1801b5ee5  mov     this, r13; this
0x1801b5ee8  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1801b5eed  mov     r15d, 1
0x1801b5ef3  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r15d; AFX_GLOBAL_DATA afxGlobalData ...
0x1801b5efa  jmp     short loc_1801B5F02
0x1801b5efc  mov     r15d, 1
0x1801b5f02  movsd   xmm1, cs:__real@3feb851eb851eb85; percentR
0x1801b5f0a  mov     ecx, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrBarFace; srcPixel
0x1801b5f10  movaps  xmm3, xmm1; percentB
0x1801b5f13  movaps  xmm2, xmm1; percentG
0x1801b5f16  call    ?PixelAlpha@CDrawingManager@@SAKKNNN@Z; CDrawingManager::PixelAlpha(ulong,double,double,double)
0x1801b5f1b  mov     [rdi+12Ch], eax
0x1801b5f21  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r12d; AFX_GLOBAL_DATA afxGlobalData ...
0x1801b5f28  jnz     short loc_1801B5F39
  ... truncated ...
```
