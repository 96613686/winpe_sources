# CMFCPropertyGridToolTipCtrl::Track(CRect,ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)

- ea: `0x1800d0230`
- end: `0x1800d0599`
- name: `?Track@CMFCPropertyGridToolTipCtrl@@QEAAXVCRect@@AEBV?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@@Z`
- size: `873`
- prototype: `void __fastcall(CMFCPropertyGridToolTipCtrl *this, CRect rect, const ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *strText)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update`

## callers

- `0x1800cb800`

## callees

- `0x1800033dc`
- `0x18000e0e0`
- `0x18006cab0`
- `0x1800d0230`
- `0x180139860`
- `0x180231d70`
- `0x1802af0b0`
- `0x1802af110`
- `0x1802b0630`
- `0x1802b06e0`
- `0x1802b09a0`
- `0x1802b6310`
- `0x1802b66c0`
- `0x1802b6730`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x1800d029a`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x1800d029a`
- `api-ms-win-crt-string-l1-1-0!wcspbrk` at `0x1800d0318`
- `api-ms-win-crt-string-l1-1-0!wcspbrk` at `0x1800d0318`
- `USER32!GetMonitorInfoW` at `0x1800d0440`
- `USER32!GetMonitorInfoW` at `0x1800d0440`
- `USER32!MonitorFromPoint` at `0x1800d0433`
- `USER32!MonitorFromPoint` at `0x1800d0433`
- `USER32!SystemParametersInfoW` at `0x1800d0466`
- `USER32!SystemParametersInfoW` at `0x1800d0466`
- `USER32!InvalidateRect` at `0x1800d0530`
- `USER32!InvalidateRect` at `0x1800d0530`
- `USER32!LoadCursorW` at `0x1800d054c`
- `USER32!LoadCursorW` at `0x1800d054c`
- `USER32!SetCursor` at `0x1800d0555`
- `USER32!SetCursor` at `0x1800d0555`
- `USER32!CopyRect` at `0x1800d0452`
- `USER32!CopyRect` at `0x1800d0452`
- `USER32!EqualRect` at `0x1800d027d`
- `USER32!EqualRect` at `0x1800d027d`
- `USER32!UpdateWindow` at `0x1800d053a`
- `USER32!UpdateWindow` at `0x1800d053a`
- `GDI32!GetTextExtentPoint32W` at `0x1800d03b8`
- `GDI32!GetTextExtentPoint32W` at `0x1800d03b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CMFCPropertyGridToolTipCtrl::Track(
        CMFCPropertyGridToolTipCtrl *this,
        CRect *rect,
        const ATL::CSimpleStringT<wchar_t,0> *strText)
{
  CRect *p_m_rectLast; // rsi
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *p_m_strText; // rsi
  HFONT__ *m_hFont; // rcx
  CFont *v9; // rax
  CFont *v10; // rax
  CFont *v11; // r15
  int v12; // r14d
  wchar_t *v13; // rax
  int v14; // eax
  int v15; // esi
  int v16; // esi
  int bottom; // ecx
  int top; // edx
  HMONITOR v19; // rax
  int left; // r10d
  int right; // edx
  int v22; // esi
  int v23; // r9d
  int v24; // r8d
  HCURSOR CursorW; // rax
  CClientDC v26; // [rsp+40h] [rbp-49h] BYREF
  tagSIZE psizl; // [rsp+68h] [rbp-21h] BYREF
  int v28; // [rsp+70h] [rbp-19h]
  int m_nTextHeightHorz; // [rsp+74h] [rbp-15h]
  tagRECT rcDst; // [rsp+78h] [rbp-11h] BYREF
  tagMONITORINFO v31; // [rsp+88h] [rbp-1h] BYREF

  if ( this && this->m_hWnd )
  {
    p_m_rectLast = &this->m_rectLast;
    if ( !EqualRect(&this->m_rectLast, rect) )
      goto LABEL_6;
    if ( !strText->m_pszData )
      ATL::AtlThrowImpl(-2147467259);
    if ( wcscmp(this->m_strText.m_pszData, strText->m_pszData) )
    {
LABEL_6:
      *p_m_rectLast = *rect;
      p_m_strText = &this->m_strText;
      ATL::CSimpleStringT<wchar_t,1>::operator=(&this->m_strText, strText);
      CClientDC::CClientDC(&v26, this);
      m_hFont = this->m_hFont;
      if ( m_hFont )
      {
        v10 = (CFont *)CGdiObject::FromHandle(m_hFont);
        v9 = CDC::SelectObject(&v26, v10);
      }
      else
      {
        v9 = (CFont *)CDC::SelectStockObject(&v26, 17);
      }
      v11 = v9;
      if ( !v9 )
        AfxThrowInvalidArgException();
      v12 = rect->bottom - rect->top;
      v13 = wcspbrk(p_m_strText->m_pszData, L"\n");
      if ( !v13 || (unsigned int)(v13 - p_m_strText->m_pszData) == -1 )
      {
        GetTextExtentPoint32W(v26.m_hAttribDC, p_m_strText->m_pszData, *((_DWORD *)p_m_strText->m_pszData - 4), &psizl);
        v16 = psizl.cx + 2 * this->m_nTextMargin;
      }
      else
      {
        if ( !afxGlobalData.m_bInitialized )
        {
          AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
          afxGlobalData.m_bInitialized = 1;
        }
        psizl.cx = 0;
        psizl.cy = 0;
        v28 = 200;
        m_nTextHeightHorz = afxGlobalData.m_nTextHeightHorz;
        v14 = v26.DrawTextW(
                &v26,
                this->m_strText.m_pszData,
                *((unsigned int *)this->m_strText.m_pszData - 4),
                (tagRECT *)&psizl,
                1040u);
        v15 = 2 * this->m_nTextMargin;
        v12 = v15 + v14;
        v16 = v28 + v15 - psizl.cx;
      }
      CDC::SelectObject(&v26, v11);
      if ( (CWnd::GetExStyle(this->m_pWndParent) & 0x400000) != 0 )
        rect->left = rect->right - v16;
      else
        rect->right = v16 + rect->left;
      rect->bottom = v12 + rect->top;
      bottom = this->m_rectLast.bottom;
      top = this->m_rectLast.top;
      if ( v12 < bottom - top )
      {
        rect->top = top;
        rect->bottom = bottom;
      }
      v31.cbSize = 40;
      rcDst = 0;
      v19 = MonitorFromPoint(*(POINT *)&rect->left, 2u);
      if ( GetMonitorInfoW(v19, &v31) )
        CopyRect(&rcDst, &v31.rcWork);
      else
        SystemParametersInfoW(0x30u, 0, &rcDst, 0);
      left = rect->left;
      right = rcDst.right;
      if ( rect->right - rect->left <= rcDst.right - rcDst.left )
      {
        if ( rect->right > rcDst.right )
        {
          left = rcDst.right - v16;
          rect->left = rcDst.right - v16;
LABEL_30:
          rect->right = right;
LABEL_31:
          v22 = rect->bottom;
          v23 = rect->top;
          v24 = rcDst.bottom;
          if ( v22 - v23 <= rcDst.bottom - rcDst.top )
          {
            if ( v22 > rcDst.bottom )
            {
              v23 = rcDst.bottom - v12;
              rect->top = rcDst.bottom - v12;
LABEL_37:
              rect->bottom = v24;
              goto LABEL_38;
            }
            v24 = rect->bottom;
            if ( v23 >= rcDst.top )
            {
LABEL_38:
              CWnd::SetWindowPos(this, &CWnd::wndTop, left, v23, right - left, v24 - v23, 0x210u);
              CWnd::ShowWindow(this, 4);
              InvalidateRect(this->m_hWnd, 0, 1);
              UpdateWindow(this->m_hWnd);
              AfxGetModuleState();
              CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
              SetCursor(CursorW);
              CClientDC::~CClientDC(&v26);
              return;
            }
            v24 = v22 + v12;
          }
          v23 = rcDst.top;
          rect->top = rcDst.top;
          goto LABEL_37;
        }
        right = rect->right;
        if ( left >= rcDst.left )
          goto LABEL_31;
        right = rcDst.left + v16;
      }
      left = rcDst.left;
      rect->left = rcDst.left;
      goto LABEL_30;
    }
  }
}

```

