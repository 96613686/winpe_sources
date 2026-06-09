# SpAcceptCredentialsInternal

- ea: `0x180020b10`
- end: `0x180021801`
- name: `SpAcceptCredentialsInternal`
- size: `3313`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180020af0`
- `0x18005a420`

## callees

- `0x1800035b4`
- `0x180004460`
- `0x180007fc0`
- `0x18000a600`
- `0x18000b9b0`
- `0x180020b10`
- `0x180026ec0`
- `0x1800281c0`
- `0x18002f080`
- `0x1800316b8`
- `0x18003a2e0`
- `0x18003f5ec`
- `0x18004c420`
- `0x18004c4e0`
- `0x18005a2f8`
- `0x18005a62c`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180021559`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180021559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021571`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021571`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800215b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021655`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800215b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021655`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002169f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021709`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002169f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021709`
- `ntdll!RtlReleaseResource` at `0x1800214d3`
- `ntdll!RtlReleaseResource` at `0x1800214d3`
- `ntdll!NtQueryInformationToken` at `0x180020d3a`
- `ntdll!NtQueryInformationToken` at `0x180020d77`
- `ntdll!NtQueryInformationToken` at `0x180020d3a`
- `ntdll!NtQueryInformationToken` at `0x180020d77`
- `ntdll!RtlValidSid` at `0x180020bc1`
- `ntdll!RtlValidSid` at `0x180020bc1`
- `ntdll!RtlInitUnicodeString` at `0x180020c27`
- `ntdll!RtlInitUnicodeString` at `0x180020c51`
- `ntdll!RtlInitUnicodeString` at `0x180020c27`
- `ntdll!RtlInitUnicodeString` at `0x180020c51`
- `ntdll!RtlEqualUnicodeString` at `0x180020c38`
- `ntdll!RtlEqualUnicodeString` at `0x180020c65`
- `ntdll!RtlEqualUnicodeString` at `0x180020c83`
- `ntdll!RtlEqualUnicodeString` at `0x180020c38`
- `ntdll!RtlEqualUnicodeString` at `0x180020c65`
- `ntdll!RtlEqualUnicodeString` at `0x180020c83`
- `ntdll!NtClose` at `0x180021729`
- `ntdll!NtClose` at `0x180021729`
- `LSASRV!LsaIGetNameFromLuid` at `0x18002103e`
- `LSASRV!LsaIGetNameFromLuid` at `0x18002103e`

## string_xrefs

