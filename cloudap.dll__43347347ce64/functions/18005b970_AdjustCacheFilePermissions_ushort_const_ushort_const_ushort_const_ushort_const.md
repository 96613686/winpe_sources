# AdjustCacheFilePermissions(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18005b970`
- end: `0x18005be82`
- name: `?AdjustCacheFilePermissions@@YAJPEBG000@Z`
- size: `1298`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000ed04`
- `0x18000fb70`

## callees

- `0x180007690`
- `0x180007fc0`
- `0x18000a600`
- `0x180042410`
- `0x18005b908`
- `0x18005b970`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005be03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005be03`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18005bc4c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18005bc4c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18005bb14`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18005bb14`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18005bcf6`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18005bcf6`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x18005bbd8`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x18005bbd8`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18005bb65`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18005bb65`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18005bd79`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18005bd79`
- `ntdll!RtlEqualSid` at `0x18005bc9b`
- `ntdll!RtlEqualSid` at `0x18005bc9b`

## string_xrefs

- `0x18005ba2c`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005bab9`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005bb72`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005bbe5`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005bd03`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005bd86`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005be0c`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005bb8d`: `GetNamedSecurityInfoW`
- `0x18005bc00`: `GetExplicitEntriesFromAclW`
- `0x18005be27`: `CreateWellKnownSid`
- `0x18005bd1e`: `SetEntriesInAclW`
- `0x18005bda1`: `SetNamedSecurityInfoW`
- `0x18005ba90`: `Cache`

## pseudocode

```c
__int64 __fastcall AdjustCacheFilePermissions(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rax
  unsigned int v10; // ebx
  WCHAR *v11; // rax
  const char *v12; // rax
  unsigned int v13; // ebx
  const char *v15; // rax
  const char *v16; // rax
  __int64 v17; // r8
  const char *v18; // rax
  __int64 v19; // r8
  char v20; // si
  char v21; // r14
  ULONG v22; // edi
  const char *v23; // rax
  __int64 v24; // r8
  const char *v25; // rax
  __int64 v26; // r8
  const char *v27; // rax
  __int64 v28; // r8
  PSID *ppsidGroup; // [rsp+20h] [rbp-E0h]
  PSID *ppsidGroupa; // [rsp+20h] [rbp-E0h]
  PSID *ppsidGroupb; // [rsp+20h] [rbp-E0h]
  ULONG pcCountOfExplicitEntries; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR pszPath; // [rsp+48h] [rbp-B8h] BYREF
  PEXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v35[4]; // [rsp+58h] [rbp-A8h] BYREF
  char v36; // [rsp+78h] [rbp-88h]
  DWORD cbSid; // [rsp+80h] [rbp-80h] BYREF
  PACL NewAcl; // [rsp+88h] [rbp-78h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+90h] [rbp-70h] BYREF
  PACL pacl; // [rsp+98h] [rbp-68h] BYREF
  struct _EXPLICIT_ACCESS_W v41; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pSid[80]; // [rsp+D0h] [rbp-30h] BYREF

  pszPath = 0;
  ppSecurityDescriptor = 0;
  pListOfExplicitEntries = 0;
  NewAcl = 0;
  v35[0] = &pszPath;
  v35[1] = &ppSecurityDescriptor;
  v35[2] = &pListOfExplicitEntries;
  v35[3] = &NewAcl;
  v36 = 1;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  v9 = -1;
  do
    ++v9;
  while ( a1[v9] );
  do
    ++v7;
  while ( a4[v7] );
  v10 = v7 + 9 + v8 + v9;
  v11 = (WCHAR *)((__int64 (__fastcall *)(_QWORD, __int64, const unsigned __int16 *))g_pLsaFunctionTable->AllocateLsaHeap)(
                   2 * v10,
                   v8,
                   a3);
  pszPath = v11;
  if ( !v11 )
  {
    v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    v13 = -1073741801;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v12, 2264, "AllocateLsaHeap", &Class);
    v36 = 0;
    lambda_b0d1934d87745b76ed827eac1a7ef93b_::operator()(v35);
    return v13;
  }
  v13 = RtlStringCchPrintfW(v11, v10, L"%ws\\%ws\\%ws\\%ws", a1, a2, L"Cache", a4);
  if ( (v13 & 0x80000000) != 0 )
  {
    v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    LODWORD(ppsidGroup) = 2279;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v13, v15, ppsidGroup, "RtlStringCchPrintfW", &Class);
    v36 = 0;
    lambda_b0d1934d87745b76ed827eac1a7ef93b_::operator()(v35);
    return v13;
  }
  if ( !PathFileExistsW(pszPath) )
  {
    v36 = 0;
    lambda_b0d1934d87745b76ed827eac1a7ef93b_::operator()(v35);
    return 0;
  }
  pacl = 0;
  if ( GetNamedSecurityInfoW(pszPath, SE_FILE_OBJECT, 4u, 0, 0, &pacl, 0, &ppSecurityDescriptor) )
  {
    v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    LODWORD(ppsidGroupa) = 2302;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v17, v16, ppsidGroupa, "GetNamedSecurityInfoW", &Class);
    v36 = 0;
    lambda_b0d1934d87745b76ed827eac1a7ef93b_::operator()(v35);
    return 3221225701LL;
  }
  pcCountOfExplicitEntries = 0;
  if ( GetExplicitEntriesFromAclW(pacl, &pcCountOfExplicitEntries, &pListOfExplicitEntries) )
  {
    v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    LODWORD(ppsidGroupa) = 2311;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v19, v18, ppsidGroupa, "GetExplicitEntriesFromAclW", &Class);
    v36 = 0;
    lambda_b0d1934d87745b76ed827eac1a7ef93b_::operator()(v35);
    return 3221225701LL;
  }
  cbSid = 68;
  if ( !CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
  {
    GetLastError();
    v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    LODWORD(ppsidGroupa) = 2322;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v28, v27, ppsidGroupa, "CreateWellKnownSid", &Class);
    v36 = 0;
    lambda_b0d1934d87745b76ed827eac1a7ef93b_::operator()(v35);
    return 3221225701LL;
  }
  v20 = 0;
  v21 = 0;
  memset(&v41, 0, sizeof(v41));
  v22 = 0;
  if ( !pcCountOfExplicitEntries )
    goto LABEL_31;
  do
  {
    if ( pListOfExplicitEntries[v22].Trustee.TrusteeForm
      || !RtlEqualSid(pListOfExplicitEntries[v22].Trustee.ptstrName, pSid) )
    {
      v20 = 1;
      if ( !v21 )
        goto LABEL_25;
    }
    else
    {
      v41 = pListOfExplicitEntries[v22];
      v21 = 1;
    }
    if ( v20 )
      goto LABEL_27;
LABEL_25:
    ++v22;
  }
  while ( v22 < pcCountOfExplicitEntries );
  if ( !v20 )
    goto LABEL_31;
