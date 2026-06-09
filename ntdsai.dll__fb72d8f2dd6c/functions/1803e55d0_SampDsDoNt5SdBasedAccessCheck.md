# SampDsDoNt5SdBasedAccessCheck

- ea: `0x1803e55d0`
- end: `0x1803e63c0`
- name: `SampDsDoNt5SdBasedAccessCheck`
- size: `3568`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x18001ea60`
- `0x180021aa3`
- `0x180030af8`
- `0x180030b60`
- `0x180048e28`
- `0x1803af8f0`
- `0x1803e00d0`
- `0x1803e55d0`
- `0x1803e6990`
- `0x1803e6d20`
- `0x1803e6dc4`
- `0x18042addc`
- `0x180453340`
- `0x18047b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803e613b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803e613b`
- `ntdll!RtlClearAllBits` at `0x1803e5771`
- `ntdll!RtlClearAllBits` at `0x1803e612d`
- `ntdll!RtlClearAllBits` at `0x1803e624e`
- `ntdll!RtlClearAllBits` at `0x1803e5771`
- `ntdll!RtlClearAllBits` at `0x1803e612d`
- `ntdll!RtlClearAllBits` at `0x1803e624e`
- `ntdll!NtAccessCheckByTypeResultList` at `0x1803e5bd3`
- `ntdll!NtAccessCheckByTypeResultList` at `0x1803e5bd3`
- `ntdll!NtAccessCheckByTypeResultListAndAuditAlarm` at `0x1803e5c67`
- `ntdll!NtAccessCheckByTypeResultListAndAuditAlarm` at `0x1803e5c67`
- `ntdll!RtlFreeHeap` at `0x1803e6378`
- `ntdll!RtlFreeHeap` at `0x1803e6378`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1803e57ac`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1803e57ac`
- `ntdll!RtlMapGenericMask` at `0x1803e60dd`
- `ntdll!RtlMapGenericMask` at `0x1803e60dd`
- `SAMSRV!SampImpersonateClient` at `0x1803e5b3d`
- `SAMSRV!SampImpersonateClient` at `0x1803e5b3d`
- `SAMSRV!SampGetSamSubsystemName` at `0x1803e5bef`
- `SAMSRV!SampGetSamSubsystemName` at `0x1803e5bef`
- `SAMSRV!SampRevertToSelf` at `0x1803e5c72`
- `SAMSRV!SampRevertToSelf` at `0x1803e5c72`
- `SAMSRV!SampSetAttributeAccess` at `0x1803e5f64`
- `SAMSRV!SampSetAttributeAccess` at `0x1803e5f64`
- `SAMSRV!SampSetExtendedAttributeAccess` at `0x1803e5f8f`
- `SAMSRV!SampSetExtendedAttributeAccess` at `0x1803e5f8f`

## pseudocode

```c
__int64 __fastcall SampDsDoNt5SdBasedAccessCheck(
        _QWORD *a1,
        void *a2,
        void *ObjectSid,
        unsigned int a4,
        struct _UNICODE_STRING *a5,
        DWORD AccessMask,
        BOOLEAN a7,
        struct _GENERIC_MAPPING *a8,
        HANDLE ClientToken,
        int *a10,
        struct _RTL_BITMAP *a11,
        int *a12)
{
  HANDLE v12; // r12
  __int64 v17; // rdx
  __int64 v18; // rcx
  int v19; // edi
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // r8
  __int64 v23; // r9
  BOOL v24; // ebx
  int v25; // eax
  struct _RTL_BITMAP *v26; // rcx
  __int64 v27; // rcx
  _WORD *v28; // rdx
  __int16 v29; // ax
  NTSTATUS v30; // ebx
  ULONG *v31; // rsi
  struct _REVERSE_MAPPING_TABLE_ENTRY *v33; // r14
  ULONG v34; // esi
  unsigned int near **v35; // rbx
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // r8
  __int64 v41; // r9
  BOOL v42; // ebx
  int v43; // eax
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 v50; // rbx
  __int64 v51; // r14
  size_t v52; // rbx
  __int64 v53; // rcx
  unsigned __int64 v54; // rcx
  void *v55; // rsp
  void *v56; // rsp
  ULONG *v57; // rax
  DWORD v58; // esi
  ACCESS_MASK v59; // esi
  ULONG v60; // r14d
  NTSTATUS v61; // eax
  __int64 v62; // rdx
  __int64 v63; // rcx
  _QWORD *v64; // r12
  NTSTATUS v65; // ebx
  unsigned __int8 *GenerateOnClose; // rbx
  struct _UNICODE_STRING *SamSubsystemName; // rax
  __int64 v68; // rax
  __int64 v69; // r14
  __int64 v70; // r15
  bool v71; // zf
  int v72; // r12d
  DWORD v73; // ebx
  __int64 v74; // rdx
  __int64 v75; // rcx
  __int64 v76; // r8
  __int64 v77; // r9
  __int64 v78; // r8
  __int64 v79; // r9
  BOOL v80; // esi
  int v81; // eax
  int v82; // esi
  __int64 v83; // rdx
  __int64 v84; // rcx
  __int64 v85; // r8
  __int64 v86; // r9
  __int64 v87; // r15
  int v88; // r14d
  _DWORD *v89; // rax
  int v90; // r15d
  int v91; // r12d
  int v92; // r13d
  __int64 v93; // r8
  __int64 v94; // r9
  BOOL v95; // ebx
  int v96; // edx
  int v97; // r8d
  int v98; // r9d
  int v99; // eax
  __int64 v100; // r9
  __int64 v101; // r8
  __int64 v102; // r8
  __int64 v103; // r9
  int v104; // esi
  int *v105; // rax
  int v106; // r14d
  int v107; // r15d
  int v108; // r12d
  int v109; // r13d
  __int64 v110; // r8
  __int64 v111; // r9
  BOOL v112; // ebx
  int v113; // r8d
  int v114; // r9d
  int v115; // eax
  __int64 v116; // rcx
  __int64 v117; // rdx
  __int64 v118; // rcx
  int *v119; // r15
  int *v120; // r14
  struct _RTL_BITMAP *v121; // rcx
  DWORD LastError; // esi
  __int64 v123; // rdx
  __int64 v124; // rcx
  __int64 v125; // r8
  __int64 v126; // r9
  __int64 v127; // r8
  __int64 v128; // r9
  BOOL v129; // ebx
  int v130; // eax
  __int64 v131; // rdx
  __int64 v132; // rcx
  __int64 v133; // r8
  __int64 v134; // r9
  DWORD v135; // esi
  int v136; // r14d
  int v137; // r15d
  __int64 v138; // r8
  __int64 v139; // r9
  BOOL v140; // ebx
  int v141; // r8d
  __int64 v142; // rcx
  __int64 v143; // [rsp+0h] [rbp-80h] BYREF
  PGENERIC_MAPPING GenericMapping; // [rsp+30h] [rbp-50h]
  PPRIVILEGE_SET PrivilegeSet; // [rsp+38h] [rbp-48h]
  PULONG PrivilegeSetLength; // [rsp+40h] [rbp-40h]
  PACCESS_MASK GrantedAccess; // [rsp+48h] [rbp-38h]
  PNTSTATUS AccessStatus; // [rsp+50h] [rbp-30h]
  PGENERIC_MAPPING v149; // [rsp+58h] [rbp-28h]
  BOOLEAN ObjectCreation[4]; // [rsp+60h] [rbp-20h]
  PACCESS_MASK GrantedAccessList; // [rsp+68h] [rbp-18h]
  int v152; // [rsp+80h] [rbp+0h] BYREF
  ULONG ObjectTypeListLength; // [rsp+84h] [rbp+4h]
  ULONG v154; // [rsp+88h] [rbp+8h] BYREF
  unsigned int v155; // [rsp+8Ch] [rbp+Ch]
  int ClassAttribute; // [rsp+90h] [rbp+10h]
  void *Src; // [rsp+98h] [rbp+18h]
  ULONG *v158; // [rsp+A0h] [rbp+20h]
  unsigned int near **v159; // [rsp+A8h] [rbp+28h]
  unsigned int v160; // [rsp+B0h] [rbp+30h] BYREF
  unsigned int v161; // [rsp+B4h] [rbp+34h]
  struct _REVERSE_MAPPING_TABLE_ENTRY *v162; // [rsp+B8h] [rbp+38h]
  PVOID HandleId; // [rsp+C0h] [rbp+40h]
  PRTL_BITMAP BitMapHeader; // [rsp+C8h] [rbp+48h]
  int *v165; // [rsp+D0h] [rbp+50h]
  PUNICODE_STRING ObjectTypeName; // [rsp+D8h] [rbp+58h]
  DWORD v167; // [rsp+E0h] [rbp+60h]
  int *v168; // [rsp+E8h] [rbp+68h]
  struct _UNICODE_STRING UnicodeString; // [rsp+F0h] [rbp+70h] BYREF
  __int64 v170; // [rsp+100h] [rbp+80h]
  __int64 v171; // [rsp+108h] [rbp+88h]
  PGENERIC_MAPPING v172; // [rsp+110h] [rbp+90h]
  __int128 v173; // [rsp+118h] [rbp+98h] BYREF
  DWORD v174[256]; // [rsp+130h] [rbp+B0h] BYREF
  int AccessStatusList[256]; // [rsp+530h] [rbp+4B0h] BYREF
  struct _PRIVILEGE_SET v176; // [rsp+930h] [rbp+8B0h] BYREF

  v12 = ClientToken;
  ObjectTypeName = a5;
  v172 = a8;
  v165 = a10;
  BitMapHeader = a11;
  v168 = a12;
  v161 = a4;
  v167 = AccessMask & 0x2000000;
  HandleId = a1;
  v173 = 0;
  v154 = 16;
  UnicodeString = 0;
  v160 = 0;
  v19 = 1;
  if ( (unsigned int)THStateCheckForTraceOverride(a1, a2)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v18, v17)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v18, v17, v20, v21)
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
  {
    v24 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v18, v17)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier(v18, v17, v22, v23)
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
    if ( (unsigned int)THStateCheckForTraceOverride(v18, v17)
      || (v25 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
    {
      v25 = 1;
    }
    WPP_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      522258342,
      4,
      13,
      v25,
      v24,
      13,
      &WPP_7c853a87250733c99b1f132b1f9c171b_Traceguids);
  }
  v26 = BitMapHeader;
  *v165 = 0;
  RtlClearAllBits(v26);
  v28 = (_WORD *)a1[22];
  if ( *((_DWORD *)v28 + 13) )
  {
    v29 = v28[26];
    BYTE1(v152) = 0;
    UnicodeString.MaximumLength = 2 * v29;
    UnicodeString.Length = 2 * v29;
    UnicodeString.Buffer = v28 + 28;
    goto LABEL_21;
  }
  v30 = RtlConvertSidToUnicodeString(&UnicodeString, v28 + 12, 1u);
  if ( v30 >= 0 )
  {
    BYTE1(v152) = 1;
LABEL_21:
    if ( !ObjectSid )
    {
      if ( !a4 )
        goto LABEL_37;
      ObjectSid = (void *)SampDsGetObjectSid(a1[22]);
      if ( !ObjectSid )
      {
        v31 = 0;
LABEL_25:
        v30 = -1073741670;
LABEL_186:
        if ( BYTE1(v152) )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, UnicodeString.Buffer);
        if ( v31 )
        {
          if ( *(v31 - 2) == 1885431112 )
            ((void (*)(void))g_pfnFree)();
        }
        return (unsigned int)v30;
      }
    }
    v27 = a4;
    if ( a4 )
    {
      v27 = a4 - 1;
      if ( a4 == 1 )
      {
        v33 = DomainReverseMappingTable;
        Src = &DomainObjectTypeList;
        v34 = 19;
        v35 = &DomainAttributeConversionMappingTable;
      }
      else
      {
        v27 = a4 - 2;
        if ( a4 == 2 )
        {
          v33 = GroupReverseMappingTable;
          Src = &GroupObjectTypeList;
          v34 = 6;
          v35 = &GroupAttributeConversionMappingTable;
        }
        else
        {
          v27 = a4 - 3;
          if ( a4 == 3 )
          {
            v33 = AliasReverseMappingTable;
            Src = &AliasObjectTypeList;
            v34 = 6;
            v35 = &AliasAttributeConversionMappingTable;
          }
          else
          {
            if ( a4 != 4 )
              return 3221225701LL;
            v33 = UserReverseMappingTable;
            Src = &UserObjectTypeList;
            v34 = 32;
            v35 = &UserAttributeConversionMappingTable;
          }
        }
      }
      v162 = v33;
      v159 = v35;
LABEL_38:
      ObjectTypeListLength = v34;
      if ( (unsigned int)THStateCheckForTraceOverride(v27, 19)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v37, v36)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v37, v36, v38, v39)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
      {
        v42 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v37, v36)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v37, v36, v40, v41)
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
        if ( (unsigned int)THStateCheckForTraceOverride(v37, v36)
          || (v43 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
        {
          v43 = 1;
        }
        LODWORD(PrivilegeSetLength) = v34;
        PrivilegeSet = (PPRIVILEGE_SET)&WPP_7c853a87250733c99b1f132b1f9c171b_Traceguids;
        LOWORD(GenericMapping) = 14;
        WPP_SF__ATTRTYP_LOG_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          522258443,
          4,
          13,
          v43,
          v42,
          14,
          (__int64)&WPP_7c853a87250733c99b1f132b1f9c171b_Traceguids);
      }
      if ( (unsigned int)THStateCheckForTraceOverride(v37, v36)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v45, v44)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v47, v46, v48, v49)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
      {
        TraceSecurityDescriptor(a2);
      }
      v50 = v34;
      v51 = v34;
      v31 = 0;
      v52 = 16 * v50;
      v158 = 0;
      if ( v52 > g_ulMaxStackAllocSize
        || v52 + g_ulAdditionalProbeSize + 8 < v52
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_194;
      }
      v53 = v52 + 23;
      if ( v52 + 23 <= v52 + 8 )
        v53 = 0xFFFFFFFFFFFFFF0LL;
      v54 = v53 & 0xFFFFFFFFFFFFFFF0uLL;
      v55 = alloca(v54);
      v56 = alloca(v54);
      v31 = (ULONG *)&v152;
      v158 = (ULONG *)&v152;
      if ( &v143 == (__int64 *)-128LL || (v152 = 1801679955, v31 = &v154, (v158 = &v154) == 0) )
      {
LABEL_194:
        if ( v52 + 8 >= v52 )
        {
          v57 = (ULONG *)((__int64 (*)(void))g_pfnAllocate)();
          v158 = v57;
          v31 = v57;
          if ( v57 )
          {
            v31 = v57 + 2;
            *v57 = 1885431112;
            v158 = v57 + 2;
          }
        }
      }
      if ( !v31 )
        goto LABEL_25;
      memcpy_0(v31, Src, v52);
      ClassAttribute = SampGetClassAttribute(*((unsigned int *)HandleId + 49), 589972, &v154, &v173);
      v30 = ClassAttribute;
      if ( ClassAttribute < 0 )
        goto LABEL_186;
      *((_QWORD *)v31 + 1) = &v173;
      v58 = AccessMask & 0x1000000;
      memset_0(AccessStatusList, 0, 4 * v51);
      memset_0(v174, 0, 4 * v51);
      if ( !v12 )
      {
        ClassAttribute = SampImpersonateClient(&v160);
        v30 = ClassAttribute;
        if ( ClassAttribute < 0 )
        {
LABEL_185:
          v31 = v158;
          goto LABEL_186;
        }
      }
      v59 = v58 | 0x2000000;
      v155 = 0;
      if ( v12 )
      {
        v154 = 256;
        memset_0(&v176, 0, 0x100u);
        v60 = ObjectTypeListLength;
        v61 = NtAccessCheckByTypeResultList(
                a2,
                ObjectSid,
                v12,
                v59,
                (POBJECT_TYPE_LIST)Src,
                ObjectTypeListLength,
                &DsGenericMap,
                &v176,
                &v154,
                v174,
                AccessStatusList);
        v64 = Src;
        v65 = v61;
      }
      else
      {
        GenerateOnClose = (unsigned __int8 *)HandleId + 208;
        SamSubsystemName = (struct _UNICODE_STRING *)SampGetSamSubsystemName();
        v60 = ObjectTypeListLength;
        v64 = Src;
        v65 = NtAccessCheckByTypeResultListAndAuditAlarm(
                SamSubsystemName,
                HandleId,
                ObjectTypeName,
                &UnicodeString,
                a2,
                ObjectSid,
                v59,
                AuditEventObjectAccess,
                0,
                (POBJECT_TYPE_LIST)Src,
                ObjectTypeListLength,
                &DsGenericMap,
                a7,
                v174,
                AccessStatusList,
                GenerateOnClose);
        SampRevertToSelf(v160);
      }
      if ( v65 < 0 )
      {
        LastError = GetLastError();
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
          || (unsigned int)THStateCheckForTraceOverride(v124, v123)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v124, v123)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v124, v123, v125, v126)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
        {
          v129 = gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v124, v123)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier(v124, v123, v127, v128)
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
          if ( (unsigned int)THStateCheckForTraceOverride(v124, v123)
            || (v130 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)) != 0 )
          {
            v130 = 1;
          }
          LODWORD(GrantedAccess) = v60;
          LODWORD(PrivilegeSetLength) = LastError;
          WPP_SF__ATTRTYP_LOG_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            522258762,
            2,
            13,
            v130,
            v129,
            18,
            (__int64)&WPP_7c853a87250733c99b1f132b1f9c171b_Traceguids);
        }
        v30 = -1073741790;
        ClassAttribute = -1073741790;
        RtlClearAllBits(BitMapHeader);
        v119 = v168;
      }
      else
      {
        v68 = 0;
        LOBYTE(v152) = 0;
        v154 = 0;
        do
        {
          v69 = 4 * v68;
          v70 = (unsigned int)v68;
          v71 = AccessStatusList[v68] == 0;
          v170 = 4 * v68;
          if ( v71 )
          {
            v72 = v155;
            v73 = 0;
            if ( !(_DWORD)v68 )
            {
              v73 = v174[v68] & 0x11F0000;
              v72 = v73 | v155;
              if ( (unsigned int)THStateCheckForTraceOverride(v63, v62)
                || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
                || gfTraceToSecondProvider
                && ((unsigned int)THStateCheckForTraceOverride(v75, v74)
                 || (unsigned int)ThStateCheckIfTraceToSecondProvier(v75, v74, v76, v77)
                 && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
              {
                v80 = gfTraceToSecondProvider
                   && ((unsigned int)THStateCheckForTraceOverride(v75, v74)
                    || (unsigned int)ThStateCheckIfTraceToSecondProvier(v75, v74, v78, v79)
                    && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
                if ( (unsigned int)THStateCheckForTraceOverride(v75, v74)
                  || (v81 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
                {
                  v81 = 1;
                }
                LODWORD(PrivilegeSetLength) = v73;
                WPP_SF__ATTRTYP_LOG_(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  522258585,
                  4,
                  13,
                  v81,
                  v80,
                  15,
                  (__int64)&WPP_7c853a87250733c99b1f132b1f9c171b_Traceguids);
              }
            }
            v82 = *((unsigned __int16 *)v162 + 512 * v70 + *((unsigned __int8 *)v174 + v69) + 256)
                | *((unsigned __int16 *)v162 + 512 * v70 + *((unsigned __int8 *)v174 + v69 + 1));
            if ( v82 || v73 )
              LOBYTE(v152) = 1;
            if ( v161 == 1 )
              v82 |= 0x70u;
            v155 = v82 | v72;
            if ( (unsigned int)THStateCheckForTraceOverride(v70 << 9, v162)
              || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
              || gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v84, v83)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier(v84, v83, v85, v86)
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
            {
              v88 = *(DWORD *)((char *)v174 + v69);
              v171 = 16 * v70;
              v89 = (_DWORD *)*((_QWORD *)Src + 2 * v70 + 1);
              v90 = v89[3];
              v91 = v89[2];
              v92 = v89[1];
              LODWORD(ObjectTypeName) = *v89;
              v95 = gfTraceToSecondProvider
                 && ((unsigned int)THStateCheckForTraceOverride(v84, v83)
                  || (unsigned int)ThStateCheckIfTraceToSecondProvier(v84, v83, v93, v94)
                  && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
              if ( (unsigned int)THStateCheckForTraceOverride(v84, v83)
                || (v99 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
              {
                v99 = 1;
              }
              LODWORD(GrantedAccessList) = v82;
              *(_DWORD *)ObjectCreation = v88;
              LODWORD(v149) = v90;
              LODWORD(AccessStatus) = v91;
              LODWORD(GrantedAccess) = v92;
              LODWORD(PrivilegeSetLength) = (_DWORD)ObjectTypeName;
              WPP_SF_DDDDDD(*((_QWORD *)WPP_GLOBAL_Control + 2), v96, v97, v98, v99, v95);
              v87 = v171;
              v69 = v170;
            }
            else
            {
              v87 = 16 * v70;
            }
            if ( v161 == 4 )
            {
              if ( (*((_BYTE *)v174 + v69) & 0x10) != 0 && *(GUID **)((char *)Src + v87 + 8) == &GUID_A_USER_PARAMETERS )
                *((_BYTE *)HandleId + 327) = 1;
              if ( (*((_BYTE *)v174 + v69) & 0x20) != 0 )
                SampSetAttributeAccess(4, *(unsigned int *)((char *)v159 + v69), BitMapHeader);
            }
            v100 = *(DWORD *)((char *)v174 + v69) >> 5;
            v101 = *(DWORD *)((char *)v174 + v69) >> 4;
            LOBYTE(v100) = (*(DWORD *)((char *)v174 + v69) & 0x20) != 0;
            LOBYTE(v101) = (*(DWORD *)((char *)v174 + v69) & 0x10) != 0;
            SampSetExtendedAttributeAccess(HandleId, *(unsigned int *)((char *)v159 + v69), v101, v100);
          }
          else if ( (unsigned int)THStateCheckForTraceOverride(v63, v62)
                 || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
                 || gfTraceToSecondProvider
                 && ((unsigned int)THStateCheckForTraceOverride(v63, v62)
                  || (unsigned int)ThStateCheckIfTraceToSecondProvier(v63, v62, v102, v103)
                  && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
          {
            v104 = *(int *)((char *)AccessStatusList + v69);
            v105 = (int *)v64[2 * v70 + 1];
            v106 = v105[3];
            v107 = v105[2];
            v108 = v105[1];
            v109 = *v105;
            v112 = gfTraceToSecondProvider
                && ((unsigned int)THStateCheckForTraceOverride(v63, v62)
                 || (unsigned int)ThStateCheckIfTraceToSecondProvier(v63, v62, v110, v111)
                 && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
            if ( (unsigned int)THStateCheckForTraceOverride(v63, v62)
              || (v115 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
            {
              v115 = 1;
            }
            *(_DWORD *)ObjectCreation = v104;
            LODWORD(v149) = v106;
            LODWORD(AccessStatus) = v107;
            v116 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            LODWORD(GrantedAccess) = v108;
            LODWORD(PrivilegeSetLength) = v109;
            WPP_SF_DDDDD(
              v116,
              522258693,
              v113,
              v114,
              v115,
              v112,
              17,
              (__int64)&WPP_7c853a87250733c99b1f132b1f9c171b_Traceguids);
          }
          v64 = Src;
          v68 = v154 + 1;
          v154 = v68;
        }
        while ( (unsigned int)v68 < ObjectTypeListLength );
        AccessMask &= ~0x2000000u;
        RtlMapGenericMask(&AccessMask, v172);
        v118 = AccessMask;
        if ( (AccessMask & v155) == AccessMask && (_BYTE)v152 )
        {
          v119 = v168;
          v30 = ClassAttribute;
          if ( v167 )
            v118 = v155;
          v120 = v165;
          *v168 = 0;
          *v120 = v118;
          goto LABEL_169;
        }
        v119 = v168;
        v121 = BitMapHeader;
        *v168 = -1073741790;
        RtlClearAllBits(v121);
        v30 = ClassAttribute;
      }
      v120 = v165;
LABEL_169:
      if ( (unsigned int)THStateCheckForTraceOverride(v118, v117)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v132, v131)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v132, v131, v133, v134)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
      {
        v135 = AccessMask;
        v136 = *v120;
        v137 = *v119;
        v140 = gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v132, v131)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v132, v131, v138, v139)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
        if ( !(unsigned int)THStateCheckForTraceOverride(v132, v131)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13) )
        {
          v19 = 0;
        }
        LODWORD(v149) = v155;
        LODWORD(AccessStatus) = v135;
        LODWORD(GrantedAccess) = v136;
        v142 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        LODWORD(PrivilegeSetLength) = v137;
        WPP_SF_dDdD(v142, 522258779, v141, 13, v19, v140, 19, (__int64)&WPP_7c853a87250733c99b1f132b1f9c171b_Traceguids);
        v30 = ClassAttribute;
      }
      goto LABEL_185;
    }
LABEL_37:
    v34 = 1;
    Src = &ServerObjectTypeList;
    v162 = ServerReverseMappingTable;
    v159 = &ServerAttributeConversionMappingTable;
    goto LABEL_38;
  }
  return (unsigned int)v30;
}

```

## disassembly

```asm
0x1803e55d0  push    rbp
0x1803e55d2  push    rbx
0x1803e55d3  push    rsi
0x1803e55d4  push    rdi
0x1803e55d5  push    r12
0x1803e55d7  push    r13
0x1803e55d9  push    r14
0x1803e55db  push    r15
0x1803e55dd  sub     rsp, 0A48h
0x1803e55e4  lea     rbp, [rsp+80h]
0x1803e55ec  mov     rax, cs:__security_cookie
0x1803e55f3  xor     rax, rbp
0x1803e55f6  mov     [rbp+0A00h+var_50], rax
0x1803e55fd  mov     rax, [rbp+0A00h+arg_20]
0x1803e5604  xorps   xmm0, xmm0
0x1803e5607  mov     r12, [rbp+0A00h+ClientToken]
0x1803e560e  mov     r14d, r9d
0x1803e5611  mov     [rbp+0A00h+ObjectTypeName], rax
0x1803e5615  mov     r15, r8
0x1803e5618  mov     rax, [rbp+0A00h+arg_38]
0x1803e561f  mov     r13, rdx
0x1803e5622  mov     [rbp+0A00h+var_970], rax
0x1803e5629  mov     rsi, rcx
0x1803e562c  mov     rax, [rbp+0A00h+arg_48]
0x1803e5633  mov     [rbp+0A00h+var_9B0], rax
0x1803e5637  mov     rax, [rbp+0A00h+arg_50]
0x1803e563e  mov     [rbp+0A00h+BitMapHeader], rax
0x1803e5642  mov     rax, [rbp+0A00h+arg_58]
0x1803e5649  mov     [rbp+0A00h+var_998], rax
0x1803e564d  mov     eax, [rbp+0A00h+AccessMask]
0x1803e5653  and     eax, 2000000h
0x1803e5658  mov     [rbp+0A00h+var_9CC], r9d
0x1803e565c  mov     [rbp+0A00h+var_9A0], eax
0x1803e565f  mov     [rbp+0A00h+HandleId], rcx
0x1803e5663  movups  [rbp+0A00h+var_968], xmm0
0x1803e566a  mov     [rbp+0A00h+var_9F8], 10h
0x1803e5671  movups  xmmword ptr [rbp+0A00h+UnicodeString.Length], xmm0
0x1803e5675  mov     [rbp+0A00h+var_9D0], 0
0x1803e567c  call    THStateCheckForTraceOverride
0x1803e5681  mov     edi, 1
0x1803e5686  lea     ebx, [rdi+0Ch]
0x1803e5689  test    eax, eax
0x1803e568b  jnz     short loc_1803E56D7
0x1803e568d  mov     r8d, ebx
0x1803e5690  lea     edx, [rdi+3]
0x1803e5693  xor     ecx, ecx
0x1803e5695  call    CheckWPPLevelFlagsEnabledForProvider
0x1803e569a  test    eax, eax
0x1803e569c  jnz     short loc_1803E56D7
0x1803e569e  mov     eax, cs:gfTraceToSecondProvider
0x1803e56a4  test    eax, eax
0x1803e56a6  jz      loc_1803E5763
0x1803e56ac  call    THStateCheckForTraceOverride
0x1803e56b1  test    eax, eax
0x1803e56b3  jnz     short loc_1803E56D7
0x1803e56b5  call    ThStateCheckIfTraceToSecondProvier
0x1803e56ba  test    eax, eax
0x1803e56bc  jz      loc_1803E5763
0x1803e56c2  mov     r8d, ebx
0x1803e56c5  lea     edx, [rdi+3]
0x1803e56c8  mov     ecx, edi
0x1803e56ca  call    CheckWPPLevelFlagsEnabledForProvider
0x1803e56cf  test    eax, eax
0x1803e56d1  jz      loc_1803E5763
0x1803e56d7  mov     eax, cs:gfTraceToSecondProvider
0x1803e56dd  test    eax, eax
0x1803e56df  jz      short loc_1803E570A
0x1803e56e1  call    THStateCheckForTraceOverride
0x1803e56e6  test    eax, eax
0x1803e56e8  jnz     short loc_1803E5706
0x1803e56ea  call    ThStateCheckIfTraceToSecondProvier
0x1803e56ef  test    eax, eax
0x1803e56f1  jz      short loc_1803E570A
0x1803e56f3  mov     r8d, ebx
0x1803e56f6  mov     edx, 4
0x1803e56fb  mov     ecx, edi
0x1803e56fd  call    CheckWPPLevelFlagsEnabledForProvider
0x1803e5702  test    eax, eax
0x1803e5704  jz      short loc_1803E570A
0x1803e5706  mov     ebx, edi
0x1803e5708  jmp     short loc_1803E570C
0x1803e570a  xor     ebx, ebx
0x1803e570c  call    THStateCheckForTraceOverride
0x1803e5711  test    eax, eax
0x1803e5713  jnz     short loc_1803E5727
0x1803e5715  lea     edx, [rax+4]
0x1803e5718  xor     ecx, ecx
0x1803e571a  lea     r8d, [rax+0Dh]
0x1803e571e  call    CheckWPPLevelFlagsEnabledForProvider
0x1803e5723  test    eax, eax
0x1803e5725  jz      short loc_1803E5729
0x1803e5727  mov     eax, edi
0x1803e5729  lea     rcx, WPP_7c853a87250733c99b1f132b1f9c171b_Traceguids
0x1803e5730  mov     edx, 1F2107A6h; int
0x1803e5735  mov     [rsp+0A80h+PrivilegeSet], rcx; LPCGUID
0x1803e573a  mov     ecx, 0Dh
0x1803e573f  mov     word ptr [rsp+0A80h+GenericMapping], cx; __int16
0x1803e5744  mov     r9d, ecx; int
0x1803e5747  mov     [rsp+0A80h+ObjectTypeLength], ebx; int
0x1803e574b  mov     dword ptr [rsp+0A80h+ObjectTypeList], eax; int
0x1803e574f  lea     r8d, [rcx-9]; int
0x1803e5753  mov     rcx, cs:WPP_GLOBAL_Control
0x1803e575a  mov     rcx, [rcx+10h]; int
0x1803e575e  call    WPP_SF_
0x1803e5763  mov     rax, [rbp+0A00h+var_9B0]
0x1803e5767  mov     rcx, [rbp+0A00h+BitMapHeader]; BitMapHeader
0x1803e576b  mov     dword ptr [rax], 0
0x1803e5771  call    cs:__imp_RtlClearAllBits
0x1803e5777  mov     rdx, [rsi+0B0h]
0x1803e577e  cmp     dword ptr [rdx+34h], 0
0x1803e5782  jbe     short loc_1803E57A1
0x1803e5784  movzx   eax, word ptr [rdx+34h]
0x1803e5788  add     ax, ax
0x1803e578b  mov     [rbp+0A00h+var_9FF], 0
0x1803e578f  mov     [rbp+0A00h+UnicodeString.MaximumLength], ax
0x1803e5793  mov     [rbp+0A00h+UnicodeString.Length], ax
0x1803e5797  lea     rax, [rdx+38h]
0x1803e579b  mov     [rbp+0A00h+UnicodeString.Buffer], rax
0x1803e579f  jmp     short loc_1803E57C0
0x1803e57a1  add     rdx, 18h; Sid
0x1803e57a5  lea     rcx, [rbp+0A00h+UnicodeString]; UnicodeString
0x1803e57a9  mov     r8b, dil; AllocateDestinationString
0x1803e57ac  call    cs:__imp_RtlConvertSidToUnicodeString
0x1803e57b2  mov     ebx, eax
0x1803e57b4  test    eax, eax
0x1803e57b6  js      loc_1803E639B
0x1803e57bc  mov     [rbp+0A00h+var_9FF], dil
0x1803e57c0  mov     edx, 13h
0x1803e57c5  test    r15, r15
0x1803e57c8  jnz     short loc_1803E57F8
0x1803e57ca  test    r14d, r14d
0x1803e57cd  jz      loc_1803E58AA
0x1803e57d3  mov     rcx, [rsi+0B0h]
0x1803e57da  call    SampDsGetObjectSid
0x1803e57df  mov     r15, rax
0x1803e57e2  test    rax, rax
0x1803e57e5  jnz     short loc_1803E57F3
0x1803e57e7  xor     esi, esi
0x1803e57e9  mov     ebx, 0C000009Ah
0x1803e57ee  jmp     loc_1803E635F
0x1803e57f3  mov     edx, 13h
0x1803e57f8  mov     ecx, r14d
0x1803e57fb  test    r14d, r14d
0x1803e57fe  jz      loc_1803E58AA
0x1803e5804  sub     ecx, edi
0x1803e5806  jz      loc_1803E588D
0x1803e580c  sub     ecx, edi
0x1803e580e  jz      short loc_1803E586D
0x1803e5810  sub     ecx, edi
0x1803e5812  jz      short loc_1803E584D
0x1803e5814  cmp     ecx, edi
0x1803e5816  jz      short loc_1803E5822
0x1803e5818  mov     eax, 0C00000E5h
0x1803e581d  jmp     loc_1803E639D
0x1803e5822  mov     r14, cs:?UserReverseMappingTable@@3PEAU_REVERSE_MAPPING_TABLE_ENTRY@@EA; _REVERSE_MAPPING_TABLE_ENTRY * UserReverseMappingTable
0x1803e5829  lea     rbx, ?UserObjectTypeList@@3PAU_OBJECT_TYPE_LIST@@A; _OBJECT_TYPE_LIST near * UserObjectTypeList
0x1803e5830  mov     [rbp+0A00h+Src], rbx
0x1803e5834  mov     esi, 20h ; ' '
0x1803e5839  lea     rbx, ?UserAttributeConversionMappingTable@@3PAKA; ulong near * UserAttributeConversionMappingTable
0x1803e5840  mov     [rbp+0A00h+var_9C8], r14
0x1803e5844  mov     [rbp+0A00h+var_9D8], rbx
0x1803e5848  jmp     loc_1803E58CD
0x1803e584d  mov     r14, cs:?AliasReverseMappingTable@@3PEAU_REVERSE_MAPPING_TABLE_ENTRY@@EA; _REVERSE_MAPPING_TABLE_ENTRY * AliasReverseMappingTable
0x1803e5854  lea     rbx, ?AliasObjectTypeList@@3PAU_OBJECT_TYPE_LIST@@A; _OBJECT_TYPE_LIST near * AliasObjectTypeList
0x1803e585b  mov     [rbp+0A00h+Src], rbx
0x1803e585f  mov     esi, 6
0x1803e5864  lea     rbx, ?AliasAttributeConversionMappingTable@@3PAKA; ulong near * AliasAttributeConversionMappingTable
0x1803e586b  jmp     short loc_1803E5840
0x1803e586d  mov     r14, cs:?GroupReverseMappingTable@@3PEAU_REVERSE_MAPPING_TABLE_ENTRY@@EA; _REVERSE_MAPPING_TABLE_ENTRY * GroupReverseMappingTable
0x1803e5874  lea     rbx, ?GroupObjectTypeList@@3PAU_OBJECT_TYPE_LIST@@A; _OBJECT_TYPE_LIST near * GroupObjectTypeList
0x1803e587b  mov     [rbp+0A00h+Src], rbx
0x1803e587f  mov     esi, 6
0x1803e5884  lea     rbx, ?GroupAttributeConversionMappingTable@@3PAKA; ulong near * GroupAttributeConversionMappingTable
0x1803e588b  jmp     short loc_1803E5840
0x1803e588d  mov     r14, cs:?DomainReverseMappingTable@@3PEAU_REVERSE_MAPPING_TABLE_ENTRY@@EA; _REVERSE_MAPPING_TABLE_ENTRY * DomainReverseMappingTable
0x1803e5894  lea     rbx, ?DomainObjectTypeList@@3PAU_OBJECT_TYPE_LIST@@A; _OBJECT_TYPE_LIST near * DomainObjectTypeList
0x1803e589b  mov     [rbp+0A00h+Src], rbx
0x1803e589f  mov     esi, edx
0x1803e58a1  lea     rbx, ?DomainAttributeConversionMappingTable@@3PAKA; ulong near * DomainAttributeConversionMappingTable
0x1803e58a8  jmp     short loc_1803E5840
0x1803e58aa  lea     rax, ?ServerObjectTypeList@@3PAU_OBJECT_TYPE_LIST@@A; _OBJECT_TYPE_LIST near * ServerObjectTypeList
0x1803e58b1  mov     esi, edi
0x1803e58b3  mov     [rbp+0A00h+Src], rax
0x1803e58b7  mov     rax, cs:?ServerReverseMappingTable@@3PEAU_REVERSE_MAPPING_TABLE_ENTRY@@EA; _REVERSE_MAPPING_TABLE_ENTRY * ServerReverseMappingTable
0x1803e58be  mov     [rbp+0A00h+var_9C8], rax
0x1803e58c2  lea     rax, ?ServerAttributeConversionMappingTable@@3PAKA; ulong near * ServerAttributeConversionMappingTable
0x1803e58c9  mov     [rbp+0A00h+var_9D8], rax
0x1803e58cd  mov     [rbp+0A00h+ObjectTypeListLength], esi
0x1803e58d0  call    THStateCheckForTraceOverride
0x1803e58d5  mov     r14d, 0Dh
0x1803e58db  lea     ebx, [r14-9]
0x1803e58df  test    eax, eax
0x1803e58e1  jnz     short loc_1803E592B
0x1803e58e3  mov     r8d, r14d
0x1803e58e6  mov     edx, ebx
0x1803e58e8  xor     ecx, ecx
0x1803e58ea  call    CheckWPPLevelFlagsEnabledForProvider
0x1803e58ef  test    eax, eax
0x1803e58f1  jnz     short loc_1803E592B
0x1803e58f3  mov     eax, cs:gfTraceToSecondProvider
0x1803e58f9  test    eax, eax
0x1803e58fb  jz      loc_1803E59B8
0x1803e5901  call    THStateCheckForTraceOverride
0x1803e5906  test    eax, eax
0x1803e5908  jnz     short loc_1803E592B
0x1803e590a  call    ThStateCheckIfTraceToSecondProvier
0x1803e590f  test    eax, eax
0x1803e5911  jz      loc_1803E59B8
0x1803e5917  mov     r8d, r14d
0x1803e591a  mov     edx, ebx
0x1803e591c  mov     ecx, edi
0x1803e591e  call    CheckWPPLevelFlagsEnabledForProvider
0x1803e5923  test    eax, eax
0x1803e5925  jz      loc_1803E59B8
0x1803e592b  mov     eax, cs:gfTraceToSecondProvider
0x1803e5931  test    eax, eax
0x1803e5933  jz      short loc_1803E595B
0x1803e5935  call    THStateCheckForTraceOverride
0x1803e593a  test    eax, eax
0x1803e593c  jnz     short loc_1803E5957
0x1803e593e  call    ThStateCheckIfTraceToSecondProvier
0x1803e5943  test    eax, eax
0x1803e5945  jz      short loc_1803E595B
0x1803e5947  mov     r8d, r14d
0x1803e594a  mov     edx, ebx
0x1803e594c  mov     ecx, edi
0x1803e594e  call    CheckWPPLevelFlagsEnabledForProvider
0x1803e5953  test    eax, eax
0x1803e5955  jz      short loc_1803E595B
0x1803e5957  mov     ebx, edi
0x1803e5959  jmp     short loc_1803E595D
0x1803e595b  xor     ebx, ebx
0x1803e595d  call    THStateCheckForTraceOverride
0x1803e5962  test    eax, eax
0x1803e5964  jnz     short loc_1803E5977
0x1803e5966  mov     r8d, r14d
0x1803e5969  lea     edx, [rax+4]
0x1803e596c  xor     ecx, ecx
0x1803e596e  call    CheckWPPLevelFlagsEnabledForProvider
0x1803e5973  test    eax, eax
0x1803e5975  jz      short loc_1803E5979
0x1803e5977  mov     eax, edi
0x1803e5979  mov     rcx, cs:WPP_GLOBAL_Control
0x1803e5980  lea     rdx, WPP_7c853a87250733c99b1f132b1f9c171b_Traceguids
0x1803e5987  mov     dword ptr [rsp+0A80h+PrivilegeSetLength], esi
0x1803e598b  mov     r9d, r14d
0x1803e598e  mov     [rsp+0A80h+PrivilegeSet], rdx
0x1803e5993  mov     edx, 1F21080Bh
0x1803e5998  mov     word ptr [rsp+0A80h+GenericMapping], 0Eh
0x1803e599f  mov     rcx, [rcx+10h]
0x1803e59a3  mov     [rsp+0A80h+ObjectTypeLength], ebx
0x1803e59a7  mov     ebx, 4
0x1803e59ac  mov     r8d, ebx
0x1803e59af  mov     dword ptr [rsp+0A80h+ObjectTypeList], eax
0x1803e59b3  call    WPP_SF__ATTRTYP_LOG_
0x1803e59b8  call    THStateCheckForTraceOverride
0x1803e59bd  test    eax, eax
0x1803e59bf  jnz     short loc_1803E59FD
0x1803e59c1  mov     r8d, r14d
0x1803e59c4  mov     edx, ebx
0x1803e59c6  xor     ecx, ecx
0x1803e59c8  call    CheckWPPLevelFlagsEnabledForProvider
0x1803e59cd  test    eax, eax
0x1803e59cf  jnz     short loc_1803E59FD
0x1803e59d1  mov     eax, cs:gfTraceToSecondProvider
0x1803e59d7  test    eax, eax
0x1803e59d9  jz      short loc_1803E5A05
0x1803e59db  call    THStateCheckForTraceOverride
0x1803e59e0  test    eax, eax
0x1803e59e2  jnz     short loc_1803E59FD
0x1803e59e4  call    ThStateCheckIfTraceToSecondProvier
0x1803e59e9  test    eax, eax
0x1803e59eb  jz      short loc_1803E5A05
0x1803e59ed  mov     r8d, r14d
0x1803e59f0  mov     edx, ebx
0x1803e59f2  mov     ecx, edi
0x1803e59f4  call    CheckWPPLevelFlagsEnabledForProvider
0x1803e59f9  test    eax, eax
0x1803e59fb  jz      short loc_1803E5A05
0x1803e59fd  mov     rcx, r13; SecurityDescriptor
0x1803e5a00  call    TraceSecurityDescriptor
0x1803e5a05  mov     ebx, esi
0x1803e5a07  mov     r14d, esi
0x1803e5a0a  xor     esi, esi
0x1803e5a0c  shl     rbx, 4
0x1803e5a10  cmp     rbx, cs:g_ulMaxStackAllocSize
0x1803e5a17  mov     [rbp+0A00h+var_9E0], rsi
0x1803e5a1b  ja      short loc_1803E5A80
0x1803e5a1d  mov     rcx, cs:g_ulAdditionalProbeSize
0x1803e5a24  add     rcx, 8
0x1803e5a28  add     rcx, rbx
0x1803e5a2b  cmp     rcx, rbx
0x1803e5a2e  jb      short loc_1803E5A80
0x1803e5a30  call    VerifyStackAvailable
0x1803e5a35  test    eax, eax
0x1803e5a37  jz      short loc_1803E5A80
0x1803e5a39  lea     rax, [rbx+8]
0x1803e5a3d  lea     rcx, [rax+0Fh]
0x1803e5a41  cmp     rcx, rax
0x1803e5a44  ja      short loc_1803E5A50
  ... truncated ...
```
