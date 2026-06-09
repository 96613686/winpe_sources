# RemoveSandboxPackages(void)

- ea: `0x180005844`
- end: `0x180006787`
- name: `?RemoveSandboxPackages@@YAJXZ`
- size: `3907`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006790`

## callees

- `0x180001510`
- `0x180002b0c`
- `0x18000551c`
- `0x180005844`
- `0x1800068d4`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000587f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005930`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000587f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005930`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005b1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005c92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005d9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005e96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005f92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000608e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000618a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006271`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006353`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006435`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800064fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800065aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005b1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005c92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005d9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005e96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005f92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000608e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000618a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006271`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006353`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006435`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800064fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800065aa`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180005895`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180005895`

## string_xrefs

- `0x1800058a8`: `onecore\base\gendrv\silos\clem\cleanup\dll\cmcleanup.cpp`
- `0x180005962`: `onecore\base\gendrv\silos\clem\cleanup\dll\cmcleanup.cpp`
- `0x1800059d2`: `onecore\base\gendrv\silos\clem\cleanup\dll\cmcleanup.cpp`
- `0x180005a60`: `onecore\base\gendrv\silos\clem\cleanup\dll\cmcleanup.cpp`
- `0x180005d36`: `onecore\base\gendrv\silos\clem\cleanup\dll\cmcleanup.cpp`
- `0x180005e32`: `onecore\base\gendrv\silos\clem\cleanup\dll\cmcleanup.cpp`
- `0x180005f2e`: `onecore\base\gendrv\silos\clem\cleanup\dll\cmcleanup.cpp`
- `0x18000602a`: `onecore\base\gendrv\silos\clem\cleanup\dll\cmcleanup.cpp`
- `0x180006126`: `onecore\base\gendrv\silos\clem\cleanup\dll\cmcleanup.cpp`
- `0x180006227`: `onecore\base\gendrv\silos\clem\cleanup\dll\cmcleanup.cpp`
- `0x180006309`: `onecore\base\gendrv\silos\clem\cleanup\dll\cmcleanup.cpp`
- `0x1800063eb`: `onecore\base\gendrv\silos\clem\cleanup\dll\cmcleanup.cpp`
- `0x1800064cd`: `onecore\base\gendrv\silos\clem\cleanup\dll\cmcleanup.cpp`
- `0x180006595`: `onecore\base\gendrv\silos\clem\cleanup\dll\cmcleanup.cpp`
- `0x180006642`: `onecore\base\gendrv\silos\clem\cleanup\dll\cmcleanup.cpp`
- `0x1800066e2`: `onecore\base\gendrv\silos\clem\cleanup\dll\cmcleanup.cpp`

## pseudocode

