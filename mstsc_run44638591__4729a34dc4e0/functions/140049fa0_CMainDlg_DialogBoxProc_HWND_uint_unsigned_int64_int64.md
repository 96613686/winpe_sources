# CMainDlg::DialogBoxProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x140049fa0`
- end: `0x14004b15b`
- name: `?DialogBoxProc@CMainDlg@@UEAA_JPEAUHWND__@@I_K_J@Z`
- size: `4539`
- prototype: `__int64 __fastcall(CMainDlg *__hidden this, HWND, unsigned int, unsigned __int64, LPARAM lParam)`
- caller_count: `1`
- callee_count: `68`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14004cd90`

## callees

- `0x140003b2c`
- `0x140004703`
- `0x140008a34`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000d078`
- `0x140013c08`
- `0x14001b344`
- `0x14001e158`
- `0x14001eec8`
- `0x1400283b8`
- `0x1400287f0`
- `0x140028bf0`
- `0x140028e10`
- `0x140029d34`
- `0x14002a7d8`
- `0x14002b650`
- `0x140049898`
- `0x140049b18`
- `0x140049f4c`
- `0x140049fa0`
- `0x14004b164`
- `0x14004b2cc`
- `0x14004b4e0`
- `0x14004b6d8`
- `0x14004b7fc`
- `0x14004bee4`
- `0x14004bf94`
- `0x14004c0b0`
- `0x14004c158`
- `0x14004c26c`
- `0x14004c2f4`
- `0x14004c450`
- `0x14004c4b0`
- `0x14004c958`
- `0x14004c9dc`
- `0x14004cc3c`
- `0x14004ce0c`
- `0x14004cf9c`
- `0x14004d40c`
- `0x14004dd40`
- `0x14004ddd0`
- `0x14006150c`
- `0x140061898`
- `0x140061904`
- `0x14006698c`
- `0x1400669a4`
- `0x140097c30`
- `0x1400a0580`

## import_xrefs

- `USER32!DrawFocusRect` at `0x14004a879`
- `USER32!DrawFocusRect` at `0x14004a879`
- `USER32!GetFocus` at `0x14004a8b8`
- `USER32!GetFocus` at `0x14004a8b8`
- `USER32!EndPaint` at `0x14004a225`
- `USER32!EndPaint` at `0x14004a225`
- `USER32!BeginPaint` at `0x14004a1c6`
- `USER32!BeginPaint` at `0x14004a1c6`
- `USER32!SendDlgItemMessageW` at `0x14004b110`
- `USER32!SendDlgItemMessageW` at `0x14004b110`
- `USER32!SetWindowLongW` at `0x14004a337`
- `USER32!SetWindowLongW` at `0x14004a337`
- `USER32!UpdateWindow` at `0x14004ad05`
- `USER32!UpdateWindow` at `0x14004ad05`
- `USER32!InvalidateRect` at `0x14004a18b`
- `USER32!InvalidateRect` at `0x14004acfc`
- `USER32!InvalidateRect` at `0x14004a18b`
- `USER32!InvalidateRect` at `0x14004acfc`
- `USER32!SetWindowTextW` at `0x14004a4f7`
- `USER32!SetWindowTextW` at `0x14004a65a`
- `USER32!SetWindowTextW` at `0x14004b0d0`
- `USER32!SetWindowTextW` at `0x14004a4f7`
- `USER32!SetWindowTextW` at `0x14004a65a`
- `USER32!SetWindowTextW` at `0x14004b0d0`
- `USER32!GetWindowLongW` at `0x14004a325`
- `USER32!GetWindowLongW` at `0x14004a325`
- `USER32!GetWindowRect` at `0x14004a6b2`
- `USER32!GetWindowRect` at `0x14004a6d4`
- `USER32!GetWindowRect` at `0x14004a6b2`
- `USER32!GetWindowRect` at `0x14004a6d4`
- `USER32!SetForegroundWindow` at `0x14004a315`
- `USER32!SetForegroundWindow` at `0x14004a559`
- `USER32!SetForegroundWindow` at `0x14004a315`
- `USER32!SetForegroundWindow` at `0x14004a559`
- `USER32!SetWindowLongPtrW` at `0x14004a897`
- `USER32!SetWindowLongPtrW` at `0x14004a897`
- `USER32!GetDlgItem` at `0x14004a471`
- `USER32!GetDlgItem` at `0x14004a64e`
- `USER32!GetDlgItem` at `0x14004a6be`
- `USER32!GetDlgItem` at `0x14004a720`
- `USER32!GetDlgItem` at `0x14004a8af`
- `USER32!GetDlgItem` at `0x14004aa13`
- `USER32!GetDlgItem` at `0x14004aa67`
- `USER32!GetDlgItem` at `0x14004abb0`
- `USER32!GetDlgItem` at `0x14004b0bf`
- `USER32!GetDlgItem` at `0x14004a471`
- `USER32!GetDlgItem` at `0x14004a64e`
- `USER32!GetDlgItem` at `0x14004a6be`
- `USER32!GetDlgItem` at `0x14004a720`
- `USER32!GetDlgItem` at `0x14004a8af`
- `USER32!GetDlgItem` at `0x14004aa13`
- `USER32!GetDlgItem` at `0x14004aa67`
- `USER32!GetDlgItem` at `0x14004abb0`
- `USER32!GetDlgItem` at `0x14004b0bf`
- `USER32!SetFocus` at `0x14004a550`
- `USER32!SetFocus` at `0x14004a8d1`
- `USER32!SetFocus` at `0x14004ac02`
- `USER32!SetFocus` at `0x14004a550`
- `USER32!SetFocus` at `0x14004a8d1`
- `USER32!SetFocus` at `0x14004ac02`
- `USER32!EndDialog` at `0x14004aa9e`
- `USER32!EndDialog` at `0x14004aa9e`
- `USER32!SendMessageW` at `0x14004a494`
- `USER32!SendMessageW` at `0x14004a734`
- `USER32!SendMessageW` at `0x14004a8ec`
- `USER32!SendMessageW` at `0x14004a97d`
- `USER32!SendMessageW` at `0x14004aa27`
- `USER32!SendMessageW` at `0x14004aa7b`
- `USER32!SendMessageW` at `0x14004aadd`
- `USER32!SendMessageW` at `0x14004aed4`
- `USER32!SendMessageW` at `0x14004aef5`
- `USER32!SendMessageW` at `0x14004af11`
- `USER32!SendMessageW` at `0x14004af6c`
- `USER32!SendMessageW` at `0x14004b0f2`
- `USER32!SendMessageW` at `0x14004a494`
- `USER32!SendMessageW` at `0x14004a734`
- `USER32!SendMessageW` at `0x14004a8ec`
- `USER32!SendMessageW` at `0x14004a97d`
- `USER32!SendMessageW` at `0x14004aa27`
- `USER32!SendMessageW` at `0x14004aa7b`
- `USER32!SendMessageW` at `0x14004aadd`
- `USER32!SendMessageW` at `0x14004aed4`
- `USER32!SendMessageW` at `0x14004aef5`
- `USER32!SendMessageW` at `0x14004af11`
- `USER32!SendMessageW` at `0x14004af6c`
- `USER32!SendMessageW` at `0x14004b0f2`
- `USER32!PostMessageW` at `0x14004aab6`
- `USER32!PostMessageW` at `0x14004aab6`
- `KERNEL32!MulDiv` at `0x14004a6f3`
- `KERNEL32!MulDiv` at `0x14004af54`
- `KERNEL32!MulDiv` at `0x14004a6f3`
- `KERNEL32!MulDiv` at `0x14004af54`
- `COMCTL32!ImageList_Destroy` at `0x14004ae84`
- `COMCTL32!ImageList_Destroy` at `0x14004ae84`
- `COMCTL32!__imp_SetWindowSubclass` at `0x14004a4aa`
- `COMCTL32!__imp_SetWindowSubclass` at `0x14004a4aa`

