# myGetAuthoritativeDomainDnEx(ldap *,bool,ushort * *,ushort * *)

- ea: `0x18002ac84`
- end: `0x18002af04`
- name: `?myGetAuthoritativeDomainDnEx@@YAJPEAUldap@@_NPEAPEAG2@Z`
- size: `640`
- prototype: `__int64 __fastcall(LDAP *ld, bool, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002b07c`

## callees

- `0x1800200c0`
- `0x1800213f0`
- `0x18002ac84`
- `0x18002af0c`
- `0x18002b008`
- `0x18002b038`
- `0x180039740`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002ae1d`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ae1d`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002ad5b`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002ae6f`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002ad5b`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002ae6f`
- `WLDAP32!__imp_ldap_first_entry` at `0x18002ad6d`
- `WLDAP32!__imp_ldap_first_entry` at `0x18002ad6d`
- `WLDAP32!__imp_ldap_msgfree` at `0x18002aec3`
- `WLDAP32!__imp_ldap_msgfree` at `0x18002aec3`
- `WLDAP32!__imp_ldap_first_attributeW` at `0x18002ad94`
- `WLDAP32!__imp_ldap_first_attributeW` at `0x18002ad94`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18002ae07`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18002ae07`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18002ae47`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18002ae47`
- `WLDAP32!__imp_ldap_next_attributeW` at `0x18002ae58`
- `WLDAP32!__imp_ldap_next_attributeW` at `0x18002ae58`
- `WLDAP32!__imp_ldap_search_stW` at `0x18002ad3e`
- `WLDAP32!__imp_ldap_search_stW` at `0x18002ad3e`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18002ae3a`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18002ae3a`

## string_xrefs

- `0x18002acf5`: `configurationNamingContext`
- `0x18002add6`: `configurationNamingContext`

## pseudocode

```c
__int64 __fastcall myGetAuthoritativeDomainDnEx(LDAP *ld, char a2, unsigned __int16 **a3, unsigned __int16 **a4)
{
  WCHAR *v5; // r13
  unsigned __int16 *v8; // rsi
  unsigned __int16 *v9; // rdi
  ULONG v10; // eax
  unsigned int v11; // r8d
  unsigned int v12; // r9d
  int Error; // eax
  int v14; // ebx
  unsigned int v15; // ecx
  int v16; // edx
  LDAPMessage *v17; // rax
  unsigned __int16 **v18; // rdx
  const WCHAR *i; // rax
  WCHAR *v20; // rbx
  unsigned __int16 *v21; // rax
  const OLECHAR **valuesW; // rax
  PWCHAR *v23; // r13
  BSTR v24; // rax
  unsigned __int16 **attrs; // [rsp+20h] [rbp-59h]
  unsigned __int16 *v27; // [rsp+40h] [rbp-39h] BYREF
  unsigned __int16 *v28; // [rsp+48h] [rbp-31h] BYREF
  PLDAPMessage res; // [rsp+50h] [rbp-29h] BYREF
  l_timeval timeout; // [rsp+58h] [rbp-21h] BYREF
  BSTR *v31; // [rsp+60h] [rbp-19h]
  WCHAR *v32; // [rsp+68h] [rbp-11h]
  BerElement *ptr; // [rsp+70h] [rbp-9h] BYREF
  LDAPMessage *entry; // [rsp+78h] [rbp-1h]
  PWSTR v35[3]; // [rsp+80h] [rbp+7h] BYREF

  v5 = L"rootDomainNamingContext";
  res = 0;
  ptr = 0;
  if ( !a2 )
    v5 = (WCHAR *)L"defaultNamingContext";
  v27 = 0;
  v32 = v5;
  v28 = 0;
  v8 = 0;
  v9 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a3 )
    *a3 = 0;
  v35[2] = 0;
  v35[1] = (PWSTR)L"configurationNamingContext";
  v35[0] = v5;
  timeout = (l_timeval)120LL;
  v10 = ldap_search_stW(ld, 0, 0, (const PWSTR)L"objectClass=*", v35, 0, &timeout, &res);
  Error = myHLdapError3(ld, v10, v11, v12, attrs);
  v14 = Error;
  if ( Error )
  {
    v15 = 53412269;
LABEL_9:
    v16 = Error;
    goto LABEL_10;
  }
  v17 = ldap_first_entry(ld, res);
  entry = v17;
  if ( !v17 )
  {
    Error = myHLdapLastError(ld, v18);
    v14 = Error;
    v15 = 53805485;
    goto LABEL_9;
  }
  for ( i = ldap_first_attributeW(ld, v17, &ptr); ; i = ldap_next_attributeW(ld, entry, ptr) )
  {
    v20 = (WCHAR *)i;
    if ( !i )
      break;
    if ( !a3 || (unsigned int)mylstrcmpNLSub(i, v5, -1, 1u) )
    {
      if ( !a4 || (unsigned int)mylstrcmpNLSub(v20, L"configurationNamingContext", -1, 1u) )
        goto LABEL_28;
      v31 = &v28;
      v21 = v9;
    }
    else
    {
      v21 = v8;
      v31 = &v27;
    }
    if ( !v21 )
    {
      valuesW = (const OLECHAR **)ldap_get_valuesW(ld, entry, v20);
      v23 = (PWCHAR *)valuesW;
      if ( valuesW )
      {
        if ( *valuesW )
        {
          v24 = SysAllocString(*valuesW);
          *v31 = v24;
          if ( !v24 )
          {
            v14 = -2147024882;
            CSPrintErrorLineFile(0x35301ADu, -2147024882);
            v8 = v27;
            v9 = v28;
            goto LABEL_40;
          }
          v8 = v27;
          v9 = v28;
        }
        ldap_value_freeW(v23);
      }
      v5 = v32;
    }
LABEL_28:
    ldap_memfreeW(v20);
  }
  if ( (!a3 || v8) && (!a4 || v9) )
  {
    if ( a3 )
    {
      *a3 = v8;
      v8 = 0;
    }
    if ( a4 )
    {
      *a4 = v9;
      v9 = 0;
    }
    v14 = 0;
  }
  else
  {
    v14 = -2147023545;
    v15 = 56754605;
    v16 = -2147023545;
LABEL_10:
    CSPrintErrorLineFile(v15, v16);
  }
LABEL_40:
  if ( res )
    ldap_msgfree(res);
  myLdapClose(0, v8, v9);
  return myHError(v14);
}

```

