# CMFCDesktopAlertWnd::CommonCreate(CPoint,CMFCDesktopAlertWndInfo *)

- ea: `0x18003e1c0`
- end: `0x18003e795`
- name: `?CommonCreate@CMFCDesktopAlertWnd@@IEAAHVCPoint@@PEAVCMFCDesktopAlertWndInfo@@@Z`
- size: `1493`
- prototype: `int __fastcall(CMFCDesktopAlertWnd *this, CPoint ptPos, CMFCDesktopAlertWndInfo *pParams)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003e0f0`
- `0x18003e150`

## callees

- `0x18000df50`
- `0x18001e760`
- `0x18003d6e0`
- `0x18003e1c0`
- `0x18003f3a0`
- `0x18006cab0`
- `0x180091f60`
- `0x180231d70`
- `0x180296d00`
- `0x1802973d0`
- `0x1802984e0`
- `0x1802b66c0`
- `0x1802b67c0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!GetForegroundWindow` at `0x18003e220`
- `USER32!GetForegroundWindow` at `0x18003e220`
- `USER32!GetMonitorInfoW` at `0x18003e445`
- `USER32!GetMonitorInfoW` at `0x18003e445`
- `USER32!MonitorFromPoint` at `0x18003e438`
- `USER32!MonitorFromPoint` at `0x18003e438`
- `USER32!SystemParametersInfoW` at `0x18003e46b`
- `USER32!SystemParametersInfoW` at `0x18003e46b`
- `USER32!SetForegroundWindow` at `0x18003e726`
- `USER32!SetForegroundWindow` at `0x18003e726`
- `USER32!LoadCursorW` at `0x18003e239`
- `USER32!LoadCursorW` at `0x18003e239`
- `USER32!GetFocus` at `0x18003e20f`
- `USER32!GetFocus` at `0x18003e20f`
- `USER32!CopyRect` at `0x18003e457`
- `USER32!CopyRect` at `0x18003e457`
- `USER32!OffsetRect` at `0x18003e585`
- `USER32!OffsetRect` at `0x18003e585`
- `USER32!SetTimer` at `0x18003e70e`
- `USER32!SetTimer` at `0x18003e70e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMFCDesktopAlertWnd::CommonCreate(
        CMFCDesktopAlertWnd *this,
        CPoint ptPos,
        CMFCDesktopAlertWndInfo *pParams)
{
  HWND Focus; // rax
  CWnd *v6; // r12
  HWND ForegroundWindow; // rax
  HCURSOR CursorW; // rax
  const wchar_t *v9; // rax
  unsigned int v10; // ebx
  int v11; // r13d
  __int64 m_uiDlgResID; // rdx
  wchar_t *v13; // rdx
  CMFCDesktopAlertDialog *m_pWndDlg; // rax
  CSize m_sizeDlg; // rax
  CSize *v17; // rax
  int v18; // ebx
  int v19; // r14d
  int v20; // r15d
  int m_bHasCloseButton; // edx
  int cx; // esi
  DWORD v23; // edx
  HMONITOR v24; // rax
  __int64 right; // r9
  int left; // r10d
  __int64 bottom; // r8
  int top; // r11d
  int v29; // ecx
  int cy; // edx
  int m_nBtnMarginVert; // edx
  CWnd *v32; // r15
  int v33; // ecx
  int v34; // edx
  int v35; // edx
  HWND m_hWnd; // rcx
  wchar_t *v37; // rdx
  CSize sizeDialog; // [rsp+50h] [rbp-59h] BYREF
  int v39; // [rsp+58h] [rbp-51h]
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strClassName; // [rsp+60h] [rbp-49h] BYREF
  CWnd *v41; // [rsp+68h] [rbp-41h]
  CRect rectDummy; // [rsp+70h] [rbp-39h] BYREF
  CRect rectScreen; // [rsp+80h] [rbp-29h] BYREF
  CRect rectBtn; // [rsp+90h] [rbp-19h] BYREF
  tagMONITORINFO mi; // [rsp+A0h] [rbp-9h] BYREF
  POINT pt; // [rsp+118h] [rbp+6Fh] BYREF

  pt = ptPos.tagPOINT;
  this->m_ptLastPos = ptPos;
  v39 = this->GetCaptionHeight(this);
  Focus = GetFocus();
  v6 = CWnd::FromHandle(Focus);
  ForegroundWindow = GetForegroundWindow();
  v41 = CWnd::FromHandle(ForegroundWindow);
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
  v9 = AfxRegisterWndClass(0x800u, CursorW, (HBRUSH__ *)0x10, 0);
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    &strClassName,
    v9);
  rectDummy = 0;
  v10 = 136;
  v11 = 0;
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    afxGlobalData.m_bInitialized = 1;
  }
  if ( afxGlobalData.m_nBitsPerPixel > 8 && this->m_nTransparency != 0xFF )
    v10 = 524424;
  if ( CWnd::CreateEx(this, v10, strClassName.m_pszData, &CmdLine, 0x80000000, &rectDummy, 0, 0, 0) )
  {
    this->m_pWndDlg->m_bDontSetFocus = 1;
    m_uiDlgResID = this->m_uiDlgResID;
    if ( (_DWORD)m_uiDlgResID )
    {
      if ( this->m_pWndDlg->Create(this->m_pWndDlg, m_uiDlgResID, this) )
      {
        sizeDialog = *this->GetDialogSize(this, &sizeDialog);
        goto LABEL_19;
      }
    }
    else
    {
      if ( !pParams )
        AfxThrowInvalidArgException();
      if ( CMFCDesktopAlertDialog::CreateFromParams(this->m_pWndDlg, pParams, this) )
      {
        m_pWndDlg = this->m_pWndDlg;
        if ( m_pWndDlg->m_bDefault )
        {
          m_sizeDlg = m_pWndDlg->m_sizeDlg;
        }
        else
        {
          sizeDialog = 0;
          m_sizeDlg = 0;
        }
        sizeDialog = m_sizeDlg;
LABEL_19:
        this->m_pWndDlg->m_bDontSetFocus = 0;
        v17 = CMenuImages::Size((CSize *)&rectDummy);
        v18 = v17->cy + 6;
        v19 = v17->cx + 6;
        v20 = v17->cy + 8;
        LOBYTE(v11) = v20 <= v39;
        if ( v20 > v39 && ((m_bHasCloseButton = this->m_bHasCloseButton) != 0 || this->m_hMenu) )
        {
          cx = sizeDialog.cx + this->m_nBtnMarginHorz;
          if ( m_bHasCloseButton )
            cx += v19;
          if ( this->m_hMenu )
            cx += v19;
        }
        else
        {
          cx = sizeDialog.cx;
        }
        rectScreen = 0;
        mi.cbSize = 40;
        if ( pt.x != -1 || (v23 = 1, pt.y != -1) )
          v23 = 2;
        v24 = MonitorFromPoint(pt, v23);
        if ( GetMonitorInfoW(v24, &mi) )
          CopyRect(&rectScreen, &mi.rcWork);
        else
          SystemParametersInfoW(0x30u, 0, &rectScreen, 0);
        right = (unsigned int)rectScreen.right;
        left = rectScreen.left;
        if ( rectScreen.right - rectScreen.left - 2 < cx )
          cx = rectScreen.right - rectScreen.left - 2;
        sizeDialog.cx = cx;
        bottom = (unsigned int)rectScreen.bottom;
        top = rectScreen.top;
        v29 = v39;
        cy = sizeDialog.cy;
        if ( rectScreen.bottom - rectScreen.top - v39 - 2 < sizeDialog.cy )
          cy = rectScreen.bottom - rectScreen.top - v39 - 2;
        sizeDialog.cy = cy;
        this->m_FinalSize = sizeDialog;
        this->m_FinalSize.cy += v29 + 2;
        this->m_FinalSize.cx += 2;
        if ( v20 > v29 )
        {
          v32 = this->m_pWndDlg;
          m_nBtnMarginVert = this->m_nBtnMarginVert;
        }
        else
        {
          m_nBtnMarginVert = (v29 - v18) / 2 + 1;
          v32 = this;
        }
        v33 = cx - this->m_nBtnMarginHorz;
        rectBtn.left = v33 - v19;
        rectBtn.right = v33;
        rectBtn.top = m_nBtnMarginVert;
        rectBtn.bottom = v18 + m_nBtnMarginVert;
        if ( this->m_bHasCloseButton )
        {
          this->m_btnClose.Create(&this->m_btnClose, &CmdLine, 1342177280u, &rectBtn, v32, -1u);
          CMFCButton::SetStdImage(&this->m_btnClose, IdClose, ImageBlack, IdArrowDown);
          this->m_btnClose.m_bDrawFocus = 0;
          this->m_btnClose.m_nFlatStyle = BUTTONSTYLE_FLAT;
          this->m_btnClose.m_bIsCaptionButton = v11;
          this->m_btnClose.m_bIsCloseButton = 1;
          OffsetRect(&rectBtn, ~v19, 0);
          bottom = (unsigned int)rectScreen.bottom;
          right = (unsigned int)rectScreen.right;
          top = rectScreen.top;
          left = rectScreen.left;
        }
        if ( this->m_hMenu )
        {
          this->m_btnMenu.Create(&this->m_btnMenu, &CmdLine, 1342177280u, &rectBtn, v32, -1u);
          CMFCButton::SetStdImage(&this->m_btnMenu, IdArrowDownLarge, ImageBlack, IdArrowDown);
          this->m_btnMenu.m_bDrawFocus = 0;
          this->m_btnMenu.m_nFlatStyle = BUTTONSTYLE_FLAT;
          this->m_btnMenu.m_bIsCaptionButton = v11;
          bottom = (unsigned int)rectScreen.bottom;
          right = (unsigned int)rectScreen.right;
          top = rectScreen.top;
          left = rectScreen.left;
        }
        if ( pt.x == -1 && pt.y == -1 )
        {
          right = (unsigned int)(right - this->m_FinalSize.cx);
          pt.x = right;
          bottom = (unsigned int)(bottom - this->m_FinalSize.cy);
        }
        else
        {
          if ( pt.x >= left )
          {
            v34 = this->m_FinalSize.cx;
            if ( v34 + pt.x > (int)right )
            {
              right = (unsigned int)(right - v34);
              pt.x = right;
            }
          }
          else
          {
            pt.x = left;
          }
          if ( pt.y < top )
          {
            pt.y = top;
            goto LABEL_56;
          }
          v35 = this->m_FinalSize.cy;
          if ( v35 + pt.y <= (int)bottom )
          {
LABEL_56:
            ((void (__fastcall *)(CMFCDesktopAlertWnd *, POINT *, __int64, __int64))this->OnBeforeShow)(
              this,
              &pt,
              bottom,
              right);
            CWnd::SetWindowPos(this, &CWnd::wndTop, pt.x, pt.y, this->m_FinalSize.cx, this->m_FinalSize.cy, 0x50u);
            CMFCDesktopAlertWnd::StartAnimation(this, 1);
            CWnd::SetWindowPos(this->m_pWndDlg, 0, 1, v39 + 1, cx, sizeDialog.cy, 0x14u);
            SetTimer(this->m_hWnd, 0xEC10u, 0x64u, 0);
            if ( v41 )
            {
              m_hWnd = v41->m_hWnd;
              if ( m_hWnd )
                SetForegroundWindow(m_hWnd);
            }
            if ( v6 && v6->m_hWnd )
              CWnd::SetFocus(v6);
            v37 = strClassName.m_pszData - 12;
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)strClassName.m_pszData - 2, 0xFFFFFFFF) <= 1 )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v37 + 8LL))(*(_QWORD *)v37);
            return 1;
          }
          bottom = (unsigned int)(bottom - v35);
        }
        pt.y = bottom;
        goto LABEL_56;
      }
    }
  }
  v13 = strClassName.m_pszData - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)strClassName.m_pszData - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 8LL))(*(_QWORD *)v13);
  return 0;
}

```

