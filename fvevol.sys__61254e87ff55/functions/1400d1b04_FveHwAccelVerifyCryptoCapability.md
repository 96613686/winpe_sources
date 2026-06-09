# FveHwAccelVerifyCryptoCapability

- ea: `0x1400d1b04`
- end: `0x1400d2f57`
- name: `FveHwAccelVerifyCryptoCapability`
- size: `5203`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400d1490`

## callees

- `0x140005e60`
- `0x140008348`
- `0x140008cd0`
- `0x140008d20`
- `0x140008e80`
- `0x140008f04`
- `0x14000afb4`
- `0x14000bda8`
- `0x14000c9ec`
- `0x14000d690`
- `0x140011e98`
- `0x140011f0c`
- `0x140011fe0`
- `0x140012238`
- `0x140014d88`
- `0x140016cfc`
- `0x140023040`
- `0x1400276e0`
- `0x140063bd4`
- `0x14009eed0`
- `0x1400b6f14`
- `0x1400cf764`
- `0x1400d0408`
- `0x1400d073c`
- `0x1400d0ce4`
- `0x1400d1b04`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400d270e`
- `ntoskrnl!RtlCompareMemory` at `0x1400d286d`
- `ntoskrnl!RtlCompareMemory` at `0x1400d2ce9`
- `ntoskrnl!RtlCompareMemory` at `0x1400d270e`
- `ntoskrnl!RtlCompareMemory` at `0x1400d286d`
- `ntoskrnl!RtlCompareMemory` at `0x1400d2ce9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400d1fe6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400d1fe6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d2efa`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d2efa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d2e5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d2e78`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d2e96`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d2eb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d2e5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d2e78`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d2e96`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d2eb3`
- `ntoskrnl!ExAllocatePool2` at `0x1400d1dff`
- `ntoskrnl!ExAllocatePool2` at `0x1400d1f41`
- `ntoskrnl!ExAllocatePool2` at `0x1400d1f60`
- `ntoskrnl!ExAllocatePool2` at `0x1400d1f7f`
- `ntoskrnl!ExAllocatePool2` at `0x1400d1f9e`
- `ntoskrnl!ExAllocatePool2` at `0x1400d1dff`
- `ntoskrnl!ExAllocatePool2` at `0x1400d1f41`
- `ntoskrnl!ExAllocatePool2` at `0x1400d1f60`
- `ntoskrnl!ExAllocatePool2` at `0x1400d1f7f`
- `ntoskrnl!ExAllocatePool2` at `0x1400d1f9e`
- `ext-ms-win-accel-api-km-l1-1-1!AccelDestroyCryptoWorkspace` at `0x1400d2e33`
- `ext-ms-win-accel-api-km-l1-1-1!AccelDestroyCryptoWorkspace` at `0x1400d2e33`
- `ext-ms-win-accel-api-km-l1-1-1!AccelSymmetricDecryptBuffer` at `0x1400d2838`
- `ext-ms-win-accel-api-km-l1-1-1!AccelSymmetricDecryptBuffer` at `0x1400d2c86`
- `ext-ms-win-accel-api-km-l1-1-1!AccelSymmetricDecryptBuffer` at `0x1400d2838`
- `ext-ms-win-accel-api-km-l1-1-1!AccelSymmetricDecryptBuffer` at `0x1400d2c86`
- `ext-ms-win-accel-api-km-l1-1-1!AccelSymmetricEncryptBuffer` at `0x1400d26da`
- `ext-ms-win-accel-api-km-l1-1-1!AccelSymmetricEncryptBuffer` at `0x1400d26da`
- `ext-ms-win-accel-api-km-l1-1-1!AccelConfigureWorkspaceCryptoCapability` at `0x1400d24e7`
- `ext-ms-win-accel-api-km-l1-1-1!AccelConfigureWorkspaceCryptoCapability` at `0x1400d24e7`
- `ext-ms-win-accel-api-km-l1-1-1!AccelInitializeCryptoWorkspace` at `0x1400d244a`
- `ext-ms-win-accel-api-km-l1-1-1!AccelInitializeCryptoWorkspace` at `0x1400d244a`

## pseudocode

```c
__int64 __fastcall FveHwAccelVerifyCryptoCapability(__int64 a1, unsigned int *a2, __int64 *a3)
{
  unsigned int v3; // edi
  __int64 v4; // rsi
  __int64 v5; // r13
  unsigned __int64 v6; // r14
  unsigned int *v7; // r15
  __int64 v8; // rdi
  unsigned int v9; // ebx
  ULONG v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  unsigned int CapabilityVerificationEntry; // esi
  __int64 v15; // r8
  __int64 v16; // r12
  __int64 Pool2; // rax
  __int64 *v18; // rcx
  void *v19; // rax
  __int64 v20; // rdi
  int KeySizeFromFvekKeyType; // ebx
  __int64 v22; // r8
  unsigned __int64 v23; // r13
  unsigned __int64 v24; // rax
  char *v25; // rdi
  unsigned int *v26; // r15
  PDEVICE_OBJECT v27; // rcx
  __int64 v28; // rdx
  int v29; // esi
  char v30; // al
  __int64 *v31; // r8
  unsigned int v32; // edi
  unsigned int v33; // esi
  __int64 v34; // rcx
  int v35; // eax
  unsigned int v36; // edi
  bool v37; // zf
  PDEVICE_OBJECT v38; // rcx
  __int64 v39; // rdx
  unsigned int v40; // eax
  unsigned int v41; // edi
  unsigned __int64 v42; // rsi
  unsigned int v43; // esi
  unsigned int v44; // r15d
  unsigned int v45; // r14d
  unsigned __int64 v46; // rdx
  __int64 v47; // rax
  int v48; // eax
  unsigned int v49; // r15d
  __int64 v50; // rax
  int v51; // eax
  PDEVICE_OBJECT v52; // rcx
  __int64 v53; // rdx
  PDEVICE_OBJECT v54; // rcx
  __int64 v55; // rdx
  PDEVICE_OBJECT v56; // rcx
  __int64 v57; // rdx
  PVOID v58; // rdi
  PDEVICE_OBJECT v59; // rcx
  __int64 v60; // rdx
  __int64 v61; // r9
  __int64 v62; // rax
  void *v63; // rdi
  int v64; // eax
  PUCHAR v66; // [rsp+30h] [rbp-D8h]
  ULONGLONG ullMultiplier; // [rsp+40h] [rbp-C8h]
  ULONGLONG ullMultipliera; // [rsp+40h] [rbp-C8h]
  __int64 v69; // [rsp+48h] [rbp-C0h]
  unsigned __int16 v70; // [rsp+54h] [rbp-B4h] BYREF
  __int64 v71; // [rsp+58h] [rbp-B0h] BYREF
  PVOID P; // [rsp+60h] [rbp-A8h]
  void *Source1; // [rsp+68h] [rbp-A0h]
  PVOID Entry; // [rsp+70h] [rbp-98h]
  __int64 v75; // [rsp+78h] [rbp-90h] BYREF
  PUCHAR v76; // [rsp+80h] [rbp-88h]
  void *Source2; // [rsp+88h] [rbp-80h]
  int v78; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int64 v79; // [rsp+98h] [rbp-70h]
  int v80[2]; // [rsp+A0h] [rbp-68h] BYREF
  PVOID v81; // [rsp+A8h] [rbp-60h]
  __int128 v82; // [rsp+B0h] [rbp-58h] BYREF
  int v83[24]; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v84; // [rsp+128h] [rbp+20h] BYREF
  PUCHAR v85; // [rsp+130h] [rbp+28h]
  unsigned int v86; // [rsp+138h] [rbp+30h]
  int v87; // [rsp+13Ch] [rbp+34h]
  __int128 v88; // [rsp+140h] [rbp+38h] BYREF
  __int128 v89; // [rsp+150h] [rbp+48h]
  __int128 v90; // [rsp+160h] [rbp+58h]
  __int64 v91; // [rsp+170h] [rbp+68h]
  int v92[24]; // [rsp+178h] [rbp+70h] BYREF
  int v93[64]; // [rsp+1D8h] [rbp+D0h] BYREF
  __int64 v97; // [rsp+340h] [rbp+238h] BYREF

  v3 = a2[8];
  v4 = *(_QWORD *)(a1 + 8);
  v5 = a1;
  v6 = *(unsigned int *)(a1 + 1308);
  v7 = a2;
  v69 = v4;
  if ( ((v3 - 1) & v3) != 0 || !v3 )
  {
    if ( 0x10000 % v3 )
      v8 = v3 - 0x10000 % v3 + 0x10000;
    else
      v8 = 0x10000;
  }
  else
  {
    v8 = ~(v3 - 1) & (v3 + 0xFFFF);
  }
  v9 = a2[7];
  v79 = *((_QWORD *)a2 + 5);
  P = 0;
  Source1 = 0;
  Source2 = 0;
  v76 = 0;
  *(_QWORD *)v80 = 0;
  v81 = 0;
  v70 = 0;
  LOWORD(v71) = 0;
  if ( ((v9 - 1) & v9) != 0 || !v9 )
  {
    if ( 0x40 % v9 )
      v10 = v9 - 0x40 % v9 + 64;
    else
      v10 = 64;
  }
  else
  {
    v10 = ~(v9 - 1) & (v9 + 63);
  }
  Entry = 0;
  memset(v92, 0, sizeof(v92));
  memset(v83, 0, sizeof(v83));
  v97 = 0;
  v75 = 0;
  HIDWORD(v84) = 0;
  v82 = 0;
  v91 = 0;
  v88 = 0;
  v87 = 0;
  v89 = 0;
  v90 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids);
  }
  if ( (*(_DWORD *)(v4 + 9928) & 0x10000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        55,
        WPP_7f5e3a43786933c00401282694ab6ced_Traceguids,
        (unsigned int)v6);
    }
    v79 = v6;
  }
  memset(v93, 0, sizeof(v93));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_LddLd(
      WPP_GLOBAL_Control->AttachedDevice,
      v11,
      v12,
      *v7,
      v7[4],
      v7[5],
      v6,
      (*(_DWORD *)(v4 + 9928) >> 23) & 1);
  }
  v78 = v6;
  CapabilityVerificationEntry = FveHwAccelFindCapabilityVerificationEntry(v4, v7, &v78, &v97);
  if ( (int)(CapabilityVerificationEntry + 0x80000000) < 0 || CapabilityVerificationEntry == -1073741275 )
  {
    if ( (CapabilityVerificationEntry & 0x80000000) == 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v16 = v97;
LABEL_261:
        CapabilityVerificationEntry = 0;
        *a3 = v16;
        goto LABEL_262;
      }
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v16 = v97;
        WPP_SF_Ldd(
          WPP_GLOBAL_Control->AttachedDevice,
          v13,
          v15,
          *(unsigned int *)(v97 + 16),
          *(_DWORD *)(v97 + 28),
          *(unsigned __int8 *)(v97 + 24));
      }
      else
      {
        v16 = v97;
      }
