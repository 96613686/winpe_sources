# KerbCacheSmartCardLogon(_UNICODE_STRING *,_UNICODE_STRING *,_NETLOGON_VALIDATION_SAM_INFO4 *,_LSA_TOKEN_INFORMATION_V3 *,_KERB_LOGON_SESSION *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *,void *,ulong)

- ea: `0x1800b72b4`
- end: `0x1800b7a1c`
- name: `?KerbCacheSmartCardLogon@@YAXPEAU_UNICODE_STRING@@0PEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAU_LSA_TOKEN_INFORMATION_V3@@PEAU_KERB_LOGON_SESSION@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@PEAXK@Z`
- size: `1896`
- prototype: `void(struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _NETLOGON_VALIDATION_SAM_INFO4 *, struct _LSA_TOKEN_INFORMATION_V3 *, struct _KERB_LOGON_SESSION *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **, void *, unsigned int)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800819b0`

## callees

- `0x1800068d0`
- `0x1800069a0`
- `0x1800093f0`
- `0x180032964`
- `0x180037128`
- `0x18003ca2c`
- `0x180060148`
- `0x1800603d8`
- `0x18006e6e8`
- `0x180070680`
- `0x18007108c`
- `0x18008b70c`
- `0x1800b72b4`
- `0x1800b8ef4`
- `0x1800b9dd0`
- `0x1800bb814`
- `0x1800bbb14`
- `0x1800de900`
- `0x1800de9c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800b7539`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800b7539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b73b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b74f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7566`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b75be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b762f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b76b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b73b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b74f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7566`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b75be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b762f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b76b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b79db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b79db`
- `ntdll!RtlEqualUnicodeString` at `0x1800b779b`
- `ntdll!RtlEqualUnicodeString` at `0x1800b779b`
- `ntdll!RtlEnterCriticalSection` at `0x1800b735b`
- `ntdll!RtlEnterCriticalSection` at `0x1800b735b`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b7992`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b7992`
- `bcrypt!BCryptDestroyKey` at `0x1800b79f3`
- `bcrypt!BCryptDestroyKey` at `0x1800b79f3`
- `CRYPT32!CertGetPublicKeyLength` at `0x1800b755c`
- `CRYPT32!CertGetPublicKeyLength` at `0x1800b755c`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x1800b73ac`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x1800b73ac`
- `CRYPTSP!SystemFunction007` at `0x1800b78a2`
- `CRYPTSP!SystemFunction007` at `0x1800b78a2`

## string_xrefs

- `0x1800b746e`: `KerbGetUserNameForSmartcardCache failed: %#x\n`
- `0x1800b73c8`: `KerbCacheSmartCardLogon`
- `0x1800b747b`: `KerbCacheSmartCardLogon`
- `0x1800b7508`: `KerbCacheSmartCardLogon`
- `0x1800b759a`: `KerbCacheSmartCardLogon`
- `0x1800b76cd`: `KerbCacheSmartCardLogon`
- `0x1800b786f`: `KerbCacheSmartCardLogon`
- `0x1800b7977`: `KerbCacheSmartCardLogon`
- `0x1800b7862`: `Unable to update password logon cache entry!\n`
- `0x1800b796a`: `KerbCacheLogonInformation failed: %#x\n`

## pseudocode

