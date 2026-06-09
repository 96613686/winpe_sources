# AddAppContainerAccessWorker(ushort const *,ushort const *,_SE_OBJECT_TYPE,ulong)

- ea: `0x18001d970`
- end: `0x18001dbd9`
- name: `?AddAppContainerAccessWorker@@YAJPEBG0W4_SE_OBJECT_TYPE@@K@Z`
- size: `617`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, enum _SE_OBJECT_TYPE, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180004594`
- `0x18000c7d4`
- `0x18000f440`
- `0x18000f5b0`
- `0x18001d7ec`
- `0x18001d970`
- `0x180020558`

## import_xrefs

- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x18001dad6`
- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x18001dad6`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18001da5f`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18001da5f`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18001db66`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18001db66`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18001dafb`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18001dafb`

## string_xrefs

- `0x18001d9a4`: `onecore\ds\security\gina\profile\profext\lpacapi.cpp`
- `0x18001d9f2`: `onecore\ds\security\gina\profile\profext\lpacapi.cpp`
- `0x18001da8a`: `onecore\ds\security\gina\profile\profext\lpacapi.cpp`
- `0x18001db1b`: `onecore\ds\security\gina\profile\profext\lpacapi.cpp`
- `0x18001db86`: `onecore\ds\security\gina\profile\profext\lpacapi.cpp`
- `0x18001da7e`: `GetNamedSecurityInfo error for '%ls'`
- `0x18001db0f`: `SetEntriesInAcl Error`
- `0x18001db7a`: `SetNamedSecurityInfo error for '%ls'`

## pseudocode

```c
__int64 __fastcall AddAppContainerAccessWorker(const unsigned __int16 *a1, WCHAR *a2, SE_OBJECT_TYPE a3, DWORD a4)
{
  __int64 v8; // rdx
  unsigned int v9; // ebx
  int LpacSid; // eax
  DWORD NamedSecurityInfoW; // ebx
  DWORD v12; // eax
  unsigned int v13; // eax
  DWORD v14; // eax
  int ppsidGroup; // [rsp+20h] [rbp-39h]
  PACL *ppDacl; // [rsp+28h] [rbp-31h]
  __int64 v18; // [rsp+40h] [rbp-19h] BYREF
  PSID pSid; // [rsp+48h] [rbp-11h] BYREF
  PACL OldAcl; // [rsp+50h] [rbp-9h] BYREF
  __int64 *v21; // [rsp+58h] [rbp-1h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+60h] [rbp+7h] BYREF
  char v23; // [rsp+68h] [rbp+Fh]
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+70h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  PACL NewAcl; // [rsp+C0h] [rbp+67h] BYREF

  if ( a1 )
  {
    if ( !a2 )
    {
      v8 = 227;
      goto LABEL_3;
    }
    pSid = 0;
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &pSid,
      0);
    LpacSid = LpacRegHelper::FetchLpacSid(a1, &pSid);
    v9 = LpacSid;
    if ( LpacSid >= 0 )
    {
      v18 = 0;
      v21 = &v18;
      OldAcl = 0;
      ppSecurityDescriptor = 0;
      v23 = 1;
      NamedSecurityInfoW = GetNamedSecurityInfoW(a2, a3, 4u, 0, 0, &OldAcl, 0, &ppSecurityDescriptor);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v21);
      if ( NamedSecurityInfoW )
      {
        v9 = wil::details::in1diag3::Return_Win32Msg(
               retaddr,
               (void *)0xF9,
               (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacapi.cpp",
               (const char *)NamedSecurityInfoW,
               (unsigned int)"GetNamedSecurityInfo error for '%ls'",
               (const char *)a2);
      }
      else
      {
        memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 36);
        pListOfExplicitEntries.grfAccessPermissions = a4;
        *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 1;
        BuildTrusteeWithSidW(&pListOfExplicitEntries.Trustee, pSid);
        NewAcl = 0;
        v12 = SetEntriesInAclW(1u, &pListOfExplicitEntries, OldAcl, &NewAcl);
        if ( v12 )
        {
          v13 = wil::details::in1diag3::Return_Win32Msg(
                  retaddr,
                  (void *)0x10D,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacapi.cpp",
                  (const char *)v12,
                  (unsigned int)"SetEntriesInAcl Error",
                  (const char *)ppDacl);
        }
        else
        {
          v14 = SetNamedSecurityInfoW(a2, a3, 4u, 0, 0, NewAcl, 0);
          if ( !v14 )
          {
            wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&NewAcl);
            wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&v18);
            v9 = 0;
            goto LABEL_17;
          }
          v13 = wil::details::in1diag3::Return_Win32Msg(
                  retaddr,
                  (void *)0x118,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacapi.cpp",
                  (const char *)v14,
                  (unsigned int)"SetNamedSecurityInfo error for '%ls'",
                  (const char *)a2);
        }
        v9 = v13;
        wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&NewAcl);
      }
      wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&v18);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEA,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacapi.cpp",
        (const char *)(unsigned int)LpacSid,
        ppsidGroup);
    }
