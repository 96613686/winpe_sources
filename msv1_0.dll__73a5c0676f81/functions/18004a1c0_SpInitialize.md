# SpInitialize

- ea: `0x18004a1c0`
- end: `0x18004aaaa`
- name: `SpInitialize`
- size: `2282`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000cba0`
- `0x180019174`
- `0x18001a258`
- `0x18002ee7c`
- `0x18002f014`
- `0x18002fb50`
- `0x180030844`
- `0x180032230`
- `0x180046b98`
- `0x180046fb8`
- `0x18004704c`
- `0x1800488b4`
- `0x180049da8`
- `0x18004a1c0`
- `0x18004aad0`
- `0x18004c940`
- `0x18004cd84`
- `0x180056820`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18004a6a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18004a6ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18004a6a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18004a6ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18004a62f`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18004a62f`
- `NtlmShared!NtlmSharedInitNew` at `0x18004a404`
- `NtlmShared!NtlmSharedInitNew` at `0x18004a404`
- `ntdll!RtlInitializeResource` at `0x18004a297`
- `ntdll!RtlInitializeResource` at `0x18004a2a4`
- `ntdll!RtlInitializeResource` at `0x18004a2b1`
- `ntdll!RtlInitializeResource` at `0x18004a2be`
- `ntdll!RtlInitializeResource` at `0x18004a2cb`
- `ntdll!RtlInitializeResource` at `0x18004a2d8`
- `ntdll!RtlInitializeResource` at `0x18004a2e5`
- `ntdll!RtlInitializeResource` at `0x18004a297`
- `ntdll!RtlInitializeResource` at `0x18004a2a4`
- `ntdll!RtlInitializeResource` at `0x18004a2b1`
- `ntdll!RtlInitializeResource` at `0x18004a2be`
- `ntdll!RtlInitializeResource` at `0x18004a2cb`
- `ntdll!RtlInitializeResource` at `0x18004a2d8`
- `ntdll!RtlInitializeResource` at `0x18004a2e5`
- `ntdll!NtAllocateLocallyUniqueId` at `0x18004a45f`
- `ntdll!NtAllocateLocallyUniqueId` at `0x18004a45f`
- `ntdll!RtlGetNtProductType` at `0x18004a5d7`
- `ntdll!RtlGetNtProductType` at `0x18004a5d7`
- `ntdll!NtQuerySystemInformation` at `0x18004a95d`
- `ntdll!NtQuerySystemInformation` at `0x18004a996`
- `ntdll!NtQuerySystemInformation` at `0x18004a95d`
- `ntdll!NtQuerySystemInformation` at `0x18004a996`
- `ntdll!RtlInitializeCriticalSection` at `0x18004a2f3`
- `ntdll!RtlInitializeCriticalSection` at `0x18004a340`
- `ntdll!RtlInitializeCriticalSection` at `0x18004a9e5`
- `ntdll!RtlInitializeCriticalSection` at `0x18004a2f3`
- `ntdll!RtlInitializeCriticalSection` at `0x18004a340`
- `ntdll!RtlInitializeCriticalSection` at `0x18004a9e5`
- `ntdll!RtlInitializeGenericTable` at `0x18004a9d8`
- `ntdll!RtlInitializeGenericTable` at `0x18004a9d8`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18004a745`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18004a745`
- `ntdll!RtlInitUnicodeString` at `0x18004a7d0`
- `ntdll!RtlInitUnicodeString` at `0x18004a7e6`
- `ntdll!RtlInitUnicodeString` at `0x18004a7d0`
- `ntdll!RtlInitUnicodeString` at `0x18004a7e6`
- `WS2_32!__imp_WSAGetLastError` at `0x18004a927`
- `WS2_32!__imp_WSAGetLastError` at `0x18004a927`
- `WS2_32!__imp_WSAStartup` at `0x18004a90c`
- `WS2_32!__imp_WSAStartup` at `0x18004a90c`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x18004a664`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x18004a664`

## pseudocode

```c
__int64 __fastcall SpInitialize(__int64 a1, __int64 a2, struct _LSA_SECPKG_FUNCTION_TABLE *a3)
{
  NTSTATUS v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  NTSTATUS inited; // eax
  struct NtlmCredIsoApi *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  enum _POLICY_NOTIFICATION_INFORMATION_CLASS v12; // ecx
  unsigned int Error; // eax
  void **v14; // rdx
  const struct _UNICODE_STRING *v15; // rcx
  DWORD nSize; // [rsp+60h] [rbp-5C8h] BYREF
  DWORD v18; // [rsp+64h] [rbp-5C4h] BYREF
  struct _LSA_SECPKG_FUNCTION_TABLE *v19; // [rsp+68h] [rbp-5C0h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-5B8h] BYREF
  struct _UNICODE_STRING v21; // [rsp+80h] [rbp-5A8h] BYREF
  _BYTE v22[40]; // [rsp+90h] [rbp-598h] BYREF
  struct NtlmCredIsoApi *IdentifierAuthority; // [rsp+B8h] [rbp-570h] BYREF
  _BYTE SystemInformation[32]; // [rsp+C0h] [rbp-568h] BYREF
  __int64 v25; // [rsp+E0h] [rbp-548h]
  _OSVERSIONINFOW VersionInformation; // [rsp+100h] [rbp-528h] BYREF
  WSAData WSAData; // [rsp+220h] [rbp-408h] BYREF
  WCHAR Buffer[16]; // [rsp+3C0h] [rbp-268h] BYREF
  WCHAR SourceString[256]; // [rsp+3E0h] [rbp-248h] BYREF

  v19 = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids);
  DestinationString = 0;
  nSize = 16;
  v21 = 0;
  v18 = 256;
  memset_0(&WSAData, 0, sizeof(WSAData));
  memset(v22, 0, sizeof(v22));
  dword_180087A84 = *(_DWORD *)(a2 + 4);
  dword_180087A88 = *(_DWORD *)(a2 + 8);
  NtLmOpenRegistryKeys();
  RtlInitializeResource(&NtLmGlobalCritSect);
  RtlInitializeResource(&NtLmProcessOptionsLock);
  RtlInitializeResource(&NtLmGlobalHostTableLock);
  RtlInitializeResource(&NtLmGlobalIPAddressesLock);
  RtlInitializeResource(&NtLmGlobalHostedTargetsLock);
  RtlInitializeResource(&NtLmGlobalCertCredLock);
  RtlInitializeResource(&NtlmGlobalAllowedTargetsLock);
  v5 = RtlInitializeCriticalSection(&NtLmGlobalIPAddressObserverLock);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 38;