LABEL_257:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        LODWORD(v66) = v7[4];
        WPP_SF_dLddL(WPP_GLOBAL_Control->AttachedDevice, v13, v15, *(unsigned __int8 *)(v16 + 24), *v7, v66, v7[5], v6);
      }
      goto LABEL_261;
    }
    Pool2 = ExAllocatePool2(64, 32, 1749374534);
    v16 = Pool2;
    if ( !Pool2 )
    {
      CapabilityVerificationEntry = -1073741670;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_262;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids, 3221225626LL);
      goto LABEL_45;
    }
    *(_OWORD *)Pool2 = 0;
    *(_OWORD *)(Pool2 + 16) = 0;
    v18 = *(__int64 **)(v69 + 10768);
    if ( *v18 != v69 + 10760 )
      __fastfail(3u);
    *(_QWORD *)Pool2 = v69 + 10760;
    *(_QWORD *)(Pool2 + 8) = v18;
    *v18 = Pool2;
    *(_QWORD *)(v69 + 10768) = Pool2;
    *(_DWORD *)(Pool2 + 16) = *v7;
    *(_DWORD *)(Pool2 + 20) = v78;
    LOBYTE(v97) = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids, *v7);
    }
    v76 = (PUCHAR)ExAllocatePool2(64, v10, 1749374534);
    P = (PVOID)ExAllocatePool2(64, v8, 1749374534);
    Source1 = (void *)ExAllocatePool2(64, v8, 1749374534);
    v19 = (void *)ExAllocatePool2(64, v8, 1749374534);
    Source2 = v19;
    if ( !v76 || !P || !Source1 || !v19 )
    {
      KeySizeFromFvekKeyType = -1073741670;
      v59 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_77;
      }
      v60 = 61;
      v61 = 3221225626LL;
