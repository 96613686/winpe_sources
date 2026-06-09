# CSidResolver::_FillUserDetails(_LSA_TRANSLATED_NAME *,_LSA_REFERENCED_DOMAIN_LIST *,ushort const *,CUserObject *)

- ea: `0x18006f6a4`
- end: `0x18006faa3`
- name: `?_FillUserDetails@CSidResolver@@IEAAJPEAU_LSA_TRANSLATED_NAME@@PEAU_LSA_REFERENCED_DOMAIN_LIST@@PEBGPEAVCUserObject@@@Z`
- size: `1023`
- prototype: `int(CSidResolver *__hidden this, struct _LSA_TRANSLATED_NAME *, struct _LSA_REFERENCED_DOMAIN_LIST *, const unsigned __int16 *, struct CUserObject *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18006f368`
- `0x18006ff1c`

## callees

- `0x180009340`
- `0x180019454`
- `0x1800254e0`
- `0x18004eb64`
- `0x18006f4a4`
- `0x18006f608`
- `0x18006f6a4`
- `0x180078010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualPrefixSid` at `0x18006fa40`
- `api-ms-win-security-base-l1-1-0!EqualPrefixSid` at `0x18006fa40`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006f933`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006f933`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f9db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f9e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f9db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f9e6`
- `SHCORE!IsOS` at `0x18006f852`
- `SHCORE!IsOS` at `0x18006f852`
- `SHCORE!SHStrDupW` at `0x18006f827`
- `SHCORE!SHStrDupW` at `0x18006f827`
- `netutils!NetApiBufferFree` at `0x18006f834`
- `netutils!NetApiBufferFree` at `0x18006f83f`
- `netutils!NetApiBufferFree` at `0x18006f834`
- `netutils!NetApiBufferFree` at `0x18006f83f`
- `samcli!NetUserGetInfo` at `0x18006f79c`
- `samcli!NetUserGetInfo` at `0x18006f80b`
- `samcli!NetUserGetInfo` at `0x18006f79c`
- `samcli!NetUserGetInfo` at `0x18006f80b`
- `ACTIVEDS!__imp_ADsGetObject` at `0x18006f8c9`
- `ACTIVEDS!__imp_ADsGetObject` at `0x18006f8c9`
- `Secur32!TranslateNameW` at `0x18006f888`
- `Secur32!TranslateNameW` at `0x18006f888`

## pseudocode

```c
__int64 __fastcall CSidResolver::_FillUserDetails(
        CSidResolver *this,
        struct _LSA_TRANSLATED_NAME *a2,
        struct _LSA_REFERENCED_DOMAIN_LIST *a3,
        const unsigned __int16 *a4,
        struct CUserObject *a5)
{
  enum _SID_NAME_USE Use; // edi
  int String; // ebx
  bool v9; // zf
  CSidResolver *v10; // rcx
  const unsigned __int16 *v11; // r9
  LPBYTE v12; // rcx
  HRESULT v13; // eax
  CSidResolver *v14; // rcx
  CSidResolver *v15; // rcx
  PSID v16; // rdx
  CSidResolver *v17; // rcx
  LPBYTE nSize; // [rsp+40h] [rbp-C0h] BYREF
  void *ppObject; // [rsp+48h] [rbp-B8h] BYREF
  LPBYTE bufptr; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v25[136]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR username[264]; // [rsp+180h] [rbp+80h] BYREF
  WCHAR TranslatedName[264]; // [rsp+390h] [rbp+290h] BYREF
  WCHAR szPathName[272]; // [rsp+5A0h] [rbp+4A0h] BYREF
  WCHAR AccountName[520]; // [rsp+7C0h] [rbp+6C0h] BYREF

