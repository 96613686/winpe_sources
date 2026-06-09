# AENeedToUpdateDSCache(ldap *,ushort *,ushort *,int,_AE_DS_INFO_ *)

- ea: `0x180003ed0`
- end: `0x18000425e`
- name: `?AENeedToUpdateDSCache@@YAHPEAUldap@@PEAG1HPEAU_AE_DS_INFO_@@@Z`
- size: `910`
- prototype: `__int64 __fastcall(LDAP *ld, unsigned __int16 *, unsigned __int16 *, int, struct _AE_DS_INFO_ *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180003d10`

## callees

- `0x180003ed0`
- `0x180004630`
- `0x180005040`

## import_xrefs

- `msvcrt!_wtoi64` at `0x180004094`
- `msvcrt!_wtoi64` at `0x180004094`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000417d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800041c6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000417d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800041c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004136`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004136`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000420c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000421b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000420c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000421b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000410e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000410e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003fac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003fac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800041ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800041ed`
- `WLDAP32!__imp_ldap_first_entry` at `0x18000405f`
- `WLDAP32!__imp_ldap_first_entry` at `0x18000405f`
- `WLDAP32!__imp_ldap_next_entry` at `0x1800040b8`
- `WLDAP32!__imp_ldap_next_entry` at `0x1800040b8`
- `WLDAP32!__imp_ldap_count_entries` at `0x18000404f`
- `WLDAP32!__imp_ldap_count_entries` at `0x18000404f`
- `WLDAP32!__imp_ldap_msgfree` at `0x18000422a`
- `WLDAP32!__imp_ldap_msgfree` at `0x18000422a`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000407a`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000407a`
- `WLDAP32!__imp_ldap_search_stW` at `0x18000403a`
- `WLDAP32!__imp_ldap_search_stW` at `0x18000403a`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800040ac`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800040c3`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800040ac`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800040c3`

## string_xrefs

- `0x1800040ec`: `SOFTWARE\Microsoft\Cryptography\AutoEnrollment\AEDirectoryCache`
- `0x180003f31`: `CN=Public Key Services,CN=Services,`
- `0x180003ef1`: `CN=OID,CN=Public Key Services,CN=Services,`

## pseudocode

```c
__int64 __fastcall AENeedToUpdateDSCache(
        LDAP *ld,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4,
        struct _AE_DS_INFO_ *a5)
{
  const unsigned __int16 *v6; // rbx
  unsigned int v8; // r13d
  struct _AE_DS_INFO_ *v9; // rsi
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned __int64 v13; // r14
  unsigned __int16 *v14; // rax
  WCHAR *v15; // r15
  int v16; // r14d
  WCHAR *v17; // r9
  ULONG v18; // eax
  LDAPMessage *v19; // rdx
  LDAPMessage *i; // rax
  LDAPMessage *v21; // rdi
  const wchar_t **valuesW; // rax
  PWCHAR *v23; // rbx
  unsigned __int64 v24; // rax
  const WCHAR *v25; // rdx
  const WCHAR *v26; // rdx
  __int64 result; // rax
  DWORD Type; // [rsp+58h] [rbp-31h] BYREF
  BYTE Data[4]; // [rsp+5Ch] [rbp-2Dh] BYREF
  HKEY hKey; // [rsp+60h] [rbp-29h] BYREF
  PLDAPMessage res; // [rsp+68h] [rbp-21h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-19h] BYREF
  l_timeval timeout; // [rsp+78h] [rbp-11h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-9h] BYREF
  BYTE v35[8]; // [rsp+88h] [rbp-1h] BYREF
  PWSTR attrs[2]; // [rsp+90h] [rbp+7h] BYREF
  DWORD cbData; // [rsp+E8h] [rbp+5Fh] BYREF
  LPCWSTR lpSubKey; // [rsp+F0h] [rbp+67h]
  int v39; // [rsp+100h] [rbp+77h]

