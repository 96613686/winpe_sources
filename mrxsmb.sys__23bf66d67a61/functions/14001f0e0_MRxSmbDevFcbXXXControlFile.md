# MRxSmbDevFcbXXXControlFile

- ea: `0x14001f0e0`
- end: `0x14001feda`
- name: `MRxSmbDevFcbXXXControlFile`
- size: `3578`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `44`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14001f0b0`

## callees

- `0x140003480`
- `0x140014400`
- `0x140014650`
- `0x14001f0e0`
- `0x14001fee0`
- `0x140023cc0`
- `0x140027a4c`
- `0x140027dc0`
- `0x140037e44`
- `0x14003838c`
- `0x140038f84`
- `0x140039368`
- `0x1400394bc`
- `0x140039610`
- `0x140039644`
- `0x140039f5c`
- `0x140039fa8`
- `0x140039fd8`
- `0x14003bdcc`
- `0x140044420`
- `0x140049c0c`
- `0x140049d2c`
- `0x140049e60`
- `0x14004ca28`
- `0x14007e008`
- `0x14007e274`
- `0x14007e37c`
- `0x14007e778`
- `0x14007e8e0`
- `0x14007edb4`
- `0x14007eee0`
- `0x14007f05c`
- `0x14007f58c`
- `0x14007f65c`
- `0x14007f8e4`
- `0x140081b78`
- `0x140081d3c`
- `0x140084268`
- `0x1400842ac`
- `0x140084d4c`
- `0x140090bb0`
- `0x140091690`
- `0x1400922d0`
- `0x140093050`

## import_xrefs

- `ntoskrnl!IoGetSiloParameters` at `0x14001f237`
- `ntoskrnl!IoGetSiloParameters` at `0x14001f38b`
- `ntoskrnl!IoGetSiloParameters` at `0x14001f417`
- `ntoskrnl!IoGetSiloParameters` at `0x14001f4ef`
- `ntoskrnl!IoGetSiloParameters` at `0x14001fb08`
- `ntoskrnl!IoGetSiloParameters` at `0x14001f237`
- `ntoskrnl!IoGetSiloParameters` at `0x14001f38b`
- `ntoskrnl!IoGetSiloParameters` at `0x14001f417`
- `ntoskrnl!IoGetSiloParameters` at `0x14001f4ef`
- `ntoskrnl!IoGetSiloParameters` at `0x14001fb08`
- `ntoskrnl!PsGetEffectiveServerSilo` at `0x14001f24c`
- `ntoskrnl!PsGetEffectiveServerSilo` at `0x14001f3a0`
- `ntoskrnl!PsGetEffectiveServerSilo` at `0x14001f42c`
- `ntoskrnl!PsGetEffectiveServerSilo` at `0x14001f504`
- `ntoskrnl!PsGetEffectiveServerSilo` at `0x14001fb1d`
- `ntoskrnl!PsGetEffectiveServerSilo` at `0x14001f24c`
- `ntoskrnl!PsGetEffectiveServerSilo` at `0x14001f3a0`
- `ntoskrnl!PsGetEffectiveServerSilo` at `0x14001f42c`
- `ntoskrnl!PsGetEffectiveServerSilo` at `0x14001f504`
- `ntoskrnl!PsGetEffectiveServerSilo` at `0x14001fb1d`
- `ntoskrnl!PsIsHostSilo` at `0x14001f25e`
- `ntoskrnl!PsIsHostSilo` at `0x14001f3b2`
- `ntoskrnl!PsIsHostSilo` at `0x14001f43e`
- `ntoskrnl!PsIsHostSilo` at `0x14001f516`
- `ntoskrnl!PsIsHostSilo` at `0x14001fb2f`
- `ntoskrnl!PsIsHostSilo` at `0x14001f25e`
- `ntoskrnl!PsIsHostSilo` at `0x14001f3b2`
- `ntoskrnl!PsIsHostSilo` at `0x14001f43e`
- `ntoskrnl!PsIsHostSilo` at `0x14001f516`
- `ntoskrnl!PsIsHostSilo` at `0x14001fb2f`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001f864`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001f8c5`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001f864`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001f8c5`
- `ntoskrnl!SeExports` at `0x14001f656`
- `ntoskrnl!SeExports` at `0x14001f676`
- `ntoskrnl!SeExports` at `0x14001f6bc`
- `ntoskrnl!SeExports` at `0x14001f702`
- `ntoskrnl!SeExports` at `0x14001f755`
- `ntoskrnl!SeExports` at `0x14001f7ac`
- `ntoskrnl!SeExports` at `0x14001f7cc`
- `ntoskrnl!SeExports` at `0x14001f8ea`
- `ntoskrnl!SeExports` at `0x14001f9c1`
- `ntoskrnl!SeExports` at `0x14001fa13`
- `ntoskrnl!SeExports` at `0x14001fcd7`
- `ntoskrnl!SeExports` at `0x14001fcf7`
- `ntoskrnl!SeExports` at `0x14001fd4e`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001f666`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001f68b`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001f6d1`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001f717`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001f76a`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001f7bc`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001f7dc`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001f8ff`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001f9d6`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001fa28`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001fce7`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001fd0c`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001fd63`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001f666`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001f68b`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001f6d1`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001f717`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001f76a`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001f7bc`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001f7dc`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001f8ff`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001f9d6`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001fa28`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001fce7`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001fd0c`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14001fd63`
- `rdbss!RxDeleteLinkedVNetRoot` at `0x14001f5e2`
- `rdbss!RxDeleteLinkedVNetRoot` at `0x14001f5e2`
- `rdbss!RxCreateLinkedVNetRoot` at `0x14001f621`
- `rdbss!RxCreateLinkedVNetRoot` at `0x14001f621`
- `rdbss!RxSignalNetStatus` at `0x14001f4cf`
- `rdbss!RxSignalNetStatus` at `0x14001f4cf`
- `rdbss!RxStopMinirdr` at `0x14001f300`
- `rdbss!RxStopMinirdr` at `0x14001f300`
- `rdbss!RxStartMinirdr` at `0x14001fc43`
- `rdbss!RxStartMinirdr` at `0x14001fc43`
- `rdbss!RxGetSiloFromIrp` at `0x14001f48c`
- `rdbss!RxGetSiloFromIrp` at `0x14001f48c`

## pseudocode

```c
__int64 __fastcall MRxSmbDevFcbXXXControlFile(PRX_CONTEXT RxContext, __int64 a2, __int64 a3, int a4)
{
  PMRX_FOBX pFobx; // rsi
  int RealDevice_low; // ebx
  unsigned int v7; // ebp
  int RdbssDbgExtension; // r14d
  int v9; // ecx
  int LinkedVNetRoot; // ebx
  int v11; // r12d
  int v12; // r14d
  unsigned __int64 v13; // rdx
  __int64 SiloParameters; // rax
  __int64 EffectiveServerSilo; // rbp
  signed __int32 v16; // eax
  bool v17; // zf
  int ConnectionInfo; // eax
  __int64 v19; // rax
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rbx
  __int64 SiloFromIrp; // r14
  __int64 UnavailableServerListForDeviceSilo; // rax
  __int64 InvalidAuthEntryListForDeviceSilo; // rax
  __int64 v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rbx
  unsigned __int64 v29; // rax
  _DWORD *v30; // r8
  __int64 v31; // rdx
  PIRP CurrentIrp; // rax
  PIRP v33; // rax
  PIRP v34; // rax
  PIRP v35; // rax
  PNON_PAGED_FCB NonPagedFcb; // rbx
  __int64 v37; // r13
  ULONG_PTR v38; // rbp
  KIRQL v39; // r15
  ULONG_PTR FirstServerEntry; // rsi
  __int64 v41; // rdx
  __int64 v42; // r8
  struct _NON_PAGED_FCB *v43; // rdx
  unsigned int v44; // ebp
  unsigned int v45; // ebp
  unsigned int v46; // ebp
  wchar_t *Buffer; // rcx
  ULONG_PTR v48; // r14
  PDEVICE_OBJECT v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // rax
  __int64 v52; // r15
  int v53; // eax
  __int64 result; // rax
  NTSTATUS started; // eax
  PIRP v56; // rax
  _OWORD v57[3]; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v58; // [rsp+70h] [rbp+8h] BYREF

  pFobx = RxContext->pFobx;
  RealDevice_low = LOBYTE(RxContext->RealDevice);
  v7 = *((_DWORD *)&RxContext->9 + 35);
  RdbssDbgExtension = (int)RxContext->RdbssDbgExtension;
  v9 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_c86fdb6c24cc347f0e6836246d5ec6ea_Traceguids);
  }
  if ( RealDevice_low != 13 )
  {
    if ( (unsigned int)(RealDevice_low - 14) < 2 )
    {
      if ( v7 == 1311736 )
      {
        if ( MRxSmbBootedRemotely )
        {
          MRxSmbUseKernelModeSecurity = 1;
          LinkedVNetRoot = 0;
        }
        else
        {
          LinkedVNetRoot = -1073741823;
        }
      }
      else
      {
        LinkedVNetRoot = -1073741808;
      }
    }
    else
    {
      LinkedVNetRoot = -1073741808;
    }
    goto LABEL_207;
  }
  if ( *((_BYTE *)&RxContext->9 + 176) )
  {
    LinkedVNetRoot = -1073741808;
    goto LABEL_207;
  }
  if ( v7 == 1311143 )
  {
    if ( (int)MRxSmbCheckDevFcbXXXControlFileAccess(1u) < 0 )
    {
      LinkedVNetRoot = -1073741790;
      goto LABEL_207;
    }
    if ( pFobx )
    {
      LinkedVNetRoot = -1073741808;
      goto LABEL_207;
    }
    ConnectionInfo = SmbShellEnumerateConnections(RxContext);
    goto LABEL_206;
  }
  if ( v7 == 1311139 )
  {
    if ( !pFobx )
    {
      LinkedVNetRoot = -1073741808;
      goto LABEL_207;
    }
    ConnectionInfo = SmbShellGetConnectionInfo(RxContext);
    goto LABEL_206;
  }
  LinkedVNetRoot = -1073741808;
  v11 = RdbssDbgExtension & 2;
  v12 = RdbssDbgExtension & 0x200;
  if ( v7 <= 0x1403A0 )
  {
    if ( v7 != 1311648 )
    {
      v13 = 0x140000000uLL;
      switch ( v7 )
      {
        case 0x140191u:
          goto LABEL_139;
        case 0x140194u:
          if ( (PRDBSS_DEVICE_OBJECT)RxContext->NonPagedFcb != MRxSmbDeviceObject )
            goto LABEL_207;
          SiloParameters = IoGetSiloParameters(RxContext->CurrentIrp->Tail.Overlay.CurrentStackLocation->FileObject);
          if ( SiloParameters )
          {
            EffectiveServerSilo = PsGetEffectiveServerSilo(*(_QWORD *)(SiloParameters + 8));
            if ( !(unsigned __int8)PsIsHostSilo(EffectiveServerSilo) )
            {
              if ( EffectiveServerSilo )
              {
                LinkedVNetRoot = 0;
                goto LABEL_207;
              }
            }
          }
          if ( (int)MRxSmbCheckDevFcbXXXControlFileAccess(2u) < 0 )
          {
            LinkedVNetRoot = -1073741790;
            goto LABEL_207;
          }
          if ( pFobx )
            goto LABEL_207;
          if ( MRxSmbBootedRemotely )
            goto LABEL_143;
          v16 = _InterlockedCompareExchange(&MRxSmbState, 3, 2);
          *((_QWORD *)RxContext->NonPagedFcb->SectionObjectPointers.DataSectionObject + 13) = MRxSmbUnload;
          if ( (unsigned int)(v16 - 2) <= 1 )
          {
            if ( v12 )
            {
              if ( !v11 )
                __int2c();
              LinkedVNetRoot = RxStopMinirdr(RxContext, (PBOOLEAN)&RxContext->RealDevice + 3);
              WitnessUpcallTerminate();
              v17 = ((__int64)RxContext->RdbssDbgExtension & 0x200) == 0;
              WitnessAlreadyStarted = 0;
              if ( !v17 )
                StopMailslotMiniRdrInFSP(RxContext);
            }
            else
            {
              LinkedVNetRoot = -1069481981;
              BYTE3(RxContext->RealDevice) = 1;
            }
          }
          goto LABEL_207;
        case 0x140199u:
          v19 = IoGetSiloParameters(RxContext->CurrentIrp->Tail.Overlay.CurrentStackLocation->FileObject);
          if ( v19 )
          {
            v20 = PsGetEffectiveServerSilo(*(_QWORD *)(v19 + 8));
            if ( !(unsigned __int8)PsIsHostSilo(v20) )
            {
              if ( v20 )
                goto LABEL_145;
            }
          }
          if ( (int)MRxSmbCheckDevFcbXXXControlFileAccess(2u) < 0 )
            goto LABEL_145;
          ConnectionInfo = MRxSmbSetConfigurationInformation(RxContext);
          goto LABEL_206;
        case 0x14019Eu:
          if ( (int)MRxSmbCheckDevFcbXXXControlFileAccess(2u) < 0 )
          {
            LinkedVNetRoot = -1073741790;
            goto LABEL_207;
          }
          ConnectionInfo = MRxSmbGetConfigurationInformation(RxContext);
          goto LABEL_206;
        case 0x1401A8u:
          CurrentIrp = RxContext->CurrentIrp;
          if ( (!CurrentIrp || CurrentIrp->RequestorMode) && !SeSinglePrivilegeCheck(SeExports->SeTcbPrivilege, 1) )
          {
            LinkedVNetRoot = -1073741790;
            if ( !SeSinglePrivilegeCheck(SeExports->SeLoadDriverPrivilege, 1) )
              goto LABEL_207;
          }
          ConnectionInfo = ProcessUserDisconnectRequest(
                             RxContext,
                             0,
                             *((_QWORD *)&RxContext->9 + 19),
                             *((unsigned int *)&RxContext->9 + 42));
          goto LABEL_206;
        case 0x1401ACu:
          if ( !pFobx )
            goto LABEL_207;
          ConnectionInfo = SmbShellDeleteConnection(RxContext, *((_QWORD *)pFobx->Context2 + 5));
          goto LABEL_206;
        case 0x1401B0u:
          v33 = RxContext->CurrentIrp;
          if ( !v33 || v33->RequestorMode )
          {
            LinkedVNetRoot = -1073741790;
            if ( !SeSinglePrivilegeCheck(SeExports->SeLoadDriverPrivilege, 1) )
              goto LABEL_207;
          }
          ConnectionInfo = MRxSmbBindTransportFsCtl(
                             RxContext,
                             *((_QWORD *)&RxContext->9 + 19),
                             *((unsigned int *)&RxContext->9 + 42));
          goto LABEL_206;
        case 0x1401B4u:
          v34 = RxContext->CurrentIrp;
          if ( !v34 || v34->RequestorMode )
          {
            LinkedVNetRoot = -1073741790;
            if ( !SeSinglePrivilegeCheck(SeExports->SeLoadDriverPrivilege, 1) )
              goto LABEL_207;
          }
          ConnectionInfo = MRxSmbUnbindTransportFsCtl(
                             RxContext,
                             *((_QWORD *)&RxContext->9 + 19),
                             *((unsigned int *)&RxContext->9 + 42));
          goto LABEL_206;
        case 0x1401BBu:
          if ( pFobx )
            goto LABEL_207;
          ConnectionInfo = MRxEnumerateTransports(RxContext);
          goto LABEL_206;
        case 0x1401D0u:
          ConnectionInfo = MRxSmbGetStatistics(RxContext);
          goto LABEL_206;
        case 0x1401D8u:
          v57[0] = 0;
          if ( pFobx )
          {
            v29 = *((unsigned int *)&RxContext->9 + 42);
            if ( (unsigned int)v29 >= 0x24 )
            {
              v30 = (_DWORD *)*((_QWORD *)&RxContext->9 + 19);
              v31 = (unsigned int)v30[5];
              if ( v29 >= v31 + 36 && (v31 & 1) == 0 && (unsigned int)v31 < 0xFFFE )
              {
                WORD1(v57[0]) = v30[5];
                LOWORD(v57[0]) = v31;
                *((_QWORD *)&v57[0] + 1) = 0;
                if ( (_WORD)v31 )
                  *((_QWORD *)&v57[0] + 1) = v30 + 6;
                if ( *v30 == 3 )
                {
                  if ( *((_DWORD *)&RxContext->9 + 43) >= 8u )
                  {
                    LinkedVNetRoot = RxCreateLinkedVNetRoot(
                                       RxContext,
                                       *((_QWORD *)pFobx->Context2 + 5),
                                       v57,
                                       RxContext->Create.TransportName.Buffer);
                    if ( LinkedVNetRoot >= 0 )
                      RxContext->InformationToReturn = 8;
                  }
                }
                else if ( *v30 == 4 )
                {
                  RxDeleteLinkedVNetRoot(RxContext, *((_QWORD *)pFobx->Context2 + 5), 255, v57);
                  LinkedVNetRoot = 0;
                  RxContext->InformationToReturn = 0;
                }
              }
            }
          }
          goto LABEL_207;
        case 0x1401E0u:
          v21 = IoGetSiloParameters(RxContext->CurrentIrp->Tail.Overlay.CurrentStackLocation->FileObject);
          if ( v21 )
          {
            v22 = PsGetEffectiveServerSilo(*(_QWORD *)(v21 + 8));
            if ( !(unsigned __int8)PsIsHostSilo(v22) )
            {
              if ( v22 )
              {
                LinkedVNetRoot = 0;
                goto LABEL_207;
              }
            }
          }
          if ( (int)MRxSmbCheckDevFcbXXXControlFileAccess(2u) < 0 )
          {
            LinkedVNetRoot = -1073741790;
            goto LABEL_207;
          }
          ConnectionInfo = MRxSmbSetDomainName(RxContext);
          break;
        case 0x1401E4u:
          v27 = IoGetSiloParameters(RxContext->CurrentIrp->Tail.Overlay.CurrentStackLocation->FileObject);
          if ( v27 )
          {
            v28 = PsGetEffectiveServerSilo(*(_QWORD *)(v27 + 8));
            if ( !(unsigned __int8)PsIsHostSilo(v28) )
            {
              if ( v28 )
                goto LABEL_145;
            }
          }
          if ( (int)MRxSmbCheckDevFcbXXXControlFileAccess(4u) < 0 )
            goto LABEL_145;
          ConnectionInfo = MRxSmbSetServerGuid(RxContext);
          goto LABEL_206;
        case 0x1401E8u:
          v35 = RxContext->CurrentIrp;
          if ( v35
            && (!v35->RequestorMode
             || SeSinglePrivilegeCheck(SeExports->SeLoadDriverPrivilege, 1)
             || SeSinglePrivilegeCheck(SeExports->SeTcbPrivilege, 1))
            && *((_DWORD *)&RxContext->9 + 42) == 36 )
          {
            NonPagedFcb = RxContext->NonPagedFcb;
            v37 = *((_QWORD *)&RxContext->9 + 19);
            v38 = 0;
            v39 = SmbCeAcquireSpinLock(NonPagedFcb, v13, a3);
            CopyConnectionConfiguration(v37, &NonPagedFcb[5].SectionObjectPointers);
            FirstServerEntry = SmbCeGetFirstServerEntry(NonPagedFcb);
            while ( FirstServerEntry )
            {
              if ( (unsigned int)SmbCeReferenceServerEntrySafe(FirstServerEntry) )
              {
                LODWORD(NonPagedFcb[4].BufferedLocksResource.SpinLock) = -1;
                v38 = FirstServerEntry;
                ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)&NonPagedFcb[4].HeaderResource, v39);
                MRxSmb2SetConnectionProps(FirstServerEntry);
                v39 = SmbCeAcquireSpinLock(NonPagedFcb, v41, v42);
              }
              v43 = *(struct _NON_PAGED_FCB **)(FirstServerEntry + 32);
              FirstServerEntry = 0;
              if ( v43 != (struct _NON_PAGED_FCB *)&NonPagedFcb[4].SectionObjectPointers.SharedCacheMap )
                FirstServerEntry = (ULONG_PTR)&v43[-1].BufferedLocksResource.NumberOfSharedWaiters;
              if ( v38 )
              {
                SmbCeDereferenceServerEntryEx(v38);
                v38 = 0;
              }
            }
            LODWORD(NonPagedFcb[4].BufferedLocksResource.SpinLock) = -1;
            ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)&NonPagedFcb[4].HeaderResource, v39);
            LinkedVNetRoot = 0;
          }
          goto LABEL_207;
        case 0x1401F8u:
          if ( RxContext->CurrentIrp )
            SiloFromIrp = RxGetSiloFromIrp();
          else
            SiloFromIrp = 0;
          UnavailableServerListForDeviceSilo = SmbCeGetUnavailableServerListForDeviceSilo(
                                                 RxContext->NonPagedFcb,
                                                 SiloFromIrp);
          SmbCeDiscardUnavailableServerList(UnavailableServerListForDeviceSilo);
          InvalidAuthEntryListForDeviceSilo = SmbCeGetInvalidAuthEntryListForDeviceSilo(
                                                RxContext->NonPagedFcb,
                                                SiloFromIrp);
          SmbCeDiscardInvalidAuthEntryList(InvalidAuthEntryListForDeviceSilo);
          LOBYTE(v26) = 1;
          ConnectionInfo = RxSignalNetStatus(0, v26, 0);
          goto LABEL_206;
        case 0x1401FCu:
          LinkedVNetRoot = -1073741790;
          if ( !SeSinglePrivilegeCheck(SeExports->SeLoadDriverPrivilege, 1) )
            goto LABEL_207;
          ConnectionInfo = SmbCeProbeServerTransportInfo((PRDBSS_DEVICE_OBJECT)RxContext->NonPagedFcb);
          goto LABEL_206;
        default:
          goto LABEL_207;
      }
      goto LABEL_206;
    }
    if ( !RxContext->CurrentIrp->RequestorMode
      || (LinkedVNetRoot = -1073741790, SeSinglePrivilegeCheck(SeExports->SeLoadDriverPrivilege, 1)) )
    {
      ConnectionInfo = MRxSmbStartInstance(
                         RxContext,
                         *((_QWORD *)&RxContext->9 + 19),
                         *((unsigned int *)&RxContext->9 + 42));
      goto LABEL_206;
    }