LABEL_231:
      WPP_SF_d(v59->AttachedDevice, v60, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids, v61);
      goto LABEL_77;
    }
    v20 = v69;
    Entry = ExAllocateFromNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v69 + 10712));
    if ( !Entry )
    {
      KeySizeFromFvekKeyType = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids, 3221225626LL);
      }
      goto LABEL_78;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids, 0x10000, v10);
    }
    v22 = 0;
    v23 = v6;
    do
    {
      v24 = (unsigned int)v22;
      v25 = (char *)P + v22;
      v22 = (unsigned int)(v6 + v22);
      memset64(v25, v24, v6 >> 3);
    }
    while ( (unsigned int)v22 < 0x10000 );
    v26 = a2;
    KeySizeFromFvekKeyType = FveRandomDataCallback(v76, v10);
    if ( KeySizeFromFvekKeyType < 0 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_76;
      }
      v28 = 64;
LABEL_75:
      WPP_SF_d(
        v27->AttachedDevice,
        v28,
        WPP_7f5e3a43786933c00401282694ab6ced_Traceguids,
        (unsigned int)KeySizeFromFvekKeyType);
LABEL_76:
      v5 = a1;
LABEL_77:
      v20 = v69;
LABEL_78:
      v29 = 1;
LABEL_79:
      v30 = v97;
      goto LABEL_80;
    }
    KeySizeFromFvekKeyType = FveHwAccelMapAlgorithmTypesToFveKeyType(a2[4], a2[5], &v70);
    if ( KeySizeFromFvekKeyType < 0 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_76;
      }
      v28 = 65;
      goto LABEL_75;
    }
    v32 = v70;
    KeySizeFromFvekKeyType = FveGetKeySizeFromFvekKeyType(v70, &v71);
    if ( KeySizeFromFvekKeyType < 0 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_76;
      }
      v28 = 66;
      goto LABEL_75;
    }
    v33 = (unsigned __int16)v71;
    KeySizeFromFvekKeyType = FveDatumKeyCreate((unsigned __int16)v32, v76, (unsigned __int16)v71, v80);
    if ( KeySizeFromFvekKeyType < 0 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_76;
      }
      v28 = 67;
      goto LABEL_75;
    }
    if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v34, v13) )
      v35 = FveFvekDataFromFvekDatum2(v6, v80[0]);
    else
      v35 = FveFvekDataFromFvekDatum(v6, v80[0]);
    KeySizeFromFvekKeyType = v35;
    if ( v35 < 0 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_76;
      }
      v28 = 68;
      goto LABEL_75;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids, v32, v33);
    }
    *(_QWORD *)&v93[16] = v81;
    v93[29] = v6;
    *(_QWORD *)&v93[4] = 0;
    v93[30] = 8193;
    KeySizeFromFvekKeyType = FveFilteredEncrypt(3, (int)v93, 0, -1, 0x10000, (PUCHAR)P, (PUCHAR)Source2, 0);
    if ( KeySizeFromFvekKeyType < 0 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_76;
      }
      v28 = 70;
      goto LABEL_75;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids);
    }
    v13 = v69;
    v36 = v33;
    v86 = v33;
    v29 = 1;
    LODWORD(v84) = 1;
    v37 = (*(_DWORD *)(v69 + 9928) & 0x800000) == 0;
    v85 = v76;
    if ( v37 )
    {
      v82 = 0;
      LODWORD(v82) = 1048577;
      *((_QWORD *)&v82 + 1) = *(_QWORD *)(v69 + 10736);
      KeySizeFromFvekKeyType = AccelInitializeCryptoWorkspace(&v82, &v75);
      if ( KeySizeFromFvekKeyType < 0 )
      {
        v38 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_129;
        }
        v39 = 72;
LABEL_128:
        WPP_SF_d(
          v38->AttachedDevice,
          v39,
          WPP_7f5e3a43786933c00401282694ab6ced_Traceguids,
          (unsigned int)KeySizeFromFvekKeyType);
LABEL_129:
        v5 = a1;
        v20 = v69;
        goto LABEL_79;
      }
      v91 = 0;
      *(_QWORD *)&v88 = 0;
      *((_QWORD *)&v88 + 1) = v75;
      v40 = *a2;
      v89 = 0;
      LODWORD(v89) = v40;
      *(_QWORD *)&v90 = v76;
      LODWORD(v88) = 3670017;
      DWORD2(v89) = 1;
      *((_QWORD *)&v90 + 1) = v36;
      LODWORD(v91) = v6;
      KeySizeFromFvekKeyType = AccelConfigureWorkspaceCryptoCapability(&v88);
      if ( KeySizeFromFvekKeyType < 0 )
      {
        v38 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_129;
        }
        v39 = 73;
        goto LABEL_128;
      }
      v13 = v69;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          74,
          WPP_7f5e3a43786933c00401282694ab6ced_Traceguids,
          (*(_DWORD *)(v13 + 9928) >> 23) & 1);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          75,
          WPP_7f5e3a43786933c00401282694ab6ced_Traceguids,
          (unsigned int)v6,
          0x10000);
      }
    }
    v41 = v6;
    if ( (unsigned int)v6 > 0x10000 )
    {
LABEL_179:
      v42 = v79;
    }
    else
    {
      while ( 2 )
      {
        v42 = v79;
        if ( v41 <= v79 )
        {
          v43 = 0;
          do
          {
            v44 = v43 + v41;
            if ( v43 + v41 <= 0x10000 )
              v45 = v41;
            else
              v45 = 0x10000 - v43;
            KeySizeFromFvekKeyType = FveHwAccelInitializeDescriptor(a1, 0, Entry);
            if ( KeySizeFromFvekKeyType < 0 )
            {
              v56 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v57 = 76;
LABEL_207:
                WPP_SF_d(
                  v56->AttachedDevice,
                  v57,
                  WPP_7f5e3a43786933c00401282694ab6ced_Traceguids,
                  (unsigned int)KeySizeFromFvekKeyType);
                goto LABEL_202;
              }
LABEL_255:
              LODWORD(v6) = v23;
              v30 = 0;
              v29 = 1;
              goto LABEL_190;
            }
            *(_QWORD *)&v92[2] = Entry;
            *(_QWORD *)&v92[6] = v75;
            *(_QWORD *)&v92[8] = (char *)P + v43;
            *(_QWORD *)&v92[10] = v45;
            *(_QWORD *)&v92[14] = v45;
            v46 = v43 % v23;
            *(_QWORD *)v92 = 6291457;
            *(_QWORD *)&v92[20] = v43 / v23;
            *(_QWORD *)&v92[4] = 0;
            *(_QWORD *)&v92[12] = (char *)Source1 + v43;
            *(_QWORD *)&v92[16] = 0;
            v47 = *(_QWORD *)(a1 + 8);
            *(_QWORD *)&v92[18] = 0;
            *(_QWORD *)&v92[22] = 0;
            if ( (*(_DWORD *)(v47 + 9928) & 0x800000) != 0 )
            {
              LODWORD(ullMultiplier) = v23;
              LOBYTE(v46) = 1;
              v48 = FveHwAccelSimPerformCrypto((int)a2, v46, (int)v92, 0, a2[4], a2[5], (__int64)&v84, ullMultiplier);
            }
            else
            {
              v48 = AccelSymmetricEncryptBuffer(v92, v46, v15, 0);
            }
            KeySizeFromFvekKeyType = v48;
            if ( v48 < 0 )
            {
              v54 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v55 = 77;
LABEL_201:
                WPP_SF_LLL(
                  v54->AttachedDevice,
                  v55,
                  WPP_7f5e3a43786933c00401282694ab6ced_Traceguids,
                  v43,
                  v45,
                  KeySizeFromFvekKeyType);
              }
              goto LABEL_202;
            }
            v43 += v41;
          }
          while ( v44 < 0x10000 );
          if ( RtlCompareMemory(Source1, Source2, 0x10000u) == 0x10000 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_LLL(
                WPP_GLOBAL_Control->AttachedDevice,
                79,
                WPP_7f5e3a43786933c00401282694ab6ced_Traceguids,
                v41,
                v23,
                0x10000);
            }
            v43 = 0;
            do
            {
              v49 = v43 + v41;
              if ( v43 + v41 <= 0x10000 )
                v45 = v41;
              else
                v45 = 0x10000 - v43;
              KeySizeFromFvekKeyType = FveHwAccelInitializeDescriptor(a1, 0, Entry);
              if ( KeySizeFromFvekKeyType < 0 )
              {
                v56 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v57 = 80;
                  goto LABEL_207;
                }
                goto LABEL_255;
              }
              *(_QWORD *)&v83[2] = Entry;
              *(_QWORD *)&v83[6] = v75;
              *(_QWORD *)&v83[8] = (char *)Source1 + v43;
              *(_QWORD *)&v83[12] = *(_QWORD *)&v83[8];
              *(_QWORD *)v83 = 6291457;
              *(_QWORD *)&v83[20] = v43 / v23;
              *(_QWORD *)&v83[4] = 0;
              *(_QWORD *)&v83[10] = v45;
              *(_QWORD *)&v83[14] = v45;
              v50 = *(_QWORD *)(a1 + 8);
              *(_QWORD *)&v83[16] = 0;
              *(_QWORD *)&v83[18] = 0;
              *(_QWORD *)&v83[22] = 0;
              if ( (*(_DWORD *)(v50 + 9928) & 0x800000) != 0 )
              {
                LODWORD(ullMultiplier) = v23;
                v51 = FveHwAccelSimPerformCrypto((int)a2, 0, 0, (int)v83, a2[4], a2[5], (__int64)&v84, ullMultiplier);
              }
              else
              {
                v51 = AccelSymmetricDecryptBuffer(v83);
              }
              KeySizeFromFvekKeyType = v51;
              if ( v51 < 0 )
              {
                v54 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v55 = 81;
                  goto LABEL_201;
                }
                goto LABEL_202;
              }
              v43 += v41;
            }
            while ( v49 < 0x10000 );
            if ( RtlCompareMemory(Source1, P, 0x10000u) == 0x10000 )
            {
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
              {
                LODWORD(v6) = v23;
              }
              else
              {
                LODWORD(v6) = v23;
                WPP_SF_LLL(
                  WPP_GLOBAL_Control->AttachedDevice,
                  83,
                  WPP_7f5e3a43786933c00401282694ab6ced_Traceguids,
                  v41,
                  v23,
                  0x10000);
              }
              v41 += v6;
              if ( v41 > 0x10000 )
              {
                v26 = a2;
                goto LABEL_179;
              }
              continue;
            }
            LOBYTE(v97) = 0;
            v52 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              v53 = 82;
              goto LABEL_196;
            }
            goto LABEL_202;
          }
          LOBYTE(v97) = 0;
          v52 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
