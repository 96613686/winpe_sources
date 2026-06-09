# CiInitializePhase2

- ea: `0x1800e5228`
- end: `0x1800e5690`
- name: `CiInitializePhase2`
- size: `1128`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800e5fd0`

## callees

- `0x18001e71c`
- `0x18005b7cc`
- `0x1800614fc`
- `0x18006400c`
- `0x1800666ac`
- `0x18006c46c`
- `0x18006d740`
- `0x18006d84c`
- `0x18006e83c`
- `0x180073034`
- `0x180077f24`
- `0x1800782e8`
- `0x180080888`
- `0x18008f198`
- `0x180090588`
- `0x1800cb940`
- `0x1800e4b58`
- `0x1800e5228`
- `0x1800f903c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800e5253`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800e53a7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800e54c2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800e5253`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800e53a7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800e54c2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800e5268`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800e53bc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800e5268`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800e53bc`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800e53da`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800e5667`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800e53da`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800e5667`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1800e563d`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1800e563d`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1800e54d7`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1800e54d7`
- `ntoskrnl!EtwRegister` at `0x1800e529d`
- `ntoskrnl!EtwRegister` at `0x1800e529d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e55e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e55e5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800e53e6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800e5649`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800e5673`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800e53e6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800e5649`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800e5673`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1800e5476`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1800e54a5`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1800e5476`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1800e54a5`
- `ntoskrnl!ExInitializeResourceLite` at `0x1800e5416`
- `ntoskrnl!ExInitializeResourceLite` at `0x1800e5416`
- `ntoskrnl!RtlCheckRegistryKey` at `0x1800e5430`
- `ntoskrnl!RtlCheckRegistryKey` at `0x1800e5430`

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
  ExInitializePagedLookasideList(&g_CiValidationLookasideList, 0, 0, 0, 0xE30u, 0x63734943u, 0);
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
      CiLogFileRequestedValidationEventWithProcessName((_DWORD)g_BootDriverList + 16, (int)&qword_1800303C0, 1, v6, v9);
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
0x1800e5228  mov     [rsp+arg_8], rbx
0x1800e522d  mov     [rsp+arg_10], rsi
0x1800e5232  push    rdi
0x1800e5233  sub     rsp, 40h
0x1800e5237  xor     ecx, ecx
0x1800e5239  mov     [rsp+48h+RegHandle], 0
0x1800e5242  xor     eax, eax
0x1800e5244  lock cmpxchg cs:g_EtwEventHandle, rcx
0x1800e524d  jnz     loc_1800E567F
0x1800e5253  call    cs:__imp_KeEnterCriticalRegion
0x1800e525a  nop     dword ptr [rax+rax+00h]
0x1800e525f  xor     edx, edx
0x1800e5261  lea     rcx, g_CiInitLock
0x1800e5268  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1800e526f  nop     dword ptr [rax+rax+00h]
0x1800e5274  xor     ecx, ecx
0x1800e5276  xor     eax, eax
0x1800e5278  lock cmpxchg cs:g_EtwEventHandle, rcx
0x1800e5281  jnz     loc_1800E565E
0x1800e5287  call    wil_InitializeFeatureStaging
0x1800e528c  lea     r9, [rsp+48h+RegHandle]; RegHandle
0x1800e5291  xor     r8d, r8d; CallbackContext
0x1800e5294  xor     edx, edx; EnableCallback
0x1800e5296  lea     rcx, CodeIntegrityEventProviderId; ProviderId
0x1800e529d  call    cs:__imp_EtwRegister
0x1800e52a4  nop     dword ptr [rax+rax+00h]
0x1800e52a9  test    eax, eax
0x1800e52ab  js      loc_1800E5657
0x1800e52b1  mov     esi, 1
0x1800e52b6  lea     rcx, dword_180049000; CallbackContext
0x1800e52bd  mov     r9d, esi
0x1800e52c0  call    TlgRegisterAggregateProviderEx
0x1800e52c5  lea     edi, [rsi+1]
0x1800e52c8  mov     r9d, edi
0x1800e52cb  lea     rcx, dword_180049080; CallbackContext
0x1800e52d2  call    TlgRegisterAggregateProviderEx
0x1800e52d7  mov     r9d, edi
0x1800e52da  lea     rcx, dword_1800491D8; CallbackContext
0x1800e52e1  call    TlgRegisterAggregateProviderEx
0x1800e52e6  mov     r9d, edi
0x1800e52e9  lea     rcx, qword_180049040; CallbackContext
0x1800e52f0  call    TlgRegisterAggregateProviderEx
0x1800e52f5  mov     r9d, edi
0x1800e52f8  lea     rcx, qword_180049168; CallbackContext
0x1800e52ff  call    TlgRegisterAggregateProviderEx
0x1800e5304  mov     r9d, edi
0x1800e5307  lea     rcx, dword_180049128; CallbackContext
0x1800e530e  call    TlgRegisterAggregateProviderEx
0x1800e5313  xor     r8d, r8d
0x1800e5316  lea     rcx, dword_1800490B8; CallbackContext
0x1800e531d  xor     edx, edx
0x1800e531f  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x1800e5324  mov     r9d, edi
0x1800e5327  lea     rcx, dword_1800491A0; CallbackContext
0x1800e532e  call    TlgRegisterAggregateProviderEx
0x1800e5333  mov     r9d, edi
0x1800e5336  lea     rcx, qword_1800490F0; CallbackContext
0x1800e533d  call    TlgRegisterAggregateProviderEx
0x1800e5342  mov     ecx, cs:g_CiDeveloperMode
0x1800e5348  mov     r9d, ecx
0x1800e534b  mov     r8d, ecx
0x1800e534e  shr     r9d, 8
0x1800e5352  mov     edx, ecx
0x1800e5354  shr     r8d, 0Ch
0x1800e5358  shr     edx, 9
0x1800e535b  and     r9b, sil
0x1800e535e  shr     ecx, 6
0x1800e5361  and     r8b, sil
0x1800e5364  and     dl, sil
0x1800e5367  and     cl, sil
0x1800e536a  call    MinCrypK_Initialize
0x1800e536f  test    eax, eax
0x1800e5371  js      loc_1800E5657
0x1800e5377  call    CiInitializeParallelHashingContexts
0x1800e537c  test    eax, eax
0x1800e537e  js      loc_1800E5657
0x1800e5384  call    CiInitializeCatalogs
0x1800e5389  test    eax, eax
0x1800e538b  js      loc_1800E5657
0x1800e5391  mov     ecx, cs:g_CiDeveloperMode
0x1800e5397  test    cl, 20h
0x1800e539a  jnz     short loc_1800E53A1
0x1800e539c  call    MinCryptRevokePrereleaseWindowsPCA
0x1800e53a1  bt      ecx, 0Bh
0x1800e53a5  jb      short loc_1800E53FA
0x1800e53a7  call    cs:__imp_KeEnterCriticalRegion
0x1800e53ae  nop     dword ptr [rax+rax+00h]
0x1800e53b3  xor     edx, edx
0x1800e53b5  lea     rcx, g_CipPolicyLock
0x1800e53bc  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1800e53c3  nop     dword ptr [rax+rax+00h]
0x1800e53c8  xor     ecx, ecx
0x1800e53ca  call    CipLoadAndValidateRevocationList
0x1800e53cf  xor     edx, edx
0x1800e53d1  lea     rcx, g_CipPolicyLock
0x1800e53d8  mov     ebx, eax
0x1800e53da  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1800e53e1  nop     dword ptr [rax+rax+00h]
0x1800e53e6  call    cs:__imp_KeLeaveCriticalRegion
0x1800e53ed  nop     dword ptr [rax+rax+00h]
0x1800e53f2  test    ebx, ebx
0x1800e53f4  js      loc_1800E5657
0x1800e53fa  lea     rax, qword_1800497E8
0x1800e5401  lea     rcx, Resource; Resource
0x1800e5408  mov     cs:qword_1800497F0, rax
0x1800e540f  mov     cs:qword_1800497E8, rax
0x1800e5416  call    cs:__imp_ExInitializeResourceLite
0x1800e541d  nop     dword ptr [rax+rax+00h]
0x1800e5422  call    PESetInitialState
0x1800e5427  lea     rdx, aMinint; "MiniNT"
0x1800e542e  mov     ecx, edi; RelativeTo
0x1800e5430  call    cs:__imp_RtlCheckRegistryKey
0x1800e5437  nop     dword ptr [rax+rax+00h]
0x1800e543c  test    eax, eax
0x1800e543e  js      short loc_1800E5447
0x1800e5440  mov     cs:g_CiIsWinPE, sil
0x1800e5447  xor     eax, eax
0x1800e5449  mov     cs:g_TrimBootCacheCatalogEntries, sil
0x1800e5450  mov     [rsp+48h+Depth], ax; Depth
0x1800e5455  lea     rcx, g_CiValidationLookasideList; Lookaside
0x1800e545c  mov     ebx, 63734943h
0x1800e5461  xor     r9d, r9d; Flags
0x1800e5464  mov     [rsp+48h+Tag], ebx; Tag
0x1800e5468  xor     r8d, r8d; Free
0x1800e546b  xor     edx, edx; Allocate
0x1800e546d  mov     [rsp+48h+Size], 0E30h; Size
0x1800e5476  call    cs:__imp_ExInitializePagedLookasideList
0x1800e547d  nop     dword ptr [rax+rax+00h]
0x1800e5482  xor     eax, eax
0x1800e5484  lea     rcx, g_CiEaCacheLookasideList; Lookaside
0x1800e548b  mov     [rsp+48h+Depth], ax; Depth
0x1800e5490  xor     r9d, r9d; Flags
0x1800e5493  mov     [rsp+48h+Tag], ebx; Tag
0x1800e5497  xor     r8d, r8d; Free
0x1800e549a  xor     edx, edx; Allocate
0x1800e549c  mov     [rsp+48h+Size], 298h; Size
0x1800e54a5  call    cs:__imp_ExInitializePagedLookasideList
0x1800e54ac  nop     dword ptr [rax+rax+00h]
0x1800e54b1  call    SIPolicyInitializeWellKnownSidBuffer
0x1800e54b6  mov     rax, [rsp+48h+RegHandle]
0x1800e54bb  xchg    rax, cs:g_EtwEventHandle
0x1800e54c2  call    cs:__imp_KeEnterCriticalRegion
0x1800e54c9  nop     dword ptr [rax+rax+00h]
0x1800e54ce  xor     edx, edx
0x1800e54d0  lea     rcx, g_CipPolicyLock
0x1800e54d7  call    cs:__imp_ExAcquirePushLockSharedEx
0x1800e54de  nop     dword ptr [rax+rax+00h]
0x1800e54e3  mov     rdi, cs:g_BootDriverList
0x1800e54ea  lea     rax, g_BootDriverList
0x1800e54f1  cmp     rdi, rax
0x1800e54f4  jz      loc_1800E55FD
0x1800e54fa  mov     eax, [rdi+20h]
0x1800e54fd  cmp     eax, 0C0000428h
0x1800e5502  jnz     short loc_1800E550D
0x1800e5504  lea     rax, CiImageFileHashNotFound
0x1800e550b  jmp     short loc_1800E551B
0x1800e550d  cmp     eax, 0C0000603h
0x1800e5512  jnz     short loc_1800E5546
0x1800e5514  lea     rax, CiRevokedDriverNotLoaded
0x1800e551b  mov     r9b, sil; int
0x1800e551e  mov     [rsp+48h+Size], rax; EventDescriptor
0x1800e5523  mov     r8d, esi; int
0x1800e5526  lea     rdx, qword_1800303C0; int
0x1800e552d  lea     rcx, [rdi+10h]; int
0x1800e5531  call    CiLogFileRequestedValidationEventWithProcessName
0x1800e5536  mov     edx, 13AEh
0x1800e553b  lea     rcx, [rdi+10h]
0x1800e553f  call    CiAudit
0x1800e5544  jmp     short loc_1800E5562
0x1800e5546  test    eax, eax
0x1800e5548  js      short loc_1800E5562
0x1800e554a  mov     eax, [rdi+24h]
0x1800e554d  test    sil, al
0x1800e5550  jz      short loc_1800E5562
0x1800e5552  lea     rcx, [rdi+10h]
0x1800e5556  lea     rdx, CiNoEmbeddedSignatureDriverLoaded
0x1800e555d  call    CiLogFileEvent
0x1800e5562  mov     edx, [rdi+24h]
0x1800e5565  test    dl, 20h
0x1800e5568  jz      short loc_1800E55A2
0x1800e556a  mov     eax, [rdi+20h]
0x1800e556d  mov     ecx, 0C0E90002h
0x1800e5572  shr     edx, 0Eh
0x1800e5575  and     dl, sil
0x1800e5578  test    eax, eax
0x1800e557a  mov     byte ptr [rsp+48h+Tag], dl; char
0x1800e557e  cmovs   ecx, eax
0x1800e5581  mov     dword ptr [rsp+48h+Size], ecx; char
0x1800e5585  lea     rcx, [rdi+10h]; int
0x1800e5589  call    CiLogSIPolicyEvent2
0x1800e558e  test    dword ptr [rdi+24h], 4000h
0x1800e5595  jz      short loc_1800E55C7
0x1800e5597  lea     rcx, [rdi+10h]
0x1800e559b  call    CiInstrumentVbsPolicyBootFailure
0x1800e55a0  jmp     short loc_1800E55C7
0x1800e55a2  bt      edx, 8
0x1800e55a6  jnb     short loc_1800E55B1
0x1800e55a8  lea     rdx, WhqlEnforcementFailureAudit
0x1800e55af  jmp     short loc_1800E55BE
0x1800e55b1  bt      edx, 9
0x1800e55b5  jnb     short loc_1800E55C7
0x1800e55b7  lea     rdx, WhqlEnforcementFailureExempted
0x1800e55be  lea     rcx, [rdi+10h]
0x1800e55c2  call    CiLogFileEvent
0x1800e55c7  mov     rax, [rdi]
0x1800e55ca  cmp     [rax+8], rdi
0x1800e55ce  jnz     short loc_1800E55F6
0x1800e55d0  mov     rcx, [rdi+8]
0x1800e55d4  cmp     [rcx], rdi
0x1800e55d7  jnz     short loc_1800E55F6
0x1800e55d9  mov     [rcx], rax
0x1800e55dc  xor     edx, edx; Tag
0x1800e55de  mov     [rax+8], rcx
0x1800e55e2  mov     rcx, rdi; P
0x1800e55e5  call    cs:__imp_ExFreePoolWithTag
0x1800e55ec  nop     dword ptr [rax+rax+00h]
0x1800e55f1  jmp     loc_1800E54E3
0x1800e55f6  mov     ecx, 3
0x1800e55fb  int     29h; Win8: RtlFailFast(ecx)
0x1800e55fd  call    CiLogWhqlSettingsEvent
0x1800e5602  xor     ebx, ebx
0x1800e5604  cmp     cs:g_NumberOfSiPolicies, ebx
0x1800e560a  jbe     short loc_1800E562D
0x1800e560c  mov     rcx, cs:g_SiPolicyHandles
0x1800e5613  lea     r8, CiPolicyRefreshActivatePolicySucceded
0x1800e561a  mov     rcx, [rcx+rbx*8]
0x1800e561e  call    CiLogSIPolicyRefresh
0x1800e5623  add     ebx, esi
0x1800e5625  cmp     ebx, cs:g_NumberOfSiPolicies
0x1800e562b  jb      short loc_1800E560C
0x1800e562d  xor     ecx, ecx
0x1800e562f  call    CiInstrumentInitialize
0x1800e5634  xor     edx, edx
0x1800e5636  lea     rcx, g_CipPolicyLock
0x1800e563d  call    cs:__imp_ExReleasePushLockSharedEx
0x1800e5644  nop     dword ptr [rax+rax+00h]
0x1800e5649  call    cs:__imp_KeLeaveCriticalRegion
0x1800e5650  nop     dword ptr [rax+rax+00h]
0x1800e5655  jmp     short loc_1800E565E
0x1800e5657  mov     ecx, 14h
0x1800e565c  int     29h; Win8: RtlFailFast(ecx)
0x1800e565e  xor     edx, edx
0x1800e5660  lea     rcx, g_CiInitLock
0x1800e5667  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1800e566e  nop     dword ptr [rax+rax+00h]
0x1800e5673  call    cs:__imp_KeLeaveCriticalRegion
0x1800e567a  nop     dword ptr [rax+rax+00h]
0x1800e567f  mov     rbx, [rsp+48h+arg_8]
0x1800e5684  mov     rsi, [rsp+48h+arg_10]
0x1800e5689  add     rsp, 40h
0x1800e568d  pop     rdi
0x1800e568e  retn
```
