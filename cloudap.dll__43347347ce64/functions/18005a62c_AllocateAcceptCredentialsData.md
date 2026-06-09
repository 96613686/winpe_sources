# AllocateAcceptCredentialsData

- ea: `0x18005a62c`
- end: `0x18005acee`
- name: `AllocateAcceptCredentialsData`
- size: `1730`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020b10`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18002bff0`
- `0x18002fd40`
- `0x1800336a4`
- `0x18003faf4`
- `0x180042410`
- `0x18005a62c`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005aca2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005aca2`
- `ntdll!NtClose` at `0x18005ac93`
- `ntdll!NtClose` at `0x18005acb6`
- `ntdll!NtClose` at `0x18005ac93`
- `ntdll!NtClose` at `0x18005acb6`
- `ntdll!NtOpenThreadToken` at `0x18005a79a`
- `ntdll!NtOpenThreadToken` at `0x18005a79a`
- `ntdll!NtSetInformationThread` at `0x18005ac84`
- `ntdll!NtSetInformationThread` at `0x18005ac84`
- `ntdll!NtDuplicateToken` at `0x18005a82a`
- `ntdll!NtDuplicateToken` at `0x18005a82a`

## string_xrefs

- `0x18005ab5f`: `DuplicateSID`
- `0x18005a7b8`: `NtOpenThreadToken`
- `0x18005a872`: `ImpersonateClient`
- `0x18005a6cb`: `onecore\ds\ext\cloudap\dll\credapi.cpp`
- `0x18005a724`: `onecore\ds\ext\cloudap\dll\credapi.cpp`
- `0x18005a763`: `onecore\ds\ext\cloudap\dll\credapi.cpp`
- `0x18005a846`: `NtDuplicateToken`

## pseudocode

```c
__int64 __fastcall AllocateAcceptCredentialsData(
        int a1,
        struct _UNICODE_STRING *a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5)
{
  int v8; // ebx
  __int64 v9; // rax
  __int64 v10; // r13
  unsigned int v11; // edi
  const char *v12; // r9
  __int64 v13; // r8
  const char *v14; // r9
  const char *v15; // r9
  const char *v16; // r9
  const char *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rbx
  __int64 v21; // r8
  const char *v22; // r9
  __int16 v23; // ax
  void *v24; // rax
  const char *v25; // r9
  __int64 v26; // r8
  __int64 v27; // rsi
  _OWORD *v28; // rax
  const char *v29; // r9
  __int64 v30; // r8
  _OWORD *v31; // rbx
  char *v32; // rbx
  __int64 *v33; // rax
  void *v34; // rcx
  __int64 TokenType; // [rsp+20h] [rbp-81h]
  const char *NewTokenHandle; // [rsp+28h] [rbp-79h]
  char v38; // [rsp+40h] [rbp-61h]
  int v39; // [rsp+44h] [rbp-5Dh]
  void *TokenHandle; // [rsp+48h] [rbp-59h] BYREF
  void *ThreadInformation; // [rsp+50h] [rbp-51h] BYREF
  __int64 v42; // [rsp+58h] [rbp-49h] BYREF
  __int64 v43; // [rsp+60h] [rbp-41h]
  __int64 *v44; // [rsp+68h] [rbp-39h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-31h] BYREF
  __int64 v46; // [rsp+A0h] [rbp-1h] BYREF
  int v47; // [rsp+A8h] [rbp+7h]

