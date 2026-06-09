# Dot11ReceiveM1

- ea: `0x1400447e0`
- end: `0x1400455c0`
- name: `Dot11ReceiveM1`
- size: `3552`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140043404`
- `0x140043c60`
- `0x14005054c`

## callees

- `0x1400012bc`
- `0x140001544`
- `0x14000170c`
- `0x14000a368`
- `0x14000a81c`
- `0x14000a934`
- `0x14000d21c`
- `0x14000d2b0`
- `0x140013b80`
- `0x140018a0c`
- `0x140020dc0`
- `0x140020e04`
- `0x140032d88`
- `0x140035924`
- `0x140036918`
- `0x140039ca8`
- `0x14003b04c`
- `0x140043ed4`
- `0x1400447e0`
- `0x14004897c`
- `0x140048dc8`
- `0x140049b6c`
- `0x14004a23c`
- `0x14005291c`
- `0x140091c20`
- `0x1400973ec`
- `0x1400975c0`
- `0x140097684`
- `0x14009bbb0`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140044b33`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140044e7a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140044b33`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140044e7a`
- `ntoskrnl!ExAllocatePool2` at `0x140044b4b`
- `ntoskrnl!ExAllocatePool2` at `0x140044e95`
- `ntoskrnl!ExAllocatePool2` at `0x140044b4b`
- `ntoskrnl!ExAllocatePool2` at `0x140044e95`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140044aa4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140044ded`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400450e4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140045538`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140044aa4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140044ded`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400450e4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140045538`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044ab5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044dfe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400450f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045549`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044ab5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044dfe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400450f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045549`
- `cng!SystemPrng` at `0x140044f27`
- `cng!SystemPrng` at `0x140044f27`

## string_xrefs

- `0x140044c5a`: `PmkCacheGetAuthInfo [PmkId]: Returning auth info for:`
- `0x140044c70`: `	PmkCacheGetAuthInfo [PmkId]: PMK:`
- `0x140044c85`: `	PmkCacheGetAuthInfo [PmkId]: PMKID:`

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
  struct NWF_PMK_ENTRY *v32; // rdi
  struct NWF_EAPOL_HEADER *v33; // rcx
  __int64 v34; // rcx
  unsigned int v35; // ecx
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rdi
  _DWORD *Pool2; // rax
  int v38; // edi
  struct NWF_EAPOL_HEADER *v39; // rcx
  _DOT11_AUTH_ALGORITHM v40; // eax
  unsigned int v41; // r8d
  struct NWF_EAPOL_HEADER *v42; // rcx
  __int64 v43; // rcx
  unsigned int v44; // ecx
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rdi
  _DWORD *v46; // rax
  struct NWF_EAPOL_HEADER *v47; // rcx
  int v48; // eax
  PDEVICE_OBJECT v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // r9
  struct NWF_PMK_ENTRY *v52; // rcx
  _DOT11_AUTH_ALGORITHM v53; // eax
  __int16 v54; // cx
  ULONG *v55; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v56; // rax
  __int64 v57; // rdx
  struct _LOCK_STATE_EX *v58; // rax
  int v59; // r8d
  int v60; // r9d
  unsigned int v61; // ecx
  struct _VELAN *v62; // r9
  struct _VELAN *v63; // rdx
  int v64; // r8d
  int v65; // r9d
  _FILE_OBJECT *v66; // rcx
  struct NWF_EAPOL_HEADER *v67; // rax
  __int128 v68; // xmm0
  __int64 uNextIndex; // rcx
  __int64 v70; // rcx
  int v71; // ecx
  struct NWF_EAPOL_HEADER *v72; // rcx
  struct _VELAN *v73; // rbx
  ULONG *v74; // rcx
  unsigned __int16 v75; // [rsp+30h] [rbp-D0h]
  struct NWF_FT_CONTEXT *pFTContext; // [rsp+38h] [rbp-C8h]
  unsigned __int16 v77[2]; // [rsp+70h] [rbp-90h] BYREF
  struct _VELAN *v78; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v79; // [rsp+80h] [rbp-80h] BYREF
  struct NWF_PMK_ENTRY *ActivePmk; // [rsp+88h] [rbp-78h] BYREF
  int v81; // [rsp+90h] [rbp-70h] BYREF
  const char *v82; // [rsp+98h] [rbp-68h] BYREF
  struct NWF_EAPOL_HEADER *v83; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *ucSSID; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v85; // [rsp+B0h] [rbp-50h]
  __int64 v86; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v87; // [rsp+C0h] [rbp-40h]
  void *p_LockState; // [rsp+C8h] [rbp-38h]
  __int128 v89; // [rsp+D0h] [rbp-30h]
  const char *v90; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v91; // [rsp+E8h] [rbp-18h]
  const char *v92; // [rsp+F0h] [rbp-10h] BYREF
  const char *v93; // [rsp+F8h] [rbp-8h] BYREF
  const char *v94; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v95[272]; // [rsp+110h] [rbp+10h] BYREF
  PLOCK_STATE_EX LockState; // [rsp+220h] [rbp+120h] BYREF
  int v97; // [rsp+228h] [rbp+128h]
  struct _GUID v98; // [rsp+230h] [rbp+130h] BYREF
  struct NWF_PTK v99; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int8 v100[16]; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int128 v101; // [rsp+2C0h] [rbp+1C0h]
  __int128 v102; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int16 v103; // [rsp+2E0h] [rbp+1E0h]
  __int128 v104; // [rsp+2E8h] [rbp+1E8h] BYREF
  __int16 v105; // [rsp+2F8h] [rbp+1F8h]

  v78 = a1;
  LockState = a4;
  v79 = 0;
  *(_OWORD *)v100 = 0;
  v101 = 0;
  memset(&v99, 0, sizeof(v99));
  v81 = 0;
  memset(v95, 0, 0x108u);
  pEapolHdr = a1->KeyContext.M1Cache.pEapolHdr;
  p_KeyContext = &a1->KeyContext;
  v83 = pEapolHdr;
  v102 = 0;
  v9 = a3 == pEapolHdr;
  v103 = 0;
  if ( (unsigned int)dword_1400B1088 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400B1088, 4) )
  {
    McastMgmtCipher = (stringify *)(unsigned int)p_KeyContext->McastMgmtCipher;
    LODWORD(ActivePmk) = p_KeyContext->bFastRoaming;
    *(_DWORD *)v77 = a3 == pEapolHdr;
    v12 = stringify::ToLogString(McastMgmtCipher, v10);
    McastCipher = (stringify *)(unsigned int)p_KeyContext->McastCipher;
    v82 = v12;
    v15 = stringify::ToLogString(McastCipher, v14);
    UcastCipher = (stringify *)(unsigned int)p_KeyContext->UcastCipher;
    v92 = v15;
    v18 = stringify::ToLogString(UcastCipher, v17);
    AkmSuite = (stringify *)(unsigned int)p_KeyContext->EapolKeyInfo.AkmSuite;
    v93 = v18;
    v21 = stringify::ToLogString(AkmSuite, v20);
    AuthAlgo = (stringify *)(unsigned int)p_KeyContext->AuthAlgo;
    v94 = v21;
    v90 = stringify::ToLogString(AuthAlgo, v23);
    v25 = MacAddrToLogString(a2 + 16, v24, &v102);
    uSSIDLength = p_KeyContext->Ssid.uSSIDLength;
    *(_QWORD *)&v98.Data1 = v25;
    if ( uSSIDLength > 0xFFFF )
      uSSIDLength = 0xFFFF;
    v85 = uSSIDLength;
    ucSSID = (unsigned __int16 *)p_KeyContext->Ssid.ucSSID;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      uSSIDLength,
      (unsigned int)byte_1400A6F79,
      v26,
      v27,
      (__int64)&ucSSID,
      (__int64)&v98,
      (__int64)&v90,
      (__int64)&v94,
      (__int64)&v93,
      (__int64)&v92,
      (__int64)&v82,
      (__int64)&ActivePmk,
      (__int64)v77);
  }
  if ( ((p_KeyContext->AuthAlgo - 7) & 0xFFFFFFFD) == 0 && !p_KeyContext->bRSNASecured && p_KeyContext->M2TxCount >= 2 )
  {
    v29 = v78;
    pSecurityEndpoint = v78->pSecurityEndpoint;
    if ( !pSecurityEndpoint )
      goto LABEL_12;
    v31 = *(_DWORD *)(a2 + 16);
    *(_DWORD *)&v98.Data2 = 0;
    v98.Data1 = v31;
    v98.Data2 = *(_WORD *)(a2 + 20);
    *(_DWORD *)v98.Data4 = *(_DWORD *)(a2 + 44);
    p_LockState = &v98;
    v86 = 12;
    v87 = 12;
    v89 = 0;
    NwfUpcallMsg((PIO_CSQ)((char *)pSecurityEndpoint->FsContext + 40), (const struct DOT11_AUTH_UPCALL_REQUEST *)&v86);
  }
  v29 = v78;