LABEL_202:
            LODWORD(v6) = v23;
            goto LABEL_76;
          }
          v53 = 78;
LABEL_196:
          LODWORD(v6) = v23;
          WPP_SF_LLL(v52->AttachedDevice, v53, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids, v41, v23, 0x10000);
          goto LABEL_76;
        }
        break;
      }
      v26 = a2;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 84, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids);
    }
    v15 = 0x10000;
    if ( v42 < 0x10000 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_Lq(WPP_GLOBAL_Control->AttachedDevice, 85, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids, 0x10000, v42);
      }
      v29 = 1;
      v30 = 1;
LABEL_190:
      v5 = a1;
      goto LABEL_191;
    }
    v58 = P;
    KeySizeFromFvekKeyType = FveFilteredDecrypt(3, (int)v93, 0, -1, 0x10000, (PUCHAR)P, (PUCHAR)Source2, 0);
    if ( KeySizeFromFvekKeyType < 0 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_76;
      }
      v28 = 86;
      goto LABEL_75;
    }
    v5 = a1;
    KeySizeFromFvekKeyType = FveHwAccelInitializeDescriptor(a1, 0, Entry);
    if ( KeySizeFromFvekKeyType < 0 )
    {
      v59 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_77;
      }
      v60 = 87;
      v61 = (unsigned int)KeySizeFromFvekKeyType;
      goto LABEL_231;
    }
    v29 = 1;
    *(_QWORD *)&v83[2] = Entry;
    *(_QWORD *)&v83[6] = v75;
    *(_QWORD *)&v83[10] = 0x10000;
    *(_QWORD *)&v83[14] = 0x10000;
    v62 = *(_QWORD *)(a1 + 8);
    *(_QWORD *)&v83[8] = v58;
    v63 = Source1;
    *(_QWORD *)v83 = 6291457;
    *(_QWORD *)&v83[4] = 0;
    *(_QWORD *)&v83[12] = Source1;
    memset(&v83[16], 0, 32);
    if ( (*(_DWORD *)(v62 + 9928) & 0x800000) != 0 )
    {
      LODWORD(ullMultipliera) = v6;
      v64 = FveHwAccelSimPerformCrypto(0, 0, 0, (int)v83, v26[4], v26[5], (__int64)&v84, ullMultipliera);
    }
    else
    {
      v64 = AccelSymmetricDecryptBuffer(v83);
    }
    KeySizeFromFvekKeyType = v64;
    if ( v64 >= 0 )
    {
      if ( RtlCompareMemory(v63, Source2, 0x10000u) == 0x10000 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          HIDWORD(v66) = 0;
          WPP_SF_LLI(WPP_GLOBAL_Control->AttachedDevice, 90, v15, (unsigned int)v6);
        }
        v30 = 1;
        goto LABEL_191;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        HIDWORD(v66) = 0;
        WPP_SF_LLI(WPP_GLOBAL_Control->AttachedDevice, 89, v15, (unsigned int)v6);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        88,
        WPP_7f5e3a43786933c00401282694ab6ced_Traceguids,
        (unsigned int)v64);
    }
    v30 = 0;
