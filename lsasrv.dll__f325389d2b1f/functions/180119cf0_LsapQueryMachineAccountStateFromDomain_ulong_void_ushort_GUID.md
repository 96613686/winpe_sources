# LsapQueryMachineAccountStateFromDomain(ulong *,void * *,ushort * *,_GUID *)

- ea: `0x180119cf0`
- end: `0x18011a0aa`
- name: `?LsapQueryMachineAccountStateFromDomain@@YAJPEAKPEAPEAXPEAPEAGPEAU_GUID@@@Z`
- size: `954`
- prototype: `__int64 __fastcall(unsigned int *, void **, unsigned __int16 **, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180119880`

## callees

- `0x180011278`
- `0x180014954`
- `0x1800b86d0`
- `0x1800c7258`
- `0x1801196cc`
- `0x180119b4c`
- `0x180119cf0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180119ebe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180119ed2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180119ebe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180119ed2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180119fd0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180119fd0`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180119f82`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180119f82`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180119fa5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180119fa5`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180119e07`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180119e07`
- `ntdll!RtlCopySid` at `0x180119ff1`
- `ntdll!RtlCopySid` at `0x180119ff1`
- `ntdll!RtlLengthSid` at `0x180119fba`
- `ntdll!RtlLengthSid` at `0x180119fba`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18011a005`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18011a005`
- `WLDAP32!__imp_ldap_unbind` at `0x180119efc`
- `WLDAP32!__imp_ldap_unbind` at `0x180119efc`
- `WLDAP32!__imp_ldap_first_entry` at `0x180119f36`
- `WLDAP32!__imp_ldap_first_entry` at `0x180119f36`
- `WLDAP32!__imp_ldap_msgfree` at `0x180119ee8`
- `WLDAP32!__imp_ldap_msgfree` at `0x180119ee8`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18011a083`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18011a099`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18011a083`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18011a099`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x180119f57`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18011a025`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x180119f57`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18011a025`
- `WLDAP32!__imp_ldap_search_sW` at `0x180119e64`
- `WLDAP32!__imp_ldap_search_sW` at `0x180119e64`

## string_xrefs

- `0x180119d38`: `objectSid`

## pseudocode

```c
__int64 __fastcall LsapQueryMachineAccountStateFromDomain(
        unsigned int *a1,
        void **a2,
        unsigned __int16 **a3,
        struct _GUID *a4)
{
  void *v4; // rdi
  int RootDSEAttribute; // eax
  unsigned __int16 *v6; // rdx
  LDAP *v7; // rsi
  int v8; // ebx
  LsaHandleCache *v9; // rcx
  __int64 v10; // rdx
  ULONG v11; // eax
  LDAPMessage *entry; // rax
  LDAPMessage *v14; // r12
  struct berval **values_lenW; // rax
  struct berval **v16; // r15
  struct berval *v17; // rax
  PCHAR bv_val; // r14
  PUCHAR SidSubAuthorityCount; // rax
  ULONG v20; // r13d
  HLOCAL v21; // rax
  struct berval **v22; // rax
  struct _GUID *v23; // r8
  _QWORD *v24; // rcx
  DWORD nSize; // [rsp+40h] [rbp-C0h] BYREF
  PWSTR base; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  LDAPMessage *res; // [rsp+58h] [rbp-A8h] BYREF
  LDAP *ld; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int *v30; // [rsp+68h] [rbp-98h]
  void **v31; // [rsp+70h] [rbp-90h]
  unsigned __int16 **v32; // [rsp+78h] [rbp-88h]
  struct _GUID *v33; // [rsp+80h] [rbp-80h]
  PWSTR attrs[3]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR Buffer[32]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR filter[304]; // [rsp+E0h] [rbp-20h] BYREF

