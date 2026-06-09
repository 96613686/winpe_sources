# Dot11ReceiveM3

- ea: `0x1400455c8`
- end: `0x14004648d`
- name: `Dot11ReceiveM3`
- size: `3781`
- prototype: ``
- caller_count: `1`
- callee_count: `40`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140043404`

## callees

- `0x1400012bc`
- `0x1400013a8`
- `0x14000170c`
- `0x14000a368`
- `0x14000a81c`
- `0x14000a934`
- `0x14000d21c`
- `0x14000d2b0`
- `0x1400185e0`
- `0x140018a0c`
- `0x140020dc0`
- `0x140020e04`
- `0x140032d88`
- `0x1400424ac`
- `0x140043158`
- `0x140044198`
- `0x1400455c8`
- `0x14004897c`
- `0x140048dc8`
- `0x140049b6c`
- `0x14004a23c`
- `0x14004e13c`
- `0x14005012c`
- `0x140050f44`
- `0x140050f84`
- `0x140051078`
- `0x1400513b4`
- `0x14005140c`
- `0x140051678`
- `0x140052dbc`
- `0x14005375c`
- `0x140053f30`
- `0x14005448c`
- `0x140091124`
- `0x1400973ec`
- `0x1400975c0`
- `0x140097684`
- `0x14009bbb0`
- `0x14009bfc0`
- `0x14009c4e0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140045cfb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046152`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140045cfb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046152`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045d0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400461d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045d0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400461d3`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400463d1`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400463d1`
- `NDIS!NdisReleaseRWLock` at `0x1400463a5`
- `NDIS!NdisReleaseRWLock` at `0x1400463a5`

## pseudocode

```c
void __fastcall Dot11ReceiveM3(
        __int64 a1,
        struct DOT11_MAC_STATE_ENTRY *a2,
        struct NWF_EAPOL_HEADER *a3,
        struct _LOCK_STATE_EX *a4)
{
  struct DOT11_MAC_STATE_ENTRY *v4; // r13
  int v6; // r15d
  __int64 v7; // rdi
  enum _DOT11_CIPHER_ALGORITHM v8; // edx
  struct NWF_PMK_ENTRY *v9; // rax
  stringify *v10; // rcx
  enum _DOT11_CIPHER_ALGORITHM v11; // edx
  union NWF_RSNA_KEY_INFO *v12; // rax
  stringify *v13; // rcx
  enum _DOT11_CIPHER_ALGORITHM v14; // edx
  const char *v15; // rax
  stringify *v16; // rcx
  enum RSNA_AKM_SUITE v17; // edx
  unsigned __int8 *v18; // rax
  stringify *v19; // rcx
  enum _DOT11_AUTH_ALGORITHM v20; // edx
  __int64 v21; // rdx
  __int64 v22; // rax
  int v23; // r8d
  int v24; // r9d
  unsigned int v25; // ecx
  __int64 v26; // r8
  unsigned __int8 *v27; // rbx
  char *v28; // rdx
  unsigned int v29; // r12d
  int v30; // ebx
  int NonceCache; // eax
  PDEVICE_OBJECT v32; // rcx
  __int64 v33; // rdx
  struct NWF_PTK *v34; // r13
  __int128 v35; // xmm0
  __int64 v36; // r12
  char v37; // al
  union NWF_RSNA_KEY_INFO *v38; // r12
  PDEVICE_OBJECT v39; // rcx
  __int64 v40; // rdx
  int updated; // eax
  PDEVICE_OBJECT v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // r9
  int v45; // eax
  struct NWF_PTK *v46; // rdx
  __int16 v47; // cx
  struct DOT11_MAC_STATE_ENTRY *v48; // r12
  ULONG *v49; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v50; // rax
  __int64 v51; // rdx
  struct NWF_EAPOL_HEADER *v52; // rax
  int v53; // r8d
  int v54; // r9d
  unsigned int v55; // ecx
  struct _VELAN *v56; // rdx
  int v57; // r8d
  int v58; // r9d
  struct NWF_EAPOL_RSNA_KEY_DESC *v59; // r9
  __int128 v60; // xmm0
  __int64 v61; // rax
  unsigned __int8 *v62; // r13
  struct _VELAN *v63; // r8
  _FILE_OBJECT *pSecurityEndpoint; // rcx
  int v65; // edx
  __int64 v66; // r9
  NWF_PMK_ENTRY *pPmk; // rax
  PDEVICE_OBJECT v68; // rcx
  __int64 v69; // rdx
  __int64 v70; // rax
  PDEVICE_OBJECT v71; // rcx
  __int64 v72; // rdx
  int v73; // ecx
  size_t v74; // [rsp+28h] [rbp-D8h]
  unsigned int v75; // [rsp+30h] [rbp-D0h]
  unsigned __int16 v76; // [rsp+30h] [rbp-D0h]
  struct _VELAN *v77; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v78[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v79; // [rsp+7Ch] [rbp-84h] BYREF
  struct DOT11_MAC_STATE_ENTRY *v80; // [rsp+80h] [rbp-80h]
  unsigned __int8 *v81; // [rsp+88h] [rbp-78h] BYREF
  int v82; // [rsp+90h] [rbp-70h] BYREF
  unsigned int Size[3]; // [rsp+94h] [rbp-6Ch] BYREF
  union NWF_RSNA_KEY_INFO *v84; // [rsp+A0h] [rbp-60h] BYREF
  struct NWF_PMK_ENTRY *ActivePmk; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int8 *v86; // [rsp+B0h] [rbp-50h] BYREF
  struct NWF_RSNA_TransitionDisable_KDE *v87; // [rsp+B8h] [rbp-48h] BYREF
  PLOCK_STATE_EX LockState; // [rsp+C0h] [rbp-40h]
  unsigned __int16 *v89; // [rsp+C8h] [rbp-38h] BYREF
  __int16 v90; // [rsp+D0h] [rbp-30h]
  __int64 v91; // [rsp+D8h] [rbp-28h] BYREF
  __int16 v92; // [rsp+E0h] [rbp-20h]
  const char *v93; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v94[3]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v95; // [rsp+108h] [rbp+8h]
  unsigned __int16 v96[136]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v97; // [rsp+230h] [rbp+130h] BYREF
  int v98; // [rsp+240h] [rbp+140h]
  struct _GUID v99; // [rsp+248h] [rbp+148h] BYREF
  struct NWF_PTK v100; // [rsp+260h] [rbp+160h] BYREF
  struct NWF_EAPOL_HEADER *v101[2]; // [rsp+2D0h] [rbp+1D0h] BYREF
  unsigned __int8 v102[16]; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int128 v103; // [rsp+2F0h] [rbp+1F0h]
  __int128 v104; // [rsp+300h] [rbp+200h] BYREF
  __int16 v105; // [rsp+310h] [rbp+210h]

  v101[0] = a3;
  v4 = a2;
  v80 = a2;
  v77 = (struct _VELAN *)a1;
  LockState = a4;
  v79 = 0;
  memset(&v100, 0, sizeof(v100));
  *(_DWORD *)v78 = 0;
  Size[0] = 0;
  v86 = 0;
  v87 = 0;
  v99 = 0;
  v6 = 0;
  memset(v96, 0, 0x108u);
  v82 = 0;
  v105 = 0;
  v7 = a1 + 5904;
  v104 = 0;
  if ( (unsigned int)dword_1400B1088 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400B1088, 4) )
  {
    v9 = (struct NWF_PMK_ENTRY *)stringify::ToLogString((stringify *)*(unsigned int *)(a1 + 5928), v8);
    v10 = (stringify *)*(unsigned int *)(a1 + 5924);
    ActivePmk = v9;
    v12 = (union NWF_RSNA_KEY_INFO *)stringify::ToLogString(v10, v11);
    v13 = (stringify *)*(unsigned int *)(a1 + 5920);
    v84 = v12;
    v15 = stringify::ToLogString(v13, v14);
    v16 = (stringify *)*(unsigned int *)(a1 + 5932);
    *(_QWORD *)&Size[1] = v15;
    v18 = (unsigned __int8 *)stringify::ToLogString(v16, v17);
    v19 = (stringify *)*(unsigned int *)(a1 + 5916);
    v81 = v18;
    v93 = stringify::ToLogString(v19, v20);
    v22 = MacAddrToLogString(v4->MacHashEntry.MacKey, v21, &v104);
    v25 = *(_DWORD *)(a1 + 7216);
    v91 = v22;
    if ( v25 > 0xFFFF )
      v25 = 0xFFFF;
    v90 = v25;
    v89 = (unsigned __int16 *)(a1 + 7220);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v25,
      (unsigned int)&word_1400A6E76,
      v23,
      v24,
      (__int64)&v89,
      (__int64)&v91,
      (__int64)&v93,
      (__int64)&v81,
      (__int64)&Size[1],
      (__int64)&v84,
      (__int64)&ActivePmk);
  }
  ActivePmk = (struct NWF_PMK_ENTRY *)GetActivePmk(v77, v4);
  if ( !ActivePmk )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 308, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
    return;
  }
  v27 = (unsigned __int8 *)v101[0];
  v28 = (char *)v101[0] + 4;
  v29 = (unsigned __int16)__ROR2__(*(_WORD *)((char *)v101[0] + 7), 8);
  *(_QWORD *)&Size[1] = (char *)v101[0] + 4;
  if ( v29 - 1 > 0x1F )
  {
    v30 = -1073741823;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 309, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v29);
    goto LABEL_110;
  }
  v84 = (struct NWF_EAPOL_HEADER *)((char *)v101[0] + 5);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_LD(WPP_GLOBAL_Control->AttachedDevice, v28, v26, v29, (*(unsigned __int16 *)((char *)v101[0] + 5) >> 1) & 1);
    v28 = (char *)(v27 + 4);
  }
  if ( !*(_DWORD *)(v7 + 1028) )
  {
    v30 = -1073741823;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 311, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
LABEL_110:
    memset(&v100, 0, sizeof(v100));
    v63 = v77;
    pSecurityEndpoint = v77->pSecurityEndpoint;
    if ( !pSecurityEndpoint || (!*(_DWORD *)(v7 + 1256) || v30 < 0 || v6) && !v6 )
    {
LABEL_132:
      if ( v30 && byte_1400B2801 < 0 )
        McTemplateK0pjq_EtwWriteTransfer(
          (_DWORD)pSecurityEndpoint,
          (unsigned int)ReceiveM3PacketError,
          (_DWORD)v63 + 4920,
          (unsigned int)&v77,
          (__int64)&v63->gDeviceId,
          v30);
      FreeRSNMessageKeyData((struct NWF_RSN_KEY_DATA *)v96);
      return;
    }
    *(_QWORD *)&v97 = 0;
    LODWORD(v97) = *(_DWORD *)v4->MacHashEntry.MacKey;
    WORD2(v97) = *(_WORD *)&v4->MacHashEntry.MacKey[4];
    DWORD2(v97) = v4->uSessionId;
    v94[2] = &v97;
    v94[0] = 11;
    v94[1] = 20;
    v95 = 0;
    HIDWORD(v97) = v30;
    v98 = v6;
    NwfUpcallMsg((PIO_CSQ)((char *)pSecurityEndpoint->FsContext + 40), (const struct DOT11_AUTH_UPCALL_REQUEST *)v94);
    if ( *(_DWORD *)(v7 + 8) == 212602624 )
    {
      v65 = *(_DWORD *)(v7 + 1144);
      v66 = v7 + 1156;
    }
    else
    {
      v65 = 0;
      v66 = 0;
    }
    LODWORD(v74) = v65;
    *(_OWORD *)v101 = 0;
    if ( !(unsigned int)PmkCacheFinalizeOn4WayCompletion(
                          &v77->Dot11PmkCache,
                          (__int64)v77->CurrentAddress,
                          v74,
                          v66,
                          (__int64)v101) )
      goto LABEL_131;
    pPmk = v4->pPmk;
    if ( pPmk )
    {
      *(_OWORD *)pPmk->PMKID = *(_OWORD *)v101;
      v68 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_125;
      v69 = 328;
    }
    else
    {
      v68 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_125;
      v69 = 329;
    }
    WPP_SF_(v68->AttachedDevice, v69, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
LABEL_125:
    v70 = *(_QWORD *)(v7 + 240);
    if ( v70 )
    {
      *(_OWORD *)(v70 + 24) = *(_OWORD *)v101;
      v71 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v72 = 330;
LABEL_130:
        WPP_SF_(v71->AttachedDevice, v72, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
      }
    }
    else
    {
      v71 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v72 = 331;
        goto LABEL_130;
      }
    }
LABEL_131:
    NdisReleaseRWLock(v77->pRWLock, LockState);
    Dot11FlushPMKIDCache(v77, v4);
    NdisAcquireRWLockWrite(v77->pRWLock, LockState, 0);
    v63 = v77;
    goto LABEL_132;
  }
  if ( memcmp((const void *)(v7 + 280), v28 + 13, 0x20u) )
  {
    LODWORD(v81) = 0;
    goto LABEL_22;
  }
  if ( VerifyMIC(
         (enum _DOT11_AUTH_ALGORITHM)(v7 + 1032),
         *(enum RSNA_AKM_SUITE *)(v7 + 28),
         (unsigned __int8 *)(v7 + 1044),
         *(_DWORD *)(v7 + 1032),
         *(_DWORD *)(v7 + 48),
         (struct NWF_EAPOL_HEADER *)v27) < 0 )
  {
    LODWORD(v81) = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 312, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, 0);
