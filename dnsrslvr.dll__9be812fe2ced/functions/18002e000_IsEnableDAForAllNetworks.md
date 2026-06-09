# IsEnableDAForAllNetworks

- ea: `0x18002e000`
- end: `0x18002e0e3`
- name: `IsEnableDAForAllNetworks`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002def4`

## callees

- `0x18002e000`
- `0x180046ec0`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e0c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e0c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e051`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e051`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e0a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e0a6`

## pseudocode

```c
__int64 IsEnableDAForAllNetworks()
{
  unsigned int v0; // eax
  __int64 v2; // r9
  __int64 v3; // rdx
  HKEY hKey; // [rsp+30h] [rbp-20h] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-14h] BYREF
  DWORD Type; // [rsp+40h] [rbp-10h] BYREF

  hKey = 0;
  Type = 4;
  cbData = 4;
  *(_DWORD *)Data = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Policies\\Microsoft\\Windows NT\\DNSClient", 0, 0x20019u, &hKey);
  if ( v0 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_3;
    v3 = 16;
    v2 = v0;
  }
  else
  {
    RegQueryValueExW(hKey, L"EnableDAForAllNetworks", 0, &Type, Data, &cbData);
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_3;
    v2 = *(unsigned int *)Data;
    v3 = 17;
  }
  WPP_SF_d(1035, v3, WPP_71228760225f354854029c0844ed0efa_Traceguids, v2);
LABEL_3:
  if ( hKey )
    RegCloseKey(hKey);
  return *(unsigned int *)Data;
}

```

## disassembly

```asm
0x18002e000  push    rbp
0x18002e002  mov     rbp, rsp
0x18002e005  sub     rsp, 50h
0x18002e009  mov     rax, cs:__security_cookie
0x18002e010  xor     rax, rsp
0x18002e013  mov     [rbp+var_8], rax
0x18002e017  mov     eax, 4
0x18002e01c  mov     [rbp+hKey], 0
0x18002e024  mov     [rbp+Type], eax
0x18002e027  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows "...
0x18002e02e  mov     [rbp+cbData], eax
0x18002e031  mov     r9d, 20019h; samDesired
0x18002e037  lea     rax, [rbp+hKey]
0x18002e03b  mov     dword ptr [rbp+Data], 0
0x18002e042  xor     r8d, r8d; ulOptions
0x18002e045  mov     [rsp+50h+phkResult], rax; phkResult
0x18002e04a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e051  call    cs:__imp_RegOpenKeyExW
0x18002e057  test    eax, eax
0x18002e059  jz      short loc_18002E082
0x18002e05b  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002e062  jnz     short loc_18002E0C8
0x18002e064  mov     rcx, [rbp+hKey]; hKey
0x18002e068  test    rcx, rcx
0x18002e06b  jnz     short loc_18002E0C0
0x18002e06d  mov     eax, dword ptr [rbp+Data]
0x18002e070  mov     rcx, [rbp+var_8]
0x18002e074  xor     rcx, rsp; StackCookie
0x18002e077  call    __security_check_cookie
0x18002e07c  add     rsp, 50h
0x18002e080  pop     rbp
0x18002e081  retn
0x18002e082  mov     rcx, [rbp+hKey]; hKey
0x18002e086  lea     rax, [rbp+cbData]
0x18002e08a  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18002e08f  lea     r9, [rbp+Type]; lpType
0x18002e093  lea     rax, [rbp+Data]
0x18002e097  xor     r8d, r8d; lpReserved
0x18002e09a  lea     rdx, aEnabledaforall; "EnableDAForAllNetworks"
0x18002e0a1  mov     [rsp+50h+phkResult], rax; lpData
0x18002e0a6  call    cs:__imp_RegQueryValueExW
0x18002e0ac  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002e0b3  jz      short loc_18002E064
0x18002e0b5  mov     r9d, dword ptr [rbp+Data]
0x18002e0b9  mov     edx, 11h
0x18002e0be  jmp     short loc_18002E0D0
0x18002e0c0  call    cs:__imp_RegCloseKey
0x18002e0c6  jmp     short loc_18002E06D
0x18002e0c8  mov     edx, 10h
0x18002e0cd  mov     r9d, eax
0x18002e0d0  lea     r8, WPP_71228760225f354854029c0844ed0efa_Traceguids
0x18002e0d7  mov     ecx, 40Bh
0x18002e0dc  call    WPP_SF_d
0x18002e0e1  jmp     short loc_18002E064
```
