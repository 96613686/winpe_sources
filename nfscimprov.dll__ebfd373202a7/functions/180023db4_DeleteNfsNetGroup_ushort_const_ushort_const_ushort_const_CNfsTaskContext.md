# DeleteNfsNetGroup(ushort const *,ushort const *,ushort const *,CNfsTaskContext *)

- ea: `0x180023db4`
- end: `0x180023fd1`
- name: `?DeleteNfsNetGroup@@YAKPEBG00PEAVCNfsTaskContext@@@Z`
- size: `541`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, PCWSTR SourceString, PCWSTR, struct CNfsTaskContext *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180014a3c`

## callees

- `0x180023db4`
- `0x180025430`
- `0x18002b368`
- `0x18002b4ac`
- `0x180035b02`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180023e55`
- `ntdll!RtlInitUnicodeString` at `0x180023e63`
- `ntdll!RtlInitUnicodeString` at `0x180023e55`
- `ntdll!RtlInitUnicodeString` at `0x180023e63`
- `ADVAPI32!LsaNtStatusToWinError` at `0x180023e7f`
- `ADVAPI32!LsaNtStatusToWinError` at `0x180023e7f`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180023f46`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180023f46`
- `WLDAP32!__imp_ldap_first_entry` at `0x180023ebc`
- `WLDAP32!__imp_ldap_first_entry` at `0x180023ebc`
- `WLDAP32!__imp_ldap_next_entry` at `0x180023f79`
- `WLDAP32!__imp_ldap_next_entry` at `0x180023f79`
- `WLDAP32!__imp_ldap_msgfree` at `0x180023f95`
- `WLDAP32!__imp_ldap_msgfree` at `0x180023f95`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x180023f0a`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x180023f0a`
- `WLDAP32!__imp_ldap_delete_sW` at `0x180023f3a`
- `WLDAP32!__imp_ldap_delete_sW` at `0x180023f3a`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180023ef9`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180023ef9`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180023f6b`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180023f6b`

## pseudocode

```c
__int64 __fastcall DeleteNfsNetGroup(
        const unsigned __int16 *a1,
        PCWSTR SourceString,
        PCWSTR a3,
        struct CNfsTaskContext *a4)
{
  NTSTATUS v8; // eax
  LDAPMessage *entry; // rdi
  PWCHAR *valuesW; // rax
  PWCHAR *v11; // rsi
  WCHAR *v12; // r15
  ULONG v13; // eax
  LDAPMessage *res; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING v16; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  LDAP *ld[68]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v19[3]; // [rsp+280h] [rbp+180h] BYREF

  v19[0] = L"cn";
  v19[1] = L"distinguishedName";
  v19[2] = 0;
  res = 0;
  DestinationString = 0;
  v16 = 0;
  memset_0(ld, 0, 0x218u);
  if ( !SourceString || !*SourceString )
    return 87;
  RtlInitUnicodeString(&DestinationString, SourceString);
  RtlInitUnicodeString(&v16, a3);
  v8 = NfsConnectLdap(ld, &DestinationString, &v16);
  LODWORD(SourceString) = LsaNtStatusToWinError(v8);
  if ( !(_DWORD)SourceString )
  {
    LODWORD(SourceString) = SearchForNetgroups(a1, v19, (struct _NFS_LDAP_CONNECTION *)ld, &res);
    if ( !(_DWORD)SourceString )
    {
      entry = ldap_first_entry(ld[0], res);
      if ( entry )
      {
        do
        {
          valuesW = ldap_get_valuesW(ld[0], entry, (const PWSTR)L"distinguishedName");
          v11 = valuesW;
          if ( valuesW )
          {
            if ( ldap_count_valuesW(valuesW) )
            {
              v12 = *v11;
              if ( (*(unsigned __int8 (__fastcall **)(struct CNfsTaskContext *, __int64, PWCHAR))(*(_QWORD *)a4 + 48LL))(
                     a4,
                     1073745949,
                     *v11) )
              {
                v13 = ldap_delete_sW(ld[0], v12);
                if ( v13 )
                {
                  SourceString = (PCWSTR)LdapMapErrorToWin32(v13);
                  (*(void (__fastcall **)(struct CNfsTaskContext *, PCWSTR, __int64, WCHAR *))(*(_QWORD *)a4 + 40LL))(
                    a4,
                    SourceString,
                    3221229598LL,
                    v12);
                }
              }
            }
            ldap_value_freeW(v11);
          }
          entry = ldap_next_entry(ld[0], entry);
        }
        while ( entry );
      }
      else
      {
        LODWORD(SourceString) = 1168;
        (*(void (__fastcall **)(struct CNfsTaskContext *, __int64, __int64, const unsigned __int16 *))(*(_QWORD *)a4 + 40LL))(
          a4,
          1168,
          3221229603LL,
          a1);
      }
      if ( res )
        ldap_msgfree(res);
    }
    NfsDisconnectLdap(ld);
  }
  return (unsigned int)SourceString;
}

```

