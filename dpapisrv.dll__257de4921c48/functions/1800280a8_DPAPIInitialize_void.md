# DPAPIInitialize(void)

- ea: `0x1800280a8`
- end: `0x180028338`
- name: `?DPAPIInitialize@@YAKXZ`
- size: `656`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180028340`

## callees

- `0x180007f10`
- `0x18000fd40`
- `0x180023d84`
- `0x1800280a8`
- `0x1800283c4`
- `0x18002c4ac`
- `0x18003576c`
- `0x180035868`
- `0x1800367f4`
- `0x18003b474`
- `0x18003b5a4`
- `0x18003baa0`

## import_xrefs

- `RPCRT4!RpcServerRegisterIf3` at `0x180028214`
- `RPCRT4!RpcServerRegisterIf3` at `0x180028268`
- `RPCRT4!RpcServerRegisterIf3` at `0x180028214`
- `RPCRT4!RpcServerRegisterIf3` at `0x180028268`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180028177`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x1800281ba`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180028177`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x1800281ba`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x180028136`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x180028136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800280e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800280e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002830f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002830f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800280d9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800280d9`

## string_xrefs

- `0x180028106`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\dpapi.cpp`
- `0x1800282a7`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\dpapi.cpp`

## pseudocode

```c
__int64 DPAPIInitialize(void)
{
  DWORD LastError; // eax
  __int64 v1; // r9
  const char *v2; // rdx
  unsigned int v3; // ebx
  __int64 v4; // rcx
  RPC_STATUS v5; // eax
  RPC_STATUS v6; // eax
  signed int v7; // eax
  const char *v8; // r8
  unsigned int v9; // ebx
  BeforeKeyRotation *v10; // rcx
  unsigned int started; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp+8h] BYREF

  SecurityDescriptor = 0;
  g_fDPAPIInitialized = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;AC)(A;;GR;;;S-1-15-3-1024-3203351429-212044"
           "3784-2872670797-1918958302-2829055647-4275794519-765664414-2751773334)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    LastError = GetLastError();
    v1 = 137;
    v2 = "dwLastError";
    v3 = LastError;
LABEL_3:
    v4 = LastError;
LABEL_4:
    DebugTraceError(v4, v2, "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\dpapi.cpp", v1);
    goto LABEL_31;
  }
  qmemcpy(&DPAPITokenSource, "DPAPI", 5);
  AllocateLocallyUniqueId(&Luid);
  FMyProviderCacheInit();
  InitializeGlobals();
  if ( !(unsigned int)InitializeKeyManagement() )
  {
    v3 = -1073741801;
    goto LABEL_31;
  }
  v5 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, (RPC_WSTR)L"protected_storage", SecurityDescriptor);
  v3 = 0;
  if ( v5 != 1740 )
    v3 = v5;
  if ( v3 )
  {
    v1 = 166;
LABEL_11:
    v2 = "status";
LABEL_12:
    v4 = v3;
    goto LABEL_4;
  }
  v6 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncacn_np", 0xAu, (RPC_WSTR)L"\\PIPE\\protected_storage", 0);
  v3 = 0;
  if ( v6 != 1740 )
    v3 = v6;
  if ( v3 )
  {
    v1 = 183;
    goto LABEL_11;
  }
  LastError = RpcServerRegisterIf3(qword_18003F8C0, 0, 0, 33, 1234, 0, ProtectCallback, SecurityDescriptor);
  v3 = LastError;
  if ( LastError )
  {
    v1 = 204;
LABEL_19:
    v2 = "status";
    goto LABEL_3;
  }
  LastError = RpcServerRegisterIf3(qword_18003F4E0, 0, 0, 33, 1234, 0, ProtectCallback, 0);
  v3 = LastError;
  if ( LastError )
  {
    v1 = 224;
    goto LABEL_19;
  }
  v7 = SIDKeyEnableLRpcInterface();
  v9 = v7;
  if ( v7 < 0 )
  {
    SidKeyDebugTraceError(v7, "hr", v8, 0x1B1u);
    DebugTraceError(v9, "ntStatus", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\dpapi.cpp", 232);
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Backup_Key_Rotation>::GetImpl'::`2'::impl) )
  {
    v3 = 0;
    if ( !(unsigned int)IsDomainController() )
      goto LABEL_30;
    started = StartBackupKeyServer();
  }
  else
  {
    started = BeforeKeyRotation::StartBackupKeyServer(v10);
  }
  v3 = started;
  if ( started )
  {
    v1 = 263;
    v2 = "dwLastError";
    goto LABEL_12;
  }
