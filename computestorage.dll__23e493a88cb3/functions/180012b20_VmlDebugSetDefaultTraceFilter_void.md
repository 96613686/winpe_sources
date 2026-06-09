# VmlDebugSetDefaultTraceFilter(void)

- ea: `0x180012b20`
- end: `0x180012e07`
- name: `?VmlDebugSetDefaultTraceFilter@@YAXXZ`
- size: `743`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016aec`
- `0x180019050`

## callees

- `0x180002690`
- `0x180008450`
- `0x180012b20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012d7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012dc9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012dde`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012d7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012dc9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012dde`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012b99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012bd5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012cfc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012b99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012bd5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012cfc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012c1e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012c55`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012c8c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012cc3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012d4f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012db4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012c1e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012c55`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012c8c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012cc3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012d4f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012db4`

## pseudocode

```c
void VmlDebugSetDefaultTraceFilter(void)
{
  __int64 i; // rcx
  int j; // ebx
  DWORD pcbData; // [rsp+40h] [rbp-29h] BYREF
  int pvData; // [rsp+44h] [rbp-25h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-21h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-19h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-11h] BYREF
  volatile __int64 *v7; // [rsp+60h] [rbp-9h] BYREF
  WCHAR Value[12]; // [rsp+68h] [rbp-1h] BYREF

  g_TraceLevel = 2;
  for ( i = 0; i != 32; ++i )
    _InterlockedExchange64((volatile __int64 *)&(&g_TraceEnabled)[i], qword_18004D3F0[i]);
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization",
          0,
          0x20019u,
          &hKey) )
  {
    pvData = 0;
    pcbData = 0;
    v7 = 0;
    hkey = 0;
    if ( !RegOpenKeyExW(hKey, L"VML", 0, 0x20019u, &hkey) )
    {
      pcbData = 4;
      RegGetValueW(hkey, 0, L"TraceFlags", 0x10u, 0, &pvData, &pcbData);
      pcbData = 4;
      RegGetValueW(hkey, 0, L"StopLevel", 0x10u, 0, &pvData, &pcbData);
      pcbData = 4;
      RegGetValueW(hkey, 0, L"DebugBreakEnabled", 0x10u, 0, &pvData, &pcbData);
      pcbData = 4;
      if ( !RegGetValueW(hkey, 0, L"TraceLevel", 0x10u, 0, &pvData, &pcbData) )
        g_TraceLevel = pvData;
      phkResult = 0;
      if ( !RegOpenKeyExW(hkey, L"TraceLevelsEnabled", 0, 0x20019u, &phkResult) )
      {
        for ( j = 0; j < 32; ++j )
        {
          swprintf_s<10>(Value, L"Trace%i", (unsigned int)j);
          pcbData = 8;
          if ( !RegGetValueW(phkResult, 0, Value, 0x40u, 0, &v7, &pcbData) )
            (&g_TraceEnabled)[j] = v7;
        }
      }
      if ( phkResult )
        RegCloseKey(phkResult);
    }
    pcbData = 4;
    RegGetValueW(hKey, 0, L"ClientAssertMask", 0x10u, 0, &pvData, &pcbData);
    if ( hkey )
      RegCloseKey(hkey);
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180012b20  push    rbp
0x180012b22  push    rbx
0x180012b23  push    rsi
0x180012b24  push    rdi
0x180012b25  push    r14
0x180012b27  push    r15
0x180012b29  lea     rbp, [rsp-2Fh]
0x180012b2e  sub     rsp, 98h
0x180012b35  mov     rax, cs:__security_cookie
0x180012b3c  xor     rax, rsp
0x180012b3f  mov     [rbp+57h+var_40], rax
0x180012b43  mov     eax, 2
0x180012b48  lea     rsi, __ImageBase
0x180012b4f  xor     edi, edi
0x180012b51  mov     cs:?g_TraceLevel@@3GA, ax; ushort g_TraceLevel
0x180012b58  mov     ecx, edi
0x180012b5a  mov     rax, ds:rva qword_18004D3F0[rsi+rcx*8]
0x180012b62  xchg    rax, rva ?g_TraceEnabled@@3RC_JC[rsi+rcx*8]; __int64 volatile near * volatile g_TraceEnabled ...
0x180012b6a  inc     rcx
0x180012b6d  cmp     rcx, 20h ; ' '
0x180012b71  jnz     short loc_180012B5A
0x180012b73  lea     rax, [rbp+57h+hKey]
0x180012b77  mov     [rbp+57h+hKey], rdi
0x180012b7b  mov     ebx, 20019h
0x180012b80  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180012b85  mov     r9d, ebx; samDesired
0x180012b88  lea     rdx, ?g_SettingsRegistryPath@Vml@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180012b8f  xor     r8d, r8d; ulOptions
0x180012b92  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012b99  call    cs:__imp_RegOpenKeyExW
0x180012ba0  nop     dword ptr [rax+rax+00h]
0x180012ba5  test    eax, eax
0x180012ba7  jnz     loc_180012DD5
0x180012bad  mov     rcx, [rbp+57h+hKey]; hKey
0x180012bb1  lea     rax, [rbp+57h+hkey]
0x180012bb5  mov     r9d, ebx; samDesired
0x180012bb8  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180012bbd  xor     r8d, r8d; ulOptions
0x180012bc0  mov     [rbp+57h+var_7C], edi
0x180012bc3  lea     rdx, ?g_VmlRegistryKeyName@Vml@@3QBGB; "VML"
0x180012bca  mov     [rbp+57h+var_80], edi
0x180012bcd  mov     [rbp+57h+var_60], rdi
0x180012bd1  mov     [rbp+57h+hkey], rdi
0x180012bd5  call    cs:__imp_RegOpenKeyExW
0x180012bdc  nop     dword ptr [rax+rax+00h]
0x180012be1  mov     r14d, 4
0x180012be7  lea     r15d, [r14+0Ch]
0x180012beb  test    eax, eax
0x180012bed  jnz     loc_180012D89
0x180012bf3  mov     rcx, [rbp+57h+hkey]; hkey
0x180012bf7  lea     rax, [rbp+57h+var_80]
0x180012bfb  mov     [rsp+0C0h+pcbData], rax; pcbData
0x180012c00  lea     r8, Value; "TraceFlags"
0x180012c07  lea     rax, [rbp+57h+var_7C]
0x180012c0b  mov     [rbp+57h+var_80], r14d
0x180012c0f  mov     [rsp+0C0h+pvData], rax; pvData
0x180012c14  mov     r9d, r15d; dwFlags
0x180012c17  xor     edx, edx; lpSubKey
0x180012c19  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x180012c1e  call    cs:__imp_RegGetValueW
0x180012c25  nop     dword ptr [rax+rax+00h]
0x180012c2a  mov     rcx, [rbp+57h+hkey]; hkey
0x180012c2e  lea     rax, [rbp+57h+var_80]
0x180012c32  mov     [rsp+0C0h+pcbData], rax; pcbData
0x180012c37  lea     r8, aStoplevel; "StopLevel"
0x180012c3e  lea     rax, [rbp+57h+var_7C]
0x180012c42  mov     [rbp+57h+var_80], r14d
0x180012c46  mov     [rsp+0C0h+pvData], rax; pvData
0x180012c4b  mov     r9d, r15d; dwFlags
0x180012c4e  xor     edx, edx; lpSubKey
0x180012c50  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x180012c55  call    cs:__imp_RegGetValueW
0x180012c5c  nop     dword ptr [rax+rax+00h]
0x180012c61  mov     rcx, [rbp+57h+hkey]; hkey
0x180012c65  lea     rax, [rbp+57h+var_80]
0x180012c69  mov     [rsp+0C0h+pcbData], rax; pcbData
0x180012c6e  lea     r8, aDebugbreakenab; "DebugBreakEnabled"
0x180012c75  lea     rax, [rbp+57h+var_7C]
0x180012c79  mov     [rbp+57h+var_80], r14d
0x180012c7d  mov     [rsp+0C0h+pvData], rax; pvData
0x180012c82  mov     r9d, r15d; dwFlags
0x180012c85  xor     edx, edx; lpSubKey
0x180012c87  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x180012c8c  call    cs:__imp_RegGetValueW
0x180012c93  nop     dword ptr [rax+rax+00h]
0x180012c98  mov     rcx, [rbp+57h+hkey]; hkey
0x180012c9c  lea     rax, [rbp+57h+var_80]
0x180012ca0  mov     [rsp+0C0h+pcbData], rax; pcbData
0x180012ca5  lea     r8, aTracelevel; "TraceLevel"
0x180012cac  lea     rax, [rbp+57h+var_7C]
0x180012cb0  mov     [rbp+57h+var_80], r14d
0x180012cb4  mov     [rsp+0C0h+pvData], rax; pvData
0x180012cb9  mov     r9d, r15d; dwFlags
0x180012cbc  xor     edx, edx; lpSubKey
0x180012cbe  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x180012cc3  call    cs:__imp_RegGetValueW
0x180012cca  nop     dword ptr [rax+rax+00h]
0x180012ccf  test    eax, eax
0x180012cd1  jnz     short loc_180012CDE
0x180012cd3  movzx   eax, word ptr [rbp+57h+var_7C]
0x180012cd7  mov     cs:?g_TraceLevel@@3GA, ax; ushort g_TraceLevel
0x180012cde  mov     rcx, [rbp+57h+hkey]; hKey
0x180012ce2  lea     rax, [rbp+57h+var_68]
0x180012ce6  mov     r9d, ebx; samDesired
0x180012ce9  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180012cee  xor     r8d, r8d; ulOptions
0x180012cf1  mov     [rbp+57h+var_68], rdi
0x180012cf5  lea     rdx, SubKey; "TraceLevelsEnabled"
0x180012cfc  call    cs:__imp_RegOpenKeyExW
0x180012d03  nop     dword ptr [rax+rax+00h]
0x180012d08  test    eax, eax
0x180012d0a  jnz     short loc_180012D74
0x180012d0c  mov     ebx, edi
0x180012d0e  mov     r8d, ebx
0x180012d11  lea     rdx, aTraceI; "Trace%i"
0x180012d18  lea     rcx, [rbp+57h+Value]
0x180012d1c  call    ??$swprintf_s@$09@@YAHAEAY09GPEBGZZ; swprintf_s<10>(ushort (&)[10],ushort const *,...)
0x180012d21  mov     rcx, [rbp+57h+var_68]; hkey
0x180012d25  lea     rax, [rbp+57h+var_80]
0x180012d29  mov     [rsp+0C0h+pcbData], rax; pcbData
0x180012d2e  lea     r8, [rbp+57h+Value]; lpValue
0x180012d32  lea     rax, [rbp+57h+var_60]
0x180012d36  mov     [rbp+57h+var_80], 8
0x180012d3d  mov     [rsp+0C0h+pvData], rax; pvData
0x180012d42  mov     r9d, 40h ; '@'; dwFlags
0x180012d48  xor     edx, edx; lpSubKey
0x180012d4a  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x180012d4f  call    cs:__imp_RegGetValueW
0x180012d56  nop     dword ptr [rax+rax+00h]
0x180012d5b  test    eax, eax
0x180012d5d  jnz     short loc_180012D6D
0x180012d5f  mov     rax, [rbp+57h+var_60]
0x180012d63  mov     ecx, ebx
0x180012d65  mov     rva ?g_TraceEnabled@@3RC_JC[rsi+rcx*8], rax; __int64 volatile near * volatile g_TraceEnabled ...
0x180012d6d  inc     ebx
0x180012d6f  cmp     ebx, 20h ; ' '
0x180012d72  jl      short loc_180012D0E
0x180012d74  mov     rcx, [rbp+57h+var_68]; hKey
0x180012d78  test    rcx, rcx
0x180012d7b  jz      short loc_180012D89
0x180012d7d  call    cs:__imp_RegCloseKey
0x180012d84  nop     dword ptr [rax+rax+00h]
0x180012d89  mov     rcx, [rbp+57h+hKey]; hkey
0x180012d8d  lea     rax, [rbp+57h+var_80]
0x180012d91  mov     [rsp+0C0h+pcbData], rax; pcbData
0x180012d96  lea     r8, ?g_DvClientAssertsMaskName@@3QBGB; "ClientAssertMask"
0x180012d9d  lea     rax, [rbp+57h+var_7C]
0x180012da1  mov     [rbp+57h+var_80], r14d
0x180012da5  mov     [rsp+0C0h+pvData], rax; pvData
0x180012daa  mov     r9d, r15d; dwFlags
0x180012dad  xor     edx, edx; lpSubKey
0x180012daf  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x180012db4  call    cs:__imp_RegGetValueW
0x180012dbb  nop     dword ptr [rax+rax+00h]
0x180012dc0  mov     rcx, [rbp+57h+hkey]; hKey
0x180012dc4  test    rcx, rcx
0x180012dc7  jz      short loc_180012DD5
0x180012dc9  call    cs:__imp_RegCloseKey
0x180012dd0  nop     dword ptr [rax+rax+00h]
0x180012dd5  mov     rcx, [rbp+57h+hKey]; hKey
0x180012dd9  test    rcx, rcx
0x180012ddc  jz      short loc_180012DEA
0x180012dde  call    cs:__imp_RegCloseKey
0x180012de5  nop     dword ptr [rax+rax+00h]
0x180012dea  mov     rcx, [rbp+57h+var_40]
0x180012dee  xor     rcx, rsp; StackCookie
0x180012df1  call    __security_check_cookie
0x180012df6  add     rsp, 98h
0x180012dfd  pop     r15
0x180012dff  pop     r14
0x180012e01  pop     rdi
0x180012e02  pop     rsi
0x180012e03  pop     rbx
0x180012e04  pop     rbp
0x180012e05  retn
```
