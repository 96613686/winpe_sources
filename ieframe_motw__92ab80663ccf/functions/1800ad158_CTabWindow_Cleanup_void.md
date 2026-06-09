# CTabWindow::_Cleanup(void)

- ea: `0x1800ad158`
- end: `0x1800ad5e9`
- name: `?_Cleanup@CTabWindow@@AEAAXXZ`
- size: `1169`
- prototype: `void __fastcall(CTabWindow *__hidden this)`
- caller_count: `3`
- callee_count: `23`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18026e684`
- `0x180274870`
- `0x18027b1ec`

## callees

- `0x1800096a0`
- `0x18001546c`
- `0x18009ce20`
- `0x1800ad158`
- `0x1800ad5f0`
- `0x1800ad624`
- `0x18026ffc4`
- `0x18027637c`
- `0x18027680c`
- `0x18027843c`
- `0x18027abb0`
- `0x18027b564`
- `0x180280c7c`
- `0x180282ad4`
- `0x180282f38`
- `0x1802961e0`
- `0x18029654c`
- `0x1802ab128`
- `0x1802ab984`
- `0x18042fa04`
- `0x180591ef6`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800ad264`
- `KERNEL32!SetEvent` at `0x1800ad264`
- `KERNEL32!CloseHandle` at `0x1800ad277`
- `KERNEL32!CloseHandle` at `0x1800ad332`
- `KERNEL32!CloseHandle` at `0x1800ad546`
- `KERNEL32!CloseHandle` at `0x1800ad277`
- `KERNEL32!CloseHandle` at `0x1800ad332`
- `KERNEL32!CloseHandle` at `0x1800ad546`
- `USER32!DestroyWindow` at `0x1800ad3da`
- `USER32!DestroyWindow` at `0x1800ad3f9`
- `USER32!DestroyWindow` at `0x1800ad3da`
- `USER32!DestroyWindow` at `0x1800ad3f9`
- `USER32!KillTimer` at `0x1800ad2b4`
- `USER32!KillTimer` at `0x1800ad2b4`
- `SHELL32!__imp_ILFree` at `0x1800ad2c7`
- `SHELL32!__imp_ILFree` at `0x1800ad2e1`
- `SHELL32!__imp_ILFree` at `0x1800ad5a6`
- `SHELL32!__imp_ILFree` at `0x1800ad2c7`
- `SHELL32!__imp_ILFree` at `0x1800ad2e1`
- `SHELL32!__imp_ILFree` at `0x1800ad5a6`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x1800ad50f`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x1800ad50f`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1800ad1cd`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1800ad1ec`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1800ad20b`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1800ad22a`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1800ad587`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1800ad1cd`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1800ad1ec`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1800ad20b`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1800ad22a`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1800ad587`
- `msIso!__imp_?IsoRemoveComponentDependenciesWithFlag@@YAJKW4_IsoComponentDependencyFlags@@@Z` at `0x1800ad24c`
- `msIso!__imp_?IsoRemoveComponentDependenciesWithFlag@@YAJKW4_IsoComponentDependencyFlags@@@Z` at `0x1800ad24c`

## pseudocode

