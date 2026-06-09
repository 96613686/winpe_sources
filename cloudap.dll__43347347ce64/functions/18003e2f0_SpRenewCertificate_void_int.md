# SpRenewCertificate(void *,int)

- ea: `0x18003e2f0`
- end: `0x18003e6ed`
- name: `?SpRenewCertificate@@YAJPEAXH@Z`
- size: `1021`
- prototype: `__int64 __fastcall(void *, int)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180007ef0`
- `0x180007fc0`
- `0x180009bf0`
- `0x18000a600`
- `0x18000e7e0`
- `0x18000e900`
- `0x18000ee60`
- `0x180010320`
- `0x18003e2f0`
- `0x180042410`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18003e498`
- `ntdll!NtQueryInformationToken` at `0x18003e498`
- `ntdll!NtClose` at `0x18003e691`
- `ntdll!NtClose` at `0x18003e691`
- `ntdll!NtOpenThreadToken` at `0x18003e43d`
- `ntdll!NtOpenThreadToken` at `0x18003e43d`

## string_xrefs

- `0x18003e36f`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18003e3c7`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18003e449`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18003e4a4`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18003e4f0`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18003e56d`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18003e602`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18003e633`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18003e4bf`: `NtQueryInformationToken`
- `0x18003e464`: `NtOpenThreadToken`

## pseudocode

```c
__int64 __fastcall SpRenewCertificate(void *a1, unsigned int a2)
{
  struct _ApPluginPkg *v3; // rdi
  struct _LOGON_SESSION *v4; // r15
  __int64 (__fastcall *v5)(void *, struct _GUID *); // rax
  unsigned int v6; // ebx
  const char *v7; // r9
  const char *v8; // rax
  bool v9; // zf
  const char *v10; // rax
  const char *v11; // r9
  const char *v12; // r9
  const char *v13; // rax
  __int64 v14; // rsi
  void *v15; // rax
  const char *v16; // rax
  const char *v17; // r9
  const char *v18; // r9
  _BYTE *v19; // rcx
  __int64 v20; // rax
  PULONG ReturnLength; // [rsp+20h] [rbp-69h]
  ULONG v23; // [rsp+40h] [rbp-49h] BYREF
  struct _ApPluginPkg *v24; // [rsp+48h] [rbp-41h] BYREF
  struct _LOGON_SESSION *v25; // [rsp+50h] [rbp-39h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-31h] BYREF
  size_t Size[2]; // [rsp+60h] [rbp-29h] BYREF
  struct _GUID v28; // [rsp+70h] [rbp-19h] BYREF
  _OWORD TokenInformation[3]; // [rsp+80h] [rbp-9h] BYREF
  __int64 v30; // [rsp+B0h] [rbp+27h]

  v23 = 0;
  v30 = 0;
  TokenHandle = 0;
  v3 = 0;
  v4 = 0;
  v28 = 0;
  v24 = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v5 = (__int64 (__fastcall *)(void *, struct _GUID *))*((_QWORD *)g_pLsaIdProvHostFunctionTable + 10);
  v25 = 0;
  *(_OWORD *)Size = 0;
  v6 = v5(a1, &v28);
  if ( v6 )
  {
    v7 = "";
    while ( 1 )
    {
      v8 = v7--;
      v9 = *v7 == 92;
      if ( *v7 == 92 )
        break;
      if ( v7 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v9 = *v7 == 92;
        break;
      }
    }
    if ( v9 )
      v7 = v8;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v6, v7, 9128, "GetProvInfo", &Class);
  }
  else
  {
    v6 = RefPackage(&v28, &v24);
    if ( v6 )
    {
      v10 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v6, v10, 9131, "RefPackage", &Class);
      v3 = v24;
      goto LABEL_25;
    }
    v3 = v24;
    if ( *((_QWORD *)v24 + 39) )
    {
      if ( a2 )
      {
        v6 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
        if ( v6 )
        {
          v11 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v6, v11, 9142, "NtOpenThreadToken", &Class);
          goto LABEL_25;
        }
        v6 = NtQueryInformationToken(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &v23);
        if ( v6 )
        {
          v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(ReturnLength) = 9150;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v6, v12, ReturnLength, "NtQueryInformationToken", &Class);
          goto LABEL_25;
        }
        v6 = _AcquireLogonSession(1, (struct _LUID *)TokenInformation + 1, &v25);
        if ( v6 )
        {
          v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(ReturnLength) = 9155;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v6, v13, ReturnLength, "AcquireLogonSession", &Class);
          v4 = v25;
          goto LABEL_25;
        }
        v4 = v25;
        v14 = *((_QWORD *)v25 + 7);
        LockAndUnProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v14, 0);
        LODWORD(Size[0]) = *(_DWORD *)(v14 + 280);
        v15 = (void *)((__int64 (*)(void))g_pLsaFunctionTable->AllocateLsaHeap)();
        Size[1] = (size_t)v15;
        if ( !v15 )
        {
          v6 = -1073741801;
          v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(ReturnLength) = 9166;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v16, ReturnLength, "AllocateLsaHeap", &Class);
          UnlockAndProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v14);
          goto LABEL_25;
        }
        memcpy_0(v15, *(const void **)(v14 + 288), LODWORD(Size[0]));
        UnlockAndProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v14);
      }
      v6 = (*((__int64 (__fastcall **)(_QWORD, unsigned __int64, _QWORD))v3 + 39))(
             *((_QWORD *)v3 + 1),
             (unsigned __int64)Size & -(__int64)(a2 != 0),
             a2);
      if ( v6 )
      {
        v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(ReturnLength) = 9180;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v6, v17, ReturnLength, "RenewCertificate", &Class);
      }
    }
    else
    {
      v6 = -1073741822;
      v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225474LL, v18, 9185, "Not Implemented", &Class);
    }
  }
