# Dhcpv6IsEnabled

- ea: `0x180003240`
- end: `0x1800034c5`
- name: `Dhcpv6IsEnabled`
- size: `645`
- prototype: `__int64 __fastcall(const WCHAR *, int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180001ff0`
- `0x1800023b0`
- `0x180002400`
- `0x180002dd0`
- `0x180003240`
- `0x1800034d0`
- `0x180003a90`
- `0x1800081c0`
- `0x180008490`

## import_xrefs

- `ntdll!RtlStringFromGUID` at `0x180003349`
- `ntdll!RtlStringFromGUID` at `0x180003349`
- `ntdll!RtlFreeUnicodeString` at `0x18000344a`
- `ntdll!RtlFreeUnicodeString` at `0x18000344a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000345d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003470`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000345d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003470`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800033fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800033fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003312`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000337b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003312`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000337b`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x18000332a`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x18000332a`

## string_xrefs

- `0x1800032e7`: `System\CurrentControlSet\Services\Tcpip6\Parameters\Interfaces`

## pseudocode

```c
__int64 __fastcall Dhcpv6IsEnabled(const WCHAR *a1, int *a2)
{
  unsigned int v4; // ebx
  int IsWCOSSystem; // eax
  const WCHAR *v6; // rdx
  unsigned int v7; // eax
  unsigned int v8; // eax
  int v9; // r14d
  const WCHAR *Buffer; // rbx
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned int EnabledDhcpFromMultipleLocations; // eax
  LSTATUS v14; // eax
  int v15; // ecx
  BYTE Data[4]; // [rsp+30h] [rbp-50h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-4Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-48h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-40h] BYREF
  DWORD Type; // [rsp+48h] [rbp-38h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+50h] [rbp-30h] BYREF
  NET_LUID InterfaceLuid; // [rsp+60h] [rbp-20h] BYREF
  GUID InterfaceGuid; // [rsp+68h] [rbp-18h] BYREF

  cbData = 4;
  InterfaceLuid.Value = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  phkResult = 0;
  hKey = 0;
  GuidString = 0;
  InterfaceGuid = 0;
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_S(a1, 62, WPP_cb48999f8e5838f952918348529d50de_Traceguids, a1);
  if ( a1 && a2 )
  {
    v4 = Dhcpv6AdapterNameToIfId(a1, &InterfaceLuid);
    if ( !v4 )
    {
      IsWCOSSystem = DhcpIsWCOSSystem();
      v6 = L"OSDATA\\Networking\\Dhcp\\Client6";
      if ( !IsWCOSSystem )
        v6 = L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Interfaces";
      v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &hKey);
      if ( !v4 )
      {
        v7 = ConvertInterfaceLuidToGuid(&InterfaceLuid, &InterfaceGuid);
        v4 = Win32FromNTSTATUS(v7);
        if ( !v4 )
        {
          v8 = RtlStringFromGUID(&InterfaceGuid, &GuidString);
          v4 = Win32FromNTSTATUS(v8);
          if ( !v4 )
          {
            v9 = 1;
            v4 = RegOpenKeyExW(hKey, GuidString.Buffer, 0, 1u, &phkResult);
            if ( !v4 )
            {
              Buffer = GuidString.Buffer;
              if ( (unsigned int)DhcpIsWCOSSystem() )
                EnabledDhcpFromMultipleLocations = DhcpRegReadEnabledDhcpFromMultipleLocations(v12, v11, Buffer, Data);
              else
                EnabledDhcpFromMultipleLocations = DhcpRegReadEnabledDhcp(
                                                     L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Interfaces",
                                                     Buffer,
                                                     Data);
              v4 = EnabledDhcpFromMultipleLocations;
              if ( EnabledDhcpFromMultipleLocations )
              {
                if ( EnabledDhcpFromMultipleLocations != 2 )
                  goto LABEL_30;
              }
              else if ( !*(_DWORD *)Data )
              {
                *a2 = 0;
                goto LABEL_30;
              }
              *(_DWORD *)Data = 0;
              cbData = 4;
              v14 = RegQueryValueExW(phkResult, L"Dhcpv6State", 0, &Type, Data, &cbData);
              v4 = v14;
              if ( v14 == 2 )
              {
                *a2 = 0;
                v4 = 0;
                goto LABEL_30;
              }
              if ( !v14 )
              {
                if ( *(_DWORD *)Data )
                {
                  if ( *(_DWORD *)Data == 1 )
                  {
LABEL_28:
                    *a2 = v9;
                    goto LABEL_30;
                  }
                  if ( *(_DWORD *)Data != 2 )
                  {
                    if ( *(_DWORD *)Data != 3 )
                    {
                      v4 = 1627;
                      goto LABEL_30;
                    }
                    goto LABEL_28;
                  }
                }
                v9 = 2;
                goto LABEL_28;
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v4 = 87;
  }
LABEL_30:
  if ( GuidString.Buffer )
  {
    RtlFreeUnicodeString(&GuidString);
    GuidString.Buffer = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v15 = (int)phkResult;
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_SD(v15, 63, (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids, (_DWORD)a1, v4);
  return v4;
}

```

