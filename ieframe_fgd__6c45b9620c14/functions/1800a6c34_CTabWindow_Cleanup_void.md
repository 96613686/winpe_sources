# CTabWindow::_Cleanup(void)

- ea: `0x1800a6c34`
- end: `0x1800a705e`
- name: `?_Cleanup@CTabWindow@@AEAAXXZ`
- size: `1066`
- prototype: `void __fastcall(CTabWindow *__hidden this)`
- caller_count: `3`
- callee_count: `23`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18024f7dc`
- `0x180255530`
- `0x18025b924`

## callees

- `0x18000c5c0`
- `0x180012140`
- `0x180095bac`
- `0x1800a6c34`
- `0x1800a7064`
- `0x1800a7098`
- `0x180250fe0`
- `0x180256f8c`
- `0x1802573ec`
- `0x180258da8`
- `0x18025b304`
- `0x18025bc8c`
- `0x180260ef8`
- `0x180262bcc`
- `0x180262fd4`
- `0x180275340`
- `0x1802756a4`
- `0x180289114`
- `0x18028991c`
- `0x1803f9174`
- `0x18054e286`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800a6d22`
- `KERNEL32!SetEvent` at `0x1800a6d22`
- `KERNEL32!CloseHandle` at `0x1800a6d2f`
- `KERNEL32!CloseHandle` at `0x1800a6dd2`
- `KERNEL32!CloseHandle` at `0x1800a6fce`
- `KERNEL32!CloseHandle` at `0x1800a6d2f`
- `KERNEL32!CloseHandle` at `0x1800a6dd2`
- `KERNEL32!CloseHandle` at `0x1800a6fce`
- `USER32!DestroyWindow` at `0x1800a6e74`
- `USER32!DestroyWindow` at `0x1800a6e8d`
- `USER32!DestroyWindow` at `0x1800a6e74`
- `USER32!DestroyWindow` at `0x1800a6e8d`
- `USER32!KillTimer` at `0x1800a6d66`
- `USER32!KillTimer` at `0x1800a6d66`
- `SHELL32!__imp_ILFree` at `0x1800a6d73`
- `SHELL32!__imp_ILFree` at `0x1800a6d87`
- `SHELL32!__imp_ILFree` at `0x1800a7022`
- `SHELL32!__imp_ILFree` at `0x1800a6d73`
- `SHELL32!__imp_ILFree` at `0x1800a6d87`
- `SHELL32!__imp_ILFree` at `0x1800a7022`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x1800a6f9d`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x1800a6f9d`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1800a6ca9`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1800a6cc2`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1800a6cdb`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1800a6cf4`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1800a7009`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1800a6ca9`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1800a6cc2`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1800a6cdb`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1800a6cf4`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1800a7009`
- `msIso!__imp_?IsoRemoveComponentDependenciesWithFlag@@YAJKW4_IsoComponentDependencyFlags@@@Z` at `0x1800a6d10`
- `msIso!__imp_?IsoRemoveComponentDependenciesWithFlag@@YAJKW4_IsoComponentDependencyFlags@@@Z` at `0x1800a6d10`

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
0x1800a6c34  mov     [rsp+arg_8], rbx
0x1800a6c39  mov     [rsp+arg_10], rsi
0x1800a6c3e  push    rdi
0x1800a6c3f  sub     rsp, 50h
0x1800a6c43  mov     rax, cs:__security_cookie
0x1800a6c4a  xor     rax, rsp
0x1800a6c4d  mov     [rsp+58h+var_10], rax
0x1800a6c52  mov     r8d, [rcx+1A4h]; int
0x1800a6c59  lea     rdi, [rcx+1E0h]
0x1800a6c60  xor     esi, esi
0x1800a6c62  mov     rbx, rcx
0x1800a6c65  cmp     r8d, 0FFFFFFFFh
0x1800a6c69  jz      short loc_1800A6C7E
0x1800a6c6b  mov     rcx, [rdi]; this
0x1800a6c6e  test    rcx, rcx
0x1800a6c71  jz      short loc_1800A6C7E
0x1800a6c73  mov     edx, [rbx+0F0h]; int
0x1800a6c79  call    ?VirtualTab_CommitToNewTab@CTabWindowManager@@QEAAJJJ@Z; CTabWindowManager::VirtualTab_CommitToNewTab(long,long)
0x1800a6c7e  mov     edx, [rbx+1A0h]; char *
0x1800a6c84  cmp     edx, 0FFFFFFFFh
0x1800a6c87  jz      short loc_1800A6C9D
0x1800a6c89  mov     rcx, [rdi]; this
0x1800a6c8c  test    rcx, rcx
0x1800a6c8f  jz      short loc_1800A6C9D
0x1800a6c91  mov     r8d, [rbx+0F0h]; int
0x1800a6c98  call    ?VirtualTab_RevertToOldTab@CTabWindowManager@@QEAAJJJ@Z; CTabWindowManager::VirtualTab_RevertToOldTab(long,long)
0x1800a6c9d  mov     rcx, [rbx+1B8h]
0x1800a6ca4  test    rcx, rcx
0x1800a6ca7  jz      short loc_1800A6CB6
0x1800a6ca9  call    cs:__imp_?IsoRemoveDependency@@YAJ_K@Z; IsoRemoveDependency(unsigned __int64)
0x1800a6caf  mov     [rbx+1B8h], rsi
0x1800a6cb6  mov     rcx, [rbx+1C0h]
0x1800a6cbd  test    rcx, rcx
0x1800a6cc0  jz      short loc_1800A6CCF
0x1800a6cc2  call    cs:__imp_?IsoRemoveDependency@@YAJ_K@Z; IsoRemoveDependency(unsigned __int64)
0x1800a6cc8  mov     [rbx+1C0h], rsi
0x1800a6ccf  mov     rcx, [rbx+3668h]
0x1800a6cd6  test    rcx, rcx
0x1800a6cd9  jz      short loc_1800A6CE8
0x1800a6cdb  call    cs:__imp_?IsoRemoveDependency@@YAJ_K@Z; IsoRemoveDependency(unsigned __int64)
0x1800a6ce1  mov     [rbx+3668h], rsi
0x1800a6ce8  mov     rcx, [rbx+3670h]
0x1800a6cef  test    rcx, rcx
0x1800a6cf2  jz      short loc_1800A6D01
0x1800a6cf4  call    cs:__imp_?IsoRemoveDependency@@YAJ_K@Z; IsoRemoveDependency(unsigned __int64)
0x1800a6cfa  mov     [rbx+3670h], rsi
0x1800a6d01  mov     ecx, [rbx+36D4h]
0x1800a6d07  test    ecx, ecx
0x1800a6d09  jz      short loc_1800A6D16
0x1800a6d0b  mov     edx, 10h
0x1800a6d10  call    cs:__imp_?IsoRemoveComponentDependenciesWithFlag@@YAJKW4_IsoComponentDependencyFlags@@@Z; IsoRemoveComponentDependenciesWithFlag(ulong,_IsoComponentDependencyFlags)
0x1800a6d16  mov     rcx, [rbx+1A8h]; hEvent
0x1800a6d1d  test    rcx, rcx
0x1800a6d20  jz      short loc_1800A6D3C
0x1800a6d22  call    cs:__imp_SetEvent
0x1800a6d28  mov     rcx, [rbx+1A8h]; hObject
0x1800a6d2f  call    cs:__imp_CloseHandle
0x1800a6d35  mov     [rbx+1A8h], rsi
0x1800a6d3c  xor     edx, edx; bool
0x1800a6d3e  mov     rcx, rbx; this
0x1800a6d41  call    ?SetFullViewportVideo@CTabWindow@@QEAAX_N@Z; CTabWindow::SetFullViewportVideo(bool)
0x1800a6d46  mov     rcx, rbx; this
0x1800a6d49  call    ?_DestroyDetachedBrowserTabUI@CTabWindow@@AEAAXXZ; CTabWindow::_DestroyDetachedBrowserTabUI(void)
0x1800a6d4e  mov     eax, [rbx+3554h]
0x1800a6d54  test    eax, eax
0x1800a6d56  jz      short loc_1800A6D6C
0x1800a6d58  mov     rcx, [rbx+160h]; hWnd
0x1800a6d5f  test    rcx, rcx
0x1800a6d62  jz      short loc_1800A6D6C
0x1800a6d64  mov     edx, eax; uIDEvent
0x1800a6d66  call    cs:__imp_KillTimer
0x1800a6d6c  mov     rcx, [rbx+1F0h]; pidl
0x1800a6d73  call    cs:__imp_ILFree
0x1800a6d79  mov     rcx, [rbx+34E8h]; pidl
0x1800a6d80  mov     [rbx+1F0h], rsi
0x1800a6d87  call    cs:__imp_ILFree
0x1800a6d8d  lea     rcx, [rbx+34F0h]
0x1800a6d94  mov     [rbx+34E8h], rsi
0x1800a6d9b  call    ?Release@?$CComPtr@UIPrivacIEDatabase@@@ATL@@QEAAXXZ; ATL::CComPtr<IPrivacIEDatabase>::Release(void)
0x1800a6da0  mov     rcx, [rbx+3710h]; lpMem
0x1800a6da7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a6dac  mov     rcx, [rbx+3718h]; lpMem
0x1800a6db3  mov     [rbx+3710h], rsi
0x1800a6dba  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a6dbf  mov     rcx, [rbx+3708h]; hObject
0x1800a6dc6  mov     [rbx+3718h], rsi
0x1800a6dcd  test    rcx, rcx
0x1800a6dd0  jz      short loc_1800A6DDF
0x1800a6dd2  call    cs:__imp_CloseHandle
0x1800a6dd8  mov     [rbx+3708h], rsi
0x1800a6ddf  cmp     [rbx+35D0h], rsi
0x1800a6de6  jz      short loc_1800A6DF5
0x1800a6de8  xor     r8d, r8d; bool
0x1800a6deb  xor     edx, edx; bool
0x1800a6ded  mov     rcx, rbx; this
0x1800a6df0  call    ?PrepareNewFrame@CTabWindow@@QEAAJ_N0@Z; CTabWindow::PrepareNewFrame(bool,bool)
0x1800a6df5  mov     rcx, rbx; this
0x1800a6df8  call    ?_OnBrowserPreparedToDehydrate@CTabWindow@@AEAAJXZ; CTabWindow::_OnBrowserPreparedToDehydrate(void)
0x1800a6dfd  mov     rcx, [rbx+3600h]
0x1800a6e04  test    rcx, rcx
0x1800a6e07  jz      short loc_1800A6E34
0x1800a6e09  mov     rax, [rcx]
0x1800a6e0c  mov     rax, [rax+28h]
0x1800a6e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6e15  mov     rcx, [rbx+3600h]
0x1800a6e1c  test    rcx, rcx
0x1800a6e1f  jz      short loc_1800A6E34
0x1800a6e21  mov     [rbx+3600h], rsi
0x1800a6e28  mov     rax, [rcx]
0x1800a6e2b  mov     rax, [rax+10h]
0x1800a6e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6e34  lea     rcx, [rbx+40h]; this
0x1800a6e38  xor     edx, edx; struct IServiceProvider *
0x1800a6e3a  call    ?ChainNavigationTarget@CNavigationTargetImpl@@IEAAJPEAUIServiceProvider@@PEAUINavigationBand@@H@Z; CNavigationTargetImpl::ChainNavigationTarget(IServiceProvider *,INavigationBand *,int)
0x1800a6e3f  lea     rcx, [rbx+1D8h]
0x1800a6e46  call    ?Release@?$CComPtr@UIPrivacIEDatabase@@@ATL@@QEAAXXZ; ATL::CComPtr<IPrivacIEDatabase>::Release(void)
0x1800a6e4b  lea     rcx, [rbx+1D0h]
0x1800a6e52  call    ?Release@?$CComPtr@UIPrivacIEDatabase@@@ATL@@QEAAXXZ; ATL::CComPtr<IPrivacIEDatabase>::Release(void)
0x1800a6e57  mov     rcx, rbx; this
0x1800a6e5a  call    ?_StopHungTabHeartbeat@CTabWindow@@AEAAXXZ; CTabWindow::_StopHungTabHeartbeat(void)
0x1800a6e5f  call    ?LCIEFrameTabWindow@@YA_NXZ; LCIEFrameTabWindow(void)
0x1800a6e64  test    al, al
0x1800a6e66  jz      short loc_1800A6E9A
0x1800a6e68  mov     rcx, [rbx+160h]; hWnd
0x1800a6e6f  test    rcx, rcx
0x1800a6e72  jz      short loc_1800A6E81
0x1800a6e74  call    cs:__imp_DestroyWindow
0x1800a6e7a  mov     [rbx+160h], rsi
0x1800a6e81  mov     rcx, [rbx+168h]; hWnd
0x1800a6e88  test    rcx, rcx
0x1800a6e8b  jz      short loc_1800A6E9A
0x1800a6e8d  call    cs:__imp_DestroyWindow
0x1800a6e93  mov     [rbx+168h], rsi
0x1800a6e9a  cmp     dword ptr [rbx+365Ch], 1
0x1800a6ea1  mov     [rbx+158h], rsi
0x1800a6ea8  mov     [rbx+170h], rsi
0x1800a6eaf  jz      loc_1800A6FC2
0x1800a6eb5  mov     rcx, [rbx+3608h]; this
0x1800a6ebc  test    rcx, rcx
0x1800a6ebf  jz      short loc_1800A6ED9
0x1800a6ec1  call    ?UnInitialize@CNotificationSqmListener@@QEAAXXZ; CNotificationSqmListener::UnInitialize(void)
0x1800a6ec6  mov     rcx, [rbx+3608h]; this
0x1800a6ecd  call    ?Release@CNotificationSqmListener@@UEAAKXZ; CNotificationSqmListener::Release(void)
0x1800a6ed2  mov     [rbx+3608h], rsi
0x1800a6ed9  mov     rcx, rbx; this
0x1800a6edc  call    ?ReceivedEndSession@CTabWindow@@QEBAHXZ; CTabWindow::ReceivedEndSession(void)
0x1800a6ee1  test    eax, eax
0x1800a6ee3  jnz     short loc_1800A6F41
0x1800a6ee5  mov     rdx, [rbx+3588h]; struct ITabRecoveryData *
0x1800a6eec  test    rdx, rdx
0x1800a6eef  jz      short loc_1800A6F13
0x1800a6ef1  mov     rcx, rbx; this
0x1800a6ef4  call    ?_CleanUpRecoveryData@CTabWindow@@AEAAXPEAUITabRecoveryData@@@Z; CTabWindow::_CleanUpRecoveryData(ITabRecoveryData *)
0x1800a6ef9  mov     rcx, [rbx+3588h]
0x1800a6f00  mov     rax, [rcx]
0x1800a6f03  mov     rax, [rax+10h]
0x1800a6f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6f0c  mov     [rbx+3588h], rsi
0x1800a6f13  mov     rdx, [rbx+3590h]; struct ITabRecoveryData *
0x1800a6f1a  test    rdx, rdx
0x1800a6f1d  jz      short loc_1800A6F41
0x1800a6f1f  mov     rcx, rbx; this
0x1800a6f22  call    ?_CleanUpRecoveryData@CTabWindow@@AEAAXPEAUITabRecoveryData@@@Z; CTabWindow::_CleanUpRecoveryData(ITabRecoveryData *)
0x1800a6f27  mov     rcx, [rbx+3590h]
0x1800a6f2e  mov     rax, [rcx]
0x1800a6f31  mov     rax, [rax+10h]
0x1800a6f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6f3a  mov     [rbx+3590h], rsi
0x1800a6f41  mov     eax, [rbx+36D8h]
0x1800a6f47  test    eax, eax
0x1800a6f49  jz      short loc_1800A6FA9
0x1800a6f4b  mov     rcx, cs:?g_pIEProcessSubscriptionManager@@3PEAUIESubscriptionManager@@EA; IESubscriptionManager * g_pIEProcessSubscriptionManager
0x1800a6f52  lea     r8, [rsp+58h+var_28]
0x1800a6f57  mov     [rsp+58h+var_24], eax
0x1800a6f5b  mov     r9d, 14h
0x1800a6f61  mov     eax, [rbx+36DCh]
0x1800a6f67  mov     [rsp+58h+var_20], eax
0x1800a6f6b  mov     eax, [rbx+36D4h]
0x1800a6f71  mov     [rsp+58h+var_1C], eax
0x1800a6f75  lea     edx, [r9-12h]
0x1800a6f79  mov     eax, [rbx+0F8h]
0x1800a6f7f  mov     [rsp+58h+var_18], eax
0x1800a6f83  mov     [rsp+58h+var_28], 2
0x1800a6f8b  mov     rax, [rcx]
0x1800a6f8e  mov     rax, [rax+30h]
0x1800a6f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6f97  mov     ecx, [rbx+36D8h]
0x1800a6f9d  call    cs:__imp_?IsoRemoveArtifact@@YAJK@Z; IsoRemoveArtifact(ulong)
0x1800a6fa3  mov     [rbx+36D8h], esi
0x1800a6fa9  mov     rcx, rdi
0x1800a6fac  call    ??$IUnknown_SafeReleaseAndNullPtr@VCTabWindowManager@@@@YAXAEAPEAVCTabWindowManager@@@Z; IUnknown_SafeReleaseAndNullPtr<CTabWindowManager>(CTabWindowManager * &)
0x1800a6fb1  cmp     dword ptr [rbx+365Ch], 2
0x1800a6fb8  jz      short loc_1800A6FC2
0x1800a6fba  mov     rcx, rbx; this
0x1800a6fbd  call    ?_Uninitialize@CTabWindow@@AEAAXXZ; CTabWindow::_Uninitialize(void)
0x1800a6fc2  mov     rcx, [rbx+100h]; hObject
0x1800a6fc9  test    rcx, rcx
0x1800a6fcc  jz      short loc_1800A6FDB
0x1800a6fce  call    cs:__imp_CloseHandle
0x1800a6fd4  mov     [rbx+100h], rsi
0x1800a6fdb  lea     rcx, [rbx+36E8h]
0x1800a6fe2  call    ?Release@?$CComPtr@UIPrivacIEDatabase@@@ATL@@QEAAXXZ; ATL::CComPtr<IPrivacIEDatabase>::Release(void)
0x1800a6fe7  xor     edx, edx; unsigned int
0x1800a6fe9  mov     rcx, rbx; this
0x1800a6fec  call    ?_SetBrowserTabComponentHandle@CTabWindow@@AEAAXK@Z; CTabWindow::_SetBrowserTabComponentHandle(ulong)
0x1800a6ff1  lea     rcx, [rbx+35F0h]; this
0x1800a6ff8  call    ?Disconnect@CTabDropTargetManager@@QEAAXXZ; CTabDropTargetManager::Disconnect(void)
0x1800a6ffd  mov     rcx, [rbx+3678h]
0x1800a7004  test    rcx, rcx
0x1800a7007  jz      short loc_1800A7016
0x1800a7009  call    cs:__imp_?IsoRemoveDependency@@YAJ_K@Z; IsoRemoveDependency(unsigned __int64)
0x1800a700f  mov     [rbx+3678h], rsi
0x1800a7016  mov     rcx, [rbx+3680h]; pidl
0x1800a701d  test    rcx, rcx
0x1800a7020  jz      short loc_1800A7041
0x1800a7022  call    cs:__imp_ILFree
0x1800a7028  xor     edx, edx; Val
0x1800a702a  mov     [rbx+3680h], rsi
0x1800a7031  lea     rcx, [rbx+3688h]; void *
0x1800a7038  lea     r8d, [rdx+48h]; Size
0x1800a703c  call    memset_0
0x1800a7041  mov     rcx, [rsp+58h+var_10]
0x1800a7046  xor     rcx, rsp; StackCookie
0x1800a7049  call    __security_check_cookie
0x1800a704e  mov     rbx, [rsp+58h+arg_8]
0x1800a7053  mov     rsi, [rsp+58h+arg_10]
0x1800a7058  add     rsp, 50h
0x1800a705c  pop     rdi
0x1800a705d  retn
```
