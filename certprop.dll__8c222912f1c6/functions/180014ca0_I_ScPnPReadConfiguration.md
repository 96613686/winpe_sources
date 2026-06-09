# I_ScPnPReadConfiguration

- ea: `0x180014ca0`
- end: `0x180014e7f`
- name: `I_ScPnPReadConfiguration`
- size: `479`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ec48`

## callees

- `0x180004600`
- `0x180014ca0`
- `0x180018b58`
- `0x180018bb4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014d27`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014d27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014e2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014e2a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014d67`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014d99`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014dd3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014e05`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014d67`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014d99`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014dd3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014e05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d33`

## pseudocode

```c
__int64 __fastcall I_ScPnPReadConfiguration(__int64 a1)
{
  DWORD LastError; // edi
  HKEY v2; // rcx
  DWORD v3; // ebx
  int Data; // [rsp+60h] [rbp+30h] BYREF
  DWORD Type; // [rsp+68h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+48h] BYREF

  hKey = 0;
  cbData = 0;
  Data = 0;
  Type = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids, WPP_pszIndent);
  }
  g_fEnableScPnP = 1;
  LastError = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows\\ScPnP", 0, 0x20019u, &hKey);
  if ( LastError )
  {
    LastError = GetLastError();
  }
  else
  {
    cbData = 4;
    Data = 0;
    if ( !RegQueryValueExW(hKey, L"EnableScPnP", 0, &Type, 0, 0)
      && Type == 4
      && !RegQueryValueExW(hKey, L"EnableScPnP", 0, 0, (LPBYTE)&Data, &cbData) )
    {
      g_fEnableScPnP = Data != 0;
    }
    Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"ScPnPNotification", 0, &Type, 0, 0)
      && Type == 4
      && !RegQueryValueExW(hKey, L"ScPnPNotification", 0, 0, (LPBYTE)&Data, &cbData) )
    {
      g_fScPnPNotification = Data != 0;
    }
  }
  v2 = hKey;
  v3 = 0;
  if ( LastError != 2 )
    v3 = LastError;
  if ( hKey )
    RegCloseKey(hKey);
  WppTraceIndent(v2, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      75,
      (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
      WPP_pszIndent,
      v3);
  }
  return v3;
}