LABEL_12:
  if ( v29->KeyContext.AuthAlgo == DOT11_AUTH_ALGO_OWE )
  {
    OWEGetAuthInfo(v29, (struct DOT11_MAC_STATE_ENTRY *)a2);
    v29 = v78;
  }
  ActivePmk = (struct NWF_PMK_ENTRY *)GetActivePmk(v29, a2);
  v32 = ActivePmk;
  if ( !ActivePmk )
  {
    if ( a3 == pEapolHdr )
    {
LABEL_38:
      v9 = 0;
      v38 = 0;
      goto LABEL_119;
    }
    p_KeyContext->bFastRoaming = 0;
    if ( v78->KeyContext.M1Cache.pMacStateEntry )
      Dot11ReleaseMacState(&v78->KeyContext.M1Cache.pMacStateEntry);
    v33 = p_KeyContext->M1Cache.pEapolHdr;
    if ( v33 )
    {
      v34 = (__int64)v33 - 16;
      if ( *(_QWORD *)v34 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v34, (PVOID)v34);
      else
        ExFreePoolWithTag((PVOID)v34, *(_DWORD *)(v34 + 8));
      p_KeyContext->M1Cache.pEapolHdr = 0;
    }
    v35 = (unsigned __int16)__ROR2__(*((_WORD *)a3 + 1), 8) + 20;
    p_KeyContext->M1Cache.pEapolHdr = 0;
    if ( v35 < 0x10 )
      goto LABEL_35;
    if ( v35 > 0x40 )
    {
      if ( v35 > 0x100 )
      {
        if ( v35 > 0x400 )
        {
          if ( v35 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v35, 2053731191);
            goto LABEL_34;
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
LABEL_34:
    if ( !Pool2 )
    {
LABEL_35:
      v38 = -1073741670;
      goto LABEL_119;
    }
    *(_QWORD *)Pool2 = p_WaitListHead;
    Pool2[2] = 2053731191;
    p_KeyContext->M1Cache.pEapolHdr = (struct NWF_EAPOL_HEADER *)(Pool2 + 4);
    _InterlockedIncrement((volatile signed __int32 *)(a2 + 36));
    v39 = p_KeyContext->M1Cache.pEapolHdr;
    p_KeyContext->M1Cache.pMacStateEntry = (DOT11_MAC_STATE_ENTRY *)a2;
    memmove(v39, a3, (unsigned __int16)__ROR2__(*((_WORD *)a3 + 1), 8) + 4LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 299, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
    goto LABEL_38;
  }
  v82 = (char *)a3 + 4;
  v40 = p_KeyContext->AuthAlgo;
  if ( v40 == DOT11_AUTH_ALGO_WPA3_SAE )
  {
    *(_DWORD *)v77 = 65;
    if ( (unsigned int)PmkCacheGetAuthInfo(&v78->Dot11PmkCache, a2 + 16, v77, &ActivePmk->149, ActivePmk->PMKID) )
    {
      v32->uSendKeyLength = *(_DWORD *)v77;
      v32->AuthAlgo = DOT11_AUTH_ALGO_WPA3_SAE;
      if ( (v78->pAdapt->uWFATestFlags & 1) != 0 )
      {
        DumpBuff(L"PmkCacheGetAuthInfo [PmkId]: Returning auth info for:", 6u, (unsigned __int8 *)(a2 + 16));
        DumpBuff(L"\tPmkCacheGetAuthInfo [PmkId]: PMK:", v32->uSendKeyLength, v32->ucSendKey);
        DumpBuff(L"\tPmkCacheGetAuthInfo [PmkId]: PMKID:", 0x10u, v32->PMKID);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF__MAC_(WPP_GLOBAL_Control->AttachedDevice, 300, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, a2 + 16);
      v32->uSendKeyLength = 0;
    }
  }
  else if ( v40 == DOT11_AUTH_ALGO_WPA3 )
  {
    if ( !(unsigned int)PmkCacheGetAuthInfo(&v78->Dot11PmkCache, a2 + 16, 0, 0, ActivePmk->PMKID)
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      WPP_SF__MAC_(WPP_GLOBAL_Control->AttachedDevice, 301, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, a2 + 16);
    }
  }
  else if ( v78->KeyContext.bFTAKM )
  {
    ActivePmk->MDID = p_KeyContext->pFTContext->MDID;
  }
  v41 = (unsigned __int16)__ROR2__(*(_WORD *)((char *)a3 + 7), 8);
  *(_DWORD *)v77 = v41;
  if ( v41 - 1 > 0x1F )
  {
    v38 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 302, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v41);
    goto LABEL_119;
  }
  v38 = ValidateM1KeyData(
          v78,
          (struct DOT11_MAC_STATE_ENTRY *)a2,
          p_KeyContext,
          (unsigned __int16)__ROR2__(*(_WORD *)((char *)a3 + p_KeyContext->EapolKeyInfo.KeyMaterialLengthOffset + 4), 8),
          (unsigned __int8 *)a3 + p_KeyContext->EapolKeyInfo.KeyMaterialOffset + 4,
          &v81,
          &ActivePmk);
  if ( v38 < 0 )
    goto LABEL_119;
  if ( p_KeyContext->bFastRoaming )
  {
    if ( !v81 )
    {
      if ( a3 == v83 )
      {
LABEL_78:
        v9 = 0;
        goto LABEL_119;
      }
      if ( v78->KeyContext.M1Cache.pMacStateEntry )
        Dot11ReleaseMacState(&v78->KeyContext.M1Cache.pMacStateEntry);
      v42 = p_KeyContext->M1Cache.pEapolHdr;
      if ( v42 )
      {
        v43 = (__int64)v42 - 16;
        if ( *(_QWORD *)v43 )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v43, (PVOID)v43);
        else
          ExFreePoolWithTag((PVOID)v43, *(_DWORD *)(v43 + 8));
        p_KeyContext->M1Cache.pEapolHdr = 0;
      }
      v44 = (unsigned __int16)__ROR2__(*((_WORD *)a3 + 1), 8) + 20;
      p_KeyContext->M1Cache.pEapolHdr = 0;
      if ( v44 < 0x10 )
        goto LABEL_35;
      if ( v44 > 0x40 )
      {
        if ( v44 > 0x100 )
        {
          if ( v44 > 0x400 )
          {
            if ( v44 > 0x800 )
            {
              p_DeviceQueue = 0;
              v46 = (_DWORD *)ExAllocatePool2(64, v44, 2053731191);
              goto LABEL_75;
            }
            p_DeviceQueue = &stru_1400B31C0;
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
      v46 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
LABEL_75:
      if ( !v46 )
        goto LABEL_35;
      *(_QWORD *)v46 = p_DeviceQueue;
      v46[2] = 2053731191;
      p_KeyContext->M1Cache.pEapolHdr = (struct NWF_EAPOL_HEADER *)(v46 + 4);
      v38 = 0;
      _InterlockedIncrement((volatile signed __int32 *)(a2 + 36));
      v47 = p_KeyContext->M1Cache.pEapolHdr;
      p_KeyContext->M1Cache.pMacStateEntry = (DOT11_MAC_STATE_ENTRY *)a2;
      memmove(v47, a3, (unsigned __int16)__ROR2__(*((_WORD *)a3 + 1), 8) + 4LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 303, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
      goto LABEL_78;
    }
    p_KeyContext->bFastRoaming = 0;
  }
  SystemPrng(v100, 32);
  if ( (unsigned int)Feature_53299205__private_IsEnabledDeviceUsageNoInline()
    && (p_KeyContext->adapterConnectionCapabilityFlags & 0x4000) != 0 )
  {
    *(_DWORD *)((char *)&v101 + 10) = 10121040;
    HIWORD(v101) = 10496;
  }
  pFTContext = p_KeyContext->pFTContext;
  v83 = (struct NWF_EAPOL_HEADER *)(v82 + 13);
  v48 = GeneratePTK(
          v78->CurrentAddress,
          (unsigned __int8 *)(a2 + 16),
          &v78->KeyContext,
          ActivePmk,
          v100,
          (unsigned __int8 *)v82 + 13,
          *(unsigned int *)v77,
          pFTContext,
          &v99);
  v38 = v48;
  if ( v48 < 0 )
  {
    v49 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_119;
    v50 = 304;
    v51 = (unsigned int)v48;
    goto LABEL_86;
  }
  v52 = ActivePmk;
  v53 = p_KeyContext->AuthAlgo;
  v98 = 0;
  ActivePmk->AuthAlgo = v53;
  v52->uTKLength = *(_DWORD *)v77;
  v77[0] = 0;
  ActivePmk = 0;
  Dot11PrepareM2KeyMaterial(v78, v77, (unsigned __int8 **)&ActivePmk);
  v54 = v79 & 0xF8FF | ((p_KeyContext->KeyDescriptorVersion & 7) << 8);
  v79 = v54 ^ ((unsigned __int8)v54 ^ (unsigned __int8)(2 * LOWORD(p_KeyContext->bRSNASecured))) & 2 | 0x801;
  v38 = ElSendSSNKeyPacket(
          v78,
          LockState,
          (struct DOT11_MAC_STATE_ENTRY *)a2,
          (unsigned __int8 (*)[6])v78->CurrentAddress,
          (unsigned __int8 (*)[6])(a2 + 16),
          v79,
          v75,
          *(_QWORD *)(v82 + 5),
          v100,
          v77[0],
          (unsigned __int8 *)ActivePmk,
          v99.PTK,
          &v98);
  if ( ActivePmk )
  {
    v55 = (ULONG *)&ActivePmk[-1].ucKey[51];
    v56 = *(struct _NPAGED_LOOKASIDE_LIST **)&ActivePmk[-1].ucKey[51];
    if ( v56 )
      ExFreeToNPagedLookasideList(v56, v55);
    else
      ExFreePoolWithTag(v55, v55[2]);
  }
  if ( v38 < 0 )
  {
    v49 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      v50 = 305;
      v51 = (unsigned int)v38;
LABEL_86:
      WPP_SF_d(v49->AttachedDevice, v50, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v51);
    }
LABEL_119:
    *(_OWORD *)v100 = 0;
    v101 = 0;
    memset(&v99, 0, sizeof(v99));
    if ( v9 )
    {
      Dot11ReleaseMacState(&v78->KeyContext.M1Cache.pMacStateEntry);
      v73 = v78;
      v72 = v78->KeyContext.M1Cache.pEapolHdr;
      if ( v72 )
      {
        v74 = (ULONG *)((char *)v72 - 16);
        if ( *(_QWORD *)v74 )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v74, v74);
        else
          ExFreePoolWithTag(v74, v74[2]);
        v73->KeyContext.M1Cache.pEapolHdr = 0;
      }
    }
    if ( v38 )
    {
      if ( (byte_1400B2801 & 0x40) != 0 )
        McTemplateK0pjq_EtwWriteTransfer(
          (_DWORD)v72,
          (unsigned int)ReceiveM1PacketError,
          (_DWORD)v78 + 4920,
          (unsigned int)&v78,
          (__int64)&v78->gDeviceId,
          v38);
    }
    FreeRSNMessageKeyData((struct NWF_RSN_KEY_DATA *)v95);
    return;
  }
  v105 = 0;
  v104 = 0;
  if ( (unsigned int)dword_1400B1088 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400B1088, 4) )
  {
    ucSSID = &v79;
    v85 = v57 - 2;
    v58 = (struct _LOCK_STATE_EX *)MacAddrToLogString(a2 + 16, v57, &v104);
    v61 = p_KeyContext->Ssid.uSSIDLength;
    LockState = v58;
    if ( v61 > 0xFFFF )
      v61 = 0xFFFF;
    v91 = v61;
    v90 = (const char *)p_KeyContext->Ssid.ucSSID;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapperArray<1>,_tlgWrapperByVal<2>>(
      v61,
      (unsigned int)word_1400A6F22,
      v59,
      v60,
      (__int64)&v90,
      (__int64)&LockState,
      (__int64)&ucSSID,
      (__int64)v77);
  }
  v62 = v78;
  if ( (*(_BYTE *)(a2 + 40) & 6) == 6 && v78->pSecurityEndpoint == v78->pMSSecurityEndpoint )
  {
    ++p_KeyContext->M2TxCount;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF__MAC__MAC_(
        WPP_GLOBAL_Control->AttachedDevice,
        307,
        (unsigned int)WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
        (_DWORD)v78 + 4906,
        a2 + 16);
    v63 = v78;
    if ( v78->pAdapt->uConfiguredOpMode == 64 )
    {
      if ( (unsigned int)dword_1400B1050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400B1050, 0x200000000000LL) )
      {
        LODWORD(ActivePmk) = v38;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1400B1050,
          (unsigned int)&byte_1400A6EEF,
          v64,
          v65,
          (__int64)&ActivePmk);
      }
      v63 = v78;
    }
    if ( (byte_1400B2801 & 0x20) != 0 )
    {
      McTemplateK0pjb6b6_EtwWriteTransfer(
        (_DWORD)v63 + 4920,
        (unsigned int)SendM2Packet,
        (unsigned int)&v98,
        (_DWORD)v63,
        (__int64)&v63->gDeviceId,
        (__int64)v63->CurrentAddress,
        a2 + 16);
      v63 = v78;
    }
    v66 = v63->pSecurityEndpoint;
    if ( v66 )
    {
      LockState = (PLOCK_STATE_EX)*(unsigned int *)(a2 + 16);
      WORD2(LockState) = *(_WORD *)(a2 + 20);
      v97 = *(_DWORD *)(a2 + 44);
      p_LockState = &LockState;
      v86 = 10;
      v87 = 12;
      v89 = 0;
      NwfUpcallMsg((PIO_CSQ)((char *)v66->FsContext + 40), (const struct DOT11_AUTH_UPCALL_REQUEST *)&v86);
    }
    v67 = v83;
    *(_OWORD *)p_KeyContext->SNonce = *(_OWORD *)v100;
    *(_OWORD *)&p_KeyContext->SNonce[16] = v101;
    *(_OWORD *)p_KeyContext->ANonce = *(_OWORD *)v67;
    *(_OWORD *)&p_KeyContext->ANonce[16] = *((_OWORD *)v67 + 1);
    *(_OWORD *)&p_KeyContext->TempPTK.KCKLength = *(_OWORD *)&v99.KCKLength;
    *(_OWORD *)&p_KeyContext->TempPTK.PTK[4] = *(_OWORD *)&v99.PTK[4];
    *(_OWORD *)&p_KeyContext->TempPTK.PTK[20] = *(_OWORD *)&v99.PTK[20];
    *(_OWORD *)&p_KeyContext->TempPTK.PTK[36] = *(_OWORD *)&v99.PTK[36];
    *(_OWORD *)&p_KeyContext->TempPTK.PTK[52] = *(_OWORD *)&v99.PTK[52];
    *(_OWORD *)&p_KeyContext->TempPTK.PTK[68] = *(_OWORD *)&v99.PTK[68];
    v68 = *(_OWORD *)&v99.PTK[80];
    p_KeyContext->bTempPTKPresent = 1;
    *(_OWORD *)&p_KeyContext->TempPTK.PTK[80] = v68;
    uNextIndex = p_KeyContext->NonceCache.uNextIndex;
    *(_OWORD *)p_KeyContext->NonceCache.NoncePair[uNextIndex].ANonce = *(_OWORD *)p_KeyContext->ANonce;
    *(_OWORD *)&p_KeyContext->NonceCache.NoncePair[uNextIndex].ANonce[16] = *(_OWORD *)&p_KeyContext->ANonce[16];
    v70 = p_KeyContext->NonceCache.uNextIndex;
    *(_OWORD *)p_KeyContext->NonceCache.NoncePair[v70].SNonce = *(_OWORD *)p_KeyContext->SNonce;
    *(_OWORD *)&p_KeyContext->NonceCache.NoncePair[v70].SNonce[16] = *(_OWORD *)&p_KeyContext->SNonce[16];
    p_KeyContext->NonceCache.NoncePair[p_KeyContext->NonceCache.uNextIndex].bUsed = 1;
    p_KeyContext->NonceCache.uNextIndex = (p_KeyContext->NonceCache.uNextIndex + 1) % 0xA;
    goto LABEL_119;
  }
  v71 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 306, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
    v62 = v78;
  }
  if ( (byte_1400B2801 & 4) != 0 )
    McTemplateK0pj_EtwWriteTransfer(
      v71,
      (unsigned int)AbortReceiveM1Packet,
      (unsigned int)&v98,
      (_DWORD)v62,
      (__int64)&v62->gDeviceId);
}

