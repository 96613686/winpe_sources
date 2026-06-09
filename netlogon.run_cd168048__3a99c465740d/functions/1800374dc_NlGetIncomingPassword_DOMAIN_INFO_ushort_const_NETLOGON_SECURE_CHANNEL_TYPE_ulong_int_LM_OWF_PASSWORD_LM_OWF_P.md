# NlGetIncomingPassword(_DOMAIN_INFO *,ushort const *,_NETLOGON_SECURE_CHANNEL_TYPE,ulong,int,_LM_OWF_PASSWORD *,_LM_OWF_PASSWORD *,ulong *,ulong *,ulong *,void * *,int *,ulong *)

- ea: `0x1800374dc`
- end: `0x180037fed`
- name: `?NlGetIncomingPassword@@YAJPEAU_DOMAIN_INFO@@PEBGW4_NETLOGON_SECURE_CHANNEL_TYPE@@KHPEAU_LM_OWF_PASSWORD@@3PEAK44PEAPEAXPEAH4@Z`
- size: `2833`
- prototype: ``
- caller_count: `8`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005a13c`
- `0x18005a400`
- `0x180061b40`
- `0x180062590`
- `0x180062b20`
- `0x180062f50`
- `0x180063610`
- `0x180072cb4`

## callees

- `0x180007518`
- `0x18000c440`
- `0x18000dd00`
- `0x18000e910`
- `0x18000ed00`
- `0x18000f3e4`
- `0x1800374dc`
- `0x180038acc`
- `0x180038e20`
- `0x180041944`
- `0x180041b98`
- `0x180041d50`
- `0x180041e68`
- `0x18005448c`
- `0x1800892fc`
- `0x180090204`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180037692`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180037a44`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180037692`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180037a44`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037b8a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037b8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037bde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037bde`
- `LSASRV!LsarQueryTrustedDomainInfoByName` at `0x180037a79`
- `LSASRV!LsarQueryTrustedDomainInfoByName` at `0x180037a79`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180037fb4`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180037fb4`
- `ntdll!RtlInitUnicodeString` at `0x18003798e`
- `ntdll!RtlInitUnicodeString` at `0x180037a0c`
- `ntdll!RtlInitUnicodeString` at `0x18003798e`
- `ntdll!RtlInitUnicodeString` at `0x180037a0c`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x180037769`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x180037940`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x180037769`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x180037940`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x180037f82`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x180037f82`
- `SAMSRV!SamrCloseHandle` at `0x180037f99`
- `SAMSRV!SamrCloseHandle` at `0x180037f99`
- `CRYPTSP!SystemFunction007` at `0x1800379a2`
- `CRYPTSP!SystemFunction007` at `0x180037cdf`
- `CRYPTSP!SystemFunction007` at `0x180037e4b`
- `CRYPTSP!SystemFunction007` at `0x1800379a2`
- `CRYPTSP!SystemFunction007` at `0x180037cdf`
- `CRYPTSP!SystemFunction007` at `0x180037e4b`

## string_xrefs

