# FindUserInCacheBySid(HKEY__ *,void *,HKEY__ * *)

- ea: `0x180006a80`
- end: `0x180006ca0`
- name: `?FindUserInCacheBySid@@YAJPEAUHKEY__@@PEAXPEAPEAU1@@Z`
- size: `544`
- prototype: `__int64 __fastcall(HKEY hKey, void *, PHKEY phkResult)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180004e80`
- `0x180037240`
- `0x18004e7b0`
- `0x180052358`
- `0x18005dc18`

## callees

- `0x180006a80`
- `0x180006cb0`
- `0x180007fc0`
- `0x18000a600`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006aea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006aea`

## string_xrefs

- `0x180006b31`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180006bac`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180006bdd`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180006c18`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180006c33`: `RegOpenKeyExW`
- `0x180006bf8`: `GetUserSid2NameSubKey`

## pseudocode

```c
__int64 __fastcall FindUserInCacheBySid(HKEY hKey, void *a2, PHKEY phkResult)
{
  unsigned int UserSid2NameSubKey; // eax
  LPCWSTR v6; // rdi
  unsigned int v7; // ebx
  const UCHAR *v9; // r9
  char v10; // cl
  const UCHAR *v11; // rdx
  bool v12; // zf
  const char *v13; // r9
  const char *v14; // rax
  __int64 v15; // r8
  PHKEY phkResulta; // [rsp+20h] [rbp-38h]
  LPCWSTR lpSubKey; // [rsp+70h] [rbp+18h] BYREF

  lpSubKey = 0;
  if ( !phkResult )
  {
    v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v13, 1448, "Invalid out arg", &Class);
    return 3221225485LL;
  }
  *phkResult = 0;
  if ( !hKey || !a2 )
  {
    v9 = "";
    while ( 1 )
    {
      v10 = *(v9 - 1);
      v11 = v9--;
      v12 = v10 == 92;
      if ( v10 == 92 )
        break;
      if ( v9 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
      {
        v12 = v10 == 92;
        break;
      }
    }
    if ( v12 )
      v9 = v11;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v9, 1457, "Invalid Arg(s)", &Class);
    return 3221225485LL;
  }
  UserSid2NameSubKey = GetUserSid2NameSubKey(a2, (unsigned __int16 **)&lpSubKey);
  v6 = lpSubKey;
  v7 = UserSid2NameSubKey;
  if ( UserSid2NameSubKey )
  {
LABEL_24:
    _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v7);
    goto LABEL_7;
  }
  v7 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, phkResult);
  if ( v7 )
  {
    v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    LODWORD(phkResulta) = 1473;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v7, v14, phkResulta, "RegOpenKeyExW", v15);
    if ( v7 - 2 <= 1 )
    {
      v7 = -1073741275;
    }
    else if ( (int)v7 > 0 )
    {
      v7 = (unsigned __int16)v7 | 0xC0070000;
    }
    goto LABEL_24;
  }
  v7 = 0;
LABEL_7:
  if ( v6 )
    ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v6);
  return v7;
}

