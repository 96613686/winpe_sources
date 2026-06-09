# SpAcquireCredentialsHandle

- ea: `0x18005d250`
- end: `0x18005db00`
- name: `SpAcquireCredentialsHandle`
- size: `2224`
- prototype: `__int64 __usercall@<rax>(struct _UNICODE_STRING *@<rcx>, unsigned int@<edx>, int, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800a56e0`

## callees

- `0x1800068d0`
- `0x180009afc`
- `0x18000a630`
- `0x18000b300`
- `0x18000d9e4`
- `0x180016600`
- `0x1800209f0`
- `0x1800378e0`
- `0x1800474d8`
- `0x180048a28`
- `0x18005d250`
- `0x18006517c`
- `0x180070680`
- `0x18008aecc`
- `0x18008af5c`
- `0x18008aff0`
- `0x18008b70c`
- `0x180092084`
- `0x1800adccc`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005da3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005da3c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18005d8ec`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18005d8ec`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18005d8d4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18005d8d4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005d8ff`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005d8ff`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18005d9d0`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18005d9d0`
- `ntdll!RtlEnterCriticalSection` at `0x18005d674`
- `ntdll!RtlEnterCriticalSection` at `0x18005d6d2`
- `ntdll!RtlEnterCriticalSection` at `0x18005d674`
- `ntdll!RtlEnterCriticalSection` at `0x18005d6d2`
- `ntdll!RtlLeaveCriticalSection` at `0x18005d694`
- `ntdll!RtlLeaveCriticalSection` at `0x18005d6b9`
- `ntdll!RtlLeaveCriticalSection` at `0x18005d708`
- `ntdll!RtlLeaveCriticalSection` at `0x18005d694`
- `ntdll!RtlLeaveCriticalSection` at `0x18005d6b9`
- `ntdll!RtlLeaveCriticalSection` at `0x18005d708`
- `LSASRV!LsaIFreeSupplementalTokenInfo` at `0x18005da75`
- `LSASRV!LsaIFreeSupplementalTokenInfo` at `0x18005da75`
- `LSASRV!LsaIGetSupplementalTokenInfo` at `0x18005d91b`
- `LSASRV!LsaIGetSupplementalTokenInfo` at `0x18005d91b`

## string_xrefs

- `0x18005d396`: `Could not get identification LUID or impersonation LUID (impossible situation??)`
- `0x18005d428`: `Failed to get client token by logon id %#x:%#x: %#x`
- `0x18005d4b1`: `Attempting to ensure localkdc is started.`
- `0x18005d51b`: `Trying to acquire credentials with an token no better than SecurityIdentification\n`
- `0x18005d589`: `SpAcquireCredentialsHandle called for unknown logon session %#x:%#x, Impersonating ? %s, AuthorizationData %p\n`
- `0x18005d650`: `Got identify token on ls %p\n`
- `0x18005d7e2`: `Adding token restrictions\n`
- `0x18005d822`: `Trying to acquire outbound credentials with a restricted token\n`
- `0x18005d92b`: `failed to get token restrictions for: %#x:%#x, status %#x\n`
- `0x18005d9a7`: `Failed to create credential: 0x%x\n`

## pseudocode

