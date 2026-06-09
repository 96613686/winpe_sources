# SpQueryMetaData(unsigned __int64,_UNICODE_STRING *,ulong,ulong *,uchar * *,unsigned __int64 *)

- ea: `0x180009070`
- end: `0x18000a32f`
- name: `?SpQueryMetaData@@YAJ_KPEAU_UNICODE_STRING@@KPEAKPEAPEAEPEA_K@Z`
- size: `4799`
- prototype: `__int64 __usercall@<rax>(struct _PKU2U_SECONDARY_CREDENTIAL *@<rcx>, struct _UNICODE_STRING *@<rdx>, unsigned int@<r8d>, unsigned int *@<r9>, unsigned __int8 **, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `25`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004d60`
- `0x180005300`
- `0x1800057f0`
- `0x180007dc8`
- `0x180009070`
- `0x18000a340`
- `0x18000a370`
- `0x18000a6c0`
- `0x18000afc0`
- `0x18000b6c0`
- `0x180010db0`
- `0x180011880`
- `0x180012820`
- `0x1800139e0`
- `0x1800178d0`
- `0x1800210f0`
- `0x180021a54`
- `0x180023cb8`
- `0x180023ce0`
- `0x180023e70`
- `0x18002b4f8`
- `0x18002dc44`
- `0x18002e234`
- `0x180044f8c`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000910c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000957a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000910c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000957a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180009710`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180009710`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000939f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009daf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000939f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009daf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009cff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009cff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009505`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a18a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009505`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a18a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180009371`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000975d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180009371`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000975d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180009cdb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180009cdb`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180009206`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180009206`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180009220`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180009220`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009d24`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009d24`
- `MSASN1!ASN1_CreateEncoder` at `0x1800098fc`
- `MSASN1!ASN1_CreateEncoder` at `0x1800098fc`
- `MSASN1!ASN1_CloseEncoder` at `0x180009a6a`
- `MSASN1!ASN1_CloseEncoder` at `0x180009a6a`
- `MSASN1!ASN1_Encode` at `0x180009926`
- `MSASN1!ASN1_Encode` at `0x180009926`
- `MSASN1!ASN1_FreeEncoded` at `0x180009a5a`
- `MSASN1!ASN1_FreeEncoded` at `0x180009a5a`
- `MSASN1!ASN1_CreateModule` at `0x180009fa3`
- `MSASN1!ASN1_CreateModule` at `0x180009fa3`
- `ntdll!RtlFreeHeap` at `0x1800097d1`
- `ntdll!RtlFreeHeap` at `0x1800097d1`
- `ntdll!NtQueryWnfStateData` at `0x1800091a3`
- `ntdll!NtQueryWnfStateData` at `0x1800091a3`
- `ntdll!RtlEqualUnicodeString` at `0x1800097f6`
- `ntdll!RtlEqualUnicodeString` at `0x180009812`
- `ntdll!RtlEqualUnicodeString` at `0x1800097f6`
- `ntdll!RtlEqualUnicodeString` at `0x180009812`
- `ntdll!NtSetInformationThread` at `0x1800092ac`
- `ntdll!NtSetInformationThread` at `0x1800092ac`
- `ntdll!NtOpenThreadToken` at `0x180009277`
- `ntdll!NtOpenThreadToken` at `0x180009277`
- `ext-ms-win-security-certpoleng-l1-1-0!IntPstGetTrustAnchors` at `0x1800092f4`
- `ext-ms-win-security-certpoleng-l1-1-0!IntPstGetTrustAnchors` at `0x1800092f4`

## pseudocode

```c
__int64 __fastcall SpQueryMetaData(
        struct _PKU2U_SECONDARY_CREDENTIAL *a1,
        struct _UNICODE_STRING *a2,
        unsigned int a3,
        unsigned int *a4,
        unsigned __int8 **a5,
        void **a6)
{
  struct _PKU2U_CONTEXT **v6; // r12
  char *v8; // rdi
  HANDLE v11; // r15
  int UserNameWithDomainPrefixHResult; // ebx
  __int64 v13; // rax
  void *v14; // r14
  void *v15; // r13
  bool v16; // sf
  int v17; // r14d
  NTSTATUS v18; // eax
  char *v19; // r8
  _BOOL8 v20; // rcx
  _DWORD *v21; // r14
  void *v22; // rax
  _QWORD *v23; // r15
  unsigned int i; // ebx
  unsigned int v25; // eax
  int v26; // r15d
  unsigned int v27; // r12d
  int v28; // eax
  int v29; // ecx
  int Context; // eax
  __int64 v31; // rdx
  _QWORD *v32; // r8
  _QWORD *v33; // rcx
  _QWORD *v34; // rsi
  void *v35; // rcx
  _QWORD *v36; // rdi
  void (*v37)(void); // rax
  int v39; // eax
  __int64 v40; // rax
  __int16 *v41; // rbx
  int v42; // eax
  void **v43; // r12
  void *v44; // r13
  unsigned int v45; // r14d
  __int64 Module; // rax
  unsigned int v47; // eax
  int v48; // eax
  size_t v49; // rbx
  unsigned __int8 *v50; // r14
  int v51; // ebx
  _QWORD *v52; // rcx
  unsigned int v53; // eax
  char *v54; // rax
  char *v55; // r15
  __int64 v56; // rax
  _QWORD *v57; // rax
  int v58; // eax
  _QWORD *v59; // rcx
  __int64 v60; // rdx
  __int64 v61; // r9
  DWORD LastError; // eax
  CHAR *v63; // rbx
  CHAR *v64; // rax
  unsigned __int8 *v65; // rax
  _QWORD *v66; // rdi
  int v67; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  WINBOOL IsMember; // [rsp+70h] [rbp-90h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp-88h] BYREF
  void **v71; // [rsp+80h] [rbp-80h]
  PVOID P; // [rsp+88h] [rbp-78h] BYREF
  void *v73; // [rsp+90h] [rbp-70h]
  LARGE_INTEGER v74; // [rsp+98h] [rbp-68h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v76; // [rsp+B0h] [rbp-50h]
  struct _UNICODE_STRING v77; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v78; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v79; // [rsp+E0h] [rbp-20h] BYREF
  void *v80; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int8 **v81; // [rsp+F8h] [rbp-8h]
  unsigned int *v82; // [rsp+100h] [rbp+0h]
  UNICODE_STRING String1; // [rsp+108h] [rbp+8h] BYREF
  UNICODE_STRING v84; // [rsp+118h] [rbp+18h] BYREF
  void *v85[2]; // [rsp+130h] [rbp+30h]
  void *ThreadInformation; // [rsp+140h] [rbp+40h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+148h] [rbp+48h] BYREF
  PSID SidToCheck; // [rsp+150h] [rbp+50h] BYREF

  v6 = (struct _PKU2U_CONTEXT **)a6;
  v82 = a4;
  *(_QWORD *)&v76 = a2;
  v8 = (char *)*a6;
  TokenHandle = *a6;
  v81 = a5;
  v11 = 0;
  v71 = a6;
  P = 0;
  v78 = 0;
  v80 = 0;
  v79 = 0;
  v73 = 0;
  v77 = 0;
  PerformanceCount.QuadPart = 0;
  v74.QuadPart = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids);
  QueryPerformanceCounter(&PerformanceCount);
  *v82 = 0;
  *a5 = 0;
  if ( v8 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v8 + 2);
    a1 = (struct _PKU2U_SECONDARY_CREDENTIAL *)*((_QWORD *)v8 + 2);
    Pku2uReferenceSecondaryCredential(a1);
    goto LABEL_4;
  }
  if ( !a1 )
  {
    a1 = 0;
    UserNameWithDomainPrefixHResult = -1073741816;
    v17 = 0;
    goto LABEL_58;
  }
  Pku2uReferenceSecondaryCredential(a1);
  if ( a2 && a2->Length )
  {
    if ( !Pku2uGlobalSupportInitiatorFirst && *((_DWORD *)a1 + 8) )
      goto LABEL_141;
    v29 = 1;
  }
  else
  {
    v29 = 0;
  }
  Context = Pku2uAllocateContext(v29, a1, a2, a3, (struct _PKU2U_CONTEXT **)&TokenHandle);
  v8 = (char *)TokenHandle;
  UserNameWithDomainPrefixHResult = Context;
  if ( Context < 0 )
    goto LABEL_142;
  v31 = *((_QWORD *)TokenHandle + 10);
  String1.Buffer = L"HTTP";
  v84.Buffer = L"HTTPS";
  *(_QWORD *)&String1.Length = 655368;
  *(_QWORD *)&v84.Length = 786442;
  if ( !v31 || *(_WORD *)(v31 + 2) != 2 || (unsigned __int16)(*(_WORD *)v31 - 1) > 2u )
    goto LABEL_45;
  if ( RtlEqualUnicodeString(&String1, (PCUNICODE_STRING)(v31 + 8), 1u) )
  {
LABEL_141:
    UserNameWithDomainPrefixHResult = -2146893053;
    goto LABEL_142;
  }
  if ( RtlEqualUnicodeString(&v84, (PCUNICODE_STRING)(*((_QWORD *)v8 + 10) + 8LL), 1u) )
  {
    UserNameWithDomainPrefixHResult = -2146893053;
    v17 = 0;
    goto LABEL_58;
  }
