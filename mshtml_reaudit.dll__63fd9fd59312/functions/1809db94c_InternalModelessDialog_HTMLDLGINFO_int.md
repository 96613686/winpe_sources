# InternalModelessDialog(HTMLDLGINFO *,int)

- ea: `0x1809db94c`
- end: `0x1809dc0ee`
- name: `?InternalModelessDialog@@YAJPEAUHTMLDLGINFO@@H@Z`
- size: `1954`
- prototype: `__int64 __fastcall(struct HTMLDLGINFO *, int)`
- caller_count: `4`
- callee_count: `26`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18087efc8`
- `0x1809b5ce4`
- `0x1809d8210`
- `0x1809d8360`

## callees

- `0x1800d6a2c`
- `0x1801af6e0`
- `0x1801b0510`
- `0x1801bf528`
- `0x1801cd5ac`
- `0x1802bf7e4`
- `0x180300074`
- `0x1803380cc`
- `0x1804f8b0c`
- `0x1805b9418`
- `0x1805f5150`
- `0x1807d659c`
- `0x1808393c4`
- `0x1808c8450`
- `0x1809d6444`
- `0x1809db94c`
- `0x1809dc12c`
- `0x1809dc800`
- `0x1809dc97c`
- `0x1809ffbd0`
- `0x18105b0fc`
- `0x18105c304`
- `0x181061c7c`
- `0x181085b00`
- `0x1810c2cb6`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!ResumeThread` at `0x1809dbf08`
- `KERNEL32!ResumeThread` at `0x1809dbf08`
- `KERNEL32!GetCurrentThreadId` at `0x1809dbe0e`
- `KERNEL32!GetCurrentThreadId` at `0x1809dbe0e`
- `KERNEL32!CreateThread` at `0x1809dbe62`
- `KERNEL32!CreateThread` at `0x1809dbe62`
- `KERNEL32!CreateEventW` at `0x1809dbb4a`
- `KERNEL32!CreateEventW` at `0x1809dbb4a`
- `KERNEL32!CloseHandle` at `0x1809dc00b`
- `KERNEL32!CloseHandle` at `0x1809dc051`
- `KERNEL32!CloseHandle` at `0x1809dc00b`
- `KERNEL32!CloseHandle` at `0x1809dc051`
- `USER32!PostMessageW` at `0x1809dbfe7`
- `USER32!PostMessageW` at `0x1809dbfe7`
- `USER32!IsWindow` at `0x1809dbfce`
- `USER32!IsWindow` at `0x1809dbfce`
- `iertutil!__imp_?LCIEUnifiedFrame@@YA_NXZ` at `0x1809dbdf5`
- `iertutil!__imp_?LCIEUnifiedFrame@@YA_NXZ` at `0x1809dbdf5`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1809dbe04`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1809dbe04`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1809dbc68`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1809dbc68`
- `api-ms-win-downlevel-ole32-l1-1-0!CoWaitForMultipleHandles` at `0x1809dbf3d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoWaitForMultipleHandles` at `0x1809dbf3d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1809dc0a2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1809dc0a2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1809dbb20`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1809dbcb4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1809dbd5a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1809dbb20`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1809dbcb4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1809dbd5a`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x1809dbe22`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x1809dbe22`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1809dbdea`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1809dbdea`
- `msIso!__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z` at `0x1809dbe2d`
- `msIso!__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z` at `0x1809dbe2d`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x1809dbe81`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x1809dbe81`
- `urlmon!CoInternetIsFeatureEnabledForUrl` at `0x1809dbd17`
- `urlmon!CoInternetIsFeatureEnabledForUrl` at `0x1809dbd17`
- `OLEAUT32!__imp_VariantCopy` at `0x1809dba57`
- `OLEAUT32!__imp_VariantCopy` at `0x1809dbbb2`
- `OLEAUT32!__imp_VariantCopy` at `0x1809dba57`
- `OLEAUT32!__imp_VariantCopy` at `0x1809dbbb2`

## pseudocode

