# FltpPerformPreCallbacksWorker

- ea: `0x1800047e0`
- end: `0x18000544f`
- name: `FltpPerformPreCallbacksWorker`
- size: `3183`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003b10`
- `0x180004710`

## callees

- `0x1800031e0`
- `0x1800047e0`
- `0x180009a00`
- `0x180009f20`
- `0x180009f80`
- `0x18000f5b0`
- `0x180011d10`
- `0x180013fa0`
- `0x1800143a0`
- `0x180015db0`
- `0x180017610`
- `0x180017a30`
- `0x180019690`
- `0x180019800`
- `0x18001cd80`
- `0x18001f4c0`
- `0x1800248e0`
- `0x180060520`
- `0x180060930`
- `0x18006ba60`

## import_xrefs

- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x180004872`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1800051e6`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x180004872`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1800051e6`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180004861`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1800051d5`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180004861`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1800051d5`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1800048c6`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1800051a1`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x18000520c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x180005246`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x18000528b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1800052b5`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1800052e5`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x180005390`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1800048c6`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1800051a1`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x18000520c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x180005246`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x18000528b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1800052b5`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1800052e5`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x180005390`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1800049cf`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1800049cf`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1800049fd`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1800053c5`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1800049fd`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1800053c5`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1800049f1`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1800053b9`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1800049f1`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1800053b9`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x180004a3a`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x180004a3a`
- `HAL!KeQueryPerformanceCounter` at `0x180004e14`
- `HAL!KeQueryPerformanceCounter` at `0x180004e14`

## pseudocode

```c
__int64 __fastcall FltpPerformPreCallbacksWorker(__int64 a1)
{
  __int64 v1; // rdi
  unsigned int v2; // esi
  char v3; // r15
  __int64 v5; // r13
  __int64 v6; // rax
  PVOID *v7; // rax
  _QWORD *v8; // r12
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rbx
  unsigned int v13; // ecx
  _QWORD *v14; // r14
  int v15; // eax
  int v16; // edx
  int v17; // r8d
  __int64 v18; // r12
  int v19; // eax
  __int64 v20; // rax
  _QWORD *v21; // rbx
  struct _FILE_OBJECT *v22; // rax
  PTXN_PARAMETER_BLOCK TransactionParameterBlock; // rdx
  unsigned __int64 *v24; // r13
  __int64 v25; // rax
  __int64 v26; // rcx
  unsigned __int64 v27; // rdx
  unsigned __int8 v28; // r8
  unsigned __int64 v29; // rdx
  __int64 v30; // rax
  PVOID v31; // r10
  unsigned __int64 v32; // rcx
  __int64 v33; // rax
  unsigned __int64 v34; // r15
  unsigned __int8 v35; // dl
  __int64 v36; // rax
  __int64 v37; // rax
  bool v38; // zf
  int v39; // r12d
  __int64 v40; // rbx
  unsigned __int64 v41; // rcx
  __int64 v42; // rax
  unsigned int v43; // ebx
  __int64 v44; // rcx
  _DWORD *v45; // r8
  int v46; // edx
  int v47; // edx
  void (__fastcall *v48)(_OWORD *, __int64, __int64, __int64); // r10
  int v49; // ecx
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // r9
  unsigned int v53; // eax
  __int64 v54; // r8
  unsigned int v55; // ebx
  const char *v56; // rax
  __int64 v57; // rax
  __int64 v58; // r8
  char v59; // al
  __int64 v60; // rdx
  int v61; // ecx
  _BYTE *v62; // rax
  _DWORD *v63; // rax
  char v64; // al
  char v65; // cl
  int v66; // ecx
  unsigned __int64 v67; // rbx
  int v68; // ecx
  int v69; // ecx
  char v70; // al
  __int64 v71; // rbx
  __int64 v72; // r8
  __int64 v73; // rcx
  ULONG v74; // ebx
  int v75; // eax
  __int64 v76; // rax
  __int64 v78; // rdx
  __int64 NextCallbackNodeForInstance; // [rsp+40h] [rbp-C0h]
  unsigned int v80; // [rsp+48h] [rbp-B8h] BYREF
  PVOID OwnerId; // [rsp+50h] [rbp-B0h]
  unsigned int v82; // [rsp+58h] [rbp-A8h] BYREF
  int v83; // [rsp+5Ch] [rbp-A4h]
  int v84; // [rsp+60h] [rbp-A0h]
  __int64 v85; // [rsp+68h] [rbp-98h]
  __int64 v86; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v87; // [rsp+78h] [rbp-88h] BYREF
  struct _FILE_OBJECT *v88; // [rsp+80h] [rbp-80h]
  __int64 v89; // [rsp+88h] [rbp-78h]
  __int64 v90; // [rsp+90h] [rbp-70h]
  __int128 v91; // [rsp+98h] [rbp-68h] BYREF
  __int128 v92; // [rsp+A8h] [rbp-58h]
  __int128 v93; // [rsp+B8h] [rbp-48h]
  __int64 v94; // [rsp+C8h] [rbp-38h]
  _OWORD v95[7]; // [rsp+D0h] [rbp-30h] BYREF
  char v97; // [rsp+158h] [rbp+58h] BYREF
  unsigned __int8 v98; // [rsp+160h] [rbp+60h]
  unsigned int v99; // [rsp+168h] [rbp+68h]

  v1 = *(_QWORD *)(a1 + 16);
  v2 = 0;
  v86 = 0;
  v91 = 0;
  v3 = 0;
  v92 = 0;
  v5 = v1 + 232;
  v80 = 0;
  v93 = 0;
  v98 = *(_BYTE *)(*(_QWORD *)(v1 + 248) + 4LL);
  v99 = (unsigned __int8)(v98 + 22);
  v6 = *(_QWORD *)(a1 + 24);
  if ( v6 == -1 )
    v7 = (PVOID *)a1;
  else
    v7 = (PVOID *)(*(_QWORD *)(v6 + 16) + 64LL);
  v8 = *v7;
  v9 = qword_18003EF20;
  OwnerId = *v7;
  KeEnterGuardedRegion();
  v10 = ExAcquireCacheAwarePushLockSharedEx(v9, 0);
  v11 = *(_QWORD *)(a1 + 24);
  v12 = v10;
  if ( v11 == -1 )
  {
    v13 = v99;
    v14 = (_QWORD *)v8[2 * v99 + 40];
    NextCallbackNodeForInstance = (__int64)v14;
  }
  else
  {
    v15 = *(_DWORD *)(a1 + 40);
    if ( (v15 & 1) != 0 )
      v14 = *(_QWORD **)v11;
    else
      v14 = *(_QWORD **)(a1 + 24);
    NextCallbackNodeForInstance = (__int64)v14;
    if ( (v15 & 2) == 0 )
      ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v11 + 16) + 56LL), 1u);
    v13 = v99;
  }
  v97 = 0;
  v94 = 16 * (v13 + 20LL);
  if ( v14 == &v8[(unsigned __int64)v94 / 8] )
  {
    OwnerId = v8;
LABEL_177:
    ExReleaseCacheAwarePushLockSharedEx(v12, 0);
    KeLeaveGuardedRegion();
    v24 = (unsigned __int64 *)(v1 + 128);
    goto LABEL_178;
  }
  v89 = 0;
  v90 = 0;
  v17 = **(_DWORD **)(v1 + 248);
  v16 = v17 & 2;
  LOBYTE(v17) = v17 & 1;
  v83 = v16;
  v84 = v17;
  while ( 1 )
  {
    v18 = v14[2];
    v85 = v18;
    if ( (*(_DWORD *)(v18 + 80) & 2) == 0 )
      break;
    v14 = (_QWORD *)*v14;
    NextCallbackNodeForInstance = (__int64)v14;
LABEL_161:
    if ( v14 == (_QWORD *)((char *)OwnerId + v94) )
      goto LABEL_177;
  }
  if ( (unsigned __int8)(*(_BYTE *)(*(_QWORD *)(v5 + 16) + 4LL) - 3) <= 1u )
  {
    v19 = *((_DWORD *)v14 + 10);
    if ( v16 && (v19 & 1) != 0 )
    {
LABEL_27:
      v14 = (_QWORD *)*v14;
      NextCallbackNodeForInstance = (__int64)v14;
      goto LABEL_161;
    }
    if ( (_BYTE)v17 )
    {
      if ( !v16 && (v19 & 0x10) != 0 )
        goto LABEL_27;
    }
    else if ( (v19 & 2) != 0 )
    {
      goto LABEL_27;
    }
  }
  v20 = *(_QWORD *)(v1 + 112);
  if ( v20 && (*(_DWORD *)(v20 + 80) & 0x400000) == 0 && (v14[5] & 8) != 0 )
  {
    v14 = (_QWORD *)*v14;
    NextCallbackNodeForInstance = (__int64)v14;
    goto LABEL_161;
  }
  if ( (*(_DWORD *)(a1 + 40) & 0x10) != 0 && (*(_DWORD *)(*(_QWORD *)(v18 + 72) + 96LL) & 4) == 0 )
  {
    v14 = (_QWORD *)*v14;
    NextCallbackNodeForInstance = (__int64)v14;
    goto LABEL_161;
  }
  if ( !ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v18 + 56), 2u) )
  {
    v14 = (_QWORD *)*v14;
    NextCallbackNodeForInstance = (__int64)v14;
LABEL_160:
    v16 = v83;
    LOBYTE(v17) = v84;
    goto LABEL_161;
  }
  ExReleaseCacheAwarePushLockSharedEx(v12, 0);
  KeLeaveGuardedRegion();
  v21 = (_QWORD *)(v1 + 112);
  *(_QWORD *)(*(_QWORD *)(v5 + 16) + 16LL) = v18;
  *(_QWORD *)(*(_QWORD *)(v5 + 16) + 8LL) = *(_QWORD *)(v1 + 112);
  v22 = *(struct _FILE_OBJECT **)(v1 + 112);
  v88 = v22;
  if ( v22 && *((_DWORD *)OwnerId + 15) == 2 )
    TransactionParameterBlock = IoGetTransactionParameterBlock(v22);
  else
    TransactionParameterBlock = 0;
  v24 = (unsigned __int64 *)(v1 + 128);
  v25 = *(_QWORD *)(v1 + 128);
  if ( v25 )
  {
    v26 = *(_QWORD *)(v25 + 64);
    *(_QWORD *)(v25 + 64) = v18;
    *(_QWORD *)(*v24 + 64) = v26;
  }
  if ( !v14[3] )
  {
    v27 = *v24;
    if ( *v24 )
    {
      *v24 = 0;
      *(_QWORD *)(v27 + 64) = v18;
      v5 = v1 + 232;
      *(_QWORD *)(v27 + 8) = v14;
      FltpLinkCompletionNodeToInstance(v18, v27);
    }
    else
    {
      v28 = *(_BYTE *)(v1 + 15);
      if ( v28 >= *(_BYTE *)(v1 + 14) )
      {
        v29 = FltpExtendIrpCtrl(v1);
      }
      else
      {
        v29 = *(_QWORD *)(v1 + 16) + ((unsigned __int64)*(unsigned __int8 *)(v1 + 15) << 7);
        *(_BYTE *)(v1 + 15) = v28 + 1;
        *(_QWORD *)v29 = v1;
      }
      if ( !v29 )
      {
        *(_DWORD *)(v1 + 256) = -1073741670;
        v2 = 1835009;
        ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v18 + 56), 2u);
        goto LABEL_179;
      }
      v5 = v1 + 232;
      *(_WORD *)(v29 + 120) = 0;
      v30 = *(_QWORD *)(v1 + 248);
      *(_OWORD *)(v29 + 48) = *(_OWORD *)v30;
      *(_OWORD *)(v29 + 64) = *(_OWORD *)(v30 + 16);
      *(_OWORD *)(v29 + 80) = *(_OWORD *)(v30 + 32);
      *(_OWORD *)(v29 + 96) = *(_OWORD *)(v30 + 48);
      *(_QWORD *)(v29 + 112) = *(_QWORD *)(v30 + 64);
      *(_QWORD *)(v29 + 8) = v14;
      FltpLinkCompletionNodeToInstance(v18, v29);
    }
    goto LABEL_154;
  }
  v31 = OwnerId;
  LOWORD(v91) = 48;
  *((_QWORD *)&v91 + 1) = *(_QWORD *)(v18 + 72);
  *(_QWORD *)&v92 = OwnerId;
  *((_QWORD *)&v92 + 1) = v18;
  *(_QWORD *)&v93 = *v21;
  if ( TransactionParameterBlock )
  {
    *((_QWORD *)&v93 + 1) = TransactionParameterBlock->TransactionObject;
    WORD1(v91) = TransactionParameterBlock->TxFsContext;
  }
  else
  {
    *((_QWORD *)&v93 + 1) = 0;
    WORD1(v91) = 0;
  }
  if ( v14[4]
    || (*(_DWORD *)(*(_QWORD *)(v14[2] + 72LL) + 96LL) & 4) != 0
    && *(_BYTE *)(v1 + 12) == 6
    && (v32 = (unsigned int)(*(_DWORD *)(*(_QWORD *)(v1 + 248) + 32LL) - 10), (unsigned int)v32 <= 0x3E)
    && (v33 = 0x4080000040000003LL, _bittest64(&v33, v32))
    || (*(_DWORD *)(v1 + 4) & 0x400) != 0 )
  {
    v34 = *v24;
    if ( *v24 )
    {
      *v24 = 0;
      *(_QWORD *)(v34 + 64) = v18;
      v87 = v34;
    }
    else
    {
      v35 = *(_BYTE *)(v1 + 15);
      if ( v35 >= *(_BYTE *)(v1 + 14) )
      {
        v36 = FltpExtendIrpCtrl(v1);
        v31 = OwnerId;
        v34 = v36;
      }
      else
      {
        v34 = *(_QWORD *)(v1 + 16) + ((unsigned __int64)*(unsigned __int8 *)(v1 + 15) << 7);
        *(_BYTE *)(v1 + 15) = v35 + 1;
        *(_QWORD *)v34 = v1;
      }
      v87 = v34;
      if ( !v34 )
      {
        *(_DWORD *)(v1 + 256) = -1073741670;
        v2 = 1835009;
        ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v18 + 56), 2u);
        v3 = 0;
        goto LABEL_179;
      }
      *(_WORD *)(v34 + 120) = 0;
      v37 = *(_QWORD *)(v1 + 248);
      *(_OWORD *)(v34 + 48) = *(_OWORD *)v37;
      *(_OWORD *)(v34 + 64) = *(_OWORD *)(v37 + 16);
      *(_OWORD *)(v34 + 80) = *(_OWORD *)(v37 + 32);
      *(_OWORD *)(v34 + 96) = *(_OWORD *)(v37 + 48);
      *(_QWORD *)(v34 + 112) = *(_QWORD *)(v37 + 64);
    }
    *(_QWORD *)(v34 + 8) = v14;
  }
  else
  {
    LODWORD(v34) = 0;
    v87 = 0;
  }
  v38 = v98 == 2;
  v39 = *(_DWORD *)(v1 + 4);
  *(_QWORD *)(v1 + 80) = v14;
  v86 = 0;
  if ( v38 && !*(_QWORD *)(v1 + 160) )
    FltpGetStreamListCtrl(v31);
  v40 = v85;
  if ( (*(_DWORD *)(*(_QWORD *)(v85 + 72) + 96LL) & 4) != 0 && *(_BYTE *)(v1 + 12) == 6 )
  {
    v41 = (unsigned int)(*(_DWORD *)(*(_QWORD *)(v1 + 248) + 32LL) - 10);
    if ( (unsigned int)v41 <= 0x3E )
    {
      v42 = 0x4080000040000003LL;
      if ( _bittest64(&v42, v41) )
      {
        v80 = FltpInvalidateNameCachingAllFrames(*(PVOID *)(v85 + 64));
        v43 = v80;
        if ( (int)FltpDbgStatus(v80, "minkernel\\fs\\filtermgr\\filter\\callbacksup.c", 1834, 0) < 0 )
        {
          --*(_BYTE *)(v1 + 15);
          v73 = v85;
          v2 = 1835009;
          *(_DWORD *)(v1 + 256) = v43;
          ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v73 + 56), 2u);
          v3 = 0;
          v21 = (_QWORD *)(v1 + 112);
          goto LABEL_179;
        }
        v40 = v85;
      }
    }
  }
  v44 = *(_QWORD *)(qword_180040318 + 24);
  if ( v44 || *(_QWORD *)(qword_180040318 + 32) || *(_QWORD *)(qword_180040318 + 16) )
  {
    v45 = (_DWORD *)(v1 + 232);
    v46 = *(_DWORD *)(v1 + 232);
    memset(v95, 0, 44);
    v47 = v46 & 1;
    if ( !v47 )
      v44 = *(_QWORD *)(qword_180040318 + 32);
    if ( v44 )
    {
      (*(void (__fastcall **)(__int64, _QWORD))qword_180040318)(v1 + 192, ((v47 ^ 1u) + 2049) << 20);
      v45 = (_DWORD *)(v1 + 232);
    }
    v48 = *(void (__fastcall **)(_OWORD *, __int64, __int64, __int64))(qword_180040318 + 16);
    if ( v48 && (*v45 & 1) != 0 )
    {
      v49 = *v45 & 0x80000;
      if ( v49 )
        v50 = v14[4];
      else
        v50 = v14[3];
      *(_QWORD *)&v95[0] = v50;
      v52 = v49 != 0;
      DWORD2(v95[2]) = *(unsigned __int8 *)(v1 + 12);
      v51 = *(_QWORD *)(v1 + 112);
      LOWORD(v52) = v52 + 1120;
      *((_QWORD *)&v95[0] + 1) = v51;
      if ( v51 )
        *(_QWORD *)&v95[1] = *(_QWORD *)(v51 + 24);
      *((_QWORD *)&v95[1] + 1) = *(_QWORD *)(v1 + 48);
      *(_QWORD *)&v95[2] = v45;
      v48(v95, 44, 2148007936LL, v52);
    }
  }
  if ( *(_DWORD *)(v40 + 708) >= *(_DWORD *)(v40 + 712) )
  {
    *(_DWORD *)(v40 + 708) = 0;
    *(LARGE_INTEGER *)(v1 + 392) = KeQueryPerformanceCounter(0);
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)(v40 + 708));
    *(_QWORD *)(v1 + 392) = 0;
  }
  v53 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64 *))(NextCallbackNodeForInstance + 24))(
          v1 + 232,
          &v91,
          &v86);
  v82 = v53;
  v55 = v53;
  if ( v53 == 2 )
  {
    v14 = (_QWORD *)NextCallbackNodeForInstance;
    if ( (byte_180040A41 & 0x10) != 0 )
    {
      v56 = "SYNC";
      if ( (v39 & 8) == 0 )
        v56 = "NotSYNC";
      McTemplateU0sdpps_EtwWriteTransfer(
        (unsigned int)"NotSYNC",
        (unsigned int)CallbackSup_c1887,
        (unsigned int)"FltpPerformPreCallbacksWorker",
        v98,
        v1,
        NextCallbackNodeForInstance,
        (__int64)v56);
    }
    if ( (v39 & 8) == 0 )
      return 259;
    FltpCancellableWaitForIo((PVOID)(v1 + 24), *(PIRP *)(v1 + 48));
    v55 = *(_DWORD *)(v1 + 136);
    v86 = *(_QWORD *)(v1 + 120);
    v82 = v55;
  }
  else
  {
    if ( v53 != 1 && *(_QWORD *)(v1 + 392) )
      FltpIoPerfBucketizeIo(v1, v85, v53, 0);
    if ( *(_QWORD *)(qword_180040318 + 24) || *(_QWORD *)(qword_180040318 + 32) )
    {
      v14 = (_QWORD *)NextCallbackNodeForInstance;
      LOBYTE(v54) = 1;
      FltpPerfTraceOperationCallback(v1, NextCallbackNodeForInstance, v54);
    }
    else
    {
      v14 = (_QWORD *)NextCallbackNodeForInstance;
    }
  }
  v18 = v85;
  if ( *(int *)(v1 + 232) < 0 )
  {
    v57 = FltpProcessDirtyData(v1, v85, v34, (unsigned int)&v97, (__int64)&v82);
    v55 = v82;
    v89 = v57;
  }
  if ( (unsigned __int8)FltpHandlePreCallbackReturnStatus(
                          v1,
                          v14[4],
                          (unsigned int)&v87,
                          (int)v1 + 128,
                          v55,
                          v86,
                          (__int64)&v80) )
  {
    v5 = v1 + 232;
    *(_DWORD *)(v1 + 232) &= ~0x80000000;
    if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 104) + 64LL) + 80LL) + 56LL) & 0x100) != 0 )
    {
      v59 = *(_BYTE *)(v1 + 12);
      if ( v59 == 6 )
      {
        v60 = *(_QWORD *)(v1 + 248);
        v61 = *(_DWORD *)(v60 + 32);
        if ( (unsigned int)(v61 - 19) <= 1 || v61 == 39 )
          goto LABEL_144;
        if ( v61 == 13 )
        {
          v62 = *(_BYTE **)(v60 + 56);
          if ( !v62 || !*v62 )
            goto LABEL_126;
LABEL_144:
          v70 = *(_BYTE *)(v1 + 12);
          *(_DWORD *)(v1 + 4) |= 0x400u;
          v66 = *(_DWORD *)(v1 + 4);
          if ( (*((_BYTE *)FltpOperationFlags + (unsigned __int8)(v70 + 22)) & 2) != 0
            && (v88 != *(struct _FILE_OBJECT **)(v1 + 112) || v97 || *(_QWORD *)(*(_QWORD *)(v18 + 72) + 384LL)) )
          {
            FltpSaveFileObjectFileName(v1);
LABEL_130:
            v66 = *(_DWORD *)(v1 + 4);
          }
          v67 = v87;
          if ( (v66 & 0x10) != 0 )
          {
            if ( v88 == *(struct _FILE_OBJECT **)(v1 + 112) )
            {
              FltpReinstateNameCachingAllFrames(*(PVOID *)(v18 + 64), v1);
            }
            else
            {
              *(_WORD *)(v87 + 120) |= 0x80u;
              *(_DWORD *)(v1 + 4) &= ~0x10u;
            }
          }
          if ( v67 )
            FltpLinkCompletionNodeToInstance(v18, v67);
          else
            ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v18 + 56), 1u);
          v2 = v80;
          v3 = 0;
LABEL_154:
          if ( v97 )
          {
            v90 = v18;
            v18 = v89;
            OwnerId = *(PVOID *)(v89 + 64);
          }
          v71 = qword_18003EF20;
          KeEnterGuardedRegion();
          v12 = ExAcquireCacheAwarePushLockSharedEx(v71, 0);
          if ( v97 )
          {
            v97 = 0;
            ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v90 + 56), 1u);
            LOBYTE(v72) = 1;
            NextCallbackNodeForInstance = FltpGetNextCallbackNodeForInstance(v18, v99, v72);
            v14 = (_QWORD *)NextCallbackNodeForInstance;
            if ( !NextCallbackNodeForInstance )
              goto LABEL_177;
          }
          else
          {
            v14 = (_QWORD *)*v14;
            NextCallbackNodeForInstance = (__int64)v14;
            ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v18 + 56), 1u);
          }
          goto LABEL_160;
        }
        if ( v61 == 64 )
        {
          v63 = *(_DWORD **)(v60 + 56);
          if ( v63 )
          {
            if ( (*v63 & 1) != 0 )
              goto LABEL_144;
          }
        }
      }
      else if ( v59 == 4
             && ((**(_DWORD **)(v1 + 248) & 1) != 0
              || (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 104) + 64LL) + 80LL) + 56LL) & 1) != 0
              || *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 104) + 64LL) + 80LL) + 60LL) == 27)
             && (**(_DWORD **)(v1 + 248) & 0x42) == 0 )
      {
        goto LABEL_144;
      }
