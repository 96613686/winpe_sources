# MRxSmb2Create

- ea: `0x1400236b0`
- end: `0x14002474f`
- name: `MRxSmb2Create`
- size: `4255`
- prototype: `__int64 __fastcall(char *pContext)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140004940`
- `0x14000ab50`
- `0x14000ad90`
- `0x1400122d0`
- `0x140012d80`
- `0x140014db0`
- `0x140019fe0`
- `0x14001b0c0`
- `0x140022490`
- `0x1400236b0`
- `0x140024760`
- `0x1400277c0`
- `0x1400286c0`
- `0x140029084`
- `0x140029840`
- `0x140029c14`
- `0x14002a3f8`
- `0x140037120`
- `0x140055eb0`
- `0x140056930`

## import_xrefs

- `ntoskrnl!SeTokenGetRedirectionTrustPolicy` at `0x140023bfe`
- `ntoskrnl!SeTokenGetRedirectionTrustPolicy` at `0x140023c21`
- `ntoskrnl!SeTokenGetRedirectionTrustPolicy` at `0x140023bfe`
- `ntoskrnl!SeTokenGetRedirectionTrustPolicy` at `0x140023c21`
- `ntoskrnl!ExAllocatePool2` at `0x140023955`
- `ntoskrnl!ExAllocatePool2` at `0x140023955`
- `ntoskrnl!ExUuidCreate` at `0x1400239aa`
- `ntoskrnl!ExUuidCreate` at `0x1400239aa`
- `ntoskrnl!KeGetCurrentIrql` at `0x140023727`
- `ntoskrnl!KeGetCurrentIrql` at `0x140023727`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140023efe`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140023f39`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140023efe`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140023f39`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140023c6e`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140023c6e`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140023cbb`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140023cbb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002410e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002410e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140024050`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140024050`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140023cd1`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140023cd1`
- `rdbss!RxNameCacheCheckEntry` at `0x140024084`
- `rdbss!RxNameCacheCheckEntry` at `0x140024084`
- `rdbss!RxNameCacheExpireEntry` at `0x1400240b4`
- `rdbss!RxNameCacheExpireEntry` at `0x1400240b4`
- `rdbss!RxNameCacheActivateEntry` at `0x1400240a6`
- `rdbss!RxNameCacheActivateEntry` at `0x1400240a6`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14002406a`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14002406a`
- `rdbss!RxOrphanSrvOpen` at `0x140024308`
- `rdbss!RxOrphanSrvOpen` at `0x140024308`
- `rdbss!RxEnableTurboIo` at `0x140024602`
- `rdbss!RxEnableTurboIo` at `0x140024602`
- `rdbss!RxOpenFileObjectForTurboIo` at `0x1400245ea`
- `rdbss!RxOpenFileObjectForTurboIo` at `0x1400245ea`
- `rdbss!RxFcbGetOutstandingBufferingChangeEvent` at `0x1400244ca`
- `rdbss!RxFcbGetOutstandingBufferingChangeEvent` at `0x1400244ca`
- `rdbss!RxProcessFcbChangeBufferingStateRequest` at `0x1400244d6`
- `rdbss!RxCreateNetFobx` at `0x140023f64`
- `rdbss!RxCreateNetFobx` at `0x140023f64`
- `ksecdd!BCryptGenRandom` at `0x140023855`
- `ksecdd!BCryptGenRandom` at `0x1400238f0`
- `ksecdd!BCryptGenRandom` at `0x1400243a1`
- `ksecdd!BCryptGenRandom` at `0x140023855`
- `ksecdd!BCryptGenRandom` at `0x1400238f0`
- `ksecdd!BCryptGenRandom` at `0x1400243a1`
- `mrxsmb!MRxSmbGetCompressionConfigBlock` at `0x14002450e`
- `mrxsmb!MRxSmbGetCompressionConfigBlock` at `0x140024520`
- `mrxsmb!MRxSmbGetCompressionConfigBlock` at `0x14002450e`
- `mrxsmb!MRxSmbGetCompressionConfigBlock` at `0x140024520`
- `mrxsmb!MRxSmbGetAuthenticationParameters` at `0x140023e19`
- `mrxsmb!MRxSmbGetAuthenticationParameters` at `0x140023e19`
- `mrxsmb!MRxSmbGetCompressionParameters` at `0x140023dbb`
- `mrxsmb!MRxSmbGetCompressionParameters` at `0x140023dbb`
- `mrxsmb!MRxSmbValidateIncomingPortsAgainstEffective` at `0x140023d87`
- `mrxsmb!MRxSmbValidateIncomingPortsAgainstEffective` at `0x140023d87`
- `mrxsmb!MRxSmbValidateAndGetTransportParametersNew` at `0x140023d13`
- `mrxsmb!MRxSmbValidateAndGetTransportParametersNew` at `0x140023d13`
- `mrxsmb!SmbCeIncrementNtlmOpenCounts` at `0x140023a52`
- `mrxsmb!SmbCeIncrementNtlmOpenCounts` at `0x140023a52`
- `mrxsmb!MRxSmbIsStreamFile` at `0x140024008`
- `mrxsmb!MRxSmbIsStreamFile` at `0x140024008`
- `mrxsmb!SmbCeDecrementNtlmOpenCounts` at `0x1400246d4`
- `mrxsmb!SmbCeDecrementNtlmOpenCounts` at `0x1400246d4`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x1400244b2`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x1400244f6`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x1400244b2`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x1400244f6`
- `mrxsmb!SmbCeInitiateExchange` at `0x14002444b`
- `mrxsmb!SmbCeInitiateExchange` at `0x14002444b`
- `mrxsmb!SmbCeInitializeExchange` at `0x1400243fc`
- `mrxsmb!SmbCeInitializeExchange` at `0x1400243fc`

## pseudocode

```c
__int64 __fastcall MRxSmb2Create(char *pContext)
{
  __int64 v1; // rdi
  __int64 v3; // rsi
  __int64 v4; // r12
  __int64 v5; // rbx
  int v6; // r13d
  __int64 v7; // rdx
  __int64 v8; // r9
  __int64 v9; // r15
  PDEVICE_OBJECT v10; // rcx
  int Parameter; // edi
  char v12; // si
  _WORD *v13; // r12
  __int64 FcbExtension; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 Pool2; // rax
  __int64 v20; // rdi
  __m128i si128; // xmm0
  unsigned int v22; // edx
  __int64 v23; // rbx
  _DWORD *v24; // rcx
  __int64 v25; // r8
  int v26; // eax
  int v27; // eax
  int v28; // eax
  __int64 v29; // rbx
  __int64 v30; // rcx
  int v31; // edx
  __int64 v32; // rbx
  __int64 v33; // rdx
  __int64 v34; // rdi
  KIRQL v35; // bl
  int v36; // eax
  __int64 v37; // rbx
  PMRX_FOBX NetFobx; // rax
  __int64 v39; // r12
  __int64 v40; // rsi
  __int64 v41; // rax
  __int64 v42; // rcx
  struct _NAME_CACHE_CONTROL_ *v43; // rsi
  __int64 v44; // rbx
  char v45; // r12
  __int64 v46; // r15
  ULONG v47; // r13d
  __int64 v48; // rdx
  __int64 v49; // rax
  struct _NAME_CACHE *Entry; // rax
  int v51; // ecx
  struct _NAME_CACHE *v52; // rbx
  char v53; // r8
  unsigned __int8 v54; // dl
  __int64 v55; // rcx
  bool v56; // sf
  char v57; // dl
  unsigned int v58; // eax
  char v59; // r8
  int v60; // r13d
  __int64 v61; // rcx
  _QWORD **v62; // rsi
  _QWORD *v63; // r15
  _QWORD *v64; // rax
  _QWORD *v65; // rdi
  _QWORD *v66; // rax
  _QWORD *v67; // rbx
  _QWORD *v68; // rax
  _QWORD *v69; // rcx
  __int64 v70; // r15
  __int64 v71; // r13
  __int64 v72; // rbx
  int v73; // ecx
  __int64 v74; // r9
  void (__stdcall *v75)(PFCB); // r8
  __int64 v76; // rdx
  __int64 v77; // rax
  int v78; // eax
  int v79; // eax
  __int64 v80; // r15
  bool v81; // bl
  int EcpContext; // [rsp+28h] [rbp-91h]
  char v84; // [rsp+40h] [rbp-79h] BYREF
  char v85[7]; // [rsp+41h] [rbp-78h] BYREF
  __int64 v86; // [rsp+48h] [rbp-71h]
  char v87; // [rsp+50h] [rbp-69h] BYREF
  char v88; // [rsp+51h] [rbp-68h] BYREF
  char v89; // [rsp+52h] [rbp-67h] BYREF
  char v90; // [rsp+53h] [rbp-66h]
  char v91; // [rsp+54h] [rbp-65h]
  char v92; // [rsp+55h] [rbp-64h]
  char v93; // [rsp+56h] [rbp-63h]
  __int64 v94; // [rsp+58h] [rbp-61h] BYREF
  __int64 v95; // [rsp+60h] [rbp-59h]
  int v96; // [rsp+68h] [rbp-51h]
  __int64 v97; // [rsp+70h] [rbp-49h]
  __int64 v98; // [rsp+78h] [rbp-41h]
  PVOID v99; // [rsp+80h] [rbp-39h] BYREF
  __int64 v100; // [rsp+88h] [rbp-31h]
  __int64 v101; // [rsp+90h] [rbp-29h]
  __int64 v102; // [rsp+98h] [rbp-21h] BYREF
  int v103; // [rsp+A0h] [rbp-19h]
  __int64 v104; // [rsp+A8h] [rbp-11h]
  UCHAR pbBuffer[16]; // [rsp+B0h] [rbp-9h] BYREF

  v1 = *((_QWORD *)pContext + 7);
  v3 = *((_QWORD *)pContext + 9);
  v4 = *((_QWORD *)pContext + 81);
  v97 = v1;
  v101 = v4;
  v5 = *(_QWORD *)(*(_QWORD *)(v3 + 40) + 40LL);
  v104 = v5;
  v86 = *(_QWORD *)(v5 + 416);
  v98 = *(_QWORD *)(v86 + 384);
  v94 = 0;
  v6 = *(_DWORD *)(v1 + 156);
  v103 = v6;
  v96 = 0;
  KeGetCurrentIrql();
  v9 = *(_QWORD *)(v5 + 24);
  v10 = 0;
  v89 = 0;
  v99 = 0;
  v85[0] = 0;
  v87 = 0;
  v84 = 0;
  v88 = 0;
  if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 2) != 0 )
  {
    LOBYTE(v8) = -76;
    McTemplateK0uq_EtwWriteTransfer(0, v7, pContext + 412, v8, 0);
  }
  if ( (*(_DWORD *)(v1 + 156) & 4) != 0 )
  {
    Parameter = -1073741822;
    v12 = -53;
    goto LABEL_215;
  }
  if ( *(_BYTE *)(v4 + 77) == 5 )
  {
    Parameter = -1073741822;
    v12 = -46;
    goto LABEL_215;
  }
  v13 = (_WORD *)(v1 + 360);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qZ(
      WPP_GLOBAL_Control->AttachedDevice,
      34,
      (unsigned int)WPP_584f9b0e749e3be8080bab44300b7711_Traceguids,
      (_DWORD)pContext,
      v1 + 360);
  }
  _InterlockedIncrement64((volatile signed __int64 *)(v5 + 488));
  v100 = *(_QWORD *)(v1 + 136);
  if ( !v100 )
  {
    FcbExtension = Smb2AllocateFcbExtension(v1);
    v100 = FcbExtension;
    if ( !FcbExtension )
    {
      Parameter = -1073741670;
      v12 = -26;
      goto LABEL_215;
    }
    if ( (pContext[746] & 0x10) != 0 )
      *(_DWORD *)(FcbExtension + 8) |= 1u;
    if ( (*(_DWORD *)(v98 + 716) & 0x20) != 0 )
    {
      *(_OWORD *)pbBuffer = 0;
      Parameter = BCryptGenRandom(0, pbBuffer, 0x10u, 2u);
      if ( Parameter < 0 )
      {
        v12 = -3;
        goto LABEL_215;
      }
      v15 = *(_QWORD *)&pbBuffer[8];
      v1 = v97;
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v97 + 168), *(signed __int64 *)pbBuffer, -1) == -1 )
        *(_QWORD *)(v97 + 176) = v15;
    }
  }
  v16 = *(_QWORD *)(v1 + 288);
  if ( v16 && !*(_QWORD *)(v16 + 136) )
  {
    if ( !Smb2AllocateFcbExtension(v16) )
    {
      Parameter = -1073741670;
      v12 = 22;
      goto LABEL_215;
    }
    if ( (*(_DWORD *)(v98 + 716) & 0x20) != 0 )
    {
      *(_OWORD *)pbBuffer = 0;
      Parameter = BCryptGenRandom(0, pbBuffer, 0x10u, 2u);
      if ( Parameter < 0 )
      {
        v12 = 37;
        goto LABEL_215;
      }
      v17 = *(_QWORD *)&pbBuffer[8];
      v18 = *(_QWORD *)(v97 + 288);
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v18 + 168), *(signed __int64 *)pbBuffer, -1) == -1 )
        *(_QWORD *)(v18 + 176) = v17;
    }
  }
  v95 = *(_QWORD *)(v3 + 48);
  if ( v95 )
  {
    v23 = v86;
    v91 = 0;
  }
  else
  {
    Pool2 = ExAllocatePool2(256, 384, 1834182982);
    v95 = Pool2;
    v20 = Pool2;
    if ( !Pool2 )
    {
      Parameter = -1073741670;
      v12 = 56;
LABEL_215:
      if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 1) != 0 )
        McTemplateK0qqq_EtwWriteTransfer(
          (_DWORD)v10,
          (unsigned int)CreateFileError,
          (_DWORD)pContext + 412,
          Parameter,
          v12,
          v96);
      goto LABEL_217;
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    *(_WORD *)Pool2 = -7152;
    *(_DWORD *)(Pool2 + 4) = 1;
    *(_QWORD *)(Pool2 + 16) = 0;
    *(__m128i *)(Pool2 + 28) = si128;
    *(_QWORD *)(Pool2 + 64) = Pool2 + 56;
    *(_QWORD *)(Pool2 + 56) = Pool2 + 56;
    *(_QWORD *)(Pool2 + 176) = -1;
    ExUuidCreate((UUID *)(Pool2 + 264));
    *(_QWORD *)(v20 + 256) = 600000000;
    *(_QWORD *)(v20 + 324) = 0;
    *(_QWORD *)(v20 + 344) = v20 + 336;
    *(_QWORD *)(v20 + 336) = v20 + 336;
    *(_QWORD *)(v3 + 48) = v20;
    v22 = (unsigned __int8)pContext[787];
    *(_BYTE *)(v20 + 328) = v22;
    if ( (v22 & 3) != 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qddd(
        WPP_GLOBAL_Control->AttachedDevice,
        (v22 >> 2) & 1,
        v22 & 1,
        v20,
        v22 & 1,
        (v22 >> 1) & 1,
        (v22 >> 2) & 1);
    }
    v23 = v86;
    SmbCeIncrementNtlmOpenCounts(v86, v20 + 328, v20 + 329);
    v91 = 1;
  }
  Parameter = Smb2SetupAlternateSPNForSession(v23, *((USHORT **)pContext + 85));
  if ( Parameter < 0 )
  {
    v12 = 91;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        36,
        WPP_584f9b0e749e3be8080bab44300b7711_Traceguids,
        pContext,
        Parameter);
    }
    goto LABEL_213;
  }
  v24 = (_DWORD *)*((_QWORD *)pContext + 84);
  v25 = 512;
  if ( v24 )
  {
    v7 = v95;
    if ( (v24[3] & 8) != 0 )
      *(_DWORD *)(v95 + 8) |= 0x800u;
    v26 = v24[2];
    switch ( v26 )
    {
      case 4:
        v27 = 1024;
        if ( (*(_DWORD *)(v98 + 716) & 0x8000) == 0 )
          v27 = 512;
        *(_DWORD *)(v7 + 8) |= v27;
        break;
      case 3:
        if ( (*(_DWORD *)(v98 + 716) & 0x8000) == 0 )
        {
          Parameter = -1073741311;
          v12 = 119;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              37,
              WPP_584f9b0e749e3be8080bab44300b7711_Traceguids,
              pContext,
              -1073741311);
          }
          goto LABEL_213;
        }
        *(_DWORD *)(v7 + 8) |= 0x400u;
        break;
      case 2:
        *(_DWORD *)(v7 + 8) |= 0x200u;
        break;
    }
    v28 = *(_DWORD *)(v7 + 8);
    if ( (v28 & 0x400) != 0 )
    {
      v24[5] = 3;
    }
    else if ( (v28 & 0x200) != 0 )
    {
      v24[5] = 2;
    }
    if ( (v24[3] & 8) != 0 )
      v24[6] |= 8u;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v97 + 120) + 32LL) + 32LL) + 716LL) & 0x80u) != 0 )
  {
    v29 = *(_QWORD *)(*((_QWORD *)pContext + 68) + 8LL);
    SeTokenGetRedirectionTrustPolicy(*(_QWORD *)(v29 + 48), v85, &v84);
    v30 = *(_QWORD *)(v29 + 32);
    if ( v30 && *(int *)(v29 + 40) >= 2 )
    {
      SeTokenGetRedirectionTrustPolicy(v30, &v87, &v88);
      v85[0] &= v87;
      v84 &= v88;
    }
    if ( v85[0] || v84 )
    {
      Parameter = FsRtlAllocateExtraCreateParameter(&GUID_ECP_ENABLE_REDIRECTIONGUARD, 4u, 0, 0, 0x6D537843u, &v99);
      if ( Parameter < 0 )
      {
        v12 = -64;
LABEL_212:
        v23 = v86;
LABEL_213:
        if ( v91 )
          SmbCeDecrementNtlmOpenCounts(v23, v95 + 329);
        goto LABEL_215;
      }
      v31 = *(_DWORD *)v99 ^ ((unsigned __int8)*(_DWORD *)v99 ^ v85[0]) & 1;
      *(_DWORD *)v99 = v31;
      *(_DWORD *)v99 = v31 ^ ((unsigned __int8)v31 ^ (unsigned __int8)(2 * v84)) & 2;
      Parameter = FsRtlInsertExtraCreateParameter(*((PECP_LIST *)pContext + 86), v99);
      if ( Parameter < 0 )
      {
        FsRtlFreeExtraCreateParameter(v99);
        if ( Parameter != -1073741811 )
        {
          v12 = -43;
          goto LABEL_212;
        }
      }
    }
  }
  v10 = (PDEVICE_OBJECT)*((_QWORD *)pContext + 106);
  v90 = 0;
  if ( v10 )
  {
    v32 = v98;
    Parameter = MRxSmbValidateAndGetTransportParametersNew(*(_QWORD *)&v10->Type, LODWORD(v10->DriverObject), v98, 0);
    if ( Parameter < 0 )
    {
      v12 = -1;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_212;
      }
      v33 = 38;
      goto LABEL_85;
    }
    Parameter = MRxSmbValidateIncomingPortsAgainstEffective(
                  **((_QWORD **)pContext + 106),
                  *(unsigned int *)(*((_QWORD *)pContext + 106) + 8LL),
                  v32);
    if ( Parameter < 0 )
    {
      v12 = 17;
      goto LABEL_212;
    }
    Parameter = MRxSmbGetCompressionParameters(
                  **((_QWORD **)pContext + 106),
                  *(unsigned int *)(*((_QWORD *)pContext + 106) + 8LL),
                  v95 + 324);
    if ( Parameter < 0 )
    {
      v12 = 29;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_212;
      }
      v33 = 39;
      goto LABEL_85;
    }
    Parameter = MRxSmbGetAuthenticationParameters(
                  **((_QWORD **)pContext + 106),
                  *(unsigned int *)(*((_QWORD *)pContext + 106) + 8LL),
                  &v89);
    if ( Parameter < 0 )
    {
      v12 = 40;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_212;
      }
      v33 = 40;
