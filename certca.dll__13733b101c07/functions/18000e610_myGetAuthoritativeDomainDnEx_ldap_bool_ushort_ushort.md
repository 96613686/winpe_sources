# myGetAuthoritativeDomainDnEx(ldap *,bool,ushort * *,ushort * *)

- ea: `0x18000e610`
- end: `0x18000e9a8`
- name: `?myGetAuthoritativeDomainDnEx@@YAJPEAUldap@@_NPEAPEAG2@Z`
- size: `920`
- prototype: `__int64 __fastcall(LDAP *ld, __int64, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000e52c`

## callees

- `0x180008610`
- `0x18000a3b0`
- `0x18000d520`
- `0x18000e610`
- `0x1800115cc`
- `0x1800382c0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000e87c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e87c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e938`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e941`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e938`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e941`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18000e6e3`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18000e70f`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18000e6e3`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18000e70f`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18000e72d`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18000e72d`
- `WLDAP32!__imp_ldap_first_entry` at `0x18000e7b5`
- `WLDAP32!__imp_ldap_first_entry` at `0x18000e7b5`
- `WLDAP32!__imp_ldap_msgfree` at `0x18000e92f`
- `WLDAP32!__imp_ldap_msgfree` at `0x18000e92f`
- `WLDAP32!__imp_ldap_first_attributeW` at `0x18000e7eb`
- `WLDAP32!__imp_ldap_first_attributeW` at `0x18000e7eb`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000e865`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000e865`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18000e75d`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18000e8a6`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18000e75d`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18000e8a6`
- `WLDAP32!__imp_ldap_next_attributeW` at `0x18000e8b6`
- `WLDAP32!__imp_ldap_next_attributeW` at `0x18000e8b6`
- `WLDAP32!__imp_ldap_search_stW` at `0x18000e6ba`
- `WLDAP32!__imp_ldap_search_stW` at `0x18000e6ba`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000e89d`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000e89d`

## string_xrefs

- `0x18000e682`: `configurationNamingContext`
- `0x18000e833`: `configurationNamingContext`

## pseudocode

```c
__int64 __fastcall myGetAuthoritativeDomainDnEx(LDAP *ld, __int64 a2, unsigned __int16 **a3, unsigned __int16 **a4)
{
  unsigned __int16 *v7; // rsi
  unsigned __int16 *v8; // r12
  ULONG v9; // ebx
  ULONG optionW; // eax
  ULONG v11; // eax
  ULONG v12; // eax
  signed int Error; // ebx
  LDAPMessage *entry; // rax
  unsigned __int16 **v15; // rdx
  LDAPMessage *v16; // rbx
  const WCHAR *i; // rax
  WCHAR *v18; // r13
  unsigned __int16 *v19; // rax
  const OLECHAR **valuesW; // rax
  BSTR v21; // rax
  int v23[2]; // [rsp+40h] [rbp-39h] BYREF
  unsigned __int16 *outvalue; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int16 *v25; // [rsp+50h] [rbp-29h] BYREF
  unsigned __int16 *v26; // [rsp+58h] [rbp-21h] BYREF
  PLDAPMessage res; // [rsp+60h] [rbp-19h] BYREF
  struct l_timeval timeout; // [rsp+68h] [rbp-11h] BYREF
  BerElement *ptr; // [rsp+70h] [rbp-9h] BYREF
  PWSTR attrs[3]; // [rsp+78h] [rbp-1h] BYREF

  res = 0;
  ptr = 0;
  v25 = 0;
  v7 = 0;
  v26 = 0;
  v8 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a3 )
    *a3 = 0;
  attrs[2] = 0;
  attrs[0] = (PWSTR)L"defaultNamingContext";
  timeout = (struct l_timeval)120LL;
  attrs[1] = (PWSTR)L"configurationNamingContext";
  v23[0] = 0;
  v9 = ldap_search_stW(ld, 0, 0, (const PWSTR)L"objectClass=*", attrs, 0, &timeout, &res);
  if ( !v9 )
    goto LABEL_14;
  outvalue = 0;
  if ( ld )
  {
    optionW = ldap_get_optionW(ld, 51, &outvalue);
    if ( optionW )
    {
      CSPrintErrorLineFileData2(0, 0xAB501ADu, optionW, 0);
      outvalue = 0;
    }
    v11 = ldap_get_optionW(ld, 52, v23);
    if ( !v11 )
    {
      v12 = v23[0];
      if ( !v23[0] )
      {
        v23[0] = -2147016555;
        CSPrintErrorLineFileData2(L"LDAP_OPT_SERVER_EXT_ERROR", 0xACA01ADu, -2147016555, 0);
        v12 = v23[0];
      }
      goto LABEL_12;
    }
    CSPrintErrorLineFileData2(0, 0xABF01ADu, v11, v11);
  }
  v12 = LdapMapErrorToWin32(v9);
  v23[0] = v12;
