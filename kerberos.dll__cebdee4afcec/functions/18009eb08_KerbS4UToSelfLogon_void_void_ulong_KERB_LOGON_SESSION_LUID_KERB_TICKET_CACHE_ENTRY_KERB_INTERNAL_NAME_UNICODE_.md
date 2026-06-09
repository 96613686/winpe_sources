# KerbS4UToSelfLogon(void *,void *,ulong,_KERB_LOGON_SESSION * *,_LUID *,_KERB_TICKET_CACHE_ENTRY * *,_KERB_INTERNAL_NAME * *,_UNICODE_STRING *,_LUID *)

- ea: `0x18009eb08`
- end: `0x18009f71f`
- name: `?KerbS4UToSelfLogon@@YAJPEAX0KPEAPEAU_KERB_LOGON_SESSION@@PEAU_LUID@@PEAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAPEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@2@Z`
- size: `3095`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned int, struct _KERB_LOGON_SESSION **, LUID *LocallyUniqueId, struct _KERB_TICKET_CACHE_ENTRY **, struct _KERB_INTERNAL_NAME **, PUNICODE_STRING DestinationString, PLUID)`
- caller_count: `1`
- callee_count: `26`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180025680`

## callees

- `0x1800063e8`
- `0x1800068d0`
- `0x1800069e0`
- `0x180009afc`
- `0x18000a630`
- `0x18000b300`
- `0x180010e90`
- `0x1800163a0`
- `0x1800209f0`
- `0x1800290c0`
- `0x18002a474`
- `0x180032964`
- `0x1800545ec`
- `0x180054c88`
- `0x180058380`
- `0x18005de50`
- `0x180066ee0`
- `0x18006ba20`
- `0x18008b70c`
- `0x180090d08`
- `0x18009d294`
- `0x18009e198`
- `0x18009eb08`
- `0x1800dcd98`
- `0x1800f1f18`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ef09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ef09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009f0e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009f3d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009f0e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009f3d8`
- `ntdll!RtlCopyLuid` at `0x18009ec90`
- `ntdll!RtlCopyLuid` at `0x18009eca1`
- `ntdll!RtlCopyLuid` at `0x18009ec90`
- `ntdll!RtlCopyLuid` at `0x18009eca1`
- `ntdll!RtlEqualDomainName` at `0x18009f1bb`
- `ntdll!RtlEqualDomainName` at `0x18009f1bb`
- `ntdll!RtlInitUnicodeString` at `0x18009eb9e`
- `ntdll!RtlInitUnicodeString` at `0x18009eb9e`
- `ntdll!RtlReleaseResource` at `0x18009f1cc`
- `ntdll!RtlReleaseResource` at `0x18009f204`
- `ntdll!RtlReleaseResource` at `0x18009f260`
- `ntdll!RtlReleaseResource` at `0x18009f1cc`
- `ntdll!RtlReleaseResource` at `0x18009f204`
- `ntdll!RtlReleaseResource` at `0x18009f260`
- `ntdll!RtlAcquireResourceShared` at `0x18009f1aa`
- `ntdll!RtlAcquireResourceShared` at `0x18009f23e`
- `ntdll!RtlAcquireResourceShared` at `0x18009f1aa`
- `ntdll!RtlAcquireResourceShared` at `0x18009f23e`
- `ntdll!NtAllocateLocallyUniqueId` at `0x18009f52e`
- `ntdll!NtAllocateLocallyUniqueId` at `0x18009f52e`
- `ntdll!RtlEnterCriticalSection` at `0x18009f42a`
- `ntdll!RtlEnterCriticalSection` at `0x18009f600`
- `ntdll!RtlEnterCriticalSection` at `0x18009f6a7`
- `ntdll!RtlEnterCriticalSection` at `0x18009f42a`
- `ntdll!RtlEnterCriticalSection` at `0x18009f600`
- `ntdll!RtlEnterCriticalSection` at `0x18009f6a7`
- `ntdll!RtlLeaveCriticalSection` at `0x18009f46b`
- `ntdll!RtlLeaveCriticalSection` at `0x18009f62d`
- `ntdll!RtlLeaveCriticalSection` at `0x18009f6d7`
- `ntdll!RtlLeaveCriticalSection` at `0x18009f702`
- `ntdll!RtlLeaveCriticalSection` at `0x18009f46b`
- `ntdll!RtlLeaveCriticalSection` at `0x18009f62d`
- `ntdll!RtlLeaveCriticalSection` at `0x18009f6d7`
- `ntdll!RtlLeaveCriticalSection` at `0x18009f702`
- `CRYPT32!CertCreateCertificateContext` at `0x18009eef7`
- `CRYPT32!CertCreateCertificateContext` at `0x18009eef7`
- `CRYPT32!CertFreeCertificateContext` at `0x18009f3ea`
- `CRYPT32!CertFreeCertificateContext` at `0x18009f3ea`

## string_xrefs

- `0x18009ec30`: `Could not get identification LUID or impersonation LUID (impossible situation??)`
- `0x18009ec68`: `Failing S4U due to LocalService\n`
- `0x18009ef0f`: `CertCreateCertificateContext failed with %#x\n`
- `0x18009f56a`: `Failed to create logon session 0x%x`

## pseudocode

