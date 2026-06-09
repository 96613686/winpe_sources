# NlChangePassword(_CLIENT_SESSION *,uchar,ulong *)

- ea: `0x180033a34`
- end: `0x18003449c`
- name: `?NlChangePassword@@YAJPEAU_CLIENT_SESSION@@EPEAK@Z`
- size: `2664`
- prototype: `__int64 __fastcall(struct _CLIENT_SESSION *, unsigned __int8, unsigned int *, char *)`
- caller_count: `4`
- callee_count: `27`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800536e4`
- `0x18005b7e0`
- `0x18006e960`
- `0x180073b6c`

## callees

- `0x180006860`
- `0x180007278`
- `0x18000d710`
- `0x18000e270`
- `0x18000e660`
- `0x180025708`
- `0x18002601c`
- `0x1800334d4`
- `0x180033a34`
- `0x1800344a4`
- `0x180034a40`
- `0x180036b78`
- `0x1800382f8`
- `0x180038ad0`
- `0x180039084`
- `0x180039150`
- `0x180039728`
- `0x18003e208`
- `0x18003e294`
- `0x18003e71c`
- `0x18003f684`
- `0x180053350`
- `0x18005ffb0`
- `0x1800675c0`
- `0x180068458`
- `0x1800694d0`
- `0x18006b580`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800343dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003440d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800343dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003440d`
- `ntdll!RtlLeaveCriticalSection` at `0x180033b1c`
- `ntdll!RtlLeaveCriticalSection` at `0x180033b33`
- `ntdll!RtlLeaveCriticalSection` at `0x180033ceb`
- `ntdll!RtlLeaveCriticalSection` at `0x180033d1e`
- `ntdll!RtlLeaveCriticalSection` at `0x180033f92`
- `ntdll!RtlLeaveCriticalSection` at `0x180033fc3`
- `ntdll!RtlLeaveCriticalSection` at `0x18003414d`
- `ntdll!RtlLeaveCriticalSection` at `0x180034173`
- `ntdll!RtlLeaveCriticalSection` at `0x180034223`
- `ntdll!RtlLeaveCriticalSection` at `0x18003426a`
- `ntdll!RtlLeaveCriticalSection` at `0x180033b1c`
- `ntdll!RtlLeaveCriticalSection` at `0x180033b33`
- `ntdll!RtlLeaveCriticalSection` at `0x180033ceb`
- `ntdll!RtlLeaveCriticalSection` at `0x180033d1e`
- `ntdll!RtlLeaveCriticalSection` at `0x180033f92`
- `ntdll!RtlLeaveCriticalSection` at `0x180033fc3`
- `ntdll!RtlLeaveCriticalSection` at `0x18003414d`
- `ntdll!RtlLeaveCriticalSection` at `0x180034173`
- `ntdll!RtlLeaveCriticalSection` at `0x180034223`
- `ntdll!RtlLeaveCriticalSection` at `0x18003426a`
- `ntdll!RtlEnterCriticalSection` at `0x180033ae6`
- `ntdll!RtlEnterCriticalSection` at `0x180033c9a`
- `ntdll!RtlEnterCriticalSection` at `0x180033e3c`
- `ntdll!RtlEnterCriticalSection` at `0x1800340df`
- `ntdll!RtlEnterCriticalSection` at `0x1800341ad`
- `ntdll!RtlEnterCriticalSection` at `0x180033ae6`
- `ntdll!RtlEnterCriticalSection` at `0x180033c9a`
- `ntdll!RtlEnterCriticalSection` at `0x180033e3c`
- `ntdll!RtlEnterCriticalSection` at `0x1800340df`
- `ntdll!RtlEnterCriticalSection` at `0x1800341ad`
- `ntdll!RtlInitUnicodeString` at `0x180033e88`
- `ntdll!RtlInitUnicodeString` at `0x180033f37`
- `ntdll!RtlInitUnicodeString` at `0x18003424d`
- `ntdll!RtlInitUnicodeString` at `0x180033e88`
- `ntdll!RtlInitUnicodeString` at `0x180033f37`
- `ntdll!RtlInitUnicodeString` at `0x18003424d`
- `ntdll!RtlEqualComputerName` at `0x180033c2b`
- `ntdll!RtlEqualComputerName` at `0x180033c6b`
- `ntdll!RtlEqualComputerName` at `0x180033c2b`
- `ntdll!RtlEqualComputerName` at `0x180033c6b`
- `CRYPTSP!SystemFunction007` at `0x180033fd1`
- `CRYPTSP!SystemFunction007` at `0x180033fd1`

## string_xrefs

- `0x180033ac5`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x180033b95`: `NlChangePassword: Can't become writer of client session.\n`
- `0x180033e66`: `NlChangePassword: Password already updated in secret\n`
- `0x180034071`: `NlChangePassword: Cannot change password on PDC managed service account 0x%lx\n`
- `0x1800341ba`: `NlChangePassword: Flag password updated on DC\n`

## pseudocode

