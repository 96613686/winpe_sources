# LsapAuBuildTokenInfoAndAddLocalAliases(_LSA_TOKEN_INFORMATION_TYPE,void *,ulong,ulong,_SID_AND_ATTRIBUTES *,ulong,_SID_AND_ATTRIBUTES *,_LSA_TOKEN_INFORMATION_V3 * *,ulong *,int,int,int *)

- ea: `0x18001531c`
- end: `0x18001624b`
- name: `?LsapAuBuildTokenInfoAndAddLocalAliases@@YAJW4_LSA_TOKEN_INFORMATION_TYPE@@PEAXKKPEAU_SID_AND_ATTRIBUTES@@K2PEAPEAU_LSA_TOKEN_INFORMATION_V3@@PEAKHHPEAH@Z`
- size: `3887`
- prototype: `__int64 __fastcall(enum _LSA_TOKEN_INFORMATION_TYPE, void *, unsigned int, unsigned int, struct _SID_AND_ATTRIBUTES *, unsigned int, struct _SID_AND_ATTRIBUTES *, struct _LSA_TOKEN_INFORMATION_V3 **, unsigned int *, int, int, int *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180059a94`

## callees

- `0x180009330`
- `0x18000c300`
- `0x180011278`
- `0x180014954`
- `0x1800149e0`
- `0x180014e94`
- `0x18001531c`
- `0x180016254`
- `0x1800162a8`
- `0x180016f70`
- `0x18003a848`
- `0x180088030`
- `0x180089d24`
- `0x180097568`
- `0x1800b1f9c`
- `0x1800b86d0`
- `0x1800bbbfc`
- `0x18012cf40`
- `0x18014a6b0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016044`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001562c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001562c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015a84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015a99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015cdb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800161e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800161fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016219`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015a84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015a99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015cdb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800161e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800161fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016219`
- `ntdll!RtlQueryInformationAcl` at `0x18001582a`
- `ntdll!RtlQueryInformationAcl` at `0x18001582a`
- `ntdll!RtlCopySid` at `0x1800158ea`
- `ntdll!RtlCopySid` at `0x1800158ea`
- `ntdll!RtlSubAuthorityCountSid` at `0x180015644`
- `ntdll!RtlSubAuthorityCountSid` at `0x180015d08`
- `ntdll!RtlSubAuthorityCountSid` at `0x180015644`
- `ntdll!RtlSubAuthorityCountSid` at `0x180015d08`
- `ntdll!RtlSubAuthoritySid` at `0x180015c24`
- `ntdll!RtlSubAuthoritySid` at `0x180015c3e`
- `ntdll!RtlSubAuthoritySid` at `0x180015d1c`
- `ntdll!RtlSubAuthoritySid` at `0x180015e44`
- `ntdll!RtlSubAuthoritySid` at `0x180015e62`
- `ntdll!RtlSubAuthoritySid` at `0x180015c24`
- `ntdll!RtlSubAuthoritySid` at `0x180015c3e`
- `ntdll!RtlSubAuthoritySid` at `0x180015d1c`
- `ntdll!RtlSubAuthoritySid` at `0x180015e44`
- `ntdll!RtlSubAuthoritySid` at `0x180015e62`
- `ntdll!RtlIdentifierAuthoritySid` at `0x180015bf4`
- `ntdll!RtlIdentifierAuthoritySid` at `0x180015bf4`
- `ntdll!RtlInitializeSid` at `0x180015e2f`
- `ntdll!RtlInitializeSid` at `0x180015e2f`
- `ntdll!RtlLengthRequiredSid` at `0x180015baa`
- `ntdll!RtlLengthRequiredSid` at `0x180015baa`
- `ntdll!RtlLengthSid` at `0x1800156b2`
- `ntdll!RtlLengthSid` at `0x1800157bf`
- `ntdll!RtlLengthSid` at `0x180015b96`
- `ntdll!RtlLengthSid` at `0x180015bcd`
- `ntdll!RtlLengthSid` at `0x180015e8a`
- `ntdll!RtlLengthSid` at `0x1800160a8`
- `ntdll!RtlLengthSid` at `0x1800156b2`
- `ntdll!RtlLengthSid` at `0x1800157bf`
- `ntdll!RtlLengthSid` at `0x180015b96`
- `ntdll!RtlLengthSid` at `0x180015bcd`
- `ntdll!RtlLengthSid` at `0x180015e8a`
- `ntdll!RtlLengthSid` at `0x1800160a8`
- `ntdll!RtlEqualSid` at `0x180015672`
- `ntdll!RtlEqualSid` at `0x180015697`
- `ntdll!RtlEqualSid` at `0x180015c8c`
- `ntdll!RtlEqualSid` at `0x180015eba`
- `ntdll!RtlEqualSid` at `0x180015672`
- `ntdll!RtlEqualSid` at `0x180015697`
- `ntdll!RtlEqualSid` at `0x180015c8c`
- `ntdll!RtlEqualSid` at `0x180015eba`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180015caa`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180015caa`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIGetAliasMembership` at `0x180015531`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIGetAliasMembership` at `0x1800155c3`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIGetAliasMembership` at `0x180015531`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIGetAliasMembership` at `0x1800155c3`

## pseudocode

