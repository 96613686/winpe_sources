# CGhostWindow::GhostWndProcWorker(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180006bb8`
- end: `0x18000717d`
- name: `?GhostWndProcWorker@CGhostWindow@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `1477`
- prototype: `LRESULT __fastcall(CGhostWindow *this, HWND hWnd, UINT Msg, WPARAM wParam, struct tagRECT *lParam)`
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update`

## callers

- `0x1800078c0`

## callees

- `0x180001190`
- `0x180001962`
- `0x1800061a4`
- `0x180006538`
- `0x180006bac`
- `0x180006bb8`
- `0x180007338`
- `0x1800073c0`
- `0x180007444`
- `0x1800075e0`
- `0x1800077ac`
- `0x180009094`
- `0x180009190`
- `0x1800092a8`
- `0x180009468`
- `0x18000a524`
- `0x18000c010`

## import_xrefs

- `USER32!BeginPaint` at `0x180006cab`
- `USER32!BeginPaint` at `0x180006cab`
- `USER32!EndPaint` at `0x180006ccc`
- `USER32!EndPaint` at `0x180006ccc`
- `GDI32!GetStockObject` at `0x180006dac`
- `GDI32!GetStockObject` at `0x180006dac`
- `ext-ms-win-ntuser-gui-l1-1-0!FillRect` at `0x180006dbc`
- `ext-ms-win-ntuser-gui-l1-1-0!FillRect` at `0x180006dbc`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x180006d09`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x180006d09`
- `ext-ms-win-ntuser-window-l1-1-0!IsIconic` at `0x180006f22`
- `ext-ms-win-ntuser-window-l1-1-0!IsIconic` at `0x180006f22`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x180006d8f`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x180006d8f`
- `ext-ms-win-ntuser-window-l1-1-0!DefWindowProcW` at `0x180006e32`
- `ext-ms-win-ntuser-window-l1-1-0!DefWindowProcW` at `0x180006e32`
- `ext-ms-win-ntuser-window-l1-1-2!KillTimer` at `0x18000714f`
- `ext-ms-win-ntuser-window-l1-1-2!KillTimer` at `0x18000714f`
- `ext-ms-win-ntuser-window-l1-1-3!IsZoomed` at `0x180006f55`
- `ext-ms-win-ntuser-window-l1-1-3!IsZoomed` at `0x180006f55`
- `dwmapi!DwmUpdateThumbnailProperties` at `0x180007144`
- `dwmapi!DwmUpdateThumbnailProperties` at `0x180007144`

## pseudocode

