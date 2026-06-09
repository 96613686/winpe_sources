# FveHwAccelVerifyCryptoCapability

- ea: `0x1400cce60`
- end: `0x1400cdcff`
- name: `FveHwAccelVerifyCryptoCapability`
- size: `3743`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400cca48`

## callees

- `0x140005e50`
- `0x140008288`
- `0x140008c10`
- `0x140008c60`
- `0x140008dc0`
- `0x140008e44`
- `0x14000c85c`
- `0x14000d500`
- `0x1400143d0`
- `0x140016344`
- `0x1400218c0`
- `0x140021d00`
- `0x1400266e0`
- `0x140061b54`
- `0x14009df90`
- `0x1400b5c18`
- `0x1400cb9a8`
- `0x1400cc200`
- `0x1400cc30c`
- `0x1400cc5f0`
- `0x1400cc664`
- `0x1400cce60`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400cd662`
- `ntoskrnl!RtlCompareMemory` at `0x1400cd773`
- `ntoskrnl!RtlCompareMemory` at `0x1400cdc58`
- `ntoskrnl!RtlCompareMemory` at `0x1400cd662`
- `ntoskrnl!RtlCompareMemory` at `0x1400cd773`
- `ntoskrnl!RtlCompareMemory` at `0x1400cdc58`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400cd137`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400cd137`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cd8d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cd8ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cd90c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cd8d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cd8ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cd90c`
- `ntoskrnl!ExAllocatePool2` at `0x1400cd00d`
- `ntoskrnl!ExAllocatePool2` at `0x1400cd0bc`
- `ntoskrnl!ExAllocatePool2` at `0x1400cd0dc`
- `ntoskrnl!ExAllocatePool2` at `0x1400cd0fe`
- `ntoskrnl!ExAllocatePool2` at `0x1400cd00d`
- `ntoskrnl!ExAllocatePool2` at `0x1400cd0bc`
- `ntoskrnl!ExAllocatePool2` at `0x1400cd0dc`
- `ntoskrnl!ExAllocatePool2` at `0x1400cd0fe`
- `ext-ms-win-accel-api-km-l1-1-1!AccelDestroyCryptoWorkspace` at `0x1400cd8b3`
- `ext-ms-win-accel-api-km-l1-1-1!AccelDestroyCryptoWorkspace` at `0x1400cd8b3`
- `ext-ms-win-accel-api-km-l1-1-1!AccelSymmetricDecryptBuffer` at `0x1400cd739`
- `ext-ms-win-accel-api-km-l1-1-1!AccelSymmetricDecryptBuffer` at `0x1400cdbfc`
- `ext-ms-win-accel-api-km-l1-1-1!AccelSymmetricDecryptBuffer` at `0x1400cd739`
- `ext-ms-win-accel-api-km-l1-1-1!AccelSymmetricDecryptBuffer` at `0x1400cdbfc`
- `ext-ms-win-accel-api-km-l1-1-1!AccelSymmetricEncryptBuffer` at `0x1400cd62b`
- `ext-ms-win-accel-api-km-l1-1-1!AccelSymmetricEncryptBuffer` at `0x1400cd62b`
- `ext-ms-win-accel-api-km-l1-1-1!AccelConfigureWorkspaceCryptoCapability` at `0x1400cd4e2`
- `ext-ms-win-accel-api-km-l1-1-1!AccelConfigureWorkspaceCryptoCapability` at `0x1400cd4e2`
- `ext-ms-win-accel-api-km-l1-1-1!AccelInitializeCryptoWorkspace` at `0x1400cd454`
- `ext-ms-win-accel-api-km-l1-1-1!AccelInitializeCryptoWorkspace` at `0x1400cd454`

## pseudocode

```c
__int64 __fastcall FveHwAccelVerifyCryptoCapability(__int64 a1, __int64 a2, PUCHAR *a3)
{
  __int64 v3; // rbx
  PUCHAR v4; // r14
  _DWORD *v5; // rsi
  void *v7; // r15
  __int64 v8; // rdi
  unsigned __int64 v9; // r13
  PVOID v10; // r12
  unsigned int CapabilityVerificationEntry; // ebx
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  __int64 Pool2; // rax
  __int64 v15; // rdi
  __int64 *v16; // rcx
  UCHAR *v17; // rbx
  void *v18; // rax
  int v19; // r14d
  int v20; // edi
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  __int64 v22; // rdx
  __int64 v23; // r9
  __int64 v24; // r8
  unsigned __int64 v25; // rax
  UCHAR *v26; // rdi
  struct _DEVICE_OBJECT *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r9
  int KeySizeFromFvekKeyType; // eax
  PDEVICE_OBJECT v31; // rcx
  __int64 v32; // rcx
  int v33; // eax
  __int64 v34; // rdx
  unsigned int v35; // ebx
  bool v36; // zf
  int v37; // eax
  unsigned int v38; // r14d
  unsigned int v39; // ebx
  unsigned int v40; // r15d
  unsigned int v41; // esi
  int v42; // eax
  __int64 v43; // r8
  unsigned __int64 v44; // rdx
  __int64 v45; // rax
  int v46; // eax
  __int64 v47; // rdx
  unsigned int v48; // r15d
  __int64 v49; // r8
  __int64 v50; // rax
  int v51; // eax
  UCHAR *v52; // rbx
  PDEVICE_OBJECT v53; // rcx
  __int64 v54; // rdx
  __int64 v55; // r9
  PDEVICE_OBJECT v56; // rcx
  __int64 v57; // rdx
  PUCHAR v58; // rbx
  char v59; // di
  __int64 *v60; // r8
  PDEVICE_OBJECT v62; // rcx
  __int64 v63; // rdx
  int v64; // eax
  __int64 v65; // rdx
  int v66; // eax
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // r9
  __int64 v70; // rax
  int v71; // eax
  PDEVICE_OBJECT v72; // rcx
  PUCHAR v73; // [rsp+30h] [rbp-D0h]
  PUCHAR v74; // [rsp+30h] [rbp-D0h]
  PVOID v75; // [rsp+40h] [rbp-C0h] BYREF
  char v76; // [rsp+48h] [rbp-B8h]
  void *Source1; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v78[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v79; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v80; // [rsp+60h] [rbp-A0h]
  PUCHAR v81; // [rsp+68h] [rbp-98h] BYREF
  __int64 v82; // [rsp+70h] [rbp-90h] BYREF
  void *Source2; // [rsp+78h] [rbp-88h]
  int v84[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v85; // [rsp+88h] [rbp-78h]
  PVOID P; // [rsp+90h] [rbp-70h]
  __int64 v87; // [rsp+98h] [rbp-68h]
  __int128 v88; // [rsp+A0h] [rbp-60h] BYREF
  int v89[24]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v90; // [rsp+110h] [rbp+10h] BYREF
  UCHAR *v91; // [rsp+118h] [rbp+18h]
  int v92; // [rsp+120h] [rbp+20h]
  int v93; // [rsp+124h] [rbp+24h]
  __int128 v94; // [rsp+128h] [rbp+28h] BYREF
  __int128 v95; // [rsp+138h] [rbp+38h]
  __int128 v96; // [rsp+148h] [rbp+48h]
  __int64 v97; // [rsp+158h] [rbp+58h]
  __int64 v98; // [rsp+160h] [rbp+60h]
  PUCHAR *v99; // [rsp+168h] [rbp+68h]
  int v100[24]; // [rsp+170h] [rbp+70h] BYREF
  int v101[64]; // [rsp+1D0h] [rbp+D0h] BYREF
  UCHAR pbBuffer[64]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v3 = *(_QWORD *)(a1 + 8);
  v4 = 0;
  v99 = a3;
  v5 = (_DWORD *)a2;
  v85 = a2;
  v80 = a1;
  v87 = v3;
  Source2 = 0;
  v7 = 0;
  memset(pbBuffer, 0, sizeof(pbBuffer));
  v8 = 0;
  v78[0] = 0;
  v79 = 0;
  *(_QWORD *)v84 = 0;
  P = 0;
  memset(v101, 0, sizeof(v101));
  v9 = *(unsigned int *)(a1 + 1308);
  v10 = 0;
  memset(v100, 0, sizeof(v100));
  memset(v89, 0, sizeof(v89));
  v81 = 0;
  v97 = 0;
  v82 = 0;
  v88 = 0;
  HIDWORD(v90) = 0;
  v94 = 0;
  v93 = 0;
  v95 = 0;
  v96 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids);
  }
  LODWORD(v75) = v9;
  CapabilityVerificationEntry = FveHwAccelFindCapabilityVerificationEntry(v3, v5, &v75, &v81);
  if ( (int)(CapabilityVerificationEntry + 0x80000000) >= 0 && CapabilityVerificationEntry != -1073741275 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v13 = 40;
LABEL_11:
      WPP_SF_d(v12->AttachedDevice, v13, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids, CapabilityVerificationEntry);
      goto LABEL_123;
    }
    goto LABEL_123;
  }
  if ( (CapabilityVerificationEntry & 0x80000000) == 0 )
  {
    v58 = v81;
    goto LABEL_122;
  }
  Pool2 = ExAllocatePool2(64, 32, 809850438);
  v98 = Pool2;
  if ( Pool2 )
  {
    v15 = v87;
    *(_OWORD *)Pool2 = 0;
    *(_OWORD *)(Pool2 + 16) = 0;
    v16 = *(__int64 **)(v15 + 10504);
    if ( *v16 != v15 + 10496 )
      __fastfail(3u);
    *(_QWORD *)Pool2 = v15 + 10496;
    *(_QWORD *)(Pool2 + 8) = v16;
    *v16 = Pool2;
    *(_QWORD *)(v15 + 10504) = Pool2;
    *(_DWORD *)(Pool2 + 16) = *v5;
    *(_DWORD *)(Pool2 + 20) = (_DWORD)v75;
    v76 = 0;
    v81 = (PUCHAR)ExAllocatePool2(72, 0x10000, 809850438);
    v17 = v81;
    Source1 = (void *)ExAllocatePool2(72, 0x10000, 809850438);
    v7 = Source1;
    v18 = (void *)ExAllocatePool2(72, 0x10000, 809850438);
    Source2 = v18;
    v19 = 1;
    if ( v17 && v7 && v18 )
    {
      v75 = ExAllocateFromNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v15 + 10456));
      v10 = v75;
      if ( !v75 )
      {
        v20 = -1073741670;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
          v22 = 43;
          v23 = 3221225626LL;
LABEL_28:
          WPP_SF_d(AttachedDevice, v22, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids, v23);
          goto LABEL_115;
        }
        goto LABEL_115;
      }
      v24 = 0;
      do
      {
        v25 = (unsigned int)v24;
        v26 = &v17[v24];
        v24 = (unsigned int)(v9 + v24);
        memset64(v26, v25, v9 >> 3);
      }
      while ( (unsigned int)v24 < 0x10000 );
      v20 = FveRandomDataCallback(pbBuffer, 0x40u);
      if ( v20 < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_114;
        }
        v27 = WPP_GLOBAL_Control->AttachedDevice;
        v28 = 44;
        v29 = (unsigned int)v20;
        goto LABEL_36;
      }
      KeySizeFromFvekKeyType = FveHwAccelMapAlgorithmTypesToFveKeyType((unsigned int)v5[4], (unsigned int)v5[5], v78);
      v20 = KeySizeFromFvekKeyType;
      if ( KeySizeFromFvekKeyType < 0 )
      {
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_114;
        }
        v28 = 45;
        goto LABEL_42;
      }
      KeySizeFromFvekKeyType = FveGetKeySizeFromFvekKeyType(v78[0], &v79);
      v20 = KeySizeFromFvekKeyType;
      if ( KeySizeFromFvekKeyType < 0 )
      {
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_114;
        }
        v28 = 46;
        goto LABEL_42;
      }
      KeySizeFromFvekKeyType = FveDatumKeyCreate(v78[0], pbBuffer, v79, v84);
      v20 = KeySizeFromFvekKeyType;
      if ( KeySizeFromFvekKeyType < 0 )
      {
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_114;
        }
        v28 = 47;
        goto LABEL_42;
      }
      if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v32) )
        v33 = FveFvekDataFromFvekDatum2(v9, v84[0]);
      else
        v33 = FveFvekDataFromFvekDatum(v9, v84[0]);
      v20 = v33;
      if ( v33 < 0 )
      {
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_114;
        }
        v28 = 48;
        v29 = (unsigned int)v33;
        goto LABEL_43;
      }
      *(_QWORD *)&v101[16] = P;
      v101[29] = v9;
      KeySizeFromFvekKeyType = FveFilteredEncrypt(3, (int)v101, v9, -1, 0x10000, v17, (PUCHAR)Source2, 0);
      v20 = KeySizeFromFvekKeyType;
      if ( KeySizeFromFvekKeyType < 0 )
      {
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_114;
        }
        v28 = 49;
        goto LABEL_42;
      }
      v35 = v79;
      LODWORD(v90) = 1;
      v91 = pbBuffer;
      v36 = (*(_DWORD *)(v87 + 9680) & 0x800000) == 0;
      v92 = v79;
      if ( v36 )
      {
        v88 = 0;
        LODWORD(v88) = 1048577;
        *((_QWORD *)&v88 + 1) = *(_QWORD *)(v87 + 10472);
        KeySizeFromFvekKeyType = AccelInitializeCryptoWorkspace(&v88, &v82);
        v20 = KeySizeFromFvekKeyType;
        if ( KeySizeFromFvekKeyType < 0 )
        {
          v31 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_114;
          }
          v28 = 50;
          goto LABEL_42;
        }
        v97 = 0;
        *(_QWORD *)&v94 = 0;
        *((_QWORD *)&v94 + 1) = v82;
        v37 = *v5;
        v95 = 0;
        LODWORD(v95) = v37;
        *(_QWORD *)&v96 = pbBuffer;
        LODWORD(v94) = 3670017;
        DWORD2(v95) = 1;
        *((_QWORD *)&v96 + 1) = v35;
        LODWORD(v97) = v9;
        KeySizeFromFvekKeyType = AccelConfigureWorkspaceCryptoCapability(&v94);
        v20 = KeySizeFromFvekKeyType;
        if ( KeySizeFromFvekKeyType < 0 )
        {
          v31 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_114;
          }
          v28 = 51;