## disassembly

```asm
0x1800d0230  test    this, this
0x1800d0233  jz      locret_1800D0587
0x1800d0239  mov     [rsp-8+arg_18], rbx
0x1800d023e  push    rbp
0x1800d023f  push    rsi
0x1800d0240  push    rdi
0x1800d0241  push    r14
0x1800d0243  push    r15
0x1800d0245  lea     rbp, [rsp+20h+var_58.cbSize+1]
0x1800d024a  sub     rsp, 0C0h
0x1800d0251  mov     rax, cs:__security_cookie
0x1800d0258  xor     rax, rsp
0x1800d025b  mov     [rbp+57h+var_30], rax
0x1800d025f  mov     r14, strText
0x1800d0262  mov     rbx, rect
0x1800d0265  mov     rdi, this
0x1800d0268  cmp     qword ptr [this+40h], 0
0x1800d026d  jz      loc_1800D0565
0x1800d0273  lea     rsi, [this+0F0h]
0x1800d027a  mov     this, rsi; lprc1
0x1800d027d  call    cs:__imp_EqualRect
0x1800d0283  test    eax, eax
0x1800d0285  jz      short loc_1800D02A9
0x1800d0287  mov     rect, [r14]; String2
0x1800d028a  test    rect, rect
0x1800d028d  jz      loc_1800D058E
0x1800d0293  mov     this, [rdi+0E8h]; String1
0x1800d029a  call    cs:__imp_wcscmp
0x1800d02a0  nop
0x1800d02a1  test    eax, eax
0x1800d02a3  jz      loc_1800D0565
0x1800d02a9  movups  xmm0, xmmword ptr [rbx]
0x1800d02ac  movdqu  xmmword ptr [rsi], xmm0
0x1800d02b0  lea     rsi, [rdi+0E8h]
0x1800d02b7  mov     rect, r14; strSrc
0x1800d02ba  mov     this, rsi; this
0x1800d02bd  call    ??4?$CSimpleStringT@_W$00@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<wchar_t,1>::operator=(ATL::CSimpleStringT<wchar_t,1> const &)
0x1800d02c2  mov     rect, rdi; pWnd
0x1800d02c5  lea     this, [rbp+57h+var_A0]; this
0x1800d02c9  call    ??0CClientDC@@QEAA@PEAVCWnd@@@Z; CClientDC::CClientDC(CWnd *)
0x1800d02ce  nop
0x1800d02cf  mov     this, [rdi+108h]; h
0x1800d02d6  test    this, this
0x1800d02d9  jnz     short loc_1800D02E9
0x1800d02db  lea     edx, [this+11h]; nIndex
0x1800d02de  lea     this, [rbp+57h+var_A0]; this
0x1800d02e2  call    ?SelectStockObject@CDC@@UEAAPEAVCGdiObject@@H@Z; CDC::SelectStockObject(int)
0x1800d02e7  jmp     short loc_1800D02FA
0x1800d02e9  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1800d02ee  mov     rect, rax; pFont
0x1800d02f1  lea     this, [rbp+57h+var_A0]; this
0x1800d02f5  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x1800d02fa  mov     r15, rax
0x1800d02fd  test    rax, rax
0x1800d0300  jz      loc_1800D0588
0x1800d0306  mov     r14d, [rbx+0Ch]
0x1800d030a  sub     r14d, [rbx+4]
0x1800d030e  lea     rect, asc_18034C4F4; "\n"
0x1800d0315  mov     this, [rsi]; String
0x1800d0318  call    cs:__imp_wcspbrk
0x1800d031e  test    rax, rax
0x1800d0321  jz      loc_1800D03A9
0x1800d0327  sub     rax, [rsi]
0x1800d032a  sar     rax, 1
0x1800d032d  cmp     eax, 0FFFFFFFFh
0x1800d0330  jz      short loc_1800D03A9
0x1800d0332  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x1800d0339  jnz     short loc_1800D0351
0x1800d033b  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x1800d0342  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1800d0347  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x1800d0351  and     [rbp+57h+psizl.cx], 0
0x1800d0355  and     [rbp+57h+psizl.cy], 0
0x1800d0359  mov     [rbp+57h+var_70], 0C8h
0x1800d0360  mov     eax, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_nTextHeightHorz; AFX_GLOBAL_DATA afxGlobalData ...
0x1800d0366  mov     [rbp+57h+var_6C], eax
0x1800d0369  mov     rax, [rbp+57h+var_A0.__vftable]
0x1800d036d  mov     rect, [rdi+0E8h]
0x1800d0374  mov     [rsp+0E0h+var_C0], 410h
0x1800d037c  lea     r9, [rbp+57h+psizl]
0x1800d0380  mov     r8d, [rect-10h]
0x1800d0384  lea     this, [rbp+57h+var_A0]
0x1800d0388  mov     rax, [rax+0E0h]
0x1800d038f  call    cs:__guard_dispatch_icall_fptr
0x1800d0395  mov     esi, [rdi+100h]
0x1800d039b  add     esi, esi
0x1800d039d  lea     r14d, [rsi+rax]
0x1800d03a1  sub     esi, [rbp+57h+psizl.cx]
0x1800d03a4  add     esi, [rbp+57h+var_70]
0x1800d03a7  jmp     short loc_1800D03CA
0x1800d03a9  mov     rect, [rsi]; lpString
0x1800d03ac  lea     r9, [rbp+57h+psizl]; psizl
0x1800d03b0  mov     r8d, [rect-10h]; c
0x1800d03b4  mov     this, [rbp+57h+var_A0.m_hAttribDC]; hdc
0x1800d03b8  call    cs:__imp_GetTextExtentPoint32W
0x1800d03be  mov     ecx, [rdi+100h]
0x1800d03c4  mov     eax, [rbp+57h+psizl.cx]
0x1800d03c7  lea     esi, [rax+this*2]
0x1800d03ca  mov     rect, r15; pFont
0x1800d03cd  lea     this, [rbp+57h+var_A0]; this
0x1800d03d1  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x1800d03d6  mov     this, [rdi+110h]; this
0x1800d03dd  call    ?GetExStyle@CWnd@@QEBAKXZ; CWnd::GetExStyle(void)
0x1800d03e2  bt      eax, 16h
0x1800d03e6  jnb     short loc_1800D03F1
0x1800d03e8  mov     eax, [rbx+8]
0x1800d03eb  sub     eax, esi
0x1800d03ed  mov     [rbx], eax
0x1800d03ef  jmp     short loc_1800D03F8
0x1800d03f1  mov     ecx, [rbx]
0x1800d03f3  add     ecx, esi
0x1800d03f5  mov     [rbx+8], ecx
0x1800d03f8  mov     ecx, [rbx+4]
0x1800d03fb  add     ecx, r14d
0x1800d03fe  mov     [rbx+0Ch], ecx
0x1800d0401  mov     ecx, [rdi+0FCh]
0x1800d0407  mov     edx, [rdi+0F4h]
0x1800d040d  mov     eax, ecx
0x1800d040f  sub     eax, edx
0x1800d0411  cmp     r14d, eax
0x1800d0414  jge     short loc_1800D041C
0x1800d0416  mov     [rbx+4], edx
0x1800d0419  mov     [rbx+0Ch], ecx
0x1800d041c  mov     [rbp+57h+var_58.cbSize], 28h ; '('
0x1800d0423  xorps   xmm0, xmm0
0x1800d0426  movdqu  xmmword ptr [rbp-11h], xmm0
0x1800d042b  mov     edx, 2; dwFlags
0x1800d0430  mov     this, [rbx]; pt
0x1800d0433  call    cs:__imp_MonitorFromPoint
0x1800d0439  mov     this, rax; hMonitor
0x1800d043c  lea     rect, [rbp+57h+var_58]; lpmi
0x1800d0440  call    cs:__imp_GetMonitorInfoW
0x1800d0446  test    eax, eax
0x1800d0448  jz      short loc_1800D045A
0x1800d044a  lea     rect, [rbp+57h+var_58.rcWork]; lprcSrc
0x1800d044e  lea     this, [rbp+57h+rcDst]; lprcDst
0x1800d0452  call    cs:__imp_CopyRect
0x1800d0458  jmp     short loc_1800D046C
0x1800d045a  xor     r9d, r9d; fWinIni
0x1800d045d  lea     strText, [rbp+57h+rcDst]; pvParam
0x1800d0461  xor     edx, edx; uiParam
0x1800d0463  lea     ecx, [rect+30h]; uiAction
0x1800d0466  call    cs:__imp_SystemParametersInfoW
0x1800d046c  mov     r10d, [rbx]
0x1800d046f  mov     ecx, [rbx+8]
0x1800d0472  sub     ecx, r10d
0x1800d0475  mov     edx, [rbp-9]
0x1800d0478  mov     eax, edx
0x1800d047a  mov     r8d, [rbp+57h+rcDst.left]
0x1800d047e  sub     eax, r8d
0x1800d0481  cmp     ecx, eax
0x1800d0483  jg      short loc_1800D04A1
0x1800d0485  cmp     [rbx+8], edx
0x1800d0488  jle     short loc_1800D0495
0x1800d048a  mov     r10d, edx
0x1800d048d  sub     r10d, esi
0x1800d0490  mov     [rbx], r10d
0x1800d0493  jmp     short loc_1800D04A7
0x1800d0495  mov     edx, [rbx+8]
0x1800d0498  cmp     r10d, r8d
0x1800d049b  jge     short loc_1800D04AA
0x1800d049d  lea     edx, [strText+rsi]
0x1800d04a1  mov     r10d, r8d
0x1800d04a4  mov     [rbx], r8d
0x1800d04a7  mov     [rbx+8], edx
0x1800d04aa  mov     esi, [rbx+0Ch]
0x1800d04ad  mov     r9d, [rbx+4]
0x1800d04b1  mov     ecx, esi
0x1800d04b3  sub     ecx, r9d
0x1800d04b6  mov     r8d, [rbp+57h+rcDst.bottom]
0x1800d04ba  mov     eax, r8d
0x1800d04bd  mov     r11d, [rbp+57h+rcDst.top]
0x1800d04c1  sub     eax, r11d
0x1800d04c4  cmp     ecx, eax
0x1800d04c6  jg      short loc_1800D04E5
0x1800d04c8  cmp     esi, r8d
0x1800d04cb  jle     short loc_1800D04D9
0x1800d04cd  mov     r9d, r8d
0x1800d04d0  sub     r9d, r14d
0x1800d04d3  mov     [rbx+4], r9d
0x1800d04d7  jmp     short loc_1800D04EC
0x1800d04d9  mov     r8d, esi
0x1800d04dc  cmp     r9d, r11d
0x1800d04df  jge     short loc_1800D04F0
0x1800d04e1  lea     r8d, [rsi+r14]
0x1800d04e5  mov     r9d, r11d; y
0x1800d04e8  mov     [rbx+4], r11d
0x1800d04ec  mov     [rbx+0Ch], r8d
0x1800d04f0  sub     r8d, r9d
0x1800d04f3  sub     edx, r10d
0x1800d04f6  mov     dword ptr [rsp+30h], 210h; nFlags
0x1800d04fe  mov     [rsp+0E0h+cy], r8d; cy
0x1800d0503  mov     [rsp+0E0h+var_C0], edx; cx
0x1800d0507  mov     r8d, r10d; x
0x1800d050a  lea     rect, ?wndTop@CWnd@@2V1@B; pWndInsertAfter
0x1800d0511  mov     this, rdi; this
0x1800d0514  call    ?SetWindowPos@CWnd@@QEAAHPEBV1@HHHHI@Z; CWnd::SetWindowPos(CWnd const *,int,int,int,int,uint)
0x1800d0519  mov     edx, 4; nCmdShow
0x1800d051e  mov     this, rdi; this
0x1800d0521  call    ?ShowWindow@CWnd@@QEAAHH@Z; CWnd::ShowWindow(int)
0x1800d0526  xor     edx, edx; lpRect
0x1800d0528  lea     r8d, [rect+1]; bErase
0x1800d052c  mov     this, [rdi+40h]; hWnd
0x1800d0530  call    cs:__imp_InvalidateRect
0x1800d0536  mov     this, [rdi+40h]; hWnd
0x1800d053a  call    cs:__imp_UpdateWindow
0x1800d0540  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x1800d0545  mov     edx, 7F00h; lpCursorName
0x1800d054a  xor     ecx, ecx; hInstance
0x1800d054c  call    cs:__imp_LoadCursorW
0x1800d0552  mov     this, rax; hCursor
0x1800d0555  call    cs:__imp_SetCursor
0x1800d055b  nop
0x1800d055c  lea     this, [rbp+57h+var_A0]; this
0x1800d0560  call    ??1CClientDC@@UEAA@XZ; CClientDC::~CClientDC(void)
0x1800d0565  mov     this, [rbp+57h+var_30]
0x1800d0569  xor     this, rsp; StackCookie
0x1800d056c  call    __security_check_cookie
0x1800d0571  mov     rbx, [rsp+0E0h+arg_18]
0x1800d0579  add     rsp, 0C0h
0x1800d0580  pop     r15
0x1800d0582  pop     r14
0x1800d0584  pop     rdi
0x1800d0585  pop     rsi
0x1800d0586  pop     rbp
0x1800d0587  retn
0x1800d0588  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
0x1800d058e  mov     ecx, 80004005h; hr
0x1800d0593  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
