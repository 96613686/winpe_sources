# MspIChangePassword

- ea: `0x180033148`
- end: `0x180034697`
- name: `MspIChangePassword`
- size: `5455`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180034720`
- `0x180034f00`

## callees

- `0x180010b14`
- `0x1800205b4`
- `0x180021bbc`
- `0x18002ee7c`
- `0x18002f014`
- `0x18002fb50`
- `0x18002fb90`
- `0x180032c8c`
- `0x180033148`
- `0x1800346a0`
- `0x180034ce4`
- `0x180034ecc`
- `0x18003509c`
- `0x1800350e8`
- `0x1800351b4`
- `0x180035234`
- `0x1800352c8`
- `0x18003544c`
- `0x180035638`
- `0x18003fdec`
- `0x180044b74`
- `0x18006b6b4`
- `0x18006bcf0`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003387d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003387d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180034585`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180034585`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180034656`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180034656`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034660`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsBindWithSpnExW` at `0x18003350c`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsBindWithSpnExW` at `0x180033770`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsBindWithSpnExW` at `0x18003350c`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsBindWithSpnExW` at `0x180033770`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x180033907`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x180033907`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x1800338c5`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180034616`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x1800338c5`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180034616`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x180033463`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x180033be9`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x180034629`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x180033463`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x180033be9`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x180034629`
- `ntdll!RtlEqualDomainName` at `0x180033e29`
- `ntdll!RtlEqualDomainName` at `0x180033e4e`
- `ntdll!RtlEqualDomainName` at `0x180033e29`
- `ntdll!RtlEqualDomainName` at `0x180033e4e`
- `ntdll!RtlReleaseResource` at `0x180033374`
- `ntdll!RtlReleaseResource` at `0x180033374`
- `ntdll!RtlAcquireResourceShared` at `0x18003335a`
- `ntdll!RtlAcquireResourceShared` at `0x18003335a`
- `ntdll!NtSetInformationThread` at `0x180033790`
- `ntdll!NtSetInformationThread` at `0x180033a92`
- `ntdll!NtSetInformationThread` at `0x180033790`
- `ntdll!NtSetInformationThread` at `0x180033a92`
- `ntdll!RtlInitUnicodeString` at `0x1800331ee`
- `ntdll!RtlInitUnicodeString` at `0x180033339`
- `ntdll!RtlInitUnicodeString` at `0x180033c50`
- `ntdll!RtlInitUnicodeString` at `0x180033cac`
- `ntdll!RtlInitUnicodeString` at `0x180033d1c`
- `ntdll!RtlInitUnicodeString` at `0x180033d32`
- `ntdll!RtlInitUnicodeString` at `0x180033d48`
- `ntdll!RtlInitUnicodeString` at `0x180033d7b`
- `ntdll!RtlInitUnicodeString` at `0x18003403c`
- `ntdll!RtlInitUnicodeString` at `0x180034245`
- `ntdll!RtlInitUnicodeString` at `0x180034422`
- `ntdll!RtlInitUnicodeString` at `0x1800331ee`
- `ntdll!RtlInitUnicodeString` at `0x180033339`
- `ntdll!RtlInitUnicodeString` at `0x180033c50`
- `ntdll!RtlInitUnicodeString` at `0x180033cac`
- `ntdll!RtlInitUnicodeString` at `0x180033d1c`
- `ntdll!RtlInitUnicodeString` at `0x180033d32`
- `ntdll!RtlInitUnicodeString` at `0x180033d48`
- `ntdll!RtlInitUnicodeString` at `0x180033d7b`
- `ntdll!RtlInitUnicodeString` at `0x18003403c`
- `ntdll!RtlInitUnicodeString` at `0x180034245`
- `ntdll!RtlInitUnicodeString` at `0x180034422`
- `netutils!NetApiBufferFree` at `0x1800333f1`
- `netutils!NetApiBufferFree` at `0x18003380b`
- `netutils!NetApiBufferFree` at `0x1800339cf`
- `netutils!NetApiBufferFree` at `0x180033c09`
- `netutils!NetApiBufferFree` at `0x1800340a7`
- `netutils!NetApiBufferFree` at `0x1800342a4`
- `netutils!NetApiBufferFree` at `0x1800343df`
- `netutils!NetApiBufferFree` at `0x180034604`
- `netutils!NetApiBufferFree` at `0x1800333f1`
- `netutils!NetApiBufferFree` at `0x18003380b`
- `netutils!NetApiBufferFree` at `0x1800339cf`
- `netutils!NetApiBufferFree` at `0x180033c09`
- `netutils!NetApiBufferFree` at `0x1800340a7`
- `netutils!NetApiBufferFree` at `0x1800342a4`
- `netutils!NetApiBufferFree` at `0x1800343df`
- `netutils!NetApiBufferFree` at `0x180034604`
- `logoncli!DsGetDcNameW` at `0x18003343f`
- `logoncli!DsGetDcNameW` at `0x180033863`
- `logoncli!DsGetDcNameW` at `0x1800339f6`
- `logoncli!DsGetDcNameW` at `0x180033fee`
- `logoncli!DsGetDcNameW` at `0x1800340d4`
- `logoncli!DsGetDcNameW` at `0x18003440b`
- `logoncli!DsGetDcNameW` at `0x18003343f`
- `logoncli!DsGetDcNameW` at `0x180033863`
- `logoncli!DsGetDcNameW` at `0x1800339f6`
- `logoncli!DsGetDcNameW` at `0x180033fee`
- `logoncli!DsGetDcNameW` at `0x1800340d4`
- `logoncli!DsGetDcNameW` at `0x18003440b`
- `LSASRV!LsaINotifyPasswordChanged` at `0x180034578`
- `LSASRV!LsaINotifyPasswordChanged` at `0x180034578`

## string_xrefs

- `0x18003322a`: `Attempting password change server/domain %wZ for user %wZ\n`
- `0x180033285`: ` (cached)`

## pseudocode

