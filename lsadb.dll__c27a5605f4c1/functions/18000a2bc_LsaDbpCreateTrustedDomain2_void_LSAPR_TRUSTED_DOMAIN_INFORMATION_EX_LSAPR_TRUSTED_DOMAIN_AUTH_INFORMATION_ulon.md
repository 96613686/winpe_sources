# LsaDbpCreateTrustedDomain2(void *,_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *,_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION *,ulong,void * *)

- ea: `0x18000a2bc`
- end: `0x18000af12`
- name: `?LsaDbpCreateTrustedDomain2@@YAJPEAXPEAU_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX@@PEAU_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION@@KPEAPEAX@Z`
- size: `3158`
- prototype: `__int64 __fastcall(void *, struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *, struct _LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION *, unsigned int, void **)`
- caller_count: `4`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000cf30`
- `0x18000d000`
- `0x18000d210`
- `0x18000d3f0`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x180002234`
- `0x1800099b4`
- `0x18000a0dc`
- `0x18000a2bc`
- `0x18000bae8`
- `0x18000bdfc`
- `0x18000beb4`
- `0x18000c080`
- `0x18000c0e0`
- `0x18000cd2c`
- `0x18000fd18`
- `0x18000fd40`
- `0x180017de8`
- `0x180018084`
- `0x1800209d0`
- `0x180020a18`
- `0x180028510`
- `0x18002fdb0`
- `0x1800311f8`
- `0x180033d80`
- `0x180035448`
- `0x1800355c4`
- `0x1800359a4`
- `0x18003a110`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aca0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000acab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000adcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000adfe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aca0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000acab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000adcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000adfe`
- `LSASRV!LsarDeleteObject` at `0x18000aec5`
- `LSASRV!LsarDeleteObject` at `0x18000aec5`
- `LSASRV!LsapDbDereferenceObject` at `0x18000aea7`
- `LSASRV!LsapDbDereferenceObject` at `0x18000aea7`
- `LSASRV!LsapDbFreeAttributes` at `0x18000ad4c`
- `LSASRV!LsapDbFreeAttributes` at `0x18000ad4c`
- `LSASRV!LsapDbReleaseLockEx` at `0x18000ad0c`
- `LSASRV!LsapDbReleaseLockEx` at `0x18000ad3e`
- `LSASRV!LsapDbReleaseLockEx` at `0x18000ad0c`
- `LSASRV!LsapDbReleaseLockEx` at `0x18000ad3e`
- `LSASRV!LsapDbApplyTransaction` at `0x18000ad01`
- `LSASRV!LsapDbApplyTransaction` at `0x18000ad01`
- `LSASRV!LsapGetGlobalRestrictAnonymous` at `0x18000ab70`
- `LSASRV!LsapGetGlobalRestrictAnonymous` at `0x18000ab70`
- `LSASRV!LsapDbCreateObject` at `0x18000ab58`
- `LSASRV!LsapDbCreateObject` at `0x18000ab58`
- `LSASRV!LsapDbSidToLogicalNameObject` at `0x18000a900`
- `LSASRV!LsapDbSidToLogicalNameObject` at `0x18000a900`
- `LSASRV!LsapGetAccountDomainHandle` at `0x18000a857`
- `LSASRV!LsapGetAccountDomainHandle` at `0x18000a857`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000a810`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000a8bb`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000a9a8`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000a9de`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000aa23`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000aa8d`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000aafd`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000a810`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000a8bb`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000a9a8`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000a9de`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000aa23`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000aa8d`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000aafd`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x18000a739`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x18000a739`
- `LSASRV!LsapDbReferenceObject` at `0x18000a721`
- `LSASRV!LsapDbReferenceObject` at `0x18000a721`
- `LSASRV!LsapDbAcquireLockEx` at `0x18000a701`
- `LSASRV!LsapDbAcquireLockEx` at `0x18000a701`
- `LSASRV!LsapRemoveTrailingDot` at `0x18000a487`
- `LSASRV!LsapRemoveTrailingDot` at `0x18000a492`
- `LSASRV!LsapRemoveTrailingDot` at `0x18000a4bd`
- `LSASRV!LsapRemoveTrailingDot` at `0x18000a4d0`
- `LSASRV!LsapRemoveTrailingDot` at `0x18000a487`
- `LSASRV!LsapRemoveTrailingDot` at `0x18000a492`
- `LSASRV!LsapRemoveTrailingDot` at `0x18000a4bd`
- `LSASRV!LsapRemoveTrailingDot` at `0x18000a4d0`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x18000a87c`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x18000ac15`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x18000a87c`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x18000ac15`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18000a767`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18000a793`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18000ac33`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18000ad80`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18000a767`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18000a793`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18000ac33`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18000ad80`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x18000ad28`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x18000ad28`
- `LSASRV!LsapDbQueryInformationPolicy` at `0x18000a5af`
- `LSASRV!LsapDbQueryInformationPolicy` at `0x18000a5af`
- `ntdll!RtlFreeUnicodeString` at `0x18000ad6e`
- `ntdll!RtlFreeUnicodeString` at `0x18000ad6e`
- `ntdll!RtlEqualUnicodeString` at `0x18000a609`
- `ntdll!RtlEqualUnicodeString` at `0x18000a627`
- `ntdll!RtlEqualUnicodeString` at `0x18000a64a`
- `ntdll!RtlEqualUnicodeString` at `0x18000a668`
- `ntdll!RtlEqualUnicodeString` at `0x18000a609`
- `ntdll!RtlEqualUnicodeString` at `0x18000a627`
- `ntdll!RtlEqualUnicodeString` at `0x18000a64a`
- `ntdll!RtlEqualUnicodeString` at `0x18000a668`
- `ntdll!RtlEqualSid` at `0x18000a5d4`
- `ntdll!RtlEqualSid` at `0x18000a5d4`
- `SAMSRV!SamIQueryServerRole` at `0x18000a865`
- `SAMSRV!SamIQueryServerRole` at `0x18000a865`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledHint` at `0x18000accc`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledHint` at `0x18000accc`

## pseudocode

```c
__int64 __fastcall LsaDbpCreateTrustedDomain2(
        void *a1,
        struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *a2,
        struct _LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION *a3,
        unsigned int a4,
        void **a5)
{
  void **v5; // r14
  unsigned __int8 v7; // r15
  char v8; // r12
  __int64 v9; // rdx
  int IsValidDomainSid; // ebx
  unsigned __int16 v11; // ax
  unsigned __int16 *v12; // rsi
  unsigned __int16 v13; // ax
  unsigned int *v14; // r12
  unsigned __int64 v15; // rax
  void *v16; // r14
  PCUNICODE_STRING v17; // rax
  void *v18; // rdx
  int v19; // eax
  int v20; // eax
  __int64 v21; // rcx
  __int128 v22; // xmm0
  __int64 v23; // rcx
  __int128 v24; // xmm0
  int v25; // ebx
  __int64 v26; // rcx
  char *v27; // r15
  struct _LSAP_DB_HANDLE *v28; // rcx
  int v29; // eax
  unsigned int *v30; // r13
  bool v31; // zf
  __int64 AccountDomainHandle; // rax
  __int64 v33; // rcx
  struct _LSAP_DB_HANDLE *v34; // rcx
  int v35; // eax
  char v36; // cl
  int v37; // eax
  _DWORD *v38; // rbx
  struct _LSAP_DB_HANDLE *v39; // rcx
  int v40; // eax
  struct _LSAP_DB_HANDLE *v41; // rcx
  _DWORD *v42; // rsi
  int v43; // eax
  struct _LSAP_DB_HANDLE *v44; // rcx
  struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *v45; // r14
  struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *v46; // rdx
  int v47; // eax
  struct _LSAP_DB_HANDLE *v48; // rcx
  _DWORD *v49; // rsi
  struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *v50; // rdx
  struct _LSAP_DB_HANDLE *v51; // rcx
  int v52; // eax
  HLOCAL v53; // rsi
  _QWORD *v54; // r13
  __int128 v55; // xmm1
  __int128 v56; // xmm0
  __int64 v57; // rcx
  __int64 v58; // rcx
  unsigned __int16 v59; // cx
  __int64 v60; // rcx
  int v61; // edi
  unsigned __int8 v63; // [rsp+40h] [rbp-C0h] BYREF
  char v64; // [rsp+41h] [rbp-BFh]
  unsigned int v65; // [rsp+44h] [rbp-BCh]
  unsigned int v66; // [rsp+48h] [rbp-B8h]
  _QWORD *v67; // [rsp+50h] [rbp-B0h]
  HLOCAL v68; // [rsp+58h] [rbp-A8h] BYREF
  char v69; // [rsp+60h] [rbp-A0h]
  char v70; // [rsp+61h] [rbp-9Fh]
  HLOCAL hMem; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v72; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL v73; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v74; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v75; // [rsp+84h] [rbp-7Ch] BYREF
  PCUNICODE_STRING String2; // [rsp+88h] [rbp-78h] BYREF
  void *v77; // [rsp+90h] [rbp-70h] BYREF
  int v78; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v79; // [rsp+9Ch] [rbp-64h]
  unsigned int v80; // [rsp+A0h] [rbp-60h] BYREF
  HLOCAL v81; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v83; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v84; // [rsp+D0h] [rbp-30h]
  struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *v85; // [rsp+D8h] [rbp-28h]
  _DWORD v86[4]; // [rsp+E0h] [rbp-20h] BYREF
  void *v87; // [rsp+F0h] [rbp-10h]
  struct _UNICODE_STRING *p_UnicodeString; // [rsp+F8h] [rbp-8h]
  int v89; // [rsp+100h] [rbp+0h]
  __int64 v90; // [rsp+108h] [rbp+8h]
  __int64 v91; // [rsp+110h] [rbp+10h]
  void *v92; // [rsp+118h] [rbp+18h]
  char v93; // [rsp+120h] [rbp+20h]
  unsigned int v94; // [rsp+124h] [rbp+24h]
  _OWORD v95[3]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v96; // [rsp+160h] [rbp+60h]
  _BYTE v97[40]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v98[40]; // [rsp+198h] [rbp+98h] BYREF
  char v99; // [rsp+1C0h] [rbp+C0h] BYREF

  v5 = a5;
  v85 = a3;
  v77 = a1;
  v79 = a4;
  hMem = a5;
  v65 = 0;
  memset_0(v86, 0, 0x48u);
  v70 = 0;
  v69 = 0;
  UnicodeString = 0;
  v84 = 0;
  v7 = 0;
  v83 = 0;
  v66 = 0;
  v8 = 0;
  v74 = 0;
  v64 = 0;
  v73 = 0;
  v78 = 0;
  String2 = 0;
  v68 = 0;
  v80 = 0;
  v81 = 0;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids);
  UnicodeString.Length = 0;
  memset_0(v97, 0, 0x2F8u);
  v9 = 1;
  if ( !a2 )
    goto LABEL_156;
  if ( DcInRootDomain )
  {
    if ( (*((_BYTE *)a2 + 48) & 8) != 0 && !LsaDbpNoMoreWin2KForest() )
      goto LABEL_9;
  }
  else if ( (*((_BYTE *)a2 + 48) & 8) != 0 )
  {
    IsValidDomainSid = -1073741603;
LABEL_157:
    v15 = 0;
    goto LABEL_158;
  }
  if ( (*((_BYTE *)a2 + 48) & 0x10) != 0 && !LsaDbpNoMoreWin2KDomain() )
  {
LABEL_9:
    IsValidDomainSid = -1073741603;
    v9 = 1;
    goto LABEL_157;
  }
  v9 = 1;
  if ( !HIBYTE(word_18004706B) )
  {
    IsValidDomainSid = -1073741135;
    goto LABEL_157;
  }
  v11 = *((_WORD *)a2 + 1);
  if ( (v11 & 1) != 0 )
    *((_WORD *)a2 + 1) = --v11;
  if ( v11 < *(_WORD *)a2
    || (((unsigned __int8)*(_WORD *)a2 | (unsigned __int8)v11) & 1) != 0
    || *(_WORD *)a2 && !*((_QWORD *)a2 + 1) )
  {
    goto LABEL_156;
  }
  v12 = (unsigned __int16 *)((char *)a2 + 16);
  if ( a2 != (struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *)-16LL )
  {
    v13 = *((_WORD *)a2 + 9);
    if ( (v13 & 1) != 0 )
      *((_WORD *)a2 + 9) = --v13;
    if ( v13 < *v12 || (((unsigned __int8)*v12 | (unsigned __int8)v13) & 1) != 0 || *v12 && !*((_QWORD *)a2 + 3) )
    {
LABEL_156:
      IsValidDomainSid = -1073741811;
      goto LABEL_157;
    }
  }
  LsapRemoveTrailingDot(a2, 0);
  LsapRemoveTrailingDot((char *)a2 + 16, 0);
  if ( !LsaDbpValidateIsNonEmptyUnicodeString((const struct _UNICODE_STRING *)a2)
    || !LsaDbpValidateIsNonEmptyUnicodeString((const struct _UNICODE_STRING *)a2 + 1)
    || (unsigned __int8)LsapRemoveTrailingDot(a2, 0)
    || (unsigned __int8)LsapRemoveTrailingDot((char *)a2 + 16, 0) )
  {
    v9 = 1;
    goto LABEL_156;
  }
  v14 = (unsigned int *)((char *)a2 + 44);
  if ( (unsigned int)(*((_DWORD *)a2 + 11) - 1) > 1 )
    goto LABEL_36;
  v63 = 0;
  IsValidDomainSid = LsaDbpValidateNetbiosName((const struct _UNICODE_STRING *)a2 + 1, &v63);
  if ( IsValidDomainSid < 0 )
    goto LABEL_169;
  if ( v63 )
  {
LABEL_36:
    if ( *v14 != 2 )
    {
LABEL_39:
      v16 = (void *)*((_QWORD *)a2 + 4);
      if ( v16 )
      {
        IsValidDomainSid = LsaDbpIsValidDomainSid(*((PSID *)a2 + 4));
        if ( IsValidDomainSid < 0 )
          goto LABEL_154;
      }
      if ( !*((_BYTE *)v77 + 133) && !v16 )
      {
        v9 = 1;
        if ( *v14 - 1 <= 1 )
        {
          IsValidDomainSid = -1073741704;
          v15 = 0;
LABEL_45:
          v5 = (void **)hMem;
          v8 = v15;
          goto LABEL_158;
        }
      }
      IsValidDomainSid = LsapDbQueryInformationPolicy(LsaDbpPolicyHandle, 12, &String2);
      if ( IsValidDomainSid < 0 )
        goto LABEL_154;
      if ( v16 )
      {
        v17 = String2;
        v18 = *(void **)&String2[4].Length;
        if ( !v18 )
        {
LABEL_54:
          if ( *((_QWORD *)a2 + 1) )
          {
            if ( v17->Buffer )
            {
              if ( RtlEqualUnicodeString((PCUNICODE_STRING)a2, v17, 1u) )
                goto LABEL_50;
              v17 = String2;
            }
            if ( v17[1].Buffer )
            {
              if ( RtlEqualUnicodeString((PCUNICODE_STRING)a2, v17 + 1, 1u) )
                goto LABEL_50;
              v17 = String2;
            }
          }
          if ( *((_QWORD *)a2 + 3) )
          {
            if ( v17->Buffer )
            {
              if ( RtlEqualUnicodeString((PCUNICODE_STRING)a2 + 1, v17, 1u) )
                goto LABEL_50;
              v17 = String2;
            }
            if ( v17[1].Buffer && RtlEqualUnicodeString((PCUNICODE_STRING)a2 + 1, v17 + 1, 1u) )
              goto LABEL_50;
          }
          IsValidDomainSid = LsaDbpVerifyTrustLocation(a2);
          if ( IsValidDomainSid >= 0 )
          {
            v19 = *((_DWORD *)a2 + 12);
            if ( (v19 & 0x20) != 0 )
            {
              if ( (v19 & 0x10) != 0 || (v19 & 8) != 0 )
              {
                IsValidDomainSid = -1073741811;
                goto LABEL_51;
              }
            }
            else if ( (v19 & 8) != 0 && *v14 == 2 )
            {
              if ( *((_QWORD *)a2 + 4) )
              {
                v20 = LsaDbpCreateInitialFTInfo(a2, (unsigned __int8 **)&v68, &v80);
                IsValidDomainSid = v20;
                if ( v20 < 0 )
                {
                  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      16,
                      &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids,
                      (unsigned int)v20);
                  goto LABEL_51;
                }
              }
            }
            LsapDbAcquireLockEx(5);
            v69 = 1;
            IsValidDomainSid = LsapDbReferenceObject(v77, 0, 1, 2);
            if ( IsValidDomainSid >= 0 )
            {
              v7 = 1;
              v63 = 1;
              IsValidDomainSid = LsapDbExpAcquireReadLockTrustedDomainList(v21);
              if ( IsValidDomainSid >= 0 )
              {
                v22 = *(_OWORD *)a2;
                v84 = 0;
                v83 = v22;
                if ( !(unsigned int)LsaDbpLookupEntryTrustedDomainList(
                                      (struct _LSAPR_TRUST_INFORMATION *)&v83,
                                      (struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **)&v73) )
                {
                  LsapDbExpReleaseLockTrustedDomainList(v23);
LABEL_82:
                  IsValidDomainSid = -1073741771;
                  goto LABEL_51;
                }
                v24 = *(_OWORD *)v12;
                v84 = 0;
                v83 = v24;
                v25 = LsaDbpLookupEntryTrustedDomainList(
                        (struct _LSAPR_TRUST_INFORMATION *)&v83,
                        (struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **)&v73);
                LsapDbExpReleaseLockTrustedDomainList(v26);
                if ( !v25 )
                  goto LABEL_82;
                IsValidDomainSid = LsaDbpMakeUnicodeAttributeDs(a2, 31, v97);
                if ( IsValidDomainSid >= 0 )
                {
                  ++v66;
                  if ( v16 )
                  {
                    IsValidDomainSid = LsaDbpMakeSidAttributeDs(v16, 2, v98);
                    if ( IsValidDomainSid < 0 )
                      goto LABEL_154;
                    ++v66;
                    v27 = &v99;
                  }
                  else
                  {
                    v27 = v98;
                  }
                  v78 = 1;
                  LsapDbInitializeAttribute(v27, 54, &v78);
                  v28 = LsaDbpDsAttInfo;
                  *((_DWORD *)v27 + 8) = *((_DWORD *)LsaDbpDsAttInfo + 162);
                  v29 = *((_DWORD *)v28 + 163);
                  ++v66;
                  v74 = 0;
                  v30 = (unsigned int *)((char *)a2 + 40);
                  v31 = (*((_BYTE *)a2 + 40) & 2) == 0;
                  *((_DWORD *)v27 + 9) = v29;
                  if ( v31
                    || *v14 - 1 > 1
                    || (v72 = 3,
                        AccountDomainHandle = LsapGetAccountDomainHandle(v28),
                        IsValidDomainSid = SamIQueryServerRole(AccountDomainHandle, &v72),
                        IsValidDomainSid >= 0)
                    && (v72 != 3
                     || (IsValidDomainSid = LsapDbExpAcquireWriteLockTrustedDomainList(v33), IsValidDomainSid >= 0)
                     && (v70 = 1,
                         IsValidDomainSid = LsaDbpAllocatePosixOffsetTrustedDomainList(&v74),
                         IsValidDomainSid >= 0)) )
                  {
                    LsapDbInitializeAttribute(v27 + 40, 36, &v74);
                    v34 = LsaDbpDsAttInfo;
                    v9 = 1;
                    *((_DWORD *)v27 + 18) = *((_DWORD *)LsaDbpDsAttInfo + 108);
                    v35 = *((_DWORD *)v34 + 109);
                    ++v66;
                    v36 = HIBYTE(word_18004706B);
                    *((_DWORD *)v27 + 19) = v35;
                    if ( v36 )
                    {
                      UnicodeString = *(struct _UNICODE_STRING *)a2;
                    }
                    else
                    {
                      v37 = LsapDbSidToLogicalNameObject(v16, &UnicodeString);
                      v36 = HIBYTE(word_18004706B);
                      v9 = 1;
                      IsValidDomainSid = v37;
                    }
                    if ( IsValidDomainSid < 0 )
                    {
                      v15 = v65;
                      v7 = v63;
                      goto LABEL_45;
                    }
                    v87 = v77;
                    p_UnicodeString = &UnicodeString;
                    v94 = v79;
                    v86[2] = 48;
                    v89 = 64;
                    v90 = 0;
                    v91 = 0;
                    v86[0] = 2;
                    v86[1] = 1;
                    v92 = v16;
                    v93 = 0;
                    if ( v36 )
                    {
                      v75 = 0;
                      v73 = 0;
                      v72 = 0;
                      IsValidDomainSid = LsaDbpMakeUnicodeAttributeDs((char *)a2 + 16, 32, v27 + 80);
                      if ( IsValidDomainSid < 0 )
                      {
                        v15 = v65;
                      }
                      else
                      {
                        ++v66;
                        v38 = v27 + 120;
                        v7 = 0;
                        LsapDbInitializeAttribute(v38, 38, (char *)a2 + 44);
                        v39 = LsaDbpDsAttInfo;
                        v38[8] = *((_DWORD *)LsaDbpDsAttInfo + 114);
                        v40 = *((_DWORD *)v39 + 115);
                        ++v66;
                        v38[9] = v40;
                        LsapDbInitializeAttribute(v38 + 10, 39, (char *)a2 + 40);
                        v41 = LsaDbpDsAttInfo;
                        v42 = v38 + 20;
                        v38[18] = *((_DWORD *)LsaDbpDsAttInfo + 117);
                        v43 = *((_DWORD *)v41 + 118);
                        ++v66;
                        v38[19] = v43;
                        v75 = *((_DWORD *)a2 + 12) & 0xFF03FFFF;
                        LsapDbInitializeAttribute(v38 + 20, 40, &v75);
                        v44 = LsaDbpDsAttInfo;
                        v45 = v85;
                        v46 = v85;
                        v38[28] = *((_DWORD *)LsaDbpDsAttInfo + 120);
                        v47 = *((_DWORD *)v44 + 121);
                        ++v66;
                        v38[29] = v47;
                        IsValidDomainSid = LsaDbpDsBuildAuthInfoAttribute(v44, v46, 0, (unsigned __int8 **)&v73, &v72);
                        if ( IsValidDomainSid >= 0 )
                        {
                          v49 = v42 + 10;
                          if ( v73 )
                          {
                            LsapDbInitializeAttribute(v49, 43, v73);
                            v48 = LsaDbpDsAttInfo;
                            v49[8] = *((_DWORD *)LsaDbpDsAttInfo + 129);
                            v49[9] = *((_DWORD *)v48 + 130);
                            v49 += 10;
                            ++v66;
                          }
                          v50 = 0;
                          if ( v45 )
                            v50 = (struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)((char *)v45 + 24);
                          IsValidDomainSid = LsaDbpDsBuildAuthInfoAttribute(v48, v50, 0, (unsigned __int8 **)&v73, &v72);
                          if ( IsValidDomainSid >= 0 )
                          {
                            if ( v73 )
                            {
                              LsapDbInitializeAttribute(v49, 44, v73);
                              v51 = LsaDbpDsAttInfo;
                              v49[8] = *((_DWORD *)LsaDbpDsAttInfo + 132);
                              v52 = *((_DWORD *)v51 + 133);
                              ++v66;
                              v49[9] = v52;
                            }
LABEL_110:
                            v5 = (void **)hMem;
                            IsValidDomainSid = LsapDbCreateObject(v86, v79, 2);
                            v67 = *v5;
                            if ( IsValidDomainSid == -1073741772 )
                            {
                              if ( (unsigned int)LsapGetGlobalRestrictAnonymous() )
                              {
                                v53 = v68;
                                v7 = v63;
                                v54 = v67;
                                LODWORD(v15) = v65;
                                if ( (*((_BYTE *)v77 + 136) & 4) == 0 )
                                  goto LABEL_168;
                                IsValidDomainSid = -1073741790;
                                v8 = v65;
                                goto LABEL_114;
                              }
                            }
                            else if ( IsValidDomainSid >= 0 )
                            {
                              v31 = (*(_BYTE *)v30 & 1) == 0;
                              v64 = 1;
                              if ( v31
                                || *v14 - 1 > 1
                                || (IsValidDomainSid = LsaDbpDsCreateInterdomainTrustAccount(*v5), IsValidDomainSid >= 0) )
                              {
                                memset_0(v95, 0, 0x40u);
                                v55 = *((_OWORD *)a2 + 1);
                                v95[0] = *(_OWORD *)a2;
                                v56 = *((_OWORD *)a2 + 2);
                                v95[1] = v55;
                                *(_QWORD *)&v55 = *((_QWORD *)a2 + 6);
                                v95[2] = v56;
                                v96 = v55;
                                IsValidDomainSid = LsapDbExpAcquireWriteLockTrustedDomainList(v57);
                                if ( IsValidDomainSid >= 0 )
                                {
                                  IsValidDomainSid = LsaDbpInsertTrustedDomainList(
                                                       (struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *)v95,
                                                       v74);
                                  LsapDbExpReleaseLockTrustedDomainList(v58);
                                  v53 = v68;
                                  if ( IsValidDomainSid >= 0 )
                                  {
                                    if ( !v68 )
                                      goto LABEL_175;
                                    v73 = 0;
                                    hMem = 0;
                                    IsValidDomainSid = NetpUnmarshalFtinfo2(v68, v80, &v73);
                                    if ( IsValidDomainSid >= 0 )
                                    {
                                      IsValidDomainSid = LsaDbrSetForestTrustInformationWorker(
                                                           v77,
                                                           (struct _UNICODE_STRING *)a2,
                                                           (enum LSA_FOREST_TRUST_RECORD_TYPE)4,
                                                           (struct _LSA_FOREST_TRUST_INFORMATION2 *)v73,
                                                           0,
                                                           (struct _LSA_FOREST_TRUST_COLLISION_INFORMATION **)&hMem);
                                      if ( IsValidDomainSid >= 0 )
                                        LocalFree(hMem);
                                      LocalFree(v73);
                                      if ( IsValidDomainSid >= 0 )
                                      {
LABEL_175:
                                        if ( (unsigned __int8)IsLsapAdtAuditingEnabledByLogonIdPresent()
                                          && (unsigned __int8)LsapAdtAuditingEnabledHint(141, 8) )
                                        {
                                          LsaDbpAdtTrustedDomainAdd(
                                            v59,
                                            (struct _UNICODE_STRING *)a2,
                                            *((void **)a2 + 4),
                                            *v14,
                                            *v30,
                                            *((_DWORD *)a2 + 12));
                                        }
                                        LsapDbApplyTransaction(v77, 0x1000000, 0);
                                        LsapDbReleaseLockEx(2);
                                        v54 = v67;
                                        goto LABEL_130;
                                      }
                                    }
                                  }
                                  goto LABEL_166;
                                }
                              }
                            }
                            v53 = v68;
LABEL_166:
                            LODWORD(v15) = v65;
                            v54 = v67;
LABEL_167:
                            v7 = v63;
                            goto LABEL_168;
                          }
                        }
                        v15 = 0;
                      }
                      v53 = v68;
                      v54 = (_QWORD *)v15;
                      v5 = (void **)hMem;
                      goto LABEL_167;
                    }
                    v7 = 0;
                    goto LABEL_110;
                  }
                  v7 = v63;
                }
              }
            }
          }
LABEL_154:
          v15 = v65;
          goto LABEL_52;
        }
        if ( RtlEqualSid(v16, v18) )
        {
LABEL_50:
          IsValidDomainSid = -1073741079;
LABEL_51:
          v15 = 0;
LABEL_52:
          v5 = (void **)hMem;
          goto LABEL_35;
        }
      }
      v17 = String2;
      goto LABEL_54;
    }
    v63 = 0;
    IsValidDomainSid = LsaDbpValidateDnsName((const struct _UNICODE_STRING *)a2, &v63);
    if ( IsValidDomainSid >= 0 )
    {
      if ( !v63 )
        goto LABEL_34;
      goto LABEL_39;
    }
