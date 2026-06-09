# CAMCListView::OnCreate(tagCREATESTRUCTW *)

- ea: `0x14003a8a0`
- end: `0x14003ac77`
- name: `?OnCreate@CAMCListView@@IEAAHPEAUtagCREATESTRUCTW@@@Z`
- size: `983`
- prototype: `__int64 __fastcall(struct FragmentControlProvider **this, struct tagCREATESTRUCTW *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140010c50`
- `0x140021920`
- `0x140025178`
- `0x140025204`
- `0x140039288`
- `0x14003a8a0`
- `0x1400413dc`
- `0x140046e08`
- `0x140057f9c`
- `0x1400598b4`
- `0x140059c74`
- `0x1400aa554`
- `0x1400e9e10`
- `0x1400f3010`

## import_xrefs

- `USER32!SetWinEventHook` at `0x14003a97d`
- `USER32!SetWinEventHook` at `0x14003a97d`
- `USER32!SendMessageW` at `0x14003abe4`
- `USER32!SendMessageW` at `0x14003abe4`
- `USER32!GetWindowLongPtrW` at `0x14003ab34`
- `USER32!GetWindowLongPtrW` at `0x14003ab34`
- `MFC42u!__imp_?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ` at `0x14003a93d`
- `MFC42u!__imp_?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ` at `0x14003a93d`
- `MFC42u!__imp_?Create@CStatic@@QEAAHPEBGKAEBUtagRECT@@PEAVCWnd@@I@Z` at `0x14003a928`
- `MFC42u!__imp_?Create@CStatic@@QEAAHPEBGKAEBUtagRECT@@PEAVCWnd@@I@Z` at `0x14003a928`
- `MFC42u!__imp_?OnCreate@CView@@IEAAHPEAUtagCREATESTRUCTW@@@Z` at `0x14003ab6a`
- `MFC42u!__imp_?OnCreate@CView@@IEAAHPEAUtagCREATESTRUCTW@@@Z` at `0x14003ab6a`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003ac10`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003ac47`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003ac10`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003ac47`
- `mmcbase!?s_CallDepth@SC@mmcerror@@0IA` at `0x14003a8da`
- `mmcbase!GetStringModule` at `0x14003ab7b`
- `mmcbase!GetStringModule` at `0x14003ab7b`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14003ac05`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14003ac05`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14003a8f6`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14003a8f6`
- `ole32!CoCreateInstance` at `0x14003aab5`
- `ole32!CoCreateInstance` at `0x14003aab5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14003a951`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14003a951`

## string_xrefs

- `0x14003a8eb`: `CAMCListView::OnCreate`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAMCListView::OnCreate(struct FragmentControlProvider **this, struct tagCREATESTRUCTW *a2)
{
  struct AFX_MODULE_STATE *ModuleState; // rax
  HMODULE v5; // rbx
  DWORD idProcess; // eax
  struct FragmentControlProvider *v7; // rcx
  __int64 v8; // rbx
  _QWORD *v9; // r11
  FragmentControlProvider *v10; // rax
  struct FragmentControlProvider *v11; // r15
  _QWORD *v12; // rsi
  HWND *v13; // rbx
  struct FragmentControlProvider *v14; // r9
  int cy; // r8d
  int cx; // edx
  int y; // ecx
  LPVOID *v18; // r14
  LPVOID v19; // rcx
  FragmentControlProvider *v20; // r14
  __int64 v21; // rax
  __int64 v22; // rcx
  struct FragmentControlProvider **v23; // r11
  HWND *v24; // rax
  CSubclassManager *SubclassManager; // rax
  unsigned int v26; // esi
  HINSTANCE StringModule; // rax
  int StringW; // eax
  __int64 v29; // rax
  struct FragmentControlProvider *v31; // [rsp+40h] [rbp-19h] BYREF
  FragmentControlProvider *v32; // [rsp+48h] [rbp-11h] BYREF
  __int64 v33; // [rsp+50h] [rbp-9h] BYREF
  __int128 v34; // [rsp+58h] [rbp-1h]
  struct tagRECT v35; // [rsp+68h] [rbp+Fh] BYREF

  v34 = 0;
  ++mmcerror::SC::s_CallDepth;
  v33 = 3;
  mmcerror::SC::SetFunctionName((mmcerror::SC *)&v33, L"CAMCListView::OnCreate");
  v35 = 0;
  CStatic::Create((CStatic *)(this + 63), &WindowName, 0x50010001u, &v35, (struct CWnd *)this, 0xFFFFu);
  this[37] = GetAMCView((struct CWnd *)this);
  ModuleState = AfxGetModuleState();
  if ( !CAMCListView::s_hObjectFocusChangeHook )
  {
    v5 = (HMODULE)*((_QWORD *)ModuleState + 2);
    idProcess = GetCurrentProcessId();
    CAMCListView::s_hObjectFocusChangeHook = SetWinEventHook(
                                               0x8005u,
                                               0x8006u,
                                               v5,
                                               CAMCListView::WinEventProc,
                                               idProcess,
                                               0,
                                               4u);
  }
  v7 = this[37];
  v31 = (struct FragmentControlProvider *)*((_QWORD *)v7 + 8);
  std::_Tree<std::_Tmap_traits<HNODE__ *,CTreeViewMap::TreeViewMapInfo *,std::less<HNODE__ *>,std::allocator<std::pair<HNODE__ * const,CTreeViewMap::TreeViewMapInfo *>>,0>>::find(
    (char *)v7 + 368,
    &v35,
    &v31);
  v8 = *(_QWORD *)&v35.left;
  if ( *(_QWORD *)&v35.left == *v9 )
  {
    v10 = 0;
  }
  else
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)&v35.left + 48LL) + 8LL))(*(_QWORD *)(*(_QWORD *)&v35.left
                                                                                                  + 48LL));
    v10 = *(FragmentControlProvider **)(v8 + 48);
  }
  v32 = v10;
  v31 = 0;
  ATL::CComObject<EmbeddedListWindowProvider>::CreateInstance(&v31);
  v11 = v31;
  v12 = this + 61;
  this[61] = v31;
  (*(void (__fastcall **)(struct FragmentControlProvider *))(*(_QWORD *)v11 + 8LL))(v11);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*v12 + 8LL) + 72LL))(*v12 + 8LL);
  v13 = (HWND *)(this + 8);
  (*(void (__fastcall **)(_QWORD, struct FragmentControlProvider *, FragmentControlProvider **, __int64, _QWORD, _QWORD))(*(_QWORD *)*v12 + 112LL))(
    *v12,
    this[8],
    &v32,
    1,
    0,
    0);
  v14 = this[61];
  cy = a2->cy;
  cx = a2->cx;
  y = a2->y;
  *((_DWORD *)v14 + 40) = a2->x;
  *((_DWORD *)v14 + 39) = y;
  *((_DWORD *)v14 + 41) = cx;
  *((_DWORD *)v14 + 42) = cy;
  v18 = (LPVOID *)((char *)this[61] + 272);
  v19 = *v18;
  if ( *v18 )
  {
    *v18 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
  }
  CoCreateInstance(&GUID_e22ad333_b25f_460c_83d0_0581107395c9, 0, 1u, &GUID_30cbe57d_d9d0_452a_ab13_7ac5ac4825ee, v18);
  *(_BYTE *)(*v12 + 92LL) = 1;
  v20 = v32;
  v21 = *v12 + 80LL;
  if ( !*v12 )
    v21 = 72;
  *(_QWORD *)&v35.left = *(_QWORD *)v21;
  std::_Tree<std::_Tmap_traits<HNODE__ *,CTreeViewMap::TreeViewMapInfo *,std::less<HNODE__ *>,std::allocator<std::pair<HNODE__ * const,CTreeViewMap::TreeViewMapInfo *>>,0>>::find(
    (char *)v32 + 200,
    &v31,
    &v35);
  if ( v31 == *v23 )
    FragmentControlProvider::appendChild(v20, this + 61);
  v24 = (HWND *)std::map<HWND__ *,CAMCListView::UiProviderContext>::operator[](v22, this + 8);
  *v24 = *v13;
  v24[1] = (HWND)v11;
  (*(void (__fastcall **)(struct FragmentControlProvider *))(*(_QWORD *)v11 + 8LL))(v11);
  this[60] = (struct FragmentControlProvider *)GetWindowLongPtrW(*v13, -4);
  SubclassManager = GetSubclassManager();
  CSubclassManager::SubclassWindow(
    SubclassManager,
    *v13,
    (struct CSubclasser *)((unsigned __int64)(this + 31) & -(__int64)(this != 0)));
  v26 = -1;
  if ( CView::OnCreate((CView *)this, a2) != -1 )
  {
    StringModule = GetStringModule();
    StringW = CStr::LoadStringW((CStr *)(this + 33), StringModule, 0x3461u);
    if ( StringW >= 0 )
    {
      SendMessageW(*v13, 0x1036u, 0, 16432);
      v29 = CMMCViewDropTarget::ScRegisterAsDropTarget(this + 21, &v35, *v13);
      mmcerror::SC::operator=(&v33, v29);
      mmcerror::SC::~SC((mmcerror::SC *)&v35);
      if ( !HIDWORD(v33) || (_DWORD)v33 == 3 && v33 >= 0 )
      {
        _CEventSource<CAMCViewObserver>::_AddObserver(
          (struct CEventSourceBase *)(this + 26),
          (struct FragmentControlProvider *)((char *)this[37] + 240));
        v26 = 0;
      }
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        15,
        WPP_bf2b9f813cf4358b795ac1814230b624_Traceguids,
        (unsigned int)StringW);
    }
  }
  mmcerror::SC::~SC((mmcerror::SC *)&v33);
  return v26;
}

```