```c
__int64 __fastcall MspIChangePassword(
        int a1,
        __m128i *a2,
        unsigned __int16 *a3,
        __int64 a4,
        __int64 a5,
        char a6,
        __int64 a7,
        __int64 a8)
{
  int v8; // edi
  int v10; // r15d
  __int64 v11; // r14
  char *p_Buffer; // r12
  PWSTR v14; // rdx
  __int64 v15; // rcx
  const char *v16; // rdx
  const char *v17; // rax
  __int64 v18; // r8
  struct _UNICODE_STRING v19; // xmm1
  int v20; // esi
  struct _UNICODE_STRING v21; // xmm0
  unsigned __int16 v22; // ax
  size_t v23; // rsi
  unsigned __int64 v24; // rsi
  bool v25; // bl
  _QWORD *v26; // rcx
  char v27; // bl
  WCHAR *v28; // r14
  const WCHAR *pDomain; // r15
  ULONG v30; // r13d
  DWORD v31; // eax
  __int64 v32; // rdx
  DWORD v33; // ebx
  int v34; // eax
  __int64 v35; // rcx
  int v36; // eax
  const WCHAR *v37; // rbx
  const WCHAR *v38; // rdx
  DWORD v39; // ebx
  int v40; // ecx
  unsigned __int64 v41; // rax
  __int64 v42; // rcx
  unsigned __int64 v43; // rax
  int v44; // ecx
  int v45; // ecx
  int v46; // edx
  int v47; // r8d
  const WCHAR *v48; // rdx
  NTSTATUS v49; // eax
  DWORD v50; // eax
  __int64 v51; // rdx
  __int64 v52; // r8
  DWORD v53; // esi
  unsigned int v54; // r8d
  DWORD v55; // eax
  PDS_NAME_RESULT_ITEMW rItems; // rax
  __int64 status; // r9
  PDS_NAME_RESULT_ITEMW v58; // rdx
  DWORD v59; // eax
  __int64 v60; // rdx
  __int64 v61; // rdx
  __int64 v62; // rbx
  bool v63; // zf
  int v64; // ecx
  int v65; // ebx
  __int64 v66; // rcx
  int v67; // eax
  char v68; // bl
  BOOLEAN v69; // al
  BOOLEAN v70; // al
  USHORT Length; // ax
  struct _UNICODE_STRING *p_DomainName2; // r14
  struct _UNICODE_STRING v73; // xmm0
  USHORT v74; // ax
  unsigned __int64 v75; // rbx
  unsigned __int64 v76; // rcx
  int v77; // eax
  __int64 v78; // rcx
  unsigned __int64 v79; // rcx
  void *v80; // rsp
  void *v81; // rsp
  char *v82; // rax
  unsigned __int64 v83; // rcx
  DWORD DcNameW; // eax
  __int64 v85; // rdx
  __int64 v86; // r8
  DWORD v87; // ebx
  int v88; // eax
  DWORD v89; // eax
  __int64 v90; // rdx
  __int64 v91; // r8
  DWORD v92; // ebx
  char v93; // bl
  int v94; // eax
  int HasCacheForPassword; // edi
  char v96; // bl
  int v97; // eax
  struct _UNICODE_STRING *v98; // rdi
  unsigned __int64 v99; // rbx
  unsigned __int64 v100; // rcx
  int v101; // eax
  __int64 v102; // rcx
  unsigned __int64 v103; // rcx
  void *v104; // rsp
  void *v105; // rsp
  char *v106; // rax
  unsigned __int8 v107; // r14
  DWORD v108; // eax
  __int64 v109; // rdx
  __int64 v110; // r8
  DWORD v111; // ebx
  int v112; // eax
  __int64 v113; // rdi
  int v114; // eax
  __int64 v115; // rcx
  bool v116; // bl
  __int64 v117; // rdx
  _BYTE v119[32]; // [rsp+0h] [rbp-50h] BYREF
  ULONG Flags[2]; // [rsp+20h] [rbp-30h]
  PDOMAIN_CONTROLLER_INFOW *DomainControllerInfo; // [rsp+28h] [rbp-28h]
  __int64 v122; // [rsp+38h] [rbp-18h]
  DWORD v123; // [rsp+50h] [rbp+0h] BYREF
  LPVOID Buffer; // [rsp+58h] [rbp+8h] BYREF
  LPCWSTR ServicePrincipalName; // [rsp+60h] [rbp+10h]
  int v126[2]; // [rsp+68h] [rbp+18h]
  HANDLE phDS[2]; // [rsp+70h] [rbp+20h] BYREF
  struct _UNICODE_STRING DomainName2; // [rsp+80h] [rbp+30h] BYREF
  struct _UNICODE_STRING v129; // [rsp+90h] [rbp+40h] BYREF
  DS_NAME_RESULTW *pResult; // [rsp+A0h] [rbp+50h] BYREF
  int v131[2]; // [rsp+A8h] [rbp+58h]
  struct _UNICODE_STRING v132; // [rsp+B0h] [rbp+60h] BYREF
  __int64 v133; // [rsp+C0h] [rbp+70h]
  struct _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp+78h] BYREF
  unsigned int v135; // [rsp+D8h] [rbp+88h]
  int v136; // [rsp+E0h] [rbp+90h]
  __int64 v137; // [rsp+E8h] [rbp+98h]
  __int64 ThreadInformation; // [rsp+F0h] [rbp+A0h] BYREF
  struct _UNICODE_STRING v139; // [rsp+F8h] [rbp+A8h] BYREF
  WCHAR SourceString[264]; // [rsp+110h] [rbp+C0h] BYREF

  v8 = 0;
  *(_QWORD *)v131 = a5;
  v133 = a7;
  v10 = a1;
  v136 = a1;
  v137 = a8;
  v11 = a4;
  *(_QWORD *)v126 = a4;
  Buffer = 0;
  DestinationString = 0;
  pResult = 0;
  p_Buffer = 0;
  DomainName2 = 0;
  phDS[0] = 0;
  v132 = 0;
  ServicePrincipalName = 0;
  v139 = 0;
  LOBYTE(v123) = 1;
  v129 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  v14 = (PWSTR)a2->m128i_u16[0];
  if ( ((unsigned __int16)v14 & 0xFFFEu) > 0x1FE || (*a3 & 0xFFFEu) > 0x400 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids,
        a2->m128i_u16[0],
        *a3);
    v18 = 0;
    goto LABEL_339;
  }
  MsvPaswdLogPrintRoutine("Attempting password change server/domain %wZ for user %wZ\n", a2, a3);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
  {
    v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v16 = "true";
    if ( !a6 )
      v16 = "false";
    v122 = (__int64)v16;
    v17 = " (cached)";
    if ( v10 != 6 )
      v17 = byte_180072560;
    WPP_SF_ZZDss(v15, (_DWORD)v16, (unsigned int)byte_180072560, (_DWORD)a2, (__int64)a3, v10, (__int64)v17, v122);
  }
  v18 = 0;
  if ( v10 == 6 )
  {
    v19 = (struct _UNICODE_STRING)*a2;
    v20 = 0;
    v21 = *(struct _UNICODE_STRING *)a3;
    DomainName2 = v19;
    v129 = v21;
LABEL_275:
    if ( v11 && NtLmGlobalPasswordChangeHardening && v10 == 5 )
    {
      LOBYTE(v123) = 0;
      HasCacheForPassword = NlpHasCacheForPassword(&DomainName2, &v129);
      v96 = v123;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids,
          (unsigned __int8)v123);
      v18 = 0;
      if ( HasCacheForPassword >= 0 && !v96 )
      {
        v8 = -1073740920;
        goto LABEL_332;
      }
    }
    v113 = *(_QWORD *)v131;
    v114 = NlpChangePassword(1, &DomainName2, &v129, *(_QWORD *)v131, v11);
    v18 = 0;
    if ( v114 < 0 && v10 == 6 )
    {
      v8 = -1073741727;
      if ( v114 == -1073741727 )
        goto LABEL_332;
      v113 = *(_QWORD *)v131;
      v20 = v114;
    }
    v116 = 0;
    if ( a6 )
      v116 = (int)((__int64 (__fastcall *)(__int64, PWSTR, _QWORD))qword_180088268)(v115, v14, 0) >= 0;
    v117 = 0;
    LOBYTE(v122) = v116;
    if ( v10 != 6 )
      v117 = v11;
    LsaINotifyPasswordChanged(
      0,
      &DomainName2,
      &v129,
      (unsigned __int64)&v132 & -(__int64)(v132.Length != 0),
      (unsigned __int64)&v139 & -(__int64)(v139.Length != 0),
      v117,
      v113,
      v122);
    v18 = 0;
    if ( v116 )
    {
      RevertToSelf();
      v18 = 0;
    }
LABEL_331:
    v8 = v20;
LABEL_332:
    if ( !p_Buffer )
      goto LABEL_225;
    goto LABEL_333;
  }
  if ( a2->m128i_i16[0] )
  {
    v73 = *(struct _UNICODE_STRING *)a3;
    v74 = _mm_cvtsi128_si32(*a2);
    DomainName2 = (struct _UNICODE_STRING)*a2;
    v129 = v73;
    DomainName2.Length = v74;
LABEL_209:
    if ( !NlpSamInitialized )
    {
      v67 = NlSamInitialize();
      v18 = 0;
      v8 = v67;
      if ( v67 < 0 )
        goto LABEL_225;
    }
    v20 = -1073741601;
    v68 = 0;
    if ( DomainName2.Length < 6u || *DomainName2.Buffer != 92 && DomainName2.Buffer[1] != 92 )
    {
      v69 = RtlEqualDomainName(&NlpComputerName, &DomainName2);
      v18 = 0;
      if ( !v69 )
      {
        if ( !NlpWorkstation )
        {
          v70 = RtlEqualDomainName(&NlpSamDomainName, &DomainName2);
          v18 = 0;
          if ( v70 )
            DestinationString = NlpComputerName;
        }
        if ( !DestinationString.Buffer )
        {
          Length = v132.Length;
          if ( v132.Length )
          {
            p_DomainName2 = &v132;
          }
          else
          {
            Length = DomainName2.Length;
            p_DomainName2 = &DomainName2;
          }
          p_Buffer = 0;
          v75 = Length + 2LL;
          if ( v75 > g_ulMaxStackAllocSize )
            goto LABEL_355;
          v76 = v75 + g_ulAdditionalProbeSize + 8;
          if ( v76 < v75 )
            goto LABEL_355;
          v77 = VerifyStackAvailable(v76, v14, 0);
          v18 = 0;
          if ( !v77 )
            goto LABEL_355;
          v78 = v75 + 23;
          if ( v75 + 23 <= v75 + 8 )
            v78 = 0xFFFFFFFFFFFFFF0LL;
          v79 = v78 & 0xFFFFFFFFFFFFFFF0uLL;
          v80 = alloca(v79);
          v81 = alloca(v79);
          p_Buffer = (char *)&v123;
          if ( v119 == (_BYTE *)-80LL || (v123 = 1801679955, (p_Buffer = (char *)&Buffer) == 0) )
          {
LABEL_355:
            if ( v75 + 8 >= v75 )
            {
              v82 = (char *)((__int64 (__fastcall *)(unsigned __int64, PWSTR, _QWORD))g_pfnAllocate)(v75 + 8, v14, 0);
              v18 = 0;
              p_Buffer = v82;
              if ( v82 )
              {
                *(_DWORD *)v82 = 1885431112;
                p_Buffer = v82 + 8;
              }
            }
          }
          if ( !p_Buffer )
            goto LABEL_242;
          memcpy_0(p_Buffer, p_DomainName2->Buffer, p_DomainName2->Length);
          v83 = (unsigned __int64)p_DomainName2->Length >> 1;
          DomainControllerInfo = (PDOMAIN_CONTROLLER_INFOW *)&Buffer;
          Flags[0] = 4096;
          *(_WORD *)&p_Buffer[2 * v83] = 0;
          DcNameW = DsGetDcNameW(0, (LPCWSTR)p_Buffer, 0, 0, Flags[0], DomainControllerInfo);
          v87 = DcNameW;
          if ( DcNameW )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, v86, (_DWORD)p_Buffer, DcNameW);
            v8 = NetpApiStatusToNtStatus(v87, v85, v86);
            if ( v8 == -1073741595 )
              v8 = -1073741601;
          }
          else
          {
            RtlInitUnicodeString(&DestinationString, *(PCWSTR *)Buffer);
          }
          v68 = 1;
          v18 = 0;
        }
        v11 = *(_QWORD *)v126;
        if ( v8 >= 0 )
        {
          v88 = MspChangePassword(
                  (int)&DestinationString,
                  (int)&v129,
                  v126[0],
                  v131[0],
                  Flags[0],
                  a6,
                  v133,
                  0,
                  (DWORD)&v123);
          v18 = 0;
          v8 = v88;
          if ( v88 >= 0 )
            goto LABEL_273;
          if ( (_BYTE)v123 )
          {
            v20 = v88;
            goto LABEL_331;
          }
        }
      }
    }
    if ( Buffer )
    {
      NetApiBufferFree(Buffer);
      v18 = 0;
      Buffer = 0;
    }
    if ( v68 )
    {
      v89 = DsGetDcNameW(0, (LPCWSTR)p_Buffer, 0, 0, 0x1001u, (PDOMAIN_CONTROLLER_INFOW *)&Buffer);
      v92 = v89;
      if ( !v89 )
      {
        RtlInitUnicodeString(&DestinationString, *(PCWSTR *)Buffer);
        v93 = a6;
        v97 = MspChangePassword((int)&DestinationString, (int)&v129, v11, v131[0], Flags[0], a6, v133, 0, (DWORD)&v123);
        v18 = 0;
        v8 = v97;
        if ( v97 >= 0 || (_BYTE)v123 )
          goto LABEL_273;
        if ( Buffer )
        {
          NetApiBufferFree(Buffer);
          v18 = 0;
          Buffer = 0;
        }
        goto LABEL_267;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, v91, (_DWORD)p_Buffer, v89);
      Buffer = 0;
      v8 = NetpApiStatusToNtStatus(v92, v90, v91);
      if ( v8 == -1073741595 )
        v8 = -1073741601;
      v18 = 0;
    }
    v93 = a6;
LABEL_267:
    if ( v8 == -1073741433 )
      goto LABEL_356;
    v94 = MspChangePassword((int)&DomainName2, (int)&v129, v11, v131[0], Flags[0], v93, v133, v137, (DWORD)&v123);
    v18 = 0;
    v8 = v94;
    if ( (_BYTE)v123 && v94 == -1073741634 )
    {
      if ( DomainName2.Length >= 6u && *DomainName2.Buffer == 92 && DomainName2.Buffer[1] == 92 )
        goto LABEL_331;
      goto LABEL_273;
    }
    if ( v94 == -1073741433 )
    {
LABEL_356:
      if ( *(_QWORD *)v137 )
      {
        v98 = &v132;
        if ( !v132.Length )
          v98 = &DomainName2;
        DomainName2 = *(struct _UNICODE_STRING *)*(_QWORD *)v137;
        if ( p_Buffer && *((_DWORD *)p_Buffer - 2) == 1885431112 )
        {
          ((void (__fastcall *)(char *, PWSTR, _QWORD))g_pfnFree)(p_Buffer - 8, v14, 0);
          v18 = 0;
        }
        p_Buffer = 0;
        v99 = v98->Length + 2LL;
        if ( v99 > g_ulMaxStackAllocSize )
          goto LABEL_357;
        v100 = v99 + g_ulAdditionalProbeSize + 8;
        if ( v100 < v99 )
          goto LABEL_357;
        v101 = VerifyStackAvailable(v100, v14, 0);
        v18 = 0;
        if ( !v101 )
          goto LABEL_357;
        v102 = v99 + 23;
        if ( v99 + 23 <= v99 + 8 )
          v102 = 0xFFFFFFFFFFFFFF0LL;
        v103 = v102 & 0xFFFFFFFFFFFFFFF0uLL;
        v104 = alloca(v103);
        v105 = alloca(v103);
        p_Buffer = (char *)&v123;
        if ( v119 == (_BYTE *)-80LL || (v123 = 1801679955, (p_Buffer = (char *)&Buffer) == 0) )
        {
LABEL_357:
          if ( v99 + 8 >= v99 )
          {
            v106 = (char *)((__int64 (__fastcall *)(unsigned __int64, PWSTR, _QWORD))g_pfnAllocate)(v99 + 8, v14, 0);
            v18 = 0;
            p_Buffer = v106;
            if ( v106 )
            {
              *(_DWORD *)v106 = 1885431112;
              p_Buffer = v106 + 8;
            }
          }
        }
        if ( p_Buffer )
        {
          memcpy_0(p_Buffer, v98->Buffer, v98->Length);
          v107 = 0;
          *(_WORD *)&p_Buffer[2 * ((unsigned __int64)v98->Length >> 1)] = 0;
          while ( 1 )
          {
            if ( Buffer )
            {
              NetApiBufferFree(Buffer);
              Buffer = 0;
            }
            v108 = DsGetDcNameW(0, (LPCWSTR)p_Buffer, 0, 0, v107 | 0x1000, (PDOMAIN_CONTROLLER_INFOW *)&Buffer);
            v111 = v108;
            if ( v108 )
              break;
            RtlInitUnicodeString(&DestinationString, *(PCWSTR *)Buffer);
            v112 = MspChangePassword(
                     (int)&DestinationString,
                     (int)&v129,
                     v126[0],
                     v131[0],
                     Flags[0],
                     a6,
                     v133,
                     0,
                     (DWORD)&v123);
            v18 = 0;
            v8 = v112;
            if ( v112 >= 0 || (_BYTE)v123 || v107 )
            {
              v11 = *(_QWORD *)v126;
              goto LABEL_273;
            }
            v107 = 1;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_SDD(*((_QWORD *)WPP_GLOBAL_Control + 2), v109, v110, (_DWORD)p_Buffer, v107, v108);
          v8 = NetpApiStatusToNtStatus(v111, v109, v110);
          if ( v8 == -1073741595 )
            v8 = -1073741601;
          v18 = 0;
LABEL_333:
          if ( *((_DWORD *)p_Buffer - 2) != 1885431112 )
            goto LABEL_225;
          ((void (__fastcall *)(char *, PWSTR, _QWORD))g_pfnFree)(p_Buffer - 8, v14, 0);
          goto LABEL_147;
        }
LABEL_242:
        v8 = -1073741670;
        goto LABEL_225;
      }
    }
LABEL_273:
    v20 = v8;
    if ( v8 < 0 )
      goto LABEL_331;
    v10 = v136;
    goto LABEL_275;
  }
  v22 = *a3 & 0xFFFE;
  ThreadInformation = 0;
  if ( v22 > 0x200u )
  {
    p_Buffer = (char *)ServicePrincipalName;
LABEL_339:
    v8 = -1073741811;
    goto LABEL_340;
  }
  v23 = *a3;
  memcpy_0(SourceString, *((const void **)a3 + 1), v23);
  v24 = v23 & 0xFFFFFFFFFFFFFFFEuLL;
  if ( v24 >= 0x202 )
    _report_rangecheckfailure();
  *(WCHAR *)((char *)SourceString + v24) = 0;
  RtlInitUnicodeString(&v139, SourceString);
  LODWORD(v18) = 0;
  if ( NlpWorkstation )
  {
    RtlAcquireResourceShared(&NtLmGlobalCritSect, 1u);
    v25 = NtLmGlobalTargetFlags == 0x20000;
    RtlReleaseResource(&NtLmGlobalCritSect);
    LODWORD(v18) = 0;
    if ( v25 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids);
        v26 = WPP_GLOBAL_Control;
      }
      v27 = 1;
LABEL_176:
      if ( phDS[0] )
      {
        DsUnBindW(phDS);
        v26 = WPP_GLOBAL_Control;
        phDS[0] = 0;
      }
      if ( Buffer )
      {
        NetApiBufferFree(Buffer);
        v26 = WPP_GLOBAL_Control;
        Buffer = 0;
      }
      if ( v27 )
      {
        if ( v26 != &WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 2) != 0 )
          WPP_SF_(v26[2], 63, WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids);
        RtlInitUnicodeString(&v129, SourceString);
        if ( v129.Length < 6u )
        {
          v8 = -1073741724;
LABEL_147:
          p_Buffer = (char *)ServicePrincipalName;
          v18 = 0;
          goto LABEL_340;
        }
        v62 = (v129.Length >> 1) - 1;
        if ( v129.Length >> 1 == 1 )
        {
LABEL_190:
          v18 = 0;
        }
        else
        {
          v14 = v129.Buffer;
          while ( v129.Buffer[v62] != 64 )
          {
            v63 = (_DWORD)v62 == 1;
            v62 = (unsigned int)(v62 - 1);
            if ( v63 )
              goto LABEL_190;
          }
          RtlInitUnicodeString(&v132, &v129.Buffer[(unsigned int)(v62 + 1)]);
          v18 = 0;
          v129.Buffer[v62] = 0;
          v129.Length = 2 * v62;
        }
        if ( !v132.Length )
        {
          v8 = -1073741724;
          goto LABEL_225;
        }
        v64 = 0;
        v14 = (PWSTR)(v132.Length >> 1);
        DomainName2 = v132;
        if ( !(v132.Length >> 1) )
          goto LABEL_206;
        while ( v132.Buffer[v64] != 46 )
        {
          if ( ++v64 >= (unsigned int)v14 )
            goto LABEL_205;
        }
        DomainName2.Length = 2 * v64;
        DomainName2.MaximumLength = 2 * v64;
      }
      else
      {
        RtlInitUnicodeString(&v132, pResult->rItems->pDomain);
        RtlInitUnicodeString(&v129, pResult->rItems->pName);
        RtlInitUnicodeString(&DomainName2, pResult->rItems->pName);
        v65 = 0;
        if ( v129.Length >> 1 )
        {
          v14 = v129.Buffer;
          while ( 1 )
          {
            v66 = (unsigned int)(v65 + 1);
            if ( v129.Buffer[v65] == 92 )
              break;
            ++v65;
            if ( (unsigned int)v66 >= v129.Length >> 1 )
              goto LABEL_205;
          }
          RtlInitUnicodeString(&v129, &v129.Buffer[v66]);
          DomainName2.Length = 2 * v65;
        }
      }
LABEL_205:
      v18 = 0;
LABEL_206:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      {
        WPP_SF_ZZZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          64,
          (unsigned int)WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids,
          (unsigned int)&DomainName2,
          (__int64)&v129,
          (__int64)&v132);
        v18 = 0;
      }
      goto LABEL_209;
    }
  }
  v26 = WPP_GLOBAL_Control;
  v28 = 0;
  pDomain = 0;
  v135 = 0;
  v30 = 1073741840;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( !v28 )
      {
        if ( Buffer )
        {
          NetApiBufferFree(Buffer);
          v26 = WPP_GLOBAL_Control;
          Buffer = 0;
        }
        if ( v26 != &WPP_GLOBAL_Control && (*((_DWORD *)v26 + 7) & 0x1000) != 0 )
          WPP_SF_SD(v26[2], 49, v18, (_DWORD)pDomain, v30);
        v31 = DsGetDcNameW(0, pDomain, 0, 0, v30, (PDOMAIN_CONTROLLER_INFOW *)&Buffer);
        v33 = v31;
        if ( v31 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, 0, (_DWORD)pDomain, v31);
            v26 = WPP_GLOBAL_Control;
          }
          if ( !pDomain && !NlpWorkstation )
          {
            v8 = NetpApiStatusToNtStatus(v33, v32, 0);
            if ( v8 == -1073741595 )
              v8 = -1073741601;
            goto LABEL_147;
          }
          goto LABEL_145;
        }
        v28 = *(WCHAR **)Buffer;
      }
      if ( phDS[0] )
      {
        DsUnBindW(phDS);
        phDS[0] = 0;
      }
      if ( ServicePrincipalName )
      {
        ((void (*)(void))LsaFunctions->FreePrivateHeap)();
        ServicePrincipalName = 0;
      }
      v34 = MspConstructSPN(v28);
      v18 = 0;
      v8 = v34;
      if ( v34 < 0 )
        goto LABEL_225;
      v36 = MspImpersonateNetworkService(v35, v14, 0);
      v18 = 0;
      v8 = v36;
      if ( v36 < 0 )
        goto LABEL_225;
      v37 = ServicePrincipalName;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)v14, 0, (_DWORD)v28, (__int64)ServicePrincipalName);
      v38 = 0;
      DomainControllerInfo = (PDOMAIN_CONTROLLER_INFOW *)phDS;
      Flags[0] = 0;
      if ( !v28 )
        v38 = pDomain;
      v39 = DsBindWithSpnExW(v28, v38, 0, v37, Flags[0], (HANDLE *)DomainControllerInfo);
      v40 = 1342177285;
      if ( v39 - 1907 <= 0x1E && _bittest(&v40, v39 - 1907)
        || v39 + 2147022989 <= 0x1E && _bittest(&v40, v39 + 2147022989)
        || v39 == -1073740781
        || v39 == -805305325
        || (v41 = v39 - 1272, v42 = 0xCC0210000000001LL, (unsigned int)v41 <= 0x3B) && _bittest64(&v42, v41)
        || (v43 = v39 + 2147023624, (unsigned int)v43 <= 0x3B) && _bittest64(&v42, v43)
        || (v44 = 837665, v39 + 1073741729 <= 0x13) && _bittest(&v44, v39 + 1073741729)
        || v39 + 805306273 <= 0x13 && _bittest(&v44, v39 + 805306273)
        || v39 == -1073741260
        || v39 == -805305804
        || v39 == 1793
        || v39 == -2147023103
        || v39 == -1073741421
        || v39 == -805305965
        || v39 == 1385
        || v39 == -2147023511
        || v39 == -1073741477
        || v39 == -805306021
        || v39 + 1067646974 <= 8 && (v45 = 279, _bittest(&v45, v39 + 1067646974))
        || v39 == -799211518
        || v39 == -799211514
        || v39 == 5
        || v39 == -2147024891
        || v39 == -1073741790
        || v39 == -805306334
        || v39 == 86
        || v39 == -2147024810
        || v39 == -2146893042
        || v39 == -2146893044
        || v39 == -2146892959
        || v39 == -1073740755
        || v39 == 1265
        || v39 == -2147023631
        || v39 == -1073740920
        || v39 == -805305464
        || v39 == -2146892976
        || v39 == -1073741276
        || v39 == -805305820
        || v39 == 2242
        || v39 == -2147022654 )
      {
        if ( a6 )
        {
          v8 = LsaFunctions->ImpersonateClient();
          if ( v8 < 0 )
          {
            NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
            goto LABEL_147;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
          {
            WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v46, v47, v39, (__int64)v28, (__int64)ServicePrincipalName);
          }
          DomainControllerInfo = (PDOMAIN_CONTROLLER_INFOW *)phDS;
          v48 = 0;
          Flags[0] = 0;
          if ( !v28 )
            v48 = pDomain;
          v39 = DsBindWithSpnExW(v28, v48, 0, ServicePrincipalName, Flags[0], (HANDLE *)DomainControllerInfo);
        }
      }
      v49 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
      v18 = 0;
      v8 = v49;
      if ( v49 < 0 )
        goto LABEL_225;
      if ( !v39 )
        break;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids, v39);
        v26 = WPP_GLOBAL_Control;
        v18 = 0;
      }
      if ( v39 != 1717 && v39 != 1722 && v39 != 1753 && v39 != 1759 && v39 != 1820 )
        goto LABEL_158;
      if ( Buffer )
      {
        NetApiBufferFree(Buffer);
        v26 = WPP_GLOBAL_Control;
        Buffer = 0;
      }
      if ( v26 != &WPP_GLOBAL_Control && (*((_DWORD *)v26 + 7) & 0x1000) != 0 )
        WPP_SF_SD(v26[2], 54, v18, (_DWORD)pDomain, v30 | 1);
      v50 = DsGetDcNameW(0, pDomain, 0, 0, v30 | 1, (PDOMAIN_CONTROLLER_INFOW *)&Buffer);
      v53 = v50;
      if ( v50 )
      {
        v39 = NetpApiStatusToNtStatus(v50, v51, v52);
        if ( v39 == -1073741595 )
          v39 = -1073741601;
LABEL_153:
        v26 = WPP_GLOBAL_Control;
LABEL_154:
        if ( v26 != &WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 2) != 0 )
        {
          WPP_SF_d(v26[2], 56, WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids, v53);
          v26 = WPP_GLOBAL_Control;
        }
LABEL_157:
        v18 = 0;
LABEL_158:
        if ( !pDomain && !NlpWorkstation )
        {
          if ( v26 != &WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 1) != 0 )
          {
            v60 = 57;
            goto LABEL_163;
          }
          goto LABEL_164;
        }
LABEL_145:
        v27 = 1;
LABEL_175:
        v11 = *(_QWORD *)v126;
        goto LABEL_176;
      }
      if ( !(unsigned int)_o__wcsicmp(v28, *(_QWORD *)Buffer) )
        goto LABEL_153;
      v26 = WPP_GLOBAL_Control;
      v54 = v135 + 1;
      v135 = v54;
      if ( v54 > 2 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids, v54);
            goto LABEL_153;
          }
          goto LABEL_154;
        }
        goto LABEL_157;
      }
      LODWORD(v18) = 0;
      v28 = *(WCHAR **)Buffer;
    }
    if ( pResult )
    {
      DsFreeNameResultW(pResult);
      pResult = 0;
    }
    v55 = DsCrackNamesW(
            phDS[0],
            pDomain == 0 ? DS_NAME_FLAG_TRUST_REFERRAL : DS_NAME_NO_FLAGS,
            DS_UNKNOWN_NAME,
            DS_NT4_ACCOUNT_NAME,
            1u,
            (const LPCWSTR *)&v139.Buffer,
            &pResult);
    v18 = 0;
    v39 = v55;
    if ( v55 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v60 = 58;
LABEL_163:
        WPP_SF_d(v26[2], v60, WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids, v39);
      }
LABEL_164:
      v8 = MspMapNtdsApiError(v39, 3221225695LL, v18);
      goto LABEL_147;
    }
    if ( pResult->cItems != 1 )
      break;
    rItems = pResult->rItems;
    status = rItems->status;
    if ( (_DWORD)status != 2 && (_DWORD)status != 5 )
    {
      if ( pDomain || (_DWORD)status != 7 )
      {
        v27 = 0;
        if ( !(_DWORD)status )
        {
          v26 = WPP_GLOBAL_Control;
          goto LABEL_175;
        }
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v61 = 62;
          goto LABEL_173;
        }
        goto LABEL_174;
      }
      pDomain = rItems->pDomain;
      v28 = 0;
      v30 = 1073741904;
      goto LABEL_136;
    }
    if ( Buffer )
    {
      if ( (*((_BYTE *)Buffer + 56) & 4) == 0 )
      {
        NetApiBufferFree(Buffer);
        Buffer = 0;
        goto LABEL_134;
      }
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids, status);
        v26 = WPP_GLOBAL_Control;
        LODWORD(v18) = 0;
      }
      if ( pDomain )
        goto LABEL_174;
      v58 = pResult->rItems;
      if ( v58->status != 5 )
        goto LABEL_174;
      pDomain = v58->pDomain;
      v28 = 0;
      v30 = 1073741904;
    }
    else
    {
LABEL_134:
      v30 |= 0x40u;
      v59 = DsGetDcNameW(0, pDomain, 0, 0, v30, (PDOMAIN_CONTROLLER_INFOW *)&Buffer);
      LODWORD(v18) = 0;
      if ( v59 )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v61 = 61;
          status = v59;
LABEL_173:
          WPP_SF_d(v26[2], v61, WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids, status);
          v26 = WPP_GLOBAL_Control;
        }
LABEL_174:
        v27 = 1;
        goto LABEL_175;
      }
      v28 = *(WCHAR **)Buffer;
LABEL_136:
      v26 = WPP_GLOBAL_Control;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids);
    v18 = 0;
  }
  v8 = -1073741595;
LABEL_225:
  p_Buffer = (char *)ServicePrincipalName;
LABEL_340:
  if ( Buffer )
  {
    NetApiBufferFree(Buffer);
    v18 = 0;
  }
  if ( pResult )
  {
    DsFreeNameResultW(pResult);
    v18 = 0;
  }
  if ( phDS[0] )
    DsUnBindW(phDS);
  if ( p_Buffer )
    ((void (__fastcall *)(char *, PWSTR, __int64))LsaFunctions->FreePrivateHeap)(p_Buffer, v14, v18);
  if ( MsvPaswdLogFile && !FlushFileBuffers(MsvPaswdLogFile) )
    GetLastError();
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180033148  push    rbp
0x18003314a  push    rsi
0x18003314b  push    rdi
0x18003314c  push    r12
0x18003314e  push    r13
0x180033150  push    r14
0x180033152  push    r15
0x180033154  sub     rsp, 330h
0x18003315b  lea     rbp, [rsp+50h]
0x180033160  mov     [rbp+310h+arg_0], rbx
0x180033167  mov     rax, cs:__security_cookie
0x18003316e  xor     rax, rbp
0x180033171  mov     [rbp+310h+var_40], rax
0x180033178  mov     rax, [rbp+310h+arg_20]
0x18003317f  xor     edi, edi
0x180033181  xorps   xmm0, xmm0
0x180033184  mov     qword ptr [rbp+310h+var_2B8], rax
0x180033188  mov     rax, [rbp+310h+arg_30]
0x18003318f  xorps   xmm1, xmm1
0x180033192  mov     [rbp+310h+var_2A0], rax
0x180033196  mov     rsi, rdx
0x180033199  mov     rax, [rbp+310h+arg_38]
0x1800331a0  mov     r15d, ecx
0x1800331a3  mov     [rbp+310h+var_280], ecx
0x1800331a9  xor     edx, edx; SourceString
0x1800331ab  lea     rcx, [rbp+310h+DestinationString]; DestinationString
0x1800331af  mov     [rbp+310h+var_278], rax
0x1800331b6  mov     r14, r9
0x1800331b9  mov     qword ptr [rbp+310h+var_2F8], r9
0x1800331bd  mov     rbx, r8
0x1800331c0  mov     [rbp+310h+Buffer], rdi
0x1800331c4  movups  xmmword ptr [rbp+310h+DestinationString.Length], xmm0
0x1800331c8  mov     [rbp+310h+pResult], rdi
0x1800331cc  mov     r12d, edi
0x1800331cf  movups  xmmword ptr [rbp+310h+DomainName2.Length], xmm1
0x1800331d3  mov     [rbp+310h+phDS], rdi
0x1800331d7  movups  xmmword ptr [rbp+310h+var_2B0.Length], xmm0
0x1800331db  mov     [rbp+310h+ServicePrincipalName], rdi
0x1800331df  movups  xmmword ptr [rbp+310h+var_268.Length], xmm1
0x1800331e6  mov     byte ptr [rbp+310h+var_310], 1
0x1800331ea  movups  xmmword ptr [rbp+310h+var_2D0.Length], xmm0
0x1800331ee  call    cs:__imp_RtlInitUnicodeString
0x1800331f4  movzx   edx, word ptr [rsi]
0x1800331f7  mov     r8d, 0FFFEh
0x1800331fd  movzx   eax, dx
0x180033200  mov     ecx, 1FEh
0x180033205  and     ax, r8w
0x180033209  cmp     ax, cx
0x18003320c  ja      loc_1800345BB
0x180033212  movzx   eax, word ptr [rbx]
0x180033215  mov     ecx, 400h
0x18003321a  and     ax, r8w
0x18003321e  cmp     ax, cx
0x180033221  ja      loc_1800345BB
0x180033227  mov     r8, rbx
0x18003322a  lea     rcx, aAttemptingPass; "Attempting password change server/domai"...
0x180033231  mov     rdx, rsi
0x180033234  call    MsvPaswdLogPrintRoutine
0x180033239  mov     rcx, cs:WPP_GLOBAL_Control
0x180033240  lea     r13, WPP_GLOBAL_Control
0x180033247  lea     r9d, [rdi+6]
0x18003324b  cmp     rcx, r13
0x18003324e  jz      short loc_1800332AB
0x180033250  test    dword ptr [rcx+1Ch], 1000h
0x180033257  jz      short loc_1800332AB
0x180033259  cmp     [rbp+310h+arg_28], dil
0x180033260  lea     rax, aFalse; "false"
0x180033267  mov     rcx, [rcx+10h]
0x18003326b  lea     r8, byte_180072560
0x180033272  lea     rdx, aTrue_0; "true"
0x180033279  cmovz   rdx, rax
0x18003327d  cmp     r15d, r9d
0x180033280  mov     [rsp+360h+var_328], rdx
0x180033285  lea     rax, aCached; " (cached)"
0x18003328c  cmovnz  rax, r8
0x180033290  mov     r9, rsi
0x180033293  mov     [rsp+360h+ppResult], rax
0x180033298  mov     dword ptr [rsp+360h+DomainControllerInfo], r15d
0x18003329d  mov     qword ptr [rsp+360h+Flags], rbx
0x1800332a2  call    WPP_SF_ZZDss
0x1800332a7  lea     r9d, [rdi+6]
0x1800332ab  xor     r8d, r8d
0x1800332ae  cmp     r15d, r9d
0x1800332b1  jnz     short loc_1800332CB
0x1800332b3  movups  xmm1, xmmword ptr [rsi]
0x1800332b6  mov     esi, r8d
0x1800332b9  movups  xmm0, xmmword ptr [rbx]
0x1800332bc  movdqu  xmmword ptr [rbp+310h+DomainName2.Length], xmm1
0x1800332c1  movdqu  xmmword ptr [rbp+310h+var_2D0.Length], xmm0
0x1800332c6  jmp     loc_1800341B3
0x1800332cb  cmp     [rsi], r8w
0x1800332cf  jnz     loc_180033EE6
0x1800332d5  movzx   eax, word ptr [rbx]
0x1800332d8  mov     ecx, 0FFFEh
0x1800332dd  and     ax, cx
0x1800332e0  mov     [rbp+310h+ThreadInformation], r8
0x1800332e7  mov     ecx, 200h
0x1800332ec  cmp     ax, cx
0x1800332ef  jbe     short loc_1800332FA
0x1800332f1  mov     r12, [rbp+310h+ServicePrincipalName]
0x1800332f5  jmp     loc_1800345F6
0x1800332fa  movzx   esi, word ptr [rbx]
0x1800332fd  lea     rcx, [rbp+310h+SourceString]; void *
0x180033304  mov     rdx, [rbx+8]; Src
0x180033308  mov     r8d, esi; Size
0x18003330b  call    memcpy_0
0x180033310  and     rsi, 0FFFFFFFFFFFFFFFEh
0x180033314  cmp     rsi, 202h
0x18003331b  jnb     loc_180034691
0x180033321  xor     eax, eax
0x180033323  lea     rdx, [rbp+310h+SourceString]; SourceString
0x18003332a  lea     rcx, [rbp+310h+var_268]; DestinationString
0x180033331  mov     [rbp+rsi+310h+SourceString], ax
0x180033339  call    cs:__imp_RtlInitUnicodeString
0x18003333f  xor     r8d, r8d
0x180033342  mov     r15d, 40h ; '@'
0x180033348  cmp     cs:NlpWorkstation, r8b
0x18003334f  jz      short loc_1800333BF
0x180033351  mov     dl, 1; Wait
0x180033353  lea     rcx, NtLmGlobalCritSect; Resource
0x18003335a  call    cs:__imp_RtlAcquireResourceShared
0x180033360  cmp     cs:NtLmGlobalTargetFlags, 20000h
0x18003336a  lea     rcx, NtLmGlobalCritSect; Resource
0x180033371  setz    bl
0x180033374  call    cs:__imp_RtlReleaseResource
0x18003337a  xor     r8d, r8d
0x18003337d  test    bl, bl
0x18003337f  jz      short loc_1800333BF
0x180033381  mov     rcx, cs:WPP_GLOBAL_Control
0x180033388  lea     rsi, WPP_GLOBAL_Control
0x18003338f  cmp     rcx, rsi
0x180033392  jz      short loc_1800333B8
0x180033394  test    byte ptr [rcx+1Ch], 2
0x180033398  jz      short loc_1800333B8
0x18003339a  mov     rcx, [rcx+10h]
0x18003339e  lea     edx, [r15-10h]
0x1800333a2  lea     r8, WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids
0x1800333a9  call    WPP_SF_
0x1800333ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800333b5  xor     r8d, r8d
0x1800333b8  mov     bl, 1
0x1800333ba  jmp     loc_180033BDF
0x1800333bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800333c6  mov     r14, r8
0x1800333c9  mov     r15, r8
0x1800333cc  mov     [rbp+310h+var_288], r8d
0x1800333d3  mov     r13d, 40000010h
0x1800333d9  lea     rsi, WPP_GLOBAL_Control
0x1800333e0  test    r14, r14
0x1800333e3  jnz     short loc_180033459
0x1800333e5  mov     rax, [rbp+310h+Buffer]
0x1800333e9  test    rax, rax
0x1800333ec  jz      short loc_180033402
0x1800333ee  mov     rcx, rax; Buffer
0x1800333f1  call    cs:__imp_NetApiBufferFree
0x1800333f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800333fe  mov     [rbp+310h+Buffer], r12
0x180033402  cmp     rcx, rsi
0x180033405  jz      short loc_180033426
0x180033407  test    dword ptr [rcx+1Ch], 1000h
0x18003340e  jz      short loc_180033426
0x180033410  mov     rcx, [rcx+10h]
0x180033414  mov     edx, 31h ; '1'
0x180033419  mov     r9, r15
0x18003341c  mov     [rsp+360h+Flags], r13d
0x180033421  call    WPP_SF_SD
0x180033426  lea     rax, [rbp+310h+Buffer]
0x18003342a  xor     r9d, r9d; SiteName
0x18003342d  mov     [rsp+360h+DomainControllerInfo], rax; DomainControllerInfo
0x180033432  xor     r8d, r8d; DomainGuid
0x180033435  mov     rdx, r15; DomainName
0x180033438  mov     [rsp+360h+Flags], r13d; Flags
0x18003343d  xor     ecx, ecx; ComputerName
0x18003343f  call    cs:__imp_DsGetDcNameW
0x180033445  xor     r8d, r8d
0x180033448  mov     ebx, eax
0x18003344a  test    eax, eax
0x18003344c  jnz     loc_180033A1A
0x180033452  mov     rax, [rbp+310h+Buffer]
0x180033456  mov     r14, [rax]
0x180033459  cmp     [rbp+310h+phDS], r8
0x18003345d  jz      short loc_180033470
0x18003345f  lea     rcx, [rbp+310h+phDS]; phDS
0x180033463  call    cs:__imp_DsUnBindW
0x180033469  xor     r8d, r8d
0x18003346c  mov     [rbp+310h+phDS], r8
0x180033470  mov     rcx, [rbp+310h+ServicePrincipalName]
0x180033474  test    rcx, rcx
0x180033477  jz      short loc_180033490
0x180033479  mov     rax, cs:LsaFunctions
0x180033480  mov     rax, [rax+188h]
0x180033487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003348c  mov     [rbp+310h+ServicePrincipalName], r12
0x180033490  lea     r8, [rbp+310h+ServicePrincipalName]
0x180033494  mov     rdx, r15
0x180033497  mov     rcx, r14; Src
0x18003349a  call    MspConstructSPN
0x18003349f  xor     r8d, r8d
0x1800334a2  mov     edi, eax
0x1800334a4  test    eax, eax
0x1800334a6  js      loc_180033EB9
0x1800334ac  call    MspImpersonateNetworkService
0x1800334b1  xor     r8d, r8d
0x1800334b4  mov     edi, eax
0x1800334b6  test    eax, eax
0x1800334b8  js      loc_180033EB9
0x1800334be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800334c5  mov     rbx, [rbp+310h+ServicePrincipalName]
0x1800334c9  cmp     rcx, rsi
0x1800334cc  jz      short loc_1800334EB
0x1800334ce  test    dword ptr [rcx+1Ch], 1000h
0x1800334d5  jz      short loc_1800334EB
0x1800334d7  mov     rcx, [rcx+10h]
0x1800334db  mov     r9, r14
0x1800334de  mov     qword ptr [rsp+360h+Flags], rbx
0x1800334e3  call    WPP_SF_SS
0x1800334e8  xor     r8d, r8d
0x1800334eb  mov     rdx, r8
0x1800334ee  lea     rax, [rbp+310h+phDS]
0x1800334f2  mov     [rsp+360h+DomainControllerInfo], rax; phDS
0x1800334f7  test    r14, r14
0x1800334fa  mov     [rsp+360h+Flags], r8d; BindFlags
0x1800334ff  mov     r9, rbx; ServicePrincipalName
0x180033502  cmovz   rdx, r15; DnsDomainName
0x180033506  mov     rcx, r14; DomainControllerName
0x180033509  xor     r8d, r8d; AuthIdentity
0x18003350c  call    cs:__imp_DsBindWithSpnExW
0x180033512  mov     ebx, eax
0x180033514  mov     ecx, 50000005h
0x180033519  add     eax, 0FFFFF88Dh
0x18003351e  cmp     eax, 1Eh
0x180033521  ja      short loc_18003352C
0x180033523  bt      ecx, eax
0x180033526  jb      loc_1800336FC
0x18003352c  lea     eax, [rbx+7FF8F88Dh]
0x180033532  cmp     eax, 1Eh
0x180033535  ja      short loc_180033540
0x180033537  bt      ecx, eax
0x18003353a  jb      loc_1800336FC
0x180033540  cmp     ebx, 0C0000413h
0x180033546  jz      loc_1800336FC
0x18003354c  cmp     ebx, 0D0000413h
0x180033552  jz      loc_1800336FC
0x180033558  lea     eax, [rbx-4F8h]
0x18003355e  mov     rcx, 0CC0210000000001h
0x180033568  cmp     eax, 3Bh ; ';'
0x18003356b  ja      short loc_180033577
0x18003356d  bt      rcx, rax
0x180033571  jb      loc_1800336FC
0x180033577  lea     eax, [rbx+7FF8FB08h]
0x18003357d  cmp     eax, 3Bh ; ';'
0x180033580  ja      short loc_18003358C
0x180033582  bt      rcx, rax
0x180033586  jb      loc_1800336FC
0x18003358c  lea     eax, [rbx+3FFFFFA1h]
0x180033592  mov     ecx, 0CC821h
0x180033597  cmp     eax, 13h
0x18003359a  ja      short loc_1800335A5
0x18003359c  bt      ecx, eax
0x18003359f  jb      loc_1800336FC
0x1800335a5  lea     eax, [rbx+2FFFFFA1h]
0x1800335ab  cmp     eax, 13h
0x1800335ae  ja      short loc_1800335B9
0x1800335b0  bt      ecx, eax
0x1800335b3  jb      loc_1800336FC
0x1800335b9  cmp     ebx, 0C0000234h
0x1800335bf  jz      loc_1800336FC
0x1800335c5  cmp     ebx, 0D0000234h
0x1800335cb  jz      loc_1800336FC
0x1800335d1  cmp     ebx, 701h
0x1800335d7  jz      loc_1800336FC
0x1800335dd  cmp     ebx, 80070701h
0x1800335e3  jz      loc_1800336FC
0x1800335e9  cmp     ebx, 0C0000193h
0x1800335ef  jz      loc_1800336FC
0x1800335f5  cmp     ebx, 0D0000193h
0x1800335fb  jz      loc_1800336FC
0x180033601  cmp     ebx, 569h
0x180033607  jz      loc_1800336FC
0x18003360d  cmp     ebx, 80070569h
0x180033613  jz      loc_1800336FC
0x180033619  cmp     ebx, 0C000015Bh
0x18003361f  jz      loc_1800336FC
0x180033625  cmp     ebx, 0D000015Bh
0x18003362b  jz      loc_1800336FC
0x180033631  lea     eax, [rbx+3FA2FFFEh]
0x180033637  cmp     eax, 8
0x18003363a  ja      short loc_18003364A
0x18003363c  mov     ecx, 117h
0x180033641  bt      ecx, eax
0x180033644  jb      loc_1800336FC
0x18003364a  cmp     ebx, 0D05D0002h
0x180033650  jz      loc_1800336FC
0x180033656  cmp     ebx, 0D05D0006h
0x18003365c  jz      loc_1800336FC
0x180033662  cmp     ebx, 5
0x180033665  jz      loc_1800336FC
0x18003366b  cmp     ebx, 80070005h
0x180033671  jz      loc_1800336FC
0x180033677  cmp     ebx, 0C0000022h
  ... truncated ...
```
