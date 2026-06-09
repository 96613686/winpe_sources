# PsmpChangeApplicationState

- ea: `0x1800114d0`
- end: `0x1800128b4`
- name: `PsmpChangeApplicationState`
- size: `5092`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 (__fastcall *)(__int64, __int64, unsigned int *, __int64 *), unsigned int, char, _BYTE *)`
- caller_count: `13`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180001230`
- `0x18000e0f4`
- `0x180010228`
- `0x180010600`
- `0x1800113b0`
- `0x180011448`
- `0x1800162b0`
- `0x180016544`
- `0x180017768`
- `0x1800184a0`
- `0x180019100`
- `0x18001cf00`
- `0x18002c250`

## callees

- `0x180003504`
- `0x180009b40`
- `0x18000da40`
- `0x18000db88`
- `0x18000dbd0`
- `0x18000e9a0`
- `0x18000ec9c`
- `0x18000f064`
- `0x18000f2a4`
- `0x180010968`
- `0x180010b40`
- `0x1800114d0`
- `0x1800138a8`
- `0x180013960`
- `0x180014df4`
- `0x180018e98`
- `0x18001b7e0`
- `0x18001c10c`
- `0x18001c1a4`
- `0x18001d3b8`
- `0x18001e760`
- `0x18002296c`
- `0x18002e17c`
- `0x18002f010`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18001238d`
- `ntdll!RtlCopySid` at `0x18001238d`
- `ntdll!RtlWakeAllConditionVariable` at `0x1800126fa`
- `ntdll!RtlWakeAllConditionVariable` at `0x1800126fa`
- `ntdll!NtSetInformationJobObject` at `0x180011820`
- `ntdll!NtSetInformationJobObject` at `0x180011e67`
- `ntdll!NtSetInformationJobObject` at `0x180011820`
- `ntdll!NtSetInformationJobObject` at `0x180011e67`
- `ntdll!RtlSleepConditionVariableSRW` at `0x1800116c3`
- `ntdll!RtlSleepConditionVariableSRW` at `0x1800116c3`
- `ntdll!RtlAllocateHeap` at `0x180012362`
- `ntdll!RtlAllocateHeap` at `0x180012362`
- `ntdll!RtlQueryUnbiasedInterruptTime` at `0x18001164a`
- `ntdll!RtlQueryUnbiasedInterruptTime` at `0x1800116a9`
- `ntdll!RtlQueryUnbiasedInterruptTime` at `0x18001164a`
- `ntdll!RtlQueryUnbiasedInterruptTime` at `0x1800116a9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180011603`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180012275`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180012331`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180011603`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180012275`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180012331`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001162c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800116fe`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001176a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180011ddf`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800122fb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800123cd`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800126e8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001162c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800116fe`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001176a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180011ddf`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800122fb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800123cd`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800126e8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800115e5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011a03`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011c29`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001205a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800121d7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012830`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800115e5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011a03`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011c29`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001205a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800121d7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012830`

## pseudocode