LABEL_42:
          v29 = (unsigned int)KeySizeFromFvekKeyType;
LABEL_43:
          v27 = v31->AttachedDevice;
LABEL_36:
          WPP_SF_d(v27, v28, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids, v29);
LABEL_114:
          v10 = v75;
          goto LABEL_115;
        }
      }
      v38 = v9;
      if ( (unsigned int)v9 <= 0x10000 )
      {
        while ( 2 )
        {
          v39 = 0;
          do
          {
            v40 = v39 + v38;
            v41 = 0x10000 - v39;
            if ( v39 + v38 <= 0x10000 )
              v41 = v38;
            v42 = FveHwAccelInitializeDescriptor(v80, v34, v75);
            v20 = v42;
            if ( v42 < 0 )
            {
              v62 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v63 = 52;
LABEL_146:
                WPP_SF_d(v62->AttachedDevice, v63, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids, (unsigned int)v42);
              }
              goto LABEL_112;
            }
            *(_QWORD *)&v100[2] = v75;
            *(_QWORD *)&v100[6] = v82;
            *(_QWORD *)&v100[8] = &v81[v39];
            *(_QWORD *)v100 = 6291457;
            *(_QWORD *)&v100[12] = (char *)Source1 + v39;
            *(_QWORD *)&v100[4] = 0;
            v44 = (v39 + (unsigned int)v9) % v9;
            *(_QWORD *)&v100[10] = v41;
            *(_QWORD *)&v100[20] = (v39 + (unsigned int)v9) / v9;
            *(_QWORD *)&v100[14] = v41;
            *(_QWORD *)&v100[16] = 0;
            *(_QWORD *)&v100[18] = 0;
            v45 = *(_QWORD *)(v80 + 8);
            *(_QWORD *)&v100[22] = 0;
            if ( (*(_DWORD *)(v45 + 9680) & 0x800000) != 0 )
            {
              LODWORD(v73) = v9;
              LOBYTE(v44) = 1;
              v46 = FveHwAccelSimPerformCrypto(v41, v44, (int)v100, 0, v85, (__int64)&v90, (ULONGLONG)v73);
            }
            else
            {
              v46 = AccelSymmetricEncryptBuffer(v100, v44, v43, 0);
            }
            v20 = v46;
            if ( v46 < 0 )
            {
              v56 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v57 = 53;
LABEL_111:
                WPP_SF_LLL(v56->AttachedDevice, v57, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids, v39, v41, v20);
              }
LABEL_112:
              v7 = Source1;
              goto LABEL_113;
            }
            v39 += v38;
          }
          while ( v40 < 0x10000 );
          v7 = Source1;
          if ( RtlCompareMemory(Source1, Source2, 0x10000u) == 0x10000 )
          {
            v39 = 0;
            do
            {
              v48 = v39 + v38;
              v41 = 0x10000 - v39;
              if ( v39 + v38 <= 0x10000 )
                v41 = v38;
              v42 = FveHwAccelInitializeDescriptor(v80, v47, v75);
              v20 = v42;
              if ( v42 < 0 )
              {
                v62 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v63 = 55;
                  goto LABEL_146;
                }
                goto LABEL_112;
              }
              *(_QWORD *)&v89[2] = v75;
              *(_QWORD *)&v89[6] = v82;
              *(_QWORD *)v89 = 6291457;
              *(_QWORD *)&v89[10] = v41;
              *(_QWORD *)&v89[14] = v41;
              *(_QWORD *)&v89[4] = 0;
              *(_QWORD *)&v89[20] = (v39 + (unsigned int)v9) / v9;
              *(_QWORD *)&v89[8] = (char *)Source1 + v39;
              *(_QWORD *)&v89[12] = *(_QWORD *)&v89[8];
              *(_QWORD *)&v89[16] = 0;
              v50 = *(_QWORD *)(v80 + 8);
              *(_QWORD *)&v89[18] = 0;
              *(_QWORD *)&v89[22] = 0;
              if ( (*(_DWORD *)(v50 + 9680) & 0x800000) != 0 )
              {
                LODWORD(v73) = v9;
                v51 = FveHwAccelSimPerformCrypto(
                        v39 + (unsigned int)Source1,
                        0,
                        0,
                        (int)v89,
                        v85,
                        (__int64)&v90,
                        (ULONGLONG)v73);
              }
              else
              {
                v51 = AccelSymmetricDecryptBuffer(v89, (v39 + (unsigned int)v9) % v9, v49, 0);
              }
              v20 = v51;
              if ( v51 < 0 )
              {
                v56 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v57 = 56;
                  goto LABEL_111;
                }
                goto LABEL_112;
              }
              v39 += v38;
            }
            while ( v48 < 0x10000 );
            v52 = v81;
            v7 = Source1;
            if ( RtlCompareMemory(Source1, v81, 0x10000u) == 0x10000 )
            {
              v38 += v9;
              if ( v38 <= 0x10000 )
                continue;
              v5 = (_DWORD *)v85;
              goto LABEL_160;
            }
            v76 = 0;
            v53 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              v54 = 57;
              goto LABEL_105;
            }
            goto LABEL_113;
          }
          break;
        }
        v76 = 0;
        v53 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