- `0x1800211a3`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x1800211d6`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18002126f`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x1800212a2`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180020f0b`: `No surrogate plugins`
- `0x180020edc`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x180021426`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x180021478`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x180020cc6`: `OpenTokenByLogonId`
- `0x180020cba`: `onecore\ds\ext\cloudap\dll\credapi.cpp`
- `0x180020d95`: `onecore\ds\ext\cloudap\dll\credapi.cpp`
- `0x180020e3f`: `onecore\ds\ext\cloudap\dll\credapi.cpp`
- `0x180020f6c`: `onecore\ds\ext\cloudap\dll\credapi.cpp`
- `0x180020fc9`: `onecore\ds\ext\cloudap\dll\credapi.cpp`
- `0x180021054`: `onecore\ds\ext\cloudap\dll\credapi.cpp`
- `0x180021212`: `onecore\ds\ext\cloudap\dll\credapi.cpp`
- `0x1800212db`: `onecore\ds\ext\cloudap\dll\credapi.cpp`
- `0x180021326`: `onecore\ds\ext\cloudap\dll\credapi.cpp`
- `0x18002138e`: `onecore\ds\ext\cloudap\dll\credapi.cpp`
- `0x1800214df`: `onecore\ds\ext\cloudap\dll\credapi.cpp`
- `0x180020dad`: `LUAIsElevatedToken`
- `0x180021587`: `CreateThread`

## pseudocode

```c
__int64 __fastcall SpAcceptCredentialsInternal(
        _SECURITY_LOGON_TYPE a1,
        __int64 a2,
        int *a3,
        struct _SECPKG_SUPPLEMENTAL_CRED *a4,
        unsigned int a5)
{
  const unsigned __int16 *v5; // r13
  const unsigned __int16 *v7; // r15
  void *v8; // rsi
  void *v9; // rcx
  int v10; // eax
  unsigned int v11; // edi
  const char *v12; // rax
  int v13; // r12d
  BOOL v14; // ebx
  const char *v15; // rax
  int v16; // ecx
  struct _SECPKG_SUPPLEMENTAL_CRED *v17; // rdx
  const char *v18; // rax
  unsigned int v19; // ebx
  int v20; // eax
  struct _ApPluginPkg *v21; // r12
  const char *v22; // r9
  char v23; // al
  const char *v24; // rdx
  bool v25; // zf
  const char *v26; // rax
  __int64 v27; // r8
  const char *v28; // r9
  char v29; // al
  const char *v30; // rcx
  bool v31; // zf
  unsigned __int16 v32; // bx
  unsigned __int16 v33; // cx
  const void *v34; // rdi
  const char *v35; // r9
  char v36; // al
  const char *v37; // rcx
  bool v38; // zf
  unsigned __int16 *v39; // rax
  unsigned __int16 v40; // cx
  size_t v41; // rdi
  struct _ApPluginPkg *v42; // rax
  struct _ApPluginPkg *v43; // rbx
  const char *v44; // rax
  int v45; // r8d
  unsigned int v46; // r11d
  __int64 v47; // r10
  const char *v48; // rax
  const char *v49; // rax
  const char *v50; // rax
  int v51; // r8d
  unsigned int v52; // r11d
  __int64 v53; // r10
  const char *v54; // rax
  const char *v55; // rax
  const char *v56; // rax
  const char *v57; // r9
  int v58; // eax
  int v59; // ecx
  int v60; // eax
  char *v61; // r8
  const char *v62; // rax
  __int64 v63; // r8
  const char *v64; // r9
  char v65; // al
  const char *v66; // rdx
  bool v67; // zf
  int v68; // r12d
  const char *v69; // rax
  int v70; // r8d
  char v71; // al
  const char *v72; // rcx
  bool v73; // zf
  void *v74; // rcx
  __int64 v75; // rbx
  __int64 v76; // rax
  __int64 v77; // rcx
  _BYTE *i; // rax
  PULONG ReturnLength; // [rsp+28h] [rbp-A1h]
  PULONG ReturnLengthb; // [rsp+28h] [rbp-A1h]
  PULONG ReturnLengthc; // [rsp+28h] [rbp-A1h]
  PULONG ReturnLengthd; // [rsp+28h] [rbp-A1h]
  PULONG ReturnLengthe; // [rsp+28h] [rbp-A1h]
  PULONG ReturnLengtha; // [rsp+28h] [rbp-A1h]
  PULONG ReturnLengthf; // [rsp+28h] [rbp-A1h]
  const char *v87; // [rsp+30h] [rbp-99h]
  __int64 v88; // [rsp+48h] [rbp-81h]
  int v89; // [rsp+50h] [rbp-79h] BYREF
  struct _ApPluginPkg *v90[2]; // [rsp+58h] [rbp-71h] BYREF
  unsigned int v91; // [rsp+68h] [rbp-61h] BYREF
  int TokenInformation; // [rsp+6Ch] [rbp-5Dh] BYREF
  ULONG v93; // [rsp+70h] [rbp-59h] BYREF
  int v94; // [rsp+74h] [rbp-55h] BYREF
  __int64 v95; // [rsp+78h] [rbp-51h] BYREF
  unsigned __int16 *v96[2]; // [rsp+80h] [rbp-49h] BYREF
  struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *v97; // [rsp+90h] [rbp-39h] BYREF
  int v98; // [rsp+98h] [rbp-31h] BYREF
  HANDLE TokenHandle; // [rsp+A0h] [rbp-29h] BYREF
  __int128 v100; // [rsp+A8h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-11h] BYREF
  UNICODE_STRING String1; // [rsp+C8h] [rbp-1h] BYREF
  _SECURITY_LOGON_TYPE CurrentThreadId; // [rsp+128h] [rbp+5Fh] BYREF
  __int64 v104; // [rsp+130h] [rbp+67h]
  HANDLE v105; // [rsp+138h] [rbp+6Fh] BYREF
  struct _SECPKG_SUPPLEMENTAL_CRED *v106; // [rsp+140h] [rbp+77h]

  v106 = a4;
  v104 = a2;
  CurrentThreadId = a1;
  v5 = 0;
  TokenHandle = 0;
  v90[0] = 0;
  v97 = 0;
  v7 = 0;
  v91 = 0;
  v8 = 0;
  v95 = 0;
  v88 = 0;
  String1 = 0;
  DestinationString = 0;
  *(_OWORD *)v96 = 0;
  v100 = 0;
  if ( (a1 & 0xFFFFFFF5) != 0
    || a1 == NetworkCleartext
    || !a3
    || !*((_QWORD *)a3 + 2)
    || !*((_WORD *)a3 + 4)
    || (v9 = (void *)*((_QWORD *)a3 + 9)) == 0
    || !RtlValidSid(v9)
    || (v10 = a3[20], (v10 & 0xA005) == 0)
    || (v10 & 0x10180) != 0
    || *a3 == dword_18009A748 && a3[1] == dword_18009A74C
    || *a3 == dword_18009A740 && a3[1] == dword_18009A744
    || (RtlInitUnicodeString(&DestinationString, &g_awchComputerName$),
        RtlEqualUnicodeString(&DestinationString, (PCUNICODE_STRING)(a3 + 2), 1u)) )
  {
    v11 = 0;
    goto LABEL_131;
  }
  RtlInitUnicodeString(&String1, &g_awchComputerName);
  if ( !RtlEqualUnicodeString(&String1, (PCUNICODE_STRING)(a3 + 6), 1u) )
  {
    if ( RtlEqualUnicodeString(&DestinationString, (PCUNICODE_STRING)(a3 + 6), 1u) )
    {
      v11 = 0;
      v8 = 0;
      goto LABEL_131;
    }
    LODWORD(v105) = ((__int64 (__fastcall *)(int *, HANDLE *))g_pLsaFunctionTable->OpenTokenByLogonId)(a3, &TokenHandle);
    v11 = (unsigned int)v105;
    if ( (_DWORD)v105 )
    {
      v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v12, 493, "OpenTokenByLogonId", &Class);
      v8 = 0;
      goto LABEL_132;
    }
    v93 = 0;
    TokenInformation = 1;
    v94 = 0;
    v13 = 1;
    v105 = TokenHandle;
    v14 = 0;
    v11 = NtQueryInformationToken(TokenHandle, TokenElevationType, &TokenInformation, 4u, &v93);
    if ( (v11 & 0x80000000) == 0 )
    {
      if ( TokenInformation == 2 )
      {
        v14 = 1;
      }
      else if ( TokenInformation == 1 )
      {
        v13 = 0;
        v11 = NtQueryInformationToken(v105, TokenElevation, &v94, 4u, &v93);
        if ( (v11 & 0x80000000) == 0 )
          v14 = v94 != 0;
      }
    }
    LODWORD(v105) = v11;
    if ( v11 )
    {
      LODWORD(ReturnLength) = 501;
      v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v15, ReturnLength, "LUAIsElevatedToken", &Class);
      goto LABEL_30;
    }
    if ( v13 && v14 )
    {
      v11 = 0;
      LODWORD(v105) = 0;
      v8 = 0;
      goto LABEL_132;
    }
    v16 = a3[20];
    v17 = (struct _SECPKG_SUPPLEMENTAL_CRED *)a3;
    if ( (v16 & 0x1000) == 0 )
      v17 = 0;
    if ( v17 && ((__int64)v17[6].Credentials & 1) != 0 )
    {
      LODWORD(v105) = GetLogonCredsFromIdentityEx2(
                        *((char **)a3 + 18),
                        *((unsigned __int16 *)a3 + 68),
                        (struct _DECRYPTED_AUTH_DATA *)v96,
                        (unsigned __int16 **)v90);
      v11 = (unsigned int)v105;
      if ( (_DWORD)v105 )
      {
        v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
        LODWORD(ReturnLength) = 518;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v18, ReturnLength, "GetLogonCredsFromIdentityEx2", &Class);
LABEL_40:
        v5 = (const unsigned __int16 *)v90[0];
        v8 = 0;
        goto LABEL_132;
      }
      v91 = 6;