LABEL_207:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        30,
        WPP_c86fdb6c24cc347f0e6836246d5ec6ea_Traceguids,
        (unsigned int)LinkedVNetRoot,
        RxContext->IoStatusBlock.Information);
    }
    return (unsigned int)LinkedVNetRoot;
  }
  if ( v7 <= 0x1403E0 )
  {
    if ( v7 != 1311712 )
    {
      v44 = v7 - 1311656;
      if ( !v44 )
      {
        ConnectionInfo = SmbIeFsctlHandler((__int64)RxContext);
        goto LABEL_206;
      }
      v45 = v44 - 4;
      if ( v45 )
      {
        v46 = v45 - 44;
        if ( v46 )
        {
          if ( v46 == 4 )
          {
            Buffer = RxContext->Create.TransportName.Buffer;
            v48 = 0;
            v58 = 0;
            if ( Buffer )
            {
              LinkedVNetRoot = MRxSmbGetCipherSuiteOrder(Buffer, *((unsigned int *)&RxContext->9 + 43), &v58);
              if ( (int)(LinkedVNetRoot + 0x80000000) < 0 || LinkedVNetRoot == -2147483643 )
                v48 = v58;
              RxContext->InformationToReturn = v48;
            }
            else
            {
              LinkedVNetRoot = -1073741811;
            }
          }
          goto LABEL_207;
        }
        if ( !RxContext->CurrentIrp->RequestorMode
          || (LinkedVNetRoot = -1073741790, SeSinglePrivilegeCheck(SeExports->SeLoadDriverPrivilege, 1)) )
        {
          ConnectionInfo = MRxSmbSetInstanceConfig(
                             RxContext,
                             *((_QWORD *)&RxContext->9 + 19),
                             *((unsigned int *)&RxContext->9 + 42));
          goto LABEL_206;
        }
      }
      else if ( (int)MRxSmbCheckDevFcbXXXControlFileAccess(2u) >= 0
             || (LinkedVNetRoot = -1073741790, SeSinglePrivilegeCheck(SeExports->SeLoadDriverPrivilege, 1)) )
      {
        ConnectionInfo = ProcessWitnessNotification(
                           RxContext,
                           *((_QWORD *)&RxContext->9 + 19),
                           *((unsigned int *)&RxContext->9 + 42));
        goto LABEL_206;
      }
      goto LABEL_207;
    }
    LinkedVNetRoot = MRxSmbUpdateCertificateMappings(RxContext);
    if ( LinkedVNetRoot >= 0 )
      goto LABEL_207;
    v49 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || !BYTE1(WPP_GLOBAL_Control->Timer) )
        goto LABEL_207;
      v50 = 27;
      goto LABEL_134;
    }
    return (unsigned int)LinkedVNetRoot;
  }
  switch ( v7 )
  {
    case 0x1403E4u:
      LinkedVNetRoot = MRxSmbRunScavenger(
                         (_DWORD)RxContext,
                         *((_QWORD *)&RxContext->9 + 19),
                         *((_DWORD *)&RxContext->9 + 42),
                         RxContext->Create.TransportName.Buffer,
                         *((_DWORD *)&RxContext->9 + 43),
                         (__int64)&RxContext->InformationToReturn);
      if ( LinkedVNetRoot >= 0 )
        goto LABEL_207;
      v49 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return (unsigned int)LinkedVNetRoot;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || !BYTE1(WPP_GLOBAL_Control->Timer) )
        goto LABEL_207;
      v50 = 28;
