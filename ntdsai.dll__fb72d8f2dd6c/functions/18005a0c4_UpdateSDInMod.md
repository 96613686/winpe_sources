# UpdateSDInMod

- ea: `0x18005a0c4`
- end: `0x18005af9f`
- name: `UpdateSDInMod`
- size: `3803`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800552b8`

## callees

- `0x180006330`
- `0x1800067d0`
- `0x18000dc7c`
- `0x18001e090`
- `0x180021a97`
- `0x180021aa3`
- `0x18005a0c4`
- `0x1800cef74`
- `0x1800d94b4`
- `0x18010cc0c`
- `0x18011fcd4`
- `0x180121330`
- `0x180132cfc`
- `0x18016a988`
- `0x180180c50`
- `0x180181ae0`
- `0x180181bf0`
- `0x1801d2a7c`
- `0x1801d46c0`
- `0x18020140c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18005a35f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18005a35f`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18005a597`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18005a723`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18005a597`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18005a723`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18005a77f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18005a77f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18005a7b6`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18005a7b6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18005a80f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18005a80f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x18005a849`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x18005a849`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18005ad4e`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18005ad70`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180455c72`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180455c93`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18005ad4e`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18005ad70`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180455c72`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180455c93`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18005a876`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18005a8db`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18005a876`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18005a8db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a5a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a72d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a789`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a7c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a819`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a8e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a5a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a72d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a789`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a7c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a819`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a8e5`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18005ace0`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18005ace0`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18005a2b5`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18005a2b5`

## pseudocode

