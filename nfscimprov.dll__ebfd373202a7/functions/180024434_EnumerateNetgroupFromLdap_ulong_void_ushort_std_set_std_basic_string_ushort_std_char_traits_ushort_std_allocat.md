# EnumerateNetgroupFromLdap(ulong (*)(void *,ushort *,std::set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &),void *,ushort const *,ushort const *,ushort const *,CNfsTaskContext *)

- ea: `0x180024434`
- end: `0x18002475a`
- name: `?EnumerateNetgroupFromLdap@@YAKP6AKPEAXPEAGAEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z0PEBG44PEAVCNfsTaskContext@@@Z`
- size: `806`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `loader_planting, service_task`

## callers

- `0x180014c58`
- `0x18001516c`
- `0x1800156bc`

## callees

- `0x180014e50`
- `0x180018230`
- `0x1800182b8`
- `0x18001c028`
- `0x1800216ac`
- `0x180023b70`
- `0x180024434`
- `0x1800248e8`
- `0x1800252d8`
- `0x18002b368`
- `0x18002b4ac`
- `0x180035b02`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002450f`
- `ntdll!RtlInitUnicodeString` at `0x18002451c`
- `ntdll!RtlInitUnicodeString` at `0x18002450f`
- `ntdll!RtlInitUnicodeString` at `0x18002451c`
- `ADVAPI32!LsaNtStatusToWinError` at `0x180024535`
- `ADVAPI32!LsaNtStatusToWinError` at `0x180024535`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180024572`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800246eb`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180024572`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800246eb`
- `WLDAP32!__imp_ldap_first_entry` at `0x18002458b`
- `WLDAP32!__imp_ldap_first_entry` at `0x18002458b`
- `WLDAP32!__imp_ldap_next_entry` at `0x1800246a0`
- `WLDAP32!__imp_ldap_next_entry` at `0x1800246a0`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800246c6`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800246c6`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x1800245ca`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x1800245ff`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x1800245ca`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x1800245ff`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800245b1`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800245ee`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800245b1`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800245ee`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18002468a`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180024693`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18002468a`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180024693`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EnumerateNetgroupFromLdap(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const WCHAR *a4,
        const WCHAR *SourceString,
        __int64 a6)
{
  __int64 v8; // r13
  NTSTATUS v9; // eax
  ULONG v10; // ebx
  LDAPMessage *v11; // r12
  LDAPMessage *i; // rax
  LDAPMessage *v13; // rsi
  PWCHAR *valuesW; // rax
  PWCHAR *v15; // r15
  PWCHAR v16; // r14
  PWCHAR *v17; // rax
  PWCHAR *v18; // rdi
  ULONG v19; // r13d
  ULONG v20; // r14d
  WCHAR *v21; // r12
  __int64 v22; // r15
  LDAPMessage *res; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR *v25; // [rsp+38h] [rbp-C8h]
  LDAP *v26; // [rsp+40h] [rbp-C0h] BYREF
  ULONG LdapError[2]; // [rsp+48h] [rbp-B8h]
  int v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  __int64 v30; // [rsp+60h] [rbp-A0h]
  _BYTE v31[16]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v32; // [rsp+78h] [rbp-88h]
  PWCHAR *v33; // [rsp+80h] [rbp-80h]
  struct _UNICODE_STRING v34; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  LDAP *ld[68]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v37[3]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v8 = a2;
  v30 = a2;
  v32 = a6;
  v37[0] = L"cn";
  v37[1] = L"nisNetgroupTriple";
  v37[2] = 0;
  res = 0;
  DestinationString = 0;
  v34 = 0;
  std::set<std::wstring>::set<std::wstring>(v31);
  v26 = 0;
  *(_QWORD *)LdapError = 30;
  v29 = 0;
  v28 = 1000;
  memset_0(ld, 0, 0x218u);
  if ( a4 && *a4 )
  {
    RtlInitUnicodeString(&DestinationString, a4);
    RtlInitUnicodeString(&v34, SourceString);
    v9 = NfsConnectLdap(ld, &DestinationString, &v34);
    v10 = LsaNtStatusToWinError(v9);
    if ( !v10 )
    {
      v26 = ld[0];
      if ( !InitNetgroupPagedSearch(a3, v37, (unsigned __int16 *)ld[1], (struct CLdapSearch *)&v26) )
        v10 = LdapMapErrorToWin32(LdapError[1]);
    }
    while ( (unsigned int)CLdapSearch::GetSearchResults((CLdapSearch *)&v26, &res) )
    {
      v11 = res;
      for ( i = ldap_first_entry(ld[0], res); ; i = ldap_next_entry(ld[0], v13) )
      {
        v13 = i;
        if ( !i )
          break;
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::clear(v31);
        valuesW = ldap_get_valuesW(ld[0], v13, (const PWSTR)L"cn");
        v15 = valuesW;
        v33 = valuesW;
        if ( !valuesW || !ldap_count_valuesW(valuesW) )
        {
          v10 = 13;
          break;
        }
        v16 = *v15;
        v25 = *v15;
        v17 = ldap_get_valuesW(ld[0], v13, (const PWSTR)L"nisNetgroupTriple");
        v18 = v17;
        if ( v17 )
        {
          v19 = ldap_count_valuesW(v17);
          v20 = 0;
          if ( v19 )
          {
            v21 = v25;
            v22 = v32;
            while ( v20 < v19 )
            {
              if ( (unsigned int)ParseHost(v18[v20], v31) )
                (*(void (__fastcall **)(__int64, __int64, PWCHAR, WCHAR *))(*(_QWORD *)v22 + 8LL))(
                  v22,
                  2147487775LL,
                  v18[v20],
                  v21);
              ++v20;
            }
            v15 = v33;
            v11 = res;
          }
          v8 = v30;
          v16 = v25;
        }
        if ( !v10 )
          v10 = EnumNetGroupCallBack(v8, v16, v31);
        if ( v18 )
          ldap_value_freeW(v18);
        ldap_value_freeW(v15);
      }
      if ( v11 )
        ldap_msgfree(v11);
    }
    if ( !v10 )
      v10 = LdapMapErrorToWin32(LdapError[1]);
    NfsDisconnectLdap(ld);
    CLdapSearch::~CLdapSearch((CLdapSearch *)&v26);
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v31);
    return v10;
  }
  else
  {
    CLdapSearch::~CLdapSearch((CLdapSearch *)&v26);
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v31);
    return 87;
  }
}

```