```

## disassembly

```asm
0x180014ca0  push    rbp
0x180014ca2  push    rbx
0x180014ca3  push    rsi
0x180014ca4  push    rdi
0x180014ca5  push    r14
0x180014ca7  mov     rbp, rsp
0x180014caa  sub     rsp, 30h
0x180014cae  xor     esi, esi
0x180014cb0  xor     edx, edx
0x180014cb2  mov     [rbp+hKey], rsi
0x180014cb6  mov     [rbp+cbData], esi
0x180014cb9  mov     [rbp+Data], esi
0x180014cbc  mov     [rbp+Type], esi
0x180014cbf  call    WppTraceIndent
0x180014cc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ccb  lea     r14, WPP_GLOBAL_Control
0x180014cd2  cmp     rcx, r14
0x180014cd5  jz      short loc_180014CFD
0x180014cd7  test    byte ptr [rcx+1Ch], 2
0x180014cdb  jz      short loc_180014CFD
0x180014cdd  cmp     byte ptr [rcx+19h], 5
0x180014ce1  jb      short loc_180014CFD
0x180014ce3  mov     r9, cs:WPP_pszIndent
0x180014cea  lea     edx, [rsi+4Ah]
0x180014ced  mov     rcx, [rcx+10h]
0x180014cf1  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x180014cf8  call    WPP_SF_s
0x180014cfd  lea     rax, [rbp+hKey]
0x180014d01  mov     cs:g_fEnableScPnP, 1
0x180014d0b  mov     r9d, 20019h; samDesired
0x180014d11  mov     [rsp+30h+phkResult], rax; phkResult
0x180014d16  xor     r8d, r8d; ulOptions
0x180014d19  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows"...
0x180014d20  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014d27  call    cs:__imp_RegOpenKeyExW
0x180014d2d  mov     edi, eax
0x180014d2f  test    eax, eax
0x180014d31  jz      short loc_180014D40
0x180014d33  call    cs:__imp_GetLastError
0x180014d39  mov     edi, eax
0x180014d3b  jmp     loc_180014E19
0x180014d40  mov     rcx, [rbp+hKey]; hKey
0x180014d44  lea     r9, [rbp+Type]; lpType
0x180014d48  mov     ebx, 4
0x180014d4d  mov     [rsp+30h+lpcbData], rsi; lpcbData
0x180014d52  xor     r8d, r8d; lpReserved
0x180014d55  mov     [rbp+cbData], ebx
0x180014d58  lea     rdx, ValueName; "EnableScPnP"
0x180014d5f  mov     [rbp+Data], esi
0x180014d62  mov     [rsp+30h+phkResult], rsi; lpData
0x180014d67  call    cs:__imp_RegQueryValueExW
0x180014d6d  test    eax, eax
0x180014d6f  jnz     short loc_180014DB1
0x180014d71  cmp     [rbp+Type], ebx
0x180014d74  jnz     short loc_180014DB1
0x180014d76  mov     rcx, [rbp+hKey]; hKey
0x180014d7a  lea     rax, [rbp+cbData]
0x180014d7e  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180014d83  lea     rdx, ValueName; "EnableScPnP"
0x180014d8a  lea     rax, [rbp+Data]
0x180014d8e  xor     r9d, r9d; lpType
0x180014d91  xor     r8d, r8d; lpReserved
0x180014d94  mov     [rsp+30h+phkResult], rax; lpData
0x180014d99  call    cs:__imp_RegQueryValueExW
0x180014d9f  test    eax, eax
0x180014da1  jnz     short loc_180014DB1
0x180014da3  cmp     [rbp+Data], esi
0x180014da6  mov     eax, esi
0x180014da8  setnz   al
0x180014dab  mov     cs:g_fEnableScPnP, eax
0x180014db1  mov     rcx, [rbp+hKey]; hKey
0x180014db5  lea     r9, [rbp+Type]; lpType
0x180014db9  mov     [rsp+30h+lpcbData], rsi; lpcbData
0x180014dbe  lea     rdx, aScpnpnotificat; "ScPnPNotification"
0x180014dc5  xor     r8d, r8d; lpReserved
0x180014dc8  mov     [rsp+30h+phkResult], rsi; lpData
0x180014dcd  mov     [rbp+Data], esi
0x180014dd0  mov     [rbp+cbData], ebx
0x180014dd3  call    cs:__imp_RegQueryValueExW
0x180014dd9  test    eax, eax
0x180014ddb  jnz     short loc_180014E19
0x180014ddd  cmp     [rbp+Type], ebx
0x180014de0  jnz     short loc_180014E19
0x180014de2  mov     rcx, [rbp+hKey]; hKey
0x180014de6  lea     rax, [rbp+cbData]
0x180014dea  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180014def  lea     rdx, aScpnpnotificat; "ScPnPNotification"
0x180014df6  lea     rax, [rbp+Data]
0x180014dfa  xor     r9d, r9d; lpType
0x180014dfd  xor     r8d, r8d; lpReserved
0x180014e00  mov     [rsp+30h+phkResult], rax; lpData
0x180014e05  call    cs:__imp_RegQueryValueExW
0x180014e0b  test    eax, eax
0x180014e0d  jnz     short loc_180014E19
0x180014e0f  cmp     [rbp+Data], esi
0x180014e12  setnz   cs:g_fScPnPNotification
0x180014e19  mov     rcx, [rbp+hKey]; hKey
0x180014e1d  cmp     edi, 2
0x180014e20  mov     ebx, esi
0x180014e22  cmovnz  ebx, edi
0x180014e25  test    rcx, rcx
0x180014e28  jz      short loc_180014E30
0x180014e2a  call    cs:__imp_RegCloseKey
0x180014e30  mov     edx, 1
0x180014e35  call    WppTraceIndent
0x180014e3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e41  cmp     rcx, r14
0x180014e44  jz      short loc_180014E72
0x180014e46  test    byte ptr [rcx+1Ch], 2
0x180014e4a  jz      short loc_180014E72
0x180014e4c  cmp     byte ptr [rcx+19h], 5
0x180014e50  jb      short loc_180014E72
0x180014e52  mov     r9, cs:WPP_pszIndent
0x180014e59  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x180014e60  mov     rcx, [rcx+10h]
0x180014e64  mov     edx, 4Bh ; 'K'
0x180014e69  mov     dword ptr [rsp+30h+phkResult], ebx
0x180014e6d  call    WPP_SF_sD
0x180014e72  mov     eax, ebx
0x180014e74  add     rsp, 30h
0x180014e78  pop     r14
0x180014e7a  pop     rdi
0x180014e7b  pop     rsi
0x180014e7c  pop     rbx
0x180014e7d  pop     rbp
0x180014e7e  retn
```
