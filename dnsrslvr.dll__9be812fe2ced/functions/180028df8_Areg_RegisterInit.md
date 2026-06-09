# Areg_RegisterInit

- ea: `0x180028df8`
- end: `0x1800290d3`
- name: `Areg_RegisterInit`
- size: `731`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180027c04`
- `0x180027ef0`
- `0x18004a600`

## callees

- `0x180008b00`
- `0x18002039c`
- `0x180028df8`
- `0x180036530`
- `0x180046ec0`
- `0x180047818`
- `0x18004aa68`
- `0x180086384`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `DNSAPI!Reg_ReadGlobalsEx` at `0x180028f13`
- `DNSAPI!Reg_ReadGlobalsEx` at `0x180028f13`
- `DNSAPI!DnsGlobals` at `0x180028f19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ff0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ff0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028fa2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028fa2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028fde`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028fde`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028e8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028eb5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028ed7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029004`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002908b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028e8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028eb5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028ed7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029004`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002908b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028e6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028ec2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028e6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028ec2`

## string_xrefs

- `0x180028f42`: `System\CurrentControlSet\Services\Tcpip\Parameters\DNSRegisteredAdapters`

## pseudocode

```c
__int64 Areg_RegisterInit()
{
  struct _RTL_CRITICAL_SECTION *v0; // rcx
  struct _RTL_CRITICAL_SECTION *v1; // rcx
  __int64 v2; // rdx
  unsigned int v3; // ebx
  int PersistedRegistryLocation; // eax
  DWORD LastError; // eax
  LSTATUS Key; // eax
  DWORD dwDisposition[4]; // [rsp+50h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-228h] BYREF

  dwDisposition[0] = 0;
  memset_0(SubKey, 0, 0x208u);
  if ( SBYTE2(xmmword_1800AB5A0) < 0 )
    WPP_SF_(1047, 17, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
  v0 = &g_AregInitCs;
  if ( !g_fVelocityLockGeneralCleanup )
    v0 = &g_csGeneralResolver;
  EnterCriticalSection(v0);
  v1 = &g_AregInitCs;
  if ( g_fAregInitialized )
  {
    if ( !g_fVelocityLockGeneralCleanup )
      v1 = &g_csGeneralResolver;
    LeaveCriticalSection(v1);
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      return 0;
    v2 = 18;
    goto LABEL_34;
  }
  if ( !g_fVelocityLockGeneralCleanup )
    v1 = &g_csGeneralResolver;
  LeaveCriticalSection(v1);
  EnterCriticalSection(&g_AregThreadCs);
  if ( g_fAregInitialized )
  {
    LeaveCriticalSection(&g_AregThreadCs);
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v2 = 22;
LABEL_34:
      WPP_SF_(1035, v2, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
      return 0;
    }
    return 0;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 19, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
  Reg_ReadGlobalsEx(0, 0);
  if ( DnsGlobals[57] )
  {
    PersistedRegistryLocation = WxGetPersistedRegistryLocation(
                                  L"DNSRegisteredAdapters",
                                  L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\DNSRegisteredAdapters",
                                  0,
                                  SubKey,
                                  520);
    if ( PersistedRegistryLocation >= 0 )
    {
      Key = RegCreateKeyExW(
              HKEY_LOCAL_MACHINE,
              SubKey,
              0,
              (LPWSTR)L"DynDRootClass",
              0,
              0x2001Fu,
              0,
              &g_hAregRegKey,
              dwDisposition);
      v3 = Key;
      if ( Key )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_SD(1035, 20, (unsigned int)WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, (unsigned int)SubKey, Key);
        goto LABEL_27;
      }
      g_hAregWakeEvent = CreateEventW(0, 0, 0, 0);
      if ( g_hAregWakeEvent )
      {
        g_fAregThreadRunning = 0;
        qword_1800AC818 = (__int64)&g_AregEntryList;
        g_AregEntryList = &g_AregEntryList;
        g_fAregThreadStop = 0;
        g_fAregThreadCheckBeforeExit = 0;
        g_AregThreadWaitCount = 0;
        g_fNoMoreUpdatess = 0;
        g_fAregPurge = 0;
        g_fAregPurgeInitiated = 0;
        areg_ResetAdaptersInRegistry();
        g_fAregInitialized = 1;
        LeaveCriticalSection(&g_AregThreadCs);
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        {
          v2 = 21;
          goto LABEL_34;
        }
        return 0;
      }
      LastError = GetLastError();
    }
    else
    {
      LastError = WX_WIN32_FROM_HR((unsigned int)PersistedRegistryLocation);
    }
    v3 = LastError;
  }
  else
  {
    v3 = 4317;
  }
LABEL_27:
  areg_CleanupGlobals();
  LeaveCriticalSection(&g_AregThreadCs);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 23, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, v3);
  if ( v3 )
    return 14;
  return v3;
}

