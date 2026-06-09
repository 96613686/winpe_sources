# NlpCreateAndAddCachedConnection(_NL_GETDC_CONTEXT *,char *,ulong)

- ea: `0x1800867d0`
- end: `0x180086aaa`
- name: `?NlpCreateAndAddCachedConnection@@YAPEAU_CACHED_CONNECTION@@PEAU_NL_GETDC_CONTEXT@@PEADK@Z`
- size: `730`
- prototype: `struct _CACHED_CONNECTION *(struct _NL_GETDC_CONTEXT *, char *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x1800862d4`

## callees

- `0x18000dd00`
- `0x18000e910`
- `0x18000f3e4`
- `0x180018fac`
- `0x1800867d0`
- `0x180086f2c`
- `0x180086ff4`
- `0x180087034`
- `0x18008709c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180086a5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180086a5c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008693e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008693e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180086a77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180086a77`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180086924`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180086924`
- `RPCRT4!UuidCreate` at `0x1800868f0`
- `RPCRT4!UuidCreate` at `0x1800868f0`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180086a10`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180086a10`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18008695d`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18008695d`
- `WLDAP32!__imp_LdapGetLastError` at `0x18008682d`
- `WLDAP32!__imp_LdapGetLastError` at `0x18008682d`
- `WLDAP32!__imp_cldap_openA` at `0x180086819`
- `WLDAP32!__imp_cldap_openA` at `0x180086819`

## string_xrefs

