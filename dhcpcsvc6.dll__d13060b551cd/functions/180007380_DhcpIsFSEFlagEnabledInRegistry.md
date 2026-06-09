# DhcpIsFSEFlagEnabledInRegistry

- ea: `0x180007380`
- end: `0x180007457`
- name: `DhcpIsFSEFlagEnabledInRegistry`
- size: `215`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180003650`

## callees

- `0x180007380`
- `0x180008170`
- `0x1800082b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007432`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007432`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007409`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007409`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800073d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800073d2`

## string_xrefs

- `0x1800073c4`: `System\CurrentControlSet\Services\Tcpip\Parameters`

## pseudocode

```c
__int64 __fastcall DhcpIsFSEFlagEnabledInRegistry(__int64 a1)
{
  unsigned int v1; // ebx
  __int64 v2; // rdx
  LSTATUS v3; // edi
  __int64 v4; // r8
  HKEY v5; // rcx
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  DWORD Type; // [rsp+58h] [rbp+28h] BYREF
  int Data; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  v1 = 0;
  cbData = 0;
  Type = 0;
  Data = 0;
  hKey = 0;
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_(a1, 26, WPP_94d5010c5674399d06148e3a91870046_Traceguids);
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters", 0, 1u, &hKey);
  if ( !v3 )
  {
    cbData = 4;
    v3 = RegQueryValueExW(hKey, L"PortTrackerEnabledMode", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v3 )
    {
      if ( Type == 4 )
      {
        v3 = 0;
        LOBYTE(v1) = Data == 1;
      }
      else
      {
        v3 = 87;
      }
    }
  }
  v5 = hKey;
  if ( hKey )
    RegCloseKey(hKey);
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_lD(v5, v2, v4, v1, v3);
  return v1;
}

```

## disassembly

```asm
0x180007380  push    rbp
0x180007382  push    rbx
0x180007383  push    rdi
0x180007384  mov     rbp, rsp
0x180007387  sub     rsp, 30h
0x18000738b  xor     ebx, ebx
0x18000738d  mov     [rbp+cbData], ebx
0x180007390  mov     [rbp+Type], ebx
0x180007393  mov     [rbp+Data], ebx
0x180007396  mov     [rbp+hKey], rbx
0x18000739a  test    byte ptr cs:xmmword_18000F160, 10h
0x1800073a1  jz      short loc_1800073B2
0x1800073a3  lea     edx, [rbx+1Ah]
0x1800073a6  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x1800073ad  call    WPP_SF_
0x1800073b2  lea     rax, [rbp+hKey]
0x1800073b6  mov     r9d, 1; samDesired
0x1800073bc  xor     r8d, r8d; ulOptions
0x1800073bf  mov     [rsp+30h+phkResult], rax; phkResult
0x1800073c4  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Tc"...
0x1800073cb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800073d2  call    cs:__imp_RegOpenKeyExW
0x1800073d8  mov     edi, eax
0x1800073da  test    eax, eax
0x1800073dc  jnz     short loc_180007429
0x1800073de  mov     rcx, [rbp+hKey]; hKey
0x1800073e2  lea     rax, [rbp+cbData]
0x1800073e6  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800073eb  lea     r9, [rbp+Type]; lpType
0x1800073ef  lea     rax, [rbp+Data]
0x1800073f3  mov     [rbp+cbData], 4
0x1800073fa  xor     r8d, r8d; lpReserved
0x1800073fd  mov     [rsp+30h+phkResult], rax; lpData
0x180007402  lea     rdx, aPorttrackerena; "PortTrackerEnabledMode"
0x180007409  call    cs:__imp_RegQueryValueExW
0x18000740f  mov     edi, eax
0x180007411  test    eax, eax
0x180007413  jnz     short loc_180007429
0x180007415  cmp     [rbp+Type], 4
0x180007419  jz      short loc_180007420
0x18000741b  lea     edi, [rax+57h]
0x18000741e  jmp     short loc_180007429
0x180007420  xor     edi, edi
0x180007422  cmp     [rbp+Data], 1
0x180007426  setz    bl
0x180007429  mov     rcx, [rbp+hKey]; hKey
0x18000742d  test    rcx, rcx
0x180007430  jz      short loc_180007438
0x180007432  call    cs:__imp_RegCloseKey
0x180007438  test    byte ptr cs:xmmword_18000F160, 10h
0x18000743f  jz      short loc_18000744D
0x180007441  mov     r9d, ebx
0x180007444  mov     dword ptr [rsp+30h+phkResult], edi
0x180007448  call    WPP_SF_lD
0x18000744d  mov     eax, ebx
0x18000744f  add     rsp, 30h
0x180007453  pop     rdi
0x180007454  pop     rbx
0x180007455  pop     rbp
0x180007456  retn
```