LABEL_134:
      WPP_SF_d(v49->AttachedDevice, v50, WPP_c86fdb6c24cc347f0e6836246d5ec6ea_Traceguids, (unsigned int)LinkedVNetRoot);
      goto LABEL_207;
    case 0x1403E8u:
      if ( RxContext->CurrentIrp->RequestorMode )
      {
        LinkedVNetRoot = -1073741790;
        if ( !SeSinglePrivilegeCheck(SeExports->SeLoadDriverPrivilege, 1) )
          goto LABEL_207;
      }
      LinkedVNetRoot = MRxSmbControlRdma(
                         (_DWORD)RxContext,
                         *((_QWORD *)&RxContext->9 + 19),
                         *((_DWORD *)&RxContext->9 + 42),
                         a4);
      if ( LinkedVNetRoot >= 0 )
        goto LABEL_207;
      v49 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return (unsigned int)LinkedVNetRoot;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || !BYTE1(WPP_GLOBAL_Control->Timer) )
        goto LABEL_207;
      v50 = 29;
      goto LABEL_134;
    case 0x1403ECu:
      v56 = RxContext->CurrentIrp;
      if ( (!v56 || v56->RequestorMode) && !SeSinglePrivilegeCheck(SeExports->SeTcbPrivilege, 1) )
      {
        LinkedVNetRoot = -1073741790;
        if ( !SeSinglePrivilegeCheck(SeExports->SeLoadDriverPrivilege, 1) )
          goto LABEL_207;
      }
      ConnectionInfo = MRxSmbSetCompressionOptions(
                         v9,
                         *((_QWORD *)&RxContext->9 + 19),
                         *((_DWORD *)&RxContext->9 + 42),
                         a4);
      goto LABEL_206;
  }
  if ( v7 != -2146172527 )
    goto LABEL_207;