```c
void __fastcall KerbCacheSmartCardLogon(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        struct _NETLOGON_VALIDATION_SAM_INFO4 *a3,
        struct _LSA_TOKEN_INFORMATION_V3 *a4,
        struct _RTL_CRITICAL_SECTION *a5,
        struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **a6,
        void *a7,
        unsigned int a8)
{
  unsigned int v9; // r14d
  int LockSemaphore; // esi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rax
  __int64 v12; // rdx
  DWORD LastError; // eax
  unsigned __int8 *v14; // rsi
  int v15; // esi
  __int64 v16; // rcx
  signed int UserNameForSmartcardCache; // eax
  const char *v18; // r9
  __int64 v19; // r8
  int v20; // esi
  DWORD v21; // eax
  const char *v22; // r9
  __int64 v23; // r8
  __int64 v24; // rdx
  DWORD PublicKeyLength; // eax
  int v26; // eax
  __int64 v27; // rdx
  HLOCAL v28; // r14
  int v29; // esi
  DWORD v30; // eax
  void *v31; // r12
  unsigned int v32; // r14d
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *v33; // rcx
  unsigned int v34; // r14d
  __int64 v35; // rsi
  BOOLEAN v36; // al
  unsigned int CredentialSize; // edx
  struct _MSV1_0_IUM_SUPPLEMENTAL_CREDENTIAL *v38; // r9
  PUCHAR Credentials; // rax
  struct _LM_OWF_PASSWORD *v40; // r8
  int v41; // eax
  const char *v42; // r9
  __int64 v43; // r8
  unsigned __int8 *v44; // rax
  __int64 v45; // rdx
  PCERT_PUBLIC_KEY_INFO pInfo; // [rsp+20h] [rbp-E0h]
  unsigned int pInfoa; // [rsp+20h] [rbp-E0h]
  BYTE *pbComputedHash; // [rsp+28h] [rbp-D8h]
  size_t v49; // [rsp+50h] [rbp-B0h]
  size_t size; // [rsp+60h] [rbp-A0h] BYREF
  void *v51; // [rsp+68h] [rbp-98h]
  HLOCAL hMem; // [rsp+70h] [rbp-90h]
  unsigned int v53; // [rsp+78h] [rbp-88h] BYREF
  void *v54; // [rsp+80h] [rbp-80h]
  DWORD pcbComputedHash; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v56; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned __int8 *v57; // [rsp+90h] [rbp-70h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+98h] [rbp-68h] BYREF
  UNICODE_STRING String2; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 *v60; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING *v61; // [rsp+B8h] [rbp-48h]
  struct _UNICODE_STRING *v62; // [rsp+C0h] [rbp-40h]
  __int128 v63; // [rsp+C8h] [rbp-38h] BYREF
  struct _UNICODE_STRING v64; // [rsp+D8h] [rbp-28h] BYREF
  struct _CRYPTOAPI_BLOB v65; // [rsp+E8h] [rbp-18h] BYREF
  PRTL_CRITICAL_SECTION CriticalSection; // [rsp+F8h] [rbp-8h]
  struct _UNICODE_STRING v67; // [rsp+100h] [rbp+0h] BYREF
  struct _UNICODE_STRING v68; // [rsp+110h] [rbp+10h] BYREF
  struct _LM_OWF_PASSWORD v69; // [rsp+120h] [rbp+20h] BYREF
  UCHAR pbBuffer[64]; // [rsp+130h] [rbp+30h] BYREF
  BYTE v71[24]; // [rsp+170h] [rbp+70h] BYREF

  v54 = a7;
  v62 = a1;
  v9 = 0;
  *(_QWORD *)&String2.Length = a4;
  v61 = a2;
  v67 = 0;
  pcbComputedHash = 0;
  v64 = 0;
  v53 = 0;
  v68 = 0;
  v57 = 0;
  v63 = 0;
  LODWORD(size) = 0;
  v51 = 0;
  v69 = 0;
  hKey = 0;
  v65 = 0;
  hMem = 0;
  v60 = 0;
  v56 = 0;
  CriticalSection = a5 + 2;
  RtlEnterCriticalSection(a5 + 2);
  LockSemaphore = (int)a5[22].LockSemaphore;
  DebugInfo = a5[10].DebugInfo;
  pcbComputedHash = 20;
  if ( !CryptHashPublicKeyInfo(
          0,
          0x8004u,
          0,
          0x10001u,
          (PCERT_PUBLIC_KEY_INFO)(*(_QWORD *)(*(_QWORD *)&DebugInfo->EntryCount + 24LL) + 96LL),
          v71,
          &pcbComputedHash) )
  {
    LastError = GetLastError();
    KerbTracerT::Log(1, "KerbCacheSmartCardLogon", 6972, "Failed to hash public key info: %#x", LastError);
    v14 = 0;
    goto LABEL_69;
  }
  LOBYTE(v12) = 1;
  v15 = LockSemaphore & 0x1000000;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_NGCKeyUsagePhase1>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_NGCKeyUsagePhase1>::GetImpl'::`2'::impl,
    v12);
  if ( (HIDWORD(a5[10].DebugInfo[1].CriticalSection) & 0x400) != 0 )
  {
    if ( (int)KerbGetNgcEncryptedPublicKey(a3, &v60, &v56) >= 0 )
    {
      v9 = v56;
      hMem = v60;
    }
    else
    {
      hMem = 0;
      MicrosoftTelemetryAssertTriggeredNoArgs(v16);
    }
  }
  UserNameForSmartcardCache = KerbGetUserNameForSmartcardCache(
                                *(_QWORD *)&a5[10].DebugInfo->EntryCount,
                                v62,
                                v61,
                                (unsigned int)(v15 != 0) + 1,
                                &v64);
  if ( UserNameForSmartcardCache < 0 )
  {
    v18 = "KerbGetUserNameForSmartcardCache failed: %#x\n";
    v19 = 7020;
LABEL_9:
    LODWORD(pInfo) = UserNameForSmartcardCache;
    KerbTracerT::Log(1, "KerbCacheSmartCardLogon", v19, v18, pInfo);
LABEL_10:
    v14 = (unsigned __int8 *)v51;
    goto LABEL_69;
  }
  if ( a6 )
  {
    memset_0(pbBuffer, 0, sizeof(pbBuffer));
    if ( KerbFilterAndEncodeCachedCredentialData(*(struct _LSA_TOKEN_INFORMATION_V3 **)&String2.Length, a6, &v57, &v53) < 0
      || (BYTE4(a5[10].DebugInfo[1].CriticalSection) & 1) == 0
      && KerbInitializePkCreds((struct _KERB_PRIMARY_CREDENTIAL *)&a5[3], 0) < 0 )
    {
      goto LABEL_10;
    }
    v20 = ScHelperGenRandBits(pbBuffer);
    if ( v20 < 0 )
    {
      v21 = GetLastError();
      v22 = "Failed to generate random bits: 0x%x, last error: %#x\n";
      v23 = 7058;
LABEL_17:
      LODWORD(pbComputedHash) = v21;
      LODWORD(pInfo) = v20;
      KerbTracerT::Log(1, "KerbCacheSmartCardLogon", v23, v22, pInfo, pbComputedHash);
      goto LABEL_10;
    }
    if ( !(unsigned int)_o__stricmp(
                          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&a5[10].DebugInfo->EntryCount + 24LL) + 96LL),
                          "1.2.840.10045.2.1") )
    {
      PublicKeyLength = CertGetPublicKeyLength(
                          **(_DWORD **)&a5[10].DebugInfo->EntryCount,
                          (PCERT_PUBLIC_KEY_INFO)(*(_QWORD *)(*(_QWORD *)&a5[10].DebugInfo->EntryCount + 24LL) + 96LL));
      if ( !PublicKeyLength )
      {
        UserNameForSmartcardCache = GetLastError();
        v18 = "Failed to retrieve bit length: %#x\n";
        v19 = 7072;
        goto LABEL_9;
      }
      if ( (unsigned int)KerbGenerateECDHKey(PublicKeyLength, &hKey) )
      {
        KerbTracerT::Log(1, "KerbCacheSmartCardLogon", 7082, "Failed to generate public key\n");
        goto LABEL_10;
      }
      if ( !(unsigned int)KerbGetECDHPublicKey(hKey, &v65) )
      {
        UserNameForSmartcardCache = GetLastError();
        v18 = "Failed to encode ECDH public key: %#x\n";
        v19 = 7089;
        goto LABEL_9;
      }
    }
    LOBYTE(v24) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_NGCKeyUsagePhase1>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_NGCKeyUsagePhase1>::GetImpl'::`2'::impl,
      v24);
    v26 = __ScHelperEncryptCredentialsEX(
            (struct _KERB_PRIMARY_CREDENTIAL *)&a5[3],
            (struct _ScHelper_RandomCredBits *)pbBuffer,
            &v65,
            (unsigned __int8 *)hMem,
            v9,
            v57,
            v53,
            0,
            (unsigned int *)&size);
    v20 = v26;
    if ( v26 && v26 != -1073741789 )
    {
      v21 = GetLastError();
      v22 = "Failed to encrypt creds: 0x%x, last error: %#x\n";
      v23 = 7124;
      goto LABEL_17;
    }
    v51 = MIDL_user_allocate((unsigned int)size);
    v14 = (unsigned __int8 *)v51;
    if ( !v51 )
      goto LABEL_69;
    LOBYTE(v27) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_NGCKeyUsagePhase1>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_NGCKeyUsagePhase1>::GetImpl'::`2'::impl,
      v27);
    pInfoa = v9;
    v28 = hMem;
    v29 = __ScHelperEncryptCredentialsEX(
            (struct _KERB_PRIMARY_CREDENTIAL *)&a5[3],
            (struct _ScHelper_RandomCredBits *)pbBuffer,
            &v65,
            (unsigned __int8 *)hMem,
            pInfoa,
            v57,
            v53,
            v14,
            (unsigned int *)&size);
    if ( v29 )
    {
      v30 = GetLastError();
      KerbTracerT::Log(
        1,
        "KerbCacheSmartCardLogon",
        7169,
        "Failed to encrypt creds 2: 0x%x, last error: %#x\n",
        v29,
        v30);
      v14 = (unsigned __int8 *)v51;
      goto LABEL_70;
    }
  }
  if ( (*((_DWORD *)a3 + 60) & 0x1000) == 0 )
  {
    if ( !a6 )
      goto LABEL_60;
    v33 = *a6;
    if ( !*a6 )
      goto LABEL_60;
    *(_QWORD *)&String2.Length = 655368;
    String2.Buffer = (PWSTR)L"NTLM";
    if ( !v33->CredentialCount )
      goto LABEL_60;
    v34 = 0;
    while ( 1 )
    {
      v35 = v34;
      v36 = RtlEqualUnicodeString(&v33->Credentials[v35].PackageName, &String2, 1u);
      v33 = *a6;
      if ( v36 )
        break;
      if ( ++v34 >= v33->CredentialCount )
        goto LABEL_60;
    }
    CredentialSize = v33->Credentials[v35].CredentialSize;
    v38 = 0;
    Credentials = v33->Credentials[v35].Credentials;
    if ( CredentialSize < 0x28 || *(_DWORD *)Credentials || (Credentials[4] & 2) == 0 )
    {
      if ( CredentialSize >= 0x2C && *(_DWORD *)Credentials == 2 && (Credentials[4] & 2) != 0 )
      {
        v40 = (struct _LM_OWF_PASSWORD *)(Credentials + 8);
      }
      else
      {
        if ( CredentialSize < 0x44 || *(_DWORD *)Credentials != 4 || (Credentials[4] & 2) == 0 )
        {
          if ( CredentialSize < 0xC || *(_DWORD *)Credentials != -65535 )
          {
LABEL_59:
            KerbTracerT::Log(1, "KerbCacheSmartCardLogon", 7256, "Unable to update password logon cache entry!\n");
LABEL_60:
            v31 = v54;
            goto LABEL_61;
          }
          v40 = 0;
          v38 = (struct _MSV1_0_IUM_SUPPLEMENTAL_CREDENTIAL *)v33->Credentials[v35].Credentials;
LABEL_57:
          if ( v38 )
            goto LABEL_58;
          goto LABEL_59;
        }
        v40 = (struct _LM_OWF_PASSWORD *)(Credentials + 12);
      }
    }
    else
    {
      v40 = (struct _LM_OWF_PASSWORD *)(Credentials + 24);
    }
    if ( v40 )
    {
LABEL_58:
      v31 = v54;
      LODWORD(v49) = a8;
      KerbCacheLogonInformation(
        (struct _UNICODE_STRING *)a3 + 3,
        (struct _UNICODE_STRING *)a3 + 13,
        v40,
        v38,
        (struct _KERB_LOGON_SESSION *)a5,
        0,
        a3,
        0,
        0,
        v54,
        v49,
        0);
LABEL_61:
      v32 = size;
      v14 = (unsigned __int8 *)v51;
      goto LABEL_62;
    }
    goto LABEL_57;
  }
  v31 = v54;
  v32 = size;
  v14 = (unsigned __int8 *)v51;
  LODWORD(v49) = a8;
  KerbCacheLogonInformation(
    (struct _UNICODE_STRING *)a3 + 3,
    (struct _UNICODE_STRING *)a3 + 13,
    0,
    0,
    (struct _KERB_LOGON_SESSION *)a5,
    4u,
    a3,
    v51,
    size,
    v54,
    v49,
    0);
