# CMFCToolBarButtonsListButton::SelectButton(CMFCToolBarButton *)

- ea: `0x180167850`
- end: `0x180167a36`
- name: `?SelectButton@CMFCToolBarButtonsListButton@@IEAAXPEAVCMFCToolBarButton@@@Z`
- size: `486`
- prototype: `void __fastcall(CMFCToolBarButtonsListButton *this, CMFCToolBarButton *pButton)`
- caller_count: `5`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180166ed0`
- `0x1801675c0`
- `0x180167710`
- `0x180167a40`
- `0x180168010`

## callees

- `0x180167850`
- `0x1801680e0`
- `0x180231d70`
- `0x180296d00`
- `0x18029a890`
- `0x1802b6600`
- `0x1802c4640`

## import_xrefs

- `USER32!IntersectRect` at `0x180167934`
- `USER32!IntersectRect` at `0x180167934`
- `USER32!GetClientRect` at `0x1801678a3`
- `USER32!GetClientRect` at `0x1801678a3`
- `USER32!SetRectEmpty` at `0x1801678b5`
- `USER32!SetRectEmpty` at `0x1801678b5`
- `USER32!SendMessageW` at `0x180167a09`
- `USER32!SendMessageW` at `0x180167a09`
- `USER32!InvalidateRect` at `0x18016794c`
- `USER32!InvalidateRect` at `0x1801679c3`
- `USER32!InvalidateRect` at `0x18016794c`
- `USER32!InvalidateRect` at `0x1801679c3`
- `USER32!IsRectEmpty` at `0x18016795f`
- `USER32!IsRectEmpty` at `0x18016795f`
- `USER32!GetParent` at `0x1801679d7`
- `USER32!GetParent` at `0x1801679d7`
- `USER32!InflateRect` at `0x18016791b`
- `USER32!InflateRect` at `0x18016791b`
- `USER32!OffsetRect` at `0x1801678f0`
- `USER32!OffsetRect` at `0x1801678f0`
- `USER32!UpdateWindow` at `0x1801679cd`
- `USER32!UpdateWindow` at `0x1801679cd`

## pseudocode

```c
void __fastcall CMFCToolBarButtonsListButton::SelectButton(
        CMFCToolBarButtonsListButton *this,
        CMFCToolBarButton *pButton)
{
  CMFCToolBarButton *m_pSelButton; // r14
  HWND__ *m_hWnd; // rcx
  CObList::CNode *m_pNodeHead; // rbx
  CMFCToolBarButton *data; // rsi
  int v7; // r8d
  int m_iScrollTotal; // ebx
  int v9; // ecx
  int v10; // eax
  HWND__ *v11; // rcx
  HWND Parent; // rax
  CWnd *v13; // rsi
  HWND__ *v14; // rbx
  unsigned __int16 DlgCtrlID; // ax
  CRect rectSelected; // [rsp+20h] [rbp-50h] BYREF
  CRect rect; // [rsp+30h] [rbp-40h] BYREF
  CRect rectClient; // [rsp+40h] [rbp-30h] BYREF
  CRect rectInter; // [rsp+50h] [rbp-20h] BYREF

  m_pSelButton = this->m_pSelButton;
  if ( m_pSelButton == pButton )
  {
    CMFCToolBarButtonsListButton::RedrawSelection(this);
    return;
  }
  this->m_pSelButton = pButton;
  m_hWnd = this->m_hWnd;
  rectClient = 0;
  GetClientRect(m_hWnd, &rectClient);
  rectSelected = 0;
  SetRectEmpty(&rectSelected);
  m_pNodeHead = this->m_Buttons.m_pNodeHead;
  while ( m_pNodeHead )
  {
    data = (CMFCToolBarButton *)m_pNodeHead->data;
    m_pNodeHead = m_pNodeHead->pNext;
    if ( !data )
      AfxThrowInvalidArgException();
    v7 = -this->m_iScrollOffset;
    rect = data->m_rect;
    OffsetRect(&rect, 0, v7);
    if ( data == this->m_pSelButton )
    {
      rectSelected = rect;
LABEL_8:
      InflateRect(&rect, 2, 2);
      rectInter = 0;
      if ( IntersectRect(&rectInter, &rectClient, &rect) )
        InvalidateRect(this->m_hWnd, &rectInter, 1);
    }
    else if ( data == m_pSelButton )
    {
      goto LABEL_8;
    }
  }
  if ( !IsRectEmpty(&rectSelected) && (rectSelected.top >= rectClient.bottom || rectSelected.bottom <= rectClient.top) )
  {
    m_iScrollTotal = this->m_iScrollTotal;
    v9 = rectClient.top - rectClient.bottom - this->m_iScrollOffset + rectSelected.bottom;
    v10 = v9;
    if ( v9 >= m_iScrollTotal )
      v10 = this->m_iScrollTotal;
    if ( v10 >= 0 )
    {
      if ( v9 < m_iScrollTotal )
        m_iScrollTotal = rectClient.top - rectClient.bottom - this->m_iScrollOffset + rectSelected.bottom;
    }
    else
    {
      m_iScrollTotal = 0;
    }
    CWnd::SetScrollPos(this, 1, m_iScrollTotal, 1);
    v11 = this->m_hWnd;
    this->m_iScrollOffset = m_iScrollTotal;
    InvalidateRect(v11, 0, 1);
  }
  UpdateWindow(this->m_hWnd);
  Parent = GetParent(this->m_hWnd);
  v13 = CWnd::FromHandle(Parent);
  if ( v13 )
  {
    v14 = this->m_hWnd;
    DlgCtrlID = CWnd::GetDlgCtrlID(this);
    SendMessageW(v13->m_hWnd, 0x111u, DlgCtrlID, (LPARAM)v14);
  }
}

