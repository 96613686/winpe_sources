# CMFCVisualManagerVS2005::OnUpdateSystemColors(void)

- ea: `0x1801bce20`
- end: `0x1801bd39e`
- name: `?OnUpdateSystemColors@CMFCVisualManagerVS2005@@UEAAXXZ`
- size: `1406`
- prototype: `void __fastcall(CMFCVisualManagerVS2005 *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1801c0280`

## callees

- `0x18005d1d0`
- `0x18005dbd0`
- `0x18006cab0`
- `0x180199f60`
- `0x1801bce20`
- `0x1802b09d0`
- `0x1802b0a60`
- `0x1802c7020`

## import_xrefs

- `USER32!GetSysColor` at `0x1801bcfb4`
- `USER32!GetSysColor` at `0x1801bd0c5`
- `USER32!GetSysColor` at `0x1801bd18e`
- `USER32!GetSysColor` at `0x1801bcfb4`
- `USER32!GetSysColor` at `0x1801bd0c5`
- `USER32!GetSysColor` at `0x1801bd18e`
- `GDI32!CreatePen` at `0x1801bd2a9`
- `GDI32!CreatePen` at `0x1801bd36a`
- `GDI32!CreatePen` at `0x1801bd2a9`
- `GDI32!CreatePen` at `0x1801bd36a`
- `GDI32!CreateSolidBrush` at `0x1801bd101`
- `GDI32!CreateSolidBrush` at `0x1801bd118`
- `GDI32!CreateSolidBrush` at `0x1801bd13e`
- `GDI32!CreateSolidBrush` at `0x1801bd255`
- `GDI32!CreateSolidBrush` at `0x1801bd277`
- `GDI32!CreateSolidBrush` at `0x1801bd101`
- `GDI32!CreateSolidBrush` at `0x1801bd118`
- `GDI32!CreateSolidBrush` at `0x1801bd13e`
- `GDI32!CreateSolidBrush` at `0x1801bd255`
- `GDI32!CreateSolidBrush` at `0x1801bd277`
- `UxTheme!GetThemeColor` at `0x1801bceb0`
- `UxTheme!GetThemeColor` at `0x1801bceb0`
- `UxTheme!GetThemeSysColor` at `0x1801bcfa7`
- `UxTheme!GetThemeSysColor` at `0x1801bd0b8`
- `UxTheme!GetThemeSysColor` at `0x1801bd181`
- `UxTheme!GetThemeSysColor` at `0x1801bcfa7`
- `UxTheme!GetThemeSysColor` at `0x1801bd0b8`
- `UxTheme!GetThemeSysColor` at `0x1801bd181`

## pseudocode

