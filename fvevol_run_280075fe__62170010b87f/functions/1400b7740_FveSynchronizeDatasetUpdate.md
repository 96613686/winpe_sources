# FveSynchronizeDatasetUpdate

- ea: `0x1400b7740`
- end: `0x1400b86b1`
- name: `FveSynchronizeDatasetUpdate`
- size: `3953`
- prototype: `__int64 __fastcall(int, void *Src)`
- caller_count: `1`
- callee_count: `43`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400644c4`

## callees

- `0x1400037e0`
- `0x140005314`
- `0x14000556c`
- `0x140005774`
- `0x140005e34`
- `0x140005e50`
- `0x1400062b4`
- `0x140008288`
- `0x140008dc0`
- `0x140008e44`
- `0x140009bf4`
- `0x14000a5d4`
- `0x14000b870`
- `0x1400132a4`
- `0x140014330`
- `0x140017130`
- `0x140017cfc`
- `0x140021a00`
- `0x1400232c8`
- `0x1400241b4`
- `0x14002e334`
- `0x14005c75c`
- `0x14005c7e8`
- `0x14005c958`
- `0x14005f27c`
- `0x140061b54`
- `0x14008d338`
- `0x14009897c`
- `0x14009df90`
- `0x1400a75a8`
- `0x1400ac500`
- `0x1400acd3c`
- `0x1400ad2fc`
- `0x1400af6b0`
- `0x1400b5c18`
- `0x1400b7740`
- `0x1400bec38`
- `0x1400c6408`
- `0x1400cca48`
- `0x1400de20c`
- `0x1400e43d8`
- `0x1400e614c`
- `0x1400ea0f0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400b783f`
- `ntoskrnl!RtlCompareMemory` at `0x1400b783f`
- `ntoskrnl!KeBugCheckEx` at `0x1400b85f6`
- `ntoskrnl!KeBugCheckEx` at `0x1400b85f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7969`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7986`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7969`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7986`
- `ntoskrnl!ExAllocatePool2` at `0x1400b7eff`
- `ntoskrnl!ExAllocatePool2` at `0x1400b7eff`

## pseudocode

