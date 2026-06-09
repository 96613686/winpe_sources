# NewNfsNetGroup(ushort const *,ushort const * *,ulong,ushort const *,ushort const *,CNfsTaskContext *)

- ea: `0x180024990`
- end: `0x180024d81`
- name: `?NewNfsNetGroup@@YAKPEBGPEAPEBGK00PEAVCNfsTaskContext@@@Z`
- size: `1009`
- prototype: `unsigned int __usercall@<eax>(const unsigned __int16 *@<rcx>, const unsigned __int16 **@<rdx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, const unsigned __int16 *, struct CNfsTaskContext *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task`

## callers

- `0x1800147ac`

## callees

- `0x1800096cc`
- `0x18000eae4`
- `0x180016248`
- `0x180018230`
- `0x1800182b8`
- `0x180023ba0`
- `0x180023c38`
- `0x180023d04`
- `0x180024990`
- `0x180025430`
- `0x18002b368`
- `0x18002b4ac`
- `0x180035b02`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180024a52`
- `ntdll!RtlInitUnicodeString` at `0x180024a60`
- `ntdll!RtlInitUnicodeString` at `0x180024a52`
- `ntdll!RtlInitUnicodeString` at `0x180024a60`
- `KERNEL32!HeapFree` at `0x180024d0f`
- `KERNEL32!HeapFree` at `0x180024d2a`
- `KERNEL32!HeapFree` at `0x180024d0f`
- `KERNEL32!HeapFree` at `0x180024d2a`
- `KERNEL32!HeapAlloc` at `0x180024b62`
- `KERNEL32!HeapAlloc` at `0x180024b62`
- `KERNEL32!GetProcessHeap` at `0x180024b53`
- `KERNEL32!GetProcessHeap` at `0x180024d01`
- `KERNEL32!GetProcessHeap` at `0x180024d1c`
- `KERNEL32!GetProcessHeap` at `0x180024b53`
- `KERNEL32!GetProcessHeap` at `0x180024d01`
- `KERNEL32!GetProcessHeap` at `0x180024d1c`
- `ADVAPI32!LsaNtStatusToWinError` at `0x180024a7b`
- `ADVAPI32!LsaNtStatusToWinError` at `0x180024a7b`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180024ce1`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180024ce1`
- `WLDAP32!__imp_ldap_first_entry` at `0x180024ab0`
- `WLDAP32!__imp_ldap_first_entry` at `0x180024ab0`
- `WLDAP32!__imp_ldap_msgfree` at `0x180024ae7`
- `WLDAP32!__imp_ldap_msgfree` at `0x180024ae7`
- `WLDAP32!__imp_ldap_add_sW` at `0x180024cd5`
- `WLDAP32!__imp_ldap_add_sW` at `0x180024cd5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NewNfsNetGroup(
        const unsigned __int16 *a1,
        const unsigned __int16 **a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *SourceString,
        struct CNfsTaskContext *a6)
{
  char v10; // r14
  NTSTATUS v11; // eax
  ULONG NetGroupMemberTriple; // edi
  _QWORD *v13; // rsi
  unsigned int v14; // r14d
  SIZE_T v15; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v17; // r12
  __int64 v18; // rbx
  _QWORD *v19; // r15
  void *p_attrs; // rcx
  __int64 v21; // rdx
  __int64 i; // rax
  __int64 v23; // rax
  ULONG v24; // eax
  unsigned int j; // ebx
  void *v26; // r15
  HANDLE v27; // rax
  HANDLE v28; // rax
  LDAPMessage *res; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR dn; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v32[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING v33; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v35[2]; // [rsp+70h] [rbp-90h] BYREF
  LDAP *ld[68]; // [rsp+80h] [rbp-80h] BYREF
  LDAPModW *attrs; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int128 v38; // [rsp+2A8h] [rbp+1A8h]
  unsigned __int64 v39; // [rsp+2B8h] [rbp+1B8h]
  _QWORD v40[4]; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v41; // [rsp+2E0h] [rbp+1E0h] BYREF
  const wchar_t *v42; // [rsp+2E8h] [rbp+1E8h]
  _QWORD *v43; // [rsp+2F0h] [rbp+1F0h]
  int v44; // [rsp+2F8h] [rbp+1F8h] BYREF
  const WCHAR *v45; // [rsp+300h] [rbp+200h]
  _QWORD *v46; // [rsp+308h] [rbp+208h]

  v35[0] = L"cn";
  v10 = 0;
  v35[1] = 0;
  dn = 0;
  res = 0;
  DestinationString = 0;
  v33 = 0;
  memset_0(ld, 0, 0x218u);
  std::set<std::wstring>::set<std::wstring>(v32);
  if ( a4 && *a4 && SourceString && *SourceString )
  {
    RtlInitUnicodeString(&DestinationString, a4);
    RtlInitUnicodeString(&v33, SourceString);
    v11 = NfsConnectLdap(ld, &DestinationString, &v33);
    NetGroupMemberTriple = LsaNtStatusToWinError(v11);
    if ( NetGroupMemberTriple )
    {
LABEL_43:
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v32);
      return NetGroupMemberTriple;
    }
    NetGroupMemberTriple = SearchForNetgroups(a1, v35, (struct _NFS_LDAP_CONNECTION *)ld, &res);
    if ( !NetGroupMemberTriple )
    {
      if ( ldap_first_entry(ld[0], res) )
      {
        NetGroupMemberTriple = 183;
        (*(void (__fastcall **)(struct CNfsTaskContext *, __int64, __int64, const unsigned __int16 *))(*(_QWORD *)a6 + 40LL))(
          a6,
          183,
          3221229602LL,
          a1);
        v10 = 1;
      }
      if ( res )
        ldap_msgfree(res);
    }
    if ( (unsigned __int8)CheckDuplicates(a2, a3, v32) )
      NetGroupMemberTriple = 87;
    if ( !v10 && !NetGroupMemberTriple )
    {
      NetGroupMemberTriple = CreateNetGroupDn(a1, SourceString, &dn);
      if ( !NetGroupMemberTriple )
      {
        v13 = 0;
        v14 = 0;
        if ( !a3 )
          goto LABEL_32;
        v15 = 8LL * v32[1] + 8;
        ProcessHeap = GetProcessHeap();
        v13 = HeapAlloc(ProcessHeap, 8u, v15);
        if ( !v13 )
        {
          NetGroupMemberTriple = 8;
          goto LABEL_42;
        }
        v17 = v32[0];
        v18 = *(_QWORD *)v32[0];
        while ( 1 )
        {
          v19 = &v13[v14];
          if ( v18 == v17 )
            break;
          std::wstring::wstring(&attrs, v18 + 32);
          ++v14;
          p_attrs = &attrs;
          if ( v39 >= 8 )
            p_attrs = attrs;
          NetGroupMemberTriple = CreateNetGroupMemberTriple(p_attrs, v19);
          LOBYTE(v21) = 1;
          std::wstring::_Tidy(&attrs, v21, 0);
          if ( !*(_BYTE *)(v18 + 25) )
          {
            if ( *(_BYTE *)(*(_QWORD *)(v18 + 16) + 25LL) )
            {
              for ( i = *(_QWORD *)(v18 + 8); !*(_BYTE *)(i + 25) && v18 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
                v18 = i;
            }
            else
            {
              i = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Min();
            }
            v18 = i;
          }
        }
        *v19 = 0;
        if ( !NetGroupMemberTriple )
        {
LABEL_32:
          v40[3] = 0;
          v38 = 0;
          v39 = 0;
          v41 = 0;
          v42 = L"objectClass";
          v43 = v40;
          v40[0] = L"top";
          v40[1] = L"nisNetGroup";
          v40[2] = 0;
          attrs = (LDAPModW *)&v41;
          v23 = 1;
          if ( a3 )
          {
            v44 = 0;
            v45 = L"nisNetgroupTriple";
            v46 = v13;
            *(_QWORD *)&v38 = &v44;
            v23 = 2;
          }
          *(&attrs + v23) = 0;
          v24 = ldap_add_sW(ld[0], dn, &attrs);
          if ( v24 )
            NetGroupMemberTriple = LdapMapErrorToWin32(v24);
        }
        if ( v13 )
        {
          for ( j = 0; j < v14; ++j )
          {
            v26 = (void *)v13[j];
            if ( v26 )
            {
              v27 = GetProcessHeap();
              HeapFree(v27, 0, v26);
            }
          }
          v28 = GetProcessHeap();
          HeapFree(v28, 0, v13);
        }
      }
    }
LABEL_42:
    NfsDisconnectLdap(ld);
    goto LABEL_43;
  }
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v32);
  return 87;
}

