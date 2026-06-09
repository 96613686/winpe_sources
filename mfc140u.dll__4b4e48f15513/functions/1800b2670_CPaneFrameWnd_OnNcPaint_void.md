# CPaneFrameWnd::OnNcPaint(void)

- ea: `0x1800b2670`
- end: `0x1800b2c25`
- name: `?OnNcPaint@CPaneFrameWnd@@IEAAXXZ`
- size: `1461`
- prototype: `void __fastcall(CPaneFrameWnd *this)`
- caller_count: `2`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800b9f60`
- `0x180152bc0`

## callees

- `0x180009844`
- `0x18001d090`
- `0x18006cab0`
- `0x18006f0f0`
- `0x1800b2670`
- `0x180296c00`
- `0x180296d50`
- `0x1802aee60`
- `0x1802aef40`
- `0x1802af260`
- `0x1802af8a0`
- `0x1802af990`
- `0x1802afe10`
- `0x1802b0720`
- `0x1802b07d0`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!GetClientRect` at `0x1800b27ed`
- `USER32!GetClientRect` at `0x1800b27ed`
- `USER32!SetRectEmpty` at `0x1800b28d0`
- `USER32!SetRectEmpty` at `0x1800b28d0`
- `USER32!GetWindowRect` at `0x1800b2731`
- `USER32!GetWindowRect` at `0x1800b27df`
- `USER32!GetWindowRect` at `0x1800b2731`
- `USER32!GetWindowRect` at `0x1800b27df`
- `USER32!SetRect` at `0x1800b275a`
- `USER32!SetRect` at `0x1800b275a`
- `USER32!IsRectEmpty` at `0x1800b283d`
- `USER32!IsRectEmpty` at `0x1800b283d`
- `USER32!InflateRect` at `0x1800b2a8a`
- `USER32!InflateRect` at `0x1800b2a8a`
- `USER32!OffsetRect` at `0x1800b280f`
- `USER32!OffsetRect` at `0x1800b280f`
- `GDI32!CreateRectRgnIndirect` at `0x1800b284a`
- `GDI32!CreateRectRgnIndirect` at `0x1800b284a`
- `GDI32!BitBlt` at `0x1800b2b5d`
- `GDI32!BitBlt` at `0x1800b2b5d`
- `GDI32!CreateCompatibleBitmap` at `0x1800b278c`
- `GDI32!CreateCompatibleBitmap` at `0x1800b278c`
- `GDI32!SelectObject` at `0x1800b27b4`
- `GDI32!SelectObject` at `0x1800b2b74`
- `GDI32!SelectObject` at `0x1800b27b4`
- `GDI32!SelectObject` at `0x1800b2b74`
- `GDI32!CreateCompatibleDC` at `0x1800b2764`
- `GDI32!CreateCompatibleDC` at `0x1800b2764`
- `GDI32!GetClipBox` at `0x1800b2b06`
- `GDI32!GetClipBox` at `0x1800b2b06`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=5
void __fastcall CPaneFrameWnd::OnNcPaint(CPaneFrameWnd *this)
{
  CDockingManager *m_pDockManager; // rax
  CWnd *v3; // rax
  HDC__ **p_m_hDC; // r14
  CGdiObject *v5; // r13
  HDC CompatibleDC; // rax
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v8; // rax
  HRGN RectRgnIndirect; // rax
  CDockingManager *DockingManager; // rax
  CWnd *v11; // rax
  CMFCVisualManager *Instance; // r10
  unsigned int (__fastcall *OnFillMiniFrameCaption)(CMFCVisualManager *, CDC *, CRect, CPaneFrameWnd *, int); // rax
  int m_bActive; // ecx
  unsigned int v15; // eax
  int v16; // r12d
  int v17; // esi
  CObList::CNode *m_pNodeHead; // r15
  CObject *data; // rbx
  CRuntimeClass *(__fastcall *GetRuntimeClass)(CObject *); // rax
  CObject *v21; // rcx
  __int64 v22; // rax
  char *v23; // rdx
  __int64 (__fastcall *v24)(HDC__ **, CFont *); // rbx
  __int64 v25; // rbx
  int v26; // eax
  int v27; // eax
  int ClipBox; // eax
  void *m_hObject; // rdx
  HGDIOBJ v30; // rax
  void (__fastcall **p_Serialize)(CObject *, CArchive *); // rdx
  unsigned int strCaption; // [rsp+58h] [rbp-B0h]
  int strCaption_4; // [rsp+5Ch] [rbp-ACh]
  CRgn rgn; // [rsp+60h] [rbp-A8h] BYREF
  CBitmap bmp; // [rsp+70h] [rbp-98h] BYREF
  CDC dcMem; // [rsp+80h] [rbp-88h] BYREF
  CWindowDC dc; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE rectClip_8[112]; // [rsp+D8h] [rbp-30h] OVERLAPPED BYREF
  char v39[16]; // [rsp+148h] [rbp+40h] BYREF
  char v40[16]; // [rsp+158h] [rbp+50h] BYREF
  char v41; // [rsp+168h] [rbp+60h] BYREF
  char v42[16]; // [rsp+178h] [rbp+70h] BYREF
  char v43; // [rsp+188h] [rbp+80h] BYREF

  m_pDockManager = this->m_pDockManager;
  if ( !m_pDockManager )
  {
    v3 = CWnd::FromHandlePermanent(this->m_hParentWnd);
    m_pDockManager = CGlobalUtils::GetDockingManager(&afxGlobalUtils, v3);
    if ( !m_pDockManager )
      return;
  }
  if ( m_pDockManager->m_bLockUpdate )
    return;
  CWindowDC::CWindowDC((CWindowDC *)&dc.m_hDC, this);
  p_m_hDC = &dc.m_hDC;
  strCaption_4 = 0;
  dcMem.m_hDC = (HDC__ *)CDC::`vftable';
  *(_OWORD *)&dcMem.m_hAttribDC = 0;
  LODWORD(dc.__vftable) = 0;
  dcMem.__vftable = 0;
  bmp.m_hObject = (void *)CBitmap::`vftable';
  v5 = 0;
  *(_OWORD *)&rectClip_8[32] = 0;
  GetWindowRect(this->m_hWnd, (LPRECT)&rectClip_8[32]);
  *(_OWORD *)&rectClip_8[16] = 0;
  SetRect(
    (LPRECT)&rectClip_8[16],
    0,
    0,
    *(_DWORD *)&rectClip_8[40] - *(_DWORD *)&rectClip_8[32],
    *(_DWORD *)&rectClip_8[44] - *(_DWORD *)&rectClip_8[36]);
  CompatibleDC = CreateCompatibleDC(dc.m_hAttribDC);
  if ( CDC::Attach((CDC *)&dcMem.m_hDC, CompatibleDC) )
  {
    CompatibleBitmap = CreateCompatibleBitmap(
                         dc.m_hAttribDC,
                         *(_DWORD *)&rectClip_8[24] - *(_DWORD *)&rectClip_8[16],
                         *(_DWORD *)&rectClip_8[28] - *(_DWORD *)&rectClip_8[20]);
    if ( CGdiObject::Attach((CGdiObject *)&bmp.m_hObject, CompatibleBitmap) )
    {
      strCaption_4 = 1;
      v8 = SelectObject(dcMem.m_hAttribDC, dcMem.__vftable);
      v5 = CGdiObject::FromHandle(v8);
      p_m_hDC = &dcMem.m_hDC;
    }
  }
  memset(&rectClip_8[80], 0, 32);
  GetWindowRect(this->m_hWnd, (LPRECT)&rectClip_8[96]);
  GetClientRect(this->m_hWnd, (LPRECT)&rectClip_8[80]);
  CWnd::ClientToScreen(this, (tagRECT *)&rectClip_8[80]);
  OffsetRect((LPRECT)&rectClip_8[80], -*(_DWORD *)&rectClip_8[96], -*(_DWORD *)&rectClip_8[100]);
  CDC::ExcludeClipRect((CDC *)&dc.m_hDC, (const tagRECT *)&rectClip_8[80]);
  bmp.__vftable = 0;
  rgn.m_hObject = (void *)CRgn::`vftable';
  if ( !IsRectEmpty(&this->m_rectRedraw) )
  {
    RectRgnIndirect = CreateRectRgnIndirect(&this->m_rectRedraw);
    CGdiObject::Attach((CGdiObject *)&rgn.m_hObject, RectRgnIndirect);
    CDC::SelectClipRgn((CDC *)&dc.m_hDC, (CRgn *)&rgn.m_hObject);
  }
  this->OnDrawBorder(this, (CDC *)p_m_hDC);
  *(_OWORD *)&rectClip_8[48] = 0;
  this->GetCaptionRect(this, (CRect *)&rectClip_8[48]);
  DockingManager = this->m_pDockManager;
  if ( !DockingManager )
  {
    v11 = CWnd::FromHandlePermanent(this->m_hParentWnd);
    DockingManager = CGlobalUtils::GetDockingManager(&afxGlobalUtils, v11);
  }
  if ( DockingManager->m_bLockUpdate )
    SetRectEmpty((LPRECT)&rectClip_8[48]);
  this->GetCaptionRect(this, (CRect *)&rectClip_8[48]);
  Instance = CMFCVisualManager::GetInstance();
  OnFillMiniFrameCaption = Instance->OnFillMiniFrameCaption;
  m_bActive = this->m_bActive;
  *(_OWORD *)rectClip_8 = *(_OWORD *)&rectClip_8[48];
  v15 = ((__int64 (__fastcall *)(CMFCVisualManager *, HDC__ **, _BYTE *, CPaneFrameWnd *, int))OnFillMiniFrameCaption)(
          Instance,
          p_m_hDC,
          rectClip_8,
          this,
          m_bActive);
  strCaption = v15;
  v16 = -1;
  v17 = -1;
  m_pNodeHead = this->m_lstCaptionButtons.m_pNodeHead;
  while ( m_pNodeHead )
  {
    data = m_pNodeHead->data;
    m_pNodeHead = m_pNodeHead->pNext;
    HIDWORD(data[4].__vftable) = v15;
    if ( !LODWORD(data[2].__vftable) )
    {
      GetRuntimeClass = data->__vftable[1].GetRuntimeClass;
      v21 = data;
      if ( HIDWORD(data[3].__vftable) )
      {
        if ( v17 == -1 )
        {
          v22 = ((__int64 (__fastcall *)(CObject *, _BYTE *))GetRuntimeClass)(data, rectClip_8);
LABEL_18:
          v17 = *(_DWORD *)(v22 + 8) + 2;
          goto LABEL_26;
        }
        if ( v17 <= *(_DWORD *)(((__int64 (__fastcall *)(CObject *, char *))GetRuntimeClass)(data, v39) + 8) + 2 )
        {
          v22 = ((__int64 (__fastcall *)(CObject *, char *))data->__vftable[1].GetRuntimeClass)(data, v40);
          goto LABEL_18;
        }
      }
      else
      {
        if ( v16 == -1 )
        {
          v23 = &v41;
        }
        else
        {
          if ( v16 < *(_DWORD *)((__int64 (__fastcall *)(CObject *, char *))GetRuntimeClass)(data, v42) )
            goto LABEL_26;
          v23 = &v43;
          v21 = data;
          GetRuntimeClass = data->__vftable[1].GetRuntimeClass;
        }
        v16 = *(_DWORD *)((__int64 (__fastcall *)(CObject *, char *))GetRuntimeClass)(v21, v23);
      }
LABEL_26:
      v15 = strCaption;
    }
  }
  CDC::SetBkMode((CDC *)p_m_hDC, 1);
  (*((void (__fastcall **)(HDC__ **, _QWORD))*p_m_hDC + 14))(p_m_hDC, strCaption);
  v24 = (__int64 (__fastcall *)(HDC__ **, CFont *))*((_QWORD *)*p_m_hDC + 12);
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    afxGlobalData.m_bInitialized = 1;
  }
  v25 = v24(p_m_hDC, &afxGlobalData.fontBold);
  this->GetCaptionText(this, (ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *)&rgn);
  *(_OWORD *)&rectClip_8[64] = *(_OWORD *)&rectClip_8[48];
  v26 = _mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)&rectClip_8[48], 8));
  if ( v16 != -1 )
    v26 = v16;
  *(_DWORD *)&rectClip_8[72] = v26;
  v27 = *(_DWORD *)&rectClip_8[64];
  if ( v17 != -1 )
    v27 = v17;
  *(_DWORD *)&rectClip_8[64] = v27;
  InflateRect((LPRECT)&rectClip_8[64], -2, 0);
  (*((void (__fastcall **)(HDC__ **, CRgn_vtbl *, _QWORD, _BYTE *, int))*p_m_hDC + 28))(
    p_m_hDC,
    rgn.__vftable,
    LODWORD(rgn.__vftable[-1].AssertValid),
    &rectClip_8[64],
    32804);
  (*((void (__fastcall **)(HDC__ **, __int64))*p_m_hDC + 12))(p_m_hDC, v25);
  CDC::SelectClipRgn((CDC *)p_m_hDC, 0);
  this->OnDrawCaptionButtons(this, (CDC *)p_m_hDC);
  if ( strCaption_4 )
  {
    *(_OWORD *)rectClip_8 = 0;
    ClipBox = GetClipBox(dc.m_hAttribDC, (LPRECT)rectClip_8);
    if ( ClipBox != 1 )
    {
      if ( ClipBox != 2 )
        *(_OWORD *)rectClip_8 = *(_OWORD *)&rectClip_8[16];
      BitBlt(
        dc.m_hAttribDC,
        *(int *)rectClip_8,
        *(int *)&rectClip_8[4],
        *(_DWORD *)&rectClip_8[8] - *(_DWORD *)rectClip_8,
        *(_DWORD *)&rectClip_8[12] - *(_DWORD *)&rectClip_8[4],
        dcMem.m_hAttribDC,
        *(int *)rectClip_8,
        *(int *)&rectClip_8[4],
        0xCC0020u);
    }
    if ( v5 )
      m_hObject = v5->m_hObject;
    else
      m_hObject = 0;
    v30 = SelectObject(dcMem.m_hAttribDC, m_hObject);
    CGdiObject::FromHandle(v30);
  }
  CWnd::Default(this);
  p_Serialize = &rgn.__vftable[-1].Serialize;
  if ( _InterlockedDecrement((volatile signed __int32 *)&rgn.__vftable[-1].Dump) <= 0 )
    (*(void (__fastcall **)(void (__fastcall *)(CObject *, CArchive *)))(*(_QWORD *)*p_Serialize + 8LL))(*p_Serialize);
  rgn.m_hObject = (void *)CRgn::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)&rgn.m_hObject);
  bmp.m_hObject = (void *)CBitmap::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)&bmp.m_hObject);
  CDC::~CDC((CDC *)&dcMem.m_hDC);
  CWindowDC::~CWindowDC((CWindowDC *)&dc.m_hDC);
}

```

## disassembly

```asm
0x1800b2670  mov     rax, rsp
0x1800b2673  mov     [rax+10h], rbx
0x1800b2677  mov     [rax+18h], rsi
0x1800b267b  mov     [rax+20h], rdi
0x1800b267f  push    rbp
0x1800b2680  push    r12
0x1800b2682  push    r13
0x1800b2684  push    r14
0x1800b2686  push    r15
0x1800b2688  lea     rbp, [rax-0C8h]
0x1800b268f  sub     rsp, 1A0h
0x1800b2696  mov     rax, cs:__security_cookie
0x1800b269d  xor     rax, rsp
0x1800b26a0  mov     [rbp+0C0h+var_30], rax
0x1800b26a7  mov     rdi, this
0x1800b26aa  mov     rax, [this+248h]
0x1800b26b1  xor     esi, esi
0x1800b26b3  test    rax, rax
0x1800b26b6  jnz     short loc_1800B26DC
0x1800b26b8  mov     this, [this+130h]; hWnd
0x1800b26bf  call    ?FromHandlePermanent@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandlePermanent(HWND__ *)
0x1800b26c4  mov     rdx, rax; pWnd
0x1800b26c7  lea     this, ?afxGlobalUtils@@3VCGlobalUtils@@A; this
0x1800b26ce  call    ?GetDockingManager@CGlobalUtils@@QEAAPEAVCDockingManager@@PEAVCWnd@@@Z; CGlobalUtils::GetDockingManager(CWnd *)
0x1800b26d3  test    rax, rax
0x1800b26d6  jz      loc_1800B2BF5
0x1800b26dc  cmp     [rax+0Ch], esi
0x1800b26df  jnz     loc_1800B2BF5
0x1800b26e5  mov     rdx, rdi; pWnd
0x1800b26e8  lea     this, [rbp+0C0h+dc.m_hDC]; this
0x1800b26ec  call    ??0CWindowDC@@QEAA@PEAVCWnd@@@Z; CWindowDC::CWindowDC(CWnd *)
0x1800b26f1  nop
0x1800b26f2  lea     r14, [rbp+0C0h+dc.m_hDC]
0x1800b26f6  mov     dword ptr [rsp+1C0h+strCaption.m_pszData+4], esi
0x1800b26fa  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x1800b2701  mov     [rbp+0C0h+dcMem.m_hDC], rax
0x1800b2705  xorps   xmm0, xmm0
0x1800b2708  movdqu  xmmword ptr [rbp+0C0h+dcMem.m_hAttribDC], xmm0
0x1800b270d  mov     dword ptr [rbp+0C0h+dc.__vftable], esi
0x1800b2710  mov     [rsp+1C0h+dcMem.__vftable], rsi
0x1800b2715  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x1800b271c  mov     [rsp+1C0h+bmp.m_hObject], rax
0x1800b2721  mov     r13, rsi
0x1800b2724  movdqu  xmmword ptr [rbp+0C0h+rectWindow.right], xmm0
0x1800b2729  lea     rdx, [rbp+0C0h+rectWindow.right]; lpRect
0x1800b272d  mov     this, [rdi+40h]; hWnd
0x1800b2731  call    cs:__imp_GetWindowRect
0x1800b2737  xorps   xmm0, xmm0
0x1800b273a  movdqa  xmmword ptr [rbp+0C0h+rect.right], xmm0
0x1800b273f  mov     eax, [rbp+0C0h+rectCaption.top]
0x1800b2742  sub     eax, [rbp+0C0h+rectWindow.bottom]
0x1800b2745  mov     r9d, [rbp+0C0h+rectCaption.left]
0x1800b2749  sub     r9d, [rbp+0C0h+rectWindow.right]; xRight
0x1800b274d  mov     [rsp+1C0h+yBottom], eax; yBottom
0x1800b2751  xor     r8d, r8d; yTop
0x1800b2754  xor     edx, edx; xLeft
0x1800b2756  lea     this, [rbp+0C0h+rect.right]; lprc
0x1800b275a  call    cs:__imp_SetRect
0x1800b2760  mov     this, [rbp+0C0h+dc.m_hAttribDC]; hdc
0x1800b2764  call    cs:__imp_CreateCompatibleDC
0x1800b276a  mov     rdx, rax; hDC
0x1800b276d  lea     this, [rbp+0C0h+dcMem.m_hDC]; this
0x1800b2771  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x1800b2776  test    eax, eax
0x1800b2778  jz      short loc_1800B27C9
0x1800b277a  mov     r8d, [rbp+0C0h+rectWindow.top]
0x1800b277e  sub     r8d, [rbp+0C0h+rect.bottom]; cy
0x1800b2782  mov     edx, [rbp+0C0h+rectWindow.left]
0x1800b2785  sub     edx, [rbp+0C0h+rect.right]; cx
0x1800b2788  mov     this, [rbp+0C0h+dc.m_hAttribDC]; hdc
0x1800b278c  call    cs:__imp_CreateCompatibleBitmap
0x1800b2792  mov     rdx, rax; hObject
0x1800b2795  lea     this, [rsp+1C0h+bmp.m_hObject]; this
0x1800b279a  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1800b279f  test    eax, eax
0x1800b27a1  jz      short loc_1800B27C9
0x1800b27a3  mov     dword ptr [rsp+1C0h+strCaption.m_pszData+4], 1
0x1800b27ab  mov     rdx, [rsp+1C0h+dcMem.__vftable]; h
0x1800b27b0  mov     this, [rbp+0C0h+dcMem.m_hAttribDC]; hdc
0x1800b27b4  call    cs:__imp_SelectObject
0x1800b27ba  mov     this, rax; h
0x1800b27bd  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1800b27c2  mov     r13, rax
0x1800b27c5  lea     r14, [rbp+0C0h+dcMem.m_hDC]
0x1800b27c9  xorps   xmm0, xmm0
0x1800b27cc  movups  xmmword ptr [rbp+0C0h+rcClient.right], xmm0
0x1800b27d0  xorps   xmm1, xmm1
0x1800b27d3  movups  xmmword ptr [rbp+0C0h+rcBar.right], xmm1
0x1800b27d7  lea     rdx, [rbp+0C0h+rcBar.right]; lpRect
0x1800b27db  mov     this, [rdi+40h]; hWnd
0x1800b27df  call    cs:__imp_GetWindowRect
0x1800b27e5  lea     rdx, [rbp+0C0h+rcClient.right]; lpRect
0x1800b27e9  mov     this, [rdi+40h]; hWnd
0x1800b27ed  call    cs:__imp_GetClientRect
0x1800b27f3  lea     rdx, [rbp+0C0h+rcClient.right]; lpRect
0x1800b27f7  mov     this, rdi; this
0x1800b27fa  call    ?ClientToScreen@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ClientToScreen(tagRECT *)
0x1800b27ff  mov     r8d, [rbp+0C0h+rcBar.bottom]
0x1800b2803  neg     r8d; dy
0x1800b2806  mov     edx, [rbp+0C0h+rcBar.right]
0x1800b2809  neg     edx; dx
0x1800b280b  lea     this, [rbp+0C0h+rcClient.right]; lprc
0x1800b280f  call    cs:__imp_OffsetRect
0x1800b2815  lea     rdx, [rbp+0C0h+rcClient.right]; lpRect
0x1800b2819  lea     this, [rbp+0C0h+dc.m_hDC]; this
0x1800b281d  call    ?ExcludeClipRect@CDC@@QEAAHPEBUtagRECT@@@Z; CDC::ExcludeClipRect(tagRECT const *)
0x1800b2822  mov     [rsp+1C0h+bmp.__vftable], rsi
0x1800b2827  lea     rax, ??_7CRgn@@6B@; const CRgn::`vftable'
0x1800b282e  mov     [rsp+1C0h+rgn.m_hObject], rax
0x1800b2833  lea     rbx, [rdi+168h]
0x1800b283a  mov     this, rbx; lprc
0x1800b283d  call    cs:__imp_IsRectEmpty
0x1800b2843  test    eax, eax
0x1800b2845  jnz     short loc_1800B286B
0x1800b2847  mov     this, rbx; lprect
0x1800b284a  call    cs:__imp_CreateRectRgnIndirect
0x1800b2850  mov     rdx, rax; hObject
0x1800b2853  lea     this, [rsp+1C0h+rgn.m_hObject]; this
0x1800b2858  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1800b285d  lea     rdx, [rsp+1C0h+rgn.m_hObject]; pRgn
0x1800b2862  lea     this, [rbp+0C0h+dc.m_hDC]; this
0x1800b2866  call    ?SelectClipRgn@CDC@@QEAAHPEAVCRgn@@@Z; CDC::SelectClipRgn(CRgn *)
0x1800b286b  mov     rax, [rdi]
0x1800b286e  mov     rdx, r14
0x1800b2871  mov     this, rdi
0x1800b2874  mov     rax, [rax+438h]
0x1800b287b  call    cs:__guard_dispatch_icall_fptr
0x1800b2881  xorps   xmm0, xmm0
0x1800b2884  movdqa  xmmword ptr [rbp+0C0h+rectCaption.right], xmm0
0x1800b2889  mov     rax, [rdi]
0x1800b288c  lea     rdx, [rbp+0C0h+rectCaption.right]
0x1800b2890  mov     this, rdi
0x1800b2893  mov     rax, [rax+3A0h]
0x1800b289a  call    cs:__guard_dispatch_icall_fptr
0x1800b28a0  mov     rax, [rdi+248h]
0x1800b28a7  test    rax, rax
0x1800b28aa  jnz     short loc_1800B28C7
0x1800b28ac  mov     this, [rdi+130h]; hWnd
0x1800b28b3  call    ?FromHandlePermanent@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandlePermanent(HWND__ *)
0x1800b28b8  mov     rdx, rax; pWnd
0x1800b28bb  lea     this, ?afxGlobalUtils@@3VCGlobalUtils@@A; this
0x1800b28c2  call    ?GetDockingManager@CGlobalUtils@@QEAAPEAVCDockingManager@@PEAVCWnd@@@Z; CGlobalUtils::GetDockingManager(CWnd *)
0x1800b28c7  cmp     [rax+0Ch], esi
0x1800b28ca  jz      short loc_1800B28D6
0x1800b28cc  lea     this, [rbp+0C0h+rectCaption.right]; lprc
0x1800b28d0  call    cs:__imp_SetRectEmpty
0x1800b28d6  mov     rax, [rdi]
0x1800b28d9  lea     rdx, [rbp+0C0h+rectCaption.right]
0x1800b28dd  mov     this, rdi
0x1800b28e0  mov     rax, [rax+3A0h]
0x1800b28e7  call    cs:__guard_dispatch_icall_fptr
0x1800b28ed  call    ?GetInstance@CMFCVisualManager@@SAPEAV1@XZ; CMFCVisualManager::GetInstance(void)
0x1800b28f2  mov     r10, rax
0x1800b28f5  mov     this, [rax]
0x1800b28f8  mov     rax, [this+2A0h]
0x1800b28ff  mov     ecx, [rdi+0ECh]
0x1800b2905  movaps  xmm0, xmmword ptr [rbp+0C0h+rectCaption.right]
0x1800b2909  movdqa  xmmword ptr [rbp+0C0h+rectClip.right], xmm0
0x1800b290e  mov     [rsp+1C0h+yBottom], ecx
0x1800b2912  mov     r9, rdi
0x1800b2915  lea     r8, [rbp+0C0h+rectClip.right]
0x1800b2919  mov     rdx, r14
0x1800b291c  mov     this, r10
0x1800b291f  call    cs:__guard_dispatch_icall_fptr
0x1800b2925  mov     dword ptr [rsp+1C0h+strCaption.m_pszData], eax
0x1800b2929  or      r12d, 0FFFFFFFFh
0x1800b292d  or      esi, r12d
0x1800b2930  mov     r15, [rdi+188h]
0x1800b2937  jmp     loc_1800B29D4
0x1800b293c  mov     rbx, [r15+10h]
0x1800b2940  mov     r15, [r15]
0x1800b2943  mov     [rbx+24h], eax
0x1800b2946  cmp     dword ptr [rbx+10h], 0
0x1800b294a  jnz     loc_1800B29D4
0x1800b2950  mov     rax, [rbx]
0x1800b2953  mov     rax, [rax+28h]
0x1800b2957  mov     this, rbx
0x1800b295a  cmp     dword ptr [rbx+1Ch], 0
0x1800b295e  jz      short loc_1800B299B
0x1800b2960  cmp     esi, 0FFFFFFFFh
0x1800b2963  jnz     short loc_1800B2977
0x1800b2965  lea     rdx, [rbp+0C0h+rectClip.right]
0x1800b2969  call    cs:__guard_dispatch_icall_fptr
0x1800b296f  mov     esi, [rax+8]
0x1800b2972  add     esi, 2
0x1800b2975  jmp     short loc_1800B29D0
0x1800b2977  lea     rdx, [rbp+0C0h+var_80]
0x1800b297b  call    cs:__guard_dispatch_icall_fptr
0x1800b2981  mov     ecx, [rax+8]
0x1800b2984  add     ecx, 2
0x1800b2987  cmp     esi, ecx
0x1800b2989  jg      short loc_1800B29D0
0x1800b298b  mov     rax, [rbx]
0x1800b298e  lea     rdx, [rbp+0C0h+var_70]
0x1800b2992  mov     this, rbx
0x1800b2995  mov     rax, [rax+28h]
0x1800b2999  jmp     short loc_1800B2969
0x1800b299b  cmp     r12d, 0FFFFFFFFh
0x1800b299f  jnz     short loc_1800B29A7
0x1800b29a1  lea     rdx, [rbp+0C0h+var_60]
0x1800b29a5  jmp     short loc_1800B29C7
0x1800b29a7  lea     rdx, [rbp+0C0h+var_50]
0x1800b29ab  call    cs:__guard_dispatch_icall_fptr
0x1800b29b1  cmp     r12d, [rax]
0x1800b29b4  jl      short loc_1800B29D0
0x1800b29b6  mov     rax, [rbx]
0x1800b29b9  lea     rdx, [rbp+0C0h+var_40]
0x1800b29c0  mov     this, rbx
0x1800b29c3  mov     rax, [rax+28h]
0x1800b29c7  call    cs:__guard_dispatch_icall_fptr
0x1800b29cd  mov     r12d, [rax]
0x1800b29d0  mov     eax, dword ptr [rsp+1C0h+strCaption.m_pszData]
0x1800b29d4  test    r15, r15
0x1800b29d7  jnz     loc_1800B293C
0x1800b29dd  mov     r15d, 1
0x1800b29e3  mov     edx, r15d; nBkMode
0x1800b29e6  mov     this, r14; this
0x1800b29e9  call    ?SetBkMode@CDC@@QEAAHH@Z; CDC::SetBkMode(int)
0x1800b29ee  mov     rax, [r14]
0x1800b29f1  mov     edx, dword ptr [rsp+1C0h+strCaption.m_pszData]
0x1800b29f5  mov     this, r14
0x1800b29f8  mov     rax, [rax+70h]
0x1800b29fc  call    cs:__guard_dispatch_icall_fptr
0x1800b2a02  mov     rax, [r14]
0x1800b2a05  mov     rbx, [rax+60h]
0x1800b2a09  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x1800b2a10  jnz     short loc_1800B2A25
0x1800b2a12  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x1800b2a19  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1800b2a1e  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r15d; AFX_GLOBAL_DATA afxGlobalData ...
0x1800b2a25  lea     rdx, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.fontBold; AFX_GLOBAL_DATA afxGlobalData ...
0x1800b2a2c  mov     this, r14
0x1800b2a2f  mov     rax, rbx
0x1800b2a32  call    cs:__guard_dispatch_icall_fptr
0x1800b2a38  mov     rbx, rax
0x1800b2a3b  mov     this, [rdi]
0x1800b2a3e  mov     rax, [this+380h]
0x1800b2a45  lea     rdx, [rsp+1C0h+rgn]
0x1800b2a4a  mov     this, rdi
0x1800b2a4d  call    cs:__guard_dispatch_icall_fptr
0x1800b2a53  nop
0x1800b2a54  movaps  xmm0, xmmword ptr [rbp+0C0h+rectCaption.right]
0x1800b2a58  movaps  xmmword ptr [rbp+0C0h+rectText.right], xmm0
0x1800b2a5c  psrldq  xmm0, 8
0x1800b2a61  movd    eax, xmm0
0x1800b2a65  or      r15d, 0FFFFFFFFh
0x1800b2a69  cmp     r12d, r15d
0x1800b2a6c  cmovnz  eax, r12d
0x1800b2a70  mov     [rbp+0C0h+rcClient.left], eax
0x1800b2a73  mov     eax, [rbp+0C0h+rectText.right]
0x1800b2a76  cmp     esi, r15d
0x1800b2a79  cmovnz  eax, esi
0x1800b2a7c  mov     [rbp+0C0h+rectText.right], eax
0x1800b2a7f  xor     r8d, r8d; dy
0x1800b2a82  lea     edx, [r15-1]; dx
0x1800b2a86  lea     this, [rbp+0C0h+rectText.right]; lprc
0x1800b2a8a  call    cs:__imp_InflateRect
0x1800b2a90  mov     rax, [r14]
0x1800b2a93  mov     rdx, [rsp+1C0h+rgn.__vftable]
0x1800b2a98  mov     [rsp+1C0h+yBottom], 8024h
0x1800b2aa0  lea     r9, [rbp+0C0h+rectText.right]
0x1800b2aa4  mov     r8d, [rdx-10h]
0x1800b2aa8  mov     this, r14
0x1800b2aab  mov     rax, [rax+0E0h]
0x1800b2ab2  call    cs:__guard_dispatch_icall_fptr
0x1800b2ab8  mov     rax, [r14]
0x1800b2abb  mov     rdx, rbx
0x1800b2abe  mov     this, r14
0x1800b2ac1  mov     rax, [rax+60h]
0x1800b2ac5  call    cs:__guard_dispatch_icall_fptr
0x1800b2acb  xor     edx, edx; pRgn
0x1800b2acd  mov     this, r14; this
0x1800b2ad0  call    ?SelectClipRgn@CDC@@QEAAHPEAVCRgn@@@Z; CDC::SelectClipRgn(CRgn *)
0x1800b2ad5  mov     rax, [rdi]
0x1800b2ad8  mov     rdx, r14
0x1800b2adb  mov     this, rdi
0x1800b2ade  mov     rax, [rax+440h]
0x1800b2ae5  call    cs:__guard_dispatch_icall_fptr
0x1800b2aeb  cmp     dword ptr [rsp+1C0h+strCaption.m_pszData+4], 0
0x1800b2af0  jz      loc_1800B2B82
0x1800b2af6  xorps   xmm0, xmm0
0x1800b2af9  movdqa  xmmword ptr [rbp+0C0h+rectClip.right], xmm0
0x1800b2afe  lea     rdx, [rbp+0C0h+rectClip.right]; lprect
0x1800b2b02  mov     this, [rbp+0C0h+dc.m_hAttribDC]; hdc
0x1800b2b06  call    cs:__imp_GetClipBox
0x1800b2b0c  cmp     eax, 1
0x1800b2b0f  jz      short loc_1800B2B63
0x1800b2b11  cmp     eax, 2
0x1800b2b14  jz      short loc_1800B2B1F
0x1800b2b16  movaps  xmm0, xmmword ptr [rbp+0C0h+rect.right]
0x1800b2b1a  movdqa  xmmword ptr [rbp+0C0h+rectClip.right], xmm0
0x1800b2b1f  mov     rdx, qword ptr [rbp+0C0h+rectClip.right]; x
0x1800b2b23  mov     r8, rdx
0x1800b2b26  shr     r8, 20h; y
0x1800b2b2a  mov     r9, qword ptr [rbp+0C0h+rect.left]
0x1800b2b2e  mov     this, r9
0x1800b2b31  shr     this, 20h
0x1800b2b35  sub     ecx, r8d
0x1800b2b38  sub     r9d, edx; cx
0x1800b2b3b  mov     [rsp+1C0h+rop], 0CC0020h; rop
  ... truncated ...
```
