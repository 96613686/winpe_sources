# CWindow::focus(void)

- ea: `0x1803fd730`
- end: `0x1803fdb2e`
- name: `?focus@CWindow@@UEAAJXZ`
- size: `1022`
- prototype: `__int64 __fastcall(CWindow *__hidden this)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180149610`
- `0x18030172c`
- `0x1803e1034`
- `0x1803e706c`
- `0x1803e7198`
- `0x1803fd730`
- `0x1803fdb34`
- `0x1803fdb84`
- `0x180402a74`
- `0x180712534`
- `0x1807550ec`
- `0x1807c6f60`
- `0x1807e2190`
- `0x18084dd5c`
- `0x1808813e4`
- `0x180888900`
- `0x1808fc784`
- `0x181104010`

## import_xrefs

- `USER32!GetParent` at `0x1803fd87f`
- `USER32!GetParent` at `0x1803fd87f`
- `USER32!AllowSetForegroundWindow` at `0x1803fd93e`
- `USER32!AllowSetForegroundWindow` at `0x1803fd93e`
- `USER32!IsIconic` at `0x1803fd893`
- `USER32!IsIconic` at `0x1803fd893`
- `USER32!ShowWindow` at `0x1803fd8ab`
- `USER32!ShowWindow` at `0x1803fd8ab`
- `USER32!SetWindowPos` at `0x1803fd8d6`
- `USER32!SetWindowPos` at `0x1803fd8d6`
- `USER32!SetForegroundWindow` at `0x1803fd8e5`
- `USER32!SetForegroundWindow` at `0x1803fd8e5`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1803fd855`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1803fd855`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1803fd902`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1803fda30`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1803fd902`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1803fda30`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1803fd7c6`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1803fd7c6`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1803fd81f`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1803fd841`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1803fd81f`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1803fd841`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1803fd9c5`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1803fd9c5`

## pseudocode

