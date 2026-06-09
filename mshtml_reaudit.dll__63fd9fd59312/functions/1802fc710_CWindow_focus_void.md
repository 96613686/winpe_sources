# CWindow::focus(void)

- ea: `0x1802fc710`
- end: `0x1802fcab8`
- name: `?focus@CWindow@@UEAAJXZ`
- size: `936`
- prototype: `__int64 __fastcall(CWindow *__hidden this)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x1800f5454`
- `0x180223a8c`
- `0x1802fc710`
- `0x1802fcac0`
- `0x1802fcb10`
- `0x1802fd8ec`
- `0x180300074`
- `0x180370004`
- `0x180373368`
- `0x1806f45d8`
- `0x18074e0f8`
- `0x1807bb7fc`
- `0x1807d6afc`
- `0x18084ac60`
- `0x18087a478`
- `0x1808814f0`
- `0x1808f022c`
- `0x1810d1010`

## import_xrefs

- `USER32!GetParent` at `0x1802fc83f`
- `USER32!GetParent` at `0x1802fc83f`
- `USER32!AllowSetForegroundWindow` at `0x1802fc8da`
- `USER32!AllowSetForegroundWindow` at `0x1802fc8da`
- `USER32!IsIconic` at `0x1802fc84d`
- `USER32!IsIconic` at `0x1802fc84d`
- `USER32!ShowWindow` at `0x1802fc85f`
- `USER32!ShowWindow` at `0x1802fc85f`
- `USER32!SetWindowPos` at `0x1802fc884`
- `USER32!SetWindowPos` at `0x1802fc884`
- `USER32!SetForegroundWindow` at `0x1802fc88d`
- `USER32!SetForegroundWindow` at `0x1802fc88d`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1802fc81f`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1802fc81f`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1802fc8a4`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1802fc9c0`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1802fc8a4`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1802fc9c0`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1802fc7a6`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1802fc7a6`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1802fc7f9`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1802fc815`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1802fc7f9`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1802fc815`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1802fc95b`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1802fc95b`

## pseudocode

