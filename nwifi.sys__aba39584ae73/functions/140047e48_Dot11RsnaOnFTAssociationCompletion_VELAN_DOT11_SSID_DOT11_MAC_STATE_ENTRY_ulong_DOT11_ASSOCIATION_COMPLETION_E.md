# Dot11RsnaOnFTAssociationCompletion(_VELAN *,_DOT11_SSID *,DOT11_MAC_STATE_ENTRY *,ulong,DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *)

- ea: `0x140047e48`
- end: `0x14004886d`
- name: `?Dot11RsnaOnFTAssociationCompletion@@YAXPEAU_VELAN@@PEAU_DOT11_SSID@@PEAUDOT11_MAC_STATE_ENTRY@@KPEAUDOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS@@@Z`
- size: `2597`
- prototype: `void __fastcall(struct _VELAN *, struct _DOT11_SSID *, struct DOT11_MAC_STATE_ENTRY *, int, struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14005e1fc`

## callees

- `0x14000d21c`
- `0x140018a0c`
- `0x140020dc0`
- `0x14002525c`
- `0x14002f44c`
- `0x140031540`
- `0x14003da34`
- `0x140040680`
- `0x14004215c`
- `0x140047e48`
- `0x1400497d8`
- `0x14004a23c`
- `0x14004a904`
- `0x14004e208`
- `0x14004f550`
- `0x14005012c`
- `0x140050d04`
- `0x140050f84`
- `0x1400513b4`
- `0x140053f88`
- `0x140053fe0`
- `0x140054d70`
- `0x140091124`
- `0x14009bbb0`
- `0x14009bcc0`
- `0x14009bfc0`
- `0x14009c4e0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140047f80`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140047f80`
- `ntoskrnl!ExAllocatePool2` at `0x140047f98`
- `ntoskrnl!ExAllocatePool2` at `0x140047f98`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047fd2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047fd2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047fe3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047fe3`

## pseudocode

