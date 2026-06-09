# GlobalCleanup(bool)

- ea: `0x18004a05c`
- end: `0x18004a20f`
- name: `?GlobalCleanup@@YAX_N@Z`
- size: `435`
- prototype: `void __fastcall(char)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18004b1e0`
- `0x18004b8a0`

## callees

- `0x1800293c0`
- `0x18004a05c`
- `0x18004b8b8`
- `0x18004cf6c`
- `0x180066d14`
- `0x180066fbc`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a1b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a1ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a1b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a1ca`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004a121`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004a121`
- `ntdll!RtlReleaseResource` at `0x18004a133`
- `ntdll!RtlReleaseResource` at `0x18004a133`
- `ntdll!RtlDeleteResource` at `0x18004a0b3`
- `ntdll!RtlDeleteResource` at `0x18004a0ce`
- `ntdll!RtlDeleteResource` at `0x18004a0e9`
- `ntdll!RtlDeleteResource` at `0x18004a104`
- `ntdll!RtlDeleteResource` at `0x18004a140`
- `ntdll!RtlDeleteResource` at `0x18004a15b`
- `ntdll!RtlDeleteResource` at `0x18004a176`
- `ntdll!RtlDeleteResource` at `0x18004a0b3`
- `ntdll!RtlDeleteResource` at `0x18004a0ce`
- `ntdll!RtlDeleteResource` at `0x18004a0e9`
- `ntdll!RtlDeleteResource` at `0x18004a104`
- `ntdll!RtlDeleteResource` at `0x18004a140`
- `ntdll!RtlDeleteResource` at `0x18004a15b`
- `ntdll!RtlDeleteResource` at `0x18004a176`
- `LSASRV!LsarClose` at `0x18004a1e7`
- `LSASRV!LsarClose` at `0x18004a1e7`

## pseudocode

```c
void __fastcall GlobalCleanup(char a1)
{
  unsigned __int8 *v1; // rcx
  __int64 v2; // rax

  if ( !a1 )
  {
    UninitializeCrypto();
    KerbUnloadECDHAlgorithmProviders();
    v1 = g_pNullPwdCredHash;
    if ( g_pNullPwdCredHash )
    {
      v2 = g_cbNullPwdCredHash;
      if ( g_cbNullPwdCredHash )
      {
        do
        {
          *v1++ = 0;
          --v2;
        }
        while ( v2 );
        v1 = g_pNullPwdCredHash;
      }
      FreeMemory(v1);
    }
    if ( g_bLogonSessionListLockInitialized )
    {
      RtlDeleteResource(&g_LogonSessionListLock);
      g_bLogonSessionListLockInitialized = 0;
    }
    if ( g_bUserCacheListLockInitialized )
    {
      RtlDeleteResource(&g_UserCacheListLock);
      g_bUserCacheListLockInitialized = 0;
    }
    if ( g_bStaleUserCacheListLockInitialized )
    {
      RtlDeleteResource(&g_StaleUserCacheListLock);
      g_bStaleUserCacheListLockInitialized = 0;
    }
    if ( g_bUserLockList_LockInitialized )
    {
      RtlDeleteResource(&g_UserLockList_Lock);
      g_bUserLockList_LockInitialized = 0;
    }
    if ( g_bPackageListLockInitialized )
    {
      RtlAcquireResourceExclusive(&g_PackageListLock, 1u);
      UninitializePlugins();
      RtlReleaseResource(&g_PackageListLock);
      RtlDeleteResource(&g_PackageListLock);
      g_bPackageListLockInitialized = 0;
    }
    if ( g_bLookupsCacheLockInitialized )
    {
      RtlDeleteResource(&g_LookupsCacheLock);
      g_bLookupsCacheLockInitialized = 0;
    }
    if ( g_bAadConnectMapLockInitialized )
    {
      RtlDeleteResource(&g_AadConnectMapLock);
      g_bAadConnectMapLockInitialized = 0;
    }
    if ( g_pwszCacheRootDirectory )
    {
      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
      g_pwszCacheRootDirectory = 0;
    }
    if ( g_pSystemSD )
    {
      LocalFree(g_pSystemSD);
      g_pSystemSD = 0;
    }
    if ( g_pSystemOnlySD )
    {
      LocalFree(g_pSystemOnlySD);
      g_pSystemSD = 0;
    }
    if ( g_LsaPolicyHandle )
    {
      LsarClose(&g_LsaPolicyHandle);
      g_LsaPolicyHandle = 0;
    }
    if ( byte_18009AC00 )
    {
      KerberosCryptoPolicy::UninitializeCiphers();
      byte_18009AC00 = 0;
    }
  }
}

