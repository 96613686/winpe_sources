# DfsReadDSObjSecDesc

- ea: `0x14005968c`
- end: `0x140059880`
- name: `DfsReadDSObjSecDesc`
- size: `500`
- prototype: `__int64 __usercall@<rax>(LDAP *ExternalHandle@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400595c8`
- `0x140059608`

## callees

- `0x140001526`
- `0x14005968c`
- `0x14005ce22`
- `0x14005ce70`

## import_xrefs

- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x14005975f`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x14005981a`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x14005983c`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x14005975f`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x14005981a`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x14005983c`
- `WLDAP32!__imp_ldap_first_entry` at `0x14005977c`
- `WLDAP32!__imp_ldap_first_entry` at `0x14005977c`
- `WLDAP32!__imp_ldap_msgfree` at `0x140059853`
- `WLDAP32!__imp_ldap_msgfree` at `0x140059853`
- `WLDAP32!__imp_ldap_value_free_len` at `0x140059809`
- `WLDAP32!__imp_ldap_value_free_len` at `0x140059809`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x14005979b`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x14005979b`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x1400597be`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x1400597be`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x140059751`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x140059751`
- `WLDAP32!__imp_ldap_value_freeW` at `0x14005982b`
- `WLDAP32!__imp_ldap_value_freeW` at `0x14005982b`

## string_xrefs

- `0x140059703`: `nTSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall DfsReadDSObjSecDesc(LDAP *ExternalHandle, WCHAR *a2, __int64 a3, _QWORD *a4, ULONG *a5)
{
  ULONG v7; // eax
  ULONG v8; // edi
  LDAPMessage *entry; // rax
  PWCHAR *valuesW; // r14
  struct berval **values_lenW; // rax
  struct berval **v12; // rsi
  void *v13; // rax
  PLDAPMessage Message; // [rsp+60h] [rbp-41h] BYREF
  PWSTR attr[2]; // [rsp+68h] [rbp-39h] BYREF
  _QWORD v17[3]; // [rsp+78h] [rbp-29h] BYREF
  char v18; // [rsp+90h] [rbp-11h]
  int v19; // [rsp+91h] [rbp-10h]
  __int16 v20; // [rsp+95h] [rbp-Ch]
  char v21; // [rsp+97h] [rbp-Ah]
  PLDAPControlW ServerControls[2]; // [rsp+98h] [rbp-9h] BYREF
  int v23; // [rsp+A8h] [rbp+7h] BYREF
  char v24; // [rsp+ACh] [rbp+Bh]

  Message = 0;
  ServerControls[1] = 0;
  attr[1] = 0;
  v17[0] = L"1.2.840.113556.1.4.801";
  v17[1] = 5;
  v17[2] = &v23;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  ServerControls[0] = (PLDAPControlW)v17;
  attr[0] = L"nTSecurityDescriptor";
  v18 = 1;
  v23 = 16909104;
  v24 = 7;
  v7 = ldap_search_ext_sW(
         ExternalHandle,
         a2,
         0,
         (const PWSTR)L"(objectClass=*)",
         attr,
         0,
         ServerControls,
         0,
         0,
         0x2710u,
         &Message);
  v8 = LdapMapErrorToWin32(v7);
  if ( !v8 )
  {
    entry = ldap_first_entry(ExternalHandle, Message);
    if ( entry && (valuesW = ldap_get_valuesW(ExternalHandle, entry, attr[0])) != 0 )
    {
      values_lenW = ldap_get_values_lenW(ExternalHandle, Message, attr[0]);
      v12 = values_lenW;
      if ( values_lenW )
      {
        v13 = malloc_0((*values_lenW)->bv_len);
        *a4 = v13;
        if ( v13 )
        {
          memcpy_0(v13, (*v12)->bv_val, (*v12)->bv_len);
          *a5 = (*v12)->bv_len;
        }
        else
        {
          v8 = 8;
        }
        ldap_value_free_len(v12);
      }
      else
      {
        v8 = LdapMapErrorToWin32(ExternalHandle->ld_errno);
      }
      ldap_value_freeW(valuesW);
    }
    else
    {
      v8 = LdapMapErrorToWin32(ExternalHandle->ld_errno);
    }
  }
  if ( Message )
    ldap_msgfree(Message);
  return v8;
}

```

## disassembly

