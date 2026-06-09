# LsaDbrSetInformationTrustedDomain(void *,_TRUSTED_INFORMATION_CLASS,_LSAPR_TRUSTED_DOMAIN_INFO *)

- ea: `0x18000e9f0`
- end: `0x18000fb02`
- name: `?LsaDbrSetInformationTrustedDomain@@YAJPEAXW4_TRUSTED_INFORMATION_CLASS@@PEAT_LSAPR_TRUSTED_DOMAIN_INFO@@@Z`
- size: `4370`
- prototype: `__int64 __fastcall(char *, enum _TRUSTED_INFORMATION_CLASS, struct _TRUSTED_DOMAIN_AUTH_INFORMATION *)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000fb10`
- `0x180017a88`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x180002234`
- `0x1800099b4`
- `0x18000b7c8`
- `0x18000bd80`
- `0x18000bdfc`
- `0x18000c080`
- `0x18000c0e0`
- `0x18000cd2c`
- `0x18000d680`
- `0x18000e9f0`
- `0x18000fd18`
- `0x18000fd40`
- `0x18000fd80`
- `0x180016d50`
- `0x180017de8`
- `0x180018084`
- `0x180018fa4`
- `0x1800209d0`
- `0x180033f80`
- `0x180034208`
- `0x18003580c`
- `0x180035ee0`
- `0x180036e00`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000eb2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f9c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f9e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000eb2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f9c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f9e2`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x18000fa2c`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x18000fa43`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x18000fa2c`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x18000fa43`
- `LSASRV!LsapDbDereferenceHandle` at `0x18000f9b4`
- `LSASRV!LsapDbDereferenceHandle` at `0x18000f9b4`
- `LSASRV!LsapDbWriteAttributesObject` at `0x18000f84e`
- `LSASRV!LsapDbWriteAttributesObject` at `0x18000f84e`
- `LSASRV!LsapCrServerGetSessionKeySafe` at `0x18000ec5f`
- `LSASRV!LsapCrServerGetSessionKeySafe` at `0x18000ec5f`
- `LSASRV!LsapDbVerifyHandle` at `0x18000ebdd`
- `LSASRV!LsapDbVerifyHandle` at `0x18000ebdd`
- `LSASRV!LsapDbVerifyInfoSetTrustedDomain` at `0x18000ebbf`
- `LSASRV!LsapDbVerifyInfoSetTrustedDomain` at `0x18000ebbf`
- `LSASRV!LsapTraceEvent` at `0x18000eaad`
- `LSASRV!LsapTraceEvent` at `0x18000faa8`
- `LSASRV!LsapTraceEvent` at `0x18000eaad`
- `LSASRV!LsapTraceEvent` at `0x18000faa8`
- `LSASRV!LsapDbDereferenceObject` at `0x18000fa17`
- `LSASRV!LsapDbDereferenceObject` at `0x18000fa17`
- `LSASRV!LsapGetAccountDomainHandle` at `0x18000f7a9`
- `LSASRV!LsapGetAccountDomainHandle` at `0x18000f7a9`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000eee5`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000ef23`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000efff`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f054`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f0e3`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f16a`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f2c1`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f2fa`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f333`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f3e2`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f4ec`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f533`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f593`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f6e4`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f73e`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f8c3`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000eee5`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000ef23`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000efff`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f054`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f0e3`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f16a`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f2c1`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f2fa`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f333`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f3e2`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f4ec`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f533`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f593`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f6e4`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f73e`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000f8c3`
- `LSASRV!LsapDbReferenceObject` at `0x18000eca3`
- `LSASRV!LsapDbReferenceObject` at `0x18000eca3`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x18000f7ef`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x18000f7ef`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18000fa50`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18000fa50`
- `LSASRV!LsapAllocateLsaHeap` at `0x18000ed6f`
- `LSASRV!LsapAllocateLsaHeap` at `0x18000ed6f`
- `LSASRV!LsapFreeLsaHeap` at `0x18000fa62`
- `LSASRV!LsapFreeLsaHeap` at `0x18000fa70`
- `LSASRV!LsapFreeLsaHeap` at `0x18000fa62`
- `LSASRV!LsapFreeLsaHeap` at `0x18000fa70`
- `ntdll!RtlCopySid` at `0x18000ed9c`
- `ntdll!RtlCopySid` at `0x18000ed9c`
- `ntdll!RtlLengthSid` at `0x18000ed65`
- `ntdll!RtlLengthSid` at `0x18000ed65`
- `SAMSRV!SamIQueryServerRole` at `0x18000f7b7`
- `SAMSRV!SamIQueryServerRole` at `0x18000f7b7`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledHint` at `0x18000f945`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledHint` at `0x18000f945`

## pseudocode

