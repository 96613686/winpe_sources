# InitializeRasIpsec(void)

- ea: `0x180015a70`
- end: `0x180015c45`
- name: `?InitializeRasIpsec@@YAXXZ`
- size: `469`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18001bf40`

## callees

- `0x180015a70`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180015a9e`
- `ADVAPI32!RegOpenKeyExW` at `0x180015bc4`
- `ADVAPI32!RegOpenKeyExW` at `0x180015a9e`
- `ADVAPI32!RegOpenKeyExW` at `0x180015bc4`
- `ADVAPI32!RegQueryValueExW` at `0x180015ae3`
- `ADVAPI32!RegQueryValueExW` at `0x180015b28`
- `ADVAPI32!RegQueryValueExW` at `0x180015b6d`
- `ADVAPI32!RegQueryValueExW` at `0x180015c05`
- `ADVAPI32!RegQueryValueExW` at `0x180015ae3`
- `ADVAPI32!RegQueryValueExW` at `0x180015b28`
- `ADVAPI32!RegQueryValueExW` at `0x180015b6d`
- `ADVAPI32!RegQueryValueExW` at `0x180015c05`
- `ADVAPI32!RegCloseKey` at `0x180015b93`
- `ADVAPI32!RegCloseKey` at `0x180015c32`
- `ADVAPI32!RegCloseKey` at `0x180015b93`
- `ADVAPI32!RegCloseKey` at `0x180015c32`

## string_xrefs

- `0x180015a90`: `System\CurrentControlSet\Services\rasman\parameters`
- `0x180015bb6`: `SYSTEM\CurrentControlSet\Services\PolicyAgent`

## pseudocode