```c
__int64 __fastcall LsapAuBuildTokenInfoAndAddLocalAliases(
        enum _LSA_TOKEN_INFORMATION_TYPE a1,
        _QWORD *a2,
        int a3,
        unsigned int a4,
        struct _SID_AND_ATTRIBUTES *a5,
        unsigned int a6,
        struct _SID_AND_ATTRIBUTES *a7,
        struct _LSA_TOKEN_INFORMATION_V3 **a8,
        unsigned int *a9,
        int a10,
        int a11,
        int *a12)
{
  unsigned int *v12; // r15
  PSID v13; // rsi
  __int64 v14; // r12
  _QWORD *v15; // r14
  __int64 result; // rax
  __int64 v17; // rdx
  struct _SID_AND_ATTRIBUTES *v18; // r8
  __int64 v19; // r9
  __int64 v20; // rdi
  unsigned __int64 v21; // rbx
  unsigned __int64 v22; // rcx
  __int64 v23; // rcx
  unsigned __int64 v24; // rcx
  void *v25; // rsp
  void *v26; // rsp
  unsigned __int64 v27; // rcx
  struct _SID_AND_ATTRIBUTES *v28; // rax
  void *v29; // rdi
  __int64 v30; // rdx
  __int64 v31; // rcx
  int AliasMembership; // ebx
  _DWORD *v33; // r8
  void *v34; // rbx
  unsigned int v35; // edx
  LPVOID Value; // rax
  PUCHAR v37; // rax
  ULONG v38; // eax
  unsigned int v39; // ecx
  unsigned int v40; // r12d
  unsigned int v41; // r11d
  void *v42; // rdx
  unsigned int v43; // r14d
  unsigned __int64 v44; // rdi
  unsigned __int64 v45; // rbx
  unsigned __int64 v46; // rsi
  unsigned int v47; // eax
  int v48; // ecx
  ULONG v49; // eax
  ULONG v50; // r14d
  NTSTATUS v51; // esi
  ULONG v52; // r13d
  unsigned int v53; // ebx
  unsigned int v54; // r12d
  struct _SID_AND_ATTRIBUTES *v55; // r13
  unsigned int v56; // edi
  __int64 j; // rbx
  struct _ACL *v58; // rcx
  unsigned int v59; // r12d
  __int64 v60; // rax
  struct _LSA_TOKEN_INFORMATION_V3 *v61; // rdi
  void **v62; // r14
  char *v63; // rax
  char *v64; // rdx
  unsigned int v65; // ecx
  struct _TOKEN_GROUPS *v66; // rdx
  int v67; // eax
  SID_AND_ATTRIBUTES *v68; // rbx
  struct _SID_AND_ATTRIBUTES *v69; // r8
  int v70; // edx
  PTOKEN_GROUPS Groups; // rcx
  __int64 v72; // r9
  struct _SID_AND_ATTRIBUTES *v73; // rax
  int *v74; // rbx
  struct _SID_AND_ATTRIBUTES *v75; // rax
  unsigned __int64 v76; // rax
  struct _SID_AND_ATTRIBUTES *v77; // rbx
  struct _TOKEN_PRIVILEGES *v78; // rbx
  LsaHandleCache *v79; // rcx
  char *v80; // rbx
  struct _TOKEN_GROUPS *v81; // r8
  ULONG v82; // edi
  ULONG v83; // r13d
  PSID_IDENTIFIER_AUTHORITY v84; // rax
  int v85; // ecx
  DWORD LastError; // ebx
  __int64 v87; // r8
  __int64 v88; // r9
  bool v89; // sf
  PUCHAR v90; // rax
  __int64 v91; // r9
  __int64 v92; // r8
  int v93; // eax
  __int64 v94; // r8
  _DWORD *v95; // rdx
  unsigned int RpcPackageId; // eax
  ULONG v97; // ebx
  PULONG v98; // rax
  ULONG v99; // eax
  __int64 i; // r8
  _DWORD *v101; // rax
  _DWORD *v102; // rax
  unsigned int *v103; // rax
  unsigned __int8 IsRunning; // al
  int v105; // eax
  int v106; // eax
  unsigned int v107; // ebx
  struct _SID_AND_ATTRIBUTES *v108; // r12
  char *v109; // rbx
  __int64 v110; // rcx
  __int64 v111; // [rsp+0h] [rbp-70h] BYREF
  unsigned int v112; // [rsp+70h] [rbp+0h] BYREF
  unsigned int v113; // [rsp+74h] [rbp+4h]
  int v114; // [rsp+78h] [rbp+8h] BYREF
  struct _SID_AND_ATTRIBUTES *v115; // [rsp+80h] [rbp+10h] BYREF
  int v116; // [rsp+88h] [rbp+18h]
  HLOCAL v117[2]; // [rsp+90h] [rbp+20h] BYREF
  HLOCAL hMem[2]; // [rsp+A0h] [rbp+30h] BYREF
  HLOCAL v119[2]; // [rsp+B0h] [rbp+40h] BYREF
  HLOCAL v120[2]; // [rsp+C0h] [rbp+50h] BYREF
  enum _LSA_TOKEN_INFORMATION_TYPE v121; // [rsp+D0h] [rbp+60h]
  struct _RTL_BALANCED_NODE *v122; // [rsp+D8h] [rbp+68h] BYREF
  struct _SID_AND_ATTRIBUTES *v123; // [rsp+E0h] [rbp+70h]
  void *v124; // [rsp+E8h] [rbp+78h]
  LPWSTR StringSid; // [rsp+F0h] [rbp+80h] BYREF
  int v126; // [rsp+F8h] [rbp+88h]
  PSID Sid; // [rsp+100h] [rbp+90h] BYREF
  __int128 v128; // [rsp+108h] [rbp+98h] BYREF
  __int128 v129; // [rsp+118h] [rbp+A8h] BYREF
  int *v130; // [rsp+128h] [rbp+B8h]
  struct _LSA_TOKEN_INFORMATION_V3 **v131; // [rsp+130h] [rbp+C0h]
  unsigned int *v132; // [rsp+138h] [rbp+C8h]
  __int128 v133; // [rsp+140h] [rbp+D0h] BYREF
  __int128 v134; // [rsp+150h] [rbp+E0h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY DestinationSidLength; // [rsp+160h] [rbp+F0h] BYREF
  __int64 Information; // [rsp+168h] [rbp+F8h] BYREF
  int v137; // [rsp+170h] [rbp+100h]
  _BYTE v138[72]; // [rsp+178h] [rbp+108h] BYREF
  WCHAR SubKey[264]; // [rsp+1C0h] [rbp+150h] BYREF

  v12 = 0;
  v126 = a3;
  v13 = a5->Sid;
  v131 = a8;
  v132 = a9;
  v115 = a5;
  v14 = a4;
  v113 = a4;
  *a12 = 0;
  v121 = a1;
  v123 = a7;
  v130 = a12;
  Sid = 0;
  v122 = 0;
  v112 = 0;
  LODWORD(Information) = 0;
  WORD2(Information) = 1280;
  *(_OWORD *)hMem = 0;
  *(_OWORD *)v117 = 0;
  *(_OWORD *)v119 = 0;
  *(_OWORD *)v120 = 0;
  v128 = 0;
  v129 = 0;
  if ( (unsigned int)(a1 - 1) <= 1 || (v124 = 0, v15 = 0, a1 == LsaTokenInformationV3) )
  {
    v15 = a2;
    v124 = a2;
  }
  result = LsapWaitForSamForAwhile();
  if ( (int)result >= 0 )
  {
    v20 = (unsigned int)v14 + a6;
    v21 = 8 * v20;
    if ( !(8 * v20) )
      goto LABEL_192;
    if ( v21 > g_ulMaxStackAllocSize )
      goto LABEL_192;
    v22 = v21 + g_ulAdditionalProbeSize + 8;
    if ( v22 < v21 || !(unsigned int)VerifyStackAvailable(v22, v17, v18, v19) )
      goto LABEL_192;
    v23 = v21 + 23;
    if ( v21 + 23 <= v21 + 8 )
      v23 = 0xFFFFFFFFFFFFFF0LL;
    v24 = v23 & 0xFFFFFFFFFFFFFFF0uLL;
    v25 = alloca(v24);
    v26 = alloca(v24);
    v12 = &v112;
    if ( &v111 == (__int64 *)-112LL || (v112 = 1801679955, (v12 = (unsigned int *)&v114) == 0) )
    {
LABEL_192:
      if ( v21 + 8 >= v21 )
      {
        v103 = (unsigned int *)((__int64 (*)(void))g_pfnAllocate)();
        v12 = v103;
        if ( v103 )
        {
          *v103 = 1885431112;
          v12 = v103 + 2;
        }
      }
    }
    if ( !v12 )
      return 3221225495LL;
    v27 = 0;
    if ( (_DWORD)v20 )
    {
      v18 = v115;
      do
      {
        v17 = (unsigned int)v27;
        if ( (unsigned int)v27 >= (unsigned int)v14 )
          v28 = &a7[(unsigned int)(v27 - v14)];
        else
          v28 = &v18[(unsigned int)v27];
        *(_QWORD *)&v12[2 * v27] = v28->Sid;
        v27 = (unsigned int)(v27 + 1);
      }
      while ( (unsigned int)v27 < (unsigned int)v20 );
    }
    LODWORD(v128) = v14;
    *((_QWORD *)&v128 + 1) = v12;
    if ( a7 )
    {
      v27 = (unsigned __int64)&v12[2 * v14];
      *((_QWORD *)&v129 + 1) = v27;
      LODWORD(v129) = a6;
    }
    if ( LsapProductType != NtProductLanManNt
      || (IsRunning = LsapSamExtDsIsRunning(), v29 = LsapLocalAccountDomainHandle, IsRunning) )
    {
      v29 = LsapAccountDomainHandle;
    }
    LODWORD(hMem[0]) = 0;
    hMem[1] = 0;
    LODWORD(v119[0]) = 0;
    v119[1] = 0;
    if ( (unsigned __int8)IsSamIDecodeClaimsBlobPresent(v27, v17, v18) )
    {
      AliasMembership = SamIGetAliasMembership(v29, &v128, hMem);
      if ( AliasMembership >= 0 )
      {
        if ( !a7
          || (AliasMembership = LsapSamExtGetAliasMembership(
                                  v29,
                                  (struct _SAMPR_PSID_ARRAY *)&v129,
                                  (struct _SAMPR_ULONG_ARRAY *)v119),
              AliasMembership >= 0) )
        {
          if ( a10 )
          {
            v105 = (int)hMem[0];
            v30 = LODWORD(hMem[0]);
            if ( LODWORD(hMem[0]) )
            {
              v33 = hMem[1];
              do
              {
                v30 = (unsigned int)(v30 - 1);
                if ( v33[v30] > 0x3E8u )
                {
                  v33[v30] = v33[v105 - 1];
                  v33 = hMem[1];
                  v105 = --LODWORD(hMem[0]);
                }
              }
              while ( (_DWORD)v30 );
            }
            if ( a7 )
            {
              v106 = (int)v119[0];
              v30 = LODWORD(v119[0]);
              if ( LODWORD(v119[0]) )
              {
                v33 = v119[1];
                do
                {
                  v30 = (unsigned int)(v30 - 1);
                  if ( v33[v30] > 0x3E8u )
                  {
                    v33[v30] = v33[v106 - 1];
                    v33 = v119[1];
                    v106 = --LODWORD(v119[0]);
                  }
                }
                while ( (_DWORD)v30 );
              }
            }
          }
          v34 = LsapBuiltinDomainHandle;
          LODWORD(v117[0]) = 0;
          v117[1] = 0;
          LODWORD(v120[0]) = 0;
          v120[1] = 0;
          if ( (unsigned __int8)IsSamIDecodeClaimsBlobPresent(v31, v30, v33) )
          {
            AliasMembership = SamIGetAliasMembership(v34, &v128, v117);
            if ( AliasMembership >= 0 )
            {
              if ( !a7
                || (AliasMembership = LsapSamExtGetAliasMembership(
                                        LsapBuiltinDomainHandle,
                                        (struct _SAMPR_PSID_ARRAY *)&v129,
                                        (struct _SAMPR_ULONG_ARRAY *)v120),
                    AliasMembership >= 0) )
              {
                v35 = (unsigned int)v117[0];
                v114 = 0;
                v116 = 0;
                if ( a10 )
                {
                  LODWORD(v92) = v117[0];
                  if ( LODWORD(v117[0]) )
                  {
                    do
                    {
                      v92 = (unsigned int)(v92 - 1);
                      if ( *((_DWORD *)v117[1] + v92) > 0x3E8u )
                      {
                        *((_DWORD *)v117[1] + v92) = *((_DWORD *)v117[1] + v35 - 1);
                        v35 = --LODWORD(v117[0]);
                      }
                    }
                    while ( (_DWORD)v92 );
                  }
                  if ( a7 )
                  {
                    v93 = (int)v120[0];
                    LODWORD(v94) = v120[0];
                    if ( LODWORD(v120[0]) )
                    {
                      v95 = v120[1];
                      do
                      {
                        v94 = (unsigned int)(v94 - 1);
                        if ( v95[v94] > 0x3E8u )
                        {
                          v95[v94] = v95[v93 - 1];
                          v95 = v120[1];
                          v93 = --LODWORD(v120[0]);
                        }
                      }
                      while ( (_DWORD)v94 );
                      v35 = (unsigned int)v117[0];
                    }
                  }
                }
                if ( a11 )
                {
                  for ( i = 0; (unsigned int)i < v35; i = (unsigned int)(i + 1) )
                  {
                    if ( *((_DWORD *)v117[1] + i) == 544 )
                    {
                      v116 = 1;
                      break;
                    }
                  }
                }
                Value = TlsGetValue(dwThreadPackage);
                if ( Value )
                {
                  RpcPackageId = SpmpGetRpcPackageId((unsigned __int64)Value);
                  v97 = RpcPackageId;
                  if ( RpcPackageId )
                  {
                    if ( RpcPackageId != 0xFFFF && RpcPackageId != 16 )
                    {
                      *(_DWORD *)DestinationSidLength.Value = 0;
                      Sid = v138;
                      *(_WORD *)&DestinationSidLength.Value[4] = 1280;
                      RtlInitializeSid(v138, &DestinationSidLength, 2u);
                      *RtlSubAuthoritySid(v138, 0) = 64;
                      v98 = RtlSubAuthoritySid(v138, 1u);
                      v114 = 1;
                      *v98 = v97;
                    }
                  }
                }
                v37 = RtlSubAuthorityCountSid(v13);
                if ( a11 )
                {
                  if ( *v37 )
                  {
                    v90 = RtlSubAuthorityCountSid(v13);
                    v91 = *RtlSubAuthoritySid(v13, (unsigned int)*v90 - 1);
                  }
                  else
                  {
                    v91 = 0;
                  }
                  RtlStringCchPrintfW(SubKey, 0x104u, L"%d", v91);
                  v51 = LsapReadInstallationProviderGroups(SubKey, &v112, (void **)&v122);
                  v89 = v51 < 0;
                }
                else
                {
                  if ( *v37 )
                  {
                    v84 = RtlIdentifierAuthoritySid(v13);
                    v85 = *(_DWORD *)v84->Value - Information;
                    if ( *(_DWORD *)v84->Value == (_DWORD)Information )
                      v85 = *(unsigned __int16 *)&v84->Value[4] - WORD2(Information);
                    if ( !v85 && *RtlSubAuthoritySid(v13, 0) >= 0x50 && *RtlSubAuthoritySid(v13, 0) <= 0x6F )
                    {
                      v51 = LsapQueryInstallationProviderGroupsForVirtualAccount(v13, &v112, (void **)&v122);
                      if ( v51 < 0 )
                        goto LABEL_83;
LABEL_38:
                      v38 = RtlLengthSid(v115->Sid);
                      v39 = 88;
                      v40 = v38;
                      *(_DWORD *)DestinationSidLength.Value = v38;
                      if ( v121 == LsaTokenInformationV3 && v15 )
                      {
                        v101 = (_DWORD *)v15[8];
                        if ( v101 )
                          v39 = ((*v101 + 23) & 0xFFFFFFF8) + 88;
                        v102 = (_DWORD *)v15[9];
                        if ( v102 )
                          v39 += (*v102 + 23) & 0xFFFFFFF8;
                      }
                      v41 = v113;
                      v42 = (void *)LODWORD(hMem[0]);
                      v43 = v39 + 16 * (v114 + v112 + LODWORD(hMem[0]) + LODWORD(v117[0]) + v113 + v116) - 8;
                      if ( a7 )
                        v43 = 16 * (a6 + LODWORD(v120[0]) + LODWORD(v119[0]))
                            + v39
                            + 16 * (v114 + v112 + LODWORD(hMem[0]) + LODWORD(v117[0]) + v113 + v116);
                      if ( (unsigned int)(LODWORD(v119[0]) + LODWORD(hMem[0])) < LODWORD(hMem[0]) )
                        goto LABEL_82;
                      v44 = LsapAccountDomainMemberSidLength
                          * (unsigned __int64)(unsigned int)(LODWORD(v119[0]) + LODWORD(hMem[0]));
                      if ( v44 > 0xFFFFFFFF )
                        goto LABEL_82;
                      if ( (unsigned int)(LODWORD(v120[0]) + LODWORD(v117[0])) < LODWORD(v117[0]) )
                        goto LABEL_82;
                      v45 = LsapBuiltinDomainMemberSidLength
                          * (unsigned __int64)(unsigned int)(LODWORD(v120[0]) + LODWORD(v117[0]));
                      if ( v45 > 0xFFFFFFFF )
                        goto LABEL_82;
                      v46 = 44LL * v112;
                      if ( v46 > 0xFFFFFFFF )
                        goto LABEL_82;
                      if ( v116 )
                      {
                        v99 = RtlLengthSid(*((PSID *)WellKnownSids + 396));
                        LODWORD(v45) = v99 + v45;
                        if ( (unsigned int)v45 < v99 )
                          goto LABEL_82;
                        v41 = v113;
                      }
                      v47 = v44 + v45;
                      if ( (int)v44 + (int)v45 >= (unsigned int)v44 )
                      {
                        v48 = v46 + v47;
                        if ( (unsigned int)v46 + v47 >= v47 )
                        {
                          v49 = v48 + v40;
                          if ( v48 + v40 >= v40 )
                          {
                            v50 = v49 + v43;
                            if ( v50 >= v49 )
                            {
                              v51 = 0;
                              v52 = 0;
                              v53 = 1;
                              if ( v41 > 1 )
                              {
                                v54 = v113;
                                v55 = v115;
                                do
                                  v50 += RtlLengthSid(v55[v53++].Sid);
                                while ( v53 < v54 );
                                v40 = *(_DWORD *)DestinationSidLength.Value;
                                v52 = 0;
                              }
                              if ( v123 )
                              {
                                v107 = 0;
                                if ( a6 )
                                {
                                  v108 = v123;
                                  do
                                    v50 += RtlLengthSid(v108[v107++].Sid);
                                  while ( v107 < a6 );
                                  v40 = *(_DWORD *)DestinationSidLength.Value;
                                }
                              }
                              v56 = v114;
                              for ( j = 0; (unsigned int)j < v56; j = (unsigned int)(j + 1) )
                                v50 += RtlLengthSid(*(&Sid + j));
                              if ( !v124 )
                                goto LABEL_62;
                              v58 = (struct _ACL *)*((_QWORD *)v124 + 7);
                              if ( !v58 )
                              {
                                v82 = LsapBuiltinDomainMemberSidLength;
                                if ( v40 > LsapBuiltinDomainMemberSidLength )
                                  v82 = v40;
                                v83 = RtlLengthSid(*((PSID *)WellKnownSids + 90));
                                v52 = RtlLengthRequiredSid(3u) + v82 + v83 + 32;
                                goto LABEL_61;
                              }
                              Information = 0;
                              v137 = 0;
                              v51 = RtlQueryInformationAcl(v58, &Information, 0xCu, AclSizeInformation);
                              if ( v51 >= 0 )
                              {
                                v52 = v137 + HIDWORD(Information);
LABEL_61:
                                v50 = v52 + ((v50 + 1) & 0xFFFFFFFE);
LABEL_62:
                                v59 = ((v50 + 3) & 0xFFFFFFFC) + 796;
                                v60 = LsapAllocate(v59);
                                v61 = (struct _LSA_TOKEN_INFORMATION_V3 *)v60;
                                if ( v60 )
                                {
                                  v62 = (void **)v124;
                                  v63 = (char *)(v60 + 88);
                                  if ( v124 && v121 == LsaTokenInformationV3 )
                                  {
                                    if ( *((_QWORD *)v124 + 8) )
                                    {
                                      v109 = (char *)((unsigned __int64)(v63 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
                                      v61->UserClaims.UserClaims = v109;
                                      LsapDuplicateClaimsBlob(v109, v62[8]);
                                      v63 = &v109[((*(unsigned int *)v62[8] + 7LL) & 0xFFFFFFFFFFFFFFF8uLL) + 16];
                                    }
                                    v64 = v63;
                                    if ( v62[9] )
                                    {
                                      v80 = (char *)((unsigned __int64)(v63 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
                                      v61->DeviceClaims.DeviceClaims = v80;
                                      LsapDuplicateClaimsBlob(v80, v62[9]);
                                      v64 = &v80[((*(unsigned int *)v62[9] + 7LL) & 0xFFFFFFFFFFFFFFF8uLL) + 16];
                                    }
                                  }
                                  else
                                  {
                                    v64 = v63;
                                  }
                                  v65 = v116 + v113;
                                  v66 = (struct _TOKEN_GROUPS *)((unsigned __int64)(v64 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
                                  v67 = v114;
                                  v61->Groups = v66;
                                  v66->GroupCount = v112 + LODWORD(hMem[0]) + LODWORD(v117[0]) + v65 + v67 - 1;
                                  v68 = &v61->Groups->Groups[v61->Groups->GroupCount];
                                  if ( v123 )
                                  {
                                    v81 = (struct _TOKEN_GROUPS *)(((unsigned __int64)&v68->Sid + 7)
                                                                 & 0xFFFFFFFFFFFFFFF8uLL);
                                    v61->DeviceGroups = v81;
                                    v81->GroupCount = a6 + LODWORD(v119[0]) + LODWORD(v120[0]);
                                    v68 = &v61->DeviceGroups->Groups[v61->DeviceGroups->GroupCount];
                                  }
                                  else
                                  {
                                    v61->DeviceGroups = 0;
                                  }
                                  RtlCopySid(*(ULONG *)DestinationSidLength.Value, v68, v115->Sid);
                                  v69 = v115;
                                  v70 = v126;
                                  Groups = v61->Groups;
                                  v72 = v113 - 1;
                                  v61->User.User.Sid = v68;
                                  v61->User.User.Attributes = v69->Attributes;
                                  v73 = (SID_AND_ATTRIBUTES *)((char *)v68 + *(unsigned int *)DestinationSidLength.Value);
                                  v133 = *(_OWORD *)v117;
                                  v74 = v130;
                                  v115 = v73;
                                  v134 = *(_OWORD *)hMem;
                                  LsapAuMarshalSIDsToTokenInfo(
                                    Groups->Groups,
                                    &v115,
                                    &v69[1],
                                    v72,
                                    v70 - 1,
                                    &v134,
                                    &v133,
                                    &Sid,
                                    v114,
                                    v116,
                                    v122,
                                    v112,
                                    v130,
                                    &v61->Owner);
                                  v75 = v123;
                                  v61->PrimaryGroup.PrimaryGroup = v61->Groups->Groups[0].Sid;
                                  if ( v75 )
                                  {
                                    v110 = (__int64)v61->DeviceGroups->Groups;
                                    v134 = *(_OWORD *)v120;
                                    v133 = *(_OWORD *)v119;
                                    LsapAuMarshalSIDsToTokenInfo(
                                      v110,
                                      &v115,
                                      v75,
                                      a6,
                                      0,
                                      &v133,
                                      &v134,
                                      0,
                                      0,
                                      0,
                                      0,
                                      0,
                                      v74,
                                      0);
                                  }
                                  if ( v124 )
                                  {
                                    v76 = ((unsigned __int64)&v115->Sid + 1) & 0xFFFFFFFFFFFFFFFEuLL;
                                    v61->DefaultDacl.DefaultDacl = (PACL)v76;
                                    v77 = (struct _SID_AND_ATTRIBUTES *)(v76 + v52);
                                  }
                                  else
                                  {
                                    v77 = v115;
                                  }
                                  v78 = (struct _TOKEN_PRIVILEGES *)(((unsigned __int64)&v77->Sid + 3)
                                                                   & 0xFFFFFFFFFFFFFFFCuLL);
                                  v61->Privileges = v78;
                                  v78->PrivilegeCount = 0;
                                  v79 = WPP_GLOBAL_Control;
                                  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control )
                                  {
                                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                                    {
                                      WPP_SF_q(
                                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                                        18,
                                        WPP_fac8e1c640d53114d3306e5e667a867e_Traceguids,
                                        v61);
                                      v79 = WPP_GLOBAL_Control;
                                    }
                                    if ( v79 != (LsaHandleCache *)&WPP_GLOBAL_Control )
                                    {
                                      if ( (*((_BYTE *)v79 + 28) & 4) != 0 )
                                      {
                                        WPP_SF_d(
                                          *((_QWORD *)v79 + 2),
                                          19,
                                          WPP_fac8e1c640d53114d3306e5e667a867e_Traceguids,
                                          v59);
                                        v79 = WPP_GLOBAL_Control;
                                      }
                                      if ( v79 != (LsaHandleCache *)&WPP_GLOBAL_Control
                                        && (*((_BYTE *)v79 + 28) & 4) != 0 )
                                      {
                                        WPP_SF_q(
                                          *((_QWORD *)v79 + 2),
                                          20,
                                          WPP_fac8e1c640d53114d3306e5e667a867e_Traceguids,
                                          v78);
                                      }
                                    }
                                  }
                                  *v131 = v61;
                                  *v132 = v59;
                                }
                                else
                                {
                                  v51 = -1073741801;
                                }
                              }
LABEL_83:
                              if ( *(v12 - 2) == 1885431112 )
                                ((void (*)(void))g_pfnFree)();
                              if ( v122 )
                                LsapSubProv_FreeRoutine(v122, v42);
                              if ( hMem[1] )
                                LocalFree(hMem[1]);
                              if ( v117[1] )
                                LocalFree(v117[1]);
                              if ( v119[1] )
                                LocalFree(v119[1]);
                              if ( v120[1] )
                                LocalFree(v120[1]);
                              return (unsigned int)v51;
                            }
                          }
                        }
                      }
LABEL_82:
                      v51 = -1073741675;
                      goto LABEL_83;
                    }
                  }
                  if ( !RtlEqualSid(*((PSID *)WellKnownSids + 156), v13)
                    && !RtlEqualSid(*((PSID *)WellKnownSids + 162), v13) )
                  {
                    goto LABEL_38;
                  }
                  LastError = 0;
                  StringSid = 0;
                  if ( RtlEqualSid(*((PSID *)WellKnownSids + 156), v13)
                    || RtlEqualSid(*((PSID *)WellKnownSids + 162), v13) )
                  {
                    if ( ConvertSidToStringSidW(v13, &StringSid) )
                    {
                      v51 = LsapReadInstallationProviderGroups(StringSid, &v112, (void **)&v122);
                    }
                    else
                    {
                      v51 = 0;
                      LastError = GetLastError();
                    }
                  }
                  else
                  {
                    v51 = -1073741811;
                  }
                  LocalFree(StringSid);
                  if ( LastError )
                    v51 = NetpApiStatusToNtStatus(LastError, v42, v87, v88);
                  v89 = v51 < 0;
                }
                if ( v89 )
                  goto LABEL_83;
                goto LABEL_38;
              }
            }
          }
          else
          {
            AliasMembership = -1073741637;
          }
          if ( hMem[1] )
            LocalFree(hMem[1]);
        }
      }
    }
    else
    {
      AliasMembership = -1073741637;
    }
    if ( *(v12 - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    return (unsigned int)AliasMembership;
  }
  return result;
}

```

