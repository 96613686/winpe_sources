# SetIkev2ConfigParams

- ea: `0x180073a40`
- end: `0x180073f6e`
- name: `SetIkev2ConfigParams`
- size: `1326`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800059f0`

## callees

- `0x180045f14`
- `0x180073a40`
- `0x180073f74`
- `0x18008c630`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180073b41`
- `ADVAPI32!RegSetValueExW` at `0x180073b7e`
- `ADVAPI32!RegSetValueExW` at `0x180073c91`
- `ADVAPI32!RegSetValueExW` at `0x180073d35`
- `ADVAPI32!RegSetValueExW` at `0x180073d6b`
- `ADVAPI32!RegSetValueExW` at `0x180073e8c`
- `ADVAPI32!RegSetValueExW` at `0x180073ebd`
- `ADVAPI32!RegSetValueExW` at `0x180073f0b`
- `ADVAPI32!RegSetValueExW` at `0x180073b41`
- `ADVAPI32!RegSetValueExW` at `0x180073b7e`
- `ADVAPI32!RegSetValueExW` at `0x180073c91`
- `ADVAPI32!RegSetValueExW` at `0x180073d35`
- `ADVAPI32!RegSetValueExW` at `0x180073d6b`
- `ADVAPI32!RegSetValueExW` at `0x180073e8c`
- `ADVAPI32!RegSetValueExW` at `0x180073ebd`
- `ADVAPI32!RegSetValueExW` at `0x180073f0b`
- `ADVAPI32!RegCloseKey` at `0x180073c9d`
- `ADVAPI32!RegCloseKey` at `0x180073ecd`
- `ADVAPI32!RegCloseKey` at `0x180073f19`
- `ADVAPI32!RegCloseKey` at `0x180073f30`
- `ADVAPI32!RegCloseKey` at `0x180073f3f`
- `ADVAPI32!RegCloseKey` at `0x180073c9d`
- `ADVAPI32!RegCloseKey` at `0x180073ecd`
- `ADVAPI32!RegCloseKey` at `0x180073f19`
- `ADVAPI32!RegCloseKey` at `0x180073f30`
- `ADVAPI32!RegCloseKey` at `0x180073f3f`
- `ADVAPI32!RegDeleteValueW` at `0x180073d47`
- `ADVAPI32!RegDeleteValueW` at `0x180073f21`
- `ADVAPI32!RegDeleteValueW` at `0x180073d47`
- `ADVAPI32!RegDeleteValueW` at `0x180073f21`
- `ADVAPI32!RegCreateKeyExW` at `0x180073bc2`
- `ADVAPI32!RegCreateKeyExW` at `0x180073c54`
- `ADVAPI32!RegCreateKeyExW` at `0x180073db9`
- `ADVAPI32!RegCreateKeyExW` at `0x180073e4b`
- `ADVAPI32!RegCreateKeyExW` at `0x180073bc2`
- `ADVAPI32!RegCreateKeyExW` at `0x180073c54`
- `ADVAPI32!RegCreateKeyExW` at `0x180073db9`
- `ADVAPI32!RegCreateKeyExW` at `0x180073e4b`
- `ADVAPI32!RegDeleteKeyExW` at `0x180073d08`
- `ADVAPI32!RegDeleteKeyExW` at `0x180073d08`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180073bde`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180073dd5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180073bde`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180073dd5`

## string_xrefs

- `0x180073ac7`: `ConfigOptions`

## pseudocode

```c
__int64 __fastcall SetIkev2ConfigParams(HKEY hKey, char a2, __int64 a3)
{
  unsigned int v6; // ebx
  unsigned int i; // r14d
  unsigned int v8; // r14d
  int v9; // eax
  DWORD cbData; // eax
  unsigned int v11; // r14d
  __int64 v12; // r15
  LSTATUS v13; // eax
  HKEY v14; // rcx
  DWORD v15; // eax
  DWORD dwDisposition; // [rsp+50h] [rbp-69h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-61h] BYREF
  HKEY hKeya; // [rsp+60h] [rbp-59h] BYREF
  HKEY v20; // [rsp+68h] [rbp-51h] BYREF
  LPCWSTR lpValueName; // [rsp+70h] [rbp-49h]
  BYTE *v22[9]; // [rsp+78h] [rbp-41h]
  WCHAR SubKey[12]; // [rsp+C0h] [rbp+7h] BYREF

  hKeya = 0;
  lpValueName = L"idleTimeout";
  v20 = 0;
  v22[1] = (BYTE *)L"networkBlackoutTime";
  dwDisposition = 0;
  v22[2] = (BYTE *)(a3 + 4);
  v22[3] = (BYTE *)L"saLifeTime";
  v22[4] = (BYTE *)(a3 + 8);
  v22[5] = (BYTE *)L"saDataSize";
  v22[6] = (BYTE *)(a3 + 12);
  v22[7] = (BYTE *)L"ConfigOptions";
  v22[8] = (BYTE *)(a3 + 16);
  v22[0] = (BYTE *)a3;
  if ( a2 != 1 )
  {
    if ( a2 != 2 && a2 != 3 && (unsigned int)(a2 - 4) >= 2 )
      return 50;
    if ( *(_DWORD *)(a3 + 48) > 3u )
      return 87;
  }
  for ( i = 0; i < 5; ++i )
  {
    v6 = RegSetValueExW(hKey, (LPCWSTR)v22[2 * i - 1], 0, 4u, v22[2 * i], 4u);
    if ( v6 )
      goto LABEL_50;
  }
  if ( a2 >= 5 )
  {
    v6 = RegSetValueExW(hKey, L"mmSaLifeTime", 0, 4u, (const BYTE *)(a3 + 96), 4u);
    if ( v6 )
      goto LABEL_50;
  }
  v6 = RegCreateKeyExW(hKey, L"AllowedTrustedRootCerts", 0, 0, 0, 0xF003Fu, 0, &hKeya, &dwDisposition);
  if ( v6 )
    goto LABEL_50;
  if ( dwDisposition == 2 )
  {
    v6 = RegDeleteTreeW(hKeya, 0);
    if ( v6 )
      goto LABEL_50;
  }
  if ( *(_DWORD *)(a3 + 20) )
  {
    phkResult = 0;
    v8 = 0;
    while ( 1 )
    {
      v9 = StringCchPrintfW(SubKey, 0xCu, L"%04d", v8);
      v6 = v9;
      if ( v9 < 0 )
        break;
      v6 = RegCreateKeyExW(hKeya, SubKey, 0, 0, 0, 0xF003Fu, 0, &phkResult, &dwDisposition);
      if ( v6 )
        goto LABEL_50;
      v6 = RegSetValueExW(
             phkResult,
             L"TrustedRootCert",
             0,
             3u,
             *(const BYTE **)(*(_QWORD *)(a3 + 24) + 16LL * v8 + 8),
             *(_DWORD *)(*(_QWORD *)(a3 + 24) + 16LL * v8));
      RegCloseKey(phkResult);
      phkResult = 0;
      if ( v6 )
        goto LABEL_50;
      if ( ++v8 >= *(_DWORD *)(a3 + 20) )
        goto LABEL_22;
    }
LABEL_26:
    if ( (v9 & 0x1FFF0000) == 0x70000 )
      v6 = (unsigned __int16)v6;
    goto LABEL_50;
  }
LABEL_22:
  if ( a2 < 2 )
    goto LABEL_57;
  if ( *(_QWORD *)(a3 + 56) )
  {
    v6 = SetIkev2CustomPolicy(hKey);
    if ( v6 )
      goto LABEL_50;
  }
  else
  {
    RegDeleteKeyExW(hKey, L"IKEv2CustomPolicy", 0, 0);
  }
  cbData = *(_DWORD *)(a3 + 32);
  if ( cbData )
  {
    v6 = RegSetValueExW(hKey, L"MachineCertificateName", 0, 3u, *(const BYTE **)(a3 + 40), cbData);
    if ( v6 )
      goto LABEL_50;
  }
  else
  {
    RegDeleteValueW(hKey, L"MachineCertificateName");
  }
  v6 = RegSetValueExW(hKey, L"EncryptionType", 0, 4u, (const BYTE *)(a3 + 48), 4u);
  if ( !v6 )
  {
LABEL_57:
    if ( a2 >= 3 )
    {
      v6 = RegCreateKeyExW(hKey, L"AllowedCertEku", 0, 0, 0, 0x2001Fu, 0, &v20, &dwDisposition);
      if ( !v6 && (dwDisposition != 2 || (v6 = RegDeleteTreeW(v20, 0)) == 0) )
      {
        if ( !*(_DWORD *)(a3 + 64) )
        {
LABEL_45:
          v15 = *(_DWORD *)(a3 + 80);
          if ( v15 )
            v6 = RegSetValueExW(hKey, L"MachineCertificateHash", 0, 3u, *(const BYTE **)(a3 + 88), v15);
          else
            RegDeleteValueW(hKey, L"MachineCertificateHash");
          goto LABEL_50;
        }
        phkResult = 0;
        v11 = 0;
        while ( 1 )
        {
          v9 = StringCchPrintfW(SubKey, 0xCu, L"%04d", v11);
          v6 = v9;
          if ( v9 < 0 )
            goto LABEL_26;
          v6 = RegCreateKeyExW(v20, SubKey, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
          if ( v6 )
            break;
          v12 = 16LL * v11;
          v6 = RegSetValueExW(
                 phkResult,
                 L"TrustedEku",
                 0,
                 1u,
                 *(const BYTE **)(v12 + *(_QWORD *)(a3 + 72) + 8),
                 2 * *(_DWORD *)(v12 + *(_QWORD *)(a3 + 72)));
          if ( v6 )
          {
            v14 = phkResult;
LABEL_48:
            RegCloseKey(v14);
            break;
          }
          v13 = RegSetValueExW(phkResult, L"IsEkuOID", 0, 4u, (const BYTE *)(v12 + *(_QWORD *)(a3 + 72) + 4LL), 4u);
          v14 = phkResult;
          v6 = v13;
          if ( v13 )
            goto LABEL_48;
          RegCloseKey(phkResult);
          ++v11;
          phkResult = 0;
          if ( v11 >= *(_DWORD *)(a3 + 64) )
            goto LABEL_45;
        }
      }
    }
  }
LABEL_50:
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( v20 )
    RegCloseKey(v20);
  return v6;
}

```

## disassembly

```asm
0x180073a40  mov     [rsp-8+arg_8], rbx
0x180073a45  push    rbp
0x180073a46  push    rsi
0x180073a47  push    rdi
0x180073a48  push    r12
0x180073a4a  push    r13
0x180073a4c  push    r14
0x180073a4e  push    r15
0x180073a50  lea     rbp, [rsp-27h]
0x180073a55  sub     rsp, 0E0h
0x180073a5c  mov     rax, cs:__security_cookie
0x180073a63  xor     rax, rsp
0x180073a66  mov     [rbp+57h+var_38], rax
0x180073a6a  xor     r12d, r12d
0x180073a6d  movsx   r15d, dl
0x180073a71  lea     rax, aIdletimeout; "idleTimeout"
0x180073a78  mov     [rbp+57h+hKey], r12
0x180073a7c  mov     [rbp+57h+lpValueName], rax
0x180073a80  mov     rsi, rcx
0x180073a83  lea     rax, aNetworkblackou; "networkBlackoutTime"
0x180073a8a  mov     [rbp+57h+var_A8], r12
0x180073a8e  mov     [rbp+57h+var_90], rax
0x180073a92  mov     ecx, r15d
0x180073a95  mov     [rbp+57h+dwDisposition], r12d
0x180073a99  lea     rax, [r8+4]
0x180073a9d  mov     [rbp+57h+var_88], rax
0x180073aa1  lea     rax, aSalifetime; "saLifeTime"
0x180073aa8  mov     [rbp+57h+var_80], rax
0x180073aac  lea     rax, [r8+8]
0x180073ab0  mov     [rbp+57h+var_78], rax
0x180073ab4  lea     rax, aSadatasize; "saDataSize"
0x180073abb  mov     [rbp+57h+var_70], rax
0x180073abf  lea     rax, [r8+0Ch]
0x180073ac3  mov     [rbp+57h+var_68], rax
0x180073ac7  lea     rax, aConfigoptions; "ConfigOptions"
0x180073ace  mov     [rbp+57h+var_60], rax
0x180073ad2  lea     rax, [r8+10h]
0x180073ad6  mov     [rbp+57h+var_58], rax
0x180073ada  mov     rdi, r8
0x180073add  mov     [rbp+57h+var_98], r8
0x180073ae1  sub     ecx, 1
0x180073ae4  jz      short loc_180073B15
0x180073ae6  sub     ecx, 1
0x180073ae9  jz      short loc_180073B04
0x180073aeb  sub     ecx, 1
0x180073aee  jz      short loc_180073B04
0x180073af0  sub     ecx, 1
0x180073af3  jz      short loc_180073B04
0x180073af5  cmp     ecx, 1
0x180073af8  jz      short loc_180073B04
0x180073afa  lea     ebx, [r12+32h]
0x180073aff  jmp     loc_180073F45
0x180073b04  cmp     dword ptr [r8+30h], 3
0x180073b09  jbe     short loc_180073B15
0x180073b0b  mov     ebx, 57h ; 'W'
0x180073b10  jmp     loc_180073F45
0x180073b15  mov     r14d, r12d
0x180073b18  mov     r13d, 4
0x180073b1e  mov     edx, r14d
0x180073b21  mov     r9d, r13d; dwType
0x180073b24  add     rdx, rdx
0x180073b27  mov     [rsp+110h+cbData], r13d; cbData
0x180073b2c  xor     r8d, r8d; Reserved
0x180073b2f  mov     rcx, rsi; hKey
0x180073b32  mov     rax, [rbp+rdx*8+57h+var_98]
0x180073b37  mov     rdx, [rbp+rdx*8+57h+lpValueName]; lpValueName
0x180073b3c  mov     [rsp+110h+lpData], rax; lpData
0x180073b41  call    cs:__imp_RegSetValueExW
0x180073b47  mov     ebx, eax
0x180073b49  test    eax, eax
0x180073b4b  jnz     loc_180073F27
0x180073b51  inc     r14d
0x180073b54  cmp     r14d, 5
0x180073b58  jb      short loc_180073B1E
0x180073b5a  cmp     r15b, 5
0x180073b5e  jl      short loc_180073B8E
0x180073b60  lea     rax, [rdi+60h]
0x180073b64  mov     [rsp+110h+cbData], r13d; cbData
0x180073b69  mov     r9d, r13d; dwType
0x180073b6c  mov     [rsp+110h+lpData], rax; lpData
0x180073b71  xor     r8d, r8d; Reserved
0x180073b74  lea     rdx, aMmsalifetime; "mmSaLifeTime"
0x180073b7b  mov     rcx, rsi; hKey
0x180073b7e  call    cs:__imp_RegSetValueExW
0x180073b84  mov     ebx, eax
0x180073b86  test    eax, eax
0x180073b88  jnz     loc_180073F27
0x180073b8e  lea     rax, [rbp+57h+dwDisposition]
0x180073b92  xor     r9d, r9d; lpClass
0x180073b95  mov     [rsp+110h+lpdwDisposition], rax; lpdwDisposition
0x180073b9a  lea     rdx, aAllowedtrusted; "AllowedTrustedRootCerts"
0x180073ba1  lea     rax, [rbp+57h+hKey]
0x180073ba5  xor     r8d, r8d; Reserved
0x180073ba8  mov     [rsp+110h+phkResult], rax; phkResult
0x180073bad  mov     rcx, rsi; hKey
0x180073bb0  mov     [rsp+110h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180073bb5  mov     [rsp+110h+cbData], 0F003Fh; samDesired
0x180073bbd  mov     dword ptr [rsp+110h+lpData], r12d; dwOptions
0x180073bc2  call    cs:__imp_RegCreateKeyExW
0x180073bc8  mov     ebx, eax
0x180073bca  test    eax, eax
0x180073bcc  jnz     loc_180073F27
0x180073bd2  cmp     [rbp+57h+dwDisposition], 2
0x180073bd6  jnz     short loc_180073BEE
0x180073bd8  mov     rcx, [rbp+57h+hKey]; hKey
0x180073bdc  xor     edx, edx; lpSubKey
0x180073bde  call    cs:__imp_RegDeleteTreeW
0x180073be4  mov     ebx, eax
0x180073be6  test    eax, eax
0x180073be8  jnz     loc_180073F27
0x180073bee  mov     eax, [rdi+14h]
0x180073bf1  test    eax, eax
0x180073bf3  jz      loc_180073CBC
0x180073bf9  mov     [rbp+57h+var_B8], r12
0x180073bfd  mov     r14d, r12d
0x180073c00  mov     r9d, r14d
0x180073c03  lea     r8, a04d; "%04d"
0x180073c0a  mov     edx, 0Ch; unsigned __int64
0x180073c0f  lea     rcx, [rbp+57h+SubKey]; unsigned __int16 *
0x180073c13  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180073c18  mov     ebx, eax
0x180073c1a  test    eax, eax
0x180073c1c  js      loc_180073CE3
0x180073c22  mov     rcx, [rbp+57h+hKey]; hKey
0x180073c26  lea     rax, [rbp+57h+dwDisposition]
0x180073c2a  mov     [rsp+110h+lpdwDisposition], rax; lpdwDisposition
0x180073c2f  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180073c33  lea     rax, [rbp+57h+var_B8]
0x180073c37  xor     r9d, r9d; lpClass
0x180073c3a  mov     [rsp+110h+phkResult], rax; phkResult
0x180073c3f  xor     r8d, r8d; Reserved
0x180073c42  mov     [rsp+110h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180073c47  mov     [rsp+110h+cbData], 0F003Fh; samDesired
0x180073c4f  mov     dword ptr [rsp+110h+lpData], r12d; dwOptions
0x180073c54  call    cs:__imp_RegCreateKeyExW
0x180073c5a  mov     ebx, eax
0x180073c5c  test    eax, eax
0x180073c5e  jnz     loc_180073F27
0x180073c64  mov     rcx, [rdi+18h]
0x180073c68  lea     r9d, [rbx+3]; dwType
0x180073c6c  mov     edx, r14d
0x180073c6f  xor     r8d, r8d; Reserved
0x180073c72  add     rdx, rdx
0x180073c75  mov     eax, [rcx+rdx*8]
0x180073c78  mov     [rsp+110h+cbData], eax; cbData
0x180073c7c  mov     rax, [rcx+rdx*8+8]
0x180073c81  lea     rdx, Value; "TrustedRootCert"
0x180073c88  mov     rcx, [rbp+57h+var_B8]; hKey
0x180073c8c  mov     [rsp+110h+lpData], rax; lpData
0x180073c91  call    cs:__imp_RegSetValueExW
0x180073c97  mov     rcx, [rbp+57h+var_B8]; hKey
0x180073c9b  mov     ebx, eax
0x180073c9d  call    cs:__imp_RegCloseKey
0x180073ca3  mov     [rbp+57h+var_B8], r12
0x180073ca7  test    ebx, ebx
0x180073ca9  jnz     loc_180073F27
0x180073caf  inc     r14d
0x180073cb2  cmp     r14d, [rdi+14h]
0x180073cb6  jb      loc_180073C00
0x180073cbc  cmp     r15b, 2
0x180073cc0  jl      loc_180073D7B
0x180073cc6  mov     rdx, [rdi+38h]
0x180073cca  mov     rcx, rsi; hKey
0x180073ccd  test    rdx, rdx
0x180073cd0  jz      short loc_180073CFB
0x180073cd2  call    SetIkev2CustomPolicy
0x180073cd7  mov     ebx, eax
0x180073cd9  test    eax, eax
0x180073cdb  jnz     loc_180073F27
0x180073ce1  jmp     short loc_180073D0E
0x180073ce3  and     eax, 1FFF0000h
0x180073ce8  cmp     eax, 70000h
0x180073ced  jnz     loc_180073F27
0x180073cf3  movzx   ebx, bx
0x180073cf6  jmp     loc_180073F27
0x180073cfb  xor     r9d, r9d; Reserved
0x180073cfe  lea     rdx, aIkev2custompol; "IKEv2CustomPolicy"
0x180073d05  xor     r8d, r8d; samDesired
0x180073d08  call    cs:__imp_RegDeleteKeyExW
0x180073d0e  mov     eax, [rdi+20h]
0x180073d11  lea     rdx, aMachinecertifi_0; "MachineCertificateName"
0x180073d18  mov     rcx, rsi; hKey
0x180073d1b  test    eax, eax
0x180073d1d  jz      short loc_180073D47
0x180073d1f  mov     [rsp+110h+cbData], eax; cbData
0x180073d23  mov     r9d, 3; dwType
0x180073d29  mov     rax, [rdi+28h]
0x180073d2d  xor     r8d, r8d; Reserved
0x180073d30  mov     [rsp+110h+lpData], rax; lpData
0x180073d35  call    cs:__imp_RegSetValueExW
0x180073d3b  mov     ebx, eax
0x180073d3d  test    eax, eax
0x180073d3f  jnz     loc_180073F27
0x180073d45  jmp     short loc_180073D4D
0x180073d47  call    cs:__imp_RegDeleteValueW
0x180073d4d  lea     rax, [rdi+30h]
0x180073d51  mov     [rsp+110h+cbData], r13d; cbData
0x180073d56  mov     r9d, r13d; dwType
0x180073d59  mov     [rsp+110h+lpData], rax; lpData
0x180073d5e  xor     r8d, r8d; Reserved
0x180073d61  lea     rdx, aEncryptiontype; "EncryptionType"
0x180073d68  mov     rcx, rsi; hKey
0x180073d6b  call    cs:__imp_RegSetValueExW
0x180073d71  mov     ebx, eax
0x180073d73  test    eax, eax
0x180073d75  jnz     loc_180073F27
0x180073d7b  cmp     r15b, 3
0x180073d7f  jl      loc_180073F27
0x180073d85  lea     rax, [rbp+57h+dwDisposition]
0x180073d89  xor     r9d, r9d; lpClass
0x180073d8c  mov     [rsp+110h+lpdwDisposition], rax; lpdwDisposition
0x180073d91  lea     rdx, aAllowedcerteku; "AllowedCertEku"
0x180073d98  lea     rax, [rbp+57h+var_A8]
0x180073d9c  xor     r8d, r8d; Reserved
0x180073d9f  mov     [rsp+110h+phkResult], rax; phkResult
0x180073da4  mov     rcx, rsi; hKey
0x180073da7  mov     [rsp+110h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180073dac  mov     [rsp+110h+cbData], 2001Fh; samDesired
0x180073db4  mov     dword ptr [rsp+110h+lpData], r12d; dwOptions
0x180073db9  call    cs:__imp_RegCreateKeyExW
0x180073dbf  mov     ebx, eax
0x180073dc1  test    eax, eax
0x180073dc3  jnz     loc_180073F27
0x180073dc9  cmp     [rbp+57h+dwDisposition], 2
0x180073dcd  jnz     short loc_180073DE5
0x180073dcf  mov     rcx, [rbp+57h+var_A8]; hKey
0x180073dd3  xor     edx, edx; lpSubKey
0x180073dd5  call    cs:__imp_RegDeleteTreeW
0x180073ddb  mov     ebx, eax
0x180073ddd  test    eax, eax
0x180073ddf  jnz     loc_180073F27
0x180073de5  mov     eax, [rdi+40h]
0x180073de8  test    eax, eax
0x180073dea  jz      loc_180073EE4
0x180073df0  mov     [rbp+57h+var_B8], r12
0x180073df4  mov     r14d, r12d
0x180073df7  mov     r9d, r14d
0x180073dfa  lea     r8, a04d; "%04d"
0x180073e01  mov     edx, 0Ch; unsigned __int64
0x180073e06  lea     rcx, [rbp+57h+SubKey]; unsigned __int16 *
0x180073e0a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180073e0f  mov     ebx, eax
0x180073e11  test    eax, eax
0x180073e13  js      loc_180073CE3
0x180073e19  mov     rcx, [rbp+57h+var_A8]; hKey
0x180073e1d  lea     rax, [rbp+57h+dwDisposition]
0x180073e21  mov     [rsp+110h+lpdwDisposition], rax; lpdwDisposition
0x180073e26  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180073e2a  lea     rax, [rbp+57h+var_B8]
0x180073e2e  xor     r9d, r9d; lpClass
0x180073e31  mov     [rsp+110h+phkResult], rax; phkResult
0x180073e36  xor     r8d, r8d; Reserved
0x180073e39  mov     [rsp+110h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180073e3e  mov     [rsp+110h+cbData], 2001Fh; samDesired
0x180073e46  mov     dword ptr [rsp+110h+lpData], r12d; dwOptions
0x180073e4b  call    cs:__imp_RegCreateKeyExW
0x180073e51  mov     ebx, eax
0x180073e53  test    eax, eax
0x180073e55  jnz     loc_180073F27
0x180073e5b  mov     rcx, [rdi+48h]
0x180073e5f  lea     r9d, [rbx+1]; dwType
0x180073e63  mov     r15d, r14d
0x180073e66  lea     rdx, aTrustedeku; "TrustedEku"
0x180073e6d  shl     r15, 4
0x180073e71  xor     r8d, r8d; Reserved
0x180073e74  mov     eax, [r15+rcx]
0x180073e78  add     eax, eax
0x180073e7a  mov     [rsp+110h+cbData], eax; cbData
0x180073e7e  mov     rax, [r15+rcx+8]
0x180073e83  mov     rcx, [rbp+57h+var_B8]; hKey
0x180073e87  mov     [rsp+110h+lpData], rax; lpData
0x180073e8c  call    cs:__imp_RegSetValueExW
0x180073e92  mov     ebx, eax
0x180073e94  test    eax, eax
0x180073e96  jnz     short loc_180073F15
0x180073e98  mov     rcx, [rdi+48h]
0x180073e9c  lea     rdx, aIsekuoid; "IsEkuOID"
0x180073ea3  add     rcx, r13
0x180073ea6  mov     [rsp+110h+cbData], r13d; cbData
0x180073eab  add     rcx, r15
0x180073eae  mov     r9d, r13d; dwType
0x180073eb1  mov     [rsp+110h+lpData], rcx; lpData
0x180073eb6  xor     r8d, r8d; Reserved
0x180073eb9  mov     rcx, [rbp+57h+var_B8]; hKey
0x180073ebd  call    cs:__imp_RegSetValueExW
0x180073ec3  mov     rcx, [rbp+57h+var_B8]; hKey
0x180073ec7  mov     ebx, eax
0x180073ec9  test    eax, eax
0x180073ecb  jnz     short loc_180073F19
0x180073ecd  call    cs:__imp_RegCloseKey
0x180073ed3  inc     r14d
0x180073ed6  mov     [rbp+57h+var_B8], r12
0x180073eda  cmp     r14d, [rdi+40h]
0x180073ede  jb      loc_180073DF7
0x180073ee4  mov     eax, [rdi+50h]
0x180073ee7  lea     rdx, aMachinecertifi; "MachineCertificateHash"
0x180073eee  mov     rcx, rsi; hKey
0x180073ef1  test    eax, eax
0x180073ef3  jz      short loc_180073F21
0x180073ef5  mov     [rsp+110h+cbData], eax; cbData
  ... truncated ...
```
