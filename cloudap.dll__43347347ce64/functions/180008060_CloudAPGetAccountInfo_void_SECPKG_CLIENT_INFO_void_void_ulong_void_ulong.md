# CloudAPGetAccountInfo(void * *,_SECPKG_CLIENT_INFO *,void *,void *,ulong,void * *,ulong *)

- ea: `0x180008060`
- end: `0x1800094d9`
- name: `?CloudAPGetAccountInfo@@YAJPEAPEAXPEAU_SECPKG_CLIENT_INFO@@PEAX2K0PEAK@Z`
- size: `5241`
- prototype: `__int64 __fastcall(void **, struct _SECPKG_CLIENT_INFO *, char *, void *, unsigned int, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800046f4`
- `0x180006cb0`
- `0x180007fc0`
- `0x180008060`
- `0x18000a600`
- `0x18000a8f0`
- `0x18000ac40`
- `0x18000b9b0`
- `0x18002ea68`
- `0x18004cf50`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000867a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000867a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000823c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000823c`
- `ntdll!RtlReleaseResource` at `0x180008584`
- `ntdll!RtlReleaseResource` at `0x180008595`
- `ntdll!RtlReleaseResource` at `0x18000873f`
- `ntdll!RtlReleaseResource` at `0x180008ee7`
- `ntdll!RtlReleaseResource` at `0x180008584`
- `ntdll!RtlReleaseResource` at `0x180008595`
- `ntdll!RtlReleaseResource` at `0x18000873f`
- `ntdll!RtlReleaseResource` at `0x180008ee7`
- `ntdll!RtlCopySid` at `0x180008473`
- `ntdll!RtlCopySid` at `0x180008473`
- `ntdll!RtlValidSid` at `0x18000810f`
- `ntdll!RtlValidSid` at `0x18000810f`
- `ntdll!RtlInitUnicodeString` at `0x1800082a8`
- `ntdll!RtlInitUnicodeString` at `0x1800082e8`
- `ntdll!RtlInitUnicodeString` at `0x18000833d`
- `ntdll!RtlInitUnicodeString` at `0x18000837c`
- `ntdll!RtlInitUnicodeString` at `0x1800082a8`
- `ntdll!RtlInitUnicodeString` at `0x1800082e8`
- `ntdll!RtlInitUnicodeString` at `0x18000833d`
- `ntdll!RtlInitUnicodeString` at `0x18000837c`
- `ntdll!RtlAcquireResourceShared` at `0x180008126`
- `ntdll!RtlAcquireResourceShared` at `0x180008e78`
- `ntdll!RtlAcquireResourceShared` at `0x180008126`
- `ntdll!RtlAcquireResourceShared` at `0x180008e78`

## string_xrefs

- `0x180008214`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x1800088cf`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180008326`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000852b`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800086e1`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180008745`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000887b`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800089c5`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180008ace`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180008be7`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180008ca4`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180008ef0`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180008f53`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180008fa0`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180008ffc`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180009051`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000909b`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180009149`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800091be`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000920d`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000934c`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000938e`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000940f`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180009454`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x1800084cf`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180008961`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180008a6a`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180008b8b`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180008cfd`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180008d3b`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180008d79`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180008db7`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180008706`: `SpFindMappedSid`
- `0x1800088aa`: `FindUserInCacheBySid`
- `0x180009171`: `RtlCopySid`
- `0x1800092e2`: `RegOpenKeyExW`
- `0x180009333`: `RegOpenKeyExW`
- `0x18000946f`: `CopyToClientBuffer`
- `0x1800091de`: `Invalid Sid`
- `0x18000928d`: `GetUserSid2NameSubKey`

## pseudocode

```c
__int64 __fastcall CloudAPGetAccountInfo(
        void **a1,
        struct _SECPKG_CLIENT_INFO *a2,
        char *a3,
        void *a4,
        unsigned int a5,
        void **a6,
        unsigned int *a7)
{
  void **v8; // rsi
  bool v9; // cf
  LPCWSTR v10; // r14
  WCHAR *v11; // r13
  PCWSTR v12; // rdi
  char *v13; // rsi
  unsigned int i; // edx
  __int64 v15; // rax
  char *v16; // r15
  __int64 v17; // rax
  PCWSTR v18; // r12
  unsigned int MappedSid; // ebx
  HKEY ParentValue; // r14
  unsigned int UserSid2NameSubKey; // eax
  LPCWSTR v22; // rdi
  unsigned int RegVal; // eax
  const char *v24; // rdi
  unsigned int v25; // eax
  int v26; // r15d
  unsigned int v27; // eax
  PCWSTR v28; // r14
  unsigned int v29; // ebx
  unsigned int v30; // r12d
  WCHAR *v31; // r14
  signed __int64 v32; // r15
  __int64 v33; // rsi
  __int64 v34; // rax
  unsigned __int64 v35; // rcx
  const char *v36; // r9
  char v37; // cl
  const char *v38; // r10
  int v39; // eax
  const char *v40; // rcx
  const char *v41; // r9
  const char *v43; // rdi
  char v44; // al
  const char *v45; // rcx
  bool v46; // zf
  const char *v47; // r9
  const UCHAR *v48; // r9
  char v49; // al
  const UCHAR *v50; // rcx
  bool v51; // zf
  const char *v52; // r9
  char v53; // cl
  const char *v54; // rdx
  bool v55; // zf
  const UCHAR *v56; // r9
  const char *v57; // rdi
  char v58; // al
  const char *v59; // rcx
  bool v60; // zf
  char v61; // al
  const UCHAR *v62; // rcx
  bool v63; // zf
  __int64 v64; // rbx
  __int64 v65; // rax
  WCHAR v66; // cx
  char *v67; // r14
  __int64 v68; // rax
  unsigned __int64 v69; // rcx
  const char *v70; // r9
  char v71; // cl
  const char *v72; // r10
  int v73; // eax
  const char *v74; // rcx
  char v75; // al
  const char *v76; // rcx
  bool v77; // zf
  __int64 v78; // rbx
  __int64 v79; // rax
  WCHAR v80; // cx
  char *v81; // r14
  __int64 v82; // rax
  unsigned __int64 v83; // rcx
  const char *v84; // r9
  char v85; // cl
  const char *v86; // r10
  int v87; // eax
  const char *v88; // rcx
  char v89; // al
  __int64 v90; // rbx
  int v91; // ecx
  WCHAR v92; // ax
  unsigned __int64 v93; // rax
  const char *v94; // r9
  char v95; // cl
  const char *v96; // r10
  int v97; // eax
  const char *v98; // rcx
  const char *v99; // r9
  char *v100; // rbx
  __int64 v101; // rdi
  WCHAR v102; // ax
  void **v103; // rcx
  const char *v104; // rdi
  char v105; // al
  const char *v106; // rcx
  bool v107; // zf
  char v108; // cl
  const char *v109; // r8
  char v110; // cl
  const char *v111; // r8
  char v112; // cl
  const char *v113; // r8
  char v114; // cl
  const char *v115; // r8
  WCHAR *v116; // rdi
  struct _RTL_BALANCED_NODE *v117; // rbx
  int v118; // eax
  struct _RTL_BALANCED_NODE *v119; // rbx
  int v120; // eax
  struct _RTL_RESOURCE *v121; // rcx
  const char *v122; // rax
  __int64 v123; // r8
  char v124; // al
  const char *v125; // rdi
  char v126; // al
  const char *v127; // rcx
  bool v128; // zf
  char v129; // al
  char v130; // al
  const char *v131; // rdi
  char v132; // al
  const char *v133; // rcx
  bool v134; // zf
  const char *v135; // r9
  char v136; // cl
  const char *v137; // rdx
  bool v138; // zf
  char v139; // al
  const char *v140; // r9
  const char *v141; // rax
  const char *v142; // r9
  const char *v143; // rax
  __int64 v144; // r8
  const char *v145; // rax
  __int64 v146; // r8
  const char *v147; // rax
  __int64 v148; // r8
  const char *v149; // rax
  __int64 v150; // r8
  const char *v151; // rax
  int v152; // r9d
  const char *v153; // rax
  const char *v154; // r9
  PHKEY phkResult; // [rsp+28h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+28h] [rbp-E0h]
  PHKEY phkResultb; // [rsp+28h] [rbp-E0h]
  PHKEY phkResultc; // [rsp+28h] [rbp-E0h]
  PHKEY phkResultd; // [rsp+28h] [rbp-E0h]
  PHKEY phkResulte; // [rsp+28h] [rbp-E0h]
  PHKEY phkResultf; // [rsp+28h] [rbp-E0h]
  PHKEY phkResulth; // [rsp+28h] [rbp-E0h]
  PHKEY phkResulti; // [rsp+28h] [rbp-E0h]
  PHKEY phkResultg; // [rsp+28h] [rbp-E0h]
  const char *v165; // [rsp+30h] [rbp-D8h]
  const char *v166; // [rsp+30h] [rbp-D8h]
  const WCHAR *v167; // [rsp+38h] [rbp-D0h]
  PCWSTR j; // [rsp+48h] [rbp-C0h] BYREF
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-B8h] BYREF
  char *v170; // [rsp+58h] [rbp-B0h]
  HKEY hKey; // [rsp+60h] [rbp-A8h] BYREF
  PCWSTR v172; // [rsp+68h] [rbp-A0h]
  _BYTE *v173; // [rsp+70h] [rbp-98h] BYREF
  PCWSTR v174; // [rsp+78h] [rbp-90h] BYREF
  int v175; // [rsp+80h] [rbp-88h] BYREF
  LPCWSTR v176; // [rsp+88h] [rbp-80h]
  PSID SourceSid; // [rsp+90h] [rbp-78h] BYREF
  PCWSTR SourceString; // [rsp+98h] [rbp-70h] BYREF
  PCWSTR v179; // [rsp+A0h] [rbp-68h] BYREF
  PCWSTR v180; // [rsp+A8h] [rbp-60h] BYREF
  struct _UNICODE_STRING v181; // [rsp+B0h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-48h] BYREF
  struct _UNICODE_STRING v183; // [rsp+D0h] [rbp-38h] BYREF
  struct _UNICODE_STRING v184; // [rsp+E0h] [rbp-28h] BYREF

  v8 = a1;
  v9 = a5 < 0x58;
  v10 = 0;
  v11 = 0;
  v176 = 0;
  v12 = 0;
  lpSubKey = 0;
  DestinationString = 0;
  *a6 = 0;
  v183 = 0;
  SourceString = 0;
  v181 = 0;
  *a7 = 0;
  v184 = 0;
  v179 = 0;
  v180 = 0;
  v174 = 0;
  hKey = 0;
  v173 = 0;
  v172 = 0;
  j = 0;
  SourceSid = 0;
  v175 = 0;
  if ( v9 || !a3 )
  {
    MappedSid = -1073741811;
    v125 = "";
    while ( 1 )
    {
      v126 = *(v125 - 1);
      v127 = v125--;
      v128 = v126 == 92;
      if ( v126 == 92 )
        break;
      if ( v125 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
      {
        v128 = v126 == 92;
        break;
      }
    }
    if ( v128 )
      v125 = v127;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v125, 4280, "Invalid Arg(s)", &Class);
    v12 = 0;
  }
  else
  {
    v13 = a3 + 20;
    if ( RtlValidSid(a3 + 20) )
    {
      RtlAcquireResourceShared(&g_PackageListLock, 1u);
      if ( g_pPlugins )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= g_cPlugins )
            goto LABEL_83;
          v15 = *(_QWORD *)(a3 + 4);
          v16 = (char *)g_pPlugins + 392 * i;
          v170 = v16;
          v17 = v15 - *(_QWORD *)(v16 + 68);
          if ( !v17 )
            v17 = *(_QWORD *)(a3 + 12) - *(_QWORD *)(v16 + 76);
          if ( !v17 )
            break;
        }
        v18 = &Class;
        if ( (v16[160] & 1) != 0 )
        {
          MappedSid = (*((__int64 (__fastcall **)(_QWORD, _QWORD, char *, __int64, PSID *, int *))g_pLsaIdProvHostFunctionTable
                       + 4))(
                        *((_QWORD *)v16 + 2),
                        0,
                        v13,
                        2,
                        &SourceSid,
                        &v175);
          if ( !MappedSid )
          {
            v13 = (char *)SourceSid;
            j = 0;
            goto LABEL_13;
          }
          v104 = "";
          while ( 1 )
          {
            v105 = *(v104 - 1);
            v106 = v104--;
            v107 = v105 == 92;
            if ( v105 == 92 )
              break;
            if ( v104 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
            {
              v107 = v105 == 92;
              break;
            }
          }
          v167 = &Class;
          v166 = "LookUpUserInfo";
          LODWORD(phkResult) = 4308;
        }
        else
        {
          MappedSid = SpFindMappedSid(*((void **)v16 + 2), v13, (void **)&lpSubKey);
          if ( (int)(MappedSid + 0x80000000) >= 0 && MappedSid != -1073741724 )
          {
            v43 = "";
            while ( 1 )
            {
              v44 = *(v43 - 1);
              v45 = v43--;
              v46 = v44 == 92;
              if ( v44 == 92 )
                break;
              if ( v43 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
              {
                v46 = v44 == 92;
                break;
              }
            }
            if ( v46 )
              v43 = v45;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", MappedSid, v43, 4321, "SpFindMappedSid", &Class);
            v10 = lpSubKey;
            goto LABEL_52;
          }
          v10 = lpSubKey;
          v176 = lpSubKey;
          if ( lpSubKey )
            v13 = (char *)lpSubKey;
          MappedSid = GetAuthenticatingAuthority((struct _ApPluginPkg *)v16, 0, v13, (unsigned __int16 **)&j);
          if ( !MappedSid )
          {
            v116 = (WCHAR *)j;
            v172 = j;
            if ( !j )
            {
              MappedSid = DuplicateString((const unsigned __int16 *)v16 + 12, 0, (unsigned __int16 **)&j);
              if ( MappedSid )
              {
                v141 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", MappedSid, v141, 4339, "DuplicateString", &Class);
                v172 = j;
LABEL_52:
                RtlReleaseResource(&g_PackageListLock);
                v12 = v172;
                v8 = a1;
                goto LABEL_53;
              }
              v116 = (WCHAR *)j;
              v172 = j;
            }
            RtlAcquireResourceShared(*((PRTL_RESOURCE *)v16 + 45), 1u);
            if ( v116 )
            {
              v117 = (struct _RTL_BALANCED_NODE *)*((_QWORD *)v16 + 47);
              for ( j = (PCWSTR)v117; v117; j = (PCWSTR)v117 )
              {
                v118 = SubPkgTable_CompareNames(v116, v117);
                if ( v118 >= 0 )
                {
                  if ( v118 <= 0 )
                  {
LABEL_254:
                    ParentValue = (HKEY)v117[24].ParentValue;
                    goto LABEL_14;
                  }
                  v117 = v117->Children[1];
                }
                else
                {
                  v117 = v117->Children[0];
                }
              }
              v119 = (struct _RTL_BALANCED_NODE *)*((_QWORD *)v16 + 48);
              while ( v119 )
              {
                v120 = SubPkgTable_CompareDnsNames(v116, v119);
                if ( v120 >= 0 )
                {
                  if ( v120 <= 0 )
                  {
                    v117 = v119 - 1;
                    j = (PCWSTR)v117;
                    goto LABEL_254;
                  }
                  v119 = v119->Children[1];
                }
                else
                {
                  v119 = v119->Children[0];
                }
              }
            }
            v121 = (struct _RTL_RESOURCE *)*((_QWORD *)v16 + 45);
            j = 0;
            RtlReleaseResource(v121);
            v122 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 2148074257LL, v122, 4344, "RefSubPackage", v123);
LABEL_13:
            ParentValue = (HKEY)*((_QWORD *)v16 + 44);
LABEL_14:
            lpSubKey = 0;
            hKey = 0;
            if ( ParentValue && v13 )
            {
              UserSid2NameSubKey = GetUserSid2NameSubKey(v13, (unsigned __int16 **)&lpSubKey);
              v22 = lpSubKey;
              MappedSid = UserSid2NameSubKey;
              if ( UserSid2NameSubKey )
              {
                v142 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
                LODWORD(phkResult) = 1463;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", MappedSid, v142, phkResult, "GetUserSid2NameSubKey", &Class);
              }
              else
              {
                MappedSid = RegOpenKeyExW(ParentValue, lpSubKey, 0, 0x20019u, &hKey);
                if ( MappedSid )
                {
                  v143 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
                  LODWORD(phkResulta) = 1473;
                  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", MappedSid, v143, phkResulta, "RegOpenKeyExW", v144);
                  if ( MappedSid - 2 <= 1 )
                  {
                    MappedSid = -1073741275;
                  }
                  else if ( (int)MappedSid > 0 )
                  {
                    MappedSid = (unsigned __int16)MappedSid | 0xC0070000;
                  }
                  v145 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
                  LODWORD(phkResultg) = 1483;
                  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", MappedSid, v145, phkResultg, "RegOpenKeyExW", v146);
                }
              }
              if ( v22 )
                ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v22);
              if ( !MappedSid )
              {
                a5 = 0;
                if ( (unsigned int)GetRegVal(hKey, L"AuthenticatingAuthority", 6u, &a5, (void **)&SourceString) )
                {
                  v147 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                  LODWORD(phkResultb) = 4366;
                  WPPTraceLogA(
                    0,
                    "0x%08x %s:%u : %s:%ws",
                    v148,
                    v147,
                    phkResultb,
                    "GetStringRegVal(AuthorityName)",
                    &Class);
                }
                RtlInitUnicodeString(&DestinationString, SourceString);
                a5 = 0;
                if ( (unsigned int)GetRegVal(hKey, L"IdentityName", 6u, &a5, (void **)&v179) )
                {
                  v149 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                  LODWORD(phkResultc) = 4373;
                  WPPTraceLogA(
                    0,
                    "0x%08x %s:%u : %s:%ws",
                    v150,
                    v149,
                    phkResultc,
                    "GetStringRegVal(IdentityName)",
                    &Class);
                }
                RtlInitUnicodeString(&v181, v179);
                if ( !v181.Length )
                {
                  MappedSid = -1073741724;
                  v131 = "";
                  while ( 1 )
                  {
                    v132 = *(v131 - 1);
                    v133 = v131--;
                    v134 = v132 == 92;
                    if ( v132 == 92 )
                      break;
                    if ( v131 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
                    {
                      v134 = v132 == 92;
                      break;
                    }
                  }
                  if ( v134 )
                    v131 = v133;
                  LODWORD(phkResultc) = 4378;
                  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225572LL, v131, phkResultc, "Empty strUPNName", &Class);
                  goto LABEL_49;
                }
                a5 = 0;
                RegVal = GetRegVal(hKey, L"DisplayName", 6u, &a5, (void **)&v180);
                v24 = "";
                if ( RegVal )
                {
                  v135 = "";
                  while ( 1 )
                  {
                    v136 = *(v135 - 1);
                    v137 = v135--;
                    v138 = v136 == 92;
                    if ( v136 == 92 )
                      break;
                    if ( v135 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
                    {
                      v138 = v136 == 92;
                      break;
                    }
                  }
                  if ( v138 )
                    v135 = v137;
                  LODWORD(phkResultd) = 4385;
                  WPPTraceLogA(
                    0,
                    "0x%08x %s:%u : %s:%ws",
                    RegVal,
                    v135,
                    phkResultd,
                    "GetStringRegVal(DisplayName)",
                    &Class);
                }
                RtlInitUnicodeString(&v183, v180);
                a5 = 0;
                v25 = GetRegVal(hKey, L"SAMName", 6u, &a5, (void **)&v174);
                if ( v25 )
                {
                  v52 = "";
                  while ( 1 )
                  {
                    v53 = *(v52 - 1);
                    v54 = v52--;
                    v55 = v53 == 92;
                    if ( v53 == 92 )
                      break;
                    if ( v52 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
                    {
                      v55 = v53 == 92;
                      break;
                    }
                  }
                  if ( v55 )
                    v52 = v54;
                  LODWORD(phkResulte) = 4392;
                  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v25, v52, phkResulte, "GetStringRegVal(SamName)", &Class);
                }
                RtlInitUnicodeString(&v184, v174);
                a5 = 0;
                v174 = 0;
                v26 = 0;
                v27 = GetRegVal(hKey, L"Flags", 0x10u, &a5, (void **)&v174);
                v28 = v174;
                v29 = v27;
                if ( v27 )
                {
                  v48 = "";
                  while ( 1 )
                  {
                    v49 = *(v48 - 1);
                    v50 = v48--;
                    v51 = v49 == 92;
                    if ( v49 == 92 )
                      break;
                    if ( v48 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
                    {
                      v51 = v49 == 92;
                      break;
                    }
                  }
                  if ( v51 )
                    v48 = v50;
                  LODWORD(phkResultf) = 474;
                  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v29, v48, phkResultf, "GetRegVal", &Class);
                }
                else if ( a5 == 4 )
                {
                  v26 = *(_DWORD *)v174;
                }
                else
                {
                  v29 = -1073741275;
                  v151 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
                  WPPTraceLogA(0, "0x%08x %s:%u : %s:%u", -1073741275, v151, 479, "Bad DWORD size", v152);
                }
                if ( v28 )
                  ((void (__fastcall *)(PCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v28);
                if ( v29 )
                {
                  v153 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                  LODWORD(phkResultf) = 4399;
                  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v29, v153, phkResultf, "GetDWordRegVal(Flags)", &Class);
                }
                v30 = v181.MaximumLength
                    + v183.MaximumLength
                    + v184.MaximumLength
                    + DestinationString.MaximumLength
                    + 144;
                lpSubKey = (LPCWSTR)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(v30);
                v11 = (WCHAR *)lpSubKey;
                if ( !lpSubKey )
                {
                  MappedSid = -1073741801;
                  while ( 1 )
                  {
                    v124 = *(v24 - 1);
                    v76 = v24--;
                    v77 = v124 == 92;
                    if ( v124 == 92 )
                      break;
                    if ( v24 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
                    {
                      v77 = v124 == 92;
                      break;
                    }
                  }
                  v165 = "AllocateLsaHeap";
                  LODWORD(phkResultf) = 4411;
                  goto LABEL_145;
                }
                MappedSid = ((__int64 (__fastcall *)(void **, _QWORD, _BYTE **))g_pLsaFunctionTable->AllocateClientBuffer)(
                              a1,
                              v30,
                              &v173);
                if ( MappedSid )
                {
                  while ( 1 )
                  {
                    v129 = *(v24 - 1);
                    v76 = v24--;
                    v77 = v129 == 92;
                    if ( v129 == 92 )
                      break;
                    if ( v24 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
                    {
                      v77 = v129 == 92;
                      break;
                    }
                  }
                  v165 = "AllocateClientBuffer";
                  LODWORD(phkResultf) = 4418;
                  goto LABEL_145;
                }
                *(_DWORD *)v11 = 3;
                *((_DWORD *)v11 + 18) = v26;
                MappedSid = RtlCopySid(0x44u, v11 + 38, v13);
                if ( MappedSid )
                {
                  while ( 1 )
                  {
                    v139 = *(v24 - 1);
                    v76 = v24--;
                    v77 = v139 == 92;
                    if ( v139 == 92 )
                      break;
                    if ( v24 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
                    {
                      v77 = v139 == 92;
                      break;
                    }
                  }
                  v165 = "RtlCopySid";
                  LODWORD(phkResultf) = 4425;
                  goto LABEL_145;
                }
                v31 = v11 + 72;
                v32 = v173 - (_BYTE *)v11;
                v33 = -1;
                if ( DestinationString.Buffer )
                {
                  v34 = -1;
                  do
                    ++v34;
                  while ( DestinationString.Buffer[v34] );
                  v35 = 2LL * (unsigned int)v34;
                  if ( v35 > 0xFFFFFFFF )
                  {
                    v36 = "";
                    do
                    {
                      v37 = *(v36 - 1);
                      v38 = v36--;
                    }
                    while ( v37 != 92 && v36 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
                    v39 = 4939;
                    v46 = v37 == 92;
                    v40 = "RtlDWordMult";
                    if ( v46 )
                      v36 = v38;
LABEL_47:
                    LODWORD(phkResultf) = v39;
                    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v36, phkResultf, v40, &Class);
                    MappedSid = -1073741675;
                    v41 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                    LODWORD(phkResulth) = 4437;
                    WPPTraceLogA(
                      0,
                      "0x%08x %s:%u : %s:%ws",
                      3221225621LL,
                      v41,
                      phkResulth,
                      "PutClientString(AuthorityName)",
                      &Class);
LABEL_48:
                    v16 = v170;
LABEL_49:
                    if ( j )
                      RtlReleaseResource(*((PRTL_RESOURCE *)v16 + 45));
                    v10 = v176;
                    goto LABEL_52;
                  }
                  v64 = (unsigned int)v35;
                  memcpy_0(v11 + 72, DestinationString.Buffer, (unsigned int)v35);
                  v11[4] = v64;
                  *((_QWORD *)v11 + 2) = (char *)v31 + v32;
                  *(WCHAR *)((char *)v31 + v64) = 0;
                  v65 = (unsigned int)(v64 + 2);
                  if ( (unsigned int)v65 < (unsigned int)v64 )
                  {
                    v36 = "";
                    do
                    {
                      v110 = *(v36 - 1);
                      v111 = v36--;
                    }
                    while ( v110 != 92 && v36 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
                    v39 = 4949;
                    v46 = v110 == 92;
                    v40 = "RtlDWordAdd";
                    if ( v46 )
                      v36 = v111;
                    goto LABEL_47;
                  }
                  v66 = v64 + 2;
                }
                else
                {
                  v65 = 0;
                  *((_QWORD *)v11 + 2) = 0;
                  v11[4] = 0;
                  v66 = 0;
                }
                v11[5] = v66;
                v67 = (char *)v31 + v65;
                if ( v183.Buffer )
                {
                  v68 = -1;
                  do
                    ++v68;
                  while ( v183.Buffer[v68] );
                  v69 = 2LL * (unsigned int)v68;
                  if ( v69 > 0xFFFFFFFF )
                  {
                    v70 = "";
                    do
                    {
                      v71 = *(v70 - 1);
                      v72 = v70--;
                    }
                    while ( v71 != 92 && v70 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
                    v73 = 4939;
                    v46 = v71 == 92;
                    v74 = "RtlDWordMult";
                    if ( v46 )
                      v70 = v72;
                    goto LABEL_124;
                  }
                  v78 = (unsigned int)v69;
                  memcpy_0(v67, v183.Buffer, (unsigned int)v69);
                  v11[12] = v78;
                  *((_QWORD *)v11 + 4) = &v67[v32];
                  *(_WORD *)&v67[v78] = 0;
                  v79 = (unsigned int)(v78 + 2);
                  if ( (unsigned int)v79 < (unsigned int)v78 )
                  {
                    v70 = "";
                    do
                    {
                      v108 = *(v70 - 1);
                      v109 = v70--;
                    }
                    while ( v108 != 92 && v70 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
                    v73 = 4949;
                    v46 = v108 == 92;
                    v74 = "RtlDWordAdd";
                    if ( v46 )
                      v70 = v109;
LABEL_124:
                    LODWORD(phkResultf) = v73;
                    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v70, phkResultf, v74, &Class);
                    MappedSid = -1073741675;
                    while ( 1 )
                    {
                      v75 = *(v24 - 1);
                      v76 = v24--;
                      v77 = v75 == 92;
                      if ( v75 == 92 )
                        break;
                      if ( v24 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
                      {
                        v77 = v75 == 92;
                        break;
                      }
                    }
                    v165 = "PutClientString(DisplayName)";
                    LODWORD(phkResultf) = 4446;
LABEL_145:
                    if ( v77 )
                      v24 = v76;
                    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", MappedSid, v24, phkResultf, v165, &Class);
                    v11 = (WCHAR *)lpSubKey;
                    goto LABEL_48;
                  }
                  v80 = v78 + 2;
                }
                else
                {
                  v79 = 0;
                  *((_QWORD *)v11 + 4) = 0;
                  v11[12] = 0;
                  v80 = 0;
                }
                v11[13] = v80;
                v81 = &v67[v79];
                if ( v181.Buffer )
                {
                  v82 = -1;
                  do
                    ++v82;
                  while ( v181.Buffer[v82] );
                  v83 = 2LL * (unsigned int)v82;
                  if ( v83 > 0xFFFFFFFF )
                  {
                    v84 = "";
                    do
                    {
                      v85 = *(v84 - 1);
                      v86 = v84--;
                    }
                    while ( v85 != 92 && v84 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
                    v87 = 4939;
                    v46 = v85 == 92;
                    v88 = "RtlDWordMult";
                    if ( v46 )
                      v84 = v86;
                    goto LABEL_140;
                  }
                  v90 = (unsigned int)v83;
                  memcpy_0(v81, v181.Buffer, (unsigned int)v83);
                  v11[20] = v90;
                  *((_QWORD *)v11 + 6) = &v81[v32];
                  v91 = v90 + 2;
                  *(_WORD *)&v81[v90] = 0;
                  if ( (int)v90 + 2 < (unsigned int)v90 )
                  {
                    v84 = "";
                    do
                    {
                      v112 = *(v84 - 1);
                      v113 = v84--;
                    }
                    while ( v112 != 92 && v84 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
                    v87 = 4949;
                    v46 = v112 == 92;
                    v88 = "RtlDWordAdd";
                    if ( v46 )
                      v84 = v113;
LABEL_140:
                    LODWORD(phkResultf) = v87;
                    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v84, phkResultf, v88, &Class);
                    MappedSid = -1073741675;
                    while ( 1 )
                    {
                      v89 = *(v24 - 1);
                      v76 = v24--;
                      v77 = v89 == 92;
                      if ( v89 == 92 )
                        break;
                      if ( v24 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
                      {
                        v77 = v89 == 92;
                        break;
                      }
                    }
                    v165 = "PutClientString(UPNName)";
                    LODWORD(phkResultf) = 4455;
                    goto LABEL_145;
                  }
                  v92 = v90 + 2;
                }
                else
                {
                  v92 = 0;
                  *((_QWORD *)v11 + 6) = 0;
                  v11[20] = 0;
                  v91 = 0;
                }
                v11[21] = v92;
                if ( v184.Buffer )
                {
                  do
                    ++v33;
                  while ( v184.Buffer[v33] );
                  v93 = 2LL * (unsigned int)v33;
                  if ( v93 > 0xFFFFFFFF )
                  {
                    v94 = "";
                    do
                    {
                      v95 = *(v94 - 1);
                      v96 = v94--;
                    }
                    while ( v95 != 92 && v94 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
                    v97 = 4939;
                    v46 = v95 == 92;
                    v98 = "RtlDWordMult";
                    if ( v46 )
                      v94 = v96;
LABEL_158:
                    LODWORD(phkResultf) = v97;
                    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v94, phkResultf, v98, &Class);
                    MappedSid = -1073741675;
                    v99 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                    LODWORD(phkResulti) = 4464;
                    WPPTraceLogA(
                      0,
                      "0x%08x %s:%u : %s:%ws",
                      3221225621LL,
                      v99,
                      phkResulti,
                      "PutClientString(SAMName)",
                      &Class);
                    goto LABEL_48;
                  }
                  v100 = &v81[v91];
                  v101 = (unsigned int)v93;
                  memcpy_0(v100, v184.Buffer, (unsigned int)v93);
                  v11[28] = v101;
                  *((_QWORD *)v11 + 8) = &v100[v32];
                  v102 = v101 + 2;
                  *(_WORD *)&v100[v101] = 0;
                  if ( (int)v101 + 2 < (unsigned int)v101 )
                  {
                    v94 = "";
                    do
                    {
                      v114 = *(v94 - 1);
                      v115 = v94--;
                    }
                    while ( v114 != 92 && v94 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
                    v46 = v114 == 92;
                    v97 = 4949;
                    v98 = "RtlDWordAdd";
                    if ( v46 )
                      v94 = v115;
                    goto LABEL_158;
                  }
                }
                else
                {
                  v102 = 0;
                  *((_QWORD *)v11 + 8) = 0;
                  v11[28] = 0;
                }
                v11[29] = v102;
                MappedSid = ((__int64 (__fastcall *)(void **, _QWORD, _BYTE *, WCHAR *))g_pLsaFunctionTable->CopyToClientBuffer)(
                              a1,
                              v30,
                              v173,
                              v11);
                if ( MappedSid )
                {
                  v154 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                  LODWORD(phkResultf) = 4471;
                  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", MappedSid, v154, phkResultf, "CopyToClientBuffer", &Class);
                }
                else
                {
                  MappedSid = 0;
                  v103 = a6;
                  *a7 = v30;
                  *v103 = v173;
                  v173 = 0;
                }
                goto LABEL_48;
              }
            }
            else
            {
              MappedSid = -1073741811;
              v56 = "";
              while ( 1 )
              {
                v61 = *(v56 - 1);
                v62 = v56--;
                v63 = v61 == 92;
                if ( v61 == 92 )
                  break;
                if ( v56 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
                {
                  v63 = v61 == 92;
                  break;
                }
              }
              if ( v63 )
                v56 = v62;
              LODWORD(phkResult) = 1457;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v56, phkResult, "Invalid Arg(s)", &Class);
            }
            v57 = "";
            while ( 1 )
            {
              v58 = *(v57 - 1);
              v59 = v57--;
              v60 = v58 == 92;
              if ( v58 == 92 )
                break;
              if ( v57 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
              {
                v60 = v58 == 92;
                break;
              }
            }
            if ( v60 )
              v57 = v59;
            LODWORD(phkResulta) = 4360;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", MappedSid, v57, phkResulta, "FindUserInCacheBySid", &Class);
            goto LABEL_48;
          }
          v104 = "";
          v172 = j;
          if ( j )
            v18 = j;
          while ( 1 )
          {
            v130 = *(v104 - 1);
            v106 = v104--;
            v107 = v130 == 92;
            if ( v130 == 92 )
              break;
            if ( v104 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
            {
              v107 = v130 == 92;
              break;
            }
          }
          v167 = v18;
          v166 = "GetAuthenticatingAuthorityForIdentity";
          LODWORD(phkResult) = 4334;
        }
        if ( v107 )
          v104 = v106;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", MappedSid, v104, phkResult, v166, v167);
        goto LABEL_52;
      }
LABEL_83:
      RtlReleaseResource(&g_PackageListLock);
      MappedSid = -2146893039;
      v47 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 2148074257LL, v47, 4296, "RefPackage", &Class);
    }
    else
    {
      MappedSid = -1073741704;
      v140 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225592LL, v140, 4290, "Invalid Sid", &Class);
    }
    v8 = a1;
  }
LABEL_53:
  if ( v173 && v8 )
    ((void (__fastcall *)(void **))g_pLsaFunctionTable->FreeClientBuffer)(v8);
  if ( v12 )
    ((void (__fastcall *)(PCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v12);
  if ( v11 )
    ((void (__fastcall *)(WCHAR *))g_pLsaFunctionTable->FreeLsaHeap)(v11);
  if ( v10 )
    ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v10);
  if ( DestinationString.Buffer )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v183.Buffer )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v181.Buffer )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v184.Buffer )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( hKey )
    RegCloseKey(hKey);
  if ( SourceSid )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  return MappedSid;
}

```

## disassembly

```asm
0x180008060  mov     rax, rsp
0x180008063  mov     [rax+8], rcx
0x180008067  push    rbp
0x180008068  push    rbx
0x180008069  lea     rbp, [rax-18h]
0x18000806d  sub     rsp, 108h
0x180008074  mov     [rax+10h], rsi
0x180008078  xorps   xmm0, xmm0
0x18000807b  mov     [rax+18h], rdi
0x18000807f  xorps   xmm1, xmm1
0x180008082  mov     [rax-18h], r13
0x180008086  mov     rbx, r8
0x180008089  mov     [rax-20h], r14
0x18000808d  mov     rsi, rcx
0x180008090  mov     [rax-28h], r15
0x180008094  xor     r15d, r15d
0x180008097  cmp     [rbp+10h+arg_20], 58h ; 'X'
0x18000809b  mov     r14d, r15d
0x18000809e  mov     rax, [rbp+10h+arg_28]
0x1800080a2  mov     r13d, r15d
0x1800080a5  mov     [rbp+10h+var_90], r15
0x1800080a9  mov     edi, r15d
0x1800080ac  mov     [rsp+110h+lpSubKey], r15
0x1800080b1  movups  xmmword ptr [rbp+10h+DestinationString.Length], xmm0
0x1800080b5  mov     [rax], r15
0x1800080b8  mov     rax, [rbp+10h+arg_30]
0x1800080bc  movups  xmmword ptr [rbp+10h+var_48.Length], xmm1
0x1800080c0  mov     [rbp+10h+SourceString], r15
0x1800080c4  movups  xmmword ptr [rbp+10h+var_68.Length], xmm0
0x1800080c8  mov     [rax], r15d
0x1800080cb  movups  xmmword ptr [rbp+10h+var_38.Length], xmm1
0x1800080cf  mov     [rbp+10h+var_78], r15
0x1800080d3  mov     [rbp+10h+var_70], r15
0x1800080d7  mov     [rsp+110h+var_A0], r15
0x1800080dc  mov     [rsp+110h+hKey], r15
0x1800080e1  mov     [rsp+110h+var_A8], r15
0x1800080e6  mov     [rsp+110h+var_B0], r15
0x1800080eb  mov     [rsp+110h+var_D0], r15
0x1800080f0  mov     [rbp+10h+SourceSid], r15
0x1800080f4  mov     [rsp+110h+var_98], r15d
0x1800080f9  jb      loc_180008F94
0x1800080ff  test    rbx, rbx
0x180008102  jz      loc_180008F94
0x180008108  lea     rsi, [r8+14h]
0x18000810c  mov     rcx, rsi; Sid
0x18000810f  call    cs:__imp_RtlValidSid
0x180008115  test    al, al
0x180008117  jz      loc_1800091BE
0x18000811d  mov     dl, 1; Wait
0x18000811f  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x180008126  call    cs:__imp_RtlAcquireResourceShared
0x18000812c  mov     r8, cs:?g_pPlugins@@3PEAU_ApPluginPkg@@EA; _ApPluginPkg * g_pPlugins
0x180008133  test    r8, r8
0x180008136  jz      loc_180008738
0x18000813c  mov     edx, r15d
0x18000813f  cmp     edx, cs:?g_cPlugins@@3KA; ulong g_cPlugins
0x180008145  jnb     loc_180008738
0x18000814b  mov     eax, edx
0x18000814d  imul    r15, rax, 188h
0x180008154  mov     rax, [rbx+4]
0x180008158  add     r15, r8
0x18000815b  mov     [rsp+110h+var_C0], r15
0x180008160  sub     rax, [r15+44h]
0x180008164  jnz     short loc_18000816E
0x180008166  mov     rax, [rbx+0Ch]
0x18000816a  sub     rax, [r15+4Ch]
0x18000816e  test    rax, rax
0x180008171  jnz     loc_1800086A5
0x180008177  test    byte ptr [r15+0A0h], 1
0x18000817f  mov     [rsp+110h+arg_18], r12
0x180008187  lea     r12, Class
0x18000818e  jz      loc_1800086AC
0x180008194  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x18000819b  lea     rcx, [rsp+110h+var_98]
0x1800081a0  mov     [rsp+110h+var_E8], rcx
0x1800081a5  mov     r9d, 2
0x1800081ab  lea     rcx, [rbp+10h+SourceSid]
0x1800081af  mov     r8, rsi
0x1800081b2  mov     [rsp+110h+phkResult], rcx
0x1800081b7  xor     edx, edx
0x1800081b9  mov     rcx, [r15+10h]
0x1800081bd  mov     rax, [rax+20h]
0x1800081c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081c6  mov     ebx, eax
0x1800081c8  test    eax, eax
0x1800081ca  jnz     loc_180008C9D
0x1800081d0  mov     rsi, [rbp+10h+SourceSid]
0x1800081d4  xor     ebx, ebx
0x1800081d6  mov     [rsp+110h+var_D0], rbx
0x1800081db  mov     r14, [r15+160h]
0x1800081e2  xor     ebx, ebx
0x1800081e4  mov     [rsp+110h+lpSubKey], rbx
0x1800081e9  mov     [rsp+110h+hKey], rbx
0x1800081ee  test    r14, r14
0x1800081f1  jz      loc_1800088C3
0x1800081f7  test    rsi, rsi
0x1800081fa  jz      loc_1800088C3
0x180008200  lea     rdx, [rsp+110h+lpSubKey]; unsigned __int16 **
0x180008205  mov     rcx, rsi; void *
0x180008208  call    ?GetUserSid2NameSubKey@@YAJPEAXPEAPEAG@Z; GetUserSid2NameSubKey(void *,ushort * *)
0x18000820d  mov     rdi, [rsp+110h+lpSubKey]
0x180008212  mov     ebx, eax
0x180008214  lea     r12, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18000821b  test    eax, eax
0x18000821d  jnz     loc_180009276
0x180008223  lea     rax, [rsp+110h+hKey]
0x180008228  mov     r9d, 20019h; samDesired
0x18000822e  xor     r8d, r8d; ulOptions
0x180008231  mov     [rsp+110h+phkResult], rax; phkResult
0x180008236  mov     rdx, rdi; lpSubKey
0x180008239  mov     rcx, r14; hKey
0x18000823c  call    cs:__imp_RegOpenKeyExW
0x180008242  mov     ebx, eax
0x180008244  test    eax, eax
0x180008246  jnz     loc_1800092B7
0x18000824c  test    rdi, rdi
0x18000824f  jz      short loc_180008264
0x180008251  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180008258  mov     rcx, rdi
0x18000825b  mov     rax, [rax+30h]
0x18000825f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008264  test    ebx, ebx
0x180008266  jnz     loc_180008874
0x18000826c  mov     rcx, [rsp+110h+hKey]; hkey
0x180008271  lea     rax, [rbp+10h+SourceString]
0x180008275  xor     ebx, ebx
0x180008277  mov     [rsp+110h+phkResult], rax; void **
0x18000827c  lea     r9, [rbp+10h+arg_20]; unsigned int *
0x180008280  mov     [rbp+10h+arg_20], ebx
0x180008283  mov     r8d, 6; dwFlags
0x180008289  lea     rdx, aAuthenticating; "AuthenticatingAuthority"
0x180008290  call    ?GetRegVal@@YAJPEAUHKEY__@@PEBGKPEAKPEAPEAX@Z; GetRegVal(HKEY__ *,ushort const *,ulong,ulong *,void * *)
0x180008295  mov     r8d, eax
0x180008298  test    eax, eax
0x18000829a  jnz     loc_18000934C
0x1800082a0  mov     rdx, [rbp+10h+SourceString]; SourceString
0x1800082a4  lea     rcx, [rbp+10h+DestinationString]; DestinationString
0x1800082a8  call    cs:__imp_RtlInitUnicodeString
0x1800082ae  mov     rcx, [rsp+110h+hKey]; hkey
0x1800082b3  lea     rax, [rbp+10h+var_78]
0x1800082b7  lea     r9, [rbp+10h+arg_20]; unsigned int *
0x1800082bb  mov     [rsp+110h+phkResult], rax; void **
0x1800082c0  mov     r8d, 6; dwFlags
0x1800082c6  mov     [rbp+10h+arg_20], ebx
0x1800082c9  lea     rdx, aIdentityname; "IdentityName"
0x1800082d0  call    ?GetRegVal@@YAJPEAUHKEY__@@PEBGKPEAKPEAPEAX@Z; GetRegVal(HKEY__ *,ushort const *,ulong,ulong *,void * *)
0x1800082d5  mov     r8d, eax
0x1800082d8  test    eax, eax
0x1800082da  jnz     loc_18000938E
0x1800082e0  mov     rdx, [rbp+10h+var_78]; SourceString
0x1800082e4  lea     rcx, [rbp+10h+var_68]; DestinationString
0x1800082e8  call    cs:__imp_RtlInitUnicodeString
0x1800082ee  cmp     [rbp+10h+var_68.Length], bx
0x1800082f2  jz      loc_18000908F
0x1800082f8  mov     rcx, [rsp+110h+hKey]; hkey
0x1800082fd  lea     rax, [rbp+10h+var_70]
0x180008301  lea     r9, [rbp+10h+arg_20]; unsigned int *
0x180008305  mov     [rsp+110h+phkResult], rax; void **
0x18000830a  mov     r8d, 6; dwFlags
0x180008310  mov     [rbp+10h+arg_20], ebx
0x180008313  lea     rdx, aDisplayname; "DisplayName"
0x18000831a  call    ?GetRegVal@@YAJPEAUHKEY__@@PEBGKPEAKPEAPEAX@Z; GetRegVal(HKEY__ *,ushort const *,ulong,ulong *,void * *)
0x18000831f  lea     rdi, aOnecoreDsExtCl_16+26h; ""
0x180008326  lea     r14, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000832d  test    eax, eax
0x18000832f  jnz     loc_1800090F4
0x180008335  mov     rdx, [rbp+10h+var_70]; SourceString
0x180008339  lea     rcx, [rbp+10h+var_48]; DestinationString
0x18000833d  call    cs:__imp_RtlInitUnicodeString
0x180008343  mov     rcx, [rsp+110h+hKey]; hkey
0x180008348  lea     rax, [rsp+110h+var_A0]
0x18000834d  lea     r9, [rbp+10h+arg_20]; unsigned int *
0x180008351  mov     [rsp+110h+phkResult], rax; void **
0x180008356  mov     r8d, 6; dwFlags
0x18000835c  mov     [rbp+10h+arg_20], ebx
0x18000835f  lea     rdx, aSamname; "SAMName"
0x180008366  call    ?GetRegVal@@YAJPEAUHKEY__@@PEBGKPEAKPEAPEAX@Z; GetRegVal(HKEY__ *,ushort const *,ulong,ulong *,void * *)
0x18000836b  test    eax, eax
0x18000836d  jnz     loc_1800087EA
0x180008373  mov     rdx, [rsp+110h+var_A0]; SourceString
0x180008378  lea     rcx, [rbp+10h+var_38]; DestinationString
0x18000837c  call    cs:__imp_RtlInitUnicodeString
0x180008382  mov     rcx, [rsp+110h+hKey]; hkey
0x180008387  lea     rax, [rsp+110h+var_A0]
0x18000838c  lea     r9, [rbp+10h+arg_20]; unsigned int *
0x180008390  mov     [rsp+110h+phkResult], rax; void **
0x180008395  mov     r8d, 10h; dwFlags
0x18000839b  mov     [rbp+10h+arg_20], ebx
0x18000839e  lea     rdx, aFlags; "Flags"
0x1800083a5  mov     [rsp+110h+var_A0], rbx
0x1800083aa  mov     r15d, ebx
0x1800083ad  call    ?GetRegVal@@YAJPEAUHKEY__@@PEBGKPEAKPEAPEAX@Z; GetRegVal(HKEY__ *,ushort const *,ulong,ulong *,void * *)
0x1800083b2  mov     r14, [rsp+110h+var_A0]
0x1800083b7  mov     ebx, eax
0x1800083b9  test    eax, eax
0x1800083bb  jnz     loc_180008793
0x1800083c1  mov     r9d, [rbp+10h+arg_20]
0x1800083c5  cmp     r9d, 4
0x1800083c9  jnz     loc_1800093D0
0x1800083cf  mov     r15d, [r14]
0x1800083d2  test    r14, r14
0x1800083d5  jz      short loc_1800083EA
0x1800083d7  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800083de  mov     rcx, r14
0x1800083e1  mov     rax, [rax+30h]
0x1800083e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083ea  test    ebx, ebx
0x1800083ec  jnz     loc_18000940F
0x1800083f2  movzx   eax, [rbp+10h+var_48.MaximumLength]
0x1800083f6  movzx   ecx, [rbp+10h+var_38.MaximumLength]
0x1800083fa  movzx   r12d, [rbp+10h+DestinationString.MaximumLength]
0x1800083ff  add     ecx, eax
0x180008401  movzx   eax, [rbp+10h+var_68.MaximumLength]
0x180008405  add     r12d, 90h
0x18000840c  add     ecx, eax
0x18000840e  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180008415  add     r12d, ecx
0x180008418  mov     ecx, r12d
0x18000841b  mov     rax, [rax+28h]
0x18000841f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008424  mov     [rsp+110h+lpSubKey], rax
0x180008429  mov     r13, rax
0x18000842c  test    rax, rax
0x18000842f  jz      loc_180008F4E
0x180008435  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000843c  lea     r8, [rsp+110h+var_A8]
0x180008441  mov     rcx, [rbp+10h+arg_0]
0x180008445  mov     edx, r12d
0x180008448  mov     rax, [rax+38h]
0x18000844c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008451  mov     ebx, eax
0x180008453  test    eax, eax
0x180008455  jnz     loc_180008FFC
0x18000845b  lea     rdx, [r13+4Ch]; DestinationSid
0x18000845f  mov     dword ptr [r13+0], 3
0x180008467  mov     r8, rsi; SourceSid
0x18000846a  mov     [r13+48h], r15d
0x18000846e  mov     ecx, 44h ; 'D'; DestinationSidLength
0x180008473  call    cs:__imp_RtlCopySid
0x180008479  mov     ebx, eax
0x18000847b  test    eax, eax
0x18000847d  jnz     loc_180009149
0x180008483  mov     r15, [rsp+110h+var_A8]
0x180008488  lea     r14, [r13+90h]
0x18000848f  mov     rdx, [rbp+10h+DestinationString.Buffer]; Src
0x180008493  sub     r15, r13
0x180008496  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000849d  mov     r8d, 0FFFFFFFFh
0x1800084a3  test    rdx, rdx
0x1800084a6  jz      loc_180008DEE
0x1800084ac  mov     rax, rsi
0x1800084af  nop
0x1800084b0  inc     rax
0x1800084b3  cmp     word ptr [rdx+rax*2], 0
0x1800084b8  jnz     short loc_1800084B0
0x1800084ba  mov     ecx, eax
0x1800084bc  add     rcx, rcx
0x1800084bf  cmp     rcx, r8
0x1800084c2  jbe     loc_1800088F5
0x1800084c8  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x1800084cf  lea     rax, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800084d6  movzx   ecx, byte ptr [r9-1]
0x1800084db  mov     r10, r9
0x1800084de  dec     r9
0x1800084e1  cmp     cl, 5Ch ; '\'
0x1800084e4  jz      short loc_1800084EB
0x1800084e6  cmp     r9, rax
0x1800084e9  ja      short loc_1800084D6
0x1800084eb  xor     r11d, r11d
0x1800084ee  mov     eax, 134Bh
0x1800084f3  cmp     cl, 5Ch ; '\'
0x1800084f6  lea     rcx, aRtldwordmult; "RtlDWordMult"
0x1800084fd  cmovz   r9, r10
0x180008501  lea     r8, Class
0x180008508  mov     [rsp+30h], r8
0x18000850d  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180008514  mov     [rsp+110h+var_E8], rcx
0x180008519  mov     r8d, 0C0000095h
0x18000851f  mov     rcx, r11
0x180008522  mov     dword ptr [rsp+110h+phkResult], eax
0x180008526  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000852b  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180008532  mov     ebx, 0C0000095h
0x180008537  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000853c  mov     r9, rax
0x18000853f  lea     rax, Class
0x180008546  mov     [rsp+30h], rax
0x18000854b  lea     rax, aPutclientstrin; "PutClientString(AuthorityName)"
0x180008552  mov     [rsp+110h+var_E8], rax
0x180008557  mov     dword ptr [rsp+110h+phkResult], 1155h
0x18000855f  mov     r8d, ebx
0x180008562  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180008569  xor     ecx, ecx
0x18000856b  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180008570  mov     r15, [rsp+110h+var_C0]
0x180008575  cmp     [rsp+110h+var_D0], 0
0x18000857b  jz      short loc_18000858A
0x18000857d  mov     rcx, [r15+168h]; Resource
0x180008584  call    cs:__imp_RtlReleaseResource
0x18000858a  mov     r14, [rbp+10h+var_90]
  ... truncated ...
```
