# CKsQueue::TransferKsIrp(_IRP *,IKsTransport * *)

- ea: `0x18000e800`
- end: `0x18000eee6`
- name: `?TransferKsIrp@CKsQueue@@UEAAJPEAU_IRP@@PEAPEAUIKsTransport@@@Z`
- size: `1766`
- prototype: `__int64 __fastcall(CKsQueue *__hidden this, struct _IRP *, struct IKsTransport **)`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001f00`
- `0x180002960`
- `0x1800031c8`
- `0x18000374c`
- `0x180006b80`
- `0x18000adb0`
- `0x18000b7bc`
- `0x18000c8d0`
- `0x18000da50`
- `0x18000e800`
- `0x180010154`
- `0x180010804`
- `0x180016434`
- `0x180019c00`
- `0x180019cb0`
- `0x180019d00`
- `0x18005119c`
- `0x180065d20`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000eb14`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000ed9b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000eb14`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000ed9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000ea41`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000eb68`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000ea41`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000eb68`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000ec85`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000ec85`
- `ntoskrnl!KeSetEvent` at `0x18000ea86`
- `ntoskrnl!KeSetEvent` at `0x18000ee95`
- `ntoskrnl!KeSetEvent` at `0x18000eec6`
- `ntoskrnl!KeSetEvent` at `0x18000ea86`
- `ntoskrnl!KeSetEvent` at `0x18000ee95`
- `ntoskrnl!KeSetEvent` at `0x18000eec6`

## pseudocode

```c
__int64 __fastcall CKsQueue::TransferKsIrp(CKsQueue *this, struct _IRP *a2, struct IKsTransport **a3)
{
  struct IKsTransport **v3; // r13
  struct _IRP *v4; // r14
  PDEVICE_OBJECT v6; // rcx
  int *p_m_TransportIrpsPlusOne; // r15
  int v8; // eax
  int v9; // edx
  __int64 p_NextFrameHeaderInIrp; // r8
  int v11; // r9d
  bool v12; // zf
  int v13; // esi
  ULONG m_ProbeFlags; // edx
  IKsMdlCache *m_MdlCacheComponent; // rcx
  int v16; // eax
  CKsQueue *v17; // rcx
  __int64 p_Parameters; // rax
  int v20; // edx
  struct _IRP *MasterIrp; // r13
  PMDL MdlAddress; // rcx
  PVOID MappedSystemVa; // rax
  struct _KSPFRAME_HEADER *AvailableFrameHeader; // rax
  struct _KSPFRAME_HEADER *v25; // rdx
  _MDL *v26; // rcx
  struct KSPIRP_FRAMING_ *v27; // r8
  unsigned int Status; // eax
  PVOID PoolWithTag; // rax
  size_t Flink_low; // r8
  void *OriginalData; // rdx
  void *BufferedData; // rcx
  int v33; // eax
  struct _MDL *Next; // rcx
  PVOID v35; // rax
  __int64 v36; // rax
  struct _KSPFRAME_HEADER *i; // rsi
  struct _LIST_ENTRY *v38; // rcx
  struct _LIST_ENTRY **v39; // r15
  int BugCheckOnFailure; // [rsp+20h] [rbp-A8h]
  PVOID P; // [rsp+50h] [rbp-78h] BYREF
  struct _MDL *v42; // [rsp+58h] [rbp-70h]
  struct _KSPFRAME_HEADER *v43; // [rsp+60h] [rbp-68h]
  PVOID v44; // [rsp+68h] [rbp-60h]
  struct _KSPFRAME_HEADER **v45; // [rsp+70h] [rbp-58h]
  struct _KSPFRAME_HEADER **v46; // [rsp+78h] [rbp-50h]
  struct KSPIRP_FRAMING_ *v47; // [rsp+80h] [rbp-48h]
  int *v48; // [rsp+88h] [rbp-40h]
  int v50; // [rsp+E8h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v6 = (PDEVICE_OBJECT)&WPP_RECORDER_INITIALIZED;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v6 = WPP_GLOBAL_Control;
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        1,
        69,
        (__int64)WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids);
    }
  }
  if ( ((__int64)WPP_MAIN_CB.Dpc.SystemArgument1 & 2) != 0 )
    McTemplateK0p_EtwWriteTransfer((__int64)v6, (__int64)KS_StreamingRequest_Start, (__int64)a3, 0);
  p_m_TransportIrpsPlusOne = &this->m_TransportIrpsPlusOne;
  v48 = &this->m_TransportIrpsPlusOne;
  if ( _InterlockedIncrement(&this->m_TransportIrpsPlusOne) > 1
    && !this->m_Flushing
    && this->m_State
    && !v4->Cancel
    && v4->IoStatus.Status >= 0 )
  {
    P = 0;
    v8 = this->m_Device->CheckIoCapability(this->m_Device);
    if ( v8 < 0 )
    {
      v4->IoStatus.Status = v8;
      v4->Tail.Overlay.CurrentStackLocation->Control |= 1u;
      KspDiscardKsIrp((__int64)this->m_TransportSink, (__int64)v4);
      *v3 = 0;
      v12 = _InterlockedExchangeAdd(p_m_TransportIrpsPlusOne, 0xFFFFFFFF) == 1;
LABEL_35:
      if ( v12 )
        KeSetEvent(&this->m_FlushEvent, 0, 0);
      return 259;
    }
    if ( this->m_EndOfStream && this->m_InputData )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v9) = 5;
        WPP_RECORDER_SF_qq(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          p_NextFrameHeaderInIrp,
          74,
          (char)WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids,
          (char)this);
      }
      this->m_EndOfStream = 0;
    }
    v13 = 259;
    m_ProbeFlags = this->m_ProbeFlags;
    if ( m_ProbeFlags )
    {
      m_MdlCacheComponent = this->m_MdlCacheComponent;
      v16 = m_MdlCacheComponent
          ? m_MdlCacheComponent->MdlCacheProbeStreamIrp(
              m_MdlCacheComponent,
              v4,
              m_ProbeFlags,
              (_KSPMDLCACHED_STREAM_POINTER **)&P)
          : KsProbeStreamIrp(v4, m_ProbeFlags, 0);
      v13 = v16;
      if ( v16 < 0 )
      {
        v17 = (CKsQueue *)&WPP_RECORDER_INITIALIZED;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_27;
        WPP_RECORDER_SF_qqDD(
          WPP_GLOBAL_Control->DeviceExtension,
          m_ProbeFlags,
          p_NextFrameHeaderInIrp,
          v11,
          BugCheckOnFailure,
          (char)this,
          (char)v4,
          v16,
          this->m_ProbeFlags);
      }
    }
    v17 = (CKsQueue *)&WPP_RECORDER_INITIALIZED;
