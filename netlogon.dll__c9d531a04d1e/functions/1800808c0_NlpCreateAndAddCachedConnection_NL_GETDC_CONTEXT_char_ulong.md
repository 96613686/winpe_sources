# NlpCreateAndAddCachedConnection(_NL_GETDC_CONTEXT *,char *,ulong)

- ea: `0x1800808c0`
- end: `0x180080b63`
- name: `?NlpCreateAndAddCachedConnection@@YAPEAU_CACHED_CONNECTION@@PEAU_NL_GETDC_CONTEXT@@PEADK@Z`
- size: `675`
- prototype: `struct _CACHED_CONNECTION *(struct _NL_GETDC_CONTEXT *, char *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180080424`

## callees

- `0x18000d710`
- `0x18000e270`
- `0x18000ed34`
- `0x18001847c`
- `0x1800808c0`
- `0x180080f8c`
- `0x180081044`
- `0x18008107c`
- `0x1800810e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180080b22`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180080b22`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180080a16`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180080a16`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180080b37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180080b37`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180080a02`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180080a02`
- `RPCRT4!UuidCreate` at `0x1800809d4`
- `RPCRT4!UuidCreate` at `0x1800809d4`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180080adc`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180080adc`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180080a2f`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180080a2f`
- `WLDAP32!__imp_LdapGetLastError` at `0x180080917`
- `WLDAP32!__imp_LdapGetLastError` at `0x180080917`
- `WLDAP32!__imp_cldap_openA` at `0x180080909`
- `WLDAP32!__imp_cldap_openA` at `0x180080909`

## string_xrefs

- `0x1800809af`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\ldapcache.cxx`
- `0x1800809e6`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\ldapcache.cxx`
- `0x180080a56`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\ldapcache.cxx`
- `0x180080a75`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\ldapcache.cxx`
- `0x180080af0`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\ldapcache.cxx`
- `0x180080a5d`: `pCacheEntry->ldapConnection.pldap == pldap`
- `0x180080a7c`: `pCacheEntry->refCount == 1`
- `0x180080af7`: `RtlNumberGenericTableElementsAvl(&_connectionCache) == _connectionCacheCount`

## pseudocode

```c
struct _CACHED_CONNECTION *__fastcall NlpCreateAndAddCachedConnection(struct _NL_GETDC_CONTEXT *a1, char *a2)
{
  volatile signed __int32 *v4; // r14
  LDAP *v5; // rax
  struct ldap *v6; // rdi
  DWORD LastError; // ebx
  unsigned int v8; // eax
  unsigned __int64 v9; // rdx
  char *v10; // r9
  char *v11; // r9
  volatile signed __int32 *inserted; // rax
  char *v13; // r9
  volatile signed __int32 *v14; // rsi
  char *v15; // r9
  unsigned __int8 NewElement[16]; // [rsp+30h] [rbp-79h] BYREF
  struct ldap *Buffer; // [rsp+40h] [rbp-69h] BYREF
  int v19; // [rsp+48h] [rbp-61h]
  int v20; // [rsp+50h] [rbp-59h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+54h] [rbp-55h] BYREF
  UUID Uuid; // [rsp+5Ch] [rbp-4Dh] BYREF
  CLONG BufferSize; // [rsp+6Ch] [rbp-3Dh]
  char v24[72]; // [rsp+70h] [rbp-39h] BYREF
  int v25; // [rsp+B8h] [rbp+Fh]
  __int64 v26; // [rsp+C0h] [rbp+17h]

