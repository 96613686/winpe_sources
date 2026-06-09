# FltPerformSynchronousIo

- ea: `0x180008a70`
- end: `0x180009390`
- name: `FltPerformSynchronousIo`
- size: `2336`
- prototype: `void __stdcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `24`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800034c0`
- `0x18000c850`
- `0x18000c950`
- `0x18000cf00`
- `0x180018400`
- `0x180053390`
- `0x180053460`
- `0x180053650`
- `0x1800536e0`
- `0x180053760`
- `0x180060330`
- `0x180063760`
- `0x18006b6b0`
- `0x18006c3d0`
- `0x18006ce30`
- `0x18006d120`
- `0x18006e050`
- `0x18006ea90`
- `0x18006f790`
- `0x18006f920`
- `0x180071370`
- `0x180071960`
- `0x180072f60`
- `0x18007f290`

## callees

- `0x180005a50`
- `0x180007500`
- `0x180007d80`
- `0x180008a70`
- `0x180009f20`
- `0x18000bfa0`
- `0x180010400`
- `0x1800247a0`
- `0x180024c00`
- `0x180074e60`

## import_xrefs

- `ntoskrnl!IoAllocateIrpEx` at `0x180008d2a`
- `ntoskrnl!IoAllocateIrpEx` at `0x180008d2a`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x180008c2a`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x180008c2a`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180008c7f`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180008c7f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180008c61`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180008c61`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008cd6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008cd6`
- `ntoskrnl!ExReleaseFastResource` at `0x180008cca`
- `ntoskrnl!ExReleaseFastResource` at `0x180008cca`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x180008c52`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x180008c52`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180008c41`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180008c41`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x180008e24`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x180009069`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x180008e24`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x180009069`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180008cf3`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180008cf3`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x180008ce7`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x180008ce7`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x180008f2a`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x180008f2a`
- `ntoskrnl!IoSetIoPriorityHint` at `0x180008f5c`
- `ntoskrnl!IoSetIoPriorityHint` at `0x180008f5c`
- `ntoskrnl!ExAcquireRundownProtection` at `0x180008b5c`
- `ntoskrnl!ExAcquireRundownProtection` at `0x180008b5c`
- `ntoskrnl!ExReleaseRundownProtection` at `0x180008fc6`
- `ntoskrnl!ExReleaseRundownProtection` at `0x180008fc6`
- `ntoskrnl!RtlWalkFrameChain` at `0x1800091a3`
- `ntoskrnl!RtlWalkFrameChain` at `0x180009273`
- `ntoskrnl!RtlWalkFrameChain` at `0x18000931b`
- `ntoskrnl!RtlWalkFrameChain` at `0x1800091a3`
- `ntoskrnl!RtlWalkFrameChain` at `0x180009273`
- `ntoskrnl!RtlWalkFrameChain` at `0x18000931b`

## pseudocode

