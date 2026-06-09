# CCbsPackage::EnumerateUpdatesUsingSessionsXML(CCbsSession *,_CbsApplicability,_CbsSelectability,CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong> *,wchar_t * *,long *)

- ea: `0x1801b54c0`
- end: `0x1801b5b27`
- name: `?EnumerateUpdatesUsingSessionsXML@CCbsPackage@@AEAAJPEAVCCbsSession@@W4_CbsApplicability@@W4_CbsSelectability@@PEAV?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@PEAPEA_WPEAJ@Z`
- size: `1639`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801a6c00`

## callees

- `0x18000d910`
- `0x180010cc0`
- `0x180023f30`
- `0x18002c34c`
- `0x180068404`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800a2d68`
- `0x1800ad504`
- `0x1800eb920`
- `0x1801a5494`
- `0x1801a8b68`
- `0x1801aa788`
- `0x1801b54c0`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b594c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b596b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b59ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b5a83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b5b12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b594c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b596b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b59ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b5a83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b5b12`

## string_xrefs

- `0x1801b56ef`: `Enumeration failed due to CBS package store corruption, hence falling back to Sessions.xml for update enumeration`
- `0x1801b5a24`: `Failed getting update CbsUpdatePropertyName property`
- `0x1801b5ab3`: `Failed getting update CbsUpdatePropertyName property`
- `0x1801b5741`: `Failed to process Sessions.xml`

## pseudocode

```c
__int64 __fastcall CCbsPackage::EnumerateUpdatesUsingSessionsXML(
        int a1,
        struct CCbsSession *a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  unsigned int v9; // ebx
  int v10; // edx
  __int64 v11; // rdx
  int v13; // edx
  int v14; // edx
  int v15; // edx
  int v16; // edi
  char *v17; // rcx
  char IsEnabled; // al
  _QWORD *v19; // rbx
  int v20; // eax
  int v21; // edx
  __int64 v22; // rdx
  int v23; // edx
  unsigned __int64 v24; // r14
  __int64 v25; // rsi
  __int64 (__fastcall *v26)(__int64, __int64, __int64); // rdi
  __int64 InitPointer; // rax
  unsigned __int64 v28; // rax
  unsigned __int64 v29; // r15
  __int64 v30; // rsi
  __int64 (__fastcall *v31)(__int64, __int64, __int64); // rdi
  __int64 v32; // rax
  int v33; // eax
  char *v34; // rcx
  int v35; // edx
  unsigned __int64 v36; // r9
  __int64 v37; // rdx
  int v38; // edx
  int v39; // [rsp+20h] [rbp-C1h]
  int v40[2]; // [rsp+70h] [rbp-71h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-69h] BYREF
  LPVOID v42; // [rsp+80h] [rbp-61h] BYREF
  int v43; // [rsp+88h] [rbp-59h] BYREF
  _BYTE v44[64]; // [rsp+90h] [rbp-51h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+47h]

  LODWORD(v42) = a4;
  v43 = a3;
  if ( !a2 )
  {
    v9 = -2147024809;
    LODWORD(v42) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No session specified");
      pv = &v42;
      LOBYTE(v10) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v10,
        3,
        (unsigned int)": {}",
        (__int64)&pv);
    }
    v11 = 28;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackageinventory.cpp",
      (const char *)v9,
      v39);
    return v9;
  }
  if ( !a5 )
  {
    v9 = -2147467261;
    LODWORD(v42) = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid Enumeration pointer passed in");
      pv = &v42;
      LOBYTE(v13) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v13,
        3,
        (unsigned int)": {}",
        (__int64)&pv);
    }
    v11 = 29;
    goto LABEL_5;
  }
  if ( !a6 )
  {
    v9 = -2147467261;
    LODWORD(v42) = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid file name pointer passed in");
      pv = &v42;
      LOBYTE(v14) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v14,
        3,
        (unsigned int)": {}",
        (__int64)&pv);
    }
    v11 = 30;
    goto LABEL_5;
  }
  if ( !a7 )
  {
    v9 = -2147467261;
    LODWORD(v42) = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid hresult pointer passed in");
      pv = &v42;
      LOBYTE(v15) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v15,
        3,
        (unsigned int)": {}",
        (__int64)&pv);
    }
    v11 = 31;
    goto LABEL_5;
  }
  CCbsInterfaceArray<CCbsPackage *>::CCbsInterfaceArray<CCbsPackage *>(v44);
  pv = 0;
  if ( Windows::AutoComPtr<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>>::AllocateWithNew<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>,>(&pv) )
  {
    LogAdapter::TraceAtLevel<>(
      1,
      "Enumeration failed due to CBS package store corruption, hence falling back to Sessions.xml for update enumeration");
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FodLPEnumHardeningErrorHandlingFixes>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_FodLPEnumHardeningErrorHandlingFixes>::GetImpl'::`2'::impl);
    v19 = pv;
    if ( IsEnabled )
    {
      v20 = CCbsSession::ProcessSessionsXML(a2);
      v16 = v20;
      if ( v20 < 0 )
      {
        LODWORD(v42) = v20;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to process Sessions.xml");
          pv = &v42;
          LOBYTE(v21) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v21,
            3,
            (unsigned int)": {}",
            (__int64)&pv);
        }
        v22 = 46;
        goto LABEL_26;
      }
    }
    else
    {
      CCbsSession::ProcessSessionsXML(a2);
    }
    v16 = CCbsPackage::InternalEnumerateUpdate(
            a1,
            (_DWORD)a2,
            (unsigned int)v44,
            v43,
            (_DWORD)v42,
            0,
            0,
            1,
            a5,
            1,
            0,
            a6,
            a7);
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FodLPEnumHardeningErrorHandlingFixes>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_FodLPEnumHardeningErrorHandlingFixes>::GetImpl'::`2'::impl)
      || v16 >= 0 )
    {
      v24 = 0;
      if ( !v19[6] )
      {
LABEL_57:
        v34 = (char *)v19 + *(int *)(v19[1] + 4LL) + 8;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v34 + 16LL))(v34);
        v16 = 0;
        goto LABEL_58;
      }
      while ( 1 )
      {
        v42 = 0;
        if ( v24 >= v19[6] )
          __fastfail(8u);
        v25 = *(_QWORD *)(v19[8] + 8 * v24);
        v26 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v25 + 24LL);
        InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v42);
        v16 = v26(v25, 1, InitPointer);
        if ( v16 < 0 )
        {
          v43 = v16;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              LogAdapter::g_Logger,
              0,
              3,
              "Failed getting update CbsUpdatePropertyName property");
            *(_QWORD *)v40 = &v43;
            LOBYTE(v38) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v38,
              3,
              (unsigned int)": {}",
              (__int64)v40);
          }
          v36 = (unsigned int)v16;
          v37 = 78;
          goto LABEL_67;
        }
        v28 = *(_QWORD *)(a5 + 48);
        v29 = 0;
        if ( v28 )
          break;
