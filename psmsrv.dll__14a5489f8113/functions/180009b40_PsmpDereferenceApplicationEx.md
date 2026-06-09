# PsmpDereferenceApplicationEx

- ea: `0x180009b40`
- end: `0x18000a748`
- name: `PsmpDereferenceApplicationEx`
- size: `3080`
- prototype: `int __fastcall(__int64, unsigned int)`
- caller_count: `59`
- callee_count: `18`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000191c`
- `0x180002000`
- `0x1800032a0`
- `0x1800037f4`
- `0x180003af0`
- `0x180004170`
- `0x1800049a0`
- `0x180004ff0`
- `0x180006f5c`
- `0x180007214`
- `0x1800078e0`
- `0x180007d40`
- `0x180007fd0`
- `0x180008360`
- `0x180008840`
- `0x180008f10`
- `0x180009630`
- `0x18000abf0`
- `0x18000b4d8`
- `0x18000c7b0`
- `0x18000cb34`
- `0x18000e0f4`
- `0x1800103ac`
- `0x1800114d0`
- `0x1800139d0`
- `0x180013b40`
- `0x180015050`
- `0x1800162b0`
- `0x180016990`
- `0x180016ed0`
- `0x180017768`
- `0x1800184a0`
- `0x180019100`
- `0x18001a190`
- `0x18001aba0`
- `0x18001cf00`
- `0x18001d6dc`
- `0x18001d740`
- `0x18001d840`
- `0x18001dc40`
- `0x18001deb0`
- `0x18001e20c`
- `0x18001e510`
- `0x18001f6f0`
- `0x180020540`
- `0x180023ae8`
- `0x180024c90`
- `0x18002a7d0`
- `0x18002abe0`
- `0x18002ae60`

## callees

- `0x1800065a0`
- `0x180009b40`
- `0x18000a750`
- `0x18000c3a8`
- `0x18000cf28`
- `0x18000d934`
- `0x18000da40`
- `0x18000dac8`
- `0x18000dbd0`
- `0x18000f2a4`
- `0x180014800`
- `0x180014a64`
- `0x180018e98`
- `0x180019c30`
- `0x180019e3c`
- `0x18001b7e0`
- `0x18001c10c`
- `0x18001c1a4`

## import_xrefs

- `ntdll!TpWaitForJobNotification` at `0x18000a1d1`
- `ntdll!TpWaitForJobNotification` at `0x18000a1f0`
- `ntdll!TpWaitForJobNotification` at `0x18000a20f`
- `ntdll!TpWaitForJobNotification` at `0x18000a22e`
- `ntdll!TpWaitForJobNotification` at `0x18000a1d1`
- `ntdll!TpWaitForJobNotification` at `0x18000a1f0`
- `ntdll!TpWaitForJobNotification` at `0x18000a20f`
- `ntdll!TpWaitForJobNotification` at `0x18000a22e`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000a152`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000a2df`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000a3ea`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000a152`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000a2df`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000a3ea`
- `ntdll!RtlFreeHeap` at `0x18000a39e`
- `ntdll!RtlFreeHeap` at `0x18000a3c5`
- `ntdll!RtlFreeHeap` at `0x18000a5eb`
- `ntdll!RtlFreeHeap` at `0x18000a39e`
- `ntdll!RtlFreeHeap` at `0x18000a3c5`
- `ntdll!RtlFreeHeap` at `0x18000a5eb`
- `ntdll!TpReleaseWork` at `0x18000a1bf`
- `ntdll!TpReleaseWork` at `0x18000a25f`
- `ntdll!TpReleaseWork` at `0x18000a271`
- `ntdll!TpReleaseWork` at `0x18000a283`
- `ntdll!TpReleaseWork` at `0x18000a1bf`
- `ntdll!TpReleaseWork` at `0x18000a25f`
- `ntdll!TpReleaseWork` at `0x18000a271`
- `ntdll!TpReleaseWork` at `0x18000a283`
- `ntdll!TpWaitForWork` at `0x18000a1b2`
- `ntdll!TpWaitForWork` at `0x18000a1b2`
- `ntdll!TpPostWork` at `0x18000a675`
- `ntdll!TpPostWork` at `0x18000a6e1`
- `ntdll!TpPostWork` at `0x18000a675`
- `ntdll!TpPostWork` at `0x18000a6e1`
- `ntdll!NtClose` at `0x18000a110`
- `ntdll!NtClose` at `0x18000a122`
- `ntdll!NtClose` at `0x18000a24d`
- `ntdll!NtClose` at `0x18000a2ca`
- `ntdll!NtClose` at `0x18000a2f9`
- `ntdll!NtClose` at `0x18000a30b`
- `ntdll!NtClose` at `0x18000a471`
- `ntdll!NtClose` at `0x18000a110`
- `ntdll!NtClose` at `0x18000a122`
- `ntdll!NtClose` at `0x18000a24d`
- `ntdll!NtClose` at `0x18000a2ca`
- `ntdll!NtClose` at `0x18000a2f9`
- `ntdll!NtClose` at `0x18000a30b`
- `ntdll!NtClose` at `0x18000a471`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18000a440`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18000a440`
- `ntdll!TpReleaseTimer` at `0x18000a19e`
- `ntdll!TpReleaseTimer` at `0x18000a19e`
- `ntdll!TpWaitForTimer` at `0x18000a191`
- `ntdll!TpWaitForTimer` at `0x18000a191`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18000a55a`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18000a55a`
- `ntdll!NtDeleteWnfStateName` at `0x18000a13d`
- `ntdll!NtDeleteWnfStateName` at `0x18000a16a`
- `ntdll!NtDeleteWnfStateName` at `0x18000a17a`
- `ntdll!NtDeleteWnfStateName` at `0x18000a418`
- `ntdll!NtDeleteWnfStateName` at `0x18000a13d`
- `ntdll!NtDeleteWnfStateName` at `0x18000a16a`
- `ntdll!NtDeleteWnfStateName` at `0x18000a17a`
- `ntdll!NtDeleteWnfStateName` at `0x18000a418`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000a15a`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000a2e7`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000a3f2`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000a15a`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000a2e7`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000a3f2`
- `ntdll!TpReleaseJobNotification` at `0x18000a1de`
- `ntdll!TpReleaseJobNotification` at `0x18000a1fd`
- `ntdll!TpReleaseJobNotification` at `0x18000a21c`
- `ntdll!TpReleaseJobNotification` at `0x18000a23b`
- `ntdll!TpReleaseJobNotification` at `0x18000a1de`
- `ntdll!TpReleaseJobNotification` at `0x18000a1fd`
- `ntdll!TpReleaseJobNotification` at `0x18000a21c`
- `ntdll!TpReleaseJobNotification` at `0x18000a23b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a0cc`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a5f8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a68f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a0cc`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a5f8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a68f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a0fe`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a682`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a6ee`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a0fe`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a682`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a6ee`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009cc5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009cc5`
- `ext-ms-win-core-psm-service-l1-1-2!PsmHostStateNotification2` at `0x18000a377`
- `ext-ms-win-core-psm-service-l1-1-2!PsmHostStateNotification2` at `0x18000a377`
- `NduProv!__imp_NduDeleteAppContext` at `0x18000a458`
- `NduProv!__imp_NduDeleteAppContext` at `0x18000a458`

## pseudocode

```c
int __fastcall PsmpDereferenceApplicationEx(__int64 a1, unsigned int a2)
{
  unsigned int v2; // r12d
  signed __int32 v4; // ebx
  __int64 v5; // rax
  char *v6; // rcx
  __int64 v7; // rax
  bool v8; // zf
  int v9; // eax
  _QWORD **v10; // rbx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  _QWORD *v13; // rax
  _QWORD **v14; // rbx
  _QWORD *v15; // rcx
  __int64 v16; // rax
  _QWORD *v17; // rdx
  _QWORD *v18; // r14
  __int64 v19; // rcx
  int v20; // r8d
  __int64 v21; // r10
  __int64 v22; // rdx
  int v23; // r9d
  int v24; // r9d
  int v25; // eax
  __int64 v26; // rcx
  int v27; // r8d
  __int64 v28; // r10
  __int64 v29; // rdx
  int v30; // r9d
  int v31; // r9d
  int v32; // eax
  _QWORD *v33; // rbx
  __int64 v34; // rcx
  int v35; // r8d
  __int64 v36; // r10
  __int64 v37; // rdx
  int v38; // r9d
  int v39; // r9d
  int v40; // eax
  __int64 *v41; // rbx
  __int64 *v42; // rcx
  __int64 **v43; // rax
  void *v44; // rcx
  void *v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  void *v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 i; // rbx
  void *v53; // rcx
  void *v54; // rcx
  void *v55; // rcx
  __int64 *v56; // rbx
  int *v57; // rsi
  int v58; // eax
  int v59; // eax
  __int64 v60; // rcx
  void *v61; // rcx
  __int64 Args; // rcx
  __int64 v63; // rax
  int v64; // r14d
  wchar_t *p_Buffer; // rsi
  WCHAR v66; // bx
  int v67; // ecx
  volatile signed __int32 *ApplicationUsageInfoEntry; // rax
  volatile signed __int32 *v69; // rbx
  signed __int32 v70; // r15d
  __int64 v71; // rax
  char v72; // cl
  _QWORD *v73; // rdx
  _QWORD *v74; // rdx
  bool v76; // [rsp+50h] [rbp-B0h] BYREF
  int v77; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v78; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v79; // [rsp+68h] [rbp-98h] BYREF
  signed __int32 v80; // [rsp+70h] [rbp-90h] BYREF
  __int64 v81; // [rsp+78h] [rbp-88h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-70h] BYREF
  void *v84; // [rsp+A0h] [rbp-60h]
  int v85; // [rsp+A8h] [rbp-58h]
  int v86; // [rsp+ACh] [rbp-54h]
  signed __int32 *v87; // [rsp+B0h] [rbp-50h]
  __int64 v88; // [rsp+B8h] [rbp-48h]
  char *v89; // [rsp+C0h] [rbp-40h]
  int v90; // [rsp+C8h] [rbp-38h]
  int v91; // [rsp+CCh] [rbp-34h]
  bool *v92; // [rsp+D0h] [rbp-30h]
  __int64 v93; // [rsp+D8h] [rbp-28h]
  wchar_t Buffer; // [rsp+E0h] [rbp-20h] BYREF
  int v95; // [rsp+E8h] [rbp-18h]
  int v96; // [rsp+F8h] [rbp-8h]
  _BYTE v97[4]; // [rsp+FCh] [rbp-4h] BYREF
  __int64 v98; // [rsp+100h] [rbp+0h] BYREF
  int v99; // [rsp+318h] [rbp+218h]
  __int64 v100; // [rsp+320h] [rbp+220h]
  int v101; // [rsp+328h] [rbp+228h]
  int v102; // [rsp+338h] [rbp+238h]

  LODWORD(v79) = a2;
  v2 = a2;
  v4 = _InterlockedDecrement((volatile signed __int32 *)a1);
  if ( v4 == -1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LODWORD(v5) = dword_18003F048;
  if ( (unsigned int)dword_18003F048 > 5 )
  {
    LODWORD(v5) = qword_18003F058;
    if ( (qword_18003F058 & 2) != 0 )
    {
      v5 = qword_18003F060 & 2;
      if ( v5 == qword_18003F060 )
      {
        v6 = (char *)(a1 + 7040);
        v80 = v4;
        v88 = 4;
        v87 = &v80;
        if ( a1 == -7040 )
        {
          v6 = byte_180034900;
          v9 = 2;
        }
        else
        {
          v7 = -1;
          do
            v8 = *(_WORD *)&v6[2 * v7++ + 2] == 0;
          while ( !v8 );
          v9 = 2 * v7 + 2;
        }
        v90 = v9;
        v89 = v6;
        v92 = &v76;
        *(_DWORD *)&EventDescriptor.Level = 5;
        UserData.Ptr = (ULONGLONG)off_18003F050;
        v76 = (v4 & 0x7FFFFFFF) == 0;
        v91 = 0;
        v93 = 1;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 2;
        UserData.Size = *(unsigned __int16 *)off_18003F050;
        v84 = &unk_1800380E8;
        UserData.Reserved = 2;
        v85 = 59;
        v86 = 1;
        v78 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        LODWORD(v5) = EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
      }
    }
  }
  if ( (v4 & 0x7FFFFFFF) == 0 )
  {
    v10 = (_QWORD **)(a1 + 6840);
    while ( 1 )
    {
      v11 = *v10;
      if ( *v10 == v10 )
        break;
      v12 = *v11;
      if ( *(_QWORD **)(*v11 + 8LL) != v11 )
        goto LABEL_169;
      v13 = (_QWORD *)v11[1];
      if ( (_QWORD *)*v13 != v11 )
        goto LABEL_169;
      *v13 = v12;
      *(_QWORD *)(v12 + 8) = v13;
      PsmpResourceAwareTimerDereference(v11);
    }
    v14 = (_QWORD **)(a1 + 6856);
    while ( 1 )
    {
      v15 = *v14;
      if ( *v14 == v14 )
        break;
      v16 = *v15;
      if ( *(_QWORD **)(*v15 + 8LL) != v15 )
        goto LABEL_169;
      v17 = (_QWORD *)v15[1];
      if ( (_QWORD *)*v17 != v15 )
        goto LABEL_169;
      *v17 = v16;
      *(_QWORD *)(v16 + 8) = v17;
      PsmpResourceAwareTimerDereference(v15);
    }
    v78 = 0;
    PsmpCheckNotifyApplicationTerminated(a1, &v78);
    switch ( *(_DWORD *)(a1 + 344) )
    {
      case 5:
      case 6:
        v18 = (_QWORD *)(a1 + 192);
        break;
      default:
        v18 = (_QWORD *)(a1 + 192);
        if ( *(_QWORD *)(a1 + 192) )
        {
          memset_0(&Buffer, 0, 0x260u);
          v19 = *(_QWORD *)(a1 + 6944);
          v95 = 1;
          v96 = 2;
          PsmpNotificationsGetApplicationIdentityFromApplication(v19, v97);
          v20 = *(_DWORD *)(a1 + 6960);
          v21 = *(_QWORD *)(a1 + 6944);
          v102 = 3;
          switch ( v20 )
          {
            case 2:
              v22 = *(_QWORD *)(v21 + 6800);
              break;
            case 4:
              v22 = *(_QWORD *)(a1 + 6984);
              break;
            case 8:
              v22 = *(_QWORD *)(v21 + 6808);
              break;
            default:
              v22 = -1;
              break;
          }
          v23 = 0;
          if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v21 + 312) + 56LL) + 16LL) == 4 )
            v23 = 4;
          v24 = (*(_DWORD *)(v21 + 128) >> 19) & 2 | v23;
          if ( v20 == 4 || (v25 = 0, (v24 & 2) != 0) )
            v25 = 1;
          v100 = v22;
          v101 = v24 | v25;
          v99 = v20;
          PsmpNotificationsDeliverMessage(v21, &Buffer);
        }
        if ( *(_QWORD *)(a1 + 200) )
        {
          memset_0(&Buffer, 0, 0x260u);
          v26 = *(_QWORD *)(a1 + 6984);
          v95 = 1;
          v96 = 2;
          PsmpNotificationsGetApplicationIdentityFromApplication(v26, v97);
          v27 = *(_DWORD *)(a1 + 7000);
          v28 = *(_QWORD *)(a1 + 6984);
          v102 = 3;
          switch ( v27 )
          {
            case 2:
              v29 = *(_QWORD *)(v28 + 6800);
              break;
            case 4:
              v29 = *(_QWORD *)(a1 + 7024);
              break;
            case 8:
              v29 = *(_QWORD *)(v28 + 6808);
              break;
            default:
              v29 = -1;
              break;
          }
          v30 = 0;
          if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v28 + 312) + 56LL) + 16LL) == 4 )
            v30 = 4;
          v31 = (*(_DWORD *)(v28 + 128) >> 19) & 2 | v30;
          if ( v27 == 4 || (v32 = 0, (v31 & 2) != 0) )
            v32 = 1;
          v100 = v29;
          v101 = v31 | v32;
          v99 = v27;
          PsmpNotificationsDeliverMessage(v28, &Buffer);
        }
        v33 = *(_QWORD **)(a1 + 6816);
        if ( v33 != (_QWORD *)(a1 + 6816) )
        {
          do
          {
            memset_0(&Buffer, 0, 0x260u);
            v34 = *(v33 - 7);
            v95 = 1;
            v96 = 2;
            PsmpNotificationsGetApplicationIdentityFromApplication(v34, v97);
            v35 = *((_DWORD *)v33 - 10);
            v36 = *(v33 - 7);
            v102 = 3;
            switch ( v35 )
            {
              case 2:
                v37 = *(_QWORD *)(v36 + 6800);
                break;
              case 4:
                v37 = *(v33 - 2);
                break;
              case 8:
                v37 = *(_QWORD *)(v36 + 6808);
                break;
              default:
                v37 = -1;
                break;
            }
            v38 = 0;
            if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v36 + 312) + 56LL) + 16LL) == 4 )
              v38 = 4;
            v39 = (*(_DWORD *)(v36 + 128) >> 19) & 2 | v38;
            if ( v35 == 4 || (v40 = 0, (v39 & 2) != 0) )
              v40 = 1;
            v100 = v37;
            v101 = v39 | v40;
            v99 = v35;
            PsmpNotificationsDeliverMessage(v36, &Buffer);
            v33 = (_QWORD *)*v33;
          }
          while ( v33 != (_QWORD *)(a1 + 6816) );
          v2 = v79;
        }
        break;
    }
    if ( *v18 )
      PsmpNotificationsDeliverHostMessage(a1 + 6944, 1, 0);
    if ( *(_QWORD *)(a1 + 200) )
      PsmpNotificationsDeliverHostMessage(a1 + 6984, 1, 0);
    PsmpNotificationsDeliverApplicationMessage(a1, 1);
    PsmpRemoveHashEntry(*(_QWORD *)(a1 + 312) + 64LL, a1);
    v41 = (__int64 *)(a1 + 6720);
    if ( (__int64 *)*v41 != v41 )
    {
      RtlAcquireSRWLockExclusive(*(_QWORD *)(a1 + 312) + 48LL);
      v42 = (__int64 *)*v41;
      if ( *(__int64 **)(*v41 + 8) != v41 )
        goto LABEL_169;
      v43 = *(__int64 ***)(a1 + 6728);
      if ( *v43 != v41 )
        goto LABEL_169;
      *v43 = v42;
      v42[1] = (__int64)v43;
      RtlReleaseSRWLockExclusive(*(_QWORD *)(a1 + 312) + 48LL);
    }
    v44 = *(void **)(a1 + 216);
    if ( v44 )
      NtClose(v44);
    v45 = *(void **)(a1 + 224);
    if ( v45 )
      NtClose(v45);
    if ( *(_DWORD *)(a1 + 6832) || *(_DWORD *)(a1 + 6836) )
      ((void (*)(void))NtDeleteWnfStateName)();
    if ( *(_QWORD *)(a1 + 104) )
    {
      if ( (v2 & 1) != 0 )
        RtlUnsubscribeWnfStateChangeNotification();
      else
        RtlUnsubscribeWnfNotificationWaitForCompletion();
    }
    if ( *(_QWORD *)(a1 + 80) )
      NtDeleteWnfStateName(a1 + 80);
    if ( *(_QWORD *)(a1 + 88) )
      NtDeleteWnfStateName(a1 + 88);
    v46 = *(_QWORD *)(a1 + 304);
    if ( v46 )
    {
      TpWaitForTimer(v46, 1);
      TpReleaseTimer(*(_QWORD *)(a1 + 304));
    }
    v47 = *(_QWORD *)(a1 + 280);
    if ( v47 )
    {
      TpWaitForWork(v47, 0);
      TpReleaseWork(*(_QWORD *)(a1 + 280));
    }
    if ( *(_QWORD *)(a1 + 6736) )
    {
      TpWaitForJobNotification();
      TpReleaseJobNotification(*(_QWORD *)(a1 + 6736));
    }
    if ( *(_QWORD *)(a1 + 6744) )
    {
      TpWaitForJobNotification();
      TpReleaseJobNotification(*(_QWORD *)(a1 + 6744));
    }
    if ( *(_QWORD *)(a1 + 6752) )
    {
      TpWaitForJobNotification();
      TpReleaseJobNotification(*(_QWORD *)(a1 + 6752));
    }
    if ( *(_QWORD *)(a1 + 6760) )
    {
      TpWaitForJobNotification();
      TpReleaseJobNotification(*(_QWORD *)(a1 + 6760));
    }
    v48 = *(void **)(a1 + 192);
    if ( v48 )
      NtClose(v48);
    v49 = *(_QWORD *)(a1 + 6968);
    if ( v49 )
      TpReleaseWork(v49);
    v50 = *(_QWORD *)(a1 + 7008);
    if ( v50 )
      TpReleaseWork(v50);
    v51 = *(_QWORD *)(a1 + 6928);
    if ( v51 )
      TpReleaseWork(v51);
    for ( i = PsmpGetNextHostJobContext(a1, 0); i; i = PsmpGetNextHostJobContext(a1, i) )
      PsmpDereferenceHostContext(i, v2);
    v53 = *(void **)(a1 + 200);
    if ( v53 )
    {
      NtClose(v53);
      if ( *(_QWORD *)(a1 + 112) )
      {
        if ( (v2 & 2) != 0 )
          RtlUnsubscribeWnfStateChangeNotification();
        else
          RtlUnsubscribeWnfNotificationWaitForCompletion();
      }
    }
    v54 = *(void **)(a1 + 208);
    if ( v54 )
      NtClose(v54);
    v55 = *(void **)(a1 + 184);
    if ( v55 )
      NtClose(v55);
    v77 = 6;
    v81 = 0;
    if ( IsPsmHostStateNotification2Present() )
    {
      v56 = 0;
      v57 = 0;
      v81 = -1;
      v58 = 0;
      if ( v77 == 6 )
      {
        v57 = &v77;
        v58 = 1;
        v56 = &v81;
      }
      PsmHostStateNotification2(
        *(_QWORD *)(*(_QWORD *)(a1 + 312) + 40LL),
        *(unsigned int *)(*(_QWORD *)(a1 + 312) + 4LL),
        *(_QWORD *)(a1 + 8),
        v57,
        v56,
        v58,
        a1,
        0);
      if ( v57 && v57 != &v77 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v57);
      if ( v56 && v56 != &v81 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v56);
    }
    if ( *(_QWORD *)(a1 + 232) )
    {
      if ( *(_QWORD *)(a1 + 272) )
      {
        if ( (v2 & 4) != 0 )
          RtlUnsubscribeWnfStateChangeNotification();
        else
          RtlUnsubscribeWnfNotificationWaitForCompletion();
        *(_QWORD *)(a1 + 272) = 0;
      }
      if ( *(_DWORD *)(a1 + 264) || *(_DWORD *)(a1 + 268) )
      {
        NtDeleteWnfStateName(a1 + 264);
        *(_QWORD *)(a1 + 264) = 0;
      }
      v79 = 0;
      v59 = RtlRunOnceExecuteOnce(&PsmpNetInit, PsmpNetInitializeCallback, 0, &v79);
      v60 = 0;
      if ( v59 >= 0 )
        v60 = v79;
      NduDeleteAppContext(v60, *(_QWORD *)(a1 + 232));
      *(_QWORD *)(a1 + 232) = 0;
    }
    v61 = *(void **)(a1 + 240);
    if ( v61 )
      NtClose(v61);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_iLL(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids,
        *(_QWORD *)(a1 + 96),
        *(_DWORD *)(a1 + 344),
        8);
    if ( (Microsoft_Windows_ProcessStateManagerEnableBits & 1) != 0 )
      PsmpTraceAppStateChange(a1, *(unsigned int *)(a1 + 344), 8);
    Args = *(_QWORD *)(a1 + 8);
    v63 = -1;
    do
      v8 = *(_WORD *)(Args + 2 * v63++ + 2) == 0;
    while ( !v8 );
    if ( (unsigned __int64)(2 * v63 + 38) <= 0x240 )
      RtlStringCbPrintfExW(&Buffer, 2048, (wchar_t *)L"%ws%wc%I64d", Args);
    v64 = 0;
    p_Buffer = &Buffer;
    do
    {
      v66 = *p_Buffer++;
      v67 = 37 * v64 + RtlUpcaseUnicodeChar(v66);
      v64 = v67;
    }
    while ( v66 );
    ApplicationUsageInfoEntry = (volatile signed __int32 *)PsmpFindApplicationUsageInfoEntry(
                                                             &PsmpUsageTable[4 * (v67 & 0x7F) + 2 + 2 * (v67 & 0x7F)],
                                                             &Buffer,
                                                             (unsigned int)p_Buffer - ((unsigned int)&v98 - 32));
    v69 = ApplicationUsageInfoEntry;
    if ( ApplicationUsageInfoEntry )
    {
      _interlockedbittestandset(ApplicationUsageInfoEntry + 32, 0);
      v70 = _InterlockedDecrement(ApplicationUsageInfoEntry);
      if ( v70 == -1 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      else if ( (v70 & 0x7FFFFFFF) == 0 )
      {
        PsmpRemoveHashEntry(PsmpUsageTable, ApplicationUsageInfoEntry);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)v69);
      }
    }
    RtlAcquireSRWLockExclusive(&PsmpNotificationQueue);
    v71 = *(_QWORD *)(a1 + 7032);
    if ( v71 )
    {
      *(_BYTE *)(v71 + 560) |= 2u;
      *(_BYTE *)(v71 + 556) &= ~2u;
      if ( !*(_DWORD *)(v71 + 16) )
        *(_QWORD *)(a1 + 7032) = 0;
      v72 = *(_BYTE *)(v71 + 556);
      if ( (v72 & 1) == 0 )
      {
        *(_BYTE *)(v71 + 556) = v72 | 1;
        v73 = (_QWORD *)xmmword_180040B10;
        if ( *(__int64 **)xmmword_180040B10 != &qword_180040B08 )
          goto LABEL_169;
        *(_QWORD *)v71 = &qword_180040B08;
        *(_QWORD *)(v71 + 8) = v73;
        *v73 = v71;
        *(_QWORD *)&xmmword_180040B10 = v71;
        if ( !(_BYTE)qword_180040B20 )
        {
          LOBYTE(qword_180040B20) = 1;
          TpPostWork(*((_QWORD *)&xmmword_180040B10 + 1));
        }
      }
    }
    RtlReleaseSRWLockExclusive(&PsmpNotificationQueue);
    RtlAcquireSRWLockExclusive(&PsmpFreeAppListLock);
    v74 = off_18003F0C0[0];
    if ( *(_UNKNOWN ***)off_18003F0C0[0] != &PsmpFreeAppList )
