# UpdatePreferredVPNDestinationInRegistry

- ea: `0x1800d14d0`
- end: `0x1800d166d`
- name: `UpdatePreferredVPNDestinationInRegistry`
- size: `413`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800c5414`
- `0x1800d14d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800d150a`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800d150a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d157f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d15f0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d157f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d15f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d162e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d163d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d164c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d162e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d163d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d164c`
- `rtutils!TracePrintfExA` at `0x1800d1534`
- `rtutils!TracePrintfExA` at `0x1800d15bb`
- `rtutils!TracePrintfExA` at `0x1800d1534`
- `rtutils!TracePrintfExA` at `0x1800d15bb`

## string_xrefs

- `0x1800d1528`: `RegOpenCurrentUser failed %d`
- `0x1800d15af`: `RegCreateKey for %s failed %d`

## pseudocode

```c
__int64 __fastcall UpdatePreferredVPNDestinationInRegistry(LPCWSTR lpSubKey, __int64 a2, int a3)
{
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  const wchar_t *v7; // rdi
  const WCHAR *v8; // rdx
  LSTATUS v9; // eax
  HKEY phkResult; // [rsp+50h] [rbp-10h] BYREF
  HKEY v12; // [rsp+58h] [rbp-8h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+48h] BYREF

  hKey = 0;
  v12 = 0;
  phkResult = 0;
  v5 = RegOpenCurrentUser(0x20006u, &phkResult);
  v6 = v5;
  if ( v5 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "RegOpenCurrentUser failed %d", v5);
  }
  else
  {
    v7 = L"Software\\Microsoft\\RAS\\Preferences\\VPN\\PerUserConnections";
    v8 = L"Software\\Microsoft\\RAS\\Preferences\\VPN\\AllUserConnections";
    if ( a3 )
      v8 = L"Software\\Microsoft\\RAS\\Preferences\\VPN\\PerUserConnections";
    v6 = RegCreateKeyExW(phkResult, v8, 0, 0, 0, 0x20006u, 0, &hKey, 0);
    if ( v6 )
    {
      if ( g_dwTraceId != -1 )
      {
        if ( !a3 )
          v7 = L"Software\\Microsoft\\RAS\\Preferences\\VPN\\AllUserConnections";
        TracePrintfExA(g_dwTraceId, 0xCu, "RegCreateKey for %s failed %d", (const char *)v7, v6);
      }
    }
    else
    {
      v9 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x20006u, 0, &v12, 0);
      v6 = v9;
      if ( v9 )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "RegCreateKey for %s failed %d", (const char *)lpSubKey, v9);
      }
      else
      {
        v6 = SetRegSz(v12, L"VPN Destination");
      }
    }
  }
  if ( v12 )
    RegCloseKey(v12);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return v6;
}

```

## disassembly

