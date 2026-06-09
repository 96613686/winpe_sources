# CloudApCallPackageHelper(bool,void * *,void *,void *,ulong,void * *,ulong *,long *)

- ea: `0x180009f10`
- end: `0x18000a5eb`
- name: `?CloudApCallPackageHelper@@YAJ_NPEAPEAXPEAX2K1PEAKPEAJ@Z`
- size: `1755`
- prototype: `__int64 __fastcall(char, void **, unsigned int *, void *, unsigned int, void **, unsigned int *, int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180008010`
- `0x1800099c0`

## callees

- `0x180007fc0`
- `0x180009f10`
- `0x18000a600`
- `0x180042410`
- `0x180048d70`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a361`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a361`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000a1ab`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000a357`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000a1ab`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000a357`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000a190`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000a33c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000a190`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000a33c`
- `ntdll!NtQueryInformationToken` at `0x18000a4cf`
- `ntdll!NtQueryInformationToken` at `0x18000a4cf`
- `ntdll!RtlIsMultiSessionSku` at `0x18000a159`
- `ntdll!RtlIsMultiSessionSku` at `0x18000a159`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000a526`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000a526`

## string_xrefs

- `0x18000a04f`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000a0df`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000a121`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000a1bf`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000a237`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000a29a`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000a2d9`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000a367`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000a3e6`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000a41f`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000a463`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000a4db`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000a532`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000a56d`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000a5b2`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000a4f6`: `NtQueryInformationToken`
- `0x18000a387`: `CheckTokenMembership`
- `0x18000a43f`: `Caller requires TCB privilege`
- `0x18000a1df`: `CheckTokenMembershipLocalSystem`

## pseudocode

