# CCHlpCreateClusterNameCOIfNotExists(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int,int,int *,int *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1800795d0`
- end: `0x18007a36b`
- name: `?CCHlpCreateClusterNameCOIfNotExists@@YAKPEB_W000000HHPEAH1AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@22@Z`
- size: `3483`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, wchar_t *, __int64, int, int, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `32`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180002f50`
- `0x1800123b0`
- `0x18001cb44`
- `0x18001cc2c`
- `0x18001d67c`
- `0x18001ecdc`
- `0x180028f30`
- `0x180029578`
- `0x180029978`
- `0x18002a644`
- `0x180040418`
- `0x18006f910`
- `0x1800795d0`
- `0x18009dfd8`
- `0x18009e19c`
- `0x18009ef90`
- `0x18009f0a8`
- `0x18009fb5c`
- `0x1800a0940`
- `0x1800a0bdc`
- `0x1800a0c6c`
- `0x1800a1250`
- `0x1800a1450`
- `0x1800a16fc`
- `0x1800a18ac`
- `0x1800a1cd0`
- `0x1800a1d98`
- `0x1800a22a8`
- `0x1800a23b4`
- `0x1800a26f8`
- `0x1800a2a74`
- `0x1800b5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180079855`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180079855`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079ec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079ec0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a209`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a297`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a2a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a2b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a2ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a2d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a2eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a2fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a30b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a32e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a340`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a209`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a297`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a2a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a2b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a2ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a2d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a2eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a2fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a30b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a32e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a340`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x18007a31c`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x18007a31c`
- `OLEAUT32!__imp_SysFreeString` at `0x18007a289`
- `OLEAUT32!__imp_SysFreeString` at `0x18007a289`
- `samcli!NetUserSetInfo` at `0x180079994`
- `samcli!NetUserSetInfo` at `0x180079994`
- `NTDSAPI!DsWriteAccountSpnW` at `0x18007a076`
- `NTDSAPI!DsWriteAccountSpnW` at `0x18007a076`
- `NTDSAPI!DsBindW` at `0x180079727`
- `NTDSAPI!DsBindW` at `0x180079727`

## string_xrefs