```c
__int64 __fastcall NlChangePassword(struct _CLIENT_SESSION *a1, unsigned __int8 a2, unsigned int *a3, char *a4)
{
  unsigned int *v5; // r14
  struct _DOMAIN_INFO *v7; // rsi
  char v8; // r13
  unsigned int v9; // r12d
  int v10; // ecx
  bool v11; // zf
  __int64 v12; // rdi
  struct _RTL_CRITICAL_SECTION *v13; // rcx
  int OutgoingPassword; // eax
  struct _UNICODE_STRING *v15; // rcx
  struct _RTL_CRITICAL_SECTION *v16; // rcx
  struct _DOMAIN_INFO *DomainByServerName; // rax
  int v18; // r13d
  int v19; // eax
  __int64 v20; // r9
  unsigned int v21; // esi
  int v22; // eax
  unsigned int i; // eax
  unsigned __int64 v24; // rcx
  int v25; // eax
  int v26; // eax
  __int64 v27; // r8
  __int64 v28; // rcx
  int v29; // eax
  const unsigned __int16 *v30; // rdx
  int v31; // eax
  int v32; // eax
  unsigned int v33; // r9d
  unsigned int v34; // ecx
  int v35; // eax
  struct _RTL_CRITICAL_SECTION *v36; // rcx
  int v37; // r15d
  int v38; // eax
  unsigned int v39; // ecx
  unsigned int v40; // eax
  __int64 v41; // rcx
  struct _LM_OWF_PASSWORD *v42; // rax
  WCHAR *v43; // rax
  PUNICODE_STRING v44; // rcx
  __int64 Length; // rdx
  PWSTR Buffer; // rax
  PUNICODE_STRING v47; // rcx
  __int64 v48; // rdx
  PWSTR v49; // rax
  union _LARGE_INTEGER *v51; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v52[4]; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v53; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v54; // [rsp+4Ch] [rbp-B4h] BYREF
  struct _DOMAIN_INFO *v55; // [rsp+50h] [rbp-B0h]
  unsigned int *v56; // [rsp+58h] [rbp-A8h]
  PUNICODE_STRING ComputerName2; // [rsp+60h] [rbp-A0h] BYREF
  int v58; // [rsp+68h] [rbp-98h] BYREF
  int v59; // [rsp+6Ch] [rbp-94h]
  union _LARGE_INTEGER v60; // [rsp+70h] [rbp-90h] BYREF
  PUNICODE_STRING v61; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v63[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING v64; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING v65; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING v66; // [rsp+C0h] [rbp-40h] BYREF
  struct _LM_OWF_PASSWORD v67; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR SourceString[128]; // [rsp+E0h] [rbp-20h] BYREF

  v56 = a3;
  v5 = a3;
  *(_DWORD *)v52 = 0;
  v67 = 0;
  v7 = 0;
  v60.QuadPart = 0;
  v8 = 0;
  ComputerName2 = 0;
  v9 = 0;
  v61 = 0;
  v54 = 0;
  DestinationString = 0;
  v55 = 0;
  v65 = 0;
  v53 = 0;
  v64 = 0;
  v66 = 0;
  if ( !*((_DWORD *)a1 + 82) )
    NlAssertFailed(
      "ClientSession->CsReferenceCount > 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
      6398,
      a4);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
  v10 = *((_DWORD *)a1 + 73);
  if ( (v10 & 0x40000) != 0 )
  {
    v10 |= 2u;
    *((_DWORD *)a1 + 73) = v10;
  }
  v11 = (v10 & 2) == 0;
  v12 = 242;
  v13 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)a1 + 34) + 400LL);
  if ( v11 )
  {
    RtlLeaveCriticalSection(v13);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb>::GetImpl'::`2'::impl)
      && (unsigned int)(*((_DWORD *)a1 + 70) - 3) > 1 )
    {
      NlPrintCsRoutine(0x200u, a1, L"NlChangePassword: Calling into Kerberos.\n");
      *(_DWORD *)v52 = CallKerbChangeMachinePassword(a2);
      goto LABEL_100;
    }
    if ( !(unsigned int)NlTimeoutSetWriterClientSession(a1, dwMilliseconds) )
    {
      NlPrintCsRoutine(0x100u, a1, L"NlChangePassword: Can't become writer of client session.\n");
      *(_DWORD *)v52 = -1073741730;
LABEL_99:
      v12 = 242;
      goto LABEL_100;
    }
    v8 = 1;
    OutgoingPassword = NlGetOutgoingPassword(a1, &ComputerName2, &v61, &v54, &v60);
    *(_DWORD *)v52 = OutgoingPassword;
    if ( OutgoingPassword < 0 )
    {
      NlPrintCsRoutine(
        0x100u,
        a1,
        L"NlChangePassword: Cannot NlGetOutgoingPassword %lX\n",
        (unsigned int)OutgoingPassword);
      goto LABEL_99;
    }
    if ( !ComputerName2
      || !ComputerName2->Length
      || (v15 = (struct _UNICODE_STRING *)(*((_QWORD *)a1 + 34) + 256LL),
          v59 = 0,
          RtlEqualComputerName(v15, ComputerName2)) )
    {
      v9 = 1;
      v59 = 1;
      NlPrintCsRoutine(0x200u, a1, L"NlChangePassword: New LsaSecret is default value.\n");
    }
    if ( !v61 || !v61->Length || RtlEqualComputerName((PUNICODE_STRING)(*((_QWORD *)a1 + 34) + 256LL), v61) )
    {
      LODWORD(v7) = 1;
      NlPrintCsRoutine(0x200u, a1, L"NlChangePassword: Old LsaSecret is default value.\n");
    }
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
    v60.QuadPart += *((_QWORD *)a1 + 62);
    if ( (*((_BYTE *)a1 + 292) & 1) == 0
      && !NlTimeHasElapsedEx(&v60, &stru_1800F12F0, &v53)
      && !v9
      && !(_DWORD)v7
      && !a2 )
    {
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
      v9 = v53;
      *(_DWORD *)v52 = 0;
      v7 = 0;
LABEL_98:
      v5 = v56;
      goto LABEL_99;
    }
    v16 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)a1 + 34) + 400LL);
    *((_QWORD *)a1 + 62) = 0;
    RtlLeaveCriticalSection(v16);
    v53 = 0;
    v9 = 0;
    NlPrintCsRoutine(0x200u, a1, L"NlChangePassword: Doing it.\n");
    if ( (*((_DWORD *)a1 + 73) & 0x20000) != 0 )
    {
      DomainByServerName = NlFindDomainByServerName(0);
      v55 = DomainByServerName;
      v7 = DomainByServerName;
      if ( DomainByServerName && (unsigned int)(*((_DWORD *)DomainByServerName + 147) - 1) <= 1 )
      {
        v18 = 1;
        goto LABEL_43;
      }
    }
    else
    {
      v7 = 0;
    }
    v18 = 0;
    if ( *((_DWORD *)a1 + 70) != 6 || *(_DWORD *)(*((_QWORD *)a1 + 34) + 588LL) != 1 )
    {
      if ( *((_DWORD *)a1 + 71) == 2 )
      {
        v19 = NlConfirmCapabilities(a1);
        v20 = *((_QWORD *)a1 + 63);
        *(_DWORD *)v52 = v19;
        if ( v19 >= 0 )
        {
          NlPrintCsRoutine(0x200u, a1, L"NlChangePassword: Successful response from DC %ws\n", v20);
        }
        else
        {
          LODWORD(v51) = v19;
          NlPrintCsRoutine(0x100u, a1, L"NlChangePassword: Unsuccessful response from DC %ws 0x%lx\n", v20, v51);
          *(_DWORD *)v52 = -1073741730;
          NlSetStatusClientSession(a1, -1073741730);
        }
      }
      if ( *((int *)a1 + 72) < 0 )
      {
        if ( NlTimeToReauthenticate(a1) )
        {
          *(_DWORD *)v52 = NlSessionSetupEx(a1);
          if ( *(int *)v52 >= 0 )
            goto LABEL_43;
        }
        else
        {
          *(_DWORD *)v52 = *((_DWORD *)a1 + 72);
        }
LABEL_97:
        v8 = 1;
        goto LABEL_98;
      }
    }
