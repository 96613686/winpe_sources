# CMFCVisualManagerOfficeXP::OnDrawMenuBorder(CDC *,CMFCPopupMenu *,CRect)

- ea: `0x1801b6790`
- end: `0x1801b6ba7`
- name: `?OnDrawMenuBorder@CMFCVisualManagerOfficeXP@@MEAAXPEAVCDC@@PEAVCMFCPopupMenu@@VCRect@@@Z`
- size: `1047`
- prototype: `void __fastcall(CMFCVisualManagerOfficeXP *this, CDC *pDC, CMFCPopupMenu *pMenu, CRect rect)`
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18019b830`
- `0x1801c2310`

## callees

- `0x1800ba970`
- `0x1801567a0`
- `0x1801b6790`
- `0x1802afdb0`
- `0x1802afe10`
- `0x1802b2690`
- `0x1802b6310`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!IntersectRect` at `0x1801b6b3e`
- `USER32!IntersectRect` at `0x1801b6b5f`
- `USER32!IntersectRect` at `0x1801b6b3e`
- `USER32!IntersectRect` at `0x1801b6b5f`
- `USER32!SetRectEmpty` at `0x1801b68f5`
- `USER32!SetRectEmpty` at `0x1801b69e1`
- `USER32!SetRectEmpty` at `0x1801b68f5`
- `USER32!SetRectEmpty` at `0x1801b69e1`
- `USER32!GetWindowRect` at `0x1801b68ad`
- `USER32!GetWindowRect` at `0x1801b68c3`
- `USER32!GetWindowRect` at `0x1801b68ad`
- `USER32!GetWindowRect` at `0x1801b68c3`
- `USER32!SetRect` at `0x1801b6951`
- `USER32!SetRect` at `0x1801b6951`
- `USER32!FillRect` at `0x1801b684d`
- `USER32!FillRect` at `0x1801b6979`
- `USER32!FillRect` at `0x1801b6b79`
- `USER32!FillRect` at `0x1801b684d`
- `USER32!FillRect` at `0x1801b6979`
- `USER32!FillRect` at `0x1801b6b79`
- `USER32!IsRectEmpty` at `0x1801b695b`
- `USER32!IsRectEmpty` at `0x1801b695b`
- `USER32!InflateRect` at `0x1801b67f9`
- `USER32!InflateRect` at `0x1801b6b2c`
- `USER32!InflateRect` at `0x1801b6b4d`
- `USER32!InflateRect` at `0x1801b67f9`
- `USER32!InflateRect` at `0x1801b6b2c`
- `USER32!InflateRect` at `0x1801b6b4d`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
void __fastcall CMFCVisualManagerOfficeXP::OnDrawMenuBorder(
        CMFCVisualManagerOfficeXP *this,
        CDC *pDC,
        CMFCPopupMenu *pMenu,
        CRect *rect)
{
  unsigned int v8; // r14d
  int bottom; // eax
  HBRUSH v10; // rbx
  HBRUSH m_hObject; // r8
  CMFCPopupMenu *ParentPopupMenu; // rax
  CMFCToolBarMenuButton *m_pParentBtn; // rax
  CMFCPopupMenu *v14; // rax
  HWND__ *m_hWnd; // rcx
  CMFCPopupMenuBar *v16; // rax
  CRect m_rect; // xmm6
  int v18; // edx
  int v19; // r9d
  HBRUSH v20; // r8
  CMFCToolBarMenuButton *v21; // r14
  CWnd *m_pWndParent; // rcx
  bool v23; // cc
  int v24; // eax
  _BYTE rectBorder_8[56]; // [rsp+38h] [rbp-49h] OVERLAPPED BYREF
  int v26; // [rsp+70h] [rbp-11h]
  int v27; // [rsp+74h] [rbp-Dh]

  v8 = CWnd::GetExStyle(pMenu) & 0x400000;
  CDC::Draw3dRect(pDC, rect, this->m_clrMenuBorder, this->m_clrMenuBorder);
  InflateRect(rect, -1, -1);
  CDC::Draw3dRect(pDC, rect, this->m_clrMenuLight, this->m_clrMenuLight);
  bottom = rect->bottom;
  v26 = 2;
  *(_DWORD *)&rectBorder_8[48] = 1;
  v10 = 0;
  *(_DWORD *)&rectBorder_8[52] = 1;
  v27 = bottom - 1;
  m_hObject = 0;
  if ( this != (CMFCVisualManagerOfficeXP *)-352LL )
    m_hObject = (HBRUSH)this->m_brBarBkgnd.m_hObject;
  FillRect(pDC->m_hDC, (const RECT *)&rectBorder_8[48], m_hObject);
  ParentPopupMenu = CMFCPopupMenu::GetParentPopupMenu(pMenu);
  if ( ParentPopupMenu )
  {
    if ( ParentPopupMenu->m_bQuickCusomize )
    {
      if ( !v8 )
      {
        m_pParentBtn = pMenu->m_pParentBtn;
        if ( m_pParentBtn )
        {
          if ( m_pParentBtn->m_bQuickCustomMode )
          {
            v14 = CMFCPopupMenu::GetParentPopupMenu(pMenu);
            *(_OWORD *)rectBorder_8 = 0;
            GetWindowRect(v14->m_hWnd, (LPRECT)rectBorder_8);
            m_hWnd = pMenu->m_hWnd;
            *(_OWORD *)&rectBorder_8[32] = 0;
            GetWindowRect(m_hWnd, (LPRECT)&rectBorder_8[32]);
            v16 = pMenu->GetMenuBar(pMenu);
            m_rect = CMFCToolBar::GetButton(v16, 0)->m_rect;
            *(_OWORD *)&rectBorder_8[16] = 0;
            SetRectEmpty((LPRECT)&rectBorder_8[16]);
            v18 = *(int *)rectBorder_8 <= *(int *)&rectBorder_8[32] ? rect->left : rect->right;
            v19 = v18 + 1;
            if ( *(int *)&rectBorder_8[4] > *(int *)&rectBorder_8[36] )
              SetRect(
                (LPRECT)&rectBorder_8[16],
                v18 - 1,
                rect->bottom
              + _mm_cvtsi128_si32(_mm_srli_si128((__m128i)m_rect, 4))
              - _mm_cvtsi128_si32(_mm_srli_si128((__m128i)m_rect, 12)),
                v19,
                rect->bottom);
            else
              SetRect(
                (LPRECT)&rectBorder_8[16],
                v18 - 1,
                rect->top,
                v19,
                _mm_cvtsi128_si32(_mm_srli_si128((__m128i)m_rect, 12)));
            if ( !IsRectEmpty((const RECT *)&rectBorder_8[16]) )
            {
              v20 = 0;
              if ( this != (CMFCVisualManagerOfficeXP *)-352LL )
                v20 = (HBRUSH)this->m_brBarBkgnd.m_hObject;
              FillRect(pDC->m_hDC, (const RECT *)&rectBorder_8[16], v20);
            }
          }
        }
      }
    }
  }
  if ( !CMFCToolBar::m_bCustomizeMode )
  {
    if ( this->m_bConnectMenuToParent )
    {
      v21 = pMenu->m_pParentBtn;
      if ( v21 )
      {
        if ( !CMFCPopupMenu::GetParentPopupMenu(pMenu) && v21->IsBorder(v21) )
        {
          *(_OWORD *)&rectBorder_8[16] = 0;
          SetRectEmpty((LPRECT)&rectBorder_8[16]);
          m_pWndParent = v21->m_pWndParent;
          *(CRect *)&rectBorder_8[32] = v21->m_rect;
          CWnd::ClientToScreen(m_pWndParent, (tagRECT *)&rectBorder_8[32]);
          CWnd::ScreenToClient(pMenu, (tagRECT *)&rectBorder_8[32]);
          if ( pMenu->m_DropDirection == DROP_DIRECTION_BOTTOM )
          {
            *(_DWORD *)&rectBorder_8[12] = rect->top;
            *(_DWORD *)&rectBorder_8[4] = *(_DWORD *)&rectBorder_8[12] - 1;
          }
          else
          {
            if ( pMenu->m_DropDirection != DROP_DIRECTION_TOP )
            {
              if ( pMenu->m_DropDirection != DROP_DIRECTION_RIGHT )
              {
                if ( pMenu->m_DropDirection == DROP_DIRECTION_LEFT )
                {
                  *(_DWORD *)rectBorder_8 = rect->right;
                  *(_DWORD *)&rectBorder_8[4] = *(_DWORD *)&rectBorder_8[36] + 1;
                  *(_DWORD *)&rectBorder_8[8] = *(_DWORD *)rectBorder_8 + 1;
                  *(_DWORD *)&rectBorder_8[12] = *(_DWORD *)&rectBorder_8[44] - 1;
                  *(_OWORD *)&rectBorder_8[16] = *(_OWORD *)rectBorder_8;
                  if ( _mm_srli_si128(*(__m128i *)rectBorder_8, 8).m128i_i32[1] - (*(_DWORD *)&rectBorder_8[36] + 1) > rect->bottom - rect->top + 2 )
                    return;
                }
                goto LABEL_34;
              }
              *(_DWORD *)&rectBorder_8[8] = rect->left;
              *(_DWORD *)rectBorder_8 = *(_DWORD *)&rectBorder_8[8] - 1;
              *(_DWORD *)&rectBorder_8[4] = *(_DWORD *)&rectBorder_8[36] + 1;
              *(_DWORD *)&rectBorder_8[12] = *(_DWORD *)&rectBorder_8[44] - 1;
              *(_OWORD *)&rectBorder_8[16] = *(_OWORD *)rectBorder_8;
              v23 = _mm_srli_si128(*(__m128i *)rectBorder_8, 8).m128i_i32[1] - (*(_DWORD *)&rectBorder_8[36] + 1) <= rect->bottom - rect->top + 2;
LABEL_33:
              if ( !v23 )
                return;
LABEL_34:
              *(CRect *)rectBorder_8 = *rect;
              InflateRect((LPRECT)rectBorder_8, 1, 1);
              IntersectRect((LPRECT)&rectBorder_8[16], (const RECT *)&rectBorder_8[16], (const RECT *)rectBorder_8);
              InflateRect((LPRECT)&rectBorder_8[32], 1, 1);
              IntersectRect((LPRECT)&rectBorder_8[16], (const RECT *)&rectBorder_8[16], (const RECT *)&rectBorder_8[32]);
              if ( this != (CMFCVisualManagerOfficeXP *)-352LL )
                v10 = (HBRUSH)this->m_brBarBkgnd.m_hObject;
              FillRect(pDC->m_hDC, (const RECT *)&rectBorder_8[16], v10);
              return;
            }
            *(_DWORD *)&rectBorder_8[4] = rect->bottom;
            *(_DWORD *)&rectBorder_8[12] = *(_DWORD *)&rectBorder_8[4] + 1;
          }
          v24 = rect->right - rect->left;
          *(_DWORD *)&rectBorder_8[8] = *(_DWORD *)&rectBorder_8[40] - 1;
          *(_DWORD *)rectBorder_8 = *(_DWORD *)&rectBorder_8[32] + 1;
          v23 = *(_DWORD *)&rectBorder_8[40] - 1 - (*(_DWORD *)&rectBorder_8[32] + 1) <= v24 + 2;
          *(_OWORD *)&rectBorder_8[16] = *(_OWORD *)rectBorder_8;
          goto LABEL_33;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1801b6790  mov     rax, rsp
0x1801b6793  push    rbp
0x1801b6794  push    rbx
0x1801b6795  push    rsi
0x1801b6796  push    rdi
0x1801b6797  push    r12
0x1801b6799  push    r13
0x1801b679b  push    r14
0x1801b679d  push    r15
0x1801b679f  lea     rbp, [rax-5Fh]
0x1801b67a3  sub     rsp, 98h
0x1801b67aa  movaps  xmmword ptr [rax-58h], xmm6
0x1801b67ae  mov     rax, cs:__security_cookie
0x1801b67b5  xor     rax, rsp
0x1801b67b8  mov     [rbp+57h+var_60], rax
0x1801b67bc  mov     r12, this
0x1801b67bf  mov     rdi, rect
0x1801b67c2  mov     this, pMenu; this
0x1801b67c5  mov     rsi, pMenu
0x1801b67c8  mov     r13, pDC
0x1801b67cb  call    ?GetExStyle@CWnd@@QEBAKXZ; CWnd::GetExStyle(void)
0x1801b67d0  mov     r8d, [r12+134h]; clrTopLeft
0x1801b67d8  mov     r14d, eax
0x1801b67db  mov     r9d, r8d; clrBottomRight
0x1801b67de  mov     pDC, rdi; lpRect
0x1801b67e1  mov     this, r13; this
0x1801b67e4  and     r14d, 400000h
0x1801b67eb  call    ?Draw3dRect@CDC@@QEAAXPEBUtagRECT@@KK@Z; CDC::Draw3dRect(tagRECT const *,ulong,ulong)
0x1801b67f0  or      edx, 0FFFFFFFFh; dx
0x1801b67f3  mov     this, rdi; lprc
0x1801b67f6  mov     r8d, edx; dy
0x1801b67f9  call    cs:__imp_InflateRect
0x1801b67ff  mov     r8d, [r12+110h]; clrTopLeft
0x1801b6807  mov     pDC, rdi; lpRect
0x1801b680a  mov     r9d, r8d; clrBottomRight
0x1801b680d  mov     this, r13; this
0x1801b6810  call    ?Draw3dRect@CDC@@QEAAXPEBUtagRECT@@KK@Z; CDC::Draw3dRect(tagRECT const *,ulong,ulong)
0x1801b6815  mov     eax, [rdi+0Ch]
0x1801b6818  lea     r15, [r12+160h]
0x1801b6820  mov     ecx, 1
0x1801b6825  mov     [rbp+57h+var_68], 2
0x1801b682c  sub     eax, ecx
0x1801b682e  mov     [rbp+57h+rectLeft.right], ecx
0x1801b6831  xor     ebx, ebx
0x1801b6833  mov     [rbp+57h+rectLeft.bottom], ecx
0x1801b6836  mov     [rbp+57h+var_64], eax
0x1801b6839  mov     r8d, ebx
0x1801b683c  test    r15, r15
0x1801b683f  jz      short loc_1801B6845
0x1801b6841  mov     pMenu, [r15+8]; hbr
0x1801b6845  mov     this, [r13+8]; hDC
0x1801b6849  lea     pDC, [rbp+57h+rectLeft.right]; lprc
0x1801b684d  call    cs:__imp_FillRect
0x1801b6853  mov     this, rsi; this
0x1801b6856  call    ?GetParentPopupMenu@CMFCPopupMenu@@QEBAPEAV1@XZ; CMFCPopupMenu::GetParentPopupMenu(void)
0x1801b685b  test    rax, rax
0x1801b685e  jz      loc_1801B697F
0x1801b6864  cmp     [rax+19A8h], ebx
0x1801b686a  jz      loc_1801B697F
0x1801b6870  test    r14d, r14d
0x1801b6873  jnz     loc_1801B697F
0x1801b6879  mov     rax, [rsi+228h]
0x1801b6880  test    rax, rax
0x1801b6883  jz      loc_1801B697F
0x1801b6889  cmp     [rax+0ECh], ebx
0x1801b688f  jz      loc_1801B697F
0x1801b6895  mov     this, rsi; this
0x1801b6898  call    ?GetParentPopupMenu@CMFCPopupMenu@@QEBAPEAV1@XZ; CMFCPopupMenu::GetParentPopupMenu(void)
0x1801b689d  xorps   xmm0, xmm0
0x1801b68a0  lea     pDC, [rbp+57h+rectBorder.right]; lpRect
0x1801b68a4  movdqu  xmmword ptr [rbp+57h+rectBorder.right], xmm0
0x1801b68a9  mov     this, [rax+40h]; hWnd
0x1801b68ad  call    cs:__imp_GetWindowRect
0x1801b68b3  mov     this, [rsi+40h]; hWnd
0x1801b68b7  lea     pDC, [rbp+57h+rectParent.right]; lpRect
0x1801b68bb  xorps   xmm0, xmm0
0x1801b68be  movdqu  xmmword ptr [rbp+57h+rectParent.right], xmm0
0x1801b68c3  call    cs:__imp_GetWindowRect
0x1801b68c9  mov     rax, [rsi]
0x1801b68cc  mov     this, rsi
0x1801b68cf  mov     rax, [rax+3A0h]
0x1801b68d6  call    cs:__guard_dispatch_icall_fptr
0x1801b68dc  mov     this, rax; this
0x1801b68df  xor     edx, edx; nIndex
0x1801b68e1  call    ?GetButton@CMFCToolBar@@QEBAPEAVCMFCToolBarButton@@H@Z; CMFCToolBar::GetButton(int)
0x1801b68e6  xorps   xmm0, xmm0
0x1801b68e9  lea     this, [rbp+57h+rectConnect.right]; lprc
0x1801b68ed  movups  xmm6, xmmword ptr [rax+68h]
0x1801b68f1  movups  xmmword ptr [rbp+57h+rectConnect.right], xmm0
0x1801b68f5  call    cs:__imp_SetRectEmpty
0x1801b68fb  mov     eax, [rbp+57h+rectParent.right]
0x1801b68fe  cmp     [rbp+57h+rectBorder.right], eax
0x1801b6901  mov     eax, [rbp+57h+rectParent.bottom]
0x1801b6904  jle     short loc_1801B6923
0x1801b6906  mov     edx, [rdi+8]
0x1801b6909  lea     r9d, [pDC+1]; xRight
0x1801b690d  cmp     [rbp+57h+rectBorder.bottom], eax
0x1801b6910  jg      short loc_1801B6927
0x1801b6912  mov     r8d, [rdi+4]
0x1801b6916  psrldq  xmm6, 0Ch
0x1801b691b  movd    dword ptr [rsp+20h], xmm6
0x1801b6921  jmp     short loc_1801B694B
0x1801b6923  mov     edx, [rdi]
0x1801b6925  jmp     short loc_1801B6909
0x1801b6927  mov     ecx, [rdi+0Ch]
0x1801b692a  movdqa  xmm0, xmm6
0x1801b692e  psrldq  xmm0, 4
0x1801b6933  psrldq  xmm6, 0Ch
0x1801b6938  movd    r8d, xmm0
0x1801b693d  movd    eax, xmm6
0x1801b6941  mov     [rsp+20h], ecx; yBottom
0x1801b6945  sub     r8d, eax
0x1801b6948  add     r8d, ecx; yTop
0x1801b694b  dec     edx; xLeft
0x1801b694d  lea     this, [rbp+57h+rectConnect.right]; lprc
0x1801b6951  call    cs:__imp_SetRect
0x1801b6957  lea     this, [rbp+57h+rectConnect.right]; lprc
0x1801b695b  call    cs:__imp_IsRectEmpty
0x1801b6961  test    eax, eax
0x1801b6963  jnz     short loc_1801B697F
0x1801b6965  mov     pMenu, rbx
0x1801b6968  test    r15, r15
0x1801b696b  jz      short loc_1801B6971
0x1801b696d  mov     pMenu, [r15+8]; hbr
0x1801b6971  mov     this, [r13+8]; hDC
0x1801b6975  lea     pDC, [rbp+57h+rectConnect.right]; lprc
0x1801b6979  call    cs:__imp_FillRect
0x1801b697f  cmp     cs:?m_bCustomizeMode@CMFCToolBar@@1HA, ebx; int CMFCToolBar::m_bCustomizeMode
0x1801b6985  jnz     loc_1801B6B7F
0x1801b698b  cmp     [r12+200h], ebx
0x1801b6993  jz      loc_1801B6B7F
0x1801b6999  mov     r14, [rsi+228h]
0x1801b69a0  test    r14, r14
0x1801b69a3  jz      loc_1801B6B7F
0x1801b69a9  mov     this, rsi; this
0x1801b69ac  call    ?GetParentPopupMenu@CMFCPopupMenu@@QEBAPEAV1@XZ; CMFCPopupMenu::GetParentPopupMenu(void)
0x1801b69b1  test    rax, rax
0x1801b69b4  jnz     loc_1801B6B7F
0x1801b69ba  mov     rax, [r14]
0x1801b69bd  mov     this, r14
0x1801b69c0  mov     rax, [rax+1D8h]
0x1801b69c7  call    cs:__guard_dispatch_icall_fptr
0x1801b69cd  test    eax, eax
0x1801b69cf  jz      loc_1801B6B7F
0x1801b69d5  xorps   xmm0, xmm0
0x1801b69d8  lea     this, [rbp+57h+rectConnect.right]; lprc
0x1801b69dc  movdqa  xmmword ptr [rbp+57h+rectConnect.right], xmm0
0x1801b69e1  call    cs:__imp_SetRectEmpty
0x1801b69e7  movups  xmm0, xmmword ptr [r14+68h]
0x1801b69ec  mov     this, [r14+80h]; this
0x1801b69f3  lea     pDC, [rbp+57h+rectParent.right]; lpRect
0x1801b69f7  movdqu  xmmword ptr [rbp+57h+rectParent.right], xmm0
0x1801b69fc  call    ?ClientToScreen@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ClientToScreen(tagRECT *)
0x1801b6a01  lea     pDC, [rbp+57h+rectParent.right]; lpRect
0x1801b6a05  mov     this, rsi; this
0x1801b6a08  call    ?ScreenToClient@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ScreenToClient(tagRECT *)
0x1801b6a0d  mov     ecx, [rsi+1650h]
0x1801b6a13  sub     ecx, 1
0x1801b6a16  jz      loc_1801B6ADF
0x1801b6a1c  sub     ecx, 1
0x1801b6a1f  jz      loc_1801B6AD1
0x1801b6a25  sub     ecx, 1
0x1801b6a28  jz      short loc_1801B6A87
0x1801b6a2a  cmp     ecx, 1
0x1801b6a2d  jnz     loc_1801B6B16
0x1801b6a33  mov     ecx, [rdi+8]
0x1801b6a36  mov     eax, [rbp+57h+rectParent.bottom]
0x1801b6a39  inc     eax
0x1801b6a3b  mov     [rbp+57h+rectBorder.right], ecx
0x1801b6a3e  mov     [rbp+57h+rectBorder.bottom], eax
0x1801b6a41  lea     eax, [this+1]
0x1801b6a44  mov     [rbp+57h+rectConnect.left], eax
0x1801b6a47  mov     eax, [rbp+57h+rectLeft.top]
0x1801b6a4a  dec     eax
0x1801b6a4c  mov     [rbp+57h+rectConnect.top], eax
0x1801b6a4f  movaps  xmm0, xmmword ptr [rbp+57h+rectBorder.right]
0x1801b6a53  movq    rax, xmm0
0x1801b6a58  movdqa  xmmword ptr [rbp+57h+rectConnect.right], xmm0
0x1801b6a5d  shr     rax, 20h
0x1801b6a61  psrldq  xmm0, 8
0x1801b6a66  movq    this, xmm0
0x1801b6a6b  shr     this, 20h
0x1801b6a6f  sub     ecx, eax
0x1801b6a71  mov     eax, [rdi+0Ch]
0x1801b6a74  sub     eax, [rdi+4]
0x1801b6a77  add     eax, 2
0x1801b6a7a  cmp     ecx, eax
0x1801b6a7c  jle     loc_1801B6B16
0x1801b6a82  jmp     loc_1801B6B7F
0x1801b6a87  mov     ecx, [rdi]
0x1801b6a89  mov     [rbp+57h+rectConnect.left], ecx
0x1801b6a8c  lea     eax, [this-1]
0x1801b6a8f  mov     [rbp+57h+rectBorder.right], eax
0x1801b6a92  mov     eax, [rbp+57h+rectParent.bottom]
0x1801b6a95  inc     eax
0x1801b6a97  mov     [rbp+57h+rectBorder.bottom], eax
0x1801b6a9a  mov     eax, [rbp+57h+rectLeft.top]
0x1801b6a9d  dec     eax
0x1801b6a9f  mov     [rbp+57h+rectConnect.top], eax
0x1801b6aa2  movaps  xmm0, xmmword ptr [rbp+57h+rectBorder.right]
0x1801b6aa6  movq    rax, xmm0
0x1801b6aab  movdqa  xmmword ptr [rbp+57h+rectConnect.right], xmm0
0x1801b6ab0  shr     rax, 20h
0x1801b6ab4  psrldq  xmm0, 8
0x1801b6ab9  movq    this, xmm0
0x1801b6abe  shr     this, 20h
0x1801b6ac2  sub     ecx, eax
0x1801b6ac4  mov     eax, [rdi+0Ch]
0x1801b6ac7  sub     eax, [rdi+4]
0x1801b6aca  add     eax, 2
0x1801b6acd  cmp     ecx, eax
0x1801b6acf  jmp     short loc_1801B6B14
0x1801b6ad1  mov     ecx, [rdi+0Ch]
0x1801b6ad4  mov     [rbp+57h+rectBorder.bottom], ecx
0x1801b6ad7  lea     eax, [this+1]
0x1801b6ada  mov     [rbp+57h+rectConnect.top], eax
0x1801b6add  jmp     short loc_1801B6AEB
0x1801b6adf  mov     ecx, [rdi+4]
0x1801b6ae2  mov     [rbp+57h+rectConnect.top], ecx
0x1801b6ae5  lea     eax, [this-1]
0x1801b6ae8  mov     [rbp+57h+rectBorder.bottom], eax
0x1801b6aeb  mov     edx, [rbp+57h+rectLeft.left]
0x1801b6aee  mov     r8d, [rbp+57h+rectParent.right]
0x1801b6af2  dec     edx
0x1801b6af4  mov     eax, [rdi+8]
0x1801b6af7  inc     r8d
0x1801b6afa  sub     eax, [rdi]
0x1801b6afc  mov     [rbp+57h+rectConnect.left], edx
0x1801b6aff  add     eax, 2
0x1801b6b02  mov     [rbp+57h+rectBorder.right], r8d
0x1801b6b06  sub     edx, r8d
0x1801b6b09  movaps  xmm0, xmmword ptr [rbp+57h+rectBorder.right]
0x1801b6b0d  cmp     edx, eax
0x1801b6b0f  movdqa  xmmword ptr [rbp+57h+rectConnect.right], xmm0
0x1801b6b14  jg      short loc_1801B6B7F
0x1801b6b16  movups  xmm0, xmmword ptr [rdi]
0x1801b6b19  mov     edi, 1
0x1801b6b1e  lea     this, [rbp+57h+rectBorder.right]; lprc
0x1801b6b22  mov     r8d, edi; dy
0x1801b6b25  mov     edx, edi; dx
0x1801b6b27  movdqu  xmmword ptr [rbp+57h+rectBorder.right], xmm0
0x1801b6b2c  call    cs:__imp_InflateRect
0x1801b6b32  lea     pMenu, [rbp+57h+rectBorder.right]; lprcSrc2
0x1801b6b36  lea     pDC, [rbp+57h+rectConnect.right]; lprcSrc1
0x1801b6b3a  lea     this, [rbp+57h+rectConnect.right]; lprcDst
0x1801b6b3e  call    cs:__imp_IntersectRect
0x1801b6b44  mov     r8d, edi; dy
0x1801b6b47  lea     this, [rbp+57h+rectParent.right]; lprc
0x1801b6b4b  mov     edx, edi; dx
0x1801b6b4d  call    cs:__imp_InflateRect
0x1801b6b53  lea     pMenu, [rbp+57h+rectParent.right]; lprcSrc2
0x1801b6b57  lea     pDC, [rbp+57h+rectConnect.right]; lprcSrc1
0x1801b6b5b  lea     this, [rbp+57h+rectConnect.right]; lprcDst
0x1801b6b5f  call    cs:__imp_IntersectRect
0x1801b6b65  test    r15, r15
0x1801b6b68  jz      short loc_1801B6B6E
0x1801b6b6a  mov     rbx, [r15+8]
0x1801b6b6e  mov     this, [r13+8]; hDC
0x1801b6b72  lea     pDC, [rbp+57h+rectConnect.right]; lprc
0x1801b6b76  mov     pMenu, rbx; hbr
0x1801b6b79  call    cs:__imp_FillRect
0x1801b6b7f  mov     this, [rbp+57h+var_60]
0x1801b6b83  xor     this, rsp; StackCookie
0x1801b6b86  call    __security_check_cookie
0x1801b6b8b  movaps  xmm6, [rsp+0D0h+var_58+8]
0x1801b6b93  add     rsp, 98h
0x1801b6b9a  pop     r15
0x1801b6b9c  pop     r14
0x1801b6b9e  pop     r13
0x1801b6ba0  pop     r12
0x1801b6ba2  pop     rdi
0x1801b6ba3  pop     rsi
0x1801b6ba4  pop     rbx
0x1801b6ba5  pop     rbp
0x1801b6ba6  retn
```
