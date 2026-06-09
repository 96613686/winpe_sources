# MRxSmb2Close

- ea: `0x140013210`
- end: `0x1400139a6`
- name: `MRxSmb2Close`
- size: `1942`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140007020`
- `0x140012f00`

## callees

- `0x140010080`
- `0x1400128a0`
- `0x140013210`
- `0x140013d00`
- `0x140014650`
- `0x140014db0`
- `0x140016df0`
- `0x140017960`
- `0x1400297fc`
- `0x140029b64`
- `0x140029c14`
- `0x140029cb0`
- `0x14002a1dc`
- `0x140037120`
- `0x140056930`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400133f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400138ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400133f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400138ce`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400138ba`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400138ba`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400138a5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400138f2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400138a5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400138f2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400137a6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400137a6`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14001339b`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400133ba`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14001339b`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400133ba`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140013385`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140013385`
- `ntoskrnl!ObfDereferenceObject` at `0x140013359`
- `ntoskrnl!ObfDereferenceObject` at `0x140013359`
- `ntoskrnl!ZwClose` at `0x1400133ab`
- `ntoskrnl!ZwClose` at `0x1400133cc`
- `ntoskrnl!ZwClose` at `0x1400133ab`
- `ntoskrnl!ZwClose` at `0x1400133cc`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400133dd`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400133dd`
- `ntoskrnl!KeStackAttachProcess` at `0x140013379`
- `ntoskrnl!KeStackAttachProcess` at `0x140013379`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400135c9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140013639`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400137e9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400138e3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400135c9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140013639`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400137e9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400138e3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001357d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400137b8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001357d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400137b8`
- `rdbss!RxGetRDBSSProcess` at `0x140013365`
- `rdbss!RxGetRDBSSProcess` at `0x140013365`
- `mrxsmb!SmbCeDecrementNtlmOpenCounts` at `0x14001392c`
- `mrxsmb!SmbCeDecrementNtlmOpenCounts` at `0x14001392c`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140013775`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140013785`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140013775`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140013785`
- `mrxsmb!SmbCeInitiateExchange` at `0x140013753`
- `mrxsmb!SmbCeInitiateExchange` at `0x140013753`
- `mrxsmb!SmbCeInitializeExchange` at `0x140013726`
- `mrxsmb!SmbCeInitializeExchange` at `0x140013726`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x1400136e2`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140013896`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x1400136e2`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140013896`
- `mrxsmb!SmbCeSwitchConnectionObjectTransport` at `0x1400136c1`
- `mrxsmb!SmbCeSwitchConnectionObjectTransport` at `0x1400136c1`

## pseudocode

