# RemoveUserFromSid2NameCache(HKEY__ *,void *)

- ea: `0x18005dc18`
- end: `0x18005df9a`
- name: `?RemoveUserFromSid2NameCache@@YAJPEAUHKEY__@@PEAX@Z`
- size: `898`
- prototype: `__int64 __fastcall(HKEY hKey, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x180052358`

## callees

- `0x180006a80`
- `0x180006cb0`
- `0x180007fc0`
- `0x18000a600`
- `0x18002f620`
- `0x1800349c4`
- `0x18005c644`
- `0x18005dc18`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18005debd`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18005debd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005df6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005df6f`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18005dd84`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18005de6f`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18005dd84`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18005de6f`

## string_xrefs

- `0x18005dc7c`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005dcd8`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005dda1`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005dde7`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005de3b`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005de89`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005ded7`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005df09`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005dc92`: `FindUserInCacheBySid`
- `0x18005de4f`: `GetUserSid2NameSubKey`
- `0x18005ddc5`: `RegDeleteKey`
- `0x18005dea1`: `RegDeleteKey`

## pseudocode

```c
__int64 __fastcall RemoveUserFromSid2NameCache(HKEY hKey, void *a2)
{
  LPCWSTR v2; // rdi
  unsigned int i; // r14d
  unsigned __int16 **v4; // r12
  const unsigned __int16 *v7; // rdx
  unsigned int UserInCacheBySid; // ebx
  const char *v9; // rax
  const char *v10; // rax
  const WCHAR *v11; // rsi
  const unsigned __int16 *v12; // rcx
  const char *v13; // rax
  __int64 v14; // r8
  __int64 v15; // r10
  const char *v16; // r9
  const char *v17; // r9
  LSTATUS v18; // eax
  const char *v19; // r9
  LSTATUS v20; // eax
  const char *v21; // r9
  const char *v22; // r9
  __int64 v24; // [rsp+20h] [rbp-30h]
  HKEY hKeya; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v26; // [rsp+90h] [rbp+40h] BYREF
  LPCWSTR lpSubKey; // [rsp+A0h] [rbp+50h] BYREF
  unsigned __int16 **v28; // [rsp+A8h] [rbp+58h] BYREF

  v2 = 0;
  i = 0;
  v4 = 0;
  v26 = 0;
  lpSubKey = 0;
  hKeya = 0;
  v28 = 0;
  if ( hKey && a2 )
  {
    UserInCacheBySid = FindUserInCacheBySid(hKey, a2, &hKeya);
    if ( UserInCacheBySid == -1073741275 )
    {
      UserInCacheBySid = 0;
      goto LABEL_38;
    }
    if ( UserInCacheBySid )
    {
      v9 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserInCacheBySid, v9, 1787, "FindUserInCacheBySid", &Class);
      goto LABEL_38;
    }
    UserInCacheBySid = GetMultiStringRegVal(hKeya, v7, &v28, &v26);
    if ( UserInCacheBySid )
    {
      v10 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserInCacheBySid, v10, 1795, "GetMultiStringRegVal(AliasHashes)", &Class);
      i = v26;
      v4 = v28;
      goto LABEL_38;
    }
    v4 = v28;
    v11 = &Class;
    for ( i = v26; i; i = v26 )
    {
      if ( v2 )
      {
        ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v2);
        v2 = 0;
        lpSubKey = 0;
      }
      v12 = v4[i - 1];
      v26 = i - 1;
      if ( v12 )
      {
        UserInCacheBySid = GetUserAliasSubKey(v12, (unsigned __int16 **)&lpSubKey);
        if ( UserInCacheBySid )
        {
          v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
          LODWORD(v24) = 1810;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserInCacheBySid, v16, v24, "GetUserAliasSubKey", &Class);
LABEL_19:
          v2 = lpSubKey;
          goto LABEL_36;
        }
        v2 = lpSubKey;
        if ( RegDeleteKeyW(hKey, lpSubKey) )
        {
          v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
          LODWORD(v24) = 1818;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v14, v13, v24, "RegDeleteKey", v15);
        }
      }
    }
    UserInCacheBySid = GetUserSid2NameSubKey(a2, (unsigned __int16 **)&lpSubKey);
    if ( UserInCacheBySid )
    {
      v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      LODWORD(v24) = 1827;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserInCacheBySid, v17, v24, "GetUserSid2NameSubKey", &Class);
      goto LABEL_19;
    }
    v2 = lpSubKey;
    v18 = RegDeleteKeyW(hKey, lpSubKey);
    UserInCacheBySid = v18;
    if ( v18 )
    {
      if ( v18 > 0 )
        UserInCacheBySid = (unsigned __int16)v18 | 0xC0070000;
      if ( v2 )
        v11 = v2;
      v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      LODWORD(v24) = 1835;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserInCacheBySid, v19, v24, "RegDeleteKey", v11);
    }
    else
    {
      v20 = RegFlushKey(hKey);
      UserInCacheBySid = v20;
      if ( v20 )
      {
        if ( v20 > 0 )
          UserInCacheBySid = (unsigned __int16)v20 | 0xC0070000;
        if ( v2 )
          v11 = v2;
        v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        LODWORD(v24) = 1842;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserInCacheBySid, v21, v24, "RegFlushKey", v11);
      }
      else
      {
        UserInCacheBySid = 0;
      }
    }
  }
  else
  {
    UserInCacheBySid = -1073741811;
    v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v22, 1775, "InvalidArg(s)", &Class);
  }
LABEL_36:
  if ( v2 )
    ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v2);
LABEL_38:
  if ( hKeya )
    RegCloseKey(hKeya);
  FreeMultiStringValues(v4, i);
  return UserInCacheBySid;
}

```

