# InitializeRpcServices(void)

- ea: `0x18004a5cc`
- end: `0x18004ada4`
- name: `?InitializeRpcServices@@YAJXZ`
- size: `2008`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180042f44`

## callees

- `0x180007500`
- `0x18003bc80`
- `0x18004a5cc`
- `0x18004adac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a875`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a8c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a913`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a9b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a875`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a8c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a913`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a9b1`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x18004acd8`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x18004acd8`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18004ac9a`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18004ac9a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004a81c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004a86b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004a8ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004a909`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004a958`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004a9a7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004a81c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004a86b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004a8ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004a909`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004a958`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004a9a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ad31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ad41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ad51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ad61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ad71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ad81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ad31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ad41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ad51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ad61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ad71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ad81`

## string_xrefs

- `0x18004abd0`: `Device Association Framework AEP Store Access RPC Interface`

## pseudocode

```c
__int64 InitializeRpcServices(void)
{
  WCHAR *v0; // rax
  __int64 v1; // r8
  __int64 v2; // rdx
  const wchar_t *v3; // rcx
  __int128 v4; // xmm1
  __int128 v5; // xmm0
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  WCHAR *v12; // rcx
  __int64 v13; // r9
  const wchar_t *v14; // rax
  const wchar_t *v15; // rdx
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  const wchar_t *v24; // rdx
  __int64 v25; // r9
  WCHAR *v26; // rcx
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  WCHAR *v34; // rcx
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  signed int v43; // eax
  int v44; // edx
  int v45; // r8d
  signed int v46; // ebx
  int v47; // r9d
  signed int v48; // eax
  signed int v49; // eax
  signed int v50; // eax
  signed int v51; // eax
  signed int LastError; // eax
  int v53; // eax
  signed int v54; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+48h] [rbp-B8h] BYREF
  PSECURITY_DESCRIPTOR v58; // [rsp+50h] [rbp-B0h] BYREF
  PSECURITY_DESCRIPTOR v59; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL v60; // [rsp+60h] [rbp-A0h] BYREF
  PSECURITY_DESCRIPTOR v61; // [rsp+68h] [rbp-98h] BYREF
  PSECURITY_DESCRIPTOR v62; // [rsp+70h] [rbp-90h] BYREF
  __int128 v63; // [rsp+78h] [rbp-88h] BYREF
  __int128 v64; // [rsp+88h] [rbp-78h] BYREF
  __int128 v65; // [rsp+98h] [rbp-68h] BYREF
  __int128 v66; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v67; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v68; // [rsp+C8h] [rbp-38h] BYREF
  int v69; // [rsp+D8h] [rbp-28h] BYREF
  const unsigned __int16 *v70; // [rsp+E0h] [rbp-20h]
  __int64 v71; // [rsp+E8h] [rbp-18h]
  PSECURITY_DESCRIPTOR v72; // [rsp+F0h] [rbp-10h]
  int v73; // [rsp+F8h] [rbp-8h]
  int v74; // [rsp+100h] [rbp+0h] BYREF
  __int64 *v75; // [rsp+108h] [rbp+8h]
  __int128 v76; // [rsp+110h] [rbp+10h]
  int v77; // [rsp+120h] [rbp+20h]
  __int64 v78; // [rsp+124h] [rbp+24h]
  __int64 v79; // [rsp+130h] [rbp+30h]
  __int128 *v80; // [rsp+138h] [rbp+38h]
  const wchar_t *v81; // [rsp+140h] [rbp+40h]
  PSECURITY_DESCRIPTOR v82; // [rsp+148h] [rbp+48h]
  int v83; // [rsp+150h] [rbp+50h]
  __int64 *v84; // [rsp+158h] [rbp+58h]
  __int128 v85; // [rsp+160h] [rbp+60h]
  int v86; // [rsp+170h] [rbp+70h]
  __int64 v87; // [rsp+174h] [rbp+74h]
  __int64 v88; // [rsp+180h] [rbp+80h]
  __int128 *v89; // [rsp+188h] [rbp+88h]
  const wchar_t *v90; // [rsp+190h] [rbp+90h]
  PSECURITY_DESCRIPTOR v91; // [rsp+198h] [rbp+98h]
  int v92; // [rsp+1A0h] [rbp+A0h]
  __int64 *v93; // [rsp+1A8h] [rbp+A8h]
  __int128 v94; // [rsp+1B0h] [rbp+B0h]
  int v95; // [rsp+1C0h] [rbp+C0h]
  __int64 v96; // [rsp+1C4h] [rbp+C4h]
  __int64 v97; // [rsp+1D0h] [rbp+D0h]
  __int128 *v98; // [rsp+1D8h] [rbp+D8h]
  const wchar_t *v99; // [rsp+1E0h] [rbp+E0h]
  PSECURITY_DESCRIPTOR v100; // [rsp+1E8h] [rbp+E8h]
  int v101; // [rsp+1F0h] [rbp+F0h]
  __int64 *v102; // [rsp+1F8h] [rbp+F8h]
  __int128 v103; // [rsp+200h] [rbp+100h]
  int v104; // [rsp+210h] [rbp+110h]
  __int64 v105; // [rsp+214h] [rbp+114h]
  __int64 v106; // [rsp+220h] [rbp+120h]
  __int128 *v107; // [rsp+228h] [rbp+128h]
  const wchar_t *v108; // [rsp+230h] [rbp+130h]
  PSECURITY_DESCRIPTOR v109; // [rsp+238h] [rbp+138h]
  int v110; // [rsp+240h] [rbp+140h]
  __int64 *v111; // [rsp+248h] [rbp+148h]
  __int128 v112; // [rsp+250h] [rbp+150h]
  int v113; // [rsp+260h] [rbp+160h]
  __int64 v114; // [rsp+264h] [rbp+164h]
  __int64 v115; // [rsp+270h] [rbp+170h]
  __int128 *v116; // [rsp+278h] [rbp+178h]
  const wchar_t *v117; // [rsp+280h] [rbp+180h]
  HLOCAL v118; // [rsp+288h] [rbp+188h]
  int v119; // [rsp+290h] [rbp+190h]
  __int64 *v120; // [rsp+298h] [rbp+198h]
  __int128 v121; // [rsp+2A0h] [rbp+1A0h]
  int v122; // [rsp+2B0h] [rbp+1B0h]
  __int64 v123; // [rsp+2B4h] [rbp+1B4h]
  __int64 v124; // [rsp+2C0h] [rbp+1C0h]
  __int128 *v125; // [rsp+2C8h] [rbp+1C8h]
  const wchar_t *v126; // [rsp+2D0h] [rbp+1D0h]
  PSECURITY_DESCRIPTOR v127; // [rsp+2D8h] [rbp+1D8h]
  wchar_t v128[16]; // [rsp+2E0h] [rbp+1E0h] BYREF
  wchar_t v129[16]; // [rsp+300h] [rbp+200h] BYREF
  WCHAR StringSecurityDescriptor[136]; // [rsp+320h] [rbp+220h] BYREF
  WCHAR v131[136]; // [rsp+430h] [rbp+330h] BYREF
  WCHAR v132[136]; // [rsp+540h] [rbp+440h] BYREF
  WCHAR v133[136]; // [rsp+650h] [rbp+550h] BYREF

  v0 = StringSecurityDescriptor;
  SecurityDescriptor = 0;
  hMem = 0;
  v63 = 0;
  v1 = 2;
  v62 = 0;
  v2 = 2;
  v58 = 0;
  v59 = 0;
  v64 = 0;
  v60 = 0;
  v3 = L"D:(A;;GR;;;WD)(A;;GR;;;AC)(A;;GR;;;S-1-15-3-1024-1692970155-4054893335-185714091-3362601943-3526593181-1159816984"
        "-2199008581-497492991)";
  v65 = 0;
  v61 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  do
  {
    v4 = *((_OWORD *)v3 + 1);
    *(_OWORD *)v0 = *(_OWORD *)v3;
    v5 = *((_OWORD *)v3 + 2);
    *((_OWORD *)v0 + 1) = v4;
    v6 = *((_OWORD *)v3 + 3);
    *((_OWORD *)v0 + 2) = v5;
    v7 = *((_OWORD *)v3 + 4);
    *((_OWORD *)v0 + 3) = v6;
    v8 = *((_OWORD *)v3 + 5);
    *((_OWORD *)v0 + 4) = v7;
    v9 = *((_OWORD *)v3 + 6);
    *((_OWORD *)v0 + 5) = v8;
    v10 = *((_OWORD *)v3 + 7);
    v3 += 64;
    *((_OWORD *)v0 + 6) = v9;
    *((_OWORD *)v0 + 7) = v10;
    v0 += 64;
    --v2;
  }
  while ( v2 );
  v11 = *(_OWORD *)v3;
  v12 = v131;
  v13 = 2;
  *(_OWORD *)v0 = v11;
  v14 = L"D:(A;;GR;;;AU)(A;;GR;;;AC)(A;;GR;;;S-1-15-3-1024-1692970155-4054893335-185714091-3362601943-3526593181-115981698"
         "4-2199008581-497492991)";
  v15 = L"D:(A;;GR;;;AU)(A;;GR;;;AC)(A;;GR;;;S-1-15-3-1024-1692970155-4054893335-185714091-3362601943-3526593181-115981698"
         "4-2199008581-497492991)";
  wcscpy(v128, L"D:(A;;R;;;AU)");
  do
  {
    v16 = *((_OWORD *)v15 + 1);
    *(_OWORD *)v12 = *(_OWORD *)v15;
    v17 = *((_OWORD *)v15 + 2);
    *((_OWORD *)v12 + 1) = v16;
    v18 = *((_OWORD *)v15 + 3);
    *((_OWORD *)v12 + 2) = v17;
    v19 = *((_OWORD *)v15 + 4);
    *((_OWORD *)v12 + 3) = v18;
    v20 = *((_OWORD *)v15 + 5);
    *((_OWORD *)v12 + 4) = v19;
    v21 = *((_OWORD *)v15 + 6);
    *((_OWORD *)v12 + 5) = v20;
    v22 = *((_OWORD *)v15 + 7);
    v15 += 64;
    *((_OWORD *)v12 + 6) = v21;
    *((_OWORD *)v12 + 7) = v22;
    v12 += 64;
    --v13;
  }
  while ( v13 );
  v23 = *(_OWORD *)v15;
  v24 = L"D:(A;;GR;;;AU)(A;;GR;;;AC)(A;;GR;;;S-1-15-3-1024-1692970155-4054893335-185714091-3362601943-3526593181-115981698"
         "4-2199008581-497492991)";
  v25 = 2;
  *(_OWORD *)v12 = v23;
  v26 = v132;
  do
  {
    v27 = *((_OWORD *)v24 + 1);
    *(_OWORD *)v26 = *(_OWORD *)v24;
    v28 = *((_OWORD *)v24 + 2);
    *((_OWORD *)v26 + 1) = v27;
    v29 = *((_OWORD *)v24 + 3);
    *((_OWORD *)v26 + 2) = v28;
    v30 = *((_OWORD *)v24 + 4);
    *((_OWORD *)v26 + 3) = v29;
    v31 = *((_OWORD *)v24 + 5);
    *((_OWORD *)v26 + 4) = v30;
    v32 = *((_OWORD *)v24 + 6);
    *((_OWORD *)v26 + 5) = v31;
    v33 = *((_OWORD *)v24 + 7);
    v24 += 64;
    *((_OWORD *)v26 + 6) = v32;
    *((_OWORD *)v26 + 7) = v33;
    v26 += 64;
    --v25;
  }
  while ( v25 );
  *(_OWORD *)v26 = *(_OWORD *)v24;
  v34 = v133;
  do
  {
    v35 = *((_OWORD *)v14 + 1);
    *(_OWORD *)v34 = *(_OWORD *)v14;
    v36 = *((_OWORD *)v14 + 2);
    *((_OWORD *)v34 + 1) = v35;
    v37 = *((_OWORD *)v14 + 3);
    *((_OWORD *)v34 + 2) = v36;
    v38 = *((_OWORD *)v14 + 4);
    *((_OWORD *)v34 + 3) = v37;
    v39 = *((_OWORD *)v14 + 5);
    *((_OWORD *)v34 + 4) = v38;
    v40 = *((_OWORD *)v14 + 6);
    *((_OWORD *)v34 + 5) = v39;
    v41 = *((_OWORD *)v14 + 7);
    v14 += 64;
    *((_OWORD *)v34 + 6) = v40;
    *((_OWORD *)v34 + 7) = v41;
    v34 += 64;
    --v1;
  }
  while ( v1 );
  v42 = *(_OWORD *)v14;
  g_DasRpcInterfaceGroupCreated = 0;
  *(_OWORD *)v34 = v42;
  g_bDasHostClientRpcInitialized = 0;
  wcscpy(v129, L"D:(A;;R;;;BA)");
  g_pszDasHostClientStringBinding = 0;
  g_bDasRpcIdle = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v128, 1u, &hMem, 0) )
    {
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v131, 1u, &v62, 0) )
      {
        if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v132, 1u, &v58, 0) )
        {
          if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v133, 1u, &v59, 0) )
          {
            if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v129, 1u, &v61, 0) )
            {
              v46 = SetAepStoreAccessSd(&v60);
              if ( v46 < 0 )
                goto LABEL_53;
              LODWORD(v63) = 1;
              LODWORD(v64) = 1;
              LODWORD(v65) = 1;
              *((_QWORD *)&v63 + 1) = DAF_Assoc_RpcEndpointObject;
              *((_QWORD *)&v64 + 1) = DAF_Inbound_RpcEndpointObject;
              *((_QWORD *)&v65 + 1) = DAF_Challenge_RpcEndpointObject;
              *((_QWORD *)&v66 + 1) = DAF_Query_RpcEndpointObject;
              *((_QWORD *)&v67 + 1) = DAF_AepStore_RpcEndpointObject;
              *((_QWORD *)&v68 + 1) = DAF_ProviderManagement_RpcEndpointObject;
              v75 = qword_180088130;
              v80 = &v63;
              v81 = L"Device Association Framework Association RPC Interface";
              v82 = hMem;
              v84 = qword_180087A40;
              v89 = &v64;
              v90 = L"Device Association Framework Inbound RPC Interface";
              v91 = v62;
              v93 = qword_180088D10;
              v98 = &v65;
              v99 = L"Device Association Framework Challenge RPC Interface";
              v100 = v58;
              v102 = qword_1800872F0;
              v107 = &v66;
              v108 = L"Device Association Framework Query RPC Interface";
              v109 = v59;
              v111 = qword_1800880D0;
              v116 = &v67;
              LODWORD(v66) = 1;
              LODWORD(v67) = 1;
              LODWORD(v68) = 1;
              v74 = 0;
              v76 = 0;
              v77 = 41;
              v78 = 1234;
              v79 = 0;
              v83 = 0;
              v85 = 0;
              v86 = 41;
              v87 = 1234;
              v88 = 0;
              v92 = 0;
              v94 = 0;
              v95 = 41;
              v96 = 1234;
              v97 = 0;
              v101 = 0;
              v103 = 0;
              v104 = 41;
              v105 = 1234;
              v106 = 0;
              v110 = 0;
              v112 = 0;
              v113 = 41;
              v114 = 1234;
              v115 = 0;
              v122 = 41;
              v117 = L"Device Association Framework AEP Store Access RPC Interface";
              v118 = v60;
              v119 = 0;
              v120 = qword_180087B30;
              v121 = 0;
              v125 = &v68;
              v126 = L"Device Association Framework Provider Management RPC Interface";
              v127 = v61;
              v70 = L"ncalrpc";
              v72 = SecurityDescriptor;
              v123 = 1234;
              v124 = 0;
              v69 = 0;
              v71 = 0;
              v73 = 10;
              v53 = RpcServerInterfaceGroupCreateW(
                      &v74,
                      6,
                      &v69,
                      1,
                      30,
                      DasRpcInterfaceGroupIdleCallback,
                      0,
                      &g_DasRpcInterfaceGroup);
              if ( v53 )
              {
                if ( v53 < 0 )
                  v46 = v53;
                else
                  v46 = (unsigned __int16)v53 | 0x80010000;
                if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                {
                  v47 = 18;
                  goto LABEL_52;
                }
              }
              else
              {
                g_DasRpcInterfaceGroupCreated = 1;
                v54 = RpcServerInterfaceGroupActivate(g_DasRpcInterfaceGroup);
                if ( v54 )
                {
                  v46 = v54 < 0 ? v54 : (unsigned __int16)v54 | 0x80010000;
                  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                  {
                    v47 = 19;
                    goto LABEL_52;
                  }
                }
              }
            }
            else
            {
              LastError = GetLastError();
              v46 = LastError;
              if ( LastError > 0 )
                v46 = (unsigned __int16)LastError | 0x80070000;
              if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                v47 = 17;
                goto LABEL_52;
              }
            }
          }
          else
          {
            v51 = GetLastError();
            v46 = v51;
            if ( v51 > 0 )
              v46 = (unsigned __int16)v51 | 0x80070000;
            if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v47 = 16;
              goto LABEL_52;
            }
          }
        }
        else
        {
          v50 = GetLastError();
          v46 = v50;
          if ( v50 > 0 )
            v46 = (unsigned __int16)v50 | 0x80070000;
          if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            v47 = 15;
            goto LABEL_52;
          }
        }
      }
      else
      {
        v49 = GetLastError();
        v46 = v49;
        if ( v49 > 0 )
          v46 = (unsigned __int16)v49 | 0x80070000;
        if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v47 = 14;
          goto LABEL_52;
        }
      }
    }
    else
    {
      v48 = GetLastError();
      v46 = v48;
      if ( v48 > 0 )
        v46 = (unsigned __int16)v48 | 0x80070000;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v47 = 13;
        goto LABEL_52;
      }
    }
  }
  else
  {
    v43 = GetLastError();
    v46 = v43;
    if ( v43 > 0 )
      v46 = (unsigned __int16)v43 | 0x80070000;
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v47 = 12;
LABEL_52:
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v44,
        v45,
        v47,
        &WPP_1ac4981e7da6391f895fbd18b31c02c5_Traceguids,
        v46);
    }
  }
