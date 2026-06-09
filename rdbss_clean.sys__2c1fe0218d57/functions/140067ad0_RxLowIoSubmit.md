# RxLowIoSubmit

- ea: `0x140067ad0`
- end: `0x14006805b`
- name: `RxLowIoSubmit`
- size: `1419`
- prototype: `NTSTATUS __stdcall(PRX_CONTEXT RxContext, PIRP Irp, PFCB Fcb, PLOWIO_COMPLETION_ROUTINE CompletionRoutine)`
- caller_count: `14`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400146a0`
- `0x140019aac`
- `0x14001a14c`
- `0x1400465c8`
- `0x140046c48`
- `0x14004aeb4`
- `0x14004b370`
- `0x140051c80`
- `0x140065ee0`
- `0x140065fa0`
- `0x140066280`
- `0x140066390`
- `0x1400679c0`
- `0x140068e90`

## callees

- `0x140002300`
- `0x1400105f0`
- `0x140010980`
- `0x1400123c0`
- `0x140013b70`
- `0x140016e20`
- `0x140017120`
- `0x140017280`
- `0x140017af0`
- `0x14001d5e8`
- `0x1400243c0`
- `0x140025d00`
- `0x140067ad0`
- `0x140068070`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140067c49`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140067c49`
- `ntoskrnl!KeClearEvent` at `0x140067d21`
- `ntoskrnl!KeClearEvent` at `0x140067d21`

## pseudocode

```c
NTSTATUS __stdcall RxLowIoSubmit(
        PRX_CONTEXT RxContext,
        PIRP Irp,
        PFCB Fcb,
        PLOWIO_COMPLETION_ROUTINE CompletionRoutine)
{
  unsigned int v5; // edi
  int v6; // esi
  bool v9; // r12
  NTSTATUS result; // eax
  struct _IO_STACK_LOCATION *v11; // rdx
  ULONG LowPart; // ecx
  int v13; // ecx
  unsigned int StoredStatus; // edi
  int v15; // ecx
  int v16; // ecx
  PMDL v17; // rcx
  wchar_t *MappedSystemVa; // rax
  LARGE_INTEGER ValidDataLength; // rbp
  __int64 v20; // rdx
  struct _LIST_ENTRY *Blink; // rcx
  struct _LIST_ENTRY *Flink; // rax
  __int64 (__fastcall *v23)(PRX_CONTEXT); // rax
  PMDL MdlAddress; // r8
  char v25; // al
  int v26; // [rsp+30h] [rbp-38h]
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+70h] [rbp+8h]

  v5 = *((unsigned __int16 *)&RxContext->9 + 60);
  v6 = (__int64)RxContext->RdbssDbgExtension & 0x1000;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v9 = v5 <= 1 && !v6 && (Irp->Flags & 2) != 0;
  *((_QWORD *)&RxContext->9 + 16) = CompletionRoutine;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v25 = 89;
    if ( v6 )
      v25 = 78;
    WPP_SF_Dqc(WPP_GLOBAL_Control->AttachedDevice, 78, Fcb, v5, RxContext, v25);
  }
  if ( ((__int64)RxContext->RdbssDbgExtension & 0x200000) == 0 && (*((_DWORD *)&Fcb->1 + 39) & 0x10000) != 0 )
  {
    RxContext->InformationToReturn = 0;
    result = RxShadowFastLowIo(RxContext, Irp);
    if ( result != -1073741802 )
      return result;
  }
  if ( v5 == 9 )
    goto LABEL_29;
  if ( v5 != 7 )
  {
    if ( v5 != 1 )
    {
      switch ( v5 )
      {
        case 0u:
          break;
        case 2u:
        case 3u:
        case 4u:
        case 5u:
        case 8u:
          goto LABEL_29;
        case 6u:
          goto LABEL_9;
        default:
          StoredStatus = -1073741811;
          goto LABEL_45;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v26 = *((_DWORD *)&RxContext->9 + 42);
      WPP_SF_qqDD(WPP_GLOBAL_Control->AttachedDevice, 10, &WPP_ab807026a5683cdcaf6085912ea536d5_Traceguids, RxContext);
    }
    RxLockUserBuffer(RxContext, Irp, (LOCK_OPERATION)(v5 == 0), *((_DWORD *)&RxContext->9 + 42));
    MdlAddress = Irp->MdlAddress;
    *((_QWORD *)&RxContext->9 + 18) = MdlAddress;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_Dqq(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        &WPP_ab807026a5683cdcaf6085912ea536d5_Traceguids,
        0,
        MdlAddress,
        Irp->MdlAddress,
        v26);
    }
    goto LABEL_29;
  }
