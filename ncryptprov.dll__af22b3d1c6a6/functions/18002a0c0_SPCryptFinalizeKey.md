# SPCryptFinalizeKey

- ea: `0x18002a0c0`
- end: `0x18002b456`
- name: `SPCryptFinalizeKey`
- size: `5014`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `6`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180027778`
- `0x1800489c8`
- `0x1800491d4`
- `0x18005b338`
- `0x18005bbcc`
- `0x18005e958`

## callees

- `0x180005290`
- `0x180008840`
- `0x180009440`
- `0x18000b250`
- `0x180014558`
- `0x180014c60`
- `0x18001a050`
- `0x18001a6d8`
- `0x18001b634`
- `0x1800209b4`
- `0x1800245d0`
- `0x180024870`
- `0x180027410`
- `0x180028114`
- `0x180029004`
- `0x1800294e4`
- `0x18002a0c0`
- `0x180032c10`
- `0x180035c9c`
- `0x18004bfb8`
- `0x18004d354`
- `0x180059588`
- `0x18005d3f4`
- `0x180062310`
- `0x180063010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18002a5ba`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002a5ba`
- `ntdll!RtlReleaseResource` at `0x18002b3e5`
- `ntdll!RtlReleaseResource` at `0x18002b42d`
- `ntdll!RtlReleaseResource` at `0x18002b3e5`
- `ntdll!RtlReleaseResource` at `0x18002b42d`
- `ntdll!RtlAcquireResourceShared` at `0x18002a144`
- `ntdll!RtlAcquireResourceShared` at `0x18002a144`
- `ntdll!RtlFreeHeap` at `0x18002a580`
- `ntdll!RtlFreeHeap` at `0x18002b410`
- `ntdll!RtlFreeHeap` at `0x18002a580`
- `ntdll!RtlFreeHeap` at `0x18002b410`
- `ntdll!RtlAllocateHeap` at `0x18002a4c3`
- `ntdll!RtlAllocateHeap` at `0x18002a4c3`
- `ntdll!RtlDllShutdownInProgress` at `0x18002ae54`
- `ntdll!RtlDllShutdownInProgress` at `0x18002ae54`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002ae48`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002b088`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002b2e8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002ae48`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002b088`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002b2e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a31b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a31b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002a304`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002a304`

## string_xrefs

- `0x18002a1a5`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18002a204`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18002a261`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18002a2ca`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18002a41c`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18002a96f`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18002abfa`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18002b357`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18002a500`: `onecore\ds\security\cryptoapi\ncrypt\storage\biopin.c`
- `0x18002a548`: `onecore\ds\security\cryptoapi\ncrypt\storage\biopin.c`
- `0x18002a6b5`: `onecore\ds\security\cryptoapi\ncrypt\storage\biopin.c`

## pseudocode

