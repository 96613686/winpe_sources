# Dot11RsnaOnFTAssociationCompletion(_VELAN *,_DOT11_SSID *,DOT11_MAC_STATE_ENTRY *,ulong,DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *)

- ea: `0x140046bf0`
- end: `0x1400475f3`
- name: `?Dot11RsnaOnFTAssociationCompletion@@YAXPEAU_VELAN@@PEAU_DOT11_SSID@@PEAUDOT11_MAC_STATE_ENTRY@@KPEAUDOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS@@@Z`
- size: `2563`
- prototype: `void __usercall(struct _VELAN *@<rcx>, struct _DOT11_SSID *@<rdx>, struct DOT11_MAC_STATE_ENTRY *@<r8>, unsigned int@<r9d>, struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14005c9dc`

## callees

- `0x14000d22c`
- `0x140018a0c`
- `0x140020dc0`
- `0x14002f1bc`
- `0x1400312b0`
- `0x14003d814`
- `0x1400416c0`
- `0x140046bf0`
- `0x140048550`
- `0x140048fb4`
- `0x14004967c`
- `0x14004ca48`
- `0x14004dd90`
- `0x14004e96c`
- `0x14004f53c`
- `0x14004f7bc`
- `0x14004fbec`
- `0x1400527c0`
- `0x140053550`
- `0x14008e068`
- `0x14008f944`
- `0x14009a3d0`
- `0x14009a4c0`
- `0x14009a7c0`
- `0x14009ace0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140046d28`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140046d28`
- `ntoskrnl!ExAllocatePool2` at `0x140046d40`
- `ntoskrnl!ExAllocatePool2` at `0x140046d40`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046d7a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046d7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046d8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046d8b`

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
  __int64 v9; // r9
  int v10; // ecx
  __int64 v11; // rax
  unsigned int *v12; // rdi
  unsigned int v13; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  DOT11_CONNECTION_INFO *v16; // rbx
  DOT11_CONNECTION_INFO *pConnectionInfo; // rcx
  ULONG *p_Rssi; // rcx
  unsigned int v19; // eax
  struct NWF_FT_CONTEXT *FTContextInformation; // rax
  struct NWF_FT_CONTEXT *v21; // r12
  unsigned int v22; // edx
  __int64 v23; // rdx
  __int64 v24; // r8
  NWF_FT_CONTEXT *pFTContext; // rax
  _DEVICE_OBJECT *AttachedDevice; // rcx
  PDEVICE_OBJECT v27; // rcx
  __int64 v28; // rdx
  __int128 v29; // xmm0
  const unsigned __int8 *AuthenticatorDeviceAddress; // r9
  DOT11_CONNECTION_INFO *v31; // rax
  int v32; // edx
  __int64 v33; // rax
  _DEVICE_OBJECT *v34; // rcx
  int v35; // edx
  unsigned int KCKLength; // r9d
  int v37; // ecx
  int FteMicForFTAssociationFrames; // eax
  _DEVICE_OBJECT *v39; // rcx
  __int16 v40; // ax
  _DEVICE_OBJECT *v41; // rcx
  _DEVICE_OBJECT *v42; // rcx
  unsigned __int8 *pFTE_MIC; // rax
  _DEVICE_OBJECT *v44; // rcx
  unsigned int v45; // ecx
  _FILE_OBJECT *pSecurityEndpoint; // rax
  int v47; // r14d
  PDEVICE_OBJECT v48; // rcx
  __int64 v49; // rdx
  unsigned int v50; // edx
  _OWORD *v51; // rax
  __int128 v52; // xmm1
  __int128 v53; // xmm0
  __int128 v54; // xmm1
  __int128 v55; // xmm0
  __int128 v56; // xmm1
  __int128 v57; // xmm0
  size_t Size; // [rsp+20h] [rbp-C1h]
  unsigned __int8 *Sizea; // [rsp+20h] [rbp-C1h]
  unsigned int TKLength; // [rsp+28h] [rbp-B9h]
  size_t v61; // [rsp+28h] [rbp-B9h]
  size_t v62; // [rsp+30h] [rbp-B1h]
  __int64 p_TempPTK; // [rsp+60h] [rbp-81h] BYREF
  char *v64; // [rsp+68h] [rbp-79h]
  __int128 v65; // [rsp+70h] [rbp-71h]
  int v66; // [rsp+80h] [rbp-61h]
  __int128 v67; // [rsp+88h] [rbp-59h] BYREF
  __int128 v68; // [rsp+98h] [rbp-49h]
  struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *v69; // [rsp+A8h] [rbp-39h]
  struct _GUID v70; // [rsp+B0h] [rbp-31h] BYREF
  __int128 v71; // [rsp+C0h] [rbp-21h] BYREF
  __int128 Buf2; // [rsp+D0h] [rbp-11h] BYREF

  p_KeyContext = &a1->KeyContext;
  v66 = a4;
  if ( a1->pSecurityEndpoint != a1->pMSSecurityEndpoint || !a1->KeyContext.bFTAKM || !a1->KeyContext.pFTContext )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 490, WPP_e90d411d816e312466897e39e745b158_Traceguids);
    v10 = -1073741811;
    goto LABEL_93;
  }
  if ( *((_BYTE *)a5 + 1) < 2u || *((_DWORD *)a5 + 8) < 6u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_DDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        491,
        WPP_e90d411d816e312466897e39e745b158_Traceguids,
        *((unsigned __int8 *)a5 + 1),
        *((_DWORD *)a5 + 8),
        *((_DWORD *)a5 + 25),
        *((_DWORD *)a5 + 26));
    goto LABEL_36;
  }
  *(_QWORD *)&v65 = GetActivePmk(a1, a3);
  if ( !(_QWORD)v65 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 493, WPP_e90d411d816e312466897e39e745b158_Traceguids);
    v10 = -1073741823;
