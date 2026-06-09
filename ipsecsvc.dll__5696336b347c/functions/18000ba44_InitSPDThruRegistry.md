# InitSPDThruRegistry

- ea: `0x18000ba44`
- end: `0x18000bd59`
- name: `InitSPDThruRegistry`
- size: `789`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180001e20`

## callees

- `0x18000ba44`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bad7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bb20`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bb6a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bbc4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bc25`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bca9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bcfe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bad7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bb20`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bb6a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bbc4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bc25`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bca9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bcfe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ba8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bc6d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ba8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bc6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd46`

## string_xrefs

- `0x18000ba6a`: `SYSTEM\CurrentControlSet\Services\PolicyAgent`
- `0x18000bc5f`: `SYSTEM\CurrentControlSet\Services\PolicyAgent\Oakley`

## pseudocode

```c
__int64 InitSPDThruRegistry()
{
  int v0; // ebx
  int v1; // edi
  HKEY v2; // rcx
  int v3; // ecx
  unsigned int v4; // ecx
  int v5; // eax
  int v6; // eax
  HKEY phkResult; // [rsp+30h] [rbp-10h] BYREF
  unsigned int Data; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+48h] BYREF

  hKey = 0;
  phkResult = 0;
  Type = 0;
  cbData = 0;
  v0 = 0;
  Data = 0;
  v1 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\PolicyAgent", 0, 0x2000000u, &hKey) )
  {
    v2 = hKey;
    if ( !hKey )
      goto LABEL_42;
    Data = 0;
    Type = 4;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"OldFallBackToClear", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && cbData == 4 )
      LOBYTE(v0) = Data != 0;
    Type = 4;
    cbData = 4;
    Data = 0;
    if ( !RegQueryValueExW(hKey, L"EnableRemoteMgmt", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && cbData == 4 )
      LOBYTE(v1) = Data != 0;
    Type = 4;
    cbData = 4;
    Data = 0;
    if ( !RegQueryValueExW(hKey, L"SAIdleTime", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && cbData == 4 )
    {
      v3 = Data;
      if ( Data - 1 > 0x2A2FD )
        v3 = 300;
      gcSaIdleTime = v3;
    }
    Type = 4;
    cbData = 4;
    Data = 0;
    if ( !RegQueryValueExW(hKey, L"NoDefaultExempt", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && cbData == 4 )
    {
      v4 = Data;
      if ( Data > 4 )
        v4 = 3;
      gcExemptFiltersValue = v4;
      gcExemptMcastBcast = v4 < 2;
    }
    Type = 4;
    cbData = 4;
    Data = 0;
    if ( !RegQueryValueExW(hKey, L"AssumeUDPEncapsulationContextOnSendRule", 0, &Type, (LPBYTE)&Data, &cbData)
      && Type == 4
      && cbData == 4 )
    {
      v5 = Data;
      if ( Data > 2 )
      {
        v5 = 0;
        Data = 0;
      }
      gcUdpEncapsulation = v5;
    }
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Services\\PolicyAgent\\Oakley",
            0,
            0x2000000u,
            &phkResult) )
    {
      Type = 4;
      cbData = 4;
      Data = 0;
      if ( !RegQueryValueExW(phkResult, L"StrongCRLCheck", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && cbData == 4 )
      {
        v6 = Data;
        if ( Data > 2 )
          v6 = 1;
        gcCrlCheck = v6;
      }
      Type = 4;
      cbData = 4;
      Data = 0;
      if ( !RegQueryValueExW(phkResult, L"IKEFlags", 0, &Type, (LPBYTE)&Data, &cbData)
        && Type == 4
        && cbData == 4
        && (Data & 8) != 0 )
      {
        gcNapFlag = 1;
      }
    }
  }
  v2 = hKey;
LABEL_42:
  gbBackwardSoftSA = v0;
  gbEnableRemoteMgmt = v1;
  if ( v2 )
    RegCloseKey(v2);
  if ( phkResult )
    RegCloseKey(phkResult);
  return 0;
}

```

## disassembly

