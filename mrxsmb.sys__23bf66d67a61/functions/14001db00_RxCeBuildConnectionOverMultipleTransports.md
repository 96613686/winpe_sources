# RxCeBuildConnectionOverMultipleTransports

- ea: `0x14001db00`
- end: `0x14001e388`
- name: `RxCeBuildConnectionOverMultipleTransports`
- size: `2184`
- prototype: `NTSTATUS __stdcall(PRDBSS_DEVICE_OBJECT pMiniRedirectorDeviceObject, RXCE_CONNECTION_CREATE_OPTIONS CreateOption, ULONG NumberOfAddresses, PRXCE_ADDRESS *pLocalAddressPointers, PUNICODE_STRING pServerName, PRXCE_CONNECTION_INFORMATION pConnectionInformation, PRXCE_CONNECTION_EVENT_HANDLER pHandler, PVOID pEventContext, PRXCE_CONNECTION_COMPLETION_ROUTINE pCompletionRoutine, PRXCE_CONNECTION_COMPLETION_CONTEXT pCompletionContext)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140024790`

## callees

- `0x14001db00`
- `0x14001e390`
- `0x14001e440`
- `0x14001e514`
- `0x140024790`
- `0x140025584`
- `0x14003838c`
- `0x140039fa8`
- `0x14004ac38`
- `0x140059dc0`
- `0x140059ea0`
- `0x140059f00`
- `0x14008eb20`
- `0x1400903a0`
- `0x140091370`
- `0x140091a30`
- `0x140092640`
- `0x140093810`
- `0x1400958f0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001e246`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001e246`
- `ntoskrnl!KeDelayExecutionThread` at `0x14001e2bf`
- `ntoskrnl!KeDelayExecutionThread` at `0x14001e2bf`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14001e319`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14001e319`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14001dba8`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14001dba8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e27f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e27f`
- `ntoskrnl!ExAllocatePool2` at `0x14001dd8b`
- `ntoskrnl!ExAllocatePool2` at `0x14001dd8b`
- `rdbss!RxDereferenceSiloAndReleaseRundown` at `0x14001e328`
- `rdbss!RxDereferenceSiloAndReleaseRundown` at `0x14001e328`
- `rdbss!RxReferenceSiloAndAcquireRundown` at `0x14001db8b`
- `rdbss!RxReferenceSiloAndAcquireRundown` at `0x14001db8b`
- `rdbss!RxRegisterAsynchronousRequest` at `0x14001ddbb`
- `rdbss!RxRegisterAsynchronousRequest` at `0x14001ddbb`

## pseudocode

```c
NTSTATUS __stdcall RxCeBuildConnectionOverMultipleTransports(
        PRDBSS_DEVICE_OBJECT pMiniRedirectorDeviceObject,
        RXCE_CONNECTION_CREATE_OPTIONS CreateOption,
        ULONG NumberOfAddresses,
        PRXCE_ADDRESS *pLocalAddressPointers,
        PUNICODE_STRING pServerName,
        PRXCE_CONNECTION_INFORMATION pConnectionInformation,
        PRXCE_CONNECTION_EVENT_HANDLER pHandler,
        PVOID pEventContext,
        PRXCE_CONNECTION_COMPLETION_ROUTINE pCompletionRoutine,
        PRXCE_CONNECTION_COMPLETION_CONTEXT pCompletionContext)
{
  __int64 v11; // rdi
  struct _LIST_ENTRY *Flink; // rbx
  struct _LIST_ENTRY *Blink; // r14
  char v14; // al
  __int64 v15; // rcx
  __int64 v16; // rax
  struct _IRP *CurrentIrp; // r8
  __int64 v18; // rdx
  __int64 Pointer_high; // rcx
  NTSTATUS v20; // ebx
  unsigned int v21; // r12d
  PDRIVER_CONTROL DeviceRoutine; // r15
  unsigned int v23; // r13d
  int v24; // ebx
  int v25; // r8d
  int v26; // ebx
  __int64 v27; // rdx
  int v28; // ecx
  struct _IO_TIMER *Pool2; // rax
  unsigned int v30; // r13d
  unsigned int v31; // r12d
  unsigned int v32; // eax
  _WORD *v33; // rbx
  __int64 v34; // rax
  void *v35; // rdi
  __int64 v36; // r14
  int v37; // r12d
  SOCKADDR_IN *ServerTransport; // r15
  __int64 v39; // rbx
  CHAR *v40; // rdi
  _WORD *v41; // rcx
  __int64 SectorSize; // rax
  const UCHAR *v43; // rax
  _BYTE *v44; // rdx
  unsigned int v45; // r13d
  unsigned int v46; // edi
  unsigned int i; // r8d
  __int64 v48; // rax
  char *v49; // rdx
  __int64 v50; // rcx
  _QWORD *v51; // rax
  BOOL v52; // r15d
  KIRQL v53; // al
  unsigned int v54; // r14d
  int j; // ebx
  __int64 v56; // rdi
  char v58; // [rsp+40h] [rbp-D8h]
  unsigned int v59; // [rsp+44h] [rbp-D4h]
  unsigned int v60; // [rsp+48h] [rbp-D0h]
  unsigned int v61; // [rsp+4Ch] [rbp-CCh]
  _WORD *v62; // [rsp+50h] [rbp-C8h]
  struct _IO_TIMER *v63; // [rsp+58h] [rbp-C0h]
  unsigned int v64; // [rsp+60h] [rbp-B8h]
  _OWORD *v65; // [rsp+68h] [rbp-B0h]
  _DWORD v66[4]; // [rsp+70h] [rbp-A8h]
  _DWORD *v67; // [rsp+80h] [rbp-98h]
  int v68; // [rsp+88h] [rbp-90h]
  BOOL v69; // [rsp+8Ch] [rbp-8Ch]
  int v70; // [rsp+90h] [rbp-88h]
  __int64 v71; // [rsp+98h] [rbp-80h]
  struct _LIST_ENTRY *v72; // [rsp+A0h] [rbp-78h]
  __int64 v73; // [rsp+A8h] [rbp-70h]
  __int64 v74; // [rsp+B0h] [rbp-68h]
  __int64 v75; // [rsp+B8h] [rbp-60h]
  PVOID DeviceExtension; // [rsp+C0h] [rbp-58h]
  SOCKADDR_INET BestSourceAddress; // [rsp+C8h] [rbp-50h] BYREF

  LODWORD(v11) = 0;
  v69 = MRxSmbObeyBindingOrder != 0;
  DeviceExtension = pMiniRedirectorDeviceObject->DeviceObject.DeviceExtension;
  v75 = *(_QWORD *)&pMiniRedirectorDeviceObject->DeviceType;
  Flink = pMiniRedirectorDeviceObject->DeviceObject.Queue.ListEntry.Flink;
  Blink = pMiniRedirectorDeviceObject->DeviceObject.Queue.ListEntry.Blink;
  v72 = Blink;
  v14 = BYTE6(pMiniRedirectorDeviceObject->DeviceQueue.Lock);
  v58 = v14;
  v74 = 0;
  v15 = *(_QWORD *)&pMiniRedirectorDeviceObject->Dpc.TargetInfoAsUlong;
  if ( v15 )
  {
    v16 = RxReferenceSiloAndAcquireRundown(v15, CreateOption, NumberOfAddresses, pLocalAddressPointers);
    v73 = v16;
    if ( !v16 )
    {
      v20 = -1073741536;
      goto LABEL_111;
    }
    v74 = PsAttachSiloToCurrentThread(*(_QWORD *)(v16 + 40));
    CurrentIrp = pMiniRedirectorDeviceObject->DeviceObject.CurrentIrp;
    if ( (*(_DWORD *)(&CurrentIrp[1].Tail.CompletionKey + 1) & 0x2000) != 0
      && (v18 = *(_QWORD *)&pMiniRedirectorDeviceObject->Dpc.TargetInfoAsUlong,
          Pointer_high = HIDWORD(CurrentIrp[6].IoStatus.Pointer),
          (unsigned int)Pointer_high < *(_DWORD *)(v18 + 4)) )
    {
      v71 = *(_QWORD *)(v18 + 8 * Pointer_high + 48);
    }
    else
    {
      v71 = 0;
    }
    v14 = v58;
  }
  else
  {
    v71 = 0;
    v73 = 0;
  }
  v21 = 0;
  v64 = 0;
  DeviceRoutine = pMiniRedirectorDeviceObject->DeviceObject.Queue.Wcb.DeviceRoutine;
  v62 = DeviceRoutine;
  if ( DeviceRoutine )
  {
    v21 = *((unsigned __int16 *)DeviceRoutine + 1);
    v64 = v21;
  }
  if ( !pMiniRedirectorDeviceObject->DeviceObject.DeviceQueue.Busy )
    goto LABEL_15;
  if ( !DeviceRoutine )
    goto LABEL_17;
  if ( (*(_BYTE *)DeviceRoutine & 4) == 0 )
  {
    v14 = v58;
  }
  else
  {
LABEL_15:
    v14 = 1;
    v58 = 1;
  }
LABEL_17:
  if ( Blink || v14 && v21 )
    v23 = v21;
  else
    v23 = v21 + LODWORD(Flink->Blink);
  v60 = v23;
  v24 = HowToUseWskAndQuic(pMiniRedirectorDeviceObject);
  if ( (_BYTE)word_14007D202 && !(unsigned __int8)MRxSmbIsRdmaRundownActive() )
  {
    v66[0] = 2;
    LODWORD(v11) = 1;
  }
  if ( v24 == 1 )
  {
    v66[(unsigned int)v11] = 1;
  }
  else if ( v24 )
  {
    v26 = v24 - 2;
    if ( v26 )
    {
      if ( v26 != 1 )
      {
        if ( DeviceRoutine )
        {
          v27 = (__int64)DeviceRoutine + 136;
          v28 = 28;
          if ( *((_WORD *)DeviceRoutine + 68) == 2 )
            v28 = 16;
        }
        else
        {
          v28 = 0;
          v27 = 0;
        }
        if ( (byte_1400712C2 & 2) != 0 )
          McTemplateK0hzr0qqbr3_EtwWriteTransfer(
            v28,
            (unsigned int)RequestedTransportDisabled,
            v25,
            LOWORD(pMiniRedirectorDeviceObject->Flags) >> 1,
            (__int64)pMiniRedirectorDeviceObject->DeviceObject.Vpb,
            4,
            v28,
            v27);
        v20 = -1073741247;
        goto LABEL_111;
      }
      v66[(unsigned int)v11] = 4;
      v11 = (unsigned int)(v11 + 1);
      v66[v11] = 1;
      v23 += v21;
      v60 = v23;
    }
    else
    {
      v66[(unsigned int)v11] = 4;
    }
  }
  else
  {
    v66[(unsigned int)v11] = 1;
    v11 = (unsigned int)(v11 + 1);
    v66[v11] = 4;
    v23 += v21;
    v60 = v23;
  }
  Pool2 = (struct _IO_TIMER *)ExAllocatePool2(64, 264LL * v23, 1649440850);
  v63 = Pool2;
  if ( !Pool2 )
  {
    v20 = -1073741670;
    goto LABEL_111;
  }
  pMiniRedirectorDeviceObject->DeviceObject.Timer = Pool2;
  RxCeReferenceConnectionCallOutContext(pMiniRedirectorDeviceObject);
  v20 = RxRegisterAsynchronousRequest((PRDBSS_DEVICE_OBJECT)pMiniRedirectorDeviceObject->DeviceObject.CurrentIrp);
  if ( v20 )
    goto LABEL_110;
  v30 = 0;
  v31 = v11 + 1;
  v61 = v11 + 1;
  pMiniRedirectorDeviceObject->PagingReadBytesRequested.LowPart |= 1u;
  v32 = 0;
  memset(&BestSourceAddress, 0, sizeof(BestSourceAddress));
  v33 = (_WORD *)((char *)DeviceRoutine + 136);
  while ( 1 )
  {
    v59 = v32;
    v65 = v33;
    if ( v32 >= v64 )
      break;
    v34 = RxCepSelectTransportForAddress(
            &BestSourceAddress,
            (__int64)pMiniRedirectorDeviceObject->DeviceObject.CurrentIrp);
    v35 = (void *)v34;
    v67 = (_DWORD *)v34;
    if ( !v34 )
      goto LABEL_83;
    if ( *(_DWORD *)(v34 + 56) == 1
      && (*v33 == 2 && *(_WORD *)(v34 + 64) || *v33 == 23 && *(_WORD *)(v34 + 66))
      && (!Blink || Blink == (struct _LIST_ENTRY *)v34) )
    {
      v36 = 0;
      while ( 1 )
      {
        v68 = v36;
        if ( (unsigned int)v36 >= v31 )
          break;
        v37 = v66[v36];
        if ( v37 != 2 || (*(_BYTE *)DeviceRoutine & 2) != 0 && !HIBYTE(pMiniRedirectorDeviceObject->DeviceQueue.Lock) )
        {
          ServerTransport = (SOCKADDR_IN *)SmbMmAllocateServerTransport(
                                             2,
                                             pMiniRedirectorDeviceObject->DeviceObject.CurrentIrp);
          v39 = 264LL * v30;
          *(_QWORD *)((char *)v63 + v39 + 216) = ServerTransport;
          if ( ServerTransport )
          {
            RxCepInitializeVcEndpoint(
              (_DWORD)ServerTransport,
              (_DWORD)v35,
              pMiniRedirectorDeviceObject->DeviceObject.SecurityDescriptor,
              (_DWORD)DeviceExtension,
              v75);
            *(_DWORD *)&ServerTransport[20].sin_family = v37;
            v40 = &ServerTransport[26].sin_zero[4];
            v41 = v65;
            *(SOCKADDR_IN *)((char *)ServerTransport + 428) = *(SOCKADDR_IN *)v65;
            *(SOCKADDR_IN *)((char *)ServerTransport + 440) = *(SOCKADDR_IN *)((char *)v65 + 12);
            SectorSize = pMiniRedirectorDeviceObject->DeviceObject.SectorSize;
            if ( (_WORD)SectorSize )
            {
              if ( (unsigned int)SectorSize >= 0x23 )
                v43 = sockaddr_size;
              else
                v43 = &sockaddr_size[SectorSize];
              memmove(&ServerTransport[25], &pMiniRedirectorDeviceObject->SectorSize, *v43);
              *(_QWORD *)((char *)v63 + v39 + 232) = ServerTransport + 25;
              v40 = &ServerTransport[26].sin_zero[4];
              v41 = v65;
              v44 = v62;
            }
            else
            {
              v44 = v62;
              if ( (*v62 & 1) != 0 || (*v62 & 2) != 0 && v37 == 2 )
              {
                ServerTransport[25] = BestSourceAddress.Ipv4;
                *(SOCKADDR_IN *)((char *)ServerTransport + 412) = *(SOCKADDR_IN *)(&BestSourceAddress.si_family + 6);
                *(_QWORD *)((char *)v63 + v39 + 232) = ServerTransport + 25;
              }
            }
            if ( (*v44 & 1) == 0 )
              ServerTransport->sin_addr.S_un.S_addr |= 2u;
            if ( *v41 == 23 )
              ServerTransport[20].sin_addr.S_un.S_un_b.s_b2 = 1;
            RxCeDetermineAndSetConnectionPortForTransportType(pMiniRedirectorDeviceObject, ServerTransport);
            *(_DWORD *)((char *)v63 + v39 + 224) = v67[12];
            *(_QWORD *)((char *)v63 + v39 + 240) = v40;
            *(_QWORD *)((char *)v63 + v39 + 248) = 0;
            *(_QWORD *)((char *)v63 + v39 + 256) = 0;
            *(_DWORD *)((char *)v63 + v39 + 208) = v30;
            *(_QWORD *)((char *)v63 + v39 + 8) = pMiniRedirectorDeviceObject;
            *(_QWORD *)((char *)v63 + v39 + 16) = 259;
            ++v30;
            DeviceRoutine = (PDRIVER_CONTROL)v62;
            if ( v72 || v37 == 2 && (*(_BYTE *)v62 & 2) != 0 )
            {
              v31 = v61;
              v35 = v67;
              break;
            }
            v35 = v67;
          }
          else
          {
            DeviceRoutine = (PDRIVER_CONTROL)v62;
          }
        }
        v36 = (unsigned int)(v36 + 1);
        v31 = v61;
      }
      SmbCepDereferenceTransport(v35);
      Blink = v72;
      v32 = v59 + 1;
      v33 = v65 + 8;
    }
    else
    {
      SmbCepDereferenceTransport((PVOID)v34);
LABEL_83:
      v32 = v59 + 1;
      v33 += 64;
    }
  }
  if ( !v58 )
    v30 += RxCepBuildConnectCalloutsForTdi((char *)v63 + 264 * v30, v60 - v30, v30, pMiniRedirectorDeviceObject);
  v45 = RxCepBuildConnectCalloutsForVmbus((char *)v63 + 264 * v30, v60 - v30, v30, pMiniRedirectorDeviceObject) + v30;
  if ( v45 )
  {
    v46 = 0;
    for ( i = 0; ; *(_QWORD *)v49 = (char *)v63 + 264 * i )
    {
      v48 = v45 - 1;
      if ( i >= (unsigned int)v48 )
        break;
      v49 = (char *)v63 + 264 * i;
      *((_QWORD *)v49 + 4) = v49 + 24;
      *((_QWORD *)v49 + 3) = v49 + 24;
      *((_DWORD *)v49 + 14) = 826898514;
      ++i;
    }
    v50 = 264 * v48;
    v51 = (_QWORD *)((char *)v63 + 264 * v48 + 24);
    v51[1] = v51;
    *v51 = v51;
    *(_DWORD *)((char *)v63 + v50 + 56) = 826898514;
    *(_QWORD *)((char *)v63 + v50) = 0;
    v52 = v69;
    *(_DWORD *)&pMiniRedirectorDeviceObject->DeviceQueue.Type = v69;
    HIDWORD(pMiniRedirectorDeviceObject->DeviceQueue.DeviceListHead.Blink) = v45;
    *(struct _LIST_ENTRY **)((char *)&pMiniRedirectorDeviceObject->DeviceQueue.DeviceListHead.Flink + 4) = 0;
    *(_DWORD *)(&pMiniRedirectorDeviceObject->DeviceQueue.Size + 1) = v45;
    LODWORD(pMiniRedirectorDeviceObject->DeviceQueue.DeviceListHead.Flink) = 0;
    pMiniRedirectorDeviceObject->DeviceObject.Queue.Wcb.DeviceObject = RxCeInitiateConnectRequest;
    pMiniRedirectorDeviceObject->DeviceObject.Queue.Wcb.CurrentIrp = RxCeCompleteConnectRequest;
    BYTE4(pMiniRedirectorDeviceObject->DeviceQueue.Lock) = 0;
    BYTE5(pMiniRedirectorDeviceObject->DeviceQueue.Lock) = 0;
    while ( v46 < 8 )
    {
      v53 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&pMiniRedirectorDeviceObject->DeviceObject.DriverObject);
      if ( BYTE4(pMiniRedirectorDeviceObject->DeviceQueue.Lock) )
      {
        v54 = v45;
      }
      else
      {
        v54 = (unsigned int)pMiniRedirectorDeviceObject->DeviceQueue.DeviceListHead.Flink;
        if ( v54 < v45 )
          LODWORD(pMiniRedirectorDeviceObject->DeviceQueue.DeviceListHead.Flink) = v54 + 1;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)&pMiniRedirectorDeviceObject->DeviceObject.DriverObject, v53);
      if ( v54 >= v45 )
        break;
      if ( v54 == 1 && !v52 )
      {
        for ( j = 0; ; ++j )
        {
          v70 = j;
          if ( j >= 10 || BYTE4(pMiniRedirectorDeviceObject->DeviceQueue.Lock) )
            break;
          KeDelayExecutionThread(0, 0, (PLARGE_INTEGER)&Interval);
        }
      }
      RxCeReferenceConnectionCallOutContext(pMiniRedirectorDeviceObject);
      ((void (__fastcall *)(char *))pMiniRedirectorDeviceObject->DeviceObject.Queue.Wcb.DeviceObject)((char *)v63 + 264 * v54);
      ++v46;
    }
    v20 = 259;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v20 = -1073741252;
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_2f623439b0cb30f148aad6ad1abf961a_Traceguids, 3221226044LL);
  }
  else
  {
    v20 = -1073741252;
  }