LABEL_45:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_qDDZ(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 2) + 24LL) + 28LL),
      *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 2) + 24LL) + 24LL),
      (__int64)(v8 + 88));
LABEL_4:
  if ( _InterlockedIncrement((volatile signed __int32 *)v8 + 80) > 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        147,
        &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
        v8,
        *((_DWORD *)v8 + 80));
    UserNameWithDomainPrefixHResult = -2146893054;
    v17 = 0;
    goto LABEL_58;
  }
  if ( *((_DWORD *)a1 + 8) == 1 )
  {
    v28 = Pku2uPopulateContextWithCredmanCreds((struct _PKU2U_CONTEXT *)v8);
    UserNameWithDomainPrefixHResult = v28;
    if ( v28 < 0 )
    {
      v59 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_142;
      v60 = 148;
      goto LABEL_151;
    }
    if ( *((_QWORD *)v8 + 3) )
    {
      Pku2uDereferenceSecondaryCredential(a1);
      a1 = (struct _PKU2U_SECONDARY_CREDENTIAL *)*((_QWORD *)v8 + 3);
      Pku2uReferenceSecondaryCredential(a1);
    }
  }
  if ( *((_DWORD *)a1 + 8) )
    goto LABEL_7;
  if ( (unsigned __int16)Pku2uMapCredsToProviderHResult(a1) )
    UserNameWithDomainPrefixHResult = (unsigned __int16)Pku2uMapCredsToProviderHResult(a1) | 0xC0070000;
  else
    UserNameWithDomainPrefixHResult = (unsigned __int16)Pku2uMapCredsToProviderHResult(a1);
  if ( UserNameWithDomainPrefixHResult < 0 )
  {
    v59 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v60 = 149;
      v61 = (unsigned int)UserNameWithDomainPrefixHResult;
      goto LABEL_152;
    }
LABEL_142:
    v17 = 0;
    goto LABEL_58;
  }
  if ( (unsigned __int16)GetUserNameWithDomainPrefixHResult(a1, &v77) )
    UserNameWithDomainPrefixHResult = (unsigned __int16)GetUserNameWithDomainPrefixHResult(a1, &v77) | 0xC0070000;
  else
    UserNameWithDomainPrefixHResult = (unsigned __int16)GetUserNameWithDomainPrefixHResult(a1, &v77);
  if ( UserNameWithDomainPrefixHResult < 0 )
  {
    v59 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v60 = 150;
      v61 = (unsigned int)UserNameWithDomainPrefixHResult;
      goto LABEL_152;
    }
    goto LABEL_142;
  }
  if ( v77.Length )
  {
    KerbFreeString((struct _UNICODE_STRING *)(v8 + 184));
    v28 = KerbDuplicateStringEx((struct _UNICODE_STRING *)(v8 + 184), &v77, 1u, 0);
    UserNameWithDomainPrefixHResult = v28;
    if ( v28 < 0 )
    {
      v59 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_142;
      v60 = 151;
LABEL_151:
      v61 = (unsigned int)v28;
LABEL_152:
      WPP_SF_d(v59[2], v60, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids, v61);
      v17 = 0;
      goto LABEL_58;
    }
  }
