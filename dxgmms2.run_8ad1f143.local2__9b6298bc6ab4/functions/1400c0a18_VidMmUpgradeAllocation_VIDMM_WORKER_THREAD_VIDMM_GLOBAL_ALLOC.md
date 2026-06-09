# VidMmUpgradeAllocation(VIDMM_WORKER_THREAD *,VIDMM_GLOBAL_ALLOC *)

- ea: `0x1400c0a18`
- end: `0x1400c11ff`
- name: `?VidMmUpgradeAllocation@@YAJPEAUVIDMM_WORKER_THREAD@@PEAUVIDMM_GLOBAL_ALLOC@@@Z`
- size: `2023`
- prototype: `__int64 __fastcall(struct VIDMM_WORKER_THREAD *, struct VIDMM_GLOBAL_ALLOC *)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation`

## callers

- `0x1400ab448`

## callees

- `0x14000d244`
- `0x140017380`
- `0x140038c08`
- `0x14004505c`
- `0x1400486b8`
- `0x140048758`
- `0x140048888`
- `0x140058680`
- `0x140058760`
- `0x1400587c0`
- `0x140058ac0`
- `0x14009b1ac`
- `0x14009c7fc`
- `0x1400a38c4`
- `0x1400b6f1c`
- `0x1400b7144`
- `0x1400bfa08`
- `0x1400bfb14`
- `0x1400c0100`
- `0x1400c045c`
- `0x1400c0528`
- `0x1400c0a18`
- `0x1400e9900`
- `0x1401104b8`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1400c0d56`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400c0d56`
- `ntoskrnl!KeStackAttachProcess` at `0x1400c0b80`
- `ntoskrnl!KeStackAttachProcess` at `0x1400c0b80`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400c1196`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400c1196`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400c0faa`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400c0faa`
- `ntoskrnl!NtSetInformationVirtualMemory` at `0x1400c0e80`
- `ntoskrnl!NtSetInformationVirtualMemory` at `0x1400c0e80`
- `ntoskrnl!MmUnlockPages` at `0x1400c0d98`
- `ntoskrnl!MmUnlockPages` at `0x1400c0d98`
- `watchdog!WdLogSingleEntry0` at `0x1400c0e9c`
- `watchdog!WdLogSingleEntry0` at `0x1400c0e9c`

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
  bool *v36; // [rsp+30h] [rbp-128h]
  __int64 v37; // [rsp+38h] [rbp-120h]
  union _LARGE_INTEGER Interval; // [rsp+40h] [rbp-118h] BYREF
  int v39; // [rsp+48h] [rbp-110h]
  int v40; // [rsp+4Ch] [rbp-10Ch]
  int v41; // [rsp+50h] [rbp-108h]
  int v42; // [rsp+54h] [rbp-104h]
  CVirtualAddressAllocator *VirtualAddressAllocator; // [rsp+58h] [rbp-100h]
  int v44; // [rsp+60h] [rbp-F8h] BYREF
  unsigned __int64 v45; // [rsp+68h] [rbp-F0h]
  unsigned __int64 v46; // [rsp+70h] [rbp-E8h]
  VIDMM_PROCESS *v47; // [rsp+78h] [rbp-E0h]
  unsigned __int64 v48; // [rsp+80h] [rbp-D8h]
  char *v49; // [rsp+88h] [rbp-D0h]
  __int64 v50; // [rsp+90h] [rbp-C8h]
  PMDL MemoryDescriptorList; // [rsp+98h] [rbp-C0h]
  __int64 v52; // [rsp+A0h] [rbp-B8h]
  __int64 v53; // [rsp+A8h] [rbp-B0h]
  unsigned __int64 v54; // [rsp+B0h] [rbp-A8h]
  unsigned __int64 v55; // [rsp+B8h] [rbp-A0h]
  void *v56; // [rsp+C0h] [rbp-98h]
  VIDMM_PROCESS *v57; // [rsp+C8h] [rbp-90h]
  PMDL v58; // [rsp+D0h] [rbp-88h]
  _BYTE *v59; // [rsp+D8h] [rbp-80h]
  void *v60; // [rsp+E0h] [rbp-78h] BYREF
  unsigned __int64 v61; // [rsp+E8h] [rbp-70h]
  struct _KAPC_STATE ApcState; // [rsp+F0h] [rbp-68h] BYREF

  v3 = *(_QWORD *)a1;
  v52 = v3;
  v4 = (_QWORD *)(v3 + 40720);
  v53 = v3 + 40720;
  v5 = *(_QWORD *)(v3 + 40720);
  v46 = v5;
  v54 = v5;
  v6 = *(_QWORD *)(v3 + 40728) - v5;
  v45 = v6;
  v55 = v6;
  v7 = (char *)a2 + 48;
  v49 = (char *)a2 + 48;
  v8 = v5 + *(_QWORD *)(*((_QWORD *)a2 + 6) + 16LL);
  v9 = v8 + v6;
  if ( (byte_140086205 & 0x40) != 0 )
  {
    McTemplateK0ppxx_EtwWriteTransfer(
      (_DWORD)a1,
      (unsigned int)VidMmUpgradeAllocationChunkStart,
      v5,
      (_DWORD)a2,
      v6,
      v8,
      v5);
    v7 = v49;
  }
  v10 = (void *)((v8 + 0xFFFF) & 0xFFFFFFFFFFFF0000uLL);
  v56 = v10;
  v11 = v9 & 0xFFFFFFFFFFFF0000uLL;
  v48 = v11;
  if ( (unsigned __int64)v10 >= v11 )
  {
    *v4 = *(_QWORD *)(v3 + 40728);
    VIDMM_GLOBAL::StopUpgradingAllocation((VIDMM_GLOBAL *)v3, *(struct VIDMM_GLOBAL_ALLOC **)(v3 + 40792));
    return 0;
  }
  memset(&ApcState, 0, sizeof(ApcState));
  v47 = *(VIDMM_PROCESS **)(*(_QWORD *)v7 + 8LL);
  v57 = v47;
  v50 = v3 + 24;
  VirtualAddressAllocator = VIDMM_PROCESS::GetVirtualAddressAllocator(
                              v47,
                              *(_DWORD *)(*(_QWORD *)(v3 + 24) + 240LL),
                              (*(_DWORD *)(*(_QWORD *)a2 + 60LL) >> 2) & 0x3F);
  KeStackAttachProcess(*((PRKPROCESS *)v47 + 2), &ApcState);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 29) + 88LL))(*((_QWORD *)a2 + 29));
  if ( !*(_BYTE *)(v3 + 40857) )
  {
    if ( (byte_140086205 & 0x40) != 0 )
      McTemplateK0_EtwWriteTransfer(v13, LargePageUpgrade_LargifyStartSuspend);
    VIDMM_PROCESS::SuspendResumeProcessGpuMmuContexts(v47, *(_DWORD *)(*(_QWORD *)v50 + 240LL), 1);
  }
  VidMmStartFaultAndStall((struct VIDMM_GLOBAL *)v3);
  v59 = (_BYTE *)(v3 + 40857);
  if ( !*(_BYTE *)(v3 + 40857) )
  {
    if ( (byte_140086205 & 0x40) == 0 )
      goto LABEL_14;
    McTemplateK0_EtwWriteTransfer(v14, LargePageUpgrade_LargifyEndSuspend);
  }
  if ( (byte_140086205 & 0x40) != 0 )
    McTemplateK0_EtwWriteTransfer(v14, LargePageUpgrade_LargifySelect);