```c
__int64 __fastcall SpAcquireCredentialsHandle(
        struct _UNICODE_STRING *a1,
        unsigned int a2,
        struct _LUID *a3,
        __int64 a4,
        int a5,
        int a6,
        struct _KERB_CREDENTIAL **a7,
        union _LARGE_INTEGER *a8)
{
  struct _LUID *v11; // rdi
  struct _KERB_LOGON_SESSION *v12; // r14
  struct _KERB_CREDENTIAL *v13; // r15
  int v14; // ebx
  int v15; // eax
  __m128i v16; // xmm1
  __m128i v17; // xmm2
  enum _SECURITY_IMPERSONATION_LEVEL v18; // esi
  void *v19; // r15
  unsigned __int8 v20; // bl
  int HighPart; // edx
  int LowPart; // ecx
  Ntlmless::LocalKdc *v23; // rcx
  LocalKdcState *v24; // rcx
  int v25; // eax
  struct _KERB_LOGON_SESSION *LogonSession; // rax
  __int64 v27; // rdx
  DWORD v28; // ecx
  const char *v29; // rax
  int v30; // eax
  __int64 v31; // rdx
  int v32; // eax
  const char *v33; // r9
  __int64 v34; // r8
  __int64 v35; // rcx
  __int64 v36; // rdx
  int v37; // eax
  union _LARGE_INTEGER *v38; // r13
  struct _KERB_CREDENTIAL **v39; // rsi
  __int64 v40; // rax
  WINBOOL v41; // ecx
  int v42; // eax
  DWORD nSubAuthority2[2]; // [rsp+20h] [rbp-E0h]
  DWORD nSubAuthority2a[2]; // [rsp+20h] [rbp-E0h]
  DWORD nSubAuthority3[2]; // [rsp+28h] [rbp-D8h]
  struct _KERB_CREDENTIAL *v47; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v48; // [rsp+68h] [rbp-98h] BYREF
  WINBOOL IsMember[2]; // [rsp+70h] [rbp-90h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp-88h] BYREF
  struct _KERB_PRIMARY_CREDENTIAL *v51; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v52[3]; // [rsp+88h] [rbp-78h] BYREF
  char v53[8]; // [rsp+B8h] [rbp-48h] BYREF
  PSID SidToCheck; // [rsp+C0h] [rbp-40h] BYREF
  struct _LSA_TOKEN_INFO_HEADER *v55; // [rsp+C8h] [rbp-38h] BYREF
  struct _LUID v56; // [rsp+D0h] [rbp-30h] BYREF
  PLARGE_INTEGER SystemTime; // [rsp+D8h] [rbp-28h]
  struct _KERB_CREDENTIAL **v58; // [rsp+E0h] [rbp-20h]
  struct _UNICODE_STRING v59; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v60; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v61; // [rsp+108h] [rbp+8h]
  _OWORD v62[3]; // [rsp+110h] [rbp+10h] BYREF
  struct _KERB_LOGON_SESSION *pIdentifierAuthority; // [rsp+140h] [rbp+40h] BYREF

  SystemTime = a8;
  *(_QWORD *)IsMember = a4;
  v58 = a7;
  KerbTracerT::KerbTracerT((KerbTracerT *)v53, "SP ACH", (unsigned int)a3);
  memset(v52, 0, sizeof(v52));
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v47 = 0;
  v51 = 0;
  v59 = 0;
  v48 = 0;
  v55 = 0;
  TokenHandle = 0;
  v60 = 0;
  v61 = 0;
  if ( !KerbGlobalInitialized )
  {
    v14 = -1073741604;
    DWORD2(v52[0]) = 0;
    goto LABEL_99;
  }
  v15 = ((__int64 (__fastcall *)(_OWORD *, __int64))LsaFunctions[1].CreateLogonSession)(v52, 48);
  v14 = v15;
  if ( v15 < 0 )
  {
    KerbTracerT::Log(1, "SpAcquireCredentialsHandle", 4909, "Failed to get client information: 0x%x.", v15);
    goto LABEL_87;
  }
  if ( (BYTE3(v52[1]) & 2) != 0 )
  {
    v14 = -1073741790;
    goto LABEL_87;
  }
  v16 = (__m128i)v52[0];
  v17 = (__m128i)v52[1];
  TokenHandle = (HANDLE)*((_QWORD *)&v52[1] + 1);
  v62[0] = v52[0];
  v62[1] = v52[1];
  v62[2] = v52[2];
  v56 = 0;
  if ( !(unsigned __int8)GetIdentificationLogonId(v62, &v56, &TokenHandle) )
  {
    v11 = (struct _LUID *)v52;
    KerbTracerT::Log(
      1,
      "SpAcquireCredentialsHandle",
      4924,
      "Could not get identification LUID or impersonation LUID (impossible situation??)");
    v14 = -2146893042;
    goto LABEL_87;
  }
  v11 = &v56;
  if ( a3 && (a3->LowPart || a3->HighPart) )
  {
    v11 = a3;
    if ( a3->LowPart != _mm_cvtsi128_si32(v16) || a3->HighPart != _mm_cvtsi128_si32(_mm_srli_si128(v16, 4)) )
    {
      if ( !(unsigned __int8)_mm_cvtsi128_si32(v17) )
      {
        v14 = -1073741727;
        goto LABEL_87;
      }
      v14 = ((__int64 (__fastcall *)(struct _LUID *, HANDLE *))LsaFunctions->OpenTokenByLogonId)(a3, &TokenHandle);
      if ( v14 < 0 )
      {
        KerbTracerT::Log(
          1,
          "SpAcquireCredentialsHandle",
          4954,
          "Failed to get client token by logon id %#x:%#x: %#x",
          v14,
          a3->HighPart,
          a3->LowPart);
        goto LABEL_87;
      }
    }
  }
  v18 = DWORD1(v52[1]);
  v19 = (void *)SDWORD2(v52[0]);
  v20 = BYTE1(v52[1]);
  if ( v11 )
  {
    LowPart = v11->LowPart;
    HighPart = v11->HighPart;
  }
  else
  {
    HighPart = -1;
    LowPart = -1;
  }
  KerbTracerT::Log(
    7,
    "SpAcquireCredentialsHandle",
    4966,
    "SpAcquireCredentialsHandle for pid 0x%x, luid (%x:%x) called\n",
    DWORD2(v52[0]),
    HighPart,
    LowPart);
  if ( Ntlmless::LocalKdc::IsEnabled(v23) )
  {
    KerbTracerT::Log(3, "SpAcquireCredentialsHandle", 4971, "Attempting to ensure localkdc is started.");
    v25 = LocalKdcState::WaitForLocalKdc(v24);
    KerbTracerT::Log(3, "SpAcquireCredentialsHandle", 4973, "Waiting for localkdc returned status 0x0x%x", v25);
  }
  LogonSession = KerbLocateLogonSession(v11, 0);
  pIdentifierAuthority = LogonSession;
  v12 = LogonSession;
  if ( LogonSession )
  {
    if ( SDWORD1(v52[1]) <= 1 )
    {
      KerbTracerT::Log(
        8,
        "SpAcquireCredentialsHandle",
        5051,
        "Got identify token on ls %p\n",
        (const void *)WORD1(LogonSession));
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)v12 + 2);
      if ( *(_QWORD *)IsMember || (*((_DWORD *)v12 + 226) & 0x1000) == 0 )
      {
        KerbTracerT::Log(1, "SpAcquireCredentialsHandle", 5065, "ACH called w identify + !s4u or w pvauth\n");
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v12 + 2);
        goto LABEL_26;
      }
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v12 + 2);
    }
    goto LABEL_48;
  }
  if ( SDWORD1(v52[1]) > 1 )
  {
    v28 = v11->LowPart;
    if ( v11->LowPart == 999 )
    {
      if ( !v11->HighPart )
        goto LABEL_34;
    }
    else if ( v28 == 998 )
    {
      goto LABEL_32;
    }
    if ( v28 != 997 )
    {
LABEL_33:
      if ( v20 )
      {
LABEL_39:
        if ( !((unsigned __int8 (__fastcall *)(__int128 *, __int64, _QWORD))LsaFunctions->GetCallInfo)(&v60, v27, 0) )
        {
          KerbTracerT::Log(1, "SpAcquireCredentialsHandle", 5023, "SpAcquireCredentialsHandle failed to get call info.");
          v14 = -1073741670;
          goto LABEL_86;
        }
        v30 = KerbCreateDummyLogonSession(WORD4(v60) & 0x2000, v11, &pIdentifierAuthority, v18, v20, v19);
        v12 = pIdentifierAuthority;
        if ( v30 < 0 )
          goto LABEL_38;
LABEL_48:
        RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)v12 + 2);
        KerbTracerT::Log(
          9,
          "SpAcquireCredentialsHandle",
          5078,
          "SpAcquireCredHandle: Acquiring creds for %wZ\\%wZ\n",
          (char *)v12 + 136,
          (char *)v12 + 120);
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v12 + 2);
        if ( *(_QWORD *)IsMember )
        {
          v32 = KerbCaptureSuppliedCreds(a2, v12, *(void **)IsMember, a1, TokenHandle, &v51, &v48);
          v14 = v32;
          if ( v32 < 0 )
          {
            v33 = "Failed to capture auth data: 0x%x.";
            v34 = 5098;
            v35 = 2;
LABEL_51:
            nSubAuthority2a[0] = v32;
            KerbTracerT::Log(v35, "SpAcquireCredentialsHandle", v34, v33, *(_QWORD *)nSubAuthority2a);
            goto LABEL_86;
          }
          if ( !v51 && v11->LowPart == 998 && !v11->HighPart )
          {
            KerbTracerT::Log(
              1,
              "SpAcquireCredentialsHandle",
              5104,
              "SpAcquireCredentialsHandle can not have anonymous with no explicit creds");
LABEL_38:
            v14 = -1073741729;
            goto LABEL_86;
          }
        }
        if ( a1 )
        {
          if ( a1->Length )
          {
            v14 = KerbDuplicateStringEx(&v59, a1);
            if ( v14 < 0 )
              goto LABEL_86;
          }
        }
        LOBYTE(v31) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstantHAADJ>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_InstantHAADJ>::GetImpl'::`2'::impl,
          v31);
        if ( BYTE2(v52[1]) )
        {
          v48 |= 0x10000000u;
          KerbTracerT::Log(7, "SpAcquireCredentialsHandle", 5140, "Adding token restrictions\n");
          if ( (a2 & 2) != 0
            && (LODWORD(v52[0]) != 996 || __PAIR64__(DWORD1(v52[0]), 996) != v11->LowPart || v11->HighPart || v51) )
          {
            KerbTracerT::Log(
              1,
              "SpAcquireCredentialsHandle",
              5147,
              "Trying to acquire outbound credentials with a restricted token\n");
            v14 = -1073741790;
            goto LABEL_86;
          }
        }
        LOBYTE(v36) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstantHAADJ>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_InstantHAADJ>::GetImpl'::`2'::impl,
          v36);
        if ( !a2 || (a2 & 0xFFFFFFAC) != 0 )
        {
          KerbTracerT::Log(1, "SpAcquireCredentialsHandle", 5162, "Invalid credential use flags: 0x%x.", a2);
          v14 = -1073741811;
          goto LABEL_86;
        }
        if ( (a2 & 1) != 0 )
        {
          IsMember[0] = 0;
          SidToCheck = 0;
          LODWORD(pIdentifierAuthority) = 0;
          WORD2(pIdentifierAuthority) = 1280;
          if ( !KerbGlobalValidateKDCPACSignature && !v51 && TokenHandle )
          {
            if ( AllocateAndInitializeSid(
                   (PSID_IDENTIFIER_AUTHORITY)&pIdentifierAuthority,
                   1u,
                   6u,
                   0,
                   0,
                   0,
                   0,
                   0,
                   0,
                   0,
                   &SidToCheck) )
            {
              if ( !CheckTokenMembership(TokenHandle, SidToCheck, IsMember) )
                IsMember[0] = 0;
              FreeSid(SidToCheck);
            }
            if ( IsMember[0] )
              v48 |= 0x2000000u;
          }
        }
        v37 = LsaIGetSupplementalTokenInfo(TokenHandle, &v55);
        v14 = v37;
        if ( v37 < 0 )
        {
          KerbTracerT::Log(
            1,
            "SpAcquireCredentialsHandle",
            5251,
            "failed to get token restrictions for: %#x:%#x, status %#x\n",
            DWORD1(v52[0]),
            LODWORD(v52[0]),
            v37);
          goto LABEL_86;
        }
        v38 = SystemTime;
        v32 = KerbCreateCredential(v11, TokenHandle, v12, a2, &v55, &v51, v48, &v59, &v47, SystemTime);
        v14 = v32;
        if ( v32 >= 0 )
        {
          v39 = v58;
          v13 = v47;
          *v58 = v47;
          RtlSystemTimeToLocalTime(v38, v38);
          v40 = 0;
          if ( *v39 )
            v40 = *((unsigned __int16 *)v39 + 1);
          KerbTracerT::Log(
            7,
            "SpAcquireCredentialsHandle",
            5285,
            "SpAcquireCredentialsHandle returning success, handle = %p\n",
            v40);
          goto LABEL_87;
        }
        v33 = "Failed to create credential: 0x%x\n";
        v34 = 5274;
        v35 = 8;
        goto LABEL_51;
      }