```asm
0x18000ba44  push    rbp
0x18000ba46  push    rbx
0x18000ba47  push    rsi
0x18000ba48  push    rdi
0x18000ba49  push    r14
0x18000ba4b  mov     rbp, rsp
0x18000ba4e  sub     rsp, 40h
0x18000ba52  xor     r14d, r14d
0x18000ba55  lea     rax, [rbp+hKey]
0x18000ba59  mov     r9d, 2000000h; samDesired
0x18000ba5f  mov     [rbp+hKey], r14
0x18000ba63  xor     r8d, r8d; ulOptions
0x18000ba66  mov     [rbp+var_10], r14
0x18000ba6a  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Po"...
0x18000ba71  mov     [rbp+Type], r14d
0x18000ba75  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ba7c  mov     [rbp+cbData], r14d
0x18000ba80  mov     ebx, r14d
0x18000ba83  mov     [rbp+Data], r14d
0x18000ba87  mov     edi, r14d
0x18000ba8a  mov     [rsp+40h+phkResult], rax; phkResult
0x18000ba8f  call    cs:__imp_RegOpenKeyExW
0x18000ba95  test    eax, eax
0x18000ba97  jnz     loc_18000BD22
0x18000ba9d  mov     rcx, [rbp+hKey]; hKey
0x18000baa1  test    rcx, rcx
0x18000baa4  jz      loc_18000BD26
0x18000baaa  lea     esi, [rax+4]
0x18000baad  mov     [rbp+Data], r14d
0x18000bab1  lea     rax, [rbp+cbData]
0x18000bab5  mov     [rbp+Type], esi
0x18000bab8  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000babd  lea     r9, [rbp+Type]; lpType
0x18000bac1  lea     rax, [rbp+Data]
0x18000bac5  mov     [rbp+cbData], esi
0x18000bac8  xor     r8d, r8d; lpReserved
0x18000bacb  mov     [rsp+40h+phkResult], rax; lpData
0x18000bad0  lea     rdx, ValueName; "OldFallBackToClear"
0x18000bad7  call    cs:__imp_RegQueryValueExW
0x18000badd  test    eax, eax
0x18000badf  jnz     short loc_18000BAF2
0x18000bae1  cmp     [rbp+Type], esi
0x18000bae4  jnz     short loc_18000BAF2
0x18000bae6  cmp     [rbp+cbData], esi
0x18000bae9  jnz     short loc_18000BAF2
0x18000baeb  cmp     [rbp+Data], r14d
0x18000baef  setnbe  bl
0x18000baf2  mov     rcx, [rbp+hKey]; hKey
0x18000baf6  lea     rax, [rbp+cbData]
0x18000bafa  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000baff  lea     r9, [rbp+Type]; lpType
0x18000bb03  lea     rax, [rbp+Data]
0x18000bb07  mov     [rbp+Type], esi
0x18000bb0a  xor     r8d, r8d; lpReserved
0x18000bb0d  mov     [rsp+40h+phkResult], rax; lpData
0x18000bb12  lea     rdx, aEnableremotemg; "EnableRemoteMgmt"
0x18000bb19  mov     [rbp+cbData], esi
0x18000bb1c  mov     [rbp+Data], r14d
0x18000bb20  call    cs:__imp_RegQueryValueExW
0x18000bb26  test    eax, eax
0x18000bb28  jnz     short loc_18000BB3C
0x18000bb2a  cmp     [rbp+Type], esi
0x18000bb2d  jnz     short loc_18000BB3C
0x18000bb2f  cmp     [rbp+cbData], esi
0x18000bb32  jnz     short loc_18000BB3C
0x18000bb34  cmp     [rbp+Data], r14d
0x18000bb38  setnbe  dil
0x18000bb3c  mov     rcx, [rbp+hKey]; hKey
0x18000bb40  lea     rax, [rbp+cbData]
0x18000bb44  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000bb49  lea     r9, [rbp+Type]; lpType
0x18000bb4d  lea     rax, [rbp+Data]
0x18000bb51  mov     [rbp+Type], esi
0x18000bb54  xor     r8d, r8d; lpReserved
0x18000bb57  mov     [rsp+40h+phkResult], rax; lpData
0x18000bb5c  lea     rdx, aSaidletime; "SAIdleTime"
0x18000bb63  mov     [rbp+cbData], esi
0x18000bb66  mov     [rbp+Data], r14d
0x18000bb6a  call    cs:__imp_RegQueryValueExW
0x18000bb70  test    eax, eax
0x18000bb72  jnz     short loc_18000BB96
0x18000bb74  cmp     [rbp+Type], esi
0x18000bb77  jnz     short loc_18000BB96
0x18000bb79  cmp     [rbp+cbData], esi
0x18000bb7c  jnz     short loc_18000BB96
0x18000bb7e  mov     ecx, [rbp+Data]
0x18000bb81  lea     eax, [rcx-1]
0x18000bb84  cmp     eax, 2A2FDh
0x18000bb89  jbe     short loc_18000BB90
0x18000bb8b  mov     ecx, 12Ch
0x18000bb90  mov     cs:gcSaIdleTime, ecx
0x18000bb96  mov     rcx, [rbp+hKey]; hKey
0x18000bb9a  lea     rax, [rbp+cbData]
0x18000bb9e  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000bba3  lea     r9, [rbp+Type]; lpType
0x18000bba7  lea     rax, [rbp+Data]
0x18000bbab  mov     [rbp+Type], esi
0x18000bbae  xor     r8d, r8d; lpReserved
0x18000bbb1  mov     [rsp+40h+phkResult], rax; lpData
0x18000bbb6  lea     rdx, aNodefaultexemp; "NoDefaultExempt"
0x18000bbbd  mov     [rbp+cbData], esi
0x18000bbc0  mov     [rbp+Data], r14d
0x18000bbc4  call    cs:__imp_RegQueryValueExW
0x18000bbca  test    eax, eax
0x18000bbcc  jnz     short loc_18000BBF7
0x18000bbce  cmp     [rbp+Type], esi
0x18000bbd1  jnz     short loc_18000BBF7
0x18000bbd3  cmp     [rbp+cbData], esi
0x18000bbd6  jnz     short loc_18000BBF7
0x18000bbd8  mov     ecx, [rbp+Data]
0x18000bbdb  cmp     ecx, esi
0x18000bbdd  jbe     short loc_18000BBE2
0x18000bbdf  lea     ecx, [rax+3]
0x18000bbe2  mov     eax, r14d
0x18000bbe5  mov     cs:gcExemptFiltersValue, ecx
0x18000bbeb  cmp     ecx, 2
0x18000bbee  setb    al
0x18000bbf1  mov     cs:gcExemptMcastBcast, eax
0x18000bbf7  mov     rcx, [rbp+hKey]; hKey
0x18000bbfb  lea     rax, [rbp+cbData]
0x18000bbff  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000bc04  lea     r9, [rbp+Type]; lpType
0x18000bc08  lea     rax, [rbp+Data]
0x18000bc0c  mov     [rbp+Type], esi
0x18000bc0f  xor     r8d, r8d; lpReserved
0x18000bc12  mov     [rsp+40h+phkResult], rax; lpData
0x18000bc17  lea     rdx, aAssumeudpencap; "AssumeUDPEncapsulationContextOnSendRule"
0x18000bc1e  mov     [rbp+cbData], esi
0x18000bc21  mov     [rbp+Data], r14d
0x18000bc25  call    cs:__imp_RegQueryValueExW
0x18000bc2b  test    eax, eax
0x18000bc2d  jnz     short loc_18000BC4D
0x18000bc2f  cmp     [rbp+Type], esi
0x18000bc32  jnz     short loc_18000BC4D
0x18000bc34  cmp     [rbp+cbData], esi
0x18000bc37  jnz     short loc_18000BC4D
0x18000bc39  mov     eax, [rbp+Data]
0x18000bc3c  cmp     eax, 2
0x18000bc3f  jbe     short loc_18000BC47
0x18000bc41  mov     eax, r14d
0x18000bc44  mov     [rbp+Data], eax
0x18000bc47  mov     cs:gcUdpEncapsulation, eax
0x18000bc4d  lea     rax, [rbp+var_10]
0x18000bc51  mov     r9d, 2000000h; samDesired
0x18000bc57  xor     r8d, r8d; ulOptions
0x18000bc5a  mov     [rsp+40h+phkResult], rax; phkResult
0x18000bc5f  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Po"...
0x18000bc66  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000bc6d  call    cs:__imp_RegOpenKeyExW
0x18000bc73  test    eax, eax
0x18000bc75  jnz     loc_18000BD22
0x18000bc7b  mov     rcx, [rbp+var_10]; hKey
0x18000bc7f  lea     rax, [rbp+cbData]
0x18000bc83  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000bc88  lea     r9, [rbp+Type]; lpType
0x18000bc8c  lea     rax, [rbp+Data]
0x18000bc90  mov     [rbp+Type], esi
0x18000bc93  xor     r8d, r8d; lpReserved
0x18000bc96  mov     [rsp+40h+phkResult], rax; lpData
0x18000bc9b  lea     rdx, aStrongcrlcheck; "StrongCRLCheck"
0x18000bca2  mov     [rbp+cbData], esi
0x18000bca5  mov     [rbp+Data], r14d
0x18000bca9  call    cs:__imp_RegQueryValueExW
0x18000bcaf  test    eax, eax
0x18000bcb1  jnz     short loc_18000BCD0
0x18000bcb3  cmp     [rbp+Type], esi
0x18000bcb6  jnz     short loc_18000BCD0
0x18000bcb8  cmp     [rbp+cbData], esi
0x18000bcbb  jnz     short loc_18000BCD0
0x18000bcbd  mov     eax, [rbp+Data]
0x18000bcc0  cmp     eax, 2
0x18000bcc3  jbe     short loc_18000BCCA
0x18000bcc5  mov     eax, 1
0x18000bcca  mov     cs:gcCrlCheck, eax
0x18000bcd0  mov     rcx, [rbp+var_10]; hKey
0x18000bcd4  lea     rax, [rbp+cbData]
0x18000bcd8  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000bcdd  lea     r9, [rbp+Type]; lpType
0x18000bce1  lea     rax, [rbp+Data]
0x18000bce5  mov     [rbp+Type], esi
0x18000bce8  xor     r8d, r8d; lpReserved
0x18000bceb  mov     [rsp+40h+phkResult], rax; lpData
0x18000bcf0  lea     rdx, aIkeflags; "IKEFlags"
0x18000bcf7  mov     [rbp+cbData], esi
0x18000bcfa  mov     [rbp+Data], r14d
0x18000bcfe  call    cs:__imp_RegQueryValueExW
0x18000bd04  test    eax, eax
0x18000bd06  jnz     short loc_18000BD22
0x18000bd08  cmp     [rbp+Type], esi
0x18000bd0b  jnz     short loc_18000BD22
0x18000bd0d  cmp     [rbp+cbData], esi
0x18000bd10  jnz     short loc_18000BD22
0x18000bd12  test    byte ptr [rbp+Data], 8
0x18000bd16  jz      short loc_18000BD22
0x18000bd18  mov     cs:gcNapFlag, 1
0x18000bd22  mov     rcx, [rbp+hKey]; hKey
0x18000bd26  mov     cs:gbBackwardSoftSA, ebx
0x18000bd2c  mov     cs:gbEnableRemoteMgmt, edi
0x18000bd32  test    rcx, rcx
0x18000bd35  jz      short loc_18000BD3D
0x18000bd37  call    cs:__imp_RegCloseKey
0x18000bd3d  mov     rcx, [rbp+var_10]; hKey
0x18000bd41  test    rcx, rcx
0x18000bd44  jz      short loc_18000BD4C
0x18000bd46  call    cs:__imp_RegCloseKey
0x18000bd4c  xor     eax, eax
0x18000bd4e  add     rsp, 40h
0x18000bd52  pop     r14
0x18000bd54  pop     rdi
0x18000bd55  pop     rsi
0x18000bd56  pop     rbx
0x18000bd57  pop     rbp
0x18000bd58  retn
```
