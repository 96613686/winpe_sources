# CLdapWrapper::SetSecurityDescriptor(wchar_t const *,cxl::SecurityDescriptor const &,ulong)

- ea: `0x1800a812c`
- end: `0x1800a82ae`
- name: `?SetSecurityDescriptor@CLdapWrapper@@QEAAJPEB_WAEBVSecurityDescriptor@cxl@@K@Z`
- size: `386`
- prototype: `int(CLdapWrapper *__hidden this, const wchar_t *, const struct SecurityDescriptor *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a3a0c`

## callees

- `0x180002f50`
- `0x180029410`
- `0x18009c888`
- `0x18009c960`
- `0x1800a812c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800a8224`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800a8224`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800a826b`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800a826b`
- `WLDAP32!__imp_ldap_modify_ext_sW` at `0x1800a825f`
- `WLDAP32!__imp_ldap_modify_ext_sW` at `0x1800a825f`

## string_xrefs

- `0x1800a81cc`: `ntSecurityDescriptor`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLdapWrapper::SetSecurityDescriptor(LDAP **this, WCHAR *a2, PSECURITY_DESCRIPTOR *a3)
{
  DWORD SecurityDescriptorLength; // eax
  ULONG v8; // eax
  signed int v9; // eax
  unsigned int v10; // ebx
  unsigned __int16 v11[2]; // [rsp+30h] [rbp-69h] BYREF
  unsigned int v12; // [rsp+34h] [rbp-65h] BYREF
  __int128 v13; // [rsp+38h] [rbp-61h] BYREF
  _QWORD v14[3]; // [rsp+48h] [rbp-51h] BYREF
  char v15; // [rsp+60h] [rbp-39h]
  int v16; // [rsp+61h] [rbp-38h]
  __int16 v17; // [rsp+65h] [rbp-34h]
  char v18; // [rsp+67h] [rbp-32h]
  __int128 v19; // [rsp+68h] [rbp-31h] BYREF
  __int64 v20; // [rsp+78h] [rbp-21h]
  _QWORD v21[3]; // [rsp+80h] [rbp-19h] BYREF
  _QWORD v22[2]; // [rsp+98h] [rbp-1h] BYREF
  PLDAPControlW ServerControls[2]; // [rsp+A8h] [rbp+Fh] BYREF
  LDAPModW *mods[2]; // [rsp+B8h] [rbp+1Fh] BYREF
  int v25; // [rsp+C8h] [rbp+2Fh] BYREF
  char v26; // [rsp+CCh] [rbp+33h]

  if ( !*this )
    return 2147500037LL;
  v14[0] = L"1.2.840.113556.1.4.801";
  v14[1] = 5;
  v14[2] = &v25;
  v15 = 1;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v25 = 16909104;
  v26 = 4;
  ServerControls[0] = (PLDAPControlW)v14;
  ServerControls[1] = 0;
  v13 = 0;
  v22[0] = &v13;
  v22[1] = 0;
  v21[0] = 130;
  v21[1] = L"ntSecurityDescriptor";
  v21[2] = v22;
  mods[0] = (LDAPModW *)v21;
  mods[1] = 0;
  v11[0] = 0;
  v19 = 0;
  v20 = 0;
  v12 = 0;
  cxl::SecurityDescriptorBase::GetControlInfo(a3, v11, &v12);
  if ( (v11[0] & 0x8000u) == 0 )
  {
    cxl::SecurityDescriptorBase::GetSelfRelative(a3, &v19);
    *((_QWORD *)&v13 + 1) = v19;
    SecurityDescriptorLength = DWORD2(v19) - v19;
  }
  else
  {
    *((_QWORD *)&v13 + 1) = a3[2];
    SecurityDescriptorLength = GetSecurityDescriptorLength(*((PSECURITY_DESCRIPTOR *)&v13 + 1));
  }
  LODWORD(v13) = SecurityDescriptorLength;
  v8 = ldap_modify_ext_sW(*this, a2, mods, ServerControls, 0);
  if ( v8 )
  {
    v9 = LdapMapErrorToWin32(v8);
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
  }
  else
  {
    v10 = 0;
  }
  std::vector<unsigned char>::_Tidy(&v19);
  return v10;
}

```

## disassembly

