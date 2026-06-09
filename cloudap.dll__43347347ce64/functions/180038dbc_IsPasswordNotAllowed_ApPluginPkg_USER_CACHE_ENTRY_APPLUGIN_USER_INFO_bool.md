# IsPasswordNotAllowed(_ApPluginPkg *,_USER_CACHE_ENTRY *,_APPLUGIN_USER_INFO *,bool *)

- ea: `0x180038dbc`
- end: `0x180039087`
- name: `?IsPasswordNotAllowed@@YAJPEAU_ApPluginPkg@@PEAU_USER_CACHE_ENTRY@@PEAU_APPLUGIN_USER_INFO@@PEA_N@Z`
- size: `715`
- prototype: `__int64 __fastcall(struct _ApPluginPkg *, struct _USER_CACHE_ENTRY *, struct _APPLUGIN_USER_INFO *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011960`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x180026d70`
- `0x180038dbc`
- `0x18003a3bc`
- `0x1800650dc`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038edf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038ee9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038edf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038ee9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180038ecb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180038ecb`

## string_xrefs

- `0x180038e01`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180038e81`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180038ef8`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180038f6a`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180038fd7`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18003901a`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180038f13`: `ConvertSidToStringSid`

## pseudocode

```c
__int64 __fastcall IsPasswordNotAllowed(
        struct _ApPluginPkg *a1,
        struct _USER_CACHE_ENTRY *a2,
        struct _APPLUGIN_USER_INFO *a3,
        bool *a4)
{
  unsigned int UserType; // ebx
  const char *v9; // r9
  const char *v10; // r9
  void *v11; // rcx
  const char *v12; // r9
  const char *v13; // r9
  const char *v14; // r9
  const char *v15; // r9
  __int64 v17; // [rsp+20h] [rbp-48h]
  unsigned int v18; // [rsp+40h] [rbp-28h] BYREF
  int v19; // [rsp+44h] [rbp-24h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-20h] BYREF
  void *v21; // [rsp+50h] [rbp-18h] BYREF
  int v22; // [rsp+B8h] [rbp+50h] BYREF

  v21 = 0;
  v18 = 0;
  v19 = 0;
  *a4 = 0;
  UserType = GetUserType(a1, a2, &v18);
  if ( UserType )
  {
    v9 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserType, v9, 6924, "GetUserType", &Class);
    goto LABEL_28;
  }
  if ( (v18 & 2) != 0 )
  {
    if ( (*((_BYTE *)a1 + 160) & 1) != 0 )
    {
      UserType = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, void **, int *))g_pLsaIdProvHostFunctionTable
                  + 4))(
                   *((_QWORD *)a1 + 2),
                   *((_QWORD *)a2 + 12),
                   0,
                   14,
                   &v21,
                   &v19);
      if ( UserType )
      {
        v10 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v17) = 6937;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserType, v10, v17, "LookUpUserInfo", &Class);
        goto LABEL_28;
      }
      v11 = v21;
    }
    else
    {
      v11 = (void *)*((_QWORD *)a3 + 2);
    }
    StringSid = 0;
    if ( ConvertSidToStringSidW(v11, &StringSid) )
    {
      v22 = 0;
      if ( (unsigned __int16)IsAccountPasswordLess(StringSid, &v22) )
        UserType = (unsigned __int16)IsAccountPasswordLess(StringSid, &v22) | 0xC0070000;
      else
        UserType = (unsigned __int16)IsAccountPasswordLess(StringSid, &v22);
      if ( UserType )
      {
        v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v17) = 6961;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserType, v13, v17, "IsAccountPasswordLess", &Class);
      }
      else
      {
        v18 = 0;
        if ( (unsigned __int16)IsAccountPasswordLessByPolicy(StringSid, &v18) )
          UserType = (unsigned __int16)IsAccountPasswordLessByPolicy(StringSid, &v18) | 0xC0070000;
        else
          UserType = (unsigned __int16)IsAccountPasswordLessByPolicy(StringSid, &v18);
        if ( UserType )
        {
          v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v17) = 6965;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserType, v14, v17, "IsAccountPasswordLessByPolicy", &Class);
        }
        else if ( v22 && !v18 )
        {
          *a4 = 1;
        }
      }
    }
    else
    {
      if ( (int)GetLastError() > 0 )
        UserType = (unsigned __int16)GetLastError() | 0xC0070000;
      else
        UserType = GetLastError();
      v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v17) = 6956;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserType, v12, v17, "ConvertSidToStringSid", &Class);
    }
  }
  else
  {
    UserType = -1073283070;
    v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221684226LL, v15, 6949, "No Cred Key for an unverified account", &Class);
  }
LABEL_28:
  if ( v21 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  return UserType;
}

```