LABEL_27:
    if ( v13 >= 0 )
    {
      if ( this->m_EndOfStream )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v17 = (CKsQueue *)WPP_GLOBAL_Control;
          if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            LOBYTE(m_ProbeFlags) = 5;
            WPP_RECORDER_SF_qq(
              WPP_GLOBAL_Control->DeviceExtension,
              m_ProbeFlags,
              p_NextFrameHeaderInIrp,
              76,
              (char)WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids,
              (char)this);
          }
        }
        CKsQueue::ZeroIrp(v17, v4);
        if ( P )
        {
          ExFreePoolWithTag(P, 0x636D534Bu);
          P = 0;
        }
        v4->Tail.Overlay.CurrentStackLocation->Control |= 1u;
        KspDiscardKsIrp((__int64)this->m_TransportSink, (__int64)v4);
        *v3 = 0;
        v12 = _InterlockedExchangeAdd(p_m_TransportIrpsPlusOne, 0xFFFFFFFF) == 1;
        goto LABEL_35;
      }
      p_Parameters = (__int64)&v4->Tail.Overlay.CurrentStackLocation->Parameters;
      v47 = (struct KSPIRP_FRAMING_ *)p_Parameters;
      *(_QWORD *)(p_Parameters + 4) = 1;
      v45 = (struct _KSPFRAME_HEADER **)(p_Parameters + 16);
      *(_QWORD *)(p_Parameters + 16) = 0;
      v46 = (struct _KSPFRAME_HEADER **)(p_Parameters + 16);
      v20 = *(_DWORD *)p_Parameters;
      v50 = *(_DWORD *)p_Parameters;
      MasterIrp = v4->AssociatedIrp.MasterIrp;
      MdlAddress = v4->MdlAddress;
