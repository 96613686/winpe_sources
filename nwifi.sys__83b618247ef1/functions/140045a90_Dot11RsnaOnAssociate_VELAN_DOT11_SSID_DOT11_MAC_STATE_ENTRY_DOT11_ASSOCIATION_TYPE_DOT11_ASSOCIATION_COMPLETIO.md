# Dot11RsnaOnAssociate(_VELAN *,_DOT11_SSID *,DOT11_MAC_STATE_ENTRY *,_DOT11_ASSOCIATION_TYPE,DOT11_ASSOCIATION_COMPLETION_PARAMETERS *,ulong,DOT11_CONNECTION_INFO *)

- ea: `0x140045a90`
- end: `0x14004639f`
- name: `?Dot11RsnaOnAssociate@@YAXPEAU_VELAN@@PEAU_DOT11_SSID@@PEAUDOT11_MAC_STATE_ENTRY@@W4_DOT11_ASSOCIATION_TYPE@@PEAUDOT11_ASSOCIATION_COMPLETION_PARAMETERS@@KPEAUDOT11_CONNECTION_INFO@@@Z`
- size: `2319`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14005c9dc`

## callees

- `0x14000d22c`
- `0x140020dc0`
- `0x140020f20`
- `0x140023730`
- `0x14002ffb4`
- `0x1400366f8`
- `0x14003a264`
- `0x14003a5f4`
- `0x14003ae2c`
- `0x140040460`
- `0x140041398`
- `0x140045a90`
- `0x140047998`
- `0x14004937c`
- `0x14004967c`
- `0x14004a7fc`
- `0x14004ac7c`
- `0x1400527c0`
- `0x14005298c`
- `0x140052ee0`
- `0x1400534b4`
- `0x14008f3f8`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140045b8b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140045b8b`
- `ntoskrnl!ExAllocatePool2` at `0x140045ba4`
- `ntoskrnl!ExAllocatePool2` at `0x140045ba4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140045c5b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140045c9b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140045ea3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004621d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004626b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046320`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140045c5b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140045c9b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140045ea3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004621d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004626b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046320`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045c6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045cac`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045eb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004627c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046297`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046331`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045c6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045cac`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045eb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004627c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046297`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046331`

## pseudocode

```c
void __fastcall Dot11RsnaOnAssociate(
        _QWORD *a1,
        struct _DOT11_SSID *a2,
        struct DOT11_MAC_STATE_ENTRY *a3,
        __int64 a4,
        struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *a5,
        unsigned int a6,
        void *Src)
{
  _DWORD *v7; // rbx
  struct _VELAN *v9; // r13
  __int64 v10; // rax
  struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *v11; // r14
  _QWORD *v12; // rdi
  unsigned int v13; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rsi
  _DWORD *Pool2; // rax
  __int64 UnicastCipher; // r9
  __int64 MulticastCipher; // r8
  _DOT11_CIPHER_ALGORITHM MulticastMgmtCipher; // eax
  PDEVICE_OBJECT v19; // rcx
  struct _NWF_KEY_CONTEXT *v20; // rdx
  unsigned __int8 *pAssocRequestRsnIE; // rcx
  unsigned __int8 *v22; // rcx
  unsigned __int8 *pAssocRequestRsnXeIE; // rcx
  unsigned __int8 *v24; // rcx
  unsigned __int64 AuthAlgo; // rcx
  const unsigned __int8 *v26; // r8
  unsigned __int8 *MacKey; // r12
  DOT11_CONNECTION_INFO *pConnectionInfo; // rcx
  int *p_Rssi; // rcx
  PDEVICE_OBJECT v30; // rcx
  __int64 v31; // rdx
  enum _DOT11_AUTH_ALGORITHM v32; // ecx
  unsigned int assocRequestRsnIELength; // r9d
  unsigned __int8 *v34; // r8
  unsigned int v35; // edx
  unsigned __int8 *pBeaconRsnIE; // r8
  enum RSNA_AKM_SUITE v37; // ebx
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // r8
  __int64 v41; // r9
  unsigned int uAssocReqRSNIESettings; // eax
  __int64 v43; // rdx
  __int64 v44; // r8
  struct _DOT11_SSID *v45; // r10
  unsigned int v46; // eax
  int v47; // ecx
  BOOL v48; // eax
  bool v49; // zf
  __int64 uAssocRespSize; // r9
  struct NWF_FT_CONTEXT *FTContextInformation; // r13
  __int64 v52; // r9
  int v53; // edx
  int v54; // r8d
  struct DOT11_MAC_STATE_ENTRY *v55; // rbx
  NWF_PMK_ENTRY *pPmk; // rcx
  ULONG *v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rcx
  unsigned __int8 *v62; // [rsp+30h] [rbp-48h]
  unsigned __int8 *v63; // [rsp+40h] [rbp-38h]
  unsigned int v64; // [rsp+50h] [rbp-28h]
  enum RSNA_AKM_SUITE v65[4]; // [rsp+60h] [rbp-18h] BYREF
  struct _VELAN *v66; // [rsp+C0h] [rbp+48h] BYREF
  struct _DOT11_SSID *v67; // [rsp+C8h] [rbp+50h]
  struct DOT11_MAC_STATE_ENTRY *v68; // [rsp+D0h] [rbp+58h]
  int v69; // [rsp+D8h] [rbp+60h]

  v69 = a4;
  v68 = a3;
  v67 = a2;
  v66 = (struct _VELAN *)a1;
  v7 = Src;
  v9 = (struct _VELAN *)a1;
  if ( Src )
  {
    v64 = *((_DWORD *)Src + 2);
    LODWORD(Src) = *((_DWORD *)Src + 1);
  }
  else
  {
    v64 = 0;
    LODWORD(Src) = 0;
  }
  v10 = a1[734];
  v65[0] = rsna_akm_none;
  if ( a1[736] != v10 )
    return;
  v11 = a5;
  v12 = a1 + 738;
  if ( (unsigned int)(a5->AuthAlgo - 6) > 5 )
  {
    *(_DWORD *)v12 = 0;
    return;
  }
  if ( !a5->uAssocReqOffset || a5->uAssocReqSize < 0xA )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_ddd_MAC_D(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)a3 + 16, (_DWORD)a3, a5->uAssocReqSize);
    return;
  }
  if ( v7 )
  {
    v13 = *v7 + 16;
    a1[749] = 0;
    if ( v13 < 0x10 )
      goto LABEL_25;
    if ( v13 > 0x40 )
    {
      if ( v13 > 0x100 )
      {
        if ( v13 > 0x400 )
        {
          if ( v13 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v13, 2053731191, a4);
LABEL_21:
            if ( Pool2 )
            {
              *(_QWORD *)Pool2 = p_WaitListHead;
              Pool2[2] = 2053731191;
              v9->KeyContext.pConnectionInfo = (DOT11_CONNECTION_INFO *)(Pool2 + 4);
              memmove(Pool2 + 4, v7, (unsigned int)*v7);
              goto LABEL_23;
            }
LABEL_25:
            v19 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                367,
                WPP_e90d411d816e312466897e39e745b158_Traceguids,
                (unsigned int)*v7);
            if ( (unsigned int)Feature_53299205__private_IsEnabledDeviceUsageNoInline(v19, a2, a3, a4) )
            {
              RsnOConnection::CleanupRsnIEs((RsnOConnection *)&v9->KeyContext, v20);
            }
            else
            {
              pAssocRequestRsnIE = v9->KeyContext.pAssocRequestRsnIE;
              if ( pAssocRequestRsnIE )
              {
                v22 = pAssocRequestRsnIE - 16;
                if ( *(_QWORD *)v22 )
                  ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v22, v22);
                else
                  ExFreePoolWithTag(v22, *((_DWORD *)v22 + 2));
                v9->KeyContext.pAssocRequestRsnIE = 0;
              }
              v9->KeyContext.assocRequestRsnIELength = 0;
              pAssocRequestRsnXeIE = v9->KeyContext.pAssocRequestRsnXeIE;
              if ( pAssocRequestRsnXeIE )
              {
                v24 = pAssocRequestRsnXeIE - 16;
                if ( *(_QWORD *)v24 )
                  ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v24, v24);
                else
                  ExFreePoolWithTag(v24, *((_DWORD *)v24 + 2));
                v9->KeyContext.pAssocRequestRsnXeIE = 0;
              }
              v9->KeyContext.assocRequestRsnIELength = 0;
            }
            return;
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
    goto LABEL_21;
  }