## disassembly

```asm
0x18003e1c0  mov     [rsp-8+arg_18], rbx
0x18003e1c5  mov     qword ptr [rsp-8+pt.x], ptPos
0x18003e1ca  push    rbp
0x18003e1cb  push    rsi
0x18003e1cc  push    rdi
0x18003e1cd  push    r12
0x18003e1cf  push    r13
0x18003e1d1  push    r14
0x18003e1d3  push    r15
0x18003e1d5  lea     rbp, [rsp-27h]
0x18003e1da  sub     rsp, 0D0h
0x18003e1e1  mov     rax, cs:__security_cookie
0x18003e1e8  xor     rax, rsp
0x18003e1eb  mov     [rbp+57h+var_38], rax
0x18003e1ef  mov     rsi, pParams
0x18003e1f2  mov     rdi, this
0x18003e1f5  mov     [this+0F0h], ptPos
0x18003e1fc  mov     rax, [this]
0x18003e1ff  mov     rax, [rax+300h]
0x18003e206  call    cs:__guard_dispatch_icall_fptr
0x18003e20c  mov     [rbp+57h+var_A8], eax
0x18003e20f  call    cs:__imp_GetFocus
0x18003e215  mov     this, rax; hWnd
0x18003e218  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x18003e21d  mov     r12, rax
0x18003e220  call    cs:__imp_GetForegroundWindow
0x18003e226  mov     this, rax; hWnd
0x18003e229  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x18003e22e  mov     [rbp+57h+var_98], rax
0x18003e232  mov     edx, 7F00h; lpCursorName
0x18003e237  xor     ecx, ecx; hInstance
0x18003e239  call    cs:__imp_LoadCursorW
0x18003e23f  mov     ptPos, rax; hCursor
0x18003e242  xor     r9d, r9d; hIcon
0x18003e245  mov     ecx, 800h; nClassStyle
0x18003e24a  lea     r8d, [r9+10h]; hbrBackground
0x18003e24e  call    ?AfxRegisterWndClass@@YAPEB_WIPEAUHICON__@@PEAUHBRUSH__@@0@Z; AfxRegisterWndClass(uint,HICON__ *,HBRUSH__ *,HICON__ *)
0x18003e253  mov     ptPos, rax; pszSrc
0x18003e256  lea     this, [rbp+57h+strClassName]; this
0x18003e25a  call    ??0?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x18003e25f  nop
0x18003e260  xorps   xmm0, xmm0
0x18003e263  movups  xmmword ptr [rbp+57h+rectDummy.left], xmm0
0x18003e267  mov     ebx, 88h
0x18003e26c  mov     r14d, 1
0x18003e272  xor     r13d, r13d
0x18003e275  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r13d; AFX_GLOBAL_DATA afxGlobalData ...
0x18003e27c  jnz     short loc_18003E291
0x18003e27e  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x18003e285  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18003e28a  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r14d; AFX_GLOBAL_DATA afxGlobalData ...
0x18003e291  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_nBitsPerPixel, 8; AFX_GLOBAL_DATA afxGlobalData ...
0x18003e298  jle     short loc_18003E2A9
0x18003e29a  mov     eax, 80088h
0x18003e29f  cmp     byte ptr [rdi+120h], 0FFh
0x18003e2a6  cmovb   ebx, eax
0x18003e2a9  mov     [rsp+100h+lpParam], r13; lpParam
0x18003e2ae  mov     [rsp+100h+nID], r13d; nID
0x18003e2b3  mov     [rsp+100h+pParentWnd], r13; pParentWnd
0x18003e2b8  lea     rax, [rbp+57h+rectDummy]
0x18003e2bc  mov     [rsp+100h+rect], rax; rect
0x18003e2c1  mov     [rsp+100h+dwStyle], 80000000h; dwStyle
0x18003e2c9  lea     r9, CmdLine; lpszWindowName
0x18003e2d0  mov     pParams, [rbp+57h+strClassName.m_pszData]; lpszClassName
0x18003e2d4  mov     edx, ebx; dwExStyle
0x18003e2d6  mov     this, rdi; this
0x18003e2d9  call    ?CreateEx@CWnd@@UEAAHKPEB_W0KAEBUtagRECT@@PEAV1@IPEAX@Z; CWnd::CreateEx(ulong,wchar_t const *,wchar_t const *,ulong,tagRECT const &,CWnd *,uint,void *)
0x18003e2de  test    eax, eax
0x18003e2e0  jz      short loc_18003E357
0x18003e2e2  mov     rax, [rdi+130h]
0x18003e2e9  mov     [rax+0EB4h], r14d
0x18003e2f0  mov     edx, [rdi+110h]
0x18003e2f6  test    edx, edx
0x18003e2f8  jz      short loc_18003E338
0x18003e2fa  mov     this, [rdi+130h]
0x18003e301  mov     rax, [this]
0x18003e304  mov     pParams, rdi
0x18003e307  mov     rax, [rax+2D8h]
0x18003e30e  call    cs:__guard_dispatch_icall_fptr
0x18003e314  test    eax, eax
0x18003e316  jz      short loc_18003E357
0x18003e318  mov     rax, [rdi]
0x18003e31b  lea     ptPos, [rbp+57h+sizeDialog]
0x18003e31f  mov     this, rdi
0x18003e322  mov     rax, [rax+2E8h]
0x18003e329  call    cs:__guard_dispatch_icall_fptr
0x18003e32f  mov     this, [rax]
0x18003e332  mov     qword ptr [rbp+57h+sizeDialog.cx], this
0x18003e336  jmp     short loc_18003E3A7
0x18003e338  test    rsi, rsi
0x18003e33b  jz      loc_18003E78F
0x18003e341  mov     pParams, rdi; pParent
0x18003e344  mov     ptPos, rsi; params
0x18003e347  mov     this, [rdi+130h]; this
0x18003e34e  call    ?CreateFromParams@CMFCDesktopAlertDialog@@QEAAHAEAVCMFCDesktopAlertWndInfo@@PEAVCMFCDesktopAlertWnd@@@Z; CMFCDesktopAlertDialog::CreateFromParams(CMFCDesktopAlertWndInfo &,CMFCDesktopAlertWnd *)
0x18003e353  test    eax, eax
0x18003e355  jnz     short loc_18003E383
0x18003e357  mov     ptPos, [rbp+57h+strClassName.m_pszData]
0x18003e35b  add     ptPos, 0FFFFFFFFFFFFFFE8h
0x18003e35f  or      eax, 0FFFFFFFFh
0x18003e362  lock xadd [ptPos+10h], eax
0x18003e367  sub     eax, 1
0x18003e36a  jg      short loc_18003E37C
0x18003e36c  mov     this, [ptPos]
0x18003e36f  mov     rax, [this]
0x18003e372  mov     rax, [rax+8]
0x18003e376  call    cs:__guard_dispatch_icall_fptr
0x18003e37c  xor     eax, eax
0x18003e37e  jmp     loc_18003E768
0x18003e383  mov     rax, [rdi+130h]
0x18003e38a  cmp     [rax+0EB0h], r13d
0x18003e391  jnz     short loc_18003E39C
0x18003e393  mov     qword ptr [rbp+57h+sizeDialog.cx], r13
0x18003e397  mov     rax, r13
0x18003e39a  jmp     short loc_18003E3A3
0x18003e39c  mov     rax, [rax+0EA8h]
0x18003e3a3  mov     qword ptr [rbp+57h+sizeDialog.cx], rax
0x18003e3a7  mov     rax, [rdi+130h]
0x18003e3ae  mov     [rax+0EB4h], r13d
0x18003e3b5  lea     this, [rbp+57h+rectDummy]; result
0x18003e3b9  call    ?Size@CMenuImages@@SA?AVCSize@@XZ; CMenuImages::Size(void)
0x18003e3be  mov     ebx, [rax+4]
0x18003e3c1  add     ebx, 6
0x18003e3c4  mov     r14d, [rax]
0x18003e3c7  add     r14d, 6
0x18003e3cb  lea     r15d, [rbx+2]
0x18003e3cf  cmp     r15d, [rbp+57h+var_A8]
0x18003e3d3  setle   r13b
0x18003e3d7  jle     short loc_18003E40C
0x18003e3d9  mov     edx, [rdi+108h]
0x18003e3df  test    edx, edx
0x18003e3e1  jnz     short loc_18003E3ED
0x18003e3e3  cmp     qword ptr [rdi+128h], 0
0x18003e3eb  jz      short loc_18003E40C
0x18003e3ed  mov     esi, [rdi+11Ch]
0x18003e3f3  add     esi, [rbp+57h+sizeDialog.cx]
0x18003e3f6  test    edx, edx
0x18003e3f8  jz      short loc_18003E3FD
0x18003e3fa  add     esi, r14d
0x18003e3fd  cmp     qword ptr [rdi+128h], 0
0x18003e405  jz      short loc_18003E40F
0x18003e407  add     esi, r14d
0x18003e40a  jmp     short loc_18003E40F
0x18003e40c  mov     esi, [rbp+57h+sizeDialog.cx]
0x18003e40f  xorps   xmm0, xmm0
0x18003e412  movdqu  xmmword ptr [rbp+57h+rectScreen.left], xmm0
0x18003e417  mov     [rbp+57h+mi.cbSize], 28h ; '('
0x18003e41e  cmp     [rbp+57h+pt.x], 0FFFFFFFFh
0x18003e422  jnz     short loc_18003E42F
0x18003e424  cmp     [rbp+57h+pt.y], 0FFFFFFFFh
0x18003e428  mov     edx, 1
0x18003e42d  jz      short loc_18003E434
0x18003e42f  mov     edx, 2; dwFlags
0x18003e434  mov     this, qword ptr [rbp+57h+pt.x]; pt
0x18003e438  call    cs:__imp_MonitorFromPoint
0x18003e43e  mov     this, rax; hMonitor
0x18003e441  lea     ptPos, [rbp+57h+mi]; lpmi
0x18003e445  call    cs:__imp_GetMonitorInfoW
0x18003e44b  test    eax, eax
0x18003e44d  jz      short loc_18003E45F
0x18003e44f  lea     ptPos, [rbp+57h+mi.rcWork]; lprcSrc
0x18003e453  lea     this, [rbp+57h+rectScreen]; lprcDst
0x18003e457  call    cs:__imp_CopyRect
0x18003e45d  jmp     short loc_18003E471
0x18003e45f  xor     r9d, r9d; fWinIni
0x18003e462  lea     pParams, [rbp+57h+rectScreen]; pvParam
0x18003e466  xor     edx, edx; uiParam
0x18003e468  lea     ecx, [ptPos+30h]; uiAction
0x18003e46b  call    cs:__imp_SystemParametersInfoW
0x18003e471  mov     r9d, [rbp+57h+rectScreen.right]
0x18003e475  mov     eax, r9d
0x18003e478  mov     r10d, [rbp+57h+rectScreen.left]
0x18003e47c  sub     eax, r10d
0x18003e47f  add     eax, 0FFFFFFFEh
0x18003e482  cmp     eax, esi
0x18003e484  cmovl   esi, eax
0x18003e487  mov     [rbp+57h+sizeDialog.cx], esi
0x18003e48a  mov     r8d, [rbp+57h+rectScreen.bottom]
0x18003e48e  mov     eax, r8d
0x18003e491  mov     r11d, [rbp+57h+rectScreen.top]
0x18003e495  sub     eax, r11d
0x18003e498  mov     ecx, [rbp+57h+var_A8]
0x18003e49b  sub     eax, ecx
0x18003e49d  add     eax, 0FFFFFFFEh
0x18003e4a0  mov     edx, [rbp+57h+sizeDialog.cy]
0x18003e4a3  cmp     eax, edx
0x18003e4a5  cmovl   edx, eax
0x18003e4a8  mov     [rbp+57h+sizeDialog.cy], edx
0x18003e4ab  mov     rax, qword ptr [rbp+57h+sizeDialog.cx]
0x18003e4af  mov     [rdi+17BCh], rax
0x18003e4b6  lea     eax, [this+2]
0x18003e4b9  add     [rdi+17C0h], eax
0x18003e4bf  add     dword ptr [rdi+17BCh], 2
0x18003e4c6  cmp     r15d, ecx
0x18003e4c9  jg      short loc_18003E4DC
0x18003e4cb  mov     eax, ecx
0x18003e4cd  sub     eax, ebx
0x18003e4cf  cdq
0x18003e4d0  sub     eax, edx
0x18003e4d2  sar     eax, 1
0x18003e4d4  lea     edx, [rax+1]
0x18003e4d7  mov     r15, rdi
0x18003e4da  jmp     short loc_18003E4E9
0x18003e4dc  mov     r15, [rdi+130h]
0x18003e4e3  mov     edx, [rdi+118h]
0x18003e4e9  mov     ecx, esi
0x18003e4eb  sub     ecx, [rdi+11Ch]
0x18003e4f1  mov     eax, ecx
0x18003e4f3  sub     eax, r14d
0x18003e4f6  mov     [rbp+57h+rectBtn.left], eax
0x18003e4f9  mov     [rbp+57h+rectBtn.right], ecx
0x18003e4fc  mov     [rbp+57h+rectBtn.top], edx
0x18003e4ff  lea     eax, [rbx+ptPos]
0x18003e502  mov     [rbp+57h+rectBtn.bottom], eax
0x18003e505  cmp     dword ptr [rdi+108h], 0
0x18003e50c  jz      loc_18003E59D
0x18003e512  lea     rbx, [rdi+138h]
0x18003e519  mov     rax, [rbx]
0x18003e51c  or      dword ptr [rsp+100h+rect], 0FFFFFFFFh
0x18003e521  mov     qword ptr [rsp+100h+dwStyle], r15
0x18003e526  lea     r9, [rbp+57h+rectBtn]
0x18003e52a  mov     r8d, 50000000h
0x18003e530  lea     ptPos, CmdLine
0x18003e537  mov     this, rbx
0x18003e53a  mov     rax, [rax+2D8h]
0x18003e541  call    cs:__guard_dispatch_icall_fptr
0x18003e547  xor     r9d, r9d; idDisabled
0x18003e54a  xor     r8d, r8d; state
0x18003e54d  lea     edx, [r9+5]; id
0x18003e551  mov     this, rbx; this
0x18003e554  call    ?SetStdImage@CMFCButton@@QEAAXW4IMAGES_IDS@CMenuImages@@W4IMAGE_STATE@3@0@Z; CMFCButton::SetStdImage(CMenuImages::IMAGES_IDS,CMenuImages::IMAGE_STATE,CMenuImages::IMAGES_IDS)
0x18003e559  and     dword ptr [rdi+234h], 0
0x18003e560  mov     ebx, 1
0x18003e565  mov     [rdi+220h], ebx
0x18003e56b  mov     [rdi+0C58h], r13d
0x18003e572  mov     [rdi+0C5Ch], ebx
0x18003e578  not     r14d
0x18003e57b  xor     r8d, r8d; dy
0x18003e57e  mov     edx, r14d; dx
0x18003e581  lea     this, [rbp+57h+rectBtn]; lprc
0x18003e585  call    cs:__imp_OffsetRect
0x18003e58b  mov     r8d, [rbp+57h+rectScreen.bottom]
0x18003e58f  mov     r9d, [rbp+57h+rectScreen.right]
0x18003e593  mov     r11d, [rbp+57h+rectScreen.top]
0x18003e597  mov     r10d, [rbp+57h+rectScreen.left]
0x18003e59b  jmp     short loc_18003E5A2
0x18003e59d  mov     ebx, 1
0x18003e5a2  xor     r14d, r14d
0x18003e5a5  cmp     [rdi+128h], r14
0x18003e5ac  jz      short loc_18003E61D
0x18003e5ae  lea     rbx, [rdi+0C60h]
0x18003e5b5  mov     rax, [rbx]
0x18003e5b8  or      dword ptr [rsp+100h+rect], 0FFFFFFFFh
0x18003e5bd  mov     qword ptr [rsp+100h+dwStyle], r15
0x18003e5c2  lea     r9, [rbp+57h+rectBtn]
0x18003e5c6  mov     r8d, 50000000h
0x18003e5cc  lea     ptPos, CmdLine
0x18003e5d3  mov     this, rbx
0x18003e5d6  mov     rax, [rax+2D8h]
0x18003e5dd  call    cs:__guard_dispatch_icall_fptr
0x18003e5e3  xor     r9d, r9d; idDisabled
0x18003e5e6  xor     r8d, r8d; state
0x18003e5e9  lea     edx, [r14+0Dh]; id
0x18003e5ed  mov     this, rbx; this
0x18003e5f0  call    ?SetStdImage@CMFCButton@@QEAAXW4IMAGES_IDS@CMenuImages@@W4IMAGE_STATE@3@0@Z; CMFCButton::SetStdImage(CMenuImages::IMAGES_IDS,CMenuImages::IMAGE_STATE,CMenuImages::IMAGES_IDS)
0x18003e5f5  mov     [rdi+0D5Ch], r14d
0x18003e5fc  lea     ebx, [r14+1]
0x18003e600  mov     [rdi+0D48h], ebx
0x18003e606  mov     [rdi+1780h], r13d
0x18003e60d  mov     r8d, [rbp+57h+rectScreen.bottom]
0x18003e611  mov     r9d, [rbp+57h+rectScreen.right]
0x18003e615  mov     r11d, [rbp+57h+rectScreen.top]
0x18003e619  mov     r10d, [rbp+57h+rectScreen.left]
0x18003e61d  mov     ecx, [rbp+57h+pt.y]
0x18003e620  mov     eax, [rbp+57h+pt.x]
0x18003e623  cmp     eax, 0FFFFFFFFh
0x18003e626  jnz     short loc_18003E640
0x18003e628  cmp     ecx, eax
0x18003e62a  jnz     short loc_18003E640
0x18003e62c  sub     r9d, [rdi+17BCh]
0x18003e633  mov     [rbp+57h+pt.x], r9d
0x18003e637  sub     r8d, [rdi+17C0h]
0x18003e63e  jmp     short loc_18003E67B
0x18003e640  cmp     eax, r10d
0x18003e643  jge     short loc_18003E64B
0x18003e645  mov     [rbp+57h+pt.x], r10d
0x18003e649  jmp     short loc_18003E65F
0x18003e64b  mov     edx, [rdi+17BCh]
0x18003e651  add     eax, edx
0x18003e653  cmp     eax, r9d
0x18003e656  jle     short loc_18003E65F
0x18003e658  sub     r9d, edx
0x18003e65b  mov     [rbp+57h+pt.x], r9d
0x18003e65f  cmp     ecx, r11d
0x18003e662  jge     short loc_18003E66A
0x18003e664  mov     [rbp+57h+pt.y], r11d
0x18003e668  jmp     short loc_18003E67F
0x18003e66a  mov     edx, [rdi+17C0h]
0x18003e670  lea     eax, [ptPos+this]
0x18003e673  cmp     eax, r8d
  ... truncated ...
```
