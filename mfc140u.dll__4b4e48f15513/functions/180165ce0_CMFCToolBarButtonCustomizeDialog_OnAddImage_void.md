# CMFCToolBarButtonCustomizeDialog::OnAddImage(void)

- ea: `0x180165ce0`
- end: `0x1801660b3`
- name: `?OnAddImage@CMFCToolBarButtonCustomizeDialog@@IEAAXXZ`
- size: `979`
- prototype: `void __fastcall(CMFCToolBarButtonCustomizeDialog *this)`
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x18001d090`
- `0x18006cab0`
- `0x180071580`
- `0x180071714`
- `0x180165ce0`
- `0x180166c30`
- `0x180167a40`
- `0x180174b20`
- `0x1801d7400`
- `0x1802128e0`
- `0x180231d70`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802b0630`
- `0x1802b06e0`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802c4640`
- `0x1802c6fb0`
- `0x1802c7020`

## import_xrefs

- `USER32!FillRect` at `0x180165e73`
- `USER32!FillRect` at `0x180165e73`
- `GDI32!DeleteDC` at `0x180165de0`
- `GDI32!DeleteDC` at `0x180165f09`
- `GDI32!DeleteDC` at `0x180165f88`
- `GDI32!DeleteDC` at `0x180165fff`
- `GDI32!DeleteDC` at `0x180166056`
- `GDI32!DeleteDC` at `0x180165de0`
- `GDI32!DeleteDC` at `0x180165f09`
- `GDI32!DeleteDC` at `0x180165f88`
- `GDI32!DeleteDC` at `0x180165fff`
- `GDI32!DeleteDC` at `0x180166056`
- `GDI32!CreateCompatibleBitmap` at `0x180165d9e`
- `GDI32!CreateCompatibleBitmap` at `0x180165d9e`
- `GDI32!SelectObject` at `0x180165e10`
- `GDI32!SelectObject` at `0x180165e8b`
- `GDI32!SelectObject` at `0x180165e10`
- `GDI32!SelectObject` at `0x180165e8b`
- `GDI32!CreateCompatibleDC` at `0x180165d79`
- `GDI32!CreateCompatibleDC` at `0x180165d79`
- `GDI32!GetObjectW` at `0x180165eb4`
- `GDI32!GetObjectW` at `0x180165eb4`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CMFCToolBarButtonCustomizeDialog::OnAddImage(CMFCToolBarButtonCustomizeDialog *this)
{
  CMFCToolBarImages *m_pImages; // rbx
  CSize m_sizeImage; // rbx
  CMFCToolBarButtonsListButton *p_m_wndButtonList; // r14
  HDC CompatibleDC; // rdx
  int top; // r15d
  HBITMAP CompatibleBitmap; // rax
  HDC v8; // rax
  HGDIOBJ v9; // rcx
  CGdiObject *v10; // rsi
  void *m_hObject; // rdx
  HGDIOBJ v12; // rax
  HDC v13; // rax
  HDC v14; // rax
  int v15; // ebx
  HDC v16; // rax
  HDC v17; // rax
  CGdiObject v18; // [rsp+30h] [rbp-2F18h] BYREF
  CDC v19; // [rsp+40h] [rbp-2F08h] BYREF
  CClientDC v20; // [rsp+60h] [rbp-2EE8h] BYREF
  _BYTE pv[18]; // [rsp+88h] [rbp-2EC0h] BYREF
  unsigned __int16 v22; // [rsp+9Ah] [rbp-2EAEh]
  RECT cy; // [rsp+A8h] [rbp-2EA0h] BYREF
  CMFCImageEditorDialog v24; // [rsp+C0h] [rbp-2E88h] BYREF

  m_pImages = this->m_pImages;
  if ( !m_pImages )
    AfxThrowInvalidArgException();
  m_sizeImage = m_pImages->m_sizeImage;
  *(CSize *)&cy.left = m_sizeImage;
  p_m_wndButtonList = &this->m_wndButtonList;
  try
  {
    CClientDC::CClientDC(&v20, &this->m_wndButtonList);
    v18.m_hObject = 0;
    v18.__vftable = (CGdiObject_vtbl *)CBitmap::`vftable';
    v19.__vftable = (CDC_vtbl *)CDC::`vftable';
    memset(&v19.m_hDC, 0, 20);
    CompatibleDC = CreateCompatibleDC(v20.m_hDC);
    CDC::Attach(&v19, CompatibleDC);
    top = cy.top;
    CompatibleBitmap = CreateCompatibleBitmap(v20.m_hDC, m_sizeImage.cx, cy.top);
    if ( !CGdiObject::Attach(&v18, CompatibleBitmap) )
    {
      AfxMessageBox(0x3E83u, 0, 0xFFFFFFFF);
      v19.__vftable = (CDC_vtbl *)CDC::`vftable';
      if ( v19.m_hDC )
      {
        v8 = CDC::Detach(&v19);
        DeleteDC(v8);
      }