LABEL_27:
  if ( SetEntriesInAclW(1u, &v41, 0, &NewAcl) )
  {
    v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    LODWORD(ppsidGroupa) = 2358;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v24, v23, ppsidGroupa, "SetEntriesInAclW", &Class);
    v36 = 0;
    lambda_b0d1934d87745b76ed827eac1a7ef93b_::operator()(v35);
    return 3221225701LL;
  }
  if ( SetNamedSecurityInfoW((LPWSTR)pszPath, SE_FILE_OBJECT, 4u, 0, 0, NewAcl, 0) )
  {
    v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    LODWORD(ppsidGroupb) = 2373;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v26, v25, ppsidGroupb, "SetNamedSecurityInfoW", &Class);
    v36 = 0;
    lambda_b0d1934d87745b76ed827eac1a7ef93b_::operator()(v35);
    return 3221225701LL;
  }
LABEL_31:
  v36 = 0;
  lambda_b0d1934d87745b76ed827eac1a7ef93b_::operator()(v35);
  return 0;
}

```

## disassembly

```asm
0x18005b970  mov     [rsp-8+arg_10], rbx
0x18005b975  push    rbp
0x18005b976  push    rsi
0x18005b977  push    rdi
0x18005b978  push    r14
0x18005b97a  push    r15
0x18005b97c  lea     rbp, [rsp-30h]
0x18005b981  sub     rsp, 130h
0x18005b988  mov     rax, cs:__security_cookie
0x18005b98f  xor     rax, rsp
0x18005b992  mov     [rbp+50h+var_30], rax
0x18005b996  mov     r14, r9
0x18005b999  mov     rdi, rdx
0x18005b99c  mov     rsi, rcx
0x18005b99f  xor     r15d, r15d
0x18005b9a2  mov     [rsp+150h+pszPath], r15
0x18005b9a7  mov     [rbp+50h+var_C0], r15
0x18005b9ab  mov     [rsp+150h+pListOfExplicitEntries], r15
0x18005b9b0  mov     [rbp+50h+NewAcl], r15
0x18005b9b4  lea     rax, [rsp+150h+pszPath]
0x18005b9b9  mov     [rsp+150h+var_F8], rax
0x18005b9be  lea     rax, [rbp+50h+var_C0]
0x18005b9c2  mov     [rsp+150h+var_F0], rax
0x18005b9c7  lea     rax, [rsp+150h+pListOfExplicitEntries]
0x18005b9cc  mov     [rsp+150h+var_E8], rax
0x18005b9d1  lea     rax, [rbp+50h+NewAcl]
0x18005b9d5  mov     [rsp+150h+var_E0], rax
0x18005b9da  mov     [rsp+150h+var_D8], 1
0x18005b9df  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18005b9e3  mov     rdx, rcx
0x18005b9e6  inc     rdx
0x18005b9e9  cmp     [rdi+rdx*2], r15w
0x18005b9ee  jnz     short loc_18005B9E6
0x18005b9f0  mov     rax, rcx
0x18005b9f3  inc     rax
0x18005b9f6  cmp     [rsi+rax*2], r15w
0x18005b9fb  jnz     short loc_18005B9F3
0x18005b9fd  inc     rcx
0x18005ba00  cmp     [r9+rcx*2], r15w
0x18005ba05  jnz     short loc_18005B9FD
0x18005ba07  lea     ebx, [rdx+rax]
0x18005ba0a  add     ecx, 9
0x18005ba0d  add     ebx, ecx
0x18005ba0f  lea     ecx, [rbx+rbx]
0x18005ba12  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005ba19  mov     rax, [rax+28h]
0x18005ba1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ba22  mov     [rsp+150h+pszPath], rax
0x18005ba27  test    rax, rax
0x18005ba2a  jnz     short loc_18005BA89
0x18005ba2c  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005ba33  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005ba38  mov     r9, rax
0x18005ba3b  lea     rax, Class
0x18005ba42  mov     [rsp+150h+ppSacl], rax
0x18005ba47  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x18005ba4e  mov     [rsp+150h+ppDacl], rax
0x18005ba53  mov     dword ptr [rsp+150h+ppsidGroup], 8D8h
0x18005ba5b  mov     ebx, 0C0000017h
0x18005ba60  mov     r8d, ebx
0x18005ba63  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005ba6a  xor     ecx, ecx
0x18005ba6c  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005ba71  nop
0x18005ba72  mov     [rsp+150h+var_D8], r15b
0x18005ba77  lea     rcx, [rsp+150h+var_F8]
0x18005ba7c  call    _lambda_b0d1934d87745b76ed827eac1a7ef93b___operator__
0x18005ba81  nop
0x18005ba82  mov     eax, ebx
0x18005ba84  jmp     loc_18005BE5F
0x18005ba89  mov     edx, ebx; unsigned __int64
0x18005ba8b  mov     [rsp+150h+ppSacl], r14
0x18005ba90  lea     rcx, aCache; "Cache"
0x18005ba97  mov     [rsp+150h+ppDacl], rcx
0x18005ba9c  mov     [rsp+150h+ppsidGroup], rdi
0x18005baa1  mov     r9, rsi
0x18005baa4  lea     r8, aWsWsWsWs; "%ws\\%ws\\%ws\\%ws"
0x18005baab  mov     rcx, rax; unsigned __int16 *
0x18005baae  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005bab3  mov     ebx, eax
0x18005bab5  test    eax, eax
0x18005bab7  jns     short loc_18005BB0F
0x18005bab9  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005bac0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005bac5  mov     r9, rax
0x18005bac8  lea     rax, Class
0x18005bacf  mov     [rsp+150h+ppSacl], rax
0x18005bad4  lea     rax, aRtlstringcchpr; "RtlStringCchPrintfW"
0x18005badb  mov     [rsp+150h+ppDacl], rax
0x18005bae0  mov     dword ptr [rsp+150h+ppsidGroup], 8E7h
0x18005bae8  mov     r8d, ebx
0x18005baeb  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005baf2  xor     ecx, ecx
0x18005baf4  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005baf9  nop
0x18005bafa  mov     [rsp+150h+var_D8], r15b
0x18005baff  lea     rcx, [rsp+150h+var_F8]
0x18005bb04  call    _lambda_b0d1934d87745b76ed827eac1a7ef93b___operator__
0x18005bb09  nop
0x18005bb0a  jmp     loc_18005BA82
0x18005bb0f  mov     rcx, [rsp+150h+pszPath]; pszPath
0x18005bb14  call    cs:__imp_PathFileExistsW
0x18005bb1a  test    eax, eax
0x18005bb1c  jnz     short loc_18005BB35
0x18005bb1e  mov     [rsp+150h+var_D8], r15b
0x18005bb23  lea     rcx, [rsp+150h+var_F8]
0x18005bb28  call    _lambda_b0d1934d87745b76ed827eac1a7ef93b___operator__
0x18005bb2d  nop
0x18005bb2e  xor     eax, eax
0x18005bb30  jmp     loc_18005BE5F
0x18005bb35  mov     [rbp+50h+pacl], r15
0x18005bb39  lea     rax, [rbp+50h+var_C0]
0x18005bb3d  mov     [rsp+150h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18005bb42  mov     [rsp+150h+ppSacl], r15; ppSacl
0x18005bb47  lea     rax, [rbp+50h+pacl]
0x18005bb4b  mov     [rsp+150h+ppDacl], rax; ppDacl
0x18005bb50  mov     [rsp+150h+ppsidGroup], r15; ppsidGroup
0x18005bb55  xor     r9d, r9d; ppsidOwner
0x18005bb58  lea     edx, [r9+1]; ObjectType
0x18005bb5c  lea     r8d, [r9+4]; SecurityInfo
0x18005bb60  mov     rcx, [rsp+150h+pszPath]; pObjectName
0x18005bb65  call    cs:__imp_GetNamedSecurityInfoW
0x18005bb6b  mov     r8d, eax
0x18005bb6e  test    eax, eax
0x18005bb70  jz      short loc_18005BBC5
0x18005bb72  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005bb79  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005bb7e  mov     r9, rax
0x18005bb81  lea     rax, Class
0x18005bb88  mov     [rsp+150h+ppSacl], rax
0x18005bb8d  lea     rax, aGetnamedsecuri; "GetNamedSecurityInfoW"
0x18005bb94  mov     [rsp+150h+ppDacl], rax
0x18005bb99  mov     dword ptr [rsp+150h+ppsidGroup], 8FEh
0x18005bba1  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005bba8  xor     ecx, ecx
0x18005bbaa  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005bbaf  nop
0x18005bbb0  mov     [rsp+150h+var_D8], r15b
0x18005bbb5  lea     rcx, [rsp+150h+var_F8]
0x18005bbba  call    _lambda_b0d1934d87745b76ed827eac1a7ef93b___operator__
0x18005bbbf  nop
0x18005bbc0  jmp     loc_18005BE5A
0x18005bbc5  mov     [rsp+150h+pcCountOfExplicitEntries], r15d
0x18005bbca  lea     r8, [rsp+150h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18005bbcf  lea     rdx, [rsp+150h+pcCountOfExplicitEntries]; pcCountOfExplicitEntries
0x18005bbd4  mov     rcx, [rbp+50h+pacl]; pacl
0x18005bbd8  call    cs:__imp_GetExplicitEntriesFromAclW
0x18005bbde  mov     r8d, eax
0x18005bbe1  test    eax, eax
0x18005bbe3  jz      short loc_18005BC38
0x18005bbe5  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005bbec  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005bbf1  mov     r9, rax
0x18005bbf4  lea     rax, Class
0x18005bbfb  mov     [rsp+150h+ppSacl], rax
0x18005bc00  lea     rax, aGetexplicitent; "GetExplicitEntriesFromAclW"
0x18005bc07  mov     [rsp+150h+ppDacl], rax
0x18005bc0c  mov     dword ptr [rsp+150h+ppsidGroup], 907h
0x18005bc14  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005bc1b  xor     ecx, ecx
0x18005bc1d  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005bc22  nop
0x18005bc23  mov     [rsp+150h+var_D8], r15b
0x18005bc28  lea     rcx, [rsp+150h+var_F8]
0x18005bc2d  call    _lambda_b0d1934d87745b76ed827eac1a7ef93b___operator__
0x18005bc32  nop
0x18005bc33  jmp     loc_18005BE5A
0x18005bc38  mov     [rbp+50h+cbSid], 44h ; 'D'
0x18005bc3f  lea     r9, [rbp+50h+cbSid]; cbSid
0x18005bc43  lea     r8, [rbp+50h+pSid]; pSid
0x18005bc47  xor     edx, edx; DomainSid
0x18005bc49  lea     ecx, [rdx+16h]; WellKnownSidType
0x18005bc4c  call    cs:__imp_CreateWellKnownSid
0x18005bc52  test    eax, eax
0x18005bc54  jz      loc_18005BE03
0x18005bc5a  mov     sil, r15b
0x18005bc5d  mov     r14b, r15b
0x18005bc60  xorps   xmm0, xmm0
0x18005bc63  movups  xmmword ptr [rbp+50h+var_B0.grfAccessPermissions], xmm0
0x18005bc67  movups  xmmword ptr [rbp+50h+var_B0.Trustee.pMultipleTrustee], xmm0
0x18005bc6b  movups  xmmword ptr [rbp+50h+var_B0.Trustee.TrusteeType], xmm0
0x18005bc6f  mov     edi, r15d
0x18005bc72  cmp     [rsp+150h+pcCountOfExplicitEntries], r15d
0x18005bc77  jbe     loc_18005BDEE
0x18005bc7d  mov     eax, edi
0x18005bc7f  lea     rbx, [rax+rax*2]
0x18005bc83  add     rbx, rbx
0x18005bc86  mov     rcx, [rsp+150h+pListOfExplicitEntries]
0x18005bc8b  cmp     [rcx+rbx*8+1Ch], r15d
0x18005bc90  jnz     short loc_18005BCC9
0x18005bc92  lea     rdx, [rbp+50h+pSid]; Sid2
0x18005bc96  mov     rcx, [rcx+rbx*8+28h]; Sid1
0x18005bc9b  call    cs:__imp_RtlEqualSid
0x18005bca1  test    al, al
0x18005bca3  jz      short loc_18005BCC9
0x18005bca5  mov     rax, [rsp+150h+pListOfExplicitEntries]
0x18005bcaa  movups  xmm0, xmmword ptr [rax+rbx*8]
0x18005bcae  movups  xmmword ptr [rbp+50h+var_B0.grfAccessPermissions], xmm0
0x18005bcb2  movups  xmm1, xmmword ptr [rax+rbx*8+10h]
0x18005bcb7  movups  xmmword ptr [rbp+50h+var_B0.Trustee.pMultipleTrustee], xmm1
0x18005bcbb  movups  xmm0, xmmword ptr [rax+rbx*8+20h]
0x18005bcc0  movups  xmmword ptr [rbp+50h+var_B0.Trustee.TrusteeType], xmm0
0x18005bcc4  mov     r14b, 1
0x18005bcc7  jmp     short loc_18005BCD1
0x18005bcc9  mov     sil, 1
0x18005bccc  test    r14b, r14b
0x18005bccf  jz      short loc_18005BCD6
0x18005bcd1  test    sil, sil
0x18005bcd4  jnz     short loc_18005BCE7
0x18005bcd6  inc     edi
0x18005bcd8  cmp     edi, [rsp+150h+pcCountOfExplicitEntries]
0x18005bcdc  jb      short loc_18005BC7D
0x18005bcde  test    sil, sil
0x18005bce1  jz      loc_18005BDEE
0x18005bce7  lea     r9, [rbp+50h+NewAcl]; NewAcl
0x18005bceb  xor     r8d, r8d; OldAcl
0x18005bcee  lea     rdx, [rbp+50h+var_B0]; pListOfExplicitEntries
0x18005bcf2  lea     ecx, [r8+1]; cCountOfExplicitEntries
0x18005bcf6  call    cs:__imp_SetEntriesInAclW
0x18005bcfc  mov     r8d, eax
0x18005bcff  test    eax, eax
0x18005bd01  jz      short loc_18005BD56
0x18005bd03  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005bd0a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005bd0f  mov     r9, rax
0x18005bd12  lea     rax, Class
0x18005bd19  mov     [rsp+150h+ppSacl], rax
0x18005bd1e  lea     rax, aSetentriesinac; "SetEntriesInAclW"
0x18005bd25  mov     [rsp+150h+ppDacl], rax
0x18005bd2a  mov     dword ptr [rsp+150h+ppsidGroup], 936h
0x18005bd32  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005bd39  xor     ecx, ecx
0x18005bd3b  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005bd40  nop
0x18005bd41  mov     [rsp+150h+var_D8], r15b
0x18005bd46  lea     rcx, [rsp+150h+var_F8]
0x18005bd4b  call    _lambda_b0d1934d87745b76ed827eac1a7ef93b___operator__
0x18005bd50  nop
0x18005bd51  jmp     loc_18005BE5A
0x18005bd56  mov     [rsp+150h+ppSacl], r15; pSacl
0x18005bd5b  mov     rax, [rbp+50h+NewAcl]
0x18005bd5f  mov     [rsp+150h+ppDacl], rax; pDacl
0x18005bd64  mov     [rsp+150h+ppsidGroup], r15; psidGroup
0x18005bd69  xor     r9d, r9d; psidOwner
0x18005bd6c  lea     edx, [r9+1]; ObjectType
0x18005bd70  lea     r8d, [r9+4]; SecurityInfo
0x18005bd74  mov     rcx, [rsp+150h+pszPath]; pObjectName
0x18005bd79  call    cs:__imp_SetNamedSecurityInfoW
0x18005bd7f  mov     r8d, eax
0x18005bd82  test    eax, eax
0x18005bd84  jz      short loc_18005BDD9
0x18005bd86  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005bd8d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005bd92  mov     r9, rax
0x18005bd95  lea     rax, Class
0x18005bd9c  mov     [rsp+150h+ppSacl], rax
0x18005bda1  lea     rax, aSetnamedsecuri; "SetNamedSecurityInfoW"
0x18005bda8  mov     [rsp+150h+ppDacl], rax
0x18005bdad  mov     dword ptr [rsp+150h+ppsidGroup], 945h
0x18005bdb5  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005bdbc  xor     ecx, ecx
0x18005bdbe  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005bdc3  nop
0x18005bdc4  mov     [rsp+150h+var_D8], r15b
0x18005bdc9  lea     rcx, [rsp+150h+var_F8]
0x18005bdce  call    _lambda_b0d1934d87745b76ed827eac1a7ef93b___operator__
0x18005bdd3  nop
0x18005bdd4  jmp     loc_18005BE5A
0x18005bdd9  mov     [rsp+150h+var_D8], r15b
0x18005bdde  lea     rcx, [rsp+150h+var_F8]
0x18005bde3  call    _lambda_b0d1934d87745b76ed827eac1a7ef93b___operator__
0x18005bde8  nop
0x18005bde9  jmp     loc_18005BB2E
0x18005bdee  mov     [rsp+150h+var_D8], r15b
0x18005bdf3  lea     rcx, [rsp+150h+var_F8]
0x18005bdf8  call    _lambda_b0d1934d87745b76ed827eac1a7ef93b___operator__
0x18005bdfd  nop
0x18005bdfe  jmp     loc_18005BB2E
0x18005be03  call    cs:__imp_GetLastError
0x18005be09  mov     r8d, eax
0x18005be0c  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005be13  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005be18  mov     r9, rax
0x18005be1b  lea     rax, Class
0x18005be22  mov     [rsp+150h+ppSacl], rax
0x18005be27  lea     rax, aCreatewellknow; "CreateWellKnownSid"
0x18005be2e  mov     [rsp+150h+ppDacl], rax
0x18005be33  mov     dword ptr [rsp+150h+ppsidGroup], 912h
0x18005be3b  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005be42  xor     ecx, ecx
0x18005be44  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005be49  nop
0x18005be4a  mov     [rsp+150h+var_D8], r15b
0x18005be4f  lea     rcx, [rsp+150h+var_F8]
0x18005be54  call    _lambda_b0d1934d87745b76ed827eac1a7ef93b___operator__
0x18005be59  nop
0x18005be5a  mov     eax, 0C00000E5h
0x18005be5f  mov     rcx, [rbp+50h+var_30]
0x18005be63  xor     rcx, rsp; StackCookie
0x18005be66  call    __security_check_cookie
  ... truncated ...
```