LABEL_110:
  RxCeDereferenceConnectionCallOutContext(pMiniRedirectorDeviceObject);
LABEL_111:
  v56 = v73;
  if ( v73 )
  {
    PsDetachSiloFromCurrentThread(v74);
    RxDereferenceSiloAndReleaseRundown(v56);
  }
  if ( v20 != 259 )
  {
    LODWORD(pMiniRedirectorDeviceObject->AttachedDevice) = v20;
    HIDWORD(pMiniRedirectorDeviceObject->AttachedDevice) = 0;
    LODWORD(pMiniRedirectorDeviceObject->NextDevice) = 2;
    RxCeInitiateConnection(pMiniRedirectorDeviceObject);
  }
  return 259;
}

```

## disassembly

```asm
0x14001db00  mov     [rsp+arg_8], rbx
0x14001db05  mov     [rsp+arg_10], rsi
0x14001db0a  push    rdi
0x14001db0b  push    r12
0x14001db0d  push    r13
0x14001db0f  push    r14
0x14001db11  push    r15
0x14001db13  sub     rsp, 0F0h
0x14001db1a  mov     rax, cs:__security_cookie
0x14001db21  xor     rax, rsp
0x14001db24  mov     [rsp+118h+var_30], rax
0x14001db2c  mov     rsi, rcx
0x14001db2f  xor     edi, edi
0x14001db31  mov     eax, edi
0x14001db33  cmp     cs:MRxSmbObeyBindingOrder, dil
0x14001db3a  setnz   al
0x14001db3d  mov     [rsp+118h+var_8C], eax
0x14001db44  mov     rax, [rcx+40h]
0x14001db48  mov     [rsp+118h+var_58], rax
0x14001db50  mov     rax, [rcx+48h]
0x14001db54  mov     [rsp+118h+var_60], rax
0x14001db5c  mov     rbx, [rcx+50h]
0x14001db60  mov     r14, [rcx+58h]
0x14001db64  mov     [rsp+118h+var_78], r14
0x14001db6c  movzx   eax, byte ptr [rcx+0BEh]
0x14001db73  mov     [rsp+118h+var_D8], al
0x14001db77  mov     [rsp+118h+var_68], rdi
0x14001db7f  mov     rcx, [rcx+0C8h]
0x14001db86  test    rcx, rcx
0x14001db89  jz      short loc_14001DC08
0x14001db8b  call    cs:__imp_RxReferenceSiloAndAcquireRundown
0x14001db92  nop     dword ptr [rax+rax+00h]
0x14001db97  mov     [rsp+118h+var_70], rax
0x14001db9f  test    rax, rax
0x14001dba2  jz      short loc_14001DBFE
0x14001dba4  mov     rcx, [rax+28h]
0x14001dba8  call    cs:__imp_PsAttachSiloToCurrentThread
0x14001dbaf  nop     dword ptr [rax+rax+00h]
0x14001dbb4  mov     [rsp+118h+var_68], rax
0x14001dbbc  mov     r8, [rsi+20h]
0x14001dbc0  test    dword ptr [r8+150h], 2000h
0x14001dbcb  jz      short loc_14001DBEF
0x14001dbcd  mov     rdx, [rsi+0C8h]
0x14001dbd4  mov     ecx, [r8+514h]
0x14001dbdb  cmp     ecx, [rdx+4]
0x14001dbde  jnb     short loc_14001DBEF
0x14001dbe0  mov     rax, [rdx+rcx*8+30h]
0x14001dbe5  mov     [rsp+118h+var_80], rax
0x14001dbed  jmp     short loc_14001DBF7
0x14001dbef  mov     [rsp+118h+var_80], rdi
0x14001dbf7  movzx   eax, [rsp+118h+var_D8]
0x14001dbfc  jmp     short loc_14001DC18
0x14001dbfe  mov     ebx, 0C0000120h
0x14001dc03  jmp     loc_14001E304
0x14001dc08  mov     [rsp+118h+var_80], rdi
0x14001dc10  mov     [rsp+118h+var_70], rdi
0x14001dc18  mov     r12d, edi
0x14001dc1b  mov     [rsp+118h+var_B8], edi
0x14001dc1f  mov     r15, [rsi+68h]
0x14001dc23  mov     [rsp+118h+var_C8], r15
0x14001dc28  test    r15, r15
0x14001dc2b  jz      short loc_14001DC37
0x14001dc2d  movzx   r12d, word ptr [r15+2]
0x14001dc32  mov     [rsp+118h+var_B8], r12d
0x14001dc37  cmp     [rsi+0C0h], dil
0x14001dc3e  jz      short loc_14001DC4B
0x14001dc40  test    r15, r15
0x14001dc43  jz      short loc_14001DC58
0x14001dc45  test    byte ptr [r15], 4
0x14001dc49  jz      short loc_14001DC53
0x14001dc4b  mov     al, 1
0x14001dc4d  mov     [rsp+118h+var_D8], al
0x14001dc51  jmp     short loc_14001DC58
0x14001dc53  movzx   eax, [rsp+118h+var_D8]
0x14001dc58  test    r14, r14
0x14001dc5b  jnz     short loc_14001DC6F
0x14001dc5d  test    al, al
0x14001dc5f  jz      short loc_14001DC66
0x14001dc61  test    r12d, r12d
0x14001dc64  jnz     short loc_14001DC6F
0x14001dc66  mov     r13d, [rbx+8]
0x14001dc6a  add     r13d, r12d
0x14001dc6d  jmp     short loc_14001DC72
0x14001dc6f  mov     r13d, r12d
0x14001dc72  mov     [rsp+118h+var_D0], r13d
0x14001dc77  mov     rcx, rsi
0x14001dc7a  call    HowToUseWskAndQuic
0x14001dc7f  mov     ebx, eax
0x14001dc81  cmp     byte ptr cs:word_14007D202, dil
0x14001dc88  jz      short loc_14001DCA0
0x14001dc8a  call    MRxSmbIsRdmaRundownActive
0x14001dc8f  test    al, al
0x14001dc91  jnz     short loc_14001DCA0
0x14001dc93  mov     [rsp+118h+var_A8], 2
0x14001dc9b  mov     edi, 1
0x14001dca0  cmp     ebx, 1
0x14001dca3  jz      loc_14001DD6C
0x14001dca9  test    ebx, ebx
0x14001dcab  jz      loc_14001DD4E
0x14001dcb1  sub     ebx, 2
0x14001dcb4  jz      loc_14001DD42
0x14001dcba  cmp     ebx, 1
0x14001dcbd  jz      short loc_14001DD24
0x14001dcbf  test    r15, r15
0x14001dcc2  jz      short loc_14001DCDE
0x14001dcc4  lea     rdx, [r15+88h]
0x14001dccb  mov     ecx, 1Ch
0x14001dcd0  mov     eax, 10h
0x14001dcd5  cmp     word ptr [rdx], 2
0x14001dcd9  cmovz   ecx, eax
0x14001dcdc  jmp     short loc_14001DCE2
0x14001dcde  xor     ecx, ecx
0x14001dce0  xor     edx, edx
0x14001dce2  test    cs:byte_1400712C2, 2
0x14001dce9  jz      short loc_14001DD1A
0x14001dceb  movzx   r9d, word ptr [rsi+30h]
0x14001dcf0  shr     r9w, 1
0x14001dcf4  mov     [rsp+118h+var_E0], rdx
0x14001dcf9  mov     [rsp+118h+var_E8], ecx
0x14001dcfd  mov     [rsp+118h+var_F0], 4
0x14001dd05  mov     rax, [rsi+38h]
0x14001dd09  mov     [rsp+118h+var_F8], rax
0x14001dd0e  lea     rdx, RequestedTransportDisabled
0x14001dd15  call    McTemplateK0hzr0qqbr3_EtwWriteTransfer
0x14001dd1a  mov     ebx, 0C0000241h
0x14001dd1f  jmp     loc_14001E304
0x14001dd24  mov     eax, edi
0x14001dd26  mov     [rsp+rax*4+118h+var_A8], 4
0x14001dd2e  inc     edi
0x14001dd30  mov     [rsp+rdi*4+118h+var_A8], 1
0x14001dd38  add     r13d, r12d
0x14001dd3b  mov     [rsp+118h+var_D0], r13d
0x14001dd40  jmp     short loc_14001DD76
0x14001dd42  mov     eax, edi
0x14001dd44  mov     [rsp+rax*4+118h+var_A8], 4
0x14001dd4c  jmp     short loc_14001DD76
0x14001dd4e  mov     eax, edi
0x14001dd50  mov     [rsp+rax*4+118h+var_A8], 1
0x14001dd58  inc     edi
0x14001dd5a  mov     [rsp+rdi*4+118h+var_A8], 4
0x14001dd62  add     r13d, r12d
0x14001dd65  mov     [rsp+118h+var_D0], r13d
0x14001dd6a  jmp     short loc_14001DD76
0x14001dd6c  mov     eax, edi
0x14001dd6e  mov     [rsp+rax*4+118h+var_A8], 1
0x14001dd76  mov     eax, r13d
0x14001dd79  imul    rdx, rax, 108h
0x14001dd80  mov     ecx, 40h ; '@'
0x14001dd85  mov     r8d, 62507852h
0x14001dd8b  call    cs:__imp_ExAllocatePool2
0x14001dd92  nop     dword ptr [rax+rax+00h]
0x14001dd97  mov     [rsp+118h+var_C0], rax
0x14001dd9c  test    rax, rax
0x14001dd9f  jnz     short loc_14001DDAB
0x14001dda1  mov     ebx, 0C000009Ah
0x14001dda6  jmp     loc_14001E304
0x14001ddab  mov     [rsi+28h], rax
0x14001ddaf  mov     rcx, rsi
0x14001ddb2  call    RxCeReferenceConnectionCallOutContext
0x14001ddb7  mov     rcx, [rsi+20h]; RxDeviceObject
0x14001ddbb  call    cs:__imp_RxRegisterAsynchronousRequest
0x14001ddc2  nop     dword ptr [rax+rax+00h]
0x14001ddc7  mov     ebx, eax
0x14001ddc9  test    eax, eax
0x14001ddcb  jnz     loc_14001E2FC
0x14001ddd1  xor     r13d, r13d
0x14001ddd4  lea     r12d, [rdi+1]
0x14001ddd8  mov     [rsp+118h+var_CC], r12d
0x14001dddd  or      dword ptr [rsi+1B0h], 1
0x14001dde4  mov     [rsp+118h+var_B0], r13
0x14001dde9  xorps   xmm0, xmm0
0x14001ddec  xor     eax, eax
0x14001ddee  movups  xmmword ptr [rsp+118h+BestSourceAddress], xmm0
0x14001ddf6  movups  xmmword ptr [rsp+118h+BestSourceAddress+0Ch], xmm0
0x14001ddfe  lea     rbx, [r15+88h]
0x14001de05  mov     [rsp+118h+var_D4], eax
0x14001de09  mov     [rsp+118h+var_B0], rbx
0x14001de0e  cmp     eax, [rsp+118h+var_B8]
0x14001de12  jnb     loc_14001E0CC
0x14001de18  mov     rax, [rsi+20h]
0x14001de1c  mov     [rsp+118h+var_F8], rax; __int64
0x14001de21  mov     r9, [rsp+118h+var_80]
0x14001de29  mov     r8, rbx
0x14001de2c  mov     rdx, r15
0x14001de2f  lea     rcx, [rsp+118h+BestSourceAddress]; BestSourceAddress
0x14001de37  call    RxCepSelectTransportForAddress
0x14001de3c  mov     rdi, rax
0x14001de3f  mov     [rsp+118h+var_98], rax
0x14001de47  test    rax, rax
0x14001de4a  jnz     short loc_14001DE51
0x14001de4c  jmp     loc_14001E0BD
0x14001de51  cmp     dword ptr [rax+38h], 1
0x14001de55  jnz     loc_14001E0B5
0x14001de5b  movzx   eax, word ptr [rbx]
0x14001de5e  cmp     ax, 2
0x14001de62  jnz     short loc_14001DE6B
0x14001de64  cmp     word ptr [rdi+40h], 0
0x14001de69  jnz     short loc_14001DE80
0x14001de6b  cmp     ax, 17h
0x14001de6f  jnz     loc_14001E0B5
0x14001de75  cmp     word ptr [rdi+42h], 0
0x14001de7a  jz      loc_14001E0B5
0x14001de80  test    r14, r14
0x14001de83  jz      short loc_14001DE97
0x14001de85  cmp     r14, rdi
0x14001de88  jz      short loc_14001DE97
0x14001de8a  mov     rcx, rdi; P
0x14001de8d  call    SmbCepDereferenceTransport
0x14001de92  jmp     loc_14001E0BD
0x14001de97  xor     r14d, r14d
0x14001de9a  mov     [rsp+118h+var_90], r14d
0x14001dea2  cmp     r14d, r12d
0x14001dea5  jnb     loc_14001E091
0x14001deab  mov     r12d, [rsp+r14*4+118h+var_A8]
0x14001deb0  cmp     r12d, 2
0x14001deb4  jnz     short loc_14001DEC9
0x14001deb6  test    [r15], r12b
0x14001deb9  jz      short loc_14001DEC4
0x14001debb  cmp     byte ptr [rsi+0BFh], 0
0x14001dec2  jz      short loc_14001DEC9
0x14001dec4  jmp     loc_14001E077
0x14001dec9  mov     rdx, [rsi+20h]
0x14001decd  mov     ecx, 2
0x14001ded2  call    SmbMmAllocateServerTransport
0x14001ded7  mov     r15, rax
0x14001deda  mov     ecx, r13d
0x14001dedd  imul    rbx, rcx, 108h
0x14001dee4  mov     rax, [rsp+118h+var_C0]
0x14001dee9  mov     [rbx+rax+0D8h], r15
0x14001def1  test    r15, r15
0x14001def4  jnz     short loc_14001DF00
0x14001def6  mov     r15, [rsp+118h+var_C8]
0x14001defb  jmp     loc_14001E077
0x14001df00  mov     rax, [rsp+118h+var_60]
0x14001df08  mov     [rsp+118h+var_F8], rax
0x14001df0d  mov     r9, [rsp+118h+var_58]
0x14001df15  mov     r8, [rsi+110h]
0x14001df1c  mov     rdx, rdi
0x14001df1f  mov     rcx, r15
0x14001df22  call    RxCepInitializeVcEndpoint
0x14001df27  mov     [r15+140h], r12d
0x14001df2e  lea     rdi, [r15+1ACh]
0x14001df35  mov     rcx, [rsp+118h+var_B0]
0x14001df3a  movups  xmm0, xmmword ptr [rcx]
0x14001df3d  movups  xmmword ptr [rdi], xmm0
0x14001df40  movups  xmm1, xmmword ptr [rcx+0Ch]
0x14001df44  movups  xmmword ptr [rdi+0Ch], xmm1
0x14001df48  lea     rdx, [rsi+130h]; Src
0x14001df4f  movzx   eax, word ptr [rdx]
0x14001df52  test    ax, ax
0x14001df55  jz      short loc_14001DFA2
0x14001df57  cmp     eax, 23h ; '#'
0x14001df5a  jnb     short loc_14001DF68
0x14001df5c  lea     rcx, sockaddr_size
0x14001df63  add     rax, rcx
0x14001df66  jmp     short loc_14001DF6F
0x14001df68  lea     rax, sockaddr_size
0x14001df6f  lea     rdi, [r15+190h]
0x14001df76  movzx   r8d, byte ptr [rax]; Size
0x14001df7a  mov     rcx, rdi; void *
0x14001df7d  call    memmove
0x14001df82  mov     rax, [rsp+118h+var_C0]
0x14001df87  mov     [rbx+rax+0E8h], rdi
0x14001df8f  lea     rdi, [r15+1ACh]
0x14001df96  mov     rcx, [rsp+118h+var_B0]
0x14001df9b  mov     rdx, [rsp+118h+var_C8]
0x14001dfa0  jmp     short loc_14001DFE3
0x14001dfa2  mov     rdx, [rsp+118h+var_C8]
0x14001dfa7  movzx   eax, word ptr [rdx]
0x14001dfaa  test    al, 1
0x14001dfac  jnz     short loc_14001DFB8
0x14001dfae  test    al, 2
0x14001dfb0  jz      short loc_14001DFE3
0x14001dfb2  cmp     r12d, 2
0x14001dfb6  jnz     short loc_14001DFE3
0x14001dfb8  lea     rax, [r15+190h]
0x14001dfbf  movups  xmm0, xmmword ptr [rsp+118h+BestSourceAddress]
0x14001dfc7  movups  xmmword ptr [rax], xmm0
0x14001dfca  movups  xmm1, xmmword ptr [rsp+118h+BestSourceAddress+0Ch]
0x14001dfd2  movups  xmmword ptr [rax+0Ch], xmm1
0x14001dfd6  mov     r8, [rsp+118h+var_C0]
0x14001dfdb  mov     [rbx+r8+0E8h], rax
0x14001dfe3  test    byte ptr [rdx], 1
0x14001dfe6  jnz     short loc_14001DFED
0x14001dfe8  or      dword ptr [r15+4], 2
0x14001dfed  cmp     word ptr [rcx], 17h
0x14001dff1  jnz     short loc_14001DFFB
0x14001dff3  mov     byte ptr [r15+145h], 1
0x14001dffb  mov     rdx, r15
0x14001dffe  mov     rcx, rsi
0x14001e001  call    RxCeDetermineAndSetConnectionPortForTransportType
0x14001e006  mov     rcx, [rsp+118h+var_98]
0x14001e00e  mov     eax, [rcx+30h]
0x14001e011  mov     rcx, [rsp+118h+var_C0]
0x14001e016  mov     [rbx+rcx+0E0h], eax
0x14001e01d  mov     [rbx+rcx+0F0h], rdi
0x14001e025  xor     eax, eax
0x14001e027  mov     [rbx+rcx+0F8h], rax
0x14001e02f  mov     [rbx+rcx+100h], rax
0x14001e037  mov     [rbx+rcx+0D0h], r13d
  ... truncated ...
```