- `0x180037641`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x180037d22`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x1800377c4`: `NlGetIncomingPassword: Invalid AAC (%x) for %ws\n`
- `0x180037616`: `NlGetIncomingPassword: Invalid channel type (%x) for %ws\n`
- `0x180037a94`: `NlGetIncomingPassword: %wZ: cannot LsarQueryTrustedDomainInfoByName 0x%lx\n`
- `0x180037acc`: `NlGetIncomingPassword: %wZ: trust is not inbound\n`
- `0x180037b09`: `NlGetIncomingPassword: %wZ: trust type doesn't match request type 0x%lx %ld\n`
- `0x180037b2d`: `NlGetIncomingPassword: %wZ: trust is KERB only\n`
- `0x180037db4`: `NlGetIncomingPassword: %wZ: No auth info for this domain.\n`
- `0x180037c46`: `NlGetIncomingPassword: %wZ: OWF password has bad length %ld\n`
- `0x180037c85`: `NlGetIncomingPassword: New Clear Password = `
- `0x180037ccb`: `NlGetIncomingPassword: New Password Changed: `
- `0x180037cf6`: `NlGetIncomingPassword: %wZ: cannot RtlCalculateNtOwfPassword 0x%lx\n`
- `0x180037e78`: `NlGetIncomingPassword: %wZ: No previous auth info for this domain.\n`
- `0x180037d9e`: `NlGetIncomingPassword: %wZ: previous OWF password has bad length %ld\n`
- `0x180037dec`: `NlGetIncomingPassword: Old Clear Password = `
- `0x180037e32`: `NlGetIncomingPassword: Old Password Changed: `
- `0x180037f32`: `NlGetIncomingPassword: %wZ: Flat Name length is bad %ld\n`
- `0x18003777a`: `NlGetIncomingPassword: Can't NlSamOpenNamedUser for %ws 0x%lx.\n`
- `0x180037f0b`: `NlGetIncomingPassword: Can't NlSamOpenNamedUser for %ws 0x%lx.\n`
- `0x18003780c`: `NlGetIncomingPassword: Invalid account type (%x) instead of %x for %ws\n`
- `0x180037837`: `NlGetIncomingPassword: %ws account is disabled\n`
- `0x180037871`: `NlGetIncomingPassword: branch id requested but account '%ws' is not an RODC account Status:0x%x`
- `0x1800378a9`: `NlGetIncomingPassword: NlQuerySecondaryKrbTgtNum failed AccountName:%ws Status:0x%x`
- `0x1800378ba`: `UserAllInfo->KrbTgtLinkObjectGuid: `
- `0x1800379d7`: `NlGetIncomingPassword: No NT Password for %ws\n`
- `0x180037953`: `NlGetIncomingPassword: Cannot set last logon time %ws %lx\n`
- `0x1800379bc`: `NlGetIncomingPassword: %ws: cannot RtlCalculateNtOwfPassword (NULL) 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NlGetIncomingPassword(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        int a4,
        int a5,
        _OWORD *a6,
        char *a7,
        unsigned int *a8,
        _DWORD *a9,
        _DWORD *a10,
        _QWORD *a11,
        _DWORD *a12,
        unsigned int *a13)
{
  int v14; // esi
  __int64 v16; // rbx
  unsigned int *v18; // r13
  int v19; // ebx
  __int64 v20; // r9
  unsigned __int16 *v21; // r8
  struct _USER_INTERNAL6_INFORMATION *v22; // rdx
  int v23; // ecx
  UUID *v24; // rsi
  int SecondaryKrbTgtNum; // eax
  _OWORD *v26; // r13
  _OWORD *v27; // rax
  int v28; // eax
  char *v29; // r15
  int v30; // eax
  int v31; // eax
  unsigned __int16 *v32; // rdx
  int v33; // ecx
  _QWORD *v34; // rbx
  _DWORD *v35; // rsi
  unsigned __int16 *v36; // rax
  unsigned __int16 *v37; // rbx
  unsigned int v38; // r12d
  __int64 v39; // rbx
  unsigned int i; // esi
  _OWORD *v41; // rax
  void *v42; // rax
  unsigned int v43; // ecx
  int v44; // eax
  struct _UNICODE_STRING *p_DestinationString; // r9
  unsigned __int16 *v46; // r8
  char *v47; // rcx
  unsigned int v48; // r13d
  __int64 v49; // rbx
  unsigned int j; // esi
  _OWORD *v51; // rax
  void *v52; // rax
  unsigned int v53; // ecx
  unsigned int *v54; // rsi
  unsigned __int16 *v55; // rbx
  unsigned __int64 v56; // rcx
  void **v57; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v58; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  int v60; // [rsp+58h] [rbp-A8h]
  char *v61; // [rsp+60h] [rbp-A0h]
  int v62; // [rsp+68h] [rbp-98h]
  void *v63[2]; // [rsp+70h] [rbp-90h] BYREF
  void *v64; // [rsp+80h] [rbp-80h] BYREF
  struct _USER_INTERNAL6_INFORMATION *v65; // [rsp+88h] [rbp-78h] BYREF
  _OWORD *v66; // [rsp+90h] [rbp-70h]
  unsigned int *v67; // [rsp+98h] [rbp-68h]
  _QWORD *v68; // [rsp+A0h] [rbp-60h]
  int v69; // [rsp+B0h] [rbp-50h] BYREF
  char v70[188]; // [rsp+B4h] [rbp-4Ch] BYREF
  unsigned __int16 v71[20]; // [rsp+170h] [rbp+70h] BYREF

  v14 = a4;
  v66 = a6;
  v68 = a11;
  v61 = a7;
  v67 = a8;
  v63[0] = a12;
  v64 = 0;
  v65 = 0;
  v58 = 0;
  if ( a8 )
    *a8 = 0;
  if ( a9 )
    *a9 = 0;
  if ( a10 )
    *a10 = 0;
  if ( a11 )
    *a11 = 0;
  if ( a12 )
    *a12 = 0;
  if ( a13 )
  {
    if ( NlGlobalCDC || a3 != 7 )
      return 3221225485LL;
    *a13 = 0;
  }
  v16 = -1;
  do
    ++v16;
  while ( a2[v16] );
  if ( !(_DWORD)v16 )
    return 3221225485LL;
  if ( a3 )
  {
    switch ( a3 )
    {
      case 2u:
        v14 = a4 | 0x80;
        break;
      case 3u:
        v14 = a4 | 0x400;
        break;
      case 4u:
        v14 = a4 | 0x40;
        break;
      case 6u:
        v14 = a4 | 0x100;
        break;
      case 7u:
        v14 = a4 | 0x100000;
        break;
      default:
        NlPrintDomRoutine(
          0x100u,
          (struct _DOMAIN_INFO *)a1,
          L"NlGetIncomingPassword: Invalid channel type (%x) for %ws\n",
          a3,
          a2);
        return 3221225485LL;
    }
  }
  else if ( !a4 )
  {
    NlPrintDomRoutine(0x100u, (struct _DOMAIN_INFO *)a1, L"NlGetIncomingPassword: Invalid AAC (%x) for %ws\n", 0, a2);
    return 3221225485LL;
  }
  v60 = 0;
  v62 = 0;
  if ( v14 != 1024 && v14 != 64 )
  {
    if ( a7 )
      NlAssertFailed(
        "OwfPreviousPassword == NULL",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
        0x5D6u,
        a7);
    if ( v14 != 256 && v14 != 128 && v14 != 0x100000
      || (unsigned int)v16 > 1 && !(unsigned int)_o__wcsicmp(&a2[(unsigned int)(v16 - 1)], L"$") )
    {
      v18 = v67;
      v19 = NlSamOpenNamedUser((struct _DOMAIN_INFO *)a1, a2, 0x23100000u, a13 != 0 ? 0x8000000 : 0, &v64, v67, &v65);
      if ( v19 < 0 )
      {
        if ( NlGlobalCDC && v19 == -1073740943 )
        {
          if ( a13 )
            NlAssertFailed(
              "!CdcBranchId",
              "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
              0x602u,
              (char *)v20);
          memset_0(&v69, 0, 0xC0u);
          if ( (int)NlSamOpenNamedUser((struct _DOMAIN_INFO *)a1, a2, 4u, 0, &v64, v18, &v65) >= 0 )
          {
            v69 = 8912896;
            SamIUpdateLogonStatistics(v64, &v69);
          }
          v19 = -1073741429;
        }
        v21 = L"NlGetIncomingPassword: Can't NlSamOpenNamedUser for %ws 0x%lx.\n";
        goto LABEL_45;
      }
      v22 = v65;
      v23 = *((_DWORD *)v65 + 70);
      if ( (v23 & v14 & 0x1001D8) == 0 )
      {
        LODWORD(v57) = v14;
        NlPrintDomRoutine(
          0x100u,
          (struct _DOMAIN_INFO *)a1,
          L"NlGetIncomingPassword: Invalid account type (%x) instead of %x for %ws\n",
          v23 & 0x1001D8,
          v57,
          a2);
LABEL_56:
        v19 = -1073741724;
        goto LABEL_158;
      }
      v19 = 0;
      if ( a5 && (v23 & 1) != 0 )
      {
        NlPrintDomRoutine(0x100u, (struct _DOMAIN_INFO *)a1, L"NlGetIncomingPassword: %ws account is disabled\n", a2);
        goto LABEL_56;
      }
      if ( a13 )
      {
        if ( (v23 & 0x100000) == 0 )
        {
          NlAssertFailed("FALSE", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx", 0x65Du, (char *)v20);
          v21 = L"NlGetIncomingPassword: branch id requested but account '%ws' is not an RODC account Status:0x%x";
          v19 = -1073741811;
LABEL_45:
          LODWORD(v57) = v19;
          NlPrintDomRoutine(0x100u, (struct _DOMAIN_INFO *)a1, v21, a2, v57);
          goto LABEL_158;
        }
        v24 = (UUID *)((char *)v65 + 628);
        SecondaryKrbTgtNum = NlQuerySecondaryKrbTgtNum(
                               (struct _DOMAIN_INFO *)a1,
                               (struct _GUID *)((char *)v65 + 628),
                               a13);
        v19 = SecondaryKrbTgtNum;
        if ( SecondaryKrbTgtNum < 0 )
        {
          LODWORD(v57) = SecondaryKrbTgtNum;
          NlPrintDomRoutine(
            0x100u,
            (struct _DOMAIN_INFO *)a1,
            L"NlGetIncomingPassword: NlQuerySecondaryKrbTgtNum failed AccountName:%ws Status:0x%x",
            a2,
            v57);
          NlPrintRoutine(0x100u, L"UserAllInfo->KrbTgtLinkObjectGuid: ");
          NlpDumpGuid(0x100u, v24);
          goto LABEL_158;
        }
        v22 = v65;
        v19 = 0;
      }
      v26 = v66;
      if ( !v66 )
      {
        v29 = v61;
        goto LABEL_154;
      }
      if ( *((_BYTE *)v22 + 313) && *((_WORD *)v22 + 112) == 16 )
      {
        v27 = (_OWORD *)*((_QWORD *)v22 + 29);
        v60 = 1;
        *v66 = *v27;
      }
      else if ( *((_BYTE *)v22 + 312) )
      {
        NlPrintRoutine(0x100u, L"NlGetIncomingPassword: No NT Password for %ws\n", a2);
        v19 = -1073741790;
        goto LABEL_158;
      }
      memset_0(v70, 0, sizeof(v70));
      v69 = 0x40000000;
      v28 = SamIUpdateLogonStatistics(v64, &v69);
      if ( v28 < 0 )
        NlPrintRoutine(0x100u, L"NlGetIncomingPassword: Cannot set last logon time %ws %lx\n", a2, (unsigned int)v28);
      v29 = v61;
LABEL_73:
      if ( !v60 && v26 )
      {
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, 0);
        v30 = SystemFunction007(&DestinationString, v26);
        v19 = v30;
        if ( v30 < 0 )
        {
          LODWORD(v57) = v30;
          NlPrintDomRoutine(
            0x100u,
            (struct _DOMAIN_INFO *)a1,
            L"NlGetIncomingPassword: %ws: cannot RtlCalculateNtOwfPassword (NULL) 0x%lx\n",
            a2,
            v57);
          goto LABEL_158;
        }
        v19 = 0;
      }
      if ( v62 )
      {
LABEL_158:
        if ( v65 )
          SamIFree_UserInternal6Information();
        goto LABEL_160;
      }
LABEL_154:
      if ( v29 )
      {
        if ( !v26 )
          NlAssertFailed(
            "OwfPassword != NULL",
            "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
            0x6CEu,
            (char *)v20);
        *(_OWORD *)v29 = *v26;
      }
      goto LABEL_158;
    }
    return 3221225572LL;
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  if ( v14 != 1024 )
  {
    if ( (unsigned int)v16 <= 1 || (unsigned int)_o__wcsicmp(&a2[(unsigned int)(v16 - 1)], L"$") )
      return 3221225572LL;
    goto LABEL_85;
  }
  if ( a2[(unsigned int)(v16 - 1)] == 46 )
LABEL_85:
    DestinationString.Length -= 2;
  v31 = LsarQueryTrustedDomainInfoByName(*(_QWORD *)(a1 + 392), &DestinationString, 8, &v58);
  v19 = v31;
  if ( v31 < 0 )
  {
    NlPrintDomRoutine(
      0x100u,
      (struct _DOMAIN_INFO *)a1,
      L"NlGetIncomingPassword: %wZ: cannot LsarQueryTrustedDomainInfoByName 0x%lx\n",
      &DestinationString,
      v31);
    if ( NlpIsNtStatusResourceError(v19) )
      goto LABEL_160;
    goto LABEL_88;
  }
  if ( (v58[20] & 1) == 0 )
  {
    NlPrintDomRoutine(
      0x100u,
      (struct _DOMAIN_INFO *)a1,
      L"NlGetIncomingPassword: %wZ: trust is not inbound\n",
      &DestinationString);
    goto LABEL_88;
  }
  v32 = v58;
  if ( (unsigned int)(*((_DWORD *)v58 + 11) - 1) > 1 )
  {
    NlPrintDomRoutine(
      0x100u,
      (struct _DOMAIN_INFO *)a1,
      L"NlGetIncomingPassword: %wZ: trust type doesn't match request type 0x%lx %ld\n",
      &DestinationString,
      v14,
      *((_DWORD *)v58 + 11));
LABEL_88:
    v19 = -1073741724;
    goto LABEL_160;
  }
  v20 = 2;
  v33 = *((_DWORD *)v58 + 12);
  if ( (v33 & 2) != 0 )
  {
    NlPrintDomRoutine(
      0x100u,
      (struct _DOMAIN_INFO *)a1,
      L"NlGetIncomingPassword: %wZ: trust is KERB only\n",
      &DestinationString);
    goto LABEL_88;
  }
  if ( a9 )
    *a9 = v33;
  if ( a10 )
    *a10 = *((_DWORD *)v32 + 11);
  v34 = v68;
  if ( v68 )
    *v34 = NlpCopySid(*((PSID *)v58 + 4));
  v35 = v63[0];
  v19 = 0;
  if ( v63[0] && *((_DWORD *)v58 + 11) == 2 && *v58 )
  {
    v36 = (unsigned __int16 *)LocalAlloc(0, *v58 + 2LL);
    v37 = v36;
    if ( !v36 )
    {
      v19 = -1073741801;
      goto LABEL_160;
    }
    memcpy_0(v36, *((const void **)v58 + 1), *v58);
    v37[(unsigned __int64)*v58 >> 1] = 0;
    *v35 = NlEqualDnsName(v37, a2);
    LocalFree(v37);
    v19 = 0;
  }
  v26 = v66;
  if ( v66 )
  {
    v38 = *((_DWORD *)v58 + 16);
    if ( !v38 || (v39 = *((_QWORD *)v58 + 9)) == 0 )
    {
      NlPrintDomRoutine(
        0x100u,
        (struct _DOMAIN_INFO *)a1,
        L"NlGetIncomingPassword: %wZ: No auth info for this domain.\n",
        &DestinationString);
      goto LABEL_88;
    }
    for ( i = 0; i < v38; ++i )
    {
      if ( *(_DWORD *)(v39 + 24LL * i + 8) == 1 )
      {
        if ( *(_DWORD *)(v39 + 24LL * i + 12) == 16 )
        {
          v41 = *(_OWORD **)(v39 + 24LL * i + 16);
          v60 = 1;
          *v26 = *v41;
        }
        else
        {
          LODWORD(v57) = *(_DWORD *)(v39 + 24LL * i + 12);
          NlPrintDomRoutine(
            0x100u,
            (struct _DOMAIN_INFO *)a1,
            L"NlGetIncomingPassword: %wZ: OWF password has bad length %ld\n",
            &DestinationString,
            v57);
        }
      }
      else if ( *(_DWORD *)(v39 + 24LL * i + 8) == 2 )
      {
        v42 = *(void **)(v39 + 24LL * i + 16);
        v63[0] = 0;
        v63[1] = v42;
        LOWORD(v63[0]) = *(_WORD *)(v39 + 24LL * i + 12);
        WORD1(v63[0]) = v63[0];
        NlPrintRoutine(0x4000000u, L"NlGetIncomingPassword: New Clear Password = ");
        NlpDumpBuffer(0x4000000u, v63[1], LOWORD(v63[0]));
        NlpDumpTime(v43, "NlGetIncomingPassword: New Password Changed: ", *(union _LARGE_INTEGER *)(v39 + 24LL * i));
        v44 = SystemFunction007(v63, v26);
        v19 = v44;
        if ( v44 < 0 )
        {
LABEL_120:
          p_DestinationString = &DestinationString;
          v46 = L"NlGetIncomingPassword: %wZ: cannot RtlCalculateNtOwfPassword 0x%lx\n";
          goto LABEL_121;
        }
        v60 = 1;
        break;
      }
    }
    v19 = 0;
  }
  v47 = v61;
  if ( !v61 )
  {
    v29 = 0;
    goto LABEL_144;
  }
  if ( !v26 )
  {
    NlAssertFailed(
      "OwfPassword != NULL",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
      0x542u,
      (char *)v20);
    v47 = v61;
  }
  v48 = *((_DWORD *)v58 + 16);
  if ( !v48 || (v49 = *((_QWORD *)v58 + 10)) == 0 )
  {
    NlPrintDomRoutine(
      0x100u,
      (struct _DOMAIN_INFO *)a1,
      L"NlGetIncomingPassword: %wZ: No previous auth info for this domain.\n",
      &DestinationString);
    goto LABEL_88;
  }
  for ( j = 0; ; ++j )
  {
    if ( j >= v48 )
    {
      v29 = v61;
      goto LABEL_140;
    }
    if ( *(_DWORD *)(v49 + 24LL * j + 8) != 1 )
      break;
    if ( *(_DWORD *)(v49 + 24LL * j + 12) == 16 )
    {
      v51 = *(_OWORD **)(v49 + 24LL * j + 16);
      v62 = 1;
      *(_OWORD *)v47 = *v51;
    }
    else
    {
      LODWORD(v57) = *(_DWORD *)(v49 + 24LL * j + 12);
      NlPrintDomRoutine(
        0x100u,
        (struct _DOMAIN_INFO *)a1,
        L"NlGetIncomingPassword: %wZ: previous OWF password has bad length %ld\n",
        &DestinationString,
        v57);
    }
LABEL_137:
    v47 = v61;
  }
  if ( *(_DWORD *)(v49 + 24LL * j + 8) != 2 )
    goto LABEL_137;
  v52 = *(void **)(v49 + 24LL * j + 16);
  v63[0] = 0;
  v63[1] = v52;
  LOWORD(v63[0]) = *(_WORD *)(v49 + 24LL * j + 12);
  WORD1(v63[0]) = v63[0];
  NlPrintRoutine(0x4000000u, L"NlGetIncomingPassword: Old Clear Password = ");
  NlpDumpBuffer(0x4000000u, v63[1], LOWORD(v63[0]));
  NlpDumpTime(v53, "NlGetIncomingPassword: Old Password Changed: ", *(union _LARGE_INTEGER *)(v49 + 24LL * j));
  v29 = v61;
  v44 = SystemFunction007(v63, v61);
  v19 = v44;
  if ( v44 < 0 )
    goto LABEL_120;
  v62 = 1;
LABEL_140:
  v26 = v66;
  v19 = 0;
LABEL_144:
  v54 = v67;
  if ( !v67 )
    goto LABEL_73;
  v55 = v58;
  if ( (unsigned __int16)(v58[8] - 2) > 0x1Cu )
  {
    LODWORD(v57) = v58[8];
    NlPrintDomRoutine(
      0x100u,
      (struct _DOMAIN_INFO *)a1,
      L"NlGetIncomingPassword: %wZ: Flat Name length is bad %ld\n",
      &DestinationString,
      v57);
    v19 = -1073741595;
    goto LABEL_160;
  }
  memcpy_0(v71, *((const void **)v58 + 3), v58[8]);
  v71[(unsigned __int64)v55[8] >> 1] = 36;
  v56 = (v55[8] & 0xFFFE) + 2LL;
  if ( v56 >= 0x22 )
    _report_rangecheckfailure();
  *(unsigned __int16 *)((char *)v71 + v56) = 0;
  v44 = NlSamOpenNamedUser((struct _DOMAIN_INFO *)a1, v71, 0, 0, 0, v54, 0);
  v19 = v44;
  if ( v44 >= 0 )
  {
    v19 = 0;
    goto LABEL_73;
  }
  p_DestinationString = (struct _UNICODE_STRING *)v71;
  v46 = L"NlGetIncomingPassword: Can't NlSamOpenNamedUser for %ws 0x%lx.\n";
LABEL_121:
  LODWORD(v57) = v44;
  NlPrintDomRoutine(0x100u, (struct _DOMAIN_INFO *)a1, v46, p_DestinationString, v57);
LABEL_160:
  if ( v64 )
    SamrCloseHandle(&v64);
  if ( v58 )
    LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO(8);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1800374dc  push    rbp
0x1800374de  push    rbx
0x1800374df  push    rsi
0x1800374e0  push    rdi
0x1800374e1  push    r12
0x1800374e3  push    r13
0x1800374e5  push    r14
0x1800374e7  push    r15
0x1800374e9  lea     rbp, [rsp-0A8h]
0x1800374f1  sub     rsp, 1A8h
0x1800374f8  mov     rax, cs:__security_cookie
0x1800374ff  xor     rax, rsp
0x180037502  mov     [rbp+0E0h+var_48], rax
0x180037509  mov     rax, [rbp+0E0h+arg_28]
0x180037510  xor     r10d, r10d
0x180037513  mov     r12, [rbp+0E0h+arg_40]
0x18003751a  mov     r14, rdx
0x18003751d  mov     rdx, [rbp+0E0h+arg_38]
0x180037524  mov     esi, r9d
0x180037527  mov     r9, [rbp+0E0h+arg_30]; char *
0x18003752e  mov     rdi, rcx
0x180037531  mov     rcx, [rbp+0E0h+arg_58]
0x180037538  mov     r13, [rbp+0E0h+arg_48]
0x18003753f  mov     r15, [rbp+0E0h+arg_60]
0x180037546  mov     [rbp+0E0h+var_150], rax
0x18003754a  mov     rax, [rbp+0E0h+arg_50]
0x180037551  mov     [rbp+0E0h+var_140], rax
0x180037555  mov     [rsp+1E0h+var_180], r9
0x18003755a  mov     [rbp+0E0h+var_148], rdx
0x18003755e  mov     [rsp+1E0h+var_170], rcx
0x180037563  mov     [rbp+0E0h+var_160], r10
0x180037567  mov     [rbp+0E0h+var_158], r10
0x18003756b  mov     [rsp+1E0h+var_1A0], r10
0x180037570  test    rdx, rdx
0x180037573  jz      short loc_180037578
0x180037575  mov     [rdx], r10d
0x180037578  test    r12, r12
0x18003757b  jz      short loc_180037581
0x18003757d  mov     [r12], r10d
0x180037581  test    r13, r13
0x180037584  jz      short loc_18003758A
0x180037586  mov     [r13+0], r10d
0x18003758a  test    rax, rax
0x18003758d  jz      short loc_180037592
0x18003758f  mov     [rax], r10
0x180037592  test    rcx, rcx
0x180037595  jz      short loc_18003759A
0x180037597  mov     [rcx], r10d
0x18003759a  test    r15, r15
0x18003759d  jz      short loc_1800375B1
0x18003759f  cmp     cs:?NlGlobalCDC@@3HA, r10d; int NlGlobalCDC
0x1800375a6  jnz     short loc_1800375C4
0x1800375a8  cmp     r8d, 7
0x1800375ac  jnz     short loc_1800375C4
0x1800375ae  mov     [r15], r10d
0x1800375b1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800375b5  inc     rbx
0x1800375b8  cmp     [r14+rbx*2], r10w
0x1800375bd  jnz     short loc_1800375B5
0x1800375bf  cmp     ebx, 1
0x1800375c2  jnb     short loc_1800375CE
0x1800375c4  mov     eax, 0C000000Dh
0x1800375c9  jmp     loc_180037FC9
0x1800375ce  mov     ecx, r8d
0x1800375d1  mov     eax, 100h
0x1800375d6  mov     edx, 400h
0x1800375db  mov     r11d, 2
0x1800375e1  test    r8d, r8d
0x1800375e4  jz      loc_1800377B9
0x1800375ea  sub     ecx, r11d
0x1800375ed  jz      loc_1800377B0
0x1800375f3  sub     ecx, 1
0x1800375f6  jz      loc_1800377A9
0x1800375fc  sub     ecx, 1
0x1800375ff  jz      loc_1800377A1
0x180037605  sub     ecx, r11d
0x180037608  jz      loc_18003779A
0x18003760e  cmp     ecx, 1
0x180037611  jz      short loc_180037622
0x180037613  mov     r9d, r8d
0x180037616  lea     r8, aNlgetincomingp_22; "NlGetIncomingPassword: Invalid channel "...
0x18003761d  jmp     loc_1800377CB
0x180037622  bts     esi, 14h
0x180037626  mov     [rsp+1E0h+var_188], r10d
0x18003762b  mov     [rsp+1E0h+var_178], r10d
0x180037630  cmp     esi, edx
0x180037632  jz      loc_1800379FC
0x180037638  cmp     esi, 40h ; '@'
0x18003763b  jz      loc_1800379FC
0x180037641  lea     r12, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180037648  test    r9, r9
0x18003764b  jz      short loc_180037667
0x18003764d  mov     r8d, 5D6h; unsigned int
0x180037653  lea     rcx, aOwfpreviouspas; "OwfPreviousPassword == NULL"
0x18003765a  mov     rdx, r12; void *
0x18003765d  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180037662  mov     eax, 100h
0x180037667  cmp     esi, eax
0x180037669  jz      short loc_18003767B
0x18003766b  cmp     esi, 80h
0x180037671  jz      short loc_18003767B
0x180037673  cmp     esi, 100000h
0x180037679  jnz     short loc_1800376A6
0x18003767b  cmp     ebx, 1
0x18003767e  jbe     loc_180037FC4
0x180037684  lea     eax, [rbx-1]
0x180037687  lea     rcx, [r14+rax*2]
0x18003768b  lea     rdx, asc_1800ACA94; "$"
0x180037692  call    cs:__imp__o__wcsicmp
0x180037699  nop     dword ptr [rax+rax+00h]
0x18003769e  test    eax, eax
0x1800376a0  jnz     loc_180037FC4
0x1800376a6  mov     r13, [rbp+0E0h+var_148]
0x1800376aa  mov     rax, r15
0x1800376ad  neg     rax
0x1800376b0  mov     r8d, 23100000h; unsigned int
0x1800376b6  lea     rax, [rbp+0E0h+var_158]
0x1800376ba  mov     rdx, r14; unsigned __int16 *
0x1800376bd  mov     [rsp+1E0h+var_1B0], rax; struct _USER_INTERNAL6_INFORMATION **
0x1800376c2  sbb     r9d, r9d
0x1800376c5  lea     rax, [rbp+0E0h+var_160]
0x1800376c9  mov     [rsp+1E0h+var_1B8], r13; unsigned int *
0x1800376ce  and     r9d, 8000000h; unsigned int
0x1800376d5  mov     [rsp+1E0h+var_1C0], rax; void **
0x1800376da  mov     rcx, rdi; struct _DOMAIN_INFO *
0x1800376dd  call    ?NlSamOpenNamedUser@@YAJPEAU_DOMAIN_INFO@@PEBGKKPEAPEAXPEAKPEAPEAU_USER_INTERNAL6_INFORMATION@@@Z; NlSamOpenNamedUser(_DOMAIN_INFO *,ushort const *,ulong,ulong,void * *,ulong *,_USER_INTERNAL6_INFORMATION * *)
0x1800376e2  mov     ebx, eax
0x1800376e4  xor     eax, eax
0x1800376e6  test    ebx, ebx
0x1800376e8  jns     loc_1800377DF
0x1800376ee  cmp     cs:?NlGlobalCDC@@3HA, eax; int NlGlobalCDC
0x1800376f4  jz      loc_18003777A
0x1800376fa  cmp     ebx, 0C0000371h
0x180037700  jnz     short loc_18003777A
0x180037702  test    r15, r15
0x180037705  jz      short loc_18003771C
0x180037707  mov     r8d, 602h; unsigned int
0x18003770d  lea     rcx, aCdcbranchid; "!CdcBranchId"
0x180037714  mov     rdx, r12; void *
0x180037717  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18003771c  xor     edx, edx; Val
0x18003771e  lea     rcx, [rbp+0E0h+var_130]; void *
0x180037722  mov     r8d, 0C0h; Size
0x180037728  call    memset_0
0x18003772d  xor     r9d, r9d; unsigned int
0x180037730  lea     rax, [rbp+0E0h+var_158]
0x180037734  mov     [rsp+1E0h+var_1B0], rax; struct _USER_INTERNAL6_INFORMATION **
0x180037739  mov     rdx, r14; unsigned __int16 *
0x18003773c  lea     rax, [rbp+0E0h+var_160]
0x180037740  mov     [rsp+1E0h+var_1B8], r13; unsigned int *
0x180037745  mov     rcx, rdi; struct _DOMAIN_INFO *
0x180037748  mov     [rsp+1E0h+var_1C0], rax; void **
0x18003774d  lea     r8d, [r9+4]; unsigned int
0x180037751  call    ?NlSamOpenNamedUser@@YAJPEAU_DOMAIN_INFO@@PEBGKKPEAPEAXPEAKPEAPEAU_USER_INTERNAL6_INFORMATION@@@Z; NlSamOpenNamedUser(_DOMAIN_INFO *,ushort const *,ulong,ulong,void * *,ulong *,_USER_INTERNAL6_INFORMATION * *)
0x180037756  test    eax, eax
0x180037758  js      short loc_180037775
0x18003775a  mov     rcx, [rbp+0E0h+var_160]
0x18003775e  lea     rdx, [rbp+0E0h+var_130]
0x180037762  mov     [rbp+0E0h+var_130], 880000h
0x180037769  call    cs:__imp_SamIUpdateLogonStatistics
0x180037770  nop     dword ptr [rax+rax+00h]
0x180037775  mov     ebx, 0C000018Bh
0x18003777a  lea     r8, aNlgetincomingp_18; "NlGetIncomingPassword: Can't NlSamOpenN"...
0x180037781  mov     dword ptr [rsp+1E0h+var_1C0], ebx
0x180037785  mov     r9, r14
0x180037788  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18003778b  mov     ecx, 100h; unsigned int
0x180037790  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180037795  jmp     loc_180037F79
0x18003779a  or      esi, eax
0x18003779c  jmp     loc_180037626
0x1800377a1  or      esi, 40h
0x1800377a4  jmp     loc_180037626
0x1800377a9  or      esi, edx
0x1800377ab  jmp     loc_180037626
0x1800377b0  bts     esi, 7
0x1800377b4  jmp     loc_180037626
0x1800377b9  test    esi, esi
0x1800377bb  jnz     loc_180037626
0x1800377c1  xor     r9d, r9d
0x1800377c4  lea     r8, aNlgetincomingp_14; "NlGetIncomingPassword: Invalid AAC (%x)"...
0x1800377cb  mov     rdx, rdi; struct _DOMAIN_INFO *
0x1800377ce  mov     [rsp+1E0h+var_1C0], r14
0x1800377d3  mov     ecx, eax; unsigned int
0x1800377d5  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x1800377da  jmp     loc_1800375C4
0x1800377df  mov     rdx, [rbp+0E0h+var_158]
0x1800377e3  mov     eax, esi
0x1800377e5  mov     r8d, 1001D8h
0x1800377eb  mov     ecx, [rdx+118h]
0x1800377f1  and     eax, ecx
0x1800377f3  test    r8d, eax
0x1800377f6  jnz     short loc_180037825
0x1800377f8  and     ecx, r8d
0x1800377fb  mov     [rsp+1E0h+var_1B8], r14
0x180037800  mov     r9d, ecx
0x180037803  mov     dword ptr [rsp+1E0h+var_1C0], esi
0x180037807  mov     ecx, 100h; unsigned int
0x18003780c  lea     r8, aNlgetincomingp_3; "NlGetIncomingPassword: Invalid account "...
0x180037813  mov     rdx, rdi; struct _DOMAIN_INFO *
0x180037816  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18003781b  mov     ebx, 0C0000064h
0x180037820  jmp     loc_180037F79
0x180037825  xor     ebx, ebx
0x180037827  cmp     [rbp+0E0h+arg_20], ebx
0x18003782d  jz      short loc_18003784D
0x18003782f  test    cl, 1
0x180037832  jz      short loc_18003784D
0x180037834  mov     r9, r14
0x180037837  lea     r8, aNlgetincomingp_16; "NlGetIncomingPassword: %ws account is d"...
0x18003783e  mov     rdx, rdi; struct _DOMAIN_INFO *
0x180037841  mov     ecx, 100h; unsigned int
0x180037846  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18003784b  jmp     short loc_18003781B
0x18003784d  test    r15, r15
0x180037850  jz      loc_1800378DD
0x180037856  bt      ecx, 14h
0x18003785a  jb      short loc_180037882
0x18003785c  mov     r8d, 65Dh; unsigned int
0x180037862  lea     rcx, aFalse; "FALSE"
0x180037869  mov     rdx, r12; void *
0x18003786c  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180037871  lea     r8, aNlgetincomingp_8; "NlGetIncomingPassword: branch id reques"...
0x180037878  mov     ebx, 0C000000Dh
0x18003787d  jmp     loc_180037781
0x180037882  lea     rsi, [rdx+274h]
0x180037889  mov     r8, r15; unsigned int *
0x18003788c  mov     rdx, rsi; struct _GUID *
0x18003788f  mov     rcx, rdi; struct _DOMAIN_INFO *
0x180037892  call    ?NlQuerySecondaryKrbTgtNum@@YAJPEAU_DOMAIN_INFO@@PEAU_GUID@@PEAK@Z; NlQuerySecondaryKrbTgtNum(_DOMAIN_INFO *,_GUID *,ulong *)
0x180037897  mov     ebx, eax
0x180037899  test    eax, eax
0x18003789b  jns     short loc_1800378D7
0x18003789d  mov     rdx, rdi; struct _DOMAIN_INFO *
0x1800378a0  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x1800378a4  mov     edi, 100h
0x1800378a9  lea     r8, aNlgetincomingp_21; "NlGetIncomingPassword: NlQuerySecondary"...
0x1800378b0  mov     ecx, edi; unsigned int
0x1800378b2  mov     r9, r14
0x1800378b5  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x1800378ba  lea     rdx, aUserallinfoKrb; "UserAllInfo->KrbTgtLinkObjectGuid: "
0x1800378c1  mov     ecx, edi; unsigned int
0x1800378c3  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800378c8  mov     rdx, rsi; Uuid
0x1800378cb  mov     ecx, edi; unsigned int
0x1800378cd  call    ?NlpDumpGuid@@YAXKPEAU_GUID@@@Z; NlpDumpGuid(ulong,_GUID *)
0x1800378d2  jmp     loc_180037F79
0x1800378d7  mov     rdx, [rbp+0E0h+var_158]
0x1800378db  xor     ebx, ebx
0x1800378dd  mov     r13, [rbp+0E0h+var_150]
0x1800378e1  test    r13, r13
0x1800378e4  jz      loc_1800379F2
0x1800378ea  cmp     [rdx+139h], bl
0x1800378f0  jz      loc_1800379C8
0x1800378f6  mov     eax, 10h
0x1800378fb  cmp     [rdx+0E0h], ax
0x180037902  jnz     loc_1800379C8
0x180037908  mov     rax, [rdx+0E8h]
0x18003790f  mov     [rsp+1E0h+var_188], 1
0x180037917  movups  xmm0, xmmword ptr [rax]
0x18003791a  movdqu  xmmword ptr [r13+0], xmm0
0x180037920  xor     edx, edx; Val
0x180037922  lea     rcx, [rbp+0E0h+var_12C]; void *
0x180037926  mov     r8d, 0BCh; Size
0x18003792c  call    memset_0
0x180037931  mov     rcx, [rbp+0E0h+var_160]
0x180037935  lea     rdx, [rbp+0E0h+var_130]
0x180037939  mov     [rbp+0E0h+var_130], 40000000h
0x180037940  call    cs:__imp_SamIUpdateLogonStatistics
0x180037947  nop     dword ptr [rax+rax+00h]
0x18003794c  test    eax, eax
0x18003794e  jns     short loc_180037967
0x180037950  mov     r9d, eax
0x180037953  lea     rdx, aNlgetincomingp_0; "NlGetIncomingPassword: Cannot set last "...
0x18003795a  mov     r8, r14
0x18003795d  mov     ecx, 100h; unsigned int
0x180037962  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180037967  mov     r15, [rsp+1E0h+var_180]
0x18003796c  cmp     [rsp+1E0h+var_188], ebx
0x180037970  jnz     loc_180037F4A
0x180037976  test    r13, r13
0x180037979  jz      loc_180037F4A
0x18003797f  xorps   xmm0, xmm0
0x180037982  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x180037987  xor     edx, edx; SourceString
0x180037989  movups  xmmword ptr [rsp+1E0h+DestinationString.Length], xmm0
0x18003798e  call    cs:__imp_RtlInitUnicodeString
0x180037995  nop     dword ptr [rax+rax+00h]
0x18003799a  mov     rdx, r13
0x18003799d  lea     rcx, [rsp+1E0h+DestinationString]
0x1800379a2  call    cs:__imp_SystemFunction007
0x1800379a9  nop     dword ptr [rax+rax+00h]
0x1800379ae  mov     ebx, eax
0x1800379b0  test    eax, eax
0x1800379b2  jns     loc_180037F48
0x1800379b8  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x1800379bc  lea     r8, aNlgetincomingp_20; "NlGetIncomingPassword: %ws: cannot RtlC"...
0x1800379c3  jmp     loc_180037785
0x1800379c8  cmp     [rdx+138h], bl
0x1800379ce  jz      loc_180037920
  ... truncated ...
```