LABEL_34:
      if ( !*(_QWORD *)IsMember )
      {
        v29 = "true";
        if ( !v20 )
          v29 = "false";
        nSubAuthority3[0] = v11->LowPart;
        nSubAuthority2[0] = v11->HighPart;
        KerbTracerT::Log(
          8,
          "SpAcquireCredentialsHandle",
          5016,
          "SpAcquireCredentialsHandle called for unknown logon session %#x:%#x, Impersonating ? %s, AuthorizationData %p\n",
          *(_QWORD *)nSubAuthority2,
          *(_QWORD *)nSubAuthority3,
          v29,
          0);
        goto LABEL_38;
      }
      goto LABEL_39;
    }
LABEL_32:
    if ( !v11->HighPart )
      goto LABEL_34;
    goto LABEL_33;
  }
  KerbTracerT::Log(
    1,
    "SpAcquireCredentialsHandle",
    4995,
    "Trying to acquire credentials with an token no better than SecurityIdentification\n");
LABEL_26:
  v14 = -2146893042;
LABEL_86:
  v13 = v47;
LABEL_87:
  if ( TokenHandle && TokenHandle != *((HANDLE *)&v52[1] + 1) && TokenHandle != *((HANDLE *)&v52[2] + 1) )
    CloseHandle(TokenHandle);
  if ( v12 )
    KerbDereferenceLogonSession(v12);
  if ( v13 )
    KerbDereferenceCredential(v13);
  if ( v51 )
    KerbFreePrimaryCredentials(v51, 1u);
  if ( v55 )
    LsaIFreeSupplementalTokenInfo();
