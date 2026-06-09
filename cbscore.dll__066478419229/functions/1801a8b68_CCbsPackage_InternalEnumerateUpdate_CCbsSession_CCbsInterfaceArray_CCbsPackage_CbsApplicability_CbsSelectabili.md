# CCbsPackage::InternalEnumerateUpdate(CCbsSession *,CCbsInterfaceArray<CCbsPackage *> *,_CbsApplicability,_CbsSelectability,int,wchar_t const *,int,CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong> *,int,int,wchar_t * *,long *)

- ea: `0x1801a8b68`
- end: `0x1801a9cd0`
- name: `?InternalEnumerateUpdate@CCbsPackage@@AEAAJPEAVCCbsSession@@PEAV?$CCbsInterfaceArray@PEAVCCbsPackage@@@@W4_CbsApplicability@@W4_CbsSelectability@@HPEB_WHPEAV?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@HHPEAPEA_WPEAJ@Z`
- size: `4456`
- prototype: ``
- caller_count: `6`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18006c6e0`
- `0x1801a6c00`
- `0x1801a80b0`
- `0x1801a8b68`
- `0x1801b54c0`
- `0x1801b5b5c`

## callees

- `0x18000c62c`
- `0x180010b60`
- `0x180010cc0`
- `0x1800138b8`
- `0x18001d7f8`
- `0x18001de20`
- `0x1800217d8`
- `0x180023750`
- `0x18002573c`
- `0x1800261e0`
- `0x18002a78c`
- `0x18002ac84`
- `0x18002b118`
- `0x1800345f0`
- `0x180051a7c`
- `0x1800658b8`
- `0x180068404`
- `0x180068b50`
- `0x180069710`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x180099f0c`
- `0x18009cf78`
- `0x1800a36d4`
- `0x1800a5934`
- `0x1800a6554`
- `0x1800a8678`
- `0x1800b980c`
- `0x1800eb920`
- `0x180129bdc`
- `0x1801a8b68`
- `0x1802d5010`

## string_xrefs

- `0x1801a8c31`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a8dae`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a8ede`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a8fa3`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a92f5`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a934f`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a9402`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a9465`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a96a8`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a9702`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a9941`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a99ef`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a9acb`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a9b70`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a9c1a`: `onecore\base\cbs\core\cbspackageupdates.cpp`
- `0x1801a9194`: `Unable to get selectability for Update: {}, skipping...`
- `0x1801a9098`: `Unable to get applicability for Update: {}, skipping...`
- `0x1801a9901`: `Failed to enumerate updates from child package`
- `0x1801a99af`: `Failed to open child package`
- `0x1801a93c2`: `Failed to create an instance of the update for public use.`
- `0x1801a92b5`: `Failed to retrieve the latest state for the update from Sessions.xml`

## pseudocode