  NewElement[0] = 0;
  memset_0(&Buffer, 0, 0x88u);
  v4 = 0;
  v5 = cldap_openA(a2, 0);
  v6 = v5;
  if ( !v5 )
  {
    LastError = LdapGetLastError();
    goto LABEL_26;
  }
  v8 = NlpSetLocatorCLDAPConnectionConfig(v5);
  LastError = v8;
  if ( v8 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_6329ba22ebb9302edb0b3a45469c8c48_Traceguids, v8, v8);
    goto LABEL_25;
  }
  memset_0(&Buffer, 0, 0x88u);
  v26 = *((_QWORD *)a1 + 14);
  v20 = 1;
  BufferSize = 136;
  Buffer = v6;
  if ( (int)RtlStringCbCopyA(v24, v9, a2) < 0 )
  {
    NlAssertFailed("FALSE", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\coreloc\\ldapcache.cxx", 706, v10);
    LastError = 87;
LABEL_25:
    NlpUnbindLdapConnection(v6);
    goto LABEL_26;
  }
  v25 = 0;
  LastError = UuidCreate(&Uuid);
  if ( LastError )
  {
    NlAssertFailed("FALSE", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\coreloc\\ldapcache.cxx", 715, v11);
    goto LABEL_25;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v19 = 1;
  AcquireSRWLockExclusive(&_rwCacheLock);
  inserted = (volatile signed __int32 *)RtlInsertElementGenericTableAvl(
                                          &_connectionCache,
                                          &Buffer,
                                          BufferSize,
                                          NewElement);
  v14 = inserted;
  if ( inserted )
  {
    if ( NewElement[0] )
    {
      if ( *(struct ldap **)inserted != v6 )
        NlAssertFailed(
          "pCacheEntry->ldapConnection.pldap == pldap",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\coreloc\\ldapcache.cxx",
          746,
          v13);
      if ( *((_DWORD *)v14 + 4) != 1 )
        NlAssertFailed(
          "pCacheEntry->refCount == 1",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\coreloc\\ldapcache.cxx",
          747,
          v13);
      v6 = 0;
      _InterlockedIncrement64(&qword_1800F1E48);
      _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(*((_QWORD *)a1 + 14) + 360LL) + 200LL));
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)a1 + 14) + 16LL));
      if ( ++_connectionCacheCount > _connectionCacheHighwaterMark )
        _connectionCacheHighwaterMark = _connectionCacheCount;
    }
    else
    {
      _InterlockedIncrement(inserted + 4);
      ++_connectionAddRaces;
    }
    if ( RtlNumberGenericTableElementsAvl(&_connectionCache) != _connectionCacheCount )
      NlAssertFailed(
        "RtlNumberGenericTableElementsAvl(&_connectionCache) == _connectionCacheCount",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\coreloc\\ldapcache.cxx",
        782,
        v15);
    NlpWarnIfCachedHostUsedForMultipleDomains(
      (struct _LDAP_CACHE_ENTRY *)v14,
      *((struct _NL_DC_DOMAIN_ENTRY **)a1 + 14));
    LastError = 0;
    v4 = v14;
  }
  else
  {
    LastError = 14;
  }
  ReleaseSRWLockExclusive(&_rwCacheLock);
  if ( v6 )
    goto LABEL_25;
LABEL_26:
  SetLastError(LastError);
  return (struct _CACHED_CONNECTION *)v4;
}