LABEL_23:
  v9->KeyContext.AuthAlgo = v11->AuthAlgo;
  UnicastCipher = (unsigned int)v11->UnicastCipher;
  v9->KeyContext.UcastCipher = UnicastCipher;
  MulticastCipher = (unsigned int)v11->MulticastCipher;
  v9->KeyContext.McastCipher = MulticastCipher;
  if ( v11->Header.Revision < 2u )
    MulticastMgmtCipher = DOT11_CIPHER_ALGO_NONE;
  else
    MulticastMgmtCipher = v11->MulticastMgmtCipher;
  v9->KeyContext.McastMgmtCipher = MulticastMgmtCipher;
  AuthAlgo = (unsigned int)v11->AuthAlgo;
  if ( (_DWORD)AuthAlgo == 9 )
  {
    if ( MulticastMgmtCipher != DOT11_CIPHER_ALGO_BIP && MulticastMgmtCipher != DOT11_CIPHER_ALGO_BIP_GMAC_256 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          368,
          WPP_e90d411d816e312466897e39e745b158_Traceguids,
          (unsigned int)MulticastMgmtCipher);
      return;
    }
  }
  else if ( (_DWORD)AuthAlgo == 8
         && ((_DWORD)UnicastCipher != 9
          || (_DWORD)MulticastCipher != 9
          || MulticastMgmtCipher != DOT11_CIPHER_ALGO_BIP_GMAC_256) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_lll(
        WPP_GLOBAL_Control->AttachedDevice,
        369,
        WPP_e90d411d816e312466897e39e745b158_Traceguids,
        UnicastCipher,
        MulticastCipher,
        MulticastMgmtCipher);
    return;
  }
  if ( v9->KeyContext.pAssocRequestRsnIE )
  {
    AuthAlgo = (unsigned __int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 370, WPP_e90d411d816e312466897e39e745b158_Traceguids);
  }
  if ( v9->KeyContext.pAssocRequestRsnXeIE )
  {
    AuthAlgo = (unsigned __int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 371, WPP_e90d411d816e312466897e39e745b158_Traceguids);
  }
  if ( v9->KeyContext.pBeaconRsnIE )
  {
    AuthAlgo = (unsigned __int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 372, WPP_e90d411d816e312466897e39e745b158_Traceguids);
  }
  if ( v9->KeyContext.pBeaconRsnXeIE )
  {
    AuthAlgo = (unsigned __int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 373, WPP_e90d411d816e312466897e39e745b158_Traceguids);
  }
  if ( !(unsigned int)Feature_53299205__private_IsEnabledDeviceUsageNoInline(
                        AuthAlgo,
                        a2,
                        MulticastCipher,
                        UnicastCipher) )
  {
    MacKey = a3->MacHashEntry.MacKey;
    if ( (unsigned int)CDRollback_GetRsnAndRsnXeIEsAfterAssociation(
                         &v9->KeyContext,
                         MacKey,
                         v11->bReAssocReq,
                         v11->uAssocReqSize,
                         &v11->Header.Type + v11->uAssocReqOffset,
                         v11->uBeaconSize,
                         &v11->Header.Type + v11->uBeaconOffset) )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return;
      v31 = 376;
LABEL_76:
      WPP_SF__MAC_(v30->AttachedDevice, v31, WPP_e90d411d816e312466897e39e745b158_Traceguids, MacKey);
      return;
    }
