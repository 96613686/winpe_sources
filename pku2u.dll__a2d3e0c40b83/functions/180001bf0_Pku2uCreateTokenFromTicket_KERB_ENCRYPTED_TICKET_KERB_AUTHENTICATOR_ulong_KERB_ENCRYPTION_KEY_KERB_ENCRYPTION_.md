# Pku2uCreateTokenFromTicket(KERB_ENCRYPTED_TICKET *,KERB_AUTHENTICATOR *,ulong,KERB_ENCRYPTION_KEY *,KERB_ENCRYPTION_KEY *,_LUID *,void * *,void * *,_UNICODE_STRING *,_LARGE_INTEGER *)

- ea: `0x180001bf0`
- end: `0x180002cb3`
- name: `?Pku2uCreateTokenFromTicket@@YAJPEAUKERB_ENCRYPTED_TICKET@@PEAUKERB_AUTHENTICATOR@@KPEAUKERB_ENCRYPTION_KEY@@2PEAU_LUID@@PEAPEAX4PEAU_UNICODE_STRING@@PEAT_LARGE_INTEGER@@@Z`
- size: `4291`
- prototype: `__int64 __fastcall(struct KERB_ENCRYPTED_TICKET *, struct KERB_AUTHENTICATOR *, int, struct KERB_ENCRYPTION_KEY *, struct KERB_ENCRYPTION_KEY *, struct _LUID *, void **, void **, struct _UNICODE_STRING *, union _LARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b990`

## callees

- `0x180001bf0`
- `0x180002cbc`
- `0x180002e40`
- `0x180003700`
- `0x180003bc0`
- `0x1800041d0`
- `0x1800041f0`
- `0x180007dc8`
- `0x180014af0`
- `0x1800160e0`
- `0x180016a10`
- `0x180017280`
- `0x180018870`
- `0x18001a1d0`
- `0x1800210f0`
- `0x180021a54`
- `0x1800222e8`
- `0x180023cb8`
- `0x180023ce0`
- `0x180023d9c`
- `0x18002b158`
- `0x18002b744`
- `0x180039f20`
- `0x18003ad20`
- `0x180044d98`
- `0x180044f8c`
- `0x180046010`

## import_xrefs

- `ntdll!RtlValidSid` at `0x1800023a1`
- `ntdll!RtlValidSid` at `0x1800023a1`
- `ntdll!NtClose` at `0x180002c1b`
- `ntdll!NtClose` at `0x180002c1b`
- `ntdll!RtlLengthSid` at `0x1800023b2`
- `ntdll!RtlLengthSid` at `0x1800023b2`
- `ntdll!NtAllocateLocallyUniqueId` at `0x180001e8a`
- `ntdll!NtAllocateLocallyUniqueId` at `0x180001e8a`
- `ntdll!RtlTimeFieldsToTime` at `0x180002337`
- `ntdll!RtlTimeFieldsToTime` at `0x180002337`
- `ext-ms-win-containers-policymanagercli-l1-1-1!CpmcGetTokenForGuest` at `0x180002b9c`
- `ext-ms-win-containers-policymanagercli-l1-1-1!CpmcGetTokenForGuest` at `0x180002bb8`
- `ext-ms-win-containers-policymanagercli-l1-1-1!CpmcGetTokenForGuest` at `0x180002bc3`
- `ext-ms-win-containers-policymanagercli-l1-1-1!CpmcGetTokenForGuest` at `0x180002b9c`
- `ext-ms-win-containers-policymanagercli-l1-1-1!CpmcGetTokenForGuest` at `0x180002bb8`
- `ext-ms-win-containers-policymanagercli-l1-1-1!CpmcGetTokenForGuest` at `0x180002bc3`
- `LSASRV!LsaIAddNamesToLogonSession` at `0x180001ec5`
- `LSASRV!LsaIAddNamesToLogonSession` at `0x180001ec5`

## string_xrefs

- `0x18000220d`: `onecore\ds\security\protocols\pku2u\token.cxx`
- `0x1800026ec`: `onecore\ds\security\protocols\pku2u\token.cxx`
- `0x1800027e0`: `onecore\ds\security\protocols\pku2u\token.cxx`
- `0x180002981`: `onecore\ds\security\protocols\pku2u\token.cxx`
- `0x1800029c4`: `onecore\ds\security\protocols\pku2u\token.cxx`

## pseudocode