LABEL_7:
  v67 = 8;
  UserNameWithDomainPrefixHResult = 0;
  IsMember = 0;
  SidToCheck = 0;
  if ( (int)NtQueryWnfStateData(&WNF_SEB_INTERNET_PRESENT, 0, 0, &IsMember, &SidToCheck, &v67) >= 0
    && v67 == 8
    && ((unsigned __int8)SidToCheck & 2) != 0 )
  {
    LODWORD(v11) = 1;
  }
  v13 = *((_QWORD *)a1 + 3);
  v67 = 0;
  hObject = 0;
  SidToCheck = 0;
  v14 = *(void **)(v13 + 32);
  v15 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    if ( !CheckTokenMembership(v14, SidToCheck, &IsMember) )
    {
      UserNameWithDomainPrefixHResult = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_145765ada38d35d83bd68130d412160b_Traceguids,
          (unsigned int)UserNameWithDomainPrefixHResult);
    }
  }
  else
  {
    UserNameWithDomainPrefixHResult = GetLastError();
  }
  if ( SidToCheck )
    FreeSid(SidToCheck);
  v16 = UserNameWithDomainPrefixHResult < 0;
  if ( UserNameWithDomainPrefixHResult > 0 )
  {
    UserNameWithDomainPrefixHResult = (unsigned __int16)UserNameWithDomainPrefixHResult | 0xC0070000;
    v16 = UserNameWithDomainPrefixHResult < 0;
  }
  if ( v16 )
  {
    v17 = 0;
  }
  else
  {
    if ( IsMember )
      goto LABEL_19;
    ThreadInformation = v14;
    v17 = 0;
    TokenHandle = 0;
    UserNameWithDomainPrefixHResult = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
    if ( (int)(UserNameWithDomainPrefixHResult + 0x80000000) < 0 || UserNameWithDomainPrefixHResult == -1073741700 )
    {
      v67 = 1;
      v18 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
      v15 = TokenHandle;
      UserNameWithDomainPrefixHResult = v18;
      TokenHandle = 0;
      v17 = v67;
      hObject = v15;
    }
    else
    {
      v67 = 0;
      hObject = 0;
      if ( TokenHandle )
        CloseHandle(TokenHandle);
    }
  }
  if ( UserNameWithDomainPrefixHResult < 0 )
  {
    v11 = hObject;
    goto LABEL_58;
  }
LABEL_19:
  v19 = (char *)a1 + 120;
  if ( *((_DWORD *)a1 + 8) == 1 )
    v19 = 0;
  v20 = (_QWORD)v76 && *(_WORD *)v76;
  UserNameWithDomainPrefixHResult = IntPstGetTrustAnchors(v20, (unsigned int)v11, v19, &P);
  if ( v67 )
  {
    if ( !SetThreadToken(0, v15) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_145765ada38d35d83bd68130d412160b_Traceguids, LastError);
      }
      RevertToSelf();
    }
    v67 = 0;
  }
  if ( UserNameWithDomainPrefixHResult < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        152,
        &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
        (unsigned int)UserNameWithDomainPrefixHResult);
LABEL_56:
    v11 = hObject;
LABEL_57:
    v17 = v67;
LABEL_58:
    QueryPerformanceCounter(&v74);
    Pku2uLogProvider::LogQueryMetadata(
      PerformanceCount,
      v74,
      a1,
      (struct _SecPkgContext_IssuerListInfoEx *)P,
      *v6,
      UserNameWithDomainPrefixHResult);
    goto LABEL_59;
  }
  v21 = P;
  v22 = 0;
  v23 = 0;
  v73 = 0;
  for ( i = 0; i < v21[2]; ++i )
  {
    if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
    {
      v32 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))(24);
      if ( !v32 )
        goto LABEL_55;
    }
    else
    {
      v32 = (_QWORD *)(**((__int64 (__fastcall ***)(__int64))Pku2uGlobalBaseSSP + 31))(24);
      if ( !v32 )
      {
LABEL_55:
        UserNameWithDomainPrefixHResult = -1073741801;
        goto LABEL_56;
      }
      *(_OWORD *)v32 = 0;
      v32[2] = 0;
    }
    *((_DWORD *)v32 + 2) = *(_DWORD *)(*(_QWORD *)v21 + 16LL * i);
    v22 = v73;
    v32[2] = *(_QWORD *)(*(_QWORD *)v21 + 16LL * i + 8);
    if ( v22 )
    {
      *v23 = v32;
    }
    else
    {
      v22 = v32;
      v73 = v32;
    }
    v23 = v32;
  }
  *((_QWORD *)&v78 + 1) = v22;
  *(_QWORD *)&v79 = 0;
  v25 = WideCharToMultiByte(0xFDE9u, 0, L"WELLKNOWN:PKU2U", 15, 0, 0, 0, 0);
  v26 = v25;
  if ( !v25 )
    goto LABEL_95;
  if ( v25 > 0xFFFC )
  {
    SetLastError(0x57u);
    goto LABEL_95;
  }
  v27 = v25 + 1;
  if ( v25 + 1 < v25 )
  {
    SetLastError(0x216u);
LABEL_94:
    v6 = (struct _PKU2U_CONTEXT **)v71;
LABEL_95:
    UserNameWithDomainPrefixHResult = KerbMapKerbError(60);
LABEL_96:
    v11 = hObject;
    goto LABEL_97;
  }
  if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
  {
    v63 = (CHAR *)(*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))(v27);
  }
  else
  {
    v64 = (CHAR *)(**((__int64 (__fastcall ***)(_QWORD))Pku2uGlobalBaseSSP + 31))(v27);
    v63 = v64;
    if ( v64 )
    {
      memset_0(v64, 0, v27);
      goto LABEL_91;
    }
  }
  if ( !v63 )
    goto LABEL_94;