LABEL_39:
      v42 = MdlAddress;
      while ( 1 )
      {
        if ( !v20 )
          goto LABEL_83;
        if ( MdlAddress )
        {
          if ( (MdlAddress->MdlFlags & 5) != 0 )
          {
            MappedSystemVa = MdlAddress->MappedSystemVa;
          }
          else
          {
            MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000020u);
            MdlAddress = v42;
          }
        }
        else
        {
          MappedSystemVa = MasterIrp->ThreadListEntry.Blink;
        }
        v44 = MappedSystemVa;
        if ( MdlAddress )
        {
          if ( !MappedSystemVa )
            break;
        }
        if ( (MasterIrp->IoStatus.Status & 0x18000) != 0 && !this->m_MdlCacheComponent
          || (MasterIrp->IoStatus.Status & 0x18000) == 0x10000 )
        {
          if ( P )
          {
            ExFreePoolWithTag(P, 0x636D534Bu);
            P = 0;
          }
LABEL_53:
          v13 = -1073741811;
          goto LABEL_83;
        }
        AvailableFrameHeader = CKsQueue::GetAvailableFrameHeader(this);
        v25 = AvailableFrameHeader;
        v43 = AvailableFrameHeader;
        if ( !AvailableFrameHeader )
          break;
        v26 = v42;
        if ( v42 && !LODWORD(MasterIrp->ThreadListEntry.Flink) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            LOBYTE(v25) = 5;
            WPP_RECORDER_SF_qq(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)v25,
              p_NextFrameHeaderInIrp,
              77,
              (char)WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids,
              (char)this);
          }
          goto LABEL_53;
        }
        AvailableFrameHeader->NextFrameHeaderInIrp = 0;
        AvailableFrameHeader->Queue = this;
        AvailableFrameHeader->OriginalIrp = v4;
        AvailableFrameHeader->Irp = v4;
        v27 = v47;
        AvailableFrameHeader->IrpFraming = v47;
        AvailableFrameHeader->Mdl = v26;
        AvailableFrameHeader->StreamHeader = (KSSTREAM_HEADER *)MasterIrp;
        AvailableFrameHeader->FrameBuffer = v44;
        AvailableFrameHeader->FrameBufferSize = (unsigned int)MasterIrp->ThreadListEntry.Flink;
        AvailableFrameHeader->BufferedData = 0;
        AvailableFrameHeader->OriginalOptionsFlags = MasterIrp->IoStatus.Status;
        AvailableFrameHeader->MdlCaching = (_KSPMDLCACHED_STREAM_POINTER *)P;
        P = 0;
        AvailableFrameHeader->Metadata = 0;
        AvailableFrameHeader->OriginalData = MasterIrp->ThreadListEntry.Blink;
        MasterIrp->ThreadListEntry.Blink = (struct _LIST_ENTRY *)AvailableFrameHeader->FrameBuffer;
        *v46 = AvailableFrameHeader;
        ++v27->QueuedFrameHeaderCount;
        Status = MasterIrp->IoStatus.Status;
        if ( (Status & 0x400) != 0 )
        {
          PoolWithTag = ExAllocatePoolWithTag(NonPagedPoolNx, LODWORD(MasterIrp->ThreadListEntry.Flink), 0x6462534Bu);
          v43->BufferedData = PoolWithTag;
          if ( !PoolWithTag )
            break;
          if ( (unsigned int)Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline() )
          {
            Flink_low = LODWORD(MasterIrp->ThreadListEntry.Flink);
            OriginalData = v43->OriginalData;
            BufferedData = v43->BufferedData;
            if ( v4->RequestorMode )
              RtlCopyFromUser(BufferedData, OriginalData, Flink_low);
            else
              RtlCopyVolatileMemory(BufferedData, OriginalData, Flink_low);
          }
          else
          {
            memmove(v43->BufferedData, v43->OriginalData, LODWORD(MasterIrp->ThreadListEntry.Flink));
          }
          v25 = v43;
          MasterIrp->ThreadListEntry.Blink = (struct _LIST_ENTRY *)v43->BufferedData;
          Status = MasterIrp->IoStatus.Status;
          if ( (Status & 0x800) != 0 )
          {
            v33 = MapVramPhysicalAddress(v4, MasterIrp);
            v13 = v33;
            if ( v33 < 0 )
            {
              v4->IoStatus.Status = v33;
              goto LABEL_83;
            }
            Status = MasterIrp->IoStatus.Status;
            v25 = v43;
          }
          v26 = v42;
        }
        p_NextFrameHeaderInIrp = (__int64)&v25->NextFrameHeaderInIrp;
        v46 = &v25->NextFrameHeaderInIrp;
        if ( (Status & 0x1000) != 0 && v26 )
        {
          v25->Metadata = (KSSTREAM_METADATA_INFO *)(&MasterIrp->Tail.CompletionKey + 1);
          Next = v26->Next;
          v42 = Next;
          if ( Next )
          {
            if ( (Next->MdlFlags & 5) != 0 )
              v35 = Next->MappedSystemVa;
            else
              v35 = MmMapLockedPagesSpecifyCache(Next, 0, MmCached, 0, 0, 0x40000020u);
          }
          else
          {
            v35 = 0;
          }
          MasterIrp->Tail.Overlay.DriverContext[3] = v35;
        }
        v36 = *(unsigned int *)&MasterIrp->Type;
        v20 = v50 - v36;
        v50 -= v36;
        MasterIrp = (struct _IRP *)((char *)MasterIrp + v36);
        MdlAddress = v42;
        if ( v42 )
        {
          MdlAddress = v42->Next;
          goto LABEL_39;
        }
      }
      v13 = -1073741670;