LABEL_169:
    v53 = v68;
    LODWORD(v15) = 0;
    v54 = 0;
    goto LABEL_168;
  }
LABEL_34:
  IsValidDomainSid = -1073741773;
  v15 = 0;
LABEL_35:
  v8 = v15;
  v9 = 1;
LABEL_158:
  v53 = v68;
  v54 = (_QWORD *)v15;
  while ( 1 )
  {
    if ( IsValidDomainSid < 0 )
      LODWORD(v15) = IsValidDomainSid;
    IsValidDomainSid = v15;
    if ( v7 )
    {
      IsValidDomainSid = LsapDbDereferenceObject(&v77, 1, 2, 1, 0, v15);
      v7 = 0;
    }
    if ( v8 )
    {
      v54[14] = 0;
      LsarDeleteObject(v5, v9);
    }
LABEL_130:
    if ( String2 )
    {
      LsaIFree_LSAPR_POLICY_INFORMATION(12);
      String2 = 0;
    }
    if ( v69 )
      LsapDbReleaseLockEx(5);
    LODWORD(v15) = LsapDbFreeAttributes(v66, v97);
    if ( (v15 & 0x80000000) == 0LL )
      break;
LABEL_168:
    v8 = v64;
LABEL_114:
    v9 = 1;
  }
  if ( !HIBYTE(word_18004706B) && UnicodeString.Length )
  {
    RtlFreeUnicodeString(&UnicodeString);
    UnicodeString.Length = 0;
  }
  if ( v70 )
    LsapDbExpReleaseLockTrustedDomainList(v60);
  if ( IsValidDomainSid >= 0
    && (*((_BYTE *)a2 + 48) & 8) != 0
    && (*((_BYTE *)a2 + 40) & 1) != 0
    && *((_DWORD *)a2 + 11) == 2
    && v53 )
  {
    v61 = CopyLsaString(a2, (unsigned __int16 **)&v81);
    if ( v61 >= 0 )
    {
      v61 = LsaDbRequestTrustScannerOperation((unsigned __int16 *)v81, 0, 0, 8u);
      LocalFree(v81);
    }
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids,
        (unsigned int)v61);
  }
  LocalFree(v53);
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids,
      (unsigned int)IsValidDomainSid);
  return (unsigned int)IsValidDomainSid;
}