LABEL_91:
  v39 = WideCharToMultiByte(0xFDE9u, 0, L"WELLKNOWN:PKU2U", 15, v63, v26, 0, 0);
  if ( !v39 )
  {
    if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
      (*(void (__fastcall **)(CHAR *))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 392LL))(v63);
    else
      (*(void (__fastcall **)(CHAR *))(*((_QWORD *)Pku2uGlobalBaseSSP + 31) + 8LL))(v63);
    goto LABEL_94;
  }
  v6 = (struct _PKU2U_CONTEXT **)v71;
  v63[v39] = 0;
  v40 = -1;
  do
    ++v40;
  while ( v63[v40] );
  if ( (unsigned int)v40 > 0xFFFD )
  {
    Pku2uFree(v63);
    goto LABEL_95;
  }
  *(_QWORD *)&v79 = v63;
  v41 = (__int16 *)*((_QWORD *)v8 + 10);
  if ( v41 )
  {
    v42 = *v41;
    v43 = &v80;
    hObject = v15;
    DWORD2(v79) = v42;
    *(_OWORD *)v85 = 0;
    v44 = 0;
    v45 = 0;
    v80 = 0;
    while ( 1 )
    {
      if ( v45 >= (unsigned __int16)v41[1] )
      {
        v11 = hObject;
        LOWORD(v78) = v78 | 0x80;
        v6 = (struct _PKU2U_CONTEXT **)v71;
        goto LABEL_112;
      }
      *(_QWORD *)&v76 = 0;
      v54 = KerbAllocUtf8StrFromUnicodeString((struct _UNICODE_STRING *)&v41[8 * v45 + 4]);
      *((_QWORD *)&v76 + 1) = v54;
      v55 = v54;
      if ( !v54 )
        break;
      *((_QWORD *)&v76 + 1) = v54;
      v56 = -1;
      do
        ++v56;
      while ( v55[v56] );
      if ( (unsigned int)v56 > 0xFFFD )
      {
        Pku2uFree(v55);
        break;
      }
      LOWORD(v76) = v56;
      WORD1(v76) = v56 + 1;
      *(_OWORD *)v85 = v76;
      if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
      {
        v57 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))(16);
        if ( !v57 )
        {
LABEL_127:
          v44 = v85[1];
          break;
        }
      }
      else
      {
        v57 = (_QWORD *)(**((__int64 (__fastcall ***)(__int64))Pku2uGlobalBaseSSP + 31))(16);
        if ( !v57 )
          goto LABEL_127;
      }
      v57[1] = v55;
      *v57 = 0;
      v44 = 0;
      *v43 = v57;
      ++v45;
      v43 = (void **)v57;
    }
    KerbFreePrincipalName((struct KERB_PRINCIPAL_NAME *)((char *)&v79 + 8));
    if ( v44 )
      Pku2uFree(v44);
    UserNameWithDomainPrefixHResult = -1073741670;
    v6 = (struct _PKU2U_CONTEXT **)v71;
    goto LABEL_96;
  }
  v11 = v15;
LABEL_112:
  hObject = 0;
  if ( fKRB5ModuleStarted )
  {
    Module = PKU2UMSG_Module;
  }
  else
  {
    fKRB5ModuleStarted = 1;
    Module = ASN1_CreateModule(
               0x10000,
               1024,
               4096,
               49,
               off_180047350,
               off_1800471C0,
               off_180047030,
               qword_180049F80,
               846556016);
    PKU2UMSG_Module = Module;
  }
  v47 = ASN1_CreateEncoder(Module, &hObject, 0, 0, 0);
  if ( v47 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, v47);
      v51 = 60;
      goto LABEL_130;
    }
  }
  else
  {
    v48 = ASN1_Encode(hObject, &v78, 30, 16, 0, 0);
    if ( v48 >= 0 )
    {
      v49 = *((unsigned int *)hObject + 7);
      if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
      {
        v50 = (unsigned __int8 *)(*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))((unsigned int)v49);
      }
      else
      {
        v65 = (unsigned __int8 *)(**((__int64 (__fastcall ***)(_QWORD))Pku2uGlobalBaseSSP + 31))((unsigned int)v49);
        v50 = v65;
        if ( v65 )
        {
          memset_0(v65, 0, v49);
          *v81 = v50;
          goto LABEL_119;
        }
      }
      *v81 = v50;
      if ( !v50 )
      {
        v52 = hObject;
        v51 = 60;
        v53 = 0;
        goto LABEL_129;
      }
LABEL_119:
      v51 = 0;
      memcpy_0(v50, *((const void **)hObject + 2), *((unsigned int *)hObject + 7));
      v52 = hObject;
      v53 = *((_DWORD *)hObject + 7);
LABEL_129:
      *v82 = v53;
      ASN1_FreeEncoded(v52, v52[2]);
      goto LABEL_130;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        78,
        &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
        (unsigned int)v48);
  }
  v51 = 60;
