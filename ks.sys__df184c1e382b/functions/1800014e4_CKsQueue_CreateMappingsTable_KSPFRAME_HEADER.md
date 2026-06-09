# CKsQueue::CreateMappingsTable(_KSPFRAME_HEADER *)

- ea: `0x1800014e4`
- end: `0x18000180d`
- name: `?CreateMappingsTable@CKsQueue@@AEAAPEAUKSPMAPPINGS_TABLE@@PEAU_KSPFRAME_HEADER@@@Z`
- size: `809`
- prototype: `struct KSPMAPPINGS_TABLE *__fastcall(CKsQueue *__hidden this, struct _KSPFRAME_HEADER *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001120`

## callees

- `0x1800014e4`
- `0x180008e78`
- `0x1800096e4`
- `0x18000a8cc`
- `0x18000b7bc`
- `0x18000b9b4`
- `0x180019cb0`
- `0x18001a000`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x18000177d`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x18000177d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x18000178c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x18000178c`
- `ntoskrnl!KeLowerIrql` at `0x1800017ad`
- `ntoskrnl!KeLowerIrql` at `0x1800017ad`
- `ntoskrnl!KfRaiseIrql` at `0x180001737`
- `ntoskrnl!KfRaiseIrql` at `0x180001737`
- `ntoskrnl!KeInitializeSpinLock` at `0x180001729`
- `ntoskrnl!KeInitializeSpinLock` at `0x180001729`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800016a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800017d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800016a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800017d3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800015b2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800015b2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1800016be`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1800016be`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000179e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800017ec`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000179e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800017ec`

## pseudocode

```c
struct KSPMAPPINGS_TABLE *__fastcall CKsQueue::CreateMappingsTable(CKsQueue *this, struct _KSPFRAME_HEADER *a2)
{
  struct _KSPFRAME_HEADER *v2; // r15
  __int64 v4; // r13
  unsigned int m_MaxMappingByteCount; // ecx
  unsigned int v6; // ebp
  SIZE_T v7; // r12
  struct KSPMAPPINGS_TABLE *PoolWithTag; // rax
  struct KSPMAPPINGS_TABLE *v9; // rbx
  DMABuffer *v10; // rax
  int started; // eax
  bool v12; // zf
  PVOID v13; // rax
  PVOID v14; // rsi
  KIRQL v15; // r12
  int v16; // ebp

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      81,
      (__int64)WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids);
  }
  v4 = *(unsigned int *)((char *)&v2->StreamHeader->DataUsed
                       + (-(__int64)(this->m_OutputData != 0) & 0xFFFFFFFFFFFFFFFCuLL));
  m_MaxMappingByteCount = this->m_MaxMappingByteCount;
  if ( m_MaxMappingByteCount >= 0x1000 )
    v6 = (v4 + (unsigned __int64)((LODWORD(v2->Mdl->StartVa) + v2->Mdl->ByteOffset) & 0xFFF) + 4095) >> 12;
  else
    v6 = ((v4 + (unsigned __int64)((LODWORD(v2->Mdl->StartVa) + v2->Mdl->ByteOffset) & 0xFFF) + 4095) >> 12)
       * ((m_MaxMappingByteCount + 4095)
        / m_MaxMappingByteCount);
  v7 = this->m_MappingTableStride * v6 + 152;
  PoolWithTag = (struct KSPMAPPINGS_TABLE *)ExAllocatePoolWithTag((POOL_TYPE)1536, v7, 0x746D534Bu);
  v9 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    memset(PoolWithTag, 0, (unsigned int)v7);
  if ( this->m_UseKsCommonBuffer )
  {
    if ( v9 )
    {
      v9->ByteCount = v4;
      v9->Stride = this->m_MappingTableStride;
      v9->MappingsAllocated = v6;
      v9->Mdl = v2->Mdl;
      v9->Mappings = (_KSMAPPING *)&v9[1];
      v10 = (DMABuffer *)this->m_Device->GetMapBuffer(this->m_Device);
      if ( !v10 )
        goto LABEL_16;
      started = DMABuffer::StartMapping(v10, &v9->Transfer, v2->Mdl, this->m_OutputData != 0);
      v12 = started == 0;
      if ( started >= 0 )
        v12 = (unsigned int)GetMappingTableFromTransferBuffer(
                              &v9->Transfer,
                              v4,
                              v2->Mdl->ByteOffset,
                              this->m_MaxMappingByteCount,
                              v9->MappingsAllocated,
                              this->m_MappingTableStride,
                              v9->Mappings,
                              &v9->MappingsFilled) == 0;
      if ( !v12 )
      {
LABEL_16:
        PurgeTransfer(&v9->Transfer);
        ExFreePoolWithTag(v9, 0);
        return 0;
      }
    }
    return v9;
  }
  v13 = ExAllocateFromNPagedLookasideList(&this->m_ChannelContextLookaside);
  v14 = v13;
  if ( v9 )
  {
    if ( !v13 )
    {
      ExFreePoolWithTag(v9, 0);
      return 0;
    }
    memset(v9, 0, v7);
    v9->ByteCount = v4;
    v9->Stride = this->m_MappingTableStride;
    v9->MappingsAllocated = v6;
    v9->Mdl = v2->Mdl;
    v9->Mappings = (_KSMAPPING *)&v9[1];
    *(_QWORD *)v14 = v9;
    *((_QWORD *)v14 + 2) = this;
    *((_DWORD *)v14 + 2) = 1;
    KeInitializeSpinLock((PKSPIN_LOCK)v14 + 3);
    v15 = KfRaiseIrql(2u);
    v16 = this->m_Device->ArbitrateAdapterChannel(
            this->m_Device,
            v9->MappingsAllocated,
            (_IO_ALLOCATION_ACTION (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *, void *))CKsQueue::CallbackFromIoAllocateAdapterChannel,
            v14);
    if ( v16 >= 0 )
    {
      if ( _InterlockedCompareExchange((volatile signed __int32 *)v14 + 2, 0, 1) )
      {
        v16 = -2147483631;
        goto LABEL_23;
      }
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)v14 + 3);
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)v14 + 3);
    }
    ExFreeToNPagedLookasideList(&this->m_ChannelContextLookaside, v14);
LABEL_23:
    KeLowerIrql(v15);
    if ( v16 >= 0 )
      return v9;
    CKsQueue::DeleteMappingsTable(this, v9);
    return 0;
  }
  if ( v13 )
    ExFreeToNPagedLookasideList(&this->m_ChannelContextLookaside, v13);
  return v9;
}

```