## disassembly

```asm
0x18001531c  push    rbp
0x18001531e  push    rsi
0x18001531f  push    rdi
0x180015320  push    r12
0x180015322  push    r13
0x180015324  push    r14
0x180015326  push    r15
0x180015328  sub     rsp, 3E0h
0x18001532f  lea     rbp, [rsp+70h]
0x180015334  mov     [rbp+3A0h+arg_0], rbx
0x18001533b  mov     rax, cs:__security_cookie
0x180015342  xor     rax, rbp
0x180015345  mov     [rbp+3A0h+var_40], rax
0x18001534c  mov     rax, [rbp+3A0h+arg_20]
0x180015353  xor     r15d, r15d
0x180015356  mov     r13, [rbp+3A0h+arg_30]
0x18001535d  xorps   xmm0, xmm0
0x180015360  mov     [rbp+3A0h+var_318], r8d
0x180015367  xorps   xmm1, xmm1
0x18001536a  mov     r8, [rbp+3A0h+arg_38]
0x180015371  mov     rsi, [rax]
0x180015374  mov     [rbp+3A0h+var_2E0], r8
0x18001537b  mov     r8, [rbp+3A0h+arg_40]
0x180015382  mov     [rbp+3A0h+var_2D8], r8
0x180015389  mov     r8, [rbp+3A0h+arg_58]
0x180015390  mov     [rbp+3A0h+var_390], rax
0x180015394  lea     eax, [rcx-1]
0x180015397  mov     r12d, r9d
0x18001539a  mov     [rbp+3A0h+var_39C], r12d
0x18001539e  mov     [r8], r15d
0x1800153a1  mov     [rbp+3A0h+var_340], ecx
0x1800153a4  mov     [rbp+3A0h+var_330], r13
0x1800153a8  mov     [rbp+3A0h+var_2E8], r8
0x1800153af  mov     [rbp+3A0h+Sid], r15
0x1800153b6  mov     [rbp+3A0h+var_338], r15
0x1800153ba  mov     [rbp+3A0h+var_3A0], r15d
0x1800153be  mov     dword ptr [rbp+3A0h+Information], r15d
0x1800153c5  mov     word ptr [rbp+3A0h+Information+4], 500h
0x1800153ce  movups  xmmword ptr [rbp+3A0h+hMem], xmm0
0x1800153d2  movups  xmmword ptr [rbp+3A0h+var_380], xmm1
0x1800153d6  movups  xmmword ptr [rbp+3A0h+var_360], xmm0
0x1800153da  movups  xmmword ptr [rbp+3A0h+var_350], xmm1
0x1800153de  movups  [rbp+3A0h+var_308], xmm0
0x1800153e5  movups  [rbp+3A0h+var_2F8], xmm1
0x1800153ec  cmp     eax, 1
0x1800153ef  ja      loc_180015F38
0x1800153f5  mov     r14, rdx
0x1800153f8  mov     [rbp+3A0h+var_328], rdx
0x1800153fc  call    ?LsapWaitForSamForAwhile@@YAJXZ; LsapWaitForSamForAwhile(void)
0x180015401  test    eax, eax
0x180015403  js      loc_180015AC1
0x180015409  mov     edi, [rbp+3A0h+arg_28]
0x18001540f  add     edi, r12d
0x180015412  lea     rbx, ds:0[rdi*8]
0x18001541a  test    rbx, rbx
0x18001541d  jz      loc_180015F4D
0x180015423  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18001542a  ja      loc_180015F4D
0x180015430  mov     rcx, cs:g_ulAdditionalProbeSize
0x180015437  add     rcx, 8
0x18001543b  add     rcx, rbx
0x18001543e  cmp     rcx, rbx
0x180015441  jb      loc_180015F4D
0x180015447  call    VerifyStackAvailable
0x18001544c  test    eax, eax
0x18001544e  jz      loc_180015F4D
0x180015454  lea     rax, [rbx+8]
0x180015458  lea     rcx, [rax+0Fh]
0x18001545c  cmp     rcx, rax
0x18001545f  ja      short loc_18001546B
0x180015461  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001546b  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001546f  mov     rax, rcx
0x180015472  call    _alloca_probe
0x180015477  sub     rsp, rcx
0x18001547a  lea     r15, [rsp+410h+var_3A0]
0x18001547f  test    r15, r15
0x180015482  jz      loc_180015F4D
0x180015488  mov     dword ptr [r15], 6B637453h
0x18001548f  add     r15, 8
0x180015493  jz      loc_180015F4D
0x180015499  test    r15, r15
0x18001549c  jz      loc_180015F81
0x1800154a2  xor     ecx, ecx
0x1800154a4  test    edi, edi
0x1800154a6  jz      short loc_1800154CD
0x1800154a8  mov     r8, [rbp+3A0h+var_390]
0x1800154ac  mov     edx, ecx
0x1800154ae  cmp     ecx, r12d
0x1800154b1  jnb     loc_180015A47
0x1800154b7  mov     eax, edx
0x1800154b9  shl     rax, 4
0x1800154bd  add     rax, r8
0x1800154c0  mov     rax, [rax]
0x1800154c3  mov     [r15+rcx*8], rax
0x1800154c7  inc     ecx
0x1800154c9  cmp     ecx, edi
0x1800154cb  jb      short loc_1800154AC
0x1800154cd  mov     dword ptr [rbp+3A0h+var_308], r12d
0x1800154d4  mov     qword ptr [rbp+3A0h+var_308+8], r15
0x1800154db  test    r13, r13
0x1800154de  jnz     loc_180015F8B
0x1800154e4  cmp     cs:LsapProductType, 2
0x1800154eb  jz      loc_180015FA7
0x1800154f1  mov     rdi, cs:?LsapAccountDomainHandle@@3PEAXEA; void * LsapAccountDomainHandle
0x1800154f8  mov     dword ptr [rbp+3A0h+hMem], 0
0x1800154ff  mov     [rbp+3A0h+hMem+8], 0
0x180015507  mov     dword ptr [rbp+3A0h+var_360], 0
0x18001550e  mov     [rbp+3A0h+var_360+8], 0
0x180015516  call    IsSamIDecodeClaimsBlobPresent
0x18001551b  test    al, al
0x18001551d  jz      loc_180016227
0x180015523  lea     r8, [rbp+3A0h+hMem]
0x180015527  mov     rcx, rdi
0x18001552a  lea     rdx, [rbp+3A0h+var_308]
0x180015531  call    cs:__imp_SamIGetAliasMembership
0x180015538  nop     dword ptr [rax+rax+00h]
0x18001553d  mov     ebx, eax
0x18001553f  test    eax, eax
0x180015541  js      loc_18001622C
0x180015547  test    r13, r13
0x18001554a  jz      short loc_180015569
0x18001554c  lea     r8, [rbp+3A0h+var_360]; struct _SAMPR_ULONG_ARRAY *
0x180015550  mov     rcx, rdi; void *
0x180015553  lea     rdx, [rbp+3A0h+var_2F8]; struct _SAMPR_PSID_ARRAY *
0x18001555a  call    ?LsapSamExtGetAliasMembership@@YAJPEAXPEAU_SAMPR_PSID_ARRAY@@PEAU_SAMPR_ULONG_ARRAY@@@Z; LsapSamExtGetAliasMembership(void *,_SAMPR_PSID_ARRAY *,_SAMPR_ULONG_ARRAY *)
0x18001555f  mov     ebx, eax
0x180015561  test    eax, eax
0x180015563  js      loc_18001622C
0x180015569  mov     edi, [rbp+3A0h+arg_48]
0x18001556f  mov     r12d, 3E8h
0x180015575  mov     r10d, 0FFFFFFFFh
0x18001557b  test    edi, edi
0x18001557d  jnz     loc_180015FC0
0x180015583  mov     rbx, cs:?LsapBuiltinDomainHandle@@3PEAXEA; void * LsapBuiltinDomainHandle
0x18001558a  mov     dword ptr [rbp+3A0h+var_380], 0
0x180015591  mov     [rbp+3A0h+var_380+8], 0
0x180015599  mov     dword ptr [rbp+3A0h+var_350], 0
0x1800155a0  mov     [rbp+3A0h+var_350+8], 0
0x1800155a8  call    IsSamIDecodeClaimsBlobPresent
0x1800155ad  test    al, al
0x1800155af  jz      loc_18001620B
0x1800155b5  lea     r8, [rbp+3A0h+var_380]
0x1800155b9  mov     rcx, rbx
0x1800155bc  lea     rdx, [rbp+3A0h+var_308]
0x1800155c3  call    cs:__imp_SamIGetAliasMembership
0x1800155ca  nop     dword ptr [rax+rax+00h]
0x1800155cf  mov     ebx, eax
0x1800155d1  test    eax, eax
0x1800155d3  js      loc_180016210
0x1800155d9  test    r13, r13
0x1800155dc  jz      short loc_1800155FF
0x1800155de  mov     rcx, cs:?LsapBuiltinDomainHandle@@3PEAXEA; void *
0x1800155e5  lea     r8, [rbp+3A0h+var_350]; struct _SAMPR_ULONG_ARRAY *
0x1800155e9  lea     rdx, [rbp+3A0h+var_2F8]; struct _SAMPR_PSID_ARRAY *
0x1800155f0  call    ?LsapSamExtGetAliasMembership@@YAJPEAXPEAU_SAMPR_PSID_ARRAY@@PEAU_SAMPR_ULONG_ARRAY@@@Z; LsapSamExtGetAliasMembership(void *,_SAMPR_PSID_ARRAY *,_SAMPR_ULONG_ARRAY *)
0x1800155f5  mov     ebx, eax
0x1800155f7  test    eax, eax
0x1800155f9  js      loc_180016210
0x1800155ff  mov     edx, dword ptr [rbp+3A0h+var_380]
0x180015602  mov     [rbp+3A0h+var_398], 0
0x180015609  mov     [rbp+3A0h+var_388], 0
0x180015610  test    edi, edi
0x180015612  jnz     loc_180015D5D
0x180015618  mov     edi, [rbp+3A0h+arg_50]
0x18001561e  test    edi, edi
0x180015620  jnz     loc_180015ED8
0x180015626  mov     ecx, cs:?dwThreadPackage@@3KA; dwTlsIndex
0x18001562c  call    cs:__imp_TlsGetValue
0x180015633  nop     dword ptr [rax+rax+00h]
0x180015638  test    rax, rax
0x18001563b  jnz     loc_180015DD7
0x180015641  mov     rcx, rsi; Sid
0x180015644  call    cs:__imp_RtlSubAuthorityCountSid
0x18001564b  nop     dword ptr [rax+rax+00h]
0x180015650  test    edi, edi
0x180015652  jnz     loc_180015CFC
0x180015658  cmp     byte ptr [rax], 1
0x18001565b  jnb     loc_180015BF1
0x180015661  mov     rcx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180015668  mov     rdx, rsi; Sid2
0x18001566b  mov     rcx, [rcx+4E0h]; Sid1
0x180015672  call    cs:__imp_RtlEqualSid
0x180015679  nop     dword ptr [rax+rax+00h]
0x18001567e  test    al, al
0x180015680  jnz     loc_180015C72
0x180015686  mov     rcx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18001568d  mov     rdx, rsi; Sid2
0x180015690  mov     rcx, [rcx+510h]; Sid1
0x180015697  call    cs:__imp_RtlEqualSid
0x18001569e  nop     dword ptr [rax+rax+00h]
0x1800156a3  test    al, al
0x1800156a5  jnz     loc_180015C72
0x1800156ab  mov     rax, [rbp+3A0h+var_390]
0x1800156af  mov     rcx, [rax]; Sid
0x1800156b2  call    cs:__imp_RtlLengthSid
0x1800156b9  nop     dword ptr [rax+rax+00h]
0x1800156be  cmp     [rbp+3A0h+var_340], 3
0x1800156c2  mov     ecx, 58h ; 'X'
0x1800156c7  mov     r12d, eax
0x1800156ca  mov     [rbp+3A0h+DestinationSidLength], eax
0x1800156d0  jz      loc_180015F02
0x1800156d6  mov     r10d, [rbp+3A0h+var_388]
0x1800156da  mov     r11d, [rbp+3A0h+var_39C]
0x1800156de  mov     r8d, dword ptr [rbp+3A0h+var_380]
0x1800156e2  mov     edx, dword ptr [rbp+3A0h+hMem]; void *
0x1800156e5  mov     esi, [rbp+3A0h+var_3A0]
0x1800156e8  mov     r9d, dword ptr [rbp+3A0h+var_350]
0x1800156ec  lea     r14d, [r11+r10]
0x1800156f0  add     r14d, r8d
0x1800156f3  add     r14d, edx
0x1800156f6  add     r14d, esi
0x1800156f9  add     r14d, [rbp+3A0h+var_398]
0x1800156fd  shl     r14d, 4
0x180015701  add     r14d, 0FFFFFFF8h
0x180015705  add     r14d, ecx
0x180015708  mov     ecx, dword ptr [rbp+3A0h+var_360]
0x18001570b  test    r13, r13
0x18001570e  jnz     loc_180016073
0x180015714  lea     eax, [rcx+rdx]
0x180015717  cmp     eax, edx
0x180015719  jb      loc_180015A58
0x18001571f  mov     edi, eax
0x180015721  mov     ecx, 0FFFFFFFFh
0x180015726  mov     eax, cs:?LsapAccountDomainMemberSidLength@@3KA; ulong LsapAccountDomainMemberSidLength
0x18001572c  imul    rdi, rax
0x180015730  cmp     rdi, rcx
0x180015733  ja      loc_180015A58
0x180015739  lea     eax, [r9+r8]
0x18001573d  cmp     eax, r8d
0x180015740  jb      loc_180015A58
0x180015746  mov     ebx, eax
0x180015748  mov     eax, cs:?LsapBuiltinDomainMemberSidLength@@3KA; ulong LsapBuiltinDomainMemberSidLength
0x18001574e  imul    rbx, rax
0x180015752  cmp     rbx, rcx
0x180015755  ja      loc_180015A58
0x18001575b  imul    rsi, 2Ch ; ','
0x18001575f  cmp     rsi, rcx
0x180015762  ja      loc_180015A58
0x180015768  test    r10d, r10d
0x18001576b  jnz     loc_180015E7C
0x180015771  lea     eax, [rdi+rbx]
0x180015774  cmp     eax, edi
0x180015776  jb      loc_180015A58
0x18001577c  lea     ecx, [rsi+rax]
0x18001577f  cmp     ecx, eax
0x180015781  jb      loc_180015A58
0x180015787  lea     eax, [rcx+r12]
0x18001578b  cmp     eax, r12d
0x18001578e  jb      loc_180015A58
0x180015794  add     r14d, eax
0x180015797  cmp     r14d, eax
0x18001579a  jb      loc_180015A58
0x1800157a0  xor     esi, esi
0x1800157a2  xor     r13d, r13d
0x1800157a5  lea     ebx, [rsi+1]
0x1800157a8  cmp     r11d, ebx
0x1800157ab  jbe     short loc_1800157DF
0x1800157ad  mov     r12d, [rbp+3A0h+var_39C]
0x1800157b1  mov     r13, [rbp+3A0h+var_390]
0x1800157b5  mov     ecx, ebx
0x1800157b7  add     rcx, rcx
0x1800157ba  mov     rcx, [r13+rcx*8+0]; Sid
0x1800157bf  call    cs:__imp_RtlLengthSid
0x1800157c6  nop     dword ptr [rax+rax+00h]
0x1800157cb  add     r14d, eax
0x1800157ce  inc     ebx
0x1800157d0  cmp     ebx, r12d
0x1800157d3  jb      short loc_1800157B5
0x1800157d5  mov     r12d, [rbp+3A0h+DestinationSidLength]
0x1800157dc  mov     r13d, esi
0x1800157df  cmp     [rbp+3A0h+var_330], rsi
0x1800157e3  jnz     loc_18001608B
0x1800157e9  mov     edi, [rbp+3A0h+var_398]
0x1800157ec  xor     ebx, ebx
0x1800157ee  test    edi, edi
0x1800157f0  jnz     loc_180015BC5
0x1800157f6  mov     rax, [rbp+3A0h+var_328]
0x1800157fa  test    rax, rax
0x1800157fd  jz      short loc_180015858
0x1800157ff  mov     rcx, [rax+38h]; Acl
0x180015803  test    rcx, rcx
0x180015806  jz      loc_180015B7B
0x18001580c  xor     eax, eax
0x18001580e  lea     rdx, [rbp+3A0h+Information]; Information
0x180015815  mov     [rbp+3A0h+Information], rax
0x18001581c  mov     [rbp+3A0h+var_2A0], eax
0x180015822  lea     r9d, [rax+2]; InformationClass
0x180015826  lea     r8d, [rax+0Ch]; InformationLength
0x18001582a  call    cs:__imp_RtlQueryInformationAcl
0x180015831  nop     dword ptr [rax+rax+00h]
0x180015836  mov     esi, eax
0x180015838  test    eax, eax
0x18001583a  js      loc_180015A5D
0x180015840  mov     r13d, dword ptr [rbp+3A0h+Information+4]
0x180015847  add     r13d, [rbp+3A0h+var_2A0]
0x18001584e  inc     r14d
0x180015851  and     r14d, 0FFFFFFFEh
0x180015855  add     r14d, r13d
0x180015858  lea     r12d, [r14+3]
  ... truncated ...
```