```c
__int64 __fastcall CCbsPackage::InternalEnumerateUpdate(
        __int64 a1,
        struct CCbsSession *a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        wchar_t *a7,
        int a8,
        __int64 a9,
        int a10,
        int a11,
        __int64 a12,
        __int64 a13)
{
  int UpdateStateFromSessionsXML; // edi
  int v17; // edx
  __int64 v18; // rdx
  int v19; // edx
  int v20; // edx
  int SessionPackageState; // eax
  const wchar_t *v22; // r14
  int v23; // edx
  unsigned __int64 i; // rbx
  __int64 v25; // rcx
  unsigned __int64 j; // rbx
  __int64 v27; // rcx
  int v28; // eax
  int v29; // edx
  unsigned __int64 k; // rbx
  __int64 v31; // rcx
  int IsDelegated; // eax
  int v33; // edx
  unsigned __int64 m; // rbx
  __int64 v35; // rcx
  __int64 *v36; // r15
  __int64 *v37; // r12
  wchar_t *v38; // rax
  __int64 v39; // rbx
  CCbsSession *v40; // rdi
  int Applicability; // eax
  const char *v42; // r8
  const wchar_t *v43; // rcx
  unsigned __int64 v44; // rbx
  int v45; // eax
  __int64 v46; // rcx
  struct CCbsPackage *v47; // rdi
  unsigned __int64 mm; // rbx
  const wchar_t *v49; // r8
  const wchar_t *v50; // rdx
  struct CCbsPublicUpdate **InitPointer; // rax
  __int64 v52; // rdx
  int v53; // eax
  unsigned __int64 kk; // rbx
  __int64 v55; // rcx
  int v56; // edx
  unsigned __int64 n; // rbx
  __int64 v58; // rcx
  unsigned __int64 jj; // rbx
  __int64 v60; // rcx
  int v61; // edx
  unsigned __int64 ii; // rbx
  __int64 v63; // rcx
  unsigned __int64 i7; // rbx
  __int64 v65; // rcx
  int v66; // eax
  int v67; // r14d
  __int64 v68; // rcx
  unsigned __int64 v69; // r8
  unsigned __int64 v70; // r14
  __int64 v71; // r15
  struct ICbsIdentity *v72; // rdx
  struct CCbsSession *v73; // r12
  struct CCbsIdentity *v74; // r8
  __int64 v75; // rdi
  wchar_t *FastCbsIdentityString; // rax
  unsigned int v77; // eax
  int v78; // edx
  unsigned __int64 i4; // rbx
  __int64 v80; // rcx
  unsigned __int64 nn; // rbx
  __int64 v82; // rcx
  struct CCbsPackage **v83; // rax
  bool v84; // cl
  int v85; // edx
  unsigned __int64 i6; // rbx
  __int64 v87; // rcx
  int v88; // edx
  unsigned __int64 i5; // rbx
  __int64 v90; // rcx
  int v91; // edx
  unsigned __int64 i3; // rbx
  __int64 v93; // rcx
  int v94; // edx
  unsigned __int64 i2; // rbx
  __int64 v96; // rcx
  int v97; // edx
  unsigned __int64 i1; // rbx
  __int64 v99; // rcx
  unsigned __int64 v100; // rbx
  __int64 v101; // rcx
  int v103; // [rsp+20h] [rbp-E0h]
  int v104; // [rsp+20h] [rbp-E0h]
  int v105[2]; // [rsp+70h] [rbp-90h] BYREF
  int v106[2]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *v107; // [rsp+80h] [rbp-80h]
  __int64 v108; // [rsp+88h] [rbp-78h] BYREF
  int v109[2]; // [rsp+90h] [rbp-70h] BYREF
  struct CCbsSession *v110; // [rsp+98h] [rbp-68h]
  __int64 v111; // [rsp+A0h] [rbp-60h]
  _BYTE v112[24]; // [rsp+A8h] [rbp-58h] BYREF
  int v113; // [rsp+C0h] [rbp-40h] BYREF
  int v114; // [rsp+C4h] [rbp-3Ch] BYREF
  const wchar_t *v115; // [rsp+C8h] [rbp-38h] BYREF
  int v116; // [rsp+D0h] [rbp-30h] BYREF
  struct CCbsPackage *v117; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v118[24]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v119; // [rsp+F8h] [rbp-8h]
  __int64 v120; // [rsp+108h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  *(_QWORD *)v109 = a12;
  v107 = a7;
  v111 = a13;
  v116 = a4;
  *(_QWORD *)v106 = a3;
  v110 = a2;
  *(_QWORD *)v105 = a9;
  if ( !a2 )
  {
    UpdateStateFromSessionsXML = -2147024809;
    v113 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No session specified");
      *(_QWORD *)v105 = &v113;
      LOBYTE(v17) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v17,
        3,
        (unsigned int)": {}",
        (__int64)v105);
    }
    v18 = 585;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
      (const char *)0x80070057LL,
      v103);
    return (unsigned int)UpdateStateFromSessionsXML;
  }
  if ( !a3 )
  {
    UpdateStateFromSessionsXML = -2147024809;
    v113 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No visited packages specified");
      *(_QWORD *)v105 = &v113;
      LOBYTE(v19) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v19,
        3,
        (unsigned int)": {}",
        (__int64)v105);
    }
    v18 = 586;
    goto LABEL_5;
  }
  if ( !a9 )
  {
    UpdateStateFromSessionsXML = -2147024809;
    v113 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No enumeration object specified");
      *(_QWORD *)v105 = &v113;
      LOBYTE(v20) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v20,
        3,
        (unsigned int)": {}",
        (__int64)v105);
    }
    v18 = 587;
    goto LABEL_5;
  }
  CCbsArray<_DRIVER_UPDATE>::CCbsArray<_DRIVER_UPDATE>(v118);
  v114 = 0;
  v117 = 0;
  SessionPackageState = CCbsSession::GetSessionPackageState(a2, (struct CCbsPackage *)a1, &v117, 0);
  UpdateStateFromSessionsXML = SessionPackageState;
  if ( SessionPackageState < 0 )
  {
    v113 = SessionPackageState;
    if ( LogAdapter::g_Logger )
    {
      v22 = &qword_1802EB518;
      if ( *(_QWORD *)(a1 + 120) )
        v22 = *(const wchar_t **)(a1 + 120);
      *(_QWORD *)v105 = v22;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to get per-session package state for package: {}",
        (__int64)v105);
      *(_QWORD *)v109 = &v113;
      LOBYTE(v23) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v23,
        3,
        (unsigned int)": {}",
        (__int64)v109);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25B,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
      (const char *)(unsigned int)UpdateStateFromSessionsXML,
      v103);
    if ( v119 )
    {
      for ( i = 0; i < v119; ++i )
      {
        v25 = *(_QWORD *)(*(_QWORD *)(v120 + 8 * i) + 8LL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      }
    }
    goto LABEL_196;
  }
  v115 = (const wchar_t *)a1;
  v108 = 0xFFFFFFFFLL;
  if ( CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::FastFind(a3, &v115, &v108) != 0xFFFFFFFFLL )
  {
    if ( v119 )
    {
      for ( j = 0; j < v119; ++j )
      {
        v27 = *(_QWORD *)(*(_QWORD *)(v120 + 8 * j) + 8LL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      }
    }
    goto LABEL_195;
  }
  v115 = (const wchar_t *)a1;
  v28 = CCbsInterfaceArray<CCbsPackage *>::InsertAt(a3, &v115, v108);
  UpdateStateFromSessionsXML = v28;
  if ( v28 < 0 )
  {
    v113 = v28;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to add package to the visited list");
      *(_QWORD *)v105 = &v113;
      LOBYTE(v29) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v29,
        3,
        (unsigned int)": {}",
        (__int64)v105);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x268,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
      (const char *)(unsigned int)UpdateStateFromSessionsXML,
      v103);
    if ( v119 )
    {
      for ( k = 0; k < v119; ++k )
      {
        v31 = *(_QWORD *)(*(_QWORD *)(v120 + 8 * k) + 8LL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      }
    }
    goto LABEL_196;
  }
  IsDelegated = CCbsPackage::IsDelegated((CCbsPackage *)a1, a2, &v114);
  UpdateStateFromSessionsXML = IsDelegated;
  if ( IsDelegated < 0 )
  {
    v113 = IsDelegated;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get delegate state.");
      *(_QWORD *)v105 = &v113;
      LOBYTE(v33) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v33,
        3,
        (unsigned int)": {}",
        (__int64)v105);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26F,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
      (const char *)(unsigned int)UpdateStateFromSessionsXML,
      v103);
    if ( v119 )
    {
      for ( m = 0; m < v119; ++m )
      {
        v35 = *(_QWORD *)(*(_QWORD *)(v120 + 8 * m) + 8LL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      }
    }
    goto LABEL_196;
  }
  if ( v114 && !a6 )
    goto LABEL_191;
  v36 = *(__int64 **)(a1 + 752);
  v37 = &v36[*(_QWORD *)(a1 + 736)];
  if ( v36 != v37 )
  {
    v38 = v107;
    do
    {
      v39 = *v36;
      v114 = 1;
      LODWORD(v115) = 4096;
      v113 = 1;
      if ( v38 && !(unsigned int)CCbsUpdate::MatchNameCaseInsensitive((CCbsUpdate *)v39, v38) )
        goto LABEL_55;
      v40 = v110;
      if ( v116 && v116 != 7 )
      {
        Applicability = CCbsUpdate::GetApplicability(
                          (CCbsUpdate *)v39,
                          v110,
                          (enum _CbsApplicability *)&v114,
                          (enum CbsState *)&v115);
        if ( Applicability < 0 )
        {
          v42 = "Unable to get applicability for Update: {}, skipping...";
LABEL_52:
          v43 = &qword_1802EB518;
          if ( *(_QWORD *)(v39 + 32) )
            v43 = *(const wchar_t **)(v39 + 32);
          v115 = v43;
          LogAdapter::TraceAtLevelHr<long,wchar_t const *>(1, (unsigned int)Applicability, v42, &v115);
LABEL_55:
          v38 = v107;
          goto LABEL_56;
        }
        if ( (v116 & v114) == 0 )
          goto LABEL_55;
      }
      if ( a5 && a5 != 31 )
      {
        Applicability = CCbsUpdate::GetSelectability((CCbsUpdate *)v39, (enum _CbsSelectability *)&v113);
        if ( Applicability < 0 )
        {
          v42 = "Unable to get selectability for Update: {}, skipping...";
          goto LABEL_52;
        }
        if ( (a5 & v113) == 0 )
          goto LABEL_55;
      }
      if ( a10 && !a11 )
      {
        v49 = &qword_1802EB518;
        v50 = &qword_1802EB518;
        if ( *(_QWORD *)(v39 + 32) )
          v49 = *(const wchar_t **)(v39 + 32);
        if ( *(_QWORD *)(a1 + 120) )
          v50 = *(const wchar_t **)(a1 + 120);
        UpdateStateFromSessionsXML = CCbsSession::GetUpdateStateFromSessionsXML(
                                       v40,
                                       v50,
                                       v49,
                                       (enum CbsState *)(v39 + 440));
        if ( UpdateStateFromSessionsXML < 0 )
        {
          LODWORD(v115) = UpdateStateFromSessionsXML;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              LogAdapter::g_Logger,
              0,
              3,
              "Failed to retrieve the latest state for the update from Sessions.xml");
            *(_QWORD *)v105 = &v115;
            LOBYTE(v56) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v56,
              3,
              (unsigned int)": {}",
              (__int64)v105);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2AC,
            (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
            (const char *)(unsigned int)UpdateStateFromSessionsXML,
            v103);
          if ( v119 )
          {
            for ( n = 0; n < v119; ++n )
            {
              v58 = *(_QWORD *)(*(_QWORD *)(v120 + 8 * n) + 8LL);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
            }
          }
          goto LABEL_196;
        }
      }
      v108 = 0;
      InitPointer = (struct CCbsPublicUpdate **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v108);
      UpdateStateFromSessionsXML = CCbsUpdate::CreatePublicInstance((CCbsUpdate *)v39, v110, InitPointer);
      if ( UpdateStateFromSessionsXML < 0 )
      {
        LODWORD(v115) = UpdateStateFromSessionsXML;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to create an instance of the update for public use.");
          *(_QWORD *)v105 = &v115;
          LOBYTE(v61) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v61,
            3,
            (unsigned int)": {}",
            (__int64)v105);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B6,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
          (const char *)(unsigned int)UpdateStateFromSessionsXML,
          v103);
        Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v108);
        if ( v119 )
        {
          for ( ii = 0; ii < v119; ++ii )
          {
            v63 = *(_QWORD *)(*(_QWORD *)(v120 + 8 * ii) + 8LL);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
          }
        }
        goto LABEL_196;
      }
      v52 = v108;
      if ( v108 )
        v52 = *(int *)(*(_QWORD *)(v108 + 8) + 4LL) + v108 + 8;
      v53 = CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>::Add(*(_QWORD *)v105, v52);
      UpdateStateFromSessionsXML = v53;
      if ( v53 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B8,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
          (const char *)(unsigned int)v53,
          v103);
        Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v108);
        if ( v119 )
        {
          for ( jj = 0; jj < v119; ++jj )
          {
            v60 = *(_QWORD *)(*(_QWORD *)(v120 + 8 * jj) + 8LL);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
          }
        }
        goto LABEL_196;
      }
      Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v108);
      v38 = v107;
      if ( v107 )
      {
        if ( v119 )
        {
          for ( kk = 0; kk < v119; ++kk )
          {
            v55 = *(_QWORD *)(*(_QWORD *)(v120 + 8 * kk) + 8LL);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
          }
        }
        goto LABEL_195;
      }
LABEL_56:
      ++v36;
    }
    while ( v36 != v37 );
  }
  if ( !a8 )
  {
LABEL_191:
    v69 = v119;
LABEL_192:
    if ( v69 )
    {
      v100 = 0;
      do
      {
        v101 = *(_QWORD *)(*(_QWORD *)(v120 + 8 * v100) + 8LL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
        ++v100;
      }
      while ( v100 < v119 );
    }
    goto LABEL_195;
  }
  CritSecLocker::CritSecLocker((CritSecLocker *)v112, (struct AutoCritSec *)(a1 + 1064), 1);
  if ( !*(_QWORD *)(a1 + 1208) )
  {
LABEL_64:
    v47 = v117;
    for ( mm = 0; mm < *((_QWORD *)v47 + 19); ++mm )
    {
      v66 = CCbsArrayBase<CCbsTask *,CCbsPointerArray<CCbsTask *>>::Add(v118, *((_QWORD *)v47 + 21) + 8 * mm);
      v67 = v66;
      if ( v66 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2D8,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
          (const char *)(unsigned int)v66,
          v103);
        CritSecLocker::~CritSecLocker((CritSecLocker *)v112);
        if ( v119 )
        {
          for ( nn = 0; nn < v119; ++nn )
          {
            v82 = *(_QWORD *)(*(_QWORD *)(v120 + 8 * nn) + 8LL);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
          }
        }
        UpdateStateFromSessionsXML = v67;
        goto LABEL_196;
      }
      if ( mm >= *((_QWORD *)v47 + 19) )
        __fastfail(8u);
      v68 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v47 + 21) + 8 * mm) + 8LL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 8LL))(v68);
    }
    CritSecLocker::~CritSecLocker((CritSecLocker *)v112);
    v69 = v119;
    v70 = 0;
    if ( !v119 )
    {
LABEL_195:
      UpdateStateFromSessionsXML = 0;
      goto LABEL_196;
    }
    while ( 1 )
    {
      v71 = *(_QWORD *)(v120 + 8 * v70);
      if ( *(int *)v71 >= 3 )
        break;
LABEL_157:
      if ( ++v70 >= v69 )
        goto LABEL_192;
    }
    v72 = *(struct ICbsIdentity **)(v71 + 8);
    if ( !v72 )
    {
      UpdateStateFromSessionsXML = -2146498560;
      v114 = -2146498560;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Child package has no identity");
        *(_QWORD *)v106 = &v114;
        LOBYTE(v97) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v97,
          3,
          (unsigned int)": {}",
          (__int64)v106);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E9,
        (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
        (const char *)0x800F0800LL,
        v103);
      if ( v119 )
      {
        for ( i1 = 0; i1 < v119; ++i1 )
        {
          v99 = *(_QWORD *)(*(_QWORD *)(v120 + 8 * i1) + 8LL);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
        }
      }
      goto LABEL_196;
    }
    v114 = 0;
    v113 = 0;
    if ( v70 >= v69 )
      __fastfail(8u);
    v73 = v110;
    UpdateStateFromSessionsXML = CCbsSession::QueryPackageIntendedState(v110, v72, 0, 0, (enum CbsState *)&v114);
    if ( UpdateStateFromSessionsXML < 0 )
    {
      v116 = UpdateStateFromSessionsXML;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to query store state");
        *(_QWORD *)v106 = &v116;
        LOBYTE(v94) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v94,
          3,
          (unsigned int)": {}",
          (__int64)v106);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F6,
        (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
        (const char *)(unsigned int)UpdateStateFromSessionsXML,
        v103);
      if ( v119 )
      {
        for ( i2 = 0; i2 < v119; ++i2 )
        {
          v96 = *(_QWORD *)(*(_QWORD *)(v120 + 8 * i2) + 8LL);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
        }
      }
      goto LABEL_196;
    }
    if ( v114 < 96 )
    {
      if ( v114 == 80 )
        goto LABEL_156;
      if ( v70 >= v119 )
        __fastfail(8u);
      UpdateStateFromSessionsXML = IsPackageActive(
                                     v73,
                                     *(struct CCbsIdentity **)(*(_QWORD *)(v120 + 8 * v70) + 8LL),
                                     &v113);
      if ( UpdateStateFromSessionsXML < 0 )
      {
        v113 = UpdateStateFromSessionsXML;
        if ( LogAdapter::g_Logger )
        {
          if ( v70 >= v119 )
            __fastfail(8u);
          *(_QWORD *)v106 = GetFastCbsIdentityString(*(const struct CCbsIdentity **)(*(_QWORD *)(v120 + 8 * v70) + 8LL));
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to check whether the package is active: {}",
            (__int64)v106);
          *(_QWORD *)v109 = &v113;
          LOBYTE(v91) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v91,
            3,
            (unsigned int)": {}",
            (__int64)v109);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x33D,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
          (const char *)(unsigned int)UpdateStateFromSessionsXML,
          v103);
        if ( v119 )
        {
          for ( i3 = 0; i3 < v119; ++i3 )
          {
            v93 = *(_QWORD *)(*(_QWORD *)(v120 + 8 * i3) + 8LL);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
          }
        }
        goto LABEL_196;
      }
      if ( !v113 )
        goto LABEL_156;
      goto LABEL_151;
    }
    if ( *(_DWORD *)(v71 + 16) == -1 )
    {
      v74 = *(struct CCbsIdentity **)(v71 + 8);
      v113 = 0;
      UpdateStateFromSessionsXML = CCbsPackage::IsChild((CCbsPackage *)a1, v73, v74, &v113);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FodLPEnumHardeningEnhancements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FodLPEnumHardeningEnhancements>::GetImpl'::`2'::impl) )
      {
        if ( UpdateStateFromSessionsXML < 0 )
        {
          if ( a10 )
          {
            if ( v111 )
              *(_DWORD *)v111 = UpdateStateFromSessionsXML;
            v75 = *(_QWORD *)v109;
            if ( *(_QWORD *)v109 )
            {
              FastCbsIdentityString = GetFastCbsIdentityString(*(const struct CCbsIdentity **)(v71 + 8));
              v77 = SczAllocFormatted(v75, L"%ws.mum", FastCbsIdentityString);
              LogAdapter::TraceAtLevelIfFailed<long,>(1, v77, "Unable to allocate string");
            }
            UpdateStateFromSessionsXML = 0;
          }
          if ( UpdateStateFromSessionsXML < 0 )
          {
LABEL_129:
            LODWORD(v115) = UpdateStateFromSessionsXML;
            if ( LogAdapter::g_Logger )
            {
              *(_QWORD *)v106 = GetFastCbsIdentityString(*(const struct CCbsIdentity **)(v71 + 8));
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to check whether this is the real child: {}",
                (__int64)v106);
              *(_QWORD *)v105 = &v115;
              LOBYTE(v78) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v78,
                3,
                (unsigned int)": {}",
                (__int64)v105);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x321,
              (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
              (const char *)(unsigned int)UpdateStateFromSessionsXML,
              v103);
            if ( v119 )
            {
              for ( i4 = 0; i4 < v119; ++i4 )
              {
                v80 = *(_QWORD *)(*(_QWORD *)(v120 + 8 * i4) + 8LL);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
              }
            }
            goto LABEL_196;
          }
        }
      }
      else if ( UpdateStateFromSessionsXML < 0 && !a10 )
      {
        goto LABEL_129;
      }
      if ( v113 )
      {
        *(_DWORD *)(v71 + 16) = 1;
LABEL_151:
        v117 = 0;
        v83 = (struct CCbsPackage **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v117);
        if ( v70 >= v119 )
          __fastfail(8u);
        UpdateStateFromSessionsXML = CCbsSession::ResolvePackage(
                                       v73,
                                       0,
                                       0,
                                       0,
                                       *(struct ICbsIdentity **)(*(_QWORD *)(v120 + 8 * v70) + 8LL),
                                       1,
                                       v83,
                                       0);
        if ( UpdateStateFromSessionsXML < 0 )
        {
          LODWORD(v115) = UpdateStateFromSessionsXML;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to open child package");
            *(_QWORD *)v106 = &v115;
            LOBYTE(v88) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v88,
              3,
              (unsigned int)": {}",
              (__int64)v106);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x34F,
            (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
            (const char *)(unsigned int)UpdateStateFromSessionsXML,
            v104);
          Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v117);
          if ( v119 )
          {
            for ( i5 = 0; i5 < v119; ++i5 )
            {
              v90 = *(_QWORD *)(*(_QWORD *)(v120 + 8 * i5) + 8LL);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
            }
          }
          goto LABEL_196;
        }
        v84 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FodLPEnumHardeningEnhancements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FodLPEnumHardeningEnhancements>::GetImpl'::`2'::impl) != 0;
        UpdateStateFromSessionsXML = CCbsPackage::InternalEnumerateUpdate(
                                       (_DWORD)v117,
                                       (_DWORD)v73,
                                       v106[0],
                                       v116,
                                       a5,
                                       1,
                                       (__int64)v107,
                                       1,
                                       *(__int64 *)v105,
                                       a10,
                                       a11 & (unsigned int)-v84,
                                       *(_QWORD *)v109 & -(__int64)v84,
                                       v111 & -(__int64)v84);
        if ( UpdateStateFromSessionsXML < 0 )
        {
          LODWORD(v115) = UpdateStateFromSessionsXML;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              LogAdapter::g_Logger,
              0,
              3,
              "Failed to enumerate updates from child package");
            *(_QWORD *)v106 = &v115;
            LOBYTE(v85) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v85,
              3,
              (unsigned int)": {}",
              (__int64)v106);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x371,
            (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
            (const char *)(unsigned int)UpdateStateFromSessionsXML,
            v103);
          Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v117);
          if ( v119 )
          {
            for ( i6 = 0; i6 < v119; ++i6 )
            {
              v87 = *(_QWORD *)(*(_QWORD *)(v120 + 8 * i6) + 8LL);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
            }
          }
          goto LABEL_196;
        }
        Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v117);
        goto LABEL_156;
      }
      *(_DWORD *)(v71 + 16) = 0;
    }
    else if ( *(_DWORD *)(v71 + 16) == 1 )
    {
      goto LABEL_151;
    }
