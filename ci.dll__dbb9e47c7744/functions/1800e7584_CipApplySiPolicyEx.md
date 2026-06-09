# CipApplySiPolicyEx

- ea: `0x1800e7584`
- end: `0x1800e82c2`
- name: `CipApplySiPolicyEx`
- size: `3390`
- prototype: ``
- caller_count: `3`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180074f04`
- `0x1800e6d64`
- `0x1800e8b74`

## callees

- `0x18000cf38`
- `0x180011bfc`
- `0x18002bf20`
- `0x18002c380`
- `0x1800592f0`
- `0x18005cc64`
- `0x18005d450`
- `0x180073624`
- `0x1800748f4`
- `0x1800755f0`
- `0x180078f64`
- `0x180079034`
- `0x1800957f8`
- `0x1800a16f0`
- `0x1800a2014`
- `0x1800a2818`
- `0x1800a7144`
- `0x1800afcc8`
- `0x1800d8390`
- `0x1800e1ed4`
- `0x1800e2424`
- `0x1800e2be0`
- `0x1800e7584`
- `0x1800e9268`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800e774e`
- `ntoskrnl!ExAllocatePool2` at `0x1800e7826`
- `ntoskrnl!ExAllocatePool2` at `0x1800e7b99`
- `ntoskrnl!ExAllocatePool2` at `0x1800e826b`
- `ntoskrnl!ExAllocatePool2` at `0x1800e774e`
- `ntoskrnl!ExAllocatePool2` at `0x1800e7826`
- `ntoskrnl!ExAllocatePool2` at `0x1800e7b99`
- `ntoskrnl!ExAllocatePool2` at `0x1800e826b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e7be3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e7bfc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e7be3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e7bfc`
- `ntoskrnl!ZwClose` at `0x1800e7c11`
- `ntoskrnl!ZwClose` at `0x1800e7c11`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1800e78b6`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1800e78b6`
- `ntoskrnl!RtlQueryPackageClaims` at `0x1800e77a0`
- `ntoskrnl!RtlQueryPackageClaims` at `0x1800e77a0`
- `ntoskrnl!RtlCapabilityCheck` at `0x1800e78d5`
- `ntoskrnl!RtlCapabilityCheck` at `0x1800e78d5`
- `HAL!KeQueryPerformanceCounter` at `0x1800e7660`
- `HAL!KeQueryPerformanceCounter` at `0x1800e7c1f`
- `HAL!KeQueryPerformanceCounter` at `0x1800e7660`
- `HAL!KeQueryPerformanceCounter` at `0x1800e7c1f`

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
  unsigned __int64 v37; // rcx
  char v38; // al
  char v39; // al
  char v40; // cl
  char v41; // cl
  __int64 v42; // rax
  __int64 v43; // rdi
  __int64 v45; // rcx
  __int64 v46; // r13
  unsigned int v47; // r14d
  unsigned int v48; // r9d
  __int64 v49; // r10
  __int64 v50; // r11
  _BYTE *v51; // r12
  unsigned __int64 v52; // rdx
  _OWORD *v53; // r14
  _QWORD *v54; // rbx
  unsigned int v55; // edx
  __int64 v56; // r9
  unsigned int v57; // edi
  __int64 v58; // r8
  __int64 v59; // rax
  __int64 v60; // rdi
  unsigned __int64 v61; // rcx
  int v62; // eax
  __int64 v63; // rdx
  int v64; // r13d
  __int64 v65; // r14
  __int64 v66; // rbx
  __int64 v67; // rax
  int v68; // ecx
  __int64 v69; // rcx
  int v70; // eax
  int v71; // eax
  char v72; // r14
  int v73; // ebx
  _OWORD *v74; // rdi
  __int64 v75; // rdx
  unsigned __int64 v76; // rcx
  int v77; // ecx
  __int64 v78; // r12
  __int64 v79; // rdi
  char v80; // [rsp+40h] [rbp-C0h] BYREF
  char v81; // [rsp+41h] [rbp-BFh] BYREF
  char v82; // [rsp+42h] [rbp-BEh]
  char v83; // [rsp+43h] [rbp-BDh]
  char v84; // [rsp+44h] [rbp-BCh]
  _OWORD *v85; // [rsp+48h] [rbp-B8h]
  __int64 v86; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v87; // [rsp+58h] [rbp-A8h]
  ULONG pulResult[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v89; // [rsp+68h] [rbp-98h] BYREF
  __int64 v90; // [rsp+70h] [rbp-90h]
  __int64 v91; // [rsp+78h] [rbp-88h] BYREF
  __int64 v92; // [rsp+80h] [rbp-80h]
  __int64 v93; // [rsp+88h] [rbp-78h]
  __int64 v94; // [rsp+90h] [rbp-70h] BYREF
  __int64 v95; // [rsp+98h] [rbp-68h] BYREF
  __int64 v96; // [rsp+A0h] [rbp-60h]
  PVOID P; // [rsp+A8h] [rbp-58h]
  HANDLE Handle; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v99; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v100; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v101; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v102; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v103[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v104; // [rsp+F0h] [rbp-10h]
  LARGE_INTEGER v105; // [rsp+F8h] [rbp-8h]
  _OWORD v106[3]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v107; // [rsp+130h] [rbp+30h]
  _OWORD v108[3]; // [rsp+138h] [rbp+38h] BYREF

  v93 = a5;
  v92 = a4;
  v107 = 0;
  v84 = a2;
  *((_QWORD *)&v99 + 1) = qword_1800335B0;
  v101 = 0;
  v103[1] = L"runFullTrust";
  v10 = 0;
  memset(v106, 0, sizeof(v106));
  *(_QWORD *)&v99 = 0x20000;
  v11 = 0;
  v90 = 0;
  v96 = 0;
  memset(v108, 0, sizeof(v108));
  pulResult[0] = 0;
  v102 = 0;
  v100 = 0;
  v103[0] = 1703960;
  v80 = 0;
  Handle = 0;
  P = 0;
  v91 = 0;
  v86 = 0;
  v81 = 0;
  v95 = 0;
  v94 = 0;
  v89 = 4;
  PerformanceCounter = KeQueryPerformanceCounter(0);
  *(_DWORD *)(a1 + 2360) |= 1u;
  v13 = PerformanceCounter;
  v105 = PerformanceCounter;
  if ( (*(_BYTE *)(*(_QWORD *)(a1 + 2440) + 32LL) & 2) != 0 )
    memset(*(void **)(a1 + 2344), 0, 4LL * (unsigned int)g_NumberOfSiPolicies);
  if ( *(_DWORD *)(a1 + 2336) == 2 )
    goto LABEL_67;
  v14 = 0;
  v87 = *(_DWORD *)(*(_QWORD *)(a1 + 2440) + 36LL);
  if ( a4 && (v14 = *(_QWORD *)(a4 + 16)) != 0 )
  {
    v15 = SIPolicyConvertChainInfo(v14, v106);
    v14 = 0;
    v10 = v15;
    if ( v15 < 0 )
      goto LABEL_67;
    v16 = v106;
  }
  else
  {
    v16 = a6;
  }
  v85 = v16;
  v17 = v14;
  v82 = v14;
  if ( *(_QWORD *)(a1 + 3040) == v14 )
    goto LABEL_35;
  if ( (unsigned __int8)(a2 - 5) <= 1u || (*((_DWORD *)g_CipWhichLevelComparisons + (a2 & 0xF)) & 4) != 0 || a2 == 8 )
  {
    v91 = 256;
    Pool2 = (_WORD *)ExAllocatePool2(256, 256, 1668499779);
    P = Pool2;
    if ( !Pool2 )
    {
LABEL_14:
      v10 = -1073741801;
      goto LABEL_67;
    }
    *Pool2 = 0;
    v10 = RtlQueryPackageClaims(*(_QWORD *)(a1 + 3040), Pool2, &v91, 0, 0, 0, &v100, 0);
    if ( (int)(v10 + 0x80000000) >= 0 && v10 != -1073741275 )
      goto LABEL_67;
    v14 = 0;
    if ( *(_QWORD *)(a1 + 832) )
    {
      v99 = *(_OWORD *)(a1 + 824);
    }
    else if ( v91 )
    {
      v19 = P;
      if ( *(_WORD *)P )
      {
        v11 = (void *)ExAllocatePool2(258, 130, 1919109443);
        if ( !v11 )
          goto LABEL_14;
        InfoFromFullName = CipPackageGetInfoFromFullName(v19, (unsigned int)(v91 - 2), v11);
        v14 = 0;
        v10 = InfoFromFullName;
        if ( InfoFromFullName < 0 )
          goto LABEL_67;
        *(_OWORD *)(a1 + 824) = v99;
        goto LABEL_20;
      }
    }
    if ( v10 >= 0 )
    {
LABEL_20:
      if ( BYTE4(v100) == 2 )
      {
        v82 = 1;
      }
      else if ( BYTE4(v100) == 3 && (unsigned __int8)(a3 - 5) <= 1u )
      {
        v21 = ObOpenObjectByPointer(*(PVOID *)(a1 + 3040), 0x200u, 0, 8u, 0, 0, &Handle);
        v14 = 0;
        if ( v21 >= 0 )
        {
          v22 = RtlCapabilityCheck(Handle, v103, &v80);
          v14 = 0;
          if ( v22 >= 0 && !v80 )
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
  v83 = v14;
  v24 = v14;
  for ( i = v14; i != 6; ++i )
  {
    if ( *(_QWORD *)(16 * i + a1 + 872) != v14 )
    {
      v26 = v23++;
      *((_QWORD *)v108 + v26) = 16 * i + a1 + 864;
      v14 = 0;
    }
  }
  v27 = (unsigned int)g_CiPolicyState >> 8;
  if ( (g_CiPolicyState & 0x200) == 0
    || v84 != 3
    || (IsDeveloperModeEnabled = CipIsDeveloperModeEnabled(&v81), LOBYTE(v14) = 0, IsDeveloperModeEnabled < 0)
    || (v29 = 1, !v81) )
  {
    v29 = v14;
  }
  if ( !v93
    || ((v30 = v27 & 1) != 0 || v29)
    && ((int)CipQueryDynamicCodeTrustClaim(v93, &v86, 1) < 0 || (v83 = v30, (v24 = v29) == 0)) )
  {
    if ( v29 && v92 && *(_BYTE *)(v92 + 52) == 3 )
      v24 = 1;
  }
  v101 = a1 + 848;
  memset((void *)(a1 + 2472), 0, 0x80u);
  v31 = v92;
  *(_QWORD *)(a1 + 2464) = v85;
  if ( v31 )
    v32 = *(_BYTE *)(v31 + 84);
  else
    v32 = *(_BYTE *)(a1 + 3012);
  *(_DWORD *)(a1 + 2480) = v32;
  v33 = v31 + 88;
  if ( !v31 )
    v33 = *(_QWORD *)(a1 + 3016);
  *(_QWORD *)(a1 + 2472) = v33;
  v34 = a1 + 744;
  for ( j = 0; j != 4; ++j )
    *(_QWORD *)(a1 + 2464 + 8 * j + 24) = v34 + 16 * j;
  *(_QWORD *)(a1 + 2520) = *(_QWORD *)(a1 + 840);
  *(_QWORD *)(a1 + 2528) = &v99;
  *(_QWORD *)(a1 + 2536) = v90;
  *(_DWORD *)(a1 + 2560) = *(_QWORD *)(a1 + 856) != 0;
  v36 = *(_QWORD *)(a1 + 856);
  *(_DWORD *)(a1 + 2576) = v23;
  *(_QWORD *)(a1 + 2544) = 0;
  v37 = (unsigned __int64)&v101 & -(__int64)(v36 != 0);
  *(_QWORD *)(a1 + 2552) = v37;
  *(_QWORD *)(a1 + 2568) = v108;
  *(_OWORD *)(a1 + 2616) = 0;
  *(_OWORD *)(a1 + 2632) = 0;
  *(_OWORD *)(a1 + 2648) = 0;
  *(_QWORD *)(a1 + 2664) = 0;
  LOBYTE(v37) = *(_BYTE *)(a1 + 2620) & 0xFE;
  *(_DWORD *)(a1 + 2616) = *(_DWORD *)(a1 + 2336);
  LOBYTE(v37) = (2 * v82) | (v17 | v37) & 0xFD;
  *(_BYTE *)(a1 + 2620) = v37;
  if ( (*(_DWORD *)(a1 + 2360) & 0x100000) != 0 )
  {
    LOBYTE(v37) = v37 | 0x10;
    *(_BYTE *)(a1 + 2620) = v37;
    *(_DWORD *)(a1 + 2580) = *(_DWORD *)(a1 + 2364);
  }
  else
  {
    *(_DWORD *)(a1 + 2580) = *(_DWORD *)(a1 + 3028);
    *(_DWORD *)(a1 + 2584) = *(_DWORD *)(a1 + 3024);
  }
  v38 = v83;
  *(_OWORD *)(a1 + 2600) = 0;
  *(_BYTE *)(a1 + 2609) = v38;
  *(_BYTE *)(a1 + 2608) = v84;
  *(_BYTE *)(a1 + 2610) = v24;
  *(_QWORD *)(a1 + 2600) = a1;
  Feature_Servicing_WdacAppidTaggingPerfImprovements_44681456__private_IsEnabledPreCheck(v37, v34, 0);
  v39 = *(_BYTE *)(a1 + 2620) & 0xF7;
  v40 = ~(unsigned __int8)(*(_DWORD *)a1 >> 1);
  *(_QWORD *)(a1 + 2624) = a1 + 2600;
  v41 = v39 | v40 & 8;
  *(_QWORD *)(a1 + 2632) = CipExternalAuthorizationCallback;
  v42 = v87;
  *(_BYTE *)(a1 + 2620) = v41;
  v10 = RtlULongLongToULong(24 * v42, pulResult);
  if ( v10 < 0 )
    goto LABEL_66;
  v43 = ExAllocatePool2(256, pulResult[0], 1769163075);
  v96 = v43;
  if ( !v43 )
  {
    v10 = -1073741801;
LABEL_66:
    v11 = 0;
    goto LABEL_67;
  }
  v45 = *(_QWORD *)(a1 + 2440);
  v93 = 0;
  LODWORD(v90) = -1;
  v10 = 0;
  v46 = 0;
  SIPolicyObjectValidationEngine(v45, a1 + 2616, a1 + 2464, v43);
  v47 = v87;
  v48 = 0;
  if ( v87 )
  {
    v49 = 0x48F222A00D2EB091LL;
    v50 = SiPolicyIDEndpointSec;
    while ( 1 )
    {
      v51 = (_BYTE *)(v43 + 24LL * v48);
      v52 = -(__int64)(*(_DWORD *)(*(_QWORD *)v51 + 40LL) < 6u) & 0xFFFFFFFFFFFFFD40uLL;
      if ( *(_QWORD *)(v52 + *(_QWORD *)v51 + 720) == v50
        && *(_QWORD *)(v52 + *(_QWORD *)v51 + 728) == v49
        && (unsigned __int8)SIPolicyIsBasePolicy() )
      {
        break;
      }
      if ( ++v48 >= v47 )
      {
        v51 = 0;
        goto LABEL_81;
      }
    }
    v51[8] = (int)SIPolicyAggregatePolicyValidationResult(v51, v43, v47, &v102) >= 0;
    v50 = SiPolicyIDEndpointSec;
LABEL_81:
    LODWORD(v86) = 0;
    v53 = 0;
    v85 = 0;
    while ( 1 )
    {
      v54 = g_SiPolicyHandles;
      v55 = 0;
      v56 = *((_QWORD *)g_SiPolicyHandles + (_QWORD)v53);
      do
      {
        v57 = v55;
        v58 = *(_QWORD *)(v96 + 24LL * v55);
        if ( v58 == v56 )
          break;
        ++v55;
      }
      while ( v55 < v87 );
      v59 = v57 + 1;
      if ( v58 == v56 )
        v59 = v57;
      v60 = v96 + 24 * v59;
      v104 = v60;
      v61 = -(__int64)(*(_DWORD *)(*(_QWORD *)v60 + 40LL) < 6u) & 0xFFFFFFFFFFFFFD40uLL;
      if ( *(_QWORD *)(v61 + *(_QWORD *)v60 + 720) == v50
        && *(_QWORD *)(v61 + *(_QWORD *)v60 + 728) == 0x48F222A00D2EB091LL )
      {
        *(_DWORD *)(*(_QWORD *)(a1 + 2344) + 4LL * (_QWORD)v53) = 0;
        *(_QWORD *)(*(_QWORD *)(a1 + 2352) + 8LL * (_QWORD)v53) = *(_QWORD *)v60;
        *(_DWORD *)(a1 + 2360) |= 2u;
LABEL_90:
        v62 = v86;
        goto LABEL_91;
      }
      pulResult[0] = SIPolicyAggregatePolicyValidationResult(v60, v96, v87, 0);
      v64 = pulResult[0];
      if ( (pulResult[0] & 0x80000000) != 0 && v51 && v51[8] )
      {
        v65 = *(_QWORD *)v60;
        if ( !(unsigned __int8)SIPolicyIsSystemPolicy(
                                 *(_QWORD *)v60
                               + (-(__int64)(*(_DWORD *)(*(_QWORD *)v60 + 40LL) < 6u) & 0xFFFFFFFFFFFFFD50uLL)
                               + 704,
                                 v63,
                                 0)
          && ((*(_DWORD *)(v65 + 672) & 8) == 0 || (*(_DWORD *)(v65 + 44) & 0x10000) != 0) )
        {
          *(_DWORD *)(v60 + 20) |= 0x10000000u;
          v64 = 0;
          pulResult[0] = 0;
          *(_WORD *)(v60 + 8) = 1;
          *(_DWORD *)(v60 + 12) = 0;
          v93 = v65;
        }
        v53 = v85;
      }
      if ( v64 < 0 )
      {
        SIPolicyProcessDbgSettingAndReprieve(
          *(_QWORD *)(a1 + 2440),
          v54[(_QWORD)v53],
          a1 + 808,
          *(_DWORD *)(a1 + 2336),
          1,
          (__int64)pulResult,
          0,
          0);
        v64 = pulResult[0];
        if ( (pulResult[0] & 0x80000000) == 0 )
          *(_DWORD *)(v60 + 20) |= 0x800000u;
      }
      v67 = *(_QWORD *)(a1 + 2344);
      *(_QWORD *)pulResult = *(_QWORD *)v60;
      v66 = *(_QWORD *)pulResult;
      *(_DWORD *)(v67 + 4LL * (_QWORD)v53) = v64;
      *(_QWORD *)(*(_QWORD *)(a1 + 2352) + 8LL * (_QWORD)v53) = v66;
      *(_DWORD *)(a1 + 2360) |= 2u;
      if ( v64 >= 0 )
      {
        v68 = *(_DWORD *)(*(_QWORD *)(a1 + 2296) + 4LL * (_QWORD)v53);
        if ( v68 < 0 )
        {
          *(_BYTE *)(v60 + 9) = 1;
          v64 = v68;
          *(_DWORD *)(v60 + 16) = *(_DWORD *)(*(_QWORD *)(a1 + 2304) + 4LL * (_QWORD)v53);
          *(_DWORD *)(v60 + 20) = *(_DWORD *)(*(_QWORD *)(a1 + 2312) + 4LL * (_QWORD)v53);
        }
      }
      else if ( *(_BYTE *)(v60 + 9) )
      {
        *(_DWORD *)(*(_QWORD *)(a1 + 2296) + 4LL * (_QWORD)v53) = v64;
        *(_DWORD *)(*(_QWORD *)(a1 + 2304) + 4LL * (_QWORD)v53) = *(_DWORD *)(v60 + 16);
        *(_DWORD *)(*(_QWORD *)(a1 + 2312) + 4LL * (_QWORD)v53) = *(_DWORD *)(v60 + 20);
      }
      v69 = *(_QWORD *)(a1 + 984);
      if ( v69 )
      {
        v70 = *(_DWORD *)(v66 + 44);
        if ( (v70 & 0x10) != 0 || (v70 & 0x8000000) != 0 )
        {
          if ( (*(_DWORD *)(a1 + 2360) & 0x400) != 0 )
          {
            v71 = *(_DWORD *)(a1 + 2116);
            LODWORD(v90) = v71;
          }
          else
          {
            v71 = v90;
          }
          CiLogSIPolicySmartlockerEvent((const wchar_t *)(v69 + 88), v86, *(_DWORD *)(v60 + 16), v71, v64);
        }
      }
      if ( *(_DWORD *)(a1 + 2336) == 1 && (*(_DWORD *)(*((_QWORD *)g_SiPolicyHandles + (_QWORD)v53) + 672LL) & 8) != 0 )
      {
        if ( (*(_DWORD *)a1 & 0x10) == 0 )
        {
          if ( v64 >= 0 )
            goto LABEL_151;
          v72 = 0;
          if ( (unsigned __int8)SIPolicyAppIdTaggingEnforceDLL() )
          {
LABEL_125:
            v73 = 0;
            if ( (int)SIPolicyEnumerateOneSecurityPolicyKey(
                        *((_QWORD *)g_SiPolicyHandles + (_QWORD)v85),
                        (unsigned int)&qword_180030960,
                        (unsigned int)&qword_1800309A0,
                        0,
                        (__int64)&v95,
                        (__int64)&v89,
                        (__int64)&v94) >= 0 )
            {
              v74 = v85;
              do
              {
                if ( v89 == 3 && v72 )
                  CiAddAppIdTaggingClaimsToOriginClaim(a1 + 992, v95, v94);
                ++v73;
              }
              while ( (int)SIPolicyEnumerateOneSecurityPolicyKey(
                             *((_QWORD *)g_SiPolicyHandles + (_QWORD)v74),
                             (unsigned int)&qword_180030960,
                             (unsigned int)&qword_1800309A0,
                             v73,
                             (__int64)&v95,
                             (__int64)&v89,
                             (__int64)&v94) >= 0 );
              v60 = v104;
            }
            v66 = *(_QWORD *)pulResult;
          }
          v53 = v85;
          goto LABEL_134;
        }
        if ( v64 < 0 )
          goto LABEL_135;
        if ( (*(_DWORD *)(v60 + 20) & 0x800000) == 0 )
        {
          v72 = 1;
          goto LABEL_125;
        }
      }
LABEL_134:
      if ( v64 >= 0 )
        goto LABEL_151;
LABEL_135:
      if ( !(unsigned __int8)SIPolicyVerifiedAndReputableAllowUnknown(v66, v63, 0) )
        *(_DWORD *)(a1 + 2360) &= ~1u;
      if ( (*(_DWORD *)(v66 + 44) & 0x10000) == 0 )
      {
        v75 = v92;
        goto LABEL_146;
      }
      if ( *(_BYTE *)(v60 + 9) )
        *(_DWORD *)(a1 + 28) = 26;
      v75 = v92;
      if ( v92 && *(_DWORD *)(v92 + 60) != 26 )
        *(_DWORD *)(v92 + 60) = *(_BYTE *)(v60 + 9) != 0 ? 26 : 21;
      if ( (*(_DWORD *)(a1 + 2360) & 0x40) != 0 )
      {
        *(_BYTE *)(v60 + 9) = 0;
LABEL_146:
        if ( v10 >= 0 )
        {
          v10 = v64;
          *(_DWORD *)(a1 + 968) = v86;
          *(_DWORD *)(a1 + 2084) = *(_DWORD *)(v60 + 16);
          *(_DWORD *)(a1 + 2088) = *(_DWORD *)(v60 + 20);
        }
        if ( *(_BYTE *)(v60 + 9) )
        {
          *(_DWORD *)(a1 + 24) = 26;
          if ( v75 )
            *(_DWORD *)(v75 + 56) = 26;
        }
      }
LABEL_151:
      if ( (g_CiPolicyState & 0x4000) == 0 )
        goto LABEL_90;
      v76 = -(__int64)(*(_DWORD *)(v66 + 40) < 6u) & 0xFFFFFFFFFFFFFD50uLL;
      if ( *(_OWORD *)(v76 + v66 + 704) != SiPolicyIDNightsWatchDesktop
        && *(_OWORD *)(v76 + v66 + 704) != SiPolicyIDNightsWatchDesktopEval )
      {
        goto LABEL_90;
      }
      *(_DWORD *)(a1 + 2072) = *(_DWORD *)(v60 + 16);
      *(_DWORD *)(a1 + 2076) = *(_DWORD *)(v60 + 20);
      v77 = *(_DWORD *)(*(_QWORD *)(a1 + 2344) + 4LL * (_QWORD)v53);
      v62 = v86;
      *(_DWORD *)(a1 + 2100) = v86;
      *(_DWORD *)(a1 + 2096) = v77;
LABEL_91:
      v53 = (_OWORD *)((char *)v53 + 1);
      LODWORD(v86) = v62 + 1;
      v85 = v53;
      if ( v62 + 1 >= v87 )
      {
        v13 = v105;
        v46 = v93;
        break;
      }
      v50 = SiPolicyIDEndpointSec;
    }
  }
  v78 = *(_QWORD *)(a1 + 984);
  *(_QWORD *)(a1 + 2448) = v102;
  *(_QWORD *)(a1 + 2456) = v46;
  if ( v78 && (*(_DWORD *)(a1 + 992) || *(_QWORD *)(a1 + 1520)) )
  {
    v79 = ExAllocatePool2(256, 568, 1668499779);
    if ( !v79 )
      goto LABEL_66;
    *(_QWORD *)(v79 + 560) = v78;
    if ( (int)CipDuplicateCodeIntegrityOriginClaimMembers(a1 + 992, v79) < 0 )
      CipDeleteOriginEntryCallback(v79 + 536, 0);
    else
      CipInsertOriginEntryIntoTable(v79);
    v11 = 0;
  }
  else
  {
    v11 = 0;
  }
LABEL_67:
  SIPolicyFreeSIChainInfo(v106);
  SIPolicyFree(v96);
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
0x1800e7584  mov     [rsp-8+arg_8], rbx
0x1800e7589  push    rbp
0x1800e758a  push    rsi
0x1800e758b  push    rdi
0x1800e758c  push    r12
0x1800e758e  push    r13
0x1800e7590  push    r14
0x1800e7592  push    r15
0x1800e7594  lea     rbp, [rsp-70h]
0x1800e7599  sub     rsp, 170h
0x1800e75a0  mov     rax, cs:__security_cookie
0x1800e75a7  xor     rax, rsp
0x1800e75aa  mov     [rbp+0A0h+var_38], rax
0x1800e75ae  mov     rax, [rbp+0A0h+arg_20]
0x1800e75b5  xorps   xmm0, xmm0
0x1800e75b8  mov     [rbp+0A0h+var_118], rax
0x1800e75bc  mov     rsi, rcx
0x1800e75bf  xor     ecx, ecx; PerformanceFrequency
0x1800e75c1  movzx   r12d, dl
0x1800e75c5  xor     eax, eax
0x1800e75c7  mov     [rbp+0A0h+var_120], r9
0x1800e75cb  mov     [rbp+0A0h+var_70], rax
0x1800e75cf  mov     r13, r9
0x1800e75d2  lea     rax, qword_1800335B0
0x1800e75d9  mov     [rsp+1A0h+var_15C], r12b
0x1800e75de  mov     qword ptr [rbp+0A0h+var_E8+8], rax
0x1800e75e2  mov     r14b, r8b
0x1800e75e5  lea     rax, aRunfulltrust; "runFullTrust"
0x1800e75ec  mov     [rbp+0A0h+var_D0], rcx
0x1800e75f0  mov     [rbp+0A0h+var_B8], rax
0x1800e75f4  mov     r15d, ecx
0x1800e75f7  movups  [rbp+0A0h+var_A0], xmm0
0x1800e75fb  mov     qword ptr [rbp+0A0h+var_E8], 20000h
0x1800e7603  mov     edi, ecx
0x1800e7605  movups  [rbp+0A0h+var_90], xmm0
0x1800e7609  mov     [rsp+1A0h+var_130], rcx
0x1800e760e  movups  [rbp+0A0h+var_80], xmm0
0x1800e7612  mov     [rbp+0A0h+var_100], rcx
0x1800e7616  movups  [rbp+0A0h+var_68], xmm0
0x1800e761a  mov     [rsp+1A0h+pulResult], ecx
0x1800e761e  movups  [rbp+0A0h+var_58], xmm0
0x1800e7622  mov     [rbp+0A0h+var_C8], rcx
0x1800e7626  movups  [rbp+0A0h+var_48], xmm0
0x1800e762a  mov     [rbp+0A0h+var_D8], rcx
0x1800e762e  mov     [rbp+0A0h+var_C0], 1A0018h
0x1800e7636  mov     [rsp+1A0h+var_160], cl
0x1800e763a  mov     [rbp+0A0h+var_F0], rcx
0x1800e763e  mov     [rbp+0A0h+P], rcx
0x1800e7642  mov     [rsp+1A0h+var_128], rcx
0x1800e7647  mov     [rsp+1A0h+var_150], rcx
0x1800e764c  mov     [rsp+1A0h+var_15F], cl
0x1800e7650  mov     [rbp+0A0h+var_108], rcx
0x1800e7654  mov     [rbp+0A0h+var_110], rcx
0x1800e7658  mov     [rsp+1A0h+var_138], 4
0x1800e7660  call    cs:__imp_KeQueryPerformanceCounter
0x1800e7667  nop     dword ptr [rax+rax+00h]
0x1800e766c  or      dword ptr [rsi+938h], 1
0x1800e7673  mov     rbx, rax
0x1800e7676  mov     [rbp+0A0h+var_A8], rax
0x1800e767a  mov     rax, [rsi+988h]
0x1800e7681  test    byte ptr [rax+20h], 2
0x1800e7685  jz      short loc_1800E76A0
0x1800e7687  mov     r8d, cs:g_NumberOfSiPolicies
0x1800e768e  xor     edx, edx; Val
0x1800e7690  mov     rcx, [rsi+928h]; void *
0x1800e7697  shl     r8, 2; Size
0x1800e769b  call    memset
0x1800e76a0  cmp     dword ptr [rsi+920h], 2
0x1800e76a7  jz      loc_1800E7BC0
0x1800e76ad  mov     rax, [rsi+988h]
0x1800e76b4  xor     ecx, ecx
0x1800e76b6  mov     eax, [rax+24h]
0x1800e76b9  mov     [rsp+1A0h+var_148], eax
0x1800e76bd  test    r13, r13
0x1800e76c0  jz      short loc_1800E76E7
0x1800e76c2  mov     rcx, [r13+10h]
0x1800e76c6  test    rcx, rcx
0x1800e76c9  jz      short loc_1800E76E7
0x1800e76cb  lea     rdx, [rbp+0A0h+var_A0]
0x1800e76cf  call    SIPolicyConvertChainInfo
0x1800e76d4  xor     ecx, ecx
0x1800e76d6  mov     r15d, eax
0x1800e76d9  test    eax, eax
0x1800e76db  js      loc_1800E7BC0
0x1800e76e1  lea     rax, [rbp+0A0h+var_A0]
0x1800e76e5  jmp     short loc_1800E76EE
0x1800e76e7  mov     rax, [rbp+0A0h+arg_28]
0x1800e76ee  mov     r9d, 100h
0x1800e76f4  mov     [rsp+1A0h+var_158], rax
0x1800e76f9  mov     r8d, 1
0x1800e76ff  movzx   r13d, cl
0x1800e7703  mov     [rsp+1A0h+var_15E], cl
0x1800e7707  cmp     [rsi+0BE0h], rcx
0x1800e770e  jz      loc_1800E78FF
0x1800e7714  lea     eax, [r12-5]
0x1800e7719  cmp     al, r8b
0x1800e771c  jbe     short loc_1800E773D
0x1800e771e  mov     rax, cs:g_CipWhichLevelComparisons
0x1800e7725  mov     rcx, r12
0x1800e7728  and     ecx, 0Fh
0x1800e772b  mov     ecx, [rax+rcx*4]
0x1800e772e  test    cl, 4
0x1800e7731  jnz     short loc_1800E773D
0x1800e7733  cmp     r12b, 8
0x1800e7737  jnz     loc_1800E78F5
0x1800e773d  mov     r8d, 63734943h
0x1800e7743  mov     [rsp+1A0h+var_128], r9
0x1800e7748  mov     rdx, r9
0x1800e774b  mov     rcx, r9
0x1800e774e  call    cs:__imp_ExAllocatePool2
0x1800e7755  nop     dword ptr [rax+rax+00h]
0x1800e775a  xor     edx, edx
0x1800e775c  mov     [rbp+0A0h+P], rax
0x1800e7760  mov     rcx, rax
0x1800e7763  test    rax, rax
0x1800e7766  jnz     short loc_1800E7773
0x1800e7768  mov     r15d, 0C0000017h
0x1800e776e  jmp     loc_1800E7BC0
0x1800e7773  mov     [rsp+1A0h+var_168], rdx
0x1800e7778  lea     r8, [rsp+1A0h+var_128]
0x1800e777d  mov     [rax], dx
0x1800e7780  xor     r9d, r9d
0x1800e7783  lea     rax, [rbp+0A0h+var_D8]
0x1800e7787  mov     [rsp+1A0h+Handle], rax
0x1800e778c  mov     qword ptr [rsp+1A0h+AccessMode], rdx
0x1800e7791  mov     [rsp+1A0h+ObjectType], rdx
0x1800e7796  mov     rdx, rcx
0x1800e7799  mov     rcx, [rsi+0BE0h]
0x1800e77a0  call    cs:__imp_RtlQueryPackageClaims
0x1800e77a7  nop     dword ptr [rax+rax+00h]
0x1800e77ac  mov     ecx, 80000000h
0x1800e77b1  mov     r15d, eax
0x1800e77b4  add     eax, ecx
0x1800e77b6  test    ecx, eax
0x1800e77b8  jnz     short loc_1800E77C7
0x1800e77ba  cmp     r15d, 0C0000225h
0x1800e77c1  jnz     loc_1800E7BC0
0x1800e77c7  xor     ecx, ecx
0x1800e77c9  cmp     [rsi+340h], rcx
0x1800e77d0  jz      short loc_1800E7804
0x1800e77d2  movups  xmm0, xmmword ptr [rsi+338h]
0x1800e77d9  movdqu  [rbp+0A0h+var_E8], xmm0
0x1800e77de  test    r15d, r15d
0x1800e77e1  js      loc_1800E78F9
0x1800e77e7  movzx   eax, byte ptr [rbp+0A0h+var_D8+4]
0x1800e77eb  mov     r8d, 1
0x1800e77f1  cmp     eax, 2
0x1800e77f4  jnz     loc_1800E7881
0x1800e77fa  mov     [rsp+1A0h+var_15E], r8b
0x1800e77ff  jmp     loc_1800E78FF
0x1800e7804  cmp     [rsp+1A0h+var_128], rcx
0x1800e7809  jbe     short loc_1800E77DE
0x1800e780b  mov     r12, [rbp+0A0h+P]
0x1800e780f  cmp     [r12], cx
0x1800e7814  jz      short loc_1800E77DE
0x1800e7816  mov     edx, 82h
0x1800e781b  mov     ecx, 102h
0x1800e7820  mov     r8d, 72634943h
0x1800e7826  call    cs:__imp_ExAllocatePool2
0x1800e782d  nop     dword ptr [rax+rax+00h]
0x1800e7832  mov     rdi, rax
0x1800e7835  test    rax, rax
0x1800e7838  jz      loc_1800E7768
0x1800e783e  mov     edx, dword ptr [rsp+1A0h+var_128]
0x1800e7842  lea     rax, [rbp+0A0h+var_E8]
0x1800e7846  mov     qword ptr [rsp+1A0h+AccessMode], rax
0x1800e784b  add     edx, 0FFFFFFFEh
0x1800e784e  lea     rax, [rsp+1A0h+var_130]
0x1800e7853  mov     r8, rdi
0x1800e7856  mov     rcx, r12
0x1800e7859  mov     [rsp+1A0h+ObjectType], rax
0x1800e785e  call    CipPackageGetInfoFromFullName
0x1800e7863  xor     ecx, ecx
0x1800e7865  mov     r15d, eax
0x1800e7868  test    eax, eax
0x1800e786a  js      loc_1800E7BC0
0x1800e7870  movups  xmm0, [rbp+0A0h+var_E8]
0x1800e7874  movdqu  xmmword ptr [rsi+338h], xmm0
0x1800e787c  jmp     loc_1800E77E7
0x1800e7881  cmp     eax, 3
0x1800e7884  jnz     short loc_1800E78FF
0x1800e7886  sub     r14b, 5
0x1800e788a  cmp     r14b, r8b
0x1800e788d  ja      short loc_1800E78FF
0x1800e788f  lea     rax, [rbp+0A0h+var_F0]
0x1800e7893  mov     r9d, 8; DesiredAccess
0x1800e7899  mov     [rsp+1A0h+Handle], rax; Handle
0x1800e789e  xor     r8d, r8d; PassedAccessState
0x1800e78a1  mov     [rsp+1A0h+AccessMode], cl; AccessMode
0x1800e78a5  mov     edx, 200h; HandleAttributes
0x1800e78aa  mov     [rsp+1A0h+ObjectType], rcx; ObjectType
0x1800e78af  mov     rcx, [rsi+0BE0h]; Object
0x1800e78b6  call    cs:__imp_ObOpenObjectByPointer
0x1800e78bd  nop     dword ptr [rax+rax+00h]
0x1800e78c2  xor     ecx, ecx
0x1800e78c4  test    eax, eax
0x1800e78c6  js      short loc_1800E78F9
0x1800e78c8  mov     rcx, [rbp+0A0h+var_F0]
0x1800e78cc  lea     r8, [rsp+1A0h+var_160]
0x1800e78d1  lea     rdx, [rbp+0A0h+var_C0]
0x1800e78d5  call    cs:__imp_RtlCapabilityCheck
0x1800e78dc  nop     dword ptr [rax+rax+00h]
0x1800e78e1  xor     ecx, ecx
0x1800e78e3  lea     r8d, [rcx+1]
0x1800e78e7  test    eax, eax
0x1800e78e9  js      short loc_1800E78FF
0x1800e78eb  cmp     [rsp+1A0h+var_160], cl
0x1800e78ef  cmovz   r13d, r8d
0x1800e78f3  jmp     short loc_1800E78FF
0x1800e78f5  xor     ecx, ecx
0x1800e78f7  jmp     short loc_1800E78FF
0x1800e78f9  mov     r8d, 1
0x1800e78ff  mov     r12d, ecx
0x1800e7902  mov     [rsp+1A0h+var_15D], cl
0x1800e7906  mov     r15b, cl
0x1800e7909  mov     rdx, rcx
0x1800e790c  mov     rax, rdx
0x1800e790f  shl     rax, 4
0x1800e7913  cmp     [rax+rsi+368h], rcx
0x1800e791b  jz      short loc_1800E7934
0x1800e791d  lea     rcx, [rsi+360h]
0x1800e7924  add     rcx, rax
0x1800e7927  mov     eax, r12d
0x1800e792a  add     r12d, r8d
0x1800e792d  mov     qword ptr [rbp+rax*8+0A0h+var_68], rcx
0x1800e7932  xor     ecx, ecx
0x1800e7934  add     rdx, r8
0x1800e7937  cmp     rdx, 6
0x1800e793b  jnz     short loc_1800E790C
0x1800e793d  mov     r14d, cs:g_CiPolicyState
0x1800e7944  shr     r14d, 8
0x1800e7948  test    cs:g_CiPolicyState, 200h
0x1800e7952  jz      short loc_1800E7978
0x1800e7954  cmp     [rsp+1A0h+var_15C], 3
0x1800e7959  jnz     short loc_1800E7978
0x1800e795b  lea     rcx, [rsp+1A0h+var_15F]
0x1800e7960  call    CipIsDeveloperModeEnabled
0x1800e7965  xor     ecx, ecx
0x1800e7967  lea     r8d, [rcx+1]
0x1800e796b  test    eax, eax
0x1800e796d  js      short loc_1800E7978
0x1800e796f  mov     dil, r8b
0x1800e7972  cmp     [rsp+1A0h+var_15F], cl
0x1800e7976  jnz     short loc_1800E797B
0x1800e7978  mov     dil, cl
0x1800e797b  mov     rax, [rbp+0A0h+var_118]
0x1800e797f  test    rax, rax
0x1800e7982  jz      short loc_1800E79B2
0x1800e7984  and     r14b, r8b
0x1800e7987  jnz     short loc_1800E798E
0x1800e7989  test    dil, dil
0x1800e798c  jz      short loc_1800E79CC
0x1800e798e  lea     rdx, [rsp+1A0h+var_150]
0x1800e7993  mov     rcx, rax
0x1800e7996  call    CipQueryDynamicCodeTrustClaim
0x1800e799b  test    eax, eax
0x1800e799d  js      short loc_1800E79AC
0x1800e799f  mov     [rsp+1A0h+var_15D], r14b
0x1800e79a4  mov     r15b, dil
0x1800e79a7  test    dil, dil
0x1800e79aa  jnz     short loc_1800E79CC
0x1800e79ac  mov     r8d, 1
0x1800e79b2  test    dil, dil
0x1800e79b5  jz      short loc_1800E79CC
0x1800e79b7  mov     rax, [rbp+0A0h+var_120]
0x1800e79bb  test    rax, rax
0x1800e79be  jz      short loc_1800E79CC
0x1800e79c0  cmp     byte ptr [rax+34h], 3
0x1800e79c4  movzx   r15d, r15b
0x1800e79c8  cmovz   r15d, r8d
0x1800e79cc  lea     rax, [rsi+350h]
0x1800e79d3  xor     edx, edx; Val
0x1800e79d5  lea     rcx, [rsi+9A8h]; void *
0x1800e79dc  mov     [rbp+0A0h+var_D0], rax
0x1800e79e0  mov     r8d, 80h; Size
0x1800e79e6  lea     r14, [rsi+9A0h]
0x1800e79ed  call    memset
0x1800e79f2  mov     rcx, [rbp+0A0h+var_120]
0x1800e79f6  xor     r8d, r8d
0x1800e79f9  mov     rax, [rsp+1A0h+var_158]
0x1800e79fe  mov     [r14], rax
0x1800e7a01  test    rcx, rcx
0x1800e7a04  jz      short loc_1800E7A0B
0x1800e7a06  mov     al, [rcx+54h]
0x1800e7a09  jmp     short loc_1800E7A11
0x1800e7a0b  mov     al, [rsi+0BC4h]
0x1800e7a11  movzx   eax, al
0x1800e7a14  mov     [r14+10h], eax
0x1800e7a18  lea     rax, [rcx+58h]
0x1800e7a1c  test    rcx, rcx
0x1800e7a1f  jnz     short loc_1800E7A28
0x1800e7a21  mov     rax, [rsi+0BC8h]
0x1800e7a28  mov     [r14+8], rax
0x1800e7a2c  lea     rdx, [rsi+2E8h]
0x1800e7a33  mov     rcx, r8
0x1800e7a36  mov     rax, rcx
0x1800e7a39  shl     rax, 4
0x1800e7a3d  add     rax, rdx
0x1800e7a40  mov     [r14+rcx*8+18h], rax
0x1800e7a45  inc     rcx
  ... truncated ...
```