LABEL_126:
      v64 = *(_BYTE *)(v1 + 12);
      if ( v64 )
      {
        if ( v64 == 13 )
        {
          v68 = *(_DWORD *)(*(_QWORD *)(v1 + 248) + 40LL);
          if ( v68 == 622792 || v68 == 623208 || v68 == 1327346 || v68 == 1343730 || v68 == 590047 )
            goto LABEL_144;
        }
        else if ( v64 == 14 )
        {
          v69 = *(_DWORD *)(*(_QWORD *)(v1 + 248) + 40LL);
          if ( v69 == 1328152 || v69 == 1344540 )
            goto LABEL_144;
        }
      }
      else
      {
        v65 = *(_BYTE *)(*(_QWORD *)(v1 + 248) + 35LL);
        if ( (v65 & 0xFA) == 0 && v65 != 1 )
          goto LABEL_144;
      }
    }
    *(_DWORD *)(v1 + 4) &= ~0x400u;
    goto LABEL_130;
  }
  *(_DWORD *)(v1 + 232) &= ~0x80000000;
  LOBYTE(v58) = 1;
  FltpTraceIOStatusOnFailure(v1, v14, v58);
  v74 = 2;
  if ( (*((_BYTE *)FltpOperationFlags + (unsigned __int8)v99) & 2) != 0 )
  {
    v75 = *(_DWORD *)(v1 + 256);
    if ( v75 >= 0 && v75 != 260 )
    {
      v76 = *(_QWORD *)(v1 + 160);
      if ( v76 )
      {
        *(_QWORD *)(v76 + 16) = v18;
        v74 = 1;
      }
    }
  }
  if ( v98 == 2 && *(_QWORD *)(v1 + 160) )
  {
    FltpCleanupStreamListCtrlForFileObjectCloseWithStreamListCtrl(OwnerId, *(_QWORD *)(v1 + 112));
    FltpReleaseStreamListCtrl(*(PVOID *)(v1 + 160));
    *(_QWORD *)(v1 + 160) = 0;
  }
  ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v18 + 56), v74);
  v2 = v80;
  v3 = 1;
