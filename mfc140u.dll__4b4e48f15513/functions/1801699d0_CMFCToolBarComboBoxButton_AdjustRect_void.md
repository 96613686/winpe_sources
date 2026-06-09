# CMFCToolBarComboBoxButton::AdjustRect(void)

- ea: `0x1801699d0`
- end: `0x180169cb6`
- name: `?AdjustRect@CMFCToolBarComboBoxButton@@IEAAXXZ`
- size: `742`
- prototype: `void __fastcall(CMFCToolBarComboBoxButton *this)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180168fb0`
- `0x180168fe0`
- `0x180169010`

## callees

- `0x180091f60`
- `0x1801699d0`
- `0x18023f820`
- `0x180296d00`
- `0x1802afdb0`
- `0x1802b66c0`
- `0x1802c7020`

## import_xrefs

- `USER32!SetRectEmpty` at `0x180169c8d`
- `USER32!SetRectEmpty` at `0x180169c9a`
- `USER32!SetRectEmpty` at `0x180169c8d`
- `USER32!SetRectEmpty` at `0x180169c9a`
- `USER32!GetWindowRect` at `0x180169b61`
- `USER32!GetWindowRect` at `0x180169b61`
- `USER32!SendMessageW` at `0x180169b46`
- `USER32!SendMessageW` at `0x180169b46`
- `USER32!MapWindowPoints` at `0x180169ba9`
- `USER32!MapWindowPoints` at `0x180169ba9`
- `USER32!IsRectEmpty` at `0x180169a0a`
- `USER32!IsRectEmpty` at `0x180169a0a`
- `USER32!GetParent` at `0x180169a4e`
- `USER32!GetParent` at `0x180169a83`
- `USER32!GetParent` at `0x180169b81`
- `USER32!GetParent` at `0x180169a4e`
- `USER32!GetParent` at `0x180169a83`
- `USER32!GetParent` at `0x180169b81`
- `USER32!InflateRect` at `0x180169bed`
- `USER32!InflateRect` at `0x180169bed`
- `USER32!OffsetRect` at `0x180169acf`
- `USER32!OffsetRect` at `0x180169ae1`
- `USER32!OffsetRect` at `0x180169aef`
- `USER32!OffsetRect` at `0x180169acf`
- `USER32!OffsetRect` at `0x180169ae1`
- `USER32!OffsetRect` at `0x180169aef`

## pseudocode