```

## disassembly

```asm
0x180024990  mov     [rsp-8+arg_10], rbx
0x180024995  push    rbp
0x180024996  push    rsi
0x180024997  push    rdi
0x180024998  push    r12
0x18002499a  push    r13
0x18002499c  push    r14
0x18002499e  push    r15
0x1800249a0  lea     rbp, [rsp-240h]
0x1800249a8  sub     rsp, 340h
0x1800249af  mov     rax, cs:__security_cookie
0x1800249b6  xor     rax, rsp
0x1800249b9  mov     [rbp+270h+var_40], rax
0x1800249c0  mov     rdi, r9
0x1800249c3  mov     r13d, r8d
0x1800249c6  mov     r12, rdx
0x1800249c9  mov     rsi, rcx
0x1800249cc  mov     rbx, [rbp+270h+SourceString]
0x1800249d3  mov     r15, [rbp+270h+arg_28]
0x1800249da  lea     rax, aCn; "cn"
0x1800249e1  mov     [rsp+370h+var_300], rax
0x1800249e6  xor     r14d, r14d
0x1800249e9  mov     [rsp+370h+var_2F8], r14
0x1800249ee  mov     [rsp+370h+dn], r14
0x1800249f3  mov     [rsp+370h+res], r14
0x1800249f8  xorps   xmm0, xmm0
0x1800249fb  movups  xmmword ptr [rsp+370h+DestinationString.Length], xmm0
0x180024a00  xorps   xmm1, xmm1
0x180024a03  movups  xmmword ptr [rsp+370h+var_320.Length], xmm1
0x180024a08  xor     edx, edx; Val
0x180024a0a  mov     r8d, 218h; Size
0x180024a10  lea     rcx, [rbp+270h+ld]; void *
0x180024a14  call    memset_0
0x180024a19  lea     rcx, [rsp+370h+var_330]
0x180024a1e  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x180024a23  nop
0x180024a24  test    rdi, rdi
0x180024a27  jz      loc_180024D48
0x180024a2d  cmp     [rdi], r14w
0x180024a31  jz      loc_180024D48
0x180024a37  test    rbx, rbx
0x180024a3a  jz      loc_180024D48
0x180024a40  cmp     [rbx], r14w
0x180024a44  jz      loc_180024D48
0x180024a4a  mov     rdx, rdi; SourceString
0x180024a4d  lea     rcx, [rsp+370h+DestinationString]; DestinationString
0x180024a52  call    cs:__imp_RtlInitUnicodeString
0x180024a58  mov     rdx, rbx; SourceString
0x180024a5b  lea     rcx, [rsp+370h+var_320]; DestinationString
0x180024a60  call    cs:__imp_RtlInitUnicodeString
0x180024a66  lea     r8, [rsp+370h+var_320]
0x180024a6b  lea     rdx, [rsp+370h+DestinationString]
0x180024a70  lea     rcx, [rbp+270h+ld]
0x180024a74  call    NfsConnectLdap
0x180024a79  mov     ecx, eax; Status
0x180024a7b  call    cs:__imp_LsaNtStatusToWinError
0x180024a81  mov     edi, eax
0x180024a83  test    eax, eax
0x180024a85  jnz     loc_180024D3A
0x180024a8b  lea     r9, [rsp+370h+res]; struct ldapmsg **
0x180024a90  lea     r8, [rbp+270h+ld]; struct _NFS_LDAP_CONNECTION *
0x180024a94  lea     rdx, [rsp+370h+var_300]; unsigned __int16 **
0x180024a99  mov     rcx, rsi; unsigned __int16 *
0x180024a9c  call    ?SearchForNetgroups@@YAKPEBGPEAPEAGPEAU_NFS_LDAP_CONNECTION@@PEAPEAUldapmsg@@@Z; SearchForNetgroups(ushort const *,ushort * *,_NFS_LDAP_CONNECTION *,ldapmsg * *)
0x180024aa1  mov     edi, eax
0x180024aa3  test    eax, eax
0x180024aa5  jnz     short loc_180024AED
0x180024aa7  mov     rdx, [rsp+370h+res]; res
0x180024aac  mov     rcx, [rbp+270h+ld]; ld
0x180024ab0  call    cs:__imp_ldap_first_entry
0x180024ab6  test    rax, rax
0x180024ab9  jz      short loc_180024ADD
0x180024abb  mov     edi, 0B7h
0x180024ac0  mov     rax, [r15]
0x180024ac3  mov     r9, rsi
0x180024ac6  mov     r8d, 0C0001022h
0x180024acc  mov     edx, edi
0x180024ace  mov     rcx, r15
0x180024ad1  mov     rax, [rax+28h]
0x180024ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ada  mov     r14b, 1
0x180024add  mov     rcx, [rsp+370h+res]; res
0x180024ae2  test    rcx, rcx
0x180024ae5  jz      short loc_180024AED
0x180024ae7  call    cs:__imp_ldap_msgfree
0x180024aed  lea     r8, [rsp+370h+var_330]
0x180024af2  mov     edx, r13d
0x180024af5  mov     rcx, r12
0x180024af8  call    ?CheckDuplicates@@YAEPEAPEBGKAEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; CheckDuplicates(ushort const * *,ulong,std::set<std::wstring> &)
0x180024afd  mov     r8d, 57h ; 'W'
0x180024b03  xor     r12d, r12d
0x180024b06  test    al, al
0x180024b08  cmovnz  edi, r8d
0x180024b0c  test    r14b, r14b
0x180024b0f  jnz     loc_180024D30
0x180024b15  test    edi, edi
0x180024b17  jnz     loc_180024D30
0x180024b1d  lea     r8, [rsp+370h+dn]
0x180024b22  mov     rdx, rbx
0x180024b25  mov     rcx, rsi
0x180024b28  call    CreateNetGroupDn
0x180024b2d  mov     edi, eax
0x180024b2f  test    eax, eax
0x180024b31  jnz     loc_180024D30
0x180024b37  mov     esi, r12d
0x180024b3a  mov     r14d, r12d
0x180024b3d  test    r13d, r13d
0x180024b40  jz      loc_180024C17
0x180024b46  mov     rax, [rsp+370h+var_328]
0x180024b4b  lea     rbx, ds:8[rax*8]
0x180024b53  call    cs:__imp_GetProcessHeap
0x180024b59  mov     rcx, rax; hHeap
0x180024b5c  mov     r8, rbx; dwBytes
0x180024b5f  lea     edx, [rdi+8]; dwFlags
0x180024b62  call    cs:__imp_HeapAlloc
0x180024b68  mov     rsi, rax
0x180024b6b  test    rax, rax
0x180024b6e  jnz     short loc_180024B78
0x180024b70  lea     edi, [rax+8]
0x180024b73  jmp     loc_180024D30
0x180024b78  mov     r12, [rsp+370h+var_330]
0x180024b7d  mov     rbx, [r12]
0x180024b81  mov     eax, r14d
0x180024b84  lea     r15, [rsi+rax*8]
0x180024b88  cmp     rbx, r12
0x180024b8b  jz      short loc_180024C09
0x180024b8d  lea     rdx, [rbx+20h]
0x180024b91  lea     rcx, [rbp+270h+attrs]
0x180024b98  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180024b9d  inc     r14d
0x180024ba0  lea     rcx, [rbp+270h+attrs]
0x180024ba7  cmp     [rbp+270h+var_B8], 8
0x180024baf  cmovnb  rcx, [rbp+270h+attrs]
0x180024bb7  mov     rdx, r15
0x180024bba  call    CreateNetGroupMemberTriple
0x180024bbf  mov     edi, eax
0x180024bc1  xor     r8d, r8d
0x180024bc4  mov     dl, 1
0x180024bc6  lea     rcx, [rbp+270h+attrs]
0x180024bcd  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180024bd2  xor     edx, edx
0x180024bd4  cmp     [rbx+19h], dl
0x180024bd7  jnz     short loc_180024B81
0x180024bd9  mov     rcx, [rbx+10h]
0x180024bdd  cmp     [rcx+19h], dl
0x180024be0  jnz     short loc_180024BE9
0x180024be2  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Min(std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x180024be7  jmp     short loc_180024C01
0x180024be9  mov     rax, [rbx+8]
0x180024bed  jmp     short loc_180024BFC
0x180024bef  cmp     rbx, [rax+10h]
0x180024bf3  jnz     short loc_180024C01
0x180024bf5  mov     rbx, rax
0x180024bf8  mov     rax, [rax+8]
0x180024bfc  cmp     [rax+19h], dl
0x180024bff  jz      short loc_180024BEF
0x180024c01  mov     rbx, rax
0x180024c04  jmp     loc_180024B81
0x180024c09  xor     r12d, r12d
0x180024c0c  mov     [r15], r12
0x180024c0f  test    edi, edi
0x180024c11  jnz     loc_180024CE9
0x180024c17  mov     [rbp+270h+var_98], r12
0x180024c1e  xorps   xmm0, xmm0
0x180024c21  movdqu  [rbp+270h+var_C8], xmm0
0x180024c29  mov     [rbp+270h+var_B8], r12
0x180024c30  mov     [rbp+270h+var_90], r12d
0x180024c37  lea     rax, aObjectclass_0; "objectClass"
0x180024c3e  mov     [rbp+270h+var_88], rax
0x180024c45  lea     rax, [rbp+270h+var_B0]
0x180024c4c  mov     [rbp+270h+var_80], rax
0x180024c53  lea     rax, aTop; "top"
0x180024c5a  mov     [rbp+270h+var_B0], rax
0x180024c61  lea     rax, aNisnetgroup; "nisNetGroup"
0x180024c68  mov     [rbp+270h+var_A8], rax
0x180024c6f  mov     [rbp+270h+var_A0], r12
0x180024c76  lea     rax, [rbp+270h+var_90]
0x180024c7d  mov     [rbp+270h+attrs], rax
0x180024c84  mov     eax, 1
0x180024c89  test    r13d, r13d
0x180024c8c  jz      short loc_180024CBD
0x180024c8e  mov     [rbp+270h+var_78], r12d
0x180024c95  lea     rax, aNisnetgrouptri; "nisNetgroupTriple"
0x180024c9c  mov     [rbp+270h+var_70], rax
0x180024ca3  mov     [rbp+270h+var_68], rsi
0x180024caa  lea     rax, [rbp+270h+var_78]
0x180024cb1  mov     qword ptr [rbp+270h+var_C8], rax
0x180024cb8  mov     eax, 2
0x180024cbd  mov     [rbp+rax*8+270h+attrs], r12
0x180024cc5  lea     r8, [rbp+270h+attrs]; attrs
0x180024ccc  mov     rdx, [rsp+370h+dn]; dn
0x180024cd1  mov     rcx, [rbp+270h+ld]; ld
0x180024cd5  call    cs:__imp_ldap_add_sW
0x180024cdb  test    eax, eax
0x180024cdd  jz      short loc_180024CE9
0x180024cdf  mov     ecx, eax; LdapError
0x180024ce1  call    cs:__imp_LdapMapErrorToWin32
0x180024ce7  mov     edi, eax
0x180024ce9  test    rsi, rsi
0x180024cec  jz      short loc_180024D30
0x180024cee  mov     ebx, r12d
0x180024cf1  test    r14d, r14d
0x180024cf4  jz      short loc_180024D1C
0x180024cf6  mov     eax, ebx
0x180024cf8  mov     r15, [rsi+rax*8]
0x180024cfc  test    r15, r15
0x180024cff  jz      short loc_180024D15
0x180024d01  call    cs:__imp_GetProcessHeap
0x180024d07  mov     rcx, rax; hHeap
0x180024d0a  mov     r8, r15; lpMem
0x180024d0d  xor     edx, edx; dwFlags
0x180024d0f  call    cs:__imp_HeapFree
0x180024d15  inc     ebx
0x180024d17  cmp     ebx, r14d
0x180024d1a  jb      short loc_180024CF6
0x180024d1c  call    cs:__imp_GetProcessHeap
0x180024d22  mov     rcx, rax; hHeap
0x180024d25  mov     r8, rsi; lpMem
0x180024d28  xor     edx, edx; dwFlags
0x180024d2a  call    cs:__imp_HeapFree
0x180024d30  lea     rcx, [rbp+270h+ld]
0x180024d34  call    NfsDisconnectLdap
0x180024d39  nop
0x180024d3a  lea     rcx, [rsp+370h+var_330]
0x180024d3f  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x180024d44  mov     eax, edi
0x180024d46  jmp     short loc_180024D57
0x180024d48  lea     rcx, [rsp+370h+var_330]
0x180024d4d  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x180024d52  mov     eax, 57h ; 'W'
0x180024d57  mov     rcx, [rbp+270h+var_40]
0x180024d5e  xor     rcx, rsp; StackCookie
0x180024d61  call    __security_check_cookie
0x180024d66  mov     rbx, [rsp+370h+arg_10]
0x180024d6e  add     rsp, 340h
0x180024d75  pop     r15
0x180024d77  pop     r14
0x180024d79  pop     r13
0x180024d7b  pop     r12
0x180024d7d  pop     rdi
0x180024d7e  pop     rsi
0x180024d7f  pop     rbp
0x180024d80  retn
```
