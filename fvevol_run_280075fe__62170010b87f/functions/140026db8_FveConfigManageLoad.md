# FveConfigManageLoad

- ea: `0x140026db8`
- end: `0x140027804`
- name: `FveConfigManageLoad`
- size: `2636`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x1400520f8`

## callees

- `0x140005edc`
- `0x1400063a8`
- `0x140006670`
- `0x140007ce8`
- `0x14000a574`
- `0x14000b3ac`
- `0x14000b62c`
- `0x14000f724`
- `0x14001ac5c`
- `0x1400218c0`
- `0x140021a00`
- `0x140021d00`
- `0x1400241b4`
- `0x140026db8`
- `0x140029a38`
- `0x14002d630`
- `0x14002e334`
- `0x14002ef38`
- `0x140050e94`
- `0x140072e68`
- `0x140073118`
- `0x140085e60`
- `0x140091688`
- `0x1400ba360`
- `0x1400ba834`
- `0x1400da590`
- `0x1400da8d4`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400274aa`
- `ntoskrnl!KeReleaseMutex` at `0x140027798`
- `ntoskrnl!KeReleaseMutex` at `0x1400274aa`
- `ntoskrnl!KeReleaseMutex` at `0x140027798`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x1400272c0`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x1400272c0`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140027395`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140027395`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140027743`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140027743`
- `ntoskrnl!MmSizeOfMdl` at `0x1400272af`
- `ntoskrnl!MmSizeOfMdl` at `0x1400272af`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027493`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027493`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027430`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027430`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140027100`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140027100`
- `ntoskrnl!IoFreeMdl` at `0x140027123`
- `ntoskrnl!IoFreeMdl` at `0x140027123`
- `ntoskrnl!MmUnlockPages` at `0x140027114`
- `ntoskrnl!MmUnlockPages` at `0x140027114`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400270c2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400270c2`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002703d`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002703d`
- `ntoskrnl!IoAllocateMdl` at `0x140026ff8`
- `ntoskrnl!IoAllocateMdl` at `0x140026ff8`
- `ntoskrnl!KeStackAttachProcess` at `0x140027028`
- `ntoskrnl!KeStackAttachProcess` at `0x140027028`
- `ntoskrnl!KeWaitForSingleObject` at `0x140026ef5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140027456`
- `ntoskrnl!KeWaitForSingleObject` at `0x140026ef5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140027456`
- `ntoskrnl!KeBugCheckEx` at `0x14002765f`
- `ntoskrnl!KeBugCheckEx` at `0x14002765f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027757`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027782`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400277d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027757`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027782`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400277d2`
- `ntoskrnl!ExAllocatePool2` at `0x140026f68`
- `ntoskrnl!ExAllocatePool2` at `0x140027353`
- `ntoskrnl!ExAllocatePool2` at `0x140026f68`
- `ntoskrnl!ExAllocatePool2` at `0x140027353`

## pseudocode

```c
__int64 __fastcall FveConfigManageLoad(__int64 a1, __int64 a2, struct _KPROCESS *a3, __int64 a4)
{
  __int64 v5; // r14
  struct _NPAGED_LOOKASIDE_LIST *Pool2; // r13
  __int64 *p_pusResult; // r12
  NTSTATUS ChatConfig; // esi
  int v10; // r8d
  __int64 v11; // rbx
  ULONG v12; // ecx
  size_t v13; // r14
  PVOID LookasideList; // r14
  _QWORD *v15; // rbx
  __int64 v16; // rax
  PMDL Mdl; // rbx
  PVOID MappedSystemVa; // rax
  __int64 v19; // r8
  PVOID *v20; // rcx
  _QWORD *v21; // rax
  unsigned int v22; // ebx
  unsigned int v23; // ebx
  int v24; // edx
  int v25; // r8d
  int v26; // r9d
  int v27; // ecx
  __int64 DeviceExtension; // rbx
  PVOID *v29; // r14
  int v30; // r8d
  KIRQL v31; // al
  PVOID *v32; // rcx
  PVOID *v33; // rcx
  _QWORD *v34; // rax
  __int64 *v35; // rdx
  __int64 v36; // rcx
  _QWORD *v37; // rax
  PVOID *v38; // rax
  PVOID *i; // rbx
  _QWORD *v40; // rax
  int v41; // ecx
  __int64 v42; // rdx
  _QWORD *v43; // rcx
  __int64 v44; // rax
  PVOID *j; // rbx
  PVOID *k; // rbx
  int Timeout; // [rsp+20h] [rbp-418h]
  KIRQL v49; // [rsp+50h] [rbp-3E8h]
  char v50; // [rsp+51h] [rbp-3E7h]
  PVOID v51; // [rsp+58h] [rbp-3E0h] BYREF
  PVOID v52; // [rsp+60h] [rbp-3D8h] BYREF
  PVOID *v53; // [rsp+68h] [rbp-3D0h]
  ULONG cbInput; // [rsp+70h] [rbp-3C8h] BYREF
  PVOID v55; // [rsp+78h] [rbp-3C0h] BYREF
  __int64 *v56; // [rsp+80h] [rbp-3B8h]
  PUCHAR pbInput; // [rsp+88h] [rbp-3B0h]
  ULONG pulResult[2]; // [rsp+90h] [rbp-3A8h] BYREF
  struct _NPAGED_LOOKASIDE_LIST *v59; // [rsp+98h] [rbp-3A0h] BYREF
  __int64 pusResult; // [rsp+A0h] [rbp-398h] BYREF
  PVOID P; // [rsp+A8h] [rbp-390h]
  __int64 v62; // [rsp+B0h] [rbp-388h]
  PMDL v63; // [rsp+B8h] [rbp-380h]
  PRKPROCESS PROCESS; // [rsp+C0h] [rbp-378h]
  __int64 v65; // [rsp+C8h] [rbp-370h]
  __int64 v66; // [rsp+D0h] [rbp-368h]
  __int64 *v67; // [rsp+D8h] [rbp-360h]
  PRKMUTEX Mutex; // [rsp+E0h] [rbp-358h]
  void *v69[26]; // [rsp+F0h] [rbp-348h] BYREF
  _KAPC_STATE ApcState; // [rsp+1C0h] [rbp-278h] BYREF
  _BYTE v71[80]; // [rsp+1F0h] [rbp-248h] BYREF
  _DWORD Length[108]; // [rsp+240h] [rbp-1F8h] BYREF

  v63 = (PMDL)a4;
  PROCESS = a3;
  v5 = a2;
  v62 = a2;
  v65 = a1;
  v66 = a2;
  Pool2 = 0;
  v59 = 0;
  v51 = 0;
  v50 = 0;
  v55 = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  pulResult[0] = 0;
  pusResult = 0;
  P = 0;
  p_pusResult = &pusResult;
  if ( !*(_WORD *)(a4 + 16) )
    p_pusResult = 0;
  v56 = p_pusResult;
  v67 = p_pusResult;
  pbInput = 0;
  cbInput = 0;
  memset(v71, 0, 0x48u);
  memset(v69, 0, sizeof(v69));
  memset(Length, 0, 0x1A8u);
  v53 = &v52;
  v52 = &v52;
  Mutex = (PRKMUTEX)(a1 + 9608);
  KeWaitForSingleObject((PVOID)(a1 + 9608), Executive, 0, 0, 0);
  ChatConfig = RtlULongLongToULong(2LL * *(unsigned __int16 *)(a4 + 16), pulResult);
  if ( ChatConfig < 0 )
    goto LABEL_9;
  v11 = pulResult[0];
  if ( pulResult[0] )
  {
    ChatConfig = RtlULongToUShort(pulResult[0], (USHORT *)&pusResult);
    if ( ChatConfig < 0 )
      goto LABEL_9;
    ChatConfig = RtlULongToUShort(v12, (USHORT *)&pusResult + 1);
    if ( ChatConfig < 0 )
      goto LABEL_9;
    v13 = (unsigned int)v11;
    *(_QWORD *)pulResult = v11;
    P = (PVOID)ExAllocatePool2(64, (unsigned int)v11, 809850438);
    if ( !P )
      goto LABEL_8;
    Mdl = IoAllocateMdl(*(PVOID *)&v63->Size, v11, 0, 1u, 0);
    v63 = Mdl;
    if ( !Mdl )
      goto LABEL_8;
    KeStackAttachProcess(PROCESS, &ApcState);
    MmProbeAndLockPages(Mdl, 1, IoReadAccess);
    if ( (Mdl->MdlFlags & 5) != 0 )
      MappedSystemVa = Mdl->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(Mdl, 0, MmCached, 0, 0, 0x40000010u);
    if ( MappedSystemVa )
      memmove(P, MappedSystemVa, v13);
    else
      ChatConfig = -1073741670;
    KeUnstackDetachProcess(&ApcState);
    MmUnlockPages(Mdl);
    IoFreeMdl(Mdl);
    if ( ChatConfig < 0 )
      goto LABEL_9;
    p_pusResult = v56;
    v5 = v62;
  }
  if ( v5 )
  {
    LOBYTE(v10) = 1;
    ChatConfig = FveConfigManageEntryCreate(v5, *(_DWORD *)(a1 + 884), v10, (_DWORD)p_pusResult, 0, (__int64)&v55);
    if ( ChatConfig < 0 )
      goto LABEL_9;
    ChatConfig = FvepAcquireRemoveLockEx(v5 + 56);
    if ( ChatConfig < 0 )
    {
      FveConfigManageEntryRelease(v55);
      ChatConfig = 0;
      goto LABEL_9;
    }
    v20 = v53;
    if ( *v53 == &v52 )
    {
      v21 = v55;
      *(_QWORD *)v55 = &v52;
      v21[1] = v20;
      *v20 = v21;
      v53 = (PVOID *)v21;
      goto LABEL_70;
    }
LABEL_95:
    __fastfail(3u);
  }
  ChatConfig = FveLoadChatConfig(a1, p_pusResult, v69);
  if ( !v69[24] )
  {
    if ( ChatConfig < 0 )
      ChatConfig = -1073741823;
    goto LABEL_9;
  }
  FveLoadCryptoThrottleConfig(a1, p_pusResult, v69, v71);
  FveLoadIoCryptoConfig(a1, 0, 0, (_DWORD)p_pusResult, (__int64)Length);
  ChatConfig = FveLibAllocWithTagZero((size_t)v69[25]);
  if ( ChatConfig < 0 || (ChatConfig = RtlULongLongToULong((ULONGLONG)v69[25], &cbInput), ChatConfig < 0) )
  {
LABEL_9:
    LookasideList = v51;
    goto LABEL_10;
  }
  memmove(pbInput, v69[24], cbInput);
  v22 = Length[*(unsigned int *)(a1 + 884)];
  v23 = MmSizeOfMdl(0, v22) + 64 + v22;
  if ( !MmIsThisAnNtAsSystem() )
  {
    Pool2 = (struct _NPAGED_LOOKASIDE_LIST *)ExAllocatePool2(64, 128, 809850438);
    v59 = Pool2;
    if ( Pool2 )
    {
      ExInitializeNPagedLookasideList(Pool2, 0, 0, 0x200u, v23, 0x70455646u, 0);
LABEL_42:
      DeviceExtension = 0;
      v29 = 0;
      v49 = 0;
      v50 = 1;
      while ( 1 )
      {
        DeviceExtension = FveDcbNextDeviceExtension(a1, DeviceExtension, 0xFFFFFFFFLL);
        if ( !DeviceExtension )
          break;
        LOBYTE(v30) = 1;
        ChatConfig = FveConfigManageEntryCreate(
                       DeviceExtension,
                       *(_DWORD *)(a1 + 884),
                       v30,
                       (_DWORD)p_pusResult,
                       (__int64)Length,
                       (__int64)&v55);
        if ( ChatConfig < 0 )
          goto LABEL_9;
        if ( (int)FvepAcquireRemoveLockEx(DeviceExtension + 56) >= 0 )
        {
          if ( *(_DWORD *)(DeviceExtension + 836) == 2 )
          {
            KeWaitForSingleObject((PVOID)(DeviceExtension + 504), Executive, 0, 0, 0);
            v31 = v49;
          }
          else
          {
            v31 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(DeviceExtension + 496));
            v49 = v31;
          }
          if ( *(int *)(DeviceExtension + 136) > 0 && *(_DWORD *)(DeviceExtension + 168) && !v29 )
          {
            v29 = (PVOID *)v55;
            v55 = 0;
          }
          if ( *(_DWORD *)(DeviceExtension + 836) == 2 )
            KeReleaseMutex((PRKMUTEX)(DeviceExtension + 504), 0);
          else
            KeReleaseSpinLock((PKSPIN_LOCK)(DeviceExtension + 496), v31);
          LODWORD(p_pusResult) = (_DWORD)v56;
          if ( v55 )
          {
            v32 = (PVOID *)v52;
            if ( v52 != &v52 )
            {
              do
              {
                if ( *(_DWORD *)(DeviceExtension + 1324) > *((_DWORD *)v32[2] + 331) )
                  break;
                v32 = (PVOID *)*v32;
              }
              while ( v32 != &v52 );
            }
            if ( v32 == &v52 )
            {
              v33 = v53;
              if ( *v53 != &v52 )
                goto LABEL_95;
              v34 = v55;
              *(_QWORD *)v55 = &v52;
              v34[1] = v33;
              *v33 = v34;
              v53 = (PVOID *)v34;
            }
            else
            {
              v35 = (__int64 *)v32[1];
              v36 = *v35;
              if ( *(__int64 **)(*v35 + 8) != v35 )
                goto LABEL_95;
              v37 = v55;
              *(_QWORD *)v55 = v36;
              v37[1] = v35;
              *(_QWORD *)(v36 + 8) = v37;
              *v35 = (__int64)v37;
            }
          }
        }
        else
        {
          FveConfigManageEntryRelease(v55);
        }
      }
      if ( v29 )
      {
        v38 = v53;
        if ( *v53 != &v52 )
          goto LABEL_95;
        *v29 = &v52;
        v29[1] = v38;
        *v38 = v29;
        v53 = v29;
      }
      FveChatConfig(pbInput, cbInput);
      pbInput = 0;
      cbInput = 0;
      v5 = v62;
LABEL_70:
      for ( i = (PVOID *)v52; i != &v52; i = (PVOID *)*i )
      {
        LOBYTE(v19) = 1;
        FvepAcquireDevFveLock(i[2], i + 3, v19);
        FveRundownAllReadsAndWrites(i[2]);
        v40 = i[2];
        if ( v40[252] || (v41 = 0, v40[253]) )
          v41 = 1;
        *((_DWORD *)i + 156) = v41;
        v42 = v40[252];
        if ( v42 && v42 == *(_QWORD *)(a1 + 9008) )
        {
          if ( !v41 )
            goto LABEL_84;
          v40[252] = 0;
        }
        v43 = i[2];
        v44 = v43[253];
        if ( v44 && v44 == *(_QWORD *)(a1 + 9016) )
        {
          if ( !*((_DWORD *)i + 156) )
LABEL_84:
            KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
          v43[253] = 0;
        }
      }
      if ( !v5 )
      {
        FveReadWriteDriverReconfig(a1, v69, v71, Length, &v59, &v51);
        Pool2 = v59;
      }
      for ( j = (PVOID *)v52; j != &v52; j = (PVOID *)*j )
      {
        if ( *((_DWORD *)j + 156) )
          FveReadWriteDeviceReconfig(j[2], j + 21, j + 74, j + 75, j + 76, j + 77);
      }
      for ( k = v53; k != &v52; k = (PVOID *)k[1] )
      {
        FveResumeAllReadsAndWrites(k[2]);
        FvepReleaseDevFveLock(k + 3);
      }
      goto LABEL_9;
    }
LABEL_8:
    ChatConfig = -1073741670;
    goto LABEL_9;
  }
  v27 = Feature_BitLocker_PerProc_Buffer__private_featureState;
  v51 = (PVOID)(unsigned int)Feature_BitLocker_PerProc_Buffer__private_featureState;
  if ( (Feature_BitLocker_PerProc_Buffer__private_featureState & 0x10) == 0 )
  {
    LODWORD(v51) = Feature_BitLocker_PerProc_Buffer__private_featureState | 1;
    wil_details_FeatureReporting_ReportUsageToService(Feature_BitLocker_PerProc_Buffer__private_descriptor, v51, 3);
    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
      v51,
      3,
      Feature_BitLocker_PerProc_Buffer__private_descriptor);
  }
  LookasideList = (PVOID)PplCreateLookasideList(v27, v24, v25, v26, Timeout, v23);
  v51 = LookasideList;
  if ( LookasideList )
    goto LABEL_42;
  ChatConfig = -1073741670;
