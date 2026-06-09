# InternalModelessDialog(HTMLDLGINFO *,int)

- ea: `0x1809ec814`
- end: `0x1809ed033`
- name: `?InternalModelessDialog@@YAJPEAUHTMLDLGINFO@@H@Z`
- size: `2079`
- prototype: `__int64 __fastcall(struct HTMLDLGINFO *, int)`
- caller_count: `4`
- callee_count: `27`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180886278`
- `0x1809c56b0`
- `0x1809e8f30`
- `0x1809e9090`

## callees

- `0x180013efc`
- `0x18005d080`
- `0x18006b2e8`
- `0x1800c5000`
- `0x18026a150`
- `0x18027fb5c`
- `0x1803ddae0`
- `0x180402a74`
- `0x18059fd60`
- `0x1805eb9a0`
- `0x1805f8874`
- `0x18069f038`
- `0x1807e1ba4`
- `0x18083bed4`
- `0x1808d29c0`
- `0x1809e7024`
- `0x1809ec814`
- `0x1809ed06c`
- `0x1809ed7b0`
- `0x1809ed92c`
- `0x180a11b60`
- `0x18108ae3c`
- `0x18108c1b0`
- `0x18109208c`
- `0x1810b78e0`
- `0x1810f6516`
- `0x181104010`

## import_xrefs

- `KERNEL32!ResumeThread` at `0x1809ece22`
- `KERNEL32!ResumeThread` at `0x1809ece22`
- `KERNEL32!GetCurrentThreadId` at `0x1809ecd0a`
- `KERNEL32!GetCurrentThreadId` at `0x1809ecd0a`
- `KERNEL32!CreateThread` at `0x1809ecd70`
- `KERNEL32!CreateThread` at `0x1809ecd70`
- `KERNEL32!CreateEventW` at `0x1809eca1e`
- `KERNEL32!CreateEventW` at `0x1809eca1e`
- `KERNEL32!CloseHandle` at `0x1809ecf3d`
- `KERNEL32!CloseHandle` at `0x1809ecf89`
- `KERNEL32!CloseHandle` at `0x1809ecf3d`
- `KERNEL32!CloseHandle` at `0x1809ecf89`
- `USER32!PostMessageW` at `0x1809ecf13`
- `USER32!PostMessageW` at `0x1809ecf13`
- `USER32!IsWindow` at `0x1809ecef4`
- `USER32!IsWindow` at `0x1809ecef4`
- `iertutil!__imp_?LCIEUnifiedFrame@@YA_NXZ` at `0x1809ecce5`
- `iertutil!__imp_?LCIEUnifiedFrame@@YA_NXZ` at `0x1809ecce5`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1809eccfa`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1809eccfa`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1809ecb3f`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1809ecb3f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoWaitForMultipleHandles` at `0x1809ece5d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoWaitForMultipleHandles` at `0x1809ece5d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1809ecfe0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1809ecfe0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1809ec9ee`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1809ecb91`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1809ecc3e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1809ec9ee`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1809ecb91`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1809ecc3e`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x1809ecd24`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x1809ecd24`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1809eccd4`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1809eccd4`
- `msIso!__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z` at `0x1809ecd35`
- `msIso!__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z` at `0x1809ecd35`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x1809ecd95`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x1809ecd95`
- `urlmon!CoInternetIsFeatureEnabledForUrl` at `0x1809ecbf5`
- `urlmon!CoInternetIsFeatureEnabledForUrl` at `0x1809ecbf5`
- `OLEAUT32!__imp_VariantCopy` at `0x1809ec91f`
- `OLEAUT32!__imp_VariantCopy` at `0x1809eca8c`
- `OLEAUT32!__imp_VariantCopy` at `0x1809ec91f`
- `OLEAUT32!__imp_VariantCopy` at `0x1809eca8c`

## pseudocode

```c
__int64 __fastcall InternalModelessDialog(struct HTMLDLGINFO *a1, int a2)
{
  CMarkup *v2; // rsi
  struct CDoc *v3; // r14
  __int64 v5; // rdx
  __int64 v6; // r8
  _QWORD *v7; // rax
  void *v8; // r13
  char *v9; // r12
  int v10; // ebx
  __int64 v11; // rax
  __int64 v12; // rdi
  const VARIANTARG *v13; // rdx
  __int64 v14; // rbx
  __int64 v15; // rax
  _DWORD *v16; // rbx
  __int64 v17; // rcx
  CSecurityContext *v18; // r14
  int Interface; // eax
  LPUNKNOWN v20; // rbx
  HRESULT LastWin32Error; // ebx
  const struct IE80TabWindowExports *v22; // rax
  __int64 v23; // rcx
  const VARIANTARG *v24; // rdx
  int v25; // r13d
  struct CDoc *v26; // rax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rax
  int v30; // eax
  IInternetSecurityManager *v31; // rbx
  const WCHAR *v32; // rax
  bool v33; // zf
  DWORD CurrentThreadId; // eax
  int v35; // eax
  char v36; // cl
  DWORD v37; // ebx
  void **v38; // r8
  HRESULT InterfaceAndReleaseStreamAtomic; // eax
  HWND v40; // r10
  CDocument *v41; // rax
  HWND v42; // r10
  struct CWindow *v43; // rax
  HWND *v44; // rax
  UINT v45; // edx
  HWND v46; // rcx
  LPVOID *v47; // rax
  HANDLE v49; // [rsp+30h] [rbp-A9h]
  HANDLE pHandles; // [rsp+38h] [rbp-A1h] BYREF
  struct IStream *v51; // [rsp+40h] [rbp-99h] BYREF
  LPUNKNOWN v52; // [rsp+48h] [rbp-91h] BYREF
  IInternetSecurityManager *pSecMgr; // [rsp+50h] [rbp-89h] BYREF
  LPSTREAM v54; // [rsp+58h] [rbp-81h] BYREF
  LPSTREAM ppStm; // [rsp+60h] [rbp-79h] BYREF
  _QWORD Parameter[5]; // [rsp+70h] [rbp-69h] BYREF
  HWND hWnd; // [rsp+98h] [rbp-41h]
  int v58; // [rsp+A0h] [rbp-39h]
  __int64 v59; // [rsp+A8h] [rbp-31h]
  BOOL v60; // [rsp+B0h] [rbp-29h]
  int v61; // [rsp+B4h] [rbp-25h]
  struct IStream *v62; // [rsp+B8h] [rbp-21h] BYREF
  LPSTREAM pStm; // [rsp+C0h] [rbp-19h] BYREF
  int v64; // [rsp+C8h] [rbp-11h]
  unsigned int v65[2]; // [rsp+CCh] [rbp-Dh] BYREF
  char v66; // [rsp+D4h] [rbp-5h]
  int v67; // [rsp+D8h] [rbp-1h]
  __int64 v68; // [rsp+E0h] [rbp+7h]
  DWORD ThreadId; // [rsp+140h] [rbp+67h] BYREF
  int v70; // [rsp+148h] [rbp+6Fh]
  LPUNKNOWN pUnk; // [rsp+150h] [rbp+77h] BYREF
  DWORD dwindex; // [rsp+158h] [rbp+7Fh] BYREF

  v70 = a2;
  v2 = (CMarkup *)*((_QWORD *)a1 + 15);
  v3 = 0;
  pHandles = 0;
  v51 = 0;
  v54 = 0;
  ppStm = 0;
  ThreadId = 0;
  memset_0(Parameter, 0, 0x78u);
  if ( v2 )
  {
    if ( *(__int64 (__fastcall **)())(*(_QWORD *)v2 + 984LL) != _vtguard )
      goto LABEL_97;
    (*(void (__fastcall **)(CMarkup *))(*(_QWORD *)v2 + 1144LL))(v2);
  }
  v7 = (_QWORD *)*((_QWORD *)a1 + 19);
  v8 = 0;
  v49 = 0;
  if ( v7 )
    *v7 = 0;
  v9 = (char *)a1 + 104;
  v10 = *((_DWORD *)a1 + 26);
  if ( (*((_BYTE *)a1 + 104) & 0x90) == 0x90 )
  {
    *(_QWORD *)a1 = 0;
  }
  else
  {
    v22 = IEProcessHelper::TabWindow();
    LOBYTE(v23) = (v10 & 0x200) != 0;
    if ( ((__int64 (__fastcall *)(__int64, _QWORD, struct HTMLDLGINFO *))v22->WaitForTabWindow)(v23, *(_QWORD *)a1, a1) < 0 )
    {
      v12 = 0;
      LastWin32Error = -2147024891;
      goto LABEL_80;
    }
  }
  v11 = MemoryProtection::HeapAlloc<0>(g_hProcessHeap, 104, v6);
  v12 = v11;
  if ( !v11 )
  {
    LastWin32Error = -2147024882;
    v12 = 0;
    goto LABEL_80;
  }
  v13 = (const VARIANTARG *)*((_QWORD *)a1 + 4);
  v14 = *((_QWORD *)a1 + 1);
  *(_QWORD *)v11 = &CThreadDialogProcParam::`vftable';
  *(_DWORD *)(v11 + 8) = 1;
  *(_OWORD *)(v11 + 16) = 0;
  *(_QWORD *)(v11 + 32) = 0;
  *(_OWORD *)(v11 + 40) = 0;
  *(_QWORD *)(v11 + 56) = 0;
  *(_OWORD *)(v11 + 72) = 0;
  *(_QWORD *)(v11 + 88) = 0;
  *(_QWORD *)(v11 + 96) = 0;
  if ( v13 )
    VariantCopy((VARIANTARG *)(v11 + 16), v13);
  *(_QWORD *)(v12 + 64) = v14;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
  if ( v2 && *((_QWORD *)v2 + 40) )
  {
    v15 = MemoryProtection::HeapAllocClear<1>(g_hProcessHeap, 72);
    v16 = (_DWORD *)v15;
    if ( !v15 )
    {
      LastWin32Error = -2147024882;
      goto LABEL_80;
    }
    v17 = *((_QWORD *)v2 + 40);
    *(_QWORD *)(v15 + 24) = 0;
    *(_DWORD *)(v15 + 20) = 1;
    *(_QWORD *)(v15 + 32) = 0;
    *(_QWORD *)(v15 + 48) = 0;
    *(_QWORD *)v15 = &CSecurityContextMarshal::`vftable'{for `IDispatch'};
    *(_QWORD *)(v15 + 8) = &CSecurityContextMarshal::`vftable'{for `CSecurityContext'};
    *(_QWORD *)(v15 + 64) = v17;
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
    v16[14] = 0;
    v18 = (CSecurityContext *)(v16 + 2);
    pUnk = 0;
    ++v16[4];
    Interface = CSecurityContextMarshal::QueryInterface((CSecurityContextMarshal *)v16, &IID_IDispatch, (void **)&pUnk);
    v20 = pUnk;
    if ( !Interface )
      CoMarshalInterThreadInterfaceInStream(&IID_IDispatch, pUnk, &ppStm);
    ((void (__fastcall *)(LPUNKNOWN))v20->lpVtbl->Release)(v20);
    CSecurityContext::Release(v18);
    v3 = 0;
  }
  pHandles = CreateEventW(0, 0, 0, 0);
  if ( !pHandles )
  {
    LastWin32Error = GetLastWin32Error();
    goto LABEL_80;
  }
  v24 = (const VARIANTARG *)*((_QWORD *)a1 + 7);
  v25 = 0;
  if ( v24 )
    VariantCopy((VARIANTARG *)(v12 + 40), v24);
  if ( v2 )
  {
    *(_QWORD *)(v12 + 96) = v2;
    if ( *(__int64 (__fastcall **)())(*(_QWORD *)v2 + 984LL) != _vtguard )
      goto LABEL_53;
    (*(void (__fastcall **)(CMarkup *))(*(_QWORD *)v2 + 1144LL))(v2);
    v26 = CMarkup::Doc(v2);
    v3 = v26;
    if ( v26 )
    {
      v25 = (*((_DWORD *)v26 + 1217) >> 7) & 1;
      pUnk = 0;
      if ( CDoc::GetPopupMgr(v26, (struct INewWindowManager **)&pUnk) >= 0 )
      {
        CNewWindowManagerStub::Marshal((struct INewWindowManager *)pUnk, &v62);
        ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
      }
      if ( (*((_BYTE *)v3 + 4872) & 2) != 0 )
        *(_DWORD *)v9 |= 0x10000000u;
      if ( (*((_BYTE *)v3 + 4872) & 0x40) != 0 )
        *(_DWORD *)v9 |= 0x20000000u;
      if ( IsDualEngineProcess() )
      {
        v52 = 0;
        v27 = TSmartPointer<ID3D11Device>::operator&(&v52);
        v28 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64))v3 + 7))(
                *((_QWORD *)v3 + 7),
                &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
                v27);
        Abandonment::RequiredQI(v28);
        CoMarshalInterThreadInterfaceInStream(&IID_IServiceProvider, v52, &pStm);
        TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(&v52);
      }
    }
    v29 = *(_QWORD *)v2;
    pSecMgr = 0;
    if ( *(__int64 (__fastcall **)())(v29 + 984) != _vtguard )
