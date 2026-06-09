# PlaiChangeSddl(ushort const *,ushort * *)

- ea: `0x180085210`
- end: `0x1800862cc`
- name: `?PlaiChangeSddl@@YAJPEBGPEAPEAG@Z`
- size: `4284`
- prototype: `__int64 __fastcall(LPCWSTR StringSecurityDescriptor, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a2908`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x180018420`
- `0x1800198b0`
- `0x18002b3a0`
- `0x180085210`
- `0x1800f1620`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008534c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008544a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008589a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800859f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085a9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085b47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085b9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085dab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085e52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086088`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008534c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008544a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008589a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800859f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085a9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085b47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085b9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085dab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085e52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086088`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180085e44`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180085e44`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180085b93`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180085b93`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180085b6f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180085b6f`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180085b3d`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180085b3d`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180085a8f`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180085a8f`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800859e4`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800859e4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18008592a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18008592a`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18008543c`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18008588a`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18008543c`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18008588a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180085d9a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180085d9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008627c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008628b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008629a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008627c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008628b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008629a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180085286`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180085286`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180085fd9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180085fd9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008533e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008533e`

## pseudocode

```c
__int64 __fastcall PlaiChangeSddl(LPCWSTR StringSecurityDescriptor, unsigned __int16 **a2)
{
  struct _ACL *pSacl; // r14
  DWORD v5; // eax
  int v6; // eax
  signed int v7; // ebx
  __int64 v8; // rax
  SECURITY_INFORMATION *p_SecurityInformation; // r9
  SECURITY_INFORMATION *v10; // rcx
  DWORD LastError; // eax
  signed int v12; // eax
  __int64 v13; // rax
  DWORD v14; // eax
  signed int v15; // eax
  __int64 v16; // rax
  __int64 v17; // rax
  struct _ACL *v18; // r13
  struct _ACL *v19; // rsi
  __int64 v20; // rax
  PSECURITY_DESCRIPTOR v21; // rsi
  __int64 v22; // rax
  __int64 v23; // rax
  void *pPrimaryGroup; // rax
  __int64 v25; // rax
  DWORD v26; // eax
  __int64 v27; // rax
  DWORD LengthSid; // eax
  DWORD v29; // edx
  struct _ACL *v30; // rax
  __int64 v31; // rax
  DWORD v32; // eax
  __int64 v33; // rax
  DWORD v34; // eax
  signed int v35; // eax
  __int64 v36; // rax
  int v37; // r14d
  DWORD i; // esi
  DWORD v39; // eax
  unsigned __int16 *v40; // r9
  BOOL v41; // eax
  DWORD v42; // eax
  __int64 v43; // rax
  __int64 v44; // rax
  DWORD v45; // eax
  signed int v46; // eax
  __int64 v47; // rax
  DWORD v48; // eax
  signed int v49; // eax
  __int64 v50; // rax
  signed int v51; // eax
  __int64 v52; // rax
  const unsigned __int16 *v53; // rcx
  const char *v54; // rdx
  int v55; // r8d
  unsigned __int16 *v56; // rax
  __int64 v57; // rax
  DWORD v58; // eax
  signed int v59; // eax
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rax
  int lpdwDaclSize; // [rsp+20h] [rbp-E0h]
  int lpdwDaclSizea; // [rsp+20h] [rbp-E0h]
  int lpdwDaclSizeb; // [rsp+20h] [rbp-E0h]
  int lpdwDaclSizec; // [rsp+20h] [rbp-E0h]
  int lpdwDaclSized; // [rsp+20h] [rbp-E0h]
  int lpdwDaclSizee; // [rsp+20h] [rbp-E0h]
  SECURITY_INFORMATION SecurityInformation; // [rsp+70h] [rbp-90h] BYREF
  int v71; // [rsp+78h] [rbp-88h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+80h] [rbp-80h]
  DWORD dwDaclSize; // [rsp+88h] [rbp-78h] BYREF
  struct _ACL *v74; // [rsp+90h] [rbp-70h]
  DWORD dwPrimaryGroupSize; // [rsp+98h] [rbp-68h] BYREF
  DWORD dwOwnerSize; // [rsp+9Ch] [rbp-64h] BYREF
  DWORD dwSaclSize; // [rsp+A0h] [rbp-60h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+A4h] [rbp-5Ch] BYREF
  PSID Sid; // [rsp+A8h] [rbp-58h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID pAce; // [rsp+B8h] [rbp-48h] BYREF
  PSID pOwner; // [rsp+C0h] [rbp-40h]
  LPWSTR StringSecurityDescriptora; // [rsp+C8h] [rbp-38h] BYREF
  PACL pAcl; // [rsp+D0h] [rbp-30h]
  LPCVOID lpMem; // [rsp+D8h] [rbp-28h]
  __int64 pAclInformation; // [rsp+E0h] [rbp-20h] BYREF
  int v87; // [rsp+E8h] [rbp-18h]
  unsigned __int16 v88[64]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v89[64]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 v90[64]; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned __int16 v91[64]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v92[64]; // [rsp+2F0h] [rbp+1F0h] BYREF
  unsigned __int16 v93[64]; // [rsp+370h] [rbp+270h] BYREF
  unsigned __int16 v94[64]; // [rsp+3F0h] [rbp+2F0h] BYREF
  unsigned __int16 v95[64]; // [rsp+470h] [rbp+370h] BYREF
  unsigned __int16 v96[64]; // [rsp+4F0h] [rbp+3F0h] BYREF
  unsigned __int16 v97[64]; // [rsp+570h] [rbp+470h] BYREF
  unsigned __int16 v98[64]; // [rsp+5F0h] [rbp+4F0h] BYREF
  unsigned __int16 v99[64]; // [rsp+670h] [rbp+570h] BYREF
  unsigned __int16 v100[64]; // [rsp+6F0h] [rbp+5F0h] BYREF
  unsigned __int16 v101[64]; // [rsp+770h] [rbp+670h] BYREF
  unsigned __int16 v102[64]; // [rsp+7F0h] [rbp+6F0h] BYREF
  unsigned __int16 v103[64]; // [rsp+870h] [rbp+770h] BYREF
  unsigned __int16 v104[64]; // [rsp+8F0h] [rbp+7F0h] BYREF
  unsigned __int16 v105[64]; // [rsp+970h] [rbp+870h] BYREF
  unsigned __int16 v106[64]; // [rsp+9F0h] [rbp+8F0h] BYREF
  unsigned __int16 v107[64]; // [rsp+A70h] [rbp+970h] BYREF
  unsigned __int16 v108[64]; // [rsp+AF0h] [rbp+9F0h] BYREF

  pSacl = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  dwAbsoluteSecurityDescriptorSize = 0;
  pAce = 0;
  pAclInformation = 0;
  v87 = 0;
  SecurityInformation = 0;
  SecurityDescriptor = 0;
  Sid = 0;
  StringSecurityDescriptora = 0;
  if ( ConvertStringSidToSidW(L"S-1-5-80-2661322625-712705077-2999183737-3043590567-590698655", &Sid)
    || (v5 = GetLastError(), v6 = PlaiHResultFromWin32(v5), v7 = v6, v6 >= 0) )
  {
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
    {
      LastError = GetLastError();
      v12 = PlaiHResultFromWin32(LastError);
      v7 = v12;
      if ( v12 < 0 )
      {
        v71 = 0;
        SecurityInformation = v12;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_181;
        }
        PlaiWhoAmI(v89, 0x4000000000000800uLL);
        v13 = -1;
        do
          ++v13;
        while ( v89[v13] );
        goto LABEL_16;
      }
    }
    dwPrimaryGroupSize = 0;
    dwOwnerSize = 0;
    dwSaclSize = 0;
    dwDaclSize = 0;
    dwAbsoluteSecurityDescriptorSize = 0;
    if ( MakeAbsoluteSD(
           SecurityDescriptor,
           0,
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
      goto LABEL_174;
    }
    v14 = GetLastError();
    v15 = PlaiHResultFromWin32(v14);
    v7 = v15;
    if ( v15 != -2147024774 )
    {
      if ( v15 < 0 )
      {
        v71 = 0;
        SecurityInformation = v15;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_181;
        }
        PlaiWhoAmI(v90, 0x4000000000000800uLL);
        v16 = -1;
        do
          ++v16;
        while ( v90[v16] );
        goto LABEL_16;
      }
LABEL_174:
      v7 = -2147467259;
      SecurityInformation = -2147467259;
      v71 = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v108, 0x4000000000000800uLL);
        v62 = -1;
        do
          ++v62;
        while ( v108[v62] );
        p_SecurityInformation = &SecurityInformation;
        v10 = (SECURITY_INFORMATION *)&v71;
        goto LABEL_180;
      }
      goto LABEL_181;
    }
    pSecurityDescriptor = PlaiAlloc(dwAbsoluteSecurityDescriptorSize, 1, 0, qword_180147320, lpdwDaclSize);
    if ( !pSecurityDescriptor )
    {
      v7 = -2147024882;
      SecurityInformation = -2147024882;
      v71 = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_181;
      }
      PlaiWhoAmI(v91, 0x4000000000000800uLL);
      v17 = -1;
      do
        ++v17;
      while ( v91[v17] );
LABEL_16:
      p_SecurityInformation = &SecurityInformation;
      v10 = (SECURITY_INFORMATION *)&v71;
LABEL_180:
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        p_SecurityInformation,
        4,
        qword_180147320,
        1,
        v10,
        4,
        "PlaiChangeSddl",
        15);
      goto LABEL_181;
    }
    pOwner = 0;
    lpMem = 0;
    v18 = 0;
    pAcl = (PACL)PlaiAlloc(dwDaclSize, 1, 0, qword_180147320, lpdwDaclSizea);
    v19 = pAcl;
    if ( !pAcl )
    {
      v7 = -2147024882;
      v71 = 0;
      SecurityInformation = -2147024882;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_40;
      }
      PlaiWhoAmI(v92, 0x4000000000000800uLL);
      v20 = -1;
      do
        ++v20;
      while ( v92[v20] );
LABEL_39:
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &SecurityInformation,
        4,
        qword_180147320,
        1,
        &v71,
        4,
        "PlaiChangeSddl",
        15);
LABEL_40:
      v21 = pSecurityDescriptor;
LABEL_112:
      PlaiFree(v21, 1);
      if ( pAcl )
        PlaiFree(pAcl, 1);
      if ( pSacl )
        PlaiFree(pSacl, 1);
      if ( pOwner )
        PlaiFree(pOwner, 1);
      if ( lpMem )
        PlaiFree(lpMem, 1);
      if ( v18 )
        PlaiFree(v18, 1);
      goto LABEL_181;
    }
    v74 = (struct _ACL *)PlaiAlloc(dwSaclSize, 1, 0, qword_180147320, lpdwDaclSizeb);
    pSacl = v74;
    if ( !v74 )
    {
      v7 = -2147024882;
      SecurityInformation = -2147024882;
      v71 = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_40;
      }
      PlaiWhoAmI(v93, 0x4000000000000800uLL);
      v22 = -1;
      do
        ++v22;
      while ( v93[v22] );
      goto LABEL_39;
    }
    pOwner = PlaiAlloc(dwOwnerSize, 1, 0, qword_180147320, lpdwDaclSizec);
    if ( !pOwner )
    {
      v7 = -2147024882;
      SecurityInformation = -2147024882;
      v71 = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_40;
      }
      PlaiWhoAmI(v94, 0x4000000000000800uLL);
      v23 = -1;
      do
        ++v23;
      while ( v94[v23] );
      goto LABEL_39;
    }
    pPrimaryGroup = PlaiAlloc(dwPrimaryGroupSize, 1, 0, qword_180147320, lpdwDaclSized);
    lpMem = pPrimaryGroup;
    if ( !pPrimaryGroup )
    {
      v7 = -2147024882;
      SecurityInformation = -2147024882;
      v71 = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_40;
      }
      PlaiWhoAmI(v95, 0x4000000000000800uLL);
      v25 = -1;
      do
        ++v25;
      while ( v95[v25] );
      goto LABEL_39;
    }
    if ( !MakeAbsoluteSD(
            SecurityDescriptor,
            pSecurityDescriptor,
            &dwAbsoluteSecurityDescriptorSize,
            v19,
            &dwDaclSize,
            pSacl,
            &dwSaclSize,
            pOwner,
            &dwOwnerSize,
            pPrimaryGroup,
            &dwPrimaryGroupSize) )
    {
      v26 = GetLastError();
      v7 = PlaiHResultFromWin32(v26);
      if ( v7 < 0 )
      {
        v71 = 0;
        SecurityInformation = v7;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_40;
        }
        PlaiWhoAmI(v96, 0x4000000000000800uLL);
        v27 = -1;
        do
          ++v27;
        while ( v96[v27] );
        goto LABEL_39;
      }
    }
    LengthSid = GetLengthSid(Sid);
    v29 = LengthSid + dwDaclSize + 8;
    if ( v29 < dwDaclSize )
    {
      dwDaclSize = -1;
      v7 = -2147024362;
      v71 = 0;
      SecurityInformation = -2147024362;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_40;
      }
      PlaiWhoAmI(v107, 0x4000000000000800uLL);
      v61 = -1;
      do
        ++v61;
      while ( v107[v61] );
      goto LABEL_39;
    }
    dwDaclSize += LengthSid + 8;
    v30 = (struct _ACL *)PlaiAlloc(v29, 1, 0, qword_180147320, lpdwDaclSizee);
    v18 = v30;
    if ( !v30 )
    {
      v7 = -2147024882;
      v71 = 0;
      SecurityInformation = -2147024882;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_40;
      }
      PlaiWhoAmI(v97, 0x4000000000000800uLL);
      v31 = -1;
      do
        ++v31;
      while ( v97[v31] );
      goto LABEL_39;
    }
    if ( !InitializeAcl(v30, dwDaclSize, 2u) )
    {
      v32 = GetLastError();
      v7 = PlaiHResultFromWin32(v32);
      if ( v7 < 0 )
      {
        v71 = 0;
        SecurityInformation = v7;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_40;
        }
        PlaiWhoAmI(v98, 0x4000000000000800uLL);
        v33 = -1;
        do
          ++v33;
        while ( v98[v33] );
        goto LABEL_39;
      }
    }
    if ( !GetAclInformation(v19, &pAclInformation, 0xCu, AclSizeInformation) )
    {
      v34 = GetLastError();
      v35 = PlaiHResultFromWin32(v34);
      v7 = v35;
      if ( v35 < 0 )
      {
        v71 = 0;
        SecurityInformation = v35;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_40;
        }
        PlaiWhoAmI(v99, 0x4000000000000800uLL);
        v36 = -1;
        do
          ++v36;
        while ( v99[v36] );
        goto LABEL_39;
      }
    }
    v37 = 1;
    for ( i = 0; i < (unsigned int)pAclInformation; ++i )
    {
      if ( !GetAce(pAcl, i, &pAce) )
      {
        v39 = GetLastError();
        v7 = PlaiHResultFromWin32(v39);
        if ( v7 < 0 )
        {
          v71 = 0;
          SecurityInformation = v7;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_110;
          }
          PlaiWhoAmI(v100, 0x4000000000000800uLL);
          v43 = -1;
          do
            ++v43;
          while ( v100[v43] );
          goto LABEL_109;
        }
      }
      v40 = (unsigned __int16 *)pAce;
      if ( !*(_BYTE *)pAce )
      {
        v41 = EqualSid(Sid, (char *)pAce + 8);
        v40 = (unsigned __int16 *)pAce;
        if ( v41 )
          v37 = 0;
      }
      if ( !AddAce(v18, 2u, i, v40, v40[1]) )
      {
        v42 = GetLastError();
        v7 = PlaiHResultFromWin32(v42);
        if ( v7 < 0 )
        {
          v71 = 0;
          SecurityInformation = v7;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v101, 0x4000000000000800uLL);
            v44 = -1;
            do
              ++v44;
            while ( v101[v44] );
            goto LABEL_109;
          }
LABEL_110:
          v21 = pSecurityDescriptor;
          goto LABEL_111;
        }
      }
    }
    if ( v37 )
    {
      if ( !AddAccessAllowedAceEx(v18, 2u, 0, 0x1301FFu, Sid) )
      {
        v45 = GetLastError();
        v46 = PlaiHResultFromWin32(v45);
        v7 = v46;
        if ( v46 < 0 )
        {
          v71 = 0;
          SecurityInformation = v46;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_110;
          }
          PlaiWhoAmI(v102, 0x4000000000000800uLL);
          v47 = -1;
          do
            ++v47;
          while ( v102[v47] );
LABEL_109:
          EventingWriteEvent(
            &g_Eventing,
            PLA_EVENT_ERROR,
            5,
            &SecurityInformation,
            4,
            qword_180147320,
            1,
            &v71,
            4,
            "PlaiChangeSddl",
            15);
          goto LABEL_110;
        }
      }
    }
    v21 = pSecurityDescriptor;
    if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v18, 0) )
    {
      v48 = GetLastError();
      v49 = PlaiHResultFromWin32(v48);
      v7 = v49;
      if ( v49 < 0 )
      {
        v71 = 0;
        SecurityInformation = v49;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_111;
        }
        PlaiWhoAmI(v103, 0x4000000000000800uLL);
        v50 = -1;
        do
          ++v50;
        while ( v103[v50] );
LABEL_144:
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &SecurityInformation,
          4,
          qword_180147320,
          1,
          &v71,
          4,
          "PlaiChangeSddl",
          15);
LABEL_111:
        pSacl = v74;
        goto LABEL_112;
      }
    }
    v51 = PlaiGetSecurityInformation(pSecurityDescriptor, &SecurityInformation);
    v7 = v51;
    if ( v51 < 0 )
    {
      v71 = 0;
      SecurityInformation = v51;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_111;
      }
      PlaiWhoAmI(v104, 0x4000000000000800uLL);
      v52 = -1;
      do
        ++v52;
      while ( v104[v52] );
      goto LABEL_144;
    }
    if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
           v21,
           1u,
           SecurityInformation,
           &StringSecurityDescriptora,
           0) )
    {
      v7 = 0;
    }
    else
    {
      v58 = GetLastError();
      v59 = PlaiHResultFromWin32(v58);
      v7 = v59;
      if ( v59 < 0 )
      {
        v71 = 0;
        SecurityInformation = v59;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_111;
        }
        PlaiWhoAmI(v105, 0x4000000000000800uLL);
        v60 = -1;
        do
          ++v60;
        while ( v105[v60] );
        goto LABEL_144;
      }
    }
    PlaiFreeString(*a2);
    v53 = StringSecurityDescriptora;
    *a2 = 0;
    v56 = PlaiAllocStringEx(v53, v54, v55);
    *a2 = v56;
    if ( v56 )
      goto LABEL_111;
    v7 = -2147024882;
    SecurityInformation = -2147024882;
    v71 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_111;
    }
    PlaiWhoAmI(v106, 0x4000000000000800uLL);
    v57 = -1;
    do
      ++v57;
    while ( v106[v57] );
    goto LABEL_144;
  }
  SecurityInformation = 0;
  v71 = v6;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v88, 0x4000000000000800uLL);
    v8 = -1;
    do
      ++v8;
    while ( v88[v8] );
    p_SecurityInformation = (SECURITY_INFORMATION *)&v71;
    v10 = &SecurityInformation;
    goto LABEL_180;
  }
LABEL_181:
  if ( StringSecurityDescriptora )
    LocalFree(StringSecurityDescriptora);
  if ( Sid )
    LocalFree(Sid);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180085210  mov     [rsp-8+arg_10], rbx
0x180085215  push    rbp
0x180085216  push    rsi
0x180085217  push    rdi
0x180085218  push    r12
0x18008521a  push    r13
0x18008521c  push    r14
0x18008521e  push    r15
0x180085220  lea     rbp, [rsp-0A80h]
0x180085228  sub     rsp, 0B80h
0x18008522f  mov     rax, cs:__security_cookie
0x180085236  xor     rax, rsp
0x180085239  mov     [rbp+0AB0h+var_40], rax
0x180085240  xor     r14d, r14d
0x180085243  xor     eax, eax
0x180085245  mov     r12, rdx
0x180085248  mov     [rbp+0AB0h+dwDaclSize], r14d
0x18008524c  mov     rsi, rcx
0x18008524f  mov     [rbp+0AB0h+dwSaclSize], r14d
0x180085253  lea     rdx, [rbp+0AB0h+Sid]; Sid
0x180085257  mov     [rbp+0AB0h+dwOwnerSize], r14d
0x18008525b  lea     rcx, StringSid; "S-1-5-80-2661322625-712705077-299918373"...
0x180085262  mov     [rbp+0AB0h+dwPrimaryGroupSize], r14d
0x180085266  mov     [rbp+0AB0h+dwAbsoluteSecurityDescriptorSize], r14d
0x18008526a  mov     [rbp+0AB0h+pAce], r14
0x18008526e  mov     [rbp+0AB0h+pAclInformation], rax
0x180085272  mov     [rbp+0AB0h+var_AC8], eax
0x180085275  mov     [rsp+0BB0h+SecurityInformation], r14d
0x18008527a  mov     [rbp+0AB0h+SecurityDescriptor], r14
0x18008527e  mov     [rbp+0AB0h+Sid], r14
0x180085282  mov     [rbp+0AB0h+StringSecurityDescriptor], r14
0x180085286  call    cs:__imp_ConvertStringSidToSidW
0x18008528c  test    eax, eax
0x18008528e  jnz     loc_18008532E
0x180085294  call    cs:__imp_GetLastError
0x18008529a  mov     ecx, eax; unsigned int
0x18008529c  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800852a1  mov     ebx, eax
0x1800852a3  test    eax, eax
0x1800852a5  jns     loc_18008532E
0x1800852ab  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800852b2  mov     [rsp+0BB0h+SecurityInformation], r14d
0x1800852b7  mov     [rsp+0BB0h+var_B38], eax
0x1800852bb  jz      loc_180086273
0x1800852c1  mov     rdx, 4000000000000800h; unsigned __int64
0x1800852cb  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800852d2  jz      loc_180086273
0x1800852d8  mov     rax, cs:qword_180169748
0x1800852df  and     rax, rdx
0x1800852e2  cmp     cs:qword_180169748, rax
0x1800852e9  jnz     loc_180086273
0x1800852ef  lea     rcx, [rbp+0AB0h+var_AC0]; unsigned __int16 *
0x1800852f3  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800852f8  lea     rcx, [rbp+0AB0h+var_AC0]
0x1800852fc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180085300  inc     rax
0x180085303  cmp     [rcx+rax*2], r14w
0x180085308  jnz     short loc_180085300
0x18008530a  lea     ecx, [rax+rax]
0x18008530d  mov     edi, 1
0x180085312  add     rcx, 2
0x180085316  lea     rax, [rbp+0AB0h+var_AC0]
0x18008531a  mov     [rsp+0BB0h+var_B50], rcx
0x18008531f  lea     r9, [rsp+0BB0h+var_B38]
0x180085324  lea     rcx, [rsp+0BB0h+SecurityInformation]
0x180085329  jmp     loc_18008621D
0x18008532e  xor     r9d, r9d; SecurityDescriptorSize
0x180085331  lea     r8, [rbp+0AB0h+SecurityDescriptor]; SecurityDescriptor
0x180085335  mov     rcx, rsi; StringSecurityDescriptor
0x180085338  lea     edi, [r9+1]
0x18008533c  mov     edx, edi; StringSDRevision
0x18008533e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180085344  test    eax, eax
0x180085346  jnz     loc_1800853E8
0x18008534c  call    cs:__imp_GetLastError
0x180085352  mov     ecx, eax; unsigned int
0x180085354  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180085359  mov     ebx, eax
0x18008535b  test    eax, eax
0x18008535d  jns     loc_1800853E8
0x180085363  cmp     dword ptr cs:xmmword_180169738, r14d
0x18008536a  mov     [rsp+0BB0h+var_B38], r14d
0x18008536f  mov     [rsp+0BB0h+SecurityInformation], eax
0x180085373  jz      loc_180086273
0x180085379  mov     rdx, 4000000000000800h; unsigned __int64
0x180085383  test    qword ptr cs:xmmword_180169738+8, rdx
0x18008538a  jz      loc_180086273
0x180085390  mov     rax, cs:qword_180169748
0x180085397  and     rax, rdx
0x18008539a  cmp     cs:qword_180169748, rax
0x1800853a1  jnz     loc_180086273
0x1800853a7  lea     rcx, [rbp+0AB0h+var_A40]; unsigned __int16 *
0x1800853ab  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800853b0  lea     rcx, [rbp+0AB0h+var_A40]
0x1800853b4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800853b8  inc     rax
0x1800853bb  cmp     [rcx+rax*2], r14w
0x1800853c0  jnz     short loc_1800853B8
0x1800853c2  lea     ecx, [rax+rax]
0x1800853c5  lea     rax, [rbp+0AB0h+var_A40]
0x1800853c9  lea     r15, qword_180147320
0x1800853d0  add     rcx, 2
0x1800853d4  lea     r9, [rsp+0BB0h+SecurityInformation]
0x1800853d9  mov     [rsp+0BB0h+var_B50], rcx
0x1800853de  lea     rcx, [rsp+0BB0h+var_B38]
0x1800853e3  jmp     loc_180086224
0x1800853e8  mov     rcx, [rbp+0AB0h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x1800853ec  lea     rax, [rbp+0AB0h+dwPrimaryGroupSize]
0x1800853f0  mov     [rsp+0BB0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x1800853f5  lea     r8, [rbp+0AB0h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x1800853f9  mov     [rsp+0BB0h+pPrimaryGroup], r14; pPrimaryGroup
0x1800853fe  lea     rax, [rbp+0AB0h+dwOwnerSize]
0x180085402  mov     [rsp+0BB0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180085407  xor     r9d, r9d; pDacl
0x18008540a  mov     [rsp+0BB0h+pOwner], r14; pOwner
0x18008540f  lea     rax, [rbp+0AB0h+dwSaclSize]
0x180085413  mov     [rsp+0BB0h+lpdwSaclSize], rax; lpdwSaclSize
0x180085418  xor     edx, edx; pAbsoluteSecurityDescriptor
0x18008541a  lea     rax, [rbp+0AB0h+dwDaclSize]
0x18008541e  mov     [rsp+0BB0h+pSacl], r14; pSacl
0x180085423  mov     [rsp+0BB0h+lpdwDaclSize], rax; int
0x180085428  mov     [rbp+0AB0h+dwPrimaryGroupSize], r14d
0x18008542c  mov     [rbp+0AB0h+dwOwnerSize], r14d
0x180085430  mov     [rbp+0AB0h+dwSaclSize], r14d
0x180085434  mov     [rbp+0AB0h+dwDaclSize], r14d
0x180085438  mov     [rbp+0AB0h+dwAbsoluteSecurityDescriptorSize], r14d
0x18008543c  call    cs:__imp_MakeAbsoluteSD
0x180085442  test    eax, eax
0x180085444  jnz     loc_180086196
0x18008544a  call    cs:__imp_GetLastError
0x180085450  mov     ecx, eax; unsigned int
0x180085452  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180085457  mov     ebx, eax
0x180085459  cmp     eax, 8007007Ah
0x18008545e  jz      short loc_1800854DC
0x180085460  test    eax, eax
0x180085462  jns     loc_180086196
0x180085468  cmp     dword ptr cs:xmmword_180169738, r14d
0x18008546f  mov     [rsp+0BB0h+var_B38], r14d
0x180085474  mov     [rsp+0BB0h+SecurityInformation], eax
0x180085478  jz      loc_180086273
0x18008547e  mov     rdx, 4000000000000800h; unsigned __int64
0x180085488  test    qword ptr cs:xmmword_180169738+8, rdx
0x18008548f  jz      loc_180086273
0x180085495  mov     rax, cs:qword_180169748
0x18008549c  and     rax, rdx
0x18008549f  cmp     cs:qword_180169748, rax
0x1800854a6  jnz     loc_180086273
0x1800854ac  lea     rcx, [rbp+0AB0h+var_9C0]; unsigned __int16 *
0x1800854b3  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800854b8  lea     rcx, [rbp+0AB0h+var_9C0]
0x1800854bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800854c3  inc     rax
0x1800854c6  cmp     [rcx+rax*2], r14w
0x1800854cb  jnz     short loc_1800854C3
0x1800854cd  lea     ecx, [rax+rax]
0x1800854d0  lea     rax, [rbp+0AB0h+var_9C0]
0x1800854d7  jmp     loc_1800853C9
0x1800854dc  mov     ecx, [rbp+0AB0h+dwAbsoluteSecurityDescriptorSize]; dwBytes
0x1800854df  lea     r15, qword_180147320
0x1800854e6  mov     r9, r15; char *
0x1800854e9  xor     r8d, r8d; int
0x1800854ec  mov     edx, edi; int
0x1800854ee  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800854f3  mov     [rbp+0AB0h+pSecurityDescriptor], rax
0x1800854f7  mov     rbx, rax
0x1800854fa  test    rax, rax
0x1800854fd  jnz     short loc_18008557A
0x1800854ff  cmp     dword ptr cs:xmmword_180169738, r14d
0x180085506  mov     eax, 8007000Eh
0x18008550b  mov     ebx, eax
0x18008550d  mov     [rsp+0BB0h+SecurityInformation], eax
0x180085511  mov     [rsp+0BB0h+var_B38], r14d
0x180085516  jz      loc_180086273
0x18008551c  mov     rdx, 4000000000000800h; unsigned __int64
0x180085526  test    qword ptr cs:xmmword_180169738+8, rdx
0x18008552d  jz      loc_180086273
0x180085533  mov     rax, cs:qword_180169748
0x18008553a  and     rax, rdx
0x18008553d  cmp     cs:qword_180169748, rax
0x180085544  jnz     loc_180086273
0x18008554a  lea     rcx, [rbp+0AB0h+var_940]; unsigned __int16 *
0x180085551  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180085556  lea     rcx, [rbp+0AB0h+var_940]
0x18008555d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180085561  inc     rax
0x180085564  cmp     [rcx+rax*2], r14w
0x180085569  jnz     short loc_180085561
0x18008556b  lea     ecx, [rax+rax]
0x18008556e  lea     rax, [rbp+0AB0h+var_940]
0x180085575  jmp     loc_1800853D0
0x18008557a  mov     ecx, [rbp+0AB0h+dwDaclSize]; dwBytes
0x18008557d  mov     r9, r15; char *
0x180085580  xor     r8d, r8d; int
0x180085583  mov     [rbp+0AB0h+var_AF0], r14
0x180085587  mov     edx, edi; int
0x180085589  mov     [rbp+0AB0h+lpMem], r14
0x18008558d  mov     r13, r14
0x180085590  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x180085595  mov     [rbp+0AB0h+pAcl], rax
0x180085599  mov     rsi, rax
0x18008559c  test    rax, rax
0x18008559f  jnz     loc_180085689
0x1800855a5  xor     r12d, r12d
0x1800855a8  mov     eax, 8007000Eh
0x1800855ad  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800855b4  mov     ebx, eax
0x1800855b6  mov     [rsp+0BB0h+var_B38], r12d
0x1800855bb  mov     [rsp+0BB0h+SecurityInformation], eax
0x1800855bf  jz      loc_180085680
0x1800855c5  mov     rdx, 4000000000000800h; unsigned __int64
0x1800855cf  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800855d6  jz      loc_180085680
0x1800855dc  mov     rax, cs:qword_180169748
0x1800855e3  and     rax, rdx
0x1800855e6  cmp     cs:qword_180169748, rax
0x1800855ed  jnz     loc_180085680
0x1800855f3  lea     rcx, [rbp+0AB0h+var_8C0]; unsigned __int16 *
0x1800855fa  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800855ff  lea     rcx, [rbp+0AB0h+var_8C0]
0x180085606  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008560a  inc     rax
0x18008560d  cmp     [rcx+rax*2], r12w
0x180085612  jnz     short loc_18008560A
0x180085614  lea     ecx, [rax+rax]
0x180085617  lea     rax, [rbp+0AB0h+var_8C0]
0x18008561e  add     rcx, 2
0x180085622  lea     r9, [rsp+0BB0h+SecurityInformation]
0x180085627  mov     [rsp+0BB0h+var_B50], rcx
0x18008562c  lea     rdx, PLA_EVENT_ERROR
0x180085633  mov     [rsp+0BB0h+var_B58], rax
0x180085638  lea     rcx, [rsp+0BB0h+var_B38]
0x18008563d  mov     [rsp+0BB0h+lpdwPrimaryGroupSize], 0Fh
0x180085646  lea     rax, aPlaichangesddl; "PlaiChangeSddl"
0x18008564d  mov     [rsp+0BB0h+pPrimaryGroup], rax
0x180085652  mov     eax, 4
0x180085657  mov     [rsp+0BB0h+lpdwOwnerSize], rax
0x18008565c  mov     [rsp+0BB0h+pOwner], rcx
0x180085661  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180085668  mov     [rsp+0BB0h+lpdwSaclSize], rdi
0x18008566d  mov     [rsp+0BB0h+pSacl], r15
0x180085672  lea     r8d, [rax+1]
0x180085676  mov     [rsp+0BB0h+lpdwDaclSize], rax
0x18008567b  call    EventingWriteEvent
0x180085680  mov     rsi, [rbp+0AB0h+pSecurityDescriptor]
0x180085684  jmp     loc_180085C99
0x180085689  mov     ecx, [rbp+0AB0h+dwSaclSize]; dwBytes
0x18008568c  mov     r9, r15; char *
0x18008568f  xor     r8d, r8d; int
0x180085692  mov     edx, edi; int
0x180085694  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x180085699  xor     ecx, ecx
0x18008569b  mov     [rbp+0AB0h+var_B20], rax
0x18008569f  mov     r14, rax
0x1800856a2  test    rax, rax
0x1800856a5  jnz     short loc_180085717
0x1800856a7  cmp     dword ptr cs:xmmword_180169738, ecx
0x1800856ad  mov     eax, 8007000Eh
0x1800856b2  mov     ebx, eax
0x1800856b4  mov     [rsp+0BB0h+SecurityInformation], eax
0x1800856b8  mov     [rsp+0BB0h+var_B38], ecx
0x1800856bc  jz      short loc_180085680
0x1800856be  mov     rdx, 4000000000000800h; unsigned __int64
0x1800856c8  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800856cf  jz      short loc_180085680
0x1800856d1  mov     rax, cs:qword_180169748
0x1800856d8  and     rax, rdx
0x1800856db  cmp     cs:qword_180169748, rax
0x1800856e2  jnz     short loc_180085680
0x1800856e4  lea     rcx, [rbp+0AB0h+var_840]; unsigned __int16 *
0x1800856eb  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800856f0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800856f4  lea     rcx, [rbp+0AB0h+var_840]
0x1800856fb  xor     r12d, r12d
0x1800856fe  inc     rax
0x180085701  cmp     [rcx+rax*2], r12w
0x180085706  jnz     short loc_1800856FE
0x180085708  lea     ecx, [rax+rax]
0x18008570b  lea     rax, [rbp+0AB0h+var_840]
0x180085712  jmp     loc_18008561E
0x180085717  mov     ecx, [rbp+0AB0h+dwOwnerSize]; dwBytes
0x18008571a  mov     r9, r15; char *
0x18008571d  xor     r8d, r8d; int
0x180085720  mov     edx, edi; int
0x180085722  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x180085727  xor     ecx, ecx
0x180085729  mov     [rbp+0AB0h+var_AF0], rax
0x18008572d  test    rax, rax
0x180085730  jnz     short loc_1800857AE
0x180085732  cmp     dword ptr cs:xmmword_180169738, ecx
0x180085738  mov     eax, 8007000Eh
0x18008573d  mov     ebx, eax
0x18008573f  mov     [rsp+0BB0h+SecurityInformation], eax
0x180085743  mov     [rsp+0BB0h+var_B38], ecx
0x180085747  jz      loc_180085680
0x18008574d  mov     rdx, 4000000000000800h; unsigned __int64
0x180085757  test    qword ptr cs:xmmword_180169738+8, rdx
0x18008575e  jz      loc_180085680
0x180085764  mov     rax, cs:qword_180169748
0x18008576b  and     rax, rdx
  ... truncated ...
```
