# CmpFinishSystemHivesLoad

- ea: `0x140aeb590`
- end: `0x140aebede`
- name: `CmpFinishSystemHivesLoad`
- size: `2382`
- prototype: `__int64 __fastcall(PRKEVENT Event)`
- caller_count: `0`
- callee_count: `44`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x140213760`
- `0x140213b40`
- `0x140214360`
- `0x140250630`
- `0x14029d990`
- `0x1402acde0`
- `0x1402ad0f0`
- `0x14033a550`
- `0x140366800`
- `0x140368930`
- `0x140388690`
- `0x1403d12b4`
- `0x14040a7b0`
- `0x140416ff0`
- `0x14043e7e0`
- `0x140468330`
- `0x140521f20`
- `0x140541bf0`
- `0x140542600`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406dd780`
- `0x1406f7380`
- `0x1407af3d4`
- `0x1407e5118`
- `0x1407f7844`
- `0x1407f7bec`
- `0x1407f7da4`
- `0x1407f7eb4`
- `0x140800050`
- `0x140800744`
- `0x1408897ac`
- `0x140889934`
- `0x140898034`
- `0x1408994e0`
- `0x1408999b8`
- `0x1408e282c`
- `0x1408e5be4`
- `0x140aa178c`
- `0x140aeb590`
- `0x140aebee4`
- `0x140bb19f0`
- `0x140bfa950`
- `0x140bfafa0`

## string_xrefs