## disassembly

```asm
0x180038dbc  push    rbp
0x180038dbe  push    rbx
0x180038dbf  push    rsi
0x180038dc0  push    rdi
0x180038dc1  push    r14
0x180038dc3  push    r15
0x180038dc5  mov     rbp, rsp
0x180038dc8  sub     rsp, 68h
0x180038dcc  mov     rsi, r8
0x180038dcf  mov     [rbp+var_18], 0
0x180038dd7  lea     r8, [rbp+var_28]; unsigned int *
0x180038ddb  mov     [rbp+var_28], 0
0x180038de2  mov     r15, r9
0x180038de5  mov     [rbp+var_24], 0
0x180038dec  mov     r14, rdx
0x180038def  mov     byte ptr [r9], 0
0x180038df3  mov     rdi, rcx
0x180038df6  call    ?GetUserType@@YAJPEAU_ApPluginPkg@@PEAU_USER_CACHE_ENTRY@@PEAK@Z; GetUserType(_ApPluginPkg *,_USER_CACHE_ENTRY *,ulong *)
0x180038dfb  mov     ebx, eax
0x180038dfd  test    eax, eax
0x180038dff  jz      short loc_180038E35
0x180038e01  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180038e08  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180038e0d  mov     r9, rax
0x180038e10  lea     rax, Class
0x180038e17  mov     [rsp+68h+var_38], rax
0x180038e1c  lea     rax, aGetusertype; "GetUserType"
0x180038e23  mov     [rsp+68h+var_40], rax
0x180038e28  mov     dword ptr [rsp+68h+var_48], 1B0Ch
0x180038e30  jmp     loc_18003904E
0x180038e35  test    byte ptr [rbp+var_28], 2
0x180038e39  jz      loc_18003901A
0x180038e3f  test    byte ptr [rdi+0A0h], 1
0x180038e46  jz      short loc_180038EBB
0x180038e48  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x180038e4f  lea     rcx, [rbp+var_24]
0x180038e53  mov     rdx, [r14+60h]
0x180038e57  mov     r9d, 0Eh
0x180038e5d  mov     [rsp+68h+var_40], rcx
0x180038e62  xor     r8d, r8d
0x180038e65  lea     rcx, [rbp+var_18]
0x180038e69  mov     rax, [rax+20h]
0x180038e6d  mov     [rsp+68h+var_48], rcx
0x180038e72  mov     rcx, [rdi+10h]
0x180038e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e7b  mov     ebx, eax
0x180038e7d  test    eax, eax
0x180038e7f  jz      short loc_180038EB5
0x180038e81  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180038e88  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180038e8d  mov     r9, rax
0x180038e90  lea     rax, Class
0x180038e97  mov     [rsp+68h+var_38], rax
0x180038e9c  lea     rax, aLookupuserinfo; "LookUpUserInfo"
0x180038ea3  mov     [rsp+68h+var_40], rax
0x180038ea8  mov     dword ptr [rsp+68h+var_48], 1B19h
0x180038eb0  jmp     loc_18003904E
0x180038eb5  mov     rcx, [rbp+var_18]
0x180038eb9  jmp     short loc_180038EBF
0x180038ebb  mov     rcx, [rsi+10h]; Sid
0x180038ebf  lea     rdx, [rbp+StringSid]; StringSid
0x180038ec3  mov     [rbp+StringSid], 0
0x180038ecb  call    cs:__imp_ConvertSidToStringSidW
0x180038ed1  test    eax, eax
0x180038ed3  jnz     short loc_180038F2C
0x180038ed5  call    cs:__imp_GetLastError
0x180038edb  test    eax, eax
0x180038edd  jg      short loc_180038EE9
0x180038edf  call    cs:__imp_GetLastError
0x180038ee5  mov     ebx, eax
0x180038ee7  jmp     short loc_180038EF8
0x180038ee9  call    cs:__imp_GetLastError
0x180038eef  movzx   ebx, ax
0x180038ef2  or      ebx, 0C0070000h
0x180038ef8  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180038eff  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180038f04  mov     r9, rax
0x180038f07  lea     rax, Class
0x180038f0e  mov     [rsp+68h+var_38], rax
0x180038f13  lea     rax, aConvertsidtost; "ConvertSidToStringSid"
0x180038f1a  mov     [rsp+68h+var_40], rax
0x180038f1f  mov     dword ptr [rsp+68h+var_48], 1B2Ch
0x180038f27  jmp     loc_18003904E
0x180038f2c  mov     rcx, [rbp+StringSid]; unsigned __int16 *
0x180038f30  lea     rdx, [rbp+arg_18]; int *
0x180038f34  mov     [rbp+arg_18], 0
0x180038f3b  call    IsAccountPasswordLess
0x180038f40  mov     rcx, [rbp+StringSid]; unsigned __int16 *
0x180038f44  mov     edi, 0C0070000h
0x180038f49  lea     rdx, [rbp+arg_18]; int *
0x180038f4d  test    ax, ax
0x180038f50  jnz     short loc_180038F5C
0x180038f52  call    IsAccountPasswordLess
0x180038f57  movzx   ebx, ax
0x180038f5a  jmp     short loc_180038F66
0x180038f5c  call    IsAccountPasswordLess
0x180038f61  movzx   ebx, ax
0x180038f64  or      ebx, edi
0x180038f66  test    ebx, ebx
0x180038f68  jz      short loc_180038F9E
0x180038f6a  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180038f71  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180038f76  mov     r9, rax
0x180038f79  lea     rax, Class
0x180038f80  mov     [rsp+68h+var_38], rax
0x180038f85  lea     rax, aIsaccountpassw; "IsAccountPasswordLess"
0x180038f8c  mov     [rsp+68h+var_40], rax
0x180038f91  mov     dword ptr [rsp+68h+var_48], 1B31h
0x180038f99  jmp     loc_18003904E
0x180038f9e  mov     rcx, [rbp+StringSid]
0x180038fa2  lea     rdx, [rbp+var_28]
0x180038fa6  mov     [rbp+var_28], 0
0x180038fad  call    IsAccountPasswordLessByPolicy
0x180038fb2  mov     rcx, [rbp+StringSid]
0x180038fb6  lea     rdx, [rbp+var_28]
0x180038fba  test    ax, ax
0x180038fbd  jnz     short loc_180038FC9
0x180038fbf  call    IsAccountPasswordLessByPolicy
0x180038fc4  movzx   ebx, ax
0x180038fc7  jmp     short loc_180038FD3
0x180038fc9  call    IsAccountPasswordLessByPolicy
0x180038fce  movzx   ebx, ax
0x180038fd1  or      ebx, edi
0x180038fd3  test    ebx, ebx
0x180038fd5  jz      short loc_180039008
0x180038fd7  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180038fde  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180038fe3  mov     r9, rax
0x180038fe6  lea     rax, Class
0x180038fed  mov     [rsp+68h+var_38], rax
0x180038ff2  lea     rax, aIsaccountpassw_0; "IsAccountPasswordLessByPolicy"
0x180038ff9  mov     [rsp+68h+var_40], rax
0x180038ffe  mov     dword ptr [rsp+68h+var_48], 1B35h
0x180039006  jmp     short loc_18003904E
0x180039008  cmp     [rbp+arg_18], 0
0x18003900c  jz      short loc_18003905F
0x18003900e  cmp     [rbp+var_28], 0
0x180039012  jnz     short loc_18003905F
0x180039014  mov     byte ptr [r15], 1
0x180039018  jmp     short loc_18003905F
0x18003901a  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180039021  mov     ebx, 0C0070002h
0x180039026  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003902b  mov     r9, rax
0x18003902e  lea     rax, Class
0x180039035  mov     [rsp+68h+var_38], rax
0x18003903a  lea     rax, aNoCredKeyForAn; "No Cred Key for an unverified account"
0x180039041  mov     [rsp+68h+var_40], rax
0x180039046  mov     dword ptr [rsp+68h+var_48], 1B25h
0x18003904e  mov     r8d, ebx
0x180039051  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180039058  xor     ecx, ecx
0x18003905a  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18003905f  mov     rcx, [rbp+var_18]
0x180039063  test    rcx, rcx
0x180039066  jz      short loc_180039078
0x180039068  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18003906f  mov     rax, [rax+30h]
0x180039073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039078  mov     eax, ebx
0x18003907a  add     rsp, 68h
0x18003907e  pop     r15
0x180039080  pop     r14
0x180039082  pop     rdi
0x180039083  pop     rsi
0x180039084  pop     rbx
0x180039085  pop     rbp
0x180039086  retn
```