```c
__int64 __fastcall MRxSmb2Close(__int64 a1)
{
  _QWORD *v1; // r13
  __int64 v2; // rsi
  __int64 v4; // rax
  __int64 v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // r15
  int v8; // eax
  __int64 v9; // rax
  PVOID *v10; // rbx
  struct _KPROCESS *RDBSSProcess; // rax
  IRP *TopLevelIrp; // rdi
  char v13; // bp
  _QWORD *v14; // r10
  _QWORD *v15; // rax
  _QWORD *v16; // rdx
  _DWORD *v17; // r8
  int v18; // ecx
  __int64 v19; // r9
  _QWORD *v20; // rax
  __int64 v21; // rdi
  unsigned int v22; // eax
  int v23; // ecx
  int v24; // ecx
  __int64 v25; // rdx
  int v26; // esi
  __int64 Timer_high; // rdx
  __int64 v28; // r8
  __int64 v29; // rbx
  __int64 v30; // rbp
  __int64 v31; // rdi
  int v32; // eax
  __int64 v33; // rcx
  struct _EX_RUNDOWN_REF *v34; // rbx
  _QWORD *Count; // r8
  void **v36; // rdx
  __int64 v37; // rbp
  __int64 v38; // rdx
  char v40; // [rsp+40h] [rbp-A8h]
  __int64 v41; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v42; // [rsp+58h] [rbp-90h]
  __int64 v43; // [rsp+60h] [rbp-88h]
  struct _KAPC_STATE ApcState; // [rsp+68h] [rbp-80h] BYREF

  v1 = *(_QWORD **)(a1 + 72);
  v2 = *(_QWORD *)(a1 + 56);
  v4 = v1[5];
  v5 = v1[6];
  v6 = *(_QWORD *)(v2 + 136);
  v42 = v5;
  v7 = *(_QWORD *)(v4 + 40);
  v43 = v7;
  v41 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqZ(
      WPP_GLOBAL_Control->AttachedDevice,
      12,
      (unsigned int)WPP_7487393bfdbf38e9a52c5915e39abd19_Traceguids,
      a1,
      (char)v1,
      v1[10]);
  }
  v40 = *(_BYTE *)(a1 + 32);
  *(_BYTE *)(a1 + 32) = 2;
  v8 = *(_DWORD *)(v5 + 8);
  if ( (v8 & 0x400) != 0 )
  {
    --*(_DWORD *)(v6 + 76);
  }
  else if ( (v8 & 0x200) != 0 )
  {
    --*(_DWORD *)(v6 + 72);
  }
  if ( (*(_DWORD *)(v2 + 156) & 1) != 0 )
  {
    Smb2InvalidateFileInfoCacheEntry(
      a1,
      (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(*(_QWORD *)(v2 + 120) + 40LL) + 376LL));
    Smb2DeleteSingleFileInDirInfoCache((_QWORD *)a1, (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v7 + 424) + 1112LL), 1);
    Smb2InvalidateFileAbeStatusCacheEntry(a1, (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v7 + 424) + 1296LL), 1);
  }
  if ( v1[8] )
  {
    v9 = *(_QWORD *)(a1 + 72);
    memset(&ApcState, 0, sizeof(ApcState));
    v10 = *(PVOID **)(v9 + 64);
    if ( v10 )
    {
      ObfDereferenceObject(*v10);
      RDBSSProcess = RxGetRDBSSProcess();
      KeStackAttachProcess(RDBSSProcess, &ApcState);
      TopLevelIrp = IoGetTopLevelIrp();
      if ( TopLevelIrp )
      {
        IoSetTopLevelIrp(0);
        ZwClose(v10[6]);
        IoSetTopLevelIrp(TopLevelIrp);
      }
      else
      {
        ZwClose(v10[6]);
      }
      KeUnstackDetachProcess(&ApcState);
      ExFreePoolWithTag(v10, 0x6D536853u);
      v5 = v42;
      *(_QWORD *)(*(_QWORD *)(a1 + 72) + 64LL) = 0;
    }
  }
  v13 = *(_BYTE *)(a1 + 504) & 1;
  if ( (*(_DWORD *)(v2 + 156) & 1) == 0
    && (unsigned __int8)Smb2ShouldUpdateFileInformationCache(a1, 4)
    && ((*(_DWORD *)(*(_QWORD *)(a1 + 72) + 72LL) & 0x800) != 0
     || *(_BYTE *)(v5 + 320)
     || (*(_DWORD *)(v2 + 164) & 1) == 0) )
  {
    v13 = 1;
  }
  if ( *(_WORD *)v2 == 0xEC21 && (*(_DWORD *)(v2 + 164) & 1) != 0 )
  {
    v14 = (_QWORD *)(v2 + 264);
    v15 = *(_QWORD **)(v2 + 264);
    if ( v15 != (_QWORD *)(v2 + 264) )
    {
      while ( 1 )
      {
        v16 = v15 - 17;
        if ( *((_WORD *)v15 - 68) != 0xEBAA )
          break;
        v15 = (_QWORD *)*v15;
        if ( v15 == v14 )
          goto LABEL_47;
      }
      if ( v15 != (_QWORD *)136 )
      {
        while ( 1 )
        {
          if ( v16 != v1 && (v16[9] & 0x604) == 0 )
          {
            v17 = (_DWORD *)v16[6];
            if ( v17 )
            {
              if ( (v17[2] & 2) == 0 )
              {
                v18 = v17[1];
                if ( v18 != 9 && v18 != 6 )
                {
                  if ( *(_WORD *)v16[4] != 0xEC21 )
                  {
                    v19 = v16[5];
LABEL_41:
                    if ( *(_QWORD *)(v19 + 40) == v7 )
                      goto LABEL_48;
                    goto LABEL_42;
                  }
                  if ( !v18 )
                  {
                    v19 = v16[5];
                    if ( v17[11] == *(_DWORD *)(*(_QWORD *)(v19 + 40) + 264LL) )
                      goto LABEL_41;
                  }
                }
              }
            }
          }
LABEL_42:
          v20 = (_QWORD *)v16[17];
          if ( v20 != v14 )
          {
            while ( 1 )
            {
              v16 = v20 - 17;
              if ( *((_WORD *)v20 - 68) != 0xEBAA )
                break;
              v20 = (_QWORD *)*v20;
              if ( v20 == v14 )
                goto LABEL_47;
            }
            if ( v20 != (_QWORD *)136 )
              continue;
          }
          break;
        }
      }
    }
LABEL_47:
    _InterlockedIncrement64((volatile signed __int64 *)(v7 + 576));
    Smb2InvalidateDirInfoCacheEx(a1, 0, (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v7 + 424) + 1112LL), 0, 0);
  }
LABEL_48:
  Smb2UpdateEffectiveOplockLevelOnClose(v2, v1);
  v21 = v1[6];
  ExAcquirePushLockExclusiveEx(v21 + 16, 0);
  v22 = *(_DWORD *)(v21 + 4);
  if ( v22 == 9 )
    goto LABEL_55;
  if ( v22 > 8 || (v23 = 344, !_bittest(&v23, v22)) )
  {
    v24 = *(_DWORD *)(v21 + 8);
    if ( (v24 & 1) != 0 || (v24 & 8) != 0 && v22 == 1 )
    {
      *(_DWORD *)(v21 + 4) = 6;
LABEL_55:
      ExReleasePushLockExclusiveEx(v21 + 16, 0);
      LOBYTE(v25) = 1;
      Smb2InvalidateSrvOpen(v1, v25);
      v26 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qZ(
          WPP_GLOBAL_Control->AttachedDevice,
          13,
          (unsigned int)WPP_7487393bfdbf38e9a52c5915e39abd19_Traceguids,
          (_DWORD)v1,
          v1[10]);
      }
      goto LABEL_73;
    }
  }
  ExReleasePushLockExclusiveEx(v21 + 16, 0);
  v26 = Smb2AttemptToCacheShareRootHandle(v1);
  if ( v26 )
  {
    v41 = 0;
    v26 = SmbCeInitializeExchange(&v41, a1, 0, 0, 0, v7, 2592, &CloseDispatch);
    if ( !v26 )
    {
      _InterlockedOr((volatile signed __int32 *)(v41 + 68), 1u);
      *(_BYTE *)(v41 + 2408) = v13;
      v26 = SmbCeInitiateExchange(v41);
      if ( v26 == 259 )
        v26 = SmbCeWaitForCompletionAndFinalizeExchangeEx(v41, 0, 0, 0);
      else
        SmbCeWaitForCompletionAndFinalizeExchangeEx(v41, 0, 0, 0);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (Timer_high & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_7487393bfdbf38e9a52c5915e39abd19_Traceguids, v1);
    }
    v29 = *(_QWORD *)(v7 + 416);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v29 + 432), 0xFFFFFFFF) == 1 )
    {
      if ( (*(_DWORD *)(*(_QWORD *)(v29 + 384) + 716LL) & 0x1000) == 0 )
        SmbCeSwitchConnectionObjectTransport(v29, Timer_high, v28);
      if ( !*(_DWORD *)(v29 + 704) )
        SmbCeSetConnectionKeepalive(v29, 0, 0);
    }
  }
LABEL_73:
  v30 = v1[6];
  v31 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 2336LL);
  ExAcquireResourceExclusiveLite((PERESOURCE)v31, 1u);
  ExAcquirePushLockExclusiveEx(v30 + 16, 0);
  v32 = *(_DWORD *)(v30 + 8);
  v33 = v30 + 16;
  if ( (v32 & 0x40) != 0 )
  {
    v34 = *(struct _EX_RUNDOWN_REF **)(v30 + 296);
    *(_DWORD *)(v30 + 8) = v32 & 0xFFFFFFBF;
    *(_QWORD *)(v30 + 296) = 0;
    ExReleasePushLockExclusiveEx(v33, 0);
    Count = (_QWORD *)v34->Count;
    if ( *(struct _EX_RUNDOWN_REF **)(v34->Count + 8) != v34 || (v36 = (void **)v34[1].Count, *v36 != v34) )
      __fastfail(3u);
    v37 = *(_QWORD *)(*(_QWORD *)(v1[5] + 40LL) + 416LL);
    *v36 = Count;
    Count[1] = v36;
    v34[1].Count = (ULONG_PTR)v34;
    v34->Count = (ULONG_PTR)v34;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_826bdefea5f439a79d7b4a7e09ca5b98_Traceguids, v1, v34);
    }
    if ( LODWORD(v34[4].Count) == *(_DWORD *)(v31 + 132) )
      --*(_DWORD *)(v31 + 120);
    else
      --*(_DWORD *)(v31 + 124);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v37 + 704), 0xFFFFFFFF) == 1 )
      SmbCeSetConnectionKeepalive(v37, 0, 2);
    ExReleaseResourceLite((PERESOURCE)v31);
    if ( v34 )
    {
      ExWaitForRundownProtectionRelease(v34 + 3);
      ExFreePoolWithTag(v34, 0x6D536946u);
    }
  }
  else
  {
    ExReleasePushLockExclusiveEx(v33, 0);
    ExReleaseResourceLite((PERESOURCE)v31);
  }
  LOBYTE(v38) = 1;
  Smb2InvalidateSrvOpen(v1, v38);
  SmbCeDecrementNtlmOpenCounts(*(_QWORD *)(v43 + 416), v42 + 329);
  if ( v26 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qDZ(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      (unsigned int)WPP_7487393bfdbf38e9a52c5915e39abd19_Traceguids,
      (_DWORD)v1,
      v26,
      v1[10]);
  }
  *(_BYTE *)(a1 + 32) = v40;
  return 0;
}

```

