# VidMmUpgradeAllocation(VIDMM_WORKER_THREAD *,VIDMM_GLOBAL_ALLOC *)

- ea: `0x1400c4b08`
- end: `0x1400c52ef`
- name: `?VidMmUpgradeAllocation@@YAJPEAUVIDMM_WORKER_THREAD@@PEAUVIDMM_GLOBAL_ALLOC@@@Z`
- size: `2023`
- prototype: `int(struct VIDMM_WORKER_THREAD *, struct VIDMM_GLOBAL_ALLOC *)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation`

## callers

- `0x1400ac7f8`

## callees

- `0x14000cf94`
- `0x14002dbd0`
- `0x140037c68`
- `0x14004525c`
- `0x140048c58`
- `0x140048cf8`
- `0x140048e28`
- `0x140058f50`
- `0x140059030`
- `0x140059080`
- `0x140059380`
- `0x140096a04`
- `0x14009ecf4`
- `0x1400a00dc`
- `0x1400ba904`
- `0x1400bab2c`
- `0x1400c3af8`
- `0x1400c3c04`
- `0x1400c41f0`
- `0x1400c454c`
- `0x1400c4618`
- `0x1400c4b08`
- `0x1400ff470`
- `0x140112c58`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1400c4e46`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400c4e46`
- `ntoskrnl!KeStackAttachProcess` at `0x1400c4c70`
- `ntoskrnl!KeStackAttachProcess` at `0x1400c4c70`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400c5286`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400c5286`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400c509a`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400c509a`
- `ntoskrnl!NtSetInformationVirtualMemory` at `0x1400c4f70`
- `ntoskrnl!NtSetInformationVirtualMemory` at `0x1400c4f70`
- `ntoskrnl!MmUnlockPages` at `0x1400c4e88`
- `ntoskrnl!MmUnlockPages` at `0x1400c4e88`
- `watchdog!WdLogSingleEntry0` at `0x1400c4f8c`
- `watchdog!WdLogSingleEntry0` at `0x1400c4f8c`

## pseudocode

