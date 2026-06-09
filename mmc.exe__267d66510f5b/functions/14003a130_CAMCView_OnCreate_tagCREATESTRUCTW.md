# CAMCView::OnCreate(tagCREATESTRUCTW *)

- ea: `0x14003a130`
- end: `0x14003a6f9`
- name: `?OnCreate@CAMCView@@IEAAHPEAUtagCREATESTRUCTW@@@Z`
- size: `1481`
- prototype: `__int64 __fastcall(CAMCView *__hidden this, struct tagCREATESTRUCTW *)`
- caller_count: `0`
- callee_count: `26`
- tags: `broker_com_uri`

## callees

- `0x14000c1d0`
- `0x1400113a0`
- `0x140014448`
- `0x140021920`
- `0x14002eedc`
- `0x1400395fc`
- `0x14003a130`
- `0x14003ce64`
- `0x14004053c`
- `0x1400413dc`
- `0x140046e08`
- `0x140048c00`
- `0x140049410`
- `0x14004dcdc`
- `0x140050de8`
- `0x140056694`
- `0x140057d04`
- `0x140058c30`
- `0x140058dc8`
- `0x140058f5c`
- `0x140059020`
- `0x14008cfc0`
- `0x140093010`
- `0x140099624`
- `0x1400e9e10`
- `0x1400f3010`

## import_xrefs

- `USER32!GetWindowRect` at `0x14003a345`
- `USER32!GetWindowRect` at `0x14003a345`
- `USER32!SendMessageW` at `0x14003a537`
- `USER32!SendMessageW` at `0x14003a537`
- `USER32!GetWindowLongPtrW` at `0x14003a1b9`
- `USER32!GetWindowLongPtrW` at `0x14003a1b9`
- `USER32!GetWindow` at `0x14003a62b`
- `USER32!GetWindow` at `0x14003a62b`
- `MFC42u!__imp_?Create@CStatic@@QEAAHPEBGKAEBUtagRECT@@PEAVCWnd@@I@Z` at `0x14003a255`
- `MFC42u!__imp_?Create@CStatic@@QEAAHPEBGKAEBUtagRECT@@PEAVCWnd@@I@Z` at `0x14003a255`
- `MFC42u!__imp_?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z` at `0x14003a634`
- `MFC42u!__imp_?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z` at `0x14003a634`
- `MFC42u!__imp_?GetMDIFrame@CMDIChildWnd@@QEAAPEAVCMDIFrameWnd@@XZ` at `0x14003a617`
- `MFC42u!__imp_?GetMDIFrame@CMDIChildWnd@@QEAAPEAVCMDIFrameWnd@@XZ` at `0x14003a617`
- `MFC42u!__imp_?OnCreate@CView@@IEAAHPEAUtagCREATESTRUCTW@@@Z` at `0x14003a1ec`
- `MFC42u!__imp_?OnCreate@CView@@IEAAHPEAUtagCREATESTRUCTW@@@Z` at `0x14003a1ec`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003a49f`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003a503`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003a55f`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003a67c`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003a6a6`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003a6c5`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003a49f`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003a503`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003a55f`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003a67c`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003a6a6`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003a6c5`
- `mmcbase!?s_CallDepth@SC@mmcerror@@0IA` at `0x14003a171`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14003a493`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14003a4f7`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14003a553`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14003a670`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14003a493`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14003a4f7`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14003a553`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14003a670`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14003a18f`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14003a18f`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x14003a69a`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x14003a69a`

## string_xrefs

