# RxShadowCommonCompletion

- ea: `0x140013260`
- end: `0x140013513`
- name: `RxShadowCommonCompletion`
- size: `691`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, PIRP Irp)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400250d0`

## callees

- `0x140002120`
- `0x140002170`
- `0x140010660`
- `0x140013260`
- `0x140025198`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400134ad`
- `ntoskrnl!KeSetEvent` at `0x1400134ad`
- `ntoskrnl!MmUnlockPages` at `0x1400133f6`
- `ntoskrnl!MmUnlockPages` at `0x1400133f6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400133bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400133bf`
- `ntoskrnl!IoFreeIrp` at `0x14001341d`
- `ntoskrnl!IoFreeIrp` at `0x14001341d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013327`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013327`

## pseudocode

```c
__int64 __fastcall RxShadowCommonCompletion(PRX_CONTEXT RxContext, PIRP Irp, __int64 a3, __int64 a4)
{
  int RdbssDbgExtension; // r15d
  NTSTATUS v6; // esi
  PIRP v7; // rbp
  KIRQL v9; // al
  struct _MDL *MdlAddress; // r12
  struct _MDL *Next; // rdi

  RdbssDbgExtension = (int)RxContext->RdbssDbgExtension;
  v6 = a3;
  v7 = Irp;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqdD(WPP_GLOBAL_Control->AttachedDevice, Irp, a3, RxContext, Irp, a3, a4);
  }
  if ( v7->MdlAddress == (PMDL)*((_QWORD *)&RxContext->9 + 18)
    && (unsigned __int8)(LOBYTE(RxContext->RealDevice) - 3) <= 1u )
  {
    v7->MdlAddress = 0;
  }
  if ( LOBYTE(RxContext->MRxContext[3]) )
  {
    v9 = KeAcquireSpinLockRaiseToDpc(&SpinLock[24
                                             * (((unsigned __int8)(WORD1(RxContext->LowIoContext.ParamsFor.Locks.Length)
                                                                 % (unsigned int)RxActiveContextNodeBucketSize)
                                               + (unsigned __int8)RxActiveContextNodeBucketSize
                                               * (unsigned __int8)LOWORD(RxContext->LowIoContext.ParamsFor.ReadWrite.Flags))
                                              & 0x3F)]);
    v7 = (PIRP)RxContext->MRxContext[2];
    _m_prefetchw(&RxContext->ScavengerEntry);
    if ( (_InterlockedXor((volatile signed __int32 *)&RxContext->ScavengerEntry, 0) & 2) != 0 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&RxContext->MRxContext[3] + 1, 0xFFFFFFFF) > 1 )
      {
        v7 = 0;
LABEL_14:
        KeReleaseSpinLock(
          &SpinLock[24
                  * (((unsigned __int8)(WORD1(RxContext->LowIoContext.ParamsFor.Locks.Length)
                                      % (unsigned int)RxActiveContextNodeBucketSize)
                    + (unsigned __int8)RxActiveContextNodeBucketSize
                    * (unsigned __int8)LOWORD(RxContext->LowIoContext.ParamsFor.ReadWrite.Flags))
                   & 0x3F)],
          v9);
        goto LABEL_15;
      }
    }
    else
    {
      RxContext->ScavengerEntry.List.Blink = 0;
    }
    RxContext->MRxContext[2] = 0;
    goto LABEL_14;
  }
