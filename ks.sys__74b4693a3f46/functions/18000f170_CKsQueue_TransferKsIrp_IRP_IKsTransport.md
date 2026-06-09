# CKsQueue::TransferKsIrp(_IRP *,IKsTransport * *)

- ea: `0x18000f170`
- end: `0x18000f832`
- name: `?TransferKsIrp@CKsQueue@@UEAAJPEAU_IRP@@PEAPEAUIKsTransport@@@Z`
- size: `1730`
- prototype: `__int64 __fastcall(CKsQueue *__hidden this, struct _IRP *, struct IKsTransport **)`
- caller_count: `0`
- callee_count: `16`
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
- `0x18000f170`
- `0x180010794`
- `0x1800163e4`
- `0x180019bb0`
- `0x180019c60`
- `0x180050ffc`
- `0x180066360`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000f484`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000f6e7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000f484`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000f6e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000f3b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000f4d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000f3b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000f4d8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000f5f5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000f5f5`
- `ntoskrnl!KeSetEvent` at `0x18000f3f6`
- `ntoskrnl!KeSetEvent` at `0x18000f7e1`
- `ntoskrnl!KeSetEvent` at `0x18000f812`
- `ntoskrnl!KeSetEvent` at `0x18000f3f6`
- `ntoskrnl!KeSetEvent` at `0x18000f7e1`
- `ntoskrnl!KeSetEvent` at `0x18000f812`

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
  int v10; // r8d
  bool v11; // zf
  int v12; // esi
  ULONG m_ProbeFlags; // edx
  IKsMdlCache *m_MdlCacheComponent; // rcx
  int v15; // eax
  int v16; // r9d
  CKsQueue *v17; // rcx
  __int64 p_Parameters; // rax
  unsigned int v20; // edx
  struct _IRP *MasterIrp; // r13
  PMDL MdlAddress; // rcx
  PVOID MappedSystemVa; // rax
  struct _KSPFRAME_HEADER *AvailableFrameHeader; // rax
  int v25; // r8d
  struct _KSPFRAME_HEADER *v26; // rdx
  _MDL *v27; // rcx
  struct KSPIRP_FRAMING_ *v28; // r8
  unsigned int Status; // eax
  PVOID PoolWithTag; // rcx
  struct _KSPFRAME_HEADER *v31; // rax
  size_t Flink_low; // r8
  void *OriginalData; // rdx
  int v34; // eax
  struct _MDL *Next; // rcx
  PVOID v36; // rax
  __int64 v37; // rax
  struct _KSPFRAME_HEADER *i; // rsi
  struct _LIST_ENTRY *v39; // rcx
  struct _LIST_ENTRY **v40; // r15
  int BugCheckOnFailure; // [rsp+20h] [rbp-A8h]
  PVOID P; // [rsp+50h] [rbp-78h] BYREF
  struct _MDL *v43; // [rsp+58h] [rbp-70h]
  PVOID v44; // [rsp+60h] [rbp-68h]
  struct _KSPFRAME_HEADER *v45; // [rsp+68h] [rbp-60h]
  struct _KSPFRAME_HEADER **v46; // [rsp+70h] [rbp-58h]
  struct _KSPFRAME_HEADER **p_NextFrameHeaderInIrp; // [rsp+78h] [rbp-50h]
  struct KSPIRP_FRAMING_ *v48; // [rsp+80h] [rbp-48h]
  int *v49; // [rsp+88h] [rbp-40h]
  unsigned int v51; // [rsp+E8h] [rbp+20h]

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
        (__int64)WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids);
    }
  }
  if ( ((__int64)WPP_MAIN_CB.Dpc.SystemArgument1 & 2) != 0 )
    McTemplateK0p_EtwWriteTransfer(v6, KS_StreamingRequest_Start, a3, 0);
  p_m_TransportIrpsPlusOne = &this->m_TransportIrpsPlusOne;
  v49 = &this->m_TransportIrpsPlusOne;
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
      KspDiscardKsIrp(this->m_TransportSink, v4);
      *v3 = 0;
      v11 = _InterlockedExchangeAdd(p_m_TransportIrpsPlusOne, 0xFFFFFFFF) == 1;
LABEL_35:
      if ( v11 )
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
          v10,
          74,
          (__int64)WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids,
          (char)this,
          (char)v4);
      }
      this->m_EndOfStream = 0;
    }
    v12 = 259;
    m_ProbeFlags = this->m_ProbeFlags;
    if ( m_ProbeFlags )
    {
      m_MdlCacheComponent = this->m_MdlCacheComponent;
      v15 = m_MdlCacheComponent
          ? m_MdlCacheComponent->MdlCacheProbeStreamIrp(
              m_MdlCacheComponent,
              v4,
              m_ProbeFlags,
              (_KSPMDLCACHED_STREAM_POINTER **)&P)
          : KsProbeStreamIrp(v4, m_ProbeFlags, 0);
      v12 = v15;
      if ( v15 < 0 )
      {
        v17 = (CKsQueue *)&WPP_RECORDER_INITIALIZED;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_27;
        WPP_RECORDER_SF_qqDD(
          WPP_GLOBAL_Control->DeviceExtension,
          m_ProbeFlags,
          v10,
          v16,
          BugCheckOnFailure,
          (char)this,
          (char)v4,
          v15,
          this->m_ProbeFlags);
      }
    }
    v17 = (CKsQueue *)&WPP_RECORDER_INITIALIZED;
LABEL_27:
    if ( v12 >= 0 )
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
              v10,
              76,
              (__int64)WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids,
              (char)this,
              (char)v4);
          }
        }
        CKsQueue::ZeroIrp(v17, v4);
        if ( P )
        {
          ExFreePoolWithTag(P, 0x636D534Bu);
          P = 0;
        }
        v4->Tail.Overlay.CurrentStackLocation->Control |= 1u;
        KspDiscardKsIrp(this->m_TransportSink, v4);
        *v3 = 0;
        v11 = _InterlockedExchangeAdd(p_m_TransportIrpsPlusOne, 0xFFFFFFFF) == 1;
        goto LABEL_35;
      }
      p_Parameters = (__int64)&v4->Tail.Overlay.CurrentStackLocation->Parameters;
      v48 = (struct KSPIRP_FRAMING_ *)p_Parameters;
      *(_QWORD *)(p_Parameters + 4) = 1;
      v46 = (struct _KSPFRAME_HEADER **)(p_Parameters + 16);
      *(_QWORD *)(p_Parameters + 16) = 0;
      p_NextFrameHeaderInIrp = (struct _KSPFRAME_HEADER **)(p_Parameters + 16);
      v20 = *(_DWORD *)p_Parameters;
      v51 = *(_DWORD *)p_Parameters;
      MasterIrp = v4->AssociatedIrp.MasterIrp;
      MdlAddress = v4->MdlAddress;
LABEL_39:
      v43 = MdlAddress;
      while ( 1 )
      {
        if ( !v20 )
          goto LABEL_81;
        if ( MdlAddress )
        {
          if ( (MdlAddress->MdlFlags & 5) != 0 )
          {
            MappedSystemVa = MdlAddress->MappedSystemVa;
          }
          else
          {
            MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000020u);
            MdlAddress = v43;
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
          v12 = -1073741811;
          goto LABEL_81;
        }
        AvailableFrameHeader = CKsQueue::GetAvailableFrameHeader(this, v20);
        v26 = AvailableFrameHeader;
        v45 = AvailableFrameHeader;
        if ( !AvailableFrameHeader )
          break;
        v27 = v43;
        if ( v43 && !LODWORD(MasterIrp->ThreadListEntry.Flink) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            LOBYTE(v26) = 5;
            WPP_RECORDER_SF_qq(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)v26,
              v25,
              77,
              (__int64)WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids,
              (char)this,
              (char)v4);
          }
          goto LABEL_53;
        }
        AvailableFrameHeader->NextFrameHeaderInIrp = 0;
        AvailableFrameHeader->Queue = this;
        AvailableFrameHeader->OriginalIrp = v4;
        AvailableFrameHeader->Irp = v4;
        v28 = v48;
        AvailableFrameHeader->IrpFraming = v48;
        AvailableFrameHeader->Mdl = v27;
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
        *p_NextFrameHeaderInIrp = AvailableFrameHeader;
        ++v28->QueuedFrameHeaderCount;
        Status = MasterIrp->IoStatus.Status;
        if ( (Status & 0x400) != 0 )
        {
          PoolWithTag = ExAllocatePoolWithTag(NonPagedPoolNx, LODWORD(MasterIrp->ThreadListEntry.Flink), 0x6462534Bu);
          v31 = v45;
          v45->BufferedData = PoolWithTag;
          if ( !PoolWithTag )
            break;
          Flink_low = LODWORD(MasterIrp->ThreadListEntry.Flink);
          OriginalData = v31->OriginalData;
          if ( v4->RequestorMode )
            RtlCopyFromUser(PoolWithTag, OriginalData, Flink_low);
          else
            RtlCopyVolatileMemory(PoolWithTag, OriginalData, Flink_low);
          v26 = v45;
          MasterIrp->ThreadListEntry.Blink = (struct _LIST_ENTRY *)v45->BufferedData;
          Status = MasterIrp->IoStatus.Status;
          if ( (Status & 0x800) != 0 )
          {
            v34 = MapVramPhysicalAddress(v4, MasterIrp);
            v12 = v34;
            if ( v34 < 0 )
            {
              v4->IoStatus.Status = v34;
              goto LABEL_81;
            }
            Status = MasterIrp->IoStatus.Status;
            v26 = v45;
          }
          v27 = v43;
        }
        p_NextFrameHeaderInIrp = &v26->NextFrameHeaderInIrp;
        if ( (Status & 0x1000) != 0 && v27 )
        {
          v26->Metadata = (KSSTREAM_METADATA_INFO *)(&MasterIrp->Tail.CompletionKey + 1);
          Next = v27->Next;
          v43 = Next;
          if ( Next )
          {
            if ( (Next->MdlFlags & 5) != 0 )
              v36 = Next->MappedSystemVa;
            else
              v36 = MmMapLockedPagesSpecifyCache(Next, 0, MmCached, 0, 0, 0x40000020u);
          }
          else
          {
            v36 = 0;
          }
          MasterIrp->Tail.Overlay.DriverContext[3] = v36;
        }
        v37 = *(unsigned int *)&MasterIrp->Type;
        v20 = v51 - v37;
        v51 -= v37;
        MasterIrp = (struct _IRP *)((char *)MasterIrp + v37);
        MdlAddress = v43;
        if ( v43 )
        {
          MdlAddress = v43->Next;
          goto LABEL_39;
        }
      }
      v12 = -1073741670;
LABEL_81:
      if ( v12 >= 0 )
      {
        for ( i = *v46; i; i = i->NextFrameHeaderInIrp )
          CKsQueue::AddFrame(this, i);
        CKsQueue::ReleaseIrp(this, v4, v48, a3);
        goto LABEL_92;
      }
      v39 = (struct _LIST_ENTRY *)*v46;
      if ( *v46 )
      {
        v40 = (struct _LIST_ENTRY **)v46;
        do
        {
          *v40 = v39[1].Flink;
          CKsQueue::PutAvailableFrameHeader(this, v39);
          v39 = *v40;
        }
        while ( *v40 );
        p_m_TransportIrpsPlusOne = v49;
      }
      v3 = a3;
    }
    *v3 = 0;
    v4->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    KspDiscardKsIrp(this->m_TransportSink, v4);
LABEL_92:
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
0x18000f170  mov     [rsp+arg_10], r8
0x18000f175  mov     [rsp+arg_8], rdx
0x18000f17a  mov     [rsp+arg_0], rcx
0x18000f17f  push    rbx
0x18000f180  push    rsi
0x18000f181  push    rdi
0x18000f182  push    r13
0x18000f184  push    r14
0x18000f186  push    r15
0x18000f188  sub     rsp, 98h
0x18000f18f  mov     r13, r8
0x18000f192  mov     r14, rdx
0x18000f195  mov     rdi, rcx
0x18000f198  lea     rcx, WPP_RECORDER_INITIALIZED
0x18000f19f  xor     ebx, ebx
0x18000f1a1  lea     rsi, WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids
0x18000f1a8  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18000f1af  jz      short loc_18000F1D6
0x18000f1b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1b8  cmp     [rcx+48h], bx
0x18000f1bc  jz      short loc_18000F1D6
0x18000f1be  lea     r9d, [rbx+45h]
0x18000f1c2  mov     qword ptr [rsp+0C8h+BugCheckOnFailure], rsi
0x18000f1c7  lea     r8d, [rbx+1]
0x18000f1cb  mov     dl, 5
0x18000f1cd  mov     rcx, [rcx+40h]
0x18000f1d1  call    WPP_RECORDER_SF_
0x18000f1d6  mov     eax, dword ptr cs:WPP_MAIN_CB.Dpc.SystemArgument1
0x18000f1dc  test    al, 2
0x18000f1de  jz      short loc_18000F1EF
0x18000f1e0  xor     r9d, r9d
0x18000f1e3  lea     rdx, KS_StreamingRequest_Start
0x18000f1ea  call    McTemplateK0p_EtwWriteTransfer
0x18000f1ef  lea     r15, [rdi+268h]
0x18000f1f6  mov     [rsp+0C8h+var_40], r15
0x18000f1fe  mov     eax, 1
0x18000f203  lock xadd [r15], eax
0x18000f208  inc     eax
0x18000f20a  cmp     eax, 1
0x18000f20d  jle     loc_18000F7F1
0x18000f213  cmp     [rdi+60h], bl
0x18000f216  jnz     loc_18000F7F1
0x18000f21c  cmp     [rdi+64h], ebx
0x18000f21f  jz      loc_18000F7F1
0x18000f225  cmp     [r14+44h], bl
0x18000f229  jnz     loc_18000F7F1
0x18000f22f  cmp     [r14+30h], ebx
0x18000f233  jl      loc_18000F7F1
0x18000f239  mov     [rsp+0C8h+P], rbx
0x18000f23e  mov     rcx, [rdi+88h]
0x18000f245  mov     rax, [rcx]
0x18000f248  mov     rax, [rax+70h]
0x18000f24c  call    _guard_dispatch_icall
0x18000f251  test    eax, eax
0x18000f253  jns     short loc_18000F284
0x18000f255  mov     [r14+30h], eax
0x18000f259  mov     rax, [r14+0B8h]
0x18000f260  or      byte ptr [rax+3], 1
0x18000f264  mov     rdx, r14
0x18000f267  mov     rcx, [rdi+50h]
0x18000f26b  call    KspDiscardKsIrp
0x18000f270  mov     [r13+0], rbx
0x18000f274  or      eax, 0FFFFFFFFh
0x18000f277  lock xadd [r15], eax
0x18000f27c  cmp     eax, 1
0x18000f27f  jmp     loc_18000F3E8
0x18000f284  cmp     [rdi+61h], bl
0x18000f287  jz      short loc_18000F2CE
0x18000f289  cmp     [rdi+72h], bl
0x18000f28c  jz      short loc_18000F2CE
0x18000f28e  lea     rcx, WPP_RECORDER_INITIALIZED
0x18000f295  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18000f29c  jz      short loc_18000F2CB
0x18000f29e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2a5  cmp     [rcx+48h], bx
0x18000f2a9  jz      short loc_18000F2CB
0x18000f2ab  mov     r9d, 4Ah ; 'J'
0x18000f2b1  mov     [rsp+0C8h+var_98], r14
0x18000f2b6  mov     qword ptr [rsp+0C8h+Priority], rdi
0x18000f2bb  mov     qword ptr [rsp+0C8h+BugCheckOnFailure], rsi
0x18000f2c0  mov     dl, 5
0x18000f2c2  mov     rcx, [rcx+40h]
0x18000f2c6  call    WPP_RECORDER_SF_qq
0x18000f2cb  mov     [rdi+61h], bl
0x18000f2ce  mov     esi, 103h
0x18000f2d3  mov     edx, [rdi+6Ch]; ProbeFlags
0x18000f2d6  test    edx, edx
0x18000f2d8  jz      short loc_18000F345
0x18000f2da  mov     rcx, [rdi+248h]
0x18000f2e1  test    rcx, rcx
0x18000f2e4  jz      short loc_18000F2FF
0x18000f2e6  mov     rax, [rcx]
0x18000f2e9  mov     rax, [rax+30h]
0x18000f2ed  lea     r9, [rsp+0C8h+P]
0x18000f2f2  mov     r8d, edx
0x18000f2f5  mov     rdx, r14
0x18000f2f8  call    _guard_dispatch_icall
0x18000f2fd  jmp     short loc_18000F30A
0x18000f2ff  xor     r8d, r8d; HeaderSize
0x18000f302  mov     rcx, r14; Irp
0x18000f305  call    KsProbeStreamIrp
0x18000f30a  mov     esi, eax
0x18000f30c  test    eax, eax
0x18000f30e  jns     short loc_18000F345
0x18000f310  lea     rcx, WPP_RECORDER_INITIALIZED
0x18000f317  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18000f31e  jz      short loc_18000F34C
0x18000f320  mov     eax, [rdi+6Ch]
0x18000f323  mov     [rsp+0C8h+var_88], eax
0x18000f327  mov     [rsp+0C8h+var_90], esi
0x18000f32b  mov     [rsp+0C8h+var_98], r14
0x18000f330  mov     qword ptr [rsp+0C8h+Priority], rdi
0x18000f335  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f33c  mov     rcx, [rcx+40h]
0x18000f340  call    WPP_RECORDER_SF_qqDD
0x18000f345  lea     rcx, WPP_RECORDER_INITIALIZED
0x18000f34c  test    esi, esi
0x18000f34e  js      loc_18000F7A8
0x18000f354  cmp     [rdi+61h], bl
0x18000f357  jz      loc_18000F40C
0x18000f35d  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18000f364  jz      short loc_18000F39A
0x18000f366  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f36d  cmp     [rcx+48h], bx
0x18000f371  jz      short loc_18000F39A
0x18000f373  mov     r9d, 4Ch ; 'L'
0x18000f379  mov     [rsp+0C8h+var_98], r14
0x18000f37e  mov     qword ptr [rsp+0C8h+Priority], rdi
0x18000f383  lea     rax, WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids
0x18000f38a  mov     qword ptr [rsp+0C8h+BugCheckOnFailure], rax
0x18000f38f  mov     dl, 5
0x18000f391  mov     rcx, [rcx+40h]
0x18000f395  call    WPP_RECORDER_SF_qq
0x18000f39a  mov     rdx, r14; struct _IRP *
0x18000f39d  call    ?ZeroIrp@CKsQueue@@AEAAXPEAU_IRP@@@Z; CKsQueue::ZeroIrp(_IRP *)
0x18000f3a2  mov     rcx, [rsp+0C8h+P]; P
0x18000f3a7  test    rcx, rcx
0x18000f3aa  jz      short loc_18000F3C2
0x18000f3ac  mov     edx, 636D534Bh; Tag
0x18000f3b1  call    cs:__imp_ExFreePoolWithTag
0x18000f3b8  nop     dword ptr [rax+rax+00h]
0x18000f3bd  mov     [rsp+0C8h+P], rbx
0x18000f3c2  mov     rax, [r14+0B8h]
0x18000f3c9  or      byte ptr [rax+3], 1
0x18000f3cd  mov     rdx, r14
0x18000f3d0  mov     rcx, [rdi+50h]
0x18000f3d4  call    KspDiscardKsIrp
0x18000f3d9  mov     [r13+0], rbx
0x18000f3dd  or      ecx, 0FFFFFFFFh
0x18000f3e0  lock xadd [r15], ecx
0x18000f3e5  cmp     ecx, 1
0x18000f3e8  jnz     short loc_18000F402
0x18000f3ea  xor     r8d, r8d; Wait
0x18000f3ed  xor     edx, edx; Increment
0x18000f3ef  lea     rcx, [rdi+270h]; Event
0x18000f3f6  call    cs:__imp_KeSetEvent
0x18000f3fd  nop     dword ptr [rax+rax+00h]
0x18000f402  mov     eax, 103h
0x18000f407  jmp     loc_18000F820
0x18000f40c  test    esi, esi
0x18000f40e  js      loc_18000F7A8
0x18000f414  mov     rax, [r14+0B8h]
0x18000f41b  add     rax, 8
0x18000f41f  mov     [rsp+0C8h+var_48], rax
0x18000f427  mov     qword ptr [rax+4], 1
0x18000f42f  lea     rcx, [rax+10h]
0x18000f433  mov     [rsp+0C8h+var_58], rcx
0x18000f438  mov     [rcx], rbx
0x18000f43b  mov     [rsp+0C8h+var_50], rcx
0x18000f440  mov     edx, [rax]; unsigned int
0x18000f442  mov     [rsp+0C8h+arg_18], edx
0x18000f449  mov     r13, [r14+18h]
0x18000f44d  mov     rcx, [r14+8]; MemoryDescriptorList
0x18000f451  mov     [rsp+0C8h+var_70], rcx
0x18000f456  test    edx, edx
0x18000f458  jz      loc_18000F731
0x18000f45e  test    rcx, rcx
0x18000f461  jz      short loc_18000F497
0x18000f463  test    byte ptr [rcx+0Ah], 5
0x18000f467  jz      short loc_18000F46F
0x18000f469  mov     rax, [rcx+18h]
0x18000f46d  jmp     short loc_18000F49B
0x18000f46f  mov     [rsp+0C8h+Priority], 40000020h; Priority
0x18000f477  mov     [rsp+0C8h+BugCheckOnFailure], ebx; BugCheckOnFailure
0x18000f47b  xor     r9d, r9d; RequestedAddress
0x18000f47e  xor     edx, edx; AccessMode
0x18000f480  lea     r8d, [r9+1]; CacheType
0x18000f484  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x18000f48b  nop     dword ptr [rax+rax+00h]
0x18000f490  mov     rcx, [rsp+0C8h+var_70]
0x18000f495  jmp     short loc_18000F49B
0x18000f497  mov     rax, [r13+28h]
0x18000f49b  mov     [rsp+0C8h+var_68], rax
0x18000f4a0  test    rcx, rcx
0x18000f4a3  jz      short loc_18000F4AE
0x18000f4a5  test    rax, rax
0x18000f4a8  jz      loc_18000F72C
0x18000f4ae  mov     eax, [r13+30h]
0x18000f4b2  and     eax, 18000h
0x18000f4b7  jz      short loc_18000F4C2
0x18000f4b9  cmp     [rdi+248h], rbx
0x18000f4c0  jz      short loc_18000F4C9
0x18000f4c2  cmp     eax, 10000h
0x18000f4c7  jnz     short loc_18000F4F3
0x18000f4c9  mov     rcx, [rsp+0C8h+P]; P
0x18000f4ce  test    rcx, rcx
0x18000f4d1  jz      short loc_18000F4E9
0x18000f4d3  mov     edx, 636D534Bh; Tag
0x18000f4d8  call    cs:__imp_ExFreePoolWithTag
0x18000f4df  nop     dword ptr [rax+rax+00h]
0x18000f4e4  mov     [rsp+0C8h+P], rbx
0x18000f4e9  mov     esi, 0C000000Dh
0x18000f4ee  jmp     loc_18000F731
0x18000f4f3  mov     rcx, rdi; this
0x18000f4f6  call    ?GetAvailableFrameHeader@CKsQueue@@AEAAPEAU_KSPFRAME_HEADER@@K@Z; CKsQueue::GetAvailableFrameHeader(ulong)
0x18000f4fb  mov     rdx, rax
0x18000f4fe  mov     [rsp+0C8h+var_60], rax
0x18000f503  test    rax, rax
0x18000f506  jz      loc_18000F72C
0x18000f50c  mov     rcx, [rsp+0C8h+var_70]
0x18000f511  test    rcx, rcx
0x18000f514  jz      short loc_18000F562
0x18000f516  cmp     [r13+20h], ebx
0x18000f51a  jnz     short loc_18000F562
0x18000f51c  lea     rcx, WPP_RECORDER_INITIALIZED
0x18000f523  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18000f52a  jz      short loc_18000F4E9
0x18000f52c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f533  cmp     [rcx+48h], bx
0x18000f537  jz      short loc_18000F4E9
0x18000f539  mov     r9d, 4Dh ; 'M'
0x18000f53f  mov     [rsp+0C8h+var_98], r14
0x18000f544  mov     qword ptr [rsp+0C8h+Priority], rdi
0x18000f549  lea     rax, WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids
0x18000f550  mov     qword ptr [rsp+0C8h+BugCheckOnFailure], rax
0x18000f555  mov     dl, 5
0x18000f557  mov     rcx, [rcx+40h]
0x18000f55b  call    WPP_RECORDER_SF_qq
0x18000f560  jmp     short loc_18000F4E9
0x18000f562  mov     [rax+10h], rbx
0x18000f566  mov     [rax+18h], rdi
0x18000f56a  mov     [rax+20h], r14
0x18000f56e  mov     [rax+30h], r14
0x18000f572  mov     r8, [rsp+0C8h+var_48]
0x18000f57a  mov     [rax+38h], r8
0x18000f57e  mov     [rax+28h], rcx
0x18000f582  mov     [rax+40h], r13
0x18000f586  mov     rax, [rsp+0C8h+var_68]
0x18000f58b  mov     [rdx+48h], rax
0x18000f58f  mov     eax, [r13+20h]
0x18000f593  mov     [rdx+5Ch], eax
0x18000f596  mov     [rdx+78h], rbx
0x18000f59a  mov     eax, [r13+30h]
0x18000f59e  mov     [rdx+98h], eax
0x18000f5a4  mov     rax, [rsp+0C8h+P]
0x18000f5a9  mov     [rdx+0A0h], rax
0x18000f5b0  mov     [rsp+0C8h+P], rbx
0x18000f5b5  mov     [rdx+0A8h], rbx
0x18000f5bc  mov     rax, [r13+28h]
0x18000f5c0  mov     [rdx+70h], rax
0x18000f5c4  mov     rax, [rdx+48h]
0x18000f5c8  mov     [r13+28h], rax
0x18000f5cc  mov     rax, [rsp+0C8h+var_50]
0x18000f5d1  mov     [rax], rdx
0x18000f5d4  inc     dword ptr [r8+8]
0x18000f5d8  mov     eax, [r13+30h]
0x18000f5dc  bt      eax, 0Ah
0x18000f5e0  jnb     loc_18000F697
0x18000f5e6  mov     edx, [r13+20h]; NumberOfBytes
0x18000f5ea  mov     ecx, 200h; PoolType
0x18000f5ef  mov     r8d, 6462534Bh; Tag
0x18000f5f5  call    cs:__imp_ExAllocatePoolWithTag
0x18000f5fc  nop     dword ptr [rax+rax+00h]
0x18000f601  mov     rcx, rax; void *
0x18000f604  mov     rax, [rsp+0C8h+var_60]
0x18000f609  mov     [rax+78h], rcx
0x18000f60d  test    rcx, rcx
0x18000f610  jz      loc_18000F72C
0x18000f616  mov     r8d, [r13+20h]; Size
0x18000f61a  mov     rdx, [rax+70h]; Src
0x18000f61e  cmp     [r14+40h], bl
0x18000f622  jz      short loc_18000F62B
0x18000f624  call    RtlCopyFromUser
0x18000f629  jmp     short loc_18000F631
0x18000f62b  call    RtlCopyVolatileMemory
0x18000f630  nop
0x18000f631  mov     rdx, [rsp+0C8h+var_60]
0x18000f636  mov     rax, [rdx+78h]
0x18000f63a  mov     [r13+28h], rax
0x18000f63e  mov     eax, [r13+30h]
0x18000f642  bt      eax, 0Bh
0x18000f646  jnb     short loc_18000F66B
0x18000f648  mov     rdx, r13
0x18000f64b  mov     rcx, r14
0x18000f64e  call    MapVramPhysicalAddress
0x18000f653  mov     esi, eax
0x18000f655  test    eax, eax
0x18000f657  jns     short loc_18000F662
0x18000f659  mov     [r14+30h], eax
0x18000f65d  jmp     loc_18000F731
  ... truncated ...
```
