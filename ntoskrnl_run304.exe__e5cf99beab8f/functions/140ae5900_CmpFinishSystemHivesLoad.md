# CmpFinishSystemHivesLoad

- ea: `0x140ae5900`
- end: `0x140ae624e`
- name: `CmpFinishSystemHivesLoad`
- size: `2382`
- prototype: `__int64 __fastcall(PRKEVENT Event)`
- caller_count: `0`
- callee_count: `44`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x140223ba0`
- `0x140223fb0`
- `0x1402247c0`
- `0x140258260`
- `0x14029a100`
- `0x14029e8c0`
- `0x14029ebd0`
- `0x1402fc480`
- `0x1403199a0`
- `0x14031bad0`
- `0x140348900`
- `0x1403f4770`
- `0x1403f8d70`
- `0x1404025b0`
- `0x14042a7b0`
- `0x140456940`
- `0x14051bd20`
- `0x14053a530`
- `0x14053af40`
- `0x1406d9d70`
- `0x1406daa70`
- `0x1406dac30`
- `0x1406f4880`
- `0x1407abe84`
- `0x1407e2458`
- `0x1407f4a04`
- `0x1407f4dac`
- `0x1407f4f64`
- `0x1407f5074`
- `0x1407fd2a8`
- `0x1407fd99c`
- `0x14088ee7c`
- `0x14088f004`
- `0x1408ad910`
- `0x1408b0cd4`
- `0x14093dc34`
- `0x14093f0e0`
- `0x14093f5b8`
- `0x140a9b78c`
- `0x140ae5900`
- `0x140ae6254`
- `0x140bae8e0`
- `0x140bf7950`
- `0x140bf7fa0`

## string_xrefs

- `0x140ae5d79`: `\Registry\User\S-1-5-18`
- `0x140ae5d64`: `\Registry\Machine\Security\SAM`
- `0x140ae5d72`: `\Registry\User\.Default`
- `0x140ae598f`: `\REGISTRY\`
- `0x140ae5d5d`: `\Registry\Machine\SAM\SAM`

## pseudocode

```c
__int64 __fastcall CmpFinishSystemHivesLoad(PRKEVENT Event)
{
  const WCHAR *v2; // rcx
  _WORD *v3; // r8
  __int64 v4; // rdx
  __int16 v5; // r15
  __int64 v6; // rax
  unsigned __int16 v7; // r15
  struct _KWAIT_BLOCK *WaitBlockArray; // rdi
  PVOID *v9; // rbx
  char v10; // r14
  __int64 i; // rdx
  char v12; // r13
  unsigned int j; // edi
  __int64 v14; // rbx
  const WCHAR *v15; // rdx
  int v16; // r9d
  wchar_t *v17; // r8
  int v18; // eax
  wchar_t **v19; // rcx
  wchar_t *v20; // rax
  struct _LIST_ENTRY *Blink; // rcx
  wchar_t *v22; // rdx
  wchar_t *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r8
  const WCHAR *v26; // rdx
  const WCHAR *v27; // rcx
  __int64 v28; // rax
  void *v29; // rdx
  AutoBoost *v30; // rsi
  struct _KTHREAD *v31; // rbx
  signed __int64 v32; // rax
  unsigned __int64 v33; // rdx
  signed __int64 v34; // r8
  __int64 v35; // rtt
  __int64 v36; // rcx
  ULONG_PTR v37; // rcx
  unsigned int k; // edi
  unsigned __int64 v39; // rbx
  __int64 v40; // rax
  void *v41; // rdx
  AutoBoost *v42; // rsi
  struct _KTHREAD *v43; // rbx
  signed __int64 v44; // rax
  unsigned __int64 v45; // rdx
  signed __int64 v46; // r8
  __int64 v47; // rtt
  char v48; // al
  unsigned int m; // edi
  __int64 v50; // r14
  __int64 v51; // rax
  void *v52; // rdx
  AutoBoost *v53; // rbx
  volatile signed __int64 *v54; // rbx
  signed __int64 v55; // rax
  signed __int64 v56; // r8
  volatile signed __int64 v57; // rtt
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // r8
  char v62; // [rsp+60h] [rbp-A0h]
  UNICODE_STRING Destination; // [rsp+68h] [rbp-98h] BYREF
  HANDLE KeyHandle; // [rsp+78h] [rbp-88h] BYREF
  PVOID P; // [rsp+80h] [rbp-80h]
  PPRIVILEGE_SET Privileges; // [rsp+88h] [rbp-78h]
  PPRIVILEGE_SET Pool; // [rsp+90h] [rbp-70h]
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  __int128 v69; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v70; // [rsp+D8h] [rbp-28h]
  _OWORD v71[3]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v72[54]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v73[128]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v70 = 0;
  KeyHandle = 0;
  Destination.Length = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(v71, 0, sizeof(v71));
  v69 = 0;
  CmpInitializeThreadInfo(&v69);
  memset_0(v72, 0, sizeof(v72));
  BYTE1(NlsMbOemCodePageTag) = 0;
  v2 = L"\\REGISTRY\\";
  WheapPfaLock.StackLimit = KeGetCurrentThread();
  v3 = v73;
  *(_DWORD *)(&Destination.MaximumLength + 1) = 0;
  Destination.MaximumLength = 128;
  v4 = 64;
  Destination.Buffer = (wchar_t *)v73;
  v5 = 0;
  v6 = 0x7FFF;
  do
  {
    if ( !v6 )
      break;
    if ( !*v2 )
      break;
    *v3++ = *v2++;
    --v6;
    ++v5;
    --v4;
  }
  while ( v4 );
  v7 = 2 * v5;
  Destination.Length = v7;
  Privileges = (PPRIVILEGE_SET)CmpAllocatePool(64, 336, 538987843);
  WaitBlockArray = (struct _KWAIT_BLOCK *)Privileges;
  if ( !Privileges )
    KeBugCheckEx(0x74u, 2u, 4u, 0, 0xFFFFFFFFC000009AuLL);
  Pool = (PPRIVILEGE_SET)CmpAllocatePool(64, 56, 538987843);
  v9 = (PVOID *)Pool;
  if ( !Pool )
    KeBugCheckEx(0x74u, 2u, 6u, 0, 0xFFFFFFFFC000009AuLL);
  v10 = 0;
  v62 = 0;
  P = (PVOID)CmpHiveRootSecurityDescriptor();
  for ( i = 0; i != 7; ++i )
    v9[i] = (char *)&unk_140E0D018 + 184 * i;
  if ( !Event )
  {
    KeWaitForSingleObject(&stru_140E0D240, Executive, 0, 0, 0);
    KeSetEvent(&stru_140E0D240, 0, 0);
    KiStackAttachProcess((ULONG_PTR)PsInitialSystemProcess);
    CmpInitCmRM(0, WheapPfaLock.CycleTime);
    KiUnstackDetachProcess(v71, 0);
    if ( WheapPfaLock.Timer.TimerListEntry.Blink )
    {
      TmEnableCallbacks(
        (PKRESOURCEMANAGER)WheapPfaLock.Timer.TimerListEntry.Blink[3].Blink,
        CmKtmNotification,
        WheapPfaLock.Timer.TimerListEntry.Blink);
      CmRmFinalizeRecovery(WheapPfaLock.Timer.TimerListEntry.Blink);
    }
  }
  while ( 2 )
  {
    KeWaitForMultipleObjects(7u, v9, WaitAny, Executive, 0, 0, 0, WaitBlockArray);
    v12 = 0;
    for ( j = 0; j < 7; ++j )
    {
      v14 = 23LL * j;
      if ( LOBYTE(CmpMachineHiveList[v14 + 7]) )
        continue;
      if ( !BYTE1(CmpMachineHiveList[v14 + 7]) )
      {
        v12 = 1;
        continue;
      }
      v15 = CmpMachineHiveList[v14 + 1];
      Destination.Length = v7;
      RtlAppendUnicodeToString(&Destination, v15);
      RtlAppendUnicodeToString(&Destination, CmpMachineHiveList[v14 + 2]);
      CmpLockRegistryExclusive();
      if ( !CmpMachineHiveList[v14 + 3] )
      {
        v17 = CmpMachineHiveList[v14 + 6];
        if ( v17 )
        {
          LOBYTE(v16) = BYTE3(CmpMachineHiveList[v14 + 7]);
          v18 = CmpLinkHiveToMaster(
                  (int)&Destination,
                  0,
                  (int)v17,
                  v16,
                  (int)CmpMachineHiveList[v14 + 5],
                  0,
                  0,
                  (__int64)P,
                  0,
                  0,
                  1,
                  (__int64)v72);
          if ( v18 < 0 )
          {
            if ( !(unsigned __int8)CmpIsHiveLoadUnloadRundownActive(v18) )
              KeBugCheckEx(0x73u, 1u, v37, j, (ULONG_PTR)&Destination);
            LOBYTE(WheapPfaLock.StackBase) = 0;
            WheapPfaLock.StackLimit = 0;
            CmpUnlockRegistry();
            for ( k = 0; k < 7; ++k )
            {
              v39 = 184LL * k;
              if ( HIDWORD(CmpMachineHiveList[v39 / 8 + 8]) && !LOBYTE(CmpMachineHiveList[v39 / 8 + 7]) )
              {
                if ( !BYTE1(CmpMachineHiveList[v39 / 8 + 7]) )
                  KeWaitForSingleObject((char *)&unk_140E0D018 + v39, Executive, 0, 0, 0);
                v40 = KeAbPreAcquire((struct _KTHREAD *)((char *)&unk_140E0D048 + v39), 0);
                v42 = (AutoBoost *)v40;
                if ( _interlockedbittestandset64((volatile signed __int32 *)((char *)&unk_140E0D048 + v39), 0) )
                  ExfAcquirePushLockExclusiveEx((char *)&unk_140E0D048 + v39, v40, (char *)&unk_140E0D048 + v39);
                if ( v42 )
                {
                  if ( (KiAbpGlobalState & 1) != 0 )
                    AutoBoost::KiAbpPostAcquire(v42, v41);
                  else
                    *((_BYTE *)v42 + 10) = 1;
                }
                KeSetEvent((PRKEVENT)((char *)&unk_140E0D030 + v39), 0, 0);
                CmpNotifyMachineHiveLoaded(k);
                v43 = (struct _KTHREAD *)&CmpMachineHiveList[v39 / 8 + 17];
                _m_prefetchw(v43);
                v44 = *(_QWORD *)&v43->Header.Lock;
                v45 = *(_QWORD *)&v43->Header.Lock & 0xFFFFFFFFFFFFFFF0uLL;
                v46 = *(_QWORD *)&v43->Header.Lock - 16LL;
                if ( v45 <= 0x10 )
                  v46 = 0;
                if ( (v44 & 2) != 0
                  || (v47 = *(_QWORD *)&v43->Header.Lock,
                      v47 != _InterlockedCompareExchange64((volatile signed __int64 *)&v43->Header.Lock, v46, v44)) )
                {
                  ExfReleasePushLock(v43, v45, v46);
                }
                KeAbPostRelease(v43);
              }
            }
            goto LABEL_115;
          }
          CmpLockHiveListExclusive(v18);
          v19 = *(wchar_t ***)&PspActiveProcessLock.Timer.Header.Lock;
          if ( **(struct _KTHREAD ***)&PspActiveProcessLock.Timer.Header.Lock != (struct _KTHREAD *)&PspActiveProcessLock.RelativeTimerBias )
            __fastfail(3u);
          v20 = CmpMachineHiveList[v14 + 6] + 808;
          *(_QWORD *)v20 = &PspActiveProcessLock.RelativeTimerBias;
          *((_QWORD *)v20 + 1) = v19;
          *v19 = v20;
          *(_QWORD *)&PspActiveProcessLock.Timer.Header.Lock = v20;
          CmpUnlockHiveList();
          CmpRecheckHiveVolumePolicy(CmpMachineHiveList[v14 + 6]);
          if ( BYTE3(CmpMachineHiveList[v14 + 7]) )
          {
            *((_DWORD *)CmpMachineHiveList[v14 + 6] + 40) |= 0x20u;
            *((_QWORD *)CmpMachineHiveList[v14 + 6] + 523) = KeGetCurrentThread();
            CmpUnlockRegistry();
            CmpFlushHive((ULONG_PTR)CmpMachineHiveList[v14 + 6]);
            CmpLockRegistryExclusive();
            *((_DWORD *)CmpMachineHiveList[v14 + 6] + 40) &= ~0x20u;
            *((_QWORD *)CmpMachineHiveList[v14 + 6] + 523) = 0;
          }
          Blink = WheapPfaLock.Timer.TimerListEntry.Blink;
          if ( WheapPfaLock.Timer.TimerListEntry.Blink )
          {
            v22 = CmpMachineHiveList[v14 + 6];
            if ( (*((_DWORD *)v22 + 40) & 2) == 0 && !*((_QWORD *)v22 + 521) )
            {
              ++LODWORD(WheapPfaLock.Timer.TimerListEntry.Blink[4].Flink);
              *((_QWORD *)CmpMachineHiveList[v14 + 6] + 521) = Blink;
            }
          }
        }
      }
      v23 = CmpMachineHiveList[v14 + 6];
      if ( v23 )
        CmpAddToHiveFileList(v23);
      LOBYTE(CmpMachineHiveList[v14 + 7]) = 1;
      switch ( j )
      {
        case 3u:
          if ( !Event )
          {
            CmpUnlockRegistry();
            CmpMountPreloadedHives();
            CmpLockRegistryExclusive();
            CmpInterlockedFunction();
            CmpUnlockRegistry();
LABEL_43:
            v28 = KeAbPreAcquire((struct _KTHREAD *)((char *)&unk_140E0D048 + v14 * 8), 0);
            v30 = (AutoBoost *)v28;
            if ( _interlockedbittestandset64((volatile signed __int32 *)((char *)&unk_140E0D048 + v14 * 8), 0) )
              ExfAcquirePushLockExclusiveEx((char *)&unk_140E0D048 + v14 * 8, v28, (char *)&unk_140E0D048 + v14 * 8);
            if ( v30 )
            {
              if ( (KiAbpGlobalState & 1) != 0 )
                AutoBoost::KiAbpPostAcquire(v30, v29);
              else
                *((_BYTE *)v30 + 10) = 1;
            }
            KeSetEvent((PRKEVENT)((char *)&unk_140E0D030 + v14 * 8), 0, 0);
            CmpNotifyMachineHiveLoaded(j);
            v31 = (struct _KTHREAD *)&CmpMachineHiveList[v14 + 17];
            _m_prefetchw(v31);
            v32 = *(_QWORD *)&v31->Header.Lock;
            v33 = *(_QWORD *)&v31->Header.Lock & 0xFFFFFFFFFFFFFFF0uLL;
            v34 = *(_QWORD *)&v31->Header.Lock - 16LL;
            if ( v33 <= 0x10 )
              v34 = 0;
            if ( (v32 & 2) != 0
              || (v35 = *(_QWORD *)&v31->Header.Lock,
                  v35 != _InterlockedCompareExchange64((volatile signed __int64 *)&v31->Header.Lock, v34, v32)) )
            {
              ExfReleasePushLock(v31, v33, v34);
            }
            KeAbPostRelease(v31);
            v10 = v62;
            goto LABEL_55;
          }
          break;
        case 2u:
          CmpUnlockRegistry();
          CmpCreatePerfKeys();
          goto LABEL_42;
        case 1u:
          v26 = L"\\Registry\\Machine\\SAM\\SAM";
          v27 = L"\\Registry\\Machine\\Security\\SAM";
LABEL_40:
          CmpLinkKeyToHive(v27, v26);
          break;
        case 4u:
          v26 = L"\\Registry\\User\\.Default";
          v27 = L"\\Registry\\User\\S-1-5-18";
          goto LABEL_40;
      }
      CmpUnlockRegistry();
LABEL_42:
      if ( !Event )
        goto LABEL_43;
LABEL_55:
      if ( j - 2 <= 1 && !Event )
      {
        v36 = (unsigned __int8)byte_140E0D220;
        if ( j == 3 )
          v36 = (unsigned __int8)byte_140E0D168;
        if ( (_BYTE)v36 )
        {
          if ( CmFastBoot )
            ExpRefreshSystemTime();
          if ( !v10 )
          {
            CmpLoadSystemVersionData();
            CmpSetVersionData();
            v10 = 1;
            v62 = 1;
          }
          if ( CmFastBoot )
            PsBootPhaseComplete(v36, v24, v25);
        }
      }
    }
    if ( v12 )
    {
      v9 = (PVOID *)Pool;
      WaitBlockArray = (struct _KWAIT_BLOCK *)Privileges;
      continue;
    }
    break;
  }
  CmpLockRegistryExclusive();
  CmpSpecialBootCondition = 0;
  if ( BYTE5(NlsMbOemCodePageTag) || (v48 = 1, CmVEEnabled != 1) )
    v48 = 0;
  CmpVEEnabled = v48;
  CmpUnlockRegistry();
  if ( Event )
  {
    KiStackAttachProcess((ULONG_PTR)PsInitialSystemProcess);
    CmpInitCmRM(0, WheapPfaLock.CycleTime);
    KiUnstackDetachProcess(v71, 0);
    if ( WheapPfaLock.Timer.TimerListEntry.Blink )
    {
      TmEnableCallbacks(
        (PKRESOURCEMANAGER)WheapPfaLock.Timer.TimerListEntry.Blink[3].Blink,
        CmKtmNotification,
        WheapPfaLock.Timer.TimerListEntry.Blink);
      CmRmFinalizeRecovery(WheapPfaLock.Timer.TimerListEntry.Blink);
    }
    CmpMountPreloadedHives();
    CmpLockRegistryExclusive();
    CmpInterlockedFunction();
    CmpUnlockRegistry();
    for ( m = 0; m < 7; ++m )
    {
      v50 = 184LL * m;
      v51 = KeAbPreAcquire((struct _KTHREAD *)((char *)&unk_140E0D048 + v50), 0);
      v53 = (AutoBoost *)v51;
      if ( _interlockedbittestandset64((volatile signed __int32 *)((char *)&unk_140E0D048 + v50), 0) )
        ExfAcquirePushLockExclusiveEx((char *)&unk_140E0D048 + v50, v51, (char *)&unk_140E0D048 + v50);
      if ( v53 )
      {
        if ( (KiAbpGlobalState & 1) != 0 )
          AutoBoost::KiAbpPostAcquire(v53, v52);
        else
          *((_BYTE *)v53 + 10) = 1;
      }
      KeSetEvent((PRKEVENT)((char *)&unk_140E0D030 + v50), 0, 0);
      CmpNotifyMachineHiveLoaded(m);
      v54 = (volatile signed __int64 *)((char *)&unk_140E0D048 + v50);
      _m_prefetchw((char *)&unk_140E0D048 + v50);
      v55 = *(_QWORD *)((char *)&unk_140E0D048 + v50);
      v56 = v55 - 16;
      if ( (v55 & 0xFFFFFFFFFFFFFFF0uLL) <= 0x10 )
        v56 = 0;
      if ( (v55 & 2) != 0 || (v57 = *v54, v57 != _InterlockedCompareExchange64(v54, v56, v55)) )
        ExfReleasePushLock((char *)&unk_140E0D048 + v50, v55 & 0xFFFFFFFFFFFFFFF0uLL, v56);
      KeAbPostRelease((struct _KTHREAD *)((char *)&unk_140E0D048 + v50));
    }
    if ( CmFastBoot )
    {
      ExpRefreshSystemTime();
      PsBootPhaseComplete(v59, v58, v60);
    }
    CmpLoadSystemVersionData();
    CmpSetVersionData();
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&CmpConfigurationManagerKeyName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwCreateKey(&KeyHandle, 2u, &ObjectAttributes, 0, 0, 0, 0) >= 0 )
    ZwClose(KeyHandle);
LABEL_115:
  CmpSpecialBootCondition = 0;
  LOBYTE(WheapPfaLock.StackBase) = 0;
  WheapPfaLock.StackLimit = 0;
  if ( Event )
    KeSetEvent(Event, 0, 0);
  if ( P )
    ExFreePoolWithTag(P, 0);
  CmSiFreeMemory(Privileges);
  CmSiFreeMemory(Pool);
  return CmCleanupThreadInfo(&v69);
}

