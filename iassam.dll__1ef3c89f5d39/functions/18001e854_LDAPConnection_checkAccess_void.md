# LDAPConnection::checkAccess(void)

- ea: `0x18001e854`
- end: `0x18001eb1e`
- name: `?checkAccess@LDAPConnection@@IEAAKXZ`
- size: `714`
- prototype: `unsigned int __fastcall(LDAPConnection *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001eb48`

## callees

- `0x18000d59c`
- `0x18001db68`
- `0x18001e854`
- `0x180025264`
- `0x1800254a0`
- `0x18002b4a0`
- `0x18002b560`
- `0x18002e010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18001e986`
- `msvcrt!wcscat_s` at `0x18001e986`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18001ea11`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18001ea11`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001eac3`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001eac3`
- `WLDAP32!__imp_ldap_first_entry` at `0x18001ead0`
- `WLDAP32!__imp_ldap_first_entry` at `0x18001ead0`
- `WLDAP32!__imp_ldap_msgfree` at `0x18001eaf6`
- `WLDAP32!__imp_ldap_msgfree` at `0x18001eaf6`
- `WLDAP32!__imp_ldap_first_attributeW` at `0x18001eae1`
- `WLDAP32!__imp_ldap_first_attributeW` at `0x18001eae1`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18001eabb`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18001eabb`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x18001e9e5`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x18001e9e5`

## string_xrefs

- `0x18001ea71`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ LDAP ERROR in %s. Code = 0x%X \nExtended error info: %S`

## pseudocode

```c
__int64 __fastcall LDAPConnection::checkAccess(LDAPConnection *this, __int64 a2)
{
  __int64 v3; // rdi
  unsigned __int64 v4; // rdi
  PLDAPMessage *p_outvalue; // rbx
  unsigned __int64 v6; // rcx
  __int64 v7; // rcx
  unsigned __int64 v8; // rcx
  void *v9; // rsp
  void *v10; // rsp
  _DWORD *v11; // rax
  ULONG lm_returncode; // edi
  LDAP *v14; // rcx
  WCHAR *v15; // rcx
  const wchar_t *v16; // rbx
  PWSTR *v17; // rax
  ULONG v18; // ebx
  LDAPMessage *entry; // rax
  __int64 v20; // [rsp+0h] [rbp-60h] BYREF
  PZPWSTR attrs; // [rsp+20h] [rbp-40h]
  BerElement *outvalue; // [rsp+60h] [rbp+0h] BYREF
  PLDAPMessage res; // [rsp+68h] [rbp+8h] BYREF
  PLDAPMessage *v24; // [rsp+70h] [rbp+10h] BYREF
  PWSTR v25[2]; // [rsp+78h] [rbp+18h] BYREF

  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)(*((_QWORD *)this + 13) + 2 * v3) );
  v4 = 2 * v3 + 94;
  p_outvalue = 0;
  if ( !v4 )
    goto LABEL_11;
  if ( v4 > g_ulMaxStackAllocSize )
    goto LABEL_11;
  v6 = v4 + g_ulAdditionalProbeSize + 8;
  if ( v6 < v4 || !(unsigned int)VerifyStackAvailable(v6, a2) )
    goto LABEL_11;
  v7 = v4 + 23;
  if ( v4 + 23 <= v4 + 8 )
    v7 = 0xFFFFFFFFFFFFFF0LL;
  v8 = v7 & 0xFFFFFFFFFFFFFFF0uLL;
  v9 = alloca(v8);
  v10 = alloca(v8);
  p_outvalue = (PLDAPMessage *)&outvalue;
  if ( &v20 == (__int64 *)-96LL || (LODWORD(outvalue) = 1801679955, (p_outvalue = &res) == 0) )
  {
LABEL_11:
    if ( v4 + 8 >= v4 )
    {
      v11 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      if ( !v11 )
        return 8;
      *v11 = 1885431112;
      p_outvalue = (PLDAPMessage *)(v11 + 2);
    }
    if ( !p_outvalue )
      return 8;
  }
  v24 = p_outvalue;
  *(_OWORD *)p_outvalue = xmmword_180036480;
  *((_OWORD *)p_outvalue + 1) = xmmword_180036490;
  *((_OWORD *)p_outvalue + 2) = xmmword_1800364A0;
  *((_OWORD *)p_outvalue + 3) = xmmword_1800364B0;
  *((_OWORD *)p_outvalue + 4) = xmmword_1800364C0;
  *(_OWORD *)((char *)p_outvalue + 78) = *(__int128 *)((char *)&xmmword_1800364C0 + 14);
  wcscat_s((wchar_t *)p_outvalue, v4 >> 1, *((const wchar_t **)this + 13));
  v25[0] = L"CN";
  v25[1] = 0;
  res = 0;
  lm_returncode = ldap_search_ext_sW(
                    *((LDAP **)this + 11),
                    (const PWSTR)p_outvalue,
                    0,
                    (const PWSTR)L"(objectclass=*)",
                    v25,
                    1u,
                    0,
                    0,
                    &LDAPConnection::SEARCH_TIMEOUT,
                    0,
                    &res);
  if ( !lm_returncode )
    lm_returncode = res->lm_returncode;
  v14 = (LDAP *)*((_QWORD *)this + 11);
  outvalue = 0;
  if ( lm_returncode )
  {
    if ( ldap_get_optionW(v14, 51, &outvalue) )
    {
      v15 = 0;
      outvalue = 0;
    }
    else
    {
      v15 = (WCHAR *)outvalue;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v16 = L"Failed to get extended error info";
      v17 = (PWSTR *)L"Failed to get extended error info";
      if ( v15 )
        v17 = (PWSTR *)v15;
      attrs = v17;
      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ LDAP ERROR in %s. Co"
                  "de = 0x%X \n"
                  "Extended error info: %S");
      if ( outvalue )
        v16 = (const wchar_t *)outvalue;
      WPP_SF_ssDS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"ldap_search_ext_sW", lm_returncode, (__int64)v16);
      v15 = (WCHAR *)outvalue;
    }
    if ( v15 )
      ldap_memfreeW(v15);
    v18 = LdapMapErrorToWin32(lm_returncode);
  }
  else
  {
    v18 = 0;
    entry = ldap_first_entry(v14, res);
    if ( !ldap_first_attributeW(*((LDAP **)this + 11), entry, &outvalue) )
      v18 = 5;
  }
  ldap_msgfree(res);
  SafeAllocaScopeGuard::~SafeAllocaScopeGuard((SafeAllocaScopeGuard *)&v24);
  return v18;
}