LABEL_62:
  LODWORD(v63) = 1310740;
  *((_QWORD *)&v63 + 1) = v71;
  v41 = SystemFunction007(&v63, &v69);
  if ( v41 >= 0 )
  {
    if ( KerbGetUserNamesForSmartcardCache(
           *(const struct _CERT_CONTEXT **)&a5[10].DebugInfo->EntryCount,
           v62,
           v61,
           &v64,
           &v67) >= 0 )
    {
      LODWORD(v49) = 0;
      KerbCacheLogonInformation(&v67, &v68, 0, 0, (struct _KERB_LOGON_SESSION *)a5, 4u, 0, 0, 0, 0, v49, 0);
    }
    LODWORD(v49) = a8;
    v41 = KerbCacheLogonInformation(
            &v64,
            &v68,
            &v69,
            0,
            (struct _KERB_LOGON_SESSION *)a5,
            8u,
            a3,
            v14,
            v32,
            v31,
            v49,
            0);
    if ( v41 >= 0 )
      goto LABEL_69;
    v42 = "KerbCacheLogonInformation failed: %#x\n";
    v43 = 7329;
  }
  else
  {
    v42 = "Failed to calculate NT OWF %#x\n";
    v43 = 7277;
  }
  LODWORD(pInfo) = v41;
  KerbTracerT::Log(1, "KerbCacheSmartCardLogon", v43, v42, pInfo);
