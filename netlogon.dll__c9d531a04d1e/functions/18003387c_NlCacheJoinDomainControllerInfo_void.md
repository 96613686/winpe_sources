# NlCacheJoinDomainControllerInfo(void)

- ea: `0x18003387c`
- end: `0x180033a2e`
- name: `?NlCacheJoinDomainControllerInfo@@YAKXZ`
- size: `434`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180078f00`

## callees

- `0x180007278`
- `0x18000d710`
- `0x18003387c`
- `0x180038dd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800338bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800338bc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180033986`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180033986`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033948`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033a1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033948`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033a1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800338fb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800338fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033a0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033a0a`

## string_xrefs

- `0x180033962`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x18003399d`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x1800339dc`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x1800338ed`: `SYSTEM\CurrentControlSet\Services\Netlogon\JoinDomain`
- `0x180033905`: `NlCacheJoinDomainControllerInfo: Failed to open JoinDomain breadcrumb in registry; assuming\n`
- `0x180033916`: `NlCacheJoinDomainControllerInfo:   therefore that this is not a post-join scenario.\n`
- `0x180033969`: `NlCacheJoinDCPingThread`
- `0x1800339ef`: `NlCacheJoinDomainControllerInfo: ping thread wait signalled, returning success\n`
- `0x1800339c3`: `NlCacheJoinDomainControllerInfo: ping thread wait timed-out, returning ERROR_NO_SUCH_DOMAIN\n`
- `0x1800339b0`: `NlCacheJoinDomainControllerInfo: ping thread wait failed, returning ERROR_NO_SUCH_DOMAIN\n`

## pseudocode

```c
__int64 NlCacheJoinDomainControllerInfo(void)
{
  unsigned int started; // ebx
  int v2; // edi
  char *v3; // r9
  HANDLE v4; // rcx
  DWORD v5; // eax
  char *v6; // r9
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  if ( !NlGlobalMemberWorkstation )
  {
    NlGlobalJoinLogicDone = 1;
    return 0;
  }
  if ( NlGlobalJoinLogicDone )
    return 0;
  started = 0;
  EnterCriticalSection(&NlDcCritSect);
  v2 = 1;
  if ( !NlGlobalJoinLogicDone )
  {
    if ( !NlCacheJoinDCPingThread )
    {
      if ( RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\Netlogon\\JoinDomain",
             0,
             0x2000000u,
             &hKey) )
      {
        NlPrintRoutine(
          0x100u,
          L"NlCacheJoinDomainControllerInfo: Failed to open JoinDomain breadcrumb in registry; assuming\n");
        NlPrintRoutine(0x100u, L"NlCacheJoinDomainControllerInfo:   therefore that this is not a post-join scenario.\n");
        NlGlobalJoinLogicDone = 1;
        goto LABEL_19;
      }
      started = NlStartJoinDCPingThreadIfNecessary();
      if ( started )
        goto LABEL_19;
    }
    LeaveCriticalSection(&NlDcCritSect);
    v4 = NlCacheJoinDCPingThread;
    v2 = 0;
    if ( !NlCacheJoinDCPingThread )
    {
      NlAssertFailed(
        "NlCacheJoinDCPingThread",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
        2404,
        v3);
      v4 = NlCacheJoinDCPingThread;
    }
    v5 = WaitForSingleObject(v4, 1000 * dword_1800F12B0);
    if ( v5 )
    {
      if ( v5 == 258 )
      {
        started = 1355;
        NlPrintRoutine(
          0x100u,
          L"NlCacheJoinDomainControllerInfo: ping thread wait timed-out, returning ERROR_NO_SUCH_DOMAIN\n");
      }
      else
      {
        NlAssertFailed("FALSE", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx", 2438, v6);
        started = 1355;
        NlPrintRoutine(
          0x100u,
          L"NlCacheJoinDomainControllerInfo: ping thread wait failed, returning ERROR_NO_SUCH_DOMAIN\n");
      }
    }
    else
    {
      started = 0;
      if ( !NlGlobalJoinLogicDone )
        NlAssertFailed(
          "NlGlobalJoinLogicDone",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
          2427,
          v6);
      NlPrintRoutine(0x100u, L"NlCacheJoinDomainControllerInfo: ping thread wait signalled, returning success\n");
    }
  }
LABEL_19:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v2 )
    LeaveCriticalSection(&NlDcCritSect);
  return started;
}

```

## disassembly