LABEL_12:
  v23[0] = myHError(v12);
  CSPrintErrorLineFileData2(outvalue, 0xADA01ADu, v9, 0);
  if ( outvalue )
    ldap_memfreeW(outvalue);
LABEL_14:
  Error = v23[0];
  if ( v23[0] )
  {
    CSPrintErrorLineFileData2(0, 0x32F01ADu, v23[0], 0);
    goto LABEL_46;
  }
  entry = ldap_first_entry(ld, res);
  v16 = entry;
  if ( !entry )
  {
    Error = myHLdapLastError(ld, v15);
    CSPrintErrorLineFileData2(0, 0x33501ADu, Error, 0);
    goto LABEL_46;
  }
  for ( i = ldap_first_attributeW(ld, entry, &ptr); ; i = ldap_next_attributeW(ld, v16, ptr) )
  {
    v18 = (WCHAR *)i;
    if ( !i )
      break;
    if ( !a3 || (unsigned int)mylstrcmpNLSub(i, L"defaultNamingContext", -1, 1) )
    {
      if ( !a4 || (unsigned int)mylstrcmpNLSub(v18, L"configurationNamingContext", -1, 1) )
        goto LABEL_34;
      outvalue = (unsigned __int16 *)&v26;
      v19 = v8;
    }
    else
    {
      v19 = v7;
      outvalue = (unsigned __int16 *)&v25;
    }
    if ( !v19 )
    {
      valuesW = (const OLECHAR **)ldap_get_valuesW(ld, v16, v18);
      *(_QWORD *)v23 = valuesW;
      if ( valuesW )
      {
        if ( *valuesW )
        {
          v21 = SysAllocString(*valuesW);
          *(_QWORD *)outvalue = v21;
          if ( !v21 )
          {
            Error = -2147024882;
            CSPrintErrorLineFileData2(0, 0x35301ADu, -2147024882, 0);
            v7 = v25;
            v8 = v26;
            goto LABEL_46;
          }
          v7 = v25;
          v8 = v26;
          valuesW = *(const OLECHAR ***)v23;
        }
        ldap_value_freeW((PWCHAR *)valuesW);
      }
    }
LABEL_34:
    ldap_memfreeW(v18);
  }
  if ( (!a3 || v7) && (!a4 || v8) )
  {
    if ( a3 )
    {
      *a3 = v7;
      v7 = 0;
    }
    if ( a4 )
    {
      *a4 = v8;
      v8 = 0;
    }
    Error = 0;
  }
  else
  {
    Error = -2147023545;
    CSPrintErrorLineFileData2(0, 0x36201ADu, -2147023545, 0);
  }
