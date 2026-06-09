# NlGetIncomingPassword(_DOMAIN_INFO *,ushort const *,_NETLOGON_SECURE_CHANNEL_TYPE,ulong,int,_LM_OWF_PASSWORD *,_LM_OWF_PASSWORD *,ulong *,ulong *,ulong *,void * *,int *,ulong *)

- ea: `0x1800354d8`
- end: `0x180035f8a`
- name: `?NlGetIncomingPassword@@YAJPEAU_DOMAIN_INFO@@PEBGW4_NETLOGON_SECURE_CHANNEL_TYPE@@KHPEAU_LM_OWF_PASSWORD@@3PEAK44PEAPEAXPEAH4@Z`
- size: `2738`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800563a4`
- `0x180056644`
- `0x18005d780`
- `0x18005e190`
- `0x18005e700`
- `0x18005eb00`
- `0x18005f1a0`
- `0x18006da7c`

## callees

- `0x180007278`
- `0x18000bd98`
- `0x18000d710`
- `0x18000e270`
- `0x18000e660`
- `0x18000ed34`
- `0x1800354d8`
- `0x1800369b4`
- `0x180036cc8`
- `0x18003f054`
- `0x18003f294`
- `0x18003f434`
- `0x18003f540`
- `0x180050ca0`
- `0x18008315c`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003568e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035a18`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003568e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035a18`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180035b52`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180035b52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035ba0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035ba0`
- `LSASRV!LsarQueryTrustedDomainInfoByName` at `0x180035a47`
- `LSASRV!LsarQueryTrustedDomainInfoByName` at `0x180035a47`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180035f58`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180035f58`
- `ntdll!RtlInitUnicodeString` at `0x180035974`
- `ntdll!RtlInitUnicodeString` at `0x1800359e6`
- `ntdll!RtlInitUnicodeString` at `0x180035974`
- `ntdll!RtlInitUnicodeString` at `0x1800359e6`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x18003575b`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x18003592c`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x18003575b`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x18003592c`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x180035f32`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x180035f32`
- `SAMSRV!SamrCloseHandle` at `0x180035f43`
- `SAMSRV!SamrCloseHandle` at `0x180035f43`
- `CRYPTSP!SystemFunction007` at `0x180035982`
- `CRYPTSP!SystemFunction007` at `0x180035c9b`
- `CRYPTSP!SystemFunction007` at `0x180035e01`
- `CRYPTSP!SystemFunction007` at `0x180035982`
- `CRYPTSP!SystemFunction007` at `0x180035c9b`
- `CRYPTSP!SystemFunction007` at `0x180035e01`

## string_xrefs

- `0x18003563d`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x180035cd8`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x1800357b0`: `NlGetIncomingPassword: Invalid AAC (%x) for %ws\n`
- `0x180035612`: `NlGetIncomingPassword: Invalid channel type (%x) for %ws\n`
- `0x180035a5c`: `NlGetIncomingPassword: %wZ: cannot LsarQueryTrustedDomainInfoByName 0x%lx\n`
- `0x180035a94`: `NlGetIncomingPassword: %wZ: trust is not inbound\n`
- `0x180035ad1`: `NlGetIncomingPassword: %wZ: trust type doesn't match request type 0x%lx %ld\n`
- `0x180035af5`: `NlGetIncomingPassword: %wZ: trust is KERB only\n`
- `0x180035d6a`: `NlGetIncomingPassword: %wZ: No auth info for this domain.\n`
- `0x180035c02`: `NlGetIncomingPassword: %wZ: OWF password has bad length %ld\n`
- `0x180035c41`: `NlGetIncomingPassword: New Clear Password = `
- `0x180035c87`: `NlGetIncomingPassword: New Password Changed: `
- `0x180035cac`: `NlGetIncomingPassword: %wZ: cannot RtlCalculateNtOwfPassword 0x%lx\n`
- `0x180035e28`: `NlGetIncomingPassword: %wZ: No previous auth info for this domain.\n`
- `0x180035d54`: `NlGetIncomingPassword: %wZ: previous OWF password has bad length %ld\n`
- `0x180035da2`: `NlGetIncomingPassword: Old Clear Password = `
- `0x180035de8`: `NlGetIncomingPassword: Old Password Changed: `
- `0x180035ee2`: `NlGetIncomingPassword: %wZ: Flat Name length is bad %ld\n`
- `0x180035766`: `NlGetIncomingPassword: Can't NlSamOpenNamedUser for %ws 0x%lx.\n`
- `0x180035ebb`: `NlGetIncomingPassword: Can't NlSamOpenNamedUser for %ws 0x%lx.\n`
- `0x1800357f8`: `NlGetIncomingPassword: Invalid account type (%x) instead of %x for %ws\n`
- `0x180035823`: `NlGetIncomingPassword: %ws account is disabled\n`
- `0x18003585d`: `NlGetIncomingPassword: branch id requested but account '%ws' is not an RODC account Status:0x%x`
- `0x180035895`: `NlGetIncomingPassword: NlQuerySecondaryKrbTgtNum failed AccountName:%ws Status:0x%x`
- `0x1800358a6`: `UserAllInfo->KrbTgtLinkObjectGuid: `
- `0x1800359b1`: `NlGetIncomingPassword: No NT Password for %ws\n`
- `0x180035939`: `NlGetIncomingPassword: Cannot set last logon time %ws %lx\n`
- `0x180035996`: `NlGetIncomingPassword: %ws: cannot RtlCalculateNtOwfPassword (NULL) 0x%lx\n`

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
  __int64 v56; // rdx
  unsigned __int64 v57; // rcx
  void **v58; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v59; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  int v61; // [rsp+58h] [rbp-A8h]
  char *v62; // [rsp+60h] [rbp-A0h]
  int v63; // [rsp+68h] [rbp-98h]
  void *v64[2]; // [rsp+70h] [rbp-90h] BYREF
  void *v65; // [rsp+80h] [rbp-80h] BYREF
  struct _USER_INTERNAL6_INFORMATION *v66; // [rsp+88h] [rbp-78h] BYREF
  _OWORD *v67; // [rsp+90h] [rbp-70h]
  unsigned int *v68; // [rsp+98h] [rbp-68h]
  _QWORD *v69; // [rsp+A0h] [rbp-60h]
  int v70; // [rsp+B0h] [rbp-50h] BYREF
  char v71[188]; // [rsp+B4h] [rbp-4Ch] BYREF
  unsigned __int16 v72[20]; // [rsp+170h] [rbp+70h] BYREF

  v14 = a4;
  v67 = a6;
  v69 = a11;
  v62 = a7;
  v68 = a8;
  v64[0] = a12;
  v65 = 0;
  v66 = 0;
  v59 = 0;
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
  v61 = 0;
  v63 = 0;
  if ( v14 != 1024 && v14 != 64 )
  {
    if ( a7 )
      NlAssertFailed(
        "OwfPreviousPassword == NULL",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
        1494,
        a7);
    if ( v14 != 256 && v14 != 128 && v14 != 0x100000
      || (unsigned int)v16 > 1 && !(unsigned int)_o__wcsicmp(&a2[(unsigned int)(v16 - 1)]) )
    {
      v18 = v68;
      v19 = NlSamOpenNamedUser((struct _DOMAIN_INFO *)a1, a2, 0x23100000u, a13 != 0 ? 0x8000000 : 0, &v65, v68, &v66);
      if ( v19 < 0 )
      {
        if ( NlGlobalCDC && v19 == -1073740943 )
        {
          if ( a13 )
            NlAssertFailed(
              "!CdcBranchId",
              "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
              1538,
              (char *)v20);
          memset_0(&v70, 0, 0xC0u);
          if ( (int)NlSamOpenNamedUser((struct _DOMAIN_INFO *)a1, a2, 4u, 0, &v65, v18, &v66) >= 0 )
          {
            v70 = 8912896;
            SamIUpdateLogonStatistics(v65, &v70);
          }
          v19 = -1073741429;
        }
        v21 = L"NlGetIncomingPassword: Can't NlSamOpenNamedUser for %ws 0x%lx.\n";
        goto LABEL_45;
      }
      v22 = v66;
      v23 = *((_DWORD *)v66 + 70);
      if ( (v23 & v14 & 0x1001D8) == 0 )
      {
        LODWORD(v58) = v14;
        NlPrintDomRoutine(
          0x100u,
          (struct _DOMAIN_INFO *)a1,
          L"NlGetIncomingPassword: Invalid account type (%x) instead of %x for %ws\n",
          v23 & 0x1001D8,
          v58,
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
          NlAssertFailed("FALSE", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx", 1629, (char *)v20);
          v21 = L"NlGetIncomingPassword: branch id requested but account '%ws' is not an RODC account Status:0x%x";
          v19 = -1073741811;
LABEL_45:
          LODWORD(v58) = v19;
          NlPrintDomRoutine(0x100u, (struct _DOMAIN_INFO *)a1, v21, a2, v58);
          goto LABEL_158;
        }
        v24 = (UUID *)((char *)v66 + 628);
        SecondaryKrbTgtNum = NlQuerySecondaryKrbTgtNum(
                               (struct _DOMAIN_INFO *)a1,
                               (struct _GUID *)((char *)v66 + 628),
                               a13);
        v19 = SecondaryKrbTgtNum;
        if ( SecondaryKrbTgtNum < 0 )
        {
          LODWORD(v58) = SecondaryKrbTgtNum;
          NlPrintDomRoutine(
            0x100u,
            (struct _DOMAIN_INFO *)a1,
            L"NlGetIncomingPassword: NlQuerySecondaryKrbTgtNum failed AccountName:%ws Status:0x%x",
            a2,
            v58);
          NlPrintRoutine(0x100u, L"UserAllInfo->KrbTgtLinkObjectGuid: ");
          NlpDumpGuid(0x100u, v24);
          goto LABEL_158;
        }
        v22 = v66;
        v19 = 0;
      }
      v26 = v67;
      if ( !v67 )
      {
        v29 = v62;
        goto LABEL_154;
      }
      if ( *((_BYTE *)v22 + 313) && *((_WORD *)v22 + 112) == 16 )
      {
        v27 = (_OWORD *)*((_QWORD *)v22 + 29);
        v61 = 1;
        *v67 = *v27;
      }
      else if ( *((_BYTE *)v22 + 312) )
      {
        NlPrintRoutine(0x100u, L"NlGetIncomingPassword: No NT Password for %ws\n", a2);
        v19 = -1073741790;
        goto LABEL_158;
      }
      memset_0(v71, 0, sizeof(v71));
      v70 = 0x40000000;
      v28 = SamIUpdateLogonStatistics(v65, &v70);
      if ( v28 < 0 )
        NlPrintRoutine(0x100u, L"NlGetIncomingPassword: Cannot set last logon time %ws %lx\n", a2, (unsigned int)v28);
      v29 = v62;
LABEL_73:
      if ( !v61 && v26 )
      {
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, 0);
        v30 = SystemFunction007(&DestinationString, v26);
        v19 = v30;
        if ( v30 < 0 )
        {
          LODWORD(v58) = v30;
          NlPrintDomRoutine(
            0x100u,
            (struct _DOMAIN_INFO *)a1,
            L"NlGetIncomingPassword: %ws: cannot RtlCalculateNtOwfPassword (NULL) 0x%lx\n",
            a2,
            v58);
          goto LABEL_158;
        }
        v19 = 0;
      }
      if ( v63 )
      {
LABEL_158:
        if ( v66 )
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
            1742,
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
    if ( (unsigned int)v16 <= 1 || (unsigned int)_o__wcsicmp(&a2[(unsigned int)(v16 - 1)]) )
      return 3221225572LL;
    goto LABEL_85;
  }
  if ( a2[(unsigned int)(v16 - 1)] == 46 )
LABEL_85:
    DestinationString.Length -= 2;
  v31 = LsarQueryTrustedDomainInfoByName(*(_QWORD *)(a1 + 392), &DestinationString, 8, &v59);
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
  if ( (v59[20] & 1) == 0 )
  {
    NlPrintDomRoutine(
      0x100u,
      (struct _DOMAIN_INFO *)a1,
      L"NlGetIncomingPassword: %wZ: trust is not inbound\n",
      &DestinationString);
    goto LABEL_88;
  }
  v32 = v59;
  if ( (unsigned int)(*((_DWORD *)v59 + 11) - 1) > 1 )
  {
    NlPrintDomRoutine(
      0x100u,
      (struct _DOMAIN_INFO *)a1,
      L"NlGetIncomingPassword: %wZ: trust type doesn't match request type 0x%lx %ld\n",
      &DestinationString,
      v14,
      *((_DWORD *)v59 + 11));
LABEL_88:
    v19 = -1073741724;
    goto LABEL_160;
  }
  v20 = 2;
  v33 = *((_DWORD *)v59 + 12);
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
  v34 = v69;
  if ( v69 )
    *v34 = NlpCopySid(*((PSID *)v59 + 4));
  v35 = v64[0];
  v19 = 0;
  if ( v64[0] && *((_DWORD *)v59 + 11) == 2 && *v59 )
  {
    v36 = (unsigned __int16 *)LocalAlloc(0, *v59 + 2LL);
    v37 = v36;
    if ( !v36 )
    {
      v19 = -1073741801;
      goto LABEL_160;
    }
    memcpy_0(v36, *((const void **)v59 + 1), *v59);
    v37[(unsigned __int64)*v59 >> 1] = 0;
    *v35 = NlEqualDnsName(v37, a2);
    LocalFree(v37);
    v19 = 0;
  }
  v26 = v67;
  if ( v67 )
  {
    v38 = *((_DWORD *)v59 + 16);
    if ( !v38 || (v39 = *((_QWORD *)v59 + 9)) == 0 )
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
          v61 = 1;
          *v26 = *v41;
        }
        else
        {
          LODWORD(v58) = *(_DWORD *)(v39 + 24LL * i + 12);
          NlPrintDomRoutine(
            0x100u,
            (struct _DOMAIN_INFO *)a1,
            L"NlGetIncomingPassword: %wZ: OWF password has bad length %ld\n",
            &DestinationString,
            v58);
        }
      }
      else if ( *(_DWORD *)(v39 + 24LL * i + 8) == 2 )
      {
        v42 = *(void **)(v39 + 24LL * i + 16);
        v64[0] = 0;
        v64[1] = v42;
        LOWORD(v64[0]) = *(_WORD *)(v39 + 24LL * i + 12);
        WORD1(v64[0]) = v64[0];
        NlPrintRoutine(0x4000000u, L"NlGetIncomingPassword: New Clear Password = ");
        NlpDumpBuffer(0x4000000u, v64[1], LOWORD(v64[0]));
        NlpDumpTime(v43, "NlGetIncomingPassword: New Password Changed: ", *(union _LARGE_INTEGER *)(v39 + 24LL * i));
        v44 = SystemFunction007(v64, v26);
        v19 = v44;
        if ( v44 < 0 )
        {
LABEL_120:
          p_DestinationString = &DestinationString;
          v46 = L"NlGetIncomingPassword: %wZ: cannot RtlCalculateNtOwfPassword 0x%lx\n";
          goto LABEL_121;
        }
        v61 = 1;
        break;
      }
    }
    v19 = 0;
  }
  v47 = v62;
  if ( !v62 )
  {
    v29 = 0;
    goto LABEL_144;
  }
  if ( !v26 )
  {
    NlAssertFailed(
      "OwfPassword != NULL",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
      1346,
      (char *)v20);
    v47 = v62;
  }
  v48 = *((_DWORD *)v59 + 16);
  if ( !v48 || (v49 = *((_QWORD *)v59 + 10)) == 0 )
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
      v29 = v62;
      goto LABEL_140;
    }
    if ( *(_DWORD *)(v49 + 24LL * j + 8) != 1 )
      break;
    if ( *(_DWORD *)(v49 + 24LL * j + 12) == 16 )
    {
      v51 = *(_OWORD **)(v49 + 24LL * j + 16);
      v63 = 1;
      *(_OWORD *)v47 = *v51;
    }
    else
    {
      LODWORD(v58) = *(_DWORD *)(v49 + 24LL * j + 12);
      NlPrintDomRoutine(
        0x100u,
        (struct _DOMAIN_INFO *)a1,
        L"NlGetIncomingPassword: %wZ: previous OWF password has bad length %ld\n",
        &DestinationString,
        v58);
    }