```c
void __fastcall CTabWindow::_Cleanup(CTabWindow *this)
{
  int v1; // r8d
  CTabWindowManager **v2; // rdi
  char *v4; // rdx
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rcx
  __int64 v9; // rcx
  void *v10; // rcx
  unsigned int v11; // eax
  HWND v12; // rcx
  ITEMIDLIST *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  struct INavigationBand *v16; // r8
  int v17; // r9d
  __int64 v18; // rcx
  __int64 v19; // rcx
  HWND v20; // rcx
  HWND v21; // rcx
  bool v22; // zf
  CNotificationSqmListener *v23; // rcx
  struct ITabRecoveryData *v24; // rdx
  struct ITabRecoveryData *v25; // rdx
  void *v26; // rcx
  unsigned __int64 v27; // rcx
  ITEMIDLIST *v28; // rcx
  _DWORD v29[6]; // [rsp+30h] [rbp-28h] BYREF

  v1 = *((_DWORD *)this + 105);
  v2 = (CTabWindowManager **)((char *)this + 480);
  if ( v1 != -1 && *v2 )
    CTabWindowManager::VirtualTab_CommitToNewTab(*v2, *((_DWORD *)this + 60), v1);
  v4 = (char *)*((unsigned int *)this + 104);
  if ( (_DWORD)v4 != -1 && *v2 )
    CTabWindowManager::VirtualTab_RevertToOldTab(*v2, v4, *((_DWORD *)this + 60));
  v5 = *((_QWORD *)this + 55);
  if ( v5 )
  {
    IsoRemoveDependency(v5);
    *((_QWORD *)this + 55) = 0;
  }
  v6 = *((_QWORD *)this + 56);
  if ( v6 )
  {
    IsoRemoveDependency(v6);
    *((_QWORD *)this + 56) = 0;
  }
  v7 = *((_QWORD *)this + 1741);
  if ( v7 )
  {
    IsoRemoveDependency(v7);
    *((_QWORD *)this + 1741) = 0;
  }
  v8 = *((_QWORD *)this + 1742);
  if ( v8 )
  {
    IsoRemoveDependency(v8);
    *((_QWORD *)this + 1742) = 0;
  }
  v9 = *((unsigned int *)this + 3509);
  if ( (_DWORD)v9 )
    IsoRemoveComponentDependenciesWithFlag(v9, 16);
  v10 = (void *)*((_QWORD *)this + 53);
  if ( v10 )
  {
    SetEvent(v10);
    CloseHandle(*((HANDLE *)this + 53));
    *((_QWORD *)this + 53) = 0;
  }
  CTabWindow::SetFullViewportVideo(this, 0);
  CTabWindow::_DestroyDetachedBrowserTabUI(this);
  v11 = *((_DWORD *)this + 3413);
  if ( v11 )
  {
    v12 = (HWND)*((_QWORD *)this + 44);
    if ( v12 )
      KillTimer(v12, v11);
  }
  ILFree(*((LPITEMIDLIST *)this + 62));
  v13 = (ITEMIDLIST *)*((_QWORD *)this + 1693);
  *((_QWORD *)this + 62) = 0;
  ILFree(v13);
  *((_QWORD *)this + 1693) = 0;
  ATL::CComPtr<IPrivacIEDatabase>::Release((char *)this + 13552);
  operator delete(*((void **)this + 1762));
  v14 = (void *)*((_QWORD *)this + 1763);
  *((_QWORD *)this + 1762) = 0;
  operator delete(v14);
  v15 = (void *)*((_QWORD *)this + 1761);
  *((_QWORD *)this + 1763) = 0;
  if ( v15 )
  {
    CloseHandle(v15);
    *((_QWORD *)this + 1761) = 0;
  }
  if ( *((_QWORD *)this + 1722) )
    CTabWindow::PrepareNewFrame(this, 0, 0);
  CTabWindow::_OnBrowserPreparedToDehydrate(this);
  v18 = *((_QWORD *)this + 1728);
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 40LL))(v18);
    v19 = *((_QWORD *)this + 1728);
    if ( v19 )
    {
      *((_QWORD *)this + 1728) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
  }
  CNavigationTargetImpl::ChainNavigationTarget((CTabWindow *)((char *)this + 64), 0, v16, v17);
  ATL::CComPtr<IPrivacIEDatabase>::Release((char *)this + 472);
  ATL::CComPtr<IPrivacIEDatabase>::Release((char *)this + 464);
  CTabWindow::_StopHungTabHeartbeat(this);
  if ( LCIEFrameTabWindow() )
  {
    v20 = (HWND)*((_QWORD *)this + 44);
    if ( v20 )
    {
      DestroyWindow(v20);
      *((_QWORD *)this + 44) = 0;
    }
    v21 = (HWND)*((_QWORD *)this + 45);
    if ( v21 )
    {
      DestroyWindow(v21);
      *((_QWORD *)this + 45) = 0;
    }
  }
  v22 = *((_DWORD *)this + 3479) == 1;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 46) = 0;
  if ( !v22 )
  {
    v23 = (CNotificationSqmListener *)*((_QWORD *)this + 1729);
    if ( v23 )
    {
      CNotificationSqmListener::UnInitialize(v23);
      CNotificationSqmListener::Release(*((CNotificationSqmListener **)this + 1729));
      *((_QWORD *)this + 1729) = 0;
    }
    if ( !(unsigned int)CTabWindow::ReceivedEndSession(this) )
    {
      v24 = (struct ITabRecoveryData *)*((_QWORD *)this + 1713);
      if ( v24 )
      {
        CTabWindow::_CleanUpRecoveryData(this, v24);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1713) + 16LL))(*((_QWORD *)this + 1713));
        *((_QWORD *)this + 1713) = 0;
      }
      v25 = (struct ITabRecoveryData *)*((_QWORD *)this + 1714);
      if ( v25 )
      {
        CTabWindow::_CleanUpRecoveryData(this, v25);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1714) + 16LL))(*((_QWORD *)this + 1714));
        *((_QWORD *)this + 1714) = 0;
      }
    }
    if ( *((_DWORD *)this + 3510) )
    {
      v29[1] = *((_DWORD *)this + 3510);
      v29[2] = *((_DWORD *)this + 3511);
      v29[3] = *((_DWORD *)this + 3509);
      v29[4] = *((_DWORD *)this + 62);
      v29[0] = 2;
      (*(void (__fastcall **)(struct IESubscriptionManager *, __int64, _DWORD *))(*(_QWORD *)g_pIEProcessSubscriptionManager
                                                                                + 48LL))(
        g_pIEProcessSubscriptionManager,
        2,
        v29);
      IsoRemoveArtifact(*((_DWORD *)this + 3510));
      *((_DWORD *)this + 3510) = 0;
    }
    IUnknown_SafeReleaseAndNullPtr<CTabWindowManager>(v2);
    if ( *((_DWORD *)this + 3479) != 2 )
      CTabWindow::_Uninitialize(this);
  }
  v26 = (void *)*((_QWORD *)this + 32);
  if ( v26 )
  {
    CloseHandle(v26);
    *((_QWORD *)this + 32) = 0;
  }
  ATL::CComPtr<IPrivacIEDatabase>::Release((char *)this + 14056);
  CTabWindow::_SetBrowserTabComponentHandle(this, 0);
  CTabDropTargetManager::Disconnect((CTabWindow *)((char *)this + 13808));
  v27 = *((_QWORD *)this + 1743);
  if ( v27 )
  {
    IsoRemoveDependency(v27);
    *((_QWORD *)this + 1743) = 0;
  }
  v28 = (ITEMIDLIST *)*((_QWORD *)this + 1744);
  if ( v28 )
  {
    ILFree(v28);
    *((_QWORD *)this + 1744) = 0;
    memset_0((char *)this + 13960, 0, 0x48u);
  }
}

```

