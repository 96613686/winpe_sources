# CMFCRibbonKeyTip::Show(int)

- ea: `0x1801132e0`
- end: `0x1801135df`
- name: `?Show@CMFCRibbonKeyTip@@QEAAHH@Z`
- size: `767`
- prototype: `int __fastcall(CMFCRibbonKeyTip *this, int bRepos)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1800e6fa0`

## callees

- `0x180002e40`
- `0x180009844`
- `0x18006cab0`
- `0x1801132e0`
- `0x180231d70`
- `0x1802984e0`
- `0x1802af110`
- `0x1802afe10`
- `0x1802b0630`
- `0x1802b06e0`
- `0x1802b6730`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1801134c3`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1801134c3`
- `USER32!GetMonitorInfoW` at `0x18011341c`
- `USER32!GetMonitorInfoW` at `0x18011341c`
- `USER32!MonitorFromPoint` at `0x18011340f`
- `USER32!MonitorFromPoint` at `0x18011340f`
- `USER32!SystemParametersInfoW` at `0x180113442`
- `USER32!SystemParametersInfoW` at `0x180113442`
- `USER32!SetLayeredWindowAttributes` at `0x180113587`
- `USER32!SetLayeredWindowAttributes` at `0x180113587`
- `USER32!LoadCursorW` at `0x18011349e`
- `USER32!LoadCursorW` at `0x18011349e`
- `USER32!CopyRect` at `0x18011342e`
- `USER32!CopyRect` at `0x18011342e`
- `USER32!IsRectEmpty` at `0x1801133db`
- `USER32!IsRectEmpty` at `0x1801133db`
- `USER32!OffsetRect` at `0x180113467`
- `USER32!OffsetRect` at `0x180113491`
- `USER32!OffsetRect` at `0x180113467`
- `USER32!OffsetRect` at `0x180113491`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMFCRibbonKeyTip::Show(CMFCRibbonKeyTip *this, __int64 bRepos)
{
  __int64 v4; // rax
  CWnd *v5; // rdi
  CFont *v6; // rsi
  HMONITOR v7; // rax
  int v8; // edx
  int v9; // r8d
  int v10; // edx
  HCURSOR CursorW; // rax
  const wchar_t *v12; // rax
  const wchar_t *v13; // rdi
  unsigned int v14; // edi
  CMFCVisualManager *Instance; // rax
  CClientDC dc; // [rsp+50h] [rbp-31h] BYREF
  _BYTE rect_8[53]; // [rsp+80h] [rbp-1h] OVERLAPPED BYREF

  if ( this && this->m_hWnd && !(_DWORD)bRepos )
  {
    CWnd::ShowWindow(this, 4);
    return 1;
  }
  v4 = ((__int64 (__fastcall *)(CMFCRibbonBaseElement *, __int64))this->m_pElement->GetParentWnd)(
         this->m_pElement,
         bRepos);
  v5 = (CWnd *)v4;
  if ( v4 && *(_QWORD *)(v4 + 64) )
  {
    CClientDC::CClientDC((CClientDC *)&dc.m_hDC, 0);
    if ( !afxGlobalData.m_bInitialized )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      afxGlobalData.m_bInitialized = 1;
    }
    v6 = CDC::SelectObject((CDC *)&dc.m_hDC, &afxGlobalData.fontRegular);
    if ( !v6 )
      AfxThrowInvalidArgException();
    this->m_pElement->GetKeyTipRect(this->m_pElement, (CRect *)rect_8, (CDC *)&dc.m_hDC, this->m_bIsMenu);
    CDC::SelectObject((CDC *)&dc.m_hDC, v6);
    if ( IsRectEmpty((const RECT *)rect_8) )
    {
LABEL_34:
      CClientDC::~CClientDC((CClientDC *)&dc.m_hDC);
      return 0;
    }
    CWnd::ClientToScreen(v5, (tagRECT *)rect_8);
    *(_OWORD *)&rect_8[16] = 0;
    *(_DWORD *)&rect_8[32] = 40;
    v7 = MonitorFromPoint(*(POINT *)rect_8, 2u);
    if ( GetMonitorInfoW(v7, (LPMONITORINFO)&rect_8[32]) )
      CopyRect((LPRECT)&rect_8[16], (const RECT *)&rect_8[52]);
    else
      SystemParametersInfoW(0x30u, 0, &rect_8[16], 0);
    if ( *(int *)&rect_8[8] <= *(int *)&rect_8[24] )
    {
      if ( *(int *)rect_8 >= *(int *)&rect_8[16] )
        goto LABEL_20;
      v8 = *(_DWORD *)&rect_8[16] - *(_DWORD *)rect_8;
    }
    else
    {
      v8 = *(_DWORD *)&rect_8[24] - *(_DWORD *)&rect_8[8];
    }
    OffsetRect((LPRECT)rect_8, v8, 0);
LABEL_20:
    if ( *(int *)&rect_8[12] <= *(int *)&rect_8[28] )
    {
      if ( *(int *)&rect_8[4] >= *(int *)&rect_8[20] )
        goto LABEL_25;
      v10 = *(_DWORD *)&rect_8[20] - *(_DWORD *)&rect_8[4];
      v9 = 0;
    }
    else
    {
      v9 = *(_DWORD *)&rect_8[28] - *(_DWORD *)&rect_8[12];
      v10 = 0;
    }
    OffsetRect((LPRECT)rect_8, v10, v9);
LABEL_25:
    CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
    v12 = AfxRegisterWndClass(0x800u, CursorW, (HBRUSH__ *)0x10, 0);
    v13 = v12;
    if ( v12 )
      LODWORD(v12) = wcslen(v12);
    ATL::CSimpleStringT<wchar_t,1>::SetString(&CMFCRibbonKeyTip::m_strClassName, v13, (int)v12);
    v14 = 136;
    if ( this->m_pElement->IsDisabled(this->m_pElement) )
    {
      Instance = CMFCVisualManager::GetInstance();
      if ( Instance->IsLayeredRibbonKeyTip(Instance) )
        v14 = 524424;
    }
    if ( this->CreateEx(
           this,
           v14,
           CMFCRibbonKeyTip::m_strClassName.m_pszData,
           &CmdLine,
           0x80000000,
           (const tagRECT *)rect_8,
           0,
           0,
           0) )
    {
      this->m_rectScreen = *(CRect *)rect_8;
      if ( (v14 & 0x80000) != 0 )
        SetLayeredWindowAttributes(this->m_hWnd, 0, 0x80u, 2u);
      CWnd::ShowWindow(this, 4);
      CClientDC::~CClientDC((CClientDC *)&dc.m_hDC);
      return 1;
    }
    goto LABEL_34;
  }
  return 0;
}