LABEL_22:
    NonceCache = QueryNonceCache(v77, v4, ActivePmk, v29, (struct NWF_NONCE_CACHE *)(v7 + 344), v27 + 17, v27, v102);
    v30 = NonceCache;
    if ( NonceCache < 0 )
    {
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_110;
      v33 = 313;
LABEL_25:
      WPP_SF_d(v32->AttachedDevice, v33, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, (unsigned int)NonceCache);
      goto LABEL_110;
    }
    goto LABEL_30;
  }
  v34 = (struct NWF_PTK *)(v7 + 1032);
  if ( v29 != *(_DWORD *)(v7 + 1040) )
  {
    v35 = *(_OWORD *)(v7 + 312);
    LODWORD(v81) = 1;
    *(_OWORD *)v102 = v35;
    v103 = *(_OWORD *)(v7 + 328);
    if ( v29 <= *(_DWORD *)(v7 + 1040) )
    {
      *(_DWORD *)(v7 + 1040) = v29;
LABEL_35:
      *(_OWORD *)(v7 + 1032) = *(_OWORD *)&v34->KCKLength;
      *(_OWORD *)(v7 + 1048) = *(_OWORD *)&v34->PTK[4];
      *(_OWORD *)(v7 + 1064) = *(_OWORD *)&v34->PTK[20];
      *(_OWORD *)(v7 + 1080) = *(_OWORD *)&v34->PTK[36];
      *(_OWORD *)(v7 + 1096) = *(_OWORD *)&v34->PTK[52];
      *(_OWORD *)(v7 + 1112) = *(_OWORD *)&v34->PTK[68];
      *(_OWORD *)(v7 + 1124) = *(_OWORD *)&v34->PTK[80];
      goto LABEL_36;
    }
    v4 = v80;
LABEL_30:
    v75 = v29;
    v36 = *(_QWORD *)&Size[1];
    NonceCache = GeneratePTK(
                   v77->CurrentAddress,
                   v4->MacHashEntry.MacKey,
                   &v77->KeyContext,
                   ActivePmk,
                   v102,
                   (unsigned __int8 *)(*(_QWORD *)&Size[1] + 13LL),
                   v75,
                   v77->KeyContext.pFTContext,
                   &v100);
    v30 = NonceCache;
    if ( NonceCache < 0 )
    {
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_110;
      v33 = 314;
      goto LABEL_25;
    }
    v34 = &v100;
    if ( !(_DWORD)v81 )
    {
      *(_OWORD *)(v7 + 312) = *(_OWORD *)v102;
      *(_OWORD *)(v7 + 328) = v103;
      *(_OWORD *)(v7 + 280) = *(_OWORD *)(v36 + 13);
      *(_OWORD *)(v7 + 296) = *(_OWORD *)(v36 + 29);
    }
    goto LABEL_35;
  }