```c
LRESULT __fastcall CGhostWindow::GhostWndProcWorker(
        CGhostWindow *this,
        HWND hWnd,
        UINT Msg,
        WPARAM wParam,
        struct tagRECT *lParam)
{
  __int64 v5; // r15
  int v10; // eax
  int v11; // r8d
  HDC v12; // rax
  int v13; // eax
  __int64 v14; // rcx
  int v15; // r8d
  UINT v16; // edx
  HBRUSH StockObject; // rax
  int v18; // eax
  int v19; // r8d
  int v20; // eax
  int v21; // r8d
  int v22; // eax
  int v23; // r8d
  int v24; // eax
  int v25; // r8d
  int v26; // eax
  CGhostWindow *v27; // rcx
  int v28; // r8d
  int v29; // eax
  __int64 v30; // rcx
  int v31; // r8d
  int v32; // eax
  int v33; // r8d
  int v34; // eax
  CGhostWindow *v35; // rcx
  int v36; // r8d
  int State; // eax
  int v38; // r8d
  unsigned __int8 v39; // al
  BYTE v40; // dl
  void *v41; // rcx
  BYTE v42; // al
  struct tagRECT Rect; // [rsp+30h] [rbp-51h] BYREF
  tagPAINTSTRUCT Paint; // [rsp+40h] [rbp-41h] BYREF

  v5 = 0;
  if ( Msg > 0x112 )
  {
    if ( Msg == 275 )
    {
      if ( wParam == *((_QWORD *)this + 20) )
      {
        v39 = *((_BYTE *)this + 168);
        v40 = 100;
        if ( v39 <= 0x64u )
        {
          KillTimer(hWnd, 0x64u);
          *((_QWORD *)this + 20) = 0;
        }
        else
        {
          v41 = (void *)*((_QWORD *)this + 18);
          v42 = v39 - 15;
          *(_OWORD *)&Paint.rcPaint.top = 0;
          if ( v42 > 0x64u )
            v40 = v42;
          *(_OWORD *)((char *)&Paint.fRestore + 1) = 0;
          *((_BYTE *)this + 168) = v40;
          Paint.rgbReserved[0] = v40;
          *(_OWORD *)&Paint.hdc = 0;
          LODWORD(Paint.hdc) = 4;
          DwmUpdateThumbnailProperties(v41, (const DWM_THUMBNAIL_PROPERTIES *)&Paint);
        }
      }
      return v5;
    }
    if ( Msg != 513 && Msg != 516 )
    {
      switch ( Msg )
      {
        case 0x231u:
          *((_DWORD *)this + 54) = 1;
          return v5;
        case 0x232u:
          *((_DWORD *)this + 54) = 0;
          State = CGhostWindow::GetState(this);
          if ( State != v38 )
            return v5;
          break;
        case 0x2E0u:
          CGhostWindow::HandleDpiChange(this, (unsigned int)hWnd, lParam);
          return v5;
        case 0x400u:
          v34 = CGhostWindow::GetState(this);
          if ( v34 == v36 )
            CGhostWindow::FrostBitmap(v35);
          return v5;
        case 0x406u:
          v32 = CGhostWindow::GetState(this);
          if ( v32 == v33 && !*((_DWORD *)this + 55) )
          {
            if ( (unsigned int)CGhostProcess::HasErrorReportingStarted(*((CGhostProcess **)this + 2)) )
            {
              if ( (unsigned __int16)(wParam - 1) <= 1u )
                CGhostWindow::ShowErrorReportingDlg(this);
            }
            else
            {
              (*(void (__fastcall **)(CGhostWindow *, _QWORD, struct tagRECT *))(*(_QWORD *)this + 24LL))(
                this,
                (unsigned __int16)wParam,
                lParam);
            }
          }
          return v5;
        case 0x500u:
          v29 = CGhostWindow::GetState(this);
          if ( v29 != v31 )
            return v5;
          break;
        default:
LABEL_82:
          v26 = CGhostWindow::GetState(this);
          if ( v26 == v28 && CGhostMgr::s_uHangRepMsg && Msg == CGhostMgr::s_uHangRepMsg )
          {
            CGhostWindow::OnWerDlgMsg(v27, wParam, (__int64)lParam);
            return v5;
          }
          goto LABEL_41;
      }
      if ( !(unsigned int)CGhostWindow::ShowErrorReportingDlg(v30) )
        CGhostProcess::FrostSiblings(*((_QWORD *)this + 2));
      return v5;
    }
LABEL_38:
    v18 = CGhostWindow::GetState(this);
    if ( v18 == v19 )
    {
      if ( (unsigned int)CGhostProcess::HasErrorReportingStarted(*((CGhostProcess **)this + 2)) )
      {
        CGhostWindow::ShowErrorReportingDlg(this);
        CGhostProcess::FlashWerDlg(*((CGhostProcess **)this + 2));
      }
      else
      {
        (*(void (__fastcall **)(CGhostWindow *, _QWORD, WPARAM, struct tagRECT *))(*(_QWORD *)this + 16LL))(
          this,
          Msg,
          wParam,
          lParam);
      }
    }
LABEL_41:
    v16 = Msg;
    return DefWindowProcW(hWnd, v16, wParam, (LPARAM)lParam);
  }
  if ( Msg == 274 )
  {
    switch ( wParam & 0xFFFFFFFFFFFFFFF0uLL )
    {
      case 0xF000uLL:
        return v5;
      case 0xF010uLL:
        if ( (unsigned int)IsWindowRectGreaterOrEqualToWorkArea(hWnd) && IsZoomed(hWnd) )
          return v5;
        break;
      case 0xF020uLL:
        *((_DWORD *)this + 55) = 1;
LABEL_66:
        v16 = 274;
        return DefWindowProcW(hWnd, v16, wParam, (LPARAM)lParam);
      case 0xF030uLL:
        return v5;
      case 0xF120uLL:
        if ( !IsIconic(hWnd) )
          return v5;
        break;
      default:
        goto LABEL_66;
    }
    v16 = 274;
    return DefWindowProcW(hWnd, v16, wParam, (LPARAM)lParam);
  }
  if ( Msg > 0x14 )
  {
    switch ( Msg )
    {
      case 0x18u:
        if ( !wParam )
        {
          v24 = CGhostWindow::GetState(this);
          if ( v24 == v25 )
            CGhostProcess::NotifyHideGhost(*((CGhostProcess **)this + 2), this);
        }
        return v5;
      case 0x46u:
        if ( lParam )
        {
          if ( !*((_DWORD *)this + 55) )
          {
            v20 = CGhostWindow::GetState(this);
            if ( v20 > v21 && !*((_DWORD *)this + 57) )
              lParam[2].left |= 1u;
          }
          if ( *((_DWORD *)this + 52) )
          {
            v22 = CGhostWindow::GetState(this);
            if ( v22 == v23 )
              lParam[2].left |= 4u;
          }
        }
        v16 = 70;
        return DefWindowProcW(hWnd, v16, wParam, (LPARAM)lParam);
      case 0x47u:
        if ( lParam && !*((_DWORD *)this + 55) && (lParam[2].left & 0x40) != 0 && *((_DWORD *)this + 38) )
          CGhostWindow::UpdateThumbnailRect(this);
        v16 = 71;
        return DefWindowProcW(hWnd, v16, wParam, (LPARAM)lParam);
    }
    if ( Msg != 256 )
      goto LABEL_82;
    goto LABEL_38;
  }
  switch ( Msg )
  {
    case 0x14u:
      Rect = 0;
      if ( GetClientRect(hWnd, &Rect) )
      {
        StockObject = (HBRUSH)GetStockObject(*((_QWORD *)this + 18) != 0 ? 4 : 0);
        FillRect((HDC)wParam, &Rect, StockObject);
        return 1;
      }
      break;
    case 2u:
      CGhostWindow::CleanupGhost(this);
      return v5;
    case 5u:
      switch ( wParam )
      {
        case 0uLL:
          goto LABEL_28;
        case 1uLL:
          *((_DWORD *)this + 55) = 1;
          return v5;
        case 2uLL:
LABEL_28:
          *((_DWORD *)this + 55) = 0;
          if ( *((_DWORD *)this + 38) )
            CGhostWindow::UpdateThumbnailRect(this);
          break;
      }
      break;
    case 6u:
      v13 = CGhostWindow::GetState(this);
      if ( (_WORD)wParam )
      {
        if ( (unsigned int)(unsigned __int16)wParam - 1 <= 1 && (unsigned int)(v13 - 1) <= 1 )
          PostMessageW(hWnd, 0x406u, wParam, (LPARAM)lParam);
      }
      else if ( v13 == v15 )
      {
        (*(void (__fastcall **)(__int64, _QWORD, struct tagRECT *))(*(_QWORD *)this + 24LL))(
          v14,
          (unsigned __int16)wParam,
          lParam);
      }
      v16 = 6;
      return DefWindowProcW(hWnd, v16, wParam, (LPARAM)lParam);
    case 0xFu:
      memset_0(&Paint, 0, sizeof(Paint));
      v12 = BeginPaint(hWnd, &Paint);
      if ( v12 )
        CGhostWindow::PaintGhost(this, v12, &Paint.rcPaint);
      EndPaint(hWnd, &Paint);
      break;
    case 0x10u:
      v10 = CGhostWindow::GetState(this);
      if ( v10 == v11 )
      {
        if ( (unsigned int)CGhostProcess::HasErrorReportingStarted(*((CGhostProcess **)this + 2)) )
        {
          if ( (int)CGhostWindow::ShowErrorReportingDlg(this) >= 0 )
            CGhostProcess::FlashWerDlg(*((CGhostProcess **)this + 2));
        }
        else
        {
          (*(void (__fastcall **)(CGhostWindow *))(*(_QWORD *)this + 32LL))(this);
        }
      }
      return v5;
    default:
      goto LABEL_82;
  }
  return v5;
}

```