LABEL_15:
  if ( v7 )
  {
    MdlAddress = v7->MdlAddress;
    if ( MdlAddress )
    {
      do
      {
        if ( MdlAddress == *((struct _MDL **)&RxContext->9 + 18) )
          break;
        Next = MdlAddress->Next;
        MdlAddress->Next = 0;
        MmUnlockPages(MdlAddress);
        RxFreeMdl(MdlAddress);
        MdlAddress = Next;
      }
      while ( Next );
      v7->MdlAddress = 0;
    }
    IoFreeIrp(v7);
  }
  if ( v6 >= 0
    || v6 == -1073741740
    || v6 == -1073741807
    || v6 == -1073741536
    || (*(_DWORD *)(*(_QWORD *)&RxContext->pFcb->UncleanCount + 56LL) & 0x40) == 0 )
  {
    RxContext->InformationToReturn += a4;
    RxContext->StoredStatus = v6;
    if ( (RdbssDbgExtension & 0x1000) != 0 )
    {
      if ( v6 >= 0 || (unsigned __int16)(*((_WORD *)&RxContext->9 + 60) - 2) > 1u )
        RxLowIoCompletion(RxContext);
      else
        RxPostToWorkerThread(
          RxFileSystemDeviceObject,
          HyperCriticalWorkQueue,
          (PRX_WORK_QUEUE_ITEM)&RxContext->SyncEvent,
          (PRX_WORKERTHREAD_ROUTINE)RxLowIoCompletion,
          RxContext);
    }
    else
    {
      LODWORD(RxContext->RdbssDbgExtension) &= ~0x100000u;
      KeSetEvent((PRKEVENT)&RxContext->PrefixClaim.NetRootType, 0, 0);
    }
  }
  else
  {
    RxPostToWorkerThread(
      (PRDBSS_DEVICE_OBJECT)RxContext->NonPagedFcb,
      HyperCriticalWorkQueue,
      (PRX_WORK_QUEUE_ITEM)&RxContext->SyncEvent,
      RxShadowFallbackToMiniRdr,
      RxContext);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x140013260  mov     [rsp+arg_18], rbx
0x140013265  push    rsi
0x140013266  push    r14
0x140013268  push    r15
0x14001326a  sub     rsp, 40h
0x14001326e  mov     r15d, [rcx+78h]
0x140013272  mov     r14, r9
0x140013275  mov     [rsp+58h+arg_0], rbp
0x14001327a  mov     esi, r8d
0x14001327d  mov     rbp, rdx
0x140013280  mov     rbx, rcx
0x140013283  mov     rcx, cs:WPP_GLOBAL_Control
0x14001328a  lea     rax, WPP_GLOBAL_Control
0x140013291  cmp     rcx, rax
0x140013294  jz      short loc_1400132BE
0x140013296  mov     eax, [rcx+2Ch]
0x140013299  test    al, 4
0x14001329b  jz      short loc_1400132BE
0x14001329d  cmp     byte ptr [rcx+29h], 2
0x1400132a1  jb      short loc_1400132BE
0x1400132a3  mov     rcx, [rcx+18h]
0x1400132a7  mov     r9, rbx
0x1400132aa  mov     [rsp+58h+var_28], r14d
0x1400132af  mov     [rsp+58h+var_30], r8d
0x1400132b4  mov     [rsp+58h+pContext], rdx
0x1400132b9  call    WPP_SF_qqdD
0x1400132be  mov     rax, [rbx+220h]
0x1400132c5  cmp     [rbp+8], rax
0x1400132c9  jnz     short loc_1400132DD
0x1400132cb  movzx   eax, byte ptr [rbx+20h]
0x1400132cf  sub     al, 3
0x1400132d1  cmp     al, 1
0x1400132d3  ja      short loc_1400132DD
0x1400132d5  mov     qword ptr [rbp+8], 0
0x1400132dd  cmp     byte ptr [rbx+0D8h], 0
0x1400132e4  mov     [rsp+58h+arg_8], rdi
0x1400132e9  jz      loc_1400133CB
0x1400132ef  movzx   eax, word ptr [rbx+1BAh]
0x1400132f6  lea     rdi, SpinLock
0x1400132fd  movzx   r8d, word ptr [rbx+1B8h]
0x140013305  xor     edx, edx
0x140013307  div     cs:RxActiveContextNodeBucketSize
0x14001330d  imul    r8d, cs:RxActiveContextNodeBucketSize
0x140013315  lea     eax, [rdx+r8]
0x140013319  and     eax, 3Fh
0x14001331c  lea     rcx, [rax+rax*2]
0x140013320  shl     rcx, 6
0x140013324  add     rcx, rdi; SpinLock
0x140013327  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001332e  nop     dword ptr [rax+rax+00h]
0x140013333  mov     rbp, [rbx+0D0h]
0x14001333a  movzx   r9d, al
0x14001333e  prefetchw byte ptr [rbx+80h]
0x140013345  mov     eax, [rbx+80h]
0x14001334b  mov     ecx, eax
0x14001334d  xor     ecx, 0
0x140013350  lock cmpxchg [rbx+80h], ecx
0x140013358  jnz     short loc_14001334B
0x14001335a  test    al, 2
0x14001335c  jz      short loc_140013374
0x14001335e  mov     eax, 0FFFFFFFFh
0x140013363  lock xadd [rbx+0DCh], eax
0x14001336b  sub     eax, 1
0x14001336e  jle     short loc_14001337F
0x140013370  xor     ebp, ebp
0x140013372  jmp     short loc_14001338A
0x140013374  mov     qword ptr [rbx+88h], 0
0x14001337f  mov     qword ptr [rbx+0D0h], 0
0x14001338a  movzx   eax, word ptr [rbx+1BAh]
0x140013391  xor     edx, edx
0x140013393  div     cs:RxActiveContextNodeBucketSize
0x140013399  movzx   r8d, word ptr [rbx+1B8h]
0x1400133a1  imul    r8d, cs:RxActiveContextNodeBucketSize
0x1400133a9  lea     eax, [rdx+r8]
0x1400133ad  movzx   edx, r9b; NewIrql
0x1400133b1  and     eax, 3Fh
0x1400133b4  lea     rcx, [rax+rax*2]
0x1400133b8  shl     rcx, 6
0x1400133bc  add     rcx, rdi; SpinLock
0x1400133bf  call    cs:__imp_KeReleaseSpinLock
0x1400133c6  nop     dword ptr [rax+rax+00h]
0x1400133cb  test    rbp, rbp
0x1400133ce  jz      short loc_14001342E
0x1400133d0  mov     [rsp+58h+arg_10], r12
0x1400133d5  mov     r12, [rbp+8]
0x1400133d9  test    r12, r12
0x1400133dc  jz      short loc_14001341A
0x1400133de  cmp     r12, [rbx+220h]
0x1400133e5  jz      short loc_140013412
0x1400133e7  mov     rdi, [r12]
0x1400133eb  mov     rcx, r12; MemoryDescriptorList
0x1400133ee  mov     qword ptr [r12], 0
0x1400133f6  call    cs:__imp_MmUnlockPages
0x1400133fd  nop     dword ptr [rax+rax+00h]
0x140013402  mov     rcx, r12
0x140013405  call    RxFreeMdl
0x14001340a  mov     r12, rdi
0x14001340d  test    rdi, rdi
0x140013410  jnz     short loc_1400133DE
0x140013412  mov     qword ptr [rbp+8], 0
0x14001341a  mov     rcx, rbp; Irp
0x14001341d  call    cs:__imp_IoFreeIrp
0x140013424  nop     dword ptr [rax+rax+00h]
0x140013429  mov     r12, [rsp+58h+arg_10]
0x14001342e  mov     rdi, [rsp+58h+arg_8]
0x140013433  mov     rbp, [rsp+58h+arg_0]
0x140013438  test    esi, esi
0x14001343a  jns     short loc_140013486
0x14001343c  cmp     esi, 0C0000054h
0x140013442  jz      short loc_140013486
0x140013444  cmp     esi, 0C0000011h
0x14001344a  jz      short loc_140013486
0x14001344c  cmp     esi, 0C0000120h
0x140013452  jz      short loc_140013486
0x140013454  mov     rax, [rbx+38h]
0x140013458  mov     rcx, [rax+78h]
0x14001345c  mov     eax, [rcx+38h]
0x14001345f  test    al, 40h
0x140013461  jz      short loc_140013486
0x140013463  mov     rcx, [rbx+50h]; pMRxDeviceObject
0x140013467  lea     r8, [rbx+130h]; pWorkQueueItem
0x14001346e  lea     r9, RxShadowFallbackToMiniRdr; Routine
0x140013475  mov     [rsp+58h+pContext], rbx; pContext
0x14001347a  mov     edx, 2; WorkQueueType
0x14001347f  call    RxPostToWorkerThread
0x140013484  jmp     short loc_1400134FE
0x140013486  add     [rbx+0B8h], r14
0x14001348d  mov     [rbx+0B0h], esi
0x140013493  bt      r15d, 0Ch
0x140013498  jb      short loc_1400134BB
0x14001349a  and     dword ptr [rbx+78h], 0FFEFFFFFh
0x1400134a1  lea     rcx, [rbx+180h]; Event
0x1400134a8  xor     r8d, r8d; Wait
0x1400134ab  xor     edx, edx; Increment
0x1400134ad  call    cs:__imp_KeSetEvent
0x1400134b4  nop     dword ptr [rax+rax+00h]
0x1400134b9  jmp     short loc_1400134FE
0x1400134bb  test    esi, esi
0x1400134bd  jns     short loc_1400134F6
0x1400134bf  movzx   eax, word ptr [rbx+208h]
0x1400134c6  sub     ax, 2
0x1400134ca  cmp     ax, 1
0x1400134ce  ja      short loc_1400134F6
0x1400134d0  mov     rcx, cs:RxFileSystemDeviceObject; pMRxDeviceObject
0x1400134d7  lea     r8, [rbx+130h]; pWorkQueueItem
0x1400134de  lea     r9, RxLowIoCompletion; Routine
0x1400134e5  mov     [rsp+58h+pContext], rbx; pContext
0x1400134ea  mov     edx, 2; WorkQueueType
0x1400134ef  call    RxPostToWorkerThread
0x1400134f4  jmp     short loc_1400134FE
0x1400134f6  mov     rcx, rbx; RxContext
0x1400134f9  call    RxLowIoCompletion
0x1400134fe  mov     eax, 0C0000016h
0x140013503  mov     rbx, [rsp+58h+arg_18]
0x140013508  add     rsp, 40h
0x14001350c  pop     r15
0x14001350e  pop     r14
0x140013510  pop     rsi
0x140013511  retn
```