LABEL_85:
      WPP_SF_qD(v10->AttachedDevice, v33, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids, pContext, Parameter);
      goto LABEL_212;
    }
    if ( v89 )
    {
      v34 = v86;
      if ( !*(_BYTE *)(v86 + 656) )
      {
        v35 = SmbCeAcquireSpinLock(v9, v7, v25, v8);
        v36 = *(_DWORD *)(v34 + 12);
        if ( v36 )
        {
          if ( (unsigned int)(v36 - 3) <= 1 )
          {
            v90 = 1;
            goto LABEL_111;
          }
        }
        else if ( *(_BYTE *)(v34 + 465) && !*(_BYTE *)(v34 + 466) )
        {
          Parameter = -1073740776;
          v12 = 64;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              41,
              WPP_584f9b0e749e3be8080bab44300b7711_Traceguids,
              pContext,
              -1073740776);
          }
          *(_DWORD *)(v9 + 2352) = -1;
          ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v9 + 1920), v35);
          goto LABEL_212;
        }
        *(_BYTE *)(v34 + 656) = 1;
LABEL_111:
        *(_DWORD *)(v9 + 2352) = -1;
        ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v9 + 1920), v35);
      }
    }
  }
  v37 = v101;
  if ( *(_BYTE *)(v101 + 77) != 1 || *v13 )
  {
    if ( *((_DWORD *)pContext + 134) == 1 )
    {
      Parameter = Smb2CheckFileExistsInDirCache(pContext, v7, v25);
      if ( Parameter == -1073741772 )
      {
        v12 = 125;
        v96 = 12;
        goto LABEL_212;
      }
      v40 = *(_QWORD *)(v37 + 40);
      v41 = *((_QWORD *)pContext + 9);
      v42 = *((_QWORD *)pContext + 7);
      Parameter = 0;
      *(_OWORD *)pbBuffer = 0;
      v43 = (struct _NAME_CACHE_CONTROL_ *)(v40 + 560);
      v44 = *(_QWORD *)(v41 + 40);
      v45 = 0;
      v46 = *(_QWORD *)(v44 + 40);
      v102 = 0;
      v47 = *(_DWORD *)(v46 + 264);
      MRxSmbIsStreamFile(v42 + 360, pbBuffer);
      v48 = *(_QWORD *)(v44 + 40);
      if ( (*(_DWORD *)(*(_QWORD *)(v48 + 424) + 184LL) & 0x800) != 0
        || (v49 = -1, (*(_BYTE *)(*(_QWORD *)(v48 + 24) + 1314LL) & 4) == 0) )
      {
        v49 = *(_QWORD *)(v46 + 96);
      }
      v102 = v49;
      ExAcquirePushLockExclusiveEx(&Smb2FileNotFoundCacheLock, 0);
      Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v43, pbBuffer, &v102, 0);
      v52 = Entry;
      if ( Entry )
      {
        if ( RxNameCacheCheckEntry(Entry, v47) )
        {
          RxNameCacheExpireEntry(v43, v52);
        }
        else
        {
          Parameter = (int)v52->Link.Blink;
          v45 = 1;
          RxNameCacheActivateEntry(v43, v52, 0, 0);
        }
      }
      if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x200) != 0 )
      {
        LOWORD(EcpContext) = *(_WORD *)pbBuffer >> 1;
        McTemplateK0pphzr2q_EtwWriteTransfer(
          v51,
          (unsigned int)SmbFetchFNFCache,
          (_DWORD)pContext + 412,
          (_DWORD)pContext,
          *((_QWORD *)pContext + 7),
          EcpContext,
          *(__int64 *)&pbBuffer[8]);
      }
      ExReleasePushLockExclusiveEx(&Smb2FileNotFoundCacheLock, 0);
      if ( v45 )
      {
        v12 = -123;
        v96 = 12;
        goto LABEL_135;
      }
      LOBYTE(v6) = v103;
    }
    v53 = v84;
    v54 = v85[0];
    v55 = *(_QWORD *)(*((_QWORD *)pContext + 9) + 48LL);
    *(_OWORD *)(v55 + 72) = *((_OWORD *)pContext + 32);
    *(_OWORD *)(v55 + 88) = *((_OWORD *)pContext + 33);
    *(_OWORD *)(v55 + 104) = *((_OWORD *)pContext + 34);
    *(_OWORD *)(v55 + 120) = *((_OWORD *)pContext + 35);
    *(_OWORD *)(v55 + 136) = *((_OWORD *)pContext + 36);
    *(_QWORD *)(v55 + 152) = *((_QWORD *)pContext + 74);
    *(_QWORD *)(v55 + 104) = 0;
    *(_QWORD *)(v55 + 128) = 0;
    *(_QWORD *)(v55 + 136) = 0;
    *(_WORD *)(v55 + 168) = *((_WORD *)pContext + 373);
    *(_QWORD *)(v55 + 160) = *((_QWORD *)pContext + 101);
    *(_BYTE *)(v55 + 170) = v54;
    *(_BYTE *)(v55 + 171) = v53;
    Parameter = Smb2AttemptDeferredOpen(pContext);
    if ( Parameter == -1073741802 )
    {
      v39 = v100;
      if ( *(_BYTE *)(v100 + 80) )
      {
        if ( (v6 & 0x10) != 0 )
        {
          v57 = pContext[32];
          v58 = *((_DWORD *)pContext + 30) & 0xFFFFEFFF;
          v59 = pContext[33];
          v60 = *((_DWORD *)pContext + 30) & 0x1000;
          v61 = *((_QWORD *)pContext + 8);
          v62 = (_QWORD **)(v97 + 264);
          v63 = (_QWORD *)*((_QWORD *)pContext + 9);
          *((_WORD *)pContext + 16) = 27;
          *((_DWORD *)pContext + 30) = v58;
          v64 = *v62;
          v102 = v61;
          v92 = v57;
          v93 = v59;
          if ( v64 != v62 )
          {
            while ( 1 )
            {
              v65 = v64 - 17;
              if ( *((_WORD *)v64 - 68) != 0xEBAA )
                break;
              v64 = (_QWORD *)*v64;
              if ( v64 == v62 )
                goto LABEL_159;
            }
            if ( v64 != (_QWORD *)136 )
            {
              do
              {
                v66 = (_QWORD *)v65[17];
                if ( v66 == v62 )
                {
LABEL_147:
                  v67 = 0;
                }
                else
                {
                  while ( 1 )
                  {
                    v67 = v66 - 17;
                    if ( *((_WORD *)v66 - 68) != 0xEBAA )
                      break;
                    v66 = (_QWORD *)*v66;
                    if ( v66 == v62 )
                      goto LABEL_147;
                  }
                }
                if ( v65 != v63 && (v65[9] & 0x604) == 0 && v65[6] )
                {
                  *((_QWORD *)pContext + 9) = v65;
                  v68 = (_QWORD *)v65[23];
                  if ( v68 == v65 + 23 )
                  {
LABEL_154:
                    v69 = 0;
                  }
                  else
                  {
                    while ( 1 )
                    {
                      v69 = v68 - 14;
                      if ( *((_WORD *)v68 - 56) != 0xEBAA )
                        break;
                      v68 = (_QWORD *)*v68;
                      if ( v68 == v65 + 23 )
                        goto LABEL_154;
                    }
                  }
                  *((_QWORD *)pContext + 8) = v69;
                  if ( (int)Smb2ValidateAndReconnectSrvOpen(pContext) < 0 )
                    RxOrphanSrvOpen(v65);
                }
                v65 = v67;
              }
              while ( v67 );
              v61 = v102;
              v57 = v92;
              v59 = v93;
            }
          }
LABEL_159:
          if ( v60 )
            *((_DWORD *)pContext + 30) |= 0x1000u;
          pContext[32] = v57;
          pContext[33] = v59;
          *((_QWORD *)pContext + 9) = v63;
          *((_QWORD *)pContext + 8) = v61;
        }
        *(_BYTE *)(v39 + 80) = 0;
      }
      v70 = v97;
      if ( (*(_DWORD *)(v98 + 716) & 0x20) != 0
        && !*(_BYTE *)(v101 + 77)
        && *(_WORD *)v97 == 0xEC22
        && (*(_DWORD *)(v97 + 156) & 0x10) == 0 )
      {
        *(_OWORD *)pbBuffer = 0;
        Parameter = BCryptGenRandom(0, pbBuffer, 0x10u, 2u);
        if ( Parameter < 0 )
        {
          v12 = -43;
          goto LABEL_212;
        }
        *(_OWORD *)(v70 + 168) = *(_OWORD *)pbBuffer;
      }
      v71 = v104;
      v94 = 0;
      Parameter = SmbCeInitializeExchange(&v94, pContext, 0, 0, 0, v104, 2416, &CreateDispatch);
      if ( Parameter )
      {
        v12 = -15;
      }
      else
      {
        _InterlockedOr((volatile signed __int32 *)(v94 + 68), 0x81u);
        if ( v90 )
          *(_BYTE *)(v94 + 2410) = 1;
        *(_BYTE *)(v94 + 1016) = pContext[787];
        Parameter = SmbCeInitiateExchange(v94);
        switch ( Parameter )
        {
          case 259:
            v72 = v95;
            if ( ((*(_DWORD *)(v95 + 48) & 0xFFEFFE7F) != 0 || *((_DWORD *)pContext + 134) != 1)
              && ((v73 = *(_DWORD *)(v39 + 60), (unsigned int)(v73 - 8) <= 1)
               || v73 == 255 && (*(_DWORD *)(v39 + 64) & 6) != 0 && *(_DWORD *)(v39 + 68) != -1) )
            {
              v12 = 44;
              v77 = RxFcbGetOutstandingBufferingChangeEvent(v70);
              v75 = RxProcessFcbChangeBufferingStateRequest;
              v74 = v70;
              v76 = v77;
            }
            else
            {
              v74 = 0;
              v75 = 0;
              v76 = 0;
              v12 = 44;
            }
            Parameter = SmbCeWaitForCompletionAndFinalizeExchangeEx(v94, v76, v75, v74);
            break;
          case 0:
            if ( (*(_BYTE *)(MRxSmbGetCompressionConfigBlock() + 26) & 2) == 0 )
            {
              if ( (*(_BYTE *)(MRxSmbGetCompressionConfigBlock() + 26) & 1) != 0
                && !*(_BYTE *)(*(_QWORD *)(v71 + 24) + 1312LL)
                || (v78 = *(_DWORD *)(v72 + 324), v78 != -1)
                && (v10 = (PDEVICE_OBJECT)*(unsigned int *)(v71 + 476), (_DWORD)v10 != -1)
                && ((_DWORD)v10 == 1 || v78 == 1 || (*(_DWORD *)(*(_QWORD *)(v71 + 424) + 180LL) & 0x80000) != 0) )
              {
                Smb2EnableCompressionForFobx(*((_QWORD *)pContext + 8), 0);
              }
            }
            goto LABEL_195;
          case -1073741772:
          case -1073741766:
            v80 = v101;
            Smb2CacheFileNotFound(pContext, *(_QWORD *)(v101 + 40) + 560LL, (unsigned int)Parameter);
            v81 = Parameter != -1073741772;
            Smb2DeleteSingleFileInDirInfoCache(pContext, *(_QWORD *)(v80 + 40) + 1112LL, v81);
            Smb2InvalidateFileIdentityCacheEntryEx(pContext, *(_QWORD *)(v80 + 40) + 192LL, 0, 0);
            Smb2InvalidateFileAbeStatusCacheEntry(pContext, *(_QWORD *)(v80 + 40) + 1296LL, v81);
            break;
          case -1073741771:
            Smb2InvalidateFileNotFoundCacheEx(pContext, *(_QWORD *)(v101 + 40) + 560LL, 0, 0);
            goto LABEL_212;
          default:
            v12 = 5;
            SmbCeWaitForCompletionAndFinalizeExchangeEx(v94, 0, 0, 0);
            v72 = v95;
            break;
        }
      }
      v56 = Parameter < 0;
      goto LABEL_211;
    }
    v12 = -98;