LABEL_17:
    wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&pSid);
    return v9;
  }
  v8 = 226;
LABEL_3:
  v9 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacapi.cpp",
    (const char *)0x80070057LL,
    ppsidGroup);
  return v9;
}

```

## disassembly

```asm
0x18001d970  mov     [rsp-8+arg_8], rbx
0x18001d975  mov     [rsp-8+arg_10], rsi
0x18001d97a  push    rbp
0x18001d97b  push    rdi
0x18001d97c  push    r14
0x18001d97e  lea     rbp, [rsp-47h]
0x18001d983  sub     rsp, 0A0h
0x18001d98a  mov     r14d, r9d
0x18001d98d  mov     esi, r8d
0x18001d990  mov     rdi, rdx
0x18001d993  mov     rbx, rcx
0x18001d996  test    rcx, rcx
0x18001d999  jnz     short loc_18001D9BD
0x18001d99b  mov     edx, 0E2h; void *
0x18001d9a0  mov     rcx, [rbp+5Fh]; this
0x18001d9a4  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001d9ab  mov     ebx, 80070057h
0x18001d9b0  mov     r9d, ebx; char *
0x18001d9b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d9b8  jmp     loc_18001DBBE
0x18001d9bd  test    rdi, rdi
0x18001d9c0  jnz     short loc_18001D9C9
0x18001d9c2  mov     edx, 0E3h
0x18001d9c7  jmp     short loc_18001D9A0
0x18001d9c9  xor     edx, edx
0x18001d9cb  mov     [rbp+57h+pSid], 0
0x18001d9d3  lea     rcx, [rbp+57h+pSid]
0x18001d9d7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18001d9dc  lea     rdx, [rbp+57h+pSid]; void **
0x18001d9e0  mov     rcx, rbx; unsigned __int16 *
0x18001d9e3  call    ?FetchLpacSid@LpacRegHelper@@SAJPEBGPEAPEAX@Z; LpacRegHelper::FetchLpacSid(ushort const *,void * *)
0x18001d9e8  mov     ebx, eax
0x18001d9ea  test    eax, eax
0x18001d9ec  jns     short loc_18001DA0B
0x18001d9ee  mov     rcx, [rbp+5Fh]; this
0x18001d9f2  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001d9f9  mov     r9d, eax; char *
0x18001d9fc  mov     edx, 0EAh; void *
0x18001da01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001da06  jmp     loc_18001DBB5
0x18001da0b  lea     rax, [rbp+57h+var_70]
0x18001da0f  mov     [rbp+57h+var_70], 0
0x18001da17  mov     [rbp+57h+var_58], rax
0x18001da1b  xor     r9d, r9d; ppsidOwner
0x18001da1e  lea     rax, [rbp+57h+var_50]
0x18001da22  mov     [rbp+57h+OldAcl], 0
0x18001da2a  mov     [rsp+0B0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18001da2f  mov     edx, esi; ObjectType
0x18001da31  lea     rax, [rbp+57h+OldAcl]
0x18001da35  mov     [rsp+0B0h+ppSacl], 0; ppSacl
0x18001da3e  mov     [rsp+0B0h+ppDacl], rax; char *
0x18001da43  lea     r8d, [r9+4]; SecurityInfo
0x18001da47  mov     rcx, rdi; pObjectName
0x18001da4a  mov     [rsp+0B0h+ppsidGroup], 0; ppsidGroup
0x18001da53  mov     [rbp+57h+var_50], 0
0x18001da5b  mov     [rbp+57h+var_48], 1
0x18001da5f  call    cs:__imp_GetNamedSecurityInfoW
0x18001da66  nop     dword ptr [rax+rax+00h]
0x18001da6b  lea     rcx, [rbp+57h+var_58]
0x18001da6f  mov     ebx, eax
0x18001da71  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18001da76  test    ebx, ebx
0x18001da78  jz      short loc_18001DAB3
0x18001da7a  mov     rcx, [rbp+5Fh]; this
0x18001da7e  lea     rax, aGetnamedsecuri_0; "GetNamedSecurityInfo error for '%ls'"
0x18001da85  mov     [rsp+0B0h+ppDacl], rdi; char *
0x18001da8a  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001da91  mov     r9d, ebx; char *
0x18001da94  mov     [rsp+0B0h+ppsidGroup], rax; unsigned int
0x18001da99  mov     edx, 0F9h; void *
0x18001da9e  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18001daa3  mov     ebx, eax
0x18001daa5  lea     rcx, [rbp+57h+var_70]
0x18001daa9  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001daae  jmp     loc_18001DBB5
0x18001dab3  mov     rdx, [rbp+57h+pSid]; pSid
0x18001dab7  lea     rcx, [rbp+57h+pListOfExplicitEntries.Trustee]; pTrustee
0x18001dabb  xorps   xmm0, xmm0
0x18001dabe  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18001dac2  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], r14d
0x18001dac6  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], 1
0x18001dace  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x18001dad2  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x18001dad6  call    cs:__imp_BuildTrusteeWithSidW
0x18001dadd  nop     dword ptr [rax+rax+00h]
0x18001dae2  mov     r8, [rbp+57h+OldAcl]; OldAcl
0x18001dae6  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x18001daea  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18001daee  mov     [rbp+57h+NewAcl], 0
0x18001daf6  mov     ecx, 1; cCountOfExplicitEntries
0x18001dafb  call    cs:__imp_SetEntriesInAclW
0x18001db02  nop     dword ptr [rax+rax+00h]
0x18001db07  test    eax, eax
0x18001db09  jz      short loc_18001DB3F
0x18001db0b  mov     rcx, [rbp+5Fh]; this
0x18001db0f  lea     rdx, aSetentriesinac_0; "SetEntriesInAcl Error"
0x18001db16  mov     [rsp+0B0h+ppsidGroup], rdx; unsigned int
0x18001db1b  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001db22  mov     edx, 10Dh; void *
0x18001db27  mov     r9d, eax; char *
0x18001db2a  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18001db2f  lea     rcx, [rbp+57h+NewAcl]
0x18001db33  mov     ebx, eax
0x18001db35  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001db3a  jmp     loc_18001DAA5
0x18001db3f  mov     rax, [rbp+57h+NewAcl]
0x18001db43  xor     r9d, r9d; psidOwner
0x18001db46  mov     [rsp+0B0h+ppSacl], 0; pSacl
0x18001db4f  mov     edx, esi; ObjectType
0x18001db51  mov     [rsp+0B0h+ppDacl], rax; pDacl
0x18001db56  mov     rcx, rdi; pObjectName
0x18001db59  mov     [rsp+0B0h+ppsidGroup], 0; psidGroup
0x18001db62  lea     r8d, [r9+4]; SecurityInfo
0x18001db66  call    cs:__imp_SetNamedSecurityInfoW
0x18001db6d  nop     dword ptr [rax+rax+00h]
0x18001db72  test    eax, eax
0x18001db74  jz      short loc_18001DBA1
0x18001db76  mov     rcx, [rbp+5Fh]; this
0x18001db7a  lea     rdx, aSetnamedsecuri_0; "SetNamedSecurityInfo error for '%ls'"
0x18001db81  mov     [rsp+0B0h+ppDacl], rdi; char *
0x18001db86  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001db8d  mov     [rsp+0B0h+ppsidGroup], rdx; unsigned int
0x18001db92  mov     r9d, eax; char *
0x18001db95  mov     edx, 118h; void *
0x18001db9a  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18001db9f  jmp     short loc_18001DB2F
0x18001dba1  lea     rcx, [rbp+57h+NewAcl]
0x18001dba5  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001dbaa  lea     rcx, [rbp+57h+var_70]
0x18001dbae  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001dbb3  xor     ebx, ebx
0x18001dbb5  lea     rcx, [rbp+57h+pSid]
0x18001dbb9  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001dbbe  lea     r11, [rsp+0B0h+var_10]
0x18001dbc6  mov     eax, ebx
0x18001dbc8  mov     rbx, [r11+28h]
0x18001dbcc  mov     rsi, [r11+30h]
0x18001dbd0  mov     rsp, r11
0x18001dbd3  pop     r14
0x18001dbd5  pop     rdi
0x18001dbd6  pop     rbp
0x18001dbd7  retn
```