LABEL_9:
  v11 = Irp->Tail.Overlay.CurrentStackLocation;
  LowPart = v11->Parameters.Read.ByteOffset.LowPart;
  *((_DWORD *)&RxContext->9 + 35) = LowPart;
  *((_DWORD *)&RxContext->9 + 42) = v11->Parameters.Create.Options;
  *((_DWORD *)&RxContext->9 + 43) = v11->Parameters.Read.Length;
  *((_BYTE *)&RxContext->9 + 176) = v11->MinorFunction;
  v13 = LowPart & 3;
  if ( v13 )
  {
    StoredStatus = 0;
    v15 = v13 - 1;
    if ( v15 && (v16 = v15 - 1) != 0 )
    {
      if ( v16 == 1 )
      {
        *((_QWORD *)&RxContext->9 + 19) = v11->Parameters.CreatePipe.Parameters;
        RxContext->Create.TransportName.Buffer = (wchar_t *)Irp->UserBuffer;
        goto LABEL_24;
      }
    }
    else
    {
      *((_QWORD *)&RxContext->9 + 19) = Irp->AssociatedIrp.MasterIrp;
      v17 = Irp->MdlAddress;
      if ( v17 )
      {
        if ( (v17->MdlFlags & 5) != 0 )
          MappedSystemVa = (wchar_t *)v17->MappedSystemVa;
        else
          MappedSystemVa = (wchar_t *)MmMapLockedPagesSpecifyCache(v17, 0, MmCached, 0, 0, 0x40000010u);
        StoredStatus = -1073741670;
        if ( MappedSystemVa )
          StoredStatus = 0;
      }
      else
      {
        MappedSystemVa = 0;
      }
      RxContext->Create.TransportName.Buffer = MappedSystemVa;
    }
    if ( StoredStatus )
      goto LABEL_45;
    goto LABEL_24;
  }
  StoredStatus = 0;
  *((_QWORD *)&RxContext->9 + 19) = Irp->AssociatedIrp.MasterIrp;
  RxContext->Create.TransportName.Buffer = (wchar_t *)Irp->AssociatedIrp.MasterIrp;
LABEL_24:
  if ( *((_DWORD *)&RxContext->9 + 42) && !*((_QWORD *)&RxContext->9 + 19) )
    StoredStatus = -1073741811;
  if ( *((_DWORD *)&RxContext->9 + 43) && !RxContext->Create.TransportName.Buffer )
  {
    StoredStatus = -1073741811;
    goto LABEL_45;
  }
  if ( StoredStatus )
    goto LABEL_45;
