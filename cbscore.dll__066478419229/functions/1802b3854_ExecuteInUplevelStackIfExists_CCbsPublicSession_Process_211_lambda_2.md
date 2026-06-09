# ExecuteInUplevelStackIfExists__CCbsPublicSession::Process_::_211_::_lambda_2___

- ea: `0x1802b3854`
- end: `0x1802b438f`
- name: `ExecuteInUplevelStackIfExists__CCbsPublicSession::Process_::_211_::_lambda_2___`
- size: `2875`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1802b66f0`

## callees

- `0x180010cc0`
- `0x180012fe4`
- `0x1800138b8`
- `0x180095924`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800ad504`
- `0x1800c0054`
- `0x1800eb920`
- `0x1800fdf20`
- `0x180100c80`
- `0x180140040`
- `0x18014f298`
- `0x18017560c`
- `0x1801cde2c`
- `0x1802b3854`
- `0x1802b46fc`
- `0x1802b490c`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802b3d84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802b3d84`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1802b3d6d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1802b3d6d`

## string_xrefs

- `0x1802b3999`: `Failed to create servicing querier`
- `0x1802b3a0d`: `Microsoft-Windows-ServicingStack,language=neutral,publicKeyToken=31bf3856ad364e35,versionScope=nonSxS,processorArchitecture=amd64`
- `0x1802b3dac`: `Failed to duplicate user token for session object.`
- `0x1802b3ed0`: `Failed to copy session communication object to the session used for writing package file list.`
- `0x1802b3c8c`: `Failed to query private session interface, wrong cbscore.dll`
- `0x1802b4359`: `No uplevel stack path configured, will not use uplevel stack.`
- `0x1802b4138`: `Failed to copy property value {} to the session.`
- `0x1802b3e56`: `Failed to create UI handler iterator.`
- `0x1802b3d2c`: `Private session 3 interface is not supported. Communication will not be shared with the uplevel stack.`

## pseudocode

