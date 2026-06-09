# NTDomain::readDomainMode(void)

- ea: `0x18001fe10`
- end: `0x18002001f`
- name: `?readDomainMode@NTDomain@@IEAAKXZ`
- size: `527`
- prototype: `unsigned int __fastcall(NTDomain *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001df3c`
- `0x18001fb74`

## callees

- `0x18001db68`
- `0x18001f608`
- `0x18001fe10`
- `0x1800254a0`

## import_xrefs

- `msvcrt!wcstoul` at `0x18001fedb`
- `msvcrt!wcstoul` at `0x18001fedb`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18001ff2b`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18001ff2b`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001ff02`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001ff02`
- `WLDAP32!__imp_ldap_first_entry` at `0x18001fea5`
- `WLDAP32!__imp_ldap_first_entry` at `0x18001fea5`
- `WLDAP32!__imp_ldap_msgfree` at `0x18001fff6`
- `WLDAP32!__imp_ldap_msgfree` at `0x18001fff6`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18001febd`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18001febd`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18001ffe8`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18001ffe8`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x18001fe82`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x18001fe82`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18001fef5`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18001fef5`

## string_xrefs

- `0x18001ff96`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ LDAP ERROR in %s. Code = 0x%X \nExtended error info: %S`

## pseudocode

```c
__int64 __fastcall NTDomain::readDomainMode(NTDomain *this)
{
  ULONG lm_returncode; // ebp
  LDAPMessage *entry; // rax
  const wchar_t **valuesW; // rax
  PWCHAR *v5; // rbx
  ULONG v6; // edi
  WCHAR *v7; // rcx
  const wchar_t *v8; // rbx
  WCHAR *outvalue; // [rsp+80h] [rbp+8h] BYREF
  LDAPMessage *res; // [rsp+88h] [rbp+10h] BYREF

  res = 0;
  lm_returncode = ldap_search_ext_sW(
                    *(LDAP **)(*((_QWORD *)this + 15) + 88LL),
                    *(const PWSTR *)(*((_QWORD *)this + 15) + 104LL),
                    0,
                    (const PWSTR)L"(objectclass=*)",
                    &off_180031310,
                    0,
                    0,
                    0,
                    &LDAPConnection::SEARCH_TIMEOUT,
                    0,
                    &res);
  if ( !lm_returncode )
    lm_returncode = res->lm_returncode;
  if ( lm_returncode )
  {
    v6 = LdapMapErrorToWin32(lm_returncode);
    outvalue = 0;
    if ( ldap_get_optionW(*(LDAP **)(*((_QWORD *)this + 15) + 88LL), 51, &outvalue) )
    {
      v7 = 0;
      outvalue = 0;
    }
    else
    {
      v7 = outvalue;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v8 = L"Failed to get extended error info";
      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ LDAP ERROR in %s. Co"
                  "de = 0x%X \n"
                  "Extended error info: %S");
      if ( outvalue )
        v8 = outvalue;
      WPP_SF_ssDS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"ldap_get_valuesW", lm_returncode, (__int64)v8);
      v7 = outvalue;
    }
    if ( v7 )
      ldap_memfreeW(v7);
  }
  else
  {
    entry = ldap_first_entry(*(LDAP **)(*((_QWORD *)this + 15) + 88LL), res);
    valuesW = (const wchar_t **)ldap_get_valuesW(
                                  *(LDAP **)(*((_QWORD *)this + 15) + 88LL),
                                  entry,
                                  (const PWSTR)L"nTMixedDomain");
    v5 = (PWCHAR *)valuesW;
    if ( valuesW && *valuesW )
    {
      v6 = 0;
      *((_DWORD *)this + 28) = 3 - (wcstoul(*valuesW, 0, 10) != 0);
    }
    else
    {
      v6 = 5;
    }
    ldap_value_freeW(v5);
  }
  ldap_msgfree(res);
  if ( v6 )
    NTDomain::closeConnection(this);
  return v6;
}