  Use = a2->Use;
  String = 0;
  if ( a2->Use != SidTypeInvalid && Use != SidTypeDomain )
  {
    v9 = a2->DomainIndex == -1;
    v25[0] = 0;
    if ( !v9 )
      StringCchCopyNW(
        v25,
        0x81u,
        a3->Domains[a2->DomainIndex].Name.Buffer,
        (unsigned __int64)a3->Domains[a2->DomainIndex].Name.Length >> 1);
    StringCchCopyNW(username, 0x104u, a2->Name.Buffer, (unsigned __int64)a2->Name.Length >> 1);
    StringCchPrintfW(AccountName, 0x208u, L"%s\\%s", v25, username);
    if ( Use != SidTypeUser )
    {
      if ( Use == SidTypeAlias )
      {
        Use = EqualPrefixSid(*(PSID *)a5, qword_180082A50) ? SidTypeAlias : SidTypeGroup;
      }
      else if ( Use != SidTypeGroup && Use != SidTypeWellKnownGroup )
      {
        return (unsigned int)String;
      }
      return (unsigned int)CSidResolver::_FillObjectDetails(v10, a5, username, username, v25, 0, Use, 1);
    }
    bufptr = 0;
    String = -2147467259;
    if ( NetUserGetInfo(a4, username, 2u, &bufptr) )
      goto LABEL_39;
    v11 = (const unsigned __int16 *)*((_QWORD *)bufptr + 8);
    if ( !*v11 )
      v11 = *(const unsigned __int16 **)bufptr;
    String = CSidResolver::_FillObjectDetails(
               (CSidResolver *)bufptr,
               a5,
               *(const unsigned __int16 **)bufptr,
               v11,
               v25,
               0,
               SidTypeUser,
               ((*((_DWORD *)bufptr + 10) >> 1) & 1) == 0);
    if ( String >= 0 )
    {
      nSize = 0;
      if ( !NetUserGetInfo(0, username, 0x18u, &nSize) )
      {
        v12 = nSize;
        if ( *(_DWORD *)nSize == 1 )
        {
          v13 = SHStrDupW(*((LPCWSTR *)nSize + 2), (LPWSTR *)a5 + 3);
          v12 = nSize;
          String = v13;
        }
        NetApiBufferFree(v12);
      }
    }
    NetApiBufferFree(bufptr);
    if ( String < 0 )
    {
LABEL_39:
      if ( !IsOS(0x1Cu) )
        goto LABEL_40;
      LODWORD(nSize) = 260;
      if ( TranslateNameW(AccountName, NameSamCompatible, NameFullyQualifiedDN, TranslatedName, (PULONG)&nSize) )
      {
        StringCchPrintfW(szPathName, 0x10Eu, L"LDAP://%s", TranslatedName);
        ppObject = 0;
        if ( !ADsGetObject(szPathName, &GUID_3e37e320_17e2_11cf_abc4_02608c9e7553, &ppObject) )
        {
          String = CSidResolver::_FillObjectDetails(v14, a5, (struct IADsUser *)ppObject, username, v25, SidTypeUser);
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
        }
      }
      if ( String < 0 )
      {
LABEL_40:
        ppv = 0;
        if ( CoCreateInstance(&CLSID_OnlineIdFilter, 0, 1u, &GUID_e6496873_6ddc_4709_8785_1a5b3267843b, &ppv) < 0 )
          return (unsigned int)CSidResolver::_FillObjectDetails(v15, a5, username, AccountName, v25, 0, SidTypeUser, 1);
        v16 = *(PSID *)a5;
        nSize = 0;
        String = (*(__int64 (__fastcall **)(LPVOID, PSID, LPBYTE *))(*(_QWORD *)ppv + 40LL))(ppv, v16, &nSize);
        if ( String >= 0 )
        {
          pv = 0;
          String = IPropertyStore_GetString(nSize, &PKEY_Identity_DisplayName, &pv);
          if ( String >= 0 )
          {
            ppObject = 0;
            String = IPropertyStore_GetString(nSize, &PKEY_Identity_UserName, &ppObject);
            if ( String >= 0 )
            {
              String = CSidResolver::_FillObjectDetails(
                         v17,
                         a5,
                         (const unsigned __int16 *)pv,
                         (const unsigned __int16 *)pv,
                         0,
                         (const unsigned __int16 *)ppObject,
                         SidTypeUser,
                         1);
              CoTaskMemFree(ppObject);
            }
            CoTaskMemFree(pv);
          }
          (*(void (__fastcall **)(LPBYTE))(*(_QWORD *)nSize + 16LL))(nSize);
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        if ( String < 0 )
          return (unsigned int)CSidResolver::_FillObjectDetails(v15, a5, username, AccountName, v25, 0, SidTypeUser, 1);
      }
    }
  }
  return (unsigned int)String;
}

```

## disassembly

```asm
0x18006f6a4  push    rbp
0x18006f6a6  push    rbx
0x18006f6a7  push    rsi
0x18006f6a8  push    rdi
0x18006f6a9  push    r12
0x18006f6ab  push    r14
0x18006f6ad  push    r15
0x18006f6af  lea     rbp, [rsp-0AE0h]
0x18006f6b7  sub     rsp, 0BE0h
0x18006f6be  mov     rax, cs:__security_cookie
0x18006f6c5  xor     rax, rsp
0x18006f6c8  mov     [rbp+0B10h+var_40], rax
0x18006f6cf  mov     edi, [rdx]
0x18006f6d1  xor     r12d, r12d
0x18006f6d4  mov     rsi, [rbp+0B10h+arg_20]
0x18006f6db  mov     r15, r9
0x18006f6de  mov     r14, rdx
0x18006f6e1  mov     ebx, r12d
0x18006f6e4  cmp     edi, 7
0x18006f6e7  jz      loc_18006FA80
0x18006f6ed  cmp     edi, 3
0x18006f6f0  jz      loc_18006FA80
0x18006f6f6  cmp     dword ptr [rdx+18h], 0FFFFFFFFh
0x18006f6fa  mov     [rsp+0C10h+var_BA0], r12w
0x18006f700  jz      short loc_18006F72A
0x18006f702  movsxd  rax, dword ptr [rdx+18h]
0x18006f706  mov     edx, 81h; unsigned __int64
0x18006f70b  mov     r8, [r8+8]
0x18006f70f  lea     rcx, [rax+rax*2]
0x18006f713  movzx   r9d, word ptr [r8+rcx*8]
0x18006f718  mov     r8, [r8+rcx*8+8]; unsigned __int16 *
0x18006f71d  lea     rcx, [rsp+0C10h+var_BA0]; unsigned __int16 *
0x18006f722  shr     r9, 1; unsigned __int64
0x18006f725  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18006f72a  movzx   r9d, word ptr [r14+8]
0x18006f72f  lea     rcx, [rbp+0B10h+username]; unsigned __int16 *
0x18006f736  mov     r8, [r14+10h]; unsigned __int16 *
0x18006f73a  mov     edx, 104h; unsigned __int64
0x18006f73f  shr     r9, 1; unsigned __int64
0x18006f742  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18006f747  lea     rax, [rbp+0B10h+username]
0x18006f74e  mov     edx, 208h; unsigned __int64
0x18006f753  lea     r9, [rsp+0C10h+var_BA0]
0x18006f758  mov     [rsp+0C10h+nSize], rax
0x18006f75d  lea     r8, aSS; "%s\\%s"
0x18006f764  lea     rcx, [rbp+0B10h+AccountName]; unsigned __int16 *
0x18006f76b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006f770  mov     r14d, 1
0x18006f776  cmp     edi, r14d
0x18006f779  jnz     loc_18006FA25
0x18006f77f  lea     r9, [rsp+0C10h+bufptr]; bufptr
0x18006f784  mov     [rsp+0C10h+bufptr], r12
0x18006f789  lea     r8d, [r14+1]; level
0x18006f78d  mov     rcx, r15; servername
0x18006f790  lea     rdx, [rbp+0B10h+username]; username
0x18006f797  mov     ebx, 80004005h
0x18006f79c  call    cs:__imp_NetUserGetInfo
0x18006f7a2  test    eax, eax
0x18006f7a4  jnz     loc_18006F84D
0x18006f7aa  mov     rcx, [rsp+0C10h+bufptr]; this
0x18006f7af  mov     rax, [rcx+40h]
0x18006f7b3  mov     r9, rax
0x18006f7b6  cmp     [rax], r12w
0x18006f7ba  jnz     short loc_18006F7BF
0x18006f7bc  mov     r9, [rcx]; unsigned __int16 *
0x18006f7bf  mov     eax, [rcx+28h]
0x18006f7c2  mov     rdx, rsi; struct CUserObject *
0x18006f7c5  mov     r8, [rcx]; unsigned __int16 *
0x18006f7c8  shr     eax, 1
0x18006f7ca  not     eax
0x18006f7cc  and     eax, r14d
0x18006f7cf  mov     [rsp+0C10h+var_BD8], eax; int
0x18006f7d3  lea     rax, [rsp+0C10h+var_BA0]
0x18006f7d8  mov     [rsp+0C10h+var_BE0], r14d; enum _SID_NAME_USE
0x18006f7dd  mov     qword ptr [rsp+0C10h+var_BE8], r12; unsigned __int16 *
0x18006f7e2  mov     [rsp+0C10h+nSize], rax; unsigned __int16 *
0x18006f7e7  call    ?_FillObjectDetails@CSidResolver@@IEAAJPEAVCUserObject@@PEBG111W4_SID_NAME_USE@@H@Z; CSidResolver::_FillObjectDetails(CUserObject *,ushort const *,ushort const *,ushort const *,ushort const *,_SID_NAME_USE,int)
0x18006f7ec  mov     ebx, eax
0x18006f7ee  test    eax, eax
0x18006f7f0  js      short loc_18006F83A
0x18006f7f2  lea     r9, [rsp+0C10h+var_BD0]; bufptr
0x18006f7f7  mov     [rsp+0C10h+var_BD0], r12
0x18006f7fc  mov     r8d, 18h; level
0x18006f802  lea     rdx, [rbp+0B10h+username]; username
0x18006f809  xor     ecx, ecx; servername
0x18006f80b  call    cs:__imp_NetUserGetInfo
0x18006f811  test    eax, eax
0x18006f813  jnz     short loc_18006F83A
0x18006f815  mov     rcx, [rsp+0C10h+var_BD0]
0x18006f81a  cmp     [rcx], r14d
0x18006f81d  jnz     short loc_18006F834
0x18006f81f  mov     rcx, [rcx+10h]; psz
0x18006f823  lea     rdx, [rsi+18h]; ppwsz
0x18006f827  call    cs:__imp_SHStrDupW
0x18006f82d  mov     rcx, [rsp+0C10h+var_BD0]; Buffer
0x18006f832  mov     ebx, eax
0x18006f834  call    cs:__imp_NetApiBufferFree
0x18006f83a  mov     rcx, [rsp+0C10h+bufptr]; Buffer
0x18006f83f  call    cs:__imp_NetApiBufferFree
0x18006f845  test    ebx, ebx
0x18006f847  jns     loc_18006FA80
0x18006f84d  mov     ecx, 1Ch; dwOS
0x18006f852  call    cs:__imp_IsOS
0x18006f858  test    eax, eax
0x18006f85a  jz      loc_18006F911
0x18006f860  lea     rax, [rsp+0C10h+var_BD0]
0x18006f865  mov     dword ptr [rsp+0C10h+var_BD0], 104h
0x18006f86d  lea     r9, [rbp+0B10h+TranslatedName]; lpTranslatedName
0x18006f874  mov     [rsp+0C10h+nSize], rax; nSize
0x18006f879  mov     r8d, r14d; DesiredNameFormat
0x18006f87c  lea     rcx, [rbp+0B10h+AccountName]; lpAccountName
0x18006f883  mov     edx, 2; AccountNameFormat
0x18006f888  call    cs:__imp_TranslateNameW
0x18006f88e  test    al, al
0x18006f890  jz      short loc_18006F909
0x18006f892  lea     r9, [rbp+0B10h+TranslatedName]
0x18006f899  mov     edx, 10Eh; unsigned __int64
0x18006f89e  lea     r8, aLdapS; "LDAP://%s"
0x18006f8a5  lea     rcx, [rbp+0B10h+szPathName]; unsigned __int16 *
0x18006f8ac  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006f8b1  lea     r8, [rsp+0C10h+ppObject]; ppObject
0x18006f8b6  mov     [rsp+0C10h+ppObject], r12
0x18006f8bb  lea     rdx, _GUID_3e37e320_17e2_11cf_abc4_02608c9e7553; riid
0x18006f8c2  lea     rcx, [rbp+0B10h+szPathName]; lpszPathName
0x18006f8c9  call    cs:__imp_ADsGetObject
0x18006f8cf  test    eax, eax
0x18006f8d1  jnz     short loc_18006F909
0x18006f8d3  mov     r8, [rsp+0C10h+ppObject]; struct IADsUser *
0x18006f8d8  lea     rax, [rsp+0C10h+var_BA0]
0x18006f8dd  mov     [rsp+0C10h+var_BE8], r14d; enum _SID_NAME_USE
0x18006f8e2  lea     r9, [rbp+0B10h+username]; unsigned __int16 *
0x18006f8e9  mov     rdx, rsi; struct CUserObject *
0x18006f8ec  mov     [rsp+0C10h+nSize], rax; unsigned __int16 *
0x18006f8f1  call    ?_FillObjectDetails@CSidResolver@@IEAAJPEAVCUserObject@@PEAUIADsUser@@PEBG2W4_SID_NAME_USE@@@Z; CSidResolver::_FillObjectDetails(CUserObject *,IADsUser *,ushort const *,ushort const *,_SID_NAME_USE)
0x18006f8f6  mov     rcx, [rsp+0C10h+ppObject]
0x18006f8fb  mov     ebx, eax
0x18006f8fd  mov     rax, [rcx]
0x18006f900  mov     rax, [rax+10h]
0x18006f904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f909  test    ebx, ebx
0x18006f90b  jns     loc_18006FA80
0x18006f911  lea     rax, [rsp+0C10h+ppv]
0x18006f916  mov     [rsp+0C10h+ppv], r12
0x18006f91b  lea     r9, _GUID_e6496873_6ddc_4709_8785_1a5b3267843b; riid
0x18006f922  mov     [rsp+0C10h+nSize], rax; ppv
0x18006f927  mov     r8d, r14d; dwClsContext
0x18006f92a  lea     rcx, CLSID_OnlineIdFilter; rclsid
0x18006f931  xor     edx, edx; pUnkOuter
0x18006f933  call    cs:__imp_CoCreateInstance
0x18006f939  test    eax, eax
0x18006f93b  js      loc_18006FA12
0x18006f941  mov     rcx, [rsp+0C10h+ppv]
0x18006f946  lea     r8, [rsp+0C10h+var_BD0]
0x18006f94b  mov     rdx, [rsi]
0x18006f94e  mov     [rsp+0C10h+var_BD0], r12
0x18006f953  mov     rax, [rcx]
0x18006f956  mov     rax, [rax+28h]
0x18006f95a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f95f  mov     ebx, eax
0x18006f961  test    eax, eax
0x18006f963  js      loc_18006F9FD
0x18006f969  mov     rcx, [rsp+0C10h+var_BD0]
0x18006f96e  lea     r8, [rsp+0C10h+pv]
0x18006f973  lea     rdx, PKEY_Identity_DisplayName
0x18006f97a  mov     [rsp+0C10h+pv], r12
0x18006f97f  call    IPropertyStore_GetString
0x18006f984  mov     ebx, eax
0x18006f986  test    eax, eax
0x18006f988  js      short loc_18006F9EC
0x18006f98a  mov     rcx, [rsp+0C10h+var_BD0]
0x18006f98f  lea     r8, [rsp+0C10h+ppObject]
0x18006f994  lea     rdx, PKEY_Identity_UserName
0x18006f99b  mov     [rsp+0C10h+ppObject], r12
0x18006f9a0  call    IPropertyStore_GetString
0x18006f9a5  mov     ebx, eax
0x18006f9a7  test    eax, eax
0x18006f9a9  js      short loc_18006F9E1
0x18006f9ab  mov     rax, [rsp+0C10h+ppObject]
0x18006f9b0  mov     rdx, rsi; struct CUserObject *
0x18006f9b3  mov     r8, [rsp+0C10h+pv]; unsigned __int16 *
0x18006f9b8  mov     [rsp+0C10h+var_BD8], r14d; int
0x18006f9bd  mov     r9, r8; unsigned __int16 *
0x18006f9c0  mov     [rsp+0C10h+var_BE0], r14d; enum _SID_NAME_USE
0x18006f9c5  mov     qword ptr [rsp+0C10h+var_BE8], rax; unsigned __int16 *
0x18006f9ca  mov     [rsp+0C10h+nSize], r12; unsigned __int16 *
0x18006f9cf  call    ?_FillObjectDetails@CSidResolver@@IEAAJPEAVCUserObject@@PEBG111W4_SID_NAME_USE@@H@Z; CSidResolver::_FillObjectDetails(CUserObject *,ushort const *,ushort const *,ushort const *,ushort const *,_SID_NAME_USE,int)
0x18006f9d4  mov     rcx, [rsp+0C10h+ppObject]; pv
0x18006f9d9  mov     ebx, eax
0x18006f9db  call    cs:__imp_CoTaskMemFree
0x18006f9e1  mov     rcx, [rsp+0C10h+pv]; pv
0x18006f9e6  call    cs:__imp_CoTaskMemFree
0x18006f9ec  mov     rcx, [rsp+0C10h+var_BD0]
0x18006f9f1  mov     rax, [rcx]
0x18006f9f4  mov     rax, [rax+10h]
0x18006f9f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f9fd  mov     rcx, [rsp+0C10h+ppv]
0x18006fa02  mov     rax, [rcx]
0x18006fa05  mov     rax, [rax+10h]
0x18006fa09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fa0e  test    ebx, ebx
0x18006fa10  jns     short loc_18006FA80
0x18006fa12  mov     [rsp+0C10h+var_BD8], r14d
0x18006fa17  lea     r9, [rbp+0B10h+AccountName]
0x18006fa1e  mov     [rsp+0C10h+var_BE0], r14d
0x18006fa23  jmp     short loc_18006FA60
0x18006fa25  cmp     edi, 4
0x18006fa28  jz      short loc_18006FA36
0x18006fa2a  cmp     edi, 2
0x18006fa2d  jz      short loc_18006FA50
0x18006fa2f  cmp     edi, 5
0x18006fa32  jnz     short loc_18006FA80
0x18006fa34  jmp     short loc_18006FA50
0x18006fa36  mov     rcx, [rsi]; pSid1
0x18006fa39  lea     rdx, qword_180082A50; pSid2
0x18006fa40  call    cs:__imp_EqualPrefixSid
0x18006fa46  neg     eax
0x18006fa48  sbb     edi, edi
0x18006fa4a  and     edi, 2
0x18006fa4d  add     edi, 2
0x18006fa50  mov     [rsp+0C10h+var_BD8], r14d; int
0x18006fa55  lea     r9, [rbp+0B10h+username]; unsigned __int16 *
0x18006fa5c  mov     [rsp+0C10h+var_BE0], edi; enum _SID_NAME_USE
0x18006fa60  lea     rax, [rsp+0C10h+var_BA0]
0x18006fa65  mov     qword ptr [rsp+0C10h+var_BE8], r12; unsigned __int16 *
0x18006fa6a  lea     r8, [rbp+0B10h+username]; unsigned __int16 *
0x18006fa71  mov     [rsp+0C10h+nSize], rax; unsigned __int16 *
0x18006fa76  mov     rdx, rsi; struct CUserObject *
0x18006fa79  call    ?_FillObjectDetails@CSidResolver@@IEAAJPEAVCUserObject@@PEBG111W4_SID_NAME_USE@@H@Z; CSidResolver::_FillObjectDetails(CUserObject *,ushort const *,ushort const *,ushort const *,ushort const *,_SID_NAME_USE,int)
0x18006fa7e  mov     ebx, eax
0x18006fa80  mov     eax, ebx
0x18006fa82  mov     rcx, [rbp+0B10h+var_40]
0x18006fa89  xor     rcx, rsp; StackCookie
0x18006fa8c  call    __security_check_cookie
0x18006fa91  add     rsp, 0BE0h
0x18006fa98  pop     r15
0x18006fa9a  pop     r14
0x18006fa9c  pop     r12
0x18006fa9e  pop     rdi
0x18006fa9f  pop     rsi
0x18006faa0  pop     rbx
0x18006faa1  pop     rbp
0x18006faa2  retn
```