```c
void __fastcall Dot11RsnaOnFTAssociationCompletion(
        struct _VELAN *a1,
        struct _DOT11_SSID *a2,
        struct DOT11_MAC_STATE_ENTRY *a3,
        int a4,
        struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *a5)
{
  _NWF_KEY_CONTEXT *p_KeyContext; // rsi
  int v9; // ecx
  __int64 v10; // rax
  unsigned int *v11; // rdi
  unsigned int v12; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  DOT11_CONNECTION_INFO *v15; // rbx
  DOT11_CONNECTION_INFO *pConnectionInfo; // rcx
  ULONG *p_Rssi; // rcx
  unsigned int v18; // eax
  int IsEnabledDeviceUsageNoInline; // eax
  const unsigned __int8 *v20; // r8
  unsigned int v21; // r9d
  struct NWF_FT_CONTEXT *FTContextInformation; // rax
  struct NWF_FT_CONTEXT *v23; // r13
  unsigned int v24; // edx
  __int64 v25; // r8
  NWF_FT_CONTEXT *pFTContext; // rax
  _DEVICE_OBJECT *AttachedDevice; // rcx
  PDEVICE_OBJECT v28; // rcx
  __int64 v29; // rdx
  __int128 v30; // xmm0
  const unsigned __int8 *AuthenticatorDeviceAddress; // r9
  DOT11_CONNECTION_INFO *v32; // rax
  int v33; // edx
  __int64 v34; // rax
  _DEVICE_OBJECT *v35; // rcx
  int v36; // edx
  unsigned int KCKLength; // r9d
  int v38; // ecx
  int FteMicForFTAssociationFrames; // eax
  _DEVICE_OBJECT *v40; // rcx
  __int16 v41; // ax
  _DEVICE_OBJECT *v42; // rcx
  _DEVICE_OBJECT *v43; // rcx
  unsigned __int8 *pFTE_MIC; // rax
  _DEVICE_OBJECT *v45; // rcx
  unsigned int v46; // ecx
  _FILE_OBJECT *pSecurityEndpoint; // rax
  int v48; // r14d
  PDEVICE_OBJECT v49; // rcx
  __int64 v50; // rdx
  unsigned int v51; // edx
  _OWORD *v52; // rax
  __int128 v53; // xmm1
  __int128 v54; // xmm0
  __int128 v55; // xmm1
  __int128 v56; // xmm0
  __int128 v57; // xmm1
  __int128 v58; // xmm0
  size_t Size; // [rsp+20h] [rbp-C1h]
  unsigned __int8 *Sizea; // [rsp+20h] [rbp-C1h]
  unsigned int TKLength; // [rsp+28h] [rbp-B9h]
  size_t v62; // [rsp+28h] [rbp-B9h]
  size_t v63; // [rsp+30h] [rbp-B1h]
  __int64 p_TempPTK; // [rsp+60h] [rbp-81h] BYREF
  char *v65; // [rsp+68h] [rbp-79h]
  __int128 v66; // [rsp+70h] [rbp-71h]
  int v67; // [rsp+80h] [rbp-61h]
  __int128 v68; // [rsp+88h] [rbp-59h] BYREF
  __int128 v69; // [rsp+98h] [rbp-49h]
  struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *v70; // [rsp+A8h] [rbp-39h]
  struct _GUID v71; // [rsp+B0h] [rbp-31h] BYREF
  __int128 v72; // [rsp+C0h] [rbp-21h] BYREF
  __int128 Buf2; // [rsp+D0h] [rbp-11h] BYREF

  p_KeyContext = &a1->KeyContext;
  v67 = a4;
  if ( a1->pSecurityEndpoint != a1->pMSSecurityEndpoint || !a1->KeyContext.bFTAKM || !a1->KeyContext.pFTContext )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 509, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
    v9 = -1073741811;
    goto LABEL_96;
  }
  if ( *((_BYTE *)a5 + 1) < 2u || *((_DWORD *)a5 + 8) < 6u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_DDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        510,
        WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
        *((unsigned __int8 *)a5 + 1),
        *((_DWORD *)a5 + 8),
        *((_DWORD *)a5 + 25),
        *((_DWORD *)a5 + 26));
    goto LABEL_39;
  }
  *(_QWORD *)&v66 = GetActivePmk(a1, a3);
  if ( !(_QWORD)v66 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 512, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
    v9 = -1073741823;
LABEL_96:
    v24 = 294923;
    goto LABEL_97;
  }
  v10 = *((unsigned int *)a5 + 25);
  if ( !(_DWORD)v10 || !*((_DWORD *)a5 + 26) )
  {
    v18 = 0;
    goto LABEL_33;
  }
  v11 = (unsigned int *)((char *)a5 + v10);
  v12 = *(_DWORD *)((char *)a5 + v10) + 16;
  if ( v12 >= 0x10 )
  {
    if ( v12 > 0x40 )
    {
      if ( v12 > 0x100 )
      {
        if ( v12 > 0x400 )
        {
          if ( v12 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v12, 2053731191);
LABEL_23:
            if ( Pool2 )
            {
              *(_QWORD *)Pool2 = p_WaitListHead;
              v15 = (DOT11_CONNECTION_INFO *)(Pool2 + 4);
              Pool2[2] = 2053731191;
              pConnectionInfo = p_KeyContext->pConnectionInfo;
              if ( pConnectionInfo )
              {
                p_Rssi = (ULONG *)&pConnectionInfo[-1].LinkInfo[0].Rssi;
                if ( *(_QWORD *)p_Rssi )
                  ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)p_Rssi, p_Rssi);
                else
                  ExFreePoolWithTag(p_Rssi, p_Rssi[2]);
              }
              p_KeyContext->pConnectionInfo = v15;
              memmove(v15, v11, *v11);
              v18 = v11[2];
LABEL_33:
              p_KeyContext->currentConnectionFlags = v18;
              IsEnabledDeviceUsageNoInline = Feature_Bugfix_53850044__private_IsEnabledDeviceUsageNoInline();
              v20 = (const unsigned __int8 *)a5 + *((unsigned int *)a5 + 7) + 6;
              v21 = *((_DWORD *)a5 + 8) - 6;
              if ( IsEnabledDeviceUsageNoInline )
                FTContextInformation = GetFTContextInformation(a2, 0, v20, v21, 0, 0, 0, 0, 0);
              else
                FTContextInformation = CDRollback_GetFTContextInformation(a2, 0, v20, v21, 0, 0, 0, 0);
              v23 = FTContextInformation;
              if ( !FTContextInformation )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 514, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
LABEL_39:
                v24 = 294928;
                v9 = -1073741811;
LABEL_97:
                CompleteFTAssociationParamsRequest(v9, v24, a1, a3, 0);
                return;
              }
              if ( memcmp(FTContextInformation->PmkR1Name, p_KeyContext->pFTContext->PmkR1Name, 0x10u) )
              {
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  goto LABEL_65;
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 515, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  goto LABEL_65;
                pFTContext = p_KeyContext->pFTContext;
                AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
                *(_QWORD *)&v66 = 16;
                *((_QWORD *)&v66 + 1) = pFTContext->PmkR1Name;
                v72 = v66;
                WPP_SF__HEX_(AttachedDevice, 516, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, &v72);
                v28 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  goto LABEL_65;
                *(_QWORD *)&v66 = 16;
                v29 = 517;
                *((_QWORD *)&v66 + 1) = v23->PmkR1Name;
                v30 = v66;
LABEL_64:
                v45 = v28->AttachedDevice;
                v72 = v30;
                WPP_SF__HEX_(v45, v29, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, &v72);
LABEL_65:
                CompleteFTAssociationParamsRequest(-1073741823, 0x4800Bu, a1, a3, v23);
                return;
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                WPP_SF_dddddddd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  518,
                  v25,
                  (unsigned int)p_KeyContext->AuthAlgo,
                  *((_DWORD *)a5 + 13),
                  p_KeyContext->UcastCipher,
                  *((_DWORD *)a5 + 14),
                  p_KeyContext->McastCipher,
                  *((_DWORD *)a5 + 15),
                  p_KeyContext->McastMgmtCipher,
                  *((_DWORD *)a5 + 22));
              p_KeyContext->AuthAlgo = *((_DWORD *)a5 + 13);
              p_KeyContext->UcastCipher = *((_DWORD *)a5 + 14);
              p_KeyContext->McastCipher = *((_DWORD *)a5 + 15);
              p_KeyContext->McastMgmtCipher = *((_DWORD *)a5 + 22);
              p_KeyContext->KeyDescriptorVersion = 3;
              p_KeyContext->TxReplayCounter = 0;
              if ( (unsigned int)IsMloConnection(p_KeyContext) )
              {
                v32 = p_KeyContext->pConnectionInfo;
                if ( v32 )
                  AuthenticatorDeviceAddress = v32->AuthenticatorDeviceAddress;
              }
              v33 = *((_DWORD *)a5 + 28);
              Buf2 = *(_OWORD *)v23->pFTE_MIC;
              if ( v33 && (v34 = *((unsigned int *)a5 + 27), (_DWORD)v34) )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                {
                  v35 = WPP_GLOBAL_Control->AttachedDevice;
                  p_TempPTK = (unsigned __int16)v33;
                  v65 = (char *)a5 + v34;
                  WPP_SF__HEX_(v35, 519, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, &p_TempPTK);
                }
                v36 = *((_DWORD *)a5 + 28);
                KCKLength = p_KeyContext->TempPTK.KCKLength;
                v38 = (_DWORD)a5 + *((_DWORD *)a5 + 27);
                v72 = 0;
                FteMicForFTAssociationFrames = WL_CMAC_128(v38, v36, (int)p_KeyContext + 1044, KCKLength, (__int64)&v72);
                if ( FteMicForFTAssociationFrames >= 0 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  {
                    v40 = WPP_GLOBAL_Control->AttachedDevice;
                    p_TempPTK = 16;
                    v65 = (char *)&v72;
                    WPP_SF__HEX_(v40, 520, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, &p_TempPTK);
                  }
                  *(_OWORD *)v23->pFTE_MIC = v72;
LABEL_58:
                  p_TempPTK = (__int64)&p_KeyContext->TempPTK;
                  if ( memcmp(v23->pFTE_MIC, &Buf2, 0x10u) )
                  {
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      goto LABEL_65;
                    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 522, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      goto LABEL_65;
                    v41 = *((_WORD *)a5 + 56);
                    v42 = WPP_GLOBAL_Control->AttachedDevice;
                    v72 = 0;
                    LOWORD(v72) = v41;
                    *((_QWORD *)&v72 + 1) = (char *)a5 + *((unsigned int *)a5 + 27);
                    WPP_SF__HEX_(v42, 523, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, &v72);
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      goto LABEL_65;
                    v43 = WPP_GLOBAL_Control->AttachedDevice;
                    *(_QWORD *)&v72 = 16;
                    *((_QWORD *)&v72 + 1) = &Buf2;
                    WPP_SF__HEX_(v43, 524, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, &v72);
                    v28 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      goto LABEL_65;
                    pFTE_MIC = v23->pFTE_MIC;
                    *(_QWORD *)&v72 = 16;
                    v29 = 525;
                    *((_QWORD *)&v72 + 1) = pFTE_MIC;
                    v30 = v72;
                    goto LABEL_64;
                  }
                  if ( a1->pSecurityEndpoint )
                  {
                    v68 = 0;
                    v70 = 0;
                    v69 = 0;
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 526, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
                    v46 = *((_DWORD *)a3 + 10);
                    DWORD2(v68) = *((_DWORD *)a5 + 1);
                    WORD6(v68) = *((_WORD *)a5 + 4);
                    LODWORD(v69) = a3->uSessionId;
                    DWORD1(v69) = (v46 >> 2) & 1;
                    HIDWORD(v69) = v67;
                    pSecurityEndpoint = a1->pSecurityEndpoint;
                    DWORD2(v69) = (v46 >> 3) & 1;
                    LODWORD(v68) = 0;
                    v70 = a5;
                    NwfUpcallMsg(
                      (PIO_CSQ)((char *)pSecurityEndpoint->FsContext + 40),
                      (const struct DOT11_AUTH_UPCALL_REQUEST *)&v68);
                  }
                  TKLength = p_KeyContext->TempPTK.TKLength;
                  Sizea = &p_KeyContext->TempPTK.PTK[p_KeyContext->TempPTK.KCKLength + p_KeyContext->TempPTK.KEKLength];
                  v71 = 0;
                  v48 = InstallPairwiseKeyWrapper(&v71, a1, p_KeyContext, a3, Sizea, TKLength);
                  if ( v48 < 0 )
                  {
                    v49 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    {
LABEL_77:
                      v51 = 294928;
LABEL_78:
                      CompleteFTAssociationParamsRequest(v48, v51, a1, a3, v23);
                      return;
                    }
                    v50 = 527;
LABEL_76:
                    WPP_SF_d(
                      v49->AttachedDevice,
                      v50,
                      WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
                      (unsigned int)v48);
                    goto LABEL_77;
                  }
                  if ( (unsigned int)IsMloConnection(p_KeyContext) && p_KeyContext->pConnectionInfo )
                  {
                    v48 = InstallMloFTGroupKeyWrapper(&v71, a1, p_KeyContext, a3, v23);
                    if ( v48 < 0 )
                    {
                      v49 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                        goto LABEL_77;
                      v50 = 528;
                      goto LABEL_76;
                    }
                  }
                  else
                  {
                    v48 = InstallNonMloFTGroupKeyWrapper(
                            &v71,
                            a1,
                            p_KeyContext,
                            a3,
                            (const struct NWF_RSNA_FT_GTK_SUB_ELEMENT *)v23->pFTE_GTKSubElement,
                            (const struct NWF_RSNA_FT_IGTK_SUB_ELEMENT *)v23->pFTE_IGTKSubElement,
                            (const struct NWF_RSNA_FT_BIGTK_SUB_ELEMENT *)v23->pFTE_BIGTKSubElement);
                    if ( v48 < 0 )
                    {
                      v49 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                        goto LABEL_77;
                      v50 = 529;
                      goto LABEL_76;
                    }
                  }
                  v52 = (_OWORD *)p_TempPTK;
                  p_KeyContext->bCurrentPTKPresent = 1;
                  v53 = v52[1];
                  *(_OWORD *)&p_KeyContext->CurrentPTK.KCKLength = *v52;
                  v54 = v52[2];
                  *(_OWORD *)&p_KeyContext->CurrentPTK.PTK[4] = v53;
                  v55 = v52[3];
                  *(_OWORD *)&p_KeyContext->CurrentPTK.PTK[20] = v54;
                  v56 = v52[4];
                  *(_OWORD *)&p_KeyContext->CurrentPTK.PTK[36] = v55;
                  v57 = v52[5];
                  *(_OWORD *)&p_KeyContext->CurrentPTK.PTK[52] = v56;
                  v58 = *(_OWORD *)((char *)v52 + 92);
                  *(_OWORD *)&p_KeyContext->CurrentPTK.PTK[68] = v57;
                  *(_OWORD *)&p_KeyContext->CurrentPTK.PTK[80] = v58;
                  memset(&p_KeyContext->TempPTK, 0, sizeof(p_KeyContext->TempPTK));
                  p_KeyContext->bTempPTKPresent = 0;
                  *(_OWORD *)p_KeyContext->ANonce = 0;
                  *(_OWORD *)&p_KeyContext->ANonce[16] = 0;
                  *(_OWORD *)p_KeyContext->SNonce = 0;
                  *(_OWORD *)&p_KeyContext->SNonce[16] = 0;
                  memset(&p_KeyContext->NonceCache, 0, sizeof(p_KeyContext->NonceCache));
                  SetRSNASecured(a1, 1);
                  NotifySecureConnectionChange(a1);
                  p_KeyContext->bAccept1XPacket = 1;
                  if ( (unsigned int)Feature_Bugfix_58508574__private_IsEnabledDeviceUsageNoInline() )
                  {
                    p_KeyContext->associatedAkm = rsna_akm_ft_1x_sha256;
                    a1->Dot11PmkCache.associatedAkm = rsna_akm_ft_1x_sha256;
                    if ( a1->KeyContext.pOpPmk )
                    {
                      LODWORD(v62) = 0;
                      PmkCacheFinalizeOn4WayCompletion(
                        &a1->Dot11PmkCache,
                        (__int64)a1->CurrentAddress,
                        v62,
                        0,
                        v66 + 24);
                    }
                  }
                  v51 = 0;
                  goto LABEL_78;
                }
              }
              else
              {
                LODWORD(v63) = 0;
                LODWORD(Size) = 0;
                FteMicForFTAssociationFrames = GenerateFteMicForFTAssociationFrames(
                                                 v23,
                                                 6,
                                                 a1->CurrentAddress,
                                                 AuthenticatorDeviceAddress,
                                                 Size,
                                                 0,
                                                 v63,
                                                 0,
                                                 p_KeyContext->TempPTK.KCKLength,
                                                 p_KeyContext->TempPTK.PTK);
                if ( FteMicForFTAssociationFrames >= 0 )
                  goto LABEL_58;
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  521,
                  WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
                  (unsigned int)FteMicForFTAssociationFrames);
              goto LABEL_65;
            }
            goto LABEL_29;
          }
          p_WaitListHead = &stru_1400B31C0;
        }
        else
        {
          p_WaitListHead = &Lookaside;
        }
      }
      else
      {
        p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    Pool2 = ExAllocateFromNPagedLookasideList(p_WaitListHead);
    goto LABEL_23;
  }
LABEL_29:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 513, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, *v11);
  CompleteFTAssociationParamsRequest(-1073741670, 0x38009u, a1, a3, 0);
}

```