- `0x14003a183`: `CAMCView::OnCreate`
- `0x14003a524`: `AccessibleToolbar`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 __fastcall CAMCView::OnCreate(CAMCView *this, struct tagCREATESTRUCTW *a2)
{
  HWND *v4; // r14
  __int64 v5; // r15
  CSubclassManager *SubclassManager; // rax
  struct CChildFrame *ParentFrame; // rax
  CMDIChildWnd *v8; // rsi
  __int64 v9; // rdx
  struct CCreateContext *lpCreateParams; // r12
  int v11; // eax
  struct FragmentControlProvider **v12; // rbx
  int v13; // r9d
  int v14; // edx
  __int64 v15; // rcx
  int v16; // edx
  __int64 v17; // rax
  HWND v18; // rcx
  int v19; // r8d
  CResultViewType *v20; // rax
  mmcerror::SC *v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 ToolbarObjects; // rax
  struct CMDIFrameWnd *MDIFrame; // rax
  HWND Window; // rax
  __int64 v27; // rax
  signed __int64 v29; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v30; // [rsp+48h] [rbp-B8h]
  struct FragmentControlProvider **v31; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v32[24]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v33; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v34[144]; // [rsp+80h] [rbp-80h] BYREF
  struct tagRECT Rect; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v36[144]; // [rsp+120h] [rbp+20h] BYREF

  v30 = 0;
  ++mmcerror::SC::s_CallDepth;
  v29 = 3;
  mmcerror::SC::SetFunctionName((mmcerror::SC *)&v29, L"CAMCView::OnCreate");
  v4 = (HWND *)((char *)this + 64);
  v5 = std::map<HWND__ *,CAMCView::UiProviderContext>::operator[]((char *)this + 368, (char *)this + 64);
  *(_QWORD *)v5 = *((_QWORD *)this + 8);
  *(_QWORD *)(v5 + 16) = GetWindowLongPtrW(*((HWND *)this + 8), -4);
  SubclassManager = GetSubclassManager();
  CSubclassManager::SubclassWindow(
    SubclassManager,
    *((HWND *)this + 8),
    (struct CSubclasser *)(((unsigned __int64)this + 336) & -(__int64)(this != 0)));
  if ( CView::OnCreate(this, a2) == -1 )
    goto LABEL_36;
  ParentFrame = CAMCView::GetParentFrame(this);
  v8 = ParentFrame;
  if ( !ParentFrame )
    goto LABEL_36;
  *((_QWORD *)ParentFrame + 126) = this;
  *((_QWORD *)this + 114) = (char *)ParentFrame + 352;
  *((_QWORD *)this + 115) = (char *)this + 136;
  CStatic::Create((CAMCView *)((char *)this + 464), 0, 0x40000000u, (const struct tagRECT *)&g_rectEmpty, this, 0x31F7u);
  v9 = *((_QWORD *)this + 16);
  lpCreateParams = (struct CCreateContext *)a2->lpCreateParams;
  v11 = *(_DWORD *)(v9 + 608);
  *((_DWORD *)this + 256) = v11;
  if ( (v11 & 1) != 0 )
    *((_DWORD *)this + 226) &= ~1u;
  if ( (v11 & 0x20) != 0 )
    *((_DWORD *)this + 226) &= ~0x80u;
  else
    CAMCView::SetActionPaneVisible(this, *(_BYTE *)(v9 + 613));
  v31 = 0;
  ATL::CComObject<MMCViewProvider>::CreateInstance(&v31);
  v12 = v31;
  (*((void (__fastcall **)(struct FragmentControlProvider **))*v31 + 1))(v31);
  (*((void (__fastcall **)(struct FragmentControlProvider **))v12[1] + 9))(v12 + 1);
  (*((void (__fastcall **)(struct FragmentControlProvider **, HWND, _QWORD, _QWORD, _QWORD, _QWORD))*v12 + 14))(
    v12,
    *v4,
    0,
    0,
    0,
    0);
  *(_QWORD *)(v5 + 8) = v12;
  (*((void (__fastcall **)(struct FragmentControlProvider **))*v12 + 1))(v12);
  (*(void (__fastcall **)(_QWORD, HWND, _QWORD, _QWORD))(**(_QWORD **)(v5 + 8) + 112LL))(*(_QWORD *)(v5 + 8), *v4, 0, 0);
  Rect = 0;
  GetWindowRect(*v4, &Rect);
  v13 = Rect.right - Rect.left;
  v14 = Rect.bottom - Rect.top;
  v15 = *(_QWORD *)(v5 + 8);
  *(_QWORD *)(v15 + 156) = *(_QWORD *)&Rect.left;
  *(_DWORD *)(v15 + 164) = v13;
  *(_DWORD *)(v15 + 168) = v14;
  if ( !CAMCView::CreateView(this, 12785) || !*((_QWORD *)this + 87) )
    goto LABEL_36;
  CAMCView::SetPane(this, 0);
  if ( (*((_BYTE *)this + 1024) & 2) != 0 )
    *((_DWORD *)this + 274) &= 0xFFFFFFFC;
  if ( !(unsigned int)CAMCView::CreateListCtrl(this, v16, lpCreateParams)
    || ((v17 = *((_QWORD *)this + 87)) != 0 ? (v18 = *(HWND *)(v17 + 64)) : (v18 = 0),
        (CAMCTreeView::GetEmbeddedWindowTreeProvider(v18),
         v33 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 88) + 128LL) + 488LL),
         v31 = (struct FragmentControlProvider **)&v33,
         FragmentControlProvider::setChildren(*(FragmentControlProvider **)(v5 + 8), &v31, v19),
         !CAMCView::CreateView(this, 12796))
     || !*((_QWORD *)this + 89)
     || (CAMCView::SetPane(this, 2), !CAMCView::CreateFolderCtrls(this))) )
  {
LABEL_36:
    v29 = 0x8000400500000003uLL;
    goto LABEL_37;
  }
  CResultViewType::CResultViewType((CResultViewType *)v36);
  v20 = CResultViewType::CResultViewType((CResultViewType *)v34, (const struct CResultViewType *)v36);
  v21 = CAMCView::ScSetResultPane((__int64)this, (mmcerror::SC *)v32, 0, v20, 0, 0);
  mmcerror::SC::operator=(&v29, v21);
  mmcerror::SC::~SC((mmcerror::SC *)v32);
  if ( HIDWORD(v29) && ((_DWORD)v29 != 3 || v29 < 0) )
  {
    CResultViewType::~CResultViewType((CResultViewType *)v36);
LABEL_37:
    mmcerror::SC::~SC((mmcerror::SC *)&v29);
    return 0xFFFFFFFFLL;
  }
  CResultViewType::~CResultViewType((CResultViewType *)v36);
  v22 = *((_QWORD *)AMCGetMainWnd() + 47);
  v23 = ScCheckPointers(v32, v22, 2147942414LL);
  mmcerror::SC::operator=(&v29, v23);
  mmcerror::SC::~SC((mmcerror::SC *)v32);
  if ( HIDWORD(v29) && ((_DWORD)v29 != 3 || v29 < 0) )
    goto LABEL_37;
  SendMessageW(*(HWND *)(v22 + 64), 0x200Bu, 0, (LPARAM)L"AccessibleToolbar");
  ToolbarObjects = CAMCView::ScCreateToolbarObjects(this, v32);
  mmcerror::SC::operator=(&v29, ToolbarObjects);
  mmcerror::SC::~SC((mmcerror::SC *)v32);
  if ( HIDWORD(v29) )
  {
    if ( (_DWORD)v29 != 3 || v29 < 0 )
      goto LABEL_37;
  }
  *((_DWORD *)this + 248) = 0;
  _com_ptr_t<_com_IIID<IDataObject,&__s_GUID const _GUID_0000010e_0000_0000_c000_000000000046>>::operator=(
    (char *)this + 1032,
    *(_QWORD *)(*((_QWORD *)this + 87) + 280LL));
  _com_ptr_t<_com_IIID<IDataObject,&__s_GUID const _GUID_0000010e_0000_0000_c000_000000000046>>::operator=(
    (char *)this + 1040,
    *(_QWORD *)(*((_QWORD *)this + 87) + 304LL));
  _com_ptr_t<_com_IIID<IDataObject,&__s_GUID const _GUID_0000010e_0000_0000_c000_000000000046>>::operator=(
    (char *)this + 1048,
    *(_QWORD *)(*((_QWORD *)this + 87) + 312LL));
  *((_QWORD *)this + 125) = *v4;
  *((_QWORD *)this + 127) = CCCListViewCtrl::GetListViewHWND(*((CCCListViewCtrl **)this + 88));
  *((_QWORD *)this + 123) = *((_QWORD *)this + 16) + 544LL;
  *((_QWORD *)this + 136) = 0;
  MDIFrame = CMDIChildWnd::GetMDIFrame(v8);
  if ( MDIFrame )
  {
    Window = GetWindow(*((HWND *)MDIFrame + 8), 5u);
    CWnd::FromHandle(Window);
  }
  _CEventSource<CAMCViewObserver>::_AddObserver((CAMCView *)((char *)this + 176), (CObserverBase *)&qword_140162098);
  v27 = CEventSource<CAMCViewObserver,CVoid,CVoid,CVoid,CVoid>::ScFireEvent<CAMCViewObserver,CAMCView *>(
          (char *)this + 176,
          v32,
           CListViewObserver::`vcall'{8,{flat}},
          this);
  mmcerror::SC::operator=(&v29, v27);
  mmcerror::SC::~SC((mmcerror::SC *)v32);
  if ( HIDWORD(v29) && ((_DWORD)v29 != 3 || v29 < 0) )
    mmcerror::SC::TraceAndClear((mmcerror::SC *)&v29);
  mmcerror::SC::~SC((mmcerror::SC *)&v29);
  return 0;
}

```

## disassembly

```asm
0x14003a130  mov     [rsp-8+arg_10], rbx
0x14003a135  mov     [rsp-8+arg_18], rsi
0x14003a13a  push    rbp
0x14003a13b  push    rdi
0x14003a13c  push    r12
0x14003a13e  push    r14
0x14003a140  push    r15
0x14003a142  lea     rbp, [rsp-0C0h]
0x14003a14a  sub     rsp, 1C0h
0x14003a151  mov     rax, cs:__security_cookie
0x14003a158  xor     rax, rsp
0x14003a15b  mov     [rbp+0E0h+var_30], rax
0x14003a162  mov     rbx, rdx
0x14003a165  mov     rdi, rcx
0x14003a168  xorps   xmm0, xmm0
0x14003a16b  movdqu  [rsp+1E0h+var_198], xmm0
0x14003a171  mov     rax, cs:__imp_?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x14003a178  inc     dword ptr [rax]
0x14003a17a  mov     [rsp+1E0h+var_1A0], 3
0x14003a183  lea     rdx, aCamcviewOncrea; "CAMCView::OnCreate"
0x14003a18a  lea     rcx, [rsp+1E0h+var_1A0]
0x14003a18f  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x14003a195  lea     r14, [rdi+40h]
0x14003a199  lea     rcx, [rdi+170h]
0x14003a1a0  mov     rdx, r14
0x14003a1a3  call    ??A?$map@PEAUHWND__@@UUiProviderContext@CAMCView@@U?$less@PEAUHWND__@@@std@@V?$allocator@U?$pair@QEAUHWND__@@UUiProviderContext@CAMCView@@@std@@@5@@std@@QEAAAEAUUiProviderContext@CAMCView@@AEBQEAUHWND__@@@Z; std::map<HWND__ *,CAMCView::UiProviderContext>::operator[](HWND__ * const &)
0x14003a1a8  mov     r15, rax
0x14003a1ab  mov     rcx, [r14]
0x14003a1ae  mov     [rax], rcx
0x14003a1b1  mov     edx, 0FFFFFFFCh; nIndex
0x14003a1b6  mov     rcx, [r14]; hWnd
0x14003a1b9  call    cs:__imp_GetWindowLongPtrW
0x14003a1bf  mov     [r15+10h], rax
0x14003a1c3  call    ?GetSubclassManager@@YAAEAVCSubclassManager@@XZ; GetSubclassManager(void)
0x14003a1c8  mov     rcx, rdi
0x14003a1cb  lea     rdx, [rdi+150h]
0x14003a1d2  neg     rcx
0x14003a1d5  sbb     r8, r8
0x14003a1d8  and     r8, rdx; struct CSubclasser *
0x14003a1db  mov     rdx, [r14]; HWND
0x14003a1de  mov     rcx, rax; this
0x14003a1e1  call    ?SubclassWindow@CSubclassManager@@QEAA_NPEAUHWND__@@PEAVCSubclasser@@@Z; CSubclassManager::SubclassWindow(HWND__ *,CSubclasser *)
0x14003a1e6  mov     rdx, rbx
0x14003a1e9  mov     rcx, rdi
0x14003a1ec  call    cs:__imp_?OnCreate@CView@@IEAAHPEAUtagCREATESTRUCTW@@@Z; CView::OnCreate(tagCREATESTRUCTW *)
0x14003a1f2  cmp     eax, 0FFFFFFFFh
0x14003a1f5  jz      loc_14003A6B0
0x14003a1fb  mov     rcx, rdi; this
0x14003a1fe  call    ?GetParentFrame@CAMCView@@IEBAPEAVCChildFrame@@XZ; CAMCView::GetParentFrame(void)
0x14003a203  mov     rsi, rax
0x14003a206  test    rax, rax
0x14003a209  jz      loc_14003A6B0
0x14003a20f  mov     [rax+3F0h], rdi
0x14003a216  lea     rcx, [rax+160h]
0x14003a21d  mov     [rdi+390h], rcx
0x14003a224  lea     rcx, [rdi+88h]
0x14003a22b  mov     [rdi+398h], rcx
0x14003a232  lea     rcx, [rdi+1D0h]
0x14003a239  mov     dword ptr [rsp+1E0h+var_1B8], 31F7h
0x14003a241  mov     [rsp+1E0h+var_1C0], rdi
0x14003a246  lea     r9, ?g_rectEmpty@@3VCRect@@B; CRect const g_rectEmpty
0x14003a24d  xor     edx, edx
0x14003a24f  mov     r8d, 40000000h
0x14003a255  call    cs:__imp_?Create@CStatic@@QEAAHPEBGKAEBUtagRECT@@PEAVCWnd@@I@Z; CStatic::Create(ushort const *,ulong,tagRECT const &,CWnd *,uint)
0x14003a25b  mov     rdx, [rdi+80h]
0x14003a262  mov     r12, [rbx]
0x14003a265  mov     eax, [rdx+260h]
0x14003a26b  mov     [rdi+400h], eax
0x14003a271  test    al, 1
0x14003a273  jz      short loc_14003A27C
0x14003a275  and     dword ptr [rdi+388h], 0FFFFFFFEh
0x14003a27c  test    al, 20h
0x14003a27e  jz      short loc_14003A28A
0x14003a280  btr     dword ptr [rdi+388h], 7
0x14003a288  jmp     short loc_14003A298
0x14003a28a  mov     dl, [rdx+265h]; bool
0x14003a290  mov     rcx, rdi; this
0x14003a293  call    ?SetActionPaneVisible@CAMCView@@AEAAX_N@Z; CAMCView::SetActionPaneVisible(bool)
0x14003a298  mov     [rsp+1E0h+var_188], 0
0x14003a2a1  lea     rcx, [rsp+1E0h+var_188]
0x14003a2a6  call    ?CreateInstance@?$CComObject@VMMCViewProvider@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<MMCViewProvider>::CreateInstance(ATL::CComObject<MMCViewProvider> * *)
0x14003a2ab  mov     rbx, [rsp+1E0h+var_188]
0x14003a2b0  mov     rax, [rbx]
0x14003a2b3  mov     rcx, rbx
0x14003a2b6  mov     rax, [rax+8]
0x14003a2ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a2bf  lea     rcx, [rbx+8]
0x14003a2c3  mov     rax, [rcx]
0x14003a2c6  mov     rax, [rax+48h]
0x14003a2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a2cf  mov     rax, [rbx]
0x14003a2d2  mov     [rsp+1E0h+var_1B8], 0
0x14003a2db  mov     [rsp+1E0h+var_1C0], 0
0x14003a2e4  xor     r9d, r9d
0x14003a2e7  xor     r8d, r8d
0x14003a2ea  mov     rdx, [r14]
0x14003a2ed  mov     rcx, rbx
0x14003a2f0  mov     rax, [rax+70h]
0x14003a2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a2f9  mov     [r15+8], rbx
0x14003a2fd  mov     rax, [rbx]
0x14003a300  mov     rcx, rbx
0x14003a303  mov     rax, [rax+8]
0x14003a307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a30c  mov     rcx, [r15+8]
0x14003a310  mov     rax, [rcx]
0x14003a313  mov     [rsp+1E0h+var_1B8], 0
0x14003a31c  mov     [rsp+1E0h+var_1C0], 0
0x14003a325  xor     r9d, r9d
0x14003a328  xor     r8d, r8d
0x14003a32b  mov     rdx, [r14]
0x14003a32e  mov     rax, [rax+70h]
0x14003a332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a337  xorps   xmm0, xmm0
0x14003a33a  movups  xmmword ptr [rbp+0E0h+Rect.left], xmm0
0x14003a33e  lea     rdx, [rbp+0E0h+Rect]; lpRect
0x14003a342  mov     rcx, [r14]; hWnd
0x14003a345  call    cs:__imp_GetWindowRect
0x14003a34b  mov     r9d, [rbp+0E0h+Rect.right]
0x14003a34f  mov     r8d, [rbp+0E0h+Rect.left]
0x14003a353  sub     r9d, r8d
0x14003a356  mov     edx, [rbp+0E0h+Rect.bottom]
0x14003a359  mov     eax, [rbp+0E0h+Rect.top]
0x14003a35c  sub     edx, eax
0x14003a35e  mov     rcx, [r15+8]
0x14003a362  mov     [rcx+0A0h], eax
0x14003a368  mov     [rcx+9Ch], r8d
0x14003a36f  mov     [rcx+0A4h], r9d
0x14003a376  mov     [rcx+0A8h], edx
0x14003a37c  mov     edx, 31F1h; int
0x14003a381  mov     rcx, rdi; this
0x14003a384  call    ?CreateView@CAMCView@@AEAA_NH@Z; CAMCView::CreateView(int)
0x14003a389  test    al, al
0x14003a38b  jz      loc_14003A6B0
0x14003a391  mov     r8, [rdi+2B8h]
0x14003a398  test    r8, r8
0x14003a39b  jz      loc_14003A6B0
0x14003a3a1  xor     edx, edx
0x14003a3a3  mov     rcx, rdi
0x14003a3a6  call    ?SetPane@CAMCView@@QEAAXW4ViewPane@CConsoleView@@PEAVCView@@W4EUIStyleType@1@@Z; CAMCView::SetPane(CConsoleView::ViewPane,CView *,CAMCView::EUIStyleType)
0x14003a3ab  test    byte ptr [rdi+400h], 2
0x14003a3b2  jz      short loc_14003A3BB
0x14003a3b4  and     dword ptr [rdi+448h], 0FFFFFFFCh
0x14003a3bb  mov     r8, r12; struct CCreateContext *
0x14003a3be  mov     rcx, rdi; this
0x14003a3c1  call    ?CreateListCtrl@CAMCView@@QEAAHHPEAUCCreateContext@@@Z; CAMCView::CreateListCtrl(int,CCreateContext *)
0x14003a3c6  test    eax, eax
0x14003a3c8  jz      loc_14003A6B0
0x14003a3ce  mov     rax, [rdi+2B8h]
0x14003a3d5  test    rax, rax
0x14003a3d8  jnz     short loc_14003A3DE
0x14003a3da  xor     ecx, ecx
0x14003a3dc  jmp     short loc_14003A3E2
0x14003a3de  mov     rcx, [rax+40h]; HWND
0x14003a3e2  call    ?GetEmbeddedWindowTreeProvider@CAMCTreeView@@SAPEAVEmbeddedWindowTreeProvider@@PEAUHWND__@@@Z; CAMCTreeView::GetEmbeddedWindowTreeProvider(HWND__ *)
0x14003a3e7  mov     rax, [rdi+2C0h]
0x14003a3ee  mov     rcx, [rax+80h]
0x14003a3f5  mov     rax, [rcx+1E8h]
0x14003a3fc  mov     [rsp+1E0h+var_168], rax
0x14003a401  lea     rax, [rsp+1E0h+var_168]
0x14003a406  mov     [rsp+1E0h+var_188], rax
0x14003a40b  lea     rdx, [rsp+1E0h+var_188]; struct FragmentControlProvider ***
0x14003a410  mov     rcx, [r15+8]; this
0x14003a414  call    ?setChildren@FragmentControlProvider@@QEAAXQEAPEAPEAV1@H@Z; FragmentControlProvider::setChildren(FragmentControlProvider * * * const,int)
0x14003a419  mov     edx, 31FCh; int
0x14003a41e  mov     rcx, rdi; this
0x14003a421  call    ?CreateView@CAMCView@@AEAA_NH@Z; CAMCView::CreateView(int)
0x14003a426  test    al, al
0x14003a428  jz      loc_14003A6B0
0x14003a42e  mov     r8, [rdi+2C8h]
0x14003a435  test    r8, r8
0x14003a438  jz      loc_14003A6B0
0x14003a43e  mov     edx, 2
0x14003a443  mov     rcx, rdi
0x14003a446  call    ?SetPane@CAMCView@@QEAAXW4ViewPane@CConsoleView@@PEAVCView@@W4EUIStyleType@1@@Z; CAMCView::SetPane(CConsoleView::ViewPane,CView *,CAMCView::EUIStyleType)
0x14003a44b  mov     rcx, rdi; this
0x14003a44e  call    ?CreateFolderCtrls@CAMCView@@AEAA_NXZ; CAMCView::CreateFolderCtrls(void)
0x14003a453  test    al, al
0x14003a455  jz      loc_14003A6B0
0x14003a45b  lea     rcx, [rbp+0E0h+var_C0]; this
0x14003a45f  call    ??0CResultViewType@@QEAA@XZ; CResultViewType::CResultViewType(void)
0x14003a464  nop
0x14003a465  lea     rdx, [rbp+0E0h+var_C0]; struct CResultViewType *
0x14003a469  lea     rcx, [rbp+0E0h+var_160]; this
0x14003a46d  call    ??0CResultViewType@@QEAA@AEBV0@@Z; CResultViewType::CResultViewType(CResultViewType const &)
0x14003a472  mov     byte ptr [rsp+1E0h+var_1B8], 0
0x14003a477  mov     r9, rax
0x14003a47a  xor     r8d, r8d
0x14003a47d  lea     rdx, [rsp+1E0h+var_180]
0x14003a482  mov     rcx, rdi
0x14003a485  call    ?ScSetResultPane@CAMCView@@QEAA?AVSC@mmcerror@@PEAUHNODE__@@VCResultViewType@@H_N@Z; CAMCView::ScSetResultPane(HNODE__ *,CResultViewType,int,bool)
0x14003a48a  nop
0x14003a48b  mov     rdx, rax
0x14003a48e  lea     rcx, [rsp+1E0h+var_1A0]
0x14003a493  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x14003a499  nop
0x14003a49a  lea     rcx, [rsp+1E0h+var_180]
0x14003a49f  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14003a4a5  mov     ecx, dword ptr [rsp+1E0h+var_1A0+4]
0x14003a4a9  test    ecx, ecx
0x14003a4ab  jz      short loc_14003A4C6
0x14003a4ad  cmp     dword ptr [rsp+1E0h+var_1A0], 3
0x14003a4b2  jnz     short loc_14003A4B8
0x14003a4b4  test    ecx, ecx
0x14003a4b6  jns     short loc_14003A4C6
0x14003a4b8  lea     rcx, [rbp+0E0h+var_C0]; this
0x14003a4bc  call    ??1CResultViewType@@QEAA@XZ; CResultViewType::~CResultViewType(void)
0x14003a4c1  jmp     loc_14003A6C0
0x14003a4c6  lea     rcx, [rbp+0E0h+var_C0]; this
0x14003a4ca  call    ??1CResultViewType@@QEAA@XZ; CResultViewType::~CResultViewType(void)
0x14003a4cf  call    ?AMCGetMainWnd@@YAPEAVCMainFrame@@XZ; AMCGetMainWnd(void)
0x14003a4d4  mov     rbx, [rax+178h]
0x14003a4db  mov     r8d, 8007000Eh
0x14003a4e1  mov     rdx, rbx
0x14003a4e4  lea     rcx, [rsp+1E0h+var_180]
0x14003a4e9  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x14003a4ee  nop
0x14003a4ef  mov     rdx, rax
0x14003a4f2  lea     rcx, [rsp+1E0h+var_1A0]
0x14003a4f7  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x14003a4fd  nop
0x14003a4fe  lea     rcx, [rsp+1E0h+var_180]
0x14003a503  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14003a509  mov     eax, dword ptr [rsp+1E0h+var_1A0+4]
0x14003a50d  test    eax, eax
0x14003a50f  jz      short loc_14003A524
0x14003a511  cmp     dword ptr [rsp+1E0h+var_1A0], 3
0x14003a516  jnz     loc_14003A6C0
0x14003a51c  test    eax, eax
0x14003a51e  js      loc_14003A6C0
0x14003a524  lea     r9, lParam; "AccessibleToolbar"
0x14003a52b  xor     r8d, r8d; wParam
0x14003a52e  mov     edx, 200Bh; Msg
0x14003a533  mov     rcx, [rbx+40h]; hWnd
0x14003a537  call    cs:__imp_SendMessageW
0x14003a53d  lea     rdx, [rsp+1E0h+var_180]
0x14003a542  mov     rcx, rdi
0x14003a545  call    ?ScCreateToolbarObjects@CAMCView@@AEAA?AVSC@mmcerror@@XZ; CAMCView::ScCreateToolbarObjects(void)
0x14003a54a  nop
0x14003a54b  mov     rdx, rax
0x14003a54e  lea     rcx, [rsp+1E0h+var_1A0]
0x14003a553  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x14003a559  nop
0x14003a55a  lea     rcx, [rsp+1E0h+var_180]
0x14003a55f  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14003a565  mov     eax, dword ptr [rsp+1E0h+var_1A0+4]
0x14003a569  test    eax, eax
0x14003a56b  jz      short loc_14003A580
0x14003a56d  cmp     dword ptr [rsp+1E0h+var_1A0], 3
0x14003a572  jnz     loc_14003A6C0
0x14003a578  test    eax, eax
0x14003a57a  js      loc_14003A6C0
0x14003a580  mov     dword ptr [rdi+3E0h], 0
0x14003a58a  mov     rdx, [rdi+2B8h]
0x14003a591  lea     rcx, [rdi+408h]
0x14003a598  mov     rdx, [rdx+118h]
0x14003a59f  call    ??4?$_com_ptr_t@V?$_com_IIID@UIDataObject@@$1?_GUID_0000010e_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAAAEAV0@PEAUIDataObject@@@Z; _com_ptr_t<_com_IIID<IDataObject,&__s_GUID const _GUID_0000010e_0000_0000_c000_000000000046>>::operator=(IDataObject *)
0x14003a5a4  mov     rdx, [rdi+2B8h]
0x14003a5ab  lea     rcx, [rdi+410h]
0x14003a5b2  mov     rdx, [rdx+130h]
0x14003a5b9  call    ??4?$_com_ptr_t@V?$_com_IIID@UIDataObject@@$1?_GUID_0000010e_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAAAEAV0@PEAUIDataObject@@@Z; _com_ptr_t<_com_IIID<IDataObject,&__s_GUID const _GUID_0000010e_0000_0000_c000_000000000046>>::operator=(IDataObject *)
0x14003a5be  mov     rdx, [rdi+2B8h]
0x14003a5c5  lea     rcx, [rdi+418h]
0x14003a5cc  mov     rdx, [rdx+138h]
0x14003a5d3  call    ??4?$_com_ptr_t@V?$_com_IIID@UIDataObject@@$1?_GUID_0000010e_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAAAEAV0@PEAUIDataObject@@@Z; _com_ptr_t<_com_IIID<IDataObject,&__s_GUID const _GUID_0000010e_0000_0000_c000_000000000046>>::operator=(IDataObject *)
0x14003a5d8  mov     rax, [r14]
0x14003a5db  mov     [rdi+3E8h], rax
0x14003a5e2  mov     rcx, [rdi+2C0h]; this
0x14003a5e9  call    ?GetListViewHWND@CCCListViewCtrl@@QEBAPEAUHWND__@@XZ; CCCListViewCtrl::GetListViewHWND(void)
0x14003a5ee  mov     [rdi+3F8h], rax
0x14003a5f5  mov     rax, [rdi+80h]
0x14003a5fc  add     rax, 220h
0x14003a602  mov     [rdi+3D8h], rax
0x14003a609  mov     qword ptr [rdi+440h], 0
0x14003a614  mov     rcx, rsi
0x14003a617  call    cs:__imp_?GetMDIFrame@CMDIChildWnd@@QEAAPEAVCMDIFrameWnd@@XZ; CMDIChildWnd::GetMDIFrame(void)
0x14003a61d  test    rax, rax
0x14003a620  jz      short loc_14003A63A
0x14003a622  mov     edx, 5; uCmd
0x14003a627  mov     rcx, [rax+40h]; hWnd
0x14003a62b  call    cs:__imp_GetWindow
0x14003a631  mov     rcx, rax
0x14003a634  call    cs:__imp_?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x14003a63a  lea     rbx, [rdi+0B0h]
0x14003a641  lea     rdx, qword_140162098; this
0x14003a648  mov     rcx, rbx; struct CEventSourceBase *
0x14003a64b  call    ?_AddObserver@?$_CEventSource@VCAMCViewObserver@@@@QEAAXAEAVCAMCViewObserver@@@Z; _CEventSource<CAMCViewObserver>::_AddObserver(CAMCViewObserver &)
0x14003a650  mov     r9, rdi
0x14003a653  lea     r8, ??_9CListViewObserver@@$B7AA; [thunk]: CListViewObserver::`vcall'{8,{flat}}
0x14003a65a  lea     rdx, [rsp+1E0h+var_180]
0x14003a65f  mov     rcx, rbx
0x14003a662  call    ??$ScFireEvent@VCAMCViewObserver@@PEAVCAMCView@@@?$CEventSource@VCAMCViewObserver@@VCVoid@@V2@V2@V2@@@QEAA?AVSC@mmcerror@@P8CAMCViewObserver@@EAA?AV12@PEAVCAMCView@@@Z0@Z; CEventSource<CAMCViewObserver,CVoid,CVoid,CVoid,CVoid>::ScFireEvent<CAMCViewObserver,CAMCView *>(mmcerror::SC (CAMCViewObserver::*)(CAMCView *),CAMCView *)
0x14003a667  nop
0x14003a668  mov     rdx, rax
0x14003a66b  lea     rcx, [rsp+1E0h+var_1A0]
0x14003a670  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x14003a676  nop
0x14003a677  lea     rcx, [rsp+1E0h+var_180]
0x14003a67c  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14003a682  mov     eax, dword ptr [rsp+1E0h+var_1A0+4]
  ... truncated ...
```
