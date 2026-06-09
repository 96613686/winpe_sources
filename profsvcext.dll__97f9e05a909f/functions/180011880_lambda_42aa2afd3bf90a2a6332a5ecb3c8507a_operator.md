# _lambda_42aa2afd3bf90a2a6332a5ecb3c8507a_::operator()

- ea: `0x180011880`
- end: `0x18001230d`
- name: `_lambda_42aa2afd3bf90a2a6332a5ecb3c8507a_::operator()`
- size: `2701`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180015dbc`

## callees

- `0x180005234`
- `0x180005424`
- `0x180005960`
- `0x180006344`
- `0x180006a9c`
- `0x180006b18`
- `0x1800079f0`
- `0x180008e5c`
- `0x18000927c`
- `0x180009f38`
- `0x18000a520`
- `0x18000f220`
- `0x18000f4b0`
- `0x18000fca8`
- `0x1800102e0`
- `0x180011454`
- `0x180011880`
- `0x180012ea4`
- `0x180013aac`
- `0x180015f30`
- `0x180016a1c`
- `0x1800172a4`
- `0x18001dd20`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800120fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800120fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012212`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011e2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011e2a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180011d77`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180011f0a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180011d77`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180011f0a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012097`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800121b6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012097`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800121b6`
- `PROFSVC!GetUserPreferenceValue` at `0x1800118d3`
- `PROFSVC!GetUserPreferenceValue` at `0x1800118d3`
- `USERENV!__imp_CheckXForestLogon` at `0x18001194b`
- `USERENV!__imp_CheckXForestLogon` at `0x18001194b`
- `USERENV!__imp_CheckDirectoryOwnership` at `0x180011fbf`
- `USERENV!__imp_CheckDirectoryOwnership` at `0x180011fbf`

## string_xrefs

- `0x18001195e`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_42aa2afd3bf90a2a6332a5ecb3c8507a_::operator()(__int64 a1)
{
  char v2; // r14
  _QWORD *v3; // rdi
  __int64 (__fastcall **v4)(_QWORD *); // rbx
  void *v5; // rax
  unsigned int UserPreferenceValue; // eax
  int v7; // eax
  __int64 v8; // rdx
  __int64 *v9; // rdi
  __int64 v10; // rbx
  int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // r8
  int LocalSetting; // eax
  __int64 v16; // r8
  int v17; // eax
  __int64 *v18; // rbx
  __int64 v19; // rdi
  int v20; // eax
  unsigned int v21; // eax
  int v22; // ecx
  int v23; // r8d
  int v24; // ecx
  int v25; // r8d
  const unsigned __int16 *v26; // rax
  const unsigned __int16 *v27; // rax
  unsigned __int64 v28; // r8
  int CscBypassPath; // eax
  const unsigned __int16 *v30; // rax
  signed int DirectoryForUser; // ebx
  __int64 v32; // rdx
  CUserProfileRoamingProvider *v34; // rbx
  const unsigned __int16 *v35; // rax
  int v36; // eax
  void *v37; // rax
  int v38; // eax
  unsigned __int64 v39; // r9
  __int64 v40; // rdx
  __int64 v41; // rax
  __int64 v42; // rcx
  int v43; // eax
  __int64 v44; // rax
  const WCHAR *v45; // rax
  DWORD FileAttributesW; // eax
  __int64 v47; // r8
  DWORD LastError; // ebx
  bool v49; // zf
  __int64 v50; // rax
  __int64 v51; // rdx
  const wchar_t **v52; // rax
  __int64 v53; // rcx
  const wchar_t *v54; // r8
  BOOL v55; // edi
  const unsigned __int16 *v56; // rbx
  const unsigned __int16 *v57; // rax
  __int64 *v58; // rdi
  __int64 v59; // r14
  int v60; // eax
  const WCHAR *v61; // rax
  int v62; // eax
  __int64 v63; // rbx
  __int64 v64; // rax
  int v65; // eax
  __int64 v66; // rax
  int v67; // eax
  __int64 *v68; // rdi
  __int64 v69; // rbx
  int v70; // eax
  signed int v71; // eax
  __int64 v72; // rax
  int v73; // eax
  __int64 *v74; // rdi
  __int64 v75; // rbx
  int v76; // eax
  signed int v77; // eax
  __int64 *v78; // rdi
  __int64 v79; // rbx
  int v80; // eax
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  bool v84; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v85[7]; // [rsp+41h] [rbp-BFh] BYREF
  int v86[2]; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR v89[3]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v90; // [rsp+88h] [rbp-78h] BYREF
  char v91; // [rsp+90h] [rbp-70h]
  unsigned __int16 v92[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v2 = 0;
  v86[0] = 0;
  v3 = *(_QWORD **)(*(_QWORD *)a1 + 8LL);
  v4 = (__int64 (__fastcall **)(_QWORD *))*v3;
  v5 = (void *)(*(__int64 (__fastcall **)(_QWORD *))*v3)(v3);
  UserPreferenceValue = GetUserPreferenceValue(v5);
  ((void (__fastcall *)(_QWORD *, _QWORD))v4[16])(v3, UserPreferenceValue);
  v7 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 120LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL));
  v8 = **(_QWORD **)(*(_QWORD *)a1 + 8LL);
  if ( v7 )
  {
    v12 = (*(__int64 (**)(void))v8)();
    v13 = CheckXForestLogon(v12);
    if ( v13 >= 0 )
    {
      if ( v13 == 1 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
          && (byte_18002DCC1 & 1) != 0 )
        {
          McGenEventWrite_EtwEventWriteTransfer(v22, (unsigned int)EVENT_XFOREST_LOGON_DETECTED, v23, 1, (__int64)&v90);
        }
        if ( (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 40LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL)) )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 48LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL));
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 88LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL));
        (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 128LL))(
          *(_QWORD *)(*(_QWORD *)a1 + 8LL),
          0);
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 184LL))(
          *(_QWORD *)(*(_QWORD *)a1 + 8LL),
          104);
        if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 1) != 0 )
          McGenEventWrite_EtwEventWriteTransfer(v24, (unsigned int)EVENT_X_FOREST_LOGON_DISABLED, v25, 1, (__int64)&v90);
        return 0;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x287,
        (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(unsigned int)v13);
    }
    v85[0] = 0;
    LocalSetting = Profile::GetLocalSetting(7, v85, v14);
    if ( LocalSetting < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2A6,
        (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(unsigned int)LocalSetting);
    v84 = 0;
    v17 = Profile::GetLocalSetting(6, &v84, v16);
    if ( v17 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2A9,
        (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(unsigned int)v17);
    v18 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
    v19 = *v18;
    v20 = (*(__int64 (__fastcall **)(__int64 *))(*v18 + 16))(v18);
    if ( v84 )
      v21 = v20 | 0x10000;
    else
      v21 = v20 & 0xFFFEFFFF;
    (*(void (__fastcall **)(__int64 *, _QWORD))(v19 + 24))(v18, v21);
    v26 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 56LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL));
    if ( (unsigned int)IsUNCPath(v26) )
    {
      v86[0] = 0;
      if ( CUserProfileRoamingProvider::_IsBypassPathNeeded(*(CUserProfileRoamingProvider **)a1, 1, v86) < 0 || v86[0] )
      {
        v27 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 56LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL));
        CscBypassPath = GetCscBypassPath(v27, v92, v28);
        if ( CscBypassPath >= 0 )
        {
          DirectoryForUser = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**(_QWORD **)(*(_QWORD *)a1 + 8LL)
                                                                                   + 96LL))(
                               *(_QWORD *)(*(_QWORD *)a1 + 8LL),
                               v92);
          if ( DirectoryForUser < 0 )
          {
            v32 = 705;
            goto LABEL_29;
          }
LABEL_33:
          v34 = *(CUserProfileRoamingProvider **)a1;
          v35 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 56LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL));
          v36 = CUserProfileRoamingProvider::_CheckRupSlowLink(v34, v35);
          if ( v36 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x2CF,
              (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
              (const char *)(unsigned int)v36);
          v90 = 0;
          v91 = 0;
          v37 = (void *)(***(__int64 (__fastcall ****)(_QWORD))(*(_QWORD *)a1 + 8LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL));
          v38 = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v90, v37);
          DirectoryForUser = v38;
          if ( v38 < 0 )
          {
            v39 = (unsigned int)v38;
            v40 = 723;
LABEL_66:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v40,
              (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
              (const char *)v39,
              dwCreationDisposition);
            goto LABEL_103;
          }
          if ( ((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 16LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL))
              & 0x400) != 0 )
          {
            if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 1) != 0 )
            {
              v41 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 56LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL));
              McTemplateU0z_EtwEventWriteTransfer(v42, EVENT_SLOW_LINK, v41);
            }
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 88LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL));
            (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 184LL))(
              *(_QWORD *)(*(_QWORD *)a1 + 8LL),
              106);
            goto LABEL_41;
          }
          v84 = 1;
          v43 = CUserProfileRoamingProvider::_CheckRupPrimaryComputer(*(CUserProfileRoamingProvider **)a1, &v84);
          if ( v43 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x2E0,
              (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
              (const char *)(unsigned int)v43);
          v44 = **(_QWORD **)(*(_QWORD *)a1 + 8LL);
          if ( !v84 )
          {
            if ( (*(__int64 (**)(void))(v44 + 40))() )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 48LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL));
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 88LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL));
            (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 128LL))(
              *(_QWORD *)(*(_QWORD *)a1 + 8LL),
              0);
            goto LABEL_41;
          }
          v45 = (const WCHAR *)(*(__int64 (**)(void))(v44 + 80))();
          FileAttributesW = GetFileAttributesW(v45);
          if ( FileAttributesW == -1 )
          {
            LastError = GetLastError();
            v49 = ((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 16LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL))
                 & 1) == 0;
            v50 = **(_QWORD **)(*(_QWORD *)a1 + 8LL);
            if ( !v49 )
            {
              (*(void (**)(void))(v50 + 88))();
              if ( LastError )
              {
                v51 = 766;
LABEL_52:
                DirectoryForUser = wil::details::in1diag3::Return_Win32(
                                     retaddr,
                                     (void *)v51,
                                     (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
                                     (const char *)LastError,
                                     dwCreationDisposition);
                goto LABEL_103;
              }
              goto LABEL_41;
            }
            if ( ((*(__int64 (**)(void))(v50 + 16))() & 0x10000) != 0 )
            {
              if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 1) != 0 )
              {
                v52 = (const wchar_t **)CErrorText::CErrorText((LPWSTR)&hMem, LastError);
                v2 = 1;
                v54 = L"???";
                if ( *v52 )
                  v54 = *v52;
                McTemplateU0z_EtwEventWriteTransfer(v53, EVENT_READONLY_NOT_AVAILABLE_DISABLE, v54);
              }
              if ( (v2 & 1) != 0 )
                LocalFree(hMem);
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 88LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL));
              goto LABEL_41;
            }
            if ( ((LastError - 2) & 0xFFFFFFBE) != 0 || LastError == 66 )
            {
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 88LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL));
              if ( LastError )
              {
                v51 = 803;
                goto LABEL_52;
              }
LABEL_41:
              DirectoryForUser = 0;
LABEL_103:
              CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v90);
              return (unsigned int)DirectoryForUser;
            }
            v55 = v85[0] != 0;
            v56 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 32LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL));
            v57 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 80LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL));
            DirectoryForUser = CreateDirectoryForUser(v57, v56, v55);
            v58 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
            v59 = *v58;
            if ( DirectoryForUser < 0 )
            {
              (*(void (__fastcall **)(__int64 *))(v59 + 88))(v58);
              v40 = 793;
LABEL_65:
              v39 = (unsigned int)DirectoryForUser;
              goto LABEL_66;
            }
            v60 = (*(__int64 (__fastcall **)(__int64 *))(v59 + 16))(v58);
            (*(void (__fastcall **)(__int64 *, _QWORD))(v59 + 24))(v58, v60 | 0x18u);
            v61 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 80LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL));
            LOBYTE(FileAttributesW) = GetFileAttributesW(v61);
          }
          if ( (FileAttributesW & 0x10) == 0 )
          {
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 88LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL));
            DirectoryForUser = -2147024893;
            v40 = 811;
            goto LABEL_65;
          }
          v85[0] = 0;
          v62 = Profile::GetLocalSetting(2, v85, v47);
          if ( v62 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x330,
              (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
              (const char *)(unsigned int)v62);
          if ( !v85[0] )
          {
            v63 = (***(__int64 (__fastcall ****)(_QWORD))(*(_QWORD *)a1 + 8LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL));
            v64 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 80LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL));
            v65 = CheckDirectoryOwnership(v64, 1, v63);
            DirectoryForUser = v65;
            if ( v65 < 0 )
            {
              if ( v65 == -2147023589 )
                **(_BYTE **)(a1 + 8) = 1;
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 88LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL));
              v40 = 830;
              goto LABEL_65;
            }
          }
          if ( ((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 16LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL))
              & 8) == 0 )
          {
            memset(lpFileName, 0, sizeof(lpFileName));
            v66 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 80LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL));
            v67 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
                    lpFileName,
                    L"%s\\%s",
                    v66,
                    L"ntuser.man");
            DirectoryForUser = v67;
            if ( v67 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x347,
                (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
                (const char *)(unsigned int)v67,
                dwCreationDisposition);
LABEL_102:
              Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
              goto LABEL_103;
            }
            *(_QWORD *)v86 = CreateFileW(lpFileName[0], 0x80000000, 1u, 0, 3u, 0x80u, 0);
            if ( *(_QWORD *)v86 != -1 )
            {
              v68 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
              v69 = *v68;
              v70 = (*(__int64 (__fastcall **)(__int64 *))(*v68 + 16))(v68);
              (*(void (__fastcall **)(__int64 *, _QWORD))(v69 + 24))(v68, v70 | 1u);
              RUPTelemetry::SetLoadConfiguredProfileType(2);
              ***(_DWORD ***)(a1 + 16) = 1;
LABEL_84:
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v86);
              Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
              goto LABEL_41;
            }
            v71 = GetLastError();
            DirectoryForUser = v71;
            if ( v71 != 2 )
            {
              if ( v71 > 0 )
                DirectoryForUser = (unsigned __int16)v71 | 0x80070000;
              if ( DirectoryForUser < 0 )
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x35D,
                  (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
                  (const char *)(unsigned int)DirectoryForUser,
                  dwCreationDispositiona);
              goto LABEL_101;
            }
            memset(v89, 0, sizeof(v89));
            v72 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 80LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL));
            v73 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
                    v89,
                    L"%s\\%s",
                    v72,
                    L"ntuser.dat");
            DirectoryForUser = v73;
            if ( v73 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x361,
                (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
                (const char *)(unsigned int)v73,
                dwCreationDispositiona);
LABEL_100:
              Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v89);
LABEL_101:
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v86);
              goto LABEL_102;
            }
            hMem = CreateFileW(v89[0], 0x80000000, 1u, 0, 3u, 0x80u, 0);
            if ( hMem != (HLOCAL)-1LL )
            {
              v74 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
              v75 = *v74;
              v76 = (*(__int64 (__fastcall **)(__int64 *))(*v74 + 16))(v74);
              (*(void (__fastcall **)(__int64 *, _QWORD))(v75 + 24))(v74, v76 | 0x10u);
              ***(_DWORD ***)(a1 + 16) = 1;
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hMem);
              Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v89);
              goto LABEL_84;
            }
            v77 = GetLastError();
            DirectoryForUser = v77;
            if ( v77 != 2 )
            {
              if ( v77 > 0 )
                DirectoryForUser = (unsigned __int16)v77 | 0x80070000;
              if ( DirectoryForUser < 0 )
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x375,
                  (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
                  (const char *)(unsigned int)DirectoryForUser,
                  dwCreationDispositionb);
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hMem);
              goto LABEL_100;
            }
            v78 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
            v79 = *v78;
            v80 = (*(__int64 (__fastcall **)(__int64 *))(*v78 + 16))(v78);
            (*(void (__fastcall **)(__int64 *, _QWORD))(v79 + 24))(v78, v80 | 0x18u);
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hMem);
            Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v89);
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v86);
            Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
          }
          ***(_DWORD ***)(a1 + 16) = 1;
          CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v90);
          return 0;
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2BE,
          (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
          (const char *)(unsigned int)CscBypassPath);
      }
    }
    v30 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 56LL))(*(_QWORD *)(*(_QWORD *)a1 + 8LL));
    DirectoryForUser = StringCchCopyW(v92, 0x104u, v30);
    if ( DirectoryForUser < 0 )
    {
      v32 = 714;
LABEL_29:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v32,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(unsigned int)DirectoryForUser,
        dwCreationDisposition);
      return (unsigned int)DirectoryForUser;
    }
    DirectoryForUser = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 96LL))(
                         *(_QWORD *)(*(_QWORD *)a1 + 8LL),
                         v92);
    if ( DirectoryForUser < 0 )
    {
      v32 = 715;
      goto LABEL_29;
    }
    goto LABEL_33;
  }
  (*(void (**)(void))(v8 + 88))();
  v9 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
  v10 = *v9;
  v11 = (*(__int64 (__fastcall **)(__int64 *))(*v9 + 16))(v9);
  (*(void (__fastcall **)(__int64 *, _QWORD))(v10 + 24))(v9, v11 | 2u);
  return 0;
}

```