LABEL_53:
      _report_securityfailure(1, v24);
    v30 = (*(__int64 (__fastcall **)(CMarkup *, IInternetSecurityManager **))(v29 + 1008))(v2, &pSecMgr);
    v31 = pSecMgr;
    LODWORD(pUnk) = v30;
    v32 = CMarkup::Url(v2);
    if ( CoInternetIsFeatureEnabledForUrl(FEATURE_FORCE_ADDR_AND_STATUS, 2u, v32, v31) != 1 )
      *(_DWORD *)v9 |= 0x80000000;
    if ( (int)pUnk >= 0 )
      ((void (__fastcall *)(IInternetSecurityManager *))pSecMgr->lpVtbl->Release)(pSecMgr);
  }
  PropagateDialogFlags(*((struct tagVARIANT **)a1 + 4), (unsigned int *)a1 + 26);
  LastWin32Error = CoMarshalInterThreadInterfaceInStream(&IID_IHTMLModelessInit, (LPUNKNOWN)v12, &v54);
  if ( !LastWin32Error )
  {
    v33 = *((_DWORD *)a1 + 16) == 0;
    Parameter[2] = pHandles;
    Parameter[0] = v54;
    Parameter[1] = ppStm;
    Parameter[4] = &v51;
    Parameter[3] = *((_QWORD *)a1 + 1);
    v58 = *(_DWORD *)v9;
    v59 = *(_QWORD *)a1;
    hWnd = 0;
    v60 = v33;
    v61 = v70;
    v64 = *((_DWORD *)a1 + 41);
    v65[1] = *((_DWORD *)a1 + 42);
    v67 = *((_DWORD *)a1 + 43);
    v68 = *((_QWORD *)a1 + 22);
    v65[0] = 0;
    v66 = 0;
    if ( IsoGetDefaultScope() && LCIEUnifiedFrame() && (unsigned __int8)IEConfiguration_GetBool(536870914) )
    {
      CurrentThreadId = GetCurrentThreadId();
      LCIEGetTypedComponentFromThread(0x203u, CurrentThreadId, v65, 0);
      v35 = IsoReferenceDefaultScope(1u, 0);
      v36 = v66;
      if ( !v35 )
        v36 = 1;
      v66 = v36;
    }
    v49 = CreateThread(0, 0, ModelessThreadProc, Parameter, 4u, &ThreadId);
    if ( !v49 )
    {
      if ( v66 )
        IsoReleaseDefaultScope(1u);
      LastWin32Error = GetLastWin32Error();
      goto LABEL_79;
    }
    if ( v25 )
    {
      if ( !v3
        || !(unsigned __int8)IsWebPlatformHostBehaviorSupported<6>(
                               *((unsigned int *)v3 + 1260),
                               *((unsigned int *)v3 + 1261),
                               *((unsigned int *)v3 + 1263),
                               *((unsigned int *)v3 + 1262))
        && !(unsigned __int8)IsWebPlatformHostBehaviorSupported<6>(
                               *((unsigned int *)v3 + 1260),
                               *((unsigned int *)v3 + 1261),
                               *((unsigned int *)v3 + 1263),
                               *((unsigned int *)v3 + 1262)) )
      {
LABEL_61:
        ResumeThread(v49);
        dwindex = 0;
        v37 = 0;
        if ( IsOs_Win8OrGreater() )
          v37 = 24;
        LastWin32Error = CoWaitForMultipleHandles(v37, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
        if ( LastWin32Error < 0 )
          goto LABEL_79;
        if ( v51 )
        {
          v38 = (void **)*((_QWORD *)a1 + 19);
          if ( v38 )
          {
            InterfaceAndReleaseStreamAtomic = CoGetInterfaceAndReleaseStreamAtomic(v51, &IID_IHTMLWindow2, v38);
            v51 = 0;
            LastWin32Error = InterfaceAndReleaseStreamAtomic;
            if ( v2 )
            {
              v40 = hWnd;
              if ( !hWnd || *v9 < 0 )
                goto LABEL_74;
              v41 = CMarkup::Document(v2);
              if ( v41 && (v43 = CDocument::Window(v41)) != 0 )
              {
                v44 = (HWND *)CDataAry<CTreeNode *>::Append((char *)v43 + 384);
                if ( v44 )
                  *v44 = hWnd;
              }
              else if ( IsWindow(v42) )
              {
                v46 = hWnd;
                v45 = 16;
                goto LABEL_77;
              }
            }
          }
        }
        v40 = hWnd;
LABEL_74:
        v45 = 1026;
        v46 = v40;
LABEL_77:
        PostMessageW(v46, v45, 0, 0);
        goto LABEL_79;
      }
    }
    else if ( *((_DWORD *)a1 + 43) )
    {
      goto LABEL_61;
    }
    AssociateThreadWithCurrentTab(ThreadId);
    goto LABEL_61;
  }
LABEL_79:
  v8 = v49;
LABEL_80:
  if ( pHandles )
    CloseHandle(pHandles);
  if ( v12 )
    CThreadDialogProcParam::PrivateRelease((CThreadDialogProcParam *)v12);
  if ( v2 )
  {
    if ( *(__int64 (__fastcall **)())(*(_QWORD *)v2 + 984LL) == _vtguard )
    {
      (*(void (__fastcall **)(CMarkup *))(*(_QWORD *)v2 + 1152LL))(v2);
      goto LABEL_87;
    }
LABEL_97:
    _report_securityfailure(1, v5);
  }
LABEL_87:
  if ( v8 )
    CloseHandle(v8);
  if ( v62 )
  {
    pUnk = 0;
    if ( CNewWindowManagerProxy::UnMarshal(v62, (struct INewWindowManager **)&pUnk) >= 0 )
      ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
  }
  if ( pStm )
  {
    pUnk = 0;
    v47 = (LPVOID *)TSmartPointer<ID3D11Device>::operator&(&pUnk);
    CoGetInterfaceAndReleaseStream(pStm, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, v47);
    pStm = 0;
    TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(&pUnk);
  }
  if ( v51 )
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v51 + 16LL))(v51);
  return (unsigned int)LastWin32Error;
}

