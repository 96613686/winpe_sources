# InitializeRasIpsec(void)

- ea: `0x18001561c`
- end: `0x1800157c6`
- name: `?InitializeRasIpsec@@YAXXZ`
- size: `426`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18001b570`

## callees

- `0x18001561c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18001564d`
- `ADVAPI32!RegOpenKeyExW` at `0x180015758`
- `ADVAPI32!RegOpenKeyExW` at `0x18001564d`
- `ADVAPI32!RegOpenKeyExW` at `0x180015758`
- `ADVAPI32!RegQueryValueExW` at `0x18001568c`
- `ADVAPI32!RegQueryValueExW` at `0x1800156cb`
- `ADVAPI32!RegQueryValueExW` at `0x18001570a`
- `ADVAPI32!RegQueryValueExW` at `0x180015793`
- `ADVAPI32!RegQueryValueExW` at `0x18001568c`
- `ADVAPI32!RegQueryValueExW` at `0x1800156cb`
- `ADVAPI32!RegQueryValueExW` at `0x18001570a`
- `ADVAPI32!RegQueryValueExW` at `0x180015793`
- `ADVAPI32!RegCloseKey` at `0x18001572a`
- `ADVAPI32!RegCloseKey` at `0x1800157ba`
- `ADVAPI32!RegCloseKey` at `0x18001572a`
- `ADVAPI32!RegCloseKey` at `0x1800157ba`

## string_xrefs

- `0x18001563f`: `System\CurrentControlSet\Services\rasman\parameters`
- `0x18001574a`: `SYSTEM\CurrentControlSet\Services\PolicyAgent`

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
      g_dwIpsecUdpEncapsulation = cbData;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18001561c  push    rbp
0x18001561e  mov     rbp, rsp
0x180015621  sub     rsp, 30h
0x180015625  lea     rax, [rbp+hKey]
0x180015629  mov     [rbp+hKey], 0
0x180015631  mov     r9d, 20019h; samDesired
0x180015637  mov     [rsp+30h+phkResult], rax; phkResult
0x18001563c  xor     r8d, r8d; ulOptions
0x18001563f  lea     rdx, aSystemCurrentc_27; "System\\CurrentControlSet\\Services\\ra"...
0x180015646  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001564d  call    cs:__imp_RegOpenKeyExW
0x180015653  test    eax, eax
0x180015655  jnz     loc_180015721
0x18001565b  mov     rcx, [rbp+hKey]; hKey
0x18001565f  lea     r9, [rbp+Type]; lpType
0x180015663  mov     [rbp+Type], eax
0x180015666  lea     rdx, aProhibitipsec; "ProhibitIpSec"
0x18001566d  mov     [rbp+Data], eax
0x180015670  xor     r8d, r8d; lpReserved
0x180015673  lea     rax, [rbp+cbData]
0x180015677  mov     [rbp+cbData], 4
0x18001567e  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180015683  lea     rax, [rbp+Data]
0x180015687  mov     [rsp+30h+phkResult], rax; lpData
0x18001568c  call    cs:__imp_RegQueryValueExW
0x180015692  xor     ecx, ecx
0x180015694  mov     [rbp+cbData], 4
0x18001569b  test    eax, eax
0x18001569d  lea     r9, [rbp+Type]; lpType
0x1800156a1  lea     rax, [rbp+cbData]
0x1800156a5  cmovz   ecx, [rbp+Data]
0x1800156a9  lea     rdx, aAllowl2tpweakc; "AllowL2TPWeakCrypto"
0x1800156b0  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800156b5  xor     r8d, r8d; lpReserved
0x1800156b8  mov     cs:g_dwProhibitIpsec, ecx
0x1800156be  lea     rax, [rbp+Data]
0x1800156c2  mov     rcx, [rbp+hKey]; hKey
0x1800156c6  mov     [rsp+30h+phkResult], rax; lpData
0x1800156cb  call    cs:__imp_RegQueryValueExW
0x1800156d1  xor     ecx, ecx
0x1800156d3  mov     [rbp+cbData], 4
0x1800156da  test    eax, eax
0x1800156dc  lea     r9, [rbp+Type]; lpType
0x1800156e0  lea     rax, [rbp+cbData]
0x1800156e4  cmovz   ecx, [rbp+Data]
0x1800156e8  lea     rdx, aL2tpcrlcheckle; "L2tpCRLCheckLevel"
0x1800156ef  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800156f4  xor     r8d, r8d; lpReserved
0x1800156f7  mov     cs:g_dwAllowL2TPWeakCrypto, ecx
0x1800156fd  lea     rax, [rbp+Data]
0x180015701  mov     rcx, [rbp+hKey]; hKey
0x180015705  mov     [rsp+30h+phkResult], rax; lpData
0x18001570a  call    cs:__imp_RegQueryValueExW
0x180015710  test    eax, eax
0x180015712  mov     ecx, 1
0x180015717  cmovz   ecx, [rbp+Data]
0x18001571b  mov     cs:g_dwL2TPCRLCheckLevel, ecx
0x180015721  mov     rcx, [rbp+hKey]; hKey
0x180015725  test    rcx, rcx
0x180015728  jz      short loc_180015738
0x18001572a  call    cs:__imp_RegCloseKey
0x180015730  mov     [rbp+hKey], 0
0x180015738  lea     rax, [rbp+hKey]
0x18001573c  mov     r9d, 1; samDesired
0x180015742  xor     r8d, r8d; ulOptions
0x180015745  mov     [rsp+30h+phkResult], rax; phkResult
0x18001574a  lea     rdx, aSystemCurrentc_14; "SYSTEM\\CurrentControlSet\\Services\\Po"...
0x180015751  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015758  call    cs:__imp_RegOpenKeyExW
0x18001575e  test    eax, eax
0x180015760  jnz     short loc_1800157B1
0x180015762  mov     rcx, [rbp+hKey]; hKey
0x180015766  lea     r9, [rbp+Data]; lpType
0x18001576a  mov     [rbp+Data], eax
0x18001576d  lea     rdx, aAssumeudpencap; "AssumeUDPEncapsulationContextOnSendRule"
0x180015774  mov     [rbp+cbData], eax
0x180015777  xor     r8d, r8d; lpReserved
0x18001577a  lea     rax, [rbp+Type]
0x18001577e  mov     [rbp+Type], 4
0x180015785  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18001578a  lea     rax, [rbp+cbData]
0x18001578e  mov     [rsp+30h+phkResult], rax; lpData
0x180015793  call    cs:__imp_RegQueryValueExW
0x180015799  test    eax, eax
0x18001579b  jnz     short loc_1800157B1
0x18001579d  cmp     [rbp+Data], 4
0x1800157a1  jnz     short loc_1800157B1
0x1800157a3  mov     eax, [rbp+cbData]
0x1800157a6  cmp     eax, 2
0x1800157a9  ja      short loc_1800157B1
0x1800157ab  mov     cs:g_dwIpsecUdpEncapsulation, eax
0x1800157b1  mov     rcx, [rbp+hKey]; hKey
0x1800157b5  test    rcx, rcx
0x1800157b8  jz      short loc_1800157C0
0x1800157ba  call    cs:__imp_RegCloseKey
0x1800157c0  add     rsp, 30h
0x1800157c4  pop     rbp
0x1800157c5  retn
```