```

## disassembly

```asm
0x1800808c0  mov     [rsp-8+arg_10], rbx
0x1800808c5  push    rbp
0x1800808c6  push    rsi
0x1800808c7  push    rdi
0x1800808c8  push    r14
0x1800808ca  push    r15
0x1800808cc  lea     rbp, [rsp-37h]
0x1800808d1  sub     rsp, 0E0h
0x1800808d8  mov     rax, cs:__security_cookie
0x1800808df  xor     rax, rsp
0x1800808e2  mov     [rbp+57h+var_30], rax
0x1800808e6  mov     rsi, rdx
0x1800808e9  mov     [rbp+57h+NewElement], 0
0x1800808ed  mov     r15, rcx
0x1800808f0  xor     edx, edx; Val
0x1800808f2  lea     rcx, [rbp+57h+Buffer]; void *
0x1800808f6  mov     r8d, 88h; Size
0x1800808fc  call    memset_0
0x180080901  xor     edx, edx; PortNumber
0x180080903  mov     rcx, rsi; HostName
0x180080906  xor     r14d, r14d
0x180080909  call    cs:__imp_cldap_openA
0x18008090f  mov     rdi, rax
0x180080912  test    rax, rax
0x180080915  jnz     short loc_180080924
0x180080917  call    cs:__imp_LdapGetLastError
0x18008091d  mov     ebx, eax
0x18008091f  jmp     loc_180080B35
0x180080924  mov     rcx, rdi; ld
0x180080927  call    ?NlpSetLocatorCLDAPConnectionConfig@@YAKPEAUldap@@@Z; NlpSetLocatorCLDAPConnectionConfig(ldap *)
0x18008092c  mov     ebx, eax
0x18008092e  test    eax, eax
0x180080930  jz      short loc_18008096E
0x180080932  mov     rcx, cs:WPP_GLOBAL_Control
0x180080939  test    byte ptr [rcx+1Ch], 4
0x18008093d  jz      loc_180080B2D
0x180080943  cmp     byte ptr [rcx+19h], 4
0x180080947  jb      loc_180080B2D
0x18008094d  mov     rcx, [rcx+10h]
0x180080951  lea     r8, WPP_6329ba22ebb9302edb0b3a45469c8c48_Traceguids
0x180080958  mov     edx, 0Bh
0x18008095d  mov     [rsp+100h+var_E0], eax
0x180080961  mov     r9d, eax
0x180080964  call    WPP_SF_Dd
0x180080969  jmp     loc_180080B2D
0x18008096e  xor     edx, edx; Val
0x180080970  lea     rcx, [rbp+57h+Buffer]; void *
0x180080974  mov     r8d, 88h; Size
0x18008097a  call    memset_0
0x18008097f  mov     rax, [r15+70h]
0x180080983  lea     rcx, [rbp+57h+var_90]; char *
0x180080987  mov     r8, rsi; char *
0x18008098a  mov     [rbp+57h+var_40], rax
0x18008098e  mov     [rbp+57h+var_B0], 1
0x180080995  mov     [rbp+57h+BufferSize], 88h
0x18008099c  mov     [rbp+57h+Buffer], rdi
0x1800809a0  call    ?RtlStringCbCopyA@@YAJPEAD_KPEBD@Z; RtlStringCbCopyA(char *,unsigned __int64,char const *)
0x1800809a5  test    eax, eax
0x1800809a7  jns     short loc_1800809CC
0x1800809a9  mov     r8d, 2C2h; unsigned int
0x1800809af  lea     rdx, aOnecoreDsNetap_14; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800809b6  lea     rcx, aFalse; "FALSE"
0x1800809bd  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800809c2  mov     ebx, 57h ; 'W'
0x1800809c7  jmp     loc_180080B2D
0x1800809cc  lea     rcx, [rbp+57h+Uuid]; Uuid
0x1800809d0  mov     [rbp+57h+var_48], r14d
0x1800809d4  call    cs:__imp_UuidCreate
0x1800809da  mov     ebx, eax
0x1800809dc  test    eax, eax
0x1800809de  jz      short loc_1800809FE
0x1800809e0  mov     r8d, 2CBh; unsigned int
0x1800809e6  lea     rdx, aOnecoreDsNetap_14; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800809ed  lea     rcx, aFalse; "FALSE"
0x1800809f4  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800809f9  jmp     loc_180080B2D
0x1800809fe  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180080a02  call    cs:__imp_GetSystemTimeAsFileTime
0x180080a08  lea     rcx, ?_rwCacheLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180080a0f  mov     [rbp+57h+var_B8], 1
0x180080a16  call    cs:__imp_AcquireSRWLockExclusive
0x180080a1c  mov     r8d, [rbp+57h+BufferSize]; BufferSize
0x180080a20  lea     r9, [rbp+57h+NewElement]; NewElement
0x180080a24  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180080a28  lea     rcx, ?_connectionCache@@3U_RTL_AVL_TABLE@@A; Table
0x180080a2f  call    cs:__imp_RtlInsertElementGenericTableAvl
0x180080a35  mov     rsi, rax
0x180080a38  test    rax, rax
0x180080a3b  jz      loc_180080B16
0x180080a41  cmp     [rbp+57h+NewElement], r14b
0x180080a45  jz      loc_180080ACB
0x180080a4b  cmp     [rax], rdi
0x180080a4e  jz      short loc_180080A69
0x180080a50  mov     r8d, 2EAh; unsigned int
0x180080a56  lea     rdx, aOnecoreDsNetap_14; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180080a5d  lea     rcx, aPcacheentryLda; "pCacheEntry->ldapConnection.pldap == pl"...
0x180080a64  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180080a69  cmp     dword ptr [rsi+10h], 1
0x180080a6d  jz      short loc_180080A88
0x180080a6f  mov     r8d, 2EBh; unsigned int
0x180080a75  lea     rdx, aOnecoreDsNetap_14; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180080a7c  lea     rcx, aPcacheentryRef; "pCacheEntry->refCount == 1"
0x180080a83  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180080a88  xor     edi, edi
0x180080a8a  lock inc cs:qword_1800F1E48
0x180080a92  mov     rax, [r15+70h]
0x180080a96  mov     rcx, [rax+168h]
0x180080a9d  lock inc qword ptr [rcx+0C8h]
0x180080aa5  mov     rax, [r15+70h]
0x180080aa9  lock inc dword ptr [rax+10h]
0x180080aad  mov     eax, cs:?_connectionCacheCount@@3KA; ulong _connectionCacheCount
0x180080ab3  inc     eax
0x180080ab5  cmp     eax, cs:?_connectionCacheHighwaterMark@@3KA; ulong _connectionCacheHighwaterMark
0x180080abb  mov     cs:?_connectionCacheCount@@3KA, eax; ulong _connectionCacheCount
0x180080ac1  jbe     short loc_180080AD5
0x180080ac3  mov     cs:?_connectionCacheHighwaterMark@@3KA, eax; ulong _connectionCacheHighwaterMark
0x180080ac9  jmp     short loc_180080AD5
0x180080acb  lock inc dword ptr [rax+10h]
0x180080acf  inc     cs:?_connectionAddRaces@@3KA; ulong _connectionAddRaces
0x180080ad5  lea     rcx, ?_connectionCache@@3U_RTL_AVL_TABLE@@A; Table
0x180080adc  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x180080ae2  cmp     eax, cs:?_connectionCacheCount@@3KA; ulong _connectionCacheCount
0x180080ae8  jz      short loc_180080B03
0x180080aea  mov     r8d, 30Eh; unsigned int
0x180080af0  lea     rdx, aOnecoreDsNetap_14; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180080af7  lea     rcx, aRtlnumbergener; "RtlNumberGenericTableElementsAvl(&_conn"...
0x180080afe  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180080b03  mov     rdx, [r15+70h]; struct _NL_DC_DOMAIN_ENTRY *
0x180080b07  mov     rcx, rsi; struct _LDAP_CACHE_ENTRY *
0x180080b0a  call    ?NlpWarnIfCachedHostUsedForMultipleDomains@@YAXPEAU_LDAP_CACHE_ENTRY@@PEAU_NL_DC_DOMAIN_ENTRY@@@Z; NlpWarnIfCachedHostUsedForMultipleDomains(_LDAP_CACHE_ENTRY *,_NL_DC_DOMAIN_ENTRY *)
0x180080b0f  xor     ebx, ebx
0x180080b11  mov     r14, rsi
0x180080b14  jmp     short loc_180080B1B
0x180080b16  mov     ebx, 0Eh
0x180080b1b  lea     rcx, ?_rwCacheLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180080b22  call    cs:__imp_ReleaseSRWLockExclusive
0x180080b28  test    rdi, rdi
0x180080b2b  jz      short loc_180080B35
0x180080b2d  mov     rcx, rdi; struct ldap *
0x180080b30  call    ?NlpUnbindLdapConnection@@YAXPEAUldap@@@Z; NlpUnbindLdapConnection(ldap *)
0x180080b35  mov     ecx, ebx; dwErrCode
0x180080b37  call    cs:__imp_SetLastError
0x180080b3d  mov     rax, r14
0x180080b40  mov     rcx, [rbp+57h+var_30]
0x180080b44  xor     rcx, rsp; StackCookie
0x180080b47  call    __security_check_cookie
0x180080b4c  mov     rbx, [rsp+100h+arg_10]
0x180080b54  add     rsp, 0E0h
0x180080b5b  pop     r15
0x180080b5d  pop     r14
0x180080b5f  pop     rdi
0x180080b60  pop     rsi
0x180080b61  pop     rbp
0x180080b62  retn
```