```

## disassembly

```asm
0x18001fe10  mov     r11, rsp
0x18001fe13  mov     [r11+18h], rbx
0x18001fe17  mov     [r11+20h], rbp
0x18001fe1b  push    rsi
0x18001fe1c  push    rdi
0x18001fe1d  push    r14
0x18001fe1f  sub     rsp, 60h
0x18001fe23  mov     rsi, rcx
0x18001fe26  mov     qword ptr [r11+10h], 0
0x18001fe2e  mov     rcx, [rcx+78h]
0x18001fe32  lea     rax, [r11+10h]
0x18001fe36  mov     [r11-28h], rax
0x18001fe3a  mov     [rsp+78h+SizeLimit], 0; SizeLimit
0x18001fe42  lea     rax, ?SEARCH_TIMEOUT@LDAPConnection@@2Ul_timeval@@A; l_timeval LDAPConnection::SEARCH_TIMEOUT
0x18001fe49  mov     [r11-38h], rax
0x18001fe4d  mov     qword ptr [r11-40h], 0
0x18001fe55  mov     qword ptr [r11-48h], 0
0x18001fe5d  mov     [rsp+78h+attrsonly], 0; attrsonly
0x18001fe65  lea     rax, off_180031310; "nTMixedDomain"
0x18001fe6c  mov     [r11-58h], rax
0x18001fe70  lea     r9, aObjectclass_0; "(objectclass=*)"
0x18001fe77  xor     r8d, r8d; scope
0x18001fe7a  mov     rdx, [rcx+68h]; base
0x18001fe7e  mov     rcx, [rcx+58h]; ld
0x18001fe82  call    cs:__imp_ldap_search_ext_sW
0x18001fe88  mov     ebp, eax
0x18001fe8a  mov     rdx, [rsp+78h+res]; res
0x18001fe92  test    eax, eax
0x18001fe94  jnz     short loc_18001FE99
0x18001fe96  mov     ebp, [rdx+38h]
0x18001fe99  test    ebp, ebp
0x18001fe9b  jnz     short loc_18001FF00
0x18001fe9d  mov     rcx, [rsi+78h]
0x18001fea1  mov     rcx, [rcx+58h]; ld
0x18001fea5  call    cs:__imp_ldap_first_entry
0x18001feab  mov     rcx, [rsi+78h]
0x18001feaf  lea     r8, aNtmixeddomain; "nTMixedDomain"
0x18001feb6  mov     rdx, rax; entry
0x18001feb9  mov     rcx, [rcx+58h]; ld
0x18001febd  call    cs:__imp_ldap_get_valuesW
0x18001fec3  mov     rbx, rax
0x18001fec6  test    rax, rax
0x18001fec9  jz      short loc_18001FEED
0x18001fecb  mov     rcx, [rax]; String
0x18001fece  test    rcx, rcx
0x18001fed1  jz      short loc_18001FEED
0x18001fed3  xor     edi, edi
0x18001fed5  xor     edx, edx; EndPtr
0x18001fed7  lea     r8d, [rbp+0Ah]; Radix
0x18001fedb  call    cs:__imp_wcstoul
0x18001fee1  neg     eax
0x18001fee3  sbb     ecx, ecx
0x18001fee5  add     ecx, 3
0x18001fee8  mov     [rsi+70h], ecx
0x18001feeb  jmp     short loc_18001FEF2
0x18001feed  mov     edi, 5
0x18001fef2  mov     rcx, rbx; vals
0x18001fef5  call    cs:__imp_ldap_value_freeW
0x18001fefb  jmp     loc_18001FFEE
0x18001ff00  mov     ecx, ebp; LdapError
0x18001ff02  call    cs:__imp_LdapMapErrorToWin32
0x18001ff08  mov     edi, eax
0x18001ff0a  mov     [rsp+78h+outvalue], 0
0x18001ff16  mov     rcx, [rsi+78h]
0x18001ff1a  lea     r8, [rsp+78h+outvalue]; outvalue
0x18001ff22  mov     edx, 33h ; '3'; option
0x18001ff27  mov     rcx, [rcx+58h]; ld
0x18001ff2b  call    cs:__imp_ldap_get_optionW
0x18001ff31  test    eax, eax
0x18001ff33  jz      short loc_18001FF41
0x18001ff35  xor     ecx, ecx
0x18001ff37  mov     [rsp+78h+outvalue], rcx
0x18001ff3f  jmp     short loc_18001FF49
0x18001ff41  mov     rcx, [rsp+78h+outvalue]
0x18001ff49  lea     rdx, WPP_GLOBAL_Control
0x18001ff50  mov     rax, cs:WPP_GLOBAL_Control
0x18001ff57  cmp     rax, rdx
0x18001ff5a  jz      loc_18001FFE3
0x18001ff60  cmp     byte ptr [rax+19h], 2
0x18001ff64  jb      short loc_18001FFE3
0x18001ff66  test    byte ptr [rax+1Ch], 4
0x18001ff6a  jz      short loc_18001FFE3
0x18001ff6c  lea     rbx, aFailedToGetExt; "Failed to get extended error info"
0x18001ff73  mov     rax, rbx
0x18001ff76  test    rcx, rcx
0x18001ff79  cmovnz  rax, rcx
0x18001ff7d  mov     [rsp+78h+var_58], rax
0x18001ff82  mov     r9d, ebp
0x18001ff85  lea     r14, aLdapGetValuesw; "ldap_get_valuesW"
0x18001ff8c  mov     r8, r14
0x18001ff8f  lea     rdx, aNpssvc; "NPSSVC"
0x18001ff96  lea     rcx, aCpuPidTidNowSL_1; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18001ff9d  call    WppDbgPrint
0x18001ffa2  mov     rax, [rsp+78h+outvalue]
0x18001ffaa  test    rax, rax
0x18001ffad  cmovnz  rbx, rax
0x18001ffb1  mov     edx, 11h
0x18001ffb6  mov     [rsp+78h+var_48], rbx; __int64
0x18001ffbb  mov     [rsp+78h+attrsonly], ebp; char
0x18001ffbf  mov     [rsp+78h+var_58], r14; __int64
0x18001ffc4  lea     r8, WPP_3d17ec2a460a38aa7d49725326c61fb2_Traceguids
0x18001ffcb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ffd2  mov     rcx, [rcx+10h]; LoggerHandle
0x18001ffd6  call    WPP_SF_ssDS
0x18001ffdb  mov     rcx, [rsp+78h+outvalue]; Block
0x18001ffe3  test    rcx, rcx
0x18001ffe6  jz      short loc_18001FFEE
0x18001ffe8  call    cs:__imp_ldap_memfreeW
0x18001ffee  mov     rcx, [rsp+78h+res]; res
0x18001fff6  call    cs:__imp_ldap_msgfree
0x18001fffc  test    edi, edi
0x18001fffe  jz      short loc_180020008
0x180020000  mov     rcx, rsi; this
0x180020003  call    ?closeConnection@NTDomain@@IEAAXXZ; NTDomain::closeConnection(void)
0x180020008  mov     eax, edi
0x18002000a  lea     r11, [rsp+78h+var_18]
0x18002000f  mov     rbx, [r11+30h]
0x180020013  mov     rbp, [r11+38h]
0x180020017  mov     rsp, r11
0x18002001a  pop     r14
0x18002001c  pop     rdi
0x18002001d  pop     rsi
0x18002001e  retn
```
