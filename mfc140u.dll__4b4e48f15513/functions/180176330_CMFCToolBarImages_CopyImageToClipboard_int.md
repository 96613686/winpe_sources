# CMFCToolBarImages::CopyImageToClipboard(int)

- ea: `0x180176330`
- end: `0x1801766cb`
- name: `?CopyImageToClipboard@CMFCToolBarImages@@QEAAHH@Z`
- size: `923`
- prototype: `int __fastcall(CMFCToolBarImages *this, int iImage)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18015dd80`

## callees

- `0x18001d090`
- `0x18006cab0`
- `0x180139950`
- `0x180173270`
- `0x1801734a0`
- `0x180173910`
- `0x180176330`
- `0x1801d7400`
- `0x18023d860`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802b0720`
- `0x1802b07d0`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!CloseClipboard` at `0x1801765bc`
- `USER32!CloseClipboard` at `0x180176655`
- `USER32!CloseClipboard` at `0x1801765bc`
- `USER32!CloseClipboard` at `0x180176655`
- `USER32!SetClipboardData` at `0x18017663a`
- `USER32!SetClipboardData` at `0x18017663a`
- `USER32!EmptyClipboard` at `0x1801765a2`
- `USER32!EmptyClipboard` at `0x1801765a2`
- `USER32!OpenClipboard` at `0x180176543`
- `USER32!OpenClipboard` at `0x180176543`
- `USER32!FillRect` at `0x180176494`
- `USER32!FillRect` at `0x180176494`
- `GDI32!DeleteDC` at `0x18017640f`
- `GDI32!DeleteDC` at `0x180176587`
- `GDI32!DeleteDC` at `0x1801765ec`
- `GDI32!DeleteDC` at `0x180176685`
- `GDI32!DeleteDC` at `0x18017640f`
- `GDI32!DeleteDC` at `0x180176587`
- `GDI32!DeleteDC` at `0x1801765ec`
- `GDI32!DeleteDC` at `0x180176685`
- `GDI32!CreateCompatibleBitmap` at `0x1801763be`
- `GDI32!CreateCompatibleBitmap` at `0x1801763be`
- `GDI32!SelectObject` at `0x180176434`
- `GDI32!SelectObject` at `0x18017650e`
- `GDI32!SelectObject` at `0x180176434`
- `GDI32!SelectObject` at `0x18017650e`
- `GDI32!CreateCompatibleDC` at `0x18017638b`
- `GDI32!CreateCompatibleDC` at `0x18017638b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall CMFCToolBarImages::CopyImageToClipboard(CMFCToolBarImages *this, int iImage)
{
  HDC CompatibleDC; // rdx
  HBITMAP CompatibleBitmap; // rdx
  HDC v6; // rax
  HGDIOBJ v7; // rcx
  CGdiObject *v8; // rdi
  int cy; // ecx
  int cx; // eax
  void *m_hObject; // rdx
  HGDIOBJ v12; // rax
  CWinThread *m_pCurrentWinThread; // rcx
  __int64 v14; // rax
  HDC v15; // rax
  HDC v16; // rax
  void *v18; // rbx
  CHandleMap *m_pmapHGDIOBJ; // rcx
  HDC v20; // rax
  CBitmap bitmapCopy; // [rsp+60h] [rbp-A8h] BYREF
  CDC memDCDest; // [rsp+70h] [rbp-98h] BYREF
  CWindowDC dc; // [rsp+90h] [rbp-78h] BYREF
  tagAFXDrawState v24; // [rsp+B8h] [rbp-50h] BYREF

  CWindowDC::CWindowDC(&dc, 0);
  memDCDest.__vftable = (CDC_vtbl *)CDC::`vftable';
  memset(&memDCDest.m_hDC, 0, 20);
  CompatibleDC = CreateCompatibleDC(0);
  CDC::Attach(&memDCDest, CompatibleDC);
  bitmapCopy.m_hObject = 0;
  bitmapCopy.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
  CompatibleBitmap = CreateCompatibleBitmap(dc.m_hDC, this->m_sizeImage.cx, this->m_sizeImage.cy);
  if ( !CGdiObject::Attach(&bitmapCopy, CompatibleBitmap) )
  {
    AfxMessageBox(0x3E8Au, 0, 0xFFFFFFFF);
    bitmapCopy.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
    CGdiObject::~CGdiObject(&bitmapCopy);
    memDCDest.__vftable = (CDC_vtbl *)CDC::`vftable';
    if ( memDCDest.m_hDC )
    {
      v6 = CDC::Detach(&memDCDest);
      DeleteDC(v6);
    }
LABEL_19:
    CWindowDC::~CWindowDC(&dc);
    return 0;
  }
  v7 = SelectObject(memDCDest.m_hDC, bitmapCopy.m_hObject);
  v8 = CGdiObject::FromHandle(v7);
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    afxGlobalData.m_bInitialized = 1;
  }
  cy = this->m_sizeImage.cy;
  cx = this->m_sizeImage.cx;
  v24.hbmMono = 0;
  v24.hbmMonoOld = (HBITMAP__ *)__PAIR64__(cy, cx);
  FillRect(memDCDest.m_hDC, (const RECT *)&v24, (HBRUSH)afxGlobalData.brBtnFace.m_hObject);
  v24.hbmMono = 0;
  CMFCToolBarImages::PrepareDrawImage(this, &v24, 0, 0);
  CMFCToolBarImages::Draw(this, &memDCDest, 0, 0, iImage, 0, 0, 0, 0, 0, 0xFFu);
  CMFCToolBarImages::EndDrawImage(this, &v24);
  m_hObject = 0;
  if ( v8 )
    m_hObject = v8->m_hObject;
  v12 = SelectObject(memDCDest.m_hDC, m_hObject);
  CGdiObject::FromHandle(v12);
  m_pCurrentWinThread = AfxGetModuleThreadState()->m_pCurrentWinThread;
  if ( m_pCurrentWinThread )
    v14 = (__int64)m_pCurrentWinThread->GetMainWnd(m_pCurrentWinThread);
  else
    v14 = 0;
  if ( !OpenClipboard(*(HWND *)(v14 + 64)) )
  {
    AfxMessageBox(0x3E8Au, 0, 0xFFFFFFFF);
    bitmapCopy.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
    CGdiObject::~CGdiObject(&bitmapCopy);
    memDCDest.__vftable = (CDC_vtbl *)CDC::`vftable';
    if ( memDCDest.m_hDC )
    {
      v15 = CDC::Detach(&memDCDest);
      DeleteDC(v15);
    }
    goto LABEL_19;
  }
  if ( !EmptyClipboard() )
  {
    AfxMessageBox(0x3E8Au, 0, 0xFFFFFFFF);
    CloseClipboard();
    bitmapCopy.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
    CGdiObject::~CGdiObject(&bitmapCopy);
    memDCDest.__vftable = (CDC_vtbl *)CDC::`vftable';
    if ( memDCDest.m_hDC )
    {
      v16 = CDC::Detach(&memDCDest);
      DeleteDC(v16);
    }
    goto LABEL_19;
  }
  v18 = bitmapCopy.m_hObject;
  if ( bitmapCopy.m_hObject )
  {
    m_pmapHGDIOBJ = AfxGetModuleThreadState()->m_pmapHGDIOBJ;
    if ( m_pmapHGDIOBJ )
      CMapPtrToWord::RemoveKey((CMapPtrToWord *)&m_pmapHGDIOBJ->m_permanentMap, bitmapCopy.m_hObject);
  }
  bitmapCopy.m_hObject = 0;
  if ( !SetClipboardData(2u, v18) )
    AfxMessageBox(0x3E8Au, 0, 0xFFFFFFFF);
  CloseClipboard();
  bitmapCopy.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
  CGdiObject::~CGdiObject(&bitmapCopy);
  memDCDest.__vftable = (CDC_vtbl *)CDC::`vftable';
  if ( memDCDest.m_hDC )
  {
    v20 = CDC::Detach(&memDCDest);
    DeleteDC(v20);
  }
  CWindowDC::~CWindowDC(&dc);
  return 1;
}

