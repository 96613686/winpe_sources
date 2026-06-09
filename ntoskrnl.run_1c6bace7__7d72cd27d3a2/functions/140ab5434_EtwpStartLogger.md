# EtwpStartLogger

- ea: `0x140ab5434`
- end: `0x140ab64a8`
- name: `EtwpStartLogger`
- size: `4212`
- prototype: ``
- caller_count: `3`
- callee_count: `56`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140ab53c4`
- `0x140adfc3c`
- `0x140c86778`

## callees

- `0x140213b40`
- `0x14025bdf0`
- `0x14025bf50`
- `0x140320960`
- `0x140371750`
- `0x140374d10`
- `0x1403cc160`
- `0x140403380`
- `0x14042975c`
- `0x1404b17fc`
- `0x1404bf02c`
- `0x1404ccc20`
- `0x1404f72f0`
- `0x140544600`
- `0x1406847c8`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406f7250`
- `0x1407d8d00`
- `0x1407d8d90`
- `0x1407d8e28`
- `0x1407d8ef4`
- `0x1408509b0`
- `0x140850a60`
- `0x140851000`
- `0x140858dc0`
- `0x1408743a0`
- `0x140874494`
- `0x140874e48`
- `0x1408e1e30`
- `0x14094b120`
- `0x140978ddc`
- `0x140978ef0`
- `0x140979090`
- `0x1409791c4`
- `0x140979290`
- `0x140979854`
- `0x14097a030`
- `0x14097ab74`
- `0x14097aea4`
- `0x140982ce0`
- `0x1409bb9d0`
- `0x1409f9654`
- `0x140a21e08`
- `0x140a354f4`
- `0x140a96cb8`
- `0x140a97f3c`
- `0x140ab5434`
- `0x140ac0238`
- `0x140ac41d0`

## string_xrefs

- `0x140ab59d4`: `Eventlog-Security`
- `0x140ab5a96`: `Eventlog-Security`

## pseudocode

