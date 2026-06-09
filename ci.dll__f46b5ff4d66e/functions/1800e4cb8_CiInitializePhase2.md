# CiInitializePhase2

- ea: `0x1800e4cb8`
- end: `0x1800e5149`
- name: `CiInitializePhase2`
- size: `1169`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800e55e0`

## callees

- `0x180010094`
- `0x18001e70c`
- `0x18005ab8c`
- `0x180060bdc`
- `0x18006365c`
- `0x180065c48`
- `0x18006b07c`
- `0x18006b4c8`
- `0x18006c68c`
- `0x18006c798`
- `0x18006d788`
- `0x180071aa4`
- `0x180076694`
- `0x180076a58`
- `0x18007e848`
- `0x18009dccc`
- `0x18009ec28`
- `0x1800ca4b0`
- `0x1800e45e8`
- `0x1800e4cb8`
- `0x1800f703c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800e4ce3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800e4e37`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800e4f52`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800e4ce3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800e4e37`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800e4f52`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800e4cf8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800e4e4c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800e4cf8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800e4e4c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800e4e6a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800e5120`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800e4e6a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800e5120`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1800e50f6`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1800e50f6`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1800e4f67`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1800e4f67`
- `ntoskrnl!EtwRegister` at `0x1800e4d2d`
- `ntoskrnl!EtwRegister` at `0x1800e4d2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e509e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e509e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800e4e76`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800e5102`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800e512c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800e4e76`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800e5102`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800e512c`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1800e4f06`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1800e4f35`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1800e4f06`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1800e4f35`
- `ntoskrnl!ExInitializeResourceLite` at `0x1800e4ea6`
- `ntoskrnl!ExInitializeResourceLite` at `0x1800e4ea6`
- `ntoskrnl!RtlCheckRegistryKey` at `0x1800e4ec0`
- `ntoskrnl!RtlCheckRegistryKey` at `0x1800e4ec0`

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
  unsigned int v13; // ecx
  __int64 v14; // rdx
  __int64 v15; // rcx
  PVOID *v16; // rax
  PVOID *v17; // rcx
  __int64 v18; // rdx
  __int64 i; // rbx
  ULONGLONG RegHandle; // [rsp+50h] [rbp+8h] BYREF

  RegHandle = 0;
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_EtwEventHandle, 0, 0) )
    return;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(&g_CiInitLock, 0);
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_EtwEventHandle, 0, 0) )
    goto LABEL_44;
  wil_InitializeFeatureStaging();
  if ( EtwRegister(&CodeIntegrityEventProviderId, 0, 0, &RegHandle) < 0 )
    goto LABEL_43;
  TlgRegisterAggregateProviderEx(&dword_180048000);
  TlgRegisterAggregateProviderEx(&dword_180048080);
  TlgRegisterAggregateProviderEx(&dword_1800481D8);
  TlgRegisterAggregateProviderEx(&qword_180048040);
  TlgRegisterAggregateProviderEx(&qword_180048168);
  TlgRegisterAggregateProviderEx(&dword_180048128);
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_1800480B8);
  TlgRegisterAggregateProviderEx(&dword_1800481A0);
  TlgRegisterAggregateProviderEx(&dword_1800480F0);
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
    goto LABEL_43;
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
LABEL_43:
      __fastfail(0x14u);
  }
  qword_1800487F0 = (__int64)&qword_1800487E8;
  qword_1800487E8 = &qword_1800487E8;
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
      CiLogFileRequestedValidationEventWithProcessName((_DWORD)g_BootDriverList + 16, (int)&qword_180030350, 1, v6, v9);
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
    if ( (unsigned int)Feature_Servicing_WhqlOnlyContainment__private_IsEnabledDeviceUsageNoInline() )
    {
      v13 = *((_DWORD *)v7 + 9);
      if ( (v13 & 0x20000) == 0 )
      {
        v14 = HIWORD(v13);
        v15 = v13 >> 15;
        LOBYTE(v14) = v14 & 1;
        LOBYTE(v15) = v15 & 1;
        CipIncrementWhqlOnlyCountersAndResetEvaluation(v15, v14, v7 + 2);
      }
    }
    v16 = *v7;
    if ( (*v7)[1] != v7 || (v17 = v7[1], *v17 != v7) )
      __fastfail(3u);
    *v17 = v16;
    v16[1] = v17;
    ExFreePoolWithTag(v7, 0);
  }
  CiLogWhqlSettingsEvent();
  for ( i = 0; (unsigned int)i < g_NumberOfSiPolicies; i = (unsigned int)(i + 1) )
    CiLogSIPolicyRefresh(*((_QWORD *)g_SiPolicyHandles + i), v18, CiPolicyRefreshActivatePolicySucceded);
  CiInstrumentInitialize(0);
  ExReleasePushLockSharedEx(&g_CipPolicyLock, 0);
  KeLeaveCriticalRegion();