```c
__int64 __fastcall VidMmUpgradeAllocation(struct VIDMM_WORKER_THREAD *a1, struct VIDMM_GLOBAL_ALLOC *a2)
{
  __int64 v3; // r13
  _QWORD *v4; // rsi
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // rdx
  char *v7; // r9
  unsigned __int64 v8; // r15
  unsigned __int64 v9; // r12
  void *v10; // r15
  unsigned __int64 v11; // r12
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // r8d
  __int64 v20; // rcx
  signed int v21; // r12d
  char NumAvailable64KPages; // al
  int v23; // edx
  int v24; // ecx
  int v25; // r8d
  LOCK_OPERATION v26; // r8d
  PMDL v27; // rbx
  __int64 v28; // rcx
  __int64 v29; // rbx
  int OneVirtualAddressRangeResident; // ebx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 *v35; // rdx
  bool v36; // [rsp+28h] [rbp-130h]
  struct VIDMM_ALLOC **v37; // [rsp+28h] [rbp-130h]
  bool *v38; // [rsp+30h] [rbp-128h]
  __int64 v39; // [rsp+38h] [rbp-120h]
  union _LARGE_INTEGER Interval; // [rsp+40h] [rbp-118h] BYREF
  int v41; // [rsp+48h] [rbp-110h]
  int v42; // [rsp+4Ch] [rbp-10Ch]
  int v43; // [rsp+50h] [rbp-108h]
  int v44; // [rsp+54h] [rbp-104h]
  CVirtualAddressAllocator *VirtualAddressAllocator; // [rsp+58h] [rbp-100h]
  int v46; // [rsp+60h] [rbp-F8h] BYREF
  unsigned __int64 v47; // [rsp+68h] [rbp-F0h]
  unsigned __int64 v48; // [rsp+70h] [rbp-E8h]
  VIDMM_PROCESS *v49; // [rsp+78h] [rbp-E0h]
  unsigned __int64 v50; // [rsp+80h] [rbp-D8h]
  char *v51; // [rsp+88h] [rbp-D0h]
  __int64 v52; // [rsp+90h] [rbp-C8h]
  PMDL MemoryDescriptorList; // [rsp+98h] [rbp-C0h]
  __int64 v54; // [rsp+A0h] [rbp-B8h]
  __int64 v55; // [rsp+A8h] [rbp-B0h]
  unsigned __int64 v56; // [rsp+B0h] [rbp-A8h]
  unsigned __int64 v57; // [rsp+B8h] [rbp-A0h]
  void *v58; // [rsp+C0h] [rbp-98h]
  VIDMM_PROCESS *v59; // [rsp+C8h] [rbp-90h]
  PMDL v60; // [rsp+D0h] [rbp-88h]
  _BYTE *v61; // [rsp+D8h] [rbp-80h]
  void *v62; // [rsp+E0h] [rbp-78h] BYREF
  unsigned __int64 v63; // [rsp+E8h] [rbp-70h]
  struct _KAPC_STATE ApcState; // [rsp+F0h] [rbp-68h] BYREF

  v3 = *(_QWORD *)a1;
  v54 = v3;
  v4 = (_QWORD *)(v3 + 40720);
  v55 = v3 + 40720;
  v5 = *(_QWORD *)(v3 + 40720);
  v48 = v5;
  v56 = v5;
  v6 = *(_QWORD *)(v3 + 40728) - v5;
  v47 = v6;
  v57 = v6;
  v7 = (char *)a2 + 48;
  v51 = (char *)a2 + 48;
  v8 = v5 + *(_QWORD *)(*((_QWORD *)a2 + 6) + 16LL);
  v9 = v8 + v6;
  if ( (byte_140087205 & 0x40) != 0 )
  {
    McTemplateK0ppxx_EtwWriteTransfer(
      (_DWORD)a1,
      (unsigned int)VidMmUpgradeAllocationChunkStart,
      v5,
      (_DWORD)a2,
      v6,
      v8,
      v5);
    v7 = v51;
  }
  v10 = (void *)((v8 + 0xFFFF) & 0xFFFFFFFFFFFF0000uLL);
  v58 = v10;
  v11 = v9 & 0xFFFFFFFFFFFF0000uLL;
  v50 = v11;
  if ( (unsigned __int64)v10 >= v11 )
  {
    *v4 = *(_QWORD *)(v3 + 40728);
    VIDMM_GLOBAL::StopUpgradingAllocation((VIDMM_GLOBAL *)v3, *(struct VIDMM_GLOBAL_ALLOC **)(v3 + 40792));
    return 0;
  }
  memset(&ApcState, 0, sizeof(ApcState));
  v49 = *(VIDMM_PROCESS **)(*(_QWORD *)v7 + 8LL);
  v59 = v49;
  v52 = v3 + 24;
  VirtualAddressAllocator = VIDMM_PROCESS::GetVirtualAddressAllocator(
                              v49,
                              *(_DWORD *)(*(_QWORD *)(v3 + 24) + 240LL),
                              (*(_DWORD *)(*(_QWORD *)a2 + 60LL) >> 2) & 0x3F);
  KeStackAttachProcess(*((PRKPROCESS *)v49 + 2), &ApcState);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 29) + 88LL))(*((_QWORD *)a2 + 29));
  if ( !*(_BYTE *)(v3 + 40857) )
  {
    if ( (byte_140087205 & 0x40) != 0 )
      McTemplateK0_EtwWriteTransfer(v13, LargePageUpgrade_LargifyStartSuspend);
    VIDMM_PROCESS::SuspendResumeProcessGpuMmuContexts(v49, *(_DWORD *)(*(_QWORD *)v52 + 240LL), 1);
  }
  VidMmStartFaultAndStall((struct VIDMM_GLOBAL *)v3);
  v61 = (_BYTE *)(v3 + 40857);
  if ( !*(_BYTE *)(v3 + 40857) )
  {
    if ( (byte_140087205 & 0x40) == 0 )
      goto LABEL_14;
    McTemplateK0_EtwWriteTransfer(v14, LargePageUpgrade_LargifyEndSuspend);
  }
  if ( (byte_140087205 & 0x40) != 0 )
    McTemplateK0_EtwWriteTransfer(v14, LargePageUpgrade_LargifySelect);
LABEL_14:
  if ( (*((_DWORD *)DXGGLOBAL::GetGlobal() + 64) & 4) != 0 )
    ValidateGpuPtes(v10, VirtualAddressAllocator);
  Interval.QuadPart = 0;
  VIDMM_GLOBAL::StartPreparation(v3, 0xFFFFFFFFLL, 0, 0, 121, &Interval);
  VIDMM_GLOBAL::MakeVirtualAddressRangeNotResidentSubrange(
    (VIDMM_GLOBAL *)v3,
    (struct VIDMM_PAGING_EXECUTION_CONTEXT *)Interval.QuadPart,
    a2,
    v48,
    v47,
    v36);
  VIDMM_GLOBAL::EndPreparation(
    (VIDMM_GLOBAL *)v3,
    (struct VIDMM_PAGING_EXECUTION_CONTEXT *)Interval.QuadPart,
    0xFFFFFFFF,
    0,
    0,
    0,
    0);
  if ( (byte_140087205 & 0x40) != 0 )
    McTemplateK0_EtwWriteTransfer(v15, VidMmUpgradeAllocationGpuVaUnmapped);
  VIDMM_GLOBAL::WaitForAllPagingEnginesIdle((VIDMM_GLOBAL *)v3, 0, 0xFFFFFFFF);
  if ( (byte_140087205 & 0x40) != 0 )
    McTemplateK0_EtwWriteTransfer(v16, VidMmUpgradeAllocationEnginesIdle);
  if ( (*((_DWORD *)DXGGLOBAL::GetGlobal() + 64) & 4) != 0 )
    ValidateGpuPtes(v10, VirtualAddressAllocator);
  if ( (*((_DWORD *)DXGGLOBAL::GetGlobal() + 64) & 2) != 0 )
  {
    memset(v10, 0, v11 - (_QWORD)v10);
    ValidateAllocationZeroed((_DWORD)v10, v11, (_DWORD)a2, (_DWORD)VirtualAddressAllocator, v3 + 40720);
    Interval.QuadPart = -100000;
    KeDelayExecutionThread(0, 0, &Interval);
    ValidateAllocationZeroed((_DWORD)v10, v11, (_DWORD)a2, (_DWORD)VirtualAddressAllocator, v3 + 40720);
  }
  MemoryDescriptorList = *(PMDL *)(*(_QWORD *)(v3 + 40832) + 8LL * *(unsigned int *)(v3 + 40808));
  v60 = MemoryDescriptorList;
  MmUnlockPages(MemoryDescriptorList);
  if ( (byte_140087205 & 0x40) != 0 )
    McTemplateK0_EtwWriteTransfer(v17, VidMmUpgradeAllocationChunkUnlocked);
  v46 = 16;
  v62 = v10;
  Interval.QuadPart = v11 - (_QWORD)v10;
  v63 = v11 - (_QWORD)v10;
  v42 = 0;
  v43 = 0;
  v41 = 0;
  v44 = 0;
  GetContiguousChunkData(v10);
  if ( (byte_140087205 & 0x40) != 0 )
  {
    McTemplateK0_EtwWriteTransfer(v18, VidMmUpgradeAllocationLargifyStart);
    if ( (byte_140087205 & 0x40) != 0 )
      McTemplateK0pxxxt_EtwWriteTransfer(
        (**((_DWORD **)a2 + 49) >> 2) & 1,
        (unsigned int)LargePageUpgrade_LargifyStart,
        v19,
        (_DWORD)a2,
        Interval.QuadPart,
        0,
        0,
        (**((_DWORD **)a2 + 49) & 4) != 0);
  }
  v21 = NtSetInformationVirtualMemory(-1, 5, 1, &v62, &v46, 4);
  Interval.LowPart = v21;
  if ( v21 < 0 )
  {
    WdLogSingleEntry0(3);
    WdLogGlobalForLineNumber = 851;
    NumAvailable64KPages = GetNumAvailable64KPages();
    if ( (byte_140087205 & 0x40) == 0 )
      goto LABEL_34;
    LODWORD(v39) = v21;
    McTemplateK0xxxxq_EtwWriteTransfer(
      v24,
      v23,
      v25,
      v63,
      *(_QWORD *)(v3 + 40864),
      *(_QWORD *)(v3 + 40872),
      NumAvailable64KPages,
      v39,
      Interval.QuadPart);
  }
  if ( (byte_140087205 & 0x40) != 0 )
    McTemplateK0_EtwWriteTransfer(v20, VidMmUpgradeAllocationLargifyEnd);
LABEL_34:
  GetContiguousChunkData(v10);
  if ( (byte_140087205 & 0x40) != 0 )
    McTemplateK0pxxxt_EtwWriteTransfer(
      (v41 - v42) << 16,
      (unsigned int)LargePageUpgrade_LargifyEnd,
      v50 - (_DWORD)v10,
      (_DWORD)a2,
      v50 - (_BYTE)v10,
      0,
      0,
      (**((_DWORD **)a2 + 49) & 4) != 0);
  if ( !v44 )
    *((_DWORD *)a2 + 6) |= 0x40000000u;
  if ( v21 >= 0 )
    ++*(_DWORD *)(v3 + 40920);
  v26 = ~(unsigned __int8)(*((_DWORD *)a2 + 6) >> 5) & 2;
  v27 = MemoryDescriptorList;
  MmProbeAndLockPages(MemoryDescriptorList, 0, v26);
  memmove(
    (void *)(*(_QWORD *)(v3 + 40776) + 48LL + 8 * ((*v4 >> 12) + ((*(_QWORD *)(v3 + 40720) & 0xFFFLL) != 0))),
    &v27[1],
    8LL * ((v27->ByteCount >> 12) + ((v27->ByteCount & 0xFFF) != 0)));
  if ( (byte_140087205 & 0x40) != 0 )
    McTemplateK0_EtwWriteTransfer(v28, VidMmUpgradeAllocationChunkLocked);
  v29 = *(_QWORD *)(*(_QWORD *)v51 + 32LL);
  Interval.QuadPart = 0;
  VIDMM_GLOBAL::StartPreparation(v3, 0xFFFFFFFFLL, 0, 0, 206, &Interval);
  OneVirtualAddressRangeResident = VIDMM_GLOBAL::MakeOneVirtualAddressRangeResident(
                                     (VIDMM_GLOBAL *)v3,
                                     (struct VIDMM_PAGING_EXECUTION_CONTEXT *)Interval.QuadPart,
                                     (struct VIDMM_ALLOC *)(v29 - 40),
                                     v48,
                                     v47,
                                     v37,
                                     v38);
  VIDMM_GLOBAL::EndPreparation(
    (VIDMM_GLOBAL *)v3,
    (struct VIDMM_PAGING_EXECUTION_CONTEXT *)Interval.QuadPart,
    0xFFFFFFFF,
    0,
    0,
    0,
    0);
  if ( (byte_140087205 & 0x40) != 0 )
    McTemplateK0_EtwWriteTransfer(v31, VidMmUpgradeAllocationGpuVaMapped);
  if ( OneVirtualAddressRangeResident >= 0 )
  {
    VIDMM_GLOBAL::WaitForAllPagingEnginesIdle((VIDMM_GLOBAL *)v3, 0, 0xFFFFFFFF);
    if ( (*((_DWORD *)DXGGLOBAL::GetGlobal() + 64) & 4) != 0 )
      ValidateGpuPtes(v10, VirtualAddressAllocator);
    if ( (byte_140087205 & 0x40) != 0 )
      McTemplateK0_EtwWriteTransfer(v32, VidMmUpgradeAllocationEnginesIdle);
    VidMmEndFaultAndStall((struct VIDMM_GLOBAL *)v3);
    if ( !*v61 )
    {
      VIDMM_PROCESS::SuspendResumeProcessGpuMmuContexts(v49, *(_DWORD *)(*(_QWORD *)v52 + 240LL), 0);
      if ( (byte_140087205 & 0x40) != 0 )
        McTemplateK0_EtwWriteTransfer(v33, LargePageUpgrade_LargifyResume);
    }
  }
  KeUnstackDetachProcess(&ApcState);
  if ( v21 < 0 )
  {
    if ( (byte_140087205 & 0x40) != 0 )
    {
      v35 = VidMmUpgradeAllocationChunkFailed;
      goto LABEL_57;
    }
  }
  else if ( (byte_140087205 & 0x40) != 0 )
  {
    v35 = VidMmUpgradeAllocationChunkEnd;
LABEL_57:
    McTemplateK0_EtwWriteTransfer(v34, v35);
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x1400c4b08  mov     [rsp+arg_10], rbx
0x1400c4b0d  mov     [rsp+arg_18], rsi
0x1400c4b12  push    rdi
0x1400c4b13  push    r12
0x1400c4b15  push    r13
0x1400c4b17  push    r14
0x1400c4b19  push    r15
0x1400c4b1b  sub     rsp, 130h
0x1400c4b22  mov     rax, cs:__security_cookie
0x1400c4b29  xor     rax, rsp
0x1400c4b2c  mov     [rsp+158h+var_38], rax
0x1400c4b34  mov     rbx, rdx
0x1400c4b37  mov     r13, [rcx]
0x1400c4b3a  mov     [rsp+158h+var_B8], r13
0x1400c4b42  lea     rsi, [r13+9F10h]
0x1400c4b49  mov     [rsp+158h+var_B0], rsi
0x1400c4b51  mov     r8, [rsi]
0x1400c4b54  mov     [rsp+158h+var_E8], r8
0x1400c4b59  mov     [rsp+158h+var_A8], r8
0x1400c4b61  mov     rdx, [rsi+8]
0x1400c4b65  sub     rdx, r8
0x1400c4b68  mov     [rsp+158h+var_F0], rdx
0x1400c4b6d  mov     [rsp+158h+var_A0], rdx
0x1400c4b75  lea     r9, [rbx+30h]
0x1400c4b79  mov     [rsp+158h+var_D0], r9
0x1400c4b81  mov     rax, [r9]
0x1400c4b84  mov     r15, [rax+10h]
0x1400c4b88  add     r15, r8
0x1400c4b8b  lea     r12, [r15+rdx]
0x1400c4b8f  mov     dil, 40h ; '@'
0x1400c4b92  test    cs:byte_140087205, dil
0x1400c4b99  jz      short loc_1400C4BC1
0x1400c4b9b  mov     [rsp+158h+var_128], r8
0x1400c4ba0  mov     [rsp+158h+var_130], r15
0x1400c4ba5  mov     qword ptr [rsp+158h+var_138], rdx
0x1400c4baa  mov     r9, rbx
0x1400c4bad  lea     rdx, VidMmUpgradeAllocationChunkStart
0x1400c4bb4  call    McTemplateK0ppxx_EtwWriteTransfer
0x1400c4bb9  mov     r9, [rsp+158h+var_D0]
0x1400c4bc1  add     r15, 0FFFFh
0x1400c4bc8  mov     rax, 0FFFFFFFFFFFF0000h
0x1400c4bcf  and     r15, rax
0x1400c4bd2  mov     [rsp+158h+var_98], r15
0x1400c4bda  and     r12, rax
0x1400c4bdd  mov     [rsp+158h+var_D8], r12
0x1400c4be5  cmp     r15, r12
0x1400c4be8  jb      short loc_1400C4C04
0x1400c4bea  mov     rax, [rsi+8]
0x1400c4bee  mov     [rsi], rax
0x1400c4bf1  mov     rdx, [rsi+48h]; struct VIDMM_GLOBAL_ALLOC *
0x1400c4bf5  mov     rcx, r13; this
0x1400c4bf8  call    ?StopUpgradingAllocation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::StopUpgradingAllocation(VIDMM_GLOBAL_ALLOC *)
0x1400c4bfd  xor     eax, eax
0x1400c4bff  jmp     loc_1400C52C1
0x1400c4c04  xorps   xmm0, xmm0
0x1400c4c07  movups  xmmword ptr [rsp+158h+ApcState.ApcListHead.Flink], xmm0
0x1400c4c0f  movups  xmmword ptr [rsp+158h+ApcState.ApcListHead.Flink+10h], xmm0
0x1400c4c17  movups  xmmword ptr [rsp+158h+ApcState.Process], xmm0
0x1400c4c1f  mov     rax, [r9]
0x1400c4c22  mov     r14, [rax+8]
0x1400c4c26  mov     [rsp+158h+var_E0], r14
0x1400c4c2b  mov     [rsp+158h+var_90], r14
0x1400c4c33  lea     rcx, [r13+18h]
0x1400c4c37  mov     [rsp+158h+var_C8], rcx
0x1400c4c3f  mov     rax, [rbx]
0x1400c4c42  mov     r8d, [rax+3Ch]
0x1400c4c46  shr     r8d, 2
0x1400c4c4a  and     r8d, 3Fh; unsigned int
0x1400c4c4e  mov     rdx, [rcx]
0x1400c4c51  mov     edx, [rdx+0F0h]; unsigned int
0x1400c4c57  mov     rcx, r14; this
0x1400c4c5a  call    ?GetVirtualAddressAllocator@VIDMM_PROCESS@@QEAAPEAVCVirtualAddressAllocator@@KI@Z; VIDMM_PROCESS::GetVirtualAddressAllocator(ulong,uint)
0x1400c4c5f  mov     [rsp+158h+var_100], rax
0x1400c4c64  lea     rdx, [rsp+158h+ApcState]; ApcState
0x1400c4c6c  mov     rcx, [r14+10h]; PROCESS
0x1400c4c70  call    cs:__imp_KeStackAttachProcess
0x1400c4c77  nop     dword ptr [rax+rax+00h]
0x1400c4c7c  mov     rcx, [rbx+0E8h]
0x1400c4c83  mov     rdx, [rcx]
0x1400c4c86  mov     rax, [rdx+58h]
0x1400c4c8a  call    _guard_dispatch_icall
0x1400c4c8f  xor     r14d, r14d
0x1400c4c92  cmp     [rsi+89h], r14b
0x1400c4c99  jnz     short loc_1400C4CCE
0x1400c4c9b  test    cs:byte_140087205, dil
0x1400c4ca2  jz      short loc_1400C4CB0
0x1400c4ca4  lea     rdx, LargePageUpgrade_LargifyStartSuspend
0x1400c4cab  call    McTemplateK0_EtwWriteTransfer
0x1400c4cb0  mov     rdx, [rsp+158h+var_C8]
0x1400c4cb8  mov     rdx, [rdx]
0x1400c4cbb  mov     r8b, 1; bool
0x1400c4cbe  mov     edx, [rdx+0F0h]; unsigned int
0x1400c4cc4  mov     rcx, [rsp+158h+var_E0]; this
0x1400c4cc9  call    ?SuspendResumeProcessGpuMmuContexts@VIDMM_PROCESS@@QEAAXI_N@Z; VIDMM_PROCESS::SuspendResumeProcessGpuMmuContexts(uint,bool)
0x1400c4cce  mov     rcx, r13; struct VIDMM_GLOBAL *
0x1400c4cd1  call    ?VidMmStartFaultAndStall@@YAXPEAVVIDMM_GLOBAL@@@Z; VidMmStartFaultAndStall(VIDMM_GLOBAL *)
0x1400c4cd6  lea     rax, [r13+9F99h]
0x1400c4cdd  mov     [rsp+158h+var_80], rax
0x1400c4ce5  cmp     [rax], r14b
0x1400c4ce8  jnz     short loc_1400C4CFF
0x1400c4cea  test    cs:byte_140087205, dil
0x1400c4cf1  jz      short loc_1400C4D14
0x1400c4cf3  lea     rdx, LargePageUpgrade_LargifyEndSuspend
0x1400c4cfa  call    McTemplateK0_EtwWriteTransfer
0x1400c4cff  test    cs:byte_140087205, dil
0x1400c4d06  jz      short loc_1400C4D14
0x1400c4d08  lea     rdx, LargePageUpgrade_LargifySelect
0x1400c4d0f  call    McTemplateK0_EtwWriteTransfer
0x1400c4d14  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1400c4d19  mov     ecx, [rax+100h]
0x1400c4d1f  test    cl, 4
0x1400c4d22  jz      short loc_1400C4D37
0x1400c4d24  xor     r9d, r9d
0x1400c4d27  mov     r8, rsi
0x1400c4d2a  mov     rdx, [rsp+158h+var_100]; this
0x1400c4d2f  mov     rcx, r15; BaseAddress
0x1400c4d32  call    ValidateGpuPtes
0x1400c4d37  mov     qword ptr [rsp+158h+Interval], r14
0x1400c4d3c  lea     rax, [rsp+158h+Interval]
0x1400c4d41  mov     [rsp+158h+var_130], rax; bool
0x1400c4d46  mov     dword ptr [rsp+158h+var_138], 79h ; 'y'
0x1400c4d4e  xor     r9d, r9d
0x1400c4d51  xor     r8d, r8d
0x1400c4d54  or      edx, 0FFFFFFFFh
0x1400c4d57  mov     rcx, r13
0x1400c4d5a  call    ?StartPreparation@VIDMM_GLOBAL@@QEAAXIPEAVVIDMM_DEVICE@@PEAUVIDMM_ALLOC@@W4VIDMM_OPERATION@@PEAPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@@Z; VIDMM_GLOBAL::StartPreparation(uint,VIDMM_DEVICE *,VIDMM_ALLOC *,VIDMM_OPERATION,VIDMM_PAGING_EXECUTION_CONTEXT * *)
0x1400c4d5f  mov     rax, [rsp+158h+var_F0]
0x1400c4d64  mov     qword ptr [rsp+158h+var_138], rax; unsigned __int64
0x1400c4d69  mov     r9, [rsp+158h+var_E8]; unsigned __int64
0x1400c4d6e  mov     r8, rbx; struct VIDMM_GLOBAL_ALLOC *
0x1400c4d71  mov     rdx, qword ptr [rsp+158h+Interval]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400c4d76  mov     rcx, r13; this
0x1400c4d79  call    ?MakeVirtualAddressRangeNotResidentSubrange@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@_K2_N@Z; VIDMM_GLOBAL::MakeVirtualAddressRangeNotResidentSubrange(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *,unsigned __int64,unsigned __int64,bool)
0x1400c4d7e  mov     [rsp+158h+var_128], r14; struct _VIDSCH_SYNC_OBJECT *
0x1400c4d83  mov     [rsp+158h+var_130], r14; unsigned __int64
0x1400c4d88  mov     [rsp+158h+var_138], r14b; bool
0x1400c4d8d  xor     r9d, r9d; struct _KEVENT *
0x1400c4d90  or      r8d, 0FFFFFFFFh; unsigned int
0x1400c4d94  mov     rdx, qword ptr [rsp+158h+Interval]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400c4d99  mov     rcx, r13; this
0x1400c4d9c  call    ?EndPreparation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@IPEAU_KEVENT@@_N_KPEAU_VIDSCH_SYNC_OBJECT@@@Z; VIDMM_GLOBAL::EndPreparation(VIDMM_PAGING_EXECUTION_CONTEXT *,uint,_KEVENT *,bool,unsigned __int64,_VIDSCH_SYNC_OBJECT *)
0x1400c4da1  test    cs:byte_140087205, dil
0x1400c4da8  jz      short loc_1400C4DB6
0x1400c4daa  lea     rdx, VidMmUpgradeAllocationGpuVaUnmapped
0x1400c4db1  call    McTemplateK0_EtwWriteTransfer
0x1400c4db6  or      r8d, 0FFFFFFFFh; unsigned int
0x1400c4dba  xor     edx, edx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400c4dbc  mov     rcx, r13; this
0x1400c4dbf  call    ?WaitForAllPagingEnginesIdle@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I@Z; VIDMM_GLOBAL::WaitForAllPagingEnginesIdle(VIDMM_PAGING_EXECUTION_CONTEXT *,uint)
0x1400c4dc4  test    cs:byte_140087205, dil
0x1400c4dcb  jz      short loc_1400C4DD9
0x1400c4dcd  lea     rdx, VidMmUpgradeAllocationEnginesIdle
0x1400c4dd4  call    McTemplateK0_EtwWriteTransfer
0x1400c4dd9  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1400c4dde  mov     ecx, [rax+100h]
0x1400c4de4  test    cl, 4
0x1400c4de7  jz      short loc_1400C4DFC
0x1400c4de9  mov     r9b, 1
0x1400c4dec  mov     r8, rsi
0x1400c4def  mov     rdx, [rsp+158h+var_100]; this
0x1400c4df4  mov     rcx, r15; BaseAddress
0x1400c4df7  call    ValidateGpuPtes
0x1400c4dfc  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1400c4e01  mov     ecx, [rax+100h]
0x1400c4e07  test    cl, 2
0x1400c4e0a  jz      short loc_1400C4E6A
0x1400c4e0c  mov     r8, r12
0x1400c4e0f  sub     r8, r15; Size
0x1400c4e12  xor     edx, edx; Val
0x1400c4e14  mov     rcx, r15; void *
0x1400c4e17  call    memset
0x1400c4e1c  mov     qword ptr [rsp+158h+var_138], rsi
0x1400c4e21  mov     r9, [rsp+158h+var_100]
0x1400c4e26  mov     r8, rbx
0x1400c4e29  mov     rdx, r12
0x1400c4e2c  mov     rcx, r15
0x1400c4e2f  call    ValidateAllocationZeroed
0x1400c4e34  mov     qword ptr [rsp+158h+Interval], 0FFFFFFFFFFFE7960h
0x1400c4e3d  lea     r8, [rsp+158h+Interval]; Interval
0x1400c4e42  xor     edx, edx; Alertable
0x1400c4e44  xor     ecx, ecx; WaitMode
0x1400c4e46  call    cs:__imp_KeDelayExecutionThread
0x1400c4e4d  nop     dword ptr [rax+rax+00h]
0x1400c4e52  mov     qword ptr [rsp+158h+var_138], rsi
0x1400c4e57  mov     r9, [rsp+158h+var_100]
0x1400c4e5c  mov     r8, rbx
0x1400c4e5f  mov     rdx, r12
0x1400c4e62  mov     rcx, r15
0x1400c4e65  call    ValidateAllocationZeroed
0x1400c4e6a  mov     ecx, [rsi+58h]
0x1400c4e6d  mov     rax, [rsi+70h]
0x1400c4e71  mov     rax, [rax+rcx*8]
0x1400c4e75  mov     [rsp+158h+MemoryDescriptorList], rax
0x1400c4e7d  mov     [rsp+158h+var_88], rax
0x1400c4e85  mov     rcx, rax; MemoryDescriptorList
0x1400c4e88  call    cs:__imp_MmUnlockPages
0x1400c4e8f  nop     dword ptr [rax+rax+00h]
0x1400c4e94  test    cs:byte_140087205, dil
0x1400c4e9b  jz      short loc_1400C4EA9
0x1400c4e9d  lea     rdx, VidMmUpgradeAllocationChunkUnlocked
0x1400c4ea4  call    McTemplateK0_EtwWriteTransfer
0x1400c4ea9  mov     [rsp+158h+var_F8], 10h
0x1400c4eb1  mov     [rsp+158h+var_78], r15
0x1400c4eb9  mov     rax, r12
0x1400c4ebc  sub     rax, r15
0x1400c4ebf  mov     qword ptr [rsp+158h+Interval], rax
0x1400c4ec4  mov     [rsp+158h+var_70], rax
0x1400c4ecc  mov     [rsp+158h+var_10C], r14d
0x1400c4ed1  mov     [rsp+158h+var_108], r14d
0x1400c4ed6  mov     [rsp+158h+var_110], r14d
0x1400c4edb  mov     [rsp+158h+var_104], r14d
0x1400c4ee0  lea     r9, [rsp+158h+var_108]
0x1400c4ee5  lea     r8, [rsp+158h+var_10C]
0x1400c4eea  mov     rdx, r12
0x1400c4eed  mov     rcx, r15; BaseAddress
0x1400c4ef0  call    GetContiguousChunkData
0x1400c4ef5  test    cs:byte_140087205, dil
0x1400c4efc  jz      short loc_1400C4F49
0x1400c4efe  lea     rdx, VidMmUpgradeAllocationLargifyStart
0x1400c4f05  call    McTemplateK0_EtwWriteTransfer
0x1400c4f0a  test    cs:byte_140087205, dil
0x1400c4f11  jz      short loc_1400C4F49
0x1400c4f13  mov     rax, [rbx+188h]
0x1400c4f1a  mov     ecx, [rax]
0x1400c4f1c  shr     ecx, 2
0x1400c4f1f  and     ecx, 1
0x1400c4f22  mov     dword ptr [rsp+158h+var_120], ecx
0x1400c4f26  mov     [rsp+158h+var_128], r14
0x1400c4f2b  mov     [rsp+158h+var_130], r14
0x1400c4f30  mov     rax, qword ptr [rsp+158h+Interval]
0x1400c4f35  mov     qword ptr [rsp+158h+var_138], rax
0x1400c4f3a  mov     r9, rbx
0x1400c4f3d  lea     rdx, LargePageUpgrade_LargifyStart
0x1400c4f44  call    McTemplateK0pxxxt_EtwWriteTransfer
0x1400c4f49  mov     dword ptr [rsp+158h+var_130], 4
0x1400c4f51  lea     rax, [rsp+158h+var_F8]
0x1400c4f56  mov     qword ptr [rsp+158h+var_138], rax
0x1400c4f5b  lea     r9, [rsp+158h+var_78]
0x1400c4f63  mov     edx, 5
0x1400c4f68  lea     r8d, [rdx-4]
0x1400c4f6c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400c4f70  call    cs:__imp_NtSetInformationVirtualMemory
0x1400c4f77  nop     dword ptr [rax+rax+00h]
0x1400c4f7c  mov     r12d, eax
0x1400c4f7f  mov     dword ptr [rsp+158h+Interval], eax
0x1400c4f83  test    eax, eax
0x1400c4f85  jns     short loc_1400C4FDF
0x1400c4f87  mov     ecx, 3
0x1400c4f8c  call    cs:__imp_WdLogSingleEntry0
0x1400c4f93  nop     dword ptr [rax+rax+00h]
0x1400c4f98  mov     cs:WdLogGlobalForLineNumber, 353h
0x1400c4fa2  call    ?GetNumAvailable64KPages@@YA_KXZ; GetNumAvailable64KPages(void)
0x1400c4fa7  test    cs:byte_140087205, dil
0x1400c4fae  jz      short loc_1400C4FF4
0x1400c4fb0  mov     dword ptr [rsp+158h+var_120], r12d
0x1400c4fb5  mov     [rsp+158h+var_128], rax
0x1400c4fba  mov     rax, [rsi+98h]
0x1400c4fc1  mov     [rsp+158h+var_130], rax
0x1400c4fc6  mov     rax, [rsi+90h]
0x1400c4fcd  mov     qword ptr [rsp+158h+var_138], rax
0x1400c4fd2  mov     r9, [rsp+158h+var_70]
0x1400c4fda  call    McTemplateK0xxxxq_EtwWriteTransfer
0x1400c4fdf  test    cs:byte_140087205, dil
0x1400c4fe6  jz      short loc_1400C4FF4
0x1400c4fe8  lea     rdx, VidMmUpgradeAllocationLargifyEnd
0x1400c4fef  call    McTemplateK0_EtwWriteTransfer
0x1400c4ff4  lea     r9, [rsp+158h+var_104]
0x1400c4ff9  lea     r8, [rsp+158h+var_110]
0x1400c4ffe  mov     rdx, [rsp+158h+var_D8]
0x1400c5006  mov     rcx, r15; BaseAddress
0x1400c5009  call    GetContiguousChunkData
0x1400c500e  test    cs:byte_140087205, dil
0x1400c5015  jz      short loc_1400C5067
0x1400c5017  mov     rax, [rbx+188h]
0x1400c501e  mov     edx, [rax]
0x1400c5020  shr     edx, 2
0x1400c5023  and     edx, 1
0x1400c5026  mov     ecx, [rsp+158h+var_110]
0x1400c502a  sub     ecx, [rsp+158h+var_10C]
0x1400c502e  shl     rcx, 10h
0x1400c5032  mov     eax, [rsp+158h+var_108]
0x1400c5036  shl     rax, 10h
0x1400c503a  mov     r8, [rsp+158h+var_D8]
0x1400c5042  sub     r8, r15
0x1400c5045  mov     dword ptr [rsp+158h+var_120], edx
0x1400c5049  mov     [rsp+158h+var_128], rcx
0x1400c504e  mov     [rsp+158h+var_130], rax
0x1400c5053  mov     qword ptr [rsp+158h+var_138], r8
0x1400c5058  mov     r9, rbx
0x1400c505b  lea     rdx, LargePageUpgrade_LargifyEnd
0x1400c5062  call    McTemplateK0pxxxt_EtwWriteTransfer
0x1400c5067  cmp     [rsp+158h+var_104], r14d
0x1400c506c  jnz     short loc_1400C5073
0x1400c506e  bts     dword ptr [rbx+18h], 1Eh
0x1400c5073  test    r12d, r12d
0x1400c5076  js      short loc_1400C507E
0x1400c5078  inc     dword ptr [rsi+0C8h]
0x1400c507e  mov     r8d, [rbx+18h]
0x1400c5082  shr     r8d, 5
0x1400c5086  not     r8d
  ... truncated ...
```