```asm
0x1800d14d0  mov     [rsp-28h+arg_0], rbx
0x1800d14d5  mov     [rsp-28h+arg_8], rsi
0x1800d14da  push    rbp
0x1800d14db  push    rdi
0x1800d14dc  push    r12
0x1800d14de  push    r14
0x1800d14e0  push    r15
0x1800d14e2  mov     rbp, rsp
0x1800d14e5  sub     rsp, 60h
0x1800d14e9  xor     r12d, r12d
0x1800d14ec  mov     r15, rdx
0x1800d14ef  mov     rsi, rcx
0x1800d14f2  mov     [rbp+hKey], r12
0x1800d14f6  lea     rdx, [rbp+phkResult]; phkResult
0x1800d14fa  mov     [rbp+var_8], r12
0x1800d14fe  mov     ecx, 20006h; samDesired
0x1800d1503  mov     [rbp+phkResult], r12
0x1800d1507  mov     r14d, r8d
0x1800d150a  call    cs:__imp_RegOpenCurrentUser
0x1800d1510  mov     ebx, eax
0x1800d1512  test    eax, eax
0x1800d1514  jz      short loc_1800D153F
0x1800d1516  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800d151c  cmp     ecx, 0FFFFFFFFh
0x1800d151f  jz      loc_1800D1625
0x1800d1525  mov     r9d, eax
0x1800d1528  lea     r8, aRegopencurrent; "RegOpenCurrentUser failed %d"
0x1800d152f  lea     edx, [r12+0Ch]; dwFlags
0x1800d1534  call    cs:__imp_TracePrintfExA
0x1800d153a  jmp     loc_1800D1625
0x1800d153f  mov     rcx, [rbp+phkResult]; hKey
0x1800d1543  lea     rax, [rbp+hKey]
0x1800d1547  mov     [rsp+60h+lpdwDisposition], r12; lpdwDisposition
0x1800d154c  lea     rdi, c_szPerUserPreferenceRegKey; "Software\\Microsoft\\RAS\\Preferences\\"...
0x1800d1553  mov     [rsp+60h+var_28], rax; phkResult
0x1800d1558  lea     rdx, c_szAllUserPreferenceRegKey; "Software\\Microsoft\\RAS\\Preferences\\"...
0x1800d155f  mov     [rsp+60h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800d1564  xor     r9d, r9d; lpClass
0x1800d1567  xor     r8d, r8d; Reserved
0x1800d156a  mov     [rsp+60h+samDesired], 20006h; samDesired
0x1800d1572  mov     [rsp+60h+dwOptions], r12d; dwOptions
0x1800d1577  test    r14d, r14d
0x1800d157a  jz      short loc_1800D157F
0x1800d157c  mov     rdx, rdi; lpSubKey
0x1800d157f  call    cs:__imp_RegCreateKeyExW
0x1800d1585  mov     ebx, eax
0x1800d1587  test    eax, eax
0x1800d1589  jz      short loc_1800D15C3
0x1800d158b  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800d1591  cmp     ecx, 0FFFFFFFFh
0x1800d1594  jz      loc_1800D1625
0x1800d159a  test    r14d, r14d
0x1800d159d  mov     [rsp+60h+dwOptions], ebx
0x1800d15a1  lea     rax, c_szAllUserPreferenceRegKey; "Software\\Microsoft\\RAS\\Preferences\\"...
0x1800d15a8  cmovz   rdi, rax
0x1800d15ac  mov     r9, rdi
0x1800d15af  lea     r8, aRegcreatekeyFo; "RegCreateKey for %s failed %d"
0x1800d15b6  mov     edx, 0Ch; dwFlags
0x1800d15bb  call    cs:__imp_TracePrintfExA
0x1800d15c1  jmp     short loc_1800D1625
0x1800d15c3  mov     rcx, [rbp+hKey]; hKey
0x1800d15c7  lea     rax, [rbp+var_8]
0x1800d15cb  mov     [rsp+60h+lpdwDisposition], r12; lpdwDisposition
0x1800d15d0  xor     r9d, r9d; lpClass
0x1800d15d3  mov     [rsp+60h+var_28], rax; phkResult
0x1800d15d8  xor     r8d, r8d; Reserved
0x1800d15db  mov     [rsp+60h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800d15e0  mov     rdx, rsi; lpSubKey
0x1800d15e3  mov     [rsp+60h+samDesired], 20006h; samDesired
0x1800d15eb  mov     [rsp+60h+dwOptions], r12d; dwOptions
0x1800d15f0  call    cs:__imp_RegCreateKeyExW
0x1800d15f6  mov     ebx, eax
0x1800d15f8  test    eax, eax
0x1800d15fa  jz      short loc_1800D1610
0x1800d15fc  mov     ecx, cs:g_dwTraceId
0x1800d1602  cmp     ecx, 0FFFFFFFFh
0x1800d1605  jz      short loc_1800D1625
0x1800d1607  mov     [rsp+60h+dwOptions], eax
0x1800d160b  mov     r9, rsi
0x1800d160e  jmp     short loc_1800D15AF
0x1800d1610  mov     rcx, [rbp+var_8]; hKey
0x1800d1614  lea     rdx, c_szVPNDestination; "VPN Destination"
0x1800d161b  mov     r8, r15
0x1800d161e  call    SetRegSz
0x1800d1623  mov     ebx, eax
0x1800d1625  mov     rcx, [rbp+var_8]; hKey
0x1800d1629  test    rcx, rcx
0x1800d162c  jz      short loc_1800D1634
0x1800d162e  call    cs:__imp_RegCloseKey
0x1800d1634  mov     rcx, [rbp+hKey]; hKey
0x1800d1638  test    rcx, rcx
0x1800d163b  jz      short loc_1800D1643
0x1800d163d  call    cs:__imp_RegCloseKey
0x1800d1643  mov     rcx, [rbp+phkResult]; hKey
0x1800d1647  test    rcx, rcx
0x1800d164a  jz      short loc_1800D1652
0x1800d164c  call    cs:__imp_RegCloseKey
0x1800d1652  lea     r11, [rsp+60h+var_s0]
0x1800d1657  mov     eax, ebx
0x1800d1659  mov     rbx, [r11+30h]
0x1800d165d  mov     rsi, [r11+38h]
0x1800d1661  mov     rsp, r11
0x1800d1664  pop     r15
0x1800d1666  pop     r14
0x1800d1668  pop     r12
0x1800d166a  pop     rdi
0x1800d166b  pop     rbp
0x1800d166c  retn
```