## disassembly

```asm
0x1800ad158  mov     [rsp+arg_8], rbx
0x1800ad15d  mov     [rsp+arg_10], rsi
0x1800ad162  push    rdi
0x1800ad163  sub     rsp, 50h
0x1800ad167  mov     rax, cs:__security_cookie
0x1800ad16e  xor     rax, rsp
0x1800ad171  mov     [rsp+58h+var_10], rax
0x1800ad176  mov     r8d, [rcx+1A4h]; int
0x1800ad17d  lea     rdi, [rcx+1E0h]
0x1800ad184  xor     esi, esi
0x1800ad186  mov     rbx, rcx
0x1800ad189  cmp     r8d, 0FFFFFFFFh
0x1800ad18d  jz      short loc_1800AD1A2
0x1800ad18f  mov     rcx, [rdi]; this
0x1800ad192  test    rcx, rcx
0x1800ad195  jz      short loc_1800AD1A2
0x1800ad197  mov     edx, [rbx+0F0h]; int
0x1800ad19d  call    ?VirtualTab_CommitToNewTab@CTabWindowManager@@QEAAJJJ@Z; CTabWindowManager::VirtualTab_CommitToNewTab(long,long)
0x1800ad1a2  mov     edx, [rbx+1A0h]; char *
0x1800ad1a8  cmp     edx, 0FFFFFFFFh
0x1800ad1ab  jz      short loc_1800AD1C1
0x1800ad1ad  mov     rcx, [rdi]; this
0x1800ad1b0  test    rcx, rcx
0x1800ad1b3  jz      short loc_1800AD1C1
0x1800ad1b5  mov     r8d, [rbx+0F0h]; int
0x1800ad1bc  call    ?VirtualTab_RevertToOldTab@CTabWindowManager@@QEAAJJJ@Z; CTabWindowManager::VirtualTab_RevertToOldTab(long,long)
0x1800ad1c1  mov     rcx, [rbx+1B8h]
0x1800ad1c8  test    rcx, rcx
0x1800ad1cb  jz      short loc_1800AD1E0
0x1800ad1cd  call    cs:__imp_?IsoRemoveDependency@@YAJ_K@Z; IsoRemoveDependency(unsigned __int64)
0x1800ad1d4  nop     dword ptr [rax+rax+00h]
0x1800ad1d9  mov     [rbx+1B8h], rsi
0x1800ad1e0  mov     rcx, [rbx+1C0h]
0x1800ad1e7  test    rcx, rcx
0x1800ad1ea  jz      short loc_1800AD1FF
0x1800ad1ec  call    cs:__imp_?IsoRemoveDependency@@YAJ_K@Z; IsoRemoveDependency(unsigned __int64)
0x1800ad1f3  nop     dword ptr [rax+rax+00h]
0x1800ad1f8  mov     [rbx+1C0h], rsi
0x1800ad1ff  mov     rcx, [rbx+3668h]
0x1800ad206  test    rcx, rcx
0x1800ad209  jz      short loc_1800AD21E
0x1800ad20b  call    cs:__imp_?IsoRemoveDependency@@YAJ_K@Z; IsoRemoveDependency(unsigned __int64)
0x1800ad212  nop     dword ptr [rax+rax+00h]
0x1800ad217  mov     [rbx+3668h], rsi
0x1800ad21e  mov     rcx, [rbx+3670h]
0x1800ad225  test    rcx, rcx
0x1800ad228  jz      short loc_1800AD23D
0x1800ad22a  call    cs:__imp_?IsoRemoveDependency@@YAJ_K@Z; IsoRemoveDependency(unsigned __int64)
0x1800ad231  nop     dword ptr [rax+rax+00h]
0x1800ad236  mov     [rbx+3670h], rsi
0x1800ad23d  mov     ecx, [rbx+36D4h]
0x1800ad243  test    ecx, ecx
0x1800ad245  jz      short loc_1800AD258
0x1800ad247  mov     edx, 10h
0x1800ad24c  call    cs:__imp_?IsoRemoveComponentDependenciesWithFlag@@YAJKW4_IsoComponentDependencyFlags@@@Z; IsoRemoveComponentDependenciesWithFlag(ulong,_IsoComponentDependencyFlags)
0x1800ad253  nop     dword ptr [rax+rax+00h]
0x1800ad258  mov     rcx, [rbx+1A8h]; hEvent
0x1800ad25f  test    rcx, rcx
0x1800ad262  jz      short loc_1800AD28A
0x1800ad264  call    cs:__imp_SetEvent
0x1800ad26b  nop     dword ptr [rax+rax+00h]
0x1800ad270  mov     rcx, [rbx+1A8h]; hObject
0x1800ad277  call    cs:__imp_CloseHandle
0x1800ad27e  nop     dword ptr [rax+rax+00h]
0x1800ad283  mov     [rbx+1A8h], rsi
0x1800ad28a  xor     edx, edx; bool
0x1800ad28c  mov     rcx, rbx; this
0x1800ad28f  call    ?SetFullViewportVideo@CTabWindow@@QEAAX_N@Z; CTabWindow::SetFullViewportVideo(bool)
0x1800ad294  mov     rcx, rbx; this
0x1800ad297  call    ?_DestroyDetachedBrowserTabUI@CTabWindow@@AEAAXXZ; CTabWindow::_DestroyDetachedBrowserTabUI(void)
0x1800ad29c  mov     eax, [rbx+3554h]
0x1800ad2a2  test    eax, eax
0x1800ad2a4  jz      short loc_1800AD2C0
0x1800ad2a6  mov     rcx, [rbx+160h]; hWnd
0x1800ad2ad  test    rcx, rcx
0x1800ad2b0  jz      short loc_1800AD2C0
0x1800ad2b2  mov     edx, eax; uIDEvent
0x1800ad2b4  call    cs:__imp_KillTimer
0x1800ad2bb  nop     dword ptr [rax+rax+00h]
0x1800ad2c0  mov     rcx, [rbx+1F0h]; pidl
0x1800ad2c7  call    cs:__imp_ILFree
0x1800ad2ce  nop     dword ptr [rax+rax+00h]
0x1800ad2d3  mov     rcx, [rbx+34E8h]; pidl
0x1800ad2da  mov     [rbx+1F0h], rsi
0x1800ad2e1  call    cs:__imp_ILFree
0x1800ad2e8  nop     dword ptr [rax+rax+00h]
0x1800ad2ed  lea     rcx, [rbx+34F0h]
0x1800ad2f4  mov     [rbx+34E8h], rsi
0x1800ad2fb  call    ?Release@?$CComPtr@UIPrivacIEDatabase@@@ATL@@QEAAXXZ; ATL::CComPtr<IPrivacIEDatabase>::Release(void)
0x1800ad300  mov     rcx, [rbx+3710h]; lpMem
0x1800ad307  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ad30c  mov     rcx, [rbx+3718h]; lpMem
0x1800ad313  mov     [rbx+3710h], rsi
0x1800ad31a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ad31f  mov     rcx, [rbx+3708h]; hObject
0x1800ad326  mov     [rbx+3718h], rsi
0x1800ad32d  test    rcx, rcx
0x1800ad330  jz      short loc_1800AD345
0x1800ad332  call    cs:__imp_CloseHandle
0x1800ad339  nop     dword ptr [rax+rax+00h]
0x1800ad33e  mov     [rbx+3708h], rsi
0x1800ad345  cmp     [rbx+35D0h], rsi
0x1800ad34c  jz      short loc_1800AD35B
0x1800ad34e  xor     r8d, r8d; bool
0x1800ad351  xor     edx, edx; bool
0x1800ad353  mov     rcx, rbx; this
0x1800ad356  call    ?PrepareNewFrame@CTabWindow@@QEAAJ_N0@Z; CTabWindow::PrepareNewFrame(bool,bool)
0x1800ad35b  mov     rcx, rbx; this
0x1800ad35e  call    ?_OnBrowserPreparedToDehydrate@CTabWindow@@AEAAJXZ; CTabWindow::_OnBrowserPreparedToDehydrate(void)
0x1800ad363  mov     rcx, [rbx+3600h]
0x1800ad36a  test    rcx, rcx
0x1800ad36d  jz      short loc_1800AD39A
0x1800ad36f  mov     rax, [rcx]
0x1800ad372  mov     rax, [rax+28h]
0x1800ad376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad37b  mov     rcx, [rbx+3600h]
0x1800ad382  test    rcx, rcx
0x1800ad385  jz      short loc_1800AD39A
0x1800ad387  mov     [rbx+3600h], rsi
0x1800ad38e  mov     rax, [rcx]
0x1800ad391  mov     rax, [rax+10h]
0x1800ad395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad39a  lea     rcx, [rbx+40h]; this
0x1800ad39e  xor     edx, edx; struct IServiceProvider *
0x1800ad3a0  call    ?ChainNavigationTarget@CNavigationTargetImpl@@IEAAJPEAUIServiceProvider@@PEAUINavigationBand@@H@Z; CNavigationTargetImpl::ChainNavigationTarget(IServiceProvider *,INavigationBand *,int)
0x1800ad3a5  lea     rcx, [rbx+1D8h]
0x1800ad3ac  call    ?Release@?$CComPtr@UIPrivacIEDatabase@@@ATL@@QEAAXXZ; ATL::CComPtr<IPrivacIEDatabase>::Release(void)
0x1800ad3b1  lea     rcx, [rbx+1D0h]
0x1800ad3b8  call    ?Release@?$CComPtr@UIPrivacIEDatabase@@@ATL@@QEAAXXZ; ATL::CComPtr<IPrivacIEDatabase>::Release(void)
0x1800ad3bd  mov     rcx, rbx; this
0x1800ad3c0  call    ?_StopHungTabHeartbeat@CTabWindow@@AEAAXXZ; CTabWindow::_StopHungTabHeartbeat(void)
0x1800ad3c5  call    ?LCIEFrameTabWindow@@YA_NXZ; LCIEFrameTabWindow(void)
0x1800ad3ca  test    al, al
0x1800ad3cc  jz      short loc_1800AD40C
0x1800ad3ce  mov     rcx, [rbx+160h]; hWnd
0x1800ad3d5  test    rcx, rcx
0x1800ad3d8  jz      short loc_1800AD3ED
0x1800ad3da  call    cs:__imp_DestroyWindow
0x1800ad3e1  nop     dword ptr [rax+rax+00h]
0x1800ad3e6  mov     [rbx+160h], rsi
0x1800ad3ed  mov     rcx, [rbx+168h]; hWnd
0x1800ad3f4  test    rcx, rcx
0x1800ad3f7  jz      short loc_1800AD40C
0x1800ad3f9  call    cs:__imp_DestroyWindow
0x1800ad400  nop     dword ptr [rax+rax+00h]
0x1800ad405  mov     [rbx+168h], rsi
0x1800ad40c  cmp     dword ptr [rbx+365Ch], 1
0x1800ad413  mov     [rbx+158h], rsi
0x1800ad41a  mov     [rbx+170h], rsi
0x1800ad421  jz      loc_1800AD53A
0x1800ad427  mov     rcx, [rbx+3608h]; this
0x1800ad42e  test    rcx, rcx
0x1800ad431  jz      short loc_1800AD44B
0x1800ad433  call    ?UnInitialize@CNotificationSqmListener@@QEAAXXZ; CNotificationSqmListener::UnInitialize(void)
0x1800ad438  mov     rcx, [rbx+3608h]; this
0x1800ad43f  call    ?Release@CNotificationSqmListener@@UEAAKXZ; CNotificationSqmListener::Release(void)
0x1800ad444  mov     [rbx+3608h], rsi
0x1800ad44b  mov     rcx, rbx; this
0x1800ad44e  call    ?ReceivedEndSession@CTabWindow@@QEBAHXZ; CTabWindow::ReceivedEndSession(void)
0x1800ad453  test    eax, eax
0x1800ad455  jnz     short loc_1800AD4B3
0x1800ad457  mov     rdx, [rbx+3588h]; struct ITabRecoveryData *
0x1800ad45e  test    rdx, rdx
0x1800ad461  jz      short loc_1800AD485
0x1800ad463  mov     rcx, rbx; this
0x1800ad466  call    ?_CleanUpRecoveryData@CTabWindow@@AEAAXPEAUITabRecoveryData@@@Z; CTabWindow::_CleanUpRecoveryData(ITabRecoveryData *)
0x1800ad46b  mov     rcx, [rbx+3588h]
0x1800ad472  mov     rax, [rcx]
0x1800ad475  mov     rax, [rax+10h]
0x1800ad479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad47e  mov     [rbx+3588h], rsi
0x1800ad485  mov     rdx, [rbx+3590h]; struct ITabRecoveryData *
0x1800ad48c  test    rdx, rdx
0x1800ad48f  jz      short loc_1800AD4B3
0x1800ad491  mov     rcx, rbx; this
0x1800ad494  call    ?_CleanUpRecoveryData@CTabWindow@@AEAAXPEAUITabRecoveryData@@@Z; CTabWindow::_CleanUpRecoveryData(ITabRecoveryData *)
0x1800ad499  mov     rcx, [rbx+3590h]
0x1800ad4a0  mov     rax, [rcx]
0x1800ad4a3  mov     rax, [rax+10h]
0x1800ad4a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad4ac  mov     [rbx+3590h], rsi
0x1800ad4b3  mov     eax, [rbx+36D8h]
0x1800ad4b9  test    eax, eax
0x1800ad4bb  jz      short loc_1800AD521
0x1800ad4bd  mov     rcx, cs:?g_pIEProcessSubscriptionManager@@3PEAUIESubscriptionManager@@EA; IESubscriptionManager * g_pIEProcessSubscriptionManager
0x1800ad4c4  lea     r8, [rsp+58h+var_28]
0x1800ad4c9  mov     [rsp+58h+var_24], eax
0x1800ad4cd  mov     r9d, 14h
0x1800ad4d3  mov     eax, [rbx+36DCh]
0x1800ad4d9  mov     [rsp+58h+var_20], eax
0x1800ad4dd  mov     eax, [rbx+36D4h]
0x1800ad4e3  mov     [rsp+58h+var_1C], eax
0x1800ad4e7  lea     edx, [r9-12h]
0x1800ad4eb  mov     eax, [rbx+0F8h]
0x1800ad4f1  mov     [rsp+58h+var_18], eax
0x1800ad4f5  mov     [rsp+58h+var_28], 2
0x1800ad4fd  mov     rax, [rcx]
0x1800ad500  mov     rax, [rax+30h]
0x1800ad504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad509  mov     ecx, [rbx+36D8h]
0x1800ad50f  call    cs:__imp_?IsoRemoveArtifact@@YAJK@Z; IsoRemoveArtifact(ulong)
0x1800ad516  nop     dword ptr [rax+rax+00h]
0x1800ad51b  mov     [rbx+36D8h], esi
0x1800ad521  mov     rcx, rdi
0x1800ad524  call    ??$IUnknown_SafeReleaseAndNullPtr@VCTabWindowManager@@@@YAXAEAPEAVCTabWindowManager@@@Z; IUnknown_SafeReleaseAndNullPtr<CTabWindowManager>(CTabWindowManager * &)
0x1800ad529  cmp     dword ptr [rbx+365Ch], 2
0x1800ad530  jz      short loc_1800AD53A
0x1800ad532  mov     rcx, rbx; this
0x1800ad535  call    ?_Uninitialize@CTabWindow@@AEAAXXZ; CTabWindow::_Uninitialize(void)
0x1800ad53a  mov     rcx, [rbx+100h]; hObject
0x1800ad541  test    rcx, rcx
0x1800ad544  jz      short loc_1800AD559
0x1800ad546  call    cs:__imp_CloseHandle
0x1800ad54d  nop     dword ptr [rax+rax+00h]
0x1800ad552  mov     [rbx+100h], rsi
0x1800ad559  lea     rcx, [rbx+36E8h]
0x1800ad560  call    ?Release@?$CComPtr@UIPrivacIEDatabase@@@ATL@@QEAAXXZ; ATL::CComPtr<IPrivacIEDatabase>::Release(void)
0x1800ad565  xor     edx, edx; unsigned int
0x1800ad567  mov     rcx, rbx; this
0x1800ad56a  call    ?_SetBrowserTabComponentHandle@CTabWindow@@AEAAXK@Z; CTabWindow::_SetBrowserTabComponentHandle(ulong)
0x1800ad56f  lea     rcx, [rbx+35F0h]; this
0x1800ad576  call    ?Disconnect@CTabDropTargetManager@@QEAAXXZ; CTabDropTargetManager::Disconnect(void)
0x1800ad57b  mov     rcx, [rbx+3678h]
0x1800ad582  test    rcx, rcx
0x1800ad585  jz      short loc_1800AD59A
0x1800ad587  call    cs:__imp_?IsoRemoveDependency@@YAJ_K@Z; IsoRemoveDependency(unsigned __int64)
0x1800ad58e  nop     dword ptr [rax+rax+00h]
0x1800ad593  mov     [rbx+3678h], rsi
0x1800ad59a  mov     rcx, [rbx+3680h]; pidl
0x1800ad5a1  test    rcx, rcx
0x1800ad5a4  jz      short loc_1800AD5CB
0x1800ad5a6  call    cs:__imp_ILFree
0x1800ad5ad  nop     dword ptr [rax+rax+00h]
0x1800ad5b2  xor     edx, edx; Val
0x1800ad5b4  mov     [rbx+3680h], rsi
0x1800ad5bb  lea     rcx, [rbx+3688h]; void *
0x1800ad5c2  lea     r8d, [rdx+48h]; Size
0x1800ad5c6  call    memset_0
0x1800ad5cb  mov     rcx, [rsp+58h+var_10]
0x1800ad5d0  xor     rcx, rsp; StackCookie
0x1800ad5d3  call    __security_check_cookie
0x1800ad5d8  mov     rbx, [rsp+58h+arg_8]
0x1800ad5dd  mov     rsi, [rsp+58h+arg_10]
0x1800ad5e2  add     rsp, 50h
0x1800ad5e6  pop     rdi
0x1800ad5e7  retn
```