- `0x140aeba02`: `\Registry\User\.Default`
- `0x140aeb9f4`: `\Registry\Machine\Security\SAM`
- `0x140aeba09`: `\Registry\User\S-1-5-18`
- `0x140aeb9ed`: `\Registry\Machine\SAM\SAM`
- `0x140aeb61f`: `\REGISTRY\`

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
  PVOID v21; // rcx
  wchar_t *v22; // rdx
  wchar_t *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r8
  const WCHAR *v26; // rdx
  const WCHAR *v27; // rcx
  __int64 v28; // rax
  void *v29; // rdx
  AutoBoost *v30; // rsi
  wchar_t **v31; // rbx
  signed __int64 v32; // rax
  unsigned __int64 v33; // rdx
  signed __int64 v34; // r8
  wchar_t *v35; // rtt
  __int64 v36; // rcx
  ULONG_PTR v37; // rcx
  unsigned int k; // edi
  __int64 v39; // rbx
  __int64 v40; // rax
  void *v41; // rdx
  AutoBoost *v42; // rsi
  wchar_t **v43; // rbx
  signed __int64 v44; // rax
  unsigned __int64 v45; // rdx
  signed __int64 v46; // r8
  wchar_t *v47; // rtt
  char v48; // al
  unsigned int m; // edi
  __int64 v50; // r14
  __int64 v51; // rax
  void *v52; // rdx
  AutoBoost *v53; // rbx
  __int64 *v54; // rbx
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
  CmpMountThread = (__int64)KeGetCurrentThread();
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
    v9[i] = &qword_140E0D018[23 * i];
  if ( !Event )
  {
    KeWaitForSingleObject(&stru_140E0D240, Executive, 0, 0, 0);
    KeSetEvent(&stru_140E0D240, 0, 0);
    KiStackAttachProcess((ULONG_PTR)PsInitialSystemProcess);
    CmpInitCmRM(0, CmpInitRmLogOnLoad);
    KiUnstackDetachProcess(v71, 0);
    if ( CmRmSystem )
    {
      TmEnableCallbacks(*((PKRESOURCEMANAGER *)CmRmSystem + 7), CmKtmNotification, CmRmSystem);
      CmRmFinalizeRecovery(CmRmSystem);
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
            CmpLoadingSystemHivesActive = 0;
            CmpMountThread = 0;
            CmpUnlockRegistry();
            for ( k = 0; k < 7; ++k )
            {
              v39 = 23LL * k;
              if ( HIDWORD(CmpMachineHiveList[v39 + 8]) && !LOBYTE(CmpMachineHiveList[v39 + 7]) )
              {
                if ( !BYTE1(CmpMachineHiveList[v39 + 7]) )
                  KeWaitForSingleObject(&qword_140E0D018[v39], Executive, 0, 0, 0);
                v40 = KeAbPreAcquire((struct _KTHREAD *)&qword_140E0D030[v39 + 3], 0);
                v42 = (AutoBoost *)v40;
                if ( _interlockedbittestandset64((volatile signed __int32 *)&qword_140E0D030[v39 + 3], 0) )
                  ExfAcquirePushLockExclusiveEx(&qword_140E0D030[v39 + 3], v40, &qword_140E0D030[v39 + 3]);
                if ( v42 )
                {
                  if ( (KiAbpGlobalState & 1) != 0 )
                    AutoBoost::KiAbpPostAcquire(v42, v41);
                  else
                    *((_BYTE *)v42 + 10) = 1;
                }
                KeSetEvent((PRKEVENT)&qword_140E0D030[v39], 0, 0);
                CmpNotifyMachineHiveLoaded(k);
                v43 = &CmpMachineHiveList[v39 + 17];
                _m_prefetchw(v43);
                v44 = (signed __int64)*v43;
                v45 = (unsigned __int64)*v43 & 0xFFFFFFFFFFFFFFF0uLL;
                v46 = (signed __int64)(*v43 - 8);
                if ( v45 <= 0x10 )
                  v46 = 0;
                if ( (v44 & 2) != 0
                  || (v47 = *v43,
                      v47 != (wchar_t *)_InterlockedCompareExchange64((volatile signed __int64 *)v43, v46, v44)) )
                {
                  ExfReleasePushLock(v43, v45, v46);
                }
                KeAbPostRelease((ULONG_PTR)v43);
              }
            }
            goto LABEL_115;
          }
          CmpLockHiveListExclusive(v18);
          v19 = (wchar_t **)qword_140FDBB50;
          if ( *(__int64 **)qword_140FDBB50 != &CmpHiveListHead )
            __fastfail(3u);
          v20 = CmpMachineHiveList[v14 + 6] + 808;
          *(_QWORD *)v20 = &CmpHiveListHead;
          *((_QWORD *)v20 + 1) = v19;
          *v19 = v20;
          qword_140FDBB50 = (__int64)v20;
          CmpUnlockHiveList();
          CmpRecheckHiveVolumePolicy(CmpMachineHiveList[v14 + 6]);
          if ( BYTE3(CmpMachineHiveList[v14 + 7]) )
          {
            *((_DWORD *)CmpMachineHiveList[v14 + 6] + 40) |= 0x20u;
            *((_QWORD *)CmpMachineHiveList[v14 + 6] + 523) = KeGetCurrentThread();
            CmpUnlockRegistry();
            CmpFlushHive(CmpMachineHiveList[v14 + 6], 4);
            CmpLockRegistryExclusive();
            *((_DWORD *)CmpMachineHiveList[v14 + 6] + 40) &= ~0x20u;
            *((_QWORD *)CmpMachineHiveList[v14 + 6] + 523) = 0;
          }
          v21 = CmRmSystem;
          if ( CmRmSystem )
          {
            v22 = CmpMachineHiveList[v14 + 6];
            if ( (*((_DWORD *)v22 + 40) & 2) == 0 && !*((_QWORD *)v22 + 521) )
            {
              ++*((_DWORD *)CmRmSystem + 16);
              *((_QWORD *)CmpMachineHiveList[v14 + 6] + 521) = v21;
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
            v28 = KeAbPreAcquire((struct _KTHREAD *)&qword_140E0D030[v14 + 3], 0);
            v30 = (AutoBoost *)v28;
            if ( _interlockedbittestandset64((volatile signed __int32 *)&qword_140E0D030[v14 + 3], 0) )
              ExfAcquirePushLockExclusiveEx(&qword_140E0D030[v14 + 3], v28, &qword_140E0D030[v14 + 3]);
            if ( v30 )
            {
              if ( (KiAbpGlobalState & 1) != 0 )
                AutoBoost::KiAbpPostAcquire(v30, v29);
              else
                *((_BYTE *)v30 + 10) = 1;
            }
            KeSetEvent((PRKEVENT)&qword_140E0D030[v14], 0, 0);
            CmpNotifyMachineHiveLoaded(j);
            v31 = &CmpMachineHiveList[v14 + 17];
            _m_prefetchw(v31);
            v32 = (signed __int64)*v31;
            v33 = (unsigned __int64)*v31 & 0xFFFFFFFFFFFFFFF0uLL;
            v34 = (signed __int64)(*v31 - 8);
            if ( v33 <= 0x10 )
              v34 = 0;
            if ( (v32 & 2) != 0
              || (v35 = *v31, v35 != (wchar_t *)_InterlockedCompareExchange64((volatile signed __int64 *)v31, v34, v32)) )
            {
              ExfReleasePushLock(v31, v33, v34);
            }
            KeAbPostRelease((ULONG_PTR)v31);
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
  if ( BYTE4(NlsMbOemCodePageTag) || (v48 = 1, CmVEEnabled != 1) )
    v48 = 0;
  CmpVEEnabled = v48;
  CmpUnlockRegistry();
  if ( Event )
  {
    KiStackAttachProcess((ULONG_PTR)PsInitialSystemProcess);
    CmpInitCmRM(0, CmpInitRmLogOnLoad);
    KiUnstackDetachProcess(v71, 0);
    if ( CmRmSystem )
    {
      TmEnableCallbacks(*((PKRESOURCEMANAGER *)CmRmSystem + 7), CmKtmNotification, CmRmSystem);
      CmRmFinalizeRecovery(CmRmSystem);
    }
    CmpMountPreloadedHives();
    CmpLockRegistryExclusive();
    CmpInterlockedFunction();
    CmpUnlockRegistry();
    for ( m = 0; m < 7; ++m )
    {
      v50 = 23LL * m;
      v51 = KeAbPreAcquire((struct _KTHREAD *)&qword_140E0D030[v50 + 3], 0);
      v53 = (AutoBoost *)v51;
      if ( _interlockedbittestandset64((volatile signed __int32 *)&qword_140E0D030[v50 + 3], 0) )
        ExfAcquirePushLockExclusiveEx(&qword_140E0D030[v50 + 3], v51, &qword_140E0D030[v50 + 3]);
      if ( v53 )
      {
        if ( (KiAbpGlobalState & 1) != 0 )
          AutoBoost::KiAbpPostAcquire(v53, v52);
        else
          *((_BYTE *)v53 + 10) = 1;
      }
      KeSetEvent((PRKEVENT)&qword_140E0D030[v50], 0, 0);
      CmpNotifyMachineHiveLoaded(m);
      v54 = &qword_140E0D030[v50 + 3];
      _m_prefetchw(&qword_140E0D030[v50 + 3]);
      v55 = qword_140E0D030[v50 + 3];
      v56 = v55 - 16;
      if ( (v55 & 0xFFFFFFFFFFFFFFF0uLL) <= 0x10 )
        v56 = 0;
      if ( (v55 & 2) != 0 || (v57 = *v54, v57 != _InterlockedCompareExchange64(v54, v56, v55)) )
        ExfReleasePushLock(&qword_140E0D030[v50 + 3], v55 & 0xFFFFFFFFFFFFFFF0uLL, v56);
      KeAbPostRelease((ULONG_PTR)&qword_140E0D030[v50 + 3]);
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
  CmpLoadingSystemHivesActive = 0;
  CmpMountThread = 0;
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
0x140aeb590  push    rbp
0x140aeb592  push    rbx
0x140aeb593  push    rsi
0x140aeb594  push    rdi
0x140aeb595  push    r12
0x140aeb597  push    r13
0x140aeb599  push    r14
0x140aeb59b  push    r15
0x140aeb59d  lea     rbp, [rsp-258h]
0x140aeb5a5  sub     rsp, 358h
0x140aeb5ac  mov     rax, cs:__security_cookie
0x140aeb5b3  xor     rax, rsp
0x140aeb5b6  mov     [rbp+290h+var_50], rax
0x140aeb5bd  xorps   xmm0, xmm0
0x140aeb5c0  xor     eax, eax
0x140aeb5c2  movups  xmmword ptr [rbp+290h+ObjectAttributes.ObjectName], xmm0
0x140aeb5c6  mov     r12, rcx
0x140aeb5c9  mov     [rbp+290h+var_2B8], rax
0x140aeb5cd  xor     esi, esi
0x140aeb5cf  lea     rcx, [rbp+290h+var_2C8]
0x140aeb5d3  movups  xmmword ptr [rbp+290h+ObjectAttributes+1Ch], xmm0
0x140aeb5d7  mov     [rsp+390h+KeyHandle], rsi
0x140aeb5dc  movups  xmmword ptr [rsp+390h+Destination.Length], xmm0
0x140aeb5e1  movups  xmmword ptr [rbp+290h+ObjectAttributes.Length], xmm0
0x140aeb5e5  movups  [rbp+290h+var_2B0], xmm0
0x140aeb5e9  movups  [rbp+290h+var_2A0], xmm0
0x140aeb5ed  movups  [rbp+290h+var_290], xmm0
0x140aeb5f1  movups  [rbp+290h+var_2C8], xmm0
0x140aeb5f5  call    CmpInitializeThreadInfo
0x140aeb5fa  xor     edx, edx; Val
0x140aeb5fc  lea     rcx, [rbp+290h+var_280]; void *
0x140aeb600  mov     r8d, 1B0h; Size
0x140aeb606  call    memset_0
0x140aeb60b  mov     byte ptr cs:NlsMbOemCodePageTag+1, sil
0x140aeb612  lea     r14d, [rsi+40h]
0x140aeb616  mov     rax, gs:188h
0x140aeb61f  lea     rcx, aRegistry_1; "\\REGISTRY\\"
0x140aeb626  mov     cs:CmpMountThread, rax
0x140aeb62d  lea     r8, [rbp+290h+var_D0]
0x140aeb634  mov     eax, 80h
0x140aeb639  mov     dword ptr [rsp+390h+Destination+4], esi
0x140aeb63d  mov     [rsp+390h+Destination.MaximumLength], ax
0x140aeb642  lea     r13d, [rsi+2]
0x140aeb646  lea     rax, [rbp+290h+var_D0]
0x140aeb64d  mov     edx, r14d
0x140aeb650  mov     [rsp+390h+Destination.Buffer], rax
0x140aeb655  mov     r15d, esi
0x140aeb658  mov     eax, 7FFFh
0x140aeb65d  test    rax, rax
0x140aeb660  jz      short loc_140AEB682
0x140aeb662  movzx   r9d, word ptr [rcx]
0x140aeb666  test    r9w, r9w
0x140aeb66a  jz      short loc_140AEB682
0x140aeb66c  mov     [r8], r9w
0x140aeb670  add     rcx, r13
0x140aeb673  add     r8, r13
0x140aeb676  dec     rax
0x140aeb679  inc     r15
0x140aeb67c  sub     rdx, 1
0x140aeb680  jnz     short loc_140AEB65D
0x140aeb682  mov     ebx, 20204D43h
0x140aeb687  add     r15w, r15w
0x140aeb68b  mov     r8d, ebx
0x140aeb68e  mov     [rsp+390h+Destination.Length], r15w
0x140aeb694  mov     edx, 150h
0x140aeb699  mov     rcx, r14
0x140aeb69c  call    CmpAllocatePool
0x140aeb6a1  mov     [rbp+290h+Privileges], rax
0x140aeb6a5  mov     rdi, rax
0x140aeb6a8  test    rax, rax
0x140aeb6ab  jnz     short loc_140AEB6C9
0x140aeb6ad  xor     r9d, r9d; BugCheckParameter3
0x140aeb6b0  mov     [rsp+390h+BugCheckParameter4], 0FFFFFFFFC000009Ah; BugCheckParameter4
0x140aeb6b9  lea     r8d, [rax+4]; BugCheckParameter2
0x140aeb6bd  mov     rdx, r13; BugCheckParameter1
0x140aeb6c0  lea     ecx, [rax+74h]; BugCheckCode
0x140aeb6c3  call    KeBugCheckEx
0x140aeb6c9  mov     r8d, ebx
0x140aeb6cc  mov     edx, 38h ; '8'
0x140aeb6d1  mov     rcx, r14
0x140aeb6d4  call    CmpAllocatePool
0x140aeb6d9  mov     [rbp+290h+var_300], rax
0x140aeb6dd  mov     rbx, rax
0x140aeb6e0  test    rax, rax
0x140aeb6e3  jnz     short loc_140AEB701
0x140aeb6e5  xor     r9d, r9d; BugCheckParameter3
0x140aeb6e8  mov     [rsp+390h+BugCheckParameter4], 0FFFFFFFFC000009Ah; BugCheckParameter4
0x140aeb6f1  lea     r8d, [rax+6]; BugCheckParameter2
0x140aeb6f5  mov     rdx, r13; BugCheckParameter1
0x140aeb6f8  lea     ecx, [rax+74h]; BugCheckCode
0x140aeb6fb  call    KeBugCheckEx
0x140aeb701  mov     r14b, sil
0x140aeb704  mov     [rsp+390h+var_330], sil
0x140aeb709  call    CmpHiveRootSecurityDescriptor
0x140aeb70e  mov     [rbp+290h+P], rax
0x140aeb712  mov     rdx, rsi
0x140aeb715  imul    rcx, rdx, 0B8h
0x140aeb71c  lea     rax, qword_140E0D018
0x140aeb723  add     rcx, rax
0x140aeb726  mov     [rbx+rdx*8], rcx
0x140aeb72a  inc     rdx
0x140aeb72d  cmp     rdx, 7
0x140aeb731  jnz     short loc_140AEB715
0x140aeb733  test    r12, r12
0x140aeb736  jnz     short loc_140AEB7B7
0x140aeb738  xor     r9d, r9d; Alertable
0x140aeb73b  mov     [rsp+390h+BugCheckParameter4], rsi; Timeout
0x140aeb740  xor     r8d, r8d; WaitMode
0x140aeb743  lea     rcx, stru_140E0D240; Object
0x140aeb74a  xor     edx, edx; WaitReason
0x140aeb74c  call    KeWaitForSingleObject
0x140aeb751  xor     r8d, r8d; Wait
0x140aeb754  lea     rcx, stru_140E0D240; Event
0x140aeb75b  xor     edx, edx; Increment
0x140aeb75d  call    KeSetEvent
0x140aeb762  mov     rcx, cs:PsInitialSystemProcess; BugCheckParameter1
0x140aeb769  lea     r8, [rbp+290h+var_2B0]
0x140aeb76d  xor     edx, edx
0x140aeb76f  call    KiStackAttachProcess
0x140aeb774  mov     dl, cs:CmpInitRmLogOnLoad
0x140aeb77a  xor     ecx, ecx
0x140aeb77c  call    CmpInitCmRM
0x140aeb781  xor     edx, edx
0x140aeb783  lea     rcx, [rbp+290h+var_2B0]
0x140aeb787  call    KiUnstackDetachProcess
0x140aeb78c  mov     rcx, cs:CmRmSystem
0x140aeb793  test    rcx, rcx
0x140aeb796  jz      short loc_140AEB7B7
0x140aeb798  mov     r8, rcx; RMKey
0x140aeb79b  lea     rdx, CmKtmNotification; CallbackRoutine
0x140aeb7a2  mov     rcx, [rcx+38h]; ResourceManager
0x140aeb7a6  call    TmEnableCallbacks
0x140aeb7ab  mov     rcx, cs:CmRmSystem
0x140aeb7b2  call    CmRmFinalizeRecovery
0x140aeb7b7  xor     r9d, r9d; WaitReason
0x140aeb7ba  mov     [rsp+390h+WaitBlockArray], rdi; WaitBlockArray
0x140aeb7bf  mov     [rsp+390h+Timeout], rsi; Timeout
0x140aeb7c4  mov     rdx, rbx; Object
0x140aeb7c7  mov     [rsp+390h+Alertable], sil; Alertable
0x140aeb7cc  mov     byte ptr [rsp+390h+BugCheckParameter4], sil; WaitMode
0x140aeb7d1  lea     r8d, [r9+1]; WaitType
0x140aeb7d5  lea     ecx, [r9+7]; Count
0x140aeb7d9  call    KeWaitForMultipleObjects
0x140aeb7de  mov     r13b, sil
0x140aeb7e1  mov     edi, esi
0x140aeb7e3  cmp     edi, 7
0x140aeb7e6  jnb     loc_140AEBB33
0x140aeb7ec  mov     esi, edi
0x140aeb7ee  lea     rax, CmpMachineHiveList
0x140aeb7f5  imul    rbx, rsi, 0B8h
0x140aeb7fc  cmp     byte ptr [rbx+rax+38h], 0
0x140aeb801  jnz     loc_140AEBB2C
0x140aeb807  cmp     byte ptr [rbx+rax+39h], 0
0x140aeb80c  jnz     short loc_140AEB816
0x140aeb80e  mov     r13b, 1
0x140aeb811  jmp     loc_140AEBB2C
0x140aeb816  mov     rdx, [rbx+rax+8]; Source
0x140aeb81b  lea     rcx, [rsp+390h+Destination]; Destination
0x140aeb820  mov     [rsp+390h+Destination.Length], r15w
0x140aeb826  call    RtlAppendUnicodeToString
0x140aeb82b  lea     rdx, CmpMachineHiveList
0x140aeb832  mov     rdx, [rbx+rdx+10h]; Source
0x140aeb837  lea     rcx, [rsp+390h+Destination]; Destination
0x140aeb83c  call    RtlAppendUnicodeToString
0x140aeb841  call    CmpLockRegistryExclusive
0x140aeb846  xor     ecx, ecx
0x140aeb848  lea     rdx, CmpMachineHiveList
0x140aeb84f  cmp     [rbx+rdx+18h], rcx
0x140aeb854  jnz     loc_140AEB997
0x140aeb85a  mov     r8, [rbx+rdx+30h]; int
0x140aeb85f  test    r8, r8
0x140aeb862  jz      loc_140AEB997
0x140aeb868  mov     r9b, [rbx+rdx+3Bh]; int
0x140aeb86d  lea     rax, [rbp+290h+var_280]
0x140aeb871  mov     [rsp+390h+var_338], rax; __int64
0x140aeb876  mov     rax, [rbp+290h+P]
0x140aeb87a  mov     [rsp+390h+var_340], 1; char
0x140aeb87f  mov     [rsp+390h+var_348], rcx; __int64
0x140aeb884  mov     [rsp+390h+var_350], rcx; __int64
0x140aeb889  mov     [rsp+390h+WaitBlockArray], rax; __int64
0x140aeb88e  mov     eax, [rbx+rdx+28h]
0x140aeb892  xor     edx, edx; int
0x140aeb894  mov     [rsp+390h+Timeout], rcx; Event
0x140aeb899  mov     [rsp+390h+Alertable], cl; char
0x140aeb89d  lea     rcx, [rsp+390h+Destination]; int
0x140aeb8a2  mov     dword ptr [rsp+390h+BugCheckParameter4], eax; int
0x140aeb8a6  call    CmpLinkHiveToMaster
0x140aeb8ab  movsxd  rcx, eax
0x140aeb8ae  test    eax, eax
0x140aeb8b0  js      loc_140AEBB52
0x140aeb8b6  call    CmpLockHiveListExclusive
0x140aeb8bb  mov     rcx, cs:qword_140FDBB50
0x140aeb8c2  lea     rdx, CmpHiveListHead
0x140aeb8c9  cmp     [rcx], rdx
0x140aeb8cc  jnz     loc_140AEBB4B
0x140aeb8d2  lea     rsi, CmpMachineHiveList
0x140aeb8d9  mov     rax, [rbx+rsi+30h]
0x140aeb8de  add     rax, 650h
0x140aeb8e4  mov     [rax], rdx
0x140aeb8e7  mov     [rax+8], rcx
0x140aeb8eb  mov     [rcx], rax
0x140aeb8ee  mov     cs:qword_140FDBB50, rax
0x140aeb8f5  call    CmpUnlockHiveList
0x140aeb8fa  mov     rcx, [rbx+rsi+30h]
0x140aeb8ff  call    CmpRecheckHiveVolumePolicy
0x140aeb904  cmp     byte ptr [rbx+rsi+3Bh], 0
0x140aeb909  jz      short loc_140AEB961
0x140aeb90b  mov     rax, [rbx+rsi+30h]
0x140aeb910  or      dword ptr [rax+0A0h], 20h
0x140aeb917  mov     rcx, gs:188h
0x140aeb920  mov     rax, [rbx+rsi+30h]
0x140aeb925  mov     [rax+1058h], rcx
0x140aeb92c  call    CmpUnlockRegistry
0x140aeb931  mov     rcx, [rbx+rsi+30h]
0x140aeb936  mov     edx, 4
0x140aeb93b  call    CmpFlushHive
0x140aeb940  call    CmpLockRegistryExclusive
0x140aeb945  mov     rax, [rbx+rsi+30h]
0x140aeb94a  and     dword ptr [rax+0A0h], 0FFFFFFDFh
0x140aeb951  mov     rax, [rbx+rsi+30h]
0x140aeb956  mov     qword ptr [rax+1058h], 0
0x140aeb961  mov     rcx, cs:CmRmSystem
0x140aeb968  test    rcx, rcx
0x140aeb96b  jz      short loc_140AEB99E
0x140aeb96d  mov     rdx, [rbx+rsi+30h]
0x140aeb972  mov     eax, [rdx+0A0h]
0x140aeb978  test    al, 2
0x140aeb97a  jnz     short loc_140AEB99E
0x140aeb97c  cmp     qword ptr [rdx+1048h], 0
0x140aeb984  jnz     short loc_140AEB99E
0x140aeb986  inc     dword ptr [rcx+40h]
0x140aeb989  mov     rax, [rbx+rsi+30h]
0x140aeb98e  mov     [rax+1048h], rcx
0x140aeb995  jmp     short loc_140AEB99E
0x140aeb997  lea     rsi, CmpMachineHiveList
0x140aeb99e  mov     rcx, [rbx+rsi+30h]
0x140aeb9a3  test    rcx, rcx
0x140aeb9a6  jz      short loc_140AEB9AD
0x140aeb9a8  call    CmpAddToHiveFileList
0x140aeb9ad  mov     byte ptr [rbx+rsi+38h], 1
0x140aeb9b2  cmp     edi, 3
0x140aeb9b5  jnz     short loc_140AEB9D7
0x140aeb9b7  test    r12, r12
0x140aeb9ba  jnz     short loc_140AEBA15
0x140aeb9bc  call    CmpUnlockRegistry
0x140aeb9c1  call    CmpMountPreloadedHives
0x140aeb9c6  call    CmpLockRegistryExclusive
0x140aeb9cb  call    CmpInterlockedFunction
0x140aeb9d0  call    CmpUnlockRegistry
0x140aeb9d5  jmp     short loc_140AEBA23
0x140aeb9d7  cmp     edi, 2
0x140aeb9da  jnz     short loc_140AEB9E8
0x140aeb9dc  call    CmpUnlockRegistry
0x140aeb9e1  call    CmpCreatePerfKeys
0x140aeb9e6  jmp     short loc_140AEBA1A
0x140aeb9e8  cmp     edi, 1
0x140aeb9eb  jnz     short loc_140AEB9FD
0x140aeb9ed  lea     rdx, aRegistryMachin_3; "\\Registry\\Machine\\SAM\\SAM"
0x140aeb9f4  lea     rcx, aRegistryMachin_189; "\\Registry\\Machine\\Security\\SAM"
0x140aeb9fb  jmp     short loc_140AEBA10
0x140aeb9fd  cmp     edi, 4
0x140aeba00  jnz     short loc_140AEBA15
0x140aeba02  lea     rdx, aRegistryUserDe; "\\Registry\\User\\.Default"
0x140aeba09  lea     rcx, aRegistryUserS1; "\\Registry\\User\\S-1-5-18"
0x140aeba10  call    CmpLinkKeyToHive
0x140aeba15  call    CmpUnlockRegistry
0x140aeba1a  test    r12, r12
0x140aeba1d  jnz     loc_140AEBAD4
0x140aeba23  lea     r14, [rsi+88h]
0x140aeba2a  xor     r8d, r8d
0x140aeba2d  add     r14, rbx
0x140aeba30  xor     edx, edx
0x140aeba32  mov     rcx, r14
0x140aeba35  call    KeAbPreAcquire
0x140aeba3a  lock bts qword ptr [r14], 0
0x140aeba40  mov     rsi, rax
0x140aeba43  jnb     short loc_140AEBA53
0x140aeba45  mov     r8, r14
0x140aeba48  mov     rdx, rax
0x140aeba4b  mov     rcx, r14
0x140aeba4e  call    ExfAcquirePushLockExclusiveEx
0x140aeba53  test    rsi, rsi
0x140aeba56  jz      short loc_140AEBA70
0x140aeba58  mov     eax, cs:?KiAbpGlobalState@@3UKI_AB_GLOBAL_STATE@@A; KI_AB_GLOBAL_STATE KiAbpGlobalState
0x140aeba5e  test    al, 1
0x140aeba60  jz      short loc_140AEBA6C
0x140aeba62  mov     rcx, rsi; this
0x140aeba65  call    ?KiAbpPostAcquire@AutoBoost@@YAXPEAX@Z; AutoBoost::KiAbpPostAcquire(void *)
0x140aeba6a  jmp     short loc_140AEBA70
0x140aeba6c  mov     byte ptr [rsi+0Ah], 1
0x140aeba70  lea     rsi, CmpMachineHiveList
0x140aeba77  xor     r8d, r8d; Wait
0x140aeba7a  lea     rcx, [rsi+70h]
0x140aeba7e  xor     edx, edx; Increment
0x140aeba80  add     rcx, rbx; Event
0x140aeba83  call    KeSetEvent
0x140aeba88  mov     ecx, edi
0x140aeba8a  call    CmpNotifyMachineHiveLoaded
0x140aeba8f  add     rbx, 88h
0x140aeba96  add     rbx, rsi
  ... truncated ...
```
