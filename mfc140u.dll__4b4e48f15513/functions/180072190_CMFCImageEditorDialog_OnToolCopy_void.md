# CMFCImageEditorDialog::OnToolCopy(void)

- ea: `0x180072190`
- end: `0x1800725a5`
- name: `?OnToolCopy@CMFCImageEditorDialog@@IEAAXXZ`
- size: `1045`
- prototype: `void __fastcall(CMFCImageEditorDialog *this)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18001d090`
- `0x180072190`
- `0x180139950`
- `0x1801d7400`
- `0x18023d860`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802b0720`
- `0x1802b07d0`
- `0x1802b09a0`
- `0x1802b09d0`

## import_xrefs

- `USER32!CloseClipboard` at `0x180072458`
- `USER32!CloseClipboard` at `0x180072518`
- `USER32!CloseClipboard` at `0x180072458`
- `USER32!CloseClipboard` at `0x180072518`
- `USER32!SetClipboardData` at `0x1800724fd`
- `USER32!SetClipboardData` at `0x1800724fd`
- `USER32!EmptyClipboard` at `0x18007243a`
- `USER32!EmptyClipboard` at `0x18007243a`
- `USER32!OpenClipboard` at `0x1800723b4`
- `USER32!OpenClipboard` at `0x1800723b4`
- `GDI32!DeleteDC` at `0x1800722a6`
- `GDI32!DeleteDC` at `0x1800722cf`
- `GDI32!DeleteDC` at `0x1800723f8`
- `GDI32!DeleteDC` at `0x180072421`
- `GDI32!DeleteDC` at `0x180072488`
- `GDI32!DeleteDC` at `0x1800724b1`
- `GDI32!DeleteDC` at `0x180072548`
- `GDI32!DeleteDC` at `0x180072571`
- `GDI32!DeleteDC` at `0x1800722a6`
- `GDI32!DeleteDC` at `0x1800722cf`
- `GDI32!DeleteDC` at `0x1800723f8`
- `GDI32!DeleteDC` at `0x180072421`
- `GDI32!DeleteDC` at `0x180072488`
- `GDI32!DeleteDC` at `0x1800724b1`
- `GDI32!DeleteDC` at `0x180072548`
- `GDI32!DeleteDC` at `0x180072571`
- `GDI32!BitBlt` at `0x180072369`
- `GDI32!BitBlt` at `0x180072369`
- `GDI32!CreateCompatibleBitmap` at `0x180072255`
- `GDI32!CreateCompatibleBitmap` at `0x180072255`
- `GDI32!SelectObject` at `0x1800722f5`
- `GDI32!SelectObject` at `0x18007231e`
- `GDI32!SelectObject` at `0x180072383`
- `GDI32!SelectObject` at `0x1800723a2`
- `GDI32!SelectObject` at `0x1800722f5`
- `GDI32!SelectObject` at `0x18007231e`
- `GDI32!SelectObject` at `0x180072383`
- `GDI32!SelectObject` at `0x1800723a2`
- `GDI32!CreateCompatibleDC` at `0x1800721f1`
- `GDI32!CreateCompatibleDC` at `0x18007221c`
- `GDI32!CreateCompatibleDC` at `0x1800721f1`
- `GDI32!CreateCompatibleDC` at `0x18007221c`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CMFCImageEditorDialog::OnToolCopy(CMFCImageEditorDialog *this)
{
  HDC CompatibleDC; // rdx
  HDC v3; // rdx
  HBITMAP CompatibleBitmap; // rdx
  HDC v5; // rax
  HDC v6; // rax
  HGDIOBJ v7; // rcx
  CGdiObject *v8; // rsi
  CBitmap *m_pBitmap; // rcx
  void *m_hObject; // rdx
  HGDIOBJ v11; // rax
  CGdiObject *v12; // rdi
  void *v13; // rdx
  HGDIOBJ v14; // rax
  void *v15; // rdx
  HGDIOBJ v16; // rax
  HDC v17; // rax
  HDC v18; // rax
  HDC v19; // rax
  HDC v20; // rax
  void *v21; // rbx
  CHandleMap *m_pmapHGDIOBJ; // rcx
  HDC v23; // rax
  HDC v24; // rax
  CBitmap bitmapCopy; // [rsp+50h] [rbp-98h] BYREF
  CDC memDCSrc; // [rsp+60h] [rbp-88h] BYREF
  CDC memDCDest; // [rsp+80h] [rbp-68h] BYREF
  CWindowDC dc; // [rsp+A0h] [rbp-48h] BYREF

  if ( this->m_pBitmap )
  {
    try
    {
      CWindowDC::CWindowDC(&dc, this);
      memDCDest.__vftable = (CDC_vtbl *)CDC::`vftable';
      memset(&memDCDest.m_hDC, 0, 20);
      CompatibleDC = CreateCompatibleDC(0);
      CDC::Attach(&memDCDest, CompatibleDC);
      memDCSrc.__vftable = (CDC_vtbl *)CDC::`vftable';
      memset(&memDCSrc.m_hDC, 0, 20);
      v3 = CreateCompatibleDC(0);
      CDC::Attach(&memDCSrc, v3);
      bitmapCopy.m_hObject = 0;
      bitmapCopy.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
      CompatibleBitmap = CreateCompatibleBitmap(dc.m_hDC, this->m_sizeImage.cx, this->m_sizeImage.cy);
      if ( CGdiObject::Attach(&bitmapCopy, CompatibleBitmap) )
      {
        v7 = SelectObject(memDCDest.m_hDC, bitmapCopy.m_hObject);
        v8 = CGdiObject::FromHandle(v7);
        m_pBitmap = this->m_pBitmap;
        m_hObject = 0;
        if ( m_pBitmap )
          m_hObject = m_pBitmap->m_hObject;
        v11 = SelectObject(memDCSrc.m_hDC, m_hObject);
        v12 = CGdiObject::FromHandle(v11);
        BitBlt(memDCDest.m_hDC, 0, 0, this->m_sizeImage.cx, this->m_sizeImage.cy, memDCSrc.m_hDC, 0, 0, 0xCC0020u);
        v13 = 0;
        if ( v8 )
          v13 = v8->m_hObject;
        v14 = SelectObject(memDCDest.m_hDC, v13);
        CGdiObject::FromHandle(v14);
        v15 = 0;
        if ( v12 )
          v15 = v12->m_hObject;
        v16 = SelectObject(memDCSrc.m_hDC, v15);
        CGdiObject::FromHandle(v16);
        if ( OpenClipboard(this->m_hWnd) )
        {
          if ( EmptyClipboard() )
          {
            v21 = bitmapCopy.m_hObject;
            if ( bitmapCopy.m_hObject )
            {
              m_pmapHGDIOBJ = AfxGetModuleThreadState()->m_pmapHGDIOBJ;
              if ( m_pmapHGDIOBJ )
                CMapPtrToWord::RemoveKey((CMapPtrToWord *)&m_pmapHGDIOBJ->m_permanentMap, bitmapCopy.m_hObject);
            }
            bitmapCopy.m_hObject = 0;
            if ( !SetClipboardData(2u, v21) )
              AfxMessageBox(0x3E8Au, 0, 0xFFFFFFFF);
            CloseClipboard();
            bitmapCopy.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
            CGdiObject::~CGdiObject(&bitmapCopy);
            memDCSrc.__vftable = (CDC_vtbl *)CDC::`vftable';
            if ( memDCSrc.m_hDC )
            {
              v23 = CDC::Detach(&memDCSrc);
              DeleteDC(v23);
            }
            memDCDest.__vftable = (CDC_vtbl *)CDC::`vftable';
            if ( memDCDest.m_hDC )
            {
              v24 = CDC::Detach(&memDCDest);
              DeleteDC(v24);
            }
          }
          else
          {
            AfxMessageBox(0x3E8Au, 0, 0xFFFFFFFF);
            CloseClipboard();
            bitmapCopy.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
            CGdiObject::~CGdiObject(&bitmapCopy);
            memDCSrc.__vftable = (CDC_vtbl *)CDC::`vftable';
            if ( memDCSrc.m_hDC )
            {
              v19 = CDC::Detach(&memDCSrc);
              DeleteDC(v19);
            }
            memDCDest.__vftable = (CDC_vtbl *)CDC::`vftable';
            if ( memDCDest.m_hDC )
            {
              v20 = CDC::Detach(&memDCDest);
              DeleteDC(v20);
            }
          }
        }
        else
        {
          AfxMessageBox(0x3E8Au, 0, 0xFFFFFFFF);
          bitmapCopy.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
          CGdiObject::~CGdiObject(&bitmapCopy);
          memDCSrc.__vftable = (CDC_vtbl *)CDC::`vftable';
          if ( memDCSrc.m_hDC )
          {
            v17 = CDC::Detach(&memDCSrc);
            DeleteDC(v17);
          }
          memDCDest.__vftable = (CDC_vtbl *)CDC::`vftable';
          if ( memDCDest.m_hDC )
          {
            v18 = CDC::Detach(&memDCDest);
            DeleteDC(v18);
          }
        }
      }
      else
      {
        AfxMessageBox(0x3E8Au, 0, 0xFFFFFFFF);
        bitmapCopy.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
        CGdiObject::~CGdiObject(&bitmapCopy);
        memDCSrc.__vftable = (CDC_vtbl *)CDC::`vftable';
        if ( memDCSrc.m_hDC )
        {
          v5 = CDC::Detach(&memDCSrc);
          DeleteDC(v5);
        }
        memDCDest.__vftable = (CDC_vtbl *)CDC::`vftable';
        if ( memDCDest.m_hDC )
        {
          v6 = CDC::Detach(&memDCDest);
          DeleteDC(v6);
        }
      }
      CWindowDC::~CWindowDC(&dc);
    }
    catch ( ... )
    {
      AfxMessageBox(0x3E88u, 0, 0xFFFFFFFF);
    }
  }
}

```

