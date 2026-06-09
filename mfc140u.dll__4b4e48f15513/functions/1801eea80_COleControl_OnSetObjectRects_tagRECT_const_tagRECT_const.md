# COleControl::OnSetObjectRects(tagRECT const *,tagRECT const *)

- ea: `0x1801eea80`
- end: `0x1801eece5`
- name: `?OnSetObjectRects@COleControl@@UEAAHPEBUtagRECT@@0@Z`
- size: `613`
- prototype: `int __fastcall(COleControl *this, const tagRECT *lprcPosRect, const tagRECT *lprcClipRect)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1801edd54`
- `0x1801eea80`
- `0x180296d00`
- `0x1802afdb0`
- `0x1802b6670`
- `0x1802c4640`

## import_xrefs

- `USER32!SetWindowRgn` at `0x1801eebbc`
- `USER32!SetWindowRgn` at `0x1801eebbc`
- `USER32!MoveWindow` at `0x1801eec2c`
- `USER32!MoveWindow` at `0x1801eec2c`
- `USER32!GetWindowRect` at `0x1801eebd1`
- `USER32!GetWindowRect` at `0x1801eec4a`
- `USER32!GetWindowRect` at `0x1801eebd1`
- `USER32!GetWindowRect` at `0x1801eec4a`
- `USER32!CopyRect` at `0x1801eeab0`
- `USER32!CopyRect` at `0x1801eeae1`
- `USER32!CopyRect` at `0x1801eeab0`
- `USER32!CopyRect` at `0x1801eeae1`
- `USER32!EqualRect` at `0x1801eebfd`
- `USER32!EqualRect` at `0x1801eec90`
- `USER32!EqualRect` at `0x1801eebfd`
- `USER32!EqualRect` at `0x1801eec90`
- `USER32!GetParent` at `0x1801eebdb`
- `USER32!GetParent` at `0x1801eec54`
- `USER32!GetParent` at `0x1801eebdb`
- `USER32!GetParent` at `0x1801eec54`
- `USER32!InflateRect` at `0x1801eeb2e`
- `USER32!InflateRect` at `0x1801eeb2e`
- `USER32!OffsetRect` at `0x1801eeb05`
- `USER32!OffsetRect` at `0x1801eeb05`
- `GDI32!CreateRectRgnIndirect` at `0x1801eeba9`
- `GDI32!CreateRectRgnIndirect` at `0x1801eeba9`

## pseudocode

