# LsaDbpInitDatabaseServer(ulong)

- ea: `0x1800060b0`
- end: `0x1800062b7`
- name: `?LsaDbpInitDatabaseServer@@YAJK@Z`
- size: `519`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001fb8`
- `0x1800060b0`
- `0x18000fd18`
- `0x18000fd40`
- `0x180025a7c`
- `0x18003138c`
- `0x180032ffc`
- `0x18003535c`

## import_xrefs

- `LSASRV!LsapGetWellKnownSid` at `0x18000611e`
- `LSASRV!LsapGetWellKnownSid` at `0x18000611e`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x1800062a9`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x1800062a9`
- `LSASRV!LsapCompareDomainNames` at `0x180006293`
- `LSASRV!LsapCompareDomainNames` at `0x180006293`
- `LSASRV!LsapDbQueryInformationPolicy` at `0x180006277`
- `LSASRV!LsapDbQueryInformationPolicy` at `0x180006277`
- `LSASRV!LsapGetPolicyHandle` at `0x18000623a`
- `LSASRV!LsapGetPolicyHandle` at `0x18000623a`
- `LSASRV!LsapDbExpMakeCacheInvalid` at `0x180006174`
- `LSASRV!LsapDbExpMakeCacheInvalid` at `0x180006174`
- `ntdll!RtlInitUnicodeString` at `0x180006132`
- `ntdll!RtlInitUnicodeString` at `0x180006132`
- `ntdll!NtCreateEvent` at `0x180006257`
- `ntdll!NtCreateEvent` at `0x180006257`
- `ntdll!RtlInitializeCriticalSection` at `0x1800060e1`
- `ntdll!RtlInitializeCriticalSection` at `0x18000621f`
- `ntdll!RtlInitializeCriticalSection` at `0x1800060e1`
- `ntdll!RtlInitializeCriticalSection` at `0x18000621f`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18000610c`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18000610c`

## pseudocode

```c
__int64 __fastcall LsaDbpInitDatabaseServer(int a1)
{
  int v1; // ebx
  _QWORD *v2; // rcx
  __int64 v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  if ( a1 == 1 )
  {
    memset_0(&LsaDbDsStateInfo, 0, 0x70u);
    RtlInitializeCriticalSection(&stru_1800485F0);
    RtlInitializeGenericTableAvl(&stru_180048618, compareLists, allocateEvntlogMap, freeEvntlogMap, 0);
    byte_180048680 = 1;
    LsapGetWellKnownSid(15);
    RtlInitUnicodeString(&LsaDbpSubsystemName, L"LSA");
    AdtpNullSid = 257;
    LsaDbpDsAttInfo = (struct _LSAP_DB_HANDLE *)qword_180047680;
    LsaDbpTrustedDomainList = 0;
    qword_1800480C0 = (__int64)&hMem;
    hMem = &hMem;
    LsapDbExpMakeCacheInvalid(2);
    v1 = LsadbInitializeRegistryParams();
    if ( v1 >= 0 )
    {
      v1 = LsaDbpForestTrustCacheInitialize();
      if ( v1 >= 0 )
      {
        v2 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids);
          v2 = WPP_GLOBAL_Control;
        }
        qword_180048168 = (__int64)&LsaDbpFixupList;
        LsaDbpFixupList = &LsaDbpFixupList;
        if ( (*((_BYTE *)v2 + 28) & 4) != 0 )
          WPP_SF_d(v2[2], 71, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids, 0);
        v1 = LsaDbTrustScannerInitialize();
        if ( v1 >= 0 )
        {
          qword_180048178 = (__int64)&LsapBindingCache;
          LsapBindingCache = (struct _LSAP_BINDING_CACHE_ENTRY *)&LsapBindingCache;
          return (unsigned int)RtlInitializeCriticalSection(&stru_180048180);
        }
      }
    }
  }
  else
  {
    v1 = 0;
    if ( a1 == 2 )
    {
      LsapGetPolicyHandle(&LsaDbpPolicyHandle);
      if ( NtCreateEvent(&LsaDbpLookupStartedEvent, 0x100003u, 0, SynchronizationEvent, 0) >= 0 )
        LsaDbpLookupInitializeWorkQueue();
      v1 = LsapDbQueryInformationPolicy(LsaDbpPolicyHandle, 12, &v4);
      if ( v1 >= 0 )
      {
        DcInRootDomain = LsapCompareDomainNames(v4 + 16, v4 + 32, 0);
        LsaIFree_LSAPR_POLICY_INFORMATION(12);
      }
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800060b0  push    rbx
0x1800060b2  sub     rsp, 30h
0x1800060b6  mov     [rsp+38h+arg_8], 0
0x1800060bf  cmp     ecx, 1
0x1800060c2  jnz     loc_18000622C
0x1800060c8  lea     r8d, [rcx+6Fh]; Size
0x1800060cc  xor     edx, edx; Val
0x1800060ce  lea     rcx, ?LsaDbDsStateInfo@@3U_LSADS_DS_STATE_INFO@@A; void *
0x1800060d5  call    memset_0
0x1800060da  lea     rcx, stru_1800485F0; CriticalSection
0x1800060e1  call    cs:__imp_RtlInitializeCriticalSection
0x1800060e7  lea     r9, freeEvntlogMap; FreeRoutine
0x1800060ee  mov     [rsp+38h+TableContext], 0; TableContext
0x1800060f7  lea     r8, allocateEvntlogMap; AllocateRoutine
0x1800060fe  lea     rdx, compareLists; CompareRoutine
0x180006105  lea     rcx, stru_180048618; Table
0x18000610c  call    cs:__imp_RtlInitializeGenericTableAvl
0x180006112  mov     ecx, 0Fh
0x180006117  mov     cs:byte_180048680, 1
0x18000611e  call    cs:__imp_LsapGetWellKnownSid
0x180006124  lea     rdx, SourceString; "LSA"
0x18000612b  lea     rcx, ?LsaDbpSubsystemName@@3U_UNICODE_STRING@@A; DestinationString
0x180006132  call    cs:__imp_RtlInitUnicodeString
0x180006138  lea     rax, qword_180047680
0x18000613f  mov     cs:AdtpNullSid, 101h
0x180006148  mov     cs:?LsaDbpDsAttInfo@@3PEAU_LSAP_DB_DS_INFO@@EA, rax; _LSAP_DB_DS_INFO * LsaDbpDsAttInfo
0x18000614f  mov     ecx, 2
0x180006154  lea     rax, hMem
0x18000615b  mov     cs:?LsaDbpTrustedDomainList@@3U_LSAP_DB_TRUSTED_DOMAIN_LIST@@A, 0; _LSAP_DB_TRUSTED_DOMAIN_LIST LsaDbpTrustedDomainList
0x180006166  mov     cs:qword_1800480C0, rax
0x18000616d  mov     cs:hMem, rax
0x180006174  call    cs:__imp_LsapDbExpMakeCacheInvalid
0x18000617a  call    ?LsadbInitializeRegistryParams@@YAJXZ; LsadbInitializeRegistryParams(void)
0x18000617f  mov     ebx, eax
0x180006181  test    eax, eax
0x180006183  js      loc_1800062AF
0x180006189  call    ?LsaDbpForestTrustCacheInitialize@@YAJXZ; LsaDbpForestTrustCacheInitialize(void)
0x18000618e  mov     ebx, eax
0x180006190  test    eax, eax
0x180006192  js      loc_1800062AF
0x180006198  mov     rcx, cs:WPP_GLOBAL_Control
0x18000619f  test    byte ptr [rcx+1Ch], 4
0x1800061a3  jz      short loc_1800061C1
0x1800061a5  mov     rcx, [rcx+10h]
0x1800061a9  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x1800061b0  mov     edx, 46h ; 'F'
0x1800061b5  call    WPP_SF_
0x1800061ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061c1  lea     rax, ?LsaDbpFixupList@@3U_LIST_ENTRY@@A; _LIST_ENTRY LsaDbpFixupList
0x1800061c8  mov     cs:qword_180048168, rax
0x1800061cf  mov     cs:?LsaDbpFixupList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY LsaDbpFixupList
0x1800061d6  test    byte ptr [rcx+1Ch], 4
0x1800061da  jz      short loc_1800061F4
0x1800061dc  mov     rcx, [rcx+10h]
0x1800061e0  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x1800061e7  mov     edx, 47h ; 'G'
0x1800061ec  xor     r9d, r9d
0x1800061ef  call    WPP_SF_d
0x1800061f4  call    ?LsaDbTrustScannerInitialize@@YAJXZ; LsaDbTrustScannerInitialize(void)
0x1800061f9  mov     ebx, eax
0x1800061fb  test    eax, eax
0x1800061fd  js      loc_1800062AF
0x180006203  lea     rax, ?LsapBindingCache@@3U_LSAP_LIST@@A; _LSAP_LIST LsapBindingCache
0x18000620a  lea     rcx, stru_180048180; CriticalSection
0x180006211  mov     cs:qword_180048178, rax
0x180006218  mov     cs:?LsapBindingCache@@3U_LSAP_LIST@@A, rax; _LSAP_LIST LsapBindingCache
0x18000621f  call    cs:__imp_RtlInitializeCriticalSection
0x180006225  mov     ebx, eax
0x180006227  jmp     loc_1800062AF
0x18000622c  xor     ebx, ebx
0x18000622e  cmp     ecx, 2
0x180006231  jnz     short loc_1800062AF
0x180006233  lea     rcx, ?LsaDbpPolicyHandle@@3PEAXEA; void * LsaDbpPolicyHandle
0x18000623a  call    cs:__imp_LsapGetPolicyHandle
0x180006240  lea     r9d, [rbx+1]; EventType
0x180006244  mov     byte ptr [rsp+38h+TableContext], bl; InitialState
0x180006248  xor     r8d, r8d; ObjectAttributes
0x18000624b  lea     rcx, ?LsaDbpLookupStartedEvent@@3PEAXEA; EventHandle
0x180006252  mov     edx, 100003h; DesiredAccess
0x180006257  call    cs:__imp_NtCreateEvent
0x18000625d  test    eax, eax
0x18000625f  js      short loc_180006266
0x180006261  call    ?LsaDbpLookupInitializeWorkQueue@@YAJXZ; LsaDbpLookupInitializeWorkQueue(void)
0x180006266  mov     rcx, cs:?LsaDbpPolicyHandle@@3PEAXEA; void * LsaDbpPolicyHandle
0x18000626d  lea     r8, [rsp+38h+arg_8]
0x180006272  mov     edx, 0Ch
0x180006277  call    cs:__imp_LsapDbQueryInformationPolicy
0x18000627d  mov     ebx, eax
0x18000627f  test    eax, eax
0x180006281  js      short loc_1800062AF
0x180006283  mov     rcx, [rsp+38h+arg_8]
0x180006288  xor     r8d, r8d
0x18000628b  lea     rdx, [rcx+20h]
0x18000628f  add     rcx, 10h
0x180006293  call    cs:__imp_LsapCompareDomainNames
0x180006299  mov     rdx, [rsp+38h+arg_8]
0x18000629e  mov     ecx, 0Ch
0x1800062a3  mov     cs:?DcInRootDomain@@3EA, al; uchar DcInRootDomain
0x1800062a9  call    cs:__imp_LsaIFree_LSAPR_POLICY_INFORMATION
0x1800062af  mov     eax, ebx
0x1800062b1  add     rsp, 30h
0x1800062b5  pop     rbx
0x1800062b6  retn
```