LABEL_42:
      v5 = (const unsigned __int16 *)v90[0];
      goto LABEL_43;
    }
    if ( (v16 & 0x108000) == 0x108000 )
    {
      LODWORD(v105) = GetLogonCredsFromIdentityEx2(
                        *((char **)a3 + 18),
                        *((unsigned __int16 *)a3 + 68),
                        (struct _DECRYPTED_AUTH_DATA *)v96,
                        (unsigned __int16 **)v90);
      v11 = (unsigned int)v105;
      if ( (_DWORD)v105 )
      {
        v26 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
        LODWORD(ReturnLength) = 528;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v26, ReturnLength, "GetLogonCredsFromIdentityEx2", &Class);
        goto LABEL_40;
      }
      v91 = 7;
      goto LABEL_42;
    }
    LODWORD(v105) = MakePackedCredentials((struct _SECPKG_PRIMARY_CRED *)a3, v17, &v97, &v91);
    v11 = (unsigned int)v105;
    if ( (_DWORD)v105 )
    {
      v28 = "";
      while ( 1 )
      {
        v29 = *(v28 - 1);
        v30 = v28--;
        v31 = v29 == 92;
        if ( v29 == 92 )
          break;
        if ( v28 <= "onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp" )
        {
          v31 = v29 == 92;
          break;
        }
      }
      if ( v31 )
        v28 = v30;
      LODWORD(ReturnLength) = 542;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v105, v28, ReturnLength, "MakePackedCredentials", &Class);
      goto LABEL_30;
    }
    if ( *((_QWORD *)a3 + 14) && (v32 = *((_WORD *)a3 + 52)) != 0 )
    {
      v33 = *((_WORD *)a3 + 53);
      v34 = (const void *)*((_QWORD *)a3 + 14);
    }
    else
    {
      LOBYTE(v27) = 1;
      LODWORD(v105) = LsaIGetNameFromLuid(a3, 8, v27, &v100);
      v11 = (unsigned int)v105;
      if ( (_DWORD)v105 )
      {
        v35 = "";
        while ( 1 )
        {
          v36 = *(v35 - 1);
          v37 = v35--;
          v38 = v36 == 92;
          if ( v36 == 92 )
            break;
          if ( v35 <= "onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp" )
          {
            v38 = v36 == 92;
            break;
          }
        }
        if ( v38 )
          v35 = v37;
        LODWORD(ReturnLength) = 554;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v105, v35, ReturnLength, "LsaIGetNameFromLuid", &Class);
        goto LABEL_30;
      }
      v32 = v100;
      v33 = WORD1(v100);
      v34 = (const void *)*((_QWORD *)&v100 + 1);
    }
    if ( v34 && v33 )
    {
      if ( v32 > v33 || (v32 & 1) != 0 )
      {
        v11 = -1073741811;
        goto LABEL_92;
      }
      v39 = (unsigned __int16 *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)((unsigned __int16)(v33 + 2));
      v7 = v39;
      if ( !v39 )
      {
        v11 = -1073741801;
LABEL_92:
        v44 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        LODWORD(ReturnLength) = v45;
        WPPTraceLogA(v46, "0x%08x %s:%u : %s:%ws", v11, v44, ReturnLength, v47, &Class);
        v7 = 0;
        v48 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        LODWORD(ReturnLengthb) = 310;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v48, ReturnLengthb, "DuplicateUnicodeString2", &Class);
        LODWORD(v105) = v11;
        v49 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
        LODWORD(ReturnLengthc) = 566;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v49, ReturnLengthc, "DuplicateUnicodeString4", &Class);
