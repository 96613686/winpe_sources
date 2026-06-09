# NotifyThread

- ea: `0x18002c980`
- end: `0x18002d061`
- name: `NotifyThread`
- size: `1761`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, installer_update`

## callees

- `0x180004aa8`
- `0x180012338`
- `0x180012680`
- `0x180018118`
- `0x18002c980`
- `0x18002d068`
- `0x18002d0ec`
- `0x18002d17c`
- `0x18002d5b0`
- `0x18002d7b8`
- `0x18002d848`
- `0x18002d994`
- `0x18003d94c`
- `0x18003ebb8`
- `0x18003f724`
- `0x18003fc98`
- `0x180040b20`
- `0x180046ec0`
- `0x180047818`
- `0x18004ce98`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `DNSAPI!AdaptiveTimeout_ClearInterfaceSpecificConfiguration` at `0x18002ccbb`
- `DNSAPI!AdaptiveTimeout_ClearInterfaceSpecificConfiguration` at `0x18002ccbb`
- `DNSAPI!DnsApiOnNetworkChange` at `0x18002cb87`
- `DNSAPI!DnsApiOnNetworkChange` at `0x18002cb87`
- `DNSAPI!NetInfo_IsTcpipConfigChange` at `0x18002cb2d`
- `DNSAPI!NetInfo_IsTcpipConfigChange` at `0x18002cb2d`
- `DNSAPI!NetInfo_UpdateDnsInterfaceConfigChange` at `0x18002ccd5`
- `DNSAPI!NetInfo_UpdateDnsInterfaceConfigChange` at `0x18002ccd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d007`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d007`
- `api-ms-win-core-file-l1-1-0!FindNextChangeNotification` at `0x18002cc6e`
- `api-ms-win-core-file-l1-1-0!FindNextChangeNotification` at `0x18002cc6e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002cabe`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002cabe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cb42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cbc2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ccfa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cb42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cbc2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ccfa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cb20`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cbaf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ccc8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ccec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cb20`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cbaf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ccc8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ccec`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002cc9e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002ce8f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002cc9e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002ce8f`
- `dhcpcsvc!DhcpStaticRefreshParams` at `0x18002cc4f`
- `dhcpcsvc!DhcpStaticRefreshParams` at `0x18002cc4f`

## string_xrefs

- `0x18002cc11`: `Registry-notification`

## pseudocode

