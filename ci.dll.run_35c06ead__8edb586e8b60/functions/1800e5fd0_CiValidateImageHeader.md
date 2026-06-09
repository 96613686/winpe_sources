# CiValidateImageHeader

- ea: `0x1800e5fd0`
- end: `0x1800e72dd`
- name: `CiValidateImageHeader`
- size: `4877`
- prototype: `__int64 __fastcall(struct _FILE_OBJECT *, void *, int, __int64, int, int *, unsigned __int8 *, PEPROCESS Process, __int64, int, __int64 *, char, char, ULONGLONG, int *, _QWORD *, __int64)`
- caller_count: `0`
- callee_count: `40`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800100a4`
- `0x18001d1e0`
- `0x18002c0d0`
- `0x18002c1b0`
- `0x18002c200`
- `0x18005986c`
- `0x18005a40c`
- `0x18005e3a8`
- `0x18005fffc`
- `0x180060894`
- `0x1800647dc`
- `0x180064af0`
- `0x180064be8`
- `0x180064cbc`
- `0x180064e4c`
- `0x18006c4c0`
- `0x180075ae8`
- `0x180076438`
- `0x18008c95c`
- `0x18008ccb0`
- `0x18008f0d0`
- `0x18008f2f4`
- `0x18008f7cc`
- `0x18009257c`
- `0x18009b8e0`
- `0x18009df48`
- `0x18009ed54`
- `0x18009f338`
- `0x18009fff8`
- `0x1800a0540`
- `0x1800a4538`
- `0x1800a4c50`
- `0x1800a647c`
- `0x1800a89b0`
- `0x1800ab748`
- `0x1800b4f38`
- `0x1800dca3c`
- `0x1800e29ac`
- `0x1800e5228`
- `0x1800e5fd0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800e6107`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800e6107`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800e6644`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800e6644`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1800e723d`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1800e723d`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1800e611c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1800e611c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e7217`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e7217`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800e7249`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800e7249`
- `ntoskrnl!PsGetProcessProtection` at `0x1800e61ad`
- `ntoskrnl!PsGetProcessProtection` at `0x1800e6e47`
- `ntoskrnl!PsGetProcessProtection` at `0x1800e61ad`
- `ntoskrnl!PsGetProcessProtection` at `0x1800e6e47`
- `ntoskrnl!PsIsProtectedProcess` at `0x1800e63d9`
- `ntoskrnl!PsIsProtectedProcess` at `0x1800e63f8`
- `ntoskrnl!PsIsProtectedProcess` at `0x1800e63d9`
- `ntoskrnl!PsIsProtectedProcess` at `0x1800e63f8`
- `ntoskrnl!IoClearActivityIdThread` at `0x1800e7259`
- `ntoskrnl!IoClearActivityIdThread` at `0x1800e7259`
- `ntoskrnl!EtwActivityIdControl` at `0x1800e60cb`
- `ntoskrnl!EtwActivityIdControl` at `0x1800e60cb`
- `ntoskrnl!IoSetActivityIdThread` at `0x1800e60db`
- `ntoskrnl!IoSetActivityIdThread` at `0x1800e60db`
- `HAL!KeQueryPerformanceCounter` at `0x1800e60ed`
- `HAL!KeQueryPerformanceCounter` at `0x1800e6ffe`
- `HAL!KeQueryPerformanceCounter` at `0x1800e60ed`
- `HAL!KeQueryPerformanceCounter` at `0x1800e6ffe`

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
        __int64 *a11,
        char a12,
        char a13,
        ULONGLONG a14,
        int *a15,
        _QWORD *a16,
        __int64 a17)
{
  struct _FILE_OBJECT *v17; // r15
  _BYTE *Keyword; // r12
  __int64 v19; // rax
  __int64 v20; // rsi
  unsigned int ActionsForImage; // ebx
  char v22; // r14
  char v23; // r13
  int v24; // r9d
  int fixed; // edi
  unsigned int v26; // r12d
  int v27; // r14d
  char v28; // cl
  unsigned int v29; // r15d
  bool v30; // zf
  int *v31; // rcx
  int ActionsForImageWithToken; // eax
  struct _FILE_OBJECT *v33; // rdi
  int IsEnabledDeviceUsageNoInline; // eax
  char v35; // r9
  int *v36; // rcx
  __int64 v37; // rsi
  int v38; // ecx
  int v39; // r8d
  int v40; // ecx
  __int64 v41; // rdi
  char v42; // r8
  int v43; // ecx
  int *v44; // rcx
  int v45; // eax
  int *v46; // r15
  char v47; // r14
  int ValidationContext; // eax
  int v49; // eax
  int v50; // r13d
  PVOID v51; // rcx
  int v52; // edx
  int v53; // eax
  char v54; // r15
  __int64 v55; // r8
  int v56; // ecx
  int v57; // eax
  __int64 (__fastcall **v58)(); // rcx
  int *v59; // rcx
  int v60; // eax
  char v61; // r13
  int v62; // ecx
  int v63; // eax
  const void *v64; // rdx
  int v65; // ecx
  unsigned int v66; // r14d
  __int64 v67; // r13
  int v68; // ecx
  int v69; // r9d
  int v70; // eax
  __int64 v71; // r15
  int v72; // r10d
  __int64 v73; // r8
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // r14
  int v77; // eax
  __int64 v78; // r9
  _DWORD *v79; // r9
  _QWORD *v80; // rbx
  __int64 v81; // r9
  int v82; // ecx
  int v83; // ecx
  _QWORD *v84; // rcx
  __int64 (__fastcall *v85)(_QWORD); // rax
  PCEVENT_DESCRIPTOR v87; // [rsp+20h] [rbp-E0h]
  int v88; // [rsp+20h] [rbp-E0h]
  ULONGLONG v89; // [rsp+30h] [rbp-D0h]
  int v90; // [rsp+38h] [rbp-C8h]
  int v91; // [rsp+48h] [rbp-B8h]
  _BYTE v92[4]; // [rsp+80h] [rbp-80h] BYREF
  int v93; // [rsp+84h] [rbp-7Ch]
  EVENT_DESCRIPTOR v94; // [rsp+88h] [rbp-78h] BYREF
  PFILE_OBJECT FileObject; // [rsp+98h] [rbp-68h]
  __int64 v96; // [rsp+A0h] [rbp-60h]
  char v97; // [rsp+A8h] [rbp-58h]
  int Size; // [rsp+ACh] [rbp-54h]
  __int16 Size_4; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v100; // [rsp+B8h] [rbp-48h] BYREF
  int v101; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v102; // [rsp+C4h] [rbp-3Ch]
  int *v103; // [rsp+C8h] [rbp-38h]
  PVOID BaseAddress; // [rsp+D0h] [rbp-30h]
  int v105; // [rsp+D8h] [rbp-28h] BYREF
  int v106; // [rsp+DCh] [rbp-24h]
  int v107; // [rsp+E0h] [rbp-20h] BYREF
  int v108; // [rsp+E4h] [rbp-1Ch] BYREF
  __int64 v109; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v110; // [rsp+F0h] [rbp-10h]
  int v111[2]; // [rsp+F8h] [rbp-8h]
  int v112; // [rsp+100h] [rbp+0h] BYREF
  unsigned int v113; // [rsp+104h] [rbp+4h] BYREF
  __int64 QuadPart; // [rsp+108h] [rbp+8h] BYREF
  int *v115; // [rsp+110h] [rbp+10h]
  _BYTE *v116; // [rsp+118h] [rbp+18h]
  __int64 v117; // [rsp+120h] [rbp+20h]
  __int64 v118; // [rsp+128h] [rbp+28h]
  struct _UNICODE_STRING DestinationString; // [rsp+130h] [rbp+30h] BYREF
  LARGE_INTEGER PerformanceCounter; // [rsp+140h] [rbp+40h]
  _QWORD *v121; // [rsp+148h] [rbp+48h]
  __int64 v122; // [rsp+150h] [rbp+50h]
  GUID ActivityId; // [rsp+158h] [rbp+58h] BYREF
  __int128 v124; // [rsp+168h] [rbp+68h] BYREF

  v17 = a1;
  Keyword = (_BYTE *)a14;
  v103 = a15;
  BaseAddress = a2;
  v110 = a9;
  FileObject = a1;
  v121 = a16;
  *(_QWORD *)v111 = a11;
  v19 = *a11;
  v115 = a6;
  v117 = a17;
  v20 = 0;
  v118 = v19;
  v116 = a7;
  ActionsForImage = 0;
  v22 = *a7;
  LODWORD(v19) = *a7;
  v109 = 0;
  v107 = 0;
  v101 = 0;
  v92[0] = 0;
  v100 = 0;
  v106 = 0;
  v112 = 0;
  v108 = 0;
  v105 = 0;
  Size_4 = 0;
  v102 = (unsigned int)v19 >> 2;
  v113 = (unsigned int)v19 >> 2;
  QuadPart = a4;
  Size = a3;
  v96 = (__int64)Process;
  v94.Keyword = a14;
  v124 = 0;
  v93 = -1073740760;
  ActivityId = 0;
  DestinationString = 0;
  EtwActivityIdControl(3u, &ActivityId);
  v122 = IoSetActivityIdThread(&ActivityId);
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
            (unsigned int)&v101,
            (unsigned int)&a10,
            (unsigned int)v92,
            (__int64)&v108,
            (__int64)&v105);
  if ( fixed < 0 )
    goto LABEL_102;
  v26 = a10;
  v97 = 4;
  LOBYTE(v94.Id) = v92[0];
  if ( v92[0] && ((a10 & 8) != 0 || (a10 & 0xE41FFF97) == 0 && (PsGetProcessProtection(v96) & 7) == 1) )
  {
    v27 = v93;
    v28 = 1;
    v92[0] = 1;
LABEL_183:
    if ( LOBYTE(v94.Id) )
    {
      if ( ((fixed + 1073741793) & 0xFFFFFFFB) != 0 )
      {
        LOBYTE(v87) = v28;
        CipReportSharedSectionFailure(v96, v17, v26, (unsigned int)fixed, (_DWORD)v87);
        if ( v92[0] )
        {
          fixed = -1073741701;
          goto LABEL_187;
        }
      }
    }
    if ( !v20 )
      goto LABEL_188;
    if ( (v26 & 0x20000015) != 0 || (PsGetProcessProtection(v96) & 8) == 0 )
      goto LABEL_215;
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
LABEL_212:
        v23 = (*((__int64 (**)(void))&xmmword_18004A650 + 1))();
        if ( !v23 && (v26 & 0xE41FFF87) == 0 )
        {
          Keyword = (_BYTE *)v94.Keyword;
          fixed = 0;
          *(_BYTE *)v94.Keyword = 0;
          *v103 = 0;
          goto LABEL_102;
        }
LABEL_215:
        if ( fixed >= 0 )
        {
          if ( (v26 & 0xE41FFF87) != 0 )
          {
LABEL_221:
            if ( (v26 & 0x20000000) == 0 )
            {
              if ( fixed >= 0 )
                goto LABEL_232;
              if ( fixed == -1073740760
                || fixed == -1073740285
                || fixed == -1058471934
                || (unsigned int)(fixed + 1058471929) <= 6
                || fixed == -1073741554
                || fixed == -1073740283
                || fixed == -1058340861 )
              {
                LOBYTE(v87) = v23;
                fixed = CipReportAndReprieveDriverAndProtectedImageFailure(v20, v96, v17, v26, (_DWORD)v87, fixed);
                if ( fixed >= 0 )
                {
                  *v103 = 0;
                  goto LABEL_232;
                }
              }
              goto LABEL_253;
            }
LABEL_239:
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
LABEL_253:
                CiBlackboxValidateImageHeaderFailure(v20, v96, (_DWORD)v17, v26, v23, fixed);
                goto LABEL_232;
              }
            }
            else
            {
              v83 = *((_DWORD *)g_CipWhichLevelComparisons + (v23 & 0xF));
              if ( _bittest(&v83, *(_BYTE *)v94.Keyword & 0xF) )
              {
LABEL_232:
                if ( (*(_DWORD *)(v20 + 2368) & 2) != 0 )
                {
                  QuadPart = KeQueryPerformanceCounter(0).QuadPart;
                  if ( (unsigned __int8)v23 >= 2u || *(_DWORD *)(v20 + 2344) )
                    v97 = v23;
                  CipProcessSIPolicyLogs(
                    v20,
                    (__int64)&QuadPart,
                    v97,
                    *(_BYTE *)v94.Keyword,
                    (__int64)BaseAddress,
                    Size);
                  if ( (*(_DWORD *)(v20 + 2368) & 1) == 0 && *(__int64 (__fastcall ***)())(v20 + 3040) != &off_18002EEF0 )
                    CiInstrumentVbsPolicyFailure(v20);
                }
                goto LABEL_187;
              }
            }
            v92[0] = 0;
            LOBYTE(v94.Id) = 1;
            LOBYTE(v89) = *(_BYTE *)v94.Keyword;
            fixed = CipReportAndReprieveUMCIFailure(v20, v96, v110, (int)v17, v26, v23, v89, fixed, (__int64)v92, &v94);
            if ( fixed >= 0 )
            {
              if ( v92[0] )
              {
                *(_BYTE *)v94.Keyword = v94.Id;
                *v103 = 0;
              }
              goto LABEL_232;
            }
            goto LABEL_253;
          }
          if ( (*((_DWORD *)g_CipWhichLevelComparisons + (v23 & 0xF)) & 4) != 0 && (g_CiPolicyState & 0x4000) != 0 )
            CiQueryProcessNameAndInstrumentSmartAppControlDecision(v20, (_DWORD)v17, v96, v26, v23, fixed);
        }
        if ( (v26 & 0xE41FFF87) == 0 )
          goto LABEL_239;
        goto LABEL_221;
      }
    }
    else
    {
      v82 = *((_DWORD *)g_CipWhichLevelComparisons + (v23 & 0xF));
      if ( _bittest(&v82, *(_BYTE *)v94.Keyword & 0xF) )
        goto LABEL_212;
    }
    LOBYTE(v81) = v23;
    LOBYTE(v87) = *(_BYTE *)v94.Keyword;
    CipReportPPLAuditFailure(v20, v96, v17, v81, (_DWORD)v87, fixed);
    goto LABEL_212;
  }
  v29 = v26 & 0xE41FFF87;
  if ( (v26 & 0xE41FFF87) != 0 )
    goto LABEL_17;
  if ( v23 )
  {
    if ( v23 != 2 && v23 != 9 )
      goto LABEL_17;
    v30 = (*((unsigned __int8 (**)(void))&xmmword_18004A650 + 1))() == 0;
    goto LABEL_12;
  }
  if ( (*((unsigned __int8 (**)(void))&xmmword_18004A650 + 1))() == 2 )
  {
    v23 = 2;
    a12 = 2;
    goto LABEL_17;
  }
  if ( !(*((unsigned __int8 (**)(void))&xmmword_18004A650 + 1))() )
  {
    v30 = (v26 & 0x2000000) == 0;
LABEL_12:
    if ( v30 )
    {
      Keyword = (_BYTE *)v94.Keyword;
      v31 = v103;
      *(_BYTE *)v94.Keyword = 0;
      *v31 = 0;
LABEL_14:
      v27 = v93;
      fixed = 0;
      v17 = FileObject;
      goto LABEL_189;
    }
  }
