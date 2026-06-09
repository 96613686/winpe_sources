# SetNfsNetGroup(ushort const *,ushort const * *,ulong,ushort const * *,ulong,ushort const *,ushort const *,CNfsTaskContext *)

- ea: `0x1800254c0`
- end: `0x180025c72`
- name: `?SetNfsNetGroup@@YAKPEBGPEAPEBGK1K00PEAVCNfsTaskContext@@@Z`
- size: `1970`
- prototype: `unsigned int __usercall@<eax>(const unsigned __int16 *@<rcx>, const unsigned __int16 **@<rdx>, unsigned int@<r8d>, const unsigned __int16 **@<r9>, unsigned int, const unsigned __int16 *, const unsigned __int16 *, struct CNfsTaskContext *)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, service_task`

## callers

- `0x18001603c`

## callees

- `0x1800096cc`
- `0x180009704`
- `0x18000eae4`
- `0x180016248`
- `0x180018230`
- `0x1800182b8`
- `0x18001c028`
- `0x18001cba0`
- `0x180023ba0`
- `0x180023d04`
- `0x1800252d8`
- `0x180025430`
- `0x1800254c0`
- `0x180025de0`
- `0x180025e6c`
- `0x18002b368`
- `0x18002b4ac`
- `0x180035b02`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180025adb`
- `msvcrt!wcscpy_s` at `0x180025adb`
- `ntdll!RtlInitUnicodeString` at `0x18002559f`
- `ntdll!RtlInitUnicodeString` at `0x1800255ac`
- `ntdll!RtlInitUnicodeString` at `0x18002559f`
- `ntdll!RtlInitUnicodeString` at `0x1800255ac`
- `KERNEL32!HeapFree` at `0x1800258fb`
- `KERNEL32!HeapFree` at `0x180025bb0`
- `KERNEL32!HeapFree` at `0x180025bcb`
- `KERNEL32!HeapFree` at `0x1800258fb`
- `KERNEL32!HeapFree` at `0x180025bb0`
- `KERNEL32!HeapFree` at `0x180025bcb`
- `KERNEL32!HeapAlloc` at `0x180025a4c`
- `KERNEL32!HeapAlloc` at `0x180025aad`
- `KERNEL32!HeapAlloc` at `0x180025a4c`
- `KERNEL32!HeapAlloc` at `0x180025aad`
- `KERNEL32!GetProcessHeap` at `0x1800258eb`
- `KERNEL32!GetProcessHeap` at `0x180025a3c`
- `KERNEL32!GetProcessHeap` at `0x180025a9c`
- `KERNEL32!GetProcessHeap` at `0x180025ba2`
- `KERNEL32!GetProcessHeap` at `0x180025bbd`
- `KERNEL32!GetProcessHeap` at `0x1800258eb`
- `KERNEL32!GetProcessHeap` at `0x180025a3c`
- `KERNEL32!GetProcessHeap` at `0x180025a9c`
- `KERNEL32!GetProcessHeap` at `0x180025ba2`
- `KERNEL32!GetProcessHeap` at `0x180025bbd`
- `ADVAPI32!LsaNtStatusToWinError` at `0x1800255c5`
- `ADVAPI32!LsaNtStatusToWinError` at `0x1800255c5`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180025b87`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180025b87`
- `WLDAP32!__imp_ldap_first_entry` at `0x180025641`
- `WLDAP32!__imp_ldap_first_entry` at `0x180025641`
- `WLDAP32!__imp_ldap_msgfree` at `0x180025bdb`
- `WLDAP32!__imp_ldap_msgfree` at `0x180025bdb`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x18002569a`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x1800256cf`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x18002569a`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x1800256cf`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180025689`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800256ba`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180025689`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800256ba`
- `WLDAP32!__imp_ldap_modify_sW` at `0x180025b7b`
- `WLDAP32!__imp_ldap_modify_sW` at `0x180025b7b`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180025844`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180025844`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall SetNfsNetGroup(
        const unsigned __int16 *a1,
        const unsigned __int16 **a2,
        unsigned int a3,
        const unsigned __int16 **a4,
        unsigned int a5,
        const unsigned __int16 *SourceString,
        const unsigned __int16 *a7,
        struct CNfsTaskContext *a8)
{
  const unsigned __int16 *v11; // r13
  struct CNfsTaskContext *v12; // r12
  NTSTATUS v13; // eax
  ULONG v14; // r14d
  LDAPMessage *entry; // rax
  LDAPMessage *v16; // rdi
  PWCHAR *valuesW; // rax
  PWSTR *v18; // rbx
  PWCHAR *v19; // rax
  PWCHAR *v20; // r15
  ULONG v21; // r13d
  ULONG v22; // r12d
  __int64 v23; // rdi
  __int64 v24; // rbx
  __int64 v25; // rsi
  __int64 v26; // rsi
  __int64 v27; // rdx
  __int64 i; // rax
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // rdi
  __int64 v32; // rbx
  wchar_t **v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rdx
  HANDLE ProcessHeap; // rax
  __int64 v37; // rdx
  __int64 j; // rax
  __int64 v39; // rdi
  __int64 v40; // rbx
  wchar_t **v41; // r8
  __int64 v42; // rdx
  __int64 k; // rax
  SIZE_T v44; // rbx
  HANDLE v45; // rax
  _QWORD *v46; // rsi
  unsigned int v47; // r15d
  __int64 v48; // r12
  __int64 v49; // rbx
  SIZE_T v50; // rdi
  HANDLE v51; // rax
  wchar_t *v52; // rax
  const wchar_t *v53; // r8
  __int64 v54; // rdx
  __int64 m; // rax
  ULONG v56; // eax
  unsigned int n; // ebx
  void *v58; // rdi
  HANDLE v59; // rax
  HANDLE v60; // rax
  LPVOID lpMem; // [rsp+30h] [rbp-D0h] BYREF
  LDAPMessage *res; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v64[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v65[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v66[2]; // [rsp+60h] [rbp-A0h] BYREF
  PWSTR dn; // [rsp+70h] [rbp-90h]
  _QWORD v68[2]; // [rsp+78h] [rbp-88h] BYREF
  const unsigned __int16 *v69; // [rsp+88h] [rbp-78h]
  struct _UNICODE_STRING v70; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v72[8]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v73[8]; // [rsp+B8h] [rbp-48h] BYREF
  LDAP *ld[68]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t *Source[2]; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int64 v76; // [rsp+2F0h] [rbp+1F0h]
  unsigned __int64 v77; // [rsp+2F8h] [rbp+1F8h]
  _BYTE v78[32]; // [rsp+300h] [rbp+200h] BYREF
  LDAPModW *mods[2]; // [rsp+320h] [rbp+220h] BYREF
  __int64 v80; // [rsp+330h] [rbp+230h]
  unsigned __int16 *v81[3]; // [rsp+338h] [rbp+238h] BYREF
  int v82; // [rsp+350h] [rbp+250h] BYREF
  _QWORD v83[11]; // [rsp+358h] [rbp+258h] BYREF

  v11 = a1;
  v69 = a1;
  v12 = a8;
  lpMem = a8;
  v81[0] = L"nisNetgroupTriple";
  v81[1] = L"distinguishedName";
  v81[2] = 0;
  res = 0;
  std::set<std::wstring>::set<std::wstring>(v65);
  std::set<std::wstring>::set<std::wstring>(v64);
  std::set<std::wstring>::set<std::wstring>(v66);
  DestinationString = 0;
  v70 = 0;
  memset_0(ld, 0, 0x218u);
  if ( SourceString && *SourceString )
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
    RtlInitUnicodeString(&v70, a7);
    v13 = NfsConnectLdap(ld, &DestinationString, &v70);
    v14 = LsaNtStatusToWinError(v13);
    if ( v14 )
    {
LABEL_87:
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v66);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v64);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v65);
      return v14;
    }
    v14 = SearchForNetgroups(v11, v81, (struct _NFS_LDAP_CONNECTION *)ld, &res);
    if ( !v14 )
    {
      if ( !(unsigned __int8)CheckDuplicates(a2, a3, v65) && !(unsigned __int8)CheckDuplicates(a4, a5, v64) )
      {
        std::set<std::wstring>::set<std::wstring>(v68);
        entry = ldap_first_entry(ld[0], res);
        v16 = entry;
        if ( !entry )
        {
          v14 = 1168;
          (*(void (__fastcall **)(struct CNfsTaskContext *, __int64, __int64, const unsigned __int16 *))(*(_QWORD *)a8 + 40LL))(
            a8,
            1168,
            3221229603LL,
            v11);
LABEL_82:
          if ( res )
            ldap_msgfree(res);
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v68);
          goto LABEL_86;
        }
        dn = 0;
        valuesW = ldap_get_valuesW(ld[0], entry, (const PWSTR)L"distinguishedName");
        v18 = valuesW;
        if ( valuesW && ldap_count_valuesW(valuesW) )
          dn = *v18;
        v19 = ldap_get_valuesW(ld[0], v16, (const PWSTR)L"nisNetgroupTriple");
        v20 = v19;
        if ( v19 )
        {
          v21 = ldap_count_valuesW(v19);
          v22 = 0;
          if ( v21 )
          {
            while ( v22 < v21 )
            {
              v14 = ParseHost(v20[v22], v68);
              if ( v14 )
                break;
              v23 = v68[0];
              v24 = *(_QWORD *)v68[0];
              while ( v24 != v23 )
              {
                std::wstring::wstring(Source, v24 + 32);
                v25 = v65[0];
                if ( v25 != *(_QWORD *)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(
                                         v65,
                                         v72,
                                         Source) )
                  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::erase(
                    v65,
                    Source);
                v26 = v64[0];
                if ( v26 != *(_QWORD *)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(
                                         v64,
                                         v73,
                                         Source) )
                {
                  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::erase(
                    v64,
                    Source);
                  LOBYTE(v29) = 1;
                  std::wstring::_Tidy(Source, v29, 0);
                  goto LABEL_31;
                }
                LOBYTE(v27) = 1;
                std::wstring::_Tidy(Source, v27, 0);
                if ( !*(_BYTE *)(v24 + 25) )
                {
                  if ( *(_BYTE *)(*(_QWORD *)(v24 + 16) + 25LL) )
                  {
                    for ( i = *(_QWORD *)(v24 + 8);
                          !*(_BYTE *)(i + 25) && v24 == *(_QWORD *)(i + 16);
                          i = *(_QWORD *)(i + 8) )
                    {
                      v24 = i;
                    }
                  }
                  else
                  {
                    i = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Min();
                  }
                  v24 = i;
                }
              }
              std::wstring::wstring(v78, v20[v22]);
              std::set<std::wstring>::insert(v66, mods, v78);
              LOBYTE(v30) = 1;
              std::wstring::_Tidy(v78, v30, 0);
LABEL_31:
              std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::clear(v68);
              ++v22;
            }
          }
          ldap_value_freeW(v20);
          if ( v14 )
            goto LABEL_82;
          v12 = (struct CNfsTaskContext *)lpMem;
          v11 = v69;
        }
        lpMem = 0;
        v31 = v65[0];
        v32 = *(_QWORD *)v65[0];
        while ( v32 != v31 )
        {
          std::wstring::wstring(Source, v32 + 32);
          v33 = Source;
          if ( v77 >= 8 )
            v33 = (wchar_t **)Source[0];
          v14 = CreateNetGroupMemberTriple(v33, &lpMem);
          if ( v14 )
          {
            LOBYTE(v34) = 1;
            std::wstring::_Tidy(Source, v34, 0);
            break;
          }
          std::wstring::wstring(v78, lpMem);
          std::set<std::wstring>::insert(v66, mods, v78);
          LOBYTE(v35) = 1;
          std::wstring::_Tidy(v78, v35, 0);
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, lpMem);
          LOBYTE(v37) = 1;
          std::wstring::_Tidy(Source, v37, 0);
          if ( !*(_BYTE *)(v32 + 25) )
          {
            if ( *(_BYTE *)(*(_QWORD *)(v32 + 16) + 25LL) )
            {
              for ( j = *(_QWORD *)(v32 + 8); !*(_BYTE *)(j + 25) && v32 == *(_QWORD *)(j + 16); j = *(_QWORD *)(j + 8) )
                v32 = j;
            }
            else
            {
              j = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Min();
            }
            v32 = j;
          }
        }
        v39 = v64[0];
        v40 = *(_QWORD *)v64[0];
        while ( v40 != v39 )
        {
          std::wstring::wstring(Source, v40 + 32);
          v41 = Source;
          if ( v77 >= 8 )
            v41 = (wchar_t **)Source[0];
          (*(void (__fastcall **)(struct CNfsTaskContext *, __int64, wchar_t **, const unsigned __int16 *))(*(_QWORD *)v12 + 8LL))(
            v12,
            2147487776LL,
            v41,
            v11);
          LOBYTE(v42) = 1;
          std::wstring::_Tidy(Source, v42, 0);
          if ( !*(_BYTE *)(v40 + 25) )
          {
            if ( *(_BYTE *)(*(_QWORD *)(v40 + 16) + 25LL) )
            {
              for ( k = *(_QWORD *)(v40 + 8); !*(_BYTE *)(k + 25) && v40 == *(_QWORD *)(k + 16); k = *(_QWORD *)(k + 8) )
                v40 = k;
            }
            else
            {
              k = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Min();
            }
            v40 = k;
          }
        }
        if ( !v14 )
        {
          *(_OWORD *)mods = 0;
          v80 = 0;
          v82 = 0;
          memset_0(v83, 0, sizeof(v83));
          v44 = 8LL * v66[1] + 8;
          v45 = GetProcessHeap();
          v46 = HeapAlloc(v45, 8u, v44);
          if ( v46 )
          {
            v47 = 0;
            v48 = v66[0];
            v49 = *(_QWORD *)v66[0];
            while ( v49 != v48 )
            {
              std::wstring::wstring(Source, v49 + 32);
              v50 = 2 * v76 + 2;
              v51 = GetProcessHeap();
              v52 = (wchar_t *)HeapAlloc(v51, 8u, v50);
              v46[v47] = v52;
              v53 = (const wchar_t *)Source;
              if ( v77 >= 8 )
                v53 = Source[0];
              wcscpy_s(v52, v76 + 1, v53);
              ++v47;
              LOBYTE(v54) = 1;
              std::wstring::_Tidy(Source, v54, 0);
              if ( !*(_BYTE *)(v49 + 25) )
              {
                if ( *(_BYTE *)(*(_QWORD *)(v49 + 16) + 25LL) )
                {
                  for ( m = *(_QWORD *)(v49 + 8); !*(_BYTE *)(m + 25) && v49 == *(_QWORD *)(m + 16); m = *(_QWORD *)(m + 8) )
                    v49 = m;
                }
                else
                {
                  m = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Min();
                }
                v49 = m;
              }
            }
            v46[v47] = 0;
            v82 = 2;
            v83[0] = L"nisNetgroupTriple";
            v83[1] = v46;
            mods[0] = (LDAPModW *)&v82;
            mods[1] = 0;
            v56 = ldap_modify_sW(ld[0], dn, mods);
            if ( v56 )
              v14 = LdapMapErrorToWin32(v56);
            for ( n = 0; n < v47; ++n )
            {
              v58 = (void *)v46[n];
              if ( v58 )
              {
                v59 = GetProcessHeap();
                HeapFree(v59, 0, v58);
              }
            }
            v60 = GetProcessHeap();
            HeapFree(v60, 0, v46);
          }
          else
          {
            v14 = 8;
          }
        }
        goto LABEL_82;
      }
      v14 = 87;
    }
LABEL_86:
    NfsDisconnectLdap(ld);
    goto LABEL_87;
  }
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v66);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v64);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v65);
  return 87;
}

```