```c
__int64 __fastcall CWindow::focus(CMarkup **this)
{
  CWindow *v1; // r14
  int v3; // ebx
  struct CDoc *v4; // rdi
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  struct CMarkup *v9; // rax
  CDoc *v10; // rcx
  unsigned int *v11; // rax
  HWND v12; // rbx
  HWND i; // rax
  DWORD v14; // ecx
  int v15; // ebx
  void (__fastcall *v16)(struct IEUserBroker *, __int128 *); // rbx
  struct IEUserBroker *v17; // rcx
  int v18; // ebx
  CElement *ElementTop; // rax
  COmWindowProxy *v20; // rax
  int v21; // edx
  int cy; // [rsp+28h] [rbp-30h]
  __int128 v24; // [rsp+40h] [rbp-18h] BYREF
  __int64 dwProcessId; // [rsp+90h] [rbp+38h] BYREF
  struct IEUserBroker *v26; // [rsp+98h] [rbp+40h] BYREF
  struct IEUserBroker *v27; // [rsp+A0h] [rbp+48h] BYREF
  HWND v28; // [rsp+A8h] [rbp+50h] BYREF

  v1 = (CWindow *)(this - 6);
  v3 = 0;
  v4 = CWindow::Doc((CWindow *)(this - 6));
  v5 = *((_QWORD *)v4 + 12);
  if ( !v5 || !*(_QWORD *)(v5 + 168) )
    goto LABEL_39;
  if ( CDoc::IsPrerendered(v4) )
  {
    v9 = CDoc::PrimaryMarkup(v4);
    CPreloadManagerLock::CPreloadManagerLock((CPreloadManagerLock *)&dwProcessId, v9);
    if ( dwProcessId )
    {
      v3 = CPreloadManager::SuspendDuringPrerender(dwProcessId, 6u);
      if ( v3 < 0 )
      {
        TSmartPointer<CPreloadManager>::~TSmartPointer<CPreloadManager>(&dwProcessId);
        goto LABEL_39;
      }
    }
    TSmartPointer<CPreloadManager>::~TSmartPointer<CPreloadManager>(&dwProcessId);
  }
  if ( (unsigned __int8)IEConfiguration_GetBool(268435481, v6, v7, v8) )
  {
    if ( CDoc::IsHiddenTab(v10) )
      goto LABEL_37;
    v28 = 0;
    if ( (int)GetBrowserHWNDForCurrentThread(&v28) < 0 )
      goto LABEL_37;
    v27 = 0;
    v26 = 0;
    if ( (int)CoCreateUserBroker(&v26) < 0 )
      goto LABEL_37;
    dwProcessId = 0;
    v18 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int64 *))(*(_QWORD *)v26 + 48LL))(
            v26,
            &CLSID_CShdocvwBroker,
            &IID_IUnknown,
            &dwProcessId);
    if ( v18 >= 0 )
    {
      v18 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IEUserBroker **))dwProcessId)(
              dwProcessId,
              &GUID_806d58df_ee78_4630_9475_f9b337a2dfcb,
              &v27);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)dwProcessId + 16LL))(dwProcessId);
    }
    (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v26 + 16LL))(v26);
    if ( v18 < 0 )
      goto LABEL_37;
    (*(void (__fastcall **)(struct IEUserBroker *, HWND))(*(_QWORD *)v27 + 48LL))(v27, v28);
    v17 = v27;
    goto LABEL_36;
  }
  if ( *((char *)v4 + 4868) >= 0
    || (v11 = (unsigned int *)CWindow::Doc(v1),
        (unsigned __int8)IsWebPlatformHostBehaviorSupported<6>(v11[1260], v11[1261], v11[1263], v11[1262])) )
  {
    if ( (unsigned int)AllowWindowManipulation()
      && (!IsDualEngineProcess() || !(unsigned __int8)_DualEnginePostMessageOrBrokerCallAsfwAndWait(0x1421u)) )
    {
      if ( !IsDualEngineProcess() && IsProtectedModeProcess() )
      {
        v12 = 0;
        for ( i = *(HWND *)(*((_QWORD *)v4 + 12) + 168LL); i; i = GetParent(i) )
          v12 = i;
        if ( IsIconic(v12) )
        {
          ShowWindow(v12, 9);
        }
        else
        {
          SetWindowPos(v12, 0, 0, 0, 0, 0, 3u);
          SetForegroundWindow(v12);
        }
        goto LABEL_37;
      }
      v26 = 0;
      v27 = 0;
      if ( (int)CoCreateUserBroker(&v27) < 0 )
        goto LABEL_37;
      LODWORD(dwProcessId) = 0;
      (*(void (__fastcall **)(struct IEUserBroker *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v27 + 24LL))(
        v27,
        0,
        0,
        &dwProcessId);
      v14 = -1;
      if ( (_DWORD)dwProcessId )
        v14 = dwProcessId;
      AllowSetForegroundWindow(v14);
      v28 = 0;
      v15 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, HWND *))(*(_QWORD *)v27 + 48LL))(
              v27,
              &CLSID_CShdocvwBroker,
              &IID_IUnknown,
              &v28);
      if ( v15 >= 0 )
      {
        v15 = (**(__int64 (__fastcall ***)(HWND, GUID *, struct IEUserBroker **))v28)(
                v28,
                &GUID_806d58df_ee78_4630_9475_f9b337a2dfcb,
                &v26);
        (*(void (__fastcall **)(HWND))(*(_QWORD *)v28 + 16LL))(v28);
      }
      (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v27 + 16LL))(v27);
      if ( v15 < 0 )
        goto LABEL_37;
      v16 = *(void (__fastcall **)(struct IEUserBroker *, __int128 *))(*(_QWORD *)v26 + 56LL);
      v24 = *(_OWORD *)GlobalThreadState();
      v16(v26, &v24);
      (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v26 + 32LL))(v26);
      v17 = v26;
LABEL_36:
      (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
LABEL_37:
  ElementTop = CMarkup::GetElementTop(this[7]);
  v3 = CElement::BecomeCurrentAndActive(ElementTop, 0, 0, 0, 1, cy, 0);
  if ( !v3 )
  {
    v20 = CMarkup::Window(this[7]);
    COmWindowProxy::Post_onfocus(v20);
  }
LABEL_39:
  v21 = 0;
  if ( v3 != 1 )
    v21 = v3;
  return CBase::SetErrorInfo(v1, v21);
}

```