```c
__int64 __fastcall LsaDbrSetInformationTrustedDomain(
        char *a1,
        enum _TRUSTED_INFORMATION_CLASS a2,
        struct _TRUSTED_DOMAIN_AUTH_INFORMATION *a3)
{
  enum _TRUSTED_INFORMATION_CLASS v4; // r14d
  union _LSAPR_TRUSTED_DOMAIN_INFO *v5; // r15
  unsigned int *p_IncomingAuthInfos; // r12
  unsigned __int8 *v7; // r13
  unsigned int v8; // edi
  void *v9; // rcx
  HLOCAL v10; // rbx
  const wchar_t *v11; // r9
  int SessionKeySafe; // ebx
  __int64 v13; // r9
  _DWORD *v14; // r10
  int v15; // r14d
  char v16; // r14
  union _LSAPR_TRUSTED_DOMAIN_INFO *v17; // rax
  void *v18; // rcx
  __int64 v19; // rbx
  __int64 LsaHeap; // rax
  void *v21; // rdx
  unsigned __int64 v22; // rcx
  __int128 v23; // xmm0
  ULONG IncomingAuthInfos; // ecx
  __int128 v25; // xmm1
  int OutgoingPreviousAuthenticationInformation_high; // eax
  int v27; // eax
  PLSA_AUTH_INFORMATION OutgoingAuthenticationInformation; // rcx
  _BYTE *v29; // r14
  char v30; // r13
  ULONG v31; // eax
  char v32; // bl
  struct _LSAP_DB_HANDLE *v33; // rcx
  _BYTE *v34; // r14
  struct _LSAP_DB_HANDLE *v35; // rcx
  _QWORD *v36; // rcx
  __int64 v37; // rdx
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm0
  ULONG v42; // ecx
  __int128 v43; // xmm1
  int v44; // eax
  int v45; // eax
  PLSA_AUTH_INFORMATION v46; // rcx
  char *v47; // r14
  struct _LSAP_DB_HANDLE *v48; // rcx
  struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *p_IncomingPreviousAuthenticationInformation; // rdx
  PLSA_AUTH_INFORMATION *p_OutgoingPreviousAuthenticationInformation; // r12
  struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *v51; // r8
  struct _LSAP_DB_HANDLE *v52; // rcx
  struct _LSAP_DB_HANDLE *v53; // rcx
  int v54; // r12d
  struct _LSAP_DB_HANDLE *v55; // rcx
  union _LSAPR_TRUSTED_DOMAIN_INFO *v56; // r9
  unsigned __int8 v57; // si
  ULONG *p_OutgoingAuthInfos; // r12
  struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *v59; // r8
  struct _LSAP_DB_HANDLE *v60; // rcx
  int v61; // r12d
  __int64 AccountDomainHandle; // rax
  unsigned int *v63; // rax
  unsigned int v64; // ecx
  unsigned int v65; // eax
  void *v66; // rcx
  struct _LSAPR_UNICODE_STRING *v67; // r8
  struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *v68; // r9
  struct _LSAPR_UNICODE_STRING *v69; // rdx
  int v70; // eax
  struct _LSAP_DB_HANDLE *v71; // rcx
  __int64 v72; // rdx
  __int64 v73; // r8
  unsigned __int16 v74; // cx
  unsigned int v75; // r9d
  unsigned int v76; // r14d
  HLOCAL *i; // rsi
  unsigned int v79; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v80[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v81; // [rsp+54h] [rbp-ACh]
  enum _TRUSTED_INFORMATION_CLASS v82; // [rsp+58h] [rbp-A8h]
  char v83; // [rsp+5Ch] [rbp-A4h]
  unsigned __int8 *v84; // [rsp+60h] [rbp-A0h] BYREF
  char v85; // [rsp+68h] [rbp-98h]
  char v86; // [rsp+69h] [rbp-97h]
  char v87; // [rsp+6Ah] [rbp-96h]
  void *v88; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v89; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v90; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v91; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v92; // [rsp+84h] [rbp-7Ch] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v94; // [rsp+90h] [rbp-70h] BYREF
  union _LSAPR_TRUSTED_DOMAIN_INFO *v95; // [rsp+98h] [rbp-68h] BYREF
  char *v96; // [rsp+A0h] [rbp-60h]
  unsigned __int8 *v97; // [rsp+A8h] [rbp-58h] BYREF
  HLOCAL v98[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING v99[4]; // [rsp+C0h] [rbp-40h] BYREF
  union _LSAPR_TRUSTED_DOMAIN_INFO *v100; // [rsp+100h] [rbp+0h]
  struct _TRUSTED_DOMAIN_AUTH_INFORMATION v101; // [rsp+108h] [rbp+8h] BYREF
  _OWORD v102[3]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v103; // [rsp+170h] [rbp+70h]
  int IncomingAuthenticationInformation; // [rsp+178h] [rbp+78h]
  struct _TRUSTED_DOMAIN_AUTH_INFORMATION v105; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v106[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  int v107; // [rsp+1D0h] [rbp+D0h]
  int v108; // [rsp+1D4h] [rbp+D4h]
  _BYTE v109[32]; // [rsp+1D8h] [rbp+D8h] BYREF
  int v110; // [rsp+1F8h] [rbp+F8h]
  int v111; // [rsp+1FCh] [rbp+FCh]
  _BYTE v112[32]; // [rsp+200h] [rbp+100h] BYREF
  int v113; // [rsp+220h] [rbp+120h]
  int v114; // [rsp+224h] [rbp+124h]
  _BYTE v115[40]; // [rsp+228h] [rbp+128h] BYREF
  char v116; // [rsp+250h] [rbp+150h] BYREF

  v82 = a2;
  v96 = a1;
  v88 = a1;
  v4 = a2;
  v94 = 0;
  v87 = 0;
  v85 = 0;
  v95 = 0;
  v5 = 0;
  memset(v99, 0, sizeof(v99));
  v100 = 0;
  memset_0(v102, 0, 0x70u);
  v81 = 0;
  v90 = 0;
  v97 = 0;
  p_IncomingAuthInfos = 0;
  v84 = 0;
  v7 = 0;
  v92 = 0;
  v89 = 0;
  v8 = 17;
  v86 = 0;
  v98[0] = 0;
  v91 = 0;
  v80[0] = 1;
  hMem = 0;
  LsapTraceEvent(1, 10);
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids);
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      LsaDbGetCallerInfo(v9, (unsigned __int16 **)&hMem);
      v10 = hMem;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        v11 = L"Unknown";
        if ( hMem )
          v11 = (const wchar_t *)hMem;
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids, v11);
      }
      LocalFree(v10);
    }
  }
  memset(&v101, 0, sizeof(v101));
  memset_0(v102, 0, 0x70u);
  hMem = v88;
  if ( v4 != TrustedPosixOffsetInformation
    && v4 != TrustedDomainInformationEx
    && v4 != TrustedDomainAuthInformation
    && v4 != TrustedDomainFullInformation
    && v4 != TrustedDomainAuthInformationInternal
    && v4 != TrustedDomainFullInformationInternal
    && v4 != TrustedDomainSupportedEncryptionTypes
    && (unsigned int)(v4 - 14) > 1
    || !LsapValidateLsaprHandle(&hMem)
    || !LsaDbpValidateLsaprTrustedDomainInfo((union _LSAPR_TRUSTED_DOMAIN_INFO *)a3, v4) )
  {
    SessionKeySafe = -1073741811;
    goto LABEL_190;
  }
  SessionKeySafe = LsapDbVerifyInfoSetTrustedDomain((unsigned int)v4, a3, 0, &v94);
  if ( SessionKeySafe < 0 )
    goto LABEL_190;
  LOBYTE(v13) = 1;
  SessionKeySafe = LsapDbVerifyHandle(v88, 0, 2, v13);
  if ( SessionKeySafe < 0 )
    goto LABEL_190;
  v14 = v88;
  v86 = 1;
  v8 = (*((_DWORD *)v88 + 34) & 0x400000) != 0 ? 1 : 17;
  v15 = (*((_DWORD *)v88 + 34) & 0x400000) != 0 ? 1 : 9;
  if ( (unsigned int)(v82 - 9) <= 1 || (unsigned int)(v82 - 14) <= 1 )
  {
    SessionKeySafe = LsaDbpIsCallLocal(v80);
    if ( SessionKeySafe < 0 )
      goto LABEL_26;
    if ( !v80[0] )
    {
      SessionKeySafe = LsapCrServerGetSessionKeySafe(*((_QWORD *)v88 + 14), 1, v98);
      if ( SessionKeySafe < 0 )
        goto LABEL_26;
    }
    v14 = v88;
  }
  if ( (v14[34] & 0x400000) == 0 )
  {
    v79 = v15;
    SessionKeySafe = LsapDbReferenceObject(v14, v94, 2, 2);
    if ( SessionKeySafe < 0 )
    {
LABEL_26:
      v4 = v82;
LABEL_190:
      v57 = v80[0];
      goto LABEL_191;
    }
    v14 = v88;
    v87 = 1;
  }
  v16 = *((_BYTE *)v14 + 133);
  *((_BYTE *)v14 + 133) = 1;
  SessionKeySafe = LsaDbrQueryInfoTrustedDomain(v88, TrustedDomainFullInformation2Internal, &v95);
  if ( SessionKeySafe >= 0 )
  {
    v5 = v95;
    v95 = 0;
    SessionKeySafe = LsaDbrQueryInfoTrustedDomain(v88, TrustedDomainSupportedEncryptionTypes, &v95);
    v17 = 0;
    if ( SessionKeySafe >= 0 )
      v17 = v95;
    v100 = v17;
  }
  *((_BYTE *)v88 + 133) = v16;
  if ( SessionKeySafe < 0 )
    goto LABEL_26;
  v99[0] = *(struct _UNICODE_STRING *)v5;
  v99[1] = *((struct _UNICODE_STRING *)v5 + 1);
  v99[2] = *((struct _UNICODE_STRING *)v5 + 2);
  v99[3] = *((struct _UNICODE_STRING *)v5 + 3);
  if ( HIBYTE(word_18004706B) )
  {
    if ( !*((_QWORD *)v88 + 11) )
    {
      v18 = (void *)*((_QWORD *)v5 + 4);
      if ( v18 )
      {
        v19 = RtlLengthSid(v18);
        LsaHeap = LsapAllocateLsaHeap(v19);
        *((_QWORD *)v88 + 11) = LsaHeap;
        v21 = (void *)*((_QWORD *)v88 + 11);
        if ( !v21 )
        {
          SessionKeySafe = -1073741670;
          goto LABEL_26;
        }
        RtlCopySid(v19, v21, *((PSID *)v5 + 4));
      }
    }
  }
  v4 = v82;
  v83 = 0;
  hMem = 0;
  if ( v82 <= TrustedDomainFullInformation )
  {
    if ( v82 != TrustedDomainFullInformation )
    {
      if ( v82 == TrustedDomainNameInformation || v82 == TrustedControllersInformation )
        goto LABEL_91;
      if ( v82 == TrustedPosixOffsetInformation )
      {
        LOBYTE(v79) = 0;
        LsapDbInitializeAttribute(v106, 36, a3);
        v34 = v109;
        p_IncomingAuthInfos = &a3->IncomingAuthInfos;
        v81 = 1;
        v107 = *((_DWORD *)LsaDbpDsAttInfo + 108);
        v108 = *((_DWORD *)LsaDbpDsAttInfo + 109);
LABEL_159:
        if ( !p_IncomingAuthInfos )
          goto LABEL_175;
LABEL_160:
        v89 = 0;
        AccountDomainHandle = LsapGetAccountDomainHandle();
        SessionKeySafe = SamIQueryServerRole(AccountDomainHandle, &v89);
        if ( SessionKeySafe >= 0 )
        {
          if ( v89 != 3 )
            goto LABEL_175;
          v63 = (unsigned int *)((char *)v5 + 64);
          if ( p_IncomingAuthInfos )
            v63 = p_IncomingAuthInfos;
          v64 = *v63;
          if ( ((__int64)v99[2].Buffer & 2) == 0 || (unsigned int)(HIDWORD(v99[2].Buffer) - 1) > 1 )
          {
            if ( v64 )
            {
              v65 = 0;
              v90 = 0;
LABEL_173:
              if ( p_IncomingAuthInfos )
              {
                *p_IncomingAuthInfos = v65;
              }
              else
              {
                LOBYTE(v79) = 0;
                p_IncomingAuthInfos = &v90;
                LsapDbInitializeAttribute(v34, 36, &v90);
                v71 = LsaDbpDsAttInfo;
                ++v81;
                *((_DWORD *)v34 + 8) = *((_DWORD *)LsaDbpDsAttInfo + 108);
                *((_DWORD *)v34 + 9) = *((_DWORD *)v71 + 109);
              }
            }
LABEL_175:
            v4 = v82;
LABEL_176:
            SessionKeySafe = LsapDbWriteAttributesObject(v88, v106);
            if ( SessionKeySafe < 0 )
              goto LABEL_146;
            if ( (_BYTE)v7 )
            {
              SessionKeySafe = LsaDbpDsCreateInterdomainTrustAccount(v88);
              if ( SessionKeySafe < 0 )
                goto LABEL_146;
            }
            if ( v83 )
            {
              v66 = (void *)*((_QWORD *)v5 + 4);
              v67 = (union _LSAPR_TRUSTED_DOMAIN_INFO *)((char *)v5 + 16);
              v68 = (struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *)v99;
              v69 = v5;
              goto LABEL_181;
            }
            if ( p_IncomingAuthInfos )
            {
              v68 = 0;
              v67 = 0;
              v69 = 0;
              v66 = (void *)*((_QWORD *)v88 + 11);
LABEL_181:
              v70 = LsaDbpFixupTrustedDomainListEntry(v66, v69, v67, v68, p_IncomingAuthInfos);
              LODWORD(p_IncomingAuthInfos) = v81;
              SessionKeySafe = v70;
              if ( v70 < 0 )
                goto LABEL_58;
              goto LABEL_187;
            }
            LODWORD(p_IncomingAuthInfos) = v81;
LABEL_187:
            SessionKeySafe = 0;
            goto LABEL_57;
          }
          if ( v64
            || (SessionKeySafe = LsapDbExpAcquireWriteLockTrustedDomainList(), SessionKeySafe >= 0)
            && (v85 = 1, SessionKeySafe = LsaDbpAllocatePosixOffsetTrustedDomainList(&v90), SessionKeySafe >= 0) )
          {
            if ( v85 )
            {
              v65 = v90;
              goto LABEL_173;
            }
            goto LABEL_175;
          }
        }
        goto LABEL_56;
      }
      if ( v82 != TrustedDomainInformationBasic )
      {
        v22 = (unsigned int)(v82 - 6);
        if ( v82 != TrustedDomainInformationEx )
        {
          if ( v82 != TrustedDomainAuthInformation )
            goto LABEL_91;
          goto LABEL_137;
        }
        p_IncomingAuthInfos = (unsigned int *)&a3->OutgoingPreviousAuthenticationInformation;
        v23 = *(_OWORD *)((char *)&a3->IncomingAuthInfos + 2);
        IncomingAuthInfos = a3[1].IncomingAuthInfos;
        v25 = *(_OWORD *)((char *)&a3->IncomingPreviousAuthenticationInformation + 2);
        v99[0].Length = a3->IncomingAuthInfos;
        LODWORD(v99[2].Buffer) = a3->OutgoingPreviousAuthenticationInformation;
        OutgoingPreviousAuthenticationInformation_high = HIDWORD(a3->OutgoingPreviousAuthenticationInformation);
        *(_OWORD *)&v99[0].MaximumLength = v23;
        HIDWORD(v99[2].Buffer) = OutgoingPreviousAuthenticationInformation_high;
        v27 = *(&a3[1].IncomingAuthInfos + 1);
        *(_QWORD *)&v23 = a3->OutgoingAuthenticationInformation;
        *(_OWORD *)&v99[1].MaximumLength = v25;
        *(_DWORD *)(&v99[3].MaximumLength + 1) = v27;
        *(_QWORD *)&v99[2].Length = v23;
        *(_DWORD *)&v99[3].Length = IncomingAuthInfos;
        *(_DWORD *)(&v99[3].MaximumLength + 1) = *((_DWORD *)v5 + 13);
        v99[3].Buffer = (PWSTR)*((_QWORD *)v5 + 7);
        if ( ((*((_BYTE *)v5 + 48) & 8) != 0
           || (IncomingAuthInfos & 8) == 0
           || DcInRootDomain && LsaDbpNoMoreWin2KForest())
          && ((*((_BYTE *)v5 + 48) & 0x10) != 0 || (a3[1].IncomingAuthInfos & 0x10) == 0 || LsaDbpNoMoreWin2KDomain()) )
        {
          if ( (a3[1].IncomingAuthInfos & 8) == 0
            || (*((_BYTE *)v5 + 48) & 4) != 0
            || (a3[1].IncomingAuthInfos & 4) == 0 )
          {
            SessionKeySafe = LsaDbpVerifyTrustLocation((struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *)a3);
            if ( SessionKeySafe < 0 )
              goto LABEL_56;
            if ( (a3[1].IncomingAuthInfos & 0x20) == 0 || (a3[1].IncomingAuthInfos & 0x18) == 0 )
            {
              LsapDbInitializeAttribute(v106, 38, (char *)&a3->OutgoingPreviousAuthenticationInformation + 4);
              LOBYTE(v79) = 0;
              v107 = *((_DWORD *)LsaDbpDsAttInfo + 114);
              v108 = *((_DWORD *)LsaDbpDsAttInfo + 115);
              LsapDbInitializeAttribute(v109, 39, &a3->OutgoingPreviousAuthenticationInformation);
              v81 = 2;
              v110 = *((_DWORD *)LsaDbpDsAttInfo + 117);
              v111 = *((_DWORD *)LsaDbpDsAttInfo + 118);
              if ( (unsigned int)(HIDWORD(a3->OutgoingPreviousAuthenticationInformation) - 1) <= 1
                && (*(_BYTE *)p_IncomingAuthInfos & 2) != 0
                && !a3->OutgoingAuthenticationInformation
                && !*((_QWORD *)v5 + 4) )
              {
LABEL_73:
                SessionKeySafe = -1073741704;
                goto LABEL_56;
              }
              OutgoingAuthenticationInformation = a3->OutgoingAuthenticationInformation;
              if ( OutgoingAuthenticationInformation )
              {
                SessionKeySafe = LsaDbpIsValidDomainSid(OutgoingAuthenticationInformation);
                if ( SessionKeySafe < 0 )
                  goto LABEL_56;
                SessionKeySafe = LsaDbpMakeSidAttributeDs(a3->OutgoingAuthenticationInformation, 33, v112);
                if ( SessionKeySafe < 0 )
                  goto LABEL_56;
                v29 = v115;
                v81 = 3;
              }
              else
              {
                v29 = v112;
              }
              v30 = *(_BYTE *)p_IncomingAuthInfos;
              v31 = a3[1].IncomingAuthInfos;
              v32 = 1;
              v83 = 1;
              LOBYTE(v7) = v30 & 1;
              LOBYTE(v79) = 0;
              v91 = v31 & 0xFF03FFFF;
              LsapDbInitializeAttribute(v29, 40, &v91);
              v33 = LsaDbpDsAttInfo;
              LODWORD(p_IncomingAuthInfos) = ++v81;
              *((_DWORD *)v29 + 8) = *((_DWORD *)LsaDbpDsAttInfo + 120);
              *((_DWORD *)v29 + 9) = *((_DWORD *)v33 + 121);
              v34 = v29 + 40;
              if ( (*((_BYTE *)v5 + 48) & 8) == 0 )
                goto LABEL_157;
              if ( (a3[1].IncomingAuthInfos & 8) != 0 )
                goto LABEL_157;
              LOBYTE(v79) = 0;
              LsapDbInitializeAttribute(v34, 45, 0);
              v35 = LsaDbpDsAttInfo;
              *((_DWORD *)v34 + 8) = *((_DWORD *)LsaDbpDsAttInfo + 135);
              *((_DWORD *)v34 + 9) = *((_DWORD *)v35 + 136);
              v34 += 40;
              LODWORD(p_IncomingAuthInfos) = (_DWORD)p_IncomingAuthInfos + 1;
              *(_DWORD *)(&v99[3].MaximumLength + 1) = 0;
              v81 = (int)p_IncomingAuthInfos;
              v99[3].Buffer = 0;
              v36 = WPP_GLOBAL_Control;
              if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
                goto LABEL_157;
              v37 = 23;
LABEL_83:
              WPP_SF_(v36[2], v37, &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids);
              goto LABEL_157;
            }
          }
          goto LABEL_65;
        }
LABEL_55:
        SessionKeySafe = -1073741603;
LABEL_56:
        LODWORD(p_IncomingAuthInfos) = v81;
LABEL_57:
        v4 = v82;
LABEL_58:
        v7 = v84;
        goto LABEL_190;
      }
LABEL_91:
      SessionKeySafe = -1073741811;
      goto LABEL_58;
    }
LABEL_96:
    p_IncomingAuthInfos = (unsigned int *)&a3->OutgoingPreviousAuthenticationInformation;
    v41 = *(_OWORD *)((char *)&a3->IncomingAuthInfos + 2);
    v42 = a3[1].IncomingAuthInfos;
    v43 = *(_OWORD *)((char *)&a3->IncomingPreviousAuthenticationInformation + 2);
    v99[0].Length = a3->IncomingAuthInfos;
    LODWORD(v99[2].Buffer) = a3->OutgoingPreviousAuthenticationInformation;
    v44 = HIDWORD(a3->OutgoingPreviousAuthenticationInformation);
    *(_OWORD *)&v99[0].MaximumLength = v41;
    HIDWORD(v99[2].Buffer) = v44;
    v45 = *(&a3[1].IncomingAuthInfos + 1);
    *(_QWORD *)&v41 = a3->OutgoingAuthenticationInformation;
    *(_OWORD *)&v99[1].MaximumLength = v43;
    *(_DWORD *)(&v99[3].MaximumLength + 1) = v45;
    *(_QWORD *)&v99[2].Length = v41;
    *(_DWORD *)&v99[3].Length = v42;
    *(_DWORD *)(&v99[3].MaximumLength + 1) = *((_DWORD *)v5 + 13);
    v99[3].Buffer = (PWSTR)*((_QWORD *)v5 + 7);
    if ( (*((_BYTE *)v5 + 48) & 8) == 0 && (v42 & 8) != 0 && (!DcInRootDomain || !LsaDbpNoMoreWin2KForest())
      || (*((_BYTE *)v5 + 48) & 0x10) == 0 && (a3[1].IncomingAuthInfos & 0x10) != 0 && !LsaDbpNoMoreWin2KDomain() )
    {
      goto LABEL_55;
    }
    SessionKeySafe = LsaDbpVerifyTrustLocation((struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *)a3);
    if ( SessionKeySafe < 0 )
      goto LABEL_56;
    if ( (a3[1].IncomingAuthInfos & 0x20) == 0 || (a3[1].IncomingAuthInfos & 0x18) == 0 )
    {
      hMem = &a3[1].IncomingAuthenticationInformation;
      LsapDbInitializeAttribute(v106, 36, &a3[1].IncomingAuthenticationInformation);
      v107 = *((_DWORD *)LsaDbpDsAttInfo + 108);
      v108 = *((_DWORD *)LsaDbpDsAttInfo + 109);
      LsapDbInitializeAttribute(v109, 38, (char *)&a3->OutgoingPreviousAuthenticationInformation + 4);
      LOBYTE(v79) = 0;
      v110 = *((_DWORD *)LsaDbpDsAttInfo + 114);
      v111 = *((_DWORD *)LsaDbpDsAttInfo + 115);
      LsapDbInitializeAttribute(v112, 39, &a3->OutgoingPreviousAuthenticationInformation);
      v81 = 3;
      v113 = *((_DWORD *)LsaDbpDsAttInfo + 117);
      v114 = *((_DWORD *)LsaDbpDsAttInfo + 118);
      if ( (unsigned int)(HIDWORD(a3->OutgoingPreviousAuthenticationInformation) - 1) <= 1
        && (*(_BYTE *)p_IncomingAuthInfos & 2) != 0
        && !a3->OutgoingAuthenticationInformation
        && !*((_QWORD *)v5 + 4) )
      {
        goto LABEL_73;
      }
      v46 = a3->OutgoingAuthenticationInformation;
      if ( v46 )
      {
        SessionKeySafe = LsaDbpMakeSidAttributeDs(v46, 33, v115);
        if ( SessionKeySafe < 0 )
          goto LABEL_56;
        v47 = &v116;
        v81 = 4;
      }
      else
      {
        v47 = v115;
      }
      LODWORD(v7) = *p_IncomingAuthInfos;
      LOBYTE(v79) = 0;
      v91 = a3[1].IncomingAuthInfos & 0xFF03FFFF;
      LsapDbInitializeAttribute(v47, 40, &v91);
      v48 = LsaDbpDsAttInfo;
      p_IncomingPreviousAuthenticationInformation = (struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)&a3[1].IncomingPreviousAuthenticationInformation;
      LODWORD(p_IncomingAuthInfos) = ++v81;
      *((_DWORD *)v47 + 8) = *((_DWORD *)LsaDbpDsAttInfo + 120);
      *((_DWORD *)v47 + 9) = *((_DWORD *)v48 + 121);
      if ( LODWORD(a3[1].IncomingPreviousAuthenticationInformation) )
      {
        if ( v82 == TrustedDomainFullInformation
          && !v96[133]
          && *(_DWORD *)p_IncomingPreviousAuthenticationInformation > 1u )
        {
          SessionKeySafe = -1073741811;
          goto LABEL_57;
        }
        SessionKeySafe = LsaDbpDsBuildAuthInfoAttribute(
                           v48,
                           p_IncomingPreviousAuthenticationInformation,
                           (union _LSAPR_TRUSTED_DOMAIN_INFO *)((char *)v5 + 72),
                           &v97,
                           &v92);
        if ( SessionKeySafe < 0 )
          goto LABEL_57;
      }
      p_OutgoingPreviousAuthenticationInformation = &a3[1].OutgoingPreviousAuthenticationInformation;
      if ( !LODWORD(a3[1].OutgoingPreviousAuthenticationInformation) )
        goto LABEL_126;
      if ( v96[133] || *(_DWORD *)p_OutgoingPreviousAuthenticationInformation <= 1u )
      {
        v51 = 0;
        if ( v5 != (union _LSAPR_TRUSTED_DOMAIN_INFO *)-72LL )
          v51 = (union _LSAPR_TRUSTED_DOMAIN_INFO *)((char *)v5 + 96);
        SessionKeySafe = LsaDbpDsBuildAuthInfoAttribute(
                           v48,
                           (struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)((unsigned __int64)p_OutgoingPreviousAuthenticationInformation
                                                                       & -(__int64)(&a3[1].IncomingPreviousAuthenticationInformation != 0)),
                           v51,
                           &v84,
                           &v89);
        if ( SessionKeySafe < 0 )
          goto LABEL_56;
LABEL_126:
        v34 = v47 + 40;
        LOBYTE(v7) = (unsigned __int8)v7 & 1;
        v83 = 1;
        v32 = 1;
        if ( LODWORD(a3[1].IncomingPreviousAuthenticationInformation) )
        {
          LOBYTE(v79) = 0;
          LsapDbInitializeAttribute(v34, 43, v97);
          v52 = LsaDbpDsAttInfo;
          *((_DWORD *)v34 + 8) = *((_DWORD *)LsaDbpDsAttInfo + 129);
          *((_DWORD *)v34 + 9) = *((_DWORD *)v52 + 130);
          v34 += 40;
          ++v81;
        }
        if ( *(_DWORD *)p_OutgoingPreviousAuthenticationInformation )
        {
          LOBYTE(v79) = 0;
          LsapDbInitializeAttribute(v34, 44, v84);
          v53 = LsaDbpDsAttInfo;
          v54 = v81;
          *((_DWORD *)v34 + 8) = *((_DWORD *)LsaDbpDsAttInfo + 132);
          *((_DWORD *)v34 + 9) = *((_DWORD *)v53 + 133);
          v34 += 40;
          LODWORD(p_IncomingAuthInfos) = v54 + 1;
          v81 = (int)p_IncomingAuthInfos;
        }
        else
        {
          LODWORD(p_IncomingAuthInfos) = v81;
        }
        if ( (*((_BYTE *)v5 + 48) & 8) == 0 )
          goto LABEL_157;
        if ( (a3[1].IncomingAuthInfos & 8) != 0 )
          goto LABEL_157;
        LOBYTE(v79) = 0;
        LsapDbInitializeAttribute(v34, 45, 0);
        v55 = LsaDbpDsAttInfo;
        *((_DWORD *)v34 + 8) = *((_DWORD *)LsaDbpDsAttInfo + 135);
        *((_DWORD *)v34 + 9) = *((_DWORD *)v55 + 136);
        v34 += 40;
        LODWORD(p_IncomingAuthInfos) = (_DWORD)p_IncomingAuthInfos + 1;
        *(_DWORD *)(&v99[3].MaximumLength + 1) = 0;
        v81 = (int)p_IncomingAuthInfos;
        v99[3].Buffer = 0;
        v36 = WPP_GLOBAL_Control;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
          goto LABEL_157;
        v37 = 24;
        goto LABEL_83;
      }
    }
LABEL_65:
    SessionKeySafe = -1073741811;
    goto LABEL_56;
  }
  if ( v82 != TrustedDomainAuthInformationInternal )
  {
    if ( v82 == TrustedDomainFullInformationInternal )
    {
LABEL_94:
      SessionKeySafe = LsaDbpDecryptAuthDataWithSessionKey(
                         (struct _LSAP_CR_CIPHER_KEY *)v98[0],
                         v80[0],
                         v82,
                         (union _LSAPR_TRUSTED_DOMAIN_INFO *)a3,
                         &v105);
      if ( SessionKeySafe < 0 )
        goto LABEL_58;
      v38 = *(_OWORD *)&a3->IncomingAuthInfos;
      v39 = *(_OWORD *)&a3->IncomingPreviousAuthenticationInformation;
      IncomingAuthenticationInformation = (int)a3[1].IncomingAuthenticationInformation;
      v102[0] = v38;
      v40 = *(_OWORD *)&a3->OutgoingAuthenticationInformation;
      v102[1] = v39;
      *(_QWORD *)&v39 = *(_QWORD *)&a3[1].IncomingAuthInfos;
      a3 = (struct _TRUSTED_DOMAIN_AUTH_INFORMATION *)v102;
      v102[2] = v40;
      v103 = v39;
      goto LABEL_96;
    }
    if ( v82 == TrustedDomainSupportedEncryptionTypes )
    {
      LOBYTE(v79) = 0;
      LsapDbInitializeAttribute(v106, 47, a3);
      v81 = 1;
      v107 = *((_DWORD *)LsaDbpDsAttInfo + 141);
      v108 = *((_DWORD *)LsaDbpDsAttInfo + 142);
      goto LABEL_176;
    }
    if ( v82 != (TrustedDomainFullInformation2Internal|TrustedControllersInformation) )
    {
      if ( v82 != (TrustedDomainSupportedEncryptionTypes|TrustedControllersInformation) )
        goto LABEL_91;
      goto LABEL_94;
    }
  }
  v56 = (union _LSAPR_TRUSTED_DOMAIN_INFO *)a3;
  v57 = v80[0];
  SessionKeySafe = LsaDbpDecryptAuthDataWithSessionKey((struct _LSAP_CR_CIPHER_KEY *)v98[0], v80[0], v82, v56, &v101);
  if ( SessionKeySafe >= 0 )
  {
    a3 = &v101;
LABEL_137:
    if ( a3->IncomingAuthInfos )
    {
      if ( v4 == TrustedDomainAuthInformation && !v96[133] && a3->IncomingAuthInfos > 1 )
        goto LABEL_91;
      SessionKeySafe = LsaDbpDsBuildAuthInfoAttribute(
                         (void *)v22,
                         (struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)a3,
                         (union _LSAPR_TRUSTED_DOMAIN_INFO *)((char *)v5 + 72),
                         &v97,
                         &v92);
      if ( SessionKeySafe < 0 )
        goto LABEL_58;
    }
    p_OutgoingAuthInfos = &a3->OutgoingAuthInfos;
    if ( a3->OutgoingAuthInfos )
    {
      if ( !v96[133] && *p_OutgoingAuthInfos > 1 )
      {
        SessionKeySafe = -1073741811;
LABEL_146:
        LODWORD(p_IncomingAuthInfos) = v81;
        goto LABEL_58;
      }
      if ( v5 == (union _LSAPR_TRUSTED_DOMAIN_INFO *)-72LL )
        v59 = 0;
      else
        v59 = (union _LSAPR_TRUSTED_DOMAIN_INFO *)((char *)v5 + 96);
      SessionKeySafe = LsaDbpDsBuildAuthInfoAttribute(
                         (void *)v22,
                         (struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)&a3->OutgoingAuthInfos,
                         v59,
                         &v84,
                         &v89);
      if ( SessionKeySafe < 0 )
        goto LABEL_146;
    }
    v34 = v106;
    if ( a3->IncomingAuthInfos )
    {
      LOBYTE(v79) = 0;
      LsapDbInitializeAttribute(v106, 43, v97);
      v34 = v109;
      v81 = 1;
      v107 = *((_DWORD *)LsaDbpDsAttInfo + 129);
      v108 = *((_DWORD *)LsaDbpDsAttInfo + 130);
    }
    if ( *p_OutgoingAuthInfos )
    {
      LOBYTE(v79) = 0;
      LsapDbInitializeAttribute(v34, 44, v84);
      v60 = LsaDbpDsAttInfo;
      v61 = v81;
      *((_DWORD *)v34 + 8) = *((_DWORD *)LsaDbpDsAttInfo + 132);
      *((_DWORD *)v34 + 9) = *((_DWORD *)v60 + 133);
      v34 += 40;
      LODWORD(p_IncomingAuthInfos) = v61 + 1;
      v81 = (int)p_IncomingAuthInfos;
    }
    else
    {
      LODWORD(p_IncomingAuthInfos) = v81;
    }
    v32 = v83;
    LOBYTE(v7) = (*((_BYTE *)v5 + 40) & 1) != 0;
LABEL_157:
    if ( !(_DWORD)p_IncomingAuthInfos )
      goto LABEL_187;
    p_IncomingAuthInfos = (unsigned int *)hMem;
    if ( v32 )
      goto LABEL_160;
    goto LABEL_159;
  }
  v7 = v84;
LABEL_191:
  if ( (unsigned __int8)IsLsapAdtAuditingEnabledByLogonIdPresent() )
  {
    if ( SessionKeySafe >= 0 )
    {
      if ( (unsigned __int8)LsapAdtAuditingEnabledHint(141, 8) )
      {
        LsaDbpAdtTrustedDomainMod(
          v74,
          *((void **)v5 + 4),
          (struct _UNICODE_STRING *)v5,
          v75,
          v79,
          *((_DWORD *)v5 + 12),
          v99,
          HIDWORD(v99[2].Buffer),
          (unsigned int)v99[2].Buffer,
          *(unsigned int *)&v99[3].Length);
        if ( !v57 && (unsigned int)(v4 - 9) <= 1 )
          LsaDbpAdtTrustedDomainModAuthInfoWithLegacyRPCMethod(
            (struct _UNICODE_STRING *)(v96 + 56),
            *((void **)v96 + 11));
      }
    }
  }
  if ( v86 )
    LsapDbDereferenceHandle(v88, SessionKeySafe >= 0);
  if ( v98[0] )
    LocalFree(v98[0]);
  v76 = 0;
  for ( i = (HLOCAL *)v106; v76 < (unsigned int)p_IncomingAuthInfos; ++v76 )
  {
    if ( *((_BYTE *)i + 28) )
      LocalFree(i[2]);
    i += 5;
  }
  if ( v87 )
    SessionKeySafe = LsapDbDereferenceObject(&v88, 2, 2, v8, 7, SessionKeySafe);
  if ( v5 )
    LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO(12, v5);
  if ( v100 )
    LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO(13, v100);
  if ( v85 )
    LsapDbExpReleaseLockTrustedDomainList();
  if ( v97 )
    LsapFreeLsaHeap(v97, v72, v73);
  if ( v7 )
    LsapFreeLsaHeap(v7, v72, v73);
  LsaDbpDsFreeUnmarshalAuthInfoHalf((struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)&v101);
  LsaDbpDsFreeUnmarshalAuthInfoHalf((struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)&v101.OutgoingAuthInfos);
  LsaDbpDsFreeUnmarshalAuthInfoHalf((struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)&v105);
  LsaDbpDsFreeUnmarshalAuthInfoHalf((struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)&v105.OutgoingAuthInfos);
  LsapTraceEvent(2, 10);
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids,
      (unsigned int)SessionKeySafe);
  return (unsigned int)SessionKeySafe;
}

```