LABEL_43:
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
    if ( ComputerName2 && ComputerName2->Length >= 0xF0u )
      *((_DWORD *)a1 + 73) &= ~1u;
    if ( (*((_BYTE *)a1 + 292) & 1) != 0 )
    {
      NlPrintCsRoutine(0x200u, a1, L"NlChangePassword: Password already updated in secret\n");
      if ( ComputerName2 )
        DestinationString = *ComputerName2;
      else
        RtlInitUnicodeString(&DestinationString, 0);
    }
    else
    {
      v58 = 0;
      v21 = 14;
      v22 = I_NetLogonMixedDomain(&v58);
      *(_DWORD *)v52 = v22;
      if ( v22 < 0 )
      {
        NlPrintRoutine(
          0x100u,
          L"Falling back to short password because I_NetLogonMixedDomain failed with ntstatus 0x%x.\n",
          (unsigned int)v22);
      }
      else if ( !v58 )
      {
        v21 = 120;
      }
      if ( !NlGenerateRandomBits((BYTE *)SourceString, 2 * v21) )
        NlPrintRoutine(0x100u, L"Can't NlGenerateRandomBits for clear password\n");
      for ( i = 0; i < v21; ++i )
      {
        if ( !SourceString[i] )
          SourceString[i] = 1;
      }
      v24 = 2LL * v21;
      if ( v24 >= 0xF2 )
        _report_rangecheckfailure(v24, 1);
      SourceString[v21] = 0;
      RtlInitUnicodeString(&DestinationString, SourceString);
      ++v54;
      v25 = NlSetOutgoingPassword(a1, &DestinationString, ComputerName2, v54, v54 - 1);
      *(_DWORD *)v52 = v25;
      if ( v25 < 0 )
      {
        NlPrintCsRoutine(0x100u, a1, L"NlChangePassword: Cannot NlSetOutgoingPassword %lX\n", (unsigned int)v25);
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
        goto LABEL_96;
      }
      *((_DWORD *)a1 + 73) |= 1u;
      v9 = 1;
      NlPrintCsRoutine(0x200u, a1, L"NlChangePassword: Flag password changed in LsaSecret\n");
    }
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
    v26 = SystemFunction007(&DestinationString, &v67);
    *(_DWORD *)v52 = v26;
    if ( v26 < 0 )
    {
      NlPrintCsRoutine(0x100u, a1, L"NlChangePassword: Cannot RtlCalculateNtOwfPassword %lX\n", (unsigned int)v26);
LABEL_95:
      v9 = v53;
      goto LABEL_96;
    }
    v27 = *((unsigned int *)a1 + 70);
    if ( (_DWORD)v27 == 6 )
    {
      v28 = *((_QWORD *)a1 + 34);
      if ( *(_DWORD *)(v28 + 588) == 1 )
      {
        v29 = NlSamChangePasswordNamedUser(
                (struct _DOMAIN_INFO *)v28,
                *((const unsigned __int16 **)a1 + 25),
                &DestinationString,
                &v67);
        *(_DWORD *)v52 = v29;
        if ( v29 < 0 )
        {
          NlPrintCsRoutine(
            0x100u,
            a1,
            L"NlChangePassword: Cannot change password on PDC local user account 0x%lx\n",
            (unsigned int)v29);
          goto LABEL_95;
        }
LABEL_83:
        v37 = v59;
        while ( 1 )
        {
          *(_OWORD *)v63 = 0;
          if ( *(int *)v52 < 0 )
          {
            NlSetStatusClientSession(a1, *(int *)v52);
            v63[0] = *((unsigned __int16 **)a1 + 25);
            v63[1] = (unsigned __int16 *)*(int *)v52;
            NlpWriteEventlogEx(0xC98u, 1u, 0x80000000, 0xFFFFFFFF, v63, 2u, v52, 4u);
            goto LABEL_95;
          }
          RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
          *((_DWORD *)a1 + 73) &= ~1u;
          NlPrintCsRoutine(0x200u, a1, L"NlChangePassword: Flag password updated on DC\n");
          if ( !v37 )
            break;
          NlPrintCsRoutine(0x200u, a1, L"NlChangePassword: Setting LsaSecret old password to same as new password\n");
          v38 = NlSetOutgoingPassword(a1, &DestinationString, &DestinationString, v54, v54);
          *(_DWORD *)v52 = v38;
          if ( v38 >= 0 )
            break;
          NlPrintCsRoutine(
            0x100u,
            a1,
            L"NlChangePassword: Cannot LsarSetSecret to set old password %lX\n",
            (unsigned int)v38);
          RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
        }
        NlDuplicateUnicodeString((struct _UNICODE_STRING *)(*((_QWORD *)a1 + 34) + 56LL), &v64);
        RtlInitUnicodeString(&v66, *((PCWSTR *)a1 + 25));
        NlDuplicateUnicodeString(&v66, &v65);
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
        v9 = -2;
        if ( (unsigned int)dword_1800F1184 <= 0x31 )
          v9 = 86400000 * dword_1800F1184;
        if ( (*((_DWORD *)a1 + 73) & 0x20000) != 0 )
        {
          NlChangeCachedPasswords(&v64, &v65, &DestinationString);
          v39 = 5824;
          v63[0] = *((unsigned __int16 **)a1 + 25);
          v63[1] = *((unsigned __int16 **)a1 + 63);
          v40 = 2;
        }
        else
        {
          v39 = 5823;
          v63[0] = *((unsigned __int16 **)a1 + 63);
          v40 = 1;
        }
        NlpWriteEventlogEx(v39, 4u, 0, 0xFFFFFFFF, v63, v40, 0, 0);
        goto LABEL_96;
      }
    }
    v30 = (const unsigned __int16 *)*((_QWORD *)a1 + 25);
    if ( v18 )
    {
      v31 = NlSamChangePasswordNamedUser(v55, v30, &DestinationString, &v67);
      *(_DWORD *)v52 = v31;
      if ( v31 < 0 )
      {
        NlPrintCsRoutine(
          0x100u,
          a1,
          L"NlChangePassword: Cannot change password on PDC managed service account 0x%lx\n",
          (unsigned int)v31);
        goto LABEL_95;
      }
      goto LABEL_83;
    }
    v32 = NlChangePasswordHigher(a1, v30, v27, &v67, &DestinationString, &v54);
    *(_DWORD *)v52 = v32;
    if ( v32 == -1073741790 || v32 == -1073741147 )
      goto LABEL_95;
    if ( v32 != -1073741718 )
      goto LABEL_83;
    NlPrintCsRoutine(0x200u, a1, L"NlChangePassword: DC refused to change password\n");
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
    if ( v9 )
    {
      NlPrintCsRoutine(0x200u, a1, L"NlChangePassword: undoing LSA secret change.\n");
      v11 = v54 == 1;
      v33 = v54 - 1;
      v54 = v33;
      v34 = v33 - 1;
      if ( v11 )
        v34 = 0;
      v35 = NlSetOutgoingPassword(a1, ComputerName2, v61, v33, v34);
      *(_DWORD *)v52 = v35;
      if ( v35 < 0 )
      {
        NlPrintCsRoutine(0x100u, a1, L"NlChangePassword: Cannot undo NlSetOutgoingPassword %lX\n", (unsigned int)v35);
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
        goto LABEL_83;
      }
      *((_DWORD *)a1 + 73) &= ~1u;
    }
    v36 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)a1 + 34);
    v9 = -1;
    *((_DWORD *)a1 + 73) |= 2u;
    RtlLeaveCriticalSection(v36 + 10);
    *(_DWORD *)v52 = 0;