## string_xrefs

- `0x14004ab37`: `StringCchCopy failed!`

## pseudocode

```c
__int64 __fastcall CMainDlg::DialogBoxProc(
        CMainDlg *this,
        HWND a2,
        unsigned int a3,
        unsigned __int64 a4,
        LPARAM lParam)
{
  unsigned __int64 v5; // rbx
  __int64 v7; // rsi
  const unsigned __int16 *v10; // r9
  unsigned int ScreenBpp; // eax
  CBrandingBar *v12; // rcx
  PVOID *v13; // rcx
  unsigned int v14; // eax
  unsigned int v15; // eax
  CProgressBand *v16; // rcx
  unsigned int v17; // eax
  HDC v18; // rsi
  int v19; // ebx
  __int64 v20; // rdx
  __int64 v21; // rax
  int v22; // ecx
  HWND v23; // rcx
  int DesiredExpandedHeight; // ebx
  unsigned int DpiForWindow; // eax
  unsigned int v26; // edx
  __int64 v27; // r8
  LONG WindowLongW; // eax
  __int64 v29; // rax
  int v30; // ebx
  CProgressBand *v31; // rax
  unsigned int v32; // edx
  unsigned int v33; // eax
  CProgressBand *v34; // rcx
  unsigned int v35; // eax
  HWND v36; // r12
  HWND v37; // rax
  unsigned int v38; // eax
  unsigned int v39; // r8d
  unsigned int v40; // r13d
  unsigned int v41; // eax
  unsigned int v42; // eax
  unsigned int v43; // eax
  const WCHAR *v44; // rbx
  HWND v45; // rax
  HWND v46; // rax
  int v47; // eax
  bool v48; // zf
  WPARAM v49; // rbx
  HWND v50; // rax
  CSH *v52; // rcx
  unsigned int v53; // eax
  __int64 v54; // rdx
  HWND v55; // rdx
  HDC v56; // rcx
  LONG_PTR v57; // r8
  HWND v58; // rsi
  HWND Focus; // rbx
  HWND v60; // rcx
  HWND v61; // rax
  int v62; // eax
  int v63; // esi
  int v64; // edx
  WPARAM v65; // rbx
  HWND v66; // rax
  HWND v67; // rcx
  int v68; // eax
  CSH *v69; // rcx
  char v70; // si
  unsigned int v71; // eax
  int v72; // eax
  int v73; // r8d
  __int64 v74; // rcx
  HWND v75; // rcx
  int v76; // edx
  HWND v77; // rdi
  unsigned int v78; // eax
  unsigned int v79; // eax
  CBrandingBar *v80; // rcx
  int NewPalette; // eax
  CBrandingBar *v82; // rcx
  unsigned int v83; // edx
  unsigned int v84; // edx
  __int64 v85; // rax
  int v86; // ebx
  CProgressBand *v87; // rcx
  HINSTANCE *v88; // r12
  CProgressBand *v89; // rcx
  CProgressBand *v90; // rax
  unsigned int v91; // edx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  CProgressBand *v93; // rcx
  unsigned int v94; // eax
  struct _IMAGELIST *v95; // rcx
  struct _IMAGELIST *ImageList32BitColors; // rax
  int v97; // ecx
  LPARAM v98; // r9
  int v99; // ebx
  int SystemMetricsForDpi; // eax
  int v101; // eax
  CProgressBand *v102; // rcx
  __int64 v103; // rcx
  int v104; // ecx
  __int64 v105; // rax
  HWND DlgItem; // rax
  HWND v107; // rcx
  const unsigned __int16 *v108; // [rsp+28h] [rbp-D8h]
  unsigned int v109; // [rsp+30h] [rbp-D0h]
  int v110; // [rsp+34h] [rbp-CCh]
  struct tagRECT v111; // [rsp+38h] [rbp-C8h] BYREF
  struct tagRECT Rect; // [rsp+48h] [rbp-B8h] BYREF
  struct tagPAINTSTRUCT Paint; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v114[296]; // [rsp+B0h] [rbp-50h] BYREF

  v5 = a4;
  *(_QWORD *)&Rect.left = a4;
  v7 = 0;
  *(_QWORD *)&v111.left = 0;
  CTextScalingHelper::OnWndProc((DWORD_PTR)this + 648, a2, a3, a4, lParam);
  CVScrollHelper::OnWndProc((CMainDlg *)((char *)this + 696), a2, a3, v5, lParam);
  if ( a3 > 0x111 )
  {
    if ( a3 > 0x420 )
    {
      if ( a3 != 1057 )
      {
        switch ( a3 )
        {
          case 0x423u:
            DlgItem = GetDlgItem(a2, 5012);
            SetWindowTextW(DlgItem, (LPCWSTR)(*((_QWORD *)this + 10) + 108LL));
            if ( *((_DWORD *)this + 24) )
            {
              v107 = (HWND)*((_QWORD *)this + 47);
              if ( v107 )
                SendMessageW(v107, 0x423u, 0, 0);
            }
            SendDlgItemMessageW(a2, 1, 0xF4u, 1u, 1);
            return *(_QWORD *)&v111.left;
          case 0x427u:
            if ( *((_DWORD *)this + 24) )
              CMainDlg::FinishToggleExpandedState(this);
            *((_DWORD *)this + 25) = 0;
            return v7;
          case 0x8102u:
            CMainDlg::SetConnectionState(this, 0);
            v103 = *((_QWORD *)this + 10);
            if ( *(_DWORD *)(v103 + 31236) )
            {
              CContainerWnd::FinishDisconnect(*((CContainerWnd **)this + 11), 0);
            }
            else
            {
              v104 = *(_DWORD *)(v103 + 29616);
              Paint.hdc = (HDC)&CDisconnectedDlg::`vftable';
              *(_QWORD *)&Paint.fErase = *((_QWORD *)this + 11);
              v105 = *((_QWORD *)this + 4);
              *(_DWORD *)&Paint.rgbReserved[4] = v104;
              *(_QWORD *)&Paint.rcPaint.top = v105;
              *(_QWORD *)&Paint.rcPaint.bottom = a2;
              *(_QWORD *)&Paint.fIncUpdate = a2;
              *(_DWORD *)&Paint.rgbReserved[8] = v5;
              *(_DWORD *)&Paint.rgbReserved[12] = lParam;
              CDisconnectedDlg::DoModal((CDisconnectedDlg *)&Paint);
            }
            return v7;
        }
        return CDlgBase::DialogBoxProc(this, a2, a3, v5, lParam);
      }
    }
    else if ( a3 != 1056 )
    {
      if ( a3 == 274 )
      {
        if ( (_WORD)v5 == 109 )
        {
          CAboutDlg::CAboutDlg(
            (CAboutDlg *)v114,
            a2,
            *((HINSTANCE *)this + 4),
            *(_DWORD *)(*((_QWORD *)this + 9) + 1612LL),
            (const unsigned __int16 *)(*((_QWORD *)this + 9) + 1616LL));
          CDlgBase::DoModal((CDlgBase *)v114);
          *(_QWORD *)v114 = &CAboutDlg::`vftable';
          CDlgBase::~CDlgBase((CDlgBase *)v114);
        }
        return v7;
      }
      if ( a3 == 275 )
      {
        v102 = (CProgressBand *)*((_QWORD *)this + 74);
        if ( v102 )
          CProgressBand::OnTimer(v102, v5);
        return v7;
      }
      if ( a3 != 736 )
      {
        if ( a3 == 783 )
        {
          v82 = (CBrandingBar *)*((_QWORD *)this + 75);
          if ( !v82 )
            return v7;
          NewPalette = CBrandingBar::OnQueryNewPalette(v82);
          goto LABEL_187;
        }
        if ( a3 == 785 )
        {
          v80 = (CBrandingBar *)*((_QWORD *)this + 75);
          if ( !v80 )
            return v7;
          NewPalette = CBrandingBar::OnPaletteChanged(v80, v5);
LABEL_187:
          *(_QWORD *)&v111.left = NewPalette;
          InvalidateRect(a2, 0, 1);
          UpdateWindow(a2);
          return *(_QWORD *)&v111.left;
        }
        return CDlgBase::DialogBoxProc(this, a2, a3, v5, lParam);
      }
      if ( !*((_DWORD *)this + 16) )
        return v7;
      *((_DWORD *)this + 17) = Win32DpiApi::GetDpiForWindow(*((Win32DpiApi **)this + 7), a2);
      CMainDlg::LoadAssetDetails(this);
      CDlgBase::SetDialogAppIcon(this, v83);
      CMainDlg::DestroyBrandingBar(this);
      CMainDlg::CreateBrandingBar(this, a2);
      v85 = *((_QWORD *)this + 75);
      if ( v85 )
      {
        v86 = *(_DWORD *)(v85 + 36);
        v7 = *(_QWORD *)(v85 + 24);
      }
      else
      {
        v86 = 0;
      }
      v87 = (CProgressBand *)*((_QWORD *)this + 74);
      if ( v87 )
      {
        CProgressBand::`scalar deleting destructor'(v87, v84);
        *((_QWORD *)this + 74) = 0;
      }
      v88 = (HINSTANCE *)((char *)this + 32);
      v89 = (CProgressBand *)operator new(0x50u);
      if ( v89 )
      {
        v90 = CProgressBand::CProgressBand(v89, a2, *v88, v86, *((_DWORD *)this + 161), (HPALETTE)v7);
        *((_QWORD *)this + 74) = v90;
        if ( v90 )
        {
          if ( !*(_DWORD *)v90 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                24,
                WPP_ff2496e086463c752882f855d2d17187_Traceguids,
                CurrentThreadActivityIdPrefix);
            }
            v93 = (CProgressBand *)*((_QWORD *)this + 74);
            if ( v93 )
              CProgressBand::`scalar deleting destructor'(v93, v91);
            *((_QWORD *)this + 74) = 0;
          }
LABEL_209:
          v95 = (struct _IMAGELIST *)*((_QWORD *)this + 78);
          if ( v95 )
          {
            ImageList_Destroy(v95);
            *((_QWORD *)this + 78) = 0;
          }
          ImageList32BitColors = LoadImageList32BitColors(
                                   *v88,
                                   (const unsigned __int16 *)*((unsigned __int16 *)this + 320),
                                   *((_DWORD *)this + 158));
          v97 = *((unsigned __int16 *)this + 318) << 16;
          *((_QWORD *)this + 78) = ImageList32BitColors;
          SendMessageW(*((HWND *)this + 77), 0x420u, 0, *((unsigned __int16 *)this + 316) | v97);
          v98 = *((_QWORD *)this + 78);
          if ( v98 )
          {
            SendMessageW(*((HWND *)this + 77), 0x430u, 0, v98);
            SendMessageW(*((HWND *)this + 77), 0x436u, 0, *((_QWORD *)this + 78));
          }
          CMainDlg::PositionExpandoButton(this, 0);
          CMainDlg::SetExpandoButtonBitmap(this);
          if ( *((_QWORD *)this + 47) )
          {
            v99 = *((_DWORD *)this + 166);
            SystemMetricsForDpi = Win32DpiApi::GetSystemMetricsForDpi(
                                    *((Win32DpiApi **)this + 7),
                                    11,
                                    *((_DWORD *)this + 17));
            v101 = MulDiv(SystemMetricsForDpi, v99, 100);
            SendMessageW(*((HWND *)this + 47), 0x429u, v101, 0);
          }
          CMainDlg::Recalc(this);
          return *(_QWORD *)&v111.left;
        }
      }
      else
      {
        *((_QWORD *)this + 74) = 0;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v94 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_ff2496e086463c752882f855d2d17187_Traceguids, v94);
      }
      goto LABEL_209;
    }
    if ( *((_DWORD *)this + 130) )
      CMainDlg::OnEndConnection(this, a3 == 1056);
    return v7;
  }
  if ( a3 == 273 )
  {
    switch ( (unsigned __int16)v5 )
    {
      case 1u:
        if ( !*((_DWORD *)this + 24) )
          goto LABEL_154;
        v67 = (HWND)*((_QWORD *)this + 47);
        if ( v67 )
          SendMessageW(v67, 0x41Eu, 0, 0);
        if ( !*((_DWORD *)this + 24) )
LABEL_154:
          CMainDlg::DlgToSettings(this);
        v68 = StringCchCopyW(v114, 0x100u, (const unsigned __int16 *)(*((_QWORD *)this + 10) + 108LL));
        v70 = v68;
        if ( v68 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v71 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            (unsigned int)WPP_ff2496e086463c752882f855d2d17187_Traceguids,
            v71,
            (__int64)"StringCchCopy failed!",
            v70);
        }
        CSH::SH_CanonicalizeServerName(v69, v114);
        v72 = CRdpConnectionString::ValidateServerPart(v114);
        v74 = *((_QWORD *)this + 10);
        if ( v72 )
        {
          CRdpConnectionString::SetFullConnectionString((CRdpConnectionString *)(v74 + 108), v114);
          CMainDlg::OnStartConnection(this);
          if ( !(unsigned int)CContainerWnd::StartConnection(*((CContainerWnd **)this + 11)) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v79 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ff2496e086463c752882f855d2d17187_Traceguids, v79);
            }
            CMainDlg::OnEndConnection(this, 0);
          }
        }
        else
        {
          CSharedSH::SH_DisplayMsgBox(a2, 0x4CBu, v73, *(_DWORD *)(v74 + 6260));
          if ( *((_DWORD *)this + 24) )
          {
            v75 = (HWND)*((_QWORD *)this + 47);
            v76 = 13050;
          }
          else
          {
            v76 = 5012;
            v75 = a2;
          }
          v77 = GetDlgItem(v75, v76);
          if ( v77 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              v78 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_ff2496e086463c752882f855d2d17187_Traceguids, v78);
            }
            SetFocus(v77);
          }
        }
        return *(_QWORD *)&v111.left;
      case 2u:
        CMainDlg::DlgToSettings(this);
        EndDialog(a2, 2);
        PostMessageW(*(HWND *)(*((_QWORD *)this + 11) + 8LL), 0x10u, 0, 0);
        return v7;
      case 0xBC7u:
      case 0xBC8u:
        if ( !*((_DWORD *)this + 24) || *((_DWORD *)this + 130) )
          return v7;
        v61 = GetDlgItem(*((HWND *)this + 1), 5015);
        v62 = SendMessageW(v61, 0x130Bu, 0, 0);
        v63 = 1;
        if ( (_WORD)v5 != 3015 )
          v63 = -1;
        v64 = v62 + v63;
        if ( v62 + v63 < 5 )
        {
          if ( v64 < 0 )
            v64 = 4;
        }
        else
        {
          v64 = 0;
        }
        v65 = v64;
        v66 = GetDlgItem(*((HWND *)this + 1), 5015);
        SendMessageW(v66, 0x130Cu, v65, 0);
        CMainDlg::OnTabSelChange(this);
        return *(_QWORD *)&v111.left;
      case 0x1394u:
        if ( WORD1(v5) == 5 )
          CMainDlg::UpdateCredPaneWithServerName(this);
        return v7;
    }
    if ( (unsigned __int16)v5 != 5013 )
    {
      if ( (unsigned __int16)v5 == 5014 || (unsigned __int16)v5 == 5018 )
      {
        CMainDlg::ToggleExpandedState(this, 0);
      }
      else
      {
        v60 = (HWND)*((_QWORD *)this + 47);
        if ( v60 )
          SendMessageW(v60, 0x111u, v5, lParam);
      }
      return v7;
    }
    v52 = (CSH *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v53 = RdpWppGetCurrentThreadActivityIdPrefix();
      v54 = 19;
      goto LABEL_99;
    }
LABEL_100:
    if ( !*((_DWORD *)this + 130) )
    {
      v55 = *(HWND *)(*((_QWORD *)this + 11) + 8LL);
      if ( v55 )
        CSH::SH_DisplayClientHelp(v52, v55, L"mshelp://windows/?id=f55326fa-e629-423b-abba-b30f76cc61e6", v10, 0, v108);
    }
    return *(_QWORD *)&v111.left;
  }
  if ( a3 > 0x46 )
  {
    if ( a3 == 78 )
    {
      if ( lParam )
      {
        if ( *(_DWORD *)(lParam + 16) == -713 )
        {
          if ( *((_QWORD *)this + 77) )
            LODWORD(v7) = *(_DWORD *)(lParam + 28) == 5018;
          *((_DWORD *)this + 91) = v7;
          return *(_QWORD *)&v111.left;
        }
        if ( *(_DWORD *)(lParam + 16) == -551 )
        {
          v58 = GetDlgItem(a2, 5015);
          Focus = GetFocus();
          CMainDlg::OnTabSelChange(this);
          if ( Focus == v58 )
            SetFocus(v58);
          SendMessageW(*((HWND *)this + 47), 0x127u, 0x10002u, 0);
          return *(_QWORD *)&v111.left;
        }
        if ( *(_DWORD *)(lParam + 16) == -12 && *(_QWORD *)(lParam + 8) == 5017 )
        {
          if ( *(_DWORD *)(lParam + 24) == 1 )
          {
            v57 = 32;
          }
          else
          {
            if ( *(_DWORD *)(lParam + 24) != 65537 )
            {
              if ( *(_DWORD *)(lParam + 24) == 65538
                && *((_DWORD *)this + 91)
                && !(unsigned int)CDlgBase::IsUIHighContrast((CDlgBase *)(unsigned int)(*(_DWORD *)(lParam + 24) - 65537)) )
              {
                v56 = *(HDC *)(lParam + 32);
                v7 = 1;
                Rect.bottom = *(_DWORD *)(lParam + 52) - 1;
                Rect.top = *(_DWORD *)(lParam + 44) + 1;
                Rect.left = *(_DWORD *)(lParam + 40) + 1;
                Rect.right = *(_DWORD *)(lParam + 48) - 1;
                DrawFocusRect(v56, &Rect);
              }
              return v7;
            }
            v57 = 16;
          }
          SetWindowLongPtrW(a2, 0, v57);
          return 1;
        }
      }
      return v7;
    }
    if ( a3 != 83 )
    {
      if ( a3 == 126 )
      {
LABEL_10:
        ScreenBpp = CSH::SH_GetScreenBpp();
        v12 = (CBrandingBar *)*((unsigned int *)this + 92);
        v109 = ScreenBpp;
        v110 = (int)v12;
        if ( (_DWORD)v12 != ScreenBpp )
        {
          v13 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              v14 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DLD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                20,
                WPP_ff2496e086463c752882f855d2d17187_Traceguids,
                v14,
                v110,
                v109);
              v13 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 4u )
            {
              v15 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_ff2496e086463c752882f855d2d17187_Traceguids, v15);
            }
          }
          v16 = (CProgressBand *)*((_QWORD *)this + 74);
          if ( v16
            && !(unsigned int)CProgressBand::ReLoadBmps(v16)
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v17 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_ff2496e086463c752882f855d2d17187_Traceguids, v17);
          }
          v12 = (CBrandingBar *)*((_QWORD *)this + 75);
          if ( v12 )
          {
            CBrandingBar::Initialize(v12, *((struct tagBRANDING_BAR_TEXT **)this + 76), 0);
            InvalidateRect(*((HWND *)this + 1), 0, 1);
          }
          v5 = *(_QWORD *)&Rect.left;
        }
        CMainDlg::PropagateMsgToChildren(v12, a2, a3, v5, lParam);
        return *(_QWORD *)&v111.left;
      }
      if ( a3 == 272 )
      {
        *((_QWORD *)this + 1) = a2;
        if ( *((_DWORD *)this + 16) )
          DpiForWindow = Win32DpiApi::GetDpiForWindow(*((Win32DpiApi **)this + 7), a2);
        else
          DpiForWindow = CSH::SH_GetDPI();
        *((_DWORD *)this + 17) = DpiForWindow;
        CDlgBase::SetDialogAppIcon(this, v26);
        if ( !*((_QWORD *)this + 9) || !*((_QWORD *)this + 11) )
          return 0;
        CDlgBase::CenterWindow(this, 0, v27, 4);
        SetForegroundWindow(a2);
        WindowLongW = GetWindowLongW(a2, -16);
        SetWindowLongW(a2, -16, WindowLongW & 0xFFFEFFFF);
        *(_QWORD *)(*((_QWORD *)this + 11) + 160LL) = a2;
        *((_DWORD *)this + 92) = CSH::SH_GetScreenBpp();
        CMainDlg::LoadAssetDetails(this);
        CMainDlg::CreateBrandingBar(this, a2);
        v29 = *((_QWORD *)this + 75);
        if ( v29 )
        {
          v30 = *(_DWORD *)(v29 + 36);
          v7 = *(_QWORD *)(v29 + 24);
        }
        else
        {
          v30 = 0;
        }
        v31 = (CProgressBand *)operator new(0x50u);
        if ( v31 )
          v31 = CProgressBand::CProgressBand(
                  v31,
                  a2,
                  *((HINSTANCE *)this + 4),
                  v30,
                  *((_DWORD *)this + 161),
                  (HPALETTE)v7);
        *((_QWORD *)this + 74) = v31;
        v7 = 1;
        if ( v31 )
        {
          if ( !*(_DWORD *)v31 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v33 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ff2496e086463c752882f855d2d17187_Traceguids, v33);
            }
            v34 = (CProgressBand *)*((_QWORD *)this + 74);
            if ( v34 )
              CProgressBand::`scalar deleting destructor'(v34, v32);
            *((_QWORD *)this + 74) = 0;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v35 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ff2496e086463c752882f855d2d17187_Traceguids, v35);
        }
        CMainDlg::SetupDialogSysMenu(this);
        v36 = GetDlgItem(a2, 5012);
        CSH::InitServerAutoCmplCombo(*((struct CTscSettings **)this + 10), v36);
        v37 = (HWND)SendMessageW(v36, 0x407u, 0, 0);
        if ( !SetWindowSubclass(v37, GeneralEditSubclassProc, 0, 0)
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v38 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ff2496e086463c752882f855d2d17187_Traceguids, v38);
        }
        SetWindowTextW(v36, (LPCWSTR)(*((_QWORD *)this + 10) + 108LL));
        v40 = TSComboBoxEx32SetCueBannerText(*((HINSTANCE *)this + 4), v36, v39);
        if ( v40
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v41 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ff2496e086463c752882f855d2d17187_Traceguids, v41, v40);
        }
        SetFocus(v36);
        SetForegroundWindow(a2);
        if ( !TSLoadString(*((HINSTANCE *)this + 4), 0x42Eu, (unsigned __int16 *)this + 54, 64) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v42 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              14,
              WPP_ff2496e086463c752882f855d2d17187_Traceguids,
              v42,
              1070);
          }
          *((_WORD *)this + 54) = 0;
        }
        if ( !TSLoadString(*((HINSTANCE *)this + 4), 0x42Fu, (unsigned __int16 *)this + 118, 64) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v43 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              15,
              WPP_ff2496e086463c752882f855d2d17187_Traceguids,
              v43,
              1071);
          }
          *((_WORD *)this + 118) = 0;
        }
        v44 = (const WCHAR *)((char *)this + (*((_DWORD *)this + 24) != 0 ? 0x80 : 0) + 108);
        v45 = GetDlgItem(*((HWND *)this + 1), 5014);
        SetWindowTextW(v45, v44);
        CDlgBase::EnableControls(this, &moreUI, 1, 0);
        CDlgBase::ShowControls(this, &moreUI, 1, 0);
        CMainDlg::InitTabs(this);
        CMainDlg::DisplayComponents(this);
        CMainDlg::CreateExpandoButton(this);
        Rect = 0;
        GetWindowRect(a2, &Rect);
        v46 = GetDlgItem(a2, 5014);
        v111 = 0;
        GetWindowRect(v46, &v111);
        v47 = MulDiv(Rect.bottom - v111.bottom, 9600, *((_DWORD *)this + 17) * *((_DWORD *)this + 166));
        v48 = *((_DWORD *)this + 126) == 0;
        *((_DWORD *)this + 128) = v47;
        if ( !v48 )
        {
          CMainDlg::ToggleExpandedState(this, 1);
          v49 = *((int *)this + 129);
          v50 = GetDlgItem(a2, 5015);
          SendMessageW(v50, 0x130Cu, v49, 0);
          CMainDlg::OnTabSelChange(this);
        }
        CMainDlg::Recalc(this);
        return v7;
      }
      return CDlgBase::DialogBoxProc(this, a2, a3, v5, lParam);
    }
    v52 = (CSH *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v53 = RdpWppGetCurrentThreadActivityIdPrefix();
      v54 = 23;
LABEL_99:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v54, WPP_ff2496e086463c752882f855d2d17187_Traceguids, v53);
      goto LABEL_100;
    }
    goto LABEL_100;
  }
  switch ( a3 )
  {
    case 0x46u:
      if ( (*(_BYTE *)(lParam + 32) & 1) == 0 )
      {
        if ( *((_DWORD *)this + 24) )
        {
          v23 = (HWND)*((_QWORD *)this + 1);
          Rect = 0;
          if ( CClientUtilsWin32::WorkRectFromHwnd(v23, &Rect) )
          {
            DesiredExpandedHeight = Rect.bottom - Rect.top;
            if ( DesiredExpandedHeight >= (int)CMainDlg::GetDesiredExpandedHeight(this) )
              DesiredExpandedHeight = CMainDlg::GetDesiredExpandedHeight(this);
            *(_DWORD *)(lParam + 28) = DesiredExpandedHeight;
            *((_DWORD *)this + 26) = 1;
          }
        }
      }
      return *(_QWORD *)&v111.left;
    case 5u:
      CMainDlg::Recalc(this);
      break;
    case 0xFu:
      memset_0(&Paint, 0, sizeof(Paint));
      v18 = BeginPaint(a2, &Paint);
      v19 = -(int)CVScrollHelper::GetPosition((CMainDlg *)((char *)this + 696));
      CMainDlg::PaintBrandImage(this, v18, v19);
      v20 = *((_QWORD *)this + 74);
      if ( v20 )
      {
        v21 = *((_QWORD *)this + 75);
        if ( v21 )
          v22 = *(_DWORD *)(v21 + 36);
        else
          v22 = 0;
        *(_DWORD *)(v20 + 24) = v22 + v19;
        CProgressBand::OnEraseParentBackground(*((CProgressBand **)this + 74), v18);
      }
      EndPaint(a2, &Paint);
      return *(_QWORD *)&v111.left;
    case 0x10u:
      break;
    case 0x15u:
    case 0x1Au:
      goto LABEL_10;
    default:
      return CDlgBase::DialogBoxProc(this, a2, a3, v5, lParam);
  }
  return v7;
}

