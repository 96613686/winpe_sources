# Dot11ReceiveM1

- ea: `0x140043c60`
- end: `0x140044a40`
- name: `Dot11ReceiveM1`
- size: `3552`
- prototype: `void __fastcall(struct _VELAN *, __int64, struct NWF_EAPOL_HEADER *, struct _LOCK_STATE_EX *)`
- caller_count: `3`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140042884`
- `0x1400430e0`
- `0x14004ed8c`

## callees

- `0x1400012bc`
- `0x140001544`
- `0x14000170c`
- `0x14000a378`
- `0x14000a82c`
- `0x14000a944`
- `0x14000d22c`
- `0x14000d2c0`
- `0x140013b90`
- `0x140018a0c`
- `0x140020dc0`
- `0x140020e04`
- `0x140032b68`
- `0x140035704`
- `0x1400366f8`
- `0x140039a88`
- `0x14003ae2c`
- `0x140043354`
- `0x140043c60`
- `0x140047704`
- `0x140047b40`
- `0x1400488e4`
- `0x140048fb4`
- `0x140051154`
- `0x140090440`
- `0x140095c0c`
- `0x140095de0`
- `0x140095ea4`
- `0x14009a3d0`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140043fb3`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400442fa`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140043fb3`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400442fa`
- `ntoskrnl!ExAllocatePool2` at `0x140043fcb`
- `ntoskrnl!ExAllocatePool2` at `0x140044315`
- `ntoskrnl!ExAllocatePool2` at `0x140043fcb`
- `ntoskrnl!ExAllocatePool2` at `0x140044315`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140043f24`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004426d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140044564`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400449b8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140043f24`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004426d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140044564`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400449b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043f35`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004427e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044575`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400449c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043f35`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004427e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044575`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400449c9`
- `cng!SystemPrng` at `0x1400443a7`
- `cng!SystemPrng` at `0x1400443a7`

## string_xrefs

- `0x1400440da`: `PmkCacheGetAuthInfo [PmkId]: Returning auth info for:`
- `0x1400440f0`: `	PmkCacheGetAuthInfo [PmkId]: PMK:`
- `0x140044105`: `	PmkCacheGetAuthInfo [PmkId]: PMKID:`

## pseudocode