LABEL_25:
  ReleaseLogonSession(v4);
  DerefPackage(v3);
  if ( TokenHandle )
    NtClose(TokenHandle);
  v19 = (_BYTE *)Size[1];
  if ( Size[1] )
  {
    v20 = LODWORD(Size[0]);
    if ( LODWORD(Size[0]) )
    {
      do
      {
        *v19++ = 0;
        --v20;
      }
      while ( v20 );
    }
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  }
  return v6;
}

```

## disassembly

```asm
0x18003e2f0  mov     [rsp-8+arg_10], rbx
0x18003e2f5  push    rbp
0x18003e2f6  push    rsi
0x18003e2f7  push    rdi
0x18003e2f8  push    r14
0x18003e2fa  push    r15
0x18003e2fc  lea     rbp, [rsp-37h]
0x18003e301  sub     rsp, 0C0h
0x18003e308  mov     rax, cs:__security_cookie
0x18003e30f  xor     rax, rsp
0x18003e312  mov     [rbp+57h+var_28], rax
0x18003e316  xorps   xmm0, xmm0
0x18003e319  mov     [rbp+57h+var_A0], 0
0x18003e320  xor     eax, eax
0x18003e322  mov     r14d, edx
0x18003e325  mov     [rbp+57h+var_30], rax
0x18003e329  lea     rdx, [rbp+57h+var_70]
0x18003e32d  mov     [rbp+57h+TokenHandle], rax
0x18003e331  xor     edi, edi
0x18003e333  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x18003e33a  xor     r15d, r15d
0x18003e33d  movups  xmmword ptr [rbp+57h+var_70.Data1], xmm0
0x18003e341  mov     [rbp+57h+var_98], rdi
0x18003e345  movups  [rbp+57h+TokenInformation], xmm0
0x18003e349  mov     rax, [rax+50h]
0x18003e34d  movups  [rbp+57h+var_50], xmm0
0x18003e351  mov     [rbp+57h+var_90], r15
0x18003e355  movups  [rbp+57h+var_40], xmm0
0x18003e359  movups  xmmword ptr [rbp+57h+Size], xmm0
0x18003e35d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e362  mov     ebx, eax
0x18003e364  test    eax, eax
0x18003e366  jz      short loc_18003E3B4
0x18003e368  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x18003e36f  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18003e376  mov     rax, r9
0x18003e379  dec     r9
0x18003e37c  cmp     byte ptr [r9], 5Ch ; '\'
0x18003e380  jz      short loc_18003E38B
0x18003e382  cmp     r9, rcx
0x18003e385  ja      short loc_18003E376
0x18003e387  cmp     byte ptr [r9], 5Ch ; '\'
0x18003e38b  cmovz   r9, rax
0x18003e38f  lea     rax, Class
0x18003e396  mov     [rsp+0E0h+var_B0], rax
0x18003e39b  lea     rax, aGetprovinfo; "GetProvInfo"
0x18003e3a2  mov     [rsp+0E0h+var_B8], rax
0x18003e3a7  mov     dword ptr [rsp+0E0h+ReturnLength], 23A8h
0x18003e3af  jmp     loc_18003E667
0x18003e3b4  lea     rdx, [rbp+57h+var_98]; struct _ApPluginPkg **
0x18003e3b8  lea     rcx, [rbp+57h+var_70]; struct _GUID *
0x18003e3bc  call    ?RefPackage@@YAJPEAU_GUID@@PEAPEAU_ApPluginPkg@@@Z; RefPackage(_GUID *,_ApPluginPkg * *)
0x18003e3c1  mov     ebx, eax
0x18003e3c3  test    eax, eax
0x18003e3c5  jz      short loc_18003E410
0x18003e3c7  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18003e3ce  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003e3d3  mov     r9, rax
0x18003e3d6  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18003e3dd  lea     rax, Class
0x18003e3e4  mov     r8d, ebx
0x18003e3e7  mov     [rsp+0E0h+var_B0], rax
0x18003e3ec  xor     ecx, ecx
0x18003e3ee  lea     rax, aRefpackage; "RefPackage"
0x18003e3f5  mov     [rsp+0E0h+var_B8], rax
0x18003e3fa  mov     dword ptr [rsp+0E0h+ReturnLength], 23ABh
0x18003e402  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18003e407  mov     rdi, [rbp+57h+var_98]
0x18003e40b  jmp     loc_18003E678
0x18003e410  mov     rdi, [rbp+57h+var_98]
0x18003e414  cmp     [rdi+138h], r15
0x18003e41b  jz      loc_18003E633
0x18003e421  test    r14d, r14d
0x18003e424  jz      loc_18003E5DA
0x18003e42a  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18003e42e  mov     r8b, 1; OpenAsSelf
0x18003e431  mov     edx, 8; DesiredAccess
0x18003e436  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18003e43d  call    cs:__imp_NtOpenThreadToken
0x18003e443  mov     ebx, eax
0x18003e445  test    eax, eax
0x18003e447  jz      short loc_18003E47D
0x18003e449  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18003e450  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003e455  mov     r9, rax
0x18003e458  lea     rax, Class
0x18003e45f  mov     [rsp+0E0h+var_B0], rax
0x18003e464  lea     rax, aNtopenthreadto; "NtOpenThreadToken"
0x18003e46b  mov     [rsp+0E0h+var_B8], rax
0x18003e470  mov     dword ptr [rsp+0E0h+ReturnLength], 23B6h
0x18003e478  jmp     loc_18003E667
0x18003e47d  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18003e481  lea     rax, [rbp+57h+var_A0]
0x18003e485  mov     r9d, 38h ; '8'; TokenInformationLength
0x18003e48b  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x18003e490  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18003e494  lea     edx, [r9-2Eh]; TokenInformationClass
0x18003e498  call    cs:__imp_NtQueryInformationToken
0x18003e49e  mov     ebx, eax
0x18003e4a0  test    eax, eax
0x18003e4a2  jz      short loc_18003E4D8
0x18003e4a4  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18003e4ab  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003e4b0  mov     r9, rax
0x18003e4b3  lea     rax, Class
0x18003e4ba  mov     [rsp+0E0h+var_B0], rax
0x18003e4bf  lea     rax, aNtqueryinforma_1; "NtQueryInformationToken"
0x18003e4c6  mov     [rsp+0E0h+var_B8], rax
0x18003e4cb  mov     dword ptr [rsp+0E0h+ReturnLength], 23BEh
0x18003e4d3  jmp     loc_18003E667
0x18003e4d8  lea     r8, [rbp+57h+var_90]; struct _LOGON_SESSION **
0x18003e4dc  mov     ecx, 1; int
0x18003e4e1  lea     rdx, [rbp+57h+TokenInformation+8]; struct _LUID *
0x18003e4e5  call    ?_AcquireLogonSession@@YAJHPEAU_LUID@@PEAPEAU_LOGON_SESSION@@@Z; _AcquireLogonSession(int,_LUID *,_LOGON_SESSION * *)
0x18003e4ea  mov     ebx, eax
0x18003e4ec  test    eax, eax
0x18003e4ee  jz      short loc_18003E539
0x18003e4f0  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18003e4f7  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003e4fc  mov     r9, rax
0x18003e4ff  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18003e506  lea     rax, Class
0x18003e50d  mov     r8d, ebx
0x18003e510  mov     [rsp+0E0h+var_B0], rax
0x18003e515  xor     ecx, ecx
0x18003e517  lea     rax, aAcquirelogonse_0; "AcquireLogonSession"
0x18003e51e  mov     [rsp+0E0h+var_B8], rax
0x18003e523  mov     dword ptr [rsp+0E0h+ReturnLength], 23C3h
0x18003e52b  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18003e530  mov     r15, [rbp+57h+var_90]
0x18003e534  jmp     loc_18003E678
0x18003e539  mov     r15, [rbp+57h+var_90]
0x18003e53d  xor     edx, edx; bool
0x18003e53f  mov     rsi, [r15+38h]
0x18003e543  mov     rcx, rsi; struct _USER_CACHE_ENTRY *
0x18003e546  call    ?LockAndUnProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@_N@Z; LockAndUnProtectUserCacheEntry(_USER_CACHE_ENTRY *,bool)
0x18003e54b  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18003e552  mov     ecx, [rsi+118h]
0x18003e558  mov     dword ptr [rbp+57h+Size], ecx
0x18003e55b  mov     rax, [rax+28h]
0x18003e55f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e564  mov     [rbp+57h+Size+8], rax
0x18003e568  test    rax, rax
0x18003e56b  jnz     short loc_18003E5BF
0x18003e56d  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18003e574  mov     ebx, 0C0000017h
0x18003e579  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003e57e  mov     r9, rax
0x18003e581  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18003e588  lea     rax, Class
0x18003e58f  mov     r8d, ebx
0x18003e592  mov     [rsp+0E0h+var_B0], rax
0x18003e597  xor     ecx, ecx
0x18003e599  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x18003e5a0  mov     [rsp+0E0h+var_B8], rax
0x18003e5a5  mov     dword ptr [rsp+0E0h+ReturnLength], 23CEh
0x18003e5ad  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18003e5b2  mov     rcx, rsi; struct _USER_CACHE_ENTRY *
0x18003e5b5  call    ?UnlockAndProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@@Z; UnlockAndProtectUserCacheEntry(_USER_CACHE_ENTRY *)
0x18003e5ba  jmp     loc_18003E678
0x18003e5bf  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x18003e5c3  mov     rcx, rax; void *
0x18003e5c6  mov     rdx, [rsi+120h]; Src
0x18003e5cd  call    memcpy_0
0x18003e5d2  mov     rcx, rsi; struct _USER_CACHE_ENTRY *
0x18003e5d5  call    ?UnlockAndProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@@Z; UnlockAndProtectUserCacheEntry(_USER_CACHE_ENTRY *)
0x18003e5da  mov     rcx, [rdi+8]
0x18003e5de  mov     eax, r14d
0x18003e5e1  neg     eax
0x18003e5e3  mov     r8d, r14d
0x18003e5e6  lea     rax, [rbp+57h+Size]
0x18003e5ea  sbb     rdx, rdx
0x18003e5ed  and     rdx, rax
0x18003e5f0  mov     rax, [rdi+138h]
0x18003e5f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e5fc  mov     ebx, eax
0x18003e5fe  test    eax, eax
0x18003e600  jz      short loc_18003E678
0x18003e602  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18003e609  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003e60e  mov     r9, rax
0x18003e611  lea     rax, Class
0x18003e618  mov     [rsp+0E0h+var_B0], rax
0x18003e61d  lea     rax, aRenewcertifica; "RenewCertificate"
0x18003e624  mov     [rsp+0E0h+var_B8], rax
0x18003e629  mov     dword ptr [rsp+0E0h+ReturnLength], 23DCh
0x18003e631  jmp     short loc_18003E667
0x18003e633  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18003e63a  mov     ebx, 0C0000002h
0x18003e63f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003e644  mov     r9, rax
0x18003e647  lea     rax, Class
0x18003e64e  mov     [rsp+0E0h+var_B0], rax
0x18003e653  lea     rax, aNotImplemented; "Not Implemented"
0x18003e65a  mov     [rsp+0E0h+var_B8], rax
0x18003e65f  mov     dword ptr [rsp+0E0h+ReturnLength], 23E1h
0x18003e667  mov     r8d, ebx
0x18003e66a  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18003e671  xor     ecx, ecx
0x18003e673  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18003e678  mov     rcx, r15; struct _LOGON_SESSION *
0x18003e67b  call    ?ReleaseLogonSession@@YAXPEAU_LOGON_SESSION@@@Z; ReleaseLogonSession(_LOGON_SESSION *)
0x18003e680  mov     rcx, rdi; struct _ApPluginPkg *
0x18003e683  call    ?DerefPackage@@YAXPEAU_ApPluginPkg@@@Z; DerefPackage(_ApPluginPkg *)
0x18003e688  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18003e68c  test    rcx, rcx
0x18003e68f  jz      short loc_18003E697
0x18003e691  call    cs:__imp_NtClose
0x18003e697  mov     rcx, [rbp+57h+Size+8]
0x18003e69b  test    rcx, rcx
0x18003e69e  jz      short loc_18003E6C8
0x18003e6a0  mov     eax, dword ptr [rbp+57h+Size]
0x18003e6a3  test    rax, rax
0x18003e6a6  jz      short loc_18003E6B8
0x18003e6a8  mov     byte ptr [rcx], 0
0x18003e6ab  inc     rcx
0x18003e6ae  sub     rax, 1
0x18003e6b2  jnz     short loc_18003E6A8
0x18003e6b4  mov     rcx, [rbp+57h+Size+8]
0x18003e6b8  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18003e6bf  mov     rax, [rax+30h]
0x18003e6c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6c8  mov     eax, ebx
0x18003e6ca  mov     rcx, [rbp+57h+var_28]
0x18003e6ce  xor     rcx, rsp; StackCookie
0x18003e6d1  call    __security_check_cookie
0x18003e6d6  mov     rbx, [rsp+0E0h+arg_10]
0x18003e6de  add     rsp, 0C0h
0x18003e6e5  pop     r15
0x18003e6e7  pop     r14
0x18003e6e9  pop     rdi
0x18003e6ea  pop     rsi
0x18003e6eb  pop     rbp
0x18003e6ec  retn
```