LABEL_80:
    v32 = v9->KeyContext.AuthAlgo;
    if ( (unsigned int)(v32 - 3) > 8
      || v11->Header.Revision < 2u
      || v9->KeyContext.pBeaconRsnIE && v9->KeyContext.beaconRsnIELength )
    {
      assocRequestRsnIELength = v9->KeyContext.assocRequestRsnIELength;
      v34 = v9->KeyContext.pAssocRequestRsnIE;
      v35 = (unsigned int)Src;
      v9->KeyContext.uAssocReqRSNIESettings = 0;
      v9->KeyContext.beaconRsnIESettings = 0;
      GetRSNIESettings(v32, v35, v34, assocRequestRsnIELength, &v9->KeyContext.uAssocReqRSNIESettings, v65);
      pBeaconRsnIE = v9->KeyContext.pBeaconRsnIE;
      if ( pBeaconRsnIE )
        GetRSNIESettings(
          v9->KeyContext.AuthAlgo,
          (unsigned int)Src,
          pBeaconRsnIE,
          v9->KeyContext.beaconRsnIELength,
          &v9->KeyContext.beaconRsnIESettings,
          0);
      else
        MacKey = v68->MacHashEntry.MacKey;
      v37 = v65[0];
      v9->KeyContext.associatedAkm = v65[0];
      if ( (unsigned int)Feature_Bugfix_58508574__private_IsEnabledDeviceUsageNoInline() )
        v9->Dot11PmkCache.associatedAkm = v9->KeyContext.associatedAkm;
      GetEapolKeyInfoFromAkm(v9, (unsigned __int8 (*)[6])MacKey, v37, &v9->KeyContext.EapolKeyInfo);
      uAssocReqRSNIESettings = v9->KeyContext.uAssocReqRSNIESettings;
      v9->KeyContext.KeyDescriptorVersion = 0;
      if ( (uAssocReqRSNIESettings & 3) != 0 )
      {
        v9->KeyContext.KeyDescriptorVersion = 2 - (((v9->KeyContext.UcastCipher - 4) & 0xFFFFFFFB) != 0);
      }
      else if ( (uAssocReqRSNIESettings & 0x3C) != 0 )
      {
        v9->KeyContext.KeyDescriptorVersion = 3;
      }
      v9->KeyContext.currentConnectionFlags = v64;
      if ( (unsigned int)Feature_53299205__private_IsEnabledDeviceUsageNoInline(v39, v38, v40, v41) )
        v9->KeyContext.adapterConnectionCapabilityFlags = v9->pAdapt->AdapterEnhancedCapabilities.AdapterConnectionCapabilityFlags;
      v45 = v67;
      v9->KeyContext.Ssid = *v67;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        WPP_SF_DDddddd(
          WPP_GLOBAL_Control->AttachedDevice,
          v43,
          v44,
          (unsigned int)Src,
          v64,
          v9->KeyContext.AuthAlgo,
          v9->KeyContext.UcastCipher,
          v9->KeyContext.McastCipher,
          v9->KeyContext.McastMgmtCipher,
          v9->KeyContext.KeyDescriptorVersion);
        v45 = v67;
      }
      v46 = v9->KeyContext.AuthAlgo;
      v9->KeyContext.TxReplayCounter = 0;
      v48 = 0;
      if ( v46 <= 0xB )
      {
        v47 = 2368;
        if ( _bittest(&v47, v46) )
        {
          if ( v68->pPmk || v9->KeyContext.pOpPmk )
            v48 = 1;
        }
      }
      v49 = v69 == 2;
      v9->KeyContext.bFastRoaming = v48;
      v9->KeyContext.bFTAKM = 0;
      v9->KeyContext.bIsPBSSNotInDS = v49;
      if ( (v9->KeyContext.uAssocReqRSNIESettings & 0xC) == 0 )
        goto LABEL_107;
      uAssocRespSize = v11->uAssocRespSize;
      if ( (unsigned int)uAssocRespSize < 6 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_Dd(
            WPP_GLOBAL_Control->AttachedDevice,
            378,
            WPP_e90d411d816e312466897e39e745b158_Traceguids,
            uAssocRespSize,
            6);
      }
      else
      {
        FTContextInformation = GetFTContextInformation(
                                 v45,
                                 0,
                                 &v11->MacAddr[v11->uAssocRespOffset + 2],
                                 (int)uAssocRespSize - 6,
                                 v9->KeyContext.pAssocRequestRsnIE,
                                 v9->KeyContext.assocRequestRsnIELength,
                                 0,
                                 0,
                                 0);
        if ( FTContextInformation )
        {
          *((_DWORD *)v12 + 322) = 1;
          FreeFTContext((struct NWF_FT_CONTEXT **)v12 + 162);
          v12[162] = FTContextInformation;
          v9 = v66;
LABEL_107:
          v52 = v12[30];
          *(_DWORD *)v12 = 1;
          if ( v52 )
          {
            Dot11GetPmkId(&v9->Dot11PmkCache);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              *(_OWORD *)v65 = 0;
              LOWORD(v65[0]) = 16;
              *(_QWORD *)&v65[2] = v12[30] + 24LL;
              WPP_SF__HEX__MAC_(WPP_GLOBAL_Control->AttachedDevice, v53, v54, (unsigned int)v65, (__int64)MacKey);
            }
          }
          if ( *((_DWORD *)v12 + 3) == 10 )
          {
            v55 = v68;
            pPmk = v68->pPmk;
            if ( pPmk )
            {
              v57 = (ULONG *)&pPmk[-1].ucKey[51];
              if ( *(_QWORD *)v57 )
                ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v57, v57);
              else
                ExFreePoolWithTag(v57, v57[2]);
              v55->pPmk = 0;
            }
            if ( !(unsigned int)OWEWasPmkIdAccepted(v9, v11, (unsigned __int8 (*)[6])MacKey) )
            {
              *(_QWORD *)v65 = 0;
              LODWORD(v66) = 0;
              LODWORD(Src) = 0;
              if ( (unsigned int)OWEParseDHIE(
                                   v11,
                                   (enum OWE_GROUP *)&Src,
                                   (const unsigned __int8 **)v65,
                                   (unsigned int *)&v66) )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 380, WPP_e90d411d816e312466897e39e745b158_Traceguids);
                v60 = v12[7];
                if ( v60 )
                {
                  v61 = v60 - 16;
                  if ( *(_QWORD *)v61 )
                    ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v61, (PVOID)v61);
                  else
                    ExFreePoolWithTag((PVOID)v61, *(_DWORD *)(v61 + 8));
                  v12[7] = 0;
                }
                *((_DWORD *)v12 + 16) = 0;
              }
              else
              {
                OWERequestPMKWorker(v9, v55, a6, v11);
              }
            }
          }
          return;
        }
      }
    }
    v58 = v12[7];
    if ( v58 )
    {
      v59 = v58 - 16;
      if ( *(_QWORD *)v59 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v59, (PVOID)v59);
      else
        ExFreePoolWithTag((PVOID)v59, *(_DWORD *)(v59 + 8));
      v12[7] = 0;
    }
    *((_DWORD *)v12 + 16) = 0;
    return;
  }
  if ( v9->KeyContext.pAssocRequestSelectionIE && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 374, WPP_e90d411d816e312466897e39e745b158_Traceguids);
  MacKey = a3->MacHashEntry.MacKey;
  LODWORD(v62) = v11->uBeaconSize;
  LOBYTE(v26) = v11->bReAssocReq != 0;
  if ( !(unsigned int)RsnOConnection::GetRsnAndRsnXeIEsAfterAssociation(
                        (RsnOConnection *)&v9->KeyContext,
                        (struct _NWF_KEY_CONTEXT *)MacKey,
                        v26,
                        (v64 & 0x4000) != 0,
                        v11->uAssocReqSize,
                        (int)v11 + v11->uAssocReqOffset,
                        v62,
                        (int)v11 + v11->uBeaconOffset,
                        v63) )
    goto LABEL_80;
  pConnectionInfo = v9->KeyContext.pConnectionInfo;
  if ( pConnectionInfo )
  {
    p_Rssi = &pConnectionInfo[-1].LinkInfo[0].Rssi;
    if ( *(_QWORD *)p_Rssi )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)p_Rssi, p_Rssi);
    else
      ExFreePoolWithTag(p_Rssi, p_Rssi[2]);
    v9->KeyContext.pConnectionInfo = 0;
  }
  v30 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    v31 = 375;
    goto LABEL_76;
  }
}