```c
__int64 __fastcall KerbS4UToSelfLogon(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned int a3,
        struct _KERB_LOGON_SESSION **a4,
        LUID *LocallyUniqueId,
        struct _KERB_TICKET_CACHE_ENTRY **a6,
        struct _KERB_INTERNAL_NAME **a7,
        PUNICODE_STRING DestinationString,
        PLUID a9)
{
  struct _KERB_TICKET_CACHE_ENTRY **v9; // rax
  struct _KERB_TICKET_CACHE_ENTRY *v10; // rdi
  unsigned __int64 v12; // r12
  struct _KERB_INTERNAL_NAME **v13; // rdx
  struct _UNICODE_STRING *v15; // rcx
  struct _KERB_LOGON_SESSION *v16; // r13
  NTSTATUS S4UClientRealm; // ebx
  unsigned __int64 v18; // rcx
  __int64 v19; // rdx
  unsigned int v20; // ebx
  bool v21; // zf
  _WORD *v22; // r9
  unsigned __int64 v23; // rcx
  __int64 v24; // rdx
  unsigned __int64 v25; // rcx
  BYTE *v26; // r15
  int v27; // edx
  unsigned int v28; // r12d
  __int64 v29; // rdx
  PCCERT_CONTEXT CertificateContext; // rax
  int v31; // edx
  const struct _CERT_CONTEXT *v32; // rbx
  DWORD LastError; // eax
  int PrincipalNameFromCertificate; // eax
  int v35; // ecx
  HLOCAL v36; // rsi
  int DnsNameArrayFromCertificate; // ecx
  int v38; // eax
  unsigned __int64 v39; // rcx
  unsigned __int8 v40; // r8
  struct _UNICODE_STRING *v41; // rbx
  unsigned int v42; // edx
  __int64 v43; // r9
  unsigned int v44; // eax
  unsigned __int8 v45; // r8
  const struct _UNICODE_STRING *v46; // rbx
  struct _KERB_INTERNAL_NAME **v47; // rsi
  struct _RTL_CRITICAL_SECTION *v48; // rax
  struct _KERB_LOGON_SESSION *v49; // r10
  struct _KERB_INTERNAL_NAME **v50; // r15
  struct _RTL_CRITICAL_SECTION *v52; // rbx
  struct _KERB_TICKET_CACHE_ENTRY *v53; // rsi
  int v54; // ecx
  unsigned __int8 v55; // r8
  struct _KERB_INTERNAL_NAME *v56; // rdx
  struct _KERB_INTERNAL_NAME **v57; // rsi
  struct _KERB_LOGON_SESSION **v58; // r15
  int v59; // esi
  struct _KERB_TICKET_CACHE_ENTRY **v60; // rbx
  int v61; // eax
  struct _RTL_CRITICAL_SECTION *v62; // rcx
  struct _UNICODE_STRING *v63; // [rsp+28h] [rbp-D8h]
  unsigned int v64; // [rsp+50h] [rbp-B0h]
  unsigned __int8 *v65; // [rsp+58h] [rbp-A8h]
  struct _KERB_TICKET_CACHE_ENTRY *v66; // [rsp+60h] [rbp-A0h]
  HLOCAL v67; // [rsp+68h] [rbp-98h]
  struct _KERB_LOGON_SESSION *v68; // [rsp+70h] [rbp-90h]
  struct _LUID SourceLuid; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL hMem[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _KERB_INTERNAL_NAME *v71; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *String2[2]; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v73; // [rsp+A8h] [rbp-58h] BYREF
  struct _LUID DestinationLuid; // [rsp+B0h] [rbp-50h] BYREF
  struct _KERB_TICKET_CACHE_ENTRY *v75; // [rsp+B8h] [rbp-48h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+C0h] [rbp-40h]
  char *v77; // [rsp+C8h] [rbp-38h] BYREF
  struct _UNICODE_STRING v78; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v79; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v80; // [rsp+F0h] [rbp-10h]
  __int128 v81; // [rsp+100h] [rbp+0h]
  _OWORD v82[6]; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v83; // [rsp+180h] [rbp+80h] BYREF
  struct _KERB_LOGON_SESSION **v84; // [rsp+198h] [rbp+98h]

  v84 = a4;
  v9 = a6;
  v10 = 0;
  *a4 = 0;
  v12 = a3;
  v13 = a7;
  v15 = DestinationString;
  v16 = 0;
  *v9 = 0;
  v68 = 0;
  *v13 = 0;
  v75 = 0;
  v79 = 0;
  v71 = 0;
  v80 = 0;
  v73 = 0;
  v81 = 0;
  DestinationLuid = (struct _LUID)999LL;
  *(_OWORD *)String2 = 0;
  v67 = 0;
  hMem[0] = 0;
  v83 = 0;
  v66 = 0;
  pCertContext = 0;
  v78 = 0;
  RtlInitUnicodeString(v15, 0);
  S4UClientRealm = ((__int64 (__fastcall *)(__int128 *, __int64))LsaFunctions[1].CreateLogonSession)(&v79, 48);
  SourceLuid = (struct _LUID)v79;
  if ( S4UClientRealm < 0 )
  {
    KerbTracerT::Log(1, "KerbS4UToSelfLogon", 6745, "Failed to get client information: 0x%x", S4UClientRealm);
LABEL_121:
    v36 = v67;
    goto LABEL_122;
  }
  if ( (BYTE3(v80) & 2) != 0 )
  {
    S4UClientRealm = -1073741790;
    goto LABEL_121;
  }
  v82[0] = v79;
  v82[1] = v80;
  v82[2] = v81;
  if ( !(unsigned __int8)GetIdentificationLogonId(v82, &SourceLuid, &v77) )
  {
    KerbTracerT::Log(
      1,
      "KerbS4UToSelfLogon",
      6758,
      "Could not get identification LUID or impersonation LUID (impossible situation??)");
LABEL_7:
    S4UClientRealm = -2146893042;
    goto LABEL_121;
  }
  if ( SourceLuid.LowPart == 997 )
  {
    if ( !SourceLuid.HighPart )
    {
      KerbTracerT::Log(1, "KerbS4UToSelfLogon", 6773, "Failing S4U due to LocalService\n");
      goto LABEL_7;
    }
    goto LABEL_13;
  }
  if ( SourceLuid.LowPart != 996 || SourceLuid.HighPart )
LABEL_13:
    RtlCopyLuid(&DestinationLuid, &SourceLuid);
  RtlCopyLuid(a9, &DestinationLuid);
  v18 = *((_QWORD *)a1 + 4);
  v19 = a1[12];
  if ( v18 )
  {
    if ( (_WORD)v19 )
    {
      if ( v18 >= a2 && (v18 -= a2) == 0
        || v18 > v12
        || v18 + v19 > v12
        || v18 < 0x28
        || (v18 & 1) != 0
        || (a1[13] = v19, *((_QWORD *)a1 + 4) = (char *)a1 + v18, (v19 & 1) != 0) )
      {
        S4UClientRealm = -1073741811;
        v10 = 0;
        goto LABEL_121;
      }
    }
    else
    {
      *((_QWORD *)a1 + 4) = 0;
    }
  }
  else if ( (_WORD)v19 )
  {
    S4UClientRealm = -1073741811;
    v10 = 0;
    goto LABEL_121;
  }
  v20 = 0;
  KerbTracerT::Log(
    21,
    "KerbS4UToSelfLogon",
    6790,
    "KerbS4UToSelfLogon MessageType %#x, Flags %#x\n",
    *(_DWORD *)a1,
    *((_DWORD *)a1 + 1));
  v21 = *(_DWORD *)a1 == 14;
  v22 = a1 + 4;
  v23 = *((_QWORD *)a1 + 2);
  v77 = (char *)(a1 + 4);
  if ( v21 )
  {
    v24 = (unsigned __int16)*v22;
    if ( v23 )
    {
      if ( (_WORD)v24 )
      {
        if ( v23 >= a2 )
        {
          v23 -= a2;
          if ( !v23 )
            goto LABEL_29;
        }
        if ( v23 > v12 )
          goto LABEL_29;
        if ( v23 + v24 > v12 )
          goto LABEL_29;
        if ( v23 < 0x38 )
          goto LABEL_29;
        if ( (v23 & 1) != 0 )
          goto LABEL_29;
        a1[5] = v24;
        *((_QWORD *)a1 + 2) = (char *)a1 + v23;
        if ( (v24 & 1) != 0 )
          goto LABEL_29;
      }
      else
      {
        *((_QWORD *)a1 + 2) = 0;
      }
    }
    else if ( (_WORD)v24 )
    {
LABEL_29:
      S4UClientRealm = -1073741811;
      v10 = 0;
      goto LABEL_121;
    }
    v25 = *((_QWORD *)a1 + 6);
    LODWORD(v16) = *((_DWORD *)a1 + 10);
    if ( v25 )
    {
      if ( (_DWORD)v16 )
      {
        if ( v25 >= a2 )
          v25 -= a2;
        if ( (unsigned int)v16 > (unsigned int)v12 || v25 > (unsigned int)(v12 - (_DWORD)v16) )
          goto LABEL_41;
        v26 = (BYTE *)a1 + v25;
        *((_QWORD *)a1 + 6) = (char *)a1 + v25;
        goto LABEL_50;
      }
      *((_QWORD *)a1 + 6) = 0;
    }
    else if ( (_DWORD)v16 )
    {
LABEL_41:
      S4UClientRealm = -1073741811;
      v10 = 0;
      v16 = 0;
      goto LABEL_121;
    }
    v26 = 0;
LABEL_50:
    v27 = *((_DWORD *)a1 + 1);
    *(_DWORD *)a1 = 12;
    if ( (v27 & 1) != 0 )
    {
      v27 &= ~1u;
      v20 = 65;
      *((_DWORD *)a1 + 1) = v27;
    }
    v23 = v20 | 0x81;
    if ( (v27 & 2) == 0 )
      v23 = v20;
    v28 = v23 | 0x401;
    if ( (v27 & 4) == 0 )
      v28 = v23;
    goto LABEL_67;
  }
  if ( v23 >= a2 )
    v23 -= a2;
  if ( !v23 )
    goto LABEL_29;
  if ( v23 > v12 )
    goto LABEL_29;
  v29 = (unsigned __int16)*v22;
  if ( v23 + v29 > v12 )
    goto LABEL_29;
  if ( v23 < 0x28 )
    goto LABEL_29;
  if ( (v23 & 1) != 0 )
    goto LABEL_29;
  a1[5] = v29;
  *((_QWORD *)a1 + 2) = (char *)a1 + v23;
  if ( (v29 & 1) != 0 )
    goto LABEL_29;
  v28 = 0;
  v26 = 0;
  if ( (a1[2] & 2) != 0 )
    v28 = 129;
LABEL_67:
  if ( *v22 > 0xFFFCu )
  {
    S4UClientRealm = -1073741562;
LABEL_69:
    v10 = 0;
    v16 = 0;
    goto LABEL_121;
  }
  if ( !*v22 && (_DWORD)v16 )
  {
    CertificateContext = CertCreateCertificateContext(0x10001u, v26, (DWORD)v16);
    pCertContext = CertificateContext;
    v32 = CertificateContext;
    if ( !CertificateContext )
    {
      LastError = GetLastError();
      KerbTracerT::Log(1, "KerbS4UToSelfLogon", 6854, "CertCreateCertificateContext failed with %#x\n", LastError);
      S4UClientRealm = -1073741811;
      goto LABEL_69;
    }
    PrincipalNameFromCertificate = KerbGetPrincipalNameFromCertificate(
                                     CertificateContext,
                                     v31,
                                     (struct _UNICODE_STRING *)String2);
    if ( PrincipalNameFromCertificate >= 0 )
    {
      if ( !String2[1] )
        goto LABEL_89;
      if ( !wcsncmp_0(L"@@@", String2[1], 3u) )
      {
        KerbTracerT::Log(
          2,
          "KerbS4UToSelfLogon",
          6891,
          "Got an X500 name from the cert - seeing if there's a DNSHostname we can use instead...");
        DnsNameArrayFromCertificate = KerbGetDnsNameArrayFromCertificate(v32, (struct _UNICODE_STRING **)hMem, &v83);
        if ( DnsNameArrayFromCertificate >= 0 && v83 )
        {
          KerbTracerT::Log(2, "KerbS4UToSelfLogon", 6897, "Yes, trying the DNSHostname instead");
          KerbFreeString(String2);
          v67 = hMem[0];
          v38 = KerbBuildHostSpn((const struct _UNICODE_STRING *)hMem[0], (struct _UNICODE_STRING *)String2);
          S4UClientRealm = v38;
          if ( v38 < 0 )
          {
            KerbTracerT::Log(1, "KerbS4UToSelfLogon", 6905, "Failed to build SPN from DNSHostname: 0x%x", v38);
            goto LABEL_69;
          }
        }
        else
        {
          KerbTracerT::Log(
            2,
            "KerbS4UToSelfLogon",
            6911,
            "Nope, no DNS names - continuing with the X500 (0x%x, got %d names)",
            DnsNameArrayFromCertificate,
            v83);
          LocalFree(hMem[0]);
          v67 = 0;
        }
      }
    }
    else
    {
      KerbTracerT::Log(
        2,
        "KerbS4UToSelfLogon",
        6867,
        "No name specified and no UPN or DN in the cert (0x%x) - seeing if we can get a DNSHostname instead...",
        PrincipalNameFromCertificate);
      v35 = KerbGetDnsNameArrayFromCertificate(v32, (struct _UNICODE_STRING **)hMem, &v83);
      if ( v35 < 0 || !v83 )
      {
        KerbTracerT::Log(1, "KerbS4UToSelfLogon", 6884, "Nope, no DNS names - giving up (0x%x, got %d names)", v35, v83);
        v10 = 0;
        S4UClientRealm = -1073741811;
        v36 = hMem[0];
        v16 = 0;
LABEL_122:
        KerbFreeString(DestinationString);
        v50 = a7;
        KerbFreeKdcName(a7);
        *v50 = 0;
        goto LABEL_123;
      }
      v67 = hMem[0];
      S4UClientRealm = KerbBuildHostSpn((const struct _UNICODE_STRING *)hMem[0], (struct _UNICODE_STRING *)String2);
      if ( S4UClientRealm < 0 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        KerbTracerT::Log(1, "KerbS4UToSelfLogon", 6878, "Failed to build host SPN?");
        goto LABEL_69;
      }
    }
    if ( String2[1] && !wcsncmp_0(L"@@@", String2[1], 3u) )
    {
LABEL_91:
      *(_OWORD *)(a1 + 4) = *(_OWORD *)String2;
      goto LABEL_92;
    }
LABEL_89:
    if ( !a1[12] )
      v28 |= 0x100u;
    goto LABEL_91;
  }
LABEL_92:
  v41 = (struct _UNICODE_STRING *)(a1 + 12);
  if ( !_KerberosSystemRole::IsEnterpriseKdc((_KerberosSystemRole *)v23) )
  {
    *(_OWORD *)hMem = 0;
    if ( v41->Length )
    {
      *(struct _UNICODE_STRING *)hMem = *v41;
      v39 = (unsigned int)_mm_cvtsi128_si32(*(__m128i *)hMem);
    }
    else
    {
      v39 = a1[4];
      v42 = a1[4] >> 1;
      if ( v42 )
      {
        v43 = *((_QWORD *)a1 + 2);
        v44 = 0;
        while ( 1 )
        {
          v40 = v44;
          if ( *(_WORD *)(v43 + 2LL * v44) == 64 )
            break;
          if ( ++v44 >= v42 )
            goto LABEL_98;
        }
        LOWORD(v39) = v39 - 2 * v44 - 2;
        hMem[1] = (HLOCAL)(v43 + 2 + 2LL * v44);
        LOWORD(hMem[0]) = v39;
        WORD1(hMem[0]) = v39;
      }
      else
      {
LABEL_98:
        v39 = LOWORD(hMem[0]);
      }
    }
    if ( (_WORD)v39 )
    {
      RtlAcquireResourceShared(&KerberosGlobalResource, 1u);
      if ( RtlEqualDomainName((PUNICODE_STRING)hMem, &KerbGlobalMachineName) )
      {
        RtlReleaseResource(&KerberosGlobalResource);
        KerbTracerT::Log(2, "KerbS4UToSelfLogon", 6973, "local s4u2self for %wZ\\%wZ not supported\n", a1 + 12, v77);
LABEL_104:
        S4UClientRealm = -1073741730;
        goto LABEL_69;
      }
      RtlReleaseResource(&KerberosGlobalResource);
    }
  }
  if ( v41->Length )
  {
    if ( v41->Length == 2 && **((_WORD **)a1 + 4) == 46 )
    {
      if ( !_KerberosSystemRole::IsEnterpriseKdc((_KerberosSystemRole *)v39) )
      {
        KerbTracerT::Log(
          2,
          "KerbS4UToSelfLogon",
          7009,
          "KerbS4UToSelfLogon fail with no_logon_servers error for . if not on the dc\n");
        goto LABEL_104;
      }
      RtlAcquireResourceShared(&KerberosGlobalResource, 1u);
      S4UClientRealm = KerbDuplicateStringEx(DestinationString, &KerbGlobalDnsDomainName, v45);
      RtlReleaseResource(&KerberosGlobalResource);
    }
    else
    {
      S4UClientRealm = KerbDuplicateStringEx(DestinationString, (const struct _UNICODE_STRING *)(a1 + 12), v40);
    }
    if ( S4UClientRealm < 0 )
      goto LABEL_69;
    v41 = (struct _UNICODE_STRING *)(a1 + 12);
  }
  v63 = v41;
  v46 = (const struct _UNICODE_STRING *)(a1 + 4);
  KerbTracerT::Log(
    21,
    "KerbS4UToSelfLogon",
    7029,
    "KerbS4UToSelfLogon ClientUpn %wZ, ClientRealm %wZ, Flags %#x\n",
    a1 + 4,
    v63,
    *((_DWORD *)a1 + 1));
  v47 = a7;
  S4UClientRealm = KerbProcessTargetNames(v46, 0, 0, 1u, 0, &v73, a7, &v78);
  if ( S4UClientRealm < 0 )
    goto LABEL_69;
  S4UClientRealm = KerbDuplicateKdcName(&v71, *v47);
  if ( S4UClientRealm < 0 )
    goto LABEL_119;
  v48 = (struct _RTL_CRITICAL_SECTION *)KerbLocateLogonSession(&SourceLuid, 0);
  v68 = (struct _KERB_LOGON_SESSION *)v48;
  v49 = (struct _KERB_LOGON_SESSION *)v48;
  if ( !v48 )
  {
    KerbTracerT::Log(
      1,
      "KerbS4UToSelfLogon",
      7064,
      "Failed to locate caller's logon session - %#x:%#x\n",
      SourceLuid.HighPart,
      SourceLuid.LowPart);
    S4UClientRealm = -1073741729;
LABEL_119:
    v16 = v68;
LABEL_120:
    v10 = v66;
    goto LABEL_121;
  }
  if ( (v28 & 1) != 0 )
  {
    v53 = 0;
    goto LABEL_144;
  }
  v52 = v48 + 2;
  RtlEnterCriticalSection(v48 + 2);
  v66 = KerbLocateS4UTicketCacheEntry(
          (struct _KERB_LOGON_SESSION *)((char *)v68 + 320),
          &SourceLuid,
          0,
          DestinationString,
          *v47,
          2u);
  v53 = v66;
  RtlLeaveCriticalSection(v52);
  if ( v66 )
  {
    v54 = *((_DWORD *)v66 + 41) & 0x20;
    if ( (v28 & 0x100) != 0 )
    {
      if ( !v54 )
        goto LABEL_138;
    }
    else if ( v54 )
    {
LABEL_138:
      KerbFreeString(DestinationString);
      S4UClientRealm = KerbDuplicateStringEx(DestinationString, (const struct _UNICODE_STRING *)v66 + 6, v55);
      if ( S4UClientRealm < 0 )
        goto LABEL_119;
      goto LABEL_143;
    }
    KerbDereferenceTicketCacheEntry(v66);
    v53 = 0;
    v66 = 0;
  }
LABEL_143:
  v49 = v68;
LABEL_144:
  if ( !DestinationString->Length )
  {
    v56 = *a7;
    if ( ((*(_WORD *)*a7 - 2) & 0xFFF3) == 0 && *(_WORD *)v56 != 14 )
    {
      S4UClientRealm = KerbGetS4UClientRealm(v49, v56, (unsigned int)v16, v26, DestinationString);
      if ( S4UClientRealm < 0 )
        goto LABEL_119;
    }
  }
  S4UClientRealm = NtAllocateLocallyUniqueId(LocallyUniqueId);
  if ( S4UClientRealm < 0 )
    goto LABEL_119;
  S4UClientRealm = KerbCreateS4ULogonSession(*a7, DestinationString, LocallyUniqueId, v84);
  if ( S4UClientRealm < 0 )
  {
    KerbTracerT::Log(1, "KerbS4UToSelfLogon", 7165, "Failed to create logon session 0x%x", S4UClientRealm);
    goto LABEL_119;
  }
  if ( v53 )
  {
    v60 = a6;
    v10 = 0;
    v58 = v84;
    v16 = v68;
    *a6 = v53;
  }
  else
  {
    v57 = a7;
    v65 = v26;
    v58 = v84;
    v64 = (unsigned int)v16;
    v16 = v68;
    S4UClientRealm = KerbGetS4USelfServiceTicket(v68, *v84, 0, a7, v71, DestinationString, a6, v28, 0, 0, v64, v65);
    if ( S4UClientRealm < 0 )
      goto LABEL_120;
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)*v58 + 2);
    KerbFreeString((char *)*v58 + 120);
    v59 = KerbConvertKdcNameToString((struct _UNICODE_STRING *)((char *)*v58 + 120), *v57, 0);
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)*v58 + 2);
    if ( v59 )
    {
      S4UClientRealm = KerbMapKerbError(v59);
      KerbTracerT::Log(
        1,
        "KerbS4UToSelfLogon",
        7206,
        "KerbConvertKdcNameToString failed to convert S4UClientName: %#x, %#x\n",
        S4UClientRealm,
        v59);
      v10 = v66;
      v36 = v67;
      if ( S4UClientRealm < 0 )
        goto LABEL_122;
      goto LABEL_123;
    }
    v10 = v66;
    v60 = a6;
  }
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)*v58 + 2);
  if ( (v28 & 0x40) != 0 )
    *((_DWORD *)*v58 + 226) |= 0x400u;
  v61 = KerbDuplicateTicketCacheEntry(*v60, &v75);
  v62 = (struct _RTL_CRITICAL_SECTION *)*v58;
  S4UClientRealm = v61;
  if ( v61 < 0 )
  {
    RtlLeaveCriticalSection(v62 + 2);
    goto LABEL_121;
  }
  KerbInsertTicketCacheEntry((struct _KERB_TICKET_CACHE *)&v62[8], v75);
  KerbDereferenceTicketCacheEntry(v75);
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)*v58 + 2);
  v36 = v67;
LABEL_123:
  if ( v71 )
    KerbFreeKdcName(&v71);
  KerbFreeString(&v78);
  if ( v10 )
    KerbDereferenceTicketCacheEntry(v10);
  if ( String2[1] )
    KerbFreeString(String2);
  LocalFree(v36);
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( v16 )
    KerbDereferenceLogonSession(v16);
  return (unsigned int)S4UClientRealm;
}

```