LABEL_130:
  if ( hObject )
    ASN1_CloseEncoder();
  if ( v51 )
  {
    switch ( v51 )
    {
      case 7:
        UserNameWithDomainPrefixHResult = -1073741429;
        break;
      case 12:
        UserNameWithDomainPrefixHResult = -1073741714;
        break;
      case 14:
        UserNameWithDomainPrefixHResult = -1073741059;
        break;
      case 16:
        UserNameWithDomainPrefixHResult = -1073741637;
        break;
      case 18:
        UserNameWithDomainPrefixHResult = -1073741710;
        break;
      case 23:
        UserNameWithDomainPrefixHResult = -1073741711;
        break;
      case 24:
      case 25:
      case 41:
        UserNameWithDomainPrefixHResult = -1073741718;
        break;
      case 27:
      case 69:
        UserNameWithDomainPrefixHResult = -1073740792;
        break;
      case 28:
        UserNameWithDomainPrefixHResult = -1073741424;
        break;
      case 29:
      case 68:
        UserNameWithDomainPrefixHResult = -1073741730;
        break;
      case 32:
      case 33:
      case 37:
        UserNameWithDomainPrefixHResult = -1073741517;
        break;
      case 35:
        UserNameWithDomainPrefixHResult = -2146893022;
        break;
      case 39:
      case 40:
      case 71:
        UserNameWithDomainPrefixHResult = -1073741811;
        break;
      case 45:
        UserNameWithDomainPrefixHResult = -1073741022;
        break;
      case 52:
        UserNameWithDomainPrefixHResult = -1073741306;
        break;
      case 60:
        UserNameWithDomainPrefixHResult = -1073741670;
        break;
      case 70:
        UserNameWithDomainPrefixHResult = -2146869247;
        break;
      case 72:
        UserNameWithDomainPrefixHResult = -2146885616;
        break;
      case 73:
        UserNameWithDomainPrefixHResult = -2146885614;
        break;
      case 74:
        UserNameWithDomainPrefixHResult = -2146885613;
        break;
      case 75:
      case 76:
        UserNameWithDomainPrefixHResult = -1073741063;
        break;
      case 77:
        UserNameWithDomainPrefixHResult = -2146762480;
        break;
      default:
        UserNameWithDomainPrefixHResult = -1073741715;
        break;
    }
LABEL_97:
    if ( UserNameWithDomainPrefixHResult >= 0 )
    {
      v17 = v67;
      goto LABEL_59;
    }
    goto LABEL_57;
  }
  v58 = 0;
  if ( !*v6 )
  {
    *v6 = (struct _PKU2U_CONTEXT *)v8;
    v58 = 1;
    _InterlockedDecrement((volatile signed __int32 *)v8 + 80);
    v8 = 0;
  }
  v17 = v67;
  UserNameWithDomainPrefixHResult = 0;
  if ( v58 )
    goto LABEL_58;
LABEL_59:
  if ( v17 )
    Pku2uRevertImpersonation(v11);
  if ( v11 )
    CloseHandle(v11);
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v8 )
  {
    *((_DWORD *)v8 + 18) = UserNameWithDomainPrefixHResult;
    _InterlockedDecrement((volatile signed __int32 *)v8 + 80);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 2, 0xFFFFFFFF) <= 1 )
      Pku2uFreeContext((struct _PKU2U_CONTEXT *)v8);
  }
  v33 = v73;
  if ( v73 )
  {
    do
    {
      v66 = (_QWORD *)*v33;
      Pku2uFree(v33);
      v33 = v66;
    }
    while ( v66 );
  }
  if ( a1 )
    Pku2uDereferenceSecondaryCredential(a1);
  v34 = v80;
  if ( v80 )
  {
    do
    {
      v35 = (void *)v34[1];
      if ( v35 )
        Pku2uFree(v35);
      v36 = (_QWORD *)*v34;
      Pku2uFree(v34);
      v34 = v36;
    }
    while ( v36 );
  }
  v80 = 0;
  if ( (_QWORD)v79 )
  {
    if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
      v37 = *(void (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 392LL);
    else
      v37 = *(void (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 31) + 8LL);
    v37();
    *(_QWORD *)&v79 = 0;
  }
  if ( v77.Buffer )
    basessp::BaseSSP::WSTFree(Pku2uGlobalBaseSSP, v77.Buffer);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      153,
      &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
      (unsigned int)UserNameWithDomainPrefixHResult);
  return (unsigned int)UserNameWithDomainPrefixHResult;
}