```c
__int64 __fastcall ExecuteInUplevelStackIfExists__CCbsPublicSession::Process_::_211_::_lambda_2___(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        __int64 *a5,
        HANDLE hExistingToken,
        _BYTE *a7)
{
  int v7; // r12d
  _WORD *v10; // rax
  __int64 v11; // rdx
  int v12; // edi
  int v13; // edx
  int ServicingQuerier; // eax
  int v15; // edx
  __int64 v16; // rax
  __int64 *v17; // rbx
  int v18; // eax
  int v19; // edx
  __int64 v20; // rdx
  int v21; // eax
  int v22; // edx
  struct ICbsSession **InitPointer; // rax
  int v24; // eax
  int v25; // edx
  __int64 (__fastcall ***v26)(_QWORD, GUID *, __int64); // rdi
  __int64 v27; // rax
  int v28; // eax
  int v29; // edx
  __int64 v30; // rdx
  __int64 (__fastcall ***v31)(_QWORD, GUID *, __int64); // rdi
  __int64 v32; // rax
  void **phNewToken; // rax
  signed int LastError; // edi
  int v35; // edx
  unsigned int v36; // eax
  int v37; // edx
  struct ICbsUIHandlerIterator **v38; // rax
  int UIHandlerIterator; // eax
  int v40; // edx
  int v41; // eax
  int v42; // edx
  __int64 *v43; // rdx
  __int64 v44; // rax
  __int64 (__fastcall ***v45)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 (__fastcall *v46)(_QWORD, GUID *, __int64); // rdi
  __int64 v47; // rax
  int v48; // eax
  int v49; // edx
  int v50; // esi
  int v51; // eax
  int v52; // edx
  int v53; // edx
  __int64 (__fastcall ***v54)(_QWORD, GUID *, __int64); // rdi
  __int64 v55; // rax
  int v56; // eax
  int v57; // edx
  int v58; // eax
  int v59; // edx
  int TokenType; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *TokenTypea; // [rsp+20h] [rbp-E0h]
  __int64 *v63; // [rsp+40h] [rbp-C0h] BYREF
  int v64[2]; // [rsp+48h] [rbp-B8h] BYREF
  char v65[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v66; // [rsp+58h] [rbp-A8h]
  __int64 *v67; // [rsp+60h] [rbp-A0h]
  __int64 *v68; // [rsp+68h] [rbp-98h]
  __int64 **v69; // [rsp+70h] [rbp-90h]
  __int64 *v70; // [rsp+78h] [rbp-88h]
  __int64 (__fastcall ****v71)(_QWORD, GUID *, __int64); // [rsp+80h] [rbp-80h]
  struct CCbsExecutionObjectBase **v72; // [rsp+88h] [rbp-78h]
  unsigned int v73[2]; // [rsp+90h] [rbp-70h] BYREF
  _WORD *v74; // [rsp+98h] [rbp-68h] BYREF
  __int64 v75; // [rsp+A0h] [rbp-60h] BYREF
  int v76[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 (__fastcall ***v77)(_QWORD, GUID *, __int64); // [rsp+B0h] [rbp-50h] BYREF
  __int64 *v78; // [rsp+B8h] [rbp-48h] BYREF
  struct CCbsExecutionObjectBase *v79; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v80; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v81; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v82; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v83; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v84; // [rsp+E8h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v7 = (int)hExistingToken;
  v63 = a5;
  v10 = *(_WORD **)(a2 + 1680);
  v75 = a3;
  *(_QWORD *)v64 = a1;
  v74 = v10;
  if ( v10 && *v10 )
  {
    v77 = 0;
    v83 = 0;
    v78 = 0;
    v82 = 0;
    v81 = 0;
    v80 = 0;
    v79 = 0;
    *(_QWORD *)v76 = 0;
    v84 = 0;
    *a7 = 1;
    LogAdapter::TraceAtLevel<wchar_t const *>(1, "Evaluating possible execution in uplevel stack: {}", &v74);
    if ( !vServicingStackVersion )
    {
      v12 = -2147418113;
      LODWORD(v75) = -2147418113;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "vServicingStackVersion has not been set. This should always be done in CbsCoreInitialize.");
        *(_QWORD *)v76 = &v75;
        LOBYTE(v13) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v13,
          3,
          (unsigned int)": {}",
          (__int64)v76);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21C,
        (unsigned int)"onecore\\base\\cbs\\core\\cbspublicsession.cpp",
        (const char *)0x8000FFFFLL,
        TokenType);
      goto LABEL_91;
    }
    ServicingQuerier = CCbsSession::CreateServicingQuerier(a2, v11, v76);
    v12 = ServicingQuerier;
    if ( ServicingQuerier < 0 )
    {
      LODWORD(v75) = ServicingQuerier;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to create servicing querier");
        *(_QWORD *)v73 = &v75;
        LOBYTE(v15) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v15,
          3,
          (unsigned int)": {}",
          (__int64)v73);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21F,
        (unsigned int)"onecore\\base\\cbs\\core\\cbspublicsession.cpp",
        (const char *)(unsigned int)v12,
        TokenType);
      if ( !*(_QWORD *)v76 )
        goto LABEL_91;
      v16 = **(_QWORD **)v76;
      goto LABEL_90;
    }
    v17 = *(__int64 **)v76;
    TokenTypea = &v84;
    v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, _WORD *, const wchar_t *))(**(_QWORD **)v76 + 56LL))(
            *(_QWORD *)v76,
            1,
            v74,
            L"Microsoft-Windows-ServicingStack,language=neutral,publicKeyToken=31bf3856ad364e35,versionScope=nonSxS,proces"
             "sorArchitecture=amd64");
    v12 = v18;
    if ( v18 < 0 )
    {
      LODWORD(v75) = v18;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to query version of uplevel stack at: {}",
          (__int64)&v74);
        *(_QWORD *)v73 = &v75;
        LOBYTE(v19) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v19,
          3,
          (unsigned int)": {}",
          (__int64)v73);
      }
      v20 = 551;
      goto LABEL_16;
    }
    if ( vServicingStackVersion >= v84 )
    {
      LogAdapter::TraceAtLevel<>(
        1,
        "Uplevel stack version is less than or equal to the running stack version. Will not use uplevel stack.");
      *a7 = 0;
      if ( v17 )
        (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
      v12 = 0;
      goto LABEL_91;
    }
    LogAdapter::TraceAtLevel<wchar_t const *>(1, "Executing operation in uplevel stack: {}", &v74);
    if ( !Windows::AutoComPtr<CCbsExecutionObject>::AllocateWithNew<CCbsExecutionObject,>(&v79) )
    {
      v12 = -2147024882;
      v20 = 562;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecore\\base\\cbs\\core\\cbspublicsession.cpp",
        (const char *)(unsigned int)v12,
        (int)TokenTypea);
LABEL_88:
      if ( !v17 )
      {
LABEL_91:
        Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v79);
        Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v80);
        Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v81);
        Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v82);
        Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v78);
        Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v83);
        Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v77);
        return (unsigned int)v12;
      }
      v16 = *v17;
LABEL_90:
      (*(void (**)(void))(v16 + 16))();
      goto LABEL_91;
    }
    v21 = ExecutionEngineAcquireLock(0, v79);
    v12 = v21;
    if ( v21 < 0 )
    {
      LODWORD(v75) = v21;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed aquiring execution engine lock");
        *(_QWORD *)v73 = &v75;
        LOBYTE(v22) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v22,
          3,
          (unsigned int)": {}",
          (__int64)v73);
      }
      v20 = 566;
      goto LABEL_16;
    }
    InitPointer = (struct ICbsSession **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v77);
    v24 = CbsOfflineUtil::CbsCreateSessionFromWindirWithVersion(
            (CbsOfflineUtil *)&vCbsOfflineUtil,
            0,
            a4,
            &v84,
            InitPointer);
    v12 = v24;
    if ( v24 < 0 )
    {
      LODWORD(v75) = v24;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to load uplevel stack at: {}",
          (__int64)&v74);
        *(_QWORD *)v73 = &v75;
        LOBYTE(v25) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v25,
          3,
          (unsigned int)": {}",
          (__int64)v73);
      }
      v20 = 570;
      goto LABEL_16;
    }
    v26 = v77;
    v66 = &v80;
    v65[0] = 1;
    v67 = &v81;
    v68 = &v82;
    v69 = &v78;
    v70 = &v83;
    v71 = &v77;
    v72 = &v79;
    v27 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v78);
    v28 = (**v26)(v26, &GUID_fb3b7670_d62d_4943_8e9f_a7de7f88f63b, v27);
    v12 = v28;
    if ( v28 < 0 )
    {
      LODWORD(v75) = v28;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to query private session interface, wrong cbscore.dll");
        *(_QWORD *)v73 = &v75;
        LOBYTE(v29) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v29,
          3,
          (unsigned int)": {}",
          (__int64)v73);
      }
      v30 = 588;
LABEL_86:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v30,
        (unsigned int)"onecore\\base\\cbs\\core\\cbspublicsession.cpp",
        (const char *)(unsigned int)v12,
        (int)TokenTypea);
LABEL_87:
      Windows::Detail::OnBlockExitImpl__ExecuteInUplevelStackIfExists__CCbsPublicSession::Process_::_211_::_lambda_2____::_2_::_lambda_1___::_OnBlockExitImpl__ExecuteInUplevelStackIfExists__CCbsPublicSession::Process_::_211_::_lambda_2____::_2_::_lambda_1___(v65);
      goto LABEL_88;
    }
    (*(void (__fastcall **)(__int64 *))(*v78 + 216))(v78);
    (*(void (__fastcall **)(__int64 *))(*v78 + 224))(v78);
    v31 = v77;
    v32 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v82);
    v12 = (**v31)(v31, &GUID_a3397718_7938_4776_bcac_0c92ccc3ece7, v32);
    if ( v12 == -2147467262 )
    {
      LogAdapter::TraceAtLevel<>(
        1,
        "Private session 3 interface is not supported. Communication will not be shared with the uplevel stack.");
    }
    else
    {
      if ( v12 < 0 )
      {
        LODWORD(v75) = v12;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to query private session 3 interface");
          *(_QWORD *)v73 = &v75;
          LOBYTE(v37) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v37,
            3,
            (unsigned int)": {}",
            (__int64)v73);
        }
        v30 = 607;
        goto LABEL_86;
      }
      v38 = (struct ICbsUIHandlerIterator **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v81);
      UIHandlerIterator = CCbsExecutionCommunication::CreateUIHandlerIterator(
                            (CCbsExecutionCommunication *)(a2 + 1280),
                            v38);
      v12 = UIHandlerIterator;
      if ( UIHandlerIterator < 0 )
      {
        LODWORD(v75) = UIHandlerIterator;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to create UI handler iterator.");
          *(_QWORD *)v73 = &v75;
          LOBYTE(v40) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v40,
            3,
            (unsigned int)": {}",
            (__int64)v73);
        }
        v30 = 612;
        goto LABEL_86;
      }
      v41 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v82 + 232LL))(v82, v81);
      v12 = v41;
      if ( v41 < 0 )
      {
        LODWORD(v75) = v41;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to copy session communication object to the session used for writing package file list.");
          *(_QWORD *)v73 = &v75;
          LOBYTE(v42) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v42,
            3,
            (unsigned int)": {}",
            (__int64)v73);
        }
        v30 = 615;
        goto LABEL_86;
      }
    }
    if ( hExistingToken )
    {
      *(_QWORD *)v76 = 0;
      phNewToken = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(v76);
      v7 = 0;
      if ( !DuplicateTokenEx(hExistingToken, 0, 0, SecurityImpersonation, TokenImpersonation, phNewToken) )
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to duplicate user token for session object.");
          if ( LastError > 0 )
            v36 = (unsigned __int16)LastError | 0x80070000;
          else
            v36 = LastError;
          LODWORD(v75) = v36;
          LOBYTE(v35) = 1;
          *(_QWORD *)v73 = &v75;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v35,
            3,
            (unsigned int)": {0}",
            (__int64)v73);
        }
        if ( !LastError )
        {
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v76);
          Windows::Detail::OnBlockExitImpl__ExecuteInUplevelStackIfExists__CCbsPublicSession::Process_::_211_::_lambda_2____::_2_::_lambda_1___::_OnBlockExitImpl__ExecuteInUplevelStackIfExists__CCbsPublicSession::Process_::_211_::_lambda_2____::_2_::_lambda_1___(v65);
          if ( v17 )
            (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
          v12 = 0;
          goto LABEL_91;
        }
        v12 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x275,
                (unsigned int)"onecore\\base\\cbs\\core\\cbspublicsession.cpp",
                (const char *)(unsigned int)LastError,
                (unsigned int)TokenTypea);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v76);
        goto LABEL_87;
      }
      v43 = *(__int64 **)v76;
      v44 = *v78;
      *(_QWORD *)v76 = 0;
      (*(void (__fastcall **)(__int64 *, __int64 *))(v44 + 208))(v78, v43);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v76);
    }
    v45 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v77;
    v46 = **v77;
    v47 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v83);
    v48 = v46(v45, &GUID_f112757a_565b_4260_bd05_9fa34417349a, v47);
    v12 = v48;
    if ( v48 < 0 )
    {
      LODWORD(v75) = v48;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed querying ICbsSession10 interface.");
        *(_QWORD *)v73 = &v75;
        LOBYTE(v49) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v49,
          3,
          (unsigned int)": {}",
          (__int64)v73);
      }
      v30 = 635;
      goto LABEL_86;
    }
    v50 = v7;
    do
    {
      if ( v50 != 9 )
      {
        *(_QWORD *)v73 = *(_QWORD *)(a2 + 8LL * v50 + 1608);
        if ( *(_QWORD *)v73 )
        {
          v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v83 + 192LL))(v83, (unsigned int)v50);
          if ( v12 < 0 )
          {
            LODWORD(v75) = v12;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to copy property value {} to the session.",
                (__int64)v73);
              v63 = &v75;
              LOBYTE(v53) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v53,
                3,
                (unsigned int)": {}",
                (__int64)&v63);
            }
            v30 = 649;
            goto LABEL_86;
          }
        }
      }
      ++v50;
    }
    while ( v50 < 16 );
    LODWORD(TokenTypea) = (_DWORD)a4;
    v51 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), _QWORD, __int64, __int64 *))(*v77)[3])(
            v77,
            0,
            v75,
            v63);
    v12 = v51;
    if ( v51 < 0 )
    {
      LODWORD(v75) = v51;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to query offline servicing processor interface");
        v63 = &v75;
        LOBYTE(v52) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v52,
          3,
          (unsigned int)": {}",
          (__int64)&v63);
      }
      v30 = 655;
      goto LABEL_86;
    }
    v54 = v77;
    v55 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v80);
    v56 = (**v54)(v54, &GUID_be996087_7c81_465a_9bb1_39ce7350adcd, v55);
    v12 = v56;
    if ( v56 < 0 )
    {
      LODWORD(v75) = v56;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to query offline servicing processor interface");
        v63 = &v75;
        LOBYTE(v57) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v57,
          3,
          (unsigned int)": {}",
          (__int64)&v63);
      }
      v30 = 658;
      goto LABEL_86;
    }
    v58 = CCbsPublicSession::Process_::_211_::_lambda_2_::operator()(*(_QWORD *)v64, v80);
    v12 = v58;
    if ( v58 < 0 )
    {
      LODWORD(v75) = v58;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to perform operation with upstream stack.");
        *(_QWORD *)v64 = &v75;
        LOBYTE(v59) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v59,
          3,
          (unsigned int)": {}",
          (__int64)v64);
      }
      v30 = 660;
      goto LABEL_86;
    }
    LogAdapter::TraceAtLevel<wchar_t const *>(1, "Returned from executing operation in uplevel stack: {}", &v74);
    Windows::Detail::OnBlockExitImpl__ExecuteInUplevelStackIfExists__CCbsPublicSession::Process_::_211_::_lambda_2____::_2_::_lambda_1___::_OnBlockExitImpl__ExecuteInUplevelStackIfExists__CCbsPublicSession::Process_::_211_::_lambda_2____::_2_::_lambda_1___(v65);
    if ( v17 )
      (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
    Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v79);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v80);
    Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v81);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v82);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v78);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v83);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v77);
  }
  else
  {
    LogAdapter::TraceAtLevel<>(1, "No uplevel stack path configured, will not use uplevel stack.");
    *a7 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1802b3854  push    rbp
0x1802b3856  push    rbx
0x1802b3857  push    rsi
0x1802b3858  push    rdi
0x1802b3859  push    r12
0x1802b385b  push    r13
0x1802b385d  push    r14
0x1802b385f  push    r15
0x1802b3861  lea     rbp, [rsp-8]
0x1802b3866  sub     rsp, 108h
0x1802b386d  mov     rax, cs:__security_cookie
0x1802b3874  xor     rax, rsp
0x1802b3877  mov     [rbp+40h+var_50], rax
0x1802b387b  mov     rax, [rbp+40h+arg_20]
0x1802b387f  xor     ebx, ebx
0x1802b3881  mov     r12, [rbp+40h+hExistingToken]
0x1802b3885  mov     r13, r9
0x1802b3888  mov     rsi, [rbp+40h+arg_30]
0x1802b388f  mov     r15, rdx
0x1802b3892  mov     [rsp+140h+var_100], rax
0x1802b3897  mov     rax, [rdx+690h]
0x1802b389e  mov     [rbp+40h+var_A0], r8
0x1802b38a2  mov     qword ptr [rsp+140h+var_F8], rcx
0x1802b38a7  mov     [rbp+40h+var_A8], rax
0x1802b38ab  test    rax, rax
0x1802b38ae  jz      loc_1802B4359
0x1802b38b4  cmp     [rax], bx
0x1802b38b7  jz      loc_1802B4359
0x1802b38bd  lea     r14d, [rbx+1]
0x1802b38c1  mov     [rbp+40h+var_90], rbx
0x1802b38c5  mov     ecx, r14d
0x1802b38c8  mov     [rbp+40h+var_60], rbx
0x1802b38cc  lea     r8, [rbp+40h+var_A8]
0x1802b38d0  mov     [rbp+40h+var_88], rbx
0x1802b38d4  lea     rdx, aEvaluatingPoss; "Evaluating possible execution in upleve"...
0x1802b38db  mov     [rbp+40h+var_68], rbx
0x1802b38df  mov     [rbp+40h+var_70], rbx
0x1802b38e3  mov     [rbp+40h+var_78], rbx
0x1802b38e7  mov     [rbp+40h+var_80], rbx
0x1802b38eb  mov     qword ptr [rbp+40h+var_98], rbx
0x1802b38ef  mov     [rbp+40h+var_58], rbx
0x1802b38f3  mov     [rsi], r14b
0x1802b38f6  call    ??$TraceAtLevel@PEB_W@LogAdapter@@YAXW4LogLevel@0@QEBDAEBQEB_W@Z; LogAdapter::TraceAtLevel<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1802b38fb  cmp     cs:?vServicingStackVersion@@3_KA, rbx; unsigned __int64 vServicingStackVersion
0x1802b3902  jnz     short loc_1802B3973
0x1802b3904  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b390b  mov     edi, 8000FFFFh
0x1802b3910  mov     dword ptr [rbp+40h+var_A0], edi
0x1802b3913  test    rcx, rcx
0x1802b3916  jz      short loc_1802B3956
0x1802b3918  lea     esi, [rbx+3]
0x1802b391b  xor     edx, edx
0x1802b391d  mov     r8d, esi
0x1802b3920  lea     r9, aVservicingstac; "vServicingStackVersion has not been set"...
0x1802b3927  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1802b392c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b3933  lea     rax, [rbp+40h+var_A0]
0x1802b3937  mov     qword ptr [rbp+40h+var_98], rax
0x1802b393b  lea     r9, asc_1802EE7AC; ": {}"
0x1802b3942  lea     rax, [rbp+40h+var_98]
0x1802b3946  mov     r8d, esi
0x1802b3949  mov     dl, r14b
0x1802b394c  mov     qword ptr [rsp+140h+TokenType], rax; int
0x1802b3951  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1802b3956  mov     rcx, [rbp+48h]; this
0x1802b395a  lea     r8, aOnecoreBaseCbs_153; "onecore\\base\\cbs\\core\\cbspublicsess"...
0x1802b3961  mov     r9d, edi; char *
0x1802b3964  mov     edx, 21Ch; void *
0x1802b3969  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b396e  jmp     loc_1802B42A1
0x1802b3973  lea     r8, [rbp+40h+var_98]
0x1802b3977  mov     rcx, r15
0x1802b397a  call    ?CreateServicingQuerier@CCbsSession@@QEAAJW4InitializeFlags@IServicingQuerier@@PEAV?$AutoComPtr@VIServicingQuerier@@@Windows@@@Z; CCbsSession::CreateServicingQuerier(IServicingQuerier::InitializeFlags,Windows::AutoComPtr<IServicingQuerier> *)
0x1802b397f  mov     edi, eax
0x1802b3981  test    eax, eax
0x1802b3983  jns     short loc_1802B3A01
0x1802b3985  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b398c  mov     dword ptr [rbp+40h+var_A0], eax
0x1802b398f  test    rcx, rcx
0x1802b3992  jz      short loc_1802B39D4
0x1802b3994  mov     esi, 3
0x1802b3999  lea     r9, aFailedToCreate_85; "Failed to create servicing querier"
0x1802b39a0  mov     r8d, esi
0x1802b39a3  xor     edx, edx
0x1802b39a5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1802b39aa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b39b1  lea     rax, [rbp+40h+var_A0]
0x1802b39b5  mov     qword ptr [rbp+40h+var_B0], rax
0x1802b39b9  lea     r9, asc_1802EE7AC; ": {}"
0x1802b39c0  lea     rax, [rbp+40h+var_B0]
0x1802b39c4  mov     r8d, esi
0x1802b39c7  mov     dl, r14b
0x1802b39ca  mov     qword ptr [rsp+140h+TokenType], rax; int
0x1802b39cf  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1802b39d4  mov     rcx, [rbp+48h]; this
0x1802b39d8  lea     r8, aOnecoreBaseCbs_153; "onecore\\base\\cbs\\core\\cbspublicsess"...
0x1802b39df  mov     r9d, edi; char *
0x1802b39e2  mov     edx, 21Fh; void *
0x1802b39e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b39ec  mov     rcx, qword ptr [rbp+40h+var_98]
0x1802b39f0  test    rcx, rcx
0x1802b39f3  jz      loc_1802B42A1
0x1802b39f9  mov     rax, [rcx]
0x1802b39fc  jmp     loc_1802B4298
0x1802b3a01  mov     rbx, qword ptr [rbp+40h+var_98]
0x1802b3a05  lea     rcx, [rbp+40h+var_58]
0x1802b3a09  mov     r8, [rbp+40h+var_A8]
0x1802b3a0d  lea     r9, aMicrosoftWindo_4; "Microsoft-Windows-ServicingStack,langua"...
0x1802b3a14  mov     [rsp+140h+phNewToken], 0
0x1802b3a1d  mov     edx, r14d
0x1802b3a20  mov     qword ptr [rsp+140h+TokenType], rcx
0x1802b3a25  mov     rcx, rbx
0x1802b3a28  mov     rax, [rbx]
0x1802b3a2b  mov     rax, [rax+38h]
0x1802b3a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b3a34  mov     edi, eax
0x1802b3a36  test    eax, eax
0x1802b3a38  jns     short loc_1802B3AAF
0x1802b3a3a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b3a41  mov     dword ptr [rbp+40h+var_A0], eax
0x1802b3a44  test    rcx, rcx
0x1802b3a47  jz      short loc_1802B3A92
0x1802b3a49  lea     rax, [rbp+40h+var_A8]
0x1802b3a4d  mov     esi, 3
0x1802b3a52  mov     r8d, esi
0x1802b3a55  mov     qword ptr [rsp+140h+TokenType], rax
0x1802b3a5a  lea     r9, aFailedToQueryV_0; "Failed to query version of uplevel stac"...
0x1802b3a61  xor     edx, edx
0x1802b3a63  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1802b3a68  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b3a6f  lea     rax, [rbp+40h+var_A0]
0x1802b3a73  mov     qword ptr [rbp+40h+var_B0], rax
0x1802b3a77  lea     r9, asc_1802EE7AC; ": {}"
0x1802b3a7e  lea     rax, [rbp+40h+var_B0]
0x1802b3a82  mov     r8d, esi
0x1802b3a85  mov     dl, r14b
0x1802b3a88  mov     qword ptr [rsp+140h+TokenType], rax; int
0x1802b3a8d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1802b3a92  mov     edx, 227h; void *
0x1802b3a97  mov     rcx, [rbp+48h]; this
0x1802b3a9b  lea     r8, aOnecoreBaseCbs_153; "onecore\\base\\cbs\\core\\cbspublicsess"...
0x1802b3aa2  mov     r9d, edi; char *
0x1802b3aa5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b3aaa  jmp     loc_1802B428D
0x1802b3aaf  mov     rax, [rbp+40h+var_58]
0x1802b3ab3  mov     ecx, r14d
0x1802b3ab6  cmp     cs:?vServicingStackVersion@@3_KA, rax; unsigned __int64 vServicingStackVersion
0x1802b3abd  jb      short loc_1802B3AE9
0x1802b3abf  lea     rdx, aUplevelStackVe; "Uplevel stack version is less than or e"...
0x1802b3ac6  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1802b3acb  mov     byte ptr [rsi], 0
0x1802b3ace  test    rbx, rbx
0x1802b3ad1  jz      short loc_1802B3AE2
0x1802b3ad3  mov     rax, [rbx]
0x1802b3ad6  mov     rcx, rbx
0x1802b3ad9  mov     rax, [rax+10h]
0x1802b3add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b3ae2  xor     edi, edi
0x1802b3ae4  jmp     loc_1802B42A1
0x1802b3ae9  lea     r8, [rbp+40h+var_A8]
0x1802b3aed  lea     rdx, aExecutingOpera; "Executing operation in uplevel stack: {"...
0x1802b3af4  call    ??$TraceAtLevel@PEB_W@LogAdapter@@YAXW4LogLevel@0@QEBDAEBQEB_W@Z; LogAdapter::TraceAtLevel<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1802b3af9  lea     rcx, [rbp+40h+var_80]
0x1802b3afd  call    ??$AllocateWithNew@VCCbsExecutionObject@@$$V@?$AutoComPtr@VCCbsExecutionObject@@@Windows@@QEAAPEAVCCbsExecutionObject@@XZ; Windows::AutoComPtr<CCbsExecutionObject>::AllocateWithNew<CCbsExecutionObject,>(void)
0x1802b3b02  test    rax, rax
0x1802b3b05  jnz     short loc_1802B3B13
0x1802b3b07  mov     edi, 8007000Eh
0x1802b3b0c  mov     edx, 232h
0x1802b3b11  jmp     short loc_1802B3A97
0x1802b3b13  mov     rdx, [rbp+40h+var_80]; struct CCbsExecutionObjectBase *
0x1802b3b17  xor     ecx, ecx; unsigned int
0x1802b3b19  call    ?ExecutionEngineAcquireLock@@YAJKPEAVCCbsExecutionObjectBase@@@Z; ExecutionEngineAcquireLock(ulong,CCbsExecutionObjectBase *)
0x1802b3b1e  mov     edi, eax
0x1802b3b20  test    eax, eax
0x1802b3b22  jns     short loc_1802B3B7D
0x1802b3b24  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b3b2b  mov     dword ptr [rbp+40h+var_A0], eax
0x1802b3b2e  test    rcx, rcx
0x1802b3b31  jz      short loc_1802B3B73
0x1802b3b33  mov     esi, 3
0x1802b3b38  lea     r9, aFailedAquiring; "Failed aquiring execution engine lock"
0x1802b3b3f  mov     r8d, esi
0x1802b3b42  xor     edx, edx
0x1802b3b44  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1802b3b49  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b3b50  lea     rax, [rbp+40h+var_A0]
0x1802b3b54  mov     qword ptr [rbp+40h+var_B0], rax
0x1802b3b58  lea     r9, asc_1802EE7AC; ": {}"
0x1802b3b5f  lea     rax, [rbp+40h+var_B0]
0x1802b3b63  mov     r8d, esi
0x1802b3b66  mov     dl, r14b
0x1802b3b69  mov     qword ptr [rsp+140h+TokenType], rax
0x1802b3b6e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1802b3b73  mov     edx, 236h
0x1802b3b78  jmp     loc_1802B3A97
0x1802b3b7d  lea     rcx, [rbp+40h+var_90]
0x1802b3b81  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1802b3b86  lea     r9, [rbp+40h+var_58]; unsigned __int64 *
0x1802b3b8a  mov     qword ptr [rsp+140h+TokenType], rax; struct ICbsSession **
0x1802b3b8f  mov     r8, r13; wchar_t *
0x1802b3b92  lea     rcx, ?vCbsOfflineUtil@@3VCbsOfflineUtil@@A; this
0x1802b3b99  xor     edx, edx; int
0x1802b3b9b  call    ?CbsCreateSessionFromWindirWithVersion@CbsOfflineUtil@@UEAAJHQEB_WPEB_KPEAPEAUICbsSession@@@Z; CbsOfflineUtil::CbsCreateSessionFromWindirWithVersion(int,wchar_t const * const,unsigned __int64 const *,ICbsSession * *)
0x1802b3ba0  mov     edi, eax
0x1802b3ba2  test    eax, eax
0x1802b3ba4  jns     short loc_1802B3C08
0x1802b3ba6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b3bad  mov     dword ptr [rbp+40h+var_A0], eax
0x1802b3bb0  test    rcx, rcx
0x1802b3bb3  jz      short loc_1802B3BFE
0x1802b3bb5  lea     rax, [rbp+40h+var_A8]
0x1802b3bb9  mov     esi, 3
0x1802b3bbe  mov     r8d, esi
0x1802b3bc1  mov     qword ptr [rsp+140h+TokenType], rax
0x1802b3bc6  lea     r9, aFailedToLoadUp_1; "Failed to load uplevel stack at: {}"
0x1802b3bcd  xor     edx, edx
0x1802b3bcf  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1802b3bd4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b3bdb  lea     rax, [rbp+40h+var_A0]
0x1802b3bdf  mov     qword ptr [rbp+40h+var_B0], rax
0x1802b3be3  lea     r9, asc_1802EE7AC; ": {}"
0x1802b3bea  lea     rax, [rbp+40h+var_B0]
0x1802b3bee  mov     r8d, esi
0x1802b3bf1  mov     dl, r14b
0x1802b3bf4  mov     qword ptr [rsp+140h+TokenType], rax
0x1802b3bf9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1802b3bfe  mov     edx, 23Ah
0x1802b3c03  jmp     loc_1802B3A97
0x1802b3c08  mov     rdi, [rbp+40h+var_90]
0x1802b3c0c  lea     rax, [rbp+40h+var_78]
0x1802b3c10  mov     [rsp+140h+var_E8], rax
0x1802b3c15  lea     rcx, [rbp+40h+var_88]
0x1802b3c19  lea     rax, [rbp+40h+var_70]
0x1802b3c1d  mov     [rsp+140h+var_F0], r14b
0x1802b3c22  mov     [rsp+140h+var_E0], rax
0x1802b3c27  lea     rax, [rbp+40h+var_68]
0x1802b3c2b  mov     [rsp+140h+var_D8], rax
0x1802b3c30  lea     rax, [rbp+40h+var_88]
0x1802b3c34  mov     [rsp+140h+var_D0], rax
0x1802b3c39  lea     rax, [rbp+40h+var_60]
0x1802b3c3d  mov     [rsp+140h+var_C8], rax
0x1802b3c42  lea     rax, [rbp+40h+var_90]
0x1802b3c46  mov     [rbp+40h+var_C0], rax
0x1802b3c4a  lea     rax, [rbp+40h+var_80]
0x1802b3c4e  mov     [rbp+40h+var_B8], rax
0x1802b3c52  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1802b3c57  mov     rcx, [rdi]
0x1802b3c5a  lea     rdx, _GUID_fb3b7670_d62d_4943_8e9f_a7de7f88f63b
0x1802b3c61  mov     r8, rax
0x1802b3c64  mov     r9, [rcx]
0x1802b3c67  mov     rcx, rdi
0x1802b3c6a  mov     rax, r9
0x1802b3c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b3c72  mov     edi, eax
0x1802b3c74  test    eax, eax
0x1802b3c76  jns     short loc_1802B3CD1
0x1802b3c78  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b3c7f  mov     dword ptr [rbp+40h+var_A0], eax
0x1802b3c82  test    rcx, rcx
0x1802b3c85  jz      short loc_1802B3CC7
0x1802b3c87  mov     esi, 3
0x1802b3c8c  lea     r9, aFailedToQueryP; "Failed to query private session interfa"...
0x1802b3c93  mov     r8d, esi
0x1802b3c96  xor     edx, edx
0x1802b3c98  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1802b3c9d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b3ca4  lea     rax, [rbp+40h+var_A0]
0x1802b3ca8  mov     qword ptr [rbp+40h+var_B0], rax
0x1802b3cac  lea     r9, asc_1802EE7AC; ": {}"
0x1802b3cb3  lea     rax, [rbp+40h+var_B0]
0x1802b3cb7  mov     r8d, esi
0x1802b3cba  mov     dl, r14b
0x1802b3cbd  mov     qword ptr [rsp+140h+TokenType], rax
0x1802b3cc2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1802b3cc7  mov     edx, 24Ch
0x1802b3ccc  jmp     loc_1802B4270
0x1802b3cd1  mov     rcx, [rbp+40h+var_88]
0x1802b3cd5  mov     rax, [rcx]
0x1802b3cd8  mov     rax, [rax+0D8h]
0x1802b3cdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b3ce4  mov     rcx, [rbp+40h+var_88]
0x1802b3ce8  mov     rax, [rcx]
0x1802b3ceb  mov     rax, [rax+0E0h]
0x1802b3cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b3cf7  mov     rdi, [rbp+40h+var_90]
0x1802b3cfb  lea     rcx, [rbp+40h+var_68]
0x1802b3cff  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1802b3d04  mov     rcx, [rdi]
0x1802b3d07  lea     rdx, _GUID_a3397718_7938_4776_bcac_0c92ccc3ece7
0x1802b3d0e  mov     r8, rax
0x1802b3d11  mov     r9, [rcx]
0x1802b3d14  mov     rcx, rdi
0x1802b3d17  mov     rax, r9
0x1802b3d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b3d1f  mov     edi, eax
0x1802b3d21  cmp     eax, 80004002h
0x1802b3d26  jnz     loc_1802B3DC7
0x1802b3d2c  lea     rdx, aPrivateSession; "Private session 3 interface is not supp"...
0x1802b3d33  mov     ecx, r14d
0x1802b3d36  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
  ... truncated ...
```