## disassembly

```asm
0x18009eb08  mov     [rsp-8+arg_8], rbx
0x18009eb0d  mov     [rsp-8+arg_18], r9
0x18009eb12  push    rbp
0x18009eb13  push    rsi
0x18009eb14  push    rdi
0x18009eb15  push    r12
0x18009eb17  push    r13
0x18009eb19  push    r14
0x18009eb1b  push    r15
0x18009eb1d  lea     rbp, [rsp-40h]
0x18009eb22  sub     rsp, 140h
0x18009eb29  mov     rax, [rbp+70h+arg_28]
0x18009eb30  xor     edi, edi
0x18009eb32  xorps   xmm0, xmm0
0x18009eb35  mov     [r9], rdi
0x18009eb38  mov     r15, rdx
0x18009eb3b  mov     r12d, r8d
0x18009eb3e  mov     rdx, [rbp+70h+arg_30]
0x18009eb45  mov     rsi, rcx
0x18009eb48  mov     rcx, [rbp+70h+DestinationString]; DestinationString
0x18009eb4f  mov     r13d, edi
0x18009eb52  mov     [rax], rdi
0x18009eb55  mov     [rsp+170h+var_100], rdi
0x18009eb5a  mov     [rdx], rdi
0x18009eb5d  xor     edx, edx; SourceString
0x18009eb5f  mov     [rbp+70h+var_B8], rdi
0x18009eb63  movups  [rbp+70h+var_90], xmm0
0x18009eb67  mov     [rbp+70h+var_E0], rdi
0x18009eb6b  movups  [rbp+70h+var_80], xmm0
0x18009eb6f  mov     [rbp+70h+var_C8], edi
0x18009eb72  movups  [rbp+70h+var_70], xmm0
0x18009eb76  mov     qword ptr [rbp+70h+DestinationLuid.LowPart], 3E7h
0x18009eb7e  movups  xmmword ptr [rbp+70h+String2], xmm0
0x18009eb82  mov     [rsp+170h+var_108], rdi
0x18009eb87  mov     [rbp+70h+hMem], rdi
0x18009eb8b  mov     [rbp+70h+arg_0], edi
0x18009eb91  mov     [rsp+170h+var_110], rdi
0x18009eb96  mov     [rbp+70h+pCertContext], rdi
0x18009eb9a  movups  xmmword ptr [rbp+70h+var_A0.Length], xmm0
0x18009eb9e  call    cs:__imp_RtlInitUnicodeString
0x18009eba4  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18009ebab  lea     edx, [rdi+30h]
0x18009ebae  lea     rcx, [rbp+70h+var_90]
0x18009ebb2  mov     rax, [rax+1F8h]
0x18009ebb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ebbe  mov     ebx, eax
0x18009ebc0  mov     rax, qword ptr [rbp+70h+var_90]
0x18009ebc4  mov     qword ptr [rsp+170h+SourceLuid.LowPart], rax
0x18009ebc9  test    ebx, ebx
0x18009ebcb  jns     short loc_18009EBF2
0x18009ebcd  lea     r9, aFailedToGetCli_4; "Failed to get client information: 0x%x"
0x18009ebd4  mov     dword ptr [rsp+170h+var_150], ebx
0x18009ebd8  mov     r8d, 1A59h
0x18009ebde  lea     rdx, aKerbs4utoselfl_2; "KerbS4UToSelfLogon"
0x18009ebe5  lea     ecx, [rdi+1]
0x18009ebe8  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18009ebed  jmp     loc_18009F377
0x18009ebf2  test    byte ptr [rbp+70h+var_80+3], 2
0x18009ebf6  jz      short loc_18009EC02
0x18009ebf8  mov     ebx, 0C0000022h
0x18009ebfd  jmp     loc_18009F377
0x18009ec02  movups  xmm0, [rbp+70h+var_90]
0x18009ec06  lea     r8, [rbp+70h+var_A8]
0x18009ec0a  movups  xmm1, [rbp+70h+var_80]
0x18009ec0e  lea     rdx, [rsp+170h+SourceLuid]
0x18009ec13  movaps  [rbp+70h+var_60], xmm0
0x18009ec17  lea     rcx, [rbp+70h+var_60]
0x18009ec1b  movups  xmm0, [rbp+70h+var_70]
0x18009ec1f  movaps  [rbp+70h+var_50], xmm1
0x18009ec23  movaps  [rbp+70h+var_40], xmm0
0x18009ec27  call    ?GetIdentificationLogonId@@YA_NU_SECPKG_CLIENT_INFO_EX@@AEAU_LUID@@AEAPEAX@Z; GetIdentificationLogonId(_SECPKG_CLIENT_INFO_EX,_LUID &,void * &)
0x18009ec2c  test    al, al
0x18009ec2e  jnz     short loc_18009EC58
0x18009ec30  lea     r9, aCouldNotGetIde; "Could not get identification LUID or im"...
0x18009ec37  mov     r8d, 1A66h
0x18009ec3d  lea     rdx, aKerbs4utoselfl_2; "KerbS4UToSelfLogon"
0x18009ec44  mov     ecx, 1
0x18009ec49  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18009ec4e  mov     ebx, 8009030Eh
0x18009ec53  jmp     loc_18009F377
0x18009ec58  cmp     [rsp+170h+SourceLuid.LowPart], 3E5h
0x18009ec60  jnz     short loc_18009EC77
0x18009ec62  cmp     [rsp+170h+SourceLuid.HighPart], edi
0x18009ec66  jnz     short loc_18009EC87
0x18009ec68  lea     r9, aFailingS4uDueT; "Failing S4U due to LocalService\n"
0x18009ec6f  mov     r8d, 1A75h
0x18009ec75  jmp     short loc_18009EC3D
0x18009ec77  cmp     [rsp+170h+SourceLuid.LowPart], 3E4h
0x18009ec7f  jnz     short loc_18009EC87
0x18009ec81  cmp     [rsp+170h+SourceLuid.HighPart], edi
0x18009ec85  jz      short loc_18009EC96
0x18009ec87  lea     rdx, [rsp+170h+SourceLuid]; SourceLuid
0x18009ec8c  lea     rcx, [rbp+70h+DestinationLuid]; DestinationLuid
0x18009ec90  call    cs:__imp_RtlCopyLuid
0x18009ec96  mov     rcx, [rbp+70h+arg_40]; DestinationLuid
0x18009ec9d  lea     rdx, [rbp+70h+DestinationLuid]; SourceLuid
0x18009eca1  call    cs:__imp_RtlCopyLuid
0x18009eca7  mov     rcx, [rsi+20h]
0x18009ecab  xor     eax, eax
0x18009ecad  movzx   edx, word ptr [rsi+18h]
0x18009ecb1  mov     edi, 1
0x18009ecb6  test    rcx, rcx
0x18009ecb9  jnz     short loc_18009ECCC
0x18009ecbb  test    dx, dx
0x18009ecbe  jz      short loc_18009ED23
0x18009ecc0  mov     ebx, 0C000000Dh
0x18009ecc5  mov     edi, eax
0x18009ecc7  jmp     loc_18009F377
0x18009eccc  test    dx, dx
0x18009eccf  jnz     short loc_18009ECD7
0x18009ecd1  mov     [rsi+20h], rax
0x18009ecd5  jmp     short loc_18009ED23
0x18009ecd7  cmp     rcx, r15
0x18009ecda  jb      short loc_18009ECE5
0x18009ecdc  sub     rcx, r15
0x18009ecdf  jz      loc_18009F712
0x18009ece5  cmp     rcx, r12
0x18009ece8  ja      loc_18009F712
0x18009ecee  lea     rax, [rcx+rdx]
0x18009ecf2  cmp     rax, r12
0x18009ecf5  ja      loc_18009F712
0x18009ecfb  cmp     rcx, 28h ; '('
0x18009ecff  jb      loc_18009F712
0x18009ed05  test    dil, cl
0x18009ed08  jnz     loc_18009F712
0x18009ed0e  mov     [rsi+1Ah], dx
0x18009ed12  lea     rax, [rcx+rsi]
0x18009ed16  mov     [rsi+20h], rax
0x18009ed1a  test    dil, dl
0x18009ed1d  jnz     loc_18009F712
0x18009ed23  mov     eax, [rsi+4]
0x18009ed26  lea     r14, aKerbs4utoselfl_2; "KerbS4UToSelfLogon"
0x18009ed2d  mov     dword ptr [rsp+170h+var_148], eax
0x18009ed31  lea     r9, aKerbs4utoselfl_0; "KerbS4UToSelfLogon MessageType %#x, Fla"...
0x18009ed38  mov     eax, [rsi]
0x18009ed3a  xor     ebx, ebx
0x18009ed3c  mov     r8d, 1A86h
0x18009ed42  mov     dword ptr [rsp+170h+var_150], eax
0x18009ed46  mov     rdx, r14
0x18009ed49  lea     ecx, [rbx+15h]
0x18009ed4c  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18009ed51  cmp     dword ptr [rsi], 0Eh
0x18009ed54  lea     r9, [rsi+8]
0x18009ed58  mov     rcx, [rsi+10h]
0x18009ed5c  mov     [rbp+70h+var_A8], r9
0x18009ed60  jnz     loc_18009EE4D
0x18009ed66  movzx   edx, word ptr [r9]
0x18009ed6a  xor     r10d, r10d
0x18009ed6d  test    rcx, rcx
0x18009ed70  jnz     short loc_18009ED84
0x18009ed72  test    dx, dx
0x18009ed75  jz      short loc_18009EDC3
0x18009ed77  mov     ebx, 0C000000Dh
0x18009ed7c  mov     rdi, r10
0x18009ed7f  jmp     loc_18009F377
0x18009ed84  test    dx, dx
0x18009ed87  jnz     short loc_18009ED8F
0x18009ed89  mov     [rsi+10h], r10
0x18009ed8d  jmp     short loc_18009EDC3
0x18009ed8f  cmp     rcx, r15
0x18009ed92  jb      short loc_18009ED99
0x18009ed94  sub     rcx, r15
0x18009ed97  jz      short loc_18009ED77
0x18009ed99  cmp     rcx, r12
0x18009ed9c  ja      short loc_18009ED77
0x18009ed9e  lea     rax, [rcx+rdx]
0x18009eda2  cmp     rax, r12
0x18009eda5  ja      short loc_18009ED77
0x18009eda7  cmp     rcx, 38h ; '8'
0x18009edab  jb      short loc_18009ED77
0x18009edad  test    dil, cl
0x18009edb0  jnz     short loc_18009ED77
0x18009edb2  mov     [rsi+0Ah], dx
0x18009edb6  lea     rax, [rcx+rsi]
0x18009edba  mov     [rsi+10h], rax
0x18009edbe  test    dil, dl
0x18009edc1  jnz     short loc_18009ED77
0x18009edc3  mov     rcx, [rsi+30h]
0x18009edc7  mov     r13d, [rsi+28h]
0x18009edcb  test    rcx, rcx
0x18009edce  jnz     short loc_18009EDE5
0x18009edd0  test    r13d, r13d
0x18009edd3  jz      short loc_18009EDEE
0x18009edd5  mov     ebx, 0C000000Dh
0x18009edda  mov     rdi, r10
0x18009eddd  mov     r13, r10
0x18009ede0  jmp     loc_18009F377
0x18009ede5  test    r13d, r13d
0x18009ede8  jnz     short loc_18009EDF3
0x18009edea  mov     [rsi+30h], r10
0x18009edee  mov     r15, r10
0x18009edf1  jmp     short loc_18009EE13
0x18009edf3  cmp     rcx, r15
0x18009edf6  jb      short loc_18009EDFB
0x18009edf8  sub     rcx, r15
0x18009edfb  cmp     r13d, r12d
0x18009edfe  ja      short loc_18009EDD5
0x18009ee00  sub     r12d, r13d
0x18009ee03  mov     eax, r12d
0x18009ee06  cmp     rcx, rax
0x18009ee09  ja      short loc_18009EDD5
0x18009ee0b  lea     r15, [rcx+rsi]
0x18009ee0f  mov     [rsi+30h], r15
0x18009ee13  mov     edx, [rsi+4]
0x18009ee16  mov     dword ptr [rsi], 0Ch
0x18009ee1c  test    dil, dl
0x18009ee1f  jz      short loc_18009EE2C
0x18009ee21  and     edx, 0FFFFFFFEh
0x18009ee24  mov     ebx, 41h ; 'A'
0x18009ee29  mov     [rsi+4], edx
0x18009ee2c  mov     ecx, ebx
0x18009ee2e  or      ecx, 81h
0x18009ee34  test    dl, 2
0x18009ee37  cmovz   ecx, ebx
0x18009ee3a  mov     r12d, ecx
0x18009ee3d  or      r12d, 401h
0x18009ee44  test    dl, 4
0x18009ee47  cmovz   r12d, ecx
0x18009ee4b  jmp     short loc_18009EEBC
0x18009ee4d  mov     rax, rcx
0x18009ee50  sub     rax, r15
0x18009ee53  cmp     rcx, r15
0x18009ee56  cmovnb  rcx, rax
0x18009ee5a  xor     r10d, r10d
0x18009ee5d  test    rcx, rcx
0x18009ee60  jz      loc_18009ED77
0x18009ee66  cmp     rcx, r12
0x18009ee69  ja      loc_18009ED77
0x18009ee6f  movzx   edx, word ptr [r9]
0x18009ee73  lea     rax, [rcx+rdx]
0x18009ee77  cmp     rax, r12
0x18009ee7a  ja      loc_18009ED77
0x18009ee80  cmp     rcx, 28h ; '('
0x18009ee84  jb      loc_18009ED77
0x18009ee8a  test    dil, cl
0x18009ee8d  jnz     loc_18009ED77
0x18009ee93  mov     [rsi+0Ah], dx
0x18009ee97  lea     rax, [rcx+rsi]
0x18009ee9b  mov     [rsi+10h], rax
0x18009ee9f  test    dil, dl
0x18009eea2  jnz     loc_18009ED77
0x18009eea8  test    byte ptr [rsi+4], 2
0x18009eeac  mov     r8d, 81h
0x18009eeb2  mov     r12d, ebx
0x18009eeb5  mov     r15d, r10d
0x18009eeb8  cmovnz  r12d, r8d
0x18009eebc  mov     eax, 0FFFCh
0x18009eec1  cmp     [r9], ax
0x18009eec5  jbe     short loc_18009EED9
0x18009eec7  mov     ebx, 0C0000106h
0x18009eecc  mov     rdi, [rsp+170h+var_110]
0x18009eed1  mov     r13, rdi
0x18009eed4  jmp     loc_18009F377
0x18009eed9  cmp     [r9], r10w
0x18009eedd  jnz     loc_18009F127
0x18009eee3  test    r13d, r13d
0x18009eee6  jz      loc_18009F127
0x18009eeec  mov     r8d, r13d; cbCertEncoded
0x18009eeef  mov     rdx, r15; pbCertEncoded
0x18009eef2  mov     ecx, 10001h; dwCertEncodingType
0x18009eef7  call    cs:__imp_CertCreateCertificateContext
0x18009eefd  mov     [rbp+70h+pCertContext], rax
0x18009ef01  mov     rbx, rax
0x18009ef04  test    rax, rax
0x18009ef07  jnz     short loc_18009EF31
0x18009ef09  call    cs:__imp_GetLastError
0x18009ef0f  lea     r9, aCertcreatecert_0; "CertCreateCertificateContext failed wit"...
0x18009ef16  mov     r8d, 1AC6h
0x18009ef1c  mov     rdx, r14
0x18009ef1f  mov     dword ptr [rsp+170h+var_150], eax
0x18009ef23  mov     ecx, edi
0x18009ef25  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18009ef2a  mov     ebx, 0C000000Dh
0x18009ef2f  jmp     short loc_18009EECC
0x18009ef31  lea     r8, [rbp+70h+String2]; struct _UNICODE_STRING *
0x18009ef35  mov     rcx, rbx; struct _CERT_CONTEXT *
0x18009ef38  call    ?KerbGetPrincipalNameFromCertificate@@YAJPEBU_CERT_CONTEXT@@HPEAU_UNICODE_STRING@@@Z; KerbGetPrincipalNameFromCertificate(_CERT_CONTEXT const *,int,_UNICODE_STRING *)
0x18009ef3d  test    eax, eax
0x18009ef3f  jns     loc_18009EFFB
0x18009ef45  lea     r9, aNoNameSpecifie; "No name specified and no UPN or DN in t"...
0x18009ef4c  mov     dword ptr [rsp+170h+var_150], eax
0x18009ef50  mov     r8d, 1AD3h
0x18009ef56  mov     rdx, r14
0x18009ef59  mov     ecx, 2
0x18009ef5e  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18009ef63  lea     r8, [rbp+70h+arg_0]; unsigned int *
0x18009ef6a  mov     rcx, rbx; struct _CERT_CONTEXT *
0x18009ef6d  lea     rdx, [rbp+70h+hMem]; struct _UNICODE_STRING **
0x18009ef71  call    ?KerbGetDnsNameArrayFromCertificate@@YAJPEBU_CERT_CONTEXT@@PEAPEAU_UNICODE_STRING@@PEAK@Z; KerbGetDnsNameArrayFromCertificate(_CERT_CONTEXT const *,_UNICODE_STRING * *,ulong *)
0x18009ef76  mov     ecx, eax
0x18009ef78  mov     eax, [rbp+70h+arg_0]
0x18009ef7e  test    ecx, ecx
0x18009ef80  js      short loc_18009EFC6
0x18009ef82  test    eax, eax
0x18009ef84  jz      short loc_18009EFC6
0x18009ef86  mov     rax, [rbp+70h+hMem]
0x18009ef8a  lea     rdx, [rbp+70h+String2]; struct _UNICODE_STRING *
0x18009ef8e  mov     rcx, rax; struct _UNICODE_STRING *
0x18009ef91  mov     [rsp+170h+var_108], rax
0x18009ef96  call    ?KerbBuildHostSpn@@YAJPEBU_UNICODE_STRING@@PEAU1@@Z; KerbBuildHostSpn(_UNICODE_STRING const *,_UNICODE_STRING *)
  ... truncated ...
```
