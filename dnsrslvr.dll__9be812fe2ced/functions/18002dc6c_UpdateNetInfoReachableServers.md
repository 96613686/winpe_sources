# UpdateNetInfoReachableServers

- ea: `0x18002dc6c`
- end: `0x18002dd9e`
- name: `UpdateNetInfoReachableServers`
- size: `306`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180039350`
- `0x180039560`

## callees

- `0x18002dc6c`
- `0x180086bd4`

## import_xrefs

- `DNSAPI!NetInfo_Free` at `0x18002dcf8`
- `DNSAPI!NetInfo_Free` at `0x18002dd3b`
- `DNSAPI!NetInfo_Free` at `0x18002dcf8`
- `DNSAPI!NetInfo_Free` at `0x18002dd3b`
- `DNSAPI!NetInfo_UpdateServerReachability` at `0x18002dcaf`
- `DNSAPI!NetInfo_UpdateServerReachability` at `0x18002dcaf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002dcef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002dd32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002dd44`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002dcef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002dd32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002dd44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002dc87`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002dcc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002dd0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002dc87`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002dcc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002dd0a`

## pseudocode

```c
__int64 UpdateNetInfoReachableServers()
{
  unsigned int updated; // edi
  __int64 v1; // rcx
  __int64 v2; // rbx
  __int64 v3; // rcx
  __int64 v4; // rbx

  updated = 0;
  EnterCriticalSection(&g_csNetinfo);
  if ( g_IsReachableServerUpdateRequired )
  {
    updated = NetInfo_UpdateServerReachability(g_NetworkInfo, g_PerNetworkNetInfo, &g_IsReachableServerUpdateRequired);
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_qd(v1, 10, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, 0, 0);
    EnterCriticalSection(&g_csNetinfo);
    v2 = g_NetworkInfo;
    ++g_NetInfoTag;
    g_NetworkInfo = 0;
    g_IsReachableServerUpdateRequired = 1;
    LeaveCriticalSection(&g_csNetinfo);
    NetInfo_Free(v2);
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_qd(v3, 10, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, 0, 1);
    EnterCriticalSection(&g_csNetinfo);
    v4 = g_PerNetworkNetInfo;
    ++g_NetInfoTag;
    g_PerNetworkNetInfo = 0;
    g_IsReachableServerUpdateRequired = 1;
    LeaveCriticalSection(&g_csNetinfo);
    NetInfo_Free(v4);
  }
  LeaveCriticalSection(&g_csNetinfo);
  return updated;
}

```

## disassembly

```asm
0x18002dc6c  mov     [rsp+arg_0], rbx
0x18002dc71  mov     [rsp+arg_8], rsi
0x18002dc76  push    rdi
0x18002dc77  sub     rsp, 30h
0x18002dc7b  lea     rsi, g_csNetinfo
0x18002dc82  xor     edi, edi
0x18002dc84  mov     rcx, rsi; lpCriticalSection
0x18002dc87  call    cs:__imp_EnterCriticalSection
0x18002dc8d  cmp     cs:g_IsReachableServerUpdateRequired, dil
0x18002dc94  jz      loc_18002DD41
0x18002dc9a  mov     rdx, cs:g_PerNetworkNetInfo
0x18002dca1  lea     r8, g_IsReachableServerUpdateRequired
0x18002dca8  mov     rcx, cs:g_NetworkInfo
0x18002dcaf  call    cs:__imp_NetInfo_UpdateServerReachability
0x18002dcb5  mov     edi, eax
0x18002dcb7  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002dcbe  jnz     loc_18002DD5C
0x18002dcc4  mov     rcx, rsi; lpCriticalSection
0x18002dcc7  call    cs:__imp_EnterCriticalSection
0x18002dccd  mov     rbx, cs:g_NetworkInfo
0x18002dcd4  inc     cs:g_NetInfoTag
0x18002dcda  mov     cs:g_NetworkInfo, 0
0x18002dce5  mov     cs:g_IsReachableServerUpdateRequired, 1
0x18002dcec  mov     rcx, rsi; lpCriticalSection
0x18002dcef  call    cs:__imp_LeaveCriticalSection
0x18002dcf5  mov     rcx, rbx
0x18002dcf8  call    cs:__imp_NetInfo_Free
0x18002dcfe  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002dd05  jnz     short loc_18002DD7D
0x18002dd07  mov     rcx, rsi; lpCriticalSection
0x18002dd0a  call    cs:__imp_EnterCriticalSection
0x18002dd10  mov     rbx, cs:g_PerNetworkNetInfo
0x18002dd17  inc     cs:g_NetInfoTag
0x18002dd1d  mov     cs:g_PerNetworkNetInfo, 0
0x18002dd28  mov     cs:g_IsReachableServerUpdateRequired, 1
0x18002dd2f  mov     rcx, rsi; lpCriticalSection
0x18002dd32  call    cs:__imp_LeaveCriticalSection
0x18002dd38  mov     rcx, rbx
0x18002dd3b  call    cs:__imp_NetInfo_Free
0x18002dd41  mov     rcx, rsi; lpCriticalSection
0x18002dd44  call    cs:__imp_LeaveCriticalSection
0x18002dd4a  mov     rbx, [rsp+38h+arg_0]
0x18002dd4f  mov     eax, edi
0x18002dd51  mov     rsi, [rsp+38h+arg_8]
0x18002dd56  add     rsp, 30h
0x18002dd5a  pop     rdi
0x18002dd5b  retn
0x18002dd5c  mov     edx, 0Ah
0x18002dd61  mov     [rsp+38h+var_18], 0
0x18002dd69  xor     r9d, r9d
0x18002dd6c  lea     r8, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids
0x18002dd73  call    WPP_SF_qd
0x18002dd78  jmp     loc_18002DCC4
0x18002dd7d  mov     edx, 0Ah
0x18002dd82  mov     [rsp+38h+var_18], 1
0x18002dd8a  xor     r9d, r9d
0x18002dd8d  lea     r8, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids
0x18002dd94  call    WPP_SF_qd
0x18002dd99  jmp     loc_18002DD07
```
