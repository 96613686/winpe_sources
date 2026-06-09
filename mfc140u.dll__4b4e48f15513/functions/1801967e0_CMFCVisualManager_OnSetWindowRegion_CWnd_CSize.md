# CMFCVisualManager::OnSetWindowRegion(CWnd *,CSize)

- ea: `0x1801967e0`
- end: `0x180196aae`
- name: `?OnSetWindowRegion@CMFCVisualManager@@UEAAHPEAVCWnd@@VCSize@@@Z`
- size: `718`
- prototype: `int __fastcall(CMFCVisualManager *this, CWnd *pWnd, CSize sizeWindow)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18001d090`
- `0x18006cab0`
- `0x18006e7b0`
- `0x180139950`
- `0x1801967e0`
- `0x18023d860`
- `0x18023f820`
- `0x1802b09d0`

## import_xrefs

- `USER32!SetWindowRgn` at `0x180196a70`
- `USER32!SetWindowRgn` at `0x180196a70`
- `USER32!IsWindowVisible` at `0x18019687a`
- `USER32!IsWindowVisible` at `0x18019687a`
- `GDI32!CreateEllipticRgn` at `0x180196940`
- `GDI32!CreateEllipticRgn` at `0x180196a11`
- `GDI32!CreateEllipticRgn` at `0x180196940`
- `GDI32!CreateEllipticRgn` at `0x180196a11`
- `GDI32!CombineRgn` at `0x1801968fd`
- `GDI32!CombineRgn` at `0x180196963`
- `GDI32!CombineRgn` at `0x1801969cc`
- `GDI32!CombineRgn` at `0x180196a34`
- `GDI32!CombineRgn` at `0x1801968fd`
- `GDI32!CombineRgn` at `0x180196963`
- `GDI32!CombineRgn` at `0x1801969cc`
- `GDI32!CombineRgn` at `0x180196a34`
- `GDI32!CreateRectRgn` at `0x1801968b0`
- `GDI32!CreateRectRgn` at `0x1801968da`
- `GDI32!CreateRectRgn` at `0x1801969a9`
- `GDI32!CreateRectRgn` at `0x1801968b0`
- `GDI32!CreateRectRgn` at `0x1801968da`
- `GDI32!CreateRectRgn` at `0x1801969a9`
- `GDI32!DeleteObject` at `0x18019692f`
- `GDI32!DeleteObject` at `0x180196995`
- `GDI32!DeleteObject` at `0x1801969fe`
- `GDI32!DeleteObject` at `0x18019692f`
- `GDI32!DeleteObject` at `0x180196995`
- `GDI32!DeleteObject` at `0x1801969fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CMFCVisualManager::OnSetWindowRegion(CMFCVisualManager *this, CWnd *pWnd, CSize sizeWindow)
{
  int cx; // ebx
  __int64 v5; // rdi
  HRGN RectRgn; // rax
  HRGN v7; // rax
  void *m_hObject; // rdi
  CHandleMap *m_pmapHGDIOBJ; // rcx
  HRGN EllipticRgn; // rax
  void *v11; // rdi
  CHandleMap *v12; // rcx
  HRGN v13; // rax
  void *v14; // rdi
  CHandleMap *v15; // rcx
  HRGN v16; // rax
  HRGN v17; // rbx
  CHandleMap *v18; // rcx
  CRgn rgnTemp; // [rsp+20h] [rbp-20h] BYREF
  CRgn rgnWnd; // [rsp+30h] [rbp-10h] BYREF
  int cy; // [rsp+74h] [rbp+34h]

  cy = sizeWindow.cy;
  cx = sizeWindow.cx;
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    afxGlobalData.m_bInitialized = 1;
  }
  if ( AFX_GLOBAL_DATA::IsDwmCompositionEnabled(&afxGlobalData) )
    return 0;
  if ( CObject::IsKindOf(pWnd, (const CRuntimeClass *)&CFrameImpl::`vftable'[1]) )
  {
    v5 = *(_QWORD *)&pWnd[3].m_nModalResult;
  }
  else
  {
    if ( !CObject::IsKindOf(pWnd, (const CRuntimeClass *)&CMDIChildWndEx::`vftable'[140]) )
      return 0;
    v5 = *(_QWORD *)&pWnd[7].m_nModalResult;
  }
  if ( !v5 || !IsWindowVisible(*(HWND *)(v5 + 64)) || !*(_DWORD *)(v5 + 1128) )
    return 0;
  rgnWnd.m_hObject = 0;
  rgnWnd.__vftable = (CRgn_vtbl *)CRgn::`vftable';
  RectRgn = CreateRectRgn(0, 0, cx, cy);
  CGdiObject::Attach(&rgnWnd, RectRgn);
  rgnTemp.m_hObject = 0;
  rgnTemp.__vftable = (CRgn_vtbl *)CRgn::`vftable';
  v7 = CreateRectRgn(0, 0, 5, 5);
  CGdiObject::Attach(&rgnTemp, v7);
  CombineRgn((HRGN)rgnWnd.m_hObject, (HRGN)rgnTemp.m_hObject, (HRGN)rgnWnd.m_hObject, 3);
  m_hObject = rgnTemp.m_hObject;
  if ( rgnTemp.m_hObject )
  {
    m_pmapHGDIOBJ = AfxGetModuleThreadState()->m_pmapHGDIOBJ;
    if ( m_pmapHGDIOBJ )
      CMapPtrToWord::RemoveKey((CMapPtrToWord *)&m_pmapHGDIOBJ->m_permanentMap, rgnTemp.m_hObject);
    rgnTemp.m_hObject = 0;
    DeleteObject(m_hObject);
  }
  EllipticRgn = CreateEllipticRgn(0, 0, 11, 11);
  CGdiObject::Attach(&rgnTemp, EllipticRgn);
  CombineRgn((HRGN)rgnWnd.m_hObject, (HRGN)rgnTemp.m_hObject, (HRGN)rgnWnd.m_hObject, 2);
  v11 = rgnTemp.m_hObject;
  if ( rgnTemp.m_hObject )
  {
    v12 = AfxGetModuleThreadState()->m_pmapHGDIOBJ;
    if ( v12 )
      CMapPtrToWord::RemoveKey((CMapPtrToWord *)&v12->m_permanentMap, rgnTemp.m_hObject);
    rgnTemp.m_hObject = 0;
    DeleteObject(v11);
  }
  v13 = CreateRectRgn(cx - 5, 0, cx, 5);
  CGdiObject::Attach(&rgnTemp, v13);
  CombineRgn((HRGN)rgnWnd.m_hObject, (HRGN)rgnTemp.m_hObject, (HRGN)rgnWnd.m_hObject, 3);
  v14 = rgnTemp.m_hObject;
  if ( rgnTemp.m_hObject )
  {
    v15 = AfxGetModuleThreadState()->m_pmapHGDIOBJ;
    if ( v15 )
      CMapPtrToWord::RemoveKey((CMapPtrToWord *)&v15->m_permanentMap, rgnTemp.m_hObject);
    rgnTemp.m_hObject = 0;
    DeleteObject(v14);
  }
  v16 = CreateEllipticRgn(cx - 10, 0, cx + 1, 11);
  CGdiObject::Attach(&rgnTemp, v16);
  CombineRgn((HRGN)rgnWnd.m_hObject, (HRGN)rgnTemp.m_hObject, (HRGN)rgnWnd.m_hObject, 2);
  v17 = (HRGN)rgnWnd.m_hObject;
  if ( rgnWnd.m_hObject )
  {
    v18 = AfxGetModuleThreadState()->m_pmapHGDIOBJ;
    if ( v18 )
      CMapPtrToWord::RemoveKey((CMapPtrToWord *)&v18->m_permanentMap, rgnWnd.m_hObject);
  }
  rgnWnd.m_hObject = 0;
  SetWindowRgn(pWnd->m_hWnd, v17, 1);
  rgnTemp.__vftable = (CRgn_vtbl *)CRgn::`vftable';
  CGdiObject::~CGdiObject(&rgnTemp);
  rgnWnd.__vftable = (CRgn_vtbl *)CRgn::`vftable';
  CGdiObject::~CGdiObject(&rgnWnd);
  return 1;
}

```

## disassembly

```asm
0x1801967e0  mov     [rsp-18h+arg_0], rbx
0x1801967e5  mov     [rsp-18h+arg_8], rsi
0x1801967ea  mov     qword ptr [rsp-18h+y2], sizeWindow
0x1801967ef  push    rbp
0x1801967f0  push    rdi
0x1801967f1  push    r12
0x1801967f3  mov     rbp, rsp
0x1801967f6  sub     rsp, 40h
0x1801967fa  mov     rbx, sizeWindow
0x1801967fd  mov     rsi, pWnd
0x180196800  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x180196807  jnz     short loc_18019681F
0x180196809  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180196810  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x180196815  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x18019681f  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180196826  call    ?IsDwmCompositionEnabled@AFX_GLOBAL_DATA@@QEAAHXZ; AFX_GLOBAL_DATA::IsDwmCompositionEnabled(void)
0x18019682b  test    eax, eax
0x18019682d  jnz     loc_180196A99
0x180196833  lea     pWnd, ??_7CFrameImpl@@6B@+8; pClass
0x18019683a  mov     this, rsi; this
0x18019683d  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x180196842  test    eax, eax
0x180196844  jz      short loc_18019684F
0x180196846  mov     rdi, [rsi+370h]
0x18019684d  jmp     short loc_18019686D
0x18019684f  lea     pWnd, ??_7CMDIChildWndEx@@6B@+460h; pClass
0x180196856  mov     this, rsi; this
0x180196859  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x18019685e  test    eax, eax
0x180196860  jz      loc_180196A99
0x180196866  mov     rdi, [rsi+710h]
0x18019686d  test    rdi, rdi
0x180196870  jz      loc_180196A99
0x180196876  mov     this, [rdi+40h]; hWnd
0x18019687a  call    cs:__imp_IsWindowVisible
0x180196880  test    eax, eax
0x180196882  jz      loc_180196A99
0x180196888  cmp     dword ptr [rdi+468h], 0
0x18019688f  jz      loc_180196A99
0x180196895  and     [rbp+rgnWnd.m_hObject], 0
0x18019689a  lea     r12, ??_7CRgn@@6B@; const CRgn::`vftable'
0x1801968a1  mov     [rbp+rgnWnd.__vftable], r12
0x1801968a5  mov     r9d, [rbp+34h]; y2
0x1801968a9  mov     r8d, ebx; x2
0x1801968ac  xor     edx, edx; y1
0x1801968ae  xor     ecx, ecx; x1
0x1801968b0  call    cs:__imp_CreateRectRgn
0x1801968b6  mov     pWnd, rax; hObject
0x1801968b9  lea     this, [rbp+rgnWnd]; this
0x1801968bd  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1801968c2  and     [rbp+rgnTemp.m_hObject], 0
0x1801968c7  mov     [rbp+rgnTemp.__vftable], r12
0x1801968cb  mov     eax, 5
0x1801968d0  mov     r9d, eax; y2
0x1801968d3  mov     r8d, eax; x2
0x1801968d6  xor     edx, edx; y1
0x1801968d8  xor     ecx, ecx; x1
0x1801968da  call    cs:__imp_CreateRectRgn
0x1801968e0  mov     pWnd, rax; hObject
0x1801968e3  lea     this, [rbp+rgnTemp]; this
0x1801968e7  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1801968ec  mov     r9d, 3; iMode
0x1801968f2  mov     this, [rbp+rgnWnd.m_hObject]; hrgnDst
0x1801968f6  mov     sizeWindow, this; hrgnSrc2
0x1801968f9  mov     pWnd, [rbp+rgnTemp.m_hObject]; hrgnSrc1
0x1801968fd  call    cs:__imp_CombineRgn
0x180196903  mov     rdi, [rbp+rgnTemp.m_hObject]
0x180196907  test    rdi, rdi
0x18019690a  jz      short loc_180196935
0x18019690c  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x180196911  mov     this, [rax+40h]
0x180196915  test    this, this
0x180196918  jz      short loc_180196927
0x18019691a  add     this, 28h ; '('; this
0x18019691e  mov     pWnd, [rbp+rgnTemp.m_hObject]; key
0x180196922  call    ?RemoveKey@CMapPtrToWord@@QEAAHPEAX@Z; CMapPtrToWord::RemoveKey(void *)
0x180196927  and     [rbp+rgnTemp.m_hObject], 0
0x18019692c  mov     this, rdi; ho
0x18019692f  call    cs:__imp_DeleteObject
0x180196935  xor     edx, edx; y1
0x180196937  xor     ecx, ecx; x1
0x180196939  lea     r9d, [pWnd+0Bh]; y2
0x18019693d  mov     r8d, r9d; x2
0x180196940  call    cs:__imp_CreateEllipticRgn
0x180196946  mov     pWnd, rax; hObject
0x180196949  lea     this, [rbp+rgnTemp]; this
0x18019694d  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x180196952  mov     r9d, 2; iMode
0x180196958  mov     this, [rbp+rgnWnd.m_hObject]; hrgnDst
0x18019695c  mov     sizeWindow, this; hrgnSrc2
0x18019695f  mov     pWnd, [rbp+rgnTemp.m_hObject]; hrgnSrc1
0x180196963  call    cs:__imp_CombineRgn
0x180196969  mov     rdi, [rbp+rgnTemp.m_hObject]
0x18019696d  test    rdi, rdi
0x180196970  jz      short loc_18019699B
0x180196972  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x180196977  mov     this, [rax+40h]
0x18019697b  test    this, this
0x18019697e  jz      short loc_18019698D
0x180196980  add     this, 28h ; '('; this
0x180196984  mov     pWnd, [rbp+rgnTemp.m_hObject]; key
0x180196988  call    ?RemoveKey@CMapPtrToWord@@QEAAHPEAX@Z; CMapPtrToWord::RemoveKey(void *)
0x18019698d  and     [rbp+rgnTemp.m_hObject], 0
0x180196992  mov     this, rdi; ho
0x180196995  call    cs:__imp_DeleteObject
0x18019699b  lea     ecx, [rbx-5]; x1
0x18019699e  mov     r9d, 5; y2
0x1801969a4  mov     r8d, ebx; x2
0x1801969a7  xor     edx, edx; y1
0x1801969a9  call    cs:__imp_CreateRectRgn
0x1801969af  mov     pWnd, rax; hObject
0x1801969b2  lea     this, [rbp+rgnTemp]; this
0x1801969b6  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1801969bb  mov     r9d, 3; iMode
0x1801969c1  mov     this, [rbp+rgnWnd.m_hObject]; hrgnDst
0x1801969c5  mov     sizeWindow, this; hrgnSrc2
0x1801969c8  mov     pWnd, [rbp+rgnTemp.m_hObject]; hrgnSrc1
0x1801969cc  call    cs:__imp_CombineRgn
0x1801969d2  mov     rdi, [rbp+rgnTemp.m_hObject]
0x1801969d6  test    rdi, rdi
0x1801969d9  jz      short loc_180196A04
0x1801969db  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x1801969e0  mov     this, [rax+40h]
0x1801969e4  test    this, this
0x1801969e7  jz      short loc_1801969F6
0x1801969e9  add     this, 28h ; '('; this
0x1801969ed  mov     pWnd, [rbp+rgnTemp.m_hObject]; key
0x1801969f1  call    ?RemoveKey@CMapPtrToWord@@QEAAHPEAX@Z; CMapPtrToWord::RemoveKey(void *)
0x1801969f6  and     [rbp+rgnTemp.m_hObject], 0
0x1801969fb  mov     this, rdi; ho
0x1801969fe  call    cs:__imp_DeleteObject
0x180196a04  lea     r8d, [rbx+1]; x2
0x180196a08  lea     ecx, [rbx-0Ah]; x1
0x180196a0b  xor     edx, edx; y1
0x180196a0d  lea     r9d, [pWnd+0Bh]; y2
0x180196a11  call    cs:__imp_CreateEllipticRgn
0x180196a17  mov     pWnd, rax; hObject
0x180196a1a  lea     this, [rbp+rgnTemp]; this
0x180196a1e  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x180196a23  mov     r9d, 2; iMode
0x180196a29  mov     this, [rbp+rgnWnd.m_hObject]; hrgnDst
0x180196a2d  mov     sizeWindow, this; hrgnSrc2
0x180196a30  mov     pWnd, [rbp+rgnTemp.m_hObject]; hrgnSrc1
0x180196a34  call    cs:__imp_CombineRgn
0x180196a3a  mov     rbx, [rbp+rgnWnd.m_hObject]
0x180196a3e  test    rbx, rbx
0x180196a41  jz      short loc_180196A5E
0x180196a43  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x180196a48  mov     this, [rax+40h]
0x180196a4c  test    this, this
0x180196a4f  jz      short loc_180196A5E
0x180196a51  add     this, 28h ; '('; this
0x180196a55  mov     pWnd, [rbp+rgnWnd.m_hObject]; key
0x180196a59  call    ?RemoveKey@CMapPtrToWord@@QEAAHPEAX@Z; CMapPtrToWord::RemoveKey(void *)
0x180196a5e  and     [rbp+rgnWnd.m_hObject], 0
0x180196a63  mov     r8d, 1; bRedraw
0x180196a69  mov     pWnd, rbx; hRgn
0x180196a6c  mov     this, [rsi+40h]; hWnd
0x180196a70  call    cs:__imp_SetWindowRgn
0x180196a76  nop
0x180196a77  mov     [rbp+rgnTemp.__vftable], r12
0x180196a7b  lea     this, [rbp+rgnTemp]; this
0x180196a7f  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180196a84  nop
0x180196a85  mov     [rbp+rgnWnd.__vftable], r12
0x180196a89  lea     this, [rbp+rgnWnd]; this
0x180196a8d  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180196a92  mov     eax, 1
0x180196a97  jmp     short loc_180196A9B
0x180196a99  xor     eax, eax
0x180196a9b  mov     rbx, [rsp+40h+arg_0]
0x180196aa0  mov     rsi, [rsp+40h+arg_8]
0x180196aa5  add     rsp, 40h
0x180196aa9  pop     r12
0x180196aab  pop     rdi
0x180196aac  pop     rbp
0x180196aad  retn
```