- `0x1800868cb`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\ldapcache.cxx`
- `0x180086908`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\ldapcache.cxx`
- `0x18008698a`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\ldapcache.cxx`
- `0x1800869a9`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\ldapcache.cxx`
- `0x180086a2a`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\ldapcache.cxx`
- `0x180086991`: `pCacheEntry->ldapConnection.pldap == pldap`
- `0x1800869b0`: `pCacheEntry->refCount == 1`
- `0x180086a31`: `RtlNumberGenericTableElementsAvl(&_connectionCache) == _connectionCacheCount`

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
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_ffa122217ec63a12741a79df23bf59f1_Traceguids, v8, v8);
    goto LABEL_25;
  }
  memset_0(&Buffer, 0, 0x88u);
  v26 = *((_QWORD *)a1 + 14);
  v20 = 1;
  BufferSize = 136;
  Buffer = v6;
  if ( (int)RtlStringCbCopyA(v24, v9, a2) < 0 )
  {
    NlAssertFailed("FALSE", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\coreloc\\ldapcache.cxx", 0x2C1u, v10);
    LastError = 87;
LABEL_25:
    NlpUnbindLdapConnection(v6);
    goto LABEL_26;
  }
  v25 = 0;
  LastError = UuidCreate(&Uuid);
  if ( LastError )
  {
    NlAssertFailed("FALSE", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\coreloc\\ldapcache.cxx", 0x2CAu, v11);
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
          0x2E9u,
          v13);
      if ( *((_DWORD *)v14 + 4) != 1 )
        NlAssertFailed(
          "pCacheEntry->refCount == 1",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\coreloc\\ldapcache.cxx",
          0x2EAu,
          v13);
      v6 = 0;
      _InterlockedIncrement64(&qword_1800F8E08);
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
        0x30Du,
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
0x1800867d0  mov     [rsp-8+arg_10], rbx
0x1800867d5  push    rbp
0x1800867d6  push    rsi
0x1800867d7  push    rdi
0x1800867d8  push    r14
0x1800867da  push    r15
0x1800867dc  lea     rbp, [rsp-37h]
0x1800867e1  sub     rsp, 0E0h
0x1800867e8  mov     rax, cs:__security_cookie
0x1800867ef  xor     rax, rsp
0x1800867f2  mov     [rbp+57h+var_30], rax
0x1800867f6  mov     rsi, rdx
0x1800867f9  mov     [rbp+57h+NewElement], 0
0x1800867fd  mov     r15, rcx
0x180086800  xor     edx, edx; Val
0x180086802  lea     rcx, [rbp+57h+Buffer]; void *
0x180086806  mov     r8d, 88h; Size
0x18008680c  call    memset_0
0x180086811  xor     edx, edx; PortNumber
0x180086813  mov     rcx, rsi; HostName
0x180086816  xor     r14d, r14d
0x180086819  call    cs:__imp_cldap_openA
0x180086820  nop     dword ptr [rax+rax+00h]
0x180086825  mov     rdi, rax
0x180086828  test    rax, rax
0x18008682b  jnz     short loc_180086840
0x18008682d  call    cs:__imp_LdapGetLastError
0x180086834  nop     dword ptr [rax+rax+00h]
0x180086839  mov     ebx, eax
0x18008683b  jmp     loc_180086A75
0x180086840  mov     rcx, rdi; ld
0x180086843  call    ?NlpSetLocatorCLDAPConnectionConfig@@YAKPEAUldap@@@Z; NlpSetLocatorCLDAPConnectionConfig(ldap *)
0x180086848  mov     ebx, eax
0x18008684a  test    eax, eax
0x18008684c  jz      short loc_18008688A
0x18008684e  mov     rcx, cs:WPP_GLOBAL_Control
0x180086855  test    byte ptr [rcx+1Ch], 4
0x180086859  jz      loc_180086A6D
0x18008685f  cmp     byte ptr [rcx+19h], 4
0x180086863  jb      loc_180086A6D
0x180086869  mov     rcx, [rcx+10h]
0x18008686d  lea     r8, WPP_ffa122217ec63a12741a79df23bf59f1_Traceguids
0x180086874  mov     edx, 0Bh
0x180086879  mov     [rsp+100h+var_E0], eax
0x18008687d  mov     r9d, eax
0x180086880  call    WPP_SF_Dd
0x180086885  jmp     loc_180086A6D
0x18008688a  xor     edx, edx; Val
0x18008688c  lea     rcx, [rbp+57h+Buffer]; void *
0x180086890  mov     r8d, 88h; Size
0x180086896  call    memset_0
0x18008689b  mov     rax, [r15+70h]
0x18008689f  lea     rcx, [rbp+57h+var_90]; char *
0x1800868a3  mov     r8, rsi; char *
0x1800868a6  mov     [rbp+57h+var_40], rax
0x1800868aa  mov     [rbp+57h+var_B0], 1
0x1800868b1  mov     [rbp+57h+BufferSize], 88h
0x1800868b8  mov     [rbp+57h+Buffer], rdi
0x1800868bc  call    ?RtlStringCbCopyA@@YAJPEAD_KPEBD@Z; RtlStringCbCopyA(char *,unsigned __int64,char const *)
0x1800868c1  test    eax, eax
0x1800868c3  jns     short loc_1800868E8
0x1800868c5  mov     r8d, 2C1h; unsigned int
0x1800868cb  lea     rdx, aOnecoreDsNetap_14; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800868d2  lea     rcx, aFalse; "FALSE"
0x1800868d9  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800868de  mov     ebx, 57h ; 'W'
0x1800868e3  jmp     loc_180086A6D
0x1800868e8  lea     rcx, [rbp+57h+Uuid]; Uuid
0x1800868ec  mov     [rbp+57h+var_48], r14d
0x1800868f0  call    cs:__imp_UuidCreate
0x1800868f7  nop     dword ptr [rax+rax+00h]
0x1800868fc  mov     ebx, eax
0x1800868fe  test    eax, eax
0x180086900  jz      short loc_180086920
0x180086902  mov     r8d, 2CAh; unsigned int
0x180086908  lea     rdx, aOnecoreDsNetap_14; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18008690f  lea     rcx, aFalse; "FALSE"
0x180086916  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18008691b  jmp     loc_180086A6D
0x180086920  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180086924  call    cs:__imp_GetSystemTimeAsFileTime
0x18008692b  nop     dword ptr [rax+rax+00h]
0x180086930  lea     rcx, ?_rwCacheLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180086937  mov     [rbp+57h+var_B8], 1
0x18008693e  call    cs:__imp_AcquireSRWLockExclusive
0x180086945  nop     dword ptr [rax+rax+00h]
0x18008694a  mov     r8d, [rbp+57h+BufferSize]; BufferSize
0x18008694e  lea     r9, [rbp+57h+NewElement]; NewElement
0x180086952  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180086956  lea     rcx, ?_connectionCache@@3U_RTL_AVL_TABLE@@A; Table
0x18008695d  call    cs:__imp_RtlInsertElementGenericTableAvl
0x180086964  nop     dword ptr [rax+rax+00h]
0x180086969  mov     rsi, rax
0x18008696c  test    rax, rax
0x18008696f  jz      loc_180086A50
0x180086975  cmp     [rbp+57h+NewElement], r14b
0x180086979  jz      loc_1800869FF
0x18008697f  cmp     [rax], rdi
0x180086982  jz      short loc_18008699D
0x180086984  mov     r8d, 2E9h; unsigned int
0x18008698a  lea     rdx, aOnecoreDsNetap_14; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180086991  lea     rcx, aPcacheentryLda; "pCacheEntry->ldapConnection.pldap == pl"...
0x180086998  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18008699d  cmp     dword ptr [rsi+10h], 1
0x1800869a1  jz      short loc_1800869BC
0x1800869a3  mov     r8d, 2EAh; unsigned int
0x1800869a9  lea     rdx, aOnecoreDsNetap_14; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800869b0  lea     rcx, aPcacheentryRef; "pCacheEntry->refCount == 1"
0x1800869b7  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800869bc  xor     edi, edi
0x1800869be  lock inc cs:qword_1800F8E08
0x1800869c6  mov     rax, [r15+70h]
0x1800869ca  mov     rcx, [rax+168h]
0x1800869d1  lock inc qword ptr [rcx+0C8h]
0x1800869d9  mov     rax, [r15+70h]
0x1800869dd  lock inc dword ptr [rax+10h]
0x1800869e1  mov     eax, cs:?_connectionCacheCount@@3KA; ulong _connectionCacheCount
0x1800869e7  inc     eax
0x1800869e9  cmp     eax, cs:?_connectionCacheHighwaterMark@@3KA; ulong _connectionCacheHighwaterMark
0x1800869ef  mov     cs:?_connectionCacheCount@@3KA, eax; ulong _connectionCacheCount
0x1800869f5  jbe     short loc_180086A09
0x1800869f7  mov     cs:?_connectionCacheHighwaterMark@@3KA, eax; ulong _connectionCacheHighwaterMark
0x1800869fd  jmp     short loc_180086A09
0x1800869ff  lock inc dword ptr [rax+10h]
0x180086a03  inc     cs:?_connectionAddRaces@@3KA; ulong _connectionAddRaces
0x180086a09  lea     rcx, ?_connectionCache@@3U_RTL_AVL_TABLE@@A; Table
0x180086a10  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x180086a17  nop     dword ptr [rax+rax+00h]
0x180086a1c  cmp     eax, cs:?_connectionCacheCount@@3KA; ulong _connectionCacheCount
0x180086a22  jz      short loc_180086A3D
0x180086a24  mov     r8d, 30Dh; unsigned int
0x180086a2a  lea     rdx, aOnecoreDsNetap_14; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180086a31  lea     rcx, aRtlnumbergener; "RtlNumberGenericTableElementsAvl(&_conn"...
0x180086a38  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180086a3d  mov     rdx, [r15+70h]; struct _NL_DC_DOMAIN_ENTRY *
0x180086a41  mov     rcx, rsi; struct _LDAP_CACHE_ENTRY *
0x180086a44  call    ?NlpWarnIfCachedHostUsedForMultipleDomains@@YAXPEAU_LDAP_CACHE_ENTRY@@PEAU_NL_DC_DOMAIN_ENTRY@@@Z; NlpWarnIfCachedHostUsedForMultipleDomains(_LDAP_CACHE_ENTRY *,_NL_DC_DOMAIN_ENTRY *)
0x180086a49  xor     ebx, ebx
0x180086a4b  mov     r14, rsi
0x180086a4e  jmp     short loc_180086A55
0x180086a50  mov     ebx, 0Eh
0x180086a55  lea     rcx, ?_rwCacheLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180086a5c  call    cs:__imp_ReleaseSRWLockExclusive
0x180086a63  nop     dword ptr [rax+rax+00h]
0x180086a68  test    rdi, rdi
0x180086a6b  jz      short loc_180086A75
0x180086a6d  mov     rcx, rdi; struct ldap *
0x180086a70  call    ?NlpUnbindLdapConnection@@YAXPEAUldap@@@Z; NlpUnbindLdapConnection(ldap *)
0x180086a75  mov     ecx, ebx; dwErrCode
0x180086a77  call    cs:__imp_SetLastError
0x180086a7e  nop     dword ptr [rax+rax+00h]
0x180086a83  mov     rax, r14
0x180086a86  mov     rcx, [rbp+57h+var_30]
0x180086a8a  xor     rcx, rsp; StackCookie
0x180086a8d  call    __security_check_cookie
0x180086a92  mov     rbx, [rsp+100h+arg_10]
0x180086a9a  add     rsp, 0E0h
0x180086aa1  pop     r15
0x180086aa3  pop     r14
0x180086aa5  pop     rdi
0x180086aa6  pop     rsi
0x180086aa7  pop     rbp
0x180086aa8  retn
```