LABEL_30:
        v8 = 0;
        goto LABEL_132;
      }
      memcpy_0(v39, v34, v32);
    }
    *(_OWORD *)v90 = 0;
    if ( a3 != (int *)-24LL && *((_QWORD *)a3 + 4) && (v40 = *((_WORD *)a3 + 13)) != 0 )
    {
      v41 = *((unsigned __int16 *)a3 + 12);
      if ( (unsigned __int16)v41 > v40 || (v41 & 1) != 0 )
      {
        v11 = -1073741811;
        goto LABEL_95;
      }
      v42 = (struct _ApPluginPkg *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)((unsigned __int16)(v40 + 2));
      v43 = v42;
      if ( !v42 )
      {
        v11 = -1073741801;
LABEL_95:
        v50 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        LODWORD(ReturnLength) = v51;
        WPPTraceLogA(v52, "0x%08x %s:%u : %s:%ws", v11, v50, ReturnLength, v53, &Class);
        v54 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        LODWORD(ReturnLengthd) = 310;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v54, ReturnLengthd, "DuplicateUnicodeString2", &Class);
        LODWORD(v105) = v11;
        v55 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
        LODWORD(ReturnLengthe) = 571;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v55, ReturnLengthe, "DuplicateUnicodeString4", &Class);
        goto LABEL_30;
      }
      memcpy_0(v42, *((const void **)a3 + 4), v41);
    }
    else
    {
      v43 = v90[1];
    }
    v5 = (const unsigned __int16 *)v43;
    LODWORD(v105) = DuplicateString(v7, 0, v96);
    v11 = (unsigned int)v105;
    if ( (_DWORD)v105 )
    {
      v56 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
      v87 = "DuplicateString";
      LODWORD(ReturnLength) = 577;
    }
    else
    {
      LODWORD(v105) = DuplicateString(v7, 1, &v96[1]);
      v11 = (unsigned int)v105;
      if ( !(_DWORD)v105 )
      {
LABEL_43:
        v19 = a3[20];
        LODWORD(v105) = v19;
        v90[0] = 0;
        v20 = RefPackageByProvName(v5, v90);
        v11 = v20;
        if ( v20 < 0 )
        {
          v20 = RefDefaultPackage(v90);
          v11 = v20;
        }
        v21 = v90[0];
        if ( v20 )
        {
          v22 = "";
          while ( 1 )
          {
            v23 = *(v22 - 1);
            v24 = v22--;
            v25 = v23 == 92;
            if ( v23 == 92 )
              break;
            if ( v22 <= "onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp" )
            {
              v25 = v23 == 92;
              break;
            }
          }
          if ( v25 )
            v22 = v24;
          LODWORD(ReturnLength) = 1553;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v22, ReturnLength, "No surrogate plugins", &Class);
        }
        else
        {
          v58 = SurrogateLogonUser(
                  CurrentThreadId,
                  v90[0],
                  (struct _LUID *)a3,
                  v19,
                  v5,
                  (struct _DECRYPTED_AUTH_DATA *const)v96,
                  v106,
                  a5);
          v59 = a3[1];
          v11 = v58;
          v98 = v58;
          v60 = *a3;
          v61 = (char *)v21 + 24;
          if ( (v11 & 0x80000000) == 0 )
          {
            v89 = v59;
            LODWORD(v90[0]) = v60;
            CloudAPProvider::CloudApSurrogateLogonSucceed<unsigned long,unsigned long,unsigned short (&)[21],unsigned long &>(
              &v89,
              v90,
              v61,
              &v105);
            v64 = "";
            while ( 1 )
            {
              v65 = *(v64 - 1);
              v66 = v64--;
              v67 = v65 == 92;
              if ( v65 == 92 )
                break;
              if ( v64 <= "onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp" )
              {
                v67 = v65 == 92;
                break;
              }
            }
            if ( v67 )
              v64 = v66;
            LODWORD(ReturnLengtha) = 1583;
            WPPTraceLogA(
              2,
              "0x%08x %s:%u : %s:%ws",
              v11,
              v64,
              ReturnLengtha,
              "SurrogateLogonUser success",
              (char *)v21 + 24);
          }
          else
          {
            v89 = *a3;
            LODWORD(v90[0]) = v59;
            CloudAPProvider::CloudApSurrogateLogonFailed<unsigned long,unsigned long,unsigned short (&)[21],long &,unsigned long &>(
              (unsigned int)v90,
              (unsigned int)&v89,
              (_DWORD)v61,
              (unsigned int)&v98,
              (__int64)&v105);
            v62 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
            LODWORD(ReturnLengthf) = 1573;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v62, ReturnLengthf, "SurrogateLogonUser", v63);
          }
        }
        if ( v21 )
          RtlReleaseResource(&g_PackageListLock);
        LODWORD(v105) = v11;
        v68 = v11;
        if ( v11 == -1073741608 )
        {
          LODWORD(v105) = AllocateAcceptCredentialsData((unsigned int)CurrentThreadId, v104, a3, v106, &v95);
          v11 = (unsigned int)v105;
          if ( (_DWORD)v105 )
          {
            v56 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
            v87 = "AllocateAcceptCredentialsData";
            LODWORD(ReturnLength) = 602;
            goto LABEL_99;
          }
          v68 = 0;
          v88 = _o__beginthreadex(0, 0, AcceptCredentialsAsyncWorker, v95, 0, 0);
          if ( v88 )
          {
            v95 = 0;
          }
          else
          {
            v11 = -1073741816;
            LODWORD(v105) = -1073741816;
            GetLastError();
            v69 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%u", -1073741816, v69, 614, "CreateThread", v70);
            v68 = -1073741816;
          }
          CurrentThreadId = GetCurrentThreadId();
          LODWORD(v90[0]) = *a3;
          v89 = a3[1];
          CloudAPProvider::CreateThreadForSurrogateLogon<unsigned long,unsigned long,long &,unsigned long &,unsigned long>(
            &v89,
            (int *)v90,
            (int *)&v105,
            a3 + 20,
            (int *)&CurrentThreadId);
        }
        if ( !v68 )
          goto LABEL_101;
        v57 = "";
        while ( 1 )
        {
          v71 = *(v57 - 1);
          v72 = v57--;
          v73 = v71 == 92;
          if ( v71 == 92 )
            break;
          if ( v57 <= "onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp" )
          {
            v73 = v71 == 92;
            break;
          }
        }
        v87 = "PerformSurrogateLogonFromPackages";
        if ( v73 )
          v57 = v72;
        LODWORD(ReturnLength) = 629;