```c
__int64 __fastcall CWindow::focus(CMarkup **this)
{
  CWindow *v1; // r14
  int v3; // ebx
  struct CDoc *v4; // rdi
  __int64 v5; // rax
  struct CMarkup *v6; // rax
  CDoc *v7; // rcx
  unsigned int *v8; // rax
  HWND v9; // rbx
  HWND i; // rax
  DWORD v11; // ecx
  int v12; // ebx
  void (__fastcall *v13)(struct IEUserBroker *, __int128 *); // rbx
  struct IEUserBroker *v14; // rcx
  int v15; // ebx
  CElement *ElementTop; // rax
  COmWindowProxy *v17; // rax
  int v18; // edx
  int cy; // [rsp+28h] [rbp-30h]
  __int128 v21; // [rsp+40h] [rbp-18h] BYREF
  __int64 dwProcessId; // [rsp+90h] [rbp+38h] BYREF
  struct IEUserBroker *v23; // [rsp+98h] [rbp+40h] BYREF
  struct IEUserBroker *v24; // [rsp+A0h] [rbp+48h] BYREF
  HWND v25; // [rsp+A8h] [rbp+50h] BYREF

  v1 = (CWindow *)(this - 6);
  v3 = 0;
  v4 = CWindow::Doc((CWindow *)(this - 6));
  v5 = *((_QWORD *)v4 + 12);
  if ( !v5 || !*(_QWORD *)(v5 + 168) )
    goto LABEL_39;
  if ( CDoc::IsPrerendered(v4) )
  {
    v6 = CDoc::PrimaryMarkup(v4);
    CPreloadManagerLock::CPreloadManagerLock((CPreloadManagerLock *)&dwProcessId, v6);
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
  if ( (unsigned __int8)IEConfiguration_GetBool(268435481) )
  {
    if ( CDoc::IsHiddenTab(v7) )
      goto LABEL_37;
    v25 = 0;
    if ( (int)GetBrowserHWNDForCurrentThread(&v25) < 0 )
      goto LABEL_37;
    v24 = 0;
    v23 = 0;
    if ( (int)CoCreateUserBroker(&v23) < 0 )
      goto LABEL_37;
    dwProcessId = 0;
    v15 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int64 *))(*(_QWORD *)v23 + 48LL))(
            v23,
            &CLSID_CShdocvwBroker,
            &IID_IUnknown,
            &dwProcessId);
    if ( v15 >= 0 )
    {
      v15 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IEUserBroker **))dwProcessId)(
              dwProcessId,
              &GUID_806d58df_ee78_4630_9475_f9b337a2dfcb,
              &v24);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)dwProcessId + 16LL))(dwProcessId);
    }
    (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v23 + 16LL))(v23);
    if ( v15 < 0 )
      goto LABEL_37;
    (*(void (__fastcall **)(struct IEUserBroker *, HWND))(*(_QWORD *)v24 + 48LL))(v24, v25);
    v14 = v24;
    goto LABEL_36;
  }
  if ( *((char *)v4 + 4868) >= 0
    || (v8 = (unsigned int *)CWindow::Doc(v1),
        (unsigned __int8)IsWebPlatformHostBehaviorSupported<6>(v8[1260], v8[1261], v8[1263], v8[1262])) )
  {
    if ( (unsigned int)AllowWindowManipulation()
      && (!IsDualEngineProcess() || !(unsigned __int8)_DualEnginePostMessageOrBrokerCallAsfwAndWait(0x1421u)) )
    {
      if ( !IsDualEngineProcess() && IsProtectedModeProcess() )
      {
        v9 = 0;
        for ( i = *(HWND *)(*((_QWORD *)v4 + 12) + 168LL); i; i = GetParent(i) )
          v9 = i;
        if ( IsIconic(v9) )
        {
          ShowWindow(v9, 9);
        }
        else
        {
          SetWindowPos(v9, 0, 0, 0, 0, 0, 3u);
          SetForegroundWindow(v9);
        }
        goto LABEL_37;
      }
      v23 = 0;
      v24 = 0;
      if ( (int)CoCreateUserBroker(&v24) < 0 )
        goto LABEL_37;
      LODWORD(dwProcessId) = 0;
      (*(void (__fastcall **)(struct IEUserBroker *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v24 + 24LL))(
        v24,
        0,
        0,
        &dwProcessId);
      v11 = -1;
      if ( (_DWORD)dwProcessId )
        v11 = dwProcessId;
      AllowSetForegroundWindow(v11);
      v25 = 0;
      v12 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, HWND *))(*(_QWORD *)v24 + 48LL))(
              v24,
              &CLSID_CShdocvwBroker,
              &IID_IUnknown,
              &v25);
      if ( v12 >= 0 )
      {
        v12 = (**(__int64 (__fastcall ***)(HWND, GUID *, struct IEUserBroker **))v25)(
                v25,
                &GUID_806d58df_ee78_4630_9475_f9b337a2dfcb,
                &v23);
        (*(void (__fastcall **)(HWND))(*(_QWORD *)v25 + 16LL))(v25);
      }
      (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v24 + 16LL))(v24);
      if ( v12 < 0 )
        goto LABEL_37;
      v13 = *(void (__fastcall **)(struct IEUserBroker *, __int128 *))(*(_QWORD *)v23 + 56LL);
      v21 = *(_OWORD *)GlobalThreadState();
      v13(v23, &v21);
      (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v23 + 32LL))(v23);
      v14 = v23;
LABEL_36:
      (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
LABEL_37:
  ElementTop = CMarkup::GetElementTop(this[7]);
  v3 = CElement::BecomeCurrentAndActive(ElementTop, 0, 0, 0, 1, cy, 0);
  if ( !v3 )
  {
    v17 = CMarkup::Window(this[7]);
    COmWindowProxy::Post_onfocus(v17);
  }
LABEL_39:
  v18 = 0;
  if ( v3 != 1 )
    v18 = v3;
  return CBase::SetErrorInfo(v1, v18);
}

```

## disassembly

