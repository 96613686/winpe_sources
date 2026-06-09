# InitializeGlobals(void)

- ea: `0x180317100`
- end: `0x1803175f9`
- name: `?InitializeGlobals@@YAHXZ`
- size: `1273`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18032d310`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x18001ea60`
- `0x180030af8`
- `0x180033b28`
- `0x180080bbc`
- `0x1801703f0`
- `0x180317100`
- `0x180317600`
- `0x1803323fc`
- `0x1803471fc`
- `0x18034e474`
- `0x18034f144`
- `0x18035e058`
- `0x18035e488`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1803173fa`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180317407`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180317427`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1803173fa`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180317407`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180317427`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18031748d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1803174bc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18031748d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1803174bc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18031741a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18031743a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18031741a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18031743a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180317546`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180317576`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1803175a3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1803175c3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180317546`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180317576`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1803175a3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1803175c3`
- `ntdll!RtlGetVersion` at `0x180317353`
- `ntdll!RtlGetVersion` at `0x180317353`

## pseudocode

```c
__int64 InitializeGlobals(void)
{
  int ConfigParamLocal; // eax
  __int64 v1; // rdx
  __int64 v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // r8
  __int64 v8; // r9
  BOOL v9; // ebx
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // r8
  __int64 v16; // r9
  BOOL v17; // ebx
  int v18; // eax
  bool v19; // al
  unsigned int v20; // edx
  __int64 v21; // r8
  __int64 v22; // rcx
  unsigned __int64 v23; // rdi
  __int64 SpecificPLS; // rbx
  __int64 result; // rax
  unsigned __int64 v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rax
  BYTE Data[4]; // [rsp+50h] [rbp-168h] BYREF
  int v30; // [rsp+54h] [rbp-164h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+60h] [rbp-158h] BYREF
  char v32; // [rsp+178h] [rbp-40h]

  *(_DWORD *)Data = 0;
  v30 = 0;
  ConfigParamLocal = GetConfigParamLocalEx((__int64)"LdapFlags", Data);
  if ( ConfigParamLocal )
  {
    if ( ConfigParamLocal != 2
      && ((unsigned int)IncrementWPPPerfCountersForLevel(2)
       || (unsigned int)THStateCheckForTraceOverride(v4, v3)
       || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4)
       || gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v4, v3)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier(v4, v3, v5, v6)
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4))) )
    {
      v9 = gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v4, v3)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v4, v3, v7, v8)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4));
      if ( (unsigned int)THStateCheckForTraceOverride(v4, v3)
        || (v10 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 4)) != 0 )
      {
        v10 = 1;
      }
      WPP_SF__ATTRTYP_LOG_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        201327051,
        2,
        4,
        v10,
        v9,
        11,
        (__int64)WPP_79f68a86932833a1bbd124f8fe52de6a_Traceguids);
    }
  }
  else
  {
    LdapFlags = *(_DWORD *)Data;
    if ( (unsigned int)THStateCheckForTraceOverride(v2, v1)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 4)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v12, v11)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v12, v11, v13, v14)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 4)) )
    {
      v17 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v12, v11)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v12, v11, v15, v16)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 4));
      if ( (unsigned int)THStateCheckForTraceOverride(v12, v11)
        || (v18 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 4)) != 0 )
      {
        v18 = 1;
      }
      WPP_SF__ATTRTYP_LOG_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        201327041,
        4,
        4,
        v18,
        v17,
        10,
        (__int64)WPP_79f68a86932833a1bbd124f8fe52de6a_Traceguids);
    }
  }
  if ( !(unsigned int)InitializeCache() )
    return 0;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( RtlGetVersion(&VersionInformation) < 0 )
    return 0;
  LdapBuildNo = VersionInformation.dwBuildNumber;
  v19 = (v32 & 1) != 0 || (v32 & 0x20) != 0;
  v20 = 0;
  gfSBSSKU = v19;
  v21 = 0;
  do
  {
    v22 = 32 * v21;
    *((_DWORD *)&LimitsNotifyBlock + 8 * v21) = v20;
    switch ( v20 )
    {
      case 0u:
        goto LABEL_52;
      case 1u:
      case 2u:
        *(_DWORD *)((char *)&LimitsNotifyBlock + v22 + 16) = 590431;
        break;
      case 3u:
      case 4u:
LABEL_52:
        *(_DWORD *)((char *)&LimitsNotifyBlock + v22 + 16) = 590667;
        break;
      case 5u:
        *(_DWORD *)((char *)&LimitsNotifyBlock + v22 + 16) = 591445;
        break;
      default:
        *(_DWORD *)((char *)&LimitsNotifyBlock + v22 + 16) = 590595;
        break;
    }
    ++v20;
    ++v21;
  }
  while ( v20 < 7 );
  InitializeSRWLock(&srw_LdapLimitsLock);
  InitializeSRWLock(&LdapSslLock);
  LdapEndpointLock_initialized = 1;
  InitializeCriticalSection(&LdapEndpointLock);
  InitializeSRWLock(&srw_LocalAddrCacheLock);
  LdapSendQueueRecoveryLock_initialized = 1;
  InitializeCriticalSection(&LdapSendQueueRecoveryLock);
  if ( InitializePageBlobCache() )
    return 0;
  v23 = 0;
  qword_1805272E8 = (__int64)&ActiveConnectionsList;
  ActiveConnectionsList.Flink = &ActiveConnectionsList;
  if ( gcNumaProcessors )
  {
    while ( 1 )
    {
      SpecificPLS = GetSpecificPLS(v23);
      *(_DWORD *)(SpecificPLS + 256) = 1;
      if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(SpecificPLS + 216), 0x190u) )
        break;
      *(_DWORD *)(SpecificPLS + 320) = 1;
      *(_QWORD *)(SpecificPLS + 272) = SpecificPLS + 264;
      *(_QWORD *)(SpecificPLS + 264) = SpecificPLS + 264;
      if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(SpecificPLS + 280), 0x190u) )
        break;
      *(_DWORD *)(SpecificPLS + 344) = v23;
      *(_QWORD *)(SpecificPLS + 336) = SpecificPLS + 328;
      ++v23;
      *(_QWORD *)(SpecificPLS + 328) = SpecificPLS + 328;
      if ( v23 >= (unsigned int)gcNumaProcessors )
        goto LABEL_59;
    }
    v26 = (unsigned int)gcNumaProcessors;
    if ( v23 < (unsigned int)gcNumaProcessors )
      v26 = v23;
    for ( ; v26; --v26 )
    {
      v27 = GetSpecificPLS(v26);
      if ( *(_DWORD *)(v27 + 256) )
      {
        DeleteCriticalSection((LPCRITICAL_SECTION)(v27 + 216));
        *(_DWORD *)(GetSpecificPLS(v26) + 256) = 0;
      }
      v28 = GetSpecificPLS(v26);
      if ( *(_DWORD *)(v28 + 320) )
      {
        DeleteCriticalSection((LPCRITICAL_SECTION)(v28 + 280));
        *(_DWORD *)(GetSpecificPLS(v26) + 320) = 0;
      }
    }
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
    UninitializePageBlobCache();
    return 0;
  }
  else
  {
LABEL_59:
    RegisterReplicationPolicyNotification();
    InitializeLimitsAndDenyList(0);
    InitializeTTLGlobals();
    UpdateSPNs(0);
    DsUuidCreate(&gCheckSum_serverGUID);
    result = 1;
    fLdapInitialized = 1;
  }
  return result;
}

