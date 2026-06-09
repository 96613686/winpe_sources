# LCIEHandleBrokerRedirect(ushort const *,CDoc *,CMarkup *)

- ea: `0x1808cb774`
- end: `0x1808cbc51`
- name: `?LCIEHandleBrokerRedirect@@YAJPEBGPEAVCDoc@@PEAVCMarkup@@@Z`
- size: `1245`
- prototype: `__int64 __fastcall(OLECHAR *psz, struct CDoc *this, struct CMarkup *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18082cb60`

## callees

- `0x18005d080`
- `0x1803b1e00`
- `0x1807cc3bc`
- `0x1808ca524`
- `0x1808cb774`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1808cbab7`
- `KERNEL32!GetCurrentProcessId` at `0x1808cbab7`
- `KERNEL32!GetCurrentThreadId` at `0x1808cb7ab`
- `KERNEL32!GetCurrentThreadId` at `0x1808cb8c9`
- `KERNEL32!GetCurrentThreadId` at `0x1808cb7ab`
- `KERNEL32!GetCurrentThreadId` at `0x1808cb8c9`
- `KERNEL32!CreateThread` at `0x1808cb9bd`
- `KERNEL32!CreateThread` at `0x1808cb9bd`
- `KERNEL32!CloseHandle` at `0x1808cb9d1`
- `KERNEL32!CloseHandle` at `0x1808cb9d1`
- `USER32!AllowSetForegroundWindow` at `0x1808cbb50`
- `USER32!AllowSetForegroundWindow` at `0x1808cbb50`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1808cbb12`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1808cbb12`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1808cbae3`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1808cbae3`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1808cba78`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1808cba78`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1808cb9f7`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1808cba32`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1808cb9f7`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1808cba32`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1808cb95f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1808cb999`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1808cb95f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1808cb999`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1808cb85e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1808cb85e`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x1808cb7c6`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x1808cb7c6`
- `msIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x1808cb7ef`
- `msIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x1808cb81c`
- `msIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x1808cb7ef`
- `msIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x1808cb81c`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808cbaf2`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808cbbd6`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808cbaf2`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808cbbd6`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1808cbac8`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1808cbac8`
- `OLEAUT32!__imp_SysAllocString` at `0x1808cb8db`
- `OLEAUT32!__imp_SysAllocString` at `0x1808cb8db`

## pseudocode