LABEL_36:
  v37 = *(_BYTE *)(v7 + 1252);
  v38 = v84;
  if ( (v37 & 0xFC) == 0 && v37 != 1 && !_bittest16((const signed __int16 *)v84, 0xEu) )
  {
    v30 = -1073741823;
    v6 = 294923;
    v39 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
LABEL_109:
      v4 = v80;
      goto LABEL_110;
    }
    v40 = 315;
LABEL_41:
    WPP_SF_(v39->AttachedDevice, v40, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
    goto LABEL_109;
  }
  if ( (*(_BYTE *)v84 & 2) == 0 )
  {
    v30 = -1073741823;
    v6 = 294926;
    v39 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_109;
    v40 = 316;
    goto LABEL_41;
  }
  updated = DecryptEapolKeyData(
              (struct NWF_EAPOL_KEY_INFO *)(v7 + 28),
              &v34->PTK[v34->KCKLength],
              v34->KEKLength,
              *(struct NWF_EAPOL_RSNA_KEY_DESC **)&Size[1],
              &v86,
              Size);
  v30 = updated;
  if ( updated < 0 )
  {
    v42 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_99;
    v43 = 317;
    goto LABEL_48;
  }
  v45 = ValidateM3KeyData(
          (struct _NWF_KEY_CONTEXT *)v7,
          v38,
          v86,
          Size[0],
          (unsigned int *)v78,
          &v87,
          (struct NWF_RSN_KEY_DATA *)v96,
          &v82);
  v30 = v45;
  if ( v45 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        318,
        WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
        (unsigned int)v45);
    v6 = *(_DWORD *)v78;
    goto LABEL_99;
  }
  v6 = *(_DWORD *)v78;
  if ( *(_DWORD *)v78 )
  {
    v30 = -1073741823;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        319,
        WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
        *(unsigned int *)v78);
    goto LABEL_99;
  }
  v78[0] = 0;
  v81 = 0;
  Dot11PrepareM4KeyMaterial((struct _NWF_KEY_CONTEXT *)v7, v46, v78, &v81);
  if ( (*(_BYTE *)v38 & 2) != 0 && v82 == 1 )
    v47 = 2;
  else
    v47 = 0;
  v48 = v80;
  v79 = v47 | v79 & 0xF8ED | ((*(_BYTE *)(v7 + 1252) & 7) << 8) | 0x801;
  v30 = ElSendSSNKeyPacket(
          v77,
          LockState,
          v80,
          (unsigned __int8 (*)[6])v77->CurrentAddress,
          (unsigned __int8 (*)[6])v80->MacHashEntry.MacKey,
          v79,
          v76,
          *(_QWORD *)(*(_QWORD *)&Size[1] + 5LL),
          0,
          v78[0],
          v81,
          v34->PTK,
          &v99);
  if ( v81 )
  {
    v49 = (ULONG *)(v81 - 16);
    v50 = (struct _NPAGED_LOOKASIDE_LIST *)*((_QWORD *)v81 - 2);
    if ( v50 )
      ExFreeToNPagedLookasideList(v50, v49);
    else
      ExFreePoolWithTag(v49, v49[2]);
  }
  if ( v30 < 0 )
  {
    v42 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      v43 = 320;
      v44 = (unsigned int)v30;
      goto LABEL_49;
    }
