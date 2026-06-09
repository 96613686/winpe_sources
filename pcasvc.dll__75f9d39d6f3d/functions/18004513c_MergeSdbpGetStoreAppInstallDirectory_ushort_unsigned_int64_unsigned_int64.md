# MergeSdbpGetStoreAppInstallDirectory(ushort *,unsigned __int64,unsigned __int64 *)

- ea: `0x18004513c`
- end: `0x1800468b8`
- name: `?MergeSdbpGetStoreAppInstallDirectory@@YAKPEAG_KPEA_K@Z`
- size: `6012`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180043424`

## callees

- `0x18000c018`
- `0x18000dc08`
- `0x180012920`
- `0x18003c608`
- `0x18003ccf8`
- `0x18003d87c`
- `0x18003fd8c`
- `0x18004513c`
- `0x18004eb34`
- `0x18004f958`
- `0x180096f60`
- `0x180097a30`
- `0x1800f1f10`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004520b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045fa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800466d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004520b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045fa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800466d7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800456be`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800456fa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800456be`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800456fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045664`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045664`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800452c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004531d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800452c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004531d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004518f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004524a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800452e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180045342`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004518f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004524a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800452e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180045342`

## string_xrefs

- `0x1800452df`: `Microsoft.ApplicationCompatibilityEnhancements`
- `0x18004539f`: `FindPackagesByUserSecurityIdNamePublisher failed (%d)`
- `0x1800451a5`: `WindowsCreateString failed (%d)`
- `0x18004526e`: `WindowsCreateString failed (%d)`
- `0x1800451ef`: `MergeSdbpGetStoreAppInstallDirectory`
- `0x180045275`: `MergeSdbpGetStoreAppInstallDirectory`
- `0x1800453ac`: `MergeSdbpGetStoreAppInstallDirectory`
- `0x18004542e`: `MergeSdbpGetStoreAppInstallDirectory`
- `0x1800454a8`: `MergeSdbpGetStoreAppInstallDirectory`
- `0x1800454ee`: `MergeSdbpGetStoreAppInstallDirectory`
- `0x180046507`: `get_Path failed (%d)`
- `0x180045670`: `%ls\AppXManifest.xml`
- `0x180045573`: `Package is installed but not registered, ignoring`
- `0x180046607`: `get_InstalledLocation failed (%d)`
- `0x1800458c0`: `%ls\ApplicationCompatibilityEnhancements.cat`
- `0x180046324`: `CoCreateInstance failed (%d)`
- `0x1800463e1`: `CoCreateInstance failed (%d)`
- `0x18004625d`: `CreateStreamOnFile failed (%d)`
- `0x18004618c`: `CreateManifestReader failed (%d)`
- `0x180045bfd`: `StringCchCopyW failed (%d)`
- `0x1800467dc`: `StringCchCopyW failed (%d)`
- `0x180045bb2`: `MoveNext failed (%d)`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall MergeSdbpGetStoreAppInstallDirectory(unsigned __int16 *a1, __int64 a2, unsigned __int64 *a3)
{
  HRESULT v4; // eax
  const char *v5; // r9
  int v6; // r8d
  int v7; // eax
  unsigned int v8; // ebx
  DWORD LastError; // eax
  HRESULT v10; // eax
  int v11; // r8d
  HSTRING v12; // rbx
  HRESULT v13; // eax
  HSTRING v14; // rbx
  HRESULT v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64 *); // rbx
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  int v24; // edx
  unsigned __int64 v25; // r13
  int v26; // eax
  int v27; // r8d
  int v28; // r9d
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 **)); // rbx
  int v33; // eax
  __int64 (__fastcall ***v34)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v35)(_QWORD, GUID *, __int64 **); // rdi
  int v36; // eax
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *StringRawBuffer; // r15
  int v40; // eax
  HRESULT v41; // eax
  HRESULT v42; // eax
  LPVOID v43; // rdi
  __int64 (__fastcall *v44)(LPVOID, unsigned __int16 *, __int64, _QWORD, int, __int64 *); // rbx
  int v45; // eax
  LPVOID v46; // rdi
  __int64 (__fastcall *v47)(LPVOID, __int64, __int64 *); // rbx
  int v48; // eax
  int v49; // eax
  int v50; // eax
  __int64 v51; // rcx
  LPVOID v52; // rcx
  LPVOID v53; // rcx
  __int64 v54; // rcx
  int v55; // eax
  unsigned __int8 **v56; // r8
  unsigned int *v57; // r9
  __int64 v58; // rcx
  LPVOID v59; // rcx
  LPVOID v60; // rcx
  __int64 v61; // rcx
  int v62; // eax
  __int64 v63; // rcx
  LPVOID v64; // rcx
  LPVOID v65; // rcx
  __int64 v66; // rcx
  int v67; // eax
  __int64 v68; // rcx
  LPVOID v69; // rcx
  LPVOID v70; // rcx
  __int64 v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rcx
  LPVOID v74; // rcx
  LPVOID v75; // rcx
  __int64 v76; // rcx
  __int64 v77; // rcx
  __int64 v78; // rcx
  LPVOID v79; // rcx
  LPVOID v80; // rcx
  __int64 v81; // rcx
  __int64 v82; // rcx
  __int64 v83; // rcx
  LPVOID v84; // rcx
  LPVOID v85; // rcx
  __int64 v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // rcx
  LPVOID v89; // rcx
  LPVOID v90; // rcx
  __int64 v91; // rcx
  __int64 v92; // rcx
  DWORD v93; // eax
  __int64 v94; // rcx
  LPVOID v95; // rcx
  LPVOID v96; // rcx
  __int64 v97; // rcx
  __int64 v98; // rcx
  __int64 v99; // rcx
  LPVOID v100; // rcx
  LPVOID v101; // rcx
  __int64 v102; // rcx
  __int64 v103; // rcx
  LPVOID v104; // rcx
  LPVOID v105; // rcx
  __int64 v106; // rcx
  __int64 v107; // rcx
  LPVOID v108; // rcx
  LPVOID v109; // rcx
  __int64 v110; // rcx
  __int64 v111; // rcx
  LPVOID v112; // rcx
  LPVOID v113; // rcx
  __int64 v114; // rcx
  __int64 v115; // rcx
  LPVOID v116; // rcx
  __int64 v117; // rcx
  __int64 v118; // rcx
  __int64 v119; // rcx
  __int64 v120; // rcx
  __int64 v121; // rcx
  __int64 v122; // rcx
  __int64 v123; // rcx
  __int64 v124; // rcx
  __int64 v125; // rcx
  __int64 v126; // rcx
  __int64 v127; // rcx
  __int64 v128; // rcx
  DWORD v129; // eax
  __int64 v130; // rcx
  __int64 v131; // rcx
  __int64 v132; // rcx
  __int64 v133; // rcx
  int v134; // eax
  __int64 v135; // rcx
  __int64 v136; // rcx
  unsigned int v138; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v139; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v140; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v141[8]; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v143; // [rsp+68h] [rbp-98h] BYREF
  HSTRING v144; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v145; // [rsp+78h] [rbp-88h] BYREF
  __int64 v146; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v147; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v148[8]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v149; // [rsp+98h] [rbp-68h] BYREF
  __int64 (__fastcall ***v150)(_QWORD, GUID *, __int64 **); // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v151; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING v152; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v153; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v154; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v155; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v156; // [rsp+D0h] [rbp-30h] BYREF
  int v157; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING string; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 *v159; // [rsp+E8h] [rbp-18h]
  unsigned __int16 v160[264]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v161[264]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int16 v162[264]; // [rsp+510h] [rbp+410h] BYREF

  v159 = a1;
  v138 = 0;
  v156 = 0;
  string = 0;
  v4 = WindowsCreateString(L"Windows.Management.Deployment.PackageManager", 0x2Cu, &string);
  if ( PcaFailedHr(&v138, v4) )
  {
    v5 = "WindowsCreateString failed (%d)";
    v6 = 882;
LABEL_5:
    v8 = v138;
LABEL_6:
    AslLogCallPrintf(1, (unsigned int)"MergeSdbpGetStoreAppInstallDirectory", v6, (_DWORD)v5);
    goto LABEL_252;
  }
  Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v156);
  v7 = Windows::Foundation::ActivateInstance<Windows::Management::Deployment::IPackageManager>(string, &v156);
  if ( PcaFailedHr(&v138, v7) )
  {
    v5 = "ActivateInstance failed (%d)";
    v6 = 888;
    goto LABEL_5;
  }
  if ( !v156 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 14;
    v8 = LastError;
    v5 = "ActivateInstance produced null (%d)";
    v6 = 896;
    goto LABEL_6;
  }
  v144 = 0;
  v143 = 0;
  v147 = 0;
  v10 = WindowsCreateString(&sourceString, 0, &v147);
  if ( PcaFailedHr(&v138, v10) )
  {
    v11 = 905;
LABEL_13:
    v8 = v138;
    AslLogCallPrintf(
      1,
      (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
      v11,
      (unsigned int)"WindowsCreateString failed (%d)");
LABEL_14:
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v143);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v144);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v147);
    goto LABEL_252;
  }
  v12 = v144;
  if ( v144 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v155);
    WindowsDeleteString(v12);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v155);
  }
  v144 = 0;
  v13 = WindowsCreateString(L"Microsoft.ApplicationCompatibilityEnhancements", 0x2Eu, &v144);
  if ( PcaFailedHr(&v138, v13) )
  {
    v11 = 909;
    goto LABEL_13;
  }
  v14 = v143;
  if ( v143 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v155);
    WindowsDeleteString(v14);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v155);
  }
  v143 = 0;
  v15 = WindowsCreateString(
          L"CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US",
          0x50u,
          &v143);
  if ( PcaFailedHr(&v138, v15) )
  {
    v11 = 913;
    goto LABEL_13;
  }
  v140 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, __int64 *))(*(_QWORD *)v156 + 104LL))(
          v156,
          v144,
          v143,
          &v140);
  if ( PcaFailedHr(&v138, v16) )
  {
    v8 = v138;
    AslLogCallPrintf(
      1,
      (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
      919,
      (unsigned int)"FindPackagesByUserSecurityIdNamePublisher failed (%d)");
    v17 = v140;
    if ( v140 )
    {
      v140 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    goto LABEL_14;
  }
  v146 = 0;
  v18 = v140;
  v19 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v140 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v146);
  v20 = v19(v18, &v146);
  if ( PcaFailedHr(&v138, v20) )
  {
    v8 = v138;
    AslLogCallPrintf(1, (unsigned int)"MergeSdbpGetStoreAppInstallDirectory", 925, (unsigned int)"First failed (%d)");
    Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v146);
    v21 = v140;
    if ( v140 )
    {
      v140 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    goto LABEL_14;
  }
  v141[0] = 0;
  v22 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v146 + 56LL))(v146, v141);
  if ( PcaFailedHr(&v138, v22) )
  {
    v8 = v138;
    AslLogCallPrintf(
      1,
      (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
      931,
      (unsigned int)"get_HasCurrent failed (%d)");
    Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v146);
    v23 = v140;
    if ( v140 )
    {
      v140 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    goto LABEL_14;
  }
  v24 = 0;
  v25 = 0;
  v160[0] = 0;
  do
  {
    if ( !v141[0] )
      break;
    v139 = 0;
    v26 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v146 + 48LL))(v146, &v139);
    if ( PcaFailedHr(&v138, v26) )
    {
      v8 = v138;
      AslLogCallPrintf(
        1,
        (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
        947,
        (unsigned int)"get_Current failed (%d)");
      v132 = v139;
      if ( v139 )
      {
        v139 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v132 + 16LL))(v132);
      }
      Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v146);
      v133 = v140;
      if ( v140 )
      {
        v140 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v133 + 16LL))(v133);
      }
      goto LABEL_14;
    }
    if ( !v139 )
    {
      v129 = GetLastError();
      if ( !v129 )
        v129 = 14;
      v8 = v129;
      AslLogCallPrintf(
        1,
        (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
        955,
        (unsigned int)"get_Current produced null (%d)");
      v130 = v139;
      if ( v139 )
      {
        v139 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v130 + 16LL))(v130);
      }
      Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v146);
      v131 = v140;
      if ( v140 )
      {
        v140 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v131 + 16LL))(v131);
      }
      goto LABEL_14;
    }
    v148[0] = 0;
    v29 = IsPackageRegistered((unsigned int)&v156, (unsigned int)&v139, v27, v28, (__int64)v148);
    if ( PcaFailedHr(&v138, v29) )
    {
      v8 = v138;
      AslLogCallPrintf(
        1,
        (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
        961,
        (unsigned int)"Failed to check if package is registered (%d)");
      v127 = v139;
      if ( v139 )
      {
        v139 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 16LL))(v127);
      }
      Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v146);
      v128 = v140;
      if ( v140 )
      {
        v140 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v128 + 16LL))(v128);
      }
      goto LABEL_14;
    }
    if ( v148[0] )
    {
      v150 = 0;
      v31 = v139;
      v32 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 **)))(*(_QWORD *)v139 + 56LL);
      Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
      v33 = v32(v31, &v150);
      if ( PcaFailedHr(&v138, v33) )
      {
        v8 = v138;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
          971,
          (unsigned int)"get_InstalledLocation failed (%d)");
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
        v125 = v139;
        if ( v139 )
        {
          v139 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v125 + 16LL))(v125);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v146);
        v126 = v140;
        if ( v140 )
        {
          v140 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v126 + 16LL))(v126);
        }
        goto LABEL_14;
      }
      v151 = 0;
      v34 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v150;
      v35 = **v150;
      Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v151);
      v36 = v35(v34, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, &v151);
      if ( PcaFailedHr(&v138, v36) )
      {
        v8 = v138;
        AslLogCallPrintf(1, (unsigned int)"MergeSdbpGetStoreAppInstallDirectory", 977, (unsigned int)"As failed (%d)");
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v151);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
        v123 = v139;
        if ( v139 )
        {
          v139 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v146);
        v124 = v140;
        if ( v140 )
        {
          v140 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v124 + 16LL))(v124);
        }
        goto LABEL_14;
      }
      v152 = 0;
      v37 = *v151;
      v152 = 0;
      v38 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v37 + 96))(v151, &v152);
      if ( PcaFailedHr(&v138, v38) )
      {
        v8 = v138;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
          983,
          (unsigned int)"get_Path failed (%d)");
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v152);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v151);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
        v121 = v139;
        if ( v139 )
        {
          v139 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v121 + 16LL))(v121);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v146);
        v122 = v140;
        if ( v140 )
        {
          v140 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
        }
        goto LABEL_14;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(v152, 0);
      v40 = StringCchPrintfW(v161, 0x104u, L"%ls\\AppXManifest.xml", StringRawBuffer);
      if ( PcaFailedHr(&v138, v40) )
      {
        v8 = v138;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
          995,
          (unsigned int)"StringCchPrintfW failed (%d)");
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v152);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v151);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
        v119 = v139;
        if ( v139 )
        {
          v139 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v119 + 16LL))(v119);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v146);
        v120 = v140;
        if ( v140 )
        {
          v140 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v120 + 16LL))(v120);
        }
        goto LABEL_14;
      }
      ppv = 0;
      v41 = CoCreateInstance(
              &GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781,
              0,
              1u,
              &GUID_beb94909_e451_438b_b5a7_d79e767b75d8,
              &ppv);
      if ( PcaFailedHr(&v138, v41) )
      {
        v8 = v138;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
          1004,
          (unsigned int)"CoCreateInstance failed (%d)");
        v116 = ppv;
        if ( ppv )
        {
          ppv = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v116 + 16LL))(v116);
        }
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v152);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v151);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
        v117 = v139;
        if ( v139 )
        {
          v139 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v117 + 16LL))(v117);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v146);
        v118 = v140;
        if ( v140 )
        {
          v140 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v118 + 16LL))(v118);
        }
        goto LABEL_14;
      }
      v145 = 0;
      v42 = CoCreateInstance(
              &GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e,
              0,
              1u,
              &GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154,
              &v145);
      if ( PcaFailedHr(&v138, v42) )
      {
        v8 = v138;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
          1013,
          (unsigned int)"CoCreateInstance failed (%d)");
        v112 = v145;
        if ( v145 )
        {
          v145 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v112 + 16LL))(v112);
        }
        v113 = ppv;
        if ( ppv )
        {
          ppv = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v113 + 16LL))(v113);
        }
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v152);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v151);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
        v114 = v139;
        if ( v139 )
        {
          v139 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v114 + 16LL))(v114);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v146);
        v115 = v140;
        if ( v140 )
        {
          v140 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v115 + 16LL))(v115);
        }
        goto LABEL_14;
      }
      v153 = 0;
      v43 = v145;
      v44 = *(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, __int64, _QWORD, int, __int64 *))(*(_QWORD *)v145
                                                                                                  + 40LL);
      Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v153);
      v45 = v44(v43, v161, 1, 0, 128, &v153);
      if ( PcaFailedHr(&v138, v45) )
      {
        v8 = v138;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
          1023,
          (unsigned int)"CreateStreamOnFile failed (%d)");
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v153);
        v108 = v145;
        if ( v145 )
        {
          v145 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v108 + 16LL))(v108);
        }
        v109 = ppv;
        if ( ppv )
        {
          ppv = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v109 + 16LL))(v109);
        }
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v152);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v151);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
        v110 = v139;
        if ( v139 )
        {
          v139 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v146);
        v111 = v140;
        if ( v140 )
        {
          v140 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
        }
        goto LABEL_14;
      }
      v154 = 0;
      v46 = ppv;
      v47 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 40LL);
      Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
      v48 = v47(v46, v153, &v154);
      if ( PcaFailedHr(&v138, v48) )
      {
        v8 = v138;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
          1029,
          (unsigned int)"CreateManifestReader failed (%d)");
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v153);
        v104 = v145;
        if ( v145 )
        {
          v145 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v104 + 16LL))(v104);
        }
        v105 = ppv;
        if ( ppv )
        {
          ppv = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v105 + 16LL))(v105);
        }
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v152);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v151);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
        v106 = v139;
        if ( v139 )
        {
          v139 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v146);
        v107 = v140;
        if ( v140 )
        {
          v140 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
        }
        goto LABEL_14;
      }
      v149 = 0;
      v49 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v154 + 24LL))(v154, &v149);
      if ( PcaFailedHr(&v138, v49) )
      {
        v8 = v138;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
          1035,
          (unsigned int)"GetPackageId failed (%d)");
        v99 = v149;
        if ( v149 )
        {
          v149 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v153);
        v100 = v145;
        if ( v145 )
        {
          v145 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v100 + 16LL))(v100);
        }
        v101 = ppv;
        if ( ppv )
        {
          ppv = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v101 + 16LL))(v101);
        }
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v152);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v151);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
        v102 = v139;
        if ( v139 )
        {
          v139 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v102 + 16LL))(v102);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v146);
        v103 = v140;
        if ( v140 )
        {
          v140 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v103 + 16LL))(v103);
        }
        goto LABEL_14;
      }
      if ( !v149 )
      {
        v93 = GetLastError();
        if ( !v93 )
          v93 = 14;
        v8 = v93;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
          1043,
          (unsigned int)"GetPackageId returned null (%d)");
        v94 = v149;
        if ( v149 )
        {
          v149 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v153);
        v95 = v145;
        if ( v145 )
        {
          v145 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v95 + 16LL))(v95);
        }
        v96 = ppv;
        if ( ppv )
        {
          ppv = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v96 + 16LL))(v96);
        }
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v152);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v151);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
        v97 = v139;
        if ( v139 )
        {
          v139 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v146);
        v98 = v140;
        if ( v140 )
        {
          v140 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
        }
        goto LABEL_14;
      }
      v157 = 0;
      v50 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v149 + 32LL))(v149, &v157);
      if ( PcaFailedHr(&v138, v50) )
      {
        v8 = v138;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
          1049,
          (unsigned int)"GetArchitecture failed (%d)");
        v88 = v149;
        if ( v149 )
        {
          v149 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v153);
        v89 = v145;
        if ( v145 )
        {
          v145 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v89 + 16LL))(v89);
        }
        v90 = ppv;
        if ( ppv )
        {
          ppv = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v90 + 16LL))(v90);
        }
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v152);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v151);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
        v91 = v139;
        if ( v139 )
        {
          v139 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v146);
        v92 = v140;
        if ( v140 )
        {
          v140 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
        }
        goto LABEL_14;
      }
      if ( v157 == 9 )
      {
        v55 = StringCchPrintfW(v162, 0x104u, L"%ls\\ApplicationCompatibilityEnhancements.cat", StringRawBuffer);
        if ( PcaFailedHr(&v138, v55) )
        {
          v8 = v138;
          AslLogCallPrintf(
            1,
            (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
            1083,
            (unsigned int)"StringCchPrintfW failed (%d)");
          v83 = v149;
          if ( v149 )
          {
            v149 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
          }
          Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
          Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v153);
          v84 = v145;
          if ( v145 )
          {
            v145 = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v84 + 16LL))(v84);
          }
          v85 = ppv;
          if ( ppv )
          {
            ppv = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v85 + 16LL))(v85);
          }
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v152);
          Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v151);
          Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
          v86 = v139;
          if ( v139 )
          {
            v139 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
          }
          Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v146);
          v87 = v140;
          if ( v140 )
          {
            v140 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
          }
          goto LABEL_14;
        }
        v138 = MergeSdbpVerifySignatureAgainstCatalog(v161, v162, v56, v57);
        if ( v138 )
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
            1088,
            (unsigned int)"MergeSdbpVerifySignatureAgainstCatalog failed, ignoring this app instance (%d)");
          v58 = v149;
          if ( v149 )
          {
            v149 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
          }
          Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
          Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v153);
          v59 = v145;
          if ( v145 )
          {
            v145 = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v59 + 16LL))(v59);
          }
          v60 = ppv;
          if ( ppv )
          {
            ppv = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v60 + 16LL))(v60);
          }
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v152);
          Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v151);
          Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
          v61 = v139;
          if ( v139 )
          {
            v139 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
          }
        }
        else
        {
          v155 = 0;
          v62 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v149 + 48LL))(v149, &v155);
          if ( PcaFailedHr(&v138, v62) )
          {
            v8 = v138;
            AslLogCallPrintf(
              1,
              (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
              1094,
              (unsigned int)"GetVersion failed (%d)");
            v78 = v149;
            if ( v149 )
            {
              v149 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
            }
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v153);
            v79 = v145;
            if ( v145 )
            {
              v145 = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v79 + 16LL))(v79);
            }
            v80 = ppv;
            if ( ppv )
            {
              ppv = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v80 + 16LL))(v80);
            }
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v152);
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v151);
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
            v81 = v139;
            if ( v139 )
            {
              v139 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
            }
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v146);
            v82 = v140;
            if ( v140 )
            {
              v140 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
            }
            goto LABEL_14;
          }
          if ( v155 > v25 )
          {
            v67 = StringCchCopyW(v160, 0x104u, StringRawBuffer);
            if ( PcaFailedHr(&v138, v67) )
            {
              v8 = v138;
              AslLogCallPrintf(
                1,
                (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
                1109,
                (unsigned int)"StringCchCopyW failed (%d)");
              v73 = v149;
              if ( v149 )
              {
                v149 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
              }
              Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
              Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v153);
              v74 = v145;
              if ( v145 )
              {
                v145 = 0;
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v74 + 16LL))(v74);
              }
              v75 = ppv;
              if ( ppv )
              {
                ppv = 0;
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v75 + 16LL))(v75);
              }
              wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v152);
              Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v151);
              Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
              v76 = v139;
              if ( v139 )
              {
                v139 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
              }
              Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v146);
              v77 = v140;
              if ( v140 )
              {
                v140 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
              }
              goto LABEL_14;
            }
            v25 = v155;
            if ( a3 )
              *a3 = v155;
            v68 = v149;
            if ( v149 )
            {
              v149 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
            }
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v153);
            v69 = v145;
            if ( v145 )
            {
              v145 = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v69 + 16LL))(v69);
            }
            v70 = ppv;
            if ( ppv )
            {
              ppv = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v70 + 16LL))(v70);
            }
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v152);
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v151);
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
            v71 = v139;
            if ( v139 )
            {
              v139 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
            }
          }
          else
          {
            v63 = v149;
            if ( v149 )
            {
              v149 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
            }
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v153);
            v64 = v145;
            if ( v145 )
            {
              v145 = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v64 + 16LL))(v64);
            }
            v65 = ppv;
            if ( ppv )
            {
              ppv = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v65 + 16LL))(v65);
            }
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v152);
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v151);
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
            v66 = v139;
            if ( v139 )
            {
              v139 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
            }
          }
        }
      }
      else
      {
        v51 = v149;
        if ( v149 )
        {
          v149 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v153);
        v52 = v145;
        if ( v145 )
        {
          v145 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v52 + 16LL))(v52);
        }
        v53 = ppv;
        if ( ppv )
        {
          ppv = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v53 + 16LL))(v53);
        }
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v152);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v151);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
        v54 = v139;
        if ( v139 )
        {
          v139 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
        }
      }
    }
    else
    {
      AslLogCallPrintf(
        0,
        (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
        965,
        (unsigned int)"Package is installed but not registered, ignoring");
      v30 = v139;
      if ( v139 )
      {
        v139 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
    }
    v24 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v146 + 64LL))(v146, v141);
  }
  while ( v24 >= 0 );
  if ( PcaFailedHr(&v138, v24) )
  {
    v8 = v138;
    AslLogCallPrintf(
      1,
      (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
      1119,
      (unsigned int)"MoveNext failed (%d)");
    Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v146);
    v72 = v140;
    if ( v140 )
    {
      v140 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
    }
    goto LABEL_14;
  }
  v134 = StringCchCopyW(v159, 0x104u, v160);
  if ( PcaFailedHr(&v138, v134) )
  {
    v8 = v138;
    AslLogCallPrintf(
      1,
      (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
      1124,
      (unsigned int)"StringCchCopyW failed (%d)");
    Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v146);
    v135 = v140;
    if ( v140 )
    {
      v140 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v135 + 16LL))(v135);
    }
    goto LABEL_14;
  }
  if ( a3 && !v160[0] )
    *a3 = -1;
  Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v146);
  v136 = v140;
  if ( v140 )
  {
    v140 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v136 + 16LL))(v136);
  }
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v143);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v144);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v147);
  v8 = 0;
LABEL_252:
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
  Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v156);
  return v8;
}

```