```

## disassembly

```asm
0x18001e854  push    rbp
0x18001e856  push    rbx
0x18001e857  push    rsi
0x18001e858  push    rdi
0x18001e859  push    r14
0x18001e85b  sub     rsp, 90h
0x18001e862  lea     rbp, [rsp+60h]
0x18001e867  mov     rax, cs:__security_cookie
0x18001e86e  xor     rax, rbp
0x18001e871  mov     [rbp+50h+var_28], rax
0x18001e875  mov     rsi, rcx
0x18001e878  mov     rax, [rcx+68h]
0x18001e87c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001e880  xor     r14d, r14d
0x18001e883  inc     rdi
0x18001e886  cmp     [rax+rdi*2], r14w
0x18001e88b  jnz     short loc_18001E883
0x18001e88d  lea     rdi, ds:5Eh[rdi*2]
0x18001e895  mov     rbx, r14
0x18001e898  test    rdi, rdi
0x18001e89b  jz      short loc_18001E8FE
0x18001e89d  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18001e8a4  ja      short loc_18001E8FE
0x18001e8a6  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001e8ad  add     rcx, 8
0x18001e8b1  add     rcx, rdi
0x18001e8b4  cmp     rcx, rdi
0x18001e8b7  jb      short loc_18001E8FE
0x18001e8b9  call    VerifyStackAvailable
0x18001e8be  test    eax, eax
0x18001e8c0  jz      short loc_18001E8FE
0x18001e8c2  lea     rax, [rdi+8]
0x18001e8c6  lea     rcx, [rax+0Fh]
0x18001e8ca  cmp     rcx, rax
0x18001e8cd  ja      short loc_18001E8D9
0x18001e8cf  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001e8d9  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001e8dd  mov     rax, rcx
0x18001e8e0  call    _alloca_probe
0x18001e8e5  sub     rsp, rcx
0x18001e8e8  lea     rbx, [rsp+0B0h+outvalue]
0x18001e8ed  test    rbx, rbx
0x18001e8f0  jz      short loc_18001E8FE
0x18001e8f2  mov     dword ptr [rbx], 6B637453h
0x18001e8f8  add     rbx, 8
0x18001e8fc  jnz     short loc_18001E934
0x18001e8fe  lea     rcx, [rdi+8]
0x18001e902  cmp     rcx, rdi
0x18001e905  jb      short loc_18001E925
0x18001e907  mov     rax, cs:g_pfnAllocate
0x18001e90e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e913  mov     rbx, rax
0x18001e916  test    rax, rax
0x18001e919  jz      short loc_18001E92A
0x18001e91b  mov     dword ptr [rax], 70616548h
0x18001e921  add     rbx, 8
0x18001e925  test    rbx, rbx
0x18001e928  jnz     short loc_18001E934
0x18001e92a  mov     eax, 8
0x18001e92f  jmp     loc_18001EB07
0x18001e934  mov     [rbp+50h+var_40], rbx
0x18001e938  movaps  xmm0, cs:xmmword_180036480
0x18001e93f  movups  xmmword ptr [rbx], xmm0
0x18001e942  movaps  xmm1, cs:xmmword_180036490
0x18001e949  movups  xmmword ptr [rbx+10h], xmm1
0x18001e94d  movaps  xmm0, cs:xmmword_1800364A0
0x18001e954  movups  xmmword ptr [rbx+20h], xmm0
0x18001e958  movaps  xmm1, cs:xmmword_1800364B0
0x18001e95f  movups  xmmword ptr [rbx+30h], xmm1
0x18001e963  movaps  xmm0, cs:xmmword_1800364C0
0x18001e96a  movups  xmmword ptr [rbx+40h], xmm0
0x18001e96e  movups  xmm1, cs:xmmword_1800364C0+0Eh
0x18001e975  movups  xmmword ptr [rbx+4Eh], xmm1
0x18001e979  shr     rdi, 1
0x18001e97c  mov     r8, [rsi+68h]; Source
0x18001e980  mov     rdx, rdi; SizeInWords
0x18001e983  mov     rcx, rbx; Destination
0x18001e986  call    cs:__imp_wcscat_s
0x18001e98c  lea     rax, aCn; "CN"
0x18001e993  mov     [rbp+50h+var_38], rax
0x18001e997  mov     [rbp+50h+var_30], r14
0x18001e99b  mov     [rbp+50h+var_48], r14
0x18001e99f  lea     rax, [rbp+50h+var_48]
0x18001e9a3  mov     [rsp+0B0h+res], rax; res
0x18001e9a8  mov     [rsp+0B0h+SizeLimit], r14d; SizeLimit
0x18001e9ad  lea     rax, ?SEARCH_TIMEOUT@LDAPConnection@@2Ul_timeval@@A; l_timeval LDAPConnection::SEARCH_TIMEOUT
0x18001e9b4  mov     [rsp+0B0h+timeout], rax; timeout
0x18001e9b9  mov     [rsp+0B0h+ClientControls], r14; ClientControls
0x18001e9be  mov     [rsp+0B0h+ServerControls], r14; ServerControls
0x18001e9c3  mov     [rsp+0B0h+attrsonly], 1; attrsonly
0x18001e9cb  lea     rax, [rbp+50h+var_38]
0x18001e9cf  mov     [rsp+0B0h+attrs], rax; attrs
0x18001e9d4  lea     r9, filter; "(objectclass=*)"
0x18001e9db  xor     r8d, r8d; scope
0x18001e9de  mov     rdx, rbx; base
0x18001e9e1  mov     rcx, [rsi+58h]; ld
0x18001e9e5  call    cs:__imp_ldap_search_ext_sW
0x18001e9eb  mov     edi, eax
0x18001e9ed  mov     rdx, [rbp+50h+var_48]; res
0x18001e9f1  test    eax, eax
0x18001e9f3  jnz     short loc_18001E9F8
0x18001e9f5  mov     edi, [rdx+38h]
0x18001e9f8  mov     rcx, [rsi+58h]; ld
0x18001e9fc  mov     [rbp+50h+outvalue], r14
0x18001ea00  test    edi, edi
0x18001ea02  jz      loc_18001EACD
0x18001ea08  lea     r8, [rbp+50h+outvalue]; outvalue
0x18001ea0c  mov     edx, 33h ; '3'; option
0x18001ea11  call    cs:__imp_ldap_get_optionW
0x18001ea17  test    eax, eax
0x18001ea19  jz      short loc_18001EA24
0x18001ea1b  mov     rcx, r14
0x18001ea1e  mov     [rbp+50h+outvalue], rcx
0x18001ea22  jmp     short loc_18001EA28
0x18001ea24  mov     rcx, [rbp+50h+outvalue]
0x18001ea28  lea     rdx, WPP_GLOBAL_Control
0x18001ea2f  mov     rax, cs:WPP_GLOBAL_Control
0x18001ea36  cmp     rax, rdx
0x18001ea39  jz      short loc_18001EAB6
0x18001ea3b  cmp     byte ptr [rax+19h], 2
0x18001ea3f  jb      short loc_18001EAB6
0x18001ea41  test    byte ptr [rax+1Ch], 4
0x18001ea45  jz      short loc_18001EAB6
0x18001ea47  lea     rbx, aFailedToGetExt; "Failed to get extended error info"
0x18001ea4e  mov     rax, rbx
0x18001ea51  test    rcx, rcx
0x18001ea54  cmovnz  rax, rcx
0x18001ea58  mov     [rsp+0B0h+attrs], rax
0x18001ea5d  mov     r9d, edi
0x18001ea60  lea     rsi, aLdapSearchExtS; "ldap_search_ext_sW"
0x18001ea67  mov     r8, rsi
0x18001ea6a  lea     rdx, aNpssvc; "NPSSVC"
0x18001ea71  lea     rcx, aCpuPidTidNowSL_1; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18001ea78  call    WppDbgPrint
0x18001ea7d  mov     rax, [rbp+50h+outvalue]
0x18001ea81  test    rax, rax
0x18001ea84  cmovnz  rbx, rax
0x18001ea88  mov     edx, 11h
0x18001ea8d  mov     [rsp+0B0h+ServerControls], rbx; __int64
0x18001ea92  mov     [rsp+0B0h+attrsonly], edi; char
0x18001ea96  mov     [rsp+0B0h+attrs], rsi; __int64
0x18001ea9b  lea     r8, WPP_5e533440ec7237f17173738acd6b67e7_Traceguids
0x18001eaa2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eaa9  mov     rcx, [rcx+10h]; LoggerHandle
0x18001eaad  call    WPP_SF_ssDS
0x18001eab2  mov     rcx, [rbp+50h+outvalue]; Block
0x18001eab6  test    rcx, rcx
0x18001eab9  jz      short loc_18001EAC1
0x18001eabb  call    cs:__imp_ldap_memfreeW
0x18001eac1  mov     ecx, edi; LdapError
0x18001eac3  call    cs:__imp_LdapMapErrorToWin32
0x18001eac9  mov     ebx, eax
0x18001eacb  jmp     short loc_18001EAF2
0x18001eacd  mov     ebx, r14d
0x18001ead0  call    cs:__imp_ldap_first_entry
0x18001ead6  lea     r8, [rbp+50h+outvalue]; ptr
0x18001eada  mov     rdx, rax; entry
0x18001eadd  mov     rcx, [rsi+58h]; ld
0x18001eae1  call    cs:__imp_ldap_first_attributeW
0x18001eae7  mov     ecx, 5
0x18001eaec  test    rax, rax
0x18001eaef  cmovz   ebx, ecx
0x18001eaf2  mov     rcx, [rbp+50h+var_48]; res
0x18001eaf6  call    cs:__imp_ldap_msgfree
0x18001eafc  lea     rcx, [rbp+50h+var_40]; this
0x18001eb00  call    ??1SafeAllocaScopeGuard@@QEAA@XZ; SafeAllocaScopeGuard::~SafeAllocaScopeGuard(void)
0x18001eb05  mov     eax, ebx
0x18001eb07  mov     rcx, [rbp+50h+var_28]
0x18001eb0b  xor     rcx, rbp; StackCookie
0x18001eb0e  call    __security_check_cookie
0x18001eb13  lea     rsp, [rbp+30h]
0x18001eb17  pop     r14
0x18001eb19  pop     rdi
0x18001eb1a  pop     rsi
0x18001eb1b  pop     rbx
0x18001eb1c  pop     rbp
0x18001eb1d  retn
```