```

## disassembly

```asm
0x18004a05c  test    cl, cl
0x18004a05e  jnz     locret_18004A20E
0x18004a064  push    rdi
0x18004a065  sub     rsp, 20h
0x18004a069  xor     edi, edi
0x18004a06b  call    ?UninitializeCrypto@@YAXXZ; UninitializeCrypto(void)
0x18004a070  call    ?KerbUnloadECDHAlgorithmProviders@@YAXXZ; KerbUnloadECDHAlgorithmProviders(void)
0x18004a075  mov     rcx, cs:?g_pNullPwdCredHash@@3PEAEEA; uchar * g_pNullPwdCredHash
0x18004a07c  test    rcx, rcx
0x18004a07f  jz      short loc_18004A0A4
0x18004a081  mov     eax, cs:?g_cbNullPwdCredHash@@3KA; ulong g_cbNullPwdCredHash
0x18004a087  test    rax, rax
0x18004a08a  jz      short loc_18004A09F
0x18004a08c  mov     [rcx], dil
0x18004a08f  inc     rcx
0x18004a092  sub     rax, 1
0x18004a096  jnz     short loc_18004A08C
0x18004a098  mov     rcx, cs:?g_pNullPwdCredHash@@3PEAEEA; void *
0x18004a09f  call    ?FreeMemory@@YAXPEAX@Z; FreeMemory(void *)
0x18004a0a4  cmp     cs:?g_bLogonSessionListLockInitialized@@3HA, edi; int g_bLogonSessionListLockInitialized
0x18004a0aa  jz      short loc_18004A0BF
0x18004a0ac  lea     rcx, ?g_LogonSessionListLock@@3U_RTL_RESOURCE@@A; Resource
0x18004a0b3  call    cs:__imp_RtlDeleteResource
0x18004a0b9  mov     cs:?g_bLogonSessionListLockInitialized@@3HA, edi; int g_bLogonSessionListLockInitialized
0x18004a0bf  cmp     cs:?g_bUserCacheListLockInitialized@@3HA, edi; int g_bUserCacheListLockInitialized
0x18004a0c5  jz      short loc_18004A0DA
0x18004a0c7  lea     rcx, ?g_UserCacheListLock@@3U_RTL_RESOURCE@@A; Resource
0x18004a0ce  call    cs:__imp_RtlDeleteResource
0x18004a0d4  mov     cs:?g_bUserCacheListLockInitialized@@3HA, edi; int g_bUserCacheListLockInitialized
0x18004a0da  cmp     cs:?g_bStaleUserCacheListLockInitialized@@3HA, edi; int g_bStaleUserCacheListLockInitialized
0x18004a0e0  jz      short loc_18004A0F5
0x18004a0e2  lea     rcx, ?g_StaleUserCacheListLock@@3U_RTL_RESOURCE@@A; Resource
0x18004a0e9  call    cs:__imp_RtlDeleteResource
0x18004a0ef  mov     cs:?g_bStaleUserCacheListLockInitialized@@3HA, edi; int g_bStaleUserCacheListLockInitialized
0x18004a0f5  cmp     cs:?g_bUserLockList_LockInitialized@@3HA, edi; int g_bUserLockList_LockInitialized
0x18004a0fb  jz      short loc_18004A110
0x18004a0fd  lea     rcx, ?g_UserLockList_Lock@@3U_RTL_RESOURCE@@A; Resource
0x18004a104  call    cs:__imp_RtlDeleteResource
0x18004a10a  mov     cs:?g_bUserLockList_LockInitialized@@3HA, edi; int g_bUserLockList_LockInitialized
0x18004a110  cmp     cs:?g_bPackageListLockInitialized@@3HA, edi; int g_bPackageListLockInitialized
0x18004a116  jz      short loc_18004A14C
0x18004a118  mov     dl, 1; Wait
0x18004a11a  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x18004a121  call    cs:__imp_RtlAcquireResourceExclusive
0x18004a127  call    ?UninitializePlugins@@YAXXZ; UninitializePlugins(void)
0x18004a12c  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x18004a133  call    cs:__imp_RtlReleaseResource
0x18004a139  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x18004a140  call    cs:__imp_RtlDeleteResource
0x18004a146  mov     cs:?g_bPackageListLockInitialized@@3HA, edi; int g_bPackageListLockInitialized
0x18004a14c  cmp     cs:?g_bLookupsCacheLockInitialized@@3HA, edi; int g_bLookupsCacheLockInitialized
0x18004a152  jz      short loc_18004A167
0x18004a154  lea     rcx, ?g_LookupsCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x18004a15b  call    cs:__imp_RtlDeleteResource
0x18004a161  mov     cs:?g_bLookupsCacheLockInitialized@@3HA, edi; int g_bLookupsCacheLockInitialized
0x18004a167  cmp     cs:?g_bAadConnectMapLockInitialized@@3HA, edi; int g_bAadConnectMapLockInitialized
0x18004a16d  jz      short loc_18004A182
0x18004a16f  lea     rcx, ?g_AadConnectMapLock@@3U_RTL_RESOURCE@@A; Resource
0x18004a176  call    cs:__imp_RtlDeleteResource
0x18004a17c  mov     cs:?g_bAadConnectMapLockInitialized@@3HA, edi; int g_bAadConnectMapLockInitialized
0x18004a182  mov     rcx, cs:?g_pwszCacheRootDirectory@@3PEAGEA; ushort * g_pwszCacheRootDirectory
0x18004a189  test    rcx, rcx
0x18004a18c  jz      short loc_18004A1A5
0x18004a18e  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18004a195  mov     rax, [rax+30h]
0x18004a199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a19e  mov     cs:?g_pwszCacheRootDirectory@@3PEAGEA, rdi; ushort * g_pwszCacheRootDirectory
0x18004a1a5  mov     rcx, cs:?g_pSystemSD@@3PEAXEA; hMem
0x18004a1ac  test    rcx, rcx
0x18004a1af  jz      short loc_18004A1BE
0x18004a1b1  call    cs:__imp_LocalFree
0x18004a1b7  mov     cs:?g_pSystemSD@@3PEAXEA, rdi; void * g_pSystemSD
0x18004a1be  mov     rcx, cs:?g_pSystemOnlySD@@3PEAXEA; hMem
0x18004a1c5  test    rcx, rcx
0x18004a1c8  jz      short loc_18004A1D7
0x18004a1ca  call    cs:__imp_LocalFree
0x18004a1d0  mov     cs:?g_pSystemSD@@3PEAXEA, rdi; void * g_pSystemSD
0x18004a1d7  cmp     cs:?g_LsaPolicyHandle@@3PEAXEA, rdi; void * g_LsaPolicyHandle
0x18004a1de  jz      short loc_18004A1F4
0x18004a1e0  lea     rcx, ?g_LsaPolicyHandle@@3PEAXEA; void * g_LsaPolicyHandle
0x18004a1e7  call    cs:__imp_LsarClose
0x18004a1ed  mov     cs:?g_LsaPolicyHandle@@3PEAXEA, rdi; void * g_LsaPolicyHandle
0x18004a1f4  cmp     cs:byte_18009AC00, dil
0x18004a1fb  jz      short loc_18004A209
0x18004a1fd  call    ?UninitializeCiphers@KerberosCryptoPolicy@@SAXW4Kerb3961PolicyType@@@Z; KerberosCryptoPolicy::UninitializeCiphers(Kerb3961PolicyType)
0x18004a202  mov     cs:byte_18009AC00, dil
0x18004a209  add     rsp, 20h
0x18004a20d  pop     rdi
0x18004a20e  retn
```
