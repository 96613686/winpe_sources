# CscNotifyChangeDirectoryCompletion

- ea: `0x14006eba0`
- end: `0x14006f050`
- name: `CscNotifyChangeDirectoryCompletion`
- size: `1200`
- prototype: `__int64 __fastcall(PMRX_FCB Fcb)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14000edc0`

## callees

- `0x14000a4f0`
- `0x14000eef0`
- `0x140018930`
- `0x140018b50`
- `0x14001ac1c`
- `0x1400205dc`
- `0x14002f140`
- `0x14006eba0`
- `0x14006f058`
- `0x140076afc`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14006efee`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006efee`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006f005`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006f005`
- `ntoskrnl!IoCancelIrp` at `0x14006edb9`
- `ntoskrnl!IoCancelIrp` at `0x14006edb9`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006ec02`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006ed81`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006edd6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006ec02`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006ed81`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006edd6`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14006ec7c`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14006ec7c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006ee66`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006ef6a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006ee66`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006ef6a`

## pseudocode

```c
__int64 __fastcall CscNotifyChangeDirectoryCompletion(PMRX_FCB Fcb)
{
  PMRX_NET_ROOT pNetRoot; // r14
  __int64 v3; // rsi
  __int64 v4; // rcx
  struct _LIST_ENTRY *Flink; // rdx
  char QuadPart; // cl
  char v7; // al
  unsigned int v8; // r15d
  ULONG *p_PipeReadThrottlingParameters; // rsi
  signed __int32 v10; // eax
  char v11; // r13
  PIRP *p_Context2; // r15
  ULONG *p_Flags; // rdx
  unsigned int v14; // eax
  ULONG *p_MaximumDelay; // r13
  __int64 v16; // rcx
  PVOID v17; // rax
  NTSTATUS Status; // ecx
  int v19; // ecx
  __int64 v20; // rcx
  PVOID v21; // rax
  NTSTATUS v22; // ecx
  PMRX_FCB v24; // [rsp+40h] [rbp-48h]
  unsigned int Size; // [rsp+98h] [rbp+10h]
  union _LARGE_INTEGER Timeout; // [rsp+A0h] [rbp+18h] BYREF
  PMRX_NET_ROOT v27; // [rsp+A8h] [rbp+20h]

  Size = (unsigned int)Fcb[3].Header.PagingIoResource;
  pNetRoot = Fcb[1].pNetRoot;
  v27 = pNetRoot;
  if ( KeGetCurrentThread() == *(struct _KTHREAD **)&pNetRoot->DiskParameters.VolumeId.Data1 )
  {
    Timeout.QuadPart = 0;
    if ( KeWaitForSingleObject(&pNetRoot->NumberOfSrvOpens, Executive, 0, 0, &Timeout) == 258 )
    {
      v3 = CscFcbContext(Fcb->Header.FilterContexts.Flink);
      _InterlockedOr((volatile signed __int32 *)&pNetRoot->NamedPipeParameters.PipeReadThrottlingParameters, 0x20u);
      v4 = *(unsigned int *)&Fcb[1].Header.NodeTypeCode;
      if ( (int)v4 < 0
        && (unsigned __int8)CscTransitnOKToGoOffline(v4)
        && v3
        && (*(_DWORD *)(v3 + 4) & 0x1000000) == 0
        && !(unsigned __int8)CscLViewIsRootGhosted(Fcb->Header.FilterContexts.Flink[8].Flink) )
      {
        if ( !(unsigned __int8)ExIsResourceAcquiredSharedLite((PERESOURCE)Fcb->Header.FilterContexts.Flink->Blink)
          && ((QuadPart = Fcb->Header.FileSize.QuadPart, QuadPart == 17)
           || QuadPart == 12 && BYTE1(Fcb->Header.FileSize.LowPart) == 2
           || (((unsigned __int8)(QuadPart - 3) <= 1u
             || (unsigned __int8)(QuadPart - 13) <= 1u
             || QuadPart == 12 && BYTE1(Fcb->Header.FileSize.LowPart) == 2)
            && ((Flink = Fcb[3].Header.FilterContexts.Flink, Flink == (struct _LIST_ENTRY *)((__int64)Fcb->pNetRoot | 3))
             || Flink == (struct _LIST_ENTRY *)Fcb->pNetRoot)
             ? (v7 = 1)
             : (v7 = 0),
               !v7)) )
        {
          CscTransitionFcbOfflineNoLocksHeld(Fcb);
        }
        else
        {
          LOBYTE(Flink) = 1;
          CscTransitionFcbOffline(Fcb->Header.FilterContexts.Flink, Flink, 2, 2);
        }
      }
LABEL_49:
      KeEnterCriticalRegion();
      v8 = CscNotifyDereferenceContextAndComplete_Real(pNetRoot);
      KeLeaveCriticalRegion();
      goto LABEL_50;
    }
  }
  v8 = 267;
  p_PipeReadThrottlingParameters = (ULONG *)&pNetRoot->NamedPipeParameters.PipeReadThrottlingParameters;
  _m_prefetchw(&pNetRoot->DiskParameters.ReadAheadGranularity);
  v10 = _InterlockedAnd(
          (volatile signed __int32 *)&pNetRoot->NamedPipeParameters.PipeReadThrottlingParameters,
          0xFFFFFFFE);
  v11 = v10;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_f1d0093ed16337749994f41f70b429cb_Traceguids, pNetRoot, v10);
  if ( (v11 & 1) != 0 )
  {
    KeWaitForSingleObject(&pNetRoot->NumberOfSrvOpens, Executive, 0, 0, 0);
    p_Context2 = (PIRP *)&pNetRoot->Context2;
    Timeout.QuadPart = (LONGLONG)&pNetRoot->Context2;
    if ( pNetRoot->Context2 )
    {
      _m_prefetchw(p_PipeReadThrottlingParameters);
      if ( (_InterlockedXor((volatile signed __int32 *)p_PipeReadThrottlingParameters, 0) & 2) != 0 )
        IoCancelIrp(*p_Context2);
      KeWaitForSingleObject(&pNetRoot->InnerNamePrefix, Executive, 0, 0, 0);
    }
    p_Flags = &pNetRoot->Flags;
    if ( (v11 & 2) == 0 || (v14 = 4, *p_Flags != -1073741536) )
      v14 = 8;
    _InterlockedOr((volatile signed __int32 *)p_PipeReadThrottlingParameters, v14);
    v24 = Fcb + 1;
    p_MaximumDelay = &pNetRoot->DiskParameters.LockThrottlingParameters.MaximumDelay;
    pNetRoot->DiskParameters.LockThrottlingParameters.MaximumDelay = *(_DWORD *)&Fcb[1].Header.NodeTypeCode;
    _m_prefetchw(p_PipeReadThrottlingParameters);
    if ( (_InterlockedXor((volatile signed __int32 *)p_PipeReadThrottlingParameters, 0) & 8) != 0 )
    {
      if ( *p_Context2 )
      {
        v16 = *(_QWORD *)(Fcb->Header.ValidDataLength.QuadPart + 8);
        if ( (*(_BYTE *)(v16 + 10) & 5) != 0 )
          v17 = *(PVOID *)(v16 + 24);
        else
          v17 = MmMapLockedPagesSpecifyCache((PMDL)v16, 0, MmCached, 0, 0, 0x40000010u);
        memmove(v17, *(const void **)(*(_QWORD *)Timeout.QuadPart + 24LL), Size);
        *(_QWORD *)(Fcb->Header.ValidDataLength.QuadPart + 56) = Size;
        Fcb[1].Header.Resource = (PERESOURCE)Size;
        Status = (*p_Context2)->IoStatus.Status;
        *p_MaximumDelay = Status;
        *(_DWORD *)(Fcb->Header.ValidDataLength.QuadPart + 48) = Status;
        *(_DWORD *)&v24->Header.NodeTypeCode = *p_MaximumDelay;
      }
      else if ( (*p_Flags & 0x80000000) != 0 )
      {
        *(_QWORD *)(Fcb->Header.ValidDataLength.QuadPart + 56) = 0;
        Fcb[1].Header.Resource = 0;
        v19 = *p_Flags;
        *p_MaximumDelay = *p_Flags;
        *(_DWORD *)(Fcb->Header.ValidDataLength.QuadPart + 48) = v19;
        *(_DWORD *)&Fcb[1].Header.NodeTypeCode = *p_MaximumDelay;
      }
    }
    if ( *p_Context2 )
    {
      _m_prefetchw(p_PipeReadThrottlingParameters);
      if ( (_InterlockedXor((volatile signed __int32 *)p_PipeReadThrottlingParameters, 0) & 8) != 0 )
      {
        v20 = *(_QWORD *)(Fcb->Header.ValidDataLength.QuadPart + 8);
        if ( (*(_BYTE *)(v20 + 10) & 5) != 0 )
          v21 = *(PVOID *)(v20 + 24);
        else
          v21 = MmMapLockedPagesSpecifyCache((PMDL)v20, 0, MmCached, 0, 0, 0x40000010u);
        memmove(v21, *(const void **)(*(_QWORD *)Timeout.QuadPart + 24LL), Size);
        *(_QWORD *)(Fcb->Header.ValidDataLength.QuadPart + 56) = Size;
        Fcb[1].Header.Resource = (PERESOURCE)Size;
        v22 = (*p_Context2)->IoStatus.Status;
        *p_MaximumDelay = v22;
        *(_DWORD *)(Fcb->Header.ValidDataLength.QuadPart + 48) = v22;
        *(_DWORD *)&v24->Header.NodeTypeCode = *p_MaximumDelay;
      }
    }
    goto LABEL_49;
  }
