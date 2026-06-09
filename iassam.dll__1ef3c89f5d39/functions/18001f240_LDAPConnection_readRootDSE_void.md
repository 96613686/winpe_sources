# LDAPConnection::readRootDSE(void)

- ea: `0x18001f240`
- end: `0x18001f44f`
- name: `?readRootDSE@LDAPConnection@@IEAAKXZ`
- size: `527`
- prototype: `unsigned int __fastcall(LDAPConnection *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001eb48`

## callees

- `0x180001f26`
- `0x18000342c`
- `0x18001db68`
- `0x18001f240`
- `0x1800254a0`

## import_xrefs

- `WLDAP32!__imp_ldap_get_optionW` at `0x18001f2df`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18001f2df`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001f39b`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001f39b`
- `WLDAP32!__imp_ldap_first_entry` at `0x18001f3a6`
- `WLDAP32!__imp_ldap_first_entry` at `0x18001f3a6`
- `WLDAP32!__imp_ldap_msgfree` at `0x18001f393`
- `WLDAP32!__imp_ldap_msgfree` at `0x18001f42e`
- `WLDAP32!__imp_ldap_msgfree` at `0x18001f393`
- `WLDAP32!__imp_ldap_msgfree` at `0x18001f42e`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18001f3b6`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18001f3b6`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18001f389`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18001f389`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x18001f2b3`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x18001f2b3`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18001f424`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18001f424`

## string_xrefs

- `0x18001f33f`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ LDAP ERROR in %s. Code = 0x%X \nExtended error info: %S`

## pseudocode

```c
ULONG __fastcall LDAPConnection::readRootDSE(LDAP **this)
{
  ULONG lm_returncode; // edi
  LDAP *v3; // rcx
  WCHAR *v4; // rcx
  const wchar_t *v5; // rbx
  LDAPMessage *entry; // rax
  PWCHAR *valuesW; // rax
  PWCHAR *v9; // r14
  PWCHAR v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // r15
  unsigned __int128 v13; // rax
  LDAP *v14; // rax
  LDAP *v15; // rbx
  int v16; // ebx
  PWSTR v17[2]; // [rsp+60h] [rbp-10h] BYREF
  WCHAR *outvalue; // [rsp+A0h] [rbp+30h] BYREF
  LDAPMessage *res; // [rsp+A8h] [rbp+38h] BYREF

  v17[0] = (PWSTR)L"defaultNamingContext";
  v17[1] = 0;
  res = 0;
  lm_returncode = ldap_search_ext_sW(
                    this[11],
                    (const PWSTR)&base,
                    0,
                    (const PWSTR)L"(objectclass=*)",
                    v17,
                    0,
                    0,
                    0,
                    &LDAPConnection::SEARCH_TIMEOUT,
                    0,
                    &res);
  if ( !lm_returncode )
    lm_returncode = res->lm_returncode;
  v3 = this[11];
  if ( lm_returncode )
  {
    outvalue = 0;
    if ( ldap_get_optionW(v3, 51, &outvalue) )
    {
      v4 = 0;
      outvalue = 0;
    }
    else
    {
      v4 = outvalue;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v5 = L"Failed to get extended error info";
      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ LDAP ERROR in %s. Co"
                  "de = 0x%X \n"
                  "Extended error info: %S");
      if ( outvalue )
        v5 = outvalue;
      WPP_SF_ssDS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"ldap_search_ext_sW", lm_returncode, (__int64)v5);
      v4 = outvalue;
    }
    if ( v4 )
      ldap_memfreeW(v4);
    ldap_msgfree(res);
    return LdapMapErrorToWin32(lm_returncode);
  }
  else
  {
    entry = ldap_first_entry(v3, res);
    valuesW = ldap_get_valuesW(this[11], entry, (const PWSTR)L"defaultNamingContext");
    v9 = valuesW;
    if ( valuesW && (v10 = *valuesW) != 0 )
    {
      v11 = -1;
      do
        ++v11;
      while ( v10[v11] );
      v12 = v11 + 1;
      v13 = (unsigned __int64)(v11 + 1) * (unsigned __int128)2uLL;
      if ( !is_mul_ok(v11 + 1, 2u) )
        *(_QWORD *)&v13 = -1;
      v14 = (LDAP *)operator new[](v13, *((const struct std::nothrow_t **)&v13 + 1));
      v15 = v14;
      if ( v14 )
        memcpy_0(v14, v10, 2 * v12);
      this[13] = v15;
      v16 = v15 == 0 ? 8 : 0;
    }
    else
    {
      v16 = 5;
    }
    ldap_value_freeW(v9);
    ldap_msgfree(res);
    return v16;
  }
}

```

