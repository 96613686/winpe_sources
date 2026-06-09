# CmInitSystem1

- ea: `0x140c89fc4`
- end: `0x140c8a99a`
- name: `CmInitSystem1`
- size: `2518`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3)`
- caller_count: `1`
- callee_count: `57`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140c4d7f4`

## callees

- `0x1403e84d0`
- `0x1403f2d50`
- `0x1403f8d70`
- `0x1404b3720`
- `0x14053a530`
- `0x140696e38`
- `0x1406d9d70`
- `0x1406daa70`
- `0x1406dac30`
- `0x1406f4880`
- `0x140726fcc`
- `0x14073d074`
- `0x1407f8ba4`
- `0x1407fc15c`
- `0x1407fe060`
- `0x1407fe294`
- `0x1407fe49c`
- `0x1407fe6f0`
- `0x1407ff0e4`
- `0x1407ff750`
- `0x1407ff9c0`
- `0x140800b98`
- `0x140800db8`
- `0x140800e50`
- `0x140801158`
- `0x1408729e0`
- `0x140899670`
- `0x14093d2d0`
- `0x14093f0e0`
- `0x14093f5b8`
- `0x14093fb00`
- `0x14093fb90`
- `0x14093fc90`
- `0x140a9b78c`
- `0x140ae6254`
- `0x140bae8e0`
- `0x140bf7910`
- `0x140bf7950`
- `0x140bf7a30`
- `0x140c89fc4`
- `0x140c8aea8`
- `0x140c8b3cc`
- `0x140c8b488`
- `0x140c8bd04`
- `0x140c8bdd4`
- `0x140c8c230`
- `0x140c8ca2c`
- `0x140c8cef8`
- `0x140c8d014`
- `0x140c8d114`

## import_xrefs

- `ext-ms-win-ntos-kcminitcfg-l1-1-0!CmSetInitMachineConfig` at `0x140c8a882`
- `ext-ms-win-ntos-kcminitcfg-l1-1-0!CmSetInitMachineConfig` at `0x140c8a882`

## pseudocode

