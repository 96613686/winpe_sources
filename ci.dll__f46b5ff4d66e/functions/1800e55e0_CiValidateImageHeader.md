# CiValidateImageHeader

- ea: `0x1800e55e0`
- end: `0x1800e6907`
- name: `CiValidateImageHeader`
- size: `4903`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int, __int64, __int64, PEPROCESS Process, __int64, int, __int64, char, char, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `42`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x180010094`
- `0x180010128`
- `0x18001d1e8`
- `0x18002bef0`
- `0x18002bfd0`
- `0x18002c040`
- `0x180058c2c`
- `0x1800597cc`
- `0x18005dd00`
- `0x18005f96c`
- `0x180060140`
- `0x180063d3c`
- `0x180064068`
- `0x180064160`
- `0x180064234`
- `0x1800643c4`
- `0x18006b0d0`
- `0x18006bbfc`
- `0x18007423c`
- `0x180074b9c`
- `0x18008bc2c`
- `0x180094950`
- `0x18009516c`
- `0x180095528`
- `0x180097ae8`
- `0x180098818`
- `0x180098ab4`
- `0x180099688`
- `0x180099bd0`
- `0x18009ca38`
- `0x18009cf10`
- `0x18009eb60`
- `0x18009eef4`
- `0x1800a0aa8`
- `0x1800a2a68`
- `0x1800a39cc`
- `0x1800a5158`
- `0x1800aaf78`
- `0x1800b3c18`
- `0x1800db63c`
- `0x1800e4cb8`
- `0x1800e55e0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800e5717`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800e5717`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800e5c54`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800e5c54`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1800e6867`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1800e6867`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1800e572c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1800e572c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e6841`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e6841`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800e6873`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800e6873`
- `ntoskrnl!PsGetProcessProtection` at `0x1800e57bd`
- `ntoskrnl!PsGetProcessProtection` at `0x1800e6471`
- `ntoskrnl!PsGetProcessProtection` at `0x1800e57bd`
- `ntoskrnl!PsGetProcessProtection` at `0x1800e6471`
- `ntoskrnl!PsIsProtectedProcess` at `0x1800e59e9`
- `ntoskrnl!PsIsProtectedProcess` at `0x1800e5a08`
- `ntoskrnl!PsIsProtectedProcess` at `0x1800e59e9`
- `ntoskrnl!PsIsProtectedProcess` at `0x1800e5a08`
- `ntoskrnl!IoClearActivityIdThread` at `0x1800e6883`
- `ntoskrnl!IoClearActivityIdThread` at `0x1800e6883`
- `ntoskrnl!EtwActivityIdControl` at `0x1800e56db`
- `ntoskrnl!EtwActivityIdControl` at `0x1800e56db`
- `ntoskrnl!IoSetActivityIdThread` at `0x1800e56eb`
- `ntoskrnl!IoSetActivityIdThread` at `0x1800e56eb`
- `HAL!KeQueryPerformanceCounter` at `0x1800e56fd`
- `HAL!KeQueryPerformanceCounter` at `0x1800e6628`
- `HAL!KeQueryPerformanceCounter` at `0x1800e56fd`
- `HAL!KeQueryPerformanceCounter` at `0x1800e6628`

## pseudocode