LABEL_96:
    v7 = v55;
    goto LABEL_97;
  }
  RtlLeaveCriticalSection(v13);
  v9 = -1;
  *(_DWORD *)v52 = 0;
LABEL_100:
  v41 = 16;
  v42 = &v67;
  do
  {
    v42->data[0].data[0] = 0;
    v42 = (struct _LM_OWF_PASSWORD *)((char *)v42 + 1);
    --v41;
  }
  while ( v41 );
  v43 = SourceString;
  do
  {
    *(_BYTE *)v43 = 0;
    v43 = (WCHAR *)((char *)v43 + 1);
    --v12;
  }
  while ( v12 );
  if ( v7 )
    NlDereferenceDomain(v7);
  v44 = ComputerName2;
  if ( ComputerName2 )
  {
    Length = ComputerName2->Length;
    Buffer = ComputerName2->Buffer;
    if ( ComputerName2->Length )
    {
      do
      {
        *(_BYTE *)Buffer = 0;
        Buffer = (PWSTR)((char *)Buffer + 1);
        --Length;
      }
      while ( Length );
      v44 = ComputerName2;
    }
    LocalFree(v44);
  }
  v47 = v61;
  if ( v61 )
  {
    v48 = v61->Length;
    v49 = v61->Buffer;
    if ( v61->Length )
    {
      do
      {
        *(_BYTE *)v49 = 0;
        v49 = (PWSTR)((char *)v49 + 1);
        --v48;
      }
      while ( v48 );
      v47 = v61;
    }
    LocalFree(v47);
  }
  if ( v8 )
  {
    if ( *((int *)a1 + 72) >= 0 && (*((_DWORD *)a1 + 73) & 0x20000) != 0 )
      NlSetStatusClientSession(a1, -1073741730);
    NlResetWriterClientSession(a1);
  }
  if ( v64.Buffer )
    NlFreeUnicodeString(&v64);
  if ( v65.Buffer )
    NlFreeUnicodeString(&v65);
  if ( v5 )
    *v5 = v9;
  return *(unsigned int *)v52;
}

