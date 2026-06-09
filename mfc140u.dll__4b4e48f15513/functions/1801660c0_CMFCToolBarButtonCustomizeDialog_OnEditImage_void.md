# CMFCToolBarButtonCustomizeDialog::OnEditImage(void)

- ea: `0x1801660c0`
- end: `0x180166543`
- name: `?OnEditImage@CMFCToolBarButtonCustomizeDialog@@IEAAXXZ`
- size: `1155`
- prototype: `void __fastcall(CMFCToolBarButtonCustomizeDialog *this)`
- caller_count: `0`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18001d090`
- `0x180071580`
- `0x180071714`
- `0x1801660c0`
- `0x180173270`
- `0x1801734a0`
- `0x180173910`
- `0x1801754f0`
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

- `USER32!InvalidateRect` at `0x1801664bd`
- `USER32!InvalidateRect` at `0x1801664bd`
- `GDI32!ExtTextOutW` at `0x18016627b`
- `GDI32!ExtTextOutW` at `0x18016627b`
- `GDI32!SetBkColor` at `0x180166249`
- `GDI32!SetBkColor` at `0x180166249`
- `GDI32!DeleteDC` at `0x1801661c4`
- `GDI32!DeleteDC` at `0x1801662c7`
- `GDI32!DeleteDC` at `0x1801663ed`
- `GDI32!DeleteDC` at `0x18016646e`
- `GDI32!DeleteDC` at `0x1801664e4`
- `GDI32!DeleteDC` at `0x1801661c4`
- `GDI32!DeleteDC` at `0x1801662c7`
- `GDI32!DeleteDC` at `0x1801663ed`
- `GDI32!DeleteDC` at `0x18016646e`
- `GDI32!DeleteDC` at `0x1801664e4`
- `GDI32!CreateCompatibleBitmap` at `0x180166194`
- `GDI32!CreateCompatibleBitmap` at `0x180166194`
- `GDI32!SelectObject` at `0x1801661f7`
- `GDI32!SelectObject` at `0x180166369`
- `GDI32!SelectObject` at `0x1801661f7`
- `GDI32!SelectObject` at `0x180166369`
- `GDI32!CreateCompatibleDC` at `0x18016616c`
- `GDI32!CreateCompatibleDC` at `0x18016616c`
- `GDI32!GetObjectW` at `0x180166392`
- `GDI32!GetObjectW` at `0x180166392`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CMFCToolBarButtonCustomizeDialog::OnEditImage(CMFCToolBarButtonCustomizeDialog *this)
{
  CMFCToolBarImages *m_pImages; // rbx
  HBITMAP__ *m_sizeImage; // rbx
  HDC CompatibleDC; // rdx
  unsigned int hbmMono_high; // r15d
  HBITMAP CompatibleBitmap; // rax
  HDC v7; // rax
  HGDIOBJ v8; // rcx
  CGdiObject *v9; // r14
  CMFCToolBarImages *v10; // rcx
  unsigned int m_clrTransparent; // esi
  HDC v12; // rax
  CMFCToolBarImages *v13; // rax
  void *m_hObject; // rdx
  HGDIOBJ v15; // rax
  HDC v16; // rax
  HDC v17; // rax
  HDC v18; // rax
  CGdiObject v19; // [rsp+60h] [rbp-2F28h] BYREF
  CDC pDCDest; // [rsp+70h] [rbp-2F18h] BYREF
  CClientDC v21; // [rsp+90h] [rbp-2EF8h] BYREF
  _BYTE pv[18]; // [rsp+B8h] [rbp-2ED0h] BYREF
  unsigned __int16 v23; // [rsp+CAh] [rbp-2EBEh]
  tagAFXDrawState cy; // [rsp+D8h] [rbp-2EB0h] BYREF
  CMFCImageEditorDialog v25; // [rsp+F0h] [rbp-2E98h] BYREF

  m_pImages = this->m_pImages;
  if ( !m_pImages || this->m_iSelImage < 0 )
    AfxThrowInvalidArgException();
  m_sizeImage = (HBITMAP__ *)m_pImages->m_sizeImage;
  cy.hbmMono = m_sizeImage;
  try
  {
    CClientDC::CClientDC(&v21, &this->m_wndButtonList);
    v19.m_hObject = 0;
    v19.__vftable = (CGdiObject_vtbl *)CBitmap::`vftable';
    pDCDest.__vftable = (CDC_vtbl *)CDC::`vftable';
    memset(&pDCDest.m_hDC, 0, 20);
    CompatibleDC = CreateCompatibleDC(v21.m_hDC);
    CDC::Attach(&pDCDest, CompatibleDC);
    hbmMono_high = HIDWORD(cy.hbmMono);
    CompatibleBitmap = CreateCompatibleBitmap(v21.m_hDC, (int)m_sizeImage, SHIDWORD(cy.hbmMono));
    if ( CGdiObject::Attach(&v19, CompatibleBitmap) )
    {
      v8 = SelectObject(pDCDest.m_hDC, v19.m_hObject);
      v9 = CGdiObject::FromHandle(v8);
      v10 = this->m_pImages;
      m_clrTransparent = v10->m_clrTransparent;
      if ( m_clrTransparent != 12632256 )
        v10->m_clrTransparent = 12632256;
      cy.hbmMono = 0;
      cy.hbmMonoOld = (HBITMAP__ *)__PAIR64__(hbmMono_high, (unsigned int)m_sizeImage);
      if ( !pDCDest.m_hDC )
        AfxThrowInvalidArgException();
      SetBkColor(pDCDest.m_hDC, 0xC0C0C0u);
      ExtTextOutW(pDCDest.m_hDC, 0, 0, 2u, (const RECT *)&cy, 0, 0, 0);
      cy.hbmMono = 0;
      if ( CMFCToolBarImages::PrepareDrawImage(this->m_pImages, &cy, 0, 0) )
      {
        CMFCToolBarImages::Draw(this->m_pImages, &pDCDest, 0, 0, this->m_iSelImage, 0, 0, 0, 0, 0, 0xFFu);
        CMFCToolBarImages::EndDrawImage(this->m_pImages, &cy);
        v13 = this->m_pImages;
        if ( m_clrTransparent != v13->m_clrTransparent )
          v13->m_clrTransparent = m_clrTransparent;
        m_hObject = 0;
        if ( v9 )
          m_hObject = v9->m_hObject;
        v15 = SelectObject(pDCDest.m_hDC, m_hObject);
        CGdiObject::FromHandle(v15);
        GetObjectW(this->m_pImages->m_hbmImageWell, 32, pv);
        if ( g_pWndCustomize )
        {
          if ( !g_pWndCustomize->OnEditToolbarMenuImage(g_pWndCustomize, this, (CBitmap *)&v19, v23) )
          {
            pDCDest.__vftable = (CDC_vtbl *)CDC::`vftable';
            if ( pDCDest.m_hDC )
            {
              v16 = CDC::Detach(&pDCDest);
              DeleteDC(v16);
            }
            goto LABEL_31;
          }
        }
        else
        {
          CMFCImageEditorDialog::CMFCImageEditorDialog(&v25, (CBitmap *)&v19, this, v23);
          if ( CDialog::DoModal(&v25) != 1 )
          {
            CMFCImageEditorDialog::~CMFCImageEditorDialog(&v25);
            pDCDest.__vftable = (CDC_vtbl *)CDC::`vftable';
            if ( pDCDest.m_hDC )
            {
              v17 = CDC::Detach(&pDCDest);
              DeleteDC(v17);
            }
            goto LABEL_31;
          }
          CMFCImageEditorDialog::~CMFCImageEditorDialog(&v25);
        }
        CMFCToolBarImages::UpdateImage(this->m_pImages, this->m_iSelImage, (HBITMAP__ *)v19.m_hObject);
        InvalidateRect(this->m_wndButtonList.m_hWnd, 0, 1);
        pDCDest.__vftable = (CDC_vtbl *)CDC::`vftable';
        if ( pDCDest.m_hDC )
        {
          v18 = CDC::Detach(&pDCDest);
          DeleteDC(v18);
        }
        goto LABEL_31;
      }
      pDCDest.__vftable = (CDC_vtbl *)CDC::`vftable';
      if ( pDCDest.m_hDC )
      {
        v12 = CDC::Detach(&pDCDest);
        DeleteDC(v12);
      }
    }
    else
    {
      pDCDest.__vftable = (CDC_vtbl *)CDC::`vftable';
      if ( pDCDest.m_hDC )
      {
        v7 = CDC::Detach(&pDCDest);
        DeleteDC(v7);
      }
    }