## disassembly

```asm
0x180011880  push    rbp
0x180011882  push    rbx
0x180011883  push    rsi
0x180011884  push    rdi
0x180011885  push    r12
0x180011887  push    r13
0x180011889  push    r14
0x18001188b  push    r15
0x18001188d  lea     rbp, [rsp-1C8h]
0x180011895  sub     rsp, 2C8h
0x18001189c  mov     rax, cs:__security_cookie
0x1800118a3  xor     rax, rsp
0x1800118a6  mov     [rbp+200h+var_50], rax
0x1800118ad  mov     rsi, rcx
0x1800118b0  xor     r15d, r15d
0x1800118b3  mov     r14d, r15d
0x1800118b6  mov     [rsp+300h+var_2B8], r15d
0x1800118bb  mov     rax, [rcx]
0x1800118be  mov     rdi, [rax+8]
0x1800118c2  mov     rbx, [rdi]
0x1800118c5  mov     rcx, rdi
0x1800118c8  mov     rax, [rbx]
0x1800118cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118d0  mov     rcx, rax
0x1800118d3  call    cs:__imp_?GetUserPreferenceValue@@YAKPEAX@Z; GetUserPreferenceValue(void *)
0x1800118d9  mov     edx, eax
0x1800118db  mov     rcx, rdi
0x1800118de  mov     rax, [rbx+80h]
0x1800118e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118ea  mov     rax, [rsi]
0x1800118ed  mov     rcx, [rax+8]
0x1800118f1  mov     rax, [rcx]
0x1800118f4  mov     rax, [rax+78h]
0x1800118f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118fd  mov     rcx, [rsi]
0x180011900  mov     rcx, [rcx+8]
0x180011904  mov     rdx, [rcx]
0x180011907  test    eax, eax
0x180011909  jnz     short loc_180011940
0x18001190b  mov     rax, [rdx+58h]
0x18001190f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011914  mov     rax, [rsi]
0x180011917  mov     rdi, [rax+8]
0x18001191b  mov     rbx, [rdi]
0x18001191e  mov     rcx, rdi
0x180011921  mov     rax, [rbx+10h]
0x180011925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001192a  or      eax, 2
0x18001192d  mov     edx, eax
0x18001192f  mov     rcx, rdi
0x180011932  mov     rax, [rbx+18h]
0x180011936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001193b  jmp     loc_1800122E8
0x180011940  mov     rax, [rdx]
0x180011943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011948  mov     rcx, rax
0x18001194b  call    cs:__imp_CheckXForestLogon
0x180011951  mov     rcx, [rbp+208h]; this
0x180011958  mov     r13d, 1
0x18001195e  lea     r12, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180011965  test    eax, eax
0x180011967  jns     loc_180011A08
0x18001196d  mov     r9d, eax; char *
0x180011970  mov     r8, r12; unsigned int
0x180011973  mov     edx, 287h; void *
0x180011978  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001197d  mov     [rsp+300h+var_2BF], r15b
0x180011982  lea     rdx, [rsp+300h+var_2BF]
0x180011987  mov     ecx, 7
0x18001198c  call    ?GetLocalSetting@Profile@@YAJW4PROFILE_SETTING_ID@1@AEA_NPEBGW4USERSTATE_SETTING_SOURCES@@@Z; Profile::GetLocalSetting(Profile::PROFILE_SETTING_ID,bool &,ushort const *,USERSTATE_SETTING_SOURCES)
0x180011991  mov     rcx, [rbp+208h]; this
0x180011998  test    eax, eax
0x18001199a  jns     short loc_1800119AC
0x18001199c  mov     r9d, eax; char *
0x18001199f  mov     r8, r12; unsigned int
0x1800119a2  mov     edx, 2A6h; void *
0x1800119a7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800119ac  mov     [rsp+300h+var_2C0], r15b
0x1800119b1  lea     rdx, [rsp+300h+var_2C0]
0x1800119b6  mov     ecx, 6
0x1800119bb  call    ?GetLocalSetting@Profile@@YAJW4PROFILE_SETTING_ID@1@AEA_NPEBGW4USERSTATE_SETTING_SOURCES@@@Z; Profile::GetLocalSetting(Profile::PROFILE_SETTING_ID,bool &,ushort const *,USERSTATE_SETTING_SOURCES)
0x1800119c0  mov     rcx, [rbp+208h]; this
0x1800119c7  test    eax, eax
0x1800119c9  jns     short loc_1800119DB
0x1800119cb  mov     r9d, eax; char *
0x1800119ce  mov     r8, r12; unsigned int
0x1800119d1  mov     edx, 2A9h; void *
0x1800119d6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800119db  mov     rax, [rsi]
0x1800119de  mov     rbx, [rax+8]
0x1800119e2  mov     rdi, [rbx]
0x1800119e5  mov     rcx, rbx
0x1800119e8  mov     rax, [rdi+10h]
0x1800119ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119f1  mov     rcx, rbx
0x1800119f4  cmp     [rsp+300h+var_2C0], r15b
0x1800119f9  jz      loc_180011ADD
0x1800119ff  bts     eax, 10h
0x180011a03  jmp     loc_180011AE1
0x180011a08  cmp     eax, r13d
0x180011a0b  jnz     loc_18001197D
0x180011a11  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180011a18  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180011a1d  test    al, al
0x180011a1f  jz      short loc_180011A42
0x180011a21  test    cs:byte_18002DCC1, r13b
0x180011a28  jz      short loc_180011A42
0x180011a2a  lea     rax, [rbp+200h+var_278]
0x180011a2e  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x180011a33  mov     r9d, r13d
0x180011a36  lea     rdx, EVENT_XFOREST_LOGON_DETECTED
0x180011a3d  call    McGenEventWrite_EtwEventWriteTransfer
0x180011a42  mov     rax, [rsi]
0x180011a45  mov     rcx, [rax+8]
0x180011a49  mov     rax, [rcx]
0x180011a4c  mov     rax, [rax+28h]
0x180011a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a55  test    rax, rax
0x180011a58  jz      short loc_180011A6D
0x180011a5a  mov     rax, [rsi]
0x180011a5d  mov     rcx, [rax+8]
0x180011a61  mov     rax, [rcx]
0x180011a64  mov     rax, [rax+30h]
0x180011a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a6d  mov     rax, [rsi]
0x180011a70  mov     rcx, [rax+8]
0x180011a74  mov     rax, [rcx]
0x180011a77  mov     rax, [rax+58h]
0x180011a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a80  mov     rax, [rsi]
0x180011a83  mov     rcx, [rax+8]
0x180011a87  mov     rax, [rcx]
0x180011a8a  xor     edx, edx
0x180011a8c  mov     rax, [rax+80h]
0x180011a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a98  mov     rax, [rsi]
0x180011a9b  mov     rcx, [rax+8]
0x180011a9f  mov     rax, [rcx]
0x180011aa2  mov     edx, 68h ; 'h'
0x180011aa7  mov     rax, [rax+0B8h]
0x180011aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ab3  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, r13b
0x180011aba  jz      loc_1800122E8
0x180011ac0  lea     rax, [rbp+200h+var_278]
0x180011ac4  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x180011ac9  mov     r9d, r13d
0x180011acc  lea     rdx, EVENT_X_FOREST_LOGON_DISABLED
0x180011ad3  call    McGenEventWrite_EtwEventWriteTransfer
0x180011ad8  jmp     loc_1800122E8
0x180011add  btr     eax, 10h
0x180011ae1  mov     edx, eax
0x180011ae3  mov     rax, [rdi+18h]
0x180011ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011aec  mov     rax, [rsi]
0x180011aef  mov     rcx, [rax+8]
0x180011af3  mov     rax, [rcx]
0x180011af6  mov     rax, [rax+38h]
0x180011afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011aff  mov     rcx, rax; unsigned __int16 *
0x180011b02  call    ?IsUNCPath@@YAHPEBG@Z; IsUNCPath(ushort const *)
0x180011b07  test    eax, eax
0x180011b09  jz      short loc_180011B65
0x180011b0b  mov     [rsp+300h+var_2B8], r15d
0x180011b10  lea     r8, [rsp+300h+var_2B8]; int *
0x180011b15  mov     edx, r13d; int
0x180011b18  mov     rcx, [rsi]; this
0x180011b1b  call    ?_IsBypassPathNeeded@CUserProfileRoamingProvider@@AEAAJHPEAH@Z; CUserProfileRoamingProvider::_IsBypassPathNeeded(int,int *)
0x180011b20  test    eax, eax
0x180011b22  js      short loc_180011B2B
0x180011b24  cmp     [rsp+300h+var_2B8], r15d
0x180011b29  jz      short loc_180011B65
0x180011b2b  mov     rax, [rsi]
0x180011b2e  mov     rcx, [rax+8]
0x180011b32  mov     rax, [rcx]
0x180011b35  mov     rax, [rax+38h]
0x180011b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b3e  mov     rcx, rax; unsigned __int16 *
0x180011b41  lea     rdx, [rbp+200h+var_260]; unsigned __int16 *
0x180011b45  call    ?GetCscBypassPath@@YAJPEBGPEAG_K@Z; GetCscBypassPath(ushort const *,ushort *,unsigned __int64)
0x180011b4a  mov     rcx, [rbp+208h]; this
0x180011b51  test    eax, eax
0x180011b53  jns     short loc_180011B96
0x180011b55  mov     r9d, eax; char *
0x180011b58  mov     r8, r12; unsigned int
0x180011b5b  mov     edx, 2BEh; void *
0x180011b60  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011b65  mov     rax, [rsi]
0x180011b68  mov     rcx, [rax+8]
0x180011b6c  mov     rax, [rcx]
0x180011b6f  mov     rax, [rax+38h]
0x180011b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b78  mov     r8, rax; unsigned __int16 *
0x180011b7b  mov     edx, 104h; unsigned __int64
0x180011b80  lea     rcx, [rbp+200h+var_260]; unsigned __int16 *
0x180011b84  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011b89  mov     ebx, eax
0x180011b8b  test    eax, eax
0x180011b8d  jns     short loc_180011BD1
0x180011b8f  mov     edx, 2CAh
0x180011b94  jmp     short loc_180011BB8
0x180011b96  mov     rax, [rsi]
0x180011b99  mov     rcx, [rax+8]
0x180011b9d  mov     rax, [rcx]
0x180011ba0  lea     rdx, [rbp+200h+var_260]
0x180011ba4  mov     rax, [rax+60h]
0x180011ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bad  mov     ebx, eax
0x180011baf  test    eax, eax
0x180011bb1  jns     short loc_180011BF5
0x180011bb3  mov     edx, 2C1h; void *
0x180011bb8  mov     rcx, [rbp+208h]; this
0x180011bbf  mov     r9d, ebx; char *
0x180011bc2  mov     r8, r12; unsigned int
0x180011bc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011bca  mov     eax, ebx
0x180011bcc  jmp     loc_1800122EA
0x180011bd1  mov     rax, [rsi]
0x180011bd4  mov     rcx, [rax+8]
0x180011bd8  mov     rax, [rcx]
0x180011bdb  lea     rdx, [rbp+200h+var_260]
0x180011bdf  mov     rax, [rax+60h]
0x180011be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011be8  mov     ebx, eax
0x180011bea  test    eax, eax
0x180011bec  jns     short loc_180011BF5
0x180011bee  mov     edx, 2CBh
0x180011bf3  jmp     short loc_180011BB8
0x180011bf5  mov     rbx, [rsi]
0x180011bf8  mov     rcx, [rbx+8]
0x180011bfc  mov     rax, [rcx]
0x180011bff  mov     rax, [rax+38h]
0x180011c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c08  mov     rdx, rax; unsigned __int16 *
0x180011c0b  mov     rcx, rbx; this
0x180011c0e  call    ?_CheckRupSlowLink@CUserProfileRoamingProvider@@AEAAJPEBG@Z; CUserProfileRoamingProvider::_CheckRupSlowLink(ushort const *)
0x180011c13  mov     rcx, [rbp+208h]; this
0x180011c1a  test    eax, eax
0x180011c1c  jns     short loc_180011C2E
0x180011c1e  mov     r9d, eax; char *
0x180011c21  mov     r8, r12; unsigned int
0x180011c24  mov     edx, 2CFh; void *
0x180011c29  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011c2e  mov     [rbp+200h+var_278], r15
0x180011c32  mov     [rbp+200h+var_270], r15b
0x180011c36  mov     rax, [rsi]
0x180011c39  mov     rcx, [rax+8]
0x180011c3d  mov     rax, [rcx]
0x180011c40  mov     rax, [rax]
0x180011c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c48  mov     rdx, rax; void *
0x180011c4b  lea     rcx, [rbp+200h+var_278]; this
0x180011c4f  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x180011c54  mov     ebx, eax
0x180011c56  test    eax, eax
0x180011c58  jns     short loc_180011C67
0x180011c5a  mov     r9d, eax
0x180011c5d  mov     edx, 2D3h
0x180011c62  jmp     loc_180011EC6
0x180011c67  mov     rax, [rsi]
0x180011c6a  mov     rcx, [rax+8]
0x180011c6e  mov     rax, [rcx]
0x180011c71  mov     rax, [rax+10h]
0x180011c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c7a  bt      eax, 0Ah
0x180011c7e  jnb     short loc_180011CE1
0x180011c80  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, r13b
0x180011c87  jz      short loc_180011CAB
0x180011c89  mov     rax, [rsi]
0x180011c8c  mov     rcx, [rax+8]
0x180011c90  mov     rax, [rcx]
0x180011c93  mov     rax, [rax+38h]
0x180011c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c9c  mov     r8, rax
0x180011c9f  lea     rdx, EVENT_SLOW_LINK
0x180011ca6  call    McTemplateU0z_EtwEventWriteTransfer
0x180011cab  mov     rax, [rsi]
0x180011cae  mov     rcx, [rax+8]
0x180011cb2  mov     rax, [rcx]
0x180011cb5  mov     rax, [rax+58h]
0x180011cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cbe  mov     rax, [rsi]
0x180011cc1  mov     rcx, [rax+8]
0x180011cc5  mov     rax, [rcx]
0x180011cc8  mov     edx, 6Ah ; 'j'
0x180011ccd  mov     rax, [rax+0B8h]
0x180011cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cd9  mov     ebx, r15d
0x180011cdc  jmp     loc_180012274
0x180011ce1  mov     [rsp+300h+var_2C0], r13b
0x180011ce6  lea     rdx, [rsp+300h+var_2C0]; bool *
0x180011ceb  mov     rcx, [rsi]; this
0x180011cee  call    ?_CheckRupPrimaryComputer@CUserProfileRoamingProvider@@AEAAJAEA_N@Z; CUserProfileRoamingProvider::_CheckRupPrimaryComputer(bool &)
0x180011cf3  mov     rcx, [rbp+208h]; this
0x180011cfa  test    eax, eax
0x180011cfc  jns     short loc_180011D0E
0x180011cfe  mov     r9d, eax; char *
0x180011d01  mov     r8, r12; unsigned int
0x180011d04  mov     edx, 2E0h; void *
0x180011d09  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011d0e  mov     rax, [rsi]
  ... truncated ...
```