```c
__int64 __fastcall SPCryptFinalizeKey(__int64 a1, __int64 a2, int a3)
{
  __int64 v3; // r13
  __int64 v4; // rbx
  void *v6; // r12
  int v7; // edx
  int v8; // r8d
  int v9; // r12d
  int BioPinOnKeyAndSaveEncryptedPinInFile; // r14d
  int v11; // edx
  int v12; // esi
  unsigned int v13; // edi
  int v14; // r12d
  int v15; // edx
  int v16; // r8d
  signed int LastError; // eax
  bool v18; // sf
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // eax
  int v22; // edx
  int v23; // r8d
  int v24; // edx
  int v25; // r8d
  wchar_t *Heap; // rax
  __int64 v27; // rdx
  int v28; // r8d
  int v29; // esi
  int v30; // r15d
  int v31; // edx
  int v32; // r8d
  __int64 v33; // rdx
  __int64 v34; // rcx
  int v35; // edx
  __int64 v36; // rcx
  int v37; // ecx
  __int64 v38; // rax
  int v39; // ecx
  int v40; // edx
  int v41; // r8d
  int v42; // edx
  int v43; // r8d
  __int64 v44; // rax
  int v45; // edx
  int v46; // r8d
  int v47; // edx
  int v48; // r8d
  __int64 v49; // rax
  int v50; // edx
  int v51; // r8d
  int v52; // edx
  int v53; // r8d
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // rax
  unsigned int v57; // eax
  const struct _TraceLoggingMetadata_t *v58; // r8
  char *v59; // r9
  char *v60; // rcx
  char v61; // al
  char v64; // al
  char v65; // dl
  __int64 v66; // rax
  int v67; // r8d
  int v68; // eax
  char *v69; // r9
  char *v70; // rcx
  char v71; // al
  char v74; // al
  char v75; // dl
  __int64 v76; // rax
  int v77; // eax
  int v78; // r8d
  char *v79; // r9
  char *v80; // rcx
  char v81; // al
  char v84; // al
  char v85; // dl
  __int64 v86; // rax
  __int64 v87; // rax
  __int64 v88; // rcx
  char UserDataCount; // [rsp+28h] [rbp-E0h]
  char UserDataCounta; // [rsp+28h] [rbp-E0h]
  char UserDataCountb; // [rsp+28h] [rbp-E0h]
  int v93; // [rsp+58h] [rbp-B0h]
  __int64 v94; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v95; // [rsp+68h] [rbp-A0h] BYREF
  void *v96; // [rsp+70h] [rbp-98h]
  __int64 v97; // [rsp+78h] [rbp-90h] BYREF
  __int64 v98; // [rsp+80h] [rbp-88h] BYREF
  __int64 v99; // [rsp+88h] [rbp-80h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+90h] [rbp-78h] BYREF
  EVENT_DESCRIPTOR v101; // [rsp+A0h] [rbp-68h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+B0h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+B8h] [rbp-50h] BYREF
  char *v104; // [rsp+C8h] [rbp-40h]
  unsigned int v105; // [rsp+D0h] [rbp-38h]
  int v106; // [rsp+D4h] [rbp-34h]
  __int64 *v107; // [rsp+D8h] [rbp-30h]
  __int64 v108; // [rsp+E0h] [rbp-28h]
  __int64 *v109; // [rsp+E8h] [rbp-20h]
  __int64 v110; // [rsp+F0h] [rbp-18h]
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+F8h] [rbp-10h]
  __int64 v112; // [rsp+100h] [rbp-8h]
  EVENT_DESCRIPTOR *v113; // [rsp+108h] [rbp+0h]
  __int64 v114; // [rsp+110h] [rbp+8h]
  __int64 *v115; // [rsp+118h] [rbp+10h]
  __int64 v116; // [rsp+120h] [rbp+18h]

  v3 = a1;
  v4 = a2;
  v93 = 0;
  v6 = 0;
  v96 = 0;
  v98 = 0;
  LODWORD(v99) = 0;
  LODWORD(v95) = 0;
  PerformanceCount.QuadPart = 0;
  if ( !a1 || *(_DWORD *)a1 < 0xA0u || *(_DWORD *)(a1 + 4) != 1263751248 )
  {
    v3 = 0;
    v4 = 0;
    BioPinOnKeyAndSaveEncryptedPinInFile = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
        54);
    Feature_Key_Guard_Attestation__private_IsEnabledPreCheck();
    v12 = 0;
LABEL_257:
    KspCryptAuditCryptOperation(0, v11, v4, 2481, BioPinOnKeyAndSaveEncryptedPinInFile);
    goto LABEL_258;
  }
  RtlAcquireResourceShared((PRTL_RESOURCE)(a1 + 64), 1u);
  if ( !v4 || *(_DWORD *)v4 < 0x248u || *(_DWORD *)(v4 + 4) != 1263751243 )
  {
    v4 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        v8,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
        63);
    Feature_Key_Guard_Attestation__private_IsEnabledPreCheck();
    BioPinOnKeyAndSaveEncryptedPinInFile = -2146893786;
    v12 = 0;
    goto LABEL_249;
  }
  v9 = -1073741823;
  if ( *(_DWORD *)(v4 + 44) == 1 )
  {
    BioPinOnKeyAndSaveEncryptedPinInFile = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        v8,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
        70);
LABEL_11:
    Feature_Key_Guard_Attestation__private_IsEnabledPreCheck();
    v12 = 0;
    goto LABEL_171;
  }
  if ( (a3 & 0xFFFF7DB7) != 0 )
  {
    BioPinOnKeyAndSaveEncryptedPinInFile = -2146893815;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        v8,
        (unsigned int)"Status",
        9,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
        80);
    goto LABEL_11;
  }
  v13 = a3 & 8;
  v14 = a3 & 0x200;
  if ( (a3 & 0x8000) != 0 )
  {
    if ( (a3 & 0x200) != 0 )
    {
      BioPinOnKeyAndSaveEncryptedPinInFile = -2146893815;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v7,
          v8,
          (unsigned int)"Status",
          9,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
          97);
LABEL_21:
      Feature_Key_Guard_Attestation__private_IsEnabledPreCheck();
      v12 = 0;
      v9 = -1073741823;
      goto LABEL_171;
    }
    if ( *(_DWORD *)(v4 + 36) || *(_QWORD *)(v4 + 208) )
    {
      BioPinOnKeyAndSaveEncryptedPinInFile = -2146893815;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v7,
          v8,
          (unsigned int)"Status",
          9,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
          114);
      goto LABEL_21;
    }
  }
  if ( QueryPerformanceCounter(&PerformanceCount) )
  {
    LODWORD(v94) = 0;
  }
  else
  {
    LastError = GetLastError();
    LODWORD(v94) = LastError;
    v18 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0xC0070000;
      LODWORD(v94) = LastError;
      v18 = LastError < 0;
    }
    if ( v18 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)&WPP_5b095617bbfd389ce3c01d1846ed1dee_Traceguids,
        (unsigned int)"SPCryptFinalizeKey",
        LastError);
  }
  if ( (a3 & 0x8000) != 0 )
    *(_DWORD *)(v4 + 564) |= 1u;
  v19 = *(_QWORD *)(v4 + 416);
  if ( v19 && (*(_BYTE *)(v19 + 4) & 1) != 0 && g_dwStrongKeyForcePassword == 2 )
    *(_DWORD *)(*(_QWORD *)(v4 + 416) + 4LL) |= 2u;
  v20 = *(_QWORD *)(v4 + 416);
  if ( v20 && (*(_BYTE *)(v20 + 4) & 2) != 0 )
    *(_DWORD *)(v4 + 428) |= 1u;
  if ( *(_DWORD *)(v4 + 568) || !v20 )
    goto LABEL_71;
  if ( (*(_BYTE *)(v20 + 4) & 4) != 0 )
  {
    if ( *(_QWORD *)(v4 + 56) )
    {
      Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0xDEu);
      *(_QWORD *)(v4 + 16) = Heap;
      if ( Heap )
      {
        BioPinOnKeyAndSaveEncryptedPinInFile = AddMachineGuidAndAppContainerSidHashToContainerNameW(
                                                 *(STRSAFE_PCNZWCH *)(v4 + 8),
                                                 *(_DWORD *)(v4 + 528),
                                                 Heap);
        if ( BioPinOnKeyAndSaveEncryptedPinInFile )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v27,
              v28,
              (unsigned int)"Status",
              BioPinOnKeyAndSaveEncryptedPinInFile,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\biopin.c",
              204);
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)(v4 + 16));
          *(_QWORD *)(v4 + 16) = 0;
        }
        else
        {
          BioPinOnKeyAndSaveEncryptedPinInFile = CreateBioPinOnKeyAndSaveEncryptedPinInFile(v4, v27);
          if ( !BioPinOnKeyAndSaveEncryptedPinInFile )
            goto LABEL_71;
        }
      }
      else
      {
        BioPinOnKeyAndSaveEncryptedPinInFile = -2146893810;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v15,
            v16,
            (unsigned int)"Status",
            14,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\biopin.c",
            192);
      }
    }
    else
    {
      BioPinOnKeyAndSaveEncryptedPinInFile = -2146893821;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v15,
          v16,
          (unsigned int)"Status",
          3,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\biopin.c",
          180);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        v16,
        (unsigned int)"Status",
        BioPinOnKeyAndSaveEncryptedPinInFile,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
        209);
    goto LABEL_53;
  }
  v21 = KspCheckStrongKey(v4);
  BioPinOnKeyAndSaveEncryptedPinInFile = v21;
  if ( v21 < 0 )
  {
    if ( v21 != -2146893778 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v22,
          v23,
          (unsigned int)"Status",
          v21,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
          180);
LABEL_53:
      Feature_Key_Guard_Attestation__private_IsEnabledPreCheck();
      v9 = v94;
      v12 = v93;
      goto LABEL_171;
    }
    if ( (a3 & 0x40) != 0 )
    {
      BioPinOnKeyAndSaveEncryptedPinInFile = -2146893790;
      Feature_Key_Guard_Attestation__private_IsEnabledPreCheck();
      v9 = v94;
      v12 = 0;
      goto LABEL_171;
    }
    BioPinOnKeyAndSaveEncryptedPinInFile = KspCallCredUI(v4, 0);
    if ( BioPinOnKeyAndSaveEncryptedPinInFile )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v24,
          v25,
          (unsigned int)"Status",
          BioPinOnKeyAndSaveEncryptedPinInFile,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
          195);
      goto LABEL_53;
    }
  }
LABEL_71:
  v29 = 0;
  v30 = 0;
  RtlAcquireResourceExclusive((PRTL_RESOURCE)(v4 + 304), 1u);
  v93 = 1;
  if ( *(_DWORD *)(v4 + 144) )
  {
    v33 = *(_QWORD *)(v4 + 200);
    *(_DWORD *)&EventDescriptor.Id = 0;
    LODWORD(v97) = 4;
    if ( v33 )
    {
      v34 = 0;
      while ( *(_WORD *)(v33 + 2 * v34) == aIsolatedKeyEnv[v34]
           && *(_WORD *)(v33 + 2 * v34 + 2) == aIsolatedKeyEnv[v34 + 1] )
      {
        v34 += 2;
        if ( v34 == 22 )
        {
LABEL_77:
          v30 = 1;
          goto LABEL_78;
        }
      }
      v36 = -1;
      do
      {
        if ( *(_WORD *)(v33 + 2 * v36 + 2) != aPkcs11rsaaeswr[v36 + 1] )
          break;
        v36 += 2;
        if ( v36 == 21 )
          goto LABEL_77;
      }
      while ( *(_WORD *)(v33 + 2 * v36) == aPkcs11rsaaeswr[v36] );
    }
LABEL_78:
    BioPinOnKeyAndSaveEncryptedPinInFile = SPCryptGetKeyProperty(
                                             v3,
                                             v4,
                                             L"Key Usage",
                                             (unsigned int *)&EventDescriptor.Id,
                                             4u,
                                             (ULONG *)&v97,
                                             0);
    if ( BioPinOnKeyAndSaveEncryptedPinInFile )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v35,
          v32,
          (unsigned int)"Status",
          BioPinOnKeyAndSaveEncryptedPinInFile,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
          3);
      goto LABEL_53;
    }
    switch ( *(_DWORD *)&EventDescriptor.Id )
    {
      case 8:
        v13 |= 0x10u;
        break;
      case 0x20:
        v13 |= 0x40u;
        break;
      case 0x10:
        Feature_Key_Guard_Attestation__private_IsEnabledPreCheck();
        if ( (unsigned int)VerifyValidAttestationAlg(*(unsigned int *)(*(_QWORD *)(v4 + 64) + 8LL)) )
        {
          if ( (*(_DWORD *)&EventDescriptor.Id & 0xFFFBFF4F) == 0 )
            v13 |= 0x20u;
        }
        break;
    }
    v31 = v13 | 4;
    if ( !*(_DWORD *)(v4 + 148) )
      v31 = v13;
    v13 = v31;
    if ( !v30 )
    {
      v37 = *(_DWORD *)(v4 + 36);
      v13 = v31 | 1;
      if ( (v37 & 2) == 0 )
        v13 = v31;
      if ( (v37 & 8) != 0 )
        v13 |= 2u;
    }
    if ( (v13 & 0x50) != 0 && (v13 & 3) != 0 )
    {
      BioPinOnKeyAndSaveEncryptedPinInFile = -2146893813;
      Feature_Key_Guard_Attestation__private_IsEnabledPreCheck();
      v9 = v94;
      v12 = 1;
      goto LABEL_171;
    }
  }
  v38 = *(_QWORD *)(v4 + 64);
  v39 = *(_DWORD *)(v38 + 8);
  if ( v39 == 1 )
    goto LABEL_134;
  if ( v39 == 7 || (unsigned int)(*(_DWORD *)(v38 + 32) - 196612) <= 5 )
  {
    if ( v39 != 7 )
      goto LABEL_116;
LABEL_134:
    if ( v14 )
    {
      BioPinOnKeyAndSaveEncryptedPinInFile = -2146893815;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v31,
          v32,
          (unsigned int)"Status",
          9,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
          91);
      goto LABEL_53;
    }
    BioPinOnKeyAndSaveEncryptedPinInFile = FinalizeCipherOrKDFKey(v4, v13);
    if ( BioPinOnKeyAndSaveEncryptedPinInFile < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v47,
          v48,
          (unsigned int)"Status",
          BioPinOnKeyAndSaveEncryptedPinInFile,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
          101);
      goto LABEL_53;
    }
    if ( !v30 )
      goto LABEL_148;
    goto LABEL_143;
  }
  if ( v14 )
    v29 = 1;
LABEL_116:
  if ( *(_QWORD *)(v4 + 208) )
  {
    BioPinOnKeyAndSaveEncryptedPinInFile = ImportKey((_QWORD *)v4, v13);
    if ( BioPinOnKeyAndSaveEncryptedPinInFile )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v40,
          v41,
          (unsigned int)"Status",
          BioPinOnKeyAndSaveEncryptedPinInFile,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
          116);
      goto LABEL_53;
    }
  }
  else
  {
    BioPinOnKeyAndSaveEncryptedPinInFile = FinalizeKey(v4, v13);
    if ( BioPinOnKeyAndSaveEncryptedPinInFile )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v42,
          v43,
          (unsigned int)"Status",
          BioPinOnKeyAndSaveEncryptedPinInFile,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
          129);
      goto LABEL_53;
    }
  }
  if ( v30 )
  {
    v44 = *(_QWORD *)(v4 + 168);
    *(_DWORD *)&EventDescriptor.Id = 0;
    LODWORD(v97) = 0;
    BioPinOnKeyAndSaveEncryptedPinInFile = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, EVENT_DESCRIPTOR *, __int64, __int64 *, _DWORD))(v44 + 16))(
                                             *(_QWORD *)(v4 + 112),
                                             L"Export Policy",
                                             &EventDescriptor,
                                             4,
                                             &v97,
                                             0);
    if ( BioPinOnKeyAndSaveEncryptedPinInFile < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v45,
          v46,
          (unsigned int)"Status",
          BioPinOnKeyAndSaveEncryptedPinInFile,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
          152);
      goto LABEL_53;
    }
    if ( (EventDescriptor.Id & 0x10) != 0 )
    {
      *(_DWORD *)(v4 + 40) = 8;
    }
    else if ( (EventDescriptor.Id & 0x40) != 0 )
    {
      *(_DWORD *)(v4 + 40) = 32;
    }
LABEL_143:
    v49 = *(_QWORD *)(v4 + 64);
    LODWORD(v97) = 0;
    *(_DWORD *)(v4 + 28) = 0;
    if ( *(_DWORD *)(v49 + 96) )
    {
      BioPinOnKeyAndSaveEncryptedPinInFile = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *, __int64, __int64, __int64 *, _DWORD))(*(_QWORD *)(v4 + 168) + 16LL))(
                                               *(_QWORD *)(v4 + 112),
                                               L"KeyStrength",
                                               v4 + 28,
                                               4,
                                               &v97,
                                               0);
      if ( BioPinOnKeyAndSaveEncryptedPinInFile < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v50,
            v51,
            (unsigned int)"Status",
            BioPinOnKeyAndSaveEncryptedPinInFile,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
            198);
        goto LABEL_53;
      }
    }
  }
LABEL_148:
  if ( !*(_DWORD *)(v4 + 568) )
  {
    BioPinOnKeyAndSaveEncryptedPinInFile = WriteKeyToStore(v4, 1, 1);
    if ( BioPinOnKeyAndSaveEncryptedPinInFile )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v52,
          v53,
          (unsigned int)"Status",
          BioPinOnKeyAndSaveEncryptedPinInFile,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
          214);
      goto LABEL_53;
    }
    KspStrongKeySuccess(v4);
    if ( v29 )
    {
      if ( (unsigned int)ReadLegacyKeyFile(v3, v4, 0, *(_QWORD *)(v4 + 72), &v95, &v98, &v99) )
      {
        v54 = 0;
        v55 = 0;
      }
      else
      {
        v54 = v98;
        v55 = (unsigned int)v99;
      }
      v56 = *(_QWORD *)(v4 + 64);
      v96 = (void *)v54;
      if ( *(_DWORD *)(v56 + 32) != 196609 || *(_DWORD *)(v4 + 144) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_5b095617bbfd389ce3c01d1846ed1dee_Traceguids);
          *(_DWORD *)(v4 + 44) = 1;
          BioPinOnKeyAndSaveEncryptedPinInFile = 0;
          Feature_Key_Guard_Attestation__private_IsEnabledPreCheck();
          v9 = v94;
          v12 = 1;
          goto LABEL_171;
        }
      }
      else
      {
        v57 = WriteRsaKeyToLegacyStore(v4, v54, v55);
        if ( v57 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_5b095617bbfd389ce3c01d1846ed1dee_Traceguids, v57);
          *(_DWORD *)(v4 + 44) = 1;
          BioPinOnKeyAndSaveEncryptedPinInFile = 0;
          Feature_Key_Guard_Attestation__private_IsEnabledPreCheck();
          v9 = v94;
          v12 = 1;
          goto LABEL_171;
        }
      }
    }
  }
  *(_DWORD *)(v4 + 44) = 1;
  BioPinOnKeyAndSaveEncryptedPinInFile = 0;
  Feature_Key_Guard_Attestation__private_IsEnabledPreCheck();
  v9 = v94;
  v12 = 1;
LABEL_171:
  if ( *(_DWORD *)(v4 + 144) )
  {
    v11 = *(_DWORD *)(v4 + 40);
    if ( (v11 & 0x10) != 0
      && ((*(_DWORD *)(*(_QWORD *)(v4 + 64) + 8LL) - 3) & 0xFFFFFFFD) == 0
      && (v11 & 0xFFFBFF4F) == 0 )
    {
      v58 = &TraceLoggingMetadata;
      if ( (unsigned int)dword_180079068 > 5
        && (qword_180079078 & 0x800000000000LL) != 0
        && (qword_180079080 & 0x800000000000LL) == qword_180079080 )
      {
        v98 = 1;
        v107 = &v98;
        v109 = &v99;
        p_EventDescriptor = (EVENT_DESCRIPTOR *)&v95;
        *(_DWORD *)&EventDescriptor.Level = 5;
        UserData.Ptr = (ULONGLONG)off_180079070;
        v108 = 8;
        v99 = 0x1000000;
        v110 = 8;
        LODWORD(v95) = BioPinOnKeyAndSaveEncryptedPinInFile;
        v112 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0x800000000000LL;
        UserData.Size = *(unsigned __int16 *)off_180079070;
        v104 = byte_180070681;
        UserData.Reserved = 2;
        v105 = 64;
        v106 = 1;
        LODWORD(v97) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_180079090 == TlgAggregateInternalRegisteredProviderEtwCallback )
        {
          LOBYTE(v58) = 0;
          v59 = &v104[v105];
          v60 = v104 + 2;
          do
            v61 = *v60++;
          while ( v61 < 0 );
          while ( *v60++ )
            ;
          if ( v60 >= v59 )
            goto LABEL_194;
          while ( 1 )
          {
            while ( *v60++ )
              ;
            if ( *v60 >= 0 )
              break;
            v64 = *v60 & 0x7F;
            if ( v60[1] >= 0 )
              break;
            v65 = v60[2];
            v60 += 2;
            if ( v65 < 0 )
            {
              while ( v65 == (char)0x80 )
              {
                v65 = *++v60;
                if ( v65 >= 0 )
                  goto LABEL_189;
              }
              break;
            }
LABEL_189:
            if ( v64 == 9 && (unsigned __int8)(v65 - 113) <= 2u )
            {
              v66 = (unsigned __int8)v58;
              LOBYTE(v58) = (_BYTE)v58 + 1;
              *((_BYTE *)&v108 + 16 * v66 + 5) = v65;
              if ( v60 < v59 )
                continue;
            }
            break;
          }
          if ( (_BYTE)v58 )
          {
            UserDataCount = (char)v58;
            LOBYTE(v58) = 5;
            InsertEventEntryInLookUpTable(
              (unsigned int)&dword_180079068,
              (unsigned int)&EventDescriptor,
              (_DWORD)v58,
              (unsigned int)&UserData,
              UserDataCount);
          }
          else
          {
LABEL_194:
            EventWriteTransfer(qword_180079088, &EventDescriptor, 0, 0, 5u, &UserData);
          }
        }
      }
      if ( !RtlDllShutdownInProgress() )
      {
        if ( dword_1800790F0 )
        {
          v11 = 0;
          if ( (qword_180079100 & 0x800000000000LL) != 0 && (qword_180079108 & 0x800000000000LL) == qword_180079108 )
          {
            v108 = 8;
            v107 = &v98;
            v109 = &v99;
            p_EventDescriptor = &EventDescriptor;
            v98 = 0;
            v99 = 1;
            v110 = 8;
            *(_QWORD *)&EventDescriptor.Id = 0;
            v112 = 8;
            if ( dword_180079D38
              || dword_180079D2C != 1
              || dword_180079D34 != 1
              || dword_180079D30
              || (v68 = 1, g_VbsRegistryData) )
            {
              v68 = 0;
            }
            LODWORD(v95) = v68;
            v114 = 4;
            v113 = (EVENT_DESCRIPTOR *)&v95;
            v115 = &v94;
            *(_DWORD *)&v101.Level = 0;
            UserData.Ptr = (ULONGLONG)off_1800790F8;
            v94 = 2048;
            v116 = 8;
            *(_DWORD *)&v101.Id = 184549376;
            v101.Keyword = 0x800000000000LL;
            UserData.Size = *(unsigned __int16 *)off_1800790F8;
            v104 = (char *)&dword_1800705EC;
            UserData.Reserved = 2;
            v105 = 137;
            v106 = 1;
            LODWORD(v97) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_180079118 == TlgAggregateInternalRegisteredProviderEtwCallback )
            {
              LOBYTE(v67) = 0;
              v69 = &v104[v105];
              v70 = v104 + 2;
              do
                v71 = *v70++;
              while ( v71 < 0 );
              while ( *v70++ )
                ;
              if ( v70 >= v69 )
                goto LABEL_221;
              while ( 1 )
              {
                while ( *v70++ )
                  ;
                if ( *v70 >= 0 )
                  break;
                v74 = *v70 & 0x7F;
                if ( v70[1] >= 0 )
                  break;
                v75 = v70[2];
                v70 += 2;
                if ( v75 < 0 )
                {
                  while ( v75 == (char)0x80 )
                  {
                    v75 = *++v70;
                    if ( v75 >= 0 )
                      goto LABEL_216;
                  }
                  break;
                }
LABEL_216:
                if ( v74 == 9 && (unsigned __int8)(v75 - 113) <= 2u )
                {
                  v76 = (unsigned __int8)v67;
                  LOBYTE(v67) = v67 + 1;
                  *((_BYTE *)&v108 + 16 * v76 + 5) = v75;
                  if ( v70 < v69 )
                    continue;
                }
                break;
              }
              if ( (_BYTE)v67 )
              {
                UserDataCounta = v67;
                LOBYTE(v67) = 7;
                InsertEventEntryInLookUpTable(
                  (unsigned int)&dword_1800790F0,
                  (unsigned int)&v101,
                  v67,
                  (unsigned int)&UserData,
                  UserDataCounta);
              }
              else
              {
LABEL_221:
                EventWriteTransfer(RegHandle, &v101, 0, 0, 7u, &UserData);
              }
            }
          }
        }
      }
      if ( v9 >= 0 && BioPinOnKeyAndSaveEncryptedPinInFile >= 0 )
      {
        v98 = 0;
        v77 = ((__int64 (__fastcall *)(_QWORD, _QWORD))EndPerfMeasure)((LARGE_INTEGER)PerformanceCount.QuadPart, &v98);
        if ( v77 >= 0 )
        {
          if ( dword_180079068 )
          {
            v11 = 0;
            if ( (qword_180079078 & 0x400000000000LL) != 0 && (qword_180079080 & 0x400000000000LL) == qword_180079080 )
            {
              v97 = 1;
              v107 = &v97;
              v99 = v98;
              *(_QWORD *)&EventDescriptor.Id = v98;
              v113 = &EventDescriptor;
              v115 = &v94;
              *(_DWORD *)&v101.Level = 0;
              UserData.Ptr = (ULONGLONG)off_180079070;
              v109 = &v98;
              v108 = 8;
              v110 = 8;
              p_EventDescriptor = (EVENT_DESCRIPTOR *)&v99;
              v112 = 8;
              v114 = 8;
              v94 = 50331648;
              v116 = 8;
              *(_DWORD *)&v101.Id = 184549376;
              v101.Keyword = 0x400000000000LL;
              UserData.Size = *(unsigned __int16 *)off_180079070;
              v104 = byte_1800703A3;
              UserData.Reserved = 2;
              v105 = 131;
              v106 = 1;
              LODWORD(v95) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
              if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_180079090 == TlgAggregateInternalRegisteredProviderEtwCallback )
              {
                LOBYTE(v78) = 0;
                v79 = &v104[v105];
                v80 = v104 + 2;
                do
                  v81 = *v80++;
                while ( v81 < 0 );
                while ( *v80++ )
                  ;
                if ( v80 >= v79 )
                  goto LABEL_247;
                while ( 1 )
                {
                  while ( *v80++ )
                    ;
                  if ( *v80 >= 0 )
                    break;
                  v84 = *v80 & 0x7F;
                  if ( v80[1] >= 0 )
                    break;
                  v85 = v80[2];
                  v80 += 2;
                  if ( v85 < 0 )
                  {
                    while ( v85 == (char)0x80 )
                    {
                      v85 = *++v80;
                      if ( v85 >= 0 )
                        goto LABEL_242;
                    }
                    break;
                  }
LABEL_242:
                  if ( v84 == 9 && (unsigned __int8)(v85 - 113) <= 2u )
                  {
                    v86 = (unsigned __int8)v78;
                    LOBYTE(v78) = v78 + 1;
                    *((_BYTE *)&v108 + 16 * v86 + 5) = v85;
                    if ( v80 < v79 )
                      continue;
                  }
                  break;
                }
                if ( (_BYTE)v78 )
                {
                  UserDataCountb = v78;
                  LOBYTE(v78) = 7;
                  InsertEventEntryInLookUpTable(
                    (unsigned int)&dword_180079068,
                    (unsigned int)&v101,
                    v78,
                    (unsigned int)&UserData,
                    UserDataCountb);
                }
                else
                {
LABEL_247:
                  EventWriteTransfer(qword_180079088, &v101, 0, 0, 7u, &UserData);
                }
              }
            }
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            (unsigned int)&WPP_5b095617bbfd389ce3c01d1846ed1dee_Traceguids,
            (unsigned int)"SPCryptFinalizeKey",
            v77);
        }
      }
    }
  }
  v6 = v96;
LABEL_249:
  if ( !BioPinOnKeyAndSaveEncryptedPinInFile )
  {
    KspCryptAuditCryptOperation(1, v11, v4, 2481, 0);
    goto LABEL_263;
  }
  if ( BioPinOnKeyAndSaveEncryptedPinInFile != -2146893778 )
    goto LABEL_257;
LABEL_258:
  if ( v4 )
  {
    v87 = *(_QWORD *)(v4 + 416);
    if ( v87 )
    {
      if ( (*(_BYTE *)(v87 + 4) & 4) != 0 )
      {
        v88 = *(_QWORD *)(v4 + 16);
        if ( v88 )
          DeleteEncryptedPinFile(v88, *(unsigned int *)(v4 + 528), *(_QWORD *)(v4 + 80));
      }
    }
  }
LABEL_263:
  if ( v12 )
    RtlReleaseResource((PRTL_RESOURCE)(v4 + 304));
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( v3 )
    RtlReleaseResource((PRTL_RESOURCE)(v3 + 64));
  return (unsigned int)BioPinOnKeyAndSaveEncryptedPinInFile;
}

```