```

## disassembly

```asm
0x1400447e0  push    rbp
0x1400447e2  push    rbx
0x1400447e3  push    rsi
0x1400447e4  push    rdi
0x1400447e5  push    r12
0x1400447e7  push    r13
0x1400447e9  push    r14
0x1400447eb  push    r15
0x1400447ed  lea     rbp, [rsp-218h]
0x1400447f5  sub     rsp, 318h
0x1400447fc  mov     rax, cs:__security_cookie
0x140044803  xor     rax, rsp
0x140044806  mov     [rbp+250h+var_50], rax
0x14004480d  xor     eax, eax
0x14004480f  mov     [rsp+350h+var_2D8], rcx
0x140044814  xorps   xmm0, xmm0
0x140044817  mov     [rbp+250h+LockState], r9
0x14004481e  mov     r13, r8
0x140044821  mov     [rbp+250h+var_2D0], ax
0x140044825  mov     r14, rdx
0x140044828  mov     rbx, rcx
0x14004482b  lea     r8d, [rax+6Ch]; Size
0x14004482f  xor     edx, edx; Val
0x140044831  lea     rcx, [rbp+250h+var_110]; void *
0x140044838  movups  xmmword ptr [rbp+250h+var_A0], xmm0
0x14004483f  movups  [rbp+250h+var_90], xmm0
0x140044846  call    memset
0x14004484b  xor     edx, edx; Val
0x14004484d  mov     [rbp+250h+var_2C0], 0
0x140044854  mov     r8d, 108h; Size
0x14004485a  lea     rcx, [rbp+250h+var_240]; void *
0x14004485e  call    memset
0x140044863  mov     r15, [rbx+17F8h]
0x14004486a  add     rbx, 1710h
0x140044871  xor     esi, esi
0x140044873  mov     [rbp+250h+var_2B0], r15
0x140044877  cmp     r13, r15
0x14004487a  xorps   xmm0, xmm0
0x14004487d  movups  [rbp+250h+var_80], xmm0
0x140044884  setz    sil
0x140044888  mov     edi, 0FFFFh
0x14004488d  xor     eax, eax
0x14004488f  mov     [rbp+250h+var_70], ax
0x140044896  mov     eax, cs:dword_1400B1088
0x14004489c  cmp     eax, 4
0x14004489f  jbe     loc_14004499B
0x1400448a5  mov     edx, 4
0x1400448aa  lea     rcx, dword_1400B1088
0x1400448b1  call    _tlgKeywordOn
0x1400448b6  test    al, al
0x1400448b8  jz      loc_14004499B
0x1400448be  mov     eax, [rbx+0F8h]
0x1400448c4  mov     ecx, [rbx+18h]; this
0x1400448c7  mov     dword ptr [rbp+250h+var_2C8], eax
0x1400448ca  mov     dword ptr [rsp+350h+var_2E0], esi
0x1400448ce  call    ?ToLogString@stringify@@YAPEBDW4_DOT11_CIPHER_ALGORITHM@@@Z; stringify::ToLogString(_DOT11_CIPHER_ALGORITHM)
0x1400448d3  mov     ecx, [rbx+14h]; this
0x1400448d6  mov     [rbp+250h+var_2B8], rax
0x1400448da  call    ?ToLogString@stringify@@YAPEBDW4_DOT11_CIPHER_ALGORITHM@@@Z; stringify::ToLogString(_DOT11_CIPHER_ALGORITHM)
0x1400448df  mov     ecx, [rbx+10h]; this
0x1400448e2  mov     [rbp+250h+var_260], rax
0x1400448e6  call    ?ToLogString@stringify@@YAPEBDW4_DOT11_CIPHER_ALGORITHM@@@Z; stringify::ToLogString(_DOT11_CIPHER_ALGORITHM)
0x1400448eb  mov     ecx, [rbx+1Ch]; this
0x1400448ee  mov     [rbp+250h+var_258], rax
0x1400448f2  call    ?ToLogString@stringify@@YAPEBDW4RSNA_AKM_SUITE@@@Z; stringify::ToLogString(RSNA_AKM_SUITE)
0x1400448f7  mov     ecx, [rbx+0Ch]; this
0x1400448fa  mov     [rbp+250h+var_250], rax
0x1400448fe  call    ?ToLogString@stringify@@YAPEBDW4_DOT11_AUTH_ALGORITHM@@@Z; stringify::ToLogString(_DOT11_AUTH_ALGORITHM)
0x140044903  lea     rcx, [r14+10h]
0x140044907  mov     [rbp+250h+var_270], rax
0x14004490b  lea     r8, [rbp+250h+var_80]
0x140044912  call    MacAddrToLogString
0x140044917  mov     ecx, [rbx+520h]
0x14004491d  mov     qword ptr [rbp+250h+var_120.Data1], rax
0x140044924  cmp     ecx, edi
0x140044926  jbe     short loc_14004492B
0x140044928  movzx   ecx, di
0x14004492b  lea     rax, [rbx+524h]
0x140044932  mov     [rbp+250h+var_2A0], cx
0x140044936  mov     [rbp+250h+var_2A8], rax
0x14004493a  lea     rdx, byte_1400A6F79
0x140044941  lea     rax, [rsp+350h+var_2E0]
0x140044946  mov     [rsp+350h+var_2F0], rax
0x14004494b  lea     rax, [rbp+250h+var_2C8]
0x14004494f  mov     [rsp+350h+var_2F8], rax
0x140044954  lea     rax, [rbp+250h+var_2B8]
0x140044958  mov     [rsp+350h+var_300], rax
0x14004495d  lea     rax, [rbp+250h+var_260]
0x140044961  mov     qword ptr [rsp+350h+var_308], rax
0x140044966  lea     rax, [rbp+250h+var_258]
0x14004496a  mov     [rsp+350h+var_310], rax
0x14004496f  lea     rax, [rbp+250h+var_250]
0x140044973  mov     [rsp+350h+var_318], rax
0x140044978  lea     rax, [rbp+250h+var_270]
0x14004497c  mov     [rsp+350h+var_320], rax
0x140044981  lea     rax, [rbp+250h+var_120]
0x140044988  mov     [rsp+350h+var_328], rax
0x14004498d  lea     rax, [rbp+250h+var_2A8]
0x140044991  mov     [rsp+350h+var_330], rax
0x140044996  call    ??$Write@U?$_tlgWrapperArray@$00@@U?$_tlgWrapSz@D@@U2@U2@U2@U2@U2@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$00@@AEBU?$_tlgWrapSz@D@@44444AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<1> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14004499b  mov     eax, [rbx+0Ch]
0x14004499e  sub     eax, 7
0x1400449a1  test    eax, 0FFFFFFFDh
0x1400449a6  jnz     loc_140044A2E
0x1400449ac  cmp     dword ptr [rbx+4E8h], 0
0x1400449b3  jnz     short loc_140044A2E
0x1400449b5  cmp     dword ptr [rbx+0FCh], 2
0x1400449bc  jb      short loc_140044A2E
0x1400449be  mov     rcx, [rsp+350h+var_2D8]
0x1400449c3  mov     rdx, [rcx+1700h]
0x1400449ca  test    rdx, rdx
0x1400449cd  jz      short loc_140044A33
0x1400449cf  mov     eax, [r14+10h]
0x1400449d3  xorps   xmm0, xmm0
0x1400449d6  mov     qword ptr [rbp+250h+var_120.Data1], 0
0x1400449e1  mov     [rbp+250h+var_120.Data1], eax
0x1400449e7  movzx   eax, word ptr [r14+14h]
0x1400449ec  mov     [rbp+250h+var_120.Data2], ax
0x1400449f3  mov     eax, [r14+2Ch]
0x1400449f7  mov     dword ptr [rbp+250h+var_120.Data4], eax
0x1400449fd  lea     rax, [rbp+250h+var_120]
0x140044a04  mov     [rbp+250h+var_288], rax
0x140044a08  mov     [rbp+250h+var_298], 0Ch
0x140044a10  mov     [rbp+250h+var_290], 0Ch
0x140044a18  movdqu  [rbp+250h+var_280], xmm0
0x140044a1d  mov     rcx, [rdx+18h]
0x140044a21  lea     rdx, [rbp+250h+var_298]; struct DOT11_AUTH_UPCALL_REQUEST *
0x140044a25  add     rcx, 28h ; '('; Csq
0x140044a29  call    ?NwfUpcallMsg@@YAJPEAUNWF_AUTH_UPCALL@@PEBUDOT11_AUTH_UPCALL_REQUEST@@@Z; NwfUpcallMsg(NWF_AUTH_UPCALL *,DOT11_AUTH_UPCALL_REQUEST const *)
0x140044a2e  mov     rcx, [rsp+350h+var_2D8]; struct _VELAN *
0x140044a33  cmp     dword ptr [rcx+171Ch], 0Ah
0x140044a3a  jnz     short loc_140044A49
0x140044a3c  mov     rdx, r14; struct DOT11_MAC_STATE_ENTRY *
0x140044a3f  call    ?OWEGetAuthInfo@@YAJPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@@Z; OWEGetAuthInfo(_VELAN *,DOT11_MAC_STATE_ENTRY *)
0x140044a44  mov     rcx, [rsp+350h+var_2D8]
0x140044a49  mov     rdx, r14
0x140044a4c  call    GetActivePmk
0x140044a51  mov     [rbp+250h+var_2C8], rax
0x140044a55  mov     rdi, rax
0x140044a58  test    rax, rax
0x140044a5b  jnz     loc_140044BD5
0x140044a61  cmp     r13, r15
0x140044a64  jz      loc_140044BCC
0x140044a6a  mov     [rbx+0F8h], eax
0x140044a70  mov     rcx, [rsp+350h+var_2D8]
0x140044a75  add     rcx, 17F0h; struct DOT11_MAC_STATE_ENTRY **
0x140044a7c  cmp     [rcx], rax
0x140044a7f  jz      short loc_140044A86
0x140044a81  call    ?Dot11ReleaseMacState@@YAXPEAPEAUDOT11_MAC_STATE_ENTRY@@@Z; Dot11ReleaseMacState(DOT11_MAC_STATE_ENTRY * *)
0x140044a86  mov     rcx, [rbx+0E8h]
0x140044a8d  test    rcx, rcx
0x140044a90  jz      short loc_140044ACC
0x140044a92  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140044a96  mov     rax, [rcx]
0x140044a99  test    rax, rax
0x140044a9c  jz      short loc_140044AB2
0x140044a9e  mov     rdx, rcx; Entry
0x140044aa1  mov     rcx, rax; Lookaside
0x140044aa4  call    cs:__imp_ExFreeToNPagedLookasideList
0x140044aab  nop     dword ptr [rax+rax+00h]
0x140044ab0  jmp     short loc_140044AC1
0x140044ab2  mov     edx, [rcx+8]; Tag
0x140044ab5  call    cs:__imp_ExFreePoolWithTag
0x140044abc  nop     dword ptr [rax+rax+00h]
0x140044ac1  mov     qword ptr [rbx+0E8h], 0
0x140044acc  movzx   eax, word ptr [r13+2]
0x140044ad1  ror     ax, 8
0x140044ad5  movzx   ecx, ax
0x140044ad8  add     ecx, 14h
0x140044adb  mov     qword ptr [rbx+0E8h], 0
0x140044ae6  cmp     ecx, 10h
0x140044ae9  jb      short loc_140044B5C
0x140044aeb  mov     r15d, 7A697377h
0x140044af1  cmp     ecx, 40h ; '@'
0x140044af4  ja      short loc_140044AFF
0x140044af6  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x140044afd  jmp     short loc_140044B30
0x140044aff  cmp     ecx, 100h
0x140044b05  ja      short loc_140044B10
0x140044b07  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140044b0e  jmp     short loc_140044B30
0x140044b10  cmp     ecx, 400h
0x140044b16  ja      short loc_140044B21
0x140044b18  lea     rdi, Lookaside
0x140044b1f  jmp     short loc_140044B30
0x140044b21  cmp     ecx, 800h
0x140044b27  ja      short loc_140044B41
0x140044b29  lea     rdi, stru_1400B31C0
0x140044b30  mov     rcx, rdi; Lookaside
0x140044b33  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140044b3a  nop     dword ptr [rax+rax+00h]
0x140044b3f  jmp     short loc_140044B57
0x140044b41  xor     edi, edi
0x140044b43  mov     edx, ecx
0x140044b45  mov     r8d, r15d
0x140044b48  lea     ecx, [rdi+40h]
0x140044b4b  call    cs:__imp_ExAllocatePool2
0x140044b52  nop     dword ptr [rax+rax+00h]
0x140044b57  test    rax, rax
0x140044b5a  jnz     short loc_140044B66
0x140044b5c  mov     edi, 0C000009Ah
0x140044b61  jmp     loc_1400454DD
0x140044b66  mov     [rax], rdi
0x140044b69  mov     [rax+8], r15d
0x140044b6d  add     rax, 10h
0x140044b71  mov     [rbx+0E8h], rax
0x140044b78  lock inc dword ptr [r14+24h]
0x140044b7d  mov     rcx, [rbx+0E8h]; void *
0x140044b84  mov     rdx, r13; Src
0x140044b87  mov     [rbx+0E0h], r14
0x140044b8e  movzx   eax, word ptr [r13+2]
0x140044b93  ror     ax, 8
0x140044b97  movzx   r8d, ax
0x140044b9b  add     r8, 4; Size
0x140044b9f  call    memmove
0x140044ba4  mov     rcx, cs:WPP_GLOBAL_Control
0x140044bab  lea     r12, WPP_GLOBAL_Control
0x140044bb2  cmp     rcx, r12
0x140044bb5  jz      short loc_140044BCC
0x140044bb7  mov     rcx, [rcx+18h]
0x140044bbb  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x140044bc2  mov     edx, 12Bh
0x140044bc7  call    WPP_SF_
0x140044bcc  xor     esi, esi
0x140044bce  xor     edi, edi
0x140044bd0  jmp     loc_1400454DD
0x140044bd5  lea     rax, [r13+4]
0x140044bd9  mov     [rbp+250h+var_2B8], rax
0x140044bdd  lea     r12, WPP_GLOBAL_Control
0x140044be4  mov     eax, [rbx+0Ch]
0x140044be7  lea     r15, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x140044bee  cmp     eax, 9
0x140044bf1  jnz     loc_140044CC0
0x140044bf7  mov     rcx, [rsp+350h+var_2D8]
0x140044bfc  lea     rdx, [rdi+18h]
0x140044c00  mov     [rsp+350h+var_330], rdx
0x140044c05  lea     r9, [rdi+95h]
0x140044c0c  lea     rdx, [r14+10h]
0x140044c10  mov     dword ptr [rsp+350h+var_2E0], 41h ; 'A'
0x140044c18  add     rcx, 1FE8h
0x140044c1f  lea     r8, [rsp+350h+var_2E0]
0x140044c24  call    PmkCacheGetAuthInfo
0x140044c29  test    eax, eax
0x140044c2b  jz      short loc_140044C96
0x140044c2d  mov     eax, dword ptr [rsp+350h+var_2E0]
0x140044c31  mov     [rdi+30h], eax
0x140044c34  mov     dword ptr [rdi], 9
0x140044c3a  mov     rax, [rsp+350h+var_2D8]
0x140044c3f  mov     rcx, [rax+10h]
0x140044c43  mov     eax, [rcx+420h]
0x140044c49  test    al, 1
0x140044c4b  jz      loc_140044D2D
0x140044c51  lea     r8, [r14+10h]; unsigned __int8 *
0x140044c55  mov     edx, 6; unsigned int
0x140044c5a  lea     rcx, aPmkcachegetaut; "PmkCacheGetAuthInfo [PmkId]: Returning "...
0x140044c61  call    ?DumpBuff@@YAXPEAGIPEAE@Z; DumpBuff(ushort *,uint,uchar *)
0x140044c66  mov     edx, [rdi+30h]; unsigned int
0x140044c69  lea     r8, [rdi+95h]; unsigned __int8 *
0x140044c70  lea     rcx, aPmkcachegetaut_0; "\tPmkCacheGetAuthInfo [PmkId]: PMK:"
0x140044c77  call    ?DumpBuff@@YAXPEAGIPEAE@Z; DumpBuff(ushort *,uint,uchar *)
0x140044c7c  lea     r8, [rdi+18h]; unsigned __int8 *
0x140044c80  mov     edx, 10h; unsigned int
0x140044c85  lea     rcx, aPmkcachegetaut_1; "\tPmkCacheGetAuthInfo [PmkId]: PMKID:"
0x140044c8c  call    ?DumpBuff@@YAXPEAGIPEAE@Z; DumpBuff(ushort *,uint,uchar *)
0x140044c91  jmp     loc_140044D2D
0x140044c96  mov     rcx, cs:WPP_GLOBAL_Control
0x140044c9d  cmp     rcx, r12
0x140044ca0  jz      short loc_140044CB7
0x140044ca2  mov     rcx, [rcx+18h]
0x140044ca6  lea     r9, [r14+10h]
0x140044caa  mov     edx, 12Ch
0x140044caf  mov     r8, r15
0x140044cb2  call    WPP_SF__MAC_
0x140044cb7  mov     dword ptr [rdi+30h], 0
0x140044cbe  jmp     short loc_140044D2D
0x140044cc0  cmp     eax, 8
0x140044cc3  jnz     short loc_140044D10
0x140044cc5  mov     rcx, [rsp+350h+var_2D8]
0x140044cca  lea     rax, [rdi+18h]
0x140044cce  add     rcx, 1FE8h
0x140044cd5  mov     [rsp+350h+var_330], rax
0x140044cda  lea     rdx, [r14+10h]
0x140044cde  xor     r9d, r9d
0x140044ce1  xor     r8d, r8d
0x140044ce4  call    PmkCacheGetAuthInfo
0x140044ce9  test    eax, eax
0x140044ceb  jnz     short loc_140044D2D
0x140044ced  mov     rcx, cs:WPP_GLOBAL_Control
0x140044cf4  cmp     rcx, r12
0x140044cf7  jz      short loc_140044D2D
0x140044cf9  mov     rcx, [rcx+18h]
0x140044cfd  lea     r9, [r14+10h]
0x140044d01  mov     edx, 12Dh
0x140044d06  mov     r8, r15
0x140044d09  call    WPP_SF__MAC_
0x140044d0e  jmp     short loc_140044D2D
0x140044d10  mov     rax, [rsp+350h+var_2D8]
0x140044d15  cmp     dword ptr [rax+1C18h], 0
0x140044d1c  jz      short loc_140044D2D
0x140044d1e  mov     rax, [rbx+510h]
  ... truncated ...
```