## disassembly

```asm
0x140047e48  push    rbp
0x140047e4a  push    rbx
0x140047e4b  push    rsi
0x140047e4c  push    rdi
0x140047e4d  push    r12
0x140047e4f  push    r13
0x140047e51  push    r14
0x140047e53  push    r15
0x140047e55  lea     rbp, [rsp-17h]
0x140047e5a  sub     rsp, 0F8h
0x140047e61  mov     rax, cs:__security_cookie
0x140047e68  xor     rax, rsp
0x140047e6b  mov     [rbp+4Fh+var_50], rax
0x140047e6f  mov     r14, [rbp+4Fh+arg_20]
0x140047e73  lea     rsi, [rcx+1710h]
0x140047e7a  mov     [rbp+4Fh+var_B0], r9d
0x140047e7e  mov     r12, r8
0x140047e81  mov     r8, [rcx+16F0h]
0x140047e88  xor     edi, edi
0x140047e8a  mov     r9, [rcx+1700h]
0x140047e91  mov     r13, rdx
0x140047e94  mov     r15, rcx
0x140047e97  cmp     r9, r8
0x140047e9a  jnz     loc_1400487FB
0x140047ea0  cmp     [rsi+508h], edi
0x140047ea6  jz      loc_1400487FB
0x140047eac  cmp     [rsi+510h], rdi
0x140047eb3  jz      loc_1400487FB
0x140047eb9  movzx   eax, byte ptr [r14+1]
0x140047ebe  cmp     al, 2
0x140047ec0  jb      loc_1400487AF
0x140047ec6  cmp     dword ptr [r14+20h], 6
0x140047ecb  jb      loc_1400487AF
0x140047ed1  mov     rdx, r12
0x140047ed4  call    GetActivePmk
0x140047ed9  mov     qword ptr [rbp+4Fh+var_C0], rax
0x140047edd  test    rax, rax
0x140047ee0  jnz     short loc_140047F14
0x140047ee2  mov     rcx, cs:WPP_GLOBAL_Control
0x140047ee9  lea     rbx, WPP_GLOBAL_Control
0x140047ef0  cmp     rcx, rbx
0x140047ef3  jz      short loc_140047F0A
0x140047ef5  mov     rcx, [rcx+18h]
0x140047ef9  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x140047f00  mov     edx, 200h
0x140047f05  call    WPP_SF_
0x140047f0a  mov     ecx, 0C0000001h
0x140047f0f  jmp     loc_140048837
0x140047f14  mov     eax, [r14+64h]
0x140047f18  mov     ebx, 10h
0x140047f1d  test    eax, eax
0x140047f1f  jz      loc_14004804E
0x140047f25  cmp     [r14+68h], edi
0x140047f29  jbe     loc_14004804E
0x140047f2f  lea     rdi, [r14+rax]
0x140047f33  mov     eax, [rdi]
0x140047f35  add     eax, ebx
0x140047f37  cmp     eax, ebx
0x140047f39  jb      loc_14004800B
0x140047f3f  lea     ecx, [rbx+30h]
0x140047f42  cmp     eax, ecx
0x140047f44  ja      short loc_140047F4F
0x140047f46  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140047f4d  jmp     short loc_140047F7D
0x140047f4f  cmp     eax, 100h
0x140047f54  ja      short loc_140047F5F
0x140047f56  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140047f5d  jmp     short loc_140047F7D
0x140047f5f  cmp     eax, 400h
0x140047f64  ja      short loc_140047F6F
0x140047f66  lea     rbx, Lookaside
0x140047f6d  jmp     short loc_140047F7D
0x140047f6f  cmp     eax, 800h
0x140047f74  ja      short loc_140047F8E
0x140047f76  lea     rbx, stru_1400B31C0
0x140047f7d  mov     rcx, rbx; Lookaside
0x140047f80  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140047f87  nop     dword ptr [rax+rax+00h]
0x140047f8c  jmp     short loc_140047FA4
0x140047f8e  xor     ebx, ebx
0x140047f90  mov     edx, eax
0x140047f92  mov     r8d, 7A697377h
0x140047f98  call    cs:__imp_ExAllocatePool2
0x140047f9f  nop     dword ptr [rax+rax+00h]
0x140047fa4  test    rax, rax
0x140047fa7  jz      short loc_14004800B
0x140047fa9  mov     [rax], rbx
0x140047fac  lea     rbx, [rax+10h]
0x140047fb0  mov     dword ptr [rax+8], 7A697377h
0x140047fb7  mov     rcx, [rsi+58h]
0x140047fbb  test    rcx, rcx
0x140047fbe  jz      short loc_140047FEF
0x140047fc0  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140047fc4  mov     rax, [rcx]
0x140047fc7  test    rax, rax
0x140047fca  jz      short loc_140047FE0
0x140047fcc  mov     rdx, rcx; Entry
0x140047fcf  mov     rcx, rax; Lookaside
0x140047fd2  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047fd9  nop     dword ptr [rax+rax+00h]
0x140047fde  jmp     short loc_140047FEF
0x140047fe0  mov     edx, [rcx+8]; Tag
0x140047fe3  call    cs:__imp_ExFreePoolWithTag
0x140047fea  nop     dword ptr [rax+rax+00h]
0x140047fef  mov     [rsi+58h], rbx
0x140047ff3  mov     rdx, rdi; Src
0x140047ff6  mov     r8d, [rdi]; Size
0x140047ff9  mov     rcx, rbx; void *
0x140047ffc  call    memmove
0x140048001  mov     eax, [rdi+8]
0x140048004  xor     edi, edi
0x140048006  lea     ebx, [rdi+10h]
0x140048009  jmp     short loc_140048050
0x14004800b  mov     rcx, cs:WPP_GLOBAL_Control
0x140048012  lea     rbx, WPP_GLOBAL_Control
0x140048019  cmp     rcx, rbx
0x14004801c  jz      short loc_140048036
0x14004801e  mov     r9d, [rdi]
0x140048021  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x140048028  mov     rcx, [rcx+18h]
0x14004802c  mov     edx, 201h
0x140048031  call    WPP_SF_d
0x140048036  mov     [rsp+130h+Size], 0
0x14004803f  mov     edx, 38009h
0x140048044  mov     ecx, 0C000009Ah
0x140048049  jmp     loc_140048841
0x14004804e  mov     eax, edi
0x140048050  mov     [rsi+518h], eax
0x140048056  call    Feature_Bugfix_53850044__private_IsEnabledDeviceUsageNoInline
0x14004805b  mov     r8d, [r14+1Ch]
0x14004805f  xor     edx, edx; int
0x140048061  mov     r9d, [r14+20h]
0x140048065  add     r8, 6
0x140048069  add     r8, r14; unsigned __int8 *
0x14004806c  add     r9d, 0FFFFFFFAh; unsigned int
0x140048070  mov     rcx, r13; struct _DOT11_SSID *
0x140048073  test    eax, eax
0x140048075  jz      short loc_140048094
0x140048077  mov     [rsp+130h+var_F0], edi; unsigned int
0x14004807b  mov     dword ptr [rsp+130h+var_F8], edi; unsigned int
0x14004807f  mov     [rsp+130h+var_100], rdi; unsigned __int8 *
0x140048084  mov     dword ptr [rsp+130h+var_108], edi; unsigned int
0x140048088  mov     [rsp+130h+Size], rdi; unsigned __int8 *
0x14004808d  call    ?GetFTContextInformation@@YAPEAUNWF_FT_CONTEXT@@PEBU_DOT11_SSID@@HPEBEK1K1KK@Z; GetFTContextInformation(_DOT11_SSID const *,int,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,ulong)
0x140048092  jmp     short loc_1400480AB
0x140048094  mov     dword ptr [rsp+130h+var_F8], edi; unsigned int
0x140048098  mov     [rsp+130h+var_100], rdi; unsigned __int8 *
0x14004809d  mov     dword ptr [rsp+130h+var_108], edi; unsigned int
0x1400480a1  mov     [rsp+130h+Size], rdi; unsigned __int8 *
0x1400480a6  call    ?CDRollback_GetFTContextInformation@@YAPEAUNWF_FT_CONTEXT@@PEBU_DOT11_SSID@@HPEBEK1K1K@Z; CDRollback_GetFTContextInformation(_DOT11_SSID const *,int,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong)
0x1400480ab  mov     r13, rax
0x1400480ae  test    rax, rax
0x1400480b1  jnz     short loc_1400480EC
0x1400480b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400480ba  lea     rbx, WPP_GLOBAL_Control
0x1400480c1  cmp     rcx, rbx
0x1400480c4  jz      short loc_1400480DD
0x1400480c6  mov     rcx, [rcx+18h]
0x1400480ca  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x1400480d1  mov     edx, 202h
0x1400480d6  call    WPP_SF_
0x1400480db  xor     edi, edi
0x1400480dd  mov     edx, 48010h
0x1400480e2  mov     ecx, 0C000000Dh
0x1400480e7  jmp     loc_14004883C
0x1400480ec  mov     rdx, [rsi+510h]
0x1400480f3  lea     rcx, [r13+78h]; Buf1
0x1400480f7  add     rdx, 78h ; 'x'; Buf2
0x1400480fb  mov     r8, rbx; Size
0x1400480fe  call    memcmp
0x140048103  test    eax, eax
0x140048105  jz      loc_1400481BB
0x14004810b  mov     rcx, cs:WPP_GLOBAL_Control
0x140048112  lea     rbx, WPP_GLOBAL_Control
0x140048119  cmp     rcx, rbx
0x14004811c  jz      loc_14004846F
0x140048122  mov     rcx, [rcx+18h]
0x140048126  lea     rdi, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004812d  mov     r8, rdi
0x140048130  mov     edx, 203h
0x140048135  call    WPP_SF_
0x14004813a  mov     rcx, cs:WPP_GLOBAL_Control
0x140048141  cmp     rcx, rbx
0x140048144  jz      loc_14004846F
0x14004814a  mov     rax, [rsi+510h]
0x140048151  lea     r9, [rbp+4Fh+var_70]
0x140048155  mov     rcx, [rcx+18h]
0x140048159  xorps   xmm0, xmm0
0x14004815c  movups  [rbp+4Fh+var_C0], xmm0
0x140048160  add     rax, 78h ; 'x'
0x140048164  mov     r14d, 10h
0x14004816a  mov     qword ptr [rbp+4Fh+var_C0+8], rax
0x14004816e  mov     edx, 204h
0x140048173  mov     word ptr [rbp+4Fh+var_C0], r14w
0x140048178  mov     r8, rdi
0x14004817b  movaps  xmm0, [rbp+4Fh+var_C0]
0x14004817f  movdqa  [rbp+4Fh+var_70], xmm0
0x140048184  call    WPP_SF__HEX_
0x140048189  mov     rcx, cs:WPP_GLOBAL_Control
0x140048190  cmp     rcx, rbx
0x140048193  jz      loc_14004846F
0x140048199  xorps   xmm0, xmm0
0x14004819c  lea     rax, [r13+78h]
0x1400481a0  movups  [rbp+4Fh+var_C0], xmm0
0x1400481a4  mov     word ptr [rbp+4Fh+var_C0], r14w
0x1400481a9  mov     edx, 205h
0x1400481ae  mov     qword ptr [rbp+4Fh+var_C0+8], rax
0x1400481b2  movaps  xmm0, [rbp+4Fh+var_C0]
0x1400481b6  jmp     loc_14004845A
0x1400481bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400481c2  lea     rbx, WPP_GLOBAL_Control
0x1400481c9  cmp     rcx, rbx
0x1400481cc  jz      short loc_140048215
0x1400481ce  mov     eax, [r14+58h]
0x1400481d2  mov     edx, 206h
0x1400481d7  mov     r9d, [rsi+0Ch]
0x1400481db  mov     rcx, [rcx+18h]
0x1400481df  mov     [rsp+130h+var_E0], eax
0x1400481e3  mov     eax, [rsi+18h]
0x1400481e6  mov     dword ptr [rsp+130h+var_E8], eax
0x1400481ea  mov     eax, [r14+3Ch]
0x1400481ee  mov     [rsp+130h+var_F0], eax
0x1400481f2  mov     eax, [rsi+14h]
0x1400481f5  mov     dword ptr [rsp+130h+var_F8], eax
0x1400481f9  mov     eax, [r14+38h]
0x1400481fd  mov     dword ptr [rsp+130h+var_100], eax
0x140048201  mov     eax, [rsi+10h]
0x140048204  mov     dword ptr [rsp+130h+var_108], eax
0x140048208  mov     eax, [r14+34h]
0x14004820c  mov     dword ptr [rsp+130h+Size], eax
0x140048210  call    WPP_SF_dddddddd
0x140048215  mov     eax, [r14+34h]
0x140048219  lea     r9, [r14+4]
0x14004821d  mov     [rsi+0Ch], eax
0x140048220  mov     rcx, rsi; struct _NWF_KEY_CONTEXT *
0x140048223  mov     eax, [r14+38h]
0x140048227  mov     [rsi+10h], eax
0x14004822a  mov     eax, [r14+3Ch]
0x14004822e  mov     [rsi+14h], eax
0x140048231  mov     eax, [r14+58h]
0x140048235  mov     [rsi+18h], eax
0x140048238  mov     byte ptr [rsi+4E4h], 3
0x14004823f  mov     [rsi+110h], rdi
0x140048246  call    ?IsMloConnection@@YAHPEAU_NWF_KEY_CONTEXT@@@Z; IsMloConnection(_NWF_KEY_CONTEXT *)
0x14004824b  test    eax, eax
0x14004824d  jz      short loc_14004825C
0x14004824f  mov     rax, [rsi+58h]
0x140048253  test    rax, rax
0x140048256  jz      short loc_14004825C
0x140048258  lea     r9, [rax+62h]; unsigned __int8 *
0x14004825c  mov     rax, [r13+98h]
0x140048263  lea     rdi, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004826a  mov     edx, [r14+70h]
0x14004826e  xor     ecx, ecx
0x140048270  movups  xmm0, xmmword ptr [rax]
0x140048273  movdqu  [rbp+4Fh+Buf2], xmm0
0x140048278  test    edx, edx
0x14004827a  jz      loc_140048483
0x140048280  mov     eax, [r14+6Ch]
0x140048284  test    eax, eax
0x140048286  jz      loc_140048483
0x14004828c  mov     rcx, cs:WPP_GLOBAL_Control
0x140048293  cmp     rcx, rbx
0x140048296  jz      short loc_1400482CD
0x140048298  mov     rcx, [rcx+18h]
0x14004829c  lea     r9, [rsp+130h+var_D0]
0x1400482a1  xorps   xmm0, xmm0
0x1400482a4  add     rax, r14
0x1400482a7  movups  [rsp+130h+var_D0], xmm0
0x1400482ac  mov     word ptr [rsp+130h+var_D0], dx
0x1400482b1  mov     r8, rdi
0x1400482b4  mov     qword ptr [rbp+4Fh+var_D0+8], rax
0x1400482b8  mov     edx, 207h
0x1400482bd  movaps  xmm0, [rsp+130h+var_D0]
0x1400482c2  movdqa  [rsp+130h+var_D0], xmm0
0x1400482c8  call    WPP_SF__HEX_
0x1400482cd  mov     ecx, [r14+6Ch]
0x1400482d1  lea     rdx, [rbp+4Fh+var_70]
0x1400482d5  lea     rax, [rsi+408h]
0x1400482dc  mov     [rsp+130h+Size], rdx
0x1400482e1  mov     edx, [r14+70h]
0x1400482e5  lea     r8, [rax+0Ch]
0x1400482e9  mov     r9d, [rax]
0x1400482ec  xorps   xmm0, xmm0
0x1400482ef  add     rcx, r14
0x1400482f2  movups  [rbp+4Fh+var_70], xmm0
0x1400482f6  call    WL_CMAC_128
0x1400482fb  test    eax, eax
0x1400482fd  js      loc_1400484C4
0x140048303  mov     rcx, cs:WPP_GLOBAL_Control
0x14004830a  cmp     rcx, rbx
0x14004830d  jz      short loc_14004834A
0x14004830f  mov     rcx, [rcx+18h]
0x140048313  lea     r9, [rsp+130h+var_D0]
0x140048318  xorps   xmm0, xmm0
0x14004831b  mov     eax, 10h
0x140048320  movups  [rsp+130h+var_D0], xmm0
0x140048325  mov     word ptr [rsp+130h+var_D0], ax
0x14004832a  mov     edx, 208h
0x14004832f  lea     rax, [rbp+4Fh+var_70]
  ... truncated ...
```