LABEL_31:
    v19.__vftable = (CGdiObject_vtbl *)CBitmap::`vftable';
    CGdiObject::~CGdiObject(&v19);
    CClientDC::~CClientDC(&v21);
  }
  catch ( ... )
  {
    AfxMessageBox(0x3E88u, 0, 0xFFFFFFFF);
  }
}

```

## disassembly

```asm
0x1801660c0  mov     [rsp+arg_8], rbx
0x1801660c5  mov     [rsp+arg_10], rsi
0x1801660ca  push    rdi
0x1801660cb  push    r12
0x1801660cd  push    r13
0x1801660cf  push    r14
0x1801660d1  push    r15
0x1801660d3  mov     eax, 2F60h
0x1801660d8  call    _alloca_probe
0x1801660dd  sub     rsp, rax
0x1801660e0  mov     rax, cs:__security_cookie
0x1801660e7  xor     rax, rsp
0x1801660ea  mov     [rsp+2F88h+var_38], rax
0x1801660f2  mov     rdi, this
0x1801660f5  mov     rbx, [this+8F0h]
0x1801660fc  xor     r12d, r12d
0x1801660ff  test    rbx, rbx
0x180166102  jz      loc_180166536
0x180166108  cmp     [this+8FCh], r12d
0x18016610f  jl      loc_180166536
0x180166115  mov     rbx, [rbx+68h]
0x180166119  mov     qword ptr [rsp+2F88h+cy], rbx
0x180166121  lea     rdx, [this+5B8h]; pWnd
0x180166128  lea     this, [rsp+2F88h+var_2EF8]; this
0x180166130  call    ??0CClientDC@@QEAA@PEAVCWnd@@@Z; CClientDC::CClientDC(CWnd *)
0x180166135  nop
0x180166136  mov     [rsp+2F88h+var_2F28.m_hObject], r12
0x18016613b  lea     r13, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x180166142  mov     [rsp+2F88h+var_2F28.__vftable], r13
0x180166147  lea     rsi, ??_7CDC@@6B@; const CDC::`vftable'
0x18016614e  mov     [rsp+2F88h+pDCDest.__vftable], rsi
0x180166153  xorps   xmm0, xmm0
0x180166156  movdqu  xmmword ptr [rsp+2F88h+pDCDest.m_hDC], xmm0
0x18016615c  mov     [rsp+2F88h+pDCDest.m_bPrinting], r12d
0x180166164  mov     this, [rsp+2F88h+var_2EF8.m_hDC]; hdc
0x18016616c  call    cs:__imp_CreateCompatibleDC
0x180166172  mov     rdx, rax; hDC
0x180166175  lea     this, [rsp+2F88h+pDCDest]; this
0x18016617a  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x18016617f  mov     r15d, [rsp+2F88h+cy+4]
0x180166187  mov     r8d, r15d; cy
0x18016618a  mov     edx, ebx; cx
0x18016618c  mov     this, [rsp+2F88h+var_2EF8.m_hDC]; hdc
0x180166194  call    cs:__imp_CreateCompatibleBitmap
0x18016619a  mov     rdx, rax; hObject
0x18016619d  lea     this, [rsp+2F88h+var_2F28]; this
0x1801661a2  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1801661a7  test    eax, eax
0x1801661a9  jnz     short loc_1801661ED
0x1801661ab  mov     [rsp+2F88h+pDCDest.__vftable], rsi
0x1801661b0  cmp     [rsp+2F88h+pDCDest.m_hDC], r12
0x1801661b5  jz      short loc_1801661CB
0x1801661b7  lea     this, [rsp+2F88h+pDCDest]; this
0x1801661bc  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1801661c1  mov     this, rax; hdc
0x1801661c4  call    cs:__imp_DeleteDC
0x1801661ca  nop
0x1801661cb  mov     [rsp+2F88h+var_2F28.__vftable], r13
0x1801661d0  lea     this, [rsp+2F88h+var_2F28]; this
0x1801661d5  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1801661da  nop
0x1801661db  lea     this, [rsp+2F88h+var_2EF8]; this
0x1801661e3  call    ??1CClientDC@@UEAA@XZ; CClientDC::~CClientDC(void)
0x1801661e8  jmp     $LN18_25
0x1801661ed  mov     rdx, [rsp+2F88h+var_2F28.m_hObject]; h
0x1801661f2  mov     this, [rsp+2F88h+pDCDest.m_hDC]; hdc
0x1801661f7  call    cs:__imp_SelectObject
0x1801661fd  mov     this, rax; h
0x180166200  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x180166205  mov     r14, rax
0x180166208  mov     this, [rdi+8F0h]
0x18016620f  mov     esi, [this+0D8h]
0x180166215  mov     edx, 0C0C0C0h; color
0x18016621a  cmp     esi, edx
0x18016621c  jz      short loc_180166224
0x18016621e  mov     [this+0D8h], edx
0x180166224  mov     qword ptr [rsp+2F88h+cy], r12
0x18016622c  mov     [rsp+2F88h+var_2EA8], ebx
0x180166233  mov     [rsp+2F88h+var_2EA4], r15d
0x18016623b  mov     this, [rsp+2F88h+pDCDest.m_hDC]; hdc
0x180166240  test    this, this
0x180166243  jz      loc_18016653C
0x180166249  call    cs:__imp_SetBkColor
0x18016624f  mov     [rsp+2F88h+lpDx], r12; lpDx
0x180166254  mov     [rsp+2F88h+c], r12d; c
0x180166259  mov     [rsp+2F88h+lpString], r12; lpString
0x18016625e  lea     rax, [rsp+2F88h+cy]
0x180166266  mov     [rsp+2F88h+lprect], rax; lprect
0x18016626b  mov     r9d, 2; options
0x180166271  xor     r8d, r8d; y
0x180166274  xor     edx, edx; x
0x180166276  mov     this, [rsp+2F88h+pDCDest.m_hDC]; hdc
0x18016627b  call    cs:__imp_ExtTextOutW
0x180166281  mov     qword ptr [rsp+2F88h+cy], r12
0x180166289  xor     r9d, r9d; bFadeInactive
0x18016628c  mov     r8, r12; sizeImageDest
0x18016628f  lea     rdx, [rsp+2F88h+cy]; ds
0x180166297  mov     this, [rdi+8F0h]; this
0x18016629e  call    ?PrepareDrawImage@CMFCToolBarImages@@QEAAHAEAUtagAFXDrawState@@VCSize@@H@Z; CMFCToolBarImages::PrepareDrawImage(tagAFXDrawState &,CSize,int)
0x1801662a3  test    eax, eax
0x1801662a5  jnz     short loc_1801662F0
0x1801662a7  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x1801662ae  mov     [rsp+2F88h+pDCDest.__vftable], rax
0x1801662b3  cmp     [rsp+2F88h+pDCDest.m_hDC], r12
0x1801662b8  jz      short loc_1801662CE
0x1801662ba  lea     this, [rsp+2F88h+pDCDest]; this
0x1801662bf  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1801662c4  mov     this, rax; hdc
0x1801662c7  call    cs:__imp_DeleteDC
0x1801662cd  nop
0x1801662ce  mov     [rsp+2F88h+var_2F28.__vftable], r13
0x1801662d3  lea     this, [rsp+2F88h+var_2F28]; this
0x1801662d8  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1801662dd  nop
0x1801662de  lea     this, [rsp+2F88h+var_2EF8]; this
0x1801662e6  call    ??1CClientDC@@UEAA@XZ; CClientDC::~CClientDC(void)
0x1801662eb  jmp     $LN18_25
0x1801662f0  mov     [rsp+2F88h+alphaSrc], 0FFh; alphaSrc
0x1801662f5  mov     [rsp+2F88h+bInactive], r12d; bInactive
0x1801662fa  mov     [rsp+2F88h+bShadow], r12d; bShadow
0x1801662ff  mov     dword ptr [rsp+2F88h+lpDx], r12d; bIndeterminate
0x180166304  mov     [rsp+2F88h+c], r12d; bDisabled
0x180166309  mov     dword ptr [rsp+2F88h+lpString], r12d; bHilite
0x18016630e  mov     eax, [rdi+8FCh]
0x180166314  mov     dword ptr [rsp+2F88h+lprect], eax; iImage
0x180166318  xor     r9d, r9d; yDest
0x18016631b  xor     r8d, r8d; xDest
0x18016631e  lea     rdx, [rsp+2F88h+pDCDest]; pDCDest
0x180166323  mov     this, [rdi+8F0h]; this
0x18016632a  call    ?Draw@CMFCToolBarImages@@QEAAHPEAVCDC@@HHHHHHHHE@Z; CMFCToolBarImages::Draw(CDC *,int,int,int,int,int,int,int,int,uchar)
0x18016632f  lea     rdx, [rsp+2F88h+cy]; ds
0x180166337  mov     this, [rdi+8F0h]; this
0x18016633e  call    ?EndDrawImage@CMFCToolBarImages@@QEAAXAEAUtagAFXDrawState@@@Z; CMFCToolBarImages::EndDrawImage(tagAFXDrawState &)
0x180166343  mov     rax, [rdi+8F0h]
0x18016634a  cmp     esi, [rax+0D8h]
0x180166350  jz      short loc_180166358
0x180166352  mov     [rax+0D8h], esi
0x180166358  test    r14, r14
0x18016635b  mov     rdx, r12
0x18016635e  jz      short loc_180166364
0x180166360  mov     rdx, [r14+8]; h
0x180166364  mov     this, [rsp+2F88h+pDCDest.m_hDC]; hdc
0x180166369  call    cs:__imp_SelectObject
0x18016636f  mov     this, rax; h
0x180166372  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x180166377  mov     this, [rdi+8F0h]
0x18016637e  lea     r8, [rsp+2F88h+pv]; pv
0x180166386  mov     edx, 20h ; ' '; c
0x18016638b  mov     this, [this+0A0h]; h
0x180166392  call    cs:__imp_GetObjectW
0x180166398  mov     this, cs:?g_pWndCustomize@@3PEAVCMFCToolBarsCustomizeDialog@@EA; CMFCToolBarsCustomizeDialog * g_pWndCustomize
0x18016639f  movzx   r9d, [rsp+2F88h+var_2EBE]; nBitsPixel
0x1801663a8  test    this, this
0x1801663ab  jz      short loc_180166416
0x1801663ad  mov     rax, [this]
0x1801663b0  lea     r8, [rsp+2F88h+var_2F28]
0x1801663b5  mov     rdx, rdi
0x1801663b8  mov     rax, [rax+348h]
0x1801663bf  call    cs:__guard_dispatch_icall_fptr
0x1801663c5  test    eax, eax
0x1801663c7  jnz     loc_180166499
0x1801663cd  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x1801663d4  mov     [rsp+2F88h+pDCDest.__vftable], rax
0x1801663d9  cmp     [rsp+2F88h+pDCDest.m_hDC], r12
0x1801663de  jz      short loc_1801663F4
0x1801663e0  lea     this, [rsp+2F88h+pDCDest]; this
0x1801663e5  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1801663ea  mov     this, rax; hdc
0x1801663ed  call    cs:__imp_DeleteDC
0x1801663f3  nop
0x1801663f4  mov     [rsp+2F88h+var_2F28.__vftable], r13
0x1801663f9  lea     this, [rsp+2F88h+var_2F28]; this
0x1801663fe  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180166403  nop
0x180166404  lea     this, [rsp+2F88h+var_2EF8]; this
0x18016640c  call    ??1CClientDC@@UEAA@XZ; CClientDC::~CClientDC(void)
0x180166411  jmp     $LN18_25
0x180166416  mov     r8, rdi; pParent
0x180166419  lea     rdx, [rsp+2F88h+var_2F28]; pBitmap
0x18016641e  lea     this, [rsp+2F88h+var_2E98]; this
0x180166426  call    ??0CMFCImageEditorDialog@@QEAA@PEAVCBitmap@@PEAVCWnd@@H@Z; CMFCImageEditorDialog::CMFCImageEditorDialog(CBitmap *,CWnd *,int)
0x18016642b  nop
0x18016642c  lea     this, [rsp+2F88h+var_2E98]; this
0x180166434  call    ?DoModal@CDialog@@UEAA_JXZ; CDialog::DoModal(void)
0x180166439  nop
0x18016643a  lea     this, [rsp+2F88h+var_2E98]; this
0x180166442  cmp     rax, 1
0x180166446  jz      short loc_180166494
0x180166448  call    ??1CMFCImageEditorDialog@@UEAA@XZ; CMFCImageEditorDialog::~CMFCImageEditorDialog(void)
0x18016644d  nop
0x18016644e  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x180166455  mov     [rsp+2F88h+pDCDest.__vftable], rax
0x18016645a  cmp     [rsp+2F88h+pDCDest.m_hDC], r12
0x18016645f  jz      short loc_180166475
0x180166461  lea     this, [rsp+2F88h+pDCDest]; this
0x180166466  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x18016646b  mov     this, rax; hdc
0x18016646e  call    cs:__imp_DeleteDC
0x180166474  nop
0x180166475  mov     [rsp+2F88h+var_2F28.__vftable], r13
0x18016647a  lea     this, [rsp+2F88h+var_2F28]; this
0x18016647f  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180166484  nop
0x180166485  lea     this, [rsp+2F88h+var_2EF8]; this
0x18016648d  call    ??1CClientDC@@UEAA@XZ; CClientDC::~CClientDC(void)
0x180166492  jmp     short $LN18_25
0x180166494  call    ??1CMFCImageEditorDialog@@UEAA@XZ; CMFCImageEditorDialog::~CMFCImageEditorDialog(void)
0x180166499  mov     r8, [rsp+2F88h+var_2F28.m_hObject]; hbmp
0x18016649e  mov     edx, [rdi+8FCh]; iImage
0x1801664a4  mov     this, [rdi+8F0h]; this
0x1801664ab  call    ?UpdateImage@CMFCToolBarImages@@QEAAHHPEAUHBITMAP__@@@Z; CMFCToolBarImages::UpdateImage(int,HBITMAP__ *)
0x1801664b0  xor     edx, edx; lpRect
0x1801664b2  lea     r8d, [rdx+1]; bErase
0x1801664b6  mov     this, [rdi+5F8h]; hWnd
0x1801664bd  call    cs:__imp_InvalidateRect
0x1801664c3  nop
0x1801664c4  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x1801664cb  mov     [rsp+2F88h+pDCDest.__vftable], rax
0x1801664d0  cmp     [rsp+2F88h+pDCDest.m_hDC], r12
0x1801664d5  jz      short loc_1801664EB
0x1801664d7  lea     this, [rsp+2F88h+pDCDest]; this
0x1801664dc  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1801664e1  mov     this, rax; hdc
0x1801664e4  call    cs:__imp_DeleteDC
0x1801664ea  nop
0x1801664eb  mov     [rsp+2F88h+var_2F28.__vftable], r13
0x1801664f0  lea     this, [rsp+2F88h+var_2F28]; this
0x1801664f5  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1801664fa  nop
0x1801664fb  lea     this, [rsp+2F88h+var_2EF8]; this
0x180166503  call    ??1CClientDC@@UEAA@XZ; CClientDC::~CClientDC(void)
0x180166508  nop
0x180166509  mov     this, [rsp+2F88h+var_38]
0x180166511  xor     this, rsp; StackCookie
0x180166514  call    __security_check_cookie
0x180166519  lea     r11, [rsp+2F88h+var_28]
0x180166521  mov     rbx, [r11+38h]
0x180166525  mov     rsi, [r11+40h]
0x180166529  mov     rsp, r11
0x18016652c  pop     r15
0x18016652e  pop     r14
0x180166530  pop     r13
0x180166532  pop     r12
0x180166534  pop     rdi
0x180166535  retn
0x180166536  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
0x18016653c  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
```
