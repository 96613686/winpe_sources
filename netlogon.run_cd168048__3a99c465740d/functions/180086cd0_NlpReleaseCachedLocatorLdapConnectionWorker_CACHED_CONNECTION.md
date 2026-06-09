# NlpReleaseCachedLocatorLdapConnectionWorker(_CACHED_CONNECTION *)

- ea: `0x180086cd0`
- end: `0x180086f25`
- name: `?NlpReleaseCachedLocatorLdapConnectionWorker@@YAXPEAU_CACHED_CONNECTION@@@Z`
- size: `597`
- prototype: `void __fastcall(struct _CACHED_CONNECTION *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18008654c`

## callees

- `0x18000d9dc`
- `0x18000dd00`
- `0x18000e910`
- `0x180086cd0`
- `0x180086ff4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180086ecb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180086ecb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180086d65`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180086d65`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180086ee7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180086ee7`
- `RPCRT4!UuidEqual` at `0x180086dd4`
- `RPCRT4!UuidEqual` at `0x180086dd4`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180086d78`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180086e87`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180086d78`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180086e87`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180086dff`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180086dff`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180086db0`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180086db0`

## string_xrefs

- `0x180086d92`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\ldapcache.cxx`
- `0x180086e1f`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\ldapcache.cxx`
- `0x180086e67`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\ldapcache.cxx`
- `0x180086ea1`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\ldapcache.cxx`
- `0x180086d99`: `RtlNumberGenericTableElementsAvl(&_connectionCache) == _connectionCacheCount`
- `0x180086ea8`: `RtlNumberGenericTableElementsAvl(&_connectionCache) == _connectionCacheCount`
- `0x180086e26`: `_connectionCacheCount > 0`

## pseudocode

```c
void __fastcall NlpReleaseCachedLocatorLdapConnectionWorker(struct _CACHED_CONNECTION *a1)
{
  __int128 v1; // xmm0
  DWORD v2; // r14d
  UUID v3; // xmm1
  struct _NL_DC_DOMAIN_ENTRY *v4; // rsi
  __int128 v5; // xmm0
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  struct ldap *v11; // rbx
  char *v12; // r9
  char *v13; // rax
  char *v14; // rdi
  char *v15; // r9
  unsigned int v16; // eax
  char *v17; // r9
  RPC_STATUS Status[4]; // [rsp+20h] [rbp-69h] BYREF
  __int128 Buffer; // [rsp+30h] [rbp-59h] BYREF
  UUID Uuid1; // [rsp+40h] [rbp-49h] BYREF
  __int128 v21; // [rsp+50h] [rbp-39h]
  __int128 v22; // [rsp+60h] [rbp-29h]
  __int128 v23; // [rsp+70h] [rbp-19h]
  __int128 v24; // [rsp+80h] [rbp-9h]
  __int128 v25; // [rsp+90h] [rbp+7h]
  __int128 v26; // [rsp+A0h] [rbp+17h]
  __int64 v27; // [rsp+B0h] [rbp+27h]

  v1 = *(_OWORD *)a1;
  v2 = 0;
  v3 = (UUID)*((_OWORD *)a1 + 1);
  v4 = 0;
  v27 = *((_QWORD *)a1 + 16);
  Buffer = v1;
  Status[0] = 0;
  v5 = *((_OWORD *)a1 + 2);
  Uuid1 = v3;
  v6 = *((_OWORD *)a1 + 3);
  v21 = v5;
  v7 = *((_OWORD *)a1 + 4);
  v22 = v6;
  v8 = *((_OWORD *)a1 + 5);
  v23 = v7;
  v9 = *((_OWORD *)a1 + 6);
  v24 = v8;
  v10 = *((_OWORD *)a1 + 7);
  v25 = v9;
  v26 = v10;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 4, 0xFFFFFFFF) == 1 )
  {
    v11 = 0;
    AcquireSRWLockExclusive(&_rwCacheLock);
    if ( RtlNumberGenericTableElementsAvl(&_connectionCache) != _connectionCacheCount )
      NlAssertFailed(
        "RtlNumberGenericTableElementsAvl(&_connectionCache) == _connectionCacheCount",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\coreloc\\ldapcache.cxx",
        0x457u,
        v12);
    v13 = (char *)RtlLookupElementGenericTableAvl(&_connectionCache, &Buffer);
    v14 = v13;
    if ( v13 )
    {
      if ( UuidEqual((UUID *)&Uuid1.Data4[4], (UUID *)(v13 + 28), Status) )
      {
        if ( !*((_DWORD *)v14 + 4) )
        {
          v11 = *(struct ldap **)v14;
          if ( RtlDeleteElementGenericTableAvl(&_connectionCache, &Buffer) )
          {
            v16 = _connectionCacheCount;
            if ( !_connectionCacheCount )
            {
              NlAssertFailed(
                "_connectionCacheCount > 0",
                "onecore\\ds\\netapi\\svcdlls\\logonsrv\\coreloc\\ldapcache.cxx",
                0x47Fu,
                v15);
              v16 = _connectionCacheCount;
            }
            _connectionCacheCount = v16 - 1;
            _InterlockedDecrement64(&qword_1800F8E08);
            _InterlockedDecrement64((volatile signed __int64 *)(*(_QWORD *)(v27 + 360) + 200LL));
            v4 = (struct _NL_DC_DOMAIN_ENTRY *)v27;
          }
          else
          {
            NlAssertFailed("FALSE", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\coreloc\\ldapcache.cxx", 0x48Du, v15);
            v11 = 0;
            v2 = 87;
          }
          if ( RtlNumberGenericTableElementsAvl(&_connectionCache) != _connectionCacheCount )
            NlAssertFailed(
              "RtlNumberGenericTableElementsAvl(&_connectionCache) == _connectionCacheCount",
              "onecore\\ds\\netapi\\svcdlls\\logonsrv\\coreloc\\ldapcache.cxx",
              0x492u,
              v17);
        }
      }
      else
      {
        ++_connectionReleaseReinsertRaces;
      }
    }
    else
    {
      ++_connectionReleaseNotFoundRaces;
    }
    ReleaseSRWLockExclusive(&_rwCacheLock);
    if ( v11 )
      NlpUnbindLdapConnection(v11);
  }
  SetLastError(v2);
  if ( v4 )
    NetpDcDerefDomainEntry(v4);
}

```