LABEL_93:
    v22 = 294923;
    goto LABEL_94;
  }
  v11 = *((unsigned int *)a5 + 25);
  if ( !(_DWORD)v11 || !*((_DWORD *)a5 + 26) )
  {
    v19 = 0;
    goto LABEL_33;
  }
  v12 = (unsigned int *)((char *)a5 + v11);
  v13 = *(_DWORD *)((char *)a5 + v11) + 16;
  if ( v13 >= 0x10 )
  {
    if ( v13 > 0x40 )
    {
      if ( v13 > 0x100 )
      {
        if ( v13 > 0x400 )
        {
          if ( v13 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v13, 2053731191, v9);
LABEL_23:
            if ( Pool2 )
            {
              *(_QWORD *)Pool2 = p_WaitListHead;
              v16 = (DOT11_CONNECTION_INFO *)(Pool2 + 4);
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
              p_KeyContext->pConnectionInfo = v16;
              memmove(v16, v12, *v12);
              v19 = v12[2];
LABEL_33:
              p_KeyContext->currentConnectionFlags = v19;
              FTContextInformation = GetFTContextInformation(
                                       a2,
                                       0,
                                       (const unsigned __int8 *)a5 + *((unsigned int *)a5 + 7) + 6,
                                       *((_DWORD *)a5 + 8) - 6,
                                       0,
                                       0,
                                       0,
                                       0,
                                       0);
              v21 = FTContextInformation;
              if ( !FTContextInformation )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 495, WPP_e90d411d816e312466897e39e745b158_Traceguids);
LABEL_36:
                v22 = 294928;
                v10 = -1073741811;
LABEL_94:
                CompleteFTAssociationParamsRequest(v10, v22, a1, a3, 0);
                return;
              }
              if ( memcmp(FTContextInformation->PmkR1Name, p_KeyContext->pFTContext->PmkR1Name, 0x10u) )
              {
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  goto LABEL_62;
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 496, WPP_e90d411d816e312466897e39e745b158_Traceguids);
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  goto LABEL_62;
                pFTContext = p_KeyContext->pFTContext;
                AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
                *(_QWORD *)&v65 = 16;
                *((_QWORD *)&v65 + 1) = pFTContext->PmkR1Name;
                v71 = v65;
                WPP_SF__HEX_(AttachedDevice, 497, WPP_e90d411d816e312466897e39e745b158_Traceguids, &v71);
                v27 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  goto LABEL_62;
                *(_QWORD *)&v65 = 16;
                v28 = 498;
                *((_QWORD *)&v65 + 1) = v21->PmkR1Name;
                v29 = v65;
LABEL_61:
                v44 = v27->AttachedDevice;
                v71 = v29;
                WPP_SF__HEX_(v44, v28, WPP_e90d411d816e312466897e39e745b158_Traceguids, &v71);
LABEL_62:
                CompleteFTAssociationParamsRequest(-1073741823, 0x4800Bu, a1, a3, v21);
                return;
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                WPP_SF_dddddddd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  v23,
                  v24,
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
                v31 = p_KeyContext->pConnectionInfo;
                if ( v31 )
                  AuthenticatorDeviceAddress = v31->AuthenticatorDeviceAddress;
              }
              v32 = *((_DWORD *)a5 + 28);
              Buf2 = *(_OWORD *)v21->pFTE_MIC;
              if ( v32 && (v33 = *((unsigned int *)a5 + 27), (_DWORD)v33) )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                {
                  v34 = WPP_GLOBAL_Control->AttachedDevice;
                  p_TempPTK = (unsigned __int16)v32;
                  v64 = (char *)a5 + v33;
                  WPP_SF__HEX_(v34, 500, WPP_e90d411d816e312466897e39e745b158_Traceguids, &p_TempPTK);
                }
                v35 = *((_DWORD *)a5 + 28);
                KCKLength = p_KeyContext->TempPTK.KCKLength;
                v37 = (_DWORD)a5 + *((_DWORD *)a5 + 27);
                v71 = 0;
                FteMicForFTAssociationFrames = WL_CMAC_128(v37, v35, (int)p_KeyContext + 1044, KCKLength, (__int64)&v71);
                if ( FteMicForFTAssociationFrames >= 0 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  {
                    v39 = WPP_GLOBAL_Control->AttachedDevice;
                    p_TempPTK = 16;
                    v64 = (char *)&v71;
                    WPP_SF__HEX_(v39, 501, WPP_e90d411d816e312466897e39e745b158_Traceguids, &p_TempPTK);
                  }
                  *(_OWORD *)v21->pFTE_MIC = v71;
LABEL_55:
                  p_TempPTK = (__int64)&p_KeyContext->TempPTK;
                  if ( memcmp(v21->pFTE_MIC, &Buf2, 0x10u) )
                  {
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      goto LABEL_62;
                    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 503, WPP_e90d411d816e312466897e39e745b158_Traceguids);
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      goto LABEL_62;
                    v40 = *((_WORD *)a5 + 56);
                    v41 = WPP_GLOBAL_Control->AttachedDevice;
                    v71 = 0;
                    LOWORD(v71) = v40;
                    *((_QWORD *)&v71 + 1) = (char *)a5 + *((unsigned int *)a5 + 27);
                    WPP_SF__HEX_(v41, 504, WPP_e90d411d816e312466897e39e745b158_Traceguids, &v71);
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      goto LABEL_62;
                    v42 = WPP_GLOBAL_Control->AttachedDevice;
                    *(_QWORD *)&v71 = 16;
                    *((_QWORD *)&v71 + 1) = &Buf2;
                    WPP_SF__HEX_(v42, 505, WPP_e90d411d816e312466897e39e745b158_Traceguids, &v71);
                    v27 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      goto LABEL_62;
                    pFTE_MIC = v21->pFTE_MIC;
                    *(_QWORD *)&v71 = 16;
                    v28 = 506;
                    *((_QWORD *)&v71 + 1) = pFTE_MIC;
                    v29 = v71;
                    goto LABEL_61;
                  }
                  if ( a1->pSecurityEndpoint )
                  {
                    v67 = 0;
                    v69 = 0;
                    v68 = 0;
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 507, WPP_e90d411d816e312466897e39e745b158_Traceguids);
                    v45 = *((_DWORD *)a3 + 10);
                    DWORD2(v67) = *((_DWORD *)a5 + 1);
                    WORD6(v67) = *((_WORD *)a5 + 4);
                    LODWORD(v68) = a3->uSessionId;
                    DWORD1(v68) = (v45 >> 2) & 1;
                    HIDWORD(v68) = v66;
                    pSecurityEndpoint = a1->pSecurityEndpoint;
                    DWORD2(v68) = (v45 >> 3) & 1;
                    LODWORD(v67) = 0;
                    v69 = a5;
                    NwfUpcallMsg(
                      (PIO_CSQ)((char *)pSecurityEndpoint->FsContext + 40),
                      (const struct DOT11_AUTH_UPCALL_REQUEST *)&v67);
                  }
                  TKLength = p_KeyContext->TempPTK.TKLength;
                  Sizea = &p_KeyContext->TempPTK.PTK[p_KeyContext->TempPTK.KCKLength + p_KeyContext->TempPTK.KEKLength];
                  v70 = 0;
                  v47 = InstallPairwiseKeyWrapper(&v70, a1, p_KeyContext, a3, Sizea, TKLength);
                  if ( v47 < 0 )
                  {
                    v48 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    {
LABEL_74:
                      v50 = 294928;
LABEL_75:
                      CompleteFTAssociationParamsRequest(v47, v50, a1, a3, v21);
                      return;
                    }
                    v49 = 508;
LABEL_73:
                    WPP_SF_d(
                      v48->AttachedDevice,
                      v49,
                      WPP_e90d411d816e312466897e39e745b158_Traceguids,
                      (unsigned int)v47);
                    goto LABEL_74;
                  }
                  if ( (unsigned int)IsMloConnection(p_KeyContext) && p_KeyContext->pConnectionInfo )
                  {
                    v47 = InstallMloFTGroupKeyWrapper(&v70, a1, p_KeyContext, a3, v21);
                    if ( v47 < 0 )
                    {
                      v48 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                        goto LABEL_74;
                      v49 = 509;
                      goto LABEL_73;
                    }
                  }
                  else
                  {
                    v47 = InstallNonMloFTGroupKeyWrapper(
                            &v70,
                            a1,
                            p_KeyContext,
                            a3,
                            (const struct NWF_RSNA_FT_GTK_SUB_ELEMENT *)v21->pFTE_GTKSubElement,
                            (const struct NWF_RSNA_FT_IGTK_SUB_ELEMENT *)v21->pFTE_IGTKSubElement,
                            (const struct NWF_RSNA_FT_BIGTK_SUB_ELEMENT *)v21->pFTE_BIGTKSubElement);
                    if ( v47 < 0 )
                    {
                      v48 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                        goto LABEL_74;
                      v49 = 510;
                      goto LABEL_73;
                    }
                  }
                  v51 = (_OWORD *)p_TempPTK;
                  p_KeyContext->bCurrentPTKPresent = 1;
                  v52 = v51[1];
                  *(_OWORD *)&p_KeyContext->CurrentPTK.KCKLength = *v51;
                  v53 = v51[2];
                  *(_OWORD *)&p_KeyContext->CurrentPTK.PTK[4] = v52;
                  v54 = v51[3];
                  *(_OWORD *)&p_KeyContext->CurrentPTK.PTK[20] = v53;
                  v55 = v51[4];
                  *(_OWORD *)&p_KeyContext->CurrentPTK.PTK[36] = v54;
                  v56 = v51[5];
                  *(_OWORD *)&p_KeyContext->CurrentPTK.PTK[52] = v55;
                  v57 = *(_OWORD *)((char *)v51 + 92);
                  *(_OWORD *)&p_KeyContext->CurrentPTK.PTK[68] = v56;
                  *(_OWORD *)&p_KeyContext->CurrentPTK.PTK[80] = v57;
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
                      LODWORD(v61) = 0;
                      PmkCacheFinalizeOn4WayCompletion(
                        &a1->Dot11PmkCache,
                        a1->KeyContext.associatedAkm,
                        0,
                        (__int64)a3->MacHashEntry.MacKey,
                        (unsigned __int16 *)a1->CurrentAddress,
                        v61,
                        0,
                        (_OWORD *)(v65 + 24));
                    }
                  }
                  v50 = 0;
                  goto LABEL_75;
                }
              }
              else
              {
                LODWORD(v62) = 0;
                LODWORD(Size) = 0;
                FteMicForFTAssociationFrames = GenerateFteMicForFTAssociationFrames(
                                                 v21,
                                                 6,
                                                 a1->CurrentAddress,
                                                 AuthenticatorDeviceAddress,
                                                 Size,
                                                 0,
                                                 v62,
                                                 0,
                                                 p_KeyContext->TempPTK.KCKLength,
                                                 p_KeyContext->TempPTK.PTK);
                if ( FteMicForFTAssociationFrames >= 0 )
                  goto LABEL_55;
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  502,
                  WPP_e90d411d816e312466897e39e745b158_Traceguids,
                  (unsigned int)FteMicForFTAssociationFrames);
              goto LABEL_62;
            }
            goto LABEL_29;
          }
          p_WaitListHead = &stru_1400B0180;
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
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 494, WPP_e90d411d816e312466897e39e745b158_Traceguids, *v12);
  CompleteFTAssociationParamsRequest(-1073741670, 0x38009u, a1, a3, 0);
}

