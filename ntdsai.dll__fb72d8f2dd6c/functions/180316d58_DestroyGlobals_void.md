# DestroyGlobals(void)

- ea: `0x180316d58`
- end: `0x180316f94`
- name: `?DestroyGlobals@@YAXXZ`
- size: `572`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18032df4c`

## callees

- `0x18000bb80`
- `0x18005ec40`
- `0x180080bbc`
- `0x180316b88`
- `0x180316bb4`
- `0x180316d58`
- `0x180346c24`
- `0x18035e488`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180316e15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180316ea9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180316e15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180316ea9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180316dd2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180316e66`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180316dd2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180316e66`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180316e27`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180316ebb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180316f27`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180316f44`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180316e27`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180316ebb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180316f27`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180316f44`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180316d99`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180316d99`

## pseudocode

```c
void DestroyGlobals(void)
{
  int v0; // ebx
  int v1; // ecx
  unsigned __int64 i; // rbx
  __int64 SpecificPLS; // rsi
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  unsigned int v5; // edx
  _QWORD **v6; // rdi
  _QWORD *v7; // rcx
  _QWORD *v8; // rax
  LDAP_REQUEST *v9; // rcx
  unsigned __int64 v10; // rbx
  __int64 v11; // rsi
  struct _RTL_CRITICAL_SECTION *v12; // rbp
  unsigned int v13; // edx
  _QWORD **v14; // rdi
  _QWORD *v15; // rcx
  _QWORD *v16; // rax
  LDAP_CONN *v17; // rcx
  char v18; // [rsp+40h] [rbp+8h] BYREF

  if ( fLdapInitialized )
  {
    v0 = 0;
    while ( 1 )
    {
      _InterlockedIncrement(&ActiveLdapConnObjects);
      if ( _InterlockedExchangeAdd(&ActiveLdapConnObjects, 0xFFFFFFFF) == 1 )
        break;
      Sleep(0x1F4u);
      if ( (unsigned int)++v0 >= 0x14 )
      {
        if ( v0 == 20 )
          return;
        break;
      }
    }
    v1 = gcNumaProcessors;
    for ( i = 0; i < (unsigned int)gcNumaProcessors; ++i )
    {
      SpecificPLS = GetSpecificPLS(i);
      v4 = (struct _RTL_CRITICAL_SECTION *)(SpecificPLS + 280);
      EnterCriticalSection((LPCRITICAL_SECTION)(SpecificPLS + 280));
      v6 = (_QWORD **)(SpecificPLS + 328);
      while ( 1 )
      {
        v7 = *v6;
        if ( *v6 == v6 )
          break;
        if ( (_QWORD **)v7[1] != v6 || (v8 = (_QWORD *)*v7, *(_QWORD **)(*v7 + 8LL) != v7) )
LABEL_38:
          __fastfail(3u);
        *v6 = v8;
        v8[1] = v6;
        v9 = (LDAP_REQUEST *)(v7 - 11);
        if ( v9 )
          LDAP_REQUEST::`scalar deleting destructor'(v9, v5);
      }
      LeaveCriticalSection(v4);
      if ( *(_DWORD *)(SpecificPLS + 320) )
      {
        DeleteCriticalSection(v4);
        *(_DWORD *)(SpecificPLS + 320) = 0;
      }
      v1 = gcNumaProcessors;
    }
    v10 = 0;
    if ( v1 )
    {
      do
      {
        v11 = GetSpecificPLS(v10);
        v12 = (struct _RTL_CRITICAL_SECTION *)(v11 + 216);
        EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 216));
        v14 = (_QWORD **)(v11 + 264);
        while ( 1 )
        {
          v15 = *v14;
          if ( *v14 == v14 )
            break;
          if ( (_QWORD **)v15[1] != v14 )
            goto LABEL_38;
          v16 = (_QWORD *)*v15;
          if ( *(_QWORD **)(*v15 + 8LL) != v15 )
            goto LABEL_38;
          *v14 = v16;
          v16[1] = v14;
          v17 = (LDAP_CONN *)(v15 - 3);
          if ( v17 )
            LDAP_CONN::`scalar deleting destructor'(v17, v13);
        }
        LeaveCriticalSection(v12);
        if ( *(_DWORD *)(v11 + 256) )
        {
          DeleteCriticalSection(v12);
          *(_DWORD *)(v11 + 256) = 0;
        }
        ++v10;
      }
      while ( v10 < (unsigned int)gcNumaProcessors );
    }
    if ( LdapAttrCache )
    {
      DSFreeAux(LdapAttrCache, 201327292);
      LdapAttrCache = 0;
    }
    if ( PolicyNotifyBlock )
    {
      DirNotifyUnRegister(PolicyNotifyBlock, &v18);
      PolicyNotifyBlock = 0;
    }
    DestroyLimits();
    if ( LdapEndpointLock_initialized )
    {
      DeleteCriticalSection(&LdapEndpointLock);
      LdapEndpointLock_initialized = 0;
    }
    if ( LdapSendQueueRecoveryLock_initialized )
    {
      DeleteCriticalSection(&LdapSendQueueRecoveryLock);
      LdapSendQueueRecoveryLock_initialized = 0;
    }
    if ( gpLocalAddrs )
    {
      DSFreeAux(gpLocalAddrs, 201327307);
      gpLocalAddrs = 0;
      gcLocalAddrs = 0;
    }
    UninitializePageBlobCache();
  }
}