```c
__int64 __fastcall FveSynchronizeDatasetUpdate(_QWORD *a1, _DWORD *Src, __int64 a3)
{
  PDEVICE_OBJECT v6; // rcx
  int v7; // eax
  ULONG_PTR v8; // r15
  __int64 v9; // r13
  __int64 v10; // r12
  int updated; // ebx
  _QWORD *v12; // rbx
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rdi
  PVOID v20; // rcx
  ULONG_PTR v21; // rsi
  int v22; // ebx
  PDEVICE_OBJECT v23; // rcx
  __int64 v24; // rdx
  PDEVICE_OBJECT v25; // rcx
  __int64 v26; // rdx
  int First; // eax
  int v28; // ebx
  int v29; // eax
  __int64 v30; // rcx
  _QWORD *v31; // rax
  int v32; // ebx
  int v33; // eax
  int Fvek; // eax
  __int64 v35; // rdx
  int FvekDatumFromVmk; // eax
  __int64 v37; // rcx
  int v38; // ebx
  int v39; // eax
  __int64 v40; // rcx
  _QWORD *v41; // rax
  int v42; // ebx
  int v43; // eax
  __int64 v44; // rax
  __int64 v45; // rbx
  __int64 v46; // rcx
  __int64 v47; // rcx
  void *Pool2; // rax
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // r8
  __int64 v52; // r15
  __int64 v53; // rcx
  __int64 v54; // rcx
  char *v55; // rsi
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v57; // rcx
  __int64 v58; // rax
  ULONG_PTR v59; // r14
  char *v60; // rsi
  int v61; // eax
  __int64 v62; // rcx
  int v63; // ebx
  int v64; // eax
  __int64 v65; // rdx
  __int64 v66; // rcx
  void *v67; // rcx
  __int64 v68; // rcx
  void *v69; // rcx
  __int64 v70; // rdx
  _QWORD *v71; // rdx
  __int64 v72; // rcx
  int v73; // eax
  int v74; // eax
  __int64 v75; // rcx
  __int64 v76; // rax
  __int64 v77; // rax
  void *v78; // rcx
  __int64 v79; // rax
  ULONG_PTR v80; // r14
  char *v81; // rsi
  _QWORD *v82; // rdx
  __int64 v83; // rcx
  int v84; // eax
  _OWORD *v85; // rsi
  _OWORD *v86; // rax
  __int64 v87; // rsi
  __int64 v88; // rcx
  __int64 v89; // rcx
  ULONG_PTR v90; // rsi
  __int64 v91; // rax
  ULONG_PTR BugCheckParameter4; // [rsp+20h] [rbp-79h]
  PVOID P; // [rsp+30h] [rbp-69h] BYREF
  __int64 v95; // [rsp+38h] [rbp-61h]
  __int64 v96; // [rsp+40h] [rbp-59h]
  PVOID v97; // [rsp+48h] [rbp-51h]
  PVOID v98; // [rsp+50h] [rbp-49h] BYREF
  int v99[2]; // [rsp+58h] [rbp-41h] BYREF
  void *v100; // [rsp+60h] [rbp-39h] BYREF
  PVOID Srca; // [rsp+68h] [rbp-31h]
  ULONG_PTR v102; // [rsp+70h] [rbp-29h]
  PVOID v103; // [rsp+78h] [rbp-21h]
  __int64 v104; // [rsp+80h] [rbp-19h] BYREF
  __int64 v105; // [rsp+88h] [rbp-11h] BYREF
  __int64 v106; // [rsp+90h] [rbp-9h] BYREF
  ULONG_PTR v107; // [rsp+98h] [rbp-1h]
  PVOID v108; // [rsp+A0h] [rbp+7h]
  __int64 v109; // [rsp+A8h] [rbp+Fh] BYREF
  __int64 v110; // [rsp+B0h] [rbp+17h]
  int v111; // [rsp+100h] [rbp+67h] BYREF
  ULONG_PTR v112; // [rsp+118h] [rbp+7Fh] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids);
  }
  v7 = *((_DWORD *)a1 + 202);
  v111 = 0;
  v8 = 0;
  P = 0;
  v9 = 0;
  v104 = 0;
  v10 = 0;
  v112 = 0;
  *(_QWORD *)v99 = 0;
  v95 = 0;
  v106 = 0;
  v109 = 0;
  v97 = 0;
  v98 = 0;
  v103 = 0;
  v100 = 0;
  v96 = 0;
  v105 = 0;
  if ( (v7 & 0x8000) != 0 )
  {
    updated = -1071579135;
    goto LABEL_289;
  }
  if ( (v7 & 0x4000) != 0 )
  {
    updated = -1071579102;
    goto LABEL_289;
  }
  v6 = (PDEVICE_OBJECT)a1[122];
  if ( !v6 )
  {
    updated = -1071579134;
    goto LABEL_289;
  }
  if ( (Src[1] & 0x7FFFFFFF) != 1 || (v110 = a1[1], RtlCompareMemory(&v6->Queue, Src + 4, 0x10u) != 16) )
  {
    updated = -1073741811;
    goto LABEL_289;
  }
  Srca = 0;
  updated = FveDuplicateInformation(a1, &P);
  if ( updated < 0 )
    goto LABEL_33;
  v12 = P;
  v108 = P;
  if ( *((_WORD *)P + 5) > 1u )
  {
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(1)
      && (*((_BYTE *)a1 + 4403) & 8) != 0
      || (v14 = a1[122], *(_WORD *)(v14 + 10) == 1) )
    {
      v15 = 0;
    }
    else
    {
      v15 = *(unsigned int *)(v14 + 28);
      if ( !(_DWORD)v15 )
        v15 = 1;
    }
    updated = FveAddLegacyVirtualizationInfoToDataset(v12 + 8, v12[7], v15 * *((unsigned int *)a1 + 327), &v104);
    if ( updated < 0 )
      goto LABEL_33;
    v13 = FveDatasetCompress(v104);
  }
  else
  {
    v13 = FveWorksetCreateWithLength((char *)P + 64);
  }
  updated = v13;
  if ( v13 >= 0 )
  {
    updated = FveDatumUpdateVerify(v104, a3);
    if ( updated < 0 )
    {
      v20 = P;
      goto LABEL_287;
    }
    if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v16) )
      LOBYTE(v10) = *(_BYTE *)(a3 + 8) & 1;
    v17 = FveDatumNestedExtractFirst(a3, 0xFFFF, 1, &v112);
    updated = v17;
    if ( v17 >= 0 )
    {
      v8 = v112;
      v102 = v112;
      if ( v112 )
      {
        if ( a1[127] && (unsigned __int8)FveDatumKeyCompare(v112) )
        {
          FveDatumFree(v8);
          v8 = 0;
          v102 = 0;
        }
        v21 = v8;
        if ( v8 )
        {
LABEL_55:
          v22 = a1[101] & 2;
          v107 = v21;
          LODWORD(v112) = v22;
          if ( !v21 && !v22 )
            goto LABEL_57;
          if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v18) )
          {
            if ( (_BYTE)v10 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids);
              }
              if ( !v22 )
              {
                updated = -1071579127;
                v23 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_32;
                }
                v24 = 14;
                goto LABEL_69;
              }
              if ( !v21 )
              {
                updated = -1073741811;
                v23 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_32;
                }
                v24 = 15;
                goto LABEL_69;
              }
              updated = FveDatasetVmkGetFvek(Src, v21, v99);
              if ( updated < 0 )
              {
                v25 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_81;
                }
                v26 = 16;
                goto LABEL_80;
              }
              if ( a1[127] )
              {
                First = FveDatasetGetFirst((char *)P + 64, 3, 5, &v109);
                updated = 0;
                if ( First != -1073741275 )
                  updated = First;
                if ( updated < 0 )
                {
                  v25 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
                    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                  {
                    goto LABEL_81;
                  }
                  v26 = 17;
LABEL_80:
                  WPP_SF_(v25->AttachedDevice, v26, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids);
LABEL_81:
                  v9 = *(_QWORD *)v99;
                  goto LABEL_32;
                }
              }
              v9 = *(_QWORD *)v99;
              if ( (unsigned __int16)(*(_WORD *)(*(_QWORD *)v99 + 8LL) + 0x8000) <= 1u )
              {
                updated = -1073741811;
                v23 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_32;
                }
                v24 = 18;
LABEL_69:
                WPP_SF_(v23->AttachedDevice, v24, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids);
                goto LABEL_32;
              }
              v28 = *((_DWORD *)a1 + 327);
              if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(1) )
                v29 = FveFvekDataFromFvekDatum2(v28, v9);
              else
                v29 = FveFvekDataFromFvekDatum(v28, v9);
              updated = v29;
              if ( v29 < 0 )
              {
                v23 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_32;
                }
                v24 = 19;
                goto LABEL_69;
              }
              if ( (a1[101] & 0x100) != 0 )
              {
                v31 = (_QWORD *)a1[92];
                if ( v31 )
                {
                  if ( *v31 )
                  {
                    v32 = *((_DWORD *)a1 + 327);
                    v33 = (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v30)
                        ? FveFvekDataFromFvekDatum2(v32, v9)
                        : FveFvekDataFromFvekDatum(v32, v9);
                    updated = v33;
                    if ( v33 < 0 )
                    {
                      v23 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
                        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                      {
                        goto LABEL_32;
                      }
                      v24 = 20;
                      goto LABEL_69;
                    }
                  }
                }
              }
            }
            goto LABEL_143;
          }
          if ( v21 )
          {
            Fvek = FveDatasetVmkGetFvek(Src, v21, v99);
            updated = Fvek;
            if ( Fvek >= 0 )
            {
              v9 = *(_QWORD *)v99;
            }
            else if ( Fvek != -1073741275 )
            {
              goto LABEL_81;
            }
          }
          v35 = a1[127];
          if ( v35 )
          {
            FvekDatumFromVmk = GetFvekDatumFromVmk((char *)P + 64, v35, &v106);
            updated = FvekDatumFromVmk;
            if ( FvekDatumFromVmk >= 0 )
            {
              v95 = v106;
              if ( v106 )
              {
                if ( !(unsigned __int8)FveDatumKeyCompare(v9) )
                {
                  if ( !(_DWORD)v112 )
                    goto LABEL_57;
                  if ( !v9 )
                    goto LABEL_125;
                  goto LABEL_124;
                }
LABEL_143:
                if ( (*(_DWORD *)(a1[15] + 48LL) & 0x400100) == 0 )
                  goto LABEL_155;
                updated = FveDatasetVmkGetAndDecryptDatum((_DWORD)Src, v21, 11, 1, (__int64)&v105);
                if ( updated < 0 )
                {
                  if ( v8 )
                  {
                    v10 = v105;
                    goto LABEL_33;
                  }
                  v44 = v105;
                  goto LABEL_154;
                }
                v45 = v105;
                v46 = a1[1];
                v96 = v105;
                if ( (unsigned __int8)FveAutoUnlockCompareMasterKey(v46, v105) )
                {
                  FveDatumFree(v45);
                  v44 = 0;
LABEL_154:
                  v96 = v44;
                  goto LABEL_155;
                }
                if ( (unsigned __int8)FveAutoUnlockCompareMasterKey(a1[1], 0)
                  || (int)FveAutoUnlockCheckBinding(v47, &v111) < 0
                  || !v111 )
                {
LABEL_155:
                  updated = FveWorksetCommit(Src, (char *)P + 64);
                  if ( updated < 0 )
                    goto LABEL_32;
                  Pool2 = (void *)ExAllocatePool2(64, 0x10000, 809850438);
                  Srca = Pool2;
                  if ( !Pool2 )
                  {
                    updated = -1073741670;
                    goto LABEL_32;
                  }
                  memmove(Pool2, P, 0x10000u);
                  updated = FveNvcWriteBackDisable(a1);
                  if ( updated < 0 )
                    goto LABEL_32;
                  if ( !(unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v49)
                    || (*((_BYTE *)a1 + 4403) & 8) == 0 )
                  {
                    LOBYTE(v51) = 1;
                    updated = FvePrepareForFveInfoCopyUpdate(a1, *((unsigned int *)a1 + 573), v51);
                    if ( updated < 0 )
                      goto LABEL_194;
                  }
                  v52 = 0;
                  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v50) )
                  {
                    if ( !(_BYTE)v10 )
                      goto LABEL_167;
                  }
                  else if ( !v97 )
                  {
LABEL_167:
                    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v53)
                      && (*((_BYTE *)a1 + 4403) & 8) != 0 )
                    {
                      v55 = (char *)Srca;
                      updated = 0;
                    }
                    else
                    {
                      BugCheckParameter4 = v21;
                      v55 = (char *)Srca;
                      updated = FveWriteInformation(a1, BugCheckParameter4, 1);
                    }
                    IsEnabledDeviceUsageNoInline = Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v54);
                    v57 = 3221225472LL;
                    if ( IsEnabledDeviceUsageNoInline )
                    {
                      if ( !(_BYTE)v10 )
                      {
LABEL_268:
                        if ( !(unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v57)
                          || (*((_BYTE *)a1 + 4403) & 8) == 0 )
                        {
                          FveCompleteFveInfoCopyUpdate(a1);
                        }
                        if ( (updated & 0xC0000000) == 0xC0000000 )
                          goto LABEL_194;
                        v85 = P;
                        memmove(P, Srca, 0x10000u);
                        v86 = (_OWORD *)a1[122];
                        *v86 = *v85;
                        v86[1] = v85[1];
                        v86[2] = v85[2];
                        v86[3] = v85[3];
                        v86[4] = v85[4];
                        v86[5] = v85[5];
                        v86[6] = v85[6];
                        v87 = _InterlockedExchange64(a1 + 123, (__int64)v85);
                        v88 = a1[123];
                        v108 = (PVOID)v87;
                        a1[128] = 0;
                        if ( (int)FveFindExtendedInfoInDataset(v88 + 64, a1 + 128) < 0 )
                          a1[128] = 0;
                        v90 = v102;
                        if ( v102 )
                        {
                          v89 = a1[127];
                          if ( v89 )
                            FveDatumFree(v89);
                          a1[127] = v90;
                          v102 = 0;
                        }
                        if ( v96 )
                        {
                          FveAutoUnlockCacheMasterKey(a1[1], v96, *a1);
                          v96 = 0;
                        }
                        if ( (_DWORD)v112 )
                          goto LABEL_194;
                        if ( !(unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v89) )
                          goto LABEL_194;
                        if ( a1[126] )
                          goto LABEL_194;
                        v91 = a1[592];
                        if ( v91 )
                        {
                          if ( *(_DWORD *)(v91 + 88) )
                            goto LABEL_194;
                        }
                        goto LABEL_285;
                      }
                      if ( (updated & 0xC0000000) != 0xC0000000 )
                      {
                        v58 = a1[128];
                        if ( v58 && *(_WORD *)v58 >= 5u && *(_WORD *)(v58 + 2) >= 0x4Cu )
                          v52 = *(_QWORD *)(v58 + 68);
                        v59 = v107;
                        v60 = v55 + 64;
                        v61 = FveResolveIceCryptoInfoV2((int)a1, v52);
                        if ( v61 < 0
                          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                        {
                          WPP_SF_d(
                            WPP_GLOBAL_Control->AttachedDevice,
                            21,
                            WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids,
                            (unsigned int)v61);
                        }
                        if ( a1[592] )
                        {
                          v62 = *(unsigned int *)(a1[1] + 9680LL);
                          if ( (v62 & 2) != 0 )
                          {
                            v63 = *((_DWORD *)a1 + 327);
                            if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v62) )
                              v64 = FveFvekDataFromFvekDatum2(v63, v9);
                            else
                              v64 = FveFvekDataFromFvekDatum(v63, v9);
                            updated = v64;
                            if ( v64 < 0 )
                            {
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                              {
                                WPP_SF_(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  22,
                                  WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids);
                              }
LABEL_193:
                              LOBYTE(v65) = 1;
                              FveDeleteIceKey(a1, v65);
                              v103 = v100;
LABEL_194:
                              FveNvcWriteBackReset(a1);
                              v20 = v108;
                              v8 = v102;
                              v10 = v96;
LABEL_287:
                              v19 = v95;
                              goto LABEL_35;
                            }
                            v66 = a1[594];
                            if ( v66 )
                            {
                              v67 = *(void **)(v66 + 152);
                              if ( v67 )
                              {
                                DeleteKey(v67);
                                *(_QWORD *)(a1[594] + 152LL) = 0;
                              }
                              v68 = a1[594];
                              v103 = 0;
                              *(_QWORD *)(v68 + 152) = v100;
                            }
                            else
                            {
                              updated = FveIceSimAlloc(a1, &v100);
                              if ( updated < 0 )
                              {
                                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                                {
                                  WPP_SF_(
                                    WPP_GLOBAL_Control->AttachedDevice,
                                    23,
                                    WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids);
                                }
                                goto LABEL_193;
                              }
                              v103 = v100;
                            }
                          }
                        }
                        v69 = (void *)a1[126];
                        if ( v69 )
                        {
                          DeleteKey(v69);
                          a1[126] = 0;
                        }
                        v70 = a1[592];
                        if ( !v70 || !*(_DWORD *)(v70 + 88) )
                        {
                          a1[126] = v97;
                          v97 = 0;
                        }
                        if ( (*(_DWORD *)(v110 + 9680) & 0x10) != 0
                          && v70
                          && *(_DWORD *)(v70 + 88)
                          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                        {
                          WPP_SF_(
                            WPP_GLOBAL_Control->AttachedDevice,
                            24,
                            WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids);
                        }
                        if ( (unsigned int)Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline() )
                        {
                          if ( !a1[592] )
                          {
                            updated = FveHwAccelTryConfigureCryptoOffload(a1, v60, v59);
                            if ( updated < 0 )
                            {
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                                && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                              {
                                WPP_SF_d(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  25,
                                  WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids,
                                  (unsigned int)updated);
                              }
                              updated = 0;
                            }
                          }
                        }
                        if ( (a1[101] & 0x100) != 0 )
                        {
                          v71 = (_QWORD *)a1[92];
                          if ( v71 )
                          {
                            if ( *v71 )
                            {
                              FveEowClearKey(a1);
                              FveEowSetKey(v72, a1[92], &v98);
                            }
                          }
                        }
                        v73 = *((_DWORD *)a1 + 202);
                        if ( (v73 & 0x17F) != 0 && (v73 & 0x40) == 0 )
                          UpdateDynamicContext(a1, v59, v60);
                      }
                      v74 = *((_DWORD *)a1 + 213);
                      if ( (v74 & 0x40) == 0
                        && (v74 & 0x19) != 0
                        && ((v75 = a1[126]) == 0 && ((v76 = a1[592]) == 0 || !*(_DWORD *)(v76 + 88))
                         || (v77 = a1[592]) != 0 && *(_DWORD *)(v77 + 88) && v75) )
                      {
LABEL_285:
                        KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
                      }
                    }
                    else
                    {
                      if ( !v97 )
                        goto LABEL_268;
                      if ( (updated & 0xC0000000) != 0xC0000000 )
                      {
                        v78 = (void *)a1[126];
                        if ( v78 )
                          DeleteKey(v78);
                        a1[126] = v97;
                        v79 = a1[128];
                        v97 = 0;
                        if ( v79 && *(_WORD *)v79 >= 5u && *(_WORD *)(v79 + 2) >= 0x4Cu )
                          v52 = *(_QWORD *)(v79 + 68);
                        v80 = v107;
                        v81 = v55 + 64;
                        FveResolveIceCryptoInfo((int)a1, v52);
                        if ( a1[592] && (*(_DWORD *)(a1[1] + 9680LL) & 2) != 0 )
                          FveIceSimAlloc(a1, 0);
                        if ( (unsigned int)Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline() )
                        {
                          if ( !a1[592] )
                          {
                            updated = FveHwAccelTryConfigureCryptoOffload(a1, v81, v80);
                            if ( updated < 0 )
                            {
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                                && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                              {
                                WPP_SF_d(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  26,
                                  WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids,
                                  (unsigned int)updated);
                              }
                              updated = 0;
                            }
                          }
                        }
                        if ( (a1[101] & 0x100) != 0 )
                        {
                          v82 = (_QWORD *)a1[92];
                          if ( v82 )
                          {
                            if ( *v82 )
                            {
                              FveEowClearKey(a1);
                              FveEowSetKey(v83, a1[92], &v98);
                            }
                          }
                        }
                        v84 = *((_DWORD *)a1 + 202);
                        if ( (v84 & 0x17F) != 0 && (v84 & 0x40) == 0 )
                          UpdateDynamicContext(a1, v80, v81);
                      }
                    }
                    FveResumeAllReadsAndWrites((__int64)a1);
                    goto LABEL_268;
                  }
                  FveRundownAllReadsAndWrites(a1);
                  goto LABEL_167;
                }
LABEL_57:
                updated = -1071579127;
                goto LABEL_32;
              }
            }
            else
            {
              if ( FvekDatumFromVmk != -1073741275 )
              {
                v19 = v106;
                v10 = v96;
                goto LABEL_34;
              }
              v95 = 0;
            }
          }
          if ( v9 )
          {
LABEL_124:
            v37 = 1;
            if ( (unsigned __int16)(*(_WORD *)(v9 + 8) + 0x8000) <= 1u )
            {
              updated = -1073741811;
              goto LABEL_32;
            }
LABEL_125:
            v38 = *((_DWORD *)a1 + 327);
            if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v37) )
              v39 = FveFvekDataFromFvekDatum2(v38, v9);
            else
              v39 = FveFvekDataFromFvekDatum(v38, v9);
            updated = v39;
            if ( v39 < 0 )
              goto LABEL_32;
            if ( (a1[101] & 0x100) != 0 )
            {
              v41 = (_QWORD *)a1[92];
              if ( v41 )
              {
                if ( *v41 )
                {
                  v42 = *((_DWORD *)a1 + 327);
                  v43 = (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v40)
                      ? FveFvekDataFromFvekDatum2(v42, v9)
                      : FveFvekDataFromFvekDatum(v42, v9);
                  updated = v43;
                  if ( v43 < 0 )
                    goto LABEL_32;
                }
              }
            }
            goto LABEL_143;
          }
          goto LABEL_143;
        }
      }
    }
    else
    {
      if ( v17 != -1073741275 )
      {
        v8 = v112;
LABEL_32:
        v10 = v96;
        goto LABEL_33;
      }
      v102 = 0;
    }
    v21 = a1[127];
    goto LABEL_55;
  }
LABEL_33:
  v19 = v95;
LABEL_34:
  v20 = P;
LABEL_35:
  if ( v20 )
    ExFreePoolWithTag(v20, 0x30455646u);
  if ( Srca )
    ExFreePoolWithTag(Srca, 0x30455646u);
  if ( v97 )
    DeleteKey(v97);
  v6 = (PDEVICE_OBJECT)v98;
  if ( v98 )
    DeleteKey(v98);
  if ( v8 )
    FveDatumFree(v8);
  if ( v9 )
    FveDatumFree(v9);
  if ( v19 )
    FveDatumFree(v19);
LABEL_289:
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v6) )
  {
    if ( v109 )
      FveDatumFree(v109);
    if ( v103 )
      DeleteKey(v103);
  }
  if ( v10 )
    FveDatumFree(v10);
  if ( v104 )
    FveWorksetFree(v104);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      27,
      WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids,
      (unsigned int)updated);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1400b7740  mov     [rsp-8+arg_8], rbx
0x1400b7745  push    rbp
0x1400b7746  push    rsi
0x1400b7747  push    rdi
0x1400b7748  push    r12
0x1400b774a  push    r13
0x1400b774c  push    r14
0x1400b774e  push    r15
0x1400b7750  lea     rbp, [rsp-27h]
0x1400b7755  sub     rsp, 0C0h
0x1400b775c  mov     rsi, r8
0x1400b775f  mov     r14, rdx
0x1400b7762  mov     rdi, rcx
0x1400b7765  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b776c  lea     rax, WPP_GLOBAL_Control
0x1400b7773  cmp     rcx, rax
0x1400b7776  jz      short loc_1400B779A
0x1400b7778  mov     eax, [rcx+2Ch]
0x1400b777b  test    al, 10h
0x1400b777d  jz      short loc_1400B779A
0x1400b777f  cmp     byte ptr [rcx+29h], 5
0x1400b7783  jb      short loc_1400B779A
0x1400b7785  mov     rcx, [rcx+18h]
0x1400b7789  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x1400b7790  mov     edx, 0Ch
0x1400b7795  call    WPP_SF_
0x1400b779a  mov     eax, [rdi+328h]
0x1400b77a0  xor     ebx, ebx
0x1400b77a2  mov     [rbp+57h+arg_0], ebx
0x1400b77a5  mov     r15d, ebx
0x1400b77a8  mov     [rbp+57h+P], rbx
0x1400b77ac  mov     r13d, ebx
0x1400b77af  mov     [rbp+57h+var_70], rbx
0x1400b77b3  mov     r12d, ebx
0x1400b77b6  mov     [rbp+57h+arg_18], rbx
0x1400b77ba  mov     qword ptr [rbp+57h+var_98], rbx
0x1400b77be  mov     [rbp+57h+var_B8], rbx
0x1400b77c2  mov     [rbp+57h+var_60], rbx
0x1400b77c6  mov     [rbp+57h+var_48], rbx
0x1400b77ca  mov     [rbp+57h+var_A8], rbx
0x1400b77ce  mov     [rbp+57h+var_A0], rbx
0x1400b77d2  mov     [rbp+57h+var_78], rbx
0x1400b77d6  mov     [rbp+57h+var_90], rbx
0x1400b77da  mov     [rbp+57h+var_B0], rbx
0x1400b77de  mov     [rbp+57h+var_68], rbx
0x1400b77e2  bt      eax, 0Fh
0x1400b77e6  jnb     short loc_1400B77F2
0x1400b77e8  mov     ebx, 0C0210001h
0x1400b77ed  jmp     loc_1400B8615
0x1400b77f2  bt      eax, 0Eh
0x1400b77f6  jnb     short loc_1400B7802
0x1400b77f8  mov     ebx, 0C0210022h
0x1400b77fd  jmp     loc_1400B8615
0x1400b7802  mov     rcx, [rdi+3D0h]
0x1400b7809  test    rcx, rcx
0x1400b780c  jnz     short loc_1400B7818
0x1400b780e  mov     ebx, 0C0210002h
0x1400b7813  jmp     loc_1400B8615
0x1400b7818  mov     eax, [r14+4]
0x1400b781c  btr     eax, 1Fh
0x1400b7820  cmp     eax, 1
0x1400b7823  jnz     loc_1400B8610
0x1400b7829  mov     rax, [rdi+8]
0x1400b782d  lea     rdx, [r14+10h]; Source2
0x1400b7831  add     rcx, 50h ; 'P'; Source1
0x1400b7835  mov     [rbp+57h+var_40], rax
0x1400b7839  mov     r8d, 10h; Length
0x1400b783f  call    cs:__imp_RtlCompareMemory
0x1400b7846  nop     dword ptr [rax+rax+00h]
0x1400b784b  cmp     rax, 10h
0x1400b784f  jnz     loc_1400B8610
0x1400b7855  lea     rdx, [rbp+57h+P]
0x1400b7859  mov     [rbp+57h+Src], rbx
0x1400b785d  mov     rcx, rdi
0x1400b7860  call    FveDuplicateInformation
0x1400b7865  mov     ebx, eax
0x1400b7867  test    eax, eax
0x1400b7869  js      loc_1400B7957
0x1400b786f  mov     rbx, [rbp+57h+P]
0x1400b7873  mov     ecx, 1
0x1400b7878  mov     [rbp+57h+var_50], rbx
0x1400b787c  cmp     [rbx+0Ah], cx
0x1400b7880  ja      short loc_1400B7896
0x1400b7882  lea     rcx, [rbx+40h]; Src
0x1400b7886  xor     r8d, r8d
0x1400b7889  mov     edx, [rcx]
0x1400b788b  lea     r9, [rbp+57h+var_70]
0x1400b788f  call    FveWorksetCreateWithLength
0x1400b7894  jmp     short loc_1400B78F1
0x1400b7896  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400b789b  test    eax, eax
0x1400b789d  jz      short loc_1400B78A8
0x1400b789f  test    byte ptr [rdi+1133h], 8
0x1400b78a6  jnz     short loc_1400B78BA
0x1400b78a8  mov     rax, [rdi+3D0h]
0x1400b78af  mov     ecx, 1
0x1400b78b4  cmp     [rax+0Ah], cx
0x1400b78b8  jnz     short loc_1400B78BE
0x1400b78ba  xor     eax, eax
0x1400b78bc  jmp     short loc_1400B78C6
0x1400b78be  mov     eax, [rax+1Ch]
0x1400b78c1  test    eax, eax
0x1400b78c3  cmovz   eax, ecx
0x1400b78c6  mov     r8d, [rdi+51Ch]
0x1400b78cd  lea     rcx, [rbx+40h]
0x1400b78d1  mov     rdx, [rbx+38h]
0x1400b78d5  lea     r9, [rbp+57h+var_70]
0x1400b78d9  imul    r8, rax
0x1400b78dd  call    FveAddLegacyVirtualizationInfoToDataset
0x1400b78e2  mov     ebx, eax
0x1400b78e4  test    eax, eax
0x1400b78e6  js      short loc_1400B7957
0x1400b78e8  mov     rcx, [rbp+57h+var_70]
0x1400b78ec  call    FveDatasetCompress
0x1400b78f1  mov     ebx, eax
0x1400b78f3  test    eax, eax
0x1400b78f5  js      short loc_1400B7957
0x1400b78f7  mov     rcx, [rbp+57h+var_70]
0x1400b78fb  mov     rdx, rsi
0x1400b78fe  call    FveDatumUpdateVerify
0x1400b7903  mov     ebx, eax
0x1400b7905  test    eax, eax
0x1400b7907  js      loc_1400B8603
0x1400b790d  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400b7912  test    eax, eax
0x1400b7914  jz      short loc_1400B791E
0x1400b7916  mov     r12b, [rsi+8]
0x1400b791a  and     r12b, 1
0x1400b791e  mov     edx, 0FFFFh
0x1400b7923  lea     r9, [rbp+57h+arg_18]
0x1400b7927  mov     r8d, 1
0x1400b792d  mov     rcx, rsi
0x1400b7930  call    FveDatumNestedExtractFirst
0x1400b7935  mov     ebx, eax
0x1400b7937  test    eax, eax
0x1400b7939  jns     loc_1400B79DE
0x1400b793f  cmp     eax, 0C0000225h
0x1400b7944  jnz     short loc_1400B794F
0x1400b7946  mov     [rbp+57h+var_80], r15
0x1400b794a  jmp     loc_1400B7A1A
0x1400b794f  mov     r15, [rbp+57h+arg_18]
0x1400b7953  mov     r12, [rbp+57h+var_B0]
0x1400b7957  mov     rdi, [rbp+57h+var_B8]
0x1400b795b  mov     rcx, [rbp+57h+P]; P
0x1400b795f  test    rcx, rcx
0x1400b7962  jz      short loc_1400B7975
0x1400b7964  mov     edx, 30455646h; Tag
0x1400b7969  call    cs:__imp_ExFreePoolWithTag
0x1400b7970  nop     dword ptr [rax+rax+00h]
0x1400b7975  mov     rax, [rbp+57h+Src]
0x1400b7979  test    rax, rax
0x1400b797c  jz      short loc_1400B7992
0x1400b797e  mov     edx, 30455646h; Tag
0x1400b7983  mov     rcx, rax; P
0x1400b7986  call    cs:__imp_ExFreePoolWithTag
0x1400b798d  nop     dword ptr [rax+rax+00h]
0x1400b7992  mov     rcx, [rbp+57h+var_A8]; P
0x1400b7996  test    rcx, rcx
0x1400b7999  jz      short loc_1400B79A0
0x1400b799b  call    DeleteKey
0x1400b79a0  mov     rcx, [rbp+57h+var_A0]; P
0x1400b79a4  test    rcx, rcx
0x1400b79a7  jz      short loc_1400B79AE
0x1400b79a9  call    DeleteKey
0x1400b79ae  test    r15, r15
0x1400b79b1  jz      short loc_1400B79BB
0x1400b79b3  mov     rcx, r15
0x1400b79b6  call    FveDatumFree
0x1400b79bb  test    r13, r13
0x1400b79be  jz      short loc_1400B79C8
0x1400b79c0  mov     rcx, r13
0x1400b79c3  call    FveDatumFree
0x1400b79c8  test    rdi, rdi
0x1400b79cb  jz      loc_1400B8615
0x1400b79d1  mov     rcx, rdi
0x1400b79d4  call    FveDatumFree
0x1400b79d9  jmp     loc_1400B8615
0x1400b79de  mov     r15, [rbp+57h+arg_18]
0x1400b79e2  mov     [rbp+57h+var_80], r15
0x1400b79e6  test    r15, r15
0x1400b79e9  jz      short loc_1400B7A1A
0x1400b79eb  mov     rdx, [rdi+3F8h]
0x1400b79f2  test    rdx, rdx
0x1400b79f5  jz      short loc_1400B7A12
0x1400b79f7  mov     rcx, r15
0x1400b79fa  call    FveDatumKeyCompare
0x1400b79ff  test    al, al
0x1400b7a01  jz      short loc_1400B7A12
0x1400b7a03  mov     rcx, r15
0x1400b7a06  call    FveDatumFree
0x1400b7a0b  xor     r15d, r15d
0x1400b7a0e  mov     [rbp+57h+var_80], r15
0x1400b7a12  mov     rsi, r15
0x1400b7a15  test    r15, r15
0x1400b7a18  jnz     short loc_1400B7A21
0x1400b7a1a  mov     rsi, [rdi+3F8h]
0x1400b7a21  mov     ebx, [rdi+328h]
0x1400b7a27  and     ebx, 2
0x1400b7a2a  mov     [rbp+57h+var_58], rsi
0x1400b7a2e  mov     dword ptr [rbp+57h+arg_18], ebx
0x1400b7a31  test    rsi, rsi
0x1400b7a34  jnz     short loc_1400B7A44
0x1400b7a36  test    ebx, ebx
0x1400b7a38  jnz     short loc_1400B7A44
0x1400b7a3a  mov     ebx, 0C0210009h
0x1400b7a3f  jmp     loc_1400B7953
0x1400b7a44  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400b7a49  test    eax, eax
0x1400b7a4b  jz      loc_1400B7D05
0x1400b7a51  test    r12b, r12b
0x1400b7a54  jz      loc_1400B7E3D
0x1400b7a5a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b7a61  lea     rax, WPP_GLOBAL_Control
0x1400b7a68  cmp     rcx, rax
0x1400b7a6b  jz      short loc_1400B7A96
0x1400b7a6d  mov     eax, [rcx+2Ch]
0x1400b7a70  test    al, 10h
0x1400b7a72  jz      short loc_1400B7A8F
0x1400b7a74  cmp     byte ptr [rcx+29h], 5
0x1400b7a78  jb      short loc_1400B7A8F
0x1400b7a7a  mov     rcx, [rcx+18h]
0x1400b7a7e  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x1400b7a85  mov     edx, 0Dh
0x1400b7a8a  call    WPP_SF_
0x1400b7a8f  lea     rax, WPP_GLOBAL_Control
0x1400b7a96  test    ebx, ebx
0x1400b7a98  jnz     short loc_1400B7ADE
0x1400b7a9a  mov     ebx, 0C0210009h
0x1400b7a9f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b7aa6  cmp     rcx, rax
0x1400b7aa9  jz      loc_1400B7953
0x1400b7aaf  mov     eax, [rcx+2Ch]
0x1400b7ab2  test    al, 10h
0x1400b7ab4  jz      loc_1400B7953
0x1400b7aba  cmp     byte ptr [rcx+29h], 2
0x1400b7abe  jb      loc_1400B7953
0x1400b7ac4  mov     edx, 0Eh
0x1400b7ac9  mov     rcx, [rcx+18h]
0x1400b7acd  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x1400b7ad4  call    WPP_SF_
0x1400b7ad9  jmp     loc_1400B7953
0x1400b7ade  test    rsi, rsi
0x1400b7ae1  jnz     short loc_1400B7B12
0x1400b7ae3  mov     ebx, 0C000000Dh
0x1400b7ae8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b7aef  cmp     rcx, rax
0x1400b7af2  jz      loc_1400B7953
0x1400b7af8  mov     eax, [rcx+2Ch]
0x1400b7afb  test    al, 10h
0x1400b7afd  jz      loc_1400B7953
0x1400b7b03  cmp     byte ptr [rcx+29h], 2
0x1400b7b07  jb      loc_1400B7953
0x1400b7b0d  lea     edx, [rsi+0Fh]
0x1400b7b10  jmp     short loc_1400B7AC9
0x1400b7b12  lea     r8, [rbp+57h+var_98]
0x1400b7b16  mov     rdx, rsi
0x1400b7b19  mov     rcx, r14
0x1400b7b1c  call    FveDatasetVmkGetFvek
0x1400b7b21  mov     ebx, eax
0x1400b7b23  test    eax, eax
0x1400b7b25  jns     short loc_1400B7B65
0x1400b7b27  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b7b2e  lea     rax, WPP_GLOBAL_Control
0x1400b7b35  cmp     rcx, rax
0x1400b7b38  jz      short loc_1400B7B5C
0x1400b7b3a  mov     eax, [rcx+2Ch]
0x1400b7b3d  test    al, 10h
0x1400b7b3f  jz      short loc_1400B7B5C
0x1400b7b41  cmp     byte ptr [rcx+29h], 2
0x1400b7b45  jb      short loc_1400B7B5C
0x1400b7b47  mov     edx, 10h
0x1400b7b4c  mov     rcx, [rcx+18h]
0x1400b7b50  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x1400b7b57  call    WPP_SF_
0x1400b7b5c  mov     r13, qword ptr [rbp+57h+var_98]
0x1400b7b60  jmp     loc_1400B7953
0x1400b7b65  cmp     [rdi+3F8h], r13
0x1400b7b6c  jz      short loc_1400B7BBD
0x1400b7b6e  mov     rcx, [rbp+57h+P]
0x1400b7b72  lea     r9, [rbp+57h+var_48]
0x1400b7b76  mov     edx, 3
0x1400b7b7b  add     rcx, 40h ; '@'
0x1400b7b7f  lea     r8d, [rdx+2]
0x1400b7b83  call    FveDatasetGetFirst
0x1400b7b88  xor     ebx, ebx
0x1400b7b8a  cmp     eax, 0C0000225h
0x1400b7b8f  cmovnz  ebx, eax
0x1400b7b92  test    ebx, ebx
0x1400b7b94  jns     short loc_1400B7BBD
0x1400b7b96  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b7b9d  lea     rax, WPP_GLOBAL_Control
0x1400b7ba4  cmp     rcx, rax
0x1400b7ba7  jz      short loc_1400B7B5C
0x1400b7ba9  mov     eax, [rcx+2Ch]
0x1400b7bac  test    al, 10h
0x1400b7bae  jz      short loc_1400B7B5C
0x1400b7bb0  cmp     byte ptr [rcx+29h], 2
0x1400b7bb4  jb      short loc_1400B7B5C
0x1400b7bb6  mov     edx, 11h
0x1400b7bbb  jmp     short loc_1400B7B4C
  ... truncated ...
```
