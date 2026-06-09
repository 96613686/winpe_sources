# NlpReleaseCachedLocatorLdapConnectionWorker(_CACHED_CONNECTION *)

- ea: `0x180080d60`
- end: `0x180080f84`
- name: `?NlpReleaseCachedLocatorLdapConnectionWorker@@YAXPEAU_CACHED_CONNECTION@@@Z`
- size: `548`
- prototype: `void __fastcall(struct _CACHED_CONNECTION *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180080670`

## callees

- `0x18000d450`
- `0x18000d710`
- `0x18000e270`
- `0x180080d60`
- `0x180081044`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180080f37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180080f37`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180080df5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180080df5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180080f4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180080f4d`
- `RPCRT4!UuidEqual` at `0x180080e52`
- `RPCRT4!UuidEqual` at `0x180080e52`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180080e02`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180080ef9`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180080e02`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180080ef9`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180080e77`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180080e77`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180080e34`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180080e34`

## string_xrefs

- `0x180080e16`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\ldapcache.cxx`
- `0x180080e91`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\ldapcache.cxx`
- `0x180080ed9`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\ldapcache.cxx`
- `0x180080f0d`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\ldapcache.cxx`
- `0x180080e1d`: `RtlNumberGenericTableElementsAvl(&_connectionCache) == _connectionCacheCount`
- `0x180080f14`: `RtlNumberGenericTableElementsAvl(&_connectionCache) == _connectionCacheCount`
- `0x180080e98`: `_connectionCacheCount > 0`

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
        1112,
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
                1152,
                v15);
              v16 = _connectionCacheCount;
            }
            _connectionCacheCount = v16 - 1;
            _InterlockedDecrement64(&qword_1800F1E48);
            _InterlockedDecrement64((volatile signed __int64 *)(*(_QWORD *)(v27 + 360) + 200LL));
            v4 = (struct _NL_DC_DOMAIN_ENTRY *)v27;
          }
          else
          {
            NlAssertFailed("FALSE", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\coreloc\\ldapcache.cxx", 1166, v15);
            v11 = 0;
            v2 = 87;
          }
          if ( RtlNumberGenericTableElementsAvl(&_connectionCache) != _connectionCacheCount )
            NlAssertFailed(
              "RtlNumberGenericTableElementsAvl(&_connectionCache) == _connectionCacheCount",
              "onecore\\ds\\netapi\\svcdlls\\logonsrv\\coreloc\\ldapcache.cxx",
              1171,
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
0x180080d60  mov     [rsp-8+arg_8], rbx
0x180080d65  mov     [rsp-8+arg_10], rsi
0x180080d6a  push    rbp
0x180080d6b  push    rdi
0x180080d6c  push    r14
0x180080d6e  lea     rbp, [rsp-47h]
0x180080d73  sub     rsp, 0D0h
0x180080d7a  mov     rax, cs:__security_cookie
0x180080d81  xor     rax, rsp
0x180080d84  mov     [rbp+57h+var_20], rax
0x180080d88  movups  xmm0, xmmword ptr [rcx]
0x180080d8b  mov     rax, [rcx+80h]
0x180080d92  xor     r14d, r14d
0x180080d95  movups  xmm1, xmmword ptr [rcx+10h]
0x180080d99  xor     esi, esi
0x180080d9b  mov     [rbp+57h+var_30], rax
0x180080d9f  movups  [rbp+57h+Buffer], xmm0
0x180080da3  mov     [rbp+57h+Status], r14d
0x180080da7  or      eax, 0FFFFFFFFh
0x180080daa  movups  xmm0, xmmword ptr [rcx+20h]
0x180080dae  movups  xmmword ptr [rbp+57h+Uuid1.Data1], xmm1
0x180080db2  movups  xmm1, xmmword ptr [rcx+30h]
0x180080db6  movups  [rbp+57h+var_90], xmm0
0x180080dba  movups  xmm0, xmmword ptr [rcx+40h]
0x180080dbe  movups  [rbp+57h+var_80], xmm1
0x180080dc2  movups  xmm1, xmmword ptr [rcx+50h]
0x180080dc6  movups  [rbp+57h+var_70], xmm0
0x180080dca  movups  xmm0, xmmword ptr [rcx+60h]
0x180080dce  movups  [rbp+57h+var_60], xmm1
0x180080dd2  movups  xmm1, xmmword ptr [rcx+70h]
0x180080dd6  movups  [rbp+57h+var_50], xmm0
0x180080dda  movups  [rbp+57h+var_40], xmm1
0x180080dde  lock xadd [rcx+10h], eax
0x180080de3  cmp     eax, 1
0x180080de6  jnz     loc_180080F4A
0x180080dec  lea     rcx, ?_rwCacheLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180080df3  xor     ebx, ebx
0x180080df5  call    cs:__imp_AcquireSRWLockExclusive
0x180080dfb  lea     rcx, ?_connectionCache@@3U_RTL_AVL_TABLE@@A; Table
0x180080e02  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x180080e08  cmp     eax, cs:?_connectionCacheCount@@3KA; ulong _connectionCacheCount
0x180080e0e  jz      short loc_180080E29
0x180080e10  mov     r8d, 458h; unsigned int
0x180080e16  lea     rdx, aOnecoreDsNetap_14; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180080e1d  lea     rcx, aRtlnumbergener; "RtlNumberGenericTableElementsAvl(&_conn"...
0x180080e24  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180080e29  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180080e2d  lea     rcx, ?_connectionCache@@3U_RTL_AVL_TABLE@@A; Table
0x180080e34  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180080e3a  mov     rdi, rax
0x180080e3d  test    rax, rax
0x180080e40  jz      loc_180080F2A
0x180080e46  lea     rdx, [rax+1Ch]; Uuid2
0x180080e4a  lea     r8, [rbp+57h+Status]; Status
0x180080e4e  lea     rcx, [rbp+57h+Uuid1.Data4+4]; Uuid1
0x180080e52  call    cs:__imp_UuidEqual
0x180080e58  test    eax, eax
0x180080e5a  jz      loc_180080F22
0x180080e60  cmp     [rdi+10h], ebx
0x180080e63  jnz     loc_180080F30
0x180080e69  mov     rbx, [rdi]
0x180080e6c  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180080e70  lea     rcx, ?_connectionCache@@3U_RTL_AVL_TABLE@@A; Table
0x180080e77  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180080e7d  test    al, al
0x180080e7f  jz      short loc_180080ED3
0x180080e81  mov     eax, cs:?_connectionCacheCount@@3KA; ulong _connectionCacheCount
0x180080e87  test    eax, eax
0x180080e89  jnz     short loc_180080EAA
0x180080e8b  mov     r8d, 480h; unsigned int
0x180080e91  lea     rdx, aOnecoreDsNetap_14; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180080e98  lea     rcx, aConnectioncach; "_connectionCacheCount > 0"
0x180080e9f  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180080ea4  mov     eax, cs:?_connectionCacheCount@@3KA; ulong _connectionCacheCount
0x180080eaa  dec     eax
0x180080eac  mov     cs:?_connectionCacheCount@@3KA, eax; ulong _connectionCacheCount
0x180080eb2  lock dec cs:qword_1800F1E48
0x180080eba  mov     rax, [rbp+57h+var_30]
0x180080ebe  mov     rcx, [rax+168h]
0x180080ec5  lock dec qword ptr [rcx+0C8h]
0x180080ecd  mov     rsi, [rbp+57h+var_30]
0x180080ed1  jmp     short loc_180080EF2
0x180080ed3  mov     r8d, 48Eh; unsigned int
0x180080ed9  lea     rdx, aOnecoreDsNetap_14; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180080ee0  lea     rcx, aFalse; "FALSE"
0x180080ee7  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180080eec  xor     ebx, ebx
0x180080eee  lea     r14d, [rbx+57h]
0x180080ef2  lea     rcx, ?_connectionCache@@3U_RTL_AVL_TABLE@@A; Table
0x180080ef9  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x180080eff  cmp     eax, cs:?_connectionCacheCount@@3KA; ulong _connectionCacheCount
0x180080f05  jz      short loc_180080F30
0x180080f07  mov     r8d, 493h; unsigned int
0x180080f0d  lea     rdx, aOnecoreDsNetap_14; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180080f14  lea     rcx, aRtlnumbergener; "RtlNumberGenericTableElementsAvl(&_conn"...
0x180080f1b  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180080f20  jmp     short loc_180080F30
0x180080f22  inc     cs:?_connectionReleaseReinsertRaces@@3KA; ulong _connectionReleaseReinsertRaces
0x180080f28  jmp     short loc_180080F30
0x180080f2a  inc     cs:?_connectionReleaseNotFoundRaces@@3KA; ulong _connectionReleaseNotFoundRaces
0x180080f30  lea     rcx, ?_rwCacheLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180080f37  call    cs:__imp_ReleaseSRWLockExclusive
0x180080f3d  test    rbx, rbx
0x180080f40  jz      short loc_180080F4A
0x180080f42  mov     rcx, rbx; struct ldap *
0x180080f45  call    ?NlpUnbindLdapConnection@@YAXPEAUldap@@@Z; NlpUnbindLdapConnection(ldap *)
0x180080f4a  mov     ecx, r14d; dwErrCode
0x180080f4d  call    cs:__imp_SetLastError
0x180080f53  test    rsi, rsi
0x180080f56  jz      short loc_180080F60
0x180080f58  mov     rcx, rsi; struct _NL_DC_DOMAIN_ENTRY *
0x180080f5b  call    ?NetpDcDerefDomainEntry@@YAXPEAU_NL_DC_DOMAIN_ENTRY@@@Z; NetpDcDerefDomainEntry(_NL_DC_DOMAIN_ENTRY *)
0x180080f60  mov     rcx, [rbp+57h+var_20]
0x180080f64  xor     rcx, rsp; StackCookie
0x180080f67  call    __security_check_cookie
0x180080f6c  lea     r11, [rsp+0E0h+var_10]
0x180080f74  mov     rbx, [r11+28h]
0x180080f78  mov     rsi, [r11+30h]
0x180080f7c  mov     rsp, r11
0x180080f7f  pop     r14
0x180080f81  pop     rdi
0x180080f82  pop     rbp
0x180080f83  retn
```
