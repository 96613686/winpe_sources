# FltpLegacyProcessingAfterPreCallbacksCompleted

- ea: `0x180007500`
- end: `0x180007d74`
- name: `FltpLegacyProcessingAfterPreCallbacksCompleted`
- size: `2164`
- prototype: ``
- caller_count: `7`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180002880`
- `0x180005dd0`
- `0x180008a70`
- `0x1800126a0`
- `0x18006e150`
- `0x18006ee20`
- `0x18006fc70`

## callees

- `0x180005b80`
- `0x180006590`
- `0x180007230`
- `0x180007500`
- `0x180009f20`
- `0x1800154d0`
- `0x180016f40`
- `0x18001b2a0`
- `0x18001bc90`
- `0x18001ca30`
- `0x18001cd80`
- `0x18005e910`
- `0x180060520`
- `0x180061e00`
- `0x180062db0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18000791b`
- `ntoskrnl!ExFreePoolWithTag` at `0x180007969`
- `ntoskrnl!ExFreePoolWithTag` at `0x180007b85`
- `ntoskrnl!ExFreePoolWithTag` at `0x180007be7`
- `ntoskrnl!ExFreePoolWithTag` at `0x180007cdd`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000791b`
- `ntoskrnl!ExFreePoolWithTag` at `0x180007969`
- `ntoskrnl!ExFreePoolWithTag` at `0x180007b85`
- `ntoskrnl!ExFreePoolWithTag` at `0x180007be7`
- `ntoskrnl!ExFreePoolWithTag` at `0x180007cdd`
- `ntoskrnl!ExQueryDepthSList` at `0x1800078f9`
- `ntoskrnl!ExQueryDepthSList` at `0x1800078f9`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x18000798f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x18000798f`
- `ntoskrnl!IoGetStackLimits` at `0x180007650`
- `ntoskrnl!IoGetStackLimits` at `0x180007650`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1800079c9`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1800079c9`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x180007c70`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x180007c70`
- `ntoskrnl!FsRtlMupGetProviderInfoFromFileObject` at `0x18002569b`
- `ntoskrnl!FsRtlMupGetProviderInfoFromFileObject` at `0x18002569b`
- `ntoskrnl!KeClearEvent` at `0x1800076cf`
- `ntoskrnl!KeClearEvent` at `0x1800076cf`
- `ntoskrnl!IofCallDriver` at `0x180007678`
- `ntoskrnl!IofCallDriver` at `0x180007678`

## pseudocode

```c
__int64 __fastcall FltpLegacyProcessingAfterPreCallbacksCompleted(__int64 a1, int a2, __int64 a3)
{
  ULONG_PTR v3; // rsi
  char v4; // r14
  __int64 v5; // rbp
  __int64 v6; // r15
  PFILE_OBJECT *v7; // rbx
  int v8; // r12d
  char v9; // r13
  ULONG_PTR v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rbp
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  struct _DEVICE_OBJECT *v17; // rbx
  NTSTATUS ProviderInfoFromFileObject; // eax
  unsigned int v19; // ebp
  unsigned int v20; // ebx
  struct _KEVENT *v22; // rcx
  __int64 v23; // rdx
  __int64 *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rcx
  char v28; // al
  char v29; // cl
  __int64 v30; // rbx
  int v31; // eax
  __int64 v32; // r8
  __int64 v33; // rdx
  bool v34; // zf
  __int64 v35; // rdx
  USHORT v36; // bx
  int v37; // eax
  int v38; // eax
  unsigned int v39; // eax
  int v40; // ecx
  int v41; // r8d
  __int64 v42; // rax
  signed int v43; // edi
  __int64 *v44; // rcx
  int v45; // ecx
  void *v46; // rcx
  void *v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rax
  unsigned __int64 LowLimit; // [rsp+30h] [rbp-78h] BYREF
  unsigned __int64 HighLimit; // [rsp+38h] [rbp-70h] BYREF
  _QWORD Parameter[2]; // [rsp+40h] [rbp-68h] BYREF
  __int64 v53; // [rsp+50h] [rbp-58h]
  int v55; // [rsp+B8h] [rbp+10h]
  unsigned int v56; // [rsp+B8h] [rbp+10h]
  char v57; // [rsp+C0h] [rbp+18h]
  PFILE_OBJECT *v58; // [rsp+C8h] [rbp+20h]

  v57 = a3;
  v3 = *(_QWORD *)(a1 + 16);
  v4 = a3;
  LODWORD(v5) = a2;
  LOBYTE(a3) = a2 != 0;
  v6 = *(_QWORD *)(v3 + 48);
  v7 = *(PFILE_OBJECT **)(v6 + 184);
  v58 = v7;
  FltpMoveCallbackDataToIrp(v3, v6, a3, 0);
  v8 = *(_DWORD *)(v3 + 4);
  v55 = *(_DWORD *)(v3 + 232);
  if ( (*((_BYTE *)FltpOperationFlags + (unsigned __int8)(*(_BYTE *)(*(_QWORD *)(v3 + 248) + 4LL) + 22)) & 2) != 0 )
  {
    v27 = *(_QWORD *)(v3 + 112);
    if ( !*(_QWORD *)(v27 + 24) )
      *(_QWORD *)(v27 + 24) = *(_QWORD *)(v3 + 168);
  }
  if ( !v4 )
  {
    v28 = *(_BYTE *)v7;
    if ( *(_BYTE *)v7 == 13 )
    {
      v40 = *((_DWORD *)v7 + 6);
      if ( v40 == 1114120 )
        goto LABEL_68;
      if ( v40 == 589916 )
        goto LABEL_68;
      if ( (unsigned int)(v40 - 589824) <= 0xC )
      {
        v41 = 4369;
        if ( _bittest(&v41, v40 - 589824) )
          goto LABEL_68;
      }
      if ( v40 == 590400 )
        goto LABEL_68;
    }
    v29 = *((_BYTE *)v7 + 1);
    if ( v28 == 12 )
    {
      if ( (unsigned __int8)(v29 - 2) <= 1u )
      {
        v9 = 0;
        goto LABEL_35;
      }
    }
    else if ( v28 == 17 && v29 == 1 )
    {
LABEL_68:
      v9 = 0;
      goto LABEL_35;
    }
    v9 = 1;
LABEL_35:
    if ( (v8 & 8) != 0 || !v9 )
      *((_BYTE *)v7 + 3) &= ~1u;
    goto LABEL_4;
  }
  v9 = 1;
LABEL_4:
  v10 = v3 + 104;
  while ( 1 )
  {
    v11 = 0x4080000000000003LL;
    if ( (_DWORD)v5 )
      break;
    v12 = *(_QWORD *)(v6 + 184);
    if ( *(_BYTE *)v12 != 6
      || ((v45 = *(_DWORD *)(v12 + 16), (unsigned int)(v45 - 10) > 0x3E) || !_bittest64(&v11, v45 - 10))
      && (v10 = v3 + 104, v45 != 40)
      || (v10 = v3 + 104,
          v5 = (unsigned int)FltpInvalidateNameCachingAllFrames(*(PVOID *)(*(_QWORD *)(*(_QWORD *)(v3 + 104) + 64LL)
                                                                         + 80LL)),
          (int)FltpDbgStatus(v5, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 3411, 0) >= 0) )
    {
      v13 = *(_QWORD *)v10;
      if ( (v8 & 8) != 0 )
      {
        v14 = *(_QWORD *)(v6 + 184);
        *(_OWORD *)(v14 - 72) = *(_OWORD *)v14;
        *(_OWORD *)(v14 - 56) = *(_OWORD *)(v14 + 16);
        *(_OWORD *)(v14 - 40) = *(_OWORD *)(v14 + 32);
        *(_QWORD *)(v14 - 24) = *(_QWORD *)(v14 + 48);
        *(_BYTE *)(v14 - 69) = 0;
        v15 = *(_QWORD *)(v6 + 184);
        *(_QWORD *)(v15 - 16) = FltpSynchronizedOperationCompletion;
        *(_QWORD *)(v15 - 8) = v3;
        *(_BYTE *)(v15 - 69) = -32;
        if ( !v57 )
        {
          *((_BYTE *)v58 + 3) &= ~1u;
          v9 = 0;
        }
      }
      else if ( *(_BYTE *)(v3 + 15) || (*(_DWORD *)(v3 + 4) & 0x1000518) != 0 )
      {
        v25 = *(_QWORD *)(v6 + 184);
        *(_OWORD *)(v25 - 72) = *(_OWORD *)v25;
        *(_OWORD *)(v25 - 56) = *(_OWORD *)(v25 + 16);
        *(_OWORD *)(v25 - 40) = *(_OWORD *)(v25 + 32);
        *(_QWORD *)(v25 - 24) = *(_QWORD *)(v25 + 48);
        *(_BYTE *)(v25 - 69) = 0;
        v26 = *(_QWORD *)(v6 + 184);
        *(_QWORD *)(v26 - 16) = FltpPassThroughCompletion;
        *(_QWORD *)(v26 - 8) = v3;
        *(_BYTE *)(v26 - 69) = -32;
      }
      else
      {
        if ( v57 )
        {
          v49 = *(_QWORD *)(v6 + 184);
          *(_OWORD *)(v49 - 72) = *(_OWORD *)v49;
          *(_OWORD *)(v49 - 56) = *(_OWORD *)(v49 + 16);
          *(_OWORD *)(v49 - 40) = *(_OWORD *)(v49 + 32);
          *(_QWORD *)(v49 - 24) = *(_QWORD *)(v49 + 48);
          *(_BYTE *)(v49 - 69) = 0;
        }
        else
        {
          v9 = 0;
          *((_BYTE *)v58 + 3) &= ~1u;
          ++*(_BYTE *)(v6 + 67);
          *(_QWORD *)(v6 + 184) += 72LL;
        }
        v30 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v10 + 64LL) + 16LL);
        v56 = *(_DWORD *)(v3 + 8) % (unsigned int)dword_18003E760;
        LowLimit = *(_QWORD *)(v30 + 680);
        if ( (*((_BYTE *)FltpOperationFlags + (unsigned __int8)(*(_BYTE *)(v3 + 12) + 22)) & 2) != 0 )
        {
          v46 = *(void **)(v3 + 160);
          if ( v46 )
          {
            FltpFreeNameCacheCreateCtrl(v46);
            *(_QWORD *)(v3 + 160) = 0;
          }
          v47 = *(void **)(v3 + 184);
          if ( v47 )
            ExFreePoolWithTag(v47, 0x6E744D46u);
        }
        if ( (*(_DWORD *)(v3 + 4) & 0x2000000) != 0 )
          ExFreePoolWithTag(*(PVOID *)(v3 + 16), 0x6C694D46u);
        v31 = *(_DWORD *)(v3 + 4);
        if ( (v31 & 0x4000000) != 0 )
        {
          FltpFreeBackPocketIrpCtrl(v3);
        }
        else if ( (v31 & 0x88FF0000) != 0 )
        {
          FltpFreeStaticIrpCtrl(v3, v30);
        }
        else if ( (v31 & 0x10000000) != 0
               && ((v32 = *(unsigned __int8 *)(v30 + 65),
                    v33 = *(unsigned __int16 *)(v3 + 2),
                    (*(_DWORD *)(v30 + 972) & 1) == 0)
                || v33 == ((unsigned __int64)*(unsigned __int8 *)(v30 + 64) << 7) + 400
                || v33 == (v32 << 7) + 400) )
        {
          *(_QWORD *)(v3 + 264) = *(unsigned __int16 *)(v3 + 2);
          v34 = v33 == (v32 << 7) + 400;
          v35 = 0;
          if ( !v34 )
            v35 = 16;
          LowLimit = *(_QWORD *)(((unsigned __int64)v56 << 6) + v35 + LowLimit);
          _InterlockedIncrement((volatile signed __int32 *)(LowLimit + 28));
          v36 = *(_WORD *)(LowLimit + 16);
          if ( ExQueryDepthSList((PSLIST_HEADER)LowLimit) < v36 )
          {
            v38 = *(_DWORD *)(v3 + 4);
            if ( (v38 & 0x20000000) != 0 )
              *(_DWORD *)(v3 + 4) = v38 & 0xDFFFFFFF;
            ExpInterlockedPushEntrySList((PSLIST_HEADER)LowLimit, (PSLIST_ENTRY)v3);
          }
          else
          {
            _InterlockedIncrement((volatile signed __int32 *)(LowLimit + 32));
            ExFreePoolWithTag((PVOID)v3, 0x63694D46u);
          }
        }
        else
        {
          ExFreePoolWithTag((PVOID)v3, 0x63694D46u);
        }
      }
      if ( (v8 & 0x4000) != 0
        && *(_BYTE *)v58 == 5
        && *((_DWORD *)v58 + 4) == 83
        && *((_DWORD *)v58 + 2) == 24
        && !*(_BYTE *)(v6 + 64) )
      {
        ProviderInfoFromFileObject = FsRtlMupGetProviderInfoFromFileObject(
                                       v58[6],
                                       **(_DWORD **)(v6 + 24),
                                       *(PVOID *)(*(_QWORD *)(v6 + 24) + 8LL),
                                       *(PULONG *)(*(_QWORD *)(v6 + 24) + 16LL));
        *(_DWORD *)(v6 + 48) = ProviderInfoFromFileObject;
        *(_QWORD *)(v6 + 56) = 0;
LABEL_13:
        v19 = ProviderInfoFromFileObject;
      }
      else
      {
        v16 = *(_QWORD *)(v13 + 64);
        HighLimit = 0;
        LowLimit = 0;
        v17 = *(struct _DEVICE_OBJECT **)(v16 + 8);
        IoGetStackLimits(&LowLimit, &HighLimit);
        if ( (unsigned __int64)&Parameter[-1] - LowLimit >= 0x4800
          || (v53 = 0,
              Parameter[0] = v17,
              Parameter[1] = v6,
              v39 = KeExpandKernelStackAndCalloutEx(FltpCallDriverCallbacksCallout, Parameter, 0x6000u, 0, 0),
              (int)FltpDbgStatus(v39, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 291, 0) < 0) )
        {
          ProviderInfoFromFileObject = IofCallDriver(v17, (PIRP)v6);
          goto LABEL_13;
        }
        v19 = v53;
      }
      if ( *(_QWORD *)(a1 + 32) )
        FltpProcessOperationStatusCallbacks(a1, v19);
      if ( (v8 & 8) != 0 )
      {
        v22 = (struct _KEVENT *)(v3 + 24);
        if ( v19 == 259 )
          FltpCancellableWaitForIo(v22, *(PIRP *)(v3 + 48));
        else
          KeClearEvent(v22);
        v24 = FltpOperationFlags;
        if ( (*((_BYTE *)FltpOperationFlags + (unsigned __int8)(*(_BYTE *)(*(_QWORD *)(v3 + 248) + 4LL) + 22)) & 2) != 0 )
        {
          v37 = *(_DWORD *)(v6 + 48);
          if ( v37 >= 0 && v37 != 260 )
          {
            if ( *(_QWORD *)(v3 + 160) )
              FltpCacheCreateNames(v3, v23);
            FltpSetIoTargetInFileObject(v3);
          }
        }
        if ( (unsigned int)FltpPassThroughCompletionWorker(v24, v23, v3, 0) == -1073741802 )
        {
          do
            FltpCancellableWaitForIo((PVOID)(v3 + 24), *(PIRP *)(v3 + 48));
          while ( (unsigned int)FltpProcessIoCompletion(v3) == -1073741802 );
        }
        if ( !v57 )
          *((_BYTE *)v58 + 3) &= ~1u;
        return (unsigned int)FltpSynchronizeIoCleanup(v3);
      }
      if ( !v9 )
        return v19;
      return 259;
    }
    *(_DWORD *)(v3 + 256) = v5;
  }
  v42 = *(_QWORD *)(v3 + 248);
  *(_DWORD *)(v3 + 4) |= 0x80u;
  v43 = *(_DWORD *)(v3 + 256);
  v44 = FltpOperationFlags;
  if ( (*((_BYTE *)FltpOperationFlags + (unsigned __int8)(*(_BYTE *)(v42 + 4) + 22)) & 2) != 0 && v43 >= 0 && v43 != 260 )
  {
    if ( *(_QWORD *)(v3 + 160) )
    {
      FltpCacheCreateNames(v3, 0x4080000000000003LL);
      v48 = *(_QWORD *)(*(_QWORD *)(v3 + 160) + 16LL);
      if ( v48 )
      {
        ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v48 + 56), 1u);
        *(_QWORD *)(*(_QWORD *)(v3 + 160) + 16LL) = 0;
        v4 = v57;
      }
    }
    FltpSetIoTargetInFileObject(v3);
  }
  v20 = FltpPassThroughCompletionWorker(v44, v11, v3, 0);
  if ( *(_QWORD *)(a1 + 32) )
    FltpProcessOperationStatusCallbacks(a1, v43);
  if ( (v8 & 8) != 0 )
  {
    if ( v20 == -1073741802 )
    {
      do
        FltpCancellableWaitForIo((PVOID)(v3 + 24), *(PIRP *)(v3 + 48));
      while ( (unsigned int)FltpProcessIoCompletion(v3) == -1073741802 );
    }
    if ( !v4 )
      *((_BYTE *)v58 + 3) &= ~1u;
    return (unsigned int)FltpSynchronizeIoCleanup(v3);
  }
  else
  {
    if ( v20 == -1073741802 )
      return 259;
    if ( (v55 & 0x10000) == 0 )
    {
      if ( !v4 )
        *((_BYTE *)v58 + 3) &= ~1u;
      FltpCompleteRequest(v6, v20);
    }
  }
  return v20;
}