LABEL_30:
  g_fDPAPIInitialized = 1;
LABEL_31:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( !g_fDPAPIInitialized )
    DPAPIShutdown();
  return v3;
}

```

## disassembly

```asm
0x1800280a8  mov     [rsp+arg_8], rbx
0x1800280ad  push    r15
0x1800280af  sub     rsp, 40h
0x1800280b3  xor     r9d, r9d; SecurityDescriptorSize
0x1800280b6  mov     [rsp+48h+SecurityDescriptor], 0
0x1800280bf  lea     r8, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x1800280c4  mov     cs:?g_fDPAPIInitialized@@3HA, 0; int g_fDPAPIInitialized
0x1800280ce  lea     rcx, StringSecurityDescriptor; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x1800280d5  lea     edx, [r9+1]; StringSDRevision
0x1800280d9  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800280e0  nop     dword ptr [rax+rax+00h]
0x1800280e5  test    eax, eax
0x1800280e7  jnz     short loc_180028117
0x1800280e9  call    cs:__imp_GetLastError
0x1800280f0  nop     dword ptr [rax+rax+00h]
0x1800280f5  mov     r9d, 89h
0x1800280fb  lea     rdx, aDwlasterror; "dwLastError"
0x180028102  mov     ebx, eax
0x180028104  mov     ecx, eax
0x180028106  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002810d  call    DebugTraceError
0x180028112  jmp     loc_180028305
0x180028117  mov     eax, dword ptr cs:aDpapi; "DPAPI"
0x18002811d  lea     rcx, Luid; Luid
0x180028124  mov     cs:?DPAPITokenSource@@3U_TOKEN_SOURCE@@A, eax; _TOKEN_SOURCE DPAPITokenSource
0x18002812a  mov     al, byte ptr cs:aDpapi+4; "I"
0x180028130  mov     cs:byte_18004C73C, al
0x180028136  call    cs:__imp_AllocateLocallyUniqueId
0x18002813d  nop     dword ptr [rax+rax+00h]
0x180028142  call    FMyProviderCacheInit
0x180028147  call    ?InitializeGlobals@@YAKXZ; InitializeGlobals(void)
0x18002814c  call    ?InitializeKeyManagement@@YAHXZ; InitializeKeyManagement(void)
0x180028151  test    eax, eax
0x180028153  jnz     short loc_18002815F
0x180028155  mov     ebx, 0C0000017h
0x18002815a  jmp     loc_180028305
0x18002815f  mov     r9, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x180028164  lea     r8, Endpoint; "protected_storage"
0x18002816b  mov     edx, 0Ah; MaxCalls
0x180028170  lea     rcx, Protseq; "ncalrpc"
0x180028177  call    cs:__imp_RpcServerUseProtseqEpW
0x18002817e  nop     dword ptr [rax+rax+00h]
0x180028183  xor     ebx, ebx
0x180028185  cmp     eax, 6CCh
0x18002818a  cmovnz  ebx, eax
0x18002818d  test    ebx, ebx
0x18002818f  jz      short loc_1800281A5
0x180028191  mov     r9d, 0A6h
0x180028197  lea     rdx, aStatus_0; "status"
0x18002819e  mov     ecx, ebx
0x1800281a0  jmp     loc_180028106
0x1800281a5  xor     r9d, r9d; SecurityDescriptor
0x1800281a8  lea     r8, aPipeProtectedS; "\\PIPE\\protected_storage"
0x1800281af  lea     rcx, aNcacnNp; "ncacn_np"
0x1800281b6  lea     edx, [r9+0Ah]; MaxCalls
0x1800281ba  call    cs:__imp_RpcServerUseProtseqEpW
0x1800281c1  nop     dword ptr [rax+rax+00h]
0x1800281c6  xor     ebx, ebx
0x1800281c8  cmp     eax, 6CCh
0x1800281cd  cmovnz  ebx, eax
0x1800281d0  test    ebx, ebx
0x1800281d2  jz      short loc_1800281DC
0x1800281d4  mov     r9d, 0B7h
0x1800281da  jmp     short loc_180028197
0x1800281dc  mov     rax, [rsp+48h+SecurityDescriptor]
0x1800281e1  lea     r15, ?ProtectCallback@@YAJPEAX0@Z; ProtectCallback(void *,void *)
0x1800281e8  mov     [rsp+48h+var_10], rax
0x1800281ed  lea     rcx, qword_18003F8C0
0x1800281f4  mov     [rsp+48h+var_18], r15
0x1800281f9  mov     r9d, 21h ; '!'
0x1800281ff  mov     [rsp+48h+var_20], 0
0x180028207  xor     r8d, r8d
0x18002820a  xor     edx, edx
0x18002820c  mov     [rsp+48h+var_28], 4D2h
0x180028214  call    cs:__imp_RpcServerRegisterIf3
0x18002821b  nop     dword ptr [rax+rax+00h]
0x180028220  mov     ebx, eax
0x180028222  test    eax, eax
0x180028224  jz      short loc_180028238
0x180028226  mov     r9d, 0CCh
0x18002822c  lea     rdx, aStatus_0; "status"
0x180028233  jmp     loc_180028104
0x180028238  mov     [rsp+48h+var_10], 0
0x180028241  lea     rcx, qword_18003F4E0
0x180028248  mov     [rsp+48h+var_18], r15
0x18002824d  mov     r9d, 21h ; '!'
0x180028253  mov     [rsp+48h+var_20], 0
0x18002825b  xor     r8d, r8d
0x18002825e  xor     edx, edx
0x180028260  mov     [rsp+48h+var_28], 4D2h
0x180028268  call    cs:__imp_RpcServerRegisterIf3
0x18002826f  nop     dword ptr [rax+rax+00h]
0x180028274  mov     ebx, eax
0x180028276  test    eax, eax
0x180028278  jz      short loc_180028282
0x18002827a  mov     r9d, 0E0h
0x180028280  jmp     short loc_18002822C
0x180028282  call    ?SIDKeyEnableLRpcInterface@@YAJXZ; SIDKeyEnableLRpcInterface(void)
0x180028287  mov     ebx, eax
0x180028289  test    eax, eax
0x18002828b  jns     short loc_1800282BC
0x18002828d  mov     r9d, 1B1h; unsigned int
0x180028293  lea     rdx, aHr; "hr"
0x18002829a  mov     ecx, eax; unsigned int
0x18002829c  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800282a1  mov     r9d, 0E8h
0x1800282a7  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800282ae  lea     rdx, aNtstatus; "ntStatus"
0x1800282b5  mov     ecx, ebx
0x1800282b7  call    DebugTraceError
0x1800282bc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation> `wil::Feature<__WilFeatureTraits_Feature_Backup_Key_Rotation>::GetImpl(void)'::`2'::impl
0x1800282c3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Key_Rotation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Key_Rotation>::__private_IsEnabled(void)
0x1800282c8  test    al, al
0x1800282ca  jz      short loc_1800282DE
0x1800282cc  xor     ebx, ebx
0x1800282ce  call    IsDomainController
0x1800282d3  test    eax, eax
0x1800282d5  jz      short loc_1800282FB
0x1800282d7  call    ?StartBackupKeyServer@@YAKXZ; StartBackupKeyServer(void)
0x1800282dc  jmp     short loc_1800282E3
0x1800282de  call    ?StartBackupKeyServer@BeforeKeyRotation@@YAKXZ; BeforeKeyRotation::StartBackupKeyServer(void)
0x1800282e3  mov     ebx, eax
0x1800282e5  test    eax, eax
0x1800282e7  jz      short loc_1800282FB
0x1800282e9  mov     r9d, 107h
0x1800282ef  lea     rdx, aDwlasterror; "dwLastError"
0x1800282f6  jmp     loc_18002819E
0x1800282fb  mov     cs:?g_fDPAPIInitialized@@3HA, 1; int g_fDPAPIInitialized
0x180028305  mov     rcx, [rsp+48h+SecurityDescriptor]; hMem
0x18002830a  test    rcx, rcx
0x18002830d  jz      short loc_18002831B
0x18002830f  call    cs:__imp_LocalFree
0x180028316  nop     dword ptr [rax+rax+00h]
0x18002831b  cmp     cs:?g_fDPAPIInitialized@@3HA, 0; int g_fDPAPIInitialized
0x180028322  jnz     short loc_180028329
0x180028324  call    DPAPIShutdown
0x180028329  mov     eax, ebx
0x18002832b  mov     rbx, [rsp+48h+arg_8]
0x180028330  add     rsp, 40h
0x180028334  pop     r15
0x180028336  retn
```