## disassembly

```asm
0x18000e9f0  mov     [rsp-8+arg_18], rbx
0x18000e9f5  push    rbp
0x18000e9f6  push    rsi
0x18000e9f7  push    rdi
0x18000e9f8  push    r12
0x18000e9fa  push    r13
0x18000e9fc  push    r14
0x18000e9fe  push    r15
0x18000ea00  lea     rbp, [rsp-340h]
0x18000ea08  sub     rsp, 440h
0x18000ea0f  mov     rax, cs:__security_cookie
0x18000ea16  xor     rax, rsp
0x18000ea19  mov     [rbp+370h+var_40], rax
0x18000ea20  xor     ebx, ebx
0x18000ea22  mov     [rsp+470h+var_418], edx
0x18000ea26  xorps   xmm0, xmm0
0x18000ea29  mov     [rbp+370h+var_3D0], rcx
0x18000ea2d  mov     rsi, r8
0x18000ea30  mov     [rsp+470h+var_400], rcx
0x18000ea35  mov     r14d, edx
0x18000ea38  mov     [rbp+370h+var_3E0], ebx
0x18000ea3b  movups  xmmword ptr [rbp+370h+var_38E], xmm0
0x18000ea3f  lea     r8d, [rbx+70h]; Size
0x18000ea43  mov     [rsp+470h+var_406], bl
0x18000ea47  xor     edx, edx; Val
0x18000ea49  mov     [rsp+470h+var_408], bl
0x18000ea4d  lea     rcx, [rbp+370h+var_330]; void *
0x18000ea51  mov     [rbp+370h+var_3D8], rbx
0x18000ea55  mov     r15d, ebx
0x18000ea58  mov     [rbp+370h+var_3B0.Length], bx
0x18000ea5c  movups  xmmword ptr [rbp+370h+var_3B0.MaximumLength], xmm0
0x18000ea60  mov     [rbp+370h+var_370], rbx
0x18000ea64  movups  [rbp+370h+var_39E], xmm0
0x18000ea68  movups  xmmword ptr [rbp+370h+var_38E+0Eh], xmm0
0x18000ea6c  call    memset_0
0x18000ea71  lea     eax, [rbx+1]
0x18000ea74  mov     [rsp+470h+var_41C], ebx
0x18000ea78  mov     ecx, eax
0x18000ea7a  mov     [rsp+470h+var_3F4], ebx
0x18000ea7e  lea     edx, [rbx+0Ah]
0x18000ea81  mov     [rbp+370h+var_3C8], rbx
0x18000ea85  mov     r12d, ebx
0x18000ea88  mov     [rsp+470h+var_410], rbx
0x18000ea8d  mov     r13d, ebx
0x18000ea90  mov     [rbp+370h+var_3EC], ebx
0x18000ea93  mov     [rsp+470h+var_3F8], ebx
0x18000ea97  lea     edi, [rbx+11h]
0x18000ea9a  mov     [rsp+470h+var_407], bl
0x18000ea9e  mov     [rbp+370h+var_3C0], rbx
0x18000eaa2  mov     [rbp+370h+var_3F0], ebx
0x18000eaa5  mov     [rsp+470h+var_420], al
0x18000eaa9  mov     [rbp+370h+hMem], rbx
0x18000eaad  call    cs:__imp_LsapTraceEvent
0x18000eab3  mov     rax, cs:WPP_GLOBAL_Control
0x18000eaba  test    dword ptr [rax+1Ch], 100h
0x18000eac1  jz      short loc_18000EB33
0x18000eac3  mov     rcx, [rax+10h]
0x18000eac7  lea     edx, [rbx+15h]
0x18000eaca  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x18000ead1  call    WPP_SF_
0x18000ead6  mov     rax, cs:WPP_GLOBAL_Control
0x18000eadd  test    dword ptr [rax+1Ch], 100h
0x18000eae4  jz      short loc_18000EB33
0x18000eae6  cmp     byte ptr [rax+19h], 4
0x18000eaea  jb      short loc_18000EB33
0x18000eaec  lea     rdx, [rbp+370h+hMem]; unsigned __int16 **
0x18000eaf0  call    ?LsaDbGetCallerInfo@@YAXPEAXPEAPEAG@Z; LsaDbGetCallerInfo(void *,ushort * *)
0x18000eaf5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eafc  mov     rbx, [rbp+370h+hMem]
0x18000eb00  test    dword ptr [rcx+1Ch], 100h
0x18000eb07  jz      short loc_18000EB2A
0x18000eb09  mov     rcx, [rcx+10h]
0x18000eb0d  lea     r9, aUnknown_0; "Unknown"
0x18000eb14  test    rbx, rbx
0x18000eb17  lea     edx, [rdi+5]
0x18000eb1a  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x18000eb21  cmovnz  r9, rbx
0x18000eb25  call    WPP_SF_S
0x18000eb2a  mov     rcx, rbx; hMem
0x18000eb2d  call    cs:__imp_LocalFree
0x18000eb33  xorps   xmm0, xmm0
0x18000eb36  lea     rcx, [rbp+370h+var_330]; void *
0x18000eb3a  xor     edx, edx; Val
0x18000eb3c  movups  xmmword ptr [rbp+370h+var_368.IncomingAuthInfos], xmm0
0x18000eb40  movups  xmmword ptr [rbp+370h+var_368.IncomingPreviousAuthenticationInformation], xmm0
0x18000eb44  lea     r8d, [rdx+70h]; Size
0x18000eb48  movups  xmmword ptr [rbp+370h+var_368.OutgoingAuthenticationInformation], xmm0
0x18000eb4c  call    memset_0
0x18000eb51  mov     rax, [rsp+470h+var_400]
0x18000eb56  mov     ecx, r14d
0x18000eb59  mov     [rbp+370h+hMem], rax
0x18000eb5d  sub     ecx, 3
0x18000eb60  jz      short loc_18000EB8E
0x18000eb62  sub     ecx, 3
0x18000eb65  jz      short loc_18000EB8E
0x18000eb67  sub     ecx, 1
0x18000eb6a  jz      short loc_18000EB8E
0x18000eb6c  sub     ecx, 1
0x18000eb6f  jz      short loc_18000EB8E
0x18000eb71  sub     ecx, 1
0x18000eb74  jz      short loc_18000EB8E
0x18000eb76  sub     ecx, 1
0x18000eb79  jz      short loc_18000EB8E
0x18000eb7b  sub     ecx, 3
0x18000eb7e  jz      short loc_18000EB8E
0x18000eb80  sub     ecx, 1
0x18000eb83  jz      short loc_18000EB8E
0x18000eb85  cmp     ecx, 1
0x18000eb88  jnz     loc_18000F924
0x18000eb8e  lea     rcx, [rbp+370h+hMem]; void **
0x18000eb92  call    ?LsapValidateLsaprHandle@@YAEPEAPEAX@Z; LsapValidateLsaprHandle(void * *)
0x18000eb97  test    al, al
0x18000eb99  jz      loc_18000F924
0x18000eb9f  mov     edx, r14d; enum _TRUSTED_INFORMATION_CLASS
0x18000eba2  mov     rcx, rsi; union _LSAPR_TRUSTED_DOMAIN_INFO *
0x18000eba5  call    ?LsaDbpValidateLsaprTrustedDomainInfo@@YAEPEAT_LSAPR_TRUSTED_DOMAIN_INFO@@W4_TRUSTED_INFORMATION_CLASS@@@Z; LsaDbpValidateLsaprTrustedDomainInfo(_LSAPR_TRUSTED_DOMAIN_INFO *,_TRUSTED_INFORMATION_CLASS)
0x18000ebaa  test    al, al
0x18000ebac  jz      loc_18000F924
0x18000ebb2  lea     r9, [rbp+370h+var_3E0]
0x18000ebb6  xor     r8d, r8d
0x18000ebb9  mov     rdx, rsi
0x18000ebbc  mov     ecx, r14d
0x18000ebbf  call    cs:__imp_LsapDbVerifyInfoSetTrustedDomain
0x18000ebc5  mov     ebx, eax
0x18000ebc7  test    eax, eax
0x18000ebc9  js      loc_18000F929
0x18000ebcf  mov     rcx, [rsp+470h+var_400]
0x18000ebd4  xor     edx, edx
0x18000ebd6  mov     r9b, 1
0x18000ebd9  lea     r8d, [rdx+2]
0x18000ebdd  call    cs:__imp_LsapDbVerifyHandle
0x18000ebe3  mov     ebx, eax
0x18000ebe5  test    eax, eax
0x18000ebe7  js      loc_18000F929
0x18000ebed  mov     r10, [rsp+470h+var_400]
0x18000ebf2  mov     r8d, 1
0x18000ebf8  mov     [rsp+470h+var_407], r8b
0x18000ebfd  mov     edx, [r10+88h]
0x18000ec04  and     edx, 400000h
0x18000ec0a  mov     eax, edx
0x18000ec0c  neg     eax
0x18000ec0e  sbb     ecx, ecx
0x18000ec10  and     ecx, 0FFFFFFF0h
0x18000ec13  add     edi, ecx
0x18000ec15  mov     ecx, [rsp+470h+var_418]
0x18000ec19  neg     edx
0x18000ec1b  sbb     r14d, r14d
0x18000ec1e  and     r14d, 0FFFFFFF8h
0x18000ec22  lea     eax, [rcx-9]
0x18000ec25  add     r14d, 9
0x18000ec29  cmp     eax, r8d
0x18000ec2c  jbe     short loc_18000EC36
0x18000ec2e  lea     eax, [rcx-0Eh]
0x18000ec31  cmp     eax, r8d
0x18000ec34  ja      short loc_18000EC80
0x18000ec36  lea     rcx, [rsp+470h+var_420]; unsigned __int8 *
0x18000ec3b  call    ?LsaDbpIsCallLocal@@YAJPEAE@Z; LsaDbpIsCallLocal(uchar *)
0x18000ec40  mov     ebx, eax
0x18000ec42  test    eax, eax
0x18000ec44  js      short loc_18000EC6B
0x18000ec46  cmp     [rsp+470h+var_420], r12b
0x18000ec4b  jnz     short loc_18000EC75
0x18000ec4d  mov     rcx, [rsp+470h+var_400]
0x18000ec52  lea     r8, [rbp+370h+var_3C0]
0x18000ec56  mov     edx, 1
0x18000ec5b  mov     rcx, [rcx+70h]
0x18000ec5f  call    cs:__imp_LsapCrServerGetSessionKeySafe
0x18000ec65  mov     ebx, eax
0x18000ec67  test    eax, eax
0x18000ec69  jns     short loc_18000EC75
0x18000ec6b  mov     r14d, [rsp+470h+var_418]
0x18000ec70  jmp     loc_18000F929
0x18000ec75  mov     r10, [rsp+470h+var_400]
0x18000ec7a  mov     r8d, 1
0x18000ec80  test    dword ptr [r10+88h], 400000h
0x18000ec8b  jnz     short loc_18000ECBF
0x18000ec8d  mov     edx, [rbp+370h+var_3E0]
0x18000ec90  mov     eax, 2
0x18000ec95  mov     r9d, eax
0x18000ec98  mov     dword ptr [rsp+470h+var_450], r14d
0x18000ec9d  mov     r8d, eax
0x18000eca0  mov     rcx, r10
0x18000eca3  call    cs:__imp_LsapDbReferenceObject
0x18000eca9  mov     ebx, eax
0x18000ecab  test    eax, eax
0x18000ecad  js      short loc_18000EC6B
0x18000ecaf  mov     r10, [rsp+470h+var_400]
0x18000ecb4  mov     r8d, 1
0x18000ecba  mov     [rsp+470h+var_406], r8b
0x18000ecbf  mov     r14b, [r10+85h]
0x18000ecc6  mov     edx, 0Ch; enum _TRUSTED_INFORMATION_CLASS
0x18000eccb  mov     [r10+85h], r8b
0x18000ecd2  lea     r8, [rbp+370h+var_3D8]; union _LSAPR_TRUSTED_DOMAIN_INFO **
0x18000ecd6  mov     rcx, [rsp+470h+var_400]; void *
0x18000ecdb  call    ?LsaDbrQueryInfoTrustedDomain@@YAJPEAXW4_TRUSTED_INFORMATION_CLASS@@PEAPEAT_LSAPR_TRUSTED_DOMAIN_INFO@@@Z; LsaDbrQueryInfoTrustedDomain(void *,_TRUSTED_INFORMATION_CLASS,_LSAPR_TRUSTED_DOMAIN_INFO * *)
0x18000ece0  mov     ebx, eax
0x18000ece2  test    eax, eax
0x18000ece4  js      short loc_18000ED11
0x18000ece6  mov     r15, [rbp+370h+var_3D8]
0x18000ecea  lea     r8, [rbp+370h+var_3D8]; union _LSAPR_TRUSTED_DOMAIN_INFO **
0x18000ecee  mov     rcx, [rsp+470h+var_400]; void *
0x18000ecf3  mov     edx, 0Dh; enum _TRUSTED_INFORMATION_CLASS
0x18000ecf8  mov     [rbp+370h+var_3D8], r12
0x18000ecfc  call    ?LsaDbrQueryInfoTrustedDomain@@YAJPEAXW4_TRUSTED_INFORMATION_CLASS@@PEAPEAT_LSAPR_TRUSTED_DOMAIN_INFO@@@Z; LsaDbrQueryInfoTrustedDomain(void *,_TRUSTED_INFORMATION_CLASS,_LSAPR_TRUSTED_DOMAIN_INFO * *)
0x18000ed01  mov     ebx, eax
0x18000ed03  mov     rax, r12
0x18000ed06  test    ebx, ebx
0x18000ed08  cmovns  rax, [rbp+370h+var_3D8]
0x18000ed0d  mov     [rbp+370h+var_370], rax
0x18000ed11  mov     rax, [rsp+470h+var_400]
0x18000ed16  mov     [rax+85h], r14b
0x18000ed1d  test    ebx, ebx
0x18000ed1f  js      loc_18000EC6B
0x18000ed25  cmp     byte ptr cs:word_18004706B+1, r12b
0x18000ed2c  movups  xmm0, xmmword ptr [r15]
0x18000ed30  movaps  xmmword ptr [rbp+370h+var_3B0.Length], xmm0
0x18000ed34  movups  xmm1, xmmword ptr [r15+10h]
0x18000ed39  movaps  xmmword ptr [rbp-30h], xmm1
0x18000ed3d  movups  xmm0, xmmword ptr [r15+20h]
0x18000ed42  movaps  [rbp+370h+var_39E+0Eh], xmm0
0x18000ed46  movups  xmm1, xmmword ptr [r15+30h]
0x18000ed4b  movaps  xmmword ptr [rbp+370h+var_38E+0Eh], xmm1
0x18000ed4f  jz      short loc_18000EDA2
0x18000ed51  mov     rax, [rsp+470h+var_400]
0x18000ed56  cmp     [rax+58h], r12
0x18000ed5a  jnz     short loc_18000EDA2
0x18000ed5c  mov     rcx, [r15+20h]; Sid
0x18000ed60  test    rcx, rcx
0x18000ed63  jz      short loc_18000EDA2
0x18000ed65  call    cs:__imp_RtlLengthSid
0x18000ed6b  mov     ecx, eax
0x18000ed6d  mov     ebx, eax
0x18000ed6f  call    cs:__imp_LsapAllocateLsaHeap
0x18000ed75  mov     rcx, [rsp+470h+var_400]
0x18000ed7a  mov     [rcx+58h], rax
0x18000ed7e  mov     rcx, [rsp+470h+var_400]
0x18000ed83  mov     rdx, [rcx+58h]; DestinationSid
0x18000ed87  test    rdx, rdx
0x18000ed8a  jnz     short loc_18000ED96
0x18000ed8c  mov     ebx, 0C000009Ah
0x18000ed91  jmp     loc_18000EC6B
0x18000ed96  mov     r8, [r15+20h]; SourceSid
0x18000ed9a  mov     ecx, ebx; DestinationSidLength
0x18000ed9c  call    cs:__imp_RtlCopySid
0x18000eda2  mov     r14d, [rsp+470h+var_418]
0x18000eda7  xor     bl, bl
0x18000eda9  mov     [rsp+470h+var_414], bl
0x18000edad  mov     [rbp+370h+hMem], r12
0x18000edb1  cmp     r14d, 8
0x18000edb5  jg      loc_18000F124
0x18000edbb  jz      loc_18000F1EF
0x18000edc1  mov     ecx, r14d
0x18000edc4  sub     ecx, 1
0x18000edc7  jz      loc_18000F148
0x18000edcd  sub     ecx, 1
0x18000edd0  jz      loc_18000F148
0x18000edd6  sub     ecx, 1
0x18000edd9  jz      loc_18000F0CB
0x18000eddf  sub     ecx, 2
0x18000ede2  jz      loc_18000F148
0x18000ede8  sub     ecx, 1
0x18000edeb  jz      short loc_18000EDFB
0x18000eded  cmp     ecx, 1
0x18000edf0  jz      loc_18000F61E
0x18000edf6  jmp     loc_18000F148
0x18000edfb  movzx   eax, word ptr [rsi]
0x18000edfe  lea     r12, [rsi+28h]
0x18000ee02  movups  xmm0, xmmword ptr [rsi+2]
0x18000ee06  mov     ecx, [rsi+30h]
0x18000ee09  lea     r14, [rsi+2Ch]
0x18000ee0d  movups  xmm1, xmmword ptr [rsi+12h]
0x18000ee11  mov     [rbp+370h+var_3B0.Length], ax
0x18000ee15  mov     eax, [r12]
0x18000ee19  mov     [rbp+370h+var_38E+6], eax
0x18000ee1c  mov     eax, [r14]
0x18000ee1f  movups  xmmword ptr [rbp+370h+var_3B0.MaximumLength], xmm0
0x18000ee23  mov     [rbp+370h+var_38E+0Ah], eax
0x18000ee26  mov     eax, [rsi+34h]
0x18000ee29  movsd   xmm0, qword ptr [rsi+20h]
0x18000ee2e  movups  [rbp+370h+var_39E], xmm1
0x18000ee32  mov     [rbp+370h+var_37C], eax
0x18000ee35  movsd   qword ptr [rbp+370h+var_39E+0Eh], xmm0
0x18000ee3a  mov     [rbp+370h+var_38E+0Eh], ecx
0x18000ee3d  mov     eax, [r15+34h]
0x18000ee41  mov     [rbp+370h+var_37C], eax
0x18000ee44  mov     rax, [r15+38h]
0x18000ee48  mov     [rbp+370h+var_378], rax
0x18000ee4c  test    byte ptr [r15+30h], 8
0x18000ee51  jnz     short loc_18000EE82
0x18000ee53  test    cl, 8
0x18000ee56  jz      short loc_18000EE82
0x18000ee58  cmp     cs:?DcInRootDomain@@3EA, bl; uchar DcInRootDomain
0x18000ee5e  jz      short loc_18000EE69
0x18000ee60  call    ?LsaDbpNoMoreWin2KForest@@YAEXZ; LsaDbpNoMoreWin2KForest(void)
0x18000ee65  test    al, al
0x18000ee67  jnz     short loc_18000EE82
0x18000ee69  mov     ebx, 0C00000DDh
0x18000ee6e  mov     r12d, [rsp+470h+var_41C]
0x18000ee73  mov     r14d, [rsp+470h+var_418]
0x18000ee78  mov     r13, [rsp+470h+var_410]
  ... truncated ...
```
