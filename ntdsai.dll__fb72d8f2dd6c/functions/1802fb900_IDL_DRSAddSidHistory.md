# IDL_DRSAddSidHistory

- ea: `0x1802fb900`
- end: `0x1802fd405`
- name: `IDL_DRSAddSidHistory`
- size: `6917`
- prototype: ``
- caller_count: `0`
- callee_count: `60`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180006330`
- `0x180006360`
- `0x1800067d0`
- `0x18000bb80`
- `0x18000ef30`
- `0x18000efd8`
- `0x180011460`
- `0x18001e090`
- `0x18001ea60`
- `0x180021aa3`
- `0x180022690`
- `0x1800234b4`
- `0x1800234f0`
- `0x18002a060`
- `0x18002a0bc`
- `0x180037ce0`
- `0x1800f998c`
- `0x180168aa4`
- `0x18016acf4`
- `0x18016ae88`
- `0x180172edc`
- `0x180173260`
- `0x180180c50`
- `0x180181ae0`
- `0x180181bf0`
- `0x1801c4a34`
- `0x1801d0ea0`
- `0x1801d614c`
- `0x1801de8ec`
- `0x1801e66c4`
- `0x1802801b8`
- `0x180280628`
- `0x1802909e8`
- `0x1802c4a90`
- `0x1802fa068`
- `0x1802fa2d4`
- `0x1802faca4`
- `0x1802fada8`
- `0x1802faf78`
- `0x1802fb074`
- `0x1802fb18c`
- `0x1802fb238`
- `0x1802fb3b8`
- `0x1802fb584`
- `0x1802fb640`
- `0x1802fb6ec`
- `0x1802fb900`
- `0x1802fd40c`
- `0x1802fe5ac`
- `0x1802fe830`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1802fb960`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1802fb960`
- `RPCRT4!RpcRevertToSelf` at `0x1802fc20c`
- `RPCRT4!RpcRevertToSelf` at `0x1802fc20c`
- `RPCRT4!RpcImpersonateClient` at `0x1802fc04f`
- `RPCRT4!RpcImpersonateClient` at `0x1802fc04f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802fcee1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802fcee1`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1802fc5e3`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1802fc5e3`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x1802fc5eb`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x1802fc5eb`
- `ntdll!RtlSubAuthoritySid` at `0x1802fc8d0`
- `ntdll!RtlSubAuthoritySid` at `0x1802fc8d0`
- `ntdll!RtlInitUnicodeString` at `0x1802fc02c`
- `ntdll!RtlInitUnicodeString` at `0x1802fc02c`
- `ntdll!RtlCopySid` at `0x1802fccf4`
- `ntdll!RtlCopySid` at `0x1802fccf4`
- `ntdll!RtlNtStatusToDosError` at `0x1802fbd99`
- `ntdll!RtlNtStatusToDosError` at `0x1802fc1e9`
- `ntdll!RtlNtStatusToDosError` at `0x1802fc279`
- `ntdll!RtlNtStatusToDosError` at `0x1802fc7ee`
- `ntdll!RtlNtStatusToDosError` at `0x1802fbd99`
- `ntdll!RtlNtStatusToDosError` at `0x1802fc1e9`
- `ntdll!RtlNtStatusToDosError` at `0x1802fc279`
- `ntdll!RtlNtStatusToDosError` at `0x1802fc7ee`
- `ntdll!RtlLengthSid` at `0x1802fcc68`
- `ntdll!RtlLengthSid` at `0x1802fcc68`
- `SAMLIB!SamCloseHandle` at `0x1802fc28b`
- `SAMLIB!SamCloseHandle` at `0x1802fcef4`
- `SAMLIB!SamCloseHandle` at `0x1802fcf07`
- `SAMLIB!SamCloseHandle` at `0x1802fc28b`
- `SAMLIB!SamCloseHandle` at `0x1802fcef4`
- `SAMLIB!SamCloseHandle` at `0x1802fcf07`
- `SAMLIB!SamConnectWithCreds` at `0x1802fc177`
- `SAMLIB!SamConnectWithCreds` at `0x1802fc1d6`
- `SAMLIB!SamConnectWithCreds` at `0x1802fc177`
- `SAMLIB!SamConnectWithCreds` at `0x1802fc1d6`
- `SAMLIB!SamOpenGroup` at `0x1802fc26d`
- `SAMLIB!SamOpenGroup` at `0x1802fc26d`
- `SAMSRV!SamIMixedDomain2` at `0x1802fbd86`
- `SAMSRV!SamIMixedDomain2` at `0x1802fbd86`

## string_xrefs

- `0x1802fc4e9`: `IDL_DRSAddSidHistory`

## pseudocode

```c
__int64 __fastcall IDL_DRSAddSidHistory(__int64 a1, int a2, __int64 a3, _DWORD *a4, ULONG *a5)
{
  unsigned int v7; // r14d
  ULONG RPCKeySize; // ebx
  struct _DSNAME *v9; // rcx
  unsigned int v10; // edi
  unsigned int v11; // eax
  _QWORD *v12; // r15
  ULONG v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r15
  ULONG IsDomainAdminOrLocalAdmin; // eax
  NTSTATUS v17; // eax
  __int64 v18; // rbx
  const WCHAR *v19; // rax
  unsigned int v20; // eax
  int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  int v27; // eax
  unsigned int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rax
  size_t v31; // rbx
  STRSAFE_LPWSTR v32; // r11
  NTSTATUS v33; // eax
  NTSTATUS v34; // eax
  ULONG FlatName; // eax
  __int64 inited; // rax
  __int64 v37; // rcx
  __int64 v38; // rax
  size_t v39; // rdi
  wchar_t *v40; // rbx
  UINT ACP; // eax
  int v42; // r8d
  int v43; // r9d
  __int64 v44; // rbx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rax
  int v48; // eax
  int v49; // eax
  unsigned int v50; // ebx
  int v51; // ecx
  NTSTATUS v52; // eax
  int v53; // eax
  ULONG v54; // eax
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // rax
  int v58; // r8d
  unsigned int *v59; // rcx
  __int64 v60; // rax
  unsigned int v61; // edi
  __int64 v62; // rbx
  ULONG v63; // eax
  __int64 v64; // rdx
  __int64 v65; // rbx
  __int64 v66; // rax
  __int64 v67; // rcx
  void *v68; // rdx
  ULONG v69; // eax
  unsigned int v70; // edi
  __int64 v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // r12
  int v74; // r8d
  int v75; // r9d
  int v76; // ecx
  __int64 v77; // rdx
  int v78; // r12d
  __int64 v79; // rcx
  int v80; // eax
  const wchar_t *v81; // rax
  __int64 v82; // rax
  _QWORD *v83; // rbx
  __int64 v84; // rdx
  __int64 v85; // rdx
  __int64 v86; // rdx
  const wchar_t **v87; // rdx
  unsigned int j; // ebx
  const wchar_t *v89; // rax
  int v91; // [rsp+20h] [rbp-698h]
  int v92; // [rsp+20h] [rbp-698h]
  int v93; // [rsp+20h] [rbp-698h]
  int v94; // [rsp+28h] [rbp-690h]
  int v95; // [rsp+28h] [rbp-690h]
  int v96; // [rsp+28h] [rbp-690h]
  __int64 v97; // [rsp+30h] [rbp-688h]
  int v98; // [rsp+30h] [rbp-688h]
  int v99; // [rsp+30h] [rbp-688h]
  int v100; // [rsp+30h] [rbp-688h]
  int v101; // [rsp+38h] [rbp-680h]
  int v102; // [rsp+38h] [rbp-680h]
  int v103; // [rsp+38h] [rbp-680h]
  unsigned int v104; // [rsp+78h] [rbp-640h] BYREF
  char v105[4]; // [rsp+7Ch] [rbp-63Ch] BYREF
  int v106; // [rsp+80h] [rbp-638h]
  __int64 Value; // [rsp+88h] [rbp-630h] BYREF
  int v108; // [rsp+90h] [rbp-628h] BYREF
  int i; // [rsp+94h] [rbp-624h]
  _DWORD v110[2]; // [rsp+98h] [rbp-620h] BYREF
  ULONG DestinationSidLength; // [rsp+A0h] [rbp-618h] BYREF
  unsigned int v112; // [rsp+A4h] [rbp-614h] BYREF
  PCWSTR SourceString; // [rsp+A8h] [rbp-610h]
  __int64 v114; // [rsp+B0h] [rbp-608h]
  __int64 v115; // [rsp+B8h] [rbp-600h]
  unsigned int v116; // [rsp+C0h] [rbp-5F8h] BYREF
  int v117; // [rsp+C4h] [rbp-5F4h] BYREF
  wchar_t *v118; // [rsp+C8h] [rbp-5F0h] BYREF
  __int64 v119; // [rsp+D0h] [rbp-5E8h] BYREF
  char v120[4]; // [rsp+D8h] [rbp-5E0h] BYREF
  NTSTATUS v121; // [rsp+DCh] [rbp-5DCh]
  int v122; // [rsp+E0h] [rbp-5D8h] BYREF
  int v123; // [rsp+E4h] [rbp-5D4h] BYREF
  unsigned int v124; // [rsp+E8h] [rbp-5D0h]
  unsigned int v125; // [rsp+ECh] [rbp-5CCh] BYREF
  __int64 v126; // [rsp+F0h] [rbp-5C8h] BYREF
  _QWORD *v127; // [rsp+F8h] [rbp-5C0h]
  STRSAFE_LPWSTR pszDest; // [rsp+100h] [rbp-5B8h]
  const wchar_t **v129; // [rsp+108h] [rbp-5B0h] BYREF
  int v130; // [rsp+110h] [rbp-5A8h] BYREF
  unsigned int v131; // [rsp+114h] [rbp-5A4h] BYREF
  int v132; // [rsp+118h] [rbp-5A0h] BYREF
  int v133; // [rsp+11Ch] [rbp-59Ch] BYREF
  unsigned int v134; // [rsp+120h] [rbp-598h]
  int v135; // [rsp+124h] [rbp-594h]
  int v136; // [rsp+128h] [rbp-590h]
  __int64 v137; // [rsp+130h] [rbp-588h] BYREF
  __int64 v138; // [rsp+138h] [rbp-580h]
  __int64 v139; // [rsp+140h] [rbp-578h] BYREF
  void *v140[2]; // [rsp+148h] [rbp-570h] BYREF
  void *v141[2]; // [rsp+158h] [rbp-560h]
  void *v142[2]; // [rsp+168h] [rbp-550h]
  __int64 v143; // [rsp+178h] [rbp-540h] BYREF
  __int64 v144; // [rsp+180h] [rbp-538h] BYREF
  __int64 v145; // [rsp+188h] [rbp-530h] BYREF
  __int64 v146; // [rsp+190h] [rbp-528h]
  __int64 v147; // [rsp+198h] [rbp-520h] BYREF
  __int64 v148; // [rsp+1A0h] [rbp-518h] BYREF
  __int64 v149; // [rsp+1A8h] [rbp-510h] BYREF
  __int64 v150; // [rsp+1B0h] [rbp-508h] BYREF
  int v151; // [rsp+1B8h] [rbp-500h]
  PCWSTR v152; // [rsp+1C0h] [rbp-4F8h]
  struct _UNICODE_STRING DestinationString; // [rsp+1C8h] [rbp-4F0h] BYREF
  __int128 v154; // [rsp+1D8h] [rbp-4E0h] BYREF
  __int64 v155; // [rsp+1E8h] [rbp-4D0h]
  __int64 v156; // [rsp+1F0h] [rbp-4C8h]
  __int64 v157; // [rsp+200h] [rbp-4B8h] BYREF
  int v158; // [rsp+208h] [rbp-4B0h]
  int Internal; // [rsp+20Ch] [rbp-4ACh]
  int v160; // [rsp+210h] [rbp-4A8h]
  int v161; // [rsp+218h] [rbp-4A0h]
  int v162; // [rsp+21Ch] [rbp-49Ch]
  __int64 v163; // [rsp+220h] [rbp-498h]
  __int64 v164; // [rsp+228h] [rbp-490h]
  __int64 v165; // [rsp+230h] [rbp-488h]
  __int64 v166; // [rsp+240h] [rbp-478h]
  int v167; // [rsp+248h] [rbp-470h]
  int *v168; // [rsp+258h] [rbp-460h]
  __int128 v169; // [rsp+260h] [rbp-458h] BYREF
  __int128 v170; // [rsp+270h] [rbp-448h]
  __int128 v171; // [rsp+280h] [rbp-438h]
  __int64 v172; // [rsp+290h] [rbp-428h] BYREF
  __int16 v173; // [rsp+298h] [rbp-420h]
  __int16 v174; // [rsp+2A8h] [rbp-410h]
  int v175; // [rsp+2B8h] [rbp-400h]
  char v176[192]; // [rsp+318h] [rbp-3A0h] BYREF
  __int64 ResObj; // [rsp+3D8h] [rbp-2E0h]
  _OWORD Sid[2]; // [rsp+3F0h] [rbp-2C8h] BYREF
  _OWORD v179[2]; // [rsp+410h] [rbp-2A8h] BYREF
  _OWORD v180[2]; // [rsp+430h] [rbp-288h] BYREF
  int v181; // [rsp+450h] [rbp-268h] BYREF
  const wchar_t *v182; // [rsp+458h] [rbp-260h]
  int v183; // [rsp+470h] [rbp-248h]
  const wchar_t *v184; // [rsp+478h] [rbp-240h]
  __int64 v185; // [rsp+488h] [rbp-230h] BYREF
  int v186; // [rsp+490h] [rbp-228h]
  __int64 *v187; // [rsp+498h] [rbp-220h]
  __int64 v188; // [rsp+4A8h] [rbp-210h] BYREF
  int v189; // [rsp+4B0h] [rbp-208h]
  __int64 *v190; // [rsp+4B8h] [rbp-200h]
  __int64 v191; // [rsp+4C8h] [rbp-1F0h] BYREF

  v115 = a3;
  LODWORD(v137) = a2;
  v138 = a1;
  v155 = a1;
  v156 = a3;
  Value = (__int64)TlsGetValue(dwTSindex);
  v110[0] = 0;
  v104 = 0;
  v7 = 0;
  v106 = 0;
  v124 = 0;
  RPCKeySize = 87;
  v110[1] = 0;
  v126 = 0;
  v127 = 0;
  v130 = 0;
  SourceString = 0;
  v152 = 0;
  *(_OWORD *)v140 = 0;
  *(_OWORD *)v141 = 0;
  *(_OWORD *)v142 = 0;
  v169 = 0;
  v170 = 0;
  v171 = 0;
  v116 = 0;
  DestinationString = 0;
  v143 = 0;
  v147 = 0;
  memset(v179, 0, 28);
  memset(Sid, 0, 28);
  memset(v180, 0, 28);
  v134 = 0;
  v117 = 0;
  v112 = 0;
  v105[0] = 1;
  DestinationSidLength = 0;
  v119 = 0;
  v131 = 0;
  v133 = 0;
  v123 = 0;
  v132 = 0;
  v122 = 0;
  memset_0(&v172, 0, 0x160u);
  v136 = 0;
  v154 = 0;
  v135 = 0;
  v125 = 0;
  v129 = 0;
  v149 = 0;
  v150 = 0;
  v145 = 0;
  v139 = 0;
  v144 = 0;
  v108 = 0;
  LODWORD(v118) = 0;
  pszDest = 0;
  v148 = -1;
  v146 = 0;
  v114 = 0;
  DRS_Prepare(&Value, v138, 3);
  drsReferenceContext(v138);
  *a4 = 1;
  *a5 = 8430;
  if ( (*(_DWORD *)a3 & 0x40000000) != 0 )
  {
    v112 = 0;
    if ( (*(_BYTE *)(v138 + 916) & 1) != 0 )
    {
      RPCKeySize = 0;
    }
    else
    {
      RPCKeySize = GetRPCKeySize(v9, &v112, &v104);
      if ( !RPCKeySize )
        RPCKeySize = v112 < 0x80 ? 0x216E : 0;
    }
    v10 = RPCKeySize;
    v106 = RPCKeySize;
    *a5 = RPCKeySize;
    v7 = v104;
    goto LABEL_181;
  }
  if ( *(int *)a3 < 0 )
  {
    v135 = 1;
    v10 = IDL_DRSInheritSecurityIdentity(v138, v137, a3, (_DWORD)a4, (__int64)a5);
    v106 = v10;
LABEL_181:
    v15 = Value;
    goto LABEL_182;
  }
  v11 = DRS_MSG_ADDSIDREQ_V1_InputValidate(a3);
  v10 = v11;
  v106 = v11;
  if ( v11 )
  {
    if ( v11 == 8437 )
    {
      v10 = 87;
      v106 = 87;
    }
    goto LABEL_181;
  }
  if ( (unsigned int)IsDomainInForest(*(STRSAFE_LPCWSTR *)(a3 + 8)) )
  {
    RPCKeySize = 8534;
    v7 = 18482669;
LABEL_180:
    *a5 = RPCKeySize;
    goto LABEL_181;
  }
  if ( !(unsigned int)IsDomainInForest(*(STRSAFE_LPCWSTR *)(a3 + 80)) )
  {
    RPCKeySize = 8535;
    v7 = 18482676;
    goto LABEL_180;
  }
  v9 = qword_18052B2C0;
  if ( !qword_18052B2C0 || (v12 = v127, !(unsigned int)NameMatched(qword_18052B2C0, *v127)) )
  {
    RPCKeySize = 8314;
    v7 = 18482684;
    goto LABEL_180;
  }
  if ( !*(_DWORD *)(*v12 + 4LL) || !v12[3] )
  {
    RPCKeySize = 8430;
    v7 = 18482691;
    goto LABEL_180;
  }
  v13 = VerifyAuditingEnabled();
  RPCKeySize = v13;
  if ( v13 )
  {
    *a5 = v13;
    v7 = 18482698;
    goto LABEL_181;
  }
  v14 = *v12 + 24LL;
  v15 = Value;
  IsDomainAdminOrLocalAdmin = VerifyCallerIsDomainAdminOrLocalAdmin(Value, v14, &v130);
  RPCKeySize = IsDomainAdminOrLocalAdmin;
  if ( IsDomainAdminOrLocalAdmin )
  {
    v7 = 18482708;
LABEL_24:
    *a5 = IsDomainAdminOrLocalAdmin;
    goto LABEL_182;
  }
  if ( !v130 )
  {
    ForceFailureAuditOnDstDom(
      *(_QWORD *)(v115 + 16),
      *(_QWORD *)(v115 + 8),
      *v127 + 24LL,
      *(_QWORD *)(v115 + 88),
      v127[3]);
    RPCKeySize = 8344;
    *a5 = 8344;
    v7 = 18482719;
    goto LABEL_182;
  }
  v17 = SamIMixedDomain2(*v127 + 24LL, v105);
  v121 = v17;
  if ( v17 < 0 )
  {
    IsDomainAdminOrLocalAdmin = RtlNtStatusToDosError(v17);
    RPCKeySize = IsDomainAdminOrLocalAdmin;
    v7 = 18482728;
    goto LABEL_24;
  }
  if ( v105[0] )
  {
    RPCKeySize = 8496;
    *a5 = 8496;
    v7 = 18482733;
    goto LABEL_182;
  }
  v18 = v115;
  v19 = *(const WCHAR **)(v115 + 24);
  SourceString = v19;
  if ( v19 )
  {
    v152 = v19;
  }
  else
  {
    SourceString = (PCWSTR)FindSrcDomainController(*(_QWORD *)(v115 + 8));
    v152 = SourceString;
    if ( !SourceString )
    {
      RPCKeySize = 8537;
      *a5 = 8537;
      v7 = 18482747;
      goto LABEL_182;
    }
  }
  if ( *(_DWORD *)(v18 + 32) )
  {
    v20 = DsaSafeAdd(*(unsigned int *)(v18 + 32), 1);
    v21 = DsaSafeMult(v20, 2);
    v140[0] = (void *)THAlloc_(v15, 1, v21, 1, 0, 18482759);
    v22 = DsaSafeMult(*(unsigned int *)(v18 + 32), 2);
    memcpy_0(v140[0], *(const void **)(v18 + 40), v22);
    LODWORD(v140[1]) = *(_DWORD *)(v18 + 32);
  }
  if ( *(_DWORD *)(v18 + 48) )
  {
    v23 = DsaSafeAdd(*(unsigned int *)(v18 + 48), 1);
    v24 = DsaSafeMult(v23, 2);
    v141[0] = (void *)THAlloc_(v15, 1, v24, 1, 0, 18482765);
    v25 = DsaSafeMult(*(unsigned int *)(v18 + 48), 2);
    memcpy_0(v141[0], *(const void **)(v18 + 56), v25);
    LODWORD(v141[1]) = *(_DWORD *)(v18 + 48);
  }
  if ( *(_DWORD *)(v18 + 64) )
  {
    v26 = DsaSafeAdd(*(unsigned int *)(v18 + 64), 1);
    v27 = DsaSafeMult(v26, 2);
    v142[0] = (void *)THAlloc_(v15, 1, v27, 1, 0, 18482771);
    v28 = DsaSafeMult(*(unsigned int *)(v18 + 64), 2);
    memcpy_0(v142[0], *(const void **)(v18 + 72), v28);
    LODWORD(v142[1]) = *(_DWORD *)(v18 + 64);
  }
  HIDWORD(v142[1]) = 2;
  if ( LODWORD(v140[1]) || LODWORD(v141[1]) )
  {
    if ( !LODWORD(v142[1]) )
    {
      v142[0] = (void *)THAlloc_(v15, 1, 4, 1, 0, 18482792);
      *(_WORD *)v142[0] = 0;
    }
  }
  else if ( !LODWORD(v142[1]) )
  {
    v140[0] = 0;
    v141[0] = 0;
    v142[0] = 0;
    LODWORD(v118) = 1;
  }
  LODWORD(v169) = 48;
  *((_QWORD *)&v169 + 1) = 0;
  DWORD2(v170) = 0;
  *(_QWORD *)&v170 = 0;
  v171 = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  if ( (_DWORD)v118 )
  {
    AssignAuthzClientContext(v15 + 5960, 0);
    IsDomainAdminOrLocalAdmin = RpcImpersonateClient(0);
    RPCKeySize = IsDomainAdminOrLocalAdmin;
    if ( IsDomainAdminOrLocalAdmin )
    {
      v7 = 18482804;
      goto LABEL_24;
    }
    v108 = 1;
    v29 = -1;
    do
      ++v29;
    while ( SourceString[v29] );
    v30 = -1;
    do
      ++v30;
    while ( *(_WORD *)(*(_QWORD *)(v115 + 8) + 2 * v30) );
    v31 = v29 + v30 + 7;
    pszDest = (STRSAFE_LPWSTR)THAlloc_(v15, 1, 2 * (int)v31, 1, 0, 18482824);
    StringCchCopyW(pszDest, v31, L"cifs/");
    StringCchCatW(v32, v31, SourceString);
    StringCchCatW(pszDest, v31, L"@");
    StringCchCatW(pszDest, v31, *(STRSAFE_LPCWSTR *)(v115 + 8));
    v18 = v115;
  }
  v33 = SamConnectWithCreds(&DestinationString, &v143, 0x2000000, &v169, v140, pszDest, &v116);
  v121 = v33;
  if ( v33 )
  {
    if ( v33 == -1073610704 && pszDest )
    {
      v33 = SamConnectWithCreds(&DestinationString, &v143, 0x2000000, &v169, v140, 0, &v116);
      v121 = v33;
    }
    if ( v33 )
    {
      IsDomainAdminOrLocalAdmin = RtlNtStatusToDosError(v33);
      RPCKeySize = IsDomainAdminOrLocalAdmin;
      v7 = 18482850;
      goto LABEL_24;
    }
  }
  if ( v108 )
  {
    v108 = 0;
    RpcRevertToSelf();
  }
  IsDomainAdminOrLocalAdmin = GetDomainHandleAndSid(v143, *(_QWORD *)(v18 + 8), &v147, v179);
  RPCKeySize = IsDomainAdminOrLocalAdmin;
  if ( IsDomainAdminOrLocalAdmin )
  {
    v7 = 18482863;
    goto LABEL_24;
  }
  RPCKeySize = 0;
  v126 = 0;
  v34 = SamOpenGroup(v147, 917535, 512, &v126);
  if ( v34 >= 0 )
    SamCloseHandle(v126);
  else
    RPCKeySize = RtlNtStatusToDosError(v34);
  if ( RPCKeySize )
  {
    *a5 = RPCKeySize;
    v7 = 18482869;
    goto LABEL_182;
  }
  IsDomainAdminOrLocalAdmin = GetSrcPrincipalSid(v147, *(_QWORD *)(v115 + 16), v179, Sid, &v112, &v133);
  RPCKeySize = IsDomainAdminOrLocalAdmin;
  if ( IsDomainAdminOrLocalAdmin )
  {
    v7 = 18482876;
    goto LABEL_24;
  }
  LODWORD(v97) = *(_DWORD *)v115;
  FlatName = BuildCheckAndUpdateArgs(
               v15,
               v116,
               (WCHAR *)SourceString,
               *(_QWORD *)(v115 + 8),
               v140,
               Sid,
               v97,
               (_DWORD)v118,
               &v125,
               &v129,
               &v149,
               &v150,
               &v104,
               &v108,
               0);
  RPCKeySize = FlatName;
  if ( FlatName )
    goto LABEL_73;
  IsDomainAdminOrLocalAdmin = CheckIfSidsInForest(v125, v129, &v154);
  RPCKeySize = IsDomainAdminOrLocalAdmin;
  if ( IsDomainAdminOrLocalAdmin )
  {
    v7 = 18482903;
    goto LABEL_24;
  }
  FlatName = ImpersonateSrcAdmin(
               (unsigned int)v140,
               (_DWORD)v118,
               (unsigned int)&v104,
               (unsigned int)&v108,
               (__int64)&v148);
  RPCKeySize = FlatName;
  if ( FlatName )
    goto LABEL_73;
  FlatName = VerifySrcAuditingEnabledAndGetFlatName((PLSA_UNICODE_STRING)&DestinationString);
  RPCKeySize = FlatName;
  if ( FlatName )
    goto LABEL_73;
  FlatName = VerifySrcIsSP4OrGreater(v116, SourceString, &v104);
  RPCKeySize = FlatName;
  if ( FlatName
    || (FlatName = VerifyIsPDC(SourceString, &v104), (RPCKeySize = FlatName) != 0)
    || (FlatName = ForceAuditOnSrcObj(SourceString), (RPCKeySize = FlatName) != 0)
    || (FlatName = UnimpersonateSrcAdmin(v9, &v104, &v108, &v148), (RPCKeySize = FlatName) != 0) )
  {
LABEL_73:
    *a5 = FlatName;
    v7 = v104;
    goto LABEL_182;
  }
  inited = InitTHSTATE_Ex_(8, 18482977, 0, L"IDL_DRSAddSidHistory");
  v15 = inited;
  Value = inited;
  if ( !inited )
  {
    RPCKeySize = 8430;
    *a5 = 8430;
    v7 = 18482978;
    goto LABEL_182;
  }
  DBOpen2(1, inited + 5576);
  v151 = 1;
  v37 = -1;
  do
    ++v37;
  while ( *(_WORD *)(v127[3] + 2 * v37) );
  v38 = -1;
  do
    ++v38;
  while ( *(_WORD *)(*(_QWORD *)(v115 + 88) + 2 * v38) );
  v39 = v37 + v38 + 2;
  v40 = (wchar_t *)THAlloc_(v15, 1, 2 * (int)v39, 1, 0, 18482998);
  v118 = v40;
  StringCchCopyW(v40, v39, (STRSAFE_LPCWSTR)v127[3]);
  StringCchCatW(v40, v39, L"\\");
  StringCchCatW(v40, v39, *(STRSAFE_LPCWSTR *)(v115 + 88));
  LODWORD(v40) = GetUserDefaultLCID();
  ACP = GetACP();
  CrackNames(0, ACP, (_DWORD)v40, 2, 1, 1, (__int64)&v118, (__int64)&DestinationSidLength, (__int64)&v119);
  if ( v118 )
    THFreeAux(v15, (_DWORD)v118, v42, v43, 18483005);
  v118 = 0;
  v44 = v119;
  v45 = *(unsigned int *)(v119 + 16);
  if ( (_DWORD)v45 == 2 )
  {
    RPCKeySize = 8333;
    v7 = 18483008;
LABEL_168:
    *a5 = RPCKeySize;
    goto LABEL_169;
  }
  if ( (_DWORD)v45 == 3 )
  {
    RPCKeySize = 8471;
    v7 = 18483012;
    goto LABEL_168;
  }
  if ( !(unsigned int)CrackNameStatusSuccess(v45) )
  {
    v7 = 18483016;
LABEL_167:
    RPCKeySize = 8430;
    goto LABEL_168;
  }
  v136 = 1;
  if ( !(unsigned int)fNullUuid(&v154) )
  {
    v46 = *(_QWORD *)(v44 + 24);
    v47 = v154 - *(_QWORD *)(v46 + 8);
    if ( (_QWORD)v154 == *(_QWORD *)(v46 + 8) )
      v47 = *((_QWORD *)&v154 + 1) - *(_QWORD *)(v46 + 16);
    if ( v47 )
    {
      RPCKeySize = 8539;
      v7 = 18483029;
      goto LABEL_168;
    }
  }
  if ( (unsigned int)DBFindDSName(*(_QWORD *)(v15 + 5576), *(_QWORD *)(v44 + 24))
    || (unsigned int)DBGetSingleValue(*(_QWORD *)(v15 + 5576), 0, &v131, 4, 0) )
  {
    v7 = 18483040;
    goto LABEL_167;
  }
  v48 = SampDeriveMostBasicDsClass(v131) - 196638;
  if ( !v48 )
    goto LABEL_118;
  v49 = v48 - 458730;
  if ( v49 )
  {
    if ( v49 != 1 )
    {
      RPCKeySize = 8212;
      v7 = 18483098;
      goto LABEL_168;
    }
LABEL_118:
    if ( v112 != 1 )
    {
      RPCKeySize = 8540;
      v7 = 18483052;
      goto LABEL_168;
    }
    if ( (unsigned int)DBGetSingleValue(*(_QWORD *)(v15 + 5576), 589832, &v123, 4, 0) )
    {
      v7 = 18483057;
      goto LABEL_167;
    }
    v53 = v123 & 0x3B00;
    v123 = v53;
    if ( (v53 & 0xFFFFCDFF) != 0 || v133 != v53 )
    {
      RPCKeySize = 8540;
      v7 = 18483064;
      goto LABEL_168;
    }
    goto LABEL_126;
  }
  v50 = v112;
  if ( ((v112 - 2) & 0xFFFFFFFD) != 0 )
  {
    RPCKeySize = 8540;
    v7 = 18483073;
    goto LABEL_168;
  }
  if ( (unsigned int)DBGetSingleValue(*(_QWORD *)(v15 + 5576), 590574, &v132, 4, 0) )
  {
    v7 = 18483078;
    goto LABEL_167;
  }
  v52 = SampComputeGroupType(v51, v132, (unsigned int)&v122, (unsigned int)&DestinationSidLength, (__int64)v120);
  v121 = v52;
  if ( v52 < 0 )
  {
    RPCKeySize = RtlNtStatusToDosError(v52);
    *a5 = RPCKeySize;
    v7 = 18483085;
    goto LABEL_169;
  }
  if ( v50 == 2 && v122 != 2 || v50 == 4 && v122 != 1 )
  {
    RPCKeySize = 8540;
    v7 = 18483092;
    goto LABEL_168;
  }
  v44 = v119;
LABEL_126:
  if ( *RtlSubAuthoritySid(Sid, 0) == 32 )
  {
    RPCKeySize = 8245;
    v7 = 18483110;
    goto LABEL_168;
  }
  SampSplitNT4SID(Sid, v180);
  SampSplitNT4SID((PSID)(*(_QWORD *)(v44 + 24) + 24LL), v180);
  if ( v134 < 0x3E8 && v134 != v117 )
  {
    RPCKeySize = 8245;
    v7 = 18483123;
    goto LABEL_168;
  }
  DestinationSidLength = 590433;
  if ( !SCGetAttById(v15, 590433) )
  {
    v7 = 18483135;
    goto LABEL_167;
  }
  if ( (unsigned int)DBGetMultipleAtts_AttrTyp(
                       *(_QWORD *)(v15 + 5576),
                       (unsigned int)&DestinationSidLength,
                       1,
                       3,
                       v91,
                       v94,
                       v98,
                       v101,
                       (__int64)v110,
                       (__int64)&v145) )
  {
    v7 = 18483150;
    goto LABEL_167;
  }
  if ( !v110[0] )
    v145 = 0;
  LODWORD(v137) = 589970;
  if ( !SCGetAttById(v15, 589970) )
  {
    v7 = 18483164;
    goto LABEL_167;
  }
  if ( (unsigned int)DBGetMultipleAtts_AttrTyp(
                       *(_QWORD *)(v15 + 5576),
                       (unsigned int)&v137,
                       1,
                       3,
                       v92,
                       v95,
                       v99,
                       v102,
                       (__int64)v110,
                       (__int64)&v144) )
  {
    v7 = 18483179;
    goto LABEL_167;
  }
  if ( !v110[0] )
    v144 = 0;
  v172 = *(_QWORD *)(v44 + 24);
  v173 = 1;
  v174 = 97;
  InitCommarg(v176);
  ResObj = CreateResObj(*(_QWORD *)(v15 + 5576), *(_QWORD *)(v44 + 24));
  v54 = BuildDstObjATTRMODLIST(v15, v149, v150, v144, v145, (__int64)&v172);
  RPCKeySize = v54;
  if ( v54 )
  {
    *a5 = v54;
    v7 = 18483204;
  }
  else if ( v175 )
  {
    *(_DWORD *)(v15 + 5604) |= 0x800u;
    LocalModify(v15, &v172);
    *(_DWORD *)(v15 + 5604) &= ~0x800u;
    if ( !*(_DWORD *)(v15 + 5560) )
    {
      *(_DWORD *)(v15 + 5604) &= ~0x800u;
      v117 = 590433;
      if ( SCGetAttById(v15, 590433) )
      {
        if ( !(unsigned int)DBGetMultipleAtts_AttrTyp(
                              *(_QWORD *)(v15 + 5576),
                              (unsigned int)&v117,
                              1,
                              3,
                              v93,
                              v96,
                              v100,
                              v103,
                              (__int64)v110,
                              (__int64)&v139) )
        {
          if ( !v110[0] )
            v139 = 0;
          v55 = DSAllocAux(16, 18483274);
          v114 = v55;
          if ( v55 )
          {
            v56 = *(unsigned int *)(v139 + 8);
            *(_DWORD *)v55 = v56;
            v57 = DSAllocAux(16 * v56, 18483282);
            v59 = (unsigned int *)v114;
            *(_QWORD *)(v114 + 8) = v57;
            v60 = v139;
            v126 = v139;
            v61 = 0;
            i = 0;
            while ( v61 < *v59 )
            {
              v62 = 16LL * v61;
              v137 = v62;
              v63 = RtlLengthSid(*(PSID *)(v62 + *(_QWORD *)(v60 + 16) + 8));
              DestinationSidLength = v63;
              v64 = v114;
              *(_DWORD *)(v62 + *(_QWORD *)(v114 + 8)) = 0;
              v65 = *(_QWORD *)(v64 + 8);
              v66 = DSAllocAux(v63, 18483290);
              v67 = v137;
              *(_QWORD *)(v137 + v65 + 8) = v66;
              v68 = *(void **)(v67 + *(_QWORD *)(v114 + 8) + 8);
              if ( !v68 )
              {
                RPCKeySize = -1073741801;
                *a5 = -1073741801;
                v7 = 18483294;
                goto LABEL_161;
              }
              RtlCopySid(DestinationSidLength, v68, *(PSID *)(v67 + *(_QWORD *)(v126 + 16) + 8));
              i = ++v61;
              v60 = v126;
              v59 = (unsigned int *)v114;
            }
            v69 = ForceSuccessAuditOnDstObj(
                    *(_QWORD *)(v115 + 16),
                    *(_QWORD *)(v115 + 8),
                    v58,
                    (unsigned int)*(_QWORD *)(v119 + 24) + 24,
                    *(PCWSTR *)(v115 + 88),
                    (PCWSTR)v127[3],
                    (__int64)v59);
            RPCKeySize = v69;
            if ( v69 )
            {
              *a5 = v69;
              v7 = 18483309;
            }
            else
            {
              v124 = 1;
            }
LABEL_161:
            v55 = v114;
          }
          else
          {
            RPCKeySize = -1073741670;
            *a5 = -1073741670;
            v7 = 18483277;
          }
          goto LABEL_170;
        }
        v7 = 18483265;
      }
      else
      {
        v7 = 18483250;
      }
      goto LABEL_167;
    }
    RPCKeySize = mapApiErrorToWin32(v15);
    *a5 = RPCKeySize;
    v7 = 18483237;
  }
  else
  {
    *a5 = 0;
    RPCKeySize = 0;
    v7 = 18483219;
  }
LABEL_169:
  v55 = 0;
LABEL_170:
  if ( v55 )
  {
    v70 = 0;
    for ( i = 0; ; i = v70 )
    {
      v71 = *(_QWORD *)(v55 + 8);
      if ( v70 >= *(_DWORD *)v55 )
        break;
      v72 = *(_QWORD *)(v71 + 16LL * v70 + 8);
      if ( v72 )
      {
        DSFreeAux(v72, 18483322);
        v55 = v114;
      }
      ++v70;
    }
    DSFreeAux(v71, 18483326);
    DSFreeAux(v114, 18483327);
  }
  DBClose(*(_QWORD *)(v15 + 5576), v124);
  *a5 = RPCKeySize;
  v10 = v106;
LABEL_182:
  v73 = v115;
  _InterlockedDecrement((volatile signed __int32 *)(v138 + 16));
  UnimpersonateSrcAdmin(v9, &v104, &v108, &v148);
  if ( SourceString && SourceString != *(PCWSTR *)(v73 + 24) )
    LocalFree((HLOCAL)SourceString);
  if ( v147 )
    SamCloseHandle(v147);
  if ( v143 )
    SamCloseHandle(v143);
  if ( v149 )
    THFreeATTR(v15, v149, 1);
  if ( v150 )
    THFreeATTR(v15, v150, 1);
  if ( v144 )
    THFreeATTR(v15, v144, 1);
  if ( v145 )
    THFreeATTR(v15, v145, 1);
  if ( v139 )
    THFreeATTR(v15, v139, 1);
  if ( ResObj )
  {
    THFreeAux(v15, ResObj, v74, v75, 18483389);
    ResObj = 0;
  }
  if ( pszDest )
  {
    THFreeAux(v15, (_DWORD)pszDest, v74, v75, 18483393);
    pszDest = 0;
  }
  if ( v146 )
  {
    THFreeAux(v15, v146, v74, v75, 18483397);
    v146 = 0;
  }
  if ( v140[0] )
  {
    THFreeAux(v15, v140[0], v74, v75, 18483401);
    v140[0] = 0;
  }
  if ( v141[0] )
  {
    THFreeAux(v15, v141[0], v74, v75, 18483405);
    v141[0] = 0;
  }
  if ( v142[0] )
  {
    THFreeAux(v15, v142[0], v74, v75, 18483409);
    v142[0] = 0;
  }
  if ( v15 && !v135 && gpDsEventConfig )
  {
    if ( v10 || (v76 = 1, RPCKeySize) )
      v76 = 0;
    if ( v76 <= SHIDWORD(gpDsEventConfig[4].Internal) )
      goto LABEL_229;
    if ( !HIDWORD(gpDsEventConfig->Internal) )
      goto LABEL_224;
    if ( v10 || (v77 = 1, RPCKeySize) )
      v77 = 0;
    if ( (unsigned int)DoLogOverride(282, v77) )
    {
LABEL_229:
      v78 = 1073743365;
    }
    else
    {
LABEL_224:
      if ( v10 || RPCKeySize )
      {
        v79 = 1073743364;
        v78 = 1073743365;
      }
      else
      {
        v78 = 1073743365;
        v79 = 1073743365;
      }
      if ( !(unsigned int)DoLogMsgOverride(v79) )
        goto LABEL_250;
    }
    memset_0(&v157, 0, 0x60u);
    v157 = 0;
    Internal = gpDsEventConfig[4].Internal;
    if ( v10 || (v80 = 1, RPCKeySize) )
      v80 = 0;
    v160 = v80;
    if ( v10 || RPCKeySize )
      v78 = 1073743364;
    v158 = v78;
    v161 = 0;
    v162 = 1;
    v168 = &v181;
    v181 = 1;
    if ( v136 )
    {
      v182 = (const wchar_t *)(*(_QWORD *)(v119 + 24) + 56LL);
      v81 = L"?";
    }
    else
    {
      v81 = L"?";
      v182 = L"?";
    }
    v157 = 1;
    if ( v10 || RPCKeySize )
    {
      v183 = 4;
      v185 = v7;
      v81 = (const wchar_t *)&v185;
    }
    else
    {
      v183 = 1;
      if ( v136 )
      {
        v184 = *v129;
LABEL_245:
        v157 = 2;
        v186 = 3;
        v82 = RPCKeySize;
        if ( v10 )
          v82 = v10;
        v188 = v82;
        v187 = &v188;
        v157 = 3;
        v189 = 10;
        if ( v10 )
          RPCKeySize = v10;
        v191 = RPCKeySize;
        v190 = &v191;
        v157 = 4;
        v165 = 0;
        v164 = 282;
        v163 = 1;
        v166 = 0;
        v167 = 0;
        DoLogEventAndTrace(&v157);
        goto LABEL_250;
      }
    }
    v184 = v81;
    goto LABEL_245;
  }
LABEL_250:
  v83 = (_QWORD *)v119;
  if ( v119 )
  {
    v84 = *(_QWORD *)(v119 + 24);
    if ( v84 )
    {
      THFreeAux(v15, v84, v74, v75, 18483439);
      v83[3] = 0;
    }
    v85 = v83[5];
    if ( v85 )
    {
      THFreeAux(v15, v85, v74, v75, 18483442);
      v83[5] = 0;
    }
    v86 = v83[4];
    if ( v86 )
    {
      THFreeAux(v15, v86, v74, v75, 18483445);
      v83[4] = 0;
    }
    THFreeAux(v15, (_DWORD)v83, v74, v75, 18483447);
    v119 = 0;
  }
  v87 = v129;
  if ( v129 )
  {
    for ( j = 0; ; ++j )
    {
      i = j;
      if ( j >= v125 )
        break;
      v89 = v87[j];
      if ( v89 )
      {
        THFreeAux(v15, (_DWORD)v89, v74, v75, 18483453);
        v129[j] = 0;
        v87 = v129;
      }
    }
    if ( v87 )
      THFreeAux(v15, (_DWORD)v87, v74, v75, 18483456);
    v129 = 0;
  }
  DRS_Complete(v15, 3);
  return v10;
}