```c
__int64 __fastcall InternalModelessDialog(struct HTMLDLGINFO *a1, int a2)
{
  CMarkup *v2; // rsi
  __int64 v3; // r14
  _QWORD *v5; // rax
  void *v6; // r13
  char *v7; // r12
  int v8; // ebx
  __int64 v9; // rax
  __int64 v10; // rdi
  const VARIANTARG *v11; // rdx
  __int64 v12; // rbx
  __int64 v13; // rax
  _DWORD *v14; // rbx
  __int64 v15; // rcx
  CSecurityContext *v16; // r14
  int Interface; // eax
  LPUNKNOWN v18; // rbx
  HRESULT LastWin32Error; // ebx
  const struct IE80TabWindowExports *v20; // rax
  __int64 v21; // rcx
  const VARIANTARG *v22; // rdx
  int v23; // r13d
  __int64 v24; // r14
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  IInternetSecurityManager *v29; // rbx
  const WCHAR *v30; // rax
  bool v31; // zf
  DWORD CurrentThreadId; // eax
  int v33; // eax
  char v34; // cl
  DWORD v35; // ebx
  void **v36; // r8
  HRESULT InterfaceAndReleaseStreamAtomic; // eax
  HWND v38; // r10
  CDocument *v39; // rax
  HWND v40; // r10
  struct CWindow *v41; // rax
  HWND *v42; // rax
  UINT v43; // edx
  HWND v44; // rcx
  LPVOID *v45; // rax
  HANDLE v47; // [rsp+30h] [rbp-A9h]
  HANDLE pHandles; // [rsp+38h] [rbp-A1h] BYREF
  struct IStream *v49; // [rsp+40h] [rbp-99h] BYREF
  LPUNKNOWN v50; // [rsp+48h] [rbp-91h] BYREF
  IInternetSecurityManager *pSecMgr; // [rsp+50h] [rbp-89h] BYREF
  LPSTREAM v52; // [rsp+58h] [rbp-81h] BYREF
  LPSTREAM ppStm; // [rsp+60h] [rbp-79h] BYREF
  _QWORD Parameter[5]; // [rsp+70h] [rbp-69h] BYREF
  HWND hWnd; // [rsp+98h] [rbp-41h]
  int v56; // [rsp+A0h] [rbp-39h]
  __int64 v57; // [rsp+A8h] [rbp-31h]
  BOOL v58; // [rsp+B0h] [rbp-29h]
  int v59; // [rsp+B4h] [rbp-25h]
  struct IStream *v60; // [rsp+B8h] [rbp-21h] BYREF
  LPSTREAM pStm; // [rsp+C0h] [rbp-19h] BYREF
  int v62; // [rsp+C8h] [rbp-11h]
  unsigned int v63[2]; // [rsp+CCh] [rbp-Dh] BYREF
  char v64; // [rsp+D4h] [rbp-5h]
  int v65; // [rsp+D8h] [rbp-1h]
  __int64 v66; // [rsp+E0h] [rbp+7h]
  DWORD ThreadId; // [rsp+140h] [rbp+67h] BYREF
  int v68; // [rsp+148h] [rbp+6Fh]
  LPUNKNOWN pUnk; // [rsp+150h] [rbp+77h] BYREF
  DWORD dwindex; // [rsp+158h] [rbp+7Fh] BYREF

  v68 = a2;
  v2 = (CMarkup *)*((_QWORD *)a1 + 15);
  v3 = 0;
  pHandles = 0;
  v49 = 0;
  v52 = 0;
  ppStm = 0;
  ThreadId = 0;
  memset_0(Parameter, 0, 0x78u);
  if ( v2 )
  {
    if ( *(__int64 (__fastcall **)())(*(_QWORD *)v2 + 984LL) != _vtguard )
      goto LABEL_99;
    (*(void (__fastcall **)(CMarkup *))(*(_QWORD *)v2 + 1144LL))(v2);
  }
  v5 = (_QWORD *)*((_QWORD *)a1 + 19);
  v6 = 0;
  v47 = 0;
  if ( v5 )
    *v5 = 0;
  v7 = (char *)a1 + 104;
  v8 = *((_DWORD *)a1 + 26);
  if ( (*((_BYTE *)a1 + 104) & 0x90) == 0x90 )
  {
    *(_QWORD *)a1 = 0;
  }
  else
  {
    v20 = IEProcessHelper::TabWindow();
    LOBYTE(v21) = (v8 & 0x200) != 0;
    if ( ((__int64 (__fastcall *)(__int64, _QWORD, struct HTMLDLGINFO *))v20->WaitForTabWindow)(v21, *(_QWORD *)a1, a1) < 0 )
    {
      v10 = 0;
      LastWin32Error = -2147024891;
      goto LABEL_82;
    }
  }
  v9 = MemoryProtection::HeapAlloc<0>(g_hProcessHeap, 104);
  v10 = v9;
  if ( !v9 )
  {
    LastWin32Error = -2147024882;
    v10 = 0;
    goto LABEL_82;
  }
  v11 = (const VARIANTARG *)*((_QWORD *)a1 + 4);
  v12 = *((_QWORD *)a1 + 1);
  *(_QWORD *)v9 = &CThreadDialogProcParam::`vftable';
  *(_DWORD *)(v9 + 8) = 1;
  *(_OWORD *)(v9 + 16) = 0;
  *(_QWORD *)(v9 + 32) = 0;
  *(_OWORD *)(v9 + 40) = 0;
  *(_QWORD *)(v9 + 56) = 0;
  *(_OWORD *)(v9 + 72) = 0;
  *(_QWORD *)(v9 + 88) = 0;
  *(_QWORD *)(v9 + 96) = 0;
  if ( v11 )
    VariantCopy((VARIANTARG *)(v9 + 16), v11);
  *(_QWORD *)(v10 + 64) = v12;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
  if ( v2 && *((_QWORD *)v2 + 40) )
  {
    v13 = MemoryProtection::HeapAllocClear<1>(g_hProcessHeap, 72);
    v14 = (_DWORD *)v13;
    if ( !v13 )
    {
      LastWin32Error = -2147024882;
      goto LABEL_82;
    }
    v15 = *((_QWORD *)v2 + 40);
    *(_QWORD *)(v13 + 24) = 0;
    *(_DWORD *)(v13 + 20) = 1;
    *(_QWORD *)(v13 + 32) = 0;
    *(_QWORD *)(v13 + 48) = 0;
    *(_QWORD *)v13 = &CSecurityContextMarshal::`vftable'{for `IDispatch'};
    *(_QWORD *)(v13 + 8) = &CSecurityContextMarshal::`vftable'{for `CSecurityContext'};
    *(_QWORD *)(v13 + 64) = v15;
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
    v14[14] = 0;
    v16 = (CSecurityContext *)(v14 + 2);
    pUnk = 0;
    ++v14[4];
    Interface = CSecurityContextMarshal::QueryInterface((CSecurityContextMarshal *)v14, &IID_IDispatch, (void **)&pUnk);
    v18 = pUnk;
    if ( !Interface )
      CoMarshalInterThreadInterfaceInStream(&IID_IDispatch, pUnk, &ppStm);
    ((void (__fastcall *)(LPUNKNOWN))v18->lpVtbl->Release)(v18);
    CSecurityContext::Release(v16);
    v3 = 0;
  }
  pHandles = CreateEventW(0, 0, 0, 0);
  if ( !pHandles )
  {
    LastWin32Error = GetLastWin32Error();
    goto LABEL_82;
  }
  v22 = (const VARIANTARG *)*((_QWORD *)a1 + 7);
  v23 = 0;
  if ( v22 )
    VariantCopy((VARIANTARG *)(v10 + 40), v22);
  if ( v2 )
  {
    *(_QWORD *)(v10 + 96) = v2;
    if ( *(__int64 (__fastcall **)())(*(_QWORD *)v2 + 984LL) != _vtguard )
      goto LABEL_55;
    (*(void (__fastcall **)(CMarkup *))(*(_QWORD *)v2 + 1144LL))(v2);
    v24 = *((_QWORD *)v2 + 40);
    if ( v24 )
    {
      v3 = *(_QWORD *)(v24 + 16);
      if ( v3 )
      {
        v23 = (*(_DWORD *)(v3 + 4868) >> 7) & 1;
        pUnk = 0;
        if ( CDoc::GetPopupMgr((CDoc *)v3, (struct INewWindowManager **)&pUnk) >= 0 )
        {
          CNewWindowManagerStub::Marshal((struct INewWindowManager *)pUnk, &v60);
          ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
        }
        if ( (*(_BYTE *)(v3 + 4872) & 2) != 0 )
          *(_DWORD *)v7 |= 0x10000000u;
        if ( (*(_BYTE *)(v3 + 4872) & 0x40) != 0 )
          *(_DWORD *)v7 |= 0x20000000u;
        if ( IsDualEngineProcess() )
        {
          v50 = 0;
          v25 = TSmartPointer<ID3D11Device>::operator&(&v50);
          v26 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64))(v3 + 56))(
                  *(_QWORD *)(v3 + 56),
                  &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
                  v25);
          Abandonment::RequiredQI(v26);
          CoMarshalInterThreadInterfaceInStream(&IID_IServiceProvider, v50, &pStm);
          TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(&v50);
        }
      }
    }
    else
    {
      v3 = 0;
    }
    v27 = *(_QWORD *)v2;
    pSecMgr = 0;
    if ( *(__int64 (__fastcall **)())(v27 + 984) != _vtguard )