LABEL_50:
        if ( v29 == *(_QWORD *)(a5 + 48) )
        {
          if ( v24 >= v19[6] )
            __fastfail(8u);
          v33 = CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>::Add(a5, *(_QWORD *)(v19[8] + 8 * v24));
          v16 = v33;
          if ( v33 < 0 )
          {
            v36 = (unsigned int)v33;
            v37 = 95;
LABEL_67:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v37,
              (unsigned int)"onecore\\base\\cbs\\core\\cbspackageinventory.cpp",
              (const char *)v36,
              v39);
            goto LABEL_68;
          }
        }
        if ( v42 )
          CoTaskMemFree(v42);
        if ( ++v24 >= v19[6] )
          goto LABEL_57;
      }
      while ( 1 )
      {
        pv = 0;
        if ( v29 >= v28 )
          __fastfail(8u);
        v30 = *(_QWORD *)(*(_QWORD *)(a5 + 64) + 8 * v29);
        v31 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v30 + 24LL);
        v32 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&pv);
        v16 = v31(v30, 1, v32);
        if ( v16 < 0 )
          break;
        if ( (unsigned __int8)StringsAreEqual(v42, pv, 1) )
        {
          if ( pv )
            CoTaskMemFree(pv);
          goto LABEL_50;
        }
        if ( pv )
          CoTaskMemFree(pv);
        v28 = *(_QWORD *)(a5 + 48);
        if ( ++v29 >= v28 )
          goto LABEL_50;
      }
      v43 = v16;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed getting update CbsUpdatePropertyName property");
        *(_QWORD *)v40 = &v43;
        LOBYTE(v35) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v35,
          3,
          (unsigned int)": {}",
          (__int64)v40);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x55,
        (unsigned int)"onecore\\base\\cbs\\core\\cbspackageinventory.cpp",
        (const char *)(unsigned int)v16,
        v39);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