```c
__int64 __fastcall LCIEHandleBrokerRedirect(OLECHAR *psz, struct CDoc *this, struct CMarkup *a3)
{
  DWORD CurrentThreadId; // eax
  int (__fastcall ***v6)(void *, GUID *, IUnknown **); // rax
  int UserBroker; // edi
  __int64 v8; // rax
  __int64 v9; // rbx
  BSTR v10; // rax
  unsigned int v11; // edx
  struct CDoc *CDoc; // rax
  HRESULT v13; // esi
  __int64 (__fastcall ***v14)(_QWORD, GUID *, LPUNKNOWN *); // rcx
  IStream **v15; // r14
  HANDLE Thread; // rax
  IStream *v17; // rcx
  IStream *v18; // rcx
  void *v19; // rcx
  DWORD v20; // ecx
  ULONG (__stdcall *AddRef)(IUnknown *); // rbx
  int v22; // eax
  LPUNKNOWN pUnk; // [rsp+30h] [rbp-69h] BYREF
  IUnknown *punk; // [rsp+38h] [rbp-61h] BYREF
  void *ppvOut; // [rsp+40h] [rbp-59h] BYREF
  unsigned int v27; // [rsp+48h] [rbp-51h] BYREF
  LPVOID ppv[2]; // [rsp+50h] [rbp-49h] BYREF
  struct _IsoComponent *v29; // [rsp+60h] [rbp-39h] BYREF
  int v30; // [rsp+70h] [rbp-29h] BYREF
  __int64 v31; // [rsp+74h] [rbp-25h]
  int v32; // [rsp+7Ch] [rbp-1Dh]
  __int64 v33; // [rsp+80h] [rbp-19h]
  __int128 v34; // [rsp+88h] [rbp-11h]
  _DWORD v35[10]; // [rsp+98h] [rbp-1h] BYREF

  v27 = 0;
  v29 = 0;
  CurrentThreadId = GetCurrentThreadId();
  if ( (int)LCIEGetTypedComponentFromThread(0x203u, CurrentThreadId, &v27, &v29) >= 0
    && IsoInProcessData(v29, 0x30014u, *((_DWORD *)v29 + 67), 0) )
  {
    ppvOut = 0;
    punk = 0;
    v6 = (int (__fastcall ***)(void *, GUID *, IUnknown **))IsoInProcessData(v29, 0x30014u, *((_DWORD *)v29 + 67), 0);
    if ( (**v6)(v6, &GUID_d8d2dda0_fd33_4b6a_9a67_e8c9fb471034, &punk) >= 0 )
    {
      IUnknown_QueryService(punk, &IID_IWebBrowserApp, &GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00, &ppvOut);
      ((void (__fastcall *)(IUnknown *, _QWORD, _QWORD))punk->lpVtbl[1].QueryInterface)(punk, 0, 0);
      ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
    }
    UserBroker = -2147024882;
    v8 = MemoryProtection::HeapAlloc<0>(g_hProcessHeap, 40);
    v9 = v8;
    if ( v8 )
    {
      *(_DWORD *)v8 = 0;
      *(_QWORD *)(v8 + 8) = 0;
      *(_DWORD *)(v8 + 16) = 0;
      *(_QWORD *)(v8 + 24) = 0;
      *(_QWORD *)(v8 + 32) = 0;
      *(_DWORD *)v8 = v27;
      *(_DWORD *)(v8 + 16) = GetCurrentThreadId();
      v10 = SysAllocString(psz);
      *(_DWORD *)(v9 + 4) = 0x4000;
      *(_QWORD *)(v9 + 8) = v10;
      if ( this && v10 )
      {
        CDoc = CBase::GetCDoc(this);
        UserBroker = -2147467259;
        v13 = -2147467259;
        if ( CDoc
          && (v14 = (__int64 (__fastcall ***)(_QWORD, GUID *, LPUNKNOWN *))*((_QWORD *)CDoc + 8)) != 0
          && (pUnk = 0, v13 = (**v14)(v14, &GUID_00000000_0000_0000_c000_000000000046, &pUnk), v13 >= 0)
          && (v15 = (IStream **)(v9 + 24),
              v13 = CoMarshalInterThreadInterfaceInStream(&IID_IUnknown, pUnk, (LPSTREAM *)(v9 + 24)),
              ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk),
              v13 >= 0) )
        {
          if ( ppvOut )
            CoMarshalInterThreadInterfaceInStream(&IID_IXMicTestMode, (LPUNKNOWN)ppvOut, (LPSTREAM *)(v9 + 32));
          Thread = CreateThread(0, 0, LCIEBrokerRedirectUrlThreadProc, (LPVOID)v9, 0, 0);
          if ( Thread )
          {
            CloseHandle(Thread);
            UserBroker = 0;
            goto LABEL_24;
          }
          v17 = *v15;
          ppv[0] = 0;
          if ( CoGetInterfaceAndReleaseStream(v17, &GUID_00000000_0000_0000_c000_000000000046, ppv) >= 0 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
          v18 = *(IStream **)(v9 + 32);
          *v15 = 0;
          pUnk = 0;
          if ( v18
            && CoGetInterfaceAndReleaseStream(v18, &GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00, (LPVOID *)&pUnk) >= 0 )
          {
            ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
          }
          *(_QWORD *)(v9 + 32) = 0;
        }
        else
        {
          UserBroker = v13;
        }
      }
      LCIESRedirectUrlInfo::`scalar deleting destructor'((LCIESRedirectUrlInfo *)v9, v11);
    }