```

## disassembly

```asm
0x18000a2bc  push    rbp
0x18000a2be  push    rbx
0x18000a2bf  push    rsi
0x18000a2c0  push    rdi
0x18000a2c1  push    r12
0x18000a2c3  push    r13
0x18000a2c5  push    r14
0x18000a2c7  push    r15
0x18000a2c9  lea     rbp, [rsp-388h]
0x18000a2d1  sub     rsp, 488h
0x18000a2d8  mov     rax, cs:__security_cookie
0x18000a2df  xor     rax, rsp
0x18000a2e2  mov     [rbp+3C0h+var_50], rax
0x18000a2e9  mov     r14, [rbp+3C0h+arg_20]
0x18000a2f0  xor     r13d, r13d
0x18000a2f3  mov     [rbp+3C0h+var_3E8], r8
0x18000a2f7  mov     rdi, rdx
0x18000a2fa  mov     [rbp+3C0h+var_430], rcx
0x18000a2fe  xor     edx, edx; Val
0x18000a300  lea     rcx, [rbp+3C0h+var_3E0]; void *
0x18000a304  mov     [rbp+3C0h+var_424], r9d
0x18000a308  lea     r8d, [r13+48h]; Size
0x18000a30c  mov     [rsp+4C0h+hMem], r14
0x18000a311  mov     [rsp+4C0h+var_47C], r13d
0x18000a316  call    memset_0
0x18000a31b  xorps   xmm0, xmm0
0x18000a31e  mov     [rsp+4C0h+var_45F], r13b
0x18000a323  xor     eax, eax
0x18000a325  mov     [rsp+4C0h+var_460], r13b
0x18000a32a  movups  xmmword ptr [rbp+3C0h+UnicodeString.Length], xmm0
0x18000a32e  mov     [rbp+3C0h+var_3F0], rax
0x18000a332  mov     r15b, r13b
0x18000a335  movups  [rbp+3C0h+var_400], xmm0
0x18000a339  mov     [rsp+4C0h+var_478], r13d
0x18000a33e  mov     r12b, r13b
0x18000a341  mov     [rbp+3C0h+var_440], r13d
0x18000a345  mov     [rsp+4C0h+var_47F], r13b
0x18000a34a  mov     [rsp+4C0h+var_448], r13
0x18000a34f  mov     [rbp+3C0h+var_428], r13d
0x18000a353  mov     [rbp+3C0h+String2], r13
0x18000a357  mov     [rsp+4C0h+var_468], r13
0x18000a35c  mov     [rbp+3C0h+var_420], r13d
0x18000a360  mov     [rbp+3C0h+var_418], r13
0x18000a364  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a36b  test    dword ptr [rcx+1Ch], 100h
0x18000a372  jz      short loc_18000A387
0x18000a374  mov     rcx, [rcx+10h]
0x18000a378  lea     edx, [rax+0Fh]
0x18000a37b  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x18000a382  call    WPP_SF_
0x18000a387  xor     edx, edx; Val
0x18000a389  mov     [rbp+3C0h+UnicodeString.Length], r13w
0x18000a38e  mov     r8d, 2F8h; Size
0x18000a394  lea     rcx, [rbp+3C0h+var_350]; void *
0x18000a398  call    memset_0
0x18000a39d  mov     edx, 1
0x18000a3a2  test    rdi, rdi
0x18000a3a5  jz      loc_18000AE72
0x18000a3ab  cmp     cs:?DcInRootDomain@@3EA, r13b; uchar DcInRootDomain
0x18000a3b2  jnz     short loc_18000A3C4
0x18000a3b4  test    byte ptr [rdi+30h], 8
0x18000a3b8  jz      short loc_18000A3E2
0x18000a3ba  mov     ebx, 0C00000DDh
0x18000a3bf  jmp     loc_18000AE77
0x18000a3c4  test    byte ptr [rdi+30h], 8
0x18000a3c8  jz      short loc_18000A3E2
0x18000a3ca  call    ?LsaDbpNoMoreWin2KForest@@YAEXZ; LsaDbpNoMoreWin2KForest(void)
0x18000a3cf  test    al, al
0x18000a3d1  jnz     short loc_18000A3E2
0x18000a3d3  mov     ebx, 0C00000DDh
0x18000a3d8  mov     edx, 1
0x18000a3dd  jmp     loc_18000AE77
0x18000a3e2  test    byte ptr [rdi+30h], 10h
0x18000a3e6  jz      short loc_18000A3F1
0x18000a3e8  call    ?LsaDbpNoMoreWin2KDomain@@YAEXZ; LsaDbpNoMoreWin2KDomain(void)
0x18000a3ed  test    al, al
0x18000a3ef  jz      short loc_18000A3D3
0x18000a3f1  cmp     byte ptr cs:word_18004706B+1, r13b
0x18000a3f8  mov     edx, 1
0x18000a3fd  jnz     short loc_18000A409
0x18000a3ff  mov     ebx, 0C00002B1h
0x18000a404  jmp     loc_18000AE77
0x18000a409  movzx   eax, word ptr [rdi+2]
0x18000a40d  test    dl, al
0x18000a40f  jz      short loc_18000A418
0x18000a411  sub     ax, dx
0x18000a414  mov     [rdi+2], ax
0x18000a418  cmp     ax, [rdi]
0x18000a41b  jb      loc_18000AE72
0x18000a421  movzx   ecx, ax
0x18000a424  movzx   eax, word ptr [rdi]
0x18000a427  or      ecx, eax
0x18000a429  test    dl, cl
0x18000a42b  jnz     loc_18000AE72
0x18000a431  cmp     [rdi], r13w
0x18000a435  jz      short loc_18000A441
0x18000a437  cmp     [rdi+8], r13
0x18000a43b  jz      loc_18000AE72
0x18000a441  lea     rsi, [rdi+10h]
0x18000a445  test    rsi, rsi
0x18000a448  jz      short loc_18000A482
0x18000a44a  movzx   eax, word ptr [rsi+2]
0x18000a44e  test    dl, al
0x18000a450  jz      short loc_18000A459
0x18000a452  sub     ax, dx
0x18000a455  mov     [rsi+2], ax
0x18000a459  cmp     ax, [rsi]
0x18000a45c  jb      loc_18000AE72
0x18000a462  movzx   ecx, ax
0x18000a465  movzx   eax, word ptr [rsi]
0x18000a468  or      ecx, eax
0x18000a46a  test    dl, cl
0x18000a46c  jnz     loc_18000AE72
0x18000a472  cmp     [rsi], r13w
0x18000a476  jz      short loc_18000A482
0x18000a478  cmp     [rsi+8], r13
0x18000a47c  jz      loc_18000AE72
0x18000a482  xor     edx, edx
0x18000a484  mov     rcx, rdi
0x18000a487  call    cs:__imp_LsapRemoveTrailingDot
0x18000a48d  xor     edx, edx
0x18000a48f  mov     rcx, rsi
0x18000a492  call    cs:__imp_LsapRemoveTrailingDot
0x18000a498  mov     rcx, rdi; struct _UNICODE_STRING *
0x18000a49b  call    ?LsaDbpValidateIsNonEmptyUnicodeString@@YAEPEBU_UNICODE_STRING@@@Z; LsaDbpValidateIsNonEmptyUnicodeString(_UNICODE_STRING const *)
0x18000a4a0  test    al, al
0x18000a4a2  jz      loc_18000AE6D
0x18000a4a8  mov     rcx, rsi; struct _UNICODE_STRING *
0x18000a4ab  call    ?LsaDbpValidateIsNonEmptyUnicodeString@@YAEPEBU_UNICODE_STRING@@@Z; LsaDbpValidateIsNonEmptyUnicodeString(_UNICODE_STRING const *)
0x18000a4b0  test    al, al
0x18000a4b2  jz      loc_18000AE6D
0x18000a4b8  xor     edx, edx
0x18000a4ba  mov     rcx, rdi
0x18000a4bd  call    cs:__imp_LsapRemoveTrailingDot
0x18000a4c3  test    al, al
0x18000a4c5  jnz     loc_18000AE6D
0x18000a4cb  xor     edx, edx
0x18000a4cd  mov     rcx, rsi
0x18000a4d0  call    cs:__imp_LsapRemoveTrailingDot
0x18000a4d6  test    al, al
0x18000a4d8  jnz     loc_18000AE6D
0x18000a4de  lea     r12, [rdi+2Ch]
0x18000a4e2  mov     eax, [r12]
0x18000a4e6  dec     eax
0x18000a4e8  cmp     eax, 1
0x18000a4eb  ja      short loc_18000A525
0x18000a4ed  lea     rdx, [rsp+4C0h+var_480]; unsigned __int8 *
0x18000a4f2  mov     [rsp+4C0h+var_480], r13b
0x18000a4f7  mov     rcx, rsi; struct _UNICODE_STRING *
0x18000a4fa  call    ?LsaDbpValidateNetbiosName@@YAJPEBU_UNICODE_STRING@@PEAE@Z; LsaDbpValidateNetbiosName(_UNICODE_STRING const *,uchar *)
0x18000a4ff  mov     ebx, eax
0x18000a501  test    eax, eax
0x18000a503  js      loc_18000AEED
0x18000a509  cmp     [rsp+4C0h+var_480], r13b
0x18000a50e  jnz     short loc_18000A525
0x18000a510  mov     ebx, 0C0000033h
0x18000a515  mov     eax, r13d
0x18000a518  mov     r12b, al
0x18000a51b  mov     edx, 1
0x18000a520  jmp     loc_18000AE7A
0x18000a525  cmp     dword ptr [r12], 2
0x18000a52a  jnz     short loc_18000A54F
0x18000a52c  lea     rdx, [rsp+4C0h+var_480]; unsigned __int8 *
0x18000a531  mov     [rsp+4C0h+var_480], r13b
0x18000a536  mov     rcx, rdi; struct _UNICODE_STRING *
0x18000a539  call    ?LsaDbpValidateDnsName@@YAJPEBU_UNICODE_STRING@@PEAE@Z; LsaDbpValidateDnsName(_UNICODE_STRING const *,uchar *)
0x18000a53e  mov     ebx, eax
0x18000a540  test    eax, eax
0x18000a542  js      loc_18000AEED
0x18000a548  cmp     [rsp+4C0h+var_480], r13b
0x18000a54d  jz      short loc_18000A510
0x18000a54f  mov     r14, [rdi+20h]
0x18000a553  test    r14, r14
0x18000a556  jz      short loc_18000A56A
0x18000a558  mov     rcx, r14; Sid1
0x18000a55b  call    ?LsaDbpIsValidDomainSid@@YAJPEAX@Z; LsaDbpIsValidDomainSid(void *)
0x18000a560  mov     ebx, eax
0x18000a562  test    eax, eax
0x18000a564  js      loc_18000AE64
0x18000a56a  mov     rax, [rbp+3C0h+var_430]
0x18000a56e  cmp     [rax+85h], r13b
0x18000a575  jnz     short loc_18000A59F
0x18000a577  test    r14, r14
0x18000a57a  jnz     short loc_18000A59F
0x18000a57c  mov     eax, [r12]
0x18000a580  lea     edx, [r14+1]
0x18000a584  sub     eax, edx
0x18000a586  cmp     eax, edx
0x18000a588  ja      short loc_18000A59F
0x18000a58a  mov     ebx, 0C0000078h
0x18000a58f  mov     eax, r13d
0x18000a592  mov     r14, [rsp+4C0h+hMem]
0x18000a597  mov     r12b, al
0x18000a59a  jmp     loc_18000AE7A
0x18000a59f  mov     rcx, cs:?LsaDbpPolicyHandle@@3PEAXEA; void * LsaDbpPolicyHandle
0x18000a5a6  lea     r8, [rbp+3C0h+String2]
0x18000a5aa  mov     edx, 0Ch
0x18000a5af  call    cs:__imp_LsapDbQueryInformationPolicy
0x18000a5b5  mov     ebx, eax
0x18000a5b7  test    eax, eax
0x18000a5b9  js      loc_18000AE64
0x18000a5bf  test    r14, r14
0x18000a5c2  jz      short loc_18000A5F0
0x18000a5c4  mov     rax, [rbp+3C0h+String2]
0x18000a5c8  mov     rdx, [rax+40h]; Sid2
0x18000a5cc  test    rdx, rdx
0x18000a5cf  jz      short loc_18000A5F4
0x18000a5d1  mov     rcx, r14; Sid1
0x18000a5d4  call    cs:__imp_RtlEqualSid
0x18000a5da  test    al, al
0x18000a5dc  jz      short loc_18000A5F0
0x18000a5de  mov     ebx, 0C00002E9h
0x18000a5e3  mov     eax, r13d
0x18000a5e6  mov     r14, [rsp+4C0h+hMem]
0x18000a5eb  jmp     loc_18000A518
0x18000a5f0  mov     rax, [rbp+3C0h+String2]
0x18000a5f4  cmp     [rdi+8], r13
0x18000a5f8  jz      short loc_18000A635
0x18000a5fa  cmp     [rax+8], r13
0x18000a5fe  jz      short loc_18000A617
0x18000a600  mov     r8b, 1; CaseInsensitive
0x18000a603  mov     rdx, rax; String2
0x18000a606  mov     rcx, rdi; String1
0x18000a609  call    cs:__imp_RtlEqualUnicodeString
0x18000a60f  test    al, al
0x18000a611  jnz     short loc_18000A5DE
0x18000a613  mov     rax, [rbp+3C0h+String2]
0x18000a617  lea     rdx, [rax+10h]; String2
0x18000a61b  cmp     [rdx+8], r13
0x18000a61f  jz      short loc_18000A635
0x18000a621  mov     r8b, 1; CaseInsensitive
0x18000a624  mov     rcx, rdi; String1
0x18000a627  call    cs:__imp_RtlEqualUnicodeString
0x18000a62d  test    al, al
0x18000a62f  jnz     short loc_18000A5DE
0x18000a631  mov     rax, [rbp+3C0h+String2]
0x18000a635  cmp     [rdi+18h], r13
0x18000a639  jz      short loc_18000A676
0x18000a63b  cmp     [rax+8], r13
0x18000a63f  jz      short loc_18000A658
0x18000a641  mov     r8b, 1; CaseInsensitive
0x18000a644  mov     rdx, rax; String2
0x18000a647  mov     rcx, rsi; String1
0x18000a64a  call    cs:__imp_RtlEqualUnicodeString
0x18000a650  test    al, al
0x18000a652  jnz     short loc_18000A5DE
0x18000a654  mov     rax, [rbp+3C0h+String2]
0x18000a658  lea     rdx, [rax+10h]; String2
0x18000a65c  cmp     [rdx+8], r13
0x18000a660  jz      short loc_18000A676
0x18000a662  mov     r8b, 1; CaseInsensitive
0x18000a665  mov     rcx, rsi; String1
0x18000a668  call    cs:__imp_RtlEqualUnicodeString
0x18000a66e  test    al, al
0x18000a670  jnz     loc_18000A5DE
0x18000a676  mov     rcx, rdi; struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *
0x18000a679  call    ?LsaDbpVerifyTrustLocation@@YAJPEAU_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX@@@Z; LsaDbpVerifyTrustLocation(_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *)
0x18000a67e  mov     ebx, eax
0x18000a680  test    eax, eax
0x18000a682  js      loc_18000AE64
0x18000a688  mov     eax, [rdi+30h]
0x18000a68b  test    al, 20h
0x18000a68d  jz      short loc_18000A6A2
0x18000a68f  test    al, 10h
0x18000a691  jnz     short loc_18000A698
0x18000a693  and     eax, 8
0x18000a696  jz      short loc_18000A6FC
0x18000a698  mov     ebx, 0C000000Dh
0x18000a69d  jmp     loc_18000A5E3
0x18000a6a2  and     eax, 8
0x18000a6a5  jz      short loc_18000A6FC
0x18000a6a7  cmp     dword ptr [r12], 2
0x18000a6ac  jnz     short loc_18000A6FC
0x18000a6ae  cmp     [rdi+20h], r13
0x18000a6b2  jz      short loc_18000A6FC
0x18000a6b4  lea     r8, [rbp+3C0h+var_420]; unsigned int *
0x18000a6b8  mov     rcx, rdi; struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *
0x18000a6bb  lea     rdx, [rsp+4C0h+var_468]; unsigned __int8 **
0x18000a6c0  call    ?LsaDbpCreateInitialFTInfo@@YAJPEAU_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX@@PEAPEAEPEAK@Z; LsaDbpCreateInitialFTInfo(_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *,uchar * *,ulong *)
0x18000a6c5  mov     ebx, eax
0x18000a6c7  test    eax, eax
0x18000a6c9  jns     short loc_18000A6FC
0x18000a6cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6d2  test    dword ptr [rcx+1Ch], 100h
0x18000a6d9  jz      loc_18000A5E3
0x18000a6df  mov     rcx, [rcx+10h]
0x18000a6e3  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x18000a6ea  mov     edx, 10h
0x18000a6ef  mov     r9d, eax
0x18000a6f2  call    WPP_SF_d
0x18000a6f7  jmp     loc_18000A5E3
0x18000a6fc  xor     edx, edx
0x18000a6fe  lea     ecx, [rdx+5]
0x18000a701  call    cs:__imp_LsapDbAcquireLockEx
0x18000a707  mov     rcx, [rbp+3C0h+var_430]
0x18000a70b  mov     eax, 1
0x18000a710  mov     r8d, eax
0x18000a713  mov     [rsp+4C0h+var_460], al
0x18000a717  xor     edx, edx
0x18000a719  mov     dword ptr [rsp+4C0h+var_4A0], eax
  ... truncated ...
```
