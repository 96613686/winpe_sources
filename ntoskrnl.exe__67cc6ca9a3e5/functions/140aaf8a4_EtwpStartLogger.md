# EtwpStartLogger

- ea: `0x140aaf8a4`
- end: `0x140ab0918`
- name: `EtwpStartLogger`
- size: `4212`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `56`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140aaf834`
- `0x140ad9fbc`
- `0x140c83918`

## callees

- `0x140223fb0`
- `0x140272040`
- `0x1402bb4b0`
- `0x1402f92c0`
- `0x140307470`
- `0x1403075d0`
- `0x14030aec0`
- `0x1403f2d50`
- `0x14041368c`
- `0x1404a3150`
- `0x1404afb50`
- `0x1404bcea4`
- `0x1404e7c00`
- `0x14053cf40`
- `0x14067ed58`
- `0x1406d9d70`
- `0x1406daa70`
- `0x1406f4750`
- `0x1407d6040`
- `0x1407d60d0`
- `0x1407d6168`
- `0x1407d6234`
- `0x140861930`
- `0x1408619e0`
- `0x140861f80`
- `0x140869d40`
- `0x1408ad040`
- `0x1408eeff0`
- `0x14094eb7c`
- `0x14094ec90`
- `0x14094ee30`
- `0x14094ef64`
- `0x14094f030`
- `0x14094f5f4`
- `0x14094f870`
- `0x140951024`
- `0x140951364`
- `0x1409590c0`
- `0x140964ff0`
- `0x1409650e4`
- `0x140965a98`
- `0x1409b3930`
- `0x1409f24f4`
- `0x140a19da8`
- `0x140a30ad4`
- `0x140a8f198`
- `0x140a9059c`
- `0x140aaf8a4`
- `0x140abb0a8`
- `0x140abf1b0`

## string_xrefs

- `0x140aafe44`: `Eventlog-Security`
- `0x140aaff06`: `Eventlog-Security`

## pseudocode

```c
__int64 __fastcall EtwpStartLogger(__int64 a1, __int64 a2)
{
  unsigned int v3; // r15d
  int FileName; // edi
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
  unsigned __int16 *FlagExtension; // rax
  __int16 v33; // dx
  unsigned __int16 *v34; // rbx
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
    if ( !*(_QWORD *)&PspActiveProcessLock.SchedulerApc.Type )
    {
      FileName = -1073741637;
      if ( EtwEventEnabled(ExpKeyManipLock.KcsanThread, &ETW_EVENT_LARGE_MDL_NOT_SUPPORTED) )
        EtwpEventWriteTemplateSessionFromCapturedData(
          v11,
          v10,
          a2 + 24,
          *(_DWORD *)(a2 + 64),
          (__int64)&DestinationString,
          (__int64)&UnicodeString);
LABEL_59:
      if ( EtwEventEnabled(ExpKeyManipLock.KcsanThread, &ETW_EVENT_SESSION_START_FAILED) )
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
    if ( byte_140EED4E0 )
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
  FileName = EtwpValidateFlagExtension((unsigned int *)a2);
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
    if ( !BYTE1(stru_140E44BE8.ThreadFlags2) )
    {
      BYTE1(stru_140E44BE8.ThreadFlags2) = 1;
      UserData.Ptr = v62 + 16;
      *(_QWORD *)&UserData.Size = 4;
      EtwWrite(ExpKeyManipLock.KcsanThread, &ETW_EVENT_OUT_OF_LOGGER_SLOTS, 0, 1u, &UserData);
      if ( (unsigned int)dword_140E0C6D0 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_140E0C6D0, 0x200000000000LL) )
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
          tlgWriteAgg((int)&dword_140E0C6D0, (int)&byte_140054AF8, v27, 5, &v72);
        }
      }
    }
    FileName = -1073741670;
    if ( EtwEventEnabled(ExpKeyManipLock.KcsanThread, &ETW_EVENT_NOT_ENOUGH_LOGGER_SLOTS) )
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
      if ( EtwEventEnabled(ExpKeyManipLock.KcsanThread, &ETW_EVENT_START_TRACE_ACCESS_DENIED) )
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
          if ( EtwEventEnabled(ExpKeyManipLock.KcsanThread, &ETW_EVENT_NOT_ENOUGH_SYSTEM_LOGGER_SLOTS) )
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
    if ( 4 * *FlagExtension == v33 + 6 )
    {
      FileName = EtwpSetPartitionContext(inited + 396, *(_QWORD *)(FlagExtension + 2));
      if ( FileName < 0 )
      {
        if ( EtwEventEnabled(ExpKeyManipLock.KcsanThread, &ETW_EVENT_INVALID_MEMORY_PARTITION) )
          EtwpEventWriteTemplateSessionAndHandle(v36, v35, &DestinationString, *(_QWORD *)(v34 + 2));
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
      _InterlockedDecrement((volatile signed __int32 *)&stru_140E2CD00.PriorityFloorCounts[8]);
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
    Pool2 = ExAllocatePool2(64, inited[1], 1517777989);
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
  if ( EtwEventEnabled(ExpKeyManipLock.KcsanThread, &ETW_EVENT_START_TRACE) )
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
    *((_WORD *)&unk_140EED380 + 2 * v57) = 1;
    *((_DWORD *)&unk_140EED380 + v57 + 1) = 42;
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
0x140aaf8a4  mov     [rsp-8+arg_10], rbx
0x140aaf8a9  push    rbp
0x140aaf8aa  push    rsi
0x140aaf8ab  push    rdi
0x140aaf8ac  push    r12
0x140aaf8ae  push    r13
0x140aaf8b0  push    r14
0x140aaf8b2  push    r15
0x140aaf8b4  lea     rbp, [rsp-20h]
0x140aaf8b9  sub     rsp, 120h
0x140aaf8c0  mov     rax, cs:__security_cookie
0x140aaf8c7  xor     rax, rsp
0x140aaf8ca  mov     [rbp+50h+var_40], rax
0x140aaf8ce  xor     edi, edi
0x140aaf8d0  mov     [rsp+150h+var_108], rcx
0x140aaf8d5  mov     eax, edi
0x140aaf8d7  mov     dword ptr [rsp+150h+var_F0], edi
0x140aaf8db  xorps   xmm0, xmm0
0x140aaf8de  mov     [rsp+150h+var_D8], rax
0x140aaf8e3  mov     r14, rdx
0x140aaf8e6  mov     [rsp+150h+SecurityDescriptor], rax
0x140aaf8eb  xorps   xmm1, xmm1
0x140aaf8ee  mov     word ptr [rbp+50h+var_A8.Size+2], di
0x140aaf8f2  xor     edx, edx; SourceString
0x140aaf8f4  mov     [rsp+150h+var_E8], edi
0x140aaf8f8  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x140aaf8fd  movups  xmmword ptr [rbp+50h+Uuid.Data1], xmm0
0x140aaf901  movups  xmmword ptr [rbp+50h+UnicodeString.Length], xmm0
0x140aaf905  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm1
0x140aaf90a  call    RtlInitUnicodeString
0x140aaf90f  xor     edx, edx; SourceString
0x140aaf911  lea     rcx, [rbp+50h+UnicodeString]; DestinationString
0x140aaf915  call    RtlInitUnicodeString
0x140aaf91a  mov     r15d, [r14+40h]
0x140aaf91e  lea     ebx, [rdi+3]
0x140aaf921  and     r15d, 9DECE5FFh
0x140aaf928  mov     [rsp+150h+var_10C], ebx
0x140aaf92c  lea     r12d, [rdi+1]
0x140aaf930  test    bl, r15b
0x140aaf933  jnz     short loc_140AAF944
0x140aaf935  test    r15b, 8
0x140aaf939  jnz     short loc_140AAF941
0x140aaf93b  test    r15b, 4
0x140aaf93f  jz      short loc_140AAF944
0x140aaf941  or      r15d, r12d
0x140aaf944  bt      r15d, 12h
0x140aaf949  jnb     short loc_140AAF950
0x140aaf94b  bts     r15d, 7
0x140aaf950  bt      r15d, 13h
0x140aaf955  jnb     short loc_140AAF963
0x140aaf957  bt      r15d, 18h
0x140aaf95c  jnb     short loc_140AAF963
0x140aaf95e  btr     r15d, 18h
0x140aaf963  lea     rcx, [r14+90h]
0x140aaf96a  cmp     [rcx], di
0x140aaf96d  jbe     loc_140AAFB5B
0x140aaf973  cmp     [r14+98h], rdi
0x140aaf97a  jz      loc_140AAFB5B
0x140aaf980  lea     rdx, [rsp+150h+DestinationString]
0x140aaf985  call    EtwpCaptureString
0x140aaf98a  mov     edi, eax
0x140aaf98c  test    eax, eax
0x140aaf98e  jnz     loc_140AAFB60
0x140aaf994  mov     r8d, 400h
0x140aaf99a  xor     edi, edi
0x140aaf99c  mov     edx, 100h
0x140aaf9a1  test    r8d, r15d
0x140aaf9a4  jz      short loc_140AAF9DB
0x140aaf9a6  cmp     [r14+88h], rdi
0x140aaf9ad  jnz     loc_140AAFB5B
0x140aaf9b3  test    r15b, 0Fh
0x140aaf9b7  jnz     loc_140AAFB5B
0x140aaf9bd  test    edx, r15d
0x140aaf9c0  jz      short loc_140AAF9C7
0x140aaf9c2  btr     r15d, 8
0x140aaf9c7  cmp     [r14+44h], edi
0x140aaf9cb  jz      short loc_140AAF9D1
0x140aaf9cd  mov     [r14+44h], edi
0x140aaf9d1  cmp     [r14+4Ch], edi
0x140aaf9d5  jz      short loc_140AAF9DB
0x140aaf9d7  mov     [r14+4Ch], edi
0x140aaf9db  mov     eax, r15d
0x140aaf9de  and     eax, ebx
0x140aaf9e0  cmp     al, bl
0x140aaf9e2  jz      loc_140AAFB5B
0x140aaf9e8  mov     ecx, 0C000h
0x140aaf9ed  mov     eax, r15d
0x140aaf9f0  and     eax, ecx
0x140aaf9f2  cmp     eax, ecx
0x140aaf9f4  jz      loc_140AAFB5B
0x140aaf9fa  mov     r13d, r15d
0x140aaf9fd  and     r13d, edx
0x140aafa00  jnz     short loc_140AAFA14
0x140aafa02  test    r8d, r15d
0x140aafa05  jnz     short loc_140AAFA14
0x140aafa07  cmp     [r14+88h], rdi
0x140aafa0e  jz      loc_140AAFB5B
0x140aafa14  mov     ecx, r15d
0x140aafa17  and     ecx, 2
0x140aafa1a  jz      short loc_140AAFA30
0x140aafa1c  test    r15b, 4
0x140aafa20  jnz     loc_140AAFB5B
0x140aafa26  cmp     [r14+3Ch], edi
0x140aafa2a  jz      loc_140AAFB5B
0x140aafa30  test    r15b, 20h
0x140aafa34  jz      short loc_140AAFA4C
0x140aafa36  cmp     [r14+3Ch], edi
0x140aafa3a  jz      loc_140AAFB5B
0x140aafa40  mov     eax, [r14+40h]
0x140aafa44  test    al, 0Ch
0x140aafa46  jnz     loc_140AAFB5B
0x140aafa4c  test    r15b, 40h
0x140aafa50  jz      short loc_140AAFA7D
0x140aafa52  mov     eax, [r14+70h]
0x140aafa56  test    al, 2
0x140aafa58  jz      loc_140AAFB5B
0x140aafa5e  test    ecx, ecx
0x140aafa60  jnz     short loc_140AAFA7D
0x140aafa62  test    r8d, r15d
0x140aafa65  jnz     short loc_140AAFA7D
0x140aafa67  test    r13d, r13d
0x140aafa6a  jz      loc_140AAFB5B
0x140aafa70  cmp     [r14+88h], rdi
0x140aafa77  jnz     loc_140AAFB5B
0x140aafa7d  mov     eax, 0C00000h
0x140aafa82  mov     esi, r15d
0x140aafa85  and     esi, eax
0x140aafa87  cmp     esi, eax
0x140aafa89  jz      loc_140AAFB5B
0x140aafa8f  test    r15b, 8
0x140aafa93  jz      short loc_140AAFB0C
0x140aafa95  cmp     [r14+88h], rdi
0x140aafa9c  jz      loc_140AAFB5B
0x140aafaa2  test    ecx, ecx
0x140aafaa4  jnz     loc_140AAFB5B
0x140aafaaa  cmp     [r14+3Ch], edi
0x140aafaae  jz      loc_140AAFB5B
0x140aafab4  mov     eax, [r14+70h]
0x140aafab8  test    al, 2
0x140aafaba  jnz     loc_140AAFB5B
0x140aafac0  test    dword ptr [r14+40h], 2000000h
0x140aafac8  jnz     loc_140AAFB5B
0x140aaface  lea     r8d, [rcx+10h]; Size
0x140aafad2  lea     rcx, [r14+18h]; Buf1
0x140aafad6  lea     rdx, SystemTraceControlGuid; Buf2
0x140aafadd  call    memcmp
0x140aafae2  test    eax, eax
0x140aafae4  jz      short loc_140AAFB5B
0x140aafae6  mov     r8d, 10h; Size
0x140aafaec  lea     rdx, CKCLGuid; Buf2
0x140aafaf3  lea     rcx, [r14+18h]; Buf1
0x140aafaf7  call    memcmp
0x140aafafc  test    eax, eax
0x140aafafe  jz      short loc_140AAFB5B
0x140aafb00  test    r15b, 4
0x140aafb04  jnz     short loc_140AAFB5B
0x140aafb06  mov     r8d, 400h
0x140aafb0c  mov     ecx, [r14+40h]
0x140aafb10  mov     edx, ecx
0x140aafb12  and     edx, 2000000h
0x140aafb18  jz      short loc_140AAFB20
0x140aafb1a  bt      ecx, 18h
0x140aafb1e  jb      short loc_140AAFB5B
0x140aafb20  bt      ecx, 1Ah
0x140aafb24  jnb     short loc_140AAFB2E
0x140aafb26  test    ecx, 106h
0x140aafb2c  jnz     short loc_140AAFB5B
0x140aafb2e  bt      ecx, 10h
0x140aafb32  jb      short loc_140AAFB5B
0x140aafb34  test    byte ptr [r14+50h], 4
0x140aafb39  jz      loc_140AAFC26
0x140aafb3f  cmp     qword ptr cs:PspActiveProcessLock.___u58, rdi
0x140aafb46  jz      loc_140AAFBE1
0x140aafb4c  test    r8d, ecx
0x140aafb4f  jz      short loc_140AAFB5B
0x140aafb51  bt      ecx, 18h
0x140aafb55  jnb     loc_140AAFC26
0x140aafb5b  mov     edi, 0C000000Dh
0x140aafb60  mov     rcx, cs:ExpKeyManipLock.KcsanThread; RegHandle
0x140aafb67  lea     rdx, ETW_EVENT_SESSION_START_FAILED; EventDescriptor
0x140aafb6e  call    EtwEventEnabled
0x140aafb73  test    al, al
0x140aafb75  jz      short loc_140AAFB9A
0x140aafb77  mov     [rsp+150h+var_120], r15d
0x140aafb7c  lea     rax, [rbp+50h+UnicodeString]
0x140aafb80  mov     dword ptr [rsp+150h+var_128], edi
0x140aafb84  lea     r9, [rsp+150h+DestinationString]
0x140aafb89  lea     rdx, ETW_EVENT_SESSION_START_FAILED
0x140aafb90  mov     [rsp+150h+UserData], rax
0x140aafb95  call    EtwpEventWriteTemplateAdmin
0x140aafb9a  lea     rcx, [rsp+150h+DestinationString]; UnicodeString
0x140aafb9f  call    RtlFreeAnsiString
0x140aafba4  lea     rcx, [rbp+50h+UnicodeString]; UnicodeString
0x140aafba8  call    RtlFreeAnsiString
0x140aafbad  lea     rcx, [rsp+150h+SecurityDescriptor]
0x140aafbb2  call    EtwpFreeSecurityDescriptor
0x140aafbb7  mov     eax, edi
0x140aafbb9  mov     rcx, [rbp+50h+var_40]
0x140aafbbd  xor     rcx, rsp; StackCookie
0x140aafbc0  call    __security_check_cookie
0x140aafbc5  mov     rbx, [rsp+150h+arg_10]
0x140aafbcd  add     rsp, 120h
0x140aafbd4  pop     r15
0x140aafbd6  pop     r14
0x140aafbd8  pop     r13
0x140aafbda  pop     r12
0x140aafbdc  pop     rdi
0x140aafbdd  pop     rsi
0x140aafbde  pop     rbp
0x140aafbdf  retn
0x140aafbe1  mov     rcx, cs:ExpKeyManipLock.KcsanThread; RegHandle
0x140aafbe8  lea     rdx, ETW_EVENT_LARGE_MDL_NOT_SUPPORTED; EventDescriptor
0x140aafbef  mov     edi, 0C00000BBh
0x140aafbf4  call    EtwEventEnabled
0x140aafbf9  test    al, al
0x140aafbfb  jz      loc_140AAFB60
0x140aafc01  mov     r9d, [r14+40h]
0x140aafc05  lea     rax, [rbp+50h+UnicodeString]
0x140aafc09  mov     [rsp+150h+var_128], rax
0x140aafc0e  lea     r8, [r14+18h]
0x140aafc12  lea     rax, [rsp+150h+DestinationString]
0x140aafc17  mov     [rsp+150h+UserData], rax
0x140aafc1c  call    EtwpEventWriteTemplateSessionFromCapturedData
0x140aafc21  jmp     loc_140AAFB60
0x140aafc26  mov     eax, [r14+70h]
0x140aafc2a  test    eax, eax
0x140aafc2c  jns     short loc_140AAFC7F
0x140aafc2e  cmp     cs:byte_140EED4E0, dil
0x140aafc35  jnz     loc_140AAFB5B
0x140aafc3b  test    al, 2
0x140aafc3d  jz      loc_140AAFB5B
0x140aafc43  test    edx, edx
0x140aafc45  jz      loc_140AAFB5B
0x140aafc4b  mov     eax, [r14+28h]
0x140aafc4f  sub     eax, 2
0x140aafc52  test    eax, 0FFFFFFFDh
0x140aafc57  jz      loc_140AAFB5B
0x140aafc5d  lea     rbx, [r14+18h]
0x140aafc61  mov     r8d, 10h; Size
0x140aafc67  mov     rcx, rbx; Buf1
0x140aafc6a  lea     rdx, NullGuid; Buf2
0x140aafc71  call    memcmp
0x140aafc76  test    eax, eax
0x140aafc78  jnz     short loc_140AAFC83
0x140aafc7a  jmp     loc_140AAFB5B
0x140aafc7f  lea     rbx, [r14+18h]
0x140aafc83  mov     rcx, r14
0x140aafc86  call    EtwpValidateFlagExtension
0x140aafc8b  mov     edi, eax
0x140aafc8d  test    eax, eax
0x140aafc8f  js      loc_140AAFB60
0x140aafc95  neg     r13d
0x140aafc98  lea     r8, [rsp+150h+var_F0]
0x140aafc9d  sbb     ecx, ecx
0x140aafc9f  xor     edi, edi
0x140aafca1  and     ecx, 20h
0x140aafca4  sub     ecx, 0FFFFFF80h
0x140aafca7  mov     edx, ecx
0x140aafca9  or      edx, 40h
0x140aafcac  cmp     [r14+80h], di
0x140aafcb4  cmovz   edx, ecx
0x140aafcb7  mov     rcx, [rsp+150h+var_108]
0x140aafcbc  mov     [rbp+50h+DesiredAccess], edx
0x140aafcbf  lea     rdx, [rsp+150h+DestinationString]
0x140aafcc4  call    EtwpLookupLoggerIdByName
0x140aafcc9  test    eax, eax
0x140aafccb  jnz     short loc_140AAFCD7
0x140aafccd  mov     edi, 0C0000035h
0x140aafcd2  jmp     loc_140AAFB60
0x140aafcd7  mov     r13d, 10h
0x140aafcdd  lea     rdx, NullGuid; Buf2
0x140aafce4  mov     r8d, r13d; Size
0x140aafce7  mov     rcx, rbx; Buf1
0x140aafcea  call    memcmp
0x140aafcef  test    eax, eax
0x140aafcf1  jnz     short loc_140AAFD0A
0x140aafcf3  lea     rcx, [rbp+50h+Uuid]; Uuid
0x140aafcf7  call    ExUuidCreate
0x140aafcfc  mov     edi, eax
0x140aafcfe  test    eax, eax
0x140aafd00  js      loc_140AAFB60
0x140aafd06  xor     edi, edi
0x140aafd08  jmp     short loc_140AAFD12
0x140aafd0a  movups  xmm0, xmmword ptr [rbx]
0x140aafd0d  movdqu  xmmword ptr [rbp+50h+Uuid.Data1], xmm0
0x140aafd12  test    esi, esi
0x140aafd14  jnz     short loc_140AAFD4D
0x140aafd16  mov     rax, gs:188h
0x140aafd1f  cmp     [rax+232h], dil
0x140aafd26  jz      short loc_140AAFD48
0x140aafd28  mov     rcx, gs:188h
0x140aafd31  mov     rcx, [rcx+0B8h]
0x140aafd38  call    PsGetSessionId
0x140aafd3d  test    eax, eax
0x140aafd3f  jz      short loc_140AAFD48
0x140aafd41  bts     r15d, 16h
0x140aafd46  jmp     short loc_140AAFD4D
0x140aafd48  bts     r15d, 17h
0x140aafd4d  mov     rbx, [rsp+150h+var_108]
0x140aafd52  lea     rdx, SystemTraceControlGuid; Buf2
  ... truncated ...
```