LABEL_24:
    v19 = ppvOut;
    if ( ppvOut )
      goto LABEL_35;
    return (unsigned int)UserBroker;
  }
  if ( IsDualEngineProcess() )
    Abandonment::AssertionFailed();
  v30 = 0;
  memset(v35, 0, 28);
  v32 = 0;
  v31 = 2048;
  v33 = 1;
  v34 = 0;
  LODWORD(v34) = GetCurrentProcessId();
  *(_QWORD *)((char *)&v34 + 4) = IsoGetIntegrity(1) & 0x7F;
  v35[0] = IEConfiguration_GetDWORD(536870929);
  punk = 0;
  pUnk = 0;
  *(_OWORD *)&v35[3] = *(_OWORD *)GlobalThreadState();
  UserBroker = CoCreateUserBroker((struct IEUserBroker **)&pUnk);
  if ( UserBroker >= 0 )
  {
    LODWORD(ppvOut) = 0;
    ((void (__fastcall *)(LPUNKNOWN, _QWORD, _QWORD, void **))pUnk->lpVtbl[1].QueryInterface)(pUnk, 0, 0, &ppvOut);
    v20 = -1;
    if ( (_DWORD)ppvOut )
      v20 = (unsigned int)ppvOut;
    AllowSetForegroundWindow(v20);
    ppv[0] = 0;
    UserBroker = ((__int64 (__fastcall *)(LPUNKNOWN, GUID *, GUID *, LPVOID *))pUnk->lpVtbl[2].QueryInterface)(
                   pUnk,
                   &CLSID_CShdocvwBroker,
                   &IID_IUnknown,
                   ppv);
    if ( UserBroker >= 0 )
    {
      UserBroker = (**(__int64 (__fastcall ***)(LPVOID, GUID *, IUnknown **))ppv[0])(
                     ppv[0],
                     &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                     &punk);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
    }
    ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
    if ( UserBroker >= 0 )
    {
      AddRef = punk->lpVtbl[52].AddRef;
      *(_OWORD *)ppv = *(_OWORD *)GlobalThreadState();
      ((void (__fastcall *)(IUnknown *, LPVOID *))AddRef)(punk, ppv);
      v22 = ((__int64 (__fastcall *)(IUnknown *, OLECHAR *, __int64, int *, _QWORD))punk->lpVtbl[1].QueryInterface)(
              punk,
              psz,
              2048,
              &v30,
              0);
      v19 = punk;
      UserBroker = v22;
LABEL_35:
      (*(void (__fastcall **)(void *))(*(_QWORD *)v19 + 16LL))(v19);
    }
  }
  return (unsigned int)UserBroker;
}