```c
int __fastcall NotifyThread(PVOID Parameter)
{
  __int64 v1; // r13
  __int64 v2; // rsi
  __int64 v3; // r15
  __int64 v4; // r14
  __int64 v5; // r12
  DWORD v6; // edi
  int result; // eax
  DWORD v8; // eax
  DWORD v9; // ebx
  QueryTable *v10; // rcx
  int v11; // r14d
  QueryTable *v12; // rsi
  int v13; // ebx
  bool v14; // zf
  __int64 v15; // rbx
  __int64 v16; // rbx
  DWORD LastError; // eax
  int v18; // [rsp+30h] [rbp-69h]
  int v19; // [rsp+34h] [rbp-65h]
  int v20; // [rsp+38h] [rbp-61h]
  int v21; // [rsp+3Ch] [rbp-5Dh]
  int v22; // [rsp+40h] [rbp-59h]
  HANDLE Handles[10]; // [rsp+50h] [rbp-49h] BYREF

  memset_0(Handles, 0, 0x48u);
  v20 = -1;
  LODWORD(v1) = -1;
  LODWORD(v2) = -1;
  v18 = -1;
  LODWORD(v3) = -1;
  v19 = -1;
  LODWORD(v4) = -1;
  v21 = -1;
  LODWORD(v5) = -1;
  v22 = -1;
  if ( (xmmword_1800AB5A0 & 4) != 0 )
    WPP_SF_(1026, 36, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids);
  g_hHostFileChange = (HANDLE)CreateHostsFileChangeHandle();
  InitializeRegistryMonitoring();
  InitializeGroupPolicyMonitoring();
  InitializeDCPTMonitoring();
  InitializeTcpipChangeMonitoring(1);
  InitializeTcpipChangeMonitoring(0);
  Handles[0] = g_hStopEvent;
  v6 = 1;
  result = (int)g_hHostFileChange;
  if ( g_hHostFileChange )
  {
    v20 = 1;
    v6 = 2;
    Handles[1] = g_hHostFileChange;
  }
  if ( g_hRegistryChange )
  {
    v1 = v6++;
    Handles[v1] = g_hRegistryChange;
  }
  if ( g_hGroupPolicyChange )
  {
    v2 = v6++;
    v18 = v2;
    Handles[v2] = g_hGroupPolicyChange;
  }
  if ( g_hInterfaceSpecificKeyChange )
  {
    v15 = v6++;
    v21 = v15;
    Handles[v15] = g_hInterfaceSpecificKeyChange;
  }
  if ( g_hTcpipv4Change )
  {
    v4 = v6++;
    v19 = v4;
    Handles[v4] = g_hTcpipv4Change;
  }
  if ( g_hTcpipv6Change )
  {
    v5 = v6++;
    Handles[v5] = g_hTcpipv6Change;
  }
  if ( g_hCacheGCEvent )
  {
    v16 = v6++;
    v22 = v16;
    Handles[v16] = g_hCacheGCEvent;
  }
  if ( g_hDCPTChange )
  {
    v3 = v6++;
    Handles[v3] = g_hDCPTChange;
  }
  if ( v6 != 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          v8 = WaitForMultipleObjectsEx(v6, Handles, 0, 0xFFFFFFFF, 0);
          v9 = v8;
          if ( v8 )
            break;
          if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
            WPP_SF_(1035, 38, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids);
          result = g_fStopFlag;
          if ( !g_fStopFlag )
          {
            if ( g_GarbageCollectFlag )
              Cache_GarbageCollect(0);
            Sleep(0x3E8u);
            result = g_fStopFlag;
            if ( !g_fStopFlag )
              continue;
          }
          goto LABEL_64;
        }
        if ( v8 != v20 )
          break;
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_(1035, 39, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids);
        result = FindNextChangeNotification(g_hHostFileChange);
        if ( !result )
        {
          if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          {
            LastError = GetLastError();
            result = WPP_SF_d(1035, 40, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids, LastError);
          }
          goto LABEL_64;
        }
LABEL_53:
        Cache_Flush(1);
      }
      if ( v8 == (_DWORD)v1 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_(1035, 41, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids);
        RestartRegistryMonitoring();
        if ( !g_hDCPTChange )
        {
          InitializeDCPTMonitoring();
          if ( g_hDCPTChange )
          {
            if ( v6 < 9 )
            {
              v3 = v6++;
              Handles[v3] = g_hDCPTChange;
            }
          }
        }
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_(1035, 42, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids);
        HandleConfigChange("Registry-notification", 0, 7);
        if ( (unsigned int)CheckForAlternateNamesChange() )
        {
          if ( SBYTE3(xmmword_1800AB5A0) < 0 )
            WPP_SF_(1055, 43, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids);
          DhcpStaticRefreshParams(0);
        }
      }
      else if ( v8 == (_DWORD)v2 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_(1035, 44, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids);
        RestartGroupPolicyMonitoring();
        if ( SBYTE3(xmmword_1800AB5A0) < 0 )
          WPP_SF_(1055, 45, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids);
        HandleConfigChange("GroupPolicy-notification", 1, 8);
      }
      else
      {
        if ( v8 == (_DWORD)v3 )
        {
          if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
            WPP_SF_(1035, 46, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids);
          RestartDCPTMonitoring();
          if ( !g_hDCPTChange )
          {
            --v6;
            LODWORD(v3) = -1;
          }
          goto LABEL_53;
        }
        if ( v8 == v21 )
        {
          if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
            WPP_SF_(1035, 47, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids);
          RestartInterfaceSpecificMonitoring();
          AdaptiveTimeout_ClearInterfaceSpecificConfiguration();
          EnterCriticalSection(&g_csNetinfo);
          if ( (unsigned int)NetInfo_UpdateDnsInterfaceConfigChange(g_NetworkInfo) )
            goto LABEL_86;
          goto LABEL_30;
        }
        if ( v8 == (_DWORD)v5 || v8 == (_DWORD)v4 )
        {
          if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
            WPP_SF_(1035, 48, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids);
          RestartTcpipMonitoring(v9 == (_DWORD)v5);
          EnterCriticalSection(&g_csNetinfo);
          if ( (unsigned int)NetInfo_IsTcpipConfigChange(g_NetworkInfo) )
          {
            UpdateNetworkInfo(0, 0);
LABEL_86:
            UpdateNetworkInfo(0, 1);
          }
LABEL_30:
          LeaveCriticalSection(&g_csNetinfo);
        }
        else if ( v8 == v22 )
        {
          if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
            WPP_SF_(1035, 49, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids);
          Cache_GarbageCollect(1);
          if ( g_QueryTable )
            QueryTable::ClearCache(v10, 1u);
          DnsApiOnNetworkChange(128);
          v11 = 0;
          _InterlockedExchange(&dword_1800AB760, 0);
          v12 = g_QueryTable;
          if ( g_QueryTable )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)g_QueryTable + 1);
            v11 = *((_DWORD *)v12 + 9);
            LeaveCriticalSection((LPCRITICAL_SECTION)v12 + 1);
          }
          EnterCriticalSection(&g_csCache);
          v13 = g_RecordSetCount;
          LeaveCriticalSection(&g_csCache);
          LODWORD(v2) = v18;
          v14 = v11 + v13 == 0;
          LODWORD(v4) = v19;
          if ( !v14 )
            Cache_GCTimerSet();
        }
        else
        {
          result = g_fStopFlag;
          if ( g_fStopFlag )
            goto LABEL_64;
          Sleep(0x1388u);
        }
      }
    }
  }
  if ( SBYTE3(xmmword_1800AB5A0) < 0 )
    result = WPP_SF_(1055, 37, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids);
LABEL_64:
  if ( (xmmword_1800AB5A0 & 4) != 0 )
    result = WPP_SF_(1026, 50, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    return WPP_SF_(1035, 51, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids);
  return result;
}

```