```c
__int64 __fastcall EtwpStartLogger(__int64 a1, __int64 a2)
{
  unsigned int v3; // r15d
  NTSTATUS FileName; // edi
  int v5; // r13d
  int v6; // ecx
  int v7; // ecx
  int v8; // r8d
  int v10; // edx
  int v11; // ecx
  int v12; // eax
  UUID *v13; // rbx
  unsigned int v14; // edi
  ACCESS_MASK v15; // edx
  __int64 v16; // rbx
  __int64 v17; // rsi
  unsigned int v18; // r13d
  bool v19; // zf
  char v20; // bl
  int v21; // edx
  int v22; // ecx
  unsigned int *v23; // rbx
  unsigned int v24; // edi
  __int64 v25; // rax
  __int64 v26; // rsi
  int v27; // r8d
  __int64 v28; // rcx
  const WCHAR *v29; // rdx
  __int64 v30; // rcx
  unsigned int *inited; // rsi
  __int64 FlagExtension; // rax
  __int16 v33; // dx
  __int64 v34; // rbx
  __int64 v35; // rdx
  __int64 v36; // rcx
  void *v37; // rcx
  unsigned int v38; // eax
  int v39; // eax
  int v40; // ebx
  __int64 v41; // rdx
  char v42; // al
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  unsigned int v46; // eax
  int v47; // edx
  unsigned __int64 v48; // rax
  __int64 Pool2; // rax
  unsigned int v50; // ecx
  unsigned __int64 v51; // rdx
  int v52; // eax
  __int64 v53; // r15
  __int64 CurrentServerSilo; // rax
  __int64 v55; // rcx
  __int64 v56; // r8
  __int64 v57; // rcx
  __int64 v58; // rdx
  __int64 v59; // rdx
  unsigned __int8 v60; // [rsp+40h] [rbp-C0h]
  unsigned int v61; // [rsp+44h] [rbp-BCh]
  __int64 v62; // [rsp+48h] [rbp-B8h] BYREF
  UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v64; // [rsp+60h] [rbp-A0h] BYREF
  int v65; // [rsp+68h] [rbp-98h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp-90h] BYREF
  __int64 v67; // [rsp+78h] [rbp-88h] BYREF
  UNICODE_STRING UnicodeString; // [rsp+80h] [rbp-80h] BYREF
  ACCESS_MASK DesiredAccess; // [rsp+90h] [rbp-70h]
  UUID Uuid; // [rsp+98h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A8h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v72; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v73; // [rsp+E0h] [rbp-20h]
  __int64 v74; // [rsp+E8h] [rbp-18h]
  __int64 *v75; // [rsp+F0h] [rbp-10h]
  __int64 v76; // [rsp+F8h] [rbp-8h]
  __int64 *v77; // [rsp+100h] [rbp+0h]
  __int64 v78; // [rsp+108h] [rbp+8h]

  v62 = a1;
  LODWORD(v64) = 0;
  v67 = 0;
  SecurityDescriptor = 0;
  HIWORD(UserData.Size) = 0;
  v65 = 0;
  Uuid = 0;
  UnicodeString = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  RtlInitUnicodeString(&UnicodeString, 0);
  v3 = *(_DWORD *)(a2 + 64) & 0x9DECE5FF;
  v61 = 3;
  if ( (*(_BYTE *)(a2 + 64) & 3) == 0 && ((*(_BYTE *)(a2 + 64) & 8) != 0 || (*(_BYTE *)(a2 + 64) & 4) != 0) )
    v3 = *(_DWORD *)(a2 + 64) & 0x9DECE5FE | 1;
  if ( (v3 & 0x40000) != 0 )
    v3 |= 0x80u;
  if ( (v3 & 0x80000) != 0 && (v3 & 0x1000000) != 0 )
    v3 &= ~0x1000000u;
  if ( !*(_WORD *)(a2 + 144) || !*(_QWORD *)(a2 + 152) )
    goto LABEL_58;
  FileName = EtwpCaptureString(a2 + 144, &DestinationString);
  if ( FileName )
    goto LABEL_59;
  if ( (v3 & 0x400) != 0 )
  {
    if ( *(_QWORD *)(a2 + 136) || (v3 & 0xF) != 0 )
      goto LABEL_58;
    if ( (v3 & 0x100) != 0 )
      v3 &= ~0x100u;
    if ( *(_DWORD *)(a2 + 68) )
      *(_DWORD *)(a2 + 68) = 0;
    if ( *(_DWORD *)(a2 + 76) )
      *(_DWORD *)(a2 + 76) = 0;
  }
  if ( (v3 & 3) == 3 )
    goto LABEL_58;
  if ( (v3 & 0xC000) == 0xC000 )
    goto LABEL_58;
  v5 = v3 & 0x100;
  if ( (v3 & 0x100) == 0 && (v3 & 0x400) == 0 && !*(_QWORD *)(a2 + 136) )
    goto LABEL_58;
  if ( (v3 & 2) != 0 && ((v3 & 4) != 0 || !*(_DWORD *)(a2 + 60)) )
    goto LABEL_58;
  if ( (v3 & 0x20) != 0 && (!*(_DWORD *)(a2 + 60) || (*(_DWORD *)(a2 + 64) & 0xC) != 0) )
    goto LABEL_58;
  if ( (v3 & 0x40) != 0
    && ((*(_DWORD *)(a2 + 112) & 2) == 0
     || (v3 & 2) == 0 && (v3 & 0x400) == 0 && ((v3 & 0x100) == 0 || *(_QWORD *)(a2 + 136))) )
  {
    goto LABEL_58;
  }
  if ( (v3 & 0xC00000) == 0xC00000
    || (v3 & 8) != 0
    && (!*(_QWORD *)(a2 + 136)
     || (v3 & 2) != 0
     || !*(_DWORD *)(a2 + 60)
     || (*(_DWORD *)(a2 + 112) & 2) != 0
     || (*(_DWORD *)(a2 + 64) & 0x2000000) != 0
     || !memcmp((const void *)(a2 + 24), &SystemTraceControlGuid, 0x10u)
     || !memcmp((const void *)(a2 + 24), CKCLGuid, 0x10u)
     || (v3 & 4) != 0) )
  {
    goto LABEL_58;
  }
  v6 = *(_DWORD *)(a2 + 64);
  if ( (v6 & 0x2000000) != 0 && (v6 & 0x1000000) != 0 )
    goto LABEL_58;
  if ( (v6 & 0x4000000) != 0 && (v6 & 0x106) != 0 || (v6 & 0x10000) != 0 )
    goto LABEL_58;
  if ( (*(_BYTE *)(a2 + 80) & 4) != 0 )
  {
    if ( !EtwpKsrCallbackObject )
    {
      FileName = -1073741637;
      if ( EtwEventEnabled(EtwpEventTracingProvRegHandle, &ETW_EVENT_LARGE_MDL_NOT_SUPPORTED) )
        EtwpEventWriteTemplateSessionFromCapturedData(
          v11,
          v10,
          a2 + 24,
          *(_DWORD *)(a2 + 64),
          (__int64)&DestinationString,
          (__int64)&UnicodeString);
LABEL_59:
      if ( EtwEventEnabled(EtwpEventTracingProvRegHandle, &ETW_EVENT_SESSION_START_FAILED) )
        EtwpEventWriteTemplateAdmin(
          v7,
          (unsigned int)&ETW_EVENT_SESSION_START_FAILED,
          v8,
          (unsigned int)&DestinationString,
          (__int64)&UnicodeString,
          FileName,
          v3);
      RtlFreeAnsiString(&DestinationString);
      RtlFreeAnsiString(&UnicodeString);
      EtwpFreeSecurityDescriptor(&SecurityDescriptor);
      return (unsigned int)FileName;
    }
    if ( (v6 & 0x400) == 0 || (v6 & 0x1000000) != 0 )
    {
LABEL_58:
      FileName = -1073741811;
      goto LABEL_59;
    }
  }
  v12 = *(_DWORD *)(a2 + 112);
  if ( v12 >= 0 )
  {
    v13 = (UUID *)(a2 + 24);
  }
  else
  {
    if ( EtwpBootPhase )
      goto LABEL_58;
    if ( (v12 & 2) == 0 )
      goto LABEL_58;
    if ( (*(_DWORD *)(a2 + 64) & 0x2000000) == 0 )
      goto LABEL_58;
    if ( ((*(_DWORD *)(a2 + 40) - 2) & 0xFFFFFFFD) == 0 )
      goto LABEL_58;
    v13 = (UUID *)(a2 + 24);
    if ( !memcmp((const void *)(a2 + 24), &NullGuid, 0x10u) )
      goto LABEL_58;
  }
  FileName = EtwpValidateFlagExtension(a2);
  if ( FileName < 0 )
    goto LABEL_59;
  v14 = 0;
  v15 = (v5 != 0 ? 160 : 128) | 0x40;
  if ( !*(_WORD *)(a2 + 128) )
    v15 = v5 != 0 ? 160 : 128;
  DesiredAccess = v15;
  if ( !(unsigned int)EtwpLookupLoggerIdByName(v62, &DestinationString, &v64) )
  {
LABEL_77:
    FileName = -1073741771;
    goto LABEL_59;
  }
  if ( !memcmp(v13, &NullGuid, 0x10u) )
  {
    FileName = ExUuidCreate(&Uuid);
    if ( FileName < 0 )
      goto LABEL_59;
    v14 = 0;
  }
  else
  {
    Uuid = *v13;
  }
  if ( (v3 & 0xC00000) == 0 )
  {
    if ( KeGetCurrentThread()->PreviousMode && (unsigned int)PsGetSessionId(KeGetCurrentThread()->ApcState.Process) )
      v3 |= 0x400000u;
    else
      v3 |= 0x800000u;
  }
  v16 = v62;
  v17 = *(_QWORD *)(v62 + 712);
  v64 = v17;
  if ( !memcmp(&Uuid, &SystemTraceControlGuid, 0x10u) || !memcmp(&Uuid, CKCLGuid, 0x10u) )
  {
    RtlFreeAnsiString(&DestinationString);
    if ( !memcmp(&Uuid, &SystemTraceControlGuid, 0x10u) )
    {
      v18 = 0;
      v29 = L"NT Kernel Logger";
    }
    else
    {
      v14 = 2;
      v29 = L"Circular Kernel Context Logger";
      v18 = 1;
    }
    v61 = v14;
    if ( RtlCreateUnicodeString(&DestinationString, v29) )
    {
      v3 |= 0x80u;
      if ( (v3 & 0x1000000) != 0 )
        goto LABEL_58;
      v19 = _InterlockedCompareExchange64((volatile signed __int64 *)(v17 + 8LL * v14), v17 | 1, 1) == 1;
      goto LABEL_133;
    }
    goto LABEL_130;
  }
  v18 = 8;
  if ( !memcmp(&Uuid, &GlobalLoggerGuid, 0x10u) )
  {
    v61 = 1;
    v14 = 1;
    if ( !EtwpGetFlagExtension(a2, 1) )
    {
LABEL_94:
      v19 = _InterlockedCompareExchange64((volatile signed __int64 *)(v17 + 8), v17 | 1, 1) == 1;
LABEL_133:
      if ( v19 )
        goto LABEL_100;
      goto LABEL_77;
    }
    if ( (v3 & 0x1000000) != 0 )
      goto LABEL_58;
    RtlFreeAnsiString(&DestinationString);
    if ( RtlCreateUnicodeString(&DestinationString, L"NT Kernel Logger") )
    {
      v18 = 0;
      goto LABEL_94;
    }
LABEL_130:
    FileName = -1073741801;
    goto LABEL_59;
  }
  if ( !memcmp(&Uuid, AuditLoggerGuid, 0x10u) )
  {
    if ( (v3 & 0x1000000) != 0 )
      goto LABEL_58;
    RtlFreeAnsiString(&DestinationString);
    if ( RtlCreateUnicodeString(&DestinationString, L"Eventlog-Security") )
    {
      v3 |= 0x80u;
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v17 + 24), v17 | 1, 1) == 1 )
      {
        v14 = 3;
        goto LABEL_100;
      }
      goto LABEL_77;
    }
    goto LABEL_130;
  }
  if ( !wcsicmp(DestinationString.Buffer, L"Eventlog-Security") && memcmp(&Uuid, AuditLoggerGuid, 0x10u) )
    goto LABEL_77;
  v23 = (unsigned int *)(v62 + 16);
  v24 = 4;
  if ( *(_DWORD *)(v62 + 16) <= 4u )
    goto LABEL_114;
  while ( 1 )
  {
    v25 = EtwpAcquireLoggerContextByLoggerId(v62, v24, 0);
    v26 = v25;
    if ( v25 )
      break;
LABEL_110:
    if ( ++v24 >= *v23 )
      goto LABEL_113;
  }
  if ( memcmp((const void *)(v25 + 276), &Uuid, 0x10u) )
  {
    EtwpReleaseLoggerContext(v26, 0);
    goto LABEL_110;
  }
  EtwpReleaseLoggerContext(v26, 0);
LABEL_113:
  v17 = v64;
LABEL_114:
  if ( v24 < *v23 )
    goto LABEL_77;
  v14 = 4;
  v61 = 4;
  if ( *v23 > 4 )
  {
    do
    {
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v17 + 8LL * v14), v17 | 1, 1) == 1 )
        break;
      ++v14;
    }
    while ( v14 < *v23 );
    v61 = v14;
  }
  if ( v14 >= *v23 )
  {
    if ( !byte_140E44DA9 )
    {
      byte_140E44DA9 = 1;
      UserData.Ptr = v62 + 16;
      *(_QWORD *)&UserData.Size = 4;
      EtwWrite(EtwpEventTracingProvRegHandle, &ETW_EVENT_OUT_OF_LOGGER_SLOTS, 0, 1u, &UserData);
      if ( (unsigned int)dword_140E0C710 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_140E0C710, 0x200000000000LL) )
        {
          v67 = 1;
          v73 = &v67;
          v74 = 8;
          v75 = &v62;
          LODWORD(v64) = *v23;
          v77 = &v64;
          v62 = 0x1000000;
          v76 = 8;
          v78 = 4;
          tlgWriteAgg((int)&dword_140E0C710, (int)&word_1400546D2, v27, 5, &v72);
        }
      }
    }
    FileName = -1073741670;
    if ( EtwEventEnabled(EtwpEventTracingProvRegHandle, &ETW_EVENT_NOT_ENOUGH_LOGGER_SLOTS) )
      EtwpEventWriteTemplateSessionMaxLoggers(v28, &ETW_EVENT_NOT_ENOUGH_LOGGER_SLOTS, &DestinationString, *v23);
    goto LABEL_59;
  }
  v16 = v62;
LABEL_100:
  ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v16 + 704) + 8LL * v14), 1u);
  if ( *(int *)(a2 + 112) >= 0 )
  {
    EtwpGetSecurityDescriptorByGuid(&Uuid, &SecurityDescriptor);
    v20 = DesiredAccess;
    v67 = (__int64)SecurityDescriptor;
    FileName = EtwpAccessCheck(SecurityDescriptor, DesiredAccess);
    if ( FileName < 0 )
    {
      if ( EtwEventEnabled(EtwpEventTracingProvRegHandle, &ETW_EVENT_START_TRACE_ACCESS_DENIED) )
        EtwpEventWriteTemplateSessionDesiredAccess(v22, v21, (unsigned int)&DestinationString, (unsigned int)&Uuid, v20);
      goto LABEL_166;
    }
    v16 = v62;
  }
  if ( !memcmp(&HeapGuid, &Uuid, 0x10u) )
    v60 = 0;
  else
    v60 = memcmp(&CritSecGuid, &Uuid, 0x10u) != 0 ? 9 : 1;
  if ( (*(_DWORD *)(a2 + 64) & 0x2000000) != 0 && v18 == 8 )
  {
    if ( *(int *)(a2 + 112) < 0 || (FileName = EtwpCheckGuidAccess(&SystemTraceControlGuid, 128, 0), FileName >= 0) )
    {
      v18 = 2;
      while ( _bittest((const signed __int32 *)(v16 + 4520), v18) )
      {
        if ( ++v18 >= 8 )
        {
          if ( v18 != 8 )
            goto LABEL_150;
          FileName = -1073741670;
          if ( EtwEventEnabled(EtwpEventTracingProvRegHandle, &ETW_EVENT_NOT_ENOUGH_SYSTEM_LOGGER_SLOTS) )
            EtwpEventWriteTemplateSessionMaxLoggers(
              v30,
              &ETW_EVENT_NOT_ENOUGH_SYSTEM_LOGGER_SLOTS,
              &DestinationString,
              8);
          goto LABEL_166;
        }
      }
      goto LABEL_150;
    }
LABEL_166:
    ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v62 + 704) + 8LL * v61), 1u);
    _InterlockedExchange64((volatile __int64 *)(v64 + 8LL * v61), 1);
    goto LABEL_59;
  }
LABEL_150:
  inited = (unsigned int *)EtwpInitLoggerContext(&DestinationString, v3, *(unsigned int *)(a2 + 112));
  if ( !inited )
  {
    FileName = -1073741801;
    goto LABEL_166;
  }
  FlagExtension = EtwpGetFlagExtension(a2, 6);
  v34 = FlagExtension;
  if ( FlagExtension )
  {
    if ( 4 * *(_WORD *)FlagExtension == v33 + 6 )
    {
      FileName = EtwpSetPartitionContext(inited + 396, *(_QWORD *)(FlagExtension + 4));
      if ( FileName < 0 )
      {
        if ( EtwEventEnabled(EtwpEventTracingProvRegHandle, &ETW_EVENT_INVALID_MEMORY_PARTITION) )
          EtwpEventWriteTemplateSessionAndHandle(v36, v35, &DestinationString, *(_QWORD *)(v34 + 4));
        goto LABEL_157;
      }
    }
  }
  RtlFreeAnsiString(&DestinationString);
  *(UUID *)(inited + 69) = Uuid;
  inited[73] = *(_DWORD *)(a2 + 60);
  if ( (*(_BYTE *)(a2 + 80) & 1) != 0 )
    _InterlockedOr((volatile signed __int32 *)inited + 204, 0x10u);
  inited[50] = *(_DWORD *)(a2 + 40);
  if ( (*(_BYTE *)(a2 + 80) & 2) != 0 )
  {
    FileName = EtwpSetQpcDeltaTracking(inited);
    if ( FileName < 0 )
      goto LABEL_157;
  }
  if ( (*(_BYTE *)(a2 + 80) & 8) != 0 )
    _InterlockedOr((volatile signed __int32 *)inited + 204, 0x40000000u);
  v38 = *(_DWORD *)(a2 + 68);
  if ( v38 )
  {
    inited[52] = v38;
  }
  else if ( (v3 & 0x100) != 0 )
  {
    inited[52] = (v3 & 0x10) != 0 ? 1000 : 1;
  }
  v39 = *(_DWORD *)(a2 + 76);
  if ( v39 )
  {
    if ( inited[52] || v39 < 0 )
    {
      *(_DWORD *)(a2 + 76) = 0;
      goto LABEL_181;
    }
  }
  else
  {
LABEL_181:
    v39 = 0;
  }
  inited[53] = v39;
  FileName = 0;
  *inited = v61;
  *((_QWORD *)inited + 170) = v62;
  if ( *(_WORD *)(a2 + 128) )
  {
    if ( *(_QWORD *)(a2 + 136) )
    {
      FileName = EtwpCaptureString(a2 + 128, &UnicodeString);
      if ( FileName < 0 )
        goto LABEL_157;
    }
  }
  if ( (*(_DWORD *)(a2 + 112) & 2) != 0 )
  {
    inited[74] = *(_DWORD *)(a2 + 96);
    *(_DWORD *)(a2 + 96) = 0;
  }
  if ( (inited[3] & 8) == 0 )
  {
    *(UNICODE_STRING *)(inited + 38) = UnicodeString;
    RtlInitUnicodeString(&UnicodeString, 0);
    goto LABEL_191;
  }
  *(UNICODE_STRING *)(inited + 42) = UnicodeString;
  RtlInitUnicodeString(&UnicodeString, 0);
  FileName = EtwpGenerateFileName(inited + 42, inited + 74, inited + 38);
  if ( FileName < 0 )
  {
LABEL_157:
    if ( (inited[3] & 0x2000000) != 0 )
      _interlockedbittestandreset((volatile signed __int32 *)(v62 + 4520), v18);
    EtwpFreeApcPool(inited + 208);
    if ( (inited[204] & 0x80u) != 0 )
      ExFreePoolWithTag(*((PVOID *)inited + 131), 0);
    if ( (inited[204] & 0x2000) != 0 )
      _InterlockedDecrement((volatile signed __int32 *)&qword_140E2CFD0);
    RtlFreeAnsiString((PUNICODE_STRING)(inited + 38));
    RtlFreeAnsiString((PUNICODE_STRING)(inited + 42));
    v37 = (void *)*((_QWORD *)inited + 100);
    if ( v37 )
      ZwClose(v37);
    ExFreePoolWithTag(inited, 0);
    goto LABEL_166;
  }
LABEL_191:
  if ( *(int *)(a2 + 112) >= 0 )
  {
    UserData.Ptr = 0x20000000CLL;
    LOWORD(UserData.Size) = 257;
    FileName = SeCreateClientSecurity(
                 KeGetCurrentThread(),
                 (PSECURITY_QUALITY_OF_SERVICE)&UserData,
                 0,
                 (PSECURITY_CLIENT_CONTEXT)(inited + 176));
  }
  if ( FileName < 0 )
    goto LABEL_157;
  if ( (inited[3] & 0x100) != 0 )
    _InterlockedOr((volatile signed __int32 *)inited + 204, 8u);
  else
    _InterlockedAnd((volatile signed __int32 *)inited + 204, 0xFFFFFFF7);
  if ( (*(_DWORD *)(a2 + 112) & 2) != 0 )
    _InterlockedOr((volatile signed __int32 *)inited + 204, 2u);
  if ( *(int *)(a2 + 112) < 0 )
    _InterlockedOr((volatile signed __int32 *)inited + 204, 0x80000000);
  if ( (*(_DWORD *)(a2 + 112) & 1) != 0 )
    _InterlockedOr((volatile signed __int32 *)inited + 204, 1u);
  v40 = 0x4000;
  if ( (*(_DWORD *)(a2 + 112) & 0x4000) != 0 )
    _InterlockedOr((volatile signed __int32 *)inited + 204, 0x4000u);
  EtwpInitializeTimeStamp(inited);
  if ( v18 < 8 )
  {
    _InterlockedAnd((volatile signed __int32 *)inited + 204, 0xFF00FFFF);
    _InterlockedOr((volatile signed __int32 *)inited + 204, v18 << 16);
    inited[3] |= 0x2000000u;
    if ( v18 <= 1 )
      _InterlockedOr((volatile signed __int32 *)inited + 204, 0x20u);
    v41 = v62;
    *(_BYTE *)(v62 + 2LL * v18 + 4504) = v61;
    if ( inited[50] - 1 >= 4 )
      v42 = 1;
    else
      v42 = *((_BYTE *)inited + 200);
    *(_BYTE *)(v41 + 2LL * v18 + 4505) = v42;
    _interlockedbittestandset((volatile signed __int32 *)(v41 + 4520), v18);
  }
  FileName = EtwpCheckForStackTracingExtension(a2, inited);
  if ( FileName < 0 )
    goto LABEL_157;
  v43 = *(_DWORD *)(a2 + 52);
  if ( v43 )
    inited[56] = v43;
  v44 = *(_DWORD *)(a2 + 56);
  if ( v44 )
    inited[59] = v44;
  v45 = *(_DWORD *)(a2 + 48);
  if ( v45 )
  {
    if ( v45 <= 0x4000 )
      v40 = *(_DWORD *)(a2 + 48);
    else
      *(_DWORD *)(a2 + 48) = 0x4000;
    inited[1] = v40 << 10;
  }
  if ( (*(_BYTE *)(a2 + 80) & 4) != 0 )
  {
    inited[1] = (inited[1] + 0x1FFFFF) & 0xFFE00000;
    _InterlockedOr((volatile signed __int32 *)inited + 204, 0x20000000u);
  }
  if ( *((_WORD *)inited + 76) )
  {
    *((_QWORD *)inited + 4) = KeGetCurrentThread();
    while ( 1 )
    {
      _InterlockedOr((volatile signed __int32 *)inited + 206, 1u);
      FileName = EtwpCreateLogFile(inited, 0, &v65);
      if ( FileName >= 0 )
        break;
      if ( FileName != -1073741306 )
        goto LABEL_157;
      v46 = inited[1];
      v47 = ~(v65 - 1) & (v65 - 1 + v46);
      if ( v46 == v47 )
        goto LABEL_157;
      inited[1] = v47;
    }
  }
  if ( inited[1] < 0x1000 && (*((_WORD *)inited + 76) || (inited[3] & 0x400) != 0) )
    _InterlockedOr((volatile signed __int32 *)inited + 204, 0x1000u);
  v48 = inited[1] - 72LL;
  if ( v48 >= 0xFFFF )
    LODWORD(v48) = 0xFFFF;
  inited[2] = v48 & 0xFFFFFFF8;
  FileName = EtwpAllocateTraceBufferPool(inited);
  if ( FileName < 0 )
  {
LABEL_237:
    EtwpFreeTraceBufferPool(inited);
    goto LABEL_157;
  }
  if ( (v3 & 0x4000000) != 0 && (v3 & 0x400) == 0 )
  {
    Pool2 = ExAllocatePool2(64, inited[1], 0x5A777445u);
    *((_QWORD *)inited + 177) = Pool2;
    if ( !Pool2 )
    {
      FileName = -1073741801;
      goto LABEL_157;
    }
  }
  v50 = inited[73];
  if ( !v50 || (inited[3] & 0x2000) != 0 )
    v51 = 10485760;
  else
    v51 = (unsigned __int64)v50 << 20;
  v52 = inited[1] * inited[59];
  if ( v51 <= (unsigned int)(2 * v52) )
    v51 = (unsigned int)(2 * v52);
  *((_QWORD *)inited + 52) = v51;
  if ( *(int *)(a2 + 112) >= 0 )
  {
    FileName = EtwpInitializeLoggerSecurityDescriptor(inited, v67);
    EtwpFreeSecurityDescriptor(&SecurityDescriptor);
    if ( FileName < 0 )
      goto LABEL_237;
  }
  v53 = v62;
  _InterlockedAdd((volatile signed __int32 *)(v62 + 4404), 1u);
  ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v62 + 704) + 8LL * v61), 1u);
  if ( (inited[3] & 0x400) == 0 && *(int *)(a2 + 112) >= 0 )
  {
    CurrentServerSilo = PsGetCurrentServerSilo();
    FileName = EtwpStartLoggerThread(CurrentServerSilo, inited);
    if ( FileName < 0 )
    {
      ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v62 + 704) + 8LL * v61), 1u);
      goto LABEL_254;
    }
  }
  if ( EtwEventEnabled(EtwpEventTracingProvRegHandle, &ETW_EVENT_START_TRACE) )
    EtwpEventWriteTemplateSession(v55, &ETW_EVENT_START_TRACE, inited);
  KeWaitForSingleObject(inited + 158, Executive, 0, 0, 0);
  _InterlockedExchange64((volatile __int64 *)(v64 + 8LL * v61), (__int64)inited);
  EtwpSendSessionNotification(inited, 5);
  if ( (inited[3] & 0x2000000) == 0 )
    goto LABEL_264;
  if ( v62 != EtwpHostSiloState )
    goto LABEL_261;
  LOBYTE(v56) = 1;
  FileName = EtwpCheckForPoolTagFilterExtension(inited, a2, v56);
  if ( FileName >= 0 )
  {
    v57 = 5LL * v18;
    *((_WORD *)EtwpObjectTypeFilter + 2 * v57) = 1;
    *((_DWORD *)EtwpObjectTypeFilter + v57 + 1) = 42;
LABEL_261:
    FileName = EtwpUpdateLoggerGroupMasks(inited, a2);
    if ( FileName >= 0 )
      goto LABEL_264;
  }
  inited[10] = FileName;
  EtwpStopLoggerInstance(inited);
  if ( (inited[3] & 0x400) != 0 )
  {
    EtwpGetLoggerInfoFromContext(a2, inited);
    LOBYTE(v58) = 1;
    EtwpReleaseLoggerContext(inited, v58);
LABEL_254:
    EtwpFreeLoggerContext(inited);
  }
  else
  {
LABEL_264:
    if ( v60 != 9 )
      EtwpUpdatePerProcessTracing(a2, v53, *inited, v60);
    EtwpGetLoggerInfoFromContext(a2, inited);
    LOBYTE(v59) = 1;
    EtwpReleaseLoggerContext(inited, v59);
  }
  return (unsigned int)FileName;
}

```

