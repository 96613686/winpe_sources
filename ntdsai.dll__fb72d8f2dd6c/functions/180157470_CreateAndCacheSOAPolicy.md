# CreateAndCacheSOAPolicy

- ea: `0x180157470`
- end: `0x180158a5e`
- name: `CreateAndCacheSOAPolicy`
- size: `5614`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18015965c`

## callees

- `0x180001008`
- `0x180001034`
- `0x180006360`
- `0x1800067d0`
- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x18001ea60`
- `0x180021aa3`
- `0x180030d80`
- `0x18003dc50`
- `0x1800a1694`
- `0x180157470`
- `0x180158d4c`
- `0x180180c50`
- `0x180181ae0`
- `0x180181bf0`
- `0x180453340`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180158915`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180158915`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1801579e5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1801579e5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180158180`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180158180`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180158071`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180158071`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18015828e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18015828e`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18015839c`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1801584a7`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18015839c`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1801584a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180157b05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015807f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015818e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015829c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801584b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801585c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180157b05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015807f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015818e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015829c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801584b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801585c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801586d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801586f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180158a51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180460c30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180460c4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801586d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801586f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180158a51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180460c30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180460c4f`
- `ntdll!RtlInitUnicodeString` at `0x180157bb2`
- `ntdll!RtlInitUnicodeString` at `0x180157bc7`
- `ntdll!RtlInitUnicodeString` at `0x180157bb2`
- `ntdll!RtlInitUnicodeString` at `0x180157bc7`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1801585b4`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1801585b4`
- `ntdll!RtlEqualUnicodeString` at `0x180157be0`
- `ntdll!RtlEqualUnicodeString` at `0x180157c07`
- `ntdll!RtlEqualUnicodeString` at `0x180157be0`
- `ntdll!RtlEqualUnicodeString` at `0x180157c07`
- `ADVAPI32!SetEntriesInAclW` at `0x180157f70`
- `ADVAPI32!SetEntriesInAclW` at `0x180157f70`

## pseudocode

```c
__int64 __fastcall CreateAndCacheSOAPolicy(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  ULONG v3; // r13d
  _OWORD *v4; // rax
  __int64 v5; // r12
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // r14d
  BOOL v9; // ebx
  size_t v11; // rbx
  void *v12; // rax
  DWORD v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // rcx
  BOOL v16; // edi
  int v17; // eax
  int v18; // edx
  __int64 v19; // r13
  __int64 v20; // rdi
  WCHAR *v21; // rdx
  unsigned int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  BOOL v25; // ebx
  int v26; // eax
  unsigned int v27; // r13d
  unsigned __int64 v28; // rdi
  const WCHAR *v29; // rax
  LPWCH *v30; // rdi
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rcx
  BOOL v34; // edi
  __int64 v35; // rbx
  char LastError; // al
  __int64 v37; // rdx
  __int64 v38; // rcx
  BOOL v39; // ebx
  int v40; // eax
  size_t v41; // rbx
  void *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rcx
  BOOL v45; // ebx
  int v46; // eax
  __int64 v47; // rdx
  __int64 v48; // rcx
  BOOL v49; // edi
  int v50; // eax
  __int64 v51; // rdx
  __int64 v52; // rcx
  BOOL v53; // edi
  BOOL v54; // ecx
  __int64 v55; // rdx
  __int64 v56; // rcx
  BOOL v57; // edi
  BOOL v58; // ecx
  __int64 v59; // rdx
  __int64 v60; // rcx
  BOOL v61; // edi
  BOOL v62; // ecx
  __int64 v63; // rdx
  __int64 v64; // rcx
  BOOL v65; // edi
  BOOL v66; // ecx
  void *v67; // rax
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // rdx
  __int64 v71; // rcx
  BOOL v72; // edi
  BOOL v73; // ecx
  __int64 v74; // rdx
  __int64 v75; // rcx
  BOOL v76; // edi
  BOOL v77; // ecx
  PACL v78; // rcx
  __int64 i; // rdi
  LPOVERLAPPED v80; // rdi
  int v81; // ecx
  int v82; // r9d
  __int64 *v83; // rax
  LPOVERLAPPED v84; // rdi
  __int16 v85; // [rsp+30h] [rbp-1188h]
  ULONG StringSecurityDescriptorLen; // [rsp+54h] [rbp-1164h] BYREF
  unsigned int v87; // [rsp+58h] [rbp-1160h]
  ULONG cCountOfExplicitEntries; // [rsp+5Ch] [rbp-115Ch]
  LPWSTR StringSecurityDescriptor; // [rsp+60h] [rbp-1158h] BYREF
  DWORD dwBufferLength; // [rsp+68h] [rbp-1150h] BYREF
  int v91; // [rsp+6Ch] [rbp-114Ch]
  int v92; // [rsp+70h] [rbp-1148h]
  PACL NewAcl; // [rsp+78h] [rbp-1140h] BYREF
  unsigned int v94; // [rsp+80h] [rbp-1138h]
  __int64 v95; // [rsp+88h] [rbp-1130h] BYREF
  UNICODE_STRING String1; // [rsp+90h] [rbp-1128h] BYREF
  LPCWSTR StringSid; // [rsp+A0h] [rbp-1118h]
  unsigned __int64 v98; // [rsp+A8h] [rbp-1110h]
  __int64 v99; // [rsp+B0h] [rbp-1108h]
  _OWORD pSecurityDescriptor[2]; // [rsp+B8h] [rbp-1100h] BYREF
  __int64 v101; // [rsp+D8h] [rbp-10E0h]
  struct _UNICODE_STRING DestinationString; // [rsp+E0h] [rbp-10D8h] BYREF
  UNICODE_STRING String2; // [rsp+F0h] [rbp-10C8h] BYREF
  __int64 v104; // [rsp+100h] [rbp-10B8h] BYREF
  int v105; // [rsp+108h] [rbp-10B0h]
  int Internal; // [rsp+10Ch] [rbp-10ACh]
  __int64 v107; // [rsp+110h] [rbp-10A8h]
  int v108; // [rsp+118h] [rbp-10A0h]
  int v109; // [rsp+11Ch] [rbp-109Ch]
  __int64 v110; // [rsp+120h] [rbp-1098h]
  __int64 v111; // [rsp+128h] [rbp-1090h]
  ULONG *p_StringSecurityDescriptorLen; // [rsp+130h] [rbp-1088h]
  __int64 v113; // [rsp+138h] [rbp-1080h]
  __int64 v114; // [rsp+140h] [rbp-1078h]
  int v115; // [rsp+148h] [rbp-1070h]
  __int64 v116; // [rsp+14Ch] [rbp-106Ch]
  int v117; // [rsp+154h] [rbp-1064h]
  int *v118; // [rsp+158h] [rbp-1060h]
  int v119; // [rsp+160h] [rbp-1058h] BYREF
  __int64 v120; // [rsp+168h] [rbp-1050h]
  int v121; // [rsp+180h] [rbp-1038h]
  __int64 *v122; // [rsp+188h] [rbp-1030h]
  __int64 v123; // [rsp+198h] [rbp-1020h] BYREF
  int v124; // [rsp+1A0h] [rbp-1018h]
  LPWSTR v125; // [rsp+1A8h] [rbp-1010h]
  HLOCAL hMem[64]; // [rsp+380h] [rbp-E38h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries[64]; // [rsp+580h] [rbp-C38h] BYREF

  v2 = a2;
  v99 = a2;
  v95 = a1;
  memset_0(pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  memset_0(hMem, 0, sizeof(hMem));
  v3 = 0;
  NewAcl = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v101 = 0;
  String1 = 0;
  DestinationString = 0;
  String2 = 0;
  dwBufferLength = 0;
  v4 = (_OWORD *)DSAllocAux(48, 56361346);
  v5 = (__int64)v4;
  if ( !v4 )
  {
    if ( !(unsigned int)IncrementWPPPerfCountersForLevel(2)
      && !(unsigned int)THStateCheckForTraceOverride(v7, v6)
      && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
    {
      if ( !gfTraceToSecondProvider )
        return 8;
      if ( !(unsigned int)THStateCheckForTraceOverride(v7, v6) )
      {
        if ( (unsigned int)ThStateCheckIfTraceToSecondProvier() )
        {
          v8 = 1;
          if ( (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3) )
            goto LABEL_11;
        }
        return 8;
      }
    }
    v8 = 1;
LABEL_11:
    v9 = gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v7, v6)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
    if ( !(unsigned int)THStateCheckForTraceOverride(v7, v6)
      && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
    {
      v8 = 0;
    }
    WPP_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56361352,
      2,
      3,
      v8,
      v9,
      10,
      &WPP_58eb3ebf6fe43bf462328e8368ddc743_Traceguids);
    return 8;
  }
  StringSecurityDescriptorLen = 0;
  cCountOfExplicitEntries = 0;
  *v4 = 0;
  v4[1] = 0;
  v4[2] = 0;
  v11 = **(unsigned int **)(v2 + 8);
  v12 = (void *)DSAllocAux(v11, 56361363);
  *(_QWORD *)(v5 + 24) = v12;
  if ( v12 )
  {
    memcpy_0(v12, *(const void **)(v2 + 8), v11);
    v19 = 0;
    while ( 1 )
    {
      v91 = v19;
      if ( (unsigned int)v19 >= *(_DWORD *)(v2 + 24) || StringSecurityDescriptorLen )
        break;
      v20 = 96 * v19;
      v98 = 96 * v19;
      v21 = *(WCHAR **)(v99 + 32);
      StringSecurityDescriptor = v21;
      if ( *(_DWORD *)&v21[48 * v19] == 3 )
      {
        v41 = **(unsigned int **)((char *)v21 + v20 + 16);
        v42 = (void *)DSAllocAux(v41 + 2, 56361386);
        *(_QWORD *)(v5 + 32) = v42;
        if ( v42 )
        {
          memcpy_0(v42, *(const void **)(*(_QWORD *)((char *)StringSecurityDescriptor + v20 + 16) + 8LL), v41);
          *(_WORD *)(*(_QWORD *)(v5 + 32) + 2 * (v41 >> 1)) = 0;
        }
        else
        {
          StringSecurityDescriptorLen = 8;
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
            || (unsigned int)THStateCheckForTraceOverride(v44, v43)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v44, v43)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier()
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
          {
            v45 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v44, v43)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
            if ( (unsigned int)THStateCheckForTraceOverride(v44, v43)
              || (v46 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)) != 0 )
            {
              v46 = 1;
            }
            WPP_SF_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              56361392,
              2,
              3,
              v46,
              v45,
              12,
              &WPP_58eb3ebf6fe43bf462328e8368ddc743_Traceguids);
          }
        }
      }
      else if ( *(_DWORD *)((char *)v21 + v20) == 589872 )
      {
        String1.Length = **(_WORD **)((char *)v21 + v20 + 16);
        String1.MaximumLength = **(_WORD **)((char *)v21 + v20 + 16);
        String1.Buffer = *(PWSTR *)(*(_QWORD *)((char *)v21 + v20 + 16) + 8LL);
        RtlInitUnicodeString(&DestinationString, L"Audit");
        RtlInitUnicodeString(&String2, L"Enforced");
        if ( RtlEqualUnicodeString(&String1, &DestinationString, 1u) )
        {
          *(_DWORD *)(v5 + 20) = 2;
        }
        else if ( RtlEqualUnicodeString(&String1, &String2, 1u) )
        {
          *(_DWORD *)(v5 + 20) = 1;
        }
        else
        {
          *(_DWORD *)(v5 + 20) = 0;
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
            || (unsigned int)THStateCheckForTraceOverride(v38, v37)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v38, v37)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier()
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
          {
            v39 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v38, v37)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
            if ( (unsigned int)THStateCheckForTraceOverride(v38, v37)
              || (v40 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)) != 0 )
            {
              v40 = 1;
            }
            WPP_SF_Z(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              56361476,
              3,
              3,
              v40,
              v39,
              15,
              &WPP_58eb3ebf6fe43bf462328e8368ddc743_Traceguids,
              (__int64)&String1);
          }
        }
      }
      else if ( *(_DWORD *)((char *)v21 + v20) == 591521 )
      {
        v22 = *(_DWORD *)((char *)v21 + v20 + 8);
        v87 = v22;
        if ( v22 > 0x40 )
        {
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
            || (unsigned int)THStateCheckForTraceOverride(v24, v23)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v24, v23)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier()
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
          {
            v25 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v24, v23)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
            if ( (unsigned int)THStateCheckForTraceOverride(v24, v23)
              || (v26 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)) != 0 )
            {
              v26 = 1;
            }
            WPP_SF_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              56361411,
              3,
              3,
              v26,
              v25,
              13,
              &WPP_58eb3ebf6fe43bf462328e8368ddc743_Traceguids);
          }
          v22 = v87;
          v21 = StringSecurityDescriptor;
        }
        v27 = 0;
        v94 = 0;
        while ( v27 < v22 && v27 < 0x40 )
        {
          v28 = *(unsigned int *)(*(_QWORD *)((char *)v21 + v20 + 16) + 16LL * v27);
          StringSid = (LPCWSTR)THAlloc_(v95, 1, (int)v28 + 2, 1, 0, 56361418);
          memcpy_0(
            (void *)StringSid,
            *(const void **)(*(_QWORD *)&StringSecurityDescriptor[v98 / 2 + 8] + 16LL * v27 + 8),
            (unsigned int)v28);
          v29 = StringSid;
          StringSid[v28 >> 1] = 0;
          v30 = (LPWCH *)&hMem[cCountOfExplicitEntries];
          if ( ConvertStringSidToSidW(v29, (PSID *)v30) )
          {
            v31 = cCountOfExplicitEntries;
            pListOfExplicitEntries[v31].grfAccessPermissions = 983551;
            *(_QWORD *)&pListOfExplicitEntries[v31].grfAccessMode = 2;
            pListOfExplicitEntries[v31].Trustee.pMultipleTrustee = 0;
            *(_QWORD *)&pListOfExplicitEntries[v31].Trustee.MultipleTrusteeOperation = 0;
            pListOfExplicitEntries[v31].Trustee.TrusteeType = TRUSTEE_IS_UNKNOWN;
            pListOfExplicitEntries[v31].Trustee.ptstrName = *v30;
            ++cCountOfExplicitEntries;
          }
          else if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
                 || (unsigned int)THStateCheckForTraceOverride(v33, v32)
                 || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
                 || gfTraceToSecondProvider
                 && ((unsigned int)THStateCheckForTraceOverride(v33, v32)
                  || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                  && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
          {
            v92 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v33, v32)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
            v34 = (unsigned int)THStateCheckForTraceOverride(v33, v32)
               || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3);
            v35 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            LastError = GetLastError();
            WPP_SF_Sd(
              v35,
              56361443,
              3,
              3,
              v34,
              v92,
              14,
              &WPP_58eb3ebf6fe43bf462328e8368ddc743_Traceguids,
              (__int64)StringSid,
              LastError);
          }
          v94 = ++v27;
          v20 = v98;
          v21 = StringSecurityDescriptor;
          v22 = v87;
        }
        LODWORD(v19) = v91;
      }
      v19 = (unsigned int)(v19 + 1);
      v2 = v99;
    }
    v3 = cCountOfExplicitEntries;
    if ( cCountOfExplicitEntries )
    {
      v13 = SetEntriesInAclW(cCountOfExplicitEntries, pListOfExplicitEntries, 0, &NewAcl);
      if ( v13 )
      {
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
          || (unsigned int)THStateCheckForTraceOverride(v52, v51)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v52, v51)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
        {
          v53 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v52, v51)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
          v54 = (unsigned int)THStateCheckForTraceOverride(v52, v51)
             || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3);
          WPP_SF__DS_NAME_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56361513,
            3,
            3,
            v54,
            v53,
            17,
            &WPP_58eb3ebf6fe43bf462328e8368ddc743_Traceguids,
            *(_QWORD *)(v5 + 24),
            v13);
        }
      }
      else if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
      {
        if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, NewAcl, 0) )
        {
          if ( SetSecurityDescriptorOwner(pSecurityDescriptor, gpEnterpriseAdminSid, 0) )
          {
            MakeSelfRelativeSD(pSecurityDescriptor, *(PSECURITY_DESCRIPTOR *)(v5 + 40), &dwBufferLength);
            v67 = (void *)DSAllocAux(dwBufferLength, 56361561);
            *(_QWORD *)(v5 + 40) = v67;
            if ( v67 )
            {
              if ( MakeSelfRelativeSD(pSecurityDescriptor, v67, &dwBufferLength) )
              {
                if ( !RtlValidRelativeSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(v5 + 40), dwBufferLength, 5u) )
                {
                  v13 = GetLastError();
                  if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
                    || (unsigned int)THStateCheckForTraceOverride(v75, v74)
                    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
                    || gfTraceToSecondProvider
                    && ((unsigned int)THStateCheckForTraceOverride(v75, v74)
                     || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
                  {
                    v76 = gfTraceToSecondProvider
                       && ((unsigned int)THStateCheckForTraceOverride(v75, v74)
                        || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
                    v77 = (unsigned int)THStateCheckForTraceOverride(v75, v74)
                       || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3);
                    WPP_SF__DS_NAME_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      56361598,
                      2,
                      3,
                      v77,
                      v76,
                      23,
                      &WPP_58eb3ebf6fe43bf462328e8368ddc743_Traceguids,
                      *(_QWORD *)(v5 + 24),
                      v13);
                  }
                }
              }
              else
              {
                v13 = GetLastError();
                if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
                  || (unsigned int)THStateCheckForTraceOverride(v71, v70)
                  || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
                  || gfTraceToSecondProvider
                  && ((unsigned int)THStateCheckForTraceOverride(v71, v70)
                   || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                   && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
                {
                  v72 = gfTraceToSecondProvider
                     && ((unsigned int)THStateCheckForTraceOverride(v71, v70)
                      || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                      && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
                  v73 = (unsigned int)THStateCheckForTraceOverride(v71, v70)
                     || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3);
                  WPP_SF__DS_NAME_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    56361583,
                    2,
                    3,
                    v73,
                    v72,
                    22,
                    &WPP_58eb3ebf6fe43bf462328e8368ddc743_Traceguids,
                    *(_QWORD *)(v5 + 24),
                    v13);
                }
              }
            }
            else
            {
              v13 = 8;
              if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
                || (unsigned int)THStateCheckForTraceOverride(v69, v68)
                || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
                || gfTraceToSecondProvider
                && ((unsigned int)THStateCheckForTraceOverride(v69, v68)
                 || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                 && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
              {
                v16 = gfTraceToSecondProvider
                   && ((unsigned int)THStateCheckForTraceOverride(v69, v68)
                    || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                    && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
                if ( (unsigned int)THStateCheckForTraceOverride(v69, v68)
                  || (v17 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)) != 0 )
                {
                  v17 = 1;
                }
                v85 = 21;
                v18 = 56361568;
                goto LABEL_42;
              }
            }
          }
          else
          {
            v13 = GetLastError();
            if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
              || (unsigned int)THStateCheckForTraceOverride(v64, v63)
              || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
              || gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v64, v63)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier()
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
            {
              v65 = gfTraceToSecondProvider
                 && ((unsigned int)THStateCheckForTraceOverride(v64, v63)
                  || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                  && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
              v66 = (unsigned int)THStateCheckForTraceOverride(v64, v63)
                 || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3);
              WPP_SF__DS_NAME_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                56361552,
                3,
                3,
                v66,
                v65,
                20,
                &WPP_58eb3ebf6fe43bf462328e8368ddc743_Traceguids,
                *(_QWORD *)(v5 + 24),
                v13);
            }
          }
        }
        else
        {
          v13 = GetLastError();
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
            || (unsigned int)THStateCheckForTraceOverride(v60, v59)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v60, v59)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier()
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
          {
            v61 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v60, v59)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
            v62 = (unsigned int)THStateCheckForTraceOverride(v60, v59)
               || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3);
            WPP_SF__DS_NAME_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              56361537,
              3,
              3,
              v62,
              v61,
              19,
              &WPP_58eb3ebf6fe43bf462328e8368ddc743_Traceguids,
              *(_QWORD *)(v5 + 24),
              v13);
          }
        }
      }
      else
      {
        v13 = GetLastError();
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
          || (unsigned int)THStateCheckForTraceOverride(v56, v55)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v56, v55)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
        {
          v57 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v56, v55)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
          v58 = (unsigned int)THStateCheckForTraceOverride(v56, v55)
             || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3);
          WPP_SF__DS_NAME_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56361525,
            3,
            3,
            v58,
            v57,
            18,
            &WPP_58eb3ebf6fe43bf462328e8368ddc743_Traceguids,
            *(_QWORD *)(v5 + 24),
            v13);
        }
      }
    }
    else
    {
      v13 = 87;
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
        || (unsigned int)THStateCheckForTraceOverride(v48, v47)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v48, v47)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
      {
        v49 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v48, v47)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
        if ( (unsigned int)THStateCheckForTraceOverride(v48, v47)
          || (v50 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)) != 0 )
        {
          v50 = 1;
        }
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          56361497,
          3,
          3,
          v50,
          v49,
          16,
          &WPP_58eb3ebf6fe43bf462328e8368ddc743_Traceguids);
      }
    }
  }
  else
  {
    v13 = 8;
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v15, v14)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v15, v14)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      v16 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v15, v14)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( (unsigned int)THStateCheckForTraceOverride(v15, v14)
        || (v17 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)) != 0 )
      {
        v17 = 1;
      }
      v85 = 11;
      v18 = 56361369;