  v44 = a5;
  v43 = a4;
  ThreadInformation = 0;
  TokenHandle = 0;
  v46 = 0;
  v47 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( a3 )
    v8 = *(_DWORD *)(a3 + 80) & 0x1000;
  else
    v8 = 0;
  v39 = v8;
  v9 = ((__int64 (__fastcall *)(__int64))g_pLsaFunctionTable->AllocateLsaHeap)(56);
  v42 = v9;
  v10 = v9;
  if ( v9 )
  {
    *(_DWORD *)v9 = a1;
    v11 = DuplicateUnicodeString2(a2, (struct _UNICODE_STRING *)(v9 + 8));
    if ( v11 )
    {
      v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v14, 214, "DuplicateUnicodeString2", &Class);
      goto LABEL_53;
    }
    v11 = ImpersonateClient(&ThreadInformation);
    if ( (v11 & 0x80000000) != 0 )
    {
      v38 = 0;
      v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v17, 247, "ImpersonateClient", &Class);
      *(_QWORD *)(v10 + 40) = 0;
    }
    else
    {
      v38 = 1;
      v11 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x2000000u, 1u, &TokenHandle);
      if ( v11 )
      {
        v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v15, 226, "NtOpenThreadToken", &Class);
        goto LABEL_52;
      }
      memset(&ObjectAttributes.RootDirectory, 0, 20);
      ObjectAttributes.SecurityDescriptor = 0;
      LOWORD(v47) = 0;
      ObjectAttributes.SecurityQualityOfService = &v46;
      ObjectAttributes.Length = 48;
      v46 = 0x20000000CLL;
      v11 = NtDuplicateToken(TokenHandle, 0x2Cu, &ObjectAttributes, 0, TokenImpersonation, (PHANDLE)(v10 + 40));
      if ( v11 )
      {
        v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
        LODWORD(TokenType) = 243;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v16, TokenType, "NtDuplicateToken", &Class);
