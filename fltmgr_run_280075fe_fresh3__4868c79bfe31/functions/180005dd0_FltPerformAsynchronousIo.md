# FltPerformAsynchronousIo

- ea: `0x180005dd0`
- end: `0x1800064ad`
- name: `FltPerformAsynchronousIo`
- size: `1757`
- prototype: `NTSTATUS __stdcall(PFLT_CALLBACK_DATA CallbackData, PFLT_COMPLETED_ASYNC_IO_CALLBACK CallbackRoutine, PVOID CallbackContext)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800027f0`
- `0x18007f130`

## callees

- `0x180005a50`
- `0x180005dd0`
- `0x180007500`
- `0x180007d80`
- `0x180009f20`
- `0x18000b7d0`
- `0x18000bfa0`
- `0x180010400`
- `0x180024880`
- `0x180024c00`
- `0x180074e60`

## import_xrefs

- `ntoskrnl!IoAllocateIrpEx` at `0x180006046`
- `ntoskrnl!IoAllocateIrpEx` at `0x180006046`
- `ntoskrnl!ObfReferenceObject` at `0x1800061aa`
- `ntoskrnl!ObfReferenceObject` at `0x1800061aa`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x180005f44`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x180005f44`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180005f99`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180005f99`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180005f7b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180005f7b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180005ff6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180005ff6`
- `ntoskrnl!ExReleaseFastResource` at `0x180005fea`
- `ntoskrnl!ExReleaseFastResource` at `0x180005fea`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x180005f6c`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x180005f6c`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180005f5b`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180005f5b`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x180006097`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x18000621d`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x180006097`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x18000621d`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180006013`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180006013`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x180006007`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x180006007`
- `ntoskrnl!ExAcquireRundownProtection` at `0x180005e78`
- `ntoskrnl!ExAcquireRundownProtection` at `0x180005e78`
- `ntoskrnl!RtlWalkFrameChain` at `0x1800063c6`
- `ntoskrnl!RtlWalkFrameChain` at `0x180006467`
- `ntoskrnl!RtlWalkFrameChain` at `0x1800063c6`
- `ntoskrnl!RtlWalkFrameChain` at `0x180006467`

## pseudocode

```c
NTSTATUS __stdcall FltPerformAsynchronousIo(
        PFLT_CALLBACK_DATA CallbackData,
        PFLT_COMPLETED_ASYNC_IO_CALLBACK CallbackRoutine,
        PVOID CallbackContext)
{
  struct _LIST_ENTRY *Flink; // rax
  PFLT_CALLBACK_DATA v4; // r15
  PVOID v6; // r12
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  PFLT_IO_PARAMETER_BLOCK v8; // rdi
  unsigned int v9; // ebx
  __int64 v10; // r13
  __int64 v11; // rcx
  __int64 v12; // rbx
  unsigned __int8 v13; // dl
  __int64 v14; // r14
  __int64 v15; // rsi
  __int64 v16; // rdi
  __int64 v17; // rbx
  __int64 v18; // r12
  __int64 v19; // r15
  __int64 v20; // r8
  __int64 *v21; // rdi
  __int64 *i; // rbx
  __int64 Irp; // rax
  __int64 v24; // rdx
  int v25; // eax
  unsigned int v26; // eax
  __int64 v27; // rdi
  unsigned int v28; // ebx
  __int64 v29; // r8
  __int64 v30; // rax
  NTSTATUS result; // eax
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  volatile signed __int32 *v35; // rcx
  unsigned __int64 v36; // rbx
  volatile signed __int32 *EaList; // rcx
  unsigned __int64 v38; // rbx
  _OWORD v39[3]; // [rsp+20h] [rbp-B8h] BYREF
  _BYTE v40[80]; // [rsp+50h] [rbp-88h] BYREF
  __int64 v44; // [rsp+F8h] [rbp+20h]

  Flink = CallbackData[-2].QueueLinks.Flink;
  v4 = CallbackData;
  memset(v39, 0, sizeof(v39));
  v6 = CallbackContext;
  *(_QWORD *)&v39[0] = Flink[4].Flink[5].Flink;
  *((_QWORD *)&v39[0] + 1) = *(_QWORD *)&CallbackData[-3].RequestorMode;
  Iopb = CallbackData->Iopb;
  *(_QWORD *)&v39[1] = (char *)CallbackData - 232;
  *(__m128i *)((char *)&v39[1] + 8) = _mm_load_si128((const __m128i *)&_xmm);
  DWORD2(v39[2]) = 0;
  if ( (*((_BYTE *)FltpOperationFlags + (unsigned __int8)(Iopb->MajorFunction + 22)) & 2) != 0 )
  {
    CallbackData->IoStatus.Information = 0;
    CallbackData->IoStatus.Status = -1071906813;
    ((void (__fastcall *)(PFLT_CALLBACK_DATA, PVOID))CallbackRoutine)(CallbackData, CallbackContext);
    return -1071906813;
  }
  v8 = CallbackData[-2].Iopb;
  if ( ExAcquireRundownProtection((PEX_RUNDOWN_REF)&v8->TargetFileObject) )
  {
    if ( (FltGlobals[0] & 0x2000) != 0 && (v8->IrpFlags & 0x2000000) != 0
      || (FltGlobals[0] & 0x4000) != 0 && (v8->IrpFlags & 0x4000000) != 0
      || (FltGlobals[0] & 0x8000) != 0 && (v8->IrpFlags & 0x1000000) != 0 )
    {
      EaList = (volatile signed __int32 *)v8->Parameters.QueryEa.EaList;
      if ( EaList )
      {
        v38 = (unsigned __int64)(((unsigned __int16)_InterlockedExchangeAdd(EaList, 1u) + 1) & 0x3FF) << 7;
        *(_DWORD *)((char *)v8->Parameters.QueryEa.EaList + v38 + 8) = 1;
        *(_QWORD *)((char *)v8->Parameters.QueryEa.EaList + v38 + 16) = v8->TargetFileObject;
        memset((char *)v8->Parameters.QueryEa.EaList + v38 + 24, 0, 0x70u);
        RtlWalkFrameChain((PVOID *)((char *)v8->Parameters.QueryEa.EaList + v38 + 24), 0xEu, 0);
      }
    }
    v9 = 0;
  }
  else
  {
    if ( (FltGlobals[0] & 0x2000) != 0 && (v8->IrpFlags & 0x2000000) != 0
      || (FltGlobals[0] & 0x4000) != 0 && (v8->IrpFlags & 0x4000000) != 0
      || (FltGlobals[0] & 0x8000) != 0 && (v8->IrpFlags & 0x1000000) != 0 )
    {
      v35 = (volatile signed __int32 *)v8->Parameters.QueryEa.EaList;
      if ( v35 )
      {
        v36 = (unsigned __int64)(((unsigned __int16)_InterlockedExchangeAdd(v35, 1u) + 1) & 0x3FF) << 7;
        *(_DWORD *)((char *)v8->Parameters.QueryEa.EaList + v36 + 8) = 5;
        *(_QWORD *)((char *)v8->Parameters.QueryEa.EaList + v36 + 16) = v8->TargetFileObject;
        memset((char *)v8->Parameters.QueryEa.EaList + v36 + 24, 0, 0x70u);
        RtlWalkFrameChain((PVOID *)((char *)v8->Parameters.QueryEa.EaList + v36 + 24), 0xEu, 0);
      }
    }
    v9 = -1071906805;
  }
  if ( (int)FltpDbgStatus(v9, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 967, 0) < 0 )
  {
    v4->IoStatus.Status = v9;
    v4->IoStatus.Information = 0;
    ((void (__fastcall *)(PFLT_CALLBACK_DATA, PVOID))CallbackRoutine)(v4, v6);
    return v9;
  }
  v10 = *(_QWORD *)&v39[1];
  v11 = *(_QWORD *)(*(_QWORD *)&v39[1] + 248LL);
  v12 = *(_QWORD *)(*(_QWORD *)&v39[1] + 72LL);
  v44 = v12;
  *(_BYTE *)(*(_QWORD *)&v39[1] + 12LL) = *(_BYTE *)(v11 + 4);
  *(_QWORD *)(v10 + 240) = KeGetCurrentThread();
  v13 = *(_BYTE *)(v11 + 4) + 22;
  *((_QWORD *)&v39[1] + 1) = 0;
  v14 = v13;
  if ( (*(_DWORD *)(v10 + 4) & 0x200) != 0 )
  {
    v27 = *(_QWORD *)(v12 + 8LL * v13 + 304);
    if ( v27
      && (*(_DWORD *)(v12 + 80) & 6) == 0
      && ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v12 + 56), 1u) )
    {
      *((_QWORD *)&v39[1] + 1) = v27;
      goto LABEL_14;
    }
    *((_QWORD *)&v39[1] + 1) = 0;
  }
  v15 = 0;
  memset(v40, 0, 0x48u);
  ExInitializeFastOwnerEntry(v40);
  v16 = *(_QWORD *)(v12 + 64);
  v17 = qword_18003E9A0;
  KeEnterGuardedRegion();
  v18 = ExAcquireCacheAwarePushLockSharedEx(v17, 0);
  KeEnterCriticalRegion();
  v19 = v16 + 192;
  LOBYTE(v20) = 1;
  ExAcquireFastResourceShared(v16 + 192, v40, v20);
  v21 = (__int64 *)(v16 + 296);
  for ( i = *(__int64 **)(v44 + 16); i != v21; v15 = 0 )
  {
    if ( (i[8] & 6) == 0 )
    {
      v15 = i[v14 + 36];
      if ( v15 )
      {
        if ( ExAcquireRundownProtectionCacheAwareEx((PEX_RUNDOWN_REF_CACHE_AWARE)i[5], 1u) )
          break;
      }
    }
    i = (__int64 *)*i;
  }
  ExReleaseFastResource(v19, v40);
  KeLeaveCriticalRegion();
  ExReleaseCacheAwarePushLockSharedEx(v18, 0);
  KeLeaveGuardedRegion();
  v4 = CallbackData;
  v6 = CallbackContext;
  *((_QWORD *)&v39[1] + 1) = v15;