  v39 = a4;
  lpSubKey = a2;
  v6 = L"CN=OID,CN=Public Key Services,CN=Services,";
  *(_DWORD *)Data = 0;
  *(_QWORD *)v35 = 0;
  Type = 0;
  v8 = 1;
  cbData = 0;
  dwDisposition = 0;
  timeout = 0;
  attrs[1] = 0;
  phkResult = 0;
  hKey = 0;
  res = 0;
  if ( !a4 )
    v6 = L"CN=Public Key Services,CN=Services,";
  attrs[0] = (PWSTR)L"uSNChanged";
  if ( ld && a2 && a3 )
  {
    v9 = a5;
    if ( a5 )
    {
      v10 = -1;
      v11 = -1;
      *(_OWORD *)a5 = 0;
      do
        ++v11;
      while ( a3[v11] );
      while ( v6[++v10] != 0 )
        ;
      v13 = v11 + v10 + 1;
      v14 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v13);
      v15 = v14;
      if ( v14 )
      {
        if ( !(unsigned int)StringCchCopyW(v14, v13, v6) && !StringCchCatW(v15, v13, a3) )
        {
          v16 = v39;
          timeout = (l_timeval)300LL;
          v17 = 0;
          if ( !v39 )
            v17 = (WCHAR *)L"(objectCategory=certificationAuthority)";
          if ( !ldap_search_stW(ld, v15, 2 - (v39 != 0), v17, attrs, 0, &timeout, &res) )
          {
            v18 = ldap_count_entries(ld, res);
            v19 = res;
            *((_DWORD *)v9 + 1) = v18;
            for ( i = ldap_first_entry(ld, v19); ; i = ldap_next_entry(ld, v21) )
            {
              v21 = i;
              if ( !i )
                break;
              valuesW = (const wchar_t **)ldap_get_valuesW(ld, i, (const PWSTR)L"uSNChanged");
              v23 = (PWCHAR *)valuesW;
              if ( !valuesW )
                goto LABEL_38;
              if ( !*valuesW || (v24 = _wtoi64(*valuesW)) == 0 )
              {
                ldap_value_freeW(v23);
                goto LABEL_38;
              }
              if ( *((_QWORD *)v9 + 1) < v24 )
                *((_QWORD *)v9 + 1) = v24;
              ldap_value_freeW(v23);
            }
            *(_DWORD *)v9 = 1;
            if ( !RegCreateKeyExW(
                    HKEY_LOCAL_MACHINE,
                    L"SOFTWARE\\Microsoft\\Cryptography\\AutoEnrollment\\AEDirectoryCache",
                    0,
                    (LPWSTR)&Class,
                    0,
                    0xF003Fu,
                    0,
                    &phkResult,
                    &dwDisposition)
              && !RegOpenKeyExW(phkResult, lpSubKey, 0, 0xF003Fu, &hKey) )
            {
              cbData = 4;
              v25 = L"OIDObjectCount";
              if ( !v16 )
                v25 = L"AEObjectCount";
              if ( !RegQueryValueExW(hKey, v25, 0, &Type, Data, &cbData) && Type == 4 )
              {
                cbData = 8;
                v26 = L"OIDMaxUSN";
                if ( !v16 )
                  v26 = L"AEMaxUSN";
                if ( !RegQueryValueExW(hKey, v26, 0, &Type, v35, &cbData)
                  && Type == 3
                  && *(_DWORD *)Data == *((_DWORD *)v9 + 1)
                  && *(_QWORD *)v35 == *((_QWORD *)v9 + 1) )
                {
                  v8 = 0;
                }
              }
            }
          }
        }
LABEL_38:
        LocalFree(v15);
      }
      if ( hKey )
        RegCloseKey(hKey);
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( res )
        ldap_msgfree(res);
      goto LABEL_46;
    }
    return 1;
  }
  v9 = a5;
  if ( !a5 )
    return 1;
LABEL_46:
  result = v8;
  if ( !v8 )
    *(_OWORD *)v9 = 0;
  return result;
}

