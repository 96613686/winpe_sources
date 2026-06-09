# HandleConfigChange

- ea: `0x18002d5b0`
- end: `0x18002d6f2`
- name: `HandleConfigChange`
- size: `322`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x18002c090`
- `0x18002c120`
- `0x18002c980`
- `0x18002d290`

## callees

- `0x180004aa8`
- `0x180012338`
- `0x18001bf58`
- `0x18001e654`
- `0x18002d5b0`
- `0x180030c2c`
- `0x180030ea0`
- `0x180036f4c`
- `0x18007a4ec`
- `0x18007c9f0`

## import_xrefs

- `DNSAPI!Reg_ReadGlobalsEx` at `0x18002d665`
- `DNSAPI!Reg_ReadGlobalsEx` at `0x18002d665`
- `DNSAPI!FlushDnsPolicyUnreachableStatus` at `0x18002d62a`
- `DNSAPI!FlushDnsPolicyUnreachableStatus` at `0x18002d62a`
- `DNSAPI!DnsUpdateMachinePresence` at `0x18002d630`
- `DNSAPI!DnsUpdateMachinePresence` at `0x18002d630`
- `DNSAPI!DelaySortDAServerlist` at `0x18002d6b3`
- `DNSAPI!DelaySortDAServerlist` at `0x18002d6b3`
- `DNSAPI!DnsNotifyProxyConfigChangePrivate` at `0x18002d6ca`
- `DNSAPI!DnsNotifyProxyConfigChangePrivate` at `0x18002d6ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d69f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d69f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d5e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d5e6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002d5ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002d636`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002d5ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002d636`

## pseudocode

```c
__int64 __fastcall HandleConfigChange(int a1, int a2, unsigned int a3)
{
  __int64 v6; // rcx
  int v7; // edx
  int v8; // ecx
  int v9; // r8d
  __int64 result; // rax

  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_sdd(a1, a2, a3, a1, a2, a3);
  EnterCriticalSection(&g_csCache);
  g_CurrentCacheTime = GetTickCount64() / 0x3E8;
  UpdateNetworkInfo(0, 0);
  UpdateNetworkInfo(0, 1);
  FlushDnsPolicyUnreachableStatus();
  DnsUpdateMachinePresence();
  GetTickCount64();
  if ( a2 )
    Cache_Flush(1);
  if ( a3 == 2 || a3 == 7 )
  {
    v6 = 4;
  }
  else
  {
    if ( a3 != 8 )
      goto LABEL_11;
    v6 = 1;
  }
  Reg_ReadGlobalsEx(v6, 0);
  IncrementGlobalCountersProxyCacheVersion();
LABEL_11:
  Mcast_Update(a3);
  _InterlockedExchange(&g_TraceOnceState, 0);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_sdl(v8, v7, v9, a1, a2, a3);
  LeaveCriticalSection(&g_csCache);
  if ( a3 == 5 )
    mDns_HandleNetworkChange();
  DelaySortDAServerlist();
  UnreachableServerCache_CleanupEntries(0);
  if ( a3 == 2 || a3 == 8 )
    DnsNotifyProxyConfigChangePrivate();
  result = a3 - 7;
  if ( (unsigned int)result <= 1 )
    return areg_AlertOrStartRegThread(1);
  return result;
}

```

## disassembly