```c
char __fastcall CmInitSystem1(ULONG_PTR BugCheckParameter3)
{
  __int64 i; // rax
  __int64 j; // rsi
  __int64 v4; // rbx
  int ObjectTypes; // eax
  int v6; // eax
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  int Hive; // eax
  int v13; // eax
  int inited; // eax
  void *v15; // rbx
  NTSTATUS v16; // eax
  ULONG_PTR v17; // rsi
  NTSTATUS v18; // eax
  ULONG_PTR v19; // rsi
  int v20; // eax
  ULONG_PTR v21; // rsi
  NTSTATUS v22; // eax
  ULONG_PTR v23; // rsi
  int v24; // eax
  int ControlSet; // eax
  __int64 k; // rcx
  __int64 v27; // rax
  int v28; // eax
  ULONG_PTR v29; // rsi
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int ExtendedControlSets; // eax
  __int64 v34; // rcx
  int v35; // eax
  int v36; // eax
  __int64 v37; // rcx
  int v38; // eax
  int v39; // eax
  HANDLE KeyHandle; // [rsp+70h] [rbp-90h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  int v43[2]; // [rsp+A8h] [rbp-58h] BYREF
  UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v45; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v46; // [rsp+D0h] [rbp-30h]
  struct _KAPC_STATE ApcState; // [rsp+D8h] [rbp-28h] BYREF
  _OWORD BugCheckParameter4[27]; // [rsp+110h] [rbp+10h] BYREF
  _DWORD v49[116]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v46 = 0;
  KeyHandle = 0;
  *(_QWORD *)v43 = 0;
  v45 = 0;
  memset(&ObjectAttributes, 0, 44);
  memset_0(v49, 0, sizeof(v49));
  DestinationString = 0;
  memset_0(BugCheckParameter4, 0, sizeof(BugCheckParameter4));
  memset(&ApcState, 0, sizeof(ApcState));
  CmpInitializeThreadInfo(&v45);
  CmpInitializeParseContext(v49);
  *($C9C4F79064DE35237E3F199A7D1BD3E1 *)((char *)&CmpCallbackListLock.116 + 4) = ($C9C4F79064DE35237E3F199A7D1BD3E1)&IoFileObjectType;
  if ( InitIsWinPEMode )
  {
    BYTE6(NlsMbOemCodePageTag) = InitIsWinPEMode;
    BYTE5(NlsMbOemCodePageTag) = 1;
    CmpForceSynchronousMachineHiveLoad = 1;
  }
  if ( HIDWORD(WheapPfaLock.CycleTime) )
    BYTE5(NlsMbOemCodePageTag) = 1;
  if ( BYTE5(NlsMbOemCodePageTag) )
  {
    for ( i = 0; i != 7; ++i )
    {
      if ( CmpMachineHiveList[23 * i] )
        LODWORD(qword_140E0CFE0[23 * i]) |= 0x8000u;
    }
  }
  CmpInitializeRegistryNames();
  CmpInitGlobalQuotaAllowed();
  CmpCallbackListLock.TrapFrame = 0;
  CmpKeyLockTracker.Timer.TimerListEntry.Blink = &CmpKeyLockTracker.Timer.TimerListEntry;
  CmpKeyLockTracker.Timer.TimerListEntry.Flink = &CmpKeyLockTracker.Timer.TimerListEntry;
  *(_QWORD *)&PspActiveProcessLock.Timer.Header.Lock = &PspActiveProcessLock.RelativeTimerBias;
  PspActiveProcessLock.RelativeTimerBias = (unsigned __int64)&PspActiveProcessLock.RelativeTimerBias;
  CmpCallbackListLock.ApcState.ApcListHead[0].Flink = 0;
  CmpShutdownRundown.Count = 0;
  CmpHiveLoadUnloadRundown.Count = 0;
  CmpActiveHiveRundownEvent = 0;
  *(_QWORD *)&CmpKeyLockTracker.Timer.Processor = 0;
  CmpKeyLockTracker.Timer.DueTime.QuadPart = 0;
  CmpRegistryLock = (struct _KTHREAD *)ExAllocateCacheAwarePushLock(1);
  CmpKeyLockTracker.Timer.Header.WaitListHead.Flink = (struct _LIST_ENTRY *)&CmpKeyLockTracker.Timer;
  *(_QWORD *)&CmpKeyLockTracker.Timer.Header.Lock = &CmpKeyLockTracker.Timer;
  qword_140FDA5B0 = (__int64)&CmpAsyncKernelPostList;
  CmpAsyncKernelPostList = (__int64)&CmpAsyncKernelPostList;
  *((_DWORD *)&CmpKeyLockTracker.SwapListEntry + 2) = 1;
  CmpKeyLockTracker.Queue = 0;
  LODWORD(CmpKeyLockTracker.Teb) = 0;
  LOWORD(CmpKeyLockTracker.RelativeTimerBias) = 1;
  BYTE2(CmpKeyLockTracker.RelativeTimerBias) = 6;
  HIDWORD(CmpKeyLockTracker.RelativeTimerBias) = 0;
  CmpInitializeNameCache();
  ExInitializeLookasideListExInternal(&CmpKcbLookaside.L.ListHead, 0, 312, 1651199299, 0, 0);
  CmpInitSIDToHiveMapping();
  WheapPfaLock.Queue = (_DISPATCHER_HEADER *volatile)CmpAdminSystemSecurityDescriptor();
  CmpInitializeTrustedInstallerSid();
  CmpInitializeDelayedCloseTable();
  CmpInitCallbacks();
  CmpInitializeMachineHiveLoadedCallbacks();
  CmpInitializeFreezeThaw();
  HvInitializeHashLibrary();
  CmpValidateGlobalFlushControlFlags();
  CmpInitializeGlobalKeyLockTracker();
  CmpInitializeTransactions();
  CmpVolumeManagerInitialize();
  for ( j = 0; j != 8; ++j )
  {
    v4 = 3 * j;
    RtlInitUnicodeString(&DestinationString, (&CmpBootLoadControl)[3 * j]);
    dword_140E0D58C[2 * v4] = CmpHashUnicodeComponent(&DestinationString);
  }
  ObjectTypes = CmpCreateObjectTypes();
  if ( ObjectTypes < 0 )
    KeBugCheckEx(0x67u, 1u, 1u, ObjectTypes, 0);
  v6 = CmpInitializeLightWeightTransactionType();
  if ( v6 < 0 )
    KeBugCheckEx(0x67u, 1u, 0x18u, v6, 0);
  v7 = CmpInitializeRegistryProcess();
  if ( v7 < 0 )
    KeBugCheckEx(0x67u, 1u, 0x19u, v7, 0);
  CmpAttachToRegistryProcess(&ApcState);
  CmpLockRegistryExclusive(v9, v8, v10, v11);
  CmpInitializePreloadedHives(BugCheckParameter3, 0);
  Hive = CmpCreateHive(&CmpMasterHive, 0, 1, 0, 0, 0, 0, 0x20000, 0, 0, 0, 0, (__int64)BugCheckParameter4);
  if ( Hive < 0 )
    KeBugCheckEx(0x67u, 1u, 2u, Hive, (ULONG_PTR)BugCheckParameter4);
  v13 = CmpInitializeKcbCache(CmpMasterHive, 128);
  if ( v13 < 0 )
    KeBugCheckEx(0x67u, 1u, 3u, v13, 0);
  if ( (int)CmpCreateRegistryRoot() < 0 )
    KeBugCheckEx(0x67u, 1u, 4u, 0, 0);
  inited = CmpInitSiloSupport(0);
  if ( inited < 0 )
    KeBugCheckEx(0x67u, 1u, 0x1Au, inited, 0);
  v15 = (void *)CmpHiveRootSecurityDescriptor();
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&PspActiveProcessLock.WaitBlockFill11[32];
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.SecurityDescriptor = v15;
  ObjectAttributes.SecurityQualityOfService = 0;
  v16 = ZwCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, (PUNICODE_STRING)&nullclass, 0, 0);
  v17 = v16;
  if ( v16 < 0 )
  {
    ExFreePoolWithTag(v15, 0);
    KeBugCheckEx(0x67u, 1u, 5u, v17, 0);
  }
  ZwClose(KeyHandle);
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&PspActiveProcessLock.ExtendedFeatureDisableMask;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.SecurityDescriptor = v15;
  ObjectAttributes.SecurityQualityOfService = 0;
  v18 = ZwCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, (PUNICODE_STRING)&nullclass, 0, 0);
  v19 = v18;
  if ( v18 < 0 )
  {
    ExFreePoolWithTag(v15, 0);
    KeBugCheckEx(0x67u, 1u, 6u, v19, 0);
  }
  ZwClose(KeyHandle);
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&PspActiveProcessLock.KernelShadowStack;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.SecurityDescriptor = v15;
  ObjectAttributes.SecurityQualityOfService = 0;
  v49[0] = 65;
  v20 = ObOpenObjectByName(
          (unsigned int)&ObjectAttributes,
          (_DWORD)CmKeyObjectType,
          0,
          0,
          131103,
          (__int64)v49,
          (__int64)&KeyHandle);
  v21 = v20;
  if ( v20 < 0 )
  {
    ExFreePoolWithTag(v15, 0);
    CmpCleanupParseContext(v49, 0);
    KeBugCheckEx(0x67u, 1u, 7u, v21, 0);
  }
  CmpCleanupParseContext(v49, 0);
  ZwClose(KeyHandle);
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&PspActiveProcessLock.KernelShadowStackBase;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.SecurityDescriptor = v15;
  ObjectAttributes.SecurityQualityOfService = 0;
  v22 = ZwCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, (PUNICODE_STRING)&nullclass, 0, 0);
  v23 = v22;
  if ( v22 < 0 )
  {
    ExFreePoolWithTag(v15, 0);
    KeBugCheckEx(0x67u, 1u, 8u, v23, 0);
  }
  ZwClose(KeyHandle);
  BYTE3(PspActiveProcessLock.Header.WaitListHead.Flink) = 1;
  CmpInitializeLoadOptions(BugCheckParameter3);
  v24 = CmpInitializePreloadedHives(BugCheckParameter3, 1);
  if ( v24 < 0 )
    KeBugCheckEx(0x67u, 1u, 0x14u, v24, 0);
  ControlSet = CmpCreateControlSet(L"SYSTEM", 0);
  if ( ControlSet < 0 )
    KeBugCheckEx(0x67u, 1u, 0xDu, ControlSet, 0);
  if ( LODWORD(ExpPlatformBinaryLock.CycleTime) )
    *(_DWORD *)(MmWriteableSharedUserData + 752) |= 0x10u;
  if ( HIDWORD(WheapPfaLock.KernelStack) )
  {
    if ( LODWORD(WheapPfaLock.KernelStack) )
    {
      for ( k = 0; k != 7; ++k )
      {
        v27 = 23 * k;
        LODWORD(qword_140E0CFE0[v27]) |= 0x8000u;
      }
    }
    else
    {
      byte_140E0D0B4 = 0;
      if ( !WheapPfaLock.ExpectedRunTime )
      {
        dword_140E0D150 |= 0x8000u;
        dword_140E0D208 |= 0x8000u;
      }
      byte_140E0D394 = 0;
      byte_140E0D44B = 1;
    }
  }
  memset_0(BugCheckParameter4, 0, sizeof(BugCheckParameter4));
  v28 = CmpCreateHive((ULONG_PTR *)v43, 0, 1, 0, 0, 0, 0, 0x20000, 0, 0, 0, 0, (__int64)BugCheckParameter4);
  v29 = v28;
  if ( v28 < 0 )
  {
    ExFreePoolWithTag(v15, 0);
    KeBugCheckEx(0x67u, 1u, 0x10u, v29, (ULONG_PTR)BugCheckParameter4);
  }
  v30 = CmpLinkHiveToMaster(
          (__int64)&PspActiveProcessLock.SchedulerSharedSwappablePage,
          0,
          *(__int64 *)v43,
          1,
          dword_140E0CFE8,
          0,
          0,
          (__int64)v15,
          0,
          0,
          1,
          BugCheckParameter4);
  if ( v30 )
    KeBugCheckEx(0x67u, 1u, 0x11u, v30, 0);
  CmpAddToHiveFileList(*(_QWORD *)v43);
  ExFreePoolWithTag(v15, 0);
  qword_140E0CFD8 = *(_QWORD *)v43;
  v31 = CmpInitializeHardwareConfiguration(BugCheckParameter3);
  if ( v31 < 0 )
    KeBugCheckEx(0x67u, 1u, 0x12u, v31, 0);
  v32 = CmpInitializeDriverStores(BugCheckParameter3);
  if ( v32 < 0 )
    KeBugCheckEx(0x67u, 1u, 0x13u, v32, 0);
  ExtendedControlSets = CmpCreateExtendedControlSets(BugCheckParameter3);
  if ( ExtendedControlSets < 0 )
    KeBugCheckEx(0x67u, 1u, 0x1Bu, ExtendedControlSets, 0);
  CmpCreateHardwareProfiles(BugCheckParameter3);
  CmSetInitMachineConfig(BugCheckParameter3);
  CmpUnlockRegistry(v34);
  CmpMarkCurrentProfileDirty();
  v35 = CmpInitializeMachineDependentConfiguration(BugCheckParameter3);
  if ( v35 < 0 )
    KeBugCheckEx(0x67u, 1u, 0x15u, v35, 0);
  v36 = CmpSetSystemValues(BugCheckParameter3);
  if ( v36 < 0 )
    KeBugCheckEx(0x67u, 1u, 0x16u, v36, 0);
  CmpMigrateOOBELanguageToInstallationLanguage();
  ExFreePoolWithTag(CmpLoadOptions.Buffer, 0);
  v37 = *(_QWORD *)(BugCheckParameter3 + 240);
  if ( *(_DWORD *)v37 >= 0x68u )
  {
    if ( *(_QWORD *)(v37 + 96) )
    {
      v38 = CmpSetNetworkValue();
      if ( v38 < 0 )
        KeBugCheckEx(0x67u, 1u, 0x17u, v38, 0);
    }
  }
  v39 = CmFcInitSystem2();
  if ( v39 < 0 )
    KeBugCheckEx(0x67u, 1u, 0x1Au, v39, 0);
  CmpDetachFromRegistryProcess(&ApcState);
  KeGetCurrentThread()[1].UserAffinity = (_KAFFINITY_EX *)v45;
  return 1;
}

```

