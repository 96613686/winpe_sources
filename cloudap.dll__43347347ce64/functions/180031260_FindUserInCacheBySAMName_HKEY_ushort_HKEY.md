# FindUserInCacheBySAMName(HKEY__ *,ushort *,HKEY__ * *)

- ea: `0x180031260`
- end: `0x18003148e`
- name: `?FindUserInCacheBySAMName@@YAJPEAUHKEY__@@PEAGPEAPEAU1@@Z`
- size: `558`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned __int16 *, PHKEY phkResult)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180004e80`
- `0x18004f600`
- `0x180052978`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x180031260`
- `0x180031494`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031375`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031375`

## string_xrefs

- `0x180031297`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180031312`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18003138f`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180031421`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x1800313aa`: `RegOpenKeyExW`

## pseudocode

```c
__int64 __fastcall FindUserInCacheBySAMName(HKEY hKey, unsigned __int16 *a2, PHKEY phkResult)
{
  LPCWSTR v3; // rdi
  const UCHAR *v6; // r9
  unsigned int UserSAMNameSubKey; // ebx
  const UCHAR *v8; // rax
  bool v9; // zf
  const char *v10; // rax
  const WCHAR *v11; // rbp
  const char *v12; // rax
  __int64 v13; // r8
  const char *v14; // r9
  const char *v15; // r9
  __int64 v16; // r8
  PHKEY phkResulta; // [rsp+20h] [rbp-38h]
  PHKEY phkResultb; // [rsp+20h] [rbp-38h]
  LPCWSTR lpSubKey; // [rsp+70h] [rbp+18h] BYREF

  v3 = 0;
  lpSubKey = 0;
  if ( phkResult )
  {
    *phkResult = 0;
    if ( hKey && a2 )
    {
      UserSAMNameSubKey = GetUserSAMNameSubKey(a2, (unsigned __int16 **)&lpSubKey);
      if ( UserSAMNameSubKey )
      {
        v10 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserSAMNameSubKey, v10, 1587, "GetUserSAMNameSubKey", &Class);
        v3 = lpSubKey;
      }
      else
      {
        v3 = lpSubKey;
        UserSAMNameSubKey = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, phkResult);
        if ( UserSAMNameSubKey )
        {
          v11 = &Class;
          v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
          LODWORD(phkResulta) = 1597;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserSAMNameSubKey, v12, phkResulta, "RegOpenKeyExW", v13);
          if ( UserSAMNameSubKey - 2 <= 1 )
          {
            UserSAMNameSubKey = -1073741275;
          }
          else if ( (int)UserSAMNameSubKey > 0 )
          {
            UserSAMNameSubKey = (unsigned __int16)UserSAMNameSubKey | 0xC0070000;
          }
          if ( v3 )
            v11 = v3;
          v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
          LODWORD(phkResultb) = 1607;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserSAMNameSubKey, v14, phkResultb, "RegOpenKeyExW", v11);
        }
        else
        {
          UserSAMNameSubKey = 0;
        }
      }
    }
    else
    {
      UserSAMNameSubKey = -1073741811;
      v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v16, v15, 1581, "Invalid Arg(s)", &Class);
    }
    if ( v3 )
      ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v3);
  }
  else
  {
    v6 = "";
    UserSAMNameSubKey = -1073741811;
    while ( 1 )
    {
      v8 = v6--;
      v9 = *v6 == 92;
      if ( *v6 == 92 )
        break;
      if ( v6 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
      {
        v9 = *v6 == 92;
        break;
      }
    }
    if ( v9 )
      v6 = v8;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v6, 1573, "Invalid out arg", &Class);
  }
  return UserSAMNameSubKey;
}

```

## disassembly