## disassembly

```asm
0x18001f240  mov     r11, rsp
0x18001f243  mov     [r11+18h], rbx
0x18001f247  mov     [r11+20h], rsi
0x18001f24b  push    rbp
0x18001f24c  push    rdi
0x18001f24d  push    r12
0x18001f24f  push    r14
0x18001f251  push    r15
0x18001f253  mov     rbp, rsp
0x18001f256  sub     rsp, 70h
0x18001f25a  mov     rsi, rcx
0x18001f25d  lea     rbx, aDefaultnamingc; "defaultNamingContext"
0x18001f264  mov     [rbp+var_10], rbx
0x18001f268  xor     r12d, r12d
0x18001f26b  mov     [rbp+var_8], r12
0x18001f26f  mov     [rbp+res], r12
0x18001f273  lea     rax, [rbp+res]
0x18001f277  mov     [r11-48h], rax
0x18001f27b  mov     [r11-50h], r12d
0x18001f27f  lea     rax, ?SEARCH_TIMEOUT@LDAPConnection@@2Ul_timeval@@A; l_timeval LDAPConnection::SEARCH_TIMEOUT
0x18001f286  mov     [r11-58h], rax
0x18001f28a  mov     [r11-60h], r12
0x18001f28e  mov     [r11-68h], r12
0x18001f292  mov     [r11-70h], r12d
0x18001f296  lea     rax, [rbp+var_10]
0x18001f29a  mov     [r11-78h], rax
0x18001f29e  lea     r9, filter; "(objectclass=*)"
0x18001f2a5  xor     r8d, r8d; scope
0x18001f2a8  lea     rdx, base; base
0x18001f2af  mov     rcx, [rcx+58h]; ld
0x18001f2b3  call    cs:__imp_ldap_search_ext_sW
0x18001f2b9  mov     edi, eax
0x18001f2bb  mov     rdx, [rbp+res]; res
0x18001f2bf  test    eax, eax
0x18001f2c1  jnz     short loc_18001F2C6
0x18001f2c3  mov     edi, [rdx+38h]
0x18001f2c6  mov     rcx, [rsi+58h]; ld
0x18001f2ca  test    edi, edi
0x18001f2cc  jz      loc_18001F3A6
0x18001f2d2  mov     [rbp+outvalue], r12
0x18001f2d6  lea     r8, [rbp+outvalue]; outvalue
0x18001f2da  mov     edx, 33h ; '3'; option
0x18001f2df  call    cs:__imp_ldap_get_optionW
0x18001f2e5  test    eax, eax
0x18001f2e7  jz      short loc_18001F2F2
0x18001f2e9  mov     rcx, r12
0x18001f2ec  mov     [rbp+outvalue], rcx
0x18001f2f0  jmp     short loc_18001F2F6
0x18001f2f2  mov     rcx, [rbp+outvalue]
0x18001f2f6  lea     rdx, WPP_GLOBAL_Control
0x18001f2fd  mov     rax, cs:WPP_GLOBAL_Control
0x18001f304  cmp     rax, rdx
0x18001f307  jz      short loc_18001F384
0x18001f309  cmp     byte ptr [rax+19h], 2
0x18001f30d  jb      short loc_18001F384
0x18001f30f  test    byte ptr [rax+1Ch], 4
0x18001f313  jz      short loc_18001F384
0x18001f315  lea     rbx, aFailedToGetExt; "Failed to get extended error info"
0x18001f31c  mov     rax, rbx
0x18001f31f  test    rcx, rcx
0x18001f322  cmovnz  rax, rcx
0x18001f326  mov     [rsp+70h+var_50], rax
0x18001f32b  mov     r9d, edi
0x18001f32e  lea     rsi, aLdapSearchExtS; "ldap_search_ext_sW"
0x18001f335  mov     r8, rsi
0x18001f338  lea     rdx, aNpssvc; "NPSSVC"
0x18001f33f  lea     rcx, aCpuPidTidNowSL_1; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18001f346  call    WppDbgPrint
0x18001f34b  mov     rax, [rbp+outvalue]
0x18001f34f  test    rax, rax
0x18001f352  cmovnz  rbx, rax
0x18001f356  mov     edx, 12h
0x18001f35b  mov     [rsp+70h+var_40], rbx; __int64
0x18001f360  mov     dword ptr [rsp+70h+var_48], edi; char
0x18001f364  mov     [rsp+70h+var_50], rsi; __int64
0x18001f369  lea     r8, WPP_5e533440ec7237f17173738acd6b67e7_Traceguids
0x18001f370  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f377  mov     rcx, [rcx+10h]; LoggerHandle
0x18001f37b  call    WPP_SF_ssDS
0x18001f380  mov     rcx, [rbp+outvalue]; Block
0x18001f384  test    rcx, rcx
0x18001f387  jz      short loc_18001F38F
0x18001f389  call    cs:__imp_ldap_memfreeW
0x18001f38f  mov     rcx, [rbp+res]; res
0x18001f393  call    cs:__imp_ldap_msgfree
0x18001f399  mov     ecx, edi; LdapError
0x18001f39b  call    cs:__imp_LdapMapErrorToWin32
0x18001f3a1  jmp     loc_18001F436
0x18001f3a6  call    cs:__imp_ldap_first_entry
0x18001f3ac  mov     r8, rbx; attr
0x18001f3af  mov     rdx, rax; entry
0x18001f3b2  mov     rcx, [rsi+58h]; ld
0x18001f3b6  call    cs:__imp_ldap_get_valuesW
0x18001f3bc  mov     r14, rax
0x18001f3bf  test    rax, rax
0x18001f3c2  jz      short loc_18001F41C
0x18001f3c4  mov     rdi, [rax]
0x18001f3c7  test    rdi, rdi
0x18001f3ca  jz      short loc_18001F41C
0x18001f3cc  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001f3d0  mov     rcx, r8
0x18001f3d3  inc     rcx
0x18001f3d6  cmp     [rdi+rcx*2], r12w
0x18001f3db  jnz     short loc_18001F3D3
0x18001f3dd  lea     r15, [rcx+1]
0x18001f3e1  mov     eax, 2
0x18001f3e6  mul     r15
0x18001f3e9  cmovb   rax, r8
0x18001f3ed  mov     rcx, rax; Size
0x18001f3f0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001f3f5  mov     rbx, rax
0x18001f3f8  test    rax, rax
0x18001f3fb  jz      short loc_18001F40C
0x18001f3fd  lea     r8, [r15+r15]; Size
0x18001f401  mov     rdx, rdi; Src
0x18001f404  mov     rcx, rax; void *
0x18001f407  call    memcpy_0
0x18001f40c  mov     [rsi+68h], rbx
0x18001f410  neg     rbx
0x18001f413  sbb     ebx, ebx
0x18001f415  not     ebx
0x18001f417  and     ebx, 8
0x18001f41a  jmp     short loc_18001F421
0x18001f41c  mov     ebx, 5
0x18001f421  mov     rcx, r14; vals
0x18001f424  call    cs:__imp_ldap_value_freeW
0x18001f42a  mov     rcx, [rbp+res]; res
0x18001f42e  call    cs:__imp_ldap_msgfree
0x18001f434  mov     eax, ebx
0x18001f436  lea     r11, [rsp+70h+var_s0]
0x18001f43b  mov     rbx, [r11+40h]
0x18001f43f  mov     rsi, [r11+48h]
0x18001f443  mov     rsp, r11
0x18001f446  pop     r15
0x18001f448  pop     r14
0x18001f44a  pop     r12
0x18001f44c  pop     rdi
0x18001f44d  pop     rbp
0x18001f44e  retn
```
