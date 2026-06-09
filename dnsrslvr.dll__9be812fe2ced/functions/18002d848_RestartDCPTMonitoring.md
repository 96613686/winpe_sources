# RestartDCPTMonitoring

- ea: `0x18002d848`
- end: `0x18002d98d`
- name: `RestartDCPTMonitoring`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18002c980`

## callees

- `0x180008b00`
- `0x18002039c`
- `0x18002d848`
- `0x180046ec0`
- `0x180047818`
- `0x18004cc80`
- `0x180086384`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d947`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d947`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18002d968`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18002d968`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x18002d8f4`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x18002d8f4`

## string_xrefs

- `0x18002d8ac`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x18002d8b3`: `Dnscache`
- `0x18002d89d`: `Parameters\DnsPolicyConfig`

## pseudocode

```c
LSTATUS RestartDCPTMonitoring()
{
  int PersistedRegistryLocation; // eax
  int v1; // eax
  HKEY hKey[2]; // [rsp+30h] [rbp-238h] BYREF
  _BYTE v4[528]; // [rsp+40h] [rbp-228h] BYREF

  if ( !g_hDCPTKey || !g_hDCPTChange )
    return 87;
  memset_0(v4, 0, 0x20Au);
  hKey[0] = 0;
  PersistedRegistryLocation = WxGetPersistedRegistryLocation(
                                L"Dnscache",
                                L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                                L"Parameters\\DnsPolicyConfig",
                                v4,
                                522);
  if ( PersistedRegistryLocation >= 0 )
    v1 = RegOpenKeyExInternalW(-2147483646, v4, 0, 131097, hKey, 0);
  else
    v1 = WX_WIN32_FROM_HR((unsigned int)PersistedRegistryLocation);
  if ( v1 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_SD(1035, 10, (unsigned int)WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids, (unsigned int)v4, v1);
    goto LABEL_9;
  }
  if ( !hKey[0] )
  {
LABEL_9:
    CleanupDCPTMonitoring(&g_hDCPTKey, &g_hDCPTChange);
    return 0;
  }
  RegCloseKey(hKey[0]);
  return RegNotifyChangeKeyValue(g_hDCPTKey, 1, 5u, g_hDCPTChange, 1);
}

```

## disassembly

```asm
0x18002d848  sub     rsp, 268h
0x18002d84f  mov     rax, cs:__security_cookie
0x18002d856  xor     rax, rsp
0x18002d859  mov     [rsp+268h+var_18], rax
0x18002d861  cmp     cs:g_hDCPTKey, 0
0x18002d869  jz      loc_18002D970
0x18002d86f  cmp     cs:g_hDCPTChange, 0
0x18002d877  jz      loc_18002D970
0x18002d87d  xor     edx, edx; Val
0x18002d87f  lea     rcx, [rsp+268h+var_228]; void *
0x18002d884  mov     r8d, 20Ah; Size
0x18002d88a  call    memset_0
0x18002d88f  lea     r9, [rsp+268h+var_228]
0x18002d894  mov     [rsp+268h+hKey], 0
0x18002d89d  lea     r8, aParametersDnsp; "Parameters\\DnsPolicyConfig"
0x18002d8a4  mov     [rsp+268h+fAsynchronous], 20Ah
0x18002d8ac  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18002d8b3  lea     rcx, aDnscache_0; "Dnscache"
0x18002d8ba  call    WxGetPersistedRegistryLocation
0x18002d8bf  test    eax, eax
0x18002d8c1  jns     short loc_18002D8CC
0x18002d8c3  mov     ecx, eax
0x18002d8c5  call    WX_WIN32_FROM_HR
0x18002d8ca  jmp     short loc_18002D8FA
0x18002d8cc  lea     rax, [rsp+268h+hKey]
0x18002d8d1  mov     [rsp+268h+var_240], 0
0x18002d8da  mov     r9d, 20019h
0x18002d8e0  mov     qword ptr [rsp+268h+fAsynchronous], rax
0x18002d8e5  xor     r8d, r8d
0x18002d8e8  lea     rdx, [rsp+268h+var_228]
0x18002d8ed  mov     rcx, 0FFFFFFFF80000002h
0x18002d8f4  call    cs:__imp_RegOpenKeyExInternalW
0x18002d8fa  test    eax, eax
0x18002d8fc  jz      short loc_18002D93D
0x18002d8fe  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002d905  jz      short loc_18002D926
0x18002d907  mov     edx, 0Ah
0x18002d90c  mov     [rsp+268h+fAsynchronous], eax
0x18002d910  mov     ecx, 40Bh
0x18002d915  lea     r9, [rsp+268h+var_228]
0x18002d91a  lea     r8, WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids
0x18002d921  call    WPP_SF_SD
0x18002d926  lea     rdx, g_hDCPTChange
0x18002d92d  lea     rcx, g_hDCPTKey
0x18002d934  call    CleanupDCPTMonitoring
0x18002d939  xor     eax, eax
0x18002d93b  jmp     short loc_18002D975
0x18002d93d  mov     rcx, [rsp+268h+hKey]; hKey
0x18002d942  test    rcx, rcx
0x18002d945  jz      short loc_18002D926
0x18002d947  call    cs:__imp_RegCloseKey
0x18002d94d  mov     r9, cs:g_hDCPTChange; hEvent
0x18002d954  mov     edx, 1; bWatchSubtree
0x18002d959  mov     rcx, cs:g_hDCPTKey; hKey
0x18002d960  mov     [rsp+268h+fAsynchronous], edx; fAsynchronous
0x18002d964  lea     r8d, [rdx+4]; dwNotifyFilter
0x18002d968  call    cs:__imp_RegNotifyChangeKeyValue
0x18002d96e  jmp     short loc_18002D975
0x18002d970  mov     eax, 57h ; 'W'
0x18002d975  mov     rcx, [rsp+268h+var_18]
0x18002d97d  xor     rcx, rsp; StackCookie
0x18002d980  call    __security_check_cookie
0x18002d985  add     rsp, 268h
0x18002d98c  retn
```