```c
void __fastcall Dot11ReceiveM1(struct _VELAN *a1, __int64 a2, struct NWF_EAPOL_HEADER *a3, struct _LOCK_STATE_EX *a4)
{
  struct NWF_EAPOL_HEADER *pEapolHdr; // r15
  _NWF_KEY_CONTEXT *p_KeyContext; // rbx
  BOOL v9; // esi
  enum _DOT11_CIPHER_ALGORITHM v10; // edx
  stringify *McastMgmtCipher; // rcx
  const char *v12; // rax
  stringify *McastCipher; // rcx
  enum _DOT11_CIPHER_ALGORITHM v14; // edx
  const char *v15; // rax
  stringify *UcastCipher; // rcx
  enum _DOT11_CIPHER_ALGORITHM v17; // edx
  const char *v18; // rax
  stringify *AkmSuite; // rcx
  enum RSNA_AKM_SUITE v20; // edx
  const char *v21; // rax
  stringify *AuthAlgo; // rcx
  enum _DOT11_AUTH_ALGORITHM v23; // edx
  __int64 v24; // rdx
  __int64 v25; // rax
  int v26; // r8d
  int v27; // r9d
  unsigned int uSSIDLength; // ecx
  struct _VELAN *v29; // rcx
  _FILE_OBJECT *pSecurityEndpoint; // rdx
  unsigned int v31; // eax
  __int64 v32; // r9
  struct NWF_PMK_ENTRY *v33; // rdi
  struct NWF_EAPOL_HEADER *v34; // rcx
  __int64 v35; // rcx
  unsigned int v36; // ecx
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rdi
  _DWORD *Pool2; // rax
  int v39; // edi
  struct NWF_EAPOL_HEADER *v40; // rcx
  _DOT11_AUTH_ALGORITHM v41; // eax
  unsigned int v42; // r8d
  __int64 v43; // r9
  struct NWF_EAPOL_HEADER *v44; // rcx
  __int64 v45; // rcx
  unsigned int v46; // ecx
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rdi
  _DWORD *v48; // rax
  struct NWF_EAPOL_HEADER *v49; // rcx
  int v50; // eax
  PDEVICE_OBJECT v51; // rcx
  __int64 v52; // rdx
  __int64 v53; // r9
  struct NWF_PMK_ENTRY *v54; // rcx
  _DOT11_AUTH_ALGORITHM v55; // eax
  __int16 v56; // cx
  ULONG *v57; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v58; // rax
  __int64 v59; // rdx
  struct _LOCK_STATE_EX *v60; // rax
  int v61; // r8d
  int v62; // r9d
  unsigned int v63; // ecx
  struct _VELAN *v64; // r9
  struct _VELAN *v65; // rdx
  int v66; // r8d
  int v67; // r9d
  _FILE_OBJECT *v68; // rcx
  struct NWF_EAPOL_HEADER *v69; // rax
  __int128 v70; // xmm0
  __int64 uNextIndex; // rcx
  __int64 v72; // rcx
  int v73; // ecx
  struct NWF_EAPOL_HEADER *v74; // rcx
  struct _VELAN *v75; // rbx
  ULONG *v76; // rcx
  unsigned __int16 v77; // [rsp+30h] [rbp-D0h]
  struct NWF_FT_CONTEXT *pFTContext; // [rsp+38h] [rbp-C8h]
  unsigned __int16 v79[2]; // [rsp+70h] [rbp-90h] BYREF
  struct _VELAN *v80; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v81; // [rsp+80h] [rbp-80h] BYREF
  struct NWF_PMK_ENTRY *ActivePmk; // [rsp+88h] [rbp-78h] BYREF
  int v83; // [rsp+90h] [rbp-70h] BYREF
  const char *v84; // [rsp+98h] [rbp-68h] BYREF
  struct NWF_EAPOL_HEADER *v85; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *ucSSID; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v87; // [rsp+B0h] [rbp-50h]
  __int64 v88; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v89; // [rsp+C0h] [rbp-40h]
  void *p_LockState; // [rsp+C8h] [rbp-38h]
  __int128 v91; // [rsp+D0h] [rbp-30h]
  const char *v92; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v93; // [rsp+E8h] [rbp-18h]
  const char *v94; // [rsp+F0h] [rbp-10h] BYREF
  const char *v95; // [rsp+F8h] [rbp-8h] BYREF
  const char *v96; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v97[272]; // [rsp+110h] [rbp+10h] BYREF
  PLOCK_STATE_EX LockState; // [rsp+220h] [rbp+120h] BYREF
  int v99; // [rsp+228h] [rbp+128h]
  struct _GUID v100; // [rsp+230h] [rbp+130h] BYREF
  struct NWF_PTK v101; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int8 v102[16]; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int128 v103; // [rsp+2C0h] [rbp+1C0h]
  __int128 v104; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int16 v105; // [rsp+2E0h] [rbp+1E0h]
  __int128 v106; // [rsp+2E8h] [rbp+1E8h] BYREF
  __int16 v107; // [rsp+2F8h] [rbp+1F8h]

  v80 = a1;
  LockState = a4;
  v81 = 0;
  *(_OWORD *)v102 = 0;
  v103 = 0;
  memset(&v101, 0, sizeof(v101));
  v83 = 0;
  memset(v97, 0, 0x108u);
  pEapolHdr = a1->KeyContext.M1Cache.pEapolHdr;
  p_KeyContext = &a1->KeyContext;
  v85 = pEapolHdr;
  v104 = 0;
  v9 = a3 == pEapolHdr;
  v105 = 0;
  if ( (unsigned int)dword_1400AE088 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400AE088, 4) )
  {
    McastMgmtCipher = (stringify *)(unsigned int)p_KeyContext->McastMgmtCipher;
    LODWORD(ActivePmk) = p_KeyContext->bFastRoaming;
    *(_DWORD *)v79 = a3 == pEapolHdr;
    v12 = stringify::ToLogString(McastMgmtCipher, v10);
    McastCipher = (stringify *)(unsigned int)p_KeyContext->McastCipher;
    v84 = v12;
    v15 = stringify::ToLogString(McastCipher, v14);
    UcastCipher = (stringify *)(unsigned int)p_KeyContext->UcastCipher;
    v94 = v15;
    v18 = stringify::ToLogString(UcastCipher, v17);
    AkmSuite = (stringify *)(unsigned int)p_KeyContext->EapolKeyInfo.AkmSuite;
    v95 = v18;
    v21 = stringify::ToLogString(AkmSuite, v20);
    AuthAlgo = (stringify *)(unsigned int)p_KeyContext->AuthAlgo;
    v96 = v21;
    v92 = stringify::ToLogString(AuthAlgo, v23);
    v25 = MacAddrToLogString(a2 + 16, v24, &v104);
    uSSIDLength = p_KeyContext->Ssid.uSSIDLength;
    *(_QWORD *)&v100.Data1 = v25;
    if ( uSSIDLength > 0xFFFF )
      uSSIDLength = 0xFFFF;
    v87 = uSSIDLength;
    ucSSID = (unsigned __int16 *)p_KeyContext->Ssid.ucSSID;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      uSSIDLength,
      (unsigned int)byte_1400A4E79,
      v26,
      v27,
      (__int64)&ucSSID,
      (__int64)&v100,
      (__int64)&v92,
      (__int64)&v96,
      (__int64)&v95,
      (__int64)&v94,
      (__int64)&v84,
      (__int64)&ActivePmk,
      (__int64)v79);
  }
  if ( ((p_KeyContext->AuthAlgo - 7) & 0xFFFFFFFD) == 0 && !p_KeyContext->bRSNASecured && p_KeyContext->M2TxCount >= 2 )
  {
    v29 = v80;
    pSecurityEndpoint = v80->pSecurityEndpoint;
    if ( !pSecurityEndpoint )
      goto LABEL_12;
    v31 = *(_DWORD *)(a2 + 16);
    *(_DWORD *)&v100.Data2 = 0;
    v100.Data1 = v31;
    v100.Data2 = *(_WORD *)(a2 + 20);
    *(_DWORD *)v100.Data4 = *(_DWORD *)(a2 + 44);
    p_LockState = &v100;
    v88 = 12;
    v89 = 12;
    v91 = 0;
    NwfUpcallMsg((PIO_CSQ)((char *)pSecurityEndpoint->FsContext + 40), (const struct DOT11_AUTH_UPCALL_REQUEST *)&v88);
  }
  v29 = v80;
LABEL_12:
  if ( v29->KeyContext.AuthAlgo == DOT11_AUTH_ALGO_OWE )
  {
    OWEGetAuthInfo(v29, (struct DOT11_MAC_STATE_ENTRY *)a2);
    v29 = v80;
  }
  ActivePmk = (struct NWF_PMK_ENTRY *)GetActivePmk(v29, a2);
  v33 = ActivePmk;
  if ( !ActivePmk )
  {
    if ( a3 == pEapolHdr )
    {
LABEL_38:
      v9 = 0;
      v39 = 0;
      goto LABEL_119;
    }
    p_KeyContext->bFastRoaming = 0;
    if ( v80->KeyContext.M1Cache.pMacStateEntry )
      Dot11ReleaseMacState(&v80->KeyContext.M1Cache.pMacStateEntry);
    v34 = p_KeyContext->M1Cache.pEapolHdr;
    if ( v34 )
    {
      v35 = (__int64)v34 - 16;
      if ( *(_QWORD *)v35 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v35, (PVOID)v35);
      else
        ExFreePoolWithTag((PVOID)v35, *(_DWORD *)(v35 + 8));
      p_KeyContext->M1Cache.pEapolHdr = 0;
    }
    v36 = (unsigned __int16)__ROR2__(*((_WORD *)a3 + 1), 8) + 20;
    p_KeyContext->M1Cache.pEapolHdr = 0;
    if ( v36 < 0x10 )
      goto LABEL_35;
    if ( v36 > 0x40 )
    {
      if ( v36 > 0x100 )
      {
        if ( v36 > 0x400 )
        {
          if ( v36 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v36, 2053731191, v32);
            goto LABEL_34;
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
LABEL_34:
    if ( !Pool2 )
    {
LABEL_35:
      v39 = -1073741670;
      goto LABEL_119;
    }
    *(_QWORD *)Pool2 = p_WaitListHead;
    Pool2[2] = 2053731191;
    p_KeyContext->M1Cache.pEapolHdr = (struct NWF_EAPOL_HEADER *)(Pool2 + 4);
    _InterlockedIncrement((volatile signed __int32 *)(a2 + 36));
    v40 = p_KeyContext->M1Cache.pEapolHdr;
    p_KeyContext->M1Cache.pMacStateEntry = (DOT11_MAC_STATE_ENTRY *)a2;
    memmove(v40, a3, (unsigned __int16)__ROR2__(*((_WORD *)a3 + 1), 8) + 4LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 299, WPP_e90d411d816e312466897e39e745b158_Traceguids);
    goto LABEL_38;
  }
  v84 = (char *)a3 + 4;
  v41 = p_KeyContext->AuthAlgo;
  if ( v41 == DOT11_AUTH_ALGO_WPA3_SAE )
  {
    *(_DWORD *)v79 = 65;
    if ( (unsigned int)PmkCacheGetAuthInfo(&v80->Dot11PmkCache, a2 + 16, v79, &ActivePmk->149, ActivePmk->PMKID) )
    {
      v33->uSendKeyLength = *(_DWORD *)v79;
      v33->AuthAlgo = DOT11_AUTH_ALGO_WPA3_SAE;
      if ( (v80->pAdapt->uWFATestFlags & 1) != 0 )
      {
        DumpBuff(L"PmkCacheGetAuthInfo [PmkId]: Returning auth info for:", 6u, (unsigned __int8 *)(a2 + 16));
        DumpBuff(L"\tPmkCacheGetAuthInfo [PmkId]: PMK:", v33->uSendKeyLength, v33->ucSendKey);
        DumpBuff(L"\tPmkCacheGetAuthInfo [PmkId]: PMKID:", 0x10u, v33->PMKID);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF__MAC_(WPP_GLOBAL_Control->AttachedDevice, 300, WPP_e90d411d816e312466897e39e745b158_Traceguids, a2 + 16);
      v33->uSendKeyLength = 0;
    }
  }
  else if ( v41 == DOT11_AUTH_ALGO_WPA3 )
  {
    if ( !(unsigned int)PmkCacheGetAuthInfo(&v80->Dot11PmkCache, a2 + 16, 0, 0, ActivePmk->PMKID)
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      WPP_SF__MAC_(WPP_GLOBAL_Control->AttachedDevice, 301, WPP_e90d411d816e312466897e39e745b158_Traceguids, a2 + 16);
    }
  }
  else if ( v80->KeyContext.bFTAKM )
  {
    ActivePmk->MDID = p_KeyContext->pFTContext->MDID;
  }
  v42 = (unsigned __int16)__ROR2__(*(_WORD *)((char *)a3 + 7), 8);
  *(_DWORD *)v79 = v42;
  if ( v42 - 1 > 0x1F )
  {
    v39 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 302, WPP_e90d411d816e312466897e39e745b158_Traceguids, v42);
    goto LABEL_119;
  }
  v39 = ValidateM1KeyData(
          v80,
          (struct DOT11_MAC_STATE_ENTRY *)a2,
          p_KeyContext,
          (unsigned __int16)__ROR2__(*(_WORD *)((char *)a3 + p_KeyContext->EapolKeyInfo.KeyMaterialLengthOffset + 4), 8),
          (unsigned __int8 *)a3 + p_KeyContext->EapolKeyInfo.KeyMaterialOffset + 4,
          &v83,
          &ActivePmk);
  if ( v39 < 0 )
    goto LABEL_119;
  if ( p_KeyContext->bFastRoaming )
  {
    if ( !v83 )
    {
      if ( a3 == v85 )
      {
LABEL_78:
        v9 = 0;
        goto LABEL_119;
      }
      if ( v80->KeyContext.M1Cache.pMacStateEntry )
        Dot11ReleaseMacState(&v80->KeyContext.M1Cache.pMacStateEntry);
      v44 = p_KeyContext->M1Cache.pEapolHdr;
      if ( v44 )
      {
        v45 = (__int64)v44 - 16;
        if ( *(_QWORD *)v45 )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v45, (PVOID)v45);
        else
          ExFreePoolWithTag((PVOID)v45, *(_DWORD *)(v45 + 8));
        p_KeyContext->M1Cache.pEapolHdr = 0;
      }
      v46 = (unsigned __int16)__ROR2__(*((_WORD *)a3 + 1), 8) + 20;
      p_KeyContext->M1Cache.pEapolHdr = 0;
      if ( v46 < 0x10 )
        goto LABEL_35;
      if ( v46 > 0x40 )
      {
        if ( v46 > 0x100 )
        {
          if ( v46 > 0x400 )
          {
            if ( v46 > 0x800 )
            {
              p_DeviceQueue = 0;
              v48 = (_DWORD *)ExAllocatePool2(64, v46, 2053731191, v43);
              goto LABEL_75;
            }
            p_DeviceQueue = &stru_1400B0180;
          }
          else
          {
            p_DeviceQueue = &Lookaside;
          }
        }
        else
        {
          p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
        }
      }
      else
      {
        p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
      }
      v48 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
LABEL_75:
      if ( !v48 )
        goto LABEL_35;
      *(_QWORD *)v48 = p_DeviceQueue;
      v48[2] = 2053731191;
      p_KeyContext->M1Cache.pEapolHdr = (struct NWF_EAPOL_HEADER *)(v48 + 4);
      v39 = 0;
      _InterlockedIncrement((volatile signed __int32 *)(a2 + 36));
      v49 = p_KeyContext->M1Cache.pEapolHdr;
      p_KeyContext->M1Cache.pMacStateEntry = (DOT11_MAC_STATE_ENTRY *)a2;
      memmove(v49, a3, (unsigned __int16)__ROR2__(*((_WORD *)a3 + 1), 8) + 4LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 303, WPP_e90d411d816e312466897e39e745b158_Traceguids);
      goto LABEL_78;
    }
    p_KeyContext->bFastRoaming = 0;
  }
  SystemPrng(v102, 32);
  if ( (unsigned int)Feature_53299205__private_IsEnabledDeviceUsageNoInline()
    && (p_KeyContext->adapterConnectionCapabilityFlags & 0x4000) != 0 )
  {
    *(_DWORD *)((char *)&v103 + 10) = 10121040;
    HIWORD(v103) = 10496;
  }
  pFTContext = p_KeyContext->pFTContext;
  v85 = (struct NWF_EAPOL_HEADER *)(v84 + 13);
  v50 = GeneratePTK(
          v80->CurrentAddress,
          (unsigned __int8 *)(a2 + 16),
          &v80->KeyContext,
          ActivePmk,
          v102,
          (unsigned __int8 *)v84 + 13,
          *(unsigned int *)v79,
          pFTContext,
          &v101);
  v39 = v50;
  if ( v50 < 0 )
  {
    v51 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_119;
    v52 = 304;
    v53 = (unsigned int)v50;
    goto LABEL_86;
  }
  v54 = ActivePmk;
  v55 = p_KeyContext->AuthAlgo;
  v100 = 0;
  ActivePmk->AuthAlgo = v55;
  v54->uTKLength = *(_DWORD *)v79;
  v79[0] = 0;
  ActivePmk = 0;
  Dot11PrepareM2KeyMaterial(v80, v79, (unsigned __int8 **)&ActivePmk);
  v56 = v81 & 0xF8FF | ((p_KeyContext->KeyDescriptorVersion & 7) << 8);
  v81 = v56 ^ ((unsigned __int8)v56 ^ (unsigned __int8)(2 * LOWORD(p_KeyContext->bRSNASecured))) & 2 | 0x801;
  v39 = ElSendSSNKeyPacket(
          v80,
          LockState,
          (struct DOT11_MAC_STATE_ENTRY *)a2,
          (unsigned __int8 (*)[6])v80->CurrentAddress,
          (unsigned __int8 (*)[6])(a2 + 16),
          v81,
          v77,
          *(_QWORD *)(v84 + 5),
          v102,
          v79[0],
          (unsigned __int8 *)ActivePmk,
          v101.PTK,
          &v100);
  if ( ActivePmk )
  {
    v57 = (ULONG *)&ActivePmk[-1].ucKey[51];
    v58 = *(struct _NPAGED_LOOKASIDE_LIST **)&ActivePmk[-1].ucKey[51];
    if ( v58 )
      ExFreeToNPagedLookasideList(v58, v57);
    else
      ExFreePoolWithTag(v57, v57[2]);
  }
  if ( v39 < 0 )
  {
    v51 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      v52 = 305;
      v53 = (unsigned int)v39;
LABEL_86:
      WPP_SF_d(v51->AttachedDevice, v52, WPP_e90d411d816e312466897e39e745b158_Traceguids, v53);
    }
LABEL_119:
    *(_OWORD *)v102 = 0;
    v103 = 0;
    memset(&v101, 0, sizeof(v101));
    if ( v9 )
    {
      Dot11ReleaseMacState(&v80->KeyContext.M1Cache.pMacStateEntry);
      v75 = v80;
      v74 = v80->KeyContext.M1Cache.pEapolHdr;
      if ( v74 )
      {
        v76 = (ULONG *)((char *)v74 - 16);
        if ( *(_QWORD *)v76 )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v76, v76);
        else
          ExFreePoolWithTag(v76, v76[2]);
        v75->KeyContext.M1Cache.pEapolHdr = 0;
      }
    }
    if ( v39 )
    {
      if ( (byte_1400AF801 & 0x40) != 0 )
        McTemplateK0pjq_EtwWriteTransfer(
          (_DWORD)v74,
          (unsigned int)ReceiveM1PacketError,
          (_DWORD)v80 + 4920,
          (unsigned int)&v80,
          (__int64)&v80->gDeviceId,
          v39);
    }
    FreeRSNMessageKeyData((struct NWF_RSN_KEY_DATA *)v97);
    return;
  }
  v107 = 0;
  v106 = 0;
  if ( (unsigned int)dword_1400AE088 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400AE088, 4) )
  {
    ucSSID = &v81;
    v87 = v59 - 2;
    v60 = (struct _LOCK_STATE_EX *)MacAddrToLogString(a2 + 16, v59, &v106);
    v63 = p_KeyContext->Ssid.uSSIDLength;
    LockState = v60;
    if ( v63 > 0xFFFF )
      v63 = 0xFFFF;
    v93 = v63;
    v92 = (const char *)p_KeyContext->Ssid.ucSSID;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapperArray<1>,_tlgWrapperByVal<2>>(
      v63,
      (unsigned int)word_1400A4E22,
      v61,
      v62,
      (__int64)&v92,
      (__int64)&LockState,
      (__int64)&ucSSID,
      (__int64)v79);
  }
  v64 = v80;
  if ( (*(_BYTE *)(a2 + 40) & 6) == 6 && v80->pSecurityEndpoint == v80->pMSSecurityEndpoint )
  {
    ++p_KeyContext->M2TxCount;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF__MAC__MAC_(
        WPP_GLOBAL_Control->AttachedDevice,
        307,
        (unsigned int)WPP_e90d411d816e312466897e39e745b158_Traceguids,
        (_DWORD)v80 + 4906,
        a2 + 16);
    v65 = v80;
    if ( v80->pAdapt->uConfiguredOpMode == 64 )
    {
      if ( (unsigned int)dword_1400AE050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400AE050, 0x200000000000LL) )
      {
        LODWORD(ActivePmk) = v39;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1400AE050,
          (unsigned int)&byte_1400A4DEF,
          v66,
          v67,
          (__int64)&ActivePmk);
      }
      v65 = v80;
    }
    if ( (byte_1400AF801 & 0x20) != 0 )
    {
      McTemplateK0pjb6b6_EtwWriteTransfer(
        (_DWORD)v65 + 4920,
        (unsigned int)SendM2Packet,
        (unsigned int)&v100,
        (_DWORD)v65,
        (__int64)&v65->gDeviceId,
        (__int64)v65->CurrentAddress,
        a2 + 16);
      v65 = v80;
    }
    v68 = v65->pSecurityEndpoint;
    if ( v68 )
    {
      LockState = (PLOCK_STATE_EX)*(unsigned int *)(a2 + 16);
      WORD2(LockState) = *(_WORD *)(a2 + 20);
      v99 = *(_DWORD *)(a2 + 44);
      p_LockState = &LockState;
      v88 = 10;
      v89 = 12;
      v91 = 0;
      NwfUpcallMsg((PIO_CSQ)((char *)v68->FsContext + 40), (const struct DOT11_AUTH_UPCALL_REQUEST *)&v88);
    }
    v69 = v85;
    *(_OWORD *)p_KeyContext->SNonce = *(_OWORD *)v102;
    *(_OWORD *)&p_KeyContext->SNonce[16] = v103;
    *(_OWORD *)p_KeyContext->ANonce = *(_OWORD *)v69;
    *(_OWORD *)&p_KeyContext->ANonce[16] = *((_OWORD *)v69 + 1);
    *(_OWORD *)&p_KeyContext->TempPTK.KCKLength = *(_OWORD *)&v101.KCKLength;
    *(_OWORD *)&p_KeyContext->TempPTK.PTK[4] = *(_OWORD *)&v101.PTK[4];
    *(_OWORD *)&p_KeyContext->TempPTK.PTK[20] = *(_OWORD *)&v101.PTK[20];
    *(_OWORD *)&p_KeyContext->TempPTK.PTK[36] = *(_OWORD *)&v101.PTK[36];
    *(_OWORD *)&p_KeyContext->TempPTK.PTK[52] = *(_OWORD *)&v101.PTK[52];
    *(_OWORD *)&p_KeyContext->TempPTK.PTK[68] = *(_OWORD *)&v101.PTK[68];
    v70 = *(_OWORD *)&v101.PTK[80];
    p_KeyContext->bTempPTKPresent = 1;
    *(_OWORD *)&p_KeyContext->TempPTK.PTK[80] = v70;
    uNextIndex = p_KeyContext->NonceCache.uNextIndex;
    *(_OWORD *)p_KeyContext->NonceCache.NoncePair[uNextIndex].ANonce = *(_OWORD *)p_KeyContext->ANonce;
    *(_OWORD *)&p_KeyContext->NonceCache.NoncePair[uNextIndex].ANonce[16] = *(_OWORD *)&p_KeyContext->ANonce[16];
    v72 = p_KeyContext->NonceCache.uNextIndex;
    *(_OWORD *)p_KeyContext->NonceCache.NoncePair[v72].SNonce = *(_OWORD *)p_KeyContext->SNonce;
    *(_OWORD *)&p_KeyContext->NonceCache.NoncePair[v72].SNonce[16] = *(_OWORD *)&p_KeyContext->SNonce[16];
    p_KeyContext->NonceCache.NoncePair[p_KeyContext->NonceCache.uNextIndex].bUsed = 1;
    p_KeyContext->NonceCache.uNextIndex = (p_KeyContext->NonceCache.uNextIndex + 1) % 0xA;
    goto LABEL_119;
  }
  v73 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 306, WPP_e90d411d816e312466897e39e745b158_Traceguids);
    v64 = v80;
  }
  if ( (byte_1400AF801 & 4) != 0 )
    McTemplateK0pj_EtwWriteTransfer(
      v73,
      (unsigned int)AbortReceiveM1Packet,
      (unsigned int)&v100,
      (_DWORD)v64,
      (__int64)&v64->gDeviceId);
}

```