```asm
0x1802fc710  push    rbp
0x1802fc712  push    rbx
0x1802fc713  push    rsi
0x1802fc714  push    rdi
0x1802fc715  push    r14
0x1802fc717  push    r15
0x1802fc719  mov     rbp, rsp
0x1802fc71c  sub     rsp, 58h
0x1802fc720  lea     r14, [rcx-30h]
0x1802fc724  mov     rsi, rcx
0x1802fc727  xor     r15d, r15d
0x1802fc72a  mov     rcx, r14; this
0x1802fc72d  mov     ebx, r15d
0x1802fc730  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x1802fc735  mov     rdi, rax
0x1802fc738  mov     rax, [rax+60h]
0x1802fc73c  test    rax, rax
0x1802fc73f  jz      loc_1802FCA9B
0x1802fc745  cmp     [rax+0A8h], r15
0x1802fc74c  jz      loc_1802FCA9B
0x1802fc752  mov     rcx, rdi; this
0x1802fc755  call    ?IsPrerendered@CDoc@@QEBA_NXZ; CDoc::IsPrerendered(void)
0x1802fc75a  test    al, al
0x1802fc75c  jz      short loc_1802FC7A1
0x1802fc75e  mov     rcx, rdi; this
0x1802fc761  call    ?PrimaryMarkup@CDoc@@QEBAPEAVCMarkup@@XZ; CDoc::PrimaryMarkup(void)
0x1802fc766  mov     rdx, rax; struct CMarkup *
0x1802fc769  lea     rcx, [rbp+dwProcessId]; this
0x1802fc76d  call    ??0CPreloadManagerLock@@QEAA@PEAVCMarkup@@@Z; CPreloadManagerLock::CPreloadManagerLock(CMarkup *)
0x1802fc772  mov     rcx, [rbp+dwProcessId]
0x1802fc776  test    rcx, rcx
0x1802fc779  jz      short loc_1802FC798
0x1802fc77b  lea     edx, [r15+6]
0x1802fc77f  call    ?SuspendDuringPrerender@CPreloadManager@@QEAAJW4PrerenderDeferredLoadingType@@@Z; CPreloadManager::SuspendDuringPrerender(PrerenderDeferredLoadingType)
0x1802fc784  mov     ebx, eax
0x1802fc786  test    eax, eax
0x1802fc788  jns     short loc_1802FC798
0x1802fc78a  lea     rcx, [rbp+dwProcessId]
0x1802fc78e  call    ??1?$TSmartPointer@VCPreloadManager@@@@QEAA@XZ; TSmartPointer<CPreloadManager>::~TSmartPointer<CPreloadManager>(void)
0x1802fc793  jmp     loc_1802FCA9B
0x1802fc798  lea     rcx, [rbp+dwProcessId]
0x1802fc79c  call    ??1?$TSmartPointer@VCPreloadManager@@@@QEAA@XZ; TSmartPointer<CPreloadManager>::~TSmartPointer<CPreloadManager>(void)
0x1802fc7a1  mov     ecx, 10000019h
0x1802fc7a6  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1802fc7ac  test    al, al
0x1802fc7ae  jnz     loc_1802FC992
0x1802fc7b4  test    byte ptr [rdi+1304h], 80h
0x1802fc7bb  jz      short loc_1802FC7EC
0x1802fc7bd  mov     rcx, r14; this
0x1802fc7c0  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x1802fc7c5  mov     r9d, [rax+13B8h]
0x1802fc7cc  mov     r8d, [rax+13BCh]
0x1802fc7d3  mov     edx, [rax+13B4h]
0x1802fc7d9  mov     ecx, [rax+13B0h]
0x1802fc7df  call    ??$IsWebPlatformHostBehaviorSupported@$05@@YA_NW4WebPlatformHostType@@KKK@Z; IsWebPlatformHostBehaviorSupported<6>(WebPlatformHostType,ulong,ulong,ulong)
0x1802fc7e4  test    al, al
0x1802fc7e6  jz      loc_1802FCA5E
0x1802fc7ec  call    ?AllowWindowManipulation@@YAHXZ; AllowWindowManipulation(void)
0x1802fc7f1  test    eax, eax
0x1802fc7f3  jz      loc_1802FCA5E
0x1802fc7f9  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1802fc7ff  test    al, al
0x1802fc801  jz      short loc_1802FC815
0x1802fc803  mov     ecx, 1421h; unsigned int
0x1802fc808  call    ?_DualEnginePostMessageOrBrokerCallAsfwAndWait@@YA_NK@Z; _DualEnginePostMessageOrBrokerCallAsfwAndWait(ulong)
0x1802fc80d  test    al, al
0x1802fc80f  jnz     loc_1802FCA5E
0x1802fc815  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1802fc81b  test    al, al
0x1802fc81d  jnz     short loc_1802FC898
0x1802fc81f  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x1802fc825  test    eax, eax
0x1802fc827  jz      short loc_1802FC898
0x1802fc829  mov     rax, [rdi+60h]
0x1802fc82d  mov     rbx, r15
0x1802fc830  mov     rax, [rax+0A8h]
0x1802fc837  jmp     short loc_1802FC845
0x1802fc839  mov     rcx, rax; hWnd
0x1802fc83c  mov     rbx, rax
0x1802fc83f  call    cs:__imp_GetParent
0x1802fc845  test    rax, rax
0x1802fc848  jnz     short loc_1802FC839
0x1802fc84a  mov     rcx, rbx; hWnd
0x1802fc84d  call    cs:__imp_IsIconic
0x1802fc853  mov     rcx, rbx; hWnd
0x1802fc856  test    eax, eax
0x1802fc858  jz      short loc_1802FC86A
0x1802fc85a  mov     edx, 9; nCmdShow
0x1802fc85f  call    cs:__imp_ShowWindow
0x1802fc865  jmp     loc_1802FCA5E
0x1802fc86a  mov     [rsp+58h+uFlags], 3; uFlags
0x1802fc872  xor     r9d, r9d; Y
0x1802fc875  mov     [rsp+58h+cy], r15d; cy
0x1802fc87a  xor     r8d, r8d; X
0x1802fc87d  xor     edx, edx; hWndInsertAfter
0x1802fc87f  mov     [rsp+58h+var_38], r15d; cx
0x1802fc884  call    cs:__imp_SetWindowPos
0x1802fc88a  mov     rcx, rbx; hWnd
0x1802fc88d  call    cs:__imp_SetForegroundWindow
0x1802fc893  jmp     loc_1802FCA5E
0x1802fc898  lea     rcx, [rbp+arg_10]
0x1802fc89c  mov     [rbp+arg_8], r15
0x1802fc8a0  mov     [rbp+arg_10], r15
0x1802fc8a4  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1802fc8aa  test    eax, eax
0x1802fc8ac  js      loc_1802FCA5E
0x1802fc8b2  mov     rcx, [rbp+arg_10]
0x1802fc8b6  lea     r9, [rbp+dwProcessId]
0x1802fc8ba  mov     dword ptr [rbp+dwProcessId], r15d
0x1802fc8be  xor     r8d, r8d
0x1802fc8c1  xor     edx, edx
0x1802fc8c3  mov     rax, [rcx]
0x1802fc8c6  mov     rax, [rax+18h]
0x1802fc8ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fc8cf  mov     eax, dword ptr [rbp+dwProcessId]
0x1802fc8d2  or      ecx, 0FFFFFFFFh
0x1802fc8d5  test    eax, eax
0x1802fc8d7  cmovnz  ecx, eax; dwProcessId
0x1802fc8da  call    cs:__imp_AllowSetForegroundWindow
0x1802fc8e0  mov     rcx, [rbp+arg_10]
0x1802fc8e4  lea     r9, [rbp+arg_18]
0x1802fc8e8  mov     [rbp+arg_18], r15
0x1802fc8ec  lea     r8, IID_IUnknown
0x1802fc8f3  lea     rdx, CLSID_CShdocvwBroker
0x1802fc8fa  mov     rax, [rcx]
0x1802fc8fd  mov     rax, [rax+30h]
0x1802fc901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fc906  mov     ebx, eax
0x1802fc908  test    eax, eax
0x1802fc90a  js      short loc_1802FC938
0x1802fc90c  mov     rcx, [rbp+arg_18]
0x1802fc910  lea     r8, [rbp+arg_8]
0x1802fc914  lea     rdx, _GUID_806d58df_ee78_4630_9475_f9b337a2dfcb
0x1802fc91b  mov     rax, [rcx]
0x1802fc91e  mov     rax, [rax]
0x1802fc921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fc926  mov     rcx, [rbp+arg_18]
0x1802fc92a  mov     ebx, eax
0x1802fc92c  mov     rax, [rcx]
0x1802fc92f  mov     rax, [rax+10h]
0x1802fc933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fc938  mov     rcx, [rbp+arg_10]
0x1802fc93c  mov     rax, [rcx]
0x1802fc93f  mov     rax, [rax+10h]
0x1802fc943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fc948  test    ebx, ebx
0x1802fc94a  js      loc_1802FCA5E
0x1802fc950  mov     rax, [rbp+arg_8]
0x1802fc954  mov     rcx, [rax]
0x1802fc957  mov     rbx, [rcx+38h]
0x1802fc95b  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1802fc961  mov     rcx, [rbp+arg_8]
0x1802fc965  lea     rdx, [rbp+var_18]
0x1802fc969  movups  xmm0, xmmword ptr [rax]
0x1802fc96c  mov     rax, rbx
0x1802fc96f  movdqu  [rbp+var_18], xmm0
0x1802fc974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fc979  mov     rcx, [rbp+arg_8]
0x1802fc97d  mov     rax, [rcx]
0x1802fc980  mov     rax, [rax+20h]
0x1802fc984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fc989  mov     rcx, [rbp+arg_8]
0x1802fc98d  jmp     loc_1802FCA52
0x1802fc992  call    ?IsHiddenTab@CDoc@@QEBA_NXZ; CDoc::IsHiddenTab(void)
0x1802fc997  test    al, al
0x1802fc999  jnz     loc_1802FCA5E
0x1802fc99f  lea     rcx, [rbp+arg_18]; HWND *
0x1802fc9a3  mov     [rbp+arg_18], r15
0x1802fc9a7  call    ?GetBrowserHWNDForCurrentThread@@YAJPEAPEAUHWND__@@@Z; GetBrowserHWNDForCurrentThread(HWND__ * *)
0x1802fc9ac  test    eax, eax
0x1802fc9ae  js      loc_1802FCA5E
0x1802fc9b4  lea     rcx, [rbp+arg_8]
0x1802fc9b8  mov     [rbp+arg_10], r15
0x1802fc9bc  mov     [rbp+arg_8], r15
0x1802fc9c0  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1802fc9c6  test    eax, eax
0x1802fc9c8  js      loc_1802FCA5E
0x1802fc9ce  mov     rcx, [rbp+arg_8]
0x1802fc9d2  lea     r9, [rbp+dwProcessId]
0x1802fc9d6  mov     [rbp+dwProcessId], r15
0x1802fc9da  lea     r8, IID_IUnknown
0x1802fc9e1  lea     rdx, CLSID_CShdocvwBroker
0x1802fc9e8  mov     rax, [rcx]
0x1802fc9eb  mov     rax, [rax+30h]
0x1802fc9ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fc9f4  mov     ebx, eax
0x1802fc9f6  test    eax, eax
0x1802fc9f8  js      short loc_1802FCA26
0x1802fc9fa  mov     rcx, [rbp+dwProcessId]
0x1802fc9fe  lea     r8, [rbp+arg_10]
0x1802fca02  lea     rdx, _GUID_806d58df_ee78_4630_9475_f9b337a2dfcb
0x1802fca09  mov     rax, [rcx]
0x1802fca0c  mov     rax, [rax]
0x1802fca0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fca14  mov     rcx, [rbp+dwProcessId]
0x1802fca18  mov     ebx, eax
0x1802fca1a  mov     rax, [rcx]
0x1802fca1d  mov     rax, [rax+10h]
0x1802fca21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fca26  mov     rcx, [rbp+arg_8]
0x1802fca2a  mov     rax, [rcx]
0x1802fca2d  mov     rax, [rax+10h]
0x1802fca31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fca36  test    ebx, ebx
0x1802fca38  js      short loc_1802FCA5E
0x1802fca3a  mov     rcx, [rbp+arg_10]
0x1802fca3e  mov     rdx, [rbp+arg_18]
0x1802fca42  mov     rax, [rcx]
0x1802fca45  mov     rax, [rax+30h]
0x1802fca49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fca4e  mov     rcx, [rbp+arg_10]
0x1802fca52  mov     rax, [rcx]
0x1802fca55  mov     rax, [rax+10h]
0x1802fca59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fca5e  mov     rcx, [rsi+38h]; this
0x1802fca62  call    ?GetElementTop@CMarkup@@QEAAPEAVCElement@@XZ; CMarkup::GetElementTop(void)
0x1802fca67  xor     r9d, r9d; struct CMessage *
0x1802fca6a  mov     [rsp+58h+uFlags], r15d; int
0x1802fca6f  xor     r8d, r8d; int *
0x1802fca72  mov     [rsp+58h+var_38], 1; int
0x1802fca7a  xor     edx, edx; int
0x1802fca7c  mov     rcx, rax; this
0x1802fca7f  call    ?BecomeCurrentAndActive@CElement@@QEAAJJPEAHPEAVCMessage@@HJH@Z; CElement::BecomeCurrentAndActive(long,int *,CMessage *,int,long,int)
0x1802fca84  mov     ebx, eax
0x1802fca86  test    eax, eax
0x1802fca88  jnz     short loc_1802FCA9B
0x1802fca8a  mov     rcx, [rsi+38h]; this
0x1802fca8e  call    ?Window@CMarkup@@QEBAPEAVCOmWindowProxy@@XZ; CMarkup::Window(void)
0x1802fca93  mov     rcx, rax; this
0x1802fca96  call    ?Post_onfocus@COmWindowProxy@@QEAAXXZ; COmWindowProxy::Post_onfocus(void)
0x1802fca9b  cmp     ebx, 1
0x1802fca9e  mov     edx, r15d
0x1802fcaa1  mov     rcx, r14; this
0x1802fcaa4  cmovnz  edx, ebx; int
0x1802fcaa7  add     rsp, 58h
0x1802fcaab  pop     r15
0x1802fcaad  pop     r14
0x1802fcaaf  pop     rdi
0x1802fcab0  pop     rsi
0x1802fcab1  pop     rbx
0x1802fcab2  pop     rbp
0x1802fcab3  jmp     ?SetErrorInfo@CBase@@QEBAJJ@Z; CBase::SetErrorInfo(long)
```