LABEL_191:
    v20 = v69;
LABEL_80:
    *(_DWORD *)(v16 + 28) = KeySizeFromFvekKeyType;
    *(_BYTE *)(v16 + 24) = v30;
    if ( *(int *)(v16 + 28) >= 0 )
    {
      if ( v30 )
      {
        v7 = a2;
        goto LABEL_257;
      }
      v29 = 0;
    }
    v7 = a2;
    v31 = FVE_HW_ACCEL_CRYPTO_VERIFY_FAILED;
    if ( !v29 )
      v31 = FVE_HW_ACCEL_CRYPTO_MISMATCH;
    FveLogStatusEventWithData(v20, v5, v31);
    goto LABEL_257;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      57,
      WPP_7f5e3a43786933c00401282694ab6ced_Traceguids,
      CapabilityVerificationEntry);
  }
LABEL_45:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      92,
      WPP_7f5e3a43786933c00401282694ab6ced_Traceguids,
      CapabilityVerificationEntry,
      *v7);
  }
LABEL_262:
  if ( v75 )
  {
    AccelDestroyCryptoWorkspace();
    v75 = 0;
  }
  if ( v76 )
    ExFreePoolWithTag(v76, 0x68455646u);
  if ( P )
    ExFreePoolWithTag(P, 0x68455646u);
  if ( Source1 )
    ExFreePoolWithTag(Source1, 0x68455646u);
  if ( Source2 )
    ExFreePoolWithTag(Source2, 0x68455646u);
  if ( *(_QWORD *)v80 )
    FveDatumFree(*(_QWORD *)v80);
  if ( v81 )
    DeleteKey(v81);
  if ( Entry )
    ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v69 + 10712), Entry);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      93,
      WPP_7f5e3a43786933c00401282694ab6ced_Traceguids,
      CapabilityVerificationEntry);
  }
  return CapabilityVerificationEntry;
}