```c
void __fastcall CMFCVisualManagerVS2005::OnUpdateSystemColors(CMFCVisualManagerVS2005 *this)
{
  CMFCVisualManagerVS2005_vtbl *v1; // rax
  int v2; // r12d
  CMFCBaseVisualManager::WinXpTheme v4; // eax
  void *m_hThemeComboBox; // rcx
  COLORREF m_clrBarBkgnd; // ebp
  COLORREF m_clrHighlightDn; // edi
  int m_bInitialized; // eax
  unsigned int *p_m_clrCustomizeButtonGradientDark; // rbx
  unsigned int *p_m_clrCustomizeButtonGradientLight; // rdi
  CMFCBaseVisualManager::WinXpTheme m_CurrAppTheme; // eax
  unsigned int *v12; // rbp
  unsigned int *v13; // r15
  void **p_m_hThemeWindow; // r14
  void *m_hThemeWindow; // rcx
  COLORREF ThemeSysColor; // eax
  unsigned int v17; // ebp
  unsigned int v18; // eax
  CMFCBaseVisualManager::WinXpTheme v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // ecx
  unsigned int v22; // eax
  unsigned int m_clrToolBarBottomLine; // ecx
  unsigned int m_clrToolBarGradientDark; // eax
  unsigned int v25; // eax
  unsigned int v26; // ecx
  unsigned int clrHilite; // ecx
  void *v28; // rcx
  COLORREF SysColor; // eax
  HBRUSH SolidBrush; // rax
  HBRUSH v31; // rax
  HBRUSH v32; // rax
  COLORREF v33; // eax
  unsigned int v34; // eax
  unsigned int m_clrBarGradientDark; // ecx
  HBRUSH v36; // rax
  HBRUSH v37; // rax
  COLORREF m_colorActiveTabBorder; // r8d
  HPEN Pen; // rax
  int v40; // eax
  COLORREF v41; // eax
  HPEN v42; // rax

  v1 = this->__vftable;
  v2 = CMFCVisualManagerOffice2003::m_bDefaultWinXPColors;
  this->m_clrPressedButtonBorder = -1;
  v4 = ((unsigned int (*)(void))v1->GetStandardWindowsTheme)();
  this->m_CurrAppTheme = v4;
  if ( v4 != WinXpTheme_Silver )
    CMFCVisualManagerOffice2003::m_bDefaultWinXPColors = 0;
  CMFCVisualManagerOffice2003::OnUpdateSystemColors(this);
  if ( v2 )
  {
    m_hThemeComboBox = this->m_hThemeComboBox;
    m_clrBarBkgnd = this->m_clrBarBkgnd;
    m_clrHighlightDn = this->m_clrHighlightDn;
    if ( !m_hThemeComboBox || GetThemeColor(m_hThemeComboBox, 5, 0, 3801, &this->m_colorActiveTabBorder) )
      this->m_colorActiveTabBorder = -1;
    m_bInitialized = afxGlobalData.m_bInitialized;
    if ( !afxGlobalData.m_bInitialized )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      m_bInitialized = 1;
      afxGlobalData.m_bInitialized = 1;
    }
    if ( afxGlobalData.m_nBitsPerPixel <= 8 )
      goto LABEL_41;
    if ( !m_bInitialized )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      afxGlobalData.m_bInitialized = 1;
    }
    if ( afxGlobalData.m_bIsWhiteHighContrast || afxGlobalData.m_bIsBlackHighContrast )
      goto LABEL_41;
    p_m_clrCustomizeButtonGradientDark = &this->m_clrCustomizeButtonGradientDark;
    p_m_clrCustomizeButtonGradientLight = &this->m_clrCustomizeButtonGradientLight;
    this->m_clrCustomizeButtonGradientLight = CDrawingManager::SmartMixColors(
                                                this->m_clrCustomizeButtonGradientDark,
                                                afxGlobalData.clrBarFace,
                                                1.5,
                                                1,
                                                1);
    m_CurrAppTheme = this->m_CurrAppTheme;
    if ( m_CurrAppTheme == WinXpTheme_Blue
      || (v12 = &this->m_clrCustomizeButtonGradientDark,
          v13 = &this->m_clrCustomizeButtonGradientLight,
          m_CurrAppTheme == WinXpTheme_Olive) )
    {
      p_m_hThemeWindow = &this->m_hThemeWindow;
      this->m_clrToolBarGradientDark = CDrawingManager::PixelAlpha(this->m_clrToolBarGradientDark, 83);
      m_hThemeWindow = this->m_hThemeWindow;
      if ( m_hThemeWindow )
        ThemeSysColor = GetThemeSysColor(m_hThemeWindow, 5);
      else
        ThemeSysColor = GetSysColor(5);
      v17 = ThemeSysColor;
      v18 = this->GetBaseThemeColor(this);
      this->m_clrToolBarGradientLight = CDrawingManager::SmartMixColors(v18, v17, 1.0, 3, 2);
      v12 = &this->m_clrCustomizeButtonGradientDark;
      v13 = &this->m_clrCustomizeButtonGradientLight;
    }
    else
    {
      p_m_hThemeWindow = &this->m_hThemeWindow;
    }
    v19 = this->m_CurrAppTheme;
    switch ( v19 )
    {
      case WinXpTheme_Blue:
        v20 = CDrawingManager::PixelAlpha(*p_m_clrCustomizeButtonGradientDark, 90);
        v21 = *p_m_clrCustomizeButtonGradientLight;
        *p_m_clrCustomizeButtonGradientDark = v20;
        v22 = CDrawingManager::PixelAlpha(v21, 115);
        m_clrToolBarBottomLine = this->m_clrToolBarBottomLine;
        *p_m_clrCustomizeButtonGradientLight = v22;
        m_clrToolBarGradientDark = CDrawingManager::PixelAlpha(m_clrToolBarBottomLine, 85);
        break;
      case WinXpTheme_Olive:
        v25 = CDrawingManager::PixelAlpha(this->m_clrToolBarBottomLine, 110);
        v26 = *v13;
        this->m_clrToolBarBottomLine = v25;
        *v12 = v25;
        *v13 = CDrawingManager::PixelAlpha(v26, 120);
        if ( !afxGlobalData.m_bInitialized )
        {
          AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
          afxGlobalData.m_bInitialized = 1;
        }
        clrHilite = afxGlobalData.clrHilite;
        this->m_clrHighlightDn = afxGlobalData.clrHilite;
        p_m_hThemeWindow = &this->m_hThemeWindow;
        this->m_clrHighlight = CDrawingManager::PixelAlpha(clrHilite, 124);
        v28 = this->m_hThemeWindow;
        if ( v28 )
          SysColor = GetThemeSysColor(v28, 27);
        else
          SysColor = GetSysColor(27);
        this->m_clrHighlightChecked = CDrawingManager::PixelAlpha(SysColor, 98);
        CGdiObject::DeleteObject(&this->m_brHighlight);
        CGdiObject::DeleteObject(&this->m_brHighlightDn);
        SolidBrush = CreateSolidBrush(this->m_clrHighlight);
        CGdiObject::Attach(&this->m_brHighlight, SolidBrush);
        v31 = CreateSolidBrush(this->m_clrHighlightDn);
        CGdiObject::Attach(&this->m_brHighlightDn, v31);
        CGdiObject::DeleteObject(&this->m_brHighlightChecked);
        v32 = CreateSolidBrush(this->m_clrHighlightChecked);
        CGdiObject::Attach(&this->m_brHighlightChecked, v32);
        goto LABEL_33;
      case WinXpTheme_Silver:
LABEL_33:
        m_clrBarBkgnd = CDrawingManager::PixelAlpha(this->m_clrBarBkgnd, 107);
        if ( *p_m_hThemeWindow )
          v33 = GetThemeSysColor(*p_m_hThemeWindow, 13);
        else
          v33 = GetSysColor(13);
        m_clrHighlightDn = v33;
        if ( (unsigned int)(this->m_CurrAppTheme - 1) <= 1 )
        {
          v34 = CDrawingManager::PixelAlpha(this->m_clrToolBarGradientLight, 95);
          m_clrBarGradientDark = this->m_clrBarGradientDark;
          this->m_clrBarGradientLight = v34;
          this->m_clrBarGradientDark = CDrawingManager::PixelAlpha(m_clrBarGradientDark, 97);
        }
        this->m_clrToolbarDisabled = CDrawingManager::SmartMixColors(
                                       this->m_clrToolBarGradientDark,
                                       this->m_clrToolBarGradientLight,
                                       0.92,
                                       1,
                                       2);
        if ( !afxGlobalData.m_bInitialized )
        {
          AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
          afxGlobalData.m_bInitialized = 1;
        }
        this->m_clrPressedButtonBorder = CDrawingManager::SmartMixColors(
                                           this->m_clrMenuItemBorder,
                                           afxGlobalData.clrBarDkShadow,
                                           0.8,
                                           1,
                                           2);
LABEL_41:
        CGdiObject::DeleteObject(&this->m_brMenuButtonDroppedDown);
        v36 = CreateSolidBrush(m_clrBarBkgnd);
        CGdiObject::Attach(&this->m_brMenuButtonDroppedDown, v36);
        CGdiObject::DeleteObject(&this->m_brMenuItemCheckedHighlight);
        v37 = CreateSolidBrush(m_clrHighlightDn);
        CGdiObject::Attach(&this->m_brMenuItemCheckedHighlight, v37);
        CGdiObject::DeleteObject(&this->m_penActiveTabBorder);
        m_colorActiveTabBorder = this->m_colorActiveTabBorder;
        if ( m_colorActiveTabBorder != -1 )
        {
          Pen = CreatePen(0, 1, m_colorActiveTabBorder);
          CGdiObject::Attach(&this->m_penActiveTabBorder, Pen);
        }
        CMFCVisualManagerOffice2003::m_bDefaultWinXPColors = v2;
        if ( !afxGlobalData.m_bInitialized )
        {
          AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
          afxGlobalData.m_bInitialized = 1;
        }
        this->m_clrInactiveTabText = afxGlobalData.clrBtnDkShadow;
        v40 = afxGlobalData.m_bInitialized;
        if ( !afxGlobalData.m_bInitialized )
        {
          AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
          v40 = 1;
          afxGlobalData.m_bInitialized = 1;
        }
        if ( afxGlobalData.m_nBitsPerPixel > 8 )
        {
          if ( !v40 )
          {
            AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
            afxGlobalData.m_bInitialized = 1;
          }
          if ( !afxGlobalData.m_bIsWhiteHighContrast && !afxGlobalData.m_bIsBlackHighContrast )
          {
            CGdiObject::DeleteObject(&this->m_penSeparator);
            if ( !afxGlobalData.m_bInitialized )
            {
              AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
              afxGlobalData.m_bInitialized = 1;
            }
            v41 = CDrawingManager::PixelAlpha(afxGlobalData.clrBarFace, 84);
            v42 = CreatePen(0, 1, v41);
            CGdiObject::Attach(&this->m_penSeparator, v42);
          }
        }
        return;
      default:
        m_clrToolBarGradientDark = this->m_clrToolBarGradientDark;
        break;
    }
    this->m_clrToolBarBottomLine = m_clrToolBarGradientDark;
    goto LABEL_33;
  }
}

```