## disassembly

```asm
0x1800254c0  mov     [rsp-8+arg_10], rbx
0x1800254c5  push    rbp
0x1800254c6  push    rsi
0x1800254c7  push    rdi
0x1800254c8  push    r12
0x1800254ca  push    r13
0x1800254cc  push    r14
0x1800254ce  push    r15
0x1800254d0  lea     rbp, [rsp-2C0h]
0x1800254d8  sub     rsp, 3C0h
0x1800254df  mov     rax, cs:__security_cookie
0x1800254e6  xor     rax, rsp
0x1800254e9  mov     [rbp+2F0h+var_40], rax
0x1800254f0  mov     rdi, r9
0x1800254f3  mov     esi, r8d
0x1800254f6  mov     r15, rdx
0x1800254f9  mov     r13, rcx
0x1800254fc  mov     [rbp+2F0h+var_368], rcx
0x180025500  mov     rbx, [rbp+2F0h+SourceString]
0x180025507  mov     r14, [rbp+2F0h+arg_30]
0x18002550e  mov     r12, [rbp+2F0h+arg_38]
0x180025515  mov     [rsp+3F0h+lpMem], r12
0x18002551a  lea     rax, aNisnetgrouptri; "nisNetgroupTriple"
0x180025521  mov     [rbp+2F0h+var_B8], rax
0x180025528  lea     rax, attr; "distinguishedName"
0x18002552f  mov     [rbp+2F0h+var_B0], rax
0x180025536  xor     eax, eax
0x180025538  mov     [rbp+2F0h+var_A8], rax
0x18002553f  mov     [rsp+3F0h+res], rax
0x180025544  lea     rcx, [rsp+3F0h+var_3A0]
0x180025549  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x18002554e  nop
0x18002554f  lea     rcx, [rsp+3F0h+var_3B0]
0x180025554  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x180025559  nop
0x18002555a  lea     rcx, [rsp+3F0h+var_390]
0x18002555f  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x180025564  nop
0x180025565  xorps   xmm0, xmm0
0x180025568  movups  xmmword ptr [rbp+2F0h+DestinationString.Length], xmm0
0x18002556c  xorps   xmm1, xmm1
0x18002556f  movups  xmmword ptr [rbp+2F0h+var_360.Length], xmm1
0x180025573  xor     edx, edx; Val
0x180025575  mov     r8d, 218h; Size
0x18002557b  lea     rcx, [rbp+2F0h+ld]; void *
0x18002557f  call    memset_0
0x180025584  xor     eax, eax
0x180025586  test    rbx, rbx
0x180025589  jz      loc_180025C23
0x18002558f  cmp     [rbx], ax
0x180025592  jz      loc_180025C23
0x180025598  mov     rdx, rbx; SourceString
0x18002559b  lea     rcx, [rbp+2F0h+DestinationString]; DestinationString
0x18002559f  call    cs:__imp_RtlInitUnicodeString
0x1800255a5  mov     rdx, r14; SourceString
0x1800255a8  lea     rcx, [rbp+2F0h+var_360]; DestinationString
0x1800255ac  call    cs:__imp_RtlInitUnicodeString
0x1800255b2  lea     r8, [rbp+2F0h+var_360]
0x1800255b6  lea     rdx, [rbp+2F0h+DestinationString]
0x1800255ba  lea     rcx, [rbp+2F0h+ld]
0x1800255be  call    NfsConnectLdap
0x1800255c3  mov     ecx, eax; Status
0x1800255c5  call    cs:__imp_LsaNtStatusToWinError
0x1800255cb  mov     r14d, eax
0x1800255ce  test    eax, eax
0x1800255d0  jnz     loc_180025BFE
0x1800255d6  lea     r9, [rsp+3F0h+res]; struct ldapmsg **
0x1800255db  lea     r8, [rbp+2F0h+ld]; struct _NFS_LDAP_CONNECTION *
0x1800255df  lea     rdx, [rbp+2F0h+var_B8]; unsigned __int16 **
0x1800255e6  mov     rcx, r13; unsigned __int16 *
0x1800255e9  call    ?SearchForNetgroups@@YAKPEBGPEAPEAGPEAU_NFS_LDAP_CONNECTION@@PEAPEAUldapmsg@@@Z; SearchForNetgroups(ushort const *,ushort * *,_NFS_LDAP_CONNECTION *,ldapmsg * *)
0x1800255ee  mov     r14d, eax
0x1800255f1  test    eax, eax
0x1800255f3  jnz     loc_180025BF4
0x1800255f9  lea     r8, [rsp+3F0h+var_3A0]
0x1800255fe  mov     edx, esi
0x180025600  mov     rcx, r15
0x180025603  call    ?CheckDuplicates@@YAEPEAPEBGKAEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; CheckDuplicates(ushort const * *,ulong,std::set<std::wstring> &)
0x180025608  xor     esi, esi
0x18002560a  test    al, al
0x18002560c  jnz     loc_180025BEE
0x180025612  lea     r8, [rsp+3F0h+var_3B0]
0x180025617  mov     edx, [rbp+2F0h+arg_20]
0x18002561d  mov     rcx, rdi
0x180025620  call    ?CheckDuplicates@@YAEPEAPEBGKAEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; CheckDuplicates(ushort const * *,ulong,std::set<std::wstring> &)
0x180025625  test    al, al
0x180025627  jnz     loc_180025BEE
0x18002562d  lea     rcx, [rsp+3F0h+var_378]
0x180025632  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x180025637  nop
0x180025638  mov     rdx, [rsp+3F0h+res]; res
0x18002563d  mov     rcx, [rbp+2F0h+ld]; ld
0x180025641  call    cs:__imp_ldap_first_entry
0x180025647  mov     rdi, rax
0x18002564a  test    rax, rax
0x18002564d  jnz     short loc_180025676
0x18002564f  mov     r14d, 490h
0x180025655  mov     rax, [r12]
0x180025659  mov     r9, r13
0x18002565c  mov     r8d, 0C0001023h
0x180025662  mov     edx, r14d
0x180025665  mov     rcx, r12
0x180025668  mov     rax, [rax+28h]
0x18002566c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025671  jmp     loc_180025BD1
0x180025676  mov     [rsp+3F0h+dn], rsi
0x18002567b  lea     r8, attr; "distinguishedName"
0x180025682  mov     rdx, rdi; entry
0x180025685  mov     rcx, [rbp+2F0h+ld]; ld
0x180025689  call    cs:__imp_ldap_get_valuesW
0x18002568f  mov     rbx, rax
0x180025692  test    rax, rax
0x180025695  jz      short loc_1800256AC
0x180025697  mov     rcx, rax; vals
0x18002569a  call    cs:__imp_ldap_count_valuesW
0x1800256a0  test    eax, eax
0x1800256a2  jz      short loc_1800256AC
0x1800256a4  mov     rax, [rbx]
0x1800256a7  mov     [rsp+3F0h+dn], rax
0x1800256ac  lea     r8, aNisnetgrouptri; "nisNetgroupTriple"
0x1800256b3  mov     rdx, rdi; entry
0x1800256b6  mov     rcx, [rbp+2F0h+ld]; ld
0x1800256ba  call    cs:__imp_ldap_get_valuesW
0x1800256c0  mov     r15, rax
0x1800256c3  test    rax, rax
0x1800256c6  jz      loc_18002585C
0x1800256cc  mov     rcx, rax; vals
0x1800256cf  call    cs:__imp_ldap_count_valuesW
0x1800256d5  mov     r13d, eax
0x1800256d8  mov     r12d, esi
0x1800256db  test    eax, eax
0x1800256dd  jz      loc_180025841
0x1800256e3  cmp     r12d, r13d
0x1800256e6  jnb     loc_180025841
0x1800256ec  movsxd  rsi, r12d
0x1800256ef  lea     rdx, [rsp+3F0h+var_378]
0x1800256f4  mov     rcx, [r15+rsi*8]
0x1800256f8  call    ?ParseHost@@YAKPEAGAEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; ParseHost(ushort *,std::set<std::wstring> &)
0x1800256fd  mov     r14d, eax
0x180025700  xor     esi, esi
0x180025702  test    eax, eax
0x180025704  jnz     loc_180025841
0x18002570a  mov     rdi, [rsp+3F0h+var_378]
0x18002570f  mov     rbx, [rdi]
0x180025712  cmp     rbx, rdi
0x180025715  jz      loc_1800257F1
0x18002571b  lea     rdx, [rbx+20h]
0x18002571f  lea     rcx, [rbp+2F0h+Source]
0x180025726  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002572b  nop
0x18002572c  mov     rsi, [rsp+3F0h+var_3A0]
0x180025731  lea     r8, [rbp+2F0h+Source]
0x180025738  lea     rdx, [rbp+2F0h+var_340]
0x18002573c  lea     rcx, [rsp+3F0h+var_3A0]
0x180025741  call    ?find@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x180025746  cmp     rsi, [rax]
0x180025749  jz      short loc_18002575C
0x18002574b  lea     rdx, [rbp+2F0h+Source]
0x180025752  lea     rcx, [rsp+3F0h+var_3A0]
0x180025757  call    ?erase@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::erase(std::wstring const &)
0x18002575c  mov     rsi, [rsp+3F0h+var_3B0]
0x180025761  lea     r8, [rbp+2F0h+Source]
0x180025768  lea     rdx, [rbp+2F0h+var_338]
0x18002576c  lea     rcx, [rsp+3F0h+var_3B0]
0x180025771  call    ?find@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x180025776  cmp     rsi, [rax]
0x180025779  jnz     short loc_1800257CA
0x18002577b  xor     r8d, r8d
0x18002577e  mov     dl, 1
0x180025780  lea     rcx, [rbp+2F0h+Source]
0x180025787  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002578c  xor     esi, esi
0x18002578e  cmp     [rbx+19h], sil
0x180025792  jnz     loc_180025712
0x180025798  mov     rcx, [rbx+10h]
0x18002579c  cmp     [rcx+19h], sil
0x1800257a0  jnz     short loc_1800257A9
0x1800257a2  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Min(std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x1800257a7  jmp     short loc_1800257C2
0x1800257a9  mov     rax, [rbx+8]
0x1800257ad  jmp     short loc_1800257BC
0x1800257af  cmp     rbx, [rax+10h]
0x1800257b3  jnz     short loc_1800257C2
0x1800257b5  mov     rbx, rax
0x1800257b8  mov     rax, [rax+8]
0x1800257bc  cmp     [rax+19h], sil
0x1800257c0  jz      short loc_1800257AF
0x1800257c2  mov     rbx, rax
0x1800257c5  jmp     loc_180025712
0x1800257ca  lea     rdx, [rbp+2F0h+Source]
0x1800257d1  lea     rcx, [rsp+3F0h+var_3B0]
0x1800257d6  call    ?erase@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::erase(std::wstring const &)
0x1800257db  nop
0x1800257dc  xor     r8d, r8d
0x1800257df  mov     dl, 1
0x1800257e1  lea     rcx, [rbp+2F0h+Source]
0x1800257e8  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800257ed  xor     esi, esi
0x1800257ef  jmp     short loc_18002582F
0x1800257f1  movsxd  rdx, r12d
0x1800257f4  mov     rdx, [r15+rdx*8]
0x1800257f8  lea     rcx, [rbp+2F0h+var_F0]
0x1800257ff  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180025804  nop
0x180025805  lea     r8, [rbp+2F0h+var_F0]
0x18002580c  lea     rdx, [rbp+2F0h+mods]
0x180025813  lea     rcx, [rsp+3F0h+var_390]
0x180025818  call    ?insert@?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@2@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::set<std::wstring>::insert(std::wstring &&)
0x18002581d  nop
0x18002581e  xor     r8d, r8d
0x180025821  mov     dl, 1
0x180025823  lea     rcx, [rbp+2F0h+var_F0]
0x18002582a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002582f  lea     rcx, [rsp+3F0h+var_378]
0x180025834  call    ?clear@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::clear(void)
0x180025839  inc     r12d
0x18002583c  jmp     loc_1800256E3
0x180025841  mov     rcx, r15; vals
0x180025844  call    cs:__imp_ldap_value_freeW
0x18002584a  test    r14d, r14d
0x18002584d  jnz     loc_180025BD1
0x180025853  mov     r12, [rsp+3F0h+lpMem]
0x180025858  mov     r13, [rbp+2F0h+var_368]
0x18002585c  mov     [rsp+3F0h+lpMem], rsi
0x180025861  mov     rdi, [rsp+3F0h+var_3A0]
0x180025866  mov     rbx, [rdi]
0x180025869  cmp     rbx, rdi
0x18002586c  jz      loc_180025960
0x180025872  lea     rdx, [rbx+20h]
0x180025876  lea     rcx, [rbp+2F0h+Source]
0x18002587d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180025882  nop
0x180025883  lea     rcx, [rbp+2F0h+Source]
0x18002588a  cmp     [rbp+2F0h+var_F8], 8
0x180025892  cmovnb  rcx, [rbp+2F0h+Source]
0x18002589a  lea     rdx, [rsp+3F0h+lpMem]
0x18002589f  call    CreateNetGroupMemberTriple
0x1800258a4  mov     r14d, eax
0x1800258a7  test    eax, eax
0x1800258a9  jnz     loc_18002594F
0x1800258af  mov     rdx, [rsp+3F0h+lpMem]
0x1800258b4  lea     rcx, [rbp+2F0h+var_F0]
0x1800258bb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800258c0  nop
0x1800258c1  lea     r8, [rbp+2F0h+var_F0]
0x1800258c8  lea     rdx, [rbp+2F0h+mods]
0x1800258cf  lea     rcx, [rsp+3F0h+var_390]
0x1800258d4  call    ?insert@?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@2@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::set<std::wstring>::insert(std::wstring &&)
0x1800258d9  nop
0x1800258da  xor     r8d, r8d
0x1800258dd  mov     dl, 1
0x1800258df  lea     rcx, [rbp+2F0h+var_F0]
0x1800258e6  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800258eb  call    cs:__imp_GetProcessHeap
0x1800258f1  mov     rcx, rax; hHeap
0x1800258f4  mov     r8, [rsp+3F0h+lpMem]; lpMem
0x1800258f9  xor     edx, edx; dwFlags
0x1800258fb  call    cs:__imp_HeapFree
0x180025901  nop
0x180025902  xor     r8d, r8d
0x180025905  mov     dl, 1
0x180025907  lea     rcx, [rbp+2F0h+Source]
0x18002590e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180025913  cmp     [rbx+19h], sil
0x180025917  jnz     loc_180025869
0x18002591d  mov     rcx, [rbx+10h]
0x180025921  cmp     [rcx+19h], sil
0x180025925  jnz     short loc_18002592E
0x180025927  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Min(std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x18002592c  jmp     short loc_180025947
0x18002592e  mov     rax, [rbx+8]
0x180025932  jmp     short loc_180025941
0x180025934  cmp     rbx, [rax+10h]
0x180025938  jnz     short loc_180025947
0x18002593a  mov     rbx, rax
0x18002593d  mov     rax, [rax+8]
0x180025941  cmp     [rax+19h], sil
0x180025945  jz      short loc_180025934
0x180025947  mov     rbx, rax
0x18002594a  jmp     loc_180025869
0x18002594f  xor     r8d, r8d
0x180025952  mov     dl, 1
0x180025954  lea     rcx, [rbp+2F0h+Source]
0x18002595b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180025960  mov     rdi, [rsp+3F0h+var_3B0]
0x180025965  mov     rbx, [rdi]
0x180025968  cmp     rbx, rdi
0x18002596b  jz      loc_1800259FB
0x180025971  lea     rdx, [rbx+20h]
0x180025975  lea     rcx, [rbp+2F0h+Source]
0x18002597c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180025981  nop
0x180025982  mov     rax, [r12]
0x180025986  lea     r8, [rbp+2F0h+Source]
0x18002598d  cmp     [rbp+2F0h+var_F8], 8
0x180025995  cmovnb  r8, [rbp+2F0h+Source]
0x18002599d  mov     r9, r13
0x1800259a0  mov     edx, 80001020h
0x1800259a5  mov     rcx, r12
0x1800259a8  mov     rax, [rax+8]
  ... truncated ...
```