```c
void InitializeRasIpsec(void)
{
  LSTATUS v0; // eax
  int v1; // ecx
  LSTATUS v2; // eax
  int v3; // ecx
  LSTATUS v4; // eax
  int v5; // ecx
  int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+18h] BYREF
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\rasman\\parameters",
          0,
          0x20019u,
          &hKey) )
  {
    Type = 0;
    Data = 0;
    cbData = 4;
    v0 = RegQueryValueExW(hKey, L"ProhibitIpSec", 0, &Type, (LPBYTE)&Data, &cbData);
    v1 = 0;
    cbData = 4;
    if ( !v0 )
      v1 = Data;
    g_dwProhibitIpsec = v1;
    v2 = RegQueryValueExW(hKey, L"AllowL2TPWeakCrypto", 0, &Type, (LPBYTE)&Data, &cbData);
    v3 = 0;
    cbData = 4;
    if ( !v2 )
      v3 = Data;
    g_dwAllowL2TPWeakCrypto = v3;
    v4 = RegQueryValueExW(hKey, L"L2tpCRLCheckLevel", 0, &Type, (LPBYTE)&Data, &cbData);
    v5 = 1;
    if ( !v4 )
      v5 = Data;
    g_dwL2TPCRLCheckLevel = v5;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\PolicyAgent", 0, 1u, &hKey) )
  {
    Data = 0;
    cbData = 0;
    Type = 4;
    if ( !RegQueryValueExW(hKey, L"AssumeUDPEncapsulationContextOnSendRule", 0, (LPDWORD)&Data, (LPBYTE)&cbData, &Type)
      && Data == 4
      && cbData <= 2 )
    {
      *(_DWORD *)&g_dwIpsecUdpEncapsulation = cbData;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180015a70  push    rbp
0x180015a72  mov     rbp, rsp
0x180015a75  sub     rsp, 30h
0x180015a79  and     [rbp+hKey], 0
0x180015a7e  lea     rax, [rbp+hKey]
0x180015a82  mov     r9d, 20019h; samDesired
0x180015a88  mov     [rsp+30h+phkResult], rax; phkResult
0x180015a8d  xor     r8d, r8d; ulOptions
0x180015a90  lea     rdx, aSystemCurrentc_27; "System\\CurrentControlSet\\Services\\ra"...
0x180015a97  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015a9e  call    cs:__imp_RegOpenKeyExW
0x180015aa5  nop     dword ptr [rax+rax+00h]
0x180015aaa  test    eax, eax
0x180015aac  jnz     loc_180015B8A
0x180015ab2  and     [rbp+Type], eax
0x180015ab5  lea     r9, [rbp+Type]; lpType
0x180015ab9  and     [rbp+Data], eax
0x180015abc  lea     rdx, aProhibitipsec; "ProhibitIpSec"
0x180015ac3  mov     rcx, [rbp+hKey]; hKey
0x180015ac7  lea     rax, [rbp+cbData]
0x180015acb  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180015ad0  xor     r8d, r8d; lpReserved
0x180015ad3  lea     rax, [rbp+Data]
0x180015ad7  mov     [rbp+cbData], 4
0x180015ade  mov     [rsp+30h+phkResult], rax; lpData
0x180015ae3  call    cs:__imp_RegQueryValueExW
0x180015aea  nop     dword ptr [rax+rax+00h]
0x180015aef  xor     ecx, ecx
0x180015af1  mov     [rbp+cbData], 4
0x180015af8  test    eax, eax
0x180015afa  lea     r9, [rbp+Type]; lpType
0x180015afe  lea     rax, [rbp+cbData]
0x180015b02  cmovz   ecx, [rbp+Data]
0x180015b06  lea     rdx, aAllowl2tpweakc; "AllowL2TPWeakCrypto"
0x180015b0d  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180015b12  xor     r8d, r8d; lpReserved
0x180015b15  mov     cs:g_dwProhibitIpsec, ecx
0x180015b1b  lea     rax, [rbp+Data]
0x180015b1f  mov     rcx, [rbp+hKey]; hKey
0x180015b23  mov     [rsp+30h+phkResult], rax; lpData
0x180015b28  call    cs:__imp_RegQueryValueExW
0x180015b2f  nop     dword ptr [rax+rax+00h]
0x180015b34  xor     ecx, ecx
0x180015b36  mov     [rbp+cbData], 4
0x180015b3d  test    eax, eax
0x180015b3f  lea     r9, [rbp+Type]; lpType
0x180015b43  lea     rax, [rbp+cbData]
0x180015b47  cmovz   ecx, [rbp+Data]
0x180015b4b  lea     rdx, aL2tpcrlcheckle; "L2tpCRLCheckLevel"
0x180015b52  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180015b57  xor     r8d, r8d; lpReserved
0x180015b5a  mov     cs:g_dwAllowL2TPWeakCrypto, ecx
0x180015b60  lea     rax, [rbp+Data]
0x180015b64  mov     rcx, [rbp+hKey]; hKey
0x180015b68  mov     [rsp+30h+phkResult], rax; lpData
0x180015b6d  call    cs:__imp_RegQueryValueExW
0x180015b74  nop     dword ptr [rax+rax+00h]
0x180015b79  test    eax, eax
0x180015b7b  mov     ecx, 1
0x180015b80  cmovz   ecx, [rbp+Data]
0x180015b84  mov     cs:g_dwL2TPCRLCheckLevel, ecx
0x180015b8a  mov     rcx, [rbp+hKey]; hKey
0x180015b8e  test    rcx, rcx
0x180015b91  jz      short loc_180015BA4
0x180015b93  call    cs:__imp_RegCloseKey
0x180015b9a  nop     dword ptr [rax+rax+00h]
0x180015b9f  and     [rbp+hKey], 0
0x180015ba4  lea     rax, [rbp+hKey]
0x180015ba8  mov     r9d, 1; samDesired
0x180015bae  xor     r8d, r8d; ulOptions
0x180015bb1  mov     [rsp+30h+phkResult], rax; phkResult
0x180015bb6  lea     rdx, aSystemCurrentc_14; "SYSTEM\\CurrentControlSet\\Services\\Po"...
0x180015bbd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015bc4  call    cs:__imp_RegOpenKeyExW
0x180015bcb  nop     dword ptr [rax+rax+00h]
0x180015bd0  test    eax, eax
0x180015bd2  jnz     short loc_180015C29
0x180015bd4  and     [rbp+Data], eax
0x180015bd7  lea     r9, [rbp+Data]; lpType
0x180015bdb  and     [rbp+cbData], eax
0x180015bde  lea     rdx, aAssumeudpencap; "AssumeUDPEncapsulationContextOnSendRule"
0x180015be5  mov     rcx, [rbp+hKey]; hKey
0x180015be9  lea     rax, [rbp+Type]
0x180015bed  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180015bf2  xor     r8d, r8d; lpReserved
0x180015bf5  lea     rax, [rbp+cbData]
0x180015bf9  mov     [rbp+Type], 4
0x180015c00  mov     [rsp+30h+phkResult], rax; lpData
0x180015c05  call    cs:__imp_RegQueryValueExW
0x180015c0c  nop     dword ptr [rax+rax+00h]
0x180015c11  test    eax, eax
0x180015c13  jnz     short loc_180015C29
0x180015c15  cmp     [rbp+Data], 4
0x180015c19  jnz     short loc_180015C29
0x180015c1b  mov     eax, [rbp+cbData]
0x180015c1e  cmp     eax, 2
0x180015c21  ja      short loc_180015C29
0x180015c23  mov     cs:g_dwIpsecUdpEncapsulation, eax
0x180015c29  mov     rcx, [rbp+hKey]; hKey
0x180015c2d  test    rcx, rcx
0x180015c30  jz      short loc_180015C3E
0x180015c32  call    cs:__imp_RegCloseKey
0x180015c39  nop     dword ptr [rax+rax+00h]
0x180015c3e  add     rsp, 30h
0x180015c42  pop     rbp
0x180015c43  retn
```