LABEL_42:
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v18,
        2,
        3,
        v17,
        v16,
        v85,
        &WPP_58eb3ebf6fe43bf462328e8368ddc743_Traceguids);
    }
  }
  v78 = NewAcl;
  if ( NewAcl )
    LocalFree(NewAcl);
  for ( i = 0; (unsigned int)i < v3; i = (unsigned int)(i + 1) )
  {
    v78 = (PACL)hMem[i];
    if ( v78 )
      LocalFree(v78);
  }
  if ( v13 )
  {
    v80 = gpDsEventConfig;
    if ( !gpDsEventConfig )
      goto LABEL_298;
    if ( (gpDsEventConfig[1].Internal & 0x8000000000000000uLL) != 0LL
      && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(860, 0)) )
    {
      if ( !(unsigned int)DoLogMsgOverride(2147486744LL) )
        goto LABEL_298;
      v80 = gpDsEventConfig;
    }
    v107 = 0;
    v113 = 0;
    v116 = 0;
    v117 = 0;
    Internal = v80[1].Internal;
    v105 = -2147480552;
    v108 = 0;
    v109 = 1;
    v118 = &v119;
    v119 = 6;
    v120 = *(_QWORD *)(v5 + 24);
    v121 = 5;
    v123 = v13;
    v122 = &v123;
    v104 = 2;
    p_StringSecurityDescriptorLen = 0;
    v111 = 860;
    v110 = 1;
    v114 = 0;
    v115 = 0;
    DoLogEventAndTrace(&v104);