```

## disassembly

```asm
0x140045a90  mov     rax, rsp
0x140045a93  mov     [rax+20h], r9d
0x140045a97  mov     [rax+18h], r8
0x140045a9b  mov     [rax+10h], rdx
0x140045a9f  mov     [rax+8], rcx
0x140045aa3  push    rbp
0x140045aa4  push    rbx
0x140045aa5  push    rsi
0x140045aa6  push    rdi
0x140045aa7  push    r12
0x140045aa9  push    r13
0x140045aab  push    r14
0x140045aad  push    r15
0x140045aaf  mov     rbp, rsp
0x140045ab2  sub     rsp, 78h
0x140045ab6  mov     rbx, [rbp+Src]
0x140045aba  xor     r15d, r15d
0x140045abd  mov     r12, r8
0x140045ac0  mov     r13, rcx
0x140045ac3  test    rbx, rbx
0x140045ac6  jz      short loc_140045AD6
0x140045ac8  mov     ecx, [rbx+8]
0x140045acb  mov     [rbp+var_28], ecx
0x140045ace  mov     ecx, [rbx+4]
0x140045ad1  mov     dword ptr [rbp+Src], ecx
0x140045ad4  jmp     short loc_140045ADE
0x140045ad6  mov     [rbp+var_28], r15d
0x140045ada  mov     dword ptr [rbp+Src], r15d
0x140045ade  mov     rax, [r13+16F0h]
0x140045ae5  mov     [rbp+var_18], 0AC0F00h
0x140045aec  cmp     [r13+1700h], rax
0x140045af3  jnz     loc_14004638D
0x140045af9  mov     r14, [rbp+arg_20]
0x140045afd  lea     rdi, [r13+1710h]
0x140045b04  mov     eax, [r14+34h]
0x140045b08  sub     eax, 6
0x140045b0b  cmp     eax, 5
0x140045b0e  jbe     short loc_140045B18
0x140045b10  mov     [rdi], r15d
0x140045b13  jmp     loc_14004638D
0x140045b18  cmp     [r14+14h], r15d
0x140045b1c  jz      loc_14004635B
0x140045b22  cmp     dword ptr [r14+18h], 0Ah
0x140045b27  jb      loc_14004635B
0x140045b2d  test    rbx, rbx
0x140045b30  jz      loc_140045BD2
0x140045b36  mov     eax, [rbx]
0x140045b38  add     eax, 10h
0x140045b3b  mov     [rdi+58h], r15
0x140045b3f  cmp     eax, 10h
0x140045b42  jb      loc_140045BFF
0x140045b48  mov     ecx, 40h ; '@'
0x140045b4d  cmp     eax, ecx
0x140045b4f  ja      short loc_140045B5A
0x140045b51  lea     rsi, WPP_MAIN_CB.DeviceQueue
0x140045b58  jmp     short loc_140045B88
0x140045b5a  cmp     eax, 100h
0x140045b5f  ja      short loc_140045B6A
0x140045b61  lea     rsi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140045b68  jmp     short loc_140045B88
0x140045b6a  cmp     eax, 400h
0x140045b6f  ja      short loc_140045B7A
0x140045b71  lea     rsi, Lookaside
0x140045b78  jmp     short loc_140045B88
0x140045b7a  cmp     eax, 800h
0x140045b7f  ja      short loc_140045B99
0x140045b81  lea     rsi, stru_1400B0180
0x140045b88  mov     rcx, rsi; Lookaside
0x140045b8b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140045b92  nop     dword ptr [rax+rax+00h]
0x140045b97  jmp     short loc_140045BB0
0x140045b99  mov     edx, eax
0x140045b9b  mov     r8d, 7A697377h
0x140045ba1  mov     rsi, r15
0x140045ba4  call    cs:__imp_ExAllocatePool2
0x140045bab  nop     dword ptr [rax+rax+00h]
0x140045bb0  test    rax, rax
0x140045bb3  jz      short loc_140045BFF
0x140045bb5  mov     [rax], rsi
0x140045bb8  lea     rcx, [rax+10h]; void *
0x140045bbc  mov     dword ptr [rax+8], 7A697377h
0x140045bc3  mov     rdx, rbx; Src
0x140045bc6  mov     [rdi+58h], rcx
0x140045bca  mov     r8d, [rbx]; Size
0x140045bcd  call    memmove
0x140045bd2  mov     eax, [r14+34h]
0x140045bd6  xor     ebx, ebx
0x140045bd8  mov     [rdi+0Ch], eax
0x140045bdb  mov     r9d, [r14+38h]
0x140045bdf  mov     [rdi+10h], r9d
0x140045be3  mov     r8d, [r14+3Ch]
0x140045be7  mov     [rdi+14h], r8d
0x140045beb  cmp     byte ptr [r14+1], 2
0x140045bf0  jb      loc_140045CC5
0x140045bf6  mov     eax, [r14+58h]
0x140045bfa  jmp     loc_140045CC7
0x140045bff  mov     rcx, cs:WPP_GLOBAL_Control
0x140045c06  lea     rsi, WPP_GLOBAL_Control
0x140045c0d  cmp     rcx, rsi
0x140045c10  jz      short loc_140045C2A
0x140045c12  mov     r9d, [rbx]
0x140045c15  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x140045c1c  mov     rcx, [rcx+18h]
0x140045c20  mov     edx, 16Fh
0x140045c25  call    WPP_SF_d
0x140045c2a  call    Feature_53299205__private_IsEnabledDeviceUsageNoInline
0x140045c2f  test    eax, eax
0x140045c31  jz      short loc_140045C40
0x140045c33  mov     rcx, rdi; this
0x140045c36  call    ?CleanupRsnIEs@RsnOConnection@@YAXPEAU_NWF_KEY_CONTEXT@@@Z; RsnOConnection::CleanupRsnIEs(_NWF_KEY_CONTEXT *)
0x140045c3b  jmp     loc_14004638D
0x140045c40  mov     rcx, [rdi+38h]
0x140045c44  test    rcx, rcx
0x140045c47  jz      short loc_140045C7C
0x140045c49  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140045c4d  mov     rax, [rcx]
0x140045c50  test    rax, rax
0x140045c53  jz      short loc_140045C69
0x140045c55  mov     rdx, rcx; Entry
0x140045c58  mov     rcx, rax; Lookaside
0x140045c5b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140045c62  nop     dword ptr [rax+rax+00h]
0x140045c67  jmp     short loc_140045C78
0x140045c69  mov     edx, [rcx+8]; Tag
0x140045c6c  call    cs:__imp_ExFreePoolWithTag
0x140045c73  nop     dword ptr [rax+rax+00h]
0x140045c78  mov     [rdi+38h], r15
0x140045c7c  mov     [rdi+40h], r15d
0x140045c80  mov     rcx, [rdi+48h]
0x140045c84  test    rcx, rcx
0x140045c87  jz      short loc_140045CBC
0x140045c89  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140045c8d  mov     rax, [rcx]
0x140045c90  test    rax, rax
0x140045c93  jz      short loc_140045CA9
0x140045c95  mov     rdx, rcx; Entry
0x140045c98  mov     rcx, rax; Lookaside
0x140045c9b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140045ca2  nop     dword ptr [rax+rax+00h]
0x140045ca7  jmp     short loc_140045CB8
0x140045ca9  mov     edx, [rcx+8]; Tag
0x140045cac  call    cs:__imp_ExFreePoolWithTag
0x140045cb3  nop     dword ptr [rax+rax+00h]
0x140045cb8  mov     [rdi+48h], r15
0x140045cbc  mov     [rdi+40h], r15d
0x140045cc0  jmp     loc_14004638D
0x140045cc5  mov     eax, ebx
0x140045cc7  mov     [rdi+18h], eax
0x140045cca  mov     ecx, [r14+34h]
0x140045cce  cmp     ecx, 9
0x140045cd1  jnz     short loc_140045D19
0x140045cd3  cmp     eax, 6
0x140045cd6  jz      loc_140045D68
0x140045cdc  cmp     eax, 0Ch
0x140045cdf  jz      loc_140045D68
0x140045ce5  mov     rcx, cs:WPP_GLOBAL_Control
0x140045cec  lea     rsi, WPP_GLOBAL_Control
0x140045cf3  cmp     rcx, rsi
0x140045cf6  jz      loc_14004638D
0x140045cfc  mov     rcx, [rcx+18h]
0x140045d00  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x140045d07  mov     edx, 170h
0x140045d0c  mov     r9d, eax
0x140045d0f  call    WPP_SF_d
0x140045d14  jmp     loc_14004638D
0x140045d19  cmp     ecx, 8
0x140045d1c  jnz     short loc_140045D68
0x140045d1e  cmp     r9d, 9
0x140045d22  jnz     short loc_140045D2E
0x140045d24  cmp     r8d, r9d
0x140045d27  jnz     short loc_140045D2E
0x140045d29  cmp     eax, 0Ch
0x140045d2c  jz      short loc_140045D68
0x140045d2e  mov     rcx, cs:WPP_GLOBAL_Control
0x140045d35  lea     rsi, WPP_GLOBAL_Control
0x140045d3c  cmp     rcx, rsi
0x140045d3f  jz      loc_14004638D
0x140045d45  mov     rcx, [rcx+18h]
0x140045d49  mov     edx, 171h
0x140045d4e  mov     dword ptr [rsp+78h+var_50], eax
0x140045d52  mov     dword ptr [rsp+78h+var_58], r8d
0x140045d57  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x140045d5e  call    WPP_SF_lll
0x140045d63  jmp     loc_14004638D
0x140045d68  lea     r15, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x140045d6f  lea     rsi, WPP_GLOBAL_Control
0x140045d76  cmp     [rdi+38h], rbx
0x140045d7a  jz      short loc_140045D99
0x140045d7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140045d83  cmp     rcx, rsi
0x140045d86  jz      short loc_140045D99
0x140045d88  mov     rcx, [rcx+18h]
0x140045d8c  mov     edx, 172h
0x140045d91  mov     r8, r15
0x140045d94  call    WPP_SF_
0x140045d99  cmp     [rdi+48h], rbx
0x140045d9d  jz      short loc_140045DBC
0x140045d9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140045da6  cmp     rcx, rsi
0x140045da9  jz      short loc_140045DBC
0x140045dab  mov     rcx, [rcx+18h]
0x140045daf  mov     edx, 173h
0x140045db4  mov     r8, r15
0x140045db7  call    WPP_SF_
0x140045dbc  cmp     [rdi+60h], rbx
0x140045dc0  jz      short loc_140045DDF
0x140045dc2  mov     rcx, cs:WPP_GLOBAL_Control
0x140045dc9  cmp     rcx, rsi
0x140045dcc  jz      short loc_140045DDF
0x140045dce  mov     rcx, [rcx+18h]
0x140045dd2  mov     edx, 174h
0x140045dd7  mov     r8, r15
0x140045dda  call    WPP_SF_
0x140045ddf  cmp     [rdi+70h], rbx
0x140045de3  jz      short loc_140045E02
0x140045de5  mov     rcx, cs:WPP_GLOBAL_Control
0x140045dec  cmp     rcx, rsi
0x140045def  jz      short loc_140045E02
0x140045df1  mov     rcx, [rcx+18h]
0x140045df5  mov     edx, 175h
0x140045dfa  mov     r8, r15
0x140045dfd  call    WPP_SF_
0x140045e02  call    Feature_53299205__private_IsEnabledDeviceUsageNoInline
0x140045e07  test    eax, eax
0x140045e09  jz      loc_140045EED
0x140045e0f  cmp     [rdi+0B0h], rbx
0x140045e16  jz      short loc_140045E35
0x140045e18  mov     rcx, cs:WPP_GLOBAL_Control
0x140045e1f  cmp     rcx, rsi
0x140045e22  jz      short loc_140045E35
0x140045e24  mov     rcx, [rcx+18h]
0x140045e28  mov     edx, 176h
0x140045e2d  mov     r8, r15
0x140045e30  call    WPP_SF_
0x140045e35  mov     r9d, [rbp+var_28]
0x140045e39  add     r12, 10h
0x140045e3d  mov     eax, [r14+24h]
0x140045e41  mov     rdx, r12; struct _NWF_KEY_CONTEXT *
0x140045e44  mov     ecx, [r14+14h]
0x140045e48  add     rax, r14
0x140045e4b  mov     qword ptr [rsp+78h+var_40], rax; unsigned int
0x140045e50  add     rcx, r14
0x140045e53  mov     eax, [r14+28h]
0x140045e57  mov     dword ptr [rsp+78h+var_48], eax; unsigned __int8 *
0x140045e5b  mov     eax, [r14+18h]
0x140045e5f  shr     r9d, 0Eh
0x140045e63  mov     [rsp+78h+var_50], rcx; unsigned int
0x140045e68  and     r9b, 1; bool
0x140045e6c  cmp     [r14+10h], bl
0x140045e70  mov     rcx, rdi; this
0x140045e73  mov     dword ptr [rsp+78h+var_58], eax; bool
0x140045e77  setnz   r8b; unsigned __int8 *
0x140045e7b  call    ?GetRsnAndRsnXeIEsAfterAssociation@RsnOConnection@@YAJPEAU_NWF_KEY_CONTEXT@@QEBE_N2KPEAEK3@Z; RsnOConnection::GetRsnAndRsnXeIEsAfterAssociation(_NWF_KEY_CONTEXT *,uchar const * const,bool,bool,ulong,uchar *,ulong,uchar *)
0x140045e80  test    eax, eax
0x140045e82  jz      loc_140045F3F
0x140045e88  mov     rcx, [rdi+58h]
0x140045e8c  test    rcx, rcx
0x140045e8f  jz      short loc_140045EC4
0x140045e91  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140045e95  mov     rax, [rcx]
0x140045e98  test    rax, rax
0x140045e9b  jz      short loc_140045EB1
0x140045e9d  mov     rdx, rcx; Entry
0x140045ea0  mov     rcx, rax; Lookaside
0x140045ea3  call    cs:__imp_ExFreeToNPagedLookasideList
0x140045eaa  nop     dword ptr [rax+rax+00h]
0x140045eaf  jmp     short loc_140045EC0
0x140045eb1  mov     edx, [rcx+8]; Tag
0x140045eb4  call    cs:__imp_ExFreePoolWithTag
0x140045ebb  nop     dword ptr [rax+rax+00h]
0x140045ec0  mov     [rdi+58h], rbx
0x140045ec4  mov     rcx, cs:WPP_GLOBAL_Control
0x140045ecb  cmp     rcx, rsi
0x140045ece  jz      loc_14004638D
0x140045ed4  mov     edx, 177h
0x140045ed9  mov     rcx, [rcx+18h]
0x140045edd  mov     r9, r12
0x140045ee0  mov     r8, r15
0x140045ee3  call    WPP_SF__MAC_
0x140045ee8  jmp     loc_14004638D
0x140045eed  mov     eax, [r14+24h]
0x140045ef1  add     r12, 10h
0x140045ef5  mov     ecx, [r14+14h]
0x140045ef9  add     rax, r14
0x140045efc  mov     r9d, [r14+18h]; unsigned int
0x140045f00  add     rcx, r14
0x140045f03  mov     r8b, [r14+10h]; unsigned __int8
0x140045f07  mov     rdx, r12; unsigned __int8 *
0x140045f0a  mov     [rsp+78h+var_48], rax; unsigned __int8 *
0x140045f0f  mov     eax, [r14+28h]
0x140045f13  mov     dword ptr [rsp+78h+var_50], eax; unsigned int
0x140045f17  mov     [rsp+78h+var_58], rcx; Src
0x140045f1c  mov     rcx, rdi; struct _NWF_KEY_CONTEXT *
0x140045f1f  call    ?CDRollback_GetRsnAndRsnXeIEsAfterAssociation@@YAJPEAU_NWF_KEY_CONTEXT@@QEBEEKPEAEK2@Z; CDRollback_GetRsnAndRsnXeIEsAfterAssociation(_NWF_KEY_CONTEXT *,uchar const * const,uchar,ulong,uchar *,ulong,uchar *)
0x140045f24  test    eax, eax
0x140045f26  jz      short loc_140045F3F
0x140045f28  mov     rcx, cs:WPP_GLOBAL_Control
0x140045f2f  cmp     rcx, rsi
0x140045f32  jz      loc_14004638D
0x140045f38  mov     edx, 178h
  ... truncated ...
```