## disassembly

```asm
0x1801bce20  mov     rax, rsp
0x1801bce23  mov     [rax+8], rbx
0x1801bce27  mov     [rax+10h], rbp
0x1801bce2b  mov     [rax+18h], rsi
0x1801bce2f  mov     [rax+20h], rdi
0x1801bce33  push    r12
0x1801bce35  push    r14
0x1801bce37  push    r15
0x1801bce39  sub     rsp, 30h
0x1801bce3d  mov     rax, [this]
0x1801bce40  or      r14d, 0FFFFFFFFh
0x1801bce44  mov     r12d, cs:?m_bDefaultWinXPColors@CMFCVisualManagerOffice2003@@1HA; int CMFCVisualManagerOffice2003::m_bDefaultWinXPColors
0x1801bce4b  mov     rsi, this
0x1801bce4e  mov     [this+124h], r14d
0x1801bce55  mov     rax, [rax+60h]
0x1801bce59  call    cs:__guard_dispatch_icall_fptr
0x1801bce5f  mov     [rsi+328h], eax
0x1801bce65  cmp     eax, 3
0x1801bce68  jz      short loc_1801BCE71
0x1801bce6a  and     cs:?m_bDefaultWinXPColors@CMFCVisualManagerOffice2003@@1HA, 0; int CMFCVisualManagerOffice2003::m_bDefaultWinXPColors
0x1801bce71  mov     this, rsi; this
0x1801bce74  call    ?OnUpdateSystemColors@CMFCVisualManagerOffice2003@@UEAAXXZ; CMFCVisualManagerOffice2003::OnUpdateSystemColors(void)
0x1801bce79  test    r12d, r12d
0x1801bce7c  jz      loc_1801BD37F
0x1801bce82  mov     this, [rsi+30h]; hTheme
0x1801bce86  lea     rbx, [rsi+2F0h]
0x1801bce8d  mov     ebp, [rsi+108h]
0x1801bce93  mov     edi, [rsi+11Ch]
0x1801bce99  test    this, this
0x1801bce9c  jz      short loc_1801BCEBA
0x1801bce9e  xor     r8d, r8d; iStateId
0x1801bcea1  mov     [rsp+48h+pColor], rbx; pColor
0x1801bcea6  mov     r9d, 0ED9h; iPropId
0x1801bceac  lea     edx, [r8+5]; iPartId
0x1801bceb0  call    cs:__imp_GetThemeColor
0x1801bceb6  test    eax, eax
0x1801bceb8  jz      short loc_1801BCEBD
0x1801bceba  mov     [rbx], r14d
0x1801bcebd  mov     eax, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized; AFX_GLOBAL_DATA afxGlobalData ...
0x1801bcec3  lea     r15, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; AFX_GLOBAL_DATA afxGlobalData
0x1801bceca  mov     r14d, 1
0x1801bced0  test    eax, eax
0x1801bced2  jnz     short loc_1801BCEE5
0x1801bced4  mov     this, r15; this
0x1801bced7  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1801bcedc  mov     eax, r14d
0x1801bcedf  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, eax; AFX_GLOBAL_DATA afxGlobalData ...
0x1801bcee5  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_nBitsPerPixel, 8; AFX_GLOBAL_DATA afxGlobalData ...
0x1801bceec  jle     loc_1801BD244
0x1801bcef2  test    eax, eax
0x1801bcef4  jnz     short loc_1801BCF07
0x1801bcef6  mov     this, r15; this
0x1801bcef9  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1801bcefe  mov     eax, r14d
0x1801bcf01  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, eax; AFX_GLOBAL_DATA afxGlobalData ...
0x1801bcf07  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bIsWhiteHighContrast, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x1801bcf0e  jnz     loc_1801BD244
0x1801bcf14  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bIsBlackHighContrast, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x1801bcf1b  jnz     loc_1801BD244
0x1801bcf21  test    eax, eax
0x1801bcf23  jnz     short loc_1801BCF34
0x1801bcf25  mov     this, r15; this
0x1801bcf28  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1801bcf2d  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r14d; AFX_GLOBAL_DATA afxGlobalData ...
0x1801bcf34  movsd   xmm2, cs:__real@3ff8000000000000; dblLumRatio
0x1801bcf3c  lea     rbx, [rsi+230h]
0x1801bcf43  mov     ecx, [rbx]; color1
0x1801bcf45  lea     rdi, [rsi+234h]
0x1801bcf4c  mov     edx, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrBarFace; color2
0x1801bcf52  mov     r9d, r14d; k1
0x1801bcf55  mov     dword ptr [rsp+48h+pColor], r14d; k2
0x1801bcf5a  call    ?SmartMixColors@CDrawingManager@@SAKKKNHH@Z; CDrawingManager::SmartMixColors(ulong,ulong,double,int,int)
0x1801bcf5f  mov     [rdi], eax
0x1801bcf61  mov     eax, [rsi+328h]
0x1801bcf67  cmp     eax, r14d
0x1801bcf6a  jz      short loc_1801BCF80
0x1801bcf6c  mov     rbp, rbx
0x1801bcf6f  mov     r15, rdi
0x1801bcf72  cmp     eax, 2
0x1801bcf75  jz      short loc_1801BCF80
0x1801bcf77  lea     r14, [rsi+8]
0x1801bcf7b  jmp     loc_1801BD002
0x1801bcf80  mov     ecx, [rsi+21Ch]; srcPixel
0x1801bcf86  mov     edx, 53h ; 'S'; percent
0x1801bcf8b  call    ?PixelAlpha@CDrawingManager@@SAKKH@Z; CDrawingManager::PixelAlpha(ulong,int)
0x1801bcf90  lea     r14, [rsi+8]
0x1801bcf94  mov     [rsi+21Ch], eax
0x1801bcf9a  mov     this, [r14]; hTheme
0x1801bcf9d  test    this, this
0x1801bcfa0  jz      short loc_1801BCFAF
0x1801bcfa2  mov     edx, 5; iColorId
0x1801bcfa7  call    cs:__imp_GetThemeSysColor
0x1801bcfad  jmp     short loc_1801BCFBA
0x1801bcfaf  mov     ecx, 5; nIndex
0x1801bcfb4  call    cs:__imp_GetSysColor
0x1801bcfba  mov     ebp, eax
0x1801bcfbc  mov     this, rsi
0x1801bcfbf  mov     rax, [rsi]
0x1801bcfc2  mov     rax, [rax+640h]
0x1801bcfc9  call    cs:__guard_dispatch_icall_fptr
0x1801bcfcf  movsd   xmm2, cs:__real@3ff0000000000000; dblLumRatio
0x1801bcfd7  mov     r9d, 3; k1
0x1801bcfdd  mov     ecx, eax; color1
0x1801bcfdf  mov     dword ptr [rsp+48h+pColor], 2; k2
0x1801bcfe7  mov     edx, ebp; color2
0x1801bcfe9  call    ?SmartMixColors@CDrawingManager@@SAKKKNHH@Z; CDrawingManager::SmartMixColors(ulong,ulong,double,int,int)
0x1801bcfee  mov     [rsi+220h], eax
0x1801bcff4  lea     rbp, [rsi+230h]
0x1801bcffb  lea     r15, [rsi+234h]
0x1801bd002  mov     eax, [rsi+328h]
0x1801bd008  cmp     eax, 1
0x1801bd00b  jnz     short loc_1801BD03C
0x1801bd00d  mov     ecx, [rbx]; srcPixel
0x1801bd00f  lea     edx, [rax+59h]; percent
0x1801bd012  call    ?PixelAlpha@CDrawingManager@@SAKKH@Z; CDrawingManager::PixelAlpha(ulong,int)
0x1801bd017  mov     ecx, [rdi]; srcPixel
0x1801bd019  mov     edx, 73h ; 's'; percent
0x1801bd01e  mov     [rbx], eax
0x1801bd020  call    ?PixelAlpha@CDrawingManager@@SAKKH@Z; CDrawingManager::PixelAlpha(ulong,int)
0x1801bd025  mov     ecx, [rsi+238h]; srcPixel
0x1801bd02b  mov     edx, 55h ; 'U'; percent
0x1801bd030  mov     [rdi], eax
0x1801bd032  call    ?PixelAlpha@CDrawingManager@@SAKKH@Z; CDrawingManager::PixelAlpha(ulong,int)
0x1801bd037  jmp     loc_1801BD15C
0x1801bd03c  cmp     eax, 2
0x1801bd03f  jnz     loc_1801BD151
0x1801bd045  mov     ecx, [rsi+238h]; srcPixel
0x1801bd04b  lea     edx, [rax+6Ch]; percent
0x1801bd04e  call    ?PixelAlpha@CDrawingManager@@SAKKH@Z; CDrawingManager::PixelAlpha(ulong,int)
0x1801bd053  mov     ecx, [r15]; srcPixel
0x1801bd056  mov     edx, 78h ; 'x'; percent
0x1801bd05b  mov     [rsi+238h], eax
0x1801bd061  mov     [rbp+0], eax
0x1801bd064  call    ?PixelAlpha@CDrawingManager@@SAKKH@Z; CDrawingManager::PixelAlpha(ulong,int)
0x1801bd069  mov     [r15], eax
0x1801bd06c  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x1801bd073  jnz     short loc_1801BD08B
0x1801bd075  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x1801bd07c  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1801bd081  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x1801bd08b  mov     ecx, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrHilite; srcPixel
0x1801bd091  mov     edx, 7Ch ; '|'; percent
0x1801bd096  mov     [rsi+11Ch], ecx
0x1801bd09c  call    ?PixelAlpha@CDrawingManager@@SAKKH@Z; CDrawingManager::PixelAlpha(ulong,int)
0x1801bd0a1  lea     r14, [rsi+8]
0x1801bd0a5  mov     [rsi+118h], eax
0x1801bd0ab  mov     this, [r14]; hTheme
0x1801bd0ae  test    this, this
0x1801bd0b1  jz      short loc_1801BD0C0
0x1801bd0b3  mov     edx, 1Bh; iColorId
0x1801bd0b8  call    cs:__imp_GetThemeSysColor
0x1801bd0be  jmp     short loc_1801BD0CB
0x1801bd0c0  mov     ecx, 1Bh; nIndex
0x1801bd0c5  call    cs:__imp_GetSysColor
0x1801bd0cb  mov     edx, 62h ; 'b'; percent
0x1801bd0d0  mov     ecx, eax; srcPixel
0x1801bd0d2  call    ?PixelAlpha@CDrawingManager@@SAKKH@Z; CDrawingManager::PixelAlpha(ulong,int)
0x1801bd0d7  lea     rbx, [rsi+1A0h]
0x1801bd0de  mov     [rsi+120h], eax
0x1801bd0e4  mov     this, rbx; this
0x1801bd0e7  call    ?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x1801bd0ec  lea     rdi, [rsi+1B0h]
0x1801bd0f3  mov     this, rdi; this
0x1801bd0f6  call    ?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x1801bd0fb  mov     ecx, [rsi+118h]; color
0x1801bd101  call    cs:__imp_CreateSolidBrush
0x1801bd107  mov     rdx, rax; hObject
0x1801bd10a  mov     this, rbx; this
0x1801bd10d  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1801bd112  mov     ecx, [rsi+11Ch]; color
0x1801bd118  call    cs:__imp_CreateSolidBrush
0x1801bd11e  mov     rdx, rax; hObject
0x1801bd121  mov     this, rdi; this
0x1801bd124  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1801bd129  lea     rbx, [rsi+1C0h]
0x1801bd130  mov     this, rbx; this
0x1801bd133  call    ?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x1801bd138  mov     ecx, [rsi+120h]; color
0x1801bd13e  call    cs:__imp_CreateSolidBrush
0x1801bd144  mov     rdx, rax; hObject
0x1801bd147  mov     this, rbx; this
0x1801bd14a  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1801bd14f  jmp     short loc_1801BD162
0x1801bd151  cmp     eax, 3
0x1801bd154  jz      short loc_1801BD162
0x1801bd156  mov     eax, [rsi+21Ch]
0x1801bd15c  mov     [rsi+238h], eax
0x1801bd162  mov     ecx, [rsi+108h]; srcPixel
0x1801bd168  mov     edx, 6Bh ; 'k'; percent
0x1801bd16d  call    ?PixelAlpha@CDrawingManager@@SAKKH@Z; CDrawingManager::PixelAlpha(ulong,int)
0x1801bd172  mov     this, [r14]; hTheme
0x1801bd175  mov     ebp, eax
0x1801bd177  test    this, this
0x1801bd17a  jz      short loc_1801BD189
0x1801bd17c  mov     edx, 0Dh; iColorId
0x1801bd181  call    cs:__imp_GetThemeSysColor
0x1801bd187  jmp     short loc_1801BD194
0x1801bd189  mov     ecx, 0Dh; nIndex
0x1801bd18e  call    cs:__imp_GetSysColor
0x1801bd194  mov     edi, eax
0x1801bd196  mov     r14d, 1
0x1801bd19c  mov     eax, [rsi+328h]
0x1801bd1a2  sub     eax, r14d
0x1801bd1a5  cmp     eax, r14d
0x1801bd1a8  ja      short loc_1801BD1D4
0x1801bd1aa  mov     ecx, [rsi+220h]; srcPixel
0x1801bd1b0  lea     edx, [r14+5Eh]; percent
0x1801bd1b4  call    ?PixelAlpha@CDrawingManager@@SAKKH@Z; CDrawingManager::PixelAlpha(ulong,int)
0x1801bd1b9  mov     ecx, [rsi+214h]; srcPixel
0x1801bd1bf  lea     edx, [r14+60h]; percent
0x1801bd1c3  mov     [rsi+218h], eax
0x1801bd1c9  call    ?PixelAlpha@CDrawingManager@@SAKKH@Z; CDrawingManager::PixelAlpha(ulong,int)
0x1801bd1ce  mov     [rsi+214h], eax
0x1801bd1d4  movsd   xmm2, cs:__real@3fed70a3d70a3d71; dblLumRatio
0x1801bd1dc  mov     ebx, 2
0x1801bd1e1  mov     edx, [rsi+220h]; color2
0x1801bd1e7  mov     r9d, r14d; k1
0x1801bd1ea  mov     ecx, [rsi+21Ch]; color1
0x1801bd1f0  mov     dword ptr [rsp+48h+pColor], ebx; k2
0x1801bd1f4  call    ?SmartMixColors@CDrawingManager@@SAKKKNHH@Z; CDrawingManager::SmartMixColors(ulong,ulong,double,int,int)
0x1801bd1f9  mov     [rsi+224h], eax
0x1801bd1ff  lea     r15, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; AFX_GLOBAL_DATA afxGlobalData
0x1801bd206  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x1801bd20d  jnz     short loc_1801BD21E
0x1801bd20f  mov     this, r15; this
0x1801bd212  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1801bd217  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r14d; AFX_GLOBAL_DATA afxGlobalData ...
0x1801bd21e  movsd   xmm2, cs:__real@3fe999999999999a; dblLumRatio
0x1801bd226  mov     r9d, r14d; k1
0x1801bd229  mov     edx, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrBarDkShadow; color2
0x1801bd22f  mov     ecx, [rsi+138h]; color1
0x1801bd235  mov     dword ptr [rsp+48h+pColor], ebx; k2
0x1801bd239  call    ?SmartMixColors@CDrawingManager@@SAKKKNHH@Z; CDrawingManager::SmartMixColors(ulong,ulong,double,int,int)
0x1801bd23e  mov     [rsi+124h], eax
0x1801bd244  lea     rbx, [rsi+308h]
0x1801bd24b  mov     this, rbx; this
0x1801bd24e  call    ?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x1801bd253  mov     ecx, ebp; color
0x1801bd255  call    cs:__imp_CreateSolidBrush
0x1801bd25b  mov     rdx, rax; hObject
0x1801bd25e  mov     this, rbx; this
0x1801bd261  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1801bd266  lea     rbx, [rsi+318h]
0x1801bd26d  mov     this, rbx; this
0x1801bd270  call    ?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x1801bd275  mov     ecx, edi; color
0x1801bd277  call    cs:__imp_CreateSolidBrush
0x1801bd27d  mov     rdx, rax; hObject
0x1801bd280  mov     this, rbx; this
0x1801bd283  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1801bd288  lea     rbx, [rsi+2F8h]
0x1801bd28f  mov     this, rbx; this
0x1801bd292  call    ?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x1801bd297  mov     r8d, [rsi+2F0h]; color
0x1801bd29e  cmp     r8d, 0FFFFFFFFh
0x1801bd2a2  jz      short loc_1801BD2BA
0x1801bd2a4  mov     edx, r14d; cWidth
0x1801bd2a7  xor     ecx, ecx; iStyle
0x1801bd2a9  call    cs:__imp_CreatePen
0x1801bd2af  mov     rdx, rax; hObject
0x1801bd2b2  mov     this, rbx; this
0x1801bd2b5  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1801bd2ba  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x1801bd2c1  mov     cs:?m_bDefaultWinXPColors@CMFCVisualManagerOffice2003@@1HA, r12d; int CMFCVisualManagerOffice2003::m_bDefaultWinXPColors
0x1801bd2c8  jnz     short loc_1801BD2D9
0x1801bd2ca  mov     this, r15; this
0x1801bd2cd  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1801bd2d2  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r14d; AFX_GLOBAL_DATA afxGlobalData ...
0x1801bd2d9  mov     eax, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrBtnDkShadow; AFX_GLOBAL_DATA afxGlobalData ...
0x1801bd2df  mov     [rsi+114h], eax
0x1801bd2e5  mov     eax, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized; AFX_GLOBAL_DATA afxGlobalData ...
0x1801bd2eb  test    eax, eax
0x1801bd2ed  jnz     short loc_1801BD300
0x1801bd2ef  mov     this, r15; this
0x1801bd2f2  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1801bd2f7  mov     eax, r14d
0x1801bd2fa  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, eax; AFX_GLOBAL_DATA afxGlobalData ...
0x1801bd300  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_nBitsPerPixel, 8; AFX_GLOBAL_DATA afxGlobalData ...
0x1801bd307  jle     short loc_1801BD37F
0x1801bd309  test    eax, eax
0x1801bd30b  jnz     short loc_1801BD31C
0x1801bd30d  mov     this, r15; this
0x1801bd310  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1801bd315  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r14d; AFX_GLOBAL_DATA afxGlobalData ...
0x1801bd31c  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bIsWhiteHighContrast, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x1801bd323  jnz     short loc_1801BD37F
0x1801bd325  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bIsBlackHighContrast, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x1801bd32c  jnz     short loc_1801BD37F
0x1801bd32e  lea     this, [rsi+1E0h]; this
0x1801bd335  call    ?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x1801bd33a  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x1801bd341  jnz     short loc_1801BD352
0x1801bd343  mov     this, r15; this
0x1801bd346  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1801bd34b  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r14d; AFX_GLOBAL_DATA afxGlobalData ...
0x1801bd352  mov     ecx, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrBarFace; srcPixel
0x1801bd358  mov     edx, 54h ; 'T'; percent
0x1801bd35d  call    ?PixelAlpha@CDrawingManager@@SAKKH@Z; CDrawingManager::PixelAlpha(ulong,int)
0x1801bd362  mov     r8d, eax; color
0x1801bd365  mov     edx, r14d; cWidth
  ... truncated ...
```