```

## disassembly

```asm
0x140ae5900  push    rbp
0x140ae5902  push    rbx
0x140ae5903  push    rsi
0x140ae5904  push    rdi
0x140ae5905  push    r12
0x140ae5907  push    r13
0x140ae5909  push    r14
0x140ae590b  push    r15
0x140ae590d  lea     rbp, [rsp-258h]
0x140ae5915  sub     rsp, 358h
0x140ae591c  mov     rax, cs:__security_cookie
0x140ae5923  xor     rax, rsp
0x140ae5926  mov     [rbp+290h+var_50], rax
0x140ae592d  xorps   xmm0, xmm0
0x140ae5930  xor     eax, eax
0x140ae5932  movups  xmmword ptr [rbp+290h+ObjectAttributes.ObjectName], xmm0
0x140ae5936  mov     r12, rcx
0x140ae5939  mov     [rbp+290h+var_2B8], rax
0x140ae593d  xor     esi, esi
0x140ae593f  lea     rcx, [rbp+290h+var_2C8]
0x140ae5943  movups  xmmword ptr [rbp+290h+ObjectAttributes+1Ch], xmm0
0x140ae5947  mov     [rsp+390h+KeyHandle], rsi
0x140ae594c  movups  xmmword ptr [rsp+390h+Destination.Length], xmm0
0x140ae5951  movups  xmmword ptr [rbp+290h+ObjectAttributes.Length], xmm0
0x140ae5955  movups  [rbp+290h+var_2B0], xmm0
0x140ae5959  movups  [rbp+290h+var_2A0], xmm0
0x140ae595d  movups  [rbp+290h+var_290], xmm0
0x140ae5961  movups  [rbp+290h+var_2C8], xmm0
0x140ae5965  call    CmpInitializeThreadInfo
0x140ae596a  xor     edx, edx; Val
0x140ae596c  lea     rcx, [rbp+290h+var_280]; void *
0x140ae5970  mov     r8d, 1B0h; Size
0x140ae5976  call    memset_0
0x140ae597b  mov     byte ptr cs:NlsMbOemCodePageTag+1, sil
0x140ae5982  lea     r14d, [rsi+40h]
0x140ae5986  mov     rax, gs:188h
0x140ae598f  lea     rcx, aRegistry_1; "\\REGISTRY\\"
0x140ae5996  mov     cs:WheapPfaLock.StackLimit, rax
0x140ae599d  lea     r8, [rbp+290h+var_D0]
0x140ae59a4  mov     eax, 80h
0x140ae59a9  mov     dword ptr [rsp+390h+Destination+4], esi
0x140ae59ad  mov     [rsp+390h+Destination.MaximumLength], ax
0x140ae59b2  lea     r13d, [rsi+2]
0x140ae59b6  lea     rax, [rbp+290h+var_D0]
0x140ae59bd  mov     edx, r14d
0x140ae59c0  mov     [rsp+390h+Destination.Buffer], rax
0x140ae59c5  mov     r15d, esi
0x140ae59c8  mov     eax, 7FFFh
0x140ae59cd  test    rax, rax
0x140ae59d0  jz      short loc_140AE59F2
0x140ae59d2  movzx   r9d, word ptr [rcx]
0x140ae59d6  test    r9w, r9w
0x140ae59da  jz      short loc_140AE59F2
0x140ae59dc  mov     [r8], r9w
0x140ae59e0  add     rcx, r13
0x140ae59e3  add     r8, r13
0x140ae59e6  dec     rax
0x140ae59e9  inc     r15
0x140ae59ec  sub     rdx, 1
0x140ae59f0  jnz     short loc_140AE59CD
0x140ae59f2  mov     ebx, 20204D43h
0x140ae59f7  add     r15w, r15w
0x140ae59fb  mov     r8d, ebx
0x140ae59fe  mov     [rsp+390h+Destination.Length], r15w
0x140ae5a04  mov     edx, 150h
0x140ae5a09  mov     rcx, r14
0x140ae5a0c  call    CmpAllocatePool
0x140ae5a11  mov     [rbp+290h+Privileges], rax
0x140ae5a15  mov     rdi, rax
0x140ae5a18  test    rax, rax
0x140ae5a1b  jnz     short loc_140AE5A39
0x140ae5a1d  xor     r9d, r9d; BugCheckParameter3
0x140ae5a20  mov     [rsp+390h+BugCheckParameter4], 0FFFFFFFFC000009Ah; BugCheckParameter4
0x140ae5a29  lea     r8d, [rax+4]; BugCheckParameter2
0x140ae5a2d  mov     rdx, r13; BugCheckParameter1
0x140ae5a30  lea     ecx, [rax+74h]; BugCheckCode
0x140ae5a33  call    KeBugCheckEx
0x140ae5a39  mov     r8d, ebx
0x140ae5a3c  mov     edx, 38h ; '8'
0x140ae5a41  mov     rcx, r14
0x140ae5a44  call    CmpAllocatePool
0x140ae5a49  mov     [rbp+290h+var_300], rax
0x140ae5a4d  mov     rbx, rax
0x140ae5a50  test    rax, rax
0x140ae5a53  jnz     short loc_140AE5A71
0x140ae5a55  xor     r9d, r9d; BugCheckParameter3
0x140ae5a58  mov     [rsp+390h+BugCheckParameter4], 0FFFFFFFFC000009Ah; BugCheckParameter4
0x140ae5a61  lea     r8d, [rax+6]; BugCheckParameter2
0x140ae5a65  mov     rdx, r13; BugCheckParameter1
0x140ae5a68  lea     ecx, [rax+74h]; BugCheckCode
0x140ae5a6b  call    KeBugCheckEx
0x140ae5a71  mov     r14b, sil
0x140ae5a74  mov     [rsp+390h+var_330], sil
0x140ae5a79  call    CmpHiveRootSecurityDescriptor
0x140ae5a7e  mov     [rbp+290h+P], rax
0x140ae5a82  mov     rdx, rsi
0x140ae5a85  imul    rcx, rdx, 0B8h
0x140ae5a8c  lea     rax, unk_140E0D018
0x140ae5a93  add     rcx, rax
0x140ae5a96  mov     [rbx+rdx*8], rcx
0x140ae5a9a  inc     rdx
0x140ae5a9d  cmp     rdx, 7
0x140ae5aa1  jnz     short loc_140AE5A85
0x140ae5aa3  test    r12, r12
0x140ae5aa6  jnz     short loc_140AE5B27
0x140ae5aa8  xor     r9d, r9d; Alertable
0x140ae5aab  mov     [rsp+390h+BugCheckParameter4], rsi; Timeout
0x140ae5ab0  xor     r8d, r8d; WaitMode
0x140ae5ab3  lea     rcx, stru_140E0D240; Object
0x140ae5aba  xor     edx, edx; WaitReason
0x140ae5abc  call    KeWaitForSingleObject
0x140ae5ac1  xor     r8d, r8d; Wait
0x140ae5ac4  lea     rcx, stru_140E0D240; Event
0x140ae5acb  xor     edx, edx; Increment
0x140ae5acd  call    KeSetEvent
0x140ae5ad2  mov     rcx, cs:PsInitialSystemProcess; BugCheckParameter1
0x140ae5ad9  lea     r8, [rbp+290h+var_2B0]
0x140ae5add  xor     edx, edx
0x140ae5adf  call    KiStackAttachProcess
0x140ae5ae4  mov     dl, byte ptr cs:WheapPfaLock.CycleTime
0x140ae5aea  xor     ecx, ecx
0x140ae5aec  call    CmpInitCmRM
0x140ae5af1  xor     edx, edx
0x140ae5af3  lea     rcx, [rbp+290h+var_2B0]
0x140ae5af7  call    KiUnstackDetachProcess
0x140ae5afc  mov     rcx, cs:WheapPfaLock.Timer.TimerListEntry.Blink
0x140ae5b03  test    rcx, rcx
0x140ae5b06  jz      short loc_140AE5B27
0x140ae5b08  mov     r8, rcx; RMKey
0x140ae5b0b  lea     rdx, CmKtmNotification; CallbackRoutine
0x140ae5b12  mov     rcx, [rcx+38h]; ResourceManager
0x140ae5b16  call    TmEnableCallbacks
0x140ae5b1b  mov     rcx, cs:WheapPfaLock.Timer.TimerListEntry.Blink
0x140ae5b22  call    CmRmFinalizeRecovery
0x140ae5b27  xor     r9d, r9d; WaitReason
0x140ae5b2a  mov     [rsp+390h+WaitBlockArray], rdi; WaitBlockArray
0x140ae5b2f  mov     [rsp+390h+Timeout], rsi; Timeout
0x140ae5b34  mov     rdx, rbx; Object
0x140ae5b37  mov     [rsp+390h+Alertable], sil; Alertable
0x140ae5b3c  mov     byte ptr [rsp+390h+BugCheckParameter4], sil; WaitMode
0x140ae5b41  lea     r8d, [r9+1]; WaitType
0x140ae5b45  lea     ecx, [r9+7]; Count
0x140ae5b49  call    KeWaitForMultipleObjects
0x140ae5b4e  mov     r13b, sil
0x140ae5b51  mov     edi, esi
0x140ae5b53  cmp     edi, 7
0x140ae5b56  jnb     loc_140AE5EA3
0x140ae5b5c  mov     esi, edi
0x140ae5b5e  lea     rax, CmpMachineHiveList
0x140ae5b65  imul    rbx, rsi, 0B8h
0x140ae5b6c  cmp     byte ptr [rbx+rax+38h], 0
0x140ae5b71  jnz     loc_140AE5E9C
0x140ae5b77  cmp     byte ptr [rbx+rax+39h], 0
0x140ae5b7c  jnz     short loc_140AE5B86
0x140ae5b7e  mov     r13b, 1
0x140ae5b81  jmp     loc_140AE5E9C
0x140ae5b86  mov     rdx, [rbx+rax+8]; Source
0x140ae5b8b  lea     rcx, [rsp+390h+Destination]; Destination
0x140ae5b90  mov     [rsp+390h+Destination.Length], r15w
0x140ae5b96  call    RtlAppendUnicodeToString
0x140ae5b9b  lea     rdx, CmpMachineHiveList
0x140ae5ba2  mov     rdx, [rbx+rdx+10h]; Source
0x140ae5ba7  lea     rcx, [rsp+390h+Destination]; Destination
0x140ae5bac  call    RtlAppendUnicodeToString
0x140ae5bb1  call    CmpLockRegistryExclusive
0x140ae5bb6  xor     ecx, ecx
0x140ae5bb8  lea     rdx, CmpMachineHiveList
0x140ae5bbf  cmp     [rbx+rdx+18h], rcx
0x140ae5bc4  jnz     loc_140AE5D07
0x140ae5bca  mov     r8, [rbx+rdx+30h]; int
0x140ae5bcf  test    r8, r8
0x140ae5bd2  jz      loc_140AE5D07
0x140ae5bd8  mov     r9b, [rbx+rdx+3Bh]; int
0x140ae5bdd  lea     rax, [rbp+290h+var_280]
0x140ae5be1  mov     [rsp+390h+var_338], rax; __int64
0x140ae5be6  mov     rax, [rbp+290h+P]
0x140ae5bea  mov     [rsp+390h+var_340], 1; char
0x140ae5bef  mov     [rsp+390h+var_348], rcx; __int64
0x140ae5bf4  mov     [rsp+390h+var_350], rcx; __int64
0x140ae5bf9  mov     [rsp+390h+WaitBlockArray], rax; __int64
0x140ae5bfe  mov     eax, [rbx+rdx+28h]
0x140ae5c02  xor     edx, edx; int
0x140ae5c04  mov     [rsp+390h+Timeout], rcx; Event
0x140ae5c09  mov     [rsp+390h+Alertable], cl; char
0x140ae5c0d  lea     rcx, [rsp+390h+Destination]; int
0x140ae5c12  mov     dword ptr [rsp+390h+BugCheckParameter4], eax; int
0x140ae5c16  call    CmpLinkHiveToMaster
0x140ae5c1b  movsxd  rcx, eax
0x140ae5c1e  test    eax, eax
0x140ae5c20  js      loc_140AE5EC2
0x140ae5c26  call    CmpLockHiveListExclusive
0x140ae5c2b  mov     rcx, qword ptr cs:PspActiveProcessLock.Timer.Header
0x140ae5c32  lea     rdx, PspActiveProcessLock.RelativeTimerBias
0x140ae5c39  cmp     [rcx], rdx
0x140ae5c3c  jnz     loc_140AE5EBB
0x140ae5c42  lea     rsi, CmpMachineHiveList
0x140ae5c49  mov     rax, [rbx+rsi+30h]
0x140ae5c4e  add     rax, 650h
0x140ae5c54  mov     [rax], rdx
0x140ae5c57  mov     [rax+8], rcx
0x140ae5c5b  mov     [rcx], rax
0x140ae5c5e  mov     qword ptr cs:PspActiveProcessLock.Timer.Header, rax
0x140ae5c65  call    CmpUnlockHiveList
0x140ae5c6a  mov     rcx, [rbx+rsi+30h]
0x140ae5c6f  call    CmpRecheckHiveVolumePolicy
0x140ae5c74  cmp     byte ptr [rbx+rsi+3Bh], 0
0x140ae5c79  jz      short loc_140AE5CD1
0x140ae5c7b  mov     rax, [rbx+rsi+30h]
0x140ae5c80  or      dword ptr [rax+0A0h], 20h
0x140ae5c87  mov     rcx, gs:188h
0x140ae5c90  mov     rax, [rbx+rsi+30h]
0x140ae5c95  mov     [rax+1058h], rcx
0x140ae5c9c  call    CmpUnlockRegistry
0x140ae5ca1  mov     rcx, [rbx+rsi+30h]; BugCheckParameter2
0x140ae5ca6  mov     edx, 4
0x140ae5cab  call    CmpFlushHive
0x140ae5cb0  call    CmpLockRegistryExclusive
0x140ae5cb5  mov     rax, [rbx+rsi+30h]
0x140ae5cba  and     dword ptr [rax+0A0h], 0FFFFFFDFh
0x140ae5cc1  mov     rax, [rbx+rsi+30h]
0x140ae5cc6  mov     qword ptr [rax+1058h], 0
0x140ae5cd1  mov     rcx, cs:WheapPfaLock.Timer.TimerListEntry.Blink
0x140ae5cd8  test    rcx, rcx
0x140ae5cdb  jz      short loc_140AE5D0E
0x140ae5cdd  mov     rdx, [rbx+rsi+30h]
0x140ae5ce2  mov     eax, [rdx+0A0h]
0x140ae5ce8  test    al, 2
0x140ae5cea  jnz     short loc_140AE5D0E
0x140ae5cec  cmp     qword ptr [rdx+1048h], 0
0x140ae5cf4  jnz     short loc_140AE5D0E
0x140ae5cf6  inc     dword ptr [rcx+40h]
0x140ae5cf9  mov     rax, [rbx+rsi+30h]
0x140ae5cfe  mov     [rax+1048h], rcx
0x140ae5d05  jmp     short loc_140AE5D0E
0x140ae5d07  lea     rsi, CmpMachineHiveList
0x140ae5d0e  mov     rcx, [rbx+rsi+30h]
0x140ae5d13  test    rcx, rcx
0x140ae5d16  jz      short loc_140AE5D1D
0x140ae5d18  call    CmpAddToHiveFileList
0x140ae5d1d  mov     byte ptr [rbx+rsi+38h], 1
0x140ae5d22  cmp     edi, 3
0x140ae5d25  jnz     short loc_140AE5D47
0x140ae5d27  test    r12, r12
0x140ae5d2a  jnz     short loc_140AE5D85
0x140ae5d2c  call    CmpUnlockRegistry
0x140ae5d31  call    CmpMountPreloadedHives
0x140ae5d36  call    CmpLockRegistryExclusive
0x140ae5d3b  call    CmpInterlockedFunction
0x140ae5d40  call    CmpUnlockRegistry
0x140ae5d45  jmp     short loc_140AE5D93
0x140ae5d47  cmp     edi, 2
0x140ae5d4a  jnz     short loc_140AE5D58
0x140ae5d4c  call    CmpUnlockRegistry
0x140ae5d51  call    CmpCreatePerfKeys
0x140ae5d56  jmp     short loc_140AE5D8A
0x140ae5d58  cmp     edi, 1
0x140ae5d5b  jnz     short loc_140AE5D6D
0x140ae5d5d  lea     rdx, aRegistryMachin_3; "\\Registry\\Machine\\SAM\\SAM"
0x140ae5d64  lea     rcx, aRegistryMachin_189; "\\Registry\\Machine\\Security\\SAM"
0x140ae5d6b  jmp     short loc_140AE5D80
0x140ae5d6d  cmp     edi, 4
0x140ae5d70  jnz     short loc_140AE5D85
0x140ae5d72  lea     rdx, aRegistryUserDe; "\\Registry\\User\\.Default"
0x140ae5d79  lea     rcx, aRegistryUserS1; "\\Registry\\User\\S-1-5-18"
0x140ae5d80  call    CmpLinkKeyToHive
0x140ae5d85  call    CmpUnlockRegistry
0x140ae5d8a  test    r12, r12
0x140ae5d8d  jnz     loc_140AE5E44
0x140ae5d93  lea     r14, [rsi+88h]
0x140ae5d9a  xor     r8d, r8d
0x140ae5d9d  add     r14, rbx
0x140ae5da0  xor     edx, edx
0x140ae5da2  mov     rcx, r14
0x140ae5da5  call    KeAbPreAcquire
0x140ae5daa  lock bts qword ptr [r14], 0
0x140ae5db0  mov     rsi, rax
0x140ae5db3  jnb     short loc_140AE5DC3
0x140ae5db5  mov     r8, r14
0x140ae5db8  mov     rdx, rax
0x140ae5dbb  mov     rcx, r14
0x140ae5dbe  call    ExfAcquirePushLockExclusiveEx
0x140ae5dc3  test    rsi, rsi
0x140ae5dc6  jz      short loc_140AE5DE0
0x140ae5dc8  mov     eax, cs:?KiAbpGlobalState@@3UKI_AB_GLOBAL_STATE@@A; KI_AB_GLOBAL_STATE KiAbpGlobalState
0x140ae5dce  test    al, 1
0x140ae5dd0  jz      short loc_140AE5DDC
0x140ae5dd2  mov     rcx, rsi; this
0x140ae5dd5  call    ?KiAbpPostAcquire@AutoBoost@@YAXPEAX@Z; AutoBoost::KiAbpPostAcquire(void *)
0x140ae5dda  jmp     short loc_140AE5DE0
0x140ae5ddc  mov     byte ptr [rsi+0Ah], 1
0x140ae5de0  lea     rsi, CmpMachineHiveList
0x140ae5de7  xor     r8d, r8d; Wait
0x140ae5dea  lea     rcx, [rsi+70h]
0x140ae5dee  xor     edx, edx; Increment
0x140ae5df0  add     rcx, rbx; Event
0x140ae5df3  call    KeSetEvent
0x140ae5df8  mov     ecx, edi
0x140ae5dfa  call    CmpNotifyMachineHiveLoaded
0x140ae5dff  add     rbx, 88h
0x140ae5e06  add     rbx, rsi
  ... truncated ...
```
