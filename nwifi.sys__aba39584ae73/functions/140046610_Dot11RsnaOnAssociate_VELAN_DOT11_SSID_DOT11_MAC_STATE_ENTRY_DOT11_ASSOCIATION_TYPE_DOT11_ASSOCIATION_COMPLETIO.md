# Dot11RsnaOnAssociate(_VELAN *,_DOT11_SSID *,DOT11_MAC_STATE_ENTRY *,_DOT11_ASSOCIATION_TYPE,DOT11_ASSOCIATION_COMPLETION_PARAMETERS *,ulong,DOT11_CONNECTION_INFO *)

- ea: `0x140046610`
- end: `0x140046f45`
- name: `?Dot11RsnaOnAssociate@@YAXPEAU_VELAN@@PEAU_DOT11_SSID@@PEAUDOT11_MAC_STATE_ENTRY@@W4_DOT11_ASSOCIATION_TYPE@@PEAUDOT11_ASSOCIATION_COMPLETION_PARAMETERS@@KPEAUDOT11_CONNECTION_INFO@@@Z`
- size: `2357`
- prototype: `void __fastcall(_QWORD *, struct _DOT11_SSID *, struct DOT11_MAC_STATE_ENTRY *, int, struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *, unsigned int, void *Src)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14005e1fc`

## callees

- `0x14000d21c`
- `0x140020dc0`
- `0x140020f20`
- `0x140023730`
- `0x140030244`
- `0x140036918`
- `0x14003a484`
- `0x14003a814`
- `0x14003b04c`
- `0x140040680`
- `0x140040efc`
- `0x140041e34`
- `0x140046610`
- `0x140048c20`
- `0x14004a604`
- `0x14004a904`
- `0x14004ba84`
- `0x14004bf04`
- `0x140053f88`
- `0x140053fe0`
- `0x1400541ac`
- `0x140054700`
- `0x140054cd4`
- `0x140090bd8`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004670b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004670b`
- `ntoskrnl!ExAllocatePool2` at `0x140046724`
- `ntoskrnl!ExAllocatePool2` at `0x140046724`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400467db`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004681b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046a23`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046dc3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046e11`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046ec6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400467db`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004681b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046a23`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046dc3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046e11`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046ec6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400467ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004682c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046a34`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046e22`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046e3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046ed7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400467ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004682c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046a34`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046e22`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046e3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046ed7`

## pseudocode