## disassembly

```asm
0x140ab5434  mov     [rsp-8+arg_10], rbx
0x140ab5439  push    rbp
0x140ab543a  push    rsi
0x140ab543b  push    rdi
0x140ab543c  push    r12
0x140ab543e  push    r13
0x140ab5440  push    r14
0x140ab5442  push    r15
0x140ab5444  lea     rbp, [rsp-20h]
0x140ab5449  sub     rsp, 120h
0x140ab5450  mov     rax, cs:__security_cookie
0x140ab5457  xor     rax, rsp
0x140ab545a  mov     [rbp+50h+var_40], rax
0x140ab545e  xor     edi, edi
0x140ab5460  mov     [rsp+150h+var_108], rcx
0x140ab5465  mov     eax, edi
0x140ab5467  mov     dword ptr [rsp+150h+var_F0], edi
0x140ab546b  xorps   xmm0, xmm0
0x140ab546e  mov     [rsp+150h+var_D8], rax
0x140ab5473  mov     r14, rdx
0x140ab5476  mov     [rsp+150h+SecurityDescriptor], rax
0x140ab547b  xorps   xmm1, xmm1
0x140ab547e  mov     word ptr [rbp+50h+var_A8.Size+2], di
0x140ab5482  xor     edx, edx; SourceString
0x140ab5484  mov     [rsp+150h+var_E8], edi
0x140ab5488  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x140ab548d  movups  xmmword ptr [rbp+50h+Uuid.Data1], xmm0
0x140ab5491  movups  xmmword ptr [rbp+50h+UnicodeString.Length], xmm0
0x140ab5495  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm1
0x140ab549a  call    RtlInitUnicodeString
0x140ab549f  xor     edx, edx; SourceString
0x140ab54a1  lea     rcx, [rbp+50h+UnicodeString]; DestinationString
0x140ab54a5  call    RtlInitUnicodeString
0x140ab54aa  mov     r15d, [r14+40h]
0x140ab54ae  lea     ebx, [rdi+3]
0x140ab54b1  and     r15d, 9DECE5FFh
0x140ab54b8  mov     [rsp+150h+var_10C], ebx
0x140ab54bc  lea     r12d, [rdi+1]
0x140ab54c0  test    bl, r15b
0x140ab54c3  jnz     short loc_140AB54D4
0x140ab54c5  test    r15b, 8
0x140ab54c9  jnz     short loc_140AB54D1
0x140ab54cb  test    r15b, 4
0x140ab54cf  jz      short loc_140AB54D4
0x140ab54d1  or      r15d, r12d
0x140ab54d4  bt      r15d, 12h
0x140ab54d9  jnb     short loc_140AB54E0
0x140ab54db  bts     r15d, 7
0x140ab54e0  bt      r15d, 13h
0x140ab54e5  jnb     short loc_140AB54F3
0x140ab54e7  bt      r15d, 18h
0x140ab54ec  jnb     short loc_140AB54F3
0x140ab54ee  btr     r15d, 18h
0x140ab54f3  lea     rcx, [r14+90h]
0x140ab54fa  cmp     [rcx], di
0x140ab54fd  jbe     loc_140AB56EB
0x140ab5503  cmp     [r14+98h], rdi
0x140ab550a  jz      loc_140AB56EB
0x140ab5510  lea     rdx, [rsp+150h+DestinationString]
0x140ab5515  call    EtwpCaptureString
0x140ab551a  mov     edi, eax
0x140ab551c  test    eax, eax
0x140ab551e  jnz     loc_140AB56F0
0x140ab5524  mov     r8d, 400h
0x140ab552a  xor     edi, edi
0x140ab552c  mov     edx, 100h
0x140ab5531  test    r8d, r15d
0x140ab5534  jz      short loc_140AB556B
0x140ab5536  cmp     [r14+88h], rdi
0x140ab553d  jnz     loc_140AB56EB
0x140ab5543  test    r15b, 0Fh
0x140ab5547  jnz     loc_140AB56EB
0x140ab554d  test    edx, r15d
0x140ab5550  jz      short loc_140AB5557
0x140ab5552  btr     r15d, 8
0x140ab5557  cmp     [r14+44h], edi
0x140ab555b  jz      short loc_140AB5561
0x140ab555d  mov     [r14+44h], edi
0x140ab5561  cmp     [r14+4Ch], edi
0x140ab5565  jz      short loc_140AB556B
0x140ab5567  mov     [r14+4Ch], edi
0x140ab556b  mov     eax, r15d
0x140ab556e  and     eax, ebx
0x140ab5570  cmp     al, bl
0x140ab5572  jz      loc_140AB56EB
0x140ab5578  mov     ecx, 0C000h
0x140ab557d  mov     eax, r15d
0x140ab5580  and     eax, ecx
0x140ab5582  cmp     eax, ecx
0x140ab5584  jz      loc_140AB56EB
0x140ab558a  mov     r13d, r15d
0x140ab558d  and     r13d, edx
0x140ab5590  jnz     short loc_140AB55A4
0x140ab5592  test    r8d, r15d
0x140ab5595  jnz     short loc_140AB55A4
0x140ab5597  cmp     [r14+88h], rdi
0x140ab559e  jz      loc_140AB56EB
0x140ab55a4  mov     ecx, r15d
0x140ab55a7  and     ecx, 2
0x140ab55aa  jz      short loc_140AB55C0
0x140ab55ac  test    r15b, 4
0x140ab55b0  jnz     loc_140AB56EB
0x140ab55b6  cmp     [r14+3Ch], edi
0x140ab55ba  jz      loc_140AB56EB
0x140ab55c0  test    r15b, 20h
0x140ab55c4  jz      short loc_140AB55DC
0x140ab55c6  cmp     [r14+3Ch], edi
0x140ab55ca  jz      loc_140AB56EB
0x140ab55d0  mov     eax, [r14+40h]
0x140ab55d4  test    al, 0Ch
0x140ab55d6  jnz     loc_140AB56EB
0x140ab55dc  test    r15b, 40h
0x140ab55e0  jz      short loc_140AB560D
0x140ab55e2  mov     eax, [r14+70h]
0x140ab55e6  test    al, 2
0x140ab55e8  jz      loc_140AB56EB
0x140ab55ee  test    ecx, ecx
0x140ab55f0  jnz     short loc_140AB560D
0x140ab55f2  test    r8d, r15d
0x140ab55f5  jnz     short loc_140AB560D
0x140ab55f7  test    r13d, r13d
0x140ab55fa  jz      loc_140AB56EB
0x140ab5600  cmp     [r14+88h], rdi
0x140ab5607  jnz     loc_140AB56EB
0x140ab560d  mov     eax, 0C00000h
0x140ab5612  mov     esi, r15d
0x140ab5615  and     esi, eax
0x140ab5617  cmp     esi, eax
0x140ab5619  jz      loc_140AB56EB
0x140ab561f  test    r15b, 8
0x140ab5623  jz      short loc_140AB569C
0x140ab5625  cmp     [r14+88h], rdi
0x140ab562c  jz      loc_140AB56EB
0x140ab5632  test    ecx, ecx
0x140ab5634  jnz     loc_140AB56EB
0x140ab563a  cmp     [r14+3Ch], edi
0x140ab563e  jz      loc_140AB56EB
0x140ab5644  mov     eax, [r14+70h]
0x140ab5648  test    al, 2
0x140ab564a  jnz     loc_140AB56EB
0x140ab5650  test    dword ptr [r14+40h], 2000000h
0x140ab5658  jnz     loc_140AB56EB
0x140ab565e  lea     r8d, [rcx+10h]; Size
0x140ab5662  lea     rcx, [r14+18h]; Buf1
0x140ab5666  lea     rdx, SystemTraceControlGuid; Buf2
0x140ab566d  call    memcmp
0x140ab5672  test    eax, eax
0x140ab5674  jz      short loc_140AB56EB
0x140ab5676  mov     r8d, 10h; Size
0x140ab567c  lea     rdx, CKCLGuid; Buf2
0x140ab5683  lea     rcx, [r14+18h]; Buf1
0x140ab5687  call    memcmp
0x140ab568c  test    eax, eax
0x140ab568e  jz      short loc_140AB56EB
0x140ab5690  test    r15b, 4
0x140ab5694  jnz     short loc_140AB56EB
0x140ab5696  mov     r8d, 400h
0x140ab569c  mov     ecx, [r14+40h]
0x140ab56a0  mov     edx, ecx
0x140ab56a2  and     edx, 2000000h
0x140ab56a8  jz      short loc_140AB56B0
0x140ab56aa  bt      ecx, 18h
0x140ab56ae  jb      short loc_140AB56EB
0x140ab56b0  bt      ecx, 1Ah
0x140ab56b4  jnb     short loc_140AB56BE
0x140ab56b6  test    ecx, 106h
0x140ab56bc  jnz     short loc_140AB56EB
0x140ab56be  bt      ecx, 10h
0x140ab56c2  jb      short loc_140AB56EB
0x140ab56c4  test    byte ptr [r14+50h], 4
0x140ab56c9  jz      loc_140AB57B6
0x140ab56cf  cmp     cs:EtwpKsrCallbackObject, rdi
0x140ab56d6  jz      loc_140AB5771
0x140ab56dc  test    r8d, ecx
0x140ab56df  jz      short loc_140AB56EB
0x140ab56e1  bt      ecx, 18h
0x140ab56e5  jnb     loc_140AB57B6
0x140ab56eb  mov     edi, 0C000000Dh
0x140ab56f0  mov     rcx, cs:EtwpEventTracingProvRegHandle; RegHandle
0x140ab56f7  lea     rdx, ETW_EVENT_SESSION_START_FAILED; EventDescriptor
0x140ab56fe  call    EtwEventEnabled
0x140ab5703  test    al, al
0x140ab5705  jz      short loc_140AB572A
0x140ab5707  mov     [rsp+150h+var_120], r15d
0x140ab570c  lea     rax, [rbp+50h+UnicodeString]
0x140ab5710  mov     dword ptr [rsp+150h+var_128], edi
0x140ab5714  lea     r9, [rsp+150h+DestinationString]
0x140ab5719  lea     rdx, ETW_EVENT_SESSION_START_FAILED
0x140ab5720  mov     [rsp+150h+UserData], rax
0x140ab5725  call    EtwpEventWriteTemplateAdmin
0x140ab572a  lea     rcx, [rsp+150h+DestinationString]; UnicodeString
0x140ab572f  call    RtlFreeAnsiString
0x140ab5734  lea     rcx, [rbp+50h+UnicodeString]; UnicodeString
0x140ab5738  call    RtlFreeAnsiString
0x140ab573d  lea     rcx, [rsp+150h+SecurityDescriptor]
0x140ab5742  call    EtwpFreeSecurityDescriptor
0x140ab5747  mov     eax, edi
0x140ab5749  mov     rcx, [rbp+50h+var_40]
0x140ab574d  xor     rcx, rsp; StackCookie
0x140ab5750  call    __security_check_cookie
0x140ab5755  mov     rbx, [rsp+150h+arg_10]
0x140ab575d  add     rsp, 120h
0x140ab5764  pop     r15
0x140ab5766  pop     r14
0x140ab5768  pop     r13
0x140ab576a  pop     r12
0x140ab576c  pop     rdi
0x140ab576d  pop     rsi
0x140ab576e  pop     rbp
0x140ab576f  retn
0x140ab5771  mov     rcx, cs:EtwpEventTracingProvRegHandle; RegHandle
0x140ab5778  lea     rdx, ETW_EVENT_LARGE_MDL_NOT_SUPPORTED; EventDescriptor
0x140ab577f  mov     edi, 0C00000BBh
0x140ab5784  call    EtwEventEnabled
0x140ab5789  test    al, al
0x140ab578b  jz      loc_140AB56F0
0x140ab5791  mov     r9d, [r14+40h]
0x140ab5795  lea     rax, [rbp+50h+UnicodeString]
0x140ab5799  mov     [rsp+150h+var_128], rax
0x140ab579e  lea     r8, [r14+18h]
0x140ab57a2  lea     rax, [rsp+150h+DestinationString]
0x140ab57a7  mov     [rsp+150h+UserData], rax
0x140ab57ac  call    EtwpEventWriteTemplateSessionFromCapturedData
0x140ab57b1  jmp     loc_140AB56F0
0x140ab57b6  mov     eax, [r14+70h]
0x140ab57ba  test    eax, eax
0x140ab57bc  jns     short loc_140AB580F
0x140ab57be  cmp     cs:EtwpBootPhase, dil
0x140ab57c5  jnz     loc_140AB56EB
0x140ab57cb  test    al, 2
0x140ab57cd  jz      loc_140AB56EB
0x140ab57d3  test    edx, edx
0x140ab57d5  jz      loc_140AB56EB
0x140ab57db  mov     eax, [r14+28h]
0x140ab57df  sub     eax, 2
0x140ab57e2  test    eax, 0FFFFFFFDh
0x140ab57e7  jz      loc_140AB56EB
0x140ab57ed  lea     rbx, [r14+18h]
0x140ab57f1  mov     r8d, 10h; Size
0x140ab57f7  mov     rcx, rbx; Buf1
0x140ab57fa  lea     rdx, NullGuid; Buf2
0x140ab5801  call    memcmp
0x140ab5806  test    eax, eax
0x140ab5808  jnz     short loc_140AB5813
0x140ab580a  jmp     loc_140AB56EB
0x140ab580f  lea     rbx, [r14+18h]
0x140ab5813  mov     rcx, r14
0x140ab5816  call    EtwpValidateFlagExtension
0x140ab581b  mov     edi, eax
0x140ab581d  test    eax, eax
0x140ab581f  js      loc_140AB56F0
0x140ab5825  neg     r13d
0x140ab5828  lea     r8, [rsp+150h+var_F0]
0x140ab582d  sbb     ecx, ecx
0x140ab582f  xor     edi, edi
0x140ab5831  and     ecx, 20h
0x140ab5834  sub     ecx, 0FFFFFF80h
0x140ab5837  mov     edx, ecx
0x140ab5839  or      edx, 40h
0x140ab583c  cmp     [r14+80h], di
0x140ab5844  cmovz   edx, ecx
0x140ab5847  mov     rcx, [rsp+150h+var_108]
0x140ab584c  mov     [rbp+50h+DesiredAccess], edx
0x140ab584f  lea     rdx, [rsp+150h+DestinationString]
0x140ab5854  call    EtwpLookupLoggerIdByName
0x140ab5859  test    eax, eax
0x140ab585b  jnz     short loc_140AB5867
0x140ab585d  mov     edi, 0C0000035h
0x140ab5862  jmp     loc_140AB56F0
0x140ab5867  mov     r13d, 10h
0x140ab586d  lea     rdx, NullGuid; Buf2
0x140ab5874  mov     r8d, r13d; Size
0x140ab5877  mov     rcx, rbx; Buf1
0x140ab587a  call    memcmp
0x140ab587f  test    eax, eax
0x140ab5881  jnz     short loc_140AB589A
0x140ab5883  lea     rcx, [rbp+50h+Uuid]; Uuid
0x140ab5887  call    ExUuidCreate
0x140ab588c  mov     edi, eax
0x140ab588e  test    eax, eax
0x140ab5890  js      loc_140AB56F0
0x140ab5896  xor     edi, edi
0x140ab5898  jmp     short loc_140AB58A2
0x140ab589a  movups  xmm0, xmmword ptr [rbx]
0x140ab589d  movdqu  xmmword ptr [rbp+50h+Uuid.Data1], xmm0
0x140ab58a2  test    esi, esi
0x140ab58a4  jnz     short loc_140AB58DD
0x140ab58a6  mov     rax, gs:188h
0x140ab58af  cmp     [rax+232h], dil
0x140ab58b6  jz      short loc_140AB58D8
0x140ab58b8  mov     rcx, gs:188h
0x140ab58c1  mov     rcx, [rcx+0B8h]
0x140ab58c8  call    PsGetSessionId
0x140ab58cd  test    eax, eax
0x140ab58cf  jz      short loc_140AB58D8
0x140ab58d1  bts     r15d, 16h
0x140ab58d6  jmp     short loc_140AB58DD
0x140ab58d8  bts     r15d, 17h
0x140ab58dd  mov     rbx, [rsp+150h+var_108]
0x140ab58e2  lea     rdx, SystemTraceControlGuid; Buf2
  ... truncated ...
```
