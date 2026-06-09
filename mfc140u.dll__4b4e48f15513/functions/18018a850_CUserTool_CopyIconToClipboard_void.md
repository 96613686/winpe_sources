# CUserTool::CopyIconToClipboard(void)

- ea: `0x18018a850`
- end: `0x18018abe2`
- name: `?CopyIconToClipboard@CUserTool@@QEAAHXZ`
- size: `914`
- prototype: `int __fastcall(CUserTool *this)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18015dd80`

## callees

- `0x18001d090`
- `0x18006cab0`
- `0x180139950`
- `0x18018a770`
- `0x18018a850`
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

- `USER32!CloseClipboard` at `0x18018aac6`
- `USER32!CloseClipboard` at `0x18018ab65`
- `USER32!CloseClipboard` at `0x18018aac6`
- `USER32!CloseClipboard` at `0x18018ab65`
- `USER32!SetClipboardData` at `0x18018ab4a`
- `USER32!SetClipboardData` at `0x18018ab4a`
- `USER32!EmptyClipboard` at `0x18018aaac`
- `USER32!EmptyClipboard` at `0x18018aaac`
- `USER32!OpenClipboard` at `0x18018aa48`
- `USER32!OpenClipboard` at `0x18018aa48`
- `USER32!FillRect` at `0x18018a9ea`
- `USER32!FillRect` at `0x18018a9ea`
- `GDI32!DeleteDC` at `0x18018a96e`
- `GDI32!DeleteDC` at `0x18018aa94`
- `GDI32!DeleteDC` at `0x18018aafe`
- `GDI32!DeleteDC` at `0x18018ab9d`
- `GDI32!DeleteDC` at `0x18018a96e`
- `GDI32!DeleteDC` at `0x18018aa94`
- `GDI32!DeleteDC` at `0x18018aafe`
- `GDI32!DeleteDC` at `0x18018ab9d`
- `GDI32!CreateCompatibleBitmap` at `0x18018a91c`
- `GDI32!CreateCompatibleBitmap` at `0x18018a91c`
- `GDI32!SelectObject` at `0x18018a990`
- `GDI32!SelectObject` at `0x18018aa14`
- `GDI32!SelectObject` at `0x18018a990`
- `GDI32!SelectObject` at `0x18018aa14`
- `GDI32!CreateCompatibleDC` at `0x18018a8ed`
- `GDI32!CreateCompatibleDC` at `0x18018a8ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall CUserTool::CopyIconToClipboard(CUserTool *this)
{
  int m_bInitialized; // eax
  int cx; // esi
  int cy; // r14d
  HDC CompatibleDC; // rax
  HBITMAP CompatibleBitmap; // rax
  HDC v7; // rax
  HGDIOBJ v8; // rcx
  CGdiObject *v9; // rdi
  void *m_hObject; // rdx
  HGDIOBJ v11; // rax
  CWinThread *m_pCurrentWinThread; // rcx
  __int64 v13; // rax
  HDC v14; // rax
  HDC v15; // rax
  void *v17; // rdi
  CHandleMap *m_pmapHGDIOBJ; // rcx
  HDC v19; // rax
  CBitmap bitmapCopy; // [rsp+20h] [rbp-88h] BYREF
  CDC memDCDest; // [rsp+30h] [rbp-78h] BYREF
  CWindowDC dc; // [rsp+50h] [rbp-58h] BYREF
  CRect rectIcon; // [rsp+78h] [rbp-30h] BYREF

  CWindowDC::CWindowDC(&dc, 0);
  m_bInitialized = afxGlobalData.m_bInitialized;
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    m_bInitialized = 1;
    afxGlobalData.m_bInitialized = 1;
  }
  cx = afxGlobalData.m_sizeSmallIcon.cx;
  if ( !m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    afxGlobalData.m_bInitialized = 1;
  }
  cy = afxGlobalData.m_sizeSmallIcon.cy;
  memDCDest.__vftable = (CDC_vtbl *)CDC::`vftable';
  memset(&memDCDest.m_hDC, 0, 20);
  CompatibleDC = CreateCompatibleDC(0);
  CDC::Attach(&memDCDest, CompatibleDC);
  bitmapCopy.m_hObject = 0;
  bitmapCopy.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
  CompatibleBitmap = CreateCompatibleBitmap(dc.m_hDC, cx, cy);
  if ( !CGdiObject::Attach(&bitmapCopy, CompatibleBitmap) )
  {
    AfxMessageBox(0x3E8Au, 0, 0xFFFFFFFF);
    bitmapCopy.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
    CGdiObject::~CGdiObject(&bitmapCopy);
    memDCDest.__vftable = (CDC_vtbl *)CDC::`vftable';
    if ( memDCDest.m_hDC )
    {
      v7 = CDC::Detach(&memDCDest);
      DeleteDC(v7);
    }
LABEL_24:
    CWindowDC::~CWindowDC(&dc);
    return 0;
  }
  v8 = SelectObject(memDCDest.m_hDC, bitmapCopy.m_hObject);
  v9 = CGdiObject::FromHandle(v8);
  rectIcon.left = 0;
  rectIcon.top = 0;
  rectIcon.right = cx;
  rectIcon.bottom = cy;
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    afxGlobalData.m_bInitialized = 1;
  }
  FillRect(memDCDest.m_hDC, &rectIcon, (HBRUSH)afxGlobalData.brBtnFace.m_hObject);
  CUserTool::DrawToolIcon(this, &memDCDest, &rectIcon);
  if ( v9 )
    m_hObject = v9->m_hObject;
  else
    m_hObject = 0;
  v11 = SelectObject(memDCDest.m_hDC, m_hObject);
  CGdiObject::FromHandle(v11);
  m_pCurrentWinThread = AfxGetModuleThreadState()->m_pCurrentWinThread;
  if ( m_pCurrentWinThread )
    v13 = (__int64)m_pCurrentWinThread->GetMainWnd(m_pCurrentWinThread);
  else
    v13 = 0;
  if ( !OpenClipboard(*(HWND *)(v13 + 64)) )
  {
    AfxMessageBox(0x3E8Au, 0, 0xFFFFFFFF);
    bitmapCopy.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
    CGdiObject::~CGdiObject(&bitmapCopy);
    memDCDest.__vftable = (CDC_vtbl *)CDC::`vftable';
    if ( memDCDest.m_hDC )
    {
      v14 = CDC::Detach(&memDCDest);
      DeleteDC(v14);
    }
    goto LABEL_24;
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
      v15 = CDC::Detach(&memDCDest);
      DeleteDC(v15);
    }
    goto LABEL_24;
  }
  v17 = bitmapCopy.m_hObject;
  if ( bitmapCopy.m_hObject )
  {
    m_pmapHGDIOBJ = AfxGetModuleThreadState()->m_pmapHGDIOBJ;
    if ( m_pmapHGDIOBJ )
      CMapPtrToWord::RemoveKey((CMapPtrToWord *)&m_pmapHGDIOBJ->m_permanentMap, bitmapCopy.m_hObject);
  }
  bitmapCopy.m_hObject = 0;
  if ( !SetClipboardData(2u, v17) )
    AfxMessageBox(0x3E8Au, 0, 0xFFFFFFFF);
  CloseClipboard();
  bitmapCopy.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
  CGdiObject::~CGdiObject(&bitmapCopy);
  memDCDest.__vftable = (CDC_vtbl *)CDC::`vftable';
  if ( memDCDest.m_hDC )
  {
    v19 = CDC::Detach(&memDCDest);
    DeleteDC(v19);
  }
  CWindowDC::~CWindowDC(&dc);
  return 1;
}

```