LABEL_46:
  if ( res )
    ldap_msgfree(res);
  SysFreeString(v7);
  SysFreeString(v8);
  if ( Error == 1 )
  {
    CSPrintErrorLineFileData2(L"S_FALSE == hr", 0x65F01CAu, 1, 0);
  }
  else if ( Error >= 1 )
  {
    Error = (unsigned __int16)Error | 0x80070000;
    if ( !(_WORD)Error )
      return (unsigned int)-2147418113;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000e610  mov     [rsp-8+arg_8], rbx
0x18000e615  push    rbp
0x18000e616  push    rsi
0x18000e617  push    rdi
0x18000e618  push    r12
0x18000e61a  push    r13
0x18000e61c  push    r14
0x18000e61e  push    r15
0x18000e620  lea     rbp, [rsp-27h]
0x18000e625  sub     rsp, 0A0h
0x18000e62c  mov     rax, cs:__security_cookie
0x18000e633  xor     rax, rsp
0x18000e636  mov     [rbp+57h+var_40], rax
0x18000e63a  xor     r13d, r13d
0x18000e63d  mov     r14, r9
0x18000e640  mov     [rbp+57h+var_70], r13
0x18000e644  mov     rdi, r8
0x18000e647  mov     [rbp+57h+ptr], r13
0x18000e64b  mov     r15, rcx
0x18000e64e  mov     [rbp+57h+var_80], r13
0x18000e652  mov     esi, r13d
0x18000e655  mov     [rbp+57h+var_78], r13
0x18000e659  mov     r12d, r13d
0x18000e65c  test    r9, r9
0x18000e65f  jz      short loc_18000E664
0x18000e661  mov     [r9], r13
0x18000e664  test    rdi, rdi
0x18000e667  jz      short loc_18000E66C
0x18000e669  mov     [r8], r13
0x18000e66c  lea     rax, aDefaultnamingc; "defaultNamingContext"
0x18000e673  mov     [rbp+57h+var_48], r13
0x18000e677  mov     [rbp+57h+var_58], rax
0x18000e67b  lea     r9, aObjectclass; "objectClass=*"
0x18000e682  lea     rax, aConfigurationn; "configurationNamingContext"
0x18000e689  mov     qword ptr [rbp+57h+var_68.tv_sec], 78h ; 'x'
0x18000e691  mov     [rbp+57h+var_50], rax
0x18000e695  xor     r8d, r8d; scope
0x18000e698  lea     rax, [rbp+57h+var_70]
0x18000e69c  xor     edx, edx; base
0x18000e69e  mov     [rsp+0D0h+res], rax; res
0x18000e6a3  lea     rax, [rbp+57h+var_68]
0x18000e6a7  mov     [rsp+0D0h+timeout], rax; timeout
0x18000e6ac  lea     rax, [rbp+57h+var_58]
0x18000e6b0  mov     [rsp+0D0h+attrsonly], r13d; attrsonly
0x18000e6b5  mov     [rsp+0D0h+attrs], rax; attrs
0x18000e6ba  call    cs:__imp_ldap_search_stW
0x18000e6c0  mov     [rbp+57h+var_90], r13d
0x18000e6c4  mov     ebx, eax
0x18000e6c6  test    eax, eax
0x18000e6c8  jz      loc_18000E763
0x18000e6ce  mov     [rbp+57h+outvalue], r13
0x18000e6d2  test    r15, r15
0x18000e6d5  jz      short loc_18000E72B
0x18000e6d7  lea     r8, [rbp+57h+outvalue]; outvalue
0x18000e6db  mov     edx, 33h ; '3'; option
0x18000e6e0  mov     rcx, r15; ld
0x18000e6e3  call    cs:__imp_ldap_get_optionW
0x18000e6e9  test    eax, eax
0x18000e6eb  jz      short loc_18000E703
0x18000e6ed  xor     r9d, r9d; int
0x18000e6f0  mov     r8d, eax; int
0x18000e6f3  mov     edx, 0AB501ADh; unsigned int
0x18000e6f8  xor     ecx, ecx; unsigned __int16 *
0x18000e6fa  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000e6ff  mov     [rbp+57h+outvalue], r13
0x18000e703  lea     r8, [rbp+57h+var_90]; outvalue
0x18000e707  mov     edx, 34h ; '4'; option
0x18000e70c  mov     rcx, r15; ld
0x18000e70f  call    cs:__imp_ldap_get_optionW
0x18000e715  test    eax, eax
0x18000e717  jz      short loc_18000E781
0x18000e719  mov     r9d, eax; int
0x18000e71c  mov     r8d, eax; int
0x18000e71f  mov     edx, 0ABF01ADh; unsigned int
0x18000e724  xor     ecx, ecx; unsigned __int16 *
0x18000e726  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000e72b  mov     ecx, ebx; LdapError
0x18000e72d  call    cs:__imp_LdapMapErrorToWin32
0x18000e733  mov     [rbp+57h+var_90], eax
0x18000e736  mov     ecx, eax; int
0x18000e738  call    ?myHError@@YAJJ@Z; myHError(long)
0x18000e73d  mov     rcx, [rbp+57h+outvalue]; unsigned __int16 *
0x18000e741  xor     r9d, r9d; int
0x18000e744  mov     r8d, ebx; int
0x18000e747  mov     [rbp+57h+var_90], eax
0x18000e74a  mov     edx, 0ADA01ADh; unsigned int
0x18000e74f  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000e754  mov     rcx, [rbp+57h+outvalue]; Block
0x18000e758  test    rcx, rcx
0x18000e75b  jz      short loc_18000E763
0x18000e75d  call    cs:__imp_ldap_memfreeW
0x18000e763  mov     ebx, [rbp+57h+var_90]
0x18000e766  test    ebx, ebx
0x18000e768  jz      short loc_18000E7AE
0x18000e76a  xor     r9d, r9d; int
0x18000e76d  mov     r8d, ebx; int
0x18000e770  mov     edx, 32F01ADh; unsigned int
0x18000e775  xor     ecx, ecx; unsigned __int16 *
0x18000e777  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000e77c  jmp     loc_18000E926
0x18000e781  mov     eax, [rbp+57h+var_90]
0x18000e784  test    eax, eax
0x18000e786  jnz     short loc_18000E736
0x18000e788  xor     r9d, r9d; int
0x18000e78b  mov     [rbp+57h+var_90], 80072095h
0x18000e792  mov     edx, 0ACA01ADh; unsigned int
0x18000e797  lea     rcx, aLdapOptServerE; "LDAP_OPT_SERVER_EXT_ERROR"
0x18000e79e  mov     r8d, 80072095h; int
0x18000e7a4  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000e7a9  mov     eax, [rbp+57h+var_90]
0x18000e7ac  jmp     short loc_18000E736
0x18000e7ae  mov     rdx, [rbp+57h+var_70]; res
0x18000e7b2  mov     rcx, r15; ld
0x18000e7b5  call    cs:__imp_ldap_first_entry
0x18000e7bb  mov     rbx, rax
0x18000e7be  mov     rcx, r15; struct ldap *
0x18000e7c1  test    rax, rax
0x18000e7c4  jnz     short loc_18000E7E4
0x18000e7c6  call    ?myHLdapLastError@@YAJPEAUldap@@PEAPEAG@Z; myHLdapLastError(ldap *,ushort * *)
0x18000e7cb  xor     r9d, r9d; int
0x18000e7ce  mov     r8d, eax; int
0x18000e7d1  mov     edx, 33501ADh; unsigned int
0x18000e7d6  xor     ecx, ecx; unsigned __int16 *
0x18000e7d8  mov     ebx, eax
0x18000e7da  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000e7df  jmp     loc_18000E926
0x18000e7e4  lea     r8, [rbp+57h+ptr]; ptr
0x18000e7e8  mov     rdx, rbx; entry
0x18000e7eb  call    cs:__imp_ldap_first_attributeW
0x18000e7f1  mov     r13, rax
0x18000e7f4  test    rax, rax
0x18000e7f7  jz      loc_18000E8E2
0x18000e7fd  test    rdi, rdi
0x18000e800  jz      short loc_18000E82B
0x18000e802  mov     r9b, 1; bool
0x18000e805  lea     rdx, aDefaultnamingc; "defaultNamingContext"
0x18000e80c  mov     r8d, 0FFFFFFFFh; int
0x18000e812  mov     rcx, rax; lpString1
0x18000e815  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18000e81a  test    eax, eax
0x18000e81c  jnz     short loc_18000E82B
0x18000e81e  lea     rcx, [rbp+57h+var_80]
0x18000e822  mov     rax, rsi
0x18000e825  mov     [rbp+57h+outvalue], rcx
0x18000e829  jmp     short loc_18000E857
0x18000e82b  test    r14, r14
0x18000e82e  jz      short loc_18000E8A3
0x18000e830  mov     r9b, 1; bool
0x18000e833  lea     rdx, aConfigurationn; "configurationNamingContext"
0x18000e83a  mov     r8d, 0FFFFFFFFh; int
0x18000e840  mov     rcx, r13; lpString1
0x18000e843  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18000e848  test    eax, eax
0x18000e84a  jnz     short loc_18000E8A3
0x18000e84c  lea     rax, [rbp+57h+var_78]
0x18000e850  mov     [rbp+57h+outvalue], rax
0x18000e854  mov     rax, r12
0x18000e857  test    rax, rax
0x18000e85a  jnz     short loc_18000E8A3
0x18000e85c  mov     r8, r13; attr
0x18000e85f  mov     rdx, rbx; entry
0x18000e862  mov     rcx, r15; ld
0x18000e865  call    cs:__imp_ldap_get_valuesW
0x18000e86b  mov     qword ptr [rbp+57h+var_90], rax
0x18000e86f  test    rax, rax
0x18000e872  jz      short loc_18000E8A3
0x18000e874  mov     rcx, [rax]; psz
0x18000e877  test    rcx, rcx
0x18000e87a  jz      short loc_18000E89A
0x18000e87c  call    cs:__imp_SysAllocString
0x18000e882  mov     rcx, [rbp+57h+outvalue]
0x18000e886  mov     [rcx], rax
0x18000e889  test    rax, rax
0x18000e88c  jz      short loc_18000E8C1
0x18000e88e  mov     rsi, [rbp+57h+var_80]
0x18000e892  mov     r12, [rbp+57h+var_78]
0x18000e896  mov     rax, qword ptr [rbp+57h+var_90]
0x18000e89a  mov     rcx, rax; vals
0x18000e89d  call    cs:__imp_ldap_value_freeW
0x18000e8a3  mov     rcx, r13; Block
0x18000e8a6  call    cs:__imp_ldap_memfreeW
0x18000e8ac  mov     r8, [rbp+57h+ptr]; ptr
0x18000e8b0  mov     rdx, rbx; entry
0x18000e8b3  mov     rcx, r15; ld
0x18000e8b6  call    cs:__imp_ldap_next_attributeW
0x18000e8bc  jmp     loc_18000E7F1
0x18000e8c1  mov     ebx, 8007000Eh
0x18000e8c6  xor     r9d, r9d; int
0x18000e8c9  mov     r8d, ebx; int
0x18000e8cc  mov     edx, 35301ADh; unsigned int
0x18000e8d1  xor     ecx, ecx; unsigned __int16 *
0x18000e8d3  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000e8d8  mov     rsi, [rbp+57h+var_80]
0x18000e8dc  mov     r12, [rbp+57h+var_78]
0x18000e8e0  jmp     short loc_18000E926
0x18000e8e2  test    rdi, rdi
0x18000e8e5  jz      short loc_18000E8EC
0x18000e8e7  test    rsi, rsi
0x18000e8ea  jz      short loc_18000E8F6
0x18000e8ec  test    r14, r14
0x18000e8ef  jz      short loc_18000E90F
0x18000e8f1  test    r12, r12
0x18000e8f4  jnz     short loc_18000E90F
0x18000e8f6  mov     ebx, 80070547h
0x18000e8fb  xor     r9d, r9d; int
0x18000e8fe  mov     r8d, ebx; int
0x18000e901  mov     edx, 36201ADh; unsigned int
0x18000e906  xor     ecx, ecx; unsigned __int16 *
0x18000e908  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000e90d  jmp     short loc_18000E926
0x18000e90f  test    rdi, rdi
0x18000e912  jz      short loc_18000E919
0x18000e914  mov     [rdi], rsi
0x18000e917  xor     esi, esi
0x18000e919  test    r14, r14
0x18000e91c  jz      short loc_18000E924
0x18000e91e  mov     [r14], r12
0x18000e921  xor     r12d, r12d
0x18000e924  xor     ebx, ebx
0x18000e926  mov     rcx, [rbp+57h+var_70]; res
0x18000e92a  test    rcx, rcx
0x18000e92d  jz      short loc_18000E935
0x18000e92f  call    cs:__imp_ldap_msgfree
0x18000e935  mov     rcx, rsi; bstrString
0x18000e938  call    cs:__imp_SysFreeString
0x18000e93e  mov     rcx, r12; bstrString
0x18000e941  call    cs:__imp_SysFreeString
0x18000e947  cmp     ebx, 1
0x18000e94a  jnz     short loc_18000E965
0x18000e94c  xor     r9d, r9d; int
0x18000e94f  lea     rcx, aSFalseHr; "S_FALSE == hr"
0x18000e956  mov     edx, 65F01CAh; unsigned int
0x18000e95b  mov     r8d, ebx; int
0x18000e95e  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000e963  jmp     short loc_18000E97F
0x18000e965  jl      short loc_18000E97F
0x18000e967  test    ebx, ebx
0x18000e969  jle     short loc_18000E974
0x18000e96b  movzx   ebx, bx
0x18000e96e  or      ebx, 80070000h
0x18000e974  test    bx, bx
0x18000e977  mov     ecx, 8000FFFFh
0x18000e97c  cmovz   ebx, ecx
0x18000e97f  mov     eax, ebx
0x18000e981  mov     rcx, [rbp+57h+var_40]
0x18000e985  xor     rcx, rsp; StackCookie
0x18000e988  call    __security_check_cookie
0x18000e98d  mov     rbx, [rsp+0D0h+arg_8]
0x18000e995  add     rsp, 0A0h
0x18000e99c  pop     r15
0x18000e99e  pop     r14
0x18000e9a0  pop     r13
0x18000e9a2  pop     r12
0x18000e9a4  pop     rdi
0x18000e9a5  pop     rsi
0x18000e9a6  pop     rbp
0x18000e9a7  retn
```