LABEL_99:
    v62 = v86;
    if ( v86 )
    {
      memset(v86, 0, Size[0]);
      if ( *((_QWORD *)v62 - 2) )
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v62 - 2), v62 - 16);
      else
        ExFreePoolWithTag(v62 - 16, *((_DWORD *)v62 - 2));
    }
    goto LABEL_109;
  }
  LOWORD(v98) = 0;
  v97 = 0;
  if ( (unsigned int)dword_1400B1088 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400B1088, 4) )
  {
    v89 = &v79;
    v90 = v51 - 2;
    v52 = (struct NWF_EAPOL_HEADER *)MacAddrToLogString(v48->MacHashEntry.MacKey, v51, &v97);
    v55 = *(_DWORD *)(v7 + 1312);
    v101[0] = v52;
    if ( v55 > 0xFFFF )
      v55 = 0xFFFF;
    v92 = v55;
    v91 = v7 + 1316;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapperArray<1>,_tlgWrapperByVal<2>>(
      v55,
      (unsigned int)&byte_1400A6E1F,
      v53,
      v54,
      (__int64)&v91,
      (__int64)v101,
      (__int64)&v89,
      (__int64)v78);
  }
  v56 = v77;
  if ( (*((_BYTE *)v48 + 40) & 6) == 6 && v77->pSecurityEndpoint == v77->pMSSecurityEndpoint )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      WPP_SF__MAC__MAC_(
        WPP_GLOBAL_Control->AttachedDevice,
        322,
        (unsigned int)WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
        (_DWORD)v77 + 4906,
        (__int64)v48->MacHashEntry.MacKey);
      v56 = v77;
    }
    if ( v56->pAdapt->uConfiguredOpMode == 64 )
    {
      if ( (unsigned int)dword_1400B1050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400B1050, 0x400000000000LL) )
      {
        v82 = v30;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1400B1050,
          (unsigned int)&dword_1400A6DEC,
          v57,
          v58,
          (__int64)&v82);
      }
      v56 = v77;
    }
    if ( (byte_1400B2801 & 0x20) != 0 )
    {
      McTemplateK0pjb6b6_EtwWriteTransfer(
        (_DWORD)v56 + 4920,
        (unsigned int)SendM4Packet,
        (unsigned int)&v99,
        (_DWORD)v56,
        (__int64)&v56->gDeviceId,
        (__int64)v56->CurrentAddress,
        (__int64)v48->MacHashEntry.MacKey);
      v56 = v77;
    }
    if ( _bittest16((const signed __int16 *)v84, 0xEu) )
    {
      updated = InstallPairwiseKeyWrapper(
                  &v99,
                  v56,
                  (struct _NWF_KEY_CONTEXT *)v7,
                  v48,
                  &v34->PTK[v34->KCKLength + v34->KEKLength],
                  v34->TKLength);
      v30 = updated;
      if ( updated < 0 )
      {
        v6 = 294928;
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_99;
        v43 = 323;
        goto LABEL_48;
      }
    }
    v59 = *(struct NWF_EAPOL_RSNA_KEY_DESC **)&Size[1];
    *(_DWORD *)(v7 + 1348) = 0;
    updated = InstallGroupKeyWrapper(&v99, v77, (struct _NWF_KEY_CONTEXT *)v7, v59, v48, (struct NWF_RSN_KEY_DATA *)v96);
    v30 = updated;
    if ( updated < 0 )
    {
      v6 = 294928;
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_99;
      v43 = 324;
      goto LABEL_48;
    }
    if ( v77->KeyContext.pFTContext )
    {
      if ( (unsigned int)Feature_60009473__private_IsEnabledDeviceUsageNoInline() )
      {
        if ( (ActivePmk->PMKFlags.ulValue & 0x1000) != 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 325, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
          goto LABEL_96;
        }
        updated = UpdateFTAuthenticationParametersInWDI(0, v77, v48, v77->KeyContext.pFTContext);
        v30 = updated;
        if ( updated < 0 )
        {
          v42 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_99;
          v43 = 326;
          goto LABEL_48;
        }
      }
      else
      {
        updated = UpdateFTAuthenticationParametersInWDI(0, v77, v48, v77->KeyContext.pFTContext);
        v30 = updated;
        if ( updated < 0 )
        {
          v42 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_99;
          v43 = 327;
LABEL_48:
          v44 = (unsigned int)updated;
LABEL_49:
          WPP_SF_d(v42->AttachedDevice, v43, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v44);
          goto LABEL_99;
        }
      }
    }