```

## disassembly

```asm
0x180176330  mov     r11, rsp
0x180176333  mov     [r11+18h], rbx
0x180176337  push    rsi
0x180176338  push    rdi
0x180176339  push    r12
0x18017633b  push    r14
0x18017633d  push    r15
0x18017633f  sub     rsp, 0E0h
0x180176346  mov     rax, cs:__security_cookie
0x18017634d  xor     rax, rsp
0x180176350  mov     [rsp+108h+var_38], rax
0x180176358  mov     esi, iImage
0x18017635a  mov     rbx, this
0x18017635d  xor     iImage, iImage; pWnd
0x18017635f  lea     this, [r11-78h]; this
0x180176363  call    ??0CWindowDC@@QEAA@PEAVCWnd@@@Z; CWindowDC::CWindowDC(CWnd *)
0x180176368  nop
0x180176369  lea     r15, ??_7CDC@@6B@; const CDC::`vftable'
0x180176370  mov     [rsp+108h+memDCDest.__vftable], r15
0x180176375  xorps   xmm0, xmm0
0x180176378  movdqu  xmmword ptr [rsp+108h+memDCDest.m_hDC], xmm0
0x18017637e  xor     r14d, r14d
0x180176381  mov     [rsp+108h+memDCDest.m_bPrinting], r14d
0x180176389  xor     ecx, ecx; hdc
0x18017638b  call    cs:__imp_CreateCompatibleDC
0x180176391  mov     rdx, rax; hDC
0x180176394  lea     this, [rsp+108h+memDCDest]; this
0x180176399  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x18017639e  mov     [rsp+108h+bitmapCopy.m_hObject], r14
0x1801763a3  lea     r12, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x1801763aa  mov     [rsp+108h+bitmapCopy.__vftable], r12
0x1801763af  mov     r8d, [rbx+6Ch]; cy
0x1801763b3  mov     iImage, [rbx+68h]; cx
0x1801763b6  mov     this, [rsp+108h+dc.m_hDC]; hdc
0x1801763be  call    cs:__imp_CreateCompatibleBitmap
0x1801763c4  mov     rdx, rax; hObject
0x1801763c7  lea     this, [rsp+108h+bitmapCopy]; this
0x1801763cc  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1801763d1  test    eax, eax
0x1801763d3  jnz     short loc_18017642A
0x1801763d5  or      r8d, 0FFFFFFFFh; nIDHelp
0x1801763d9  xor     iImage, iImage; nType
0x1801763db  mov     ecx, 3E8Ah; nIDPrompt
0x1801763e0  call    ?AfxMessageBox@@YAHIII@Z; AfxMessageBox(uint,uint,uint)
0x1801763e5  nop
0x1801763e6  mov     [rsp+108h+bitmapCopy.__vftable], r12
0x1801763eb  lea     this, [rsp+108h+bitmapCopy]; this
0x1801763f0  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1801763f5  nop
0x1801763f6  mov     [rsp+108h+memDCDest.__vftable], r15
0x1801763fb  cmp     [rsp+108h+memDCDest.m_hDC], r14
0x180176400  jz      short loc_180176416
0x180176402  lea     this, [rsp+108h+memDCDest]; this
0x180176407  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x18017640c  mov     this, rax; hdc
0x18017640f  call    cs:__imp_DeleteDC
0x180176415  nop
0x180176416  lea     this, [rsp+108h+dc]; this
0x18017641e  call    ??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x180176423  xor     eax, eax
0x180176425  jmp     loc_1801766A2
0x18017642a  mov     rdx, [rsp+108h+bitmapCopy.m_hObject]; h
0x18017642f  mov     this, [rsp+108h+memDCDest.m_hDC]; hdc
0x180176434  call    cs:__imp_SelectObject
0x18017643a  mov     this, rax; h
0x18017643d  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x180176442  mov     rdi, rax
0x180176445  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r14d; AFX_GLOBAL_DATA afxGlobalData ...
0x18017644c  jnz     short loc_180176464
0x18017644e  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180176455  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18017645a  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x180176464  mov     ecx, [rbx+6Ch]
0x180176467  mov     eax, [rbx+68h]
0x18017646a  mov     [rsp+108h+var_50.hbmMono], r14
0x180176472  mov     dword ptr [rsp+108h+var_50.hbmMonoOld], eax
0x180176479  mov     dword ptr [rsp+108h+var_50.hbmMonoOld+4], ecx
0x180176480  mov     r8, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.brBtnFace.m_hObject; hbr
0x180176487  lea     rdx, [rsp+108h+var_50]; lprc
0x18017648f  mov     this, [rsp+108h+memDCDest.m_hDC]; hDC
0x180176494  call    cs:__imp_FillRect
0x18017649a  mov     [rsp+108h+var_50.hbmMono], r14
0x1801764a2  xor     r9d, r9d; bFadeInactive
0x1801764a5  mov     r8, r14; sizeImageDest
0x1801764a8  lea     rdx, [rsp+108h+var_50]; ds
0x1801764b0  mov     this, rbx; this
0x1801764b3  call    ?PrepareDrawImage@CMFCToolBarImages@@QEAAHAEAUtagAFXDrawState@@VCSize@@H@Z; CMFCToolBarImages::PrepareDrawImage(tagAFXDrawState &,CSize,int)
0x1801764b8  mov     [rsp+108h+alphaSrc], 0FFh; alphaSrc
0x1801764bd  mov     [rsp+108h+bInactive], r14d; bInactive
0x1801764c2  mov     [rsp+108h+bShadow], r14d; bShadow
0x1801764c7  mov     [rsp+108h+bIndeterminate], r14d; bIndeterminate
0x1801764cc  mov     [rsp+108h+bDisabled], r14d; bDisabled
0x1801764d1  mov     [rsp+108h+bHilite], r14d; bHilite
0x1801764d6  mov     [rsp+108h+var_E8], esi; iImage
0x1801764da  xor     r9d, r9d; yDest
0x1801764dd  xor     r8d, r8d; xDest
0x1801764e0  lea     rdx, [rsp+108h+memDCDest]; pDCDest
0x1801764e5  mov     this, rbx; this
0x1801764e8  call    ?Draw@CMFCToolBarImages@@QEAAHPEAVCDC@@HHHHHHHHE@Z; CMFCToolBarImages::Draw(CDC *,int,int,int,int,int,int,int,int,uchar)
0x1801764ed  lea     rdx, [rsp+108h+var_50]; ds
0x1801764f5  mov     this, rbx; this
0x1801764f8  call    ?EndDrawImage@CMFCToolBarImages@@QEAAXAEAUtagAFXDrawState@@@Z; CMFCToolBarImages::EndDrawImage(tagAFXDrawState &)
0x1801764fd  test    rdi, rdi
0x180176500  mov     rdx, r14
0x180176503  jz      short loc_180176509
0x180176505  mov     rdx, [rdi+8]; h
0x180176509  mov     this, [rsp+108h+memDCDest.m_hDC]; hdc
0x18017650e  call    cs:__imp_SelectObject
0x180176514  mov     this, rax; h
0x180176517  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18017651c  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x180176521  mov     this, [rax+8]
0x180176525  test    this, this
0x180176528  jz      short loc_18017653C
0x18017652a  mov     rax, [this]
0x18017652d  mov     rax, [rax+0F8h]
0x180176534  call    cs:__guard_dispatch_icall_fptr
0x18017653a  jmp     short loc_18017653F
0x18017653c  mov     rax, r14
0x18017653f  mov     this, [rax+40h]; hWndNewOwner
0x180176543  call    cs:__imp_OpenClipboard
0x180176549  test    eax, eax
0x18017654b  jnz     short loc_1801765A2
0x18017654d  or      r8d, 0FFFFFFFFh; nIDHelp
0x180176551  xor     iImage, iImage; nType
0x180176553  mov     ecx, 3E8Ah; nIDPrompt
0x180176558  call    ?AfxMessageBox@@YAHIII@Z; AfxMessageBox(uint,uint,uint)
0x18017655d  nop
0x18017655e  mov     [rsp+108h+bitmapCopy.__vftable], r12
0x180176563  lea     this, [rsp+108h+bitmapCopy]; this
0x180176568  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18017656d  nop
0x18017656e  mov     [rsp+108h+memDCDest.__vftable], r15
0x180176573  cmp     [rsp+108h+memDCDest.m_hDC], r14
0x180176578  jz      short loc_18017658E
0x18017657a  lea     this, [rsp+108h+memDCDest]; this
0x18017657f  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180176584  mov     this, rax; hdc
0x180176587  call    cs:__imp_DeleteDC
0x18017658d  nop
0x18017658e  lea     this, [rsp+108h+dc]; this
0x180176596  call    ??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x18017659b  xor     eax, eax
0x18017659d  jmp     loc_1801766A2
0x1801765a2  call    cs:__imp_EmptyClipboard
0x1801765a8  test    eax, eax
0x1801765aa  jnz     short loc_180176607
0x1801765ac  or      r8d, 0FFFFFFFFh; nIDHelp
0x1801765b0  xor     iImage, iImage; nType
0x1801765b2  mov     ecx, 3E8Ah; nIDPrompt
0x1801765b7  call    ?AfxMessageBox@@YAHIII@Z; AfxMessageBox(uint,uint,uint)
0x1801765bc  call    cs:__imp_CloseClipboard
0x1801765c2  nop
0x1801765c3  mov     [rsp+108h+bitmapCopy.__vftable], r12
0x1801765c8  lea     this, [rsp+108h+bitmapCopy]; this
0x1801765cd  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1801765d2  nop
0x1801765d3  mov     [rsp+108h+memDCDest.__vftable], r15
0x1801765d8  cmp     [rsp+108h+memDCDest.m_hDC], r14
0x1801765dd  jz      short loc_1801765F3
0x1801765df  lea     this, [rsp+108h+memDCDest]; this
0x1801765e4  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1801765e9  mov     this, rax; hdc
0x1801765ec  call    cs:__imp_DeleteDC
0x1801765f2  nop
0x1801765f3  lea     this, [rsp+108h+dc]; this
0x1801765fb  call    ??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x180176600  xor     eax, eax
0x180176602  jmp     loc_1801766A2
0x180176607  mov     rbx, [rsp+108h+bitmapCopy.m_hObject]
0x18017660c  test    rbx, rbx
0x18017660f  jz      short loc_18017662D
0x180176611  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x180176616  mov     this, [rax+40h]
0x18017661a  test    this, this
0x18017661d  jz      short loc_18017662D
0x18017661f  add     this, 28h ; '('; this
0x180176623  mov     rdx, [rsp+108h+bitmapCopy.m_hObject]; key
0x180176628  call    ?RemoveKey@CMapPtrToWord@@QEAAHPEAX@Z; CMapPtrToWord::RemoveKey(void *)
0x18017662d  mov     [rsp+108h+bitmapCopy.m_hObject], r14
0x180176632  mov     rdx, rbx; hMem
0x180176635  mov     ecx, 2; uFormat
0x18017663a  call    cs:__imp_SetClipboardData
0x180176640  test    rax, rax
0x180176643  jnz     short loc_180176655
0x180176645  or      r8d, 0FFFFFFFFh; nIDHelp
0x180176649  xor     iImage, iImage; nType
0x18017664b  mov     ecx, 3E8Ah; nIDPrompt
0x180176650  call    ?AfxMessageBox@@YAHIII@Z; AfxMessageBox(uint,uint,uint)
0x180176655  call    cs:__imp_CloseClipboard
0x18017665b  nop
0x18017665c  mov     [rsp+108h+bitmapCopy.__vftable], r12
0x180176661  lea     this, [rsp+108h+bitmapCopy]; this
0x180176666  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18017666b  nop
0x18017666c  mov     [rsp+108h+memDCDest.__vftable], r15
0x180176671  cmp     [rsp+108h+memDCDest.m_hDC], r14
0x180176676  jz      short loc_18017668C
0x180176678  lea     this, [rsp+108h+memDCDest]; this
0x18017667d  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180176682  mov     this, rax; hdc
0x180176685  call    cs:__imp_DeleteDC
0x18017668b  nop
0x18017668c  lea     this, [rsp+108h+dc]; this
0x180176694  call    ??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x180176699  mov     eax, 1
0x18017669e  jmp     short loc_1801766A2
0x1801766a0  xor     eax, eax
0x1801766a2  mov     this, [rsp+108h+var_38]
0x1801766aa  xor     this, rsp; StackCookie
0x1801766ad  call    __security_check_cookie
0x1801766b2  mov     rbx, [rsp+108h+arg_10]
0x1801766ba  add     rsp, 0E0h
0x1801766c1  pop     r15
0x1801766c3  pop     r14
0x1801766c5  pop     r12
0x1801766c7  pop     rdi
0x1801766c8  pop     rsi
0x1801766c9  retn
```
