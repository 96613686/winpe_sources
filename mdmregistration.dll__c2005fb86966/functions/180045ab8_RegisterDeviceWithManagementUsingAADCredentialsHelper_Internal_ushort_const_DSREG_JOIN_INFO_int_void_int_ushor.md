# RegisterDeviceWithManagementUsingAADCredentialsHelper_Internal(ushort const *,_DSREG_JOIN_INFO *,int,void *,int,ushort const *)

- ea: `0x180045ab8`
- end: `0x18004693c`
- name: `?RegisterDeviceWithManagementUsingAADCredentialsHelper_Internal@@YAJPEBGPEAU_DSREG_JOIN_INFO@@HPEAXH0@Z`
- size: `3716`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, struct _DSREG_JOIN_INFO *@<rdx>, int@<r8d>, void *@<r9>, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180045698`

## callees

- `0x1800026d0`
- `0x1800031a0`
- `0x180004a7c`
- `0x1800194e0`
- `0x180021db4`
- `0x180041410`
- `0x1800416a0`
- `0x1800419b8`
- `0x180041aa4`
- `0x180041b90`
- `0x180041c7c`
- `0x180041d5c`
- `0x180041e10`
- `0x180041fb4`
- `0x1800420a0`
- `0x18004218c`
- `0x180044f4c`
- `0x1800451d8`
- `0x180045358`
- `0x180045ab8`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045bb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045bed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045ccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045d08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045f63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045fee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046152`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045bb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045bed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045ccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045d08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045f63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045fee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046152`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180045e58`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180045e58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045bd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045c0c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045ceb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045d27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004600e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045bd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045c0c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045ceb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045d27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004600e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045bc6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045bfe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045cdd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045d19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045dcb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046000`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046058`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800468a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800468b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800468cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045bc6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045bfe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045cdd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045d19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045dcb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046000`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046058`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800468a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800468b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800468cb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180046142`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180046142`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180045f3e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180045f3e`
- `DMCmnUtils!DmIsRunningInSystemContext` at `0x180045f1f`
- `DMCmnUtils!DmIsRunningInSystemContext` at `0x180045f1f`
- `DMCmnUtils!DmRaiseToastNotificationAndWait` at `0x1800461f3`
- `DMCmnUtils!DmRaiseToastNotificationAndWait` at `0x1800461f3`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180045fb5`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180045fb5`
- `DMCmnUtils!DmRevertToSelf` at `0x180046084`
- `DMCmnUtils!DmRevertToSelf` at `0x180046179`
- `DMCmnUtils!DmRevertToSelf` at `0x18004627e`
- `DMCmnUtils!DmRevertToSelf` at `0x180046084`
- `DMCmnUtils!DmRevertToSelf` at `0x180046179`
- `DMCmnUtils!DmRevertToSelf` at `0x18004627e`
- `DMCmnUtils!DmImpersonate` at `0x18004602e`
- `DMCmnUtils!DmImpersonate` at `0x18004602e`
- `DMCmnUtils!DmGetAadUserToken` at `0x1800460e8`
- `DMCmnUtils!DmGetAadUserToken` at `0x1800460e8`
- `DMCmnUtils!DmRequestAadUserToken` at `0x180046250`
- `DMCmnUtils!DmRequestAadUserToken` at `0x180046250`
- `DMCmnUtils!DmGetAadDeviceToken` at `0x180045db6`
- `DMCmnUtils!DmGetAadDeviceToken` at `0x180045db6`
- `DMCmnUtils!DmGetAadDeviceTokenWithDiscovery` at `0x180045c3f`
- `DMCmnUtils!DmGetAadDeviceTokenWithDiscovery` at `0x180045d5d`
- `DMCmnUtils!DmGetAadDeviceTokenWithDiscovery` at `0x180045c3f`
- `DMCmnUtils!DmGetAadDeviceTokenWithDiscovery` at `0x180045d5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800463da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800463da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004631e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180046340`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180046362`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180046385`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800463b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004631e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180046340`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180046362`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180046385`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800463b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180045e39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180045e39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800467e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800467f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046802`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046813`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800467e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800467f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046802`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046813`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180046092`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180046187`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18004628c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180046092`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180046187`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18004628c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800460b8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800462ae`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800460b8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800462ae`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180045efa`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180045efa`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180045eb8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180045eb8`

## string_xrefs

- `0x18004613b`: `%windir%\system32\deviceenroller.exe`
- `0x1800461ec`: `DMAppsRes.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall RegisterDeviceWithManagementUsingAADCredentialsHelper_Internal(
        unsigned __int16 *a1,
        struct _DSREG_JOIN_INFO *a2,
        int a3,
        void *a4,
        int a5,
        unsigned __int16 *a6)
{
  unsigned __int16 *v7; // r15
  unsigned __int16 *v8; // rbx
  const WCHAR *v9; // r12
  __int64 v10; // r13
  unsigned int v11; // r8d
  HLOCAL v12; // rdi
  DWORD LastError; // ebx
  HLOCAL v14; // rdi
  DWORD v15; // ebx
  signed int AadDeviceTokenWithDiscovery; // esi
  CEnrollmentLogger *Logger; // rax
  CEnrollmentLogger *v18; // rax
  int DeviceApplicaitonId; // eax
  int v20; // edi
  unsigned __int16 *v21; // rbx
  HLOCAL v22; // r14
  DWORD v23; // edi
  HLOCAL v24; // r14
  DWORD v25; // edi
  CEnrollmentLogger *v26; // rax
  CEnrollmentLogger *v27; // rax
  CEnrollmentLogger *v28; // rax
  __int64 *v29; // rcx
  char v30; // r14
  BOOL v31; // ebx
  char v32; // r15
  signed int v33; // eax
  HSTRING v34; // rax
  DWORD v35; // edi
  CEnrollmentLogger *v36; // rax
  HRESULT v37; // eax
  const unsigned __int16 *v38; // rdi
  int v39; // ecx
  signed int v40; // eax
  HRESULT v41; // eax
  CEnrollmentLogger *v42; // rax
  CEnrollmentLogger *v43; // rax
  HRESULT v44; // eax
  unsigned __int16 *v45; // rdi
  __int64 v46; // rdx
  __int64 v47; // rax
  UINT32 v48; // edx
  unsigned __int16 *v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // rdx
  __int64 v52; // rdx
  const WCHAR *v53; // rcx
  CEnrollmentLogger *v54; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v56; // rax
  CEnrollmentLogger *v57; // rax
  __int64 v58; // rcx
  __int64 *v59; // rcx
  CEnrollmentLogger *v60; // rax
  __int64 v61; // rcx
  __int64 *v62; // rcx
  CEnrollmentLogger *v63; // rax
  __int64 v64; // rcx
  __int64 v65; // rcx
  __int64 *v66; // rcx
  HLOCAL v67; // rcx
  __int64 v68; // rcx
  __int64 v69; // rcx
  __int64 *v70; // rcx
  HLOCAL v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 *v74; // rcx
  HLOCAL v75; // rcx
  __int64 v76; // rcx
  __int64 v77; // rcx
  __int64 *v78; // rcx
  HLOCAL v79; // rcx
  __int64 v80; // rcx
  __int64 v81; // rcx
  __int64 *v82; // rcx
  int v83; // eax
  HLOCAL v84; // rcx
  __int64 v85; // rcx
  __int64 v86; // rcx
  __int64 *v87; // rcx
  WCHAR *v88; // rcx
  int dwAuthnLevel; // [rsp+20h] [rbp-E0h]
  int dwAuthnLevela; // [rsp+20h] [rbp-E0h]
  __int64 v92; // [rsp+50h] [rbp-B0h] BYREF
  int v93[2]; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL v94; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v95; // [rsp+68h] [rbp-98h] BYREF
  int v96; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL v97; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL v98; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v99; // [rsp+88h] [rbp-78h]
  HLOCAL hMem; // [rsp+90h] [rbp-70h] BYREF
  PCNZWCH sourceString; // [rsp+98h] [rbp-68h] BYREF
  PVOID Reserved1; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v103; // [rsp+A8h] [rbp-58h]
  char v104; // [rsp+B0h] [rbp-50h]
  char v105; // [rsp+B2h] [rbp-4Eh]
  HLOCAL v106; // [rsp+C0h] [rbp-40h]
  HSTRING v107; // [rsp+C8h] [rbp-38h]
  struct _DSREG_JOIN_INFO *v108; // [rsp+D0h] [rbp-30h]
  HSTRING v109[2]; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v110[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v111; // [rsp+100h] [rbp+0h]
  HSTRING v112[2]; // [rsp+110h] [rbp+10h] BYREF
  HSTRING v113[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v114; // [rsp+130h] [rbp+30h]
  _OWORD v115[5]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v116; // [rsp+190h] [rbp+90h]
  HSTRING string; // [rsp+1A0h] [rbp+A0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+1A8h] [rbp+A8h] BYREF
  WCHAR Dst[264]; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+428h] [rbp+328h]

  v93[0] = a3;
  v108 = a2;
  v7 = a1;
  v97 = a1;
  sourceString = 0;
  v98 = 0;
  hMem = 0;
  v8 = a1;
  v99 = a1;
  if ( a2 )
  {
    v103 = (unsigned __int16 *)*((_QWORD *)a2 + 5);
    v9 = (const WCHAR *)*((_QWORD *)a2 + 7);
  }
  else
  {
    v103 = 0;
    v9 = 0;
  }
  v10 = -1;
  if ( a3 )
  {
    v11 = *(_DWORD *)Feature_Servicing_RegisterDeviceWithManagementUsingAADDeviceCredentials_27687908__descriptor;
    if ( (*(_DWORD *)Feature_Servicing_RegisterDeviceWithManagementUsingAADDeviceCredentials_27687908__descriptor & 4) == 0 )
    {
      v97 = *(HLOCAL *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegisterDeviceWithManagementUsingAADDeviceCredentials_27687908>::GetCachedFeatureEnabledState(
                         1,
                         &Reserved1);
      v11 = (unsigned int)v97;
    }
    LODWORD(v92) = 0;
    WORD2(v92) = 3;
    wil::details::ReportUsageToService(&qword_180070FA0, 27168760, (v11 >> 10) & 1, (v11 >> 11) & 1, &v92, 1);
    if ( a6 )
    {
      v12 = hMem;
      if ( hMem )
      {
        LastError = GetLastError();
        LocalFree(v12);
        SetLastError(LastError);
      }
      hMem = 0;
      v14 = v98;
      if ( v98 )
      {
        v15 = GetLastError();
        LocalFree(v14);
        SetLastError(v15);
      }
      v98 = 0;
      AadDeviceTokenWithDiscovery = DmGetAadDeviceTokenWithDiscovery(
                                      L"de50c81f-5f80-4771-b66b-cebd28ccdfc1",
                                      a6,
                                      0,
                                      (unsigned __int16 **)&sourceString,
                                      (unsigned __int16 **)&v98,
                                      (unsigned __int16 **)&hMem);
      if ( AadDeviceTokenWithDiscovery < 0 )
      {
        v8 = v99;
      }
      else
      {
        v8 = (unsigned __int16 *)v98;
        v9 = (const WCHAR *)hMem;
      }
      v99 = v8;
      Logger = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogAutoEnrollGetAadDeviceTokenWithDiscovery(Logger, AadDeviceTokenWithDiscovery, a6);
      if ( AadDeviceTokenWithDiscovery >= 0 )
      {
        v99 = v8;
      }
      else
      {
        v18 = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogAutoEnrollDmGetAadDeviceTokenFailure(v18, AadDeviceTokenWithDiscovery);
      }
    }
    else
    {
      AadDeviceTokenWithDiscovery = 0;
      v97 = 0;
      DeviceApplicaitonId = GetDeviceApplicaitonId((unsigned __int16 **)&v97);
      v20 = 0;
      if ( DeviceApplicaitonId != -2147024894 )
        v20 = DeviceApplicaitonId;
      v21 = (unsigned __int16 *)v97;
      if ( v20 >= 0 )
      {
        v22 = hMem;
        if ( hMem )
        {
          v23 = GetLastError();
          LocalFree(v22);
          SetLastError(v23);
        }
        hMem = 0;
        v24 = v98;
        if ( v98 )
        {
          v25 = GetLastError();
          LocalFree(v24);
          SetLastError(v25);
        }
        v98 = 0;
        v20 = DmGetAadDeviceTokenWithDiscovery(
                L"de50c81f-5f80-4771-b66b-cebd28ccdfc1",
                v21,
                0,
                (unsigned __int16 **)&sourceString,
                (unsigned __int16 **)&v98,
                (unsigned __int16 **)&hMem);
        if ( v20 >= 0 )
        {
          v99 = (unsigned __int16 *)v98;
          v9 = (const WCHAR *)hMem;
        }
      }
      v26 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogAutoEnrollGetAadDeviceTokenWithDiscovery(v26, v20, v21);
      if ( v20 < 0 )
      {
        v27 = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogAutoEnrollDmGetAadDeviceTokenFailure(v27, v20);
        if ( v7 )
          DmGetAadDeviceToken(L"de50c81f-5f80-4771-b66b-cebd28ccdfc1", v7, 0, (unsigned __int16 **)&sourceString);
      }
      if ( v21 )
        LocalFree(v21);
      v8 = v99;
    }
    goto LABEL_33;
  }
  v30 = 0;
  if ( !a1 )
  {
    AadDeviceTokenWithDiscovery = -2145910735;
LABEL_33:
    v28 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogAutoEnrollGetAadToken(
      v28,
      AadDeviceTokenWithDiscovery,
      v93[0],
      v7,
      (const unsigned __int16 *)v98);
    if ( AadDeviceTokenWithDiscovery >= 0 )
    {
      if ( v9 && v8 )
      {
        if ( sourceString )
        {
          if ( WindowsCreateStringReference(
                 L"Windows.Internal.Management.Enrollment.Enroller",
                 0x2Fu,
                 &hstringHeader,
                 &string) < 0 )
            RaiseException(0xC000000D, 1u, 0, 0);
          *(_QWORD *)v93 = 0;
          AadDeviceTokenWithDiscovery = Windows::Foundation::ActivateInstance<Windows::Internal::Management::Enrollment::IEnrollment>(
                                          string,
                                          v93);
          if ( AadDeviceTokenWithDiscovery >= 0 )
          {
            memset_0(v109, 0, 0x58u);
            v45 = v103;
            if ( !v103 )
              goto LABEL_105;
            v46 = -1;
            do
              ++v46;
            while ( v103[v46] );
            if ( v46 )
            {
              v47 = -1;
              do
                ++v47;
              while ( v103[v47] );
              v48 = v46 + 1;
              v49 = v103;
            }
            else
            {
LABEL_105:
              v48 = 1;
              v49 = (unsigned __int16 *)&String2;
            }
            WindowsCreateString(v49, v48, v109);
            v50 = -1;
            do
              ++v50;
            while ( v9[v50] );
            WindowsCreateString(v9, v50 + 1, &v109[1]);
            v51 = -1;
            do
              ++v51;
            while ( v8[v51] );
            WindowsCreateString(v7, v51 + 1, v112);
            v52 = -1;
            do
              ++v52;
            while ( sourceString[v52] );
            WindowsCreateString(sourceString, v52 + 1, v110);
            if ( v108 )
            {
              v53 = (const WCHAR *)*((_QWORD *)v108 + 4);
              if ( v53 )
              {
                do
                  ++v10;
                while ( v53[v10] );
                WindowsCreateString(v53, v10 + 1, v113);
              }
            }
            LODWORD(v111) = 0;
            LODWORD(v114) = 1;
            v54 = CEnrollmentLogger::GetLogger();
            StringRawBuffer = WindowsGetStringRawBuffer(v113[0], 0);
            CEnrollmentLogger::LogAutoEnrollEnrollmentInformation(v54, v9, v99, StringRawBuffer, v45);
            v92 = 0;
            v56 = **(_QWORD **)v93;
            v115[0] = *(_OWORD *)v109;
            v115[1] = *(_OWORD *)v110;
            v115[2] = v111;
            v115[3] = *(_OWORD *)v112;
            v115[4] = *(_OWORD *)v113;
            v116 = v114;
            AadDeviceTokenWithDiscovery = (*(__int64 (__fastcall **)(_QWORD, _OWORD *, __int64 *))(v56 + 72))(
                                            *(_QWORD *)v93,
                                            v115,
                                            &v92);
            if ( AadDeviceTokenWithDiscovery >= 0 )
            {
              AadDeviceTokenWithDiscovery = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> *>(v92);
              if ( AadDeviceTokenWithDiscovery >= 0 )
              {
                v95 = 0;
                AadDeviceTokenWithDiscovery = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v92 + 64LL))(
                                                v92,
                                                &v95);
                if ( AadDeviceTokenWithDiscovery >= 0 )
                {
                  v94 = 0;
                  v97 = 0;
                  AadDeviceTokenWithDiscovery = (**(__int64 (__fastcall ***)(__int64, GUID *, HLOCAL *))v92)(
                                                  v92,
                                                  &GUID_00000036_0000_0000_c000_000000000046,
                                                  &v94);
                  if ( AadDeviceTokenWithDiscovery >= 0 )
                  {
                    AadDeviceTokenWithDiscovery = (*(__int64 (__fastcall **)(__int64, HLOCAL *))(*(_QWORD *)v95 + 56LL))(
                                                    v95,
                                                    &v97);
                    if ( AadDeviceTokenWithDiscovery >= 0 )
                    {
                      v96 = 0;
                      AadDeviceTokenWithDiscovery = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v95 + 64LL))(
                                                      v95,
                                                      &v96);
                      if ( AadDeviceTokenWithDiscovery >= 0 )
                      {
                        AadDeviceTokenWithDiscovery = v96;
                        if ( v96 >= 0 )
                        {
                          v83 = 0;
                          if ( v96 != 1 )
                            v83 = v96;
                          AadDeviceTokenWithDiscovery = v83;
                          WindowsDeleteString(v109[0]);
                          WindowsDeleteString(v109[1]);
                          WindowsDeleteString(v110[0]);
                          WindowsDeleteString((HSTRING)v97);
                          v84 = v94;
                          if ( v94 )
                          {
                            v94 = 0;
                            (*(void (__fastcall **)(HLOCAL))(*(_QWORD *)v84 + 16LL))(v84);
                          }
                          v85 = v95;
                          if ( v95 )
                          {
                            v95 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
                          }
                          v86 = v92;
                          if ( v92 )
                          {
                            v92 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
                          }
                          v87 = *(__int64 **)v93;
                          if ( *(_QWORD *)v93 )
                          {
                            *(_QWORD *)v93 = 0;
                            (*(void (__fastcall **)(__int64 *))(*v87 + 16))(v87);
                          }
                        }
                        else
                        {
                          v79 = v94;
                          if ( v94 )
                          {
                            v94 = 0;
                            (*(void (__fastcall **)(HLOCAL))(*(_QWORD *)v79 + 16LL))(v79);
                          }
                          v80 = v95;
                          if ( v95 )
                          {
                            v95 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
                          }
                          v81 = v92;
                          if ( v92 )
                          {
                            v92 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
                          }
                          v82 = *(__int64 **)v93;
                          if ( *(_QWORD *)v93 )
                          {
                            *(_QWORD *)v93 = 0;
                            (*(void (__fastcall **)(__int64 *))(*v82 + 16))(v82);
                          }
                        }
                      }
                      else
                      {
                        v75 = v94;
                        if ( v94 )
                        {
                          v94 = 0;
                          (*(void (__fastcall **)(HLOCAL))(*(_QWORD *)v75 + 16LL))(v75);
                        }
                        v76 = v95;
                        if ( v95 )
                        {
                          v95 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
                        }
                        v77 = v92;
                        if ( v92 )
                        {
                          v92 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
                        }
                        v78 = *(__int64 **)v93;
                        if ( *(_QWORD *)v93 )
                        {
                          *(_QWORD *)v93 = 0;
                          (*(void (__fastcall **)(__int64 *))(*v78 + 16))(v78);
                        }
                      }
                    }
                    else
                    {
                      v71 = v94;
                      if ( v94 )
                      {
                        v94 = 0;
                        (*(void (__fastcall **)(HLOCAL))(*(_QWORD *)v71 + 16LL))(v71);
                      }
                      v72 = v95;
                      if ( v95 )
                      {
                        v95 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
                      }
                      v73 = v92;
                      if ( v92 )
                      {
                        v92 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
                      }
                      v74 = *(__int64 **)v93;
                      if ( *(_QWORD *)v93 )
                      {
                        *(_QWORD *)v93 = 0;
                        (*(void (__fastcall **)(__int64 *))(*v74 + 16))(v74);
                      }
                    }
                  }
                  else
                  {
                    v67 = v94;
                    if ( v94 )
                    {
                      v94 = 0;
                      (*(void (__fastcall **)(HLOCAL))(*(_QWORD *)v67 + 16LL))(v67);
                    }
                    v68 = v95;
                    if ( v95 )
                    {
                      v95 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
                    }
                    v69 = v92;
                    if ( v92 )
                    {
                      v92 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
                    }
                    v70 = *(__int64 **)v93;
                    if ( *(_QWORD *)v93 )
                    {
                      *(_QWORD *)v93 = 0;
                      (*(void (__fastcall **)(__int64 *))(*v70 + 16))(v70);
                    }
                  }
                }
                else
                {
                  v63 = CEnrollmentLogger::GetLogger();
                  CEnrollmentLogger::LogAutoEnrollGetAsyncResultsFailure(v63, AadDeviceTokenWithDiscovery);
                  v64 = v95;
                  if ( v95 )
                  {
                    v95 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
                  }
                  v65 = v92;
                  if ( v92 )
                  {
                    v92 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
                  }
                  v66 = *(__int64 **)v93;
                  if ( *(_QWORD *)v93 )
                  {
                    *(_QWORD *)v93 = 0;
                    (*(void (__fastcall **)(__int64 *))(*v66 + 16))(v66);
                  }
                }
              }
              else
              {
                v60 = CEnrollmentLogger::GetLogger();
                CEnrollmentLogger::LogAutoEnrollWaitForCompletiongNoThrowFailure(v60, AadDeviceTokenWithDiscovery);
                v61 = v92;
                if ( v92 )
                {
                  v92 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
                }
                v62 = *(__int64 **)v93;
                if ( *(_QWORD *)v93 )
                {
                  *(_QWORD *)v93 = 0;
                  (*(void (__fastcall **)(__int64 *))(*v62 + 16))(v62);
                }
              }
            }
            else
            {
              v57 = CEnrollmentLogger::GetLogger();
              CEnrollmentLogger::LogAutoEnrollAADEnrollAsyncFailure(v57, AadDeviceTokenWithDiscovery);
              v58 = v92;
              if ( v92 )
              {
                v92 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
              }
              v59 = *(__int64 **)v93;
              if ( *(_QWORD *)v93 )
              {
                *(_QWORD *)v93 = 0;
                (*(void (__fastcall **)(__int64 *))(*v59 + 16))(v59);
              }
            }
          }
          else
          {
            v29 = *(__int64 **)v93;
            if ( *(_QWORD *)v93 )
            {
              *(_QWORD *)v93 = 0;
              (*(void (__fastcall **)(__int64 *))(*v29 + 16))(v29);
            }
          }
        }
      }
      else
      {
        AadDeviceTokenWithDiscovery = -2145910735;
      }
    }
    goto LABEL_188;
  }
  v31 = CoInitializeEx(0, 0) >= 0;
  LODWORD(v92) = v31;
  LODWORD(v95) = CoInitializeSecurity(0, -1, 0, 0, 1u, 3u, 0, 0x40u, 0);
  v32 = 0;
  v104 = 0;
  v105 = 0;
  v96 = 0;
  DmIsRunningInSystemContext(&v96);
  if ( !v96 )
    goto LABEL_67;
  if ( a4 )
  {
    if ( ImpersonateLoggedOnUser(a4) )
    {
      v32 = 1;
      v104 = 1;
      v30 = 1;
      v105 = 1;
      AadDeviceTokenWithDiscovery = 0;
    }
    else
    {
      v33 = GetLastError();
      AadDeviceTokenWithDiscovery = v33;
      if ( v33 > 0 )
        AadDeviceTokenWithDiscovery = (unsigned __int16)v33 | 0x80070000;
    }
  }
  else
  {
    v94 = 0;
    string = (HSTRING)&v94;
    hstringHeader.Reserved.Reserved1 = 0;
    hstringHeader.Reserved.Reserved2[8] = 1;
    AadDeviceTokenWithDiscovery = DmGetActiveUserSid((unsigned __int16 **)&hstringHeader);
    if ( hstringHeader.Reserved.Reserved2[8] )
    {
      Reserved1 = hstringHeader.Reserved.Reserved1;
      v34 = string;
      v107 = string;
      v106 = *(HLOCAL *)string;
      if ( v106 )
      {
        v35 = GetLastError();
        LocalFree(v106);
        SetLastError(v35);
        v34 = v107;
      }
      *(_QWORD *)v34 = Reserved1;
    }
    if ( AadDeviceTokenWithDiscovery >= 0 )
    {
      AadDeviceTokenWithDiscovery = DmImpersonate((const unsigned __int16 *)v94);
      if ( AadDeviceTokenWithDiscovery >= 0 )
      {
        v32 = 1;
        v104 = 1;
        v30 = 1;
        v105 = 1;
      }
    }
    if ( v94 )
      LocalFree(v94);
  }
  if ( AadDeviceTokenWithDiscovery >= 0 )
  {
LABEL_67:
    v38 = (const unsigned __int16 *)v97;
    AadDeviceTokenWithDiscovery = DmGetAadUserToken(
                                    L"de50c81f-5f80-4771-b66b-cebd28ccdfc1",
                                    (const unsigned __int16 *)v97,
                                    0,
                                    (unsigned __int16 **)&sourceString,
                                    0);
    if ( AadDeviceTokenWithDiscovery != -895352820 )
    {
LABEL_89:
      v44 = 0;
      if ( v32 )
      {
        if ( v30 )
          v44 = DmRevertToSelf();
        else
          v44 = CoRevertToSelf();
      }
      if ( v44 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x2C,
          (unsigned int)"onecoreuap\\admin\\dm\\published\\inc\\dmraii.hxx",
          (const char *)(unsigned int)v44,
          dwAuthnLevela);
      if ( v31 )
        CoUninitialize();
      v8 = v99;
      v7 = v99;
      goto LABEL_33;
    }
    v39 = a5 == 0;
    LODWORD(v94) = v39;
    if ( a5 )
    {
      memset_0(Dst, 0, 0x208u);
      if ( !ExpandEnvironmentStringsW(L"%windir%\\system32\\deviceenroller.exe", Dst, 0x104u) )
      {
        v40 = GetLastError();
        AadDeviceTokenWithDiscovery = v40;
        if ( v40 > 0 )
          AadDeviceTokenWithDiscovery = (unsigned __int16)v40 | 0x80070000;
        v41 = 0;
        if ( v32 )
        {
          if ( v30 )
            v41 = DmRevertToSelf();
          else
            v41 = CoRevertToSelf();
        }
        if ( v41 < 0 )
          wil::details::in1diag3::_FailFast_Hr(
            retaddr,
            (void *)0x2C,
            (unsigned int)"onecoreuap\\admin\\dm\\published\\inc\\dmraii.hxx",
            (const char *)(unsigned int)v41,
            dwAuthnLevela);
        goto LABEL_65;
      }
      AadDeviceTokenWithDiscovery = DmRaiseToastNotificationAndWait(
                                      L"DMAppsRes.dll",
                                      0x65F4u,
                                      0x65F5u,
                                      0,
                                      Dst,
                                      L"AADJFROMDJ",
                                      (const struct _GUID *)qword_180066AA8,
                                      0x7530u,
                                      (int *)&v94);
      if ( AadDeviceTokenWithDiscovery == -2147024891 && (int)v95 < 0 )
        AadDeviceTokenWithDiscovery = v95;
      v39 = (int)v94;
      if ( !(_DWORD)v94 )
      {
        if ( AadDeviceTokenWithDiscovery >= 0 )
          AadDeviceTokenWithDiscovery = -2145910742;
        goto LABEL_85;
      }
      if ( AadDeviceTokenWithDiscovery < 0 )
      {
LABEL_85:
        v42 = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogAutoEnrollDmRaiseToastNotificationAndWaitFailure(v42, AadDeviceTokenWithDiscovery);
        v39 = (int)v94;
      }
    }
    if ( v39 )
    {
      AadDeviceTokenWithDiscovery = DmRequestAadUserToken(
                                      L"de50c81f-5f80-4771-b66b-cebd28ccdfc1",
                                      v38,
                                      0,
                                      (unsigned __int16 **)&sourceString);
      if ( AadDeviceTokenWithDiscovery < 0 )
      {
        v43 = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogAutoEnrollDmRequestAadUserTokenFailure(v43, AadDeviceTokenWithDiscovery);
      }
    }
    goto LABEL_89;
  }
  v36 = CEnrollmentLogger::GetLogger();
  CEnrollmentLogger::LogAutoEnrollImpersonateFailure(v36, AadDeviceTokenWithDiscovery);
  v37 = 0;
  if ( v32 )
  {
    if ( v30 )
      v37 = DmRevertToSelf();
    else
      v37 = CoRevertToSelf();
  }
  if ( v37 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\admin\\dm\\published\\inc\\dmraii.hxx",
      (const char *)(unsigned int)v37,
      dwAuthnLevel);
