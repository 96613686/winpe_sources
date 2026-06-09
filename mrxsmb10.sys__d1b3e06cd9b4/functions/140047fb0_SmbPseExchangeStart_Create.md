# SmbPseExchangeStart_Create

- ea: `0x140047fb0`
- end: `0x140048b2a`
- name: `SmbPseExchangeStart_Create`
- size: `2938`
- prototype: `__int64 __fastcall(char *pContext, __int64)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x14000b6f0`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000e52c`
- `0x14003608c`
- `0x14003630c`
- `0x14003652c`
- `0x14003a5f0`
- `0x140045d50`
- `0x140046a50`
- `0x140047dc0`
- `0x140047fb0`
- `0x140048b30`
- `0x1400495b4`
- `0x140049870`
- `0x14004a4a4`
- `0x14004f920`
- `0x1400507a0`
- `0x14005289c`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcessId` at `0x1400482e4`
- `ntoskrnl!IoGetRequestorProcessId` at `0x1400482e4`
- `ntoskrnl!FsRtlIsFatDbcsLegal` at `0x140048207`
- `ntoskrnl!FsRtlIsFatDbcsLegal` at `0x140048207`
- `ntoskrnl!FsRtlIsHpfsDbcsLegal` at `0x140048231`
- `ntoskrnl!FsRtlIsHpfsDbcsLegal` at `0x140048231`
- `ntoskrnl!ExLocalTimeToSystemTime` at `0x1400484f6`
- `ntoskrnl!ExLocalTimeToSystemTime` at `0x1400484f6`
- `ntoskrnl!RtlSecondsSince1970ToTime` at `0x1400484e2`
- `ntoskrnl!RtlSecondsSince1970ToTime` at `0x1400484e2`
- `ntoskrnl!RtlFreeOemString` at `0x14004821b`
- `ntoskrnl!RtlFreeOemString` at `0x14004823f`
- `ntoskrnl!RtlFreeOemString` at `0x14004821b`
- `ntoskrnl!RtlFreeOemString` at `0x14004823f`
- `ntoskrnl!RtlUnicodeStringToOemString` at `0x1400481d5`
- `ntoskrnl!RtlUnicodeStringToOemString` at `0x1400481d5`
- `ntoskrnl!ExAllocatePool2` at `0x140048558`
- `ntoskrnl!ExAllocatePool2` at `0x1400486cb`
- `ntoskrnl!ExAllocatePool2` at `0x140048558`
- `ntoskrnl!ExAllocatePool2` at `0x1400486cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048683`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048800`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048ab1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048683`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048800`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048ab1`
- `rdbss!RxFinishFcbInitialization` at `0x1400488da`
- `rdbss!RxFinishFcbInitialization` at `0x1400488da`
- `rdbss!RxInitializeContext` at `0x140048582`
- `rdbss!RxInitializeContext` at `0x1400486fc`
- `rdbss!RxInitializeContext` at `0x140048582`
- `rdbss!RxInitializeContext` at `0x1400486fc`

## pseudocode