```

## disassembly

```asm
0x140046bf0  push    rbp
0x140046bf2  push    rbx
0x140046bf3  push    rsi
0x140046bf4  push    rdi
0x140046bf5  push    r12
0x140046bf7  push    r13
0x140046bf9  push    r14
0x140046bfb  push    r15
0x140046bfd  lea     rbp, [rsp-17h]
0x140046c02  sub     rsp, 0F8h
0x140046c09  mov     rax, cs:__security_cookie
0x140046c10  xor     rax, rsp
0x140046c13  mov     [rbp+4Fh+var_50], rax
0x140046c17  mov     r14, [rbp+4Fh+arg_20]
0x140046c1b  lea     rsi, [rcx+1710h]
0x140046c22  mov     [rbp+4Fh+var_B0], r9d
0x140046c26  mov     r13, r8
0x140046c29  mov     r8, [rcx+16F0h]
0x140046c30  xor     edi, edi
0x140046c32  mov     r9, [rcx+1700h]
0x140046c39  mov     r12, rdx
0x140046c3c  mov     r15, rcx
0x140046c3f  cmp     r9, r8
0x140046c42  jnz     loc_140047581
0x140046c48  cmp     [rsi+508h], edi
0x140046c4e  jz      loc_140047581
0x140046c54  cmp     [rsi+510h], rdi
0x140046c5b  jz      loc_140047581
0x140046c61  movzx   eax, byte ptr [r14+1]
0x140046c66  cmp     al, 2
0x140046c68  jb      loc_140047535
0x140046c6e  cmp     dword ptr [r14+20h], 6
0x140046c73  jb      loc_140047535
0x140046c79  mov     rdx, r13
0x140046c7c  call    GetActivePmk
0x140046c81  mov     qword ptr [rbp+4Fh+var_C0], rax
0x140046c85  test    rax, rax
0x140046c88  jnz     short loc_140046CBC
0x140046c8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140046c91  lea     rbx, WPP_GLOBAL_Control
0x140046c98  cmp     rcx, rbx
0x140046c9b  jz      short loc_140046CB2
0x140046c9d  mov     rcx, [rcx+18h]
0x140046ca1  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x140046ca8  mov     edx, 1EDh
0x140046cad  call    WPP_SF_
0x140046cb2  mov     ecx, 0C0000001h
0x140046cb7  jmp     loc_1400475BD
0x140046cbc  mov     eax, [r14+64h]
0x140046cc0  mov     ebx, 10h
0x140046cc5  test    eax, eax
0x140046cc7  jz      loc_140046DF6
0x140046ccd  cmp     [r14+68h], edi
0x140046cd1  jbe     loc_140046DF6
0x140046cd7  lea     rdi, [r14+rax]
0x140046cdb  mov     eax, [rdi]
0x140046cdd  add     eax, ebx
0x140046cdf  cmp     eax, ebx
0x140046ce1  jb      loc_140046DB3
0x140046ce7  lea     ecx, [rbx+30h]
0x140046cea  cmp     eax, ecx
0x140046cec  ja      short loc_140046CF7
0x140046cee  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140046cf5  jmp     short loc_140046D25
0x140046cf7  cmp     eax, 100h
0x140046cfc  ja      short loc_140046D07
0x140046cfe  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140046d05  jmp     short loc_140046D25
0x140046d07  cmp     eax, 400h
0x140046d0c  ja      short loc_140046D17
0x140046d0e  lea     rbx, Lookaside
0x140046d15  jmp     short loc_140046D25
0x140046d17  cmp     eax, 800h
0x140046d1c  ja      short loc_140046D36
0x140046d1e  lea     rbx, stru_1400B0180
0x140046d25  mov     rcx, rbx; Lookaside
0x140046d28  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140046d2f  nop     dword ptr [rax+rax+00h]
0x140046d34  jmp     short loc_140046D4C
0x140046d36  xor     ebx, ebx
0x140046d38  mov     edx, eax
0x140046d3a  mov     r8d, 7A697377h
0x140046d40  call    cs:__imp_ExAllocatePool2
0x140046d47  nop     dword ptr [rax+rax+00h]
0x140046d4c  test    rax, rax
0x140046d4f  jz      short loc_140046DB3
0x140046d51  mov     [rax], rbx
0x140046d54  lea     rbx, [rax+10h]
0x140046d58  mov     dword ptr [rax+8], 7A697377h
0x140046d5f  mov     rcx, [rsi+58h]
0x140046d63  test    rcx, rcx
0x140046d66  jz      short loc_140046D97
0x140046d68  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140046d6c  mov     rax, [rcx]
0x140046d6f  test    rax, rax
0x140046d72  jz      short loc_140046D88
0x140046d74  mov     rdx, rcx; Entry
0x140046d77  mov     rcx, rax; Lookaside
0x140046d7a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140046d81  nop     dword ptr [rax+rax+00h]
0x140046d86  jmp     short loc_140046D97
0x140046d88  mov     edx, [rcx+8]; Tag
0x140046d8b  call    cs:__imp_ExFreePoolWithTag
0x140046d92  nop     dword ptr [rax+rax+00h]
0x140046d97  mov     [rsi+58h], rbx
0x140046d9b  mov     rdx, rdi; Src
0x140046d9e  mov     r8d, [rdi]; Size
0x140046da1  mov     rcx, rbx; void *
0x140046da4  call    memmove
0x140046da9  mov     eax, [rdi+8]
0x140046dac  xor     edi, edi
0x140046dae  lea     ebx, [rdi+10h]
0x140046db1  jmp     short loc_140046DF8
0x140046db3  mov     rcx, cs:WPP_GLOBAL_Control
0x140046dba  lea     rbx, WPP_GLOBAL_Control
0x140046dc1  cmp     rcx, rbx
0x140046dc4  jz      short loc_140046DDE
0x140046dc6  mov     r9d, [rdi]
0x140046dc9  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x140046dd0  mov     rcx, [rcx+18h]
0x140046dd4  mov     edx, 1EEh
0x140046dd9  call    WPP_SF_d
0x140046dde  mov     [rsp+130h+Size], 0
0x140046de7  mov     edx, 38009h
0x140046dec  mov     ecx, 0C000009Ah
0x140046df1  jmp     loc_1400475C7
0x140046df6  mov     eax, edi
0x140046df8  mov     [rsp+130h+var_F0], edi; unsigned int
0x140046dfc  xor     edx, edx; int
0x140046dfe  mov     [rsi+518h], eax
0x140046e04  mov     rcx, r12; struct _DOT11_SSID *
0x140046e07  mov     r8d, [r14+1Ch]
0x140046e0b  mov     r9d, [r14+20h]
0x140046e0f  add     r8, 6
0x140046e13  mov     dword ptr [rsp+130h+var_F8], edi; unsigned int
0x140046e17  add     r8, r14; unsigned __int8 *
0x140046e1a  mov     [rsp+130h+var_100], rdi; unsigned __int8 *
0x140046e1f  sub     r9d, 6; unsigned int
0x140046e23  mov     dword ptr [rsp+130h+var_108], edi; unsigned int
0x140046e27  mov     [rsp+130h+Size], rdi; unsigned __int8 *
0x140046e2c  call    ?GetFTContextInformation@@YAPEAUNWF_FT_CONTEXT@@PEBU_DOT11_SSID@@HPEBEK1K1KK@Z; GetFTContextInformation(_DOT11_SSID const *,int,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,ulong)
0x140046e31  mov     r12, rax
0x140046e34  test    rax, rax
0x140046e37  jnz     short loc_140046E72
0x140046e39  mov     rcx, cs:WPP_GLOBAL_Control
0x140046e40  lea     rbx, WPP_GLOBAL_Control
0x140046e47  cmp     rcx, rbx
0x140046e4a  jz      short loc_140046E63
0x140046e4c  mov     rcx, [rcx+18h]
0x140046e50  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x140046e57  mov     edx, 1EFh
0x140046e5c  call    WPP_SF_
0x140046e61  xor     edi, edi
0x140046e63  mov     edx, 48010h
0x140046e68  mov     ecx, 0C000000Dh
0x140046e6d  jmp     loc_1400475C2
0x140046e72  mov     rdx, [rsi+510h]
0x140046e79  lea     rcx, [rax+78h]; Buf1
0x140046e7d  add     rdx, 78h ; 'x'; Buf2
0x140046e81  mov     r8, rbx; Size
0x140046e84  call    memcmp
0x140046e89  test    eax, eax
0x140046e8b  jz      loc_140046F42
0x140046e91  mov     rcx, cs:WPP_GLOBAL_Control
0x140046e98  lea     rbx, WPP_GLOBAL_Control
0x140046e9f  cmp     rcx, rbx
0x140046ea2  jz      loc_1400471F5
0x140046ea8  mov     rcx, [rcx+18h]
0x140046eac  lea     rdi, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x140046eb3  mov     r8, rdi
0x140046eb6  mov     edx, 1F0h
0x140046ebb  call    WPP_SF_
0x140046ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x140046ec7  cmp     rcx, rbx
0x140046eca  jz      loc_1400471F5
0x140046ed0  mov     rax, [rsi+510h]
0x140046ed7  lea     r9, [rbp+4Fh+var_70]
0x140046edb  mov     rcx, [rcx+18h]
0x140046edf  xorps   xmm0, xmm0
0x140046ee2  movups  [rbp+4Fh+var_C0], xmm0
0x140046ee6  add     rax, 78h ; 'x'
0x140046eea  mov     r14d, 10h
0x140046ef0  mov     qword ptr [rbp+4Fh+var_C0+8], rax
0x140046ef4  mov     edx, 1F1h
0x140046ef9  mov     word ptr [rbp+4Fh+var_C0], r14w
0x140046efe  mov     r8, rdi
0x140046f01  movaps  xmm0, [rbp+4Fh+var_C0]
0x140046f05  movdqa  [rbp+4Fh+var_70], xmm0
0x140046f0a  call    WPP_SF__HEX_
0x140046f0f  mov     rcx, cs:WPP_GLOBAL_Control
0x140046f16  cmp     rcx, rbx
0x140046f19  jz      loc_1400471F5
0x140046f1f  xorps   xmm0, xmm0
0x140046f22  lea     rax, [r12+78h]
0x140046f27  movups  [rbp+4Fh+var_C0], xmm0
0x140046f2b  mov     word ptr [rbp+4Fh+var_C0], r14w
0x140046f30  mov     edx, 1F2h
0x140046f35  mov     qword ptr [rbp+4Fh+var_C0+8], rax
0x140046f39  movaps  xmm0, [rbp+4Fh+var_C0]
0x140046f3d  jmp     loc_1400471E0
0x140046f42  mov     rcx, cs:WPP_GLOBAL_Control
0x140046f49  lea     rbx, WPP_GLOBAL_Control
0x140046f50  cmp     rcx, rbx
0x140046f53  jz      short loc_140046F97
0x140046f55  mov     eax, [r14+58h]
0x140046f59  mov     r9d, [rsi+0Ch]
0x140046f5d  mov     rcx, [rcx+18h]
0x140046f61  mov     [rsp+130h+var_E0], eax
0x140046f65  mov     eax, [rsi+18h]
0x140046f68  mov     dword ptr [rsp+130h+var_E8], eax
0x140046f6c  mov     eax, [r14+3Ch]
0x140046f70  mov     [rsp+130h+var_F0], eax
0x140046f74  mov     eax, [rsi+14h]
0x140046f77  mov     dword ptr [rsp+130h+var_F8], eax
0x140046f7b  mov     eax, [r14+38h]
0x140046f7f  mov     dword ptr [rsp+130h+var_100], eax
0x140046f83  mov     eax, [rsi+10h]
0x140046f86  mov     dword ptr [rsp+130h+var_108], eax
0x140046f8a  mov     eax, [r14+34h]
0x140046f8e  mov     dword ptr [rsp+130h+Size], eax
0x140046f92  call    WPP_SF_dddddddd
0x140046f97  mov     eax, [r14+34h]
0x140046f9b  lea     r9, [r14+4]
0x140046f9f  mov     [rsi+0Ch], eax
0x140046fa2  mov     rcx, rsi; struct _NWF_KEY_CONTEXT *
0x140046fa5  mov     eax, [r14+38h]
0x140046fa9  mov     [rsi+10h], eax
0x140046fac  mov     eax, [r14+3Ch]
0x140046fb0  mov     [rsi+14h], eax
0x140046fb3  mov     eax, [r14+58h]
0x140046fb7  mov     [rsi+18h], eax
0x140046fba  mov     byte ptr [rsi+4E4h], 3
0x140046fc1  mov     [rsi+110h], rdi
0x140046fc8  call    ?IsMloConnection@@YAHPEAU_NWF_KEY_CONTEXT@@@Z; IsMloConnection(_NWF_KEY_CONTEXT *)
0x140046fcd  test    eax, eax
0x140046fcf  jz      short loc_140046FDE
0x140046fd1  mov     rax, [rsi+58h]
0x140046fd5  test    rax, rax
0x140046fd8  jz      short loc_140046FDE
0x140046fda  lea     r9, [rax+62h]; unsigned __int8 *
0x140046fde  mov     rax, [r12+98h]
0x140046fe6  lea     rdi, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x140046fed  mov     edx, [r14+70h]
0x140046ff1  xor     ecx, ecx
0x140046ff3  movups  xmm0, xmmword ptr [rax]
0x140046ff6  movdqu  [rbp+4Fh+Buf2], xmm0
0x140046ffb  test    edx, edx
0x140046ffd  jz      loc_140047209
0x140047003  mov     eax, [r14+6Ch]
0x140047007  test    eax, eax
0x140047009  jz      loc_140047209
0x14004700f  mov     rcx, cs:WPP_GLOBAL_Control
0x140047016  cmp     rcx, rbx
0x140047019  jz      short loc_140047050
0x14004701b  mov     rcx, [rcx+18h]
0x14004701f  lea     r9, [rsp+130h+var_D0]
0x140047024  xorps   xmm0, xmm0
0x140047027  add     rax, r14
0x14004702a  movups  [rsp+130h+var_D0], xmm0
0x14004702f  mov     word ptr [rsp+130h+var_D0], dx
0x140047034  mov     r8, rdi
0x140047037  mov     qword ptr [rbp+4Fh+var_D0+8], rax
0x14004703b  mov     edx, 1F4h
0x140047040  movaps  xmm0, [rsp+130h+var_D0]
0x140047045  movdqa  [rsp+130h+var_D0], xmm0
0x14004704b  call    WPP_SF__HEX_
0x140047050  mov     ecx, [r14+6Ch]
0x140047054  lea     rdx, [rbp+4Fh+var_70]
0x140047058  lea     rax, [rsi+408h]
0x14004705f  mov     [rsp+130h+Size], rdx
0x140047064  mov     edx, [r14+70h]
0x140047068  lea     r8, [rax+0Ch]
0x14004706c  mov     r9d, [rax]
0x14004706f  xorps   xmm0, xmm0
0x140047072  add     rcx, r14
0x140047075  movups  [rbp+4Fh+var_70], xmm0
0x140047079  call    WL_CMAC_128
0x14004707e  test    eax, eax
0x140047080  js      loc_14004724A
0x140047086  mov     rcx, cs:WPP_GLOBAL_Control
0x14004708d  cmp     rcx, rbx
0x140047090  jz      short loc_1400470CD
0x140047092  mov     rcx, [rcx+18h]
0x140047096  lea     r9, [rsp+130h+var_D0]
0x14004709b  xorps   xmm0, xmm0
0x14004709e  mov     eax, 10h
0x1400470a3  movups  [rsp+130h+var_D0], xmm0
0x1400470a8  mov     word ptr [rsp+130h+var_D0], ax
0x1400470ad  mov     edx, 1F5h
0x1400470b2  lea     rax, [rbp+4Fh+var_70]
0x1400470b6  mov     r8, rdi
0x1400470b9  mov     qword ptr [rbp+4Fh+var_D0+8], rax
0x1400470bd  movaps  xmm0, [rsp+130h+var_D0]
0x1400470c2  movdqa  [rsp+130h+var_D0], xmm0
0x1400470c8  call    WPP_SF__HEX_
0x1400470cd  mov     rax, [r12+98h]
0x1400470d5  movups  xmm0, [rbp+4Fh+var_70]
0x1400470d9  movdqu  xmmword ptr [rax], xmm0
0x1400470dd  lea     rcx, [rsi+408h]
0x1400470e4  mov     r8d, 10h; Size
  ... truncated ...
```
