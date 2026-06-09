# SyncDpapiKey(void *,bool,_ApPluginPkg *,_USER_CACHE_ENTRY *,bool,bool,_CloudAPCache *,bool *)

- ea: `0x1800104c0`
- end: `0x180010a8f`
- name: `?SyncDpapiKey@@YAJPEAX_NPEAU_ApPluginPkg@@PEAU_USER_CACHE_ENTRY@@11PEAU_CloudAPCache@@PEA_N@Z`
- size: `1487`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, char, struct _ApPluginPkg *, struct _USER_CACHE_ENTRY *, bool, bool, struct _CloudAPCache *, bool *)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x18000f210`
- `0x180011960`

## callees

- `0x180003584`
- `0x180007fc0`
- `0x18000a600`
- `0x1800104c0`
- `0x180010aa0`
- `0x180011294`
- `0x180011424`
- `0x180032968`
- `0x180042410`
- `0x18004317c`
- `0x180051544`
- `0x180081010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180010725`
- `ntdll!RtlAcquireResourceExclusive` at `0x180010725`
- `ntdll!RtlReleaseResource` at `0x180010575`
- `ntdll!RtlReleaseResource` at `0x180010719`
- `ntdll!RtlReleaseResource` at `0x180010575`
- `ntdll!RtlReleaseResource` at `0x180010719`
- `ntdll!NtQueryInformationToken` at `0x180010672`
- `ntdll!NtQueryInformationToken` at `0x180010672`
- `ntdll!RtlAcquireResourceShared` at `0x180010581`
- `ntdll!RtlAcquireResourceShared` at `0x180010581`

## string_xrefs

- `0x1800105ab`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180010689`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800107fe`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180010895`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180010916`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001094a`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180010993`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800106b8`: `NtQueryInformationToken`
- `0x1800106e4`: `PersistTokens`
- `0x180010842`: `PersistSSOTokens`
- `0x180010a16`: `PersistSSOTokens`

## pseudocode