```c
__int64 __fastcall CiValidateImageHeader(
        struct _FILE_OBJECT *a1,
        void *a2,
        int a3,
        __int64 a4,
        int a5,
        int *a6,
        unsigned __int8 *a7,
        PEPROCESS Process,
        __int64 a9,
        int a10,
        _QWORD *a11,
        char a12,
        char a13,
        ULONGLONG a14,
        int *a15,
        _QWORD *a16,
        __int64 a17)
{
  struct _FILE_OBJECT *v17; // r15
  _BYTE *Keyword; // r12
  _DWORD *v19; // rax
  __int64 v20; // rsi
  unsigned int ActionsForImage; // ebx
  char v22; // r14
  char v23; // r13
  int v24; // r9d
  __int64 v25; // rdx
  signed int fixed; // edi
  unsigned int v27; // r12d
  int v28; // r14d
  char v29; // cl
  unsigned int v30; // r15d
  bool v31; // zf
  int *v32; // rcx
  int ActionsForImageWithToken; // eax
  struct _FILE_OBJECT *v34; // rdi
  int IsEnabledDeviceUsageNoInline; // eax
  int v36; // r9d
  int *v37; // rcx
  __int64 v38; // rsi
  int v39; // ecx
  int v40; // r8d
  int v41; // ecx
  _DWORD *v42; // rdi
  char v43; // r8
  int v44; // ecx
  int *v45; // rcx
  int v46; // eax
  int *v47; // r15
  char v48; // r14
  int v49; // eax
  int v50; // eax
  int v51; // r13d
  PVOID v52; // rcx
  int v53; // edx
  int v54; // eax
  char v55; // r15
  __int64 v56; // r8
  int v57; // ecx
  int v58; // eax
  __int64 (__fastcall **v59)(); // rcx
  int *v60; // rcx
  int v61; // eax
  char v62; // r13
  int v63; // ecx
  int v64; // eax
  const void *v65; // rdx
  int v66; // ecx
  unsigned int v67; // r14d
  __int64 v68; // r13
  int v69; // ecx
  int v70; // r9d
  int v71; // eax
  __int64 v72; // r15
  int v73; // r10d
  __int64 v74; // r8
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // r14
  int v78; // eax
  __int64 v79; // r9
  _DWORD *v80; // r9
  _QWORD *v81; // rbx
  __int64 v82; // r9
  int v83; // ecx
  int v84; // ecx
  _QWORD *v85; // rcx
  __int64 (__fastcall *v86)(_QWORD); // rax
  int v88; // [rsp+20h] [rbp-E0h]
  int v89; // [rsp+20h] [rbp-E0h]
  ULONGLONG Size; // [rsp+30h] [rbp-D0h]
  ULONGLONG Sizea; // [rsp+30h] [rbp-D0h]
  int v92; // [rsp+38h] [rbp-C8h]
  int v93; // [rsp+48h] [rbp-B8h]
  char v94[4]; // [rsp+80h] [rbp-80h] BYREF
  int v95; // [rsp+84h] [rbp-7Ch]
  EVENT_DESCRIPTOR v96; // [rsp+88h] [rbp-78h] BYREF
  PFILE_OBJECT FileObject; // [rsp+98h] [rbp-68h]
  __int64 v98; // [rsp+A0h] [rbp-60h]
  char v99; // [rsp+A8h] [rbp-58h]
  int v100; // [rsp+ACh] [rbp-54h]
  __int16 v101; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v102; // [rsp+B8h] [rbp-48h] BYREF
  int v103; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v104; // [rsp+C4h] [rbp-3Ch]
  int *v105; // [rsp+C8h] [rbp-38h]
  PVOID BaseAddress; // [rsp+D0h] [rbp-30h]
  int v107; // [rsp+D8h] [rbp-28h] BYREF
  int v108; // [rsp+DCh] [rbp-24h]
  unsigned int v109; // [rsp+E0h] [rbp-20h] BYREF
  int v110; // [rsp+E4h] [rbp-1Ch] BYREF
  __int64 v111; // [rsp+E8h] [rbp-18h] BYREF
  int v112[2]; // [rsp+F0h] [rbp-10h]
  int v113[2]; // [rsp+F8h] [rbp-8h]
  int v114; // [rsp+100h] [rbp+0h] BYREF
  unsigned int v115; // [rsp+104h] [rbp+4h] BYREF
  __int64 QuadPart; // [rsp+108h] [rbp+8h] BYREF
  int *v117; // [rsp+110h] [rbp+10h]
  _BYTE *v118; // [rsp+118h] [rbp+18h]
  __int64 v119; // [rsp+120h] [rbp+20h]
  _DWORD *v120; // [rsp+128h] [rbp+28h]
  struct _UNICODE_STRING DestinationString; // [rsp+130h] [rbp+30h] BYREF
  LARGE_INTEGER PerformanceCounter; // [rsp+140h] [rbp+40h]
  _QWORD *v123; // [rsp+148h] [rbp+48h]
  __int64 v124; // [rsp+150h] [rbp+50h]
  GUID ActivityId; // [rsp+158h] [rbp+58h] BYREF
  __int128 v126; // [rsp+168h] [rbp+68h] BYREF

  v17 = a1;
  Keyword = (_BYTE *)a14;
  v105 = a15;
  BaseAddress = a2;
  *(_QWORD *)v112 = a9;
  FileObject = a1;
  v123 = a16;
  *(_QWORD *)v113 = a11;
  v19 = (_DWORD *)*a11;
  v117 = a6;
  v119 = a17;
  v20 = 0;
  v120 = v19;
  v118 = a7;
  ActionsForImage = 0;
  v22 = *a7;
  LODWORD(v19) = *a7;
  v111 = 0;
  v109 = 0;
  v103 = 0;
  v94[0] = 0;
  v102 = 0;
  v108 = 0;
  v114 = 0;
  v110 = 0;
  v107 = 0;
  v101 = 0;
  v104 = (unsigned int)v19 >> 2;
  v115 = (unsigned int)v19 >> 2;
  QuadPart = a4;
  v100 = a3;
  v98 = (__int64)Process;
  v96.Keyword = a14;
  v126 = 0;
  v95 = -1073740760;
  ActivityId = 0;
  DestinationString = 0;
  EtwActivityIdControl(3u, &ActivityId);
  v124 = IoSetActivityIdThread(&ActivityId);
  PerformanceCounter = KeQueryPerformanceCounter(0);
  *Keyword = 1;
  CiInitializePhase2();
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(&g_CipPolicyLock, 0);
  v23 = a12;
  LOBYTE(v24) = a12;
  CiLogFileRequestedValidationEvent((_DWORD)v17 + 88, Process, a10, v24, &CiValidateImageHeaderStart);
  fixed = CipFixImageType(
            (_DWORD)BaseAddress,
            (unsigned int)&v103,
            (unsigned int)&a10,
            (unsigned int)v94,
            (__int64)&v110,
            (__int64)&v107);
  if ( fixed < 0 )
    goto LABEL_102;
  v27 = a10;
  v99 = 4;
  LOBYTE(v96.Id) = v94[0];
  if ( v94[0] && ((a10 & 8) != 0 || (a10 & 0xE41FFF97) == 0 && (PsGetProcessProtection(v98, v25) & 7) == 1) )
  {
    v28 = v95;
    v29 = 1;
    v94[0] = 1;
LABEL_184:
    if ( LOBYTE(v96.Id) )
    {
      if ( ((fixed + 1073741793) & 0xFFFFFFFB) != 0 )
      {
        LOBYTE(v88) = v29;
        CipReportSharedSectionFailure(v98, v17, v27, (unsigned int)fixed, v88);
        if ( v94[0] )
        {
          fixed = -1073741701;
          goto LABEL_188;
        }
      }
    }
    if ( !v20 )
      goto LABEL_189;
    if ( (v27 & 0x20000015) != 0 || (PsGetProcessProtection(v98, v25) & 8) == 0 )
      goto LABEL_216;
    if ( fixed < 0 )
    {
      if ( fixed != -1073740760
        && fixed != -1073740285
        && fixed != -1058471934
        && (unsigned int)(fixed + 1058471929) > 6
        && fixed != -1073741554
        && fixed != -1073740283
        && fixed != -1058340861
        && fixed != -1073741701 )
      {
LABEL_213:
        v23 = (*((__int64 (**)(void))&xmmword_180049650 + 1))();
        if ( !v23 && (v27 & 0xE41FFF87) == 0 )
        {
          Keyword = (_BYTE *)v96.Keyword;
          fixed = 0;
          *(_BYTE *)v96.Keyword = 0;
          *v105 = 0;
          goto LABEL_102;
        }
LABEL_216:
        if ( fixed >= 0 )
        {
          if ( (v27 & 0xE41FFF87) != 0 )
          {
LABEL_222:
            if ( (v27 & 0x20000000) == 0 )
            {
              if ( fixed >= 0 )
                goto LABEL_233;
              if ( fixed == -1073740760
                || fixed == -1073740285
                || fixed == -1058471934
                || (unsigned int)(fixed + 1058471929) <= 6
                || fixed == -1073741554
                || fixed == -1073740283
                || fixed == -1058340861 )
              {
                LOBYTE(v88) = v23;
                fixed = CipReportAndReprieveDriverAndProtectedImageFailure(v20, v98, v17, v27, v88, fixed);
                if ( fixed >= 0 )
                {
                  *v105 = 0;
                  goto LABEL_233;
                }
              }
              goto LABEL_254;
            }
LABEL_240:
            if ( fixed < 0 )
            {
              if ( fixed != -1073740760
                && fixed != -1073740285
                && fixed != -1058471934
                && (unsigned int)(fixed + 1058471929) > 6
                && fixed != -1073741554
                && fixed != -1073740283
                && fixed != -1058340861
                && fixed != -1073741701 )
              {
LABEL_254:
                CiBlackboxValidateImageHeaderFailure(v20, v98, (_DWORD)v17, v27, v23, fixed);
                goto LABEL_233;
              }
            }
            else
            {
              v84 = *((_DWORD *)g_CipWhichLevelComparisons + (v23 & 0xF));
              if ( _bittest(&v84, *(_BYTE *)v96.Keyword & 0xF) )
              {
LABEL_233:
                if ( (*(_DWORD *)(v20 + 2360) & 2) != 0 )
                {
                  QuadPart = KeQueryPerformanceCounter(0).QuadPart;
                  if ( (unsigned __int8)v23 >= 2u || *(_DWORD *)(v20 + 2336) )
                    v99 = v23;
                  CipProcessSIPolicyLogs(
                    v20,
                    (__int64)&QuadPart,
                    v99,
                    *(_BYTE *)v96.Keyword,
                    (__int64)BaseAddress,
                    v100);
                  if ( (*(_DWORD *)(v20 + 2360) & 1) == 0 && *(__int64 (__fastcall ***)())(v20 + 3032) != &off_18002EE80 )
                    CiInstrumentVbsPolicyFailure(v20);
                }
                goto LABEL_188;
              }
            }
            v94[0] = 0;
            LOBYTE(v96.Id) = 1;
            fixed = CipReportAndReprieveUMCIFailure(
                      v20,
                      (struct _KPROCESS *)v98,
                      *(__int64 *)v112,
                      (__int64)v17,
                      v27,
                      v23,
                      *(_BYTE *)v96.Keyword,
                      fixed,
                      v94,
                      &v96);
            if ( fixed >= 0 )
            {
              if ( v94[0] )
              {
                *(_BYTE *)v96.Keyword = v96.Id;
                *v105 = 0;
              }
              goto LABEL_233;
            }
            goto LABEL_254;
          }
          if ( (*((_DWORD *)g_CipWhichLevelComparisons + (v23 & 0xF)) & 4) != 0 && (g_CiPolicyState & 0x4000) != 0 )
            CiQueryProcessNameAndInstrumentSmartAppControlDecision(v20, (_DWORD)v17, v98, v27, v23, fixed);
        }
        if ( (v27 & 0xE41FFF87) == 0 )
          goto LABEL_240;
        goto LABEL_222;
      }
    }
    else
    {
      v83 = *((_DWORD *)g_CipWhichLevelComparisons + (v23 & 0xF));
      if ( _bittest(&v83, *(_BYTE *)v96.Keyword & 0xF) )
        goto LABEL_213;
    }
    LOBYTE(v82) = v23;
    LOBYTE(v88) = *(_BYTE *)v96.Keyword;
    CipReportPPLAuditFailure(v20, v98, v17, v82, v88, fixed);
    goto LABEL_213;
  }
  v30 = v27 & 0xE41FFF87;
  if ( (v27 & 0xE41FFF87) != 0 )
    goto LABEL_17;
  if ( v23 )
  {
    if ( v23 != 2 && v23 != 9 )
      goto LABEL_17;
    v31 = (*((unsigned __int8 (**)(void))&xmmword_180049650 + 1))() == 0;
    goto LABEL_12;
  }
  if ( (*((unsigned __int8 (**)(void))&xmmword_180049650 + 1))() == 2 )
  {
    v23 = 2;
    a12 = 2;
    goto LABEL_17;
  }
  if ( !(*((unsigned __int8 (**)(void))&xmmword_180049650 + 1))() )
  {
    v31 = (v27 & 0x2000000) == 0;
LABEL_12:
    if ( v31 )
    {
      Keyword = (_BYTE *)v96.Keyword;
      v32 = v105;
      *(_BYTE *)v96.Keyword = 0;
      *v32 = 0;
LABEL_14:
      v28 = v95;
      fixed = 0;
      v17 = FileObject;
      goto LABEL_190;
    }
  }
LABEL_17:
  if ( (unsigned int)Feature_CodeIntegrity_TrustedLaunchPolicy__private_IsEnabledDeviceUsageNoInline() )
  {
    ActionsForImageWithToken = CiGetActionsForImageWithToken(v98, v112[0], (_DWORD)FileObject, v27, v23, (__int64)&v109);
    ActionsForImage = v109;
    fixed = ActionsForImageWithToken;
    if ( ActionsForImageWithToken < 0 )
    {
LABEL_22:
      v28 = v95;
LABEL_23:
      v17 = FileObject;
LABEL_189:
      Keyword = (_BYTE *)v96.Keyword;
      goto LABEL_190;
    }
    v34 = FileObject;
  }
  else
  {
    if ( (unsigned int)Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline() )
    {
      v94[0] = 0;
      fixed = CipIsTrustedLaunch(*(_QWORD *)v112, v27, v94);
      if ( fixed < 0 )
        goto LABEL_22;
      if ( v94[0] )
      {
        fixed = CipGetTrustedLaunchPackage(*(_QWORD *)v112, &DestinationString);
        if ( fixed < 0 )
          goto LABEL_22;
      }
    }
    IsEnabledDeviceUsageNoInline = Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline();
    v34 = FileObject;
    if ( IsEnabledDeviceUsageNoInline )
      LOBYTE(v36) = DestinationString.Buffer != 0;
    else
      v36 = 0;
    ActionsForImage = CiGetActionsForImage(v98, (_DWORD)FileObject, v27, v36, v23);
  }
  if ( (v22 & 3) != 0 && (v22 & 3) != 1 )
  {
    if ( (v22 & 3) == 2 )
    {
LABEL_37:
      ActionsForImage &= ~1u;
      goto LABEL_38;
    }
    if ( (v22 & 3) == 3 )
    {
      ActionsForImage &= 0xFFFFFFDB;
      goto LABEL_37;
    }
  }
LABEL_38:
  if ( !v30 && (unsigned __int8)CipIsFileInUMCIExclusionPaths(v34) )
  {
    Keyword = (_BYTE *)v96.Keyword;
    v37 = v105;
    *(_BYTE *)v96.Keyword = v23;
    *v37 = 0;
    goto LABEL_14;
  }
  v94[0] = 0;
  if ( (ActionsForImage & 1) != 0 )
  {
    v38 = v98;
    fixed = CipValidateFileInCache(
              v34,
              v98,
              *(__int64 *)v112,
              v23,
              a13,
              (__int64)&v111,
              (__int64)&v115,
              v96.Keyword,
              (__int64)&v114);
    v108 = v114;
    if ( fixed >= 0 )
    {
      if ( (ActionsForImage & 0x10) == 0
        || (v39 = *((_DWORD *)g_CipWhichLevelComparisons + 12), !_bittest(&v39, *(_BYTE *)v96.Keyword & 0xF)) )
      {
        if ( (v114 & 0x10) == 0 )
        {
          if ( !(unsigned int)PsIsProtectedProcess(v38)
            || (v108 & 0x40) != 0
            || (v27 & 0x10) != 0
            || (unsigned int)PsIsProtectedProcess(v38)
            && (v25 = *(_BYTE *)v96.Keyword & 0xF,
                v41 = *((_DWORD *)g_CipWhichLevelComparisons + 12),
                !_bittest(&v41, v25)) )
          {
            v17 = FileObject;
            *v105 = (v108 & 0x40) != 0 ? 7 : 2;
            if ( (g_CiDeveloperMode & 0x10000) != 0 )
            {
              LOBYTE(v40) = v23;
              LODWORD(Size) = v100;
              CiAuditImageForHvci(0, v27, v40, v38, v17, BaseAddress, Size, v110, v107);
            }
            v20 = v111;
            v28 = v95;
            goto LABEL_183;
          }
        }
      }
    }
    v20 = v111;
    v104 = v115;
    v22 = (4 * v115) | v22 & 3;
    *v118 = v22;
    if ( v20 && fixed == -1073741267 )
      ActionsForImage = ActionsForImage & 0xFFFFFEFF | *(_DWORD *)(v20 + 3048) & 0x100;
  }
  v42 = v120;
  if ( (ActionsForImage & 0x40) != 0 )
  {
    if ( v120 )
    {
      if ( !v30 && (*v120 & 0x10) != 0 && (g_CiPolicyState & 0x40) == 0 && (g_CiPolicyState & 0x80u) == 0 )
      {
        v17 = FileObject;
        v43 = ((__int64 (__fastcall *)(PFILE_OBJECT))xmmword_180049650)(FileObject);
        v25 = v43 & 0xF;
        v44 = *((_DWORD *)g_CipWhichLevelComparisons + (v23 & 0xF));
        if ( _bittest(&v44, v25) )
        {
          v45 = v105;
          v28 = v95;
          *(_BYTE *)v96.Keyword = v43;
          *v45 = 7;
LABEL_65:
          fixed = 0;
          v29 = 0;
          goto LABEL_184;
        }
      }
    }
  }
  v46 = CipMapEntireImage(v27, ActionsForImage);
  v47 = v117;
  if ( v46 > *v117 )
  {
    *v117 = v46;
    if ( (ActionsForImage & 0x100) != 0 )
    {
LABEL_70:
      fixed = -1073741789;
      goto LABEL_22;
    }
    goto LABEL_68;
  }
  if ( !v20 )
  {
    v49 = CipAllocateValidationContext(
            v27,
            ActionsForImage,
            FileObject,
            BaseAddress,
            v100,
            *(_QWORD *)v112,
            v42,
            v98,
            &v111);
    v20 = v111;
    fixed = v49;
    if ( v49 < 0 )
      goto LABEL_22;
  }
  v50 = v107;
  v51 = v110;
  *(_DWORD *)(v20 + 3048) = ActionsForImage;
  *(_DWORD *)(v20 + 3024) = v51;
  *(_DWORD *)(v20 + 3028) = v50;
  *(_DWORD *)(v20 + 3320) = v104;
  if ( (unsigned int)Feature_CodeIntegrity_TrustedLaunchPolicy__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( (ActionsForImage & 0x20000) != 0 )
    {
      fixed = CipGetTrustedLaunchPackage(*(_QWORD *)v112, v20 + 3592);
      if ( fixed < 0 )
        goto LABEL_22;
    }
    if ( (ActionsForImage & 0x40000) != 0 )
    {
      fixed = CiInitializeTrustedLaunchPolicyState();
      if ( fixed < 0 )
        goto LABEL_22;
    }
  }
  else if ( (unsigned int)Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline() && DestinationString.Buffer )
  {
    *(struct _UNICODE_STRING *)(v20 + 3592) = DestinationString;
    RtlInitUnicodeString(&DestinationString, 0);
  }
  v52 = BaseAddress;
  v53 = v100;
  if ( *v47 >= 1 )
  {
    if ( *v47 == 2 )
    {
      *(_QWORD *)(v20 + 3328) = BaseAddress;
      *(_DWORD *)(v20 + 3336) = v53;
    }
    else
    {
      *(_QWORD *)(v20 + 3328) = QuadPart;
      *(_DWORD *)(v20 + 3336) = a5;
    }
  }
  if ( (ActionsForImage & 0x100) != 0 )
  {
    v17 = FileObject;
    v54 = CipValidateImageHash(
            (unsigned int)&CipValidateFileHash,
            v20,
            (_DWORD)FileObject,
            v98,
            (__int64)v52,
            v53,
            v27,
            a12,
            a13,
            *(__int64 *)v113,
            (__int64)&v102);
    fixed = v54;
    if ( v54 >= 0 )
    {
LABEL_88:
      v55 = 1;
      goto LABEL_89;
    }
    v31 = *(_QWORD *)(v20 + 3032) == 0;
    v95 = v54;
    if ( v31 )
    {
      v28 = v54;
      *(_QWORD *)(v20 + 3032) = &off_18002EE80;
      goto LABEL_189;
    }
    ActionsForImage &= ~0x100u;
    *(_DWORD *)(v20 + 3048) = ActionsForImage;
    *(_BYTE *)(v20 + 2672) = 0;
  }
  v55 = 0;
  if ( (ActionsForImage & 4) == 0 )
  {
    v60 = v117;
    goto LABEL_113;
  }
  v58 = CipValidateImageHash(
          (unsigned int)&CipValidatePageHash,
          v20,
          (_DWORD)FileObject,
          v98,
          (__int64)BaseAddress,
          v100,
          v27,
          a12,
          a13,
          *(__int64 *)v113,
          (__int64)&v102);
  v59 = *(__int64 (__fastcall ***)())(v20 + 3032);
  fixed = v58;
  v95 = v58;
  if ( v59 )
  {
    if ( v58 >= 0 )
      goto LABEL_89;
    if ( ((ActionsForImage >> 3) & 1) != 0 && v59 == &off_18002EE80 )
    {
      v60 = v117;
    }
    else
    {
      v60 = v117;
      if ( *v117 == 1 )
      {
        *v117 = 2;
LABEL_68:
        v48 = v22 & 0xFC | 2;
LABEL_69:
        *v118 = v48;
        goto LABEL_70;
      }
      if ( ((ActionsForImage >> 3) & 1) == 0 )
        goto LABEL_89;
    }
    *(_DWORD *)(v20 + 3048) &= ~4u;
LABEL_113:
    if ( *v60 < 2 )
    {
      *v60 = 2;
      v48 = v22 | 3;
      goto LABEL_69;
    }
    v61 = CipValidateImageHash(
            (unsigned int)&CipValidateFileHash,
            v20,
            (_DWORD)FileObject,
            v98,
            (__int64)BaseAddress,
            v100,
            v27,
            a12,
            a13,
            *(__int64 *)v113,
            (__int64)&v102);
    fixed = v61;
    if ( v61 >= 0 )
      goto LABEL_88;
    if ( !*(_QWORD *)(v20 + 3032) )
    {
      v28 = v61;
      *(_QWORD *)(v20 + 3032) = &off_18002EE80;
      goto LABEL_23;
    }
LABEL_89:
    v95 = fixed;
    v103 = (ActionsForImage >> 6) & 1;
    if ( v103 )
    {
      if ( fixed >= 0 )
      {
        v56 = v102;
        v57 = *((_DWORD *)g_CipWhichLevelComparisons + 12);
        if ( !_bittest(&v57, *(_BYTE *)(v102 + 52) & 0xF) )
          goto LABEL_120;
        LOBYTE(v89) = 1;
        fixed = CipMitigatePPLBypassThroughInterpreters(
                  FileObject,
                  *(_QWORD *)(v20 + 3328),
                  *(unsigned int *)(v20 + 3336),
                  0,
                  v89);
        if ( fixed >= 0 )
        {
          if ( **(_QWORD **)v113 )
            _InterlockedOr(**(volatile signed __int32 ***)v113, 0x10u);
          goto LABEL_119;
        }
      }
    }
    else if ( fixed >= 0 )
    {
LABEL_119:
      v56 = v102;
LABEL_120:
      if ( (g_CiDeveloperMode & 0x10000) != 0 || (v27 & 5) != 0 && (g_CiDeveloperMode & 0x80u) != 0 )
      {
        v92 = v51;
        v62 = a12;
        LODWORD(Sizea) = v100;
        LOBYTE(v56) = a12;
        CiAuditImageForHvci(v20, v27, v56, v98, FileObject, BaseAddress, Sizea, v92, v107);
        v56 = v102;
      }
      else
      {
        v62 = a12;
      }
      *(_BYTE *)v96.Keyword = *(_BYTE *)(v56 + 52);
      if ( ((ActionsForImage >> 6) & 1) == 0
        || (v63 = *((_DWORD *)g_CipWhichLevelComparisons + 12), v64 = 7, !_bittest(&v63, *(_BYTE *)(v56 + 52) & 0xF)) )
      {
        v64 = *(_DWORD *)(v56 + 48);
      }
      *v105 = v64;
      *(_DWORD *)(v20 + 2360) = *(_DWORD *)(v20 + 2360) & 0xFFFFFFFE | ((*(_DWORD *)(v56 + 64) & 4) == 0);
      if ( (*(_BYTE *)(*(_QWORD *)(v20 + 2440) + 32LL) & 2) != 0 )
      {
        v65 = *(const void **)(v102 + 72);
        if ( v65 )
          memmove(*(void **)(v20 + 2344), v65, 4LL * (unsigned int)g_NumberOfSiPolicies);
      }
      if ( (v27 & 5) != 0 )
      {
        CiAuditDriverAllow(FileObject, v27, v102, v20);
        if ( (unsigned int)Feature_Servicing_WhqlOnlyContainment__private_IsEnabledDeviceUsageNoInline() )
          CipProcessPicrootExceptionsPolicyFailures(v20, 0, v20 + 744);
      }
      if ( v55 )
      {
        QuadPart = v62 & 0xF;
        v66 = *((_DWORD *)g_CipWhichLevelComparisons + QuadPart);
        if ( _bittest(&v66, *(_BYTE *)v96.Keyword & 0xF) )
        {
          if ( (*(_DWORD *)(v20 + 3048) & 2) != 0 && (*(_DWORD *)(v102 + 64) & 4) == 0 && (v108 & 0x10) == 0 )
          {
            v67 = v104;
            if ( ((ActionsForImage >> 8) & 1) != 0
              && (v104 == 12 && (*(_DWORD *)(v20 + 2360) & 0x400) == 0
               || v104 == 33 && (unsigned __int8)CiDoesFilenameHavePerAppPolicyRules((PCUNICODE_STRING)(v20 + 744))
               || v67 == 34) )
            {
              Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline();
            }
            else if ( !(unsigned int)Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline()
                   || ((ActionsForImage >> 8) & 1) == 0
                   || v67 != 39 )
            {
              v68 = 0;
              CipImageValidityPeriod(v20 + 24, &v126);
              v71 = *(_DWORD *)(v20 + 2360);
              if ( (v71 & 0x400) != 0 )
              {
                v72 = v20 + 2108;
              }
              else
              {
                v72 = 0;
                if ( (v71 & 0x1000) != 0 )
                  v72 = v20 + 2186;
              }
              LOBYTE(v70) = v104 == 25;
              LOBYTE(v69) = *(_BYTE *)v96.Keyword;
              CipGetValidatedSigningLevels(v69, v20, v27, v70, FileObject, (__int64)&v101);
              v73 = *(_DWORD *)(v20 + 2096);
              if ( v73 < 0 )
                v68 = v20 + 3340;
              v74 = *(_QWORD *)(v102 + 16);
              if ( v74 && *(_DWORD *)(v74 + 48) )
              {
                CipSetFileCache(
                  FileObject,
                  *(_DWORD *)(*(_QWORD *)(v74 + 40) + 4LL),
                  **(_DWORD **)(v74 + 40),
                  v102 + 88,
                  *(_DWORD *)(v102 + 84),
                  *(_DWORD *)(v102 + 80),
                  v93,
                  v98,
                  v72,
                  v101,
                  v73,
                  v68);
              }
              else if ( (*((_DWORD *)g_CipWhichLevelComparisons + QuadPart) & 4) != 0 )
              {
                CipSetFileCache(FileObject, 0, 0, 0, 0, 0, v93, v98, v72, v101, v73, v68);
              }
            }
          }
        }
      }
      v75 = v102;
      goto LABEL_164;
    }
    v76 = *(unsigned int *)(v20 + 32);
    if ( (_DWORD)v76 )
      v76 = ((_BYTE)v76 - 1) & 3;
    v75 = v20 + 160 * v76 + 40;
LABEL_164:
    v17 = FileObject;
    v77 = v98;
    v78 = CipCallPeauth((unsigned int)fixed, v20 + 4, v98, v27, v75, FileObject);
    fixed = v78;
    if ( (v27 & 0x2800000) != 0 )
    {
LABEL_188:
      v28 = v95;
      goto LABEL_189;
    }
    if ( v78 < 0 && v78 != -1073740285 && v78 != -1073740283 )
    {
      if ( (g_CiOptions & 4) != 0 && (v27 & 0x80000000) != 0 )
      {
        v28 = v95;
LABEL_182:
        v23 = a12;
        goto LABEL_183;
      }
      if ( ((g_CiOptions & 2) == 0 || (v27 & 1) == 0)
        && (v27 & 0x40000006) == 0
        && ((g_CiOptions & 2) != 0 || (v27 & 1) == 0 || (g_CiPolicyState & 1) == 0 || (*(_DWORD *)(v20 + 2360) & 1) != 0) )
      {
        v23 = a12;
        if ( (v27 & 0x80000001) != 0 )
        {
          LOBYTE(v79) = a12;
          CipReportSystemOptionsReprieve(v17, v77, v27, v79, v78);
          v28 = v95;
          *v105 = 0;
          goto LABEL_65;
        }
        v28 = v95;
LABEL_183:
        v29 = v94[0];
        goto LABEL_184;
      }
    }
    v28 = v95;
    goto LABEL_182;
  }
  v17 = FileObject;
  Keyword = (_BYTE *)v96.Keyword;
  *(_QWORD *)(v20 + 3032) = &off_18002EE80;
  if ( v58 >= 0 )
  {
    fixed = -1073741801;
LABEL_102:
    v28 = v95;
    goto LABEL_190;
  }
  v28 = v58;
LABEL_190:
  if ( v123 )
  {
    if ( fixed < 0 )
    {
      if ( fixed != -1073741789 && v20 )
        CipBuildSigningInformation(
          v17,
          *(_QWORD *)(v20 + 3016),
          *(unsigned int *)(v20 + 3012),
          *(unsigned int *)(v20 + 3008),
          0,
          v123,
          v119);
      goto LABEL_195;
    }
    v80 = (_DWORD *)v119;
    if ( !v102 )
    {
      *v123 = 0;
      *v80 = 0;
      goto LABEL_257;
    }
    fixed = CipBuildSigningInformation(
              v17,
              v102 + 88,
              *(unsigned int *)(v102 + 84),
              *(unsigned int *)(v102 + 80),
              v102,
              v123,
              v119);
  }
  if ( fixed < 0 )
  {
LABEL_195:
    v81 = *(_QWORD **)v113;
    if ( **(_QWORD **)v113 && !v120 )
    {
      CiReleaseContext();
      *v81 = 0;
    }
    goto LABEL_263;
  }
LABEL_257:
  v85 = *(_QWORD **)v113;
  if ( *Keyword && !**(_QWORD **)v113 )
    **(_QWORD **)v113 = g_CiPolicyGenerationCounter & 0x3FFFFFFFFFFFFFFLL
                      | ((unsigned __int64)(ActionsForImage & 0x18000) << 43);
  if ( v28 >= 0 )
  {
    v86 = *(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)(v20 + 3032) + 8LL);
    if ( v86 )
      fixed = v86(*v85);
  }
LABEL_263:
  if ( v20 )
    CiFreeValidationContext((PVOID)v20);
  if ( (unsigned int)Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline() && DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x63734943u);
  CiLogStatusEventWithCorrelationId((unsigned int)fixed, CiValidateImageHeaderComplete, 0);
  ExReleasePushLockSharedEx(&g_CipPolicyLock, 0);
  KeLeaveCriticalRegion();
  IoClearActivityIdThread(v124);
  return (unsigned int)fixed;
}

```