LABEL_8:
      WPP_SF_(v6[2], v7, WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids);
LABEL_9:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_100;
    }
    goto LABEL_100;
  }
  v5 = RtlInitializeCriticalSection(&NtLmGlobalLoopbackContextListLock);
  if ( v5 >= 0 )
  {
    qword_180087A50 = (__int64)&NtLmGlobalLoopbackContextListHead;
    NtLmGlobalLoopbackContextListHead = (__int64)&NtLmGlobalLoopbackContextListHead;
    qword_180087B60 = (__int64)&NtLmProcessOptionsList;
    NtLmProcessOptionsList.Flink = &NtLmProcessOptionsList;
    NtLmState = 1;
    NtLmPackageId = a1;
    NtLmGlobalForever = 0x7FFFFF36D5969FFFLL;
    LsaFunctions = v19;
    *(_DWORD *)v22 = ((unsigned int)dword_180087A84 >> 5) & 1;
    *(_OWORD *)&v22[8] = *(_OWORD *)off_18006E410;
    *(_OWORD *)&v22[24] = *(_OWORD *)off_18006E420;
    inited = NtlmSharedInitNew(v22);
    v5 = inited;
    if ( inited < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_100;
      v10 = 40;
LABEL_18:
      v11 = (unsigned int)inited;
      goto LABEL_19;
    }
    if ( (dword_180087A84 & 0x20) != 0 )
    {
      IdentifierAuthority = 0;
      v5 = NtlmCredIsoIum::Create(v9, &IdentifierAuthority);
      LocalhostNtLmCredIsoObj::IsoObj = IdentifierAuthority;
      if ( v5 < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_100;
        v10 = 41;
        v11 = (unsigned int)v5;
        goto LABEL_19;
      }
    }
    else
    {
      LocalhostNtLmCredIsoObj::IsoObj = (struct NtlmCredIsoApi *)NtLmCredIsoInProc;
    }
    inited = NtAllocateLocallyUniqueId(&NtLmGlobalLuidMachineLogon);
    v5 = inited;
    if ( inited < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_100;
      v10 = 42;
      goto LABEL_18;
    }
    inited = ((__int64 (__fastcall *)(LUID *))LsaFunctions->CreateLogonSession)(&NtLmGlobalLuidMachineLogon);
    v5 = inited;
    if ( inited < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_100;
      v10 = 43;
      goto LABEL_18;
    }
    inited = NtLmDuplicateUnicodeString(&stru_180087A98, a2 + 24);
    v5 = inited;
    if ( inited < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_100;
      v10 = 44;
      goto LABEL_18;
    }
    inited = NtLmDuplicateUnicodeString(&stru_180087AA8, a2 + 40);
    v5 = inited;
    if ( inited < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_100;
      v10 = 45;
      goto LABEL_18;
    }
    if ( *(_QWORD *)(a2 + 16) )
    {
      inited = NtLmDuplicateSid(&Sid1);
      v5 = inited;
      if ( inited < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_100;
        v10 = 46;
        goto LABEL_18;
      }
    }
    if ( !RtlGetNtProductType(&NtLmGlobalNtProductType)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids);
    }
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
    VersionInformation.dwOSVersionInfoSize = 284;
    if ( !GetVersionExW(&VersionInformation)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids);
    }
    inited = LsaIOpenPolicyTrusted(&NtLmGlobalPolicyHandle);
    v5 = inited;
    if ( inited < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_100;
      v10 = 49;
      goto LABEL_18;
    }
    if ( GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
    {
      if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, SourceString, &v18) )
        SourceString[0] = 0;
      LODWORD(IdentifierAuthority) = 0;
      WORD2(IdentifierAuthority) = 1280;
      v5 = RtlAllocateAndInitializeSid(
             (PSID_IDENTIFIER_AUTHORITY)&IdentifierAuthority,
             1u,
             7u,
             0,
             0,
             0,
             0,
             0,
             0,
             0,
             &NtLmGlobalAnonymousSid);
      if ( v5 < 0 )
        goto LABEL_9;
      inited = SspCredentialInitialize();
      v5 = inited;
      if ( inited >= 0 )
      {
        if ( Sid1 )
          NtLmGlobalDomainJoined = 1;
        inited = NtLmQueryGlobals();
        v5 = inited;
        if ( inited >= 0 )
        {
          RtlInitUnicodeString(&DestinationString, Buffer);
          RtlInitUnicodeString(&v21, SourceString);
          inited = NtLmSetPolicyInfo(
                     &v21,
                     &DestinationString,
                     &stru_180087AA8,
                     &stru_180087A98,
                     Sid1,
                     PolicyNotifyAuditEventsInformation,
                     1);
          v5 = inited;
          if ( inited >= 0 )
          {
            inited = LsaApInitializePackage(a1, (_DWORD)v19, 0, 0, 0);
            v5 = inited;
            if ( inited >= 0 )
            {
              inited = NtLmRegisterForPolicyChange(v12);
              v5 = inited;
              if ( inited >= 0 )
              {
                inited = SspGenerateRandomBits(&NtlmGlobalMagicNumber, 16);
                v5 = inited;
                if ( inited >= 0 )
                {
                  NtLmGlobalHasWinsock = 1;
                  if ( WSAStartup(2u, &WSAData) )
                  {
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    {
                      Error = WSAGetLastError();
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        59,
                        WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids,
                        Error);
                    }
                    NtLmGlobalHasWinsock = 0;
                  }
                  NtQuerySystemInformation(SystemKernelDebuggerInformation, &NtLmGlobalKdInfo, 2u, 0);
                  memset_0(SystemInformation, 0, 0x40u);
                  v25 = 0x10000;
                  NtQuerySystemInformation(SystemBasicInformation, SystemInformation, 0x40u, 0);
                  NtLmGlobalLoopbackCounter = v25;
                  NtLmGlobalActiveIPAddressObserverActive = 0;
                  NtLmGlobalIsIPAddressObserverInitialized = 0;
                  RtlInitializeGenericTable(
                    &NtLmGlobalActiveChallengeTable,
                    SspSplayCompare,
                    SspSplayAllocate,
                    SspSplayFree,
                    0);
                  v5 = RtlInitializeCriticalSection(&NtlmGlobalChallengeTrackingLock);
                  if ( v5 >= 0 )
                    v5 = NtLmAllocateAndInitializeServiceSid(v15, v14);
                  else
                    SspDeleteChallengeTracking(-1);
                  goto LABEL_9;
                }
                v6 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                {
                  goto LABEL_100;
                }
                v10 = 58;
              }
              else
              {
                v6 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                {
                  goto LABEL_100;
                }
                v10 = 57;
              }
            }
            else
            {
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_100;
              }
              v10 = 56;
            }
          }
          else
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_100;
            v10 = 55;
          }
        }
        else
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_100;
          v10 = 54;
        }
      }
      else
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_100;
        v10 = 51;
      }
      goto LABEL_18;
    }
    v5 = -1073741534;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_100;
    v10 = 50;
    v11 = 3221225762LL;