```

## disassembly

```asm
0x180317100  push    rbx
0x180317102  push    rbp
0x180317103  push    rdi
0x180317104  push    r14
0x180317106  push    r15
0x180317108  sub     rsp, 190h
0x18031710f  mov     rax, cs:__security_cookie
0x180317116  xor     rax, rsp
0x180317119  mov     [rsp+1B8h+var_38], rax
0x180317121  mov     r14d, 4
0x180317127  mov     dword ptr [rsp+1B8h+Data], 0
0x18031712f  mov     r8d, r14d
0x180317132  mov     [rsp+1B8h+var_164], 0
0x18031713a  lea     r9, [rsp+1B8h+var_164]
0x18031713f  lea     rdx, [rsp+1B8h+Data]; lpData
0x180317144  lea     rcx, aLdapflags; "LdapFlags"
0x18031714b  call    GetConfigParamLocalEx
0x180317150  lea     ebp, [r14-3]
0x180317154  mov     edi, eax
0x180317156  test    eax, eax
0x180317158  jz      loc_18031723D
0x18031715e  lea     r15d, [r14-2]
0x180317162  cmp     eax, r15d
0x180317165  jz      loc_180317327
0x18031716b  mov     ecx, r15d
0x18031716e  call    IncrementWPPPerfCountersForLevel
0x180317173  test    eax, eax
0x180317175  jnz     short loc_1803171CA
0x180317177  call    THStateCheckForTraceOverride
0x18031717c  test    eax, eax
0x18031717e  jnz     short loc_1803171CA
0x180317180  mov     r8d, r14d
0x180317183  mov     edx, r15d
0x180317186  xor     ecx, ecx
0x180317188  call    CheckWPPLevelFlagsEnabledForProvider
0x18031718d  test    eax, eax
0x18031718f  jnz     short loc_1803171CA
0x180317191  mov     eax, cs:gfTraceToSecondProvider
0x180317197  test    eax, eax
0x180317199  jz      loc_180317327
0x18031719f  call    THStateCheckForTraceOverride
0x1803171a4  test    eax, eax
0x1803171a6  jnz     short loc_1803171CA
0x1803171a8  call    ThStateCheckIfTraceToSecondProvier
0x1803171ad  test    eax, eax
0x1803171af  jz      loc_180317327
0x1803171b5  mov     r8d, r14d
0x1803171b8  mov     edx, r15d
0x1803171bb  mov     ecx, ebp
0x1803171bd  call    CheckWPPLevelFlagsEnabledForProvider
0x1803171c2  test    eax, eax
0x1803171c4  jz      loc_180317327
0x1803171ca  mov     eax, cs:gfTraceToSecondProvider
0x1803171d0  test    eax, eax
0x1803171d2  jz      short loc_1803171FB
0x1803171d4  call    THStateCheckForTraceOverride
0x1803171d9  test    eax, eax
0x1803171db  jnz     short loc_1803171F7
0x1803171dd  call    ThStateCheckIfTraceToSecondProvier
0x1803171e2  test    eax, eax
0x1803171e4  jz      short loc_1803171FB
0x1803171e6  mov     r8d, r14d
0x1803171e9  mov     edx, r15d
0x1803171ec  mov     ecx, ebp
0x1803171ee  call    CheckWPPLevelFlagsEnabledForProvider
0x1803171f3  test    eax, eax
0x1803171f5  jz      short loc_1803171FB
0x1803171f7  mov     ebx, ebp
0x1803171f9  jmp     short loc_1803171FD
0x1803171fb  xor     ebx, ebx
0x1803171fd  call    THStateCheckForTraceOverride
0x180317202  test    eax, eax
0x180317204  jnz     short loc_180317217
0x180317206  mov     r8d, r14d
0x180317209  mov     edx, r15d
0x18031720c  xor     ecx, ecx
0x18031720e  call    CheckWPPLevelFlagsEnabledForProvider
0x180317213  test    eax, eax
0x180317215  jz      short loc_180317219
0x180317217  mov     eax, ebp
0x180317219  mov     [rsp+1B8h+var_178], edi
0x18031721d  lea     rcx, WPP_79f68a86932833a1bbd124f8fe52de6a_Traceguids
0x180317224  mov     [rsp+1B8h+var_180], rcx
0x180317229  mov     r8d, r15d
0x18031722c  mov     [rsp+1B8h+var_188], 0Bh
0x180317233  mov     edx, 0C0001CBh
0x180317238  jmp     loc_18031730C
0x18031723d  mov     eax, dword ptr [rsp+1B8h+Data]
0x180317241  mov     cs:?LdapFlags@@3KA, eax; ulong LdapFlags
0x180317247  call    THStateCheckForTraceOverride
0x18031724c  test    eax, eax
0x18031724e  jnz     short loc_18031729A
0x180317250  mov     r8d, r14d
0x180317253  mov     edx, r14d
0x180317256  xor     ecx, ecx
0x180317258  call    CheckWPPLevelFlagsEnabledForProvider
0x18031725d  test    eax, eax
0x18031725f  jnz     short loc_18031729A
0x180317261  mov     eax, cs:gfTraceToSecondProvider
0x180317267  test    eax, eax
0x180317269  jz      loc_180317327
0x18031726f  call    THStateCheckForTraceOverride
0x180317274  test    eax, eax
0x180317276  jnz     short loc_18031729A
0x180317278  call    ThStateCheckIfTraceToSecondProvier
0x18031727d  test    eax, eax
0x18031727f  jz      loc_180317327
0x180317285  mov     r8d, r14d
0x180317288  mov     edx, r14d
0x18031728b  mov     ecx, ebp
0x18031728d  call    CheckWPPLevelFlagsEnabledForProvider
0x180317292  test    eax, eax
0x180317294  jz      loc_180317327
0x18031729a  mov     eax, cs:gfTraceToSecondProvider
0x1803172a0  mov     edi, dword ptr [rsp+1B8h+Data]
0x1803172a4  test    eax, eax
0x1803172a6  jz      short loc_1803172CF
0x1803172a8  call    THStateCheckForTraceOverride
0x1803172ad  test    eax, eax
0x1803172af  jnz     short loc_1803172CB
0x1803172b1  call    ThStateCheckIfTraceToSecondProvier
0x1803172b6  test    eax, eax
0x1803172b8  jz      short loc_1803172CF
0x1803172ba  mov     r8d, r14d
0x1803172bd  mov     edx, r14d
0x1803172c0  mov     ecx, ebp
0x1803172c2  call    CheckWPPLevelFlagsEnabledForProvider
0x1803172c7  test    eax, eax
0x1803172c9  jz      short loc_1803172CF
0x1803172cb  mov     ebx, ebp
0x1803172cd  jmp     short loc_1803172D1
0x1803172cf  xor     ebx, ebx
0x1803172d1  call    THStateCheckForTraceOverride
0x1803172d6  test    eax, eax
0x1803172d8  jnz     short loc_1803172EB
0x1803172da  mov     r8d, r14d
0x1803172dd  mov     edx, r14d
0x1803172e0  xor     ecx, ecx
0x1803172e2  call    CheckWPPLevelFlagsEnabledForProvider
0x1803172e7  test    eax, eax
0x1803172e9  jz      short loc_1803172ED
0x1803172eb  mov     eax, ebp
0x1803172ed  mov     [rsp+1B8h+var_178], edi
0x1803172f1  lea     rcx, WPP_79f68a86932833a1bbd124f8fe52de6a_Traceguids
0x1803172f8  mov     [rsp+1B8h+var_180], rcx
0x1803172fd  mov     r8d, r14d
0x180317300  mov     [rsp+1B8h+var_188], 0Ah
0x180317307  mov     edx, 0C0001C1h
0x18031730c  mov     rcx, cs:WPP_GLOBAL_Control
0x180317313  mov     r9d, r14d
0x180317316  mov     [rsp+1B8h+var_190], ebx
0x18031731a  mov     [rsp+1B8h+var_198], eax
0x18031731e  mov     rcx, [rcx+10h]
0x180317322  call    WPP_SF__ATTRTYP_LOG_
0x180317327  call    ?InitializeCache@@YAHXZ; InitializeCache(void)
0x18031732c  test    eax, eax
0x18031732e  jz      loc_1803175D8
0x180317334  xor     edx, edx; Val
0x180317336  lea     rcx, [rsp+1B8h+VersionInformation.dwMajorVersion]; void *
0x18031733b  mov     r8d, 118h; Size
0x180317341  call    memset_0
0x180317346  lea     rcx, [rsp+1B8h+VersionInformation]; lpVersionInformation
0x18031734b  mov     [rsp+1B8h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180317353  call    cs:__imp_RtlGetVersion
0x180317359  test    eax, eax
0x18031735b  js      loc_1803175D8
0x180317361  movzx   eax, word ptr [rsp+1B8h+VersionInformation.dwBuildNumber]
0x180317366  mov     cs:?LdapBuildNo@@3GA, ax; ushort LdapBuildNo
0x18031736d  mov     al, [rsp+1B8h+var_40]
0x180317374  test    bpl, al
0x180317377  jnz     short loc_180317381
0x180317379  test    al, 20h
0x18031737b  jnz     short loc_180317381
0x18031737d  xor     al, al
0x18031737f  jmp     short loc_180317384
0x180317381  mov     al, bpl
0x180317384  xor     edx, edx
0x180317386  mov     cs:?gfSBSSKU@@3EA, al; uchar gfSBSSKU
0x18031738c  xor     r8d, r8d
0x18031738f  lea     r9, ?LimitsNotifyBlock@@3PAU_LIMITS_NOTIFICATION_BLOCK@@A; _LIMITS_NOTIFICATION_BLOCK near * LimitsNotifyBlock
0x180317396  mov     rcx, r8
0x180317399  mov     eax, edx
0x18031739b  shl     rcx, 5
0x18031739f  mov     [rcx+r9], edx
0x1803173a3  test    edx, edx
0x1803173a5  jz      short loc_1803173E0
0x1803173a7  sub     eax, ebp
0x1803173a9  jz      short loc_1803173D5
0x1803173ab  sub     eax, ebp
0x1803173ad  jz      short loc_1803173D5
0x1803173af  sub     eax, ebp
0x1803173b1  jz      short loc_1803173E0
0x1803173b3  sub     eax, ebp
0x1803173b5  jz      short loc_1803173E0
0x1803173b7  sub     eax, ebp
0x1803173b9  jz      short loc_1803173CA
0x1803173bb  cmp     eax, ebp
0x1803173bd  jnz     short loc_1803173E9
0x1803173bf  mov     dword ptr [rcx+r9+10h], 90303h
0x1803173c8  jmp     short loc_1803173E9
0x1803173ca  mov     dword ptr [rcx+r9+10h], 90655h
0x1803173d3  jmp     short loc_1803173E9
0x1803173d5  mov     dword ptr [rcx+r9+10h], 9025Fh
0x1803173de  jmp     short loc_1803173E9
0x1803173e0  mov     dword ptr [rcx+r9+10h], 9034Bh
0x1803173e9  add     edx, ebp
0x1803173eb  add     r8, rbp
0x1803173ee  cmp     edx, 7
0x1803173f1  jb      short loc_180317396
0x1803173f3  lea     rcx, srw_LdapLimitsLock; SRWLock
0x1803173fa  call    cs:__imp_InitializeSRWLock
0x180317400  lea     rcx, LdapSslLock; SRWLock
0x180317407  call    cs:__imp_InitializeSRWLock
0x18031740d  lea     rcx, LdapEndpointLock; lpCriticalSection
0x180317414  mov     cs:LdapEndpointLock_initialized, ebp
0x18031741a  call    cs:__imp_InitializeCriticalSection
0x180317420  lea     rcx, srw_LocalAddrCacheLock; SRWLock
0x180317427  call    cs:__imp_InitializeSRWLock
0x18031742d  lea     rcx, LdapSendQueueRecoveryLock; lpCriticalSection
0x180317434  mov     cs:LdapSendQueueRecoveryLock_initialized, ebp
0x18031743a  call    cs:__imp_InitializeCriticalSection
0x180317440  call    ?InitializePageBlobCache@@YAKXZ; InitializePageBlobCache(void)
0x180317445  test    eax, eax
0x180317447  jnz     loc_1803175D8
0x18031744d  lea     rax, ?ActiveConnectionsList@@3U_LIST_ENTRY@@A; _LIST_ENTRY ActiveConnectionsList
0x180317454  xor     edi, edi
0x180317456  cmp     cs:gcNumaProcessors, edi
0x18031745c  mov     cs:qword_1805272E8, rax
0x180317463  mov     cs:?ActiveConnectionsList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY ActiveConnectionsList
0x18031746a  jbe     short loc_1803174EB
0x18031746c  mov     r14d, 190h
0x180317472  mov     rcx, rdi
0x180317475  call    GetSpecificPLS
0x18031747a  mov     edx, r14d; dwSpinCount
0x18031747d  mov     rbx, rax
0x180317480  lea     rcx, [rax+0D8h]; lpCriticalSection
0x180317487  mov     [rax+100h], ebp
0x18031748d  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180317493  test    eax, eax
0x180317495  jz      loc_18031751C
0x18031749b  lea     rcx, [rbx+108h]
0x1803174a2  mov     [rbx+140h], ebp
0x1803174a8  mov     [rbx+110h], rcx
0x1803174af  mov     edx, r14d; dwSpinCount
0x1803174b2  mov     [rcx], rcx
0x1803174b5  lea     rcx, [rbx+118h]; lpCriticalSection
0x1803174bc  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1803174c2  test    eax, eax
0x1803174c4  jz      short loc_18031751C
0x1803174c6  lea     rax, [rbx+148h]
0x1803174cd  mov     [rbx+158h], edi
0x1803174d3  mov     [rbx+150h], rax
0x1803174da  add     rdi, rbp
0x1803174dd  mov     [rax], rax
0x1803174e0  mov     eax, cs:gcNumaProcessors
0x1803174e6  cmp     rdi, rax
0x1803174e9  jb      short loc_180317472
0x1803174eb  call    ?RegisterReplicationPolicyNotification@@YAHXZ; RegisterReplicationPolicyNotification(void)
0x1803174f0  xor     ecx, ecx; struct _LIMITS_NOTIFICATION_BLOCK *
0x1803174f2  call    ?InitializeLimitsAndDenyList@@YAHPEAU_LIMITS_NOTIFICATION_BLOCK@@@Z; InitializeLimitsAndDenyList(_LIMITS_NOTIFICATION_BLOCK *)
0x1803174f7  call    ?InitializeTTLGlobals@@YAHXZ; InitializeTTLGlobals(void)
0x1803174fc  xor     ecx, ecx; struct _LIMITS_NOTIFICATION_BLOCK *
0x1803174fe  call    ?UpdateSPNs@@YAXPEAU_LIMITS_NOTIFICATION_BLOCK@@@Z; UpdateSPNs(_LIMITS_NOTIFICATION_BLOCK *)
0x180317503  lea     rcx, ?gCheckSum_serverGUID@@3U_GUID@@A; _GUID gCheckSum_serverGUID
0x18031750a  call    DsUuidCreate
0x18031750f  mov     eax, ebp
0x180317511  mov     cs:?fLdapInitialized@@3HA, ebp; int fLdapInitialized
0x180317517  jmp     loc_1803175DA
0x18031751c  mov     ebx, cs:gcNumaProcessors
0x180317522  cmp     rdi, rbx
0x180317525  cmovb   rbx, rdi
0x180317529  test    rbx, rbx
0x18031752c  jz      short loc_180317593
0x18031752e  mov     rcx, rbx
0x180317531  call    GetSpecificPLS
0x180317536  cmp     dword ptr [rax+100h], 0
0x18031753d  jz      short loc_18031755E
0x18031753f  lea     rcx, [rax+0D8h]; lpCriticalSection
0x180317546  call    cs:__imp_DeleteCriticalSection
0x18031754c  mov     rcx, rbx
0x18031754f  call    GetSpecificPLS
0x180317554  mov     dword ptr [rax+100h], 0
0x18031755e  mov     rcx, rbx
0x180317561  call    GetSpecificPLS
0x180317566  cmp     dword ptr [rax+140h], 0
0x18031756d  jz      short loc_18031758E
0x18031756f  lea     rcx, [rax+118h]; lpCriticalSection
0x180317576  call    cs:__imp_DeleteCriticalSection
0x18031757c  mov     rcx, rbx
0x18031757f  call    GetSpecificPLS
0x180317584  mov     dword ptr [rax+140h], 0
0x18031758e  sub     rbx, rbp
0x180317591  jnz     short loc_18031752E
0x180317593  cmp     cs:LdapEndpointLock_initialized, 0
0x18031759a  jz      short loc_1803175B3
0x18031759c  lea     rcx, LdapEndpointLock; lpCriticalSection
0x1803175a3  call    cs:__imp_DeleteCriticalSection
0x1803175a9  mov     cs:LdapEndpointLock_initialized, 0
0x1803175b3  cmp     cs:LdapSendQueueRecoveryLock_initialized, 0
0x1803175ba  jz      short loc_1803175D3
  ... truncated ...
```
