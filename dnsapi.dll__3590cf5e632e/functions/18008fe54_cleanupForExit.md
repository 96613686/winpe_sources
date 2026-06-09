# cleanupForExit

- ea: `0x18008fe54`
- end: `0x18008ffec`
- name: `cleanupForExit`
- size: `408`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180078efc`
- `0x18008fff4`

## callees

- `0x180008750`
- `0x1800166a0`
- `0x18006d534`
- `0x1800712e4`
- `0x180072a88`
- `0x180072f4c`
- `0x180074588`
- `0x1800813d4`
- `0x18008fe54`
- `0x18009a640`
- `0x18009f740`
- `0x1800b0780`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008feef`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008feef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008ff5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008ff7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008ff5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008ff7e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008fe74`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008fe74`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008feb3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008ff0d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008feb3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008ff0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008fed7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ff43`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008fed7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ff43`
- `ntdll!EtwUnregisterTraceGuids` at `0x18008ffaa`
- `ntdll!EtwUnregisterTraceGuids` at `0x18008ffaa`
- `fwpuclnt!FwpmEngineClose0` at `0x18008ff25`
- `fwpuclnt!FwpmEngineClose0` at `0x18008ff25`

## pseudocode

```c
__int64 cleanupForExit()
{
  __int64 result; // rax

  if ( !g_fVelocityDisableInternalExports && (g_InitLevel & 0x10000) != 0 )
    DeleteCriticalSection(&g_csSecurityContextList);
  if ( (g_InitLevel & 0x100) != 0 )
  {
    CleanupNetworkInfo();
    Reg_FreeQueryTimeouts();
    Coalesce_Cleanup();
    AdaptiveTimeout_Cleanup();
  }
  if ( (g_InitLevel & 0x100000) != 0 )
  {
    AcquireSRWLockExclusive(&g_DnsPolicyTableLock);
    EmptyDnsPolicyTable();
    FreeSuffixAndPrefixPolicyTable(&g_DnsPolicyTable);
    ReleaseSRWLockExclusive(&g_DnsPolicyTableLock);
    if ( hLibModule )
    {
      FreeLibrary(hLibModule);
      hLibModule = 0;
    }
  }
  AcquireSRWLockExclusive(&stru_180111D48);
  if ( engineHandle )
  {
    FwpmEngineClose0(engineHandle);
    engineHandle = 0;
  }
  ReleaseSRWLockExclusive(&stru_180111D48);
  if ( g_Dhcpv4Key )
  {
    RegCloseKey(g_Dhcpv4Key);
    g_Dhcpv4Key = 0;
  }
  if ( g_Dhcpv6Key )
  {
    RegCloseKey(g_Dhcpv6Key);
    g_Dhcpv6Key = 0;
  }
  DnsFreeConnectionManagerInstance();
  if ( g_TraceInit )
    EtwUnregisterTraceGuids(g_TraceRegHandle);
  if ( !g_fVelocityDisableInternalExports )
    CleanUpDnsStatistics();
  ReleaseDnsGlobalRpcBindingHandle();
  if ( g_fVelocityZtdns )
    ReleaseZtHelperGlobalRpcBindingHandle();
  result = CleanupDefaultServers();
  g_InitLevel = 0;
  return result;
}

```

## disassembly