LABEL_69:
  v28 = hMem;
LABEL_70:
  RtlLeaveCriticalSection(CriticalSection);
  KerbFreeString((__int64)&v67);
  KerbFreeString((__int64)&v64);
  v44 = v57;
  if ( v57 )
  {
    v45 = v53;
    if ( v53 )
    {
      do
      {
        *v44++ = 0;
        --v45;
      }
      while ( v45 );
    }
    KerbFree(v57);
  }
  KerbFree(v14);
  LocalFree(v28);
  KerbFree(v65.pbData);
  if ( hKey )
    BCryptDestroyKey(hKey);
}

```

## disassembly

```asm
0x1800b72b4  push    rbp
0x1800b72b6  push    rbx
0x1800b72b7  push    rsi
0x1800b72b8  push    rdi
0x1800b72b9  push    r12
0x1800b72bb  push    r13
0x1800b72bd  push    r14
0x1800b72bf  push    r15
0x1800b72c1  lea     rbp, [rsp-98h]
0x1800b72c9  sub     rsp, 198h
0x1800b72d0  mov     rax, cs:__security_cookie
0x1800b72d7  xor     rax, rsp
0x1800b72da  mov     [rbp+0D0h+var_48], rax
0x1800b72e1  mov     rax, [rbp+0D0h+arg_30]
0x1800b72e8  xor     ebx, ebx
0x1800b72ea  mov     rdi, [rbp+0D0h+arg_20]
0x1800b72f1  xorps   xmm0, xmm0
0x1800b72f4  mov     r12, [rbp+0D0h+arg_28]
0x1800b72fb  xorps   xmm1, xmm1
0x1800b72fe  mov     [rbp+0D0h+var_150], rax
0x1800b7302  mov     r15, r8
0x1800b7305  mov     [rbp+0D0h+var_110], rcx
0x1800b7309  mov     r14d, ebx
0x1800b730c  lea     rax, [rdi+50h]
0x1800b7310  mov     qword ptr [rbp+0D0h+String2.Length], r9
0x1800b7314  mov     rcx, rax; CriticalSection
0x1800b7317  mov     [rbp+0D0h+var_118], rdx
0x1800b731b  movups  xmmword ptr [rbp+0D0h+var_D0.Length], xmm0
0x1800b731f  mov     [rbp+0D0h+var_148], ebx
0x1800b7322  movups  xmmword ptr [rbp+0D0h+var_F8.Length], xmm1
0x1800b7326  mov     [rsp+1D0h+var_158], ebx
0x1800b732a  movups  xmmword ptr [rbp+0D0h+var_C0.Length], xmm0
0x1800b732e  mov     [rbp+0D0h+var_140], rbx
0x1800b7332  movups  [rbp+0D0h+var_108], xmm0
0x1800b7336  mov     dword ptr [rsp+1D0h+size], ebx
0x1800b733a  mov     [rsp+1D0h+var_168], rbx
0x1800b733f  movups  xmmword ptr [rbp+0D0h+var_B0.data.data], xmm0
0x1800b7343  mov     [rbp+0D0h+hKey], rbx
0x1800b7347  movups  xmmword ptr [rbp+0D0h+var_E8.cbData], xmm1
0x1800b734b  mov     [rsp+1D0h+hMem], rbx
0x1800b7350  mov     [rbp+0D0h+var_120], rbx
0x1800b7354  mov     [rbp+0D0h+var_144], ebx
0x1800b7357  mov     [rbp+0D0h+CriticalSection], rax
0x1800b735b  call    cs:__imp_RtlEnterCriticalSection
0x1800b7361  mov     esi, [rdi+388h]
0x1800b7367  lea     r13, [rdi+78h]
0x1800b736b  mov     rax, [r13+118h]
0x1800b7372  mov     r9d, 10001h; dwCertEncodingType
0x1800b7378  mov     [rbp+0D0h+var_148], 14h
0x1800b737f  xor     r8d, r8d; dwFlags
0x1800b7382  mov     edx, 8004h; Algid
0x1800b7387  mov     rcx, [rax+20h]
0x1800b738b  mov     rax, [rcx+18h]
0x1800b738f  lea     rcx, [rbp+0D0h+var_148]
0x1800b7393  mov     [rsp+1D0h+pcbComputedHash], rcx; pcbComputedHash
0x1800b7398  add     rax, 60h ; '`'
0x1800b739c  lea     rcx, [rbp+0D0h+var_60]
0x1800b73a0  mov     [rsp+1D0h+pbComputedHash], rcx; pbComputedHash
0x1800b73a5  xor     ecx, ecx; hCryptProv
0x1800b73a7  mov     [rsp+1D0h+pInfo], rax; pInfo
0x1800b73ac  call    cs:__imp_CryptHashPublicKeyInfo
0x1800b73b2  test    eax, eax
0x1800b73b4  jnz     short loc_1800B73E8
0x1800b73b6  call    cs:__imp_GetLastError
0x1800b73bc  mov     ebx, 1
0x1800b73c1  lea     r9, aFailedToHashPu; "Failed to hash public key info: %#x"
0x1800b73c8  lea     rdx, aKerbcachesmart; "KerbCacheSmartCardLogon"
0x1800b73cf  mov     dword ptr [rsp+1D0h+pInfo], eax
0x1800b73d3  mov     ecx, ebx
0x1800b73d5  mov     r8d, 1B3Ch
0x1800b73db  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b73e0  mov     esi, r14d
0x1800b73e3  jmp     loc_1800B7989
0x1800b73e8  mov     ebx, 1
0x1800b73ed  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NGCKeyUsagePhase1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NGCKeyUsagePhase1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NGCKeyUsagePhase1> `wil::Feature<__WilFeatureTraits_Feature_NGCKeyUsagePhase1>::GetImpl(void)'::`2'::impl
0x1800b73f4  mov     dl, bl
0x1800b73f6  and     esi, 1000000h
0x1800b73fc  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_NGCKeyUsagePhase1@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NGCKeyUsagePhase1>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800b7401  mov     rax, [rdi+190h]
0x1800b7408  test    dword ptr [rax+3Ch], 400h
0x1800b740f  jz      short loc_1800B743E
0x1800b7411  lea     r8, [rbp+0D0h+var_144]; unsigned int *
0x1800b7415  mov     rcx, r15; struct _NETLOGON_VALIDATION_SAM_INFO4 *
0x1800b7418  lea     rdx, [rbp+0D0h+var_120]; unsigned __int8 **
0x1800b741c  call    ?KerbGetNgcEncryptedPublicKey@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAPEAEPEAK@Z; KerbGetNgcEncryptedPublicKey(_NETLOGON_VALIDATION_SAM_INFO4 *,uchar * *,ulong *)
0x1800b7421  test    eax, eax
0x1800b7423  jns     short loc_1800B7431
0x1800b7425  mov     [rsp+1D0h+hMem], r14
0x1800b742a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800b742f  jmp     short loc_1800B743E
0x1800b7431  mov     rax, [rbp+0D0h+var_120]
0x1800b7435  mov     r14d, [rbp+0D0h+var_144]
0x1800b7439  mov     [rsp+1D0h+hMem], rax
0x1800b743e  mov     rcx, [rdi+190h]
0x1800b7445  lea     rax, [rbp+0D0h+var_F8]
0x1800b7449  mov     r8, [rbp+0D0h+var_118]
0x1800b744d  neg     esi
0x1800b744f  mov     rdx, [rbp+0D0h+var_110]
0x1800b7453  sbb     r9d, r9d
0x1800b7456  mov     [rsp+1D0h+pInfo], rax
0x1800b745b  mov     rcx, [rcx+20h]
0x1800b745f  neg     r9d
0x1800b7462  add     r9d, ebx
0x1800b7465  call    ?KerbGetUserNameForSmartcardCache@@YAJPEBU_CERT_CONTEXT@@PEAU_UNICODE_STRING@@1W4_CertificateNameFormat@@1@Z; KerbGetUserNameForSmartcardCache(_CERT_CONTEXT const *,_UNICODE_STRING *,_UNICODE_STRING *,_CertificateNameFormat,_UNICODE_STRING *)
0x1800b746a  test    eax, eax
0x1800b746c  jns     short loc_1800B7497
0x1800b746e  lea     r9, aKerbgetusernam_1; "KerbGetUserNameForSmartcardCache failed"...
0x1800b7475  mov     r8d, 1B6Ch
0x1800b747b  lea     rdx, aKerbcachesmart; "KerbCacheSmartCardLogon"
0x1800b7482  mov     dword ptr [rsp+1D0h+pInfo], eax
0x1800b7486  mov     ecx, ebx
0x1800b7488  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b748d  mov     rsi, [rsp+1D0h+var_168]
0x1800b7492  jmp     loc_1800B7989
0x1800b7497  test    r12, r12
0x1800b749a  jz      loc_1800B76E5
0x1800b74a0  xor     edx, edx; Val
0x1800b74a2  lea     rcx, [rbp+0D0h+pbBuffer]; void *
0x1800b74a6  lea     r8d, [rdx+40h]; Size
0x1800b74aa  call    memset_0
0x1800b74af  mov     rcx, qword ptr [rbp+0D0h+String2.Length]; struct _LSA_TOKEN_INFORMATION_V3 *
0x1800b74b3  lea     r9, [rsp+1D0h+var_158]; unsigned int *
0x1800b74b8  lea     r8, [rbp+0D0h+var_140]; unsigned __int8 **
0x1800b74bc  mov     rdx, r12; struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **
0x1800b74bf  call    ?KerbFilterAndEncodeCachedCredentialData@@YAJPEAU_LSA_TOKEN_INFORMATION_V3@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@PEAPEAEPEAK@Z; KerbFilterAndEncodeCachedCredentialData(_LSA_TOKEN_INFORMATION_V3 *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *,uchar * *,ulong *)
0x1800b74c4  test    eax, eax
0x1800b74c6  js      short loc_1800B748D
0x1800b74c8  mov     rax, [rdi+190h]
0x1800b74cf  test    [rax+3Ch], bl
0x1800b74d2  jnz     short loc_1800B74E2
0x1800b74d4  xor     edx, edx; struct _UNICODE_STRING *
0x1800b74d6  mov     rcx, r13; struct _KERB_PRIMARY_CREDENTIAL *
0x1800b74d9  call    ?KerbInitializePkCreds@@YAJPEAU_KERB_PRIMARY_CREDENTIAL@@PEAU_UNICODE_STRING@@@Z; KerbInitializePkCreds(_KERB_PRIMARY_CREDENTIAL *,_UNICODE_STRING *)
0x1800b74de  test    eax, eax
0x1800b74e0  js      short loc_1800B748D
0x1800b74e2  lea     rcx, [rbp+0D0h+pbBuffer]; pbBuffer
0x1800b74e6  call    ScHelperGenRandBits
0x1800b74eb  mov     esi, eax
0x1800b74ed  test    eax, eax
0x1800b74ef  jns     short loc_1800B751F
0x1800b74f1  call    cs:__imp_GetLastError
0x1800b74f7  lea     r9, aFailedToGenera; "Failed to generate random bits: 0x%x, l"...
0x1800b74fe  mov     r8d, 1B92h
0x1800b7504  mov     dword ptr [rsp+1D0h+pbComputedHash], eax
0x1800b7508  lea     rdx, aKerbcachesmart; "KerbCacheSmartCardLogon"
0x1800b750f  mov     ecx, ebx
0x1800b7511  mov     dword ptr [rsp+1D0h+pInfo], esi
0x1800b7515  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b751a  jmp     loc_1800B748D
0x1800b751f  mov     rax, [rdi+190h]
0x1800b7526  lea     rdx, a128401004521; "1.2.840.10045.2.1"
0x1800b752d  mov     rcx, [rax+20h]
0x1800b7531  mov     rcx, [rcx+18h]
0x1800b7535  mov     rcx, [rcx+60h]
0x1800b7539  call    cs:__imp__o__stricmp
0x1800b753f  test    eax, eax
0x1800b7541  jnz     loc_1800B75D6
0x1800b7547  mov     rax, [rdi+190h]
0x1800b754e  mov     rcx, [rax+20h]
0x1800b7552  mov     rdx, [rcx+18h]
0x1800b7556  mov     ecx, [rcx]; dwCertEncodingType
0x1800b7558  add     rdx, 60h ; '`'; pPublicKey
0x1800b755c  call    cs:__imp_CertGetPublicKeyLength
0x1800b7562  test    eax, eax
0x1800b7564  jnz     short loc_1800B757E
0x1800b7566  call    cs:__imp_GetLastError
0x1800b756c  lea     r9, aFailedToRetrie_0; "Failed to retrieve bit length: %#x\n"
0x1800b7573  mov     r8d, 1BA0h
0x1800b7579  jmp     loc_1800B747B
0x1800b757e  lea     rdx, [rbp+0D0h+hKey]; phKey
0x1800b7582  mov     ecx, eax; dwLength
0x1800b7584  call    ?KerbGenerateECDHKey@@YAJKPEAPEAX@Z; KerbGenerateECDHKey(ulong,void * *)
0x1800b7589  test    eax, eax
0x1800b758b  jz      short loc_1800B75AD
0x1800b758d  lea     r9, aFailedToGenera_0; "Failed to generate public key\n"
0x1800b7594  mov     r8d, 1BAAh
0x1800b759a  lea     rdx, aKerbcachesmart; "KerbCacheSmartCardLogon"
0x1800b75a1  mov     ecx, ebx
0x1800b75a3  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b75a8  jmp     loc_1800B748D
0x1800b75ad  mov     rcx, [rbp+0D0h+hKey]; hKey
0x1800b75b1  lea     rdx, [rbp+0D0h+var_E8]; struct _CRYPTOAPI_BLOB *
0x1800b75b5  call    ?KerbGetECDHPublicKey@@YAHPEAXPEAU_CRYPTOAPI_BLOB@@@Z; KerbGetECDHPublicKey(void *,_CRYPTOAPI_BLOB *)
0x1800b75ba  test    eax, eax
0x1800b75bc  jnz     short loc_1800B75D6
0x1800b75be  call    cs:__imp_GetLastError
0x1800b75c4  lea     r9, aFailedToEncode_1; "Failed to encode ECDH public key: %#x\n"
0x1800b75cb  mov     r8d, 1BB1h
0x1800b75d1  jmp     loc_1800B747B
0x1800b75d6  mov     dl, bl
0x1800b75d8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NGCKeyUsagePhase1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NGCKeyUsagePhase1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NGCKeyUsagePhase1> `wil::Feature<__WilFeatureTraits_Feature_NGCKeyUsagePhase1>::GetImpl(void)'::`2'::impl
0x1800b75df  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_NGCKeyUsagePhase1@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NGCKeyUsagePhase1>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800b75e4  mov     r9, [rsp+1D0h+hMem]; unsigned __int8 *
0x1800b75e9  lea     rax, [rsp+1D0h+size]
0x1800b75ee  mov     [rsp+1D0h+var_190], rax; unsigned int *
0x1800b75f3  lea     r8, [rbp+0D0h+var_E8]; struct _CRYPTOAPI_BLOB *
0x1800b75f7  mov     eax, [rsp+1D0h+var_158]
0x1800b75fb  lea     rdx, [rbp+0D0h+pbBuffer]; struct _ScHelper_RandomCredBits *
0x1800b75ff  mov     [rsp+1D0h+var_198], 0; unsigned __int8 *
0x1800b7608  mov     rcx, r13; struct _KERB_PRIMARY_CREDENTIAL *
0x1800b760b  mov     dword ptr [rsp+1D0h+pcbComputedHash], eax; unsigned int
0x1800b760f  mov     rax, [rbp+0D0h+var_140]
0x1800b7613  mov     [rsp+1D0h+pbComputedHash], rax; unsigned __int8 *
0x1800b7618  mov     dword ptr [rsp+1D0h+pInfo], r14d; unsigned int
0x1800b761d  call    ?__ScHelperEncryptCredentialsEX@@YAJPEAU_KERB_PRIMARY_CREDENTIAL@@PEAU_ScHelper_RandomCredBits@@PEAU_CRYPTOAPI_BLOB@@PEAEK3K3PEAK@Z; __ScHelperEncryptCredentialsEX(_KERB_PRIMARY_CREDENTIAL *,_ScHelper_RandomCredBits *,_CRYPTOAPI_BLOB *,uchar *,ulong,uchar *,ulong,uchar *,ulong *)
0x1800b7622  mov     esi, eax
0x1800b7624  test    eax, eax
0x1800b7626  jz      short loc_1800B7647
0x1800b7628  cmp     eax, 0C0000023h
0x1800b762d  jz      short loc_1800B7647
0x1800b762f  call    cs:__imp_GetLastError
0x1800b7635  lea     r9, aFailedToEncryp_1; "Failed to encrypt creds: 0x%x, last err"...
0x1800b763c  mov     r8d, 1BD4h
0x1800b7642  jmp     loc_1800B7504
0x1800b7647  mov     ecx, dword ptr [rsp+1D0h+size]; size
0x1800b764b  call    MIDL_user_allocate
0x1800b7650  mov     [rsp+1D0h+var_168], rax
0x1800b7655  mov     rsi, rax
0x1800b7658  test    rax, rax
0x1800b765b  jz      loc_1800B7989
0x1800b7661  mov     dl, bl
0x1800b7663  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NGCKeyUsagePhase1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NGCKeyUsagePhase1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NGCKeyUsagePhase1> `wil::Feature<__WilFeatureTraits_Feature_NGCKeyUsagePhase1>::GetImpl(void)'::`2'::impl
0x1800b766a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_NGCKeyUsagePhase1@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NGCKeyUsagePhase1>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800b766f  mov     edx, [rsp+1D0h+var_158]
0x1800b7673  lea     rax, [rsp+1D0h+size]
0x1800b7678  mov     [rsp+1D0h+var_190], rax; unsigned int *
0x1800b767d  lea     r8, [rbp+0D0h+var_E8]; struct _CRYPTOAPI_BLOB *
0x1800b7681  mov     [rsp+1D0h+var_198], rsi; unsigned __int8 *
0x1800b7686  mov     rcx, r13; struct _KERB_PRIMARY_CREDENTIAL *
0x1800b7689  mov     dword ptr [rsp+1D0h+pcbComputedHash], edx; unsigned int
0x1800b768d  mov     rdx, [rbp+0D0h+var_140]
0x1800b7691  mov     [rsp+1D0h+pbComputedHash], rdx; unsigned __int8 *
0x1800b7696  lea     rdx, [rbp+0D0h+pbBuffer]; struct _ScHelper_RandomCredBits *
0x1800b769a  mov     dword ptr [rsp+1D0h+pInfo], r14d; unsigned int
0x1800b769f  mov     r14, [rsp+1D0h+hMem]
0x1800b76a4  mov     r9, r14; unsigned __int8 *
0x1800b76a7  call    ?__ScHelperEncryptCredentialsEX@@YAJPEAU_KERB_PRIMARY_CREDENTIAL@@PEAU_ScHelper_RandomCredBits@@PEAU_CRYPTOAPI_BLOB@@PEAEK3K3PEAK@Z; __ScHelperEncryptCredentialsEX(_KERB_PRIMARY_CREDENTIAL *,_ScHelper_RandomCredBits *,_CRYPTOAPI_BLOB *,uchar *,ulong,uchar *,ulong,uchar *,ulong *)
0x1800b76ac  mov     esi, eax
0x1800b76ae  test    eax, eax
0x1800b76b0  jz      short loc_1800B76E5
0x1800b76b2  call    cs:__imp_GetLastError
0x1800b76b8  mov     dword ptr [rsp+1D0h+pbComputedHash], eax
0x1800b76bc  lea     r9, aFailedToEncryp_2; "Failed to encrypt creds 2: 0x%x, last e"...
0x1800b76c3  mov     r8d, 1C01h
0x1800b76c9  mov     dword ptr [rsp+1D0h+pInfo], esi
0x1800b76cd  lea     rdx, aKerbcachesmart; "KerbCacheSmartCardLogon"
0x1800b76d4  mov     ecx, ebx
0x1800b76d6  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b76db  mov     rsi, [rsp+1D0h+var_168]
0x1800b76e0  jmp     loc_1800B798E
0x1800b76e5  test    dword ptr [r15+0F0h], 1000h
0x1800b76f0  mov     r13d, dword ptr [rbp+0D0h+arg_38]
0x1800b76f7  jz      short loc_1800B7751
0x1800b76f9  mov     r12, [rbp+0D0h+var_150]
0x1800b76fd  lea     rdx, [r15+0D0h]; struct _UNICODE_STRING *
0x1800b7704  mov     r14d, dword ptr [rsp+1D0h+size]
0x1800b7709  lea     rcx, [r15+30h]; struct _UNICODE_STRING *
0x1800b770d  mov     rsi, [rsp+1D0h+var_168]
0x1800b7712  xor     r9d, r9d; struct _MSV1_0_IUM_SUPPLEMENTAL_CREDENTIAL *
0x1800b7715  mov     [rsp+1D0h+var_178], 0; struct _FIDO_CACHE_BLOB **
0x1800b771e  xor     r8d, r8d; struct _LM_OWF_PASSWORD *
0x1800b7721  mov     dword ptr [rsp+1D0h+var_180], r13d; size_t
0x1800b7726  mov     [rsp+1D0h+var_188], r12; void *
0x1800b772b  mov     dword ptr [rsp+1D0h+var_190], r14d; unsigned int
0x1800b7730  mov     [rsp+1D0h+var_198], rsi; void *
0x1800b7735  mov     [rsp+1D0h+pcbComputedHash], r15; struct _NETLOGON_VALIDATION_SAM_INFO4 *
0x1800b773a  mov     dword ptr [rsp+1D0h+pbComputedHash], 4; unsigned int
0x1800b7742  mov     [rsp+1D0h+pInfo], rdi; struct _KERB_LOGON_SESSION *
0x1800b7747  call    ?KerbCacheLogonInformation@@YAJPEAU_UNICODE_STRING@@0PEAU_LM_OWF_PASSWORD@@PEAU_MSV1_0_IUM_SUPPLEMENTAL_CREDENTIAL@@PEAU_KERB_LOGON_SESSION@@KPEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAXK5KPEAPEAU_FIDO_CACHE_BLOB@@@Z; KerbCacheLogonInformation(_UNICODE_STRING *,_UNICODE_STRING *,_LM_OWF_PASSWORD *,_MSV1_0_IUM_SUPPLEMENTAL_CREDENTIAL *,_KERB_LOGON_SESSION *,ulong,_NETLOGON_VALIDATION_SAM_INFO4 *,void *,ulong,void *,ulong,_FIDO_CACHE_BLOB * *)
0x1800b774c  jmp     loc_1800B788B
0x1800b7751  test    r12, r12
0x1800b7754  jz      loc_1800B787D
0x1800b775a  mov     rcx, [r12]
0x1800b775e  test    rcx, rcx
0x1800b7761  jz      loc_1800B787D
0x1800b7767  lea     rax, aNtlm; "NTLM"
0x1800b776e  mov     qword ptr [rbp+0D0h+String2.Length], 0A0008h
0x1800b7776  mov     [rbp+0D0h+String2.Buffer], rax
0x1800b777a  cmp     dword ptr [rcx], 0
0x1800b777d  jbe     loc_1800B787D
0x1800b7783  xor     r14d, r14d
0x1800b7786  add     rcx, 8
0x1800b778a  mov     esi, r14d
0x1800b778d  shl     rsi, 5
0x1800b7791  lea     rdx, [rbp+0D0h+String2]; String2
0x1800b7795  add     rcx, rsi; String1
0x1800b7798  mov     r8b, bl; CaseInsensitive
0x1800b779b  call    cs:__imp_RtlEqualUnicodeString
0x1800b77a1  mov     rcx, [r12]
0x1800b77a5  xor     r10d, r10d
0x1800b77a8  test    al, al
0x1800b77aa  jnz     short loc_1800B77B9
0x1800b77ac  add     r14d, ebx
0x1800b77af  cmp     r14d, [rcx]
0x1800b77b2  jb      short loc_1800B7786
0x1800b77b4  jmp     loc_1800B787D
0x1800b77b9  mov     edx, [rsi+rcx+18h]
0x1800b77bd  mov     r9, r10
0x1800b77c0  mov     rax, [rsi+rcx+20h]
0x1800b77c5  cmp     edx, 28h ; '('
  ... truncated ...
```