```

## disassembly

```asm
0x180003ed0  mov     rax, rsp
0x180003ed3  mov     [rax+20h], r9d
0x180003ed7  mov     [rax+10h], rdx
0x180003edb  push    rbp
0x180003edc  push    rbx
0x180003edd  push    rsi
0x180003ede  push    rdi
0x180003edf  push    r12
0x180003ee1  push    r13
0x180003ee3  lea     rbp, [rax-57h]
0x180003ee7  sub     rsp, 0A8h
0x180003eee  mov     r12, rcx
0x180003ef1  lea     rbx, aCnOidCnPublicK; "CN=OID,CN=Public Key Services,CN=Servic"...
0x180003ef8  xor     ecx, ecx
0x180003efa  mov     rdi, r8
0x180003efd  test    r9d, r9d
0x180003f00  mov     dword ptr [rbp+4Fh+Data], ecx
0x180003f03  mov     qword ptr [rbp+4Fh+var_50], rcx
0x180003f07  lea     r8, attr; "uSNChanged"
0x180003f0e  mov     [rbp+4Fh+Type], ecx
0x180003f11  mov     r13d, 1
0x180003f17  mov     [rbp+4Fh+cbData], ecx
0x180003f1a  mov     [rbp+4Fh+dwDisposition], ecx
0x180003f1d  mov     qword ptr [rbp+4Fh+var_60.tv_sec], rcx
0x180003f21  mov     [rbp+4Fh+var_40], rcx
0x180003f25  mov     [rbp+4Fh+phkResult], rcx
0x180003f29  mov     [rbp+4Fh+hKey], rcx
0x180003f2d  mov     [rbp+4Fh+var_70], rcx
0x180003f31  lea     rcx, aCnPublicKeySer; "CN=Public Key Services,CN=Services,"
0x180003f38  cmovz   rbx, rcx
0x180003f3c  mov     [rbp+4Fh+var_48], r8
0x180003f40  test    r12, r12
0x180003f43  jz      loc_180004232
0x180003f49  test    rdx, rdx
0x180003f4c  jz      loc_180004232
0x180003f52  test    rdi, rdi
0x180003f55  jz      loc_180004232
0x180003f5b  mov     rsi, [rbp+4Fh+arg_20]
0x180003f5f  test    rsi, rsi
0x180003f62  jz      loc_18000424B
0x180003f68  mov     [rax+18h], r14
0x180003f6c  xorps   xmm0, xmm0
0x180003f6f  mov     [rax-38h], r15
0x180003f73  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003f7a  mov     rcx, rax
0x180003f7d  movups  xmmword ptr [rsi], xmm0
0x180003f80  inc     rcx
0x180003f83  cmp     word ptr [rdi+rcx*2], 0
0x180003f88  jnz     short loc_180003F80
0x180003f8a  nop     word ptr [rax+rax+00h]
0x180003f90  cmp     word ptr [rbx+rax*2+2], 0
0x180003f96  lea     rax, [rax+1]
0x180003f9a  jnz     short loc_180003F90
0x180003f9c  lea     r14, [rax+1]
0x180003fa0  add     r14, rcx
0x180003fa3  mov     ecx, 40h ; '@'; uFlags
0x180003fa8  lea     rdx, [r14+r14]; uBytes
0x180003fac  call    cs:__imp_LocalAlloc
0x180003fb2  mov     r15, rax
0x180003fb5  test    rax, rax
0x180003fb8  jz      loc_1800041F3
0x180003fbe  mov     r8, rbx; unsigned __int16 *
0x180003fc1  mov     rdx, r14; unsigned __int64
0x180003fc4  mov     rcx, rax; unsigned __int16 *
0x180003fc7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003fcc  test    eax, eax
0x180003fce  jnz     loc_1800041EA
0x180003fd4  mov     r8, rdi; unsigned __int16 *
0x180003fd7  mov     rdx, r14; unsigned __int64
0x180003fda  mov     rcx, r15; unsigned __int16 *
0x180003fdd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003fe2  test    eax, eax
0x180003fe4  jnz     loc_1800041EA
0x180003fea  mov     r14d, [rbp+4Fh+arg_18]
0x180003fee  lea     rax, filter; "(objectCategory=certificationAuthority)"
0x180003ff5  xor     ebx, ebx
0x180003ff7  mov     qword ptr [rbp+4Fh+var_60.tv_sec], 12Ch
0x180003fff  test    r14d, r14d
0x180004002  mov     r9d, ebx
0x180004005  mov     rdx, r15; base
0x180004008  mov     rcx, r12; ld
0x18000400b  cmovz   r9, rax; filter
0x18000400f  mov     eax, r14d
0x180004012  neg     eax
0x180004014  lea     rax, [rbp+4Fh+var_70]
0x180004018  mov     [rsp+0D0h+res], rax; res
0x18000401d  sbb     r8d, r8d
0x180004020  lea     rax, [rbp+4Fh+var_60]
0x180004024  add     r8d, 2; scope
0x180004028  mov     [rsp+0D0h+timeout], rax; timeout
0x18000402d  lea     rax, [rbp+4Fh+var_48]
0x180004031  mov     [rsp+0D0h+attrsonly], ebx; attrsonly
0x180004035  mov     [rsp+0D0h+attrs], rax; attrs
0x18000403a  call    cs:__imp_ldap_search_stW
0x180004040  test    eax, eax
0x180004042  jnz     loc_1800041EA
0x180004048  mov     rdx, [rbp+4Fh+var_70]; res
0x18000404c  mov     rcx, r12; ld
0x18000404f  call    cs:__imp_ldap_count_entries
0x180004055  mov     rdx, [rbp+4Fh+var_70]; res
0x180004059  mov     rcx, r12; ld
0x18000405c  mov     [rsi+4], eax
0x18000405f  call    cs:__imp_ldap_first_entry
0x180004065  mov     rdi, rax
0x180004068  test    rax, rax
0x18000406b  jz      short loc_1800040CE
0x18000406d  lea     r8, attr; "uSNChanged"
0x180004074  mov     rdx, rax; entry
0x180004077  mov     rcx, r12; ld
0x18000407a  call    cs:__imp_ldap_get_valuesW
0x180004080  mov     rbx, rax
0x180004083  test    rax, rax
0x180004086  jz      loc_1800041EA
0x18000408c  mov     rcx, [rax]; String
0x18000408f  test    rcx, rcx
0x180004092  jz      short loc_1800040C0
0x180004094  call    cs:__imp__wtoi64
0x18000409a  test    rax, rax
0x18000409d  jz      short loc_1800040C0
0x18000409f  cmp     [rsi+8], rax
0x1800040a3  jnb     short loc_1800040A9
0x1800040a5  mov     [rsi+8], rax
0x1800040a9  mov     rcx, rbx; vals
0x1800040ac  call    cs:__imp_ldap_value_freeW
0x1800040b2  mov     rdx, rdi; entry
0x1800040b5  mov     rcx, r12; ld
0x1800040b8  call    cs:__imp_ldap_next_entry
0x1800040be  jmp     short loc_180004065
0x1800040c0  mov     rcx, rbx; vals
0x1800040c3  call    cs:__imp_ldap_value_freeW
0x1800040c9  jmp     loc_1800041EA
0x1800040ce  lea     rax, [rbp+4Fh+dwDisposition]
0x1800040d2  mov     [rsi], r13d
0x1800040d5  mov     [rsp+40h], rax; lpdwDisposition
0x1800040da  lea     r9, Class; lpClass
0x1800040e1  lea     rax, [rbp+4Fh+phkResult]
0x1800040e5  xor     ebx, ebx
0x1800040e7  mov     [rsp+0D0h+res], rax; phkResult
0x1800040ec  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Cryptography\\Auto"...
0x1800040f3  mov     [rsp+0D0h+timeout], rbx; lpSecurityAttributes
0x1800040f8  xor     r8d, r8d; Reserved
0x1800040fb  mov     [rsp+0D0h+attrsonly], 0F003Fh; samDesired
0x180004103  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000410a  mov     dword ptr [rsp+0D0h+attrs], ebx; dwOptions
0x18000410e  call    cs:__imp_RegCreateKeyExW
0x180004114  test    eax, eax
0x180004116  jnz     loc_1800041EA
0x18000411c  mov     rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x180004120  lea     rax, [rbp+4Fh+hKey]
0x180004124  mov     rcx, [rbp+4Fh+phkResult]; hKey
0x180004128  mov     r9d, 0F003Fh; samDesired
0x18000412e  xor     r8d, r8d; ulOptions
0x180004131  mov     [rsp+0D0h+attrs], rax; phkResult
0x180004136  call    cs:__imp_RegOpenKeyExW
0x18000413c  test    eax, eax
0x18000413e  jnz     loc_1800041EA
0x180004144  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180004148  lea     rax, aAeobjectcount; "AEObjectCount"
0x18000414f  test    r14d, r14d
0x180004152  mov     [rbp+4Fh+cbData], 4
0x180004159  lea     rdx, aOidobjectcount; "OIDObjectCount"
0x180004160  cmovz   rdx, rax; lpValueName
0x180004164  lea     r9, [rbp+4Fh+Type]; lpType
0x180004168  lea     rax, [rbp+4Fh+cbData]
0x18000416c  xor     r8d, r8d; lpReserved
0x18000416f  mov     qword ptr [rsp+0D0h+attrsonly], rax; lpcbData
0x180004174  lea     rax, [rbp+4Fh+Data]
0x180004178  mov     [rsp+0D0h+attrs], rax; lpData
0x18000417d  call    cs:__imp_RegQueryValueExW
0x180004183  test    eax, eax
0x180004185  jnz     short loc_1800041EA
0x180004187  cmp     [rbp+4Fh+Type], 4
0x18000418b  jnz     short loc_1800041EA
0x18000418d  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180004191  lea     rax, aAemaxusn; "AEMaxUSN"
0x180004198  test    r14d, r14d
0x18000419b  mov     [rbp+4Fh+cbData], 8
0x1800041a2  lea     rdx, aOidmaxusn; "OIDMaxUSN"
0x1800041a9  cmovz   rdx, rax; lpValueName
0x1800041ad  lea     r9, [rbp+4Fh+Type]; lpType
0x1800041b1  lea     rax, [rbp+4Fh+cbData]
0x1800041b5  xor     r8d, r8d; lpReserved
0x1800041b8  mov     qword ptr [rsp+0D0h+attrsonly], rax; lpcbData
0x1800041bd  lea     rax, [rbp+4Fh+var_50]
0x1800041c1  mov     [rsp+0D0h+attrs], rax; lpData
0x1800041c6  call    cs:__imp_RegQueryValueExW
0x1800041cc  test    eax, eax
0x1800041ce  jnz     short loc_1800041EA
0x1800041d0  cmp     [rbp+4Fh+Type], 3
0x1800041d4  jnz     short loc_1800041EA
0x1800041d6  mov     eax, [rsi+4]
0x1800041d9  cmp     dword ptr [rbp+4Fh+Data], eax
0x1800041dc  jnz     short loc_1800041EA
0x1800041de  mov     rax, [rsi+8]
0x1800041e2  cmp     qword ptr [rbp+4Fh+var_50], rax
0x1800041e6  cmovz   r13d, ebx
0x1800041ea  mov     rcx, r15; hMem
0x1800041ed  call    cs:__imp_LocalFree
0x1800041f3  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800041f7  mov     r15, [rsp+0A0h]
0x1800041ff  mov     r14, [rsp+0D0h+arg_10]
0x180004207  test    rcx, rcx
0x18000420a  jz      short loc_180004212
0x18000420c  call    cs:__imp_RegCloseKey
0x180004212  mov     rcx, [rbp+4Fh+phkResult]; hKey
0x180004216  test    rcx, rcx
0x180004219  jz      short loc_180004221
0x18000421b  call    cs:__imp_RegCloseKey
0x180004221  mov     rcx, [rbp+4Fh+var_70]; res
0x180004225  test    rcx, rcx
0x180004228  jz      short loc_18000423B
0x18000422a  call    cs:__imp_ldap_msgfree
0x180004230  jmp     short loc_18000423B
0x180004232  mov     rsi, [rbp+4Fh+arg_20]
0x180004236  test    rsi, rsi
0x180004239  jz      short loc_18000424B
0x18000423b  mov     eax, r13d
0x18000423e  test    r13d, r13d
0x180004241  jnz     short loc_18000424E
0x180004243  xorps   xmm0, xmm0
0x180004246  movups  xmmword ptr [rsi], xmm0
0x180004249  jmp     short loc_18000424E
0x18000424b  mov     eax, r13d
0x18000424e  add     rsp, 0A8h
0x180004255  pop     r13
0x180004257  pop     r12
0x180004259  pop     rdi
0x18000425a  pop     rsi
0x18000425b  pop     rbx
0x18000425c  pop     rbp
0x18000425d  retn
```