## disassembly

```asm
0x18018a850  mov     [rsp+arg_8], rsi
0x18018a855  mov     [rsp+arg_10], rdi
0x18018a85a  push    r13
0x18018a85c  push    r14
0x18018a85e  push    r15
0x18018a860  sub     rsp, 90h
0x18018a867  mov     rax, cs:__security_cookie
0x18018a86e  xor     rax, rsp
0x18018a871  mov     [rsp+0A8h+var_20], rax
0x18018a879  mov     r15, this
0x18018a87c  xor     edx, edx; pWnd
0x18018a87e  lea     this, [rsp+0A8h+dc]; this
0x18018a883  call    ??0CWindowDC@@QEAA@PEAVCWnd@@@Z; CWindowDC::CWindowDC(CWnd *)
0x18018a888  nop
0x18018a889  mov     eax, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized; AFX_GLOBAL_DATA afxGlobalData ...
0x18018a88f  test    eax, eax
0x18018a891  jnz     short loc_18018A8AA
0x18018a893  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x18018a89a  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18018a89f  mov     eax, 1
0x18018a8a4  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, eax; AFX_GLOBAL_DATA afxGlobalData ...
0x18018a8aa  mov     esi, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_sizeSmallIcon.cx; AFX_GLOBAL_DATA afxGlobalData ...
0x18018a8b0  test    eax, eax
0x18018a8b2  jnz     short loc_18018A8CA
0x18018a8b4  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x18018a8bb  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18018a8c0  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x18018a8ca  mov     r14d, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_sizeSmallIcon.cy; AFX_GLOBAL_DATA afxGlobalData ...
0x18018a8d1  lea     r13, ??_7CDC@@6B@; const CDC::`vftable'
0x18018a8d8  mov     [rsp+0A8h+memDCDest.__vftable], r13
0x18018a8dd  xorps   xmm0, xmm0
0x18018a8e0  movdqu  xmmword ptr [rsp+0A8h+memDCDest.m_hDC], xmm0
0x18018a8e6  and     [rsp+0A8h+memDCDest.m_bPrinting], 0
0x18018a8eb  xor     ecx, ecx; hdc
0x18018a8ed  call    cs:__imp_CreateCompatibleDC
0x18018a8f3  mov     rdx, rax; hDC
0x18018a8f6  lea     this, [rsp+0A8h+memDCDest]; this
0x18018a8fb  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x18018a900  and     [rsp+0A8h+bitmapCopy.m_hObject], 0
0x18018a906  lea     rdi, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18018a90d  mov     [rsp+0A8h+bitmapCopy.__vftable], rdi
0x18018a912  mov     r8d, r14d; cy
0x18018a915  mov     edx, esi; cx
0x18018a917  mov     this, [rsp+0A8h+dc.m_hDC]; hdc
0x18018a91c  call    cs:__imp_CreateCompatibleBitmap
0x18018a922  mov     rdx, rax; hObject
0x18018a925  lea     this, [rsp+0A8h+bitmapCopy]; this
0x18018a92a  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x18018a92f  test    eax, eax
0x18018a931  jnz     short loc_18018A986
0x18018a933  or      r8d, 0FFFFFFFFh; nIDHelp
0x18018a937  xor     edx, edx; nType
0x18018a939  mov     ecx, 3E8Ah; nIDPrompt
0x18018a93e  call    ?AfxMessageBox@@YAHIII@Z; AfxMessageBox(uint,uint,uint)
0x18018a943  nop
0x18018a944  mov     [rsp+0A8h+bitmapCopy.__vftable], rdi
0x18018a949  lea     this, [rsp+0A8h+bitmapCopy]; this
0x18018a94e  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18018a953  nop
0x18018a954  mov     [rsp+0A8h+memDCDest.__vftable], r13
0x18018a959  cmp     [rsp+0A8h+memDCDest.m_hDC], 0
0x18018a95f  jz      short loc_18018A975
0x18018a961  lea     this, [rsp+0A8h+memDCDest]; this
0x18018a966  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x18018a96b  mov     this, rax; hdc
0x18018a96e  call    cs:__imp_DeleteDC
0x18018a974  nop
0x18018a975  lea     this, [rsp+0A8h+dc]; this
0x18018a97a  call    ??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x18018a97f  xor     eax, eax
0x18018a981  jmp     loc_18018ABB7
0x18018a986  mov     rdx, [rsp+0A8h+bitmapCopy.m_hObject]; h
0x18018a98b  mov     this, [rsp+0A8h+memDCDest.m_hDC]; hdc
0x18018a990  call    cs:__imp_SelectObject
0x18018a996  mov     this, rax; h
0x18018a999  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18018a99e  mov     rdi, rax
0x18018a9a1  and     [rsp+0A8h+rectIcon.left], 0
0x18018a9a6  and     [rsp+0A8h+rectIcon.top], 0
0x18018a9ab  mov     [rsp+0A8h+rectIcon.right], esi
0x18018a9b2  mov     [rsp+0A8h+rectIcon.bottom], r14d
0x18018a9ba  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x18018a9c1  jnz     short loc_18018A9D9
0x18018a9c3  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x18018a9ca  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18018a9cf  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x18018a9d9  mov     r8, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.brBtnFace.m_hObject; hbr
0x18018a9e0  lea     rdx, [rsp+0A8h+rectIcon]; lprc
0x18018a9e5  mov     this, [rsp+0A8h+memDCDest.m_hDC]; hDC
0x18018a9ea  call    cs:__imp_FillRect
0x18018a9f0  lea     r8, [rsp+0A8h+rectIcon]; rectImage
0x18018a9f5  lea     rdx, [rsp+0A8h+memDCDest]; pDC
0x18018a9fa  mov     this, r15; this
0x18018a9fd  call    ?DrawToolIcon@CUserTool@@QEAAXPEAVCDC@@AEBVCRect@@@Z; CUserTool::DrawToolIcon(CDC *,CRect const &)
0x18018aa02  test    rdi, rdi
0x18018aa05  jnz     short loc_18018AA0B
0x18018aa07  xor     edx, edx
0x18018aa09  jmp     short loc_18018AA0F
0x18018aa0b  mov     rdx, [rdi+8]; h
0x18018aa0f  mov     this, [rsp+0A8h+memDCDest.m_hDC]; hdc
0x18018aa14  call    cs:__imp_SelectObject
0x18018aa1a  mov     this, rax; h
0x18018aa1d  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18018aa22  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x18018aa27  mov     this, [rax+8]
0x18018aa2b  test    this, this
0x18018aa2e  jz      short loc_18018AA42
0x18018aa30  mov     rax, [this]
0x18018aa33  mov     rax, [rax+0F8h]
0x18018aa3a  call    cs:__guard_dispatch_icall_fptr
0x18018aa40  jmp     short loc_18018AA44
0x18018aa42  xor     eax, eax
0x18018aa44  mov     this, [rax+40h]; hWndNewOwner
0x18018aa48  call    cs:__imp_OpenClipboard
0x18018aa4e  test    eax, eax
0x18018aa50  jnz     short loc_18018AAAC
0x18018aa52  or      r8d, 0FFFFFFFFh; nIDHelp
0x18018aa56  xor     edx, edx; nType
0x18018aa58  mov     ecx, 3E8Ah; nIDPrompt
0x18018aa5d  call    ?AfxMessageBox@@YAHIII@Z; AfxMessageBox(uint,uint,uint)
0x18018aa62  nop
0x18018aa63  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18018aa6a  mov     [rsp+0A8h+bitmapCopy.__vftable], rax
0x18018aa6f  lea     this, [rsp+0A8h+bitmapCopy]; this
0x18018aa74  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18018aa79  nop
0x18018aa7a  mov     [rsp+0A8h+memDCDest.__vftable], r13
0x18018aa7f  cmp     [rsp+0A8h+memDCDest.m_hDC], 0
0x18018aa85  jz      short loc_18018AA9B
0x18018aa87  lea     this, [rsp+0A8h+memDCDest]; this
0x18018aa8c  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x18018aa91  mov     this, rax; hdc
0x18018aa94  call    cs:__imp_DeleteDC
0x18018aa9a  nop
0x18018aa9b  lea     this, [rsp+0A8h+dc]; this
0x18018aaa0  call    ??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x18018aaa5  xor     eax, eax
0x18018aaa7  jmp     loc_18018ABB7
0x18018aaac  call    cs:__imp_EmptyClipboard
0x18018aab2  test    eax, eax
0x18018aab4  jnz     short loc_18018AB16
0x18018aab6  or      r8d, 0FFFFFFFFh; nIDHelp
0x18018aaba  xor     edx, edx; nType
0x18018aabc  mov     ecx, 3E8Ah; nIDPrompt
0x18018aac1  call    ?AfxMessageBox@@YAHIII@Z; AfxMessageBox(uint,uint,uint)
0x18018aac6  call    cs:__imp_CloseClipboard
0x18018aacc  nop
0x18018aacd  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18018aad4  mov     [rsp+0A8h+bitmapCopy.__vftable], rax
0x18018aad9  lea     this, [rsp+0A8h+bitmapCopy]; this
0x18018aade  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18018aae3  nop
0x18018aae4  mov     [rsp+0A8h+memDCDest.__vftable], r13
0x18018aae9  cmp     [rsp+0A8h+memDCDest.m_hDC], 0
0x18018aaef  jz      short loc_18018AB05
0x18018aaf1  lea     this, [rsp+0A8h+memDCDest]; this
0x18018aaf6  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x18018aafb  mov     this, rax; hdc
0x18018aafe  call    cs:__imp_DeleteDC
0x18018ab04  nop
0x18018ab05  lea     this, [rsp+0A8h+dc]; this
0x18018ab0a  call    ??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x18018ab0f  xor     eax, eax
0x18018ab11  jmp     loc_18018ABB7
0x18018ab16  mov     rdi, [rsp+0A8h+bitmapCopy.m_hObject]
0x18018ab1b  test    rdi, rdi
0x18018ab1e  jz      short loc_18018AB3C
0x18018ab20  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x18018ab25  mov     this, [rax+40h]
0x18018ab29  test    this, this
0x18018ab2c  jz      short loc_18018AB3C
0x18018ab2e  add     this, 28h ; '('; this
0x18018ab32  mov     rdx, [rsp+0A8h+bitmapCopy.m_hObject]; key
0x18018ab37  call    ?RemoveKey@CMapPtrToWord@@QEAAHPEAX@Z; CMapPtrToWord::RemoveKey(void *)
0x18018ab3c  and     [rsp+0A8h+bitmapCopy.m_hObject], 0
0x18018ab42  mov     rdx, rdi; hMem
0x18018ab45  mov     ecx, 2; uFormat
0x18018ab4a  call    cs:__imp_SetClipboardData
0x18018ab50  test    rax, rax
0x18018ab53  jnz     short loc_18018AB65
0x18018ab55  or      r8d, 0FFFFFFFFh; nIDHelp
0x18018ab59  xor     edx, edx; nType
0x18018ab5b  mov     ecx, 3E8Ah; nIDPrompt
0x18018ab60  call    ?AfxMessageBox@@YAHIII@Z; AfxMessageBox(uint,uint,uint)
0x18018ab65  call    cs:__imp_CloseClipboard
0x18018ab6b  nop
0x18018ab6c  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18018ab73  mov     [rsp+0A8h+bitmapCopy.__vftable], rax
0x18018ab78  lea     this, [rsp+0A8h+bitmapCopy]; this
0x18018ab7d  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18018ab82  nop
0x18018ab83  mov     [rsp+0A8h+memDCDest.__vftable], r13
0x18018ab88  cmp     [rsp+0A8h+memDCDest.m_hDC], 0
0x18018ab8e  jz      short loc_18018ABA4
0x18018ab90  lea     this, [rsp+0A8h+memDCDest]; this
0x18018ab95  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x18018ab9a  mov     this, rax; hdc
0x18018ab9d  call    cs:__imp_DeleteDC
0x18018aba3  nop
0x18018aba4  lea     this, [rsp+0A8h+dc]; this
0x18018aba9  call    ??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x18018abae  mov     eax, 1
0x18018abb3  jmp     short loc_18018ABB7
0x18018abb5  xor     eax, eax
0x18018abb7  mov     this, [rsp+0A8h+var_20]
0x18018abbf  xor     this, rsp; StackCookie
0x18018abc2  call    __security_check_cookie
0x18018abc7  lea     r11, [rsp+0A8h+var_18]
0x18018abcf  mov     rsi, [r11+28h]
0x18018abd3  mov     rdi, [r11+30h]
0x18018abd7  mov     rsp, r11
0x18018abda  pop     r15
0x18018abdc  pop     r14
0x18018abde  pop     r13
0x18018abe0  retn
```