## disassembly

```asm
0x180006bb8  push    rbp
0x180006bba  push    rbx
0x180006bbb  push    rsi
0x180006bbc  push    rdi
0x180006bbd  push    r12
0x180006bbf  push    r14
0x180006bc1  push    r15
0x180006bc3  lea     rbp, [rsp-1Fh]
0x180006bc8  sub     rsp, 0A0h
0x180006bcf  mov     rax, cs:__security_cookie
0x180006bd6  xor     rax, rsp
0x180006bd9  mov     [rbp+4Fh+var_40], rax
0x180006bdd  mov     rsi, [rbp+4Fh+lParam]
0x180006be1  xor     r15d, r15d
0x180006be4  mov     r12d, r8d
0x180006be7  mov     rbx, rcx
0x180006bea  mov     ecx, 112h
0x180006bef  mov     rdi, r9
0x180006bf2  mov     r14, rdx
0x180006bf5  lea     r8d, [r15+2]
0x180006bf9  cmp     r12d, ecx
0x180006bfc  ja      loc_180006F65
0x180006c02  jz      loc_180006EE7
0x180006c08  cmp     r12d, 14h
0x180006c0c  ja      loc_180006DCD
0x180006c12  jz      loc_180006D81
0x180006c18  mov     eax, r12d
0x180006c1b  sub     eax, r8d
0x180006c1e  jz      loc_180006D74
0x180006c24  sub     eax, 3
0x180006c27  jz      loc_180006D2F
0x180006c2d  sub     eax, 1
0x180006c30  jz      loc_180006CD7
0x180006c36  sub     eax, 9
0x180006c39  jz      short loc_180006C95
0x180006c3b  cmp     eax, 1
0x180006c3e  jnz     loc_180006FBB
0x180006c44  mov     rcx, rbx
0x180006c47  call    ?GetState@CGhostWindow@@QEBA?AW4GHOSTSTATE@@XZ; CGhostWindow::GetState(void)
0x180006c4c  cmp     eax, r8d
0x180006c4f  jnz     loc_18000715C
0x180006c55  mov     rcx, [rbx+10h]; this
0x180006c59  call    ?HasErrorReportingStarted@CGhostProcess@@QEAAHXZ; CGhostProcess::HasErrorReportingStarted(void)
0x180006c5e  mov     rcx, rbx
0x180006c61  test    eax, eax
0x180006c63  jz      short loc_180006C84
0x180006c65  lea     edx, [r15+1]
0x180006c69  call    ?ShowErrorReportingDlg@CGhostWindow@@IEAAJW4WERDLGSHOW@@@Z; CGhostWindow::ShowErrorReportingDlg(WERDLGSHOW)
0x180006c6e  test    eax, eax
0x180006c70  js      loc_18000715C
0x180006c76  mov     rcx, [rbx+10h]; this
0x180006c7a  call    ?FlashWerDlg@CGhostProcess@@QEAAHXZ; CGhostProcess::FlashWerDlg(void)
0x180006c7f  jmp     loc_18000715C
0x180006c84  mov     rax, [rbx]
0x180006c87  mov     rax, [rax+20h]
0x180006c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c90  jmp     loc_18000715C
0x180006c95  xor     edx, edx; Val
0x180006c97  lea     rcx, [rbp+4Fh+Paint]; void *
0x180006c9b  lea     r8d, [rdx+48h]; Size
0x180006c9f  call    memset_0
0x180006ca4  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x180006ca8  mov     rcx, r14; hWnd
0x180006cab  call    cs:__imp_BeginPaint
0x180006cb1  test    rax, rax
0x180006cb4  jz      short loc_180006CC5
0x180006cb6  lea     r8, [rbp+4Fh+Paint.rcPaint]; struct tagRECT *
0x180006cba  mov     rdx, rax; HDC
0x180006cbd  mov     rcx, rbx; this
0x180006cc0  call    ?PaintGhost@CGhostWindow@@AEAAXPEAUHDC__@@PEBUtagRECT@@@Z; CGhostWindow::PaintGhost(HDC__ *,tagRECT const *)
0x180006cc5  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x180006cc9  mov     rcx, r14; hWnd
0x180006ccc  call    cs:__imp_EndPaint
0x180006cd2  jmp     loc_18000715C
0x180006cd7  mov     rcx, rbx
0x180006cda  call    ?GetState@CGhostWindow@@QEBA?AW4GHOSTSTATE@@XZ; CGhostWindow::GetState(void)
0x180006cdf  movzx   edx, di
0x180006ce2  test    edx, edx
0x180006ce4  jz      short loc_180006D11
0x180006ce6  sub     edx, 1
0x180006ce9  jz      short loc_180006CF0
0x180006ceb  cmp     edx, 1
0x180006cee  jnz     short loc_180006D25
0x180006cf0  dec     eax
0x180006cf2  mov     edx, 1
0x180006cf7  cmp     eax, edx
0x180006cf9  ja      short loc_180006D25
0x180006cfb  mov     r9, rsi; lParam
0x180006cfe  mov     r8, rdi; wParam
0x180006d01  mov     edx, 406h; Msg
0x180006d06  mov     rcx, r14; hWnd
0x180006d09  call    cs:__imp_PostMessageW
0x180006d0f  jmp     short loc_180006D25
0x180006d11  cmp     eax, r8d
0x180006d14  jnz     short loc_180006D25
0x180006d16  mov     rax, [rbx]
0x180006d19  mov     r8, rsi
0x180006d1c  mov     rax, [rax+18h]
0x180006d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d25  mov     edx, 6
0x180006d2a  jmp     loc_180006E29
0x180006d2f  test    rdi, rdi
0x180006d32  jz      short loc_180006D44
0x180006d34  sub     rdi, 1
0x180006d38  jz      short loc_180006D65
0x180006d3a  cmp     rdi, 1
0x180006d3e  jnz     loc_18000715C
0x180006d44  mov     [rbx+0DCh], r15d
0x180006d4b  cmp     [rbx+98h], r15d
0x180006d52  jz      loc_18000715C
0x180006d58  mov     rcx, rbx; this
0x180006d5b  call    ?UpdateThumbnailRect@CGhostWindow@@AEAAHXZ; CGhostWindow::UpdateThumbnailRect(void)
0x180006d60  jmp     loc_18000715C
0x180006d65  mov     dword ptr [rbx+0DCh], 1
0x180006d6f  jmp     loc_18000715C
0x180006d74  mov     rcx, rbx; this
0x180006d77  call    ?CleanupGhost@CGhostWindow@@AEAAXXZ; CGhostWindow::CleanupGhost(void)
0x180006d7c  jmp     loc_18000715C
0x180006d81  xorps   xmm0, xmm0
0x180006d84  lea     rdx, [rbp+4Fh+Rect]; lpRect
0x180006d88  mov     rcx, r14; hWnd
0x180006d8b  movups  xmmword ptr [rbp+4Fh+Rect.left], xmm0
0x180006d8f  call    cs:__imp_GetClientRect
0x180006d95  test    eax, eax
0x180006d97  jz      loc_18000715C
0x180006d9d  mov     rax, [rbx+90h]
0x180006da4  neg     rax
0x180006da7  sbb     ecx, ecx
0x180006da9  and     ecx, 4; i
0x180006dac  call    cs:__imp_GetStockObject
0x180006db2  lea     rdx, [rbp+4Fh+Rect]; lprc
0x180006db6  mov     rcx, rdi; hDC
0x180006db9  mov     r8, rax; hbr
0x180006dbc  call    cs:__imp_FillRect
0x180006dc2  mov     r15d, 1
0x180006dc8  jmp     loc_18000715C
0x180006dcd  mov     eax, r12d
0x180006dd0  sub     eax, 18h
0x180006dd3  jz      loc_180006EBC
0x180006dd9  sub     eax, 2Eh ; '.'
0x180006ddc  jz      loc_180006E6C
0x180006de2  sub     eax, 1
0x180006de5  jz      short loc_180006E40
0x180006de7  cmp     eax, 0B9h
0x180006dec  jnz     loc_180006FBB
0x180006df2  mov     rcx, rbx
0x180006df5  call    ?GetState@CGhostWindow@@QEBA?AW4GHOSTSTATE@@XZ; CGhostWindow::GetState(void)
0x180006dfa  cmp     eax, r8d
0x180006dfd  jnz     short loc_180006E26
0x180006dff  mov     rcx, [rbx+10h]; this
0x180006e03  call    ?HasErrorReportingStarted@CGhostProcess@@QEAAHXZ; CGhostProcess::HasErrorReportingStarted(void)
0x180006e08  mov     rcx, rbx
0x180006e0b  test    eax, eax
0x180006e0d  jz      loc_1800070DE
0x180006e13  mov     edx, 1
0x180006e18  call    ?ShowErrorReportingDlg@CGhostWindow@@IEAAJW4WERDLGSHOW@@@Z; CGhostWindow::ShowErrorReportingDlg(WERDLGSHOW)
0x180006e1d  mov     rcx, [rbx+10h]; this
0x180006e21  call    ?FlashWerDlg@CGhostProcess@@QEAAHXZ; CGhostProcess::FlashWerDlg(void)
0x180006e26  mov     edx, r12d; Msg
0x180006e29  mov     r8, rdi; wParam
0x180006e2c  mov     r9, rsi; lParam
0x180006e2f  mov     rcx, r14; hWnd
0x180006e32  call    cs:__imp_DefWindowProcW
0x180006e38  mov     r15, rax
0x180006e3b  jmp     loc_18000715C
0x180006e40  test    rsi, rsi
0x180006e43  jz      short loc_180006E65
0x180006e45  cmp     [rbx+0DCh], r15d
0x180006e4c  jnz     short loc_180006E65
0x180006e4e  test    byte ptr [rsi+20h], 40h
0x180006e52  jz      short loc_180006E65
0x180006e54  cmp     [rbx+98h], r15d
0x180006e5b  jz      short loc_180006E65
0x180006e5d  mov     rcx, rbx; this
0x180006e60  call    ?UpdateThumbnailRect@CGhostWindow@@AEAAHXZ; CGhostWindow::UpdateThumbnailRect(void)
0x180006e65  mov     edx, 47h ; 'G'
0x180006e6a  jmp     short loc_180006E29
0x180006e6c  test    rsi, rsi
0x180006e6f  jz      short loc_180006EB2
0x180006e71  cmp     [rbx+0DCh], r15d
0x180006e78  jnz     short loc_180006E98
0x180006e7a  mov     rcx, rbx
0x180006e7d  call    ?GetState@CGhostWindow@@QEBA?AW4GHOSTSTATE@@XZ; CGhostWindow::GetState(void)
0x180006e82  cmp     eax, r8d
0x180006e85  jle     short loc_180006E98
0x180006e87  cmp     [rbx+0E4h], r15d
0x180006e8e  jnz     short loc_180006E98
0x180006e90  mov     edx, 1
0x180006e95  or      [rsi+20h], edx
0x180006e98  cmp     [rbx+0D0h], r15d
0x180006e9f  jz      short loc_180006EB2
0x180006ea1  mov     rcx, rbx
0x180006ea4  call    ?GetState@CGhostWindow@@QEBA?AW4GHOSTSTATE@@XZ; CGhostWindow::GetState(void)
0x180006ea9  cmp     eax, r8d
0x180006eac  jnz     short loc_180006EB2
0x180006eae  or      dword ptr [rsi+20h], 4
0x180006eb2  mov     edx, 46h ; 'F'
0x180006eb7  jmp     loc_180006E29
0x180006ebc  test    rdi, rdi
0x180006ebf  jnz     loc_18000715C
0x180006ec5  mov     rcx, rbx
0x180006ec8  call    ?GetState@CGhostWindow@@QEBA?AW4GHOSTSTATE@@XZ; CGhostWindow::GetState(void)
0x180006ecd  cmp     eax, r8d
0x180006ed0  jnz     loc_18000715C
0x180006ed6  mov     rcx, [rbx+10h]; this
0x180006eda  mov     rdx, rbx; struct CGhostWindow *
0x180006edd  call    ?NotifyHideGhost@CGhostProcess@@QEAAHPEAVCGhostWindow@@@Z; CGhostProcess::NotifyHideGhost(CGhostWindow *)
0x180006ee2  jmp     loc_18000715C
0x180006ee7  mov     rax, rdi
0x180006eea  and     rax, 0FFFFFFFFFFFFFFF0h
0x180006eee  sub     rax, 0F000h
0x180006ef4  jz      loc_18000715C
0x180006efa  sub     rax, 10h
0x180006efe  jz      short loc_180006F46
0x180006f00  sub     rax, 10h
0x180006f04  jz      short loc_180006F3A
0x180006f06  sub     rax, 10h
0x180006f0a  jz      loc_18000715C
0x180006f10  cmp     rax, 0F0h
0x180006f16  jz      short loc_180006F1F
0x180006f18  mov     edx, ecx
0x180006f1a  jmp     loc_180006E29
0x180006f1f  mov     rcx, r14; hWnd
0x180006f22  call    cs:__imp_IsIconic
0x180006f28  test    eax, eax
0x180006f2a  jz      loc_18000715C
0x180006f30  mov     edx, 112h
0x180006f35  jmp     loc_180006E29
0x180006f3a  mov     dword ptr [rbx+0DCh], 1
0x180006f44  jmp     short loc_180006F18
0x180006f46  mov     rcx, r14; hWnd
0x180006f49  call    IsWindowRectGreaterOrEqualToWorkArea
0x180006f4e  test    eax, eax
0x180006f50  jz      short loc_180006F30
0x180006f52  mov     rcx, r14; hWnd
0x180006f55  call    cs:__imp_IsZoomed
0x180006f5b  test    eax, eax
0x180006f5d  jnz     loc_18000715C
0x180006f63  jmp     short loc_180006F30
0x180006f65  mov     eax, r12d
0x180006f68  sub     eax, 113h
0x180006f6d  jz      loc_1800070F8
0x180006f73  sub     eax, 0EEh
0x180006f78  jz      loc_180006DF2
0x180006f7e  sub     eax, 3
0x180006f81  jz      loc_180006DF2
0x180006f87  sub     eax, 2Dh ; '-'
0x180006f8a  jz      loc_1800070D2
0x180006f90  sub     eax, 1
0x180006f93  jz      loc_18000709A
0x180006f99  sub     eax, 0AEh
0x180006f9e  jz      loc_18000708A
0x180006fa4  sub     eax, 120h
0x180006fa9  jz      loc_18000706F
0x180006faf  sub     eax, 6
0x180006fb2  jz      short loc_18000700C
0x180006fb4  cmp     eax, 0FAh
0x180006fb9  jz      short loc_180006FF3
0x180006fbb  mov     rcx, rbx
0x180006fbe  call    ?GetState@CGhostWindow@@QEBA?AW4GHOSTSTATE@@XZ; CGhostWindow::GetState(void)
0x180006fc3  cmp     eax, r8d
0x180006fc6  jnz     loc_180006E26
0x180006fcc  mov     eax, cs:?s_uHangRepMsg@CGhostMgr@@2IA; uint CGhostMgr::s_uHangRepMsg
0x180006fd2  test    eax, eax
0x180006fd4  jz      loc_180006E26
0x180006fda  cmp     r12d, eax
0x180006fdd  jnz     loc_180006E26
0x180006fe3  mov     r8, rsi; __int64
0x180006fe6  mov     rdx, rdi; unsigned __int64
0x180006fe9  call    ?OnWerDlgMsg@CGhostWindow@@AEAAH_K_J@Z; CGhostWindow::OnWerDlgMsg(unsigned __int64,__int64)
0x180006fee  jmp     loc_18000715C
0x180006ff3  mov     rcx, rbx
0x180006ff6  call    ?GetState@CGhostWindow@@QEBA?AW4GHOSTSTATE@@XZ; CGhostWindow::GetState(void)
0x180006ffb  cmp     eax, r8d
0x180006ffe  jnz     loc_18000715C
0x180007004  mov     edx, r8d
0x180007007  jmp     loc_1800070B7
0x18000700c  mov     rcx, rbx
0x18000700f  call    ?GetState@CGhostWindow@@QEBA?AW4GHOSTSTATE@@XZ; CGhostWindow::GetState(void)
0x180007014  cmp     eax, r8d
0x180007017  jnz     loc_18000715C
0x18000701d  cmp     [rbx+0DCh], r15d
0x180007024  jnz     loc_18000715C
0x18000702a  mov     rcx, [rbx+10h]; this
0x18000702e  call    ?HasErrorReportingStarted@CGhostProcess@@QEAAHXZ; CGhostProcess::HasErrorReportingStarted(void)
0x180007033  test    eax, eax
0x180007035  jz      short loc_180007055
0x180007037  mov     edx, 1
0x18000703c  sub     di, dx
0x18000703f  cmp     di, dx
0x180007042  ja      loc_18000715C
0x180007048  mov     rcx, rbx
0x18000704b  call    ?ShowErrorReportingDlg@CGhostWindow@@IEAAJW4WERDLGSHOW@@@Z; CGhostWindow::ShowErrorReportingDlg(WERDLGSHOW)
0x180007050  jmp     loc_18000715C
0x180007055  mov     rax, [rbx]
0x180007058  mov     r8, rsi
0x18000705b  movzx   edx, di
0x18000705e  mov     rcx, rbx
0x180007061  mov     rax, [rax+18h]
0x180007065  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