```c
__int64 __fastcall SyncDpapiKey(
        HANDLE TokenHandle,
        char a2,
        struct _ApPluginPkg *a3,
        struct _USER_CACHE_ENTRY *a4,
        bool a5,
        bool a6,
        struct _CloudAPCache *a7,
        bool *a8)
{
  unsigned int v12; // esi
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(_QWORD, HANDLE, char *); // rax
  bool v15; // r13
  __int64 (__fastcall *v16)(_QWORD, HANDLE, char *, bool); // rax
  const char *v17; // r9
  char v18; // al
  const char *v19; // rcx
  bool v20; // zf
  const char *v21; // r9
  char v22; // cl
  const char *v23; // rax
  bool v24; // zf
  __int64 v25; // rbx
  __int64 (__fastcall *v27)(_QWORD, _QWORD, int *); // rax
  const char *v28; // r9
  const char *v29; // rax
  char v30; // al
  const char *v31; // rcx
  bool v32; // zf
  const char *v33; // r9
  const char *v34; // r9
  const char *v35; // r9
  const char *v36; // r9
  unsigned int v37; // eax
  const char *v38; // rax
  const char *v39; // rax
  PULONG ReturnLength; // [rsp+20h] [rbp-E8h]
  PULONG ReturnLengtha; // [rsp+20h] [rbp-E8h]
  PULONG ReturnLengthb; // [rsp+20h] [rbp-E8h]
  PULONG ReturnLengthc; // [rsp+20h] [rbp-E8h]
  const char *v44; // [rsp+28h] [rbp-E0h]
  bool v45; // [rsp+40h] [rbp-C8h] BYREF
  int v46; // [rsp+44h] [rbp-C4h] BYREF
  ULONG v47; // [rsp+48h] [rbp-C0h] BYREF
  bool *v48; // [rsp+50h] [rbp-B8h]
  _QWORD TokenInformation[12]; // [rsp+60h] [rbp-A8h] BYREF

  v48 = a8;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  memset_0(TokenInformation, 0, 0x58u);
  if ( (*((_BYTE *)a3 + 160) & 1) == 0 || !a2 )
    goto LABEL_2;
  v12 = NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x58u, &v47);
  if ( !v12 )
  {
    v27 = (__int64 (__fastcall *)(_QWORD, _QWORD, int *))*((_QWORD *)a3 + 27);
    if ( v27 )
    {
      v12 = v27(*((_QWORD *)a3 + 1), TokenInformation[0], &v46);
      if ( v12 )
      {
        v33 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(ReturnLengtha) = 6646;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v33, ReturnLengtha, "ConnectIdentity", &Class);
        return v12;
      }
    }
    if ( !v46 && *((_QWORD *)a3 + 37) )
    {
      v12 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, _QWORD *, ULONG *))g_pLsaIdProvHostFunctionTable
             + 4))(
              *((_QWORD *)a3 + 2),
              *((_QWORD *)a4 + 12),
              0,
              14,
              TokenInformation,
              &v47);
      if ( v12 )
      {
        v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(ReturnLengthb) = 6660;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v28, ReturnLengthb, "LookUpUserInfo", &Class);
        return v12;
      }
      SCLockConvertExclusiveToShared((PRTL_RESOURCE)(*((_QWORD *)a4 + 3) + 24LL));
      v12 = (*((__int64 (__fastcall **)(_QWORD, __int64, HANDLE, _QWORD, char *))a3 + 37))(
              *((_QWORD *)a3 + 1),
              1,
              TokenHandle,
              TokenInformation[0],
              (char *)a4 + 280);
      SCLockConvertSharedToExclusive((PRTL_RESOURCE)(*((_QWORD *)a4 + 3) + 24LL));
      if ( v12 )
      {
        v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(ReturnLengthc) = 6672;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v34, ReturnLengthc, "ConnectIdentity", &Class);
        return v12;
      }
    }
LABEL_2:
    v12 = RollDpapiKey(TokenHandle, a3, a4, a6, a7, &v45);
    if ( v12 )
    {
      v35 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(ReturnLength) = 6686;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v35, ReturnLength, "RollDpapiKey", &Class);
      return v12;
    }
    v13 = *((_QWORD *)a4 + 3);
    _InterlockedIncrement((volatile signed __int32 *)(v13 + 120));
    RtlReleaseResource((PRTL_RESOURCE)(v13 + 24));
    RtlAcquireResourceShared((PRTL_RESOURCE)(v13 + 24), 1u);
    _InterlockedDecrement((volatile signed __int32 *)(v13 + 120));
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::GetImpl'::`2'::impl);
    if ( IsLoadAadCredKeyFromProfileEnabled() && *((_DWORD *)a4 + 88) != 1 )
    {
      CloudAPProvider::GetCredKeyFromProfileStatusFailedOnSyncDpapiKey<enum GET_CRED_KEY_FROM_PROFILE_STATUS &>();
      v12 = -1073739508;
      v36 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(ReturnLength) = 6705;
      WPPTraceLogA(
        0,
        "0x%08x %s:%u : %s:%ws",
        3221227788LL,
        v36,
        ReturnLength,
        "Failing SyncDpapiKey call due to eGetCredKeyFromProfileStatus",
        &Class);
      goto LABEL_29;
    }
    v14 = (__int64 (__fastcall *)(_QWORD, HANDLE, char *))*((_QWORD *)a3 + 25);
    if ( v14 && (*(_BYTE *)a7 & 1) != 0 )
    {
      v37 = v14(*((_QWORD *)a3 + 1), TokenHandle, (char *)a4 + 280);
      v12 = v37;
      if ( v37 != -1073741801 && v37 != -1073741670 )
      {
        if ( v37 )
        {
          v38 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(ReturnLength) = 1961;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v38, ReturnLength, "PersistSSOTokens", &Class);
        }
        *(_DWORD *)a7 &= ~1u;
        v15 = 1;
        goto LABEL_6;
      }
      v29 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(ReturnLength) = 1959;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v29, ReturnLength, "PersistSSOTokens", &Class);
      if ( v12 )
      {
        v17 = "";
        while ( 1 )
        {
          v30 = *(v17 - 1);
          v31 = v17--;
          v32 = v30 == 92;
          if ( v30 == 92 )
            break;
          if ( v17 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
          {
            v32 = v30 == 92;
            break;
          }
        }
        v44 = "PersistTokens";
        if ( v32 )
          v17 = v31;
        LODWORD(ReturnLength) = 6715;
        goto LABEL_28;
      }
    }
    v15 = v45;