## disassembly

```asm
0x140013210  push    rbx
0x140013212  push    rbp
0x140013213  push    rsi
0x140013214  push    rdi
0x140013215  push    r12
0x140013217  push    r13
0x140013219  push    r14
0x14001321b  push    r15
0x14001321d  sub     rsp, 0A8h
0x140013224  mov     rax, cs:__security_cookie
0x14001322b  xor     rax, rsp
0x14001322e  mov     [rsp+0E8h+var_50], rax
0x140013236  mov     r13, [rcx+48h]
0x14001323a  xor     ebp, ebp
0x14001323c  mov     rsi, [rcx+38h]
0x140013240  mov     r12, rcx
0x140013243  mov     rax, [r13+28h]
0x140013247  mov     rdi, [r13+30h]
0x14001324b  mov     rbx, [rsi+88h]
0x140013252  mov     [rsp+0E8h+var_90], rdi
0x140013257  mov     r15, [rax+28h]
0x14001325b  mov     [rsp+0E8h+var_88], r15
0x140013260  mov     [rsp+0E8h+var_A0], rbp
0x140013265  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001326c  lea     rax, WPP_GLOBAL_Control
0x140013273  cmp     rcx, rax
0x140013276  jz      short loc_1400132AB
0x140013278  mov     eax, [rcx+2Ch]
0x14001327b  test    al, 20h
0x14001327d  jz      short loc_1400132AB
0x14001327f  cmp     byte ptr [rcx+29h], 2
0x140013283  jb      short loc_1400132AB
0x140013285  mov     rax, [r13+50h]
0x140013289  lea     r8, WPP_7487393bfdbf38e9a52c5915e39abd19_Traceguids
0x140013290  mov     rcx, [rcx+18h]
0x140013294  mov     edx, 0Ch
0x140013299  mov     [rsp+0E8h+var_C0], rax
0x14001329e  mov     r9, r12
0x1400132a1  mov     [rsp+0E8h+var_C8], r13
0x1400132a6  call    WPP_SF_qqZ
0x1400132ab  movzx   eax, byte ptr [r12+20h]
0x1400132b1  mov     [rsp+0E8h+var_A8], al
0x1400132b5  mov     byte ptr [r12+20h], 2
0x1400132bb  mov     eax, [rdi+8]
0x1400132be  bt      eax, 0Ah
0x1400132c2  jnb     short loc_1400132C9
0x1400132c4  dec     dword ptr [rbx+4Ch]
0x1400132c7  jmp     short loc_1400132D2
0x1400132c9  bt      eax, 9
0x1400132cd  jnb     short loc_1400132D2
0x1400132cf  dec     dword ptr [rbx+48h]
0x1400132d2  mov     eax, [rsi+9Ch]
0x1400132d8  test    al, 1
0x1400132da  jz      short loc_140013325
0x1400132dc  mov     rax, [rsi+78h]
0x1400132e0  mov     rcx, r12
0x1400132e3  mov     rdx, [rax+28h]
0x1400132e7  add     rdx, 178h
0x1400132ee  call    Smb2InvalidateFileInfoCacheEntry
0x1400132f3  mov     rdx, [r15+1A8h]
0x1400132fa  mov     r8b, 1
0x1400132fd  add     rdx, 458h
0x140013304  mov     rcx, r12
0x140013307  call    Smb2DeleteSingleFileInDirInfoCache
0x14001330c  mov     rdx, [r15+1A8h]
0x140013313  mov     r8b, 1
0x140013316  add     rdx, 510h
0x14001331d  mov     rcx, r12
0x140013320  call    Smb2InvalidateFileAbeStatusCacheEntry
0x140013325  cmp     [r13+40h], rbp
0x140013329  jz      loc_14001340B
0x14001332f  mov     rax, [r12+48h]
0x140013334  xorps   xmm0, xmm0
0x140013337  movups  xmmword ptr [rsp+0E8h+ApcState.ApcListHead.Flink], xmm0
0x14001333c  movups  xmmword ptr [rsp+0E8h+ApcState.ApcListHead.Flink+10h], xmm0
0x140013341  movups  xmmword ptr [rsp+0E8h+ApcState.Process], xmm0
0x140013349  mov     rbx, [rax+40h]
0x14001334d  test    rbx, rbx
0x140013350  jz      loc_14001340B
0x140013356  mov     rcx, [rbx]; Object
0x140013359  call    cs:__imp_ObfDereferenceObject
0x140013360  nop     dword ptr [rax+rax+00h]
0x140013365  call    cs:__imp_RxGetRDBSSProcess
0x14001336c  nop     dword ptr [rax+rax+00h]
0x140013371  mov     rcx, rax; PROCESS
0x140013374  lea     rdx, [rsp+0E8h+ApcState]; ApcState
0x140013379  call    cs:__imp_KeStackAttachProcess
0x140013380  nop     dword ptr [rax+rax+00h]
0x140013385  call    cs:__imp_IoGetTopLevelIrp
0x14001338c  nop     dword ptr [rax+rax+00h]
0x140013391  mov     rdi, rax
0x140013394  test    rax, rax
0x140013397  jz      short loc_1400133C8
0x140013399  xor     ecx, ecx; Irp
0x14001339b  call    cs:__imp_IoSetTopLevelIrp
0x1400133a2  nop     dword ptr [rax+rax+00h]
0x1400133a7  mov     rcx, [rbx+30h]; Handle
0x1400133ab  call    cs:__imp_ZwClose
0x1400133b2  nop     dword ptr [rax+rax+00h]
0x1400133b7  mov     rcx, rdi; Irp
0x1400133ba  call    cs:__imp_IoSetTopLevelIrp
0x1400133c1  nop     dword ptr [rax+rax+00h]
0x1400133c6  jmp     short loc_1400133D8
0x1400133c8  mov     rcx, [rbx+30h]; Handle
0x1400133cc  call    cs:__imp_ZwClose
0x1400133d3  nop     dword ptr [rax+rax+00h]
0x1400133d8  lea     rcx, [rsp+0E8h+ApcState]; ApcState
0x1400133dd  call    cs:__imp_KeUnstackDetachProcess
0x1400133e4  nop     dword ptr [rax+rax+00h]
0x1400133e9  mov     edx, 6D536853h; Tag
0x1400133ee  mov     rcx, rbx; P
0x1400133f1  call    cs:__imp_ExFreePoolWithTag
0x1400133f8  nop     dword ptr [rax+rax+00h]
0x1400133fd  mov     rax, [r12+48h]
0x140013402  mov     rdi, [rsp+0E8h+var_90]
0x140013407  mov     [rax+40h], rbp
0x14001340b  movzx   ebp, byte ptr [r12+1F8h]
0x140013414  mov     eax, [rsi+9Ch]
0x14001341a  and     bpl, 1
0x14001341e  test    al, 1
0x140013420  jnz     short loc_140013457
0x140013422  mov     edx, 4
0x140013427  mov     rcx, r12
0x14001342a  call    Smb2ShouldUpdateFileInformationCache
0x14001342f  test    al, al
0x140013431  jz      short loc_140013457
0x140013433  mov     rax, [r12+48h]
0x140013438  test    dword ptr [rax+48h], 800h
0x14001343f  jnz     short loc_140013454
0x140013441  cmp     byte ptr [rdi+140h], 0
0x140013448  jnz     short loc_140013454
0x14001344a  mov     eax, [rsi+0A4h]
0x140013450  test    al, 1
0x140013452  jnz     short loc_140013457
0x140013454  mov     bpl, 1
0x140013457  mov     ebx, 0EC21h
0x14001345c  cmp     [rsi], bx
0x14001345f  jnz     loc_140013568
0x140013465  mov     eax, [rsi+0A4h]
0x14001346b  test    al, 1
0x14001346d  jz      loc_140013568
0x140013473  lea     r10, [rsi+108h]
0x14001347a  mov     rax, [r10]
0x14001347d  cmp     rax, r10
0x140013480  jz      loc_140013540
0x140013486  mov     r11d, 0EBAAh
0x14001348c  nop     dword ptr [rax+00h]
0x140013490  lea     rdx, [rax-88h]
0x140013497  cmp     [rdx], r11w
0x14001349b  jnz     short loc_1400134AA
0x14001349d  mov     rax, [rax]
0x1400134a0  cmp     rax, r10
0x1400134a3  jnz     short loc_140013490
0x1400134a5  jmp     loc_140013540
0x1400134aa  test    rdx, rdx
0x1400134ad  jz      loc_140013540
0x1400134b3  cmp     rdx, r13
0x1400134b6  jz      short loc_14001350D
0x1400134b8  test    dword ptr [rdx+48h], 604h
0x1400134bf  jnz     short loc_14001350D
0x1400134c1  mov     r8, [rdx+30h]
0x1400134c5  test    r8, r8
0x1400134c8  jz      short loc_14001350D
0x1400134ca  mov     eax, [r8+8]
0x1400134ce  test    al, 2
0x1400134d0  jnz     short loc_14001350D
0x1400134d2  mov     ecx, [r8+4]
0x1400134d6  cmp     ecx, 9
0x1400134d9  jz      short loc_14001350D
0x1400134db  cmp     ecx, 6
0x1400134de  jz      short loc_14001350D
0x1400134e0  mov     rax, [rdx+20h]
0x1400134e4  cmp     [rax], bx
0x1400134e7  jnz     short loc_140013503
0x1400134e9  test    ecx, ecx
0x1400134eb  jnz     short loc_14001350D
0x1400134ed  mov     r9, [rdx+28h]
0x1400134f1  mov     rax, [r9+28h]
0x1400134f5  mov     ecx, [rax+108h]
0x1400134fb  cmp     [r8+2Ch], ecx
0x1400134ff  jnz     short loc_14001350D
0x140013501  jmp     short loc_140013507
0x140013503  mov     r9, [rdx+28h]
0x140013507  cmp     [r9+28h], r15
0x14001350b  jz      short loc_140013568
0x14001350d  mov     rax, [rdx+88h]
0x140013514  cmp     rax, r10
0x140013517  jz      short loc_140013540
0x140013519  nop     dword ptr [rax+00000000h]
0x140013520  lea     rdx, [rax-88h]
0x140013527  cmp     [rdx], r11w
0x14001352b  jnz     short loc_140013537
0x14001352d  mov     rax, [rax]
0x140013530  cmp     rax, r10
0x140013533  jnz     short loc_140013520
0x140013535  jmp     short loc_140013540
0x140013537  test    rdx, rdx
0x14001353a  jnz     loc_1400134B3
0x140013540  lock inc qword ptr [r15+240h]
0x140013548  mov     r8, [r15+1A8h]
0x14001354f  xor     r9d, r9d
0x140013552  add     r8, 458h
0x140013559  mov     byte ptr [rsp+0E8h+var_C8], 0
0x14001355e  xor     edx, edx
0x140013560  mov     rcx, r12
0x140013563  call    Smb2InvalidateDirInfoCacheEx
0x140013568  mov     rdx, r13
0x14001356b  mov     rcx, rsi
0x14001356e  call    Smb2UpdateEffectiveOplockLevelOnClose
0x140013573  mov     rdi, [r13+30h]
0x140013577  xor     edx, edx
0x140013579  lea     rcx, [rdi+10h]
0x14001357d  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140013584  nop     dword ptr [rax+rax+00h]
0x140013589  mov     eax, [rdi+4]
0x14001358c  mov     r14d, 0FFFFFFFFh
0x140013592  cmp     eax, 9
0x140013595  jz      short loc_1400135C3
0x140013597  cmp     eax, 8
0x14001359a  ja      short loc_1400135AA
0x14001359c  mov     ecx, 158h
0x1400135a1  bt      ecx, eax
0x1400135a4  jb      loc_140013633
0x1400135aa  mov     ecx, [rdi+8]
0x1400135ad  test    cl, 1
0x1400135b0  jnz     short loc_1400135BC
0x1400135b2  test    cl, 8
0x1400135b5  jz      short loc_140013633
0x1400135b7  cmp     eax, 1
0x1400135ba  jnz     short loc_140013633
0x1400135bc  mov     dword ptr [rdi+4], 6
0x1400135c3  xor     edx, edx
0x1400135c5  lea     rcx, [rdi+10h]
0x1400135c9  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400135d0  nop     dword ptr [rax+rax+00h]
0x1400135d5  mov     dl, 1
0x1400135d7  mov     rcx, r13
0x1400135da  call    Smb2InvalidateSrvOpen
0x1400135df  xor     esi, esi
0x1400135e1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400135e8  lea     rax, WPP_GLOBAL_Control
0x1400135ef  cmp     rcx, rax
0x1400135f2  jz      loc_140013791
0x1400135f8  mov     eax, [rcx+2Ch]
0x1400135fb  test    al, 20h
0x1400135fd  jz      loc_140013791
0x140013603  cmp     byte ptr [rcx+29h], 2
0x140013607  jb      loc_140013791
0x14001360d  mov     rax, [r13+50h]
0x140013611  lea     r8, WPP_7487393bfdbf38e9a52c5915e39abd19_Traceguids
0x140013618  mov     rcx, [rcx+18h]
0x14001361c  mov     edx, 0Dh
0x140013621  mov     r9, r13
0x140013624  mov     [rsp+0E8h+var_C8], rax
0x140013629  call    WPP_SF_qZ
0x14001362e  jmp     loc_140013791
0x140013633  xor     edx, edx
0x140013635  lea     rcx, [rdi+10h]
0x140013639  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140013640  nop     dword ptr [rax+rax+00h]
0x140013645  mov     rcx, r13
0x140013648  call    Smb2AttemptToCacheShareRootHandle
0x14001364d  mov     esi, eax
0x14001364f  test    eax, eax
0x140013651  jnz     loc_1400136F3
0x140013657  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001365e  lea     rax, WPP_GLOBAL_Control
0x140013665  cmp     rcx, rax
0x140013668  jz      short loc_140013690
0x14001366a  mov     edx, [rcx+2Ch]
0x14001366d  test    dl, 20h
0x140013670  jz      short loc_140013690
0x140013672  cmp     byte ptr [rcx+29h], 2
0x140013676  jb      short loc_140013690
0x140013678  mov     rcx, [rcx+18h]
0x14001367c  lea     r8, WPP_7487393bfdbf38e9a52c5915e39abd19_Traceguids
0x140013683  mov     edx, 0Eh
0x140013688  mov     r9, r13
0x14001368b  call    WPP_SF_q
0x140013690  mov     rbx, [r15+1A0h]
0x140013697  mov     eax, r14d
0x14001369a  lock xadd [rbx+1B0h], eax
0x1400136a2  cmp     eax, 1
0x1400136a5  jnz     loc_140013791
0x1400136ab  mov     rax, [rbx+180h]
0x1400136b2  test    dword ptr [rax+2CCh], 1000h
0x1400136bc  jnz     short loc_1400136CD
0x1400136be  mov     rcx, rbx
0x1400136c1  call    cs:__imp_SmbCeSwitchConnectionObjectTransport
0x1400136c8  nop     dword ptr [rax+rax+00h]
0x1400136cd  cmp     dword ptr [rbx+2C0h], 0
0x1400136d4  jnz     loc_140013791
0x1400136da  xor     r8d, r8d
0x1400136dd  xor     edx, edx
0x1400136df  mov     rcx, rbx
0x1400136e2  call    cs:__imp_SmbCeSetConnectionKeepalive
0x1400136e9  nop     dword ptr [rax+rax+00h]
0x1400136ee  jmp     loc_140013791
0x1400136f3  xor     ecx, ecx
0x1400136f5  lea     rax, CloseDispatch
  ... truncated ...
```