## disassembly

```asm
0x18004513c  mov     [rsp-8+arg_8], rbx
0x180045141  push    rbp
0x180045142  push    rsi
0x180045143  push    rdi
0x180045144  push    r12
0x180045146  push    r13
0x180045148  push    r14
0x18004514a  push    r15
0x18004514c  lea     rbp, [rsp-630h]
0x180045154  sub     rsp, 730h
0x18004515b  mov     rax, cs:__security_cookie
0x180045162  xor     rax, rsp
0x180045165  mov     [rbp+660h+var_40], rax
0x18004516c  mov     r12, r8
0x18004516f  mov     [rbp+660h+var_678], rcx
0x180045173  xor     edi, edi
0x180045175  mov     [rsp+760h+var_720], edi
0x180045179  mov     [rbp+660h+var_690], rdi
0x18004517d  mov     [rbp+660h+string], rdi
0x180045181  lea     r8, [rbp+660h+string]; string
0x180045185  lea     edx, [rdi+2Ch]; length
0x180045188  lea     rcx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x18004518f  call    cs:__imp_WindowsCreateString
0x180045195  mov     edx, eax; int
0x180045197  lea     rcx, [rsp+760h+var_720]; unsigned int *
0x18004519c  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x1800451a1  test    al, al
0x1800451a3  jz      short loc_1800451B4
0x1800451a5  lea     r9, aWindowscreates_1; "WindowsCreateString failed (%d)"
0x1800451ac  mov     r8d, 372h
0x1800451b2  jmp     short loc_1800451E7
0x1800451b4  lea     rcx, [rbp+660h+var_690]
0x1800451b8  call    ?InternalRelease@?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(void)
0x1800451bd  lea     rdx, [rbp+660h+var_690]
0x1800451c1  mov     rcx, [rbp+660h+string]
0x1800451c5  call    ??$ActivateInstance@UIPackageManager@Deployment@Management@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIPackageManager@Deployment@Management@1@@Z; Windows::Foundation::ActivateInstance<Windows::Management::Deployment::IPackageManager>(HSTRING__ *,Windows::Management::Deployment::IPackageManager * *)
0x1800451ca  mov     edx, eax; int
0x1800451cc  lea     rcx, [rsp+760h+var_720]; unsigned int *
0x1800451d1  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x1800451d6  test    al, al
0x1800451d8  jz      short loc_180045205
0x1800451da  lea     r9, aActivateinstan; "ActivateInstance failed (%d)"
0x1800451e1  mov     r8d, 378h
0x1800451e7  mov     ebx, [rsp+760h+var_720]
0x1800451eb  mov     dword ptr [rsp+760h+ppv], ebx
0x1800451ef  lea     rdx, aMergesdbpgetst_1; "MergeSdbpGetStoreAppInstallDirectory"
0x1800451f6  mov     ecx, 1
0x1800451fb  call    AslLogCallPrintf
0x180045200  jmp     loc_180046879
0x180045205  cmp     [rbp+660h+var_690], rdi
0x180045209  jnz     short loc_18004522F
0x18004520b  call    cs:__imp_GetLastError
0x180045211  test    eax, eax
0x180045213  jnz     short loc_18004521A
0x180045215  mov     eax, 0Eh
0x18004521a  mov     ebx, eax
0x18004521c  mov     dword ptr [rsp+760h+ppv], eax
0x180045220  lea     r9, aActivateinstan_0; "ActivateInstance produced null (%d)"
0x180045227  mov     r8d, 380h
0x18004522d  jmp     short loc_1800451EF
0x18004522f  mov     [rsp+760h+var_6F0], rdi
0x180045234  mov     [rsp+760h+var_6F8], rdi
0x180045239  mov     [rbp+660h+var_6D8], rdi
0x18004523d  lea     r8, [rbp+660h+var_6D8]; string
0x180045241  xor     edx, edx; length
0x180045243  lea     rcx, sourceString; sourceString
0x18004524a  call    cs:__imp_WindowsCreateString
0x180045250  mov     edx, eax; int
0x180045252  lea     rcx, [rsp+760h+var_720]; unsigned int *
0x180045257  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x18004525c  test    al, al
0x18004525e  jz      short loc_1800452AB
0x180045260  mov     r8d, 389h
0x180045266  mov     ebx, [rsp+760h+var_720]
0x18004526a  mov     dword ptr [rsp+760h+ppv], ebx
0x18004526e  lea     r9, aWindowscreates_1; "WindowsCreateString failed (%d)"
0x180045275  lea     rdx, aMergesdbpgetst_1; "MergeSdbpGetStoreAppInstallDirectory"
0x18004527c  mov     ecx, 1
0x180045281  call    AslLogCallPrintf
0x180045286  nop
0x180045287  lea     rcx, [rsp+760h+var_6F8]
0x18004528c  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180045291  nop
0x180045292  lea     rcx, [rsp+760h+var_6F0]
0x180045297  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18004529c  nop
0x18004529d  lea     rcx, [rbp+660h+var_6D8]
0x1800452a1  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800452a6  jmp     loc_180046879
0x1800452ab  mov     rbx, [rsp+760h+var_6F0]
0x1800452b0  test    rbx, rbx
0x1800452b3  jz      short loc_1800452D0
0x1800452b5  lea     rcx, [rbp+660h+var_698]; this
0x1800452b9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800452be  mov     rcx, rbx; string
0x1800452c1  call    cs:__imp_WindowsDeleteString
0x1800452c7  lea     rcx, [rbp+660h+var_698]; this
0x1800452cb  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800452d0  mov     [rsp+760h+var_6F0], rdi
0x1800452d5  lea     r8, [rsp+760h+var_6F0]; string
0x1800452da  mov     edx, 2Eh ; '.'; length
0x1800452df  lea     rcx, aMicrosoftAppli; "Microsoft.ApplicationCompatibilityEnhan"...
0x1800452e6  call    cs:__imp_WindowsCreateString
0x1800452ec  mov     edx, eax; int
0x1800452ee  lea     rcx, [rsp+760h+var_720]; unsigned int *
0x1800452f3  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x1800452f8  test    al, al
0x1800452fa  jz      short loc_180045307
0x1800452fc  mov     r8d, 38Dh
0x180045302  jmp     loc_180045266
0x180045307  mov     rbx, [rsp+760h+var_6F8]
0x18004530c  test    rbx, rbx
0x18004530f  jz      short loc_18004532C
0x180045311  lea     rcx, [rbp+660h+var_698]; this
0x180045315  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004531a  mov     rcx, rbx; string
0x18004531d  call    cs:__imp_WindowsDeleteString
0x180045323  lea     rcx, [rbp+660h+var_698]; this
0x180045327  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004532c  mov     [rsp+760h+var_6F8], rdi
0x180045331  lea     r8, [rsp+760h+var_6F8]; string
0x180045336  mov     edx, 50h ; 'P'; length
0x18004533b  lea     rcx, aCnMicrosoftCor; "CN=Microsoft Corporation, O=Microsoft C"...
0x180045342  call    cs:__imp_WindowsCreateString
0x180045348  mov     edx, eax; int
0x18004534a  lea     rcx, [rsp+760h+var_720]; unsigned int *
0x18004534f  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x180045354  test    al, al
0x180045356  jz      short loc_180045363
0x180045358  mov     r8d, 391h
0x18004535e  jmp     loc_180045266
0x180045363  mov     [rsp+760h+var_710], rdi
0x180045368  mov     rcx, [rbp+660h+var_690]
0x18004536c  mov     rax, [rcx]
0x18004536f  lea     r9, [rsp+760h+var_710]
0x180045374  mov     r8, [rsp+760h+var_6F8]
0x180045379  mov     rdx, [rsp+760h+var_6F0]
0x18004537e  mov     rax, [rax+68h]
0x180045382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045387  mov     edx, eax; int
0x180045389  lea     rcx, [rsp+760h+var_720]; unsigned int *
0x18004538e  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x180045393  test    al, al
0x180045395  jz      short loc_1800453DF
0x180045397  mov     ebx, [rsp+760h+var_720]
0x18004539b  mov     dword ptr [rsp+760h+ppv], ebx
0x18004539f  lea     r9, aFindpackagesby; "FindPackagesByUserSecurityIdNamePublish"...
0x1800453a6  mov     r8d, 397h
0x1800453ac  lea     rdx, aMergesdbpgetst_1; "MergeSdbpGetStoreAppInstallDirectory"
0x1800453b3  mov     ecx, 1
0x1800453b8  call    AslLogCallPrintf
0x1800453bd  nop
0x1800453be  mov     rcx, [rsp+760h+var_710]
0x1800453c3  test    rcx, rcx
0x1800453c6  jz      short loc_1800453DA
0x1800453c8  mov     [rsp+760h+var_710], rdi
0x1800453cd  mov     rax, [rcx]
0x1800453d0  mov     rax, [rax+10h]
0x1800453d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800453d9  nop
0x1800453da  jmp     loc_180045287
0x1800453df  mov     [rbp+660h+var_6E0], rdi
0x1800453e3  mov     rdi, [rsp+760h+var_710]
0x1800453e8  mov     rax, [rdi]
0x1800453eb  mov     rbx, [rax+30h]
0x1800453ef  lea     rcx, [rbp+660h+var_6E0]
0x1800453f3  call    ?InternalRelease@?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(void)
0x1800453f8  lea     rdx, [rbp+660h+var_6E0]
0x1800453fc  mov     rcx, rdi
0x1800453ff  mov     rax, rbx
0x180045402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045407  mov     edx, eax; int
0x180045409  lea     rcx, [rsp+760h+var_720]; unsigned int *
0x18004540e  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x180045413  xor     edi, edi
0x180045415  test    al, al
0x180045417  jz      short loc_180045469
0x180045419  mov     ebx, [rsp+760h+var_720]
0x18004541d  mov     dword ptr [rsp+760h+ppv], ebx
0x180045421  lea     r9, aFirstFailedD; "First failed (%d)"
0x180045428  mov     r8d, 39Dh
0x18004542e  lea     rdx, aMergesdbpgetst_1; "MergeSdbpGetStoreAppInstallDirectory"
0x180045435  lea     ecx, [rdi+1]
0x180045438  call    AslLogCallPrintf
0x18004543d  nop
0x18004543e  lea     rcx, [rbp+660h+var_6E0]
0x180045442  call    ?InternalRelease@?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(void)
0x180045447  nop
0x180045448  mov     rcx, [rsp+760h+var_710]
0x18004544d  test    rcx, rcx
0x180045450  jz      short loc_180045464
0x180045452  mov     [rsp+760h+var_710], rdi
0x180045457  mov     rax, [rcx]
0x18004545a  mov     rax, [rax+10h]
0x18004545e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045463  nop
0x180045464  jmp     loc_180045287
0x180045469  mov     [rsp+760h+var_708], dil
0x18004546e  mov     rcx, [rbp+660h+var_6E0]
0x180045472  mov     rax, [rcx]
0x180045475  lea     rdx, [rsp+760h+var_708]
0x18004547a  mov     rax, [rax+38h]
0x18004547e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045483  mov     edx, eax; int
0x180045485  lea     rcx, [rsp+760h+var_720]; unsigned int *
0x18004548a  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x18004548f  test    al, al
0x180045491  jz      short loc_1800454E5
0x180045493  mov     ebx, [rsp+760h+var_720]
0x180045497  mov     dword ptr [rsp+760h+ppv], ebx
0x18004549b  lea     r9, aGetHascurrentF_0; "get_HasCurrent failed (%d)"
0x1800454a2  mov     r8d, 3A3h
0x1800454a8  lea     rdx, aMergesdbpgetst_1; "MergeSdbpGetStoreAppInstallDirectory"
0x1800454af  mov     ecx, 1
0x1800454b4  call    AslLogCallPrintf
0x1800454b9  nop
0x1800454ba  lea     rcx, [rbp+660h+var_6E0]
0x1800454be  call    ?InternalRelease@?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(void)
0x1800454c3  nop
0x1800454c4  mov     rcx, [rsp+760h+var_710]
0x1800454c9  test    rcx, rcx
0x1800454cc  jz      short loc_1800454E0
0x1800454ce  mov     [rsp+760h+var_710], rdi
0x1800454d3  mov     rax, [rcx]
0x1800454d6  mov     rax, [rax+10h]
0x1800454da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800454df  nop
0x1800454e0  jmp     loc_180045287
0x1800454e5  mov     edx, edi
0x1800454e7  mov     r13, rdi
0x1800454ea  mov     [rbp+660h+var_670], di
0x1800454ee  lea     r14, aMergesdbpgetst_1; "MergeSdbpGetStoreAppInstallDirectory"
0x1800454f5  mov     esi, 1
0x1800454fa  cmp     [rsp+760h+var_708], dil
0x1800454ff  jz      loc_180045B98
0x180045505  mov     [rsp+760h+var_718], rdi
0x18004550a  mov     rcx, [rbp+660h+var_6E0]
0x18004550e  mov     rax, [rcx]
0x180045511  lea     rdx, [rsp+760h+var_718]
0x180045516  mov     rax, [rax+30h]
0x18004551a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004551f  mov     edx, eax; int
0x180045521  lea     rcx, [rsp+760h+var_720]; unsigned int *
0x180045526  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x18004552b  test    al, al
0x18004552d  jnz     loc_18004674B
0x180045533  cmp     [rsp+760h+var_718], rdi
0x180045538  jz      loc_1800466D7
0x18004553e  mov     [rbp+660h+var_6D0], dil
0x180045542  lea     rax, [rbp+660h+var_6D0]
0x180045546  mov     [rsp+760h+ppv], rax
0x18004554b  lea     rdx, [rsp+760h+var_718]
0x180045550  lea     rcx, [rbp+660h+var_690]
0x180045554  call    ?IsPackageRegistered@@YAJAEBV?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@23@PEAXPEBGAEA_N@Z; IsPackageRegistered(Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager> const &,Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &,void *,ushort const *,bool &)
0x180045559  mov     edx, eax; int
0x18004555b  lea     rcx, [rsp+760h+var_720]; unsigned int *
0x180045560  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x180045565  test    al, al
0x180045567  jnz     loc_180046670
0x18004556d  cmp     [rbp+660h+var_6D0], dil
0x180045571  jnz     short loc_1800455AC
0x180045573  lea     r9, aPackageIsInsta; "Package is installed but not registered"...
0x18004557a  mov     r8d, 3C5h
0x180045580  mov     rdx, r14
0x180045583  xor     ecx, ecx
0x180045585  call    AslLogCallPrintf
0x18004558a  nop
0x18004558b  mov     rcx, [rsp+760h+var_718]
0x180045590  test    rcx, rcx
0x180045593  jz      short loc_1800455A7
0x180045595  mov     [rsp+760h+var_718], rdi
0x18004559a  mov     rax, [rcx]
0x18004559d  mov     rax, [rax+10h]
0x1800455a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800455a6  nop
0x1800455a7  jmp     loc_180045B79
0x1800455ac  mov     [rbp+660h+var_6C0], rdi
0x1800455b0  mov     rdi, [rsp+760h+var_718]
0x1800455b5  mov     rax, [rdi]
0x1800455b8  mov     rbx, [rax+38h]
0x1800455bc  lea     rcx, [rbp+660h+var_6C0]
0x1800455c0  call    ?InternalRelease@?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(void)
0x1800455c5  lea     rdx, [rbp+660h+var_6C0]
0x1800455c9  mov     rcx, rdi
0x1800455cc  mov     rax, rbx
0x1800455cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800455d4  mov     edx, eax; int
0x1800455d6  lea     rcx, [rsp+760h+var_720]; unsigned int *
0x1800455db  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x1800455e0  xor     edi, edi
0x1800455e2  test    al, al
0x1800455e4  jnz     loc_1800465FF
0x1800455ea  mov     [rbp+660h+var_6B8], rdi
0x1800455ee  mov     rbx, [rbp+660h+var_6C0]
0x1800455f2  mov     rax, [rbx]
0x1800455f5  mov     rdi, [rax]
0x1800455f8  lea     rcx, [rbp+660h+var_6B8]
0x1800455fc  call    ?InternalRelease@?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(void)
0x180045601  lea     r8, [rbp+660h+var_6B8]
0x180045605  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
  ... truncated ...
```