LABEL_139:
  if ( (PRDBSS_DEVICE_OBJECT)RxContext->NonPagedFcb != MRxSmbDeviceObject )
    goto LABEL_207;
  v51 = IoGetSiloParameters(RxContext->CurrentIrp->Tail.Overlay.CurrentStackLocation->FileObject);
  if ( v51 )
  {
    v52 = PsGetEffectiveServerSilo(*(_QWORD *)(v51 + 8));
    if ( !(unsigned __int8)PsIsHostSilo(v52) )
    {
      if ( v52 )
      {
LABEL_143:
        LinkedVNetRoot = 0;
        goto LABEL_207;
      }
    }
  }
  if ( (int)MRxSmbCheckDevFcbXXXControlFileAccess(2u) < 0 )
  {
LABEL_145:
    LinkedVNetRoot = -1073741790;
    goto LABEL_207;
  }
  if ( WitnessAlreadyStarted )
  {
    WitnessUpcallTerminate();
    WitnessAlreadyStarted = 0;
  }
  v53 = WitnessUpcallInitialize();
  if ( v53 >= 0 )
  {
    WitnessAlreadyStarted = 1;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_c86fdb6c24cc347f0e6836246d5ec6ea_Traceguids, (unsigned int)v53);
  }
  if ( MRxSmbState )
  {
    if ( MRxSmbState != 1 )
    {
      if ( MRxSmbState == 2 )
        LinkedVNetRoot = 0;
      goto LABEL_207;
    }
LABEL_164:
    if ( !v12 )
    {
      LinkedVNetRoot = -1069481981;
      BYTE3(RxContext->RealDevice) = 1;
      goto LABEL_207;
    }
    if ( !v11 )
      __int2c();
    started = RxStartMinirdr(RxContext, (PBOOLEAN)&RxContext->RealDevice + 3);
    LinkedVNetRoot = 0;
    if ( started != -1073741572 )
      LinkedVNetRoot = started;
    if ( (int)StartMailslotMiniRdrInFSP(RxContext) < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_c86fdb6c24cc347f0e6836246d5ec6ea_Traceguids);
    }
    if ( !LinkedVNetRoot )
      LinkedVNetRoot = 0;
    if ( !MRxSmbBootedRemotely || LinkedVNetRoot || v7 != 1311121 )
      goto LABEL_207;
    ConnectionInfo = MRxSmbInitializeSecurity();