## disassembly

```asm
0x1803fd730  push    rbp
0x1803fd732  push    rbx
0x1803fd733  push    rsi
0x1803fd734  push    rdi
0x1803fd735  push    r14
0x1803fd737  push    r15
0x1803fd739  mov     rbp, rsp
0x1803fd73c  sub     rsp, 58h
0x1803fd740  lea     r14, [rcx-30h]
0x1803fd744  mov     rsi, rcx
0x1803fd747  xor     r15d, r15d
0x1803fd74a  mov     rcx, r14; this
0x1803fd74d  mov     ebx, r15d
0x1803fd750  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x1803fd755  mov     rdi, rax
0x1803fd758  mov     rax, [rax+60h]
0x1803fd75c  test    rax, rax
0x1803fd75f  jz      loc_1803FDB11
0x1803fd765  cmp     [rax+0A8h], r15
0x1803fd76c  jz      loc_1803FDB11
0x1803fd772  mov     rcx, rdi; this
0x1803fd775  call    ?IsPrerendered@CDoc@@QEBA_NXZ; CDoc::IsPrerendered(void)
0x1803fd77a  test    al, al
0x1803fd77c  jz      short loc_1803FD7C1
0x1803fd77e  mov     rcx, rdi; this
0x1803fd781  call    ?PrimaryMarkup@CDoc@@QEBAPEAVCMarkup@@XZ; CDoc::PrimaryMarkup(void)
0x1803fd786  mov     rdx, rax; struct CMarkup *
0x1803fd789  lea     rcx, [rbp+dwProcessId]; this
0x1803fd78d  call    ??0CPreloadManagerLock@@QEAA@PEAVCMarkup@@@Z; CPreloadManagerLock::CPreloadManagerLock(CMarkup *)
0x1803fd792  mov     rcx, [rbp+dwProcessId]
0x1803fd796  test    rcx, rcx
0x1803fd799  jz      short loc_1803FD7B8
0x1803fd79b  lea     edx, [r15+6]
0x1803fd79f  call    ?SuspendDuringPrerender@CPreloadManager@@QEAAJW4PrerenderDeferredLoadingType@@@Z; CPreloadManager::SuspendDuringPrerender(PrerenderDeferredLoadingType)
0x1803fd7a4  mov     ebx, eax
0x1803fd7a6  test    eax, eax
0x1803fd7a8  jns     short loc_1803FD7B8
0x1803fd7aa  lea     rcx, [rbp+dwProcessId]
0x1803fd7ae  call    ??1?$TSmartPointer@VCPreloadManager@@@@QEAA@XZ; TSmartPointer<CPreloadManager>::~TSmartPointer<CPreloadManager>(void)
0x1803fd7b3  jmp     loc_1803FDB11
0x1803fd7b8  lea     rcx, [rbp+dwProcessId]
0x1803fd7bc  call    ??1?$TSmartPointer@VCPreloadManager@@@@QEAA@XZ; TSmartPointer<CPreloadManager>::~TSmartPointer<CPreloadManager>(void)
0x1803fd7c1  mov     ecx, 10000019h
0x1803fd7c6  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1803fd7cd  nop     dword ptr [rax+rax+00h]
0x1803fd7d2  test    al, al
0x1803fd7d4  jnz     loc_1803FDA02
0x1803fd7da  test    byte ptr [rdi+1304h], 80h
0x1803fd7e1  jz      short loc_1803FD812
0x1803fd7e3  mov     rcx, r14; this
0x1803fd7e6  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x1803fd7eb  mov     r9d, [rax+13B8h]
0x1803fd7f2  mov     r8d, [rax+13BCh]
0x1803fd7f9  mov     edx, [rax+13B4h]
0x1803fd7ff  mov     ecx, [rax+13B0h]
0x1803fd805  call    ??$IsWebPlatformHostBehaviorSupported@$05@@YA_NW4WebPlatformHostType@@KKK@Z; IsWebPlatformHostBehaviorSupported<6>(WebPlatformHostType,ulong,ulong,ulong)
0x1803fd80a  test    al, al
0x1803fd80c  jz      loc_1803FDAD4
0x1803fd812  call    ?AllowWindowManipulation@@YAHXZ; AllowWindowManipulation(void)
0x1803fd817  test    eax, eax
0x1803fd819  jz      loc_1803FDAD4
0x1803fd81f  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1803fd826  nop     dword ptr [rax+rax+00h]
0x1803fd82b  test    al, al
0x1803fd82d  jz      short loc_1803FD841
0x1803fd82f  mov     ecx, 1421h; unsigned int
0x1803fd834  call    ?_DualEnginePostMessageOrBrokerCallAsfwAndWait@@YA_NK@Z; _DualEnginePostMessageOrBrokerCallAsfwAndWait(ulong)
0x1803fd839  test    al, al
0x1803fd83b  jnz     loc_1803FDAD4
0x1803fd841  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1803fd848  nop     dword ptr [rax+rax+00h]
0x1803fd84d  test    al, al
0x1803fd84f  jnz     loc_1803FD8F6
0x1803fd855  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x1803fd85c  nop     dword ptr [rax+rax+00h]
0x1803fd861  test    eax, eax
0x1803fd863  jz      loc_1803FD8F6
0x1803fd869  mov     rax, [rdi+60h]
0x1803fd86d  mov     rbx, r15
0x1803fd870  mov     rax, [rax+0A8h]
0x1803fd877  jmp     short loc_1803FD88B
0x1803fd879  mov     rcx, rax; hWnd
0x1803fd87c  mov     rbx, rax
0x1803fd87f  call    cs:__imp_GetParent
0x1803fd886  nop     dword ptr [rax+rax+00h]
0x1803fd88b  test    rax, rax
0x1803fd88e  jnz     short loc_1803FD879
0x1803fd890  mov     rcx, rbx; hWnd
0x1803fd893  call    cs:__imp_IsIconic
0x1803fd89a  nop     dword ptr [rax+rax+00h]
0x1803fd89f  mov     rcx, rbx; hWnd
0x1803fd8a2  test    eax, eax
0x1803fd8a4  jz      short loc_1803FD8BC
0x1803fd8a6  mov     edx, 9; nCmdShow
0x1803fd8ab  call    cs:__imp_ShowWindow
0x1803fd8b2  nop     dword ptr [rax+rax+00h]
0x1803fd8b7  jmp     loc_1803FDAD4
0x1803fd8bc  mov     [rsp+58h+uFlags], 3; uFlags
0x1803fd8c4  xor     r9d, r9d; Y
0x1803fd8c7  mov     [rsp+58h+cy], r15d; cy
0x1803fd8cc  xor     r8d, r8d; X
0x1803fd8cf  xor     edx, edx; hWndInsertAfter
0x1803fd8d1  mov     [rsp+58h+var_38], r15d; cx
0x1803fd8d6  call    cs:__imp_SetWindowPos
0x1803fd8dd  nop     dword ptr [rax+rax+00h]
0x1803fd8e2  mov     rcx, rbx; hWnd
0x1803fd8e5  call    cs:__imp_SetForegroundWindow
0x1803fd8ec  nop     dword ptr [rax+rax+00h]
0x1803fd8f1  jmp     loc_1803FDAD4
0x1803fd8f6  lea     rcx, [rbp+arg_10]
0x1803fd8fa  mov     [rbp+arg_8], r15
0x1803fd8fe  mov     [rbp+arg_10], r15
0x1803fd902  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1803fd909  nop     dword ptr [rax+rax+00h]
0x1803fd90e  test    eax, eax
0x1803fd910  js      loc_1803FDAD4
0x1803fd916  mov     rcx, [rbp+arg_10]
0x1803fd91a  lea     r9, [rbp+dwProcessId]
0x1803fd91e  mov     dword ptr [rbp+dwProcessId], r15d
0x1803fd922  xor     r8d, r8d
0x1803fd925  xor     edx, edx
0x1803fd927  mov     rax, [rcx]
0x1803fd92a  mov     rax, [rax+18h]
0x1803fd92e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803fd933  mov     eax, dword ptr [rbp+dwProcessId]
0x1803fd936  or      ecx, 0FFFFFFFFh
0x1803fd939  test    eax, eax
0x1803fd93b  cmovnz  ecx, eax; dwProcessId
0x1803fd93e  call    cs:__imp_AllowSetForegroundWindow
0x1803fd945  nop     dword ptr [rax+rax+00h]
0x1803fd94a  mov     rcx, [rbp+arg_10]
0x1803fd94e  lea     r9, [rbp+arg_18]
0x1803fd952  mov     [rbp+arg_18], r15
0x1803fd956  lea     r8, IID_IUnknown
0x1803fd95d  lea     rdx, CLSID_CShdocvwBroker
0x1803fd964  mov     rax, [rcx]
0x1803fd967  mov     rax, [rax+30h]
0x1803fd96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803fd970  mov     ebx, eax
0x1803fd972  test    eax, eax
0x1803fd974  js      short loc_1803FD9A2
0x1803fd976  mov     rcx, [rbp+arg_18]
0x1803fd97a  lea     r8, [rbp+arg_8]
0x1803fd97e  lea     rdx, _GUID_806d58df_ee78_4630_9475_f9b337a2dfcb
0x1803fd985  mov     rax, [rcx]
0x1803fd988  mov     rax, [rax]
0x1803fd98b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803fd990  mov     rcx, [rbp+arg_18]
0x1803fd994  mov     ebx, eax
0x1803fd996  mov     rax, [rcx]
0x1803fd999  mov     rax, [rax+10h]
0x1803fd99d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803fd9a2  mov     rcx, [rbp+arg_10]
0x1803fd9a6  mov     rax, [rcx]
0x1803fd9a9  mov     rax, [rax+10h]
0x1803fd9ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803fd9b2  test    ebx, ebx
0x1803fd9b4  js      loc_1803FDAD4
0x1803fd9ba  mov     rax, [rbp+arg_8]
0x1803fd9be  mov     rcx, [rax]
0x1803fd9c1  mov     rbx, [rcx+38h]
0x1803fd9c5  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1803fd9cc  nop     dword ptr [rax+rax+00h]
0x1803fd9d1  mov     rcx, [rbp+arg_8]
0x1803fd9d5  lea     rdx, [rbp+var_18]
0x1803fd9d9  movups  xmm0, xmmword ptr [rax]
0x1803fd9dc  mov     rax, rbx
0x1803fd9df  movdqu  [rbp+var_18], xmm0
0x1803fd9e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803fd9e9  mov     rcx, [rbp+arg_8]
0x1803fd9ed  mov     rax, [rcx]
0x1803fd9f0  mov     rax, [rax+20h]
0x1803fd9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803fd9f9  mov     rcx, [rbp+arg_8]
0x1803fd9fd  jmp     loc_1803FDAC8
0x1803fda02  call    ?IsHiddenTab@CDoc@@QEBA_NXZ; CDoc::IsHiddenTab(void)
0x1803fda07  test    al, al
0x1803fda09  jnz     loc_1803FDAD4
0x1803fda0f  lea     rcx, [rbp+arg_18]; HWND *
0x1803fda13  mov     [rbp+arg_18], r15
0x1803fda17  call    ?GetBrowserHWNDForCurrentThread@@YAJPEAPEAUHWND__@@@Z; GetBrowserHWNDForCurrentThread(HWND__ * *)
0x1803fda1c  test    eax, eax
0x1803fda1e  js      loc_1803FDAD4
0x1803fda24  lea     rcx, [rbp+arg_8]
0x1803fda28  mov     [rbp+arg_10], r15
0x1803fda2c  mov     [rbp+arg_8], r15
0x1803fda30  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1803fda37  nop     dword ptr [rax+rax+00h]
0x1803fda3c  test    eax, eax
0x1803fda3e  js      loc_1803FDAD4
0x1803fda44  mov     rcx, [rbp+arg_8]
0x1803fda48  lea     r9, [rbp+dwProcessId]
0x1803fda4c  mov     [rbp+dwProcessId], r15
0x1803fda50  lea     r8, IID_IUnknown
0x1803fda57  lea     rdx, CLSID_CShdocvwBroker
0x1803fda5e  mov     rax, [rcx]
0x1803fda61  mov     rax, [rax+30h]
0x1803fda65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803fda6a  mov     ebx, eax
0x1803fda6c  test    eax, eax
0x1803fda6e  js      short loc_1803FDA9C
0x1803fda70  mov     rcx, [rbp+dwProcessId]
0x1803fda74  lea     r8, [rbp+arg_10]
0x1803fda78  lea     rdx, _GUID_806d58df_ee78_4630_9475_f9b337a2dfcb
0x1803fda7f  mov     rax, [rcx]
0x1803fda82  mov     rax, [rax]
0x1803fda85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803fda8a  mov     rcx, [rbp+dwProcessId]
0x1803fda8e  mov     ebx, eax
0x1803fda90  mov     rax, [rcx]
0x1803fda93  mov     rax, [rax+10h]
0x1803fda97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803fda9c  mov     rcx, [rbp+arg_8]
0x1803fdaa0  mov     rax, [rcx]
0x1803fdaa3  mov     rax, [rax+10h]
0x1803fdaa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803fdaac  test    ebx, ebx
0x1803fdaae  js      short loc_1803FDAD4
0x1803fdab0  mov     rcx, [rbp+arg_10]
0x1803fdab4  mov     rdx, [rbp+arg_18]
0x1803fdab8  mov     rax, [rcx]
0x1803fdabb  mov     rax, [rax+30h]
0x1803fdabf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803fdac4  mov     rcx, [rbp+arg_10]
0x1803fdac8  mov     rax, [rcx]
0x1803fdacb  mov     rax, [rax+10h]
0x1803fdacf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803fdad4  mov     rcx, [rsi+38h]; this
0x1803fdad8  call    ?GetElementTop@CMarkup@@QEAAPEAVCElement@@XZ; CMarkup::GetElementTop(void)
0x1803fdadd  xor     r9d, r9d; struct CMessage *
0x1803fdae0  mov     [rsp+58h+uFlags], r15d; int
0x1803fdae5  xor     r8d, r8d; int *
0x1803fdae8  mov     [rsp+58h+var_38], 1; int
0x1803fdaf0  xor     edx, edx; int
0x1803fdaf2  mov     rcx, rax; this
0x1803fdaf5  call    ?BecomeCurrentAndActive@CElement@@QEAAJJPEAHPEAVCMessage@@HJH@Z; CElement::BecomeCurrentAndActive(long,int *,CMessage *,int,long,int)
0x1803fdafa  mov     ebx, eax
0x1803fdafc  test    eax, eax
0x1803fdafe  jnz     short loc_1803FDB11
0x1803fdb00  mov     rcx, [rsi+38h]; this
0x1803fdb04  call    ?Window@CMarkup@@QEBAPEAVCOmWindowProxy@@XZ; CMarkup::Window(void)
0x1803fdb09  mov     rcx, rax; this
0x1803fdb0c  call    ?Post_onfocus@COmWindowProxy@@QEAAXXZ; COmWindowProxy::Post_onfocus(void)
0x1803fdb11  cmp     ebx, 1
0x1803fdb14  mov     edx, r15d
0x1803fdb17  mov     rcx, r14; this
0x1803fdb1a  cmovnz  edx, ebx; int
0x1803fdb1d  add     rsp, 58h
0x1803fdb21  pop     r15
0x1803fdb23  pop     r14
0x1803fdb25  pop     rdi
0x1803fdb26  pop     rsi
0x1803fdb27  pop     rbx
0x1803fdb28  pop     rbp
0x1803fdb29  jmp     ?SetErrorInfo@CBase@@QEBAJJ@Z; CBase::SetErrorInfo(long)
```