```asm
0x18008fe54  sub     rsp, 28h
0x18008fe58  cmp     cs:g_fVelocityDisableInternalExports, 0
0x18008fe5f  jnz     short loc_18008FE80
0x18008fe61  test    cs:g_InitLevel, 10000h
0x18008fe6b  jz      short loc_18008FE80
0x18008fe6d  lea     rcx, g_csSecurityContextList; lpCriticalSection
0x18008fe74  call    cs:__imp_DeleteCriticalSection
0x18008fe7b  nop     dword ptr [rax+rax+00h]
0x18008fe80  test    cs:g_InitLevel, 100h
0x18008fe8a  jz      short loc_18008FEA0
0x18008fe8c  call    CleanupNetworkInfo
0x18008fe91  call    Reg_FreeQueryTimeouts
0x18008fe96  call    Coalesce_Cleanup
0x18008fe9b  call    AdaptiveTimeout_Cleanup
0x18008fea0  test    cs:g_InitLevel, 100000h
0x18008feaa  jz      short loc_18008FF06
0x18008feac  lea     rcx, g_DnsPolicyTableLock; SRWLock
0x18008feb3  call    cs:__imp_AcquireSRWLockExclusive
0x18008feba  nop     dword ptr [rax+rax+00h]
0x18008febf  call    EmptyDnsPolicyTable
0x18008fec4  lea     rcx, g_DnsPolicyTable
0x18008fecb  call    FreeSuffixAndPrefixPolicyTable
0x18008fed0  lea     rcx, g_DnsPolicyTableLock; SRWLock
0x18008fed7  call    cs:__imp_ReleaseSRWLockExclusive
0x18008fede  nop     dword ptr [rax+rax+00h]
0x18008fee3  mov     rcx, cs:hLibModule; hLibModule
0x18008feea  test    rcx, rcx
0x18008feed  jz      short loc_18008FF06
0x18008feef  call    cs:__imp_FreeLibrary
0x18008fef6  nop     dword ptr [rax+rax+00h]
0x18008fefb  mov     cs:hLibModule, 0
0x18008ff06  lea     rcx, stru_180111D48; SRWLock
0x18008ff0d  call    cs:__imp_AcquireSRWLockExclusive
0x18008ff14  nop     dword ptr [rax+rax+00h]
0x18008ff19  mov     rcx, cs:engineHandle; engineHandle
0x18008ff20  test    rcx, rcx
0x18008ff23  jz      short loc_18008FF3C
0x18008ff25  call    cs:__imp_FwpmEngineClose0
0x18008ff2c  nop     dword ptr [rax+rax+00h]
0x18008ff31  mov     cs:engineHandle, 0
0x18008ff3c  lea     rcx, stru_180111D48; SRWLock
0x18008ff43  call    cs:__imp_ReleaseSRWLockExclusive
0x18008ff4a  nop     dword ptr [rax+rax+00h]
0x18008ff4f  mov     rcx, cs:g_Dhcpv4Key; hKey
0x18008ff56  test    rcx, rcx
0x18008ff59  jz      short loc_18008FF72
0x18008ff5b  call    cs:__imp_RegCloseKey
0x18008ff62  nop     dword ptr [rax+rax+00h]
0x18008ff67  mov     cs:g_Dhcpv4Key, 0
0x18008ff72  mov     rcx, cs:g_Dhcpv6Key; hKey
0x18008ff79  test    rcx, rcx
0x18008ff7c  jz      short loc_18008FF95
0x18008ff7e  call    cs:__imp_RegCloseKey
0x18008ff85  nop     dword ptr [rax+rax+00h]
0x18008ff8a  mov     cs:g_Dhcpv6Key, 0
0x18008ff95  call    DnsFreeConnectionManagerInstance
0x18008ff9a  cmp     cs:g_TraceInit, 0
0x18008ffa1  jz      short loc_18008FFB6
0x18008ffa3  mov     rcx, cs:g_TraceRegHandle
0x18008ffaa  call    cs:__imp_EtwUnregisterTraceGuids
0x18008ffb1  nop     dword ptr [rax+rax+00h]
0x18008ffb6  cmp     cs:g_fVelocityDisableInternalExports, 0
0x18008ffbd  jnz     short loc_18008FFC4
0x18008ffbf  call    CleanUpDnsStatistics
0x18008ffc4  call    ReleaseDnsGlobalRpcBindingHandle
0x18008ffc9  cmp     cs:g_fVelocityZtdns, 0
0x18008ffd0  jz      short loc_18008FFD7
0x18008ffd2  call    ReleaseZtHelperGlobalRpcBindingHandle
0x18008ffd7  call    CleanupDefaultServers
0x18008ffdc  mov     cs:g_InitLevel, 0
0x18008ffe6  add     rsp, 28h
0x18008ffea  retn
```