LABEL_137:
    v47 = v62;
  }
  if ( *(_DWORD *)(v49 + 24LL * j + 8) != 2 )
    goto LABEL_137;
  v52 = *(void **)(v49 + 24LL * j + 16);
  v64[0] = 0;
  v64[1] = v52;
  LOWORD(v64[0]) = *(_WORD *)(v49 + 24LL * j + 12);
  WORD1(v64[0]) = v64[0];
  NlPrintRoutine(0x4000000u, L"NlGetIncomingPassword: Old Clear Password = ");
  NlpDumpBuffer(0x4000000u, v64[1], LOWORD(v64[0]));
  NlpDumpTime(v53, "NlGetIncomingPassword: Old Password Changed: ", *(union _LARGE_INTEGER *)(v49 + 24LL * j));
  v29 = v62;
  v44 = SystemFunction007(v64, v62);
  v19 = v44;
  if ( v44 < 0 )
    goto LABEL_120;
  v63 = 1;
LABEL_140:
  v26 = v67;
  v19 = 0;
LABEL_144:
  v54 = v68;
  if ( !v68 )
    goto LABEL_73;
  v55 = v59;
  if ( (unsigned __int16)(v59[8] - 2) > 0x1Cu )
  {
    LODWORD(v58) = v59[8];
    NlPrintDomRoutine(
      0x100u,
      (struct _DOMAIN_INFO *)a1,
      L"NlGetIncomingPassword: %wZ: Flat Name length is bad %ld\n",
      &DestinationString,
      v58);
    v19 = -1073741595;
    goto LABEL_160;
  }
  memcpy_0(v72, *((const void **)v59 + 3), v59[8]);
  v72[(unsigned __int64)v55[8] >> 1] = 36;
  v57 = (v55[8] & 0xFFFE) + 2LL;
  if ( v57 >= 0x22 )
    _report_rangecheckfailure(v57, v56);
  *(unsigned __int16 *)((char *)v72 + v57) = 0;
  v44 = NlSamOpenNamedUser((struct _DOMAIN_INFO *)a1, v72, 0, 0, 0, v54, 0);
  v19 = v44;
  if ( v44 >= 0 )
  {
    v19 = 0;
    goto LABEL_73;
  }
  p_DestinationString = (struct _UNICODE_STRING *)v72;
  v46 = L"NlGetIncomingPassword: Can't NlSamOpenNamedUser for %ws 0x%lx.\n";