## disassembly

```asm
0x18002ac84  mov     [rsp-8+arg_8], rbx
0x18002ac89  push    rbp
0x18002ac8a  push    rsi
0x18002ac8b  push    rdi
0x18002ac8c  push    r12
0x18002ac8e  push    r13
0x18002ac90  push    r14
0x18002ac92  push    r15
0x18002ac94  lea     rbp, [rsp-27h]
0x18002ac99  sub     rsp, 0A0h
0x18002aca0  mov     rax, cs:__security_cookie
0x18002aca7  xor     rax, rsp
0x18002acaa  mov     [rbp+57h+var_38], rax
0x18002acae  mov     r12, rcx
0x18002acb1  lea     rax, aDefaultnamingc; "defaultNamingContext"
0x18002acb8  xor     ecx, ecx
0x18002acba  lea     r13, aRootdomainnami; "rootDomainNamingContext"
0x18002acc1  test    dl, dl
0x18002acc3  mov     [rbp+57h+var_80], rcx
0x18002acc7  mov     r15, r9
0x18002acca  mov     [rbp+57h+ptr], rcx
0x18002acce  cmovz   r13, rax
0x18002acd2  mov     [rbp+57h+var_90], rcx
0x18002acd6  mov     [rbp+57h+var_68], r13
0x18002acda  mov     r14, r8
0x18002acdd  mov     [rbp+57h+var_88], rcx
0x18002ace1  mov     esi, ecx
0x18002ace3  mov     edi, ecx
0x18002ace5  test    r9, r9
0x18002ace8  jz      short loc_18002ACED
0x18002acea  mov     [r9], rcx
0x18002aced  test    r14, r14
0x18002acf0  jz      short loc_18002ACF5
0x18002acf2  mov     [r8], rcx
0x18002acf5  lea     rax, aConfigurationn; "configurationNamingContext"
0x18002acfc  mov     [rbp+57h+var_40], rcx
0x18002ad00  mov     [rbp+57h+var_48], rax
0x18002ad04  lea     r9, filter; "objectClass=*"
0x18002ad0b  lea     rax, [rbp+57h+var_80]
0x18002ad0f  mov     [rbp+57h+var_50], r13
0x18002ad13  mov     [rsp+0D0h+res], rax; res
0x18002ad18  xor     r8d, r8d; scope
0x18002ad1b  lea     rax, [rbp+57h+var_78]
0x18002ad1f  mov     qword ptr [rbp+57h+var_78.tv_sec], 78h ; 'x'
0x18002ad27  mov     [rsp+0D0h+timeout], rax; timeout
0x18002ad2c  xor     edx, edx; base
0x18002ad2e  mov     [rsp+0D0h+attrsonly], ecx; attrsonly
0x18002ad32  lea     rax, [rbp+57h+var_50]
0x18002ad36  mov     rcx, r12; ld
0x18002ad39  mov     [rsp+0D0h+attrs], rax; unsigned __int16 **
0x18002ad3e  call    cs:__imp_ldap_search_stW
0x18002ad44  mov     edx, eax; LdapError
0x18002ad46  mov     rcx, r12; ld
0x18002ad49  call    ?myHLdapError3@@YAJPEAUldap@@KKKPEAPEAG@Z; myHLdapError3(ldap *,ulong,ulong,ulong,ushort * *)
0x18002ad4e  mov     ebx, eax
0x18002ad50  test    eax, eax
0x18002ad52  jz      short loc_18002AD66
0x18002ad54  mov     ecx, 32F01ADh
0x18002ad59  mov     edx, eax
0x18002ad5b  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002ad61  jmp     loc_18002AEBA
0x18002ad66  mov     rdx, [rbp+57h+var_80]; res
0x18002ad6a  mov     rcx, r12; ld
0x18002ad6d  call    cs:__imp_ldap_first_entry
0x18002ad73  mov     [rbp+57h+entry], rax
0x18002ad77  mov     rcx, r12; ld
0x18002ad7a  test    rax, rax
0x18002ad7d  jnz     short loc_18002AD8D
0x18002ad7f  call    ?myHLdapLastError@@YAJPEAUldap@@PEAPEAG@Z; myHLdapLastError(ldap *,ushort * *)
0x18002ad84  mov     ebx, eax
0x18002ad86  mov     ecx, 33501ADh
0x18002ad8b  jmp     short loc_18002AD59
0x18002ad8d  lea     r8, [rbp+57h+ptr]; ptr
0x18002ad91  mov     rdx, rax; entry
0x18002ad94  call    cs:__imp_ldap_first_attributeW
0x18002ad9a  mov     rbx, rax
0x18002ad9d  test    rax, rax
0x18002ada0  jz      loc_18002AE7F
0x18002ada6  test    r14, r14
0x18002ada9  jz      short loc_18002ADCE
0x18002adab  mov     r9b, 1; bool
0x18002adae  or      r8d, 0FFFFFFFFh; int
0x18002adb2  mov     rdx, r13; unsigned __int16 *
0x18002adb5  mov     rcx, rax; lpString1
0x18002adb8  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18002adbd  test    eax, eax
0x18002adbf  jnz     short loc_18002ADCE
0x18002adc1  lea     rcx, [rbp+57h+var_90]
0x18002adc5  mov     rax, rsi
0x18002adc8  mov     [rbp+57h+var_70], rcx
0x18002adcc  jmp     short loc_18002ADF8
0x18002adce  test    r15, r15
0x18002add1  jz      short loc_18002AE44
0x18002add3  mov     r9b, 1; bool
0x18002add6  lea     rdx, aConfigurationn; "configurationNamingContext"
0x18002addd  or      r8d, 0FFFFFFFFh; int
0x18002ade1  mov     rcx, rbx; lpString1
0x18002ade4  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18002ade9  test    eax, eax
0x18002adeb  jnz     short loc_18002AE44
0x18002aded  lea     rax, [rbp+57h+var_88]
0x18002adf1  mov     [rbp+57h+var_70], rax
0x18002adf5  mov     rax, rdi
0x18002adf8  test    rax, rax
0x18002adfb  jnz     short loc_18002AE44
0x18002adfd  mov     rdx, [rbp+57h+entry]; entry
0x18002ae01  mov     r8, rbx; attr
0x18002ae04  mov     rcx, r12; ld
0x18002ae07  call    cs:__imp_ldap_get_valuesW
0x18002ae0d  mov     r13, rax
0x18002ae10  test    rax, rax
0x18002ae13  jz      short loc_18002AE40
0x18002ae15  mov     rcx, [rax]; psz
0x18002ae18  test    rcx, rcx
0x18002ae1b  jz      short loc_18002AE37
0x18002ae1d  call    cs:__imp_SysAllocString
0x18002ae23  mov     rcx, [rbp+57h+var_70]
0x18002ae27  mov     [rcx], rax
0x18002ae2a  test    rax, rax
0x18002ae2d  jz      short loc_18002AE63
0x18002ae2f  mov     rsi, [rbp+57h+var_90]
0x18002ae33  mov     rdi, [rbp+57h+var_88]
0x18002ae37  mov     rcx, r13; vals
0x18002ae3a  call    cs:__imp_ldap_value_freeW
0x18002ae40  mov     r13, [rbp+57h+var_68]
0x18002ae44  mov     rcx, rbx; Block
0x18002ae47  call    cs:__imp_ldap_memfreeW
0x18002ae4d  mov     r8, [rbp+57h+ptr]; ptr
0x18002ae51  mov     rcx, r12; ld
0x18002ae54  mov     rdx, [rbp+57h+entry]; entry
0x18002ae58  call    cs:__imp_ldap_next_attributeW
0x18002ae5e  jmp     loc_18002AD9A
0x18002ae63  mov     ebx, 8007000Eh
0x18002ae68  mov     ecx, 35301ADh
0x18002ae6d  mov     edx, ebx
0x18002ae6f  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002ae75  mov     rsi, [rbp+57h+var_90]
0x18002ae79  mov     rdi, [rbp+57h+var_88]
0x18002ae7d  jmp     short loc_18002AEBA
0x18002ae7f  test    r14, r14
0x18002ae82  jz      short loc_18002AE89
0x18002ae84  test    rsi, rsi
0x18002ae87  jz      short loc_18002AE93
0x18002ae89  test    r15, r15
0x18002ae8c  jz      short loc_18002AEA4
0x18002ae8e  test    rdi, rdi
0x18002ae91  jnz     short loc_18002AEA4
0x18002ae93  mov     ebx, 80070547h
0x18002ae98  mov     ecx, 36201ADh
0x18002ae9d  mov     edx, ebx
0x18002ae9f  jmp     loc_18002AD5B
0x18002aea4  test    r14, r14
0x18002aea7  jz      short loc_18002AEAE
0x18002aea9  mov     [r14], rsi
0x18002aeac  xor     esi, esi
0x18002aeae  test    r15, r15
0x18002aeb1  jz      short loc_18002AEB8
0x18002aeb3  mov     [r15], rdi
0x18002aeb6  xor     edi, edi
0x18002aeb8  xor     ebx, ebx
0x18002aeba  mov     rcx, [rbp+57h+var_80]; res
0x18002aebe  test    rcx, rcx
0x18002aec1  jz      short loc_18002AEC9
0x18002aec3  call    cs:__imp_ldap_msgfree
0x18002aec9  mov     r8, rdi; BSTR
0x18002aecc  mov     rdx, rsi; bstrString
0x18002aecf  xor     ecx, ecx; ld
0x18002aed1  call    ?myLdapClose@@YAXPEAUldap@@PEAG1@Z; myLdapClose(ldap *,ushort *,ushort *)
0x18002aed6  mov     ecx, ebx; int
0x18002aed8  call    ?myHError@@YAJJ@Z; myHError(long)
0x18002aedd  mov     rcx, [rbp+57h+var_38]
0x18002aee1  xor     rcx, rsp; StackCookie
0x18002aee4  call    __security_check_cookie
0x18002aee9  mov     rbx, [rsp+0D0h+arg_8]
0x18002aef1  add     rsp, 0A0h
0x18002aef8  pop     r15
0x18002aefa  pop     r14
0x18002aefc  pop     r13
0x18002aefe  pop     r12
0x18002af00  pop     rdi
0x18002af01  pop     rsi
0x18002af02  pop     rbp
0x18002af03  retn
```