LABEL_83:
      if ( v13 >= 0 )
      {
        for ( i = *v45; i; i = i->NextFrameHeaderInIrp )
          CKsQueue::AddFrame(this, i);
        CKsQueue::ReleaseIrp(this, v4, v47, a3);
        goto LABEL_94;
      }
      v38 = (struct _LIST_ENTRY *)*v45;
      if ( *v45 )
      {
        v39 = (struct _LIST_ENTRY **)v45;
        do
        {
          *v39 = v38[1].Flink;
          CKsQueue::PutAvailableFrameHeader(this, v38, p_NextFrameHeaderInIrp, v11);
          v38 = *v39;
        }
        while ( *v39 );
        p_m_TransportIrpsPlusOne = v48;
      }
      v3 = a3;
    }
    *v3 = 0;
    v4->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    KspDiscardKsIrp((__int64)this->m_TransportSink, (__int64)v4);
LABEL_94:
    if ( _InterlockedExchangeAdd(p_m_TransportIrpsPlusOne, 0xFFFFFFFF) == 1 )
      KeSetEvent(&this->m_FlushEvent, 0, 0);
    return 259;
  }
  *v3 = this->m_TransportSink;
  if ( _InterlockedExchangeAdd(p_m_TransportIrpsPlusOne, 0xFFFFFFFF) == 1 )
    KeSetEvent(&this->m_FlushEvent, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x18000e800  mov     [rsp+arg_10], r8
0x18000e805  mov     [rsp+arg_8], rdx
0x18000e80a  mov     [rsp+arg_0], rcx
0x18000e80f  push    rbx
0x18000e810  push    rsi
0x18000e811  push    rdi
0x18000e812  push    r13
0x18000e814  push    r14
0x18000e816  push    r15
0x18000e818  sub     rsp, 98h
0x18000e81f  mov     r13, r8
0x18000e822  mov     r14, rdx
0x18000e825  mov     rdi, rcx
0x18000e828  lea     rcx, WPP_RECORDER_INITIALIZED
0x18000e82f  xor     ebx, ebx
0x18000e831  lea     rsi, WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids
0x18000e838  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18000e83f  jz      short loc_18000E866
0x18000e841  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e848  cmp     [rcx+48h], bx
0x18000e84c  jz      short loc_18000E866
0x18000e84e  lea     r9d, [rbx+45h]
0x18000e852  mov     qword ptr [rsp+0C8h+BugCheckOnFailure], rsi
0x18000e857  lea     r8d, [rbx+1]
0x18000e85b  mov     dl, 5
0x18000e85d  mov     rcx, [rcx+40h]
0x18000e861  call    WPP_RECORDER_SF_
0x18000e866  mov     eax, dword ptr cs:WPP_MAIN_CB.Dpc.SystemArgument1
0x18000e86c  test    al, 2
0x18000e86e  jz      short loc_18000E87F
0x18000e870  xor     r9d, r9d
0x18000e873  lea     rdx, KS_StreamingRequest_Start
0x18000e87a  call    McTemplateK0p_EtwWriteTransfer
0x18000e87f  lea     r15, [rdi+268h]
0x18000e886  mov     [rsp+0C8h+var_40], r15
0x18000e88e  mov     eax, 1
0x18000e893  lock xadd [r15], eax
0x18000e898  inc     eax
0x18000e89a  cmp     eax, 1
0x18000e89d  jle     loc_18000EEA5
0x18000e8a3  cmp     [rdi+60h], bl
0x18000e8a6  jnz     loc_18000EEA5
0x18000e8ac  cmp     [rdi+64h], ebx
0x18000e8af  jz      loc_18000EEA5
0x18000e8b5  cmp     [r14+44h], bl
0x18000e8b9  jnz     loc_18000EEA5
0x18000e8bf  cmp     [r14+30h], ebx
0x18000e8c3  jl      loc_18000EEA5
0x18000e8c9  mov     [rsp+0C8h+P], rbx
0x18000e8ce  mov     rcx, [rdi+88h]
0x18000e8d5  mov     rax, [rcx]
0x18000e8d8  mov     rax, [rax+70h]
0x18000e8dc  call    _guard_dispatch_icall
0x18000e8e1  test    eax, eax
0x18000e8e3  jns     short loc_18000E914
0x18000e8e5  mov     [r14+30h], eax
0x18000e8e9  mov     rax, [r14+0B8h]
0x18000e8f0  or      byte ptr [rax+3], 1
0x18000e8f4  mov     rdx, r14
0x18000e8f7  mov     rcx, [rdi+50h]
0x18000e8fb  call    KspDiscardKsIrp
0x18000e900  mov     [r13+0], rbx
0x18000e904  or      eax, 0FFFFFFFFh
0x18000e907  lock xadd [r15], eax
0x18000e90c  cmp     eax, 1
0x18000e90f  jmp     loc_18000EA78
0x18000e914  cmp     [rdi+61h], bl
0x18000e917  jz      short loc_18000E95E
0x18000e919  cmp     [rdi+72h], bl
0x18000e91c  jz      short loc_18000E95E
0x18000e91e  lea     rcx, WPP_RECORDER_INITIALIZED
0x18000e925  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18000e92c  jz      short loc_18000E95B
0x18000e92e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e935  cmp     [rcx+48h], bx
0x18000e939  jz      short loc_18000E95B
0x18000e93b  mov     r9d, 4Ah ; 'J'
0x18000e941  mov     [rsp+0C8h+var_98], r14
0x18000e946  mov     qword ptr [rsp+0C8h+Priority], rdi
0x18000e94b  mov     qword ptr [rsp+0C8h+BugCheckOnFailure], rsi
0x18000e950  mov     dl, 5
0x18000e952  mov     rcx, [rcx+40h]
0x18000e956  call    WPP_RECORDER_SF_qq
0x18000e95b  mov     [rdi+61h], bl
0x18000e95e  mov     esi, 103h
0x18000e963  mov     edx, [rdi+6Ch]; ProbeFlags
0x18000e966  test    edx, edx
0x18000e968  jz      short loc_18000E9D5
0x18000e96a  mov     rcx, [rdi+248h]
0x18000e971  test    rcx, rcx
0x18000e974  jz      short loc_18000E98F
0x18000e976  mov     rax, [rcx]
0x18000e979  mov     rax, [rax+30h]
0x18000e97d  lea     r9, [rsp+0C8h+P]
0x18000e982  mov     r8d, edx
0x18000e985  mov     rdx, r14
0x18000e988  call    _guard_dispatch_icall
0x18000e98d  jmp     short loc_18000E99A
0x18000e98f  xor     r8d, r8d; HeaderSize
0x18000e992  mov     rcx, r14; Irp
0x18000e995  call    KsProbeStreamIrp
0x18000e99a  mov     esi, eax
0x18000e99c  test    eax, eax
0x18000e99e  jns     short loc_18000E9D5
0x18000e9a0  lea     rcx, WPP_RECORDER_INITIALIZED
0x18000e9a7  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18000e9ae  jz      short loc_18000E9DC
0x18000e9b0  mov     eax, [rdi+6Ch]
0x18000e9b3  mov     [rsp+0C8h+var_88], eax
0x18000e9b7  mov     [rsp+0C8h+var_90], esi
0x18000e9bb  mov     [rsp+0C8h+var_98], r14
0x18000e9c0  mov     qword ptr [rsp+0C8h+Priority], rdi
0x18000e9c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9cc  mov     rcx, [rcx+40h]
0x18000e9d0  call    WPP_RECORDER_SF_qqDD
0x18000e9d5  lea     rcx, WPP_RECORDER_INITIALIZED
0x18000e9dc  test    esi, esi
0x18000e9de  js      loc_18000EE5C
0x18000e9e4  cmp     [rdi+61h], bl
0x18000e9e7  jz      loc_18000EA9C
0x18000e9ed  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18000e9f4  jz      short loc_18000EA2A
0x18000e9f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9fd  cmp     [rcx+48h], bx
0x18000ea01  jz      short loc_18000EA2A
0x18000ea03  mov     r9d, 4Ch ; 'L'
0x18000ea09  mov     [rsp+0C8h+var_98], r14
0x18000ea0e  mov     qword ptr [rsp+0C8h+Priority], rdi
0x18000ea13  lea     rax, WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids
0x18000ea1a  mov     qword ptr [rsp+0C8h+BugCheckOnFailure], rax
0x18000ea1f  mov     dl, 5
0x18000ea21  mov     rcx, [rcx+40h]
0x18000ea25  call    WPP_RECORDER_SF_qq
0x18000ea2a  mov     rdx, r14; struct _IRP *
0x18000ea2d  call    ?ZeroIrp@CKsQueue@@AEAAXPEAU_IRP@@@Z; CKsQueue::ZeroIrp(_IRP *)
0x18000ea32  mov     rcx, [rsp+0C8h+P]; P
0x18000ea37  test    rcx, rcx
0x18000ea3a  jz      short loc_18000EA52
0x18000ea3c  mov     edx, 636D534Bh; Tag
0x18000ea41  call    cs:__imp_ExFreePoolWithTag
0x18000ea48  nop     dword ptr [rax+rax+00h]
0x18000ea4d  mov     [rsp+0C8h+P], rbx
0x18000ea52  mov     rax, [r14+0B8h]
0x18000ea59  or      byte ptr [rax+3], 1
0x18000ea5d  mov     rdx, r14
0x18000ea60  mov     rcx, [rdi+50h]
0x18000ea64  call    KspDiscardKsIrp
0x18000ea69  mov     [r13+0], rbx
0x18000ea6d  or      ecx, 0FFFFFFFFh
0x18000ea70  lock xadd [r15], ecx
0x18000ea75  cmp     ecx, 1
0x18000ea78  jnz     short loc_18000EA92
0x18000ea7a  xor     r8d, r8d; Wait
0x18000ea7d  xor     edx, edx; Increment
0x18000ea7f  lea     rcx, [rdi+270h]; Event
0x18000ea86  call    cs:__imp_KeSetEvent
0x18000ea8d  nop     dword ptr [rax+rax+00h]
0x18000ea92  mov     eax, 103h
0x18000ea97  jmp     loc_18000EED4
0x18000ea9c  test    esi, esi
0x18000ea9e  js      loc_18000EE5C
0x18000eaa4  mov     rax, [r14+0B8h]
0x18000eaab  add     rax, 8
0x18000eaaf  mov     [rsp+0C8h+var_48], rax
0x18000eab7  mov     qword ptr [rax+4], 1
0x18000eabf  lea     rcx, [rax+10h]
0x18000eac3  mov     [rsp+0C8h+var_58], rcx
0x18000eac8  mov     [rcx], rbx
0x18000eacb  mov     [rsp+0C8h+var_50], rcx
0x18000ead0  mov     edx, [rax]; unsigned int
0x18000ead2  mov     [rsp+0C8h+arg_18], edx
0x18000ead9  mov     r13, [r14+18h]
0x18000eadd  mov     rcx, [r14+8]; MemoryDescriptorList
0x18000eae1  mov     [rsp+0C8h+var_70], rcx
0x18000eae6  test    edx, edx
0x18000eae8  jz      loc_18000EDE5
0x18000eaee  test    rcx, rcx
0x18000eaf1  jz      short loc_18000EB27
0x18000eaf3  test    byte ptr [rcx+0Ah], 5
0x18000eaf7  jz      short loc_18000EAFF
0x18000eaf9  mov     rax, [rcx+18h]
0x18000eafd  jmp     short loc_18000EB2B
0x18000eaff  mov     [rsp+0C8h+Priority], 40000020h; Priority
0x18000eb07  mov     [rsp+0C8h+BugCheckOnFailure], ebx; BugCheckOnFailure
0x18000eb0b  xor     r9d, r9d; RequestedAddress
0x18000eb0e  xor     edx, edx; AccessMode
0x18000eb10  lea     r8d, [r9+1]; CacheType
0x18000eb14  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x18000eb1b  nop     dword ptr [rax+rax+00h]
0x18000eb20  mov     rcx, [rsp+0C8h+var_70]
0x18000eb25  jmp     short loc_18000EB2B
0x18000eb27  mov     rax, [r13+28h]
0x18000eb2b  mov     [rsp+0C8h+var_60], rax
0x18000eb30  test    rcx, rcx
0x18000eb33  jz      short loc_18000EB3E
0x18000eb35  test    rax, rax
0x18000eb38  jz      loc_18000EDE0
0x18000eb3e  mov     eax, [r13+30h]
0x18000eb42  and     eax, 18000h
0x18000eb47  jz      short loc_18000EB52
0x18000eb49  cmp     [rdi+248h], rbx
0x18000eb50  jz      short loc_18000EB59
0x18000eb52  cmp     eax, 10000h
0x18000eb57  jnz     short loc_18000EB83
0x18000eb59  mov     rcx, [rsp+0C8h+P]; P
0x18000eb5e  test    rcx, rcx
0x18000eb61  jz      short loc_18000EB79
0x18000eb63  mov     edx, 636D534Bh; Tag
0x18000eb68  call    cs:__imp_ExFreePoolWithTag
0x18000eb6f  nop     dword ptr [rax+rax+00h]
0x18000eb74  mov     [rsp+0C8h+P], rbx
0x18000eb79  mov     esi, 0C000000Dh
0x18000eb7e  jmp     loc_18000EDE5
0x18000eb83  mov     rcx, rdi; this
0x18000eb86  call    ?GetAvailableFrameHeader@CKsQueue@@AEAAPEAU_KSPFRAME_HEADER@@K@Z; CKsQueue::GetAvailableFrameHeader(ulong)
0x18000eb8b  mov     rdx, rax
0x18000eb8e  mov     [rsp+0C8h+var_68], rax
0x18000eb93  test    rax, rax
0x18000eb96  jz      loc_18000EDE0
0x18000eb9c  mov     rcx, [rsp+0C8h+var_70]
0x18000eba1  test    rcx, rcx
0x18000eba4  jz      short loc_18000EBF2
0x18000eba6  cmp     [r13+20h], ebx
0x18000ebaa  jnz     short loc_18000EBF2
0x18000ebac  lea     rcx, WPP_RECORDER_INITIALIZED
0x18000ebb3  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18000ebba  jz      short loc_18000EB79
0x18000ebbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebc3  cmp     [rcx+48h], bx
0x18000ebc7  jz      short loc_18000EB79
0x18000ebc9  mov     r9d, 4Dh ; 'M'
0x18000ebcf  mov     [rsp+0C8h+var_98], r14
0x18000ebd4  mov     qword ptr [rsp+0C8h+Priority], rdi
0x18000ebd9  lea     rax, WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids
0x18000ebe0  mov     qword ptr [rsp+0C8h+BugCheckOnFailure], rax
0x18000ebe5  mov     dl, 5
0x18000ebe7  mov     rcx, [rcx+40h]
0x18000ebeb  call    WPP_RECORDER_SF_qq
0x18000ebf0  jmp     short loc_18000EB79
0x18000ebf2  mov     [rax+10h], rbx
0x18000ebf6  mov     [rax+18h], rdi
0x18000ebfa  mov     [rax+20h], r14
0x18000ebfe  mov     [rax+30h], r14
0x18000ec02  mov     r8, [rsp+0C8h+var_48]
0x18000ec0a  mov     [rax+38h], r8
0x18000ec0e  mov     [rax+28h], rcx
0x18000ec12  mov     [rax+40h], r13
0x18000ec16  mov     rax, [rsp+0C8h+var_60]
0x18000ec1b  mov     [rdx+48h], rax
0x18000ec1f  mov     eax, [r13+20h]
0x18000ec23  mov     [rdx+5Ch], eax
0x18000ec26  mov     [rdx+78h], rbx
0x18000ec2a  mov     eax, [r13+30h]
0x18000ec2e  mov     [rdx+98h], eax
0x18000ec34  mov     rax, [rsp+0C8h+P]
0x18000ec39  mov     [rdx+0A0h], rax
0x18000ec40  mov     [rsp+0C8h+P], rbx
0x18000ec45  mov     [rdx+0A8h], rbx
0x18000ec4c  mov     rax, [r13+28h]
0x18000ec50  mov     [rdx+70h], rax
0x18000ec54  mov     rax, [rdx+48h]
0x18000ec58  mov     [r13+28h], rax
0x18000ec5c  mov     rax, [rsp+0C8h+var_50]
0x18000ec61  mov     [rax], rdx
0x18000ec64  inc     dword ptr [r8+8]
0x18000ec68  mov     eax, [r13+30h]
0x18000ec6c  bt      eax, 0Ah
0x18000ec70  jnb     loc_18000ED4B
0x18000ec76  mov     edx, [r13+20h]; NumberOfBytes
0x18000ec7a  mov     ecx, 200h; PoolType
0x18000ec7f  mov     r8d, 6462534Bh; Tag
0x18000ec85  call    cs:__imp_ExAllocatePoolWithTag
0x18000ec8c  nop     dword ptr [rax+rax+00h]
0x18000ec91  mov     rcx, [rsp+0C8h+var_68]
0x18000ec96  mov     [rcx+78h], rax
0x18000ec9a  test    rax, rax
0x18000ec9d  jz      loc_18000EDE0
0x18000eca3  call    Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline
0x18000eca8  test    eax, eax
0x18000ecaa  jz      short loc_18000ECF6
0x18000ecac  mov     r8d, [r13+20h]; Size
0x18000ecb0  mov     rax, [rsp+0C8h+var_68]
0x18000ecb5  mov     rdx, [rax+70h]; Src
0x18000ecb9  mov     rcx, [rax+78h]; void *
0x18000ecbd  cmp     [r14+40h], bl
0x18000ecc1  jz      short loc_18000ECCA
0x18000ecc3  call    RtlCopyFromUser
0x18000ecc8  jmp     short loc_18000ECCF
0x18000ecca  call    RtlCopyVolatileMemory
0x18000eccf  jmp     short loc_18000ED0C
0x18000ecd1  mov     esi, eax
0x18000ecd3  mov     r14, [rsp+0C8h+arg_8]
0x18000ecdb  mov     [r14+30h], eax
0x18000ecdf  xor     ebx, ebx
0x18000ece1  mov     rdi, [rsp+0C8h+arg_0]
0x18000ece9  mov     r15, [rsp+0C8h+var_40]
0x18000ecf1  jmp     loc_18000EDE5
0x18000ecf6  mov     r8d, [r13+20h]; Size
0x18000ecfa  mov     rax, [rsp+0C8h+var_68]
0x18000ecff  mov     rdx, [rax+70h]; Src
  ... truncated ...
```