LABEL_206:
    LinkedVNetRoot = ConnectionInfo;
    goto LABEL_207;
  }
  if ( pFobx )
    goto LABEL_207;
  if ( v7 != 1311121 )
    MRxSmbBootedRemotely = 1;
  if ( DestinationString.Buffer || (result = SmbCeGetComputerName(), !(_DWORD)result) )
  {
    result = MRxSmbExternalStart(RxContext);
    if ( !(_DWORD)result )
      goto LABEL_164;
  }
  return result;
}

```

## disassembly

```asm
0x14001f0e0  mov     [rsp+arg_18], rbx
0x14001f0e5  push    rbp
0x14001f0e6  push    rsi
0x14001f0e7  push    rdi
0x14001f0e8  push    r13
0x14001f0ea  push    r14
0x14001f0ec  sub     rsp, 40h
0x14001f0f0  mov     rsi, [rcx+40h]
0x14001f0f4  mov     rdi, rcx
0x14001f0f7  movzx   ebx, byte ptr [rcx+20h]
0x14001f0fb  mov     ebp, [rcx+21Ch]
0x14001f101  mov     r14d, [rcx+78h]
0x14001f105  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001f10c  lea     r13, WPP_GLOBAL_Control
0x14001f113  cmp     rcx, r13
0x14001f116  jz      short loc_14001F13A
0x14001f118  mov     eax, [rcx+2Ch]
0x14001f11b  test    al, 2
0x14001f11d  jz      short loc_14001F13A
0x14001f11f  cmp     byte ptr [rcx+29h], 4
0x14001f123  jb      short loc_14001F13A
0x14001f125  mov     rcx, [rcx+18h]
0x14001f129  lea     r8, WPP_c86fdb6c24cc347f0e6836246d5ec6ea_Traceguids
0x14001f130  mov     edx, 18h
0x14001f135  call    WPP_SF_
0x14001f13a  mov     eax, ebx
0x14001f13c  mov     [rsp+68h+arg_8], r12
0x14001f141  mov     [rsp+68h+arg_10], r15
0x14001f149  sub     eax, 0Dh
0x14001f14c  jz      short loc_14001F199
0x14001f14e  sub     eax, 1
0x14001f151  jz      short loc_14001F162
0x14001f153  cmp     eax, 1
0x14001f156  jz      short loc_14001F162
0x14001f158  mov     ebx, 0C0000010h
0x14001f15d  jmp     def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f162  cmp     ebp, 1403F8h
0x14001f168  jz      short loc_14001F174
0x14001f16a  mov     ebx, 0C0000010h
0x14001f16f  jmp     def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f174  cmp     cs:MRxSmbBootedRemotely, 0
0x14001f17b  jz      short loc_14001F18F
0x14001f17d  xor     r14d, r14d
0x14001f180  mov     cs:MRxSmbUseKernelModeSecurity, 1
0x14001f187  mov     ebx, r14d
0x14001f18a  jmp     def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f18f  mov     ebx, 0C0000001h
0x14001f194  jmp     def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f199  cmp     byte ptr [rdi+240h], 0
0x14001f1a0  jz      short loc_14001F1AC
0x14001f1a2  mov     ebx, 0C0000010h
0x14001f1a7  jmp     def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f1ac  cmp     ebp, 1401A7h
0x14001f1b2  jz      loc_14001FE50
0x14001f1b8  cmp     ebp, 1401A3h
0x14001f1be  jz      loc_14001FE32
0x14001f1c4  mov     r12d, r14d
0x14001f1c7  mov     ebx, 0C0000010h
0x14001f1cc  and     r12d, 2
0x14001f1d0  and     r14d, 200h
0x14001f1d7  cmp     ebp, 1403A0h
0x14001f1dd  ja      loc_14001F92E
0x14001f1e3  jz      loc_14001F8E0
0x14001f1e9  lea     eax, [rbp-140191h]; switch 108 cases
0x14001f1ef  cmp     eax, 6Bh
0x14001f1f2  ja      def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f1f8  lea     rdx, cs:140000000h
0x14001f1ff  movzx   eax, ds:(byte_140067894 - 140000000h)[rdx+rax]
0x14001f207  mov     ecx, ds:(jpt_14001F211 - 140000000h)[rdx+rax*4]
0x14001f20e  add     rcx, rdx
0x14001f211  jmp     rcx; switch jump
0x14001f217  mov     rax, cs:MRxSmbDeviceObject; jumptable 000000014001F211 case 1311124
0x14001f21e  cmp     [rdi+50h], rax
0x14001f222  jnz     def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f228  mov     rax, [rdi+28h]
0x14001f22c  mov     rcx, [rax+0B8h]
0x14001f233  mov     rcx, [rcx+30h]
0x14001f237  call    cs:__imp_IoGetSiloParameters
0x14001f23e  nop     dword ptr [rax+rax+00h]
0x14001f243  test    rax, rax
0x14001f246  jz      short loc_14001F27E
0x14001f248  mov     rcx, [rax+8]
0x14001f24c  call    cs:__imp_PsGetEffectiveServerSilo
0x14001f253  nop     dword ptr [rax+rax+00h]
0x14001f258  mov     rcx, rax
0x14001f25b  mov     rbp, rax
0x14001f25e  call    cs:__imp_PsIsHostSilo
0x14001f265  nop     dword ptr [rax+rax+00h]
0x14001f26a  test    al, al
0x14001f26c  jnz     short loc_14001F27E
0x14001f26e  test    rbp, rbp
0x14001f271  jz      short loc_14001F27E
0x14001f273  xor     r14d, r14d
0x14001f276  mov     ebx, r14d
0x14001f279  jmp     def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f27e  mov     ecx, 2; DesiredAccess
0x14001f283  call    MRxSmbCheckDevFcbXXXControlFileAccess
0x14001f288  test    eax, eax
0x14001f28a  jns     short loc_14001F296
0x14001f28c  mov     ebx, 0C0000022h
0x14001f291  jmp     def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f296  test    rsi, rsi
0x14001f299  jnz     def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f29f  cmp     cs:MRxSmbBootedRemotely, sil
0x14001f2a6  jnz     loc_14001FB44
0x14001f2ac  mov     ecx, 3
0x14001f2b1  mov     eax, 2
0x14001f2b6  lock cmpxchg cs:MRxSmbState, ecx
0x14001f2be  mov     edx, eax
0x14001f2c0  mov     rax, [rdi+50h]
0x14001f2c4  mov     rcx, [rax+8]
0x14001f2c8  lea     rax, MRxSmbUnload
0x14001f2cf  mov     [rcx+68h], rax
0x14001f2d3  lea     eax, [rdx-2]
0x14001f2d6  cmp     eax, 1
0x14001f2d9  ja      def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f2df  test    r14d, r14d
0x14001f2e2  jnz     short loc_14001F2F2
0x14001f2e4  mov     ebx, 0C0410003h
0x14001f2e9  mov     byte ptr [rdi+23h], 1
0x14001f2ed  jmp     def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f2f2  test    r12d, r12d
0x14001f2f5  jnz     short loc_14001F2F9
0x14001f2f7  int     2Ch; Windows NT - assertion failure
0x14001f2f9  lea     rdx, [rdi+23h]; PostToFsp
0x14001f2fd  mov     rcx, rdi; RxContext
0x14001f300  call    cs:__imp_RxStopMinirdr
0x14001f307  nop     dword ptr [rax+rax+00h]
0x14001f30c  mov     ebx, eax
0x14001f30e  call    WitnessUpcallTerminate
0x14001f313  test    dword ptr [rdi+78h], 200h
0x14001f31a  mov     cs:WitnessAlreadyStarted, 0
0x14001f321  jz      def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f327  mov     rcx, rdi
0x14001f32a  call    StopMailslotMiniRdrInFSP
0x14001f32f  jmp     def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f334  test    rsi, rsi; jumptable 000000014001F211 case 1311163
0x14001f337  jnz     def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f33d  mov     rcx, rdi
0x14001f340  call    MRxEnumerateTransports
0x14001f345  jmp     loc_14001FE79
0x14001f34a  mov     rcx, rdi; jumptable 000000014001F211 case 1311184
0x14001f34d  call    MRxSmbGetStatistics
0x14001f352  jmp     loc_14001FE79
0x14001f357  mov     ecx, 2; jumptable 000000014001F211 case 1311134
0x14001f35c  call    MRxSmbCheckDevFcbXXXControlFileAccess
0x14001f361  test    eax, eax
0x14001f363  jns     short loc_14001F36F
0x14001f365  mov     ebx, 0C0000022h
0x14001f36a  jmp     def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f36f  mov     rcx, rdi
0x14001f372  call    MRxSmbGetConfigurationInformation
0x14001f377  jmp     loc_14001FE79
0x14001f37c  mov     rax, [rdi+28h]; jumptable 000000014001F211 case 1311129
0x14001f380  mov     rcx, [rax+0B8h]
0x14001f387  mov     rcx, [rcx+30h]
0x14001f38b  call    cs:__imp_IoGetSiloParameters
0x14001f392  nop     dword ptr [rax+rax+00h]
0x14001f397  test    rax, rax
0x14001f39a  jz      short loc_14001F3CB
0x14001f39c  mov     rcx, [rax+8]
0x14001f3a0  call    cs:__imp_PsGetEffectiveServerSilo
0x14001f3a7  nop     dword ptr [rax+rax+00h]
0x14001f3ac  mov     rcx, rax
0x14001f3af  mov     rbx, rax
0x14001f3b2  call    cs:__imp_PsIsHostSilo
0x14001f3b9  nop     dword ptr [rax+rax+00h]
0x14001f3be  test    al, al
0x14001f3c0  jnz     short loc_14001F3CB
0x14001f3c2  test    rbx, rbx
0x14001f3c5  jnz     loc_14001FB5D
0x14001f3cb  mov     ecx, 2; DesiredAccess
0x14001f3d0  call    MRxSmbCheckDevFcbXXXControlFileAccess
0x14001f3d5  test    eax, eax
0x14001f3d7  js      loc_14001FB5D
0x14001f3dd  mov     rcx, rdi
0x14001f3e0  call    MRxSmbSetConfigurationInformation
0x14001f3e5  jmp     loc_14001FE79
0x14001f3ea  test    rsi, rsi; jumptable 000000014001F211 case 1311148
0x14001f3ed  jz      def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f3f3  mov     rdx, [rsi+20h]
0x14001f3f7  mov     rcx, rdi
0x14001f3fa  mov     rdx, [rdx+28h]
0x14001f3fe  call    SmbShellDeleteConnection
0x14001f403  jmp     loc_14001FE79
0x14001f408  mov     rax, [rdi+28h]; jumptable 000000014001F211 case 1311200
0x14001f40c  mov     rcx, [rax+0B8h]
0x14001f413  mov     rcx, [rcx+30h]
0x14001f417  call    cs:__imp_IoGetSiloParameters
0x14001f41e  nop     dword ptr [rax+rax+00h]
0x14001f423  test    rax, rax
0x14001f426  jz      short loc_14001F45E
0x14001f428  mov     rcx, [rax+8]
0x14001f42c  call    cs:__imp_PsGetEffectiveServerSilo
0x14001f433  nop     dword ptr [rax+rax+00h]
0x14001f438  mov     rcx, rax
0x14001f43b  mov     rbx, rax
0x14001f43e  call    cs:__imp_PsIsHostSilo
0x14001f445  nop     dword ptr [rax+rax+00h]
0x14001f44a  test    al, al
0x14001f44c  jnz     short loc_14001F45E
0x14001f44e  test    rbx, rbx
0x14001f451  jz      short loc_14001F45E
0x14001f453  xor     r14d, r14d
0x14001f456  mov     ebx, r14d
0x14001f459  jmp     def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f45e  mov     ecx, 2; DesiredAccess
0x14001f463  call    MRxSmbCheckDevFcbXXXControlFileAccess
0x14001f468  test    eax, eax
0x14001f46a  jns     short loc_14001F476
0x14001f46c  mov     ebx, 0C0000022h
0x14001f471  jmp     def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f476  mov     rcx, rdi
0x14001f479  call    MRxSmbSetDomainName
0x14001f47e  jmp     loc_14001FE79
0x14001f483  mov     rcx, [rdi+28h]; jumptable 000000014001F211 case 1311224
0x14001f487  test    rcx, rcx
0x14001f48a  jz      short loc_14001F49D
0x14001f48c  call    cs:__imp_RxGetSiloFromIrp
0x14001f493  nop     dword ptr [rax+rax+00h]
0x14001f498  mov     r14, rax
0x14001f49b  jmp     short loc_14001F4A0
0x14001f49d  xor     r14d, r14d
0x14001f4a0  mov     rcx, [rdi+50h]
0x14001f4a4  mov     rdx, r14
0x14001f4a7  call    SmbCeGetUnavailableServerListForDeviceSilo
0x14001f4ac  mov     rcx, rax
0x14001f4af  call    SmbCeDiscardUnavailableServerList
0x14001f4b4  mov     rcx, [rdi+50h]
0x14001f4b8  mov     rdx, r14
0x14001f4bb  call    SmbCeGetInvalidAuthEntryListForDeviceSilo
0x14001f4c0  mov     rcx, rax
0x14001f4c3  call    SmbCeDiscardInvalidAuthEntryList
0x14001f4c8  xor     r8d, r8d
0x14001f4cb  mov     dl, 1
0x14001f4cd  xor     ecx, ecx
0x14001f4cf  call    cs:__imp_RxSignalNetStatus
0x14001f4d6  nop     dword ptr [rax+rax+00h]
0x14001f4db  jmp     loc_14001FE79
0x14001f4e0  mov     rax, [rdi+28h]; jumptable 000000014001F211 case 1311204
0x14001f4e4  mov     rcx, [rax+0B8h]
0x14001f4eb  mov     rcx, [rcx+30h]
0x14001f4ef  call    cs:__imp_IoGetSiloParameters
0x14001f4f6  nop     dword ptr [rax+rax+00h]
0x14001f4fb  test    rax, rax
0x14001f4fe  jz      short loc_14001F52F
0x14001f500  mov     rcx, [rax+8]
0x14001f504  call    cs:__imp_PsGetEffectiveServerSilo
0x14001f50b  nop     dword ptr [rax+rax+00h]
0x14001f510  mov     rcx, rax
0x14001f513  mov     rbx, rax
0x14001f516  call    cs:__imp_PsIsHostSilo
0x14001f51d  nop     dword ptr [rax+rax+00h]
0x14001f522  test    al, al
0x14001f524  jnz     short loc_14001F52F
0x14001f526  test    rbx, rbx
0x14001f529  jnz     loc_14001FB5D
0x14001f52f  mov     ecx, 4; DesiredAccess
0x14001f534  call    MRxSmbCheckDevFcbXXXControlFileAccess
0x14001f539  test    eax, eax
0x14001f53b  js      loc_14001FB5D
0x14001f541  mov     rcx, rdi
0x14001f544  call    MRxSmbSetServerGuid
0x14001f549  jmp     loc_14001FE79
0x14001f54e  xorps   xmm0, xmm0; jumptable 000000014001F211 case 1311192
0x14001f551  movups  [rsp+68h+var_38], xmm0
0x14001f556  test    rsi, rsi
0x14001f559  jz      def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f55f  mov     eax, [rdi+238h]
0x14001f565  cmp     eax, 24h ; '$'
0x14001f568  jb      def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f56e  mov     r8, [rdi+228h]
0x14001f575  mov     edx, [r8+14h]
0x14001f579  lea     rcx, [rdx+24h]
0x14001f57d  cmp     rax, rcx
0x14001f580  jb      def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f586  test    dl, 1
0x14001f589  jnz     def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f58f  cmp     edx, 0FFFEh
0x14001f595  jnb     def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f59b  xor     r14d, r14d
0x14001f59e  mov     word ptr [rsp+68h+var_38+2], dx
0x14001f5a3  mov     word ptr [rsp+68h+var_38], dx
0x14001f5a8  mov     qword ptr [rsp+68h+var_38+8], r14
0x14001f5ad  test    dx, dx
0x14001f5b0  jz      short loc_14001F5BB
0x14001f5b2  lea     rax, [r8+18h]
0x14001f5b6  mov     qword ptr [rsp+68h+var_38+8], rax
0x14001f5bb  mov     ecx, [r8]
0x14001f5be  sub     ecx, 3
0x14001f5c1  jz      short loc_14001F5FD
0x14001f5c3  cmp     ecx, 1
0x14001f5c6  jnz     def_14001F211; jumptable 000000014001F211 default case, cases 1311122,1311123,1311125-1311128,1311130-1311133,1311135-1311143,1311145-1311147,1311149-1311151,1311153-1311155,1311157-1311162,1311164-1311183,1311185-1311191,1311193-1311199,1311201-1311203,1311205-1311207,1311209-1311223,1311225-1311227
0x14001f5cc  mov     rdx, [rsi+20h]
0x14001f5d0  lea     r9, [rsp+68h+var_38]
0x14001f5d5  mov     r8d, 0FFh
0x14001f5db  mov     rcx, rdi
0x14001f5de  mov     rdx, [rdx+28h]
0x14001f5e2  call    cs:__imp_RxDeleteLinkedVNetRoot
0x14001f5e9  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