```c
__int64 __fastcall Pku2uCreateTokenFromTicket(
        struct KERB_ENCRYPTED_TICKET *a1,
        struct KERB_AUTHENTICATOR *a2,
        int a3,
        struct KERB_ENCRYPTION_KEY *a4,
        struct KERB_ENCRYPTION_KEY *a5,
        struct _LUID *a6,
        void **a7,
        void **a8,
        struct _UNICODE_STRING *a9,
        union _LARGE_INTEGER *a10)
{
  __int64 *v12; // rsi
  __int64 **i; // rax
  __int64 v14; // r9
  void *v15; // r8
  __int64 *v16; // rcx
  struct PKERB_AUTHORIZATION_DATA *v17; // r15
  int v18; // eax
  signed int TokenForGuest; // ebx
  __int64 v20; // rdx
  int v21; // edi
  struct KERB_AUTHENTICATOR *v22; // r12
  __int64 v23; // r9
  int v24; // eax
  __int64 *v25; // rbx
  void *v26; // r8
  struct PKERB_AUTHORIZATION_DATA *v27; // rcx
  union _LARGE_INTEGER v28; // rbx
  struct _PACTYPE *v29; // r15
  __int64 *v31; // rbx
  struct PKERB_AUTHORIZATION_DATA *AuthDataEntry; // rax
  struct PKERB_AUTHORIZATION_DATA *v33; // rdi
  __int64 v34; // rcx
  struct _PACTYPE *v35; // rbx
  unsigned int v36; // r8d
  unsigned __int64 v37; // rax
  unsigned int v38; // r9d
  char *v39; // rdx
  unsigned int j; // ecx
  char *v41; // r10
  unsigned int v42; // ecx
  __int64 v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rax
  int v47; // eax
  int TokenInformationV2; // eax
  PSID Sid; // rbx
  unsigned __int64 v50; // rdi
  void *v51; // rax
  struct _NETLOGON_VALIDATION_SAM_INFO4 *v52; // rbx
  unsigned int v53; // r14d
  __int64 Length; // rax
  unsigned __int16 *v55; // rbx
  unsigned __int64 v56; // rdi
  unsigned int v57; // r15d
  _WORD *v58; // r12
  _WORD *v59; // rcx
  int v60; // eax
  unsigned int v61; // r11d
  _WORD *v62; // rax
  int v63; // eax
  int CpmTokenInformation; // eax
  int v65; // eax
  struct PKERB_AUTHORIZATION_DATA *v66; // rax
  int v67; // eax
  struct PKERB_AUTHORIZATION_DATA *v68; // rax
  void *v69; // rcx
  void *v70; // [rsp+70h] [rbp-90h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp-88h] BYREF
  int v72; // [rsp+80h] [rbp-80h] BYREF
  struct _NETLOGON_VALIDATION_SAM_INFO4 *v73; // [rsp+88h] [rbp-78h] BYREF
  LUID LocallyUniqueId; // [rsp+90h] [rbp-70h] BYREF
  void *v75; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v76; // [rsp+A0h] [rbp-60h] BYREF
  struct _LSA_TOKEN_INFORMATION_V1 *v77; // [rsp+A8h] [rbp-58h] BYREF
  struct CPM_TOKEN_INFORMATION *v78; // [rsp+B0h] [rbp-50h] BYREF
  void *v79; // [rsp+B8h] [rbp-48h] BYREF
  union _LARGE_INTEGER v80; // [rsp+C0h] [rbp-40h] BYREF
  void *v81; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v82[11]; // [rsp+D0h] [rbp-30h] BYREF
  char v83; // [rsp+128h] [rbp+28h]
  struct _NETLOGON_VALIDATION_SAM_INFO4 *v84; // [rsp+130h] [rbp+30h] BYREF
  _LARGE_INTEGER Time; // [rsp+138h] [rbp+38h] BYREF
  struct PKERB_AUTHORIZATION_DATA **v86; // [rsp+140h] [rbp+40h] BYREF
  void **v87; // [rsp+148h] [rbp+48h]
  struct KERB_ENCRYPTION_KEY *v88; // [rsp+150h] [rbp+50h]
  struct KERB_AUTHENTICATOR *v89; // [rsp+158h] [rbp+58h]
  struct KERB_ENCRYPTION_KEY *v90; // [rsp+160h] [rbp+60h]
  LUID *v91; // [rsp+168h] [rbp+68h]
  void **v92; // [rsp+170h] [rbp+70h]
  _OWORD v93[2]; // [rsp+178h] [rbp+78h] BYREF
  __int128 v94; // [rsp+198h] [rbp+98h] BYREF
  char v95[8]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v96; // [rsp+1B8h] [rbp+B8h] BYREF
  _WORD *v97; // [rsp+1C0h] [rbp+C0h]
  __int64 v98[13]; // [rsp+218h] [rbp+118h] BYREF
  _TIME_FIELDS TimeFields; // [rsp+280h] [rbp+180h] BYREF

  v90 = a4;
  v89 = a2;
  v88 = a5;
  v91 = a6;
  v87 = a7;
  v92 = a8;
  v81 = 0;
  v80.QuadPart = 0;
  v79 = 0;
  v86 = 0;
  v75 = 0;
  v73 = 0;
  v84 = 0;
  v77 = 0;
  v78 = 0;
  LocallyUniqueId = 0;
  v94 = 0;
  v72 = 0;
  Handle = 0;
  memset(v93, 0, sizeof(v93));
  memset_0(v95, 0, 0xC8u);
  LODWORD(v70) = 0;
  v76 = 0;
  v82[0] = v95;
  v82[1] = &v77;
  v82[2] = &v78;
  v82[3] = &Handle;
  v82[4] = &LocallyUniqueId;
  v82[5] = &v81;
  v82[6] = &v73;
  v82[7] = &v84;
  v82[8] = &v79;
  v82[9] = &v86;
  v82[10] = &v75;
  v83 = 1;
  *a7 = 0;
  *a6 = 0;
  if ( a10 )
    *a10 = Pku2uGlobalWillNeverTime;
  if ( !a1 )
  {
    v83 = 0;
    lambda_34f3ea1d5cd7eb78e6dff7dc8a06a7dd_::operator()(v82);
    return 3221225485LL;
  }
  if ( (unsigned int)KerbConvertPrincipalNameToString(
                       a9,
                       (unsigned int *)&v70,
                       (struct KERB_ENCRYPTED_TICKET *)((char *)a1 + 56)) )
  {
    v83 = 0;
    lambda_34f3ea1d5cd7eb78e6dff7dc8a06a7dd_::operator()(v82);
    return 3221225626LL;
  }
  if ( (*(_BYTE *)a1 & 0x10) == 0 || (v12 = (__int64 *)*((_QWORD *)a1 + 20)) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids);
    goto LABEL_221;
  }
  for ( i = (__int64 **)*((_QWORD *)a1 + 20); i; i = (__int64 **)*i )
  {
    v14 = *((unsigned int *)i + 2);
    if ( (v14 & 1) != 0 && (_DWORD)v14 != 142 )
    {
      if ( (int)v14 > 65 )
      {
        if ( (_DWORD)v14 != 128 && (_DWORD)v14 != 129 && (_DWORD)v14 != 139 && (_DWORD)v14 != 141 )
        {
LABEL_132:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids, v14);
          v83 = 0;
          lambda_34f3ea1d5cd7eb78e6dff7dc8a06a7dd_::operator()(v82);
          return 3221225581LL;
        }
      }
      else if ( (_DWORD)v14 != 65 && (_DWORD)v14 != -128 && (_DWORD)v14 != 1 && (_DWORD)v14 != 4 && (_DWORD)v14 != 64 )
      {
        goto LABEL_132;
      }
    }
  }
  v15 = 0;
  v70 = 0;
  v79 = 0;
  v16 = v12;
  while ( *((_DWORD *)v16 + 2) != 1 )
  {
    v16 = (__int64 *)*v16;
    if ( !v16 )
      goto LABEL_22;
  }
  v60 = KerbUnpackData((unsigned __int8 *)v16[3], *((_DWORD *)v16 + 4), 1u, &v70);
  v15 = v70;
  if ( v60
    || (AuthDataEntry = KerbFindAuthDataEntry(0x80u, *(struct PKERB_AUTHORIZATION_DATA **)v70),
        (v33 = AuthDataEntry) == 0) )
  {
    do
    {
LABEL_22:
      if ( *((_DWORD *)v12 + 2) == 128 )
        break;
      v12 = (__int64 *)*v12;
    }
    while ( v12 );
    v79 = v15;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids);
LABEL_221:
    v83 = 0;
    lambda_34f3ea1d5cd7eb78e6dff7dc8a06a7dd_::operator()(v82);
    return 3221225659LL;
  }
  v79 = v15;
  v70 = 0;
  v34 = *((unsigned int *)AuthDataEntry + 4);
  if ( (unsigned int)v34 < 0x18 )
    goto LABEL_89;
  v35 = (struct _PACTYPE *)*((_QWORD *)AuthDataEntry + 3);
  v36 = *(_DWORD *)v35;
  v37 = 16LL * *(unsigned int *)v35;
  if ( v37 > 0xFFFFFFFF
    || (int)v37 + 24 < (unsigned int)v37
    || (int)v37 + 24 > (unsigned int)v34
    || *((_DWORD *)v35 + 1) )
  {
    goto LABEL_89;
  }
  v38 = 0;
  v39 = (char *)v35 + v34;
  for ( j = 0; j < v36; ++j )
  {
    v41 = (char *)v35 + *((_QWORD *)v35 + 2 * j + 2);
    if ( v41 > v39 )
      goto LABEL_89;
    if ( v41 < (char *)v35 )
      goto LABEL_89;
    v61 = *((_DWORD *)v35 + 4 * j + 3);
    if ( v61 > (int)v39 - (int)v41 || v38 + v61 < v38 )
      goto LABEL_89;
    v38 += v61;
  }
  v42 = 0;
  if ( v36 )
  {
    do
      *((_QWORD *)v35 + 2 * ++v42) += v35;
    while ( v42 < *(_DWORD *)v35 );
  }
  if ( !v38 )
  {
LABEL_89:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        (unsigned int)&WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
        (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\token.cxx",
        136);
    v83 = 0;
    lambda_34f3ea1d5cd7eb78e6dff7dc8a06a7dd_::operator()(v82);
    return 3221225485LL;
  }
  Time.QuadPart = 0;
  *(_QWORD *)&TimeFields.Year = 0;
  *(_DWORD *)&TimeFields.Minute = 0x10000;
  v43 = -*((_QWORD *)a1 + 12);
  if ( !*((_QWORD *)a1 + 12) )
  {
    v44 = *((unsigned int *)a1 + 26);
    v43 = 0x10000 - v44;
    if ( v44 == 0x10000 )
      v43 = -(__int64)*((unsigned __int16 *)a1 + 54);
  }
  if ( v43 )
  {
    *(_DWORD *)&TimeFields.Year = 16844722;
    v45 = *(_QWORD *)&TimeFields.Year - *((_QWORD *)a1 + 12);
    if ( *(_QWORD *)&TimeFields.Year == *((_QWORD *)a1 + 12) )
    {
      v46 = *((unsigned int *)a1 + 26);
      v45 = 0x10000 - v46;
      if ( v46 == 0x10000 )
        v45 = -(__int64)*((unsigned __int16 *)a1 + 54);
    }
    if ( v45 )
    {
      TimeFields.Year = *((_WORD *)a1 + 48);
      TimeFields.Month = *((unsigned __int8 *)a1 + 98);
      TimeFields.Day = *((unsigned __int8 *)a1 + 99);
      TimeFields.Hour = *((unsigned __int8 *)a1 + 100);
      TimeFields.Minute = *((unsigned __int8 *)a1 + 101);
      TimeFields.Second = *((unsigned __int8 *)a1 + 102);
      TimeFields.Milliseconds = *((_WORD *)a1 + 52);
      TimeFields.Weekday = 0;
      RtlTimeFieldsToTime(&TimeFields, &Time);
    }
  }
  v47 = Pku2uVerifyPacSignature(v35, *((_DWORD *)v33 + 4), v88, &Time, a9, &v73);
  TokenForGuest = v47;
  if ( v47 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
        (unsigned int)v47);
    goto LABEL_214;
  }
  if ( !v73 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids);
    goto LABEL_221;
  }
  TokenInformationV2 = Pku2uMakeTokenInformationV2(v73, 0, 0, &v77, &v76);
  TokenForGuest = TokenInformationV2;
  if ( TokenInformationV2 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        (unsigned int)&WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
        TokenInformationV2,
        (__int64)"onecore\\ds\\security\\protocols\\pku2u\\token.cxx",
        197);
    goto LABEL_214;
  }
  Sid = v77->User.User.Sid;
  if ( !RtlValidSid(Sid) )
  {
    TokenForGuest = -1073741811;
    goto LABEL_214;
  }
  v50 = RtlLengthSid(Sid);
  v51 = basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, v50);
  v81 = v51;
  if ( !v51 )
  {
    TokenForGuest = -1073741801;
    goto LABEL_214;
  }
  memcpy_0(v51, Sid, v50);
  v52 = v73;
  if ( a10 )
  {
    a10->LowPart = *((_DWORD *)v73 + 2);
    a10->HighPart = *((_DWORD *)v52 + 3);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2));
    v52 = v73;
  }
  v53 = 2 - ((a3 & 0x20000) != 0);
  Length = a9->Length;
  if ( (_WORD)Length && a9->Buffer )
  {
    v59 = basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, Length + 2);
    v97 = v59;
    if ( !v59 )
    {
      v83 = 0;
      lambda_34f3ea1d5cd7eb78e6dff7dc8a06a7dd_::operator()(v82);
      return 3221225495LL;
    }
    LOWORD(v96) = a9->Length;
    WORD1(v96) = v96 + 2;
    memcpy_0(v59, a9->Buffer, (unsigned __int16)v96);
    v17 = 0;
    goto LABEL_30;
  }
  v55 = (unsigned __int16 *)((char *)v52 + 48);
  if ( !v55 || !*((_QWORD *)v55 + 1) )
  {
    v17 = 0;
    v97 = 0;
    LODWORD(v96) = 0;
    goto LABEL_30;
  }
  v56 = *v55;
  v57 = v56 + 2;
  if ( (unsigned int)v56 > 0xFFFC )
  {
    v97 = 0;
    TokenForGuest = -1073741562;
    goto LABEL_214;
  }
  if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
  {
    v58 = (_WORD *)(*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))(v57);
    goto LABEL_28;
  }
  v62 = (_WORD *)(**((__int64 (__fastcall ***)(_QWORD))Pku2uGlobalBaseSSP + 31))(v57);
  v58 = v62;
  if ( !v62 )
  {
LABEL_28:
    v97 = v58;
    if ( !v58 )
    {
      TokenForGuest = -1073741670;
      goto LABEL_214;
    }
    goto LABEL_29;
  }
  memset_0(v62, 0, v57);
  v97 = v58;
LABEL_29:
  LOWORD(v96) = *v55;
  WORD1(v96) = v56 + 2;
  memcpy_0(v58, *((const void **)v55 + 1), *v55);
  v17 = 0;
  v97[v56 >> 1] = 0;
LABEL_30:
  NtAllocateLocallyUniqueId(&LocallyUniqueId);
  v18 = ((__int64 (__fastcall *)(LUID *))Pku2uGlobalLsaFunctions->CreateLogonSession)(&LocallyUniqueId);
  TokenForGuest = v18;
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        (unsigned int)&WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
        v18,
        (__int64)"onecore\\ds\\security\\protocols\\pku2u\\token.cxx",
        21);
    goto LABEL_214;
  }
  v20 = 0;
  if ( v73 )
  {
    LODWORD(v93[0]) = 3;
    *((_QWORD *)&v93[0] + 1) = (char *)v73 + 64;
    v20 = 1;
  }
  LsaIAddNamesToLogonSession(&LocallyUniqueId, v20, v93);
  if ( (v76 & 1) == 0 || (v21 = 1, !(unsigned __int8)IsCpmcGetTokenForGuestPresent()) )
    v21 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_ZZZd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)&v96, (__int64)v98, v21);
  v22 = v89;
  if ( v89 )
  {
    if ( (*(_BYTE *)v89 & 0x10) != 0 )
    {
      v27 = (struct PKERB_AUTHORIZATION_DATA *)*((_QWORD *)v89 + 15);
      if ( v27 )
      {
        if ( !(unsigned int)KerbGetPacFromAuthData(v27, &v86, (struct PKERB_AUTHORIZATION_DATA **)&v80) )
        {
          v28 = v80;
          if ( v80.QuadPart )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids);
            v29 = *(struct _PACTYPE **)(v28.QuadPart + 24);
            if ( !(unsigned int)PAC_UnMarshal((unsigned __int64)v29, *(_DWORD *)(v28.QuadPart + 16)) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids);
              MicrosoftTelemetryAssertTriggeredNoArgs();
              v83 = 0;
              lambda_34f3ea1d5cd7eb78e6dff7dc8a06a7dd_::operator()(v82);
              return 3221225485LL;
            }
            v80.QuadPart = 0;
            KerbConvertGeneralizedTimeToLargeInt(
              &v80,
              (struct KERB_AUTHENTICATOR *)((char *)v22 + 60),
              *((_DWORD *)v22 + 14));
            v63 = Pku2uVerifyPacSignature(
                    v29,
                    *(_DWORD *)(v28.QuadPart + 16),
                    v90,
                    &v80,
                    &Pku2uGlobalContainerUserName,
                    &v84);
            TokenForGuest = v63;
            if ( v63 < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  48,
                  &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
                  (unsigned int)v63);
              goto LABEL_214;
            }
            CpmTokenInformation = Pku2uMakeCpmTokenInformation(v29, v84, &v78);
            TokenForGuest = CpmTokenInformation;
            if ( CpmTokenInformation < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  49,
                  &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
                  (unsigned int)CpmTokenInformation);
              goto LABEL_214;
            }
            v17 = 0;
          }
        }
      }
    }
  }
  v23 = v53;
  if ( v21 )
    v23 = 2;
  v24 = ((__int64 (__fastcall *)(LUID *, struct _TOKEN_SOURCE *, __int64, __int64, int, struct _LSA_TOKEN_INFORMATION_V1 *, _QWORD, __int128 *, char *, char *, _DWORD, HANDLE *, int *))Pku2uGlobalLsaFunctions->CreateTokenEx)(
          &LocallyUniqueId,
          &Pku2uGlobalSource,
          3,
          v23,
          2,
          v77,
          0,
          &v94,
          (char *)v73 + 96,
          v95,
          0,
          &Handle,
          &v72);
  TokenForGuest = v24;
  v77 = 0;
  if ( v24 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        (unsigned int)&WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
        v24,
        (__int64)"onecore\\ds\\security\\protocols\\pku2u\\token.cxx",
        137);
    goto LABEL_214;
  }
  TokenForGuest = v72;
  if ( v72 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        51,
        (unsigned int)&WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
        v72,
        (__int64)"onecore\\ds\\security\\protocols\\pku2u\\token.cxx",
        143);
      TokenForGuest = v72;
    }
    goto LABEL_214;
  }
  if ( (*(_BYTE *)a1 & 0x10) == 0 )
    goto LABEL_66;
  v25 = (__int64 *)*((_QWORD *)a1 + 20);
  if ( !v25 )
    goto LABEL_66;
  v26 = 0;
  v70 = 0;
  v75 = 0;
  while ( 1 )
  {
    if ( !v25 )
      goto LABEL_48;
    if ( *((_DWORD *)v25 + 2) != 1 )
      goto LABEL_47;
    if ( v26 )
    {
      KerbFreeData(1u, v26);
      v70 = 0;
    }
    v65 = KerbUnpackData((unsigned __int8 *)v25[3], *((_DWORD *)v25 + 4), 1u, &v70);
    if ( v65 )
      break;
    v66 = KerbFindAuthDataEntry(0x8Du, *(struct PKERB_AUTHORIZATION_DATA **)v70);
    if ( v66 )
    {
      v75 = v26;
      v26 = 0;
      v70 = 0;
      v17 = v66;
LABEL_48:
      TokenForGuest = 0;
      goto LABEL_49;
    }
LABEL_47:
    v25 = (__int64 *)*v25;
  }
  TokenForGuest = KerbMapKerbError(v65);
  v26 = v70;
LABEL_49:
  if ( v26 )
    KerbFreeData(1u, v26);
  if ( TokenForGuest < 0 )
    goto LABEL_214;
  if ( v17 )
    goto LABEL_202;
LABEL_66:
  if ( v75 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !v22 )
    goto LABEL_203;
  if ( (*(_BYTE *)v22 & 0x10) == 0 )
    goto LABEL_203;
  v31 = (__int64 *)*((_QWORD *)v22 + 15);
  if ( !v31 )
    goto LABEL_203;
  v26 = 0;
  v70 = 0;
  v75 = 0;
  while ( 2 )
  {
    if ( !v31 )
      goto LABEL_75;
    if ( *((_DWORD *)v31 + 2) != 1 )
    {
LABEL_74:
      v31 = (__int64 *)*v31;
      continue;
    }
    break;
  }
  if ( v26 )
  {
    KerbFreeData(1u, v26);
    v70 = 0;
  }
  v67 = KerbUnpackData((unsigned __int8 *)v31[3], *((_DWORD *)v31 + 4), 1u, &v70);
  if ( !v67 )
  {
    v68 = KerbFindAuthDataEntry(0x8Du, *(struct PKERB_AUTHORIZATION_DATA **)v70);
    if ( v68 )
    {
      v75 = v26;
      v26 = 0;
      v70 = 0;
      v17 = v68;
LABEL_75:
      TokenForGuest = 0;
      goto LABEL_76;
    }
    goto LABEL_74;
  }
  TokenForGuest = KerbMapKerbError(v67);
  v26 = v70;
LABEL_76:
  if ( v26 )
    KerbFreeData(1u, v26);
  if ( TokenForGuest < 0 )
  {
LABEL_214:
    v83 = 0;
    lambda_34f3ea1d5cd7eb78e6dff7dc8a06a7dd_::operator()(v82);
    return (unsigned int)TokenForGuest;
  }
  if ( v17 )
  {
LABEL_202:
    TokenForGuest = KerbApplyAuthDataRestrictions(&Handle, v17, (int *)v26);
    if ( TokenForGuest < 0 )
      goto LABEL_214;
  }
LABEL_203:
  if ( v21 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids);
    v70 = 0;
    if ( (unsigned __int16)CpmcGetTokenForGuest(v78, Handle, v53, &v70) )
      TokenForGuest = (unsigned __int16)CpmcGetTokenForGuest(v78, Handle, v53, &v70) | 0xC0070000;
    else
      TokenForGuest = (unsigned __int16)CpmcGetTokenForGuest(v78, Handle, v53, &v70);
    if ( TokenForGuest < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          53,
          &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
          (unsigned int)TokenForGuest);
      goto LABEL_214;
    }
    NtClose(Handle);
    v69 = v70;
  }
  else
  {
    v69 = Handle;
  }
  *v91 = LocallyUniqueId;
  LocallyUniqueId = 0;
  *v92 = v69;
  Handle = 0;
  *v87 = v81;
  v81 = 0;
  v83 = 0;
  lambda_34f3ea1d5cd7eb78e6dff7dc8a06a7dd_::operator()(v82);
  return 0;
}

```