```

## disassembly

```asm
0x180316d58  mov     [rsp+arg_8], rbx
0x180316d5d  mov     [rsp+arg_10], rbp
0x180316d62  push    rsi
0x180316d63  push    rdi
0x180316d64  push    r14
0x180316d66  sub     rsp, 20h
0x180316d6a  xor     r14d, r14d
0x180316d6d  cmp     cs:?fLdapInitialized@@3HA, r14d; int fLdapInitialized
0x180316d74  jz      loc_180316F7A
0x180316d7a  mov     ebx, r14d
0x180316d7d  lock inc cs:?ActiveLdapConnObjects@@3JA; long ActiveLdapConnObjects
0x180316d84  or      eax, 0FFFFFFFFh
0x180316d87  lock xadd cs:?ActiveLdapConnObjects@@3JA, eax; long ActiveLdapConnObjects
0x180316d8f  cmp     eax, 1
0x180316d92  jz      short loc_180316DAC
0x180316d94  mov     ecx, 1F4h; dwMilliseconds
0x180316d99  call    cs:__imp_Sleep
0x180316d9f  inc     ebx
0x180316da1  cmp     ebx, 14h
0x180316da4  jb      short loc_180316D7D
0x180316da6  jz      loc_180316F7A
0x180316dac  mov     ecx, cs:gcNumaProcessors
0x180316db2  mov     rbx, r14
0x180316db5  test    ecx, ecx
0x180316db7  jz      loc_180316E46
0x180316dbd  mov     rcx, rbx
0x180316dc0  call    GetSpecificPLS
0x180316dc5  mov     rsi, rax
0x180316dc8  lea     rbp, [rax+118h]
0x180316dcf  mov     rcx, rbp; lpCriticalSection
0x180316dd2  call    cs:__imp_EnterCriticalSection
0x180316dd8  lea     rdi, [rsi+148h]
0x180316ddf  mov     rcx, [rdi]
0x180316de2  cmp     rcx, rdi
0x180316de5  jz      short loc_180316E12
0x180316de7  cmp     [rcx+8], rdi
0x180316deb  jnz     loc_180316F8D
0x180316df1  mov     rax, [rcx]
0x180316df4  cmp     [rax+8], rcx
0x180316df8  jnz     loc_180316F8D
0x180316dfe  mov     [rdi], rax
0x180316e01  mov     [rax+8], rdi
0x180316e05  add     rcx, 0FFFFFFFFFFFFFFA8h; this
0x180316e09  jz      short loc_180316DDF
0x180316e0b  call    ??_GLDAP_REQUEST@@QEAAPEAXI@Z; LDAP_REQUEST::`scalar deleting destructor'(uint)
0x180316e10  jmp     short loc_180316DDF
0x180316e12  mov     rcx, rbp; lpCriticalSection
0x180316e15  call    cs:__imp_LeaveCriticalSection
0x180316e1b  cmp     [rsi+140h], r14d
0x180316e22  jz      short loc_180316E34
0x180316e24  mov     rcx, rbp; lpCriticalSection
0x180316e27  call    cs:__imp_DeleteCriticalSection
0x180316e2d  mov     [rsi+140h], r14d
0x180316e34  mov     ecx, cs:gcNumaProcessors
0x180316e3a  inc     rbx
0x180316e3d  cmp     rbx, rcx
0x180316e40  jb      loc_180316DBD
0x180316e46  mov     rbx, r14
0x180316e49  test    ecx, ecx
0x180316e4b  jz      loc_180316EDA
0x180316e51  mov     rcx, rbx
0x180316e54  call    GetSpecificPLS
0x180316e59  mov     rsi, rax
0x180316e5c  lea     rbp, [rax+0D8h]
0x180316e63  mov     rcx, rbp; lpCriticalSection
0x180316e66  call    cs:__imp_EnterCriticalSection
0x180316e6c  lea     rdi, [rsi+108h]
0x180316e73  mov     rcx, [rdi]
0x180316e76  cmp     rcx, rdi
0x180316e79  jz      short loc_180316EA6
0x180316e7b  cmp     [rcx+8], rdi
0x180316e7f  jnz     loc_180316F8D
0x180316e85  mov     rax, [rcx]
0x180316e88  cmp     [rax+8], rcx
0x180316e8c  jnz     loc_180316F8D
0x180316e92  mov     [rdi], rax
0x180316e95  mov     [rax+8], rdi
0x180316e99  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180316e9d  jz      short loc_180316E73
0x180316e9f  call    ??_GLDAP_CONN@@QEAAPEAXI@Z; LDAP_CONN::`scalar deleting destructor'(uint)
0x180316ea4  jmp     short loc_180316E73
0x180316ea6  mov     rcx, rbp; lpCriticalSection
0x180316ea9  call    cs:__imp_LeaveCriticalSection
0x180316eaf  cmp     [rsi+100h], r14d
0x180316eb6  jz      short loc_180316EC8
0x180316eb8  mov     rcx, rbp; lpCriticalSection
0x180316ebb  call    cs:__imp_DeleteCriticalSection
0x180316ec1  mov     [rsi+100h], r14d
0x180316ec8  mov     eax, cs:gcNumaProcessors
0x180316ece  inc     rbx
0x180316ed1  cmp     rbx, rax
0x180316ed4  jb      loc_180316E51
0x180316eda  mov     rcx, cs:?LdapAttrCache@@3PEAUAttributeVals_@@EA; AttributeVals_ * LdapAttrCache
0x180316ee1  test    rcx, rcx
0x180316ee4  jz      short loc_180316EF7
0x180316ee6  mov     edx, 0C0002BCh
0x180316eeb  call    DSFreeAux
0x180316ef0  mov     cs:?LdapAttrCache@@3PEAUAttributeVals_@@EA, r14; AttributeVals_ * LdapAttrCache
0x180316ef7  mov     ecx, cs:?PolicyNotifyBlock@@3U_POLICY_NOTIFICATION_BLOCK@@A; _POLICY_NOTIFICATION_BLOCK PolicyNotifyBlock
0x180316efd  test    ecx, ecx
0x180316eff  jz      short loc_180316F12
0x180316f01  lea     rdx, [rsp+38h+arg_0]
0x180316f06  call    DirNotifyUnRegister
0x180316f0b  mov     cs:?PolicyNotifyBlock@@3U_POLICY_NOTIFICATION_BLOCK@@A, r14d; _POLICY_NOTIFICATION_BLOCK PolicyNotifyBlock
0x180316f12  call    ?DestroyLimits@@YAXXZ; DestroyLimits(void)
0x180316f17  cmp     cs:LdapEndpointLock_initialized, r14d
0x180316f1e  jz      short loc_180316F34
0x180316f20  lea     rcx, LdapEndpointLock; lpCriticalSection
0x180316f27  call    cs:__imp_DeleteCriticalSection
0x180316f2d  mov     cs:LdapEndpointLock_initialized, r14d
0x180316f34  cmp     cs:LdapSendQueueRecoveryLock_initialized, r14d
0x180316f3b  jz      short loc_180316F51
0x180316f3d  lea     rcx, LdapSendQueueRecoveryLock; lpCriticalSection
0x180316f44  call    cs:__imp_DeleteCriticalSection
0x180316f4a  mov     cs:LdapSendQueueRecoveryLock_initialized, r14d
0x180316f51  mov     rcx, cs:gpLocalAddrs
0x180316f58  test    rcx, rcx
0x180316f5b  jz      short loc_180316F75
0x180316f5d  mov     edx, 0C0002CBh
0x180316f62  call    DSFreeAux
0x180316f67  mov     cs:gpLocalAddrs, r14
0x180316f6e  mov     cs:gcLocalAddrs, r14d
0x180316f75  call    ?UninitializePageBlobCache@@YAXXZ; UninitializePageBlobCache(void)
0x180316f7a  mov     rbx, [rsp+38h+arg_8]
0x180316f7f  mov     rbp, [rsp+38h+arg_10]
0x180316f84  add     rsp, 20h
0x180316f88  pop     r14
0x180316f8a  pop     rdi
0x180316f8b  pop     rsi
0x180316f8c  retn
0x180316f8d  mov     ecx, 3
0x180316f92  int     29h; Win8: RtlFailFast(ecx)
```