```

## disassembly

```asm
0x180009070  push    rbp
0x180009072  push    rbx
0x180009073  push    rsi
0x180009074  push    rdi
0x180009075  push    r12
0x180009077  push    r13
0x180009079  push    r14
0x18000907b  push    r15
0x18000907d  lea     rbp, [rsp-68h]
0x180009082  sub     rsp, 168h
0x180009089  mov     rax, cs:__security_cookie
0x180009090  xor     rax, rsp
0x180009093  mov     [rbp+0A0h+var_48], rax
0x180009097  mov     r12, [rbp+0A0h+arg_28]
0x18000909e  xorps   xmm0, xmm0
0x1800090a1  mov     r13, [rbp+0A0h+arg_20]
0x1800090a8  mov     rsi, rcx
0x1800090ab  xor     ecx, ecx
0x1800090ad  mov     [rbp+0A0h+var_A0], r9
0x1800090b1  xor     eax, eax
0x1800090b3  mov     qword ptr [rbp+0A0h+var_F0], rdx
0x1800090b7  mov     rdi, [r12]
0x1800090bb  mov     ebx, r8d
0x1800090be  mov     [rsp+1A0h+TokenHandle], rdi
0x1800090c3  mov     r14, rdx
0x1800090c6  mov     [rbp+0A0h+var_A8], r13
0x1800090ca  mov     r15d, ecx
0x1800090cd  mov     [rbp+0A0h+var_120], r12
0x1800090d1  mov     [rbp+0A0h+P], rcx
0x1800090d5  movups  [rbp+0A0h+var_D0], xmm0
0x1800090d9  mov     [rbp+0A0h+var_B0], rax
0x1800090dd  movups  [rbp+0A0h+var_C0], xmm0
0x1800090e1  mov     [rbp+0A0h+var_110], rcx
0x1800090e5  movups  xmmword ptr [rbp+0A0h+var_E0.Length], xmm0
0x1800090e9  mov     qword ptr [rbp+0A0h+PerformanceCount], rcx
0x1800090ed  mov     qword ptr [rbp+0A0h+var_108], rcx
0x1800090f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090f8  lea     rax, WPP_GLOBAL_Control
0x1800090ff  cmp     rcx, rax
0x180009102  jnz     loc_1800096C3
0x180009108  lea     rcx, [rbp+0A0h+PerformanceCount]; lpPerformanceCount
0x18000910c  call    cs:__imp_QueryPerformanceCounter
0x180009112  mov     rax, [rbp+0A0h+var_A0]
0x180009116  xor     ecx, ecx
0x180009118  mov     [rax], ecx
0x18000911a  mov     [r13+0], rcx
0x18000911e  mov     r13d, 8
0x180009124  test    rdi, rdi
0x180009127  jz      loc_180009407
0x18000912d  lock inc dword ptr [rdi+8]
0x180009131  mov     rsi, [rdi+10h]
0x180009135  mov     rcx, rsi; struct _PKU2U_SECONDARY_CREDENTIAL *
0x180009138  call    ?Pku2uReferenceSecondaryCredential@@YAXPEAU_PKU2U_SECONDARY_CREDENTIAL@@@Z; Pku2uReferenceSecondaryCredential(_PKU2U_SECONDARY_CREDENTIAL *)
0x18000913d  lea     r14, WPP_GLOBAL_Control
0x180009144  mov     eax, 1
0x180009149  lock xadd [rdi+140h], eax
0x180009151  inc     eax
0x180009153  cmp     eax, 1
0x180009156  jg      loc_180009B0B
0x18000915c  cmp     dword ptr [rsi+20h], 1
0x180009160  jz      loc_1800093B2
0x180009166  cmp     [rsi+20h], r15d
0x18000916a  jz      loc_180009B8F
0x180009170  lea     rax, [rsp+1A0h+var_140]
0x180009175  mov     [rsp+1A0h+var_140], r13d
0x18000917a  mov     qword ptr [rsp+1A0h+nSubAuthority3], rax
0x18000917f  lea     r9, [rsp+1A0h+IsMember]
0x180009184  lea     rax, [rbp+0A0h+SidToCheck]
0x180009188  xor     ebx, ebx
0x18000918a  xor     r8d, r8d
0x18000918d  mov     qword ptr [rsp+1A0h+nSubAuthority2], rax
0x180009192  xor     edx, edx
0x180009194  mov     [rsp+1A0h+IsMember], ebx
0x180009198  lea     rcx, WNF_SEB_INTERNET_PRESENT
0x18000919f  mov     [rbp+0A0h+SidToCheck], rbx
0x1800091a3  call    cs:__imp_NtQueryWnfStateData
0x1800091a9  test    eax, eax
0x1800091ab  jns     loc_1800093E7
0x1800091b1  mov     rax, [rsi+18h]
0x1800091b5  lea     rcx, [rbp+0A0h+pIdentifierAuthority]; pIdentifierAuthority
0x1800091b9  xor     r9d, r9d; nSubAuthority1
0x1800091bc  mov     [rsp+1A0h+var_140], ebx
0x1800091c0  mov     r8d, 14h; nSubAuthority0
0x1800091c6  mov     [rsp+1A0h+hObject], rbx
0x1800091cb  mov     dl, 1; nSubAuthorityCount
0x1800091cd  mov     [rbp+0A0h+SidToCheck], rbx
0x1800091d1  mov     r14, [rax+20h]
0x1800091d5  mov     r13, rbx
0x1800091d8  lea     rax, [rbp+0A0h+SidToCheck]
0x1800091dc  mov     dword ptr [rbp+0A0h+pIdentifierAuthority.Value], ebx
0x1800091df  mov     [rsp+1A0h+pSid], rax; pSid
0x1800091e4  mov     [rsp+1A0h+nSubAuthority7], ebx; nSubAuthority7
0x1800091e8  mov     [rsp+1A0h+nSubAuthority6], ebx; nSubAuthority6
0x1800091ec  mov     [rsp+1A0h+nSubAuthority5], ebx; nSubAuthority5
0x1800091f0  mov     [rsp+1A0h+nSubAuthority4], ebx; nSubAuthority4
0x1800091f4  mov     [rsp+1A0h+nSubAuthority3], ebx; nSubAuthority3
0x1800091f8  mov     [rsp+1A0h+nSubAuthority2], ebx; nSubAuthority2
0x1800091fc  mov     word ptr [rbp+0A0h+pIdentifierAuthority.Value+4], 500h
0x180009202  mov     [rsp+1A0h+IsMember], ebx
0x180009206  call    cs:__imp_AllocateAndInitializeSid
0x18000920c  test    eax, eax
0x18000920e  jz      loc_180009C88
0x180009214  mov     rdx, [rbp+0A0h+SidToCheck]; SidToCheck
0x180009218  lea     r8, [rsp+1A0h+IsMember]; IsMember
0x18000921d  mov     rcx, r14; TokenHandle
0x180009220  call    cs:__imp_CheckTokenMembership
0x180009226  test    eax, eax
0x180009228  jz      loc_180009C95
0x18000922e  mov     rcx, [rbp+0A0h+SidToCheck]; pSid
0x180009232  test    rcx, rcx
0x180009235  jnz     loc_180009CDB
0x18000923b  test    ebx, ebx
0x18000923d  jle     short loc_18000924A
0x18000923f  movzx   ebx, bx
0x180009242  or      ebx, 0C0070000h
0x180009248  test    ebx, ebx
0x18000924a  js      loc_1800093AA
0x180009250  cmp     [rsp+1A0h+IsMember], r13d
0x180009255  jnz     short loc_1800092D0
0x180009257  mov     [rbp+0A0h+ThreadInformation], r14
0x18000925b  lea     r9, [rsp+1A0h+TokenHandle]; TokenHandle
0x180009260  xor     r14d, r14d
0x180009263  mov     r8b, 1; OpenAsSelf
0x180009266  mov     edx, 0Ch; DesiredAccess
0x18000926b  mov     [rsp+1A0h+TokenHandle], r14
0x180009270  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180009277  call    cs:__imp_NtOpenThreadToken
0x18000927d  mov     ecx, 80000000h
0x180009282  mov     ebx, eax
0x180009284  add     eax, ecx
0x180009286  test    ecx, eax
0x180009288  jz      loc_1800094E1
0x18000928e  mov     r9d, 8; ThreadInformationLength
0x180009294  mov     [rsp+1A0h+var_140], 1
0x18000929c  lea     r8, [rbp+0A0h+ThreadInformation]; ThreadInformation
0x1800092a0  mov     edx, 5; ThreadInformationClass
0x1800092a5  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800092ac  call    cs:__imp_NtSetInformationThread
0x1800092b2  mov     r13, [rsp+1A0h+TokenHandle]
0x1800092b7  mov     ebx, eax
0x1800092b9  mov     [rsp+1A0h+TokenHandle], r14
0x1800092be  mov     r14d, [rsp+1A0h+var_140]
0x1800092c3  mov     [rsp+1A0h+hObject], r13
0x1800092c8  test    ebx, ebx
0x1800092ca  js      loc_18000983D
0x1800092d0  xor     eax, eax
0x1800092d2  lea     r8, [rsi+78h]
0x1800092d6  cmp     dword ptr [rsi+20h], 1
0x1800092da  cmovz   r8, rax
0x1800092de  mov     rax, qword ptr [rbp+0A0h+var_F0]
0x1800092e2  test    rax, rax
0x1800092e5  jnz     loc_1800096E7
0x1800092eb  xor     ecx, ecx
0x1800092ed  lea     r9, [rbp+0A0h+P]
0x1800092f1  mov     edx, r15d
0x1800092f4  call    cs:__imp_IntPstGetTrustAnchors
0x1800092fa  cmp     [rsp+1A0h+var_140], 0
0x1800092ff  mov     ebx, eax
0x180009301  jnz     loc_18000970B
0x180009307  test    ebx, ebx
0x180009309  js      loc_180009510
0x18000930f  mov     r14, [rbp+0A0h+P]
0x180009313  xor     eax, eax
0x180009315  xor     r15d, r15d
0x180009318  mov     [rbp+0A0h+var_110], rax
0x18000931c  xor     ebx, ebx
0x18000931e  cmp     ebx, [r14+8]
0x180009322  jb      loc_180009D2F
0x180009328  mov     qword ptr [rsp+1A0h+nSubAuthority5], 0; lpUsedDefaultChar
0x180009331  lea     r8, WideCharStr; "WELLKNOWN:PKU2U"
0x180009338  mov     qword ptr [rsp+1A0h+nSubAuthority4], 0; lpDefaultChar
0x180009341  mov     r14d, 1Eh
0x180009347  shr     r14d, 1
0x18000934a  xor     edx, edx; dwFlags
0x18000934c  mov     r9d, r14d; cchWideChar
0x18000934f  mov     [rsp+1A0h+nSubAuthority3], 0; cbMultiByte
0x180009357  mov     ecx, 0FDE9h; CodePage
0x18000935c  mov     qword ptr [rbp+0A0h+var_D0+8], rax
0x180009360  mov     qword ptr [rbp+0A0h+var_C0], 0
0x180009368  mov     qword ptr [rsp+1A0h+nSubAuthority2], 0; lpMultiByteStr
0x180009371  call    cs:__imp_WideCharToMultiByte
0x180009377  mov     r15d, eax
0x18000937a  test    eax, eax
0x18000937c  jz      loc_180009799
0x180009382  cmp     eax, 0FFFCh
0x180009387  ja      loc_180009DAA
0x18000938d  lea     r12d, [rax+1]
0x180009391  cmp     r12d, eax
0x180009394  jnb     loc_180009DBA
0x18000939a  mov     ecx, 216h; dwErrCode
0x18000939f  call    cs:__imp_SetLastError
0x1800093a5  jmp     loc_180009795
0x1800093aa  mov     r14d, r13d
0x1800093ad  jmp     loc_1800092C8
0x1800093b2  mov     rcx, rdi; struct _PKU2U_CONTEXT *
0x1800093b5  call    ?Pku2uPopulateContextWithCredmanCreds@@YAJPEAU_PKU2U_CONTEXT@@@Z; Pku2uPopulateContextWithCredmanCreds(_PKU2U_CONTEXT *)
0x1800093ba  mov     ebx, eax
0x1800093bc  test    eax, eax
0x1800093be  js      loc_180009B4C
0x1800093c4  cmp     [rdi+18h], r15
0x1800093c8  jz      loc_180009166
0x1800093ce  mov     rcx, rsi; struct _PKU2U_SECONDARY_CREDENTIAL *
0x1800093d1  call    ?Pku2uDereferenceSecondaryCredential@@YAXPEAU_PKU2U_SECONDARY_CREDENTIAL@@@Z; Pku2uDereferenceSecondaryCredential(_PKU2U_SECONDARY_CREDENTIAL *)
0x1800093d6  mov     rsi, [rdi+18h]
0x1800093da  mov     rcx, rsi; struct _PKU2U_SECONDARY_CREDENTIAL *
0x1800093dd  call    ?Pku2uReferenceSecondaryCredential@@YAXPEAU_PKU2U_SECONDARY_CREDENTIAL@@@Z; Pku2uReferenceSecondaryCredential(_PKU2U_SECONDARY_CREDENTIAL *)
0x1800093e2  jmp     loc_180009166
0x1800093e7  cmp     [rsp+1A0h+var_140], r13d
0x1800093ec  jnz     loc_1800091B1
0x1800093f2  test    byte ptr [rbp+0A0h+SidToCheck], 2
0x1800093f6  jz      loc_1800091B1
0x1800093fc  mov     r15d, 1
0x180009402  jmp     loc_1800091B1
0x180009407  test    rsi, rsi
0x18000940a  jz      loc_18000982D
0x180009410  mov     rcx, rsi; struct _PKU2U_SECONDARY_CREDENTIAL *
0x180009413  call    ?Pku2uReferenceSecondaryCredential@@YAXPEAU_PKU2U_SECONDARY_CREDENTIAL@@@Z; Pku2uReferenceSecondaryCredential(_PKU2U_SECONDARY_CREDENTIAL *)
0x180009418  test    r14, r14
0x18000941b  jz      short loc_180009427
0x18000941d  cmp     [r14], r15w
0x180009421  jnz     loc_180009AE5
0x180009427  xor     ecx, ecx; int
0x180009429  lea     rax, [rsp+1A0h+TokenHandle]
0x18000942e  mov     r9d, ebx; unsigned int
0x180009431  mov     r8, r14; struct _UNICODE_STRING *
0x180009434  mov     qword ptr [rsp+1A0h+nSubAuthority2], rax; struct _PKU2U_CONTEXT **
0x180009439  mov     rdx, rsi; struct _PKU2U_SECONDARY_CREDENTIAL *
0x18000943c  call    ?Pku2uAllocateContext@@YAJHPEAU_PKU2U_SECONDARY_CREDENTIAL@@PEAU_UNICODE_STRING@@KPEAPEAU_PKU2U_CONTEXT@@@Z; Pku2uAllocateContext(int,_PKU2U_SECONDARY_CREDENTIAL *,_UNICODE_STRING *,ulong,_PKU2U_CONTEXT * *)
0x180009441  mov     rdi, [rsp+1A0h+TokenHandle]
0x180009446  mov     ebx, eax
0x180009448  test    eax, eax
0x18000944a  js      loc_180009AF9
0x180009450  mov     rdx, [rdi+50h]
0x180009454  lea     rax, aHttp; "HTTP"
0x18000945b  mov     [rbp+0A0h+String1.Buffer], rax
0x18000945f  lea     rax, aHttps; "HTTPS"
0x180009466  mov     [rbp+0A0h+var_88.Buffer], rax
0x18000946a  mov     qword ptr [rbp+0A0h+String1.Length], 0A0008h
0x180009472  mov     qword ptr [rbp+0A0h+var_88.Length], 0C000Ah
0x18000947a  test    rdx, rdx
0x18000947d  jz      short loc_18000948A
0x18000947f  cmp     word ptr [rdx+2], 2
0x180009484  jz      loc_1800097DC
0x18000948a  mov     r8, cs:WPP_GLOBAL_Control
0x180009491  lea     r14, WPP_GLOBAL_Control
0x180009498  cmp     r8, r14
0x18000949b  jz      loc_180009144
0x1800094a1  test    byte ptr [r8+1Ch], 20h
0x1800094a6  jz      loc_180009144
0x1800094ac  mov     rax, [rdi+10h]
0x1800094b0  mov     edx, 92h
0x1800094b5  mov     r9, rdi
0x1800094b8  mov     rcx, [rax+18h]
0x1800094bc  lea     rax, [rdi+58h]
0x1800094c0  mov     qword ptr [rsp+1A0h+nSubAuthority4], rax; __int64
0x1800094c5  mov     eax, [rcx+18h]
0x1800094c8  mov     [rsp+1A0h+nSubAuthority3], eax; char
0x1800094cc  mov     eax, [rcx+1Ch]
0x1800094cf  mov     rcx, [r8+10h]; LoggerHandle
0x1800094d3  mov     [rsp+1A0h+nSubAuthority2], eax; char
0x1800094d7  call    WPP_SF_qDDZ
0x1800094dc  jmp     loc_180009144
0x1800094e1  cmp     ebx, 0C000007Ch
0x1800094e7  jz      loc_18000928E
0x1800094ed  mov     rcx, [rsp+1A0h+TokenHandle]; hObject
0x1800094f2  mov     [rsp+1A0h+var_140], r14d
0x1800094f7  mov     [rsp+1A0h+hObject], r13
0x1800094fc  test    rcx, rcx
0x1800094ff  jz      loc_1800092C8
0x180009505  call    cs:__imp_CloseHandle
0x18000950b  jmp     loc_1800092C8
0x180009510  mov     rcx, cs:WPP_GLOBAL_Control
0x180009517  lea     rax, WPP_GLOBAL_Control
0x18000951e  cmp     rcx, rax
0x180009521  jz      short loc_18000956C
0x180009523  test    byte ptr [rcx+1Ch], 2
0x180009527  jz      short loc_18000956C
0x180009529  mov     rcx, [rcx+10h]
0x18000952d  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x180009534  mov     edx, 98h
0x180009539  mov     r9d, ebx
0x18000953c  call    WPP_SF_d
0x180009541  jmp     short loc_18000956C
0x180009543  mov     rax, [rax+0F0h]
0x18000954a  mov     ecx, 18h
0x18000954f  mov     rax, [rax+180h]
0x180009556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000955b  mov     r8, rax
0x18000955e  test    rax, rax
0x180009561  jnz     loc_180009D70
0x180009567  mov     ebx, 0C0000017h
0x18000956c  mov     r15, [rsp+1A0h+hObject]
0x180009571  mov     r14d, [rsp+1A0h+var_140]
0x180009576  lea     rcx, [rbp+0A0h+var_108]; lpPerformanceCount
0x18000957a  call    cs:__imp_QueryPerformanceCounter
0x180009580  mov     rax, [r12]
0x180009584  mov     r8, rsi; struct _PKU2U_SECONDARY_CREDENTIAL *
0x180009587  mov     r9, [rbp+0A0h+P]; struct _SecPkgContext_IssuerListInfoEx *
0x18000958b  mov     rdx, qword ptr [rbp+0A0h+var_108]; union _LARGE_INTEGER
0x18000958f  mov     rcx, qword ptr [rbp+0A0h+PerformanceCount]; union _LARGE_INTEGER
  ... truncated ...
```
