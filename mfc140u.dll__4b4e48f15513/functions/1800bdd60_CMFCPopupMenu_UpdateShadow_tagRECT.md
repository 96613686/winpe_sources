# CMFCPopupMenu::UpdateShadow(tagRECT *)

- ea: `0x1800bdd60`
- end: `0x1800be17f`
- name: `?UpdateShadow@CMFCPopupMenu@@QEAAXPEAUtagRECT@@@Z`
- size: `1055`
- prototype: `void __fastcall(CMFCPopupMenu *this, tagRECT *lprectScreen)`
- caller_count: `5`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1800298e0`
- `0x1800311b0`
- `0x18005e3c0`
- `0x1800bafa0`
- `0x1800be180`

## callees

- `0x1800bdd60`
- `0x18029a470`
- `0x1802afdb0`
- `0x1802b0a60`
- `0x1802b6310`
- `0x1802b66c0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!UnionRect` at `0x1800bdf10`
- `USER32!UnionRect` at `0x1800bdf10`
- `USER32!IntersectRect` at `0x1800bde53`
- `USER32!IntersectRect` at `0x1800bde96`
- `USER32!IntersectRect` at `0x1800bde53`
- `USER32!IntersectRect` at `0x1800bde96`
- `USER32!GetClientRect` at `0x1800bdddd`
- `USER32!GetClientRect` at `0x1800bdddd`
- `USER32!SetRectEmpty` at `0x1800bde61`
- `USER32!SetRectEmpty` at `0x1800bdea4`
- `USER32!SetRectEmpty` at `0x1800bde61`
- `USER32!SetRectEmpty` at `0x1800bdea4`
- `USER32!GetWindowRect` at `0x1800bded9`
- `USER32!GetWindowRect` at `0x1800bdef7`
- `USER32!GetWindowRect` at `0x1800bdfac`
- `USER32!GetWindowRect` at `0x1800bded9`
- `USER32!GetWindowRect` at `0x1800bdef7`
- `USER32!GetWindowRect` at `0x1800bdfac`
- `USER32!InvalidateRect` at `0x1800be10d`
- `USER32!InvalidateRect` at `0x1800be13f`
- `USER32!InvalidateRect` at `0x1800be10d`
- `USER32!InvalidateRect` at `0x1800be13f`
- `USER32!CopyRect` at `0x1800bde02`
- `USER32!CopyRect` at `0x1800bde02`
- `USER32!MapWindowPoints` at `0x1800be037`
- `USER32!MapWindowPoints` at `0x1800be08d`
- `USER32!MapWindowPoints` at `0x1800be037`
- `USER32!MapWindowPoints` at `0x1800be08d`
- `USER32!IsRectEmpty` at `0x1800bdeae`
- `USER32!IsRectEmpty` at `0x1800bdebc`
- `USER32!IsRectEmpty` at `0x1800be01d`
- `USER32!IsRectEmpty` at `0x1800be061`
- `USER32!IsRectEmpty` at `0x1800be0f7`
- `USER32!IsRectEmpty` at `0x1800be117`
- `USER32!IsRectEmpty` at `0x1800bdeae`
- `USER32!IsRectEmpty` at `0x1800bdebc`
- `USER32!IsRectEmpty` at `0x1800be01d`
- `USER32!IsRectEmpty` at `0x1800be061`
- `USER32!IsRectEmpty` at `0x1800be0f7`
- `USER32!IsRectEmpty` at `0x1800be117`
- `USER32!EqualRect` at `0x1800bdf1e`
- `USER32!EqualRect` at `0x1800be073`
- `USER32!EqualRect` at `0x1800be129`
- `USER32!EqualRect` at `0x1800bdf1e`
- `USER32!EqualRect` at `0x1800be073`
- `USER32!EqualRect` at `0x1800be129`
- `USER32!UpdateWindow` at `0x1800be0ae`
- `USER32!UpdateWindow` at `0x1800be149`
- `USER32!UpdateWindow` at `0x1800be0ae`
- `USER32!UpdateWindow` at `0x1800be149`
- `USER32!RedrawWindow` at `0x1800be04e`
- `USER32!RedrawWindow` at `0x1800be0a4`
- `USER32!RedrawWindow` at `0x1800be04e`
- `USER32!RedrawWindow` at `0x1800be0a4`

## pseudocode

```c
void __fastcall CMFCPopupMenu::UpdateShadow(CMFCPopupMenu *this, tagRECT *lprectScreen)
{
  CWnd *TopLevelParent; // rax
  CWnd *v5; // rdi
  unsigned int v6; // eax
  HWND__ *m_hWnd; // rcx
  int v8; // r15d
  CRect si128; // xmm0
  int m_iShadowSize; // ecx
  HWND__ *v11; // rcx
  HWND v12; // rcx
  int v13; // r14d
  CMFCPopupMenu_vtbl *v14; // rax
  unsigned int nFlags; // esi
  __int64 v16; // r13
  int top; // r9d
  int left; // r8d
  int v19; // [rsp+20h] [rbp-89h]
  int cy; // [rsp+28h] [rbp-81h]
  CRect rectClient; // [rsp+40h] [rbp-69h] BYREF
  CRect rectUpdate1; // [rsp+50h] [rbp-59h] BYREF
  CRect rectUpdate2; // [rsp+60h] [rbp-49h] BYREF
  CRect rectMain; // [rsp+70h] [rbp-39h] BYREF
  CRect rectParent; // [rsp+80h] [rbp-29h] BYREF
  CRect rectWindow; // [rsp+90h] [rbp-19h] BYREF
  CRect rectInter; // [rsp+A0h] [rbp-9h] BYREF
  CRect rectShadowRight; // [rsp+B0h] [rbp+7h] BYREF
  CRect rectMenu; // [rsp+C0h] [rbp+17h] BYREF

  if ( this->m_iShadowSize > 0 )
  {
    TopLevelParent = CWnd::GetTopLevelParent(this);
    v5 = TopLevelParent;
    if ( TopLevelParent )
    {
      if ( TopLevelParent->m_hWnd )
      {
        v6 = CWnd::GetExStyle(this);
        m_hWnd = this->m_hWnd;
        v8 = v6 & 0x400000;
        rectClient = 0;
        GetClientRect(m_hWnd, &rectClient);
        rectUpdate1 = (CRect)_mm_load_si128((const __m128i *)&rectClient);
        rectUpdate2 = rectUpdate1;
        if ( !lprectScreen )
          goto LABEL_14;
        CopyRect(&rectMain, lprectScreen);
        CWnd::ScreenToClient(this, &rectMain);
        si128 = (CRect)_mm_load_si128((const __m128i *)&rectClient);
        m_iShadowSize = this->m_iShadowSize;
        rectShadowRight = si128;
        if ( v8 )
          rectShadowRight.right = _mm_cvtsi128_si32((__m128i)si128) + 1 + m_iShadowSize;
        else
          rectShadowRight.left = _mm_srli_si128((__m128i)si128, 8).m128i_u32[0] - m_iShadowSize - 1;
        if ( !IntersectRect(&rectUpdate1, &rectMain, &rectShadowRight) )
          SetRectEmpty(&rectUpdate1);
        rectInter = (CRect)_mm_load_si128((const __m128i *)&rectClient);
        rectInter.top = _mm_srli_si128(*(__m128i *)&rectInter, 8).m128i_i32[1] - this->m_iShadowSize - 1;
        if ( !IntersectRect(&rectUpdate2, &rectMain, &rectInter) )
          SetRectEmpty(&rectUpdate2);
        if ( !IsRectEmpty(&rectUpdate1) || !IsRectEmpty(&rectUpdate2) )
        {
LABEL_14:
          v11 = this->m_hWnd;
          rectMenu = 0;
          GetWindowRect(v11, &rectMenu);
          if ( CMFCPopupMenu::m_bForceShadow
            || (v12 = v5->m_hWnd,
                rectMain = 0,
                GetWindowRect(v12, &rectMain),
                rectInter = 0,
                UnionRect(&rectInter, &rectMenu, &rectMain),
                EqualRect(&rectInter, &rectMain)) )
          {
            v13 = this->m_iShadowSize;
            this->m_iShadowSize = 0;
            if ( this != (CMFCPopupMenu *)-6168LL && this->m_bmpShadowRight.m_hObject )
              CGdiObject::DeleteObject(&this->m_bmpShadowRight);
            if ( this != (CMFCPopupMenu *)-6184LL && this->m_bmpShadowBottom.m_hObject )
              CGdiObject::DeleteObject(&this->m_bmpShadowBottom);
            v14 = this->__vftable;
            nFlags = 1052;
            rectWindow = (CRect)_mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
            v16 = (__int64)v14->GetMenuBar(this);
            *(_DWORD *)(v16 + 4380) = 1;
            if ( v8 )
            {
              GetWindowRect(this->m_hWnd, &rectWindow);
              CWnd::SetWindowPos(
                this,
                0,
                v13 + rectWindow.left,
                rectWindow.top,
                rectClient.right - rectClient.left - v13,
                rectClient.bottom - rectClient.top - v13,
                0x41Cu);
            }
            else
            {
              nFlags = 1054;
              CWnd::SetWindowPos(
                this,
                0,
                -1,
                -1,
                rectClient.right - rectClient.left - v13,
                rectClient.bottom - rectClient.top - v13,
                0x41Eu);
            }
            rectParent = rectUpdate1;
            if ( !IsRectEmpty(&rectUpdate1) )
            {
              MapWindowPoints(this->m_hWnd, v5->m_hWnd, (LPPOINT)&rectParent, 2u);
              RedrawWindow(v5->m_hWnd, &rectParent, 0, 0x185u);
            }
            rectParent = rectUpdate2;
            if ( !IsRectEmpty(&rectUpdate2) && !EqualRect(&rectUpdate1, &rectUpdate2) )
            {
              MapWindowPoints(this->m_hWnd, v5->m_hWnd, (LPPOINT)&rectParent, 2u);
              RedrawWindow(v5->m_hWnd, &rectParent, 0, 0x185u);
            }
            UpdateWindow(v5->m_hWnd);
            cy = rectClient.bottom - rectClient.top;
            v19 = rectClient.right - rectClient.left;
            this->m_iShadowSize = v13;
            if ( v8 )
            {
              top = rectWindow.top;
              left = rectWindow.left;
            }
            else
            {
              left = -1;
              top = -1;
            }
            CWnd::SetWindowPos(this, 0, left, top, v19, cy, nFlags);
            if ( !IsRectEmpty(&rectUpdate1) )
              InvalidateRect(this->m_hWnd, &rectUpdate1, 1);
            if ( !IsRectEmpty(&rectUpdate2) && !EqualRect(&rectUpdate1, &rectUpdate2) )
              InvalidateRect(this->m_hWnd, &rectUpdate2, 1);
            UpdateWindow(this->m_hWnd);
            *(_DWORD *)(v16 + 4380) = 0;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800bdd60  mov     [rsp-8+arg_10], rbx
0x1800bdd65  mov     [rsp-8+arg_18], rsi
0x1800bdd6a  push    rbp
0x1800bdd6b  push    rdi
0x1800bdd6c  push    r13
0x1800bdd6e  push    r14
0x1800bdd70  push    r15
0x1800bdd72  lea     rbp, [rsp-37h]
0x1800bdd77  sub     rsp, 0E0h
0x1800bdd7e  mov     rax, cs:__security_cookie
0x1800bdd85  xor     rax, rsp
0x1800bdd88  mov     [rbp+57h+var_30], rax
0x1800bdd8c  cmp     dword ptr [this+1810h], 0
0x1800bdd93  mov     rsi, lprectScreen
0x1800bdd96  mov     rbx, this
0x1800bdd99  jle     loc_1800BE157
0x1800bdd9f  call    ?GetTopLevelParent@CWnd@@QEBAPEAV1@XZ; CWnd::GetTopLevelParent(void)
0x1800bdda4  mov     rdi, rax
0x1800bdda7  test    rax, rax
0x1800bddaa  jz      loc_1800BE157
0x1800bddb0  cmp     qword ptr [rax+40h], 0
0x1800bddb5  jz      loc_1800BE157
0x1800bddbb  mov     this, rbx; this
0x1800bddbe  call    ?GetExStyle@CWnd@@QEBAKXZ; CWnd::GetExStyle(void)
0x1800bddc3  mov     this, [rbx+40h]; hWnd
0x1800bddc7  lea     lprectScreen, [rbp+57h+rectClient]; lpRect
0x1800bddcb  mov     r15d, eax
0x1800bddce  xorps   xmm0, xmm0
0x1800bddd1  and     r15d, 400000h
0x1800bddd8  movdqa  xmmword ptr [rbp+57h+rectClient.left], xmm0
0x1800bdddd  call    cs:__imp_GetClientRect
0x1800bdde3  movdqa  xmm0, xmmword ptr [rbp+57h+rectClient.left]
0x1800bdde8  movdqa  xmmword ptr [rbp+57h+rectUpdate1.left], xmm0
0x1800bdded  movdqa  xmmword ptr [rbp+57h+rectUpdate2.left], xmm0
0x1800bddf2  test    rsi, rsi
0x1800bddf5  jz      loc_1800BDECA
0x1800bddfb  mov     lprectScreen, rsi; lprcSrc
0x1800bddfe  lea     this, [rbp+57h+rectMain]; lprcDst
0x1800bde02  call    cs:__imp_CopyRect
0x1800bde08  lea     lprectScreen, [rbp+57h+rectMain]; lpRect
0x1800bde0c  mov     this, rbx; this
0x1800bde0f  call    ?ScreenToClient@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ScreenToClient(tagRECT *)
0x1800bde14  movdqa  xmm0, xmmword ptr [rbp+57h+rectClient.left]
0x1800bde19  mov     ecx, [rbx+1810h]
0x1800bde1f  movdqa  xmmword ptr [rbp+57h+rectShadowRight.left], xmm0
0x1800bde24  test    r15d, r15d
0x1800bde27  jz      short loc_1800BDE36
0x1800bde29  movd    eax, xmm0
0x1800bde2d  inc     eax
0x1800bde2f  add     ecx, eax
0x1800bde31  mov     [rbp+57h+rectShadowRight.right], ecx
0x1800bde34  jmp     short loc_1800BDE47
0x1800bde36  psrldq  xmm0, 8
0x1800bde3b  movq    rax, xmm0
0x1800bde40  sub     eax, ecx
0x1800bde42  dec     eax
0x1800bde44  mov     [rbp+57h+rectShadowRight.left], eax
0x1800bde47  lea     r8, [rbp+57h+rectShadowRight]; lprcSrc2
0x1800bde4b  lea     lprectScreen, [rbp+57h+rectMain]; lprcSrc1
0x1800bde4f  lea     this, [rbp+57h+rectUpdate1]; lprcDst
0x1800bde53  call    cs:__imp_IntersectRect
0x1800bde59  test    eax, eax
0x1800bde5b  jnz     short loc_1800BDE67
0x1800bde5d  lea     this, [rbp+57h+rectUpdate1]; lprc
0x1800bde61  call    cs:__imp_SetRectEmpty
0x1800bde67  movdqa  xmm0, xmmword ptr [rbp+57h+rectClient.left]
0x1800bde6c  lea     r8, [rbp+57h+rectInter]; lprcSrc2
0x1800bde70  movdqa  xmmword ptr [rbp+57h+rectInter.left], xmm0
0x1800bde75  lea     lprectScreen, [rbp+57h+rectMain]; lprcSrc1
0x1800bde79  psrldq  xmm0, 8
0x1800bde7e  lea     this, [rbp+57h+rectUpdate2]; lprcDst
0x1800bde82  movq    rax, xmm0
0x1800bde87  shr     rax, 20h
0x1800bde8b  sub     eax, [rbx+1810h]
0x1800bde91  dec     eax
0x1800bde93  mov     [rbp+57h+rectInter.top], eax
0x1800bde96  call    cs:__imp_IntersectRect
0x1800bde9c  test    eax, eax
0x1800bde9e  jnz     short loc_1800BDEAA
0x1800bdea0  lea     this, [rbp+57h+rectUpdate2]; lprc
0x1800bdea4  call    cs:__imp_SetRectEmpty
0x1800bdeaa  lea     this, [rbp+57h+rectUpdate1]; lprc
0x1800bdeae  call    cs:__imp_IsRectEmpty
0x1800bdeb4  test    eax, eax
0x1800bdeb6  jz      short loc_1800BDECA
0x1800bdeb8  lea     this, [rbp+57h+rectUpdate2]; lprc
0x1800bdebc  call    cs:__imp_IsRectEmpty
0x1800bdec2  test    eax, eax
0x1800bdec4  jnz     loc_1800BE157
0x1800bdeca  mov     this, [rbx+40h]; hWnd
0x1800bdece  lea     lprectScreen, [rbp+57h+rectMenu]; lpRect
0x1800bded2  xorps   xmm0, xmm0
0x1800bded5  movups  xmmword ptr [rbp+57h+rectMenu.left], xmm0
0x1800bded9  call    cs:__imp_GetWindowRect
0x1800bdedf  cmp     cs:?m_bForceShadow@CMFCPopupMenu@@1HA, 0; int CMFCPopupMenu::m_bForceShadow
0x1800bdee6  jnz     short loc_1800BDF2C
0x1800bdee8  mov     this, [rdi+40h]; hWnd
0x1800bdeec  lea     lprectScreen, [rbp+57h+rectMain]; lpRect
0x1800bdef0  xorps   xmm0, xmm0
0x1800bdef3  movups  xmmword ptr [rbp+57h+rectMain.left], xmm0
0x1800bdef7  call    cs:__imp_GetWindowRect
0x1800bdefd  xorps   xmm0, xmm0
0x1800bdf00  lea     r8, [rbp+57h+rectMain]; lprcSrc2
0x1800bdf04  lea     lprectScreen, [rbp+57h+rectMenu]; lprcSrc1
0x1800bdf08  lea     this, [rbp+57h+rectInter]; lprcDst
0x1800bdf0c  movups  xmmword ptr [rbp+57h+rectInter.left], xmm0
0x1800bdf10  call    cs:__imp_UnionRect
0x1800bdf16  lea     lprectScreen, [rbp+57h+rectMain]; lprc2
0x1800bdf1a  lea     this, [rbp+57h+rectInter]; lprc1
0x1800bdf1e  call    cs:__imp_EqualRect
0x1800bdf24  test    eax, eax
0x1800bdf26  jz      loc_1800BE157
0x1800bdf2c  mov     r14d, [rbx+1810h]
0x1800bdf33  lea     this, [rbx+1818h]; this
0x1800bdf3a  and     dword ptr [rbx+1810h], 0
0x1800bdf41  test    this, this
0x1800bdf44  jz      short loc_1800BDF52
0x1800bdf46  cmp     qword ptr [this+8], 0
0x1800bdf4b  jz      short loc_1800BDF52
0x1800bdf4d  call    ?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x1800bdf52  lea     this, [rbx+1828h]; this
0x1800bdf59  test    this, this
0x1800bdf5c  jz      short loc_1800BDF6A
0x1800bdf5e  cmp     qword ptr [this+8], 0
0x1800bdf63  jz      short loc_1800BDF6A
0x1800bdf65  call    ?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x1800bdf6a  mov     rax, [rbx]
0x1800bdf6d  mov     this, rbx
0x1800bdf70  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800bdf78  mov     esi, 41Ch
0x1800bdf7d  movdqu  xmmword ptr [rbp+57h+rectWindow.left], xmm0
0x1800bdf82  mov     rax, [rax+3A0h]
0x1800bdf89  call    cs:__guard_dispatch_icall_fptr
0x1800bdf8f  or      edx, 0FFFFFFFFh
0x1800bdf92  mov     r13, rax
0x1800bdf95  mov     dword ptr [rax+111Ch], 1
0x1800bdf9f  test    r15d, r15d
0x1800bdfa2  jz      short loc_1800BDFDD
0x1800bdfa4  mov     this, [rbx+40h]; hWnd
0x1800bdfa8  lea     lprectScreen, [rbp+57h+rectWindow]; lpRect
0x1800bdfac  call    cs:__imp_GetWindowRect
0x1800bdfb2  mov     edx, [rbp+57h+rectClient.bottom]
0x1800bdfb5  sub     edx, [rbp+57h+rectClient.top]
0x1800bdfb8  mov     ecx, [rbp+57h+rectClient.right]
0x1800bdfbb  sub     edx, r14d
0x1800bdfbe  sub     ecx, [rbp+57h+rectClient.left]
0x1800bdfc1  mov     r8d, [rbp+57h+rectWindow.left]
0x1800bdfc5  sub     ecx, r14d
0x1800bdfc8  mov     r9d, [rbp+57h+rectWindow.top]
0x1800bdfcc  add     r8d, r14d
0x1800bdfcf  mov     [rsp+100h+nFlags], esi
0x1800bdfd3  mov     [rsp+100h+cy], edx
0x1800bdfd7  mov     [rsp+100h+var_E0], ecx
0x1800bdfdb  jmp     short loc_1800BE006
0x1800bdfdd  mov     ecx, [rbp+57h+rectClient.bottom]
0x1800bdfe0  mov     esi, 41Eh
0x1800bdfe5  sub     ecx, [rbp+57h+rectClient.top]
0x1800bdfe8  mov     r9d, edx; y
0x1800bdfeb  mov     eax, [rbp+57h+rectClient.right]
0x1800bdfee  sub     ecx, r14d
0x1800bdff1  sub     eax, [rbp+57h+rectClient.left]
0x1800bdff4  mov     r8d, edx; x
0x1800bdff7  mov     [rsp+100h+nFlags], esi; nFlags
0x1800bdffb  sub     eax, r14d
0x1800bdffe  mov     [rsp+100h+cy], ecx; cy
0x1800be002  mov     [rsp+100h+var_E0], eax; cx
0x1800be006  xor     edx, edx; pWndInsertAfter
0x1800be008  mov     this, rbx; this
0x1800be00b  call    ?SetWindowPos@CWnd@@QEAAHPEBV1@HHHHI@Z; CWnd::SetWindowPos(CWnd const *,int,int,int,int,uint)
0x1800be010  movaps  xmm0, xmmword ptr [rbp+57h+rectUpdate1.left]
0x1800be014  lea     this, [rbp+57h+rectUpdate1]; lprc
0x1800be018  movdqa  xmmword ptr [rbp+57h+rectParent.left], xmm0
0x1800be01d  call    cs:__imp_IsRectEmpty
0x1800be023  test    eax, eax
0x1800be025  jnz     short loc_1800BE054
0x1800be027  mov     lprectScreen, [rdi+40h]; hWndTo
0x1800be02b  lea     r9d, [rax+2]; cPoints
0x1800be02f  mov     this, [rbx+40h]; hWndFrom
0x1800be033  lea     r8, [rbp+57h+rectParent]; lpPoints
0x1800be037  call    cs:__imp_MapWindowPoints
0x1800be03d  mov     this, [rdi+40h]; hWnd
0x1800be041  lea     lprectScreen, [rbp+57h+rectParent]; lprcUpdate
0x1800be045  mov     r9d, 185h; flags
0x1800be04b  xor     r8d, r8d; hrgnUpdate
0x1800be04e  call    cs:__imp_RedrawWindow
0x1800be054  movaps  xmm0, xmmword ptr [rbp+57h+rectUpdate2.left]
0x1800be058  lea     this, [rbp+57h+rectUpdate2]; lprc
0x1800be05c  movdqa  xmmword ptr [rbp+57h+rectParent.left], xmm0
0x1800be061  call    cs:__imp_IsRectEmpty
0x1800be067  test    eax, eax
0x1800be069  jnz     short loc_1800BE0AA
0x1800be06b  lea     lprectScreen, [rbp+57h+rectUpdate2]; lprc2
0x1800be06f  lea     this, [rbp+57h+rectUpdate1]; lprc1
0x1800be073  call    cs:__imp_EqualRect
0x1800be079  test    eax, eax
0x1800be07b  jnz     short loc_1800BE0AA
0x1800be07d  mov     lprectScreen, [rdi+40h]; hWndTo
0x1800be081  lea     r9d, [rax+2]; cPoints
0x1800be085  mov     this, [rbx+40h]; hWndFrom
0x1800be089  lea     r8, [rbp+57h+rectParent]; lpPoints
0x1800be08d  call    cs:__imp_MapWindowPoints
0x1800be093  mov     this, [rdi+40h]; hWnd
0x1800be097  lea     lprectScreen, [rbp+57h+rectParent]; lprcUpdate
0x1800be09b  mov     r9d, 185h; flags
0x1800be0a1  xor     r8d, r8d; hrgnUpdate
0x1800be0a4  call    cs:__imp_RedrawWindow
0x1800be0aa  mov     this, [rdi+40h]; hWnd
0x1800be0ae  call    cs:__imp_UpdateWindow
0x1800be0b4  mov     ecx, [rbp+57h+rectClient.bottom]
0x1800be0b7  xor     edx, edx; pWndInsertAfter
0x1800be0b9  sub     ecx, [rbp+57h+rectClient.top]
0x1800be0bc  mov     eax, [rbp+57h+rectClient.right]
0x1800be0bf  sub     eax, [rbp+57h+rectClient.left]
0x1800be0c2  mov     [rsp+100h+nFlags], esi; nFlags
0x1800be0c6  mov     [rsp+100h+cy], ecx; cy
0x1800be0ca  mov     this, rbx; this
0x1800be0cd  mov     [rsp+100h+var_E0], eax; cx
0x1800be0d1  mov     [rbx+1810h], r14d
0x1800be0d8  test    r15d, r15d
0x1800be0db  jz      short loc_1800BE0E7
0x1800be0dd  mov     r9d, [rbp+57h+rectWindow.top]
0x1800be0e1  mov     r8d, [rbp+57h+rectWindow.left]
0x1800be0e5  jmp     short loc_1800BE0EE
0x1800be0e7  or      r8d, 0FFFFFFFFh; x
0x1800be0eb  mov     r9d, r8d; y
0x1800be0ee  call    ?SetWindowPos@CWnd@@QEAAHPEBV1@HHHHI@Z; CWnd::SetWindowPos(CWnd const *,int,int,int,int,uint)
0x1800be0f3  lea     this, [rbp+57h+rectUpdate1]; lprc
0x1800be0f7  call    cs:__imp_IsRectEmpty
0x1800be0fd  test    eax, eax
0x1800be0ff  jnz     short loc_1800BE113
0x1800be101  mov     this, [rbx+40h]; hWnd
0x1800be105  lea     r8d, [rax+1]; bErase
0x1800be109  lea     lprectScreen, [rbp+57h+rectUpdate1]; lpRect
0x1800be10d  call    cs:__imp_InvalidateRect
0x1800be113  lea     this, [rbp+57h+rectUpdate2]; lprc
0x1800be117  call    cs:__imp_IsRectEmpty
0x1800be11d  test    eax, eax
0x1800be11f  jnz     short loc_1800BE145
0x1800be121  lea     lprectScreen, [rbp+57h+rectUpdate2]; lprc2
0x1800be125  lea     this, [rbp+57h+rectUpdate1]; lprc1
0x1800be129  call    cs:__imp_EqualRect
0x1800be12f  test    eax, eax
0x1800be131  jnz     short loc_1800BE145
0x1800be133  mov     this, [rbx+40h]; hWnd
0x1800be137  lea     r8d, [rax+1]; bErase
0x1800be13b  lea     lprectScreen, [rbp+57h+rectUpdate2]; lpRect
0x1800be13f  call    cs:__imp_InvalidateRect
0x1800be145  mov     this, [rbx+40h]; hWnd
0x1800be149  call    cs:__imp_UpdateWindow
0x1800be14f  and     dword ptr [r13+111Ch], 0
0x1800be157  mov     this, [rbp+57h+var_30]
0x1800be15b  xor     this, rsp; StackCookie
0x1800be15e  call    __security_check_cookie
0x1800be163  lea     r11, [rsp+100h+var_20]
0x1800be16b  mov     rbx, [r11+40h]
0x1800be16f  mov     rsi, [r11+48h]
0x1800be173  mov     rsp, r11
0x1800be176  pop     r15
0x1800be178  pop     r14
0x1800be17a  pop     r13
0x1800be17c  pop     rdi
0x1800be17d  pop     rbp
0x1800be17e  retn
```