```

## disassembly

```asm
0x180006a80  push    rbp
0x180006a82  push    rsi
0x180006a83  push    r14
0x180006a85  sub     rsp, 40h
0x180006a89  xor     r14d, r14d
0x180006a8c  mov     rsi, r8
0x180006a8f  mov     [rsp+58h+lpSubKey], r14
0x180006a94  mov     rax, rdx
0x180006a97  mov     rbp, rcx
0x180006a9a  test    r8, r8
0x180006a9d  jz      loc_180006BAC
0x180006aa3  mov     [r8], r14
0x180006aa6  test    rcx, rcx
0x180006aa9  jz      short loc_180006B2A
0x180006aab  test    rdx, rdx
0x180006aae  jz      short loc_180006B2A
0x180006ab0  mov     [rsp+58h+arg_0], rbx
0x180006ab5  lea     rdx, [rsp+58h+lpSubKey]; unsigned __int16 **
0x180006aba  mov     rcx, rax; void *
0x180006abd  mov     [rsp+58h+arg_8], rdi
0x180006ac2  call    ?GetUserSid2NameSubKey@@YAJPEAXPEAPEAG@Z; GetUserSid2NameSubKey(void *,ushort * *)
0x180006ac7  mov     rdi, [rsp+58h+lpSubKey]
0x180006acc  mov     ebx, eax
0x180006ace  test    eax, eax
0x180006ad0  jnz     loc_180006BDD
0x180006ad6  mov     r9d, 20019h; samDesired
0x180006adc  mov     [rsp+58h+phkResult], rsi; phkResult
0x180006ae1  xor     r8d, r8d; ulOptions
0x180006ae4  mov     rdx, rdi; lpSubKey
0x180006ae7  mov     rcx, rbp; hKey
0x180006aea  call    cs:__imp_RegOpenKeyExW
0x180006af0  mov     ebx, eax
0x180006af2  test    eax, eax
0x180006af4  jnz     loc_180006C0E
0x180006afa  mov     ebx, r14d
0x180006afd  test    rdi, rdi
0x180006b00  jz      short loc_180006B15
0x180006b02  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180006b09  mov     rcx, rdi
0x180006b0c  mov     rax, [rax+30h]
0x180006b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b15  mov     rdi, [rsp+58h+arg_8]
0x180006b1a  mov     eax, ebx
0x180006b1c  mov     rbx, [rsp+58h+arg_0]
0x180006b21  add     rsp, 40h
0x180006b25  pop     r14
0x180006b27  pop     rsi
0x180006b28  pop     rbp
0x180006b29  retn
0x180006b2a  lea     r9, pbInput+24h; ""
0x180006b31  lea     rsi, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180006b38  movzx   ecx, byte ptr [r9-1]
0x180006b3d  mov     rdx, r9
0x180006b40  dec     r9
0x180006b43  cmp     cl, 5Ch ; '\'
0x180006b46  jz      short loc_180006B50
0x180006b48  cmp     r9, rsi
0x180006b4b  ja      short loc_180006B38
0x180006b4d  cmp     cl, 5Ch ; '\'
0x180006b50  lea     rbp, Class
0x180006b57  cmovz   r9, rdx
0x180006b5b  mov     [rsp+58h+var_28], rbp
0x180006b60  lea     rax, aInvalidArgS; "Invalid Arg(s)"
0x180006b67  mov     [rsp+58h+var_30], rax
0x180006b6c  mov     dword ptr [rsp+58h+phkResult], 5B1h
0x180006b74  mov     r8d, 0C000000Dh
0x180006b7a  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180006b81  xor     ecx, ecx
0x180006b83  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180006b88  mov     eax, 0C000000Dh
0x180006b8d  add     rsp, 40h
0x180006b91  pop     r14
0x180006b93  pop     rsi
0x180006b94  pop     rbp
0x180006b95  retn
0x180006b96  mov     r8d, ebx
0x180006b99  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180006ba0  xor     ecx, ecx
0x180006ba2  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180006ba7  jmp     loc_180006AFD
0x180006bac  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180006bb3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180006bb8  mov     r9, rax
0x180006bbb  lea     rbp, Class
0x180006bc2  mov     [rsp+58h+var_28], rbp
0x180006bc7  lea     rax, aInvalidOutArg; "Invalid out arg"
0x180006bce  mov     [rsp+58h+var_30], rax
0x180006bd3  mov     dword ptr [rsp+58h+phkResult], 5A8h
0x180006bdb  jmp     short loc_180006B74
0x180006bdd  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180006be4  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180006be9  mov     r9, rax
0x180006bec  lea     rbp, Class
0x180006bf3  mov     [rsp+58h+var_28], rbp
0x180006bf8  lea     rax, aGetusersid2nam; "GetUserSid2NameSubKey"
0x180006bff  mov     [rsp+58h+var_30], rax
0x180006c04  mov     dword ptr [rsp+58h+phkResult], 5B7h
0x180006c0c  jmp     short loc_180006B96
0x180006c0e  lea     rbp, Class
0x180006c15  test    rdi, rdi
0x180006c18  lea     rsi, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180006c1f  mov     r8, rbp
0x180006c22  mov     rcx, rsi; char *
0x180006c25  cmovnz  r8, rdi
0x180006c29  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180006c2e  mov     [rsp+58h+var_28], r8
0x180006c33  lea     r14, aRegopenkeyexw; "RegOpenKeyExW"
0x180006c3a  mov     [rsp+58h+var_30], r14
0x180006c3f  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180006c46  mov     r9, rax
0x180006c49  mov     dword ptr [rsp+58h+phkResult], 5C1h
0x180006c51  mov     r8d, ebx
0x180006c54  xor     ecx, ecx
0x180006c56  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180006c5b  lea     eax, [rbx-2]
0x180006c5e  cmp     eax, 1
0x180006c61  jbe     short loc_180006C72
0x180006c63  test    ebx, ebx
0x180006c65  jle     short loc_180006C77
0x180006c67  movzx   ebx, bx
0x180006c6a  or      ebx, 0C0070000h
0x180006c70  jmp     short loc_180006C77
0x180006c72  mov     ebx, 0C0000225h
0x180006c77  test    rdi, rdi
0x180006c7a  mov     rcx, rsi; char *
0x180006c7d  cmovnz  rbp, rdi
0x180006c81  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180006c86  mov     [rsp+58h+var_28], rbp
0x180006c8b  mov     r9, rax
0x180006c8e  mov     [rsp+58h+var_30], r14
0x180006c93  mov     dword ptr [rsp+58h+phkResult], 5CBh
0x180006c9b  jmp     loc_180006B96
```
