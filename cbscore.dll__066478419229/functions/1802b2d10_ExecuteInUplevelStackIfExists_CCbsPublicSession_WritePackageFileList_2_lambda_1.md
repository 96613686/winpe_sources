# ExecuteInUplevelStackIfExists__CCbsPublicSession::WritePackageFileList_::_2_::_lambda_1___

- ea: `0x1802b2d10`
- end: `0x1802b384b`
- name: `ExecuteInUplevelStackIfExists__CCbsPublicSession::WritePackageFileList_::_2_::_lambda_1___`
- size: `2875`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1802b79b0`

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
- `0x1802b2d10`
- `0x1802b46fc`
- `0x1802b4890`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802b3240`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802b3240`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1802b3229`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1802b3229`

## string_xrefs

- `0x1802b2e55`: `Failed to create servicing querier`
- `0x1802b2ec9`: `Microsoft-Windows-ServicingStack,language=neutral,publicKeyToken=31bf3856ad364e35,versionScope=nonSxS,processorArchitecture=amd64`
- `0x1802b3268`: `Failed to duplicate user token for session object.`
- `0x1802b338c`: `Failed to copy session communication object to the session used for writing package file list.`
- `0x1802b3148`: `Failed to query private session interface, wrong cbscore.dll`
- `0x1802b3815`: `No uplevel stack path configured, will not use uplevel stack.`
- `0x1802b35f4`: `Failed to copy property value {} to the session.`
- `0x1802b3312`: `Failed to create UI handler iterator.`
- `0x1802b31e8`: `Private session 3 interface is not supported. Communication will not be shared with the uplevel stack.`

## pseudocode

```c
__int64 __fastcall ExecuteInUplevelStackIfExists__CCbsPublicSession::WritePackageFileList_::_2_::_lambda_1___(
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
    v58 = CCbsPublicSession::WritePackageFileList_::_2_::_lambda_1_::operator()(*(_QWORD *)v64, v80);
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
0x1802b2d10  push    rbp
0x1802b2d12  push    rbx
0x1802b2d13  push    rsi
0x1802b2d14  push    rdi
0x1802b2d15  push    r12
0x1802b2d17  push    r13
0x1802b2d19  push    r14
0x1802b2d1b  push    r15
0x1802b2d1d  lea     rbp, [rsp-8]
0x1802b2d22  sub     rsp, 108h
0x1802b2d29  mov     rax, cs:__security_cookie
0x1802b2d30  xor     rax, rsp
0x1802b2d33  mov     [rbp+40h+var_50], rax
0x1802b2d37  mov     rax, [rbp+40h+arg_20]
0x1802b2d3b  xor     ebx, ebx
0x1802b2d3d  mov     r12, [rbp+40h+hExistingToken]
0x1802b2d41  mov     r13, r9
0x1802b2d44  mov     rsi, [rbp+40h+arg_30]
0x1802b2d4b  mov     r15, rdx
0x1802b2d4e  mov     [rsp+140h+var_100], rax
0x1802b2d53  mov     rax, [rdx+690h]
0x1802b2d5a  mov     [rbp+40h+var_A0], r8
0x1802b2d5e  mov     qword ptr [rsp+140h+var_F8], rcx
0x1802b2d63  mov     [rbp+40h+var_A8], rax
0x1802b2d67  test    rax, rax
0x1802b2d6a  jz      loc_1802B3815
0x1802b2d70  cmp     [rax], bx
0x1802b2d73  jz      loc_1802B3815
0x1802b2d79  lea     r14d, [rbx+1]
0x1802b2d7d  mov     [rbp+40h+var_90], rbx
0x1802b2d81  mov     ecx, r14d
0x1802b2d84  mov     [rbp+40h+var_60], rbx
0x1802b2d88  lea     r8, [rbp+40h+var_A8]
0x1802b2d8c  mov     [rbp+40h+var_88], rbx
0x1802b2d90  lea     rdx, aEvaluatingPoss; "Evaluating possible execution in upleve"...
0x1802b2d97  mov     [rbp+40h+var_68], rbx
0x1802b2d9b  mov     [rbp+40h+var_70], rbx
0x1802b2d9f  mov     [rbp+40h+var_78], rbx
0x1802b2da3  mov     [rbp+40h+var_80], rbx
0x1802b2da7  mov     qword ptr [rbp+40h+var_98], rbx
0x1802b2dab  mov     [rbp+40h+var_58], rbx
0x1802b2daf  mov     [rsi], r14b
0x1802b2db2  call    ??$TraceAtLevel@PEB_W@LogAdapter@@YAXW4LogLevel@0@QEBDAEBQEB_W@Z; LogAdapter::TraceAtLevel<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1802b2db7  cmp     cs:?vServicingStackVersion@@3_KA, rbx; unsigned __int64 vServicingStackVersion
0x1802b2dbe  jnz     short loc_1802B2E2F
0x1802b2dc0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b2dc7  mov     edi, 8000FFFFh
0x1802b2dcc  mov     dword ptr [rbp+40h+var_A0], edi
0x1802b2dcf  test    rcx, rcx
0x1802b2dd2  jz      short loc_1802B2E12
0x1802b2dd4  lea     esi, [rbx+3]
0x1802b2dd7  xor     edx, edx
0x1802b2dd9  mov     r8d, esi
0x1802b2ddc  lea     r9, aVservicingstac; "vServicingStackVersion has not been set"...
0x1802b2de3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1802b2de8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b2def  lea     rax, [rbp+40h+var_A0]
0x1802b2df3  mov     qword ptr [rbp+40h+var_98], rax
0x1802b2df7  lea     r9, asc_1802EE7AC; ": {}"
0x1802b2dfe  lea     rax, [rbp+40h+var_98]
0x1802b2e02  mov     r8d, esi
0x1802b2e05  mov     dl, r14b
0x1802b2e08  mov     qword ptr [rsp+140h+TokenType], rax; int
0x1802b2e0d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1802b2e12  mov     rcx, [rbp+48h]; this
0x1802b2e16  lea     r8, aOnecoreBaseCbs_153; "onecore\\base\\cbs\\core\\cbspublicsess"...
0x1802b2e1d  mov     r9d, edi; char *
0x1802b2e20  mov     edx, 21Ch; void *
0x1802b2e25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b2e2a  jmp     loc_1802B375D
0x1802b2e2f  lea     r8, [rbp+40h+var_98]
0x1802b2e33  mov     rcx, r15
0x1802b2e36  call    ?CreateServicingQuerier@CCbsSession@@QEAAJW4InitializeFlags@IServicingQuerier@@PEAV?$AutoComPtr@VIServicingQuerier@@@Windows@@@Z; CCbsSession::CreateServicingQuerier(IServicingQuerier::InitializeFlags,Windows::AutoComPtr<IServicingQuerier> *)
0x1802b2e3b  mov     edi, eax
0x1802b2e3d  test    eax, eax
0x1802b2e3f  jns     short loc_1802B2EBD
0x1802b2e41  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b2e48  mov     dword ptr [rbp+40h+var_A0], eax
0x1802b2e4b  test    rcx, rcx
0x1802b2e4e  jz      short loc_1802B2E90
0x1802b2e50  mov     esi, 3
0x1802b2e55  lea     r9, aFailedToCreate_85; "Failed to create servicing querier"
0x1802b2e5c  mov     r8d, esi
0x1802b2e5f  xor     edx, edx
0x1802b2e61  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1802b2e66  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b2e6d  lea     rax, [rbp+40h+var_A0]
0x1802b2e71  mov     qword ptr [rbp+40h+var_B0], rax
0x1802b2e75  lea     r9, asc_1802EE7AC; ": {}"
0x1802b2e7c  lea     rax, [rbp+40h+var_B0]
0x1802b2e80  mov     r8d, esi
0x1802b2e83  mov     dl, r14b
0x1802b2e86  mov     qword ptr [rsp+140h+TokenType], rax; int
0x1802b2e8b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1802b2e90  mov     rcx, [rbp+48h]; this
0x1802b2e94  lea     r8, aOnecoreBaseCbs_153; "onecore\\base\\cbs\\core\\cbspublicsess"...
0x1802b2e9b  mov     r9d, edi; char *
0x1802b2e9e  mov     edx, 21Fh; void *
0x1802b2ea3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b2ea8  mov     rcx, qword ptr [rbp+40h+var_98]
0x1802b2eac  test    rcx, rcx
0x1802b2eaf  jz      loc_1802B375D
0x1802b2eb5  mov     rax, [rcx]
0x1802b2eb8  jmp     loc_1802B3754
0x1802b2ebd  mov     rbx, qword ptr [rbp+40h+var_98]
0x1802b2ec1  lea     rcx, [rbp+40h+var_58]
0x1802b2ec5  mov     r8, [rbp+40h+var_A8]
0x1802b2ec9  lea     r9, aMicrosoftWindo_4; "Microsoft-Windows-ServicingStack,langua"...
0x1802b2ed0  mov     [rsp+140h+phNewToken], 0
0x1802b2ed9  mov     edx, r14d
0x1802b2edc  mov     qword ptr [rsp+140h+TokenType], rcx
0x1802b2ee1  mov     rcx, rbx
0x1802b2ee4  mov     rax, [rbx]
0x1802b2ee7  mov     rax, [rax+38h]
0x1802b2eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b2ef0  mov     edi, eax
0x1802b2ef2  test    eax, eax
0x1802b2ef4  jns     short loc_1802B2F6B
0x1802b2ef6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b2efd  mov     dword ptr [rbp+40h+var_A0], eax
0x1802b2f00  test    rcx, rcx
0x1802b2f03  jz      short loc_1802B2F4E
0x1802b2f05  lea     rax, [rbp+40h+var_A8]
0x1802b2f09  mov     esi, 3
0x1802b2f0e  mov     r8d, esi
0x1802b2f11  mov     qword ptr [rsp+140h+TokenType], rax
0x1802b2f16  lea     r9, aFailedToQueryV_0; "Failed to query version of uplevel stac"...
0x1802b2f1d  xor     edx, edx
0x1802b2f1f  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1802b2f24  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b2f2b  lea     rax, [rbp+40h+var_A0]
0x1802b2f2f  mov     qword ptr [rbp+40h+var_B0], rax
0x1802b2f33  lea     r9, asc_1802EE7AC; ": {}"
0x1802b2f3a  lea     rax, [rbp+40h+var_B0]
0x1802b2f3e  mov     r8d, esi
0x1802b2f41  mov     dl, r14b
0x1802b2f44  mov     qword ptr [rsp+140h+TokenType], rax; int
0x1802b2f49  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1802b2f4e  mov     edx, 227h; void *
0x1802b2f53  mov     rcx, [rbp+48h]; this
0x1802b2f57  lea     r8, aOnecoreBaseCbs_153; "onecore\\base\\cbs\\core\\cbspublicsess"...
0x1802b2f5e  mov     r9d, edi; char *
0x1802b2f61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b2f66  jmp     loc_1802B3749
0x1802b2f6b  mov     rax, [rbp+40h+var_58]
0x1802b2f6f  mov     ecx, r14d
0x1802b2f72  cmp     cs:?vServicingStackVersion@@3_KA, rax; unsigned __int64 vServicingStackVersion
0x1802b2f79  jb      short loc_1802B2FA5
0x1802b2f7b  lea     rdx, aUplevelStackVe; "Uplevel stack version is less than or e"...
0x1802b2f82  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1802b2f87  mov     byte ptr [rsi], 0
0x1802b2f8a  test    rbx, rbx
0x1802b2f8d  jz      short loc_1802B2F9E
0x1802b2f8f  mov     rax, [rbx]
0x1802b2f92  mov     rcx, rbx
0x1802b2f95  mov     rax, [rax+10h]
0x1802b2f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b2f9e  xor     edi, edi
0x1802b2fa0  jmp     loc_1802B375D
0x1802b2fa5  lea     r8, [rbp+40h+var_A8]
0x1802b2fa9  lea     rdx, aExecutingOpera; "Executing operation in uplevel stack: {"...
0x1802b2fb0  call    ??$TraceAtLevel@PEB_W@LogAdapter@@YAXW4LogLevel@0@QEBDAEBQEB_W@Z; LogAdapter::TraceAtLevel<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1802b2fb5  lea     rcx, [rbp+40h+var_80]
0x1802b2fb9  call    ??$AllocateWithNew@VCCbsExecutionObject@@$$V@?$AutoComPtr@VCCbsExecutionObject@@@Windows@@QEAAPEAVCCbsExecutionObject@@XZ; Windows::AutoComPtr<CCbsExecutionObject>::AllocateWithNew<CCbsExecutionObject,>(void)
0x1802b2fbe  test    rax, rax
0x1802b2fc1  jnz     short loc_1802B2FCF
0x1802b2fc3  mov     edi, 8007000Eh
0x1802b2fc8  mov     edx, 232h
0x1802b2fcd  jmp     short loc_1802B2F53
0x1802b2fcf  mov     rdx, [rbp+40h+var_80]; struct CCbsExecutionObjectBase *
0x1802b2fd3  xor     ecx, ecx; unsigned int
0x1802b2fd5  call    ?ExecutionEngineAcquireLock@@YAJKPEAVCCbsExecutionObjectBase@@@Z; ExecutionEngineAcquireLock(ulong,CCbsExecutionObjectBase *)
0x1802b2fda  mov     edi, eax
0x1802b2fdc  test    eax, eax
0x1802b2fde  jns     short loc_1802B3039
0x1802b2fe0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b2fe7  mov     dword ptr [rbp+40h+var_A0], eax
0x1802b2fea  test    rcx, rcx
0x1802b2fed  jz      short loc_1802B302F
0x1802b2fef  mov     esi, 3
0x1802b2ff4  lea     r9, aFailedAquiring; "Failed aquiring execution engine lock"
0x1802b2ffb  mov     r8d, esi
0x1802b2ffe  xor     edx, edx
0x1802b3000  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1802b3005  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b300c  lea     rax, [rbp+40h+var_A0]
0x1802b3010  mov     qword ptr [rbp+40h+var_B0], rax
0x1802b3014  lea     r9, asc_1802EE7AC; ": {}"
0x1802b301b  lea     rax, [rbp+40h+var_B0]
0x1802b301f  mov     r8d, esi
0x1802b3022  mov     dl, r14b
0x1802b3025  mov     qword ptr [rsp+140h+TokenType], rax
0x1802b302a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1802b302f  mov     edx, 236h
0x1802b3034  jmp     loc_1802B2F53
0x1802b3039  lea     rcx, [rbp+40h+var_90]
0x1802b303d  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1802b3042  lea     r9, [rbp+40h+var_58]; unsigned __int64 *
0x1802b3046  mov     qword ptr [rsp+140h+TokenType], rax; struct ICbsSession **
0x1802b304b  mov     r8, r13; wchar_t *
0x1802b304e  lea     rcx, ?vCbsOfflineUtil@@3VCbsOfflineUtil@@A; this
0x1802b3055  xor     edx, edx; int
0x1802b3057  call    ?CbsCreateSessionFromWindirWithVersion@CbsOfflineUtil@@UEAAJHQEB_WPEB_KPEAPEAUICbsSession@@@Z; CbsOfflineUtil::CbsCreateSessionFromWindirWithVersion(int,wchar_t const * const,unsigned __int64 const *,ICbsSession * *)
0x1802b305c  mov     edi, eax
0x1802b305e  test    eax, eax
0x1802b3060  jns     short loc_1802B30C4
0x1802b3062  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b3069  mov     dword ptr [rbp+40h+var_A0], eax
0x1802b306c  test    rcx, rcx
0x1802b306f  jz      short loc_1802B30BA
0x1802b3071  lea     rax, [rbp+40h+var_A8]
0x1802b3075  mov     esi, 3
0x1802b307a  mov     r8d, esi
0x1802b307d  mov     qword ptr [rsp+140h+TokenType], rax
0x1802b3082  lea     r9, aFailedToLoadUp_1; "Failed to load uplevel stack at: {}"
0x1802b3089  xor     edx, edx
0x1802b308b  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1802b3090  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b3097  lea     rax, [rbp+40h+var_A0]
0x1802b309b  mov     qword ptr [rbp+40h+var_B0], rax
0x1802b309f  lea     r9, asc_1802EE7AC; ": {}"
0x1802b30a6  lea     rax, [rbp+40h+var_B0]
0x1802b30aa  mov     r8d, esi
0x1802b30ad  mov     dl, r14b
0x1802b30b0  mov     qword ptr [rsp+140h+TokenType], rax
0x1802b30b5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1802b30ba  mov     edx, 23Ah
0x1802b30bf  jmp     loc_1802B2F53
0x1802b30c4  mov     rdi, [rbp+40h+var_90]
0x1802b30c8  lea     rax, [rbp+40h+var_78]
0x1802b30cc  mov     [rsp+140h+var_E8], rax
0x1802b30d1  lea     rcx, [rbp+40h+var_88]
0x1802b30d5  lea     rax, [rbp+40h+var_70]
0x1802b30d9  mov     [rsp+140h+var_F0], r14b
0x1802b30de  mov     [rsp+140h+var_E0], rax
0x1802b30e3  lea     rax, [rbp+40h+var_68]
0x1802b30e7  mov     [rsp+140h+var_D8], rax
0x1802b30ec  lea     rax, [rbp+40h+var_88]
0x1802b30f0  mov     [rsp+140h+var_D0], rax
0x1802b30f5  lea     rax, [rbp+40h+var_60]
0x1802b30f9  mov     [rsp+140h+var_C8], rax
0x1802b30fe  lea     rax, [rbp+40h+var_90]
0x1802b3102  mov     [rbp+40h+var_C0], rax
0x1802b3106  lea     rax, [rbp+40h+var_80]
0x1802b310a  mov     [rbp+40h+var_B8], rax
0x1802b310e  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1802b3113  mov     rcx, [rdi]
0x1802b3116  lea     rdx, _GUID_fb3b7670_d62d_4943_8e9f_a7de7f88f63b
0x1802b311d  mov     r8, rax
0x1802b3120  mov     r9, [rcx]
0x1802b3123  mov     rcx, rdi
0x1802b3126  mov     rax, r9
0x1802b3129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b312e  mov     edi, eax
0x1802b3130  test    eax, eax
0x1802b3132  jns     short loc_1802B318D
0x1802b3134  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b313b  mov     dword ptr [rbp+40h+var_A0], eax
0x1802b313e  test    rcx, rcx
0x1802b3141  jz      short loc_1802B3183
0x1802b3143  mov     esi, 3
0x1802b3148  lea     r9, aFailedToQueryP; "Failed to query private session interfa"...
0x1802b314f  mov     r8d, esi
0x1802b3152  xor     edx, edx
0x1802b3154  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1802b3159  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802b3160  lea     rax, [rbp+40h+var_A0]
0x1802b3164  mov     qword ptr [rbp+40h+var_B0], rax
0x1802b3168  lea     r9, asc_1802EE7AC; ": {}"
0x1802b316f  lea     rax, [rbp+40h+var_B0]
0x1802b3173  mov     r8d, esi
0x1802b3176  mov     dl, r14b
0x1802b3179  mov     qword ptr [rsp+140h+TokenType], rax
0x1802b317e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1802b3183  mov     edx, 24Ch
0x1802b3188  jmp     loc_1802B372C
0x1802b318d  mov     rcx, [rbp+40h+var_88]
0x1802b3191  mov     rax, [rcx]
0x1802b3194  mov     rax, [rax+0D8h]
0x1802b319b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b31a0  mov     rcx, [rbp+40h+var_88]
0x1802b31a4  mov     rax, [rcx]
0x1802b31a7  mov     rax, [rax+0E0h]
0x1802b31ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b31b3  mov     rdi, [rbp+40h+var_90]
0x1802b31b7  lea     rcx, [rbp+40h+var_68]
0x1802b31bb  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1802b31c0  mov     rcx, [rdi]
0x1802b31c3  lea     rdx, _GUID_a3397718_7938_4776_bcac_0c92ccc3ece7
0x1802b31ca  mov     r8, rax
0x1802b31cd  mov     r9, [rcx]
0x1802b31d0  mov     rcx, rdi
0x1802b31d3  mov     rax, r9
0x1802b31d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b31db  mov     edi, eax
0x1802b31dd  cmp     eax, 80004002h
0x1802b31e2  jnz     loc_1802B3283
0x1802b31e8  lea     rdx, aPrivateSession; "Private session 3 interface is not supp"...
0x1802b31ef  mov     ecx, r14d
0x1802b31f2  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
  ... truncated ...
```
