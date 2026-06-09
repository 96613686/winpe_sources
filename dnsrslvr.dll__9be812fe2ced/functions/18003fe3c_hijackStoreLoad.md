# hijackStoreLoad

- ea: `0x18003fe3c`
- end: `0x18004013a`
- name: `hijackStoreLoad`
- size: `766`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x1800409d0`

## callees

- `0x18001fe74`
- `0x18002025c`
- `0x180025630`
- `0x180033ab4`
- `0x180034be8`
- `0x18003fe3c`
- `0x180046ec0`
- `0x180062164`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003ff60`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003ff60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040098`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800400fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004010b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040098`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800400fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004010b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800400b6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800400b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ffbe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ffbe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180040002`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180040047`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180040002`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180040047`

## string_xrefs

- `0x18003fedb`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x18003fee7`: `Dnscache`

## pseudocode

```c
__int64 hijackStoreLoad()
{
  unsigned int v0; // esi
  unsigned int CurrentTime; // r15d
  int v2; // r9d
  unsigned int v3; // r14d
  DWORD v4; // edi
  unsigned int v5; // eax
  unsigned int v6; // ecx
  int v7; // ebx
  unsigned int v9; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  BYTE v16[4]; // [rsp+6Ch] [rbp-94h] BYREF
  GUID Guid; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[256]; // [rsp+80h] [rbp-80h] BYREF

  hKey = 0;
  phkResult = 0;
  cchName = 256;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v16 = 0;
  Type = 0;
  cbData = 0;
  v9 = 0;
  Guid = 0;
  if ( !g_HijackList || g_HijackList != &g_HijackList )
    return 0;
  v0 = 0;
  CurrentTime = hijackGetCurrentTime();
  if ( (unsigned int)CreatePersistedRegistryKeyHelper(
                       (unsigned int)L"Dnscache",
                       (unsigned int)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                       (unsigned int)L"Parameters\\Probe",
                       v2,
                       983103,
                       0,
                       0,
                       (__int64)&hKey) )
    goto LABEL_28;
  v3 = 604800;
  v4 = 0;
  if ( (unsigned int)hijackTestGetInterval(&v9) )
    v3 = v9;
  while ( 1 )
  {
    if ( v4 >= 0x3E8 || (cchName = 256, v5 = RegEnumKeyExW(hKey, v4, Name, &cchName, 0, 0, 0, 0), v5 == 259) )
    {
      v0 = 1;
      goto LABEL_28;
    }
    if ( v5 == 234 )
      goto LABEL_24;
    if ( v5 )
      break;
    Name[255] = 0;
    if ( !(unsigned int)Dns_StringToGuid(Name, &Guid) )
      goto LABEL_20;
    if ( RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult) )
    {
      phkResult = 0;
      goto LABEL_24;
    }
    cbData = 4;
    if ( RegQueryValueExW(phkResult, L"LastProbeTime", 0, &Type, Data, &cbData)
      || Type != 4
      || (cbData = 4, RegQueryValueExW(phkResult, L"NetworkPerformsHijacking", 0, &Type, v16, &cbData))
      || Type != 4
      || (unsigned int)hijackIsExpired(*(unsigned int *)Data, CurrentTime, v3) )
    {
LABEL_20:
      v7 = 1;
    }
    else
    {
      if ( !hijackListAdd(0, &Guid, v6, *(_DWORD *)v16 == 1) )
        goto LABEL_28;
      v7 = 0;
    }
    RegCloseKey(phkResult);
    phkResult = 0;
    if ( v7 )
    {
      if ( !RegDeleteKeyExW(hKey, Name, 0, 0) )
        --v4;
    }
LABEL_24:
    ++v4;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 11, WPP_0709937be1093c69bca0496091e2f548_Traceguids, v5);