LABEL_178:
  v21 = (_QWORD *)(v1 + 112);
  if ( v2 != 259 )
  {
LABEL_179:
    if ( *v24 )
    {
      --*(_BYTE *)(v1 + 15);
      *v24 = 0;
    }
    if ( v98 == 2 && !v3 )
    {
      v78 = *v21;
      if ( *(_QWORD *)(v1 + 160) )
      {
        FltpCleanupStreamListCtrlForFileObjectCloseWithStreamListCtrl(OwnerId, v78);
        FltpReleaseStreamListCtrl(*(PVOID *)(v1 + 160));
        *(_QWORD *)(v1 + 160) = 0;
      }
      else
      {
        FltpCleanupStreamListCtrlForFileObjectClose(OwnerId, v78);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800047e0  mov     [rsp-8+arg_0], rcx
0x1800047e5  push    rbp
0x1800047e6  push    rbx
0x1800047e7  push    rsi
0x1800047e8  push    rdi
0x1800047e9  push    r12
0x1800047eb  push    r13
0x1800047ed  push    r14
0x1800047ef  push    r15
0x1800047f1  lea     rbp, [rsp-8]
0x1800047f6  sub     rsp, 108h
0x1800047fd  mov     rdi, [rcx+10h]
0x180004801  xor     esi, esi
0x180004803  xorps   xmm0, xmm0
0x180004806  mov     [rsp+140h+var_D0], rsi
0x18000480b  movups  [rbp+40h+var_A8], xmm0
0x18000480f  xor     r15b, r15b
0x180004812  mov     r14, rcx
0x180004815  movups  [rbp+40h+var_98], xmm0
0x180004819  lea     r13, [rdi+0E8h]
0x180004820  mov     [rsp+140h+var_F8], esi
0x180004824  movups  [rbp+40h+var_88], xmm0
0x180004828  mov     rax, [r13+10h]
0x18000482c  movzx   eax, byte ptr [rax+4]
0x180004830  mov     [rbp+40h+arg_10], al
0x180004833  add     al, 16h
0x180004835  movzx   eax, al
0x180004838  mov     [rbp+40h+arg_18], eax
0x18000483b  mov     rax, [rcx+18h]
0x18000483f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004843  jnz     short loc_18000484A
0x180004845  mov     rax, rcx
0x180004848  jmp     short loc_180004852
0x18000484a  mov     rax, [rax+10h]
0x18000484e  add     rax, 40h ; '@'
0x180004852  mov     r12, [rax]
0x180004855  mov     rbx, cs:qword_18003EF20
0x18000485c  mov     [rsp+140h+OwnerId], r12
0x180004861  call    cs:__imp_KeEnterGuardedRegion
0x180004868  nop     dword ptr [rax+rax+00h]
0x18000486d  xor     edx, edx
0x18000486f  mov     rcx, rbx
0x180004872  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x180004879  nop     dword ptr [rax+rax+00h]
0x18000487e  mov     rcx, [r14+18h]
0x180004882  mov     rbx, rax
0x180004885  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180004889  jnz     short loc_1800048A0
0x18000488b  mov     ecx, [rbp+40h+arg_18]
0x18000488e  lea     rax, [rcx+14h]
0x180004892  add     rax, rax
0x180004895  mov     r14, [r12+rax*8]
0x180004899  mov     [rsp+140h+var_100], r14
0x18000489e  jmp     short loc_1800048D5
0x1800048a0  mov     eax, [r14+28h]
0x1800048a4  test    al, 1
0x1800048a6  jz      short loc_1800048AD
0x1800048a8  mov     r14, [rcx]
0x1800048ab  jmp     short loc_1800048B0
0x1800048ad  mov     r14, rcx
0x1800048b0  mov     [rsp+140h+var_100], r14
0x1800048b5  test    al, 2
0x1800048b7  jnz     short loc_1800048D2
0x1800048b9  mov     rcx, [rcx+10h]
0x1800048bd  mov     edx, 1; Count
0x1800048c2  mov     rcx, [rcx+38h]; RunRef
0x1800048c6  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1800048cd  nop     dword ptr [rax+rax+00h]
0x1800048d2  mov     ecx, [rbp+40h+arg_18]
0x1800048d5  mov     eax, ecx
0x1800048d7  add     rax, 14h
0x1800048db  mov     [rbp+40h+arg_8], sil
0x1800048df  shl     rax, 4
0x1800048e3  mov     [rbp+40h+var_78], rax
0x1800048e7  add     rax, r12
0x1800048ea  cmp     r14, rax
0x1800048ed  jz      loc_1800053AF
0x1800048f3  xor     eax, eax
0x1800048f5  mov     [rbp+40h+var_B8], rax
0x1800048f9  mov     [rbp+40h+var_B0], rax
0x1800048fd  mov     rax, [r13+10h]
0x180004901  mov     r8d, [rax]
0x180004904  mov     edx, r8d
0x180004907  and     edx, 2
0x18000490a  and     r8b, 1
0x18000490e  mov     [rsp+140h+var_E4], edx
0x180004912  mov     [rsp+140h+var_E0], r8d
0x180004917  nop     word ptr [rax+rax+00000000h]
0x180004920  mov     r12, [r14+10h]
0x180004924  mov     [rsp+140h+var_D8], r12
0x180004929  mov     eax, [r12+50h]
0x18000492e  test    al, 2
0x180004930  jz      short loc_18000493F
0x180004932  mov     r14, [r14]
0x180004935  mov     [rsp+140h+var_100], r14
0x18000493a  jmp     loc_18000525B
0x18000493f  mov     rax, [r13+10h]
0x180004943  movzx   ecx, byte ptr [rax+4]
0x180004947  sub     cl, 3
0x18000494a  cmp     cl, 1
0x18000494d  ja      short loc_180004968
0x18000494f  mov     eax, [r14+28h]
0x180004953  test    edx, edx
0x180004955  jz      short loc_18000495B
0x180004957  test    al, 1
0x180004959  jnz     short loc_180004993
0x18000495b  test    r8b, r8b
0x18000495e  jz      short loc_18000498F
0x180004960  test    edx, edx
0x180004962  jnz     short loc_180004968
0x180004964  test    al, 10h
0x180004966  jnz     short loc_180004993
0x180004968  mov     rax, [rdi+70h]
0x18000496c  test    rax, rax
0x18000496f  jz      short loc_1800049A0
0x180004971  mov     eax, [rax+50h]
0x180004974  bt      eax, 16h
0x180004978  jb      short loc_1800049A0
0x18000497a  mov     eax, [r14+28h]
0x18000497e  test    al, 8
0x180004980  jz      short loc_1800049A0
0x180004982  mov     r14, [r14]
0x180004985  mov     [rsp+140h+var_100], r14
0x18000498a  jmp     loc_18000525B
0x18000498f  test    al, 2
0x180004991  jz      short loc_180004968
0x180004993  mov     r14, [r14]
0x180004996  mov     [rsp+140h+var_100], r14
0x18000499b  jmp     loc_18000525B
0x1800049a0  mov     rax, [rbp+40h+arg_0]
0x1800049a4  mov     eax, [rax+28h]
0x1800049a7  test    al, 10h
0x1800049a9  jz      short loc_1800049C5
0x1800049ab  mov     rax, [r12+48h]
0x1800049b0  mov     ecx, [rax+60h]
0x1800049b3  test    cl, 4
0x1800049b6  jnz     short loc_1800049C5
0x1800049b8  mov     r14, [r14]
0x1800049bb  mov     [rsp+140h+var_100], r14
0x1800049c0  jmp     loc_18000525B
0x1800049c5  mov     rcx, [r12+38h]; RunRefCacheAware
0x1800049ca  mov     edx, 2; Count
0x1800049cf  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1800049d6  nop     dword ptr [rax+rax+00h]
0x1800049db  test    al, al
0x1800049dd  jnz     short loc_1800049EC
0x1800049df  mov     r14, [r14]
0x1800049e2  mov     [rsp+140h+var_100], r14
0x1800049e7  jmp     loc_180005252
0x1800049ec  xor     edx, edx
0x1800049ee  mov     rcx, rbx
0x1800049f1  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1800049f8  nop     dword ptr [rax+rax+00h]
0x1800049fd  call    cs:__imp_KeLeaveGuardedRegion
0x180004a04  nop     dword ptr [rax+rax+00h]
0x180004a09  mov     rax, [r13+10h]
0x180004a0d  lea     rbx, [rdi+70h]
0x180004a11  mov     [rax+10h], r12
0x180004a15  mov     rax, [rbx]
0x180004a18  mov     rcx, [r13+10h]
0x180004a1c  mov     [rcx+8], rax
0x180004a20  mov     rax, [rbx]
0x180004a23  mov     [rbp+40h+var_C0], rax
0x180004a27  test    rax, rax
0x180004a2a  jz      short loc_180004A4B
0x180004a2c  mov     rcx, [rsp+140h+OwnerId]
0x180004a31  cmp     dword ptr [rcx+3Ch], 2
0x180004a35  jnz     short loc_180004A4B
0x180004a37  mov     rcx, rax; FileObject
0x180004a3a  call    cs:__imp_IoGetTransactionParameterBlock
0x180004a41  nop     dword ptr [rax+rax+00h]
0x180004a46  mov     rdx, rax
0x180004a49  jmp     short loc_180004A4D
0x180004a4b  xor     edx, edx
0x180004a4d  lea     r13, [rdi+80h]
0x180004a54  mov     rax, [r13+0]
0x180004a58  test    rax, rax
0x180004a5b  jz      short loc_180004A6D
0x180004a5d  mov     rcx, [rax+40h]
0x180004a61  mov     [rax+40h], r12
0x180004a65  mov     rax, [r13+0]
0x180004a69  mov     [rax+40h], rcx
0x180004a6d  cmp     qword ptr [r14+18h], 0
0x180004a72  jnz     loc_180004B30
0x180004a78  mov     rdx, [r13+0]
0x180004a7c  test    rdx, rdx
0x180004a7f  jnz     loc_180004B09
0x180004a85  movzx   r8d, byte ptr [rdi+0Fh]
0x180004a8a  cmp     r8b, [rdi+0Eh]
0x180004a8e  jnb     short loc_180004AA7
0x180004a90  mov     edx, r8d
0x180004a93  shl     rdx, 7
0x180004a97  add     rdx, [rdi+10h]
0x180004a9b  inc     r8b
0x180004a9e  mov     [rdi+0Fh], r8b
0x180004aa2  mov     [rdx], rdi
0x180004aa5  jmp     short loc_180004AB2
0x180004aa7  mov     rcx, rdi
0x180004aaa  call    FltpExtendIrpCtrl
0x180004aaf  mov     rdx, rax
0x180004ab2  test    rdx, rdx
0x180004ab5  jz      loc_180005272
0x180004abb  xor     eax, eax
0x180004abd  lea     r13, [rdi+0E8h]
0x180004ac4  mov     [rdx+78h], ax
0x180004ac8  mov     rcx, r12
0x180004acb  mov     rax, [r13+10h]
0x180004acf  movups  xmm0, xmmword ptr [rax]
0x180004ad2  movups  xmmword ptr [rdx+30h], xmm0
0x180004ad6  movups  xmm1, xmmword ptr [rax+10h]
0x180004ada  movups  xmmword ptr [rdx+40h], xmm1
0x180004ade  movups  xmm0, xmmword ptr [rax+20h]
0x180004ae2  movups  xmmword ptr [rdx+50h], xmm0
0x180004ae6  movups  xmm1, xmmword ptr [rax+30h]
0x180004aea  movups  xmmword ptr [rdx+60h], xmm1
0x180004aee  movsd   xmm0, qword ptr [rax+40h]
0x180004af3  mov     rax, rdx
0x180004af6  movsd   qword ptr [rdx+70h], xmm0
0x180004afb  mov     [rdx+8], r14
0x180004aff  call    FltpLinkCompletionNodeToInstance
0x180004b04  jmp     loc_1800051B4
0x180004b09  mov     qword ptr [r13+0], 0
0x180004b11  mov     rax, rdx
0x180004b14  mov     [rdx+40h], r12
0x180004b18  lea     r13, [rdi+0E8h]
0x180004b1f  mov     rcx, r12
0x180004b22  mov     [rdx+8], r14
0x180004b26  call    FltpLinkCompletionNodeToInstance
0x180004b2b  jmp     loc_1800051B4
0x180004b30  mov     r10, [rsp+140h+OwnerId]
0x180004b35  mov     eax, 30h ; '0'
0x180004b3a  mov     word ptr [rbp+40h+var_A8], ax
0x180004b3e  xor     esi, esi
0x180004b40  mov     rax, [r12+48h]
0x180004b45  mov     qword ptr [rbp+40h+var_A8+8], rax
0x180004b49  mov     qword ptr [rbp+40h+var_98], r10
0x180004b4d  mov     qword ptr [rbp+40h+var_98+8], r12
0x180004b51  mov     rax, [rbx]
0x180004b54  mov     qword ptr [rbp+40h+var_88], rax
0x180004b58  test    rdx, rdx
0x180004b5b  jz      short loc_180004B6F
0x180004b5d  mov     rax, [rdx+8]
0x180004b61  mov     qword ptr [rbp+40h+var_88+8], rax
0x180004b65  movzx   eax, word ptr [rdx+2]
0x180004b69  mov     word ptr [rbp+40h+var_A8+2], ax
0x180004b6d  jmp     short loc_180004B77
0x180004b6f  mov     qword ptr [rbp+40h+var_88+8], rsi
0x180004b73  mov     word ptr [rbp+40h+var_A8+2], si
0x180004b77  cmp     qword ptr [r14+20h], 0
0x180004b7c  jnz     short loc_180004BCB
0x180004b7e  mov     rax, [r14+10h]
0x180004b82  mov     rcx, [rax+48h]
0x180004b86  mov     eax, [rcx+60h]
0x180004b89  test    al, 4
0x180004b8b  jz      short loc_180004BB5
0x180004b8d  cmp     byte ptr [rdi+0Ch], 6
0x180004b91  jnz     short loc_180004BB5
0x180004b93  mov     rax, [rdi+0F8h]
0x180004b9a  mov     ecx, [rax+20h]
0x180004b9d  add     ecx, 0FFFFFFF6h
0x180004ba0  cmp     ecx, 3Eh ; '>'
0x180004ba3  ja      short loc_180004BB5
0x180004ba5  mov     rax, 4080000040000003h
0x180004baf  bt      rax, rcx
0x180004bb3  jb      short loc_180004BCB
0x180004bb5  test    dword ptr [rdi+4], 400h
0x180004bbc  jnz     short loc_180004BCB
0x180004bbe  mov     r15, rsi
0x180004bc1  mov     [rsp+140h+var_C8], rsi
0x180004bc6  jmp     loc_180004C60
0x180004bcb  mov     r15, [r13+0]
0x180004bcf  test    r15, r15
0x180004bd2  jnz     short loc_180004C4C
0x180004bd4  movzx   edx, byte ptr [rdi+0Fh]
0x180004bd8  cmp     dl, [rdi+0Eh]
0x180004bdb  jnb     short loc_180004BF2
0x180004bdd  mov     r15d, edx
0x180004be0  shl     r15, 7
0x180004be4  add     r15, [rdi+10h]
0x180004be8  inc     dl
0x180004bea  mov     [rdi+0Fh], dl
0x180004bed  mov     [r15], rdi
0x180004bf0  jmp     short loc_180004C02
0x180004bf2  mov     rcx, rdi
0x180004bf5  call    FltpExtendIrpCtrl
0x180004bfa  mov     r10, [rsp+140h+OwnerId]
0x180004bff  mov     r15, rax
0x180004c02  mov     [rsp+140h+var_C8], r15
0x180004c07  test    r15, r15
0x180004c0a  jz      loc_18000529C
0x180004c10  mov     [r15+78h], si
0x180004c15  mov     rax, [rdi+0F8h]
0x180004c1c  movups  xmm0, xmmword ptr [rax]
0x180004c1f  movups  xmmword ptr [r15+30h], xmm0
0x180004c24  movups  xmm1, xmmword ptr [rax+10h]
0x180004c28  movups  xmmword ptr [r15+40h], xmm1
0x180004c2d  movups  xmm0, xmmword ptr [rax+20h]
0x180004c31  movups  xmmword ptr [r15+50h], xmm0
0x180004c36  movups  xmm1, xmmword ptr [rax+30h]
0x180004c3a  movups  xmmword ptr [r15+60h], xmm1
  ... truncated ...
```