LABEL_96:
    memset(&v34->PTK[v34->KCKLength + v34->KEKLength], 0, v34->TKLength);
    *(_OWORD *)(v7 + 1144) = *(_OWORD *)&v34->KCKLength;
    *(_OWORD *)(v7 + 1160) = *(_OWORD *)&v34->PTK[4];
    *(_OWORD *)(v7 + 1176) = *(_OWORD *)&v34->PTK[20];
    *(_OWORD *)(v7 + 1192) = *(_OWORD *)&v34->PTK[36];
    *(_OWORD *)(v7 + 1208) = *(_OWORD *)&v34->PTK[52];
    *(_OWORD *)(v7 + 1224) = *(_OWORD *)&v34->PTK[68];
    v60 = *(_OWORD *)&v34->PTK[80];
    *(_DWORD *)(v7 + 1140) = 1;
    *(_OWORD *)(v7 + 1236) = v60;
    memset((void *)(v7 + 1032), 0, 0x6Cu);
    *(_DWORD *)(v7 + 1028) = 0;
    *(_OWORD *)(v7 + 280) = 0;
    *(_OWORD *)(v7 + 296) = 0;
    *(_OWORD *)(v7 + 312) = 0;
    *(_OWORD *)(v7 + 328) = 0;
    memset((void *)(v7 + 344), 0, 0x2ACu);
    v61 = *(_QWORD *)&Size[1];
    *(_DWORD *)(v7 + 256) = 1;
    SetReplayCounter(v77, _byteswap_uint64(*(_QWORD *)(v61 + 5)));
    NotifyReplayCounterUpdated(v77);
    SetRSNASecured(v77, 1);
    NotifySecureConnectionChange(v77);
    if ( (unsigned int)(*(_DWORD *)(v7 + 12) - 8) <= 2 && v87 )
      SendTransitionDisabledUpcall(v77, v87);
    goto LABEL_99;
  }
  v73 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 321, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
    v56 = v77;
  }
  if ( (byte_1400B2801 & 4) != 0 )
    McTemplateK0pj_EtwWriteTransfer(
      v73,
      (unsigned int)AbortReceiveM3Packet,
      (unsigned int)&v99,
      (_DWORD)v56,
      (__int64)&v56->gDeviceId);
}