LABEL_10:
  while ( 1 )
  {
    v15 = v52;
    if ( v52 == &v52 )
      break;
    if ( *((PVOID **)v52 + 1) != &v52 )
      goto LABEL_95;
    v16 = *(_QWORD *)v52;
    if ( *(PVOID *)(*(_QWORD *)v52 + 8LL) != v52 )
      goto LABEL_95;
    v52 = *(PVOID *)v52;
    *(_QWORD *)(v16 + 8) = &v52;
    FvepReleaseRemoveLock(v15[2] + 56LL);
    FveConfigManageEntryRelease(v15);
  }
  if ( Pool2 )
  {
    if ( v50 )
      ExDeleteNPagedLookasideList(Pool2);
    ExFreePoolWithTag(Pool2, 0x30455646u);
  }
  if ( LookasideList )
    PplDestroyLookasideList(LookasideList);
  if ( P )
    ExFreePoolWithTag(P, 0x30455646u);
  KeReleaseMutex(Mutex, 0);
  if ( pbInput )
    FveLibFreeWithTag(pbInput, cbInput, 2);
  if ( v69[24] )
    ExFreePoolWithTag(v69[24], 0x30455646u);
  return (unsigned int)ChatConfig;
}

```

## disassembly

```asm
0x140026db8  mov     r11, rsp
0x140026dbb  push    rbx
0x140026dbc  push    rsi
0x140026dbd  push    rdi
0x140026dbe  push    r12
0x140026dc0  push    r13
0x140026dc2  push    r14
0x140026dc4  push    r15
0x140026dc6  sub     rsp, 400h
0x140026dcd  mov     rax, cs:__security_cookie
0x140026dd4  xor     rax, rsp
0x140026dd7  mov     [rsp+438h+var_48], rax
0x140026ddf  mov     rbx, r9
0x140026de2  mov     [rsp+438h+var_380], rbx
0x140026dea  mov     [rsp+438h+PROCESS], r8
0x140026df2  mov     r14, rdx
0x140026df5  mov     [rsp+438h+var_388], rdx
0x140026dfd  mov     r15, rcx
0x140026e00  mov     [rsp+438h+var_370], rcx
0x140026e08  mov     [rsp+438h+var_368], rdx
0x140026e10  xor     edi, edi
0x140026e12  mov     r13d, edi
0x140026e15  mov     [r11-3A0h], rdi
0x140026e1c  mov     [rsp+438h+var_3E0], rdi
0x140026e21  mov     [rsp+438h+var_3E7], dil
0x140026e26  mov     [rsp+438h+var_3C0], rdi
0x140026e2b  xorps   xmm0, xmm0
0x140026e2e  movups  xmmword ptr [rsp+438h+ApcState.ApcListHead.Flink], xmm0
0x140026e36  movups  xmmword ptr [rsp+438h+ApcState.ApcListHead.Flink+10h], xmm0
0x140026e3e  movups  xmmword ptr [rsp+438h+ApcState.Process], xmm0
0x140026e46  mov     [rsp+438h+pulResult], edi
0x140026e4d  mov     [r11-398h], rdi
0x140026e54  mov     [r11-390h], rdi
0x140026e5b  lea     r12, [r11-398h]
0x140026e62  cmp     [r9+10h], di
0x140026e67  cmovbe  r12, rdi
0x140026e6b  mov     [rsp+438h+var_3B8], r12
0x140026e73  mov     [rsp+438h+var_360], r12
0x140026e7b  mov     [r11-3B0h], rdi
0x140026e82  mov     [rsp+438h+cbInput], edi
0x140026e86  xor     edx, edx; Val
0x140026e88  lea     r8d, [rdi+48h]; Size
0x140026e8c  lea     rcx, [r11-248h]; void *
0x140026e93  call    memset
0x140026e98  xor     edx, edx; Val
0x140026e9a  mov     r8d, 0D0h; Size
0x140026ea0  lea     rcx, [rsp+438h+var_348]; void *
0x140026ea8  call    memset
0x140026ead  xor     edx, edx; Val
0x140026eaf  mov     r8d, 1A8h; Size
0x140026eb5  lea     rcx, [rsp+438h+Length]; void *
0x140026ebd  call    memset
0x140026ec2  lea     rax, [rsp+438h+var_3D8]
0x140026ec7  mov     [rsp+438h+var_3D0], rax
0x140026ecc  lea     rax, [rsp+438h+var_3D8]
0x140026ed1  mov     [rsp+438h+var_3D8], rax
0x140026ed6  lea     rax, [r15+2588h]
0x140026edd  mov     [rsp+438h+Mutex], rax
0x140026ee5  mov     [rsp+438h+Timeout], rdi; Timeout
0x140026eea  xor     r9d, r9d; Alertable
0x140026eed  xor     r8d, r8d; WaitMode
0x140026ef0  xor     edx, edx; WaitReason
0x140026ef2  mov     rcx, rax; Object
0x140026ef5  call    cs:__imp_KeWaitForSingleObject
0x140026efc  nop     dword ptr [rax+rax+00h]
0x140026f01  movzx   ecx, word ptr [rbx+10h]
0x140026f05  add     rcx, rcx; ullOperand
0x140026f08  lea     rdx, [rsp+438h+pulResult]; pulResult
0x140026f10  call    RtlULongLongToULong
0x140026f15  mov     esi, eax
0x140026f17  test    eax, eax
0x140026f19  js      short loc_140026F86
0x140026f1b  mov     ebx, [rsp+438h+pulResult]
0x140026f22  test    ebx, ebx
0x140026f24  jz      loc_140027147
0x140026f2a  lea     rdx, [rsp+438h+pusResult]; pusResult
0x140026f32  mov     ecx, ebx; ulOperand
0x140026f34  call    RtlULongToUShort
0x140026f39  mov     esi, eax
0x140026f3b  test    eax, eax
0x140026f3d  js      short loc_140026F86
0x140026f3f  lea     rdx, [rsp+438h+var_396]; pusResult
0x140026f47  call    RtlULongToUShort
0x140026f4c  mov     esi, eax
0x140026f4e  test    eax, eax
0x140026f50  js      short loc_140026F86
0x140026f52  mov     r14d, ebx
0x140026f55  mov     qword ptr [rsp+438h+pulResult], rbx
0x140026f5d  mov     r8d, 30455646h
0x140026f63  mov     edx, ebx
0x140026f65  lea     ecx, [rdi+40h]
0x140026f68  call    cs:__imp_ExAllocatePool2
0x140026f6f  nop     dword ptr [rax+rax+00h]
0x140026f74  mov     [rsp+438h+P], rax
0x140026f7c  test    rax, rax
0x140026f7f  jnz     short loc_140026FDF
0x140026f81  mov     esi, 0C000009Ah
0x140026f86  mov     r14, [rsp+438h+var_3E0]
0x140026f8b  mov     rbx, [rsp+438h+var_3D8]
0x140026f90  lea     rax, [rsp+438h+var_3D8]
0x140026f95  cmp     rbx, rax
0x140026f98  jz      loc_140027734
0x140026f9e  lea     rax, [rsp+438h+var_3D8]
0x140026fa3  cmp     [rbx+8], rax
0x140026fa7  jnz     loc_14002772D
0x140026fad  mov     rax, [rbx]
0x140026fb0  cmp     [rax+8], rbx
0x140026fb4  jnz     loc_14002772D
0x140026fba  mov     [rsp+438h+var_3D8], rax
0x140026fbf  lea     rcx, [rsp+438h+var_3D8]
0x140026fc4  mov     [rax+8], rcx
0x140026fc8  mov     rcx, [rbx+10h]
0x140026fcc  add     rcx, 38h ; '8'; BugCheckParameter2
0x140026fd0  call    FvepReleaseRemoveLock
0x140026fd5  mov     rcx, rbx; P
0x140026fd8  call    FveConfigManageEntryRelease
0x140026fdd  jmp     short loc_140026F8B
0x140026fdf  mov     [rsp+438h+Timeout], rdi; Irp
0x140026fe4  mov     r9b, 1; ChargeQuota
0x140026fe7  xor     r8d, r8d; SecondaryBuffer
0x140026fea  mov     edx, ebx; Length
0x140026fec  mov     rcx, [rsp+438h+var_380]
0x140026ff4  mov     rcx, [rcx+8]; VirtualAddress
0x140026ff8  call    cs:__imp_IoAllocateMdl
0x140026fff  nop     dword ptr [rax+rax+00h]
0x140027004  mov     rbx, rax
0x140027007  mov     [rsp+438h+var_380], rax
0x14002700f  test    rax, rax
0x140027012  jz      loc_140026F81
0x140027018  lea     rdx, [rsp+438h+ApcState]; ApcState
0x140027020  mov     rcx, [rsp+438h+PROCESS]; PROCESS
0x140027028  call    cs:__imp_KeStackAttachProcess
0x14002702f  nop     dword ptr [rax+rax+00h]
0x140027034  nop
0x140027035  xor     r8d, r8d; Operation
0x140027038  mov     dl, 1; AccessMode
0x14002703a  mov     rcx, rbx; MemoryDescriptorList
0x14002703d  call    cs:__imp_MmProbeAndLockPages
0x140027044  nop     dword ptr [rax+rax+00h]
0x140027049  jmp     short loc_140027097
0x14002704b  mov     esi, 0C000000Dh
0x140027050  xor     edi, edi
0x140027052  mov     r13, [rsp+438h+var_3A0]
0x14002705a  mov     [rsp+438h+var_3E7], dil
0x14002705f  mov     rbx, [rsp+438h+var_380]
0x140027067  mov     r15, [rsp+438h+var_370]
0x14002706f  mov     rax, [rsp+438h+var_368]
0x140027077  mov     [rsp+438h+var_388], rax
0x14002707f  mov     r14, qword ptr [rsp+438h+pulResult]
0x140027087  mov     rax, [rsp+438h+var_360]
0x14002708f  mov     [rsp+438h+var_3B8], rax
0x140027097  test    esi, esi
0x140027099  js      short loc_1400270DA
0x14002709b  mov     r12b, 1
0x14002709e  test    byte ptr [rbx+0Ah], 5
0x1400270a2  jz      short loc_1400270AA
0x1400270a4  mov     rax, [rbx+18h]
0x1400270a8  jmp     short loc_1400270CE
0x1400270aa  mov     [rsp+438h+Priority], 40000010h; Priority
0x1400270b2  mov     dword ptr [rsp+438h+Timeout], edi; BugCheckOnFailure
0x1400270b6  xor     r9d, r9d; RequestedAddress
0x1400270b9  xor     edx, edx; AccessMode
0x1400270bb  lea     r8d, [r9+1]; CacheType
0x1400270bf  mov     rcx, rbx; MemoryDescriptorList
0x1400270c2  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400270c9  nop     dword ptr [rax+rax+00h]
0x1400270ce  test    rax, rax
0x1400270d1  jnz     short loc_1400270E5
0x1400270d3  mov     esi, 0C000009Ah
0x1400270d8  jmp     short loc_1400270E0
0x1400270da  mov     r12b, dil
0x1400270dd  mov     rax, rdi
0x1400270e0  test    rax, rax
0x1400270e3  jz      short loc_1400270F8
0x1400270e5  mov     r8, r14; Size
0x1400270e8  mov     rdx, rax; Src
0x1400270eb  mov     rcx, [rsp+438h+P]; void *
0x1400270f3  call    memmove
0x1400270f8  lea     rcx, [rsp+438h+ApcState]; ApcState
0x140027100  call    cs:__imp_KeUnstackDetachProcess
0x140027107  nop     dword ptr [rax+rax+00h]
0x14002710c  test    r12b, r12b
0x14002710f  jz      short loc_140027120
0x140027111  mov     rcx, rbx; MemoryDescriptorList
0x140027114  call    cs:__imp_MmUnlockPages
0x14002711b  nop     dword ptr [rax+rax+00h]
0x140027120  mov     rcx, rbx; Mdl
0x140027123  call    cs:__imp_IoFreeMdl
0x14002712a  nop     dword ptr [rax+rax+00h]
0x14002712f  test    esi, esi
0x140027131  js      loc_140026F86
0x140027137  mov     r12, [rsp+438h+var_3B8]
0x14002713f  mov     r14, [rsp+438h+var_388]
0x140027147  test    r14, r14
0x14002714a  jz      loc_1400271D1
0x140027150  lea     rax, [rsp+438h+var_3C0]
0x140027155  mov     qword ptr [rsp+438h+Priority], rax
0x14002715a  mov     [rsp+438h+Timeout], rdi
0x14002715f  mov     r9, r12
0x140027162  mov     r8b, 1
0x140027165  mov     edx, [r15+374h]
0x14002716c  mov     rcx, r14
0x14002716f  call    FveConfigManageEntryCreate
0x140027174  mov     esi, eax
0x140027176  test    eax, eax
0x140027178  js      loc_140026F86
0x14002717e  lea     rcx, [r14+38h]; BugCheckParameter2
0x140027182  xor     edx, edx
0x140027184  call    FvepAcquireRemoveLockEx
0x140027189  mov     esi, eax
0x14002718b  test    eax, eax
0x14002718d  jns     short loc_1400271A0
0x14002718f  mov     rcx, [rsp+438h+var_3C0]; P
0x140027194  call    FveConfigManageEntryRelease
0x140027199  mov     esi, edi
0x14002719b  jmp     loc_140026F86
0x1400271a0  mov     rcx, [rsp+438h+var_3D0]
0x1400271a5  lea     rax, [rsp+438h+var_3D8]
0x1400271aa  cmp     [rcx], rax
0x1400271ad  jnz     loc_14002772D
0x1400271b3  mov     rax, [rsp+438h+var_3C0]
0x1400271b8  lea     rdx, [rsp+438h+var_3D8]
0x1400271bd  mov     [rax], rdx
0x1400271c0  mov     [rax+8], rcx
0x1400271c4  mov     [rcx], rax
0x1400271c7  mov     [rsp+438h+var_3D0], rax
0x1400271cc  jmp     loc_1400275AC
0x1400271d1  lea     r8, [rsp+438h+var_348]
0x1400271d9  mov     rdx, r12
0x1400271dc  mov     rcx, r15
0x1400271df  call    FveLoadChatConfig
0x1400271e4  mov     esi, eax
0x1400271e6  cmp     [rsp+438h+Src], rdi
0x1400271ee  jnz     short loc_1400271FF
0x1400271f0  mov     eax, 0C0000001h
0x1400271f5  test    esi, esi
0x1400271f7  cmovs   esi, eax
0x1400271fa  jmp     loc_140026F86
0x1400271ff  lea     r9, [rsp+438h+var_248]
0x140027207  lea     r8, [rsp+438h+var_348]
0x14002720f  mov     rdx, r12
0x140027212  mov     rcx, r15
0x140027215  call    FveLoadCryptoThrottleConfig
0x14002721a  lea     rax, [rsp+438h+Length]
0x140027222  mov     [rsp+438h+Timeout], rax; int
0x140027227  mov     r9, r12
0x14002722a  xor     r8d, r8d
0x14002722d  xor     edx, edx
0x14002722f  mov     rcx, r15
0x140027232  call    FveLoadIoCryptoConfig
0x140027237  lea     r8, [rsp+438h+pbInput]
0x14002723f  mov     edx, 2
0x140027244  mov     rcx, [rsp+438h+ullOperand]; Size
0x14002724c  call    FveLibAllocWithTagZero
0x140027251  mov     esi, eax
0x140027253  test    eax, eax
0x140027255  js      loc_140026F86
0x14002725b  lea     rdx, [rsp+438h+cbInput]; pulResult
0x140027260  mov     rcx, [rsp+438h+ullOperand]; ullOperand
0x140027268  call    RtlULongLongToULong
0x14002726d  mov     esi, eax
0x14002726f  test    eax, eax
0x140027271  js      loc_140026F86
0x140027277  mov     r8d, [rsp+438h+cbInput]; Size
0x14002727c  mov     rdx, [rsp+438h+Src]; Src
0x140027284  mov     rcx, [rsp+438h+pbInput]; void *
0x14002728c  call    memmove
0x140027291  mov     eax, [r15+374h]
0x140027298  mov     ebx, [rsp+rax*4+438h+Length]
0x14002729f  mov     eax, [r15+374h]
0x1400272a6  mov     edx, [rsp+rax*4+438h+Length]; Length
0x1400272ad  xor     ecx, ecx; Base
0x1400272af  call    cs:__imp_MmSizeOfMdl
0x1400272b6  nop     dword ptr [rax+rax+00h]
0x1400272bb  add     eax, 40h ; '@'
0x1400272be  add     ebx, eax
0x1400272c0  call    cs:__imp_MmIsThisAnNtAsSystem
0x1400272c7  nop     dword ptr [rax+rax+00h]
0x1400272cc  test    al, al
0x1400272ce  jz      short loc_140027345
0x1400272d0  mov     [rsp+438h+var_3E0], rdi
0x1400272d5  mov     ecx, cs:Feature_BitLocker_PerProc_Buffer__private_featureState
0x1400272db  mov     dword ptr [rsp+438h+var_3E0], ecx
0x1400272df  test    cl, 10h
0x1400272e2  jnz     short loc_140027322
0x1400272e4  mov     rax, [rsp+438h+var_3E0]
0x1400272e9  mov     [rsp+438h+var_3E0], rax
0x1400272ee  or      ecx, 1
0x1400272f1  mov     dword ptr [rsp+438h+var_3E0], ecx
0x1400272f5  mov     r8d, 3
0x1400272fb  mov     rdx, [rsp+438h+var_3E0]
0x140027300  lea     rcx, Feature_BitLocker_PerProc_Buffer__private_descriptor
0x140027307  call    wil_details_FeatureReporting_ReportUsageToService
0x14002730c  lea     r8, Feature_BitLocker_PerProc_Buffer__private_descriptor
0x140027313  mov     edx, 3
0x140027318  mov     rcx, [rsp+438h+var_3E0]
0x14002731d  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x140027322  mov     eax, ebx
0x140027324  mov     qword ptr [rsp+438h+Priority], rax; SIZE_T
0x140027329  call    PplCreateLookasideList
  ... truncated ...
```