LABEL_99:
  KerbFreeString((__int64)&v59);
  if ( v11 )
  {
    IsMember[0] = v11->LowPart;
    v42 = v11->HighPart;
    v41 = IsMember[0];
  }
  else
  {
    v41 = -1;
    v42 = -1;
  }
  KerbTracerT::Log(
    7,
    "SpAcquireCredentialsHandle",
    5317,
    "SpAcquireCredentialsHandle for pid 0x%x, luid (%x:%x) returned 0x%x\n",
    DWORD2(v52[0]),
    v42,
    v41,
    v14);
  KerbTracerT::CaptureLastStatus(v14);
  KerbTracerT::~KerbTracerT((KerbTracerT *)v53);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18005d250  push    rbp
0x18005d252  push    rbx
0x18005d253  push    rsi
0x18005d254  push    rdi
0x18005d255  push    r12
0x18005d257  push    r13
0x18005d259  push    r14
0x18005d25b  push    r15
0x18005d25d  lea     rbp, [rsp-58h]
0x18005d262  sub     rsp, 158h
0x18005d269  mov     rax, cs:__security_cookie
0x18005d270  xor     rax, rsp
0x18005d273  mov     [rbp+90h+var_48], rax
0x18005d277  mov     rax, [rbp+90h+arg_30]
0x18005d27e  mov     r13, rcx
0x18005d281  mov     rcx, [rbp+90h+arg_38]
0x18005d288  mov     r12d, edx
0x18005d28b  mov     [rbp+90h+SystemTime], rcx
0x18005d28f  lea     rdx, aSpAch; "SP ACH"
0x18005d296  lea     rcx, [rbp+90h+var_D8]; this
0x18005d29a  mov     qword ptr [rsp+190h+IsMember], r9
0x18005d29f  mov     rsi, r8
0x18005d2a2  mov     [rbp+90h+var_B0], rax
0x18005d2a6  call    ??0KerbTracerT@@QEAA@PEBDK@Z; KerbTracerT::KerbTracerT(char const *,ulong)
0x18005d2ab  xor     ecx, ecx
0x18005d2ad  xorps   xmm0, xmm0
0x18005d2b0  xor     eax, eax
0x18005d2b2  mov     dword ptr [rbp+90h+var_108], ecx
0x18005d2b5  cmp     cs:?KerbGlobalInitialized@@3EA, cl; uchar KerbGlobalInitialized
0x18005d2bb  mov     edi, ecx
0x18005d2bd  movups  xmmword ptr [rbp+90h+var_F4], xmm0
0x18005d2c1  mov     r14d, ecx
0x18005d2c4  mov     r15d, ecx
0x18005d2c7  movups  xmmword ptr [rbp+90h+var_F4+0Ch], xmm0
0x18005d2cb  mov     [rsp+190h+var_130], rcx
0x18005d2d0  movups  [rbp+90h+var_108+4], xmm0
0x18005d2d4  mov     [rbp+90h+var_110], rcx
0x18005d2d8  movups  xmmword ptr [rbp+90h+var_A8.Length], xmm0
0x18005d2dc  mov     [rsp+190h+var_128], ecx
0x18005d2e0  mov     [rbp+90h+var_C8], rcx
0x18005d2e4  mov     [rsp+190h+TokenHandle], rcx
0x18005d2e9  movups  [rbp+90h+var_98], xmm0
0x18005d2ed  mov     [rbp+90h+var_88], rax
0x18005d2f1  jnz     short loc_18005D300
0x18005d2f3  mov     ebx, 0C00000DCh
0x18005d2f8  mov     dword ptr [rbp+90h+var_108+8], ecx
0x18005d2fb  jmp     loc_18005DA7B
0x18005d300  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18005d307  lea     rcx, [rbp+90h+var_108]
0x18005d30b  mov     edx, 30h ; '0'
0x18005d310  mov     rax, [rax+1F8h]
0x18005d317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d31c  mov     ebx, eax
0x18005d31e  test    eax, eax
0x18005d320  jns     short loc_18005D349
0x18005d322  mov     [rsp+190h+nSubAuthority2], eax
0x18005d326  lea     r9, aFailedToGetCli_2; "Failed to get client information: 0x%x."
0x18005d32d  mov     r8d, 132Dh
0x18005d333  mov     ecx, 1
0x18005d338  lea     rdx, aSpacquirecrede_5; "SpAcquireCredentialsHandle"
0x18005d33f  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005d344  jmp     loc_18005DA26
0x18005d349  test    byte ptr [rbp-65h], 2
0x18005d34d  jz      short loc_18005D359
0x18005d34f  mov     ebx, 0C0000022h
0x18005d354  jmp     loc_18005DA26
0x18005d359  movups  xmm0, xmmword ptr [rbp+90h+var_F4+0Ch]
0x18005d35d  mov     rax, qword ptr [rbp+90h+var_F4+4]
0x18005d361  lea     r8, [rsp+190h+TokenHandle]
0x18005d366  movups  xmm1, [rbp+90h+var_108]
0x18005d36a  xor     ebx, ebx
0x18005d36c  lea     rdx, [rbp+90h+var_C0]
0x18005d370  movups  xmm2, xmmword ptr [rbp-68h]
0x18005d374  lea     rcx, [rbp+90h+var_80]
0x18005d378  mov     [rsp+190h+TokenHandle], rax
0x18005d37d  movaps  [rbp+90h+var_80], xmm1
0x18005d381  movaps  [rbp+90h+var_70], xmm2
0x18005d385  movaps  [rbp+90h+var_60], xmm0
0x18005d389  mov     qword ptr [rbp+90h+var_C0.LowPart], rbx
0x18005d38d  call    ?GetIdentificationLogonId@@YA_NU_SECPKG_CLIENT_INFO_EX@@AEAU_LUID@@AEAPEAX@Z; GetIdentificationLogonId(_SECPKG_CLIENT_INFO_EX,_LUID &,void * &)
0x18005d392  test    al, al
0x18005d394  jnz     short loc_18005D3C0
0x18005d396  lea     r9, aCouldNotGetIde; "Could not get identification LUID or im"...
0x18005d39d  mov     r8d, 133Ch
0x18005d3a3  lea     rdx, aSpacquirecrede_5; "SpAcquireCredentialsHandle"
0x18005d3aa  lea     ecx, [rbx+1]
0x18005d3ad  lea     rdi, [rbp+90h+var_108]
0x18005d3b1  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005d3b6  mov     ebx, 8009030Eh
0x18005d3bb  jmp     loc_18005DA26
0x18005d3c0  lea     rdi, [rbp+90h+var_C0]
0x18005d3c4  test    rsi, rsi
0x18005d3c7  jz      loc_18005D45A
0x18005d3cd  cmp     [rsi], ebx
0x18005d3cf  jnz     short loc_18005D3DA
0x18005d3d1  cmp     [rsi+4], ebx
0x18005d3d4  jz      loc_18005D45A
0x18005d3da  movd    eax, xmm1
0x18005d3de  mov     rdi, rsi
0x18005d3e1  cmp     [rsi], eax
0x18005d3e3  jnz     short loc_18005D3F3
0x18005d3e5  psrldq  xmm1, 4
0x18005d3ea  movd    eax, xmm1
0x18005d3ee  cmp     [rsi+4], eax
0x18005d3f1  jz      short loc_18005D45A
0x18005d3f3  movd    eax, xmm2
0x18005d3f7  test    al, al
0x18005d3f9  jnz     short loc_18005D405
0x18005d3fb  mov     ebx, 0C0000061h
0x18005d400  jmp     loc_18005DA26
0x18005d405  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18005d40c  lea     rdx, [rsp+190h+TokenHandle]
0x18005d411  mov     rcx, rsi
0x18005d414  mov     rax, [rax+170h]
0x18005d41b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d420  mov     ebx, eax
0x18005d422  test    eax, eax
0x18005d424  jns     short loc_18005D45A
0x18005d426  mov     eax, [rsi]
0x18005d428  lea     r9, aFailedToGetCli_3; "Failed to get client token by logon id "...
0x18005d42f  mov     [rsp+190h+nSubAuthority4], eax
0x18005d433  lea     rdx, aSpacquirecrede_5; "SpAcquireCredentialsHandle"
0x18005d43a  mov     eax, [rsi+4]
0x18005d43d  mov     r8d, 135Ah
0x18005d443  mov     [rsp+190h+nSubAuthority3], eax
0x18005d447  mov     ecx, 1
0x18005d44c  mov     [rsp+190h+nSubAuthority2], ebx
0x18005d450  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005d455  jmp     loc_18005DA26
0x18005d45a  movsxd  rax, dword ptr [rbp+90h+var_108+8]
0x18005d45e  mov     esi, [rbp+90h+var_F4]
0x18005d461  mov     r15, rax
0x18005d464  mov     bl, [rbp+90h+var_F7]
0x18005d467  test    rdi, rdi
0x18005d46a  jnz     short loc_18005D473
0x18005d46c  or      edx, 0FFFFFFFFh
0x18005d46f  mov     ecx, edx
0x18005d471  jmp     short loc_18005D478
0x18005d473  mov     ecx, [rdi]
0x18005d475  mov     edx, [rdi+4]
0x18005d478  mov     [rsp+190h+nSubAuthority4], ecx
0x18005d47c  lea     r9, aSpacquirecrede; "SpAcquireCredentialsHandle for pid 0x%x"...
0x18005d483  mov     [rsp+190h+nSubAuthority3], edx
0x18005d487  mov     r8d, 1366h
0x18005d48d  lea     rdx, aSpacquirecrede_5; "SpAcquireCredentialsHandle"
0x18005d494  mov     [rsp+190h+nSubAuthority2], eax
0x18005d498  mov     ecx, 7
0x18005d49d  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005d4a2  call    ?IsEnabled@LocalKdc@Ntlmless@@YA_NXZ; Ntlmless::LocalKdc::IsEnabled(void)
0x18005d4a7  test    al, al
0x18005d4a9  jz      short loc_18005D4F2
0x18005d4ab  mov     r14d, 3
0x18005d4b1  lea     r9, aAttemptingToEn; "Attempting to ensure localkdc is starte"...
0x18005d4b8  mov     ecx, r14d
0x18005d4bb  lea     rdx, aSpacquirecrede_5; "SpAcquireCredentialsHandle"
0x18005d4c2  mov     r8d, 136Bh
0x18005d4c8  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005d4cd  call    ?WaitForLocalKdc@LocalKdcState@@YAJXZ; LocalKdcState::WaitForLocalKdc(void)
0x18005d4d2  lea     r9, aWaitingForLoca; "Waiting for localkdc returned status 0x"...
0x18005d4d9  mov     [rsp+190h+nSubAuthority2], eax
0x18005d4dd  mov     r8d, 136Dh
0x18005d4e3  lea     rdx, aSpacquirecrede_5; "SpAcquireCredentialsHandle"
0x18005d4ea  mov     ecx, r14d
0x18005d4ed  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005d4f2  xor     edx, edx; unsigned __int8
0x18005d4f4  mov     rcx, rdi; struct _LUID *
0x18005d4f7  call    ?KerbLocateLogonSession@@YAPEAU_KERB_LOGON_SESSION@@PEBU_LUID@@E@Z; KerbLocateLogonSession(_LUID const *,uchar)
0x18005d4fc  xor     r8d, r8d
0x18005d4ff  mov     [rbp+90h+pIdentifierAuthority], rax
0x18005d503  mov     r14, rax
0x18005d506  mov     r10d, 8
0x18005d50c  test    rax, rax
0x18005d50f  jnz     loc_18005D638
0x18005d515  cmp     [rbp+90h+var_F4], 1
0x18005d519  jg      short loc_18005D541
0x18005d51b  lea     r9, aTryingToAcquir_0; "Trying to acquire credentials with an t"...
0x18005d522  mov     r8d, 1383h
0x18005d528  lea     rdx, aSpacquirecrede_5; "SpAcquireCredentialsHandle"
0x18005d52f  lea     ecx, [rax+1]
0x18005d532  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005d537  mov     ebx, 8009030Eh
0x18005d53c  jmp     loc_18005DA21
0x18005d541  mov     ecx, [rdi]
0x18005d543  cmp     ecx, 3E7h
0x18005d549  jnz     short loc_18005D553
0x18005d54b  cmp     [rdi+4], r8d
0x18005d54f  jz      short loc_18005D56D
0x18005d551  jmp     short loc_18005D55B
0x18005d553  cmp     ecx, 3E6h
0x18005d559  jz      short loc_18005D563
0x18005d55b  cmp     ecx, 3E5h
0x18005d561  jnz     short loc_18005D569
0x18005d563  cmp     [rdi+4], r8d
0x18005d567  jz      short loc_18005D56D
0x18005d569  test    bl, bl
0x18005d56b  jnz     short loc_18005D5C3
0x18005d56d  cmp     qword ptr [rsp+190h+IsMember], r8
0x18005d572  jnz     short loc_18005D5C3
0x18005d574  mov     qword ptr [rsp+190h+nSubAuthority5], r8
0x18005d579  lea     rdx, aFalse; "false"
0x18005d580  test    bl, bl
0x18005d582  lea     rax, aTrue; "true"
0x18005d589  lea     r9, aSpacquirecrede_0; "SpAcquireCredentialsHandle called for u"...
0x18005d590  mov     r8d, 1398h
0x18005d596  cmovz   rax, rdx
0x18005d59a  lea     rdx, aSpacquirecrede_5; "SpAcquireCredentialsHandle"
0x18005d5a1  mov     qword ptr [rsp+190h+nSubAuthority4], rax
0x18005d5a6  mov     eax, [rdi+4]
0x18005d5a9  mov     [rsp+190h+nSubAuthority3], ecx
0x18005d5ad  mov     ecx, r10d
0x18005d5b0  mov     [rsp+190h+nSubAuthority2], eax
0x18005d5b4  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005d5b9  mov     ebx, 0C000005Fh
0x18005d5be  jmp     loc_18005DA21
0x18005d5c3  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18005d5ca  lea     rcx, [rbp+90h+var_98]
0x18005d5ce  mov     rax, [rax+0C0h]
0x18005d5d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d5da  test    al, al
0x18005d5dc  jnz     short loc_18005D606
0x18005d5de  lea     r9, aSpacquirecrede_1; "SpAcquireCredentialsHandle failed to ge"...
0x18005d5e5  mov     r8d, 139Fh
0x18005d5eb  lea     rdx, aSpacquirecrede_5; "SpAcquireCredentialsHandle"
0x18005d5f2  mov     ecx, 1
0x18005d5f7  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005d5fc  mov     ebx, 0C000009Ah
0x18005d601  jmp     loc_18005DA21
0x18005d606  mov     ecx, dword ptr [rbp+90h+var_98+8]
0x18005d609  lea     r8, [rbp+90h+pIdentifierAuthority]; struct _KERB_LOGON_SESSION **
0x18005d60d  and     ecx, 2000h; int
0x18005d613  mov     qword ptr [rsp+190h+nSubAuthority3], r15; void *
0x18005d618  mov     r9d, esi; enum _SECURITY_IMPERSONATION_LEVEL
0x18005d61b  mov     byte ptr [rsp+190h+nSubAuthority2], bl; unsigned __int8
0x18005d61f  mov     rdx, rdi; struct _LUID *
0x18005d622  call    ?KerbCreateDummyLogonSession@@YAJHPEAU_LUID@@PEAPEAU_KERB_LOGON_SESSION@@W4_SECURITY_IMPERSONATION_LEVEL@@EPEAX@Z; KerbCreateDummyLogonSession(int,_LUID *,_KERB_LOGON_SESSION * *,_SECURITY_IMPERSONATION_LEVEL,uchar,void *)
0x18005d627  mov     r14, [rbp+90h+pIdentifierAuthority]
0x18005d62b  xor     r15d, r15d
0x18005d62e  test    eax, eax
0x18005d630  jns     loc_18005D6C7
0x18005d636  jmp     short loc_18005D5B9
0x18005d638  cmp     [rbp+90h+var_F4], 1
0x18005d63c  jg      loc_18005D6C4
0x18005d642  shr     rax, 10h
0x18005d646  lea     rsi, aSpacquirecrede_5; "SpAcquireCredentialsHandle"
0x18005d64d  movzx   eax, ax
0x18005d650  lea     r9, aGotIdentifyTok; "Got identify token on ls %p\n"
0x18005d657  mov     r8d, 13BBh
0x18005d65d  mov     qword ptr [rsp+190h+nSubAuthority2], rax
0x18005d662  mov     rdx, rsi
0x18005d665  mov     ecx, r10d
0x18005d668  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005d66d  lea     rbx, [r14+50h]
0x18005d671  mov     rcx, rbx; CriticalSection
0x18005d674  call    cs:__imp_RtlEnterCriticalSection
0x18005d67a  xor     r15d, r15d
0x18005d67d  cmp     qword ptr [rsp+190h+IsMember], r15
0x18005d682  jnz     short loc_18005D69C
0x18005d684  test    dword ptr [r14+388h], 1000h
0x18005d68f  jz      short loc_18005D69C
0x18005d691  mov     rcx, rbx; CriticalSection
0x18005d694  call    cs:__imp_RtlLeaveCriticalSection
0x18005d69a  jmp     short loc_18005D6CE
0x18005d69c  lea     r9, aAchCalledWIden; "ACH called w identify + !s4u or w pvaut"...
0x18005d6a3  mov     r8d, 13C9h
0x18005d6a9  mov     rdx, rsi
0x18005d6ac  mov     ecx, 1
0x18005d6b1  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005d6b6  mov     rcx, rbx; CriticalSection
0x18005d6b9  call    cs:__imp_RtlLeaveCriticalSection
0x18005d6bf  jmp     loc_18005D537
0x18005d6c4  xor     r15d, r15d
0x18005d6c7  lea     rsi, aSpacquirecrede_5; "SpAcquireCredentialsHandle"
0x18005d6ce  lea     rcx, [r14+50h]; CriticalSection
0x18005d6d2  call    cs:__imp_RtlEnterCriticalSection
0x18005d6d8  lea     rax, [r14+78h]
0x18005d6dc  mov     r8d, 13D6h
0x18005d6e2  lea     rcx, [rax+10h]
0x18005d6e6  mov     qword ptr [rsp+190h+nSubAuthority3], rax
0x18005d6eb  mov     qword ptr [rsp+190h+nSubAuthority2], rcx
0x18005d6f0  lea     r9, aSpacquirecredh; "SpAcquireCredHandle: Acquiring creds fo"...
0x18005d6f7  mov     ecx, 9
0x18005d6fc  mov     rdx, rsi
0x18005d6ff  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005d704  lea     rcx, [r14+50h]; CriticalSection
0x18005d708  call    cs:__imp_RtlLeaveCriticalSection
0x18005d70e  mov     rcx, qword ptr [rsp+190h+IsMember]
0x18005d713  test    rcx, rcx
0x18005d716  jz      loc_18005D7A6
0x18005d71c  lea     rax, [rsp+190h+var_128]
0x18005d721  mov     r8, rcx; void *
0x18005d724  mov     qword ptr [rsp+190h+nSubAuthority4], rax; unsigned int *
0x18005d729  mov     r9, r13; struct _UNICODE_STRING *
0x18005d72c  lea     rax, [rbp+90h+var_110]
0x18005d730  mov     rdx, r14; struct _KERB_LOGON_SESSION *
0x18005d733  mov     qword ptr [rsp+190h+nSubAuthority3], rax; struct _KERB_PRIMARY_CREDENTIAL **
0x18005d738  mov     ecx, r12d; unsigned int
0x18005d73b  mov     rax, [rsp+190h+TokenHandle]
0x18005d740  mov     qword ptr [rsp+190h+nSubAuthority2], rax; void *
0x18005d745  call    ?KerbCaptureSuppliedCreds@@YAJKPEAU_KERB_LOGON_SESSION@@PEAXPEAU_UNICODE_STRING@@1PEAPEAU_KERB_PRIMARY_CREDENTIAL@@PEAK@Z; KerbCaptureSuppliedCreds(ulong,_KERB_LOGON_SESSION *,void *,_UNICODE_STRING *,void *,_KERB_PRIMARY_CREDENTIAL * *,ulong *)
0x18005d74a  mov     ebx, eax
  ... truncated ...
```