## disassembly

```asm
0x1800014e4  push    rbx
0x1800014e6  push    rbp
0x1800014e7  push    rsi
0x1800014e8  push    rdi
0x1800014e9  push    r12
0x1800014eb  push    r13
0x1800014ed  push    r14
0x1800014ef  push    r15
0x1800014f1  sub     rsp, 48h
0x1800014f5  mov     r15, rdx
0x1800014f8  mov     rdi, rcx
0x1800014fb  lea     rax, WPP_RECORDER_INITIALIZED
0x180001502  xor     r14d, r14d
0x180001505  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000150c  jz      short loc_18000153B
0x18000150e  mov     rcx, cs:WPP_GLOBAL_Control
0x180001515  cmp     [rcx+48h], r14w
0x18000151a  jz      short loc_18000153B
0x18000151c  mov     rcx, [rcx+40h]
0x180001520  lea     rax, WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids
0x180001527  lea     r9d, [r14+51h]
0x18000152b  mov     qword ptr [rsp+88h+var_68], rax
0x180001530  lea     r8d, [r14+1]
0x180001534  mov     dl, 5
0x180001536  call    WPP_RECORDER_SF_
0x18000153b  mov     al, [rdi+73h]
0x18000153e  neg     al
0x180001540  mov     rax, [r15+40h]
0x180001544  sbb     rcx, rcx
0x180001547  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18000154b  mov     r13d, [rcx+rax+24h]
0x180001550  mov     rax, [r15+28h]
0x180001554  mov     ecx, [rdi+0A0h]
0x18000155a  mov     r8d, [rax+2Ch]
0x18000155e  add     r8d, [rax+20h]
0x180001562  and     r8d, 0FFFh
0x180001569  add     r8, 0FFFh
0x180001570  add     r8, r13
0x180001573  shr     r8, 0Ch
0x180001577  cmp     ecx, 1000h
0x18000157d  jnb     short loc_180001591
0x18000157f  xor     edx, edx
0x180001581  lea     eax, [rcx+0FFFh]
0x180001587  div     ecx
0x180001589  mov     ebp, eax
0x18000158b  imul    ebp, r8d
0x18000158f  jmp     short loc_180001594
0x180001591  mov     ebp, r8d
0x180001594  mov     eax, ebp
0x180001596  mov     r8d, 746D534Bh; Tag
0x18000159c  imul    eax, [rdi+0A4h]
0x1800015a3  mov     ecx, 600h; PoolType
0x1800015a8  add     eax, 98h
0x1800015ad  mov     edx, eax; NumberOfBytes
0x1800015af  mov     r12d, eax
0x1800015b2  call    cs:__imp_ExAllocatePoolWithTag
0x1800015b9  nop     dword ptr [rax+rax+00h]
0x1800015be  cmp     cs:ExPoolZeroingNativelySupported, r14b
0x1800015c5  mov     rbx, rax
0x1800015c8  jnz     short loc_1800015DC
0x1800015ca  test    rax, rax
0x1800015cd  jz      short loc_1800015DC
0x1800015cf  mov     r8d, r12d; Size
0x1800015d2  xor     edx, edx; Val
0x1800015d4  mov     rcx, rax; void *
0x1800015d7  call    memset
0x1800015dc  cmp     [rdi+76h], r14b
0x1800015e0  jz      loc_1800016B4
0x1800015e6  test    rbx, rbx
0x1800015e9  jz      loc_1800017F8
0x1800015ef  mov     [rbx], r13d
0x1800015f2  lea     rsi, [rbx+18h]
0x1800015f6  mov     eax, [rdi+0A4h]
0x1800015fc  mov     [rbx+4], eax
0x1800015ff  mov     [rbx+8], ebp
0x180001602  mov     rax, [r15+28h]
0x180001606  mov     [rbx+10h], rax
0x18000160a  lea     rax, [rbx+98h]
0x180001611  mov     [rbx+90h], rax
0x180001618  mov     rcx, [rdi+88h]
0x18000161f  mov     rax, [rcx]
0x180001622  mov     rax, [rax+60h]
0x180001626  call    _guard_dispatch_icall
0x18000162b  test    rax, rax
0x18000162e  jz      short loc_180001693
0x180001630  cmp     [rdi+73h], r14b
0x180001634  mov     rdx, rsi; struct _DMATransfer *
0x180001637  mov     r8, [r15+28h]; struct _MDL *
0x18000163b  mov     rcx, rax; this
0x18000163e  setnz   r9b; unsigned __int8
0x180001642  call    ?StartMapping@DMABuffer@@QEAAJAEAU_DMATransfer@@PEAU_MDL@@E@Z; DMABuffer::StartMapping(_DMATransfer &,_MDL *,uchar)
0x180001647  test    eax, eax
0x180001649  js      short loc_18000168D
0x18000164b  mov     r8, [r15+28h]
0x18000164f  lea     rax, [rbx+0Ch]
0x180001653  mov     r9d, [rdi+0A0h]; unsigned int
0x18000165a  mov     edx, r13d; unsigned int
0x18000165d  mov     [rsp+88h+var_50], rax; unsigned int *
0x180001662  mov     rcx, rsi; struct _DMATransfer *
0x180001665  mov     rax, [rbx+90h]
0x18000166c  mov     r8d, [r8+2Ch]; unsigned int
0x180001670  mov     [rsp+88h+var_58], rax; struct _KSMAPPING *
0x180001675  mov     eax, [rdi+0A4h]
0x18000167b  mov     [rsp+88h+var_60], eax; unsigned int
0x18000167f  mov     eax, [rbx+8]
0x180001682  mov     [rsp+88h+var_68], eax; unsigned int
0x180001686  call    ?GetMappingTableFromTransferBuffer@@YAJPEAU_DMATransfer@@KKKKKPEAU_KSMAPPING@@PEAK@Z; GetMappingTableFromTransferBuffer(_DMATransfer *,ulong,ulong,ulong,ulong,ulong,_KSMAPPING *,ulong *)
0x18000168b  test    eax, eax
0x18000168d  jz      loc_1800017F8
0x180001693  mov     rcx, rsi; void *
0x180001696  call    PurgeTransfer
0x18000169b  xor     edx, edx; Tag
0x18000169d  mov     rcx, rbx; P
0x1800016a0  call    cs:__imp_ExFreePoolWithTag
0x1800016a7  nop     dword ptr [rax+rax+00h]
0x1800016ac  mov     rbx, r14
0x1800016af  jmp     loc_1800017F8
0x1800016b4  lea     r14, [rdi+2C0h]
0x1800016bb  mov     rcx, r14; Lookaside
0x1800016be  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1800016c5  nop     dword ptr [rax+rax+00h]
0x1800016ca  mov     rsi, rax
0x1800016cd  test    rbx, rbx
0x1800016d0  jz      loc_1800017E1
0x1800016d6  xor     edx, edx; Val
0x1800016d8  mov     rcx, rbx; void *
0x1800016db  test    rax, rax
0x1800016de  jz      loc_1800017D3
0x1800016e4  mov     r8, r12; Size
0x1800016e7  call    memset
0x1800016ec  mov     [rbx], r13d
0x1800016ef  mov     r13d, 1
0x1800016f5  mov     eax, [rdi+0A4h]
0x1800016fb  mov     [rbx+4], eax
0x1800016fe  mov     [rbx+8], ebp
0x180001701  mov     rax, [r15+28h]
0x180001705  lea     r15, [rsi+18h]
0x180001709  mov     [rbx+10h], rax
0x18000170d  mov     rcx, r15; SpinLock
0x180001710  lea     rax, [rbx+98h]
0x180001717  mov     [rbx+90h], rax
0x18000171e  mov     [rsi], rbx
0x180001721  mov     [rsi+10h], rdi
0x180001725  mov     [rsi+8], r13d
0x180001729  call    cs:__imp_KeInitializeSpinLock
0x180001730  nop     dword ptr [rax+rax+00h]
0x180001735  mov     cl, 2; NewIrql
0x180001737  call    cs:__imp_KfRaiseIrql
0x18000173e  nop     dword ptr [rax+rax+00h]
0x180001743  mov     rcx, [rdi+88h]
0x18000174a  lea     r8, ?CallbackFromIoAllocateAdapterChannel@CKsQueue@@CA?AW4_IO_ALLOCATION_ACTION@@PEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX2@Z; CKsQueue::CallbackFromIoAllocateAdapterChannel(_DEVICE_OBJECT *,_IRP *,void *,void *)
0x180001751  mov     r12b, al
0x180001754  mov     r9, rsi
0x180001757  mov     rdx, [rcx]
0x18000175a  mov     rax, [rdx+68h]
0x18000175e  mov     edx, [rbx+8]
0x180001761  call    _guard_dispatch_icall
0x180001766  mov     ebp, eax
0x180001768  test    eax, eax
0x18000176a  js      short loc_180001798
0x18000176c  xor     edx, edx
0x18000176e  mov     eax, r13d
0x180001771  lock cmpxchg [rsi+8], edx
0x180001776  test    eax, eax
0x180001778  jnz     short loc_1800017CC
0x18000177a  mov     rcx, r15; SpinLock
0x18000177d  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x180001784  nop     dword ptr [rax+rax+00h]
0x180001789  mov     rcx, r15; SpinLock
0x18000178c  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x180001793  nop     dword ptr [rax+rax+00h]
0x180001798  mov     rdx, rsi; Entry
0x18000179b  mov     rcx, r14; Lookaside
0x18000179e  call    cs:__imp_ExFreeToNPagedLookasideList
0x1800017a5  nop     dword ptr [rax+rax+00h]
0x1800017aa  mov     cl, r12b; NewIrql
0x1800017ad  call    cs:__imp_KeLowerIrql
0x1800017b4  nop     dword ptr [rax+rax+00h]
0x1800017b9  test    ebp, ebp
0x1800017bb  jns     short loc_1800017F8
0x1800017bd  mov     rdx, rbx; struct KSPMAPPINGS_TABLE *
0x1800017c0  mov     rcx, rdi; this
0x1800017c3  call    ?DeleteMappingsTable@CKsQueue@@AEAAXPEAUKSPMAPPINGS_TABLE@@@Z; CKsQueue::DeleteMappingsTable(KSPMAPPINGS_TABLE *)
0x1800017c8  xor     ebx, ebx
0x1800017ca  jmp     short loc_1800017F8
0x1800017cc  mov     ebp, 80000011h
0x1800017d1  jmp     short loc_1800017AA
0x1800017d3  call    cs:__imp_ExFreePoolWithTag
0x1800017da  nop     dword ptr [rax+rax+00h]
0x1800017df  jmp     short loc_1800017C8
0x1800017e1  test    rsi, rsi
0x1800017e4  jz      short loc_1800017F8
0x1800017e6  mov     rdx, rsi; Entry
0x1800017e9  mov     rcx, r14; Lookaside
0x1800017ec  call    cs:__imp_ExFreeToNPagedLookasideList
0x1800017f3  nop     dword ptr [rax+rax+00h]
0x1800017f8  mov     rax, rbx
0x1800017fb  add     rsp, 48h
0x1800017ff  pop     r15
0x180001801  pop     r14
0x180001803  pop     r13
0x180001805  pop     r12
0x180001807  pop     rdi
0x180001808  pop     rsi
0x180001809  pop     rbp
0x18000180a  pop     rbx
0x18000180b  retn
```