```c
__int64 __fastcall CloudApCallPackageHelper(
        char a1,
        void **a2,
        unsigned int *a3,
        void *a4,
        unsigned int a5,
        void **a6,
        unsigned int *a7,
        int *a8)
{
  unsigned int v9; // ebx
  int LastError; // edi
  __int64 (__fastcall **v11)(void **, struct _SECPKG_CLIENT_INFO *, void *, void *, unsigned int, void **, unsigned int *); // rax
  const char *v12; // r9
  char v13; // al
  const char *v14; // rcx
  bool v15; // zf
  const char *v17; // r9
  const char *v18; // rax
  const char *v19; // rax
  char v20; // al
  const char *v21; // rcx
  bool v22; // zf
  char v23; // al
  const char *v24; // rax
  PULONG ReturnLength; // [rsp+20h] [rbp-B9h]
  const char *v26; // [rsp+28h] [rbp-B1h]
  _BYTE v27[4]; // [rsp+40h] [rbp-99h] BYREF
  WINBOOL IsMember; // [rsp+44h] [rbp-95h] BYREF
  DWORD cbSid; // [rsp+48h] [rbp-91h] BYREF
  _SECPKG_CLIENT_INFO v30; // [rsp+50h] [rbp-89h] BYREF
  void *v31; // [rsp+70h] [rbp-69h]
  void **v32; // [rsp+78h] [rbp-61h]
  _BYTE pSid[80]; // [rsp+80h] [rbp-59h] BYREF

  v32 = a2;
  v31 = a4;
  v27[0] = a1;
  memset(&v30, 0, sizeof(v30));
  if ( !a8 || !a7 || !a6 )
  {
    LastError = -1073741811;
    v17 = "";
    while ( 1 )
    {
      v23 = *(v17 - 1);
      v21 = v17--;
      v22 = v23 == 92;
      if ( v23 == 92 )
        break;
      if ( v17 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
      {
        v22 = v23 == 92;
        break;
      }
    }
    v26 = "Invalid Arg(s)";
    LODWORD(ReturnLength) = 4693;
    goto LABEL_40;
  }
  *a8 = 0;
  *a7 = 0;
  *a6 = 0;
  if ( a5 < 4 || !a3 )
  {
    LastError = -1073741811;
    v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    v26 = "Invalid Arg(s)";
    LODWORD(ReturnLength) = 4705;
    goto LABEL_42;
  }
  v9 = *a3;
  if ( *a3 == 1026 )
  {
    v9 = 9;
  }
  else if ( v9 >= 0x12 )
  {
    LastError = -1073741811;
    v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%u", 3221225485LL, v18, 4718, "Bad Message Value", v9);
    return (unsigned int)LastError;
  }
  LastError = ((__int64 (__fastcall *)(_SECPKG_CLIENT_INFO *))g_pLsaFunctionTable->GetClientInfo)(&v30);
  if ( LastError )
  {
    v17 = "";
    while ( 1 )
    {
      v20 = *(v17 - 1);
      v21 = v17--;
      v22 = v20 == 92;
      if ( v20 == 92 )
        break;
      if ( v17 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
      {
        v22 = v20 == 92;
        break;
      }
    }
    v26 = "GetClientInfo";
    LODWORD(ReturnLength) = 4722;
LABEL_40:
    if ( v22 )
      v17 = v21;
    goto LABEL_42;
  }
  if ( (v30.ClientFlags & 1) != 0 )
  {
    LastError = -1073741558;
    v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    v26 = "Caller is terminating";
    LODWORD(ReturnLength) = 4727;
    goto LABEL_42;
  }
  v11 = &funcs_18000A041 + 2 * v9;
  if ( (*((_BYTE *)v11 + 9) || *((_BYTE *)v11 + 10)) && !v30.HasTcbPrivilege )
  {
    if ( !*((_BYTE *)v11 + 10) )
    {
      LastError = -1073741790;
      v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      v26 = "Caller requires TCB privilege";
      LODWORD(ReturnLength) = 4763;
      goto LABEL_42;
    }
    IsMember = 0;
    cbSid = 68;
    if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, &cbSid)
      && !CheckTokenMembership(v30.ClientToken, pSid, &IsMember) )
    {
      LastError = GetLastError();
      v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)LastError, v24, 4748, "CheckTokenMembership", &Class);
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0xC0070000;
      v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      v26 = "CheckTokenMembership";
      LODWORD(ReturnLength) = 4750;
      goto LABEL_42;
    }
    if ( !IsMember )
    {
      LastError = -1073741790;
      v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      v26 = "Caller needs to be TCB or admin";
      LODWORD(ReturnLength) = 4756;
      goto LABEL_42;
    }
  }
  if ( *((_BYTE *)&funcs_18000A041 + 16 * v9 + 8) && !v27[0] )
  {
    LastError = -1073741790;
    v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    v26 = "Caller needs to be trusted";
    LODWORD(ReturnLength) = 4773;
LABEL_42:
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)LastError, v17, ReturnLength, v26, &Class);
    return (unsigned int)LastError;
  }
  if ( v9 - 14 <= 1 )
  {
    if ( (unsigned __int8)RtlIsMultiSessionSku() )
    {
      if ( v9 == 14 )
      {
        IsMember = 0;
        cbSid = 68;
        if ( CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid)
          && !CheckTokenMembership(v30.ClientToken, pSid, &IsMember) )
        {
          LastError = GetLastError();
          v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            (unsigned int)LastError,
            v19,
            4798,
            "CheckTokenMembershipLocalSystem",
            &Class);
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0xC0070000;
          v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
          v26 = "CheckTokenMembershipLocalSystem";
          LODWORD(ReturnLength) = 4800;
          goto LABEL_42;
        }
        if ( !IsMember )
        {
          LastError = -1073741790;
          v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
          v26 = "Caller needs to be local system";
          LODWORD(ReturnLength) = 4807;
          goto LABEL_42;
        }
      }
    }
    else
    {
      IsMember = 0;
      cbSid = 0;
      v27[0] = 0;
      LastError = NtQueryInformationToken(v30.ClientToken, TokenIsAppContainer, &IsMember, 4u, &cbSid);
      if ( LastError < 0 )
      {
        v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        v26 = "NtQueryInformationToken";
        LODWORD(ReturnLength) = 4825;
        goto LABEL_42;
      }
      if ( IsMember == 1 )
      {
        LastError = CapabilityCheck(v30.ClientToken, L"userSigninSupport", v27);
        if ( LastError < 0 )
        {
          v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
          v26 = "CapabilityCheck";
          LODWORD(ReturnLength) = 4836;
          goto LABEL_42;
        }
      }
      if ( !v27[0] )
      {
        LastError = -1073741790;
        v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        v26 = "Caller needs to have userSigninSupport capability";
        LODWORD(ReturnLength) = 4843;
        goto LABEL_42;
      }
    }
  }
  LastError = (*(&funcs_18000A041 + 2 * v9))(v32, &v30, a3, v31, a5, a6, a7);
  v12 = "";
  while ( 1 )
  {
    v13 = *(v12 - 1);
    v14 = v12--;
    v15 = v13 == 92;
    if ( v13 == 92 )
      break;
    if ( v12 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
    {
      v15 = v13 == 92;
      break;
    }
  }
  if ( v15 )
    v12 = v14;
  WPPTraceLogA(2, "0x%08x %s:%u : %s:%u", LastError, v12, 4857, "CallPackageDispatch", v9);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180009f10  mov     [rsp-8+arg_0], rbx
0x180009f15  push    rbp
0x180009f16  push    rsi
0x180009f17  push    rdi
0x180009f18  push    r12
0x180009f1a  push    r13
0x180009f1c  push    r14
0x180009f1e  push    r15
0x180009f20  lea     rbp, [rsp-7]
0x180009f25  sub     rsp, 0E0h
0x180009f2c  mov     rax, cs:__security_cookie
0x180009f33  xor     rax, rsp
0x180009f36  mov     [rbp+37h+var_40], rax
0x180009f3a  mov     rax, [rbp+37h+arg_38]
0x180009f3e  xorps   xmm0, xmm0
0x180009f41  mov     r15, [rbp+37h+arg_28]
0x180009f45  mov     r14, r8
0x180009f48  mov     r12, [rbp+37h+arg_30]
0x180009f4c  mov     [rbp+37h+var_98], rdx
0x180009f50  xor     edx, edx
0x180009f52  mov     [rbp+37h+var_A0], r9
0x180009f56  mov     [rsp+110h+var_D0], cl
0x180009f5a  mov     [rsp+110h+var_C0.LogonId.LowPart], edx
0x180009f5e  movups  xmmword ptr [rsp+110h+var_C0.LogonId.HighPart], xmm0
0x180009f63  movups  xmmword ptr [rbp+37h+var_C0.HasTcbPrivilege], xmm0
0x180009f67  test    rax, rax
0x180009f6a  jz      loc_18000A28E
0x180009f70  test    r12, r12
0x180009f73  jz      loc_18000A28E
0x180009f79  test    r15, r15
0x180009f7c  jz      loc_18000A28E
0x180009f82  mov     r13d, [rbp+37h+arg_20]
0x180009f86  mov     [rax], edx
0x180009f88  mov     [r12], edx
0x180009f8c  mov     [r15], rdx
0x180009f8f  cmp     r13d, 4
0x180009f93  jb      loc_18000A5B2
0x180009f99  test    r8, r8
0x180009f9c  jz      loc_18000A5B2
0x180009fa2  mov     ebx, [r8]
0x180009fa5  cmp     ebx, 402h
0x180009fab  jnz     loc_18000A118
0x180009fb1  mov     ebx, 9
0x180009fb6  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180009fbd  lea     rcx, [rsp+110h+var_C0]
0x180009fc2  mov     rax, [rax+80h]
0x180009fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fce  mov     edi, eax
0x180009fd0  test    eax, eax
0x180009fd2  jnz     loc_18000A230
0x180009fd8  test    [rbp+37h+var_C0.ClientFlags], 1
0x180009fdc  jnz     loc_18000A2D9
0x180009fe2  lea     rdi, funcs_18000A041
0x180009fe9  mov     esi, ebx
0x180009feb  add     rsi, rsi
0x180009fee  cmp     byte ptr [rdi+rsi*8+9], 0
0x180009ff3  lea     rax, [rdi+rsi*8]
0x180009ff7  jz      loc_18000A0C5
0x180009ffd  cmp     [rbp+37h+var_C0.HasTcbPrivilege], 0
0x18000a001  jz      loc_18000A312
0x18000a007  cmp     byte ptr [rdi+rsi*8+8], 0
0x18000a00c  jnz     loc_18000A0D4
0x18000a012  lea     eax, [rbx-0Eh]
0x18000a015  cmp     eax, 1
0x18000a018  jbe     loc_18000A159
0x18000a01e  mov     r9, [rbp+37h+var_A0]; void *
0x18000a022  lea     rdx, [rsp+110h+var_C0]; struct _SECPKG_CLIENT_INFO *
0x18000a027  mov     rcx, [rbp+37h+var_98]; void **
0x18000a02b  mov     r8, r14; void *
0x18000a02e  mov     rax, (funcs_18000A041 - 18009A000h)[rdi+rsi*8]
0x18000a032  mov     [rsp+110h+var_E0], r12; unsigned int *
0x18000a037  mov     [rsp+110h+var_E8], r15; void **
0x18000a03c  mov     dword ptr [rsp+110h+ReturnLength], r13d; unsigned int
0x18000a041  call    _guard_dispatch_icall$thunk$10345483385596137414; CloudAPReinitPlugins(void * *,_SECPKG_CLIENT_INFO *,void *,void *,ulong,void * *,ulong *) ...
0x18000a046  mov     edi, eax
0x18000a048  lea     r9, aOnecoreDsExtCl_16+26h; ""
0x18000a04f  lea     rsi, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000a056  movzx   eax, byte ptr [r9-1]
0x18000a05b  mov     rcx, r9
0x18000a05e  dec     r9
0x18000a061  cmp     al, 5Ch ; '\'
0x18000a063  jz      short loc_18000A06C
0x18000a065  cmp     r9, rsi
0x18000a068  ja      short loc_18000A056
0x18000a06a  cmp     al, 5Ch ; '\'
0x18000a06c  lea     rax, aCallpackagedis; "CallPackageDispatch"
0x18000a073  mov     dword ptr [rsp+110h+var_E0], ebx
0x18000a077  cmovz   r9, rcx
0x18000a07b  mov     [rsp+110h+var_E8], rax
0x18000a080  mov     r8d, edi
0x18000a083  mov     dword ptr [rsp+110h+ReturnLength], 12F9h
0x18000a08b  lea     rdx, a0x08xSUSU; "0x%08x %s:%u : %s:%u"
0x18000a092  mov     ecx, 2
0x18000a097  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000a09c  mov     eax, edi
0x18000a09e  mov     rcx, [rbp+37h+var_40]
0x18000a0a2  xor     rcx, rsp; StackCookie
0x18000a0a5  call    __security_check_cookie
0x18000a0aa  mov     rbx, [rsp+110h+arg_0]
0x18000a0b2  add     rsp, 0E0h
0x18000a0b9  pop     r15
0x18000a0bb  pop     r14
0x18000a0bd  pop     r13
0x18000a0bf  pop     r12
0x18000a0c1  pop     rdi
0x18000a0c2  pop     rsi
0x18000a0c3  pop     rbp
0x18000a0c4  retn
0x18000a0c5  cmp     byte ptr [rax+0Ah], 0
0x18000a0c9  jz      loc_18000A007
0x18000a0cf  jmp     loc_180009FFD
0x18000a0d4  cmp     [rsp+110h+var_D0], 0
0x18000a0d9  jnz     loc_18000A012
0x18000a0df  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000a0e6  mov     edi, 0C0000022h
0x18000a0eb  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000a0f0  mov     r9, rax
0x18000a0f3  lea     rbx, Class
0x18000a0fa  mov     [rsp+110h+var_E0], rbx
0x18000a0ff  lea     rax, aCallerNeedsToB_1; "Caller needs to be trusted"
0x18000a106  mov     [rsp+110h+var_E8], rax
0x18000a10b  mov     dword ptr [rsp+110h+ReturnLength], 12A5h
0x18000a113  jmp     loc_18000A278
0x18000a118  cmp     ebx, 12h
0x18000a11b  jb      loc_180009FB6
0x18000a121  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000a128  mov     edi, 0C000000Dh
0x18000a12d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000a132  mov     dword ptr [rsp+110h+var_E0], ebx
0x18000a136  lea     rdx, a0x08xSUSU; "0x%08x %s:%u : %s:%u"
0x18000a13d  mov     r9, rax
0x18000a140  lea     rax, aBadMessageValu; "Bad Message Value"
0x18000a147  mov     [rsp+110h+var_E8], rax
0x18000a14c  mov     dword ptr [rsp+110h+ReturnLength], 126Eh
0x18000a154  jmp     loc_18000A27F
0x18000a159  call    cs:__imp_RtlIsMultiSessionSku
0x18000a15f  test    al, al
0x18000a161  jz      loc_18000A49C
0x18000a167  cmp     ebx, 0Eh
0x18000a16a  jnz     loc_18000A01E
0x18000a170  lea     r9, [rsp+110h+cbSid]; cbSid
0x18000a175  mov     [rsp+110h+IsMember], 0
0x18000a17d  lea     r8, [rbp+37h+pSid]; pSid
0x18000a181  mov     [rsp+110h+cbSid], 44h ; 'D'
0x18000a189  xor     edx, edx; DomainSid
0x18000a18b  mov     ecx, 16h; WellKnownSidType
0x18000a190  call    cs:__imp_CreateWellKnownSid
0x18000a196  test    eax, eax
0x18000a198  jz      loc_18000A458
0x18000a19e  mov     rcx, [rbp+37h+var_C0.ClientToken]; TokenHandle
0x18000a1a2  lea     r8, [rsp+110h+IsMember]; IsMember
0x18000a1a7  lea     rdx, [rbp+37h+pSid]; SidToCheck
0x18000a1ab  call    cs:__imp_CheckTokenMembership
0x18000a1b1  test    eax, eax
0x18000a1b3  jnz     loc_18000A458
0x18000a1b9  call    cs:__imp_GetLastError
0x18000a1bf  lea     rsi, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000a1c6  mov     edi, eax
0x18000a1c8  mov     rcx, rsi; char *
0x18000a1cb  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000a1d0  lea     rbx, Class
0x18000a1d7  mov     r9, rax
0x18000a1da  mov     [rsp+110h+var_E0], rbx
0x18000a1df  lea     r14, aChecktokenmemb; "CheckTokenMembershipLocalSystem"
0x18000a1e6  mov     [rsp+110h+var_E8], r14
0x18000a1eb  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000a1f2  mov     r8d, edi
0x18000a1f5  mov     dword ptr [rsp+110h+ReturnLength], 12BEh
0x18000a1fd  xor     ecx, ecx
0x18000a1ff  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000a204  test    edi, edi
0x18000a206  jle     short loc_18000A211
0x18000a208  movzx   edi, di
0x18000a20b  or      edi, 0C0070000h
0x18000a211  mov     rcx, rsi; char *
0x18000a214  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000a219  mov     [rsp+110h+var_E0], rbx
0x18000a21e  mov     r9, rax
0x18000a221  mov     [rsp+110h+var_E8], r14
0x18000a226  mov     dword ptr [rsp+110h+ReturnLength], 12C0h
0x18000a22e  jmp     short loc_18000A278
0x18000a230  lea     r9, aOnecoreDsExtCl_16+26h; ""
0x18000a237  lea     rsi, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000a23e  movzx   eax, byte ptr [r9-1]
0x18000a243  mov     rcx, r9
0x18000a246  dec     r9
0x18000a249  cmp     al, 5Ch ; '\'
0x18000a24b  jz      short loc_18000A254
0x18000a24d  cmp     r9, rsi
0x18000a250  ja      short loc_18000A23E
0x18000a252  cmp     al, 5Ch ; '\'
0x18000a254  lea     rbx, Class
0x18000a25b  mov     [rsp+110h+var_E0], rbx
0x18000a260  lea     rax, aGetclientinfo; "GetClientInfo"
0x18000a267  mov     [rsp+110h+var_E8], rax
0x18000a26c  mov     dword ptr [rsp+110h+ReturnLength], 1272h
0x18000a274  cmovz   r9, rcx
0x18000a278  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000a27f  mov     r8d, edi
0x18000a282  xor     ecx, ecx
0x18000a284  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000a289  jmp     loc_18000A09C
0x18000a28e  mov     edi, 0C000000Dh
0x18000a293  lea     r9, aOnecoreDsExtCl_16+26h; ""
0x18000a29a  lea     rsi, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000a2a1  movzx   eax, byte ptr [r9-1]
0x18000a2a6  mov     rcx, r9
0x18000a2a9  dec     r9
0x18000a2ac  cmp     al, 5Ch ; '\'
0x18000a2ae  jz      short loc_18000A2B7
0x18000a2b0  cmp     r9, rsi
0x18000a2b3  ja      short loc_18000A2A1
0x18000a2b5  cmp     al, 5Ch ; '\'
0x18000a2b7  lea     rbx, Class
0x18000a2be  mov     [rsp+110h+var_E0], rbx
0x18000a2c3  lea     rax, aInvalidArgS; "Invalid Arg(s)"
0x18000a2ca  mov     [rsp+110h+var_E8], rax
0x18000a2cf  mov     dword ptr [rsp+110h+ReturnLength], 1255h
0x18000a2d7  jmp     short loc_18000A274
0x18000a2d9  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000a2e0  mov     edi, 0C000010Ah
0x18000a2e5  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000a2ea  mov     r9, rax
0x18000a2ed  lea     rbx, Class
0x18000a2f4  mov     [rsp+110h+var_E0], rbx
0x18000a2f9  lea     rax, aCallerIsTermin; "Caller is terminating"
0x18000a300  mov     [rsp+110h+var_E8], rax
0x18000a305  mov     dword ptr [rsp+110h+ReturnLength], 1277h
0x18000a30d  jmp     loc_18000A278
0x18000a312  cmp     byte ptr [rax+0Ah], 0
0x18000a316  jz      loc_18000A41F
0x18000a31c  lea     r9, [rsp+110h+cbSid]; cbSid
0x18000a321  mov     [rsp+110h+IsMember], 0
0x18000a329  lea     r8, [rbp+37h+pSid]; pSid
0x18000a32d  mov     [rsp+110h+cbSid], 44h ; 'D'
0x18000a335  xor     edx, edx; DomainSid
0x18000a337  mov     ecx, 1Ah; WellKnownSidType
0x18000a33c  call    cs:__imp_CreateWellKnownSid
0x18000a342  test    eax, eax
0x18000a344  jz      loc_18000A3DB
0x18000a34a  mov     rcx, [rbp+37h+var_C0.ClientToken]; TokenHandle
0x18000a34e  lea     r8, [rsp+110h+IsMember]; IsMember
0x18000a353  lea     rdx, [rbp+37h+pSid]; SidToCheck
0x18000a357  call    cs:__imp_CheckTokenMembership
0x18000a35d  test    eax, eax
0x18000a35f  jnz     short loc_18000A3DB
0x18000a361  call    cs:__imp_GetLastError
0x18000a367  lea     rsi, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000a36e  mov     edi, eax
0x18000a370  mov     rcx, rsi; char *
0x18000a373  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000a378  lea     rbx, Class
0x18000a37f  mov     r9, rax
0x18000a382  mov     [rsp+110h+var_E0], rbx
0x18000a387  lea     r14, aChecktokenmemb_0; "CheckTokenMembership"
0x18000a38e  mov     [rsp+110h+var_E8], r14
0x18000a393  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000a39a  mov     r8d, edi
0x18000a39d  mov     dword ptr [rsp+110h+ReturnLength], 128Ch
0x18000a3a5  xor     ecx, ecx
0x18000a3a7  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000a3ac  test    edi, edi
0x18000a3ae  jle     short loc_18000A3B9
0x18000a3b0  movzx   edi, di
0x18000a3b3  or      edi, 0C0070000h
0x18000a3b9  mov     rcx, rsi; char *
0x18000a3bc  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000a3c1  mov     [rsp+110h+var_E0], rbx
0x18000a3c6  mov     r9, rax
0x18000a3c9  mov     [rsp+110h+var_E8], r14
0x18000a3ce  mov     dword ptr [rsp+110h+ReturnLength], 128Eh
0x18000a3d6  jmp     loc_18000A278
0x18000a3db  cmp     [rsp+110h+IsMember], 0
0x18000a3e0  jnz     loc_18000A007
0x18000a3e6  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000a3ed  mov     edi, 0C0000022h
0x18000a3f2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000a3f7  mov     r9, rax
0x18000a3fa  lea     rbx, Class
0x18000a401  mov     [rsp+110h+var_E0], rbx
0x18000a406  lea     rax, aCallerNeedsToB; "Caller needs to be TCB or admin"
0x18000a40d  mov     [rsp+110h+var_E8], rax
0x18000a412  mov     dword ptr [rsp+110h+ReturnLength], 1294h
0x18000a41a  jmp     loc_18000A278
0x18000a41f  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000a426  mov     edi, 0C0000022h
0x18000a42b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000a430  mov     r9, rax
0x18000a433  lea     rbx, Class
0x18000a43a  mov     [rsp+110h+var_E0], rbx
0x18000a43f  lea     rax, aCallerRequires; "Caller requires TCB privilege"
0x18000a446  mov     [rsp+110h+var_E8], rax
0x18000a44b  mov     dword ptr [rsp+110h+ReturnLength], 129Bh
0x18000a453  jmp     loc_18000A278
0x18000a458  cmp     [rsp+110h+IsMember], 0
0x18000a45d  jnz     loc_18000A01E
0x18000a463  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000a46a  mov     edi, 0C0000022h
0x18000a46f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000a474  mov     r9, rax
  ... truncated ...
```