LABEL_100:
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v57, ReturnLength, v87, &Class);
LABEL_101:
        v8 = (void *)v88;
        goto LABEL_132;
      }
      v56 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
      v87 = "DuplicateString";
      LODWORD(ReturnLength) = 583;
    }
LABEL_99:
    v57 = v56;
    goto LABEL_100;
  }
  v11 = 0;
  v8 = 0;
LABEL_131:
  LODWORD(v105) = 0;
LABEL_132:
  if ( (a3[20] & 0x2004) == 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    LODWORD(v90[0]) = *a3;
    v89 = a3[1];
    CloudAPProvider::CloudApAcceptCreds<unsigned long,unsigned long,long &,unsigned long &,unsigned long &,unsigned long>(
      (unsigned int)&v89,
      (unsigned int)v90,
      (unsigned int)&v105,
      (unsigned int)&v91,
      (__int64)(a3 + 20),
      (__int64)&CurrentThreadId);
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v7 )
    ((void (__fastcall *)(const unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v7);
  if ( *((_QWORD *)&v100 + 1) )
    ((void (*)(void))g_pLsaFunctionTable->FreePrivateHeap)();
  if ( v5 )
    ((void (__fastcall *)(const unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v5);
  if ( v8 )
    CloseHandle(v8);
  if ( v95 )
  {
    v74 = *(void **)(v95 + 40);
    if ( v74 )
      NtClose(v74);
  }
  FreePackedCreds(v97);
  if ( v96[0] )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v96[1] )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  v75 = v95;
  v97 = 0;
  *(_OWORD *)v96 = 0;
  if ( v95 )
  {
    if ( *(_QWORD *)(v95 + 16) )
      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
    FreePrimaryCred(*(struct _SECPKG_PRIMARY_CRED **)(v75 + 24));
    v76 = *(_QWORD *)(v75 + 32);
    if ( v76 )
    {
      v77 = *(unsigned int *)(v76 + 16);
      for ( i = *(_BYTE **)(v76 + 24); v77; --v77 )
        *i++ = 0;
      ((void (__fastcall *)(_QWORD))g_pLsaFunctionTable->FreeLsaHeap)(*(_QWORD *)(v75 + 32));
    }
    ((void (__fastcall *)(__int64))g_pLsaFunctionTable->FreeLsaHeap)(v75);
  }
  return v11;
}

```

## disassembly

```asm
0x180020b10  mov     rax, rsp
0x180020b13  mov     [rax+20h], r9
0x180020b17  mov     [rax+10h], rdx
0x180020b1b  mov     [rax+8], ecx
0x180020b1e  push    rbp
0x180020b1f  push    rbx
0x180020b20  push    rdi
0x180020b21  lea     rbp, [rax-57h]
0x180020b25  sub     rsp, 100h
0x180020b2c  mov     [rax-20h], rsi
0x180020b30  xorps   xmm0, xmm0
0x180020b33  mov     [rax-28h], r12
0x180020b37  xorps   xmm1, xmm1
0x180020b3a  xor     r12d, r12d
0x180020b3d  mov     [rax-30h], r13
0x180020b41  mov     [rax-38h], r14
0x180020b45  mov     r13d, r12d
0x180020b48  mov     [rax-40h], r15
0x180020b4c  mov     r14, r8
0x180020b4f  mov     eax, ecx
0x180020b51  mov     [rbp+4Fh+TokenHandle], r12
0x180020b55  xor     ecx, ecx
0x180020b57  mov     [rbp+4Fh+var_C0], r12
0x180020b5b  mov     [rbp+4Fh+var_88], rcx
0x180020b5f  mov     r15d, r12d
0x180020b62  mov     [rbp+4Fh+var_B0], r12d
0x180020b66  mov     esi, r12d
0x180020b69  mov     [rbp+4Fh+var_A0], r12
0x180020b6d  mov     [rsp+40h], r12
0x180020b72  movups  xmmword ptr [rbp+4Fh+String1.Length], xmm0
0x180020b76  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm1
0x180020b7a  movups  xmmword ptr [rbp+4Fh+var_98], xmm0
0x180020b7e  movups  [rbp+4Fh+var_70], xmm0
0x180020b82  test    eax, 0FFFFFFF5h
0x180020b87  jnz     loc_180021638
0x180020b8d  cmp     eax, 8
0x180020b90  jz      loc_180021638
0x180020b96  test    r8, r8
0x180020b99  jz      loc_180021638
0x180020b9f  cmp     [r8+10h], rcx
0x180020ba3  jz      loc_180021638
0x180020ba9  cmp     r12w, [r8+8]
0x180020bae  jz      loc_180021638
0x180020bb4  mov     rcx, [r8+48h]; Sid
0x180020bb8  test    rcx, rcx
0x180020bbb  jz      loc_180021638
0x180020bc1  call    cs:__imp_RtlValidSid
0x180020bc7  test    al, al
0x180020bc9  jz      loc_180021638
0x180020bcf  mov     eax, [r14+50h]
0x180020bd3  test    eax, 0A005h
0x180020bd8  jz      loc_180021638
0x180020bde  test    eax, 10180h
0x180020be3  jnz     loc_180021638
0x180020be9  mov     ecx, [r14]
0x180020bec  cmp     ecx, cs:dword_18009A748
0x180020bf2  jnz     short loc_180020C04
0x180020bf4  mov     eax, cs:dword_18009A74C
0x180020bfa  cmp     [r14+4], eax
0x180020bfe  jz      loc_180021638
0x180020c04  cmp     ecx, cs:dword_18009A740
0x180020c0a  jnz     short loc_180020C1C
0x180020c0c  mov     eax, cs:dword_18009A744
0x180020c12  cmp     [r14+4], eax
0x180020c16  jz      loc_180021638
0x180020c1c  lea     rdx, ?g_awchComputerName$@@3PAGA; SourceString
0x180020c23  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x180020c27  call    cs:__imp_RtlInitUnicodeString
0x180020c2d  mov     r8b, 1; CaseInsensitive
0x180020c30  lea     rdx, [r14+8]; String2
0x180020c34  lea     rcx, [rbp+4Fh+DestinationString]; String1
0x180020c38  call    cs:__imp_RtlEqualUnicodeString
0x180020c3e  test    al, al
0x180020c40  jnz     loc_180021638
0x180020c46  lea     rdx, ?g_awchComputerName@@3PAGA; SourceString
0x180020c4d  lea     rcx, [rbp+4Fh+String1]; DestinationString
0x180020c51  call    cs:__imp_RtlInitUnicodeString
0x180020c57  lea     rsi, [r14+18h]
0x180020c5b  mov     r8b, 1; CaseInsensitive
0x180020c5e  mov     rdx, rsi; String2
0x180020c61  lea     rcx, [rbp+4Fh+String1]; String1
0x180020c65  call    cs:__imp_RtlEqualUnicodeString
0x180020c6b  test    al, al
0x180020c6d  jz      short loc_180020C79
0x180020c6f  mov     edi, r12d
0x180020c72  mov     esi, edi
0x180020c74  jmp     loc_18002163B
0x180020c79  mov     r8b, 1; CaseInsensitive
0x180020c7c  lea     rcx, [rbp+4Fh+DestinationString]; String1
0x180020c80  mov     rdx, rsi; String2
0x180020c83  call    cs:__imp_RtlEqualUnicodeString
0x180020c89  test    al, al
0x180020c8b  jz      short loc_180020C97
0x180020c8d  mov     edi, r12d
0x180020c90  mov     esi, edi
0x180020c92  jmp     loc_18002163B
0x180020c97  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180020c9e  lea     rdx, [rbp+4Fh+TokenHandle]
0x180020ca2  mov     rcx, r14
0x180020ca5  mov     rax, [rax+170h]
0x180020cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cb1  mov     dword ptr [rbp+4Fh+arg_10], eax
0x180020cb4  mov     edi, eax
0x180020cb6  test    eax, eax
0x180020cb8  jz      short loc_180020D02
0x180020cba  lea     rcx, aOnecoreDsExtCl_4; "onecore\\ds\\ext\\cloudap\\dll\\credapi"...
0x180020cc1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180020cc6  lea     rcx, aOpentokenbylog; "OpenTokenByLogonId"
0x180020ccd  mov     r9, rax
0x180020cd0  lea     rsi, Class
0x180020cd7  mov     r8d, edi
0x180020cda  mov     [rsp+110h+var_E0], rsi
0x180020cdf  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180020ce6  mov     [rsp+110h+var_E8], rcx
0x180020ceb  xor     ecx, ecx
0x180020ced  mov     dword ptr [rsp+110h+ReturnLength], 1EDh
0x180020cf5  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180020cfa  mov     rsi, r12
0x180020cfd  jmp     loc_18002163F
0x180020d02  mov     rax, [rbp+4Fh+TokenHandle]
0x180020d06  lea     r8, [rbp+4Fh+TokenInformation]; TokenInformation
0x180020d0a  mov     ecx, 1
0x180020d0f  mov     [rbp+4Fh+var_A8], r12d
0x180020d13  mov     [rbp+4Fh+TokenInformation], ecx
0x180020d16  mov     r9d, 4; TokenInformationLength
0x180020d1c  mov     [rbp+4Fh+var_A4], r12d
0x180020d20  mov     edx, 12h; TokenInformationClass
0x180020d25  mov     r12d, ecx
0x180020d28  mov     [rbp+4Fh+arg_10], rax
0x180020d2c  lea     rcx, [rbp+4Fh+var_A8]
0x180020d30  xor     ebx, ebx
0x180020d32  mov     [rsp+110h+ReturnLength], rcx; ReturnLength
0x180020d37  mov     rcx, rax; TokenHandle
0x180020d3a  call    cs:__imp_NtQueryInformationToken
0x180020d40  mov     edi, eax
0x180020d42  test    eax, eax
0x180020d44  js      short loc_180020D8E
0x180020d46  mov     eax, [rbp+4Fh+TokenInformation]
0x180020d49  cmp     eax, 2
0x180020d4c  jnz     short loc_180020D53
0x180020d4e  mov     ebx, r12d
0x180020d51  jmp     short loc_180020D8E
0x180020d53  cmp     eax, r12d
0x180020d56  jnz     short loc_180020D8E
0x180020d58  mov     rcx, [rbp+4Fh+arg_10]; TokenHandle
0x180020d5c  lea     rax, [rbp+4Fh+var_A8]
0x180020d60  mov     r9d, 4; TokenInformationLength
0x180020d66  mov     [rsp+110h+ReturnLength], rax; ReturnLength
0x180020d6b  lea     r8, [rbp+4Fh+var_A4]; TokenInformation
0x180020d6f  mov     edx, 14h; TokenInformationClass
0x180020d74  xor     r12d, r12d
0x180020d77  call    cs:__imp_NtQueryInformationToken
0x180020d7d  mov     edi, eax
0x180020d7f  test    eax, eax
0x180020d81  js      short loc_180020D8E
0x180020d83  cmp     [rbp+4Fh+var_A4], ebx
0x180020d86  mov     eax, 1
0x180020d8b  cmovnz  ebx, eax
0x180020d8e  mov     dword ptr [rbp+4Fh+arg_10], edi
0x180020d91  test    edi, edi
0x180020d93  jz      short loc_180020DDD
0x180020d95  lea     rcx, aOnecoreDsExtCl_4; "onecore\\ds\\ext\\cloudap\\dll\\credapi"...
0x180020d9c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180020da1  lea     rsi, Class
0x180020da8  mov     [rsp+110h+var_E0], rsi
0x180020dad  lea     rcx, aLuaiselevatedt; "LUAIsElevatedToken"
0x180020db4  mov     [rsp+110h+var_E8], rcx
0x180020db9  mov     dword ptr [rsp+110h+ReturnLength], 1F5h
0x180020dc1  mov     r9, rax
0x180020dc4  mov     r8d, edi
0x180020dc7  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180020dce  xor     ecx, ecx
0x180020dd0  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180020dd5  mov     rsi, r13
0x180020dd8  jmp     loc_18002163F
0x180020ddd  test    r12d, r12d
0x180020de0  jz      short loc_180020DF2
0x180020de2  test    ebx, ebx
0x180020de4  jz      short loc_180020DF2
0x180020de6  xor     edi, edi
0x180020de8  mov     dword ptr [rbp+4Fh+arg_10], edi
0x180020deb  mov     esi, edi
0x180020ded  jmp     loc_18002163F
0x180020df2  mov     ecx, [r14+50h]
0x180020df6  mov     rdx, r14
0x180020df9  bt      ecx, 0Ch
0x180020dfd  mov     rax, r13
0x180020e00  cmovnb  rdx, rax; struct _SECPKG_SUPPLEMENTAL_CRED *
0x180020e04  test    rdx, rdx
0x180020e07  jz      loc_180020F39
0x180020e0d  test    byte ptr [rdx+0D8h], 1
0x180020e14  jz      loc_180020F39
0x180020e1a  movzx   edx, word ptr [r14+88h]; AuthIdentityLength
0x180020e22  lea     r9, [rbp+4Fh+var_C0]; unsigned __int16 **
0x180020e26  mov     rcx, [r14+90h]; AuthIdentityByteArray
0x180020e2d  lea     r8, [rbp+4Fh+var_98]; struct _DECRYPTED_AUTH_DATA *
0x180020e31  call    ?GetLogonCredsFromIdentityEx2@@YAJPEAXKPEAU_DECRYPTED_AUTH_DATA@@PEAPEAG@Z; GetLogonCredsFromIdentityEx2(void *,ulong,_DECRYPTED_AUTH_DATA *,ushort * *)
0x180020e36  mov     dword ptr [rbp+4Fh+arg_10], eax
0x180020e39  mov     edi, eax
0x180020e3b  test    eax, eax
0x180020e3d  jz      short loc_180020E8B
0x180020e3f  lea     rcx, aOnecoreDsExtCl_4; "onecore\\ds\\ext\\cloudap\\dll\\credapi"...
0x180020e46  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180020e4b  lea     rsi, Class
0x180020e52  mov     [rsp+110h+var_E0], rsi
0x180020e57  lea     rcx, aGetlogoncredsf_0; "GetLogonCredsFromIdentityEx2"
0x180020e5e  mov     [rsp+110h+var_E8], rcx
0x180020e63  mov     dword ptr [rsp+110h+ReturnLength], 206h
0x180020e6b  mov     r9, rax
0x180020e6e  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180020e75  mov     r8d, edi
0x180020e78  xor     ecx, ecx
0x180020e7a  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180020e7f  mov     r13, [rbp+4Fh+var_C0]
0x180020e83  mov     rsi, r15
0x180020e86  jmp     loc_18002163F
0x180020e8b  mov     [rbp+4Fh+var_B0], 6
0x180020e92  mov     r13, [rbp+4Fh+var_C0]
0x180020e96  mov     ebx, [r14+50h]
0x180020e9a  lea     rdx, [rbp+4Fh+var_C0]; struct _ApPluginPkg **
0x180020e9e  mov     rcx, r13; unsigned __int16 *
0x180020ea1  mov     dword ptr [rbp+4Fh+arg_10], ebx
0x180020ea4  mov     [rbp+4Fh+var_C0], 0
0x180020eac  call    ?RefPackageByProvName@@YAJPEBGPEAPEAU_ApPluginPkg@@@Z; RefPackageByProvName(ushort const *,_ApPluginPkg * *)
0x180020eb1  mov     edi, eax
0x180020eb3  test    eax, eax
0x180020eb5  jns     short loc_180020EC2
0x180020eb7  lea     rcx, [rbp+4Fh+var_C0]; struct _ApPluginPkg **
0x180020ebb  call    ?RefDefaultPackage@@YAJPEAPEAU_ApPluginPkg@@@Z; RefDefaultPackage(_ApPluginPkg * *)
0x180020ec0  mov     edi, eax
0x180020ec2  mov     r12, [rbp+4Fh+var_C0]
0x180020ec6  lea     rsi, Class
0x180020ecd  test    eax, eax
0x180020ecf  jz      loc_1800213BC
0x180020ed5  lea     r9, aOnecoreDsExtCl+2Eh; ""
0x180020edc  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x180020ee3  nop     dword ptr [rax+00h]
0x180020ee7  nop     word ptr [rax+rax+00000000h]
0x180020ef0  movzx   eax, byte ptr [r9-1]
0x180020ef5  mov     rdx, r9
0x180020ef8  dec     r9
0x180020efb  cmp     al, 5Ch ; '\'
0x180020efd  jz      short loc_180020F06
0x180020eff  cmp     r9, rcx
0x180020f02  ja      short loc_180020EF0
0x180020f04  cmp     al, 5Ch ; '\'
0x180020f06  mov     [rsp+110h+var_E0], rsi
0x180020f0b  lea     rax, aNoSurrogatePlu; "No surrogate plugins"
0x180020f12  mov     [rsp+110h+var_E8], rax
0x180020f17  cmovz   r9, rdx
0x180020f1b  mov     dword ptr [rsp+110h+ReturnLength], 611h
0x180020f23  mov     r8d, edi
0x180020f26  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180020f2d  xor     ecx, ecx
0x180020f2f  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180020f34  jmp     loc_1800214C7
0x180020f39  and     ecx, 108000h
0x180020f3f  cmp     ecx, 108000h
0x180020f45  jnz     short loc_180020FA9
0x180020f47  movzx   edx, word ptr [r14+88h]; AuthIdentityLength
0x180020f4f  lea     r9, [rbp+4Fh+var_C0]; unsigned __int16 **
0x180020f53  mov     rcx, [r14+90h]; AuthIdentityByteArray
0x180020f5a  lea     r8, [rbp+4Fh+var_98]; struct _DECRYPTED_AUTH_DATA *
0x180020f5e  call    ?GetLogonCredsFromIdentityEx2@@YAJPEAXKPEAU_DECRYPTED_AUTH_DATA@@PEAPEAG@Z; GetLogonCredsFromIdentityEx2(void *,ulong,_DECRYPTED_AUTH_DATA *,ushort * *)
0x180020f63  mov     dword ptr [rbp+4Fh+arg_10], eax
0x180020f66  mov     edi, eax
0x180020f68  test    eax, eax
0x180020f6a  jz      short loc_180020F9D
0x180020f6c  lea     rcx, aOnecoreDsExtCl_4; "onecore\\ds\\ext\\cloudap\\dll\\credapi"...
0x180020f73  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180020f78  lea     rsi, Class
0x180020f7f  mov     [rsp+110h+var_E0], rsi
0x180020f84  lea     rcx, aGetlogoncredsf_0; "GetLogonCredsFromIdentityEx2"
0x180020f8b  mov     [rsp+110h+var_E8], rcx
0x180020f90  mov     dword ptr [rsp+110h+ReturnLength], 210h
0x180020f98  jmp     loc_180020E6B
0x180020f9d  mov     [rbp+4Fh+var_B0], 7
0x180020fa4  jmp     loc_180020E92
0x180020fa9  lea     r9, [rbp+4Fh+var_B0]; unsigned int *
0x180020fad  mov     rcx, r14; struct _SECPKG_PRIMARY_CRED *
0x180020fb0  lea     r8, [rbp+4Fh+var_88]; struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS **
0x180020fb4  call    ?MakePackedCredentials@@YAJPEAU_SECPKG_PRIMARY_CRED@@PEAU_SECPKG_SUPPLEMENTAL_CRED@@PEAPEAU_SEC_WINNT_AUTH_PACKED_CREDENTIALS@@PEAK@Z; MakePackedCredentials(_SECPKG_PRIMARY_CRED *,_SECPKG_SUPPLEMENTAL_CRED *,_SEC_WINNT_AUTH_PACKED_CREDENTIALS * *,ulong *)
0x180020fb9  mov     dword ptr [rbp+4Fh+arg_10], eax
0x180020fbc  mov     edi, eax
0x180020fbe  test    eax, eax
0x180020fc0  jz      short loc_18002100F
0x180020fc2  lea     r9, aOnecoreDsExtCl_4+26h; ""
0x180020fc9  lea     rbx, aOnecoreDsExtCl_4; "onecore\\ds\\ext\\cloudap\\dll\\credapi"...
0x180020fd0  movzx   eax, byte ptr [r9-1]
0x180020fd5  mov     rcx, r9
0x180020fd8  dec     r9
0x180020fdb  cmp     al, 5Ch ; '\'
0x180020fdd  jz      short loc_180020FE6
0x180020fdf  cmp     r9, rbx
0x180020fe2  ja      short loc_180020FD0
0x180020fe4  cmp     al, 5Ch ; '\'
0x180020fe6  lea     rsi, Class
0x180020fed  cmovz   r9, rcx
0x180020ff1  mov     [rsp+110h+var_E0], rsi
0x180020ff6  lea     rax, aMakepackedcred; "MakePackedCredentials"
  ... truncated ...
```