## disassembly

```asm
0x1800e55e0  mov     [rsp-8+arg_18], rbx
0x1800e55e5  push    rbp
0x1800e55e6  push    rsi
0x1800e55e7  push    rdi
0x1800e55e8  push    r12
0x1800e55ea  push    r13
0x1800e55ec  push    r14
0x1800e55ee  push    r15
0x1800e55f0  lea     rbp, [rsp-80h]
0x1800e55f5  sub     rsp, 180h
0x1800e55fc  mov     rax, cs:__security_cookie
0x1800e5603  xor     rax, rsp
0x1800e5606  mov     [rbp+0B0h+var_38], rax
0x1800e560a  mov     rax, [rbp+0B0h+arg_70]
0x1800e5611  mov     r15, rcx
0x1800e5614  mov     rdi, [rbp+0B0h+Process]
0x1800e561b  xorps   xmm0, xmm0
0x1800e561e  mov     r12, [rbp+0B0h+arg_68]
0x1800e5625  mov     [rbp+0B0h+var_E8], rax
0x1800e5629  mov     rax, [rbp+0B0h+arg_40]
0x1800e5630  mov     [rbp+0B0h+var_E0], rdx
0x1800e5634  mov     rdx, [rbp+0B0h+arg_78]
0x1800e563b  mov     qword ptr [rbp+0B0h+var_C0], rax
0x1800e563f  mov     rax, [rbp+0B0h+arg_50]
0x1800e5646  mov     [rbp+0B0h+FileObject], rcx
0x1800e564a  mov     rcx, [rbp+0B0h+arg_28]
0x1800e5651  mov     [rbp+0B0h+var_68], rdx
0x1800e5655  mov     rdx, [rbp+0B0h+arg_80]
0x1800e565c  mov     qword ptr [rbp+0B0h+var_B8], rax
0x1800e5660  mov     rax, [rax]
0x1800e5663  mov     [rbp+0B0h+var_A0], rcx
0x1800e5667  mov     rcx, [rbp+0B0h+arg_30]
0x1800e566e  mov     [rbp+0B0h+var_90], rdx
0x1800e5672  xor     edx, edx
0x1800e5674  mov     esi, edx
0x1800e5676  mov     [rbp+0B0h+var_88], rax
0x1800e567a  mov     [rbp+0B0h+var_98], rcx
0x1800e567e  mov     ebx, edx
0x1800e5680  movzx   r14d, byte ptr [rcx]
0x1800e5684  mov     eax, r14d
0x1800e5687  mov     [rbp+0B0h+var_C8], rdx
0x1800e568b  shr     eax, 2
0x1800e568e  lea     ecx, [rsi+3]; ControlCode
0x1800e5691  mov     [rbp+0B0h+var_D0], edx
0x1800e5694  mov     [rbp+0B0h+var_F0], edx
0x1800e5697  mov     byte ptr [rbp+0B0h+var_130], dl
0x1800e569a  mov     [rbp+0B0h+var_F8], rdx
0x1800e569e  mov     [rbp+0B0h+var_D4], edx
0x1800e56a1  mov     [rbp+0B0h+var_B0], edx
0x1800e56a4  mov     [rbp+0B0h+var_CC], edx
0x1800e56a7  mov     [rbp+0B0h+var_D8], edx
0x1800e56aa  mov     word ptr [rbp+0B0h+var_104+4], dx
0x1800e56ae  lea     rdx, [rbp+0B0h+ActivityId]; ActivityId
0x1800e56b2  mov     [rbp+0B0h+var_EC], eax
0x1800e56b5  mov     [rbp+0B0h+var_AC], eax
0x1800e56b8  mov     [rbp+0B0h+var_A8], r9
0x1800e56bc  mov     dword ptr [rbp+0B0h+var_104], r8d
0x1800e56c0  mov     [rbp+0B0h+var_110], rdi
0x1800e56c4  mov     [rbp+0B0h+var_128.Keyword], r12
0x1800e56c8  movups  [rbp+0B0h+var_48], xmm0
0x1800e56cc  mov     dword ptr [rbp+0B0h+var_130+4], 0C0000428h
0x1800e56d3  movups  xmmword ptr [rbp+0B0h+ActivityId.Data1], xmm0
0x1800e56d7  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x1800e56db  call    cs:__imp_EtwActivityIdControl
0x1800e56e2  nop     dword ptr [rax+rax+00h]
0x1800e56e7  lea     rcx, [rbp+0B0h+ActivityId]
0x1800e56eb  call    cs:__imp_IoSetActivityIdThread
0x1800e56f2  nop     dword ptr [rax+rax+00h]
0x1800e56f7  xor     ecx, ecx; PerformanceFrequency
0x1800e56f9  mov     [rbp+0B0h+var_60], rax
0x1800e56fd  call    cs:__imp_KeQueryPerformanceCounter
0x1800e5704  nop     dword ptr [rax+rax+00h]
0x1800e5709  mov     [rbp+0B0h+var_70], rax
0x1800e570d  mov     byte ptr [r12], 1
0x1800e5712  call    CiInitializePhase2
0x1800e5717  call    cs:__imp_KeEnterCriticalRegion
0x1800e571e  nop     dword ptr [rax+rax+00h]
0x1800e5723  xor     edx, edx
0x1800e5725  lea     rcx, g_CipPolicyLock
0x1800e572c  call    cs:__imp_ExAcquirePushLockSharedEx
0x1800e5733  nop     dword ptr [rax+rax+00h]
0x1800e5738  mov     r13b, [rbp+0B0h+arg_58]
0x1800e573f  lea     rax, CiValidateImageHeaderStart
0x1800e5746  mov     r8d, [rbp+0B0h+arg_48]; int
0x1800e574d  lea     rcx, [r15+58h]; int
0x1800e5751  mov     r9b, r13b; int
0x1800e5754  mov     [rsp+1B0h+var_190], rax; PCEVENT_DESCRIPTOR
0x1800e5759  mov     rdx, rdi; Process
0x1800e575c  call    CiLogFileRequestedValidationEvent
0x1800e5761  mov     rcx, [rbp+0B0h+var_E0]
0x1800e5765  lea     rax, [rbp+0B0h+var_D8]
0x1800e5769  mov     [rsp+1B0h+BaseAddress], rax
0x1800e576e  lea     r9, [rbp+0B0h+var_130]
0x1800e5772  lea     rax, [rbp+0B0h+var_CC]
0x1800e5776  lea     r8, [rbp+0B0h+arg_48]
0x1800e577d  mov     [rsp+1B0h+var_190], rax
0x1800e5782  lea     rdx, [rbp+0B0h+var_F0]
0x1800e5786  call    CipFixImageType
0x1800e578b  mov     edi, eax
0x1800e578d  test    eax, eax
0x1800e578f  js      loc_1800E5E46
0x1800e5795  mov     al, byte ptr [rbp+0B0h+var_130]
0x1800e5798  mov     r12d, [rbp+0B0h+arg_48]
0x1800e579f  mov     [rbp+0B0h+var_108], 4
0x1800e57a3  mov     byte ptr [rbp+0B0h+var_128.Id], al
0x1800e57a6  test    al, al
0x1800e57a8  jz      short loc_1800E57DD
0x1800e57aa  test    r12b, 8
0x1800e57ae  jnz     short loc_1800E57CF
0x1800e57b0  test    r12d, 0E41FFF97h
0x1800e57b7  jnz     short loc_1800E57DD
0x1800e57b9  mov     rcx, [rbp+0B0h+var_110]
0x1800e57bd  call    cs:__imp_PsGetProcessProtection
0x1800e57c4  nop     dword ptr [rax+rax+00h]
0x1800e57c9  and     al, 7
0x1800e57cb  cmp     al, 1
0x1800e57cd  jnz     short loc_1800E57DD
0x1800e57cf  mov     r14d, dword ptr [rbp+0B0h+var_130+4]
0x1800e57d3  mov     cl, 1
0x1800e57d5  mov     byte ptr [rbp+0B0h+var_130], cl
0x1800e57d8  jmp     loc_1800E638E
0x1800e57dd  mov     r15d, r12d
0x1800e57e0  and     r15d, 0E41FFF87h
0x1800e57e7  jnz     short loc_1800E5840
0x1800e57e9  test    r13b, r13b
0x1800e57ec  jz      short loc_1800E5827
0x1800e57ee  cmp     r13b, 2
0x1800e57f2  jz      short loc_1800E57FA
0x1800e57f4  cmp     r13b, 9
0x1800e57f8  jnz     short loc_1800E5840
0x1800e57fa  mov     rax, qword ptr cs:xmmword_180049650+8
0x1800e5801  call    _guard_dispatch_icall
0x1800e5806  test    al, al
0x1800e5808  jnz     short loc_1800E5840
0x1800e580a  mov     r12, [rbp+0B0h+var_128.Keyword]
0x1800e580e  mov     rcx, [rbp+0B0h+var_E8]
0x1800e5812  mov     [r12], bl
0x1800e5816  mov     [rcx], ebx
0x1800e5818  mov     r14d, dword ptr [rbp+0B0h+var_130+4]
0x1800e581c  xor     edi, edi
0x1800e581e  mov     r15, [rbp+0B0h+FileObject]
0x1800e5822  jmp     loc_1800E63D6
0x1800e5827  mov     rax, qword ptr cs:xmmword_180049650+8
0x1800e582e  call    _guard_dispatch_icall
0x1800e5833  cmp     al, 2
0x1800e5835  jnz     short loc_1800E587D
0x1800e5837  mov     r13b, al
0x1800e583a  mov     [rbp+0B0h+arg_58], al
0x1800e5840  call    Feature_CodeIntegrity_TrustedLaunchPolicy__private_IsEnabledDeviceUsageNoInline
0x1800e5845  test    eax, eax
0x1800e5847  jz      short loc_1800E58A6
0x1800e5849  mov     r8, [rbp+0B0h+FileObject]
0x1800e584d  lea     rax, [rbp+0B0h+var_D0]
0x1800e5851  mov     rdx, qword ptr [rbp+0B0h+var_C0]
0x1800e5855  mov     r9d, r12d
0x1800e5858  mov     rcx, [rbp+0B0h+var_110]
0x1800e585c  mov     [rsp+1B0h+BaseAddress], rax
0x1800e5861  mov     byte ptr [rsp+1B0h+var_190], r13b
0x1800e5866  call    CiGetActionsForImageWithToken
0x1800e586b  mov     ebx, [rbp+0B0h+var_D0]
0x1800e586e  mov     edi, eax
0x1800e5870  test    eax, eax
0x1800e5872  js      short loc_1800E5899
0x1800e5874  mov     rdi, [rbp+0B0h+FileObject]
0x1800e5878  jmp     loc_1800E5910
0x1800e587d  mov     rax, qword ptr cs:xmmword_180049650+8
0x1800e5884  call    _guard_dispatch_icall
0x1800e5889  test    al, al
0x1800e588b  jnz     short loc_1800E5840
0x1800e588d  test    r12d, 2000000h
0x1800e5894  jmp     loc_1800E5808
0x1800e5899  mov     r14d, dword ptr [rbp+0B0h+var_130+4]
0x1800e589d  mov     r15, [rbp+0B0h+FileObject]
0x1800e58a1  jmp     loc_1800E63D2
0x1800e58a6  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x1800e58ab  test    eax, eax
0x1800e58ad  jz      short loc_1800E58E0
0x1800e58af  mov     rcx, qword ptr [rbp+0B0h+var_C0]
0x1800e58b3  lea     r8, [rbp+0B0h+var_130]
0x1800e58b7  mov     edx, r12d
0x1800e58ba  mov     byte ptr [rbp+0B0h+var_130], bl
0x1800e58bd  call    CipIsTrustedLaunch
0x1800e58c2  mov     edi, eax
0x1800e58c4  test    eax, eax
0x1800e58c6  js      short loc_1800E5899
0x1800e58c8  cmp     byte ptr [rbp+0B0h+var_130], bl
0x1800e58cb  jz      short loc_1800E58E0
0x1800e58cd  mov     rcx, qword ptr [rbp+0B0h+var_C0]
0x1800e58d1  lea     rdx, [rbp+0B0h+DestinationString]
0x1800e58d5  call    CipGetTrustedLaunchPackage
0x1800e58da  mov     edi, eax
0x1800e58dc  test    eax, eax
0x1800e58de  js      short loc_1800E5899
0x1800e58e0  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x1800e58e5  mov     rdi, [rbp+0B0h+FileObject]
0x1800e58e9  mov     r8d, r12d
0x1800e58ec  mov     rcx, [rbp+0B0h+var_110]
0x1800e58f0  mov     rdx, rdi
0x1800e58f3  mov     byte ptr [rsp+1B0h+var_190], r13b
0x1800e58f8  test    eax, eax
0x1800e58fa  jz      short loc_1800E5906
0x1800e58fc  cmp     [rbp+0B0h+DestinationString.Buffer], rbx
0x1800e5900  setnz   r9b
0x1800e5904  jmp     short loc_1800E5909
0x1800e5906  xor     r9d, r9d
0x1800e5909  call    CiGetActionsForImage
0x1800e590e  mov     ebx, eax
0x1800e5910  mov     ecx, r14d
0x1800e5913  and     ecx, 3
0x1800e5916  jz      short loc_1800E592D
0x1800e5918  sub     ecx, 1
0x1800e591b  jz      short loc_1800E592D
0x1800e591d  sub     ecx, 1
0x1800e5920  jz      short loc_1800E592A
0x1800e5922  cmp     ecx, 1
0x1800e5925  jnz     short loc_1800E592D
0x1800e5927  and     ebx, 0FFFFFFDBh
0x1800e592a  and     ebx, 0FFFFFFFEh
0x1800e592d  test    r15d, r15d
0x1800e5930  jnz     short loc_1800E5951
0x1800e5932  mov     rcx, rdi
0x1800e5935  call    CipIsFileInUMCIExclusionPaths
0x1800e593a  test    al, al
0x1800e593c  jz      short loc_1800E5951
0x1800e593e  mov     r12, [rbp+0B0h+var_128.Keyword]
0x1800e5942  mov     rcx, [rbp+0B0h+var_E8]
0x1800e5946  mov     [r12], r13b
0x1800e594a  mov     [rcx], esi
0x1800e594c  jmp     loc_1800E5818
0x1800e5951  xor     al, al
0x1800e5953  mov     byte ptr [rbp+0B0h+var_130], al
0x1800e5956  test    bl, 1
0x1800e5959  jz      loc_1800E5AD5
0x1800e595f  mov     rsi, [rbp+0B0h+var_110]
0x1800e5963  lea     rax, [rbp+0B0h+var_B0]
0x1800e5967  mov     r8, qword ptr [rbp+0B0h+var_C0]
0x1800e596b  mov     r9d, r12d
0x1800e596e  mov     [rsp+1B0h+var_168], rax
0x1800e5973  mov     rdx, rsi
0x1800e5976  mov     rax, [rbp+0B0h+var_128.Keyword]
0x1800e597a  mov     rcx, rdi
0x1800e597d  mov     [rsp+1B0h+var_170], rax
0x1800e5982  lea     rax, [rbp+0B0h+var_AC]
0x1800e5986  mov     qword ptr [rsp+1B0h+var_178], rax
0x1800e598b  lea     rax, [rbp+0B0h+var_C8]
0x1800e598f  mov     [rsp+1B0h+Size], rax
0x1800e5994  mov     al, [rbp+0B0h+arg_60]
0x1800e599a  mov     byte ptr [rsp+1B0h+BaseAddress], al
0x1800e599e  mov     byte ptr [rsp+1B0h+var_190], r13b
0x1800e59a3  call    CipValidateFileInCache
0x1800e59a8  mov     r8d, [rbp+0B0h+var_B0]
0x1800e59ac  mov     edi, eax
0x1800e59ae  mov     [rbp+0B0h+var_D4], r8d
0x1800e59b2  test    eax, eax
0x1800e59b4  js      loc_1800E5A97
0x1800e59ba  test    bl, 10h
0x1800e59bd  jz      short loc_1800E59DC
0x1800e59bf  mov     rax, [rbp+0B0h+var_128.Keyword]
0x1800e59c3  movzx   edx, byte ptr [rax]
0x1800e59c6  mov     rax, cs:g_CipWhichLevelComparisons
0x1800e59cd  and     edx, 0Fh
0x1800e59d0  mov     ecx, [rax+30h]
0x1800e59d3  bt      ecx, edx
0x1800e59d6  jb      loc_1800E5A97
0x1800e59dc  test    r8b, 10h
0x1800e59e0  jnz     loc_1800E5A97
0x1800e59e6  mov     rcx, rsi
0x1800e59e9  call    cs:__imp_PsIsProtectedProcess
0x1800e59f0  nop     dword ptr [rax+rax+00h]
0x1800e59f5  test    eax, eax
0x1800e59f7  jz      short loc_1800E5A31
0x1800e59f9  test    byte ptr [rbp+0B0h+var_D4], 40h
0x1800e59fd  jnz     short loc_1800E5A31
0x1800e59ff  test    r12b, 10h
0x1800e5a03  jnz     short loc_1800E5A31
0x1800e5a05  mov     rcx, rsi
0x1800e5a08  call    cs:__imp_PsIsProtectedProcess
0x1800e5a0f  nop     dword ptr [rax+rax+00h]
0x1800e5a14  test    eax, eax
0x1800e5a16  jz      short loc_1800E5A97
0x1800e5a18  mov     rax, [rbp+0B0h+var_128.Keyword]
0x1800e5a1c  movzx   edx, byte ptr [rax]
0x1800e5a1f  mov     rax, cs:g_CipWhichLevelComparisons
0x1800e5a26  and     edx, 0Fh
0x1800e5a29  mov     ecx, [rax+30h]
0x1800e5a2c  bt      ecx, edx
0x1800e5a2f  jb      short loc_1800E5A97
0x1800e5a31  mov     r14d, [rbp+0B0h+var_D4]
0x1800e5a35  mov     rcx, [rbp+0B0h+var_E8]
0x1800e5a39  and     r14b, 40h
0x1800e5a3d  mov     r15, [rbp+0B0h+FileObject]
0x1800e5a41  neg     r14b
0x1800e5a44  sbb     eax, eax
0x1800e5a46  and     eax, 5
0x1800e5a49  add     eax, 2
0x1800e5a4c  mov     [rcx], eax
0x1800e5a4e  test    byte ptr cs:g_CiDeveloperMode+2, 1
0x1800e5a55  jz      short loc_1800E5A8A
0x1800e5a57  mov     eax, [rbp+0B0h+var_D8]
0x1800e5a5a  mov     r9, rsi; int
  ... truncated ...
```