LABEL_53:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( hMem )
    LocalFree(hMem);
  if ( v58 )
    LocalFree(v58);
  if ( v59 )
    LocalFree(v59);
  if ( v60 )
    LocalFree(v60);
  if ( v61 )
    LocalFree(v61);
  return (unsigned int)v46;
}

```

## disassembly

```asm
0x18004a5cc  push    rbp
0x18004a5ce  push    rbx
0x18004a5cf  push    rsi
0x18004a5d0  push    rdi
0x18004a5d1  lea     rbp, [rsp-678h]
0x18004a5d9  sub     rsp, 778h
0x18004a5e0  mov     rax, cs:__security_cookie
0x18004a5e7  xor     rax, rsp
0x18004a5ea  mov     [rbp+690h+var_30], rax
0x18004a5f1  xor     edi, edi
0x18004a5f3  lea     rax, [rbp+690h+StringSecurityDescriptor]
0x18004a5fa  xorps   xmm0, xmm0
0x18004a5fd  mov     [rsp+790h+SecurityDescriptor], rdi
0x18004a602  xorps   xmm1, xmm1
0x18004a605  mov     [rsp+790h+hMem], rdi
0x18004a60a  movups  [rsp+790h+var_718], xmm0
0x18004a60f  lea     r8d, [rdi+2]
0x18004a613  mov     [rsp+790h+var_720], rdi
0x18004a618  mov     edx, r8d
0x18004a61b  mov     [rsp+790h+var_740], rdi
0x18004a620  lea     r10d, [r8+7Eh]
0x18004a624  mov     [rsp+790h+var_738], rdi
0x18004a629  movups  [rbp+690h+var_708], xmm1
0x18004a62d  mov     [rsp+790h+var_730], rdi
0x18004a632  lea     rcx, aDAGrWdAGrAcAGr; "D:(A;;GR;;;WD)(A;;GR;;;AC)(A;;GR;;;S-1-"...
0x18004a639  movups  [rbp+690h+var_6F8], xmm0
0x18004a63d  mov     [rsp+790h+var_728], rdi
0x18004a642  movups  [rbp+690h+var_6E8], xmm1
0x18004a646  movups  [rbp+690h+var_6D8], xmm0
0x18004a64a  movups  [rbp+690h+var_6C8], xmm1
0x18004a64e  movups  xmm0, xmmword ptr [rcx]
0x18004a651  movups  xmm1, xmmword ptr [rcx+10h]
0x18004a655  movups  xmmword ptr [rax], xmm0
0x18004a658  movups  xmm0, xmmword ptr [rcx+20h]
0x18004a65c  movups  xmmword ptr [rax+10h], xmm1
0x18004a660  movups  xmm1, xmmword ptr [rcx+30h]
0x18004a664  movups  xmmword ptr [rax+20h], xmm0
0x18004a668  movups  xmm0, xmmword ptr [rcx+40h]
0x18004a66c  movups  xmmword ptr [rax+30h], xmm1
0x18004a670  movups  xmm1, xmmword ptr [rcx+50h]
0x18004a674  movups  xmmword ptr [rax+40h], xmm0
0x18004a678  movups  xmm0, xmmword ptr [rcx+60h]
0x18004a67c  movups  xmmword ptr [rax+50h], xmm1
0x18004a680  movups  xmm1, xmmword ptr [rcx+70h]
0x18004a684  add     rcx, r10
0x18004a687  movups  xmmword ptr [rax+60h], xmm0
0x18004a68b  movups  xmmword ptr [rax+70h], xmm1
0x18004a68f  add     rax, r10
0x18004a692  sub     rdx, 1
0x18004a696  jnz     short loc_18004A64E
0x18004a698  movups  xmm0, xmmword ptr [rcx]
0x18004a69b  lea     rcx, [rbp+690h+var_360]
0x18004a6a2  mov     r9, r8
0x18004a6a5  movups  xmm1, xmmword ptr cs:aDAGrAu; "D:(A;;GR;;;AU)"
0x18004a6ac  movups  xmmword ptr [rax], xmm0
0x18004a6af  lea     rax, aDAGrAuAGrAcAGr; "D:(A;;GR;;;AU)(A;;GR;;;AC)(A;;GR;;;S-1-"...
0x18004a6b6  movups  xmm0, xmmword ptr cs:aDAGrAu+0Eh; "R;;;AU)"
0x18004a6bd  mov     rdx, rax
0x18004a6c0  movups  xmmword ptr [rbp+690h+var_4B0], xmm1
0x18004a6c7  movups  xmmword ptr [rbp+690h+var_4B0+0Eh], xmm0
0x18004a6ce  movups  xmm0, xmmword ptr [rdx]
0x18004a6d1  movups  xmm1, xmmword ptr [rdx+10h]
0x18004a6d5  movups  xmmword ptr [rcx], xmm0
0x18004a6d8  movups  xmm0, xmmword ptr [rdx+20h]
0x18004a6dc  movups  xmmword ptr [rcx+10h], xmm1
0x18004a6e0  movups  xmm1, xmmword ptr [rdx+30h]
0x18004a6e4  movups  xmmword ptr [rcx+20h], xmm0
0x18004a6e8  movups  xmm0, xmmword ptr [rdx+40h]
0x18004a6ec  movups  xmmword ptr [rcx+30h], xmm1
0x18004a6f0  movups  xmm1, xmmword ptr [rdx+50h]
0x18004a6f4  movups  xmmword ptr [rcx+40h], xmm0
0x18004a6f8  movups  xmm0, xmmword ptr [rdx+60h]
0x18004a6fc  movups  xmmword ptr [rcx+50h], xmm1
0x18004a700  movups  xmm1, xmmword ptr [rdx+70h]
0x18004a704  add     rdx, r10
0x18004a707  movups  xmmword ptr [rcx+60h], xmm0
0x18004a70b  movups  xmmword ptr [rcx+70h], xmm1
0x18004a70f  add     rcx, r10
0x18004a712  sub     r9, 1
0x18004a716  jnz     short loc_18004A6CE
0x18004a718  movups  xmm0, xmmword ptr [rdx]
0x18004a71b  mov     rdx, rax
0x18004a71e  mov     r9, r8
0x18004a721  movups  xmmword ptr [rcx], xmm0
0x18004a724  lea     rcx, [rbp+690h+var_250]
0x18004a72b  movups  xmm0, xmmword ptr [rdx]
0x18004a72e  movups  xmm1, xmmword ptr [rdx+10h]
0x18004a732  movups  xmmword ptr [rcx], xmm0
0x18004a735  movups  xmm0, xmmword ptr [rdx+20h]
0x18004a739  movups  xmmword ptr [rcx+10h], xmm1
0x18004a73d  movups  xmm1, xmmword ptr [rdx+30h]
0x18004a741  movups  xmmword ptr [rcx+20h], xmm0
0x18004a745  movups  xmm0, xmmword ptr [rdx+40h]
0x18004a749  movups  xmmword ptr [rcx+30h], xmm1
0x18004a74d  movups  xmm1, xmmword ptr [rdx+50h]
0x18004a751  movups  xmmword ptr [rcx+40h], xmm0
0x18004a755  movups  xmm0, xmmword ptr [rdx+60h]
0x18004a759  movups  xmmword ptr [rcx+50h], xmm1
0x18004a75d  movups  xmm1, xmmword ptr [rdx+70h]
0x18004a761  add     rdx, r10
0x18004a764  movups  xmmword ptr [rcx+60h], xmm0
0x18004a768  movups  xmmword ptr [rcx+70h], xmm1
0x18004a76c  add     rcx, r10
0x18004a76f  sub     r9, 1
0x18004a773  jnz     short loc_18004A72B
0x18004a775  movups  xmm0, xmmword ptr [rdx]
0x18004a778  movups  xmmword ptr [rcx], xmm0
0x18004a77b  lea     rcx, [rbp+690h+var_140]
0x18004a782  movups  xmm0, xmmword ptr [rax]
0x18004a785  movups  xmm1, xmmword ptr [rax+10h]
0x18004a789  movups  xmmword ptr [rcx], xmm0
0x18004a78c  movups  xmm0, xmmword ptr [rax+20h]
0x18004a790  movups  xmmword ptr [rcx+10h], xmm1
0x18004a794  movups  xmm1, xmmword ptr [rax+30h]
0x18004a798  movups  xmmword ptr [rcx+20h], xmm0
0x18004a79c  movups  xmm0, xmmword ptr [rax+40h]
0x18004a7a0  movups  xmmword ptr [rcx+30h], xmm1
0x18004a7a4  movups  xmm1, xmmword ptr [rax+50h]
0x18004a7a8  movups  xmmword ptr [rcx+40h], xmm0
0x18004a7ac  movups  xmm0, xmmword ptr [rax+60h]
0x18004a7b0  movups  xmmword ptr [rcx+50h], xmm1
0x18004a7b4  movups  xmm1, xmmword ptr [rax+70h]
0x18004a7b8  add     rax, r10
0x18004a7bb  movups  xmmword ptr [rcx+60h], xmm0
0x18004a7bf  movups  xmmword ptr [rcx+70h], xmm1
0x18004a7c3  add     rcx, r10
0x18004a7c6  sub     r8, 1
0x18004a7ca  jnz     short loc_18004A782
0x18004a7cc  movups  xmm0, xmmword ptr [rax]
0x18004a7cf  xor     r9d, r9d; SecurityDescriptorSize
0x18004a7d2  lea     r8, [rsp+790h+SecurityDescriptor]; SecurityDescriptor
0x18004a7d7  movups  xmm1, xmmword ptr cs:aDAGrBa; "D:(A;;GR;;;BA)"
0x18004a7de  mov     cs:?g_DasRpcInterfaceGroupCreated@@3HA, edi; int g_DasRpcInterfaceGroupCreated
0x18004a7e4  movups  xmmword ptr [rcx], xmm0
0x18004a7e7  lea     esi, [r9+1]
0x18004a7eb  mov     cs:?g_bDasHostClientRpcInitialized@@3HA, edi; int g_bDasHostClientRpcInitialized
0x18004a7f1  movups  xmm0, xmmword ptr cs:aDAGrBa+0Eh; "R;;;BA)"
0x18004a7f8  mov     edx, esi; StringSDRevision
0x18004a7fa  lea     rcx, [rbp+690h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18004a801  movups  xmmword ptr [rbp+690h+var_490], xmm1
0x18004a808  mov     cs:?g_pszDasHostClientStringBinding@@3PEAGEA, rdi; ushort * g_pszDasHostClientStringBinding
0x18004a80f  movups  xmmword ptr [rbp+690h+var_490+0Eh], xmm0
0x18004a816  mov     cs:?g_bDasRpcIdle@@3HA, edi; int g_bDasRpcIdle
0x18004a81c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004a822  test    eax, eax
0x18004a824  jnz     short loc_18004A85A
0x18004a826  call    cs:__imp_GetLastError
0x18004a82c  mov     ebx, eax
0x18004a82e  test    eax, eax
0x18004a830  jle     short loc_18004A83B
0x18004a832  movzx   ebx, ax
0x18004a835  or      ebx, 80070000h
0x18004a83b  lea     rax, WPP_RECORDER_INITIALIZED
0x18004a842  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004a849  jz      loc_18004AD27
0x18004a84f  mov     r9d, 0Ch
0x18004a855  jmp     loc_18004AD07
0x18004a85a  xor     r9d, r9d; SecurityDescriptorSize
0x18004a85d  lea     r8, [rsp+790h+hMem]; SecurityDescriptor
0x18004a862  mov     edx, esi; StringSDRevision
0x18004a864  lea     rcx, [rbp+690h+var_4B0]; StringSecurityDescriptor
0x18004a86b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004a871  test    eax, eax
0x18004a873  jnz     short loc_18004A8A9
0x18004a875  call    cs:__imp_GetLastError
0x18004a87b  mov     ebx, eax
0x18004a87d  test    eax, eax
0x18004a87f  jle     short loc_18004A88A
0x18004a881  movzx   ebx, ax
0x18004a884  or      ebx, 80070000h
0x18004a88a  lea     rax, WPP_RECORDER_INITIALIZED
0x18004a891  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004a898  jz      loc_18004AD27
0x18004a89e  mov     r9d, 0Dh
0x18004a8a4  jmp     loc_18004AD07
0x18004a8a9  xor     r9d, r9d; SecurityDescriptorSize
0x18004a8ac  lea     r8, [rsp+790h+var_720]; SecurityDescriptor
0x18004a8b1  mov     edx, esi; StringSDRevision
0x18004a8b3  lea     rcx, [rbp+690h+var_360]; StringSecurityDescriptor
0x18004a8ba  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004a8c0  test    eax, eax
0x18004a8c2  jnz     short loc_18004A8F8
0x18004a8c4  call    cs:__imp_GetLastError
0x18004a8ca  mov     ebx, eax
0x18004a8cc  test    eax, eax
0x18004a8ce  jle     short loc_18004A8D9
0x18004a8d0  movzx   ebx, ax
0x18004a8d3  or      ebx, 80070000h
0x18004a8d9  lea     rax, WPP_RECORDER_INITIALIZED
0x18004a8e0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004a8e7  jz      loc_18004AD27
0x18004a8ed  mov     r9d, 0Eh
0x18004a8f3  jmp     loc_18004AD07
0x18004a8f8  xor     r9d, r9d; SecurityDescriptorSize
0x18004a8fb  lea     r8, [rsp+790h+var_740]; SecurityDescriptor
0x18004a900  mov     edx, esi; StringSDRevision
0x18004a902  lea     rcx, [rbp+690h+var_250]; StringSecurityDescriptor
0x18004a909  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004a90f  test    eax, eax
0x18004a911  jnz     short loc_18004A947
0x18004a913  call    cs:__imp_GetLastError
0x18004a919  mov     ebx, eax
0x18004a91b  test    eax, eax
0x18004a91d  jle     short loc_18004A928
0x18004a91f  movzx   ebx, ax
0x18004a922  or      ebx, 80070000h
0x18004a928  lea     rax, WPP_RECORDER_INITIALIZED
0x18004a92f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004a936  jz      loc_18004AD27
0x18004a93c  mov     r9d, 0Fh
0x18004a942  jmp     loc_18004AD07
0x18004a947  xor     r9d, r9d; SecurityDescriptorSize
0x18004a94a  lea     r8, [rsp+790h+var_738]; SecurityDescriptor
0x18004a94f  mov     edx, esi; StringSDRevision
0x18004a951  lea     rcx, [rbp+690h+var_140]; StringSecurityDescriptor
0x18004a958  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004a95e  test    eax, eax
0x18004a960  jnz     short loc_18004A996
0x18004a962  call    cs:__imp_GetLastError
0x18004a968  mov     ebx, eax
0x18004a96a  test    eax, eax
0x18004a96c  jle     short loc_18004A977
0x18004a96e  movzx   ebx, ax
0x18004a971  or      ebx, 80070000h
0x18004a977  lea     rax, WPP_RECORDER_INITIALIZED
0x18004a97e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004a985  jz      loc_18004AD27
0x18004a98b  mov     r9d, 10h
0x18004a991  jmp     loc_18004AD07
0x18004a996  xor     r9d, r9d; SecurityDescriptorSize
0x18004a999  lea     r8, [rsp+790h+var_728]; SecurityDescriptor
0x18004a99e  mov     edx, esi; StringSDRevision
0x18004a9a0  lea     rcx, [rbp+690h+var_490]; StringSecurityDescriptor
0x18004a9a7  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004a9ad  test    eax, eax
0x18004a9af  jnz     short loc_18004A9E5
0x18004a9b1  call    cs:__imp_GetLastError
0x18004a9b7  mov     ebx, eax
0x18004a9b9  test    eax, eax
0x18004a9bb  jle     short loc_18004A9C6
0x18004a9bd  movzx   ebx, ax
0x18004a9c0  or      ebx, 80070000h
0x18004a9c6  lea     rax, WPP_RECORDER_INITIALIZED
0x18004a9cd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004a9d4  jz      loc_18004AD27
0x18004a9da  mov     r9d, 11h
0x18004a9e0  jmp     loc_18004AD07
0x18004a9e5  lea     rcx, [rsp+790h+var_730]; SecurityDescriptor
0x18004a9ea  call    ?SetAepStoreAccessSd@@YAJPEAPEAX@Z; SetAepStoreAccessSd(void * *)
0x18004a9ef  mov     ebx, eax
0x18004a9f1  test    eax, eax
0x18004a9f3  js      loc_18004AD27
0x18004a9f9  xorps   xmm0, xmm0
0x18004a9fc  mov     dword ptr [rsp+790h+var_718], esi
0x18004aa00  mov     edx, 29h ; ')'
0x18004aa05  mov     dword ptr [rbp+690h+var_708], esi
0x18004aa08  lea     rax, DAF_Assoc_RpcEndpointObject
0x18004aa0f  mov     dword ptr [rbp+690h+var_6F8], esi
0x18004aa12  mov     qword ptr [rbp+690h+var_718+8], rax
0x18004aa16  lea     rax, DAF_Inbound_RpcEndpointObject
0x18004aa1d  mov     qword ptr [rbp+690h+var_708+8], rax
0x18004aa21  lea     rax, DAF_Challenge_RpcEndpointObject
0x18004aa28  mov     qword ptr [rbp+690h+var_6F8+8], rax
0x18004aa2c  lea     rax, DAF_Query_RpcEndpointObject
0x18004aa33  mov     qword ptr [rbp+690h+var_6E8+8], rax
0x18004aa37  lea     rax, DAF_AepStore_RpcEndpointObject
0x18004aa3e  mov     qword ptr [rbp+690h+var_6D8+8], rax
0x18004aa42  lea     rax, DAF_ProviderManagement_RpcEndpointObject
0x18004aa49  mov     qword ptr [rbp+690h+var_6C8+8], rax
0x18004aa4d  lea     rax, qword_180088130
0x18004aa54  mov     [rbp+690h+var_688], rax
0x18004aa58  lea     rax, [rsp+790h+var_718]
0x18004aa5d  mov     [rbp+690h+var_658], rax
0x18004aa61  lea     rax, aDeviceAssociat; "Device Association Framework Associatio"...
0x18004aa68  mov     [rbp+690h+var_650], rax
0x18004aa6c  mov     rax, [rsp+790h+hMem]
0x18004aa71  mov     [rbp+690h+var_648], rax
0x18004aa75  lea     rax, qword_180087A40
0x18004aa7c  mov     [rbp+690h+var_638], rax
0x18004aa80  lea     rax, [rbp+690h+var_708]
0x18004aa84  mov     [rbp+690h+var_608], rax
0x18004aa8b  lea     rax, aDeviceAssociat_3; "Device Association Framework Inbound RP"...
0x18004aa92  mov     [rbp+690h+var_600], rax
0x18004aa99  mov     rax, [rsp+790h+var_720]
0x18004aa9e  mov     [rbp+690h+var_5F8], rax
0x18004aaa5  lea     rax, qword_180088D10
0x18004aaac  mov     [rbp+690h+var_5E8], rax
0x18004aab3  lea     rax, [rbp+690h+var_6F8]
0x18004aab7  mov     [rbp+690h+var_5B8], rax
0x18004aabe  lea     rax, aDeviceAssociat_4; "Device Association Framework Challenge "...
0x18004aac5  mov     [rbp+690h+var_5B0], rax
0x18004aacc  mov     rax, [rsp+790h+var_740]
0x18004aad1  mov     [rbp+690h+var_5A8], rax
0x18004aad8  lea     rax, qword_1800872F0
0x18004aadf  mov     [rbp+690h+var_598], rax
0x18004aae6  lea     rax, [rbp+690h+var_6E8]
0x18004aaea  mov     [rbp+690h+var_568], rax
0x18004aaf1  lea     rax, aDeviceAssociat_0; "Device Association Framework Query RPC "...
0x18004aaf8  mov     [rbp+690h+var_560], rax
0x18004aaff  mov     rax, [rsp+790h+var_738]
  ... truncated ...
```