```

## disassembly

```asm
0x1802fb900  push    rbx
0x1802fb902  push    rsi
0x1802fb903  push    rdi
0x1802fb904  push    r12
0x1802fb906  push    r13
0x1802fb908  push    r14
0x1802fb90a  push    r15
0x1802fb90c  sub     rsp, 680h
0x1802fb913  mov     rax, cs:__security_cookie
0x1802fb91a  xor     rax, rsp
0x1802fb91d  mov     [rsp+6B8h+var_48], rax
0x1802fb925  mov     rdi, r9
0x1802fb928  mov     r15, r8
0x1802fb92b  mov     [rsp+6B8h+var_600], r8
0x1802fb933  mov     dword ptr [rsp+6B8h+var_588], edx
0x1802fb93a  mov     [rsp+6B8h+var_580], rcx
0x1802fb942  mov     r12, [rsp+6B8h+arg_20]
0x1802fb94a  mov     [rsp+6B8h+var_4D0], rcx
0x1802fb952  mov     [rsp+6B8h+var_4C8], r8
0x1802fb95a  mov     ecx, cs:dwTSindex; dwTlsIndex
0x1802fb960  call    cs:__imp_TlsGetValue
0x1802fb966  mov     [rsp+6B8h+var_630], rax
0x1802fb96e  xor     esi, esi
0x1802fb970  mov     [rsp+6B8h+var_620], esi
0x1802fb977  mov     [rsp+6B8h+var_640], esi
0x1802fb97b  mov     r14d, esi
0x1802fb97e  mov     [rsp+6B8h+var_644], esi
0x1802fb982  mov     [rsp+6B8h+var_638], esi
0x1802fb989  mov     [rsp+6B8h+var_5D0], esi
0x1802fb990  lea     ebx, [rsi+57h]
0x1802fb993  mov     [rsp+6B8h+var_648], ebx
0x1802fb997  mov     [rsp+6B8h+var_61C], esi
0x1802fb99e  mov     [rsp+6B8h+var_5C8], rsi
0x1802fb9a6  mov     [rsp+6B8h+var_5C0], rsi
0x1802fb9ae  mov     [rsp+6B8h+var_5A8], esi
0x1802fb9b5  mov     eax, esi
0x1802fb9b7  mov     [rsp+6B8h+SourceString], rax
0x1802fb9bf  mov     [rsp+6B8h+var_4F8], rax
0x1802fb9c7  xorps   xmm0, xmm0
0x1802fb9ca  movups  xmmword ptr [rsp+6B8h+var_570], xmm0
0x1802fb9d2  movups  xmmword ptr [rsp+6B8h+var_560], xmm0
0x1802fb9da  movups  xmmword ptr [rsp+6B8h+var_550], xmm0
0x1802fb9e2  xorps   xmm1, xmm1
0x1802fb9e5  movups  [rsp+6B8h+var_458], xmm1
0x1802fb9ed  movups  [rsp+6B8h+var_448], xmm1
0x1802fb9f5  movups  [rsp+6B8h+var_438], xmm1
0x1802fb9fd  mov     [rsp+6B8h+var_5F8], esi
0x1802fba04  movups  xmmword ptr [rsp+6B8h+DestinationString.Length], xmm0
0x1802fba0c  mov     [rsp+6B8h+var_540], rsi
0x1802fba14  mov     [rsp+6B8h+var_520], rsi
0x1802fba1c  movups  [rsp+6B8h+var_2A8], xmm0
0x1802fba24  movups  [rsp+6B8h+var_2A8+0Ch], xmm0
0x1802fba2c  movups  [rsp+6B8h+Sid], xmm1
0x1802fba34  movups  [rsp+6B8h+Sid+0Ch], xmm1
0x1802fba3c  movups  [rsp+6B8h+var_288], xmm0
0x1802fba44  movups  [rsp+6B8h+var_288+0Ch], xmm0
0x1802fba4c  mov     [rsp+6B8h+var_598], esi
0x1802fba53  mov     [rsp+6B8h+var_5F4], esi
0x1802fba5a  mov     [rsp+6B8h+var_614], esi
0x1802fba61  lea     r13d, [rsi+1]
0x1802fba65  mov     [rsp+6B8h+var_63C], r13b
0x1802fba6a  mov     [rsp+6B8h+DestinationSidLength], esi
0x1802fba71  mov     [rsp+6B8h+var_5E8], rsi
0x1802fba79  mov     [rsp+6B8h+var_5A4], esi
0x1802fba80  mov     [rsp+6B8h+var_59C], esi
0x1802fba87  mov     [rsp+6B8h+var_5D4], esi
0x1802fba8e  mov     [rsp+6B8h+var_5A0], esi
0x1802fba95  mov     [rsp+6B8h+var_5D8], esi
0x1802fba9c  xor     edx, edx; Val
0x1802fba9e  mov     r8d, 160h; Size
0x1802fbaa4  lea     rcx, [rsp+6B8h+var_428]; void *
0x1802fbaac  call    memset_0
0x1802fbab1  mov     [rsp+6B8h+var_590], esi
0x1802fbab8  xorps   xmm0, xmm0
0x1802fbabb  movups  [rsp+6B8h+var_4E0], xmm0
0x1802fbac3  mov     [rsp+6B8h+var_594], esi
0x1802fbaca  mov     [rsp+6B8h+var_5CC], esi
0x1802fbad1  mov     [rsp+6B8h+var_5B0], rsi
0x1802fbad9  mov     [rsp+6B8h+var_510], rsi
0x1802fbae1  mov     [rsp+6B8h+var_508], rsi
0x1802fbae9  mov     [rsp+6B8h+var_530], rsi
0x1802fbaf1  mov     [rsp+6B8h+var_578], rsi
0x1802fbaf9  mov     [rsp+6B8h+var_538], rsi
0x1802fbb01  mov     [rsp+6B8h+var_628], esi
0x1802fbb08  mov     dword ptr [rsp+6B8h+var_5F0], esi
0x1802fbb0f  mov     [rsp+6B8h+pszDest], rsi
0x1802fbb17  mov     [rsp+6B8h+var_518], 0FFFFFFFFFFFFFFFFh
0x1802fbb23  mov     [rsp+6B8h+var_528], rsi
0x1802fbb2b  mov     [rsp+6B8h+var_608], rsi
0x1802fbb33  lea     r8d, [rsi+3]
0x1802fbb37  mov     rdx, [rsp+6B8h+var_580]
0x1802fbb3f  lea     rcx, [rsp+6B8h+var_630]
0x1802fbb47  call    DRS_Prepare
0x1802fbb4c  mov     rcx, [rsp+6B8h+var_580]
0x1802fbb54  call    drsReferenceContext
0x1802fbb59  nop
0x1802fbb5a  mov     [rdi], r13d
0x1802fbb5d  mov     dword ptr [r12], 20EEh
0x1802fbb65  test    dword ptr [r15], 40000000h
0x1802fbb6c  jz      short loc_1802FBBD0
0x1802fbb6e  mov     [rsp+6B8h+var_614], esi
0x1802fbb75  mov     rax, [rsp+6B8h+var_580]
0x1802fbb7d  test    [rax+394h], r13b
0x1802fbb84  jz      short loc_1802FBB8A
0x1802fbb86  mov     ebx, esi
0x1802fbb88  jmp     short loc_1802FBBB5
0x1802fbb8a  lea     r8, [rsp+6B8h+var_640]
0x1802fbb8f  lea     rdx, [rsp+6B8h+var_614]
0x1802fbb97  call    GetRPCKeySize
0x1802fbb9c  mov     ebx, eax
0x1802fbb9e  test    eax, eax
0x1802fbba0  jnz     short loc_1802FBBB5
0x1802fbba2  cmp     [rsp+6B8h+var_614], 80h
0x1802fbbad  sbb     ebx, ebx
0x1802fbbaf  and     ebx, 216Eh
0x1802fbbb5  mov     edi, ebx
0x1802fbbb7  mov     [rsp+6B8h+var_638], ebx
0x1802fbbbe  mov     [r12], ebx
0x1802fbbc2  mov     [rsp+6B8h+var_648], ebx
0x1802fbbc6  mov     r14d, [rsp+6B8h+var_640]
0x1802fbbcb  jmp     loc_1802FCE41
0x1802fbbd0  cmp     [r15], esi
0x1802fbbd3  jge     short loc_1802FBC0A
0x1802fbbd5  mov     [rsp+6B8h+var_594], r13d
0x1802fbbdd  mov     [rsp+6B8h+var_698], r12
0x1802fbbe2  mov     r9, rdi
0x1802fbbe5  mov     r8, r15
0x1802fbbe8  mov     edx, dword ptr [rsp+6B8h+var_588]
0x1802fbbef  mov     rcx, [rsp+6B8h+var_580]
0x1802fbbf7  call    IDL_DRSInheritSecurityIdentity
0x1802fbbfc  mov     edi, eax
0x1802fbbfe  mov     [rsp+6B8h+var_638], eax
0x1802fbc05  jmp     loc_1802FCE46
0x1802fbc0a  mov     rcx, r15
0x1802fbc0d  call    DRS_MSG_ADDSIDREQ_V1_InputValidate
0x1802fbc12  mov     edi, eax
0x1802fbc14  mov     [rsp+6B8h+var_638], eax
0x1802fbc1b  test    eax, eax
0x1802fbc1d  jz      short loc_1802FBC38
0x1802fbc1f  cmp     eax, 20F5h
0x1802fbc24  jnz     loc_1802FCE46
0x1802fbc2a  mov     edi, ebx
0x1802fbc2c  mov     [rsp+6B8h+var_638], ebx
0x1802fbc33  jmp     loc_1802FCE46
0x1802fbc38  lea     rdx, [rsp+6B8h+var_5C8]
0x1802fbc40  mov     rcx, [r15+8]; pszSrc
0x1802fbc44  call    IsDomainInForest
0x1802fbc49  test    eax, eax
0x1802fbc4b  jz      short loc_1802FBC5D
0x1802fbc4d  mov     ebx, 2156h
0x1802fbc52  mov     r14d, 11A05EDh
0x1802fbc58  jmp     loc_1802FCE39
0x1802fbc5d  lea     rdx, [rsp+6B8h+var_5C0]
0x1802fbc65  mov     rcx, [r15+50h]; pszSrc
0x1802fbc69  call    IsDomainInForest
0x1802fbc6e  test    eax, eax
0x1802fbc70  jnz     short loc_1802FBC82
0x1802fbc72  mov     ebx, 2157h
0x1802fbc77  mov     r14d, 11A05F4h
0x1802fbc7d  jmp     loc_1802FCE39
0x1802fbc82  mov     rcx, cs:qword_18052B2C0
0x1802fbc89  test    rcx, rcx
0x1802fbc8c  jz      loc_1802FCE2E
0x1802fbc92  mov     r15, [rsp+6B8h+var_5C0]
0x1802fbc9a  mov     rdx, [r15]
0x1802fbc9d  call    NameMatched
0x1802fbca2  test    eax, eax
0x1802fbca4  jz      loc_1802FCE2E
0x1802fbcaa  mov     rax, [r15]
0x1802fbcad  cmp     [rax+4], esi
0x1802fbcb0  jz      loc_1802FCE21
0x1802fbcb6  cmp     [r15+18h], rsi
0x1802fbcba  jz      loc_1802FCE21
0x1802fbcc0  call    VerifyAuditingEnabled
0x1802fbcc5  mov     ebx, eax
0x1802fbcc7  mov     [rsp+6B8h+var_648], eax
0x1802fbccb  test    eax, eax
0x1802fbccd  jz      short loc_1802FBCE2
0x1802fbccf  mov     [r12], eax
0x1802fbcd3  mov     [rsp+6B8h+var_648], eax
0x1802fbcd7  mov     r14d, 11A060Ah
0x1802fbcdd  jmp     loc_1802FCE41
0x1802fbce2  mov     rdx, [r15]
0x1802fbce5  add     rdx, 18h
0x1802fbce9  lea     r8, [rsp+6B8h+var_5A8]
0x1802fbcf1  mov     r15, [rsp+6B8h+var_630]
0x1802fbcf9  mov     rcx, r15
0x1802fbcfc  call    VerifyCallerIsDomainAdminOrLocalAdmin
0x1802fbd01  mov     ebx, eax
0x1802fbd03  mov     [rsp+6B8h+var_648], eax
0x1802fbd07  test    eax, eax
0x1802fbd09  jz      short loc_1802FBD23
0x1802fbd0b  mov     r14d, 11A0614h
0x1802fbd11  mov     [r12], eax
0x1802fbd15  mov     [rsp+6B8h+var_648], eax
0x1802fbd19  mov     [rsp+6B8h+var_644], r14d
0x1802fbd1e  jmp     loc_1802FCE4E
0x1802fbd23  cmp     [rsp+6B8h+var_5A8], esi
0x1802fbd2a  jnz     short loc_1802FBD72
0x1802fbd2c  mov     rax, [rsp+6B8h+var_5C0]
0x1802fbd34  mov     r8, [rax]
0x1802fbd37  add     r8, 18h
0x1802fbd3b  mov     rax, [rax+18h]
0x1802fbd3f  mov     [rsp+6B8h+var_698], rax
0x1802fbd44  mov     rax, [rsp+6B8h+var_600]
0x1802fbd4c  mov     r9, [rax+58h]
0x1802fbd50  mov     rdx, [rax+8]
0x1802fbd54  mov     rcx, [rax+10h]
0x1802fbd58  call    ForceFailureAuditOnDstDom
0x1802fbd5d  mov     ebx, 2098h
0x1802fbd62  mov     [r12], ebx
0x1802fbd66  mov     [rsp+6B8h+var_648], ebx
0x1802fbd6a  mov     r14d, 11A061Fh
0x1802fbd70  jmp     short loc_1802FBD19
0x1802fbd72  mov     rcx, [rsp+6B8h+var_5C0]
0x1802fbd7a  mov     rcx, [rcx]
0x1802fbd7d  add     rcx, 18h
0x1802fbd81  lea     rdx, [rsp+6B8h+var_63C]
0x1802fbd86  call    cs:__imp_SamIMixedDomain2
0x1802fbd8c  mov     [rsp+6B8h+var_5DC], eax
0x1802fbd93  test    eax, eax
0x1802fbd95  jns     short loc_1802FBDAC
0x1802fbd97  mov     ecx, eax; Status
0x1802fbd99  call    cs:__imp_RtlNtStatusToDosError
0x1802fbd9f  mov     ebx, eax
0x1802fbda1  mov     r14d, 11A0628h
0x1802fbda7  jmp     loc_1802FBD11
0x1802fbdac  cmp     [rsp+6B8h+var_63C], sil
0x1802fbdb1  jz      short loc_1802FBDCB
0x1802fbdb3  mov     ebx, 2130h
0x1802fbdb8  mov     [r12], ebx
0x1802fbdbc  mov     [rsp+6B8h+var_648], ebx
0x1802fbdc0  mov     r14d, 11A062Dh
0x1802fbdc6  jmp     loc_1802FBD19
0x1802fbdcb  mov     rbx, [rsp+6B8h+var_600]
0x1802fbdd3  mov     rax, [rbx+18h]
0x1802fbdd7  mov     [rsp+6B8h+SourceString], rax
0x1802fbddf  test    rax, rax
0x1802fbde2  jz      loc_1802FBF80
0x1802fbde8  mov     [rsp+6B8h+var_4F8], rax
0x1802fbdf0  cmp     [rbx+20h], esi
0x1802fbdf3  jz      short loc_1802FBE5C
0x1802fbdf5  mov     ecx, [rbx+20h]
0x1802fbdf8  mov     rdx, r13
0x1802fbdfb  call    DsaSafeAdd
0x1802fbe00  mov     ecx, eax
0x1802fbe02  mov     edx, 2
0x1802fbe07  call    DsaSafeMult
0x1802fbe0c  mov     r8d, eax
0x1802fbe0f  mov     dword ptr [rsp+6B8h+var_690], 11A0647h
0x1802fbe17  mov     dword ptr [rsp+6B8h+var_698], esi
0x1802fbe1b  mov     r9d, r13d
0x1802fbe1e  mov     rdx, r13
0x1802fbe21  mov     rcx, r15
0x1802fbe24  call    THAlloc_
0x1802fbe29  mov     [rsp+6B8h+var_570], rax
0x1802fbe31  mov     ecx, [rbx+20h]
0x1802fbe34  mov     edx, 2
0x1802fbe39  call    DsaSafeMult
0x1802fbe3e  mov     r8d, eax; Size
0x1802fbe41  mov     rdx, [rbx+28h]; Src
0x1802fbe45  mov     rcx, [rsp+6B8h+var_570]; void *
0x1802fbe4d  call    memcpy_0
0x1802fbe52  mov     eax, [rbx+20h]
0x1802fbe55  mov     dword ptr [rsp+6B8h+var_570+8], eax
0x1802fbe5c  cmp     [rbx+30h], esi
0x1802fbe5f  jz      short loc_1802FBEC8
0x1802fbe61  mov     ecx, [rbx+30h]
0x1802fbe64  mov     rdx, r13
0x1802fbe67  call    DsaSafeAdd
0x1802fbe6c  mov     ecx, eax
0x1802fbe6e  mov     edx, 2
0x1802fbe73  call    DsaSafeMult
0x1802fbe78  mov     r8d, eax
0x1802fbe7b  mov     dword ptr [rsp+6B8h+var_690], 11A064Dh
0x1802fbe83  mov     dword ptr [rsp+6B8h+var_698], esi
0x1802fbe87  mov     r9d, r13d
0x1802fbe8a  mov     rdx, r13
0x1802fbe8d  mov     rcx, r15
0x1802fbe90  call    THAlloc_
0x1802fbe95  mov     [rsp+6B8h+var_560], rax
0x1802fbe9d  mov     ecx, [rbx+30h]
0x1802fbea0  mov     edx, 2
0x1802fbea5  call    DsaSafeMult
0x1802fbeaa  mov     r8d, eax; Size
0x1802fbead  mov     rdx, [rbx+38h]; Src
0x1802fbeb1  mov     rcx, [rsp+6B8h+var_560]; void *
0x1802fbeb9  call    memcpy_0
0x1802fbebe  mov     eax, [rbx+30h]
0x1802fbec1  mov     dword ptr [rsp+6B8h+var_560+8], eax
0x1802fbec8  cmp     [rbx+40h], esi
0x1802fbecb  jz      short loc_1802FBF34
0x1802fbecd  mov     ecx, [rbx+40h]
0x1802fbed0  mov     rdx, r13
0x1802fbed3  call    DsaSafeAdd
0x1802fbed8  mov     ecx, eax
0x1802fbeda  mov     edx, 2
0x1802fbedf  call    DsaSafeMult
0x1802fbee4  mov     r8d, eax
0x1802fbee7  mov     dword ptr [rsp+6B8h+var_690], 11A0653h
  ... truncated ...
```