## disassembly

```asm
0x140c89fc4  push    rbp
0x140c89fc6  push    rbx
0x140c89fc7  push    rsi
0x140c89fc8  push    rdi
0x140c89fc9  push    r12
0x140c89fcb  push    r13
0x140c89fcd  push    r14
0x140c89fcf  push    r15
0x140c89fd1  lea     rbp, [rsp-3A8h]
0x140c89fd9  sub     rsp, 4A8h
0x140c89fe0  mov     rax, cs:__security_cookie
0x140c89fe7  xor     rax, rsp
0x140c89fea  mov     [rbp+3E0h+var_50], rax
0x140c89ff1  xorps   xmm0, xmm0
0x140c89ff4  mov     rdi, rcx
0x140c89ff7  xor     eax, eax
0x140c89ff9  lea     rcx, [rbp+3E0h+var_220]; void *
0x140c8a000  xor     r14d, r14d
0x140c8a003  mov     [rbp+3E0h+var_410], rax
0x140c8a007  movups  xmmword ptr [rbp+3E0h+ObjectAttributes.ObjectName], xmm0
0x140c8a00b  xor     edx, edx; Val
0x140c8a00d  mov     [rsp+4E0h+KeyHandle], r14
0x140c8a012  mov     r8d, 1D0h; Size
0x140c8a018  mov     qword ptr [rbp+3E0h+var_438], r14
0x140c8a01c  movups  xmmword ptr [rbp+3E0h+ObjectAttributes+1Ch], xmm0
0x140c8a020  movups  [rbp+3E0h+var_420], xmm0
0x140c8a024  movups  xmmword ptr [rsp+4E0h+ObjectAttributes.Length], xmm0
0x140c8a029  call    memset_0
0x140c8a02e  xorps   xmm0, xmm0
0x140c8a031  lea     rcx, [rbp+3E0h+var_3D0]; void *
0x140c8a035  xor     edx, edx; Val
0x140c8a037  mov     r8d, 1B0h; Size
0x140c8a03d  movups  xmmword ptr [rbp+3E0h+DestinationString.Length], xmm0
0x140c8a041  call    memset_0
0x140c8a046  xorps   xmm0, xmm0
0x140c8a049  lea     rcx, [rbp+3E0h+var_420]
0x140c8a04d  movups  xmmword ptr [rbp+3E0h+ApcState.ApcListHead.Flink], xmm0
0x140c8a051  movups  xmmword ptr [rbp+3E0h+ApcState.ApcListHead.Flink+10h], xmm0
0x140c8a055  movups  xmmword ptr [rbp+3E0h+ApcState.Process], xmm0
0x140c8a059  call    CmpInitializeThreadInfo
0x140c8a05e  lea     rcx, [rbp+3E0h+var_220]
0x140c8a065  call    CmpInitializeParseContext
0x140c8a06a  lea     rax, IoFileObjectType
0x140c8a071  mov     qword ptr cs:CmpCallbackListLock.___u16+4, rax
0x140c8a078  lea     r15d, [r14+1]
0x140c8a07c  mov     al, cs:InitIsWinPEMode
0x140c8a082  test    al, al
0x140c8a084  jz      short loc_140C8A09A
0x140c8a086  mov     byte ptr cs:NlsMbOemCodePageTag+6, al
0x140c8a08c  mov     byte ptr cs:NlsMbOemCodePageTag+5, r15b
0x140c8a093  mov     cs:CmpForceSynchronousMachineHiveLoad, r15b
0x140c8a09a  cmp     dword ptr cs:WheapPfaLock.CycleTime+4, r14d
0x140c8a0a1  jz      short loc_140C8A0AA
0x140c8a0a3  mov     byte ptr cs:NlsMbOemCodePageTag+5, r15b
0x140c8a0aa  cmp     byte ptr cs:NlsMbOemCodePageTag+5, r14b
0x140c8a0b1  lea     r12, cs:140000000h
0x140c8a0b8  mov     r13d, 8000h
0x140c8a0be  jz      short loc_140C8A0E5
0x140c8a0c0  mov     rax, r14
0x140c8a0c3  imul    rcx, rax, 0B8h
0x140c8a0ca  cmp     [rcx+r12+0E0CFC0h], r14
0x140c8a0d2  jz      short loc_140C8A0DC
0x140c8a0d4  or      [rcx+r12+0E0CFE0h], r13d
0x140c8a0dc  add     rax, r15
0x140c8a0df  cmp     rax, 7
0x140c8a0e3  jnz     short loc_140C8A0C3
0x140c8a0e5  call    CmpInitializeRegistryNames
0x140c8a0ea  call    CmpInitGlobalQuotaAllowed
0x140c8a0ef  lea     rax, CmpKeyLockTracker.Timer.TimerListEntry
0x140c8a0f6  mov     cs:CmpCallbackListLock.TrapFrame, r14
0x140c8a0fd  lea     r8, PspActiveProcessLock.RelativeTimerBias
0x140c8a104  mov     cs:CmpKeyLockTracker.Timer.TimerListEntry.Blink, rax
0x140c8a10b  mov     ecx, r15d
0x140c8a10e  mov     cs:CmpKeyLockTracker.Timer.TimerListEntry.Flink, rax
0x140c8a115  mov     qword ptr cs:PspActiveProcessLock.Timer.Header, r8
0x140c8a11c  mov     cs:PspActiveProcessLock.RelativeTimerBias, r8
0x140c8a123  mov     qword ptr cs:CmpCallbackListLock.___u25, r14
0x140c8a12a  mov     qword ptr cs:CmpShutdownRundown.___u0, r14
0x140c8a131  mov     qword ptr cs:CmpHiveLoadUnloadRundown.___u0, r14
0x140c8a138  mov     cs:CmpActiveHiveRundownEvent, r14
0x140c8a13f  mov     qword ptr cs:CmpKeyLockTracker.Timer.Processor, r14
0x140c8a146  mov     qword ptr cs:CmpKeyLockTracker.Timer.DueTime, r14
0x140c8a14d  call    ExAllocateCacheAwarePushLock
0x140c8a152  mov     cs:CmpRegistryLock, rax
0x140c8a159  lea     rax, CmpKeyLockTracker.Timer
0x140c8a160  mov     cs:CmpKeyLockTracker.Timer.Header.WaitListHead.Flink, rax
0x140c8a167  mov     qword ptr cs:CmpKeyLockTracker.Timer.Header, rax
0x140c8a16e  lea     rax, CmpAsyncKernelPostList
0x140c8a175  mov     cs:qword_140FDA5B0, rax
0x140c8a17c  mov     cs:CmpAsyncKernelPostList, rax
0x140c8a183  mov     dword ptr cs:CmpKeyLockTracker.___u28+8, r15d
0x140c8a18a  mov     cs:CmpKeyLockTracker.Queue, r14
0x140c8a191  mov     dword ptr cs:CmpKeyLockTracker.Teb, r14d
0x140c8a198  mov     word ptr cs:CmpKeyLockTracker.RelativeTimerBias, r15w
0x140c8a1a0  mov     byte ptr cs:CmpKeyLockTracker.RelativeTimerBias+2, 6
0x140c8a1a7  mov     dword ptr cs:CmpKeyLockTracker.RelativeTimerBias+4, r14d
0x140c8a1ae  call    CmpInitializeNameCache
0x140c8a1b3  mov     dword ptr [rsp+4E0h+var_4A0], r14d; int
0x140c8a1b8  lea     r8, CmSiFreeMemory
0x140c8a1bf  mov     [rsp+4E0h+var_4A8], r14w; __int16
0x140c8a1c5  lea     rdx, CmpAllocatePoolLookaside
0x140c8a1cc  mov     dword ptr [rsp+4E0h+Disposition], 626B4D43h; int
0x140c8a1d4  lea     rcx, CmpKcbLookaside; SListHead
0x140c8a1db  mov     qword ptr [rsp+4E0h+CreateOptions], 138h; __int64
0x140c8a1e4  mov     r9d, r15d
0x140c8a1e7  mov     dword ptr [rsp+4E0h+BugCheckParameter4], r14d; int
0x140c8a1ec  call    ExInitializeLookasideListExInternal
0x140c8a1f1  call    CmpInitSIDToHiveMapping
0x140c8a1f6  call    CmpAdminSystemSecurityDescriptor
0x140c8a1fb  mov     cs:WheapPfaLock.Queue, rax
0x140c8a202  call    CmpInitializeTrustedInstallerSid
0x140c8a207  call    CmpInitializeDelayedCloseTable
0x140c8a20c  call    CmpInitCallbacks
0x140c8a211  call    CmpInitializeMachineHiveLoadedCallbacks
0x140c8a216  call    CmpInitializeFreezeThaw
0x140c8a21b  call    HvInitializeHashLibrary
0x140c8a220  call    CmpValidateGlobalFlushControlFlags
0x140c8a225  call    CmpInitializeGlobalKeyLockTracker
0x140c8a22a  call    CmpInitializeTransactions
0x140c8a22f  call    CmpVolumeManagerInitialize
0x140c8a234  mov     rsi, r14
0x140c8a237  lea     rbx, [rsi+rsi*2]
0x140c8a23b  mov     rdx, rva CmpBootLoadControl[r12+rbx*8]; SourceString
0x140c8a243  lea     rcx, [rbp+3E0h+DestinationString]; DestinationString
0x140c8a247  call    RtlInitUnicodeString
0x140c8a24c  lea     rcx, [rbp+3E0h+DestinationString]
0x140c8a250  call    CmpHashUnicodeComponent
0x140c8a255  add     rsi, r15
0x140c8a258  mov     rva dword_140E0D58C[r12+rbx*8], eax
0x140c8a260  cmp     rsi, 8
0x140c8a264  jnz     short loc_140C8A237
0x140c8a266  call    CmpCreateObjectTypes
0x140c8a26b  test    eax, eax
0x140c8a26d  jns     short loc_140C8A286
0x140c8a26f  movsxd  r9, eax; BugCheckParameter3
0x140c8a272  lea     ecx, [rsi+5Fh]; BugCheckCode
0x140c8a275  mov     r8, r15; BugCheckParameter2
0x140c8a278  mov     [rsp+4E0h+BugCheckParameter4], r14; BugCheckParameter4
0x140c8a27d  mov     rdx, r15; BugCheckParameter1
0x140c8a280  call    KeBugCheckEx
0x140c8a286  call    CmpInitializeLightWeightTransactionType
0x140c8a28b  test    eax, eax
0x140c8a28d  jns     short loc_140C8A2AA
0x140c8a28f  mov     r8d, 18h; BugCheckParameter2
0x140c8a295  movsxd  r9, eax; BugCheckParameter3
0x140c8a298  mov     rdx, r15; BugCheckParameter1
0x140c8a29b  mov     [rsp+4E0h+BugCheckParameter4], r14; BugCheckParameter4
0x140c8a2a0  lea     ecx, [r8+4Fh]; BugCheckCode
0x140c8a2a4  call    KeBugCheckEx
0x140c8a2aa  call    CmpInitializeRegistryProcess
0x140c8a2af  test    eax, eax
0x140c8a2b1  jns     short loc_140C8A2CE
0x140c8a2b3  mov     r8d, 19h; BugCheckParameter2
0x140c8a2b9  movsxd  r9, eax; BugCheckParameter3
0x140c8a2bc  mov     rdx, r15; BugCheckParameter1
0x140c8a2bf  mov     [rsp+4E0h+BugCheckParameter4], r14; BugCheckParameter4
0x140c8a2c4  lea     ecx, [r8+4Eh]; BugCheckCode
0x140c8a2c8  call    KeBugCheckEx
0x140c8a2ce  lea     rcx, [rbp+3E0h+ApcState]; ApcState
0x140c8a2d2  call    CmpAttachToRegistryProcess
0x140c8a2d7  call    CmpLockRegistryExclusive
0x140c8a2dc  xor     edx, edx
0x140c8a2de  mov     rcx, rdi
0x140c8a2e1  call    CmpInitializePreloadedHives
0x140c8a2e6  lea     rax, [rbp+3E0h+var_3D0]
0x140c8a2ea  xor     r9d, r9d
0x140c8a2ed  mov     [rsp+4E0h+var_480], rax
0x140c8a2f2  lea     rcx, CmpMasterHive
0x140c8a2f9  mov     [rsp+4E0h+var_488], r14
0x140c8a2fe  mov     r8d, r15d
0x140c8a301  mov     qword ptr [rsp+4E0h+var_490], r14
0x140c8a306  xor     edx, edx
0x140c8a308  mov     [rsp+4E0h+var_498], r14
0x140c8a30d  mov     [rsp+4E0h+var_4A0], r14
0x140c8a312  mov     dword ptr [rsp+4E0h+var_4A8], 20000h
0x140c8a31a  mov     [rsp+4E0h+Disposition], r14
0x140c8a31f  mov     qword ptr [rsp+4E0h+CreateOptions], r14
0x140c8a324  mov     [rsp+4E0h+BugCheckParameter4], r14
0x140c8a329  call    CmpCreateHive
0x140c8a32e  test    eax, eax
0x140c8a330  jns     short loc_140C8A351
0x140c8a332  mov     r8d, 2; BugCheckParameter2
0x140c8a338  movsxd  r9, eax; BugCheckParameter3
0x140c8a33b  lea     rax, [rbp+3E0h+var_3D0]
0x140c8a33f  mov     rdx, r15; BugCheckParameter1
0x140c8a342  mov     [rsp+4E0h+BugCheckParameter4], rax; BugCheckParameter4
0x140c8a347  lea     ecx, [r8+65h]; BugCheckCode
0x140c8a34b  call    KeBugCheckEx
0x140c8a351  mov     rcx, cs:CmpMasterHive
0x140c8a358  mov     edx, 80h
0x140c8a35d  call    CmpInitializeKcbCache
0x140c8a362  test    eax, eax
0x140c8a364  jns     short loc_140C8A381
0x140c8a366  mov     r8d, 3; BugCheckParameter2
0x140c8a36c  movsxd  r9, eax; BugCheckParameter3
0x140c8a36f  mov     rdx, r15; BugCheckParameter1
0x140c8a372  mov     [rsp+4E0h+BugCheckParameter4], r14; BugCheckParameter4
0x140c8a377  lea     ecx, [r8+64h]; BugCheckCode
0x140c8a37b  call    KeBugCheckEx
0x140c8a381  call    CmpCreateRegistryRoot
0x140c8a386  test    eax, eax
0x140c8a388  jns     short loc_140C8A3A3
0x140c8a38a  xor     r9d, r9d; BugCheckParameter3
0x140c8a38d  mov     [rsp+4E0h+BugCheckParameter4], r14; BugCheckParameter4
0x140c8a392  mov     rdx, r15; BugCheckParameter1
0x140c8a395  lea     r8d, [r9+4]; BugCheckParameter2
0x140c8a399  lea     ecx, [r9+67h]; BugCheckCode
0x140c8a39d  call    KeBugCheckEx
0x140c8a3a3  xor     ecx, ecx
0x140c8a3a5  call    CmpInitSiloSupport
0x140c8a3aa  test    eax, eax
0x140c8a3ac  jns     short loc_140C8A3C9
0x140c8a3ae  mov     r8d, 1Ah; BugCheckParameter2
0x140c8a3b4  movsxd  r9, eax; BugCheckParameter3
0x140c8a3b7  mov     rdx, r15; BugCheckParameter1
0x140c8a3ba  mov     [rsp+4E0h+BugCheckParameter4], r14; BugCheckParameter4
0x140c8a3bf  lea     ecx, [r8+4Dh]; BugCheckCode
0x140c8a3c3  call    KeBugCheckEx
0x140c8a3c9  call    CmpHiveRootSecurityDescriptor
0x140c8a3ce  mov     rbx, rax
0x140c8a3d1  mov     [rsp+4E0h+Disposition], r14; Disposition
0x140c8a3d6  lea     rax, PspActiveProcessLock.___u33+20h
0x140c8a3dd  mov     [rsp+4E0h+CreateOptions], r14d; CreateOptions
0x140c8a3e2  mov     [rbp+3E0h+ObjectAttributes.ObjectName], rax
0x140c8a3e6  lea     r8, [rsp+4E0h+ObjectAttributes]; ObjectAttributes
0x140c8a3eb  lea     rax, nullclass
0x140c8a3f2  mov     [rsp+4E0h+ObjectAttributes.Length], 30h ; '0'
0x140c8a3fa  xor     r9d, r9d; TitleIndex
0x140c8a3fd  mov     [rsp+4E0h+BugCheckParameter4], rax; Class
0x140c8a402  mov     edx, 2001Fh; DesiredAccess
0x140c8a407  mov     [rbp+3E0h+ObjectAttributes.RootDirectory], r14
0x140c8a40b  lea     rcx, [rsp+4E0h+KeyHandle]; KeyHandle
0x140c8a410  mov     [rbp+3E0h+ObjectAttributes.Attributes], 240h
0x140c8a417  mov     [rbp+3E0h+ObjectAttributes.SecurityDescriptor], rbx
0x140c8a41b  mov     [rbp+3E0h+ObjectAttributes.SecurityQualityOfService], r14
0x140c8a41f  call    ZwCreateKey
0x140c8a424  movsxd  rsi, eax
0x140c8a427  test    eax, eax
0x140c8a429  jns     short loc_140C8A450
0x140c8a42b  xor     edx, edx; Tag
0x140c8a42d  mov     rcx, rbx; P
0x140c8a430  call    ExFreePoolWithTag
0x140c8a435  mov     r8d, 5; BugCheckParameter2
0x140c8a43b  mov     [rsp+4E0h+BugCheckParameter4], r14; BugCheckParameter4
0x140c8a440  mov     r9, rsi; BugCheckParameter3
0x140c8a443  mov     rdx, r15; BugCheckParameter1
0x140c8a446  lea     ecx, [r8+62h]; BugCheckCode
0x140c8a44a  call    KeBugCheckEx
0x140c8a450  mov     rcx, [rsp+4E0h+KeyHandle]; Handle
0x140c8a455  call    ZwClose
0x140c8a45a  lea     rax, PspActiveProcessLock.ExtendedFeatureDisableMask
0x140c8a461  mov     [rsp+4E0h+Disposition], r14; Disposition
0x140c8a466  mov     [rbp+3E0h+ObjectAttributes.ObjectName], rax
0x140c8a46a  lea     r8, [rsp+4E0h+ObjectAttributes]; ObjectAttributes
0x140c8a46f  lea     rax, nullclass
0x140c8a476  mov     [rsp+4E0h+CreateOptions], r14d; CreateOptions
0x140c8a47b  xor     r9d, r9d; TitleIndex
0x140c8a47e  mov     [rsp+4E0h+BugCheckParameter4], rax; Class
0x140c8a483  mov     edx, 2001Fh; DesiredAccess
0x140c8a488  mov     [rsp+4E0h+ObjectAttributes.Length], 30h ; '0'
0x140c8a490  lea     rcx, [rsp+4E0h+KeyHandle]; KeyHandle
0x140c8a495  mov     [rbp+3E0h+ObjectAttributes.RootDirectory], r14
0x140c8a499  mov     [rbp+3E0h+ObjectAttributes.Attributes], 240h
0x140c8a4a0  mov     [rbp+3E0h+ObjectAttributes.SecurityDescriptor], rbx
0x140c8a4a4  mov     [rbp+3E0h+ObjectAttributes.SecurityQualityOfService], r14
0x140c8a4a8  call    ZwCreateKey
0x140c8a4ad  movsxd  rsi, eax
0x140c8a4b0  test    eax, eax
0x140c8a4b2  jns     short loc_140C8A4D9
0x140c8a4b4  xor     edx, edx; Tag
0x140c8a4b6  mov     rcx, rbx; P
0x140c8a4b9  call    ExFreePoolWithTag
0x140c8a4be  mov     r8d, 6; BugCheckParameter2
0x140c8a4c4  mov     [rsp+4E0h+BugCheckParameter4], r14; BugCheckParameter4
0x140c8a4c9  mov     r9, rsi; BugCheckParameter3
0x140c8a4cc  mov     rdx, r15; BugCheckParameter1
0x140c8a4cf  lea     ecx, [r8+61h]; BugCheckCode
0x140c8a4d3  call    KeBugCheckEx
0x140c8a4d9  mov     rcx, [rsp+4E0h+KeyHandle]; Handle
0x140c8a4de  call    ZwClose
0x140c8a4e3  mov     rdx, cs:CmKeyObjectType
0x140c8a4ea  lea     rax, PspActiveProcessLock.KernelShadowStack
0x140c8a4f1  mov     [rbp+3E0h+ObjectAttributes.ObjectName], rax
0x140c8a4f5  lea     rcx, [rsp+4E0h+ObjectAttributes]
0x140c8a4fa  lea     rax, [rsp+4E0h+KeyHandle]
0x140c8a4ff  mov     [rsp+4E0h+ObjectAttributes.Length], 30h ; '0'
0x140c8a507  mov     [rsp+4E0h+Disposition], rax
0x140c8a50c  xor     r9d, r9d
0x140c8a50f  lea     rax, [rbp+3E0h+var_220]
0x140c8a516  mov     [rbp+3E0h+ObjectAttributes.RootDirectory], r14
0x140c8a51a  mov     qword ptr [rsp+4E0h+CreateOptions], rax
0x140c8a51f  xor     r8d, r8d
0x140c8a522  mov     dword ptr [rsp+4E0h+BugCheckParameter4], 2001Fh
0x140c8a52a  mov     [rbp+3E0h+ObjectAttributes.Attributes], 240h
0x140c8a531  mov     [rbp+3E0h+ObjectAttributes.SecurityDescriptor], rbx
0x140c8a535  mov     [rbp+3E0h+ObjectAttributes.SecurityQualityOfService], r14
0x140c8a539  mov     [rbp+3E0h+var_220], 41h ; 'A'
0x140c8a543  call    ObOpenObjectByName
0x140c8a548  xor     edx, edx; Tag
0x140c8a54a  movsxd  rsi, eax
  ... truncated ...
```