```c
void __fastcall CMFCToolBarComboBoxButton::AdjustRect(CMFCToolBarComboBoxButton *this)
{
  CComboBox *m_pWndCombo; // rax
  CRect *p_m_rect; // r14
  HWND Parent; // rax
  CWnd *v5; // rbx
  __int64 v6; // rsi
  HWND v7; // rax
  int v8; // ebx
  __int64 v9; // kr00_8
  CRect *p_m_rectCombo; // rsi
  CComboBox *v11; // rbx
  HWND v12; // rax
  CWnd *v13; // rax
  HWND m_hWnd; // rdx
  CRect *v15; // rbx
  int v16; // r8d
  int v17; // eax
  bool v18; // zf
  CEdit *m_pWndEdit; // rcx
  CRect *p_m_rectButton; // rcx
  CSize result; // [rsp+50h] [rbp+8h] BYREF

  m_pWndCombo = this->m_pWndCombo;
  if ( !m_pWndCombo || !m_pWndCombo->m_hWnd || (p_m_rect = &this->m_rect, IsRectEmpty(&this->m_rect)) || !this->m_bHorz )
  {
    SetRectEmpty(&this->m_rectCombo);
    p_m_rectButton = &this->m_rectButton;
    goto LABEL_25;
  }
  if ( CMFCToolBarComboBoxButton::m_bCenterVert && (!this->m_bTextBelow || !*((_DWORD *)this->m_strText.m_pszData - 4)) )
  {
    Parent = GetParent(this->m_pWndCombo->m_hWnd);
    v5 = CWnd::FromHandle(Parent);
    while ( v5 )
    {
      v6 = (unsigned __int64)v5 & -(__int64)(CObject::IsKindOf(v5, &CMFCToolBar::classCMFCToolBar) != 0);
      v7 = GetParent(v5->m_hWnd);
      v5 = CWnd::FromHandle(v7);
      if ( v6 )
      {
        v8 = 0;
        v9 = (int)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 1720LL))(v6)
                 + this->m_rect.top
                 - this->m_rect.bottom);
        if ( ((int)v9 - HIDWORD(v9)) >> 1 >= 0 )
          v8 = ((int)v9 - HIDWORD(v9)) >> 1;
        OffsetRect(&this->m_rectButton, 0, v8);
        OffsetRect(&this->m_rectCombo, 0, v8);
        OffsetRect(p_m_rect, 0, v8);
        break;
      }
    }
  }
  CWnd::SetWindowPos(
    this->m_pWndCombo,
    0,
    p_m_rect->left + 1,
    this->m_rect.top,
    p_m_rect->right - p_m_rect->left - 2,
    this->m_nDropDownHeight,
    0x14u);
  SendMessageW(this->m_pWndCombo->m_hWnd, 0x142u, 0, 0xFFFF);
  p_m_rectCombo = &this->m_rectCombo;
  GetWindowRect(this->m_pWndCombo->m_hWnd, &this->m_rectCombo);
  CWnd::ScreenToClient(this->m_pWndCombo, &this->m_rectCombo);
  v11 = this->m_pWndCombo;
  v12 = GetParent(v11->m_hWnd);
  v13 = CWnd::FromHandle(v12);
  if ( v13 )
    m_hWnd = v13->m_hWnd;
  else
    m_hWnd = 0;
  MapWindowPoints(v11->m_hWnd, m_hWnd, (LPPOINT)&this->m_rectCombo, 2u);
  v15 = &this->m_rectButton;
  if ( !CMFCToolBarComboBoxButton::m_bFlat )
  {
    p_m_rectButton = &this->m_rectButton;
LABEL_25:
    SetRectEmpty(p_m_rectButton);
    return;
  }
  *v15 = *p_m_rectCombo;
  v15->left = this->m_rectButton.right - 2 * CMenuImages::Size(&result)->cx;
  InflateRect(&this->m_rectButton, -2, -2);
  v16 = p_m_rectCombo->left - 1;
  v17 = this->m_rectCombo.right + 1;
  p_m_rect->left = v16;
  v18 = this->m_bTextBelow == 0;
  this->m_rect.right = v17;
  if ( v18 || !*((_DWORD *)this->m_strText.m_pszData - 4) )
  {
    this->m_rect.top = this->m_rectCombo.top;
    this->m_rect.bottom = this->m_rectCombo.bottom;
  }
  m_pWndEdit = this->m_pWndEdit;
  if ( m_pWndEdit )
    CWnd::SetWindowPos(
      m_pWndEdit,
      0,
      v16 + 4,
      this->m_rect.top + 3,
      this->m_rect.right - this->m_rectButton.right - v16 + v15->left - 8,
      this->m_rectCombo.bottom - this->m_rectCombo.top - 6,
      0x14u);
}

```

## disassembly