```

## disassembly

```asm
0x180033a34  mov     [rsp-8+arg_18], rbx
0x180033a39  push    rbp
0x180033a3a  push    rsi
0x180033a3b  push    rdi
0x180033a3c  push    r12
0x180033a3e  push    r13
0x180033a40  push    r14
0x180033a42  push    r15
0x180033a44  lea     rbp, [rsp-0F0h]
0x180033a4c  sub     rsp, 1F0h
0x180033a53  mov     rax, cs:__security_cookie
0x180033a5a  xor     rax, rsp
0x180033a5d  mov     [rbp+120h+var_40], rax
0x180033a64  xorps   xmm0, xmm0
0x180033a67  mov     [rsp+220h+var_1C8], r8
0x180033a6c  mov     rbx, rcx
0x180033a6f  xorps   xmm1, xmm1
0x180033a72  xor     ecx, ecx
0x180033a74  mov     r14, r8
0x180033a77  mov     r15b, dl
0x180033a7a  mov     dword ptr [rsp+220h+var_1DC], ecx
0x180033a7e  movdqu  xmmword ptr [rbp+120h+var_150.data.data], xmm0
0x180033a83  mov     esi, ecx
0x180033a85  mov     qword ptr [rsp+220h+var_1B0], rcx
0x180033a8a  mov     r13b, cl
0x180033a8d  mov     [rsp+220h+ComputerName2], rcx
0x180033a92  mov     r12d, ecx
0x180033a95  mov     [rsp+220h+var_1A8], rcx
0x180033a9a  mov     [rsp+220h+var_1D4], ecx
0x180033a9e  movups  xmmword ptr [rbp+120h+DestinationString.Length], xmm0
0x180033aa2  mov     [rsp+220h+var_1D0], rcx
0x180033aa7  movups  xmmword ptr [rbp+120h+var_170.Length], xmm1
0x180033aab  mov     [rsp+220h+var_1D8], ecx
0x180033aaf  movups  xmmword ptr [rbp+120h+var_180.Length], xmm0
0x180033ab3  movups  xmmword ptr [rbp+120h+var_160.Length], xmm1
0x180033ab7  cmp     [rbx+148h], ecx
0x180033abd  ja      short loc_180033AD8
0x180033abf  mov     r8d, 18FEh; unsigned int
0x180033ac5  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180033acc  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x180033ad3  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180033ad8  mov     rcx, [rbx+110h]
0x180033adf  add     rcx, 190h; CriticalSection
0x180033ae6  call    cs:__imp_RtlEnterCriticalSection
0x180033aec  mov     ecx, [rbx+124h]
0x180033af2  mov     edx, 2
0x180033af7  bt      ecx, 12h
0x180033afb  jnb     short loc_180033B05
0x180033afd  or      ecx, edx
0x180033aff  mov     [rbx+124h], ecx
0x180033b05  mov     rax, [rbx+110h]
0x180033b0c  test    dl, cl
0x180033b0e  mov     edi, 0F2h
0x180033b13  lea     rcx, [rax+190h]; CriticalSection
0x180033b1a  jz      short loc_180033B33
0x180033b1c  call    cs:__imp_RtlLeaveCriticalSection
0x180033b22  or      r12d, 0FFFFFFFFh
0x180033b26  xor     r15d, r15d
0x180033b29  mov     dword ptr [rsp+220h+var_1DC], r15d
0x180033b2e  jmp     loc_18003437E
0x180033b33  call    cs:__imp_RtlLeaveCriticalSection
0x180033b39  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb> `wil::Feature<__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb>::GetImpl(void)'::`2'::impl
0x180033b40  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb>::__private_IsEnabled(void)
0x180033b45  test    al, al
0x180033b47  jz      short loc_180033B83
0x180033b49  mov     eax, [rbx+118h]
0x180033b4f  mov     edx, 1
0x180033b54  sub     eax, 3
0x180033b57  cmp     eax, edx
0x180033b59  jbe     short loc_180033B83
0x180033b5b  lea     r8, aNlchangepasswo_18; "NlChangePassword: Calling into Kerberos"...
0x180033b62  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180033b65  mov     ecx, 200h; unsigned int
0x180033b6a  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180033b6f  mov     cl, r15b; unsigned __int8
0x180033b72  call    ?CallKerbChangeMachinePassword@@YAJE@Z; CallKerbChangeMachinePassword(uchar)
0x180033b77  mov     dword ptr [rsp+220h+var_1DC], eax
0x180033b7b  xor     r15d, r15d
0x180033b7e  jmp     loc_18003437E
0x180033b83  mov     edx, cs:dwMilliseconds; dwMilliseconds
0x180033b89  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180033b8c  call    ?NlTimeoutSetWriterClientSession@@YAHPEAU_CLIENT_SESSION@@K@Z; NlTimeoutSetWriterClientSession(_CLIENT_SESSION *,ulong)
0x180033b91  test    eax, eax
0x180033b93  jnz     short loc_180033BB9
0x180033b95  lea     r8, aNlchangepasswo_6; "NlChangePassword: Can't become writer o"...
0x180033b9c  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180033b9f  mov     ecx, 100h; unsigned int
0x180033ba4  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180033ba9  mov     dword ptr [rsp+220h+var_1DC], 0C000005Eh
0x180033bb1  xor     r15d, r15d
0x180033bb4  jmp     loc_180034379
0x180033bb9  lea     rax, [rsp+220h+var_1B0]
0x180033bbe  mov     r13b, 1
0x180033bc1  lea     r9, [rsp+220h+var_1D4]; unsigned int *
0x180033bc6  mov     [rsp+220h+var_1E0], r13b
0x180033bcb  lea     r8, [rsp+220h+var_1A8]; struct _UNICODE_STRING **
0x180033bd0  mov     [rsp+220h+var_200], rax; union _LARGE_INTEGER *
0x180033bd5  lea     rdx, [rsp+220h+ComputerName2]; struct _UNICODE_STRING **
0x180033bda  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180033bdd  call    ?NlGetOutgoingPassword@@YAJPEAU_CLIENT_SESSION@@PEAPEAU_UNICODE_STRING@@1PEAKPEAT_LARGE_INTEGER@@@Z; NlGetOutgoingPassword(_CLIENT_SESSION *,_UNICODE_STRING * *,_UNICODE_STRING * *,ulong *,_LARGE_INTEGER *)
0x180033be2  mov     dword ptr [rsp+220h+var_1DC], eax
0x180033be6  test    eax, eax
0x180033be8  jns     short loc_180033C03
0x180033bea  mov     r9d, eax
0x180033bed  lea     r8, aNlchangepasswo_11; "NlChangePassword: Cannot NlGetOutgoingP"...
0x180033bf4  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180033bf7  mov     ecx, 100h; unsigned int
0x180033bfc  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180033c01  jmp     short loc_180033BB1
0x180033c03  mov     rdx, [rsp+220h+ComputerName2]; ComputerName2
0x180033c08  mov     edi, 100h
0x180033c0d  mov     r14d, 200h
0x180033c13  test    rdx, rdx
0x180033c16  jz      short loc_180033C35
0x180033c18  cmp     [rdx], si
0x180033c1b  jz      short loc_180033C35
0x180033c1d  mov     rcx, [rbx+110h]
0x180033c24  add     rcx, rdi; ComputerName1
0x180033c27  mov     [rsp+220h+var_1B4], esi
0x180033c2b  call    cs:__imp_RtlEqualComputerName
0x180033c31  test    al, al
0x180033c33  jz      short loc_180033C52
0x180033c35  mov     r12d, 1
0x180033c3b  lea     r8, aNlchangepasswo_14; "NlChangePassword: New LsaSecret is defa"...
0x180033c42  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180033c45  mov     [rsp+220h+var_1B4], r12d
0x180033c4a  mov     ecx, r14d; unsigned int
0x180033c4d  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180033c52  mov     rdx, [rsp+220h+var_1A8]; ComputerName2
0x180033c57  test    rdx, rdx
0x180033c5a  jz      short loc_180033C75
0x180033c5c  cmp     [rdx], si
0x180033c5f  jz      short loc_180033C75
0x180033c61  mov     rcx, [rbx+110h]
0x180033c68  add     rcx, rdi; ComputerName1
0x180033c6b  call    cs:__imp_RtlEqualComputerName
0x180033c71  test    al, al
0x180033c73  jz      short loc_180033C8C
0x180033c75  lea     r8, aNlchangepasswo_0; "NlChangePassword: Old LsaSecret is defa"...
0x180033c7c  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180033c7f  mov     ecx, r14d; unsigned int
0x180033c82  mov     esi, 1
0x180033c87  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180033c8c  mov     rcx, [rbx+110h]
0x180033c93  add     rcx, 190h; CriticalSection
0x180033c9a  call    cs:__imp_RtlEnterCriticalSection
0x180033ca0  mov     rax, [rbx+1F0h]
0x180033ca7  add     qword ptr [rsp+220h+var_1B0], rax
0x180033cac  test    [rbx+124h], r13b
0x180033cb3  jnz     short loc_180033D06
0x180033cb5  lea     r8, [rsp+220h+var_1D8]; unsigned int *
0x180033cba  lea     rdx, stru_1800F12F0; union _LARGE_INTEGER *
0x180033cc1  lea     rcx, [rsp+220h+var_1B0]; union _LARGE_INTEGER *
0x180033cc6  call    ?NlTimeHasElapsedEx@@YAEPEAT_LARGE_INTEGER@@0PEAK@Z; NlTimeHasElapsedEx(_LARGE_INTEGER *,_LARGE_INTEGER *,ulong *)
0x180033ccb  test    al, al
0x180033ccd  jnz     short loc_180033D06
0x180033ccf  test    r12d, r12d
0x180033cd2  jnz     short loc_180033D06
0x180033cd4  test    esi, esi
0x180033cd6  jnz     short loc_180033D06
0x180033cd8  test    r15b, r15b
0x180033cdb  jnz     short loc_180033D06
0x180033cdd  mov     rcx, [rbx+110h]
0x180033ce4  add     rcx, 190h; CriticalSection
0x180033ceb  call    cs:__imp_RtlLeaveCriticalSection
0x180033cf1  mov     r12d, [rsp+220h+var_1D8]
0x180033cf6  xor     r15d, r15d
0x180033cf9  mov     dword ptr [rsp+220h+var_1DC], r15d
0x180033cfe  mov     esi, r15d
0x180033d01  jmp     loc_180034374
0x180033d06  mov     rcx, [rbx+110h]
0x180033d0d  xor     r15d, r15d
0x180033d10  add     rcx, 190h; CriticalSection
0x180033d17  mov     [rbx+1F0h], r15
0x180033d1e  call    cs:__imp_RtlLeaveCriticalSection
0x180033d24  lea     r8, aNlchangepasswo_16; "NlChangePassword: Doing it.\n"
0x180033d2b  mov     [rsp+220h+var_1D8], r15d
0x180033d30  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180033d33  mov     ecx, r14d; unsigned int
0x180033d36  mov     r12d, r15d
0x180033d39  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180033d3e  test    dword ptr [rbx+124h], 20000h
0x180033d48  jz      short loc_180033D76
0x180033d4a  xor     ecx, ecx; unsigned __int16 *
0x180033d4c  call    ?NlFindDomainByServerName@@YAPEAU_DOMAIN_INFO@@PEAG@Z; NlFindDomainByServerName(ushort *)
0x180033d51  mov     [rsp+220h+var_1D0], rax
0x180033d56  mov     rsi, rax
0x180033d59  lea     edx, [r15+1]
0x180033d5d  test    rax, rax
0x180033d60  jz      short loc_180033D7E
0x180033d62  mov     ecx, [rax+24Ch]
0x180033d68  sub     ecx, edx
0x180033d6a  cmp     ecx, edx
0x180033d6c  ja      short loc_180033D7E
0x180033d6e  mov     r13d, edx
0x180033d71  jmp     loc_180033E2E
0x180033d76  mov     rsi, r12
0x180033d79  mov     edx, 1
0x180033d7e  cmp     dword ptr [rbx+118h], 6
0x180033d85  mov     r13d, r15d
0x180033d88  jnz     short loc_180033D9D
0x180033d8a  mov     rax, [rbx+110h]
0x180033d91  cmp     [rax+24Ch], edx
0x180033d97  jz      loc_180033E2E
0x180033d9d  cmp     dword ptr [rbx+11Ch], 2
0x180033da4  jnz     short loc_180033DF6
0x180033da6  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180033da9  call    ?NlConfirmCapabilities@@YAJPEAU_CLIENT_SESSION@@@Z; NlConfirmCapabilities(_CLIENT_SESSION *)
0x180033dae  mov     r9, [rbx+1F8h]
0x180033db5  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180033db8  mov     dword ptr [rsp+220h+var_1DC], eax
0x180033dbc  test    eax, eax
0x180033dbe  jns     short loc_180033DE7
0x180033dc0  lea     r8, aNlchangepasswo_3; "NlChangePassword: Unsuccessful response"...
0x180033dc7  mov     dword ptr [rsp+220h+var_200], eax
0x180033dcb  mov     ecx, edi; unsigned int
0x180033dcd  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180033dd2  mov     eax, 0C000005Eh
0x180033dd7  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180033dda  mov     edx, eax; int
0x180033ddc  mov     dword ptr [rsp+220h+var_1DC], eax
0x180033de0  call    ?NlSetStatusClientSession@@YAXPEAU_CLIENT_SESSION@@J@Z; NlSetStatusClientSession(_CLIENT_SESSION *,long)
0x180033de5  jmp     short loc_180033DF6
0x180033de7  lea     r8, aNlchangepasswo_12; "NlChangePassword: Successful response f"...
0x180033dee  mov     ecx, r14d; unsigned int
0x180033df1  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180033df6  cmp     [rbx+120h], r15d
0x180033dfd  jge     short loc_180033E2E
0x180033dff  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180033e02  call    ?NlTimeToReauthenticate@@YAEPEAU_CLIENT_SESSION@@@Z; NlTimeToReauthenticate(_CLIENT_SESSION *)
0x180033e07  test    al, al
0x180033e09  jnz     short loc_180033E1A
0x180033e0b  mov     eax, [rbx+120h]
0x180033e11  mov     dword ptr [rsp+220h+var_1DC], eax
0x180033e15  jmp     loc_18003436F
0x180033e1a  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180033e1d  call    ?NlSessionSetupEx@@YAJPEAU_CLIENT_SESSION@@@Z; NlSessionSetupEx(_CLIENT_SESSION *)
0x180033e22  mov     dword ptr [rsp+220h+var_1DC], eax
0x180033e26  test    eax, eax
0x180033e28  js      loc_18003436F
0x180033e2e  mov     rcx, [rbx+110h]
0x180033e35  add     rcx, 190h; CriticalSection
0x180033e3c  call    cs:__imp_RtlEnterCriticalSection
0x180033e42  mov     rax, [rsp+220h+ComputerName2]
0x180033e47  test    rax, rax
0x180033e4a  jz      short loc_180033E5D
0x180033e4c  mov     ecx, 0F0h
0x180033e51  cmp     [rax], cx
0x180033e54  jb      short loc_180033E5D
0x180033e56  and     dword ptr [rbx+124h], 0FFFFFFFEh
0x180033e5d  test    byte ptr [rbx+124h], 1
0x180033e64  jz      short loc_180033EA0
0x180033e66  lea     r8, aNlchangepasswo_15; "NlChangePassword: Password already upda"...
0x180033e6d  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180033e70  mov     ecx, r14d; unsigned int
0x180033e73  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180033e78  mov     rax, [rsp+220h+ComputerName2]
0x180033e7d  test    rax, rax
0x180033e80  jnz     short loc_180033E93
0x180033e82  xor     edx, edx; SourceString
0x180033e84  lea     rcx, [rbp+120h+DestinationString]; DestinationString
0x180033e88  call    cs:__imp_RtlInitUnicodeString
0x180033e8e  jmp     loc_180033FB5
0x180033e93  movups  xmm0, xmmword ptr [rax]
0x180033e96  movdqu  xmmword ptr [rbp+120h+DestinationString.Length], xmm0
0x180033e9b  jmp     loc_180033FB5
0x180033ea0  lea     rcx, [rsp+220h+var_1B8]
0x180033ea5  mov     [rsp+220h+var_1B8], r15d
0x180033eaa  mov     esi, 0Eh
0x180033eaf  call    I_NetLogonMixedDomain
0x180033eb4  mov     dword ptr [rsp+220h+var_1DC], eax
0x180033eb8  test    eax, eax
0x180033eba  js      short loc_180033ECA
0x180033ebc  cmp     [rsp+220h+var_1B8], r15d
0x180033ec1  jnz     short loc_180033EDB
0x180033ec3  mov     esi, 78h ; 'x'
0x180033ec8  jmp     short loc_180033EDB
0x180033eca  mov     r8d, eax
0x180033ecd  lea     rdx, aFallingBackToS; "Falling back to short password because "...
0x180033ed4  mov     ecx, edi; unsigned int
0x180033ed6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180033edb  lea     edx, [rsi+rsi]; unsigned int
0x180033ede  lea     rcx, [rbp+120h+SourceString]; pbBuffer
0x180033ee2  call    ?NlGenerateRandomBits@@YAEPEAEK@Z; NlGenerateRandomBits(uchar *,ulong)
0x180033ee7  test    al, al
0x180033ee9  jnz     short loc_180033EF9
0x180033eeb  lea     rdx, aCanTNlgenerate_1; "Can't NlGenerateRandomBits for clear pa"...
0x180033ef2  mov     ecx, edi; unsigned int
0x180033ef4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180033ef9  mov     eax, r15d
0x180033efc  mov     edx, 1
0x180033f01  mov     ecx, eax
0x180033f03  cmp     [rbp+rcx*2+120h+SourceString], r15w
0x180033f09  jnz     short loc_180033F10
0x180033f0b  mov     [rbp+rcx*2+120h+SourceString], dx
0x180033f10  add     eax, edx
0x180033f12  cmp     eax, esi
0x180033f14  jb      short loc_180033F01
0x180033f16  mov     eax, esi
0x180033f18  lea     rcx, [rax+rax]
  ... truncated ...
```