LABEL_68:
      if ( v42 )
      {
        CoTaskMemFree(v42);
        v42 = 0;
      }
      goto LABEL_27;
    }
    v43 = v16;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to Enumerate using parsed session.");
      pv = &v43;
      LOBYTE(v23) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v23,
        3,
        (unsigned int)": {}",
        (__int64)&pv);
    }
    v22 = 71;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackageinventory.cpp",
      (const char *)(unsigned int)v16,
      v39);
    if ( !v19 )
      goto LABEL_58;
LABEL_27:
    v17 = (char *)v19 + *(int *)(v19[1] + 4LL) + 8;
    goto LABEL_28;
  }
  v16 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x25,
    (unsigned int)"onecore\\base\\cbs\\core\\cbspackageinventory.cpp",
    (const char *)0x8007000ELL,
    v39);
  if ( pv )
  {
    v17 = (char *)pv + *(int *)(*((_QWORD *)pv + 1) + 4LL) + 8;
LABEL_28:
    (*(void (__fastcall **)(char *))(*(_QWORD *)v17 + 16LL))(v17);
  }
LABEL_58:
  CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v44);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1801b54c0  push    rbp
0x1801b54c2  push    rbx
0x1801b54c3  push    rsi
0x1801b54c4  push    rdi
0x1801b54c5  push    r12
0x1801b54c7  push    r13
0x1801b54c9  push    r14
0x1801b54cb  push    r15
0x1801b54cd  lea     rbp, [rsp-7]
0x1801b54d2  sub     rsp, 0E8h
0x1801b54d9  mov     rax, cs:__security_cookie
0x1801b54e0  xor     rax, rsp
0x1801b54e3  mov     [rbp+3Fh+var_50], rax
0x1801b54e7  mov     r13, [rbp+3Fh+arg_20]
0x1801b54eb  mov     rsi, rdx
0x1801b54ee  mov     r14, [rbp+3Fh+arg_28]
0x1801b54f2  mov     r12, rcx
0x1801b54f5  mov     r15, [rbp+3Fh+arg_30]
0x1801b54f9  mov     dword ptr [rbp+3Fh+var_A0], r9d
0x1801b54fd  mov     [rbp+3Fh+var_98], r8d
0x1801b5501  test    rdx, rdx
0x1801b5504  jnz     short loc_1801B5574
0x1801b5506  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b550d  mov     ebx, 80070057h
0x1801b5512  mov     dword ptr [rbp+3Fh+var_A0], ebx
0x1801b5515  test    rcx, rcx
0x1801b5518  jz      short loc_1801B5555
0x1801b551a  lea     esi, [rdx+3]
0x1801b551d  mov     r8d, esi
0x1801b5520  lea     r9, aNoSessionSpeci_0; "No session specified"
0x1801b5527  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801b552c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b5533  lea     rax, [rbp+3Fh+var_A0]
0x1801b5537  mov     [rbp+3Fh+pv], rax
0x1801b553b  lea     r9, asc_1802EE7AC; ": {}"
0x1801b5542  lea     rax, [rbp+3Fh+pv]
0x1801b5546  mov     r8d, esi
0x1801b5549  mov     dl, 1
0x1801b554b  mov     qword ptr [rsp+120h+var_100], rax; int
0x1801b5550  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801b5555  mov     edx, 1Ch; void *
0x1801b555a  mov     rcx, [rbp+47h]; this
0x1801b555e  lea     r8, aOnecoreBaseCbs_75; "onecore\\base\\cbs\\core\\cbspackageinv"...
0x1801b5565  mov     r9d, ebx; char *
0x1801b5568  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b556d  mov     eax, ebx
0x1801b556f  jmp     loc_1801B59EF
0x1801b5574  test    r13, r13
0x1801b5577  jnz     short loc_1801B55D2
0x1801b5579  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b5580  mov     ebx, 80004003h
0x1801b5585  mov     dword ptr [rbp+3Fh+var_A0], ebx
0x1801b5588  test    rcx, rcx
0x1801b558b  jz      short loc_1801B55CB
0x1801b558d  lea     esi, [r13+3]
0x1801b5591  xor     edx, edx
0x1801b5593  mov     r8d, esi
0x1801b5596  lea     r9, aInvalidEnumera; "Invalid Enumeration pointer passed in"
0x1801b559d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801b55a2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b55a9  lea     rax, [rbp+3Fh+var_A0]
0x1801b55ad  mov     [rbp+3Fh+pv], rax
0x1801b55b1  lea     r9, asc_1802EE7AC; ": {}"
0x1801b55b8  lea     rax, [rbp+3Fh+pv]
0x1801b55bc  mov     r8d, esi
0x1801b55bf  mov     dl, 1
0x1801b55c1  mov     qword ptr [rsp+120h+var_100], rax
0x1801b55c6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801b55cb  mov     edx, 1Dh
0x1801b55d0  jmp     short loc_1801B555A
0x1801b55d2  test    r14, r14
0x1801b55d5  jnz     short loc_1801B5633
0x1801b55d7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b55de  mov     ebx, 80004003h
0x1801b55e3  mov     dword ptr [rbp+3Fh+var_A0], ebx
0x1801b55e6  test    rcx, rcx
0x1801b55e9  jz      short loc_1801B5629
0x1801b55eb  lea     esi, [r14+3]
0x1801b55ef  xor     edx, edx
0x1801b55f1  mov     r8d, esi
0x1801b55f4  lea     r9, aInvalidFileNam; "Invalid file name pointer passed in"
0x1801b55fb  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801b5600  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b5607  lea     rax, [rbp+3Fh+var_A0]
0x1801b560b  mov     [rbp+3Fh+pv], rax
0x1801b560f  lea     r9, asc_1802EE7AC; ": {}"
0x1801b5616  lea     rax, [rbp+3Fh+pv]
0x1801b561a  mov     r8d, esi
0x1801b561d  mov     dl, 1
0x1801b561f  mov     qword ptr [rsp+120h+var_100], rax
0x1801b5624  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801b5629  mov     edx, 1Eh
0x1801b562e  jmp     loc_1801B555A
0x1801b5633  test    r15, r15
0x1801b5636  jnz     short loc_1801B5694
0x1801b5638  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b563f  mov     ebx, 80004003h
0x1801b5644  mov     dword ptr [rbp+3Fh+var_A0], ebx
0x1801b5647  test    rcx, rcx
0x1801b564a  jz      short loc_1801B568A
0x1801b564c  lea     esi, [r15+3]
0x1801b5650  xor     edx, edx
0x1801b5652  mov     r8d, esi
0x1801b5655  lea     r9, aInvalidHresult; "Invalid hresult pointer passed in"
0x1801b565c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801b5661  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b5668  lea     rax, [rbp+3Fh+var_A0]
0x1801b566c  mov     [rbp+3Fh+pv], rax
0x1801b5670  lea     r9, asc_1802EE7AC; ": {}"
0x1801b5677  lea     rax, [rbp+3Fh+pv]
0x1801b567b  mov     r8d, esi
0x1801b567e  mov     dl, 1
0x1801b5680  mov     qword ptr [rsp+120h+var_100], rax
0x1801b5685  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801b568a  mov     edx, 1Fh
0x1801b568f  jmp     loc_1801B555A
0x1801b5694  lea     rcx, [rbp+3Fh+var_90]
0x1801b5698  call    ??0?$CCbsInterfaceArray@PEAVCCbsPackage@@@@QEAA@XZ; CCbsInterfaceArray<CCbsPackage *>::CCbsInterfaceArray<CCbsPackage *>(void)
0x1801b569d  lea     rcx, [rbp+3Fh+pv]
0x1801b56a1  mov     [rbp+3Fh+pv], 0
0x1801b56a9  call    ??$AllocateWithNew@V?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@$$V@?$AutoComPtr@V?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@@Windows@@QEAAPEAV?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@XZ; Windows::AutoComPtr<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong>>::AllocateWithNew<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong>,>(void)
0x1801b56ae  test    rax, rax
0x1801b56b1  jnz     short loc_1801B56EF
0x1801b56b3  mov     rcx, [rbp+47h]; this
0x1801b56b7  lea     r8, aOnecoreBaseCbs_75; "onecore\\base\\cbs\\core\\cbspackageinv"...
0x1801b56be  mov     edi, 8007000Eh
0x1801b56c3  lea     edx, [rax+25h]; void *
0x1801b56c6  mov     r9d, edi; char *
0x1801b56c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b56ce  mov     rax, [rbp+3Fh+pv]
0x1801b56d2  test    rax, rax
0x1801b56d5  jz      loc_1801B59E4
0x1801b56db  mov     rcx, [rax+8]
0x1801b56df  add     rax, 8
0x1801b56e3  movsxd  rcx, dword ptr [rcx+4]
0x1801b56e7  add     rcx, rax
0x1801b56ea  jmp     loc_1801B57AB
0x1801b56ef  lea     rdx, aEnumerationFai_0; "Enumeration failed due to CBS package s"...
0x1801b56f6  mov     ecx, 1
0x1801b56fb  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1801b5700  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_FodLPEnumHardeningErrorHandlingFixes@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FodLPEnumHardeningErrorHandlingFixes@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FodLPEnumHardeningErrorHandlingFixes> `wil::Feature<__WilFeatureTraits_Feature_Servicing_FodLPEnumHardeningErrorHandlingFixes>::GetImpl(void)'::`2'::impl
0x1801b5707  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FodLPEnumHardeningErrorHandlingFixes@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FodLPEnumHardeningErrorHandlingFixes>::__private_IsEnabled(void)
0x1801b570c  mov     rbx, [rbp+3Fh+pv]
0x1801b5710  mov     rcx, rsi; struct CCbsSession *
0x1801b5713  mov     rdx, rbx
0x1801b5716  test    al, al
0x1801b5718  jz      loc_1801B57BC
0x1801b571e  call    ?ProcessSessionsXML@CCbsSession@@QEAAJPEAV?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@@Z; CCbsSession::ProcessSessionsXML(CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong> *)
0x1801b5723  mov     edi, eax
0x1801b5725  test    eax, eax
0x1801b5727  jns     loc_1801B57C1
0x1801b572d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b5734  mov     dword ptr [rbp+3Fh+var_A0], eax
0x1801b5737  test    rcx, rcx
0x1801b573a  jz      short loc_1801B577B
0x1801b573c  mov     esi, 3
0x1801b5741  lea     r9, aFailedToProces_13; "Failed to process Sessions.xml"
0x1801b5748  mov     r8d, esi
0x1801b574b  xor     edx, edx
0x1801b574d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801b5752  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b5759  lea     rax, [rbp+3Fh+var_A0]
0x1801b575d  mov     [rbp+3Fh+pv], rax
0x1801b5761  lea     r9, asc_1802EE7AC; ": {}"
0x1801b5768  lea     rax, [rbp+3Fh+pv]
0x1801b576c  mov     r8d, esi
0x1801b576f  mov     dl, 1
0x1801b5771  mov     qword ptr [rsp+120h+var_100], rax; int
0x1801b5776  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801b577b  mov     edx, 2Eh ; '.'; void *
0x1801b5780  mov     rcx, [rbp+47h]; this
0x1801b5784  lea     r8, aOnecoreBaseCbs_75; "onecore\\base\\cbs\\core\\cbspackageinv"...
0x1801b578b  mov     r9d, edi; char *
0x1801b578e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b5793  test    rbx, rbx
0x1801b5796  jz      loc_1801B59E4
0x1801b579c  mov     rax, [rbx+8]
0x1801b57a0  movsxd  rcx, dword ptr [rax+4]
0x1801b57a4  add     rcx, 8
0x1801b57a8  add     rcx, rbx
0x1801b57ab  mov     rax, [rcx]
0x1801b57ae  mov     rax, [rax+10h]
0x1801b57b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b57b7  jmp     loc_1801B59E4
0x1801b57bc  call    ?ProcessSessionsXML@CCbsSession@@QEAAJPEAV?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@@Z; CCbsSession::ProcessSessionsXML(CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong> *)
0x1801b57c1  mov     eax, dword ptr [rbp+3Fh+var_A0]
0x1801b57c4  lea     r8, [rbp+3Fh+var_90]
0x1801b57c8  mov     r9d, [rbp+3Fh+var_98]
0x1801b57cc  mov     rdx, rsi
0x1801b57cf  mov     [rsp+120h+var_C0], r15
0x1801b57d4  mov     rcx, r12
0x1801b57d7  mov     [rsp+120h+var_C8], r14
0x1801b57dc  mov     [rsp+120h+var_D0], 0
0x1801b57e4  mov     [rsp+120h+var_D8], 1
0x1801b57ec  mov     [rsp+120h+var_E0], r13
0x1801b57f1  mov     [rsp+120h+var_E8], 1
0x1801b57f9  mov     [rsp+120h+var_F0], 0
0x1801b5802  mov     [rsp+120h+var_F8], 0
0x1801b580a  mov     [rsp+120h+var_100], eax
0x1801b580e  call    ?InternalEnumerateUpdate@CCbsPackage@@AEAAJPEAVCCbsSession@@PEAV?$CCbsInterfaceArray@PEAVCCbsPackage@@@@W4_CbsApplicability@@W4_CbsSelectability@@HPEB_WHPEAV?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@HHPEAPEA_WPEAJ@Z; CCbsPackage::InternalEnumerateUpdate(CCbsSession *,CCbsInterfaceArray<CCbsPackage *> *,_CbsApplicability,_CbsSelectability,int,wchar_t const *,int,CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong> *,int,int,wchar_t * *,long *)
0x1801b5813  mov     edi, eax
0x1801b5815  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_FodLPEnumHardeningErrorHandlingFixes@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FodLPEnumHardeningErrorHandlingFixes@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FodLPEnumHardeningErrorHandlingFixes> `wil::Feature<__WilFeatureTraits_Feature_Servicing_FodLPEnumHardeningErrorHandlingFixes>::GetImpl(void)'::`2'::impl
0x1801b581c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FodLPEnumHardeningErrorHandlingFixes@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FodLPEnumHardeningErrorHandlingFixes>::__private_IsEnabled(void)
0x1801b5821  xor     r12d, r12d
0x1801b5824  test    al, al
0x1801b5826  jz      short loc_1801B5884
0x1801b5828  test    edi, edi
0x1801b582a  jns     short loc_1801B5884
0x1801b582c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b5833  mov     [rbp+3Fh+var_98], edi
0x1801b5836  test    rcx, rcx
0x1801b5839  jz      short loc_1801B587A
0x1801b583b  lea     esi, [r12+3]
0x1801b5840  xor     edx, edx
0x1801b5842  mov     r8d, esi
0x1801b5845  lea     r9, aFailedToEnumer_3; "Failed to Enumerate using parsed sessio"...
0x1801b584c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801b5851  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b5858  lea     rax, [rbp+3Fh+var_98]
0x1801b585c  mov     [rbp+3Fh+pv], rax
0x1801b5860  lea     r9, asc_1802EE7AC; ": {}"
0x1801b5867  lea     rax, [rbp+3Fh+pv]
0x1801b586b  mov     r8d, esi
0x1801b586e  mov     dl, 1
0x1801b5870  mov     qword ptr [rsp+120h+var_100], rax
0x1801b5875  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801b587a  mov     edx, 47h ; 'G'
0x1801b587f  jmp     loc_1801B5780
0x1801b5884  mov     r14, r12
0x1801b5887  cmp     [rbx+30h], r12
0x1801b588b  jbe     loc_1801B59C6
0x1801b5891  mov     [rbp+3Fh+var_A0], r12
0x1801b5895  cmp     r14, [rbx+30h]
0x1801b5899  jb      short loc_1801B58A2
0x1801b589b  mov     ecx, 8
0x1801b58a0  int     29h; Win8: RtlFailFast(ecx)
0x1801b58a2  mov     rax, [rbx+40h]
0x1801b58a6  lea     rcx, [rbp+3Fh+var_A0]
0x1801b58aa  mov     rsi, [rax+r14*8]
0x1801b58ae  mov     rax, [rsi]
0x1801b58b1  mov     rdi, [rax+18h]
0x1801b58b5  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801b58ba  mov     r8, rax
0x1801b58bd  mov     edx, 1
0x1801b58c2  mov     rax, rdi
0x1801b58c5  mov     rcx, rsi
0x1801b58c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b58cd  mov     edi, eax
0x1801b58cf  test    eax, eax
0x1801b58d1  js      loc_1801B5A9F
0x1801b58d7  mov     rax, [r13+30h]
0x1801b58db  mov     r15, r12
0x1801b58de  test    rax, rax
0x1801b58e1  jz      loc_1801B5977
0x1801b58e7  mov     [rbp+3Fh+pv], r12
0x1801b58eb  cmp     r15, rax
0x1801b58ee  jb      short loc_1801B58F7
0x1801b58f0  mov     ecx, 8
0x1801b58f5  int     29h; Win8: RtlFailFast(ecx)
0x1801b58f7  mov     rax, [r13+40h]
0x1801b58fb  lea     rcx, [rbp+3Fh+pv]
0x1801b58ff  mov     rsi, [rax+r15*8]
0x1801b5903  mov     rax, [rsi]
0x1801b5906  mov     rdi, [rax+18h]
0x1801b590a  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801b590f  mov     r8, rax
0x1801b5912  mov     edx, 1
0x1801b5917  mov     rax, rdi
0x1801b591a  mov     rcx, rsi
0x1801b591d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5922  mov     edi, eax
0x1801b5924  test    eax, eax
0x1801b5926  js      loc_1801B5A10
0x1801b592c  mov     rdx, [rbp+3Fh+pv]
0x1801b5930  mov     r8d, 1
0x1801b5936  mov     rcx, [rbp+3Fh+var_A0]
0x1801b593a  call    StringsAreEqual
0x1801b593f  mov     rcx, [rbp+3Fh+pv]; pv
0x1801b5943  test    al, al
0x1801b5945  jnz     short loc_1801B5966
0x1801b5947  test    rcx, rcx
0x1801b594a  jz      short loc_1801B5958
0x1801b594c  call    cs:__imp_CoTaskMemFree
0x1801b5953  nop     dword ptr [rax+rax+00h]
0x1801b5958  mov     rax, [r13+30h]
0x1801b595c  inc     r15
0x1801b595f  cmp     r15, rax
0x1801b5962  jb      short loc_1801B58E7
0x1801b5964  jmp     short loc_1801B5977
0x1801b5966  test    rcx, rcx
0x1801b5969  jz      short loc_1801B5977
0x1801b596b  call    cs:__imp_CoTaskMemFree
0x1801b5972  nop     dword ptr [rax+rax+00h]
0x1801b5977  cmp     r15, [r13+30h]
0x1801b597b  jnz     short loc_1801B59A4
0x1801b597d  cmp     r14, [rbx+30h]
0x1801b5981  jb      short loc_1801B598A
0x1801b5983  mov     ecx, 8
0x1801b5988  int     29h; Win8: RtlFailFast(ecx)
0x1801b598a  mov     rdx, [rbx+40h]
  ... truncated ...
```
