# CFrameImpl::OnGetMinMaxInfo(tagMINMAXINFO *)

- ea: `0x180067710`
- end: `0x1800679f6`
- name: `?OnGetMinMaxInfo@CFrameImpl@@IEAAXPEAUtagMINMAXINFO@@@Z`
- size: `742`
- prototype: `void __fastcall(CFrameImpl *this, tagMINMAXINFO *lpMMI)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180068b20`
- `0x18006aa60`
- `0x18008c3d0`

## callees

- `0x180063e8c`
- `0x180067710`
- `0x18006cab0`
- `0x18006e7b0`
- `0x180231d70`
- `0x1802b62e0`
- `0x1802c4640`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x1800679b6`
- `USER32!GetSystemMetrics` at `0x1800679c4`
- `USER32!GetSystemMetrics` at `0x1800679b6`
- `USER32!GetSystemMetrics` at `0x1800679c4`
- `USER32!IsIconic` at `0x1800677ed`
- `USER32!IsIconic` at `0x1800677ed`
- `USER32!GetMonitorInfoW` at `0x180067862`
- `USER32!GetMonitorInfoW` at `0x180067862`
- `USER32!MonitorFromPoint` at `0x180067855`
- `USER32!MonitorFromPoint` at `0x180067855`
- `USER32!SystemParametersInfoW` at `0x1800678ba`
- `USER32!SystemParametersInfoW` at `0x1800678ba`
- `USER32!IsWindowVisible` at `0x180067760`
- `USER32!IsWindowVisible` at `0x18006777d`
- `USER32!IsWindowVisible` at `0x180067760`
- `USER32!IsWindowVisible` at `0x18006777d`
- `USER32!GetWindowRect` at `0x1800677dc`
- `USER32!GetWindowRect` at `0x1800677dc`
- `USER32!CopyRect` at `0x18006781b`
- `USER32!CopyRect` at `0x180067874`
- `USER32!CopyRect` at `0x180067882`
- `USER32!CopyRect` at `0x18006781b`
- `USER32!CopyRect` at `0x180067874`
- `USER32!CopyRect` at `0x180067882`
- `USER32!GetWindowPlacement` at `0x18006780d`
- `USER32!GetWindowPlacement` at `0x18006780d`
- `USER32!OffsetRect` at `0x1800678ff`
- `USER32!OffsetRect` at `0x1800678ff`

## pseudocode

```c
void __fastcall CFrameImpl::OnGetMinMaxInfo(CFrameImpl *this, tagMINMAXINFO *lpMMI)
{
  CMFCRibbonBar *m_pRibbonBar; // rax
  int v5; // edi
  HWND m_hWnd; // rcx
  CFrameWnd *m_pFrame; // rcx
  CFrameWnd *v8; // rcx
  HMONITOR v9; // rax
  char ShellAutohideBars; // al
  int bottom; // ecx
  char v12; // dl
  int top; // r8d
  int right; // eax
  bool v15; // zf
  int left; // edx
  CMFCRibbonBar *v17; // rax
  CRect rect; // [rsp+20h] [rbp-69h] BYREF
  CRect rectWork; // [rsp+30h] [rbp-59h] BYREF
  CRect rectWindow; // [rsp+40h] [rbp-49h] BYREF
  CRect rectScreen; // [rsp+50h] [rbp-39h] BYREF
  tagMONITORINFO mi; // [rsp+60h] [rbp-29h] BYREF
  tagWINDOWPLACEMENT wp; // [rsp+88h] [rbp-1h] BYREF

  if ( !lpMMI )
    AfxThrowInvalidArgException();
  m_pRibbonBar = this->m_pRibbonBar;
  v5 = 0;
  if ( m_pRibbonBar )
  {
    m_hWnd = m_pRibbonBar->m_hWnd;
    if ( m_hWnd )
    {
      if ( IsWindowVisible(m_hWnd) || this->m_FullScreenMgr.m_bFullScreen || !IsWindowVisible(this->m_pFrame->m_hWnd) )
      {
        if ( this->m_pRibbonBar->m_bReplaceFrameCaption )
          v5 = 1;
      }
    }
  }
  if ( (CWnd::GetStyle(this->m_pFrame) & 0xC00000) == 0 || (CWnd::GetStyle(this->m_pFrame) & 0x800000) == 0 || v5 )
  {
    m_pFrame = this->m_pFrame;
    rectWindow = 0;
    GetWindowRect(m_pFrame->m_hWnd, &rectWindow);
    if ( IsIconic(this->m_pFrame->m_hWnd) )
    {
      v8 = this->m_pFrame;
      wp.length = 44;
      GetWindowPlacement(v8->m_hWnd, &wp);
      CopyRect(&rectWindow, &wp.rcNormalPosition);
    }
    mi.cbSize = 40;
    rectWork.left = (rectWindow.left + rectWindow.right) / 2;
    rectWork.top = (rectWindow.top + rectWindow.bottom) / 2;
    rect = 0;
    v9 = MonitorFromPoint(*(POINT *)&rectWork.left, 2u);
    if ( GetMonitorInfoW(v9, &mi) )
    {
      CopyRect(&rectWork, &mi.rcWork);
      CopyRect(&rectScreen, &mi.rcMonitor);
      rect.left = rectWork.left - rectScreen.left;
      rect.top = rectWork.top - rectScreen.top;
      rect.bottom = rectWork.bottom - rectScreen.top;
      rect.right = rectWork.right - rectScreen.left;
    }
    else
    {
      SystemParametersInfoW(0x30u, 0, &rect, 0);
    }
    if ( v5 )
    {
      if ( !afxGlobalData.m_bInitialized )
      {
        AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
        afxGlobalData.m_bInitialized = 1;
      }
      if ( AFX_GLOBAL_DATA::IsDwmCompositionEnabled(&afxGlobalData) )
        OffsetRect(&rect, -rect.left, -rect.top);
    }
    if ( !afxGlobalData.m_bInitialized )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      afxGlobalData.m_bInitialized = 1;
    }
    ShellAutohideBars = AFX_GLOBAL_DATA::GetShellAutohideBars(&afxGlobalData);
    bottom = rect.bottom;
    v12 = ShellAutohideBars;
    if ( (ShellAutohideBars & 8) != 0 )
    {
      bottom = rect.bottom - 2;
      rect.bottom -= 2;
    }
    top = rect.top;
    if ( (ShellAutohideBars & 4) != 0 )
    {
      top = rect.top + 2;
      rect.top += 2;
    }
    right = rect.right;
    if ( (v12 & 2) != 0 )
    {
      right = rect.right - 2;
      rect.right -= 2;
    }
    v15 = (v12 & 1) == 0;
    left = rect.left;
    if ( !v15 )
    {
      left = rect.left + 2;
      rect.left += 2;
    }
    lpMMI->ptMaxPosition.x = left;
    lpMMI->ptMaxSize.x = right - left;
    lpMMI->ptMaxSize.y = bottom - top;
    lpMMI->ptMaxPosition.y = top;
    v17 = this->m_pRibbonBar;
    if ( v17 && v17->m_hWnd && v17->m_bReplaceFrameCaption )
    {
      if ( !afxGlobalData.m_bInitialized )
      {
        AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
        afxGlobalData.m_bInitialized = 1;
      }
      if ( !AFX_GLOBAL_DATA::IsDwmCompositionEnabled(&afxGlobalData) )
      {
        lpMMI->ptMinTrackSize.x = GetSystemMetrics(34);
        lpMMI->ptMinTrackSize.y = GetSystemMetrics(35);
      }
    }
  }
}