```c
__int64 __fastcall SmbPseExchangeStart_Create(char *pContext, __int64 a2)
{
  struct _MRX_FCB_ *v2; // rax
  char *v3; // r12
  __int64 v6; // r14
  char v7; // r13
  int v8; // r15d
  NTSTATUS FileInformation; // edi
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v13; // r9
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  int v16; // eax
  PERESOURCE *p_Resource; // rdx
  ULONGLONG v18; // rcx
  int v20; // r15d
  BOOLEAN IsHpfsDbcsLegal; // al
  _QWORD *v22; // rdi
  IRP *v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rcx
  int v29; // edx
  int v30; // edi
  _QWORD *v31; // r13
  _QWORD *v32; // r12
  int v33; // ecx
  __int64 v34; // r15
  __int64 v35; // r15
  struct _RX_CONTEXT *Pool2; // rax
  struct _RX_CONTEXT *v37; // r15
  PVOID *p_EaBuffer; // rcx
  __int64 v39; // rdx
  __int128 *v40; // rax
  __int128 v41; // xmm0
  bool v42; // al
  struct _RX_CONTEXT *v43; // rax
  struct _RX_CONTEXT *v44; // r15
  _DWORD *v45; // r12
  PVOID *v46; // rcx
  __int64 v47; // rdx
  struct _MRX_SRV_OPEN_ *v48; // rax
  __int128 *v49; // rax
  __int128 v50; // xmm0
  char v51; // cl
  RX_FILE_TYPE v52; // edx
  int v53; // eax
  PMRX_FCB v54; // r15
  int Blink_high; // eax
  NTSTATUS v56; // eax
  NTSTATUS FileInformationFromPseudoOpen; // eax
  char v58; // r15
  unsigned int v59; // eax
  __int64 v60; // [rsp+30h] [rbp-69h]
  struct _STRING DestinationString; // [rsp+40h] [rbp-59h] BYREF
  ANSI_STRING DbcsName; // [rsp+50h] [rbp-49h] BYREF
  _FCB_INIT_PACKET InitPacket; // [rsp+60h] [rbp-39h] BYREF
  char *v64; // [rsp+A8h] [rbp+Fh]
  int v65; // [rsp+100h] [rbp+67h]
  ULONGLONG ActualAllocationLength; // [rsp+108h] [rbp+6Fh]
  PMRX_FCB Fcb; // [rsp+110h] [rbp+77h]
  union _LARGE_INTEGER Time; // [rsp+118h] [rbp+7Fh] BYREF

  v2 = *(struct _MRX_FCB_ **)(a2 + 56);
  v3 = pContext + 888;
  Fcb = v2;
  if ( v2 )
    ActualAllocationLength = v2->ActualAllocationLength;
  else
    ActualAllocationLength = 0;
  v6 = *(_QWORD *)(a2 + 72);
  if ( v6 )
    v6 = *(_QWORD *)(v6 + 48);
  v7 = pContext[564];
  v60 = *(_QWORD *)(*((_QWORD *)pContext + 11) + 104LL);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
  Time.QuadPart = *((_QWORD *)pContext + 10) + 400LL;
  v8 = *(_DWORD *)(Time.QuadPart + 20);
  v65 = v8;
  FileInformation = MRxSmbSetInitialSMB(v3);
  if ( FileInformation )
    goto LABEL_30;
  v10 = *((_QWORD *)pContext + 11);
  if ( v10 )
    v11 = *(_QWORD *)(v10 + 96);
  else
    v11 = 0;
  v12 = *(_QWORD *)(a2 + 672);
  if ( v12 )
  {
    if ( ((*(_DWORD *)(v12 + 8) - 2) & 0xFFFFFFFD) == 0 )
    {
      v13 = *((_QWORD *)pContext + 10);
      if ( (*(_BYTE *)(v13 + 672) & 8) == 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
        {
          goto LABEL_20;
        }
        v15 = 37;
LABEL_19:
        WPP_SF_qq(v14->AttachedDevice, v15, WPP_d95790c14120305e97e490eb33b089fe_Traceguids, v13, a2);
LABEL_20:
        FileInformation = -1073741311;
LABEL_30:
        v18 = ActualAllocationLength;
        goto LABEL_31;
      }
    }
    if ( (*(_DWORD *)(v12 + 12) & 8) != 0 && !*(_BYTE *)(v11 + 381) )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
        goto LABEL_20;
      }
      v15 = 38;
      v13 = v11;
      goto LABEL_19;
    }
  }
  v16 = SmbCeSetupAlternateSPNForSession(v11, *(unsigned __int16 **)(a2 + 680));
  FileInformation = v16;
  if ( v16 == -1073740964 )
  {
    FileInformation = -1069481983;
LABEL_29:
    *((_DWORD *)pContext + 10) = FileInformation;
    goto LABEL_30;
  }
  if ( v16 < 0 )
    goto LABEL_29;
  v20 = v8 & 0x40000;
  if ( !v20 )
  {
    p_Resource = &Fcb[2].Header.Resource;
    DestinationString = 0;
    if ( LOWORD(Fcb[2].Header.Resource) )
    {
      FileInformation = RtlUnicodeStringToOemString(&DestinationString, (PCUNICODE_STRING)p_Resource, 1u);
      if ( FileInformation < 0 )
        goto LABEL_30;
      DbcsName = DestinationString;
      if ( (v65 & 0x20) != 0 )
        IsHpfsDbcsLegal = FsRtlIsHpfsDbcsLegal(&DbcsName, 0, 1u, 1u);
      else
        IsHpfsDbcsLegal = FsRtlIsFatDbcsLegal(&DbcsName, 0, 1u, 1u);
      if ( !IsHpfsDbcsLegal )
      {
        RtlFreeOemString(&DestinationString);
        FileInformation = -1073741773;
        goto LABEL_30;
      }
      RtlFreeOemString(&DestinationString);
    }
  }
  if ( v3[120] != -1 )
  {
    FileInformation = SmbPseOrdinaryExchange(pContext);
    if ( FileInformation )
      goto LABEL_30;
    SmbCeUpdateSessionEntryAndVNetRootContext(pContext);
    *((_DWORD *)pContext + 18) &= ~0x10u;
    FileInformation = MRxSmbSetInitialSMB(v3);
    if ( FileInformation )
      goto LABEL_30;
  }
  if ( v7 )
    goto LABEL_30;
  v22 = pContext + 556;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
  if ( *(int *)(a2 + 120) < 0 )
  {
    v25 = *(_QWORD *)(a2 + 72);
    if ( v25 )
      v26 = *(_QWORD *)(v25 + 48);
    else
      v26 = 0;
    *(_QWORD *)(a2 + 544) = 0;
    *v22 = *(_QWORD *)(*(_QWORD *)(v26 + 16) + 92LL);
  }
  else
  {
    *(_DWORD *)(a2 + 540) &= 0xFFFFFFCF;
    v23 = *(IRP **)(a2 + 40);
    if ( v23 )
      *(_DWORD *)v22 = IoGetRequestorProcessId(v23);
    pContext[560] = 0;
    v24 = *(_QWORD *)(a2 + 544);
    if ( v24 && *(_QWORD *)v24 )
    {
      LOBYTE(p_Resource) = 0;
      if ( *(_BYTE *)(*(_QWORD *)v24 + 8LL) == 1 )
      {
        pContext[560] = 1;
        LOBYTE(p_Resource) = 1;
      }
      if ( *(_BYTE *)(**(_QWORD **)(a2 + 544) + 9LL) )
      {
        LOBYTE(p_Resource) = (unsigned __int8)p_Resource | 2;
        pContext[560] = (char)p_Resource;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
  if ( *(_BYTE *)(*(_QWORD *)(a2 + 648) + 77LL) == 3 )
  {
    FileInformation = MRxSmbBuildOpenPrintFile(v3, p_Resource, 0);
    if ( !FileInformation )
      FileInformation = SmbPseOrdinaryExchange(pContext);
    goto LABEL_30;
  }
  if ( v20 )
  {
    v27 = *(_QWORD *)(a2 + 544);
    if ( v27 && (v28 = *(_QWORD *)(v27 + 8)) != 0 && *(_QWORD *)(v28 + 64)
      || !MRxSmbDeferredOpensEnabled
      || (*(_DWORD *)(a2 + 120) & 0xA0000000) != 0
      || *(_BYTE *)(*(_QWORD *)&Fcb->UncleanCount + 77LL)
      || *(_DWORD *)(a2 + 536) != 1
      || (v29 = *(_DWORD *)(a2 + 540), (v29 & 0x4000) != 0)
      || (*(_DWORD *)(a2 + 512) & 0xFFEFFF7F) != 0 && (v29 & 1) == 0 )
    {
      FileInformation = MRxSmbBuildNtCreateAndX(v3, pContext + 556, 0);
      if ( FileInformation )
        goto LABEL_30;
      FileInformation = SmbPseOrdinaryExchange(pContext);
      if ( FileInformation )
        goto LABEL_30;
      if ( !*(_QWORD *)(a2 + 64) )
      {
        FileInformation = -1073741629;
        goto LABEL_30;
      }
      if ( *(_DWORD *)(a2 + 536) == 1 )
        MRxSmbAdjustReturnedCreateAction(a2);
      MRxSmbInvalidateFileNotFoundCache(a2);
      v54 = Fcb;
      if ( Fcb[1].Header.FilterContexts.Blink || (v65 & 0x1000000) == 0 || *(_BYTE *)(v60 + 106) != 2 )
        goto LABEL_30;
      FileInformationFromPseudoOpen = MRxSmbQueryFileInformationFromPseudoOpen(pContext, a2, 6);
      v18 = ActualAllocationLength;
      FileInformation = FileInformationFromPseudoOpen;
      if ( FileInformationFromPseudoOpen )
      {
LABEL_121:
        FileInformation = 0;
        goto LABEL_31;
      }
    }
    else
    {
      if ( (v29 & 1) != 0 || !*(_WORD *)(*(_QWORD *)(a2 + 56) + 360LL) )
        v30 = 1;
      else
        v30 = 2;
      *((_QWORD *)pContext + 61) = 0;
      v31 = pContext + 472;
      *((_QWORD *)pContext + 62) = 0;
      v32 = pContext + 512;
      *(_QWORD *)(pContext + 508) = 0;
      *(_QWORD *)(pContext + 516) = 0;
      *(_QWORD *)(pContext + 524) = 0;
      *(_QWORD *)(pContext + 532) = 0;
      *((_DWORD *)pContext + 135) = 0;
      if ( v30 == 1 )
        v33 = 16;
      else
        v33 = 128;
      *((_DWORD *)pContext + 126) = v33;
      *((_DWORD *)pContext + 132) = 1;
      *v31 = 0;
      *((_QWORD *)pContext + 60) = 0;
      v34 = *((_QWORD *)pContext + 10);
      Time.QuadPart = 0;
      RtlSecondsSince1970ToTime(0, &Time);
      ExLocalTimeToSystemTime(&Time, (PLARGE_INTEGER)pContext + 61);
      v35 = v34 + 400;
      if ( v35 )
        *((_QWORD *)pContext + 61) += *(_QWORD *)(v35 + 40);
      *((_QWORD *)pContext + 62) = 0;
      *v32 = 0;
      *((_QWORD *)pContext + 65) = 0;
      pContext[533] = (*((_DWORD *)pContext + 126) & 0x10) != 0;
      *((_DWORD *)pContext + 138) = v30;
      FileInformation = MRxSmbPseudoOpenTailFromGFAResponse(pContext);
      if ( FileInformation )
        goto LABEL_30;
      Pool2 = (struct _RX_CONTEXT *)ExAllocatePool2(64, 896, 2018667859);
      v37 = Pool2;
      if ( !Pool2 )
      {
        FileInformation = -1073741670;
LABEL_142:
        ExFreePoolWithTag(*(PVOID *)(v6 + 16), 0);
        *(_QWORD *)(v6 + 16) = 0;
        goto LABEL_30;
      }
      RxInitializeContext(0, *(PRDBSS_DEVICE_OBJECT *)(a2 + 80), 0, Pool2);
      p_EaBuffer = &v37->Create.EaBuffer;
      v37->pFcb = *(PMRX_FCB *)(a2 + 56);
      v39 = 2;
      v37->pFobx = *(PMRX_FOBX *)(a2 + 64);
      v37->CurrentIrp = *(PIRP *)(a2 + 40);
      v37->CurrentIrpSp = *(PIO_STACK_LOCATION *)(a2 + 48);
      LOBYTE(v37->RealDevice) = 0;
      v37->pRelevantSrvOpen = *(PMRX_SRV_OPEN *)(a2 + 72);
      v40 = (__int128 *)(a2 + 512);
      LODWORD(v37->RdbssDbgExtension) = -2143289342;
      *((_DWORD *)&v37->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) = 40;
      v37->LowIoContext.ParamsFor.ReadWrite.ByteOffset = (RXVBO)v31;
      v37->LowIoContext.ParamsFor.Locks.Flags = 4;
      do
      {
        p_EaBuffer += 16;
        v41 = *v40;
        v40 += 8;
        *((_OWORD *)p_EaBuffer - 8) = v41;
        *((_OWORD *)p_EaBuffer - 7) = *(v40 - 7);
        *((_OWORD *)p_EaBuffer - 6) = *(v40 - 6);
        *((_OWORD *)p_EaBuffer - 5) = *(v40 - 5);
        *((_OWORD *)p_EaBuffer - 4) = *(v40 - 4);
        *((_OWORD *)p_EaBuffer - 3) = *(v40 - 3);
        *((_OWORD *)p_EaBuffer - 2) = *(v40 - 2);
        *((_OWORD *)p_EaBuffer - 1) = *(v40 - 1);
        --v39;
      }
      while ( v39 );
      *(_OWORD *)p_EaBuffer = *v40;
      *((_OWORD *)p_EaBuffer + 1) = v40[1];
      *((_OWORD *)p_EaBuffer + 2) = v40[2];
      *((_OWORD *)p_EaBuffer + 3) = v40[3];
      *((_OWORD *)p_EaBuffer + 4) = v40[4];
      p_EaBuffer[10] = (PVOID)*((_QWORD *)v40 + 10);
      FileInformation = MRxSmbQueryFileInformation(v37);
      ExFreePoolWithTag(v37, 0);
      if ( FileInformation )
        goto LABEL_142;
      v42 = (*((_DWORD *)pContext + 126) & 0x10) != 0;
      pContext[533] = v42;
      *((_DWORD *)pContext + 138) = !v42 + 1;
      v43 = (struct _RX_CONTEXT *)ExAllocatePool2(64, 896, 2018667859);
      v44 = v43;
      if ( v43 )
      {
        RxInitializeContext(0, *(PRDBSS_DEVICE_OBJECT *)(a2 + 80), 0, v43);
        v46 = &v44->Create.EaBuffer;
        v44->pFcb = *(PMRX_FCB *)(a2 + 56);
        v47 = 2;
        v44->pFobx = *(PMRX_FOBX *)(a2 + 64);
        v44->CurrentIrp = *(PIRP *)(a2 + 40);
        v44->CurrentIrpSp = *(PIO_STACK_LOCATION *)(a2 + 48);
        LOBYTE(v44->RealDevice) = 0;
        v48 = *(struct _MRX_SRV_OPEN_ **)(a2 + 72);
        v44->LowIoContext.ParamsFor.ReadWrite.ByteOffset = (RXVBO)v32;
        v45 = (_DWORD *)(a2 + 512);
        v44->pRelevantSrvOpen = v48;
        v49 = (__int128 *)(a2 + 512);
        LODWORD(v44->RdbssDbgExtension) = -2143289342;
        *((_DWORD *)&v44->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) = 24;
        v44->LowIoContext.ParamsFor.Locks.Flags = 5;
        do
        {
          v46 += 16;
          v50 = *v49;
          v49 += 8;
          *((_OWORD *)v46 - 8) = v50;
          *((_OWORD *)v46 - 7) = *(v49 - 7);
          *((_OWORD *)v46 - 6) = *(v49 - 6);
          *((_OWORD *)v46 - 5) = *(v49 - 5);
          *((_OWORD *)v46 - 4) = *(v49 - 4);
          *((_OWORD *)v46 - 3) = *(v49 - 3);
          *((_OWORD *)v46 - 2) = *(v49 - 2);
          *((_OWORD *)v46 - 1) = *(v49 - 1);
          --v47;
        }
        while ( v47 );
        *(_OWORD *)v46 = *v49;
        *((_OWORD *)v46 + 1) = v49[1];
        *((_OWORD *)v46 + 2) = v49[2];
        *((_OWORD *)v46 + 3) = v49[3];
        *((_OWORD *)v46 + 4) = v49[4];
        v46[10] = (PVOID)*((_QWORD *)v49 + 10);
        FileInformation = MRxSmbQueryFileInformation(v44);
        ExFreePoolWithTag(v44, 0);
      }
      else
      {
        FileInformation = -1073741670;
        v45 = (_DWORD *)(a2 + 512);
      }
      if ( FileInformation )
        goto LABEL_142;
      v51 = pContext[533];
      if ( (v45[7] & 1) != 0 )
      {
        if ( !v51 )
        {
          FileInformation = -1073741565;
          goto LABEL_142;
        }
        v54 = Fcb;
      }
      else
      {
        HIDWORD(InitPacket.pAttributes) = 0;
        if ( v51 )
        {
          v52 = 60449;
          *(_DWORD *)(ActualAllocationLength + 84) = *((_DWORD *)pContext + 126);
        }
        else
        {
          v52 = 60450;
        }
        if ( (*((_DWORD *)pContext + 126) & 0x400) != 0 )
        {
          v53 = 2;
        }
        else
        {
          v53 = 1;
          if ( (v45[7] & 0x200000) != 0 )
            v53 = 4;
        }
        v54 = Fcb;
        LODWORD(InitPacket.pAttributes) = v53;
        InitPacket.pCreationTime = (PLARGE_INTEGER)(pContext + 528);
        InitPacket.pLastWriteTime = (PLARGE_INTEGER)(pContext + 480);
        InitPacket.pLastChangeTime = (PLARGE_INTEGER)(pContext + 488);
        InitPacket.pAllocationSize = (PLARGE_INTEGER)(pContext + 496);
        InitPacket.pFileSize = (PLARGE_INTEGER)(pContext + 512);
        InitPacket.pValidDataLength = (PLARGE_INTEGER)(pContext + 520);
        v64 = pContext + 520;
        Blink_high = HIDWORD(Fcb->SrvOpenList.Blink);
        InitPacket.pNumLinks = (PULONG)(pContext + 504);
        InitPacket.pLastAccessTime = (PLARGE_INTEGER)(pContext + 472);
        if ( (Blink_high & 2) == 0 )
          RxFinishFcbInitialization(Fcb, v52, &InitPacket);
      }
      if ( (*v45 & 0x10000) == 0
        || v54[1].Header.FilterContexts.Blink
        || (v65 & 0x1000000) == 0
        || *(_BYTE *)(v60 + 106) != 2 )
      {
        goto LABEL_30;
      }
      v56 = MRxSmbQueryFileInformationFromPseudoOpen(pContext, a2, 6);
      v18 = ActualAllocationLength;
      FileInformation = v56;
      if ( v56 )
        goto LABEL_121;
    }
    *(_QWORD *)(v18 + 96) = *((_QWORD *)pContext + 67);
    v54[1].Header.FilterContexts.Blink = (struct _LIST_ENTRY *)*((_QWORD *)pContext + 67);
  }
  else
  {
    v58 = 0;
    if ( (v65 & 0x10) != 0 && (*(_DWORD *)(a2 + 540) & 1) == 0 )
    {
      v58 = 1;
      if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))MRxSmbCanCreatePseudoOpen)(
                           a2,
                           Fcb,
                           (union _LARGE_INTEGER)Time.QuadPart,
                           1) )
      {
        if ( *(_WORD *)(*(_QWORD *)(a2 + 56) + 360LL) )
          v59 = 2;
        else
          v59 = 1;
        FileInformation = MRxSmbPseudoOpenTailFromFakeGFAResponse(pContext, v59);
        if ( FileInformation )
          goto LABEL_30;
        if ( !LOWORD(Fcb[2].Header.Resource) )
          goto LABEL_30;
        FileInformation = MRxSmbQueryFileInformationFromPseudoOpen(pContext, a2, 4);
        if ( !FileInformation )
          goto LABEL_30;
        goto LABEL_142;
      }
      FileInformation = MRxSmbBuildOpenAndX(v3);
      if ( FileInformation )
        goto LABEL_30;
      FileInformation = SmbPseOrdinaryExchange(pContext);
      if ( FileInformation != -1073741790 )
        goto LABEL_30;
    }
    FileInformation = MRxSmbDownlevelCreate(pContext);
    if ( !FileInformation )
      goto LABEL_30;
    v18 = ActualAllocationLength;
    if ( v58 )
      FileInformation = -1073741790;
  }
LABEL_31:
  if ( (*(_DWORD *)v6 & 0x10) != 0 )
  {
    ++*(_WORD *)(v18 + 8);
    *(_DWORD *)(a2 + 740) &= 0xF5FFFFFF;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      39,
      WPP_d95790c14120305e97e490eb33b089fe_Traceguids,
      (unsigned int)FileInformation);
  return (unsigned int)FileInformation;
}

```