LABEL_298:
    if ( (unsigned int)dword_18050B220 > 5 && (unsigned __int8)tlgKeywordOn(v78, 0x400000000000LL) )
    {
      v95 = 0x1000000;
      v110 = (__int64)&v95;
      v111 = 8;
      StringSecurityDescriptorLen = v13;
      p_StringSecurityDescriptorLen = &StringSecurityDescriptorLen;
      v113 = 4;
      tlgWriteTransfer_EtwEventWriteTransfer(v81, (unsigned int)&byte_1804DD34F, 4, v82, 4, (__int64)&v104);
    }
    FreeSOAPolicy(v5);
    return v13;
  }
  _InterlockedAdd((volatile signed __int32 *)(v5 + 16), 1u);
  v83 = (__int64 *)qword_180E68258;
  if ( *(__int64 **)qword_180E68258 != &gSOAPolicyCacheList )
    __fastfail(3u);
  *(_QWORD *)v5 = &gSOAPolicyCacheList;
  *(_QWORD *)(v5 + 8) = v83;
  *v83 = v5;
  qword_180E68258 = v5;
  ++gSOAPolicyCacheCount;
  StringSecurityDescriptor = 0;
  StringSecurityDescriptorLen = 0;
  ConvertSecurityDescriptorToStringSecurityDescriptorW(
    *(PSECURITY_DESCRIPTOR *)(v5 + 40),
    1u,
    4u,
    &StringSecurityDescriptor,
    &StringSecurityDescriptorLen);
  v84 = gpDsEventConfig;
  if ( gpDsEventConfig )
  {
    if ( (gpDsEventConfig[1].Internal & 0x8000000000000000uLL) == 0LL
      || HIDWORD(gpDsEventConfig->Internal) && (unsigned int)DoLogOverride(860, 0) )
    {
      goto LABEL_310;
    }
    if ( (unsigned int)DoLogMsgOverride(1073744919) )
    {
      v84 = gpDsEventConfig;
LABEL_310:
      v107 = 0;
      v113 = 0;
      v116 = 0;
      v117 = 0;
      Internal = v84[1].Internal;
      v105 = 1073744919;
      v108 = 0;
      v109 = 1;
      v118 = &v119;
      v119 = 6;
      v120 = *(_QWORD *)(v5 + 24);
      v121 = 3;
      v123 = *(unsigned int *)(v5 + 20);
      v122 = &v123;
      v124 = 1;
      v125 = StringSecurityDescriptor;
      v104 = 3;
      p_StringSecurityDescriptorLen = 0;
      v111 = 860;
      v110 = 1;
      v114 = 0;
      v115 = 0;
      DoLogEventAndTrace(&v104);
    }
  }
  LocalFree(StringSecurityDescriptor);
  return v13;
}

