# GetCurrentPreferredVPNDestination

- ea: `0x1800d083c`
- end: `0x1800d09ba`
- name: `GetCurrentPreferredVPNDestination`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d0ce0`

## callees

- `0x1800c5120`
- `0x1800d083c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d08d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d0934`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d08d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d0934`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800d0876`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800d0876`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d097c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d098b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d099a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d097c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d098b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d099a`
- `rtutils!TracePrintfExA` at `0x1800d08a0`
- `rtutils!TracePrintfExA` at `0x1800d0913`
- `rtutils!TracePrintfExA` at `0x1800d08a0`
- `rtutils!TracePrintfExA` at `0x1800d0913`

## string_xrefs

- `0x1800d0894`: `RegOpenCurrentUser failed %d`
- `0x1800d0907`: `RegOpenKeyEx for %S failed %d`

## pseudocode

```c
__int64 __fastcall GetCurrentPreferredVPNDestination(int a1, const WCHAR *a2, __int64 a3)
{
  LSTATUS v6; // eax
  unsigned int RegSz; // ebx
  const wchar_t *v8; // rsi
  const WCHAR *v9; // rdx
  LSTATUS v10; // eax
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF
  HKEY v13; // [rsp+38h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+50h] BYREF

  hKey = 0;
  v13 = 0;
  phkResult = 0;
  v6 = RegOpenCurrentUser(0x20019u, &phkResult);
  RegSz = v6;
  if ( v6 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "RegOpenCurrentUser failed %d", v6);
  }
  else
  {
    v8 = L"Software\\Microsoft\\RAS\\Preferences\\VPN\\AllUserConnections";
    v9 = L"Software\\Microsoft\\RAS\\Preferences\\VPN\\AllUserConnections";
    if ( a1 )
      v9 = L"Software\\Microsoft\\RAS\\Preferences\\VPN\\PerUserConnections";
    RegSz = RegOpenKeyExW(phkResult, v9, 0, 0x20019u, &hKey);
    if ( RegSz )
    {
      if ( g_dwTraceId != -1 )
      {
        if ( a1 )
          v8 = L"Software\\Microsoft\\RAS\\Preferences\\VPN\\PerUserConnections";
        TracePrintfExA(g_dwTraceId, 0xCu, "RegOpenKeyEx for %S failed %d", v8, RegSz);
      }
    }
    else
    {
      v10 = RegOpenKeyExW(hKey, a2, 0, 0x20019u, &v13);
      RegSz = v10;
      if ( v10 )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "RegOpenKeyEx for %S failed %d", a2, v10);
      }
      else
      {
        if ( !a3 )
          return 87;
        RegSz = GetRegSz(v13, L"VPN Destination");
      }
    }
  }
  if ( v13 )
    RegCloseKey(v13);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( RegSz == 2 )
    return 846;
  return RegSz;
}