## disassembly

```asm
0x140043c60  push    rbp
0x140043c62  push    rbx
0x140043c63  push    rsi
0x140043c64  push    rdi
0x140043c65  push    r12
0x140043c67  push    r13
0x140043c69  push    r14
0x140043c6b  push    r15
0x140043c6d  lea     rbp, [rsp-218h]
0x140043c75  sub     rsp, 318h
0x140043c7c  mov     rax, cs:__security_cookie
0x140043c83  xor     rax, rsp
0x140043c86  mov     [rbp+250h+var_50], rax
0x140043c8d  xor     eax, eax
0x140043c8f  mov     [rsp+350h+var_2D8], rcx
0x140043c94  xorps   xmm0, xmm0
0x140043c97  mov     [rbp+250h+LockState], r9
0x140043c9e  mov     r13, r8
0x140043ca1  mov     [rbp+250h+var_2D0], ax
0x140043ca5  mov     r14, rdx
0x140043ca8  mov     rbx, rcx
0x140043cab  lea     r8d, [rax+6Ch]; Size
0x140043caf  xor     edx, edx; Val
0x140043cb1  lea     rcx, [rbp+250h+var_110]; void *
0x140043cb8  movups  xmmword ptr [rbp+250h+var_A0], xmm0
0x140043cbf  movups  [rbp+250h+var_90], xmm0
0x140043cc6  call    memset
0x140043ccb  xor     edx, edx; Val
0x140043ccd  mov     [rbp+250h+var_2C0], 0
0x140043cd4  mov     r8d, 108h; Size
0x140043cda  lea     rcx, [rbp+250h+var_240]; void *
0x140043cde  call    memset
0x140043ce3  mov     r15, [rbx+17F8h]
0x140043cea  add     rbx, 1710h
0x140043cf1  xor     esi, esi
0x140043cf3  mov     [rbp+250h+var_2B0], r15
0x140043cf7  cmp     r13, r15
0x140043cfa  xorps   xmm0, xmm0
0x140043cfd  movups  [rbp+250h+var_80], xmm0
0x140043d04  setz    sil
0x140043d08  mov     edi, 0FFFFh
0x140043d0d  xor     eax, eax
0x140043d0f  mov     [rbp+250h+var_70], ax
0x140043d16  mov     eax, cs:dword_1400AE088
0x140043d1c  cmp     eax, 4
0x140043d1f  jbe     loc_140043E1B
0x140043d25  mov     edx, 4
0x140043d2a  lea     rcx, dword_1400AE088
0x140043d31  call    _tlgKeywordOn
0x140043d36  test    al, al
0x140043d38  jz      loc_140043E1B
0x140043d3e  mov     eax, [rbx+0F8h]
0x140043d44  mov     ecx, [rbx+18h]; this
0x140043d47  mov     dword ptr [rbp+250h+var_2C8], eax
0x140043d4a  mov     dword ptr [rsp+350h+var_2E0], esi
0x140043d4e  call    ?ToLogString@stringify@@YAPEBDW4_DOT11_CIPHER_ALGORITHM@@@Z; stringify::ToLogString(_DOT11_CIPHER_ALGORITHM)
0x140043d53  mov     ecx, [rbx+14h]; this
0x140043d56  mov     [rbp+250h+var_2B8], rax
0x140043d5a  call    ?ToLogString@stringify@@YAPEBDW4_DOT11_CIPHER_ALGORITHM@@@Z; stringify::ToLogString(_DOT11_CIPHER_ALGORITHM)
0x140043d5f  mov     ecx, [rbx+10h]; this
0x140043d62  mov     [rbp+250h+var_260], rax
0x140043d66  call    ?ToLogString@stringify@@YAPEBDW4_DOT11_CIPHER_ALGORITHM@@@Z; stringify::ToLogString(_DOT11_CIPHER_ALGORITHM)
0x140043d6b  mov     ecx, [rbx+1Ch]; this
0x140043d6e  mov     [rbp+250h+var_258], rax
0x140043d72  call    ?ToLogString@stringify@@YAPEBDW4RSNA_AKM_SUITE@@@Z; stringify::ToLogString(RSNA_AKM_SUITE)
0x140043d77  mov     ecx, [rbx+0Ch]; this
0x140043d7a  mov     [rbp+250h+var_250], rax
0x140043d7e  call    ?ToLogString@stringify@@YAPEBDW4_DOT11_AUTH_ALGORITHM@@@Z; stringify::ToLogString(_DOT11_AUTH_ALGORITHM)
0x140043d83  lea     rcx, [r14+10h]
0x140043d87  mov     [rbp+250h+var_270], rax
0x140043d8b  lea     r8, [rbp+250h+var_80]
0x140043d92  call    MacAddrToLogString
0x140043d97  mov     ecx, [rbx+520h]
0x140043d9d  mov     qword ptr [rbp+250h+var_120.Data1], rax
0x140043da4  cmp     ecx, edi
0x140043da6  jbe     short loc_140043DAB
0x140043da8  movzx   ecx, di
0x140043dab  lea     rax, [rbx+524h]
0x140043db2  mov     [rbp+250h+var_2A0], cx
0x140043db6  mov     [rbp+250h+var_2A8], rax
0x140043dba  lea     rdx, byte_1400A4E79
0x140043dc1  lea     rax, [rsp+350h+var_2E0]
0x140043dc6  mov     [rsp+350h+var_2F0], rax
0x140043dcb  lea     rax, [rbp+250h+var_2C8]
0x140043dcf  mov     [rsp+350h+var_2F8], rax
0x140043dd4  lea     rax, [rbp+250h+var_2B8]
0x140043dd8  mov     [rsp+350h+var_300], rax
0x140043ddd  lea     rax, [rbp+250h+var_260]
0x140043de1  mov     qword ptr [rsp+350h+var_308], rax
0x140043de6  lea     rax, [rbp+250h+var_258]
0x140043dea  mov     [rsp+350h+var_310], rax
0x140043def  lea     rax, [rbp+250h+var_250]
0x140043df3  mov     [rsp+350h+var_318], rax
0x140043df8  lea     rax, [rbp+250h+var_270]
0x140043dfc  mov     [rsp+350h+var_320], rax
0x140043e01  lea     rax, [rbp+250h+var_120]
0x140043e08  mov     [rsp+350h+var_328], rax
0x140043e0d  lea     rax, [rbp+250h+var_2A8]
0x140043e11  mov     [rsp+350h+var_330], rax
0x140043e16  call    ??$Write@U?$_tlgWrapperArray@$00@@U?$_tlgWrapSz@D@@U2@U2@U2@U2@U2@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$00@@AEBU?$_tlgWrapSz@D@@44444AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<1> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140043e1b  mov     eax, [rbx+0Ch]
0x140043e1e  sub     eax, 7
0x140043e21  test    eax, 0FFFFFFFDh
0x140043e26  jnz     loc_140043EAE
0x140043e2c  cmp     dword ptr [rbx+4E8h], 0
0x140043e33  jnz     short loc_140043EAE
0x140043e35  cmp     dword ptr [rbx+0FCh], 2
0x140043e3c  jb      short loc_140043EAE
0x140043e3e  mov     rcx, [rsp+350h+var_2D8]
0x140043e43  mov     rdx, [rcx+1700h]
0x140043e4a  test    rdx, rdx
0x140043e4d  jz      short loc_140043EB3
0x140043e4f  mov     eax, [r14+10h]
0x140043e53  xorps   xmm0, xmm0
0x140043e56  mov     qword ptr [rbp+250h+var_120.Data1], 0
0x140043e61  mov     [rbp+250h+var_120.Data1], eax
0x140043e67  movzx   eax, word ptr [r14+14h]
0x140043e6c  mov     [rbp+250h+var_120.Data2], ax
0x140043e73  mov     eax, [r14+2Ch]
0x140043e77  mov     dword ptr [rbp+250h+var_120.Data4], eax
0x140043e7d  lea     rax, [rbp+250h+var_120]
0x140043e84  mov     [rbp+250h+var_288], rax
0x140043e88  mov     [rbp+250h+var_298], 0Ch
0x140043e90  mov     [rbp+250h+var_290], 0Ch
0x140043e98  movdqu  [rbp+250h+var_280], xmm0
0x140043e9d  mov     rcx, [rdx+18h]
0x140043ea1  lea     rdx, [rbp+250h+var_298]; struct DOT11_AUTH_UPCALL_REQUEST *
0x140043ea5  add     rcx, 28h ; '('; Csq
0x140043ea9  call    ?NwfUpcallMsg@@YAJPEAUNWF_AUTH_UPCALL@@PEBUDOT11_AUTH_UPCALL_REQUEST@@@Z; NwfUpcallMsg(NWF_AUTH_UPCALL *,DOT11_AUTH_UPCALL_REQUEST const *)
0x140043eae  mov     rcx, [rsp+350h+var_2D8]; struct _VELAN *
0x140043eb3  cmp     dword ptr [rcx+171Ch], 0Ah
0x140043eba  jnz     short loc_140043EC9
0x140043ebc  mov     rdx, r14; struct DOT11_MAC_STATE_ENTRY *
0x140043ebf  call    ?OWEGetAuthInfo@@YAJPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@@Z; OWEGetAuthInfo(_VELAN *,DOT11_MAC_STATE_ENTRY *)
0x140043ec4  mov     rcx, [rsp+350h+var_2D8]
0x140043ec9  mov     rdx, r14
0x140043ecc  call    GetActivePmk
0x140043ed1  mov     [rbp+250h+var_2C8], rax
0x140043ed5  mov     rdi, rax
0x140043ed8  test    rax, rax
0x140043edb  jnz     loc_140044055
0x140043ee1  cmp     r13, r15
0x140043ee4  jz      loc_14004404C
0x140043eea  mov     [rbx+0F8h], eax
0x140043ef0  mov     rcx, [rsp+350h+var_2D8]
0x140043ef5  add     rcx, 17F0h; struct DOT11_MAC_STATE_ENTRY **
0x140043efc  cmp     [rcx], rax
0x140043eff  jz      short loc_140043F06
0x140043f01  call    ?Dot11ReleaseMacState@@YAXPEAPEAUDOT11_MAC_STATE_ENTRY@@@Z; Dot11ReleaseMacState(DOT11_MAC_STATE_ENTRY * *)
0x140043f06  mov     rcx, [rbx+0E8h]
0x140043f0d  test    rcx, rcx
0x140043f10  jz      short loc_140043F4C
0x140043f12  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140043f16  mov     rax, [rcx]
0x140043f19  test    rax, rax
0x140043f1c  jz      short loc_140043F32
0x140043f1e  mov     rdx, rcx; Entry
0x140043f21  mov     rcx, rax; Lookaside
0x140043f24  call    cs:__imp_ExFreeToNPagedLookasideList
0x140043f2b  nop     dword ptr [rax+rax+00h]
0x140043f30  jmp     short loc_140043F41
0x140043f32  mov     edx, [rcx+8]; Tag
0x140043f35  call    cs:__imp_ExFreePoolWithTag
0x140043f3c  nop     dword ptr [rax+rax+00h]
0x140043f41  mov     qword ptr [rbx+0E8h], 0
0x140043f4c  movzx   eax, word ptr [r13+2]
0x140043f51  ror     ax, 8
0x140043f55  movzx   ecx, ax
0x140043f58  add     ecx, 14h
0x140043f5b  mov     qword ptr [rbx+0E8h], 0
0x140043f66  cmp     ecx, 10h
0x140043f69  jb      short loc_140043FDC
0x140043f6b  mov     r15d, 7A697377h
0x140043f71  cmp     ecx, 40h ; '@'
0x140043f74  ja      short loc_140043F7F
0x140043f76  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x140043f7d  jmp     short loc_140043FB0
0x140043f7f  cmp     ecx, 100h
0x140043f85  ja      short loc_140043F90
0x140043f87  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140043f8e  jmp     short loc_140043FB0
0x140043f90  cmp     ecx, 400h
0x140043f96  ja      short loc_140043FA1
0x140043f98  lea     rdi, Lookaside
0x140043f9f  jmp     short loc_140043FB0
0x140043fa1  cmp     ecx, 800h
0x140043fa7  ja      short loc_140043FC1
0x140043fa9  lea     rdi, stru_1400B0180
0x140043fb0  mov     rcx, rdi; Lookaside
0x140043fb3  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140043fba  nop     dword ptr [rax+rax+00h]
0x140043fbf  jmp     short loc_140043FD7
0x140043fc1  xor     edi, edi
0x140043fc3  mov     edx, ecx
0x140043fc5  mov     r8d, r15d
0x140043fc8  lea     ecx, [rdi+40h]
0x140043fcb  call    cs:__imp_ExAllocatePool2
0x140043fd2  nop     dword ptr [rax+rax+00h]
0x140043fd7  test    rax, rax
0x140043fda  jnz     short loc_140043FE6
0x140043fdc  mov     edi, 0C000009Ah
0x140043fe1  jmp     loc_14004495D
0x140043fe6  mov     [rax], rdi
0x140043fe9  mov     [rax+8], r15d
0x140043fed  add     rax, 10h
0x140043ff1  mov     [rbx+0E8h], rax
0x140043ff8  lock inc dword ptr [r14+24h]
0x140043ffd  mov     rcx, [rbx+0E8h]; void *
0x140044004  mov     rdx, r13; Src
0x140044007  mov     [rbx+0E0h], r14
0x14004400e  movzx   eax, word ptr [r13+2]
0x140044013  ror     ax, 8
0x140044017  movzx   r8d, ax
0x14004401b  add     r8, 4; Size
0x14004401f  call    memmove
0x140044024  mov     rcx, cs:WPP_GLOBAL_Control
0x14004402b  lea     r12, WPP_GLOBAL_Control
0x140044032  cmp     rcx, r12
0x140044035  jz      short loc_14004404C
0x140044037  mov     rcx, [rcx+18h]
0x14004403b  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x140044042  mov     edx, 12Bh
0x140044047  call    WPP_SF_
0x14004404c  xor     esi, esi
0x14004404e  xor     edi, edi
0x140044050  jmp     loc_14004495D
0x140044055  lea     rax, [r13+4]
0x140044059  mov     [rbp+250h+var_2B8], rax
0x14004405d  lea     r12, WPP_GLOBAL_Control
0x140044064  mov     eax, [rbx+0Ch]
0x140044067  lea     r15, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004406e  cmp     eax, 9
0x140044071  jnz     loc_140044140
0x140044077  mov     rcx, [rsp+350h+var_2D8]
0x14004407c  lea     rdx, [rdi+18h]
0x140044080  mov     [rsp+350h+var_330], rdx
0x140044085  lea     r9, [rdi+95h]
0x14004408c  lea     rdx, [r14+10h]
0x140044090  mov     dword ptr [rsp+350h+var_2E0], 41h ; 'A'
0x140044098  add     rcx, 1FE8h
0x14004409f  lea     r8, [rsp+350h+var_2E0]
0x1400440a4  call    PmkCacheGetAuthInfo
0x1400440a9  test    eax, eax
0x1400440ab  jz      short loc_140044116
0x1400440ad  mov     eax, dword ptr [rsp+350h+var_2E0]
0x1400440b1  mov     [rdi+30h], eax
0x1400440b4  mov     dword ptr [rdi], 9
0x1400440ba  mov     rax, [rsp+350h+var_2D8]
0x1400440bf  mov     rcx, [rax+10h]
0x1400440c3  mov     eax, [rcx+420h]
0x1400440c9  test    al, 1
0x1400440cb  jz      loc_1400441AD
0x1400440d1  lea     r8, [r14+10h]; unsigned __int8 *
0x1400440d5  mov     edx, 6; unsigned int
0x1400440da  lea     rcx, aPmkcachegetaut; "PmkCacheGetAuthInfo [PmkId]: Returning "...
0x1400440e1  call    ?DumpBuff@@YAXPEAGIPEAE@Z; DumpBuff(ushort *,uint,uchar *)
0x1400440e6  mov     edx, [rdi+30h]; unsigned int
0x1400440e9  lea     r8, [rdi+95h]; unsigned __int8 *
0x1400440f0  lea     rcx, aPmkcachegetaut_0; "\tPmkCacheGetAuthInfo [PmkId]: PMK:"
0x1400440f7  call    ?DumpBuff@@YAXPEAGIPEAE@Z; DumpBuff(ushort *,uint,uchar *)
0x1400440fc  lea     r8, [rdi+18h]; unsigned __int8 *
0x140044100  mov     edx, 10h; unsigned int
0x140044105  lea     rcx, aPmkcachegetaut_1; "\tPmkCacheGetAuthInfo [PmkId]: PMKID:"
0x14004410c  call    ?DumpBuff@@YAXPEAGIPEAE@Z; DumpBuff(ushort *,uint,uchar *)
0x140044111  jmp     loc_1400441AD
0x140044116  mov     rcx, cs:WPP_GLOBAL_Control
0x14004411d  cmp     rcx, r12
0x140044120  jz      short loc_140044137
0x140044122  mov     rcx, [rcx+18h]
0x140044126  lea     r9, [r14+10h]
0x14004412a  mov     edx, 12Ch
0x14004412f  mov     r8, r15
0x140044132  call    WPP_SF__MAC_
0x140044137  mov     dword ptr [rdi+30h], 0
0x14004413e  jmp     short loc_1400441AD
0x140044140  cmp     eax, 8
0x140044143  jnz     short loc_140044190
0x140044145  mov     rcx, [rsp+350h+var_2D8]
0x14004414a  lea     rax, [rdi+18h]
0x14004414e  add     rcx, 1FE8h
0x140044155  mov     [rsp+350h+var_330], rax
0x14004415a  lea     rdx, [r14+10h]
0x14004415e  xor     r9d, r9d
0x140044161  xor     r8d, r8d
0x140044164  call    PmkCacheGetAuthInfo
0x140044169  test    eax, eax
0x14004416b  jnz     short loc_1400441AD
0x14004416d  mov     rcx, cs:WPP_GLOBAL_Control
0x140044174  cmp     rcx, r12
0x140044177  jz      short loc_1400441AD
0x140044179  mov     rcx, [rcx+18h]
0x14004417d  lea     r9, [r14+10h]
0x140044181  mov     edx, 12Dh
0x140044186  mov     r8, r15
0x140044189  call    WPP_SF__MAC_
0x14004418e  jmp     short loc_1400441AD
0x140044190  mov     rax, [rsp+350h+var_2D8]
0x140044195  cmp     dword ptr [rax+1C18h], 0
0x14004419c  jz      short loc_1400441AD
0x14004419e  mov     rax, [rbx+510h]
  ... truncated ...
```