## disassembly

```asm
0x18005dc18  mov     [rsp-38h+arg_8], rbx
0x18005dc1d  push    rbp
0x18005dc1e  push    rsi
0x18005dc1f  push    rdi
0x18005dc20  push    r12
0x18005dc22  push    r13
0x18005dc24  push    r14
0x18005dc26  push    r15
0x18005dc28  mov     rbp, rsp
0x18005dc2b  sub     rsp, 50h
0x18005dc2f  xor     edi, edi
0x18005dc31  xor     r14d, r14d
0x18005dc34  xor     r12d, r12d
0x18005dc37  mov     [rbp+arg_0], r14d
0x18005dc3b  mov     [rbp+lpSubKey], rdi
0x18005dc3f  mov     r13, rdx
0x18005dc42  mov     [rbp+hKey], rdi
0x18005dc46  mov     r15, rcx
0x18005dc49  mov     [rbp+arg_18], r12
0x18005dc4d  test    rcx, rcx
0x18005dc50  jz      loc_18005DF09
0x18005dc56  test    rdx, rdx
0x18005dc59  jz      loc_18005DF09
0x18005dc5f  lea     r8, [rbp+hKey]; phkResult
0x18005dc63  call    ?FindUserInCacheBySid@@YAJPEAUHKEY__@@PEAXPEAPEAU1@@Z; FindUserInCacheBySid(HKEY__ *,void *,HKEY__ * *)
0x18005dc68  mov     ebx, eax
0x18005dc6a  cmp     eax, 0C0000225h
0x18005dc6f  jnz     short loc_18005DC78
0x18005dc71  xor     ebx, ebx
0x18005dc73  jmp     loc_18005DF66
0x18005dc78  test    ebx, ebx
0x18005dc7a  jz      short loc_18005DCC1
0x18005dc7c  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005dc83  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005dc88  mov     r9, rax
0x18005dc8b  lea     rsi, Class
0x18005dc92  lea     rax, aFinduserincach; "FindUserInCacheBySid"
0x18005dc99  mov     [rsp+50h+var_20], rsi
0x18005dc9e  mov     [rsp+50h+var_28], rax
0x18005dca3  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005dcaa  mov     r8d, ebx
0x18005dcad  mov     dword ptr [rsp+50h+var_30], 6FBh
0x18005dcb5  xor     ecx, ecx
0x18005dcb7  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005dcbc  jmp     loc_18005DF66
0x18005dcc1  mov     rcx, [rbp+hKey]; HKEY
0x18005dcc5  lea     r9, [rbp+arg_0]; unsigned int *
0x18005dcc9  lea     r8, [rbp+arg_18]; unsigned __int16 ***
0x18005dccd  call    ?GetMultiStringRegVal@@YAJPEAUHKEY__@@PEBGPEAPEAPEAGPEAK@Z; GetMultiStringRegVal(HKEY__ *,ushort const *,ushort * * *,ulong *)
0x18005dcd2  mov     ebx, eax
0x18005dcd4  test    eax, eax
0x18005dcd6  jz      short loc_18005DD25
0x18005dcd8  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005dcdf  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005dce4  mov     r9, rax
0x18005dce7  lea     rsi, Class
0x18005dcee  lea     rax, aGetmultistring; "GetMultiStringRegVal(AliasHashes)"
0x18005dcf5  mov     [rsp+50h+var_20], rsi
0x18005dcfa  mov     [rsp+50h+var_28], rax
0x18005dcff  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005dd06  mov     r8d, ebx
0x18005dd09  mov     dword ptr [rsp+50h+var_30], 703h
0x18005dd11  xor     ecx, ecx
0x18005dd13  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005dd18  mov     r14d, [rbp+arg_0]
0x18005dd1c  mov     r12, [rbp+arg_18]
0x18005dd20  jmp     loc_18005DF66
0x18005dd25  mov     r12, [rbp+arg_18]
0x18005dd29  lea     rsi, Class
0x18005dd30  mov     r14d, [rbp+arg_0]
0x18005dd34  test    r14d, r14d
0x18005dd37  jz      loc_18005DE29
0x18005dd3d  test    rdi, rdi
0x18005dd40  jz      short loc_18005DD5B
0x18005dd42  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005dd49  mov     rcx, rdi
0x18005dd4c  mov     rax, [rax+30h]
0x18005dd50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dd55  xor     edi, edi
0x18005dd57  mov     [rbp+lpSubKey], rdi
0x18005dd5b  lea     eax, [r14-1]
0x18005dd5f  mov     rcx, [r12+rax*8]; unsigned __int16 *
0x18005dd63  mov     [rbp+arg_0], eax
0x18005dd66  test    rcx, rcx
0x18005dd69  jz      short loc_18005DDDE
0x18005dd6b  lea     rdx, [rbp+lpSubKey]; unsigned __int16 **
0x18005dd6f  call    ?GetUserAliasSubKey@@YAJPEBGPEAPEAG@Z; GetUserAliasSubKey(ushort const *,ushort * *)
0x18005dd74  mov     ebx, eax
0x18005dd76  test    eax, eax
0x18005dd78  jnz     short loc_18005DDE7
0x18005dd7a  mov     rdi, [rbp+lpSubKey]
0x18005dd7e  mov     rcx, r15; hKey
0x18005dd81  mov     rdx, rdi; lpSubKey
0x18005dd84  call    cs:__imp_RegDeleteKeyW
0x18005dd8a  mov     r8d, eax
0x18005dd8d  test    eax, eax
0x18005dd8f  jz      short loc_18005DDDE
0x18005dd91  jle     short loc_18005DD9E
0x18005dd93  movzx   r8d, ax
0x18005dd97  or      r8d, 0C0070000h
0x18005dd9e  test    rdi, rdi
0x18005dda1  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005dda8  mov     r10, rsi
0x18005ddab  cmovnz  r10, rdi
0x18005ddaf  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005ddb4  mov     [rsp+50h+var_20], r10
0x18005ddb9  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005ddc0  mov     r9, rax
0x18005ddc3  xor     ecx, ecx
0x18005ddc5  lea     rax, aRegdeletekey; "RegDeleteKey"
0x18005ddcc  mov     [rsp+50h+var_28], rax
0x18005ddd1  mov     dword ptr [rsp+50h+var_30], 71Ah
0x18005ddd9  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005ddde  mov     r14d, [rbp+arg_0]
0x18005dde2  jmp     loc_18005DD34
0x18005dde7  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005ddee  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005ddf3  mov     [rsp+50h+var_20], rsi
0x18005ddf8  mov     r9, rax
0x18005ddfb  lea     rax, aGetuseraliassu; "GetUserAliasSubKey"
0x18005de02  mov     [rsp+50h+var_28], rax
0x18005de07  mov     dword ptr [rsp+50h+var_30], 712h
0x18005de0f  mov     r8d, ebx
0x18005de12  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005de19  xor     ecx, ecx
0x18005de1b  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005de20  mov     rdi, [rbp+lpSubKey]
0x18005de24  jmp     loc_18005DF4E
0x18005de29  lea     rdx, [rbp+lpSubKey]; unsigned __int16 **
0x18005de2d  mov     rcx, r13; void *
0x18005de30  call    ?GetUserSid2NameSubKey@@YAJPEAXPEAPEAG@Z; GetUserSid2NameSubKey(void *,ushort * *)
0x18005de35  mov     ebx, eax
0x18005de37  test    eax, eax
0x18005de39  jz      short loc_18005DE65
0x18005de3b  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005de42  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005de47  mov     [rsp+50h+var_20], rsi
0x18005de4c  mov     r9, rax
0x18005de4f  lea     rax, aGetusersid2nam; "GetUserSid2NameSubKey"
0x18005de56  mov     [rsp+50h+var_28], rax
0x18005de5b  mov     dword ptr [rsp+50h+var_30], 723h
0x18005de63  jmp     short loc_18005DE0F
0x18005de65  mov     rdi, [rbp+lpSubKey]
0x18005de69  mov     rcx, r15; hKey
0x18005de6c  mov     rdx, rdi; lpSubKey
0x18005de6f  call    cs:__imp_RegDeleteKeyW
0x18005de75  mov     ebx, eax
0x18005de77  test    eax, eax
0x18005de79  jz      short loc_18005DEBA
0x18005de7b  jle     short loc_18005DE86
0x18005de7d  movzx   ebx, ax
0x18005de80  or      ebx, 0C0070000h
0x18005de86  test    rdi, rdi
0x18005de89  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005de90  cmovnz  rsi, rdi
0x18005de94  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005de99  mov     [rsp+50h+var_20], rsi
0x18005de9e  mov     r9, rax
0x18005dea1  lea     rax, aRegdeletekey; "RegDeleteKey"
0x18005dea8  mov     [rsp+50h+var_28], rax
0x18005dead  mov     dword ptr [rsp+50h+var_30], 72Bh
0x18005deb5  jmp     loc_18005DF3D
0x18005deba  mov     rcx, r15; hKey
0x18005debd  call    cs:__imp_RegFlushKey
0x18005dec3  mov     ebx, eax
0x18005dec5  test    eax, eax
0x18005dec7  jz      short loc_18005DF05
0x18005dec9  jle     short loc_18005DED4
0x18005decb  movzx   ebx, ax
0x18005dece  or      ebx, 0C0070000h
0x18005ded4  test    rdi, rdi
0x18005ded7  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005dede  cmovnz  rsi, rdi
0x18005dee2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005dee7  mov     [rsp+50h+var_20], rsi
0x18005deec  mov     r9, rax
0x18005deef  lea     rax, aRegflushkey; "RegFlushKey"
0x18005def6  mov     [rsp+50h+var_28], rax
0x18005defb  mov     dword ptr [rsp+50h+var_30], 732h
0x18005df03  jmp     short loc_18005DF3D
0x18005df05  xor     ebx, ebx
0x18005df07  jmp     short loc_18005DF4E
0x18005df09  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005df10  mov     ebx, 0C000000Dh
0x18005df15  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005df1a  mov     r9, rax
0x18005df1d  lea     rsi, Class
0x18005df24  mov     [rsp+50h+var_20], rsi
0x18005df29  lea     rax, aInvalidargS; "InvalidArg(s)"
0x18005df30  mov     [rsp+50h+var_28], rax
0x18005df35  mov     dword ptr [rsp+50h+var_30], 6EFh
0x18005df3d  mov     r8d, ebx
0x18005df40  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005df47  xor     ecx, ecx
0x18005df49  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005df4e  test    rdi, rdi
0x18005df51  jz      short loc_18005DF66
0x18005df53  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005df5a  mov     rcx, rdi
0x18005df5d  mov     rax, [rax+30h]
0x18005df61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005df66  mov     rcx, [rbp+hKey]; hKey
0x18005df6a  test    rcx, rcx
0x18005df6d  jz      short loc_18005DF75
0x18005df6f  call    cs:__imp_RegCloseKey
0x18005df75  mov     edx, r14d; unsigned int
0x18005df78  mov     rcx, r12; unsigned __int16 **
0x18005df7b  call    ?FreeMultiStringValues@@YAXPEAPEAGK@Z; FreeMultiStringValues(ushort * *,ulong)
0x18005df80  mov     eax, ebx
0x18005df82  mov     rbx, [rsp+50h+arg_8]
0x18005df8a  add     rsp, 50h
0x18005df8e  pop     r15
0x18005df90  pop     r14
0x18005df92  pop     r13
0x18005df94  pop     r12
0x18005df96  pop     rdi
0x18005df97  pop     rsi
0x18005df98  pop     rbp
0x18005df99  retn
```