```asm
0x18003387c  mov     [rsp+arg_8], rbx
0x180033881  push    rdi
0x180033882  sub     rsp, 30h
0x180033886  cmp     cs:?NlGlobalMemberWorkstation@@3HA, 0; int NlGlobalMemberWorkstation
0x18003388d  mov     [rsp+38h+hKey], 0
0x180033896  jnz     short loc_1800338AA
0x180033898  mov     edi, 1
0x18003389d  mov     cs:?NlGlobalJoinLogicDone@@3HA, edi; int NlGlobalJoinLogicDone
0x1800338a3  xor     eax, eax
0x1800338a5  jmp     loc_180033A23
0x1800338aa  cmp     cs:?NlGlobalJoinLogicDone@@3HA, 0; int NlGlobalJoinLogicDone
0x1800338b1  jnz     short loc_1800338A3
0x1800338b3  lea     rcx, ?NlDcCritSect@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800338ba  xor     ebx, ebx
0x1800338bc  call    cs:__imp_EnterCriticalSection
0x1800338c2  cmp     cs:?NlGlobalJoinLogicDone@@3HA, ebx; int NlGlobalJoinLogicDone
0x1800338c8  lea     edi, [rbx+1]
0x1800338cb  jnz     loc_180033A00
0x1800338d1  cmp     cs:?NlCacheJoinDCPingThread@@3PEAXEA, rbx; void * NlCacheJoinDCPingThread
0x1800338d8  jnz     short loc_180033941
0x1800338da  lea     rax, [rsp+38h+hKey]
0x1800338df  mov     r9d, 2000000h; samDesired
0x1800338e5  xor     r8d, r8d; ulOptions
0x1800338e8  mov     [rsp+38h+phkResult], rax; phkResult
0x1800338ed  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x1800338f4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800338fb  call    cs:__imp_RegOpenKeyExW
0x180033901  test    eax, eax
0x180033903  jz      short loc_180033932
0x180033905  lea     rdx, aNlcachejoindom; "NlCacheJoinDomainControllerInfo: Failed"...
0x18003390c  mov     ecx, 100h; unsigned int
0x180033911  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180033916  lea     rdx, aNlcachejoindom_3; "NlCacheJoinDomainControllerInfo:   ther"...
0x18003391d  mov     ecx, 100h; unsigned int
0x180033922  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180033927  mov     cs:?NlGlobalJoinLogicDone@@3HA, edi; int NlGlobalJoinLogicDone
0x18003392d  jmp     loc_180033A00
0x180033932  call    ?NlStartJoinDCPingThreadIfNecessary@@YAKXZ; NlStartJoinDCPingThreadIfNecessary(void)
0x180033937  mov     ebx, eax
0x180033939  test    eax, eax
0x18003393b  jnz     loc_180033A00
0x180033941  lea     rcx, ?NlDcCritSect@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180033948  call    cs:__imp_LeaveCriticalSection
0x18003394e  mov     rcx, cs:?NlCacheJoinDCPingThread@@3PEAXEA; void * NlCacheJoinDCPingThread
0x180033955  xor     edi, edi
0x180033957  test    rcx, rcx
0x18003395a  jnz     short loc_18003397C
0x18003395c  mov     r8d, 964h; unsigned int
0x180033962  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180033969  lea     rcx, aNlcachejoindcp; "NlCacheJoinDCPingThread"
0x180033970  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180033975  mov     rcx, cs:?NlCacheJoinDCPingThread@@3PEAXEA; hHandle
0x18003397c  imul    edx, cs:dword_1800F12B0, 3E8h; dwMilliseconds
0x180033986  call    cs:__imp_WaitForSingleObject
0x18003398c  test    eax, eax
0x18003398e  jz      short loc_1800339CC
0x180033990  cmp     eax, 102h
0x180033995  jz      short loc_1800339BE
0x180033997  mov     r8d, 986h; unsigned int
0x18003399d  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800339a4  lea     rcx, aFalse; "FALSE"
0x1800339ab  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800339b0  lea     rdx, aNlcachejoindom_2; "NlCacheJoinDomainControllerInfo: ping t"...
0x1800339b7  mov     ebx, 54Bh
0x1800339bc  jmp     short loc_1800339F6
0x1800339be  mov     ebx, 54Bh
0x1800339c3  lea     rdx, aNlcachejoindom_1; "NlCacheJoinDomainControllerInfo: ping t"...
0x1800339ca  jmp     short loc_1800339F6
0x1800339cc  xor     ebx, ebx
0x1800339ce  cmp     cs:?NlGlobalJoinLogicDone@@3HA, ebx; int NlGlobalJoinLogicDone
0x1800339d4  jnz     short loc_1800339EF
0x1800339d6  mov     r8d, 97Bh; unsigned int
0x1800339dc  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800339e3  lea     rcx, aNlglobaljoinlo; "NlGlobalJoinLogicDone"
0x1800339ea  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800339ef  lea     rdx, aNlcachejoindom_0; "NlCacheJoinDomainControllerInfo: ping t"...
0x1800339f6  mov     ecx, 100h; unsigned int
0x1800339fb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180033a00  mov     rcx, [rsp+38h+hKey]; hKey
0x180033a05  test    rcx, rcx
0x180033a08  jz      short loc_180033A10
0x180033a0a  call    cs:__imp_RegCloseKey
0x180033a10  test    edi, edi
0x180033a12  jz      short loc_180033A21
0x180033a14  lea     rcx, ?NlDcCritSect@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180033a1b  call    cs:__imp_LeaveCriticalSection
0x180033a21  mov     eax, ebx
0x180033a23  mov     rbx, [rsp+38h+arg_8]
0x180033a28  add     rsp, 30h
0x180033a2c  pop     rdi
0x180033a2d  retn
```