```c
__int64 RemoveSandboxPackages(void)
{
  HRESULT v0; // eax
  int v1; // edx
  unsigned int v2; // r8d
  int v3; // eax
  unsigned int v4; // r8d
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  _QWORD *v8; // rbx
  __int64 (__fastcall **v9)(_QWORD *, GUID *, _QWORD *); // rdi
  unsigned __int64 v10; // rdx
  HRESULT v11; // eax
  int v12; // edx
  unsigned int v13; // r8d
  int v14; // eax
  __int64 v15; // rcx
  _QWORD *v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  _QWORD *v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  _QWORD *v24; // rcx
  int v25; // eax
  int v26; // eax
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, HSTRING *); // rbx
  int v29; // eax
  int v30; // eax
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r8
  int v34; // eax
  int v35; // eax
  int v36; // eax
  int v37; // eax
  int v38; // eax
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  _QWORD *v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  _QWORD *v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rcx
  _QWORD *v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // rcx
  __int64 v66; // rcx
  __int64 v67; // rcx
  __int64 v68; // rcx
  __int64 v69; // rcx
  _QWORD *v70; // rcx
  __int64 v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 v74; // rcx
  __int64 v75; // rcx
  __int64 v76; // rcx
  __int64 v77; // rcx
  _QWORD *v78; // rcx
  __int64 v79; // rcx
  __int64 v80; // rcx
  __int64 v81; // rcx
  __int64 v82; // rcx
  __int64 v83; // rcx
  __int64 v84; // rcx
  __int64 v85; // rcx
  _QWORD *v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // rcx
  __int64 v89; // rcx
  __int64 v90; // rcx
  __int64 v91; // rcx
  __int64 v92; // rcx
  _QWORD *v93; // rcx
  __int64 v94; // rcx
  __int64 v95; // rcx
  __int64 v96; // rcx
  __int64 v97; // rcx
  __int64 v98; // rcx
  __int64 v99; // rcx
  _QWORD *v100; // rcx
  __int64 v101; // rcx
  __int64 v102; // rcx
  __int64 v103; // rcx
  __int64 v104; // rcx
  __int64 v105; // rcx
  __int64 v106; // rcx
  _QWORD *v107; // rcx
  __int64 v108; // rcx
  __int64 v109; // rcx
  __int64 v110; // rcx
  __int64 v111; // rcx
  __int64 v112; // rcx
  _QWORD *v113; // rcx
  __int64 v114; // rcx
  __int64 v115; // rcx
  __int64 v116; // rcx
  __int64 v117; // rcx
  _QWORD *v118; // rcx
  __int64 v119; // rcx
  __int64 v120; // rcx
  __int64 v121; // rcx
  __int64 v122; // rcx
  _QWORD *v123; // rcx
  __int64 v124; // rcx
  __int64 v125; // rcx
  __int64 v126; // rcx
  _QWORD *v127; // rcx
  int v128; // [rsp+20h] [rbp-69h]
  char v129[8]; // [rsp+30h] [rbp-59h] BYREF
  _QWORD *v130; // [rsp+38h] [rbp-51h] BYREF
  __int64 v131; // [rsp+40h] [rbp-49h] BYREF
  __int64 v132; // [rsp+48h] [rbp-41h] BYREF
  __int64 v133; // [rsp+50h] [rbp-39h] BYREF
  __int64 v134; // [rsp+58h] [rbp-31h] BYREF
  HSTRING v135; // [rsp+60h] [rbp-29h] BYREF
  char v136[8]; // [rsp+68h] [rbp-21h] BYREF
  __int64 v137; // [rsp+70h] [rbp-19h] BYREF
  __int64 v138; // [rsp+78h] [rbp-11h] BYREF
  __int64 v139; // [rsp+80h] [rbp-9h] BYREF
  char *v140; // [rsp+88h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp+7h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v130 = 0;
  string = 0;
  v0 = WindowsCreateStringReference(L"Windows.Management.Deployment.PackageManager", 0x2Cu, &hstringHeader, &string);
  if ( v0 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v0, v1, v2);
    __debugbreak();
  }
  v3 = RoActivateInstance(string, &v130);
  v5 = v3;
  if ( v3 >= 0 )
  {
    v132 = 0;
    v8 = v130;
    v9 = (__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD *))*v130;
    string = 0;
    v10 = -1;
    do
      ++v10;
    while ( aMicrosoftwindo[v10] );
    if ( v10 > 0xFFFFFFFF )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v10, v4);
      __debugbreak();
    }
    if ( (int)v10 + 1 < (unsigned int)v10 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v10, v4);
      __debugbreak();
    }
    v11 = WindowsCreateStringReference(L"MicrosoftWindows.WindowsSandbox_cw5n1h2txyewy", v10, &hstringHeader, &string);
    if ( v11 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
      JUMPOUT(0x180006786LL);
    }
    v14 = v9[19](v8, (GUID *)string, &v132);
    v5 = v14;
    if ( v14 >= 0 )
    {
      v131 = 0;
      v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v132 + 48LL))(v132, &v131);
      v5 = v17;
      if ( v17 >= 0 )
      {
        v129[0] = 0;
        v21 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v131 + 56LL))(v131, v129);
        v5 = v21;
        if ( v21 >= 0 )
        {
          while ( 1 )
          {
            if ( !v129[0] )
            {
              v44 = v131;
              if ( v131 )
              {
                v131 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
              }
              v45 = v132;
              if ( v132 )
              {
                v132 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
              }
              v46 = v130;
              if ( v130 )
              {
                v130 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
              }
              return 0;
            }
            v133 = 0;
            v25 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v131 + 48LL))(v131, &v133);
            v5 = v25;
            if ( v25 < 0 )
              break;
            v134 = 0;
            v26 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v133 + 48LL))(v133, &v134);
            v5 = v26;
            if ( v26 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x60,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\cleanup\\dll\\cmcleanup.cpp",
                (const char *)(unsigned int)v26,
                v128);
              v119 = v134;
              if ( v134 )
              {
                v134 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v119 + 16LL))(v119);
              }
              v120 = v133;
              if ( v133 )
              {
                v133 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v120 + 16LL))(v120);
              }
              v121 = v131;
              if ( v131 )
              {
                v131 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v121 + 16LL))(v121);
              }
              v122 = v132;
              if ( v132 )
              {
                v132 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
              }
              v123 = v130;
              if ( v130 )
              {
                v130 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v123 + 16LL))(v123);
              }
              return v5;
            }
            v135 = 0;
            v27 = v134;
            v28 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v134 + 96LL);
            WindowsDeleteString(0);
            v135 = 0;
            v29 = v28(v27, &v135);
            v5 = v29;
            if ( v29 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x63,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\cleanup\\dll\\cmcleanup.cpp",
                (const char *)(unsigned int)v29,
                v128);
              WindowsDeleteString(v135);
              v135 = 0;
              v114 = v134;
              if ( v134 )
              {
                v134 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v114 + 16LL))(v114);
              }
              v115 = v133;
              if ( v133 )
              {
                v133 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v115 + 16LL))(v115);
              }
              v116 = v131;
              if ( v131 )
              {
                v131 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v116 + 16LL))(v116);
              }
              v117 = v132;
              if ( v132 )
              {
                v132 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v117 + 16LL))(v117);
              }
              v118 = v130;
              if ( v130 )
              {
                v130 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v118 + 16LL))(v118);
              }
              return v5;
            }
            v137 = 0;
            v30 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*v130)(
                    v130,
                    &GUID_f7aad08d_0840_46f2_b5d8_cad47693a095,
                    &v137);
            v5 = v30;
            if ( v30 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x66,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\cleanup\\dll\\cmcleanup.cpp",
                (const char *)(unsigned int)v30,
                v128);
              v108 = v137;
              if ( v137 )
              {
                v137 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v108 + 16LL))(v108);
              }
              WindowsDeleteString(v135);
              v135 = 0;
              v109 = v134;
              if ( v134 )
              {
                v134 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
              }
              v110 = v133;
              if ( v133 )
              {
                v133 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
              }
              v111 = v131;
              if ( v131 )
              {
                v131 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
              }
              v112 = v132;
              if ( v132 )
              {
                v132 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 16LL))(v112);
              }
              v113 = v130;
              if ( v130 )
              {
                v130 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v113 + 16LL))(v113);
              }
              return v5;
            }
            v138 = 0;
            v31 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64, __int64 *))(*(_QWORD *)v137 + 48LL))(
                    v137,
                    v135,
                    0x80000,
                    &v138);
            v5 = v31;
            if ( v31 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x6D,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\cleanup\\dll\\cmcleanup.cpp",
                (const char *)(unsigned int)v31,
                v128);
              v101 = v138;
              if ( v138 )
              {
                v138 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
              }
              v102 = v137;
              if ( v137 )
              {
                v137 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v102 + 16LL))(v102);
              }
              WindowsDeleteString(v135);
              v135 = 0;
              v103 = v134;
              if ( v134 )
              {
                v134 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v103 + 16LL))(v103);
              }
              v104 = v133;
              if ( v133 )
              {
                v133 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
              }
              v105 = v131;
              if ( v131 )
              {
                v131 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
              }
              v106 = v132;
              if ( v132 )
              {
                v132 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
              }
              v107 = v130;
              if ( v130 )
              {
                v130 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v107 + 16LL))(v107);
              }
              return v5;
            }
            v136[0] = 0;
            v34 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *>(
                    v138,
                    v32,
                    v33,
                    v136);
            v5 = v34;
            if ( v34 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x73,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\cleanup\\dll\\cmcleanup.cpp",
                (const char *)(unsigned int)v34,
                v128);
              v94 = v138;
              if ( v138 )
              {
                v138 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
              }
              v95 = v137;
              if ( v137 )
              {
                v137 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
              }
              WindowsDeleteString(v135);
              v135 = 0;
              v96 = v134;
              if ( v134 )
              {
                v134 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
              }
              v97 = v133;
              if ( v133 )
              {
                v133 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
              }
              v98 = v131;
              if ( v131 )
              {
                v131 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
              }
              v99 = v132;
              if ( v132 )
              {
                v132 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
              }
              v100 = v130;
              if ( v130 )
              {
                v130 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v100 + 16LL))(v100);
              }
              return v5;
            }
            if ( v136[0] )
            {
              v5 = -2147023436;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x75,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\cleanup\\dll\\cmcleanup.cpp",
                (const char *)0x800705B4LL,
                v128);
              v87 = v138;
              if ( v138 )
              {
                v138 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
              }
              v88 = v137;
              if ( v137 )
              {
                v137 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
              }
              WindowsDeleteString(v135);
              v135 = 0;
              v89 = v134;
              if ( v134 )
              {
                v134 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
              }
              v90 = v133;
              if ( v133 )
              {
                v133 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
              }
              v91 = v131;
              if ( v131 )
              {
                v131 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
              }
              v92 = v132;
              if ( v132 )
              {
                v132 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
              }
              v93 = v130;
              if ( v130 )
              {
                v130 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v93 + 16LL))(v93);
              }
              return v5;
            }
            v139 = 0;
            v35 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v138 + 80LL))(v138, &v139);
            v5 = v35;
            if ( v35 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x78,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\cleanup\\dll\\cmcleanup.cpp",
                (const char *)(unsigned int)v35,
                v128);
              v79 = v139;
              if ( v139 )
              {
                v139 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
              }
              v80 = v138;
              if ( v138 )
              {
                v138 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
              }
              v81 = v137;
              if ( v137 )
              {
                v137 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
              }
              WindowsDeleteString(v135);
              v135 = 0;
              v82 = v134;
              if ( v134 )
              {
                v134 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
              }
              v83 = v133;
              if ( v133 )
              {
                v133 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
              }
              v84 = v131;
              if ( v131 )
              {
                v131 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
              }
              v85 = v132;
              if ( v132 )
              {
                v132 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
              }
              v86 = v130;
              if ( v130 )
              {
                v130 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v86 + 16LL))(v86);
              }
              return v5;
            }
            LODWORD(v140) = 0;
            v36 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v139 + 64LL))(v139, &v140);
            v5 = v36;
            if ( v36 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x7B,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\cleanup\\dll\\cmcleanup.cpp",
                (const char *)(unsigned int)v36,
                v128);
              v71 = v139;
              if ( v139 )
              {
                v139 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
              }
              v72 = v138;
              if ( v138 )
              {
                v138 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
              }
              v73 = v137;
              if ( v137 )
              {
                v137 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
              }
              WindowsDeleteString(v135);
              v135 = 0;
              v74 = v134;
              if ( v134 )
              {
                v134 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
              }
              v75 = v133;
              if ( v133 )
              {
                v133 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
              }
              v76 = v131;
              if ( v131 )
              {
                v131 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
              }
              v77 = v132;
              if ( v132 )
              {
                v132 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
              }
              v78 = v130;
              if ( v130 )
              {
                v130 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v78 + 16LL))(v78);
              }
              return v5;
            }
            v5 = (unsigned int)v140;
            if ( (int)v140 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x7C,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\cleanup\\dll\\cmcleanup.cpp",
                (const char *)(unsigned int)v140,
                v128);
              v63 = v139;
              if ( v139 )
              {
                v139 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
              }
              v64 = v138;
              if ( v138 )
              {
                v138 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
              }
              v65 = v137;
              if ( v137 )
              {
                v137 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
              }
              WindowsDeleteString(v135);
              v135 = 0;
              v66 = v134;
              if ( v134 )
              {
                v134 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
              }
              v67 = v133;
              if ( v133 )
              {
                v133 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
              }
              v68 = v131;
              if ( v131 )
              {
                v131 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
              }
              v69 = v132;
              if ( v132 )
              {
                v132 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
              }
              v70 = v130;
              if ( v130 )
              {
                v130 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v70 + 16LL))(v70);
              }
              return v5;
            }
            v37 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v131 + 64LL))(v131, v129);
            v5 = v37;
            if ( v37 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x7E,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\cleanup\\dll\\cmcleanup.cpp",
                (const char *)(unsigned int)v37,
                v128);
              v55 = v139;
              if ( v139 )
              {
                v139 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
              }
              v56 = v138;
              if ( v138 )
              {
                v138 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
              }
              v57 = v137;
              if ( v137 )
              {
                v137 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
              }
              WindowsDeleteString(v135);
              v135 = 0;
              v58 = v134;
              if ( v134 )
              {
                v134 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
              }
              v59 = v133;
              if ( v133 )
              {
                v133 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
              }
              v60 = v131;
              if ( v131 )
              {
                v131 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
              }
              v61 = v132;
              if ( v132 )
              {
                v132 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
              }
              v62 = v130;
              if ( v130 )
              {
                v130 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v62 + 16LL))(v62);
              }
              return v5;
            }
            v38 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v131 + 56LL))(v131, v129);
            v5 = v38;
            if ( v38 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x7F,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\cleanup\\dll\\cmcleanup.cpp",
                (const char *)(unsigned int)v38,
                v128);
              v47 = v139;
              if ( v139 )
              {
                v139 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
              }
              v48 = v138;
              if ( v138 )
              {
                v138 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
              }
              v49 = v137;
              if ( v137 )
              {
                v137 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
              }
              WindowsDeleteString(v135);
              v135 = 0;
              v50 = v134;
              if ( v134 )
              {
                v134 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
              }
              v51 = v133;
              if ( v133 )
              {
                v133 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
              }
              v52 = v131;
              if ( v131 )
              {
                v131 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
              }
              v53 = v132;
              if ( v132 )
              {
                v132 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
              }
              v54 = v130;
              if ( v130 )
              {
                v130 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v54 + 16LL))(v54);
              }
              return v5;
            }
            v39 = v139;
            if ( v139 )
            {
              v139 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
            }
            v40 = v138;
            if ( v138 )
            {
              v138 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
            }
            v41 = v137;
            if ( v137 )
            {
              v137 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
            }
            WindowsDeleteString(v135);
            v135 = 0;
            v42 = v134;
            if ( v134 )
            {
              v134 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
            }
            v43 = v133;
            if ( v133 )
            {
              v133 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
            }
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5C,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\cleanup\\dll\\cmcleanup.cpp",
            (const char *)(unsigned int)v25,
            v128);
          v124 = v133;
          if ( v133 )
          {
            v133 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v124 + 16LL))(v124);
          }
          v125 = v131;
          if ( v131 )
          {
            v131 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v125 + 16LL))(v125);
          }
          v126 = v132;
          if ( v132 )
          {
            v132 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v126 + 16LL))(v126);
          }
          v127 = v130;
          if ( v130 )
          {
            v130 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v127 + 16LL))(v127);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x56,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\cleanup\\dll\\cmcleanup.cpp",
            (const char *)(unsigned int)v21,
            v128);
          v22 = v131;
          if ( v131 )
          {
            v131 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          }
          v23 = v132;
          if ( v132 )
          {
            v132 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          }
          v24 = v130;
          if ( v130 )
          {
            v130 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v24 + 16LL))(v24);
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x53,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\cleanup\\dll\\cmcleanup.cpp",
          (const char *)(unsigned int)v17,
          v128);
        v18 = v131;
        if ( v131 )
        {
          v131 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
        v19 = v132;
        if ( v132 )
        {
          v132 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        }
        v20 = v130;
        if ( v130 )
        {
          v130 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v20 + 16LL))(v20);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x50,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\cleanup\\dll\\cmcleanup.cpp",
        (const char *)(unsigned int)v14,
        v128);
      v15 = v132;
      if ( v132 )
      {
        v132 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      v16 = v130;
      if ( v130 )
      {
        v130 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\cleanup\\dll\\cmcleanup.cpp",
      (const char *)(unsigned int)v3,
      v128);
    v6 = v130;
    if ( v130 )
    {
      v130 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180005844  push    rbp
0x180005846  push    rbx
0x180005847  push    rsi
0x180005848  push    rdi
0x180005849  lea     rbp, [rsp-3Fh]
0x18000584e  sub     rsp, 0C8h
0x180005855  mov     rax, cs:__security_cookie
0x18000585c  xor     rax, rsp
0x18000585f  mov     [rbp+57h+var_30], rax
0x180005863  xor     esi, esi
0x180005865  mov     [rbp+57h+var_A8], rsi
0x180005869  mov     [rbp+57h+string], rsi
0x18000586d  lea     r9, [rbp+57h+string]; string
0x180005871  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180005875  lea     edx, [rsi+2Ch]; length
0x180005878  lea     rcx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x18000587f  call    cs:__imp_WindowsCreateStringReference
0x180005885  test    eax, eax
0x180005887  js      loc_180006777
0x18000588d  lea     rdx, [rbp+57h+var_A8]
0x180005891  mov     rcx, [rbp+57h+string]
0x180005895  call    cs:__imp_RoActivateInstance
0x18000589b  mov     ebx, eax
0x18000589d  test    eax, eax
0x18000589f  jns     short loc_1800058EC
0x1800058a1  mov     rcx, [rbp+5Fh]; this
0x1800058a5  mov     r9d, eax; char *
0x1800058a8  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\cle"...
0x1800058af  lea     edx, [rsi+49h]; void *
0x1800058b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800058b7  nop
0x1800058b8  mov     rcx, [rbp+57h+var_A8]
0x1800058bc  test    rcx, rcx
0x1800058bf  jz      short loc_1800058D2
0x1800058c1  mov     [rbp+57h+var_A8], rsi
0x1800058c5  mov     rax, [rcx]
0x1800058c8  mov     rax, [rax+10h]
0x1800058cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058d1  nop
0x1800058d2  mov     eax, ebx
0x1800058d4  mov     rcx, [rbp+57h+var_30]
0x1800058d8  xor     rcx, rsp; StackCookie
0x1800058db  call    __security_check_cookie
0x1800058e0  add     rsp, 0C8h
0x1800058e7  pop     rdi
0x1800058e8  pop     rsi
0x1800058e9  pop     rbx
0x1800058ea  pop     rbp
0x1800058eb  retn
0x1800058ec  mov     [rbp+57h+var_98], rsi
0x1800058f0  mov     rbx, [rbp+57h+var_A8]
0x1800058f4  mov     rdi, [rbx]
0x1800058f7  mov     [rbp+57h+string], rsi
0x1800058fb  mov     rcx, cs:sourceString; sourceString
0x180005902  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180005906  inc     rdx; int
0x180005909  cmp     [rcx+rdx*2], si
0x18000590d  jnz     short loc_180005906
0x18000590f  mov     eax, 0FFFFFFFFh
0x180005914  cmp     rdx, rax
0x180005917  ja      loc_18000676C
0x18000591d  lea     eax, [rdx+1]
0x180005920  cmp     eax, edx
0x180005922  jb      loc_180006761
0x180005928  lea     r9, [rbp+57h+string]; string
0x18000592c  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180005930  call    cs:__imp_WindowsCreateStringReference
0x180005936  test    eax, eax
0x180005938  js      loc_18000677F
0x18000593e  lea     r8, [rbp+57h+var_98]
0x180005942  mov     rdx, [rbp+57h+string]
0x180005946  mov     rcx, rbx
0x180005949  mov     rax, [rdi+98h]
0x180005950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005955  mov     ebx, eax
0x180005957  test    eax, eax
0x180005959  jns     short loc_1800059AD
0x18000595b  mov     rcx, [rbp+5Fh]; this
0x18000595f  mov     r9d, eax; char *
0x180005962  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\cle"...
0x180005969  mov     edx, 50h ; 'P'; void *
0x18000596e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005973  nop
0x180005974  mov     rcx, [rbp+57h+var_98]
0x180005978  test    rcx, rcx
0x18000597b  jz      short loc_18000598E
0x18000597d  mov     [rbp+57h+var_98], rsi
0x180005981  mov     rax, [rcx]
0x180005984  mov     rax, [rax+10h]
0x180005988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000598d  nop
0x18000598e  mov     rcx, [rbp+57h+var_A8]
0x180005992  test    rcx, rcx
0x180005995  jz      short loc_1800059A8
0x180005997  mov     [rbp+57h+var_A8], rsi
0x18000599b  mov     rax, [rcx]
0x18000599e  mov     rax, [rax+10h]
0x1800059a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059a7  nop
0x1800059a8  jmp     loc_1800058D2
0x1800059ad  mov     [rbp+57h+var_A0], rsi
0x1800059b1  mov     rcx, [rbp+57h+var_98]
0x1800059b5  mov     rax, [rcx]
0x1800059b8  lea     rdx, [rbp+57h+var_A0]
0x1800059bc  mov     rax, [rax+30h]
0x1800059c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059c5  mov     ebx, eax
0x1800059c7  test    eax, eax
0x1800059c9  jns     short loc_180005A37
0x1800059cb  mov     rcx, [rbp+5Fh]; this
0x1800059cf  mov     r9d, eax; char *
0x1800059d2  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\cle"...
0x1800059d9  mov     edx, 53h ; 'S'; void *
0x1800059de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800059e3  nop
0x1800059e4  mov     rcx, [rbp+57h+var_A0]
0x1800059e8  test    rcx, rcx
0x1800059eb  jz      short loc_1800059FE
0x1800059ed  mov     [rbp+57h+var_A0], rsi
0x1800059f1  mov     rax, [rcx]
0x1800059f4  mov     rax, [rax+10h]
0x1800059f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059fd  nop
0x1800059fe  mov     rcx, [rbp+57h+var_98]
0x180005a02  test    rcx, rcx
0x180005a05  jz      short loc_180005A18
0x180005a07  mov     [rbp+57h+var_98], rsi
0x180005a0b  mov     rax, [rcx]
0x180005a0e  mov     rax, [rax+10h]
0x180005a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a17  nop
0x180005a18  mov     rcx, [rbp+57h+var_A8]
0x180005a1c  test    rcx, rcx
0x180005a1f  jz      short loc_180005A32
0x180005a21  mov     [rbp+57h+var_A8], rsi
0x180005a25  mov     rax, [rcx]
0x180005a28  mov     rax, [rax+10h]
0x180005a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a31  nop
0x180005a32  jmp     loc_1800058D2
0x180005a37  mov     [rbp+57h+var_B0], sil
0x180005a3b  mov     rcx, [rbp+57h+var_A0]
0x180005a3f  mov     rax, [rcx]
0x180005a42  lea     rdx, [rbp+57h+var_B0]
0x180005a46  mov     rax, [rax+38h]
0x180005a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a4f  mov     ebx, eax
0x180005a51  test    eax, eax
0x180005a53  jns     loc_180005CD0
0x180005a59  mov     rcx, [rbp+5Fh]; this
0x180005a5d  mov     r9d, eax; char *
0x180005a60  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\cle"...
0x180005a67  mov     edx, 56h ; 'V'; void *
0x180005a6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005a71  nop
0x180005a72  mov     rcx, [rbp+57h+var_A0]
0x180005a76  test    rcx, rcx
0x180005a79  jz      short loc_180005A8C
0x180005a7b  mov     [rbp+57h+var_A0], rsi
0x180005a7f  mov     rax, [rcx]
0x180005a82  mov     rax, [rax+10h]
0x180005a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a8b  nop
0x180005a8c  mov     rcx, [rbp+57h+var_98]
0x180005a90  test    rcx, rcx
0x180005a93  jz      short loc_180005AA6
0x180005a95  mov     [rbp+57h+var_98], rsi
0x180005a99  mov     rax, [rcx]
0x180005a9c  mov     rax, [rax+10h]
0x180005aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aa5  nop
0x180005aa6  mov     rcx, [rbp+57h+var_A8]
0x180005aaa  test    rcx, rcx
0x180005aad  jz      short loc_180005AC0
0x180005aaf  mov     [rbp+57h+var_A8], rsi
0x180005ab3  mov     rax, [rcx]
0x180005ab6  mov     rax, [rax+10h]
0x180005aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005abf  nop
0x180005ac0  jmp     loc_1800058D2
0x180005ac5  mov     [rbp+57h+var_90], rsi
0x180005ac9  mov     rcx, [rbp+57h+var_A0]
0x180005acd  mov     rax, [rcx]
0x180005ad0  lea     rdx, [rbp+57h+var_90]
0x180005ad4  mov     rax, [rax+30h]
0x180005ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005add  mov     ebx, eax
0x180005adf  test    eax, eax
0x180005ae1  js      loc_1800066DB
0x180005ae7  mov     [rbp+57h+var_88], rsi
0x180005aeb  mov     rcx, [rbp+57h+var_90]
0x180005aef  mov     rax, [rcx]
0x180005af2  lea     rdx, [rbp+57h+var_88]
0x180005af6  mov     rax, [rax+30h]
0x180005afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aff  mov     ebx, eax
0x180005b01  test    eax, eax
0x180005b03  js      loc_18000663B
0x180005b09  mov     [rbp+57h+var_80], rsi
0x180005b0d  mov     rdi, [rbp+57h+var_88]
0x180005b11  mov     rax, [rdi]
0x180005b14  mov     rbx, [rax+60h]
0x180005b18  xor     ecx, ecx; string
0x180005b1a  call    cs:__imp_WindowsDeleteString
0x180005b20  mov     [rbp+57h+var_80], rsi
0x180005b24  lea     rdx, [rbp+57h+var_80]
0x180005b28  mov     rcx, rdi
0x180005b2b  mov     rax, rbx
0x180005b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b33  mov     ebx, eax
0x180005b35  test    eax, eax
0x180005b37  js      loc_18000658E
0x180005b3d  mov     [rbp+57h+var_70], rsi
0x180005b41  mov     rcx, [rbp+57h+var_A8]
0x180005b45  mov     rax, [rcx]
0x180005b48  lea     r8, [rbp+57h+var_70]
0x180005b4c  lea     rdx, _GUID_f7aad08d_0840_46f2_b5d8_cad47693a095
0x180005b53  mov     rax, [rax]
0x180005b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b5b  mov     ebx, eax
0x180005b5d  test    eax, eax
0x180005b5f  js      loc_1800064C6
0x180005b65  mov     [rbp+57h+var_68], rsi
0x180005b69  mov     rcx, [rbp+57h+var_70]
0x180005b6d  mov     rax, [rcx]
0x180005b70  lea     r9, [rbp+57h+var_68]
0x180005b74  mov     r8d, 80000h
0x180005b7a  mov     rdx, [rbp+57h+var_80]
0x180005b7e  mov     rax, [rax+30h]
0x180005b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b87  mov     ebx, eax
0x180005b89  test    eax, eax
0x180005b8b  js      loc_1800063E4
0x180005b91  mov     [rbp+57h+var_78], sil
0x180005b95  lea     r9, [rbp+57h+var_78]
0x180005b99  mov     rcx, [rbp+57h+var_68]
0x180005b9d  call    ??$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180005ba2  mov     ebx, eax
0x180005ba4  test    eax, eax
0x180005ba6  js      loc_180006302
0x180005bac  cmp     [rbp+57h+var_78], sil
0x180005bb0  jnz     loc_18000621B
0x180005bb6  mov     [rbp+57h+var_60], rsi
0x180005bba  mov     rcx, [rbp+57h+var_68]
0x180005bbe  mov     rax, [rcx]
0x180005bc1  lea     rdx, [rbp+57h+var_60]
0x180005bc5  mov     rax, [rax+50h]
0x180005bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bce  mov     ebx, eax
0x180005bd0  test    eax, eax
0x180005bd2  js      loc_18000611F
0x180005bd8  mov     dword ptr [rbp+57h+var_58], esi
0x180005bdb  mov     rcx, [rbp+57h+var_60]
0x180005bdf  mov     rax, [rcx]
0x180005be2  lea     rdx, [rbp+57h+var_58]
0x180005be6  mov     rax, [rax+40h]
0x180005bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bef  mov     ebx, eax
0x180005bf1  test    eax, eax
0x180005bf3  js      loc_180006023
0x180005bf9  mov     ebx, dword ptr [rbp+57h+var_58]
0x180005bfc  test    ebx, ebx
0x180005bfe  js      loc_180005F27
0x180005c04  mov     rcx, [rbp+57h+var_A0]
0x180005c08  mov     rax, [rcx]
0x180005c0b  lea     rdx, [rbp+57h+var_B0]
0x180005c0f  mov     rax, [rax+40h]
0x180005c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c18  mov     ebx, eax
0x180005c1a  test    eax, eax
0x180005c1c  js      loc_180005E2B
0x180005c22  mov     rcx, [rbp+57h+var_A0]
0x180005c26  mov     rax, [rcx]
0x180005c29  lea     rdx, [rbp+57h+var_B0]
0x180005c2d  mov     rax, [rax+38h]
0x180005c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c36  mov     ebx, eax
0x180005c38  test    eax, eax
0x180005c3a  js      loc_180005D2F
0x180005c40  mov     rcx, [rbp+57h+var_60]
0x180005c44  test    rcx, rcx
0x180005c47  jz      short loc_180005C5A
0x180005c49  mov     [rbp+57h+var_60], rsi
0x180005c4d  mov     rax, [rcx]
0x180005c50  mov     rax, [rax+10h]
0x180005c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c59  nop
0x180005c5a  mov     rcx, [rbp+57h+var_68]
0x180005c5e  test    rcx, rcx
0x180005c61  jz      short loc_180005C74
0x180005c63  mov     [rbp+57h+var_68], rsi
0x180005c67  mov     rax, [rcx]
0x180005c6a  mov     rax, [rax+10h]
0x180005c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c73  nop
0x180005c74  mov     rcx, [rbp+57h+var_70]
0x180005c78  test    rcx, rcx
0x180005c7b  jz      short loc_180005C8E
0x180005c7d  mov     [rbp+57h+var_70], rsi
0x180005c81  mov     rax, [rcx]
  ... truncated ...
```