```asm
0x18002d5b0  mov     rax, rsp
0x18002d5b3  mov     [rax+8], rbx
0x18002d5b7  mov     [rax+10h], rsi
0x18002d5bb  push    rdi
0x18002d5bc  sub     rsp, 30h
0x18002d5c0  mov     ebx, r8d
0x18002d5c3  mov     edi, edx
0x18002d5c5  mov     rsi, rcx
0x18002d5c8  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002d5cf  jz      short loc_18002D5DF
0x18002d5d1  mov     [rax-10h], ebx
0x18002d5d4  mov     r9, rcx
0x18002d5d7  mov     [rax-18h], edx
0x18002d5da  call    WPP_SF_sdd
0x18002d5df  lea     rcx, g_csCache; lpCriticalSection
0x18002d5e6  call    cs:__imp_EnterCriticalSection
0x18002d5ec  call    cs:__imp_GetTickCount64
0x18002d5f2  mov     rcx, rax
0x18002d5f5  mov     rax, 624DD2F1A9FBE77h
0x18002d5ff  mul     rcx
0x18002d602  sub     rcx, rdx
0x18002d605  shr     rcx, 1
0x18002d608  add     rcx, rdx
0x18002d60b  xor     edx, edx
0x18002d60d  shr     rcx, 9
0x18002d611  mov     cs:g_CurrentCacheTime, ecx
0x18002d617  xor     ecx, ecx
0x18002d619  call    UpdateNetworkInfo
0x18002d61e  mov     edx, 1
0x18002d623  xor     ecx, ecx
0x18002d625  call    UpdateNetworkInfo
0x18002d62a  call    cs:__imp_FlushDnsPolicyUnreachableStatus
0x18002d630  call    cs:__imp_DnsUpdateMachinePresence
0x18002d636  call    cs:__imp_GetTickCount64
0x18002d63c  test    edi, edi
0x18002d63e  jz      short loc_18002D64A
0x18002d640  mov     ecx, 1
0x18002d645  call    Cache_Flush
0x18002d64a  cmp     ebx, 2
0x18002d64d  jz      short loc_18002D65E
0x18002d64f  cmp     ebx, 7
0x18002d652  jz      short loc_18002D65E
0x18002d654  cmp     ebx, 8
0x18002d657  jnz     short loc_18002D670
0x18002d659  lea     ecx, [rbx-7]
0x18002d65c  jmp     short loc_18002D663
0x18002d65e  mov     ecx, 4
0x18002d663  xor     edx, edx
0x18002d665  call    cs:__imp_Reg_ReadGlobalsEx
0x18002d66b  call    IncrementGlobalCountersProxyCacheVersion
0x18002d670  mov     ecx, ebx
0x18002d672  call    Mcast_Update
0x18002d677  xor     eax, eax
0x18002d679  xchg    eax, cs:g_TraceOnceState
0x18002d67f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002d686  jz      short loc_18002D698
0x18002d688  mov     [rsp+38h+var_10], ebx
0x18002d68c  mov     r9, rsi
0x18002d68f  mov     [rsp+38h+var_18], edi
0x18002d693  call    WPP_SF_sdl
0x18002d698  lea     rcx, g_csCache; lpCriticalSection
0x18002d69f  call    cs:__imp_LeaveCriticalSection
0x18002d6a5  mov     ecx, 5
0x18002d6aa  cmp     ebx, ecx
0x18002d6ac  jnz     short loc_18002D6B3
0x18002d6ae  call    mDns_HandleNetworkChange
0x18002d6b3  call    cs:__imp_DelaySortDAServerlist
0x18002d6b9  xor     ecx, ecx
0x18002d6bb  call    UnreachableServerCache_CleanupEntries
0x18002d6c0  cmp     ebx, 2
0x18002d6c3  jz      short loc_18002D6CA
0x18002d6c5  cmp     ebx, 8
0x18002d6c8  jnz     short loc_18002D6D0
0x18002d6ca  call    cs:__imp_DnsNotifyProxyConfigChangePrivate
0x18002d6d0  lea     eax, [rbx-7]
0x18002d6d3  cmp     eax, 1
0x18002d6d6  ja      short loc_18002D6E2
0x18002d6d8  mov     ecx, 1
0x18002d6dd  call    areg_AlertOrStartRegThread
0x18002d6e2  mov     rbx, [rsp+38h+arg_0]
0x18002d6e7  mov     rsi, [rsp+38h+arg_8]
0x18002d6ec  add     rsp, 30h
0x18002d6f0  pop     rdi
0x18002d6f1  retn
```