```c
__int64 __fastcall PsmpChangeApplicationState(
        __int64 a1,
        __int64 a2,
        __int64 (__fastcall *a3)(__int64, __int64, unsigned int *, __int64 *),
        unsigned int a4,
        char a5,
        _BYTE *a6)
{
  __int64 v6; // rsi
  int v7; // eax
  int v8; // ebx
  int v9; // r14d
  _DWORD *v10; // rdi
  _DWORD *v11; // rbx
  unsigned int v12; // r9d
  int v13; // eax
  unsigned int v14; // eax
  __int16 *v15; // rdx
  unsigned int v16; // edi
  int v17; // r12d
  char v18; // bl
  int v19; // r13d
  int v20; // r15d
  int v21; // ecx
  void *v22; // rdi
  NTSTATUS v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  char *v26; // rcx
  __int64 v27; // rax
  bool v28; // zf
  unsigned int v29; // eax
  __int64 v30; // rax
  unsigned int v31; // ecx
  __int64 v32; // r15
  int v33; // eax
  signed __int8 v34; // r14
  __int64 v35; // r8
  unsigned int v36; // r9d
  __int64 v37; // r8
  __int64 v38; // rdx
  _QWORD *i; // rcx
  __int64 v40; // rcx
  unsigned int v41; // r9d
  __int64 v42; // rdx
  int v43; // r12d
  int v44; // ecx
  unsigned int v45; // eax
  void *v46; // rdi
  NTSTATUS v47; // eax
  __int64 v48; // r8
  char *v49; // rcx
  __int64 v50; // rax
  unsigned int v51; // eax
  __int64 v52; // rax
  int v53; // ecx
  __int64 v54; // rdx
  __int64 v55; // rdx
  char *v56; // rcx
  __int64 v57; // rax
  unsigned int v58; // eax
  __int64 v59; // r8
  unsigned int v60; // eax
  __int64 v61; // r8
  int v62; // eax
  __int64 v63; // r9
  int v64; // edx
  __int64 v65; // rdx
  _BYTE *v66; // rdx
  __int64 v67; // rax
  _WORD *v68; // r12
  void *v69; // rcx
  __int64 v70; // rdi
  _DWORD *Heap; // rax
  _DWORD *v72; // r15
  __int64 v73; // rcx
  int v74; // r12d
  __int64 v75; // rcx
  int v76; // edx
  __int64 v77; // r10
  __int64 v78; // r9
  int v79; // r8d
  int v80; // r8d
  BOOL v81; // eax
  __int64 v82; // rcx
  int v83; // edx
  __int64 v84; // r10
  __int64 v85; // r9
  int v86; // r8d
  int v87; // r8d
  BOOL v88; // eax
  _QWORD *v89; // rdi
  __int64 v90; // rcx
  int v91; // edx
  __int64 v92; // r10
  __int64 v93; // r9
  int v94; // r8d
  int v95; // r8d
  BOOL v96; // eax
  int v98; // [rsp+38h] [rbp-D0h] BYREF
  unsigned int v99; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v100; // [rsp+48h] [rbp-C0h] BYREF
  char v101; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v102; // [rsp+50h] [rbp-B8h] BYREF
  __int64 (__fastcall *v103)(__int64, __int64, unsigned int *, __int64 *); // [rsp+58h] [rbp-B0h] BYREF
  __int64 v104; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v105; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v106; // [rsp+70h] [rbp-98h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+78h] [rbp-90h] BYREF
  int v108; // [rsp+88h] [rbp-80h] BYREF
  int v109; // [rsp+8Ch] [rbp-7Ch] BYREF
  PSID SourceSid; // [rsp+90h] [rbp-78h] BYREF
  __int64 v111; // [rsp+98h] [rbp-70h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A0h] [rbp-68h] BYREF
  char *v113; // [rsp+B0h] [rbp-58h]
  int v114; // [rsp+B8h] [rbp-50h]
  int v115; // [rsp+BCh] [rbp-4Ch]
  struct _EVENT_DATA_DESCRIPTOR v116; // [rsp+C8h] [rbp-40h] BYREF
  __int16 *v117; // [rsp+D8h] [rbp-30h]
  int v118; // [rsp+E0h] [rbp-28h]
  int v119; // [rsp+E4h] [rbp-24h] BYREF
  PSID *p_SourceSid; // [rsp+E8h] [rbp-20h]
  __int64 v121; // [rsp+F0h] [rbp-18h]
  EVENT_DESCRIPTOR *v122; // [rsp+F8h] [rbp-10h]
  __int64 v123; // [rsp+100h] [rbp-8h]
  int *v124; // [rsp+108h] [rbp+0h]
  __int64 v125; // [rsp+110h] [rbp+8h]
  __int64 *v126; // [rsp+118h] [rbp+10h]
  __int64 v127; // [rsp+120h] [rbp+18h]
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+128h] [rbp+20h]
  __int64 v129; // [rsp+130h] [rbp+28h]
  __int64 *v130; // [rsp+138h] [rbp+30h]
  __int64 v131; // [rsp+140h] [rbp+38h]
  __int64 *v132; // [rsp+148h] [rbp+40h]
  __int64 v133; // [rsp+150h] [rbp+48h]
  int *v134; // [rsp+158h] [rbp+50h]
  __int64 v135; // [rsp+160h] [rbp+58h]
  int v136; // [rsp+300h] [rbp+1F8h]
  __int64 v137; // [rsp+308h] [rbp+200h]
  int v138; // [rsp+310h] [rbp+208h]
  int v139; // [rsp+320h] [rbp+218h]

  v6 = a1;
  v103 = a3;
  v105 = a2;
  v111 = a1;
  v99 = a4;
  SourceSid = 0;
  LODWORD(v106) = 0;
  if ( (unsigned int)dword_18003F080 > 4 && (qword_18003F090 & 1) != 0 && (qword_18003F098 & 1) == qword_18003F098 )
  {
    *(_DWORD *)&EventDescriptor.Level = 260;
    UserData.Ptr = (ULONGLONG)off_18003F088;
    EventDescriptor.Keyword = 1;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    UserData.Size = *(unsigned __int16 *)off_18003F088;
    v113 = byte_180037EE5;
    v115 = 1;
    UserData.Reserved = 2;
    v114 = 32;
    v100 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(qword_18003F0A0, &EventDescriptor, 0, 0, 2u, &UserData);
  }
  if ( a6 )
    *a6 = 0;
  RtlAcquireSRWLockExclusive(v6 + 328);
  if ( v99 == 6 )
  {
    v7 = *(_DWORD *)(v6 + 160);
    if ( (v7 & 1) != 0 )
    {
      v8 = 10;
      v9 = -1073741558;
      RtlReleaseSRWLockExclusive(v6 + 328);
      goto LABEL_220;
    }
    *(_DWORD *)(v6 + 160) = v7 | 1;
  }
  *(_QWORD *)&EventDescriptor.Id = 0;
  RtlQueryUnbiasedInterruptTime(&EventDescriptor);
  v10 = (_DWORD *)(v6 + 7024);
  v11 = (_DWORD *)(v6 + 7024);
  while ( 1 )
  {
    if ( (a5 & 1) != 0 )
    {
      v11 = (_DWORD *)(v6 + 7024);
      if ( *(_DWORD *)(v6 + 344) == 5 )
      {
        v11 = (_DWORD *)(v6 + 7024);
        goto LABEL_17;
      }
    }
    if ( (a5 & 2) == 0 )
      break;
    v11 = (_DWORD *)(v6 + 7024);
    if ( !*(_DWORD *)(v6 + 7024) )
      break;
LABEL_17:
    *(_QWORD *)&EventDescriptor.Id = 0;
    RtlQueryUnbiasedInterruptTime(&EventDescriptor);
    RtlSleepConditionVariableSRW(v6 + 336, v6 + 328, 0, 0);
  }
  v12 = v99;
  if ( v99 == 6 )
    *(_DWORD *)(v6 + 160) &= ~1u;
  else
    v10 = v11;
  if ( *v10 )
  {
    v8 = 20;
    goto LABEL_23;
  }
  if ( *(_DWORD *)(v6 + 344) != 5 || (a5 & 4) != 0 )
  {
    v9 = -1073700861;
    if ( v103 )
    {
      v99 = *(_DWORD *)(v6 + 344);
      v13 = v103(v6, v105, &v99, &v106);
      v9 = v13;
      if ( a6 )
        *a6 = 1;
      if ( v13 < 0 )
      {
        v8 = 40;
        RtlReleaseSRWLockExclusive(v6 + 328);
        goto LABEL_220;
      }
      v12 = v99;
    }
    v14 = *(_DWORD *)(v6 + 344);
    v15 = &_ImageBase;
    v16 = 0;
    v17 = 2;
    v18 = 0;
    if ( v14 != v12 )
    {
      v21 = 137;
      if ( v14 <= 7
        && _bittest(&v21, v14)
        && (v12 > 7 || !_bittest(&v21, v12))
        && (*(_DWORD *)(v6 + 128) & 0x18000) != 0 )
      {
        PsmpEnableDisablePrioritySandbox(v6, 1, 0);
        *(_QWORD *)&EventDescriptor.Id = 0;
        v22 = *(void **)(v6 + 184);
        IsPsmHostStateNotification2Present();
        *(_DWORD *)&EventDescriptor.Id = 0;
        v23 = NtSetInformationJobObject(v22, MaxJobObjectInfoClass|JobObjectBasicProcessIdList, &EventDescriptor, 8u);
        if ( v23 < 0 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v16 = 0;
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_idd(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, v25, *(_QWORD *)(v6 + 96), v23, 0);
        }
        else
        {
          v16 = 0;
        }
        if ( PsmpRegisteredTlgProv )
        {
          v26 = *(char **)(v6 + 8);
          if ( (unsigned int)dword_18003F080 > 4 )
          {
            v24 = qword_18003F098;
            if ( (qword_18003F090 & 1) != 0 && (qword_18003F098 & 1) == qword_18003F098 )
            {
              if ( v26 )
              {
                v27 = -1;
                do
                  v28 = *(_WORD *)&v26[2 * v27++ + 2] == 0;
                while ( !v28 );
                v29 = 2 * v27 + 2;
              }
              else
              {
                v26 = byte_180034900;
                v29 = 2;
              }
              v121 = v29;
              v30 = *(_QWORD *)(v6 + 312);
              p_SourceSid = (PSID *)v26;
              UserData.Ptr = 0x40B000000LL;
              v31 = *(_DWORD *)(v30 + 4);
              v122 = (EVENT_DESCRIPTOR *)&v100;
              v124 = &v108;
              v126 = (__int64 *)&v98;
              v109 = *(_DWORD *)(v6 + 344);
              p_EventDescriptor = (EVENT_DESCRIPTOR *)&v109;
              LODWORD(v104) = *(_DWORD *)(v6 + 136);
              v130 = &v104;
              LODWORD(v102) = *(_DWORD *)(v6 + 140);
              v132 = &v102;
              LODWORD(v105) = *(_DWORD *)(v6 + 144);
              v134 = (int *)&v105;
              v116.Ptr = (ULONGLONG)off_18003F088;
              v100 = v31;
              v123 = 4;
              v108 = 6;
              v125 = 4;
              LOBYTE(v98) = 0;
              v127 = 1;
              v129 = 4;
              v131 = 4;
              v133 = 4;
              v135 = 4;
              *(_QWORD *)&UserData.Size = 1;
              v116.Size = *(unsigned __int16 *)off_18003F088;
              v117 = (__int16 *)&unk_180038E20;
              v116.Reserved = 2;
              v118 = 140;
              v119 = 1;
              LODWORD(v103) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
              EventWriteTransfer(qword_18003F0A0, (PCEVENT_DESCRIPTOR)&UserData, 0, 0, 0xAu, &v116);
            }
          }
        }
        if ( (Microsoft_Windows_ProcessStateManagerEnableBits & 4) != 0 )
          PsmpTraceAppPriorityChange(v6, v24);
        v12 = v99;
        v15 = &_ImageBase;
      }
      v32 = *(_QWORD *)(v6 + 320);
      switch ( v12 )
      {
        case 0u:
          v33 = *(_DWORD *)(v6 + 344);
          if ( v33 != 3 || (*(_DWORD *)(v6 + 132) & 0x1000) == 0 )
          {
            switch ( v33 )
            {
              case 1:
              case 2:
              case 4:
                v34 = _interlockedbittestandreset((volatile signed __int32 *)(v6 + 128), 0x16u);
                v16 = ~(*(_DWORD *)(v6 + 128) >> 4) & 2;
                if ( (unsigned int)(*(_DWORD *)(v6 + 344) - 1) <= 1 )
                  PsmpEnableDisableSandbox(v6, v99);
                goto LABEL_65;
              case 5:
                goto LABEL_71;
              case 6:
                goto LABEL_68;
              case 7:
                break;
              default:
                goto LABEL_74;
            }
          }
          v34 = 0;
LABEL_65:
          if ( *(_DWORD *)(v6 + 152) && !v34 )
            PsmpSendProcessNotifications(v6, 0);
LABEL_68:
          v35 = 4294967271LL;
          if ( *(_DWORD *)(v32 + 16) )
            v35 = 0;
          PsmpSetApplicationExecutionState(v6, v16, v35);
          v12 = v99;
          v9 = 0;
          goto LABEL_106;
        case 1u:
        case 2u:
          PsmpEnableDisableSandbox(v6, v12);
          goto LABEL_73;
        case 3u:
          _InterlockedAnd((volatile signed __int32 *)(v6 + 128), 0xFFBFFFFF);
          LOBYTE(v15) = 1;
          PsmpSendProcessNotifications(v6, v15);
          goto LABEL_73;
        case 4u:
          if ( (unsigned int)(*(_DWORD *)(v6 + 344) - 1) <= 1 )
          {
            PsmpEnableDisableSandbox(v6, v12);
            v12 = v99;
          }
          if ( (*(_BYTE *)(v6 + 132) & 4) != 0 )
            goto LABEL_74;
          v36 = 5;
          v37 = 4294967271LL;
          if ( *(_DWORD *)(v32 + 16) )
          {
            v36 = 1;
            v37 = 0;
          }
          v38 = v36 | 8;
          if ( (a5 & 8) == 0 )
            v38 = v36;
          PsmpSetApplicationExecutionState(v6, v38, v37);
LABEL_73:
          v12 = v99;
          goto LABEL_74;
        case 5u:
          if ( !(unsigned __int8)PsmpCheckWorkItemCompletedState(v6, &_ImageBase) )
            goto LABEL_71;
          if ( *(_DWORD *)(v6 + 344) == 3 )
          {
            for ( i = *(_QWORD **)(v6 + 6704); i != (_QWORD *)(v6 + 6704); i = (_QWORD *)*i )
              *((_DWORD *)i - 18) = 4 * (*(_DWORD *)(i - 9) & 2 | 1);
            *(_QWORD *)(v6 + 148) = 0;
          }
          v17 = 0;
          v18 = 1;
          PsmpSetApplicationExecutionState(v6, 1, 0);
          v12 = v99;
          v9 = 0;
          goto LABEL_106;
        case 6u:
          if ( (unsigned __int8)PsmpCheckWorkItemCompletedState(v6, &_ImageBase) )
          {
            if ( (unsigned int)(*(_DWORD *)(v6 + 344) - 1) <= 1 )
              PsmpEnableDisableSandbox(v40, v41);
            PsmpCheckNotifyApplicationTerminated(v6, &v106);
            PsmpTerminateJobObject(v6, 0, 6);
            _interlockedbittestandreset((volatile signed __int32 *)(v6 + 128), 0x16u);
            _interlockedbittestandreset((volatile signed __int32 *)(v6 + 128), 0x17u);
            if ( (*(_BYTE *)(v6 + 132) & 4) != 0 )
              PsmpSetApplicationExecutionState(v6, 2, 0);
            v43 = 0;
            if ( *(_DWORD *)(v6 + 344) == 5 )
              v18 = 3;
            LOBYTE(v43) = *(_DWORD *)(v6 + 344) != 5;
            v17 = v43 + 1;
            if ( *(_DWORD *)(v6 + 348) )
            {
              *(_DWORD *)(v6 + 348) = 0;
              if ( (Microsoft_Windows_ProcessStateManagerEnableBits & 4) != 0 )
                PsmpTraceAppPriorityChange(v6, v42);
            }
            v12 = v99;
            v9 = 0;
LABEL_106:
            v20 = 0;
            if ( v12 <= 7 )
            {
              v44 = 137;
              if ( _bittest(&v44, v12) )
              {
                v45 = *(_DWORD *)(v6 + 344);
                if ( (v45 > 7 || !_bittest(&v44, v45)) && *(_DWORD *)(v6 + 348) == 1 && !*(_DWORD *)(v6 + 164) )
                {
                  *(_QWORD *)&EventDescriptor.Id = 0;
                  v46 = *(void **)(v6 + 184);
                  IsPsmHostStateNotification2Present();
                  *(_DWORD *)&EventDescriptor.Id = 3;
                  *(_DWORD *)&EventDescriptor.Level = 5;
                  v47 = NtSetInformationJobObject(
                          v46,
                          MaxJobObjectInfoClass|JobObjectBasicProcessIdList,
                          &EventDescriptor,
                          8u);
                  if ( v47 < 0
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_idd(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, v48, *(_QWORD *)(v6 + 96), v47, 1);
                  }
                  if ( PsmpRegisteredTlgProv )
                  {
                    v49 = *(char **)(v6 + 8);
                    if ( (unsigned int)dword_18003F080 > 4
                      && (qword_18003F090 & 1) != 0
                      && (qword_18003F098 & 1) == qword_18003F098 )
                    {
                      if ( v49 )
                      {
                        v50 = -1;
                        do
                          v28 = *(_WORD *)&v49[2 * v50++ + 2] == 0;
                        while ( !v28 );
                        v51 = 2 * v50 + 2;
                      }
                      else
                      {
                        v49 = byte_180034900;
                        v51 = 2;
                      }
                      v121 = v51;
                      v52 = *(_QWORD *)(v6 + 312);
                      p_SourceSid = (PSID *)v49;
                      UserData.Ptr = 0x40B000000LL;
                      v53 = *(_DWORD *)(v52 + 4);
                      v122 = (EVENT_DESCRIPTOR *)&v103;
                      v124 = (int *)&v105;
                      v126 = (__int64 *)&v98;
                      LODWORD(v102) = *(_DWORD *)(v6 + 344);
                      p_EventDescriptor = (EVENT_DESCRIPTOR *)&v102;
                      LODWORD(v104) = *(_DWORD *)(v6 + 136);
                      v130 = &v104;
                      v109 = *(_DWORD *)(v6 + 140);
                      v132 = (__int64 *)&v109;
                      v108 = *(_DWORD *)(v6 + 144);
                      v134 = &v108;
                      v116.Ptr = (ULONGLONG)off_18003F088;
                      LODWORD(v103) = v53;
                      v123 = 4;
                      LODWORD(v105) = 6;
                      v125 = 4;
                      LOBYTE(v98) = 1;
                      v127 = 1;
                      v129 = 4;
                      v131 = 4;
                      v133 = 4;
                      v135 = 4;
                      *(_QWORD *)&UserData.Size = 1;
                      v116.Size = *(unsigned __int16 *)off_18003F088;
                      v117 = (__int16 *)&unk_180038E20;
                      v116.Reserved = 2;
                      v118 = 140;
                      v119 = 1;
                      v100 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                      EventWriteTransfer(qword_18003F0A0, (PCEVENT_DESCRIPTOR)&UserData, 0, 0, 0xAu, &v116);
                    }
                  }
                  LOBYTE(v48) = 1;
                  PsmpEnableDisablePrioritySandbox(v6, 0, v48);
                  if ( (Microsoft_Windows_ProcessStateManagerEnableBits & 4) != 0 )
                    PsmpTraceAppPriorityChange(v6, v54);
                }
              }
            }
            PsmpUpdateApplicationCounters(v6);
            if ( (unsigned int)dword_18003F080 > 4
              && (qword_18003F090 & 3) != 0
              && (qword_18003F098 & 3) == qword_18003F098 )
            {
              v56 = *(char **)(v6 + 8);
              LODWORD(v103) = v9;
              p_SourceSid = (PSID *)&v103;
              v121 = 4;
              if ( v56 )
              {
                v57 = -1;
                do
                  v28 = *(_WORD *)&v56[2 * v57++ + 2] == 0;
                while ( !v28 );
                v58 = 2 * v57 + 2;
              }
              else
              {
                v56 = byte_180034900;
                v58 = 2;
              }
              v123 = v58;
              LOBYTE(v98) = v99;
              v122 = (EVENT_DESCRIPTOR *)v56;
              v124 = &v98;
              v101 = *(_BYTE *)(v6 + 344);
              v126 = (__int64 *)&v101;
              *(_QWORD *)&EventDescriptor.Id = *(_QWORD *)(v6 + 96);
              p_EventDescriptor = &EventDescriptor;
              v116.Ptr = (ULONGLONG)off_18003F088;
              v125 = 1;
              v127 = 1;
              v129 = 8;
              UserData.Ptr = 0x2040B000000LL;
              *(_QWORD *)&UserData.Size = 3;
              v116.Size = *(unsigned __int16 *)off_18003F088;
              v117 = (__int16 *)&dword_180038054;
              v119 = 1;
              v116.Reserved = 2;
              v118 = 84;
              LODWORD(v105) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
              EventWriteTransfer(qword_18003F0A0, (PCEVENT_DESCRIPTOR)&UserData, 0, 0, 7u, &v116);
            }
            if ( (Microsoft_Windows_ProcessStateManagerEnableBits & 1) != 0 )
              PsmpTraceAppStateChange(v6, *(unsigned int *)(v6 + 344), v99);
            v59 = *(unsigned int *)(v6 + 344);
            if ( v99 )
            {
              if ( (_DWORD)v59 )
              {
                v19 = 2;
              }
              else
              {
                v19 = 1;
                v18 |= 4u;
              }
            }
            else
            {
              v19 = 0;
              v18 |= 4u;
            }
            v60 = PsmpConvertInternalApplicationState(v99, v55, v59);
            v62 = PsmpConvertInternalApplicationState((unsigned int)v61, v60, v61);
            if ( v62 != v64 )
              v18 |= 8u;
            *(_DWORD *)(v6 + 344) = v63;
            ++*(_DWORD *)(352 * v63 + v6 + 736);
            PsmpUpdateApplicationEnergyTrackingState(v6);
            goto LABEL_147;
          }
LABEL_71:
          v9 = -1073700861;
LABEL_75:
          if ( (unsigned int)dword_18003F080 > 4
            && (qword_18003F090 & 1) != 0
            && (qword_18003F098 & 1) == qword_18003F098 )
          {
            SourceSid = *(PSID *)(v6 + 96);
            v121 = 8;
            *(_QWORD *)&UserData.Size = 1;
            p_SourceSid = &SourceSid;
            *(_QWORD *)&EventDescriptor.Id = *(int *)(v6 + 344);
            v122 = &EventDescriptor;
            LODWORD(v103) = v99;
            v124 = (int *)&v103;
            v126 = &v105;
            v116.Ptr = (ULONGLONG)off_18003F088;
            v123 = 8;
            v125 = 4;
            LODWORD(v105) = v9;
            v127 = 4;
            UserData.Ptr = 0x40B000000LL;
            v116.Size = *(unsigned __int16 *)off_18003F088;
            v117 = (__int16 *)&unk_180038430;
            v119 = 1;
            v116.Reserved = 2;
            v118 = 87;
            LODWORD(v102) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(qword_18003F0A0, (PCEVENT_DESCRIPTOR)&UserData, 0, 0, 6u, &v116);
          }
          v8 = 60;
          RtlReleaseSRWLockExclusive(v6 + 328);
          break;
        default:
LABEL_74:
          if ( v9 < 0 )
            goto LABEL_75;
          goto LABEL_106;
      }
      goto LABEL_220;
    }
    v19 = 2;
    v9 = 0;
    v20 = 50;
LABEL_147:
    v100 = v20;
    if ( (v18 & 1) == 0 )
    {
      v100 = v20;
      goto LABEL_158;
    }
    RtlAcquireSRWLockExclusive(&PsmpNotificationQueue);
    if ( v17 == 1 )
    {
      v65 = *(_QWORD *)(v6 + 7032);
      if ( v65 )
      {
        *(_BYTE *)(v65 + 560) |= 2u;
        *(_BYTE *)(v65 + 556) &= ~2u;
        if ( !*(_DWORD *)(v65 + 16) )
          *(_QWORD *)(v6 + 7032) = 0;
LABEL_155:
        ((void (*)(void))PsmpNotificationQueueInsertConditionally)();
      }
    }
    else if ( (int)PsmpNotificationQueueCreateMessage(
                     0,
                     *(unsigned int *)(*(_QWORD *)(v6 + 312) + 4LL),
                     *(_QWORD *)(*(_QWORD *)(v6 + 312) + 40LL),
                     *(_QWORD *)(v6 + 8),
                     &SourceSid) >= 0 )
    {
      v66 = SourceSid;
      *((_BYTE *)SourceSid + 560) |= 1u;
      v66[556] |= 2u;
      if ( !*((_DWORD *)v66 + 4) )
        *(_QWORD *)(v6 + 7032) = v66;
      goto LABEL_155;
    }
    RtlReleaseSRWLockExclusive(&PsmpNotificationQueue);
LABEL_158:
    if ( (v18 & 4) != 0 )
    {
      v67 = *(_QWORD *)(v6 + 312);
      v68 = *(_WORD **)(v6 + 8);
      v69 = *(void **)(v67 + 40);
      LODWORD(v67) = *(_DWORD *)(v67 + 4);
      SourceSid = v69;
      LODWORD(v103) = v67;
      RtlAcquireSRWLockExclusive(&PsmpNotificationQueue);
      v70 = -1;
      do
        v28 = v68[++v70] == 0;
      while ( !v28 );
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x238u);
      v72 = Heap;
      if ( Heap )
      {
        memset_0(Heap, 0, 0x238u);
        RtlCopySid(0x44u, v72 + 6, SourceSid);
        memcpy_0(v72 + 23, v68, (unsigned int)(2 * v70 + 2));
        v72[5] = (_DWORD)v103;
        v72[4] = 1;
        v72[140] = v19;
        PsmpNotificationQueueInsertConditionally(v73, v72);
      }
      RtlReleaseSRWLockExclusive(&PsmpNotificationQueue);
    }
    if ( (v18 & 8) != 0 )
    {
      switch ( *(_DWORD *)(v6 + 344) )
      {
        case 1:
        case 2:
        case 4:
          v74 = 2;
          break;
        case 3:
          v74 = 1;
          break;
        case 5:
        case 6:
          v74 = 3;
          break;
        case 7:
          v74 = 5;
          break;
        default:
          v74 = 0;
          break;
      }
      if ( *(_QWORD *)(v6 + 192) )
      {
        memset_0(&v116, 0, 0x260u);
        v75 = *(_QWORD *)(v6 + 6944);
        v116.Size = 1;
        v118 = 2;
        PsmpNotificationsGetApplicationIdentityFromApplication(v75, &v119);
        v76 = *(_DWORD *)(v6 + 6960);
        v77 = *(_QWORD *)(v6 + 6944);
        v139 = v74;
        switch ( v76 )
        {
          case 2:
            v78 = *(_QWORD *)(v77 + 6800);
            break;
          case 4:
            v78 = *(_QWORD *)(v6 + 6984);
            break;
          case 8:
            v78 = *(_QWORD *)(v77 + 6808);
            break;
          default:
            v78 = -1;
            break;
        }
        v79 = 0;
        if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v77 + 312) + 56LL) + 16LL) == 4 )
          v79 = 4;
        v80 = (*(_DWORD *)(v77 + 128) >> 19) & 2 | v79;
        v81 = v76 == 4 || (v80 & 2) != 0;
        v136 = v76;
        v138 = v80 | v81;
        v137 = v78;
        PsmpNotificationsDeliverMessage(v77, &v116);
      }
      if ( *(_QWORD *)(v6 + 200) )
      {
        memset_0(&v116, 0, 0x260u);
        v82 = *(_QWORD *)(v6 + 6984);
        v116.Size = 1;
        v118 = 2;
        PsmpNotificationsGetApplicationIdentityFromApplication(v82, &v119);
        v83 = *(_DWORD *)(v6 + 7000);
        v84 = *(_QWORD *)(v6 + 6984);
        v139 = v74;
        switch ( v83 )
        {
          case 2:
            v85 = *(_QWORD *)(v84 + 6800);
            break;
          case 4:
            v85 = *(_QWORD *)(v6 + 7024);
            break;
          case 8:
            v85 = *(_QWORD *)(v84 + 6808);
            break;
          default:
            v85 = -1;
            break;
        }
        v86 = 0;
        if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v84 + 312) + 56LL) + 16LL) == 4 )
          v86 = 4;
        v87 = (*(_DWORD *)(v84 + 128) >> 19) & 2 | v86;
        v88 = v83 == 4 || (v87 & 2) != 0;
        v136 = v83;
        v138 = v87 | v88;
        v137 = v85;
        PsmpNotificationsDeliverMessage(v84, &v116);
      }
      v89 = *(_QWORD **)(v6 + 6816);
      if ( v89 != (_QWORD *)(v6 + 6816) )
      {
        do
        {
          memset_0(&v116, 0, 0x260u);
          v90 = *(v89 - 7);
          v116.Size = 1;
          v118 = 2;
          PsmpNotificationsGetApplicationIdentityFromApplication(v90, &v119);
          v91 = *((_DWORD *)v89 - 10);
          v92 = *(v89 - 7);
          v139 = v74;
          switch ( v91 )
          {
            case 2:
              v93 = *(_QWORD *)(v92 + 6800);
              break;
            case 4:
              v93 = *(v89 - 2);
              break;
            case 8:
              v93 = *(_QWORD *)(v92 + 6808);
              break;
            default:
              v93 = -1;
              break;
          }
          v94 = 0;
          if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v92 + 312) + 56LL) + 16LL) == 4 )
            v94 = 4;
          v95 = (*(_DWORD *)(v92 + 128) >> 19) & 2 | v94;
          v96 = v91 == 4 || (v95 & 2) != 0;
          v136 = v91;
          v138 = v95 | v96;
          v137 = v93;
          PsmpNotificationsDeliverMessage(v92, &v116);
          v89 = (_QWORD *)*v89;
        }
        while ( v89 != (_QWORD *)(v6 + 6816) );
        v6 = v111;
      }
    }
    RtlReleaseSRWLockExclusive(v6 + 328);
    if ( (v18 & 2) != 0 )
      RtlWakeAllConditionVariable(v6 + 336);
    v8 = v100;
    goto LABEL_220;
  }
  v8 = 30;
LABEL_23:
  v9 = -1073741558;
  RtlReleaseSRWLockExclusive(v6 + 328);
LABEL_220:
  if ( (v106 & 1) != 0 )
    PsmpDereferenceApplicationEx(v6, 0);
  if ( (unsigned int)dword_18003F080 > 4 && (qword_18003F090 & 1) != 0 && (qword_18003F098 & 1) == qword_18003F098 )
  {
    LODWORD(v103) = v9;
    p_SourceSid = (PSID *)&v103;
    LODWORD(v105) = v106;
    *(_QWORD *)&UserData.Size = 1;
    v122 = (EVENT_DESCRIPTOR *)&v105;
    v121 = 4;
    v124 = (int *)&v102;
    v116.Ptr = (ULONGLONG)off_18003F088;
    v123 = 4;
    LODWORD(v102) = v8;
    v125 = 4;
    UserData.Ptr = 0x2040B000000LL;
    v116.Size = *(unsigned __int16 *)off_18003F088;
    v117 = word_1800382C2;
    v119 = 1;
    v116.Reserved = 2;
    v118 = 69;
    LODWORD(v104) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(qword_18003F0A0, (PCEVENT_DESCRIPTOR)&UserData, 0, 0, 5u, &v116);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800114d0  mov     r11, rsp
0x1800114d3  push    rbp
0x1800114d4  push    rbx
0x1800114d5  push    r15
0x1800114d7  lea     rbp, [r11-278h]
0x1800114de  sub     rsp, 360h
0x1800114e5  mov     rax, cs:__security_cookie
0x1800114ec  xor     rax, rsp
0x1800114ef  mov     [rbp+270h+var_50], rax
0x1800114f6  mov     eax, cs:dword_18003F080
0x1800114fc  lea     r15, _TraceLoggingMetadataEnd
0x180011503  mov     [r11-20h], rsi
0x180011507  xor     ebx, ebx
0x180011509  mov     [r11-28h], rdi
0x18001150d  mov     rsi, rcx
0x180011510  mov     [r11-30h], r12
0x180011514  mov     r12, [rbp+270h+arg_28]
0x18001151b  mov     [rsp+370h+var_320], r8
0x180011520  lea     r8, _TraceLoggingMetadata
0x180011527  mov     [rsp+370h+var_310], rdx
0x18001152c  mov     edx, 1
0x180011531  mov     [r11-38h], r13
0x180011535  mov     [rbp+270h+var_2E0], rcx
0x180011539  mov     [rsp+370h+var_338], r9d
0x18001153e  mov     [rbp+270h+SourceSid], rbx
0x180011542  mov     dword ptr [rsp+370h+var_308], ebx
0x180011546  cmp     eax, 4
0x180011549  jbe     loc_1800115EB
0x18001154f  mov     rcx, cs:qword_18003F098
0x180011556  mov     rax, cs:qword_18003F090
0x18001155d  test    dl, al
0x18001155f  jz      loc_1800115EB
0x180011565  mov     rax, rcx
0x180011568  and     eax, edx
0x18001156a  cmp     rax, rcx
0x18001156d  jnz     short loc_1800115EB
0x18001156f  movzx   eax, cs:word_180037EDB
0x180011576  xor     r9d, r9d; RelatedActivityId
0x180011579  mov     dword ptr [rsp+370h+EventDescriptor.Level], eax
0x18001157d  mov     rax, cs:off_18003F088
0x180011584  mov     [rbp+270h+var_2D8.Ptr], rax
0x180011588  mov     [rsp+370h+EventDescriptor.Keyword], rdx
0x18001158d  mov     dword ptr [rsp+370h+EventDescriptor.Id], 0B000000h
0x180011595  movzx   eax, word ptr [rax]
0x180011598  mov     [rbp+270h+var_2D8.Size], eax
0x18001159b  lea     rax, byte_180037EE5
0x1800115a2  mov     [rbp+270h+var_2C8], rax
0x1800115a6  mov     rax, r15
0x1800115a9  sub     eax, r8d
0x1800115ac  mov     [rbp+270h+var_2BC], edx
0x1800115af  mov     dword ptr [rbp+270h+var_2D8.0Ch], 2
0x1800115b6  lea     rdx, [rsp+370h+EventDescriptor]; EventDescriptor
0x1800115bb  mov     [rbp+270h+var_2C0], 20h ; ' '
0x1800115c2  xor     r8d, r8d; ActivityId
0x1800115c5  mov     [rsp+370h+var_330], eax
0x1800115c9  mov     eax, [rsp+370h+var_330]
0x1800115cd  mov     rcx, cs:qword_18003F0A0; RegHandle
0x1800115d4  lea     rax, [rbp+270h+var_2D8]
0x1800115d8  mov     [rsp+370h+UserData], rax; UserData
0x1800115dd  mov     [rsp+370h+UserDataCount], 2; UserDataCount
0x1800115e5  call    cs:__imp_EventWriteTransfer
0x1800115eb  test    r12, r12
0x1800115ee  jz      short loc_1800115F4
0x1800115f0  mov     [r12], bl
0x1800115f4  lea     rcx, [rsi+148h]
0x1800115fb  mov     [rsp+370h+var_38], r14
0x180011603  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180011609  cmp     [rsp+370h+var_338], 6
0x18001160e  jnz     short loc_180011640
0x180011610  mov     eax, [rsi+0A0h]
0x180011616  test    al, 1
0x180011618  jz      short loc_180011637
0x18001161a  lea     rcx, [rsi+148h]
0x180011621  mov     ebx, 0Ah
0x180011626  mov     r14d, 0C000010Ah
0x18001162c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180011632  jmp     loc_18001270B
0x180011637  or      eax, 1
0x18001163a  mov     [rsi+0A0h], eax
0x180011640  lea     rcx, [rsp+370h+EventDescriptor]
0x180011645  mov     qword ptr [rsp+370h+EventDescriptor.Id], rbx
0x18001164a  call    cs:__imp_RtlQueryUnbiasedInterruptTime
0x180011650  mov     r14d, dword ptr [rbp+270h+arg_20]
0x180011657  lea     rdi, [rsi+1B70h]
0x18001165e  mov     r15d, dword ptr [rbp+270h+arg_20]
0x180011665  and     r14d, 1
0x180011669  and     r15d, 2
0x18001166d  mov     rbx, rdi
0x180011670  test    r14d, r14d
0x180011673  jz      short loc_18001168A
0x180011675  cmp     dword ptr [rsi+158h], 5
0x18001167c  mov     rbx, rdi
0x18001167f  jnz     short loc_18001168A
0x180011681  lea     rbx, [rsi+1B70h]
0x180011688  jmp     short loc_18001169B
0x18001168a  test    r15d, r15d
0x18001168d  jz      short loc_1800116CB
0x18001168f  lea     rbx, [rsi+1B70h]
0x180011696  cmp     dword ptr [rbx], 0
0x180011699  jbe     short loc_1800116CB
0x18001169b  lea     rcx, [rsp+370h+EventDescriptor]
0x1800116a0  mov     qword ptr [rsp+370h+EventDescriptor.Id], 0
0x1800116a9  call    cs:__imp_RtlQueryUnbiasedInterruptTime
0x1800116af  lea     rcx, [rsi+150h]
0x1800116b6  xor     r9d, r9d
0x1800116b9  xor     r8d, r8d
0x1800116bc  lea     rdx, [rsi+148h]
0x1800116c3  call    cs:__imp_RtlSleepConditionVariableSRW
0x1800116c9  jmp     short loc_180011670
0x1800116cb  mov     r9d, [rsp+370h+var_338]
0x1800116d0  cmp     r9d, 6
0x1800116d4  jnz     short loc_1800116DF
0x1800116d6  and     dword ptr [rsi+0A0h], 0FFFFFFFEh
0x1800116dd  jmp     short loc_1800116E2
0x1800116df  mov     rdi, rbx
0x1800116e2  cmp     dword ptr [rdi], 0
0x1800116e5  mov     r13, [rsp+370h+var_320]
0x1800116ea  jbe     short loc_180011709
0x1800116ec  mov     ebx, 14h
0x1800116f1  lea     rcx, [rsi+148h]
0x1800116f8  mov     r14d, 0C000010Ah
0x1800116fe  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180011704  jmp     loc_180012704
0x180011709  mov     eax, [rsi+158h]
0x18001170f  cmp     eax, 5
0x180011712  jnz     short loc_180011724
0x180011714  test    [rbp+270h+arg_20], 4
0x18001171b  jnz     short loc_180011724
0x18001171d  mov     ebx, 1Eh
0x180011722  jmp     short loc_1800116F1
0x180011724  mov     r14d, 0C000A003h
0x18001172a  test    r13, r13
0x18001172d  jz      short loc_18001177A
0x18001172f  mov     rdx, [rsp+370h+var_310]
0x180011734  lea     r9, [rsp+370h+var_308]
0x180011739  mov     [rsp+370h+var_338], eax
0x18001173d  lea     r8, [rsp+370h+var_338]
0x180011742  mov     rax, r13
0x180011745  mov     rcx, rsi
0x180011748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001174d  mov     r14d, eax
0x180011750  test    r12, r12
0x180011753  jz      short loc_18001175A
0x180011755  mov     byte ptr [r12], 1
0x18001175a  test    eax, eax
0x18001175c  jns     short loc_180011775
0x18001175e  lea     rcx, [rsi+148h]
0x180011765  mov     ebx, 28h ; '('
0x18001176a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180011770  jmp     loc_180012704
0x180011775  mov     r9d, [rsp+370h+var_338]
0x18001177a  mov     eax, [rsi+158h]
0x180011780  lea     rdx, __ImageBase
0x180011787  xor     edi, edi
0x180011789  mov     r12d, 2
0x18001178f  mov     ebx, edi
0x180011791  mov     r13d, 3
0x180011797  cmp     eax, r9d
0x18001179a  jnz     short loc_1800117AD
0x18001179c  mov     r13d, r12d
0x18001179f  mov     r14d, edi
0x1800117a2  mov     r15d, 32h ; '2'
0x1800117a8  jmp     loc_18001225E
0x1800117ad  mov     ecx, 89h
0x1800117b2  cmp     eax, 7
0x1800117b5  ja      loc_180011A26
0x1800117bb  bt      ecx, eax
0x1800117be  jnb     loc_180011A26
0x1800117c4  cmp     r9d, 7
0x1800117c8  ja      short loc_1800117D4
0x1800117ca  bt      ecx, r9d
0x1800117ce  jb      loc_180011A26
0x1800117d4  test    dword ptr [rsi+80h], 18000h
0x1800117de  jz      loc_180011A26
0x1800117e4  mov     r15d, 1
0x1800117ea  xor     r8d, r8d
0x1800117ed  mov     edx, r15d
0x1800117f0  mov     rcx, rsi
0x1800117f3  call    PsmpEnableDisablePrioritySandbox
0x1800117f8  mov     qword ptr [rsp+370h+EventDescriptor.Id], rdi
0x1800117fd  mov     rdi, [rsi+0B8h]
0x180011804  call    IsPsmHostStateNotification2Present
0x180011809  mov     r9d, 8; JobInformationLength
0x18001180f  mov     dword ptr [rsp+370h+EventDescriptor.Id], ebx
0x180011813  lea     r8, [rsp+370h+EventDescriptor]; JobInformation
0x180011818  mov     edx, 0Fh; JobInformationClass
0x18001181d  mov     rcx, rdi; JobHandle
0x180011820  call    cs:__imp_NtSetInformationJobObject
0x180011826  test    eax, eax
0x180011828  jns     short loc_18001185B
0x18001182a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011831  test    [rcx+1Ch], r15b
0x180011835  jz      short loc_18001185B
0x180011837  xor     edi, edi
0x180011839  cmp     [rcx+19h], r12b
0x18001183d  jb      short loc_18001185D
0x18001183f  mov     r9, [rsi+60h]
0x180011843  mov     edx, 14h
0x180011848  mov     rcx, [rcx+10h]
0x18001184c  mov     dword ptr [rsp+370h+UserData], edi
0x180011850  mov     [rsp+370h+UserDataCount], eax
0x180011854  call    WPP_SF_idd
0x180011859  jmp     short loc_18001185D
0x18001185b  xor     edi, edi
0x18001185d  cmp     cs:PsmpRegisteredTlgProv, bl
0x180011863  jz      loc_180011A09
0x180011869  mov     eax, cs:dword_18003F080
0x18001186f  mov     rcx, [rsi+8]
0x180011873  cmp     eax, 4
0x180011876  jbe     loc_180011A09
0x18001187c  mov     rdx, cs:qword_18003F098
0x180011883  mov     rax, cs:qword_18003F090
0x18001188a  test    r15b, al
0x18001188d  jz      loc_180011A09
0x180011893  mov     rax, rdx
0x180011896  and     eax, r15d
0x180011899  cmp     rax, rdx
0x18001189c  jnz     loc_180011A09
0x1800118a2  test    rcx, rcx
0x1800118a5  jz      short loc_1800118C4
0x1800118a7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800118ae  xchg    ax, ax
0x1800118b0  cmp     [rcx+rax*2+2], bx
0x1800118b5  lea     rax, [rax+1]
0x1800118b9  jnz     short loc_1800118B0
0x1800118bb  lea     eax, ds:2[rax*2]
0x1800118c2  jmp     short loc_1800118CE
0x1800118c4  lea     rcx, byte_180034900
0x1800118cb  mov     eax, r12d
0x1800118ce  mov     dword ptr [rbp+270h+var_288], eax
0x1800118d1  lea     rdx, [rbp+270h+var_2D8]; EventDescriptor
0x1800118d5  mov     rax, [rsi+138h]
0x1800118dc  xor     r9d, r9d; RelatedActivityId
0x1800118df  mov     [rbp+270h+var_290], rcx
0x1800118e3  xor     r8d, r8d; ActivityId
0x1800118e6  mov     dword ptr [rbp+270h+var_288+4], edi
0x1800118e9  mov     dword ptr [rbp+270h+var_2D8.Ptr], 0B000000h
0x1800118f0  mov     ecx, [rax+4]
0x1800118f3  lea     rax, [rsp+370h+var_330]
0x1800118f8  mov     [rbp+270h+var_280], rax
0x1800118fc  lea     rax, [rbp+270h+var_2F0]
0x180011900  mov     [rbp+270h+var_270], rax
0x180011904  lea     rax, [rsp+370h+var_340]
0x180011909  mov     [rbp+270h+var_260], rax
0x18001190d  mov     eax, [rsi+158h]
0x180011913  mov     [rbp+270h+var_2EC], eax
0x180011916  lea     rax, [rbp+270h+var_2EC]
0x18001191a  mov     [rbp+270h+var_250], rax
0x18001191e  mov     eax, [rsi+88h]
0x180011924  mov     dword ptr [rsp+370h+var_318], eax
0x180011928  lea     rax, [rsp+370h+var_318]
0x18001192d  mov     [rbp+270h+var_240], rax
0x180011931  mov     eax, [rsi+8Ch]
0x180011937  mov     dword ptr [rsp+370h+var_328], eax
0x18001193b  lea     rax, [rsp+370h+var_328]
0x180011940  mov     [rbp+270h+var_230], rax
0x180011944  mov     eax, [rsi+90h]
0x18001194a  mov     dword ptr [rsp+370h+var_310], eax
0x18001194e  lea     rax, [rsp+370h+var_310]
0x180011953  mov     [rbp+270h+var_220], rax
0x180011957  movzx   eax, cs:word_180038E16
0x18001195e  mov     dword ptr [rbp+270h+var_2D8.Ptr+4], eax
0x180011961  mov     rax, cs:off_18003F088
0x180011968  mov     [rbp+270h+var_2B0.Ptr], rax
0x18001196c  mov     [rsp+370h+var_330], ecx
0x180011970  lea     rcx, _TraceLoggingMetadata
0x180011977  mov     [rbp+270h+var_278], 4
0x18001197f  mov     [rbp+270h+var_2F0], 6
0x180011986  mov     [rbp+270h+var_268], 4
0x18001198e  mov     byte ptr [rsp+370h+var_340], bl
0x180011992  mov     [rbp+270h+var_258], r15
0x180011996  mov     [rbp+270h+var_248], 4
0x18001199e  mov     [rbp+270h+var_238], 4
0x1800119a6  mov     [rbp+270h+var_228], 4
0x1800119ae  mov     [rbp+270h+var_218], 4
0x1800119b6  mov     qword ptr [rbp+270h+var_2D8.Size], r15
0x1800119ba  movzx   eax, word ptr [rax]
0x1800119bd  mov     [rbp+270h+var_2B0.Size], eax
0x1800119c0  lea     rax, unk_180038E20
0x1800119c7  mov     [rbp+270h+var_2A0], rax
0x1800119cb  lea     rax, _TraceLoggingMetadataEnd
0x1800119d2  sub     eax, ecx
0x1800119d4  mov     dword ptr [rbp+270h+var_2B0.0Ch], r12d
0x1800119d8  mov     [rbp+270h+var_298], 8Ch
0x1800119df  mov     [rbp+270h+var_294], r15d
0x1800119e3  mov     dword ptr [rsp+370h+var_320], eax
0x1800119e7  mov     eax, dword ptr [rsp+370h+var_320]
0x1800119eb  mov     rcx, cs:qword_18003F0A0; RegHandle
0x1800119f2  lea     rax, [rbp+270h+var_2B0]
0x1800119f6  mov     [rsp+370h+UserData], rax; UserData
0x1800119fb  mov     [rsp+370h+UserDataCount], 0Ah; UserDataCount
0x180011a03  call    cs:__imp_EventWriteTransfer
0x180011a09  test    cs:Microsoft_Windows_ProcessStateManagerEnableBits, 4
0x180011a10  jz      short loc_180011A1A
0x180011a12  mov     rcx, rsi
0x180011a15  call    PsmpTraceAppPriorityChange
0x180011a1a  mov     r9d, [rsp+370h+var_338]
0x180011a1f  lea     rdx, __ImageBase
0x180011a26  cmp     r9d, 6; switch 7 cases
0x180011a2a  ja      def_180011A44; jumptable 0000000180011A44 default case
  ... truncated ...
```