LABEL_135:
    v56 = Parameter < 0;
    if ( !Parameter )
    {
      v39 = v100;
      goto LABEL_195;
    }
LABEL_211:
    if ( !v56 )
      goto LABEL_217;
    goto LABEL_212;
  }
  if ( !*((_QWORD *)pContext + 8) )
  {
    NetFobx = RxCreateNetFobx((PRX_CONTEXT)pContext, (PMRX_SRV_OPEN)v3);
    *((_QWORD *)pContext + 8) = NetFobx;
    if ( !NetFobx )
    {
      Parameter = -1073741670;
      v12 = 112;
      goto LABEL_212;
    }
  }
  v39 = v100;
  *(_DWORD *)(v95 + 8) |= 1u;
  Parameter = 0;
LABEL_195:
  v79 = *(_DWORD *)(v95 + 8);
  if ( (v79 & 0x400) != 0 )
  {
    ++*(_DWORD *)(v39 + 76);
  }
  else if ( (v79 & 0x200) != 0 )
  {
    ++*(_DWORD *)(v39 + 72);
  }
  if ( ((*(_BYTE *)(*((_QWORD *)pContext + 10) + 1314LL) & 0x20) != 0 || dbgEnableTurboIo)
    && (*((_DWORD *)pContext + 135) & 8) != 0
    && (*((_DWORD *)pContext + 128) & 3) != 0
    && (int)RxOpenFileObjectForTurboIo(
              *(_QWORD *)(*((_QWORD *)pContext + 6) + 48LL),
              *((_QWORD *)pContext + 7),
              &MRxSmb2TurboIoDispatch) >= 0 )
  {
    RxEnableTurboIo(*((_QWORD *)pContext + 7));
  }
