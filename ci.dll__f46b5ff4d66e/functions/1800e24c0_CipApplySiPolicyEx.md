# CipApplySiPolicyEx

- ea: `0x1800e24c0`
- end: `0x1800e31fe`
- name: `CipApplySiPolicyEx`
- size: `3390`
- prototype: ``
- caller_count: `3`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180073c54`
- `0x1800e2208`
- `0x1800e75c8`

## callees

- `0x18000cf38`
- `0x180011d14`
- `0x18002bef0`
- `0x18002c340`
- `0x1800585d8`
- `0x18005c5fc`
- `0x18005cde8`
- `0x180072374`
- `0x180073644`
- `0x180074024`
- `0x1800779b4`
- `0x180077a84`
- `0x1800941c8`
- `0x1800a00c0`
- `0x1800a09e4`
- `0x1800a11e8`
- `0x1800a5b14`
- `0x1800ae848`
- `0x1800d7460`
- `0x1800e0ee4`
- `0x1800e1434`
- `0x1800e1bf0`
- `0x1800e24c0`
- `0x1800e7cbc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800e268a`
- `ntoskrnl!ExAllocatePool2` at `0x1800e2762`
- `ntoskrnl!ExAllocatePool2` at `0x1800e2ad5`
- `ntoskrnl!ExAllocatePool2` at `0x1800e31a7`
- `ntoskrnl!ExAllocatePool2` at `0x1800e268a`
- `ntoskrnl!ExAllocatePool2` at `0x1800e2762`
- `ntoskrnl!ExAllocatePool2` at `0x1800e2ad5`
- `ntoskrnl!ExAllocatePool2` at `0x1800e31a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e2b1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e2b38`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e2b1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e2b38`
- `ntoskrnl!ZwClose` at `0x1800e2b4d`
- `ntoskrnl!ZwClose` at `0x1800e2b4d`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1800e27f2`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1800e27f2`
- `ntoskrnl!RtlQueryPackageClaims` at `0x1800e26dc`
- `ntoskrnl!RtlQueryPackageClaims` at `0x1800e26dc`
- `ntoskrnl!RtlCapabilityCheck` at `0x1800e2811`
- `ntoskrnl!RtlCapabilityCheck` at `0x1800e2811`
- `HAL!KeQueryPerformanceCounter` at `0x1800e259c`
- `HAL!KeQueryPerformanceCounter` at `0x1800e2b5b`
- `HAL!KeQueryPerformanceCounter` at `0x1800e259c`
- `HAL!KeQueryPerformanceCounter` at `0x1800e2b5b`

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
  *((_QWORD *)&v99 + 1) = qword_180033520;
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
                        (unsigned int)&qword_1800308C0,
                        (unsigned int)&qword_180030900,
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
                             (unsigned int)&qword_1800308C0,
                             (unsigned int)&qword_180030900,
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
0x1800e24c0  mov     [rsp-8+arg_8], rbx
0x1800e24c5  push    rbp
0x1800e24c6  push    rsi
0x1800e24c7  push    rdi
0x1800e24c8  push    r12
0x1800e24ca  push    r13
0x1800e24cc  push    r14
0x1800e24ce  push    r15
0x1800e24d0  lea     rbp, [rsp-70h]
0x1800e24d5  sub     rsp, 170h
0x1800e24dc  mov     rax, cs:__security_cookie
0x1800e24e3  xor     rax, rsp
0x1800e24e6  mov     [rbp+0A0h+var_38], rax
0x1800e24ea  mov     rax, [rbp+0A0h+arg_20]
0x1800e24f1  xorps   xmm0, xmm0
0x1800e24f4  mov     [rbp+0A0h+var_118], rax
0x1800e24f8  mov     rsi, rcx
0x1800e24fb  xor     ecx, ecx; PerformanceFrequency
0x1800e24fd  movzx   r12d, dl
0x1800e2501  xor     eax, eax
0x1800e2503  mov     [rbp+0A0h+var_120], r9
0x1800e2507  mov     [rbp+0A0h+var_70], rax
0x1800e250b  mov     r13, r9
0x1800e250e  lea     rax, qword_180033520
0x1800e2515  mov     [rsp+1A0h+var_15C], r12b
0x1800e251a  mov     qword ptr [rbp+0A0h+var_E8+8], rax
0x1800e251e  mov     r14b, r8b
0x1800e2521  lea     rax, aRunfulltrust; "runFullTrust"
0x1800e2528  mov     [rbp+0A0h+var_D0], rcx
0x1800e252c  mov     [rbp+0A0h+var_B8], rax
0x1800e2530  mov     r15d, ecx
0x1800e2533  movups  [rbp+0A0h+var_A0], xmm0
0x1800e2537  mov     qword ptr [rbp+0A0h+var_E8], 20000h
0x1800e253f  mov     edi, ecx
0x1800e2541  movups  [rbp+0A0h+var_90], xmm0
0x1800e2545  mov     [rsp+1A0h+var_130], rcx
0x1800e254a  movups  [rbp+0A0h+var_80], xmm0
0x1800e254e  mov     [rbp+0A0h+var_100], rcx
0x1800e2552  movups  [rbp+0A0h+var_68], xmm0
0x1800e2556  mov     [rsp+1A0h+pulResult], ecx
0x1800e255a  movups  [rbp+0A0h+var_58], xmm0
0x1800e255e  mov     [rbp+0A0h+var_C8], rcx
0x1800e2562  movups  [rbp+0A0h+var_48], xmm0
0x1800e2566  mov     [rbp+0A0h+var_D8], rcx
0x1800e256a  mov     [rbp+0A0h+var_C0], 1A0018h
0x1800e2572  mov     [rsp+1A0h+var_160], cl
0x1800e2576  mov     [rbp+0A0h+var_F0], rcx
0x1800e257a  mov     [rbp+0A0h+P], rcx
0x1800e257e  mov     [rsp+1A0h+var_128], rcx
0x1800e2583  mov     [rsp+1A0h+var_150], rcx
0x1800e2588  mov     [rsp+1A0h+var_15F], cl
0x1800e258c  mov     [rbp+0A0h+var_108], rcx
0x1800e2590  mov     [rbp+0A0h+var_110], rcx
0x1800e2594  mov     [rsp+1A0h+var_138], 4
0x1800e259c  call    cs:__imp_KeQueryPerformanceCounter
0x1800e25a3  nop     dword ptr [rax+rax+00h]
0x1800e25a8  or      dword ptr [rsi+938h], 1
0x1800e25af  mov     rbx, rax
0x1800e25b2  mov     [rbp+0A0h+var_A8], rax
0x1800e25b6  mov     rax, [rsi+988h]
0x1800e25bd  test    byte ptr [rax+20h], 2
0x1800e25c1  jz      short loc_1800E25DC
0x1800e25c3  mov     r8d, cs:g_NumberOfSiPolicies
0x1800e25ca  xor     edx, edx; Val
0x1800e25cc  mov     rcx, [rsi+928h]; void *
0x1800e25d3  shl     r8, 2; Size
0x1800e25d7  call    memset
0x1800e25dc  cmp     dword ptr [rsi+920h], 2
0x1800e25e3  jz      loc_1800E2AFC
0x1800e25e9  mov     rax, [rsi+988h]
0x1800e25f0  xor     ecx, ecx
0x1800e25f2  mov     eax, [rax+24h]
0x1800e25f5  mov     [rsp+1A0h+var_148], eax
0x1800e25f9  test    r13, r13
0x1800e25fc  jz      short loc_1800E2623
0x1800e25fe  mov     rcx, [r13+10h]
0x1800e2602  test    rcx, rcx
0x1800e2605  jz      short loc_1800E2623
0x1800e2607  lea     rdx, [rbp+0A0h+var_A0]
0x1800e260b  call    SIPolicyConvertChainInfo
0x1800e2610  xor     ecx, ecx
0x1800e2612  mov     r15d, eax
0x1800e2615  test    eax, eax
0x1800e2617  js      loc_1800E2AFC
0x1800e261d  lea     rax, [rbp+0A0h+var_A0]
0x1800e2621  jmp     short loc_1800E262A
0x1800e2623  mov     rax, [rbp+0A0h+arg_28]
0x1800e262a  mov     r9d, 100h
0x1800e2630  mov     [rsp+1A0h+var_158], rax
0x1800e2635  mov     r8d, 1
0x1800e263b  movzx   r13d, cl
0x1800e263f  mov     [rsp+1A0h+var_15E], cl
0x1800e2643  cmp     [rsi+0BE0h], rcx
0x1800e264a  jz      loc_1800E283B
0x1800e2650  lea     eax, [r12-5]
0x1800e2655  cmp     al, r8b
0x1800e2658  jbe     short loc_1800E2679
0x1800e265a  mov     rax, cs:g_CipWhichLevelComparisons
0x1800e2661  mov     rcx, r12
0x1800e2664  and     ecx, 0Fh
0x1800e2667  mov     ecx, [rax+rcx*4]
0x1800e266a  test    cl, 4
0x1800e266d  jnz     short loc_1800E2679
0x1800e266f  cmp     r12b, 8
0x1800e2673  jnz     loc_1800E2831
0x1800e2679  mov     r8d, 63734943h
0x1800e267f  mov     [rsp+1A0h+var_128], r9
0x1800e2684  mov     rdx, r9
0x1800e2687  mov     rcx, r9
0x1800e268a  call    cs:__imp_ExAllocatePool2
0x1800e2691  nop     dword ptr [rax+rax+00h]
0x1800e2696  xor     edx, edx
0x1800e2698  mov     [rbp+0A0h+P], rax
0x1800e269c  mov     rcx, rax
0x1800e269f  test    rax, rax
0x1800e26a2  jnz     short loc_1800E26AF
0x1800e26a4  mov     r15d, 0C0000017h
0x1800e26aa  jmp     loc_1800E2AFC
0x1800e26af  mov     [rsp+1A0h+var_168], rdx
0x1800e26b4  lea     r8, [rsp+1A0h+var_128]
0x1800e26b9  mov     [rax], dx
0x1800e26bc  xor     r9d, r9d
0x1800e26bf  lea     rax, [rbp+0A0h+var_D8]
0x1800e26c3  mov     [rsp+1A0h+Handle], rax
0x1800e26c8  mov     qword ptr [rsp+1A0h+AccessMode], rdx
0x1800e26cd  mov     [rsp+1A0h+ObjectType], rdx
0x1800e26d2  mov     rdx, rcx
0x1800e26d5  mov     rcx, [rsi+0BE0h]
0x1800e26dc  call    cs:__imp_RtlQueryPackageClaims
0x1800e26e3  nop     dword ptr [rax+rax+00h]
0x1800e26e8  mov     ecx, 80000000h
0x1800e26ed  mov     r15d, eax
0x1800e26f0  add     eax, ecx
0x1800e26f2  test    ecx, eax
0x1800e26f4  jnz     short loc_1800E2703
0x1800e26f6  cmp     r15d, 0C0000225h
0x1800e26fd  jnz     loc_1800E2AFC
0x1800e2703  xor     ecx, ecx
0x1800e2705  cmp     [rsi+340h], rcx
0x1800e270c  jz      short loc_1800E2740
0x1800e270e  movups  xmm0, xmmword ptr [rsi+338h]
0x1800e2715  movdqu  [rbp+0A0h+var_E8], xmm0
0x1800e271a  test    r15d, r15d
0x1800e271d  js      loc_1800E2835
0x1800e2723  movzx   eax, byte ptr [rbp+0A0h+var_D8+4]
0x1800e2727  mov     r8d, 1
0x1800e272d  cmp     eax, 2
0x1800e2730  jnz     loc_1800E27BD
0x1800e2736  mov     [rsp+1A0h+var_15E], r8b
0x1800e273b  jmp     loc_1800E283B
0x1800e2740  cmp     [rsp+1A0h+var_128], rcx
0x1800e2745  jbe     short loc_1800E271A
0x1800e2747  mov     r12, [rbp+0A0h+P]
0x1800e274b  cmp     [r12], cx
0x1800e2750  jz      short loc_1800E271A
0x1800e2752  mov     edx, 82h
0x1800e2757  mov     ecx, 102h
0x1800e275c  mov     r8d, 72634943h
0x1800e2762  call    cs:__imp_ExAllocatePool2
0x1800e2769  nop     dword ptr [rax+rax+00h]
0x1800e276e  mov     rdi, rax
0x1800e2771  test    rax, rax
0x1800e2774  jz      loc_1800E26A4
0x1800e277a  mov     edx, dword ptr [rsp+1A0h+var_128]
0x1800e277e  lea     rax, [rbp+0A0h+var_E8]
0x1800e2782  mov     qword ptr [rsp+1A0h+AccessMode], rax
0x1800e2787  add     edx, 0FFFFFFFEh
0x1800e278a  lea     rax, [rsp+1A0h+var_130]
0x1800e278f  mov     r8, rdi
0x1800e2792  mov     rcx, r12
0x1800e2795  mov     [rsp+1A0h+ObjectType], rax
0x1800e279a  call    CipPackageGetInfoFromFullName
0x1800e279f  xor     ecx, ecx
0x1800e27a1  mov     r15d, eax
0x1800e27a4  test    eax, eax
0x1800e27a6  js      loc_1800E2AFC
0x1800e27ac  movups  xmm0, [rbp+0A0h+var_E8]
0x1800e27b0  movdqu  xmmword ptr [rsi+338h], xmm0
0x1800e27b8  jmp     loc_1800E2723
0x1800e27bd  cmp     eax, 3
0x1800e27c0  jnz     short loc_1800E283B
0x1800e27c2  sub     r14b, 5
0x1800e27c6  cmp     r14b, r8b
0x1800e27c9  ja      short loc_1800E283B
0x1800e27cb  lea     rax, [rbp+0A0h+var_F0]
0x1800e27cf  mov     r9d, 8; DesiredAccess
0x1800e27d5  mov     [rsp+1A0h+Handle], rax; Handle
0x1800e27da  xor     r8d, r8d; PassedAccessState
0x1800e27dd  mov     [rsp+1A0h+AccessMode], cl; AccessMode
0x1800e27e1  mov     edx, 200h; HandleAttributes
0x1800e27e6  mov     [rsp+1A0h+ObjectType], rcx; ObjectType
0x1800e27eb  mov     rcx, [rsi+0BE0h]; Object
0x1800e27f2  call    cs:__imp_ObOpenObjectByPointer
0x1800e27f9  nop     dword ptr [rax+rax+00h]
0x1800e27fe  xor     ecx, ecx
0x1800e2800  test    eax, eax
0x1800e2802  js      short loc_1800E2835
0x1800e2804  mov     rcx, [rbp+0A0h+var_F0]
0x1800e2808  lea     r8, [rsp+1A0h+var_160]
0x1800e280d  lea     rdx, [rbp+0A0h+var_C0]
0x1800e2811  call    cs:__imp_RtlCapabilityCheck
0x1800e2818  nop     dword ptr [rax+rax+00h]
0x1800e281d  xor     ecx, ecx
0x1800e281f  lea     r8d, [rcx+1]
0x1800e2823  test    eax, eax
0x1800e2825  js      short loc_1800E283B
0x1800e2827  cmp     [rsp+1A0h+var_160], cl
0x1800e282b  cmovz   r13d, r8d
0x1800e282f  jmp     short loc_1800E283B
0x1800e2831  xor     ecx, ecx
0x1800e2833  jmp     short loc_1800E283B
0x1800e2835  mov     r8d, 1
0x1800e283b  mov     r12d, ecx
0x1800e283e  mov     [rsp+1A0h+var_15D], cl
0x1800e2842  mov     r15b, cl
0x1800e2845  mov     rdx, rcx
0x1800e2848  mov     rax, rdx
0x1800e284b  shl     rax, 4
0x1800e284f  cmp     [rax+rsi+368h], rcx
0x1800e2857  jz      short loc_1800E2870
0x1800e2859  lea     rcx, [rsi+360h]
0x1800e2860  add     rcx, rax
0x1800e2863  mov     eax, r12d
0x1800e2866  add     r12d, r8d
0x1800e2869  mov     qword ptr [rbp+rax*8+0A0h+var_68], rcx
0x1800e286e  xor     ecx, ecx
0x1800e2870  add     rdx, r8
0x1800e2873  cmp     rdx, 6
0x1800e2877  jnz     short loc_1800E2848
0x1800e2879  mov     r14d, cs:g_CiPolicyState
0x1800e2880  shr     r14d, 8
0x1800e2884  test    cs:g_CiPolicyState, 200h
0x1800e288e  jz      short loc_1800E28B4
0x1800e2890  cmp     [rsp+1A0h+var_15C], 3
0x1800e2895  jnz     short loc_1800E28B4
0x1800e2897  lea     rcx, [rsp+1A0h+var_15F]
0x1800e289c  call    CipIsDeveloperModeEnabled
0x1800e28a1  xor     ecx, ecx
0x1800e28a3  lea     r8d, [rcx+1]
0x1800e28a7  test    eax, eax
0x1800e28a9  js      short loc_1800E28B4
0x1800e28ab  mov     dil, r8b
0x1800e28ae  cmp     [rsp+1A0h+var_15F], cl
0x1800e28b2  jnz     short loc_1800E28B7
0x1800e28b4  mov     dil, cl
0x1800e28b7  mov     rax, [rbp+0A0h+var_118]
0x1800e28bb  test    rax, rax
0x1800e28be  jz      short loc_1800E28EE
0x1800e28c0  and     r14b, r8b
0x1800e28c3  jnz     short loc_1800E28CA
0x1800e28c5  test    dil, dil
0x1800e28c8  jz      short loc_1800E2908
0x1800e28ca  lea     rdx, [rsp+1A0h+var_150]
0x1800e28cf  mov     rcx, rax
0x1800e28d2  call    CipQueryDynamicCodeTrustClaim
0x1800e28d7  test    eax, eax
0x1800e28d9  js      short loc_1800E28E8
0x1800e28db  mov     [rsp+1A0h+var_15D], r14b
0x1800e28e0  mov     r15b, dil
0x1800e28e3  test    dil, dil
0x1800e28e6  jnz     short loc_1800E2908
0x1800e28e8  mov     r8d, 1
0x1800e28ee  test    dil, dil
0x1800e28f1  jz      short loc_1800E2908
0x1800e28f3  mov     rax, [rbp+0A0h+var_120]
0x1800e28f7  test    rax, rax
0x1800e28fa  jz      short loc_1800E2908
0x1800e28fc  cmp     byte ptr [rax+34h], 3
0x1800e2900  movzx   r15d, r15b
0x1800e2904  cmovz   r15d, r8d
0x1800e2908  lea     rax, [rsi+350h]
0x1800e290f  xor     edx, edx; Val
0x1800e2911  lea     rcx, [rsi+9A8h]; void *
0x1800e2918  mov     [rbp+0A0h+var_D0], rax
0x1800e291c  mov     r8d, 80h; Size
0x1800e2922  lea     r14, [rsi+9A0h]
0x1800e2929  call    memset
0x1800e292e  mov     rcx, [rbp+0A0h+var_120]
0x1800e2932  xor     r8d, r8d
0x1800e2935  mov     rax, [rsp+1A0h+var_158]
0x1800e293a  mov     [r14], rax
0x1800e293d  test    rcx, rcx
0x1800e2940  jz      short loc_1800E2947
0x1800e2942  mov     al, [rcx+54h]
0x1800e2945  jmp     short loc_1800E294D
0x1800e2947  mov     al, [rsi+0BC4h]
0x1800e294d  movzx   eax, al
0x1800e2950  mov     [r14+10h], eax
0x1800e2954  lea     rax, [rcx+58h]
0x1800e2958  test    rcx, rcx
0x1800e295b  jnz     short loc_1800E2964
0x1800e295d  mov     rax, [rsi+0BC8h]
0x1800e2964  mov     [r14+8], rax
0x1800e2968  lea     rdx, [rsi+2E8h]
0x1800e296f  mov     rcx, r8
0x1800e2972  mov     rax, rcx
0x1800e2975  shl     rax, 4
0x1800e2979  add     rax, rdx
0x1800e297c  mov     [r14+rcx*8+18h], rax
0x1800e2981  inc     rcx
  ... truncated ...
```