## disassembly

```asm
0x14003a8a0  mov     [rsp-8+arg_10], rbx
0x14003a8a5  mov     [rsp-8+arg_18], rsi
0x14003a8aa  push    rbp
0x14003a8ab  push    rdi
0x14003a8ac  push    r13
0x14003a8ae  push    r14
0x14003a8b0  push    r15
0x14003a8b2  lea     rbp, [rsp-37h]
0x14003a8b7  sub     rsp, 90h
0x14003a8be  mov     rax, cs:__security_cookie
0x14003a8c5  xor     rax, rsp
0x14003a8c8  mov     [rbp+57h+var_30], rax
0x14003a8cc  mov     r13, rdx
0x14003a8cf  mov     rdi, rcx
0x14003a8d2  xorps   xmm0, xmm0
0x14003a8d5  movdqu  [rbp+57h+var_58], xmm0
0x14003a8da  mov     rax, cs:__imp_?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x14003a8e1  inc     dword ptr [rax]
0x14003a8e3  mov     [rbp+57h+var_60], 3
0x14003a8eb  lea     rdx, aCamclistviewOn_0; "CAMCListView::OnCreate"
0x14003a8f2  lea     rcx, [rbp+57h+var_60]
0x14003a8f6  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x14003a8fc  xorps   xmm0, xmm0
0x14003a8ff  movups  xmmword ptr [rbp+57h+var_48.left], xmm0
0x14003a903  lea     rcx, [rdi+1F8h]
0x14003a90a  mov     [rsp+0B0h+idThread], 0FFFFh
0x14003a912  mov     qword ptr [rsp+0B0h+idProcess], rdi
0x14003a917  lea     r9, [rbp+57h+var_48]
0x14003a91b  mov     r8d, 50010001h
0x14003a921  lea     rdx, WindowName
0x14003a928  call    cs:__imp_?Create@CStatic@@QEAAHPEBGKAEBUtagRECT@@PEAVCWnd@@I@Z; CStatic::Create(ushort const *,ulong,tagRECT const &,CWnd *,uint)
0x14003a92e  mov     rcx, rdi; struct CWnd *
0x14003a931  call    ?GetAMCView@@YAPEAVCAMCView@@PEAVCWnd@@@Z; GetAMCView(CWnd *)
0x14003a936  mov     [rdi+128h], rax
0x14003a93d  call    cs:__imp_?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x14003a943  cmp     cs:?s_hObjectFocusChangeHook@CAMCListView@@0PEAUHWINEVENTHOOK__@@EA, 0; HWINEVENTHOOK__ * CAMCListView::s_hObjectFocusChangeHook
0x14003a94b  jnz     short loc_14003A98A
0x14003a94d  mov     rbx, [rax+10h]
0x14003a951  call    cs:__imp_GetCurrentProcessId
0x14003a957  mov     [rsp+0B0h+dwFlags], 4; dwFlags
0x14003a95f  mov     [rsp+0B0h+idThread], 0; idThread
0x14003a967  mov     [rsp+0B0h+idProcess], eax; idProcess
0x14003a96b  lea     r9, ?WinEventProc@CAMCListView@@SAXPEAUHWINEVENTHOOK__@@KPEAUHWND__@@JJKK@Z; pfnWinEventProc
0x14003a972  mov     r8, rbx; hmodWinEventProc
0x14003a975  mov     edx, 8006h; eventMax
0x14003a97a  lea     ecx, [rdx-1]; eventMin
0x14003a97d  call    cs:__imp_SetWinEventHook
0x14003a983  mov     cs:?s_hObjectFocusChangeHook@CAMCListView@@0PEAUHWINEVENTHOOK__@@EA, rax; HWINEVENTHOOK__ * CAMCListView::s_hObjectFocusChangeHook
0x14003a98a  mov     rcx, [rdi+128h]
0x14003a991  mov     rax, [rcx+40h]
0x14003a995  mov     [rbp+57h+var_70], rax
0x14003a999  lea     r11, [rcx+170h]
0x14003a9a0  lea     r8, [rbp+57h+var_70]
0x14003a9a4  lea     rdx, [rbp+57h+var_48]
0x14003a9a8  mov     rcx, r11
0x14003a9ab  call    ?find@?$_Tree@V?$_Tmap_traits@PEAUHNODE__@@PEAUTreeViewMapInfo@CTreeViewMap@@U?$less@PEAUHNODE__@@@std@@V?$allocator@U?$pair@QEAUHNODE__@@PEAUTreeViewMapInfo@CTreeViewMap@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUHNODE__@@PEAUTreeViewMapInfo@CTreeViewMap@@@std@@@std@@@std@@@2@AEBQEAUHNODE__@@@Z; std::_Tree<std::_Tmap_traits<HNODE__ *,CTreeViewMap::TreeViewMapInfo *,std::less<HNODE__ *>,std::allocator<std::pair<HNODE__ * const,CTreeViewMap::TreeViewMapInfo *>>,0>>::find(HNODE__ * const &)
0x14003a9b0  mov     rbx, qword ptr [rbp+57h+var_48.left]
0x14003a9b4  cmp     rbx, [r11]
0x14003a9b7  jnz     short loc_14003A9BD
0x14003a9b9  xor     eax, eax
0x14003a9bb  jmp     short loc_14003A9D1
0x14003a9bd  mov     rcx, [rbx+30h]
0x14003a9c1  mov     rax, [rcx]
0x14003a9c4  mov     rax, [rax+8]
0x14003a9c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a9cd  mov     rax, [rbx+30h]
0x14003a9d1  mov     [rbp+57h+var_68], rax
0x14003a9d5  mov     [rbp+57h+var_70], 0
0x14003a9dd  lea     rcx, [rbp+57h+var_70]
0x14003a9e1  call    ?CreateInstance@?$CComObject@VEmbeddedListWindowProvider@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<EmbeddedListWindowProvider>::CreateInstance(ATL::CComObject<EmbeddedListWindowProvider> * *)
0x14003a9e6  mov     r15, [rbp+57h+var_70]
0x14003a9ea  lea     rsi, [rdi+1E8h]
0x14003a9f1  mov     [rsi], r15
0x14003a9f4  mov     rax, [r15]
0x14003a9f7  mov     rcx, r15
0x14003a9fa  mov     rax, [rax+8]
0x14003a9fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003aa03  mov     rcx, [rsi]
0x14003aa06  add     rcx, 8
0x14003aa0a  mov     rax, [rcx]
0x14003aa0d  mov     rax, [rax+48h]
0x14003aa11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003aa16  mov     rcx, [rsi]
0x14003aa19  lea     rbx, [rdi+40h]
0x14003aa1d  mov     rax, [rcx]
0x14003aa20  mov     qword ptr [rsp+0B0h+idThread], 0
0x14003aa29  mov     qword ptr [rsp+0B0h+idProcess], 0
0x14003aa32  mov     r9d, 1
0x14003aa38  lea     r8, [rbp+57h+var_68]
0x14003aa3c  mov     rdx, [rbx]
0x14003aa3f  mov     rax, [rax+70h]
0x14003aa43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003aa48  mov     r9, [rsi]
0x14003aa4b  mov     r8d, [r13+20h]
0x14003aa4f  mov     edx, [r13+24h]
0x14003aa53  mov     ecx, [r13+28h]
0x14003aa57  mov     eax, [r13+2Ch]
0x14003aa5b  mov     [r9+0A0h], eax
0x14003aa62  mov     [r9+9Ch], ecx
0x14003aa69  mov     [r9+0A4h], edx
0x14003aa70  mov     [r9+0A8h], r8d
0x14003aa77  mov     r14, [rsi]
0x14003aa7a  add     r14, 110h
0x14003aa81  mov     rcx, [r14]
0x14003aa84  test    rcx, rcx
0x14003aa87  jz      short loc_14003AA9C
0x14003aa89  mov     qword ptr [r14], 0
0x14003aa90  mov     rax, [rcx]
0x14003aa93  mov     rax, [rax+10h]
0x14003aa97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003aa9c  mov     qword ptr [rsp+0B0h+idProcess], r14; ppv
0x14003aaa1  lea     r9, _GUID_30cbe57d_d9d0_452a_ab13_7ac5ac4825ee; riid
0x14003aaa8  xor     edx, edx; pUnkOuter
0x14003aaaa  lea     r8d, [rdx+1]; dwClsContext
0x14003aaae  lea     rcx, _GUID_e22ad333_b25f_460c_83d0_0581107395c9; rclsid
0x14003aab5  call    cs:__imp_CoCreateInstance
0x14003aabb  mov     rax, [rsi]
0x14003aabe  mov     byte ptr [rax+5Ch], 1
0x14003aac2  mov     rdx, [rsi]
0x14003aac5  mov     r14, [rbp+57h+var_68]
0x14003aac9  lea     rax, [rdx+50h]
0x14003aacd  mov     ecx, 48h ; 'H'
0x14003aad2  test    rdx, rdx
0x14003aad5  cmovz   rax, rcx
0x14003aad9  mov     rax, [rax]
0x14003aadc  mov     qword ptr [rbp+57h+var_48.left], rax
0x14003aae0  lea     r11, [r14+0C8h]
0x14003aae7  lea     r8, [rbp+57h+var_48]
0x14003aaeb  lea     rdx, [rbp+57h+var_70]
0x14003aaef  mov     rcx, r11
0x14003aaf2  call    ?find@?$_Tree@V?$_Tmap_traits@PEAUHNODE__@@PEAUTreeViewMapInfo@CTreeViewMap@@U?$less@PEAUHNODE__@@@std@@V?$allocator@U?$pair@QEAUHNODE__@@PEAUTreeViewMapInfo@CTreeViewMap@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUHNODE__@@PEAUTreeViewMapInfo@CTreeViewMap@@@std@@@std@@@std@@@2@AEBQEAUHNODE__@@@Z; std::_Tree<std::_Tmap_traits<HNODE__ *,CTreeViewMap::TreeViewMapInfo *,std::less<HNODE__ *>,std::allocator<std::pair<HNODE__ * const,CTreeViewMap::TreeViewMapInfo *>>,0>>::find(HNODE__ * const &)
0x14003aaf7  mov     rdx, [r11]
0x14003aafa  cmp     [rbp+57h+var_70], rdx
0x14003aafe  jnz     short loc_14003AB0B
0x14003ab00  mov     rdx, rsi; struct FragmentControlProvider **
0x14003ab03  mov     rcx, r14; this
0x14003ab06  call    ?appendChild@FragmentControlProvider@@QEAAXPEAPEAV1@@Z; FragmentControlProvider::appendChild(FragmentControlProvider * *)
0x14003ab0b  mov     rdx, rbx
0x14003ab0e  call    ??A?$map@PEAUHWND__@@UUiProviderContext@CAMCListView@@U?$less@PEAUHWND__@@@std@@V?$allocator@U?$pair@QEAUHWND__@@UUiProviderContext@CAMCListView@@@std@@@5@@std@@QEAAAEAUUiProviderContext@CAMCListView@@AEBQEAUHWND__@@@Z; std::map<HWND__ *,CAMCListView::UiProviderContext>::operator[](HWND__ * const &)
0x14003ab13  mov     rdx, [rbx]
0x14003ab16  mov     [rax], rdx
0x14003ab19  mov     [rax+8], r15
0x14003ab1d  mov     rax, [r15]
0x14003ab20  mov     rcx, r15
0x14003ab23  mov     rax, [rax+8]
0x14003ab27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ab2c  mov     edx, 0FFFFFFFCh; nIndex
0x14003ab31  mov     rcx, [rbx]; hWnd
0x14003ab34  call    cs:__imp_GetWindowLongPtrW
0x14003ab3a  mov     [rdi+1E0h], rax
0x14003ab41  call    ?GetSubclassManager@@YAAEAVCSubclassManager@@XZ; GetSubclassManager(void)
0x14003ab46  mov     rcx, rdi
0x14003ab49  lea     r9, [rdi+0F8h]
0x14003ab50  neg     rcx
0x14003ab53  sbb     r8, r8
0x14003ab56  and     r8, r9; struct CSubclasser *
0x14003ab59  mov     rdx, [rbx]; HWND
0x14003ab5c  mov     rcx, rax; this
0x14003ab5f  call    ?SubclassWindow@CSubclassManager@@QEAA_NPEAUHWND__@@PEAVCSubclasser@@@Z; CSubclassManager::SubclassWindow(HWND__ *,CSubclasser *)
0x14003ab64  mov     rdx, r13
0x14003ab67  mov     rcx, rdi
0x14003ab6a  call    cs:__imp_?OnCreate@CView@@IEAAHPEAUtagCREATESTRUCTW@@@Z; CView::OnCreate(tagCREATESTRUCTW *)
0x14003ab70  or      esi, 0FFFFFFFFh
0x14003ab73  cmp     eax, esi
0x14003ab75  jz      loc_14003AC43
0x14003ab7b  call    cs:__imp_?GetStringModule@@YAPEAUHINSTANCE__@@XZ; GetStringModule(void)
0x14003ab81  mov     rdx, rax; hInstance
0x14003ab84  lea     rcx, [rdi+108h]; this
0x14003ab8b  mov     r8d, 3461h; uID
0x14003ab91  call    ?LoadStringW@CStr@@QEAAJPEAUHINSTANCE__@@I@Z; CStr::LoadStringW(HINSTANCE__ *,uint)
0x14003ab96  test    eax, eax
0x14003ab98  jns     short loc_14003ABD3
0x14003ab9a  lea     rdx, WPP_GLOBAL_Control
0x14003aba1  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aba8  cmp     rcx, rdx
0x14003abab  jz      loc_14003AC43
0x14003abb1  cmp     byte ptr [rcx+19h], 2
0x14003abb5  jb      loc_14003AC43
0x14003abbb  lea     edx, [rsi+10h]
0x14003abbe  mov     r9d, eax
0x14003abc1  lea     r8, WPP_bf2b9f813cf4358b795ac1814230b624_Traceguids
0x14003abc8  mov     rcx, [rcx+10h]
0x14003abcc  call    WPP_SF_d
0x14003abd1  jmp     short loc_14003AC43
0x14003abd3  mov     r9d, 4030h; lParam
0x14003abd9  xor     r8d, r8d; wParam
0x14003abdc  mov     edx, 1036h; Msg
0x14003abe1  mov     rcx, [rbx]; hWnd
0x14003abe4  call    cs:__imp_SendMessageW
0x14003abea  lea     rcx, [rdi+0A8h]
0x14003abf1  mov     r8, [rbx]
0x14003abf4  lea     rdx, [rbp+57h+var_48]
0x14003abf8  call    ?ScRegisterAsDropTarget@CMMCViewDropTarget@@IEAA?AVSC@mmcerror@@PEAUHWND__@@@Z; CMMCViewDropTarget::ScRegisterAsDropTarget(HWND__ *)
0x14003abfd  nop
0x14003abfe  mov     rdx, rax
0x14003ac01  lea     rcx, [rbp+57h+var_60]
0x14003ac05  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x14003ac0b  nop
0x14003ac0c  lea     rcx, [rbp+57h+var_48]
0x14003ac10  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14003ac16  mov     eax, dword ptr [rbp+57h+var_60+4]
0x14003ac19  test    eax, eax
0x14003ac1b  jz      short loc_14003AC27
0x14003ac1d  cmp     dword ptr [rbp+57h+var_60], 3
0x14003ac21  jnz     short loc_14003AC43
0x14003ac23  test    eax, eax
0x14003ac25  js      short loc_14003AC43
0x14003ac27  mov     rdx, [rdi+128h]
0x14003ac2e  add     rdx, 0F0h; this
0x14003ac35  lea     rcx, [rdi+0D0h]; struct CEventSourceBase *
0x14003ac3c  call    ?_AddObserver@?$_CEventSource@VCAMCViewObserver@@@@QEAAXAEAVCAMCViewObserver@@@Z; _CEventSource<CAMCViewObserver>::_AddObserver(CAMCViewObserver &)
0x14003ac41  xor     esi, esi
0x14003ac43  lea     rcx, [rbp+57h+var_60]
0x14003ac47  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14003ac4d  mov     eax, esi
0x14003ac4f  mov     rcx, [rbp+57h+var_30]
0x14003ac53  xor     rcx, rsp; StackCookie
0x14003ac56  call    __security_check_cookie
0x14003ac5b  lea     r11, [rsp+0B0h+var_20]
0x14003ac63  mov     rbx, [r11+40h]
0x14003ac67  mov     rsi, [r11+48h]
0x14003ac6b  mov     rsp, r11
0x14003ac6e  pop     r15
0x14003ac70  pop     r14
0x14003ac72  pop     r13
0x14003ac74  pop     rdi
0x14003ac75  pop     rbp
0x14003ac76  retn
```