LABEL_65:
  if ( v31 )
    CoUninitialize();
LABEL_188:
  if ( hMem )
    LocalFree(hMem);
  if ( v98 )
    LocalFree(v98);
  v88 = (WCHAR *)sourceString;
  sourceString = 0;
  LocalFree(v88);
  return (unsigned int)AadDeviceTokenWithDiscovery;
}

```

## disassembly

```asm
0x180045ab8  push    rbp
0x180045aba  push    rbx
0x180045abb  push    rsi
0x180045abc  push    rdi
0x180045abd  push    r12
0x180045abf  push    r13
0x180045ac1  push    r14
0x180045ac3  push    r15
0x180045ac5  lea     rbp, [rsp-2E8h]
0x180045acd  sub     rsp, 3E8h
0x180045ad4  mov     rax, cs:__security_cookie
0x180045adb  xor     rax, rsp
0x180045ade  mov     [rbp+320h+var_50], rax
0x180045ae5  mov     rdi, r9
0x180045ae8  mov     [rsp+420h+var_3C8], r8d
0x180045aed  mov     [rbp+320h+var_350], rdx
0x180045af1  mov     r15, rcx
0x180045af4  mov     [rsp+420h+var_3A8], rcx
0x180045af9  mov     r14, [rbp+320h+arg_28]
0x180045b00  xor     esi, esi
0x180045b02  mov     [rbp+320h+sourceString], rsi
0x180045b06  mov     [rbp+320h+var_3A0], rsi
0x180045b0a  mov     [rbp+320h+hMem], rsi
0x180045b0e  mov     rbx, rcx
0x180045b11  mov     [rbp+320h+var_398], rcx
0x180045b15  test    rdx, rdx
0x180045b18  jz      short loc_180045B28
0x180045b1a  mov     rax, [rdx+28h]
0x180045b1e  mov     [rbp+320h+var_378], rax
0x180045b22  mov     r12, [rdx+38h]
0x180045b26  jmp     short loc_180045B2F
0x180045b28  mov     [rbp+320h+var_378], rsi
0x180045b2c  mov     r12, rsi
0x180045b2f  or      r13, 0FFFFFFFFFFFFFFFFh
0x180045b33  lea     ecx, [r13+2]
0x180045b37  test    r8d, r8d
0x180045b3a  jz      loc_180045EA5
0x180045b40  mov     rax, cs:Feature_Servicing_RegisterDeviceWithManagementUsingAADDeviceCredentials_27687908__descriptor
0x180045b47  mov     r8d, [rax]
0x180045b4a  test    r8b, 4
0x180045b4e  jnz     short loc_180045B68
0x180045b50  lea     rdx, [rbp+320h+var_380]
0x180045b54  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RegisterDeviceWithManagementUsingAADDeviceCredentials_27687908@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RegisterDeviceWithManagementUsingAADDeviceCredentials_27687908>::GetCachedFeatureEnabledState(void)
0x180045b59  mov     rcx, [rax]
0x180045b5c  mov     [rsp+420h+var_3A8], rcx
0x180045b61  mov     r8d, ecx
0x180045b64  lea     ecx, [r13+2]
0x180045b68  mov     dword ptr [rsp+420h+var_3D0], esi
0x180045b6c  mov     word ptr [rsp+420h+var_3D0+4], 3
0x180045b73  mov     r9d, r8d
0x180045b76  shr     r9d, 0Bh
0x180045b7a  and     r9d, ecx
0x180045b7d  shr     r8d, 0Ah
0x180045b81  and     r8d, ecx
0x180045b84  mov     [rsp+420h+dwImpLevel], ecx
0x180045b88  lea     rax, [rsp+420h+var_3D0]
0x180045b8d  mov     qword ptr [rsp+420h+dwAuthnLevel], rax
0x180045b92  mov     edx, 19E8FF8h
0x180045b97  lea     rcx, qword_180070FA0
0x180045b9e  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180045ba3  test    r14, r14
0x180045ba6  jz      loc_180045C99
0x180045bac  mov     rdi, [rbp+320h+hMem]
0x180045bb0  test    rdi, rdi
0x180045bb3  jz      short loc_180045BE0
0x180045bb5  call    cs:__imp_GetLastError
0x180045bbc  nop     dword ptr [rax+rax+00h]
0x180045bc1  mov     ebx, eax
0x180045bc3  mov     rcx, rdi; hMem
0x180045bc6  call    cs:__imp_LocalFree
0x180045bcd  nop     dword ptr [rax+rax+00h]
0x180045bd2  mov     ecx, ebx; dwErrCode
0x180045bd4  call    cs:__imp_SetLastError
0x180045bdb  nop     dword ptr [rax+rax+00h]
0x180045be0  mov     [rbp+320h+hMem], rsi
0x180045be4  mov     rdi, [rbp+320h+var_3A0]
0x180045be8  test    rdi, rdi
0x180045beb  jz      short loc_180045C18
0x180045bed  call    cs:__imp_GetLastError
0x180045bf4  nop     dword ptr [rax+rax+00h]
0x180045bf9  mov     ebx, eax
0x180045bfb  mov     rcx, rdi; hMem
0x180045bfe  call    cs:__imp_LocalFree
0x180045c05  nop     dword ptr [rax+rax+00h]
0x180045c0a  mov     ecx, ebx; dwErrCode
0x180045c0c  call    cs:__imp_SetLastError
0x180045c13  nop     dword ptr [rax+rax+00h]
0x180045c18  mov     [rbp+320h+var_3A0], rsi
0x180045c1c  lea     rax, [rbp+320h+hMem]
0x180045c20  mov     qword ptr [rsp+420h+dwImpLevel], rax
0x180045c25  lea     rax, [rbp+320h+var_3A0]
0x180045c29  mov     qword ptr [rsp+420h+dwAuthnLevel], rax
0x180045c2e  lea     r9, [rbp+320h+sourceString]
0x180045c32  xor     r8d, r8d
0x180045c35  mov     rdx, r14
0x180045c38  lea     rcx, aDe50c81f5f8047; "de50c81f-5f80-4771-b66b-cebd28ccdfc1"
0x180045c3f  call    cs:__imp_?DmGetAadDeviceTokenWithDiscovery@@YAJPEBG00PEAPEAG11@Z; DmGetAadDeviceTokenWithDiscovery(ushort const *,ushort const *,ushort const *,ushort * *,ushort * *,ushort * *)
0x180045c46  nop     dword ptr [rax+rax+00h]
0x180045c4b  mov     esi, eax
0x180045c4d  test    eax, eax
0x180045c4f  js      short loc_180045C5B
0x180045c51  mov     rbx, [rbp+320h+var_3A0]
0x180045c55  mov     r12, [rbp+320h+hMem]
0x180045c59  jmp     short loc_180045C5F
0x180045c5b  mov     rbx, [rbp+320h+var_398]
0x180045c5f  mov     [rbp+320h+var_398], rbx
0x180045c63  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180045c68  mov     r8, r14; unsigned __int16 *
0x180045c6b  mov     edx, esi; int
0x180045c6d  mov     rcx, rax; this
0x180045c70  call    ?LogAutoEnrollGetAadDeviceTokenWithDiscovery@CEnrollmentLogger@@QEAAXJPEBG@Z; CEnrollmentLogger::LogAutoEnrollGetAadDeviceTokenWithDiscovery(long,ushort const *)
0x180045c75  xor     r14d, r14d
0x180045c78  test    esi, esi
0x180045c7a  jns     short loc_180045C90
0x180045c7c  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180045c81  mov     edx, esi; int
0x180045c83  mov     rcx, rax; this
0x180045c86  call    ?LogAutoEnrollDmGetAadDeviceTokenFailure@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogAutoEnrollDmGetAadDeviceTokenFailure(long)
0x180045c8b  jmp     loc_180045DDB
0x180045c90  mov     [rbp+320h+var_398], rbx
0x180045c94  jmp     loc_180045DDB
0x180045c99  mov     esi, r14d
0x180045c9c  mov     [rsp+420h+var_3A8], r14
0x180045ca1  lea     rcx, [rsp+420h+var_3A8]; unsigned __int16 **
0x180045ca6  call    ?GetDeviceApplicaitonId@@YAJPEAPEAG@Z; GetDeviceApplicaitonId(ushort * *)
0x180045cab  mov     edi, r14d
0x180045cae  cmp     eax, 80070002h
0x180045cb3  cmovnz  edi, eax
0x180045cb6  mov     rbx, [rsp+420h+var_3A8]
0x180045cbb  test    edi, edi
0x180045cbd  js      loc_180045D7B
0x180045cc3  mov     r14, [rbp+320h+hMem]
0x180045cc7  test    r14, r14
0x180045cca  jz      short loc_180045CF7
0x180045ccc  call    cs:__imp_GetLastError
0x180045cd3  nop     dword ptr [rax+rax+00h]
0x180045cd8  mov     edi, eax
0x180045cda  mov     rcx, r14; hMem
0x180045cdd  call    cs:__imp_LocalFree
0x180045ce4  nop     dword ptr [rax+rax+00h]
0x180045ce9  mov     ecx, edi; dwErrCode
0x180045ceb  call    cs:__imp_SetLastError
0x180045cf2  nop     dword ptr [rax+rax+00h]
0x180045cf7  mov     [rbp+320h+hMem], 0
0x180045cff  mov     r14, [rbp+320h+var_3A0]
0x180045d03  test    r14, r14
0x180045d06  jz      short loc_180045D33
0x180045d08  call    cs:__imp_GetLastError
0x180045d0f  nop     dword ptr [rax+rax+00h]
0x180045d14  mov     edi, eax
0x180045d16  mov     rcx, r14; hMem
0x180045d19  call    cs:__imp_LocalFree
0x180045d20  nop     dword ptr [rax+rax+00h]
0x180045d25  mov     ecx, edi; dwErrCode
0x180045d27  call    cs:__imp_SetLastError
0x180045d2e  nop     dword ptr [rax+rax+00h]
0x180045d33  xor     r14d, r14d
0x180045d36  mov     [rbp+320h+var_3A0], r14
0x180045d3a  lea     rax, [rbp+320h+hMem]
0x180045d3e  mov     qword ptr [rsp+420h+dwImpLevel], rax
0x180045d43  lea     rax, [rbp+320h+var_3A0]
0x180045d47  mov     qword ptr [rsp+420h+dwAuthnLevel], rax
0x180045d4c  lea     r9, [rbp+320h+sourceString]
0x180045d50  xor     r8d, r8d
0x180045d53  mov     rdx, rbx
0x180045d56  lea     rcx, aDe50c81f5f8047; "de50c81f-5f80-4771-b66b-cebd28ccdfc1"
0x180045d5d  call    cs:__imp_?DmGetAadDeviceTokenWithDiscovery@@YAJPEBG00PEAPEAG11@Z; DmGetAadDeviceTokenWithDiscovery(ushort const *,ushort const *,ushort const *,ushort * *,ushort * *,ushort * *)
0x180045d64  nop     dword ptr [rax+rax+00h]
0x180045d69  mov     edi, eax
0x180045d6b  test    eax, eax
0x180045d6d  js      short loc_180045D7B
0x180045d6f  mov     r8, [rbp+320h+var_3A0]
0x180045d73  mov     [rbp+320h+var_398], r8
0x180045d77  mov     r12, [rbp+320h+hMem]
0x180045d7b  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180045d80  mov     r8, rbx; unsigned __int16 *
0x180045d83  mov     edx, edi; int
0x180045d85  mov     rcx, rax; this
0x180045d88  call    ?LogAutoEnrollGetAadDeviceTokenWithDiscovery@CEnrollmentLogger@@QEAAXJPEBG@Z; CEnrollmentLogger::LogAutoEnrollGetAadDeviceTokenWithDiscovery(long,ushort const *)
0x180045d8d  test    edi, edi
0x180045d8f  jns     short loc_180045DC3
0x180045d91  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180045d96  mov     edx, edi; int
0x180045d98  mov     rcx, rax; this
0x180045d9b  call    ?LogAutoEnrollDmGetAadDeviceTokenFailure@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogAutoEnrollDmGetAadDeviceTokenFailure(long)
0x180045da0  test    r15, r15
0x180045da3  jz      short loc_180045DC3
0x180045da5  lea     r9, [rbp+320h+sourceString]
0x180045da9  xor     r8d, r8d
0x180045dac  mov     rdx, r15
0x180045daf  lea     rcx, aDe50c81f5f8047; "de50c81f-5f80-4771-b66b-cebd28ccdfc1"
0x180045db6  call    cs:__imp_?DmGetAadDeviceToken@@YAJPEBG00PEAPEAG@Z; DmGetAadDeviceToken(ushort const *,ushort const *,ushort const *,ushort * *)
0x180045dbd  nop     dword ptr [rax+rax+00h]
0x180045dc2  nop
0x180045dc3  test    rbx, rbx
0x180045dc6  jz      short loc_180045DD7
0x180045dc8  mov     rcx, rbx; hMem
0x180045dcb  call    cs:__imp_LocalFree
0x180045dd2  nop     dword ptr [rax+rax+00h]
0x180045dd7  mov     rbx, [rbp+320h+var_398]
0x180045ddb  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180045de0  mov     rcx, [rbp+320h+var_3A0]
0x180045de4  mov     qword ptr [rsp+420h+dwAuthnLevel], rcx; unsigned __int16 *
0x180045de9  mov     r9, r15; unsigned __int16 *
0x180045dec  mov     r8d, [rsp+420h+var_3C8]; int
0x180045df1  mov     edx, esi; int
0x180045df3  mov     rcx, rax; this
0x180045df6  call    ?LogAutoEnrollGetAadToken@CEnrollmentLogger@@QEAAXJHPEBG0@Z; CEnrollmentLogger::LogAutoEnrollGetAadToken(long,int,ushort const *,ushort const *)
0x180045dfb  test    esi, esi
0x180045dfd  js      loc_180046897
0x180045e03  test    r12, r12
0x180045e06  jz      loc_180046892
0x180045e0c  test    rbx, rbx
0x180045e0f  jz      loc_180046892
0x180045e15  cmp     [rbp+320h+sourceString], r14
0x180045e19  jz      loc_180046897
0x180045e1f  lea     r9, [rbp+320h+string]; string
0x180045e26  lea     r8, [rbp+320h+hstringHeader]; hstringHeader
0x180045e2d  mov     edx, 2Fh ; '/'; length
0x180045e32  lea     rcx, ?RuntimeClass_Windows_Internal_Management_Enrollment_Enroller@@3QBGB; "Windows.Internal.Management.Enrollment."...
0x180045e39  call    cs:__imp_WindowsCreateStringReference
0x180045e40  nop     dword ptr [rax+rax+00h]
0x180045e45  test    eax, eax
0x180045e47  jns     short loc_180045E64
0x180045e49  xor     r9d, r9d; lpArguments
0x180045e4c  xor     r8d, r8d; nNumberOfArguments
0x180045e4f  lea     edx, [r9+1]; dwExceptionFlags
0x180045e53  mov     ecx, 0C000000Dh; dwExceptionCode
0x180045e58  call    cs:__imp_RaiseException
0x180045e5f  nop     dword ptr [rax+rax+00h]
0x180045e64  mov     qword ptr [rsp+420h+var_3C8], r14
0x180045e69  lea     rdx, [rsp+420h+var_3C8]
0x180045e6e  mov     rcx, [rbp+320h+string]
0x180045e75  call    ??$ActivateInstance@UIEnrollment@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIEnrollment@Enrollment@Management@Internal@1@@Z; Windows::Foundation::ActivateInstance<Windows::Internal::Management::Enrollment::IEnrollment>(HSTRING__ *,Windows::Internal::Management::Enrollment::IEnrollment * *)
0x180045e7a  mov     esi, eax
0x180045e7c  test    eax, eax
0x180045e7e  jns     loc_1800462D0
0x180045e84  mov     rcx, qword ptr [rsp+420h+var_3C8]
0x180045e89  test    rcx, rcx
0x180045e8c  jz      short loc_180045EA0
0x180045e8e  mov     qword ptr [rsp+420h+var_3C8], r14
0x180045e93  mov     rax, [rcx]
0x180045e96  mov     rax, [rax+10h]
0x180045e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e9f  nop
0x180045ea0  jmp     loc_180046897
0x180045ea5  xor     r14d, r14d
0x180045ea8  test    r15, r15
0x180045eab  jz      loc_1800462C6
0x180045eb1  mov     ebx, r14d
0x180045eb4  xor     edx, edx; dwCoInit
0x180045eb6  xor     ecx, ecx; pvReserved
0x180045eb8  call    cs:__imp_CoInitializeEx
0x180045ebf  nop     dword ptr [rax+rax+00h]
0x180045ec4  test    eax, eax
0x180045ec6  lea     esi, [r14+1]
0x180045eca  cmovns  ebx, esi
0x180045ecd  mov     dword ptr [rsp+420h+var_3D0], ebx
0x180045ed1  mov     [rsp+420h+pReserved3], r14; pReserved3
0x180045ed6  mov     [rsp+420h+dwCapabilities], 40h ; '@'; dwCapabilities
0x180045ede  mov     [rsp+420h+pAuthList], r14; pAuthList
0x180045ee3  mov     [rsp+420h+dwImpLevel], 3; dwImpLevel
0x180045eeb  mov     [rsp+420h+dwAuthnLevel], esi; int
0x180045eef  xor     r9d, r9d; pReserved1
0x180045ef2  xor     r8d, r8d; asAuthSvc
0x180045ef5  mov     edx, r13d; cAuthSvc
0x180045ef8  xor     ecx, ecx; pSecDesc
0x180045efa  call    cs:__imp_CoInitializeSecurity
0x180045f01  nop     dword ptr [rax+rax+00h]
0x180045f06  mov     dword ptr [rsp+420h+var_3B8], eax
0x180045f0a  mov     r15b, r14b
0x180045f0d  mov     [rbp+320h+var_370], r14b
0x180045f11  mov     [rbp+320h+var_36E], r14b
0x180045f15  mov     [rsp+420h+var_3B0], r14d
0x180045f1a  lea     rcx, [rsp+420h+var_3B0]
0x180045f1f  call    cs:__imp_?DmIsRunningInSystemContext@@YAJPEAH@Z; DmIsRunningInSystemContext(int *)
0x180045f26  nop     dword ptr [rax+rax+00h]
0x180045f2b  cmp     [rsp+420h+var_3B0], r14d
0x180045f30  jz      loc_1800460C9
0x180045f36  test    rdi, rdi
0x180045f39  jz      short loc_180045F87
0x180045f3b  mov     rcx, rdi; hToken
0x180045f3e  call    cs:__imp_ImpersonateLoggedOnUser
0x180045f45  nop     dword ptr [rax+rax+00h]
0x180045f4a  cmp     eax, esi
0x180045f4c  jnz     short loc_180045F63
0x180045f4e  mov     r15b, sil
0x180045f51  mov     [rbp+320h+var_370], sil
0x180045f55  mov     r14b, sil
0x180045f58  mov     [rbp+320h+var_36E], sil
0x180045f5c  xor     esi, esi
0x180045f5e  jmp     loc_180046064
0x180045f63  call    cs:__imp_GetLastError
0x180045f6a  nop     dword ptr [rax+rax+00h]
0x180045f6f  mov     esi, eax
0x180045f71  test    eax, eax
0x180045f73  jle     loc_180046064
0x180045f79  movzx   esi, ax
0x180045f7c  or      esi, 80070000h
0x180045f82  jmp     loc_180046064
  ... truncated ...
```