```

## disassembly

```asm
0x1800d083c  push    rbp
0x1800d083e  push    rbx
0x1800d083f  push    rsi
0x1800d0840  push    rdi
0x1800d0841  push    r14
0x1800d0843  push    r15
0x1800d0845  mov     rbp, rsp
0x1800d0848  sub     rsp, 48h
0x1800d084c  mov     r14, rdx
0x1800d084f  mov     [rbp+hKey], 0
0x1800d0857  mov     r15d, ecx
0x1800d085a  mov     [rbp+var_10], 0
0x1800d0862  lea     rdx, [rbp+phkResult]; phkResult
0x1800d0866  mov     [rbp+phkResult], 0
0x1800d086e  mov     ecx, 20019h; samDesired
0x1800d0873  mov     rdi, r8
0x1800d0876  call    cs:__imp_RegOpenCurrentUser
0x1800d087c  mov     ebx, eax
0x1800d087e  test    eax, eax
0x1800d0880  jz      short loc_1800D08AB
0x1800d0882  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800d0888  cmp     ecx, 0FFFFFFFFh
0x1800d088b  jz      loc_1800D0973
0x1800d0891  mov     r9d, eax
0x1800d0894  lea     r8, aRegopencurrent; "RegOpenCurrentUser failed %d"
0x1800d089b  mov     edx, 0Ch; dwFlags
0x1800d08a0  call    cs:__imp_TracePrintfExA
0x1800d08a6  jmp     loc_1800D0973
0x1800d08ab  mov     rcx, [rbp+phkResult]; hKey
0x1800d08af  lea     rsi, c_szAllUserPreferenceRegKey; "Software\\Microsoft\\RAS\\Preferences\\"...
0x1800d08b6  xor     r8d, r8d; ulOptions
0x1800d08b9  lea     rax, [rbp+hKey]
0x1800d08bd  mov     [rsp+48h+var_28], rax; phkResult
0x1800d08c2  mov     r9d, 20019h; samDesired
0x1800d08c8  mov     rdx, rsi
0x1800d08cb  test    r15d, r15d
0x1800d08ce  jz      short loc_1800D08D7
0x1800d08d0  lea     rdx, c_szPerUserPreferenceRegKey; "Software\\Microsoft\\RAS\\Preferences\\"...
0x1800d08d7  call    cs:__imp_RegOpenKeyExW
0x1800d08dd  mov     ebx, eax
0x1800d08df  test    eax, eax
0x1800d08e1  jz      short loc_1800D091B
0x1800d08e3  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800d08e9  cmp     ecx, 0FFFFFFFFh
0x1800d08ec  jz      loc_1800D0973
0x1800d08f2  test    r15d, r15d
0x1800d08f5  mov     dword ptr [rsp+48h+var_28], ebx
0x1800d08f9  lea     rax, c_szPerUserPreferenceRegKey; "Software\\Microsoft\\RAS\\Preferences\\"...
0x1800d0900  cmovnz  rsi, rax
0x1800d0904  mov     r9, rsi
0x1800d0907  lea     r8, aRegopenkeyexFo; "RegOpenKeyEx for %S failed %d"
0x1800d090e  mov     edx, 0Ch; dwFlags
0x1800d0913  call    cs:__imp_TracePrintfExA
0x1800d0919  jmp     short loc_1800D0973
0x1800d091b  mov     rcx, [rbp+hKey]; hKey
0x1800d091f  lea     rax, [rbp+var_10]
0x1800d0923  mov     r9d, 20019h; samDesired
0x1800d0929  mov     [rsp+48h+var_28], rax; phkResult
0x1800d092e  xor     r8d, r8d; ulOptions
0x1800d0931  mov     rdx, r14; lpSubKey
0x1800d0934  call    cs:__imp_RegOpenKeyExW
0x1800d093a  mov     ebx, eax
0x1800d093c  test    eax, eax
0x1800d093e  jz      short loc_1800D0954
0x1800d0940  mov     ecx, cs:g_dwTraceId
0x1800d0946  cmp     ecx, 0FFFFFFFFh
0x1800d0949  jz      short loc_1800D0973
0x1800d094b  mov     dword ptr [rsp+48h+var_28], eax
0x1800d094f  mov     r9, r14
0x1800d0952  jmp     short loc_1800D0907
0x1800d0954  test    rdi, rdi
0x1800d0957  jnz     short loc_1800D095E
0x1800d0959  lea     eax, [rdi+57h]
0x1800d095c  jmp     short loc_1800D09AD
0x1800d095e  mov     rcx, [rbp+var_10]; hKey
0x1800d0962  lea     rdx, c_szVPNDestination; "VPN Destination"
0x1800d0969  mov     r8, rdi
0x1800d096c  call    GetRegSz
0x1800d0971  mov     ebx, eax
0x1800d0973  mov     rcx, [rbp+var_10]; hKey
0x1800d0977  test    rcx, rcx
0x1800d097a  jz      short loc_1800D0982
0x1800d097c  call    cs:__imp_RegCloseKey
0x1800d0982  mov     rcx, [rbp+hKey]; hKey
0x1800d0986  test    rcx, rcx
0x1800d0989  jz      short loc_1800D0991
0x1800d098b  call    cs:__imp_RegCloseKey
0x1800d0991  mov     rcx, [rbp+phkResult]; hKey
0x1800d0995  test    rcx, rcx
0x1800d0998  jz      short loc_1800D09A0
0x1800d099a  call    cs:__imp_RegCloseKey
0x1800d09a0  mov     eax, 34Eh
0x1800d09a5  cmp     ebx, 2
0x1800d09a8  cmovz   ebx, eax
0x1800d09ab  mov     eax, ebx
0x1800d09ad  add     rsp, 48h
0x1800d09b1  pop     r15
0x1800d09b3  pop     r14
0x1800d09b5  pop     rdi
0x1800d09b6  pop     rsi
0x1800d09b7  pop     rbx
0x1800d09b8  pop     rbp
0x1800d09b9  retn
```