LABEL_14:
  if ( *(_QWORD *)(v10 + 48) )
    goto LABEL_17;
  Irp = IoAllocateIrpEx(*(_QWORD *)(v10 + 104), *(unsigned __int8 *)(*(_QWORD *)(v10 + 104) + 76LL), 0);
  if ( Irp )
  {
    *(_DWORD *)(v10 + 4) |= 0x1000000u;
    *(_QWORD *)(v10 + 48) = Irp;
LABEL_17:
    v24 = *(_QWORD *)(v10 + 248);
    v25 = *(unsigned __int8 *)(v24 + 4);
    if ( v25 == 27 )
    {
LABEL_24:
      v26 = FltpBuildRequest(v10 + 232, 0);
    }
    else
    {
      if ( v25 != 15 )
      {
        switch ( *(_BYTE *)(v24 + 4) )
        {
          case 0:
          case 1:
          case 0x13:
          case 0x17:
            v28 = -1073741822;
            goto LABEL_26;
          case 2:
          case 0x12:
            v26 = FltpBuildCleanupRequest(v10 + 232);
            goto LABEL_25;
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
            goto LABEL_24;
          case 0xD:
            v32 = *(unsigned __int8 *)(v24 + 5);
            if ( v32 == 4 || !*(_BYTE *)(v24 + 5) )
              goto LABEL_19;
            v33 = v32 - 1;
            if ( !v33 || (v34 = v33 - 1) == 0 )
            {
              v28 = -1073741823;
              goto LABEL_26;
            }
            if ( v34 == 1 )
              goto LABEL_19;
LABEL_67:
            v28 = -1073741811;
            break;
          case 0xE:
            goto LABEL_19;
          default:
            goto LABEL_67;
        }
        goto LABEL_26;
      }
LABEL_19:
      v26 = FltpBuildDeviceControlRequest(v10 + 232);
    }
LABEL_25:
    v28 = v26;
LABEL_26:
    if ( (int)FltpDbgStatus(v28, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 1220, 0) >= 0 )
    {
      v29 = *(_QWORD *)(v10 + 48);
      v30 = *(_QWORD *)(v29 + 184);
      *(_QWORD *)(v30 - 16) = 0;
      *(_QWORD *)(v30 - 8) = 0;
      *(_BYTE *)(v30 - 69) = 0;
      --*(_BYTE *)(v29 + 67);
      *(_QWORD *)(v29 + 184) -= 72LL;
      **(_DWORD **)(v10 + 248) = *(_DWORD *)(v29 + 16);
      *(_BYTE *)(v10 + 312) = *(_BYTE *)(v29 + 64);
    }
    FltpDbgStatus(v28, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 667, 0);
    FltpSetIrpCtrlIoPriority(v10);
    goto LABEL_29;
  }
  v28 = -1073741670;