LABEL_113:
          v19 = 1;
          goto LABEL_114;
        }
        v54 = 54;
LABEL_105:
        v55 = 3221225473LL;
LABEL_106:
        WPP_SF_d(v53->AttachedDevice, v54, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids, v55);
        goto LABEL_113;
      }
      v52 = v81;
LABEL_160:
      v64 = FveFilteredDecrypt(3, (int)v101, v9, -1, 0x10000, v52, (PUCHAR)Source2, 0);
      v20 = v64;
      if ( v64 < 0 )
      {
        v53 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_113;
        }
        v54 = 58;
        v55 = (unsigned int)v64;
        goto LABEL_106;
      }
      v10 = v75;
      v66 = FveHwAccelInitializeDescriptor(v80, v65, v75);
      v20 = v66;
      if ( v66 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            59,
            WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids,
            (unsigned int)v66);
        }
        v19 = 1;
        goto LABEL_115;
      }
      v19 = 1;
      *(_QWORD *)&v89[6] = v82;
      *(_QWORD *)&v89[8] = v52;
      *(_QWORD *)v89 = 6291457;
      *(_QWORD *)&v89[2] = v10;
      v70 = *(_QWORD *)(v80 + 8);
      *(_QWORD *)&v89[4] = 0;
      *(_QWORD *)&v89[10] = 0x10000;
      *(_QWORD *)&v89[12] = v7;
      *(_QWORD *)&v89[14] = 0x10000;
      *(_QWORD *)&v89[16] = 0;
      *(_QWORD *)&v89[18] = 0;
      *(_QWORD *)&v89[20] = 1;
      *(_QWORD *)&v89[22] = 0;
      if ( (*(_DWORD *)(v70 + 9680) & 0x800000) != 0 )
      {
        LODWORD(v74) = v9;
        v71 = FveHwAccelSimPerformCrypto(0, 0, 0, (int)v89, (__int64)v5, (__int64)&v90, (ULONGLONG)v74);
      }
      else
      {
        v71 = AccelSymmetricDecryptBuffer(v89, v67, v68, v69);
      }
      v20 = v71;
      if ( v71 >= 0 )
      {
        if ( RtlCompareMemory(v7, Source2, 0x10000u) == 0x10000 )
        {
          v76 = 1;
          goto LABEL_115;
        }
        v76 = 0;
        v72 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
LABEL_115:
          v58 = (PUCHAR)v98;
          *(_DWORD *)(v98 + 28) = v20;
          v59 = v76;
          v58[24] = v76;
          if ( *((int *)v58 + 7) >= 0 )
          {
            if ( v59 )
            {
LABEL_121:
              v4 = v81;
              v8 = *(_QWORD *)v84;
LABEL_122:
              *v99 = v58;
              CapabilityVerificationEntry = 0;
              goto LABEL_123;
            }
            v19 = 0;
          }
          v60 = FVE_HW_ACCEL_CRYPTO_VERIFY_FAILED;
          if ( !v19 )
            v60 = FVE_HW_ACCEL_CRYPTO_MISMATCH;
          FveLogStatusEventWithData(v87, v80, v60);
          goto LABEL_121;
        }
        v22 = 61;
        v23 = 3221225473LL;
      }
      else
      {
        v72 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_115;
        }
        v22 = 60;
        v23 = (unsigned int)v71;
      }
    }
    else
    {
      v20 = -1073741670;
      v72 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_115;
      }
      v22 = 42;
      v23 = 3221225626LL;
    }
    AttachedDevice = v72->AttachedDevice;
    goto LABEL_28;
  }
  CapabilityVerificationEntry = -1073741670;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v13 = 41;
    goto LABEL_11;
  }