```asm
0x1800a812c  mov     [rsp-8+arg_18], rbx
0x1800a8131  push    rbp
0x1800a8132  push    rsi
0x1800a8133  push    rdi
0x1800a8134  lea     rbp, [rsp-47h]
0x1800a8139  sub     rsp, 0E0h
0x1800a8140  mov     rax, cs:__security_cookie
0x1800a8147  xor     rax, rsp
0x1800a814a  mov     [rbp+57h+var_20], rax
0x1800a814e  mov     rbx, r8
0x1800a8151  mov     rsi, rdx
0x1800a8154  mov     rdi, rcx
0x1800a8157  cmp     qword ptr [rcx], 0
0x1800a815b  jnz     short loc_1800A8167
0x1800a815d  mov     eax, 80004005h
0x1800a8162  jmp     loc_1800A828F
0x1800a8167  lea     rax, a12840113556148; "1.2.840.113556.1.4.801"
0x1800a816e  mov     [rbp+57h+var_A8], rax
0x1800a8172  mov     [rbp+57h+var_A0], 5
0x1800a817a  lea     rax, [rbp+57h+var_28]
0x1800a817e  mov     [rbp+57h+var_98], rax
0x1800a8182  mov     [rbp+57h+var_90], 1
0x1800a8186  xor     eax, eax
0x1800a8188  mov     [rbp+57h+var_8F], eax
0x1800a818b  mov     [rbp+57h+var_8B], ax
0x1800a818f  mov     [rbp+57h+var_89], al
0x1800a8192  mov     [rbp+57h+var_28], 1020330h
0x1800a8199  mov     [rbp+57h+var_24], 4
0x1800a819d  lea     rax, [rbp+57h+var_A8]
0x1800a81a1  mov     [rbp+57h+ServerControls], rax
0x1800a81a5  mov     [rbp+57h+var_40], 0
0x1800a81ad  xorps   xmm0, xmm0
0x1800a81b0  movups  [rbp+57h+var_B8], xmm0
0x1800a81b4  lea     rax, [rbp+57h+var_B8]
0x1800a81b8  mov     [rbp+57h+var_58], rax
0x1800a81bc  mov     [rbp+57h+var_50], 0
0x1800a81c4  mov     [rbp+57h+var_70], 82h
0x1800a81cc  lea     rax, aNtsecuritydesc_0; "ntSecurityDescriptor"
0x1800a81d3  mov     [rbp+57h+var_68], rax
0x1800a81d7  lea     rax, [rbp+57h+var_58]
0x1800a81db  mov     [rbp+57h+var_60], rax
0x1800a81df  lea     rax, [rbp+57h+var_70]
0x1800a81e3  mov     [rbp+57h+mods], rax
0x1800a81e7  mov     [rbp+57h+var_30], 0
0x1800a81ef  xor     eax, eax
0x1800a81f1  mov     [rbp+57h+var_C0], ax
0x1800a81f5  movdqu  [rbp+57h+var_88], xmm0
0x1800a81fa  mov     [rbp+57h+var_78], rax
0x1800a81fe  mov     [rbp+57h+var_BC], eax
0x1800a8201  lea     r8, [rbp+57h+var_BC]; unsigned int *
0x1800a8205  lea     rdx, [rbp+57h+var_C0]; unsigned __int16 *
0x1800a8209  mov     rcx, rbx; this
0x1800a820c  call    ?GetControlInfo@SecurityDescriptorBase@cxl@@QEBAXPEAGPEAK@Z; cxl::SecurityDescriptorBase::GetControlInfo(ushort *,ulong *)
0x1800a8211  mov     eax, 8000h
0x1800a8216  test    [rbp+57h+var_C0], ax
0x1800a821a  jz      short loc_1800A822C
0x1800a821c  mov     rcx, [rbx+10h]; pSecurityDescriptor
0x1800a8220  mov     qword ptr [rbp+57h+var_B8+8], rcx
0x1800a8224  call    cs:__imp_GetSecurityDescriptorLength
0x1800a822a  jmp     short loc_1800A8245
0x1800a822c  lea     rdx, [rbp+57h+var_88]
0x1800a8230  mov     rcx, rbx
0x1800a8233  call    ?GetSelfRelative@SecurityDescriptorBase@cxl@@QEBAXPEAV?$vector@DV?$allocator@D@std@@@std@@@Z; cxl::SecurityDescriptorBase::GetSelfRelative(std::vector<char> *)
0x1800a8238  mov     rcx, qword ptr [rbp+57h+var_88]
0x1800a823c  mov     qword ptr [rbp+57h+var_B8+8], rcx
0x1800a8240  mov     eax, dword ptr [rbp+57h+var_88+8]
0x1800a8243  sub     eax, ecx
0x1800a8245  mov     dword ptr [rbp+57h+var_B8], eax
0x1800a8248  mov     [rsp+0F0h+ClientControls], 0; ClientControls
0x1800a8251  lea     r9, [rbp+57h+ServerControls]; ServerControls
0x1800a8255  lea     r8, [rbp+57h+mods]; mods
0x1800a8259  mov     rdx, rsi; dn
0x1800a825c  mov     rcx, [rdi]; ld
0x1800a825f  call    cs:__imp_ldap_modify_ext_sW
0x1800a8265  test    eax, eax
0x1800a8267  jz      short loc_1800A8282
0x1800a8269  mov     ecx, eax; LdapError
0x1800a826b  call    cs:__imp_LdapMapErrorToWin32
0x1800a8271  mov     ebx, eax
0x1800a8273  test    eax, eax
0x1800a8275  jle     short loc_1800A8284
0x1800a8277  movzx   ebx, ax
0x1800a827a  or      ebx, 80070000h
0x1800a8280  jmp     short loc_1800A8284
0x1800a8282  xor     ebx, ebx
0x1800a8284  lea     rcx, [rbp+57h+var_88]
0x1800a8288  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800a828d  mov     eax, ebx
0x1800a828f  mov     rcx, [rbp+57h+var_20]
0x1800a8293  xor     rcx, rsp; StackCookie
0x1800a8296  call    __security_check_cookie
0x1800a829b  mov     rbx, [rsp+0F0h+arg_18]
0x1800a82a3  add     rsp, 0E0h
0x1800a82aa  pop     rdi
0x1800a82ab  pop     rsi
0x1800a82ac  pop     rbp
0x1800a82ad  retn
```