LABEL_29:
  if ( (int)FltpDbgStatus(v28, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 993, 0) < 0 )
  {
    v4->IoStatus.Status = v28;
    v4->IoStatus.Information = 0;
    ((void (__fastcall *)(PFLT_CALLBACK_DATA, PVOID))CallbackRoutine)(v4, v6);
    FltObjectDereference(*(PVOID *)(*(_QWORD *)&v39[1] + 72LL));
    return v28;
  }
  else
  {
    *((_QWORD *)&v39[0] + 1) = *(_QWORD *)(*(_QWORD *)&v39[1] + 48LL);
    *(_QWORD *)(*(_QWORD *)&v39[1] + 56LL) = CallbackRoutine;
    *(_QWORD *)(*(_QWORD *)&v39[1] + 64LL) = v6;
    ObfReferenceObject(v4->Thread);
    result = FltpPassThroughInternal((__int64)v39, 0);
    if ( (BYTE8(v39[2]) & 4) != 0 )
      return FltpLegacyProcessingAfterPreCallbacksCompleted(v39, (unsigned int)result, 0);
  }
  return result;
}

```

## disassembly

```asm
0x180005dd0  mov     r11, rsp
0x180005dd3  mov     [r11+18h], r8
0x180005dd7  mov     [r11+10h], rdx
0x180005ddb  mov     [r11+8], rcx
0x180005ddf  push    r12
0x180005de1  push    r14
0x180005de3  push    r15
0x180005de5  sub     rsp, 0C0h
0x180005dec  lea     r10, [rcx-0E8h]
0x180005df3  xorps   xmm0, xmm0
0x180005df6  mov     rax, [r10+68h]
0x180005dfa  mov     r15, rcx
0x180005dfd  movups  [rsp+0D8h+var_B8], xmm0
0x180005e02  mov     r14, rdx
0x180005e05  xor     edx, edx
0x180005e07  movups  [rsp+0D8h+var_A8], xmm0
0x180005e0c  mov     r12, r8
0x180005e0f  movups  [rsp+0D8h+var_98], xmm0
0x180005e14  mov     r9, [rax+40h]
0x180005e18  movdqa  xmm0, cs:__xmm@0000000000000000ffffffffffffffff
0x180005e20  mov     rax, [r9+50h]
0x180005e24  mov     qword ptr [rsp+0D8h+var_B8], rax
0x180005e29  mov     rax, [r10+30h]
0x180005e2d  mov     qword ptr [rsp+0D8h+var_B8+8], rax
0x180005e32  mov     rax, [rcx+10h]
0x180005e36  mov     qword ptr [rsp+0D8h+var_A8], r10
0x180005e3b  movdqu  [rsp+0D8h+var_A8+8], xmm0
0x180005e41  mov     dword ptr [rsp+0D8h+var_98+8], edx
0x180005e45  movzx   ecx, byte ptr [rax+4]
0x180005e49  add     cl, 16h
0x180005e4c  movzx   eax, cl
0x180005e4f  lea     rcx, cs:180000000h
0x180005e56  test    byte ptr [rax+rcx+28CB0h], 2
0x180005e5e  jnz     loc_180006305
0x180005e64  mov     [r11-20h], rbx
0x180005e68  mov     [r11-28h], rsi
0x180005e6c  mov     [r11-30h], rdi
0x180005e70  mov     rdi, [r10+48h]
0x180005e74  lea     rcx, [rdi+8]; RunRef
0x180005e78  call    cs:__imp_ExAcquireRundownProtection
0x180005e7f  nop     dword ptr [rax+rax+00h]
0x180005e84  mov     ecx, cs:FltGlobals
0x180005e8a  test    al, al
0x180005e8c  jz      loc_180006292
0x180005e92  bt      ecx, 0Dh
0x180005e96  jb      loc_1800063F5
0x180005e9c  bt      ecx, 0Eh
0x180005ea0  jb      loc_180006478
0x180005ea6  bt      ecx, 0Fh
0x180005eaa  jb      loc_180006489
0x180005eb0  xor     ebx, ebx
0x180005eb2  mov     r8d, 3C7h
0x180005eb8  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180005ebf  xor     r9d, r9d
0x180005ec2  mov     ecx, ebx
0x180005ec4  call    FltpDbgStatus
0x180005ec9  test    eax, eax
0x180005ecb  js      loc_180006333
0x180005ed1  mov     [rsp+0D8h+var_38], r13
0x180005ed9  mov     r13, qword ptr [rsp+0D8h+var_A8]
0x180005ede  mov     rcx, [r13+0F8h]
0x180005ee5  mov     rbx, [r13+48h]
0x180005ee9  mov     [rsp+0D8h+arg_18], rbx
0x180005ef1  movzx   eax, byte ptr [rcx+4]
0x180005ef5  mov     [r13+0Ch], al
0x180005ef9  mov     rax, gs:188h
0x180005f02  mov     [r13+0F0h], rax
0x180005f09  movzx   edx, byte ptr [rcx+4]
0x180005f0d  add     dl, 16h
0x180005f10  mov     qword ptr [rsp+0D8h+var_A8+8], 0
0x180005f19  test    dword ptr [r13+4], 200h
0x180005f21  movzx   r14d, dl
0x180005f25  jnz     loc_1800060B0
0x180005f2b  xor     edx, edx; Val
0x180005f2d  lea     rcx, [rsp+0D8h+var_88]; void *
0x180005f32  mov     r8d, 48h ; 'H'; Size
0x180005f38  xor     esi, esi
0x180005f3a  call    memset
0x180005f3f  lea     rcx, [rsp+0D8h+var_88]
0x180005f44  call    cs:__imp_ExInitializeFastOwnerEntry
0x180005f4b  nop     dword ptr [rax+rax+00h]
0x180005f50  mov     rdi, [rbx+40h]
0x180005f54  mov     rbx, cs:qword_18003E9A0
0x180005f5b  call    cs:__imp_KeEnterGuardedRegion
0x180005f62  nop     dword ptr [rax+rax+00h]
0x180005f67  xor     edx, edx
0x180005f69  mov     rcx, rbx
0x180005f6c  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x180005f73  nop     dword ptr [rax+rax+00h]
0x180005f78  mov     r12, rax
0x180005f7b  call    cs:__imp_KeEnterCriticalRegion
0x180005f82  nop     dword ptr [rax+rax+00h]
0x180005f87  lea     r15, [rdi+0C0h]
0x180005f8e  mov     r8b, 1
0x180005f91  mov     rcx, r15
0x180005f94  lea     rdx, [rsp+0D8h+var_88]
0x180005f99  call    cs:__imp_ExAcquireFastResourceShared
0x180005fa0  nop     dword ptr [rax+rax+00h]
0x180005fa5  mov     rbx, [rsp+0D8h+arg_18]
0x180005fad  add     rdi, 128h
0x180005fb4  mov     rbx, [rbx+10h]
0x180005fb8  cmp     rbx, rdi
0x180005fbb  jz      short loc_180005FE2
0x180005fbd  nop     dword ptr [rax]
0x180005fc0  mov     eax, [rbx+40h]
0x180005fc3  test    al, 6
0x180005fc5  jnz     short loc_180005FD8
0x180005fc7  mov     rsi, [rbx+r14*8+120h]
0x180005fcf  test    rsi, rsi
0x180005fd2  jnz     loc_18000608E
0x180005fd8  mov     rbx, [rbx]
0x180005fdb  xor     esi, esi
0x180005fdd  cmp     rbx, rdi
0x180005fe0  jnz     short loc_180005FC0
0x180005fe2  lea     rdx, [rsp+0D8h+var_88]
0x180005fe7  mov     rcx, r15
0x180005fea  call    cs:__imp_ExReleaseFastResource
0x180005ff1  nop     dword ptr [rax+rax+00h]
0x180005ff6  call    cs:__imp_KeLeaveCriticalRegion
0x180005ffd  nop     dword ptr [rax+rax+00h]
0x180006002  xor     edx, edx
0x180006004  mov     rcx, r12
0x180006007  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x18000600e  nop     dword ptr [rax+rax+00h]
0x180006013  call    cs:__imp_KeLeaveGuardedRegion
0x18000601a  nop     dword ptr [rax+rax+00h]
0x18000601f  mov     r15, [rsp+0D8h+arg_0]
0x180006027  mov     r12, [rsp+0D8h+arg_10]
0x18000602f  mov     qword ptr [rsp+0D8h+var_A8+8], rsi
0x180006034  cmp     qword ptr [r13+30h], 0
0x180006039  jnz     short loc_180006067
0x18000603b  mov     rcx, [r13+68h]
0x18000603f  xor     r8d, r8d
0x180006042  movzx   edx, byte ptr [rcx+4Ch]
0x180006046  call    cs:__imp_IoAllocateIrpEx
0x18000604d  nop     dword ptr [rax+rax+00h]
0x180006052  test    rax, rax
0x180006055  jz      loc_1800061FF
0x18000605b  or      dword ptr [r13+4], 1000000h
0x180006063  mov     [r13+30h], rax
0x180006067  lea     r8, [r13+0E8h]
0x18000606e  mov     rdx, [r8+10h]
0x180006072  movzx   eax, byte ptr [rdx+4]
0x180006076  cmp     eax, 1Bh
0x180006079  jz      short loc_1800060D2; jumptable 000000018000625F cases 3-12,16,17,20-22,25,26
0x18000607b  cmp     eax, 0Fh
0x18000607e  jnz     loc_18000623B
0x180006084  mov     rcx, r8; jumptable 000000018000625F case 14
0x180006087  call    FltpBuildDeviceControlRequest
0x18000608c  jmp     short loc_1800060DC
0x18000608e  mov     rcx, [rbx+28h]; RunRefCacheAware
0x180006092  mov     edx, 1; Count
0x180006097  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x18000609e  nop     dword ptr [rax+rax+00h]
0x1800060a3  test    al, al
0x1800060a5  jz      loc_180005FD8
0x1800060ab  jmp     loc_180005FE2
0x1800060b0  movzx   eax, dl
0x1800060b3  mov     rdi, [rbx+rax*8+130h]
0x1800060bb  test    rdi, rdi
0x1800060be  jnz     loc_180006209
0x1800060c4  mov     qword ptr [rsp+0D8h+var_A8+8], 0
0x1800060cd  jmp     loc_180005F2B
0x1800060d2  xor     edx, edx; jumptable 000000018000625F cases 3-12,16,17,20-22,25,26
0x1800060d4  mov     rcx, r8
0x1800060d7  call    FltpBuildRequest
0x1800060dc  mov     ebx, eax
0x1800060de  mov     r8d, 4C4h
0x1800060e4  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x1800060eb  xor     r9d, r9d
0x1800060ee  mov     ecx, ebx
0x1800060f0  call    FltpDbgStatus
0x1800060f5  test    eax, eax
0x1800060f7  js      short loc_18000613D
0x1800060f9  mov     r8, [r13+30h]
0x1800060fd  mov     rax, [r8+0B8h]
0x180006104  mov     qword ptr [rax-10h], 0
0x18000610c  mov     qword ptr [rax-8], 0
0x180006114  mov     byte ptr [rax-45h], 0
0x180006118  dec     byte ptr [r8+43h]
0x18000611c  add     qword ptr [r8+0B8h], 0FFFFFFFFFFFFFFB8h
0x180006124  mov     eax, [r8+10h]
0x180006128  mov     rdx, [r13+0F8h]
0x18000612f  mov     [rdx], eax
0x180006131  movzx   eax, byte ptr [r8+40h]
0x180006136  mov     [r13+138h], al
0x18000613d  mov     r8d, 29Bh
0x180006143  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x18000614a  xor     r9d, r9d
0x18000614d  mov     ecx, ebx
0x18000614f  call    FltpDbgStatus
0x180006154  mov     rcx, r13
0x180006157  call    FltpSetIrpCtrlIoPriority
0x18000615c  mov     r8d, 3E1h
0x180006162  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180006169  xor     r9d, r9d
0x18000616c  mov     ecx, ebx
0x18000616e  call    FltpDbgStatus
0x180006173  mov     r13, [rsp+0D8h+var_38]
0x18000617b  test    eax, eax
0x18000617d  js      loc_1800062D1
0x180006183  mov     rcx, qword ptr [rsp+0D8h+var_A8]
0x180006188  mov     rax, [rcx+30h]
0x18000618c  mov     qword ptr [rsp+0D8h+var_B8+8], rax
0x180006191  mov     rax, [rsp+0D8h+arg_8]
0x180006199  mov     [rcx+38h], rax
0x18000619d  mov     rax, qword ptr [rsp+0D8h+var_A8]
0x1800061a2  mov     [rax+40h], r12
0x1800061a6  mov     rcx, [r15+8]; Object
0x1800061aa  call    cs:__imp_ObfReferenceObject
0x1800061b1  nop     dword ptr [rax+rax+00h]
0x1800061b6  xor     edx, edx
0x1800061b8  lea     rcx, [rsp+0D8h+var_B8]
0x1800061bd  call    FltpPassThroughInternal
0x1800061c2  test    byte ptr [rsp+0D8h+var_98+8], 4
0x1800061c7  jz      short loc_1800061D8
0x1800061c9  xor     r8d, r8d
0x1800061cc  lea     rcx, [rsp+0D8h+var_B8]
0x1800061d1  mov     edx, eax
0x1800061d3  call    FltpLegacyProcessingAfterPreCallbacksCompleted
0x1800061d8  mov     rsi, [rsp+0D8h+var_28]
0x1800061e0  mov     rbx, [rsp+0D8h+var_20]
0x1800061e8  mov     rdi, [rsp+0D8h+var_30]
0x1800061f0  add     rsp, 0C0h
0x1800061f7  pop     r15
0x1800061f9  pop     r14
0x1800061fb  pop     r12
0x1800061fd  retn
0x1800061ff  mov     ebx, 0C000009Ah
0x180006204  jmp     loc_18000615C
0x180006209  mov     eax, [rbx+50h]
0x18000620c  test    al, 6
0x18000620e  jnz     loc_1800060C4
0x180006214  mov     rcx, [rbx+38h]; RunRefCacheAware
0x180006218  mov     edx, 1; Count
0x18000621d  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x180006224  nop     dword ptr [rax+rax+00h]
0x180006229  test    al, al
0x18000622b  jz      loc_1800060C4
0x180006231  mov     qword ptr [rsp+0D8h+var_A8+8], rdi
0x180006236  jmp     loc_180006034
0x18000623b  cmp     eax, 1Ah; switch 27 cases
0x18000623e  ja      def_18000625F; jumptable 000000018000625F default case, cases 15,24
0x180006244  lea     r9, cs:180000000h
0x18000624b  movzx   eax, ds:(byte_180031BBA - 180000000h)[r9+rax]
0x180006254  mov     ecx, ds:(jpt_18000625F - 180000000h)[r9+rax*4]
0x18000625c  add     rcx, r9
0x18000625f  jmp     rcx; switch jump
0x180006265  movzx   ecx, byte ptr [rdx+5]; jumptable 000000018000625F case 13
0x180006269  cmp     ecx, 4
0x18000626c  jz      loc_180006084; jumptable 000000018000625F case 14
0x180006272  test    ecx, ecx
0x180006274  jz      loc_180006084; jumptable 000000018000625F case 14
0x18000627a  sub     ecx, 1
0x18000627d  jz      short loc_180006288
0x18000627f  sub     ecx, 1
0x180006282  jnz     loc_18000649A
0x180006288  mov     ebx, 0C0000001h
0x18000628d  jmp     loc_1800060DE
0x180006292  bt      ecx, 0Dh
0x180006296  jb      loc_180006354
0x18000629c  bt      ecx, 0Eh
0x1800062a0  jb      loc_1800063D7
0x1800062a6  bt      ecx, 0Fh
0x1800062aa  jb      loc_1800063E4
0x1800062b0  mov     ebx, 0C01C000Bh
0x1800062b5  jmp     loc_180005EB2
0x1800062ba  mov     rcx, r8; jumptable 000000018000625F cases 2,18
0x1800062bd  call    FltpBuildCleanupRequest
0x1800062c2  jmp     loc_1800060DC
0x1800062c7  mov     ebx, 0C0000002h; jumptable 000000018000625F cases 0,1,19,23
0x1800062cc  jmp     loc_1800060DE
0x1800062d1  mov     rax, [rsp+0D8h+arg_8]
0x1800062d9  mov     rdx, r12
0x1800062dc  mov     rcx, r15
0x1800062df  mov     [r15+18h], ebx
0x1800062e3  mov     qword ptr [r15+20h], 0
0x1800062eb  call    _guard_dispatch_icall
0x1800062f0  mov     rcx, qword ptr [rsp+0D8h+var_A8]
0x1800062f5  mov     rcx, [rcx+48h]; FltObject
0x1800062f9  call    FltObjectDereference
0x1800062fe  mov     eax, ebx
0x180006300  jmp     loc_1800061D8
0x180006305  mov     [r15+20h], rdx
0x180006309  mov     rcx, r15
0x18000630c  mov     rdx, r12
0x18000630f  mov     dword ptr [r15+18h], 0C01C0003h
0x180006317  mov     rax, r14
0x18000631a  call    _guard_dispatch_icall
0x18000631f  mov     eax, 0C01C0003h
0x180006324  add     rsp, 0C0h
0x18000632b  pop     r15
0x18000632d  pop     r14
0x18000632f  pop     r12
0x180006331  retn
0x180006333  mov     rdx, r12
0x180006336  mov     [r15+18h], ebx
0x18000633a  mov     rcx, r15
0x18000633d  mov     qword ptr [r15+20h], 0
0x180006345  mov     rax, r14
  ... truncated ...
```
