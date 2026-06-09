# NlCacheJoinDomainControllerInfo(void)

- ea: `0x180035744`
- end: `0x18003591b`
- name: `?NlCacheJoinDomainControllerInfo@@YAKXZ`
- size: `471`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18007ea48`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x180035744`
- `0x18003b040`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035784`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035784`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180035860`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180035860`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003581c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035901`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003581c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035901`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800357c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800357c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800358ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800358ea`

## string_xrefs

- `0x18003583c`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x18003587d`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x1800358bc`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x1800357bb`: `SYSTEM\CurrentControlSet\Services\Netlogon\JoinDomain`
- `0x1800357d9`: `NlCacheJoinDomainControllerInfo: Failed to open JoinDomain breadcrumb in registry; assuming\n`
- `0x1800357ea`: `NlCacheJoinDomainControllerInfo:   therefore that this is not a post-join scenario.\n`
- `0x180035843`: `NlCacheJoinDCPingThread`
- `0x1800358cf`: `NlCacheJoinDomainControllerInfo: ping thread wait signalled, returning success\n`
- `0x1800358a3`: `NlCacheJoinDomainControllerInfo: ping thread wait timed-out, returning ERROR_NO_SUCH_DOMAIN\n`
- `0x180035890`: `NlCacheJoinDomainControllerInfo: ping thread wait failed, returning ERROR_NO_SUCH_DOMAIN\n`

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
        0x964u,
        v3);
      v4 = NlCacheJoinDCPingThread;
    }
    v5 = WaitForSingleObject(v4, 1000 * dword_1800F82B0);
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
        NlAssertFailed("FALSE", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx", 0x986u, v6);
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
          0x97Bu,
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
0x180035744  mov     [rsp+arg_8], rbx
0x180035749  push    rdi
0x18003574a  sub     rsp, 30h
0x18003574e  cmp     cs:?NlGlobalMemberWorkstation@@3HA, 0; int NlGlobalMemberWorkstation
0x180035755  mov     [rsp+38h+hKey], 0
0x18003575e  jnz     short loc_180035772
0x180035760  mov     edi, 1
0x180035765  mov     cs:?NlGlobalJoinLogicDone@@3HA, edi; int NlGlobalJoinLogicDone
0x18003576b  xor     eax, eax
0x18003576d  jmp     loc_18003590F
0x180035772  cmp     cs:?NlGlobalJoinLogicDone@@3HA, 0; int NlGlobalJoinLogicDone
0x180035779  jnz     short loc_18003576B
0x18003577b  lea     rcx, ?NlDcCritSect@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180035782  xor     ebx, ebx
0x180035784  call    cs:__imp_EnterCriticalSection
0x18003578b  nop     dword ptr [rax+rax+00h]
0x180035790  cmp     cs:?NlGlobalJoinLogicDone@@3HA, ebx; int NlGlobalJoinLogicDone
0x180035796  lea     edi, [rbx+1]
0x180035799  jnz     loc_1800358E0
0x18003579f  cmp     cs:?NlCacheJoinDCPingThread@@3PEAXEA, rbx; void * NlCacheJoinDCPingThread
0x1800357a6  jnz     short loc_180035815
0x1800357a8  lea     rax, [rsp+38h+hKey]
0x1800357ad  mov     r9d, 2000000h; samDesired
0x1800357b3  xor     r8d, r8d; ulOptions
0x1800357b6  mov     [rsp+38h+phkResult], rax; phkResult
0x1800357bb  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x1800357c2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800357c9  call    cs:__imp_RegOpenKeyExW
0x1800357d0  nop     dword ptr [rax+rax+00h]
0x1800357d5  test    eax, eax
0x1800357d7  jz      short loc_180035806
0x1800357d9  lea     rdx, aNlcachejoindom; "NlCacheJoinDomainControllerInfo: Failed"...
0x1800357e0  mov     ecx, 100h; unsigned int
0x1800357e5  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800357ea  lea     rdx, aNlcachejoindom_3; "NlCacheJoinDomainControllerInfo:   ther"...
0x1800357f1  mov     ecx, 100h; unsigned int
0x1800357f6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800357fb  mov     cs:?NlGlobalJoinLogicDone@@3HA, edi; int NlGlobalJoinLogicDone
0x180035801  jmp     loc_1800358E0
0x180035806  call    ?NlStartJoinDCPingThreadIfNecessary@@YAKXZ; NlStartJoinDCPingThreadIfNecessary(void)
0x18003580b  mov     ebx, eax
0x18003580d  test    eax, eax
0x18003580f  jnz     loc_1800358E0
0x180035815  lea     rcx, ?NlDcCritSect@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003581c  call    cs:__imp_LeaveCriticalSection
0x180035823  nop     dword ptr [rax+rax+00h]
0x180035828  mov     rcx, cs:?NlCacheJoinDCPingThread@@3PEAXEA; void * NlCacheJoinDCPingThread
0x18003582f  xor     edi, edi
0x180035831  test    rcx, rcx
0x180035834  jnz     short loc_180035856
0x180035836  mov     r8d, 964h; unsigned int
0x18003583c  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180035843  lea     rcx, aNlcachejoindcp; "NlCacheJoinDCPingThread"
0x18003584a  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18003584f  mov     rcx, cs:?NlCacheJoinDCPingThread@@3PEAXEA; hHandle
0x180035856  imul    edx, cs:dword_1800F82B0, 3E8h; dwMilliseconds
0x180035860  call    cs:__imp_WaitForSingleObject
0x180035867  nop     dword ptr [rax+rax+00h]
0x18003586c  test    eax, eax
0x18003586e  jz      short loc_1800358AC
0x180035870  cmp     eax, 102h
0x180035875  jz      short loc_18003589E
0x180035877  mov     r8d, 986h; unsigned int
0x18003587d  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180035884  lea     rcx, aFalse; "FALSE"
0x18003588b  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180035890  lea     rdx, aNlcachejoindom_2; "NlCacheJoinDomainControllerInfo: ping t"...
0x180035897  mov     ebx, 54Bh
0x18003589c  jmp     short loc_1800358D6
0x18003589e  mov     ebx, 54Bh
0x1800358a3  lea     rdx, aNlcachejoindom_1; "NlCacheJoinDomainControllerInfo: ping t"...
0x1800358aa  jmp     short loc_1800358D6
0x1800358ac  xor     ebx, ebx
0x1800358ae  cmp     cs:?NlGlobalJoinLogicDone@@3HA, ebx; int NlGlobalJoinLogicDone
0x1800358b4  jnz     short loc_1800358CF
0x1800358b6  mov     r8d, 97Bh; unsigned int
0x1800358bc  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800358c3  lea     rcx, aNlglobaljoinlo; "NlGlobalJoinLogicDone"
0x1800358ca  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800358cf  lea     rdx, aNlcachejoindom_0; "NlCacheJoinDomainControllerInfo: ping t"...
0x1800358d6  mov     ecx, 100h; unsigned int
0x1800358db  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800358e0  mov     rcx, [rsp+38h+hKey]; hKey
0x1800358e5  test    rcx, rcx
0x1800358e8  jz      short loc_1800358F6
0x1800358ea  call    cs:__imp_RegCloseKey
0x1800358f1  nop     dword ptr [rax+rax+00h]
0x1800358f6  test    edi, edi
0x1800358f8  jz      short loc_18003590D
0x1800358fa  lea     rcx, ?NlDcCritSect@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180035901  call    cs:__imp_LeaveCriticalSection
0x180035908  nop     dword ptr [rax+rax+00h]
0x18003590d  mov     eax, ebx
0x18003590f  mov     rbx, [rsp+38h+arg_8]
0x180035914  add     rsp, 30h
0x180035918  pop     rdi
0x180035919  retn
```