```asm
0x14005968c  push    rbp
0x14005968e  push    rbx
0x14005968f  push    rsi
0x140059690  push    rdi
0x140059691  push    r12
0x140059693  push    r14
0x140059695  push    r15
0x140059697  lea     rbp, [rsp-1Fh]
0x14005969c  sub     rsp, 0C0h
0x1400596a3  mov     rax, cs:__security_cookie
0x1400596aa  xor     rax, rsp
0x1400596ad  mov     [rbp+4Fh+var_40], rax
0x1400596b1  mov     r12, [rbp+4Fh+arg_20]
0x1400596b5  lea     rax, a12840113556148_0; "1.2.840.113556.1.4.801"
0x1400596bc  and     [rbp+4Fh+Message], 0
0x1400596c1  mov     r15, r9
0x1400596c4  and     [rbp+4Fh+var_50], 0
0x1400596c9  lea     r9, SearchFilter; "(objectClass=*)"
0x1400596d0  and     [rbp+4Fh+var_80], 0
0x1400596d5  xor     r8d, r8d; scope
0x1400596d8  mov     [rbp+4Fh+var_78], rax
0x1400596dc  mov     rbx, rcx
0x1400596df  lea     rax, [rbp+4Fh+var_48]
0x1400596e3  mov     [rbp+4Fh+var_70], 5
0x1400596eb  mov     [rbp+4Fh+var_68], rax
0x1400596ef  xor     eax, eax
0x1400596f1  mov     [rbp+4Fh+var_5F], eax
0x1400596f4  mov     [rbp+4Fh+var_5B], ax
0x1400596f8  mov     [rbp+4Fh+var_59], al
0x1400596fb  lea     rax, [rbp+4Fh+var_78]
0x1400596ff  mov     [rbp+4Fh+var_58], rax
0x140059703  lea     rax, aNtsecuritydesc; "nTSecurityDescriptor"
0x14005970a  mov     [rbp+4Fh+attr], rax
0x14005970e  lea     rax, [rbp+4Fh+Message]
0x140059712  mov     [rsp+0F0h+res], rax; res
0x140059717  lea     rax, [rbp+4Fh+var_58]
0x14005971b  mov     [rsp+0F0h+SizeLimit], 2710h; SizeLimit
0x140059723  and     [rsp+0F0h+var_B0], 0
0x140059729  and     [rsp+0F0h+var_B8], 0
0x14005972f  mov     [rsp+0F0h+ServerControls], rax; ServerControls
0x140059734  lea     rax, [rbp+4Fh+attr]
0x140059738  and     [rsp+0F0h+var_C8], 0
0x14005973d  mov     [rsp+0F0h+attrs], rax; attrs
0x140059742  mov     [rbp+4Fh+var_60], 1
0x140059746  mov     [rbp+4Fh+var_48], 1020330h
0x14005974d  mov     [rbp+4Fh+var_44], 7
0x140059751  call    cs:__imp_ldap_search_ext_sW
0x140059758  nop     dword ptr [rax+rax+00h]
0x14005975d  mov     ecx, eax; LdapError
0x14005975f  call    cs:__imp_LdapMapErrorToWin32
0x140059766  nop     dword ptr [rax+rax+00h]
0x14005976b  mov     edi, eax
0x14005976d  test    eax, eax
0x14005976f  jnz     loc_14005984A
0x140059775  mov     rdx, [rbp+4Fh+Message]; res
0x140059779  mov     rcx, rbx; ld
0x14005977c  call    cs:__imp_ldap_first_entry
0x140059783  nop     dword ptr [rax+rax+00h]
0x140059788  test    rax, rax
0x14005978b  jz      loc_140059839
0x140059791  mov     r8, [rbp+4Fh+attr]; attr
0x140059795  mov     rdx, rax; entry
0x140059798  mov     rcx, rbx; ld
0x14005979b  call    cs:__imp_ldap_get_valuesW
0x1400597a2  nop     dword ptr [rax+rax+00h]
0x1400597a7  mov     r14, rax
0x1400597aa  test    rax, rax
0x1400597ad  jz      loc_140059839
0x1400597b3  mov     r8, [rbp+4Fh+attr]; attr
0x1400597b7  mov     rcx, rbx; ExternalHandle
0x1400597ba  mov     rdx, [rbp+4Fh+Message]; Message
0x1400597be  call    cs:__imp_ldap_get_values_lenW
0x1400597c5  nop     dword ptr [rax+rax+00h]
0x1400597ca  mov     rsi, rax
0x1400597cd  test    rax, rax
0x1400597d0  jz      short loc_140059817
0x1400597d2  mov     rcx, [rax]
0x1400597d5  mov     ecx, [rcx]; Size
0x1400597d7  call    malloc_0
0x1400597dc  mov     [r15], rax
0x1400597df  test    rax, rax
0x1400597e2  jz      short loc_140059801
0x1400597e4  mov     rdx, [rsi]
0x1400597e7  mov     rcx, rax; void *
0x1400597ea  mov     r8d, [rdx]; Size
0x1400597ed  mov     rdx, [rdx+8]; Src
0x1400597f1  call    memcpy_0
0x1400597f6  mov     rax, [rsi]
0x1400597f9  mov     ecx, [rax]
0x1400597fb  mov     [r12], ecx
0x1400597ff  jmp     short loc_140059806
0x140059801  mov     edi, 8
0x140059806  mov     rcx, rsi; vals
0x140059809  call    cs:__imp_ldap_value_free_len
0x140059810  nop     dword ptr [rax+rax+00h]
0x140059815  jmp     short loc_140059828
0x140059817  mov     ecx, [rbx+74h]; LdapError
0x14005981a  call    cs:__imp_LdapMapErrorToWin32
0x140059821  nop     dword ptr [rax+rax+00h]
0x140059826  mov     edi, eax
0x140059828  mov     rcx, r14; vals
0x14005982b  call    cs:__imp_ldap_value_freeW
0x140059832  nop     dword ptr [rax+rax+00h]
0x140059837  jmp     short loc_14005984A
0x140059839  mov     ecx, [rbx+74h]; LdapError
0x14005983c  call    cs:__imp_LdapMapErrorToWin32
0x140059843  nop     dword ptr [rax+rax+00h]
0x140059848  mov     edi, eax
0x14005984a  mov     rcx, [rbp+4Fh+Message]; res
0x14005984e  test    rcx, rcx
0x140059851  jz      short loc_14005985F
0x140059853  call    cs:__imp_ldap_msgfree
0x14005985a  nop     dword ptr [rax+rax+00h]
0x14005985f  mov     eax, edi
0x140059861  mov     rcx, [rbp+4Fh+var_40]
0x140059865  xor     rcx, rsp; StackCookie
0x140059868  call    __security_check_cookie
0x14005986d  add     rsp, 0C0h
0x140059874  pop     r15
0x140059876  pop     r14
0x140059878  pop     r12
0x14005987a  pop     rdi
0x14005987b  pop     rsi
0x14005987c  pop     rbx
0x14005987d  pop     rbp
0x14005987e  retn
```