```asm
0x180031260  mov     [rsp+arg_0], rbx
0x180031265  mov     [rsp+arg_8], rbp
0x18003126a  push    rsi
0x18003126b  push    rdi
0x18003126c  push    r14
0x18003126e  sub     rsp, 40h
0x180031272  xor     edi, edi
0x180031274  mov     rsi, r8
0x180031277  mov     [rsp+58h+lpSubKey], rdi
0x18003127c  mov     rax, rdx
0x18003127f  mov     rbp, rcx
0x180031282  test    r8, r8
0x180031285  jnz     short loc_1800312EA
0x180031287  mov     r8d, 0C000000Dh
0x18003128d  lea     r9, pbInput+24h; ""
0x180031294  mov     ebx, r8d
0x180031297  lea     rsi, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18003129e  mov     rax, r9
0x1800312a1  dec     r9
0x1800312a4  cmp     byte ptr [r9], 5Ch ; '\'
0x1800312a8  jz      short loc_1800312B3
0x1800312aa  cmp     r9, rsi
0x1800312ad  ja      short loc_18003129E
0x1800312af  cmp     byte ptr [r9], 5Ch ; '\'
0x1800312b3  cmovz   r9, rax
0x1800312b7  lea     rbp, Class
0x1800312be  lea     rax, aInvalidOutArg; "Invalid out arg"
0x1800312c5  mov     [rsp+58h+var_28], rbp
0x1800312ca  mov     [rsp+58h+var_30], rax
0x1800312cf  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800312d6  xor     ecx, ecx
0x1800312d8  mov     dword ptr [rsp+58h+phkResult], 625h
0x1800312e0  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800312e5  jmp     loc_180031479
0x1800312ea  mov     [r8], rdi
0x1800312ed  test    rbp, rbp
0x1800312f0  jz      loc_18003141B
0x1800312f6  test    rax, rax
0x1800312f9  jz      loc_18003141B
0x1800312ff  lea     rdx, [rsp+58h+lpSubKey]; unsigned __int16 **
0x180031304  mov     rcx, rax; unsigned __int16 *
0x180031307  call    ?GetUserSAMNameSubKey@@YAJPEBGPEAPEAG@Z; GetUserSAMNameSubKey(ushort const *,ushort * *)
0x18003130c  mov     ebx, eax
0x18003130e  test    eax, eax
0x180031310  jz      short loc_18003135C
0x180031312  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180031319  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003131e  mov     r9, rax
0x180031321  lea     rbp, Class
0x180031328  lea     rax, aGetusersamname; "GetUserSAMNameSubKey"
0x18003132f  mov     [rsp+58h+var_28], rbp
0x180031334  mov     [rsp+58h+var_30], rax
0x180031339  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180031340  mov     r8d, ebx
0x180031343  mov     dword ptr [rsp+58h+phkResult], 633h
0x18003134b  xor     ecx, ecx
0x18003134d  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180031352  mov     rdi, [rsp+58h+lpSubKey]
0x180031357  jmp     loc_180031461
0x18003135c  mov     rdi, [rsp+58h+lpSubKey]
0x180031361  mov     r9d, 20019h; samDesired
0x180031367  mov     rdx, rdi; lpSubKey
0x18003136a  mov     [rsp+58h+phkResult], rsi; phkResult
0x18003136f  xor     r8d, r8d; ulOptions
0x180031372  mov     rcx, rbp; hKey
0x180031375  call    cs:__imp_RegOpenKeyExW
0x18003137b  mov     ebx, eax
0x18003137d  test    eax, eax
0x18003137f  jz      loc_180031417
0x180031385  lea     rbp, Class
0x18003138c  test    rdi, rdi
0x18003138f  lea     rsi, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180031396  mov     r8, rbp
0x180031399  mov     rcx, rsi; char *
0x18003139c  cmovnz  r8, rdi
0x1800313a0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800313a5  mov     [rsp+58h+var_28], r8
0x1800313aa  lea     r14, aRegopenkeyexw; "RegOpenKeyExW"
0x1800313b1  mov     [rsp+58h+var_30], r14
0x1800313b6  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800313bd  mov     r9, rax
0x1800313c0  mov     dword ptr [rsp+58h+phkResult], 63Dh
0x1800313c8  mov     r8d, ebx
0x1800313cb  xor     ecx, ecx
0x1800313cd  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800313d2  lea     eax, [rbx-2]
0x1800313d5  cmp     eax, 1
0x1800313d8  jbe     short loc_1800313E9
0x1800313da  test    ebx, ebx
0x1800313dc  jle     short loc_1800313EE
0x1800313de  movzx   ebx, bx
0x1800313e1  or      ebx, 0C0070000h
0x1800313e7  jmp     short loc_1800313EE
0x1800313e9  mov     ebx, 0C0000225h
0x1800313ee  test    rdi, rdi
0x1800313f1  mov     rcx, rsi; char *
0x1800313f4  cmovnz  rbp, rdi
0x1800313f8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800313fd  mov     [rsp+58h+var_28], rbp
0x180031402  mov     r9, rax
0x180031405  mov     [rsp+58h+var_30], r14
0x18003140a  mov     r8d, ebx
0x18003140d  mov     dword ptr [rsp+58h+phkResult], 647h
0x180031415  jmp     short loc_180031453
0x180031417  xor     ebx, ebx
0x180031419  jmp     short loc_180031461
0x18003141b  mov     r8d, 0C000000Dh
0x180031421  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180031428  mov     ebx, r8d
0x18003142b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180031430  mov     r9, rax
0x180031433  lea     rbp, Class
0x18003143a  mov     [rsp+58h+var_28], rbp
0x18003143f  lea     rax, aInvalidArgS; "Invalid Arg(s)"
0x180031446  mov     [rsp+58h+var_30], rax
0x18003144b  mov     dword ptr [rsp+58h+phkResult], 62Dh
0x180031453  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18003145a  xor     ecx, ecx
0x18003145c  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180031461  test    rdi, rdi
0x180031464  jz      short loc_180031479
0x180031466  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18003146d  mov     rcx, rdi
0x180031470  mov     rax, [rax+30h]
0x180031474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031479  mov     rbp, [rsp+58h+arg_8]
0x18003147e  mov     eax, ebx
0x180031480  mov     rbx, [rsp+58h+arg_0]
0x180031485  add     rsp, 40h
0x180031489  pop     r14
0x18003148b  pop     rdi
0x18003148c  pop     rsi
0x18003148d  retn
```