LABEL_6:
    if ( !a2 || (v16 = (__int64 (__fastcall *)(_QWORD, HANDLE, char *, bool))*((_QWORD *)a3 + 36)) == 0 )
    {
LABEL_34:
      if ( v15 )
        *v48 = 1;
      v12 = 0;
      goto LABEL_29;
    }
    v12 = v16(*((_QWORD *)a3 + 1), TokenHandle, (char *)a4 + 280, a5);
    if ( v12 != -1073741801 && v12 != -1073741670 )
    {
      if ( v12 )
      {
        v39 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(ReturnLength) = 6736;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v39, ReturnLength, "UserProfileLoaded", &Class);
      }
      goto LABEL_34;
    }
    v17 = "";
    while ( 1 )
    {
      v18 = *(v17 - 1);
      v19 = v17--;
      v20 = v18 == 92;
      if ( v18 == 92 )
        break;
      if ( v17 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v20 = v18 == 92;
        break;
      }
    }
    v44 = "UserProfileLoaded";
    if ( v20 )
      v17 = v19;
    LODWORD(ReturnLength) = 6734;
LABEL_28:
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v17, ReturnLength, v44, &Class);
LABEL_29:
    v25 = *((_QWORD *)a4 + 3);
    _InterlockedIncrement((volatile signed __int32 *)(v25 + 120));
    RtlReleaseResource((PRTL_RESOURCE)(v25 + 24));
    RtlAcquireResourceExclusive((PRTL_RESOURCE)(v25 + 24), 1u);
    _InterlockedDecrement((volatile signed __int32 *)(v25 + 120));
    return v12;
  }
  v21 = "";
  while ( 1 )
  {
    v22 = *(v21 - 1);
    v23 = v21--;
    v24 = v22 == 92;
    if ( v22 == 92 )
      break;
    if ( v21 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
    {
      v24 = v22 == 92;
      break;
    }
  }
  if ( v24 )
    v21 = v23;
  LODWORD(ReturnLengtha) = 6637;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v21, ReturnLengtha, "NtQueryInformationToken", &Class);
  return v12;
}