```c
__int64 __fastcall COleControl::OnSetObjectRects(
        COleControl *this,
        const tagRECT *lprcPosRect,
        const tagRECT *lprcClipRect)
{
  CRect *p_m_rcPos; // rbx
  bool v6; // zf
  CRect v7; // xmm0
  CControlFrameWnd *m_pWndOpenFrame; // rcx
  int v9; // r8d
  COleControl *m_pReflect; // rbx
  HRGN v11; // rax
  HWND m_hWnd; // rcx
  HWND Parent; // rax
  CWnd *v14; // rax
  HWND__ *v15; // rcx
  HWND v16; // rax
  CWnd *v17; // rax
  CRect rectPos; // [rsp+30h] [rbp-50h] BYREF
  CRect rectClip; // [rsp+40h] [rbp-40h] BYREF
  CRect rectClipLocal; // [rsp+50h] [rbp-30h] BYREF
  CRect rectInner; // [rsp+60h] [rbp-20h] BYREF

  p_m_rcPos = &this->m_rcPos;
  CopyRect(&this->m_rcPos, lprcPosRect);
  v6 = (*((_DWORD *)this + 88) & 0x800) == 0;
  v7 = *p_m_rcPos;
  rectPos = *p_m_rcPos;
  if ( !v6 )
  {
    m_pWndOpenFrame = this->m_pWndOpenFrame;
    if ( m_pWndOpenFrame )
    {
      if ( lprcClipRect )
      {
        CopyRect((LPRECT)&m_pWndOpenFrame->m_pStdObject, lprcClipRect);
        v7 = rectPos;
      }
      rectInner = v7;
      OffsetRect(&rectInner, -v7.left, -v7.top);
      *(CRect *)(&this->m_pWndOpenFrame->m_dwRef + 1) = rectInner;
      v9 = HIDWORD(this->m_pWndOpenFrame->m_xDispatch.m_vtbl) - 1;
      InflateRect(&rectPos, v9, v9);
    }
  }
  rectClip = 0;
  _GetClippingCoordinates(&rectPos, lprcClipRect, &rectClip, &this->m_ptOffset);
  if ( (*((_DWORD *)this + 88) & 0x400000) == 0 )
  {
    m_pReflect = (COleControl *)this->m_pReflect;
    if ( m_pReflect || (m_pReflect = this) != 0 )
    {
      rectClipLocal.left = rectClip.left - rectPos.left;
      rectClipLocal.right = rectClip.right - rectPos.left;
      rectClipLocal.top = rectClip.top - rectPos.top;
      rectClipLocal.bottom = rectClip.bottom - rectPos.top;
      v11 = CreateRectRgnIndirect(&rectClipLocal);
      SetWindowRgn(m_pReflect->m_hWnd, v11, 1);
      m_hWnd = m_pReflect->m_hWnd;
      rectInner = 0;
      GetWindowRect(m_hWnd, &rectInner);
      Parent = GetParent(m_pReflect->m_hWnd);
      v14 = CWnd::FromHandle(Parent);
      CWnd::ScreenToClient(v14, &rectInner);
      if ( !EqualRect(&rectInner, &rectPos) )
        MoveWindow(
          m_pReflect->m_hWnd,
          rectPos.left,
          rectPos.top,
          rectPos.right - rectPos.left,
          rectPos.bottom - rectPos.top,
          1);
    }
    if ( m_pReflect != this )
    {
      v15 = this->m_hWnd;
      rectInner = 0;
      GetWindowRect(v15, &rectInner);
      v16 = GetParent(this->m_hWnd);
      v17 = CWnd::FromHandle(v16);
      CWnd::ScreenToClient(v17, &rectInner);
      rectClipLocal.left = 0;
      rectClipLocal.top = 0;
      rectClipLocal.right = rectPos.right - rectPos.left;
      rectClipLocal.bottom = rectPos.bottom - rectPos.top;
      if ( !EqualRect(&rectInner, &rectClipLocal) )
        CWnd::MoveWindow(this, 0, 0, rectPos.right - rectPos.left, rectPos.bottom - rectPos.top, 1);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1801eea80  mov     [rsp-18h+arg_18], rbx
0x1801eea85  push    rbp
0x1801eea86  push    rsi
0x1801eea87  push    rdi
0x1801eea88  mov     rbp, rsp
0x1801eea8b  sub     rsp, 80h
0x1801eea92  mov     rax, cs:__security_cookie
0x1801eea99  xor     rax, rsp
0x1801eea9c  mov     [rbp+var_10], rax
0x1801eeaa0  lea     rbx, [this+120h]
0x1801eeaa7  mov     rdi, this
0x1801eeaaa  mov     this, rbx; lprcDst
0x1801eeaad  mov     rsi, lprcClipRect
0x1801eeab0  call    cs:__imp_CopyRect
0x1801eeab6  test    dword ptr [rdi+160h], 800h
0x1801eeac0  movups  xmm0, xmmword ptr [rbx]
0x1801eeac3  movaps  xmmword ptr [rbp+rectPos.left], xmm0
0x1801eeac7  jz      short loc_1801EEB34
0x1801eeac9  mov     this, [rdi+118h]
0x1801eead0  test    this, this
0x1801eead3  jz      short loc_1801EEB34
0x1801eead5  test    rsi, rsi
0x1801eead8  jz      short loc_1801EEAEB
0x1801eeada  add     this, 50h ; 'P'; lprcDst
0x1801eeade  mov     lprcPosRect, rsi; lprcSrc
0x1801eeae1  call    cs:__imp_CopyRect
0x1801eeae7  movaps  xmm0, xmmword ptr [rbp+rectPos.left]
0x1801eeaeb  movq    lprcPosRect, xmm0
0x1801eeaf0  movdqa  xmmword ptr [rbp+rectInner.left], xmm0
0x1801eeaf5  mov     lprcClipRect, lprcPosRect
0x1801eeaf8  lea     this, [rbp+rectInner]; lprc
0x1801eeafc  shr     lprcClipRect, 20h
0x1801eeb00  neg     edx; dx
0x1801eeb02  neg     r8d; dy
0x1801eeb05  call    cs:__imp_OffsetRect
0x1801eeb0b  mov     rax, [rdi+118h]
0x1801eeb12  lea     this, [rbp+rectPos]; lprc
0x1801eeb16  movaps  xmm0, xmmword ptr [rbp+rectInner.left]
0x1801eeb1a  movdqu  xmmword ptr [rax+0Ch], xmm0
0x1801eeb1f  mov     rax, [rdi+118h]
0x1801eeb26  mov     edx, [rax+24h]
0x1801eeb29  dec     edx; dx
0x1801eeb2b  mov     r8d, edx; dy
0x1801eeb2e  call    cs:__imp_InflateRect
0x1801eeb34  xorps   xmm0, xmm0
0x1801eeb37  lea     r9, [rdi+140h]; pOffsetPoint
0x1801eeb3e  lea     lprcClipRect, [rbp+rectClip]; pIntersectRect
0x1801eeb42  mov     lprcPosRect, rsi; pClipRect
0x1801eeb45  lea     this, [rbp+rectPos]; pPosRect
0x1801eeb49  movdqu  xmmword ptr [rbp+rectClip.left], xmm0
0x1801eeb4e  call    ?_GetClippingCoordinates@@YAXPEBUtagRECT@@0PEAU1@PEAUtagPOINT@@@Z; _GetClippingCoordinates(tagRECT const *,tagRECT const *,tagRECT *,tagPOINT *)
0x1801eeb53  test    dword ptr [rdi+160h], 400000h
0x1801eeb5d  jnz     loc_1801EECC1
0x1801eeb63  mov     rbx, [rdi+150h]
0x1801eeb6a  test    rbx, rbx
0x1801eeb6d  jnz     short loc_1801EEB7B
0x1801eeb6f  mov     rbx, rdi
0x1801eeb72  test    rdi, rdi
0x1801eeb75  jz      loc_1801EEC32
0x1801eeb7b  mov     ecx, [rbp+rectClip.top]
0x1801eeb7e  mov     eax, [rbp+rectClip.left]
0x1801eeb81  mov     r8d, [rbp+rectClip.right]
0x1801eeb85  mov     edx, [rbp+rectClip.bottom]
0x1801eeb88  sub     r8d, eax
0x1801eeb8b  sub     eax, [rbp+rectPos.left]
0x1801eeb8e  sub     edx, ecx
0x1801eeb90  sub     ecx, [rbp+rectPos.top]
0x1801eeb93  mov     [rbp+rectClipLocal.left], eax
0x1801eeb96  add     eax, r8d
0x1801eeb99  mov     [rbp+rectClipLocal.right], eax
0x1801eeb9c  mov     [rbp+rectClipLocal.top], ecx
0x1801eeb9f  lea     eax, [lprcPosRect+this]
0x1801eeba2  lea     this, [rbp+rectClipLocal]; lprect
0x1801eeba6  mov     [rbp+rectClipLocal.bottom], eax
0x1801eeba9  call    cs:__imp_CreateRectRgnIndirect
0x1801eebaf  mov     this, [rbx+40h]; hWnd
0x1801eebb3  mov     r8d, 1; bRedraw
0x1801eebb9  mov     lprcPosRect, rax; hRgn
0x1801eebbc  call    cs:__imp_SetWindowRgn
0x1801eebc2  mov     this, [rbx+40h]; hWnd
0x1801eebc6  lea     lprcPosRect, [rbp+rectInner]; lpRect
0x1801eebca  xorps   xmm0, xmm0
0x1801eebcd  movups  xmmword ptr [rbp+rectInner.left], xmm0
0x1801eebd1  call    cs:__imp_GetWindowRect
0x1801eebd7  mov     this, [rbx+40h]; hWnd
0x1801eebdb  call    cs:__imp_GetParent
0x1801eebe1  mov     this, rax; hWnd
0x1801eebe4  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x1801eebe9  lea     lprcPosRect, [rbp+rectInner]; lpRect
0x1801eebed  mov     this, rax; this
0x1801eebf0  call    ?ScreenToClient@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ScreenToClient(tagRECT *)
0x1801eebf5  lea     lprcPosRect, [rbp+rectPos]; lprc2
0x1801eebf9  lea     this, [rbp+rectInner]; lprc1
0x1801eebfd  call    cs:__imp_EqualRect
0x1801eec03  test    eax, eax
0x1801eec05  jnz     short loc_1801EEC32
0x1801eec07  mov     eax, [rbp+rectPos.bottom]
0x1801eec0a  mov     r8d, [rbp+rectPos.top]; Y
0x1801eec0e  sub     eax, r8d
0x1801eec11  mov     r9d, [rbp+rectPos.right]
0x1801eec15  mov     lprcPosRect, qword ptr [rbp+rectPos.left]; X
0x1801eec19  mov     this, [rbx+40h]; hWnd
0x1801eec1d  sub     r9d, edx; nWidth
0x1801eec20  mov     [rsp+80h+bRepaint], 1; bRepaint
0x1801eec28  mov     [rsp+80h+nHeight], eax; nHeight
0x1801eec2c  call    cs:__imp_MoveWindow
0x1801eec32  cmp     rbx, rdi
0x1801eec35  jz      loc_1801EECC1
0x1801eec3b  mov     this, [rdi+40h]; hWnd
0x1801eec3f  lea     lprcPosRect, [rbp+rectInner]; lpRect
0x1801eec43  xorps   xmm0, xmm0
0x1801eec46  movups  xmmword ptr [rbp+rectInner.left], xmm0
0x1801eec4a  call    cs:__imp_GetWindowRect
0x1801eec50  mov     this, [rdi+40h]; hWnd
0x1801eec54  call    cs:__imp_GetParent
0x1801eec5a  mov     this, rax; hWnd
0x1801eec5d  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x1801eec62  lea     lprcPosRect, [rbp+rectInner]; lpRect
0x1801eec66  mov     this, rax; this
0x1801eec69  call    ?ScreenToClient@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ScreenToClient(tagRECT *)
0x1801eec6e  mov     ecx, [rbp+rectPos.right]
0x1801eec71  lea     lprcPosRect, [rbp+rectClipLocal]; lprc2
0x1801eec75  sub     ecx, [rbp+rectPos.left]
0x1801eec78  mov     eax, [rbp+rectPos.bottom]
0x1801eec7b  sub     eax, [rbp+rectPos.top]
0x1801eec7e  and     [rbp+rectClipLocal.left], 0
0x1801eec82  and     [rbp+rectClipLocal.top], 0
0x1801eec86  mov     [rbp+rectClipLocal.right], ecx
0x1801eec89  lea     this, [rbp+rectInner]; lprc1
0x1801eec8d  mov     [rbp+rectClipLocal.bottom], eax
0x1801eec90  call    cs:__imp_EqualRect
0x1801eec96  test    eax, eax
0x1801eec98  jnz     short loc_1801EECC1
0x1801eec9a  mov     edx, [rbp+rectPos.bottom]
0x1801eec9d  xor     r8d, r8d; y
0x1801eeca0  sub     edx, [rbp+rectPos.top]
0x1801eeca3  mov     this, rdi; this
0x1801eeca6  mov     r9d, [rbp+rectPos.right]
0x1801eecaa  sub     r9d, [rbp+rectPos.left]; nWidth
0x1801eecae  mov     [rsp+80h+bRepaint], 1; bRepaint
0x1801eecb6  mov     [rsp+80h+nHeight], edx; nHeight
0x1801eecba  xor     edx, edx; x
0x1801eecbc  call    ?MoveWindow@CWnd@@QEAAXHHHHH@Z; CWnd::MoveWindow(int,int,int,int,int)
0x1801eecc1  mov     eax, 1
0x1801eecc6  mov     this, [rbp+var_10]
0x1801eecca  xor     this, rsp; StackCookie
0x1801eeccd  call    __security_check_cookie
0x1801eecd2  mov     rbx, [rsp+80h+arg_18]
0x1801eecda  add     rsp, 80h
0x1801eece1  pop     rdi
0x1801eece2  pop     rsi
0x1801eece3  pop     rbp
0x1801eece4  retn
```
