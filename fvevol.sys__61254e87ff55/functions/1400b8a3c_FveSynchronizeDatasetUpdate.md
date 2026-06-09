# FveSynchronizeDatasetUpdate

- ea: `0x1400b8a3c`
- end: `0x1400b99de`
- name: `FveSynchronizeDatasetUpdate`
- size: `4002`
- prototype: `__int64 __fastcall(int, void *Src)`
- caller_count: `1`
- callee_count: `43`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140066554`

## callees

- `0x1400037f0`
- `0x140005324`
- `0x14000557c`
- `0x140005784`
- `0x140005e44`
- `0x140005e60`
- `0x1400062c4`
- `0x140008348`
- `0x140008e80`
- `0x140008f04`
- `0x140009cb4`
- `0x14000a694`
- `0x14000b998`
- `0x140013c5c`
- `0x140014ce8`
- `0x140017b40`
- `0x14001870c`
- `0x140022d40`
- `0x1400242c8`
- `0x1400251b4`
- `0x14002f334`
- `0x14005e7dc`
- `0x14005e868`
- `0x14005e9d8`
- `0x1400612fc`
- `0x140063bd4`
- `0x14008f3e8`
- `0x14009aa2c`
- `0x14009eed0`
- `0x1400a8500`
- `0x1400ad780`
- `0x1400adfbc`
- `0x1400ae57c`
- `0x1400b0938`
- `0x1400b6f14`
- `0x1400b8a3c`
- `0x1400c26a8`
- `0x1400c9ea0`
- `0x1400d1490`
- `0x1400e092c`
- `0x1400e6f90`
- `0x1400e89fc`
- `0x1400ef0f0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400b8b3f`
- `ntoskrnl!RtlCompareMemory` at `0x1400b8b3f`
- `ntoskrnl!KeBugCheckEx` at `0x1400b9923`
- `ntoskrnl!KeBugCheckEx` at `0x1400b9923`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b8c69`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b8c86`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b8c69`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b8c86`
- `ntoskrnl!ExAllocatePool2` at `0x1400b9207`
- `ntoskrnl!ExAllocatePool2` at `0x1400b9207`

## pseudocode

```c
__int64 __fastcall FveSynchronizeDatasetUpdate(_QWORD *a1, _DWORD *Src, __int64 a3)
{
  _DWORD *v4; // r14
  PDEVICE_OBJECT v6; // rcx
  int v7; // eax
  ULONG_PTR v8; // r12
  __int64 v9; // r15
  __int64 v10; // r13
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
  int FvekDatumFromVmk; // eax
  __int64 v36; // rcx
  int v37; // ebx
  int v38; // eax
  __int64 v39; // rcx
  _QWORD *v40; // rax
  int v41; // ebx
  int v42; // eax
  __int64 v43; // rax
  __int64 v44; // rbx
  __int64 v45; // rcx
  __int64 v46; // rcx
  void *Pool2; // rax
  __int64 v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // r8
  __int64 v52; // r15
  char v53; // r12
  __int64 v54; // rdx
  __int64 v55; // rcx
  bool v56; // zf
  __int64 v57; // rdx
  __int64 v58; // rcx
  PVOID v59; // rsi
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // rax
  __int64 v64; // r14
  __int64 v65; // rsi
  int v66; // eax
  __int64 Timer_high; // rdx
  __int64 v68; // r8
  __int64 v69; // rcx
  int v70; // ebx
  int v71; // eax
  __int64 v72; // rdx
  PDEVICE_OBJECT v73; // rcx
  __int64 v74; // rdx
  __int64 v75; // rcx
  void *v76; // rcx
  __int64 v77; // rcx
  PDEVICE_OBJECT v78; // rcx
  __int64 v79; // rdx
  _QWORD *v80; // rdx
  __int64 v81; // rcx
  int v82; // eax
  int v83; // eax
  __int64 v84; // rcx
  __int64 v85; // rax
  __int64 v86; // rax
  void *v87; // rcx
  __int64 v88; // rax
  __int64 v89; // r14
  __int64 v90; // rsi
  __int64 v91; // rdx
  __int64 v92; // rcx
  __int64 v93; // r8
  _QWORD *v94; // rdx
  __int64 v95; // rcx
  int v96; // eax
  _OWORD *v97; // rsi
  _OWORD *v98; // rax
  __int64 v99; // rsi
  __int64 v100; // rcx
  __int64 v101; // rdx
  __int64 v102; // rcx
  ULONG_PTR v103; // rsi
  __int64 v104; // rax
  ULONG_PTR BugCheckParameter4; // [rsp+20h] [rbp-79h]
  PVOID P; // [rsp+30h] [rbp-69h] BYREF
  __int64 v108; // [rsp+38h] [rbp-61h]
  __int64 v109; // [rsp+40h] [rbp-59h]
  PVOID v110; // [rsp+48h] [rbp-51h]
  PVOID v111; // [rsp+50h] [rbp-49h] BYREF
  int v112[2]; // [rsp+58h] [rbp-41h] BYREF
  void *v113; // [rsp+60h] [rbp-39h] BYREF
  int v114[2]; // [rsp+68h] [rbp-31h]
  PVOID Srca; // [rsp+70h] [rbp-29h]
  ULONG_PTR v116; // [rsp+78h] [rbp-21h]
  PVOID v117; // [rsp+80h] [rbp-19h]
  __int64 v118; // [rsp+88h] [rbp-11h] BYREF
  __int64 v119; // [rsp+90h] [rbp-9h] BYREF
  __int64 v120; // [rsp+98h] [rbp-1h] BYREF
  __int64 v121; // [rsp+A0h] [rbp+7h]
  PVOID v122; // [rsp+A8h] [rbp+Fh]
  __int64 v123; // [rsp+B0h] [rbp+17h] BYREF
  __int64 v124; // [rsp+B8h] [rbp+1Fh]
  int v125; // [rsp+100h] [rbp+67h] BYREF
  ULONG_PTR v126; // [rsp+118h] [rbp+7Fh] BYREF

  v4 = Src;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids);
  }
  v7 = *((_DWORD *)a1 + 202);
  v125 = 0;
  v8 = 0;
  P = 0;
  v9 = 0;
  v118 = 0;
  v10 = 0;
  v126 = 0;
  *(_QWORD *)v114 = 0;
  *(_QWORD *)v112 = 0;
  v108 = 0;
  v120 = 0;
  v123 = 0;
  v110 = 0;
  v111 = 0;
  v117 = 0;
  v113 = 0;
  v109 = 0;
  v119 = 0;
  if ( (v7 & 0x8000) != 0 )
  {
    updated = -1071579135;
    goto LABEL_297;
  }
  if ( (v7 & 0x4000) != 0 )
  {
    updated = -1071579102;
    goto LABEL_297;
  }
  v6 = (PDEVICE_OBJECT)a1[122];
  if ( !v6 )
  {
    updated = -1071579134;
    goto LABEL_297;
  }
  if ( (v4[1] & 0x7FFFFFFF) != 1 || (v124 = a1[1], RtlCompareMemory(&v6->Queue, v4 + 4, 0x10u) != 16) )
  {
    updated = -1073741811;
    goto LABEL_297;
  }
  Srca = 0;
  updated = FveDuplicateInformation(a1, &P);
  if ( updated < 0 )
    goto LABEL_33;
  v12 = P;
  v122 = P;
  if ( *((_WORD *)P + 5) > 1u )
  {
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(1, Src)
      && (*((_BYTE *)a1 + 4419) & 8) != 0
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
    updated = FveAddLegacyVirtualizationInfoToDataset(v12 + 8, v12[7], v15 * *((unsigned int *)a1 + 327), &v118);
    if ( updated < 0 )
      goto LABEL_33;
    v13 = FveDatasetCompress(v118);
  }
  else
  {
    v13 = FveWorksetCreateWithLength((char *)P + 64);
  }
  updated = v13;
  if ( v13 >= 0 )
  {
    updated = FveDatumUpdateVerify(v118, a3);
    if ( updated < 0 )
    {
      v20 = P;
      goto LABEL_295;
    }
    if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v16, Src) )
      LOBYTE(v10) = *(_BYTE *)(a3 + 8) & 1;
    v17 = FveDatumNestedExtractFirst(a3, 0xFFFF, 1, &v126);
    updated = v17;
    if ( v17 >= 0 )
    {
      v8 = v126;
      v116 = v126;
      if ( v126 )
      {
        Src = (_DWORD *)a1[127];
        if ( Src && (unsigned __int8)FveDatumKeyCompare(v126) )
        {
          FveDatumFree(v8);
          v8 = 0;
          v116 = 0;
        }
        v21 = v8;
        if ( v8 )
        {
LABEL_55:
          v22 = a1[101] & 2;
          v121 = v21;
          LODWORD(v126) = v22;
          if ( !v21 && !v22 )
            goto LABEL_57;
          if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v18, Src) )
          {
            if ( (_BYTE)v10 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids);
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
              updated = FveDatasetVmkGetFvek(v4, v21, v112);
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
                First = FveDatasetGetFirst((char *)P + 64, 3, 5, &v123);
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
                  WPP_SF_(v25->AttachedDevice, v26, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids);
LABEL_81:
                  v9 = *(_QWORD *)v112;
                  goto LABEL_32;
                }
              }
              v9 = *(_QWORD *)v112;
              *(_QWORD *)v114 = *(_QWORD *)v112;
              if ( (unsigned __int16)(*(_WORD *)(*(_QWORD *)v112 + 8LL) + 0x8000) <= 1u )
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
                WPP_SF_(v23->AttachedDevice, v24, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids);
                goto LABEL_32;
              }
              v28 = *((_DWORD *)a1 + 327);
              if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(1, Src) )
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
                    v33 = (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(
                                          v30,
                                          Src)
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
            goto LABEL_144;
          }
          if ( v21 )
          {
            Fvek = FveDatasetVmkGetFvek(v4, v21, v112);
            updated = Fvek;
            if ( Fvek >= 0 )
            {
              v9 = *(_QWORD *)v112;
            }
            else if ( Fvek != -1073741275 )
            {
              goto LABEL_81;
            }
            *(_QWORD *)v114 = v9;
          }
          Src = (_DWORD *)a1[127];
          if ( Src )
          {
            FvekDatumFromVmk = GetFvekDatumFromVmk((char *)P + 64, Src, &v120);
            updated = FvekDatumFromVmk;
            if ( FvekDatumFromVmk >= 0 )
            {
              v108 = v120;
              if ( v120 )
              {
                if ( !(unsigned __int8)FveDatumKeyCompare(v9) )
                {
                  if ( !(_DWORD)v126 )
                    goto LABEL_57;
                  if ( !v9 )
                    goto LABEL_126;
                  goto LABEL_125;
                }
LABEL_144:
                if ( (*(_DWORD *)(a1[15] + 48LL) & 0x400100) == 0 )
                  goto LABEL_156;
                updated = FveDatasetVmkGetAndDecryptDatum((_DWORD)v4, v21, 11, 1, (__int64)&v119);
                if ( updated < 0 )
                {
                  if ( v8 )
                  {
                    v10 = v119;
                    goto LABEL_33;
                  }
                  v43 = v119;
                  goto LABEL_155;
                }
                v44 = v119;
                v45 = a1[1];
                v109 = v119;
                if ( (unsigned __int8)FveAutoUnlockCompareMasterKey(v45, v119) )
                {
                  FveDatumFree(v44);
                  v43 = 0;
LABEL_155:
                  v109 = v43;
                  goto LABEL_156;
                }
                if ( (unsigned __int8)FveAutoUnlockCompareMasterKey(a1[1], 0)
                  || (int)FveAutoUnlockCheckBinding(v46, &v125) < 0
                  || !v125 )
                {
LABEL_156:
                  updated = FveWorksetCommit(v4, (char *)P + 64);
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
                  v52 = 0;
                  if ( !(unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(
                                        v48,
                                        Src)
                    || (v56 = (*((_BYTE *)a1 + 4419) & 8) == 0, LOBYTE(v125) = 0, v56) )
                  {
                    LOBYTE(v51) = 1;
                    updated = FvePrepareForFveInfoCopyUpdate(a1, *((unsigned int *)a1 + 577), v51);
                    if ( updated < 0 )
                    {
LABEL_202:
                      FveNvcWriteBackReset(a1);
                      v20 = v122;
                      v9 = *(_QWORD *)v114;
                      v8 = v116;
                      v10 = v109;
LABEL_295:
                      v19 = v108;
                      goto LABEL_35;
                    }
                    LOBYTE(v125) = 1;
                  }
                  v53 = 0;
                  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(
                                       v50,
                                       v49) )
                    v56 = (_BYTE)v10 == 0;
                  else
                    v56 = v110 == 0;
                  if ( !v56 )
                  {
                    FveRundownAllReadsAndWrites(a1);
                    v53 = 1;
                  }
                  if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(
                                       v55,
                                       v54)
                    && (*((_BYTE *)a1 + 4419) & 8) != 0 )
                  {
                    v59 = Srca;
                    updated = 0;
                  }
                  else
                  {
                    BugCheckParameter4 = v21;
                    v59 = Srca;
                    updated = FveWriteInformation(a1, BugCheckParameter4, 1);
                  }
                  IsEnabledDeviceUsageNoInline = Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(
                                                   v58,
                                                   v57);
                  v62 = 3221225472LL;
                  if ( IsEnabledDeviceUsageNoInline )
                  {
                    if ( (_BYTE)v10 )
                    {
                      if ( (updated & 0xC0000000) != 0xC0000000 )
                      {
                        v63 = a1[128];
                        if ( v63 && *(_WORD *)v63 >= 5u && *(_WORD *)(v63 + 2) >= 0x4Cu )
                          v52 = *(_QWORD *)(v63 + 68);
                        v64 = v121;
                        v65 = (__int64)v59 + 64;
                        v66 = FveResolveIceCryptoInfoV2((int)a1, v52);
                        if ( v66 < 0 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                        {
                          Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
                          if ( (Timer_high & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                            WPP_SF_d(
                              WPP_GLOBAL_Control->AttachedDevice,
                              21,
                              WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids,
                              (unsigned int)v66);
                        }
                        if ( a1[594] )
                        {
                          v69 = *(unsigned int *)(a1[1] + 9928LL);
                          if ( (v69 & 2) != 0 )
                          {
                            v70 = *((_DWORD *)a1 + 327);
                            if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(
                                                 v69,
                                                 Timer_high) )
                              v71 = FveFvekDataFromFvekDatum2(v70, v114[0]);
                            else
                              v71 = FveFvekDataFromFvekDatum(v70, v114[0]);
                            updated = v71;
                            if ( v71 < 0 )
                            {
                              v73 = WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
                                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                              {
                                goto LABEL_197;
                              }
                              v74 = 22;
LABEL_196:
                              WPP_SF_(v73->AttachedDevice, v74, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids);
LABEL_197:
                              LOBYTE(v72) = 1;
                              FveDeleteIceKey(a1, v72);
                              v117 = v113;
LABEL_198:
                              if ( v53 )
                                FveResumeAllReadsAndWrites((__int64)a1);
                              if ( (_BYTE)v125 )
                                FveCompleteFveInfoCopyUpdate(a1);
                              goto LABEL_202;
                            }
                            v75 = a1[596];
                            if ( v75 )
                            {
                              v76 = *(void **)(v75 + 152);
                              if ( v76 )
                              {
                                DeleteKey(v76);
                                *(_QWORD *)(a1[596] + 152LL) = 0;
                              }
                              v77 = a1[596];
                              v117 = 0;
                              *(_QWORD *)(v77 + 152) = v113;
                            }
                            else
                            {
                              updated = FveIceSimAlloc(a1, &v113);
                              if ( updated < 0 )
                              {
                                v73 = WPP_GLOBAL_Control;
                                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
                                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                                {
                                  goto LABEL_197;
                                }
                                v74 = 23;
                                goto LABEL_196;
                              }
                              v117 = v113;
                            }
                          }
                        }
                        v78 = (PDEVICE_OBJECT)a1[126];
                        if ( v78 )
                        {
                          DeleteKey(v78);
                          a1[126] = 0;
                        }
                        v79 = a1[594];
                        if ( !v79 || !*(_DWORD *)(v79 + 88) )
                        {
                          a1[126] = v110;
                          v110 = 0;
                        }
                        if ( (*(_DWORD *)(v124 + 9928) & 0x10) != 0 )
                        {
                          if ( v79 )
                          {
                            if ( *(_DWORD *)(v79 + 88) )
                            {
                              v78 = WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                                && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                              {
                                WPP_SF_(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  24,
                                  WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids);
                              }
                            }
                          }
                        }
                        if ( (unsigned int)Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline(
                                             v78,
                                             v79,
                                             v68) )
                        {
                          if ( !a1[594] )
                          {
                            updated = FveHwAccelTryConfigureCryptoOffload((__int64)a1, v65, v64);
                            if ( updated < 0 )
                            {
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                                && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                              {
                                WPP_SF_d(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  25,
                                  WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids,
                                  (unsigned int)updated);
                              }
                              updated = 0;
                            }
                          }
                        }
                        if ( (a1[101] & 0x100) != 0 )
                        {
                          v80 = (_QWORD *)a1[92];
                          if ( v80 )
                          {
                            if ( *v80 )
                            {
                              FveEowClearKey(a1);
                              FveEowSetKey(v81, a1[92], &v111);
                            }
                          }
                        }
                        v82 = *((_DWORD *)a1 + 202);
                        if ( (v82 & 0x17F) != 0 && (v82 & 0x40) == 0 )
                          UpdateDynamicContext(a1, v64, v65);
                      }
                      v83 = *((_DWORD *)a1 + 213);
                      if ( (v83 & 0x40) == 0
                        && (v83 & 0x19) != 0
                        && ((v84 = a1[126]) == 0 && ((v85 = a1[594]) == 0 || !*(_DWORD *)(v85 + 88))
                         || (v86 = a1[594]) != 0 && *(_DWORD *)(v86 + 88) && v84) )
                      {
LABEL_293:
                        KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
                      }
                      goto LABEL_275;
                    }
                  }
                  else if ( v110 )
                  {
                    if ( (updated & 0xC0000000) != 0xC0000000 )
                    {
                      v87 = (void *)a1[126];
                      if ( v87 )
                        DeleteKey(v87);
                      a1[126] = v110;
                      v88 = a1[128];
                      v110 = 0;
                      if ( v88 && *(_WORD *)v88 >= 5u && *(_WORD *)(v88 + 2) >= 0x4Cu )
                        v52 = *(_QWORD *)(v88 + 68);
                      v89 = v121;
                      v90 = (__int64)v59 + 64;
                      FveResolveIceCryptoInfo((int)a1, v52);
                      if ( a1[594] )
                      {
                        v92 = *(unsigned int *)(a1[1] + 9928LL);
                        if ( (v92 & 2) != 0 )
                          FveIceSimAlloc(a1, 0);
                      }
                      if ( (unsigned int)Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline(
                                           v92,
                                           v91,
                                           v93) )
                      {
                        if ( !a1[594] )
                        {
                          updated = FveHwAccelTryConfigureCryptoOffload((__int64)a1, v90, v89);
                          if ( updated < 0 )
                          {
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                            {
                              WPP_SF_d(
                                WPP_GLOBAL_Control->AttachedDevice,
                                26,
                                WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids,
                                (unsigned int)updated);
                            }
                            updated = 0;
                          }
                        }
                      }
                      if ( (a1[101] & 0x100) != 0 )
                      {
                        v94 = (_QWORD *)a1[92];
                        if ( v94 )
                        {
                          if ( *v94 )
                          {
                            FveEowClearKey(a1);
                            FveEowSetKey(v95, a1[92], &v111);
                          }
                        }
                      }
                      v96 = *((_DWORD *)a1 + 202);
                      if ( (v96 & 0x17F) != 0 && (v96 & 0x40) == 0 )
                        UpdateDynamicContext(a1, v89, v90);
                    }
LABEL_275:
                    FveResumeAllReadsAndWrites((__int64)a1);
                    v53 = 0;
                  }
                  if ( !(unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(
                                        v62,
                                        v61)
                    || (*((_BYTE *)a1 + 4419) & 8) == 0 )
                  {
                    FveCompleteFveInfoCopyUpdate(a1);
                    LOBYTE(v125) = 0;
                  }
                  if ( (updated & 0xC0000000) == 0xC0000000 )
                    goto LABEL_198;
                  v97 = P;
                  memmove(P, Srca, 0x10000u);
                  v98 = (_OWORD *)a1[122];
                  *v98 = *v97;
                  v98[1] = v97[1];
                  v98[2] = v97[2];
                  v98[3] = v97[3];
                  v98[4] = v97[4];
                  v98[5] = v97[5];
                  v98[6] = v97[6];
                  v99 = _InterlockedExchange64(a1 + 123, (__int64)v97);
                  v100 = a1[123];
                  v122 = (PVOID)v99;
                  a1[128] = 0;
                  if ( (int)FveFindExtendedInfoInDataset(v100 + 64, a1 + 128) < 0 )
                    a1[128] = 0;
                  v103 = v116;
                  if ( v116 )
                  {
                    v102 = a1[127];
                    if ( v102 )
                      FveDatumFree(v102);
                    a1[127] = v103;
                    v116 = 0;
                  }
                  if ( v109 )
                  {
                    FveAutoUnlockCacheMasterKey(a1[1], v109, *a1);
                    v109 = 0;
                  }
                  if ( (_DWORD)v126 )
                    goto LABEL_198;
                  if ( !(unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(
                                        v102,
                                        v101) )
                    goto LABEL_198;
                  if ( a1[126] )
                    goto LABEL_198;
                  v104 = a1[594];
                  if ( v104 )
                  {
                    if ( *(_DWORD *)(v104 + 88) )
                      goto LABEL_198;
                  }
                  goto LABEL_293;
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
                v19 = v120;
                v10 = v109;
                goto LABEL_34;
              }
              v108 = 0;
            }
          }
          if ( v9 )
          {
LABEL_125:
            v36 = 1;
            if ( (unsigned __int16)(*(_WORD *)(v9 + 8) + 0x8000) <= 1u )
            {
              updated = -1073741811;
              goto LABEL_32;
            }
LABEL_126:
            v37 = *((_DWORD *)a1 + 327);
            if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v36, Src) )
              v38 = FveFvekDataFromFvekDatum2(v37, v9);
            else
              v38 = FveFvekDataFromFvekDatum(v37, v9);
            updated = v38;
            if ( v38 < 0 )
              goto LABEL_32;
            if ( (a1[101] & 0x100) != 0 )
            {
              v40 = (_QWORD *)a1[92];
              if ( v40 )
              {
                if ( *v40 )
                {
                  v41 = *((_DWORD *)a1 + 327);
                  v42 = (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(
                                        v39,
                                        Src)
                      ? FveFvekDataFromFvekDatum2(v41, v9)
                      : FveFvekDataFromFvekDatum(v41, v9);
                  updated = v42;
                  if ( v42 < 0 )
                    goto LABEL_32;
                }
              }
            }
            goto LABEL_144;
          }
          goto LABEL_144;
        }
      }
    }
    else
    {
      if ( v17 != -1073741275 )
      {
        v8 = v126;
LABEL_32:
        v10 = v109;
        goto LABEL_33;
      }
      v116 = 0;
    }
    v21 = a1[127];
    goto LABEL_55;
  }