## disassembly

```asm
0x180023db4  push    rbp
0x180023db6  push    rbx
0x180023db7  push    rsi
0x180023db8  push    rdi
0x180023db9  push    r12
0x180023dbb  push    r13
0x180023dbd  push    r14
0x180023dbf  push    r15
0x180023dc1  lea     rbp, [rsp-1A8h]
0x180023dc9  sub     rsp, 2A8h
0x180023dd0  mov     rax, cs:__security_cookie
0x180023dd7  xor     rax, rsp
0x180023dda  mov     [rbp+1E0h+var_48], rax
0x180023de1  mov     rdi, r8
0x180023de4  lea     rax, aCn; "cn"
0x180023deb  mov     rbx, rdx
0x180023dee  mov     [rbp+1E0h+var_60], rax
0x180023df5  mov     rsi, rcx
0x180023df8  lea     r13, attr; "distinguishedName"
0x180023dff  xor     r12d, r12d
0x180023e02  mov     [rbp+1E0h+var_58], r13
0x180023e09  xorps   xmm0, xmm0
0x180023e0c  mov     [rbp+1E0h+var_50], r12
0x180023e13  xorps   xmm1, xmm1
0x180023e16  mov     [rsp+2E0h+res], r12
0x180023e1b  xor     edx, edx; Val
0x180023e1d  lea     rcx, [rsp+2E0h+ld]; void *
0x180023e22  mov     r8d, 218h; Size
0x180023e28  mov     r14, r9
0x180023e2b  movups  xmmword ptr [rsp+2E0h+DestinationString.Length], xmm0
0x180023e30  movups  xmmword ptr [rsp+2E0h+var_2A8.Length], xmm1
0x180023e35  call    memset_0
0x180023e3a  test    rbx, rbx
0x180023e3d  jz      loc_180023FA9
0x180023e43  cmp     [rbx], r12w
0x180023e47  jz      loc_180023FA9
0x180023e4d  mov     rdx, rbx; SourceString
0x180023e50  lea     rcx, [rsp+2E0h+DestinationString]; DestinationString
0x180023e55  call    cs:__imp_RtlInitUnicodeString
0x180023e5b  mov     rdx, rdi; SourceString
0x180023e5e  lea     rcx, [rsp+2E0h+var_2A8]; DestinationString
0x180023e63  call    cs:__imp_RtlInitUnicodeString
0x180023e69  lea     r8, [rsp+2E0h+var_2A8]
0x180023e6e  lea     rdx, [rsp+2E0h+DestinationString]
0x180023e73  lea     rcx, [rsp+2E0h+ld]
0x180023e78  call    NfsConnectLdap
0x180023e7d  mov     ecx, eax; Status
0x180023e7f  call    cs:__imp_LsaNtStatusToWinError
0x180023e85  mov     ebx, eax
0x180023e87  test    eax, eax
0x180023e89  jnz     loc_180023FA5
0x180023e8f  lea     r9, [rsp+2E0h+res]; struct ldapmsg **
0x180023e94  mov     rcx, rsi; unsigned __int16 *
0x180023e97  lea     r8, [rsp+2E0h+ld]; struct _NFS_LDAP_CONNECTION *
0x180023e9c  lea     rdx, [rbp+1E0h+var_60]; unsigned __int16 **
0x180023ea3  call    ?SearchForNetgroups@@YAKPEBGPEAPEAGPEAU_NFS_LDAP_CONNECTION@@PEAPEAUldapmsg@@@Z; SearchForNetgroups(ushort const *,ushort * *,_NFS_LDAP_CONNECTION *,ldapmsg * *)
0x180023ea8  mov     ebx, eax
0x180023eaa  test    eax, eax
0x180023eac  jnz     loc_180023F9B
0x180023eb2  mov     rdx, [rsp+2E0h+res]; res
0x180023eb7  mov     rcx, [rsp+2E0h+ld]; ld
0x180023ebc  call    cs:__imp_ldap_first_entry
0x180023ec2  mov     rdi, rax
0x180023ec5  test    rax, rax
0x180023ec8  jnz     short loc_180023EEE
0x180023eca  mov     rax, [r14]
0x180023ecd  mov     ebx, 490h
0x180023ed2  mov     r9, rsi
0x180023ed5  mov     r8d, 0C0001023h
0x180023edb  mov     edx, ebx
0x180023edd  mov     rcx, r14
0x180023ee0  mov     rax, [rax+28h]
0x180023ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ee9  jmp     loc_180023F8B
0x180023eee  mov     rcx, [rsp+2E0h+ld]; ld
0x180023ef3  mov     r8, r13; attr
0x180023ef6  mov     rdx, rdi; entry
0x180023ef9  call    cs:__imp_ldap_get_valuesW
0x180023eff  mov     rsi, rax
0x180023f02  test    rax, rax
0x180023f05  jz      short loc_180023F71
0x180023f07  mov     rcx, rax; vals
0x180023f0a  call    cs:__imp_ldap_count_valuesW
0x180023f10  test    eax, eax
0x180023f12  jz      short loc_180023F68
0x180023f14  mov     rcx, [r14]
0x180023f17  mov     edx, 4000101Dh
0x180023f1c  mov     r15, [rsi]
0x180023f1f  mov     r8, r15
0x180023f22  mov     rax, [rcx+30h]
0x180023f26  mov     rcx, r14
0x180023f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f2e  test    al, al
0x180023f30  jz      short loc_180023F68
0x180023f32  mov     rcx, [rsp+2E0h+ld]; ld
0x180023f37  mov     rdx, r15; dn
0x180023f3a  call    cs:__imp_ldap_delete_sW
0x180023f40  test    eax, eax
0x180023f42  jz      short loc_180023F68
0x180023f44  mov     ecx, eax; LdapError
0x180023f46  call    cs:__imp_LdapMapErrorToWin32
0x180023f4c  mov     r9, r15
0x180023f4f  mov     r8d, 0C000101Eh
0x180023f55  mov     ebx, eax
0x180023f57  mov     rcx, r14
0x180023f5a  mov     rax, [r14]
0x180023f5d  mov     edx, ebx
0x180023f5f  mov     rax, [rax+28h]
0x180023f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f68  mov     rcx, rsi; vals
0x180023f6b  call    cs:__imp_ldap_value_freeW
0x180023f71  mov     rcx, [rsp+2E0h+ld]; ld
0x180023f76  mov     rdx, rdi; entry
0x180023f79  call    cs:__imp_ldap_next_entry
0x180023f7f  mov     rdi, rax
0x180023f82  test    rax, rax
0x180023f85  jnz     loc_180023EEE
0x180023f8b  mov     rcx, [rsp+2E0h+res]; res
0x180023f90  test    rcx, rcx
0x180023f93  jz      short loc_180023F9B
0x180023f95  call    cs:__imp_ldap_msgfree
0x180023f9b  lea     rcx, [rsp+2E0h+ld]
0x180023fa0  call    NfsDisconnectLdap
0x180023fa5  mov     eax, ebx
0x180023fa7  jmp     short loc_180023FAE
0x180023fa9  mov     eax, 57h ; 'W'
0x180023fae  mov     rcx, [rbp+1E0h+var_48]
0x180023fb5  xor     rcx, rsp; StackCookie
0x180023fb8  call    __security_check_cookie
0x180023fbd  add     rsp, 2A8h
0x180023fc4  pop     r15
0x180023fc6  pop     r14
0x180023fc8  pop     r13
0x180023fca  pop     r12
0x180023fcc  pop     rdi
0x180023fcd  pop     rsi
0x180023fce  pop     rbx
0x180023fcf  pop     rbp
0x180023fd0  retn
```