```c
void __stdcall FltPerformSynchronousIo(PFLT_CALLBACK_DATA CallbackData)
{
  struct _LIST_ENTRY *Flink; // rax
  PFLT_CALLBACK_DATA v2; // rdi
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  PFLT_IO_PARAMETER_BLOCK v4; // r12
  PEX_RUNDOWN_REF p_TargetFileObject; // r15
  unsigned int v6; // ebx
  __int64 v7; // r13
  __int64 v8; // rcx
  __int64 v9; // rbx
  unsigned __int8 v10; // dl
  __int64 v11; // r14
  __int64 v12; // rsi
  __int64 v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // r12
  __int64 v16; // r15
  __int64 v17; // r8
  __int64 *v18; // rdi
  __int64 *i; // rbx
  __int64 v20; // rdx
  __int64 Irp; // rax
  _DWORD *v22; // rsi
  __int64 v23; // r8
  int v24; // eax
  __int64 v25; // r9
  __int64 v26; // rcx
  int v27; // eax
  unsigned int v28; // ebx
  unsigned int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rax
  struct _FILE_OBJECT *v33; // rdx
  unsigned int v34; // eax
  unsigned int v35; // eax
  int v36; // ecx
  volatile signed __int32 *v37; // rax
  unsigned __int64 v38; // rbx
  int v39; // ecx
  int v40; // ecx
  volatile signed __int32 *v41; // rcx
  unsigned __int64 v42; // rbx
  volatile signed __int32 *EaList; // rcx
  unsigned __int64 v44; // rbx
  _OWORD v45[3]; // [rsp+20h] [rbp-E8h] BYREF
  __int64 v46; // [rsp+50h] [rbp-B8h]
  PFLT_CALLBACK_DATA v47; // [rsp+60h] [rbp-A8h]
  PEX_RUNDOWN_REF RunRef; // [rsp+68h] [rbp-A0h]
  _BYTE v49[80]; // [rsp+70h] [rbp-98h] BYREF
  struct _IO_PRIORITY_INFO PriorityInfo; // [rsp+C0h] [rbp-48h] BYREF

  v47 = CallbackData;
  Flink = CallbackData[-2].QueueLinks.Flink;
  memset(v45, 0, sizeof(v45));
  v2 = CallbackData;
  *(_QWORD *)&v45[0] = Flink[4].Flink[5].Flink;
  *((_QWORD *)&v45[0] + 1) = *(_QWORD *)&CallbackData[-3].RequestorMode;
  Iopb = CallbackData->Iopb;
  *(_QWORD *)&v45[1] = (char *)CallbackData - 232;
  *(__m128i *)((char *)&v45[1] + 8) = _mm_load_si128((const __m128i *)&_xmm);
  DWORD2(v45[2]) = 0;
  if ( (*((_BYTE *)FltpOperationFlags + (unsigned __int8)(Iopb->MajorFunction + 22)) & 2) != 0 )
  {
    CallbackData->IoStatus.Information = 0;
    CallbackData->IoStatus.Status = -1073741811;
    return;
  }
  v4 = CallbackData[-2].Iopb;
  *(_QWORD *)&PriorityInfo.Size = v4;
  p_TargetFileObject = (PEX_RUNDOWN_REF)&v4->TargetFileObject;
  RunRef = (PEX_RUNDOWN_REF)&v4->TargetFileObject;
  if ( ExAcquireRundownProtection((PEX_RUNDOWN_REF)&v4->TargetFileObject) )
  {
    if ( (FltGlobals[0] & 0x2000) != 0 && (v4->IrpFlags & 0x2000000) != 0
      || (FltGlobals[0] & 0x4000) != 0 && (v4->IrpFlags & 0x4000000) != 0
      || (FltGlobals[0] & 0x8000) != 0 && (v4->IrpFlags & 0x1000000) != 0 )
    {
      EaList = (volatile signed __int32 *)v4->Parameters.QueryEa.EaList;
      if ( EaList )
      {
        v44 = (unsigned __int64)(((unsigned __int16)_InterlockedExchangeAdd(EaList, 1u) + 1) & 0x3FF) << 7;
        *(_DWORD *)((char *)v4->Parameters.QueryEa.EaList + v44 + 8) = 1;
        *(struct _EX_RUNDOWN_REF *)((char *)v4->Parameters.QueryEa.EaList + v44 + 16) = (struct _EX_RUNDOWN_REF)p_TargetFileObject->Count;
        memset((char *)v4->Parameters.QueryEa.EaList + v44 + 24, 0, 0x70u);
        RtlWalkFrameChain((PVOID *)((char *)v4->Parameters.QueryEa.EaList + v44 + 24), 0xEu, 0);
      }
    }
    v6 = 0;
  }
  else
  {
    if ( (FltGlobals[0] & 0x2000) != 0 && (v4->IrpFlags & 0x2000000) != 0
      || (FltGlobals[0] & 0x4000) != 0 && (v4->IrpFlags & 0x4000000) != 0
      || (FltGlobals[0] & 0x8000) != 0 && (v4->IrpFlags & 0x1000000) != 0 )
    {
      v41 = (volatile signed __int32 *)v4->Parameters.QueryEa.EaList;
      if ( v41 )
      {
        v42 = (unsigned __int64)(((unsigned __int16)_InterlockedExchangeAdd(v41, 1u) + 1) & 0x3FF) << 7;
        *(_DWORD *)((char *)v4->Parameters.QueryEa.EaList + v42 + 8) = 5;
        *(struct _EX_RUNDOWN_REF *)((char *)v4->Parameters.QueryEa.EaList + v42 + 16) = (struct _EX_RUNDOWN_REF)p_TargetFileObject->Count;
        memset((char *)v4->Parameters.QueryEa.EaList + v42 + 24, 0, 0x70u);
        RtlWalkFrameChain((PVOID *)((char *)v4->Parameters.QueryEa.EaList + v42 + 24), 0xEu, 0);
      }
    }
    v6 = -1071906805;
  }
  if ( (int)FltpDbgStatus(v6, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 804, 0) < 0 )
  {
    v2->IoStatus.Information = 0;
    v2->IoStatus.Status = v6;
    return;
  }
  v7 = *(_QWORD *)&v45[1];
  v8 = *(_QWORD *)(*(_QWORD *)&v45[1] + 248LL);
  v9 = *(_QWORD *)(*(_QWORD *)&v45[1] + 72LL);
  v46 = v9;
  *(_BYTE *)(*(_QWORD *)&v45[1] + 12LL) = *(_BYTE *)(v8 + 4);
  *(_QWORD *)(v7 + 240) = KeGetCurrentThread();
  v10 = *(_BYTE *)(v8 + 4) + 22;
  *((_QWORD *)&v45[1] + 1) = 0;
  v11 = v10;
  if ( (*(_DWORD *)(v7 + 4) & 0x200) != 0 )
  {
    v12 = *(_QWORD *)(v9 + 8LL * v10 + 304);
    if ( v12
      && (*(_DWORD *)(v9 + 80) & 6) == 0
      && ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v9 + 56), 1u) )
    {
      goto LABEL_15;
    }
    *((_QWORD *)&v45[1] + 1) = 0;
  }
  v12 = 0;
  memset(v49, 0, 0x48u);
  ExInitializeFastOwnerEntry(v49);
  v13 = *(_QWORD *)(v9 + 64);
  v14 = qword_18003E9A0;
  KeEnterGuardedRegion();
  v15 = ExAcquireCacheAwarePushLockSharedEx(v14, 0);
  KeEnterCriticalRegion();
  v16 = v13 + 192;
  LOBYTE(v17) = 1;
  ExAcquireFastResourceShared(v13 + 192, v49, v17);
  v18 = (__int64 *)(v13 + 296);
  for ( i = *(__int64 **)(v46 + 16); i != v18; v12 = 0 )
  {
    if ( (i[8] & 6) == 0 )
    {
      v12 = i[v11 + 36];
      if ( v12 )
      {
        if ( ExAcquireRundownProtectionCacheAwareEx((PEX_RUNDOWN_REF_CACHE_AWARE)i[5], 1u) )
          break;
      }
    }
    i = (__int64 *)*i;
  }
  ExReleaseFastResource(v16, v49);
  KeLeaveCriticalRegion();
  ExReleaseCacheAwarePushLockSharedEx(v15, 0);
  KeLeaveGuardedRegion();
  v2 = v47;
  p_TargetFileObject = RunRef;
  v4 = *(PFLT_IO_PARAMETER_BLOCK *)&PriorityInfo.Size;
LABEL_15:
  *((_QWORD *)&v45[1] + 1) = v12;
  v20 = *(_QWORD *)(v7 + 48);
  if ( v20 )
    goto LABEL_18;
  Irp = IoAllocateIrpEx(*(_QWORD *)(v7 + 104), *(unsigned __int8 *)(*(_QWORD *)(v7 + 104) + 76LL), 0);
  v20 = Irp;
  if ( Irp )
  {
    *(_DWORD *)(v7 + 4) |= 0x1000000u;
    *(_QWORD *)(v7 + 48) = Irp;
LABEL_18:
    v22 = (_DWORD *)(v7 + 232);
    v23 = *(_QWORD *)(v7 + 248);
    v24 = *(unsigned __int8 *)(v23 + 4);
    if ( v24 == 27 )
    {
LABEL_29:
      v29 = FltpBuildRequest(v7 + 232, 0);
LABEL_30:
      v28 = v29;
      goto LABEL_31;
    }
    if ( v24 != 15 )
    {
      switch ( *(_BYTE *)(v23 + 4) )
      {
        case 0:
        case 1:
        case 0x13:
        case 0x17:
          v28 = -1073741822;
          goto LABEL_31;
        case 2:
        case 0x12:
          v29 = FltpBuildCleanupRequest(v7 + 232);
          goto LABEL_30;
        case 3:
        case 4:
        case 5:
        case 6:
        case 7:
        case 8:
        case 9:
        case 0xA:
        case 0xB:
        case 0xC:
        case 0x10:
        case 0x11:
        case 0x14:
        case 0x15:
        case 0x16:
        case 0x19:
        case 0x1A:
          goto LABEL_29;
        case 0xD:
          v36 = *(unsigned __int8 *)(v23 + 5);
          if ( v36 == 4 || !*(_BYTE *)(v23 + 5) )
            goto LABEL_59;
          v39 = v36 - 1;
          if ( v39 && (v40 = v39 - 1) != 0 )
          {
            if ( v40 == 1 )
            {
LABEL_59:
              v29 = FltpBuildDeviceControlRequest(v7 + 232);
              goto LABEL_30;
            }
LABEL_92:
            v28 = -1073741811;
          }
          else
          {
            v28 = -1073741823;
          }
          break;
        case 0xE:
          goto LABEL_20;
        default:
          goto LABEL_92;
      }
      goto LABEL_31;
    }
LABEL_20:
    v25 = *(_QWORD *)(v20 + 184);
    *(_QWORD *)(v20 + 152) = KeGetCurrentThread();
    *(_QWORD *)(v20 + 72) = 0;
    *(_BYTE *)(v20 + 64) = 0;
    *(_DWORD *)(v20 + 16) |= **(_DWORD **)(v7 + 248);
    *(_BYTE *)(v25 - 72) = *(_BYTE *)(*(_QWORD *)(v7 + 248) + 4LL);
    *(_BYTE *)(v25 - 71) = *(_BYTE *)(*(_QWORD *)(v7 + 248) + 5LL);
    *(_BYTE *)(v25 - 70) = *(_BYTE *)(*(_QWORD *)(v7 + 248) + 6LL);
    *(_OWORD *)(v25 - 64) = *(_OWORD *)(v23 + 24);
    *(_QWORD *)(v25 - 48) = *(_QWORD *)(v23 + 40);
    *(_BYTE *)(v25 - 69) = 0;
    v26 = *(_QWORD *)(*(_QWORD *)(v7 + 248) + 8LL);
    if ( !v26 )
      v26 = *(_QWORD *)(v7 + 112);
    *(_QWORD *)(v25 - 24) = v26;
    *(_QWORD *)(v25 - 32) = *(_QWORD *)(v7 + 104);
    v27 = *(_DWORD *)(v23 + 40) & 3;
    if ( v27 == 3 )
    {
      *(_QWORD *)(v20 + 112) = *(_QWORD *)(v23 + 56);
      *(_QWORD *)(v25 - 40) = *(_QWORD *)(v23 + 48);
    }
    else if ( v27 )
    {
      if ( (unsigned int)(v27 - 1) <= 1 )
      {
        *(_QWORD *)(v20 + 24) = *(_QWORD *)(v23 + 48);
        *(_QWORD *)(v25 - 40) = 0;
        *(_QWORD *)(v20 + 8) = *(_QWORD *)(v23 + 64);
        if ( *(_DWORD *)(v25 - 56) )
        {
          *v22 |= 8u;
          *(_DWORD *)(v20 + 16) |= 0x10u;
        }
      }
    }
    else
    {
      *(_QWORD *)(v20 + 24) = *(_QWORD *)(v23 + 48);
      *(_QWORD *)(v25 - 40) = 0;
      if ( *(_DWORD *)(v25 - 56) || *(_DWORD *)(v25 - 64) )
      {
        *v22 |= 8u;
        v28 = 0;
        *(_DWORD *)(v20 + 16) |= 0x10u;
        goto LABEL_31;
      }
    }
    v28 = 0;
LABEL_31:
    if ( (int)FltpDbgStatus(v28, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 1220, 0) >= 0 )
    {
      v30 = *(_QWORD *)(v7 + 48);
      v31 = *(_QWORD *)(v30 + 184);
      *(_QWORD *)(v31 - 16) = 0;
      *(_QWORD *)(v31 - 8) = 0;
      *(_BYTE *)(v31 - 69) = 0;
      --*(_BYTE *)(v30 + 67);
      *(_QWORD *)(v30 + 184) -= 72LL;
      **(_DWORD **)(v7 + 248) = *(_DWORD *)(v30 + 16);
      *(_BYTE *)(v7 + 312) = *(_BYTE *)(v30 + 64);
    }
    FltpDbgStatus(v28, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 667, 0);
    if ( (*v22 & 1) != 0 )
    {
      v32 = *(_QWORD *)(v7 + 248);
      PriorityInfo.Size = 16;
      *(_QWORD *)&PriorityInfo.ThreadPriority = 0xFFFF;
      PriorityInfo.IoPriority = IoPriorityNormal;
      v33 = *(struct _FILE_OBJECT **)(v32 + 8);
      if ( !v33 )
        v33 = *(struct _FILE_OBJECT **)(v7 + 112);
      v34 = IoRetrievePriorityInfo(*(PIRP *)(v7 + 48), v33, KeGetCurrentThread(), &PriorityInfo);
      if ( (int)FltpDbgStatus(v34, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 10024, 0) >= 0 )
        IoSetIoPriorityHint(*(PIRP *)(v7 + 48), PriorityInfo.IoPriority);
    }
    goto LABEL_38;
  }
  v28 = -1073741670;
LABEL_38:
  if ( (int)FltpDbgStatus(v28, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 823, 0) < 0 )
  {
    FltObjectDereference(v4);
    v2->IoStatus.Information = 0;
    v2->IoStatus.Status = v28;
  }
  else
  {
    *((_QWORD *)&v45[0] + 1) = *(_QWORD *)(*(_QWORD *)&v45[1] + 48LL);
    *(_DWORD *)(*(_QWORD *)&v45[1] + 4LL) |= 8u;
    v35 = FltpPassThroughInternal(v45, 0);
    if ( (BYTE8(v45[2]) & 4) != 0 )
      FltpLegacyProcessingAfterPreCallbacksCompleted(v45, v35, 0);
    ExReleaseRundownProtection(p_TargetFileObject);
    if ( (FltGlobals[0] & 0x2000) != 0 && (v4->IrpFlags & 0x2000000) != 0
      || (FltGlobals[0] & 0x4000) != 0 && (v4->IrpFlags & 0x4000000) != 0
      || (FltGlobals[0] & 0x8000) != 0 && (v4->IrpFlags & 0x1000000) != 0 )
    {
      v37 = (volatile signed __int32 *)v4->Parameters.QueryEa.EaList;
      if ( v37 )
      {
        v38 = (unsigned __int64)(((unsigned __int16)_InterlockedExchangeAdd(v37, 1u) + 1) & 0x3FF) << 7;
        *(_DWORD *)((char *)v4->Parameters.QueryEa.EaList + v38 + 8) = -1;
        *(_QWORD *)((char *)v4->Parameters.QueryEa.EaList + v38 + 16) = v4->TargetFileObject;
        memset((char *)v4->Parameters.QueryEa.EaList + v38 + 24, 0, 0x70u);
        RtlWalkFrameChain((PVOID *)((char *)v4->Parameters.QueryEa.EaList + v38 + 24), 0xEu, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x180008a70  push    rbx
0x180008a72  push    rdi
0x180008a73  push    r14
0x180008a75  sub     rsp, 0F0h
0x180008a7c  mov     rax, cs:__security_cookie
0x180008a83  xor     rax, rsp
0x180008a86  mov     [rsp+108h+var_38], rax
0x180008a8e  lea     r8, [rcx-0E8h]
0x180008a95  mov     [rsp+108h+var_A8], rcx
0x180008a9a  mov     rax, [r8+68h]
0x180008a9e  xorps   xmm0, xmm0
0x180008aa1  movups  [rsp+108h+var_E8], xmm0
0x180008aa6  mov     rdi, rcx
0x180008aa9  xor     r14d, r14d
0x180008aac  movups  [rsp+108h+var_D8], xmm0
0x180008ab1  movups  [rsp+108h+var_C8], xmm0
0x180008ab6  mov     rdx, [rax+40h]
0x180008aba  movdqa  xmm0, cs:__xmm@0000000000000000ffffffffffffffff
0x180008ac2  mov     rax, [rdx+50h]
0x180008ac6  mov     qword ptr [rsp+108h+var_E8], rax
0x180008acb  mov     rax, [r8+30h]
0x180008acf  mov     qword ptr [rsp+108h+var_E8+8], rax
0x180008ad4  mov     rax, [rcx+10h]
0x180008ad8  mov     qword ptr [rsp+108h+var_D8], r8
0x180008add  movdqu  [rsp+108h+var_D8+8], xmm0
0x180008ae3  mov     dword ptr [rsp+108h+var_C8+8], r14d
0x180008ae8  movzx   ecx, byte ptr [rax+4]
0x180008aec  add     cl, 16h
0x180008aef  movzx   eax, cl
0x180008af2  lea     rcx, cs:180000000h
0x180008af9  test    byte ptr [rax+rcx+28CB0h], 2
0x180008b01  jz      short loc_180008B2B
0x180008b03  mov     [rdi+20h], r14
0x180008b07  mov     dword ptr [rdi+18h], 0C000000Dh
0x180008b0e  mov     rcx, [rsp+108h+var_38]
0x180008b16  xor     rcx, rsp; StackCookie
0x180008b19  call    __security_check_cookie
0x180008b1e  add     rsp, 0F0h
0x180008b25  pop     r14
0x180008b27  pop     rdi
0x180008b28  pop     rbx
0x180008b29  retn
0x180008b2b  mov     [rsp+108h+arg_8], rsi
0x180008b33  mov     [rsp+108h+arg_10], r12
0x180008b3b  mov     r12, [r8+48h]
0x180008b3f  mov     [rsp+108h+var_28], r15
0x180008b47  mov     qword ptr [rsp+108h+PriorityInfo.Size], r12
0x180008b4f  lea     r15, [r12+8]
0x180008b54  mov     rcx, r15; RunRef
0x180008b57  mov     [rsp+108h+RunRef], r15
0x180008b5c  call    cs:__imp_ExAcquireRundownProtection
0x180008b63  nop     dword ptr [rax+rax+00h]
0x180008b68  mov     ecx, cs:FltGlobals
0x180008b6e  mov     esi, 1
0x180008b73  test    al, al
0x180008b75  jz      loc_180009101
0x180008b7b  bt      ecx, 0Dh
0x180008b7f  jb      loc_1800092AA
0x180008b85  bt      ecx, 0Eh
0x180008b89  jb      loc_18000932C
0x180008b8f  bt      ecx, 0Fh
0x180008b93  jb      loc_18000933F
0x180008b99  mov     ebx, r14d
0x180008b9c  mov     r8d, 324h
0x180008ba2  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180008ba9  xor     r9d, r9d
0x180008bac  mov     ecx, ebx
0x180008bae  call    FltpDbgStatus
0x180008bb3  test    eax, eax
0x180008bb5  js      loc_180009013
0x180008bbb  mov     [rsp+108h+var_20], r13
0x180008bc3  mov     r13, qword ptr [rsp+108h+var_D8]
0x180008bc8  mov     rcx, [r13+0F8h]
0x180008bcf  mov     rbx, [r13+48h]
0x180008bd3  mov     [rsp+108h+var_B8], rbx
0x180008bd8  movzx   eax, byte ptr [rcx+4]
0x180008bdc  mov     [r13+0Ch], al
0x180008be0  mov     rax, gs:188h
0x180008be9  mov     [r13+0F0h], rax
0x180008bf0  movzx   edx, byte ptr [rcx+4]
0x180008bf4  xor     ecx, ecx
0x180008bf6  add     dl, 16h
0x180008bf9  mov     qword ptr [rsp+108h+var_D8+8], rcx
0x180008bfe  test    dword ptr [r13+4], 200h
0x180008c06  movzx   r14d, dl
0x180008c0a  jnz     loc_180008E3D
0x180008c10  mov     rsi, rcx
0x180008c13  xor     edx, edx; Val
0x180008c15  lea     rcx, [rsp+108h+var_98]; void *
0x180008c1a  mov     r8d, 48h ; 'H'; Size
0x180008c20  call    memset
0x180008c25  lea     rcx, [rsp+108h+var_98]
0x180008c2a  call    cs:__imp_ExInitializeFastOwnerEntry
0x180008c31  nop     dword ptr [rax+rax+00h]
0x180008c36  mov     rdi, [rbx+40h]
0x180008c3a  mov     rbx, cs:qword_18003E9A0
0x180008c41  call    cs:__imp_KeEnterGuardedRegion
0x180008c48  nop     dword ptr [rax+rax+00h]
0x180008c4d  xor     edx, edx
0x180008c4f  mov     rcx, rbx
0x180008c52  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x180008c59  nop     dword ptr [rax+rax+00h]
0x180008c5e  mov     r12, rax
0x180008c61  call    cs:__imp_KeEnterCriticalRegion
0x180008c68  nop     dword ptr [rax+rax+00h]
0x180008c6d  lea     r15, [rdi+0C0h]
0x180008c74  mov     r8b, 1
0x180008c77  mov     rcx, r15
0x180008c7a  lea     rdx, [rsp+108h+var_98]
0x180008c7f  call    cs:__imp_ExAcquireFastResourceShared
0x180008c86  nop     dword ptr [rax+rax+00h]
0x180008c8b  mov     rbx, [rsp+108h+var_B8]
0x180008c90  add     rdi, 128h
0x180008c97  mov     rbx, [rbx+10h]
0x180008c9b  cmp     rbx, rdi
0x180008c9e  jz      short loc_180008CC2
0x180008ca0  mov     eax, [rbx+40h]
0x180008ca3  test    al, 6
0x180008ca5  jnz     short loc_180008CB8
0x180008ca7  mov     rsi, [rbx+r14*8+120h]
0x180008caf  test    rsi, rsi
0x180008cb2  jnz     loc_180008E1B
0x180008cb8  mov     rbx, [rbx]
0x180008cbb  xor     esi, esi
0x180008cbd  cmp     rbx, rdi
0x180008cc0  jnz     short loc_180008CA0
0x180008cc2  lea     rdx, [rsp+108h+var_98]
0x180008cc7  mov     rcx, r15
0x180008cca  call    cs:__imp_ExReleaseFastResource
0x180008cd1  nop     dword ptr [rax+rax+00h]
0x180008cd6  call    cs:__imp_KeLeaveCriticalRegion
0x180008cdd  nop     dword ptr [rax+rax+00h]
0x180008ce2  xor     edx, edx
0x180008ce4  mov     rcx, r12
0x180008ce7  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x180008cee  nop     dword ptr [rax+rax+00h]
0x180008cf3  call    cs:__imp_KeLeaveGuardedRegion
0x180008cfa  nop     dword ptr [rax+rax+00h]
0x180008cff  mov     rdi, [rsp+108h+var_A8]
0x180008d04  mov     r15, [rsp+108h+RunRef]
0x180008d09  mov     r12, qword ptr [rsp+108h+PriorityInfo.Size]
0x180008d11  mov     qword ptr [rsp+108h+var_D8+8], rsi
0x180008d16  mov     rdx, [r13+30h]
0x180008d1a  test    rdx, rdx
0x180008d1d  jnz     short loc_180008D4E
0x180008d1f  mov     rcx, [r13+68h]
0x180008d23  xor     r8d, r8d
0x180008d26  movzx   edx, byte ptr [rcx+4Ch]
0x180008d2a  call    cs:__imp_IoAllocateIrpEx
0x180008d31  nop     dword ptr [rax+rax+00h]
0x180008d36  mov     rdx, rax
0x180008d39  test    rax, rax
0x180008d3c  jz      loc_18000904B
0x180008d42  or      dword ptr [r13+4], 1000000h
0x180008d4a  mov     [r13+30h], rax
0x180008d4e  lea     rsi, [r13+0E8h]
0x180008d55  mov     r8, [rsi+10h]
0x180008d59  movzx   eax, byte ptr [r8+4]
0x180008d5e  cmp     eax, 1Bh
0x180008d61  jz      loc_180008E5B; jumptable 00000001800090E0 cases 3-12,16,17,20-22,25,26
0x180008d67  cmp     eax, 0Fh
0x180008d6a  jnz     loc_1800090BC
0x180008d70  mov     rax, gs:188h; jumptable 00000001800090E0 case 14
0x180008d79  xor     r14d, r14d
0x180008d7c  mov     r9, [rdx+0B8h]
0x180008d83  mov     [rdx+98h], rax
0x180008d8a  mov     [rdx+48h], r14
0x180008d8e  mov     byte ptr [rdx+40h], 0
0x180008d92  mov     rax, [rsi+10h]
0x180008d96  mov     ecx, [rax]
0x180008d98  or      [rdx+10h], ecx
0x180008d9b  mov     rax, [rsi+10h]
0x180008d9f  movzx   ecx, byte ptr [rax+4]
0x180008da3  mov     [r9-48h], cl
0x180008da7  mov     rax, [rsi+10h]
0x180008dab  movzx   ecx, byte ptr [rax+5]
0x180008daf  mov     [r9-47h], cl
0x180008db3  mov     rax, [rsi+10h]
0x180008db7  movzx   ecx, byte ptr [rax+6]
0x180008dbb  mov     [r9-46h], cl
0x180008dbf  movups  xmm0, xmmword ptr [r8+18h]
0x180008dc4  movups  xmmword ptr [r9-40h], xmm0
0x180008dc9  movsd   xmm1, qword ptr [r8+28h]
0x180008dcf  movsd   qword ptr [r9-30h], xmm1
0x180008dd5  mov     [r9-45h], r14b
0x180008dd9  mov     rax, [rsi+10h]
0x180008ddd  mov     rcx, [rax+8]
0x180008de1  test    rcx, rcx
0x180008de4  jnz     short loc_180008DEA
0x180008de6  mov     rcx, [rsi-78h]
0x180008dea  mov     [r9-18h], rcx
0x180008dee  mov     rax, [rsi-80h]
0x180008df2  mov     [r9-20h], rax
0x180008df6  mov     eax, [r8+28h]
0x180008dfa  and     eax, 3
0x180008dfd  cmp     eax, 3
0x180008e00  jnz     loc_18000901C
0x180008e06  mov     rax, [r8+38h]
0x180008e0a  mov     [rdx+70h], rax
0x180008e0e  mov     rax, [r8+30h]
0x180008e12  mov     [r9-28h], rax
0x180008e16  mov     ebx, r14d
0x180008e19  jmp     short loc_180008E6A
0x180008e1b  mov     rcx, [rbx+28h]; RunRefCacheAware
0x180008e1f  mov     edx, 1; Count
0x180008e24  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x180008e2b  nop     dword ptr [rax+rax+00h]
0x180008e30  test    al, al
0x180008e32  jz      loc_180008CB8
0x180008e38  jmp     loc_180008CC2
0x180008e3d  movzx   eax, dl
0x180008e40  mov     rsi, [rbx+rax*8+130h]
0x180008e48  test    rsi, rsi
0x180008e4b  jnz     loc_180009055
0x180008e51  mov     qword ptr [rsp+108h+var_D8+8], rcx
0x180008e56  jmp     loc_180008C10
0x180008e5b  xor     edx, edx; jumptable 00000001800090E0 cases 3-12,16,17,20-22,25,26
0x180008e5d  mov     rcx, rsi
0x180008e60  call    FltpBuildRequest
0x180008e65  mov     ebx, eax
0x180008e67  xor     r14d, r14d
0x180008e6a  mov     r8d, 4C4h
0x180008e70  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180008e77  xor     r9d, r9d
0x180008e7a  mov     ecx, ebx
0x180008e7c  call    FltpDbgStatus
0x180008e81  test    eax, eax
0x180008e83  js      short loc_180008EBE
0x180008e85  mov     rdx, [r13+30h]
0x180008e89  mov     rax, [rdx+0B8h]
0x180008e90  mov     [rax-10h], r14
0x180008e94  mov     [rax-8], r14
0x180008e98  mov     byte ptr [rax-45h], 0
0x180008e9c  dec     byte ptr [rdx+43h]
0x180008e9f  add     qword ptr [rdx+0B8h], 0FFFFFFFFFFFFFFB8h
0x180008ea7  mov     eax, [rdx+10h]
0x180008eaa  mov     rcx, [r13+0F8h]
0x180008eb1  mov     [rcx], eax
0x180008eb3  movzx   eax, byte ptr [rdx+40h]
0x180008eb7  mov     [r13+138h], al
0x180008ebe  mov     r8d, 29Bh
0x180008ec4  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180008ecb  xor     r9d, r9d
0x180008ece  mov     ecx, ebx
0x180008ed0  call    FltpDbgStatus
0x180008ed5  mov     eax, [rsi]
0x180008ed7  test    al, 1
0x180008ed9  jz      loc_180008F68
0x180008edf  mov     rax, [r13+0F8h]
0x180008ee6  mov     [rsp+108h+PriorityInfo.Size], 10h
0x180008ef1  mov     qword ptr [rsp+108h+PriorityInfo.ThreadPriority], 0FFFFh
0x180008efd  mov     [rsp+108h+PriorityInfo.IoPriority], 2
0x180008f08  mov     rdx, [rax+8]
0x180008f0c  test    rdx, rdx
0x180008f0f  jnz     short loc_180008F15
0x180008f11  mov     rdx, [r13+70h]; FileObject
0x180008f15  mov     r8, gs:188h; Thread
0x180008f1e  lea     r9, [rsp+108h+PriorityInfo]; PriorityInfo
0x180008f26  mov     rcx, [r13+30h]; Irp
0x180008f2a  call    cs:__imp_IoRetrievePriorityInfo
0x180008f31  nop     dword ptr [rax+rax+00h]
0x180008f36  mov     r8d, 2728h
0x180008f3c  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180008f43  mov     ecx, eax
0x180008f45  xor     r9d, r9d
0x180008f48  call    FltpDbgStatus
0x180008f4d  test    eax, eax
0x180008f4f  js      short loc_180008F68
0x180008f51  mov     edx, [rsp+108h+PriorityInfo.IoPriority]; PriorityHint
0x180008f58  mov     rcx, [r13+30h]; Irp
0x180008f5c  call    cs:__imp_IoSetIoPriorityHint
0x180008f63  nop     dword ptr [rax+rax+00h]
0x180008f68  mov     r8d, 337h
0x180008f6e  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180008f75  xor     r9d, r9d
0x180008f78  mov     ecx, ebx
0x180008f7a  call    FltpDbgStatus
0x180008f7f  mov     r13, [rsp+108h+var_20]
0x180008f87  test    eax, eax
0x180008f89  js      loc_180009378
0x180008f8f  mov     rcx, qword ptr [rsp+108h+var_D8]
0x180008f94  xor     edx, edx
0x180008f96  mov     rax, [rcx+30h]
0x180008f9a  mov     qword ptr [rsp+108h+var_E8+8], rax
0x180008f9f  or      dword ptr [rcx+4], 8
0x180008fa3  lea     rcx, [rsp+108h+var_E8]
0x180008fa8  call    FltpPassThroughInternal
0x180008fad  test    byte ptr [rsp+108h+var_C8+8], 4
0x180008fb2  jz      short loc_180008FC3
0x180008fb4  xor     r8d, r8d
0x180008fb7  lea     rcx, [rsp+108h+var_E8]
0x180008fbc  mov     edx, eax
0x180008fbe  call    FltpLegacyProcessingAfterPreCallbacksCompleted
0x180008fc3  mov     rcx, r15; RunRef
0x180008fc6  call    cs:__imp_ExReleaseRundownProtection
0x180008fcd  nop     dword ptr [rax+rax+00h]
0x180008fd2  mov     ecx, cs:FltGlobals
0x180008fd8  bt      ecx, 0Dh
0x180008fdc  jb      loc_1800091EB
0x180008fe2  bt      ecx, 0Eh
  ... truncated ...
```