LABEL_33:
  v19 = v108;
LABEL_34:
  v20 = P;
LABEL_35:
  if ( v20 )
    ExFreePoolWithTag(v20, 0x30455646u);
  if ( Srca )
    ExFreePoolWithTag(Srca, 0x30455646u);
  if ( v110 )
    DeleteKey(v110);
  v6 = (PDEVICE_OBJECT)v111;
  if ( v111 )
    DeleteKey(v111);
  if ( v8 )
    FveDatumFree(v8);
  if ( v9 )
    FveDatumFree(v9);
  if ( v19 )
    FveDatumFree(v19);
LABEL_297:
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v6, Src) )
  {
    if ( v123 )
      FveDatumFree(v123);
    if ( v117 )
      DeleteKey(v117);
  }
  if ( v10 )
    FveDatumFree(v10);
  if ( v118 )
    FveWorksetFree(v118);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      27,
      WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids,
      (unsigned int)updated);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1400b8a3c  mov     [rsp-8+arg_8], rbx
0x1400b8a41  push    rbp
0x1400b8a42  push    rsi
0x1400b8a43  push    rdi
0x1400b8a44  push    r12
0x1400b8a46  push    r13
0x1400b8a48  push    r14
0x1400b8a4a  push    r15
0x1400b8a4c  lea     rbp, [rsp-27h]
0x1400b8a51  sub     rsp, 0C0h
0x1400b8a58  mov     rsi, r8
0x1400b8a5b  mov     r14, rdx
0x1400b8a5e  mov     rdi, rcx
0x1400b8a61  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b8a68  lea     rax, WPP_GLOBAL_Control
0x1400b8a6f  cmp     rcx, rax
0x1400b8a72  jz      short loc_1400B8A96
0x1400b8a74  mov     eax, [rcx+2Ch]
0x1400b8a77  test    al, 10h
0x1400b8a79  jz      short loc_1400B8A96
0x1400b8a7b  cmp     byte ptr [rcx+29h], 5
0x1400b8a7f  jb      short loc_1400B8A96
0x1400b8a81  mov     rcx, [rcx+18h]
0x1400b8a85  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x1400b8a8c  mov     edx, 0Ch
0x1400b8a91  call    WPP_SF_
0x1400b8a96  mov     eax, [rdi+328h]
0x1400b8a9c  xor     ebx, ebx
0x1400b8a9e  mov     [rbp+57h+arg_0], ebx
0x1400b8aa1  mov     r12d, ebx
0x1400b8aa4  mov     [rbp+57h+P], rbx
0x1400b8aa8  mov     r15d, ebx
0x1400b8aab  mov     [rbp+57h+var_68], rbx
0x1400b8aaf  mov     r13d, ebx
0x1400b8ab2  mov     [rbp+57h+arg_18], rbx
0x1400b8ab6  mov     qword ptr [rbp+57h+var_88], rbx
0x1400b8aba  mov     qword ptr [rbp+57h+var_98], rbx
0x1400b8abe  mov     [rbp+57h+var_B8], rbx
0x1400b8ac2  mov     [rbp+57h+var_58], rbx
0x1400b8ac6  mov     [rbp+57h+var_40], rbx
0x1400b8aca  mov     [rbp+57h+var_A8], rbx
0x1400b8ace  mov     [rbp+57h+var_A0], rbx
0x1400b8ad2  mov     [rbp+57h+var_70], rbx
0x1400b8ad6  mov     [rbp+57h+var_90], rbx
0x1400b8ada  mov     [rbp+57h+var_B0], rbx
0x1400b8ade  mov     [rbp+57h+var_60], rbx
0x1400b8ae2  bt      eax, 0Fh
0x1400b8ae6  jnb     short loc_1400B8AF2
0x1400b8ae8  mov     ebx, 0C0210001h
0x1400b8aed  jmp     loc_1400B9942
0x1400b8af2  bt      eax, 0Eh
0x1400b8af6  jnb     short loc_1400B8B02
0x1400b8af8  mov     ebx, 0C0210022h
0x1400b8afd  jmp     loc_1400B9942
0x1400b8b02  mov     rcx, [rdi+3D0h]
0x1400b8b09  test    rcx, rcx
0x1400b8b0c  jnz     short loc_1400B8B18
0x1400b8b0e  mov     ebx, 0C0210002h
0x1400b8b13  jmp     loc_1400B9942
0x1400b8b18  mov     eax, [r14+4]
0x1400b8b1c  btr     eax, 1Fh
0x1400b8b20  cmp     eax, 1
0x1400b8b23  jnz     loc_1400B993D
0x1400b8b29  mov     rax, [rdi+8]
0x1400b8b2d  lea     rdx, [r14+10h]; Source2
0x1400b8b31  add     rcx, 50h ; 'P'; Source1
0x1400b8b35  mov     [rbp+57h+var_38], rax
0x1400b8b39  mov     r8d, 10h; Length
0x1400b8b3f  call    cs:__imp_RtlCompareMemory
0x1400b8b46  nop     dword ptr [rax+rax+00h]
0x1400b8b4b  cmp     rax, 10h
0x1400b8b4f  jnz     loc_1400B993D
0x1400b8b55  lea     rdx, [rbp+57h+P]
0x1400b8b59  mov     [rbp+57h+Src], rbx
0x1400b8b5d  mov     rcx, rdi
0x1400b8b60  call    FveDuplicateInformation
0x1400b8b65  mov     ebx, eax
0x1400b8b67  test    eax, eax
0x1400b8b69  js      loc_1400B8C57
0x1400b8b6f  mov     rbx, [rbp+57h+P]
0x1400b8b73  mov     ecx, 1
0x1400b8b78  mov     [rbp+57h+var_48], rbx
0x1400b8b7c  cmp     [rbx+0Ah], cx
0x1400b8b80  ja      short loc_1400B8B96
0x1400b8b82  lea     rcx, [rbx+40h]; Src
0x1400b8b86  xor     r8d, r8d
0x1400b8b89  mov     edx, [rcx]
0x1400b8b8b  lea     r9, [rbp+57h+var_68]
0x1400b8b8f  call    FveWorksetCreateWithLength
0x1400b8b94  jmp     short loc_1400B8BF1
0x1400b8b96  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400b8b9b  test    eax, eax
0x1400b8b9d  jz      short loc_1400B8BA8
0x1400b8b9f  test    byte ptr [rdi+1143h], 8
0x1400b8ba6  jnz     short loc_1400B8BBA
0x1400b8ba8  mov     rax, [rdi+3D0h]
0x1400b8baf  mov     ecx, 1
0x1400b8bb4  cmp     [rax+0Ah], cx
0x1400b8bb8  jnz     short loc_1400B8BBE
0x1400b8bba  xor     eax, eax
0x1400b8bbc  jmp     short loc_1400B8BC6
0x1400b8bbe  mov     eax, [rax+1Ch]
0x1400b8bc1  test    eax, eax
0x1400b8bc3  cmovz   eax, ecx
0x1400b8bc6  mov     r8d, [rdi+51Ch]
0x1400b8bcd  lea     rcx, [rbx+40h]
0x1400b8bd1  mov     rdx, [rbx+38h]
0x1400b8bd5  lea     r9, [rbp+57h+var_68]
0x1400b8bd9  imul    r8, rax
0x1400b8bdd  call    FveAddLegacyVirtualizationInfoToDataset
0x1400b8be2  mov     ebx, eax
0x1400b8be4  test    eax, eax
0x1400b8be6  js      short loc_1400B8C57
0x1400b8be8  mov     rcx, [rbp+57h+var_68]
0x1400b8bec  call    FveDatasetCompress
0x1400b8bf1  mov     ebx, eax
0x1400b8bf3  test    eax, eax
0x1400b8bf5  js      short loc_1400B8C57
0x1400b8bf7  mov     rcx, [rbp+57h+var_68]
0x1400b8bfb  mov     rdx, rsi
0x1400b8bfe  call    FveDatumUpdateVerify
0x1400b8c03  mov     ebx, eax
0x1400b8c05  test    eax, eax
0x1400b8c07  js      loc_1400B9930
0x1400b8c0d  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400b8c12  test    eax, eax
0x1400b8c14  jz      short loc_1400B8C1E
0x1400b8c16  mov     r13b, [rsi+8]
0x1400b8c1a  and     r13b, 1
0x1400b8c1e  mov     edx, 0FFFFh
0x1400b8c23  lea     r9, [rbp+57h+arg_18]
0x1400b8c27  mov     r8d, 1
0x1400b8c2d  mov     rcx, rsi
0x1400b8c30  call    FveDatumNestedExtractFirst
0x1400b8c35  mov     ebx, eax
0x1400b8c37  test    eax, eax
0x1400b8c39  jns     loc_1400B8CDE
0x1400b8c3f  cmp     eax, 0C0000225h
0x1400b8c44  jnz     short loc_1400B8C4F
0x1400b8c46  mov     [rbp+57h+var_78], r12
0x1400b8c4a  jmp     loc_1400B8D1A
0x1400b8c4f  mov     r12, [rbp+57h+arg_18]
0x1400b8c53  mov     r13, [rbp+57h+var_B0]
0x1400b8c57  mov     rdi, [rbp+57h+var_B8]
0x1400b8c5b  mov     rcx, [rbp+57h+P]; P
0x1400b8c5f  test    rcx, rcx
0x1400b8c62  jz      short loc_1400B8C75
0x1400b8c64  mov     edx, 30455646h; Tag
0x1400b8c69  call    cs:__imp_ExFreePoolWithTag
0x1400b8c70  nop     dword ptr [rax+rax+00h]
0x1400b8c75  mov     rax, [rbp+57h+Src]
0x1400b8c79  test    rax, rax
0x1400b8c7c  jz      short loc_1400B8C92
0x1400b8c7e  mov     edx, 30455646h; Tag
0x1400b8c83  mov     rcx, rax; P
0x1400b8c86  call    cs:__imp_ExFreePoolWithTag
0x1400b8c8d  nop     dword ptr [rax+rax+00h]
0x1400b8c92  mov     rcx, [rbp+57h+var_A8]; P
0x1400b8c96  test    rcx, rcx
0x1400b8c99  jz      short loc_1400B8CA0
0x1400b8c9b  call    DeleteKey
0x1400b8ca0  mov     rcx, [rbp+57h+var_A0]; P
0x1400b8ca4  test    rcx, rcx
0x1400b8ca7  jz      short loc_1400B8CAE
0x1400b8ca9  call    DeleteKey
0x1400b8cae  test    r12, r12
0x1400b8cb1  jz      short loc_1400B8CBB
0x1400b8cb3  mov     rcx, r12
0x1400b8cb6  call    FveDatumFree
0x1400b8cbb  test    r15, r15
0x1400b8cbe  jz      short loc_1400B8CC8
0x1400b8cc0  mov     rcx, r15
0x1400b8cc3  call    FveDatumFree
0x1400b8cc8  test    rdi, rdi
0x1400b8ccb  jz      loc_1400B9942
0x1400b8cd1  mov     rcx, rdi
0x1400b8cd4  call    FveDatumFree
0x1400b8cd9  jmp     loc_1400B9942
0x1400b8cde  mov     r12, [rbp+57h+arg_18]
0x1400b8ce2  mov     [rbp+57h+var_78], r12
0x1400b8ce6  test    r12, r12
0x1400b8ce9  jz      short loc_1400B8D1A
0x1400b8ceb  mov     rdx, [rdi+3F8h]
0x1400b8cf2  test    rdx, rdx
0x1400b8cf5  jz      short loc_1400B8D12
0x1400b8cf7  mov     rcx, r12
0x1400b8cfa  call    FveDatumKeyCompare
0x1400b8cff  test    al, al
0x1400b8d01  jz      short loc_1400B8D12
0x1400b8d03  mov     rcx, r12
0x1400b8d06  call    FveDatumFree
0x1400b8d0b  xor     r12d, r12d
0x1400b8d0e  mov     [rbp+57h+var_78], r12
0x1400b8d12  mov     rsi, r12
0x1400b8d15  test    r12, r12
0x1400b8d18  jnz     short loc_1400B8D21
0x1400b8d1a  mov     rsi, [rdi+3F8h]
0x1400b8d21  mov     ebx, [rdi+328h]
0x1400b8d27  and     ebx, 2
0x1400b8d2a  mov     [rbp+57h+var_50], rsi
0x1400b8d2e  mov     dword ptr [rbp+57h+arg_18], ebx
0x1400b8d31  test    rsi, rsi
0x1400b8d34  jnz     short loc_1400B8D44
0x1400b8d36  test    ebx, ebx
0x1400b8d38  jnz     short loc_1400B8D44
0x1400b8d3a  mov     ebx, 0C0210009h
0x1400b8d3f  jmp     loc_1400B8C53
0x1400b8d44  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400b8d49  test    eax, eax
0x1400b8d4b  jz      loc_1400B9009
0x1400b8d51  test    r13b, r13b
0x1400b8d54  jz      loc_1400B9145
0x1400b8d5a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b8d61  lea     rax, WPP_GLOBAL_Control
0x1400b8d68  cmp     rcx, rax
0x1400b8d6b  jz      short loc_1400B8D96
0x1400b8d6d  mov     eax, [rcx+2Ch]
0x1400b8d70  test    al, 10h
0x1400b8d72  jz      short loc_1400B8D8F
0x1400b8d74  cmp     byte ptr [rcx+29h], 5
0x1400b8d78  jb      short loc_1400B8D8F
0x1400b8d7a  mov     rcx, [rcx+18h]
0x1400b8d7e  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x1400b8d85  mov     edx, 0Dh
0x1400b8d8a  call    WPP_SF_
0x1400b8d8f  lea     rax, WPP_GLOBAL_Control
0x1400b8d96  test    ebx, ebx
0x1400b8d98  jnz     short loc_1400B8DDE
0x1400b8d9a  mov     ebx, 0C0210009h
0x1400b8d9f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b8da6  cmp     rcx, rax
0x1400b8da9  jz      loc_1400B8C53
0x1400b8daf  mov     eax, [rcx+2Ch]
0x1400b8db2  test    al, 10h
0x1400b8db4  jz      loc_1400B8C53
0x1400b8dba  cmp     byte ptr [rcx+29h], 2
0x1400b8dbe  jb      loc_1400B8C53
0x1400b8dc4  mov     edx, 0Eh
0x1400b8dc9  mov     rcx, [rcx+18h]
0x1400b8dcd  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x1400b8dd4  call    WPP_SF_
0x1400b8dd9  jmp     loc_1400B8C53
0x1400b8dde  test    rsi, rsi
0x1400b8de1  jnz     short loc_1400B8E12
0x1400b8de3  mov     ebx, 0C000000Dh
0x1400b8de8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b8def  cmp     rcx, rax
0x1400b8df2  jz      loc_1400B8C53
0x1400b8df8  mov     eax, [rcx+2Ch]
0x1400b8dfb  test    al, 10h
0x1400b8dfd  jz      loc_1400B8C53
0x1400b8e03  cmp     byte ptr [rcx+29h], 2
0x1400b8e07  jb      loc_1400B8C53
0x1400b8e0d  lea     edx, [rsi+0Fh]
0x1400b8e10  jmp     short loc_1400B8DC9
0x1400b8e12  lea     r8, [rbp+57h+var_98]
0x1400b8e16  mov     rdx, rsi
0x1400b8e19  mov     rcx, r14
0x1400b8e1c  call    FveDatasetVmkGetFvek
0x1400b8e21  mov     ebx, eax
0x1400b8e23  test    eax, eax
0x1400b8e25  jns     short loc_1400B8E65
0x1400b8e27  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b8e2e  lea     rax, WPP_GLOBAL_Control
0x1400b8e35  cmp     rcx, rax
0x1400b8e38  jz      short loc_1400B8E5C
0x1400b8e3a  mov     eax, [rcx+2Ch]
0x1400b8e3d  test    al, 10h
0x1400b8e3f  jz      short loc_1400B8E5C
0x1400b8e41  cmp     byte ptr [rcx+29h], 2
0x1400b8e45  jb      short loc_1400B8E5C
0x1400b8e47  mov     edx, 10h
0x1400b8e4c  mov     rcx, [rcx+18h]
0x1400b8e50  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x1400b8e57  call    WPP_SF_
0x1400b8e5c  mov     r15, qword ptr [rbp+57h+var_98]
0x1400b8e60  jmp     loc_1400B8C53
0x1400b8e65  cmp     [rdi+3F8h], r15
0x1400b8e6c  jz      short loc_1400B8EBD
0x1400b8e6e  mov     rcx, [rbp+57h+P]
0x1400b8e72  lea     r9, [rbp+57h+var_40]
0x1400b8e76  mov     edx, 3
0x1400b8e7b  add     rcx, 40h ; '@'
0x1400b8e7f  lea     r8d, [rdx+2]
0x1400b8e83  call    FveDatasetGetFirst
0x1400b8e88  xor     ebx, ebx
0x1400b8e8a  cmp     eax, 0C0000225h
0x1400b8e8f  cmovnz  ebx, eax
0x1400b8e92  test    ebx, ebx
0x1400b8e94  jns     short loc_1400B8EBD
0x1400b8e96  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b8e9d  lea     rax, WPP_GLOBAL_Control
0x1400b8ea4  cmp     rcx, rax
0x1400b8ea7  jz      short loc_1400B8E5C
0x1400b8ea9  mov     eax, [rcx+2Ch]
0x1400b8eac  test    al, 10h
0x1400b8eae  jz      short loc_1400B8E5C
0x1400b8eb0  cmp     byte ptr [rcx+29h], 2
0x1400b8eb4  jb      short loc_1400B8E5C
0x1400b8eb6  mov     edx, 11h
  ... truncated ...
```