```c
void __fastcall Dot11RsnaOnAssociate(
        _QWORD *a1,
        struct _DOT11_SSID *a2,
        struct DOT11_MAC_STATE_ENTRY *a3,
        int a4,
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
  _DOT11_CIPHER_ALGORITHM MulticastCipher; // r8d
  _DOT11_CIPHER_ALGORITHM MulticastMgmtCipher; // eax
  struct _NWF_KEY_CONTEXT *v19; // rdx
  unsigned __int8 *pAssocRequestRsnIE; // rcx
  unsigned __int8 *v21; // rcx
  unsigned __int8 *pAssocRequestRsnXeIE; // rcx
  unsigned __int8 *v23; // rcx
  _DOT11_AUTH_ALGORITHM AuthAlgo; // ecx
  const unsigned __int8 *v25; // r8
  unsigned __int8 *MacKey; // r12
  DOT11_CONNECTION_INFO *pConnectionInfo; // rcx
  int *p_Rssi; // rcx
  PDEVICE_OBJECT v29; // rcx
  __int64 v30; // rdx
  enum _DOT11_AUTH_ALGORITHM v31; // ecx
  unsigned int assocRequestRsnIELength; // r9d
  unsigned __int8 *v33; // r8
  unsigned int v34; // edx
  unsigned __int8 *pBeaconRsnIE; // r8
  enum RSNA_AKM_SUITE v36; // ebx
  unsigned int uAssocReqRSNIESettings; // eax
  __int64 v38; // rdx
  __int64 v39; // r8
  unsigned int v40; // eax
  int v41; // ecx
  BOOL v42; // eax
  bool v43; // zf
  __int64 uAssocRespSize; // r9
  int IsEnabledDeviceUsageNoInline; // eax
  unsigned int v46; // edx
  const unsigned __int8 *v47; // r8
  unsigned __int8 *v48; // r10
  unsigned int v49; // r9d
  struct NWF_FT_CONTEXT *FTContextInformation; // rax
  struct NWF_FT_CONTEXT *v51; // r13
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
            Pool2 = (_DWORD *)ExAllocatePool2(64, v13, 2053731191);
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
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                367,
                WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
                (unsigned int)*v7);
            if ( (unsigned int)Feature_53299205__private_IsEnabledDeviceUsageNoInline() )
            {
              RsnOConnection::CleanupRsnIEs((RsnOConnection *)&v9->KeyContext, v19);
            }
            else
            {
              pAssocRequestRsnIE = v9->KeyContext.pAssocRequestRsnIE;
              if ( pAssocRequestRsnIE )
              {
                v21 = pAssocRequestRsnIE - 16;
                if ( *(_QWORD *)v21 )
                  ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v21, v21);
                else
                  ExFreePoolWithTag(v21, *((_DWORD *)v21 + 2));
                v9->KeyContext.pAssocRequestRsnIE = 0;
              }
              v9->KeyContext.assocRequestRsnIELength = 0;
              pAssocRequestRsnXeIE = v9->KeyContext.pAssocRequestRsnXeIE;
              if ( pAssocRequestRsnXeIE )
              {
                v23 = pAssocRequestRsnXeIE - 16;
                if ( *(_QWORD *)v23 )
                  ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v23, v23);
                else
                  ExFreePoolWithTag(v23, *((_DWORD *)v23 + 2));
                v9->KeyContext.pAssocRequestRsnXeIE = 0;
              }
              v9->KeyContext.assocRequestRsnIELength = 0;
            }
            return;
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
    goto LABEL_21;
  }
LABEL_23:
  v9->KeyContext.AuthAlgo = v11->AuthAlgo;
  UnicastCipher = (unsigned int)v11->UnicastCipher;
  v9->KeyContext.UcastCipher = UnicastCipher;
  MulticastCipher = v11->MulticastCipher;
  v9->KeyContext.McastCipher = MulticastCipher;
  if ( v11->Header.Revision < 2u )
    MulticastMgmtCipher = DOT11_CIPHER_ALGO_NONE;
  else
    MulticastMgmtCipher = v11->MulticastMgmtCipher;
  v9->KeyContext.McastMgmtCipher = MulticastMgmtCipher;
  AuthAlgo = v11->AuthAlgo;
  if ( AuthAlgo == DOT11_AUTH_ALGO_WPA3_SAE )
  {
    if ( MulticastMgmtCipher != DOT11_CIPHER_ALGO_BIP && MulticastMgmtCipher != DOT11_CIPHER_ALGO_BIP_GMAC_256 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          368,
          WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
          (unsigned int)MulticastMgmtCipher);
      return;
    }
  }
  else if ( AuthAlgo == DOT11_AUTH_ALGO_WPA3
         && ((_DWORD)UnicastCipher != 9
          || MulticastCipher != DOT11_CIPHER_ALGO_GCMP_256
          || MulticastMgmtCipher != DOT11_CIPHER_ALGO_BIP_GMAC_256) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_lll(
        WPP_GLOBAL_Control->AttachedDevice,
        369,
        WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
        UnicastCipher,
        MulticastCipher,
        MulticastMgmtCipher);
    return;
  }
  if ( v9->KeyContext.pAssocRequestRsnIE && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 370, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
  if ( v9->KeyContext.pAssocRequestRsnXeIE && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 371, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
  if ( v9->KeyContext.pBeaconRsnIE && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 372, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
  if ( v9->KeyContext.pBeaconRsnXeIE && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 373, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
  if ( !(unsigned int)Feature_53299205__private_IsEnabledDeviceUsageNoInline() )
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
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return;
      v30 = 376;
LABEL_76:
      WPP_SF__MAC_(v29->AttachedDevice, v30, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, MacKey);
      return;
    }
LABEL_80:
    v31 = v9->KeyContext.AuthAlgo;
    if ( (unsigned int)(v31 - 3) > 8
      || v11->Header.Revision < 2u
      || v9->KeyContext.pBeaconRsnIE && v9->KeyContext.beaconRsnIELength )
    {
      assocRequestRsnIELength = v9->KeyContext.assocRequestRsnIELength;
      v33 = v9->KeyContext.pAssocRequestRsnIE;
      v34 = (unsigned int)Src;
      v9->KeyContext.uAssocReqRSNIESettings = 0;
      v9->KeyContext.beaconRsnIESettings = 0;
      GetRSNIESettings(v31, v34, v33, assocRequestRsnIELength, &v9->KeyContext.uAssocReqRSNIESettings, v65);
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
      v36 = v65[0];
      v9->KeyContext.associatedAkm = v65[0];
      if ( (unsigned int)Feature_Bugfix_58508574__private_IsEnabledDeviceUsageNoInline() )
        v9->Dot11PmkCache.associatedAkm = v9->KeyContext.associatedAkm;
      GetEapolKeyInfoFromAkm(v9, (unsigned __int8 (*)[6])MacKey, v36, &v9->KeyContext.EapolKeyInfo);
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
      if ( (unsigned int)Feature_53299205__private_IsEnabledDeviceUsageNoInline() )
        v9->KeyContext.adapterConnectionCapabilityFlags = v9->pAdapt->AdapterEnhancedCapabilities.AdapterConnectionCapabilityFlags;
      v9->KeyContext.Ssid = *v67;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_DDddddd(
          WPP_GLOBAL_Control->AttachedDevice,
          v38,
          v39,
          (unsigned int)Src,
          v64,
          v9->KeyContext.AuthAlgo,
          v9->KeyContext.UcastCipher,
          v9->KeyContext.McastCipher,
          v9->KeyContext.McastMgmtCipher,
          v9->KeyContext.KeyDescriptorVersion);
      v40 = v9->KeyContext.AuthAlgo;
      v9->KeyContext.TxReplayCounter = 0;
      v42 = 0;
      if ( v40 <= 0xB )
      {
        v41 = 2368;
        if ( _bittest(&v41, v40) )
        {
          if ( v68->pPmk || v9->KeyContext.pOpPmk )
            v42 = 1;
        }
      }
      v43 = v69 == 2;
      v9->KeyContext.bFastRoaming = v42;
      v9->KeyContext.bFTAKM = 0;
      v9->KeyContext.bIsPBSSNotInDS = v43;
      if ( (v9->KeyContext.uAssocReqRSNIESettings & 0xC) == 0 )
        goto LABEL_110;
      uAssocRespSize = v11->uAssocRespSize;
      if ( (unsigned int)uAssocRespSize < 6 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_Dd(
            WPP_GLOBAL_Control->AttachedDevice,
            378,
            WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
            uAssocRespSize,
            6);
      }
      else
      {
        IsEnabledDeviceUsageNoInline = Feature_Bugfix_53850044__private_IsEnabledDeviceUsageNoInline();
        v46 = v9->KeyContext.assocRequestRsnIELength;
        v47 = &v11->MacAddr[v11->uAssocRespOffset + 2];
        v48 = v9->KeyContext.pAssocRequestRsnIE;
        v49 = v11->uAssocRespSize - 6;
        if ( IsEnabledDeviceUsageNoInline )
          FTContextInformation = GetFTContextInformation(v67, 0, v47, v49, v48, v46, 0, 0, 0);
        else
          FTContextInformation = CDRollback_GetFTContextInformation(
                                   v67,
                                   0,
                                   v47,
                                   v49,
                                   (struct DOT11_INFO_ELEMENT *)v48,
                                   v46,
                                   0,
                                   0);
        v51 = FTContextInformation;
        if ( FTContextInformation )
        {
          *((_DWORD *)v12 + 322) = 1;
          FreeFTContext((struct NWF_FT_CONTEXT **)v12 + 162);
          v12[162] = v51;
          v9 = v66;
LABEL_110:
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
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 380, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 374, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
  MacKey = a3->MacHashEntry.MacKey;
  LODWORD(v62) = v11->uBeaconSize;
  LOBYTE(v25) = v11->bReAssocReq != 0;
  if ( !(unsigned int)RsnOConnection::GetRsnAndRsnXeIEsAfterAssociation(
                        (RsnOConnection *)&v9->KeyContext,
                        (struct _NWF_KEY_CONTEXT *)MacKey,
                        v25,
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
  v29 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    v30 = 375;
    goto LABEL_76;
  }
}

```