LABEL_29:
  if ( v6 )
  {
    if ( ((__int64)RxContext->RdbssDbgExtension & 0x200) == 0 )
      Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, &WPP_ab807026a5683cdcaf6085912ea536d5_Traceguids);
    }
  }
  ValidDataLength = RxContext->pFcb[2].Header.ValidDataLength;
  if ( ValidDataLength.QuadPart
    || (ValidDataLength = *(LARGE_INTEGER *)(*(_QWORD *)(*((_QWORD *)RxContext->pRelevantSrvOpen->ShadowContext->FastIoWrite
                                                         + 4)
                                                       + 48LL)
                                           + 352LL),
        ValidDataLength.QuadPart) )
  {
    while ( 1 )
    {
      RxContext->InformationToReturn = 0;
      RxContext->StoredStatus = 0;
      RxContext->Create.NtCreateParameters.AllocationSize.LowPart = 0;
      KeClearEvent((PRKEVENT)&RxContext->PrefixClaim.NetRootType);
      if ( (*((_DWORD *)&Fcb->1 + 39) & 0x10000) != 0 )
      {
        StoredStatus = RxShadowLowIo(RxContext, Irp, Fcb);
        if ( StoredStatus != -1073741802 )
          goto LABEL_42;
      }
      Blink = RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink;
      if ( Blink )
      {
        Flink = Blink[42].Flink;
        if ( Flink )
        {
          LOBYTE(v20) = 8;
          ((void (__fastcall *)(PRX_CONTEXT, __int64))Flink)(RxContext, v20);
        }
      }
      v23 = *(__int64 (__fastcall **)(PRX_CONTEXT))(ValidDataLength.QuadPart
                                                  + 8LL * *((unsigned __int16 *)&RxContext->9 + 60)
                                                  + 304);
      if ( v23 )
        break;
      StoredStatus = -1073741822;
LABEL_43:
      if ( v6 )
      {
        if ( StoredStatus != -1069481983 || RxContext->Create.NtCreateParameters.AllocationSize.LowPart )
        {
          if ( ((__int64)RxContext->RdbssDbgExtension & 0x200) == 0 )
            CurrentStackLocation->Control &= ~1u;
          goto LABEL_44;
        }
      }
      else
      {
LABEL_44:
        if ( StoredStatus != -1069481983 || RxContext->Create.NtCreateParameters.AllocationSize.LowPart )
          goto LABEL_45;
      }
    }
    StoredStatus = v23(RxContext);
LABEL_42:
    if ( StoredStatus == 259 )
    {
      if ( v6 )
        goto LABEL_47;
      if ( (int)RxCancellableWaitSync(RxContext) < 0 )
      {
        if ( !v9 || (RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.LockNV & 1) == 0 )
          RxCancelContext(RxContext);
        RxWaitSync(RxContext);
      }
      StoredStatus = RxContext->StoredStatus;
      goto LABEL_44;
    }
    goto LABEL_43;
  }
  StoredStatus = -1073741811;
LABEL_45:
  RxContext->StoredStatus = StoredStatus;
  *((_WORD *)&RxContext->9 + 61) |= 1u;
  StoredStatus = RxLowIoCompletionTail(RxContext);
LABEL_47:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, &WPP_ab807026a5683cdcaf6085912ea536d5_Traceguids, StoredStatus);
  }
  return StoredStatus;
}