```c
__int64 __fastcall UpdateSDInMod(__int64 a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v4; // r12
  void *v6; // r15
  GUID *v7; // rax
  GUID *v8; // rsi
  __int64 v9; // r9
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r14
  unsigned int v14; // eax
  ULONG v16; // r13d
  __int64 v17; // rax
  void *v18; // r14
  ULONG v19; // ebx
  bool v20; // zf
  int v21; // eax
  SECURITY_INFORMATION v22; // r12d
  int v23; // r8d
  int v24; // r9d
  void *v25; // rbx
  _QWORD *v26; // r9
  __int64 v27; // rax
  int v28; // r12d
  SECURITY_INFORMATION v29; // r8d
  __int64 v30; // rdx
  unsigned int v31; // ebx
  DWORD SidForNC; // eax
  __int64 v33; // r9
  struct _ACL *v34; // rbx
  struct _ACL *pSacl; // rsi
  void *pPrimaryGroup; // rax
  DWORD LastError; // eax
  __int64 v38; // r9
  DWORD v39; // eax
  int v40; // esi
  int v41; // eax
  char v42; // cl
  int v43; // eax
  ULONG v44; // eax
  ULONG v45; // ebx
  __int64 v46; // rcx
  __int64 v47; // rax
  LPOVERLAPPED v48; // rbx
  WORD pControl; // [rsp+70h] [rbp-3F8h] BYREF
  void *v50; // [rsp+78h] [rbp-3F0h]
  SECURITY_INFORMATION v51; // [rsp+80h] [rbp-3E8h]
  DWORD dwBufferLength; // [rsp+84h] [rbp-3E4h] BYREF
  ULONG v53; // [rsp+88h] [rbp-3E0h] BYREF
  int v54; // [rsp+8Ch] [rbp-3DCh]
  WINBOOL bDaclDefaulted; // [rsp+90h] [rbp-3D8h] BYREF
  WINBOOL bDaclPresent; // [rsp+94h] [rbp-3D4h] BYREF
  ULONG Size; // [rsp+98h] [rbp-3D0h] BYREF
  int Size_4; // [rsp+9Ch] [rbp-3CCh]
  int v59; // [rsp+A0h] [rbp-3C8h]
  int v60; // [rsp+A4h] [rbp-3C4h]
  struct _ACL *v61; // [rsp+A8h] [rbp-3C0h]
  struct _ACL *v62; // [rsp+B0h] [rbp-3B8h]
  PSECURITY_DESCRIPTOR ObjectDescriptor; // [rsp+B8h] [rbp-3B0h] BYREF
  _QWORD *v64; // [rsp+C0h] [rbp-3A8h]
  DWORD dwPrimaryGroupSize; // [rsp+C8h] [rbp-3A0h] BYREF
  DWORD dwOwnerSize; // [rsp+CCh] [rbp-39Ch] BYREF
  DWORD dwSaclSize; // [rsp+D0h] [rbp-398h] BYREF
  DWORD dwDaclSize; // [rsp+D4h] [rbp-394h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+D8h] [rbp-390h] BYREF
  ULONG v70; // [rsp+DCh] [rbp-38Ch] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+E0h] [rbp-388h] BYREF
  void *Src[2]; // [rsp+E8h] [rbp-380h] BYREF
  void *v73; // [rsp+F8h] [rbp-370h]
  PSID pOwner; // [rsp+100h] [rbp-368h]
  PACL pDacl; // [rsp+108h] [rbp-360h] BYREF
  void *Buf2; // [rsp+110h] [rbp-358h]
  void *Buf1; // [rsp+118h] [rbp-350h] BYREF
  ULONG v78; // [rsp+120h] [rbp-348h]
  int v79; // [rsp+124h] [rbp-344h] BYREF
  DWORD dwRevision; // [rsp+128h] [rbp-340h] BYREF
  __int64 v81; // [rsp+130h] [rbp-338h] BYREF
  GUID *v82; // [rsp+138h] [rbp-330h] BYREF
  __int64 v83; // [rsp+140h] [rbp-328h]
  void *v84; // [rsp+148h] [rbp-320h]
  void *v85; // [rsp+150h] [rbp-318h]
  __int64 v86; // [rsp+158h] [rbp-310h]
  _OWORD pAbsoluteSecurityDescriptor[2]; // [rsp+160h] [rbp-308h] BYREF
  __int64 v88; // [rsp+180h] [rbp-2E8h]
  __int128 v89; // [rsp+188h] [rbp-2E0h] BYREF
  __int64 v90; // [rsp+198h] [rbp-2D0h]
  __int64 v91; // [rsp+1A0h] [rbp-2C8h] BYREF
  int v92; // [rsp+1A8h] [rbp-2C0h]
  int Internal; // [rsp+1ACh] [rbp-2BCh]
  __int64 v94; // [rsp+1B0h] [rbp-2B8h]
  int v95; // [rsp+1B8h] [rbp-2B0h]
  int v96; // [rsp+1BCh] [rbp-2ACh]
  __int64 v97; // [rsp+1C0h] [rbp-2A8h]
  __int64 v98; // [rsp+1C8h] [rbp-2A0h]
  __int64 v99; // [rsp+1D0h] [rbp-298h]
  __int64 v100; // [rsp+1D8h] [rbp-290h]
  __int64 v101; // [rsp+1E0h] [rbp-288h]
  int v102; // [rsp+1E8h] [rbp-280h]
  __int64 v103; // [rsp+1ECh] [rbp-27Ch]
  int v104; // [rsp+1F4h] [rbp-274h]
  int *v105; // [rsp+1F8h] [rbp-270h]
  int v106; // [rsp+200h] [rbp-268h] BYREF
  __int64 v107; // [rsp+208h] [rbp-260h]
  int v108; // [rsp+220h] [rbp-248h]
  __int64 *v109; // [rsp+228h] [rbp-240h]
  __int64 v110; // [rsp+238h] [rbp-230h] BYREF

  v86 = a3;
  v4 = a2;
  v64 = a2;
  Src[1] = (void *)a1;
  v6 = 0;
  v82 = 0;
  dwRevision = 0;
  pControl = 0;
  Buf1 = 0;
  v53 = 0;
  dwBufferLength = 0;
  ObjectDescriptor = 0;
  Size = 0;
  Src[0] = 0;
  v70 = 0;
  v7 = (GUID *)SCGetClassById(a1, *(unsigned int *)(a2[41] + 12LL));
  v8 = v7;
  if ( v7 )
  {
    v13 = *(_QWORD *)(a1 + 5576);
    v83 = v13;
    v82 = v7 + 8;
    v14 = DBGetAttVal(v13, 1, 131353, 0, (__int64)&v53, (__int64)&Buf1);
    if ( v14 )
    {
      if ( v14 != 8995 || (*(_DWORD *)(a1 + 5604) & 0x100) == 0 )
      {
        v9 = 51324399;
        v10 = v14;
        v11 = 8526;
        goto LABEL_3;
      }
      v53 = 0;
      Buf1 = 0;
    }
    if ( (*(_DWORD *)(a1 + 5604) & 0x100) != 0 )
      goto LABEL_124;
    if ( dsaInitPhase != 1 )
    {
      if ( DataSource != 1 )
        return 0;
LABEL_124:
      if ( *(_DWORD *)(a3 + 24) != 1 )
        DoSetSvcError(5003, 8311, 0, 51324881);
      v47 = *(_QWORD *)(a3 + 32);
      v16 = *(_DWORD *)v47;
      v25 = *(void **)(v47 + 8);
      goto LABEL_127;
    }
    if ( *(_WORD *)(a3 + 8) != 67 || !*(_DWORD *)(a3 + 24) )
    {
      v12 = 5003;
      v9 = 51324461;
      v10 = 0;
      v11 = 8311;
      goto LABEL_4;
    }
    v60 = 0;
    v50 = 0;
    v59 = 0;
    Size_4 = 0;
    v84 = 0;
    Buf2 = 0;
    v85 = 0;
    v16 = 0;
    v17 = *(_QWORD *)(a3 + 32);
    v18 = *(void **)(v17 + 8);
    v19 = *(_DWORD *)v17;
    v20 = (v4[17] & 0xF) == 0;
    v21 = v4[17] & 0xF;
    v22 = 15;
    if ( !v20 )
      v22 = v21;
    v51 = v22;
    if ( !RtlValidRelativeSecurityDescriptor(v18, v19, 0) )
    {
      v4 = v64;
      DoSetAttError(*v64, 131353, 1005, 0, 1338, 0, 51324495);
LABEL_20:
      v18 = v50;
LABEL_21:
      v25 = Buf2;
LABEL_110:
      if ( v6 && v6 != v25 )
        THFreeAux(a1, (_DWORD)v6, v23, v24, 51324860);
      if ( Src[0] && Size_4 )
        DestroyPrivateObjectSecurity(Src);
      if ( ObjectDescriptor && v59 )
        DestroyPrivateObjectSecurity(&ObjectDescriptor);
      if ( v18 && v60 )
        THFreeAux(a1, (_DWORD)v18, v23, v24, 51324872);
      v13 = v83;
LABEL_127:
      if ( !*(_DWORD *)(a1 + 5560) && (!gfDontPropagateOnNoChangeUpdate || v53 != v16 || memcmp_0(Buf1, v25, v53)) )
        DBEnqueueSDPropagationEx(v13, (unsigned int)-__CFSHR__(*(_DWORD *)(a1 + 5604), 12), 0xFFFFFFFFLL, 0);
      if ( (*(_DWORD *)(a1 + 5604) & 0x100) != 0 )
        return *(unsigned int *)(a1 + 5560);
      if ( v16 < LdapSecurityDescriptorWarningSize )
        return *(unsigned int *)(a1 + 5560);
      v48 = gpDsEventConfig;
      if ( !gpDsEventConfig )
        return *(unsigned int *)(a1 + 5560);
      if ( (gpDsEventConfig[1].Internal & 0x8000000000000000uLL) != 0LL
        && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(783, 0)) )
      {
        if ( !(unsigned int)DoLogMsgOverride(2147486719LL) )
          return *(unsigned int *)(a1 + 5560);
        v48 = gpDsEventConfig;
      }
      v94 = 0;
      v100 = 0;
      v103 = 0;
      v104 = 0;
      Internal = v48[1].Internal;
      v92 = -2147480577;
      v95 = 0;
      v96 = 1;
      v105 = &v106;
      v106 = 6;
      v107 = *v4;
      v108 = 5;
      v110 = v16;
      v109 = &v110;
      v91 = 2;
      v99 = 0;
      v98 = 783;
      v97 = 1;
      v101 = 0;
      v102 = 0;
      DoLogEventAndTrace(&v91);
      return *(unsigned int *)(a1 + 5560);
    }
    if ( *(_DWORD *)gfADAM
      && (unsigned int)ValidateSidReferences(
                         a1,
                         v18,
                         v22,
                         0,
                         *v64,
                         *(_DWORD *)(v64[41] + 24LL),
                         *(_DWORD *)(v64[41] + 8LL) & 1) )
    {
      goto LABEL_88;
    }
    GetSecurityDescriptorControl(v18, &pControl, &dwRevision);
    v26 = v64;
    if ( (pControl & 0x3000) == 0x3000
      || (v27 = v64[41], (*(_BYTE *)(v27 + 8) & 1) != 0)
      || (v54 = 1, *(_DWORD *)(v27 + 28)) )
    {
      v54 = 0;
    }
    v28 = v22 & 4;
    if ( !v28 || (pControl & 4) != 0 )
    {
      v29 = v51;
      if ( (v51 & 8) == 0 || (pControl & 0x10) != 0 )
      {
        v60 = 0;
        v50 = v18;
        dwBufferLength = v19;
        goto LABEL_90;
      }
    }
    v30 = v64[41];
    v31 = *(_DWORD *)(v30 + 8) & 1;
    v81 = 0;
    pSecurityDescriptor = 0;
    v79 = 0;
    memset(pAbsoluteSecurityDescriptor, 0, sizeof(pAbsoluteSecurityDescriptor));
    v88 = 0;
    dwAbsoluteSecurityDescriptorSize = 40;
    v61 = 0;
    dwDaclSize = 0;
    v62 = 0;
    dwSaclSize = 0;
    pOwner = 0;
    dwOwnerSize = 0;
    v73 = 0;
    dwPrimaryGroupSize = 0;
    bDaclDefaulted = 0;
    bDaclPresent = 0;
    pDacl = 0;
    v60 = 1;
    if ( v31 && *(_DWORD *)(*v64 + 4LL) )
    {
      v81 = *v64 + 24LL;
    }
    else
    {
      SidForNC = GetSidForNC(a1, *(unsigned int *)(v30 + 24), &v81, v64);
      if ( SidForNC )
      {
        if ( *(_DWORD *)(a1 + 5560) )
        {
LABEL_74:
          pSacl = v62;
          v34 = v61;
          goto LABEL_75;
        }
        v33 = 51324584;
LABEL_37:
        DoSetSvcError(5012, SidForNC, 0, v33);
        goto LABEL_74;
      }
      v26 = v64;
    }
    SCGetDefaultSD(a1, v8, v81, v31, *v26, &pSecurityDescriptor, &v79);
    if ( *(_DWORD *)(a1 + 5560) )
      goto LABEL_74;
    if ( !MakeAbsoluteSD(
            v18,
            pAbsoluteSecurityDescriptor,
            &dwAbsoluteSecurityDescriptorSize,
            0,
            &dwDaclSize,
            0,
            &dwSaclSize,
            0,
            &dwOwnerSize,
            0,
            &dwPrimaryGroupSize) )
    {
      SidForNC = GetLastError();
      if ( SidForNC != 122 )
      {
        v33 = 51324602;
        goto LABEL_37;
      }
      dwAbsoluteSecurityDescriptorSize = 40;
    }
    if ( dwDaclSize )
    {
      v34 = (struct _ACL *)THAlloc_(a1, 1, dwDaclSize, 1, 0, 51324612);
      v61 = v34;
    }
    else
    {
      v34 = v61;
    }
    if ( dwSaclSize )
    {
      pSacl = (struct _ACL *)THAlloc_(a1, 1, dwSaclSize, 1, 0, 51324615);
      v62 = pSacl;
    }
    else
    {
      pSacl = v62;
    }
    if ( dwOwnerSize )
      pOwner = (PSID)THAlloc_(a1, 1, dwOwnerSize, 1, 0, 51324618);
    if ( dwPrimaryGroupSize )
    {
      pPrimaryGroup = (void *)THAlloc_(a1, 1, dwPrimaryGroupSize, 1, 0, 51324621);
      v73 = pPrimaryGroup;
    }
    else
    {
      pPrimaryGroup = v73;
    }
    if ( !MakeAbsoluteSD(
            v18,
            pAbsoluteSecurityDescriptor,
            &dwAbsoluteSecurityDescriptorSize,
            v34,
            &dwDaclSize,
            pSacl,
            &dwSaclSize,
            pOwner,
            &dwOwnerSize,
            pPrimaryGroup,
            &dwPrimaryGroupSize) )
    {
      LastError = GetLastError();
      v38 = 51324628;
LABEL_57:
      DoSetSvcError(5012, LastError, 0, v38);
LABEL_75:
      v18 = v50;
      goto LABEL_76;
    }
    if ( v28 && (pControl & 4) == 0 )
    {
      if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      {
        LastError = GetLastError();
        v38 = 51324636;
        goto LABEL_57;
      }
      if ( !SetSecurityDescriptorDacl(pAbsoluteSecurityDescriptor, bDaclPresent, pDacl, bDaclDefaulted) )
      {
        LastError = GetLastError();
        v38 = 51324641;
        goto LABEL_57;
      }
    }
    if ( (v51 & 8) != 0 && (pControl & 0x10) == 0 )
    {
      if ( !GetSecurityDescriptorSacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      {
        LastError = GetLastError();
        v38 = 51324650;
        goto LABEL_57;
      }
      if ( !SetSecurityDescriptorSacl(pAbsoluteSecurityDescriptor, bDaclPresent, pDacl, bDaclDefaulted) )
      {
        LastError = GetLastError();
        v38 = 51324655;
        goto LABEL_57;
      }
    }
    if ( MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, 0, &dwBufferLength)
      || (LastError = GetLastError(), LastError == 122) )
    {
      v18 = (void *)THAlloc_(a1, 1, dwBufferLength, 1, 0, 51324676);
      v50 = v18;
      if ( !MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, v18, &dwBufferLength) )
      {
        v39 = GetLastError();
        DoSetSvcError(5012, v39, 0, 51324680);
      }
LABEL_76:
      if ( pSecurityDescriptor )
      {
        THFreeAux(a1, (_DWORD)pSecurityDescriptor, v23, v24, 51324686);
        pSecurityDescriptor = 0;
      }
      if ( v34 )
      {
        THFreeAux(a1, (_DWORD)v34, v23, v24, 51324689);
        v61 = 0;
      }
      if ( pSacl )
      {
        THFreeAux(a1, (_DWORD)pSacl, v23, v24, 51324692);
        v62 = 0;
      }
      if ( v73 )
      {
        THFreeAux(a1, (_DWORD)v73, v23, v24, 51324695);
        v73 = 0;
      }
      if ( pOwner )
      {
        THFreeAux(a1, (_DWORD)pOwner, v23, v24, 51324698);
        pOwner = 0;
      }
      if ( !*(_DWORD *)(a1 + 5560) )
      {
        v19 = dwBufferLength;
        v29 = v51;
LABEL_90:
        v40 = v54;
        if ( v54 && v29 == 15 )
        {
          v59 = 0;
          ObjectDescriptor = v18;
          Size = v19;
          v4 = v64;
        }
        else
        {
          v59 = 1;
          v4 = v64;
          v43 = MergeSecurityDescriptorAnyClient(
                  a1,
                  Buf1,
                  v53,
                  v18,
                  v19,
                  v29,
                  (*(_DWORD *)(a1 + 5604) & 0x800u) >> 10,
                  &v82,
                  1u,
                  0,
                  *(_DWORD *)(v64[41] + 24LL),
                  &ObjectDescriptor,
                  &Size);
          if ( v43 )
          {
            DoSetAttError(*v4, 131353, 1005, 0, v43, 0, 51324749);
            goto LABEL_21;
          }
        }
        if ( v40 )
        {
          v89 = 0;
          v90 = 0;
          Size_4 = 1;
          v41 = DBGetParentSecurityInfo(v83, &v89, 0, 0);
          if ( v41 )
            goto LABEL_99;
          if ( (*(_DWORD *)(a1 + 5604) & 0x800) != 0 || (v42 = 1, v51 != 15) )
            v42 = 3;
          v41 = MergeSecurityDescriptorAnyClient(
                  a1,
                  *((void **)&v89 + 1),
                  DWORD1(v89),
                  ObjectDescriptor,
                  Size,
                  v51,
                  v42,
                  &v82,
                  1u,
                  0,
                  *(_DWORD *)(v4[41] + 24LL),
                  Src,
                  &v70);
          if ( v41 )
          {
LABEL_99:
            DoSetAttError(*v4, 131353, 1005, 0, v41, 0, 51324801);
            goto LABEL_21;
          }
          v44 = v70;
        }
        else
        {
          Size_4 = 0;
          Src[0] = ObjectDescriptor;
          v44 = Size;
          v70 = Size;
        }
        v16 = v44;
        v78 = v44;
        v45 = v44;
        v6 = (void *)THAlloc_(a1, 1, v44, 1, 0, 51324820);
        v84 = v6;
        memcpy_0(v6, Src[0], v45);
        if ( !gfDontStandardizeSDs && dword_18052B3E0 >= 2 )
        {
          v51 = 0;
          v54 = 0;
          if ( (unsigned int)StandardizeSecurityDescriptor(v6) )
          {
            v16 = RtlLengthSecurityDescriptor(v6);
            v78 = v16;
          }
        }
        v25 = v6;
        v85 = v6;
        v46 = v86;
        *(_QWORD *)(*(_QWORD *)(v86 + 32) + 8LL) = v6;
        **(_DWORD **)(v46 + 32) = v16;
        goto LABEL_110;
      }
LABEL_88:
      v4 = v64;
      goto LABEL_20;
    }
    v38 = 51324664;
    goto LABEL_57;
  }
  v9 = 51324366;
  v10 = 0;
  v11 = 8315;
LABEL_3:
  v12 = 5012;
LABEL_4:
  DoSetSvcError(v12, v11, v10, v9);
  return *(unsigned int *)(a1 + 5560);
}

```