  v30 = a1;
  v33 = a4;
  v32 = a3;
  v31 = a2;
  v4 = 0;
  ld = 0;
  *a1 = 0;
  *a2 = 0;
  *a3 = 0;
  nSize = 0;
  base = 0;
  *a4 = GUID_00000000_0000_0000_0000_000000000000;
  hMem = 0;
  res = 0;
  attrs[0] = (PWSTR)L"objectSid";
  attrs[1] = (PWSTR)L"objectGuid";
  attrs[2] = 0;
  RootDSEAttribute = LsapBindToDomainLdapServer((int)L"objectGuid", (int)a2, (int)a3, &ld);
  v7 = ld;
  v8 = RootDSEAttribute;
  if ( RootDSEAttribute < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) == 0 )
      goto LABEL_14;
    v10 = 26;
    goto LABEL_4;
  }
  RootDSEAttribute = LsapGetRootDSEAttribute(ld, v6, &base);
  v8 = RootDSEAttribute;
  if ( RootDSEAttribute >= 0 )
  {
    nSize = 30;
    if ( !GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
      goto LABEL_13;
    v8 = RtlStringCchPrintfW(filter, 0x12Cu, L"(samAccountName=%s$)", Buffer);
    if ( v8 < 0 )
      goto LABEL_14;
    v11 = ldap_search_sW(v7, base, 2u, filter, attrs, 0, &res);
    if ( v11 )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
        WPP_SF_SSD(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          28,
          (unsigned int)&WPP_274f25f32faf31b8faf4b7c40419aa06_Traceguids,
          (_DWORD)base,
          (__int64)filter,
          v11);
      goto LABEL_13;
    }
    entry = ldap_first_entry(v7, res);
    v14 = entry;
    if ( !entry || (values_lenW = ldap_get_values_lenW(v7, entry, (const PWSTR)L"objectSid"), (v16 = values_lenW) == 0) )
    {
LABEL_13:
      v8 = -1073741670;
      goto LABEL_14;
    }
    v17 = *values_lenW;
    bv_val = v17->bv_val;
    if ( bv_val )
    {
      SidSubAuthorityCount = GetSidSubAuthorityCount(v17->bv_val);
      if ( !*SidSubAuthorityCount )
      {
        v8 = -1073741811;
LABEL_36:
        ldap_value_free_len(v16);
        goto LABEL_14;
      }
      LODWORD(base) = *GetSidSubAuthority(bv_val, (unsigned int)*SidSubAuthorityCount - 1);
      v20 = RtlLengthSid(bv_val);
      v21 = LocalAlloc(0x40u, v20);
      v4 = v21;
      if ( v21 )
      {
        RtlCopySid(v20, v21, bv_val);
        if ( ConvertSidToStringSidW(v4, (LPWSTR *)&hMem) )
        {
          v22 = ldap_get_values_lenW(v7, v14, (const PWSTR)L"objectGuid");
          if ( v22 )
          {
            v23 = (struct _GUID *)(*v22)->bv_val;
            if ( v23 )
            {
              *v30 = (unsigned int)base;
              v24 = v32;
              *v31 = v4;
              v4 = 0;
              *v24 = hMem;
              hMem = 0;
              *v33 = *v23;
            }
            else
            {
              v8 = -1073741670;
            }
            ldap_value_free_len(v22);
            goto LABEL_36;
          }
        }
      }
    }
    v8 = -1073741670;
    goto LABEL_36;
  }
  v9 = WPP_GLOBAL_Control;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
  {
    v10 = 27;
LABEL_4:
    WPP_SF_d(
      *((_QWORD *)v9 + 12),
      v10,
      &WPP_274f25f32faf31b8faf4b7c40419aa06_Traceguids,
      (unsigned int)RootDSEAttribute);
  }