```

## disassembly

```asm
0x140067ad0  mov     [rsp+arg_10], rbx
0x140067ad5  mov     [rsp+arg_18], rbp
0x140067ada  push    rsi
0x140067adb  push    rdi
0x140067adc  push    r12
0x140067ade  push    r13
0x140067ae0  push    r15
0x140067ae2  sub     rsp, 40h
0x140067ae6  mov     esi, [rcx+78h]
0x140067ae9  mov     r13, r8
0x140067aec  movzx   edi, word ptr [rcx+208h]
0x140067af3  and     esi, 1000h
0x140067af9  mov     rax, [rdx+0B8h]
0x140067b00  mov     r15, rdx
0x140067b03  mov     [rsp+68h+arg_0], rax
0x140067b08  mov     rbx, rcx
0x140067b0b  cmp     edi, 1
0x140067b0e  jbe     loc_140067BF5
0x140067b14  xor     r12b, r12b
0x140067b17  mov     [rcx+210h], r9
0x140067b1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140067b25  lea     rbp, WPP_GLOBAL_Control
0x140067b2c  cmp     rcx, rbp
0x140067b2f  jz      short loc_140067B3C
0x140067b31  mov     eax, [rcx+2Ch]
0x140067b34  test    al, 4
0x140067b36  jnz     loc_140067F5C
0x140067b3c  test    dword ptr [rbx+78h], 200000h
0x140067b43  setz    cl
0x140067b46  test    dword ptr [r13+9Ch], 10000h
0x140067b51  setnz   al
0x140067b54  test    al, cl
0x140067b56  jz      short loc_140067B79
0x140067b58  mov     rdx, r15; Irp
0x140067b5b  mov     qword ptr [rbx+0B8h], 0
0x140067b66  mov     rcx, rbx; RxContext
0x140067b69  call    RxShadowFastLowIo
0x140067b6e  cmp     eax, 0C0000016h
0x140067b73  jnz     loc_140067DEC
0x140067b79  mov     [rsp+68h+arg_8], r14
0x140067b7e  cmp     edi, 9
0x140067b81  jz      loc_140067CA2; jumptable 000000014007E702 cases 2-5,8
0x140067b87  cmp     edi, 7
0x140067b8a  jnz     loc_140067E32
0x140067b90  mov     rdx, [r15+0B8h]; jumptable 000000014007E702 case 6
0x140067b97  mov     ecx, [rdx+18h]
0x140067b9a  mov     [rbx+21Ch], ecx
0x140067ba0  mov     eax, [rdx+10h]
0x140067ba3  mov     [rbx+238h], eax
0x140067ba9  mov     eax, [rdx+8]
0x140067bac  mov     [rbx+23Ch], eax
0x140067bb2  movzx   eax, byte ptr [rdx+1]
0x140067bb6  mov     [rbx+240h], al
0x140067bbc  and     ecx, 3
0x140067bbf  jz      loc_140067E15
0x140067bc5  xor     edi, edi
0x140067bc7  sub     ecx, 1
0x140067bca  jz      short loc_140067C10
0x140067bcc  sub     ecx, 1
0x140067bcf  jz      short loc_140067C10
0x140067bd1  cmp     ecx, 1
0x140067bd4  jnz     loc_140067C6E
0x140067bda  mov     rax, [rdx+20h]
0x140067bde  mov     [rbx+228h], rax
0x140067be5  mov     rax, [r15+70h]
0x140067be9  mov     [rbx+230h], rax
0x140067bf0  jmp     loc_140067C76
0x140067bf5  test    esi, esi
0x140067bf7  jnz     loc_140067B14
0x140067bfd  mov     eax, [rdx+10h]
0x140067c00  test    al, 2
0x140067c02  jz      loc_140067B14
0x140067c08  mov     r12b, 1
0x140067c0b  jmp     loc_140067B17
0x140067c10  mov     rax, [r15+18h]
0x140067c14  mov     [rbx+228h], rax
0x140067c1b  mov     rcx, [r15+8]; MemoryDescriptorList
0x140067c1f  test    rcx, rcx
0x140067c22  jz      loc_140067F35
0x140067c28  test    byte ptr [rcx+0Ah], 5
0x140067c2c  jnz     loc_140067F2C
0x140067c32  mov     [rsp+68h+Priority], 40000010h; Priority
0x140067c3a  xor     r9d, r9d; RequestedAddress
0x140067c3d  xor     edx, edx; AccessMode
0x140067c3f  mov     [rsp+68h+BugCheckOnFailure], edi; BugCheckOnFailure
0x140067c43  mov     r8d, 1; CacheType
0x140067c49  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140067c50  nop     dword ptr [rax+rax+00h]
0x140067c55  xor     ecx, ecx
0x140067c57  mov     edi, 0C000009Ah
0x140067c5c  test    rax, rax
0x140067c5f  cmovnz  edi, ecx
0x140067c62  mov     ecx, 230h
0x140067c67  mov     rdx, rbx
0x140067c6a  mov     [rbx+rcx], rax
0x140067c6e  test    edi, edi
0x140067c70  jnz     loc_140067DA5
0x140067c76  cmp     dword ptr [rbx+238h], 0
0x140067c7d  jbe     short loc_140067C8D
0x140067c7f  cmp     qword ptr [rbx+228h], 0
0x140067c87  jz      loc_140067FC9
0x140067c8d  cmp     dword ptr [rbx+23Ch], 0
0x140067c94  ja      loc_140067EC8
0x140067c9a  test    edi, edi
0x140067c9c  jnz     loc_140067DA5
0x140067ca2  test    esi, esi; jumptable 000000014007E702 cases 2-5,8
0x140067ca4  jz      short loc_140067CD1
0x140067ca6  test    dword ptr [rbx+78h], 200h
0x140067cad  jnz     short loc_140067CBA
0x140067caf  mov     rax, [r15+0B8h]
0x140067cb6  or      byte ptr [rax+3], 1
0x140067cba  mov     rcx, cs:WPP_GLOBAL_Control
0x140067cc1  cmp     rcx, rbp
0x140067cc4  jz      short loc_140067CD1
0x140067cc6  mov     eax, [rcx+2Ch]
0x140067cc9  test    al, 4
0x140067ccb  jnz     loc_140067FD3
0x140067cd1  mov     rax, [rbx+38h]
0x140067cd5  mov     rbp, [rax+188h]
0x140067cdc  test    rbp, rbp
0x140067cdf  jnz     short loc_140067D05
0x140067ce1  mov     rax, [rbx+48h]
0x140067ce5  mov     rcx, [rax+28h]
0x140067ce9  mov     rax, [rcx+20h]
0x140067ced  mov     rcx, [rax+20h]
0x140067cf1  mov     rax, [rcx+30h]
0x140067cf5  mov     rbp, [rax+160h]
0x140067cfc  test    rbp, rbp
0x140067cff  jz      loc_14006802A
0x140067d05  xor     eax, eax
0x140067d07  lea     rcx, [rbx+180h]; Event
0x140067d0e  mov     [rbx+0B8h], rax
0x140067d15  mov     [rbx+0B0h], eax
0x140067d1b  mov     [rbx+198h], eax
0x140067d21  call    cs:__imp_KeClearEvent
0x140067d28  nop     dword ptr [rax+rax+00h]
0x140067d2d  test    dword ptr [r13+9Ch], 10000h
0x140067d38  jnz     loc_140067F3C
0x140067d3e  mov     rax, [rbx+50h]
0x140067d42  mov     rcx, [rax+160h]
0x140067d49  test    rcx, rcx
0x140067d4c  jz      short loc_140067D64
0x140067d4e  mov     rax, [rcx+2A0h]
0x140067d55  test    rax, rax
0x140067d58  jz      short loc_140067D64
0x140067d5a  mov     dl, 8
0x140067d5c  mov     rcx, rbx
0x140067d5f  call    _guard_dispatch_icall
0x140067d64  movzx   eax, word ptr [rbx+208h]
0x140067d6b  mov     rax, [rbp+rax*8+130h]
0x140067d73  test    rax, rax
0x140067d76  jz      loc_140067F22
0x140067d7c  mov     rcx, rbx
0x140067d7f  call    _guard_dispatch_icall
0x140067d84  mov     edi, eax
0x140067d86  cmp     edi, 103h
0x140067d8c  jz      short loc_140067DBF
0x140067d8e  test    esi, esi
0x140067d90  jnz     loc_140067EFB
0x140067d96  cmp     edi, 0C0410001h
0x140067d9c  jz      short loc_140067E06
0x140067d9e  lea     rbp, WPP_GLOBAL_Control
0x140067da5  mov     [rbx+0B0h], edi
0x140067dab  mov     rcx, rbx; RxContext
0x140067dae  or      word ptr [rbx+20Ah], 1
0x140067db6  call    RxLowIoCompletionTail
0x140067dbb  mov     edi, eax
0x140067dbd  jmp     short loc_140067DCE
0x140067dbf  test    esi, esi
0x140067dc1  jz      loc_140067EE0
0x140067dc7  lea     rbp, WPP_GLOBAL_Control
0x140067dce  mov     rcx, cs:WPP_GLOBAL_Control
0x140067dd5  mov     r14, [rsp+68h+arg_8]
0x140067dda  cmp     rcx, rbp
0x140067ddd  jz      short loc_140067DEA
0x140067ddf  mov     eax, [rcx+2Ch]
0x140067de2  test    al, 4
0x140067de4  jnz     loc_140068034
0x140067dea  mov     eax, edi
0x140067dec  lea     r11, [rsp+68h+var_28]
0x140067df1  mov     rbx, [r11+40h]
0x140067df5  mov     rbp, [r11+48h]
0x140067df9  mov     rsp, r11
0x140067dfc  pop     r15
0x140067dfe  pop     r13
0x140067e00  pop     r12
0x140067e02  pop     rdi
0x140067e03  pop     rsi
0x140067e04  retn
0x140067e06  cmp     dword ptr [rbx+198h], 0
0x140067e0d  jz      loc_140067D05
0x140067e13  jmp     short loc_140067D9E
0x140067e15  mov     rax, [r15+18h]
0x140067e19  xor     edi, edi
0x140067e1b  mov     [rbx+228h], rax
0x140067e22  mov     rax, [r15+18h]
0x140067e26  mov     [rbx+230h], rax
0x140067e2d  jmp     loc_140067C76
0x140067e32  cmp     edi, 1
0x140067e35  jnz     loc_14007E6EC
0x140067e3b  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 000000014007E702 case 0
0x140067e42  cmp     rcx, rbp
0x140067e45  jz      short loc_140067E52
0x140067e47  mov     eax, [rcx+2Ch]
0x140067e4a  test    al, 2
0x140067e4c  jnz     loc_140067F8F
0x140067e52  mov     r9d, [rbx+238h]; BufferLength
0x140067e59  xor     r8d, r8d
0x140067e5c  test    edi, edi
0x140067e5e  mov     rdx, r15; Irp
0x140067e61  mov     rcx, rbx; RxContext
0x140067e64  setz    r8b; Operation
0x140067e68  call    RxLockUserBuffer
0x140067e6d  mov     r8, [r15+8]
0x140067e71  mov     [rbx+220h], r8
0x140067e78  mov     rcx, cs:WPP_GLOBAL_Control
0x140067e7f  cmp     rcx, rbp
0x140067e82  jz      loc_140067CA2; jumptable 000000014007E702 cases 2-5,8
0x140067e88  mov     eax, [rcx+2Ch]
0x140067e8b  test    al, 2
0x140067e8d  jz      loc_140067CA2; jumptable 000000014007E702 cases 2-5,8
0x140067e93  cmp     byte ptr [rcx+29h], 4
0x140067e97  jb      loc_140067CA2; jumptable 000000014007E702 cases 2-5,8
0x140067e9d  mov     rax, [r15+8]
0x140067ea1  mov     edx, 0Bh
0x140067ea6  mov     rcx, [rcx+18h]
0x140067eaa  xor     r9d, r9d
0x140067ead  mov     qword ptr [rsp+68h+Priority], rax
0x140067eb2  mov     qword ptr [rsp+68h+BugCheckOnFailure], r8
0x140067eb7  lea     r8, WPP_ab807026a5683cdcaf6085912ea536d5_Traceguids
0x140067ebe  call    WPP_SF_Dqq
0x140067ec3  jmp     loc_140067CA2; jumptable 000000014007E702 cases 2-5,8
0x140067ec8  cmp     qword ptr [rbx+230h], 0
0x140067ed0  jnz     loc_140067C9A
0x140067ed6  mov     edi, 0C000000Dh
0x140067edb  jmp     loc_140067DA5
0x140067ee0  mov     rcx, rbx
0x140067ee3  call    RxCancellableWaitSync
0x140067ee8  test    eax, eax
0x140067eea  js      loc_140067FF7
0x140067ef0  mov     edi, [rbx+0B0h]
0x140067ef6  jmp     loc_140067D96
0x140067efb  cmp     edi, 0C0410001h
0x140067f01  jz      loc_140068018
0x140067f07  test    dword ptr [rbx+78h], 200h
0x140067f0e  jnz     loc_140067D96
0x140067f14  mov     rax, [rsp+68h+arg_0]
0x140067f19  and     byte ptr [rax+3], 0FEh
0x140067f1d  jmp     loc_140067D96
0x140067f22  mov     edi, 0C0000002h
0x140067f27  jmp     loc_140067D8E
0x140067f2c  mov     rax, [rcx+18h]
0x140067f30  jmp     loc_140067C55
0x140067f35  xor     eax, eax
0x140067f37  jmp     loc_140067C62
0x140067f3c  mov     r8, r13; Fcb
0x140067f3f  mov     rdx, r15; Irp
0x140067f42  mov     rcx, rbx; RxContext
0x140067f45  call    RxShadowLowIo
0x140067f4a  mov     edi, eax
0x140067f4c  cmp     eax, 0C0000016h
0x140067f51  jnz     loc_140067D86
0x140067f57  jmp     loc_140067D3E
0x140067f5c  cmp     byte ptr [rcx+29h], 4
0x140067f60  jb      loc_140067B3C
0x140067f66  mov     rcx, [rcx+18h]
0x140067f6a  test    esi, esi
0x140067f6c  mov     eax, 59h ; 'Y'
0x140067f71  mov     edx, 4Eh ; 'N'
0x140067f76  cmovnz  eax, edx
0x140067f79  mov     r9d, edi
0x140067f7c  mov     byte ptr [rsp+68h+Priority], al
0x140067f80  mov     qword ptr [rsp+68h+BugCheckOnFailure], rbx
0x140067f85  call    WPP_SF_Dqc
0x140067f8a  jmp     loc_140067B3C
0x140067f8f  cmp     byte ptr [rcx+29h], 4
0x140067f93  jb      loc_140067E52
0x140067f99  mov     eax, [rbx+238h]
0x140067f9f  lea     r8, WPP_ab807026a5683cdcaf6085912ea536d5_Traceguids
0x140067fa6  mov     rcx, [rcx+18h]
0x140067faa  mov     edx, 0Ah
0x140067faf  mov     [rsp+68h+var_38], eax
0x140067fb3  mov     r9, rbx
0x140067fb6  mov     [rsp+68h+Priority], edi
0x140067fba  mov     qword ptr [rsp+68h+BugCheckOnFailure], r15
0x140067fbf  call    WPP_SF_qqDD
0x140067fc4  jmp     loc_140067E52
0x140067fc9  mov     edi, 0C000000Dh
0x140067fce  jmp     loc_140067C8D
0x140067fd3  cmp     byte ptr [rcx+29h], 4
0x140067fd7  jb      loc_140067CD1
0x140067fdd  mov     rcx, [rcx+18h]
0x140067fe1  lea     r8, WPP_ab807026a5683cdcaf6085912ea536d5_Traceguids
0x140067fe8  mov     edx, 16h
0x140067fed  call    WPP_SF_
0x140067ff2  jmp     loc_140067CD1
0x140067ff7  test    r12b, r12b
0x140067ffa  jz      loc_14007E712
0x140068000  mov     rax, [rbx+50h]
0x140068004  mov     ecx, [rax+150h]
  ... truncated ...
```