## disassembly

```asm
0x18005a0c4  mov     r11, rsp
0x18005a0c7  push    rbx
0x18005a0c8  push    rsi
0x18005a0c9  push    rdi
0x18005a0ca  push    r12
0x18005a0cc  push    r13
0x18005a0ce  push    r14
0x18005a0d0  push    r15
0x18005a0d2  sub     rsp, 430h
0x18005a0d9  mov     rax, cs:__security_cookie
0x18005a0e0  xor     rax, rsp
0x18005a0e3  mov     [rsp+468h+var_48], rax
0x18005a0eb  mov     rbx, r8
0x18005a0ee  mov     [rsp+468h+var_310], rbx
0x18005a0f6  mov     r12, rdx
0x18005a0f9  mov     [rsp+468h+var_3A8], rdx
0x18005a101  mov     rdi, rcx
0x18005a104  mov     [rsp+468h+var_378], rcx
0x18005a10c  xor     r15d, r15d
0x18005a10f  mov     [r11-330h], r15
0x18005a116  mov     [r11-340h], r15d
0x18005a11d  mov     [rsp+468h+pControl], r15w
0x18005a123  mov     [r11-350h], r15
0x18005a12a  mov     [r11-3E0h], r15d
0x18005a131  mov     [r11-3E4h], r15d
0x18005a138  mov     [r11-3B0h], r15
0x18005a13f  mov     [r11-3D0h], r15d
0x18005a146  mov     [r11-380h], r15
0x18005a14d  mov     [r11-38Ch], r15d
0x18005a154  mov     rdx, [rdx+148h]
0x18005a15b  mov     edx, [rdx+0Ch]
0x18005a15e  call    SCGetClassById
0x18005a163  mov     rsi, rax
0x18005a166  test    rax, rax
0x18005a169  jnz     short loc_18005A188
0x18005a16b  mov     r9d, 30F25CEh
0x18005a171  xor     r8d, r8d
0x18005a174  mov     edx, 207Bh
0x18005a179  mov     ecx, 1394h
0x18005a17e  call    DoSetSvcError
0x18005a183  jmp     loc_18005AF76
0x18005a188  mov     r14, [rdi+15C8h]
0x18005a18f  mov     [rsp+468h+var_328], r14
0x18005a197  sub     rax, 0FFFFFFFFFFFFFF80h
0x18005a19b  mov     [rsp+468h+var_330], rax
0x18005a1a3  lea     rax, [rsp+468h+Buf1]
0x18005a1ab  mov     [rsp+468h+pSacl], rax
0x18005a1b0  lea     rax, [rsp+468h+var_3E0]
0x18005a1b8  mov     [rsp+468h+lpdwDaclSize], rax
0x18005a1bd  xor     r9d, r9d
0x18005a1c0  lea     edx, [r9+1]
0x18005a1c4  mov     r8d, 20119h
0x18005a1ca  mov     rcx, r14
0x18005a1cd  call    DBGetAttVal
0x18005a1d2  test    eax, eax
0x18005a1d4  jz      short loc_18005A1F9
0x18005a1d6  cmp     eax, 2323h
0x18005a1db  jnz     short loc_18005A226
0x18005a1dd  test    dword ptr [rdi+15E4h], 100h
0x18005a1e7  jz      short loc_18005A226
0x18005a1e9  mov     dword ptr [rsp+468h+var_3E0], r15d
0x18005a1f1  mov     [rsp+468h+Buf1], r15
0x18005a1f9  test    dword ptr [rdi+15E4h], 100h
0x18005a203  jnz     loc_18005ADBA
0x18005a209  cmp     cs:dsaInitPhase, 1
0x18005a210  jz      short loc_18005A239
0x18005a212  cmp     cs:DataSource, 1
0x18005a219  jz      loc_18005ADBA
0x18005a21f  xor     eax, eax
0x18005a221  jmp     loc_18005AF7C
0x18005a226  mov     r9d, 30F25EFh
0x18005a22c  mov     r8d, eax
0x18005a22f  mov     edx, 214Eh
0x18005a234  jmp     loc_18005A179
0x18005a239  cmp     word ptr [rbx+8], 43h ; 'C'
0x18005a23e  jnz     loc_18005ADA2
0x18005a244  cmp     [rbx+18h], r15d
0x18005a248  jz      loc_18005ADA2
0x18005a24e  mov     [rsp+468h+var_3C4], r15d
0x18005a256  mov     [rsp+468h+var_3F0], r15
0x18005a25b  mov     [rsp+468h+var_3C8], r15d
0x18005a263  mov     dword ptr [rsp+468h+Size+4], r15d
0x18005a26b  mov     [rsp+468h+var_320], r15
0x18005a273  xor     eax, eax
0x18005a275  mov     [rsp+468h+Buf2], rax
0x18005a27d  mov     [rsp+468h+var_318], rax
0x18005a285  xor     r13d, r13d
0x18005a288  mov     rax, [rbx+20h]
0x18005a28c  mov     r14, [rax+8]
0x18005a290  mov     ebx, [rax]
0x18005a292  mov     eax, [r12+88h]
0x18005a29a  and     eax, 0Fh
0x18005a29d  lea     r12d, [r13+0Fh]
0x18005a2a1  cmovnz  r12d, eax
0x18005a2a5  mov     [rsp+468h+var_3E8], r12d
0x18005a2ad  xor     r8d, r8d; RequiredInformation
0x18005a2b0  mov     edx, ebx; SecurityDescriptorLength
0x18005a2b2  mov     rcx, r14; SecurityDescriptorInput
0x18005a2b5  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x18005a2bb  test    al, al
0x18005a2bd  jnz     short loc_18005A305
0x18005a2bf  mov     r8d, 3EDh
0x18005a2c5  mov     dword ptr [rsp+468h+lpdwSaclSize], 30F264Fh
0x18005a2cd  mov     dword ptr [rsp+468h+pSacl], r13d
0x18005a2d2  mov     dword ptr [rsp+468h+lpdwDaclSize], 53Ah
0x18005a2da  xor     r9d, r9d
0x18005a2dd  mov     edx, 20119h
0x18005a2e2  mov     r12, [rsp+468h+var_3A8]
0x18005a2ea  mov     rcx, [r12]
0x18005a2ee  call    DoSetAttError
0x18005a2f3  mov     r14, [rsp+468h+var_3F0]
0x18005a2f8  mov     rbx, [rsp+468h+Buf2]
0x18005a300  jmp     loc_18005AD12
0x18005a305  cmp     cs:gfADAM, 0
0x18005a30c  jz      short loc_18005A34F
0x18005a30e  mov     rdx, [rsp+468h+var_3A8]
0x18005a316  mov     rcx, [rdx+148h]
0x18005a31d  mov     eax, [rcx+8]
0x18005a320  and     eax, 1
0x18005a323  mov     dword ptr [rsp+468h+lpdwSaclSize], eax
0x18005a327  mov     eax, [rcx+18h]
0x18005a32a  mov     dword ptr [rsp+468h+pSacl], eax
0x18005a32e  mov     rax, [rdx]
0x18005a331  mov     [rsp+468h+lpdwDaclSize], rax
0x18005a336  xor     r9d, r9d
0x18005a339  mov     r8d, r12d
0x18005a33c  mov     rdx, r14
0x18005a33f  mov     rcx, rdi
0x18005a342  call    ValidateSidReferences
0x18005a347  test    eax, eax
0x18005a349  jnz     loc_18005A9F7
0x18005a34f  lea     r8, [rsp+468h+dwRevision]; lpdwRevision
0x18005a357  lea     rdx, [rsp+468h+pControl]; pControl
0x18005a35c  mov     rcx, r14; pSecurityDescriptor
0x18005a35f  call    cs:__imp_GetSecurityDescriptorControl
0x18005a365  movzx   edx, [rsp+468h+pControl]
0x18005a36a  movzx   eax, dx
0x18005a36d  mov     ecx, 3000h
0x18005a372  and     ax, cx
0x18005a375  mov     r9, [rsp+468h+var_3A8]
0x18005a37d  cmp     ax, cx
0x18005a380  jz      short loc_18005A3A0
0x18005a382  mov     rax, [r9+148h]
0x18005a389  test    byte ptr [rax+8], 1
0x18005a38d  jnz     short loc_18005A3A0
0x18005a38f  mov     dword ptr [rsp+468h+var_3E0+4], 1
0x18005a39a  cmp     dword ptr [rax+1Ch], 0
0x18005a39e  jz      short loc_18005A3AB
0x18005a3a0  mov     dword ptr [rsp+468h+var_3E0+4], 0
0x18005a3ab  mov     eax, 4
0x18005a3b0  and     r12d, eax
0x18005a3b3  jz      short loc_18005A3B9
0x18005a3b5  test    al, dl
0x18005a3b7  jz      short loc_18005A3D7
0x18005a3b9  mov     r8d, [rsp+468h+var_3E8]
0x18005a3c1  test    r8b, 8
0x18005a3c5  setnz   cl
0x18005a3c8  bt      dx, ax
0x18005a3cc  setnb   al
0x18005a3cf  test    al, cl
0x18005a3d1  jz      loc_18005AA04
0x18005a3d7  mov     rdx, [r9+148h]
0x18005a3de  mov     ebx, [rdx+8]
0x18005a3e1  and     ebx, 1
0x18005a3e4  mov     [rsp+468h+var_338], 0
0x18005a3f0  mov     [rsp+468h+pSecurityDescriptor], 0
0x18005a3fc  mov     [rsp+468h+var_344], 0
0x18005a407  xorps   xmm0, xmm0
0x18005a40a  xor     eax, eax
0x18005a40c  movups  [rsp+468h+pAbsoluteSecurityDescriptor], xmm0
0x18005a414  movups  [rsp+468h+var_2F8], xmm0
0x18005a41c  mov     [rsp+468h+var_2E8], rax
0x18005a424  mov     [rsp+468h+dwAbsoluteSecurityDescriptorSize], 28h ; '('
0x18005a42f  mov     [rsp+468h+var_3C0], rax
0x18005a437  mov     [rsp+468h+dwDaclSize], eax
0x18005a43e  mov     [rsp+468h+var_3B8], rax
0x18005a446  mov     [rsp+468h+dwSaclSize], eax
0x18005a44d  mov     [rsp+468h+var_368], rax
0x18005a455  mov     [rsp+468h+dwOwnerSize], eax
0x18005a45c  mov     [rsp+468h+var_370], rax
0x18005a464  mov     [rsp+468h+dwPrimaryGroupSize], eax
0x18005a46b  mov     [rsp+468h+bDaclDefaulted], eax
0x18005a472  mov     [rsp+468h+bDaclPresent], eax
0x18005a479  mov     [rsp+468h+pDacl], rax
0x18005a481  mov     [rsp+468h+var_3C4], 1
0x18005a48c  test    ebx, ebx
0x18005a48e  jz      short loc_18005A4A7
0x18005a490  mov     rax, [r9]
0x18005a493  cmp     dword ptr [rax+4], 0
0x18005a497  jbe     short loc_18005A4A7
0x18005a499  add     rax, 18h
0x18005a49d  mov     [rsp+468h+var_338], rax
0x18005a4a5  jmp     short loc_18005A4ED
0x18005a4a7  lea     r8, [rsp+468h+var_338]
0x18005a4af  mov     edx, [rdx+18h]
0x18005a4b2  mov     rcx, rdi
0x18005a4b5  call    GetSidForNC
0x18005a4ba  test    eax, eax
0x18005a4bc  jz      short loc_18005A4E5
0x18005a4be  cmp     dword ptr [rdi+15B8h], 0
0x18005a4c5  jnz     loc_18005A902
0x18005a4cb  mov     r9d, 30F26A8h
0x18005a4d1  mov     ecx, 1394h
0x18005a4d6  xor     r8d, r8d
0x18005a4d9  mov     edx, eax
0x18005a4db  call    DoSetSvcError
0x18005a4e0  jmp     loc_18005A902
0x18005a4e5  mov     r9, [rsp+468h+var_3A8]
0x18005a4ed  lea     rax, [rsp+468h+var_344]
0x18005a4f5  mov     [rsp+468h+lpdwSaclSize], rax
0x18005a4fa  lea     rax, [rsp+468h+pSecurityDescriptor]
0x18005a502  mov     [rsp+468h+pSacl], rax
0x18005a507  mov     rax, [r9]
0x18005a50a  mov     [rsp+468h+lpdwDaclSize], rax
0x18005a50f  mov     r9d, ebx
0x18005a512  mov     r8, [rsp+468h+var_338]
0x18005a51a  mov     rdx, rsi
0x18005a51d  mov     rcx, rdi
0x18005a520  call    SCGetDefaultSD
0x18005a525  cmp     dword ptr [rdi+15B8h], 0
0x18005a52c  jnz     loc_18005A902
0x18005a532  lea     rax, [rsp+468h+dwPrimaryGroupSize]
0x18005a53a  mov     [rsp+468h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x18005a53f  mov     [rsp+468h+pPrimaryGroup], 0; pPrimaryGroup
0x18005a548  lea     rax, [rsp+468h+dwOwnerSize]
0x18005a550  mov     [rsp+468h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18005a555  mov     [rsp+468h+pOwner], 0; pOwner
0x18005a55e  lea     rax, [rsp+468h+dwSaclSize]
0x18005a566  mov     [rsp+468h+lpdwSaclSize], rax; lpdwSaclSize
0x18005a56b  mov     [rsp+468h+pSacl], 0; pSacl
0x18005a574  lea     rax, [rsp+468h+dwDaclSize]
0x18005a57c  mov     [rsp+468h+lpdwDaclSize], rax; lpdwDaclSize
0x18005a581  xor     r9d, r9d; pDacl
0x18005a584  lea     r8, [rsp+468h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18005a58c  lea     rdx, [rsp+468h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x18005a594  mov     rcx, r14; pSelfRelativeSecurityDescriptor
0x18005a597  call    cs:__imp_MakeAbsoluteSD
0x18005a59d  test    eax, eax
0x18005a59f  jnz     short loc_18005A5C2
0x18005a5a1  call    cs:__imp_GetLastError
0x18005a5a7  cmp     eax, 7Ah ; 'z'
0x18005a5aa  jz      short loc_18005A5B7
0x18005a5ac  mov     r9d, 30F26BAh
0x18005a5b2  jmp     loc_18005A4D1
0x18005a5b7  mov     [rsp+468h+dwAbsoluteSecurityDescriptorSize], 28h ; '('
0x18005a5c2  mov     eax, [rsp+468h+dwDaclSize]
0x18005a5c9  mov     esi, 1
0x18005a5ce  test    eax, eax
0x18005a5d0  jz      short loc_18005A5FF
0x18005a5d2  mov     r8d, eax
0x18005a5d5  mov     dword ptr [rsp+468h+pSacl], 30F26C4h
0x18005a5dd  mov     dword ptr [rsp+468h+lpdwDaclSize], 0
0x18005a5e5  mov     r9d, esi
0x18005a5e8  mov     edx, esi
0x18005a5ea  mov     rcx, rdi
0x18005a5ed  call    THAlloc_
0x18005a5f2  mov     rbx, rax
0x18005a5f5  mov     [rsp+468h+var_3C0], rax
0x18005a5fd  jmp     short loc_18005A607
0x18005a5ff  mov     rbx, [rsp+468h+var_3C0]
0x18005a607  mov     ecx, [rsp+468h+dwSaclSize]
0x18005a60e  test    ecx, ecx
0x18005a610  jz      short loc_18005A640
0x18005a612  mov     r8d, ecx
0x18005a615  mov     dword ptr [rsp+468h+pSacl], 30F26C7h
0x18005a61d  mov     dword ptr [rsp+468h+lpdwDaclSize], 0
0x18005a625  mov     r9d, esi
0x18005a628  mov     rdx, rsi
0x18005a62b  mov     rcx, rdi
0x18005a62e  call    THAlloc_
0x18005a633  mov     rsi, rax
0x18005a636  mov     [rsp+468h+var_3B8], rax
0x18005a63e  jmp     short loc_18005A648
0x18005a640  mov     rsi, [rsp+468h+var_3B8]
0x18005a648  mov     ecx, [rsp+468h+dwOwnerSize]
0x18005a64f  test    ecx, ecx
0x18005a651  jz      short loc_18005A680
0x18005a653  mov     r8d, ecx
0x18005a656  mov     dword ptr [rsp+468h+pSacl], 30F26CAh
0x18005a65e  mov     dword ptr [rsp+468h+lpdwDaclSize], 0
0x18005a666  mov     eax, 1
0x18005a66b  mov     r9d, eax
0x18005a66e  mov     edx, eax
0x18005a670  mov     rcx, rdi
0x18005a673  call    THAlloc_
0x18005a678  mov     [rsp+468h+var_368], rax
0x18005a680  mov     ecx, [rsp+468h+dwPrimaryGroupSize]
0x18005a687  test    ecx, ecx
0x18005a689  jz      short loc_18005A6BA
0x18005a68b  mov     r8d, ecx
0x18005a68e  mov     dword ptr [rsp+468h+pSacl], 30F26CDh
0x18005a696  mov     dword ptr [rsp+468h+lpdwDaclSize], 0
0x18005a69e  mov     eax, 1
0x18005a6a3  mov     r9d, eax
0x18005a6a6  mov     edx, eax
0x18005a6a8  mov     rcx, rdi
0x18005a6ab  call    THAlloc_
0x18005a6b0  mov     [rsp+468h+var_370], rax
0x18005a6b8  jmp     short loc_18005A6C2
0x18005a6ba  mov     rax, [rsp+468h+var_370]
  ... truncated ...
```