LABEL_28:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x18003fe3c  push    rbp
0x18003fe3e  push    rbx
0x18003fe3f  push    rsi
0x18003fe40  push    rdi
0x18003fe41  push    r12
0x18003fe43  push    r13
0x18003fe45  push    r14
0x18003fe47  push    r15
0x18003fe49  lea     rbp, [rsp-198h]
0x18003fe51  sub     rsp, 298h
0x18003fe58  mov     rax, cs:__security_cookie
0x18003fe5f  xor     rax, rsp
0x18003fe62  mov     [rbp+1D0h+var_50], rax
0x18003fe69  mov     rax, cs:g_HijackList
0x18003fe70  xor     r12d, r12d
0x18003fe73  mov     [rsp+2D0h+hKey], r12
0x18003fe78  xorps   xmm0, xmm0
0x18003fe7b  mov     [rsp+2D0h+phkResult], r12
0x18003fe80  mov     [rsp+2D0h+cchName], 100h
0x18003fe88  mov     dword ptr [rsp+2D0h+Data], r12d
0x18003fe8d  mov     dword ptr [rsp+2D0h+var_264], r12d
0x18003fe92  mov     [rsp+2D0h+Type], r12d
0x18003fe97  mov     [rsp+2D0h+cbData], r12d
0x18003fe9c  mov     [rsp+2D0h+var_290], r12d
0x18003fea1  movups  xmmword ptr [rsp+2D0h+Guid.Data1], xmm0
0x18003fea6  test    rax, rax
0x18003fea9  jz      loc_180040115
0x18003feaf  lea     rcx, g_HijackList
0x18003feb6  cmp     rax, rcx
0x18003feb9  jnz     loc_180040115
0x18003febf  mov     esi, r12d
0x18003fec2  call    hijackGetCurrentTime
0x18003fec7  mov     r15d, eax
0x18003feca  lea     r8, aParametersProb; "Parameters\\Probe"
0x18003fed1  lea     rax, [rsp+2D0h+hKey]
0x18003fed6  mov     [rsp+2D0h+lpftLastWriteTime], rax
0x18003fedb  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18003fee2  mov     dword ptr [rsp+2D0h+lpcchClass], r12d
0x18003fee7  lea     rcx, aDnscache_0; "Dnscache"
0x18003feee  mov     [rsp+2D0h+lpClass], r12
0x18003fef3  mov     dword ptr [rsp+2D0h+lpReserved], 0F003Fh
0x18003fefb  call    CreatePersistedRegistryKeyHelper
0x18003ff00  test    eax, eax
0x18003ff02  jnz     loc_1800400F1
0x18003ff08  lea     rcx, [rsp+2D0h+var_290]
0x18003ff0d  mov     r14d, 93A80h
0x18003ff13  call    hijackTestGetInterval
0x18003ff18  test    eax, eax
0x18003ff1a  lea     r13d, [r12+1]
0x18003ff1f  mov     edi, r12d
0x18003ff22  cmovnz  r14d, [rsp+2D0h+var_290]
0x18003ff28  cmp     edi, 3E8h
0x18003ff2e  jnb     loc_1800400EE
0x18003ff34  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18003ff39  lea     r9, [rsp+2D0h+cchName]; lpcchName
0x18003ff3e  mov     [rsp+2D0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18003ff43  lea     r8, [rbp+1D0h+Name]; lpName
0x18003ff47  mov     [rsp+2D0h+lpcchClass], r12; lpcchClass
0x18003ff4c  mov     edx, edi; dwIndex
0x18003ff4e  mov     [rsp+2D0h+lpClass], r12; lpClass
0x18003ff53  mov     [rsp+2D0h+lpReserved], r12; lpReserved
0x18003ff58  mov     [rsp+2D0h+cchName], 100h
0x18003ff60  call    cs:__imp_RegEnumKeyExW
0x18003ff66  cmp     eax, 103h
0x18003ff6b  jz      loc_1800400EE
0x18003ff71  cmp     eax, 0EAh
0x18003ff76  jz      loc_1800400C2
0x18003ff7c  test    eax, eax
0x18003ff7e  jnz     loc_1800400CA
0x18003ff84  lea     rdx, [rsp+2D0h+Guid]; Guid
0x18003ff89  mov     [rbp+1D0h+var_52], r12w
0x18003ff91  lea     rcx, [rbp+1D0h+Name]; SourceString
0x18003ff95  call    Dns_StringToGuid
0x18003ff9a  test    eax, eax
0x18003ff9c  jz      loc_180040090
0x18003ffa2  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18003ffa7  lea     rax, [rsp+2D0h+phkResult]
0x18003ffac  mov     r9d, 20019h; samDesired
0x18003ffb2  mov     [rsp+2D0h+lpReserved], rax; phkResult
0x18003ffb7  xor     r8d, r8d; ulOptions
0x18003ffba  lea     rdx, [rbp+1D0h+Name]; lpSubKey
0x18003ffbe  call    cs:__imp_RegOpenKeyExW
0x18003ffc4  test    eax, eax
0x18003ffc6  jz      short loc_18003FFD2
0x18003ffc8  mov     [rsp+2D0h+phkResult], r12
0x18003ffcd  jmp     loc_1800400C2
0x18003ffd2  mov     rcx, [rsp+2D0h+phkResult]; hKey
0x18003ffd7  lea     rax, [rsp+2D0h+cbData]
0x18003ffdc  mov     [rsp+2D0h+lpClass], rax; lpcbData
0x18003ffe1  lea     r9, [rsp+2D0h+Type]; lpType
0x18003ffe6  lea     rax, [rsp+2D0h+Data]
0x18003ffeb  mov     [rsp+2D0h+cbData], 4
0x18003fff3  xor     r8d, r8d; lpReserved
0x18003fff6  mov     [rsp+2D0h+lpReserved], rax; lpData
0x18003fffb  lea     rdx, aLastprobetime; "LastProbeTime"
0x180040002  call    cs:__imp_RegQueryValueExW
0x180040008  test    eax, eax
0x18004000a  jnz     loc_180040090
0x180040010  cmp     [rsp+2D0h+Type], 4
0x180040015  jnz     short loc_180040090
0x180040017  mov     rcx, [rsp+2D0h+phkResult]; hKey
0x18004001c  lea     rax, [rsp+2D0h+cbData]
0x180040021  mov     [rsp+2D0h+lpClass], rax; lpcbData
0x180040026  lea     r9, [rsp+2D0h+Type]; lpType
0x18004002b  lea     rax, [rsp+2D0h+var_264]
0x180040030  mov     [rsp+2D0h+cbData], 4
0x180040038  xor     r8d, r8d; lpReserved
0x18004003b  mov     [rsp+2D0h+lpReserved], rax; lpData
0x180040040  lea     rdx, aNetworkperform; "NetworkPerformsHijacking"
0x180040047  call    cs:__imp_RegQueryValueExW
0x18004004d  test    eax, eax
0x18004004f  jnz     short loc_180040090
0x180040051  cmp     [rsp+2D0h+Type], 4
0x180040056  jnz     short loc_180040090
0x180040058  mov     ecx, dword ptr [rsp+2D0h+Data]
0x18004005c  mov     r8d, r14d
0x18004005f  mov     edx, r15d
0x180040062  call    hijackIsExpired
0x180040067  test    eax, eax
0x180040069  jnz     short loc_180040090
0x18004006b  cmp     dword ptr [rsp+2D0h+var_264], r13d
0x180040070  lea     rdx, [rsp+2D0h+Guid]
0x180040075  mov     r9d, r12d
0x180040078  mov     r8d, ecx
0x18004007b  setz    r9b
0x18004007f  xor     ecx, ecx
0x180040081  call    hijackListAdd
0x180040086  test    rax, rax
0x180040089  jz      short loc_1800400F1
0x18004008b  mov     ebx, r12d
0x18004008e  jmp     short loc_180040093
0x180040090  mov     ebx, r13d
0x180040093  mov     rcx, [rsp+2D0h+phkResult]; hKey
0x180040098  call    cs:__imp_RegCloseKey
0x18004009e  mov     [rsp+2D0h+phkResult], r12
0x1800400a3  test    ebx, ebx
0x1800400a5  jz      short loc_1800400C2
0x1800400a7  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800400ac  lea     rdx, [rbp+1D0h+Name]; lpSubKey
0x1800400b0  xor     r9d, r9d; Reserved
0x1800400b3  xor     r8d, r8d; samDesired
0x1800400b6  call    cs:__imp_RegDeleteKeyExW
0x1800400bc  test    eax, eax
0x1800400be  jnz     short loc_1800400C2
0x1800400c0  dec     edi
0x1800400c2  add     edi, r13d
0x1800400c5  jmp     loc_18003FF28
0x1800400ca  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800400d1  jz      short loc_1800400F1
0x1800400d3  mov     edx, 0Bh
0x1800400d8  lea     r8, WPP_0709937be1093c69bca0496091e2f548_Traceguids
0x1800400df  mov     ecx, 40Bh
0x1800400e4  mov     r9d, eax
0x1800400e7  call    WPP_SF_d
0x1800400ec  jmp     short loc_1800400F1
0x1800400ee  mov     esi, r13d
0x1800400f1  mov     rcx, [rsp+2D0h+phkResult]; hKey
0x1800400f6  test    rcx, rcx
0x1800400f9  jz      short loc_180040101
0x1800400fb  call    cs:__imp_RegCloseKey
0x180040101  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180040106  test    rcx, rcx
0x180040109  jz      short loc_180040111
0x18004010b  call    cs:__imp_RegCloseKey
0x180040111  mov     eax, esi
0x180040113  jmp     short loc_180040117
0x180040115  xor     eax, eax
0x180040117  mov     rcx, [rbp+1D0h+var_50]
0x18004011e  xor     rcx, rsp; StackCookie
0x180040121  call    __security_check_cookie
0x180040126  add     rsp, 298h
0x18004012d  pop     r15
0x18004012f  pop     r14
0x180040131  pop     r13
0x180040133  pop     r12
0x180040135  pop     rdi
0x180040136  pop     rsi
0x180040137  pop     rbx
0x180040138  pop     rbp
0x180040139  retn
```