LABEL_169:
      __fastfail(3u);
    *(_QWORD *)(a1 + 6872) = &PsmpFreeAppList;
    *(_QWORD *)(a1 + 6880) = v74;
    *v74 = a1 + 6872;
    off_18003F0C0[0] = (_UNKNOWN **)(a1 + 6872);
    if ( ++PsmpFreeAppListCount == 1 )
      TpPostWork(PsmpFreeAppListWorker);
    LODWORD(v5) = RtlReleaseSRWLockExclusive(&PsmpFreeAppListLock);
  }
  return v5;
}

```

## disassembly

```asm
0x180009b40  mov     [rsp-8+arg_10], rbx
0x180009b45  mov     [rsp-8+arg_18], rsi
0x180009b4a  push    rbp
0x180009b4b  push    rdi
0x180009b4c  push    r12
0x180009b4e  push    r13
0x180009b50  push    r15
0x180009b52  lea     rbp, [rsp-250h]
0x180009b5a  sub     rsp, 350h
0x180009b61  mov     rax, cs:__security_cookie
0x180009b68  xor     rax, rsp
0x180009b6b  mov     [rbp+270h+var_30], rax
0x180009b72  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180009b79  mov     dword ptr [rsp+370h+var_308], edx
0x180009b7d  mov     ebx, r15d
0x180009b80  mov     r12d, edx
0x180009b83  mov     rdi, rcx
0x180009b86  lock xadd [rcx], ebx
0x180009b8a  dec     ebx
0x180009b8c  cmp     ebx, 0FFFFFFFFh
0x180009b8f  jnz     short loc_180009B96
0x180009b91  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009b96  mov     eax, cs:dword_18003F048
0x180009b9c  mov     esi, ebx
0x180009b9e  and     esi, 7FFFFFFFh
0x180009ba4  setz    dl
0x180009ba7  xor     r13d, r13d
0x180009baa  cmp     eax, 5
0x180009bad  jbe     loc_180009CCB
0x180009bb3  mov     rcx, cs:qword_18003F060
0x180009bba  mov     rax, cs:qword_18003F058
0x180009bc1  test    al, 2
0x180009bc3  jz      loc_180009CCB
0x180009bc9  mov     rax, rcx
0x180009bcc  and     eax, 2
0x180009bcf  cmp     rax, rcx
0x180009bd2  jnz     loc_180009CCB
0x180009bd8  lea     rcx, [rdi+1B80h]
0x180009bdf  mov     [rsp+370h+var_300], ebx
0x180009be3  mov     [rbp+270h+var_2B8], 4
0x180009beb  lea     rax, [rsp+370h+var_300]
0x180009bf0  mov     [rbp+270h+var_2C0], rax
0x180009bf4  test    rcx, rcx
0x180009bf7  jz      short loc_180009C15
0x180009bf9  mov     rax, r15
0x180009bfc  nop     dword ptr [rax+00h]
0x180009c00  cmp     [rcx+rax*2+2], r13w
0x180009c06  lea     rax, [rax+1]
0x180009c0a  jnz     short loc_180009C00
0x180009c0c  lea     eax, ds:2[rax*2]
0x180009c13  jmp     short loc_180009C21
0x180009c15  lea     rcx, byte_180034900
0x180009c1c  mov     eax, 2
0x180009c21  mov     [rbp+270h+var_2A8], eax
0x180009c24  xor     r9d, r9d; RelatedActivityId
0x180009c27  mov     [rbp+270h+var_2B0], rcx
0x180009c2b  lea     rax, [rsp+370h+var_320]
0x180009c30  mov     [rbp+270h+var_2A0], rax
0x180009c34  lea     rcx, _TraceLoggingMetadata
0x180009c3b  movzx   eax, cs:word_1800380DE
0x180009c42  xor     r8d, r8d; ActivityId
0x180009c45  mov     dword ptr [rbp+270h+EventDescriptor.Level], eax
0x180009c48  mov     rax, cs:off_18003F050
0x180009c4f  mov     [rbp+270h+var_2E0.Ptr], rax
0x180009c53  mov     [rsp+370h+var_320], dl
0x180009c57  lea     rdx, [rbp+270h+EventDescriptor]; EventDescriptor
0x180009c5b  mov     [rbp+270h+var_2A4], r13d
0x180009c5f  mov     [rbp+270h+var_298], 1
0x180009c67  mov     dword ptr [rbp+270h+EventDescriptor.Id], 0B000000h
0x180009c6e  mov     [rbp+270h+EventDescriptor.Keyword], 2
0x180009c76  movzx   eax, word ptr [rax]
0x180009c79  mov     [rbp+270h+var_2E0.Size], eax
0x180009c7c  lea     rax, unk_1800380E8
0x180009c83  mov     [rbp+270h+var_2D0], rax
0x180009c87  lea     rax, _TraceLoggingMetadataEnd
0x180009c8e  sub     eax, ecx
0x180009c90  mov     dword ptr [rbp+270h+var_2E0.0Ch], 2
0x180009c97  mov     [rbp+270h+var_2C8], 3Bh ; ';'
0x180009c9e  mov     [rbp+270h+var_2C4], 1
0x180009ca5  mov     [rsp+370h+var_310], eax
0x180009ca9  mov     eax, [rsp+370h+var_310]
0x180009cad  mov     rcx, cs:RegHandle; RegHandle
0x180009cb4  lea     rax, [rbp+270h+var_2E0]
0x180009cb8  mov     [rsp+370h+UserData], rax; UserData
0x180009cbd  mov     [rsp+370h+UserDataCount], 5; UserDataCount
0x180009cc5  call    cs:__imp_EventWriteTransfer
0x180009ccb  test    esi, esi
0x180009ccd  jnz     loc_18000A6FC
0x180009cd3  lea     rbx, [rdi+1AB8h]
0x180009cda  mov     [rsp+370h+arg_8], r14
0x180009ce2  mov     rcx, [rbx]; P
0x180009ce5  cmp     rcx, rbx
0x180009ce8  jz      short loc_180009D12
0x180009cea  mov     rdx, [rcx]
0x180009ced  cmp     [rdx+8], rcx
0x180009cf1  jnz     loc_18000A6A8
0x180009cf7  mov     rax, [rcx+8]
0x180009cfb  cmp     [rax], rcx
0x180009cfe  jnz     loc_18000A6A8
0x180009d04  mov     [rax], rdx
0x180009d07  mov     [rdx+8], rax
0x180009d0b  call    PsmpResourceAwareTimerDereference
0x180009d10  jmp     short loc_180009CE2
0x180009d12  lea     rbx, [rdi+1AC8h]
0x180009d19  nop     dword ptr [rax+00000000h]
0x180009d20  mov     rcx, [rbx]; P
0x180009d23  cmp     rcx, rbx
0x180009d26  jz      short loc_180009D50
0x180009d28  mov     rax, [rcx]
0x180009d2b  cmp     [rax+8], rcx
0x180009d2f  jnz     loc_18000A6A8
0x180009d35  mov     rdx, [rcx+8]
0x180009d39  cmp     [rdx], rcx
0x180009d3c  jnz     loc_18000A6A8
0x180009d42  mov     [rdx], rax
0x180009d45  mov     [rax+8], rdx
0x180009d49  call    PsmpResourceAwareTimerDereference
0x180009d4e  jmp     short loc_180009D20
0x180009d50  lea     rdx, [rsp+370h+var_310]
0x180009d55  mov     [rsp+370h+var_310], r13d
0x180009d5a  mov     rcx, rdi
0x180009d5d  call    PsmpCheckNotifyApplicationTerminated
0x180009d62  movsxd  rax, dword ptr [rdi+158h]
0x180009d69  cmp     eax, 7; switch 8 cases
0x180009d6c  ja      short def_180009D7F; jumptable 0000000180009D7F default case, cases 0-4,7
0x180009d6e  lea     rdx, __ImageBase
0x180009d75  mov     ecx, ds:(jpt_180009D7F - 180000000h)[rdx+rax*4]
0x180009d7c  add     rcx, rdx
0x180009d7f  jmp     rcx; switch jump
0x180009d81  lea     r14, [rdi+0C0h]; jumptable 0000000180009D7F cases 5,6
0x180009d88  jmp     loc_18000A05F
0x180009d8d  lea     r14, [rdi+0C0h]; jumptable 0000000180009D7F default case, cases 0-4,7
0x180009d94  cmp     [r14], r13
0x180009d97  jz      loc_180009E7D
0x180009d9d  xor     edx, edx; Val
0x180009d9f  lea     rcx, [rbp+270h+Buffer]; void *
0x180009da3  mov     r8d, 260h; Size
0x180009da9  call    memset_0
0x180009dae  mov     rcx, [rdi+1B20h]
0x180009db5  lea     rdx, [rbp+270h+var_274]
0x180009db9  mov     [rbp+270h+var_288], 1
0x180009dc0  mov     [rbp+270h+var_278], 2
0x180009dc7  call    PsmpNotificationsGetApplicationIdentityFromApplication
0x180009dcc  mov     r8d, [rdi+1B30h]
0x180009dd3  mov     r10, [rdi+1B20h]
0x180009dda  mov     [rbp+270h+var_38], 3
0x180009de4  cmp     r8d, 2
0x180009de8  jz      short loc_180009E13
0x180009dea  cmp     r8d, 4
0x180009dee  jz      short loc_180009E0A
0x180009df0  cmp     r8d, 6
0x180009df4  jz      short loc_180009DFC
0x180009df6  cmp     r8d, 8
0x180009dfa  jz      short loc_180009E01
0x180009dfc  mov     rdx, r15
0x180009dff  jmp     short loc_180009E1A
0x180009e01  mov     rdx, [r10+1A98h]
0x180009e08  jmp     short loc_180009E1A
0x180009e0a  mov     rdx, [rdi+1B48h]
0x180009e11  jmp     short loc_180009E1A
0x180009e13  mov     rdx, [r10+1A90h]
0x180009e1a  mov     rax, [r10+138h]
0x180009e21  mov     ebx, 4
0x180009e26  mov     r9d, r13d
0x180009e29  mov     rcx, [rax+38h]
0x180009e2d  mov     eax, [r10+80h]
0x180009e34  cmp     dword ptr [rcx+10h], 4
0x180009e38  cmovz   r9d, ebx
0x180009e3c  shr     eax, 13h
0x180009e3f  and     eax, 2
0x180009e42  or      r9d, eax
0x180009e45  cmp     r8d, ebx
0x180009e48  jz      short loc_180009E53
0x180009e4a  mov     eax, r13d
0x180009e4d  test    r9b, 2
0x180009e51  jz      short loc_180009E58
0x180009e53  mov     eax, 1
0x180009e58  mov     [rbp+270h+var_50], rdx
0x180009e5f  or      eax, r9d
0x180009e62  lea     rdx, [rbp+270h+Buffer]
0x180009e66  mov     [rbp+270h+var_48], eax
0x180009e6c  mov     rcx, r10
0x180009e6f  mov     [rbp+270h+var_58], r8d
0x180009e76  call    PsmpNotificationsDeliverMessage
0x180009e7b  jmp     short loc_180009E82
0x180009e7d  mov     ebx, 4
0x180009e82  cmp     [rdi+0C8h], r13
0x180009e89  jz      loc_180009F69
0x180009e8f  xor     edx, edx; Val
0x180009e91  lea     rcx, [rbp+270h+Buffer]; void *
0x180009e95  mov     r8d, 260h; Size
0x180009e9b  call    memset_0
0x180009ea0  mov     rcx, [rdi+1B48h]
0x180009ea7  lea     rdx, [rbp+270h+var_274]
0x180009eab  mov     [rbp+270h+var_288], 1
0x180009eb2  mov     [rbp+270h+var_278], 2
0x180009eb9  call    PsmpNotificationsGetApplicationIdentityFromApplication
0x180009ebe  mov     r8d, [rdi+1B58h]
0x180009ec5  mov     r10, [rdi+1B48h]
0x180009ecc  mov     [rbp+270h+var_38], 3
0x180009ed6  cmp     r8d, 2
0x180009eda  jz      short loc_180009F05
0x180009edc  cmp     r8d, 4
0x180009ee0  jz      short loc_180009EFC
0x180009ee2  cmp     r8d, 6
0x180009ee6  jz      short loc_180009EEE
0x180009ee8  cmp     r8d, 8
0x180009eec  jz      short loc_180009EF3
0x180009eee  mov     rdx, r15
0x180009ef1  jmp     short loc_180009F0C
0x180009ef3  mov     rdx, [r10+1A98h]
0x180009efa  jmp     short loc_180009F0C
0x180009efc  mov     rdx, [rdi+1B70h]
0x180009f03  jmp     short loc_180009F0C
0x180009f05  mov     rdx, [r10+1A90h]
0x180009f0c  mov     rax, [r10+138h]
0x180009f13  mov     r9d, r13d
0x180009f16  mov     rcx, [rax+38h]
0x180009f1a  mov     eax, [r10+80h]
0x180009f21  cmp     dword ptr [rcx+10h], 4
0x180009f25  cmovz   r9d, ebx
0x180009f29  shr     eax, 13h
0x180009f2c  and     eax, 2
0x180009f2f  or      r9d, eax
0x180009f32  cmp     r8d, 4
0x180009f36  jz      short loc_180009F41
0x180009f38  mov     eax, r13d
0x180009f3b  test    r9b, 2
0x180009f3f  jz      short loc_180009F46
0x180009f41  mov     eax, 1
0x180009f46  mov     [rbp+270h+var_50], rdx
0x180009f4d  or      eax, r9d
0x180009f50  lea     rdx, [rbp+270h+Buffer]
0x180009f54  mov     [rbp+270h+var_48], eax
0x180009f5a  mov     rcx, r10
0x180009f5d  mov     [rbp+270h+var_58], r8d
0x180009f64  call    PsmpNotificationsDeliverMessage
0x180009f69  lea     rsi, [rdi+1AA0h]
0x180009f70  mov     rbx, [rsi]
0x180009f73  cmp     rbx, rsi
0x180009f76  jz      loc_18000A05F
0x180009f7c  mov     r12d, 4
0x180009f82  xor     edx, edx; Val
0x180009f84  lea     rcx, [rbp+270h+Buffer]; void *
0x180009f88  mov     r8d, 260h; Size
0x180009f8e  call    memset_0
0x180009f93  mov     rcx, [rbx-38h]
0x180009f97  lea     rdx, [rbp+270h+var_274]
0x180009f9b  mov     [rbp+270h+var_288], 1
0x180009fa2  mov     [rbp+270h+var_278], 2
0x180009fa9  call    PsmpNotificationsGetApplicationIdentityFromApplication
0x180009fae  mov     r8d, [rbx-28h]
0x180009fb2  mov     r10, [rbx-38h]
0x180009fb6  mov     [rbp+270h+var_38], 3
0x180009fc0  cmp     r8d, 2
0x180009fc4  jz      short loc_180009FEB
0x180009fc6  cmp     r8d, r12d
0x180009fc9  jz      short loc_180009FE5
0x180009fcb  cmp     r8d, 6
0x180009fcf  jz      short loc_180009FD7
0x180009fd1  cmp     r8d, 8
0x180009fd5  jz      short loc_180009FDC
0x180009fd7  mov     rdx, r15
0x180009fda  jmp     short loc_180009FF2
0x180009fdc  mov     rdx, [r10+1A98h]
0x180009fe3  jmp     short loc_180009FF2
0x180009fe5  mov     rdx, [rbx-10h]
0x180009fe9  jmp     short loc_180009FF2
0x180009feb  mov     rdx, [r10+1A90h]
0x180009ff2  mov     rax, [r10+138h]
0x180009ff9  mov     r9d, r13d
0x180009ffc  mov     rcx, [rax+38h]
0x18000a000  mov     eax, [r10+80h]
0x18000a007  cmp     [rcx+10h], r12d
0x18000a00b  cmovz   r9d, r12d
0x18000a00f  shr     eax, 13h
0x18000a012  and     eax, 2
0x18000a015  or      r9d, eax
0x18000a018  cmp     r8d, r12d
0x18000a01b  jz      short loc_18000A026
0x18000a01d  mov     eax, r13d
0x18000a020  test    r9b, 2
0x18000a024  jz      short loc_18000A02B
0x18000a026  mov     eax, 1
0x18000a02b  mov     [rbp+270h+var_50], rdx
0x18000a032  or      eax, r9d
0x18000a035  lea     rdx, [rbp+270h+Buffer]
0x18000a039  mov     [rbp+270h+var_48], eax
0x18000a03f  mov     rcx, r10
0x18000a042  mov     [rbp+270h+var_58], r8d
0x18000a049  call    PsmpNotificationsDeliverMessage
0x18000a04e  mov     rbx, [rbx]
0x18000a051  cmp     rbx, rsi
0x18000a054  jnz     loc_180009F82
0x18000a05a  mov     r12d, dword ptr [rsp+370h+var_308]
0x18000a05f  cmp     [r14], r13
0x18000a062  jz      short loc_18000A078
0x18000a064  lea     rcx, [rdi+1B20h]
0x18000a06b  xor     r8d, r8d
0x18000a06e  mov     edx, 1
  ... truncated ...
```