LABEL_28:
      v18.__vftable = (CGdiObject_vtbl *)CBitmap::`vftable';
      CGdiObject::~CGdiObject(&v18);
      CClientDC::~CClientDC(&v20);
      return;
    }
    v9 = SelectObject(v19.m_hDC, v18.m_hObject);
    v10 = CGdiObject::FromHandle(v9);
    if ( !afxGlobalData.m_bInitialized )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      afxGlobalData.m_bInitialized = 1;
    }
    cy.left = 0;
    cy.top = 0;
    cy.right = m_sizeImage.cx;
    cy.bottom = top;
    FillRect(v19.m_hDC, &cy, (HBRUSH)afxGlobalData.brBtnFace.m_hObject);
    if ( v10 )
      m_hObject = v10->m_hObject;
    else
      m_hObject = 0;
    v12 = SelectObject(v19.m_hDC, m_hObject);
    CGdiObject::FromHandle(v12);
    GetObjectW(this->m_pImages->m_hbmImageWell, 32, pv);
    if ( g_pWndCustomize )
    {
      if ( !g_pWndCustomize->OnEditToolbarMenuImage(g_pWndCustomize, this, (CBitmap *)&v18, v22) )
      {
        v19.__vftable = (CDC_vtbl *)CDC::`vftable';
        if ( v19.m_hDC )
        {
          v13 = CDC::Detach(&v19);
          DeleteDC(v13);
        }
        goto LABEL_28;
      }
    }
    else
    {
      CMFCImageEditorDialog::CMFCImageEditorDialog(&v24, (CBitmap *)&v18, this, v22);
      if ( CDialog::DoModal(&v24) != 1 )
      {
        CMFCImageEditorDialog::~CMFCImageEditorDialog(&v24);
        v19.__vftable = (CDC_vtbl *)CDC::`vftable';
        if ( v19.m_hDC )
        {
          v14 = CDC::Detach(&v19);
          DeleteDC(v14);
        }
        goto LABEL_28;
      }
      CMFCImageEditorDialog::~CMFCImageEditorDialog(&v24);
    }
    v15 = CMFCToolBarImages::AddImage(this->m_pImages, (HBITMAP__ *)v18.m_hObject, 0);
    if ( v15 >= 0 )
    {
      CMFCToolBarButtonCustomizeDialog::RebuildImageList(this);
      CMFCToolBarButtonsListButton::SelectButton(p_m_wndButtonList, v15);
      v19.__vftable = (CDC_vtbl *)CDC::`vftable';
      if ( v19.m_hDC )
      {
        v17 = CDC::Detach(&v19);
        DeleteDC(v17);
      }
    }
    else
    {
      AfxMessageBox(0x3E83u, 0, 0xFFFFFFFF);
      v19.__vftable = (CDC_vtbl *)CDC::`vftable';
      if ( v19.m_hDC )
      {
        v16 = CDC::Detach(&v19);
        DeleteDC(v16);
      }
    }
    goto LABEL_28;
  }
  catch ( ... )
  {
    AfxMessageBox(0x3E88u, 0, 0xFFFFFFFF);
  }
}

```

## disassembly

```asm
0x180165ce0  mov     [rsp+arg_8], rbx
0x180165ce5  mov     [rsp+bitmap.__vftable], rsi
0x180165cea  mov     [rsp+bitmap.m_hObject], rdi
0x180165cef  push    r13
0x180165cf1  push    r14
0x180165cf3  push    r15
0x180165cf5  mov     eax, 2F30h
0x180165cfa  call    _alloca_probe
0x180165cff  sub     rsp, rax
0x180165d02  mov     rax, cs:__security_cookie
0x180165d09  xor     rax, rsp
0x180165d0c  mov     [rsp+2F48h+var_28], rax
0x180165d14  mov     rdi, this
0x180165d17  mov     rbx, [this+8F0h]
0x180165d1e  test    rbx, rbx
0x180165d21  jz      loc_1801660AD
0x180165d27  mov     rbx, [rbx+68h]
0x180165d2b  mov     qword ptr [rsp+2F48h+cy], rbx
0x180165d33  lea     r14, [this+5B8h]
0x180165d3a  mov     rdx, r14; pWnd
0x180165d3d  lea     this, [rsp+2F48h+var_2EE8]; this
0x180165d42  call    ??0CClientDC@@QEAA@PEAVCWnd@@@Z; CClientDC::CClientDC(CWnd *)
0x180165d47  nop
0x180165d48  and     [rsp+2F48h+var_2F18.m_hObject], 0
0x180165d4e  lea     rsi, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x180165d55  mov     [rsp+2F48h+var_2F18.__vftable], rsi
0x180165d5a  lea     r13, ??_7CDC@@6B@; const CDC::`vftable'
0x180165d61  mov     [rsp+2F48h+var_2F08.__vftable], r13
0x180165d66  xorps   xmm0, xmm0
0x180165d69  movdqu  xmmword ptr [rsp+2F48h+var_2F08.m_hDC], xmm0
0x180165d6f  and     [rsp+2F48h+var_2F08.m_bPrinting], 0
0x180165d74  mov     this, [rsp+2F48h+var_2EE8.m_hDC]; hdc
0x180165d79  call    cs:__imp_CreateCompatibleDC
0x180165d7f  mov     rdx, rax; hDC
0x180165d82  lea     this, [rsp+2F48h+var_2F08]; this
0x180165d87  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180165d8c  mov     r15d, [rsp+2F48h+cy+4]
0x180165d94  mov     r8d, r15d; cy
0x180165d97  mov     edx, ebx; cx
0x180165d99  mov     this, [rsp+2F48h+var_2EE8.m_hDC]; hdc
0x180165d9e  call    cs:__imp_CreateCompatibleBitmap
0x180165da4  mov     rdx, rax; hObject
0x180165da7  lea     this, [rsp+2F48h+var_2F18]; this
0x180165dac  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x180165db1  test    eax, eax
0x180165db3  jnz     short loc_180165E06
0x180165db5  or      r8d, 0FFFFFFFFh; nIDHelp
0x180165db9  xor     edx, edx; nType
0x180165dbb  mov     ecx, 3E83h; nIDPrompt
0x180165dc0  call    ?AfxMessageBox@@YAHIII@Z; AfxMessageBox(uint,uint,uint)
0x180165dc5  nop
0x180165dc6  mov     [rsp+2F48h+var_2F08.__vftable], r13
0x180165dcb  cmp     [rsp+2F48h+var_2F08.m_hDC], 0
0x180165dd1  jz      short loc_180165DE7
0x180165dd3  lea     this, [rsp+2F48h+var_2F08]; this
0x180165dd8  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180165ddd  mov     this, rax; hdc
0x180165de0  call    cs:__imp_DeleteDC
0x180165de6  nop
0x180165de7  mov     [rsp+2F48h+var_2F18.__vftable], rsi
0x180165dec  lea     this, [rsp+2F48h+var_2F18]; this
0x180165df1  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180165df6  nop
0x180165df7  lea     this, [rsp+2F48h+var_2EE8]; this
0x180165dfc  call    ??1CClientDC@@UEAA@XZ; CClientDC::~CClientDC(void)
0x180165e01  jmp     $LN21_27
0x180165e06  mov     rdx, [rsp+2F48h+var_2F18.m_hObject]; h
0x180165e0b  mov     this, [rsp+2F48h+var_2F08.m_hDC]; hdc
0x180165e10  call    cs:__imp_SelectObject
0x180165e16  mov     this, rax; h
0x180165e19  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x180165e1e  mov     rsi, rax
0x180165e21  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x180165e28  jnz     short loc_180165E40
0x180165e2a  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180165e31  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x180165e36  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x180165e40  and     [rsp+2F48h+cy], 0
0x180165e48  and     [rsp+2F48h+cy+4], 0
0x180165e50  mov     [rsp+2F48h+var_2E98], ebx
0x180165e57  mov     [rsp+2F48h+var_2E94], r15d
0x180165e5f  mov     r8, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.brBtnFace.m_hObject; hbr
0x180165e66  lea     rdx, [rsp+2F48h+cy]; lprc
0x180165e6e  mov     this, [rsp+2F48h+var_2F08.m_hDC]; hDC
0x180165e73  call    cs:__imp_FillRect
0x180165e79  test    rsi, rsi
0x180165e7c  jnz     short loc_180165E82
0x180165e7e  xor     edx, edx
0x180165e80  jmp     short loc_180165E86
0x180165e82  mov     rdx, [rsi+8]; h
0x180165e86  mov     this, [rsp+2F48h+var_2F08.m_hDC]; hdc
0x180165e8b  call    cs:__imp_SelectObject
0x180165e91  mov     this, rax; h
0x180165e94  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x180165e99  mov     this, [rdi+8F0h]
0x180165ea0  lea     r8, [rsp+2F48h+pv]; pv
0x180165ea8  mov     edx, 20h ; ' '; c
0x180165ead  mov     this, [this+0A0h]; h
0x180165eb4  call    cs:__imp_GetObjectW
0x180165eba  mov     this, cs:?g_pWndCustomize@@3PEAVCMFCToolBarsCustomizeDialog@@EA; CMFCToolBarsCustomizeDialog * g_pWndCustomize
0x180165ec1  movzx   r9d, [rsp+2F48h+var_2EAE]; nBitsPixel
0x180165eca  test    this, this
0x180165ecd  jz      short loc_180165F36
0x180165ecf  mov     rax, [this]
0x180165ed2  lea     r8, [rsp+2F48h+var_2F18]
0x180165ed7  mov     rdx, rdi
0x180165eda  mov     rax, [rax+348h]
0x180165ee1  call    cs:__guard_dispatch_icall_fptr
0x180165ee7  test    eax, eax
0x180165ee9  jnz     loc_180165FBA
0x180165eef  mov     [rsp+2F48h+var_2F08.__vftable], r13
0x180165ef4  cmp     [rsp+2F48h+var_2F08.m_hDC], 0
0x180165efa  jz      short loc_180165F10
0x180165efc  lea     this, [rsp+2F48h+var_2F08]; this
0x180165f01  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180165f06  mov     this, rax; hdc
0x180165f09  call    cs:__imp_DeleteDC
0x180165f0f  nop
0x180165f10  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x180165f17  mov     [rsp+2F48h+var_2F18.__vftable], rax
0x180165f1c  lea     this, [rsp+2F48h+var_2F18]; this
0x180165f21  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180165f26  nop
0x180165f27  lea     this, [rsp+2F48h+var_2EE8]; this
0x180165f2c  call    ??1CClientDC@@UEAA@XZ; CClientDC::~CClientDC(void)
0x180165f31  jmp     $LN21_27
0x180165f36  mov     r8, rdi; pParent
0x180165f39  lea     rdx, [rsp+2F48h+var_2F18]; pBitmap
0x180165f3e  lea     this, [rsp+2F48h+var_2E88]; this
0x180165f46  call    ??0CMFCImageEditorDialog@@QEAA@PEAVCBitmap@@PEAVCWnd@@H@Z; CMFCImageEditorDialog::CMFCImageEditorDialog(CBitmap *,CWnd *,int)
0x180165f4b  nop
0x180165f4c  lea     this, [rsp+2F48h+var_2E88]; this
0x180165f54  call    ?DoModal@CDialog@@UEAA_JXZ; CDialog::DoModal(void)
0x180165f59  nop
0x180165f5a  lea     this, [rsp+2F48h+var_2E88]; this
0x180165f62  cmp     rax, 1
0x180165f66  jz      short loc_180165FB5
0x180165f68  call    ??1CMFCImageEditorDialog@@UEAA@XZ; CMFCImageEditorDialog::~CMFCImageEditorDialog(void)
0x180165f6d  nop
0x180165f6e  mov     [rsp+2F48h+var_2F08.__vftable], r13
0x180165f73  cmp     [rsp+2F48h+var_2F08.m_hDC], 0
0x180165f79  jz      short loc_180165F8F
0x180165f7b  lea     this, [rsp+2F48h+var_2F08]; this
0x180165f80  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180165f85  mov     this, rax; hdc
0x180165f88  call    cs:__imp_DeleteDC
0x180165f8e  nop
0x180165f8f  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x180165f96  mov     [rsp+2F48h+var_2F18.__vftable], rax
0x180165f9b  lea     this, [rsp+2F48h+var_2F18]; this
0x180165fa0  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180165fa5  nop
0x180165fa6  lea     this, [rsp+2F48h+var_2EE8]; this
0x180165fab  call    ??1CClientDC@@UEAA@XZ; CClientDC::~CClientDC(void)
0x180165fb0  jmp     $LN21_27
0x180165fb5  call    ??1CMFCImageEditorDialog@@UEAA@XZ; CMFCImageEditorDialog::~CMFCImageEditorDialog(void)
0x180165fba  xor     r8d, r8d; bSetBitPerPixel
0x180165fbd  mov     rdx, [rsp+2F48h+var_2F18.m_hObject]; hbmp
0x180165fc2  mov     this, [rdi+8F0h]; this
0x180165fc9  call    ?AddImage@CMFCToolBarImages@@QEAAHPEAUHBITMAP__@@H@Z; CMFCToolBarImages::AddImage(HBITMAP__ *,int)
0x180165fce  mov     ebx, eax
0x180165fd0  test    eax, eax
0x180165fd2  jns     short loc_180166029
0x180165fd4  or      r8d, 0FFFFFFFFh; nIDHelp
0x180165fd8  xor     edx, edx; nType
0x180165fda  mov     ecx, 3E83h; nIDPrompt
0x180165fdf  call    ?AfxMessageBox@@YAHIII@Z; AfxMessageBox(uint,uint,uint)
0x180165fe4  nop
0x180165fe5  mov     [rsp+2F48h+var_2F08.__vftable], r13
0x180165fea  cmp     [rsp+2F48h+var_2F08.m_hDC], 0
0x180165ff0  jz      short loc_180166006
0x180165ff2  lea     this, [rsp+2F48h+var_2F08]; this
0x180165ff7  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180165ffc  mov     this, rax; hdc
0x180165fff  call    cs:__imp_DeleteDC
0x180166005  nop
0x180166006  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18016600d  mov     [rsp+2F48h+var_2F18.__vftable], rax
0x180166012  lea     this, [rsp+2F48h+var_2F18]; this
0x180166017  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18016601c  nop
0x18016601d  lea     this, [rsp+2F48h+var_2EE8]; this
0x180166022  call    ??1CClientDC@@UEAA@XZ; CClientDC::~CClientDC(void)
0x180166027  jmp     short $LN21_27
0x180166029  mov     this, rdi; this
0x18016602c  call    ?RebuildImageList@CMFCToolBarButtonCustomizeDialog@@IEAAXXZ; CMFCToolBarButtonCustomizeDialog::RebuildImageList(void)
0x180166031  mov     edx, ebx; iImage
0x180166033  mov     this, r14; this
0x180166036  call    ?SelectButton@CMFCToolBarButtonsListButton@@QEAAHH@Z; CMFCToolBarButtonsListButton::SelectButton(int)
0x18016603b  nop
0x18016603c  mov     [rsp+2F48h+var_2F08.__vftable], r13
0x180166041  cmp     [rsp+2F48h+var_2F08.m_hDC], 0
0x180166047  jz      short loc_18016605D
0x180166049  lea     this, [rsp+2F48h+var_2F08]; this
0x18016604e  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180166053  mov     this, rax; hdc
0x180166056  call    cs:__imp_DeleteDC
0x18016605c  nop
0x18016605d  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x180166064  mov     [rsp+2F48h+var_2F18.__vftable], rax
0x180166069  lea     this, [rsp+2F48h+var_2F18]; this
0x18016606e  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180166073  nop
0x180166074  lea     this, [rsp+2F48h+var_2EE8]; this
0x180166079  call    ??1CClientDC@@UEAA@XZ; CClientDC::~CClientDC(void)
0x18016607e  nop
0x18016607f  mov     this, [rsp+2F48h+var_28]
0x180166087  xor     this, rsp; StackCookie
0x18016608a  call    __security_check_cookie
0x18016608f  lea     r11, [rsp+2F48h+var_18]
0x180166097  mov     rbx, [r11+28h]
0x18016609b  mov     rsi, [r11+30h]
0x18016609f  mov     rdi, [r11+38h]
0x1801660a3  mov     rsp, r11
0x1801660a6  pop     r15
0x1801660a8  pop     r14
0x1801660aa  pop     r13
0x1801660ac  retn
0x1801660ad  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
```