## disassembly

```asm
0x180001bf0  mov     [rsp-8+arg_10], rbx
0x180001bf5  push    rbp
0x180001bf6  push    rsi
0x180001bf7  push    rdi
0x180001bf8  push    r12
0x180001bfa  push    r13
0x180001bfc  push    r14
0x180001bfe  push    r15
0x180001c00  lea     rbp, [rsp-1A0h]
0x180001c08  sub     rsp, 2A0h
0x180001c0f  mov     rax, cs:__security_cookie
0x180001c16  xor     rax, rsp
0x180001c19  mov     [rbp+1D0h+var_40], rax
0x180001c20  mov     [rbp+1D0h+var_170], r9
0x180001c24  mov     r14d, r8d
0x180001c27  mov     [rbp+1D0h+var_178], rdx
0x180001c2b  mov     r13, rcx
0x180001c2e  mov     r12, [rbp+1D0h+arg_40]
0x180001c35  mov     r15, [rbp+1D0h+arg_48]
0x180001c3c  mov     rax, [rbp+1D0h+arg_20]
0x180001c43  mov     [rbp+1D0h+var_180], rax
0x180001c47  mov     rbx, [rbp+1D0h+arg_28]
0x180001c4e  mov     [rbp+1D0h+var_168], rbx
0x180001c52  mov     rdi, [rbp+1D0h+arg_30]
0x180001c59  mov     [rbp+1D0h+var_188], rdi
0x180001c5d  mov     rax, [rbp+1D0h+arg_38]
0x180001c64  mov     [rbp+1D0h+var_160], rax
0x180001c68  xor     esi, esi
0x180001c6a  mov     [rbp+1D0h+var_208], rsi
0x180001c6e  mov     qword ptr [rbp+1D0h+var_210], rsi
0x180001c72  mov     [rbp+1D0h+var_218], rsi
0x180001c76  mov     [rbp+1D0h+var_190], rsi
0x180001c7a  mov     [rbp+1D0h+var_238], rsi
0x180001c7e  mov     [rbp+1D0h+var_248], rsi
0x180001c82  mov     [rbp+1D0h+var_1A0], rsi
0x180001c86  mov     [rbp+1D0h+var_228], rsi
0x180001c8a  mov     [rbp+1D0h+var_220], rsi
0x180001c8e  mov     qword ptr [rbp+1D0h+LocallyUniqueId.LowPart], rsi
0x180001c92  xorps   xmm0, xmm0
0x180001c95  movups  [rbp+1D0h+var_138], xmm0
0x180001c9c  mov     [rbp+1D0h+var_250], esi
0x180001c9f  mov     [rsp+2D0h+Handle], rsi
0x180001ca4  movups  [rbp+1D0h+var_158], xmm0
0x180001ca8  movups  [rbp+1D0h+var_148], xmm0
0x180001caf  xor     edx, edx; Val
0x180001cb1  mov     r8d, 0C8h; Size
0x180001cb7  lea     rcx, [rbp+1D0h+var_120]; void *
0x180001cbe  call    memset_0
0x180001cc3  mov     dword ptr [rsp+2D0h+var_260], esi
0x180001cc7  mov     [rbp+1D0h+var_230], esi
0x180001cca  lea     rax, [rbp+1D0h+var_120]
0x180001cd1  mov     [rbp+1D0h+var_200], rax
0x180001cd5  lea     rax, [rbp+1D0h+var_228]
0x180001cd9  mov     [rbp+1D0h+var_1F8], rax
0x180001cdd  lea     rax, [rbp+1D0h+var_220]
0x180001ce1  mov     [rbp+1D0h+var_1F0], rax
0x180001ce5  lea     rax, [rsp+2D0h+Handle]
0x180001cea  mov     [rbp+1D0h+var_1E8], rax
0x180001cee  lea     rax, [rbp+1D0h+LocallyUniqueId]
0x180001cf2  mov     [rbp+1D0h+var_1E0], rax
0x180001cf6  lea     rax, [rbp+1D0h+var_208]
0x180001cfa  mov     [rbp+1D0h+var_1D8], rax
0x180001cfe  lea     rax, [rbp+1D0h+var_248]
0x180001d02  mov     [rbp+1D0h+var_1D0], rax
0x180001d06  lea     rax, [rbp+1D0h+var_1A0]
0x180001d0a  mov     [rbp+1D0h+var_1C8], rax
0x180001d0e  lea     rax, [rbp+1D0h+var_218]
0x180001d12  mov     [rbp+1D0h+var_1C0], rax
0x180001d16  lea     rax, [rbp+1D0h+var_190]
0x180001d1a  mov     [rbp+1D0h+var_1B8], rax
0x180001d1e  lea     rax, [rbp+1D0h+var_238]
0x180001d22  mov     [rbp+1D0h+var_1B0], rax
0x180001d26  mov     [rbp+1D0h+var_1A8], 1
0x180001d2a  mov     [rdi], rsi
0x180001d2d  mov     [rbx], rsi
0x180001d30  test    r15, r15
0x180001d33  jnz     loc_18000252B
0x180001d39  test    r13, r13
0x180001d3c  jz      loc_18000253A
0x180001d42  lea     r8, [r13+38h]; struct KERB_PRINCIPAL_NAME *
0x180001d46  lea     rdx, [rsp+2D0h+var_260]; unsigned int *
0x180001d4b  mov     rcx, r12; struct _UNICODE_STRING *
0x180001d4e  call    ?KerbConvertPrincipalNameToString@@YAJPEAU_UNICODE_STRING@@PEAKPEAUKERB_PRINCIPAL_NAME@@@Z; KerbConvertPrincipalNameToString(_UNICODE_STRING *,ulong *,KERB_PRINCIPAL_NAME *)
0x180001d53  test    eax, eax
0x180001d55  jnz     loc_180002552
0x180001d5b  test    byte ptr [r13+0], 10h
0x180001d60  jz      loc_180002C6C
0x180001d66  mov     rsi, [r13+0A0h]
0x180001d6d  test    rsi, rsi
0x180001d70  jz      loc_180002C6C
0x180001d76  mov     rax, rsi
0x180001d79  nop     dword ptr [rax+00000000h]
0x180001d80  test    rax, rax
0x180001d83  jz      short loc_180001DC7
0x180001d85  mov     r9d, [rax+8]
0x180001d89  test    r9b, 1
0x180001d8d  jnz     short loc_180001D94
0x180001d8f  mov     rax, [rax]
0x180001d92  jmp     short loc_180001D80
0x180001d94  cmp     r9d, 8Eh
0x180001d9b  jz      short loc_180001D8F
0x180001d9d  cmp     r9d, 41h ; 'A'
0x180001da1  jg      loc_18000256A
0x180001da7  jz      short loc_180001D8F
0x180001da9  cmp     r9d, 0FFFFFF80h
0x180001dad  jz      short loc_180001D8F
0x180001daf  cmp     r9d, 1
0x180001db3  jz      short loc_180001D8F
0x180001db5  cmp     r9d, 4
0x180001db9  jz      short loc_180001D8F
0x180001dbb  cmp     r9d, 40h ; '@'
0x180001dbf  jnz     loc_180002594
0x180001dc5  jmp     short loc_180001D8F
0x180001dc7  xor     r8d, r8d
0x180001dca  mov     [rsp+2D0h+var_260], r8
0x180001dcf  mov     [rbp+1D0h+var_218], r8
0x180001dd3  mov     rcx, rsi
0x180001dd6  cmp     dword ptr [rcx+8], 1
0x180001dda  jz      loc_1800025DB
0x180001de0  mov     rcx, [rcx]
0x180001de3  test    rcx, rcx
0x180001de6  jnz     short loc_180001DD6
0x180001de8  cmp     dword ptr [rsi+8], 80h
0x180001def  jz      short loc_180001DF9
0x180001df1  mov     rsi, [rsi]
0x180001df4  test    rsi, rsi
0x180001df7  jnz     short loc_180001DE8
0x180001df9  mov     [rbp+1D0h+var_218], r8
0x180001dfd  lea     rsi, WPP_GLOBAL_Control
0x180001e04  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e0b  cmp     rcx, rsi
0x180001e0e  jz      short loc_180001E2C
0x180001e10  test    byte ptr [rcx+1Ch], 1
0x180001e14  jz      short loc_180001E2C
0x180001e16  mov     edx, 27h ; '''
0x180001e1b  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids
0x180001e22  mov     rcx, [rcx+10h]
0x180001e26  call    WPP_SF_
0x180001e2b  nop
0x180001e2c  mov     [rbp+1D0h+var_1A8], 0
0x180001e30  lea     rcx, [rbp+1D0h+var_200]
0x180001e34  call    _lambda_34f3ea1d5cd7eb78e6dff7dc8a06a7dd___operator__
0x180001e39  nop
0x180001e3a  jmp     loc_180002CA9
0x180001e3f  mov     [rbp+1D0h+var_110], r12
0x180001e46  test    r12, r12
0x180001e49  jz      loc_1800027B7
0x180001e4f  movzx   eax, word ptr [rbx]
0x180001e52  mov     word ptr [rbp+1D0h+var_118], ax
0x180001e59  mov     word ptr [rbp+1D0h+var_118+2], r15w
0x180001e61  movzx   r8d, word ptr [rbx]; Size
0x180001e65  mov     rdx, [rbx+8]; Src
0x180001e69  mov     rcx, r12; void *
0x180001e6c  call    memcpy_0
0x180001e71  mov     rdx, rdi
0x180001e74  shr     rdx, 1
0x180001e77  xor     r15d, r15d
0x180001e7a  mov     rax, [rbp+1D0h+var_110]
0x180001e81  mov     [rax+rdx*2], r15w
0x180001e86  lea     rcx, [rbp+1D0h+LocallyUniqueId]; LocallyUniqueId
0x180001e8a  call    cs:__imp_NtAllocateLocallyUniqueId
0x180001e90  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x180001e97  lea     rcx, [rbp+1D0h+LocallyUniqueId]
0x180001e9b  mov     rax, [rax]
0x180001e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ea3  mov     ebx, eax
0x180001ea5  test    eax, eax
0x180001ea7  js      loc_1800027C1
0x180001ead  mov     edx, r15d
0x180001eb0  mov     rax, [rbp+1D0h+var_248]
0x180001eb4  test    rax, rax
0x180001eb7  jnz     loc_180002815
0x180001ebd  lea     r8, [rbp+1D0h+var_158]
0x180001ec1  lea     rcx, [rbp+1D0h+LocallyUniqueId]
0x180001ec5  call    cs:__imp_LsaIAddNamesToLogonSession
0x180001ecb  test    byte ptr [rbp+1D0h+var_230], 1
0x180001ecf  jnz     loc_180002831
0x180001ed5  mov     edi, r15d
0x180001ed8  mov     rcx, cs:WPP_GLOBAL_Control
0x180001edf  cmp     rcx, rsi
0x180001ee2  jnz     loc_180002848
0x180001ee8  mov     r12, [rbp+1D0h+var_178]
0x180001eec  test    r12, r12
0x180001eef  jz      short loc_180001EFC
0x180001ef1  test    byte ptr [r12], 10h
0x180001ef6  jnz     loc_180002043
0x180001efc  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x180001f03  mov     r10, [rax+190h]
0x180001f0a  mov     rax, [rbp+1D0h+var_248]
0x180001f0e  add     rax, 60h ; '`'
0x180001f12  mov     r9d, r14d
0x180001f15  mov     edx, 2
0x180001f1a  test    edi, edi
0x180001f1c  cmovnz  r9d, edx
0x180001f20  lea     rcx, [rbp+1D0h+var_250]
0x180001f24  mov     [rsp+2D0h+var_270], rcx
0x180001f29  lea     rcx, [rsp+2D0h+Handle]
0x180001f2e  mov     [rsp+2D0h+var_278], rcx
0x180001f33  mov     [rsp+2D0h+var_280], r15d
0x180001f38  lea     rcx, [rbp+1D0h+var_120]
0x180001f3f  mov     [rsp+2D0h+var_288], rcx
0x180001f44  mov     [rsp+2D0h+var_290], rax
0x180001f49  lea     rax, [rbp+1D0h+var_138]
0x180001f50  mov     [rsp+2D0h+var_298], rax
0x180001f55  mov     qword ptr [rsp+2D0h+var_2A0], r15
0x180001f5a  mov     rcx, [rbp+1D0h+var_228]
0x180001f5e  mov     [rsp+2D0h+var_2A8], rcx
0x180001f63  mov     dword ptr [rsp+2D0h+var_2B0], edx
0x180001f67  mov     r8d, 3
0x180001f6d  lea     rdx, ?Pku2uGlobalSource@@3U_TOKEN_SOURCE@@A; _TOKEN_SOURCE Pku2uGlobalSource
0x180001f74  lea     rcx, [rbp+1D0h+LocallyUniqueId]
0x180001f78  mov     rax, r10
0x180001f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f80  mov     ebx, eax
0x180001f82  mov     [rbp+1D0h+var_228], r15
0x180001f86  test    eax, eax
0x180001f88  js      loc_180002021
0x180001f8e  mov     ebx, [rbp+1D0h+var_250]
0x180001f91  test    ebx, ebx
0x180001f93  js      loc_1800029A5
0x180001f99  test    byte ptr [r13+0], 10h
0x180001f9e  jz      loc_1800020F6
0x180001fa4  mov     rbx, [r13+0A0h]
0x180001fab  test    rbx, rbx
0x180001fae  jz      loc_1800020F6
0x180001fb4  mov     r8, r15
0x180001fb7  mov     [rsp+2D0h+var_260], r15
0x180001fbc  mov     [rbp+1D0h+var_238], r15
0x180001fc0  test    rbx, rbx
0x180001fc3  jz      short loc_180001FD4
0x180001fc5  cmp     dword ptr [rbx+8], 1
0x180001fc9  jz      loc_1800029FB
0x180001fcf  mov     rbx, [rbx]
0x180001fd2  jmp     short loc_180001FC0
0x180001fd4  xor     ebx, ebx
0x180001fd6  test    r8, r8
0x180001fd9  jnz     loc_180002A73
0x180001fdf  test    ebx, ebx
0x180001fe1  jns     loc_180002A85
0x180001fe7  mov     [rbp+1D0h+var_1A8], 0
0x180001feb  lea     rcx, [rbp+1D0h+var_200]
0x180001fef  call    _lambda_34f3ea1d5cd7eb78e6dff7dc8a06a7dd___operator__
0x180001ff4  nop
0x180001ff5  mov     eax, ebx
0x180001ff7  mov     rcx, [rbp+1D0h+var_40]
0x180001ffe  xor     rcx, rsp; StackCookie
0x180002001  call    __security_check_cookie
0x180002006  mov     rbx, [rsp+2D0h+arg_10]
0x18000200e  add     rsp, 2A0h
0x180002015  pop     r15
0x180002017  pop     r14
0x180002019  pop     r13
0x18000201b  pop     r12
0x18000201d  pop     rdi
0x18000201e  pop     rsi
0x18000201f  pop     rbp
0x180002020  retn
0x180002021  mov     rcx, cs:WPP_GLOBAL_Control
0x180002028  cmp     rcx, rsi
0x18000202b  jnz     loc_18000296A
0x180002031  mov     [rbp+1D0h+var_1A8], 0
0x180002035  lea     rcx, [rbp+1D0h+var_200]
0x180002039  call    _lambda_34f3ea1d5cd7eb78e6dff7dc8a06a7dd___operator__
0x18000203e  nop
0x18000203f  mov     eax, ebx
0x180002041  jmp     short loc_180001FF7
0x180002043  mov     rcx, [r12+78h]; struct PKERB_AUTHORIZATION_DATA *
0x180002048  test    rcx, rcx
0x18000204b  jz      loc_180001EFC
0x180002051  lea     r8, [rbp+1D0h+var_210]; struct PKERB_AUTHORIZATION_DATA **
0x180002055  lea     rdx, [rbp+1D0h+var_190]; struct PKERB_AUTHORIZATION_DATA ***
0x180002059  call    ?KerbGetPacFromAuthData@@YAJPEAUPKERB_AUTHORIZATION_DATA@@PEAPEAPEAU1@PEAPEAU1@@Z; KerbGetPacFromAuthData(PKERB_AUTHORIZATION_DATA *,PKERB_AUTHORIZATION_DATA * * *,PKERB_AUTHORIZATION_DATA * *)
0x18000205e  test    eax, eax
0x180002060  jnz     loc_180001EFC
0x180002066  mov     rbx, qword ptr [rbp+1D0h+var_210]
0x18000206a  test    rbx, rbx
0x18000206d  jz      loc_180001EFC
0x180002073  mov     rcx, cs:WPP_GLOBAL_Control
0x18000207a  cmp     rcx, rsi
0x18000207d  jz      short loc_18000209A
0x18000207f  test    byte ptr [rcx+1Ch], 4
0x180002083  jz      short loc_18000209A
0x180002085  mov     edx, 2Eh ; '.'
0x18000208a  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids
0x180002091  mov     rcx, [rcx+10h]
0x180002095  call    WPP_SF_
0x18000209a  mov     r15, [rbx+18h]
0x18000209e  mov     edx, [rbx+10h]; unsigned int
0x1800020a1  mov     rcx, r15; struct _PACTYPE *
0x1800020a4  call    ?PAC_UnMarshal@@YAKPEAU_PACTYPE@@K@Z; PAC_UnMarshal(_PACTYPE *,ulong)
0x1800020a9  test    eax, eax
0x1800020ab  jnz     loc_180002883
0x1800020b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800020b8  cmp     rcx, rsi
0x1800020bb  jz      short loc_1800020D8
0x1800020bd  test    byte ptr [rcx+1Ch], 1
0x1800020c1  jz      short loc_1800020D8
0x1800020c3  mov     edx, 2Fh ; '/'
0x1800020c8  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids
0x1800020cf  mov     rcx, [rcx+10h]
  ... truncated ...
```
