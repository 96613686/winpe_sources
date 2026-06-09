# OnepackageCheckApplicabilityFromSandbox(ICbsSession *,AutoThreadPriority::PriorityType,bool,wchar_t const *,wchar_t const *,bool *,bool *)

- ea: `0x18020c63c`
- end: `0x18020dc46`
- name: `?OnepackageCheckApplicabilityFromSandbox@@YAJPEAUICbsSession@@W4PriorityType@AutoThreadPriority@@_NPEB_W3PEA_N4@Z`
- size: `5642`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006ba9c`

## callees

- `0x180010cc0`
- `0x180011a14`
- `0x180012fe4`
- `0x180013250`
- `0x180015420`
- `0x180019bdc`
- `0x180023ca8`
- `0x1800261e0`
- `0x18002a448`
- `0x18004bca8`
- `0x180059a00`
- `0x18005a548`
- `0x18005aa38`
- `0x18005dd58`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800ad1f0`
- `0x1800ae508`
- `0x1800bd218`
- `0x1800c19b0`
- `0x1800d0588`
- `0x1800eb920`
- `0x1800ec920`
- `0x1800ef360`
- `0x1800fa3ec`
- `0x18020babc`
- `0x18020c63c`
- `0x18020ed08`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18020ce01`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18020ce01`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18020d36c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18020d452`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18020dc2a`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18020d36c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18020d452`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18020dc2a`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18020cdcd`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18020cdcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020cc0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020dae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020cc0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020dae3`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18020c94b`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18020c94b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x18020caae`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x18020caae`

## string_xrefs

- `0x18020c989`: `updateagent.dll`
- `0x18020c944`: `UPDATE_AGENT_OVERRIDE_DLL_PATH`
- `0x18020d799`: `update.mum`
- `0x18020d1fa`: `actionlist.xml`
- `0x18020d117`: `Failed to convert thread priority to update session priority.`
- `0x18020cdf7`: `CreateOfflineDeploymentSession`
- `0x18020cb0f`: `Failed to validate signature of Updateagent dll.`
- `0x18020da96`: `No express package path found for LCU`
- `0x18020d818`: `Failed opening package {}`
- `0x18020c803`: `No installed result specified`
- `0x18020d15f`: `UpdatePriority`
- `0x18020cc2f`: `Failed to copy aggregatedmetadata file to sandbox`
- `0x18020db02`: `Failed to load update agent DLL`
- `0x18020c741`: `No sandbox path specified`

## pseudocode

```c
__int64 __fastcall OnepackageCheckApplicabilityFromSandbox(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _BYTE *a6,
        bool *a7)
{
  __int64 v7; // r12
  __int64 v10; // rdi
  int v11; // ebx
  int v12; // edx
  __int64 v13; // rdx
  int v14; // edx
  int v15; // edx
  unsigned __int64 v16; // r9
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rcx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  int v23; // eax
  __int64 v24; // rdx
  int v25; // edx
  unsigned __int64 v26; // rsi
  unsigned __int64 v27; // r14
  __int64 v28; // r12
  int v29; // eax
  int v30; // eax
  int v31; // edx
  signed int v33; // ebx
  int v34; // edx
  unsigned int v35; // eax
  __int64 v36; // rdx
  HMODULE Library; // rax
  HMODULE v38; // r14
  FARPROC ProcAddress; // rax
  int v40; // eax
  int v41; // edx
  __int64 v42; // rdx
  __int64 (__fastcall ***v43)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v44)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 (__fastcall *v45)(_QWORD, GUID *, __int64); // rbx
  __int64 InitPointer; // rax
  int v47; // eax
  int v48; // eax
  int v49; // edx
  __int64 (__fastcall ***v50)(_QWORD, _QWORD, _QWORD); // rcx
  int updated; // eax
  int v52; // edx
  int v53; // eax
  int v54; // edx
  HMODULE v55; // rbx
  int v56; // eax
  unsigned int v57; // esi
  int v58; // edx
  __int64 (__fastcall ***v59)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v60; // rdx
  bool *v61; // r12
  int v62; // ecx
  __int64 v63; // r8
  __int64 i; // rax
  int v65; // eax
  int v66; // edx
  __int64 v67; // rdx
  int v68; // eax
  void (*v69)(void); // rax
  void (*v70)(void); // rax
  __int64 v71; // rdx
  __int64 (__fastcall *v72)(__int64, _QWORD, __int64, __int64); // rsi
  __int64 v73; // rbx
  int v74; // eax
  int v75; // edx
  __int64 v76; // rdx
  HMODULE v77; // rdi
  __int64 v78; // rax
  int v79; // eax
  int v80; // edx
  int v81; // eax
  int v82; // edx
  bool v83; // zf
  int v84; // edx
  signed int LastError; // ebx
  int v86; // edx
  unsigned int v87; // eax
  unsigned int v88; // [rsp+20h] [rbp-E0h]
  HMODULE *v89; // [rsp+20h] [rbp-E0h]
  int v90; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpExistingFileName; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpNewFileName; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v93; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpLibFileName; // [rsp+68h] [rbp-98h] BYREF
  __int64 v95; // [rsp+70h] [rbp-90h] BYREF
  HMODULE v96; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v97[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v98; // [rsp+88h] [rbp-78h] BYREF
  __int128 v99; // [rsp+90h] [rbp-70h] BYREF
  __int64 v100; // [rsp+A0h] [rbp-60h]
  int v101[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v102; // [rsp+B0h] [rbp-50h] BYREF
  const wchar_t *v103; // [rsp+C0h] [rbp-40h] BYREF
  int v104; // [rsp+100h] [rbp+0h]
  __int64 (__fastcall ***v105)(_QWORD, GUID *, __int64); // [rsp+130h] [rbp+30h]
  __int64 v106; // [rsp+138h] [rbp+38h] BYREF
  __int64 v107; // [rsp+140h] [rbp+40h] BYREF
  unsigned int v108; // [rsp+148h] [rbp+48h] BYREF
  int v109; // [rsp+14Ch] [rbp+4Ch] BYREF
  __int64 v110; // [rsp+150h] [rbp+50h] BYREF
  HMODULE hModule[2]; // [rsp+160h] [rbp+60h] BYREF
  int v112; // [rsp+170h] [rbp+70h] BYREF
  _QWORD v113[3]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v114[24]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int64 v115; // [rsp+1A8h] [rbp+A8h]
  __int64 v116; // [rsp+1B8h] [rbp+B8h]
  __int128 v117; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v118; // [rsp+1E0h] [rbp+E0h]
  int v119; // [rsp+1E8h] [rbp+E8h] BYREF
  WCHAR Buffer[264]; // [rsp+1F0h] [rbp+F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+448h] [rbp+348h]

  v7 = a5;
  v100 = 0;
  v108 = a2;
  v98 = a5;
  *(_QWORD *)v97 = a6;
  hModule[0] = 0;
  v95 = 0;
  lpLibFileName = 0;
  v96 = 0;
  v99 = 0;
  v102 = 0;
  v113[1] = 0;
  v113[0] = &Windows::Rtl::PrivateHeapPool::`vftable';
  v113[2] = 0;
  memset_0(&v103, 0, 0x68u);
  v105 = 0;
  v107 = 0;
  v106 = 0;
  CCbsStringArray::CCbsStringArray((CCbsStringArray *)v114);
  lpExistingFileName = 0;
  lpNewFileName = 0;
  v93 = 0;
  v10 = 0;
  memset_0(Buffer, 0, 0x208u);
  if ( !a4 )
  {
    v11 = -2147024809;
    v108 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No sandbox path specified");
      hModule[0] = (HMODULE)&v108;
      LOBYTE(v12) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v12,
        3,
        (unsigned int)": {}",
        (__int64)hModule);
    }
    v13 = 215;
LABEL_13:
    v16 = (unsigned int)v11;
    goto LABEL_14;
  }
  if ( !a6 )
  {
    v11 = -2147467261;
    v108 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No applicability result specified");
      hModule[0] = (HMODULE)&v108;
      LOBYTE(v14) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v14,
        3,
        (unsigned int)": {}",
        (__int64)hModule);
    }
    v13 = 216;
    goto LABEL_13;
  }
  if ( !a7 )
  {
    v11 = -2147467261;
    v108 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No installed result specified");
      hModule[0] = (HMODULE)&v108;
      LOBYTE(v15) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v15,
        3,
        (unsigned int)": {}",
        (__int64)hModule);
    }
    v13 = 217;
    goto LABEL_13;
  }
  if ( a1 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    v10 = a1;
    v93 = a1;
  }
  *a6 = 0;
  *a7 = 0;
  v18 = SczAllocFromSzAndEnsureBackslash(&v95, a4);
  v11 = v18;
  if ( v18 < 0 )
  {
    v16 = (unsigned int)v18;
    v13 = 228;
    goto LABEL_14;
  }
  v19 = SczAllocConcatSz(&v95, L"metadata\\");
  v11 = v19;
  if ( v19 < 0 )
  {
    v16 = (unsigned int)v19;
    v13 = 229;
    goto LABEL_14;
  }
  if ( GetEnvironmentVariableW(L"UPDATE_AGENT_OVERRIDE_DLL_PATH", Buffer, 0x104u) - 1 > 0x102 )
  {
    v22 = SczAllocCombinePath2Sz(&lpLibFileName, v95, L"updateagent.dll");
    v11 = v22;
    if ( v22 < 0 )
    {
      v16 = (unsigned int)v22;
      v13 = 240;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\base\\cbs\\onepackage\\lib\\cbsonepackage.cpp",
        (const char *)v16,
        v88);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v93);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v114);
      if ( v106 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
        v106 = 0;
      }
      if ( v107 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
        v107 = 0;
      }
      v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v105;
      if ( !v105 )
        goto LABEL_57;
      goto LABEL_56;
    }
  }
  else
  {
    v20 = SczAllocFromSz(&lpLibFileName, Buffer);
    v11 = v20;
    if ( v20 < 0 )
    {
      v16 = (unsigned int)v20;
      v13 = 236;
      goto LABEL_14;
    }
  }
  v23 = CbsEnumFiles(v21, a4, L"*.aggregatedmetadata.cab", v114);
  v11 = v23;
  if ( v23 < 0 )
  {
    v108 = v23;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed getting the aggregatedmetadata files.");
      hModule[0] = (HMODULE)&v108;
      LOBYTE(v25) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v25,
        3,
        (unsigned int)": {}",
        (__int64)hModule);
    }
    v13 = 246;
    goto LABEL_13;
  }
  v26 = 0;
  v27 = v115;
  if ( !v115 )
  {
LABEL_47:
    LOBYTE(v24) = v7 == 0;
    v30 = CbsVerifyFileSignature(lpLibFileName, v24);
    v11 = v30;
    if ( v30 < 0 )
    {
      v108 = v30;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to validate signature of Updateagent dll.");
        hModule[0] = (HMODULE)&v108;
        LOBYTE(v31) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v31,
          3,
          (unsigned int)": {}",
          (__int64)hModule);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10D,
        (unsigned int)"onecore\\base\\cbs\\onepackage\\lib\\cbsonepackage.cpp",
        (const char *)(unsigned int)v11,
        v88);
LABEL_51:
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v93);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v114);
      if ( v106 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
        v106 = 0;
      }
      if ( v107 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
        v107 = 0;
      }
      v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v105;
      if ( !v105 )
        goto LABEL_57;
LABEL_56:
      ((void (__fastcall *)(_QWORD))(*v105)[2])(v17);
      v105 = 0;
      goto LABEL_57;
    }
    Library = LoadLibraryExW(lpLibFileName, 0, 8u);
    Windows::Rtl::AutoHandleBase<Windows::Rtl::AutoHModuleTraits,Windows::Rtl::AutoHModule>::TakeOwnership(
      hModule,
      Library);
    v38 = hModule[0];
    if ( (unsigned __int64)hModule[0] - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to load update agent DLL");
        if ( LastError > 0 )
          v87 = (unsigned __int16)LastError | 0x80070000;
        else
          v87 = LastError;
        v109 = v87;
        LOBYTE(v86) = 1;
        *(_QWORD *)v97 = &v109;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v86,
          3,
          (unsigned int)": {0}",
          (__int64)v97);
      }
      if ( !LastError )
        goto LABEL_135;
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x118,
              (unsigned int)"onecore\\base\\cbs\\onepackage\\lib\\cbsonepackage.cpp",
              (const char *)(unsigned int)LastError,
              v88);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v93);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v114);
      if ( !v106 )
      {
LABEL_223:
        if ( v107 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
          v107 = 0;
        }
        v43 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v105;
        if ( !v105 )
          goto LABEL_227;
LABEL_226:
        ((void (__fastcall *)(_QWORD))(*v105)[2])(v43);
        v105 = 0;
        goto LABEL_227;
      }
      v70 = *(void (**)(void))(*(_QWORD *)v106 + 16LL);
LABEL_222:
      v70();
      v106 = 0;
      goto LABEL_223;
    }
    ProcAddress = GetProcAddress(hModule[0], "CreateOfflineDeploymentSession");
    v104 = 32;
    v103 = L"{\"ModuleID\":\"LocalServicing\"}";
    if ( v105 )
      goto LABEL_229;
    v89 = hModule;
    *(GUID *)hModule = GUID_NULL;
    v40 = ((__int64 (__fastcall *)(__int64, __int64, __int64))ProcAddress)(1, a4, v7);
    v11 = v40;
    if ( v40 < 0 )
    {
      v108 = v40;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Creation of deployment session failed.");
        hModule[0] = (HMODULE)&v108;
        LOBYTE(v41) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v41,
          3,
          (unsigned int)": {}",
          (__int64)hModule);
      }
      v42 = 300;
      goto LABEL_88;
    }
    v44 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v105;
    v45 = **v105;
    InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v107);
    v47 = v45(v44, &GUID_57816c47_d685_423a_89c6_feefbd90ed47, InitPointer);
    if ( v47 < 0 )
    {
      LogAdapter::TraceAtLevelHr<long,>(
        1,
        (unsigned int)v47,
        "Unable to query for IDeploymentSession8. Continuing with default priorities.");
      goto LABEL_96;
    }
    v112 = 0;
    updated = ThreadPriorityToUpdateSessionPriority(v108, &v112);
    v11 = updated;
    if ( updated >= 0 )
    {
      v53 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)v107 + 168LL))(
              v107,
              0,
              L"UpdatePriority",
              v112);
      v11 = v53;
      if ( v53 >= 0 )
      {
LABEL_96:
        if ( !v106 )
        {
          v48 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), __int64 *))(*v105)[4])(
                  v105,
                  &v106);
          v11 = 0;
          if ( v48 != -1047526399 )
            v11 = v48;
          if ( v11 < 0 )
          {
            v108 = v11;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed getting the download request.");
              hModule[0] = (HMODULE)&v108;
              LOBYTE(v49) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v49,
                3,
                (unsigned int)": {}",
                (__int64)hModule);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x147,
              (unsigned int)"onecore\\base\\cbs\\onepackage\\lib\\cbsonepackage.cpp",
              (const char *)(unsigned int)v11,
              (int)v89);
            Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v93);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
            CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v114);
            if ( v106 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
              v106 = 0;
            }
            if ( v107 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
              v107 = 0;
            }
            v50 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v105;
            if ( !v105 )
              goto LABEL_227;
            goto LABEL_107;
          }
          v11 = SczAllocFromSzAndEnsureBackslash(&v96, a4);
          if ( v11 < 0 )
          {
            v42 = 329;
            goto LABEL_88;
          }
          v11 = SczAllocConcatSz(&v96, L"actionlist.xml");
          if ( v11 < 0 )
          {
            v42 = 330;
            goto LABEL_88;
          }
          v55 = v96;
          v56 = ActionListParser::ReadActionList(v96, v113, &v102, &v99);
          v57 = v56;
          if ( v56 < 0 )
          {
            v119 = v56;
            if ( LogAdapter::g_Logger )
            {
              hModule[0] = v55;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to load actions from {}",
                (__int64)hModule);
              *(_QWORD *)v97 = &v119;
              LOBYTE(v58) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v58,
                3,
                (unsigned int)": {}",
                (__int64)v97);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x14F,
              (unsigned int)"onecore\\base\\cbs\\onepackage\\lib\\cbsonepackage.cpp",
              (const char *)v57,
              (int)v89);
            Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v93);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
            CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v114);
            if ( v106 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
              v106 = 0;
            }
            if ( v107 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
              v107 = 0;
            }
            v59 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v105;
            if ( !v105 )
              goto LABEL_130;
            goto LABEL_129;
          }
          v60 = v102;
          v61 = *(bool **)v97;
          v62 = *(_DWORD *)(v102 + 80);
          **(_BYTE **)v97 = v62 != 0;
          if ( !v62 )
            goto LABEL_134;
          v63 = 0;
          for ( i = *(_QWORD *)(*(_QWORD *)(v60 + 152) + 56LL); i; i = *(_QWORD *)(i + 296) )
          {
            if ( *(_DWORD *)(i + 140) != 2
              && *(_DWORD *)(i + 140) != 3
              && *(_DWORD *)(i + 140) != 4
              && *(_DWORD *)(i + 140) != 5 )
            {
              if ( *(_DWORD *)(i + 140) == 6 )
              {
                v63 = i;
              }
              else if ( *(_DWORD *)(i + 140) != 7 && *(_DWORD *)(i + 140) != 9 && *(_DWORD *)(i + 140) != 13 )
              {
                goto LABEL_134;
              }
            }
          }
          if ( !v63 )
          {
            *a7 = 1;
            goto LABEL_135;
          }
          if ( !v10 )
          {
LABEL_134:
            *a7 = 0;
LABEL_135:
            Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v93);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
            CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v114);
            if ( v106 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
              v106 = 0;
            }
            if ( v107 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
              v107 = 0;
            }
            if ( v105 )
            {
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v105)[2])(v105);
              v105 = 0;
            }
            Windows::Rtl::PrivateHeapPool::~PrivateHeapPool((Windows::Rtl::PrivateHeapPool *)v113);
            Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v99);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v96);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v95);
            if ( (unsigned __int64)v38 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
              FreeLibrary(v38);
            return 0;
          }
          hModule[0] = 0;
          v118 = 0;
          v65 = *(_DWORD *)(v63 + 140);
          v110 = 0;
          v98 = 0;
          v112 = 0;
          v108 = 0;
          v117 = 0;
          if ( v65 != 6 )
          {
            v11 = -2146498221;
            v109 = -2146498221;
            if ( LogAdapter::g_Logger )
            {
              v101[0] = v65;
              LogAdapter::Logger::LogNumObjects<long>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Unexpected package reason {}",
                (__int64)v101);
              *(_QWORD *)v97 = &v109;
              LOBYTE(v66) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v66,
                3,
                (unsigned int)": {}",
                (__int64)v97);
            }
            v67 = 393;
            goto LABEL_163;
          }
          if ( !*(_BYTE *)(v63 + 307) || !*(_QWORD *)(v63 + 88) )
          {
            v11 = -2146498222;
            v109 = -2146498222;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No express package path found for LCU");
              *(_QWORD *)v97 = &v109;
              LOBYTE(v84) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v84,
                3,
                (unsigned int)": {}",
                (__int64)v97);
            }
            v67 = 397;
LABEL_163:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v67,
              (unsigned int)"onecore\\base\\cbs\\onepackage\\lib\\cbsonepackage.cpp",
              (const char *)(unsigned int)v11,
              (int)v89);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v98);
            Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v117);
            if ( v110 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
              v110 = 0;
            }
            Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(hModule);
            Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v93);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
            CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v114);
            if ( v106 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
              v106 = 0;
            }
            if ( v107 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
              v107 = 0;
            }
            v50 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v105;
            if ( !v105 )
              goto LABEL_227;
LABEL_107:
            ((void (__fastcall *)(_QWORD))(*v105)[2])(v50);
            v105 = 0;
LABEL_227:
            Windows::Rtl::PrivateHeapPool::~PrivateHeapPool((Windows::Rtl::PrivateHeapPool *)v113);
            Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v99);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v96);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v95);
            if ( (unsigned __int64)v38 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
              FreeLibrary(v38);
            return (unsigned int)v11;
          }
          *(_QWORD *)v97 = &v117;
          v68 = Windows::StringUtil::Rtl::DuplicateToNullTerminatedString<_LUTF8_STRING,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>>(
                  v63 + 88,
                  v97);
          if ( v68 >= 0 )
          {
            v11 = SczAllocCombinePath2Sz(&v98, a4, v118);
            if ( v11 >= 0 )
            {
              v11 = SczEnsureBackslashTerminated(&v98);
              if ( v11 >= 0 )
              {
                v11 = SczAllocConcatSz(&v98, L"update.mum");
                if ( v11 >= 0 )
                {
                  v72 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v10 + 40LL);
                  Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(hModule);
                  v73 = v98;
                  v90 = a4;
                  v74 = v72(v10, 0, 4, v98);
                  v57 = v74;
                  if ( v74 >= 0 )
                  {
                    v77 = hModule[0];
                    v78 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v110);
                    v79 = (**(__int64 (__fastcall ***)(HMODULE, GUID *, __int64))v77)(
                            v77,
                            &GUID_75207393_23f2_4396_85f0_8fdb879ed0ed,
                            v78);
                    v57 = v79;
                    if ( v79 >= 0 )
                    {
                      v81 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, unsigned int *))(*(_QWORD *)v110 + 80LL))(
                              v110,
                              0,
                              &v112,
                              &v108);
                      v57 = v81;
                      if ( v81 >= 0 )
                      {
                        v83 = v108 == 7;
                        *v61 = v112 == 7;
                        *a7 = v83;
                        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v98);
                        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v117);
                        if ( v110 )
                        {
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
                          v110 = 0;
                        }
                        Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(hModule);
                        goto LABEL_135;
                      }
                      v109 = v81;
                      if ( LogAdapter::g_Logger )
                      {
                        *(_QWORD *)v97 = v73;
                        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                          (_DWORD)LogAdapter::g_Logger,
                          0,
                          3,
                          (unsigned int)"Failed to determine package applicability and current state for package {}",
                          (__int64)v97);
                        *(_QWORD *)v101 = &v109;
                        LOBYTE(v82) = 1;
                        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                          (_DWORD)LogAdapter::g_Logger,
                          v82,
                          3,
                          (unsigned int)": {}",
                          (__int64)v101);
                      }
                      v76 = 424;
                    }
                    else
                    {
                      v109 = v79;
                      if ( LogAdapter::g_Logger )
                      {
                        LogAdapter::Logger::LogNumObjects<>(
                          LogAdapter::g_Logger,
                          0,
                          3,
                          "Failed to QI for ICbsPackage interface.");
                        *(_QWORD *)v97 = &v109;
                        LOBYTE(v80) = 1;
                        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                          (_DWORD)LogAdapter::g_Logger,
                          v80,
                          3,
                          (unsigned int)": {}",
                          (__int64)v97);
                      }
                      v76 = 420;
                    }
                  }
                  else
                  {
                    v109 = v74;
                    if ( LogAdapter::g_Logger )
                    {
                      *(_QWORD *)v97 = v73;
                      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                        (_DWORD)LogAdapter::g_Logger,
                        0,
                        3,
                        (unsigned int)"Failed opening package {}",
                        (__int64)v97);
                      *(_QWORD *)v101 = &v109;
                      LOBYTE(v75) = 1;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        (_DWORD)LogAdapter::g_Logger,
                        v75,
                        3,
                        (unsigned int)": {}",
                        (__int64)v101);
                    }
                    v76 = 417;
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v76,
                    (unsigned int)"onecore\\base\\cbs\\onepackage\\lib\\cbsonepackage.cpp",
                    (const char *)v57,
                    v90);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v98);
                  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v117);
                  if ( v110 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
                    v110 = 0;
                  }
                  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(hModule);
                  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v93);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
                  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v114);
                  if ( v106 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
                    v106 = 0;
                  }
                  if ( v107 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
                    v107 = 0;
                  }
                  v59 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v105;
                  if ( !v105 )
                    goto LABEL_130;
LABEL_129:
                  ((void (__fastcall *)(_QWORD))(*v105)[2])(v59);
                  v105 = 0;
LABEL_130:
                  Windows::Rtl::PrivateHeapPool::~PrivateHeapPool((Windows::Rtl::PrivateHeapPool *)v113);
                  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v99);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v96);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v95);
                  if ( (unsigned __int64)v38 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
                    FreeLibrary(v38);
                  return v57;
                }
                v71 = 408;
              }
              else
              {
                v71 = 407;
              }
            }
            else
            {
              v71 = 406;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v71,
              (unsigned int)"onecore\\base\\cbs\\onepackage\\lib\\cbsonepackage.cpp",
              (const char *)(unsigned int)v11,
              (int)hModule);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v98);
            Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v117);
            if ( !v110 )
              goto LABEL_177;
            v69 = *(void (**)(void))(*(_QWORD *)v110 + 16LL);
          }
          else
          {
            v11 = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x193,
                    (unsigned int)"onecore\\base\\cbs\\onepackage\\lib\\cbsonepackage.cpp",
                    (const char *)(unsigned int)v68,
                    (int)hModule);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v98);
            Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v117);
            if ( !v110 )
            {
LABEL_177:
              Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(hModule);
              Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v93);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v114);
              if ( !v106 )
                goto LABEL_223;
              v70 = *(void (**)(void))(*(_QWORD *)v106 + 16LL);
              goto LABEL_222;
            }
            v69 = *(void (**)(void))(*(_QWORD *)v110 + 16LL);
          }
          v69();
          v110 = 0;
          goto LABEL_177;
        }
LABEL_229:
        INTERNAL_ERROR_ACTION(-1073741595);
        JUMPOUT(0x18020DC45LL);
      }
      v108 = v53;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to set priority on deployment session.");
        hModule[0] = (HMODULE)&v108;
        LOBYTE(v54) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v54,
          3,
          (unsigned int)": {}",
          (__int64)hModule);
      }
      v42 = 318;
    }
    else
    {
      v108 = updated;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to convert thread priority to update session priority.");
        hModule[0] = (HMODULE)&v108;
        LOBYTE(v52) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v52,
          3,
          (unsigned int)": {}",
          (__int64)hModule);
      }
      v42 = 314;
    }
LABEL_88:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v42,
      (unsigned int)"onecore\\base\\cbs\\onepackage\\lib\\cbsonepackage.cpp",
      (const char *)(unsigned int)v11,
      (int)v89);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v93);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v114);
    if ( v106 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
      v106 = 0;
    }
    if ( v107 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
      v107 = 0;
    }
    v43 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v105;
    if ( !v105 )
      goto LABEL_227;
    goto LABEL_226;
  }
  v28 = v116;
  while ( 1 )
  {
    v29 = SczAllocFromSzAndEnsureBackslash(&lpExistingFileName, a4);
    v11 = v29;
    if ( v29 < 0 )
    {
      v36 = 250;
LABEL_76:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v36,
        (unsigned int)"onecore\\base\\cbs\\onepackage\\lib\\cbsonepackage.cpp",
        (const char *)(unsigned int)v29,
        v88);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v93);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v114);
      if ( v106 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
        v106 = 0;
      }
      if ( v107 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
        v107 = 0;
      }
      v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v105;
      if ( !v105 )
        goto LABEL_57;
      goto LABEL_56;
    }
    if ( v26 >= v27 )
      __fastfail(8u);
    v29 = SczAllocConcatSz(&lpExistingFileName, *(_QWORD *)(v28 + 8 * v26));
    v11 = v29;
    if ( v29 < 0 )
    {
      v36 = 251;
      goto LABEL_76;
    }
    if ( v26 >= v27 )
      __fastfail(8u);
    v29 = SczAllocFormatted(&lpNewFileName, L"%ws%ws", v95, *(_QWORD *)(v28 + 8 * v26));
    v11 = v29;
    if ( v29 < 0 )
    {
      v36 = 252;
      goto LABEL_76;
    }
    if ( !CopyFileW(lpExistingFileName, lpNewFileName, 0) )
      break;
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
    if ( ++v26 >= v27 )
    {
      v7 = v98;
      goto LABEL_47;
    }
  }
  v33 = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to copy aggregatedmetadata file to sandbox");
    if ( v33 > 0 )
      v35 = (unsigned __int16)v33 | 0x80070000;
    else
      v35 = v33;
    v108 = v35;
    LOBYTE(v34) = 1;
    hModule[0] = (HMODULE)&v108;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v34,
      3,
      (unsigned int)": {0}",
      (__int64)hModule);
  }
  if ( v33 )
  {
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xFF,
            (unsigned int)"onecore\\base\\cbs\\onepackage\\lib\\cbsonepackage.cpp",
            (const char *)(unsigned int)v33,
            v88);
    goto LABEL_51;
  }
  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v93);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v114);
  if ( v106 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
    v106 = 0;
  }
  if ( v107 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
    v107 = 0;
  }
  if ( v105 )
  {
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v105)[2])(v105);
    v105 = 0;
  }
  v11 = 0;
LABEL_57:
  Windows::Rtl::PrivateHeapPool::~PrivateHeapPool((Windows::Rtl::PrivateHeapPool *)v113);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v99);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v96);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v95);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18020c63c  mov     [rsp-8+arg_8], rbx
0x18020c641  push    rbp
0x18020c642  push    rsi
0x18020c643  push    rdi
0x18020c644  push    r12
0x18020c646  push    r13
0x18020c648  push    r14
0x18020c64a  push    r15
0x18020c64c  lea     rbp, [rsp-310h]
0x18020c654  sub     rsp, 410h
0x18020c65b  mov     rax, cs:__security_cookie
0x18020c662  xor     rax, rsp
0x18020c665  mov     [rbp+340h+var_40], rax
0x18020c66c  mov     r12, [rbp+340h+arg_20]
0x18020c673  xor     r14d, r14d
0x18020c676  mov     rsi, [rbp+340h+arg_28]
0x18020c67d  xor     eax, eax
0x18020c67f  mov     r15, [rbp+340h+arg_30]
0x18020c686  mov     rbx, rcx
0x18020c689  mov     [rbp+340h+var_3A0], rax
0x18020c68d  lea     rcx, [rbp+340h+var_380]; void *
0x18020c691  mov     [rbp+340h+var_2F8], edx
0x18020c694  lea     rax, ??_7PrivateHeapPool@Rtl@Windows@@6B@; const Windows::Rtl::PrivateHeapPool::`vftable'
0x18020c69b  xorps   xmm0, xmm0
0x18020c69e  mov     [rbp+340h+var_3B8], r12
0x18020c6a2  lea     r8d, [r14+68h]; Size
0x18020c6a6  mov     qword ptr [rbp+340h+var_3C0], rsi
0x18020c6aa  xor     edx, edx; Val
0x18020c6ac  mov     [rbp+340h+hModule], r14
0x18020c6b0  mov     r13, r9
0x18020c6b3  mov     [rsp+440h+var_3D0], r14
0x18020c6b8  mov     [rsp+440h+lpLibFileName], r14
0x18020c6bd  mov     [rsp+440h+var_3C8], r14
0x18020c6c2  movups  [rbp+340h+var_3B0], xmm0
0x18020c6c6  mov     [rbp+340h+var_390], r14
0x18020c6ca  mov     [rbp+340h+var_2C0], r14
0x18020c6d1  mov     [rbp+340h+var_2C8], rax
0x18020c6d5  mov     [rbp+340h+var_2B8], r14
0x18020c6dc  call    memset_0
0x18020c6e1  lea     rcx, [rbp+340h+var_2B0]; this
0x18020c6e8  mov     [rbp+340h+var_310], r14
0x18020c6ec  mov     [rbp+340h+var_300], r14
0x18020c6f0  mov     [rbp+340h+var_308], r14
0x18020c6f4  call    ??0CCbsStringArray@@QEAA@XZ; CCbsStringArray::CCbsStringArray(void)
0x18020c6f9  xor     edx, edx; Val
0x18020c6fb  mov     [rsp+440h+lpExistingFileName], r14
0x18020c700  mov     r8d, 208h; Size
0x18020c706  mov     [rsp+440h+lpNewFileName], r14
0x18020c70b  lea     rcx, [rbp+340h+Buffer]; void *
0x18020c712  mov     [rsp+440h+var_3E0], r14
0x18020c717  mov     edi, r14d
0x18020c71a  call    memset_0
0x18020c71f  test    r13, r13
0x18020c722  jnz     short loc_18020C780
0x18020c724  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18020c72b  mov     ebx, 80070057h
0x18020c730  mov     [rbp+340h+var_2F8], ebx
0x18020c733  test    rcx, rcx
0x18020c736  jz      short loc_18020C776
0x18020c738  lea     edi, [r14+3]
0x18020c73c  xor     edx, edx
0x18020c73e  mov     r8d, edi
0x18020c741  lea     r9, aNoSandboxPathS; "No sandbox path specified"
0x18020c748  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18020c74d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18020c754  lea     rax, [rbp+340h+var_2F8]
0x18020c758  mov     [rbp+340h+hModule], rax
0x18020c75c  lea     r9, asc_1802EE7AC; ": {}"
0x18020c763  lea     rax, [rbp+340h+hModule]
0x18020c767  mov     r8d, edi
0x18020c76a  mov     dl, 1
0x18020c76c  mov     qword ptr [rsp+440h+var_420], rax
0x18020c771  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18020c776  mov     edx, 0D7h
0x18020c77b  jmp     loc_18020C83D
0x18020c780  test    rsi, rsi
0x18020c783  jnz     short loc_18020C7DD
0x18020c785  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18020c78c  mov     ebx, 80004003h
0x18020c791  mov     [rbp+340h+var_2F8], ebx
0x18020c794  test    rcx, rcx
0x18020c797  jz      short loc_18020C7D6
0x18020c799  lea     edi, [rsi+3]
0x18020c79c  xor     edx, edx
0x18020c79e  mov     r8d, edi
0x18020c7a1  lea     r9, aNoApplicabilit_0; "No applicability result specified"
0x18020c7a8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18020c7ad  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18020c7b4  lea     rax, [rbp+340h+var_2F8]
0x18020c7b8  mov     [rbp+340h+hModule], rax
0x18020c7bc  lea     r9, asc_1802EE7AC; ": {}"
0x18020c7c3  lea     rax, [rbp+340h+hModule]
0x18020c7c7  mov     r8d, edi
0x18020c7ca  mov     dl, 1
0x18020c7cc  mov     qword ptr [rsp+440h+var_420], rax
0x18020c7d1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18020c7d6  mov     edx, 0D8h
0x18020c7db  jmp     short loc_18020C83D
0x18020c7dd  test    r15, r15
0x18020c7e0  jnz     loc_18020C8D1
0x18020c7e6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18020c7ed  mov     ebx, 80004003h
0x18020c7f2  mov     [rbp+340h+var_2F8], ebx
0x18020c7f5  test    rcx, rcx
0x18020c7f8  jz      short loc_18020C838
0x18020c7fa  lea     edi, [r15+3]
0x18020c7fe  xor     edx, edx
0x18020c800  mov     r8d, edi
0x18020c803  lea     r9, aNoInstalledRes; "No installed result specified"
0x18020c80a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18020c80f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18020c816  lea     rax, [rbp+340h+var_2F8]
0x18020c81a  mov     [rbp+340h+hModule], rax
0x18020c81e  lea     r9, asc_1802EE7AC; ": {}"
0x18020c825  lea     rax, [rbp+340h+hModule]
0x18020c829  mov     r8d, edi
0x18020c82c  mov     dl, 1
0x18020c82e  mov     qword ptr [rsp+440h+var_420], rax; int
0x18020c833  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18020c838  mov     edx, 0D9h; void *
0x18020c83d  mov     r9d, ebx; char *
0x18020c840  mov     rcx, [rbp+348h]; this
0x18020c847  lea     r8, aOnecoreBaseCbs_147; "onecore\\base\\cbs\\onepackage\\lib\\cb"...
0x18020c84e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020c853  lea     rcx, [rsp+440h+var_3E0]
0x18020c858  call    ?Close@?$AutoComPtr@UIEnumCSI_PENDING_TRANSACTION@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(void)
0x18020c85d  lea     rcx, [rsp+440h+lpNewFileName]
0x18020c862  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18020c867  lea     rcx, [rsp+440h+lpExistingFileName]
0x18020c86c  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18020c871  lea     rcx, [rbp+340h+var_2B0]
0x18020c878  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x18020c87d  mov     rcx, [rbp+340h+var_308]
0x18020c881  test    rcx, rcx
0x18020c884  jz      short loc_18020C896
0x18020c886  mov     rax, [rcx]
0x18020c889  mov     rax, [rax+10h]
0x18020c88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020c892  mov     [rbp+340h+var_308], r14
0x18020c896  mov     rcx, [rbp+340h+var_300]
0x18020c89a  test    rcx, rcx
0x18020c89d  jz      short loc_18020C8AF
0x18020c89f  mov     rax, [rcx]
0x18020c8a2  mov     rax, [rax+10h]
0x18020c8a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020c8ab  mov     [rbp+340h+var_300], r14
0x18020c8af  mov     rcx, [rbp+340h+var_310]
0x18020c8b3  test    rcx, rcx
0x18020c8b6  jz      loc_18020CBD4
0x18020c8bc  mov     rax, [rcx]
0x18020c8bf  mov     rax, [rax+10h]
0x18020c8c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020c8c8  mov     [rbp+340h+var_310], r14
0x18020c8cc  jmp     loc_18020CBD4
0x18020c8d1  test    rbx, rbx
0x18020c8d4  jz      short loc_18020C8ED
0x18020c8d6  mov     rax, [rbx]
0x18020c8d9  mov     rcx, rbx
0x18020c8dc  mov     rax, [rax+8]
0x18020c8e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020c8e5  mov     rdi, rbx
0x18020c8e8  mov     [rsp+440h+var_3E0], rbx
0x18020c8ed  mov     [rsi], r14b
0x18020c8f0  lea     rcx, [rsp+440h+var_3D0]
0x18020c8f5  mov     rdx, r13
0x18020c8f8  mov     [r15], r14b
0x18020c8fb  call    SczAllocFromSzAndEnsureBackslash
0x18020c900  mov     ebx, eax
0x18020c902  test    eax, eax
0x18020c904  jns     short loc_18020C913
0x18020c906  mov     r9d, eax
0x18020c909  mov     edx, 0E4h
0x18020c90e  jmp     loc_18020C840
0x18020c913  lea     rdx, aMetadata_0; "metadata\\"
0x18020c91a  lea     rcx, [rsp+440h+var_3D0]
0x18020c91f  call    SczAllocConcatSz
0x18020c924  mov     ebx, eax
0x18020c926  test    eax, eax
0x18020c928  jns     short loc_18020C937
0x18020c92a  mov     r9d, eax
0x18020c92d  mov     edx, 0E5h
0x18020c932  jmp     loc_18020C840
0x18020c937  mov     r8d, 104h; nSize
0x18020c93d  lea     rdx, [rbp+340h+Buffer]; lpBuffer
0x18020c944  lea     rcx, aUpdateAgentOve; "UPDATE_AGENT_OVERRIDE_DLL_PATH"
0x18020c94b  call    cs:__imp_GetEnvironmentVariableW
0x18020c952  nop     dword ptr [rax+rax+00h]
0x18020c957  dec     eax
0x18020c959  lea     rcx, [rsp+440h+lpLibFileName]
0x18020c95e  cmp     eax, 102h
0x18020c963  ja      short loc_18020C984
0x18020c965  lea     rdx, [rbp+340h+Buffer]
0x18020c96c  call    SczAllocFromSz
0x18020c971  mov     ebx, eax
0x18020c973  test    eax, eax
0x18020c975  jns     short loc_18020C9A8
0x18020c977  mov     r9d, eax
0x18020c97a  mov     edx, 0ECh
0x18020c97f  jmp     loc_18020C840
0x18020c984  mov     rdx, [rsp+440h+var_3D0]
0x18020c989  lea     r8, aUpdateagentDll; "updateagent.dll"
0x18020c990  call    SczAllocCombinePath2Sz
0x18020c995  mov     ebx, eax
0x18020c997  test    eax, eax
0x18020c999  jns     short loc_18020C9A8
0x18020c99b  mov     r9d, eax
0x18020c99e  mov     edx, 0F0h
0x18020c9a3  jmp     loc_18020C840
0x18020c9a8  lea     r9, [rbp+340h+var_2B0]
0x18020c9af  mov     rdx, r13
0x18020c9b2  lea     r8, aAggregatedmeta; "*.aggregatedmetadata.cab"
0x18020c9b9  call    CbsEnumFiles
0x18020c9be  mov     ebx, eax
0x18020c9c0  test    eax, eax
0x18020c9c2  jns     short loc_18020CA1C
0x18020c9c4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18020c9cb  mov     [rbp+340h+var_2F8], eax
0x18020c9ce  test    rcx, rcx
0x18020c9d1  jz      short loc_18020CA12
0x18020c9d3  mov     edi, 3
0x18020c9d8  lea     r9, aFailedGettingT_3; "Failed getting the aggregatedmetadata f"...
0x18020c9df  mov     r8d, edi
0x18020c9e2  xor     edx, edx
0x18020c9e4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18020c9e9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18020c9f0  lea     rax, [rbp+340h+var_2F8]
0x18020c9f4  mov     [rbp+340h+hModule], rax
0x18020c9f8  lea     r9, asc_1802EE7AC; ": {}"
0x18020c9ff  lea     rax, [rbp+340h+hModule]
0x18020ca03  mov     r8d, edi
0x18020ca06  mov     dl, 1
0x18020ca08  mov     qword ptr [rsp+440h+var_420], rax
0x18020ca0d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18020ca12  mov     edx, 0F6h
0x18020ca17  jmp     loc_18020C83D
0x18020ca1c  mov     rsi, r14
0x18020ca1f  mov     r14, [rbp+340h+var_298]
0x18020ca26  test    r14, r14
0x18020ca29  jz      loc_18020CADC
0x18020ca2f  mov     r12, [rbp+340h+var_288]
0x18020ca36  mov     rdx, r13
0x18020ca39  lea     rcx, [rsp+440h+lpExistingFileName]
0x18020ca3e  call    SczAllocFromSzAndEnsureBackslash
0x18020ca43  mov     ebx, eax
0x18020ca45  test    eax, eax
0x18020ca47  js      loc_18020CD27
0x18020ca4d  cmp     rsi, r14
0x18020ca50  jb      short loc_18020CA59
0x18020ca52  mov     ecx, 8
0x18020ca57  int     29h; Win8: RtlFailFast(ecx)
0x18020ca59  mov     rdx, [r12+rsi*8]
0x18020ca5d  lea     rcx, [rsp+440h+lpExistingFileName]
0x18020ca62  call    SczAllocConcatSz
0x18020ca67  mov     ebx, eax
0x18020ca69  test    eax, eax
0x18020ca6b  js      loc_18020CD20
0x18020ca71  cmp     rsi, r14
0x18020ca74  jb      short loc_18020CA7D
0x18020ca76  mov     ecx, 8
0x18020ca7b  int     29h; Win8: RtlFailFast(ecx)
0x18020ca7d  mov     r9, [r12+rsi*8]
0x18020ca81  lea     rdx, aWsWs_1; "%ws%ws"
0x18020ca88  mov     r8, [rsp+440h+var_3D0]
0x18020ca8d  lea     rcx, [rsp+440h+lpNewFileName]
0x18020ca92  call    SczAllocFormatted
0x18020ca97  mov     ebx, eax
0x18020ca99  test    eax, eax
0x18020ca9b  js      loc_18020CD19
0x18020caa1  mov     rdx, [rsp+440h+lpNewFileName]; lpNewFileName
0x18020caa6  xor     r8d, r8d; bFailIfExists
0x18020caa9  mov     rcx, [rsp+440h+lpExistingFileName]; lpExistingFileName
0x18020caae  call    cs:__imp_CopyFileW
0x18020cab5  nop     dword ptr [rax+rax+00h]
0x18020caba  test    eax, eax
0x18020cabc  jz      loc_18020CC0B
0x18020cac2  lea     rcx, [rsp+440h+lpExistingFileName]
0x18020cac7  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18020cacc  inc     rsi
0x18020cacf  cmp     rsi, r14
0x18020cad2  jb      loc_18020CA36
0x18020cad8  mov     r12, [rbp+340h+var_3B8]
0x18020cadc  mov     rcx, [rsp+440h+lpLibFileName]
0x18020cae1  xor     esi, esi
0x18020cae3  test    r12, r12
0x18020cae6  setz    dl
0x18020cae9  call    CbsVerifyFileSignature
0x18020caee  mov     ebx, eax
0x18020caf0  test    eax, eax
0x18020caf2  jns     loc_18020CDC2
0x18020caf8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18020caff  mov     [rbp+340h+var_2F8], eax
0x18020cb02  test    rcx, rcx
0x18020cb05  jz      short loc_18020CB44
0x18020cb07  lea     edi, [rsi+3]
0x18020cb0a  xor     edx, edx
0x18020cb0c  mov     r8d, edi
0x18020cb0f  lea     r9, aFailedToValida_4; "Failed to validate signature of Updatea"...
0x18020cb16  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18020cb1b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18020cb22  lea     rax, [rbp+340h+var_2F8]
  ... truncated ...
```
