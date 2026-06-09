# CiInitializePhase2

- ea: `0x1800e4ca8`
- end: `0x1800e5110`
- name: `CiInitializePhase2`
- size: `1128`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800e5a50`

## callees

- `0x18001e64c`
- `0x18005b89c`
- `0x180061398`
- `0x180063e9c`
- `0x18006653c`
- `0x18006c2fc`
- `0x18006d460`
- `0x18006d56c`
- `0x18006e55c`
- `0x180072d54`
- `0x180077c44`
- `0x180078008`
- `0x18007fe74`
- `0x18009f2fc`
- `0x1800a0258`
- `0x1800cb930`
- `0x1800e45d8`
- `0x1800e4ca8`
- `0x1800f803c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800e4cd3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800e4e27`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800e4f42`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800e4cd3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800e4e27`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800e4f42`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800e4ce8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800e4e3c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800e4ce8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800e4e3c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800e4e5a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800e50e7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800e4e5a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800e50e7`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1800e50bd`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1800e50bd`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1800e4f57`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1800e4f57`
- `ntoskrnl!EtwRegister` at `0x1800e4d1d`
- `ntoskrnl!EtwRegister` at `0x1800e4d1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e5065`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e5065`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800e4e66`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800e50c9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800e50f3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800e4e66`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800e50c9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800e50f3`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1800e4ef6`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1800e4f25`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1800e4ef6`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1800e4f25`
- `ntoskrnl!ExInitializeResourceLite` at `0x1800e4e96`
- `ntoskrnl!ExInitializeResourceLite` at `0x1800e4e96`
- `ntoskrnl!RtlCheckRegistryKey` at `0x1800e4eb0`
- `ntoskrnl!RtlCheckRegistryKey` at `0x1800e4eb0`

## pseudocode

```c
void CiInitializePhase2()
{
  __int64 v0; // r9
  __int64 v1; // r8
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int16 v4; // cx
  int v5; // ebx
  int v6; // r9d
  PVOID **v7; // rdi
  int v8; // eax
  const EVENT_DESCRIPTOR *v9; // rax
  int v10; // edx
  char v11; // cl
  __int64 *v12; // rdx
  PVOID *v13; // rax
  PVOID *v14; // rcx
  __int64 v15; // rdx
  __int64 i; // rbx
  ULONGLONG RegHandle; // [rsp+50h] [rbp+8h] BYREF

  RegHandle = 0;
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_EtwEventHandle, 0, 0) )
    return;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(&g_CiInitLock, 0);
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_EtwEventHandle, 0, 0) )
    goto LABEL_41;
  wil_InitializeFeatureStaging();
  if ( EtwRegister(&CodeIntegrityEventProviderId, 0, 0, &RegHandle) < 0 )
    goto LABEL_40;
  TlgRegisterAggregateProviderEx(&dword_180049000);
  TlgRegisterAggregateProviderEx(&dword_180049080);
  TlgRegisterAggregateProviderEx(&dword_1800491D8);
  TlgRegisterAggregateProviderEx(&qword_180049040);
  TlgRegisterAggregateProviderEx(&qword_180049168);
  TlgRegisterAggregateProviderEx(&dword_180049128);
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_1800490B8);
  TlgRegisterAggregateProviderEx(&dword_1800491A0);
  TlgRegisterAggregateProviderEx(&qword_1800490F0);
  v0 = (unsigned int)g_CiDeveloperMode >> 8;
  v1 = (unsigned int)g_CiDeveloperMode >> 12;
  v2 = (unsigned int)g_CiDeveloperMode >> 9;
  LOBYTE(v0) = BYTE1(g_CiDeveloperMode) & 1;
  v3 = (unsigned int)g_CiDeveloperMode >> 6;
  LOBYTE(v1) = (g_CiDeveloperMode & 0x1000) != 0;
  LOBYTE(v2) = (g_CiDeveloperMode & 0x200) != 0;
  LOBYTE(v3) = (g_CiDeveloperMode & 0x40) != 0;
  if ( (int)MinCrypK_Initialize(v3, v2, v1, v0) < 0
    || (int)CiInitializeParallelHashingContexts() < 0
    || (int)CiInitializeCatalogs() < 0 )
  {
    goto LABEL_40;
  }
  v4 = g_CiDeveloperMode;
  if ( (g_CiDeveloperMode & 0x20) == 0 )
    MinCryptRevokePrereleaseWindowsPCA();
  if ( (v4 & 0x800) == 0 )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(&g_CipPolicyLock, 0);
    v5 = CipLoadAndValidateRevocationList(0);
    ExReleasePushLockExclusiveEx(&g_CipPolicyLock, 0);
    KeLeaveCriticalRegion();
    if ( v5 < 0 )