LABEL_19:
    WPP_SF_d(v6[2], v10, WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids, v11);
    goto LABEL_9;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 39;
    goto LABEL_8;
  }
LABEL_100:
  if ( v5 < 0 )
  {
    SpShutdown();
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x100) != 0 )
    WPP_SF_(v6[2], 60, WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004a1c0  push    rbx
0x18004a1c2  push    rsi
0x18004a1c3  push    rdi
0x18004a1c4  push    r12
0x18004a1c6  push    r13
0x18004a1c8  push    r14
0x18004a1ca  push    r15
0x18004a1cc  sub     rsp, 5F0h
0x18004a1d3  mov     rax, cs:__security_cookie
0x18004a1da  xor     rax, rsp
0x18004a1dd  mov     [rsp+628h+var_48], rax
0x18004a1e5  mov     [rsp+628h+var_5C0], r8
0x18004a1ea  mov     r13, rdx
0x18004a1ed  mov     r12, rcx
0x18004a1f0  lea     r14, WPP_GLOBAL_Control
0x18004a1f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a1fe  lea     r15, WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids
0x18004a205  cmp     rcx, r14
0x18004a208  jz      short loc_18004A224
0x18004a20a  test    dword ptr [rcx+1Ch], 100h
0x18004a211  jz      short loc_18004A224
0x18004a213  mov     edx, 24h ; '$'
0x18004a218  mov     r8, r15
0x18004a21b  mov     rcx, [rcx+10h]
0x18004a21f  call    WPP_SF_
0x18004a224  xorps   xmm0, xmm0
0x18004a227  movups  xmmword ptr [rsp+628h+DestinationString.Length], xmm0
0x18004a22c  mov     [rsp+628h+nSize], 10h
0x18004a234  movups  xmmword ptr [rsp+628h+var_5A8.Length], xmm0
0x18004a23c  mov     [rsp+628h+var_5C4], 100h
0x18004a244  xor     edx, edx; Val
0x18004a246  mov     r8d, 198h; Size
0x18004a24c  lea     rcx, [rsp+628h+WSAData]; void *
0x18004a254  call    memset_0
0x18004a259  xorps   xmm0, xmm0
0x18004a25c  xor     eax, eax
0x18004a25e  movups  [rsp+628h+var_598], xmm0
0x18004a266  movups  [rsp+628h+var_588], xmm0
0x18004a26e  mov     [rsp+628h+var_578], rax
0x18004a276  mov     eax, [r13+4]
0x18004a27a  mov     cs:dword_180087A84, eax
0x18004a280  mov     eax, [r13+8]
0x18004a284  mov     cs:dword_180087A88, eax
0x18004a28a  call    NtLmOpenRegistryKeys
0x18004a28f  nop
0x18004a290  lea     rcx, NtLmGlobalCritSect; Resource
0x18004a297  call    cs:__imp_RtlInitializeResource
0x18004a29d  lea     rcx, ?NtLmProcessOptionsLock@@3U_RTL_RESOURCE@@A; Resource
0x18004a2a4  call    cs:__imp_RtlInitializeResource
0x18004a2aa  lea     rcx, NtLmGlobalHostTableLock; Resource
0x18004a2b1  call    cs:__imp_RtlInitializeResource
0x18004a2b7  lea     rcx, NtLmGlobalIPAddressesLock; Resource
0x18004a2be  call    cs:__imp_RtlInitializeResource
0x18004a2c4  lea     rcx, NtLmGlobalHostedTargetsLock; Resource
0x18004a2cb  call    cs:__imp_RtlInitializeResource
0x18004a2d1  lea     rcx, NtLmGlobalCertCredLock; Resource
0x18004a2d8  call    cs:__imp_RtlInitializeResource
0x18004a2de  lea     rcx, NtlmGlobalAllowedTargetsLock; Resource
0x18004a2e5  call    cs:__imp_RtlInitializeResource
0x18004a2eb  nop
0x18004a2ec  lea     rcx, NtLmGlobalIPAddressObserverLock; CriticalSection
0x18004a2f3  call    cs:__imp_RtlInitializeCriticalSection
0x18004a2f9  mov     ebx, eax
0x18004a2fb  xor     edi, edi
0x18004a2fd  test    eax, eax
0x18004a2ff  jns     short loc_18004A339
0x18004a301  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a308  cmp     rcx, r14
0x18004a30b  jz      loc_18004AA56
0x18004a311  lea     esi, [rdi+1]
0x18004a314  test    [rcx+1Ch], sil
0x18004a318  jz      loc_18004AA56
0x18004a31e  lea     edx, [rdi+26h]
0x18004a321  mov     r8, r15
0x18004a324  mov     rcx, [rcx+10h]
0x18004a328  call    WPP_SF_
0x18004a32d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a334  jmp     loc_18004AA56
0x18004a339  lea     rcx, NtLmGlobalLoopbackContextListLock; CriticalSection
0x18004a340  call    cs:__imp_RtlInitializeCriticalSection
0x18004a346  mov     ebx, eax
0x18004a348  test    eax, eax
0x18004a34a  jns     short loc_18004A370
0x18004a34c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a353  cmp     rcx, r14
0x18004a356  jz      loc_18004AA56
0x18004a35c  mov     esi, 1
0x18004a361  test    [rcx+1Ch], sil
0x18004a365  jz      loc_18004AA56
0x18004a36b  lea     edx, [rsi+26h]
0x18004a36e  jmp     short loc_18004A321
0x18004a370  lea     rax, NtLmGlobalLoopbackContextListHead
0x18004a377  mov     cs:qword_180087A50, rax
0x18004a37e  mov     cs:NtLmGlobalLoopbackContextListHead, rax
0x18004a385  lea     rax, ?NtLmProcessOptionsList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NtLmProcessOptionsList
0x18004a38c  mov     cs:qword_180087B60, rax
0x18004a393  mov     cs:?NtLmProcessOptionsList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NtLmProcessOptionsList
0x18004a39a  mov     esi, 1
0x18004a39f  mov     cs:NtLmState, esi
0x18004a3a5  mov     cs:NtLmPackageId, r12
0x18004a3ac  mov     dword ptr cs:NtLmGlobalForever+4, 7FFFFF36h
0x18004a3b6  mov     dword ptr cs:NtLmGlobalForever, 0D5969FFFh
0x18004a3c0  mov     rax, [rsp+628h+var_5C0]
0x18004a3c5  mov     cs:LsaFunctions, rax
0x18004a3cc  mov     eax, cs:dword_180087A84
0x18004a3d2  shr     eax, 5
0x18004a3d5  and     eax, esi
0x18004a3d7  mov     dword ptr [rsp+628h+var_598], eax
0x18004a3de  movups  xmm0, xmmword ptr cs:off_18006E410
0x18004a3e5  movups  [rsp+628h+var_598+8], xmm0
0x18004a3ed  movups  xmm1, xmmword ptr cs:off_18006E420
0x18004a3f4  movups  [rsp+628h+var_588+8], xmm1
0x18004a3fc  lea     rcx, [rsp+628h+var_598]
0x18004a404  call    cs:__imp_NtlmSharedInitNew
0x18004a40a  mov     ebx, eax
0x18004a40c  test    eax, eax
0x18004a40e  jns     short loc_18004A441
0x18004a410  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a417  cmp     rcx, r14
0x18004a41a  jz      loc_18004AA56
0x18004a420  test    [rcx+1Ch], sil
0x18004a424  jz      loc_18004AA56
0x18004a42a  lea     edx, [rsi+27h]
0x18004a42d  mov     r9d, eax
0x18004a430  mov     r8, r15
0x18004a433  mov     rcx, [rcx+10h]
0x18004a437  call    WPP_SF_d
0x18004a43c  jmp     loc_18004A32D
0x18004a441  test    byte ptr cs:dword_180087A84, 20h
0x18004a448  jnz     short loc_18004A48C
0x18004a44a  lea     rax, ?NtLmCredIsoInProc@@3VNtlmCredIsoInProc@@A; NtlmCredIsoInProc NtLmCredIsoInProc
0x18004a451  mov     cs:?IsoObj@LocalhostNtLmCredIsoObj@@0PEAVNtlmCredIsoApi@@EA, rax; NtlmCredIsoApi * LocalhostNtLmCredIsoObj::IsoObj
0x18004a458  lea     rcx, NtLmGlobalLuidMachineLogon; LocallyUniqueId
0x18004a45f  call    cs:__imp_NtAllocateLocallyUniqueId
0x18004a465  mov     ebx, eax
0x18004a467  test    eax, eax
0x18004a469  jns     short loc_18004A4DD
0x18004a46b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a472  cmp     rcx, r14
0x18004a475  jz      loc_18004AA56
0x18004a47b  test    [rcx+1Ch], sil
0x18004a47f  jz      loc_18004AA56
0x18004a485  mov     edx, 2Ah ; '*'
0x18004a48a  jmp     short loc_18004A42D
0x18004a48c  mov     [rsp+628h+IdentifierAuthority], rdi
0x18004a494  lea     rdx, [rsp+628h+IdentifierAuthority]; struct NtlmCredIsoApi **
0x18004a49c  call    ?Create@NtlmCredIsoIum@@SAJPEAVNtlmCredIsoApi@@PEAPEAV2@@Z; NtlmCredIsoIum::Create(NtlmCredIsoApi *,NtlmCredIsoApi * *)
0x18004a4a1  mov     ebx, eax
0x18004a4a3  mov     rax, [rsp+628h+IdentifierAuthority]
0x18004a4ab  mov     cs:?IsoObj@LocalhostNtLmCredIsoObj@@0PEAVNtlmCredIsoApi@@EA, rax; NtlmCredIsoApi * LocalhostNtLmCredIsoObj::IsoObj
0x18004a4b2  test    ebx, ebx
0x18004a4b4  jns     short loc_18004A458
0x18004a4b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a4bd  cmp     rcx, r14
0x18004a4c0  jz      loc_18004AA56
0x18004a4c6  test    [rcx+1Ch], sil
0x18004a4ca  jz      loc_18004AA56
0x18004a4d0  mov     edx, 29h ; ')'
0x18004a4d5  mov     r9d, ebx
0x18004a4d8  jmp     loc_18004A430
0x18004a4dd  mov     rax, cs:LsaFunctions
0x18004a4e4  lea     rcx, NtLmGlobalLuidMachineLogon
0x18004a4eb  mov     rax, [rax]
0x18004a4ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a4f3  mov     ebx, eax
0x18004a4f5  test    eax, eax
0x18004a4f7  jns     short loc_18004A51D
0x18004a4f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a500  cmp     rcx, r14
0x18004a503  jz      loc_18004AA56
0x18004a509  test    [rcx+1Ch], sil
0x18004a50d  jz      loc_18004AA56
0x18004a513  mov     edx, 2Bh ; '+'
0x18004a518  jmp     loc_18004A42D
0x18004a51d  lea     rdx, [r13+18h]
0x18004a521  lea     rcx, stru_180087A98
0x18004a528  call    NtLmDuplicateUnicodeString
0x18004a52d  mov     ebx, eax
0x18004a52f  test    eax, eax
0x18004a531  jns     short loc_18004A557
0x18004a533  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a53a  cmp     rcx, r14
0x18004a53d  jz      loc_18004AA56
0x18004a543  test    [rcx+1Ch], sil
0x18004a547  jz      loc_18004AA56
0x18004a54d  mov     edx, 2Ch ; ','
0x18004a552  jmp     loc_18004A42D
0x18004a557  lea     rdx, [r13+28h]
0x18004a55b  lea     rcx, stru_180087AA8
0x18004a562  call    NtLmDuplicateUnicodeString
0x18004a567  mov     ebx, eax
0x18004a569  test    eax, eax
0x18004a56b  jns     short loc_18004A591
0x18004a56d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a574  cmp     rcx, r14
0x18004a577  jz      loc_18004AA56
0x18004a57d  test    [rcx+1Ch], sil
0x18004a581  jz      loc_18004AA56
0x18004a587  mov     edx, 2Dh ; '-'
0x18004a58c  jmp     loc_18004A42D
0x18004a591  mov     rdx, [r13+10h]
0x18004a595  test    rdx, rdx
0x18004a598  jz      short loc_18004A5D0
0x18004a59a  lea     rcx, Sid1
0x18004a5a1  call    NtLmDuplicateSid
0x18004a5a6  mov     ebx, eax
0x18004a5a8  test    eax, eax
0x18004a5aa  jns     short loc_18004A5D0
0x18004a5ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a5b3  cmp     rcx, r14
0x18004a5b6  jz      loc_18004AA56
0x18004a5bc  test    [rcx+1Ch], sil
0x18004a5c0  jz      loc_18004AA56
0x18004a5c6  mov     edx, 2Eh ; '.'
0x18004a5cb  jmp     loc_18004A42D
0x18004a5d0  lea     rcx, NtLmGlobalNtProductType; ProductType
0x18004a5d7  call    cs:__imp_RtlGetNtProductType
0x18004a5dd  test    al, al
0x18004a5df  jnz     short loc_18004A607
0x18004a5e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a5e8  cmp     rcx, r14
0x18004a5eb  jz      short loc_18004A607
0x18004a5ed  test    dword ptr [rcx+1Ch], 200h
0x18004a5f4  jz      short loc_18004A607
0x18004a5f6  mov     edx, 2Fh ; '/'
0x18004a5fb  mov     r8, r15
0x18004a5fe  mov     rcx, [rcx+10h]
0x18004a602  call    WPP_SF_
0x18004a607  xor     edx, edx; Val
0x18004a609  mov     r8d, 118h; Size
0x18004a60f  lea     rcx, [rsp+628h+VersionInformation.dwMajorVersion]; void *
0x18004a617  call    memset_0
0x18004a61c  mov     [rsp+628h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18004a627  lea     rcx, [rsp+628h+VersionInformation]; lpVersionInformation
0x18004a62f  call    cs:__imp_GetVersionExW
0x18004a635  test    eax, eax
0x18004a637  jnz     short loc_18004A65D
0x18004a639  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a640  cmp     rcx, r14
0x18004a643  jz      short loc_18004A65D
0x18004a645  test    dword ptr [rcx+1Ch], 200h
0x18004a64c  jz      short loc_18004A65D
0x18004a64e  lea     edx, [rax+30h]
0x18004a651  mov     r8, r15
0x18004a654  mov     rcx, [rcx+10h]
0x18004a658  call    WPP_SF_
0x18004a65d  lea     rcx, NtLmGlobalPolicyHandle
0x18004a664  call    cs:__imp_LsaIOpenPolicyTrusted
0x18004a66a  mov     ebx, eax
0x18004a66c  test    eax, eax
0x18004a66e  jns     short loc_18004A694
0x18004a670  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a677  cmp     rcx, r14
0x18004a67a  jz      loc_18004AA56
0x18004a680  test    [rcx+1Ch], sil
0x18004a684  jz      loc_18004AA56
0x18004a68a  mov     edx, 31h ; '1'
0x18004a68f  jmp     loc_18004A42D
0x18004a694  lea     r8, [rsp+628h+nSize]; nSize
0x18004a699  lea     rdx, [rsp+628h+Buffer]; lpBuffer
0x18004a6a1  xor     ecx, ecx; NameType
0x18004a6a3  call    cs:__imp_GetComputerNameExW
0x18004a6a9  test    eax, eax
0x18004a6ab  jnz     short loc_18004A6DA
0x18004a6ad  mov     ebx, 0C0000122h
0x18004a6b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a6b9  cmp     rcx, r14
0x18004a6bc  jz      loc_18004AA56
0x18004a6c2  test    [rcx+1Ch], sil
0x18004a6c6  jz      loc_18004AA56
0x18004a6cc  lea     edx, [rax+32h]
0x18004a6cf  mov     r9d, 0C0000122h
0x18004a6d5  jmp     loc_18004A430
0x18004a6da  lea     r8, [rsp+628h+var_5C4]; nSize
0x18004a6df  lea     rdx, [rsp+628h+SourceString]; lpBuffer
0x18004a6e7  mov     ecx, 3; NameType
0x18004a6ec  call    cs:__imp_GetComputerNameExW
0x18004a6f2  test    eax, eax
0x18004a6f4  jnz     short loc_18004A6FE
0x18004a6f6  mov     [rsp+628h+SourceString], di
0x18004a6fe  mov     dword ptr [rsp+628h+IdentifierAuthority], edi
0x18004a705  mov     word ptr [rsp+628h+IdentifierAuthority+4], 500h
0x18004a70f  lea     rax, NtLmGlobalAnonymousSid
0x18004a716  mov     [rsp+628h+Sid], rax; Sid
0x18004a71b  mov     [rsp+628h+SubAuthority7], edi; SubAuthority7
0x18004a71f  mov     [rsp+628h+SubAuthority6], edi; SubAuthority6
0x18004a723  mov     [rsp+628h+SubAuthority5], edi; SubAuthority5
0x18004a727  mov     [rsp+628h+SubAuthority4], edi; SubAuthority4
0x18004a72b  mov     [rsp+628h+SubAuthority3], edi; SubAuthority3
0x18004a72f  mov     [rsp+628h+SubAuthority2], edi; SubAuthority2
0x18004a733  xor     r9d, r9d; SubAuthority1
0x18004a736  lea     r8d, [r9+7]; SubAuthority0
0x18004a73a  mov     dl, sil; SubAuthorityCount
0x18004a73d  lea     rcx, [rsp+628h+IdentifierAuthority]; IdentifierAuthority
0x18004a745  call    cs:__imp_RtlAllocateAndInitializeSid
0x18004a74b  mov     ebx, eax
0x18004a74d  test    eax, eax
0x18004a74f  js      loc_18004A32D
0x18004a755  call    SspCredentialInitialize
0x18004a75a  mov     ebx, eax
  ... truncated ...
```