```

## disassembly

```asm
0x1801132e0  mov     rax, rsp
0x1801132e3  mov     [rax+10h], rbx
0x1801132e7  mov     [rax+18h], rsi
0x1801132eb  mov     [rax+20h], rdi
0x1801132ef  push    rbp
0x1801132f0  lea     rbp, [rax-5Fh]
0x1801132f4  sub     rsp, 0D0h
0x1801132fb  mov     rax, cs:__security_cookie
0x180113302  xor     rax, rsp
0x180113305  mov     [rbp+57h+var_10], rax
0x180113309  mov     rbx, this
0x18011330c  test    this, this
0x18011330f  jz      short loc_180113330
0x180113311  cmp     qword ptr [this+40h], 0
0x180113316  jz      short loc_180113330
0x180113318  test    bRepos, bRepos
0x18011331a  jnz     short loc_180113330
0x18011331c  mov     bRepos, 4; nCmdShow
0x180113321  call    ?ShowWindow@CWnd@@QEAAHH@Z; CWnd::ShowWindow(int)
0x180113326  mov     eax, 1
0x18011332b  jmp     loc_1801135B4
0x180113330  mov     this, [this+0E8h]
0x180113337  mov     rax, [this]
0x18011333a  mov     rax, [rax+158h]
0x180113341  call    cs:__guard_dispatch_icall_fptr
0x180113347  mov     rdi, rax
0x18011334a  test    rax, rax
0x18011334d  jz      loc_1801135B2
0x180113353  cmp     qword ptr [rax+40h], 0
0x180113358  jz      loc_1801135B2
0x18011335e  xor     bRepos, bRepos; pWnd
0x180113360  lea     this, [rbp+57h+dc.m_hDC]; this
0x180113364  call    ??0CClientDC@@QEAA@PEAVCWnd@@@Z; CClientDC::CClientDC(CWnd *)
0x180113369  nop
0x18011336a  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x180113371  jnz     short loc_180113389
0x180113373  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x18011337a  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18011337f  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x180113389  lea     rdx, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.fontRegular; pFont
0x180113390  lea     this, [rbp+57h+dc.m_hDC]; this
0x180113394  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x180113399  mov     rsi, rax
0x18011339c  test    rax, rax
0x18011339f  jz      loc_1801135D9
0x1801133a5  mov     this, [rbx+0E8h]
0x1801133ac  mov     rax, [this]
0x1801133af  mov     r9d, [rbx+100h]
0x1801133b6  lea     r8, [rbp+57h+dc.m_hDC]
0x1801133ba  lea     rdx, [rbp+57h+rect.right]
0x1801133be  mov     rax, [rax+3C0h]
0x1801133c5  call    cs:__guard_dispatch_icall_fptr
0x1801133cb  mov     rdx, rsi; pFont
0x1801133ce  lea     this, [rbp+57h+dc.m_hDC]; this
0x1801133d2  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x1801133d7  lea     this, [rbp+57h+rect.right]; lprc
0x1801133db  call    cs:__imp_IsRectEmpty
0x1801133e1  test    eax, eax
0x1801133e3  jnz     loc_1801135A9
0x1801133e9  lea     rdx, [rbp+57h+rect.right]; lpRect
0x1801133ed  mov     this, rdi; this
0x1801133f0  call    ?ClientToScreen@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ClientToScreen(tagRECT *)
0x1801133f5  xorps   xmm0, xmm0
0x1801133f8  movdqu  xmmword ptr [rbp+57h+rectScreen.right], xmm0
0x1801133fd  mov     [rbp+57h+mi.rcMonitor.top], 28h ; '('
0x180113404  mov     esi, 2
0x180113409  mov     bRepos, esi; dwFlags
0x18011340b  mov     this, qword ptr [rbp+57h+rect.right]; pt
0x18011340f  call    cs:__imp_MonitorFromPoint
0x180113415  mov     this, rax; hMonitor
0x180113418  lea     rdx, [rbp+57h+mi.rcMonitor.top]; lpmi
0x18011341c  call    cs:__imp_GetMonitorInfoW
0x180113422  test    eax, eax
0x180113424  jz      short loc_180113436
0x180113426  lea     rdx, [rbp+57h+mi.rcWork.right]; lprcSrc
0x18011342a  lea     this, [rbp+57h+rectScreen.right]; lprcDst
0x18011342e  call    cs:__imp_CopyRect
0x180113434  jmp     short loc_180113448
0x180113436  xor     r9d, r9d; fWinIni
0x180113439  lea     r8, [rbp+57h+rectScreen.right]; pvParam
0x18011343d  xor     bRepos, bRepos; uiParam
0x18011343f  lea     ecx, [rdx+30h]; uiAction
0x180113442  call    cs:__imp_SystemParametersInfoW
0x180113448  mov     bRepos, [rbp+57h+mi.cbSize]
0x18011344b  cmp     [rbp+57h+rectScreen.left], bRepos
0x18011344e  jle     short loc_180113455
0x180113450  sub     bRepos, [rbp+57h+rectScreen.left]
0x180113453  jmp     short loc_180113460
0x180113455  mov     bRepos, [rbp+57h+rectScreen.right]
0x180113458  cmp     [rbp+57h+rect.right], bRepos
0x18011345b  jge     short loc_18011346D
0x18011345d  sub     bRepos, [rbp+57h+rect.right]; dx
0x180113460  xor     r8d, r8d; dy
0x180113463  lea     this, [rbp+57h+rect.right]; lprc
0x180113467  call    cs:__imp_OffsetRect
0x18011346d  mov     r8d, [rbp+57h+mi.rcMonitor.left]
0x180113471  cmp     [rbp+57h+rectScreen.top], r8d
0x180113475  jle     short loc_18011347F
0x180113477  sub     r8d, [rbp+57h+rectScreen.top]
0x18011347b  xor     bRepos, bRepos
0x18011347d  jmp     short loc_18011348D
0x18011347f  mov     bRepos, [rbp+57h+rectScreen.bottom]
0x180113482  cmp     [rbp+57h+rect.bottom], bRepos
0x180113485  jge     short loc_180113497
0x180113487  sub     bRepos, [rbp+57h+rect.bottom]; dx
0x18011348a  xor     r8d, r8d; dy
0x18011348d  lea     this, [rbp+57h+rect.right]; lprc
0x180113491  call    cs:__imp_OffsetRect
0x180113497  mov     bRepos, 7F00h; lpCursorName
0x18011349c  xor     ecx, ecx; hInstance
0x18011349e  call    cs:__imp_LoadCursorW
0x1801134a4  mov     rdx, rax; hCursor
0x1801134a7  xor     r9d, r9d; hIcon
0x1801134aa  mov     ecx, 800h; nClassStyle
0x1801134af  lea     r8d, [r9+10h]; hbrBackground
0x1801134b3  call    ?AfxRegisterWndClass@@YAPEB_WIPEAUHICON__@@PEAUHBRUSH__@@0@Z; AfxRegisterWndClass(uint,HICON__ *,HBRUSH__ *,HICON__ *)
0x1801134b8  mov     rdi, rax
0x1801134bb  test    rax, rax
0x1801134be  jz      short loc_1801134C9
0x1801134c0  mov     this, rdi; String
0x1801134c3  call    cs:__imp_wcslen
0x1801134c9  mov     r8d, eax; nLength
0x1801134cc  mov     rdx, rdi; pszSrc
0x1801134cf  lea     this, ?m_strClassName@CMFCRibbonKeyTip@@1V?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@A; this
0x1801134d6  call    ?SetString@?$CSimpleStringT@_W$00@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,1>::SetString(wchar_t const *,int)
0x1801134db  mov     edi, 88h
0x1801134e0  mov     this, [rbx+0E8h]
0x1801134e7  mov     rax, [this]
0x1801134ea  mov     rax, [rax+1C8h]
0x1801134f1  call    cs:__guard_dispatch_icall_fptr
0x1801134f7  test    eax, eax
0x1801134f9  jz      short loc_180113520
0x1801134fb  call    ?GetInstance@CMFCVisualManager@@SAPEAV1@XZ; CMFCVisualManager::GetInstance(void)
0x180113500  mov     rdx, rax
0x180113503  mov     this, [rax]
0x180113506  mov     rax, [this+570h]
0x18011350d  mov     this, rdx
0x180113510  call    cs:__guard_dispatch_icall_fptr
0x180113516  mov     ecx, 80088h
0x18011351b  test    eax, eax
0x18011351d  cmovnz  edi, ecx
0x180113520  mov     rax, [rbx]
0x180113523  and     [rsp+0D0h+var_90], 0
0x180113529  and     dword ptr [rsp+0D0h+var_98], 0
0x18011352e  and     qword ptr [rsp+0D0h+var_A0], 0
0x180113534  lea     this, [rbp+57h+rect.right]
0x180113538  mov     [rsp+0D0h+var_A8], this
0x18011353d  mov     dword ptr [rsp+0D0h+var_B0], 80000000h
0x180113545  lea     r9, CmdLine
0x18011354c  mov     r8, cs:?m_strClassName@CMFCRibbonKeyTip@@1V?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@A.m_pszData; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> CMFCRibbonKeyTip::m_strClassName ...
0x180113553  mov     bRepos, edi
0x180113555  mov     this, rbx
0x180113558  mov     rax, [rax+0C0h]
0x18011355f  call    cs:__guard_dispatch_icall_fptr
0x180113565  test    eax, eax
0x180113567  jz      short loc_1801135A9
0x180113569  movups  xmm0, xmmword ptr [rbp+57h+rect.right]
0x18011356d  movdqu  xmmword ptr [rbx+0F0h], xmm0
0x180113575  bt      edi, 13h
0x180113579  jnb     short loc_18011358D
0x18011357b  mov     r9d, esi; dwFlags
0x18011357e  mov     r8b, 80h; bAlpha
0x180113581  xor     bRepos, bRepos; crKey
0x180113583  mov     this, [rbx+40h]; hwnd
0x180113587  call    cs:__imp_SetLayeredWindowAttributes
0x18011358d  mov     bRepos, 4; nCmdShow
0x180113592  mov     this, rbx; this
0x180113595  call    ?ShowWindow@CWnd@@QEAAHH@Z; CWnd::ShowWindow(int)
0x18011359a  nop
0x18011359b  lea     this, [rbp+57h+dc.m_hDC]; this
0x18011359f  call    ??1CClientDC@@UEAA@XZ; CClientDC::~CClientDC(void)
0x1801135a4  jmp     loc_180113326
0x1801135a9  lea     this, [rbp+57h+dc.m_hDC]; this
0x1801135ad  call    ??1CClientDC@@UEAA@XZ; CClientDC::~CClientDC(void)
0x1801135b2  xor     eax, eax
0x1801135b4  mov     this, [rbp+57h+var_10]
0x1801135b8  xor     this, rsp; StackCookie
0x1801135bb  call    __security_check_cookie
0x1801135c0  lea     r11, [rsp+0D0h+var_s0]
0x1801135c8  mov     rbx, [r11+18h]
0x1801135cc  mov     rsi, [r11+20h]
0x1801135d0  mov     rdi, [r11+28h]
0x1801135d4  mov     rsp, r11
0x1801135d7  pop     rbp
0x1801135d8  retn
0x1801135d9  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
```