- `0x180079a1f`: `Computer object %ws is already in use. Error %d.`
- `0x180079959`: `The AD environment is Read-Only. But the account <%ws> is disabled on DC <%ws>. The account needs to be enabled.`
- `0x180079783`: `Failed to check whether the computer object for node %ws exists in the domain. DC %ws. Error %d.`
- `0x180079795`: `CCHlpCreateClusterNameCOIfNotExists`
- `0x180079815`: `CCHlpCreateClusterNameCOIfNotExists`
- `0x180079832`: `CCHlpCreateClusterNameCOIfNotExists`
- `0x180079a6f`: `CCHlpCreateClusterNameCOIfNotExists`
- `0x180079a8a`: `CCHlpCreateClusterNameCOIfNotExists`
- `0x180079a5d`: `The AD environment is Read-Only. But the account <%ws> is not found on DC <%ws>. The account needs to be pre-created and enabled.`
- `0x180079bb2`: `Failed to query status of the computer object for node %ws on DC %ws. Error %d.`
- `0x180079bfd`: `The computer object for node %ws is not found on DC %ws.`
- `0x180079c7a`: `Using OU %ws for the CNO from node %ws computer object OU.`
- `0x180079d0e`: `Failed to create computer object %ws on DC %ws with OU %ws. Error %d.`
- `0x180079d8a`: `Failed to query FQDN of computer object %ws on DC %ws. Error %d.`
- `0x180079dd9`: `Computer object %ws doesn't exist on DC %ws. Error %d.`
- `0x180079e0b`: `Configuring Computer Object %s to act as the CNO on DC %ws`
- `0x18007a240`: `Cannot get GUID of computer object with FQDN: <%s>, Error: <%d>.`
- `0x180079e92`: `Configuring Cluster CNO resource.`
- `0x180079ecc`: `Cannot get running context of this thread.  Error <%d>.`
- `0x180079f8d`: `Cannot allocate SID.  Error <%d>.`
- `0x18007a097`: `Cannot write SPN list of object.  Error <%d>. Retrying.`
- `0x18007a0bc`: `Cannot write SPN list of object.  Error <%d>.`
- `0x18007a1b6`: `Error while setting special permissions on the Cluster Computer Object: <%ws>. It looks like the DACL in the SD is too big.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCHlpCreateClusterNameCOIfNotExists(
        const WCHAR *a1,
        const WCHAR *a2,
        const WCHAR *a3,
        const WCHAR *a4,
        void **a5,
        wchar_t *a6,
        __int64 a7,
        int a8,
        int a9,
        _DWORD *a10,
        _DWORD *a11,
        __int64 a12,
        __int64 a13,
        __int64 a14)
{
  const WCHAR *v15; // rsi
  WCHAR *v16; // r12
  WCHAR *v17; // r14
  void *v18; // r15
  int v19; // eax
  DWORD LastError; // ebx
  int IsComputerObjectInDS; // r14d
  const WCHAR *v22; // rcx
  DWORD v23; // eax
  const char *v24; // rdi
  const wchar_t *v25; // rax
  __int64 v26; // r9
  int v27; // edx
  int v28; // ecx
  int v29; // r8d
  const WCHAR *v30; // rax
  const WCHAR *v31; // r14
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // r8
  __int64 v35; // rax
  __int64 v36; // rax
  char v37; // bl
  int v38; // eax
  int v39; // eax
  const WCHAR *v40; // rax
  int ComputerObject; // eax
  const WCHAR *v42; // rcx
  const WCHAR *v43; // rax
  const WCHAR *v44; // rdx
  int v45; // eax
  const WCHAR *v46; // rax
  const wchar_t *v47; // rax
  __int64 v48; // r9
  const WCHAR *v49; // rax
  const WCHAR *v50; // rcx
  const WCHAR *v51; // rax
  int ComputerObjectViaFQDN; // ecx
  __int64 v53; // r8
  void **SidOfCallingThread; // rax
  wchar_t **v55; // r8
  unsigned int v56; // r9d
  int v57; // eax
  const wchar_t *v58; // rax
  __int64 v59; // r9
  DWORD WellKnownSid; // eax
  wchar_t **v61; // r8
  unsigned int v62; // r9d
  int v63; // eax
  DWORD v64; // eax
  int v65; // r8d
  int v66; // r9d
  DWORD v67; // eax
  char i; // r13
  const WCHAR *v69; // r13
  DWORD OSAttributesForNode; // eax
  __int64 v71; // r8
  const WCHAR *v72; // rax
  __int64 v73; // r8
  DWORD v74; // eax
  int v75; // r9d
  int parm_erra; // [rsp+20h] [rbp-E0h]
  int parm_err; // [rsp+20h] [rbp-E0h]
  WCHAR *v79; // [rsp+28h] [rbp-D8h]
  int v80; // [rsp+28h] [rbp-D8h]
  int v81[2]; // [rsp+28h] [rbp-D8h]
  int v82[2]; // [rsp+28h] [rbp-D8h]
  int v83[2]; // [rsp+28h] [rbp-D8h]
  int v84[2]; // [rsp+30h] [rbp-D0h]
  int v85[2]; // [rsp+30h] [rbp-D0h]
  int v86; // [rsp+30h] [rbp-D0h]
  int v87; // [rsp+30h] [rbp-D0h]
  wchar_t *v88; // [rsp+30h] [rbp-D0h]
  int v89[2]; // [rsp+30h] [rbp-D0h]
  int v90; // [rsp+38h] [rbp-C8h]
  int v91; // [rsp+38h] [rbp-C8h]
  int v92; // [rsp+38h] [rbp-C8h]
  int v93; // [rsp+40h] [rbp-C0h]
  int v94; // [rsp+40h] [rbp-C0h]
  void *v95; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR pszAccount; // [rsp+58h] [rbp-A8h] BYREF
  void **v97; // [rsp+60h] [rbp-A0h]
  int v98; // [rsp+68h] [rbp-98h] BYREF
  int v99; // [rsp+6Ch] [rbp-94h] BYREF
  int v100; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL v101; // [rsp+78h] [rbp-88h] BYREF
  BYTE buf[8]; // [rsp+80h] [rbp-80h] BYREF
  struct IDirectoryObject *v103; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL v104; // [rsp+90h] [rbp-70h] BYREF
  HLOCAL v105; // [rsp+98h] [rbp-68h] BYREF
  void *v106; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE phDS; // [rsp+A8h] [rbp-58h] BYREF
  DWORD v108; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v109; // [rsp+B8h] [rbp-48h] BYREF
  const WCHAR *v110; // [rsp+C0h] [rbp-40h]
  __int64 v111; // [rsp+C8h] [rbp-38h] BYREF
  BSTR bstrString; // [rsp+D0h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+D8h] [rbp-28h] BYREF
  HLOCAL v114; // [rsp+E0h] [rbp-20h] BYREF
  HLOCAL v115; // [rsp+E8h] [rbp-18h] BYREF
  const WCHAR *v116; // [rsp+F0h] [rbp-10h]
  HLOCAL v117; // [rsp+F8h] [rbp-8h] BYREF
  PCWSTR v118; // [rsp+100h] [rbp+0h]
  int v119; // [rsp+108h] [rbp+8h]
  _DWORD *v120; // [rsp+110h] [rbp+10h]
  __int64 v121; // [rsp+118h] [rbp+18h]
  __int128 v122; // [rsp+120h] [rbp+20h] BYREF
  __int64 v123; // [rsp+130h] [rbp+30h]
  __int128 v124; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v125[16]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int64 v126; // [rsp+160h] [rbp+60h]
  _BYTE v127[32]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v128[32]; // [rsp+190h] [rbp+90h] BYREF
  WCHAR username[20]; // [rsp+1B0h] [rbp+B0h] BYREF

  v110 = a4;
  v15 = a2;
  v116 = a2;
  v118 = a1;
  v97 = a5;
  v121 = a7;
  *(_QWORD *)&v122 = a10;
  v120 = a11;
  v123 = a12;
  *(_QWORD *)&v124 = a13;
  v109 = a14;
  v16 = 0;
  v119 = 0;
  phDS = 0;
  v17 = 0;
  pszAccount = 0;
  v18 = 0;
  v95 = 0;
  v117 = 0;
  v114 = 0;
  hMem = 0;
  v101 = 0;
  v104 = 0;
  v105 = 0;
  v115 = 0;
  v100 = 0;
  v108 = 0;
  bstrString = 0;
  v99 = 0;
  *(_DWORD *)buf = 0;
  v111 = 0;
  v106 = 0;
  v103 = 0;
  v98 = 0;
  if ( a10 )
    *a10 = 0;
  if ( a11 )
    *a11 = 0;
  v19 = StringCchPrintfW(username, 0x11u, L"%.*ws$");
  LastError = v19;
  if ( v19 < 0 )
  {
    if ( (v19 & 0x1FFF0000) == 0x70000 )
      LastError = (unsigned __int16)v19;
    goto LABEL_164;
  }
  v16 = (WCHAR *)ClRtlDupString(a6);
  LastError = DsBindW(v16, 0, &phDS);
  if ( LastError )
    goto LABEL_164;
  IsComputerObjectInDS = ClRtlIsComputerObjectInDS(
                           (_DWORD)v15,
                           (_DWORD)a3,
                           (_DWORD)v16,
                           (unsigned int)&v100,
                           (__int64)&pszAccount);
  if ( IsComputerObjectInDS >= 0 )
  {
    if ( v100 )
    {
      v17 = (WCHAR *)pszAccount;
      v23 = ClRtlParseDistinguishedName(pszAccount, &hMem, &v101);
      LastError = v23;
      v24 = (const char *)&base;
      if ( v23 )
      {
        if ( v17 )
          v24 = (const char *)v17;
        v84[0] = v23;
        v79 = (WCHAR *)v24;
        v25 = L"Failed to parse distinguished name for VCO %ws. Error %d.";
        v26 = 268;
LABEL_23:
        TraceMsg(2, 0, L"CCHlpCreateClusterNameCOIfNotExists", v26, v25, v79, *(_QWORD *)v84);
LABEL_163:
        v18 = v95;
        goto LABEL_164;
      }
      if ( v97 && (unsigned int)_o__wcsicmp(v101) )
      {
        v80 = (int)v97;
        TraceMsg(
          2,
          0,
          L"CCHlpCreateClusterNameCOIfNotExists",
          279,
          L"Input OU %ws did not match OU %ws where the object was found.");
        LastError = 87;
        v122 = CLUSAPI_CREATE_MISMATCHED_OU;
        ClusterLogEvent3(v28, v27, v29, (unsigned int)&v122, parm_erra, v80, (__int64)hMem, (__int64)v97, (__int64)v101);
      }
      v30 = &base;
      if ( v101 )
        v30 = (const WCHAR *)v101;
      TraceMsg(4, 0, L"CCHlpCreateClusterNameCOIfNotExists", 297, L"The OU used for the CNO is %ws", v30);
      if ( LastError )
        goto LABEL_163;
      if ( !(unsigned int)ClRtlGetObjectFlags(v17, v16, &v99) )
      {
        if ( (v99 & 2) != 0 )
        {
          if ( a9 )
          {
            LastError = 1327;
            if ( v16 )
              v24 = (const char *)v16;
            *(_QWORD *)v84 = v24;
            v79 = username;
            v25 = L"The AD environment is Read-Only. But the account <%ws> is disabled on DC <%ws>. The account needs to be enabled.";
            v26 = 316;
            goto LABEL_23;
          }
          *(_DWORD *)buf = v99 & 0xFFFFFFFD;
          LastError = NetUserSetInfo(v16, username, 0x3F0u, buf, &v108);
          if ( v120 )
            *v120 = 1;
          if ( LastError )
            goto LABEL_163;
        }
        else if ( a8 && !a9 )
        {
          LastError = 5936;
          if ( !a3 )
            a3 = &base;
          v84[0] = 5936;
          v79 = (WCHAR *)a3;
          v25 = L"Computer object %ws is already in use. Error %d.";
          v26 = 340;
          goto LABEL_23;
        }
      }
      LastError = ClRtlKerbSetPassword(username, v16, v118);
      if ( LastError )
      {
        if ( v16 )
          v24 = (const char *)v16;
        *(_QWORD *)v84 = v24;
        v79 = username;
        v25 = L"Unable to set password on <%ws>, DC is %ws.";
        v26 = 358;
        goto LABEL_23;
      }
LABEL_108:
      v50 = &base;
      if ( v16 )
        LODWORD(v50) = (_DWORD)v16;
      v51 = a3;
      if ( !a3 )
        v51 = &base;
      v86 = (int)v50;
      TraceMsg(
        4,
        0,
        L"CCHlpCreateClusterNameCOIfNotExists",
        490,
        L"Configuring Computer Object %s to act as the CNO on DC %ws",
        v51);
      ComputerObjectViaFQDN = ClRtlGetComputerObjectViaFQDN(v17, v16, &v103);
      if ( ComputerObjectViaFQDN < 0
        || (ComputerObjectViaFQDN = ((__int64 (__fastcall *)(struct IDirectoryObject *, GUID *, __int64 *))v103->lpVtbl->QueryInterface)(
                                      v103,
                                      &IID_IADs,
                                      &v111),
            ComputerObjectViaFQDN < 0)
        || (ComputerObjectViaFQDN = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v111 + 72LL))(
                                      v111,
                                      &bstrString),
            ComputerObjectViaFQDN < 0) )
      {
        LastError = (unsigned __int16)ComputerObjectViaFQDN;
        if ( (ComputerObjectViaFQDN & 0x1FFF0000) != 0x70000 )
          LastError = ComputerObjectViaFQDN;
        if ( v17 )
          v24 = (const char *)v17;
        ClRtlLogPrint(1, "Cannot get GUID of computer object with FQDN: <%s>, Error: <%d>.", v24, LastError);
        goto LABEL_163;
      }
      std::wstring::assign(v123, bstrString, v53);
      TraceMsg(4, 0, L"CCHlpCreateClusterNameCOIfNotExists", 507, L"Configuring Cluster CNO resource.");
      SidOfCallingThread = (void **)ClRtlGetSidOfCallingThread();
      v97 = SidOfCallingThread;
      if ( !SidOfCallingThread )
      {
        LastError = GetLastError();
        v81[0] = LastError;
        TraceMsg(
          2,
          0,
          L"CCHlpCreateClusterNameCOIfNotExists",
          517,
          L"Cannot get running context of this thread.  Error <%d>.",
          *(_QWORD *)v81);
        goto LABEL_156;
      }
      if ( a9 )
      {
LABEL_155:
        LocalFree(SidOfCallingThread);
LABEL_156:
        if ( v106 )
          ClRtlFreeWellKnownSid(&v106);
        goto LABEL_163;
      }
      v57 = ProvideSpecialPermissions(
              v103,
              *SidOfCallingThread,
              v55,
              v56,
              287179199,
              5,
              v86,
              v90,
              v93,
              (enum ProvideSpecialPermissionsErrorStep *)&v98);
      LastError = v57;
      if ( v57 >= 0 )
      {
        WellKnownSid = ClRtlAllocateAndCreateWellKnownSid(WinSelfSid);
        LastError = WellKnownSid;
        if ( WellKnownSid )
        {
          v82[0] = WellKnownSid;
          TraceMsg(
            2,
            0,
            L"CCHlpCreateClusterNameCOIfNotExists",
            533,
            L"Cannot allocate SID.  Error <%d>.",
            *(_QWORD *)v82);
LABEL_149:
          if ( v98 == 8 && LastError == 87 )
          {
            LastError = 1336;
            if ( v17 )
              v24 = (const char *)v17;
            TraceMsg(
              2,
              0,
              L"CCHlpCreateClusterNameCOIfNotExists",
              624,
              L"Error while setting special permissions on the Cluster Computer Object: <%ws>. It looks like the DACL in t"
               "he SD is too big.",
              v24);
            v109 = (__int64)v17;
            v124 = CLUSAPI_CREATE_CANNOT_SET_AD_DACL;
            ClRtlpReportEvent(1, (unsigned int)&v124, 1, v75, (__int64)&v109);
          }
          SidOfCallingThread = v97;
          goto LABEL_155;
        }
        v63 = ProvideSpecialPermissions(
                v103,
                v106,
                v61,
                v62,
                287179199,
                5,
                v87,
                v92,
                v94,
                (enum ProvideSpecialPermissionsErrorStep *)&v98);
        LastError = v63;
        if ( v63 >= 0 )
        {
          v64 = ClRtlModifyObjectForAccidentalDeletion(v17, v16);
          LastError = v64;
          if ( v64 )
          {
            v82[0] = v64;
            TraceMsg(
              2,
              0,
              L"CCHlpCreateClusterNameCOIfNotExists",
              547,
              L"Cannot provide permissions to protect object from accidental deletion.  Error <%d>",
              *(_QWORD *)v82);
          }
          else
          {
            v67 = ClRtlPopulateSPNList((_DWORD)a3, (_DWORD)v110, v65, v66, parm_err, (__int64)&v115);
            LastError = v67;
            if ( v67 )
            {
              v83[0] = v67;
              TraceMsg(
                2,
                0,
                L"CCHlpCreateClusterNameCOIfNotExists",
                559,
                L"Cannot populate SPN list of object.  Error <%d>.",
                *(_QWORD *)v83);
            }
            else
            {
              for ( i = 0; ; i = 1 )
              {
                LastError = DsWriteAccountSpnW(phDS, DS_SPN_ADD_SPN_OP, v17, *(_DWORD *)v115, (LPCWSTR *)v115 + 1);
                if ( !LastError )
                  break;
                if ( LastError != 8206 || i )
                {
                  v83[0] = LastError;
                  TraceMsg(
                    2,
                    0,
                    L"CCHlpCreateClusterNameCOIfNotExists",
                    579,
                    L"Cannot write SPN list of object.  Error <%d>.",
                    *(_QWORD *)v83);
                  goto LABEL_149;
                }
                v83[0] = 8206;
                TraceMsg(
                  3,
                  0,
                  L"CCHlpCreateClusterNameCOIfNotExists",
                  577,
                  L"Cannot write SPN list of object.  Error <%d>. Retrying.",
                  *(_QWORD *)v83);
              }
              v69 = v116;
              OSAttributesForNode = ClRtlGetOSAttributesForNode(v116, &v104, &v105);
              LastError = OSAttributesForNode;
              if ( OSAttributesForNode )
              {
                if ( !v69 )
                  v69 = &base;
                v89[0] = OSAttributesForNode;
                TraceMsg(
                  2,
                  0,
                  L"CCHlpCreateClusterNameCOIfNotExists",
                  593,
                  L"Unable to get OS attributes for name <%ws> from AD. Error <%d>.",
                  v69,
                  *(_QWORD *)v89);
              }
              else
              {
                LastError = ClRtlSetOSAttributesInAD(v17, v16, v104, v105);
                if ( LastError )
                {
                  v72 = &base;
                  if ( v17 )
                    v72 = v17;
                  v89[0] = LastError;
                  TraceMsg(
                    2,
                    0,
                    L"CCHlpCreateClusterNameCOIfNotExists",
                    599,
                    L"Unable to set OS attributes for name <%ws> to AD. Error <%d>.",
                    v72,
                    *(_QWORD *)v89);
                }
                else
                {
                  std::wstring::assign(v124, v104, v71);
                  std::wstring::assign(v109, v105, v73);
                  v74 = ClRtlSetSupportedEncTypes(v69, v17, v16);
                  LastError = v74;
                  if ( v74 )
                  {
                    v83[0] = v74;
                    TraceMsg(
                      2,
                      0,
                      L"CCHlpCreateClusterNameCOIfNotExists",
                      611,
                      L"Could not set supported encryption types in AD.  Error <%d>.",
                      *(_QWORD *)v83);
                  }
                }
              }
            }
          }
          goto LABEL_149;
        }
        if ( (v63 & 0x1FFF0000) == 0x70000 )
          LastError = (unsigned __int16)v63;
        v88 = off_1800B80B0[v98];
        v58 = L"Cannot provide self special permissions to the object.  Error <%d> (Step %ws).";
        v59 = 540;
      }
      else
      {
        if ( (v57 & 0x1FFF0000) == 0x70000 )
          LastError = (unsigned __int16)v57;
        v88 = off_1800B80B0[v98];
        v58 = L"Cannot provide user special permissions to the object.  Error <%d> (Step %ws).";
        v59 = 527;
      }
      v82[0] = LastError;
      TraceMsg(2, 0, L"CCHlpCreateClusterNameCOIfNotExists", v59, v58, *(_QWORD *)v82, v88);
      goto LABEL_149;
    }
    v24 = (const char *)&base;
    if ( a9 )
    {
      LastError = 4312;
      if ( v16 )
        v24 = (const char *)v16;
      TraceMsg(
        2,
        0,
        L"CCHlpCreateClusterNameCOIfNotExists",
        370,
        L"The AD environment is Read-Only. But the account <%ws> is not found on DC <%ws>. The account needs to be pre-cre"
         "ated and enabled.",
        username,
        v24);
      goto LABEL_52;
    }
    v31 = v116;
    v32 = (__int64)v97;
    if ( v116 && !v97 )
    {
      v99 = 0;
      std::wstring::wstring(v125, v116);
      v33 = std::wstring::find(v125, L".");
      if ( v33 != -1 )
      {
        v35 = std::wstring::substr(v125, v127, v34, v33);
        std::wstring::operator=(v125, v35);
        std::wstring::_Tidy_deallocate(v127);
      }
      if ( v126 <= 0xF )
      {
        v36 = std::wstring::wstring(v127, v125);
        v37 = 2;
      }
      else
      {
        v36 = std::wstring::substr(v125, v128, v34, 15);
        v37 = 1;
      }
      std::wstring::operator=(v125, v36);
      if ( (v37 & 2) != 0 )
      {
        v37 &= ~2u;
        std::wstring::_Tidy_deallocate(v127);
      }
      if ( (v37 & 1) != 0 )
        std::wstring::_Tidy_deallocate(v128);
      v38 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v125);
      v39 = ClRtlIsComputerObjectInDS((_DWORD)v31, v38, (_DWORD)v16, (unsigned int)&v99, (__int64)&v95);
      LastError = v39;
      if ( v39 < 0 )
      {
        if ( (v39 & 0x1FFF0000) == 0x70000 )
          LastError = (unsigned __int16)v39;
        if ( v16 )
          v24 = (const char *)v16;
        TraceMsg(
          2,
          0,
          L"CCHlpCreateClusterNameCOIfNotExists",
          412,
          L"Failed to query status of the computer object for node %ws on DC %ws. Error %d.",
          v31,
          v24,
          LastError);
LABEL_70:
        std::wstring::_Tidy_deallocate(v125);
        goto LABEL_52;
      }
      if ( !v99 )
      {
        LastError = 4312;
        if ( v16 )
          v24 = (const char *)v16;
        TraceMsg(
          2,
          0,
          L"CCHlpCreateClusterNameCOIfNotExists",
          420,
          L"The computer object for node %ws is not found on DC %ws.",
          v31,
          v24);
        goto LABEL_70;
      }
      LastError = ClRtlParseDistinguishedName(v95, &v117, &v114);
      if ( LastError )
      {
        if ( v95 )
          v24 = (const char *)v95;
        TraceMsg(
          2,
          0,
          L"CCHlpCreateClusterNameCOIfNotExists",
          426,
          L"Failed to parse distinguished name for node %ws. Error %d.",
          v24,
          LastError);
        goto LABEL_70;
      }
      v97 = (void **)v114;
      v40 = &base;
      if ( v114 )
        v40 = (const WCHAR *)v114;
      TraceMsg(
        4,
        0,
        L"CCHlpCreateClusterNameCOIfNotExists",
        434,
        L"Using OU %ws for the CNO from node %ws computer object OU.",
        v40,
        v31);
      std::wstring::_Tidy_deallocate(v125);
      v32 = (__int64)v97;
    }
    ComputerObject = ClRtlCreateComputerObject((_DWORD)v110, (_DWORD)v118, (_DWORD)v16, v121, v32);
    if ( ComputerObject >= 0 )
    {
      if ( (_QWORD)v122 )
        *(_DWORD *)v122 = 1;
      v45 = ClRtlIsComputerObjectInDS((_DWORD)v31, (_DWORD)a3, (_DWORD)v16, (unsigned int)&v100, (__int64)&pszAccount);
      if ( v45 >= 0 )
      {
        if ( v100 )
        {
          v17 = (WCHAR *)pszAccount;
          goto LABEL_108;
        }
        LastError = 8240;
        v49 = &base;
        if ( v16 )
          v49 = v16;
        v91 = 8240;
        *(_QWORD *)v85 = v49;
        v47 = L"Computer object %ws doesn't exist on DC %ws. Error %d.";
        v48 = 482;
      }
      else
      {
        LastError = (unsigned __int16)v45;
        if ( (v45 & 0x1FFF0000) != 0x70000 )
          LastError = v45;
        v46 = &base;
        if ( v16 )
          v46 = v16;
        v91 = LastError;
        *(_QWORD *)v85 = v46;
        v47 = L"Failed to query FQDN of computer object %ws on DC %ws. Error %d.";
        v48 = 474;
      }
      if ( !a3 )
        a3 = &base;
      TraceMsg(2, 0, L"CCHlpCreateClusterNameCOIfNotExists", v48, v47, a3, *(_QWORD *)v85, v91);
    }
    else
    {
      LastError = (unsigned __int16)ComputerObject;
      if ( (ComputerObject & 0x1FFF0000) != 0x70000 )
        LastError = ComputerObject;
      v42 = &base;
      if ( v97 )
        v42 = (const WCHAR *)v97;
      v43 = &base;
      if ( v16 )
        v43 = v16;
      v44 = v110;
      if ( !v110 )
        v44 = &base;
      TraceMsg(
        2,
        0,
        L"CCHlpCreateClusterNameCOIfNotExists",
        451,
        L"Failed to create computer object %ws on DC %ws with OU %ws. Error %d.",
        v44,
        v43,
        v42,
        LastError);
    }
LABEL_52:
    v17 = (WCHAR *)pszAccount;
    goto LABEL_163;
  }
  v22 = &base;
  if ( v16 )
    v22 = v16;
  if ( !v15 )
    v15 = &base;
  TraceMsg(
    LastError + 2,
    0,
    L"CCHlpCreateClusterNameCOIfNotExists",
    254,
    L"Failed to check whether the computer object for node %ws exists in the domain. DC %ws. Error %d.",
    v15,
    v22,
    0);
  v18 = v95;
  if ( (IsComputerObjectInDS & 0x1FFF0000) == 0x70000 )
    LastError = (unsigned __int16)IsComputerObjectInDS;
  else
    LastError = IsComputerObjectInDS;
  v17 = (WCHAR *)pszAccount;
LABEL_164:
  if ( v103 )
    ((void (__fastcall *)(struct IDirectoryObject *))v103->lpVtbl->Release)(v103);
  if ( v111 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v17 )
    LocalFree(v17);
  if ( v18 )
    LocalFree(v18);
  if ( hMem )
    LocalFree(hMem);
  if ( v101 )
    LocalFree(v101);
  if ( v117 )
    LocalFree(v117);
  if ( v114 )
    LocalFree(v114);
  if ( v115 )
    LocalFree(v115);
  if ( v16 )
    LocalFree(v16);
  if ( phDS )
    DsUnBindW(&phDS);
  if ( v104 )
    LocalFree(v104);
  if ( v105 )
    LocalFree(v105);
  return LastError;
}

```