```

## disassembly

```asm
0x1400455c8  push    rbp
0x1400455ca  push    rbx
0x1400455cb  push    rsi
0x1400455cc  push    rdi
0x1400455cd  push    r12
0x1400455cf  push    r13
0x1400455d1  push    r14
0x1400455d3  push    r15
0x1400455d5  lea     rbp, [rsp-228h]
0x1400455dd  sub     rsp, 328h
0x1400455e4  mov     rax, cs:__security_cookie
0x1400455eb  xor     rax, rsp
0x1400455ee  mov     [rbp+260h+var_48], rax
0x1400455f5  xor     esi, esi
0x1400455f7  mov     [rbp+260h+var_90], r8
0x1400455fe  mov     r13, rdx
0x140045601  mov     [rbp+260h+var_2E0], rdx
0x140045605  mov     rbx, rcx
0x140045608  mov     [rsp+360h+var_2F0], rcx
0x14004560d  xor     edx, edx; Val
0x14004560f  mov     [rbp+260h+LockState], r9
0x140045613  lea     r8d, [rsi+6Ch]; Size
0x140045617  mov     [rsp+360h+var_2E4], si
0x14004561c  lea     rcx, [rbp+260h+var_100]; void *
0x140045623  call    memset
0x140045628  xorps   xmm0, xmm0
0x14004562b  mov     dword ptr [rsp+360h+var_2E8], esi
0x14004562f  xor     edx, edx; Val
0x140045631  mov     dword ptr [rbp+260h+Size], esi
0x140045634  mov     r8d, 108h; Size
0x14004563a  mov     [rbp+260h+var_2B0], rsi
0x14004563e  lea     rcx, [rbp+260h+var_240]; void *
0x140045642  mov     [rbp+260h+var_2A8], rsi
0x140045646  movups  xmmword ptr [rbp+260h+var_118.Data1], xmm0
0x14004564d  mov     r15d, esi
0x140045650  call    memset
0x140045655  xor     eax, eax
0x140045657  mov     [rbp+260h+var_2D0], esi
0x14004565a  mov     [rbp+260h+var_50], ax
0x140045661  lea     rdi, [rbx+1710h]
0x140045668  mov     eax, cs:dword_1400B1088
0x14004566e  xorps   xmm0, xmm0
0x140045671  mov     ebx, 0FFFFh
0x140045676  movups  [rbp+260h+var_60], xmm0
0x14004567d  cmp     eax, 4
0x140045680  jbe     loc_140045754
0x140045686  lea     edx, [rsi+4]
0x140045689  lea     rcx, dword_1400B1088
0x140045690  call    _tlgKeywordOn
0x140045695  test    al, al
0x140045697  jz      loc_140045754
0x14004569d  mov     ecx, [rdi+18h]; this
0x1400456a0  call    ?ToLogString@stringify@@YAPEBDW4_DOT11_CIPHER_ALGORITHM@@@Z; stringify::ToLogString(_DOT11_CIPHER_ALGORITHM)
0x1400456a5  mov     ecx, [rdi+14h]; this
0x1400456a8  mov     [rbp+260h+var_2B8], rax
0x1400456ac  call    ?ToLogString@stringify@@YAPEBDW4_DOT11_CIPHER_ALGORITHM@@@Z; stringify::ToLogString(_DOT11_CIPHER_ALGORITHM)
0x1400456b1  mov     ecx, [rdi+10h]; this
0x1400456b4  mov     [rbp+260h+var_2C0], rax
0x1400456b8  call    ?ToLogString@stringify@@YAPEBDW4_DOT11_CIPHER_ALGORITHM@@@Z; stringify::ToLogString(_DOT11_CIPHER_ALGORITHM)
0x1400456bd  mov     ecx, [rdi+1Ch]; this
0x1400456c0  mov     qword ptr [rbp+260h+Size+4], rax
0x1400456c4  call    ?ToLogString@stringify@@YAPEBDW4RSNA_AKM_SUITE@@@Z; stringify::ToLogString(RSNA_AKM_SUITE)
0x1400456c9  mov     ecx, [rdi+0Ch]; this
0x1400456cc  mov     [rbp+260h+var_2D8], rax
0x1400456d0  call    ?ToLogString@stringify@@YAPEBDW4_DOT11_AUTH_ALGORITHM@@@Z; stringify::ToLogString(_DOT11_AUTH_ALGORITHM)
0x1400456d5  lea     rcx, [r13+10h]
0x1400456d9  mov     [rbp+260h+var_278], rax
0x1400456dd  lea     r8, [rbp+260h+var_60]
0x1400456e4  call    MacAddrToLogString
0x1400456e9  mov     ecx, [rdi+520h]
0x1400456ef  mov     [rbp+260h+var_288], rax
0x1400456f3  cmp     ecx, ebx
0x1400456f5  jbe     short loc_1400456FA
0x1400456f7  movzx   ecx, bx
0x1400456fa  lea     rax, [rdi+524h]
0x140045701  mov     [rbp+260h+var_290], cx
0x140045705  mov     [rbp+260h+var_298], rax
0x140045709  lea     rdx, word_1400A6E76
0x140045710  lea     rax, [rbp+260h+var_2B8]
0x140045714  mov     [rsp+360h+var_310], rax
0x140045719  lea     rax, [rbp+260h+var_2C0]
0x14004571d  mov     qword ptr [rsp+360h+var_318], rax
0x140045722  lea     rax, [rbp+260h+Size+4]
0x140045726  mov     [rsp+360h+var_320], rax
0x14004572b  lea     rax, [rbp+260h+var_2D8]
0x14004572f  mov     [rsp+360h+var_328], rax
0x140045734  lea     rax, [rbp+260h+var_278]
0x140045738  mov     [rsp+360h+var_330], rax
0x14004573d  lea     rax, [rbp+260h+var_288]
0x140045741  mov     [rsp+360h+var_338], rax
0x140045746  lea     rax, [rbp+260h+var_298]
0x14004574a  mov     [rsp+360h+var_340], rax
0x14004574f  call    ??$Write@U?$_tlgWrapperArray@$00@@U?$_tlgWrapSz@D@@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$00@@AEBU?$_tlgWrapSz@D@@44444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<1> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x140045754  mov     rcx, [rsp+360h+var_2F0]
0x140045759  mov     rdx, r13
0x14004575c  call    GetActivePmk
0x140045761  mov     [rbp+260h+var_2B8], rax
0x140045765  test    rax, rax
0x140045768  jnz     short loc_14004579B
0x14004576a  mov     rcx, cs:WPP_GLOBAL_Control
0x140045771  lea     rsi, WPP_GLOBAL_Control
0x140045778  cmp     rcx, rsi
0x14004577b  jz      loc_140046469
0x140045781  mov     rcx, [rcx+18h]
0x140045785  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004578c  mov     edx, 134h
0x140045791  call    WPP_SF_
0x140045796  jmp     loc_140046469
0x14004579b  mov     rbx, [rbp+260h+var_90]
0x1400457a2  lea     r14, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x1400457a9  lea     rdx, [rbx+4]
0x1400457ad  movzx   eax, word ptr [rdx+3]
0x1400457b1  ror     ax, 8
0x1400457b5  movzx   r12d, ax
0x1400457b9  mov     qword ptr [rbp+260h+Size+4], rdx
0x1400457bd  lea     eax, [r12-1]
0x1400457c2  cmp     eax, 1Fh
0x1400457c5  jbe     short loc_1400457FC
0x1400457c7  mov     ebx, 0C0000001h
0x1400457cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400457d3  lea     rsi, WPP_GLOBAL_Control
0x1400457da  cmp     rcx, rsi
0x1400457dd  jz      loc_1400461E3
0x1400457e3  mov     rcx, [rcx+18h]
0x1400457e7  mov     edx, 135h
0x1400457ec  mov     r9d, r12d
0x1400457ef  mov     r8, r14
0x1400457f2  call    WPP_SF_d
0x1400457f7  jmp     loc_1400461E3
0x1400457fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140045803  lea     rsi, WPP_GLOBAL_Control
0x14004580a  lea     rax, [rdx+1]
0x14004580e  mov     [rbp+260h+var_2C0], rax
0x140045812  cmp     rcx, rsi
0x140045815  jz      short loc_140045833
0x140045817  movzx   eax, word ptr [rax]
0x14004581a  mov     r9d, r12d
0x14004581d  mov     rcx, [rcx+18h]
0x140045821  shr     eax, 1
0x140045823  and     eax, 1
0x140045826  mov     dword ptr [rsp+360h+var_340], eax
0x14004582a  call    WPP_SF_LD
0x14004582f  lea     rdx, [rbx+4]
0x140045833  cmp     [rdi+404h], r15d
0x14004583a  jnz     short loc_140045867
0x14004583c  mov     ebx, 0C0000001h
0x140045841  mov     rcx, cs:WPP_GLOBAL_Control
0x140045848  cmp     rcx, rsi
0x14004584b  jz      loc_1400461E3
0x140045851  mov     rcx, [rcx+18h]
0x140045855  mov     edx, 137h
0x14004585a  mov     r8, r14
0x14004585d  call    WPP_SF_
0x140045862  jmp     loc_1400461E3
0x140045867  add     rdx, 0Dh; Buf2
0x14004586b  lea     rcx, [rdi+118h]; Buf1
0x140045872  mov     r8d, 20h ; ' '; Size
0x140045878  call    memcmp
0x14004587d  test    eax, eax
0x14004587f  jz      short loc_14004588A
0x140045881  mov     dword ptr [rbp+260h+var_2D8], 0
0x140045888  jmp     short loc_1400458D8
0x14004588a  mov     eax, [rdi+30h]
0x14004588d  lea     rcx, [rdi+408h]; enum _DOT11_AUTH_ALGORITHM
0x140045894  mov     r9d, [rcx]; unsigned int
0x140045897  lea     r8, [rcx+0Ch]; unsigned __int8 *
0x14004589b  mov     edx, [rdi+1Ch]; enum RSNA_AKM_SUITE
0x14004589e  mov     [rsp+360h+var_338], rbx; struct NWF_EAPOL_HEADER *
0x1400458a3  mov     dword ptr [rsp+360h+var_340], eax; unsigned int
0x1400458a7  call    ?VerifyMIC@@YAJW4_DOT11_AUTH_ALGORITHM@@W4RSNA_AKM_SUITE@@PEAEKKPEFAUNWF_EAPOL_HEADER@@@Z; VerifyMIC(_DOT11_AUTH_ALGORITHM,RSNA_AKM_SUITE,uchar *,ulong,ulong,NWF_EAPOL_HEADER *)
0x1400458ac  test    eax, eax
0x1400458ae  jns     loc_140045941
0x1400458b4  mov     dword ptr [rbp+260h+var_2D8], r15d
0x1400458b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400458bf  cmp     rcx, rsi
0x1400458c2  jz      short loc_1400458D8
0x1400458c4  mov     rcx, [rcx+18h]
0x1400458c8  mov     edx, 138h
0x1400458cd  xor     r9d, r9d
0x1400458d0  mov     r8, r14
0x1400458d3  call    WPP_SF_d
0x1400458d8  mov     r8, [rbp+260h+var_2B8]; struct NWF_PMK_ENTRY *
0x1400458dc  lea     rcx, [rbp+260h+var_80]
0x1400458e3  mov     [rsp+360h+var_328], rcx; unsigned __int8 *
0x1400458e8  lea     rax, [rdi+158h]
0x1400458ef  lea     rcx, [rbx+11h]
0x1400458f3  mov     [rsp+360h+var_330], rbx; void *
0x1400458f8  mov     [rsp+360h+var_338], rcx; unsigned __int8 *
0x1400458fd  mov     r9d, r12d; unsigned int
0x140045900  mov     rcx, [rsp+360h+var_2F0]; struct _VELAN *
0x140045905  mov     rdx, r13; struct DOT11_MAC_STATE_ENTRY *
0x140045908  mov     [rsp+360h+var_340], rax; struct NWF_NONCE_CACHE *
0x14004590d  call    ?QueryNonceCache@@YAJPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@PEAUNWF_PMK_ENTRY@@KPEAUNWF_NONCE_CACHE@@PEAEPEAX4@Z; QueryNonceCache(_VELAN *,DOT11_MAC_STATE_ENTRY *,NWF_PMK_ENTRY *,ulong,NWF_NONCE_CACHE *,uchar *,void *,uchar *)
0x140045912  mov     ebx, eax
0x140045914  test    eax, eax
0x140045916  jns     short loc_14004598E
0x140045918  mov     rcx, cs:WPP_GLOBAL_Control
0x14004591f  cmp     rcx, rsi
0x140045922  jz      loc_1400461E3
0x140045928  mov     edx, 139h
0x14004592d  mov     rcx, [rcx+18h]
0x140045931  mov     r9d, eax
0x140045934  mov     r8, r14
0x140045937  call    WPP_SF_d
0x14004593c  jmp     loc_1400461E3
0x140045941  lea     rax, [rdi+408h]
0x140045948  mov     r13, rax
0x14004594b  cmp     r12d, [rdi+410h]
0x140045952  jz      loc_140045A9C
0x140045958  movups  xmm0, xmmword ptr [rdi+138h]
0x14004595f  mov     dword ptr [rbp+260h+var_2D8], 1
0x140045966  movups  xmmword ptr [rbp+260h+var_80], xmm0
0x14004596d  movups  xmm1, xmmword ptr [rdi+148h]
0x140045974  movups  [rbp+260h+var_70], xmm1
0x14004597b  cmp     r12d, [rax+8]
0x14004597f  ja      short loc_14004598A
0x140045981  mov     [rax+8], r12d
0x140045985  jmp     loc_140045A48
0x14004598a  mov     r13, [rbp+260h+var_2E0]
0x14004598e  mov     rcx, [rsp+360h+var_2F0]
0x140045993  lea     rax, [rbp+260h+var_100]
0x14004599a  mov     r9, [rbp+260h+var_2B8]; struct NWF_PMK_ENTRY *
0x14004599e  lea     rdx, [r13+10h]; unsigned __int8 *
0x1400459a2  mov     [rsp+360h+var_320], rax; struct NWF_PTK *
0x1400459a7  lea     r8, [rcx+1710h]; struct _NWF_KEY_CONTEXT *
0x1400459ae  add     rcx, 132Ah; unsigned __int8 *
0x1400459b5  mov     rax, [r8+510h]
0x1400459bc  mov     [rsp+360h+var_328], rax; struct NWF_FT_CONTEXT *
0x1400459c1  mov     dword ptr [rsp+360h+var_330], r12d; unsigned int
0x1400459c6  mov     r12, qword ptr [rbp+260h+Size+4]
0x1400459ca  lea     rax, [r12+0Dh]
0x1400459cf  mov     [rsp+360h+var_338], rax; unsigned __int8 *
0x1400459d4  lea     rax, [rbp+260h+var_80]
0x1400459db  mov     [rsp+360h+var_340], rax; unsigned __int8 *
0x1400459e0  call    ?GeneratePTK@@YAJPEAE0PEAU_NWF_KEY_CONTEXT@@PEAUNWF_PMK_ENTRY@@00KPEAUNWF_FT_CONTEXT@@PEAUNWF_PTK@@@Z; GeneratePTK(uchar *,uchar *,_NWF_KEY_CONTEXT *,NWF_PMK_ENTRY *,uchar *,uchar *,ulong,NWF_FT_CONTEXT *,NWF_PTK *)
0x1400459e5  mov     ebx, eax
0x1400459e7  test    eax, eax
0x1400459e9  jns     short loc_140045A05
0x1400459eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400459f2  cmp     rcx, rsi
0x1400459f5  jz      loc_1400461E3
0x1400459fb  mov     edx, 13Ah
0x140045a00  jmp     loc_14004592D
0x140045a05  lea     r13, [rbp+260h+var_100]
0x140045a0c  cmp     dword ptr [rbp+260h+var_2D8], r15d
0x140045a10  jnz     short loc_140045A48
0x140045a12  movups  xmm0, xmmword ptr [rbp+260h+var_80]
0x140045a19  movups  xmmword ptr [rdi+138h], xmm0
0x140045a20  movups  xmm1, [rbp+260h+var_70]
0x140045a27  movups  xmmword ptr [rdi+148h], xmm1
0x140045a2e  movups  xmm0, xmmword ptr [r12+0Dh]
0x140045a34  movups  xmmword ptr [rdi+118h], xmm0
0x140045a3b  movups  xmm1, xmmword ptr [r12+1Dh]
0x140045a41  movups  xmmword ptr [rdi+128h], xmm1
0x140045a48  movups  xmm0, xmmword ptr [r13+0]
0x140045a4d  movups  xmmword ptr [rdi+408h], xmm0
0x140045a54  movups  xmm1, xmmword ptr [r13+10h]
0x140045a59  movups  xmmword ptr [rdi+418h], xmm1
0x140045a60  movups  xmm0, xmmword ptr [r13+20h]
0x140045a65  movups  xmmword ptr [rdi+428h], xmm0
0x140045a6c  movups  xmm1, xmmword ptr [r13+30h]
0x140045a71  movups  xmmword ptr [rdi+438h], xmm1
0x140045a78  movups  xmm0, xmmword ptr [r13+40h]
0x140045a7d  movups  xmmword ptr [rdi+448h], xmm0
0x140045a84  movups  xmm1, xmmword ptr [r13+50h]
0x140045a89  movups  xmmword ptr [rdi+458h], xmm1
0x140045a90  movups  xmm0, xmmword ptr [r13+5Ch]
0x140045a95  movups  xmmword ptr [rdi+464h], xmm0
0x140045a9c  mov     al, [rdi+4E4h]
0x140045aa2  mov     r12, [rbp+260h+var_2C0]
0x140045aa6  test    al, 0FCh
0x140045aa8  jnz     short loc_140045AE8
0x140045aaa  cmp     al, 1
0x140045aac  jz      short loc_140045AE8
0x140045aae  bt      word ptr [r12], 0Eh
0x140045ab5  jb      short loc_140045AE8
0x140045ab7  mov     ebx, 0C0000001h
0x140045abc  mov     r15d, 4800Bh
0x140045ac2  mov     rcx, cs:WPP_GLOBAL_Control
0x140045ac9  cmp     rcx, rsi
0x140045acc  jz      loc_1400461DF
0x140045ad2  mov     edx, 13Bh
0x140045ad7  mov     rcx, [rcx+18h]
0x140045adb  mov     r8, r14
0x140045ade  call    WPP_SF_
0x140045ae3  jmp     loc_1400461DF
0x140045ae8  test    byte ptr [r12], 2
0x140045aed  jnz     short loc_140045B11
0x140045aef  mov     ebx, 0C0000001h
0x140045af4  mov     r15d, 4800Eh
0x140045afa  mov     rcx, cs:WPP_GLOBAL_Control
0x140045b01  cmp     rcx, rsi
0x140045b04  jz      loc_1400461DF
0x140045b0a  mov     edx, 13Ch
0x140045b0f  jmp     short loc_140045AD7
0x140045b11  mov     edx, [r13+0]
0x140045b15  lea     rax, [rbp+260h+Size]
0x140045b19  mov     r9, qword ptr [rbp+260h+Size+4]; struct NWF_EAPOL_RSNA_KEY_DESC *
0x140045b1d  lea     rcx, [rdi+1Ch]; struct NWF_EAPOL_KEY_INFO *
0x140045b21  mov     r8d, [r13+4]; unsigned int
  ... truncated ...
```