LABEL_121:
  LODWORD(v58) = v44;
  NlPrintDomRoutine(0x100u, (struct _DOMAIN_INFO *)a1, v46, p_DestinationString, v58);
LABEL_160:
  if ( v65 )
    SamrCloseHandle(&v65);
  if ( v59 )
    LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO(8);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1800354d8  push    rbp
0x1800354da  push    rbx
0x1800354db  push    rsi
0x1800354dc  push    rdi
0x1800354dd  push    r12
0x1800354df  push    r13
0x1800354e1  push    r14
0x1800354e3  push    r15
0x1800354e5  lea     rbp, [rsp-0A8h]
0x1800354ed  sub     rsp, 1A8h
0x1800354f4  mov     rax, cs:__security_cookie
0x1800354fb  xor     rax, rsp
0x1800354fe  mov     [rbp+0E0h+var_48], rax
0x180035505  mov     rax, [rbp+0E0h+arg_28]
0x18003550c  xor     r10d, r10d
0x18003550f  mov     r12, [rbp+0E0h+arg_40]
0x180035516  mov     r14, rdx
0x180035519  mov     rdx, [rbp+0E0h+arg_38]
0x180035520  mov     esi, r9d
0x180035523  mov     r9, [rbp+0E0h+arg_30]; char *
0x18003552a  mov     rdi, rcx
0x18003552d  mov     rcx, [rbp+0E0h+arg_58]
0x180035534  mov     r13, [rbp+0E0h+arg_48]
0x18003553b  mov     r15, [rbp+0E0h+arg_60]
0x180035542  mov     [rbp+0E0h+var_150], rax
0x180035546  mov     rax, [rbp+0E0h+arg_50]
0x18003554d  mov     [rbp+0E0h+var_140], rax
0x180035551  mov     [rsp+1E0h+var_180], r9
0x180035556  mov     [rbp+0E0h+var_148], rdx
0x18003555a  mov     [rsp+1E0h+var_170], rcx
0x18003555f  mov     [rbp+0E0h+var_160], r10
0x180035563  mov     [rbp+0E0h+var_158], r10
0x180035567  mov     [rsp+1E0h+var_1A0], r10
0x18003556c  test    rdx, rdx
0x18003556f  jz      short loc_180035574
0x180035571  mov     [rdx], r10d
0x180035574  test    r12, r12
0x180035577  jz      short loc_18003557D
0x180035579  mov     [r12], r10d
0x18003557d  test    r13, r13
0x180035580  jz      short loc_180035586
0x180035582  mov     [r13+0], r10d
0x180035586  test    rax, rax
0x180035589  jz      short loc_18003558E
0x18003558b  mov     [rax], r10
0x18003558e  test    rcx, rcx
0x180035591  jz      short loc_180035596
0x180035593  mov     [rcx], r10d
0x180035596  test    r15, r15
0x180035599  jz      short loc_1800355AD
0x18003559b  cmp     cs:?NlGlobalCDC@@3HA, r10d; int NlGlobalCDC
0x1800355a2  jnz     short loc_1800355C0
0x1800355a4  cmp     r8d, 7
0x1800355a8  jnz     short loc_1800355C0
0x1800355aa  mov     [r15], r10d
0x1800355ad  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800355b1  inc     rbx
0x1800355b4  cmp     [r14+rbx*2], r10w
0x1800355b9  jnz     short loc_1800355B1
0x1800355bb  cmp     ebx, 1
0x1800355be  jnb     short loc_1800355CA
0x1800355c0  mov     eax, 0C000000Dh
0x1800355c5  jmp     loc_180035F67
0x1800355ca  mov     ecx, r8d
0x1800355cd  mov     eax, 100h
0x1800355d2  mov     edx, 400h
0x1800355d7  mov     r11d, 2
0x1800355dd  test    r8d, r8d
0x1800355e0  jz      loc_1800357A5
0x1800355e6  sub     ecx, r11d
0x1800355e9  jz      loc_18003579C
0x1800355ef  sub     ecx, 1
0x1800355f2  jz      loc_180035795
0x1800355f8  sub     ecx, 1
0x1800355fb  jz      loc_18003578D
0x180035601  sub     ecx, r11d
0x180035604  jz      loc_180035786
0x18003560a  cmp     ecx, 1
0x18003560d  jz      short loc_18003561E
0x18003560f  mov     r9d, r8d
0x180035612  lea     r8, aNlgetincomingp_22; "NlGetIncomingPassword: Invalid channel "...
0x180035619  jmp     loc_1800357B7
0x18003561e  bts     esi, 14h
0x180035622  mov     [rsp+1E0h+var_188], r10d
0x180035627  mov     [rsp+1E0h+var_178], r10d
0x18003562c  cmp     esi, edx
0x18003562e  jz      loc_1800359D6
0x180035634  cmp     esi, 40h ; '@'
0x180035637  jz      loc_1800359D6
0x18003563d  lea     r12, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180035644  test    r9, r9
0x180035647  jz      short loc_180035663
0x180035649  mov     r8d, 5D6h; unsigned int
0x18003564f  lea     rcx, aOwfpreviouspas; "OwfPreviousPassword == NULL"
0x180035656  mov     rdx, r12; void *
0x180035659  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18003565e  mov     eax, 100h
0x180035663  cmp     esi, eax
0x180035665  jz      short loc_180035677
0x180035667  cmp     esi, 80h
0x18003566d  jz      short loc_180035677
0x18003566f  cmp     esi, 100000h
0x180035675  jnz     short loc_18003569C
0x180035677  cmp     ebx, 1
0x18003567a  jbe     loc_180035F62
0x180035680  lea     eax, [rbx-1]
0x180035683  lea     rcx, [r14+rax*2]
0x180035687  lea     rdx, asc_1800A5A84; "$"
0x18003568e  call    cs:__imp__o__wcsicmp
0x180035694  test    eax, eax
0x180035696  jnz     loc_180035F62
0x18003569c  mov     r13, [rbp+0E0h+var_148]
0x1800356a0  mov     rax, r15
0x1800356a3  neg     rax
0x1800356a6  mov     r8d, 23100000h; unsigned int
0x1800356ac  lea     rax, [rbp+0E0h+var_158]
0x1800356b0  mov     rdx, r14; unsigned __int16 *
0x1800356b3  mov     [rsp+1E0h+var_1B0], rax; struct _USER_INTERNAL6_INFORMATION **
0x1800356b8  sbb     r9d, r9d
0x1800356bb  lea     rax, [rbp+0E0h+var_160]
0x1800356bf  mov     [rsp+1E0h+var_1B8], r13; unsigned int *
0x1800356c4  and     r9d, 8000000h; unsigned int
0x1800356cb  mov     [rsp+1E0h+var_1C0], rax; void **
0x1800356d0  mov     rcx, rdi; struct _DOMAIN_INFO *
0x1800356d3  call    ?NlSamOpenNamedUser@@YAJPEAU_DOMAIN_INFO@@PEBGKKPEAPEAXPEAKPEAPEAU_USER_INTERNAL6_INFORMATION@@@Z; NlSamOpenNamedUser(_DOMAIN_INFO *,ushort const *,ulong,ulong,void * *,ulong *,_USER_INTERNAL6_INFORMATION * *)
0x1800356d8  mov     ebx, eax
0x1800356da  xor     eax, eax
0x1800356dc  test    ebx, ebx
0x1800356de  jns     loc_1800357CB
0x1800356e4  cmp     cs:?NlGlobalCDC@@3HA, eax; int NlGlobalCDC
0x1800356ea  jz      short loc_180035766
0x1800356ec  cmp     ebx, 0C0000371h
0x1800356f2  jnz     short loc_180035766
0x1800356f4  test    r15, r15
0x1800356f7  jz      short loc_18003570E
0x1800356f9  mov     r8d, 602h; unsigned int
0x1800356ff  lea     rcx, aCdcbranchid; "!CdcBranchId"
0x180035706  mov     rdx, r12; void *
0x180035709  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18003570e  xor     edx, edx; Val
0x180035710  lea     rcx, [rbp+0E0h+var_130]; void *
0x180035714  mov     r8d, 0C0h; Size
0x18003571a  call    memset_0
0x18003571f  xor     r9d, r9d; unsigned int
0x180035722  lea     rax, [rbp+0E0h+var_158]
0x180035726  mov     [rsp+1E0h+var_1B0], rax; struct _USER_INTERNAL6_INFORMATION **
0x18003572b  mov     rdx, r14; unsigned __int16 *
0x18003572e  lea     rax, [rbp+0E0h+var_160]
0x180035732  mov     [rsp+1E0h+var_1B8], r13; unsigned int *
0x180035737  mov     rcx, rdi; struct _DOMAIN_INFO *
0x18003573a  mov     [rsp+1E0h+var_1C0], rax; void **
0x18003573f  lea     r8d, [r9+4]; unsigned int
0x180035743  call    ?NlSamOpenNamedUser@@YAJPEAU_DOMAIN_INFO@@PEBGKKPEAPEAXPEAKPEAPEAU_USER_INTERNAL6_INFORMATION@@@Z; NlSamOpenNamedUser(_DOMAIN_INFO *,ushort const *,ulong,ulong,void * *,ulong *,_USER_INTERNAL6_INFORMATION * *)
0x180035748  test    eax, eax
0x18003574a  js      short loc_180035761
0x18003574c  mov     rcx, [rbp+0E0h+var_160]
0x180035750  lea     rdx, [rbp+0E0h+var_130]
0x180035754  mov     [rbp+0E0h+var_130], 880000h
0x18003575b  call    cs:__imp_SamIUpdateLogonStatistics
0x180035761  mov     ebx, 0C000018Bh
0x180035766  lea     r8, aNlgetincomingp_18; "NlGetIncomingPassword: Can't NlSamOpenN"...
0x18003576d  mov     dword ptr [rsp+1E0h+var_1C0], ebx
0x180035771  mov     r9, r14
0x180035774  mov     rdx, rdi; struct _DOMAIN_INFO *
0x180035777  mov     ecx, 100h; unsigned int
0x18003577c  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180035781  jmp     loc_180035F29
0x180035786  or      esi, eax
0x180035788  jmp     loc_180035622
0x18003578d  or      esi, 40h
0x180035790  jmp     loc_180035622
0x180035795  or      esi, edx
0x180035797  jmp     loc_180035622
0x18003579c  bts     esi, 7
0x1800357a0  jmp     loc_180035622
0x1800357a5  test    esi, esi
0x1800357a7  jnz     loc_180035622
0x1800357ad  xor     r9d, r9d
0x1800357b0  lea     r8, aNlgetincomingp_14; "NlGetIncomingPassword: Invalid AAC (%x)"...
0x1800357b7  mov     rdx, rdi; struct _DOMAIN_INFO *
0x1800357ba  mov     [rsp+1E0h+var_1C0], r14
0x1800357bf  mov     ecx, eax; unsigned int
0x1800357c1  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x1800357c6  jmp     loc_1800355C0
0x1800357cb  mov     rdx, [rbp+0E0h+var_158]
0x1800357cf  mov     eax, esi
0x1800357d1  mov     r8d, 1001D8h
0x1800357d7  mov     ecx, [rdx+118h]
0x1800357dd  and     eax, ecx
0x1800357df  test    r8d, eax
0x1800357e2  jnz     short loc_180035811
0x1800357e4  and     ecx, r8d
0x1800357e7  mov     [rsp+1E0h+var_1B8], r14
0x1800357ec  mov     r9d, ecx
0x1800357ef  mov     dword ptr [rsp+1E0h+var_1C0], esi
0x1800357f3  mov     ecx, 100h; unsigned int
0x1800357f8  lea     r8, aNlgetincomingp_3; "NlGetIncomingPassword: Invalid account "...
0x1800357ff  mov     rdx, rdi; struct _DOMAIN_INFO *
0x180035802  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180035807  mov     ebx, 0C0000064h
0x18003580c  jmp     loc_180035F29
0x180035811  xor     ebx, ebx
0x180035813  cmp     [rbp+0E0h+arg_20], ebx
0x180035819  jz      short loc_180035839
0x18003581b  test    cl, 1
0x18003581e  jz      short loc_180035839
0x180035820  mov     r9, r14
0x180035823  lea     r8, aNlgetincomingp_16; "NlGetIncomingPassword: %ws account is d"...
0x18003582a  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18003582d  mov     ecx, 100h; unsigned int
0x180035832  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180035837  jmp     short loc_180035807
0x180035839  test    r15, r15
0x18003583c  jz      loc_1800358C9
0x180035842  bt      ecx, 14h
0x180035846  jb      short loc_18003586E
0x180035848  mov     r8d, 65Dh; unsigned int
0x18003584e  lea     rcx, aFalse; "FALSE"
0x180035855  mov     rdx, r12; void *
0x180035858  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18003585d  lea     r8, aNlgetincomingp_8; "NlGetIncomingPassword: branch id reques"...
0x180035864  mov     ebx, 0C000000Dh
0x180035869  jmp     loc_18003576D
0x18003586e  lea     rsi, [rdx+274h]
0x180035875  mov     r8, r15; unsigned int *
0x180035878  mov     rdx, rsi; struct _GUID *
0x18003587b  mov     rcx, rdi; struct _DOMAIN_INFO *
0x18003587e  call    ?NlQuerySecondaryKrbTgtNum@@YAJPEAU_DOMAIN_INFO@@PEAU_GUID@@PEAK@Z; NlQuerySecondaryKrbTgtNum(_DOMAIN_INFO *,_GUID *,ulong *)
0x180035883  mov     ebx, eax
0x180035885  test    eax, eax
0x180035887  jns     short loc_1800358C3
0x180035889  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18003588c  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x180035890  mov     edi, 100h
0x180035895  lea     r8, aNlgetincomingp_21; "NlGetIncomingPassword: NlQuerySecondary"...
0x18003589c  mov     ecx, edi; unsigned int
0x18003589e  mov     r9, r14
0x1800358a1  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x1800358a6  lea     rdx, aUserallinfoKrb; "UserAllInfo->KrbTgtLinkObjectGuid: "
0x1800358ad  mov     ecx, edi; unsigned int
0x1800358af  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800358b4  mov     rdx, rsi; Uuid
0x1800358b7  mov     ecx, edi; unsigned int
0x1800358b9  call    ?NlpDumpGuid@@YAXKPEAU_GUID@@@Z; NlpDumpGuid(ulong,_GUID *)
0x1800358be  jmp     loc_180035F29
0x1800358c3  mov     rdx, [rbp+0E0h+var_158]
0x1800358c7  xor     ebx, ebx
0x1800358c9  mov     r13, [rbp+0E0h+var_150]
0x1800358cd  test    r13, r13
0x1800358d0  jz      loc_1800359CC
0x1800358d6  cmp     [rdx+139h], bl
0x1800358dc  jz      loc_1800359A2
0x1800358e2  mov     eax, 10h
0x1800358e7  cmp     [rdx+0E0h], ax
0x1800358ee  jnz     loc_1800359A2
0x1800358f4  mov     rax, [rdx+0E8h]
0x1800358fb  mov     [rsp+1E0h+var_188], 1
0x180035903  movups  xmm0, xmmword ptr [rax]
0x180035906  movdqu  xmmword ptr [r13+0], xmm0
0x18003590c  xor     edx, edx; Val
0x18003590e  lea     rcx, [rbp+0E0h+var_12C]; void *
0x180035912  mov     r8d, 0BCh; Size
0x180035918  call    memset_0
0x18003591d  mov     rcx, [rbp+0E0h+var_160]
0x180035921  lea     rdx, [rbp+0E0h+var_130]
0x180035925  mov     [rbp+0E0h+var_130], 40000000h
0x18003592c  call    cs:__imp_SamIUpdateLogonStatistics
0x180035932  test    eax, eax
0x180035934  jns     short loc_18003594D
0x180035936  mov     r9d, eax
0x180035939  lea     rdx, aNlgetincomingp_0; "NlGetIncomingPassword: Cannot set last "...
0x180035940  mov     r8, r14
0x180035943  mov     ecx, 100h; unsigned int
0x180035948  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003594d  mov     r15, [rsp+1E0h+var_180]
0x180035952  cmp     [rsp+1E0h+var_188], ebx
0x180035956  jnz     loc_180035EFA
0x18003595c  test    r13, r13
0x18003595f  jz      loc_180035EFA
0x180035965  xorps   xmm0, xmm0
0x180035968  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x18003596d  xor     edx, edx; SourceString
0x18003596f  movups  xmmword ptr [rsp+1E0h+DestinationString.Length], xmm0
0x180035974  call    cs:__imp_RtlInitUnicodeString
0x18003597a  mov     rdx, r13
0x18003597d  lea     rcx, [rsp+1E0h+DestinationString]
0x180035982  call    cs:__imp_SystemFunction007
0x180035988  mov     ebx, eax
0x18003598a  test    eax, eax
0x18003598c  jns     loc_180035EF8
0x180035992  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x180035996  lea     r8, aNlgetincomingp_20; "NlGetIncomingPassword: %ws: cannot RtlC"...
0x18003599d  jmp     loc_180035771
0x1800359a2  cmp     [rdx+138h], bl
0x1800359a8  jz      loc_18003590C
0x1800359ae  mov     r8, r14
0x1800359b1  lea     rdx, aNlgetincomingp_17; "NlGetIncomingPassword: No NT Password f"...
0x1800359b8  mov     ecx, 100h; unsigned int
0x1800359bd  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800359c2  mov     ebx, 0C0000022h
  ... truncated ...
```