```

## disassembly

```asm
0x180028df8  mov     [rsp+arg_0], rbx
0x180028dfd  mov     [rsp+arg_8], rbp
0x180028e02  push    rsi
0x180028e03  sub     rsp, 280h
0x180028e0a  mov     rax, cs:__security_cookie
0x180028e11  xor     rax, rsp
0x180028e14  mov     [rsp+288h+var_18], rax
0x180028e1c  xor     esi, esi
0x180028e1e  lea     rcx, [rsp+288h+SubKey]; void *
0x180028e23  xor     edx, edx; Val
0x180028e25  mov     [rsp+288h+dwDisposition], esi
0x180028e29  mov     r8d, 208h; Size
0x180028e2f  call    memset_0
0x180028e34  cmp     byte ptr cs:xmmword_1800AB5A0+2, sil
0x180028e3b  lea     rbp, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180028e42  jge     short loc_180028E54
0x180028e44  lea     edx, [rsi+11h]
0x180028e47  mov     ecx, 417h
0x180028e4c  mov     r8, rbp
0x180028e4f  call    WPP_SF_
0x180028e54  cmp     cs:g_fVelocityLockGeneralCleanup, esi
0x180028e5a  lea     rbx, g_csGeneralResolver
0x180028e61  lea     rcx, g_AregInitCs
0x180028e68  jnz     short loc_180028E6D
0x180028e6a  mov     rcx, rbx; lpCriticalSection
0x180028e6d  call    cs:__imp_EnterCriticalSection
0x180028e73  cmp     cs:g_fAregInitialized, esi
0x180028e79  lea     rcx, g_AregInitCs
0x180028e80  jz      short loc_180028EAA
0x180028e82  cmp     cs:g_fVelocityLockGeneralCleanup, esi
0x180028e88  jnz     short loc_180028E8D
0x180028e8a  mov     rcx, rbx; lpCriticalSection
0x180028e8d  call    cs:__imp_LeaveCriticalSection
0x180028e93  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180028e9a  jz      loc_1800290AC
0x180028ea0  mov     edx, 12h
0x180028ea5  jmp     loc_18002909F
0x180028eaa  cmp     cs:g_fVelocityLockGeneralCleanup, esi
0x180028eb0  jnz     short loc_180028EB5
0x180028eb2  mov     rcx, rbx; lpCriticalSection
0x180028eb5  call    cs:__imp_LeaveCriticalSection
0x180028ebb  lea     rcx, g_AregThreadCs; lpCriticalSection
0x180028ec2  call    cs:__imp_EnterCriticalSection
0x180028ec8  cmp     cs:g_fAregInitialized, esi
0x180028ece  jz      short loc_180028EF4
0x180028ed0  lea     rcx, g_AregThreadCs; lpCriticalSection
0x180028ed7  call    cs:__imp_LeaveCriticalSection
0x180028edd  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180028ee4  jz      loc_1800290AC
0x180028eea  mov     edx, 16h
0x180028eef  jmp     loc_18002909F
0x180028ef4  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180028efb  jz      short loc_180028F0F
0x180028efd  mov     edx, 13h
0x180028f02  mov     ecx, 40Bh
0x180028f07  mov     r8, rbp
0x180028f0a  call    WPP_SF_
0x180028f0f  xor     edx, edx
0x180028f11  xor     ecx, ecx
0x180028f13  call    cs:__imp_Reg_ReadGlobalsEx
0x180028f19  mov     rax, cs:__imp_DnsGlobals
0x180028f20  cmp     [rax+0E4h], esi
0x180028f26  jnz     short loc_180028F32
0x180028f28  mov     ebx, 10DDh
0x180028f2d  jmp     loc_180028FF8
0x180028f32  lea     r9, [rsp+288h+SubKey]
0x180028f37  mov     [rsp+288h+dwOptions], 208h
0x180028f3f  xor     r8d, r8d
0x180028f42  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Tc"...
0x180028f49  lea     rcx, aDnsregistereda; "DNSRegisteredAdapters"
0x180028f50  call    WxGetPersistedRegistryLocation
0x180028f55  test    eax, eax
0x180028f57  jns     short loc_180028F65
0x180028f59  mov     ecx, eax
0x180028f5b  call    WX_WIN32_FROM_HR
0x180028f60  jmp     loc_180028FF6
0x180028f65  lea     rax, [rsp+288h+dwDisposition]
0x180028f6a  xor     r8d, r8d; Reserved
0x180028f6d  mov     [rsp+288h+lpdwDisposition], rax; lpdwDisposition
0x180028f72  lea     r9, Class; "DynDRootClass"
0x180028f79  lea     rax, g_hAregRegKey
0x180028f80  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028f87  mov     [rsp+288h+phkResult], rax; phkResult
0x180028f8c  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x180028f91  mov     [rsp+288h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180028f96  mov     [rsp+288h+samDesired], 2001Fh; samDesired
0x180028f9e  mov     [rsp+288h+dwOptions], esi; dwOptions
0x180028fa2  call    cs:__imp_RegCreateKeyExW
0x180028fa8  mov     ebx, eax
0x180028faa  test    eax, eax
0x180028fac  jz      short loc_180028FD4
0x180028fae  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180028fb5  jz      short loc_180028FF8
0x180028fb7  mov     edx, 14h
0x180028fbc  mov     [rsp+288h+dwOptions], eax
0x180028fc0  mov     ecx, 40Bh
0x180028fc5  lea     r9, [rsp+288h+SubKey]
0x180028fca  mov     r8, rbp
0x180028fcd  call    WPP_SF_SD
0x180028fd2  jmp     short loc_180028FF8
0x180028fd4  xor     r9d, r9d; lpName
0x180028fd7  xor     r8d, r8d; bInitialState
0x180028fda  xor     edx, edx; bManualReset
0x180028fdc  xor     ecx, ecx; lpEventAttributes
0x180028fde  call    cs:__imp_CreateEventW
0x180028fe4  mov     cs:g_hAregWakeEvent, rax
0x180028feb  test    rax, rax
0x180028fee  jnz     short loc_180029036
0x180028ff0  call    cs:__imp_GetLastError
0x180028ff6  mov     ebx, eax
0x180028ff8  call    areg_CleanupGlobals
0x180028ffd  lea     rcx, g_AregThreadCs; lpCriticalSection
0x180029004  call    cs:__imp_LeaveCriticalSection
0x18002900a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180029011  jz      short loc_180029028
0x180029013  mov     edx, 17h
0x180029018  mov     ecx, 40Bh
0x18002901d  mov     r9d, ebx
0x180029020  mov     r8, rbp
0x180029023  call    WPP_SF_d
0x180029028  mov     eax, 0Eh
0x18002902d  test    ebx, ebx
0x18002902f  cmovnz  ebx, eax
0x180029032  mov     eax, ebx
0x180029034  jmp     short loc_1800290AE
0x180029036  lea     rax, g_AregEntryList
0x18002903d  mov     cs:g_fAregThreadRunning, esi
0x180029043  mov     cs:qword_1800AC818, rax
0x18002904a  mov     cs:g_AregEntryList, rax
0x180029051  mov     cs:g_fAregThreadStop, esi
0x180029057  mov     cs:g_fAregThreadCheckBeforeExit, esi
0x18002905d  mov     cs:g_AregThreadWaitCount, esi
0x180029063  mov     cs:g_fNoMoreUpdatess, esi
0x180029069  mov     cs:g_fAregPurge, esi
0x18002906f  mov     cs:g_fAregPurgeInitiated, esi
0x180029075  call    areg_ResetAdaptersInRegistry
0x18002907a  lea     rcx, g_AregThreadCs; lpCriticalSection
0x180029081  mov     cs:g_fAregInitialized, 1
0x18002908b  call    cs:__imp_LeaveCriticalSection
0x180029091  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180029098  jz      short loc_1800290AC
0x18002909a  mov     edx, 15h
0x18002909f  mov     r8, rbp
0x1800290a2  mov     ecx, 40Bh
0x1800290a7  call    WPP_SF_
0x1800290ac  xor     eax, eax
0x1800290ae  mov     rcx, [rsp+288h+var_18]
0x1800290b6  xor     rcx, rsp; StackCookie
0x1800290b9  call    __security_check_cookie
0x1800290be  lea     r11, [rsp+288h+var_8]
0x1800290c6  mov     rbx, [r11+10h]
0x1800290ca  mov     rbp, [r11+18h]
0x1800290ce  mov     rsp, r11
0x1800290d1  pop     rsi
0x1800290d2  retn
```