LABEL_52:
        NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
        goto LABEL_53;
      }
    }
    if ( a3 )
    {
      v18 = 224;
      if ( !v8 )
        v18 = 200;
      v19 = ((__int64 (__fastcall *)(__int64))g_pLsaFunctionTable->AllocateLsaHeap)(v18);
      *(_QWORD *)(v10 + 24) = v19;
      v20 = v19;
      if ( !v19 )
      {
        v11 = -1073741801;
        v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
        NewTokenHandle = "AllocateLsaHeap(SECPKG_PRIMARY_CRED)";
        LODWORD(TokenType) = 267;
LABEL_21:
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v21, v22, TokenType, NewTokenHandle, &Class);
        goto LABEL_51;
      }
      *(_QWORD *)v19 = *(_QWORD *)a3;
      *(_DWORD *)(v19 + 80) = *(_DWORD *)(a3 + 80);
      v11 = DuplicateUnicodeString2((struct _UNICODE_STRING *)(a3 + 8), (struct _UNICODE_STRING *)(v19 + 8));
      if ( v11 )
      {
        v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
        NewTokenHandle = "DuplicateUnicodeString2(DownlevelName)";
        LODWORD(TokenType) = 277;
LABEL_25:
        v21 = v11;
        goto LABEL_21;
      }
      v11 = DuplicateUnicodeString2((struct _UNICODE_STRING *)(a3 + 24), (struct _UNICODE_STRING *)(v20 + 24));
      if ( v11 )
      {
        v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
        NewTokenHandle = "DuplicateUnicodeString2(DomainName)";
        LODWORD(TokenType) = 281;
        goto LABEL_25;
      }
      v11 = DuplicateUnicodeString2((struct _UNICODE_STRING *)(a3 + 40), (struct _UNICODE_STRING *)(v20 + 40));
      if ( v11 )
      {
        v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
        NewTokenHandle = "DuplicateUnicodeString2(Password)";
        LODWORD(TokenType) = 285;
        goto LABEL_25;
      }
      v11 = DuplicateUnicodeString2((struct _UNICODE_STRING *)(a3 + 56), (struct _UNICODE_STRING *)(v20 + 56));
      if ( v11 )
      {
        v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
        NewTokenHandle = "DuplicateUnicodeString2(OldPassword)";
        LODWORD(TokenType) = 289;
        goto LABEL_25;
      }
      v11 = DuplicateUnicodeString2((struct _UNICODE_STRING *)(a3 + 88), (struct _UNICODE_STRING *)(v20 + 88));
      if ( v11 )
      {
        v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
        NewTokenHandle = "DuplicateUnicodeString2(DnsDomainName)";
        LODWORD(TokenType) = 293;
        goto LABEL_25;
      }
      v11 = DuplicateUnicodeString2((struct _UNICODE_STRING *)(a3 + 104), (struct _UNICODE_STRING *)(v20 + 104));
      if ( v11 )
      {
        v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
        NewTokenHandle = "DuplicateUnicodeString2(Upn)";
        LODWORD(TokenType) = 297;
        goto LABEL_25;
      }
      v11 = DuplicateUnicodeString2((struct _UNICODE_STRING *)(a3 + 120), (struct _UNICODE_STRING *)(v20 + 120));
      if ( v11 )
      {
        v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
        NewTokenHandle = "DuplicateUnicodeString2(LogonServer)";
        LODWORD(TokenType) = 301;
        goto LABEL_25;
      }
      v23 = *(_WORD *)(a3 + 136);
      *(_WORD *)(v20 + 138) = v23;
      *(_WORD *)(v20 + 136) = v23;
      if ( *(_WORD *)(a3 + 136) )
      {
        v24 = (void *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(*(unsigned __int16 *)(a3 + 136));
        *(_QWORD *)(v20 + 144) = v24;
        if ( !v24 )
        {
          v11 = -1073741801;
          v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
          LODWORD(TokenType) = 310;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v26, v25, TokenType, "AllocateLsaHeap(Spare1)", &Class);
          goto LABEL_51;
        }
        memcpy_0(v24, *(const void **)(a3 + 144), *(unsigned __int16 *)(v20 + 136));
      }
      v11 = DuplicateSID(*(void **)(a3 + 72), (void **)(v20 + 72));
      if ( v11 )
      {
        v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
        NewTokenHandle = "DuplicateSID";
        LODWORD(TokenType) = 317;
        goto LABEL_25;
      }
      if ( v39 )
      {
        *(_QWORD *)(v20 + 200) = *(_QWORD *)(a3 + 200);
        *(_QWORD *)(v20 + 208) = *(_QWORD *)(a3 + 208);
        *(_DWORD *)(v20 + 216) = *(_DWORD *)(a3 + 216);
      }
    }
    v27 = v43;
    if ( v43 )
    {
      v28 = (_OWORD *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(*(_DWORD *)(v43 + 16) + 32 + (unsigned int)*(unsigned __int16 *)(v43 + 2));
      *(_QWORD *)(v10 + 32) = v28;
      if ( !v28 )
      {
        v11 = -1073741801;
        v29 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
        LODWORD(TokenType) = 341;
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          v30,
          v29,
          TokenType,
          "AllocateLsaHeap(SECPKG_SUPPLEMENTAL_CRED)",
          &Class);
        goto LABEL_51;
      }
      v31 = v28 + 2;
      *v28 = *(_OWORD *)v27;
      v28[1] = *(_OWORD *)(v27 + 16);
      memcpy_0(v28 + 2, *(const void **)(v27 + 8), *(unsigned __int16 *)(v27 + 2));
      *(_QWORD *)(*(_QWORD *)(v10 + 32) + 8LL) = v31;
      v32 = (char *)v31 + *(unsigned __int16 *)(v27 + 2);
      memcpy_0(v32, *(const void **)(v27 + 24), *(unsigned int *)(v27 + 16));
      *(_QWORD *)(*(_QWORD *)(v10 + 32) + 24LL) = v32;
    }
    v33 = v44;
    *(_DWORD *)(v10 + 48) = 4624;
    *v33 = v10;
    v10 = 0;
    v42 = 0;
LABEL_51:
    if ( !v38 )
      goto LABEL_53;
    goto LABEL_52;
  }
  v11 = -1073741801;
  v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v13, v12, 208, "AllocateLsaHeap(ACCEPT_CREDENTIALS_DATA)", &Class);