```

## disassembly

```asm
0x1800104c0  mov     [rsp+arg_8], rbx
0x1800104c5  push    rbp
0x1800104c6  push    rsi
0x1800104c7  push    rdi
0x1800104c8  push    r12
0x1800104ca  push    r13
0x1800104cc  push    r14
0x1800104ce  push    r15
0x1800104d0  sub     rsp, 0D0h
0x1800104d7  mov     rax, cs:__security_cookie
0x1800104de  xor     rax, rsp
0x1800104e1  mov     [rsp+108h+var_48], rax
0x1800104e9  mov     rax, [rsp+108h+arg_38]
0x1800104f1  mov     rdi, r8
0x1800104f4  mov     r13, [rsp+108h+arg_30]
0x1800104fc  movzx   r15d, dl
0x180010500  mov     [rsp+108h+var_B8], rax
0x180010505  mov     r12, rcx
0x180010508  xor     eax, eax
0x18001050a  mov     [rsp+108h+var_C8], 0
0x18001050f  xor     edx, edx; Val
0x180010511  mov     [rsp+108h+var_C4], eax
0x180010515  mov     r8d, 58h ; 'X'; Size
0x18001051b  mov     [rsp+108h+var_C0], eax
0x18001051f  lea     rcx, [rsp+108h+TokenInformation]; void *
0x180010524  mov     rbp, r9
0x180010527  call    memset_0
0x18001052c  test    byte ptr [rdi+0A0h], 1
0x180010533  jnz     loc_18001064C
0x180010539  movzx   r9d, [rsp+108h+arg_28]; bool
0x180010542  lea     rax, [rsp+108h+var_C8]
0x180010547  mov     [rsp+108h+var_E0], rax; bool *
0x18001054c  mov     r8, rbp; struct _USER_CACHE_ENTRY *
0x18001054f  mov     rdx, rdi; struct _ApPluginPkg *
0x180010552  mov     [rsp+108h+ReturnLength], r13; struct _CloudAPCache *
0x180010557  mov     rcx, r12; void *
0x18001055a  call    ?RollDpapiKey@@YAJPEAXPEAU_ApPluginPkg@@PEAU_USER_CACHE_ENTRY@@_NPEAU_CloudAPCache@@PEA_N@Z; RollDpapiKey(void *,_ApPluginPkg *,_USER_CACHE_ENTRY *,bool,_CloudAPCache *,bool *)
0x18001055f  mov     esi, eax
0x180010561  test    eax, eax
0x180010563  jnz     loc_18001094A
0x180010569  mov     rbx, [rbp+18h]
0x18001056d  lock inc dword ptr [rbx+78h]
0x180010571  lea     rcx, [rbx+18h]; Resource
0x180010575  call    cs:__imp_RtlReleaseResource
0x18001057b  mov     dl, 1; Wait
0x18001057d  lea     rcx, [rbx+18h]; Resource
0x180010581  call    cs:__imp_RtlAcquireResourceShared
0x180010587  lock dec dword ptr [rbx+78h]
0x18001058b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile> `wil::Feature<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::GetImpl(void)'::`2'::impl
0x180010592  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x180010597  call    ?IsLoadAadCredKeyFromProfileEnabled@@YA_NXZ; IsLoadAadCredKeyFromProfileEnabled(void)
0x18001059c  test    al, al
0x18001059e  jnz     loc_18001097E
0x1800105a4  mov     rax, [rdi+0C8h]
0x1800105ab  lea     rbx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800105b2  lea     r14, Class
0x1800105b9  test    rax, rax
0x1800105bc  jnz     loc_1800109CC
0x1800105c2  movzx   r13d, [rsp+108h+var_C8]
0x1800105c8  lea     rcx, [rbp+118h]
0x1800105cf  test    r15b, r15b
0x1800105d2  jz      loc_180010770
0x1800105d8  mov     rax, [rdi+120h]
0x1800105df  test    rax, rax
0x1800105e2  jz      loc_180010770
0x1800105e8  movzx   r9d, [rsp+108h+arg_20]
0x1800105f1  mov     r8, rcx
0x1800105f4  mov     rcx, [rdi+8]
0x1800105f8  mov     rdx, r12
0x1800105fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010600  mov     esi, eax
0x180010602  cmp     eax, 0C0000017h
0x180010607  jnz     loc_18001075C
0x18001060d  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x180010614  movzx   eax, byte ptr [r9-1]
0x180010619  mov     rcx, r9
0x18001061c  dec     r9
0x18001061f  cmp     al, 5Ch ; '\'
0x180010621  jz      short loc_18001062A
0x180010623  cmp     r9, rbx
0x180010626  ja      short loc_180010614
0x180010628  cmp     al, 5Ch ; '\'
0x18001062a  mov     [rsp+108h+var_D8], r14
0x18001062f  lea     rax, aUserprofileloa; "UserProfileLoaded"
0x180010636  mov     [rsp+108h+var_E0], rax
0x18001063b  cmovz   r9, rcx
0x18001063f  mov     dword ptr [rsp+108h+ReturnLength], 1A4Eh
0x180010647  jmp     loc_1800106FC
0x18001064c  test    r15b, r15b
0x18001064f  jz      loc_180010539
0x180010655  lea     rax, [rsp+108h+var_C0]
0x18001065a  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180010660  lea     r8, [rsp+108h+TokenInformation]; TokenInformation
0x180010665  mov     [rsp+108h+ReturnLength], rax; ReturnLength
0x18001066a  mov     edx, 1; TokenInformationClass
0x18001066f  mov     rcx, r12; TokenHandle
0x180010672  call    cs:__imp_NtQueryInformationToken
0x180010678  mov     esi, eax
0x18001067a  test    eax, eax
0x18001067c  jz      loc_18001077D
0x180010682  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x180010689  lea     rbx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180010690  movzx   ecx, byte ptr [r9-1]
0x180010695  mov     rax, r9
0x180010698  dec     r9
0x18001069b  cmp     cl, 5Ch ; '\'
0x18001069e  jz      short loc_1800106A8
0x1800106a0  cmp     r9, rbx
0x1800106a3  ja      short loc_180010690
0x1800106a5  cmp     cl, 5Ch ; '\'
0x1800106a8  cmovz   r9, rax
0x1800106ac  lea     r14, Class
0x1800106b3  mov     [rsp+108h+var_D8], r14
0x1800106b8  lea     rax, aNtqueryinforma_1; "NtQueryInformationToken"
0x1800106bf  mov     [rsp+108h+var_E0], rax
0x1800106c4  mov     dword ptr [rsp+108h+ReturnLength], 19EDh
0x1800106cc  mov     r8d, esi
0x1800106cf  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800106d6  xor     ecx, ecx
0x1800106d8  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800106dd  jmp     short loc_18001072F
0x1800106df  mov     [rsp+108h+var_D8], r14
0x1800106e4  lea     rax, aPersisttokens; "PersistTokens"
0x1800106eb  mov     [rsp+108h+var_E0], rax
0x1800106f0  cmovz   r9, rcx
0x1800106f4  mov     dword ptr [rsp+108h+ReturnLength], 1A3Bh
0x1800106fc  mov     r8d, esi
0x1800106ff  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180010706  xor     ecx, ecx
0x180010708  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001070d  mov     rbx, [rbp+18h]
0x180010711  lock inc dword ptr [rbx+78h]
0x180010715  lea     rcx, [rbx+18h]; Resource
0x180010719  call    cs:__imp_RtlReleaseResource
0x18001071f  mov     dl, 1; Wait
0x180010721  lea     rcx, [rbx+18h]; Resource
0x180010725  call    cs:__imp_RtlAcquireResourceExclusive
0x18001072b  lock dec dword ptr [rbx+78h]
0x18001072f  mov     eax, esi
0x180010731  mov     rcx, [rsp+108h+var_48]
0x180010739  xor     rcx, rsp; StackCookie
0x18001073c  call    __security_check_cookie
0x180010741  mov     rbx, [rsp+108h+arg_8]
0x180010749  add     rsp, 0D0h
0x180010750  pop     r15
0x180010752  pop     r14
0x180010754  pop     r13
0x180010756  pop     r12
0x180010758  pop     rdi
0x180010759  pop     rsi
0x18001075a  pop     rbp
0x18001075b  retn
0x18001075c  cmp     esi, 0C000009Ah
0x180010762  jz      loc_18001060D
0x180010768  test    esi, esi
0x18001076a  jnz     loc_180010A48
0x180010770  test    r13b, r13b
0x180010773  jnz     loc_180010A82
0x180010779  xor     esi, esi
0x18001077b  jmp     short loc_18001070D
0x18001077d  mov     rax, [rdi+0D8h]
0x180010784  test    rax, rax
0x180010787  jz      short loc_1800107A6
0x180010789  mov     rdx, [rsp+108h+TokenInformation]
0x18001078e  lea     r8, [rsp+108h+var_C4]
0x180010793  mov     rcx, [rdi+8]
0x180010797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001079c  mov     esi, eax
0x18001079e  test    eax, eax
0x1800107a0  jnz     loc_180010895
0x1800107a6  cmp     [rsp+108h+var_C4], 0
0x1800107ab  jnz     loc_180010539
0x1800107b1  cmp     qword ptr [rdi+128h], 0
0x1800107b9  jz      loc_180010539
0x1800107bf  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x1800107c6  lea     rcx, [rsp+108h+var_C0]
0x1800107cb  mov     rdx, [rbp+60h]
0x1800107cf  mov     r9d, 0Eh
0x1800107d5  mov     [rsp+108h+var_E0], rcx
0x1800107da  xor     r8d, r8d
0x1800107dd  lea     rcx, [rsp+108h+TokenInformation]
0x1800107e2  mov     rax, [rax+20h]
0x1800107e6  mov     [rsp+108h+ReturnLength], rcx
0x1800107eb  mov     rcx, [rdi+10h]
0x1800107ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107f4  mov     esi, eax
0x1800107f6  test    eax, eax
0x1800107f8  jz      loc_1800108C9
0x1800107fe  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180010805  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001080a  mov     r9, rax
0x18001080d  lea     r14, Class
0x180010814  mov     [rsp+108h+var_D8], r14
0x180010819  lea     rax, aLookupuserinfo; "LookUpUserInfo"
0x180010820  mov     [rsp+108h+var_E0], rax
0x180010825  mov     dword ptr [rsp+108h+ReturnLength], 1A04h
0x18001082d  jmp     loc_1800106CC
0x180010832  mov     rcx, rbx; char *
0x180010835  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001083a  mov     r9, rax
0x18001083d  mov     [rsp+108h+var_D8], r14
0x180010842  lea     rax, aPersistssotoke; "PersistSSOTokens"
0x180010849  mov     r8d, esi
0x18001084c  mov     [rsp+108h+var_E0], rax
0x180010851  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180010858  xor     ecx, ecx
0x18001085a  mov     dword ptr [rsp+108h+ReturnLength], 7A7h
0x180010862  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180010867  test    esi, esi
0x180010869  jz      loc_1800105C2
0x18001086f  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x180010876  movzx   eax, byte ptr [r9-1]
0x18001087b  mov     rcx, r9
0x18001087e  dec     r9
0x180010881  cmp     al, 5Ch ; '\'
0x180010883  jz      loc_1800106DF
0x180010889  cmp     r9, rbx
0x18001088c  ja      short loc_180010876
0x18001088e  cmp     al, 5Ch ; '\'
0x180010890  jmp     loc_1800106DF
0x180010895  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18001089c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800108a1  mov     r9, rax
0x1800108a4  lea     r14, Class
0x1800108ab  mov     [rsp+108h+var_D8], r14
0x1800108b0  lea     rax, aConnectidentit; "ConnectIdentity"
0x1800108b7  mov     [rsp+108h+var_E0], rax
0x1800108bc  mov     dword ptr [rsp+108h+ReturnLength], 19F6h
0x1800108c4  jmp     loc_1800106CC
0x1800108c9  mov     rcx, [rbp+18h]
0x1800108cd  add     rcx, 18h; Resource
0x1800108d1  call    SCLockConvertExclusiveToShared
0x1800108d6  mov     r9, [rsp+108h+TokenInformation]
0x1800108db  lea     rcx, [rbp+118h]
0x1800108e2  mov     rax, [rdi+128h]
0x1800108e9  mov     r8, r12
0x1800108ec  mov     [rsp+108h+ReturnLength], rcx
0x1800108f1  mov     edx, 1
0x1800108f6  mov     rcx, [rdi+8]
0x1800108fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108ff  mov     rcx, [rbp+18h]
0x180010903  mov     esi, eax
0x180010905  add     rcx, 18h; Resource
0x180010909  call    SCLockConvertSharedToExclusive
0x18001090e  test    esi, esi
0x180010910  jz      loc_180010539
0x180010916  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18001091d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180010922  mov     r9, rax
0x180010925  lea     r14, Class
0x18001092c  mov     [rsp+108h+var_D8], r14
0x180010931  lea     rax, aConnectidentit; "ConnectIdentity"
0x180010938  mov     [rsp+108h+var_E0], rax
0x18001093d  mov     dword ptr [rsp+108h+ReturnLength], 1A10h
0x180010945  jmp     loc_1800106CC
0x18001094a  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180010951  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180010956  mov     r9, rax
0x180010959  lea     r14, Class
0x180010960  mov     [rsp+108h+var_D8], r14
0x180010965  lea     rax, aRolldpapikey; "RollDpapiKey"
0x18001096c  mov     [rsp+108h+var_E0], rax
0x180010971  mov     dword ptr [rsp+108h+ReturnLength], 1A1Eh
0x180010979  jmp     loc_1800106CC
0x18001097e  lea     rcx, [rbp+160h]
0x180010985  cmp     dword ptr [rcx], 1
0x180010988  jz      loc_1800105A4
0x18001098e  call    ??$GetCredKeyFromProfileStatusFailedOnSyncDpapiKey@AEAW4GET_CRED_KEY_FROM_PROFILE_STATUS@@@CloudAPProvider@@SAXAEAW4GET_CRED_KEY_FROM_PROFILE_STATUS@@@Z; CloudAPProvider::GetCredKeyFromProfileStatusFailedOnSyncDpapiKey<GET_CRED_KEY_FROM_PROFILE_STATUS &>(GET_CRED_KEY_FROM_PROFILE_STATUS &)
0x180010993  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18001099a  mov     esi, 0C000090Ch
0x18001099f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800109a4  mov     r9, rax
0x1800109a7  lea     r14, Class
0x1800109ae  mov     [rsp+108h+var_D8], r14
0x1800109b3  lea     rax, aFailingSyncdpa; "Failing SyncDpapiKey call due to eGetCr"...
0x1800109ba  mov     [rsp+108h+var_E0], rax
0x1800109bf  mov     dword ptr [rsp+108h+ReturnLength], 1A31h
0x1800109c7  jmp     loc_1800106FC
0x1800109cc  test    byte ptr [r13+0], 1
0x1800109d1  jz      loc_1800105C2
0x1800109d7  mov     rcx, [rdi+8]
0x1800109db  lea     r8, [rbp+118h]
0x1800109e2  mov     rdx, r12
0x1800109e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109ea  mov     esi, eax
0x1800109ec  cmp     eax, 0C0000017h
0x1800109f1  jz      loc_180010832
0x1800109f7  cmp     eax, 0C000009Ah
0x1800109fc  jz      loc_180010832
0x180010a02  test    eax, eax
0x180010a04  jz      short loc_180010A3B
0x180010a06  mov     rcx, rbx; char *
0x180010a09  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180010a0e  mov     r9, rax
0x180010a11  mov     [rsp+108h+var_D8], r14
0x180010a16  lea     rax, aPersistssotoke; "PersistSSOTokens"
0x180010a1d  mov     r8d, esi
0x180010a20  mov     [rsp+108h+var_E0], rax
0x180010a25  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180010a2c  xor     ecx, ecx
  ... truncated ...
```