LABEL_55:
      _report_securityfailure(1);
    v28 = (*(__int64 (__fastcall **)(CMarkup *, IInternetSecurityManager **))(v27 + 1008))(v2, &pSecMgr);
    v29 = pSecMgr;
    LODWORD(pUnk) = v28;
    v30 = CMarkup::Url(v2);
    if ( CoInternetIsFeatureEnabledForUrl(FEATURE_FORCE_ADDR_AND_STATUS, 2u, v30, v29) != 1 )
      *(_DWORD *)v7 |= 0x80000000;
    if ( (int)pUnk >= 0 )
      ((void (__fastcall *)(IInternetSecurityManager *))pSecMgr->lpVtbl->Release)(pSecMgr);
  }
  PropagateDialogFlags(*((struct tagVARIANT **)a1 + 4), (unsigned int *)a1 + 26);
  LastWin32Error = CoMarshalInterThreadInterfaceInStream(&IID_IHTMLModelessInit, (LPUNKNOWN)v10, &v52);
  if ( !LastWin32Error )
  {
    v31 = *((_DWORD *)a1 + 16) == 0;
    Parameter[2] = pHandles;
    Parameter[0] = v52;
    Parameter[1] = ppStm;
    Parameter[4] = &v49;
    Parameter[3] = *((_QWORD *)a1 + 1);
    v56 = *(_DWORD *)v7;
    v57 = *(_QWORD *)a1;
    hWnd = 0;
    v58 = v31;
    v59 = v68;
    v62 = *((_DWORD *)a1 + 41);
    v63[1] = *((_DWORD *)a1 + 42);
    v65 = *((_DWORD *)a1 + 43);
    v66 = *((_QWORD *)a1 + 22);
    v63[0] = 0;
    v64 = 0;
    if ( IsoGetDefaultScope() && LCIEUnifiedFrame() && (unsigned __int8)IEConfiguration_GetBool(536870914) )
    {
      CurrentThreadId = GetCurrentThreadId();
      LCIEGetTypedComponentFromThread(0x203u, CurrentThreadId, v63, 0);
      v33 = IsoReferenceDefaultScope(1u, 0);
      v34 = v64;
      if ( !v33 )
        v34 = 1;
      v64 = v34;
    }
    v47 = CreateThread(0, 0, ModelessThreadProc, Parameter, 4u, &ThreadId);
    if ( !v47 )
    {
      if ( v64 )
        IsoReleaseDefaultScope(1u);
      LastWin32Error = GetLastWin32Error();
      goto LABEL_81;
    }
    if ( v23 )
    {
      if ( !v3
        || !(unsigned __int8)IsWebPlatformHostBehaviorSupported<6>(
                               *(unsigned int *)(v3 + 5040),
                               *(unsigned int *)(v3 + 5044),
                               *(unsigned int *)(v3 + 5052),
                               *(unsigned int *)(v3 + 5048))
        && !(unsigned __int8)IsWebPlatformHostBehaviorSupported<6>(
                               *(unsigned int *)(v3 + 5040),
                               *(unsigned int *)(v3 + 5044),
                               *(unsigned int *)(v3 + 5052),
                               *(unsigned int *)(v3 + 5048)) )
      {
LABEL_63:
        ResumeThread(v47);
        dwindex = 0;
        v35 = 0;
        if ( IsOs_Win8OrGreater() )
          v35 = 24;
        LastWin32Error = CoWaitForMultipleHandles(v35, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
        if ( LastWin32Error < 0 )
          goto LABEL_81;
        if ( v49 )
        {
          v36 = (void **)*((_QWORD *)a1 + 19);
          if ( v36 )
          {
            InterfaceAndReleaseStreamAtomic = CoGetInterfaceAndReleaseStreamAtomic(v49, &IID_IHTMLWindow2, v36);
            v49 = 0;
            LastWin32Error = InterfaceAndReleaseStreamAtomic;
            if ( v2 )
            {
              v38 = hWnd;
              if ( !hWnd || *v7 < 0 )
                goto LABEL_76;
              v39 = CMarkup::Document(v2);
              if ( v39 && (v41 = CDocument::Window(v39)) != 0 )
              {
                v42 = (HWND *)CDataAry<CTreeNode *>::Append((char *)v41 + 384);
                if ( v42 )
                  *v42 = hWnd;
              }
              else if ( IsWindow(v40) )
              {
                v44 = hWnd;
                v43 = 16;
                goto LABEL_79;
              }
            }
          }
        }
        v38 = hWnd;
LABEL_76:
        v43 = 1026;
        v44 = v38;
LABEL_79:
        PostMessageW(v44, v43, 0, 0);
        goto LABEL_81;
      }
    }
    else if ( *((_DWORD *)a1 + 43) )
    {
      goto LABEL_63;
    }
    AssociateThreadWithCurrentTab(ThreadId);
    goto LABEL_63;
  }
LABEL_81:
  v6 = v47;
LABEL_82:
  if ( pHandles )
    CloseHandle(pHandles);
  if ( v10 )
    CThreadDialogProcParam::PrivateRelease((CThreadDialogProcParam *)v10);
  if ( v2 )
  {
    if ( *(__int64 (__fastcall **)())(*(_QWORD *)v2 + 984LL) == _vtguard )
    {
      (*(void (__fastcall **)(CMarkup *))(*(_QWORD *)v2 + 1152LL))(v2);
      goto LABEL_89;
    }
LABEL_99:
    _report_securityfailure(1);
  }
LABEL_89:
  if ( v6 )
    CloseHandle(v6);
  if ( v60 )
  {
    pUnk = 0;
    if ( CNewWindowManagerProxy::UnMarshal(v60, (struct INewWindowManager **)&pUnk) >= 0 )
      ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
  }
  if ( pStm )
  {
    pUnk = 0;
    v45 = (LPVOID *)TSmartPointer<ID3D11Device>::operator&(&pUnk);
    CoGetInterfaceAndReleaseStream(pStm, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, v45);
    pStm = 0;
    TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(&pUnk);
  }
  if ( v49 )
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v49 + 16LL))(v49);
  return (unsigned int)LastWin32Error;
}