LABEL_17:
  if ( (unsigned int)Feature_CodeIntegrity_TrustedLaunchPolicy__private_IsEnabledDeviceUsageNoInline() )
  {
    ActionsForImageWithToken = CiGetActionsForImageWithToken(v96, v110, (__int64)FileObject, v26, v23, &v107);
    ActionsForImage = v107;
    fixed = ActionsForImageWithToken;
    if ( ActionsForImageWithToken < 0 )
    {
LABEL_22:
      v27 = v93;
LABEL_23:
      v17 = FileObject;
LABEL_188:
      Keyword = (_BYTE *)v94.Keyword;
      goto LABEL_189;
    }
    v33 = FileObject;
  }
  else
  {
    if ( (unsigned int)Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline() )
    {
      v92[0] = 0;
      fixed = CipIsTrustedLaunch(v110, v26, v92);
      if ( fixed < 0 )
        goto LABEL_22;
      if ( v92[0] )
      {
        fixed = CipGetTrustedLaunchPackage(v110, &DestinationString);
        if ( fixed < 0 )
          goto LABEL_22;
      }
    }
    IsEnabledDeviceUsageNoInline = Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline();
    v33 = FileObject;
    if ( IsEnabledDeviceUsageNoInline )
      v35 = DestinationString.Buffer != 0;
    else
      v35 = 0;
    ActionsForImage = CiGetActionsForImage(v96, (__int64)FileObject, v26, v35, v23);
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
  if ( !v29 && (unsigned __int8)CipIsFileInUMCIExclusionPaths(v33) )
  {
    Keyword = (_BYTE *)v94.Keyword;
    v36 = v103;
    *(_BYTE *)v94.Keyword = v23;
    *v36 = 0;
    goto LABEL_14;
  }
  v92[0] = 0;
  if ( (ActionsForImage & 1) != 0 )
  {
    v37 = v96;
    fixed = CipValidateFileInCache(
              v33,
              v96,
              v110,
              v23,
              a13,
              (__int64)&v109,
              (__int64)&v113,
              v94.Keyword,
              (__int64)&v112);
    v106 = v112;
    if ( fixed >= 0 )
    {
      if ( (ActionsForImage & 0x10) == 0
        || (v38 = *((_DWORD *)g_CipWhichLevelComparisons + 12), !_bittest(&v38, *(_BYTE *)v94.Keyword & 0xF)) )
      {
        if ( (v112 & 0x10) == 0 )
        {
          if ( !(unsigned int)PsIsProtectedProcess(v37)
            || (v106 & 0x40) != 0
            || (v26 & 0x10) != 0
            || (unsigned int)PsIsProtectedProcess(v37)
            && (v40 = *((_DWORD *)g_CipWhichLevelComparisons + 12), !_bittest(&v40, *(_BYTE *)v94.Keyword & 0xF)) )
          {
            v17 = FileObject;
            *v103 = (v106 & 0x40) != 0 ? 7 : 2;
            if ( (g_CiDeveloperMode & 0x10000) != 0 )
            {
              LOBYTE(v39) = v23;
              LODWORD(v89) = Size;
              CiAuditImageForHvci(0, v26, v39, v37, v17, BaseAddress, v89, v108, v105);
            }
            v20 = v109;
            v27 = v93;
            goto LABEL_182;
          }
        }
      }
    }
    v20 = v109;
    v102 = v113;
    v22 = (4 * v113) | v22 & 3;
    *v116 = v22;
    if ( v20 && fixed == -1073741267 )
      ActionsForImage = ActionsForImage & 0xFFFFFEFF | *(_DWORD *)(v20 + 3056) & 0x100;
  }
  v41 = v118;
  if ( (ActionsForImage & 0x40) != 0 )
  {
    if ( v118 )
    {
      if ( !v29 && (*(_DWORD *)v118 & 0x10) != 0 && (g_CiPolicyState & 0x40) == 0 && (g_CiPolicyState & 0x80u) == 0 )
      {
        v17 = FileObject;
        v42 = ((__int64 (__fastcall *)(PFILE_OBJECT))xmmword_18004A650)(FileObject);
        v43 = *((_DWORD *)g_CipWhichLevelComparisons + (v23 & 0xF));
        if ( _bittest(&v43, v42 & 0xF) )
        {
          v44 = v103;
          v27 = v93;
          *(_BYTE *)v94.Keyword = v42;
          *v44 = 7;
LABEL_65:
          fixed = 0;
          v28 = 0;
          goto LABEL_183;
        }
      }
    }
  }
  v45 = CipMapEntireImage(v26, ActionsForImage);
  v46 = v115;
  if ( v45 > *v115 )
  {
    *v115 = v45;
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
    LODWORD(v87) = Size;
    ValidationContext = CipAllocateValidationContext(
                          v26,
                          ActionsForImage,
                          (int)FileObject,
                          (int)BaseAddress,
                          (ULONGLONG)v87,
                          v110,
                          v41,
                          v96,
                          (__int64)&v109);
    v20 = v109;
    fixed = ValidationContext;
    if ( ValidationContext < 0 )
      goto LABEL_22;
  }
  v49 = v105;
  v50 = v108;
  *(_DWORD *)(v20 + 3056) = ActionsForImage;
  *(_DWORD *)(v20 + 3032) = v50;
  *(_DWORD *)(v20 + 3036) = v49;
  *(_DWORD *)(v20 + 3336) = v102;
  if ( (unsigned int)Feature_CodeIntegrity_TrustedLaunchPolicy__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( (ActionsForImage & 0x20000) != 0 )
    {
      fixed = CipGetTrustedLaunchPackage(v110, v20 + 3608);
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
    *(struct _UNICODE_STRING *)(v20 + 3608) = DestinationString;
    RtlInitUnicodeString(&DestinationString, 0);
  }
  v51 = BaseAddress;
  v52 = Size;
  if ( *v46 >= 1 )
  {
    if ( *v46 == 2 )
    {
      *(_QWORD *)(v20 + 3344) = BaseAddress;
      *(_DWORD *)(v20 + 3352) = v52;
    }
    else
    {
      *(_QWORD *)(v20 + 3344) = QuadPart;
      *(_DWORD *)(v20 + 3352) = a5;
    }
  }
  if ( (ActionsForImage & 0x100) != 0 )
  {
    v17 = FileObject;
    v53 = CipValidateImageHash(
            (unsigned int)&CipValidateFileHash,
            v20,
            (_DWORD)FileObject,
            v96,
            (__int64)v51,
            v52,
            v26,
            a12,
            a13,
            *(__int64 *)v111,
            (__int64)&v100);
    fixed = v53;
    if ( v53 >= 0 )
    {
LABEL_88:
      v54 = 1;
      goto LABEL_89;
    }
    v30 = *(_QWORD *)(v20 + 3040) == 0;
    v93 = v53;
    if ( v30 )
    {
      v27 = v53;
      *(_QWORD *)(v20 + 3040) = &off_18002EEF0;
      goto LABEL_188;
    }
    ActionsForImage &= ~0x100u;
    *(_DWORD *)(v20 + 3056) = ActionsForImage;
    *(_BYTE *)(v20 + 2680) = 0;
  }
  v54 = 0;
  if ( (ActionsForImage & 4) == 0 )
  {
    v59 = v115;
    goto LABEL_113;
  }
  v57 = CipValidateImageHash(
          (unsigned int)&CipValidatePageHash,
          v20,
          (_DWORD)FileObject,
          v96,
          (__int64)BaseAddress,
          Size,
          v26,
          a12,
          a13,
          *(__int64 *)v111,
          (__int64)&v100);
  v58 = *(__int64 (__fastcall ***)())(v20 + 3040);
  fixed = v57;
  v93 = v57;
  if ( v58 )
  {
    if ( v57 >= 0 )
      goto LABEL_89;
    if ( ((ActionsForImage >> 3) & 1) != 0 && v58 == &off_18002EEF0 )
    {
      v59 = v115;
    }
    else
    {
      v59 = v115;
      if ( *v115 == 1 )
      {
        *v115 = 2;
LABEL_68:
        v47 = v22 & 0xFC | 2;
LABEL_69:
        *v116 = v47;
        goto LABEL_70;
      }
      if ( ((ActionsForImage >> 3) & 1) == 0 )
        goto LABEL_89;
    }
    *(_DWORD *)(v20 + 3056) &= ~4u;
LABEL_113:
    if ( *v59 < 2 )
    {
      *v59 = 2;
      v47 = v22 | 3;
      goto LABEL_69;
    }
    v60 = CipValidateImageHash(
            (unsigned int)&CipValidateFileHash,
            v20,
            (_DWORD)FileObject,
            v96,
            (__int64)BaseAddress,
            Size,
            v26,
            a12,
            a13,
            *(__int64 *)v111,
            (__int64)&v100);
    fixed = v60;
    if ( v60 >= 0 )
      goto LABEL_88;
    if ( !*(_QWORD *)(v20 + 3040) )
    {
      v27 = v60;
      *(_QWORD *)(v20 + 3040) = &off_18002EEF0;
      goto LABEL_23;
    }
LABEL_89:
    v93 = fixed;
    v101 = (ActionsForImage >> 6) & 1;
    if ( v101 )
    {
      if ( fixed >= 0 )
      {
        v55 = v100;
        v56 = *((_DWORD *)g_CipWhichLevelComparisons + 12);
        if ( !_bittest(&v56, *(_BYTE *)(v100 + 52) & 0xF) )
          goto LABEL_120;
        LOBYTE(v88) = 1;
        fixed = CipMitigatePPLBypassThroughInterpreters(
                  FileObject,
                  *(_QWORD *)(v20 + 3344),
                  *(unsigned int *)(v20 + 3352),
                  0,
                  v88);
        if ( fixed >= 0 )
        {
          if ( **(_QWORD **)v111 )
            _InterlockedOr(**(volatile signed __int32 ***)v111, 0x10u);
          goto LABEL_119;
        }
      }
    }
    else if ( fixed >= 0 )
    {
LABEL_119:
      v55 = v100;
LABEL_120:
      if ( (g_CiDeveloperMode & 0x10000) != 0 || (v26 & 5) != 0 && (g_CiDeveloperMode & 0x80u) != 0 )
      {
        v90 = v50;
        v61 = a12;
        LODWORD(v89) = Size;
        LOBYTE(v55) = a12;
        CiAuditImageForHvci(v20, v26, v55, v96, FileObject, BaseAddress, v89, v90, v105);
        v55 = v100;
      }
      else
      {
        v61 = a12;
      }
      *(_BYTE *)v94.Keyword = *(_BYTE *)(v55 + 52);
      if ( ((ActionsForImage >> 6) & 1) == 0
        || (v62 = *((_DWORD *)g_CipWhichLevelComparisons + 12), v63 = 7, !_bittest(&v62, *(_BYTE *)(v55 + 52) & 0xF)) )
      {
        v63 = *(_DWORD *)(v55 + 48);
      }
      *v103 = v63;
      *(_DWORD *)(v20 + 2368) = *(_DWORD *)(v20 + 2368) & 0xFFFFFFFE | ((*(_DWORD *)(v55 + 64) & 4) == 0);
      if ( (*(_BYTE *)(*(_QWORD *)(v20 + 2448) + 32LL) & 2) != 0 )
      {
        v64 = *(const void **)(v100 + 72);
        if ( v64 )
          memmove(*(void **)(v20 + 2352), v64, 4LL * (unsigned int)g_NumberOfSiPolicies);
      }
      if ( (v26 & 5) != 0 )
        CiAuditDriverAllow(FileObject, v26, v100, v20);
      if ( v54 )
      {
        QuadPart = v61 & 0xF;
        v65 = *((_DWORD *)g_CipWhichLevelComparisons + QuadPart);
        if ( _bittest(&v65, *(_BYTE *)v94.Keyword & 0xF) )
        {
          if ( (*(_DWORD *)(v20 + 3056) & 2) != 0 && (*(_DWORD *)(v100 + 64) & 4) == 0 && (v106 & 0x10) == 0 )
          {
            v66 = v102;
            if ( ((ActionsForImage >> 8) & 1) != 0
              && (v102 == 12 && (*(_DWORD *)(v20 + 2368) & 0x400) == 0
               || v102 == 33 && (unsigned __int8)CiDoesFilenameHavePerAppPolicyRules((PCUNICODE_STRING)(v20 + 744))
               || v66 == 34) )
            {
              Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline();
            }
            else if ( !(unsigned int)Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline()
                   || ((ActionsForImage >> 8) & 1) == 0
                   || v66 != 39 )
            {
              v67 = 0;
              CipImageValidityPeriod(v20 + 24, &v124);
              v70 = *(_DWORD *)(v20 + 2368);
              if ( (v70 & 0x400) != 0 )
              {
                v71 = v20 + 2108;
              }
              else
              {
                v71 = 0;
                if ( (v70 & 0x1000) != 0 )
                  v71 = v20 + 2186;
              }
              LOBYTE(v69) = v102 == 25;
              LOBYTE(v68) = *(_BYTE *)v94.Keyword;
              CipGetValidatedSigningLevels(v68, v20, v26, v69, FileObject, (__int64)&Size_4);
              v72 = *(_DWORD *)(v20 + 2096);
              if ( v72 < 0 )
                v67 = v20 + 3356;
              v73 = *(_QWORD *)(v100 + 16);
              if ( v73 && *(_DWORD *)(v73 + 48) )
              {
                CipSetFileCache(
                  FileObject,
                  *(_DWORD *)(*(_QWORD *)(v73 + 40) + 4LL),
                  **(_DWORD **)(v73 + 40),
                  v100 + 88,
                  *(_DWORD *)(v100 + 84),
                  *(_DWORD *)(v100 + 80),
                  v91,
                  v96,
                  v71,
                  Size_4,
                  v72,
                  v67);
              }
              else if ( (*((_DWORD *)g_CipWhichLevelComparisons + QuadPart) & 4) != 0 )
              {
                CipSetFileCache(FileObject, 0, 0, 0, 0, 0, v91, v96, v71, Size_4, v72, v67);
              }
            }
          }
        }
      }
      v74 = v100;
      goto LABEL_163;
    }
    v75 = *(unsigned int *)(v20 + 32);
    if ( (_DWORD)v75 )
      v75 = ((_BYTE)v75 - 1) & 3;
    v74 = v20 + 160 * v75 + 40;
LABEL_163:
    v17 = FileObject;
    v76 = v96;
    v77 = CipCallPeauth((unsigned int)fixed, v20 + 4, v96, v26, v74, FileObject);
    fixed = v77;
    if ( (v26 & 0x2800000) != 0 )
    {
LABEL_187:
      v27 = v93;
      goto LABEL_188;
    }
    if ( v77 < 0 && v77 != -1073740285 && v77 != -1073740283 )
    {
      if ( (g_CiOptions & 4) != 0 && (v26 & 0x80000000) != 0 )
      {
        v27 = v93;
LABEL_181:
        v23 = a12;
        goto LABEL_182;
      }
      if ( ((g_CiOptions & 2) == 0 || (v26 & 1) == 0)
        && (v26 & 0x40000006) == 0
        && ((g_CiOptions & 2) != 0 || (v26 & 1) == 0 || (g_CiPolicyState & 1) == 0 || (*(_DWORD *)(v20 + 2368) & 1) != 0) )
      {
        v23 = a12;
        if ( (v26 & 0x80000001) != 0 )
        {
          LOBYTE(v78) = a12;
          CipReportSystemOptionsReprieve(v17, v76, v26, v78, v77);
          v27 = v93;
          *v103 = 0;
          goto LABEL_65;
        }
        v27 = v93;
LABEL_182:
        v28 = v92[0];
        goto LABEL_183;
      }
    }
    v27 = v93;
    goto LABEL_181;
  }
  v17 = FileObject;
  Keyword = (_BYTE *)v94.Keyword;
  *(_QWORD *)(v20 + 3040) = &off_18002EEF0;
  if ( v57 >= 0 )
  {
    fixed = -1073741801;
LABEL_102:
    v27 = v93;
    goto LABEL_189;
  }
  v27 = v57;
LABEL_189:
  if ( v121 )
  {
    if ( fixed < 0 )
    {
      if ( fixed != -1073741789 && v20 )
        CipBuildSigningInformation(
          v17,
          *(_QWORD *)(v20 + 3024),
          *(unsigned int *)(v20 + 3020),
          *(unsigned int *)(v20 + 3016),
          0,
          v121,
          v117);
      goto LABEL_194;
    }
    v79 = (_DWORD *)v117;
    if ( !v100 )
    {
      *v121 = 0;
      *v79 = 0;
      goto LABEL_256;
    }
    fixed = CipBuildSigningInformation(
              v17,
              v100 + 88,
              *(unsigned int *)(v100 + 84),
              *(unsigned int *)(v100 + 80),
              v100,
              v121,
              v117);
  }
  if ( fixed < 0 )
  {
LABEL_194:
    v80 = *(_QWORD **)v111;
    if ( **(_QWORD **)v111 && !v118 )
    {
      CiReleaseContext();
      *v80 = 0;
    }
    goto LABEL_262;
  }
LABEL_256:
  v84 = *(_QWORD **)v111;
  if ( *Keyword && !**(_QWORD **)v111 )
    **(_QWORD **)v111 = g_CiPolicyGenerationCounter & 0x3FFFFFFFFFFFFFFLL
                      | ((unsigned __int64)(ActionsForImage & 0x18000) << 43);
  if ( v27 >= 0 )
  {
    v85 = *(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)(v20 + 3040) + 8LL);
    if ( v85 )
      fixed = v85(*v84);
  }
LABEL_262:
  if ( v20 )
    CiFreeValidationContext((PVOID)v20);
  if ( (unsigned int)Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline() && DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x63734943u);
  CiLogStatusEventWithCorrelationId((unsigned int)fixed, CiValidateImageHeaderComplete, 0);
  ExReleasePushLockSharedEx(&g_CipPolicyLock, 0);
  KeLeaveCriticalRegion();
  IoClearActivityIdThread(v122);
  return (unsigned int)fixed;
}

