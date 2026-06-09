# DnsConnectionManager::ReadConnectionPolicyRules(void)

- ea: `0x180075ec8`
- end: `0x180076125`
- name: `?ReadConnectionPolicyRules@DnsConnectionManager@@AEAAJXZ`
- size: `605`
- prototype: `__int64 __fastcall(DnsConnectionManager *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180086bf8`
- `0x1800ab380`

## callees

- `0x1800097e0`
- `0x180075ec8`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800abc38`
- `0x1800dc9e0`
- `0x1800ddfa8`
- `0x1800de650`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007605c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007605c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075fbf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800760d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800760ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075fbf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800760d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800760ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075fed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075fed`

## string_xrefs

- `0x180075f63`: `Dnscache`
- `0x180075f5c`: `SYSTEM\CurrentControlSet\Services\Dnscache`

## pseudocode

```c
__int64 __fastcall DnsConnectionManager::ReadConnectionPolicyRules(DnsConnectionManager *this)
{
  __int64 v2; // r9
  int v3; // eax
  signed int v4; // ebx
  DWORD v5; // edi
  DWORD i; // edx
  LSTATUS v7; // eax
  int ConnectionPolicyRule; // eax
  LPWSTR lpClass; // [rsp+28h] [rbp-D8h]
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v13; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  v13 = 0;
  hKey = 0;
  memset_0(SubKey, 0, 0x20Au);
  cchName = 261;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_q(1035, 20, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids, this);
  v3 = CreatePersistedRegistryKeyHelper(
         (__int64)L"Dnscache",
         (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
         (__int64)L"Parameters\\DnsConnections",
         v2,
         0x20019u,
         (__int64)lpClass,
         0,
         &v13);
  v4 = v3;
  if ( v3 == 2 || v3 == 1168 )
  {
    if ( (BYTE3(xmmword_1801119E0) & 0x40) != 0 )
      WPP_SF_(1054, 21, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids);
    v4 = 0;
  }
  else
  {
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    if ( v4 >= 0 )
    {
      v5 = 0;
      for ( i = 0; !RegEnumKeyExW(v13, i, SubKey, &cchName, 0, 0, 0, 0); i = v5 )
      {
        if ( hKey )
        {
          RegCloseKey(hKey);
          hKey = 0;
        }
        v7 = RegOpenKeyExW(v13, SubKey, 0, 0x20019u, &hKey);
        v4 = v7;
        if ( v7 > 0 )
          v4 = (unsigned __int16)v7 | 0x80070000;
        if ( v4 < 0 )
          break;
        ConnectionPolicyRule = DnsConnectionManager::ReadConnectionPolicyRule(this, hKey);
        if ( ConnectionPolicyRule != -2147023728 && ConnectionPolicyRule != -2147024894 )
        {
          v4 = ConnectionPolicyRule;
          if ( ConnectionPolicyRule < 0 )
            break;
        }
        ++v5;
        cchName = 261;
      }
    }
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 22, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids, (unsigned int)v4);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v13 )
    RegCloseKey(v13);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180075ec8  mov     [rsp-8+arg_8], rbx
0x180075ecd  mov     [rsp-8+arg_10], rsi
0x180075ed2  push    rbp
0x180075ed3  push    rdi
0x180075ed4  push    r14
0x180075ed6  lea     rbp, [rsp-180h]
0x180075ede  sub     rsp, 280h
0x180075ee5  mov     rax, cs:__security_cookie
0x180075eec  xor     rax, rsp
0x180075eef  mov     [rbp+190h+var_20], rax
0x180075ef6  xor     r14d, r14d
0x180075ef9  mov     rsi, rcx
0x180075efc  lea     rcx, [rsp+290h+SubKey]; void *
0x180075f01  mov     [rsp+290h+var_24C], r14d
0x180075f06  xor     edx, edx; Val
0x180075f08  mov     [rsp+290h+var_238], r14
0x180075f0d  mov     r8d, 20Ah; Size
0x180075f13  mov     [rsp+290h+hKey], r14
0x180075f18  call    memset_0
0x180075f1d  mov     [rsp+290h+cchName], 105h
0x180075f25  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180075f2c  jz      short loc_180075F46
0x180075f2e  lea     edx, [r14+14h]
0x180075f32  mov     ecx, 40Bh
0x180075f37  mov     r9, rsi
0x180075f3a  lea     r8, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids
0x180075f41  call    WPP_SF_q
0x180075f46  lea     rax, [rsp+290h+var_238]
0x180075f4b  mov     [rsp+290h+lpftLastWriteTime], rax
0x180075f50  lea     r8, aParametersDnsc; "Parameters\\DnsConnections"
0x180075f57  mov     dword ptr [rsp+290h+lpcchClass], r14d
0x180075f5c  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x180075f63  lea     rcx, aDnscache_1; "Dnscache"
0x180075f6a  mov     dword ptr [rsp+290h+phkResult], 20019h
0x180075f72  call    CreatePersistedRegistryKeyHelper
0x180075f77  mov     ebx, eax
0x180075f79  cmp     eax, 2
0x180075f7c  jz      loc_180076086
0x180075f82  cmp     eax, 490h
0x180075f87  jz      loc_180076086
0x180075f8d  test    eax, eax
0x180075f8f  jle     short loc_180075F9A
0x180075f91  movzx   ebx, ax
0x180075f94  or      ebx, 80070000h
0x180075f9a  test    ebx, ebx
0x180075f9c  jns     short loc_180075FAB
0x180075f9e  mov     [rsp+290h+var_24C], 103h
0x180075fa6  jmp     loc_1800760A8
0x180075fab  mov     edi, r14d
0x180075fae  xor     edx, edx
0x180075fb0  jmp     loc_180076039
0x180075fb5  mov     rcx, [rsp+290h+hKey]; hKey
0x180075fba  test    rcx, rcx
0x180075fbd  jz      short loc_180075FD0
0x180075fbf  call    cs:__imp_RegCloseKey
0x180075fc6  nop     dword ptr [rax+rax+00h]
0x180075fcb  mov     [rsp+290h+hKey], r14
0x180075fd0  mov     rcx, [rsp+290h+var_238]; hKey
0x180075fd5  lea     rax, [rsp+290h+hKey]
0x180075fda  mov     r9d, 20019h; samDesired
0x180075fe0  mov     [rsp+290h+phkResult], rax; phkResult
0x180075fe5  xor     r8d, r8d; ulOptions
0x180075fe8  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x180075fed  call    cs:__imp_RegOpenKeyExW
0x180075ff4  nop     dword ptr [rax+rax+00h]
0x180075ff9  mov     ebx, eax
0x180075ffb  test    eax, eax
0x180075ffd  jle     short loc_180076008
0x180075fff  movzx   ebx, ax
0x180076002  or      ebx, 80070000h
0x180076008  test    ebx, ebx
0x18007600a  js      short loc_18007607C
0x18007600c  mov     rdx, [rsp+290h+hKey]; hkey
0x180076011  mov     rcx, rsi; this
0x180076014  call    ?ReadConnectionPolicyRule@DnsConnectionManager@@AEAAJPEAUHKEY__@@@Z; DnsConnectionManager::ReadConnectionPolicyRule(HKEY__ *)
0x180076019  cmp     eax, 80070490h
0x18007601e  jz      short loc_18007602D
0x180076020  cmp     eax, 80070002h
0x180076025  jz      short loc_18007602D
0x180076027  mov     ebx, eax
0x180076029  test    eax, eax
0x18007602b  js      short loc_180076072
0x18007602d  inc     edi
0x18007602f  mov     [rsp+290h+cchName], 105h
0x180076037  mov     edx, edi; dwIndex
0x180076039  mov     rcx, [rsp+290h+var_238]; hKey
0x18007603e  lea     r9, [rsp+290h+cchName]; lpcchName
0x180076043  mov     [rsp+290h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180076048  lea     r8, [rsp+290h+SubKey]; lpName
0x18007604d  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180076052  mov     [rsp+290h+lpClass], r14; lpClass
0x180076057  mov     [rsp+290h+phkResult], r14; lpReserved
0x18007605c  call    cs:__imp_RegEnumKeyExW
0x180076063  nop     dword ptr [rax+rax+00h]
0x180076068  test    eax, eax
0x18007606a  jz      loc_180075FB5
0x180076070  jmp     short loc_1800760A8
0x180076072  mov     [rsp+290h+var_24C], 126h
0x18007607a  jmp     short loc_1800760A8
0x18007607c  mov     [rsp+290h+var_24C], 117h
0x180076084  jmp     short loc_1800760A8
0x180076086  test    byte ptr cs:xmmword_1801119E0+3, 40h
0x18007608d  jz      short loc_1800760A5
0x18007608f  mov     edx, 15h
0x180076094  lea     r8, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids
0x18007609b  mov     ecx, 41Eh
0x1800760a0  call    WPP_SF_
0x1800760a5  mov     ebx, r14d
0x1800760a8  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800760af  jz      short loc_1800760CA
0x1800760b1  mov     edx, 16h
0x1800760b6  lea     r8, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids
0x1800760bd  mov     ecx, 40Bh
0x1800760c2  mov     r9d, ebx
0x1800760c5  call    WPP_SF_d
0x1800760ca  mov     rcx, [rsp+290h+hKey]; hKey
0x1800760cf  test    rcx, rcx
0x1800760d2  jz      short loc_1800760E5
0x1800760d4  call    cs:__imp_RegCloseKey
0x1800760db  nop     dword ptr [rax+rax+00h]
0x1800760e0  mov     [rsp+290h+hKey], r14
0x1800760e5  mov     rcx, [rsp+290h+var_238]; hKey
0x1800760ea  test    rcx, rcx
0x1800760ed  jz      short loc_1800760FB
0x1800760ef  call    cs:__imp_RegCloseKey
0x1800760f6  nop     dword ptr [rax+rax+00h]
0x1800760fb  mov     eax, ebx
0x1800760fd  mov     rcx, [rbp+190h+var_20]
0x180076104  xor     rcx, rsp; StackCookie
0x180076107  call    __security_check_cookie
0x18007610c  lea     r11, [rsp+290h+var_10]
0x180076114  mov     rbx, [r11+28h]
0x180076118  mov     rsi, [r11+30h]
0x18007611c  mov     rsp, r11
0x18007611f  pop     r14
0x180076121  pop     rdi
0x180076122  pop     rbp
0x180076123  retn
```