```

## disassembly

```asm
0x1809db94c  mov     [rsp-8+arg_8], edx
0x1809db950  push    rbp
0x1809db951  push    rbx
0x1809db952  push    rsi
0x1809db953  push    rdi
0x1809db954  push    r12
0x1809db956  push    r13
0x1809db958  push    r14
0x1809db95a  push    r15
0x1809db95c  lea     rbp, [rsp-1Fh]
0x1809db961  sub     rsp, 0F8h
0x1809db968  mov     rsi, [rcx+78h]
0x1809db96c  xor     r14d, r14d
0x1809db96f  mov     r15, rcx
0x1809db972  mov     [rsp+130h+pHandles], r14
0x1809db977  xor     edx, edx; Val
0x1809db979  mov     [rsp+130h+var_F0], r14
0x1809db97e  lea     rcx, [rbp+57h+Parameter]; void *
0x1809db982  mov     [rsp+130h+var_D8], r14
0x1809db987  lea     r8d, [r14+78h]; Size
0x1809db98b  mov     [rbp+57h+ppStm], r14
0x1809db98f  mov     [rbp+57h+ThreadId], r14d
0x1809db993  call    memset_0
0x1809db998  lea     edi, [r14+1]
0x1809db99c  lea     rcx, __vtguard
0x1809db9a3  test    rsi, rsi
0x1809db9a6  jz      short loc_1809DB9C7
0x1809db9a8  mov     rax, [rsi]
0x1809db9ab  cmp     [rax+3D8h], rcx
0x1809db9b2  jnz     loc_1809DC0E6
0x1809db9b8  mov     rax, [rax+478h]
0x1809db9bf  mov     rcx, rsi
0x1809db9c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809db9c7  mov     rax, [r15+98h]
0x1809db9ce  mov     r13, r14
0x1809db9d1  mov     [rsp+130h+var_100], r14
0x1809db9d6  test    rax, rax
0x1809db9d9  jz      short loc_1809DB9DE
0x1809db9db  mov     [rax], r14
0x1809db9de  lea     r12, [r15+68h]
0x1809db9e2  mov     ebx, [r12]
0x1809db9e6  mov     eax, ebx
0x1809db9e8  and     eax, 90h
0x1809db9ed  cmp     al, 90h
0x1809db9ef  jnz     loc_1809DBB66
0x1809db9f5  mov     [r15], r14
0x1809db9f8  mov     rcx, cs:g_hProcessHeap
0x1809db9ff  mov     edx, 68h ; 'h'
0x1809dba04  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x1809dba09  mov     rdi, rax
0x1809dba0c  test    rax, rax
0x1809dba0f  jz      loc_1809DBFEF
0x1809dba15  mov     rdx, [r15+20h]; pvargSrc
0x1809dba19  lea     rax, ??_7CThreadDialogProcParam@@6B@; const CThreadDialogProcParam::`vftable'
0x1809dba20  mov     rbx, [r15+8]
0x1809dba24  lea     rcx, [rdi+10h]; pvargDest
0x1809dba28  mov     [rdi], rax
0x1809dba2b  xorps   xmm0, xmm0
0x1809dba2e  mov     dword ptr [rdi+8], 1
0x1809dba35  xor     eax, eax
0x1809dba37  movups  xmmword ptr [rcx], xmm0
0x1809dba3a  mov     [rcx+10h], rax
0x1809dba3e  movups  xmmword ptr [rdi+28h], xmm0
0x1809dba42  mov     [rdi+38h], rax
0x1809dba46  movups  xmmword ptr [rdi+48h], xmm0
0x1809dba4a  mov     [rdi+58h], rax
0x1809dba4e  mov     [rdi+60h], r14
0x1809dba52  test    rdx, rdx
0x1809dba55  jz      short loc_1809DBA5D
0x1809dba57  call    cs:__imp_VariantCopy
0x1809dba5d  mov     [rdi+40h], rbx
0x1809dba61  mov     rcx, rbx
0x1809dba64  mov     rax, [rbx]
0x1809dba67  mov     rax, [rax+8]
0x1809dba6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809dba70  test    rsi, rsi
0x1809dba73  jz      loc_1809DBB40
0x1809dba79  cmp     [rsi+140h], r14
0x1809dba80  jz      loc_1809DBB40
0x1809dba86  mov     rcx, cs:g_hProcessHeap
0x1809dba8d  mov     edx, 48h ; 'H'
0x1809dba92  call    ??$HeapAllocClear@$00@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAllocClear<1>(void *,unsigned __int64)
0x1809dba97  mov     rbx, rax
0x1809dba9a  test    rax, rax
0x1809dba9d  jz      loc_1809DBB96
0x1809dbaa3  mov     rcx, [rsi+140h]
0x1809dbaaa  mov     [rax+18h], r14
0x1809dbaae  mov     dword ptr [rax+14h], 1
0x1809dbab5  mov     [rax+20h], r14
0x1809dbab9  mov     [rax+30h], r14
0x1809dbabd  lea     rax, ??_7CSecurityContextMarshal@@6BIDispatch@@@; const CSecurityContextMarshal::`vftable'{for `IDispatch'}
0x1809dbac4  mov     [rbx], rax
0x1809dbac7  lea     rax, ??_7CSecurityContextMarshal@@6BCSecurityContext@@@; const CSecurityContextMarshal::`vftable'{for `CSecurityContext'}
0x1809dbace  mov     [rbx+8], rax
0x1809dbad2  mov     [rbx+40h], rcx
0x1809dbad6  test    rcx, rcx
0x1809dbad9  jz      short loc_1809DBAE7
0x1809dbadb  mov     rax, [rcx]
0x1809dbade  mov     rax, [rax+8]
0x1809dbae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809dbae7  mov     [rbx+38h], r14d
0x1809dbaeb  lea     r8, [rbp+57h+pUnk]; void **
0x1809dbaef  lea     r14, [rbx+8]
0x1809dbaf3  mov     [rbp+57h+pUnk], r13
0x1809dbaf7  inc     dword ptr [r14+8]
0x1809dbafb  lea     rdx, IID_IDispatch; struct _GUID *
0x1809dbb02  mov     rcx, rbx; this
0x1809dbb05  call    ?QueryInterface@CSecurityContextMarshal@@UEAAJAEBU_GUID@@PEAPEAX@Z; CSecurityContextMarshal::QueryInterface(_GUID const &,void * *)
0x1809dbb0a  mov     rbx, [rbp+57h+pUnk]
0x1809dbb0e  test    eax, eax
0x1809dbb10  jnz     short loc_1809DBB26
0x1809dbb12  lea     r8, [rbp+57h+ppStm]; ppStm
0x1809dbb16  mov     rdx, rbx; pUnk
0x1809dbb19  lea     rcx, IID_IDispatch; riid
0x1809dbb20  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x1809dbb26  mov     rax, [rbx]
0x1809dbb29  mov     rcx, rbx
0x1809dbb2c  mov     rax, [rax+10h]
0x1809dbb30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809dbb35  mov     rcx, r14; this
0x1809dbb38  call    ?Release@CSecurityContext@@UEAAKXZ; CSecurityContext::Release(void)
0x1809dbb3d  xor     r14d, r14d
0x1809dbb40  xor     r9d, r9d; lpName
0x1809dbb43  xor     r8d, r8d; bInitialState
0x1809dbb46  xor     edx, edx; bManualReset
0x1809dbb48  xor     ecx, ecx; lpEventAttributes
0x1809dbb4a  call    cs:__imp_CreateEventW
0x1809dbb50  mov     [rsp+130h+pHandles], rax
0x1809dbb55  test    rax, rax
0x1809dbb58  jnz     short loc_1809DBBA0
0x1809dbb5a  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1809dbb5f  mov     ebx, eax
0x1809dbb61  jmp     loc_1809DC001
0x1809dbb66  call    ?TabWindow@IEProcessHelper@@SAPEBUIE80TabWindowExports@@XZ; IEProcessHelper::TabWindow(void)
0x1809dbb6b  mov     rdx, [r15]
0x1809dbb6e  mov     r8, r15
0x1809dbb71  shr     ebx, 9
0x1809dbb74  and     bl, dil
0x1809dbb77  mov     rax, [rax]
0x1809dbb7a  mov     cl, bl
0x1809dbb7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809dbb81  test    eax, eax
0x1809dbb83  jns     loc_1809DB9F8
0x1809dbb89  mov     rdi, r14
0x1809dbb8c  mov     ebx, 80070005h
0x1809dbb91  jmp     loc_1809DC001
0x1809dbb96  mov     ebx, 8007000Eh
0x1809dbb9b  jmp     loc_1809DC001
0x1809dbba0  mov     rdx, [r15+38h]; pvargSrc
0x1809dbba4  xor     ebx, ebx
0x1809dbba6  mov     r13d, r14d
0x1809dbba9  test    rdx, rdx
0x1809dbbac  jz      short loc_1809DBBB8
0x1809dbbae  lea     rcx, [rdi+28h]; pvargDest
0x1809dbbb2  call    cs:__imp_VariantCopy
0x1809dbbb8  test    rsi, rsi
0x1809dbbbb  jz      loc_1809DBD3F
0x1809dbbc1  mov     [rdi+60h], rsi
0x1809dbbc5  lea     rcx, __vtguard
0x1809dbbcc  mov     rax, [rsi]
0x1809dbbcf  cmp     [rax+3D8h], rcx
0x1809dbbd6  jnz     loc_1809DBE93
0x1809dbbdc  mov     rax, [rax+478h]
0x1809dbbe3  mov     rcx, rsi
0x1809dbbe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809dbbeb  mov     r14, [rsi+140h]
0x1809dbbf2  test    r14, r14
0x1809dbbf5  jz      loc_1809DBCC6
0x1809dbbfb  mov     r14, [r14+10h]
0x1809dbbff  test    r14, r14
0x1809dbc02  jz      loc_1809DBCC9
0x1809dbc08  mov     r13d, [r14+1304h]
0x1809dbc0f  lea     rdx, [rbp+57h+pUnk]; struct INewWindowManager **
0x1809dbc13  shr     r13d, 7
0x1809dbc17  mov     rcx, r14; this
0x1809dbc1a  and     r13d, 1
0x1809dbc1e  mov     [rbp+57h+pUnk], rbx
0x1809dbc22  call    ?GetPopupMgr@CDoc@@QEAAJPEAPEAUINewWindowManager@@@Z; CDoc::GetPopupMgr(INewWindowManager * *)
0x1809dbc27  test    eax, eax
0x1809dbc29  js      short loc_1809DBC48
0x1809dbc2b  mov     rcx, [rbp+57h+pUnk]; struct INewWindowManager *
0x1809dbc2f  lea     rdx, [rbp+57h+var_78]; struct IStream **
0x1809dbc33  call    ?Marshal@CNewWindowManagerStub@@SAJPEAUINewWindowManager@@PEAPEAUIStream@@@Z; CNewWindowManagerStub::Marshal(INewWindowManager *,IStream * *)
0x1809dbc38  mov     rcx, [rbp+57h+pUnk]
0x1809dbc3c  mov     rax, [rcx]
0x1809dbc3f  mov     rax, [rax+10h]
0x1809dbc43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809dbc48  test    byte ptr [r14+1308h], 2
0x1809dbc50  jz      short loc_1809DBC58
0x1809dbc52  bts     dword ptr [r12], 1Ch
0x1809dbc58  test    byte ptr [r14+1308h], 40h
0x1809dbc60  jz      short loc_1809DBC68
0x1809dbc62  bts     dword ptr [r12], 1Dh
0x1809dbc68  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1809dbc6e  test    al, al
0x1809dbc70  jz      short loc_1809DBCC9
0x1809dbc72  lea     rcx, [rsp+130h+var_E8]
0x1809dbc77  mov     [rsp+130h+var_E8], rbx
0x1809dbc7c  call    ??I?$TSmartPointer@UID3D11Device@@@@QEAAPEAPEAUID3D11Device@@XZ; TSmartPointer<ID3D11Device>::operator&(void)
0x1809dbc81  mov     rcx, [r14+38h]
0x1809dbc85  mov     r8, rax
0x1809dbc88  mov     rdx, [rcx]
0x1809dbc8b  mov     r9, [rdx]
0x1809dbc8e  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x1809dbc95  mov     rax, r9
0x1809dbc98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809dbc9d  mov     ecx, eax; int
0x1809dbc9f  call    ?RequiredQI@Abandonment@@SAXJ@Z; Abandonment::RequiredQI(long)
0x1809dbca4  mov     rdx, [rsp+130h+var_E8]; pUnk
0x1809dbca9  lea     r8, [rbp+57h+pStm]; ppStm
0x1809dbcad  lea     rcx, IID_IServiceProvider; riid
0x1809dbcb4  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x1809dbcba  lea     rcx, [rsp+130h+var_E8]; void *
0x1809dbcbf  call    ??1?$TSmartPointer@UIWebPlatformPermanentSecurityManagerInternal@@@@QEAA@XZ; TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(void)
0x1809dbcc4  jmp     short loc_1809DBCC9
0x1809dbcc6  mov     r14, rbx
0x1809dbcc9  mov     rax, [rsi]
0x1809dbccc  lea     rcx, __vtguard
0x1809dbcd3  mov     [rsp+130h+pSecMgr], rbx
0x1809dbcd8  cmp     [rax+3D8h], rcx
0x1809dbcdf  jnz     loc_1809DBE93
0x1809dbce5  mov     rax, [rax+3F0h]
0x1809dbcec  lea     rdx, [rsp+130h+pSecMgr]
0x1809dbcf1  mov     rcx, rsi
0x1809dbcf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809dbcf9  mov     rbx, [rsp+130h+pSecMgr]
0x1809dbcfe  mov     rcx, rsi; this
0x1809dbd01  mov     dword ptr [rbp+57h+pUnk], eax
0x1809dbd04  call    ?Url@CMarkup@@QEAAPEAGXZ; CMarkup::Url(void)
0x1809dbd09  mov     edx, 2; dwFlags
0x1809dbd0e  mov     r9, rbx; pSecMgr
0x1809dbd11  mov     r8, rax; szURL
0x1809dbd14  lea     ecx, [rdx+15h]; FeatureEntry
0x1809dbd17  call    cs:__imp_CoInternetIsFeatureEnabledForUrl
0x1809dbd1d  cmp     eax, 1
0x1809dbd20  jz      short loc_1809DBD28
0x1809dbd22  bts     dword ptr [r12], 1Fh
0x1809dbd28  cmp     dword ptr [rbp+57h+pUnk], 0
0x1809dbd2c  jl      short loc_1809DBD3F
0x1809dbd2e  mov     rcx, [rsp+130h+pSecMgr]
0x1809dbd33  mov     rax, [rcx]
0x1809dbd36  mov     rax, [rax+10h]
0x1809dbd3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809dbd3f  mov     rcx, [r15+20h]; struct tagVARIANT *
0x1809dbd43  mov     rdx, r12; unsigned int *
0x1809dbd46  call    ?PropagateDialogFlags@@YAXPEAUtagVARIANT@@PEAK@Z; PropagateDialogFlags(tagVARIANT *,ulong *)
0x1809dbd4b  lea     r8, [rsp+130h+var_D8]; ppStm
0x1809dbd50  mov     rdx, rdi; pUnk
0x1809dbd53  lea     rcx, IID_IHTMLModelessInit; riid
0x1809dbd5a  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x1809dbd60  mov     ebx, eax
0x1809dbd62  test    eax, eax
0x1809dbd64  jnz     loc_1809DBFF9
0x1809dbd6a  mov     rax, [rsp+130h+pHandles]
0x1809dbd6f  xor     ebx, ebx
0x1809dbd71  cmp     [r15+40h], ebx
0x1809dbd75  mov     [rbp+57h+var_B0], rax
0x1809dbd79  mov     rax, [rsp+130h+var_D8]
0x1809dbd7e  mov     [rbp+57h+Parameter], rax
0x1809dbd82  mov     rax, [rbp+57h+ppStm]
0x1809dbd86  mov     [rbp+57h+var_B8], rax
0x1809dbd8a  lea     rax, [rsp+130h+var_F0]
0x1809dbd8f  mov     [rbp+57h+var_A0], rax
0x1809dbd93  mov     rax, [r15+8]
0x1809dbd97  mov     [rbp+57h+var_A8], rax
0x1809dbd9b  mov     eax, [r12]
0x1809dbd9f  mov     [rbp+57h+var_90], eax
0x1809dbda2  mov     rax, [r15]
0x1809dbda5  mov     [rbp+57h+var_88], rax
0x1809dbda9  mov     eax, ebx
0x1809dbdab  setz    al
0x1809dbdae  mov     [rbp+57h+hWnd], rbx
0x1809dbdb2  mov     [rbp+57h+var_80], eax
0x1809dbdb5  mov     eax, [rbp+57h+arg_8]
0x1809dbdb8  mov     [rbp+57h+var_7C], eax
0x1809dbdbb  mov     eax, [r15+0A4h]
0x1809dbdc2  mov     [rbp+57h+var_68], eax
0x1809dbdc5  mov     eax, [r15+0A8h]
0x1809dbdcc  mov     [rbp+57h+var_60], eax
0x1809dbdcf  mov     eax, [r15+0ACh]
0x1809dbdd6  mov     [rbp+57h+var_58], eax
0x1809dbdd9  mov     rax, [r15+0B0h]
0x1809dbde0  mov     [rbp+57h+var_50], rax
0x1809dbde4  mov     [rbp+57h+var_64], ebx
0x1809dbde7  mov     [rbp+57h+var_5C], bl
0x1809dbdea  call    cs:__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ; IsoGetDefaultScope(void)
0x1809dbdf0  test    rax, rax
0x1809dbdf3  jz      short loc_1809DBE42
0x1809dbdf5  call    cs:__imp_?LCIEUnifiedFrame@@YA_NXZ; LCIEUnifiedFrame(void)
0x1809dbdfb  test    al, al
0x1809dbdfd  jz      short loc_1809DBE42
0x1809dbdff  mov     ecx, 20000002h
0x1809dbe04  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1809dbe0a  test    al, al
0x1809dbe0c  jz      short loc_1809DBE42
0x1809dbe0e  call    cs:__imp_GetCurrentThreadId
0x1809dbe14  xor     r9d, r9d
0x1809dbe17  lea     r8, [rbp+57h+var_64]
0x1809dbe1b  mov     edx, eax
0x1809dbe1d  mov     ecx, 203h
  ... truncated ...
```