LABEL_14:
  if ( (*((_DWORD *)DXGGLOBAL::GetGlobal() + 64) & 4) != 0 )
    ValidateGpuPtes(v10, VirtualAddressAllocator);
  Interval.QuadPart = 0;
  VIDMM_GLOBAL::StartPreparation(v3, 0xFFFFFFFFLL, 0, 0, 121);
  VIDMM_GLOBAL::MakeVirtualAddressRangeNotResidentSubrange(
    (VIDMM_GLOBAL *)v3,
    (struct VIDMM_PAGING_EXECUTION_CONTEXT *)Interval.QuadPart,
    a2,
    v46,
    v45,
    (bool)&Interval);
  VIDMM_GLOBAL::EndPreparation(
    (VIDMM_GLOBAL *)v3,
    (struct VIDMM_PAGING_EXECUTION_CONTEXT *)Interval.QuadPart,
    0xFFFFFFFF,
    0,
    0,
    0,
    0);
  if ( (byte_140086205 & 0x40) != 0 )
    McTemplateK0_EtwWriteTransfer(v15, VidMmUpgradeAllocationGpuVaUnmapped);
  VIDMM_GLOBAL::WaitForAllPagingEnginesIdle((VIDMM_GLOBAL *)v3, 0, 0xFFFFFFFF);
  if ( (byte_140086205 & 0x40) != 0 )
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
  v58 = MemoryDescriptorList;
  MmUnlockPages(MemoryDescriptorList);
  if ( (byte_140086205 & 0x40) != 0 )
    McTemplateK0_EtwWriteTransfer(v17, VidMmUpgradeAllocationChunkUnlocked);
  v44 = 16;
  v60 = v10;
  Interval.QuadPart = v11 - (_QWORD)v10;
  v61 = v11 - (_QWORD)v10;
  v40 = 0;
  v41 = 0;
  v39 = 0;
  v42 = 0;
  GetContiguousChunkData(v10);
  if ( (byte_140086205 & 0x40) != 0 )
  {
    McTemplateK0_EtwWriteTransfer(v18, VidMmUpgradeAllocationLargifyStart);
    if ( (byte_140086205 & 0x40) != 0 )
      McTemplateK0pxxxt_EtwWriteTransfer(
        (**((_DWORD **)a2 + 48) >> 2) & 1,
        (unsigned int)LargePageUpgrade_LargifyStart,
        v19,
        (_DWORD)a2,
        Interval.QuadPart,
        0,
        0,
        (**((_DWORD **)a2 + 48) & 4) != 0);
  }
  v21 = NtSetInformationVirtualMemory(-1, 5, 1, &v60, &v44, 4);
  Interval.LowPart = v21;
  if ( v21 < 0 )
  {
    WdLogSingleEntry0(3);
    WdLogGlobalForLineNumber = 851;
    NumAvailable64KPages = GetNumAvailable64KPages();
    if ( (byte_140086205 & 0x40) == 0 )
      goto LABEL_34;
    LODWORD(v37) = v21;
    McTemplateK0xxxxq_EtwWriteTransfer(
      v24,
      v23,
      v25,
      v61,
      *(_QWORD *)(v3 + 40864),
      *(_QWORD *)(v3 + 40872),
      NumAvailable64KPages,
      v37,
      Interval.QuadPart);
  }
  if ( (byte_140086205 & 0x40) != 0 )
    McTemplateK0_EtwWriteTransfer(v20, VidMmUpgradeAllocationLargifyEnd);