```

## disassembly

```asm
0x1800e5fd0  mov     [rsp-8+arg_18], rbx
0x1800e5fd5  push    rbp
0x1800e5fd6  push    rsi
0x1800e5fd7  push    rdi
0x1800e5fd8  push    r12
0x1800e5fda  push    r13
0x1800e5fdc  push    r14
0x1800e5fde  push    r15
0x1800e5fe0  lea     rbp, [rsp-80h]
0x1800e5fe5  sub     rsp, 180h
0x1800e5fec  mov     rax, cs:__security_cookie
0x1800e5ff3  xor     rax, rsp
0x1800e5ff6  mov     [rbp+0B0h+var_38], rax
0x1800e5ffa  mov     rax, [rbp+0B0h+arg_70]
0x1800e6001  mov     r15, rcx
0x1800e6004  mov     rdi, [rbp+0B0h+Process]
0x1800e600b  xorps   xmm0, xmm0
0x1800e600e  mov     r12, [rbp+0B0h+arg_68]
0x1800e6015  mov     [rbp+0B0h+var_E8], rax
0x1800e6019  mov     rax, [rbp+0B0h+arg_40]
0x1800e6020  mov     [rbp+0B0h+var_E0], rdx
0x1800e6024  mov     rdx, [rbp+0B0h+arg_78]
0x1800e602b  mov     [rbp+0B0h+var_C0], rax
0x1800e602f  mov     rax, [rbp+0B0h+arg_50]
0x1800e6036  mov     [rbp+0B0h+FileObject], rcx
0x1800e603a  mov     rcx, [rbp+0B0h+arg_28]
0x1800e6041  mov     [rbp+0B0h+var_68], rdx
0x1800e6045  mov     rdx, [rbp+0B0h+arg_80]
0x1800e604c  mov     qword ptr [rbp+0B0h+var_B8], rax
0x1800e6050  mov     rax, [rax]
0x1800e6053  mov     [rbp+0B0h+var_A0], rcx
0x1800e6057  mov     rcx, [rbp+0B0h+arg_30]
0x1800e605e  mov     [rbp+0B0h+var_90], rdx
0x1800e6062  xor     edx, edx
0x1800e6064  mov     esi, edx
0x1800e6066  mov     [rbp+0B0h+var_88], rax
0x1800e606a  mov     [rbp+0B0h+var_98], rcx
0x1800e606e  mov     ebx, edx
0x1800e6070  movzx   r14d, byte ptr [rcx]
0x1800e6074  mov     eax, r14d
0x1800e6077  mov     [rbp+0B0h+var_C8], rdx
0x1800e607b  shr     eax, 2
0x1800e607e  lea     ecx, [rsi+3]; ControlCode
0x1800e6081  mov     [rbp+0B0h+var_D0], edx
0x1800e6084  mov     [rbp+0B0h+var_F0], edx
0x1800e6087  mov     byte ptr [rbp+0B0h+var_130], dl
0x1800e608a  mov     [rbp+0B0h+var_F8], rdx
0x1800e608e  mov     [rbp+0B0h+var_D4], edx
0x1800e6091  mov     [rbp+0B0h+var_B0], edx
0x1800e6094  mov     [rbp+0B0h+var_CC], edx
0x1800e6097  mov     [rbp+0B0h+var_D8], edx
0x1800e609a  mov     word ptr [rbp+0B0h+Size+4], dx
0x1800e609e  lea     rdx, [rbp+0B0h+ActivityId]; ActivityId
0x1800e60a2  mov     [rbp+0B0h+var_EC], eax
0x1800e60a5  mov     [rbp+0B0h+var_AC], eax
0x1800e60a8  mov     [rbp+0B0h+var_A8], r9
0x1800e60ac  mov     dword ptr [rbp+0B0h+Size], r8d
0x1800e60b0  mov     [rbp+0B0h+var_110], rdi
0x1800e60b4  mov     [rbp+0B0h+var_128.Keyword], r12
0x1800e60b8  movups  [rbp+0B0h+var_48], xmm0
0x1800e60bc  mov     dword ptr [rbp+0B0h+var_130+4], 0C0000428h
0x1800e60c3  movups  xmmword ptr [rbp+0B0h+ActivityId.Data1], xmm0
0x1800e60c7  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x1800e60cb  call    cs:__imp_EtwActivityIdControl
0x1800e60d2  nop     dword ptr [rax+rax+00h]
0x1800e60d7  lea     rcx, [rbp+0B0h+ActivityId]
0x1800e60db  call    cs:__imp_IoSetActivityIdThread
0x1800e60e2  nop     dword ptr [rax+rax+00h]
0x1800e60e7  xor     ecx, ecx; PerformanceFrequency
0x1800e60e9  mov     [rbp+0B0h+var_60], rax
0x1800e60ed  call    cs:__imp_KeQueryPerformanceCounter
0x1800e60f4  nop     dword ptr [rax+rax+00h]
0x1800e60f9  mov     [rbp+0B0h+var_70], rax
0x1800e60fd  mov     byte ptr [r12], 1
0x1800e6102  call    CiInitializePhase2
0x1800e6107  call    cs:__imp_KeEnterCriticalRegion
0x1800e610e  nop     dword ptr [rax+rax+00h]
0x1800e6113  xor     edx, edx
0x1800e6115  lea     rcx, g_CipPolicyLock
0x1800e611c  call    cs:__imp_ExAcquirePushLockSharedEx
0x1800e6123  nop     dword ptr [rax+rax+00h]
0x1800e6128  mov     r13b, [rbp+0B0h+arg_58]
0x1800e612f  lea     rax, CiValidateImageHeaderStart
0x1800e6136  mov     r8d, [rbp+0B0h+arg_48]; int
0x1800e613d  lea     rcx, [r15+58h]; int
0x1800e6141  mov     r9b, r13b; int
0x1800e6144  mov     [rsp+1B0h+var_190], rax; PCEVENT_DESCRIPTOR
0x1800e6149  mov     rdx, rdi; Process
0x1800e614c  call    CiLogFileRequestedValidationEvent
0x1800e6151  mov     rcx, [rbp+0B0h+var_E0]
0x1800e6155  lea     rax, [rbp+0B0h+var_D8]
0x1800e6159  mov     [rsp+1B0h+BaseAddress], rax
0x1800e615e  lea     r9, [rbp+0B0h+var_130]
0x1800e6162  lea     rax, [rbp+0B0h+var_CC]
0x1800e6166  lea     r8, [rbp+0B0h+arg_48]
0x1800e616d  mov     [rsp+1B0h+var_190], rax
0x1800e6172  lea     rdx, [rbp+0B0h+var_F0]
0x1800e6176  call    CipFixImageType
0x1800e617b  mov     edi, eax
0x1800e617d  test    eax, eax
0x1800e617f  js      loc_1800E6836
0x1800e6185  mov     al, byte ptr [rbp+0B0h+var_130]
0x1800e6188  mov     r12d, [rbp+0B0h+arg_48]
0x1800e618f  mov     [rbp+0B0h+var_108], 4
0x1800e6193  mov     byte ptr [rbp+0B0h+var_128.Id], al
0x1800e6196  test    al, al
0x1800e6198  jz      short loc_1800E61CD
0x1800e619a  test    r12b, 8
0x1800e619e  jnz     short loc_1800E61BF
0x1800e61a0  test    r12d, 0E41FFF97h
0x1800e61a7  jnz     short loc_1800E61CD
0x1800e61a9  mov     rcx, [rbp+0B0h+var_110]
0x1800e61ad  call    cs:__imp_PsGetProcessProtection
0x1800e61b4  nop     dword ptr [rax+rax+00h]
0x1800e61b9  and     al, 7
0x1800e61bb  cmp     al, 1
0x1800e61bd  jnz     short loc_1800E61CD
0x1800e61bf  mov     r14d, dword ptr [rbp+0B0h+var_130+4]
0x1800e61c3  mov     cl, 1
0x1800e61c5  mov     byte ptr [rbp+0B0h+var_130], cl
0x1800e61c8  jmp     loc_1800E6D64
0x1800e61cd  mov     r15d, r12d
0x1800e61d0  and     r15d, 0E41FFF87h
0x1800e61d7  jnz     short loc_1800E6230
0x1800e61d9  test    r13b, r13b
0x1800e61dc  jz      short loc_1800E6217
0x1800e61de  cmp     r13b, 2
0x1800e61e2  jz      short loc_1800E61EA
0x1800e61e4  cmp     r13b, 9
0x1800e61e8  jnz     short loc_1800E6230
0x1800e61ea  mov     rax, qword ptr cs:xmmword_18004A650+8
0x1800e61f1  call    _guard_dispatch_icall
0x1800e61f6  test    al, al
0x1800e61f8  jnz     short loc_1800E6230
0x1800e61fa  mov     r12, [rbp+0B0h+var_128.Keyword]
0x1800e61fe  mov     rcx, [rbp+0B0h+var_E8]
0x1800e6202  mov     [r12], bl
0x1800e6206  mov     [rcx], ebx
0x1800e6208  mov     r14d, dword ptr [rbp+0B0h+var_130+4]
0x1800e620c  xor     edi, edi
0x1800e620e  mov     r15, [rbp+0B0h+FileObject]
0x1800e6212  jmp     loc_1800E6DAC
0x1800e6217  mov     rax, qword ptr cs:xmmword_18004A650+8
0x1800e621e  call    _guard_dispatch_icall
0x1800e6223  cmp     al, 2
0x1800e6225  jnz     short loc_1800E626D
0x1800e6227  mov     r13b, al
0x1800e622a  mov     [rbp+0B0h+arg_58], al
0x1800e6230  call    Feature_CodeIntegrity_TrustedLaunchPolicy__private_IsEnabledDeviceUsageNoInline
0x1800e6235  test    eax, eax
0x1800e6237  jz      short loc_1800E6296
0x1800e6239  mov     r8, [rbp+0B0h+FileObject]
0x1800e623d  lea     rax, [rbp+0B0h+var_D0]
0x1800e6241  mov     rdx, [rbp+0B0h+var_C0]
0x1800e6245  mov     r9d, r12d
0x1800e6248  mov     rcx, [rbp+0B0h+var_110]
0x1800e624c  mov     [rsp+1B0h+BaseAddress], rax
0x1800e6251  mov     byte ptr [rsp+1B0h+var_190], r13b
0x1800e6256  call    CiGetActionsForImageWithToken
0x1800e625b  mov     ebx, [rbp+0B0h+var_D0]
0x1800e625e  mov     edi, eax
0x1800e6260  test    eax, eax
0x1800e6262  js      short loc_1800E6289
0x1800e6264  mov     rdi, [rbp+0B0h+FileObject]
0x1800e6268  jmp     loc_1800E6300
0x1800e626d  mov     rax, qword ptr cs:xmmword_18004A650+8
0x1800e6274  call    _guard_dispatch_icall
0x1800e6279  test    al, al
0x1800e627b  jnz     short loc_1800E6230
0x1800e627d  test    r12d, 2000000h
0x1800e6284  jmp     loc_1800E61F8
0x1800e6289  mov     r14d, dword ptr [rbp+0B0h+var_130+4]
0x1800e628d  mov     r15, [rbp+0B0h+FileObject]
0x1800e6291  jmp     loc_1800E6DA8
0x1800e6296  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x1800e629b  test    eax, eax
0x1800e629d  jz      short loc_1800E62D0
0x1800e629f  mov     rcx, [rbp+0B0h+var_C0]
0x1800e62a3  lea     r8, [rbp+0B0h+var_130]
0x1800e62a7  mov     edx, r12d
0x1800e62aa  mov     byte ptr [rbp+0B0h+var_130], bl
0x1800e62ad  call    CipIsTrustedLaunch
0x1800e62b2  mov     edi, eax
0x1800e62b4  test    eax, eax
0x1800e62b6  js      short loc_1800E6289
0x1800e62b8  cmp     byte ptr [rbp+0B0h+var_130], bl
0x1800e62bb  jz      short loc_1800E62D0
0x1800e62bd  mov     rcx, [rbp+0B0h+var_C0]
0x1800e62c1  lea     rdx, [rbp+0B0h+DestinationString]
0x1800e62c5  call    CipGetTrustedLaunchPackage
0x1800e62ca  mov     edi, eax
0x1800e62cc  test    eax, eax
0x1800e62ce  js      short loc_1800E6289
0x1800e62d0  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x1800e62d5  mov     rdi, [rbp+0B0h+FileObject]
0x1800e62d9  mov     r8d, r12d
0x1800e62dc  mov     rcx, [rbp+0B0h+var_110]
0x1800e62e0  mov     rdx, rdi
0x1800e62e3  mov     byte ptr [rsp+1B0h+var_190], r13b
0x1800e62e8  test    eax, eax
0x1800e62ea  jz      short loc_1800E62F6
0x1800e62ec  cmp     [rbp+0B0h+DestinationString.Buffer], rbx
0x1800e62f0  setnz   r9b
0x1800e62f4  jmp     short loc_1800E62F9
0x1800e62f6  xor     r9d, r9d
0x1800e62f9  call    CiGetActionsForImage
0x1800e62fe  mov     ebx, eax
0x1800e6300  mov     ecx, r14d
0x1800e6303  and     ecx, 3
0x1800e6306  jz      short loc_1800E631D
0x1800e6308  sub     ecx, 1
0x1800e630b  jz      short loc_1800E631D
0x1800e630d  sub     ecx, 1
0x1800e6310  jz      short loc_1800E631A
0x1800e6312  cmp     ecx, 1
0x1800e6315  jnz     short loc_1800E631D
0x1800e6317  and     ebx, 0FFFFFFDBh
0x1800e631a  and     ebx, 0FFFFFFFEh
0x1800e631d  test    r15d, r15d
0x1800e6320  jnz     short loc_1800E6341
0x1800e6322  mov     rcx, rdi
0x1800e6325  call    CipIsFileInUMCIExclusionPaths
0x1800e632a  test    al, al
0x1800e632c  jz      short loc_1800E6341
0x1800e632e  mov     r12, [rbp+0B0h+var_128.Keyword]
0x1800e6332  mov     rcx, [rbp+0B0h+var_E8]
0x1800e6336  mov     [r12], r13b
0x1800e633a  mov     [rcx], esi
0x1800e633c  jmp     loc_1800E6208
0x1800e6341  xor     al, al
0x1800e6343  mov     byte ptr [rbp+0B0h+var_130], al
0x1800e6346  test    bl, 1
0x1800e6349  jz      loc_1800E64C5
0x1800e634f  mov     rsi, [rbp+0B0h+var_110]
0x1800e6353  lea     rax, [rbp+0B0h+var_B0]
0x1800e6357  mov     r8, [rbp+0B0h+var_C0]
0x1800e635b  mov     r9d, r12d
0x1800e635e  mov     [rsp+1B0h+var_168], rax
0x1800e6363  mov     rdx, rsi
0x1800e6366  mov     rax, [rbp+0B0h+var_128.Keyword]
0x1800e636a  mov     rcx, rdi
0x1800e636d  mov     [rsp+1B0h+var_170], rax
0x1800e6372  lea     rax, [rbp+0B0h+var_AC]
0x1800e6376  mov     qword ptr [rsp+1B0h+var_178], rax
0x1800e637b  lea     rax, [rbp+0B0h+var_C8]
0x1800e637f  mov     [rsp+1B0h+var_180], rax
0x1800e6384  mov     al, [rbp+0B0h+arg_60]
0x1800e638a  mov     byte ptr [rsp+1B0h+BaseAddress], al
0x1800e638e  mov     byte ptr [rsp+1B0h+var_190], r13b
0x1800e6393  call    CipValidateFileInCache
0x1800e6398  mov     r8d, [rbp+0B0h+var_B0]
0x1800e639c  mov     edi, eax
0x1800e639e  mov     [rbp+0B0h+var_D4], r8d
0x1800e63a2  test    eax, eax
0x1800e63a4  js      loc_1800E6487
0x1800e63aa  test    bl, 10h
0x1800e63ad  jz      short loc_1800E63CC
0x1800e63af  mov     rax, [rbp+0B0h+var_128.Keyword]
0x1800e63b3  movzx   edx, byte ptr [rax]
0x1800e63b6  mov     rax, cs:g_CipWhichLevelComparisons
0x1800e63bd  and     edx, 0Fh
0x1800e63c0  mov     ecx, [rax+30h]
0x1800e63c3  bt      ecx, edx
0x1800e63c6  jb      loc_1800E6487
0x1800e63cc  test    r8b, 10h
0x1800e63d0  jnz     loc_1800E6487
0x1800e63d6  mov     rcx, rsi
0x1800e63d9  call    cs:__imp_PsIsProtectedProcess
0x1800e63e0  nop     dword ptr [rax+rax+00h]
0x1800e63e5  test    eax, eax
0x1800e63e7  jz      short loc_1800E6421
0x1800e63e9  test    byte ptr [rbp+0B0h+var_D4], 40h
0x1800e63ed  jnz     short loc_1800E6421
0x1800e63ef  test    r12b, 10h
0x1800e63f3  jnz     short loc_1800E6421
0x1800e63f5  mov     rcx, rsi
0x1800e63f8  call    cs:__imp_PsIsProtectedProcess
0x1800e63ff  nop     dword ptr [rax+rax+00h]
0x1800e6404  test    eax, eax
0x1800e6406  jz      short loc_1800E6487
0x1800e6408  mov     rax, [rbp+0B0h+var_128.Keyword]
0x1800e640c  movzx   edx, byte ptr [rax]
0x1800e640f  mov     rax, cs:g_CipWhichLevelComparisons
0x1800e6416  and     edx, 0Fh
0x1800e6419  mov     ecx, [rax+30h]
0x1800e641c  bt      ecx, edx
0x1800e641f  jb      short loc_1800E6487
0x1800e6421  mov     r14d, [rbp+0B0h+var_D4]
0x1800e6425  mov     rcx, [rbp+0B0h+var_E8]
0x1800e6429  and     r14b, 40h
0x1800e642d  mov     r15, [rbp+0B0h+FileObject]
0x1800e6431  neg     r14b
0x1800e6434  sbb     eax, eax
0x1800e6436  and     eax, 5
0x1800e6439  add     eax, 2
0x1800e643c  mov     [rcx], eax
0x1800e643e  test    byte ptr cs:g_CiDeveloperMode+2, 1
0x1800e6445  jz      short loc_1800E647A
0x1800e6447  mov     eax, [rbp+0B0h+var_D8]
0x1800e644a  mov     r9, rsi; int
  ... truncated ...
```