```

## disassembly

```asm
0x180067710  mov     [rsp-8+arg_10], rbx
0x180067715  push    rbp
0x180067716  push    rsi
0x180067717  push    rdi
0x180067718  push    r13
0x18006771a  push    r15
0x18006771c  lea     rbp, [rsp-37h]
0x180067721  sub     rsp, 0C0h
0x180067728  mov     rax, cs:__security_cookie
0x18006772f  xor     rax, rsp
0x180067732  mov     [rbp+57h+var_28], rax
0x180067736  mov     rsi, lpMMI
0x180067739  mov     rbx, this
0x18006773c  test    lpMMI, lpMMI
0x18006773f  jz      loc_1800679F0
0x180067745  mov     rax, [this+180h]
0x18006774c  xor     edi, edi
0x18006774e  lea     r13d, [rdi+1]
0x180067752  test    rax, rax
0x180067755  jz      short loc_180067798
0x180067757  mov     this, [rax+40h]; hWnd
0x18006775b  test    this, this
0x18006775e  jz      short loc_180067798
0x180067760  call    cs:__imp_IsWindowVisible
0x180067766  test    eax, eax
0x180067768  jnz     short loc_180067787
0x18006776a  cmp     [rbx+148h], edi
0x180067770  jnz     short loc_180067787
0x180067772  mov     this, [rbx+118h]
0x180067779  mov     this, [this+40h]; hWnd
0x18006777d  call    cs:__imp_IsWindowVisible
0x180067783  test    eax, eax
0x180067785  jnz     short loc_180067798
0x180067787  mov     rax, [rbx+180h]
0x18006778e  cmp     [rax+468h], edi
0x180067794  cmovnz  edi, r13d
0x180067798  mov     this, [rbx+118h]; this
0x18006779f  call    ?GetStyle@CWnd@@QEBAKXZ; CWnd::GetStyle(void)
0x1800677a4  test    eax, 0C00000h
0x1800677a9  jz      short loc_1800677C5
0x1800677ab  mov     this, [rbx+118h]; this
0x1800677b2  call    ?GetStyle@CWnd@@QEBAKXZ; CWnd::GetStyle(void)
0x1800677b7  bt      eax, 17h
0x1800677bb  jnb     short loc_1800677C5
0x1800677bd  test    edi, edi
0x1800677bf  jz      loc_1800679CD
0x1800677c5  mov     this, [rbx+118h]
0x1800677cc  lea     lpMMI, [rbp+57h+rectWindow]; lpRect
0x1800677d0  xorps   xmm0, xmm0
0x1800677d3  movdqu  xmmword ptr [rbp+57h+rectWindow.left], xmm0
0x1800677d8  mov     this, [this+40h]; hWnd
0x1800677dc  call    cs:__imp_GetWindowRect
0x1800677e2  mov     this, [rbx+118h]
0x1800677e9  mov     this, [this+40h]; hWnd
0x1800677ed  call    cs:__imp_IsIconic
0x1800677f3  test    eax, eax
0x1800677f5  jz      short loc_180067821
0x1800677f7  mov     this, [rbx+118h]
0x1800677fe  lea     lpMMI, [rbp+57h+wp]; lpwndpl
0x180067802  mov     [rbp+57h+wp.length], 2Ch ; ','
0x180067809  mov     this, [this+40h]; hWnd
0x18006780d  call    cs:__imp_GetWindowPlacement
0x180067813  lea     lpMMI, [rbp+57h+wp.rcNormalPosition]; lprcSrc
0x180067817  lea     this, [rbp+57h+rectWindow]; lprcDst
0x18006781b  call    cs:__imp_CopyRect
0x180067821  mov     eax, [rbp+57h+rectWindow.right]
0x180067824  xorps   xmm0, xmm0
0x180067827  add     eax, [rbp+57h+rectWindow.left]
0x18006782a  cdq
0x18006782b  mov     [rbp+57h+mi.cbSize], 28h ; '('
0x180067832  sub     eax, edx
0x180067834  sar     eax, 1
0x180067836  mov     [rbp+57h+rectWork.left], eax
0x180067839  mov     eax, [rbp+57h+rectWindow.bottom]
0x18006783c  add     eax, [rbp+57h+rectWindow.top]
0x18006783f  cdq
0x180067840  sub     eax, edx
0x180067842  mov     edx, 2; dwFlags
0x180067847  sar     eax, 1
0x180067849  mov     [rbp+57h+rectWork.top], eax
0x18006784c  mov     this, qword ptr [rbp+57h+rectWork.left]; pt
0x180067850  movdqu  xmmword ptr [rbp+57h+rect.left], xmm0
0x180067855  call    cs:__imp_MonitorFromPoint
0x18006785b  mov     this, rax; hMonitor
0x18006785e  lea     lpMMI, [rbp+57h+mi]; lpmi
0x180067862  call    cs:__imp_GetMonitorInfoW
0x180067868  test    eax, eax
0x18006786a  jz      short loc_1800678AE
0x18006786c  lea     lpMMI, [rbp+57h+mi.rcWork]; lprcSrc
0x180067870  lea     this, [rbp+57h+rectWork]; lprcDst
0x180067874  call    cs:__imp_CopyRect
0x18006787a  lea     lpMMI, [rbp+57h+mi.rcMonitor]; lprcSrc
0x18006787e  lea     this, [rbp+57h+rectScreen]; lprcDst
0x180067882  call    cs:__imp_CopyRect
0x180067888  mov     eax, [rbp+57h+rectWork.left]
0x18006788b  sub     eax, [rbp+57h+rectScreen.left]
0x18006788e  mov     ecx, [rbp+57h+rectWork.top]
0x180067891  sub     ecx, [rbp+57h+rectScreen.top]
0x180067894  mov     [rbp+57h+rect.left], eax
0x180067897  sub     eax, [rbp+57h+rectWork.left]
0x18006789a  add     eax, [rbp+57h+rectWork.right]
0x18006789d  mov     [rbp+57h+rect.top], ecx
0x1800678a0  sub     ecx, [rbp+57h+rectWork.top]
0x1800678a3  add     ecx, [rbp+57h+rectWork.bottom]
0x1800678a6  mov     [rbp+57h+rect.bottom], ecx
0x1800678a9  mov     [rbp+57h+rect.right], eax
0x1800678ac  jmp     short loc_1800678C0
0x1800678ae  xor     edx, edx; uiParam
0x1800678b0  lea     r8, [rbp+57h+rect]; pvParam
0x1800678b4  xor     r9d, r9d; fWinIni
0x1800678b7  lea     ecx, [lpMMI+30h]; uiAction
0x1800678ba  call    cs:__imp_SystemParametersInfoW
0x1800678c0  lea     r15, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; AFX_GLOBAL_DATA afxGlobalData
0x1800678c7  test    edi, edi
0x1800678c9  jz      short loc_180067905
0x1800678cb  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x1800678d2  jnz     short loc_1800678E3
0x1800678d4  mov     this, r15; this
0x1800678d7  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1800678dc  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r13d; AFX_GLOBAL_DATA afxGlobalData ...
0x1800678e3  mov     this, r15; this
0x1800678e6  call    ?IsDwmCompositionEnabled@AFX_GLOBAL_DATA@@QEAAHXZ; AFX_GLOBAL_DATA::IsDwmCompositionEnabled(void)
0x1800678eb  test    eax, eax
0x1800678ed  jz      short loc_180067905
0x1800678ef  mov     edx, [rbp+57h+rect.left]
0x1800678f2  lea     this, [rbp+57h+rect]; lprc
0x1800678f6  mov     r8d, [rbp+57h+rect.top]
0x1800678fa  neg     edx; dx
0x1800678fc  neg     r8d; dy
0x1800678ff  call    cs:__imp_OffsetRect
0x180067905  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x18006790c  jnz     short loc_18006791D
0x18006790e  mov     this, r15; this
0x180067911  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x180067916  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r13d; AFX_GLOBAL_DATA afxGlobalData ...
0x18006791d  mov     this, r15; this
0x180067920  call    ?GetShellAutohideBars@AFX_GLOBAL_DATA@@QEAAHXZ; AFX_GLOBAL_DATA::GetShellAutohideBars(void)
0x180067925  mov     ecx, [rbp+57h+rect.bottom]
0x180067928  mov     edx, eax
0x18006792a  test    al, 8
0x18006792c  jz      short loc_180067934
0x18006792e  sub     ecx, 2
0x180067931  mov     [rbp+57h+rect.bottom], ecx
0x180067934  mov     r8d, [rbp+57h+rect.top]
0x180067938  test    dl, 4
0x18006793b  jz      short loc_180067945
0x18006793d  add     r8d, 2
0x180067941  mov     [rbp+57h+rect.top], r8d
0x180067945  mov     eax, [rbp+57h+rect.right]
0x180067948  test    dl, 2
0x18006794b  jz      short loc_180067953
0x18006794d  sub     eax, 2
0x180067950  mov     [rbp+57h+rect.right], eax
0x180067953  test    r13b, dl
0x180067956  mov     edx, [rbp+57h+rect.left]
0x180067959  jz      short loc_180067961
0x18006795b  add     edx, 2
0x18006795e  mov     [rbp+57h+rect.left], edx
0x180067961  sub     eax, edx
0x180067963  mov     [rsi+10h], edx
0x180067966  sub     ecx, r8d
0x180067969  mov     [rsi+8], eax
0x18006796c  mov     [rsi+0Ch], ecx
0x18006796f  mov     [rsi+14h], r8d
0x180067973  mov     rax, [rbx+180h]
0x18006797a  test    rax, rax
0x18006797d  jz      short loc_1800679CD
0x18006797f  cmp     qword ptr [rax+40h], 0
0x180067984  jz      short loc_1800679CD
0x180067986  cmp     dword ptr [rax+468h], 0
0x18006798d  jz      short loc_1800679CD
0x18006798f  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x180067996  jnz     short loc_1800679A7
0x180067998  mov     this, r15; this
0x18006799b  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1800679a0  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r13d; AFX_GLOBAL_DATA afxGlobalData ...
0x1800679a7  mov     this, r15; this
0x1800679aa  call    ?IsDwmCompositionEnabled@AFX_GLOBAL_DATA@@QEAAHXZ; AFX_GLOBAL_DATA::IsDwmCompositionEnabled(void)
0x1800679af  test    eax, eax
0x1800679b1  jnz     short loc_1800679CD
0x1800679b3  lea     ecx, [rax+22h]; nIndex
0x1800679b6  call    cs:__imp_GetSystemMetrics
0x1800679bc  mov     ecx, 23h ; '#'; nIndex
0x1800679c1  mov     [rsi+18h], eax
0x1800679c4  call    cs:__imp_GetSystemMetrics
0x1800679ca  mov     [rsi+1Ch], eax
0x1800679cd  mov     this, [rbp+57h+var_28]
0x1800679d1  xor     this, rsp; StackCookie
0x1800679d4  call    __security_check_cookie
0x1800679d9  mov     rbx, [rsp+0E0h+arg_10]
0x1800679e1  add     rsp, 0C0h
0x1800679e8  pop     r15
0x1800679ea  pop     r13
0x1800679ec  pop     rdi
0x1800679ed  pop     rsi
0x1800679ee  pop     rbp
0x1800679ef  retn
0x1800679f0  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
```