LABEL_156:
    v69 = v119;
    goto LABEL_157;
  }
  v44 = 0;
  while ( 1 )
  {
    v45 = CCbsArrayBase<CCbsTask *,CCbsPointerArray<CCbsTask *>>::Add(v118, *(_QWORD *)(a1 + 1224) + 8 * v44);
    UpdateStateFromSessionsXML = v45;
    if ( v45 < 0 )
      break;
    if ( v44 >= *(_QWORD *)(a1 + 1208) )
      __fastfail(8u);
    v46 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 1224) + 8 * v44) + 8LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 8LL))(v46);
    if ( ++v44 >= *(_QWORD *)(a1 + 1208) )
      goto LABEL_64;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2D0,
    (unsigned int)"onecore\\base\\cbs\\core\\cbspackageupdates.cpp",
    (const char *)(unsigned int)v45,
    v103);
  CritSecLocker::~CritSecLocker((CritSecLocker *)v112);
  if ( v119 )
  {
    for ( i7 = 0; i7 < v119; ++i7 )
    {
      v65 = *(_QWORD *)(*(_QWORD *)(v120 + 8 * i7) + 8LL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    }
  }
LABEL_196:
  CCbsArrayBase<CCbsUpdate *,CCbsArray<CCbsUpdate *>>::~CCbsArrayBase<CCbsUpdate *,CCbsArray<CCbsUpdate *>>(v118);
  return (unsigned int)UpdateStateFromSessionsXML;
}