```

## disassembly

```asm
0x180167850  mov     [rsp-18h+arg_8], rbx
0x180167855  mov     [rsp-18h+arg_10], rsi
0x18016785a  push    rbp
0x18016785b  push    rdi
0x18016785c  push    r14
0x18016785e  mov     rbp, rsp
0x180167861  sub     rsp, 70h
0x180167865  mov     rax, cs:__security_cookie
0x18016786c  xor     rax, rsp
0x18016786f  mov     [rbp+var_10], rax
0x180167873  mov     r14, [this+218h]
0x18016787a  mov     rdi, this
0x18016787d  cmp     r14, pButton
0x180167880  jnz     short loc_18016788C
0x180167882  call    ?RedrawSelection@CMFCToolBarButtonsListButton@@IEAAXXZ; CMFCToolBarButtonsListButton::RedrawSelection(void)
0x180167887  jmp     loc_180167A0F
0x18016788c  mov     [this+218h], pButton
0x180167893  xorps   xmm0, xmm0
0x180167896  mov     this, [this+40h]; hWnd
0x18016789a  lea     pButton, [rbp+rectClient]; lpRect
0x18016789e  movdqu  xmmword ptr [rbp+rectClient.left], xmm0
0x1801678a3  call    cs:__imp_GetClientRect
0x1801678a9  xorps   xmm0, xmm0
0x1801678ac  lea     this, [rbp+rectSelected]; lprc
0x1801678b0  movdqa  xmmword ptr [rbp+rectSelected.left], xmm0
0x1801678b5  call    cs:__imp_SetRectEmpty
0x1801678bb  mov     rbx, [rdi+0F0h]
0x1801678c2  jmp     loc_180167952
0x1801678c7  mov     rsi, [rbx+10h]
0x1801678cb  mov     rbx, [rbx]
0x1801678ce  test    rsi, rsi
0x1801678d1  jz      loc_180167A30
0x1801678d7  movups  xmm0, xmmword ptr [rsi+68h]
0x1801678db  mov     r8d, [rdi+220h]
0x1801678e2  lea     this, [rbp+rect]; lprc
0x1801678e6  neg     r8d; dy
0x1801678e9  xor     edx, edx; dx
0x1801678eb  movdqu  xmmword ptr [rbp+rect.left], xmm0
0x1801678f0  call    cs:__imp_OffsetRect
0x1801678f6  cmp     rsi, [rdi+218h]
0x1801678fd  jnz     short loc_18016790A
0x1801678ff  movaps  xmm0, xmmword ptr [rbp+rect.left]
0x180167903  movdqa  xmmword ptr [rbp+rectSelected.left], xmm0
0x180167908  jmp     short loc_18016790F
0x18016790a  cmp     rsi, r14
0x18016790d  jnz     short loc_180167952
0x18016790f  mov     edx, 2; dx
0x180167914  lea     this, [rbp+rect]; lprc
0x180167918  mov     r8d, edx; dy
0x18016791b  call    cs:__imp_InflateRect
0x180167921  xorps   xmm0, xmm0
0x180167924  lea     r8, [rbp+rect]; lprcSrc2
0x180167928  lea     pButton, [rbp+rectClient]; lprcSrc1
0x18016792c  lea     this, [rbp+rectInter]; lprcDst
0x180167930  movups  xmmword ptr [rbp+rectInter.left], xmm0
0x180167934  call    cs:__imp_IntersectRect
0x18016793a  test    eax, eax
0x18016793c  jz      short loc_180167952
0x18016793e  mov     this, [rdi+40h]; hWnd
0x180167942  lea     pButton, [rbp+rectInter]; lpRect
0x180167946  mov     r8d, 1; bErase
0x18016794c  call    cs:__imp_InvalidateRect
0x180167952  test    rbx, rbx
0x180167955  jnz     loc_1801678C7
0x18016795b  lea     this, [rbp+rectSelected]; lprc
0x18016795f  call    cs:__imp_IsRectEmpty
0x180167965  test    eax, eax
0x180167967  jnz     short loc_1801679C9
0x180167969  mov     edx, [rbp+rectClient.bottom]
0x18016796c  mov     eax, [rbp+rectClient.top]
0x18016796f  mov     ecx, [rbp+rectSelected.bottom]
0x180167972  cmp     [rbp+rectSelected.top], edx
0x180167975  jge     short loc_18016797B
0x180167977  cmp     ecx, eax
0x180167979  jg      short loc_1801679C9
0x18016797b  mov     ebx, [rdi+224h]
0x180167981  sub     eax, edx
0x180167983  sub     eax, [rdi+220h]
0x180167989  add     ecx, eax
0x18016798b  cmp     ecx, ebx
0x18016798d  mov     eax, ecx
0x18016798f  cmovge  eax, ebx
0x180167992  test    eax, eax
0x180167994  jns     short loc_18016799A
0x180167996  xor     ebx, ebx
0x180167998  jmp     short loc_18016799F
0x18016799a  cmp     ecx, ebx
0x18016799c  cmovl   ebx, ecx
0x18016799f  mov     r9d, 1; bRedraw
0x1801679a5  mov     r8d, ebx; nPos
0x1801679a8  mov     edx, r9d; nBar
0x1801679ab  mov     this, rdi; this
0x1801679ae  call    ?SetScrollPos@CWnd@@QEAAHHHH@Z; CWnd::SetScrollPos(int,int,int)
0x1801679b3  mov     this, [rdi+40h]; hWnd
0x1801679b7  xor     edx, edx; lpRect
0x1801679b9  mov     [rdi+220h], ebx
0x1801679bf  lea     r8d, [pButton+1]; bErase
0x1801679c3  call    cs:__imp_InvalidateRect
0x1801679c9  mov     this, [rdi+40h]; hWnd
0x1801679cd  call    cs:__imp_UpdateWindow
0x1801679d3  mov     this, [rdi+40h]; hWnd
0x1801679d7  call    cs:__imp_GetParent
0x1801679dd  mov     this, rax; hWnd
0x1801679e0  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x1801679e5  mov     rsi, rax
0x1801679e8  test    rax, rax
0x1801679eb  jz      short loc_180167A0F
0x1801679ed  mov     rbx, [rdi+40h]
0x1801679f1  mov     this, rdi; this
0x1801679f4  call    ?GetDlgCtrlID@CWnd@@QEBAHXZ; CWnd::GetDlgCtrlID(void)
0x1801679f9  mov     this, [rsi+40h]; hWnd
0x1801679fd  mov     r9, rbx; lParam
0x180167a00  movzx   r8d, ax; wParam
0x180167a04  mov     edx, 111h; Msg
0x180167a09  call    cs:__imp_SendMessageW
0x180167a0f  mov     this, [rbp+var_10]
0x180167a13  xor     this, rsp; StackCookie
0x180167a16  call    __security_check_cookie
0x180167a1b  lea     r11, [rsp+70h+var_s0]
0x180167a20  mov     rbx, [r11+28h]
0x180167a24  mov     rsi, [r11+30h]
0x180167a28  mov     rsp, r11
0x180167a2b  pop     r14
0x180167a2d  pop     rdi
0x180167a2e  pop     rbp
0x180167a2f  retn
0x180167a30  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
```