## disassembly

```asm
0x1800795d0  push    rbp
0x1800795d2  push    rbx
0x1800795d3  push    rsi
0x1800795d4  push    rdi
0x1800795d5  push    r12
0x1800795d7  push    r13
0x1800795d9  push    r14
0x1800795db  push    r15
0x1800795dd  lea     rbp, [rsp-0E8h]
0x1800795e5  sub     rsp, 1E8h
0x1800795ec  mov     rax, cs:__security_cookie
0x1800795f3  xor     rax, rsp
0x1800795f6  mov     [rbp+120h+var_48], rax
0x1800795fd  mov     [rbp+120h+var_160], r9
0x180079601  mov     r13, r8
0x180079604  mov     rsi, rdx
0x180079607  mov     [rbp+120h+var_130], rdx
0x18007960b  mov     [rbp+120h+var_120], rcx
0x18007960f  mov     rax, [rbp+120h+arg_20]
0x180079616  mov     [rsp+220h+var_1C0], rax
0x18007961b  mov     rdi, [rbp+120h+arg_28]
0x180079622  mov     rax, [rbp+120h+arg_30]
0x180079629  mov     [rbp+120h+var_108], rax
0x18007962d  mov     rcx, [rbp+120h+arg_48]
0x180079634  mov     qword ptr [rbp+120h+var_100], rcx
0x180079638  mov     rax, [rbp+120h+arg_50]
0x18007963f  mov     [rbp+120h+var_110], rax
0x180079643  mov     rdx, [rbp+120h+arg_58]
0x18007964a  mov     [rbp+120h+var_F0], rdx
0x18007964e  mov     rdx, [rbp+120h+arg_60]
0x180079655  mov     qword ptr [rbp+120h+var_E0], rdx
0x180079659  mov     rdx, [rbp+120h+arg_68]
0x180079660  mov     [rbp+120h+var_168], rdx
0x180079664  xor     r12d, r12d
0x180079667  mov     [rbp+120h+var_118], r12d
0x18007966b  mov     [rbp+120h+phDS], r12
0x18007966f  mov     r14d, r12d
0x180079672  mov     [rsp+220h+pszAccount], r12
0x180079677  mov     r15d, r12d
0x18007967a  mov     [rsp+220h+var_1D0], r12
0x18007967f  mov     [rbp+120h+var_128], r12
0x180079683  mov     [rbp+120h+var_140], r12
0x180079687  mov     [rbp+120h+hMem], r12
0x18007968b  mov     [rsp+220h+var_1A8], r12
0x180079690  mov     [rbp+120h+var_190], r12
0x180079694  mov     [rbp+120h+var_188], r12
0x180079698  mov     [rbp+120h+var_138], r12
0x18007969c  mov     [rsp+220h+var_1B0], r12d
0x1800796a1  mov     [rbp+120h+var_170], r12d
0x1800796a5  mov     [rbp+120h+bstrString], r12
0x1800796a9  mov     [rsp+220h+var_1B4], r12d
0x1800796ae  mov     dword ptr [rbp+120h+buf], r12d
0x1800796b2  mov     [rbp+120h+var_158], r12
0x1800796b6  mov     [rbp+120h+var_180], r12
0x1800796ba  mov     [rbp+120h+var_198], r12
0x1800796be  mov     [rsp+220h+var_1B8], r12d
0x1800796c3  test    rcx, rcx
0x1800796c6  jz      short loc_1800796CB
0x1800796c8  mov     [rcx], r12d
0x1800796cb  test    rax, rax
0x1800796ce  jz      short loc_1800796D3
0x1800796d0  mov     [rax], r12d
0x1800796d3  mov     [rsp+220h+parm_err], r13
0x1800796d8  mov     r9d, 0Fh
0x1800796de  lea     r8, aWs; "%.*ws$"
0x1800796e5  lea     edx, [r9+2]; unsigned __int64
0x1800796e9  lea     rcx, [rbp+120h+username]; wchar_t *
0x1800796f0  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800796f5  mov     ebx, eax
0x1800796f7  test    eax, eax
0x1800796f9  jns     short loc_180079713
0x1800796fb  and     eax, 1FFF0000h
0x180079700  cmp     eax, 70000h
0x180079705  jnz     loc_18007A256
0x18007970b  movzx   ebx, bx
0x18007970e  jmp     loc_18007A256
0x180079713  mov     rcx, rdi; wchar_t *
0x180079716  call    ClRtlDupString
0x18007971b  mov     r12, rax
0x18007971e  lea     r8, [rbp+120h+phDS]; phDS
0x180079722  xor     edx, edx; DnsDomainName
0x180079724  mov     rcx, rax; DomainControllerName
0x180079727  call    cs:__imp_DsBindW
0x18007972d  mov     ebx, eax
0x18007972f  test    eax, eax
0x180079731  jnz     loc_18007A256
0x180079737  lea     rax, [rsp+220h+pszAccount]
0x18007973c  mov     [rsp+220h+parm_err], rax
0x180079741  lea     r9, [rsp+220h+var_1B0]
0x180079746  mov     r8, r12
0x180079749  mov     rdx, r13
0x18007974c  mov     rcx, rsi
0x18007974f  call    ClRtlIsComputerObjectInDS
0x180079754  mov     r14d, eax
0x180079757  xor     edx, edx
0x180079759  test    eax, eax
0x18007975b  jns     short loc_1800797CB
0x18007975d  lea     rdi, base
0x180079764  mov     rcx, rdi
0x180079767  test    r12, r12
0x18007976a  cmovnz  rcx, r12
0x18007976e  test    rsi, rsi
0x180079771  cmovz   rsi, rdi
0x180079775  mov     dword ptr [rsp+220h+var_1E8], edx
0x180079779  mov     qword ptr [rsp+220h+var_1F0], rcx
0x18007977e  mov     qword ptr [rsp+220h+var_1F8], rsi
0x180079783  lea     rax, aFailedToCheckW; "Failed to check whether the computer ob"...
0x18007978a  mov     [rsp+220h+parm_err], rax
0x18007978f  mov     r9d, 0FEh
0x180079795  lea     r8, aCchlpcreateclu_1; "CCHlpCreateClusterNameCOIfNotExists"
0x18007979c  lea     ecx, [rbx+2]
0x18007979f  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800797a4  mov     eax, r14d
0x1800797a7  and     eax, 1FFF0000h
0x1800797ac  mov     r15, [rsp+220h+var_1D0]
0x1800797b1  cmp     eax, 70000h
0x1800797b6  jnz     short loc_1800797C6
0x1800797b8  movzx   ebx, r14w
0x1800797bc  mov     r14, [rsp+220h+pszAccount]
0x1800797c1  jmp     loc_18007A256
0x1800797c6  mov     ebx, r14d
0x1800797c9  jmp     short loc_1800797BC
0x1800797cb  cmp     [rsp+220h+var_1B0], edx
0x1800797cf  jz      loc_180079A31
0x1800797d5  lea     r8, [rsp+220h+var_1A8]
0x1800797da  lea     rdx, [rbp+120h+hMem]
0x1800797de  mov     r14, [rsp+220h+pszAccount]
0x1800797e3  mov     rcx, r14
0x1800797e6  call    ClRtlParseDistinguishedName
0x1800797eb  mov     ebx, eax
0x1800797ed  lea     rdi, base
0x1800797f4  test    eax, eax
0x1800797f6  jz      short loc_180079832
0x1800797f8  test    r14, r14
0x1800797fb  cmovnz  rdi, r14
0x1800797ff  mov     [rsp+220h+var_1F0], eax
0x180079803  mov     qword ptr [rsp+220h+var_1F8], rdi
0x180079808  lea     rax, aFailedToParseD_0; "Failed to parse distinguished name for "...
0x18007980f  mov     r9d, 10Ch
0x180079815  lea     r8, aCchlpcreateclu_1; "CCHlpCreateClusterNameCOIfNotExists"
0x18007981c  mov     ecx, 2
0x180079821  mov     [rsp+220h+parm_err], rax
0x180079826  xor     edx, edx
0x180079828  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18007982d  jmp     loc_18007A251
0x180079832  lea     rsi, aCchlpcreateclu_1; "CCHlpCreateClusterNameCOIfNotExists"
0x180079839  mov     r15d, 2
0x18007983f  mov     rax, [rsp+220h+var_1C0]
0x180079844  test    rax, rax
0x180079847  jz      loc_1800798D2
0x18007984d  mov     rdx, rax
0x180079850  mov     rcx, [rsp+220h+var_1A8]
0x180079855  call    cs:__imp__o__wcsicmp
0x18007985b  test    eax, eax
0x18007985d  jz      short loc_1800798D2
0x18007985f  mov     rax, rdi
0x180079862  mov     rcx, [rsp+220h+var_1A8]
0x180079867  test    rcx, rcx
0x18007986a  cmovnz  rax, rcx
0x18007986e  mov     qword ptr [rsp+220h+var_1F0], rax
0x180079873  mov     rax, [rsp+220h+var_1C0]
0x180079878  mov     qword ptr [rsp+220h+var_1F8], rax
0x18007987d  lea     rax, aInputOuWsDidNo; "Input OU %ws did not match OU %ws where"...
0x180079884  mov     [rsp+220h+parm_err], rax
0x180079889  mov     r9d, 117h
0x18007988f  mov     r8, rsi
0x180079892  xor     edx, edx
0x180079894  mov     ecx, r15d
0x180079897  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18007989c  lea     ebx, [r15+55h]
0x1800798a0  movups  xmm0, cs:CLUSAPI_CREATE_MISMATCHED_OU
0x1800798a7  movdqu  [rbp+120h+var_100], xmm0
0x1800798ac  mov     rax, [rsp+220h+var_1A8]
0x1800798b1  mov     [rsp+220h+var_1E0], rax
0x1800798b6  mov     rax, [rsp+220h+var_1C0]
0x1800798bb  mov     [rsp+220h+var_1E8], rax
0x1800798c0  mov     rax, [rbp+120h+hMem]
0x1800798c4  mov     qword ptr [rsp+220h+var_1F0], rax
0x1800798c9  lea     r9, [rbp+120h+var_100]
0x1800798cd  call    ClusterLogEvent3
0x1800798d2  mov     rax, rdi
0x1800798d5  mov     rcx, [rsp+220h+var_1A8]
0x1800798da  test    rcx, rcx
0x1800798dd  cmovnz  rax, rcx
0x1800798e1  mov     qword ptr [rsp+220h+var_1F8], rax
0x1800798e6  lea     rax, aTheOuUsedForTh; "The OU used for the CNO is %ws"
0x1800798ed  mov     [rsp+220h+parm_err], rax
0x1800798f2  mov     r9d, 129h
0x1800798f8  mov     r8, rsi
0x1800798fb  xor     edx, edx
0x1800798fd  lea     ecx, [rdx+4]
0x180079900  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180079905  test    ebx, ebx
0x180079907  jnz     loc_18007A251
0x18007990d  lea     r8, [rsp+220h+var_1B4]
0x180079912  mov     rdx, r12
0x180079915  mov     rcx, r14
0x180079918  call    ClRtlGetObjectFlags
0x18007991d  xor     ecx, ecx
0x18007991f  test    eax, eax
0x180079921  jnz     loc_1800799B3
0x180079927  mov     eax, [rsp+220h+var_1B4]
0x18007992b  test    r15b, al
0x18007992e  jz      loc_1800799FA
0x180079934  cmp     [rbp+120h+arg_40], ecx
0x18007993a  jz      short loc_180079971
0x18007993c  mov     ebx, 52Fh
0x180079941  test    r12, r12
0x180079944  cmovnz  rdi, r12
0x180079948  mov     qword ptr [rsp+220h+var_1F0], rdi
0x18007994d  lea     rax, [rbp+120h+username]
0x180079954  mov     qword ptr [rsp+220h+var_1F8], rax
0x180079959  lea     rax, aTheAdEnvironme_1; "The AD environment is Read-Only. But th"...
0x180079960  mov     r9d, 13Ch
0x180079966  mov     r8, rsi
0x180079969  mov     ecx, r15d
0x18007996c  jmp     loc_180079821
0x180079971  and     eax, 0FFFFFFFDh
0x180079974  mov     dword ptr [rbp+120h+buf], eax
0x180079977  lea     rax, [rbp+120h+var_170]
0x18007997b  mov     [rsp+220h+parm_err], rax; parm_err
0x180079980  lea     r9, [rbp+120h+buf]; buf
0x180079984  mov     r8d, 3F0h; level
0x18007998a  lea     rdx, [rbp+120h+username]; username
0x180079991  mov     rcx, r12; servername
0x180079994  call    cs:__imp_NetUserSetInfo
0x18007999a  mov     ebx, eax
0x18007999c  mov     rax, [rbp+120h+var_110]
0x1800799a0  test    rax, rax
0x1800799a3  jz      short loc_1800799AB
0x1800799a5  mov     dword ptr [rax], 1
0x1800799ab  test    ebx, ebx
0x1800799ad  jnz     loc_18007A251
0x1800799b3  mov     r8, [rbp+120h+var_120]; PCWSTR
0x1800799b7  mov     rdx, r12; lpServer
0x1800799ba  lea     rcx, [rbp+120h+username]; PCWSTR
0x1800799c1  call    ClRtlKerbSetPassword
0x1800799c6  mov     ebx, eax
0x1800799c8  test    eax, eax
0x1800799ca  jz      loc_180079DED
0x1800799d0  test    r12, r12
0x1800799d3  cmovnz  rdi, r12
0x1800799d7  mov     qword ptr [rsp+220h+var_1F0], rdi
0x1800799dc  lea     rax, [rbp+120h+username]
0x1800799e3  mov     qword ptr [rsp+220h+var_1F8], rax
0x1800799e8  lea     rax, aUnableToSetPas; "Unable to set password on <%ws>, DC is "...
0x1800799ef  mov     r9d, 166h
0x1800799f5  jmp     loc_180079966
0x1800799fa  cmp     [rbp+120h+arg_38], ecx
0x180079a00  jz      short loc_1800799B3
0x180079a02  cmp     [rbp+120h+arg_40], ecx
0x180079a08  jnz     short loc_1800799B3
0x180079a0a  mov     ebx, 1730h
0x180079a0f  test    r13, r13
0x180079a12  cmovz   r13, rdi
0x180079a16  mov     [rsp+220h+var_1F0], ebx
0x180079a1a  mov     qword ptr [rsp+220h+var_1F8], r13
0x180079a1f  lea     rax, aComputerObject_0; "Computer object %ws is already in use. "...
0x180079a26  mov     r9d, 154h
0x180079a2c  jmp     loc_180079966
0x180079a31  lea     rdi, base
0x180079a38  cmp     [rbp+120h+arg_40], edx
0x180079a3e  jz      short loc_180079A8A
0x180079a40  mov     ebx, 10D8h
0x180079a45  test    r12, r12
0x180079a48  cmovnz  rdi, r12
0x180079a4c  mov     qword ptr [rsp+220h+var_1F0], rdi
0x180079a51  lea     rax, [rbp+120h+username]
0x180079a58  mov     qword ptr [rsp+220h+var_1F8], rax
0x180079a5d  lea     rax, aTheAdEnvironme_0; "The AD environment is Read-Only. But th"...
0x180079a64  mov     [rsp+220h+parm_err], rax
0x180079a69  mov     r9d, 172h
0x180079a6f  lea     r8, aCchlpcreateclu_1; "CCHlpCreateClusterNameCOIfNotExists"
0x180079a76  mov     ecx, 2
0x180079a7b  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180079a80  mov     r14, [rsp+220h+pszAccount]
0x180079a85  jmp     loc_18007A251
0x180079a8a  lea     rsi, aCchlpcreateclu_1; "CCHlpCreateClusterNameCOIfNotExists"
0x180079a91  mov     r15d, 2
0x180079a97  mov     r14, [rbp+120h+var_130]
0x180079a9b  mov     rax, [rsp+220h+var_1C0]
0x180079aa0  test    r14, r14
0x180079aa3  jz      loc_180079CA5
0x180079aa9  test    rax, rax
0x180079aac  jnz     loc_180079CA5
0x180079ab2  mov     [rsp+220h+var_1B4], edx
0x180079ab6  mov     rdx, r14
0x180079ab9  lea     rcx, [rbp+120h+var_D0]
0x180079abd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180079ac2  nop
0x180079ac3  lea     rdx, S; "."
0x180079aca  lea     rcx, [rbp+120h+var_D0]
0x180079ace  call    ?find@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_KQEB_W_K@Z; std::wstring::find(wchar_t const * const,unsigned __int64)
0x180079ad3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180079ad7  jz      short loc_180079AFE
0x180079ad9  mov     r9, rax
0x180079adc  lea     rdx, [rbp+120h+var_B0]
0x180079ae0  lea     rcx, [rbp+120h+var_D0]
0x180079ae4  call    ?substr@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180079ae9  mov     rdx, rax
  ... truncated ...
```