LABEL_217:
  if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 2) != 0 )
  {
    LOBYTE(v8) = -75;
    McTemplateK0uq_EtwWriteTransfer(v10, v7, pContext + 412, v8, Parameter);
  }
  return (unsigned int)Parameter;
}

```

## disassembly

```asm
0x1400236b0  push    rbp
0x1400236b2  push    rbx
0x1400236b3  push    rsi
0x1400236b4  push    rdi
0x1400236b5  push    r12
0x1400236b7  push    r13
0x1400236b9  push    r14
0x1400236bb  push    r15
0x1400236bd  lea     rbp, [rsp-1Fh]
0x1400236c2  sub     rsp, 0D8h
0x1400236c9  mov     rax, cs:__security_cookie
0x1400236d0  xor     rax, rsp
0x1400236d3  mov     [rbp+57h+var_50], rax
0x1400236d7  mov     rdi, [rcx+38h]
0x1400236db  mov     r14, rcx
0x1400236de  mov     rsi, [rcx+48h]
0x1400236e2  mov     r12, [rcx+288h]
0x1400236e9  mov     [rbp+57h+var_A0], rdi
0x1400236ed  mov     [rbp+57h+var_80], r12
0x1400236f1  mov     rax, [rsi+28h]
0x1400236f5  mov     rbx, [rax+28h]
0x1400236f9  mov     [rbp+57h+var_68], rbx
0x1400236fd  mov     rax, [rbx+1A0h]
0x140023704  mov     [rbp+57h+var_C8], rax
0x140023708  mov     rax, [rax+180h]
0x14002370f  mov     [rbp+57h+var_98], rax
0x140023713  xor     eax, eax
0x140023715  mov     [rbp+57h+var_B8], rax
0x140023719  mov     r13d, [rdi+9Ch]
0x140023720  mov     [rbp+57h+var_70], r13d
0x140023724  mov     [rbp+57h+var_A8], eax
0x140023727  call    cs:__imp_KeGetCurrentIrql
0x14002372e  nop     dword ptr [rax+rax+00h]
0x140023733  mov     r15, [rbx+18h]
0x140023737  xor     ecx, ecx
0x140023739  test    byte ptr cs:WPP_MAIN_CB.Queue+10h, 2
0x140023740  mov     [rbp+57h+var_BE], 0
0x140023744  mov     [rbp+57h+var_90], rcx
0x140023748  mov     [rbp+57h+var_CF], cl
0x14002374b  mov     [rbp+57h+var_C0], cl
0x14002374e  mov     [rbp+57h+var_D0], cl
0x140023751  mov     [rbp+57h+var_BF], cl
0x140023754  jz      short loc_140023769
0x140023756  lea     r8, [r14+19Ch]
0x14002375d  mov     [rsp+110h+PoolTag], ecx
0x140023761  mov     r9b, 0B4h
0x140023764  call    McTemplateK0uq_EtwWriteTransfer
0x140023769  mov     eax, [rdi+9Ch]
0x14002376f  test    al, 4
0x140023771  jz      short loc_140023782
0x140023773  mov     edi, 0C0000002h
0x140023778  mov     esi, 9CBh
0x14002377d  jmp     loc_1400246E0
0x140023782  cmp     byte ptr [r12+4Dh], 5
0x140023788  jnz     short loc_140023799
0x14002378a  mov     edi, 0C0000002h
0x14002378f  mov     esi, 9D2h
0x140023794  jmp     loc_1400246E0
0x140023799  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400237a0  lea     rax, WPP_GLOBAL_Control
0x1400237a7  lea     r12, [rdi+168h]
0x1400237ae  cmp     rcx, rax
0x1400237b1  jz      short loc_1400237DD
0x1400237b3  mov     eax, [rcx+2Ch]
0x1400237b6  test    al, 20h
0x1400237b8  jz      short loc_1400237DD
0x1400237ba  cmp     byte ptr [rcx+29h], 2
0x1400237be  jb      short loc_1400237DD
0x1400237c0  mov     rcx, [rcx+18h]
0x1400237c4  lea     r8, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids
0x1400237cb  mov     edx, 22h ; '"'
0x1400237d0  mov     qword ptr [rsp+110h+PoolTag], r12
0x1400237d5  mov     r9, r14
0x1400237d8  call    WPP_SF_qZ
0x1400237dd  lock inc qword ptr [rbx+1E8h]
0x1400237e5  mov     rcx, [rdi+88h]
0x1400237ec  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1400237f3  mov     [rbp+57h+var_88], rcx
0x1400237f7  test    rcx, rcx
0x1400237fa  jnz     loc_140023892
0x140023800  mov     rcx, rdi
0x140023803  call    Smb2AllocateFcbExtension
0x140023808  mov     [rbp+57h+var_88], rax
0x14002380c  test    rax, rax
0x14002380f  jnz     short loc_140023820
0x140023811  mov     edi, 0C000009Ah
0x140023816  mov     esi, 9E6h
0x14002381b  jmp     loc_1400246E0
0x140023820  test    byte ptr [r14+2EAh], 10h
0x140023828  jz      short loc_14002382E
0x14002382a  or      dword ptr [rax+8], 1
0x14002382e  mov     rax, [rbp+57h+var_98]
0x140023832  mov     eax, [rax+2CCh]
0x140023838  test    al, 20h
0x14002383a  jz      short loc_140023892
0x14002383c  xorps   xmm0, xmm0
0x14002383f  lea     rdx, [rbp+57h+pbBuffer]; pbBuffer
0x140023843  mov     r9d, 2; dwFlags
0x140023849  mov     r8d, 10h; cbBuffer
0x14002384f  xor     ecx, ecx; hAlgorithm
0x140023851  movups  xmmword ptr [rbp+57h+pbBuffer], xmm0
0x140023855  call    cs:__imp_BCryptGenRandom
0x14002385c  nop     dword ptr [rax+rax+00h]
0x140023861  mov     edi, eax
0x140023863  test    eax, eax
0x140023865  jns     short loc_140023871
0x140023867  mov     esi, 9FDh
0x14002386c  jmp     loc_1400246E0
0x140023871  mov     rdx, qword ptr [rbp+57h+pbBuffer+8]
0x140023875  mov     rax, rbx
0x140023878  mov     rcx, qword ptr [rbp+57h+pbBuffer]
0x14002387c  mov     rdi, [rbp+57h+var_A0]
0x140023880  lock cmpxchg [rdi+0A8h], rcx
0x140023889  jnz     short loc_140023892
0x14002388b  mov     [rdi+0B0h], rdx
0x140023892  mov     rcx, [rdi+120h]
0x140023899  test    rcx, rcx
0x14002389c  jz      loc_140023934
0x1400238a2  cmp     qword ptr [rcx+88h], 0
0x1400238aa  jnz     loc_140023934
0x1400238b0  call    Smb2AllocateFcbExtension
0x1400238b5  test    rax, rax
0x1400238b8  jnz     short loc_1400238C9
0x1400238ba  mov     edi, 0C000009Ah
0x1400238bf  mov     esi, 0A16h
0x1400238c4  jmp     loc_1400246E0
0x1400238c9  mov     rax, [rbp+57h+var_98]
0x1400238cd  mov     eax, [rax+2CCh]
0x1400238d3  test    al, 20h
0x1400238d5  jz      short loc_140023934
0x1400238d7  xorps   xmm0, xmm0
0x1400238da  lea     rdx, [rbp+57h+pbBuffer]; pbBuffer
0x1400238de  mov     r9d, 2; dwFlags
0x1400238e4  mov     r8d, 10h; cbBuffer
0x1400238ea  xor     ecx, ecx; hAlgorithm
0x1400238ec  movups  xmmword ptr [rbp+57h+pbBuffer], xmm0
0x1400238f0  call    cs:__imp_BCryptGenRandom
0x1400238f7  nop     dword ptr [rax+rax+00h]
0x1400238fc  mov     edi, eax
0x1400238fe  test    eax, eax
0x140023900  jns     short loc_14002390C
0x140023902  mov     esi, 0A25h
0x140023907  jmp     loc_1400246E0
0x14002390c  mov     rdx, [rbp+57h+var_A0]
0x140023910  mov     rax, rbx
0x140023913  mov     r8, qword ptr [rbp+57h+pbBuffer+8]
0x140023917  mov     rcx, qword ptr [rbp+57h+pbBuffer]
0x14002391b  mov     rdx, [rdx+120h]
0x140023922  lock cmpxchg [rdx+0A8h], rcx
0x14002392b  jnz     short loc_140023934
0x14002392d  mov     [rdx+0B0h], r8
0x140023934  mov     rax, [rsi+30h]
0x140023938  mov     [rbp+57h+var_B0], rax
0x14002393c  test    rax, rax
0x14002393f  jnz     loc_140023A73
0x140023945  mov     edx, 180h
0x14002394a  mov     ecx, 100h
0x14002394f  mov     r8d, 6D536946h
0x140023955  call    cs:__imp_ExAllocatePool2
0x14002395c  nop     dword ptr [rax+rax+00h]
0x140023961  mov     [rbp+57h+var_B0], rax
0x140023965  mov     rdi, rax
0x140023968  test    rax, rax
0x14002396b  jz      loc_140023A64
0x140023971  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140023979  lea     rcx, [rax+38h]
0x14002397d  mov     word ptr [rax], 0E410h
0x140023982  mov     dword ptr [rax+4], 1
0x140023989  mov     qword ptr [rax+10h], 0
0x140023991  movups  xmmword ptr [rax+1Ch], xmm0
0x140023995  mov     [rcx+8], rcx
0x140023999  mov     [rcx], rcx
0x14002399c  lea     rcx, [rax+108h]; Uuid
0x1400239a3  mov     [rax+0B0h], rbx
0x1400239aa  call    cs:__imp_ExUuidCreate
0x1400239b1  nop     dword ptr [rax+rax+00h]
0x1400239b6  mov     qword ptr [rdi+100h], 23C34600h
0x1400239c1  xor     eax, eax
0x1400239c3  mov     [rdi+144h], rax
0x1400239ca  lea     rax, [rdi+150h]
0x1400239d1  mov     [rax+8], rax
0x1400239d5  mov     [rax], rax
0x1400239d8  mov     [rsi+30h], rdi
0x1400239dc  movzx   edx, byte ptr [r14+313h]
0x1400239e4  mov     [rdi+148h], dl
0x1400239ea  test    dl, 3
0x1400239ed  jz      short loc_140023A3D
0x1400239ef  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400239f6  lea     rax, WPP_GLOBAL_Control
0x1400239fd  cmp     rcx, rax
0x140023a00  jz      short loc_140023A3D
0x140023a02  mov     eax, [rcx+2Ch]
0x140023a05  test    al, 40h
0x140023a07  jz      short loc_140023A3D
0x140023a09  cmp     byte ptr [rcx+29h], 2
0x140023a0d  jb      short loc_140023A3D
0x140023a0f  mov     rcx, [rcx+18h]
0x140023a13  mov     r8d, edx
0x140023a16  mov     eax, r8d
0x140023a19  shr     edx, 2
0x140023a1c  shr     eax, 1
0x140023a1e  and     edx, 1
0x140023a21  mov     dword ptr [rsp+110h+var_E0], edx
0x140023a25  and     eax, 1
0x140023a28  and     r8d, 1
0x140023a2c  mov     dword ptr [rsp+110h+EcpContext], eax
0x140023a30  mov     r9, rdi
0x140023a33  mov     [rsp+110h+PoolTag], r8d
0x140023a38  call    WPP_SF_qddd
0x140023a3d  mov     rbx, [rbp+57h+var_C8]
0x140023a41  lea     r8, [rdi+149h]
0x140023a48  mov     rcx, rbx
0x140023a4b  lea     rdx, [rdi+148h]
0x140023a52  call    cs:__imp_SmbCeIncrementNtlmOpenCounts
0x140023a59  nop     dword ptr [rax+rax+00h]
0x140023a5e  mov     [rbp+57h+var_BC], 1
0x140023a62  jmp     short loc_140023A7B
0x140023a64  mov     edi, 0C000009Ah
0x140023a69  mov     esi, 0A38h
0x140023a6e  jmp     loc_1400246E0
0x140023a73  mov     rbx, [rbp+57h+var_C8]
0x140023a77  mov     [rbp+57h+var_BC], 0
0x140023a7b  mov     rdx, [r14+2A8h]
0x140023a82  mov     rcx, rbx
0x140023a85  call    Smb2SetupAlternateSPNForSession
0x140023a8a  mov     edi, eax
0x140023a8c  test    eax, eax
0x140023a8e  jns     short loc_140023ACF
0x140023a90  mov     esi, 0A5Bh
0x140023a95  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140023a9c  lea     rax, WPP_GLOBAL_Control
0x140023aa3  cmp     rcx, rax
0x140023aa6  jz      loc_1400246C0
0x140023aac  mov     eax, [rcx+2Ch]
0x140023aaf  test    al, 1
0x140023ab1  jz      loc_1400246C0
0x140023ab7  cmp     byte ptr [rcx+29h], 1
0x140023abb  jb      loc_1400246C0
0x140023ac1  mov     edx, 24h ; '$'
0x140023ac6  mov     [rsp+110h+PoolTag], edi
0x140023aca  jmp     loc_140023B7F
0x140023acf  mov     rcx, [r14+2A0h]
0x140023ad6  mov     r8d, 200h
0x140023adc  test    rcx, rcx
0x140023adf  jz      loc_140023BC9
0x140023ae5  mov     eax, [rcx+0Ch]
0x140023ae8  mov     rdx, [rbp+57h+var_B0]
0x140023aec  test    al, 8
0x140023aee  jz      short loc_140023AF7
0x140023af0  or      dword ptr [rdx+8], 800h
0x140023af7  mov     eax, [rcx+8]
0x140023afa  cmp     eax, 4
0x140023afd  jnz     short loc_140023B1E
0x140023aff  mov     rax, [rbp+57h+var_98]
0x140023b03  test    dword ptr [rax+2CCh], 8000h
0x140023b0d  mov     eax, 400h
0x140023b12  cmovz   eax, r8d
0x140023b16  or      [rdx+8], eax
0x140023b19  jmp     loc_140023BA0
0x140023b1e  cmp     eax, 3
0x140023b21  jnz     short loc_140023B97
0x140023b23  mov     rax, [rbp+57h+var_98]
0x140023b27  test    dword ptr [rax+2CCh], 8000h
0x140023b31  jz      short loc_140023B3C
0x140023b33  or      dword ptr [rdx+8], 400h
0x140023b3a  jmp     short loc_140023BA0
0x140023b3c  mov     edi, 0C0000201h
0x140023b41  mov     esi, 0A77h
0x140023b46  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140023b4d  lea     rax, WPP_GLOBAL_Control
0x140023b54  cmp     rcx, rax
0x140023b57  jz      loc_1400246C0
0x140023b5d  mov     eax, [rcx+2Ch]
0x140023b60  test    al, 1
0x140023b62  jz      loc_1400246C0
0x140023b68  cmp     byte ptr [rcx+29h], 1
0x140023b6c  jb      loc_1400246C0
0x140023b72  mov     edx, 25h ; '%'
0x140023b77  mov     [rsp+110h+PoolTag], 0C0000201h
0x140023b7f  mov     rcx, [rcx+18h]
0x140023b83  lea     r8, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids
0x140023b8a  mov     r9, r14
0x140023b8d  call    WPP_SF_qD
0x140023b92  jmp     loc_1400246C0
0x140023b97  cmp     eax, 2
0x140023b9a  jnz     short loc_140023BA0
0x140023b9c  or      [rdx+8], r8d
0x140023ba0  mov     eax, [rdx+8]
0x140023ba3  bt      eax, 0Ah
0x140023ba7  jnb     short loc_140023BB2
0x140023ba9  mov     dword ptr [rcx+14h], 3
0x140023bb0  jmp     short loc_140023BBE
0x140023bb2  test    r8d, eax
0x140023bb5  jz      short loc_140023BBE
0x140023bb7  mov     dword ptr [rcx+14h], 2
0x140023bbe  mov     eax, [rcx+0Ch]
0x140023bc1  test    al, 8
0x140023bc3  jz      short loc_140023BC9
0x140023bc5  or      dword ptr [rcx+18h], 8
0x140023bc9  mov     rax, [rbp+57h+var_A0]
  ... truncated ...
```