## disassembly

```asm
0x140047fb0  push    rbp
0x140047fb2  push    rbx
0x140047fb3  push    rsi
0x140047fb4  push    rdi
0x140047fb5  push    r12
0x140047fb7  push    r13
0x140047fb9  push    r14
0x140047fbb  push    r15
0x140047fbd  lea     rbp, [rsp-1Fh]
0x140047fc2  sub     rsp, 0B8h
0x140047fc9  mov     rax, [rdx+38h]
0x140047fcd  lea     r12, [rcx+378h]
0x140047fd4  mov     [rbp+57h+Fcb], rax
0x140047fd8  mov     rsi, rdx
0x140047fdb  mov     rbx, rcx
0x140047fde  test    rax, rax
0x140047fe1  jnz     short loc_140047FE9
0x140047fe3  mov     [rbp+57h+arg_8], rax
0x140047fe7  jmp     short loc_140047FF4
0x140047fe9  mov     rax, [rax+88h]
0x140047ff0  mov     [rbp+57h+arg_8], rax
0x140047ff4  mov     r14, [rdx+48h]
0x140047ff8  test    r14, r14
0x140047ffb  jz      short loc_140048001
0x140047ffd  mov     r14, [r14+30h]
0x140048001  mov     rax, [rcx+58h]
0x140048005  movzx   r13d, byte ptr [rcx+234h]
0x14004800d  mov     rax, [rax+68h]
0x140048011  mov     [rbp+57h+var_C0], rax
0x140048015  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004801c  lea     rax, WPP_GLOBAL_Control
0x140048023  cmp     rcx, rax
0x140048026  jz      short loc_140048046
0x140048028  test    dword ptr [rcx+2Ch], 400h
0x14004802f  jz      short loc_140048046
0x140048031  mov     rcx, [rcx+18h]
0x140048035  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x14004803c  mov     edx, 24h ; '$'
0x140048041  call    WPP_SF_
0x140048046  mov     rax, [rbx+50h]
0x14004804a  mov     rcx, r12
0x14004804d  add     rax, 190h
0x140048053  mov     qword ptr [rbp+57h+Time], rax
0x140048057  mov     r15d, [rax+14h]
0x14004805b  mov     [rbp+57h+arg_0], r15d
0x14004805f  call    MRxSmbSetInitialSMB
0x140048064  mov     edi, eax
0x140048066  test    eax, eax
0x140048068  jnz     loc_140048145
0x14004806e  mov     rax, [rbx+58h]
0x140048072  test    rax, rax
0x140048075  jz      short loc_14004807D
0x140048077  mov     r8, [rax+60h]
0x14004807b  jmp     short loc_140048080
0x14004807d  xor     r8d, r8d
0x140048080  mov     rcx, [rsi+2A0h]
0x140048087  test    rcx, rcx
0x14004808a  jz      loc_14004811F
0x140048090  mov     eax, [rcx+8]
0x140048093  sub     eax, 2
0x140048096  test    eax, 0FFFFFFFDh
0x14004809b  jnz     short loc_1400480E8
0x14004809d  mov     r9, [rbx+50h]
0x1400480a1  test    byte ptr [r9+2A0h], 8
0x1400480a9  jnz     short loc_1400480E8
0x1400480ab  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400480b2  lea     r13, WPP_GLOBAL_Control
0x1400480b9  cmp     rcx, r13
0x1400480bc  jz      short loc_1400480E1
0x1400480be  test    dword ptr [rcx+2Ch], 100h
0x1400480c5  jz      short loc_1400480E1
0x1400480c7  mov     edx, 25h ; '%'
0x1400480cc  mov     rcx, [rcx+18h]
0x1400480d0  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x1400480d7  mov     [rsp+0F0h+var_D0], rsi
0x1400480dc  call    WPP_SF_qq
0x1400480e1  mov     edi, 0C0000201h
0x1400480e6  jmp     short loc_14004814C
0x1400480e8  mov     eax, [rcx+0Ch]
0x1400480eb  test    al, 8
0x1400480ed  jz      short loc_14004811F
0x1400480ef  cmp     byte ptr [r8+17Dh], 0
0x1400480f7  jnz     short loc_14004811F
0x1400480f9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140048100  lea     r13, WPP_GLOBAL_Control
0x140048107  cmp     rcx, r13
0x14004810a  jz      short loc_1400480E1
0x14004810c  test    dword ptr [rcx+2Ch], 100h
0x140048113  jz      short loc_1400480E1
0x140048115  mov     edx, 26h ; '&'
0x14004811a  mov     r9, r8
0x14004811d  jmp     short loc_1400480CC
0x14004811f  mov     rdx, [rsi+2A8h]
0x140048126  mov     rcx, r8
0x140048129  call    SmbCeSetupAlternateSPNForSession
0x14004812e  mov     edi, eax
0x140048130  cmp     eax, 0C000035Ch
0x140048135  jnz     short loc_14004813E
0x140048137  mov     edi, 0C0410001h
0x14004813c  jmp     short loc_140048142
0x14004813e  test    eax, eax
0x140048140  jns     short loc_1400481A9
0x140048142  mov     [rbx+28h], edi
0x140048145  lea     r13, WPP_GLOBAL_Control
0x14004814c  mov     rcx, [rbp+57h+arg_8]
0x140048150  mov     eax, [r14]
0x140048153  test    al, 10h
0x140048155  jz      short loc_140048165
0x140048157  inc     word ptr [rcx+8]
0x14004815b  and     dword ptr [rsi+2E4h], 0F5FFFFFFh
0x140048165  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004816c  cmp     rcx, r13
0x14004816f  jz      short loc_140048192
0x140048171  test    dword ptr [rcx+2Ch], 400h
0x140048178  jz      short loc_140048192
0x14004817a  mov     rcx, [rcx+18h]
0x14004817e  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140048185  mov     edx, 27h ; '''
0x14004818a  mov     r9d, edi
0x14004818d  call    WPP_SF_d
0x140048192  mov     eax, edi
0x140048194  add     rsp, 0B8h
0x14004819b  pop     r15
0x14004819d  pop     r14
0x14004819f  pop     r13
0x1400481a1  pop     r12
0x1400481a3  pop     rdi
0x1400481a4  pop     rsi
0x1400481a5  pop     rbx
0x1400481a6  pop     rbp
0x1400481a7  retn
0x1400481a9  and     r15d, 40000h
0x1400481b0  jnz     loc_14004824B
0x1400481b6  mov     rdx, [rbp+57h+Fcb]
0x1400481ba  xorps   xmm0, xmm0
0x1400481bd  add     rdx, 168h; SourceString
0x1400481c4  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400481c8  cmp     [rdx], r15w
0x1400481cc  jz      short loc_14004824B
0x1400481ce  mov     r8b, 1; AllocateDestinationString
0x1400481d1  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400481d5  call    cs:__imp_RtlUnicodeStringToOemString
0x1400481dc  nop     dword ptr [rax+rax+00h]
0x1400481e1  mov     edi, eax
0x1400481e3  test    eax, eax
0x1400481e5  js      loc_140048145
0x1400481eb  movaps  xmm0, xmmword ptr [rbp+57h+DestinationString.Length]
0x1400481ef  lea     rcx, [rbp+57h+DbcsName]; DbcsName
0x1400481f3  xor     edx, edx; WildCardsPermissible
0x1400481f5  movdqa  xmmword ptr [rbp+57h+DbcsName.Length], xmm0
0x1400481fa  test    byte ptr [rbp+57h+arg_0], 20h
0x1400481fe  mov     r9b, 1; LeadingBackslashPermissible
0x140048201  movzx   r8d, r9b; PathNamePermissible
0x140048205  jnz     short loc_140048231
0x140048207  call    cs:__imp_FsRtlIsFatDbcsLegal
0x14004820e  nop     dword ptr [rax+rax+00h]
0x140048213  lea     rcx, [rbp+57h+DestinationString]; OemString
0x140048217  test    al, al
0x140048219  jnz     short loc_14004823F
0x14004821b  call    cs:__imp_RtlFreeOemString
0x140048222  nop     dword ptr [rax+rax+00h]
0x140048227  mov     edi, 0C0000033h
0x14004822c  jmp     loc_140048145
0x140048231  call    cs:__imp_FsRtlIsHpfsDbcsLegal
0x140048238  nop     dword ptr [rax+rax+00h]
0x14004823d  jmp     short loc_140048213
0x14004823f  call    cs:__imp_RtlFreeOemString
0x140048246  nop     dword ptr [rax+rax+00h]
0x14004824b  cmp     byte ptr [r12+78h], 0FFh
0x140048251  jz      short loc_140048289
0x140048253  xor     r8d, r8d
0x140048256  mov     rdx, rsi
0x140048259  mov     rcx, rbx; pContext
0x14004825c  call    SmbPseOrdinaryExchange
0x140048261  mov     edi, eax
0x140048263  test    eax, eax
0x140048265  jnz     loc_140048145
0x14004826b  mov     rcx, rbx
0x14004826e  call    SmbCeUpdateSessionEntryAndVNetRootContext
0x140048273  and     dword ptr [rbx+48h], 0FFFFFFEFh
0x140048277  mov     rcx, r12
0x14004827a  call    MRxSmbSetInitialSMB
0x14004827f  mov     edi, eax
0x140048281  test    eax, eax
0x140048283  jnz     loc_140048145
0x140048289  test    r13b, r13b
0x14004828c  jnz     loc_140048145
0x140048292  lea     rdi, [rbx+22Ch]
0x140048299  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400482a0  lea     r13, WPP_GLOBAL_Control
0x1400482a7  cmp     rcx, r13
0x1400482aa  jz      short loc_1400482CA
0x1400482ac  test    dword ptr [rcx+2Ch], 400h
0x1400482b3  jz      short loc_1400482CA
0x1400482b5  mov     rcx, [rcx+18h]
0x1400482b9  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x1400482c0  mov     edx, 1Fh
0x1400482c5  call    WPP_SF_
0x1400482ca  cmp     dword ptr [rsi+78h], 0
0x1400482ce  jl      loc_140048395
0x1400482d4  and     dword ptr [rsi+21Ch], 0FFFFFFCFh
0x1400482db  mov     rcx, [rsi+28h]; Irp
0x1400482df  test    rcx, rcx
0x1400482e2  jz      short loc_1400482F2
0x1400482e4  call    cs:__imp_IoGetRequestorProcessId
0x1400482eb  nop     dword ptr [rax+rax+00h]
0x1400482f0  mov     [rdi], eax
0x1400482f2  mov     byte ptr [rdi+4], 0
0x1400482f6  mov     rax, [rsi+220h]
0x1400482fd  test    rax, rax
0x140048300  jz      short loc_14004832E
0x140048302  mov     rcx, [rax]
0x140048305  test    rcx, rcx
0x140048308  jz      short loc_14004832E
0x14004830a  xor     dl, dl
0x14004830c  cmp     byte ptr [rcx+8], 1
0x140048310  jnz     short loc_140048318
0x140048312  mov     byte ptr [rdi+4], 1
0x140048316  mov     dl, 1
0x140048318  mov     rax, [rsi+220h]
0x14004831f  mov     rcx, [rax]
0x140048322  cmp     byte ptr [rcx+9], 0
0x140048326  jz      short loc_14004832E
0x140048328  or      dl, 2
0x14004832b  mov     [rdi+4], dl
0x14004832e  xor     r8d, r8d
0x140048331  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140048338  cmp     rcx, r13
0x14004833b  jz      short loc_14004835E
0x14004833d  test    dword ptr [rcx+2Ch], 400h
0x140048344  jz      short loc_14004835E
0x140048346  mov     rcx, [rcx+18h]
0x14004834a  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140048351  mov     edx, 20h ; ' '
0x140048356  call    WPP_SF_
0x14004835b  xor     r8d, r8d
0x14004835e  mov     rax, [rsi+288h]
0x140048365  cmp     byte ptr [rax+4Dh], 3
0x140048369  jnz     short loc_1400483C1
0x14004836b  mov     rcx, r12
0x14004836e  call    MRxSmbBuildOpenPrintFile
0x140048373  mov     edi, eax
0x140048375  test    eax, eax
0x140048377  jnz     loc_14004814C
0x14004837d  mov     r8d, 20h ; ' '
0x140048383  mov     rdx, rsi
0x140048386  mov     rcx, rbx; pContext
0x140048389  call    SmbPseOrdinaryExchange
0x14004838e  mov     edi, eax
0x140048390  jmp     loc_14004814C
0x140048395  mov     rax, [rsi+48h]
0x140048399  xor     r8d, r8d
0x14004839c  test    rax, rax
0x14004839f  jnz     short loc_1400483A6
0x1400483a1  mov     eax, r8d
0x1400483a4  jmp     short loc_1400483AA
0x1400483a6  mov     rax, [rax+30h]
0x1400483aa  mov     [rsi+220h], r8
0x1400483b1  mov     rax, [rax+10h]
0x1400483b5  mov     rcx, [rax+5Ch]
0x1400483b9  mov     [rdi], rcx
0x1400483bc  jmp     loc_140048331
0x1400483c1  test    r15d, r15d
0x1400483c4  jz      loc_140048A1B
0x1400483ca  mov     rax, [rsi+220h]
0x1400483d1  test    rax, rax
0x1400483d4  jz      short loc_1400483EA
0x1400483d6  mov     rcx, [rax+8]
0x1400483da  test    rcx, rcx
0x1400483dd  jz      short loc_1400483EA
0x1400483df  cmp     qword ptr [rcx+40h], 0
0x1400483e4  jnz     loc_140048950
0x1400483ea  cmp     cs:MRxSmbDeferredOpensEnabled, 0
0x1400483f1  jz      loc_140048950
0x1400483f7  test    dword ptr [rsi+78h], 0A0000000h
0x1400483fe  jnz     loc_140048950
0x140048404  mov     rax, [rbp+57h+Fcb]
0x140048408  mov     rax, [rax+78h]
0x14004840c  cmp     byte ptr [rax+4Dh], 0
0x140048410  jnz     loc_140048950
0x140048416  cmp     dword ptr [rsi+218h], 1
0x14004841d  jnz     loc_140048950
0x140048423  mov     edx, [rsi+21Ch]
0x140048429  bt      edx, 0Eh
0x14004842d  jb      loc_140048950
0x140048433  test    dword ptr [rsi+200h], 0FFEFFF7Fh
0x14004843d  setnz   cl
0x140048440  test    dl, 1
0x140048443  setz    al
0x140048446  test    al, cl
0x140048448  jnz     loc_140048950
0x14004844e  mov     eax, edx
0x140048450  mov     edx, 1
0x140048455  test    dl, al
0x140048457  jnz     short loc_14004846E
0x140048459  mov     rax, [rsi+38h]
0x14004845d  cmp     word ptr [rax+168h], 0
0x140048465  jbe     short loc_14004846E
0x140048467  mov     edi, 2
0x14004846c  jmp     short loc_140048470
  ... truncated ...
```