```

## disassembly

```asm
0x1808cb774  mov     [rsp-8+arg_10], rbx
0x1808cb779  push    rbp
0x1808cb77a  push    rsi
0x1808cb77b  push    rdi
0x1808cb77c  push    r14
0x1808cb77e  push    r15
0x1808cb780  lea     rbp, [rsp-37h]
0x1808cb785  sub     rsp, 0D0h
0x1808cb78c  mov     rax, cs:__security_cookie
0x1808cb793  xor     rax, rsp
0x1808cb796  mov     [rbp+57h+var_30], rax
0x1808cb79a  xor     r15d, r15d
0x1808cb79d  mov     rsi, rdx
0x1808cb7a0  mov     [rbp+57h+var_A8], r15d
0x1808cb7a4  mov     r14, rcx
0x1808cb7a7  mov     [rbp+57h+var_90], r15
0x1808cb7ab  call    cs:__imp_GetCurrentThreadId
0x1808cb7b2  nop     dword ptr [rax+rax+00h]
0x1808cb7b7  lea     r9, [rbp+57h+var_90]
0x1808cb7bb  mov     ecx, 203h
0x1808cb7c0  mov     edx, eax
0x1808cb7c2  lea     r8, [rbp+57h+var_A8]
0x1808cb7c6  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x1808cb7cd  nop     dword ptr [rax+rax+00h]
0x1808cb7d2  test    eax, eax
0x1808cb7d4  js      loc_1808CBA78
0x1808cb7da  mov     rcx, [rbp+57h+var_90]
0x1808cb7de  mov     ebx, 30014h
0x1808cb7e3  xor     r9d, r9d
0x1808cb7e6  mov     edx, ebx
0x1808cb7e8  mov     r8d, [rcx+10Ch]
0x1808cb7ef  call    cs:__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z; IsoInProcessData(_IsoArtifact *,ulong,ulong,void *)
0x1808cb7f6  nop     dword ptr [rax+rax+00h]
0x1808cb7fb  test    rax, rax
0x1808cb7fe  jz      loc_1808CBA78
0x1808cb804  mov     rcx, [rbp+57h+var_90]
0x1808cb808  xor     r9d, r9d
0x1808cb80b  mov     [rbp+57h+ppvOut], r15
0x1808cb80f  mov     edx, ebx
0x1808cb811  mov     [rbp+57h+punk], r15
0x1808cb815  mov     r8d, [rcx+10Ch]
0x1808cb81c  call    cs:__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z; IsoInProcessData(_IsoArtifact *,ulong,ulong,void *)
0x1808cb823  nop     dword ptr [rax+rax+00h]
0x1808cb828  mov     r9, rax
0x1808cb82b  lea     r8, [rbp+57h+punk]
0x1808cb82f  lea     rdx, _GUID_d8d2dda0_fd33_4b6a_9a67_e8c9fb471034
0x1808cb836  mov     rcx, [rax]
0x1808cb839  mov     rax, [rcx]
0x1808cb83c  mov     rcx, r9
0x1808cb83f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cb844  test    eax, eax
0x1808cb846  js      short loc_1808CB88F
0x1808cb848  mov     rcx, [rbp+57h+punk]; punk
0x1808cb84c  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x1808cb850  lea     r8, _GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00; riid
0x1808cb857  lea     rdx, IID_IWebBrowserApp; guidService
0x1808cb85e  call    cs:__imp_IUnknown_QueryService
0x1808cb865  nop     dword ptr [rax+rax+00h]
0x1808cb86a  mov     rcx, [rbp+57h+punk]
0x1808cb86e  xor     r8d, r8d
0x1808cb871  xor     edx, edx
0x1808cb873  mov     rax, [rcx]
0x1808cb876  mov     rax, [rax+18h]
0x1808cb87a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cb87f  mov     rcx, [rbp+57h+punk]
0x1808cb883  mov     rax, [rcx]
0x1808cb886  mov     rax, [rax+10h]
0x1808cb88a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cb88f  mov     rcx, cs:g_hProcessHeap
0x1808cb896  mov     edx, 28h ; '('
0x1808cb89b  mov     edi, 8007000Eh
0x1808cb8a0  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x1808cb8a5  mov     rbx, rax
0x1808cb8a8  test    rax, rax
0x1808cb8ab  jz      loc_1808CBA66
0x1808cb8b1  mov     [rax], r15d
0x1808cb8b4  mov     [rax+8], r15
0x1808cb8b8  mov     [rax+10h], r15d
0x1808cb8bc  mov     [rax+18h], r15
0x1808cb8c0  mov     [rax+20h], r15
0x1808cb8c4  mov     edx, [rbp+57h+var_A8]
0x1808cb8c7  mov     [rax], edx
0x1808cb8c9  call    cs:__imp_GetCurrentThreadId
0x1808cb8d0  nop     dword ptr [rax+rax+00h]
0x1808cb8d5  mov     rcx, r14; psz
0x1808cb8d8  mov     [rbx+10h], eax
0x1808cb8db  call    cs:__imp_SysAllocString
0x1808cb8e2  nop     dword ptr [rax+rax+00h]
0x1808cb8e7  mov     dword ptr [rbx+4], 4000h
0x1808cb8ee  mov     [rbx+8], rax
0x1808cb8f2  test    rsi, rsi
0x1808cb8f5  jz      loc_1808CBA5E
0x1808cb8fb  test    rax, rax
0x1808cb8fe  jz      loc_1808CBA5E
0x1808cb904  mov     rcx, rsi; this
0x1808cb907  call    ?GetCDoc@CBase@@QEAAPEAVCDoc@@XZ; CBase::GetCDoc(void)
0x1808cb90c  mov     edi, 80004005h
0x1808cb911  mov     esi, edi
0x1808cb913  test    rax, rax
0x1808cb916  jz      loc_1808CBA58
0x1808cb91c  mov     rcx, [rax+40h]
0x1808cb920  test    rcx, rcx
0x1808cb923  jz      loc_1808CBA58
0x1808cb929  mov     [rbp+57h+pUnk], r15
0x1808cb92d  lea     r8, [rbp+57h+pUnk]
0x1808cb931  mov     rax, [rcx]
0x1808cb934  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1808cb93b  mov     rax, [rax]
0x1808cb93e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cb943  mov     esi, eax
0x1808cb945  test    eax, eax
0x1808cb947  js      loc_1808CBA58
0x1808cb94d  mov     rdx, [rbp+57h+pUnk]; pUnk
0x1808cb951  lea     r14, [rbx+18h]
0x1808cb955  mov     r8, r14; ppStm
0x1808cb958  lea     rcx, IID_IUnknown; riid
0x1808cb95f  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x1808cb966  nop     dword ptr [rax+rax+00h]
0x1808cb96b  mov     rcx, [rbp+57h+pUnk]
0x1808cb96f  mov     esi, eax
0x1808cb971  mov     rax, [rcx]
0x1808cb974  mov     rax, [rax+10h]
0x1808cb978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cb97d  test    esi, esi
0x1808cb97f  js      loc_1808CBA58
0x1808cb985  mov     rdx, [rbp+57h+ppvOut]; pUnk
0x1808cb989  test    rdx, rdx
0x1808cb98c  jz      short loc_1808CB9A5
0x1808cb98e  lea     r8, [rbx+20h]; ppStm
0x1808cb992  lea     rcx, IID_IXMicTestMode; riid
0x1808cb999  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x1808cb9a0  nop     dword ptr [rax+rax+00h]
0x1808cb9a5  mov     [rsp+0F0h+lpThreadId], r15; lpThreadId
0x1808cb9aa  lea     r8, _LCIEBrokerRedirectUrlThreadProc; lpStartAddress
0x1808cb9b1  mov     r9, rbx; lpParameter
0x1808cb9b4  mov     [rsp+0F0h+dwCreationFlags], r15d; dwCreationFlags
0x1808cb9b9  xor     edx, edx; dwStackSize
0x1808cb9bb  xor     ecx, ecx; lpThreadAttributes
0x1808cb9bd  call    cs:__imp_CreateThread
0x1808cb9c4  nop     dword ptr [rax+rax+00h]
0x1808cb9c9  test    rax, rax
0x1808cb9cc  jz      short loc_1808CB9E5
0x1808cb9ce  mov     rcx, rax; hObject
0x1808cb9d1  call    cs:__imp_CloseHandle
0x1808cb9d8  nop     dword ptr [rax+rax+00h]
0x1808cb9dd  mov     edi, r15d
0x1808cb9e0  jmp     loc_1808CBA66
0x1808cb9e5  mov     rcx, [r14]; pStm
0x1808cb9e8  lea     r8, [rbp+57h+ppv]; ppv
0x1808cb9ec  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; iid
0x1808cb9f3  mov     [rbp+57h+ppv], r15
0x1808cb9f7  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x1808cb9fe  nop     dword ptr [rax+rax+00h]
0x1808cba03  test    eax, eax
0x1808cba05  js      short loc_1808CBA17
0x1808cba07  mov     rcx, [rbp+57h+ppv]
0x1808cba0b  mov     rax, [rcx]
0x1808cba0e  mov     rax, [rax+10h]
0x1808cba12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cba17  mov     rcx, [rbx+20h]; pStm
0x1808cba1b  mov     [r14], r15
0x1808cba1e  mov     [rbp+57h+pUnk], r15
0x1808cba22  test    rcx, rcx
0x1808cba25  jz      short loc_1808CBA52
0x1808cba27  lea     r8, [rbp+57h+pUnk]; ppv
0x1808cba2b  lea     rdx, _GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00; iid
0x1808cba32  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x1808cba39  nop     dword ptr [rax+rax+00h]
0x1808cba3e  test    eax, eax
0x1808cba40  js      short loc_1808CBA52
0x1808cba42  mov     rcx, [rbp+57h+pUnk]
0x1808cba46  mov     rax, [rcx]
0x1808cba49  mov     rax, [rax+10h]
0x1808cba4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cba52  mov     [rbx+20h], r15
0x1808cba56  jmp     short loc_1808CBA5E
0x1808cba58  mov     edi, esi
0x1808cba5a  test    esi, esi
0x1808cba5c  jz      short loc_1808CBA66
0x1808cba5e  mov     rcx, rbx; this
0x1808cba61  call    ??_GLCIESRedirectUrlInfo@@QEAAPEAXI@Z; LCIESRedirectUrlInfo::`scalar deleting destructor'(uint)
0x1808cba66  mov     rcx, [rbp+57h+ppvOut]
0x1808cba6a  test    rcx, rcx
0x1808cba6d  jz      loc_1808CBC2B
0x1808cba73  jmp     loc_1808CBC1F
0x1808cba78  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1808cba7f  nop     dword ptr [rax+rax+00h]
0x1808cba84  test    al, al
0x1808cba86  jz      short loc_1808CBA8E
0x1808cba88  call    ?AssertionFailed@Abandonment@@SAXXZ; Abandonment::AssertionFailed(void)
0x1808cba8e  xorps   xmm0, xmm0
0x1808cba91  mov     [rbp+57h+var_80], r15d
0x1808cba95  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x1808cba99  mov     esi, 800h
0x1808cba9e  mov     [rbp+57h+var_74], r15d
0x1808cbaa2  mov     ebx, 1
0x1808cbaa7  mov     [rbp+57h+var_7C], rsi
0x1808cbaab  movups  xmmword ptr [rbp+57h+var_58+0Ch], xmm0
0x1808cbaaf  mov     [rbp+57h+var_70], rbx
0x1808cbab3  movups  [rbp+57h+var_68], xmm0
0x1808cbab7  call    cs:__imp_GetCurrentProcessId
0x1808cbabe  nop     dword ptr [rax+rax+00h]
0x1808cbac3  mov     ecx, ebx
0x1808cbac5  mov     dword ptr [rbp+57h+var_68], eax
0x1808cbac8  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x1808cbacf  nop     dword ptr [rax+rax+00h]
0x1808cbad4  mov     ecx, 20000011h
0x1808cbad9  mov     dword ptr [rbp+57h+var_68+8], r15d
0x1808cbadd  and     eax, 7Fh
0x1808cbae0  mov     dword ptr [rbp+57h+var_68+4], eax
0x1808cbae3  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x1808cbaea  nop     dword ptr [rax+rax+00h]
0x1808cbaef  mov     [rbp+57h+var_58], eax
0x1808cbaf2  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1808cbaf9  nop     dword ptr [rax+rax+00h]
0x1808cbafe  lea     rcx, [rbp+57h+pUnk]
0x1808cbb02  mov     [rbp+57h+punk], r15
0x1808cbb06  mov     [rbp+57h+pUnk], r15
0x1808cbb0a  movups  xmm0, xmmword ptr [rax]
0x1808cbb0d  movdqu  xmmword ptr [rbp+57h+var_58+0Ch], xmm0
0x1808cbb12  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1808cbb19  nop     dword ptr [rax+rax+00h]
0x1808cbb1e  mov     edi, eax
0x1808cbb20  test    eax, eax
0x1808cbb22  js      loc_1808CBC2B
0x1808cbb28  mov     rcx, [rbp+57h+pUnk]
0x1808cbb2c  lea     r9, [rbp+57h+ppvOut]
0x1808cbb30  mov     dword ptr [rbp+57h+ppvOut], r15d
0x1808cbb34  xor     r8d, r8d
0x1808cbb37  xor     edx, edx
0x1808cbb39  mov     rax, [rcx]
0x1808cbb3c  mov     rax, [rax+18h]
0x1808cbb40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cbb45  mov     eax, dword ptr [rbp+57h+ppvOut]
0x1808cbb48  or      ecx, 0FFFFFFFFh
0x1808cbb4b  test    eax, eax
0x1808cbb4d  cmovnz  ecx, eax; dwProcessId
0x1808cbb50  call    cs:__imp_AllowSetForegroundWindow
0x1808cbb57  nop     dword ptr [rax+rax+00h]
0x1808cbb5c  mov     rcx, [rbp+57h+pUnk]
0x1808cbb60  lea     r9, [rbp+57h+ppv]
0x1808cbb64  mov     [rbp+57h+ppv], r15
0x1808cbb68  lea     r8, IID_IUnknown
0x1808cbb6f  lea     rdx, CLSID_CShdocvwBroker
0x1808cbb76  mov     rax, [rcx]
0x1808cbb79  mov     rax, [rax+30h]
0x1808cbb7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cbb82  mov     edi, eax
0x1808cbb84  test    eax, eax
0x1808cbb86  js      short loc_1808CBBB4
0x1808cbb88  mov     rcx, [rbp+57h+ppv]
0x1808cbb8c  lea     r8, [rbp+57h+punk]
0x1808cbb90  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x1808cbb97  mov     rax, [rcx]
0x1808cbb9a  mov     rax, [rax]
0x1808cbb9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cbba2  mov     rcx, [rbp+57h+ppv]
0x1808cbba6  mov     edi, eax
0x1808cbba8  mov     rax, [rcx]
0x1808cbbab  mov     rax, [rax+10h]
0x1808cbbaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cbbb4  mov     rcx, [rbp+57h+pUnk]
0x1808cbbb8  mov     rax, [rcx]
0x1808cbbbb  mov     rax, [rax+10h]
0x1808cbbbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cbbc4  test    edi, edi
0x1808cbbc6  js      short loc_1808CBC2B
0x1808cbbc8  mov     rax, [rbp+57h+punk]
0x1808cbbcc  mov     rcx, [rax]
0x1808cbbcf  mov     rbx, [rcx+4E8h]
0x1808cbbd6  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1808cbbdd  nop     dword ptr [rax+rax+00h]
0x1808cbbe2  mov     rcx, [rbp+57h+punk]
0x1808cbbe6  lea     rdx, [rbp+57h+ppv]
0x1808cbbea  movups  xmm0, xmmword ptr [rax]
0x1808cbbed  mov     rax, rbx
0x1808cbbf0  movdqu  xmmword ptr [rbp+57h+ppv], xmm0
0x1808cbbf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cbbfa  mov     rcx, [rbp+57h+punk]
0x1808cbbfe  lea     r9, [rbp+57h+var_80]
0x1808cbc02  mov     r8d, esi
0x1808cbc05  mov     qword ptr [rsp+0F0h+dwCreationFlags], r15
0x1808cbc0a  mov     rdx, r14
0x1808cbc0d  mov     rax, [rcx]
0x1808cbc10  mov     rax, [rax+18h]
0x1808cbc14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cbc19  mov     rcx, [rbp+57h+punk]
0x1808cbc1d  mov     edi, eax
0x1808cbc1f  mov     rax, [rcx]
0x1808cbc22  mov     rax, [rax+10h]
0x1808cbc26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cbc2b  mov     eax, edi
0x1808cbc2d  mov     rcx, [rbp+57h+var_30]
0x1808cbc31  xor     rcx, rsp; StackCookie
0x1808cbc34  call    __security_check_cookie
0x1808cbc39  mov     rbx, [rsp+0F0h+arg_10]
0x1808cbc41  add     rsp, 0D0h
0x1808cbc48  pop     r15
0x1808cbc4a  pop     r14
0x1808cbc4c  pop     rdi
  ... truncated ...
```