## disassembly

```asm
0x180024434  mov     [rsp-8+arg_0], rbx
0x180024439  push    rbp
0x18002443a  push    rsi
0x18002443b  push    rdi
0x18002443c  push    r12
0x18002443e  push    r13
0x180024440  push    r14
0x180024442  push    r15
0x180024444  lea     rbp, [rsp-1F0h]
0x18002444c  sub     rsp, 2F0h
0x180024453  mov     rax, cs:__security_cookie
0x18002445a  xor     rax, rsp
0x18002445d  mov     [rbp+220h+var_38], rax
0x180024464  mov     rbx, r9
0x180024467  mov     rdi, r8
0x18002446a  mov     r13, rdx
0x18002446d  mov     [rsp+320h+var_2C0], rdx
0x180024472  mov     rsi, [rbp+220h+SourceString]
0x180024479  mov     rax, [rbp+220h+arg_28]
0x180024480  mov     [rsp+320h+var_2A8], rax
0x180024485  lea     r15, aCn; "cn"
0x18002448c  mov     [rbp+220h+var_50], r15
0x180024493  lea     rax, aNisnetgrouptri; "nisNetgroupTriple"
0x18002449a  mov     [rbp+220h+var_48], rax
0x1800244a1  xor     r14d, r14d
0x1800244a4  mov     [rbp+220h+var_40], r14
0x1800244ab  mov     [rsp+320h+res], r14
0x1800244b0  xorps   xmm0, xmm0
0x1800244b3  movups  xmmword ptr [rbp+220h+DestinationString.Length], xmm0
0x1800244b7  xorps   xmm1, xmm1
0x1800244ba  movups  xmmword ptr [rbp+220h+var_298.Length], xmm1
0x1800244be  lea     rcx, [rsp+320h+var_2B8]
0x1800244c3  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x1800244c8  nop
0x1800244c9  mov     [rsp+320h+var_2E0], r14
0x1800244ce  mov     qword ptr [rsp+320h+LdapError], 1Eh
0x1800244d7  mov     [rsp+320h+var_2C8], r14
0x1800244dc  mov     [rsp+320h+var_2D0], 3E8h
0x1800244e4  xor     edx, edx; Val
0x1800244e6  mov     r8d, 218h; Size
0x1800244ec  lea     rcx, [rbp+220h+ld]; void *
0x1800244f0  call    memset_0
0x1800244f5  test    rbx, rbx
0x1800244f8  jz      loc_180024716
0x1800244fe  cmp     [rbx], r14w
0x180024502  jz      loc_180024716
0x180024508  mov     rdx, rbx; SourceString
0x18002450b  lea     rcx, [rbp+220h+DestinationString]; DestinationString
0x18002450f  call    cs:__imp_RtlInitUnicodeString
0x180024515  mov     rdx, rsi; SourceString
0x180024518  lea     rcx, [rbp+220h+var_298]; DestinationString
0x18002451c  call    cs:__imp_RtlInitUnicodeString
0x180024522  lea     r8, [rbp+220h+var_298]
0x180024526  lea     rdx, [rbp+220h+DestinationString]
0x18002452a  lea     rcx, [rbp+220h+ld]
0x18002452e  call    NfsConnectLdap
0x180024533  mov     ecx, eax; Status
0x180024535  call    cs:__imp_LsaNtStatusToWinError
0x18002453b  mov     ebx, eax
0x18002453d  test    eax, eax
0x18002453f  jnz     loc_1800246CC
0x180024545  mov     rdx, [rbp+220h+ld]
0x180024549  mov     [rsp+320h+var_2E0], rdx
0x18002454e  lea     r9, [rsp+320h+var_2E0]; struct CLdapSearch *
0x180024553  mov     r8, [rbp+220h+var_268]; unsigned __int16 *
0x180024557  lea     rdx, [rbp+220h+var_50]; unsigned __int16 **
0x18002455e  mov     rcx, rdi; unsigned __int16 *
0x180024561  call    ?InitNetgroupPagedSearch@@YAHPEBGPEAPEAGPEAGPEAVCLdapSearch@@@Z; InitNetgroupPagedSearch(ushort const *,ushort * *,ushort *,CLdapSearch *)
0x180024566  test    eax, eax
0x180024568  jnz     loc_1800246CC
0x18002456e  mov     ecx, [rsp+320h+LdapError+4]; LdapError
0x180024572  call    cs:__imp_LdapMapErrorToWin32
0x180024578  mov     ebx, eax
0x18002457a  jmp     loc_1800246CC
0x18002457f  mov     r12, [rsp+320h+res]
0x180024584  mov     rdx, r12; res
0x180024587  mov     rcx, [rbp+220h+ld]; ld
0x18002458b  call    cs:__imp_ldap_first_entry
0x180024591  mov     rsi, rax
0x180024594  test    rax, rax
0x180024597  jz      loc_1800246BE
0x18002459d  lea     rcx, [rsp+320h+var_2B8]
0x1800245a2  call    ?clear@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::clear(void)
0x1800245a7  mov     r8, r15; attr
0x1800245aa  mov     rdx, rsi; entry
0x1800245ad  mov     rcx, [rbp+220h+ld]; ld
0x1800245b1  call    cs:__imp_ldap_get_valuesW
0x1800245b7  mov     r15, rax
0x1800245ba  mov     [rbp+220h+var_2A0], rax
0x1800245be  test    rax, rax
0x1800245c1  jz      loc_1800246B2
0x1800245c7  mov     rcx, rax; vals
0x1800245ca  call    cs:__imp_ldap_count_valuesW
0x1800245d0  test    eax, eax
0x1800245d2  jz      loc_1800246B2
0x1800245d8  mov     r14, [r15]
0x1800245db  mov     [rsp+320h+var_2E8], r14
0x1800245e0  lea     r8, aNisnetgrouptri; "nisNetgroupTriple"
0x1800245e7  mov     rdx, rsi; entry
0x1800245ea  mov     rcx, [rbp+220h+ld]; ld
0x1800245ee  call    cs:__imp_ldap_get_valuesW
0x1800245f4  mov     rdi, rax
0x1800245f7  test    rax, rax
0x1800245fa  jz      short loc_180024669
0x1800245fc  mov     rcx, rax; vals
0x1800245ff  call    cs:__imp_ldap_count_valuesW
0x180024605  mov     r13d, eax
0x180024608  xor     r14d, r14d
0x18002460b  test    eax, eax
0x18002460d  jz      short loc_18002465F
0x18002460f  mov     r12, [rsp+320h+var_2E8]
0x180024614  mov     r15, [rsp+320h+var_2A8]
0x180024619  cmp     r14d, r13d
0x18002461c  jnb     short loc_180024656
0x18002461e  movsxd  rax, r14d
0x180024621  lea     rdx, [rsp+320h+var_2B8]
0x180024626  mov     rcx, [rdi+rax*8]
0x18002462a  call    ?ParseHost@@YAKPEAGAEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; ParseHost(ushort *,std::set<std::wstring> &)
0x18002462f  test    eax, eax
0x180024631  jz      short loc_180024651
0x180024633  mov     rax, [r15]
0x180024636  mov     r9, r12
0x180024639  movsxd  r8, r14d
0x18002463c  mov     r8, [rdi+r8*8]
0x180024640  mov     edx, 8000101Fh
0x180024645  mov     rcx, r15
0x180024648  mov     rax, [rax+8]
0x18002464c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024651  inc     r14d
0x180024654  jmp     short loc_180024619
0x180024656  mov     r15, [rbp+220h+var_2A0]
0x18002465a  mov     r12, [rsp+320h+res]
0x18002465f  mov     r13, [rsp+320h+var_2C0]
0x180024664  mov     r14, [rsp+320h+var_2E8]
0x180024669  test    ebx, ebx
0x18002466b  jnz     short loc_18002467F
0x18002466d  lea     r8, [rsp+320h+var_2B8]
0x180024672  mov     rdx, r14
0x180024675  mov     rcx, r13
0x180024678  call    ?EnumNetGroupCallBack@@YAKPEAXPEAGAEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; EnumNetGroupCallBack(void *,ushort *,std::set<std::wstring> &)
0x18002467d  mov     ebx, eax
0x18002467f  xor     r14d, r14d
0x180024682  test    rdi, rdi
0x180024685  jz      short loc_180024690
0x180024687  mov     rcx, rdi; vals
0x18002468a  call    cs:__imp_ldap_value_freeW
0x180024690  mov     rcx, r15; vals
0x180024693  call    cs:__imp_ldap_value_freeW
0x180024699  mov     rdx, rsi; entry
0x18002469c  mov     rcx, [rbp+220h+ld]; ld
0x1800246a0  call    cs:__imp_ldap_next_entry
0x1800246a6  lea     r15, aCn; "cn"
0x1800246ad  jmp     loc_180024591
0x1800246b2  mov     ebx, 0Dh
0x1800246b7  lea     r15, aCn; "cn"
0x1800246be  test    r12, r12
0x1800246c1  jz      short loc_1800246CC
0x1800246c3  mov     rcx, r12; res
0x1800246c6  call    cs:__imp_ldap_msgfree
0x1800246cc  lea     rdx, [rsp+320h+res]; struct ldapmsg **
0x1800246d1  lea     rcx, [rsp+320h+var_2E0]; this
0x1800246d6  call    ?GetSearchResults@CLdapSearch@@QEAAHPEAPEAUldapmsg@@@Z; CLdapSearch::GetSearchResults(ldapmsg * *)
0x1800246db  test    eax, eax
0x1800246dd  jnz     loc_18002457F
0x1800246e3  test    ebx, ebx
0x1800246e5  jnz     short loc_1800246F3
0x1800246e7  mov     ecx, [rsp+320h+LdapError+4]; LdapError
0x1800246eb  call    cs:__imp_LdapMapErrorToWin32
0x1800246f1  mov     ebx, eax
0x1800246f3  lea     rcx, [rbp+220h+ld]
0x1800246f7  call    NfsDisconnectLdap
0x1800246fc  nop
0x1800246fd  lea     rcx, [rsp+320h+var_2E0]; this
0x180024702  call    ??1CLdapSearch@@QEAA@XZ; CLdapSearch::~CLdapSearch(void)
0x180024707  nop
0x180024708  lea     rcx, [rsp+320h+var_2B8]
0x18002470d  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x180024712  mov     eax, ebx
0x180024714  jmp     short loc_180024730
0x180024716  lea     rcx, [rsp+320h+var_2E0]; this
0x18002471b  call    ??1CLdapSearch@@QEAA@XZ; CLdapSearch::~CLdapSearch(void)
0x180024720  nop
0x180024721  lea     rcx, [rsp+320h+var_2B8]
0x180024726  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18002472b  mov     eax, 57h ; 'W'
0x180024730  mov     rcx, [rbp+220h+var_38]
0x180024737  xor     rcx, rsp; StackCookie
0x18002473a  call    __security_check_cookie
0x18002473f  mov     rbx, [rsp+320h+arg_0]
0x180024747  add     rsp, 2F0h
0x18002474e  pop     r15
0x180024750  pop     r14
0x180024752  pop     r13
0x180024754  pop     r12
0x180024756  pop     rdi
0x180024757  pop     rsi
0x180024758  pop     rbp
0x180024759  retn
```