## disassembly

```asm
0x18002c980  push    rbp
0x18002c982  push    rbx
0x18002c983  push    rsi
0x18002c984  push    rdi
0x18002c985  push    r12
0x18002c987  push    r13
0x18002c989  push    r14
0x18002c98b  push    r15
0x18002c98d  lea     rbp, [rsp-1Fh]
0x18002c992  sub     rsp, 0B8h
0x18002c999  mov     rax, cs:__security_cookie
0x18002c9a0  xor     rax, rsp
0x18002c9a3  mov     [rbp+57h+var_50], rax
0x18002c9a7  xor     edx, edx; Val
0x18002c9a9  lea     rcx, [rbp+57h+Handles]; void *
0x18002c9ad  lea     r8d, [rdx+48h]; Size
0x18002c9b1  call    memset_0
0x18002c9b6  or      eax, 0FFFFFFFFh
0x18002c9b9  mov     [rbp+57h+var_B8], eax
0x18002c9bc  mov     r13d, eax
0x18002c9bf  mov     esi, eax
0x18002c9c1  mov     [rbp+57h+var_C0], eax
0x18002c9c4  mov     r15d, eax
0x18002c9c7  mov     [rbp+57h+var_BC], eax
0x18002c9ca  mov     r14d, eax
0x18002c9cd  mov     [rbp+57h+var_B4], eax
0x18002c9d0  mov     r12d, eax
0x18002c9d3  mov     [rbp+57h+var_B0], eax
0x18002c9d6  test    byte ptr cs:xmmword_1800AB5A0, 4
0x18002c9dd  jnz     loc_18002CD87
0x18002c9e3  call    CreateHostsFileChangeHandle
0x18002c9e8  mov     cs:g_hHostFileChange, rax
0x18002c9ef  call    InitializeRegistryMonitoring
0x18002c9f4  call    InitializeGroupPolicyMonitoring
0x18002c9f9  call    InitializeDCPTMonitoring
0x18002c9fe  mov     ecx, 1
0x18002ca03  call    InitializeTcpipChangeMonitoring
0x18002ca08  xor     ecx, ecx
0x18002ca0a  call    InitializeTcpipChangeMonitoring
0x18002ca0f  mov     rax, cs:g_hStopEvent
0x18002ca16  mov     edx, 1
0x18002ca1b  mov     [rbp+57h+Handles], rax
0x18002ca1f  mov     edi, edx
0x18002ca21  mov     rax, cs:g_hHostFileChange
0x18002ca28  test    rax, rax
0x18002ca2b  jnz     loc_18002CDA2
0x18002ca31  mov     rcx, cs:g_hRegistryChange
0x18002ca38  test    rcx, rcx
0x18002ca3b  jnz     loc_18002CDB3
0x18002ca41  mov     rcx, cs:g_hGroupPolicyChange
0x18002ca48  test    rcx, rcx
0x18002ca4b  jnz     loc_18002CDC2
0x18002ca51  mov     rcx, cs:g_hInterfaceSpecificKeyChange
0x18002ca58  test    rcx, rcx
0x18002ca5b  jnz     loc_18002CDD3
0x18002ca61  mov     rcx, cs:g_hTcpipv4Change
0x18002ca68  test    rcx, rcx
0x18002ca6b  jnz     loc_18002CDE4
0x18002ca71  mov     rcx, cs:g_hTcpipv6Change
0x18002ca78  test    rcx, rcx
0x18002ca7b  jnz     loc_18002CDF7
0x18002ca81  mov     rcx, cs:g_hCacheGCEvent
0x18002ca88  test    rcx, rcx
0x18002ca8b  jnz     loc_18002CE06
0x18002ca91  mov     rcx, cs:g_hDCPTChange
0x18002ca98  test    rcx, rcx
0x18002ca9b  jnz     loc_18002CE17
0x18002caa1  cmp     edi, edx
0x18002caa3  jz      loc_18002CE26
0x18002caa9  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18002caad  mov     [rsp+0F0h+bAlertable], 0; bAlertable
0x18002cab5  xor     r8d, r8d; bWaitAll
0x18002cab8  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18002cabc  mov     ecx, edi; nCount
0x18002cabe  call    cs:__imp_WaitForMultipleObjectsEx
0x18002cac4  mov     ebx, eax
0x18002cac6  test    eax, eax
0x18002cac8  jz      loc_18002CE4E
0x18002cace  cmp     eax, [rbp+57h+var_B8]
0x18002cad1  jz      loc_18002CC5A
0x18002cad7  cmp     eax, r13d
0x18002cada  jz      loc_18002CBE2
0x18002cae0  cmp     eax, esi
0x18002cae2  jz      loc_18002CF26
0x18002cae8  cmp     eax, r15d
0x18002caeb  jz      loc_18002CD05
0x18002caf1  cmp     eax, [rbp+57h+var_B4]
0x18002caf4  jz      loc_18002CCA9
0x18002cafa  cmp     eax, r12d
0x18002cafd  jnz     short loc_18002CB4D
0x18002caff  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002cb06  jnz     loc_18002CD6C
0x18002cb0c  xor     ecx, ecx
0x18002cb0e  cmp     ebx, r12d
0x18002cb11  setz    cl
0x18002cb14  call    RestartTcpipMonitoring
0x18002cb19  lea     rcx, g_csNetinfo; lpCriticalSection
0x18002cb20  call    cs:__imp_EnterCriticalSection
0x18002cb26  mov     rcx, cs:g_NetworkInfo
0x18002cb2d  call    cs:__imp_NetInfo_IsTcpipConfigChange
0x18002cb33  test    eax, eax
0x18002cb35  jnz     loc_18002CFE0
0x18002cb3b  lea     rcx, g_csNetinfo; lpCriticalSection
0x18002cb42  call    cs:__imp_LeaveCriticalSection
0x18002cb48  jmp     loc_18002CAA9
0x18002cb4d  cmp     ebx, r14d
0x18002cb50  jz      short loc_18002CAFF
0x18002cb52  cmp     ebx, [rbp+57h+var_B0]
0x18002cb55  jnz     loc_18002CC8B
0x18002cb5b  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002cb62  jnz     loc_18002CFB9
0x18002cb68  mov     ebx, 1
0x18002cb6d  mov     ecx, ebx
0x18002cb6f  call    Cache_GarbageCollect
0x18002cb74  cmp     cs:?g_QueryTable@@3PEAVQueryTable@@EA, 0; QueryTable * g_QueryTable
0x18002cb7c  jnz     loc_18002CFD4
0x18002cb82  mov     ecx, 80h
0x18002cb87  call    cs:__imp_DnsApiOnNetworkChange
0x18002cb8d  xor     eax, eax
0x18002cb8f  xor     r14d, r14d
0x18002cb92  xchg    eax, cs:dword_1800AB760
0x18002cb98  mov     rsi, cs:?g_QueryTable@@3PEAVQueryTable@@EA; QueryTable * g_QueryTable
0x18002cb9f  test    rsi, rsi
0x18002cba2  jnz     loc_18002CCE8
0x18002cba8  lea     rcx, g_csCache; lpCriticalSection
0x18002cbaf  call    cs:__imp_EnterCriticalSection
0x18002cbb5  mov     ebx, cs:g_RecordSetCount
0x18002cbbb  lea     rcx, g_csCache; lpCriticalSection
0x18002cbc2  call    cs:__imp_LeaveCriticalSection
0x18002cbc8  mov     esi, [rbp+57h+var_C0]
0x18002cbcb  add     ebx, r14d
0x18002cbce  mov     r14d, [rbp+57h+var_BC]
0x18002cbd2  jz      loc_18002CAA9
0x18002cbd8  call    Cache_GCTimerSet
0x18002cbdd  jmp     loc_18002CAA9
0x18002cbe2  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002cbe9  jnz     loc_18002CEC3
0x18002cbef  call    RestartRegistryMonitoring
0x18002cbf4  cmp     cs:g_hDCPTChange, 0
0x18002cbfc  jz      loc_18002CEDE
0x18002cc02  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002cc09  jnz     loc_18002CF0B
0x18002cc0f  xor     edx, edx
0x18002cc11  lea     rcx, aRegistryNotifi; "Registry-notification"
0x18002cc18  lea     r8d, [rdx+7]
0x18002cc1c  call    HandleConfigChange
0x18002cc21  call    CheckForAlternateNamesChange
0x18002cc26  test    eax, eax
0x18002cc28  jz      loc_18002CAA9
0x18002cc2e  cmp     byte ptr cs:xmmword_1800AB5A0+3, 0
0x18002cc35  jge     short loc_18002CC4D
0x18002cc37  mov     edx, 2Bh ; '+'
0x18002cc3c  lea     r8, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids
0x18002cc43  mov     ecx, 41Fh
0x18002cc48  call    WPP_SF_
0x18002cc4d  xor     ecx, ecx
0x18002cc4f  call    cs:__imp_DhcpStaticRefreshParams
0x18002cc55  jmp     loc_18002CAA9
0x18002cc5a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002cc61  jnz     loc_18002CEA8
0x18002cc67  mov     rcx, cs:g_hHostFileChange; hChangeHandle
0x18002cc6e  call    cs:__imp_FindNextChangeNotification
0x18002cc74  test    eax, eax
0x18002cc76  jz      loc_18002CFFA
0x18002cc7c  mov     ecx, 1
0x18002cc81  call    Cache_Flush
0x18002cc86  jmp     loc_18002CAA9
0x18002cc8b  mov     eax, cs:g_fStopFlag
0x18002cc91  test    eax, eax
0x18002cc93  jnz     loc_18002CD32
0x18002cc99  mov     ecx, 1388h; dwMilliseconds
0x18002cc9e  call    cs:__imp_Sleep
0x18002cca4  jmp     loc_18002CAA9
0x18002cca9  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002ccb0  jnz     loc_18002CF9E
0x18002ccb6  call    RestartInterfaceSpecificMonitoring
0x18002ccbb  call    cs:__imp_AdaptiveTimeout_ClearInterfaceSpecificConfiguration
0x18002ccc1  lea     rcx, g_csNetinfo; lpCriticalSection
0x18002ccc8  call    cs:__imp_EnterCriticalSection
0x18002ccce  mov     rcx, cs:g_NetworkInfo
0x18002ccd5  call    cs:__imp_NetInfo_UpdateDnsInterfaceConfigChange
0x18002ccdb  test    eax, eax
0x18002ccdd  jz      loc_18002CB3B
0x18002cce3  jmp     loc_18002CFE9
0x18002cce8  lea     rcx, [rsi+28h]; lpCriticalSection
0x18002ccec  call    cs:__imp_EnterCriticalSection
0x18002ccf2  mov     r14d, [rsi+24h]
0x18002ccf6  lea     rcx, [rsi+28h]; lpCriticalSection
0x18002ccfa  call    cs:__imp_LeaveCriticalSection
0x18002cd00  jmp     loc_18002CBA8
0x18002cd05  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002cd0c  jnz     loc_18002CF83
0x18002cd12  call    RestartDCPTMonitoring
0x18002cd17  cmp     cs:g_hDCPTChange, 0
0x18002cd1f  jnz     loc_18002CC7C
0x18002cd25  or      eax, 0FFFFFFFFh
0x18002cd28  add     edi, eax
0x18002cd2a  mov     r15d, eax
0x18002cd2d  jmp     loc_18002CC7C
0x18002cd32  test    byte ptr cs:xmmword_1800AB5A0, 4
0x18002cd39  jnz     loc_18002D02B
0x18002cd3f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002cd46  jnz     loc_18002D046
0x18002cd4c  mov     rcx, [rbp+57h+var_50]
0x18002cd50  xor     rcx, rsp; StackCookie
0x18002cd53  call    __security_check_cookie
0x18002cd58  add     rsp, 0B8h
0x18002cd5f  pop     r15
0x18002cd61  pop     r14
0x18002cd63  pop     r13
0x18002cd65  pop     r12
0x18002cd67  pop     rdi
0x18002cd68  pop     rsi
0x18002cd69  pop     rbx
0x18002cd6a  pop     rbp
0x18002cd6b  retn
0x18002cd6c  mov     edx, 30h ; '0'
0x18002cd71  lea     r8, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids
0x18002cd78  mov     ecx, 40Bh
0x18002cd7d  call    WPP_SF_
0x18002cd82  jmp     loc_18002CB0C
0x18002cd87  mov     edx, 24h ; '$'
0x18002cd8c  lea     r8, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids
0x18002cd93  mov     ecx, 402h
0x18002cd98  call    WPP_SF_
0x18002cd9d  jmp     loc_18002C9E3
0x18002cda2  mov     [rbp+57h+var_B8], edx
0x18002cda5  mov     edi, 2
0x18002cdaa  mov     [rbp+57h+var_98], rax
0x18002cdae  jmp     loc_18002CA31
0x18002cdb3  mov     r13d, edi
0x18002cdb6  add     edi, edx
0x18002cdb8  mov     [rbp+r13*8+57h+Handles], rcx
0x18002cdbd  jmp     loc_18002CA41
0x18002cdc2  mov     esi, edi
0x18002cdc4  add     edi, edx
0x18002cdc6  mov     [rbp+57h+var_C0], esi
0x18002cdc9  mov     [rbp+rsi*8+57h+Handles], rcx
0x18002cdce  jmp     loc_18002CA51
0x18002cdd3  mov     ebx, edi
0x18002cdd5  add     edi, edx
0x18002cdd7  mov     [rbp+57h+var_B4], ebx
0x18002cdda  mov     [rbp+rbx*8+57h+Handles], rcx
0x18002cddf  jmp     loc_18002CA61
0x18002cde4  mov     r14d, edi
0x18002cde7  add     edi, edx
0x18002cde9  mov     [rbp+57h+var_BC], r14d
0x18002cded  mov     [rbp+r14*8+57h+Handles], rcx
0x18002cdf2  jmp     loc_18002CA71
0x18002cdf7  mov     r12d, edi
0x18002cdfa  add     edi, edx
0x18002cdfc  mov     [rbp+r12*8+57h+Handles], rcx
0x18002ce01  jmp     loc_18002CA81
0x18002ce06  mov     ebx, edi
0x18002ce08  add     edi, edx
0x18002ce0a  mov     [rbp+57h+var_B0], ebx
0x18002ce0d  mov     [rbp+rbx*8+57h+Handles], rcx
0x18002ce12  jmp     loc_18002CA91
0x18002ce17  mov     r15d, edi
0x18002ce1a  add     edi, edx
0x18002ce1c  mov     [rbp+r15*8+57h+Handles], rcx
0x18002ce21  jmp     loc_18002CAA1
0x18002ce26  cmp     byte ptr cs:xmmword_1800AB5A0+3, 0
0x18002ce2d  jge     loc_18002CD32
0x18002ce33  mov     edx, 25h ; '%'
0x18002ce38  lea     r8, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids
0x18002ce3f  mov     ecx, 41Fh
0x18002ce44  call    WPP_SF_
0x18002ce49  jmp     loc_18002CD32
0x18002ce4e  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002ce55  jz      short loc_18002CE6D
0x18002ce57  mov     edx, 26h ; '&'
0x18002ce5c  lea     r8, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids
0x18002ce63  mov     ecx, 40Bh
0x18002ce68  call    WPP_SF_
0x18002ce6d  mov     eax, cs:g_fStopFlag
0x18002ce73  test    eax, eax
0x18002ce75  jnz     loc_18002CD32
0x18002ce7b  cmp     cs:g_GarbageCollectFlag, eax
0x18002ce81  jz      short loc_18002CE8A
0x18002ce83  xor     ecx, ecx
0x18002ce85  call    Cache_GarbageCollect
0x18002ce8a  mov     ecx, 3E8h; dwMilliseconds
0x18002ce8f  call    cs:__imp_Sleep
0x18002ce95  mov     eax, cs:g_fStopFlag
0x18002ce9b  test    eax, eax
0x18002ce9d  jz      loc_18002CAA9
0x18002cea3  jmp     loc_18002CD32
0x18002cea8  mov     edx, 27h ; '''
0x18002cead  lea     r8, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids
0x18002ceb4  mov     ecx, 40Bh
0x18002ceb9  call    WPP_SF_
0x18002cebe  jmp     loc_18002CC67
0x18002cec3  mov     edx, 29h ; ')'
0x18002cec8  lea     r8, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids
0x18002cecf  mov     ecx, 40Bh
0x18002ced4  call    WPP_SF_
0x18002ced9  jmp     loc_18002CBEF
0x18002cede  call    InitializeDCPTMonitoring
0x18002cee3  mov     rcx, cs:g_hDCPTChange
  ... truncated ...
```