LABEL_14:
  if ( hMem )
    LocalFree(hMem);
  if ( v4 )
    LocalFree(v4);
  if ( res )
    ldap_msgfree(res);
  if ( v7 )
    ldap_unbind(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180119cf0  push    rbp
0x180119cf2  push    rbx
0x180119cf3  push    rsi
0x180119cf4  push    rdi
0x180119cf5  push    r12
0x180119cf7  push    r13
0x180119cf9  push    r14
0x180119cfb  push    r15
0x180119cfd  lea     rbp, [rsp-258h]
0x180119d05  sub     rsp, 358h
0x180119d0c  mov     rax, cs:__security_cookie
0x180119d13  xor     rax, rsp
0x180119d16  mov     [rbp+290h+var_50], rax
0x180119d1d  xor     r13d, r13d
0x180119d20  mov     [rsp+390h+var_328], rcx
0x180119d25  mov     rax, rcx
0x180119d28  mov     [rbp+290h+var_310], r9
0x180119d2c  lea     rcx, aObjectguid; "objectGuid"
0x180119d33  mov     [rsp+390h+var_318], r8
0x180119d38  lea     r14, aObjectsid; "objectSid"
0x180119d3f  mov     [rsp+390h+var_320], rdx
0x180119d44  mov     edi, r13d
0x180119d47  mov     [rsp+390h+ld], r13
0x180119d4c  mov     [rax], r13d
0x180119d4f  mov     [rdx], r13
0x180119d52  mov     [r8], r13
0x180119d55  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180119d5c  mov     [rsp+390h+nSize], r13d
0x180119d61  mov     [rsp+390h+base], r13
0x180119d66  movdqu  xmmword ptr [r9], xmm0
0x180119d6b  lea     r9, [rsp+390h+ld]; struct ldap **
0x180119d70  mov     [rsp+390h+hMem], r13
0x180119d75  mov     [rsp+390h+var_338], r13
0x180119d7a  mov     [rbp+290h+var_308], r14
0x180119d7e  mov     [rbp+290h+var_300], rcx
0x180119d82  mov     [rbp+290h+var_2F8], r13
0x180119d86  call    ?LsapBindToDomainLdapServer@@YAJHHHPEAPEAUldap@@@Z; LsapBindToDomainLdapServer(int,int,int,ldap * *)
0x180119d8b  mov     rsi, [rsp+390h+ld]
0x180119d90  mov     ebx, eax
0x180119d92  test    eax, eax
0x180119d94  jns     short loc_180119DC6
0x180119d96  mov     rcx, cs:WPP_GLOBAL_Control
0x180119d9d  test    dword ptr [rcx+6Ch], 1000h
0x180119da4  jz      loc_180119EB4
0x180119daa  lea     edx, [r13+1Ah]
0x180119dae  mov     rcx, [rcx+60h]
0x180119db2  lea     r8, WPP_274f25f32faf31b8faf4b7c40419aa06_Traceguids
0x180119db9  mov     r9d, eax
0x180119dbc  call    WPP_SF_d
0x180119dc1  jmp     loc_180119EB4
0x180119dc6  lea     r8, [rsp+390h+base]; unsigned __int16 **
0x180119dcb  mov     rcx, rsi; ld
0x180119dce  call    ?LsapGetRootDSEAttribute@@YAJPEAUldap@@PEAGPEAPEAG@Z; LsapGetRootDSEAttribute(ldap *,ushort *,ushort * *)
0x180119dd3  mov     ebx, eax
0x180119dd5  test    eax, eax
0x180119dd7  jns     short loc_180119DF4
0x180119dd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180119de0  test    dword ptr [rcx+6Ch], 1000h
0x180119de7  jz      loc_180119EB4
0x180119ded  mov     edx, 1Bh
0x180119df2  jmp     short loc_180119DAE
0x180119df4  lea     r8, [rsp+390h+nSize]; nSize
0x180119df9  mov     [rsp+390h+nSize], 1Eh
0x180119e01  lea     rdx, [rbp+290h+Buffer]; lpBuffer
0x180119e05  xor     ecx, ecx; NameType
0x180119e07  call    cs:__imp_GetComputerNameExW
0x180119e0e  nop     dword ptr [rax+rax+00h]
0x180119e13  test    eax, eax
0x180119e15  jz      loc_180119EAF
0x180119e1b  lea     r9, [rbp+290h+Buffer]
0x180119e1f  mov     edx, 12Ch; unsigned __int64
0x180119e24  lea     r8, aSamaccountname; "(samAccountName=%s$)"
0x180119e2b  lea     rcx, [rbp+290h+filter]; unsigned __int16 *
0x180119e2f  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180119e34  mov     ebx, eax
0x180119e36  test    eax, eax
0x180119e38  js      short loc_180119EB4
0x180119e3a  mov     rdx, [rsp+390h+base]; base
0x180119e3f  lea     rax, [rsp+390h+var_338]
0x180119e44  mov     [rsp+390h+res], rax; res
0x180119e49  lea     r9, [rbp+290h+filter]; filter
0x180119e4d  lea     rax, [rbp+290h+var_308]
0x180119e51  mov     [rsp+390h+attrsonly], r13d; attrsonly
0x180119e56  mov     r8d, 2; scope
0x180119e5c  mov     [rsp+390h+attrs], rax; attrs
0x180119e61  mov     rcx, rsi; ld
0x180119e64  call    cs:__imp_ldap_search_sW
0x180119e6b  nop     dword ptr [rax+rax+00h]
0x180119e70  test    eax, eax
0x180119e72  jz      loc_180119F2E
0x180119e78  mov     rcx, cs:WPP_GLOBAL_Control
0x180119e7f  test    dword ptr [rcx+6Ch], 1000h
0x180119e86  jz      short loc_180119EAF
0x180119e88  mov     r9, [rsp+390h+base]
0x180119e8d  lea     r8, WPP_274f25f32faf31b8faf4b7c40419aa06_Traceguids
0x180119e94  mov     rcx, [rcx+60h]
0x180119e98  mov     edx, 1Ch
0x180119e9d  mov     [rsp+390h+attrsonly], eax
0x180119ea1  lea     rax, [rbp+290h+filter]
0x180119ea5  mov     [rsp+390h+attrs], rax
0x180119eaa  call    WPP_SF_SSD
0x180119eaf  mov     ebx, 0C000009Ah
0x180119eb4  mov     rcx, [rsp+390h+hMem]; hMem
0x180119eb9  test    rcx, rcx
0x180119ebc  jz      short loc_180119ECA
0x180119ebe  call    cs:__imp_LocalFree
0x180119ec5  nop     dword ptr [rax+rax+00h]
0x180119eca  test    rdi, rdi
0x180119ecd  jz      short loc_180119EDE
0x180119ecf  mov     rcx, rdi; hMem
0x180119ed2  call    cs:__imp_LocalFree
0x180119ed9  nop     dword ptr [rax+rax+00h]
0x180119ede  mov     rcx, [rsp+390h+var_338]; res
0x180119ee3  test    rcx, rcx
0x180119ee6  jz      short loc_180119EF4
0x180119ee8  call    cs:__imp_ldap_msgfree
0x180119eef  nop     dword ptr [rax+rax+00h]
0x180119ef4  test    rsi, rsi
0x180119ef7  jz      short loc_180119F08
0x180119ef9  mov     rcx, rsi; ld
0x180119efc  call    cs:__imp_ldap_unbind
0x180119f03  nop     dword ptr [rax+rax+00h]
0x180119f08  mov     eax, ebx
0x180119f0a  mov     rcx, [rbp+290h+var_50]
0x180119f11  xor     rcx, rsp; StackCookie
0x180119f14  call    __security_check_cookie
0x180119f19  add     rsp, 358h
0x180119f20  pop     r15
0x180119f22  pop     r14
0x180119f24  pop     r13
0x180119f26  pop     r12
0x180119f28  pop     rdi
0x180119f29  pop     rsi
0x180119f2a  pop     rbx
0x180119f2b  pop     rbp
0x180119f2c  retn
0x180119f2e  mov     rdx, [rsp+390h+var_338]; res
0x180119f33  mov     rcx, rsi; ld
0x180119f36  call    cs:__imp_ldap_first_entry
0x180119f3d  nop     dword ptr [rax+rax+00h]
0x180119f42  mov     r12, rax
0x180119f45  test    rax, rax
0x180119f48  jz      loc_180119EAF
0x180119f4e  mov     r8, r14; attr
0x180119f51  mov     rdx, rax; Message
0x180119f54  mov     rcx, rsi; ExternalHandle
0x180119f57  call    cs:__imp_ldap_get_values_lenW
0x180119f5e  nop     dword ptr [rax+rax+00h]
0x180119f63  mov     r15, rax
0x180119f66  test    rax, rax
0x180119f69  jz      loc_180119EAF
0x180119f6f  mov     rax, [rax]
0x180119f72  mov     r14, [rax+8]
0x180119f76  test    r14, r14
0x180119f79  jz      loc_18011A091
0x180119f7f  mov     rcx, r14; pSid
0x180119f82  call    cs:__imp_GetSidSubAuthorityCount
0x180119f89  nop     dword ptr [rax+rax+00h]
0x180119f8e  cmp     [rax], r13b
0x180119f91  jnz     short loc_180119F9D
0x180119f93  mov     ebx, 0C000000Dh
0x180119f98  jmp     loc_18011A096
0x180119f9d  movzx   edx, byte ptr [rax]
0x180119fa0  mov     rcx, r14; pSid
0x180119fa3  dec     edx; nSubAuthority
0x180119fa5  call    cs:__imp_GetSidSubAuthority
0x180119fac  nop     dword ptr [rax+rax+00h]
0x180119fb1  mov     rcx, r14; Sid
0x180119fb4  mov     eax, [rax]
0x180119fb6  mov     dword ptr [rsp+390h+base], eax
0x180119fba  call    cs:__imp_RtlLengthSid
0x180119fc1  nop     dword ptr [rax+rax+00h]
0x180119fc6  mov     edx, eax; uBytes
0x180119fc8  mov     ecx, 40h ; '@'; uFlags
0x180119fcd  mov     r13d, eax
0x180119fd0  call    cs:__imp_LocalAlloc
0x180119fd7  nop     dword ptr [rax+rax+00h]
0x180119fdc  mov     rdi, rax
0x180119fdf  test    rax, rax
0x180119fe2  jz      loc_18011A091
0x180119fe8  mov     r8, r14; SourceSid
0x180119feb  mov     rdx, rax; DestinationSid
0x180119fee  mov     ecx, r13d; DestinationSidLength
0x180119ff1  call    cs:__imp_RtlCopySid
0x180119ff8  nop     dword ptr [rax+rax+00h]
0x180119ffd  lea     rdx, [rsp+390h+hMem]; StringSid
0x18011a002  mov     rcx, rdi; Sid
0x18011a005  call    cs:__imp_ConvertSidToStringSidW
0x18011a00c  nop     dword ptr [rax+rax+00h]
0x18011a011  xor     r13d, r13d
0x18011a014  test    eax, eax
0x18011a016  jz      short loc_18011A091
0x18011a018  lea     r8, aObjectguid; "objectGuid"
0x18011a01f  mov     rdx, r12; Message
0x18011a022  mov     rcx, rsi; ExternalHandle
0x18011a025  call    cs:__imp_ldap_get_values_lenW
0x18011a02c  nop     dword ptr [rax+rax+00h]
0x18011a031  mov     rdx, rax
0x18011a034  test    rax, rax
0x18011a037  jz      short loc_18011A091
0x18011a039  mov     rcx, [rax]
0x18011a03c  mov     r8, [rcx+8]
0x18011a040  test    r8, r8
0x18011a043  jnz     short loc_18011A04C
0x18011a045  mov     ebx, 0C000009Ah
0x18011a04a  jmp     short loc_18011A080
0x18011a04c  mov     rcx, [rsp+390h+var_328]
0x18011a051  mov     eax, dword ptr [rsp+390h+base]
0x18011a055  mov     [rcx], eax
0x18011a057  mov     rax, [rsp+390h+var_320]
0x18011a05c  mov     rcx, [rsp+390h+var_318]
0x18011a061  mov     [rax], rdi
0x18011a064  mov     rdi, r13
0x18011a067  mov     rax, [rsp+390h+hMem]
0x18011a06c  mov     [rcx], rax
0x18011a06f  mov     rax, [rbp+290h+var_310]
0x18011a073  mov     [rsp+390h+hMem], r13
0x18011a078  movups  xmm0, xmmword ptr [r8]
0x18011a07c  movdqu  xmmword ptr [rax], xmm0
0x18011a080  mov     rcx, rdx; vals
0x18011a083  call    cs:__imp_ldap_value_free_len
0x18011a08a  nop     dword ptr [rax+rax+00h]
0x18011a08f  jmp     short loc_18011A096
0x18011a091  mov     ebx, 0C000009Ah
0x18011a096  mov     rcx, r15; vals
0x18011a099  call    cs:__imp_ldap_value_free_len
0x18011a0a0  nop     dword ptr [rax+rax+00h]
0x18011a0a5  jmp     loc_180119EB4
```