```asm
0x1801699d0  mov     [rsp+arg_8], rbx
0x1801699d5  mov     [rsp+arg_10], rsi
0x1801699da  mov     [rsp+arg_18], rdi
0x1801699df  push    r14
0x1801699e1  sub     rsp, 40h
0x1801699e5  mov     rax, [this+0D0h]
0x1801699ec  mov     rdi, this
0x1801699ef  test    rax, rax
0x1801699f2  jz      loc_180169C86
0x1801699f8  cmp     qword ptr [rax+40h], 0
0x1801699fd  jz      loc_180169C86
0x180169a03  lea     r14, [this+68h]
0x180169a07  mov     this, r14; lprc
0x180169a0a  call    cs:__imp_IsRectEmpty
0x180169a10  test    eax, eax
0x180169a12  jnz     loc_180169C86
0x180169a18  cmp     [rdi+94h], eax
0x180169a1e  jz      loc_180169C86
0x180169a24  cmp     cs:?m_bCenterVert@CMFCToolBarComboBoxButton@@1HA, eax; int CMFCToolBarComboBoxButton::m_bCenterVert
0x180169a2a  jz      loc_180169AF5
0x180169a30  cmp     [rdi+1Ch], eax
0x180169a33  jz      short loc_180169A43
0x180169a35  mov     rax, [rdi+38h]
0x180169a39  cmp     dword ptr [rax-10h], 0
0x180169a3d  jnz     loc_180169AF5
0x180169a43  mov     this, [rdi+0D0h]
0x180169a4a  mov     this, [this+40h]; hWnd
0x180169a4e  call    cs:__imp_GetParent
0x180169a54  mov     this, rax; hWnd
0x180169a57  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x180169a5c  mov     rbx, rax
0x180169a5f  test    rbx, rbx
0x180169a62  jz      loc_180169AF5
0x180169a68  lea     rdx, ?classCMFCToolBar@CMFCToolBar@@2UCRuntimeClass@@A; pClass
0x180169a6f  mov     this, rbx; this
0x180169a72  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x180169a77  mov     this, [rbx+40h]; hWnd
0x180169a7b  neg     eax
0x180169a7d  sbb     rsi, rsi
0x180169a80  and     rsi, rbx
0x180169a83  call    cs:__imp_GetParent
0x180169a89  mov     this, rax; hWnd
0x180169a8c  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x180169a91  mov     rbx, rax
0x180169a94  test    rsi, rsi
0x180169a97  jz      short loc_180169A5F
0x180169a99  mov     rax, [rsi]
0x180169a9c  mov     this, rsi
0x180169a9f  mov     rax, [rax+6B8h]
0x180169aa6  call    cs:__guard_dispatch_icall_fptr
0x180169aac  mov     ecx, eax
0x180169aae  mov     ebx, 0
0x180169ab3  mov     eax, [rdi+6Ch]
0x180169ab6  sub     eax, [rdi+74h]
0x180169ab9  add     eax, ecx
0x180169abb  lea     this, [rdi+0B8h]; lprc
0x180169ac2  cdq
0x180169ac3  sub     eax, edx
0x180169ac5  sar     eax, 1
0x180169ac7  cmovns  ebx, eax
0x180169aca  xor     edx, edx; dx
0x180169acc  mov     r8d, ebx; dy
0x180169acf  call    cs:__imp_OffsetRect
0x180169ad5  lea     this, [rdi+0A8h]; lprc
0x180169adc  mov     r8d, ebx; dy
0x180169adf  xor     edx, edx; dx
0x180169ae1  call    cs:__imp_OffsetRect
0x180169ae7  mov     r8d, ebx; dy
0x180169aea  xor     edx, edx; dx
0x180169aec  mov     this, r14; lprc
0x180169aef  call    cs:__imp_OffsetRect
0x180169af5  mov     ecx, [r14+8]
0x180169af9  xor     edx, edx; pWndInsertAfter
0x180169afb  mov     r8d, [r14]
0x180169afe  sub     ecx, r8d
0x180169b01  mov     eax, [rdi+90h]
0x180169b07  sub     ecx, 2
0x180169b0a  mov     r9d, [rdi+6Ch]; y
0x180169b0e  inc     r8d; x
0x180169b11  mov     [rsp+48h+nFlags], 14h; nFlags
0x180169b19  mov     [rsp+48h+cy], eax; cy
0x180169b1d  mov     [rsp+48h+var_28], ecx; cx
0x180169b21  mov     this, [rdi+0D0h]; this
0x180169b28  call    ?SetWindowPos@CWnd@@QEAAHPEBV1@HHHHI@Z; CWnd::SetWindowPos(CWnd const *,int,int,int,int,uint)
0x180169b2d  mov     this, [rdi+0D0h]
0x180169b34  mov     r9d, 0FFFFh; lParam
0x180169b3a  xor     r8d, r8d; wParam
0x180169b3d  mov     edx, 142h; Msg
0x180169b42  mov     this, [this+40h]; hWnd
0x180169b46  call    cs:__imp_SendMessageW
0x180169b4c  mov     this, [rdi+0D0h]
0x180169b53  lea     rsi, [rdi+0A8h]
0x180169b5a  mov     rdx, rsi; lpRect
0x180169b5d  mov     this, [this+40h]; hWnd
0x180169b61  call    cs:__imp_GetWindowRect
0x180169b67  mov     this, [rdi+0D0h]; this
0x180169b6e  mov     rdx, rsi; lpRect
0x180169b71  call    ?ScreenToClient@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ScreenToClient(tagRECT *)
0x180169b76  mov     rbx, [rdi+0D0h]
0x180169b7d  mov     this, [rbx+40h]; hWnd
0x180169b81  call    cs:__imp_GetParent
0x180169b87  mov     this, rax; hWnd
0x180169b8a  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x180169b8f  test    rax, rax
0x180169b92  jnz     short loc_180169B98
0x180169b94  xor     edx, edx
0x180169b96  jmp     short loc_180169B9C
0x180169b98  mov     rdx, [rax+40h]; hWndTo
0x180169b9c  mov     this, [rbx+40h]; hWndFrom
0x180169ba0  mov     r9d, 2; cPoints
0x180169ba6  mov     r8, rsi; lpPoints
0x180169ba9  call    cs:__imp_MapWindowPoints
0x180169baf  cmp     cs:?m_bFlat@CMFCToolBarComboBoxButton@@1HA, 0; int CMFCToolBarComboBoxButton::m_bFlat
0x180169bb6  lea     rbx, [rdi+0B8h]
0x180169bbd  jz      loc_180169C81
0x180169bc3  movups  xmm0, xmmword ptr [rsi]
0x180169bc6  lea     this, [rsp+48h+result]; result
0x180169bcb  movdqu  xmmword ptr [rbx], xmm0
0x180169bcf  call    ?Size@CMenuImages@@SA?AVCSize@@XZ; CMenuImages::Size(void)
0x180169bd4  mov     edx, 0FFFFFFFEh; dx
0x180169bd9  mov     r8d, edx; dy
0x180169bdc  mov     ecx, [rax]
0x180169bde  mov     eax, [rdi+0C0h]
0x180169be4  add     ecx, ecx
0x180169be6  sub     eax, ecx
0x180169be8  mov     this, rbx; lprc
0x180169beb  mov     [rbx], eax
0x180169bed  call    cs:__imp_InflateRect
0x180169bf3  mov     r8d, [rsi]
0x180169bf6  mov     eax, [rdi+0B0h]
0x180169bfc  dec     r8d
0x180169bff  inc     eax
0x180169c01  mov     [r14], r8d
0x180169c04  cmp     dword ptr [rdi+1Ch], 0
0x180169c08  mov     [rdi+70h], eax
0x180169c0b  jz      short loc_180169C17
0x180169c0d  mov     rax, [rdi+38h]
0x180169c11  cmp     dword ptr [rax-10h], 0
0x180169c15  jnz     short loc_180169C29
0x180169c17  mov     eax, [rdi+0ACh]
0x180169c1d  mov     [rdi+6Ch], eax
0x180169c20  mov     eax, [rdi+0B4h]
0x180169c26  mov     [rdi+74h], eax
0x180169c29  mov     this, [rdi+0C8h]; this
0x180169c30  test    this, this
0x180169c33  jz      short loc_180169CA0
0x180169c35  mov     edx, [rdi+70h]
0x180169c38  sub     edx, [rbx+8]
0x180169c3b  mov     r11d, [rdi+0B4h]
0x180169c42  sub     edx, r8d
0x180169c45  mov     r10d, [rbx]
0x180169c48  add     r8d, 4; x
0x180169c4c  sub     r11d, [rdi+0ACh]
0x180169c53  add     r10d, 0FFFFFFF8h
0x180169c57  mov     r9d, [rdi+6Ch]
0x180169c5b  add     r10d, edx
0x180169c5e  sub     r11d, 6
0x180169c62  mov     [rsp+48h+nFlags], 14h; nFlags
0x180169c6a  mov     [rsp+48h+cy], r11d; cy
0x180169c6f  xor     edx, edx; pWndInsertAfter
0x180169c71  add     r9d, 3; y
0x180169c75  mov     [rsp+48h+var_28], r10d; cx
0x180169c7a  call    ?SetWindowPos@CWnd@@QEAAHPEBV1@HHHHI@Z; CWnd::SetWindowPos(CWnd const *,int,int,int,int,uint)
0x180169c7f  jmp     short loc_180169CA0
0x180169c81  mov     this, rbx
0x180169c84  jmp     short loc_180169C9A
0x180169c86  lea     this, [rdi+0A8h]; lprc
0x180169c8d  call    cs:__imp_SetRectEmpty
0x180169c93  lea     this, [rdi+0B8h]; lprc
0x180169c9a  call    cs:__imp_SetRectEmpty
0x180169ca0  mov     rbx, [rsp+48h+arg_8]
0x180169ca5  mov     rsi, [rsp+48h+arg_10]
0x180169caa  mov     rdi, [rsp+48h+arg_18]
0x180169caf  add     rsp, 40h
0x180169cb3  pop     r14
0x180169cb5  retn
```