LABEL_123:
  if ( v82 )
  {
    AccelDestroyCryptoWorkspace();
    v82 = 0;
  }
  if ( v4 )
    ExFreePoolWithTag(v4, 0x30455646u);
  if ( v7 )
    ExFreePoolWithTag(v7, 0x30455646u);
  if ( Source2 )
    ExFreePoolWithTag(Source2, 0x30455646u);
  if ( v8 )
    FveDatumFree(v8);
  if ( P )
    DeleteKey(P);
  if ( v10 )
    FveHwAccelReleaseDescriptor(v80, v10);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      62,
      WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids,
      CapabilityVerificationEntry);
  }
  return CapabilityVerificationEntry;
}

```

## disassembly

```asm
0x1400cce60  mov     [rsp-8+arg_18], rbx
0x1400cce65  push    rbp
0x1400cce66  push    rsi
0x1400cce67  push    rdi
0x1400cce68  push    r12
0x1400cce6a  push    r13
0x1400cce6c  push    r14
0x1400cce6e  push    r15
0x1400cce70  lea     rbp, [rsp-220h]
0x1400cce78  sub     rsp, 320h
0x1400cce7f  mov     rax, cs:__security_cookie
0x1400cce86  xor     rax, rsp
0x1400cce89  mov     [rbp+250h+var_40], rax
0x1400cce90  mov     rbx, [rcx+8]
0x1400cce94  xor     r14d, r14d
0x1400cce97  mov     [rbp+250h+var_1E8], r8
0x1400cce9b  mov     rsi, rdx
0x1400cce9e  mov     [rbp+250h+var_2C8], rdx
0x1400ccea2  mov     r13, rcx
0x1400ccea5  mov     [rsp+350h+var_2F0], rcx
0x1400cceaa  xor     edx, edx; Val
0x1400cceac  lea     r8d, [r14+40h]; Size
0x1400cceb0  mov     [rbp+250h+var_2B8], rbx
0x1400cceb4  lea     rcx, [rbp+250h+pbBuffer]; void *
0x1400ccebb  mov     [rsp+350h+Source2], r14
0x1400ccec0  xor     r15d, r15d
0x1400ccec3  call    memset
0x1400ccec8  xor     eax, eax
0x1400cceca  lea     rcx, [rbp+250h+var_180]; void *
0x1400cced1  xor     edi, edi
0x1400cced3  mov     [rsp+350h+var_2F8], ax
0x1400cced8  xor     edx, edx; Val
0x1400cceda  mov     [rsp+350h+var_2F4], ax
0x1400ccedf  mov     r8d, 100h; Size
0x1400ccee5  mov     qword ptr [rbp+250h+var_2D0], rdi
0x1400ccee9  mov     [rbp+250h+P], rdi
0x1400cceed  call    memset
0x1400ccef2  mov     r13d, [r13+51Ch]
0x1400ccef9  lea     r8d, [r14+60h]; Size
0x1400ccefd  xor     edx, edx; Val
0x1400cceff  lea     rcx, [rbp+250h+var_1E0]; void *
0x1400ccf03  xor     r12d, r12d
0x1400ccf06  call    memset
0x1400ccf0b  xor     edx, edx; Val
0x1400ccf0d  lea     r8d, [r14+60h]; Size
0x1400ccf11  lea     rcx, [rbp+250h+var_2A0]; void *
0x1400ccf15  call    memset
0x1400ccf1a  xor     ecx, ecx
0x1400ccf1c  xorps   xmm1, xmm1
0x1400ccf1f  xor     eax, eax
0x1400ccf21  mov     [rsp+350h+var_2E8], rcx
0x1400ccf26  xorps   xmm0, xmm0
0x1400ccf29  mov     [rbp+250h+var_1F8], rax
0x1400ccf2d  mov     [rsp+350h+var_2E0], rcx
0x1400ccf32  movups  [rbp+250h+var_2B0], xmm0
0x1400ccf36  mov     dword ptr [rbp+250h+var_240+4], ecx
0x1400ccf39  movups  [rbp+250h+var_228], xmm1
0x1400ccf3d  mov     [rbp+250h+var_22C], ecx
0x1400ccf40  movups  [rbp+250h+var_218], xmm1
0x1400ccf44  movups  [rbp+250h+var_208], xmm1
0x1400ccf48  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ccf4f  lea     rax, WPP_GLOBAL_Control
0x1400ccf56  cmp     rcx, rax
0x1400ccf59  jz      short loc_1400CCF7D
0x1400ccf5b  test    dword ptr [rcx+2Ch], 400000h
0x1400ccf62  jz      short loc_1400CCF7D
0x1400ccf64  cmp     byte ptr [rcx+29h], 5
0x1400ccf68  jb      short loc_1400CCF7D
0x1400ccf6a  mov     rcx, [rcx+18h]
0x1400ccf6e  lea     edx, [rdi+27h]
0x1400ccf71  lea     r8, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids
0x1400ccf78  call    WPP_SF_
0x1400ccf7d  lea     r9, [rsp+350h+var_2E8]
0x1400ccf82  mov     dword ptr [rsp+350h+var_310], r13d
0x1400ccf87  lea     r8, [rsp+350h+var_310]
0x1400ccf8c  mov     rdx, rsi
0x1400ccf8f  mov     rcx, rbx
0x1400ccf92  call    FveHwAccelFindCapabilityVerificationEntry
0x1400ccf97  mov     ecx, 80000000h
0x1400ccf9c  mov     ebx, eax
0x1400ccf9e  add     eax, ecx
0x1400ccfa0  test    ecx, eax
0x1400ccfa2  jnz     short loc_1400CCFF7
0x1400ccfa4  cmp     ebx, 0C0000225h
0x1400ccfaa  jz      short loc_1400CCFF7
0x1400ccfac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ccfb3  lea     rsi, WPP_GLOBAL_Control
0x1400ccfba  cmp     rcx, rsi
0x1400ccfbd  jz      loc_1400CD8A9
0x1400ccfc3  test    dword ptr [rcx+2Ch], 400000h
0x1400ccfca  jz      loc_1400CD8A9
0x1400ccfd0  cmp     byte ptr [rcx+29h], 2
0x1400ccfd4  jb      loc_1400CD8A9
0x1400ccfda  mov     edx, 28h ; '('
0x1400ccfdf  mov     rcx, [rcx+18h]
0x1400ccfe3  lea     r8, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids
0x1400ccfea  mov     r9d, ebx
0x1400ccfed  call    WPP_SF_d
0x1400ccff2  jmp     loc_1400CD8A9
0x1400ccff7  test    ebx, ebx
0x1400ccff9  jns     loc_1400CDCF5
0x1400ccfff  mov     edx, 20h ; ' '
0x1400cd004  mov     r8d, 30455646h
0x1400cd00a  lea     ecx, [rdx+20h]
0x1400cd00d  call    cs:__imp_ExAllocatePool2
0x1400cd014  nop     dword ptr [rax+rax+00h]
0x1400cd019  mov     [rbp+250h+var_1F0], rax
0x1400cd01d  mov     rdx, rax
0x1400cd020  test    rax, rax
0x1400cd023  jnz     short loc_1400CD05D
0x1400cd025  mov     ebx, 0C000009Ah
0x1400cd02a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cd031  lea     rsi, WPP_GLOBAL_Control
0x1400cd038  cmp     rcx, rsi
0x1400cd03b  jz      loc_1400CD8A9
0x1400cd041  test    dword ptr [rcx+2Ch], 400000h
0x1400cd048  jz      loc_1400CD8A9
0x1400cd04e  cmp     byte ptr [rcx+29h], 2
0x1400cd052  jb      loc_1400CD8A9
0x1400cd058  lea     edx, [rax+29h]
0x1400cd05b  jmp     short loc_1400CCFDF
0x1400cd05d  mov     rdi, [rbp+250h+var_2B8]
0x1400cd061  xorps   xmm0, xmm0
0x1400cd064  movups  xmmword ptr [rax], xmm0
0x1400cd067  movups  xmmword ptr [rax+10h], xmm0
0x1400cd06b  lea     rax, [rdi+2900h]
0x1400cd072  mov     rcx, [rax+8]
0x1400cd076  cmp     [rcx], rax
0x1400cd079  jz      short loc_1400CD082
0x1400cd07b  mov     ecx, 3
0x1400cd080  int     29h; Win8: RtlFailFast(ecx)
0x1400cd082  mov     [rdx], rax
0x1400cd085  xor     r8b, r8b
0x1400cd088  mov     [rdx+8], rcx
0x1400cd08c  mov     r15d, 10000h
0x1400cd092  mov     [rcx], rdx
0x1400cd095  mov     r14d, 48h ; 'H'
0x1400cd09b  mov     [rax+8], rdx
0x1400cd09f  mov     ecx, r14d
0x1400cd0a2  mov     eax, [rsi]
0x1400cd0a4  mov     [rdx+10h], eax
0x1400cd0a7  mov     eax, dword ptr [rsp+350h+var_310]
0x1400cd0ab  mov     [rdx+14h], eax
0x1400cd0ae  mov     edx, r15d
0x1400cd0b1  mov     [rsp+350h+var_308], r8b
0x1400cd0b6  mov     r8d, 30455646h
0x1400cd0bc  call    cs:__imp_ExAllocatePool2
0x1400cd0c3  nop     dword ptr [rax+rax+00h]
0x1400cd0c8  mov     r8d, 30455646h
0x1400cd0ce  mov     edx, r15d
0x1400cd0d1  mov     ecx, r14d
0x1400cd0d4  mov     [rsp+350h+var_2E8], rax
0x1400cd0d9  mov     rbx, rax
0x1400cd0dc  call    cs:__imp_ExAllocatePool2
0x1400cd0e3  nop     dword ptr [rax+rax+00h]
0x1400cd0e8  mov     edx, 10000h
0x1400cd0ed  mov     r8d, 30455646h
0x1400cd0f3  mov     ecx, r14d
0x1400cd0f6  mov     [rsp+350h+Source1], rax
0x1400cd0fb  mov     r15, rax
0x1400cd0fe  call    cs:__imp_ExAllocatePool2
0x1400cd105  nop     dword ptr [rax+rax+00h]
0x1400cd10a  mov     [rsp+350h+Source2], rax
0x1400cd10f  mov     r14d, 1
0x1400cd115  test    rbx, rbx
0x1400cd118  jz      loc_1400CDCB3
0x1400cd11e  test    r15, r15
0x1400cd121  jz      loc_1400CDCB3
0x1400cd127  test    rax, rax
0x1400cd12a  jz      loc_1400CDCB3
0x1400cd130  mov     rcx, [rdi+28D8h]; Lookaside
0x1400cd137  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400cd13e  nop     dword ptr [rax+rax+00h]
0x1400cd143  mov     [rsp+350h+var_310], rax
0x1400cd148  mov     r12, rax
0x1400cd14b  test    rax, rax
0x1400cd14e  jnz     short loc_1400CD1A2
0x1400cd150  mov     ebx, 0C000009Ah
0x1400cd155  mov     edi, ebx
0x1400cd157  mov     r10, cs:WPP_GLOBAL_Control
0x1400cd15e  lea     rdx, WPP_GLOBAL_Control
0x1400cd165  cmp     r10, rdx
0x1400cd168  jz      loc_1400CD82F
0x1400cd16e  test    dword ptr [r10+2Ch], 400000h
0x1400cd176  jz      loc_1400CD82F
0x1400cd17c  cmp     byte ptr [r10+29h], 2
0x1400cd181  jb      loc_1400CD82F
0x1400cd187  mov     rcx, [r10+18h]
0x1400cd18b  lea     edx, [rax+2Bh]
0x1400cd18e  mov     r9d, ebx
0x1400cd191  lea     r8, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids
0x1400cd198  call    WPP_SF_d
0x1400cd19d  jmp     loc_1400CD82F
0x1400cd1a2  xor     r8d, r8d
0x1400cd1a5  mov     r9, r13
0x1400cd1a8  shr     r9, 3
0x1400cd1ac  mov     r12, r13
0x1400cd1af  mov     eax, r8d
0x1400cd1b2  lea     rdi, [r8+rbx]
0x1400cd1b6  add     r8d, r13d
0x1400cd1b9  mov     rcx, r9
0x1400cd1bc  rep stosq
0x1400cd1bf  cmp     r8d, 10000h
0x1400cd1c6  jb      short loc_1400CD1AF
0x1400cd1c8  mov     edx, 40h ; '@'; cbBuffer
0x1400cd1cd  lea     rcx, [rbp+250h+pbBuffer]; pbBuffer
0x1400cd1d4  call    FveRandomDataCallback
0x1400cd1d9  mov     edi, eax
0x1400cd1db  test    eax, eax
0x1400cd1dd  jns     short loc_1400CD22A
0x1400cd1df  mov     rax, cs:WPP_GLOBAL_Control
0x1400cd1e6  lea     rdx, WPP_GLOBAL_Control
0x1400cd1ed  cmp     rax, rdx
0x1400cd1f0  jz      loc_1400CD82A
0x1400cd1f6  test    dword ptr [rax+2Ch], 400000h
0x1400cd1fd  jz      loc_1400CD82A
0x1400cd203  cmp     byte ptr [rax+29h], 2
0x1400cd207  jb      loc_1400CD82A
0x1400cd20d  mov     rcx, [rax+18h]
0x1400cd211  mov     edx, 2Ch ; ','
0x1400cd216  mov     r9d, edi
0x1400cd219  lea     r8, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids
0x1400cd220  call    WPP_SF_d
0x1400cd225  jmp     loc_1400CD82A
0x1400cd22a  mov     edx, [rsi+14h]
0x1400cd22d  lea     r8, [rsp+350h+var_2F8]
0x1400cd232  mov     ecx, [rsi+10h]
0x1400cd235  call    FveHwAccelMapAlgorithmTypesToFveKeyType
0x1400cd23a  mov     edi, eax
0x1400cd23c  test    eax, eax
0x1400cd23e  jns     short loc_1400CD27C
0x1400cd240  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cd247  lea     rdx, WPP_GLOBAL_Control
0x1400cd24e  cmp     rcx, rdx
0x1400cd251  jz      loc_1400CD82A
0x1400cd257  test    dword ptr [rcx+2Ch], 400000h
0x1400cd25e  jz      loc_1400CD82A
0x1400cd264  cmp     byte ptr [rcx+29h], 2
0x1400cd268  jb      loc_1400CD82A
0x1400cd26e  mov     edx, 2Dh ; '-'
0x1400cd273  mov     r9d, eax
0x1400cd276  mov     rcx, [rcx+18h]
0x1400cd27a  jmp     short loc_1400CD219
0x1400cd27c  movzx   ecx, [rsp+350h+var_2F8]
0x1400cd281  lea     rdx, [rsp+350h+var_2F4]
0x1400cd286  call    FveGetKeySizeFromFvekKeyType
0x1400cd28b  mov     edi, eax
0x1400cd28d  test    eax, eax
0x1400cd28f  jns     short loc_1400CD2C6
0x1400cd291  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cd298  lea     rdx, WPP_GLOBAL_Control
0x1400cd29f  cmp     rcx, rdx
0x1400cd2a2  jz      loc_1400CD82A
0x1400cd2a8  test    dword ptr [rcx+2Ch], 400000h
0x1400cd2af  jz      loc_1400CD82A
0x1400cd2b5  cmp     byte ptr [rcx+29h], 2
0x1400cd2b9  jb      loc_1400CD82A
0x1400cd2bf  mov     edx, 2Eh ; '.'
0x1400cd2c4  jmp     short loc_1400CD273
0x1400cd2c6  movzx   r8d, [rsp+350h+var_2F4]
0x1400cd2cc  lea     r9, [rbp+250h+var_2D0]
0x1400cd2d0  movzx   ecx, [rsp+350h+var_2F8]
0x1400cd2d5  lea     rdx, [rbp+250h+pbBuffer]
0x1400cd2dc  call    FveDatumKeyCreate
0x1400cd2e1  mov     edi, eax
0x1400cd2e3  test    eax, eax
0x1400cd2e5  jns     short loc_1400CD31F
0x1400cd2e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cd2ee  lea     rdx, WPP_GLOBAL_Control
0x1400cd2f5  cmp     rcx, rdx
0x1400cd2f8  jz      loc_1400CD82A
0x1400cd2fe  test    dword ptr [rcx+2Ch], 400000h
0x1400cd305  jz      loc_1400CD82A
0x1400cd30b  cmp     byte ptr [rcx+29h], 2
0x1400cd30f  jb      loc_1400CD82A
0x1400cd315  mov     edx, 2Fh ; '/'
0x1400cd31a  jmp     loc_1400CD273
0x1400cd31f  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400cd324  mov     rdx, qword ptr [rbp+250h+var_2D0]; int
0x1400cd328  lea     r8, [rbp+250h+P]
0x1400cd32c  mov     ecx, r13d; int
0x1400cd32f  test    eax, eax
0x1400cd331  jnz     short loc_1400CD33A
0x1400cd333  call    FveFvekDataFromFvekDatum
0x1400cd338  jmp     short loc_1400CD33F
0x1400cd33a  call    FveFvekDataFromFvekDatum2
0x1400cd33f  mov     edi, eax
0x1400cd341  test    eax, eax
0x1400cd343  jns     short loc_1400CD380
0x1400cd345  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cd34c  lea     rdx, WPP_GLOBAL_Control
0x1400cd353  cmp     rcx, rdx
0x1400cd356  jz      loc_1400CD82A
0x1400cd35c  test    dword ptr [rcx+2Ch], 400000h
0x1400cd363  jz      loc_1400CD82A
0x1400cd369  cmp     byte ptr [rcx+29h], 2
0x1400cd36d  jb      loc_1400CD82A
0x1400cd373  mov     edx, 30h ; '0'
0x1400cd378  mov     r9d, eax
0x1400cd37b  jmp     loc_1400CD276
  ... truncated ...
```