```

## disassembly

```asm
0x1400d1b04  mov     rax, rsp
0x1400d1b07  mov     [rax+18h], r8
0x1400d1b0b  mov     [rax+10h], rdx
0x1400d1b0f  mov     [rax+8], rcx
0x1400d1b13  push    rbp
0x1400d1b14  push    rbx
0x1400d1b15  push    rsi
0x1400d1b16  push    rdi
0x1400d1b17  push    r12
0x1400d1b19  push    r13
0x1400d1b1b  push    r14
0x1400d1b1d  push    r15
0x1400d1b1f  lea     rbp, [rax-218h]
0x1400d1b26  sub     rsp, 2D8h
0x1400d1b2d  mov     edi, [rdx+20h]
0x1400d1b30  xor     r12d, r12d
0x1400d1b33  mov     rsi, [rcx+8]
0x1400d1b37  mov     r13, rcx
0x1400d1b3a  mov     r14d, [rcx+51Ch]
0x1400d1b41  mov     r15, rdx
0x1400d1b44  mov     [rsp+40h], rsi
0x1400d1b49  mov     ecx, 10000h
0x1400d1b4e  lea     eax, [rdi-1]
0x1400d1b51  test    edi, eax
0x1400d1b53  jnz     short loc_1400D1B65
0x1400d1b55  test    edi, edi
0x1400d1b57  jz      short loc_1400D1B65
0x1400d1b59  add     edi, 0FFFFh
0x1400d1b5f  not     eax
0x1400d1b61  and     edi, eax
0x1400d1b63  jmp     short loc_1400D1B77
0x1400d1b65  xor     edx, edx
0x1400d1b67  mov     eax, ecx
0x1400d1b69  div     edi
0x1400d1b6b  test    edx, edx
0x1400d1b6d  jnz     short loc_1400D1B73
0x1400d1b6f  mov     edi, ecx
0x1400d1b71  jmp     short loc_1400D1B77
0x1400d1b73  sub     edi, edx
0x1400d1b75  add     edi, ecx
0x1400d1b77  mov     ebx, [r15+1Ch]
0x1400d1b7b  mov     rax, [r15+28h]
0x1400d1b7f  mov     [rbp+210h+var_280], rax
0x1400d1b83  mov     [rsp+310h+P], r12
0x1400d1b88  lea     eax, [rbx-1]
0x1400d1b8b  mov     [rsp+310h+Source1], r12
0x1400d1b90  mov     [rbp+210h+Source2], r12
0x1400d1b94  mov     [rsp+310h+var_298], r12
0x1400d1b99  mov     qword ptr [rbp+210h+var_278], r12
0x1400d1b9d  mov     [rbp+210h+var_270], r12
0x1400d1ba1  mov     [rsp+310h+var_2C4], r12w
0x1400d1ba7  mov     word ptr [rsp+310h+var_2C0], r12w
0x1400d1bad  test    ebx, eax
0x1400d1baf  jnz     short loc_1400D1BBE
0x1400d1bb1  test    ebx, ebx
0x1400d1bb3  jz      short loc_1400D1BBE
0x1400d1bb5  add     ebx, 3Fh ; '?'
0x1400d1bb8  not     eax
0x1400d1bba  and     ebx, eax
0x1400d1bbc  jmp     short loc_1400D1BD3
0x1400d1bbe  xor     edx, edx
0x1400d1bc0  lea     eax, [rdx+40h]
0x1400d1bc3  div     ebx
0x1400d1bc5  test    edx, edx
0x1400d1bc7  jnz     short loc_1400D1BCE
0x1400d1bc9  lea     ebx, [rdx+40h]
0x1400d1bcc  jmp     short loc_1400D1BD3
0x1400d1bce  sub     ebx, edx
0x1400d1bd0  add     ebx, 40h ; '@'
0x1400d1bd3  xor     edx, edx; Val
0x1400d1bd5  mov     [rsp+310h+Entry], r12
0x1400d1bda  lea     rcx, [rbp+210h+var_1A0]; void *
0x1400d1bde  lea     r8d, [rdx+60h]; Size
0x1400d1be2  call    memset
0x1400d1be7  xor     edx, edx; Val
0x1400d1be9  lea     rcx, [rbp+210h+var_250]; void *
0x1400d1bed  lea     r8d, [rdx+60h]; Size
0x1400d1bf1  call    memset
0x1400d1bf6  xorps   xmm1, xmm1
0x1400d1bf9  mov     [rbp+210h+arg_18], r12
0x1400d1c00  xorps   xmm0, xmm0
0x1400d1c03  mov     [rsp+310h+var_2A0], r12
0x1400d1c08  xor     eax, eax
0x1400d1c0a  mov     dword ptr [rbp+210h+var_1F0+4], r12d
0x1400d1c0e  movups  [rbp+210h+var_268], xmm0
0x1400d1c12  mov     [rbp+210h+var_1A8], rax
0x1400d1c16  movups  [rbp+210h+var_1D8], xmm1
0x1400d1c1a  mov     [rbp+210h+var_1DC], r12d
0x1400d1c1e  movups  [rbp+210h+var_1C8], xmm1
0x1400d1c22  movups  [rbp+210h+var_1B8], xmm1
0x1400d1c26  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d1c2d  lea     rdx, WPP_GLOBAL_Control
0x1400d1c34  cmp     rcx, rdx
0x1400d1c37  jz      short loc_1400D1C62
0x1400d1c39  test    dword ptr [rcx+2Ch], 400000h
0x1400d1c40  jz      short loc_1400D1C62
0x1400d1c42  cmp     byte ptr [rcx+29h], 5
0x1400d1c46  jb      short loc_1400D1C62
0x1400d1c48  mov     rcx, [rcx+18h]
0x1400d1c4c  lea     edx, [rax+36h]
0x1400d1c4f  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400d1c56  call    WPP_SF_
0x1400d1c5b  lea     rdx, WPP_GLOBAL_Control
0x1400d1c62  test    dword ptr [rsi+26C8h], 10000000h
0x1400d1c6c  jz      short loc_1400D1CA5
0x1400d1c6e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d1c75  cmp     rcx, rdx
0x1400d1c78  jz      short loc_1400D1CA1
0x1400d1c7a  test    dword ptr [rcx+2Ch], 400000h
0x1400d1c81  jz      short loc_1400D1CA1
0x1400d1c83  cmp     byte ptr [rcx+29h], 4
0x1400d1c87  jb      short loc_1400D1CA1
0x1400d1c89  mov     rcx, [rcx+18h]
0x1400d1c8d  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400d1c94  mov     edx, 37h ; '7'
0x1400d1c99  mov     r9d, r14d
0x1400d1c9c  call    WPP_SF_d
0x1400d1ca1  mov     [rbp+210h+var_280], r14
0x1400d1ca5  xor     edx, edx; Val
0x1400d1ca7  lea     rcx, [rbp+210h+var_140]; void *
0x1400d1cae  mov     r8d, 100h; Size
0x1400d1cb4  call    memset
0x1400d1cb9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d1cc0  lea     rax, WPP_GLOBAL_Control
0x1400d1cc7  cmp     rcx, rax
0x1400d1cca  jz      short loc_1400D1D0C
0x1400d1ccc  test    dword ptr [rcx+2Ch], 400000h
0x1400d1cd3  jz      short loc_1400D1D0C
0x1400d1cd5  cmp     byte ptr [rcx+29h], 4
0x1400d1cd9  jb      short loc_1400D1D0C
0x1400d1cdb  mov     eax, [rsi+26C8h]
0x1400d1ce1  mov     r9d, [r15]
0x1400d1ce4  mov     rcx, [rcx+18h]
0x1400d1ce8  shr     eax, 17h
0x1400d1ceb  and     eax, 1
0x1400d1cee  mov     dword ptr [rsp+310h+ullMultiplier], eax
0x1400d1cf2  mov     eax, [r15+14h]
0x1400d1cf6  mov     dword ptr [rsp+310h+var_2E0], r14d
0x1400d1cfb  mov     dword ptr [rsp+310h+var_2E8], eax
0x1400d1cff  mov     eax, [r15+10h]
0x1400d1d03  mov     [rsp+310h+var_2F0], eax
0x1400d1d07  call    WPP_SF_LddLd
0x1400d1d0c  lea     r9, [rbp+210h+arg_18]
0x1400d1d13  mov     [rbp+210h+var_288], r14d
0x1400d1d17  lea     r8, [rbp+210h+var_288]
0x1400d1d1b  mov     rdx, r15
0x1400d1d1e  mov     rcx, rsi
0x1400d1d21  call    FveHwAccelFindCapabilityVerificationEntry
0x1400d1d26  mov     ecx, 80000000h
0x1400d1d2b  mov     esi, eax
0x1400d1d2d  add     eax, ecx
0x1400d1d2f  test    ecx, eax
0x1400d1d31  jnz     short loc_1400D1D86
0x1400d1d33  cmp     esi, 0C0000225h
0x1400d1d39  jz      short loc_1400D1D86
0x1400d1d3b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d1d42  lea     rdi, WPP_GLOBAL_Control
0x1400d1d49  cmp     rcx, rdi
0x1400d1d4c  jz      loc_1400D1E61
0x1400d1d52  test    dword ptr [rcx+2Ch], 400000h
0x1400d1d59  jz      loc_1400D1E61
0x1400d1d5f  cmp     byte ptr [rcx+29h], 2
0x1400d1d63  jb      loc_1400D1E61
0x1400d1d69  mov     rcx, [rcx+18h]
0x1400d1d6d  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400d1d74  mov     edx, 39h ; '9'
0x1400d1d79  mov     r9d, esi
0x1400d1d7c  call    WPP_SF_d
0x1400d1d81  jmp     loc_1400D1E61
0x1400d1d86  test    esi, esi
0x1400d1d88  js      short loc_1400D1DF1
0x1400d1d8a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d1d91  lea     rax, WPP_GLOBAL_Control
0x1400d1d98  cmp     rcx, rax
0x1400d1d9b  jz      short loc_1400D1DE5
0x1400d1d9d  test    dword ptr [rcx+2Ch], 400000h
0x1400d1da4  jz      short loc_1400D1DD9
0x1400d1da6  cmp     byte ptr [rcx+29h], 4
0x1400d1daa  jb      short loc_1400D1DD9
0x1400d1dac  mov     r12, [rbp+210h+arg_18]
0x1400d1db3  mov     rcx, [rcx+18h]
0x1400d1db7  movzx   eax, byte ptr [r12+18h]
0x1400d1dbd  mov     r9d, [r12+10h]
0x1400d1dc2  mov     dword ptr [rsp+310h+var_2E8], eax
0x1400d1dc6  mov     eax, [r12+1Ch]
0x1400d1dcb  mov     [rsp+310h+var_2F0], eax
0x1400d1dcf  call    WPP_SF_Ldd
0x1400d1dd4  jmp     loc_1400D2DD0
0x1400d1dd9  mov     r12, [rbp+210h+arg_18]
0x1400d1de0  jmp     loc_1400D2DD0
0x1400d1de5  mov     r12, [rbp+210h+arg_18]
0x1400d1dec  jmp     loc_1400D2E1D
0x1400d1df1  mov     edx, 20h ; ' '
0x1400d1df6  mov     r8d, 68455646h
0x1400d1dfc  lea     ecx, [rdx+20h]
0x1400d1dff  call    cs:__imp_ExAllocatePool2
0x1400d1e06  nop     dword ptr [rax+rax+00h]
0x1400d1e0b  mov     r12, rax
0x1400d1e0e  test    rax, rax
0x1400d1e11  jnz     loc_1400D1EAC
0x1400d1e17  mov     esi, 0C000009Ah
0x1400d1e1c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d1e23  lea     rax, WPP_GLOBAL_Control
0x1400d1e2a  cmp     rcx, rax
0x1400d1e2d  jz      loc_1400D2E29
0x1400d1e33  test    dword ptr [rcx+2Ch], 400000h
0x1400d1e3a  jz      short loc_1400D1E5A
0x1400d1e3c  cmp     byte ptr [rcx+29h], 2
0x1400d1e40  jb      short loc_1400D1E5A
0x1400d1e42  mov     rcx, [rcx+18h]
0x1400d1e46  lea     edx, [r12+3Bh]
0x1400d1e4b  mov     r9d, esi
0x1400d1e4e  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400d1e55  call    WPP_SF_d
0x1400d1e5a  lea     rdi, WPP_GLOBAL_Control
0x1400d1e61  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d1e68  cmp     rcx, rdi
0x1400d1e6b  jz      loc_1400D2E29
0x1400d1e71  test    dword ptr [rcx+2Ch], 400000h
0x1400d1e78  jz      loc_1400D2E29
0x1400d1e7e  cmp     byte ptr [rcx+29h], 2
0x1400d1e82  jb      loc_1400D2E29
0x1400d1e88  mov     eax, [r15]
0x1400d1e8b  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400d1e92  mov     rcx, [rcx+18h]
0x1400d1e96  mov     edx, 5Ch ; '\'
0x1400d1e9b  mov     r9d, esi
0x1400d1e9e  mov     [rsp+310h+var_2F0], eax
0x1400d1ea2  call    WPP_SF_Dd
0x1400d1ea7  jmp     loc_1400D2E29
0x1400d1eac  xorps   xmm0, xmm0
0x1400d1eaf  movups  xmmword ptr [rax], xmm0
0x1400d1eb2  movups  xmmword ptr [rax+10h], xmm0
0x1400d1eb6  mov     rax, [rsp+40h]
0x1400d1ebb  add     rax, 2A08h
0x1400d1ec1  mov     rcx, [rax+8]
0x1400d1ec5  cmp     [rcx], rax
0x1400d1ec8  jz      short loc_1400D1ED1
0x1400d1eca  mov     ecx, 3
0x1400d1ecf  int     29h; Win8: RtlFailFast(ecx)
0x1400d1ed1  mov     [r12], rax
0x1400d1ed5  mov     [r12+8], rcx
0x1400d1eda  mov     [rcx], r12
0x1400d1edd  mov     [rax+8], r12
0x1400d1ee1  mov     eax, [r15]
0x1400d1ee4  mov     [r12+10h], eax
0x1400d1ee9  mov     eax, [rbp+210h+var_288]
0x1400d1eec  mov     [r12+14h], eax
0x1400d1ef1  mov     byte ptr [rbp+210h+arg_18], 0
0x1400d1ef8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d1eff  lea     rax, WPP_GLOBAL_Control
0x1400d1f06  cmp     rcx, rax
0x1400d1f09  jz      short loc_1400D1F32
0x1400d1f0b  test    dword ptr [rcx+2Ch], 400000h
0x1400d1f12  jz      short loc_1400D1F32
0x1400d1f14  cmp     byte ptr [rcx+29h], 4
0x1400d1f18  jb      short loc_1400D1F32
0x1400d1f1a  mov     r9d, [r15]
0x1400d1f1d  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400d1f24  mov     rcx, [rcx+18h]
0x1400d1f28  mov     edx, 3Ch ; '<'
0x1400d1f2d  call    WPP_SF_d
0x1400d1f32  mov     r8d, 68455646h
0x1400d1f38  mov     edx, ebx
0x1400d1f3a  mov     ecx, 40h ; '@'
0x1400d1f3f  mov     esi, ebx
0x1400d1f41  call    cs:__imp_ExAllocatePool2
0x1400d1f48  nop     dword ptr [rax+rax+00h]
0x1400d1f4d  mov     r8d, 68455646h
0x1400d1f53  mov     rdx, rdi
0x1400d1f56  mov     ecx, 40h ; '@'
0x1400d1f5b  mov     [rsp+310h+var_298], rax
0x1400d1f60  call    cs:__imp_ExAllocatePool2
0x1400d1f67  nop     dword ptr [rax+rax+00h]
0x1400d1f6c  mov     r8d, 68455646h
0x1400d1f72  mov     rdx, rdi
0x1400d1f75  mov     ecx, 40h ; '@'
0x1400d1f7a  mov     [rsp+310h+P], rax
0x1400d1f7f  call    cs:__imp_ExAllocatePool2
0x1400d1f86  nop     dword ptr [rax+rax+00h]
0x1400d1f8b  mov     r8d, 68455646h
0x1400d1f91  mov     rdx, rdi
0x1400d1f94  mov     ecx, 40h ; '@'
0x1400d1f99  mov     [rsp+310h+Source1], rax
0x1400d1f9e  call    cs:__imp_ExAllocatePool2
0x1400d1fa5  nop     dword ptr [rax+rax+00h]
0x1400d1faa  xor     ecx, ecx
0x1400d1fac  mov     [rbp+210h+Source2], rax
0x1400d1fb0  cmp     [rsp+310h+var_298], rcx
0x1400d1fb5  jz      loc_1400D2D77
0x1400d1fbb  cmp     [rsp+310h+P], rcx
0x1400d1fc0  jz      loc_1400D2D77
0x1400d1fc6  cmp     [rsp+310h+Source1], rcx
0x1400d1fcb  jz      loc_1400D2D77
0x1400d1fd1  test    rax, rax
0x1400d1fd4  jz      loc_1400D2D77
0x1400d1fda  mov     rdi, [rsp+40h]
0x1400d1fdf  mov     rcx, [rdi+29D8h]; Lookaside
0x1400d1fe6  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400d1fed  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