```

## disassembly

```asm
0x140049fa0  push    rbp
0x140049fa2  push    rbx
0x140049fa3  push    rsi
0x140049fa4  push    rdi
0x140049fa5  push    r12
0x140049fa7  push    r13
0x140049fa9  push    r14
0x140049fab  push    r15
0x140049fad  lea     rbp, [rsp-218h]
0x140049fb5  sub     rsp, 318h
0x140049fbc  mov     rax, cs:__security_cookie
0x140049fc3  xor     rax, rsp
0x140049fc6  mov     [rbp+250h+var_50], rax
0x140049fcd  mov     r13, [rbp+250h+lParam]
0x140049fd4  mov     rbx, r9
0x140049fd7  mov     rdi, rcx
0x140049fda  mov     qword ptr [rsp+350h+Rect.left], rbx
0x140049fdf  xor     esi, esi
0x140049fe1  mov     [rsp+350h+var_330], r13; __int64
0x140049fe6  add     rcx, 288h; dwRefData
0x140049fed  mov     qword ptr [rsp+350h+var_318.left], rsi
0x140049ff2  mov     r12d, r8d
0x140049ff5  mov     r14, rdx
0x140049ff8  call    ?OnWndProc@CTextScalingHelper@@QEAAXPEAUHWND__@@I_K_J@Z; CTextScalingHelper::OnWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x140049ffd  lea     r15, [rdi+2B8h]
0x14004a004  mov     [rsp+350h+var_330], r13; __int64
0x14004a009  mov     rcx, r15; this
0x14004a00c  mov     r9, rbx; unsigned __int64
0x14004a00f  mov     r8d, r12d; unsigned int
0x14004a012  mov     rdx, r14; HWND
0x14004a015  call    ?OnWndProc@CVScrollHelper@@QEAAXPEAUHWND__@@I_K_J@Z; CVScrollHelper::OnWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x14004a01a  mov     edx, 111h; Msg
0x14004a01f  cmp     r12d, edx
0x14004a022  ja      loc_14004AC7D
0x14004a028  jz      loc_14004A91A
0x14004a02e  cmp     r12d, 46h ; 'F'
0x14004a032  ja      loc_14004A29E
0x14004a038  jz      loc_14004A23D
0x14004a03e  mov     eax, r12d
0x14004a041  lea     ecx, [rsi+5]
0x14004a044  sub     eax, ecx
0x14004a046  jz      loc_14004A230
0x14004a04c  sub     eax, 0Ah
0x14004a04f  jz      loc_14004A1AE
0x14004a055  sub     eax, 1
0x14004a058  jz      loc_14004B135
0x14004a05e  sub     eax, ecx
0x14004a060  jz      short loc_14004A06A
0x14004a062  cmp     eax, ecx
0x14004a064  jnz     loc_14004B01B
0x14004a06a  call    ?SH_GetScreenBpp@CSH@@SAIXZ; CSH::SH_GetScreenBpp(void)
0x14004a06f  mov     ecx, [rdi+170h]
0x14004a075  mov     [rsp+350h+var_320], eax
0x14004a079  mov     [rsp+350h+var_31C], ecx
0x14004a07d  cmp     ecx, eax
0x14004a07f  jz      loc_14004A196
0x14004a085  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a08c  lea     rbx, WPP_GLOBAL_Control
0x14004a093  lea     r15, WPP_ff2496e086463c752882f855d2d17187_Traceguids
0x14004a09a  mov     esi, 1
0x14004a09f  cmp     rcx, rbx
0x14004a0a2  jz      short loc_14004A11A
0x14004a0a4  lea     eax, [rsi+3]
0x14004a0a7  test    [rcx+1Ch], sil
0x14004a0ab  jz      short loc_14004A0EA
0x14004a0ad  cmp     [rcx+19h], al
0x14004a0b0  jb      short loc_14004A0EA
0x14004a0b2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004a0b7  mov     ecx, [rsp+350h+var_320]
0x14004a0bb  lea     edx, [rsi+13h]
0x14004a0be  mov     dword ptr [rsp+350h+var_328], ecx
0x14004a0c2  mov     r9d, eax
0x14004a0c5  mov     ecx, [rsp+350h+var_31C]
0x14004a0c9  mov     r8, r15
0x14004a0cc  mov     dword ptr [rsp+350h+var_330], ecx
0x14004a0d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a0d7  mov     rcx, [rcx+10h]
0x14004a0db  call    WPP_SF_DLD
0x14004a0e0  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a0e7  lea     eax, [rsi+3]
0x14004a0ea  cmp     rcx, rbx
0x14004a0ed  jz      short loc_14004A11A
0x14004a0ef  test    [rcx+1Ch], sil
0x14004a0f3  jz      short loc_14004A11A
0x14004a0f5  cmp     [rcx+19h], al
0x14004a0f8  jb      short loc_14004A11A
0x14004a0fa  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004a0ff  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a106  mov     edx, 15h
0x14004a10b  mov     r9d, eax
0x14004a10e  mov     r8, r15
0x14004a111  mov     rcx, [rcx+10h]
0x14004a115  call    WPP_SF_d
0x14004a11a  mov     rcx, [rdi+250h]; this
0x14004a121  test    rcx, rcx
0x14004a124  jz      short loc_14004A167
0x14004a126  call    ?ReLoadBmps@CProgressBand@@QEAAHXZ; CProgressBand::ReLoadBmps(void)
0x14004a12b  test    eax, eax
0x14004a12d  jnz     short loc_14004A167
0x14004a12f  mov     rax, cs:WPP_GLOBAL_Control
0x14004a136  cmp     rax, rbx
0x14004a139  jz      short loc_14004A167
0x14004a13b  test    [rax+1Ch], sil
0x14004a13f  jz      short loc_14004A167
0x14004a141  cmp     byte ptr [rax+19h], 2
0x14004a145  jb      short loc_14004A167
0x14004a147  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004a14c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a153  mov     edx, 16h
0x14004a158  mov     r9d, eax
0x14004a15b  mov     r8, r15
0x14004a15e  mov     rcx, [rcx+10h]
0x14004a162  call    WPP_SF_d
0x14004a167  mov     rcx, [rdi+258h]; this
0x14004a16e  test    rcx, rcx
0x14004a171  jz      short loc_14004A191
0x14004a173  mov     rdx, [rdi+260h]; struct tagBRANDING_BAR_TEXT *
0x14004a17a  xor     r8d, r8d; int
0x14004a17d  call    ?Initialize@CBrandingBar@@QEAAHPEAUtagBRANDING_BAR_TEXT@@H@Z; CBrandingBar::Initialize(tagBRANDING_BAR_TEXT *,int)
0x14004a182  mov     rcx, [rdi+8]; hWnd
0x14004a186  mov     r8d, esi; bErase
0x14004a189  xor     edx, edx; lpRect
0x14004a18b  call    cs:__imp_InvalidateRect
0x14004a191  mov     rbx, qword ptr [rsp+350h+Rect.left]
0x14004a196  mov     r9, rbx; unsigned __int64
0x14004a199  mov     [rsp+350h+var_330], r13; __int64
0x14004a19e  mov     r8d, r12d; unsigned int
0x14004a1a1  mov     rdx, r14; HWND
0x14004a1a4  call    ?PropagateMsgToChildren@CMainDlg@@AEAAXPEAUHWND__@@I_K_J@Z; CMainDlg::PropagateMsgToChildren(HWND__ *,uint,unsigned __int64,__int64)
0x14004a1a9  jmp     loc_14004B116
0x14004a1ae  xor     edx, edx; Val
0x14004a1b0  lea     rcx, [rsp+350h+Paint]; void *
0x14004a1b5  lea     r8d, [rdx+48h]; Size
0x14004a1b9  call    memset_0
0x14004a1be  lea     rdx, [rsp+350h+Paint]; lpPaint
0x14004a1c3  mov     rcx, r14; hWnd
0x14004a1c6  call    cs:__imp_BeginPaint
0x14004a1cc  mov     rcx, r15; this
0x14004a1cf  mov     rsi, rax
0x14004a1d2  call    ?GetPosition@CVScrollHelper@@QEAAHXZ; CVScrollHelper::GetPosition(void)
0x14004a1d7  mov     ebx, eax
0x14004a1d9  mov     rdx, rsi; HDC
0x14004a1dc  neg     ebx
0x14004a1de  mov     rcx, rdi; this
0x14004a1e1  mov     r8d, ebx; int
0x14004a1e4  call    ?PaintBrandImage@CMainDlg@@AEAAXPEAUHDC__@@H@Z; CMainDlg::PaintBrandImage(HDC__ *,int)
0x14004a1e9  mov     rdx, [rdi+250h]
0x14004a1f0  test    rdx, rdx
0x14004a1f3  jz      short loc_14004A21D
0x14004a1f5  mov     rax, [rdi+258h]
0x14004a1fc  test    rax, rax
0x14004a1ff  jz      short loc_14004A206
0x14004a201  mov     ecx, [rax+24h]
0x14004a204  jmp     short loc_14004A208
0x14004a206  xor     ecx, ecx
0x14004a208  lea     eax, [rcx+rbx]
0x14004a20b  mov     [rdx+18h], eax
0x14004a20e  mov     rdx, rsi; HDC
0x14004a211  mov     rcx, [rdi+250h]; this
0x14004a218  call    ?OnEraseParentBackground@CProgressBand@@QEAAHPEAUHDC__@@@Z; CProgressBand::OnEraseParentBackground(HDC__ *)
0x14004a21d  lea     rdx, [rsp+350h+Paint]; lpPaint
0x14004a222  mov     rcx, r14; hWnd
0x14004a225  call    cs:__imp_EndPaint
0x14004a22b  jmp     loc_14004B116
0x14004a230  mov     rcx, rdi; this
0x14004a233  call    ?Recalc@CMainDlg@@AEAAXXZ; CMainDlg::Recalc(void)
0x14004a238  jmp     loc_14004B135
0x14004a23d  mov     esi, 1
0x14004a242  test    [r13+20h], sil
0x14004a246  jnz     loc_14004B116
0x14004a24c  cmp     dword ptr [rdi+60h], 0
0x14004a250  jz      loc_14004B116
0x14004a256  mov     rcx, [rdi+8]; HWND
0x14004a25a  lea     rdx, [rsp+350h+Rect]; struct tagRECT *
0x14004a25f  xorps   xmm0, xmm0
0x14004a262  movups  xmmword ptr [rsp+350h+Rect.left], xmm0
0x14004a267  call    ?WorkRectFromHwnd@CClientUtilsWin32@@SAHPEAUHWND__@@PEAUtagRECT@@@Z; CClientUtilsWin32::WorkRectFromHwnd(HWND__ *,tagRECT *)
0x14004a26c  test    eax, eax
0x14004a26e  jz      loc_14004B116
0x14004a274  mov     ebx, [rsp+350h+Rect.bottom]
0x14004a278  mov     rcx, rdi; this
0x14004a27b  sub     ebx, [rsp+350h+Rect.top]
0x14004a27f  call    ?GetDesiredExpandedHeight@CMainDlg@@AEAAHXZ; CMainDlg::GetDesiredExpandedHeight(void)
0x14004a284  cmp     ebx, eax
0x14004a286  jl      short loc_14004A292
0x14004a288  mov     rcx, rdi; this
0x14004a28b  call    ?GetDesiredExpandedHeight@CMainDlg@@AEAAHXZ; CMainDlg::GetDesiredExpandedHeight(void)
0x14004a290  mov     ebx, eax
0x14004a292  mov     [r13+1Ch], ebx
0x14004a296  mov     [rdi+68h], esi
0x14004a299  jmp     loc_14004B116
0x14004a29e  cmp     r12d, 4Eh ; 'N'
0x14004a2a2  jz      loc_14004A7D2
0x14004a2a8  cmp     r12d, 53h ; 'S'
0x14004a2ac  jz      loc_14004A756
0x14004a2b2  cmp     r12d, 7Eh ; '~'
0x14004a2b6  jz      loc_14004A06A
0x14004a2bc  cmp     r12d, 110h
0x14004a2c3  jnz     loc_14004B01B
0x14004a2c9  mov     [rdi+8], r14
0x14004a2cd  cmp     [rdi+40h], esi
0x14004a2d0  jz      short loc_14004A2E0
0x14004a2d2  mov     rcx, [rdi+38h]; this
0x14004a2d6  mov     rdx, r14; HWND
0x14004a2d9  call    ?GetDpiForWindow@Win32DpiApi@@QEAAIPEAUHWND__@@@Z; Win32DpiApi::GetDpiForWindow(HWND__ *)
0x14004a2de  jmp     short loc_14004A2E5
0x14004a2e0  call    ?SH_GetDPI@CSH@@SAIXZ; CSH::SH_GetDPI(void)
0x14004a2e5  mov     rcx, rdi; this
0x14004a2e8  mov     [rdi+44h], eax
0x14004a2eb  call    ?SetDialogAppIcon@CDlgBase@@IEAAXI@Z; CDlgBase::SetDialogAppIcon(uint)
0x14004a2f0  cmp     [rdi+48h], rsi
0x14004a2f4  jz      loc_14004A74F
0x14004a2fa  cmp     [rdi+58h], rsi
0x14004a2fe  jz      loc_14004A74F
0x14004a304  xor     edx, edx; HWND
0x14004a306  mov     rcx, rdi; this
0x14004a309  lea     r9d, [rdx+4]; int
0x14004a30d  call    ?CenterWindow@CDlgBase@@IEAAXPEAUHWND__@@HH@Z; CDlgBase::CenterWindow(HWND__ *,int,int)
0x14004a312  mov     rcx, r14; hWnd
0x14004a315  call    cs:__imp_SetForegroundWindow
0x14004a31b  mov     ebx, 0FFFFFFF0h
0x14004a320  mov     rcx, r14; hWnd
0x14004a323  mov     edx, ebx; nIndex
0x14004a325  call    cs:__imp_GetWindowLongW
0x14004a32b  mov     edx, ebx; nIndex
0x14004a32d  mov     rcx, r14; hWnd
0x14004a330  btr     eax, 10h
0x14004a334  mov     r8d, eax; dwNewLong
0x14004a337  call    cs:__imp_SetWindowLongW
0x14004a33d  mov     rax, [rdi+58h]
0x14004a341  mov     [rax+0A0h], r14
0x14004a348  call    ?SH_GetScreenBpp@CSH@@SAIXZ; CSH::SH_GetScreenBpp(void)
0x14004a34d  mov     rcx, rdi; this
0x14004a350  mov     [rdi+170h], eax
0x14004a356  call    ?LoadAssetDetails@CMainDlg@@AEAAXXZ; CMainDlg::LoadAssetDetails(void)
0x14004a35b  mov     rdx, r14; HWND
0x14004a35e  mov     rcx, rdi; this
0x14004a361  call    ?CreateBrandingBar@CMainDlg@@AEAAHPEAUHWND__@@@Z; CMainDlg::CreateBrandingBar(HWND__ *)
0x14004a366  mov     rax, [rdi+258h]
0x14004a36d  test    rax, rax
0x14004a370  jz      short loc_14004A37B
0x14004a372  mov     ebx, [rax+24h]
0x14004a375  mov     rsi, [rax+18h]
0x14004a379  jmp     short loc_14004A37D
0x14004a37b  xor     ebx, ebx
0x14004a37d  mov     ecx, 50h ; 'P'; Size
0x14004a382  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004a387  mov     rcx, rax; this
0x14004a38a  test    rax, rax
0x14004a38d  jz      short loc_14004A3AD
0x14004a38f  mov     eax, [rdi+284h]
0x14004a395  mov     r9d, ebx; int
0x14004a398  mov     r8, [rdi+20h]; HINSTANCE
0x14004a39c  mov     rdx, r14; HWND
0x14004a39f  mov     [rsp+350h+var_328], rsi; HPALETTE
0x14004a3a4  mov     dword ptr [rsp+350h+var_330], eax; int
0x14004a3a8  call    ??0CProgressBand@@QEAA@PEAUHWND__@@PEAUHINSTANCE__@@HHPEAUHPALETTE__@@@Z; CProgressBand::CProgressBand(HWND__ *,HINSTANCE__ *,int,int,HPALETTE__ *)
0x14004a3ad  mov     [rdi+250h], rax
0x14004a3b4  lea     r15, WPP_ff2496e086463c752882f855d2d17187_Traceguids
0x14004a3bb  lea     rbx, WPP_GLOBAL_Control
0x14004a3c2  mov     esi, 1
0x14004a3c7  test    rax, rax
0x14004a3ca  jz      short loc_14004A429
0x14004a3cc  cmp     dword ptr [rax], 0
0x14004a3cf  jnz     loc_14004A461
0x14004a3d5  mov     rax, cs:WPP_GLOBAL_Control
0x14004a3dc  cmp     rax, rbx
0x14004a3df  jz      short loc_14004A40B
0x14004a3e1  test    [rax+1Ch], sil
0x14004a3e5  jz      short loc_14004A40B
0x14004a3e7  cmp     byte ptr [rax+19h], 2
0x14004a3eb  jb      short loc_14004A40B
0x14004a3ed  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004a3f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a3f9  lea     edx, [rsi+9]
0x14004a3fc  mov     r9d, eax
0x14004a3ff  mov     r8, r15
0x14004a402  mov     rcx, [rcx+10h]
0x14004a406  call    WPP_SF_d
0x14004a40b  mov     rcx, [rdi+250h]; this
0x14004a412  test    rcx, rcx
0x14004a415  jz      short loc_14004A41C
0x14004a417  call    ??_GCProgressBand@@QEAAPEAXI@Z; CProgressBand::`scalar deleting destructor'(uint)
0x14004a41c  mov     qword ptr [rdi+250h], 0
0x14004a427  jmp     short loc_14004A461
0x14004a429  mov     rax, cs:WPP_GLOBAL_Control
0x14004a430  cmp     rax, rbx
0x14004a433  jz      short loc_14004A461
0x14004a435  test    [rax+1Ch], sil
0x14004a439  jz      short loc_14004A461
0x14004a43b  cmp     byte ptr [rax+19h], 2
0x14004a43f  jb      short loc_14004A461
0x14004a441  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004a446  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a44d  mov     edx, 0Bh
0x14004a452  mov     r9d, eax
0x14004a455  mov     r8, r15
0x14004a458  mov     rcx, [rcx+10h]
0x14004a45c  call    WPP_SF_d
0x14004a461  mov     rcx, rdi; this
  ... truncated ...
```