## disassembly

```asm
0x18002a0c0  mov     r11, rsp
0x18002a0c3  push    rbp
0x18002a0c4  push    r13
0x18002a0c6  push    r14
0x18002a0c8  lea     rbp, [r11-68h]
0x18002a0cc  sub     rsp, 150h
0x18002a0d3  mov     rax, cs:__security_cookie
0x18002a0da  xor     rax, rsp
0x18002a0dd  mov     [rbp+60h+var_40], rax
0x18002a0e1  mov     [r11+18h], rbx
0x18002a0e5  mov     r13, rcx
0x18002a0e8  mov     [r11-20h], rsi
0x18002a0ec  mov     rbx, rdx
0x18002a0ef  mov     [r11-28h], rdi
0x18002a0f3  mov     esi, r8d
0x18002a0f6  xor     edi, edi
0x18002a0f8  mov     [r11-30h], r12
0x18002a0fc  mov     dword ptr [rsp+160h+var_110], edi
0x18002a100  mov     r12d, edi
0x18002a103  mov     [rsp+160h+var_F8], rdi
0x18002a108  mov     [rsp+160h+var_E8], rdi
0x18002a10d  mov     dword ptr [rbp+60h+var_E0], edi
0x18002a110  mov     dword ptr [rsp+160h+var_100], edi
0x18002a114  mov     qword ptr [rbp+60h+PerformanceCount], rdi
0x18002a118  test    rcx, rcx
0x18002a11b  jz      loc_18002B32E
0x18002a121  cmp     dword ptr [rcx], 0A0h
0x18002a127  jb      loc_18002B32E
0x18002a12d  cmp     dword ptr [rcx+4], 4B535050h
0x18002a134  jnz     loc_18002B32E
0x18002a13a  add     rcx, 40h ; '@'; Resource
0x18002a13e  mov     [r11-38h], r15
0x18002a142  mov     dl, 1; Wait
0x18002a144  call    cs:__imp_RtlAcquireResourceShared
0x18002a14b  nop     dword ptr [rax+rax+00h]
0x18002a150  test    rbx, rbx
0x18002a153  jz      loc_18002ABDA
0x18002a159  cmp     dword ptr [rbx], 248h
0x18002a15f  jb      loc_18002ABDA
0x18002a165  cmp     dword ptr [rbx+4], 4B53504Bh
0x18002a16c  jnz     loc_18002ABDA
0x18002a172  cmp     dword ptr [rbx+2Ch], 1
0x18002a176  mov     r12d, 0C0000001h
0x18002a17c  jnz     short loc_18002A1D5
0x18002a17e  mov     r14d, 80090026h
0x18002a184  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a18b  lea     r15, WPP_GLOBAL_Control
0x18002a192  cmp     rcx, r15
0x18002a195  jz      short loc_18002A1C9
0x18002a197  test    byte ptr [rcx+1Ch], 1
0x18002a19b  jz      short loc_18002A1C9
0x18002a19d  mov     dword ptr [rsp+30h], 0A46h
0x18002a1a5  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002a1ac  mov     [rsp+160h+UserData], rax
0x18002a1b1  mov     [rsp+160h+UserDataCount], 80090026h
0x18002a1b9  mov     rcx, [rcx+10h]
0x18002a1bd  lea     r9, aStatus; "Status"
0x18002a1c4  call    WPP_SF_sDsd
0x18002a1c9  call    Feature_Key_Guard_Attestation__private_IsEnabledPreCheck
0x18002a1ce  mov     esi, edi
0x18002a1d0  jmp     loc_18002AC3E
0x18002a1d5  test    esi, 0FFFF7DB7h
0x18002a1db  jz      short loc_18002A21A
0x18002a1dd  mov     r14d, 80090009h
0x18002a1e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a1ea  lea     r15, WPP_GLOBAL_Control
0x18002a1f1  cmp     rcx, r15
0x18002a1f4  jz      short loc_18002A1C9
0x18002a1f6  test    byte ptr [rcx+1Ch], 1
0x18002a1fa  jz      short loc_18002A1C9
0x18002a1fc  mov     dword ptr [rsp+30h], 0A50h
0x18002a204  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002a20b  mov     [rsp+160h+UserData], rax
0x18002a210  mov     [rsp+160h+UserDataCount], 80090009h
0x18002a218  jmp     short loc_18002A1B9
0x18002a21a  mov     edi, esi
0x18002a21c  mov     r12d, esi
0x18002a21f  and     edi, 8
0x18002a222  and     r12d, 200h
0x18002a229  mov     r14d, esi
0x18002a22c  and     r14d, 8000h
0x18002a233  jz      loc_18002A300
0x18002a239  test    r12d, r12d
0x18002a23c  jz      short loc_18002A297
0x18002a23e  mov     r14d, 80090009h
0x18002a244  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a24b  lea     r15, WPP_GLOBAL_Control
0x18002a252  cmp     rcx, r15
0x18002a255  jz      short loc_18002A289
0x18002a257  test    byte ptr [rcx+1Ch], 1
0x18002a25b  jz      short loc_18002A289
0x18002a25d  mov     rcx, [rcx+10h]
0x18002a261  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002a268  mov     dword ptr [rsp+30h], 0A61h
0x18002a270  lea     r9, aStatus; "Status"
0x18002a277  mov     [rsp+160h+UserData], rax
0x18002a27c  mov     [rsp+160h+UserDataCount], 80090009h
0x18002a284  call    WPP_SF_sDsd
0x18002a289  call    Feature_Key_Guard_Attestation__private_IsEnabledPreCheck
0x18002a28e  mov     esi, dword ptr [rsp+160h+var_110]
0x18002a292  jmp     loc_18002AC38
0x18002a297  cmp     dword ptr [rbx+24h], 0
0x18002a29b  jnz     short loc_18002A2A7
0x18002a29d  cmp     qword ptr [rbx+0D0h], 0
0x18002a2a5  jz      short loc_18002A300
0x18002a2a7  mov     r14d, 80090009h
0x18002a2ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a2b4  lea     r15, WPP_GLOBAL_Control
0x18002a2bb  cmp     rcx, r15
0x18002a2be  jz      short loc_18002A2F2
0x18002a2c0  test    byte ptr [rcx+1Ch], 1
0x18002a2c4  jz      short loc_18002A2F2
0x18002a2c6  mov     rcx, [rcx+10h]
0x18002a2ca  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002a2d1  mov     dword ptr [rsp+30h], 0A72h
0x18002a2d9  lea     r9, aStatus; "Status"
0x18002a2e0  mov     [rsp+160h+UserData], rax
0x18002a2e5  mov     [rsp+160h+UserDataCount], 80090009h
0x18002a2ed  call    WPP_SF_sDsd
0x18002a2f2  call    Feature_Key_Guard_Attestation__private_IsEnabledPreCheck
0x18002a2f7  mov     esi, dword ptr [rsp+160h+var_110]
0x18002a2fb  jmp     loc_18002AC38
0x18002a300  lea     rcx, [rbp+60h+PerformanceCount]; lpPerformanceCount
0x18002a304  call    cs:__imp_QueryPerformanceCounter
0x18002a30b  nop     dword ptr [rax+rax+00h]
0x18002a310  lea     r15, WPP_GLOBAL_Control
0x18002a317  test    eax, eax
0x18002a319  jnz     short loc_18002A373
0x18002a31b  call    cs:__imp_GetLastError
0x18002a322  nop     dword ptr [rax+rax+00h]
0x18002a327  mov     dword ptr [rsp+160h+var_108], eax
0x18002a32b  test    eax, eax
0x18002a32d  jle     short loc_18002A33D
0x18002a32f  movzx   eax, ax
0x18002a332  or      eax, 0C0070000h
0x18002a337  mov     dword ptr [rsp+160h+var_108], eax
0x18002a33b  test    eax, eax
0x18002a33d  jns     short loc_18002A37B
0x18002a33f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a346  cmp     rcx, r15
0x18002a349  jz      short loc_18002A37B
0x18002a34b  test    byte ptr [rcx+1Ch], 1
0x18002a34f  jz      short loc_18002A37B
0x18002a351  mov     rcx, [rcx+10h]
0x18002a355  lea     r9, aSpcryptfinaliz; "SPCryptFinalizeKey"
0x18002a35c  mov     edx, 11h
0x18002a361  mov     [rsp+160h+UserDataCount], eax
0x18002a365  lea     r8, WPP_5b095617bbfd389ce3c01d1846ed1dee_Traceguids
0x18002a36c  call    WPP_SF_sD
0x18002a371  jmp     short loc_18002A37B
0x18002a373  mov     dword ptr [rsp+160h+var_108], 0
0x18002a37b  test    r14d, r14d
0x18002a37e  jz      short loc_18002A387
0x18002a380  or      dword ptr [rbx+234h], 1
0x18002a387  mov     rax, [rbx+1A0h]
0x18002a38e  test    rax, rax
0x18002a391  jz      short loc_18002A3AF
0x18002a393  test    byte ptr [rax+4], 1
0x18002a397  jz      short loc_18002A3AF
0x18002a399  mov     eax, cs:g_dwStrongKeyForcePassword
0x18002a39f  cmp     eax, 2
0x18002a3a2  jnz     short loc_18002A3AF
0x18002a3a4  mov     rax, [rbx+1A0h]
0x18002a3ab  or      dword ptr [rax+4], 2
0x18002a3af  mov     rax, [rbx+1A0h]
0x18002a3b6  test    rax, rax
0x18002a3b9  jz      short loc_18002A3C8
0x18002a3bb  test    byte ptr [rax+4], 2
0x18002a3bf  jz      short loc_18002A3C8
0x18002a3c1  or      dword ptr [rbx+1ACh], 1
0x18002a3c8  cmp     dword ptr [rbx+238h], 0
0x18002a3cf  jnz     loc_18002A5AC
0x18002a3d5  test    rax, rax
0x18002a3d8  jz      loc_18002A5AC
0x18002a3de  test    byte ptr [rax+4], 4
0x18002a3e2  jnz     loc_18002A4A3
0x18002a3e8  mov     rcx, rbx
0x18002a3eb  call    KspCheckStrongKey
0x18002a3f0  mov     r14d, eax
0x18002a3f3  test    eax, eax
0x18002a3f5  jns     loc_18002A5AC
0x18002a3fb  cmp     eax, 8009002Eh
0x18002a400  jz      short loc_18002A450
0x18002a402  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a409  cmp     rcx, r15
0x18002a40c  jz      short loc_18002A43D
0x18002a40e  test    byte ptr [rcx+1Ch], 1
0x18002a412  jz      short loc_18002A43D
0x18002a414  mov     dword ptr [rsp+30h], 0AB4h
0x18002a41c  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002a423  mov     [rsp+160h+UserData], rax
0x18002a428  mov     [rsp+160h+UserDataCount], r14d
0x18002a42d  mov     rcx, [rcx+10h]
0x18002a431  lea     r9, aStatus; "Status"
0x18002a438  call    WPP_SF_sDsd
0x18002a43d  call    Feature_Key_Guard_Attestation__private_IsEnabledPreCheck
0x18002a442  mov     r12d, dword ptr [rsp+160h+var_108]
0x18002a447  mov     esi, dword ptr [rsp+160h+var_110]
0x18002a44b  jmp     loc_18002AC3E
0x18002a450  test    sil, 40h
0x18002a454  jz      short loc_18002A46F
0x18002a456  mov     r14d, 80090022h
0x18002a45c  call    Feature_Key_Guard_Attestation__private_IsEnabledPreCheck
0x18002a461  mov     r12d, dword ptr [rsp+160h+var_108]
0x18002a466  mov     esi, dword ptr [rsp+160h+var_110]
0x18002a46a  jmp     loc_18002AC3E
0x18002a46f  xor     edx, edx
0x18002a471  mov     rcx, rbx
0x18002a474  call    KspCallCredUI
0x18002a479  mov     r14d, eax
0x18002a47c  test    eax, eax
0x18002a47e  jz      loc_18002A5AC
0x18002a484  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a48b  cmp     rcx, r15
0x18002a48e  jz      short loc_18002A43D
0x18002a490  test    byte ptr [rcx+1Ch], 1
0x18002a494  jz      short loc_18002A43D
0x18002a496  mov     dword ptr [rsp+30h], 0AC3h
0x18002a49e  jmp     loc_18002A41C
0x18002a4a3  cmp     qword ptr [rbx+38h], 0
0x18002a4a8  jz      loc_18002A695
0x18002a4ae  mov     rcx, gs:60h
0x18002a4b7  xor     edx, edx; Flags
0x18002a4b9  mov     r8d, 0DEh; Size
0x18002a4bf  mov     rcx, [rcx+30h]; HeapHandle
0x18002a4c3  call    cs:__imp_RtlAllocateHeap
0x18002a4ca  nop     dword ptr [rax+rax+00h]
0x18002a4cf  mov     [rbx+10h], rax
0x18002a4d3  test    rax, rax
0x18002a4d6  jnz     short loc_18002A519
0x18002a4d8  mov     r14d, 8009000Eh
0x18002a4de  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a4e5  cmp     rcx, r15
0x18002a4e8  jz      loc_18002A6D9
0x18002a4ee  test    byte ptr [rcx+1Ch], 1
0x18002a4f2  jz      loc_18002A6D9
0x18002a4f8  mov     dword ptr [rsp+30h], 1C0h
0x18002a500  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002a507  mov     [rsp+160h+UserData], rax
0x18002a50c  mov     [rsp+160h+UserDataCount], 8009000Eh
0x18002a514  jmp     loc_18002A6C9
0x18002a519  mov     edx, [rbx+210h]
0x18002a51f  mov     r8, rax
0x18002a522  mov     rcx, [rbx+8]; pszSrc
0x18002a526  call    AddMachineGuidAndAppContainerSidHashToContainerNameW
0x18002a52b  mov     r14d, eax
0x18002a52e  test    eax, eax
0x18002a530  jz      short loc_18002A599
0x18002a532  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a539  cmp     rcx, r15
0x18002a53c  jz      short loc_18002A56D
0x18002a53e  test    byte ptr [rcx+1Ch], 1
0x18002a542  jz      short loc_18002A56D
0x18002a544  mov     rcx, [rcx+10h]
0x18002a548  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002a54f  mov     dword ptr [rsp+30h], 1CCh
0x18002a557  lea     r9, aStatus; "Status"
0x18002a55e  mov     [rsp+160h+UserData], rax
0x18002a563  mov     [rsp+160h+UserDataCount], r14d
0x18002a568  call    WPP_SF_sDsd
0x18002a56d  mov     rcx, gs:60h
0x18002a576  xor     edx, edx; Flags
0x18002a578  mov     r8, [rbx+10h]; P
0x18002a57c  mov     rcx, [rcx+30h]; HeapHandle
0x18002a580  call    cs:__imp_RtlFreeHeap
0x18002a587  nop     dword ptr [rax+rax+00h]
0x18002a58c  mov     qword ptr [rbx+10h], 0
0x18002a594  jmp     loc_18002A6D9
0x18002a599  mov     rcx, rbx
0x18002a59c  call    CreateBioPinOnKeyAndSaveEncryptedPinInFile
0x18002a5a1  mov     r14d, eax
0x18002a5a4  test    eax, eax
0x18002a5a6  jnz     loc_18002A6D9
0x18002a5ac  xor     esi, esi
0x18002a5ae  lea     rcx, [rbx+130h]; Resource
0x18002a5b5  mov     dl, 1; Wait
0x18002a5b7  mov     r15d, esi
0x18002a5ba  call    cs:__imp_RtlAcquireResourceExclusive
0x18002a5c1  nop     dword ptr [rax+rax+00h]
0x18002a5c6  mov     dword ptr [rsp+160h+var_110], 1
0x18002a5ce  cmp     [rbx+90h], esi
0x18002a5d4  jz      loc_18002A7D7
0x18002a5da  mov     rdx, [rbx+0C8h]
0x18002a5e1  mov     dword ptr [rbp+60h+EventDescriptor.Id], esi
0x18002a5e4  mov     dword ptr [rsp+160h+var_F0], 4
0x18002a5ec  test    rdx, rdx
0x18002a5ef  jz      short loc_18002A630
0x18002a5f1  lea     r8, aIsolatedKeyEnv; "ISOLATED_KEY_ENVELOPE"
0x18002a5f8  mov     ecx, esi
0x18002a5fa  nop     word ptr [rax+rax+00h]
0x18002a600  movzx   eax, word ptr [rdx+rcx*2]
0x18002a604  cmp     ax, [r8+rcx*2]
0x18002a609  jnz     loc_18002A700
0x18002a60f  movzx   eax, word ptr [rdx+rcx*2+2]
0x18002a614  cmp     ax, [r8+rcx*2+2]
0x18002a61a  jnz     loc_18002A700
0x18002a620  add     rcx, 2
0x18002a624  cmp     rcx, 16h
0x18002a628  jnz     short loc_18002A600
0x18002a62a  mov     r15d, 1
  ... truncated ...
```
