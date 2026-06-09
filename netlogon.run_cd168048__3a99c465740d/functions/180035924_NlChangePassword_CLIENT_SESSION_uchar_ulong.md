# NlChangePassword(_CLIENT_SESSION *,uchar,ulong *)

- ea: `0x180035924`
- end: `0x180036417`
- name: `?NlChangePassword@@YAJPEAU_CLIENT_SESSION@@EPEAK@Z`
- size: `2803`
- prototype: `__int64 __fastcall(struct _CLIENT_SESSION *, unsigned __int8, unsigned int *)`
- caller_count: `4`
- callee_count: `27`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800570c0`
- `0x18005fa30`
- `0x180073c20`
- `0x1800792d4`

## callees

- `0x180006a94`
- `0x180007518`
- `0x18000dd00`
- `0x18000e910`
- `0x18000ed00`
- `0x1800267ec`
- `0x1800271d4`
- `0x18003537c`
- `0x180035924`
- `0x180036420`
- `0x1800369d0`
- `0x180038cb8`
- `0x18003a51c`
- `0x18003ad18`
- `0x18003b32c`
- `0x18003b3e4`
- `0x18003ba18`
- `0x180040928`
- `0x1800409c4`
- `0x180040f18`
- `0x180041fbc`
- `0x180056cec`
- `0x1800644a0`
- `0x18006c2e8`
- `0x18006d2b0`
- `0x18006e444`
- `0x180070620`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003634a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036381`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003634a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036381`
- `ntdll!RtlLeaveCriticalSection` at `0x180035a12`
- `ntdll!RtlLeaveCriticalSection` at `0x180035a2f`
- `ntdll!RtlLeaveCriticalSection` at `0x180035bff`
- `ntdll!RtlLeaveCriticalSection` at `0x180035c38`
- `ntdll!RtlLeaveCriticalSection` at `0x180035ec4`
- `ntdll!RtlLeaveCriticalSection` at `0x180035efb`
- `ntdll!RtlLeaveCriticalSection` at `0x180036097`
- `ntdll!RtlLeaveCriticalSection` at `0x1800360c3`
- `ntdll!RtlLeaveCriticalSection` at `0x18003617f`
- `ntdll!RtlLeaveCriticalSection` at `0x1800361d2`
- `ntdll!RtlLeaveCriticalSection` at `0x180035a12`
- `ntdll!RtlLeaveCriticalSection` at `0x180035a2f`
- `ntdll!RtlLeaveCriticalSection` at `0x180035bff`
- `ntdll!RtlLeaveCriticalSection` at `0x180035c38`
- `ntdll!RtlLeaveCriticalSection` at `0x180035ec4`
- `ntdll!RtlLeaveCriticalSection` at `0x180035efb`
- `ntdll!RtlLeaveCriticalSection` at `0x180036097`
- `ntdll!RtlLeaveCriticalSection` at `0x1800360c3`
- `ntdll!RtlLeaveCriticalSection` at `0x18003617f`
- `ntdll!RtlLeaveCriticalSection` at `0x1800361d2`
- `ntdll!RtlEnterCriticalSection` at `0x1800359d6`
- `ntdll!RtlEnterCriticalSection` at `0x180035ba8`
- `ntdll!RtlEnterCriticalSection` at `0x180035d5c`
- `ntdll!RtlEnterCriticalSection` at `0x180036023`
- `ntdll!RtlEnterCriticalSection` at `0x180036103`
- `ntdll!RtlEnterCriticalSection` at `0x1800359d6`
- `ntdll!RtlEnterCriticalSection` at `0x180035ba8`
- `ntdll!RtlEnterCriticalSection` at `0x180035d5c`
- `ntdll!RtlEnterCriticalSection` at `0x180036023`
- `ntdll!RtlEnterCriticalSection` at `0x180036103`
- `ntdll!RtlInitUnicodeString` at `0x180035dae`
- `ntdll!RtlInitUnicodeString` at `0x180035e63`
- `ntdll!RtlInitUnicodeString` at `0x1800361af`
- `ntdll!RtlInitUnicodeString` at `0x180035dae`
- `ntdll!RtlInitUnicodeString` at `0x180035e63`
- `ntdll!RtlInitUnicodeString` at `0x1800361af`
- `ntdll!RtlEqualComputerName` at `0x180035b2d`
- `ntdll!RtlEqualComputerName` at `0x180035b73`
- `ntdll!RtlEqualComputerName` at `0x180035b2d`
- `ntdll!RtlEqualComputerName` at `0x180035b73`
- `CRYPTSP!SystemFunction007` at `0x180035f0f`
- `CRYPTSP!SystemFunction007` at `0x180035f0f`

## string_xrefs

- `0x1800359b5`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x180035a97`: `NlChangePassword: Can't become writer of client session.\n`
- `0x180035d8c`: `NlChangePassword: Password already updated in secret\n`
- `0x180035fb5`: `NlChangePassword: Cannot change password on PDC managed service account 0x%lx\n`
- `0x180036116`: `NlChangePassword: Flag password updated on DC\n`

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
      0x1908u,
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
      && !NlTimeHasElapsedEx(&v60, &stru_1800F82F0, &v53)
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
        if ( (unsigned int)dword_1800F8184 <= 0x31 )
          v9 = 86400000 * dword_1800F8184;
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
0x180035924  mov     [rsp-8+arg_18], rbx
0x180035929  push    rbp
0x18003592a  push    rsi
0x18003592b  push    rdi
0x18003592c  push    r12
0x18003592e  push    r13
0x180035930  push    r14
0x180035932  push    r15
0x180035934  lea     rbp, [rsp-0F0h]
0x18003593c  sub     rsp, 1F0h
0x180035943  mov     rax, cs:__security_cookie
0x18003594a  xor     rax, rsp
0x18003594d  mov     [rbp+120h+var_40], rax
0x180035954  xorps   xmm0, xmm0
0x180035957  mov     [rsp+220h+var_1C8], r8
0x18003595c  mov     rbx, rcx
0x18003595f  xorps   xmm1, xmm1
0x180035962  xor     ecx, ecx
0x180035964  mov     r14, r8
0x180035967  mov     r15b, dl
0x18003596a  mov     dword ptr [rsp+220h+var_1DC], ecx
0x18003596e  movdqu  xmmword ptr [rbp+120h+var_150.data.data], xmm0
0x180035973  mov     esi, ecx
0x180035975  mov     qword ptr [rsp+220h+var_1B0], rcx
0x18003597a  mov     r13b, cl
0x18003597d  mov     [rsp+220h+ComputerName2], rcx
0x180035982  mov     r12d, ecx
0x180035985  mov     [rsp+220h+var_1A8], rcx
0x18003598a  mov     [rsp+220h+var_1D4], ecx
0x18003598e  movups  xmmword ptr [rbp+120h+DestinationString.Length], xmm0
0x180035992  mov     [rsp+220h+var_1D0], rcx
0x180035997  movups  xmmword ptr [rbp+120h+var_170.Length], xmm1
0x18003599b  mov     [rsp+220h+var_1D8], ecx
0x18003599f  movups  xmmword ptr [rbp+120h+var_180.Length], xmm0
0x1800359a3  movups  xmmword ptr [rbp+120h+var_160.Length], xmm1
0x1800359a7  cmp     [rbx+148h], ecx
0x1800359ad  ja      short loc_1800359C8
0x1800359af  mov     r8d, 1908h; unsigned int
0x1800359b5  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800359bc  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x1800359c3  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800359c8  mov     rcx, [rbx+110h]
0x1800359cf  add     rcx, 190h; CriticalSection
0x1800359d6  call    cs:__imp_RtlEnterCriticalSection
0x1800359dd  nop     dword ptr [rax+rax+00h]
0x1800359e2  mov     ecx, [rbx+124h]
0x1800359e8  mov     edx, 2
0x1800359ed  bt      ecx, 12h
0x1800359f1  jnb     short loc_1800359FB
0x1800359f3  or      ecx, edx
0x1800359f5  mov     [rbx+124h], ecx
0x1800359fb  mov     rax, [rbx+110h]
0x180035a02  test    dl, cl
0x180035a04  mov     edi, 0F2h
0x180035a09  lea     rcx, [rax+190h]; CriticalSection
0x180035a10  jz      short loc_180035A2F
0x180035a12  call    cs:__imp_RtlLeaveCriticalSection
0x180035a19  nop     dword ptr [rax+rax+00h]
0x180035a1e  or      r12d, 0FFFFFFFFh
0x180035a22  xor     r15d, r15d
0x180035a25  mov     dword ptr [rsp+220h+var_1DC], r15d
0x180035a2a  jmp     loc_1800362EC
0x180035a2f  call    cs:__imp_RtlLeaveCriticalSection
0x180035a36  nop     dword ptr [rax+rax+00h]
0x180035a3b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb> `wil::Feature<__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb>::GetImpl(void)'::`2'::impl
0x180035a42  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ChangeMachinePasswordViaKerb>::__private_IsEnabled(void)
0x180035a47  test    al, al
0x180035a49  jz      short loc_180035A85
0x180035a4b  mov     eax, [rbx+118h]
0x180035a51  mov     edx, 1
0x180035a56  sub     eax, 3
0x180035a59  cmp     eax, edx
0x180035a5b  jbe     short loc_180035A85
0x180035a5d  lea     r8, aNlchangepasswo_18; "NlChangePassword: Calling into Kerberos"...
0x180035a64  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180035a67  mov     ecx, 200h; unsigned int
0x180035a6c  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180035a71  mov     cl, r15b; unsigned __int8
0x180035a74  call    ?CallKerbChangeMachinePassword@@YAJE@Z; CallKerbChangeMachinePassword(uchar)
0x180035a79  mov     dword ptr [rsp+220h+var_1DC], eax
0x180035a7d  xor     r15d, r15d
0x180035a80  jmp     loc_1800362EC
0x180035a85  mov     edx, cs:dwMilliseconds; dwMilliseconds
0x180035a8b  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180035a8e  call    ?NlTimeoutSetWriterClientSession@@YAHPEAU_CLIENT_SESSION@@K@Z; NlTimeoutSetWriterClientSession(_CLIENT_SESSION *,ulong)
0x180035a93  test    eax, eax
0x180035a95  jnz     short loc_180035ABB
0x180035a97  lea     r8, aNlchangepasswo_6; "NlChangePassword: Can't become writer o"...
0x180035a9e  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180035aa1  mov     ecx, 100h; unsigned int
0x180035aa6  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180035aab  mov     dword ptr [rsp+220h+var_1DC], 0C000005Eh
0x180035ab3  xor     r15d, r15d
0x180035ab6  jmp     loc_1800362E7
0x180035abb  lea     rax, [rsp+220h+var_1B0]
0x180035ac0  mov     r13b, 1
0x180035ac3  lea     r9, [rsp+220h+var_1D4]; unsigned int *
0x180035ac8  mov     [rsp+220h+var_1E0], r13b
0x180035acd  lea     r8, [rsp+220h+var_1A8]; struct _UNICODE_STRING **
0x180035ad2  mov     [rsp+220h+var_200], rax; union _LARGE_INTEGER *
0x180035ad7  lea     rdx, [rsp+220h+ComputerName2]; struct _UNICODE_STRING **
0x180035adc  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180035adf  call    ?NlGetOutgoingPassword@@YAJPEAU_CLIENT_SESSION@@PEAPEAU_UNICODE_STRING@@1PEAKPEAT_LARGE_INTEGER@@@Z; NlGetOutgoingPassword(_CLIENT_SESSION *,_UNICODE_STRING * *,_UNICODE_STRING * *,ulong *,_LARGE_INTEGER *)
0x180035ae4  mov     dword ptr [rsp+220h+var_1DC], eax
0x180035ae8  test    eax, eax
0x180035aea  jns     short loc_180035B05
0x180035aec  mov     r9d, eax
0x180035aef  lea     r8, aNlchangepasswo_11; "NlChangePassword: Cannot NlGetOutgoingP"...
0x180035af6  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180035af9  mov     ecx, 100h; unsigned int
0x180035afe  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180035b03  jmp     short loc_180035AB3
0x180035b05  mov     rdx, [rsp+220h+ComputerName2]; ComputerName2
0x180035b0a  mov     edi, 100h
0x180035b0f  mov     r14d, 200h
0x180035b15  test    rdx, rdx
0x180035b18  jz      short loc_180035B3D
0x180035b1a  cmp     [rdx], si
0x180035b1d  jz      short loc_180035B3D
0x180035b1f  mov     rcx, [rbx+110h]
0x180035b26  add     rcx, rdi; ComputerName1
0x180035b29  mov     [rsp+220h+var_1B4], esi
0x180035b2d  call    cs:__imp_RtlEqualComputerName
0x180035b34  nop     dword ptr [rax+rax+00h]
0x180035b39  test    al, al
0x180035b3b  jz      short loc_180035B5A
0x180035b3d  mov     r12d, 1
0x180035b43  lea     r8, aNlchangepasswo_14; "NlChangePassword: New LsaSecret is defa"...
0x180035b4a  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180035b4d  mov     [rsp+220h+var_1B4], r12d
0x180035b52  mov     ecx, r14d; unsigned int
0x180035b55  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180035b5a  mov     rdx, [rsp+220h+var_1A8]; ComputerName2
0x180035b5f  test    rdx, rdx
0x180035b62  jz      short loc_180035B83
0x180035b64  cmp     [rdx], si
0x180035b67  jz      short loc_180035B83
0x180035b69  mov     rcx, [rbx+110h]
0x180035b70  add     rcx, rdi; ComputerName1
0x180035b73  call    cs:__imp_RtlEqualComputerName
0x180035b7a  nop     dword ptr [rax+rax+00h]
0x180035b7f  test    al, al
0x180035b81  jz      short loc_180035B9A
0x180035b83  lea     r8, aNlchangepasswo_0; "NlChangePassword: Old LsaSecret is defa"...
0x180035b8a  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180035b8d  mov     ecx, r14d; unsigned int
0x180035b90  mov     esi, 1
0x180035b95  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180035b9a  mov     rcx, [rbx+110h]
0x180035ba1  add     rcx, 190h; CriticalSection
0x180035ba8  call    cs:__imp_RtlEnterCriticalSection
0x180035baf  nop     dword ptr [rax+rax+00h]
0x180035bb4  mov     rax, [rbx+1F0h]
0x180035bbb  add     qword ptr [rsp+220h+var_1B0], rax
0x180035bc0  test    [rbx+124h], r13b
0x180035bc7  jnz     short loc_180035C20
0x180035bc9  lea     r8, [rsp+220h+var_1D8]; unsigned int *
0x180035bce  lea     rdx, stru_1800F82F0; union _LARGE_INTEGER *
0x180035bd5  lea     rcx, [rsp+220h+var_1B0]; union _LARGE_INTEGER *
0x180035bda  call    ?NlTimeHasElapsedEx@@YAEPEAT_LARGE_INTEGER@@0PEAK@Z; NlTimeHasElapsedEx(_LARGE_INTEGER *,_LARGE_INTEGER *,ulong *)
0x180035bdf  test    al, al
0x180035be1  jnz     short loc_180035C20
0x180035be3  test    r12d, r12d
0x180035be6  jnz     short loc_180035C20
0x180035be8  test    esi, esi
0x180035bea  jnz     short loc_180035C20
0x180035bec  test    r15b, r15b
0x180035bef  jnz     short loc_180035C20
0x180035bf1  mov     rcx, [rbx+110h]
0x180035bf8  add     rcx, 190h; CriticalSection
0x180035bff  call    cs:__imp_RtlLeaveCriticalSection
0x180035c06  nop     dword ptr [rax+rax+00h]
0x180035c0b  mov     r12d, [rsp+220h+var_1D8]
0x180035c10  xor     r15d, r15d
0x180035c13  mov     dword ptr [rsp+220h+var_1DC], r15d
0x180035c18  mov     esi, r15d
0x180035c1b  jmp     loc_1800362E2
0x180035c20  mov     rcx, [rbx+110h]
0x180035c27  xor     r15d, r15d
0x180035c2a  add     rcx, 190h; CriticalSection
0x180035c31  mov     [rbx+1F0h], r15
0x180035c38  call    cs:__imp_RtlLeaveCriticalSection
0x180035c3f  nop     dword ptr [rax+rax+00h]
0x180035c44  lea     r8, aNlchangepasswo_16; "NlChangePassword: Doing it.\n"
0x180035c4b  mov     [rsp+220h+var_1D8], r15d
0x180035c50  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180035c53  mov     ecx, r14d; unsigned int
0x180035c56  mov     r12d, r15d
0x180035c59  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180035c5e  test    dword ptr [rbx+124h], 20000h
0x180035c68  jz      short loc_180035C96
0x180035c6a  xor     ecx, ecx; unsigned __int16 *
0x180035c6c  call    ?NlFindDomainByServerName@@YAPEAU_DOMAIN_INFO@@PEAG@Z; NlFindDomainByServerName(ushort *)
0x180035c71  mov     [rsp+220h+var_1D0], rax
0x180035c76  mov     rsi, rax
0x180035c79  lea     edx, [r15+1]
0x180035c7d  test    rax, rax
0x180035c80  jz      short loc_180035C9E
0x180035c82  mov     ecx, [rax+24Ch]
0x180035c88  sub     ecx, edx
0x180035c8a  cmp     ecx, edx
0x180035c8c  ja      short loc_180035C9E
0x180035c8e  mov     r13d, edx
0x180035c91  jmp     loc_180035D4E
0x180035c96  mov     rsi, r12
0x180035c99  mov     edx, 1
0x180035c9e  cmp     dword ptr [rbx+118h], 6
0x180035ca5  mov     r13d, r15d
0x180035ca8  jnz     short loc_180035CBD
0x180035caa  mov     rax, [rbx+110h]
0x180035cb1  cmp     [rax+24Ch], edx
0x180035cb7  jz      loc_180035D4E
0x180035cbd  cmp     dword ptr [rbx+11Ch], 2
0x180035cc4  jnz     short loc_180035D16
0x180035cc6  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180035cc9  call    ?NlConfirmCapabilities@@YAJPEAU_CLIENT_SESSION@@@Z; NlConfirmCapabilities(_CLIENT_SESSION *)
0x180035cce  mov     r9, [rbx+1F8h]
0x180035cd5  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180035cd8  mov     dword ptr [rsp+220h+var_1DC], eax
0x180035cdc  test    eax, eax
0x180035cde  jns     short loc_180035D07
0x180035ce0  lea     r8, aNlchangepasswo_3; "NlChangePassword: Unsuccessful response"...
0x180035ce7  mov     dword ptr [rsp+220h+var_200], eax
0x180035ceb  mov     ecx, edi; unsigned int
0x180035ced  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180035cf2  mov     eax, 0C000005Eh
0x180035cf7  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180035cfa  mov     edx, eax; int
0x180035cfc  mov     dword ptr [rsp+220h+var_1DC], eax
0x180035d00  call    ?NlSetStatusClientSession@@YAXPEAU_CLIENT_SESSION@@J@Z; NlSetStatusClientSession(_CLIENT_SESSION *,long)
0x180035d05  jmp     short loc_180035D16
0x180035d07  lea     r8, aNlchangepasswo_12; "NlChangePassword: Successful response f"...
0x180035d0e  mov     ecx, r14d; unsigned int
0x180035d11  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180035d16  cmp     [rbx+120h], r15d
0x180035d1d  jge     short loc_180035D4E
0x180035d1f  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180035d22  call    ?NlTimeToReauthenticate@@YAEPEAU_CLIENT_SESSION@@@Z; NlTimeToReauthenticate(_CLIENT_SESSION *)
0x180035d27  test    al, al
0x180035d29  jnz     short loc_180035D3A
0x180035d2b  mov     eax, [rbx+120h]
0x180035d31  mov     dword ptr [rsp+220h+var_1DC], eax
0x180035d35  jmp     loc_1800362DD
0x180035d3a  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180035d3d  call    ?NlSessionSetupEx@@YAJPEAU_CLIENT_SESSION@@@Z; NlSessionSetupEx(_CLIENT_SESSION *)
0x180035d42  mov     dword ptr [rsp+220h+var_1DC], eax
0x180035d46  test    eax, eax
0x180035d48  js      loc_1800362DD
0x180035d4e  mov     rcx, [rbx+110h]
0x180035d55  add     rcx, 190h; CriticalSection
0x180035d5c  call    cs:__imp_RtlEnterCriticalSection
0x180035d63  nop     dword ptr [rax+rax+00h]
0x180035d68  mov     rax, [rsp+220h+ComputerName2]
0x180035d6d  test    rax, rax
0x180035d70  jz      short loc_180035D83
0x180035d72  mov     ecx, 0F0h
0x180035d77  cmp     [rax], cx
0x180035d7a  jb      short loc_180035D83
0x180035d7c  and     dword ptr [rbx+124h], 0FFFFFFFEh
0x180035d83  test    byte ptr [rbx+124h], 1
0x180035d8a  jz      short loc_180035DCC
0x180035d8c  lea     r8, aNlchangepasswo_15; "NlChangePassword: Password already upda"...
0x180035d93  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180035d96  mov     ecx, r14d; unsigned int
0x180035d99  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180035d9e  mov     rax, [rsp+220h+ComputerName2]
0x180035da3  test    rax, rax
0x180035da6  jnz     short loc_180035DBF
0x180035da8  xor     edx, edx; SourceString
0x180035daa  lea     rcx, [rbp+120h+DestinationString]; DestinationString
0x180035dae  call    cs:__imp_RtlInitUnicodeString
0x180035db5  nop     dword ptr [rax+rax+00h]
0x180035dba  jmp     loc_180035EED
0x180035dbf  movups  xmm0, xmmword ptr [rax]
0x180035dc2  movdqu  xmmword ptr [rbp+120h+DestinationString.Length], xmm0
0x180035dc7  jmp     loc_180035EED
0x180035dcc  lea     rcx, [rsp+220h+var_1B8]
0x180035dd1  mov     [rsp+220h+var_1B8], r15d
0x180035dd6  mov     esi, 0Eh
0x180035ddb  call    I_NetLogonMixedDomain
0x180035de0  mov     dword ptr [rsp+220h+var_1DC], eax
0x180035de4  test    eax, eax
0x180035de6  js      short loc_180035DF6
0x180035de8  cmp     [rsp+220h+var_1B8], r15d
0x180035ded  jnz     short loc_180035E07
0x180035def  mov     esi, 78h ; 'x'
0x180035df4  jmp     short loc_180035E07
0x180035df6  mov     r8d, eax
0x180035df9  lea     rdx, aFallingBackToS; "Falling back to short password because "...
0x180035e00  mov     ecx, edi; unsigned int
0x180035e02  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180035e07  lea     edx, [rsi+rsi]; unsigned int
0x180035e0a  lea     rcx, [rbp+120h+SourceString]; pbBuffer
0x180035e0e  call    ?NlGenerateRandomBits@@YAEPEAEK@Z; NlGenerateRandomBits(uchar *,ulong)
0x180035e13  test    al, al
0x180035e15  jnz     short loc_180035E25
0x180035e17  lea     rdx, aCanTNlgenerate_1; "Can't NlGenerateRandomBits for clear pa"...
0x180035e1e  mov     ecx, edi; unsigned int
0x180035e20  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180035e25  mov     eax, r15d
  ... truncated ...
```