```

## disassembly

```asm
0x1809ec814  mov     [rsp-8+arg_8], edx
0x1809ec818  push    rbp
0x1809ec819  push    rbx
0x1809ec81a  push    rsi
0x1809ec81b  push    rdi
0x1809ec81c  push    r12
0x1809ec81e  push    r13
0x1809ec820  push    r14
0x1809ec822  push    r15
0x1809ec824  lea     rbp, [rsp-1Fh]
0x1809ec829  sub     rsp, 0F8h
0x1809ec830  mov     rsi, [rcx+78h]
0x1809ec834  xor     r14d, r14d
0x1809ec837  mov     r15, rcx
0x1809ec83a  mov     [rsp+130h+pHandles], r14
0x1809ec83f  xor     edx, edx; Val
0x1809ec841  mov     [rsp+130h+var_F0], r14
0x1809ec846  lea     rcx, [rbp+57h+Parameter]; void *
0x1809ec84a  mov     [rsp+130h+var_D8], r14
0x1809ec84f  lea     r8d, [r14+78h]; Size
0x1809ec853  mov     [rbp+57h+ppStm], r14
0x1809ec857  mov     [rbp+57h+ThreadId], r14d
0x1809ec85b  call    memset_0
0x1809ec860  lea     edi, [r14+1]
0x1809ec864  lea     rcx, __vtguard
0x1809ec86b  test    rsi, rsi
0x1809ec86e  jz      short loc_1809EC88F
0x1809ec870  mov     rax, [rsi]
0x1809ec873  cmp     [rax+3D8h], rcx
0x1809ec87a  jnz     loc_1809ED02B
0x1809ec880  mov     rax, [rax+478h]
0x1809ec887  mov     rcx, rsi
0x1809ec88a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809ec88f  mov     rax, [r15+98h]
0x1809ec896  mov     r13, r14
0x1809ec899  mov     [rsp+130h+var_100], r14
0x1809ec89e  test    rax, rax
0x1809ec8a1  jz      short loc_1809EC8A6
0x1809ec8a3  mov     [rax], r14
0x1809ec8a6  lea     r12, [r15+68h]
0x1809ec8aa  mov     ebx, [r12]
0x1809ec8ae  mov     eax, ebx
0x1809ec8b0  and     eax, 90h
0x1809ec8b5  cmp     al, 90h
0x1809ec8b7  jnz     loc_1809ECA40
0x1809ec8bd  mov     [r15], r14
0x1809ec8c0  mov     rcx, cs:g_hProcessHeap
0x1809ec8c7  mov     edx, 68h ; 'h'
0x1809ec8cc  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x1809ec8d1  mov     rdi, rax
0x1809ec8d4  test    rax, rax
0x1809ec8d7  jz      loc_1809ECF21
0x1809ec8dd  mov     rdx, [r15+20h]; pvargSrc
0x1809ec8e1  lea     rax, ??_7CThreadDialogProcParam@@6B@; const CThreadDialogProcParam::`vftable'
0x1809ec8e8  mov     rbx, [r15+8]
0x1809ec8ec  lea     rcx, [rdi+10h]; pvargDest
0x1809ec8f0  mov     [rdi], rax
0x1809ec8f3  xorps   xmm0, xmm0
0x1809ec8f6  mov     dword ptr [rdi+8], 1
0x1809ec8fd  xor     eax, eax
0x1809ec8ff  movups  xmmword ptr [rcx], xmm0
0x1809ec902  mov     [rcx+10h], rax
0x1809ec906  movups  xmmword ptr [rdi+28h], xmm0
0x1809ec90a  mov     [rdi+38h], rax
0x1809ec90e  movups  xmmword ptr [rdi+48h], xmm0
0x1809ec912  mov     [rdi+58h], rax
0x1809ec916  mov     [rdi+60h], r14
0x1809ec91a  test    rdx, rdx
0x1809ec91d  jz      short loc_1809EC92B
0x1809ec91f  call    cs:__imp_VariantCopy
0x1809ec926  nop     dword ptr [rax+rax+00h]
0x1809ec92b  mov     [rdi+40h], rbx
0x1809ec92f  mov     rcx, rbx
0x1809ec932  mov     rax, [rbx]
0x1809ec935  mov     rax, [rax+8]
0x1809ec939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809ec93e  test    rsi, rsi
0x1809ec941  jz      loc_1809ECA14
0x1809ec947  cmp     [rsi+140h], r14
0x1809ec94e  jz      loc_1809ECA14
0x1809ec954  mov     rcx, cs:g_hProcessHeap
0x1809ec95b  mov     edx, 48h ; 'H'
0x1809ec960  call    ??$HeapAllocClear@$00@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAllocClear<1>(void *,unsigned __int64)
0x1809ec965  mov     rbx, rax
0x1809ec968  test    rax, rax
0x1809ec96b  jz      loc_1809ECA70
0x1809ec971  mov     rcx, [rsi+140h]
0x1809ec978  mov     [rax+18h], r14
0x1809ec97c  mov     dword ptr [rax+14h], 1
0x1809ec983  mov     [rax+20h], r14
0x1809ec987  mov     [rax+30h], r14
0x1809ec98b  lea     rax, ??_7CSecurityContextMarshal@@6BIDispatch@@@; const CSecurityContextMarshal::`vftable'{for `IDispatch'}
0x1809ec992  mov     [rbx], rax
0x1809ec995  lea     rax, ??_7CSecurityContextMarshal@@6BCSecurityContext@@@; const CSecurityContextMarshal::`vftable'{for `CSecurityContext'}
0x1809ec99c  mov     [rbx+8], rax
0x1809ec9a0  mov     [rbx+40h], rcx
0x1809ec9a4  test    rcx, rcx
0x1809ec9a7  jz      short loc_1809EC9B5
0x1809ec9a9  mov     rax, [rcx]
0x1809ec9ac  mov     rax, [rax+8]
0x1809ec9b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809ec9b5  mov     [rbx+38h], r14d
0x1809ec9b9  lea     r8, [rbp+57h+pUnk]; void **
0x1809ec9bd  lea     r14, [rbx+8]
0x1809ec9c1  mov     [rbp+57h+pUnk], r13
0x1809ec9c5  inc     dword ptr [r14+8]
0x1809ec9c9  lea     rdx, IID_IDispatch; struct _GUID *
0x1809ec9d0  mov     rcx, rbx; this
0x1809ec9d3  call    ?QueryInterface@CSecurityContextMarshal@@UEAAJAEBU_GUID@@PEAPEAX@Z; CSecurityContextMarshal::QueryInterface(_GUID const &,void * *)
0x1809ec9d8  mov     rbx, [rbp+57h+pUnk]
0x1809ec9dc  test    eax, eax
0x1809ec9de  jnz     short loc_1809EC9FA
0x1809ec9e0  lea     r8, [rbp+57h+ppStm]; ppStm
0x1809ec9e4  mov     rdx, rbx; pUnk
0x1809ec9e7  lea     rcx, IID_IDispatch; riid
0x1809ec9ee  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x1809ec9f5  nop     dword ptr [rax+rax+00h]
0x1809ec9fa  mov     rax, [rbx]
0x1809ec9fd  mov     rcx, rbx
0x1809eca00  mov     rax, [rax+10h]
0x1809eca04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809eca09  mov     rcx, r14; this
0x1809eca0c  call    ?Release@CSecurityContext@@UEAAKXZ; CSecurityContext::Release(void)
0x1809eca11  xor     r14d, r14d
0x1809eca14  xor     r9d, r9d; lpName
0x1809eca17  xor     r8d, r8d; bInitialState
0x1809eca1a  xor     edx, edx; bManualReset
0x1809eca1c  xor     ecx, ecx; lpEventAttributes
0x1809eca1e  call    cs:__imp_CreateEventW
0x1809eca25  nop     dword ptr [rax+rax+00h]
0x1809eca2a  mov     [rsp+130h+pHandles], rax
0x1809eca2f  test    rax, rax
0x1809eca32  jnz     short loc_1809ECA7A
0x1809eca34  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1809eca39  mov     ebx, eax
0x1809eca3b  jmp     loc_1809ECF33
0x1809eca40  call    ?TabWindow@IEProcessHelper@@SAPEBUIE80TabWindowExports@@XZ; IEProcessHelper::TabWindow(void)
0x1809eca45  mov     rdx, [r15]
0x1809eca48  mov     r8, r15
0x1809eca4b  shr     ebx, 9
0x1809eca4e  and     bl, dil
0x1809eca51  mov     rax, [rax]
0x1809eca54  mov     cl, bl
0x1809eca56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809eca5b  test    eax, eax
0x1809eca5d  jns     loc_1809EC8C0
0x1809eca63  mov     rdi, r14
0x1809eca66  mov     ebx, 80070005h
0x1809eca6b  jmp     loc_1809ECF33
0x1809eca70  mov     ebx, 8007000Eh
0x1809eca75  jmp     loc_1809ECF33
0x1809eca7a  mov     rdx, [r15+38h]; pvargSrc
0x1809eca7e  xor     ebx, ebx
0x1809eca80  mov     r13d, r14d
0x1809eca83  test    rdx, rdx
0x1809eca86  jz      short loc_1809ECA98
0x1809eca88  lea     rcx, [rdi+28h]; pvargDest
0x1809eca8c  call    cs:__imp_VariantCopy
0x1809eca93  nop     dword ptr [rax+rax+00h]
0x1809eca98  test    rsi, rsi
0x1809eca9b  jz      loc_1809ECC23
0x1809ecaa1  mov     [rdi+60h], rsi
0x1809ecaa5  lea     rcx, __vtguard
0x1809ecaac  mov     rax, [rsi]
0x1809ecaaf  cmp     [rax+3D8h], rcx
0x1809ecab6  jnz     loc_1809ECDAD
0x1809ecabc  mov     rax, [rax+478h]
0x1809ecac3  mov     rcx, rsi
0x1809ecac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809ecacb  mov     rcx, rsi; this
0x1809ecace  call    ?Doc@CMarkup@@QEBAPEAVCDoc@@XZ; CMarkup::Doc(void)
0x1809ecad3  mov     r14, rax
0x1809ecad6  test    rax, rax
0x1809ecad9  jz      loc_1809ECBA7
0x1809ecadf  mov     r13d, [rax+1304h]
0x1809ecae6  lea     rdx, [rbp+57h+pUnk]; struct INewWindowManager **
0x1809ecaea  shr     r13d, 7
0x1809ecaee  mov     rcx, rax; this
0x1809ecaf1  and     r13d, 1
0x1809ecaf5  mov     [rbp+57h+pUnk], rbx
0x1809ecaf9  call    ?GetPopupMgr@CDoc@@QEAAJPEAPEAUINewWindowManager@@@Z; CDoc::GetPopupMgr(INewWindowManager * *)
0x1809ecafe  test    eax, eax
0x1809ecb00  js      short loc_1809ECB1F
0x1809ecb02  mov     rcx, [rbp+57h+pUnk]; struct INewWindowManager *
0x1809ecb06  lea     rdx, [rbp+57h+var_78]; struct IStream **
0x1809ecb0a  call    ?Marshal@CNewWindowManagerStub@@SAJPEAUINewWindowManager@@PEAPEAUIStream@@@Z; CNewWindowManagerStub::Marshal(INewWindowManager *,IStream * *)
0x1809ecb0f  mov     rcx, [rbp+57h+pUnk]
0x1809ecb13  mov     rax, [rcx]
0x1809ecb16  mov     rax, [rax+10h]
0x1809ecb1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809ecb1f  test    byte ptr [r14+1308h], 2
0x1809ecb27  jz      short loc_1809ECB2F
0x1809ecb29  bts     dword ptr [r12], 1Ch
0x1809ecb2f  test    byte ptr [r14+1308h], 40h
0x1809ecb37  jz      short loc_1809ECB3F
0x1809ecb39  bts     dword ptr [r12], 1Dh
0x1809ecb3f  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1809ecb46  nop     dword ptr [rax+rax+00h]
0x1809ecb4b  test    al, al
0x1809ecb4d  jz      short loc_1809ECBA7
0x1809ecb4f  lea     rcx, [rsp+130h+var_E8]
0x1809ecb54  mov     [rsp+130h+var_E8], rbx
0x1809ecb59  call    ??I?$TSmartPointer@UID3D11Device@@@@QEAAPEAPEAUID3D11Device@@XZ; TSmartPointer<ID3D11Device>::operator&(void)
0x1809ecb5e  mov     rcx, [r14+38h]
0x1809ecb62  mov     r8, rax
0x1809ecb65  mov     rdx, [rcx]
0x1809ecb68  mov     r9, [rdx]
0x1809ecb6b  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x1809ecb72  mov     rax, r9
0x1809ecb75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809ecb7a  mov     ecx, eax; int
0x1809ecb7c  call    ?RequiredQI@Abandonment@@SAXJ@Z; Abandonment::RequiredQI(long)
0x1809ecb81  mov     rdx, [rsp+130h+var_E8]; pUnk
0x1809ecb86  lea     r8, [rbp+57h+pStm]; ppStm
0x1809ecb8a  lea     rcx, IID_IServiceProvider; riid
0x1809ecb91  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x1809ecb98  nop     dword ptr [rax+rax+00h]
0x1809ecb9d  lea     rcx, [rsp+130h+var_E8]; void *
0x1809ecba2  call    ??1?$TSmartPointer@UIWebPlatformPermanentSecurityManagerInternal@@@@QEAA@XZ; TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(void)
0x1809ecba7  mov     rax, [rsi]
0x1809ecbaa  lea     rcx, __vtguard
0x1809ecbb1  mov     [rsp+130h+pSecMgr], rbx
0x1809ecbb6  cmp     [rax+3D8h], rcx
0x1809ecbbd  jnz     loc_1809ECDAD
0x1809ecbc3  mov     rax, [rax+3F0h]
0x1809ecbca  lea     rdx, [rsp+130h+pSecMgr]
0x1809ecbcf  mov     rcx, rsi
0x1809ecbd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809ecbd7  mov     rbx, [rsp+130h+pSecMgr]
0x1809ecbdc  mov     rcx, rsi; this
0x1809ecbdf  mov     dword ptr [rbp+57h+pUnk], eax
0x1809ecbe2  call    ?Url@CMarkup@@QEAAPEAGXZ; CMarkup::Url(void)
0x1809ecbe7  mov     edx, 2; dwFlags
0x1809ecbec  mov     r9, rbx; pSecMgr
0x1809ecbef  mov     r8, rax; szURL
0x1809ecbf2  lea     ecx, [rdx+15h]; FeatureEntry
0x1809ecbf5  call    cs:__imp_CoInternetIsFeatureEnabledForUrl
0x1809ecbfc  nop     dword ptr [rax+rax+00h]
0x1809ecc01  cmp     eax, 1
0x1809ecc04  jz      short loc_1809ECC0C
0x1809ecc06  bts     dword ptr [r12], 1Fh
0x1809ecc0c  cmp     dword ptr [rbp+57h+pUnk], 0
0x1809ecc10  jl      short loc_1809ECC23
0x1809ecc12  mov     rcx, [rsp+130h+pSecMgr]
0x1809ecc17  mov     rax, [rcx]
0x1809ecc1a  mov     rax, [rax+10h]
0x1809ecc1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809ecc23  mov     rcx, [r15+20h]; struct tagVARIANT *
0x1809ecc27  mov     rdx, r12; unsigned int *
0x1809ecc2a  call    ?PropagateDialogFlags@@YAXPEAUtagVARIANT@@PEAK@Z; PropagateDialogFlags(tagVARIANT *,ulong *)
0x1809ecc2f  lea     r8, [rsp+130h+var_D8]; ppStm
0x1809ecc34  mov     rdx, rdi; pUnk
0x1809ecc37  lea     rcx, IID_IHTMLModelessInit; riid
0x1809ecc3e  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x1809ecc45  nop     dword ptr [rax+rax+00h]
0x1809ecc4a  mov     ebx, eax
0x1809ecc4c  test    eax, eax
0x1809ecc4e  jnz     loc_1809ECF2B
0x1809ecc54  mov     rax, [rsp+130h+pHandles]
0x1809ecc59  xor     ebx, ebx
0x1809ecc5b  cmp     [r15+40h], ebx
0x1809ecc5f  mov     [rbp+57h+var_B0], rax
0x1809ecc63  mov     rax, [rsp+130h+var_D8]
0x1809ecc68  mov     [rbp+57h+Parameter], rax
0x1809ecc6c  mov     rax, [rbp+57h+ppStm]
0x1809ecc70  mov     [rbp+57h+var_B8], rax
0x1809ecc74  lea     rax, [rsp+130h+var_F0]
0x1809ecc79  mov     [rbp+57h+var_A0], rax
0x1809ecc7d  mov     rax, [r15+8]
0x1809ecc81  mov     [rbp+57h+var_A8], rax
0x1809ecc85  mov     eax, [r12]
0x1809ecc89  mov     [rbp+57h+var_90], eax
0x1809ecc8c  mov     rax, [r15]
0x1809ecc8f  mov     [rbp+57h+var_88], rax
0x1809ecc93  mov     eax, ebx
0x1809ecc95  setz    al
0x1809ecc98  mov     [rbp+57h+hWnd], rbx
0x1809ecc9c  mov     [rbp+57h+var_80], eax
0x1809ecc9f  mov     eax, [rbp+57h+arg_8]
0x1809ecca2  mov     [rbp+57h+var_7C], eax
0x1809ecca5  mov     eax, [r15+0A4h]
0x1809eccac  mov     [rbp+57h+var_68], eax
0x1809eccaf  mov     eax, [r15+0A8h]
0x1809eccb6  mov     [rbp+57h+var_60], eax
0x1809eccb9  mov     eax, [r15+0ACh]
0x1809eccc0  mov     [rbp+57h+var_58], eax
0x1809eccc3  mov     rax, [r15+0B0h]
0x1809eccca  mov     [rbp+57h+var_50], rax
0x1809eccce  mov     [rbp+57h+var_64], ebx
0x1809eccd1  mov     [rbp+57h+var_5C], bl
0x1809eccd4  call    cs:__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ; IsoGetDefaultScope(void)
0x1809eccdb  nop     dword ptr [rax+rax+00h]
0x1809ecce0  test    rax, rax
0x1809ecce3  jz      short loc_1809ECD50
0x1809ecce5  call    cs:__imp_?LCIEUnifiedFrame@@YA_NXZ; LCIEUnifiedFrame(void)
0x1809eccec  nop     dword ptr [rax+rax+00h]
0x1809eccf1  test    al, al
0x1809eccf3  jz      short loc_1809ECD50
0x1809eccf5  mov     ecx, 20000002h
0x1809eccfa  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
  ... truncated ...
```