```

## disassembly

```asm
0x180007500  mov     [rsp+arg_10], r8b
0x180007505  mov     [rsp+arg_0], rcx
0x18000750a  push    rbx
0x18000750b  push    rbp
0x18000750c  push    rsi
0x18000750d  push    rdi
0x18000750e  push    r12
0x180007510  push    r14
0x180007512  push    r15
0x180007514  sub     rsp, 70h
0x180007518  mov     rsi, [rcx+10h]
0x18000751c  test    edx, edx
0x18000751e  movzx   r14d, r8b
0x180007522  mov     ebp, edx
0x180007524  setnz   r8b
0x180007528  mov     rcx, rsi
0x18000752b  xor     r9d, r9d
0x18000752e  mov     r15, [rsi+30h]
0x180007532  mov     rdx, r15
0x180007535  mov     rbx, [r15+0B8h]
0x18000753c  mov     [rsp+0A8h+arg_18], rbx
0x180007544  call    FltpMoveCallbackDataToIrp
0x180007549  mov     eax, [rsi+0E8h]
0x18000754f  lea     r9, FltpOperationFlags
0x180007556  mov     r12d, [rsi+4]
0x18000755a  mov     [rsp+0A8h+arg_8], eax
0x180007561  mov     rax, [rsi+0F8h]
0x180007568  movzx   ecx, byte ptr [rax+4]
0x18000756c  add     cl, 16h
0x18000756f  movzx   eax, cl
0x180007572  test    byte ptr [rax+r9], 2
0x180007577  jnz     loc_18000778D
0x18000757d  mov     [rsp+0A8h+var_40], r13
0x180007582  test    r14b, r14b
0x180007585  jz      loc_1800077AC
0x18000758b  mov     r13b, 1
0x18000758e  lea     rbx, [rsi+68h]
0x180007592  mov     rdx, 4080000000000003h
0x18000759c  nop     dword ptr [rax+00h]
0x1800075a0  test    ebp, ebp
0x1800075a2  jnz     loc_180007A4F
0x1800075a8  mov     rax, [r15+0B8h]
0x1800075af  cmp     byte ptr [rax], 6
0x1800075b2  jz      loc_180007AEB
0x1800075b8  mov     rbp, [rbx]
0x1800075bb  mov     edi, r12d
0x1800075be  xor     r14d, r14d
0x1800075c1  and     edi, 8
0x1800075c4  jz      loc_180007738
0x1800075ca  lea     rcx, FltpSynchronizedOperationCompletion
0x1800075d1  mov     rax, [r15+0B8h]
0x1800075d8  movups  xmm0, xmmword ptr [rax]
0x1800075db  movups  xmmword ptr [rax-48h], xmm0
0x1800075df  movups  xmm1, xmmword ptr [rax+10h]
0x1800075e3  movups  xmmword ptr [rax-38h], xmm1
0x1800075e7  movups  xmm0, xmmword ptr [rax+20h]
0x1800075eb  movups  xmmword ptr [rax-28h], xmm0
0x1800075ef  movsd   xmm1, qword ptr [rax+30h]
0x1800075f4  movsd   qword ptr [rax-18h], xmm1
0x1800075f9  mov     [rax-45h], r14b
0x1800075fd  mov     rax, [r15+0B8h]
0x180007604  mov     [rax-10h], rcx
0x180007608  mov     [rax-8], rsi
0x18000760c  mov     byte ptr [rax-45h], 0E0h
0x180007610  cmp     [rsp+0A8h+arg_10], r14b
0x180007618  jnz     short loc_180007629
0x18000761a  mov     rax, [rsp+0A8h+arg_18]
0x180007622  and     byte ptr [rax+3], 0FEh
0x180007626  xor     r13b, r13b
0x180007629  bt      r12d, 0Eh
0x18000762e  jb      loc_18002565A
0x180007634  mov     rax, [rbp+40h]
0x180007638  lea     rdx, [rsp+0A8h+HighLimit]; HighLimit
0x18000763d  lea     rcx, [rsp+0A8h+LowLimit]; LowLimit
0x180007642  mov     [rsp+0A8h+HighLimit], r14
0x180007647  mov     [rsp+0A8h+LowLimit], r14
0x18000764c  mov     rbx, [rax+8]
0x180007650  call    cs:__imp_IoGetStackLimits
0x180007657  nop     dword ptr [rax+rax+00h]
0x18000765c  lea     rax, [rsp+0A8h+HighLimit]
0x180007661  sub     rax, [rsp+0A8h+LowLimit]
0x180007666  cmp     rax, 4800h
0x18000766c  jb      loc_1800079A0
0x180007672  mov     rdx, r15; Irp
0x180007675  mov     rcx, rbx; DeviceObject
0x180007678  call    cs:__imp_IofCallDriver
0x18000767f  nop     dword ptr [rax+rax+00h]
0x180007684  mov     ebp, eax
0x180007686  mov     rcx, [rsp+0A8h+arg_0]
0x18000768e  cmp     [rcx+20h], r14
0x180007692  jnz     loc_180007D1A
0x180007698  test    edi, edi
0x18000769a  jnz     short loc_1800076BE
0x18000769c  test    r13b, r13b
0x18000769f  jnz     loc_180007AE1
0x1800076a5  mov     ebx, ebp
0x1800076a7  mov     r13, [rsp+0A8h+var_40]
0x1800076ac  mov     eax, ebx
0x1800076ae  add     rsp, 70h
0x1800076b2  pop     r15
0x1800076b4  pop     r14
0x1800076b6  pop     r12
0x1800076b8  pop     rdi
0x1800076b9  pop     rsi
0x1800076ba  pop     rbp
0x1800076bb  pop     rbx
0x1800076bc  retn
0x1800076be  mov     ebx, 103h
0x1800076c3  lea     rcx, [rsi+18h]; Object
0x1800076c7  cmp     ebp, ebx
0x1800076c9  jz      loc_180007BA8
0x1800076cf  call    cs:__imp_KeClearEvent
0x1800076d6  nop     dword ptr [rax+rax+00h]
0x1800076db  mov     rax, [rsi+0F8h]
0x1800076e2  movzx   ecx, byte ptr [rax+4]
0x1800076e6  add     cl, 16h
0x1800076e9  movzx   eax, cl
0x1800076ec  lea     rcx, FltpOperationFlags
0x1800076f3  test    byte ptr [rax+rcx], 2
0x1800076f7  jnz     loc_18000792C
0x1800076fd  xor     r9d, r9d
0x180007700  mov     r8, rsi
0x180007703  call    FltpPassThroughCompletionWorker
0x180007708  cmp     eax, 0C0000016h
0x18000770d  jz      loc_180007D26
0x180007713  cmp     [rsp+0A8h+arg_10], r14b
0x18000771b  jnz     short loc_180007729
0x18000771d  mov     rax, [rsp+0A8h+arg_18]
0x180007725  and     byte ptr [rax+3], 0FEh
0x180007729  mov     rcx, rsi; BugCheckParameter3
0x18000772c  call    FltpSynchronizeIoCleanup
0x180007731  mov     ebp, eax
0x180007733  jmp     loc_1800076A5
0x180007738  cmp     [rsi+0Fh], r14b
0x18000773c  jbe     loc_1800077E6
0x180007742  mov     rax, [r15+0B8h]
0x180007749  lea     rcx, FltpPassThroughCompletion
0x180007750  movups  xmm0, xmmword ptr [rax]
0x180007753  movups  xmmword ptr [rax-48h], xmm0
0x180007757  movups  xmm1, xmmword ptr [rax+10h]
0x18000775b  movups  xmmword ptr [rax-38h], xmm1
0x18000775f  movups  xmm0, xmmword ptr [rax+20h]
0x180007763  movups  xmmword ptr [rax-28h], xmm0
0x180007767  movsd   xmm1, qword ptr [rax+30h]
0x18000776c  movsd   qword ptr [rax-18h], xmm1
0x180007771  mov     [rax-45h], r14b
0x180007775  mov     rax, [r15+0B8h]
0x18000777c  mov     [rax-10h], rcx
0x180007780  mov     [rax-8], rsi
0x180007784  mov     byte ptr [rax-45h], 0E0h
0x180007788  jmp     loc_180007629
0x18000778d  mov     rcx, [rsi+70h]
0x180007791  cmp     qword ptr [rcx+18h], 0
0x180007796  jnz     loc_18000757D
0x18000779c  mov     rax, [rsi+0A8h]
0x1800077a3  mov     [rcx+18h], rax
0x1800077a7  jmp     loc_18000757D
0x1800077ac  movzx   eax, byte ptr [rbx]
0x1800077af  cmp     al, 0Dh
0x1800077b1  jz      loc_1800079FD
0x1800077b7  movzx   ecx, byte ptr [rbx+1]
0x1800077bb  cmp     al, 0Ch
0x1800077bd  jz      loc_180007A3B
0x1800077c3  cmp     al, 11h
0x1800077c5  jz      loc_180007C95
0x1800077cb  mov     r13b, 1
0x1800077ce  test    r12b, 8
0x1800077d2  jnz     short loc_1800077DD
0x1800077d4  test    r13b, r13b
0x1800077d7  jnz     loc_18000758E
0x1800077dd  and     byte ptr [rbx+3], 0FEh
0x1800077e1  jmp     loc_18000758E
0x1800077e6  test    dword ptr [rsi+4], 1000518h
0x1800077ed  jnz     loc_180007742
0x1800077f3  cmp     [rsp+0A8h+arg_10], r14b
0x1800077fb  jnz     loc_180007CA3
0x180007801  mov     rax, [rsp+0A8h+arg_18]
0x180007809  xor     r13b, r13b
0x18000780c  and     byte ptr [rax+3], 0FEh
0x180007810  inc     byte ptr [r15+43h]
0x180007814  add     qword ptr [r15+0B8h], 48h ; 'H'
0x18000781c  mov     rax, [rbx]
0x18000781f  lea     rcx, FltpOperationFlags
0x180007826  xor     edx, edx
0x180007828  mov     r8, [rax+40h]
0x18000782c  mov     eax, [rsi+8]
0x18000782f  div     cs:dword_18003E760
0x180007835  mov     rbx, [r8+10h]
0x180007839  mov     [rsp+0A8h+arg_8], edx
0x180007840  mov     rax, [rbx+2A8h]
0x180007847  mov     [rsp+0A8h+LowLimit], rax
0x18000784c  movzx   eax, byte ptr [rsi+0Ch]
0x180007850  add     al, 16h
0x180007852  movzx   eax, al
0x180007855  test    byte ptr [rax+rcx], 2
0x180007859  jnz     loc_180007BB6
0x18000785f  test    dword ptr [rsi+4], 2000000h
0x180007866  jnz     loc_180007CD4
0x18000786c  mov     eax, [rsi+4]
0x18000786f  bt      eax, 1Ah
0x180007873  jb      loc_180007CEE
0x180007879  test    eax, 88FF0000h
0x18000787e  jnz     loc_180007CFE
0x180007884  bt      eax, 1Ch
0x180007888  jnb     loc_180007961
0x18000788e  movzx   ecx, byte ptr [rbx+40h]
0x180007892  movzx   r8d, byte ptr [rbx+41h]
0x180007897  mov     eax, [rbx+3CCh]
0x18000789d  movzx   edx, word ptr [rsi+2]
0x1800078a1  test    al, 1
0x1800078a3  jnz     loc_180007B51
0x1800078a9  movzx   eax, word ptr [rsi+2]
0x1800078ad  mov     rcx, r8
0x1800078b0  shl     rcx, 7
0x1800078b4  mov     r8d, 10h
0x1800078ba  add     rcx, 190h
0x1800078c1  mov     [rsi+108h], rax
0x1800078c8  mov     rax, [rsp+0A8h+LowLimit]
0x1800078cd  cmp     rdx, rcx
0x1800078d0  mov     ecx, [rsp+0A8h+arg_8]
0x1800078d7  mov     rdx, r14
0x1800078da  cmovnz  rdx, r8
0x1800078de  shl     rcx, 6
0x1800078e2  add     rax, rdx
0x1800078e5  mov     rax, [rcx+rax]
0x1800078e9  mov     [rsp+0A8h+LowLimit], rax
0x1800078ee  lock inc dword ptr [rax+1Ch]
0x1800078f2  movzx   ebx, word ptr [rax+10h]
0x1800078f6  mov     rcx, rax; SListHead
0x1800078f9  call    cs:__imp_ExQueryDepthSList
0x180007900  nop     dword ptr [rax+rax+00h]
0x180007905  cmp     ax, bx
0x180007908  jb      short loc_18000797A
0x18000790a  mov     rcx, [rsp+0A8h+LowLimit]
0x18000790f  lock inc dword ptr [rcx+20h]
0x180007913  mov     edx, 63694D46h; Tag
0x180007918  mov     rcx, rsi; P
0x18000791b  call    cs:__imp_ExFreePoolWithTag
0x180007922  nop     dword ptr [rax+rax+00h]
0x180007927  jmp     loc_180007629
0x18000792c  mov     eax, [r15+30h]
0x180007930  test    eax, eax
0x180007932  js      loc_1800076FD
0x180007938  cmp     eax, 104h
0x18000793d  jz      loc_1800076FD
0x180007943  cmp     [rsi+0A0h], r14
0x18000794a  jz      short loc_180007954
0x18000794c  mov     rcx, rsi
0x18000794f  call    FltpCacheCreateNames
0x180007954  mov     rcx, rsi
0x180007957  call    FltpSetIoTargetInFileObject
0x18000795c  jmp     loc_1800076FD
0x180007961  mov     edx, 63694D46h; Tag
0x180007966  mov     rcx, rsi; P
0x180007969  call    cs:__imp_ExFreePoolWithTag
0x180007970  nop     dword ptr [rax+rax+00h]
0x180007975  jmp     loc_180007629
0x18000797a  mov     eax, [rsi+4]
0x18000797d  bt      eax, 1Dh
0x180007981  jb      loc_180007D0E
0x180007987  mov     rcx, [rsp+0A8h+LowLimit]; ListHead
0x18000798c  mov     rdx, rsi; ListEntry
0x18000798f  call    cs:__imp_ExpInterlockedPushEntrySList
0x180007996  nop     dword ptr [rax+rax+00h]
0x18000799b  jmp     loc_180007629
0x1800079a0  xor     r9d, r9d; Wait
0x1800079a3  mov     [rsp+0A8h+var_58], r14
0x1800079a8  mov     r8d, 6000h; Size
0x1800079ae  mov     [rsp+0A8h+Parameter], rbx
0x1800079b3  lea     rdx, [rsp+0A8h+Parameter]; Parameter
0x1800079b8  mov     [rsp+0A8h+var_60], r15
0x1800079bd  lea     rcx, FltpCallDriverCallbacksCallout; Callout
0x1800079c4  mov     [rsp+0A8h+Context], r14; Context
0x1800079c9  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x1800079d0  nop     dword ptr [rax+rax+00h]
0x1800079d5  mov     r8d, 123h
0x1800079db  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x1800079e2  mov     ecx, eax
0x1800079e4  xor     r9d, r9d
0x1800079e7  call    FltpDbgStatus
0x1800079ec  test    eax, eax
0x1800079ee  js      loc_180007672
0x1800079f4  mov     ebp, dword ptr [rsp+0A8h+var_58]
0x1800079f8  jmp     loc_180007686
0x1800079fd  mov     ecx, [rbx+18h]
0x180007a00  cmp     ecx, 110008h
0x180007a06  jz      short loc_180007A33
0x180007a08  cmp     ecx, 9005Ch
0x180007a0e  jz      short loc_180007A33
0x180007a10  lea     edx, [rcx-90000h]
0x180007a16  cmp     edx, 0Ch
0x180007a19  ja      short loc_180007A27
0x180007a1b  mov     r8d, 1111h
0x180007a21  bt      r8d, edx
0x180007a25  jb      short loc_180007A33
0x180007a27  cmp     ecx, 90240h
0x180007a2d  jnz     loc_1800077B7
0x180007a33  xor     r13b, r13b
0x180007a36  jmp     loc_1800077CE
0x180007a3b  sub     cl, 2
  ... truncated ...
```