```

## disassembly

```asm
0x180157470  mov     [rsp+arg_10], rbx
0x180157475  mov     [rsp+arg_18], rsi
0x18015747a  push    rdi
0x18015747b  push    r12
0x18015747d  push    r13
0x18015747f  push    r14
0x180157481  push    r15
0x180157483  mov     eax, 1190h
0x180157488  call    _alloca_probe
0x18015748d  sub     rsp, rax
0x180157490  mov     rax, cs:__security_cookie
0x180157497  xor     rax, rsp
0x18015749a  mov     [rsp+11B8h+var_38], rax
0x1801574a2  mov     rdi, rdx
0x1801574a5  mov     [rsp+11B8h+var_1108], rdx
0x1801574ad  mov     [rsp+11B8h+var_1130], rcx
0x1801574b5  xor     edx, edx; Val
0x1801574b7  mov     r8d, 0C00h; Size
0x1801574bd  lea     rcx, [rsp+11B8h+pListOfExplicitEntries]; void *
0x1801574c5  call    memset_0
0x1801574ca  xor     edx, edx; Val
0x1801574cc  mov     r8d, 200h; Size
0x1801574d2  lea     rcx, [rsp+11B8h+hMem]; void *
0x1801574da  call    memset_0
0x1801574df  xor     r13d, r13d
0x1801574e2  mov     [rsp+11B8h+NewAcl], r13
0x1801574e7  xorps   xmm0, xmm0
0x1801574ea  xor     eax, eax
0x1801574ec  movups  [rsp+11B8h+pSecurityDescriptor], xmm0
0x1801574f4  movups  [rsp+11B8h+var_10F0], xmm0
0x1801574fc  mov     [rsp+11B8h+var_10E0], rax
0x180157504  movups  xmmword ptr [rsp+11B8h+String1.Length], xmm0
0x18015750c  xorps   xmm1, xmm1
0x18015750f  movups  xmmword ptr [rsp+11B8h+DestinationString.Length], xmm1
0x180157517  movups  xmmword ptr [rsp+11B8h+String2.Length], xmm0
0x18015751f  mov     [rsp+11B8h+dwBufferLength], r13d
0x180157524  mov     edx, 35C0182h
0x180157529  lea     ecx, [rax+30h]
0x18015752c  call    DSAllocAux
0x180157531  mov     r12, rax
0x180157534  test    rax, rax
0x180157537  jnz     loc_180157671
0x18015753d  lea     r15d, [r13+2]
0x180157541  mov     ecx, r15d
0x180157544  call    IncrementWPPPerfCountersForLevel
0x180157549  test    eax, eax
0x18015754b  jnz     short loc_1801575AA
0x18015754d  call    THStateCheckForTraceOverride
0x180157552  test    eax, eax
0x180157554  jnz     short loc_1801575AA
0x180157556  lea     esi, [rax+3]
0x180157559  mov     r8d, esi
0x18015755c  mov     edx, r15d
0x18015755f  xor     ecx, ecx
0x180157561  call    CheckWPPLevelFlagsEnabledForProvider
0x180157566  test    eax, eax
0x180157568  jnz     short loc_1801575AF
0x18015756a  mov     eax, cs:gfTraceToSecondProvider
0x180157570  test    eax, eax
0x180157572  jz      loc_18015763F
0x180157578  call    THStateCheckForTraceOverride
0x18015757d  test    eax, eax
0x18015757f  jnz     short loc_1801575AF
0x180157581  call    ThStateCheckIfTraceToSecondProvier
0x180157586  test    eax, eax
0x180157588  jz      loc_18015763F
0x18015758e  mov     r8d, esi
0x180157591  mov     edx, r15d
0x180157594  lea     r14d, [r13+1]
0x180157598  mov     ecx, r14d
0x18015759b  call    CheckWPPLevelFlagsEnabledForProvider
0x1801575a0  test    eax, eax
0x1801575a2  jz      loc_18015763F
0x1801575a8  jmp     short loc_1801575B5
0x1801575aa  mov     esi, 3
0x1801575af  mov     r14d, 1
0x1801575b5  mov     eax, cs:gfTraceToSecondProvider
0x1801575bb  test    eax, eax
0x1801575bd  jz      short loc_1801575E8
0x1801575bf  call    THStateCheckForTraceOverride
0x1801575c4  test    eax, eax
0x1801575c6  jnz     short loc_1801575E3
0x1801575c8  call    ThStateCheckIfTraceToSecondProvier
0x1801575cd  test    eax, eax
0x1801575cf  jz      short loc_1801575E8
0x1801575d1  mov     r8d, esi
0x1801575d4  mov     edx, r15d
0x1801575d7  mov     ecx, r14d
0x1801575da  call    CheckWPPLevelFlagsEnabledForProvider
0x1801575df  test    eax, eax
0x1801575e1  jz      short loc_1801575E8
0x1801575e3  mov     ebx, r14d
0x1801575e6  jmp     short loc_1801575EB
0x1801575e8  mov     ebx, r13d
0x1801575eb  call    THStateCheckForTraceOverride
0x1801575f0  test    eax, eax
0x1801575f2  jnz     short loc_180157608
0x1801575f4  mov     r8d, esi
0x1801575f7  mov     edx, r15d
0x1801575fa  xor     ecx, ecx
0x1801575fc  call    CheckWPPLevelFlagsEnabledForProvider
0x180157601  test    eax, eax
0x180157603  jnz     short loc_180157608
0x180157605  mov     r14d, r13d
0x180157608  lea     rax, WPP_58eb3ebf6fe43bf462328e8368ddc743_Traceguids
0x18015760f  mov     [rsp+11B8h+var_1180], rax; LPCGUID
0x180157614  mov     [rsp+11B8h+var_1188], 0Ah; __int16
0x18015761b  mov     [rsp+11B8h+var_1190], ebx; int
0x18015761f  mov     dword ptr [rsp+11B8h+StringSecurityDescriptorLen], r14d; int
0x180157624  mov     r9d, esi; int
0x180157627  mov     r8d, r15d; int
0x18015762a  mov     edx, 35C0188h; int
0x18015762f  mov     rcx, cs:WPP_GLOBAL_Control
0x180157636  mov     rcx, [rcx+10h]; int
0x18015763a  call    WPP_SF_
0x18015763f  mov     eax, 8
0x180157644  mov     rcx, [rsp+11B8h+var_38]
0x18015764c  xor     rcx, rsp; StackCookie
0x18015764f  call    __security_check_cookie
0x180157654  lea     r11, [rsp+11B8h+var_28]
0x18015765c  mov     rbx, [r11+40h]
0x180157660  mov     rsi, [r11+48h]
0x180157664  mov     rsp, r11
0x180157667  pop     r15
0x180157669  pop     r14
0x18015766b  pop     r13
0x18015766d  pop     r12
0x18015766f  pop     rdi
0x180157670  retn
0x180157671  mov     [rsp+11B8h+var_1164], r13d
0x180157676  mov     [rsp+11B8h+cCountOfExplicitEntries], r13d
0x18015767b  xorps   xmm0, xmm0
0x18015767e  movups  xmmword ptr [rax], xmm0
0x180157681  movups  xmmword ptr [rax+10h], xmm0
0x180157685  movups  xmmword ptr [rax+20h], xmm0
0x180157689  mov     rax, [rdi+8]
0x18015768d  mov     ebx, [rax]
0x18015768f  mov     edx, 35C0193h
0x180157694  mov     ecx, ebx
0x180157696  call    DSAllocAux
0x18015769b  mov     [r12+18h], rax
0x1801576a0  test    rax, rax
0x1801576a3  jnz     loc_1801577BB
0x1801576a9  lea     ebx, [rax+8]
0x1801576ac  mov     [rsp+11B8h+var_1168], ebx
0x1801576b0  lea     r15d, [rax+2]
0x1801576b4  mov     ecx, r15d
0x1801576b7  call    IncrementWPPPerfCountersForLevel
0x1801576bc  test    eax, eax
0x1801576be  jnz     short loc_180157720
0x1801576c0  call    THStateCheckForTraceOverride
0x1801576c5  test    eax, eax
0x1801576c7  jnz     short loc_180157720
0x1801576c9  lea     esi, [rbx-5]
0x1801576cc  mov     r8d, esi
0x1801576cf  mov     edx, r15d
0x1801576d2  xor     ecx, ecx
0x1801576d4  call    CheckWPPLevelFlagsEnabledForProvider
0x1801576d9  test    eax, eax
0x1801576db  jnz     short loc_180157725
0x1801576dd  mov     eax, cs:gfTraceToSecondProvider
0x1801576e3  test    eax, eax
0x1801576e5  jz      short loc_180157715
0x1801576e7  call    THStateCheckForTraceOverride
0x1801576ec  test    eax, eax
0x1801576ee  jnz     short loc_180157725
0x1801576f0  call    ThStateCheckIfTraceToSecondProvier
0x1801576f5  test    eax, eax
0x1801576f7  jz      short loc_180157715
0x1801576f9  mov     r8d, esi
0x1801576fc  mov     edx, r15d
0x1801576ff  lea     r14d, [rbx-7]
0x180157703  mov     ecx, r14d
0x180157706  call    CheckWPPLevelFlagsEnabledForProvider
0x18015770b  test    eax, eax
0x18015770d  jz      loc_1801586CC
0x180157713  jmp     short loc_18015772B
0x180157715  mov     r14d, 1
0x18015771b  jmp     loc_1801586CC
0x180157720  mov     esi, 3
0x180157725  mov     r14d, 1
0x18015772b  mov     eax, cs:gfTraceToSecondProvider
0x180157731  test    eax, eax
0x180157733  jz      short loc_18015775E
0x180157735  call    THStateCheckForTraceOverride
0x18015773a  test    eax, eax
0x18015773c  jnz     short loc_180157759
0x18015773e  call    ThStateCheckIfTraceToSecondProvier
0x180157743  test    eax, eax
0x180157745  jz      short loc_18015775E
0x180157747  mov     r8d, esi
0x18015774a  mov     edx, r15d
0x18015774d  mov     ecx, r14d
0x180157750  call    CheckWPPLevelFlagsEnabledForProvider
0x180157755  test    eax, eax
0x180157757  jz      short loc_18015775E
0x180157759  mov     edi, r14d
0x18015775c  jmp     short loc_180157760
0x18015775e  xor     edi, edi
0x180157760  call    THStateCheckForTraceOverride
0x180157765  test    eax, eax
0x180157767  jnz     short loc_18015777A
0x180157769  mov     r8d, esi
0x18015776c  mov     edx, r15d
0x18015776f  xor     ecx, ecx
0x180157771  call    CheckWPPLevelFlagsEnabledForProvider
0x180157776  test    eax, eax
0x180157778  jz      short loc_18015777D
0x18015777a  mov     eax, r14d
0x18015777d  mov     edx, 0Bh
0x180157782  lea     rcx, WPP_58eb3ebf6fe43bf462328e8368ddc743_Traceguids
0x180157789  mov     [rsp+11B8h+var_1180], rcx; LPCGUID
0x18015778e  mov     [rsp+11B8h+var_1188], dx; __int16
0x180157793  mov     edx, 35C0199h; int
0x180157798  mov     r8d, r15d; int
0x18015779b  mov     [rsp+11B8h+var_1190], edi; int
0x18015779f  mov     dword ptr [rsp+11B8h+StringSecurityDescriptorLen], eax; int
0x1801577a3  mov     r9d, esi; int
0x1801577a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801577ad  mov     rcx, [rcx+10h]; int
0x1801577b1  call    WPP_SF_
0x1801577b6  jmp     loc_1801586CC
0x1801577bb  mov     r8, rbx; Size
0x1801577be  mov     rdx, [rdi+8]; Src
0x1801577c2  mov     rcx, rax; void *
0x1801577c5  call    memcpy_0
0x1801577ca  xor     r13d, r13d
0x1801577cd  lea     esi, [r13+3]
0x1801577d1  lea     r15d, [r13+2]
0x1801577d5  lea     r14d, [r13+1]
0x1801577d9  mov     [rsp+11B8h+var_114C], r13d
0x1801577de  cmp     r13d, [rdi+18h]
0x1801577e2  jnb     loc_180157E77
0x1801577e8  cmp     [rsp+11B8h+var_1164], 0
0x1801577ed  jnz     loc_180157E77
0x1801577f3  mov     eax, r13d
0x1801577f6  lea     rdi, ds:0[r13*2]
0x1801577fe  add     rdi, r13
0x180157801  shl     rdi, 5
0x180157805  mov     [rsp+11B8h+var_1110], rdi
0x18015780d  mov     rdx, [rsp+11B8h+var_1108]
0x180157815  mov     rdx, [rdx+20h]
0x180157819  mov     [rsp+11B8h+StringSecurityDescriptor], rdx
0x18015781e  cmp     [rdi+rdx], esi
0x180157821  jz      loc_180157D1C
0x180157827  cmp     dword ptr [rdi+rdx], 90030h
0x18015782e  jz      loc_180157B72
0x180157834  cmp     dword ptr [rdi+rdx], 906A1h
0x18015783b  jnz     loc_180157E67
0x180157841  mov     eax, [rdi+rdx+8]
0x180157845  mov     [rsp+11B8h+var_1160], eax
0x180157849  cmp     eax, 40h ; '@'
0x18015784c  jbe     loc_180157941
0x180157852  mov     ecx, esi
0x180157854  call    IncrementWPPPerfCountersForLevel
0x180157859  test    eax, eax
0x18015785b  jnz     short loc_1801578AF
0x18015785d  call    THStateCheckForTraceOverride
0x180157862  test    eax, eax
0x180157864  jnz     short loc_1801578AF
0x180157866  mov     r8d, esi
0x180157869  mov     edx, esi
0x18015786b  xor     ecx, ecx
0x18015786d  call    CheckWPPLevelFlagsEnabledForProvider
0x180157872  test    eax, eax
0x180157874  jnz     short loc_1801578AF
0x180157876  mov     eax, cs:gfTraceToSecondProvider
0x18015787c  test    eax, eax
0x18015787e  jz      loc_180157938
0x180157884  call    THStateCheckForTraceOverride
0x180157889  test    eax, eax
0x18015788b  jnz     short loc_1801578AF
0x18015788d  call    ThStateCheckIfTraceToSecondProvier
0x180157892  test    eax, eax
0x180157894  jz      loc_180157938
0x18015789a  mov     r8d, esi
0x18015789d  mov     edx, esi
0x18015789f  mov     ecx, r14d
0x1801578a2  call    CheckWPPLevelFlagsEnabledForProvider
0x1801578a7  test    eax, eax
0x1801578a9  jz      loc_180157938
0x1801578af  mov     eax, cs:gfTraceToSecondProvider
0x1801578b5  test    eax, eax
0x1801578b7  jz      short loc_1801578E1
0x1801578b9  call    THStateCheckForTraceOverride
0x1801578be  test    eax, eax
0x1801578c0  jnz     short loc_1801578DC
0x1801578c2  call    ThStateCheckIfTraceToSecondProvier
0x1801578c7  test    eax, eax
0x1801578c9  jz      short loc_1801578E1
0x1801578cb  mov     r8d, esi
0x1801578ce  mov     edx, esi
0x1801578d0  mov     ecx, r14d
0x1801578d3  call    CheckWPPLevelFlagsEnabledForProvider
0x1801578d8  test    eax, eax
0x1801578da  jz      short loc_1801578E1
0x1801578dc  mov     ebx, r14d
0x1801578df  jmp     short loc_1801578E3
0x1801578e1  xor     ebx, ebx
0x1801578e3  call    THStateCheckForTraceOverride
  ... truncated ...
```