## disassembly

```asm
0x140046610  mov     rax, rsp
0x140046613  mov     [rax+20h], r9d
0x140046617  mov     [rax+18h], r8
0x14004661b  mov     [rax+10h], rdx
0x14004661f  mov     [rax+8], rcx
0x140046623  push    rbp
0x140046624  push    rbx
0x140046625  push    rsi
0x140046626  push    rdi
0x140046627  push    r12
0x140046629  push    r13
0x14004662b  push    r14
0x14004662d  push    r15
0x14004662f  mov     rbp, rsp
0x140046632  sub     rsp, 78h
0x140046636  mov     rbx, [rbp+Src]
0x14004663a  xor     r15d, r15d
0x14004663d  mov     r12, r8
0x140046640  mov     r13, rcx
0x140046643  test    rbx, rbx
0x140046646  jz      short loc_140046656
0x140046648  mov     ecx, [rbx+8]
0x14004664b  mov     [rbp+var_28], ecx
0x14004664e  mov     ecx, [rbx+4]
0x140046651  mov     dword ptr [rbp+Src], ecx
0x140046654  jmp     short loc_14004665E
0x140046656  mov     [rbp+var_28], r15d
0x14004665a  mov     dword ptr [rbp+Src], r15d
0x14004665e  mov     rax, [r13+16F0h]
0x140046665  mov     [rbp+var_18], 0AC0F00h
0x14004666c  cmp     [r13+1700h], rax
0x140046673  jnz     loc_140046F33
0x140046679  mov     r14, [rbp+arg_20]
0x14004667d  lea     rdi, [r13+1710h]
0x140046684  mov     eax, [r14+34h]
0x140046688  sub     eax, 6
0x14004668b  cmp     eax, 5
0x14004668e  jbe     short loc_140046698
0x140046690  mov     [rdi], r15d
0x140046693  jmp     loc_140046F33
0x140046698  cmp     [r14+14h], r15d
0x14004669c  jz      loc_140046F01
0x1400466a2  cmp     dword ptr [r14+18h], 0Ah
0x1400466a7  jb      loc_140046F01
0x1400466ad  test    rbx, rbx
0x1400466b0  jz      loc_140046752
0x1400466b6  mov     eax, [rbx]
0x1400466b8  add     eax, 10h
0x1400466bb  mov     [rdi+58h], r15
0x1400466bf  cmp     eax, 10h
0x1400466c2  jb      loc_14004677F
0x1400466c8  mov     ecx, 40h ; '@'
0x1400466cd  cmp     eax, ecx
0x1400466cf  ja      short loc_1400466DA
0x1400466d1  lea     rsi, WPP_MAIN_CB.DeviceQueue
0x1400466d8  jmp     short loc_140046708
0x1400466da  cmp     eax, 100h
0x1400466df  ja      short loc_1400466EA
0x1400466e1  lea     rsi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400466e8  jmp     short loc_140046708
0x1400466ea  cmp     eax, 400h
0x1400466ef  ja      short loc_1400466FA
0x1400466f1  lea     rsi, Lookaside
0x1400466f8  jmp     short loc_140046708
0x1400466fa  cmp     eax, 800h
0x1400466ff  ja      short loc_140046719
0x140046701  lea     rsi, stru_1400B31C0
0x140046708  mov     rcx, rsi; Lookaside
0x14004670b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140046712  nop     dword ptr [rax+rax+00h]
0x140046717  jmp     short loc_140046730
0x140046719  mov     edx, eax
0x14004671b  mov     r8d, 7A697377h
0x140046721  mov     rsi, r15
0x140046724  call    cs:__imp_ExAllocatePool2
0x14004672b  nop     dword ptr [rax+rax+00h]
0x140046730  test    rax, rax
0x140046733  jz      short loc_14004677F
0x140046735  mov     [rax], rsi
0x140046738  lea     rcx, [rax+10h]; void *
0x14004673c  mov     dword ptr [rax+8], 7A697377h
0x140046743  mov     rdx, rbx; Src
0x140046746  mov     [rdi+58h], rcx
0x14004674a  mov     r8d, [rbx]; Size
0x14004674d  call    memmove
0x140046752  mov     eax, [r14+34h]
0x140046756  xor     ebx, ebx
0x140046758  mov     [rdi+0Ch], eax
0x14004675b  mov     r9d, [r14+38h]
0x14004675f  mov     [rdi+10h], r9d
0x140046763  mov     r8d, [r14+3Ch]
0x140046767  mov     [rdi+14h], r8d
0x14004676b  cmp     byte ptr [r14+1], 2
0x140046770  jb      loc_140046845
0x140046776  mov     eax, [r14+58h]
0x14004677a  jmp     loc_140046847
0x14004677f  mov     rcx, cs:WPP_GLOBAL_Control
0x140046786  lea     rsi, WPP_GLOBAL_Control
0x14004678d  cmp     rcx, rsi
0x140046790  jz      short loc_1400467AA
0x140046792  mov     r9d, [rbx]
0x140046795  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004679c  mov     rcx, [rcx+18h]
0x1400467a0  mov     edx, 16Fh
0x1400467a5  call    WPP_SF_d
0x1400467aa  call    Feature_53299205__private_IsEnabledDeviceUsageNoInline
0x1400467af  test    eax, eax
0x1400467b1  jz      short loc_1400467C0
0x1400467b3  mov     rcx, rdi; this
0x1400467b6  call    ?CleanupRsnIEs@RsnOConnection@@YAXPEAU_NWF_KEY_CONTEXT@@@Z; RsnOConnection::CleanupRsnIEs(_NWF_KEY_CONTEXT *)
0x1400467bb  jmp     loc_140046F33
0x1400467c0  mov     rcx, [rdi+38h]
0x1400467c4  test    rcx, rcx
0x1400467c7  jz      short loc_1400467FC
0x1400467c9  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400467cd  mov     rax, [rcx]
0x1400467d0  test    rax, rax
0x1400467d3  jz      short loc_1400467E9
0x1400467d5  mov     rdx, rcx; Entry
0x1400467d8  mov     rcx, rax; Lookaside
0x1400467db  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400467e2  nop     dword ptr [rax+rax+00h]
0x1400467e7  jmp     short loc_1400467F8
0x1400467e9  mov     edx, [rcx+8]; Tag
0x1400467ec  call    cs:__imp_ExFreePoolWithTag
0x1400467f3  nop     dword ptr [rax+rax+00h]
0x1400467f8  mov     [rdi+38h], r15
0x1400467fc  mov     [rdi+40h], r15d
0x140046800  mov     rcx, [rdi+48h]
0x140046804  test    rcx, rcx
0x140046807  jz      short loc_14004683C
0x140046809  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14004680d  mov     rax, [rcx]
0x140046810  test    rax, rax
0x140046813  jz      short loc_140046829
0x140046815  mov     rdx, rcx; Entry
0x140046818  mov     rcx, rax; Lookaside
0x14004681b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140046822  nop     dword ptr [rax+rax+00h]
0x140046827  jmp     short loc_140046838
0x140046829  mov     edx, [rcx+8]; Tag
0x14004682c  call    cs:__imp_ExFreePoolWithTag
0x140046833  nop     dword ptr [rax+rax+00h]
0x140046838  mov     [rdi+48h], r15
0x14004683c  mov     [rdi+40h], r15d
0x140046840  jmp     loc_140046F33
0x140046845  mov     eax, ebx
0x140046847  mov     [rdi+18h], eax
0x14004684a  mov     ecx, [r14+34h]
0x14004684e  cmp     ecx, 9
0x140046851  jnz     short loc_140046899
0x140046853  cmp     eax, 6
0x140046856  jz      loc_1400468E8
0x14004685c  cmp     eax, 0Ch
0x14004685f  jz      loc_1400468E8
0x140046865  mov     rcx, cs:WPP_GLOBAL_Control
0x14004686c  lea     rsi, WPP_GLOBAL_Control
0x140046873  cmp     rcx, rsi
0x140046876  jz      loc_140046F33
0x14004687c  mov     rcx, [rcx+18h]
0x140046880  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x140046887  mov     edx, 170h
0x14004688c  mov     r9d, eax
0x14004688f  call    WPP_SF_d
0x140046894  jmp     loc_140046F33
0x140046899  cmp     ecx, 8
0x14004689c  jnz     short loc_1400468E8
0x14004689e  cmp     r9d, 9
0x1400468a2  jnz     short loc_1400468AE
0x1400468a4  cmp     r8d, r9d
0x1400468a7  jnz     short loc_1400468AE
0x1400468a9  cmp     eax, 0Ch
0x1400468ac  jz      short loc_1400468E8
0x1400468ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400468b5  lea     rsi, WPP_GLOBAL_Control
0x1400468bc  cmp     rcx, rsi
0x1400468bf  jz      loc_140046F33
0x1400468c5  mov     rcx, [rcx+18h]
0x1400468c9  mov     edx, 171h
0x1400468ce  mov     dword ptr [rsp+78h+var_50], eax
0x1400468d2  mov     dword ptr [rsp+78h+var_58], r8d
0x1400468d7  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x1400468de  call    WPP_SF_lll
0x1400468e3  jmp     loc_140046F33
0x1400468e8  lea     r15, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x1400468ef  lea     rsi, WPP_GLOBAL_Control
0x1400468f6  cmp     [rdi+38h], rbx
0x1400468fa  jz      short loc_140046919
0x1400468fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140046903  cmp     rcx, rsi
0x140046906  jz      short loc_140046919
0x140046908  mov     rcx, [rcx+18h]
0x14004690c  mov     edx, 172h
0x140046911  mov     r8, r15
0x140046914  call    WPP_SF_
0x140046919  cmp     [rdi+48h], rbx
0x14004691d  jz      short loc_14004693C
0x14004691f  mov     rcx, cs:WPP_GLOBAL_Control
0x140046926  cmp     rcx, rsi
0x140046929  jz      short loc_14004693C
0x14004692b  mov     rcx, [rcx+18h]
0x14004692f  mov     edx, 173h
0x140046934  mov     r8, r15
0x140046937  call    WPP_SF_
0x14004693c  cmp     [rdi+60h], rbx
0x140046940  jz      short loc_14004695F
0x140046942  mov     rcx, cs:WPP_GLOBAL_Control
0x140046949  cmp     rcx, rsi
0x14004694c  jz      short loc_14004695F
0x14004694e  mov     rcx, [rcx+18h]
0x140046952  mov     edx, 174h
0x140046957  mov     r8, r15
0x14004695a  call    WPP_SF_
0x14004695f  cmp     [rdi+70h], rbx
0x140046963  jz      short loc_140046982
0x140046965  mov     rcx, cs:WPP_GLOBAL_Control
0x14004696c  cmp     rcx, rsi
0x14004696f  jz      short loc_140046982
0x140046971  mov     rcx, [rcx+18h]
0x140046975  mov     edx, 175h
0x14004697a  mov     r8, r15
0x14004697d  call    WPP_SF_
0x140046982  call    Feature_53299205__private_IsEnabledDeviceUsageNoInline
0x140046987  test    eax, eax
0x140046989  jz      loc_140046A6D
0x14004698f  cmp     [rdi+0B0h], rbx
0x140046996  jz      short loc_1400469B5
0x140046998  mov     rcx, cs:WPP_GLOBAL_Control
0x14004699f  cmp     rcx, rsi
0x1400469a2  jz      short loc_1400469B5
0x1400469a4  mov     rcx, [rcx+18h]
0x1400469a8  mov     edx, 176h
0x1400469ad  mov     r8, r15
0x1400469b0  call    WPP_SF_
0x1400469b5  mov     r9d, [rbp+var_28]
0x1400469b9  add     r12, 10h
0x1400469bd  mov     eax, [r14+24h]
0x1400469c1  mov     rdx, r12; struct _NWF_KEY_CONTEXT *
0x1400469c4  mov     ecx, [r14+14h]
0x1400469c8  add     rax, r14
0x1400469cb  mov     qword ptr [rsp+78h+var_40], rax; unsigned int
0x1400469d0  add     rcx, r14
0x1400469d3  mov     eax, [r14+28h]
0x1400469d7  mov     dword ptr [rsp+78h+var_48], eax; unsigned __int8 *
0x1400469db  mov     eax, [r14+18h]
0x1400469df  shr     r9d, 0Eh
0x1400469e3  mov     [rsp+78h+var_50], rcx; unsigned int
0x1400469e8  and     r9b, 1; bool
0x1400469ec  cmp     [r14+10h], bl
0x1400469f0  mov     rcx, rdi; this
0x1400469f3  mov     dword ptr [rsp+78h+var_58], eax; bool
0x1400469f7  setnz   r8b; unsigned __int8 *
0x1400469fb  call    ?GetRsnAndRsnXeIEsAfterAssociation@RsnOConnection@@YAJPEAU_NWF_KEY_CONTEXT@@QEBE_N2KPEAEK3@Z; RsnOConnection::GetRsnAndRsnXeIEsAfterAssociation(_NWF_KEY_CONTEXT *,uchar const * const,bool,bool,ulong,uchar *,ulong,uchar *)
0x140046a00  test    eax, eax
0x140046a02  jz      loc_140046ABF
0x140046a08  mov     rcx, [rdi+58h]
0x140046a0c  test    rcx, rcx
0x140046a0f  jz      short loc_140046A44
0x140046a11  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140046a15  mov     rax, [rcx]
0x140046a18  test    rax, rax
0x140046a1b  jz      short loc_140046A31
0x140046a1d  mov     rdx, rcx; Entry
0x140046a20  mov     rcx, rax; Lookaside
0x140046a23  call    cs:__imp_ExFreeToNPagedLookasideList
0x140046a2a  nop     dword ptr [rax+rax+00h]
0x140046a2f  jmp     short loc_140046A40
0x140046a31  mov     edx, [rcx+8]; Tag
0x140046a34  call    cs:__imp_ExFreePoolWithTag
0x140046a3b  nop     dword ptr [rax+rax+00h]
0x140046a40  mov     [rdi+58h], rbx
0x140046a44  mov     rcx, cs:WPP_GLOBAL_Control
0x140046a4b  cmp     rcx, rsi
0x140046a4e  jz      loc_140046F33
0x140046a54  mov     edx, 177h
0x140046a59  mov     rcx, [rcx+18h]
0x140046a5d  mov     r9, r12
0x140046a60  mov     r8, r15
0x140046a63  call    WPP_SF__MAC_
0x140046a68  jmp     loc_140046F33
0x140046a6d  mov     eax, [r14+24h]
0x140046a71  add     r12, 10h
0x140046a75  mov     ecx, [r14+14h]
0x140046a79  add     rax, r14
0x140046a7c  mov     r9d, [r14+18h]; unsigned int
0x140046a80  add     rcx, r14
0x140046a83  mov     r8b, [r14+10h]; unsigned __int8
0x140046a87  mov     rdx, r12; unsigned __int8 *
0x140046a8a  mov     [rsp+78h+var_48], rax; unsigned __int8 *
0x140046a8f  mov     eax, [r14+28h]
0x140046a93  mov     dword ptr [rsp+78h+var_50], eax; unsigned int
0x140046a97  mov     [rsp+78h+var_58], rcx; Src
0x140046a9c  mov     rcx, rdi; struct _NWF_KEY_CONTEXT *
0x140046a9f  call    ?CDRollback_GetRsnAndRsnXeIEsAfterAssociation@@YAJPEAU_NWF_KEY_CONTEXT@@QEBEEKPEAEK2@Z; CDRollback_GetRsnAndRsnXeIEsAfterAssociation(_NWF_KEY_CONTEXT *,uchar const * const,uchar,ulong,uchar *,ulong,uchar *)
0x140046aa4  test    eax, eax
0x140046aa6  jz      short loc_140046ABF
0x140046aa8  mov     rcx, cs:WPP_GLOBAL_Control
0x140046aaf  cmp     rcx, rsi
0x140046ab2  jz      loc_140046F33
0x140046ab8  mov     edx, 178h
  ... truncated ...
```