```

## disassembly

```asm
0x1801a8b68  push    rbp
0x1801a8b6a  push    rbx
0x1801a8b6b  push    rsi
0x1801a8b6c  push    rdi
0x1801a8b6d  push    r12
0x1801a8b6f  push    r13
0x1801a8b71  push    r14
0x1801a8b73  push    r15
0x1801a8b75  lea     rbp, [rsp-38h]
0x1801a8b7a  sub     rsp, 138h
0x1801a8b81  mov     rax, cs:__security_cookie
0x1801a8b88  xor     rax, rsp
0x1801a8b8b  mov     [rbp+70h+var_50], rax
0x1801a8b8f  mov     rax, [rbp+70h+arg_58]
0x1801a8b96  mov     r13, rcx
0x1801a8b99  mov     rcx, [rbp+70h+arg_40]
0x1801a8ba0  mov     rsi, r8
0x1801a8ba3  mov     qword ptr [rbp+70h+var_E0], rax
0x1801a8ba7  mov     rbx, rdx
0x1801a8baa  mov     rax, [rbp+70h+arg_30]
0x1801a8bb1  mov     [rbp+70h+var_F0], rax
0x1801a8bb5  mov     rax, [rbp+70h+arg_60]
0x1801a8bbc  mov     [rbp+70h+var_D0], rax
0x1801a8bc0  mov     [rbp+70h+var_A0], r9d
0x1801a8bc4  mov     qword ptr [rsp+170h+var_F8], r8
0x1801a8bc9  mov     [rbp+70h+var_D8], rdx
0x1801a8bcd  mov     qword ptr [rsp+170h+var_100], rcx
0x1801a8bd2  test    rdx, rdx
0x1801a8bd5  jnz     short loc_1801A8C45
0x1801a8bd7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8bde  mov     edi, 80070057h
0x1801a8be3  mov     [rbp+70h+var_B0], edi
0x1801a8be6  test    rcx, rcx
0x1801a8be9  jz      short loc_1801A8C28
0x1801a8beb  lea     ebx, [rdx+3]
0x1801a8bee  mov     r8d, ebx
0x1801a8bf1  lea     r9, aNoSessionSpeci_0; "No session specified"
0x1801a8bf8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801a8bfd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8c04  lea     rax, [rbp+70h+var_B0]
0x1801a8c08  mov     qword ptr [rsp+170h+var_100], rax
0x1801a8c0d  lea     r9, asc_1802EE7AC; ": {}"
0x1801a8c14  lea     rax, [rsp+170h+var_100]
0x1801a8c19  mov     r8d, ebx
0x1801a8c1c  mov     dl, 1
0x1801a8c1e  mov     [rsp+170h+var_150], rax; int
0x1801a8c23  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801a8c28  mov     edx, 249h; void *
0x1801a8c2d  mov     rcx, [rbp+78h]; this
0x1801a8c31  lea     r8, aOnecoreBaseCbs_146; "onecore\\base\\cbs\\core\\cbspackageupd"...
0x1801a8c38  mov     r9d, edi; char *
0x1801a8c3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a8c40  jmp     loc_1801A9CAD
0x1801a8c45  test    rsi, rsi
0x1801a8c48  jnz     short loc_1801A8CA4
0x1801a8c4a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8c51  mov     edi, 80070057h
0x1801a8c56  mov     [rbp+70h+var_B0], edi
0x1801a8c59  test    rcx, rcx
0x1801a8c5c  jz      short loc_1801A8C9D
0x1801a8c5e  lea     ebx, [rsi+3]
0x1801a8c61  xor     edx, edx
0x1801a8c63  mov     r8d, ebx
0x1801a8c66  lea     r9, aNoVisitedPacka; "No visited packages specified"
0x1801a8c6d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801a8c72  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8c79  lea     rax, [rbp+70h+var_B0]
0x1801a8c7d  mov     qword ptr [rsp+170h+var_100], rax
0x1801a8c82  lea     r9, asc_1802EE7AC; ": {}"
0x1801a8c89  lea     rax, [rsp+170h+var_100]
0x1801a8c8e  mov     r8d, ebx
0x1801a8c91  mov     dl, 1
0x1801a8c93  mov     [rsp+170h+var_150], rax
0x1801a8c98  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801a8c9d  mov     edx, 24Ah
0x1801a8ca2  jmp     short loc_1801A8C2D
0x1801a8ca4  test    rcx, rcx
0x1801a8ca7  jnz     short loc_1801A8D08
0x1801a8ca9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8cb0  mov     edi, 80070057h
0x1801a8cb5  mov     [rbp+70h+var_B0], edi
0x1801a8cb8  test    rcx, rcx
0x1801a8cbb  jz      short loc_1801A8CFE
0x1801a8cbd  mov     ebx, 3
0x1801a8cc2  lea     r9, aNoEnumerationO; "No enumeration object specified"
0x1801a8cc9  mov     r8d, ebx
0x1801a8ccc  xor     edx, edx
0x1801a8cce  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801a8cd3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8cda  lea     rax, [rbp+70h+var_B0]
0x1801a8cde  mov     qword ptr [rsp+170h+var_100], rax
0x1801a8ce3  lea     r9, asc_1802EE7AC; ": {}"
0x1801a8cea  lea     rax, [rsp+170h+var_100]
0x1801a8cef  mov     r8d, ebx
0x1801a8cf2  mov     dl, 1
0x1801a8cf4  mov     [rsp+170h+var_150], rax
0x1801a8cf9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801a8cfe  mov     edx, 24Bh
0x1801a8d03  jmp     loc_1801A8C2D
0x1801a8d08  lea     rcx, [rbp+70h+var_90]
0x1801a8d0c  call    ??0?$CCbsArray@U_DRIVER_UPDATE@@@@QEAA@XZ; CCbsArray<_DRIVER_UPDATE>::CCbsArray<_DRIVER_UPDATE>(void)
0x1801a8d11  xor     r9d, r9d; unsigned __int64 *
0x1801a8d14  mov     [rbp+70h+var_AC], 0
0x1801a8d1b  lea     r8, [rbp+70h+var_98]; struct PerSessionPackageState **
0x1801a8d1f  mov     [rbp+70h+var_98], 0
0x1801a8d27  mov     rdx, r13; struct CCbsPackage *
0x1801a8d2a  mov     rcx, rbx; this
0x1801a8d2d  call    ?GetSessionPackageState@CCbsSession@@QEAAJPEAVCCbsPackage@@PEAPEAUPerSessionPackageState@@PEA_K@Z; CCbsSession::GetSessionPackageState(CCbsPackage *,PerSessionPackageState * *,unsigned __int64 *)
0x1801a8d32  mov     edi, eax
0x1801a8d34  test    eax, eax
0x1801a8d36  jns     loc_1801A8E06
0x1801a8d3c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8d43  mov     [rbp+70h+var_B0], eax
0x1801a8d46  test    rcx, rcx
0x1801a8d49  jz      short loc_1801A8DAA
0x1801a8d4b  cmp     qword ptr [r13+78h], 0
0x1801a8d50  lea     rax, [rsp+170h+var_100]
0x1801a8d55  lea     r14, qword_1802EB518
0x1801a8d5c  mov     [rsp+170h+var_150], rax
0x1801a8d61  cmovnz  r14, [r13+78h]
0x1801a8d66  lea     r9, aFailedToGetPer_1; "Failed to get per-session package state"...
0x1801a8d6d  mov     ebx, 3
0x1801a8d72  mov     qword ptr [rsp+170h+var_100], r14
0x1801a8d77  xor     edx, edx
0x1801a8d79  mov     r8d, ebx
0x1801a8d7c  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1801a8d81  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8d88  lea     rax, [rbp+70h+var_B0]
0x1801a8d8c  mov     qword ptr [rbp+70h+var_E0], rax
0x1801a8d90  lea     r9, asc_1802EE7AC; ": {}"
0x1801a8d97  lea     rax, [rbp+70h+var_E0]
0x1801a8d9b  mov     r8d, ebx
0x1801a8d9e  mov     dl, 1
0x1801a8da0  mov     [rsp+170h+var_150], rax; int
0x1801a8da5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801a8daa  mov     rcx, [rbp+78h]; this
0x1801a8dae  lea     r8, aOnecoreBaseCbs_146; "onecore\\base\\cbs\\core\\cbspackageupd"...
0x1801a8db5  mov     r9d, edi; char *
0x1801a8db8  mov     edx, 25Bh; void *
0x1801a8dbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a8dc2  mov     rax, [rbp+70h+var_78]
0x1801a8dc6  test    rax, rax
0x1801a8dc9  jz      loc_1801A9CA4
0x1801a8dcf  xor     ebx, ebx
0x1801a8dd1  lea     esi, [rbx+8]
0x1801a8dd4  cmp     rbx, rax
0x1801a8dd7  jb      short loc_1801A8DDD
0x1801a8dd9  mov     ecx, esi
0x1801a8ddb  int     29h; Win8: RtlFailFast(ecx)
0x1801a8ddd  mov     rax, [rbp+70h+var_68]
0x1801a8de1  mov     rcx, [rax+rbx*8]
0x1801a8de5  mov     rcx, [rcx+8]
0x1801a8de9  mov     rax, [rcx]
0x1801a8dec  mov     rax, [rax+10h]
0x1801a8df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8df5  mov     rax, [rbp+70h+var_78]
0x1801a8df9  inc     rbx
0x1801a8dfc  cmp     rbx, rax
0x1801a8dff  jb      short loc_1801A8DDD
0x1801a8e01  jmp     loc_1801A9CA4
0x1801a8e06  mov     edi, 0FFFFFFFFh
0x1801a8e0b  mov     [rbp+70h+var_A8], r13
0x1801a8e0f  lea     r8, [rbp+70h+var_E8]
0x1801a8e13  mov     [rbp+70h+var_E8], rdi
0x1801a8e17  lea     rdx, [rbp+70h+var_A8]
0x1801a8e1b  mov     rcx, rsi
0x1801a8e1e  call    ?FastFind@?$CCbsArrayBase@PEAVCCbsPackage@@V?$CCbsInterfaceArray@PEAVCCbsPackage@@@@@@QEBA_KAEBQEAVCCbsPackage@@PEA_KP6AH00@Z@Z; CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::FastFind(CCbsPackage * const &,unsigned __int64 *,int (*)(CCbsPackage * const &,CCbsPackage * const &))
0x1801a8e23  cmp     rax, rdi
0x1801a8e26  jz      short loc_1801A8E6C
0x1801a8e28  mov     rax, [rbp+70h+var_78]
0x1801a8e2c  test    rax, rax
0x1801a8e2f  jz      loc_1801A9CA2
0x1801a8e35  xor     ebx, ebx
0x1801a8e37  lea     esi, [rbx+8]
0x1801a8e3a  cmp     rbx, rax
0x1801a8e3d  jb      short loc_1801A8E43
0x1801a8e3f  mov     ecx, esi
0x1801a8e41  int     29h; Win8: RtlFailFast(ecx)
0x1801a8e43  mov     rax, [rbp+70h+var_68]
0x1801a8e47  mov     rcx, [rax+rbx*8]
0x1801a8e4b  mov     rcx, [rcx+8]
0x1801a8e4f  mov     rax, [rcx]
0x1801a8e52  mov     rax, [rax+10h]
0x1801a8e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8e5b  mov     rax, [rbp+70h+var_78]
0x1801a8e5f  inc     rbx
0x1801a8e62  cmp     rbx, rax
0x1801a8e65  jb      short loc_1801A8E43
0x1801a8e67  jmp     loc_1801A9CA2
0x1801a8e6c  mov     r8, [rbp+70h+var_E8]
0x1801a8e70  lea     rdx, [rbp+70h+var_A8]
0x1801a8e74  mov     rcx, rsi
0x1801a8e77  mov     [rbp+70h+var_A8], r13
0x1801a8e7b  call    ?InsertAt@?$CCbsInterfaceArray@PEAVCCbsPackage@@@@QEAAJAEBQEAVCCbsPackage@@_K@Z; CCbsInterfaceArray<CCbsPackage *>::InsertAt(CCbsPackage * const &,unsigned __int64)
0x1801a8e80  mov     edi, eax
0x1801a8e82  test    eax, eax
0x1801a8e84  jns     loc_1801A8F36
0x1801a8e8a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8e91  mov     [rbp+70h+var_B0], eax
0x1801a8e94  test    rcx, rcx
0x1801a8e97  jz      short loc_1801A8EDA
0x1801a8e99  mov     ebx, 3
0x1801a8e9e  lea     r9, aFailedToAddPac_4; "Failed to add package to the visited li"...
0x1801a8ea5  mov     r8d, ebx
0x1801a8ea8  xor     edx, edx
0x1801a8eaa  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801a8eaf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8eb6  lea     rax, [rbp+70h+var_B0]
0x1801a8eba  mov     qword ptr [rsp+170h+var_100], rax
0x1801a8ebf  lea     r9, asc_1802EE7AC; ": {}"
0x1801a8ec6  lea     rax, [rsp+170h+var_100]
0x1801a8ecb  mov     r8d, ebx
0x1801a8ece  mov     dl, 1
0x1801a8ed0  mov     [rsp+170h+var_150], rax; int
0x1801a8ed5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801a8eda  mov     rcx, [rbp+78h]; this
0x1801a8ede  lea     r8, aOnecoreBaseCbs_146; "onecore\\base\\cbs\\core\\cbspackageupd"...
0x1801a8ee5  mov     r9d, edi; char *
0x1801a8ee8  mov     edx, 268h; void *
0x1801a8eed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a8ef2  mov     rax, [rbp+70h+var_78]
0x1801a8ef6  test    rax, rax
0x1801a8ef9  jz      loc_1801A9CA4
0x1801a8eff  xor     ebx, ebx
0x1801a8f01  lea     esi, [rbx+8]
0x1801a8f04  cmp     rbx, rax
0x1801a8f07  jb      short loc_1801A8F0D
0x1801a8f09  mov     ecx, esi
0x1801a8f0b  int     29h; Win8: RtlFailFast(ecx)
0x1801a8f0d  mov     rax, [rbp+70h+var_68]
0x1801a8f11  mov     rcx, [rax+rbx*8]
0x1801a8f15  mov     rcx, [rcx+8]
0x1801a8f19  mov     rax, [rcx]
0x1801a8f1c  mov     rax, [rax+10h]
0x1801a8f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8f25  mov     rax, [rbp+70h+var_78]
0x1801a8f29  inc     rbx
0x1801a8f2c  cmp     rbx, rax
0x1801a8f2f  jb      short loc_1801A8F0D
0x1801a8f31  jmp     loc_1801A9CA4
0x1801a8f36  lea     r8, [rbp+70h+var_AC]; int *
0x1801a8f3a  mov     rdx, rbx; struct CCbsSession *
0x1801a8f3d  mov     rcx, r13; this
0x1801a8f40  call    ?IsDelegated@CCbsPackage@@AEBAJPEAVCCbsSession@@PEAH@Z; CCbsPackage::IsDelegated(CCbsSession *,int *)
0x1801a8f45  mov     edi, eax
0x1801a8f47  test    eax, eax
0x1801a8f49  jns     loc_1801A8FFB
0x1801a8f4f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8f56  mov     [rbp+70h+var_B0], eax
0x1801a8f59  test    rcx, rcx
0x1801a8f5c  jz      short loc_1801A8F9F
0x1801a8f5e  mov     ebx, 3
0x1801a8f63  lea     r9, aFailedToGetDel; "Failed to get delegate state."
0x1801a8f6a  mov     r8d, ebx
0x1801a8f6d  xor     edx, edx
0x1801a8f6f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801a8f74  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801a8f7b  lea     rax, [rbp+70h+var_B0]
0x1801a8f7f  mov     qword ptr [rsp+170h+var_100], rax
0x1801a8f84  lea     r9, asc_1802EE7AC; ": {}"
0x1801a8f8b  lea     rax, [rsp+170h+var_100]
0x1801a8f90  mov     r8d, ebx
0x1801a8f93  mov     dl, 1
0x1801a8f95  mov     [rsp+170h+var_150], rax; int
0x1801a8f9a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801a8f9f  mov     rcx, [rbp+78h]; this
0x1801a8fa3  lea     r8, aOnecoreBaseCbs_146; "onecore\\base\\cbs\\core\\cbspackageupd"...
0x1801a8faa  mov     r9d, edi; char *
0x1801a8fad  mov     edx, 26Fh; void *
0x1801a8fb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a8fb7  mov     rax, [rbp+70h+var_78]
0x1801a8fbb  test    rax, rax
0x1801a8fbe  jz      loc_1801A9CA4
0x1801a8fc4  xor     ebx, ebx
0x1801a8fc6  lea     esi, [rbx+8]
0x1801a8fc9  cmp     rbx, rax
0x1801a8fcc  jb      short loc_1801A8FD2
0x1801a8fce  mov     ecx, esi
0x1801a8fd0  int     29h; Win8: RtlFailFast(ecx)
0x1801a8fd2  mov     rax, [rbp+70h+var_68]
0x1801a8fd6  mov     rcx, [rax+rbx*8]
0x1801a8fda  mov     rcx, [rcx+8]
0x1801a8fde  mov     rax, [rcx]
0x1801a8fe1  mov     rax, [rax+10h]
0x1801a8fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8fea  mov     rax, [rbp+70h+var_78]
0x1801a8fee  inc     rbx
0x1801a8ff1  cmp     rbx, rax
0x1801a8ff4  jb      short loc_1801A8FD2
0x1801a8ff6  jmp     loc_1801A9CA4
0x1801a8ffb  cmp     [rbp+70h+var_AC], 0
0x1801a8fff  mov     esi, 8
0x1801a9004  jz      short loc_1801A9013
0x1801a9006  cmp     [rbp+70h+arg_28], 0
0x1801a900d  jz      loc_1801A9C69
0x1801a9013  mov     r15, [r13+2F0h]
0x1801a901a  mov     rax, [r13+2E0h]
0x1801a9021  lea     r12, [r15+rax*8]
0x1801a9025  cmp     r15, r12
0x1801a9028  jz      loc_1801A90D0
  ... truncated ...
```