LABEL_53:
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( ThreadInformation )
    CloseHandle(ThreadInformation);
  if ( v10 )
  {
    v34 = *(void **)(v10 + 40);
    if ( v34 )
      NtClose(v34);
  }
  FreeAcceptCredentialsData(&v42);
  return v11;
}

```

## disassembly

```asm
0x18005a62c  mov     [rsp-8+arg_0], rbx
0x18005a631  push    rbp
0x18005a632  push    rsi
0x18005a633  push    rdi
0x18005a634  push    r12
0x18005a636  push    r13
0x18005a638  push    r14
0x18005a63a  push    r15
0x18005a63c  lea     rbp, [rsp-1Fh]
0x18005a641  sub     rsp, 0C0h
0x18005a648  mov     rax, cs:__security_cookie
0x18005a64f  xor     rax, rsp
0x18005a652  mov     [rbp+4Fh+var_40], rax
0x18005a656  mov     rax, [rbp+4Fh+arg_20]
0x18005a65a  xor     r15d, r15d
0x18005a65d  xorps   xmm0, xmm0
0x18005a660  mov     [rbp+4Fh+var_88], rax
0x18005a664  xor     eax, eax
0x18005a666  mov     [rbp+4Fh+var_90], r9
0x18005a66a  mov     [rbp+4Fh+ThreadInformation], r15
0x18005a66e  mov     rsi, r8
0x18005a671  mov     [rbp+4Fh+TokenHandle], r15
0x18005a675  mov     r14, rdx
0x18005a678  mov     [rbp+4Fh+var_50], rax
0x18005a67c  mov     edi, ecx
0x18005a67e  mov     [rbp+4Fh+var_48], eax
0x18005a681  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x18005a685  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x18005a689  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18005a68d  test    r8, r8
0x18005a690  jz      short loc_18005A69E
0x18005a692  mov     ebx, [r8+50h]
0x18005a696  and     ebx, 1000h
0x18005a69c  jmp     short loc_18005A6A1
0x18005a69e  mov     ebx, r15d
0x18005a6a1  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005a6a8  mov     ecx, 38h ; '8'
0x18005a6ad  mov     [rbp+4Fh+var_AC], ebx
0x18005a6b0  mov     rax, [rax+28h]
0x18005a6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a6b9  mov     [rbp+4Fh+var_98], rax
0x18005a6bd  mov     r13, rax
0x18005a6c0  test    rax, rax
0x18005a6c3  jnz     short loc_18005A710
0x18005a6c5  mov     r8d, 0C0000017h
0x18005a6cb  lea     rcx, aOnecoreDsExtCl_4; "onecore\\ds\\ext\\cloudap\\dll\\credapi"...
0x18005a6d2  mov     edi, r8d
0x18005a6d5  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005a6da  mov     r9, rax
0x18005a6dd  lea     r12, Class
0x18005a6e4  mov     [rsp+0F0h+var_C0], r12
0x18005a6e9  lea     rax, aAllocatelsahea_2; "AllocateLsaHeap(ACCEPT_CREDENTIALS_DATA"...
0x18005a6f0  mov     [rsp+0F0h+NewTokenHandle], rax
0x18005a6f5  mov     dword ptr [rsp+0F0h+TokenType], 0D0h
0x18005a6fd  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005a704  xor     ecx, ecx
0x18005a706  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005a70b  jmp     loc_18005AC8A
0x18005a710  lea     rdx, [rax+8]; struct _UNICODE_STRING *
0x18005a714  mov     [rax], edi
0x18005a716  mov     rcx, r14; struct _UNICODE_STRING *
0x18005a719  call    ?DuplicateUnicodeString2@@YAJPEAU_UNICODE_STRING@@0@Z; DuplicateUnicodeString2(_UNICODE_STRING *,_UNICODE_STRING *)
0x18005a71e  mov     edi, eax
0x18005a720  test    eax, eax
0x18005a722  jz      short loc_18005A758
0x18005a724  lea     rcx, aOnecoreDsExtCl_4; "onecore\\ds\\ext\\cloudap\\dll\\credapi"...
0x18005a72b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005a730  mov     r9, rax
0x18005a733  lea     r12, Class
0x18005a73a  mov     [rsp+0F0h+var_C0], r12
0x18005a73f  lea     rax, aDuplicateunico; "DuplicateUnicodeString2"
0x18005a746  mov     [rsp+0F0h+NewTokenHandle], rax
0x18005a74b  mov     r8d, edi
0x18005a74e  mov     dword ptr [rsp+0F0h+TokenType], 0D6h
0x18005a756  jmp     short loc_18005A6FD
0x18005a758  lea     rcx, [rbp+4Fh+ThreadInformation]; void **
0x18005a75c  call    ?ImpersonateClient@@YAJPEAPEAX@Z; ImpersonateClient(void * *)
0x18005a761  mov     edi, eax
0x18005a763  lea     r14, aOnecoreDsExtCl_4; "onecore\\ds\\ext\\cloudap\\dll\\credapi"...
0x18005a76a  xor     eax, eax
0x18005a76c  lea     r12, Class
0x18005a773  lea     r15, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005a77a  test    edi, edi
0x18005a77c  js      loc_18005A85F
0x18005a782  mov     al, 1
0x18005a784  lea     r9, [rbp+4Fh+TokenHandle]; TokenHandle
0x18005a788  mov     r8b, al; OpenAsSelf
0x18005a78b  mov     [rbp+4Fh+var_B0], al
0x18005a78e  mov     edx, 2000000h; DesiredAccess
0x18005a793  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18005a79a  call    cs:__imp_NtOpenThreadToken
0x18005a7a0  mov     edi, eax
0x18005a7a2  xor     eax, eax
0x18005a7a4  test    edi, edi
0x18005a7a6  jz      short loc_18005A7DE
0x18005a7a8  mov     rcx, r14; char *
0x18005a7ab  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005a7b0  mov     [rsp+0F0h+var_C0], r12
0x18005a7b5  mov     r9, rax
0x18005a7b8  lea     rax, aNtopenthreadto; "NtOpenThreadToken"
0x18005a7bf  mov     [rsp+0F0h+NewTokenHandle], rax
0x18005a7c4  mov     dword ptr [rsp+0F0h+TokenType], 0E2h
0x18005a7cc  mov     r8d, edi
0x18005a7cf  mov     rdx, r15
0x18005a7d2  xor     ecx, ecx
0x18005a7d4  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005a7d9  jmp     loc_18005AC6F
0x18005a7de  mov     ecx, 2
0x18005a7e3  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rax
0x18005a7e7  mov     [rbp+4Fh+ObjectAttributes.Attributes], eax
0x18005a7ea  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18005a7ee  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x18005a7f2  xor     r9d, r9d; EffectiveOnly
0x18005a7f5  mov     [rbp+4Fh+ObjectAttributes.SecurityDescriptor], rax
0x18005a7f9  mov     word ptr [rbp+4Fh+var_48], ax
0x18005a7fd  lea     edx, [rcx+2Ah]; DesiredAccess
0x18005a800  lea     rax, [rbp+4Fh+var_50]
0x18005a804  mov     dword ptr [rbp+4Fh+var_50+4], ecx
0x18005a807  mov     [rbp+4Fh+ObjectAttributes.SecurityQualityOfService], rax
0x18005a80b  lea     rax, [r13+28h]
0x18005a80f  mov     [rsp+0F0h+NewTokenHandle], rax; NewTokenHandle
0x18005a814  mov     dword ptr [rsp+0F0h+TokenType], ecx; TokenType
0x18005a818  mov     rcx, [rbp+4Fh+TokenHandle]; ExistingTokenHandle
0x18005a81c  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18005a823  mov     dword ptr [rbp+4Fh+var_50], 0Ch
0x18005a82a  call    cs:__imp_NtDuplicateToken
0x18005a830  mov     edi, eax
0x18005a832  test    eax, eax
0x18005a834  jz      short loc_18005A899
0x18005a836  mov     rcx, r14; char *
0x18005a839  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005a83e  mov     [rsp+0F0h+var_C0], r12
0x18005a843  mov     r9, rax
0x18005a846  lea     rax, aNtduplicatetok; "NtDuplicateToken"
0x18005a84d  mov     [rsp+0F0h+NewTokenHandle], rax
0x18005a852  mov     dword ptr [rsp+0F0h+TokenType], 0F3h
0x18005a85a  jmp     loc_18005A7CC
0x18005a85f  mov     rcx, r14; char *
0x18005a862  mov     [rbp+4Fh+var_B0], al
0x18005a865  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005a86a  mov     r9, rax
0x18005a86d  mov     [rsp+0F0h+var_C0], r12
0x18005a872  lea     rax, aImpersonatecli; "ImpersonateClient"
0x18005a879  mov     r8d, edi
0x18005a87c  mov     [rsp+0F0h+NewTokenHandle], rax
0x18005a881  mov     rdx, r15
0x18005a884  xor     ecx, ecx
0x18005a886  mov     dword ptr [rsp+0F0h+TokenType], 0F7h
0x18005a88e  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005a893  xor     eax, eax
0x18005a895  mov     [r13+28h], rax
0x18005a899  test    rsi, rsi
0x18005a89c  jz      loc_18005ABA5
0x18005a8a2  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005a8a9  mov     ecx, 0E0h
0x18005a8ae  mov     rax, [rax+28h]
0x18005a8b2  test    ebx, ebx
0x18005a8b4  jnz     short loc_18005A8BB
0x18005a8b6  mov     ecx, 0C8h
0x18005a8bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a8c0  mov     [r13+18h], rax
0x18005a8c4  mov     rbx, rax
0x18005a8c7  test    rax, rax
0x18005a8ca  jnz     short loc_18005A908
0x18005a8cc  mov     r8d, 0C0000017h
0x18005a8d2  mov     rcx, r14; char *
0x18005a8d5  mov     edi, r8d
0x18005a8d8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005a8dd  mov     [rsp+0F0h+var_C0], r12
0x18005a8e2  mov     r9, rax
0x18005a8e5  lea     rax, aAllocatelsahea; "AllocateLsaHeap(SECPKG_PRIMARY_CRED)"
0x18005a8ec  mov     [rsp+0F0h+NewTokenHandle], rax
0x18005a8f1  mov     dword ptr [rsp+0F0h+TokenType], 10Bh
0x18005a8f9  mov     rdx, r15
0x18005a8fc  xor     ecx, ecx
0x18005a8fe  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005a903  jmp     loc_18005AC69
0x18005a908  mov     rax, [rsi]
0x18005a90b  lea     rdx, [rbx+8]; struct _UNICODE_STRING *
0x18005a90f  mov     [rbx], rax
0x18005a912  lea     rcx, [rsi+8]; struct _UNICODE_STRING *
0x18005a916  mov     eax, [rsi+50h]
0x18005a919  mov     [rbx+50h], eax
0x18005a91c  call    ?DuplicateUnicodeString2@@YAJPEAU_UNICODE_STRING@@0@Z; DuplicateUnicodeString2(_UNICODE_STRING *,_UNICODE_STRING *)
0x18005a921  mov     edi, eax
0x18005a923  test    eax, eax
0x18005a925  jz      short loc_18005A950
0x18005a927  mov     rcx, r14; char *
0x18005a92a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005a92f  mov     [rsp+0F0h+var_C0], r12
0x18005a934  mov     r9, rax
0x18005a937  lea     rax, aDuplicateunico_1; "DuplicateUnicodeString2(DownlevelName)"
0x18005a93e  mov     [rsp+0F0h+NewTokenHandle], rax
0x18005a943  mov     dword ptr [rsp+0F0h+TokenType], 115h
0x18005a94b  mov     r8d, edi
0x18005a94e  jmp     short loc_18005A8F9
0x18005a950  lea     rdx, [rbx+18h]; struct _UNICODE_STRING *
0x18005a954  lea     rcx, [rsi+18h]; struct _UNICODE_STRING *
0x18005a958  call    ?DuplicateUnicodeString2@@YAJPEAU_UNICODE_STRING@@0@Z; DuplicateUnicodeString2(_UNICODE_STRING *,_UNICODE_STRING *)
0x18005a95d  mov     edi, eax
0x18005a95f  test    eax, eax
0x18005a961  jz      short loc_18005A989
0x18005a963  mov     rcx, r14; char *
0x18005a966  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005a96b  mov     [rsp+0F0h+var_C0], r12
0x18005a970  mov     r9, rax
0x18005a973  lea     rax, aDuplicateunico_3; "DuplicateUnicodeString2(DomainName)"
0x18005a97a  mov     [rsp+0F0h+NewTokenHandle], rax
0x18005a97f  mov     dword ptr [rsp+0F0h+TokenType], 119h
0x18005a987  jmp     short loc_18005A94B
0x18005a989  lea     rdx, [rbx+28h]; struct _UNICODE_STRING *
0x18005a98d  lea     rcx, [rsi+28h]; struct _UNICODE_STRING *
0x18005a991  call    ?DuplicateUnicodeString2@@YAJPEAU_UNICODE_STRING@@0@Z; DuplicateUnicodeString2(_UNICODE_STRING *,_UNICODE_STRING *)
0x18005a996  mov     edi, eax
0x18005a998  test    eax, eax
0x18005a99a  jz      short loc_18005A9C2
0x18005a99c  mov     rcx, r14; char *
0x18005a99f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005a9a4  mov     [rsp+0F0h+var_C0], r12
0x18005a9a9  mov     r9, rax
0x18005a9ac  lea     rax, aDuplicateunico_0; "DuplicateUnicodeString2(Password)"
0x18005a9b3  mov     [rsp+0F0h+NewTokenHandle], rax
0x18005a9b8  mov     dword ptr [rsp+0F0h+TokenType], 11Dh
0x18005a9c0  jmp     short loc_18005A94B
0x18005a9c2  lea     rdx, [rbx+38h]; struct _UNICODE_STRING *
0x18005a9c6  lea     rcx, [rsi+38h]; struct _UNICODE_STRING *
0x18005a9ca  call    ?DuplicateUnicodeString2@@YAJPEAU_UNICODE_STRING@@0@Z; DuplicateUnicodeString2(_UNICODE_STRING *,_UNICODE_STRING *)
0x18005a9cf  mov     edi, eax
0x18005a9d1  test    eax, eax
0x18005a9d3  jz      short loc_18005A9FE
0x18005a9d5  mov     rcx, r14; char *
0x18005a9d8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005a9dd  mov     [rsp+0F0h+var_C0], r12
0x18005a9e2  mov     r9, rax
0x18005a9e5  lea     rax, aDuplicateunico_4; "DuplicateUnicodeString2(OldPassword)"
0x18005a9ec  mov     [rsp+0F0h+NewTokenHandle], rax
0x18005a9f1  mov     dword ptr [rsp+0F0h+TokenType], 121h
0x18005a9f9  jmp     loc_18005A94B
0x18005a9fe  lea     rdx, [rbx+58h]; struct _UNICODE_STRING *
0x18005aa02  lea     rcx, [rsi+58h]; struct _UNICODE_STRING *
0x18005aa06  call    ?DuplicateUnicodeString2@@YAJPEAU_UNICODE_STRING@@0@Z; DuplicateUnicodeString2(_UNICODE_STRING *,_UNICODE_STRING *)
0x18005aa0b  mov     edi, eax
0x18005aa0d  test    eax, eax
0x18005aa0f  jz      short loc_18005AA3A
0x18005aa11  mov     rcx, r14; char *
0x18005aa14  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005aa19  mov     [rsp+0F0h+var_C0], r12
0x18005aa1e  mov     r9, rax
0x18005aa21  lea     rax, aDuplicateunico_2; "DuplicateUnicodeString2(DnsDomainName)"
0x18005aa28  mov     [rsp+0F0h+NewTokenHandle], rax
0x18005aa2d  mov     dword ptr [rsp+0F0h+TokenType], 125h
0x18005aa35  jmp     loc_18005A94B
0x18005aa3a  lea     rdx, [rbx+68h]; struct _UNICODE_STRING *
0x18005aa3e  lea     rcx, [rsi+68h]; struct _UNICODE_STRING *
0x18005aa42  call    ?DuplicateUnicodeString2@@YAJPEAU_UNICODE_STRING@@0@Z; DuplicateUnicodeString2(_UNICODE_STRING *,_UNICODE_STRING *)
0x18005aa47  mov     edi, eax
0x18005aa49  test    eax, eax
0x18005aa4b  jz      short loc_18005AA76
0x18005aa4d  mov     rcx, r14; char *
0x18005aa50  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005aa55  mov     [rsp+0F0h+var_C0], r12
0x18005aa5a  mov     r9, rax
0x18005aa5d  lea     rax, aDuplicateunico_9; "DuplicateUnicodeString2(Upn)"
0x18005aa64  mov     [rsp+0F0h+NewTokenHandle], rax
0x18005aa69  mov     dword ptr [rsp+0F0h+TokenType], 129h
0x18005aa71  jmp     loc_18005A94B
0x18005aa76  lea     rdx, [rbx+78h]; struct _UNICODE_STRING *
0x18005aa7a  lea     rcx, [rsi+78h]; struct _UNICODE_STRING *
0x18005aa7e  call    ?DuplicateUnicodeString2@@YAJPEAU_UNICODE_STRING@@0@Z; DuplicateUnicodeString2(_UNICODE_STRING *,_UNICODE_STRING *)
0x18005aa83  mov     edi, eax
0x18005aa85  test    eax, eax
0x18005aa87  jz      short loc_18005AAB2
0x18005aa89  mov     rcx, r14; char *
0x18005aa8c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005aa91  mov     [rsp+0F0h+var_C0], r12
0x18005aa96  mov     r9, rax
0x18005aa99  lea     rax, aDuplicateunico_6; "DuplicateUnicodeString2(LogonServer)"
0x18005aaa0  mov     [rsp+0F0h+NewTokenHandle], rax
0x18005aaa5  mov     dword ptr [rsp+0F0h+TokenType], 12Dh
0x18005aaad  jmp     loc_18005A94B
0x18005aab2  movzx   eax, word ptr [rsi+88h]
0x18005aab9  mov     [rbx+8Ah], ax
0x18005aac0  mov     [rbx+88h], ax
0x18005aac7  movzx   eax, word ptr [rsi+88h]
0x18005aace  test    ax, ax
0x18005aad1  jz      short loc_18005AB3A
0x18005aad3  mov     ecx, eax
0x18005aad5  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005aadc  mov     rax, [rax+28h]
0x18005aae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aae5  mov     [rbx+90h], rax
0x18005aaec  test    rax, rax
0x18005aaef  jnz     short loc_18005AB23
0x18005aaf1  mov     r8d, 0C0000017h
0x18005aaf7  mov     rcx, r14; char *
0x18005aafa  mov     edi, r8d
0x18005aafd  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005ab02  mov     [rsp+0F0h+var_C0], r12
0x18005ab07  mov     r9, rax
0x18005ab0a  lea     rax, aAllocatelsahea_4; "AllocateLsaHeap(Spare1)"
  ... truncated ...
```
