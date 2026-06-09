# CipApplySiPolicyEx

- ea: `0x1800e7db8`
- end: `0x1800e8b5f`
- name: `CipApplySiPolicyEx`
- size: `3495`
- prototype: ``
- caller_count: `3`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800751e4`
- `0x18008b730`
- `0x1800e72e4`

## callees

- `0x18000cf48`
- `0x180011c0c`
- `0x18002c0d0`
- `0x18002c500`
- `0x180059218`
- `0x18005cc04`
- `0x18005d3f0`
- `0x180073904`
- `0x180074bd4`
- `0x1800758d0`
- `0x180079280`
- `0x180079344`
- `0x180091e90`
- `0x18009b158`
- `0x18009be98`
- `0x1800a6ce4`
- `0x1800acf2c`
- `0x1800afb68`
- `0x1800d83a0`
- `0x1800e1de4`
- `0x1800e2334`
- `0x1800e2bb0`
- `0x1800e7db8`
- `0x1800e9aa8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800e7f8e`
- `ntoskrnl!ExAllocatePool2` at `0x1800e8066`
- `ntoskrnl!ExAllocatePool2` at `0x1800e8433`
- `ntoskrnl!ExAllocatePool2` at `0x1800e8b08`
- `ntoskrnl!ExAllocatePool2` at `0x1800e7f8e`
- `ntoskrnl!ExAllocatePool2` at `0x1800e8066`
- `ntoskrnl!ExAllocatePool2` at `0x1800e8433`
- `ntoskrnl!ExAllocatePool2` at `0x1800e8b08`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e847d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e8496`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e847d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e8496`
- `ntoskrnl!ZwClose` at `0x1800e84ab`
- `ntoskrnl!ZwClose` at `0x1800e84ab`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1800e80f6`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1800e80f6`
- `ntoskrnl!RtlQueryPackageClaims` at `0x1800e7fe0`
- `ntoskrnl!RtlQueryPackageClaims` at `0x1800e7fe0`
- `ntoskrnl!RtlCapabilityCheck` at `0x1800e8115`
- `ntoskrnl!RtlCapabilityCheck` at `0x1800e8115`
- `HAL!KeQueryPerformanceCounter` at `0x1800e7ea0`
- `HAL!KeQueryPerformanceCounter` at `0x1800e84b9`
- `HAL!KeQueryPerformanceCounter` at `0x1800e7ea0`
- `HAL!KeQueryPerformanceCounter` at `0x1800e84b9`

## pseudocode

```c
__int64 __fastcall CipApplySiPolicyEx(__int64 a1, char a2, char a3, __int64 a4, __int64 a5, _OWORD *a6)
{
  NTSTATUS v10; // r15d
  void *v11; // rdi
  LARGE_INTEGER PerformanceCounter; // rax
  LARGE_INTEGER v13; // rbx
  __int64 v14; // rcx
  int v15; // eax
  _OWORD *v16; // rax
  char v17; // r13
  _WORD *Pool2; // rax
  PVOID v19; // r12
  int InfoFromFullName; // eax
  NTSTATUS v21; // eax
  int v22; // eax
  unsigned int v23; // r12d
  char v24; // r15
  __int64 i; // rdx
  __int64 v26; // rax
  unsigned int v27; // r14d
  int IsDeveloperModeEnabled; // eax
  char v29; // di
  char v30; // r14
  __int64 v31; // rcx
  unsigned __int8 v32; // al
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 j; // rcx
  __int64 v36; // rax
  char v37; // cl
  char v38; // cl
  __int64 v39; // rcx
  char v40; // al
  char v41; // al
  char v42; // cl
  char v43; // cl
  __int64 v44; // rax
  __int64 v45; // rdi
  __int64 v47; // rcx
  __int64 v48; // r13
  unsigned int v49; // r14d
  unsigned int v50; // r9d
  __int64 v51; // r10
  __int64 v52; // r11
  _BYTE *v53; // r12
  __int64 v54; // rcx
  unsigned __int64 v55; // rdx
  _OWORD *v56; // r14
  _QWORD *v57; // rbx
  unsigned int v58; // edx
  __int64 v59; // r9
  unsigned int v60; // edi
  __int64 v61; // r8
  __int64 v62; // rax
  __int64 v63; // rdi
  unsigned __int64 v64; // rcx
  int v65; // eax
  __int64 v66; // rdx
  int v67; // r13d
  __int64 v68; // r14
  __int64 v69; // rbx
  __int64 v70; // rax
  int v71; // ecx
  __int64 v72; // rcx
  int v73; // eax
  int v74; // eax
  char v75; // r14
  int v76; // ebx
  _OWORD *v77; // rdi
  __int64 v78; // rdx
  unsigned __int64 v79; // rcx
  int v80; // ecx
  __int64 v81; // r12
  __int64 v82; // rdi
  char v83; // [rsp+40h] [rbp-C0h] BYREF
  char v84; // [rsp+41h] [rbp-BFh] BYREF
  char v85; // [rsp+42h] [rbp-BEh]
  char v86; // [rsp+43h] [rbp-BDh]
  char v87; // [rsp+44h] [rbp-BCh]
  _OWORD *v88; // [rsp+48h] [rbp-B8h]
  __int64 v89; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v90; // [rsp+58h] [rbp-A8h]
  ULONG pulResult[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v92; // [rsp+68h] [rbp-98h] BYREF
  __int64 v93; // [rsp+70h] [rbp-90h]
  __int64 v94; // [rsp+78h] [rbp-88h] BYREF
  __int64 v95; // [rsp+80h] [rbp-80h]
  __int64 v96; // [rsp+88h] [rbp-78h]
  __int64 v97; // [rsp+90h] [rbp-70h] BYREF
  __int64 v98; // [rsp+98h] [rbp-68h] BYREF
  __int64 v99; // [rsp+A0h] [rbp-60h]
  PVOID P; // [rsp+A8h] [rbp-58h]
  HANDLE Handle; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v102; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v103; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v104; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v105; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v106[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v107; // [rsp+F0h] [rbp-10h]
  LARGE_INTEGER v108; // [rsp+F8h] [rbp-8h]
  __int128 v109; // [rsp+100h] [rbp+0h] BYREF
  __int128 v110; // [rsp+110h] [rbp+10h]
  __int128 v111; // [rsp+120h] [rbp+20h]
  __int64 v112; // [rsp+130h] [rbp+30h]
  _OWORD v113[3]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v114; // [rsp+168h] [rbp+68h]
  _OWORD v115[3]; // [rsp+170h] [rbp+70h] BYREF

  v96 = a5;
  v95 = a4;
  v114 = 0;
  v87 = a2;
  *((_QWORD *)&v102 + 1) = &qword_180033418;
  v104 = 0;
  v106[1] = L"runFullTrust";
  v10 = 0;
  memset(v113, 0, sizeof(v113));
  *(_QWORD *)&v102 = 0x20000;
  v11 = 0;
  v93 = 0;
  v99 = 0;
  memset(v115, 0, sizeof(v115));
  pulResult[0] = 0;
  v105 = 0;
  v103 = 0;
  v106[0] = 1703960;
  v83 = 0;
  Handle = 0;
  P = 0;
  v94 = 0;
  v89 = 0;
  v84 = 0;
  v98 = 0;
  v97 = 0;
  v92 = 4;
  PerformanceCounter = KeQueryPerformanceCounter(0);
  *(_DWORD *)(a1 + 2368) |= 1u;
  v13 = PerformanceCounter;
  v108 = PerformanceCounter;
  if ( (*(_BYTE *)(*(_QWORD *)(a1 + 2448) + 32LL) & 2) != 0 )
    memset(*(void **)(a1 + 2352), 0, 4LL * (unsigned int)g_NumberOfSiPolicies);
  if ( *(_DWORD *)(a1 + 2344) == 2 )
    goto LABEL_69;
  v14 = 0;
  v90 = *(_DWORD *)(*(_QWORD *)(a1 + 2448) + 36LL);
  if ( a4 && (v14 = *(_QWORD *)(a4 + 16)) != 0 )
  {
    v15 = SIPolicyConvertChainInfo(v14, v113);
    v14 = 0;
    v10 = v15;
    if ( v15 < 0 )
      goto LABEL_69;
    v16 = v113;
  }
  else
  {
    v16 = a6;
  }
  v88 = v16;
  v17 = v14;
  v85 = v14;
  if ( *(_QWORD *)(a1 + 3048) == v14 )
    goto LABEL_35;
  if ( (unsigned __int8)(a2 - 5) <= 1u || (*((_DWORD *)g_CipWhichLevelComparisons + (a2 & 0xF)) & 4) != 0 || a2 == 8 )
  {
    v94 = 256;
    Pool2 = (_WORD *)ExAllocatePool2(256, 256, 1668499779);
    P = Pool2;
    if ( !Pool2 )
    {
LABEL_14:
      v10 = -1073741801;
      goto LABEL_69;
    }
    *Pool2 = 0;
    v10 = RtlQueryPackageClaims(*(_QWORD *)(a1 + 3048), Pool2, &v94, 0, 0, 0, &v103, 0);
    if ( (int)(v10 + 0x80000000) >= 0 && v10 != -1073741275 )
      goto LABEL_69;
    v14 = 0;
    if ( *(_QWORD *)(a1 + 832) )
    {
      v102 = *(_OWORD *)(a1 + 824);
    }
    else if ( v94 )
    {
      v19 = P;
      if ( *(_WORD *)P )
      {
        v11 = (void *)ExAllocatePool2(258, 130, 1919109443);
        if ( !v11 )
          goto LABEL_14;
        InfoFromFullName = CipPackageGetInfoFromFullName(v19, (unsigned int)(v94 - 2), v11);
        v14 = 0;
        v10 = InfoFromFullName;
        if ( InfoFromFullName < 0 )
          goto LABEL_69;
        *(_OWORD *)(a1 + 824) = v102;
        goto LABEL_20;
      }
    }
    if ( v10 >= 0 )
    {
LABEL_20:
      if ( BYTE4(v103) == 2 )
      {
        v85 = 1;
      }
      else if ( BYTE4(v103) == 3 && (unsigned __int8)(a3 - 5) <= 1u )
      {
        v21 = ObOpenObjectByPointer(*(PVOID *)(a1 + 3048), 0x200u, 0, 8u, 0, 0, &Handle);
        v14 = 0;
        if ( v21 >= 0 )
        {
          v22 = RtlCapabilityCheck(Handle, v106, &v83);
          v14 = 0;
          if ( v22 >= 0 && !v83 )
            v17 = 1;
        }
      }
    }
  }
  else
  {
    v14 = 0;
  }
LABEL_35:
  v23 = v14;
  v86 = v14;
  v24 = v14;
  for ( i = v14; i != 6; ++i )
  {
    if ( *(_QWORD *)(16 * i + a1 + 872) != v14 )
    {
      v26 = v23++;
      *((_QWORD *)v115 + v26) = 16 * i + a1 + 864;
      v14 = 0;
    }
  }
  v27 = (unsigned int)g_CiPolicyState >> 8;
  if ( (g_CiPolicyState & 0x200) == 0
    || v87 != 3
    || (IsDeveloperModeEnabled = CipIsDeveloperModeEnabled(&v84), LOBYTE(v14) = 0, IsDeveloperModeEnabled < 0)
    || (v29 = 1, !v84) )
  {
    v29 = v14;
  }
  if ( !v96
    || ((v30 = v27 & 1) != 0 || v29)
    && ((int)CipQueryDynamicCodeTrustClaim(v96, &v89, 1) < 0 || (v86 = v30, (v24 = v29) == 0)) )
  {
    if ( v29 && v95 && *(_BYTE *)(v95 + 52) == 3 )
      v24 = 1;
  }
  v104 = a1 + 848;
  memset((void *)(a1 + 2480), 0, 0x80u);
  v31 = v95;
  *(_QWORD *)(a1 + 2472) = v88;
  if ( v31 )
    v32 = *(_BYTE *)(v31 + 84);
  else
    v32 = *(_BYTE *)(a1 + 3020);
  *(_DWORD *)(a1 + 2488) = v32;
  v33 = v31 + 88;
  if ( !v31 )
    v33 = *(_QWORD *)(a1 + 3024);
  *(_QWORD *)(a1 + 2480) = v33;
  v34 = a1 + 744;
  for ( j = 0; j != 4; ++j )
    *(_QWORD *)(a1 + 2472 + 8 * j + 24) = v34 + 16 * j;
  *(_QWORD *)(a1 + 2528) = *(_QWORD *)(a1 + 840);
  *(_QWORD *)(a1 + 2536) = &v102;
  *(_QWORD *)(a1 + 2544) = v93;
  *(_DWORD *)(a1 + 2568) = *(_QWORD *)(a1 + 856) != 0;
  v36 = *(_QWORD *)(a1 + 856);
  *(_DWORD *)(a1 + 2584) = v23;
  *(_QWORD *)(a1 + 2552) = 0;
  *(_QWORD *)(a1 + 2560) = (unsigned __int64)&v104 & -(__int64)(v36 != 0);
  *(_QWORD *)(a1 + 2576) = v115;
  *(_OWORD *)(a1 + 2624) = 0;
  *(_OWORD *)(a1 + 2640) = 0;
  *(_OWORD *)(a1 + 2656) = 0;
  *(_QWORD *)(a1 + 2672) = 0;
  v37 = *(_BYTE *)(a1 + 2628) & 0xFE;
  *(_DWORD *)(a1 + 2624) = *(_DWORD *)(a1 + 2344);
  v38 = (2 * v85) | (v17 | v37) & 0xFD;
  *(_BYTE *)(a1 + 2628) = v38;
  if ( (*(_DWORD *)(a1 + 2368) & 0x100000) != 0 )
  {
    *(_BYTE *)(a1 + 2628) = v38 | 0x10;
    *(_DWORD *)(a1 + 2588) = *(_DWORD *)(a1 + 2372);
  }
  else
  {
    *(_DWORD *)(a1 + 2588) = *(_DWORD *)(a1 + 3036);
    *(_DWORD *)(a1 + 2592) = *(_DWORD *)(a1 + 3032);
  }
  v39 = *(_QWORD *)(a1 + 2320);
  v112 = 0;
  v109 = 0;
  v110 = 0;
  v111 = 0;
  if ( v39 )
  {
    *(_QWORD *)&v109 = v39 + 16;
    *((_QWORD *)&v109 + 1) = *(_QWORD *)v39;
    LODWORD(v110) = *(_DWORD *)(v39 + 8);
    *((_QWORD *)&v110 + 1) = v39 + 72;
    *(_QWORD *)&v111 = v39 + 88;
    *((_QWORD *)&v111 + 1) = *(_QWORD *)(v39 + 104);
    *(_QWORD *)(a1 + 2600) = &v109;
    v112 = 0;
  }
  v40 = v86;
  *(_OWORD *)(a1 + 2608) = 0;
  *(_BYTE *)(a1 + 2617) = v40;
  *(_BYTE *)(a1 + 2616) = v87;
  *(_BYTE *)(a1 + 2618) = v24;
  *(_QWORD *)(a1 + 2608) = a1;
  Feature_Servicing_WdacAppidTaggingPerfImprovements_44681456__private_IsEnabledPreCheck(v39, v34, 0);
  v41 = *(_BYTE *)(a1 + 2628) & 0xF7;
  v42 = ~(unsigned __int8)(*(_DWORD *)a1 >> 1);
  *(_QWORD *)(a1 + 2632) = a1 + 2608;
  v43 = v41 | v42 & 8;
  *(_QWORD *)(a1 + 2640) = CipExternalAuthorizationCallback;
  v44 = v90;
  *(_BYTE *)(a1 + 2628) = v43;
  v10 = RtlULongLongToULong(24 * v44, pulResult);
  if ( v10 < 0 )
    goto LABEL_68;
  v45 = ExAllocatePool2(256, pulResult[0], 1769163075);
  v99 = v45;
  if ( !v45 )
  {
    v10 = -1073741801;
LABEL_68:
    v11 = 0;
    goto LABEL_69;
  }
  v47 = *(_QWORD *)(a1 + 2448);
  v96 = 0;
  LODWORD(v93) = -1;
  v10 = 0;
  v48 = 0;
  SIPolicyObjectValidationEngine(v47, a1 + 2624, a1 + 2472, v45);
  v49 = v90;
  v50 = 0;
  if ( v90 )
  {
    v51 = 0x48F222A00D2EB091LL;
    v52 = SiPolicyIDEndpointSec;
    while ( 1 )
    {
      v53 = (_BYTE *)(v45 + 24LL * v50);
      v54 = *(_QWORD *)v53;
      v55 = -(__int64)(*(_DWORD *)(*(_QWORD *)v53 + 40LL) < 6u) & 0xFFFFFFFFFFFFFD40uLL;
      if ( *(_QWORD *)(v55 + *(_QWORD *)v53 + 720) == v52
        && *(_QWORD *)(v55 + v54 + 728) == v51
        && (unsigned __int8)SIPolicyIsBasePolicy(v54) )
      {
        break;
      }
      if ( ++v50 >= v49 )
      {
        v53 = 0;
        goto LABEL_83;
      }
    }
    v53[8] = (int)SIPolicyAggregatePolicyValidationResult(v53, v45, v49, &v105) >= 0;
    v52 = SiPolicyIDEndpointSec;
LABEL_83:
    LODWORD(v89) = 0;
    v56 = 0;
    v88 = 0;
    while ( 1 )
    {
      v57 = g_SiPolicyHandles;
      v58 = 0;
      v59 = *((_QWORD *)g_SiPolicyHandles + (_QWORD)v56);
      do
      {
        v60 = v58;
        v61 = *(_QWORD *)(v99 + 24LL * v58);
        if ( v61 == v59 )
          break;
        ++v58;
      }
      while ( v58 < v90 );
      v62 = v60 + 1;
      if ( v61 == v59 )
        v62 = v60;
      v63 = v99 + 24 * v62;
      v107 = v63;
      v64 = -(__int64)(*(_DWORD *)(*(_QWORD *)v63 + 40LL) < 6u) & 0xFFFFFFFFFFFFFD40uLL;
      if ( *(_QWORD *)(v64 + *(_QWORD *)v63 + 720) == v52
        && *(_QWORD *)(v64 + *(_QWORD *)v63 + 728) == 0x48F222A00D2EB091LL )
      {
        *(_DWORD *)(*(_QWORD *)(a1 + 2352) + 4LL * (_QWORD)v56) = 0;
        *(_QWORD *)(*(_QWORD *)(a1 + 2360) + 8LL * (_QWORD)v56) = *(_QWORD *)v63;
        *(_DWORD *)(a1 + 2368) |= 2u;
LABEL_92:
        v65 = v89;
        goto LABEL_93;
      }
      pulResult[0] = SIPolicyAggregatePolicyValidationResult(v63, v99, v90, 0);
      v67 = pulResult[0];
      if ( (pulResult[0] & 0x80000000) != 0 && v53 && v53[8] )
      {
        v68 = *(_QWORD *)v63;
        if ( !(unsigned __int8)SIPolicyIsSystemPolicy(
                                 *(_QWORD *)v63
                               + (-(__int64)(*(_DWORD *)(*(_QWORD *)v63 + 40LL) < 6u) & 0xFFFFFFFFFFFFFD50uLL)
                               + 704,
                                 v66,
                                 0)
          && ((*(_DWORD *)(v68 + 672) & 8) == 0 || (*(_DWORD *)(v68 + 44) & 0x10000) != 0) )
        {
          *(_DWORD *)(v63 + 20) |= 0x10000000u;
          v67 = 0;
          pulResult[0] = 0;
          *(_WORD *)(v63 + 8) = 1;
          *(_DWORD *)(v63 + 12) = 0;
          v96 = v68;
        }
        v56 = v88;
      }
      if ( v67 < 0 )
      {
        SIPolicyProcessDbgSettingAndReprieve(
          *(_QWORD *)(a1 + 2448),
          v57[(_QWORD)v56],
          a1 + 808,
          *(_DWORD *)(a1 + 2344),
          1,
          (__int64)pulResult,
          0,
          0);
        v67 = pulResult[0];
        if ( (pulResult[0] & 0x80000000) == 0 )
          *(_DWORD *)(v63 + 20) |= 0x800000u;
      }
      v70 = *(_QWORD *)(a1 + 2352);
      *(_QWORD *)pulResult = *(_QWORD *)v63;
      v69 = *(_QWORD *)pulResult;
      *(_DWORD *)(v70 + 4LL * (_QWORD)v56) = v67;
      *(_QWORD *)(*(_QWORD *)(a1 + 2360) + 8LL * (_QWORD)v56) = v69;
      *(_DWORD *)(a1 + 2368) |= 2u;
      if ( v67 >= 0 )
      {
        v71 = *(_DWORD *)(*(_QWORD *)(a1 + 2296) + 4LL * (_QWORD)v56);
        if ( v71 < 0 )
        {
          *(_BYTE *)(v63 + 9) = 1;
          v67 = v71;
          *(_DWORD *)(v63 + 16) = *(_DWORD *)(*(_QWORD *)(a1 + 2304) + 4LL * (_QWORD)v56);
          *(_DWORD *)(v63 + 20) = *(_DWORD *)(*(_QWORD *)(a1 + 2312) + 4LL * (_QWORD)v56);
        }
      }
      else if ( *(_BYTE *)(v63 + 9) )
      {
        *(_DWORD *)(*(_QWORD *)(a1 + 2296) + 4LL * (_QWORD)v56) = v67;
        *(_DWORD *)(*(_QWORD *)(a1 + 2304) + 4LL * (_QWORD)v56) = *(_DWORD *)(v63 + 16);
        *(_DWORD *)(*(_QWORD *)(a1 + 2312) + 4LL * (_QWORD)v56) = *(_DWORD *)(v63 + 20);
      }
      v72 = *(_QWORD *)(a1 + 984);
      if ( v72 )
      {
        v73 = *(_DWORD *)(v69 + 44);
        if ( (v73 & 0x10) != 0 || (v73 & 0x8000000) != 0 )
        {
          if ( (*(_DWORD *)(a1 + 2368) & 0x400) != 0 )
          {
            v74 = *(_DWORD *)(a1 + 2116);
            LODWORD(v93) = v74;
          }
          else
          {
            v74 = v93;
          }
          CiLogSIPolicySmartlockerEvent((const wchar_t *)(v72 + 88), v89, *(_DWORD *)(v63 + 16), v74, v67);
        }
      }
      if ( *(_DWORD *)(a1 + 2344) == 1 && (*(_DWORD *)(*((_QWORD *)g_SiPolicyHandles + (_QWORD)v56) + 672LL) & 8) != 0 )
      {
        if ( (*(_DWORD *)a1 & 0x10) == 0 )
        {
          if ( v67 >= 0 )
            goto LABEL_153;
          v75 = 0;
          if ( (unsigned __int8)SIPolicyAppIdTaggingEnforceDLL() )
          {
LABEL_127:
            v76 = 0;
            if ( (int)SIPolicyEnumerateOneSecurityPolicyKey(
                        *((_QWORD *)g_SiPolicyHandles + (_QWORD)v88),
                        (unsigned int)&qword_180030940,
                        (unsigned int)&qword_180030980,
                        0,
                        (__int64)&v98,
                        (__int64)&v92,
                        (__int64)&v97) >= 0 )
            {
              v77 = v88;
              do
              {
                if ( v92 == 3 && v75 )
                  CiAddAppIdTaggingClaimsToOriginClaim(a1 + 992, v98, v97);
                ++v76;
              }
              while ( (int)SIPolicyEnumerateOneSecurityPolicyKey(
                             *((_QWORD *)g_SiPolicyHandles + (_QWORD)v77),
                             (unsigned int)&qword_180030940,
                             (unsigned int)&qword_180030980,
                             v76,
                             (__int64)&v98,
                             (__int64)&v92,
                             (__int64)&v97) >= 0 );
              v63 = v107;
            }
            v69 = *(_QWORD *)pulResult;
          }
          v56 = v88;
          goto LABEL_136;
        }
        if ( v67 < 0 )
          goto LABEL_137;
        if ( (*(_DWORD *)(v63 + 20) & 0x800000) == 0 )
        {
          v75 = 1;
          goto LABEL_127;
        }
      }
LABEL_136:
      if ( v67 >= 0 )
        goto LABEL_153;
LABEL_137:
      if ( !(unsigned __int8)SIPolicyVerifiedAndReputableAllowUnknown(v69, v66, 0) )
        *(_DWORD *)(a1 + 2368) &= ~1u;
      if ( (*(_DWORD *)(v69 + 44) & 0x10000) == 0 )
      {
        v78 = v95;
        goto LABEL_148;
      }
      if ( *(_BYTE *)(v63 + 9) )
        *(_DWORD *)(a1 + 28) = 26;
      v78 = v95;
      if ( v95 && *(_DWORD *)(v95 + 60) != 26 )
        *(_DWORD *)(v95 + 60) = *(_BYTE *)(v63 + 9) != 0 ? 26 : 21;
      if ( (*(_DWORD *)(a1 + 2368) & 0x40) != 0 )
      {
        *(_BYTE *)(v63 + 9) = 0;
LABEL_148:
        if ( v10 >= 0 )
        {
          v10 = v67;
          *(_DWORD *)(a1 + 968) = v89;
          *(_DWORD *)(a1 + 2084) = *(_DWORD *)(v63 + 16);
          *(_DWORD *)(a1 + 2088) = *(_DWORD *)(v63 + 20);
        }
        if ( *(_BYTE *)(v63 + 9) )
        {
          *(_DWORD *)(a1 + 24) = 26;
          if ( v78 )
            *(_DWORD *)(v78 + 56) = 26;
        }
      }
LABEL_153:
      if ( (g_CiPolicyState & 0x4000) == 0 )
        goto LABEL_92;
      v79 = -(__int64)(*(_DWORD *)(v69 + 40) < 6u) & 0xFFFFFFFFFFFFFD50uLL;
      if ( *(_OWORD *)(v79 + v69 + 704) != SiPolicyIDNightsWatchDesktop
        && *(_OWORD *)(v79 + v69 + 704) != SiPolicyIDNightsWatchDesktopEval )
      {
        goto LABEL_92;
      }
      *(_DWORD *)(a1 + 2072) = *(_DWORD *)(v63 + 16);
      *(_DWORD *)(a1 + 2076) = *(_DWORD *)(v63 + 20);
      v80 = *(_DWORD *)(*(_QWORD *)(a1 + 2352) + 4LL * (_QWORD)v56);
      v65 = v89;
      *(_DWORD *)(a1 + 2100) = v89;
      *(_DWORD *)(a1 + 2096) = v80;
LABEL_93:
      v56 = (_OWORD *)((char *)v56 + 1);
      LODWORD(v89) = v65 + 1;
      v88 = v56;
      if ( v65 + 1 >= v90 )
      {
        v13 = v108;
        v48 = v96;
        break;
      }
      v52 = SiPolicyIDEndpointSec;
    }
  }
  v81 = *(_QWORD *)(a1 + 984);
  *(_QWORD *)(a1 + 2456) = v105;
  *(_QWORD *)(a1 + 2464) = v48;
  if ( v81 && (*(_DWORD *)(a1 + 992) || *(_QWORD *)(a1 + 1520)) )
  {
    v82 = ExAllocatePool2(256, 568, 1668499779);
    if ( !v82 )
      goto LABEL_68;
    *(_QWORD *)(v82 + 560) = v81;
    if ( (int)CipDuplicateCodeIntegrityOriginClaimMembers(a1 + 992, v82) < 0 )
      CipDeleteOriginEntryCallback(v82 + 536, 0);
    else
      CipInsertOriginEntryIntoTable(v82);
    v11 = 0;
  }
  else
  {
    v11 = 0;
  }
LABEL_69:
  SIPolicyFreeSIChainInfo(v113);
  SIPolicyFree(v99);
  if ( P )
    ExFreePoolWithTag(P, 0x63734943u);
  if ( v11 )
    ExFreePoolWithTag(v11, 0x72634943u);
  if ( Handle )
    ZwClose(Handle);
  *(_QWORD *)(a1 + 960) = (unsigned __int64)(1000000 * (*(_QWORD *)&KeQueryPerformanceCounter(0) - v13.QuadPart))
                        / g_CiPerfFrequency.QuadPart;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800e7db8  mov     [rsp-8+arg_8], rbx
0x1800e7dbd  push    rbp
0x1800e7dbe  push    rsi
0x1800e7dbf  push    rdi
0x1800e7dc0  push    r12
0x1800e7dc2  push    r13
0x1800e7dc4  push    r14
0x1800e7dc6  push    r15
0x1800e7dc8  lea     rbp, [rsp-0B0h]
0x1800e7dd0  sub     rsp, 1B0h
0x1800e7dd7  mov     rax, cs:__security_cookie
0x1800e7dde  xor     rax, rsp
0x1800e7de1  mov     [rbp+0E0h+var_40], rax
0x1800e7de8  mov     rax, [rbp+0E0h+arg_20]
0x1800e7def  xorps   xmm0, xmm0
0x1800e7df2  mov     [rbp+0E0h+var_158], rax
0x1800e7df6  mov     rsi, rcx
0x1800e7df9  xor     ecx, ecx; PerformanceFrequency
0x1800e7dfb  movzx   r12d, dl
0x1800e7dff  xor     eax, eax
0x1800e7e01  mov     [rbp+0E0h+var_160], r9
0x1800e7e05  mov     [rbp+0E0h+var_78], rax
0x1800e7e09  mov     r13, r9
0x1800e7e0c  lea     rax, qword_180033418
0x1800e7e13  mov     [rsp+1E0h+var_19C], r12b
0x1800e7e18  mov     qword ptr [rbp+0E0h+var_128+8], rax
0x1800e7e1c  mov     r14b, r8b
0x1800e7e1f  lea     rax, aRunfulltrust; "runFullTrust"
0x1800e7e26  mov     [rbp+0E0h+var_110], rcx
0x1800e7e2a  mov     [rbp+0E0h+var_F8], rax
0x1800e7e2e  mov     r15d, ecx
0x1800e7e31  movups  [rbp+0E0h+var_A8], xmm0
0x1800e7e35  mov     qword ptr [rbp+0E0h+var_128], 20000h
0x1800e7e3d  mov     edi, ecx
0x1800e7e3f  movups  [rbp+0E0h+var_98], xmm0
0x1800e7e43  mov     [rsp+1E0h+var_170], rcx
0x1800e7e48  movups  [rbp+0E0h+var_88], xmm0
0x1800e7e4c  mov     [rbp+0E0h+var_140], rcx
0x1800e7e50  movups  [rbp+0E0h+var_70], xmm0
0x1800e7e54  mov     [rsp+1E0h+pulResult], ecx
0x1800e7e58  movups  [rbp+0E0h+var_60], xmm0
0x1800e7e5f  mov     [rbp+0E0h+var_108], rcx
0x1800e7e63  movups  [rbp+0E0h+var_50], xmm0
0x1800e7e6a  mov     [rbp+0E0h+var_118], rcx
0x1800e7e6e  mov     [rbp+0E0h+var_100], 1A0018h
0x1800e7e76  mov     [rsp+1E0h+var_1A0], cl
0x1800e7e7a  mov     [rbp+0E0h+var_130], rcx
0x1800e7e7e  mov     [rbp+0E0h+P], rcx
0x1800e7e82  mov     [rsp+1E0h+var_168], rcx
0x1800e7e87  mov     [rsp+1E0h+var_190], rcx
0x1800e7e8c  mov     [rsp+1E0h+var_19F], cl
0x1800e7e90  mov     [rbp+0E0h+var_148], rcx
0x1800e7e94  mov     [rbp+0E0h+var_150], rcx
0x1800e7e98  mov     [rsp+1E0h+var_178], 4
0x1800e7ea0  call    cs:__imp_KeQueryPerformanceCounter
0x1800e7ea7  nop     dword ptr [rax+rax+00h]
0x1800e7eac  or      dword ptr [rsi+940h], 1
0x1800e7eb3  mov     rbx, rax
0x1800e7eb6  mov     [rbp+0E0h+var_E8], rax
0x1800e7eba  mov     rax, [rsi+990h]
0x1800e7ec1  test    byte ptr [rax+20h], 2
0x1800e7ec5  jz      short loc_1800E7EE0
0x1800e7ec7  mov     r8d, cs:g_NumberOfSiPolicies
0x1800e7ece  xor     edx, edx; Val
0x1800e7ed0  mov     rcx, [rsi+930h]; void *
0x1800e7ed7  shl     r8, 2; Size
0x1800e7edb  call    memset
0x1800e7ee0  cmp     dword ptr [rsi+928h], 2
0x1800e7ee7  jz      loc_1800E845A
0x1800e7eed  mov     rax, [rsi+990h]
0x1800e7ef4  xor     ecx, ecx
0x1800e7ef6  mov     eax, [rax+24h]
0x1800e7ef9  mov     [rsp+1E0h+var_188], eax
0x1800e7efd  test    r13, r13
0x1800e7f00  jz      short loc_1800E7F27
0x1800e7f02  mov     rcx, [r13+10h]
0x1800e7f06  test    rcx, rcx
0x1800e7f09  jz      short loc_1800E7F27
0x1800e7f0b  lea     rdx, [rbp+0E0h+var_A8]
0x1800e7f0f  call    SIPolicyConvertChainInfo
0x1800e7f14  xor     ecx, ecx
0x1800e7f16  mov     r15d, eax
0x1800e7f19  test    eax, eax
0x1800e7f1b  js      loc_1800E845A
0x1800e7f21  lea     rax, [rbp+0E0h+var_A8]
0x1800e7f25  jmp     short loc_1800E7F2E
0x1800e7f27  mov     rax, [rbp+0E0h+arg_28]
0x1800e7f2e  mov     r9d, 100h
0x1800e7f34  mov     [rsp+1E0h+var_198], rax
0x1800e7f39  mov     r8d, 1
0x1800e7f3f  movzx   r13d, cl
0x1800e7f43  mov     [rsp+1E0h+var_19E], cl
0x1800e7f47  cmp     [rsi+0BE8h], rcx
0x1800e7f4e  jz      loc_1800E813F
0x1800e7f54  lea     eax, [r12-5]
0x1800e7f59  cmp     al, r8b
0x1800e7f5c  jbe     short loc_1800E7F7D
0x1800e7f5e  mov     rax, cs:g_CipWhichLevelComparisons
0x1800e7f65  mov     rcx, r12
0x1800e7f68  and     ecx, 0Fh
0x1800e7f6b  mov     ecx, [rax+rcx*4]
0x1800e7f6e  test    cl, 4
0x1800e7f71  jnz     short loc_1800E7F7D
0x1800e7f73  cmp     r12b, 8
0x1800e7f77  jnz     loc_1800E8135
0x1800e7f7d  mov     r8d, 63734943h
0x1800e7f83  mov     [rsp+1E0h+var_168], r9
0x1800e7f88  mov     rdx, r9
0x1800e7f8b  mov     rcx, r9
0x1800e7f8e  call    cs:__imp_ExAllocatePool2
0x1800e7f95  nop     dword ptr [rax+rax+00h]
0x1800e7f9a  xor     edx, edx
0x1800e7f9c  mov     [rbp+0E0h+P], rax
0x1800e7fa0  mov     rcx, rax
0x1800e7fa3  test    rax, rax
0x1800e7fa6  jnz     short loc_1800E7FB3
0x1800e7fa8  mov     r15d, 0C0000017h
0x1800e7fae  jmp     loc_1800E845A
0x1800e7fb3  mov     [rsp+1E0h+var_1A8], rdx
0x1800e7fb8  lea     r8, [rsp+1E0h+var_168]
0x1800e7fbd  mov     [rax], dx
0x1800e7fc0  xor     r9d, r9d
0x1800e7fc3  lea     rax, [rbp+0E0h+var_118]
0x1800e7fc7  mov     [rsp+1E0h+Handle], rax
0x1800e7fcc  mov     qword ptr [rsp+1E0h+AccessMode], rdx
0x1800e7fd1  mov     [rsp+1E0h+ObjectType], rdx
0x1800e7fd6  mov     rdx, rcx
0x1800e7fd9  mov     rcx, [rsi+0BE8h]
0x1800e7fe0  call    cs:__imp_RtlQueryPackageClaims
0x1800e7fe7  nop     dword ptr [rax+rax+00h]
0x1800e7fec  mov     ecx, 80000000h
0x1800e7ff1  mov     r15d, eax
0x1800e7ff4  add     eax, ecx
0x1800e7ff6  test    ecx, eax
0x1800e7ff8  jnz     short loc_1800E8007
0x1800e7ffa  cmp     r15d, 0C0000225h
0x1800e8001  jnz     loc_1800E845A
0x1800e8007  xor     ecx, ecx
0x1800e8009  cmp     [rsi+340h], rcx
0x1800e8010  jz      short loc_1800E8044
0x1800e8012  movups  xmm0, xmmword ptr [rsi+338h]
0x1800e8019  movdqu  [rbp+0E0h+var_128], xmm0
0x1800e801e  test    r15d, r15d
0x1800e8021  js      loc_1800E8139
0x1800e8027  movzx   eax, byte ptr [rbp+0E0h+var_118+4]
0x1800e802b  mov     r8d, 1
0x1800e8031  cmp     eax, 2
0x1800e8034  jnz     loc_1800E80C1
0x1800e803a  mov     [rsp+1E0h+var_19E], r8b
0x1800e803f  jmp     loc_1800E813F
0x1800e8044  cmp     [rsp+1E0h+var_168], rcx
0x1800e8049  jbe     short loc_1800E801E
0x1800e804b  mov     r12, [rbp+0E0h+P]
0x1800e804f  cmp     [r12], cx
0x1800e8054  jz      short loc_1800E801E
0x1800e8056  mov     edx, 82h
0x1800e805b  mov     ecx, 102h
0x1800e8060  mov     r8d, 72634943h
0x1800e8066  call    cs:__imp_ExAllocatePool2
0x1800e806d  nop     dword ptr [rax+rax+00h]
0x1800e8072  mov     rdi, rax
0x1800e8075  test    rax, rax
0x1800e8078  jz      loc_1800E7FA8
0x1800e807e  mov     edx, dword ptr [rsp+1E0h+var_168]
0x1800e8082  lea     rax, [rbp+0E0h+var_128]
0x1800e8086  mov     qword ptr [rsp+1E0h+AccessMode], rax
0x1800e808b  add     edx, 0FFFFFFFEh
0x1800e808e  lea     rax, [rsp+1E0h+var_170]
0x1800e8093  mov     r8, rdi
0x1800e8096  mov     rcx, r12
0x1800e8099  mov     [rsp+1E0h+ObjectType], rax
0x1800e809e  call    CipPackageGetInfoFromFullName
0x1800e80a3  xor     ecx, ecx
0x1800e80a5  mov     r15d, eax
0x1800e80a8  test    eax, eax
0x1800e80aa  js      loc_1800E845A
0x1800e80b0  movups  xmm0, [rbp+0E0h+var_128]
0x1800e80b4  movdqu  xmmword ptr [rsi+338h], xmm0
0x1800e80bc  jmp     loc_1800E8027
0x1800e80c1  cmp     eax, 3
0x1800e80c4  jnz     short loc_1800E813F
0x1800e80c6  sub     r14b, 5
0x1800e80ca  cmp     r14b, r8b
0x1800e80cd  ja      short loc_1800E813F
0x1800e80cf  lea     rax, [rbp+0E0h+var_130]
0x1800e80d3  mov     r9d, 8; DesiredAccess
0x1800e80d9  mov     [rsp+1E0h+Handle], rax; Handle
0x1800e80de  xor     r8d, r8d; PassedAccessState
0x1800e80e1  mov     [rsp+1E0h+AccessMode], cl; AccessMode
0x1800e80e5  mov     edx, 200h; HandleAttributes
0x1800e80ea  mov     [rsp+1E0h+ObjectType], rcx; ObjectType
0x1800e80ef  mov     rcx, [rsi+0BE8h]; Object
0x1800e80f6  call    cs:__imp_ObOpenObjectByPointer
0x1800e80fd  nop     dword ptr [rax+rax+00h]
0x1800e8102  xor     ecx, ecx
0x1800e8104  test    eax, eax
0x1800e8106  js      short loc_1800E8139
0x1800e8108  mov     rcx, [rbp+0E0h+var_130]
0x1800e810c  lea     r8, [rsp+1E0h+var_1A0]
0x1800e8111  lea     rdx, [rbp+0E0h+var_100]
0x1800e8115  call    cs:__imp_RtlCapabilityCheck
0x1800e811c  nop     dword ptr [rax+rax+00h]
0x1800e8121  xor     ecx, ecx
0x1800e8123  lea     r8d, [rcx+1]
0x1800e8127  test    eax, eax
0x1800e8129  js      short loc_1800E813F
0x1800e812b  cmp     [rsp+1E0h+var_1A0], cl
0x1800e812f  cmovz   r13d, r8d
0x1800e8133  jmp     short loc_1800E813F
0x1800e8135  xor     ecx, ecx
0x1800e8137  jmp     short loc_1800E813F
0x1800e8139  mov     r8d, 1
0x1800e813f  mov     r12d, ecx
0x1800e8142  mov     [rsp+1E0h+var_19D], cl
0x1800e8146  mov     r15b, cl
0x1800e8149  mov     rdx, rcx
0x1800e814c  mov     rax, rdx
0x1800e814f  shl     rax, 4
0x1800e8153  cmp     [rax+rsi+368h], rcx
0x1800e815b  jz      short loc_1800E8174
0x1800e815d  lea     rcx, [rsi+360h]
0x1800e8164  add     rcx, rax
0x1800e8167  mov     eax, r12d
0x1800e816a  add     r12d, r8d
0x1800e816d  mov     qword ptr [rbp+rax*8+0E0h+var_70], rcx
0x1800e8172  xor     ecx, ecx
0x1800e8174  add     rdx, r8
0x1800e8177  cmp     rdx, 6
0x1800e817b  jnz     short loc_1800E814C
0x1800e817d  mov     r14d, cs:g_CiPolicyState
0x1800e8184  shr     r14d, 8
0x1800e8188  test    cs:g_CiPolicyState, 200h
0x1800e8192  jz      short loc_1800E81B8
0x1800e8194  cmp     [rsp+1E0h+var_19C], 3
0x1800e8199  jnz     short loc_1800E81B8
0x1800e819b  lea     rcx, [rsp+1E0h+var_19F]
0x1800e81a0  call    CipIsDeveloperModeEnabled
0x1800e81a5  xor     ecx, ecx
0x1800e81a7  lea     r8d, [rcx+1]
0x1800e81ab  test    eax, eax
0x1800e81ad  js      short loc_1800E81B8
0x1800e81af  mov     dil, r8b
0x1800e81b2  cmp     [rsp+1E0h+var_19F], cl
0x1800e81b6  jnz     short loc_1800E81BB
0x1800e81b8  mov     dil, cl
0x1800e81bb  mov     rax, [rbp+0E0h+var_158]
0x1800e81bf  test    rax, rax
0x1800e81c2  jz      short loc_1800E81F2
0x1800e81c4  and     r14b, r8b
0x1800e81c7  jnz     short loc_1800E81CE
0x1800e81c9  test    dil, dil
0x1800e81cc  jz      short loc_1800E820C
0x1800e81ce  lea     rdx, [rsp+1E0h+var_190]
0x1800e81d3  mov     rcx, rax
0x1800e81d6  call    CipQueryDynamicCodeTrustClaim
0x1800e81db  test    eax, eax
0x1800e81dd  js      short loc_1800E81EC
0x1800e81df  mov     [rsp+1E0h+var_19D], r14b
0x1800e81e4  mov     r15b, dil
0x1800e81e7  test    dil, dil
0x1800e81ea  jnz     short loc_1800E820C
0x1800e81ec  mov     r8d, 1
0x1800e81f2  test    dil, dil
0x1800e81f5  jz      short loc_1800E820C
0x1800e81f7  mov     rax, [rbp+0E0h+var_160]
0x1800e81fb  test    rax, rax
0x1800e81fe  jz      short loc_1800E820C
0x1800e8200  cmp     byte ptr [rax+34h], 3
0x1800e8204  movzx   r15d, r15b
0x1800e8208  cmovz   r15d, r8d
0x1800e820c  lea     rax, [rsi+350h]
0x1800e8213  xor     edx, edx; Val
0x1800e8215  lea     rcx, [rsi+9B0h]; void *
0x1800e821c  mov     [rbp+0E0h+var_110], rax
0x1800e8220  mov     r8d, 80h; Size
0x1800e8226  lea     r14, [rsi+9A8h]
0x1800e822d  call    memset
0x1800e8232  mov     rcx, [rbp+0E0h+var_160]
0x1800e8236  xor     r8d, r8d
0x1800e8239  mov     rax, [rsp+1E0h+var_198]
0x1800e823e  mov     [r14], rax
0x1800e8241  test    rcx, rcx
0x1800e8244  jz      short loc_1800E824B
0x1800e8246  mov     al, [rcx+54h]
0x1800e8249  jmp     short loc_1800E8251
0x1800e824b  mov     al, [rsi+0BCCh]
0x1800e8251  movzx   eax, al
0x1800e8254  mov     [r14+10h], eax
0x1800e8258  lea     rax, [rcx+58h]
0x1800e825c  test    rcx, rcx
0x1800e825f  jnz     short loc_1800E8268
0x1800e8261  mov     rax, [rsi+0BD0h]
0x1800e8268  mov     [r14+8], rax
0x1800e826c  lea     rdx, [rsi+2E8h]
0x1800e8273  mov     rcx, r8
0x1800e8276  mov     rax, rcx
0x1800e8279  shl     rax, 4
0x1800e827d  add     rax, rdx
0x1800e8280  mov     [r14+rcx*8+18h], rax
0x1800e8285  inc     rcx
  ... truncated ...
```