LABEL_34:
  GetContiguousChunkData(v10);
  if ( (byte_140086205 & 0x40) != 0 )
    McTemplateK0pxxxt_EtwWriteTransfer(
      (v39 - v40) << 16,
      (unsigned int)LargePageUpgrade_LargifyEnd,
      v48 - (_DWORD)v10,
      (_DWORD)a2,
      v48 - (_BYTE)v10,
      0,
      0,
      (**((_DWORD **)a2 + 48) & 4) != 0);
  if ( !v42 )
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
  if ( (byte_140086205 & 0x40) != 0 )
    McTemplateK0_EtwWriteTransfer(v28, VidMmUpgradeAllocationChunkLocked);
  v29 = *(_QWORD *)(*(_QWORD *)v49 + 32LL);
  Interval.QuadPart = 0;
  VIDMM_GLOBAL::StartPreparation(v3, 0xFFFFFFFFLL, 0, 0, 206);
  OneVirtualAddressRangeResident = VIDMM_GLOBAL::MakeOneVirtualAddressRangeResident(
                                     (VIDMM_GLOBAL *)v3,
                                     (struct VIDMM_PAGING_EXECUTION_CONTEXT *)Interval.QuadPart,
                                     (struct VIDMM_ALLOC *)(v29 - 40),
                                     v46,
                                     v45,
                                     (struct VIDMM_ALLOC **)&Interval,
                                     v36);
  VIDMM_GLOBAL::EndPreparation(
    (VIDMM_GLOBAL *)v3,
    (struct VIDMM_PAGING_EXECUTION_CONTEXT *)Interval.QuadPart,
    0xFFFFFFFF,
    0,
    0,
    0,
    0);
  if ( (byte_140086205 & 0x40) != 0 )
    McTemplateK0_EtwWriteTransfer(v31, VidMmUpgradeAllocationGpuVaMapped);
  if ( OneVirtualAddressRangeResident >= 0 )
  {
    VIDMM_GLOBAL::WaitForAllPagingEnginesIdle((VIDMM_GLOBAL *)v3, 0, 0xFFFFFFFF);
    if ( (*((_DWORD *)DXGGLOBAL::GetGlobal() + 64) & 4) != 0 )
      ValidateGpuPtes(v10, VirtualAddressAllocator);
    if ( (byte_140086205 & 0x40) != 0 )
      McTemplateK0_EtwWriteTransfer(v32, VidMmUpgradeAllocationEnginesIdle);
    VidMmEndFaultAndStall((struct VIDMM_GLOBAL *)v3);
    if ( !*v59 )
    {
      VIDMM_PROCESS::SuspendResumeProcessGpuMmuContexts(v47, *(_DWORD *)(*(_QWORD *)v50 + 240LL), 0);
      if ( (byte_140086205 & 0x40) != 0 )
        McTemplateK0_EtwWriteTransfer(v33, LargePageUpgrade_LargifyResume);
    }
  }
  KeUnstackDetachProcess(&ApcState);
  if ( v21 < 0 )
  {
    if ( (byte_140086205 & 0x40) != 0 )
    {
      v35 = VidMmUpgradeAllocationChunkFailed;
      goto LABEL_57;
    }
  }
  else if ( (byte_140086205 & 0x40) != 0 )
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
0x1400c0a18  mov     [rsp+arg_10], rbx
0x1400c0a1d  mov     [rsp+arg_18], rsi
0x1400c0a22  push    rdi
0x1400c0a23  push    r12
0x1400c0a25  push    r13
0x1400c0a27  push    r14
0x1400c0a29  push    r15
0x1400c0a2b  sub     rsp, 130h
0x1400c0a32  mov     rax, cs:__security_cookie
0x1400c0a39  xor     rax, rsp
0x1400c0a3c  mov     [rsp+158h+var_38], rax
0x1400c0a44  mov     rbx, rdx
0x1400c0a47  mov     r13, [rcx]
0x1400c0a4a  mov     [rsp+158h+var_B8], r13
0x1400c0a52  lea     rsi, [r13+9F10h]
0x1400c0a59  mov     [rsp+158h+var_B0], rsi
0x1400c0a61  mov     r8, [rsi]
0x1400c0a64  mov     [rsp+158h+var_E8], r8
0x1400c0a69  mov     [rsp+158h+var_A8], r8
0x1400c0a71  mov     rdx, [rsi+8]
0x1400c0a75  sub     rdx, r8
0x1400c0a78  mov     [rsp+158h+var_F0], rdx
0x1400c0a7d  mov     [rsp+158h+var_A0], rdx
0x1400c0a85  lea     r9, [rbx+30h]
0x1400c0a89  mov     [rsp+158h+var_D0], r9
0x1400c0a91  mov     rax, [r9]
0x1400c0a94  mov     r15, [rax+10h]
0x1400c0a98  add     r15, r8
0x1400c0a9b  lea     r12, [r15+rdx]
0x1400c0a9f  mov     dil, 40h ; '@'
0x1400c0aa2  test    cs:byte_140086205, dil
0x1400c0aa9  jz      short loc_1400C0AD1
0x1400c0aab  mov     [rsp+158h+var_128], r8
0x1400c0ab0  mov     [rsp+158h+var_130], r15
0x1400c0ab5  mov     qword ptr [rsp+158h+var_138], rdx
0x1400c0aba  mov     r9, rbx
0x1400c0abd  lea     rdx, VidMmUpgradeAllocationChunkStart
0x1400c0ac4  call    McTemplateK0ppxx_EtwWriteTransfer
0x1400c0ac9  mov     r9, [rsp+158h+var_D0]
0x1400c0ad1  add     r15, 0FFFFh
0x1400c0ad8  mov     rax, 0FFFFFFFFFFFF0000h
0x1400c0adf  and     r15, rax
0x1400c0ae2  mov     [rsp+158h+var_98], r15
0x1400c0aea  and     r12, rax
0x1400c0aed  mov     [rsp+158h+var_D8], r12
0x1400c0af5  cmp     r15, r12
0x1400c0af8  jb      short loc_1400C0B14
0x1400c0afa  mov     rax, [rsi+8]
0x1400c0afe  mov     [rsi], rax
0x1400c0b01  mov     rdx, [rsi+48h]; struct VIDMM_GLOBAL_ALLOC *
0x1400c0b05  mov     rcx, r13; this
0x1400c0b08  call    ?StopUpgradingAllocation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::StopUpgradingAllocation(VIDMM_GLOBAL_ALLOC *)
0x1400c0b0d  xor     eax, eax
0x1400c0b0f  jmp     loc_1400C11D1
0x1400c0b14  xorps   xmm0, xmm0
0x1400c0b17  movups  xmmword ptr [rsp+158h+ApcState.ApcListHead.Flink], xmm0
0x1400c0b1f  movups  xmmword ptr [rsp+158h+ApcState.ApcListHead.Flink+10h], xmm0
0x1400c0b27  movups  xmmword ptr [rsp+158h+ApcState.Process], xmm0
0x1400c0b2f  mov     rax, [r9]
0x1400c0b32  mov     r14, [rax+8]
0x1400c0b36  mov     [rsp+158h+var_E0], r14
0x1400c0b3b  mov     [rsp+158h+var_90], r14
0x1400c0b43  lea     rcx, [r13+18h]
0x1400c0b47  mov     [rsp+158h+var_C8], rcx
0x1400c0b4f  mov     rax, [rbx]
0x1400c0b52  mov     r8d, [rax+3Ch]
0x1400c0b56  shr     r8d, 2
0x1400c0b5a  and     r8d, 3Fh; unsigned int
0x1400c0b5e  mov     rdx, [rcx]
0x1400c0b61  mov     edx, [rdx+0F0h]; unsigned int
0x1400c0b67  mov     rcx, r14; this
0x1400c0b6a  call    ?GetVirtualAddressAllocator@VIDMM_PROCESS@@QEAAPEAVCVirtualAddressAllocator@@KI@Z; VIDMM_PROCESS::GetVirtualAddressAllocator(ulong,uint)
0x1400c0b6f  mov     [rsp+158h+var_100], rax
0x1400c0b74  lea     rdx, [rsp+158h+ApcState]; ApcState
0x1400c0b7c  mov     rcx, [r14+10h]; PROCESS
0x1400c0b80  call    cs:__imp_KeStackAttachProcess
0x1400c0b87  nop     dword ptr [rax+rax+00h]
0x1400c0b8c  mov     rcx, [rbx+0E8h]
0x1400c0b93  mov     rdx, [rcx]
0x1400c0b96  mov     rax, [rdx+58h]
0x1400c0b9a  call    _guard_dispatch_icall
0x1400c0b9f  xor     r14d, r14d
0x1400c0ba2  cmp     [rsi+89h], r14b
0x1400c0ba9  jnz     short loc_1400C0BDE
0x1400c0bab  test    cs:byte_140086205, dil
0x1400c0bb2  jz      short loc_1400C0BC0
0x1400c0bb4  lea     rdx, LargePageUpgrade_LargifyStartSuspend
0x1400c0bbb  call    McTemplateK0_EtwWriteTransfer
0x1400c0bc0  mov     rdx, [rsp+158h+var_C8]
0x1400c0bc8  mov     rdx, [rdx]
0x1400c0bcb  mov     r8b, 1; bool
0x1400c0bce  mov     edx, [rdx+0F0h]; unsigned int
0x1400c0bd4  mov     rcx, [rsp+158h+var_E0]; this
0x1400c0bd9  call    ?SuspendResumeProcessGpuMmuContexts@VIDMM_PROCESS@@QEAAXI_N@Z; VIDMM_PROCESS::SuspendResumeProcessGpuMmuContexts(uint,bool)
0x1400c0bde  mov     rcx, r13; struct VIDMM_GLOBAL *
0x1400c0be1  call    ?VidMmStartFaultAndStall@@YAXPEAVVIDMM_GLOBAL@@@Z; VidMmStartFaultAndStall(VIDMM_GLOBAL *)
0x1400c0be6  lea     rax, [r13+9F99h]
0x1400c0bed  mov     [rsp+158h+var_80], rax
0x1400c0bf5  cmp     [rax], r14b
0x1400c0bf8  jnz     short loc_1400C0C0F
0x1400c0bfa  test    cs:byte_140086205, dil
0x1400c0c01  jz      short loc_1400C0C24
0x1400c0c03  lea     rdx, LargePageUpgrade_LargifyEndSuspend
0x1400c0c0a  call    McTemplateK0_EtwWriteTransfer
0x1400c0c0f  test    cs:byte_140086205, dil
0x1400c0c16  jz      short loc_1400C0C24
0x1400c0c18  lea     rdx, LargePageUpgrade_LargifySelect
0x1400c0c1f  call    McTemplateK0_EtwWriteTransfer
0x1400c0c24  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1400c0c29  mov     ecx, [rax+100h]
0x1400c0c2f  test    cl, 4
0x1400c0c32  jz      short loc_1400C0C47
0x1400c0c34  xor     r9d, r9d
0x1400c0c37  mov     r8, rsi
0x1400c0c3a  mov     rdx, [rsp+158h+var_100]; this
0x1400c0c3f  mov     rcx, r15; BaseAddress
0x1400c0c42  call    ValidateGpuPtes
0x1400c0c47  mov     qword ptr [rsp+158h+Interval], r14
0x1400c0c4c  lea     rax, [rsp+158h+Interval]
0x1400c0c51  mov     [rsp+158h+var_130], rax; bool
0x1400c0c56  mov     dword ptr [rsp+158h+var_138], 79h ; 'y'
0x1400c0c5e  xor     r9d, r9d
0x1400c0c61  xor     r8d, r8d
0x1400c0c64  or      edx, 0FFFFFFFFh
0x1400c0c67  mov     rcx, r13
0x1400c0c6a  call    ?StartPreparation@VIDMM_GLOBAL@@QEAAXIPEAVVIDMM_DEVICE@@PEAUVIDMM_ALLOC@@W4VIDMM_OPERATION@@PEAPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@@Z; VIDMM_GLOBAL::StartPreparation(uint,VIDMM_DEVICE *,VIDMM_ALLOC *,VIDMM_OPERATION,VIDMM_PAGING_EXECUTION_CONTEXT * *)
0x1400c0c6f  mov     rax, [rsp+158h+var_F0]
0x1400c0c74  mov     qword ptr [rsp+158h+var_138], rax; unsigned __int64
0x1400c0c79  mov     r9, [rsp+158h+var_E8]; unsigned __int64
0x1400c0c7e  mov     r8, rbx; struct VIDMM_GLOBAL_ALLOC *
0x1400c0c81  mov     rdx, qword ptr [rsp+158h+Interval]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400c0c86  mov     rcx, r13; this
0x1400c0c89  call    ?MakeVirtualAddressRangeNotResidentSubrange@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@_K2_N@Z; VIDMM_GLOBAL::MakeVirtualAddressRangeNotResidentSubrange(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *,unsigned __int64,unsigned __int64,bool)
0x1400c0c8e  mov     [rsp+158h+var_128], r14; struct _VIDSCH_SYNC_OBJECT *
0x1400c0c93  mov     [rsp+158h+var_130], r14; unsigned __int64
0x1400c0c98  mov     [rsp+158h+var_138], r14b; bool
0x1400c0c9d  xor     r9d, r9d; Event
0x1400c0ca0  or      r8d, 0FFFFFFFFh; unsigned int
0x1400c0ca4  mov     rdx, qword ptr [rsp+158h+Interval]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400c0ca9  mov     rcx, r13; this
0x1400c0cac  call    ?EndPreparation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@IPEAU_KEVENT@@_N_KPEAU_VIDSCH_SYNC_OBJECT@@@Z; VIDMM_GLOBAL::EndPreparation(VIDMM_PAGING_EXECUTION_CONTEXT *,uint,_KEVENT *,bool,unsigned __int64,_VIDSCH_SYNC_OBJECT *)
0x1400c0cb1  test    cs:byte_140086205, dil
0x1400c0cb8  jz      short loc_1400C0CC6
0x1400c0cba  lea     rdx, VidMmUpgradeAllocationGpuVaUnmapped
0x1400c0cc1  call    McTemplateK0_EtwWriteTransfer
0x1400c0cc6  or      r8d, 0FFFFFFFFh; unsigned int
0x1400c0cca  xor     edx, edx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400c0ccc  mov     rcx, r13; this
0x1400c0ccf  call    ?WaitForAllPagingEnginesIdle@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I@Z; VIDMM_GLOBAL::WaitForAllPagingEnginesIdle(VIDMM_PAGING_EXECUTION_CONTEXT *,uint)
0x1400c0cd4  test    cs:byte_140086205, dil
0x1400c0cdb  jz      short loc_1400C0CE9
0x1400c0cdd  lea     rdx, VidMmUpgradeAllocationEnginesIdle
0x1400c0ce4  call    McTemplateK0_EtwWriteTransfer
0x1400c0ce9  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1400c0cee  mov     ecx, [rax+100h]
0x1400c0cf4  test    cl, 4
0x1400c0cf7  jz      short loc_1400C0D0C
0x1400c0cf9  mov     r9b, 1
0x1400c0cfc  mov     r8, rsi
0x1400c0cff  mov     rdx, [rsp+158h+var_100]; this
0x1400c0d04  mov     rcx, r15; BaseAddress
0x1400c0d07  call    ValidateGpuPtes
0x1400c0d0c  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1400c0d11  mov     ecx, [rax+100h]
0x1400c0d17  test    cl, 2
0x1400c0d1a  jz      short loc_1400C0D7A
0x1400c0d1c  mov     r8, r12
0x1400c0d1f  sub     r8, r15; Size
0x1400c0d22  xor     edx, edx; Val
0x1400c0d24  mov     rcx, r15; void *
0x1400c0d27  call    memset
0x1400c0d2c  mov     qword ptr [rsp+158h+var_138], rsi
0x1400c0d31  mov     r9, [rsp+158h+var_100]
0x1400c0d36  mov     r8, rbx
0x1400c0d39  mov     rdx, r12
0x1400c0d3c  mov     rcx, r15
0x1400c0d3f  call    ValidateAllocationZeroed
0x1400c0d44  mov     qword ptr [rsp+158h+Interval], 0FFFFFFFFFFFE7960h
0x1400c0d4d  lea     r8, [rsp+158h+Interval]; Interval
0x1400c0d52  xor     edx, edx; Alertable
0x1400c0d54  xor     ecx, ecx; WaitMode
0x1400c0d56  call    cs:__imp_KeDelayExecutionThread
0x1400c0d5d  nop     dword ptr [rax+rax+00h]
0x1400c0d62  mov     qword ptr [rsp+158h+var_138], rsi
0x1400c0d67  mov     r9, [rsp+158h+var_100]
0x1400c0d6c  mov     r8, rbx
0x1400c0d6f  mov     rdx, r12
0x1400c0d72  mov     rcx, r15
0x1400c0d75  call    ValidateAllocationZeroed
0x1400c0d7a  mov     ecx, [rsi+58h]
0x1400c0d7d  mov     rax, [rsi+70h]
0x1400c0d81  mov     rax, [rax+rcx*8]
0x1400c0d85  mov     [rsp+158h+MemoryDescriptorList], rax
0x1400c0d8d  mov     [rsp+158h+var_88], rax
0x1400c0d95  mov     rcx, rax; MemoryDescriptorList
0x1400c0d98  call    cs:__imp_MmUnlockPages
0x1400c0d9f  nop     dword ptr [rax+rax+00h]
0x1400c0da4  test    cs:byte_140086205, dil
0x1400c0dab  jz      short loc_1400C0DB9
0x1400c0dad  lea     rdx, VidMmUpgradeAllocationChunkUnlocked
0x1400c0db4  call    McTemplateK0_EtwWriteTransfer
0x1400c0db9  mov     [rsp+158h+var_F8], 10h
0x1400c0dc1  mov     [rsp+158h+var_78], r15
0x1400c0dc9  mov     rax, r12
0x1400c0dcc  sub     rax, r15
0x1400c0dcf  mov     qword ptr [rsp+158h+Interval], rax
0x1400c0dd4  mov     [rsp+158h+var_70], rax
0x1400c0ddc  mov     [rsp+158h+var_10C], r14d
0x1400c0de1  mov     [rsp+158h+var_108], r14d
0x1400c0de6  mov     [rsp+158h+var_110], r14d
0x1400c0deb  mov     [rsp+158h+var_104], r14d
0x1400c0df0  lea     r9, [rsp+158h+var_108]
0x1400c0df5  lea     r8, [rsp+158h+var_10C]
0x1400c0dfa  mov     rdx, r12
0x1400c0dfd  mov     rcx, r15; BaseAddress
0x1400c0e00  call    GetContiguousChunkData
0x1400c0e05  test    cs:byte_140086205, dil
0x1400c0e0c  jz      short loc_1400C0E59
0x1400c0e0e  lea     rdx, VidMmUpgradeAllocationLargifyStart
0x1400c0e15  call    McTemplateK0_EtwWriteTransfer
0x1400c0e1a  test    cs:byte_140086205, dil
0x1400c0e21  jz      short loc_1400C0E59
0x1400c0e23  mov     rax, [rbx+180h]
0x1400c0e2a  mov     ecx, [rax]
0x1400c0e2c  shr     ecx, 2
0x1400c0e2f  and     ecx, 1
0x1400c0e32  mov     dword ptr [rsp+158h+var_120], ecx
0x1400c0e36  mov     [rsp+158h+var_128], r14
0x1400c0e3b  mov     [rsp+158h+var_130], r14
0x1400c0e40  mov     rax, qword ptr [rsp+158h+Interval]
0x1400c0e45  mov     qword ptr [rsp+158h+var_138], rax
0x1400c0e4a  mov     r9, rbx
0x1400c0e4d  lea     rdx, LargePageUpgrade_LargifyStart
0x1400c0e54  call    McTemplateK0pxxxt_EtwWriteTransfer
0x1400c0e59  mov     dword ptr [rsp+158h+var_130], 4
0x1400c0e61  lea     rax, [rsp+158h+var_F8]
0x1400c0e66  mov     qword ptr [rsp+158h+var_138], rax
0x1400c0e6b  lea     r9, [rsp+158h+var_78]
0x1400c0e73  mov     edx, 5
0x1400c0e78  lea     r8d, [rdx-4]
0x1400c0e7c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400c0e80  call    cs:__imp_NtSetInformationVirtualMemory
0x1400c0e87  nop     dword ptr [rax+rax+00h]
0x1400c0e8c  mov     r12d, eax
0x1400c0e8f  mov     dword ptr [rsp+158h+Interval], eax
0x1400c0e93  test    eax, eax
0x1400c0e95  jns     short loc_1400C0EEF
0x1400c0e97  mov     ecx, 3
0x1400c0e9c  call    cs:__imp_WdLogSingleEntry0
0x1400c0ea3  nop     dword ptr [rax+rax+00h]
0x1400c0ea8  mov     cs:WdLogGlobalForLineNumber, 353h
0x1400c0eb2  call    ?GetNumAvailable64KPages@@YA_KXZ; GetNumAvailable64KPages(void)
0x1400c0eb7  test    cs:byte_140086205, dil
0x1400c0ebe  jz      short loc_1400C0F04
0x1400c0ec0  mov     dword ptr [rsp+158h+var_120], r12d
0x1400c0ec5  mov     [rsp+158h+var_128], rax
0x1400c0eca  mov     rax, [rsi+98h]
0x1400c0ed1  mov     [rsp+158h+var_130], rax
0x1400c0ed6  mov     rax, [rsi+90h]
0x1400c0edd  mov     qword ptr [rsp+158h+var_138], rax
0x1400c0ee2  mov     r9, [rsp+158h+var_70]
0x1400c0eea  call    McTemplateK0xxxxq_EtwWriteTransfer
0x1400c0eef  test    cs:byte_140086205, dil
0x1400c0ef6  jz      short loc_1400C0F04
0x1400c0ef8  lea     rdx, VidMmUpgradeAllocationLargifyEnd
0x1400c0eff  call    McTemplateK0_EtwWriteTransfer
0x1400c0f04  lea     r9, [rsp+158h+var_104]
0x1400c0f09  lea     r8, [rsp+158h+var_110]
0x1400c0f0e  mov     rdx, [rsp+158h+var_D8]
0x1400c0f16  mov     rcx, r15; BaseAddress
0x1400c0f19  call    GetContiguousChunkData
0x1400c0f1e  test    cs:byte_140086205, dil
0x1400c0f25  jz      short loc_1400C0F77
0x1400c0f27  mov     rax, [rbx+180h]
0x1400c0f2e  mov     edx, [rax]
0x1400c0f30  shr     edx, 2
0x1400c0f33  and     edx, 1
0x1400c0f36  mov     ecx, [rsp+158h+var_110]
0x1400c0f3a  sub     ecx, [rsp+158h+var_10C]
0x1400c0f3e  shl     rcx, 10h
0x1400c0f42  mov     eax, [rsp+158h+var_108]
0x1400c0f46  shl     rax, 10h
0x1400c0f4a  mov     r8, [rsp+158h+var_D8]
0x1400c0f52  sub     r8, r15
0x1400c0f55  mov     dword ptr [rsp+158h+var_120], edx
0x1400c0f59  mov     [rsp+158h+var_128], rcx
0x1400c0f5e  mov     [rsp+158h+var_130], rax
0x1400c0f63  mov     qword ptr [rsp+158h+var_138], r8
0x1400c0f68  mov     r9, rbx
0x1400c0f6b  lea     rdx, LargePageUpgrade_LargifyEnd
0x1400c0f72  call    McTemplateK0pxxxt_EtwWriteTransfer
0x1400c0f77  cmp     [rsp+158h+var_104], r14d
0x1400c0f7c  jnz     short loc_1400C0F83
0x1400c0f7e  bts     dword ptr [rbx+18h], 1Eh
0x1400c0f83  test    r12d, r12d
0x1400c0f86  js      short loc_1400C0F8E
0x1400c0f88  inc     dword ptr [rsi+0C8h]
0x1400c0f8e  mov     r8d, [rbx+18h]
0x1400c0f92  shr     r8d, 5
0x1400c0f96  not     r8d
  ... truncated ...
```