## disassembly

```asm
0x180003240  mov     [rsp-28h+arg_10], rbx
0x180003245  mov     [rsp-28h+arg_18], rsi
0x18000324a  push    rbp
0x18000324b  push    rdi
0x18000324c  push    r12
0x18000324e  push    r14
0x180003250  push    r15
0x180003252  mov     rbp, rsp
0x180003255  sub     rsp, 80h
0x18000325c  mov     rax, cs:__security_cookie
0x180003263  xor     rax, rsp
0x180003266  mov     [rbp+var_8], rax
0x18000326a  xor     r15d, r15d
0x18000326d  mov     [rbp+cbData], 4
0x180003274  xorps   xmm0, xmm0
0x180003277  mov     qword ptr [rbp+InterfaceLuid], r15
0x18000327b  xorps   xmm1, xmm1
0x18000327e  mov     [rbp+Type], r15d
0x180003282  mov     dword ptr [rbp+Data], r15d
0x180003286  mov     rdi, rdx
0x180003289  mov     [rbp+var_40], r15
0x18000328d  mov     rsi, rcx
0x180003290  mov     [rbp+hKey], r15
0x180003294  movups  xmmword ptr [rbp+GuidString.Length], xmm0
0x180003298  movups  xmmword ptr [rbp+InterfaceGuid.Data1], xmm1
0x18000329c  test    byte ptr cs:xmmword_18000F160, 10h
0x1800032a3  jz      short loc_1800032B8
0x1800032a5  lea     edx, [r15+3Eh]
0x1800032a9  mov     r9, rcx
0x1800032ac  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x1800032b3  call    WPP_SF_S
0x1800032b8  test    rsi, rsi
0x1800032bb  jz      loc_18000343B
0x1800032c1  test    rdi, rdi
0x1800032c4  jz      loc_18000343B
0x1800032ca  lea     rdx, [rbp+InterfaceLuid]
0x1800032ce  mov     rcx, rsi
0x1800032d1  call    Dhcpv6AdapterNameToIfId
0x1800032d6  mov     ebx, eax
0x1800032d8  test    eax, eax
0x1800032da  jnz     loc_180003440
0x1800032e0  call    DhcpIsWCOSSystem
0x1800032e5  test    eax, eax
0x1800032e7  lea     r12, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x1800032ee  lea     rax, [rbp+hKey]
0x1800032f2  mov     r9d, 20019h; samDesired
0x1800032f8  lea     rdx, aOsdataNetworki; "OSDATA\\Networking\\Dhcp\\Client6"
0x1800032ff  mov     [rsp+80h+phkResult], rax; phkResult
0x180003304  cmovz   rdx, r12; lpSubKey
0x180003308  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000330f  xor     r8d, r8d; ulOptions
0x180003312  call    cs:__imp_RegOpenKeyExW
0x180003318  mov     ebx, eax
0x18000331a  test    eax, eax
0x18000331c  jnz     loc_180003440
0x180003322  lea     rdx, [rbp+InterfaceGuid]; InterfaceGuid
0x180003326  lea     rcx, [rbp+InterfaceLuid]; InterfaceLuid
0x18000332a  call    cs:__imp_ConvertInterfaceLuidToGuid
0x180003330  mov     ecx, eax
0x180003332  call    Win32FromNTSTATUS
0x180003337  mov     ebx, eax
0x180003339  test    eax, eax
0x18000333b  jnz     loc_180003440
0x180003341  lea     rdx, [rbp+GuidString]; GuidString
0x180003345  lea     rcx, [rbp+InterfaceGuid]; Guid
0x180003349  call    cs:__imp_RtlStringFromGUID
0x18000334f  mov     ecx, eax
0x180003351  call    Win32FromNTSTATUS
0x180003356  mov     ebx, eax
0x180003358  test    eax, eax
0x18000335a  jnz     loc_180003440
0x180003360  mov     rdx, [rbp+GuidString.Buffer]; lpSubKey
0x180003364  lea     rax, [rbp+var_40]
0x180003368  mov     rcx, [rbp+hKey]; hKey
0x18000336c  lea     r14d, [rbx+1]
0x180003370  mov     r9d, r14d; samDesired
0x180003373  mov     [rsp+80h+phkResult], rax; phkResult
0x180003378  xor     r8d, r8d; ulOptions
0x18000337b  call    cs:__imp_RegOpenKeyExW
0x180003381  mov     ebx, eax
0x180003383  test    eax, eax
0x180003385  jnz     loc_180003440
0x18000338b  mov     rbx, [rbp+GuidString.Buffer]
0x18000338f  call    DhcpIsWCOSSystem
0x180003394  test    eax, eax
0x180003396  jz      short loc_1800033A6
0x180003398  lea     r9, [rbp+Data]
0x18000339c  mov     r8, rbx
0x18000339f  call    DhcpRegReadEnabledDhcpFromMultipleLocations
0x1800033a4  jmp     short loc_1800033B5
0x1800033a6  lea     r8, [rbp+Data]
0x1800033aa  mov     rdx, rbx; LPCWSTR
0x1800033ad  mov     rcx, r12; lpSubKey
0x1800033b0  call    DhcpRegReadEnabledDhcp
0x1800033b5  mov     ebx, eax
0x1800033b7  test    eax, eax
0x1800033b9  jnz     short loc_1800033C6
0x1800033bb  cmp     dword ptr [rbp+Data], r15d
0x1800033bf  jnz     short loc_1800033CB
0x1800033c1  mov     [rdi], r15d
0x1800033c4  jmp     short loc_180003440
0x1800033c6  cmp     ebx, 2
0x1800033c9  jnz     short loc_180003440
0x1800033cb  mov     rcx, [rbp+var_40]; hKey
0x1800033cf  lea     rax, [rbp+cbData]
0x1800033d3  mov     [rsp+80h+lpcbData], rax; lpcbData
0x1800033d8  lea     r9, [rbp+Type]; lpType
0x1800033dc  lea     rax, [rbp+Data]
0x1800033e0  mov     dword ptr [rbp+Data], r15d
0x1800033e4  xor     r8d, r8d; lpReserved
0x1800033e7  mov     [rsp+80h+phkResult], rax; lpData
0x1800033ec  lea     rdx, aDhcpv6state; "Dhcpv6State"
0x1800033f3  mov     [rbp+cbData], 4
0x1800033fa  call    cs:__imp_RegQueryValueExW
0x180003400  mov     ebx, eax
0x180003402  cmp     eax, 2
0x180003405  jnz     short loc_18000340F
0x180003407  mov     [rdi], r15d
0x18000340a  mov     ebx, r15d
0x18000340d  jmp     short loc_180003440
0x18000340f  test    eax, eax
0x180003411  jnz     short loc_180003440
0x180003413  mov     eax, dword ptr [rbp+Data]
0x180003416  test    eax, eax
0x180003418  jz      short loc_180003430
0x18000341a  sub     eax, r14d
0x18000341d  jz      short loc_180003436
0x18000341f  sub     eax, r14d
0x180003422  jz      short loc_180003430
0x180003424  cmp     eax, r14d
0x180003427  jz      short loc_180003436
0x180003429  mov     ebx, 65Bh
0x18000342e  jmp     short loc_180003440
0x180003430  mov     r14d, 2
0x180003436  mov     [rdi], r14d
0x180003439  jmp     short loc_180003440
0x18000343b  mov     ebx, 57h ; 'W'
0x180003440  cmp     [rbp+GuidString.Buffer], r15
0x180003444  jz      short loc_180003454
0x180003446  lea     rcx, [rbp+GuidString]; UnicodeString
0x18000344a  call    cs:__imp_RtlFreeUnicodeString
0x180003450  mov     [rbp+GuidString.Buffer], r15
0x180003454  mov     rcx, [rbp+hKey]; hKey
0x180003458  test    rcx, rcx
0x18000345b  jz      short loc_180003467
0x18000345d  call    cs:__imp_RegCloseKey
0x180003463  mov     [rbp+hKey], r15
0x180003467  mov     rcx, [rbp+var_40]; hKey
0x18000346b  test    rcx, rcx
0x18000346e  jz      short loc_18000347A
0x180003470  call    cs:__imp_RegCloseKey
0x180003476  mov     [rbp+var_40], r15
0x18000347a  test    byte ptr cs:xmmword_18000F160, 10h
0x180003481  jz      short loc_18000349B
0x180003483  mov     edx, 3Fh ; '?'
0x180003488  mov     dword ptr [rsp+80h+phkResult], ebx
0x18000348c  mov     r9, rsi
0x18000348f  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180003496  call    WPP_SF_SD
0x18000349b  mov     eax, ebx
0x18000349d  mov     rcx, [rbp+var_8]
0x1800034a1  xor     rcx, rsp; StackCookie
0x1800034a4  call    __security_check_cookie
0x1800034a9  lea     r11, [rsp+80h+var_s0]
0x1800034b1  mov     rbx, [r11+40h]
0x1800034b5  mov     rsi, [r11+48h]
0x1800034b9  mov     rsp, r11
0x1800034bc  pop     r15
0x1800034be  pop     r14
0x1800034c0  pop     r12
0x1800034c2  pop     rdi
0x1800034c3  pop     rbp
0x1800034c4  retn
```