## disassembly

```asm
0x180086cd0  mov     [rsp-8+arg_8], rbx
0x180086cd5  mov     [rsp-8+arg_10], rsi
0x180086cda  push    rbp
0x180086cdb  push    rdi
0x180086cdc  push    r14
0x180086cde  lea     rbp, [rsp-47h]
0x180086ce3  sub     rsp, 0D0h
0x180086cea  mov     rax, cs:__security_cookie
0x180086cf1  xor     rax, rsp
0x180086cf4  mov     [rbp+57h+var_20], rax
0x180086cf8  movups  xmm0, xmmword ptr [rcx]
0x180086cfb  mov     rax, [rcx+80h]
0x180086d02  xor     r14d, r14d
0x180086d05  movups  xmm1, xmmword ptr [rcx+10h]
0x180086d09  xor     esi, esi
0x180086d0b  mov     [rbp+57h+var_30], rax
0x180086d0f  movups  [rbp+57h+Buffer], xmm0
0x180086d13  mov     [rbp+57h+Status], r14d
0x180086d17  or      eax, 0FFFFFFFFh
0x180086d1a  movups  xmm0, xmmword ptr [rcx+20h]
0x180086d1e  movups  xmmword ptr [rbp+57h+Uuid1.Data1], xmm1
0x180086d22  movups  xmm1, xmmword ptr [rcx+30h]
0x180086d26  movups  [rbp+57h+var_90], xmm0
0x180086d2a  movups  xmm0, xmmword ptr [rcx+40h]
0x180086d2e  movups  [rbp+57h+var_80], xmm1
0x180086d32  movups  xmm1, xmmword ptr [rcx+50h]
0x180086d36  movups  [rbp+57h+var_70], xmm0
0x180086d3a  movups  xmm0, xmmword ptr [rcx+60h]
0x180086d3e  movups  [rbp+57h+var_60], xmm1
0x180086d42  movups  xmm1, xmmword ptr [rcx+70h]
0x180086d46  movups  [rbp+57h+var_50], xmm0
0x180086d4a  movups  [rbp+57h+var_40], xmm1
0x180086d4e  lock xadd [rcx+10h], eax
0x180086d53  cmp     eax, 1
0x180086d56  jnz     loc_180086EE4
0x180086d5c  lea     rcx, ?_rwCacheLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180086d63  xor     ebx, ebx
0x180086d65  call    cs:__imp_AcquireSRWLockExclusive
0x180086d6c  nop     dword ptr [rax+rax+00h]
0x180086d71  lea     rcx, ?_connectionCache@@3U_RTL_AVL_TABLE@@A; Table
0x180086d78  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x180086d7f  nop     dword ptr [rax+rax+00h]
0x180086d84  cmp     eax, cs:?_connectionCacheCount@@3KA; ulong _connectionCacheCount
0x180086d8a  jz      short loc_180086DA5
0x180086d8c  mov     r8d, 457h; unsigned int
0x180086d92  lea     rdx, aOnecoreDsNetap_14; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180086d99  lea     rcx, aRtlnumbergener; "RtlNumberGenericTableElementsAvl(&_conn"...
0x180086da0  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180086da5  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180086da9  lea     rcx, ?_connectionCache@@3U_RTL_AVL_TABLE@@A; Table
0x180086db0  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180086db7  nop     dword ptr [rax+rax+00h]
0x180086dbc  mov     rdi, rax
0x180086dbf  test    rax, rax
0x180086dc2  jz      loc_180086EBE
0x180086dc8  lea     rdx, [rax+1Ch]; Uuid2
0x180086dcc  lea     r8, [rbp+57h+Status]; Status
0x180086dd0  lea     rcx, [rbp+57h+Uuid1.Data4+4]; Uuid1
0x180086dd4  call    cs:__imp_UuidEqual
0x180086ddb  nop     dword ptr [rax+rax+00h]
0x180086de0  test    eax, eax
0x180086de2  jz      loc_180086EB6
0x180086de8  cmp     [rdi+10h], ebx
0x180086deb  jnz     loc_180086EC4
0x180086df1  mov     rbx, [rdi]
0x180086df4  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180086df8  lea     rcx, ?_connectionCache@@3U_RTL_AVL_TABLE@@A; Table
0x180086dff  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180086e06  nop     dword ptr [rax+rax+00h]
0x180086e0b  test    al, al
0x180086e0d  jz      short loc_180086E61
0x180086e0f  mov     eax, cs:?_connectionCacheCount@@3KA; ulong _connectionCacheCount
0x180086e15  test    eax, eax
0x180086e17  jnz     short loc_180086E38
0x180086e19  mov     r8d, 47Fh; unsigned int
0x180086e1f  lea     rdx, aOnecoreDsNetap_14; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180086e26  lea     rcx, aConnectioncach; "_connectionCacheCount > 0"
0x180086e2d  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180086e32  mov     eax, cs:?_connectionCacheCount@@3KA; ulong _connectionCacheCount
0x180086e38  dec     eax
0x180086e3a  mov     cs:?_connectionCacheCount@@3KA, eax; ulong _connectionCacheCount
0x180086e40  lock dec cs:qword_1800F8E08
0x180086e48  mov     rax, [rbp+57h+var_30]
0x180086e4c  mov     rcx, [rax+168h]
0x180086e53  lock dec qword ptr [rcx+0C8h]
0x180086e5b  mov     rsi, [rbp+57h+var_30]
0x180086e5f  jmp     short loc_180086E80
0x180086e61  mov     r8d, 48Dh; unsigned int
0x180086e67  lea     rdx, aOnecoreDsNetap_14; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180086e6e  lea     rcx, aFalse; "FALSE"
0x180086e75  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180086e7a  xor     ebx, ebx
0x180086e7c  lea     r14d, [rbx+57h]
0x180086e80  lea     rcx, ?_connectionCache@@3U_RTL_AVL_TABLE@@A; Table
0x180086e87  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x180086e8e  nop     dword ptr [rax+rax+00h]
0x180086e93  cmp     eax, cs:?_connectionCacheCount@@3KA; ulong _connectionCacheCount
0x180086e99  jz      short loc_180086EC4
0x180086e9b  mov     r8d, 492h; unsigned int
0x180086ea1  lea     rdx, aOnecoreDsNetap_14; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180086ea8  lea     rcx, aRtlnumbergener; "RtlNumberGenericTableElementsAvl(&_conn"...
0x180086eaf  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180086eb4  jmp     short loc_180086EC4
0x180086eb6  inc     cs:?_connectionReleaseReinsertRaces@@3KA; ulong _connectionReleaseReinsertRaces
0x180086ebc  jmp     short loc_180086EC4
0x180086ebe  inc     cs:?_connectionReleaseNotFoundRaces@@3KA; ulong _connectionReleaseNotFoundRaces
0x180086ec4  lea     rcx, ?_rwCacheLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180086ecb  call    cs:__imp_ReleaseSRWLockExclusive
0x180086ed2  nop     dword ptr [rax+rax+00h]
0x180086ed7  test    rbx, rbx
0x180086eda  jz      short loc_180086EE4
0x180086edc  mov     rcx, rbx; struct ldap *
0x180086edf  call    ?NlpUnbindLdapConnection@@YAXPEAUldap@@@Z; NlpUnbindLdapConnection(ldap *)
0x180086ee4  mov     ecx, r14d; dwErrCode
0x180086ee7  call    cs:__imp_SetLastError
0x180086eee  nop     dword ptr [rax+rax+00h]
0x180086ef3  test    rsi, rsi
0x180086ef6  jz      short loc_180086F00
0x180086ef8  mov     rcx, rsi; struct _NL_DC_DOMAIN_ENTRY *
0x180086efb  call    ?NetpDcDerefDomainEntry@@YAXPEAU_NL_DC_DOMAIN_ENTRY@@@Z; NetpDcDerefDomainEntry(_NL_DC_DOMAIN_ENTRY *)
0x180086f00  mov     rcx, [rbp+57h+var_20]
0x180086f04  xor     rcx, rsp; StackCookie
0x180086f07  call    __security_check_cookie
0x180086f0c  lea     r11, [rsp+0E0h+var_10]
0x180086f14  mov     rbx, [r11+28h]
0x180086f18  mov     rsi, [r11+30h]
0x180086f1c  mov     rsp, r11
0x180086f1f  pop     r14
0x180086f21  pop     rdi
0x180086f22  pop     rbp
0x180086f23  retn
```