LABEL_40:
      __fastfail(0x14u);
  }
  qword_1800497F0 = (__int64)&qword_1800497E8;
  qword_1800497E8 = &qword_1800497E8;
  ExInitializeResourceLite(&Resource);
  PESetInitialState();
  if ( RtlCheckRegistryKey(2u, (PWSTR)L"MiniNT") >= 0 )
    g_CiIsWinPE = 1;
  g_TrimBootCacheCatalogEntries = 1;
  ExInitializePagedLookasideList(&g_CiValidationLookasideList, 0, 0, 0, 0xE20u, 0x63734943u, 0);
  ExInitializePagedLookasideList(&g_CiEaCacheLookasideList, 0, 0, 0, 0x298u, 0x63734943u, 0);
  SIPolicyInitializeWellKnownSidBuffer();
  _InterlockedExchange64((volatile __int64 *)&g_EtwEventHandle, RegHandle);
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(&g_CipPolicyLock, 0);
  while ( 1 )
  {
    v7 = (PVOID **)g_BootDriverList;
    if ( g_BootDriverList == &g_BootDriverList )
      break;
    v8 = *((_DWORD *)g_BootDriverList + 8);
    if ( v8 == -1073740760 )
    {
      v9 = &CiImageFileHashNotFound;
LABEL_19:
      LOBYTE(v6) = 1;
      CiLogFileRequestedValidationEventWithProcessName((_DWORD)g_BootDriverList + 16, (int)&qword_1800303F0, 1, v6, v9);
      CiAudit(v7 + 2, 5038);
      goto LABEL_23;
    }
    if ( v8 == -1073740285 )
    {
      v9 = (const EVENT_DESCRIPTOR *)CiRevokedDriverNotLoaded;
      goto LABEL_19;
    }
    if ( v8 >= 0 && (*((_DWORD *)g_BootDriverList + 9) & 1) != 0 )
      CiLogFileEvent((char *)g_BootDriverList + 16, CiNoEmbeddedSignatureDriverLoaded);
LABEL_23:
    v10 = *((_DWORD *)v7 + 9);
    if ( (v10 & 0x20) != 0 )
    {
      v11 = 2;
      if ( *((int *)v7 + 8) < 0 )
        v11 = *((_DWORD *)v7 + 8);
      CiLogSIPolicyEvent2((_DWORD)v7 + 16, v11, (*((_DWORD *)v7 + 9) & 0x4000) != 0);
      if ( (*((_DWORD *)v7 + 9) & 0x4000) != 0 )
        CiInstrumentVbsPolicyBootFailure(v7 + 2);
    }
    else
    {
      if ( (v10 & 0x100) != 0 )
      {
        v12 = WhqlEnforcementFailureAudit;
LABEL_32:
        CiLogFileEvent(v7 + 2, v12);
        goto LABEL_33;
      }
      if ( (v10 & 0x200) != 0 )
      {
        v12 = WhqlEnforcementFailureExempted;
        goto LABEL_32;
      }
    }
LABEL_33:
    v13 = *v7;
    if ( (*v7)[1] != v7 || (v14 = v7[1], *v14 != v7) )
      __fastfail(3u);
    *v14 = v13;
    v13[1] = v14;
    ExFreePoolWithTag(v7, 0);
  }
  CiLogWhqlSettingsEvent();
  for ( i = 0; (unsigned int)i < g_NumberOfSiPolicies; i = (unsigned int)(i + 1) )
    CiLogSIPolicyRefresh(*((_QWORD *)g_SiPolicyHandles + i), v15, CiPolicyRefreshActivatePolicySucceded);
  CiInstrumentInitialize(0);
  ExReleasePushLockSharedEx(&g_CipPolicyLock, 0);
  KeLeaveCriticalRegion();