## disassembly

```asm
0x180072190  mov     rax, rsp
0x180072193  mov     [rax+8], rbx
0x180072197  mov     [rax+10h], rsi
0x18007219b  mov     [rax+18h], rdi
0x18007219f  push    r12
0x1800721a1  push    r14
0x1800721a3  push    r15
0x1800721a5  sub     rsp, 0D0h
0x1800721ac  mov     rbx, this
0x1800721af  xor     r14d, r14d
0x1800721b2  cmp     [this+5D0h], r14
0x1800721b9  jz      $LN16_1
0x1800721bf  mov     rdx, this; pWnd
0x1800721c2  lea     this, [rax-48h]; this
0x1800721c6  call    ??0CWindowDC@@QEAA@PEAVCWnd@@@Z; CWindowDC::CWindowDC(CWnd *)
0x1800721cb  nop
0x1800721cc  lea     r15, ??_7CDC@@6B@; const CDC::`vftable'
0x1800721d3  mov     [rsp+0E8h+memDCDest.__vftable], r15
0x1800721db  xorps   xmm0, xmm0
0x1800721de  movdqu  xmmword ptr [rsp+0E8h+memDCDest.m_hDC], xmm0
0x1800721e7  mov     [rsp+0E8h+memDCDest.m_bPrinting], r14d
0x1800721ef  xor     ecx, ecx; hdc
0x1800721f1  call    cs:__imp_CreateCompatibleDC
0x1800721f7  mov     rdx, rax; hDC
0x1800721fa  lea     this, [rsp+0E8h+memDCDest]; this
0x180072202  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180072207  mov     [rsp+0E8h+memDCSrc.__vftable], r15
0x18007220c  xorps   xmm0, xmm0
0x18007220f  movdqu  xmmword ptr [rsp+0E8h+memDCSrc.m_hDC], xmm0
0x180072215  mov     [rsp+0E8h+memDCSrc.m_bPrinting], r14d
0x18007221a  xor     ecx, ecx; hdc
0x18007221c  call    cs:__imp_CreateCompatibleDC
0x180072222  mov     rdx, rax; hDC
0x180072225  lea     this, [rsp+0E8h+memDCSrc]; this
0x18007222a  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x18007222f  mov     [rsp+0E8h+bitmapCopy.m_hObject], r14
0x180072234  lea     r12, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18007223b  mov     [rsp+0E8h+bitmapCopy.__vftable], r12
0x180072240  mov     r8d, [rbx+5DCh]; cy
0x180072247  mov     edx, [rbx+5D8h]; cx
0x18007224d  mov     this, [rsp+0E8h+dc.m_hDC]; hdc
0x180072255  call    cs:__imp_CreateCompatibleBitmap
0x18007225b  mov     rdx, rax; hObject
0x18007225e  lea     this, [rsp+0E8h+bitmapCopy]; this
0x180072263  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x180072268  test    eax, eax
0x18007226a  jnz     short loc_1800722E8
0x18007226c  or      r8d, 0FFFFFFFFh; nIDHelp
0x180072270  xor     edx, edx; nType
0x180072272  mov     ecx, 3E8Ah; nIDPrompt
0x180072277  call    ?AfxMessageBox@@YAHIII@Z; AfxMessageBox(uint,uint,uint)
0x18007227c  nop
0x18007227d  mov     [rsp+0E8h+bitmapCopy.__vftable], r12
0x180072282  lea     this, [rsp+0E8h+bitmapCopy]; this
0x180072287  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18007228c  nop
0x18007228d  mov     [rsp+0E8h+memDCSrc.__vftable], r15
0x180072292  cmp     [rsp+0E8h+memDCSrc.m_hDC], r14
0x180072297  jz      short loc_1800722AD
0x180072299  lea     this, [rsp+0E8h+memDCSrc]; this
0x18007229e  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1800722a3  mov     this, rax; hdc
0x1800722a6  call    cs:__imp_DeleteDC
0x1800722ac  nop
0x1800722ad  mov     [rsp+0E8h+memDCDest.__vftable], r15
0x1800722b5  cmp     [rsp+0E8h+memDCDest.m_hDC], r14
0x1800722bd  jz      short loc_1800722D6
0x1800722bf  lea     this, [rsp+0E8h+memDCDest]; this
0x1800722c7  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1800722cc  mov     this, rax; hdc
0x1800722cf  call    cs:__imp_DeleteDC
0x1800722d5  nop
0x1800722d6  lea     this, [rsp+0E8h+dc]; this
0x1800722de  call    ??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x1800722e3  jmp     $LN16_1
0x1800722e8  mov     rdx, [rsp+0E8h+bitmapCopy.m_hObject]; h
0x1800722ed  mov     this, [rsp+0E8h+memDCDest.m_hDC]; hdc
0x1800722f5  call    cs:__imp_SelectObject
0x1800722fb  mov     this, rax; h
0x1800722fe  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x180072303  mov     rsi, rax
0x180072306  mov     this, [rbx+5D0h]
0x18007230d  test    this, this
0x180072310  mov     rdx, r14
0x180072313  jz      short loc_180072319
0x180072315  mov     rdx, [this+8]; h
0x180072319  mov     this, [rsp+0E8h+memDCSrc.m_hDC]; hdc
0x18007231e  call    cs:__imp_SelectObject
0x180072324  mov     this, rax; h
0x180072327  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18007232c  mov     rdi, rax
0x18007232f  mov     edx, [rbx+5DCh]
0x180072335  mov     [rsp+0E8h+rop], 0CC0020h; rop
0x18007233d  mov     [rsp+0E8h+y1], r14d; y1
0x180072342  mov     [rsp+0E8h+x1], r14d; x1
0x180072347  mov     this, [rsp+0E8h+memDCSrc.m_hDC]
0x18007234c  mov     [rsp+0E8h+hdcSrc], this; hdcSrc
0x180072351  mov     [rsp+0E8h+cy], edx; cy
0x180072355  mov     r9d, [rbx+5D8h]; cx
0x18007235c  xor     r8d, r8d; y
0x18007235f  xor     edx, edx; x
0x180072361  mov     this, [rsp+0E8h+memDCDest.m_hDC]; hdc
0x180072369  call    cs:__imp_BitBlt
0x18007236f  test    rsi, rsi
0x180072372  mov     rdx, r14
0x180072375  jz      short loc_18007237B
0x180072377  mov     rdx, [rsi+8]; h
0x18007237b  mov     this, [rsp+0E8h+memDCDest.m_hDC]; hdc
0x180072383  call    cs:__imp_SelectObject
0x180072389  mov     this, rax; h
0x18007238c  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x180072391  test    rdi, rdi
0x180072394  mov     rdx, r14
0x180072397  jz      short loc_18007239D
0x180072399  mov     rdx, [rdi+8]; h
0x18007239d  mov     this, [rsp+0E8h+memDCSrc.m_hDC]; hdc
0x1800723a2  call    cs:__imp_SelectObject
0x1800723a8  mov     this, rax; h
0x1800723ab  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1800723b0  mov     this, [rbx+40h]; hWndNewOwner
0x1800723b4  call    cs:__imp_OpenClipboard
0x1800723ba  test    eax, eax
0x1800723bc  jnz     short loc_18007243A
0x1800723be  or      r8d, 0FFFFFFFFh; nIDHelp
0x1800723c2  xor     edx, edx; nType
0x1800723c4  mov     ecx, 3E8Ah; nIDPrompt
0x1800723c9  call    ?AfxMessageBox@@YAHIII@Z; AfxMessageBox(uint,uint,uint)
0x1800723ce  nop
0x1800723cf  mov     [rsp+0E8h+bitmapCopy.__vftable], r12
0x1800723d4  lea     this, [rsp+0E8h+bitmapCopy]; this
0x1800723d9  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1800723de  nop
0x1800723df  mov     [rsp+0E8h+memDCSrc.__vftable], r15
0x1800723e4  cmp     [rsp+0E8h+memDCSrc.m_hDC], r14
0x1800723e9  jz      short loc_1800723FF
0x1800723eb  lea     this, [rsp+0E8h+memDCSrc]; this
0x1800723f0  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1800723f5  mov     this, rax; hdc
0x1800723f8  call    cs:__imp_DeleteDC
0x1800723fe  nop
0x1800723ff  mov     [rsp+0E8h+memDCDest.__vftable], r15
0x180072407  cmp     [rsp+0E8h+memDCDest.m_hDC], r14
0x18007240f  jz      short loc_180072428
0x180072411  lea     this, [rsp+0E8h+memDCDest]; this
0x180072419  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x18007241e  mov     this, rax; hdc
0x180072421  call    cs:__imp_DeleteDC
0x180072427  nop
0x180072428  lea     this, [rsp+0E8h+dc]; this
0x180072430  call    ??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x180072435  jmp     $LN16_1
0x18007243a  call    cs:__imp_EmptyClipboard
0x180072440  test    eax, eax
0x180072442  jnz     loc_1800724CA
0x180072448  or      r8d, 0FFFFFFFFh; nIDHelp
0x18007244c  xor     edx, edx; nType
0x18007244e  mov     ecx, 3E8Ah; nIDPrompt
0x180072453  call    ?AfxMessageBox@@YAHIII@Z; AfxMessageBox(uint,uint,uint)
0x180072458  call    cs:__imp_CloseClipboard
0x18007245e  nop
0x18007245f  mov     [rsp+0E8h+bitmapCopy.__vftable], r12
0x180072464  lea     this, [rsp+0E8h+bitmapCopy]; this
0x180072469  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18007246e  nop
0x18007246f  mov     [rsp+0E8h+memDCSrc.__vftable], r15
0x180072474  cmp     [rsp+0E8h+memDCSrc.m_hDC], r14
0x180072479  jz      short loc_18007248F
0x18007247b  lea     this, [rsp+0E8h+memDCSrc]; this
0x180072480  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180072485  mov     this, rax; hdc
0x180072488  call    cs:__imp_DeleteDC
0x18007248e  nop
0x18007248f  mov     [rsp+0E8h+memDCDest.__vftable], r15
0x180072497  cmp     [rsp+0E8h+memDCDest.m_hDC], r14
0x18007249f  jz      short loc_1800724B8
0x1800724a1  lea     this, [rsp+0E8h+memDCDest]; this
0x1800724a9  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1800724ae  mov     this, rax; hdc
0x1800724b1  call    cs:__imp_DeleteDC
0x1800724b7  nop
0x1800724b8  lea     this, [rsp+0E8h+dc]; this
0x1800724c0  call    ??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x1800724c5  jmp     $LN16_1
0x1800724ca  mov     rbx, [rsp+0E8h+bitmapCopy.m_hObject]
0x1800724cf  test    rbx, rbx
0x1800724d2  jz      short loc_1800724F0
0x1800724d4  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x1800724d9  mov     this, [rax+40h]
0x1800724dd  test    this, this
0x1800724e0  jz      short loc_1800724F0
0x1800724e2  add     this, 28h ; '('; this
0x1800724e6  mov     rdx, [rsp+0E8h+bitmapCopy.m_hObject]; key
0x1800724eb  call    ?RemoveKey@CMapPtrToWord@@QEAAHPEAX@Z; CMapPtrToWord::RemoveKey(void *)
0x1800724f0  mov     [rsp+0E8h+bitmapCopy.m_hObject], r14
0x1800724f5  mov     rdx, rbx; hMem
0x1800724f8  mov     ecx, 2; uFormat
0x1800724fd  call    cs:__imp_SetClipboardData
0x180072503  test    rax, rax
0x180072506  jnz     short loc_180072518
0x180072508  or      r8d, 0FFFFFFFFh; nIDHelp
0x18007250c  xor     edx, edx; nType
0x18007250e  mov     ecx, 3E8Ah; nIDPrompt
0x180072513  call    ?AfxMessageBox@@YAHIII@Z; AfxMessageBox(uint,uint,uint)
0x180072518  call    cs:__imp_CloseClipboard
0x18007251e  nop
0x18007251f  mov     [rsp+0E8h+bitmapCopy.__vftable], r12
0x180072524  lea     this, [rsp+0E8h+bitmapCopy]; this
0x180072529  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18007252e  nop
0x18007252f  mov     [rsp+0E8h+memDCSrc.__vftable], r15
0x180072534  cmp     [rsp+0E8h+memDCSrc.m_hDC], r14
0x180072539  jz      short loc_18007254F
0x18007253b  lea     this, [rsp+0E8h+memDCSrc]; this
0x180072540  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180072545  mov     this, rax; hdc
0x180072548  call    cs:__imp_DeleteDC
0x18007254e  nop
0x18007254f  mov     [rsp+0E8h+memDCDest.__vftable], r15
0x180072557  cmp     [rsp+0E8h+memDCDest.m_hDC], r14
0x18007255f  jz      short loc_180072578
0x180072561  lea     this, [rsp+0E8h+memDCDest]; this
0x180072569  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x18007256e  mov     this, rax; hdc
0x180072571  call    cs:__imp_DeleteDC
0x180072577  nop
0x180072578  lea     this, [rsp+0E8h+dc]; this
0x180072580  call    ??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x180072585  nop
0x180072586  lea     r11, [rsp+0E8h+var_18]
0x18007258e  mov     rbx, [r11+20h]
0x180072592  mov     rsi, [r11+28h]
0x180072596  mov     rdi, [r11+30h]
0x18007259a  mov     rsp, r11
0x18007259d  pop     r15
0x18007259f  pop     r14
0x1800725a1  pop     r12
0x1800725a3  retn
```
