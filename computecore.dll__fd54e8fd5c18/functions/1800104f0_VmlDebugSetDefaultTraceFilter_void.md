# VmlDebugSetDefaultTraceFilter(void)

- ea: `0x1800104f0`
- end: `0x18001078e`
- name: `?VmlDebugSetDefaultTraceFilter@@YAXXZ`
- size: `670`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b0fc`
- `0x1800107a0`

## callees

- `0x1800067c0`
- `0x180009908`
- `0x1800104f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001071d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001075d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001076c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001071d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001075d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001076c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010569`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001059f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800106a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010569`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001059f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800106a8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800105e2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010613`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010644`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010675`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800106f5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001074e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800105e2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010613`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010644`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010675`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800106f5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001074e`

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
    _InterlockedExchange64((volatile __int64 *)&(&g_TraceEnabled)[i], qword_1800AE1B0[i]);
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
0x1800104f0  push    rbp
0x1800104f2  push    rbx
0x1800104f3  push    rsi
0x1800104f4  push    rdi
0x1800104f5  push    r14
0x1800104f7  push    r15
0x1800104f9  lea     rbp, [rsp-2Fh]
0x1800104fe  sub     rsp, 98h
0x180010505  mov     rax, cs:__security_cookie
0x18001050c  xor     rax, rsp
0x18001050f  mov     [rbp+57h+var_40], rax
0x180010513  mov     eax, 2
0x180010518  lea     rsi, __ImageBase
0x18001051f  xor     edi, edi
0x180010521  mov     cs:?g_TraceLevel@@3GA, ax; ushort g_TraceLevel
0x180010528  mov     ecx, edi
0x18001052a  mov     rax, ds:rva qword_1800AE1B0[rsi+rcx*8]
0x180010532  xchg    rax, rva ?g_TraceEnabled@@3RC_JC[rsi+rcx*8]; __int64 volatile near * volatile g_TraceEnabled ...
0x18001053a  inc     rcx
0x18001053d  cmp     rcx, 20h ; ' '
0x180010541  jnz     short loc_18001052A
0x180010543  lea     rax, [rbp+57h+hKey]
0x180010547  mov     [rbp+57h+hKey], rdi
0x18001054b  mov     ebx, 20019h
0x180010550  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180010555  mov     r9d, ebx; samDesired
0x180010558  lea     rdx, ?g_SettingsRegistryPath@Vml@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001055f  xor     r8d, r8d; ulOptions
0x180010562  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010569  call    cs:__imp_RegOpenKeyExW
0x18001056f  test    eax, eax
0x180010571  jnz     loc_180010763
0x180010577  mov     rcx, [rbp+57h+hKey]; hKey
0x18001057b  lea     rax, [rbp+57h+hkey]
0x18001057f  mov     r9d, ebx; samDesired
0x180010582  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180010587  xor     r8d, r8d; ulOptions
0x18001058a  mov     [rbp+57h+var_7C], edi
0x18001058d  lea     rdx, ?g_VmlRegistryKeyName@Vml@@3QBGB; "VML"
0x180010594  mov     [rbp+57h+var_80], edi
0x180010597  mov     [rbp+57h+var_60], rdi
0x18001059b  mov     [rbp+57h+hkey], rdi
0x18001059f  call    cs:__imp_RegOpenKeyExW
0x1800105a5  mov     r14d, 4
0x1800105ab  lea     r15d, [r14+0Ch]
0x1800105af  test    eax, eax
0x1800105b1  jnz     loc_180010723
0x1800105b7  mov     rcx, [rbp+57h+hkey]; hkey
0x1800105bb  lea     rax, [rbp+57h+var_80]
0x1800105bf  mov     [rsp+0C0h+pcbData], rax; pcbData
0x1800105c4  lea     r8, aTraceflags; "TraceFlags"
0x1800105cb  lea     rax, [rbp+57h+var_7C]
0x1800105cf  mov     [rbp+57h+var_80], r14d
0x1800105d3  mov     [rsp+0C0h+pvData], rax; pvData
0x1800105d8  mov     r9d, r15d; dwFlags
0x1800105db  xor     edx, edx; lpSubKey
0x1800105dd  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x1800105e2  call    cs:__imp_RegGetValueW
0x1800105e8  mov     rcx, [rbp+57h+hkey]; hkey
0x1800105ec  lea     rax, [rbp+57h+var_80]
0x1800105f0  mov     [rsp+0C0h+pcbData], rax; pcbData
0x1800105f5  lea     r8, aStoplevel; "StopLevel"
0x1800105fc  lea     rax, [rbp+57h+var_7C]
0x180010600  mov     [rbp+57h+var_80], r14d
0x180010604  mov     [rsp+0C0h+pvData], rax; pvData
0x180010609  mov     r9d, r15d; dwFlags
0x18001060c  xor     edx, edx; lpSubKey
0x18001060e  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x180010613  call    cs:__imp_RegGetValueW
0x180010619  mov     rcx, [rbp+57h+hkey]; hkey
0x18001061d  lea     rax, [rbp+57h+var_80]
0x180010621  mov     [rsp+0C0h+pcbData], rax; pcbData
0x180010626  lea     r8, aDebugbreakenab; "DebugBreakEnabled"
0x18001062d  lea     rax, [rbp+57h+var_7C]
0x180010631  mov     [rbp+57h+var_80], r14d
0x180010635  mov     [rsp+0C0h+pvData], rax; pvData
0x18001063a  mov     r9d, r15d; dwFlags
0x18001063d  xor     edx, edx; lpSubKey
0x18001063f  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x180010644  call    cs:__imp_RegGetValueW
0x18001064a  mov     rcx, [rbp+57h+hkey]; hkey
0x18001064e  lea     rax, [rbp+57h+var_80]
0x180010652  mov     [rsp+0C0h+pcbData], rax; pcbData
0x180010657  lea     r8, aTracelevel; "TraceLevel"
0x18001065e  lea     rax, [rbp+57h+var_7C]
0x180010662  mov     [rbp+57h+var_80], r14d
0x180010666  mov     [rsp+0C0h+pvData], rax; pvData
0x18001066b  mov     r9d, r15d; dwFlags
0x18001066e  xor     edx, edx; lpSubKey
0x180010670  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x180010675  call    cs:__imp_RegGetValueW
0x18001067b  test    eax, eax
0x18001067d  jnz     short loc_18001068A
0x18001067f  movzx   eax, word ptr [rbp+57h+var_7C]
0x180010683  mov     cs:?g_TraceLevel@@3GA, ax; ushort g_TraceLevel
0x18001068a  mov     rcx, [rbp+57h+hkey]; hKey
0x18001068e  lea     rax, [rbp+57h+var_68]
0x180010692  mov     r9d, ebx; samDesired
0x180010695  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18001069a  xor     r8d, r8d; ulOptions
0x18001069d  mov     [rbp+57h+var_68], rdi
0x1800106a1  lea     rdx, SubKey; "TraceLevelsEnabled"
0x1800106a8  call    cs:__imp_RegOpenKeyExW
0x1800106ae  test    eax, eax
0x1800106b0  jnz     short loc_180010714
0x1800106b2  mov     ebx, edi
0x1800106b4  mov     r8d, ebx
0x1800106b7  lea     rdx, aTraceI; "Trace%i"
0x1800106be  lea     rcx, [rbp+57h+Value]
0x1800106c2  call    ??$swprintf_s@$09@@YAHAEAY09GPEBGZZ; swprintf_s<10>(ushort (&)[10],ushort const *,...)
0x1800106c7  mov     rcx, [rbp+57h+var_68]; hkey
0x1800106cb  lea     rax, [rbp+57h+var_80]
0x1800106cf  mov     [rsp+0C0h+pcbData], rax; pcbData
0x1800106d4  lea     r8, [rbp+57h+Value]; lpValue
0x1800106d8  lea     rax, [rbp+57h+var_60]
0x1800106dc  mov     [rbp+57h+var_80], 8
0x1800106e3  mov     [rsp+0C0h+pvData], rax; pvData
0x1800106e8  mov     r9d, 40h ; '@'; dwFlags
0x1800106ee  xor     edx, edx; lpSubKey
0x1800106f0  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x1800106f5  call    cs:__imp_RegGetValueW
0x1800106fb  test    eax, eax
0x1800106fd  jnz     short loc_18001070D
0x1800106ff  mov     rax, [rbp+57h+var_60]
0x180010703  mov     ecx, ebx
0x180010705  mov     rva ?g_TraceEnabled@@3RC_JC[rsi+rcx*8], rax; __int64 volatile near * volatile g_TraceEnabled ...
0x18001070d  inc     ebx
0x18001070f  cmp     ebx, 20h ; ' '
0x180010712  jl      short loc_1800106B4
0x180010714  mov     rcx, [rbp+57h+var_68]; hKey
0x180010718  test    rcx, rcx
0x18001071b  jz      short loc_180010723
0x18001071d  call    cs:__imp_RegCloseKey
0x180010723  mov     rcx, [rbp+57h+hKey]; hkey
0x180010727  lea     rax, [rbp+57h+var_80]
0x18001072b  mov     [rsp+0C0h+pcbData], rax; pcbData
0x180010730  lea     r8, ?g_DvClientAssertsMaskName@@3QBGB; "ClientAssertMask"
0x180010737  lea     rax, [rbp+57h+var_7C]
0x18001073b  mov     [rbp+57h+var_80], r14d
0x18001073f  mov     [rsp+0C0h+pvData], rax; pvData
0x180010744  mov     r9d, r15d; dwFlags
0x180010747  xor     edx, edx; lpSubKey
0x180010749  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x18001074e  call    cs:__imp_RegGetValueW
0x180010754  mov     rcx, [rbp+57h+hkey]; hKey
0x180010758  test    rcx, rcx
0x18001075b  jz      short loc_180010763
0x18001075d  call    cs:__imp_RegCloseKey
0x180010763  mov     rcx, [rbp+57h+hKey]; hKey
0x180010767  test    rcx, rcx
0x18001076a  jz      short loc_180010772
0x18001076c  call    cs:__imp_RegCloseKey
0x180010772  mov     rcx, [rbp+57h+var_40]
0x180010776  xor     rcx, rsp; StackCookie
0x180010779  call    __security_check_cookie
0x18001077e  add     rsp, 98h
0x180010785  pop     r15
0x180010787  pop     r14
0x180010789  pop     rdi
0x18001078a  pop     rsi
0x18001078b  pop     rbx
0x18001078c  pop     rbp
0x18001078d  retn
```