LABEL_41:
  ExReleasePushLockExclusiveEx(&g_CiInitLock, 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x1800e4ca8  mov     [rsp+arg_8], rbx
0x1800e4cad  mov     [rsp+arg_10], rsi
0x1800e4cb2  push    rdi
0x1800e4cb3  sub     rsp, 40h
0x1800e4cb7  xor     ecx, ecx
0x1800e4cb9  mov     [rsp+48h+RegHandle], 0
0x1800e4cc2  xor     eax, eax
0x1800e4cc4  lock cmpxchg cs:g_EtwEventHandle, rcx
0x1800e4ccd  jnz     loc_1800E50FF
0x1800e4cd3  call    cs:__imp_KeEnterCriticalRegion
0x1800e4cda  nop     dword ptr [rax+rax+00h]
0x1800e4cdf  xor     edx, edx
0x1800e4ce1  lea     rcx, g_CiInitLock
0x1800e4ce8  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1800e4cef  nop     dword ptr [rax+rax+00h]
0x1800e4cf4  xor     ecx, ecx
0x1800e4cf6  xor     eax, eax
0x1800e4cf8  lock cmpxchg cs:g_EtwEventHandle, rcx
0x1800e4d01  jnz     loc_1800E50DE
0x1800e4d07  call    wil_InitializeFeatureStaging
0x1800e4d0c  lea     r9, [rsp+48h+RegHandle]; RegHandle
0x1800e4d11  xor     r8d, r8d; CallbackContext
0x1800e4d14  xor     edx, edx; EnableCallback
0x1800e4d16  lea     rcx, CodeIntegrityEventProviderId; ProviderId
0x1800e4d1d  call    cs:__imp_EtwRegister
0x1800e4d24  nop     dword ptr [rax+rax+00h]
0x1800e4d29  test    eax, eax
0x1800e4d2b  js      loc_1800E50D7
0x1800e4d31  mov     esi, 1
0x1800e4d36  lea     rcx, dword_180049000; CallbackContext
0x1800e4d3d  mov     r9d, esi
0x1800e4d40  call    TlgRegisterAggregateProviderEx
0x1800e4d45  lea     edi, [rsi+1]
0x1800e4d48  mov     r9d, edi
0x1800e4d4b  lea     rcx, dword_180049080; CallbackContext
0x1800e4d52  call    TlgRegisterAggregateProviderEx
0x1800e4d57  mov     r9d, edi
0x1800e4d5a  lea     rcx, dword_1800491D8; CallbackContext
0x1800e4d61  call    TlgRegisterAggregateProviderEx
0x1800e4d66  mov     r9d, edi
0x1800e4d69  lea     rcx, qword_180049040; CallbackContext
0x1800e4d70  call    TlgRegisterAggregateProviderEx
0x1800e4d75  mov     r9d, edi
0x1800e4d78  lea     rcx, qword_180049168; CallbackContext
0x1800e4d7f  call    TlgRegisterAggregateProviderEx
0x1800e4d84  mov     r9d, edi
0x1800e4d87  lea     rcx, dword_180049128; CallbackContext
0x1800e4d8e  call    TlgRegisterAggregateProviderEx
0x1800e4d93  xor     r8d, r8d
0x1800e4d96  lea     rcx, dword_1800490B8; CallbackContext
0x1800e4d9d  xor     edx, edx
0x1800e4d9f  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x1800e4da4  mov     r9d, edi
0x1800e4da7  lea     rcx, dword_1800491A0; CallbackContext
0x1800e4dae  call    TlgRegisterAggregateProviderEx
0x1800e4db3  mov     r9d, edi
0x1800e4db6  lea     rcx, qword_1800490F0; CallbackContext
0x1800e4dbd  call    TlgRegisterAggregateProviderEx
0x1800e4dc2  mov     ecx, cs:g_CiDeveloperMode
0x1800e4dc8  mov     r9d, ecx
0x1800e4dcb  mov     r8d, ecx
0x1800e4dce  shr     r9d, 8
0x1800e4dd2  mov     edx, ecx
0x1800e4dd4  shr     r8d, 0Ch
0x1800e4dd8  shr     edx, 9
0x1800e4ddb  and     r9b, sil
0x1800e4dde  shr     ecx, 6
0x1800e4de1  and     r8b, sil
0x1800e4de4  and     dl, sil
0x1800e4de7  and     cl, sil
0x1800e4dea  call    MinCrypK_Initialize
0x1800e4def  test    eax, eax
0x1800e4df1  js      loc_1800E50D7
0x1800e4df7  call    CiInitializeParallelHashingContexts
0x1800e4dfc  test    eax, eax
0x1800e4dfe  js      loc_1800E50D7
0x1800e4e04  call    CiInitializeCatalogs
0x1800e4e09  test    eax, eax
0x1800e4e0b  js      loc_1800E50D7
0x1800e4e11  mov     ecx, cs:g_CiDeveloperMode
0x1800e4e17  test    cl, 20h
0x1800e4e1a  jnz     short loc_1800E4E21
0x1800e4e1c  call    MinCryptRevokePrereleaseWindowsPCA
0x1800e4e21  bt      ecx, 0Bh
0x1800e4e25  jb      short loc_1800E4E7A
0x1800e4e27  call    cs:__imp_KeEnterCriticalRegion
0x1800e4e2e  nop     dword ptr [rax+rax+00h]
0x1800e4e33  xor     edx, edx
0x1800e4e35  lea     rcx, g_CipPolicyLock
0x1800e4e3c  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1800e4e43  nop     dword ptr [rax+rax+00h]
0x1800e4e48  xor     ecx, ecx
0x1800e4e4a  call    CipLoadAndValidateRevocationList
0x1800e4e4f  xor     edx, edx
0x1800e4e51  lea     rcx, g_CipPolicyLock
0x1800e4e58  mov     ebx, eax
0x1800e4e5a  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1800e4e61  nop     dword ptr [rax+rax+00h]
0x1800e4e66  call    cs:__imp_KeLeaveCriticalRegion
0x1800e4e6d  nop     dword ptr [rax+rax+00h]
0x1800e4e72  test    ebx, ebx
0x1800e4e74  js      loc_1800E50D7
0x1800e4e7a  lea     rax, qword_1800497E8
0x1800e4e81  lea     rcx, Resource; Resource
0x1800e4e88  mov     cs:qword_1800497F0, rax
0x1800e4e8f  mov     cs:qword_1800497E8, rax
0x1800e4e96  call    cs:__imp_ExInitializeResourceLite
0x1800e4e9d  nop     dword ptr [rax+rax+00h]
0x1800e4ea2  call    PESetInitialState
0x1800e4ea7  lea     rdx, aMinint; "MiniNT"
0x1800e4eae  mov     ecx, edi; RelativeTo
0x1800e4eb0  call    cs:__imp_RtlCheckRegistryKey
0x1800e4eb7  nop     dword ptr [rax+rax+00h]
0x1800e4ebc  test    eax, eax
0x1800e4ebe  js      short loc_1800E4EC7
0x1800e4ec0  mov     cs:g_CiIsWinPE, sil
0x1800e4ec7  xor     eax, eax
0x1800e4ec9  mov     cs:g_TrimBootCacheCatalogEntries, sil
0x1800e4ed0  mov     [rsp+48h+Depth], ax; Depth
0x1800e4ed5  lea     rcx, g_CiValidationLookasideList; Lookaside
0x1800e4edc  mov     ebx, 63734943h
0x1800e4ee1  xor     r9d, r9d; Flags
0x1800e4ee4  mov     [rsp+48h+Tag], ebx; Tag
0x1800e4ee8  xor     r8d, r8d; Free
0x1800e4eeb  xor     edx, edx; Allocate
0x1800e4eed  mov     [rsp+48h+Size], 0E20h; Size
0x1800e4ef6  call    cs:__imp_ExInitializePagedLookasideList
0x1800e4efd  nop     dword ptr [rax+rax+00h]
0x1800e4f02  xor     eax, eax
0x1800e4f04  lea     rcx, g_CiEaCacheLookasideList; Lookaside
0x1800e4f0b  mov     [rsp+48h+Depth], ax; Depth
0x1800e4f10  xor     r9d, r9d; Flags
0x1800e4f13  mov     [rsp+48h+Tag], ebx; Tag
0x1800e4f17  xor     r8d, r8d; Free
0x1800e4f1a  xor     edx, edx; Allocate
0x1800e4f1c  mov     [rsp+48h+Size], 298h; Size
0x1800e4f25  call    cs:__imp_ExInitializePagedLookasideList
0x1800e4f2c  nop     dword ptr [rax+rax+00h]
0x1800e4f31  call    SIPolicyInitializeWellKnownSidBuffer
0x1800e4f36  mov     rax, [rsp+48h+RegHandle]
0x1800e4f3b  xchg    rax, cs:g_EtwEventHandle
0x1800e4f42  call    cs:__imp_KeEnterCriticalRegion
0x1800e4f49  nop     dword ptr [rax+rax+00h]
0x1800e4f4e  xor     edx, edx
0x1800e4f50  lea     rcx, g_CipPolicyLock
0x1800e4f57  call    cs:__imp_ExAcquirePushLockSharedEx
0x1800e4f5e  nop     dword ptr [rax+rax+00h]
0x1800e4f63  mov     rdi, cs:g_BootDriverList
0x1800e4f6a  lea     rax, g_BootDriverList
0x1800e4f71  cmp     rdi, rax
0x1800e4f74  jz      loc_1800E507D
0x1800e4f7a  mov     eax, [rdi+20h]
0x1800e4f7d  cmp     eax, 0C0000428h
0x1800e4f82  jnz     short loc_1800E4F8D
0x1800e4f84  lea     rax, CiImageFileHashNotFound
0x1800e4f8b  jmp     short loc_1800E4F9B
0x1800e4f8d  cmp     eax, 0C0000603h
0x1800e4f92  jnz     short loc_1800E4FC6
0x1800e4f94  lea     rax, CiRevokedDriverNotLoaded
0x1800e4f9b  mov     r9b, sil; int
0x1800e4f9e  mov     [rsp+48h+Size], rax; EventDescriptor
0x1800e4fa3  mov     r8d, esi; int
0x1800e4fa6  lea     rdx, qword_1800303F0; int
0x1800e4fad  lea     rcx, [rdi+10h]; int
0x1800e4fb1  call    CiLogFileRequestedValidationEventWithProcessName
0x1800e4fb6  mov     edx, 13AEh
0x1800e4fbb  lea     rcx, [rdi+10h]
0x1800e4fbf  call    CiAudit
0x1800e4fc4  jmp     short loc_1800E4FE2
0x1800e4fc6  test    eax, eax
0x1800e4fc8  js      short loc_1800E4FE2
0x1800e4fca  mov     eax, [rdi+24h]
0x1800e4fcd  test    sil, al
0x1800e4fd0  jz      short loc_1800E4FE2
0x1800e4fd2  lea     rcx, [rdi+10h]
0x1800e4fd6  lea     rdx, CiNoEmbeddedSignatureDriverLoaded
0x1800e4fdd  call    CiLogFileEvent
0x1800e4fe2  mov     edx, [rdi+24h]
0x1800e4fe5  test    dl, 20h
0x1800e4fe8  jz      short loc_1800E5022
0x1800e4fea  mov     eax, [rdi+20h]
0x1800e4fed  mov     ecx, 0C0E90002h
0x1800e4ff2  shr     edx, 0Eh
0x1800e4ff5  and     dl, sil
0x1800e4ff8  test    eax, eax
0x1800e4ffa  mov     byte ptr [rsp+48h+Tag], dl; char
0x1800e4ffe  cmovs   ecx, eax
0x1800e5001  mov     dword ptr [rsp+48h+Size], ecx; char
0x1800e5005  lea     rcx, [rdi+10h]; int
0x1800e5009  call    CiLogSIPolicyEvent2
0x1800e500e  test    dword ptr [rdi+24h], 4000h
0x1800e5015  jz      short loc_1800E5047
0x1800e5017  lea     rcx, [rdi+10h]
0x1800e501b  call    CiInstrumentVbsPolicyBootFailure
0x1800e5020  jmp     short loc_1800E5047
0x1800e5022  bt      edx, 8
0x1800e5026  jnb     short loc_1800E5031
0x1800e5028  lea     rdx, WhqlEnforcementFailureAudit
0x1800e502f  jmp     short loc_1800E503E
0x1800e5031  bt      edx, 9
0x1800e5035  jnb     short loc_1800E5047
0x1800e5037  lea     rdx, WhqlEnforcementFailureExempted
0x1800e503e  lea     rcx, [rdi+10h]
0x1800e5042  call    CiLogFileEvent
0x1800e5047  mov     rax, [rdi]
0x1800e504a  cmp     [rax+8], rdi
0x1800e504e  jnz     short loc_1800E5076
0x1800e5050  mov     rcx, [rdi+8]
0x1800e5054  cmp     [rcx], rdi
0x1800e5057  jnz     short loc_1800E5076
0x1800e5059  mov     [rcx], rax
0x1800e505c  xor     edx, edx; Tag
0x1800e505e  mov     [rax+8], rcx
0x1800e5062  mov     rcx, rdi; P
0x1800e5065  call    cs:__imp_ExFreePoolWithTag
0x1800e506c  nop     dword ptr [rax+rax+00h]
0x1800e5071  jmp     loc_1800E4F63
0x1800e5076  mov     ecx, 3
0x1800e507b  int     29h; Win8: RtlFailFast(ecx)
0x1800e507d  call    CiLogWhqlSettingsEvent
0x1800e5082  xor     ebx, ebx
0x1800e5084  cmp     cs:g_NumberOfSiPolicies, ebx
0x1800e508a  jbe     short loc_1800E50AD
0x1800e508c  mov     rcx, cs:g_SiPolicyHandles
0x1800e5093  lea     r8, CiPolicyRefreshActivatePolicySucceded
0x1800e509a  mov     rcx, [rcx+rbx*8]
0x1800e509e  call    CiLogSIPolicyRefresh
0x1800e50a3  add     ebx, esi
0x1800e50a5  cmp     ebx, cs:g_NumberOfSiPolicies
0x1800e50ab  jb      short loc_1800E508C
0x1800e50ad  xor     ecx, ecx
0x1800e50af  call    CiInstrumentInitialize
0x1800e50b4  xor     edx, edx
0x1800e50b6  lea     rcx, g_CipPolicyLock
0x1800e50bd  call    cs:__imp_ExReleasePushLockSharedEx
0x1800e50c4  nop     dword ptr [rax+rax+00h]
0x1800e50c9  call    cs:__imp_KeLeaveCriticalRegion
0x1800e50d0  nop     dword ptr [rax+rax+00h]
0x1800e50d5  jmp     short loc_1800E50DE
0x1800e50d7  mov     ecx, 14h
0x1800e50dc  int     29h; Win8: RtlFailFast(ecx)
0x1800e50de  xor     edx, edx
0x1800e50e0  lea     rcx, g_CiInitLock
0x1800e50e7  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1800e50ee  nop     dword ptr [rax+rax+00h]
0x1800e50f3  call    cs:__imp_KeLeaveCriticalRegion
0x1800e50fa  nop     dword ptr [rax+rax+00h]
0x1800e50ff  mov     rbx, [rsp+48h+arg_8]
0x1800e5104  mov     rsi, [rsp+48h+arg_10]
0x1800e5109  add     rsp, 40h
0x1800e510d  pop     rdi
0x1800e510e  retn
```