LABEL_44:
  ExReleasePushLockExclusiveEx(&g_CiInitLock, 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x1800e4cb8  mov     [rsp+arg_8], rbx
0x1800e4cbd  mov     [rsp+arg_10], rsi
0x1800e4cc2  push    rdi
0x1800e4cc3  sub     rsp, 40h
0x1800e4cc7  xor     ecx, ecx
0x1800e4cc9  mov     [rsp+48h+RegHandle], 0
0x1800e4cd2  xor     eax, eax
0x1800e4cd4  lock cmpxchg cs:g_EtwEventHandle, rcx
0x1800e4cdd  jnz     loc_1800E5138
0x1800e4ce3  call    cs:__imp_KeEnterCriticalRegion
0x1800e4cea  nop     dword ptr [rax+rax+00h]
0x1800e4cef  xor     edx, edx
0x1800e4cf1  lea     rcx, g_CiInitLock
0x1800e4cf8  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1800e4cff  nop     dword ptr [rax+rax+00h]
0x1800e4d04  xor     ecx, ecx
0x1800e4d06  xor     eax, eax
0x1800e4d08  lock cmpxchg cs:g_EtwEventHandle, rcx
0x1800e4d11  jnz     loc_1800E5117
0x1800e4d17  call    wil_InitializeFeatureStaging
0x1800e4d1c  lea     r9, [rsp+48h+RegHandle]; RegHandle
0x1800e4d21  xor     r8d, r8d; CallbackContext
0x1800e4d24  xor     edx, edx; EnableCallback
0x1800e4d26  lea     rcx, CodeIntegrityEventProviderId; ProviderId
0x1800e4d2d  call    cs:__imp_EtwRegister
0x1800e4d34  nop     dword ptr [rax+rax+00h]
0x1800e4d39  test    eax, eax
0x1800e4d3b  js      loc_1800E5110
0x1800e4d41  mov     esi, 1
0x1800e4d46  lea     rcx, dword_180048000; CallbackContext
0x1800e4d4d  mov     r9d, esi
0x1800e4d50  call    TlgRegisterAggregateProviderEx
0x1800e4d55  lea     edi, [rsi+1]
0x1800e4d58  mov     r9d, edi
0x1800e4d5b  lea     rcx, dword_180048080; CallbackContext
0x1800e4d62  call    TlgRegisterAggregateProviderEx
0x1800e4d67  mov     r9d, edi
0x1800e4d6a  lea     rcx, dword_1800481D8; CallbackContext
0x1800e4d71  call    TlgRegisterAggregateProviderEx
0x1800e4d76  mov     r9d, edi
0x1800e4d79  lea     rcx, qword_180048040; CallbackContext
0x1800e4d80  call    TlgRegisterAggregateProviderEx
0x1800e4d85  mov     r9d, edi
0x1800e4d88  lea     rcx, qword_180048168; CallbackContext
0x1800e4d8f  call    TlgRegisterAggregateProviderEx
0x1800e4d94  mov     r9d, edi
0x1800e4d97  lea     rcx, dword_180048128; CallbackContext
0x1800e4d9e  call    TlgRegisterAggregateProviderEx
0x1800e4da3  xor     r8d, r8d
0x1800e4da6  lea     rcx, dword_1800480B8; CallbackContext
0x1800e4dad  xor     edx, edx
0x1800e4daf  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x1800e4db4  mov     r9d, edi
0x1800e4db7  lea     rcx, dword_1800481A0; CallbackContext
0x1800e4dbe  call    TlgRegisterAggregateProviderEx
0x1800e4dc3  mov     r9d, edi
0x1800e4dc6  lea     rcx, dword_1800480F0; CallbackContext
0x1800e4dcd  call    TlgRegisterAggregateProviderEx
0x1800e4dd2  mov     ecx, cs:g_CiDeveloperMode
0x1800e4dd8  mov     r9d, ecx
0x1800e4ddb  mov     r8d, ecx
0x1800e4dde  shr     r9d, 8
0x1800e4de2  mov     edx, ecx
0x1800e4de4  shr     r8d, 0Ch
0x1800e4de8  shr     edx, 9
0x1800e4deb  and     r9b, sil
0x1800e4dee  shr     ecx, 6
0x1800e4df1  and     r8b, sil
0x1800e4df4  and     dl, sil
0x1800e4df7  and     cl, sil
0x1800e4dfa  call    MinCrypK_Initialize
0x1800e4dff  test    eax, eax
0x1800e4e01  js      loc_1800E5110
0x1800e4e07  call    CiInitializeParallelHashingContexts
0x1800e4e0c  test    eax, eax
0x1800e4e0e  js      loc_1800E5110
0x1800e4e14  call    CiInitializeCatalogs
0x1800e4e19  test    eax, eax
0x1800e4e1b  js      loc_1800E5110
0x1800e4e21  mov     ecx, cs:g_CiDeveloperMode
0x1800e4e27  test    cl, 20h
0x1800e4e2a  jnz     short loc_1800E4E31
0x1800e4e2c  call    MinCryptRevokePrereleaseWindowsPCA
0x1800e4e31  bt      ecx, 0Bh
0x1800e4e35  jb      short loc_1800E4E8A
0x1800e4e37  call    cs:__imp_KeEnterCriticalRegion
0x1800e4e3e  nop     dword ptr [rax+rax+00h]
0x1800e4e43  xor     edx, edx
0x1800e4e45  lea     rcx, g_CipPolicyLock
0x1800e4e4c  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1800e4e53  nop     dword ptr [rax+rax+00h]
0x1800e4e58  xor     ecx, ecx
0x1800e4e5a  call    CipLoadAndValidateRevocationList
0x1800e4e5f  xor     edx, edx
0x1800e4e61  lea     rcx, g_CipPolicyLock
0x1800e4e68  mov     ebx, eax
0x1800e4e6a  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1800e4e71  nop     dword ptr [rax+rax+00h]
0x1800e4e76  call    cs:__imp_KeLeaveCriticalRegion
0x1800e4e7d  nop     dword ptr [rax+rax+00h]
0x1800e4e82  test    ebx, ebx
0x1800e4e84  js      loc_1800E5110
0x1800e4e8a  lea     rax, qword_1800487E8
0x1800e4e91  lea     rcx, Resource; Resource
0x1800e4e98  mov     cs:qword_1800487F0, rax
0x1800e4e9f  mov     cs:qword_1800487E8, rax
0x1800e4ea6  call    cs:__imp_ExInitializeResourceLite
0x1800e4ead  nop     dword ptr [rax+rax+00h]
0x1800e4eb2  call    PESetInitialState
0x1800e4eb7  lea     rdx, aMinint; "MiniNT"
0x1800e4ebe  mov     ecx, edi; RelativeTo
0x1800e4ec0  call    cs:__imp_RtlCheckRegistryKey
0x1800e4ec7  nop     dword ptr [rax+rax+00h]
0x1800e4ecc  test    eax, eax
0x1800e4ece  js      short loc_1800E4ED7
0x1800e4ed0  mov     cs:g_CiIsWinPE, sil
0x1800e4ed7  xor     eax, eax
0x1800e4ed9  mov     cs:g_TrimBootCacheCatalogEntries, sil
0x1800e4ee0  mov     [rsp+48h+Depth], ax; Depth
0x1800e4ee5  lea     rcx, g_CiValidationLookasideList; Lookaside
0x1800e4eec  mov     ebx, 63734943h
0x1800e4ef1  xor     r9d, r9d; Flags
0x1800e4ef4  mov     [rsp+48h+Tag], ebx; Tag
0x1800e4ef8  xor     r8d, r8d; Free
0x1800e4efb  xor     edx, edx; Allocate
0x1800e4efd  mov     [rsp+48h+Size], 0E20h; Size
0x1800e4f06  call    cs:__imp_ExInitializePagedLookasideList
0x1800e4f0d  nop     dword ptr [rax+rax+00h]
0x1800e4f12  xor     eax, eax
0x1800e4f14  lea     rcx, g_CiEaCacheLookasideList; Lookaside
0x1800e4f1b  mov     [rsp+48h+Depth], ax; Depth
0x1800e4f20  xor     r9d, r9d; Flags
0x1800e4f23  mov     [rsp+48h+Tag], ebx; Tag
0x1800e4f27  xor     r8d, r8d; Free
0x1800e4f2a  xor     edx, edx; Allocate
0x1800e4f2c  mov     [rsp+48h+Size], 298h; Size
0x1800e4f35  call    cs:__imp_ExInitializePagedLookasideList
0x1800e4f3c  nop     dword ptr [rax+rax+00h]
0x1800e4f41  call    SIPolicyInitializeWellKnownSidBuffer
0x1800e4f46  mov     rax, [rsp+48h+RegHandle]
0x1800e4f4b  xchg    rax, cs:g_EtwEventHandle
0x1800e4f52  call    cs:__imp_KeEnterCriticalRegion
0x1800e4f59  nop     dword ptr [rax+rax+00h]
0x1800e4f5e  xor     edx, edx
0x1800e4f60  lea     rcx, g_CipPolicyLock
0x1800e4f67  call    cs:__imp_ExAcquirePushLockSharedEx
0x1800e4f6e  nop     dword ptr [rax+rax+00h]
0x1800e4f73  mov     rdi, cs:g_BootDriverList
0x1800e4f7a  lea     rax, g_BootDriverList
0x1800e4f81  cmp     rdi, rax
0x1800e4f84  jz      loc_1800E50B6
0x1800e4f8a  mov     eax, [rdi+20h]
0x1800e4f8d  cmp     eax, 0C0000428h
0x1800e4f92  jnz     short loc_1800E4F9D
0x1800e4f94  lea     rax, CiImageFileHashNotFound
0x1800e4f9b  jmp     short loc_1800E4FAB
0x1800e4f9d  cmp     eax, 0C0000603h
0x1800e4fa2  jnz     short loc_1800E4FD6
0x1800e4fa4  lea     rax, CiRevokedDriverNotLoaded
0x1800e4fab  mov     r9b, sil; int
0x1800e4fae  mov     [rsp+48h+Size], rax; EventDescriptor
0x1800e4fb3  mov     r8d, esi; int
0x1800e4fb6  lea     rdx, qword_180030350; int
0x1800e4fbd  lea     rcx, [rdi+10h]; int
0x1800e4fc1  call    CiLogFileRequestedValidationEventWithProcessName
0x1800e4fc6  mov     edx, 13AEh
0x1800e4fcb  lea     rcx, [rdi+10h]
0x1800e4fcf  call    CiAudit
0x1800e4fd4  jmp     short loc_1800E4FF2
0x1800e4fd6  test    eax, eax
0x1800e4fd8  js      short loc_1800E4FF2
0x1800e4fda  mov     eax, [rdi+24h]
0x1800e4fdd  test    sil, al
0x1800e4fe0  jz      short loc_1800E4FF2
0x1800e4fe2  lea     rcx, [rdi+10h]
0x1800e4fe6  lea     rdx, CiNoEmbeddedSignatureDriverLoaded
0x1800e4fed  call    CiLogFileEvent
0x1800e4ff2  mov     edx, [rdi+24h]
0x1800e4ff5  test    dl, 20h
0x1800e4ff8  jz      short loc_1800E5032
0x1800e4ffa  mov     eax, [rdi+20h]
0x1800e4ffd  mov     ecx, 0C0E90002h
0x1800e5002  shr     edx, 0Eh
0x1800e5005  and     dl, sil
0x1800e5008  test    eax, eax
0x1800e500a  mov     byte ptr [rsp+48h+Tag], dl; char
0x1800e500e  cmovs   ecx, eax
0x1800e5011  mov     dword ptr [rsp+48h+Size], ecx; char
0x1800e5015  lea     rcx, [rdi+10h]; int
0x1800e5019  call    CiLogSIPolicyEvent2
0x1800e501e  test    dword ptr [rdi+24h], 4000h
0x1800e5025  jz      short loc_1800E5057
0x1800e5027  lea     rcx, [rdi+10h]
0x1800e502b  call    CiInstrumentVbsPolicyBootFailure
0x1800e5030  jmp     short loc_1800E5057
0x1800e5032  bt      edx, 8
0x1800e5036  jnb     short loc_1800E5041
0x1800e5038  lea     rdx, WhqlEnforcementFailureAudit
0x1800e503f  jmp     short loc_1800E504E
0x1800e5041  bt      edx, 9
0x1800e5045  jnb     short loc_1800E5057
0x1800e5047  lea     rdx, WhqlEnforcementFailureExempted
0x1800e504e  lea     rcx, [rdi+10h]
0x1800e5052  call    CiLogFileEvent
0x1800e5057  call    Feature_Servicing_WhqlOnlyContainment__private_IsEnabledDeviceUsageNoInline
0x1800e505c  test    eax, eax
0x1800e505e  jz      short loc_1800E5080
0x1800e5060  mov     ecx, [rdi+24h]
0x1800e5063  bt      ecx, 11h
0x1800e5067  jb      short loc_1800E5080
0x1800e5069  mov     edx, ecx
0x1800e506b  lea     r8, [rdi+10h]
0x1800e506f  shr     edx, 10h
0x1800e5072  shr     ecx, 0Fh
0x1800e5075  and     dl, sil
0x1800e5078  and     cl, sil
0x1800e507b  call    CipIncrementWhqlOnlyCountersAndResetEvaluation
0x1800e5080  mov     rax, [rdi]
0x1800e5083  cmp     [rax+8], rdi
0x1800e5087  jnz     short loc_1800E50AF
0x1800e5089  mov     rcx, [rdi+8]
0x1800e508d  cmp     [rcx], rdi
0x1800e5090  jnz     short loc_1800E50AF
0x1800e5092  mov     [rcx], rax
0x1800e5095  xor     edx, edx; Tag
0x1800e5097  mov     [rax+8], rcx
0x1800e509b  mov     rcx, rdi; P
0x1800e509e  call    cs:__imp_ExFreePoolWithTag
0x1800e50a5  nop     dword ptr [rax+rax+00h]
0x1800e50aa  jmp     loc_1800E4F73
0x1800e50af  mov     ecx, 3
0x1800e50b4  int     29h; Win8: RtlFailFast(ecx)
0x1800e50b6  call    CiLogWhqlSettingsEvent
0x1800e50bb  xor     ebx, ebx
0x1800e50bd  cmp     cs:g_NumberOfSiPolicies, ebx
0x1800e50c3  jbe     short loc_1800E50E6
0x1800e50c5  mov     rcx, cs:g_SiPolicyHandles
0x1800e50cc  lea     r8, CiPolicyRefreshActivatePolicySucceded
0x1800e50d3  mov     rcx, [rcx+rbx*8]
0x1800e50d7  call    CiLogSIPolicyRefresh
0x1800e50dc  add     ebx, esi
0x1800e50de  cmp     ebx, cs:g_NumberOfSiPolicies
0x1800e50e4  jb      short loc_1800E50C5
0x1800e50e6  xor     ecx, ecx
0x1800e50e8  call    CiInstrumentInitialize
0x1800e50ed  xor     edx, edx
0x1800e50ef  lea     rcx, g_CipPolicyLock
0x1800e50f6  call    cs:__imp_ExReleasePushLockSharedEx
0x1800e50fd  nop     dword ptr [rax+rax+00h]
0x1800e5102  call    cs:__imp_KeLeaveCriticalRegion
0x1800e5109  nop     dword ptr [rax+rax+00h]
0x1800e510e  jmp     short loc_1800E5117
0x1800e5110  mov     ecx, 14h
0x1800e5115  int     29h; Win8: RtlFailFast(ecx)
0x1800e5117  xor     edx, edx
0x1800e5119  lea     rcx, g_CiInitLock
0x1800e5120  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1800e5127  nop     dword ptr [rax+rax+00h]
0x1800e512c  call    cs:__imp_KeLeaveCriticalRegion
0x1800e5133  nop     dword ptr [rax+rax+00h]
0x1800e5138  mov     rbx, [rsp+48h+arg_8]
0x1800e513d  mov     rsi, [rsp+48h+arg_10]
0x1800e5142  add     rsp, 40h
0x1800e5146  pop     rdi
0x1800e5147  retn
```