LABEL_50:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_f1d0093ed16337749994f41f70b429cb_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x14006eba0  mov     r11, rsp
0x14006eba3  mov     [r11+8], rcx
0x14006eba7  push    rbx
0x14006eba8  push    rsi
0x14006eba9  push    rdi
0x14006ebaa  push    r12
0x14006ebac  push    r13
0x14006ebae  push    r14
0x14006ebb0  push    r15
0x14006ebb2  sub     rsp, 50h
0x14006ebb6  mov     rbx, rcx
0x14006ebb9  mov     eax, [rcx+220h]
0x14006ebbf  mov     dword ptr [rsp+88h+Size], eax
0x14006ebc6  mov     r14, [rcx+108h]
0x14006ebcd  mov     [rsp+88h+arg_18], r14
0x14006ebd5  lea     rcx, [r14+28h]; Object
0x14006ebd9  mov     rax, gs:188h
0x14006ebe2  xor     edi, edi
0x14006ebe4  cmp     rax, [r14+68h]
0x14006ebe8  jnz     loc_14006ED0D
0x14006ebee  mov     [r11+18h], rdi
0x14006ebf2  lea     rax, [r11+18h]
0x14006ebf6  mov     [r11-68h], rax
0x14006ebfa  xor     r9d, r9d; Alertable
0x14006ebfd  xor     r8d, r8d; WaitMode
0x14006ec00  xor     edx, edx; WaitReason
0x14006ec02  call    cs:__imp_KeWaitForSingleObject
0x14006ec09  nop     dword ptr [rax+rax+00h]
0x14006ec0e  cmp     eax, 102h
0x14006ec13  jnz     loc_14006ED0D
0x14006ec19  mov     rcx, [rbx+38h]
0x14006ec1d  call    CscFcbContext
0x14006ec22  mov     rsi, rax
0x14006ec25  lock or dword ptr [r14+58h], 20h
0x14006ec2b  mov     ecx, [rbx+0B0h]
0x14006ec31  test    ecx, ecx
0x14006ec33  jns     loc_14006ED01
0x14006ec39  call    CscTransitnOKToGoOffline
0x14006ec3e  test    al, al
0x14006ec40  jz      loc_14006ED01
0x14006ec46  test    rsi, rsi
0x14006ec49  jz      loc_14006ED01
0x14006ec4f  test    dword ptr [rsi+4], 1000000h
0x14006ec56  jnz     loc_14006ED01
0x14006ec5c  mov     rcx, [rbx+38h]
0x14006ec60  mov     rcx, [rcx+80h]
0x14006ec67  call    CscLViewIsRootGhosted
0x14006ec6c  test    al, al
0x14006ec6e  jnz     loc_14006ED01
0x14006ec74  mov     rcx, [rbx+38h]
0x14006ec78  mov     rcx, [rcx+8]; Resource
0x14006ec7c  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x14006ec83  nop     dword ptr [rax+rax+00h]
0x14006ec88  test    al, al
0x14006ec8a  jnz     short loc_14006ECED
0x14006ec8c  mov     cl, [rbx+20h]
0x14006ec8f  cmp     cl, 11h
0x14006ec92  jz      short loc_14006ECDF
0x14006ec94  cmp     cl, 0Ch
0x14006ec97  jnz     short loc_14006EC9F
0x14006ec99  cmp     byte ptr [rbx+21h], 2
0x14006ec9d  jz      short loc_14006ECDF
0x14006ec9f  lea     eax, [rcx-3]
0x14006eca2  cmp     al, 1
0x14006eca4  jbe     short loc_14006ECB8
0x14006eca6  lea     eax, [rcx-0Dh]
0x14006eca9  cmp     al, 1
0x14006ecab  jbe     short loc_14006ECB8
0x14006ecad  cmp     cl, 0Ch
0x14006ecb0  jnz     short loc_14006ECD4
0x14006ecb2  cmp     byte ptr [rbx+21h], 2
0x14006ecb6  jnz     short loc_14006ECD4
0x14006ecb8  mov     rcx, [rbx+58h]
0x14006ecbc  mov     rdx, [rbx+248h]
0x14006ecc3  mov     rax, rcx
0x14006ecc6  or      rax, 3
0x14006ecca  cmp     rdx, rax
0x14006eccd  jz      short loc_14006ECD9
0x14006eccf  cmp     rdx, rcx
0x14006ecd2  jz      short loc_14006ECD9
0x14006ecd4  mov     al, dil
0x14006ecd7  jmp     short loc_14006ECDB
0x14006ecd9  mov     al, 1
0x14006ecdb  test    al, al
0x14006ecdd  jnz     short loc_14006ECED
0x14006ecdf  mov     rdx, [rbx+38h]
0x14006ece3  mov     rcx, rbx; Fcb
0x14006ece6  call    CscTransitionFcbOfflineNoLocksHeld
0x14006eceb  jmp     short loc_14006ED01
0x14006eced  mov     r9d, 2
0x14006ecf3  mov     r8d, r9d
0x14006ecf6  mov     dl, 1
0x14006ecf8  mov     rcx, [rbx+38h]
0x14006ecfc  call    CscTransitionFcbOffline
0x14006ed01  lea     r12, WPP_GLOBAL_Control
0x14006ed08  jmp     loc_14006EFEE
0x14006ed0d  mov     r15d, 10Bh
0x14006ed13  lea     rsi, [r14+58h]
0x14006ed17  mov     [rsp+88h+var_40], rsi
0x14006ed1c  prefetchw byte ptr [rsi]
0x14006ed1f  mov     eax, [rsi]
0x14006ed21  mov     ecx, eax
0x14006ed23  and     ecx, 0FFFFFFFEh
0x14006ed26  lock cmpxchg [rsi], ecx
0x14006ed2a  jnz     short loc_14006ED21
0x14006ed2c  mov     r13d, eax
0x14006ed2f  lea     r12, WPP_GLOBAL_Control
0x14006ed36  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ed3d  cmp     rcx, r12
0x14006ed40  jz      short loc_14006ED66
0x14006ed42  mov     edx, [rcx+2Ch]
0x14006ed45  test    dl, 40h
0x14006ed48  jz      short loc_14006ED66
0x14006ed4a  mov     edx, 39h ; '9'
0x14006ed4f  mov     dword ptr [rsp+88h+Timeout], eax
0x14006ed53  mov     r9, r14
0x14006ed56  lea     r8, WPP_f1d0093ed16337749994f41f70b429cb_Traceguids
0x14006ed5d  mov     rcx, [rcx+18h]
0x14006ed61  call    WPP_SF_qD
0x14006ed66  test    r13b, 1
0x14006ed6a  jz      loc_14006F011
0x14006ed70  mov     [rsp+88h+Timeout], rdi; Timeout
0x14006ed75  xor     r9d, r9d; Alertable
0x14006ed78  xor     r8d, r8d; WaitMode
0x14006ed7b  xor     edx, edx; WaitReason
0x14006ed7d  lea     rcx, [r14+28h]; Object
0x14006ed81  call    cs:__imp_KeWaitForSingleObject
0x14006ed88  nop     dword ptr [rax+rax+00h]
0x14006ed8d  lea     r15, [r14+18h]
0x14006ed91  mov     [rsp+88h+var_58], r15
0x14006ed96  mov     [rsp+88h+arg_10], r15
0x14006ed9e  cmp     [r15], rdi
0x14006eda1  jz      short loc_14006EDE2
0x14006eda3  prefetchw byte ptr [rsi]
0x14006eda6  mov     eax, [rsi]
0x14006eda8  mov     ecx, eax
0x14006edaa  xor     ecx, edi
0x14006edac  lock cmpxchg [rsi], ecx
0x14006edb0  jnz     short loc_14006EDA8
0x14006edb2  test    al, 2
0x14006edb4  jz      short loc_14006EDC5
0x14006edb6  mov     rcx, [r15]; Irp
0x14006edb9  call    cs:__imp_IoCancelIrp
0x14006edc0  nop     dword ptr [rax+rax+00h]
0x14006edc5  lea     rcx, [r14+40h]; Object
0x14006edc9  mov     [rsp+88h+Timeout], rdi; Timeout
0x14006edce  xor     r9d, r9d; Alertable
0x14006edd1  xor     r8d, r8d; WaitMode
0x14006edd4  xor     edx, edx; WaitReason
0x14006edd6  call    cs:__imp_KeWaitForSingleObject
0x14006eddd  nop     dword ptr [rax+rax+00h]
0x14006ede2  lea     rdx, [r14+20h]
0x14006ede6  test    r13b, 2
0x14006edea  jz      short loc_14006EDF9
0x14006edec  cmp     dword ptr [rdx], 0C0000120h
0x14006edf2  mov     eax, 4
0x14006edf7  jz      short loc_14006EDFE
0x14006edf9  mov     eax, 8
0x14006edfe  lock or [rsi], eax
0x14006ee01  lea     r8, [rbx+0B0h]
0x14006ee08  mov     [rsp+88h+var_48], r8
0x14006ee0d  lea     r13, [r14+60h]
0x14006ee11  mov     [rsp+88h+var_50], r13
0x14006ee16  mov     eax, [r8]
0x14006ee19  mov     [r13+0], eax
0x14006ee1d  prefetchw byte ptr [rsi]
0x14006ee20  mov     eax, [rsi]
0x14006ee22  mov     ecx, eax
0x14006ee24  xor     ecx, edi
0x14006ee26  lock cmpxchg [rsi], ecx
0x14006ee2a  jnz     short loc_14006EE22
0x14006ee2c  test    al, 8
0x14006ee2e  jz      loc_14006EF21
0x14006ee34  cmp     [r15], rdi
0x14006ee37  jz      loc_14006EEFA
0x14006ee3d  mov     rax, [rbx+28h]
0x14006ee41  mov     rcx, [rax+8]; MemoryDescriptorList
0x14006ee45  test    byte ptr [rcx+0Ah], 5
0x14006ee49  jz      short loc_14006EE51
0x14006ee4b  mov     rax, [rcx+18h]
0x14006ee4f  jmp     short loc_14006EE72
0x14006ee51  mov     [rsp+88h+Priority], 40000010h; Priority
0x14006ee59  mov     dword ptr [rsp+88h+Timeout], edi; BugCheckOnFailure
0x14006ee5d  xor     r9d, r9d; RequestedAddress
0x14006ee60  xor     edx, edx; AccessMode
0x14006ee62  lea     r8d, [r9+1]; CacheType
0x14006ee66  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006ee6d  nop     dword ptr [rax+rax+00h]
0x14006ee72  mov     r8d, dword ptr [rsp+88h+Size]; Size
0x14006ee7a  mov     rdx, [rsp+88h+arg_10]
0x14006ee82  mov     rdx, [rdx]
0x14006ee85  mov     rdx, [rdx+18h]; Src
0x14006ee89  mov     rcx, rax; void *
0x14006ee8c  call    memmove
0x14006ee91  mov     eax, dword ptr [rsp+88h+Size]
0x14006ee98  jmp     short loc_14006EECB
0x14006ee9a  xor     eax, eax
0x14006ee9c  mov     dword ptr [rsp+88h+Size], eax
0x14006eea3  xor     edi, edi
0x14006eea5  lea     r12, WPP_GLOBAL_Control
0x14006eeac  mov     rbx, [rsp+88h+arg_0]
0x14006eeb4  mov     r14, [rsp+88h+arg_18]
0x14006eebc  mov     rsi, [rsp+88h+var_40]
0x14006eec1  mov     r15, [rsp+88h+var_58]
0x14006eec6  mov     r13, [rsp+88h+var_50]
0x14006eecb  mov     ecx, eax
0x14006eecd  mov     rax, [rbx+28h]
0x14006eed1  mov     [rax+38h], rcx
0x14006eed5  mov     [rbx+0B8h], rcx
0x14006eedc  mov     rax, [r15]
0x14006eedf  mov     ecx, [rax+30h]
0x14006eee2  mov     [r13+0], ecx
0x14006eee6  mov     rax, [rbx+28h]
0x14006eeea  mov     [rax+30h], ecx
0x14006eeed  mov     eax, [r13+0]
0x14006eef1  mov     rcx, [rsp+88h+var_48]
0x14006eef6  mov     [rcx], eax
0x14006eef8  jmp     short loc_14006EF21
0x14006eefa  cmp     [rdx], edi
0x14006eefc  jge     short loc_14006EF21
0x14006eefe  mov     rax, [rbx+28h]
0x14006ef02  mov     [rax+38h], rdi
0x14006ef06  mov     [rbx+0B8h], rdi
0x14006ef0d  mov     ecx, [rdx]
0x14006ef0f  mov     [r13+0], ecx
0x14006ef13  mov     rax, [rbx+28h]
0x14006ef17  mov     [rax+30h], ecx
0x14006ef1a  mov     eax, [r13+0]
0x14006ef1e  mov     [r8], eax
0x14006ef21  cmp     [r15], rdi
0x14006ef24  jz      loc_14006EFEE
0x14006ef2a  prefetchw byte ptr [rsi]
0x14006ef2d  mov     eax, [rsi]
0x14006ef2f  mov     ecx, eax
0x14006ef31  xor     ecx, edi
0x14006ef33  lock cmpxchg [rsi], ecx
0x14006ef37  jnz     short loc_14006EF2F
0x14006ef39  test    al, 8
0x14006ef3b  jz      loc_14006EFEE
0x14006ef41  mov     rax, [rbx+28h]
0x14006ef45  mov     rcx, [rax+8]; MemoryDescriptorList
0x14006ef49  test    byte ptr [rcx+0Ah], 5
0x14006ef4d  jz      short loc_14006EF55
0x14006ef4f  mov     rax, [rcx+18h]
0x14006ef53  jmp     short loc_14006EF76
0x14006ef55  mov     [rsp+88h+Priority], 40000010h; Priority
0x14006ef5d  mov     dword ptr [rsp+88h+Timeout], edi; BugCheckOnFailure
0x14006ef61  xor     r9d, r9d; RequestedAddress
0x14006ef64  xor     edx, edx; AccessMode
0x14006ef66  lea     r8d, [r9+1]; CacheType
0x14006ef6a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006ef71  nop     dword ptr [rax+rax+00h]
0x14006ef76  mov     r8d, dword ptr [rsp+88h+Size]; Size
0x14006ef7e  mov     rcx, [rsp+88h+arg_10]
0x14006ef86  mov     rdx, [rcx]
0x14006ef89  mov     rdx, [rdx+18h]; Src
0x14006ef8d  mov     rcx, rax; void *
0x14006ef90  call    memmove
0x14006ef95  mov     eax, dword ptr [rsp+88h+Size]
0x14006ef9c  jmp     short loc_14006EFC1
0x14006ef9e  xor     eax, eax
0x14006efa0  lea     r12, WPP_GLOBAL_Control
0x14006efa7  mov     rbx, [rsp+88h+arg_0]
0x14006efaf  mov     r14, [rsp+88h+arg_18]
0x14006efb7  mov     r15, [rsp+88h+var_58]
0x14006efbc  mov     r13, [rsp+88h+var_50]
0x14006efc1  mov     ecx, eax
0x14006efc3  mov     rax, [rbx+28h]
0x14006efc7  mov     [rax+38h], rcx
0x14006efcb  mov     [rbx+0B8h], rcx
0x14006efd2  mov     rax, [r15]
0x14006efd5  mov     ecx, [rax+30h]
0x14006efd8  mov     [r13+0], ecx
0x14006efdc  mov     rax, [rbx+28h]
0x14006efe0  mov     [rax+30h], ecx
0x14006efe3  mov     eax, [r13+0]
0x14006efe7  mov     rcx, [rsp+88h+var_48]
0x14006efec  mov     [rcx], eax
0x14006efee  call    cs:__imp_KeEnterCriticalRegion
0x14006eff5  nop     dword ptr [rax+rax+00h]
0x14006effa  mov     rcx, r14; P
0x14006effd  call    CscNotifyDereferenceContextAndComplete_Real
0x14006f002  mov     r15d, eax
0x14006f005  call    cs:__imp_KeLeaveCriticalRegion
0x14006f00c  nop     dword ptr [rax+rax+00h]
0x14006f011  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f018  cmp     rcx, r12
0x14006f01b  jz      short loc_14006F03C
0x14006f01d  mov     eax, [rcx+2Ch]
0x14006f020  test    al, 20h
0x14006f022  jz      short loc_14006F03C
0x14006f024  mov     edx, 3Bh ; ';'
0x14006f029  mov     r9d, r15d
0x14006f02c  lea     r8, WPP_f1d0093ed16337749994f41f70b429cb_Traceguids
0x14006f033  mov     rcx, [rcx+18h]
0x14006f037  call    WPP_SF_d
0x14006f03c  mov     eax, r15d
0x14006f03f  add     rsp, 50h
0x14006f043  pop     r15
0x14006f045  pop     r14
  ... truncated ...
```
