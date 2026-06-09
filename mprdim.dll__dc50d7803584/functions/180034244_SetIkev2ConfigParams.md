# SetIkev2ConfigParams

- ea: `0x180034244`
- end: `0x180034725`
- name: `SetIkev2ConfigParams`
- size: `1249`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180042b00`

## callees

- `0x180034244`
- `0x18003472c`
- `0x1800347e0`
- `0x180046e70`

## import_xrefs

- `KERNEL32!RegDeleteKeyExW` at `0x1800344cd`
- `KERNEL32!RegDeleteKeyExW` at `0x1800344cd`
- `KERNEL32!RegDeleteValueW` at `0x18003450c`
- `KERNEL32!RegDeleteValueW` at `0x1800346d8`
- `KERNEL32!RegDeleteValueW` at `0x18003450c`
- `KERNEL32!RegDeleteValueW` at `0x1800346d8`
- `ADVAPI32!RegSetValueExW` at `0x180034324`
- `ADVAPI32!RegSetValueExW` at `0x180034349`
- `ADVAPI32!RegSetValueExW` at `0x180034465`
- `ADVAPI32!RegSetValueExW` at `0x1800344fa`
- `ADVAPI32!RegSetValueExW` at `0x18003452c`
- `ADVAPI32!RegSetValueExW` at `0x18003464c`
- `ADVAPI32!RegSetValueExW` at `0x18003467d`
- `ADVAPI32!RegSetValueExW` at `0x1800346ce`
- `ADVAPI32!RegSetValueExW` at `0x180034324`
- `ADVAPI32!RegSetValueExW` at `0x180034349`
- `ADVAPI32!RegSetValueExW` at `0x180034465`
- `ADVAPI32!RegSetValueExW` at `0x1800344fa`
- `ADVAPI32!RegSetValueExW` at `0x18003452c`
- `ADVAPI32!RegSetValueExW` at `0x18003464c`
- `ADVAPI32!RegSetValueExW` at `0x18003467d`
- `ADVAPI32!RegSetValueExW` at `0x1800346ce`
- `ADVAPI32!RegCloseKey` at `0x180034471`
- `ADVAPI32!RegCloseKey` at `0x18003468d`
- `ADVAPI32!RegCloseKey` at `0x18003469f`
- `ADVAPI32!RegCloseKey` at `0x1800346e7`
- `ADVAPI32!RegCloseKey` at `0x1800346f6`
- `ADVAPI32!RegCloseKey` at `0x180034471`
- `ADVAPI32!RegCloseKey` at `0x18003468d`
- `ADVAPI32!RegCloseKey` at `0x18003469f`
- `ADVAPI32!RegCloseKey` at `0x1800346e7`
- `ADVAPI32!RegCloseKey` at `0x1800346f6`
- `ADVAPI32!RegDeleteTreeW` at `0x1800343a9`
- `ADVAPI32!RegDeleteTreeW` at `0x18003458c`
- `ADVAPI32!RegDeleteTreeW` at `0x1800343a9`
- `ADVAPI32!RegDeleteTreeW` at `0x18003458c`
- `ADVAPI32!RegCreateKeyExW` at `0x18003438d`
- `ADVAPI32!RegCreateKeyExW` at `0x180034428`
- `ADVAPI32!RegCreateKeyExW` at `0x180034570`
- `ADVAPI32!RegCreateKeyExW` at `0x18003460b`
- `ADVAPI32!RegCreateKeyExW` at `0x18003438d`
- `ADVAPI32!RegCreateKeyExW` at `0x180034428`
- `ADVAPI32!RegCreateKeyExW` at `0x180034570`
- `ADVAPI32!RegCreateKeyExW` at `0x18003460b`

## string_xrefs

- `0x1800342d3`: `ConfigOptions`

## pseudocode

```c
__int64 __fastcall SetIkev2ConfigParams(HKEY hKey, __int64 a2, __int64 a3)
{
  const BYTE *lpData; // r15
  bool v4; // cc
  unsigned int v7; // ebx
  unsigned int i; // r14d
  unsigned int j; // r14d
  HRESULT v10; // eax
  DWORD cbData; // eax
  unsigned int k; // r14d
  __int64 v13; // r15
  LSTATUS v14; // eax
  HKEY v15; // rcx
  DWORD v16; // eax
  DWORD dwDisposition; // [rsp+50h] [rbp-69h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-61h] BYREF
  HKEY hKeya; // [rsp+60h] [rbp-59h] BYREF
  HKEY v21; // [rsp+68h] [rbp-51h] BYREF
  LPCWSTR lpValueName; // [rsp+70h] [rbp-49h]
  BYTE *v23[9]; // [rsp+78h] [rbp-41h]
  wchar_t pszDest[12]; // [rsp+C0h] [rbp+7h] BYREF

  v23[0] = (BYTE *)a3;
  hKeya = 0;
  lpValueName = L"idleTimeout";
  lpData = (const BYTE *)(a3 + 48);
  v4 = *(_DWORD *)(a3 + 48) <= 3u;
  v23[1] = (BYTE *)L"networkBlackoutTime";
  v21 = 0;
  v23[2] = (BYTE *)(a3 + 4);
  dwDisposition = 0;
  v23[3] = (BYTE *)L"saLifeTime";
  v23[4] = (BYTE *)(a3 + 8);
  v23[5] = (BYTE *)L"saDataSize";
  v23[6] = (BYTE *)(a3 + 12);
  v23[7] = (BYTE *)L"ConfigOptions";
  v23[8] = (BYTE *)(a3 + 16);
  if ( !v4 )
    return 87;
  for ( i = 0; i < 5; ++i )
  {
    v7 = RegSetValueExW(hKey, (LPCWSTR)v23[2 * i - 1], 0, 4u, v23[2 * i], 4u);
    if ( v7 )
      goto LABEL_45;
  }
  v7 = RegSetValueExW(hKey, L"mmSaLifeTime", 0, 4u, (const BYTE *)(a3 + 96), 4u);
  if ( !v7 )
  {
    v7 = RegCreateKeyExW(hKey, L"AllowedTrustedRootCerts", 0, 0, 0, 0xF003Fu, 0, &hKeya, &dwDisposition);
    if ( !v7 && (dwDisposition != 2 || (v7 = RegDeleteTreeW(hKeya, 0)) == 0) )
    {
      if ( *(_DWORD *)(a3 + 20) )
      {
        phkResult = 0;
        for ( j = 0; j < *(_DWORD *)(a3 + 20); ++j )
        {
          v10 = StringCchPrintfW(pszDest, 0xCu, L"%04d", j);
          v7 = v10;
          if ( v10 < 0 )
          {
LABEL_18:
            if ( (v10 & 0x1FFF0000) == 0x70000 )
              v7 = (unsigned __int16)v7;
            goto LABEL_45;
          }
          v7 = RegCreateKeyExW(hKeya, pszDest, 0, 0, 0, 0xF003Fu, 0, &phkResult, &dwDisposition);
          if ( !v7 )
          {
            v7 = RegSetValueExW(
                   phkResult,
                   L"TrustedRootCert",
                   0,
                   3u,
                   *(const BYTE **)(*(_QWORD *)(a3 + 24) + 16LL * j + 8),
                   *(_DWORD *)(*(_QWORD *)(a3 + 24) + 16LL * j));
            RegCloseKey(phkResult);
            phkResult = 0;
            if ( !v7 )
              continue;
          }
          goto LABEL_45;
        }
      }
      if ( *(_QWORD *)(a3 + 56) )
      {
        v7 = SetIkev2CustomPolicy(hKey);
        if ( v7 )
          goto LABEL_45;
      }
      else
      {
        RegDeleteKeyExW(hKey, L"IKEv2CustomPolicy", 0, 0);
      }
      cbData = *(_DWORD *)(a3 + 32);
      if ( !cbData )
      {
        RegDeleteValueW(hKey, L"MachineCertificateName");
LABEL_28:
        v7 = RegSetValueExW(hKey, L"EncryptionType", 0, 4u, lpData, 4u);
        if ( !v7 )
        {
          v7 = RegCreateKeyExW(hKey, L"AllowedCertEku", 0, 0, 0, 0x2001Fu, 0, &v21, &dwDisposition);
          if ( !v7 && (dwDisposition != 2 || (v7 = RegDeleteTreeW(v21, 0)) == 0) )
          {
            if ( *(_DWORD *)(a3 + 64) )
            {
              for ( k = 0; ; ++k )
              {
                phkResult = 0;
                if ( k >= *(_DWORD *)(a3 + 64) )
                  break;
                v10 = StringCchPrintfW(pszDest, 0xCu, L"%04d", k);
                v7 = v10;
                if ( v10 < 0 )
                  goto LABEL_18;
                v7 = RegCreateKeyExW(v21, pszDest, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
                if ( v7 )
                  goto LABEL_45;
                v13 = 16LL * k;
                v7 = RegSetValueExW(
                       phkResult,
                       L"TrustedEku",
                       0,
                       1u,
                       *(const BYTE **)(v13 + *(_QWORD *)(a3 + 72) + 8),
                       2 * *(_DWORD *)(v13 + *(_QWORD *)(a3 + 72)));
                if ( v7 )
                {
                  v15 = phkResult;
LABEL_41:
                  RegCloseKey(v15);
                  goto LABEL_45;
                }
                v14 = RegSetValueExW(
                        phkResult,
                        L"IsEkuOID",
                        0,
                        4u,
                        (const BYTE *)(v13 + *(_QWORD *)(a3 + 72) + 4LL),
                        4u);
                v15 = phkResult;
                v7 = v14;
                if ( v14 )
                  goto LABEL_41;
                RegCloseKey(phkResult);
              }
            }
            v16 = *(_DWORD *)(a3 + 80);
            if ( v16 )
              v7 = RegSetValueExW(hKey, L"MachineCertificateHash", 0, 3u, *(const BYTE **)(a3 + 88), v16);
            else
              RegDeleteValueW(hKey, L"MachineCertificateHash");
          }
        }
        goto LABEL_45;
      }
      v7 = RegSetValueExW(hKey, L"MachineCertificateName", 0, 3u, *(const BYTE **)(a3 + 40), cbData);
      if ( !v7 )
        goto LABEL_28;
    }
  }
LABEL_45:
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( v21 )
    RegCloseKey(v21);
  return v7;
}

```

## disassembly

```asm
0x180034244  mov     [rsp-8+arg_8], rbx
0x180034249  push    rbp
0x18003424a  push    rsi
0x18003424b  push    rdi
0x18003424c  push    r12
0x18003424e  push    r13
0x180034250  push    r14
0x180034252  push    r15
0x180034254  lea     rbp, [rsp-27h]
0x180034259  sub     rsp, 0E0h
0x180034260  mov     rax, cs:__security_cookie
0x180034267  xor     rax, rsp
0x18003426a  mov     [rbp+57h+var_38], rax
0x18003426e  xor     r12d, r12d
0x180034271  mov     [rbp+57h+var_98], r8
0x180034275  lea     rax, aIdletimeout; "idleTimeout"
0x18003427c  mov     [rbp+57h+hKey], r12
0x180034280  mov     [rbp+57h+lpValueName], rax
0x180034284  lea     r15, [r8+30h]
0x180034288  cmp     dword ptr [r15], 3
0x18003428c  lea     rax, aNetworkblackou; "networkBlackoutTime"
0x180034293  mov     [rbp+57h+var_90], rax
0x180034297  mov     rdi, r8
0x18003429a  lea     rax, [r8+4]
0x18003429e  mov     [rbp+57h+var_A8], r12
0x1800342a2  mov     [rbp+57h+var_88], rax
0x1800342a6  mov     rsi, rcx
0x1800342a9  lea     rax, aSalifetime; "saLifeTime"
0x1800342b0  mov     [rbp+57h+dwDisposition], r12d
0x1800342b4  mov     [rbp+57h+var_80], rax
0x1800342b8  lea     rax, [r8+8]
0x1800342bc  mov     [rbp+57h+var_78], rax
0x1800342c0  lea     rax, aSadatasize; "saDataSize"
0x1800342c7  mov     [rbp+57h+var_70], rax
0x1800342cb  lea     rax, [r8+0Ch]
0x1800342cf  mov     [rbp+57h+var_68], rax
0x1800342d3  lea     rax, aConfigoptions; "ConfigOptions"
0x1800342da  mov     [rbp+57h+var_60], rax
0x1800342de  lea     rax, [r8+10h]
0x1800342e2  mov     [rbp+57h+var_58], rax
0x1800342e6  jbe     short loc_1800342F2
0x1800342e8  lea     ebx, [r12+57h]
0x1800342ed  jmp     loc_1800346FC
0x1800342f2  mov     r14d, r12d
0x1800342f5  mov     r13d, 4
0x1800342fb  xor     r8d, r8d; Reserved
0x1800342fe  mov     [rsp+110h+cbData], r13d; cbData
0x180034303  mov     r9d, r13d; dwType
0x180034306  mov     rcx, rsi; hKey
0x180034309  cmp     r14d, 5
0x18003430d  jnb     short loc_180034339
0x18003430f  mov     edx, r14d
0x180034312  add     rdx, rdx
0x180034315  mov     rax, [rbp+rdx*8+57h+var_98]
0x18003431a  mov     rdx, [rbp+rdx*8+57h+lpValueName]; lpValueName
0x18003431f  mov     [rsp+110h+lpData], rax; lpData
0x180034324  call    cs:__imp_RegSetValueExW
0x18003432a  mov     ebx, eax
0x18003432c  test    eax, eax
0x18003432e  jnz     loc_1800346DE
0x180034334  inc     r14d
0x180034337  jmp     short loc_1800342FB
0x180034339  lea     rax, [rdi+60h]
0x18003433d  lea     rdx, aMmsalifetime_0; "mmSaLifeTime"
0x180034344  mov     [rsp+110h+lpData], rax; lpData
0x180034349  call    cs:__imp_RegSetValueExW
0x18003434f  mov     ebx, eax
0x180034351  test    eax, eax
0x180034353  jnz     loc_1800346DE
0x180034359  lea     rax, [rbp+57h+dwDisposition]
0x18003435d  xor     r9d, r9d; lpClass
0x180034360  mov     [rsp+110h+lpdwDisposition], rax; lpdwDisposition
0x180034365  lea     rdx, aAllowedtrusted; "AllowedTrustedRootCerts"
0x18003436c  lea     rax, [rbp+57h+hKey]
0x180034370  xor     r8d, r8d; Reserved
0x180034373  mov     [rsp+110h+phkResult], rax; phkResult
0x180034378  mov     rcx, rsi; hKey
0x18003437b  mov     [rsp+110h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180034380  mov     [rsp+110h+cbData], 0F003Fh; samDesired
0x180034388  mov     dword ptr [rsp+110h+lpData], r12d; dwOptions
0x18003438d  call    cs:__imp_RegCreateKeyExW
0x180034393  mov     ebx, eax
0x180034395  test    eax, eax
0x180034397  jnz     loc_1800346DE
0x18003439d  cmp     [rbp+57h+dwDisposition], 2
0x1800343a1  jnz     short loc_1800343B9
0x1800343a3  mov     rcx, [rbp+57h+hKey]; hKey
0x1800343a7  xor     edx, edx; lpSubKey
0x1800343a9  call    cs:__imp_RegDeleteTreeW
0x1800343af  mov     ebx, eax
0x1800343b1  test    eax, eax
0x1800343b3  jnz     loc_1800346DE
0x1800343b9  cmp     [rdi+14h], r12d
0x1800343bd  jz      loc_1800344A3
0x1800343c3  mov     [rbp+57h+var_B8], r12
0x1800343c7  mov     r14d, r12d
0x1800343ca  cmp     r14d, [rdi+14h]
0x1800343ce  jnb     loc_1800344A3
0x1800343d4  mov     r9d, r14d
0x1800343d7  lea     r8, a04d; "%04d"
0x1800343de  mov     edx, 0Ch; cchDest
0x1800343e3  lea     rcx, [rbp+57h+pszDest]; pszDest
0x1800343e7  call    StringCchPrintfW
0x1800343ec  mov     ebx, eax
0x1800343ee  test    eax, eax
0x1800343f0  js      loc_18003448B
0x1800343f6  mov     rcx, [rbp+57h+hKey]; hKey
0x1800343fa  lea     rax, [rbp+57h+dwDisposition]
0x1800343fe  mov     [rsp+110h+lpdwDisposition], rax; lpdwDisposition
0x180034403  lea     rdx, [rbp+57h+pszDest]; lpSubKey
0x180034407  lea     rax, [rbp+57h+var_B8]
0x18003440b  xor     r9d, r9d; lpClass
0x18003440e  mov     [rsp+110h+phkResult], rax; phkResult
0x180034413  xor     r8d, r8d; Reserved
0x180034416  mov     [rsp+110h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18003441b  mov     [rsp+110h+cbData], 0F003Fh; samDesired
0x180034423  mov     dword ptr [rsp+110h+lpData], r12d; dwOptions
0x180034428  call    cs:__imp_RegCreateKeyExW
0x18003442e  mov     ebx, eax
0x180034430  test    eax, eax
0x180034432  jnz     loc_1800346DE
0x180034438  mov     rcx, [rdi+18h]
0x18003443c  lea     r9d, [rbx+3]; dwType
0x180034440  mov     edx, r14d
0x180034443  xor     r8d, r8d; Reserved
0x180034446  add     rdx, rdx
0x180034449  mov     eax, [rcx+rdx*8]
0x18003444c  mov     [rsp+110h+cbData], eax; cbData
0x180034450  mov     rax, [rcx+rdx*8+8]
0x180034455  lea     rdx, Value; "TrustedRootCert"
0x18003445c  mov     rcx, [rbp+57h+var_B8]; hKey
0x180034460  mov     [rsp+110h+lpData], rax; lpData
0x180034465  call    cs:__imp_RegSetValueExW
0x18003446b  mov     rcx, [rbp+57h+var_B8]; hKey
0x18003446f  mov     ebx, eax
0x180034471  call    cs:__imp_RegCloseKey
0x180034477  mov     [rbp+57h+var_B8], r12
0x18003447b  test    ebx, ebx
0x18003447d  jnz     loc_1800346DE
0x180034483  inc     r14d
0x180034486  jmp     loc_1800343CA
0x18003448b  and     eax, 1FFF0000h
0x180034490  cmp     eax, 70000h
0x180034495  jnz     loc_1800346DE
0x18003449b  movzx   ebx, bx
0x18003449e  jmp     loc_1800346DE
0x1800344a3  mov     rdx, [rdi+38h]
0x1800344a7  mov     rcx, rsi; hKey
0x1800344aa  test    rdx, rdx
0x1800344ad  jz      short loc_1800344C0
0x1800344af  call    SetIkev2CustomPolicy
0x1800344b4  mov     ebx, eax
0x1800344b6  test    eax, eax
0x1800344b8  jnz     loc_1800346DE
0x1800344be  jmp     short loc_1800344D3
0x1800344c0  xor     r9d, r9d; Reserved
0x1800344c3  lea     rdx, aIkev2custompol; "IKEv2CustomPolicy"
0x1800344ca  xor     r8d, r8d; samDesired
0x1800344cd  call    cs:__imp_RegDeleteKeyExW
0x1800344d3  mov     eax, [rdi+20h]
0x1800344d6  lea     rdx, aMachinecertifi_0; "MachineCertificateName"
0x1800344dd  mov     rcx, rsi; hKey
0x1800344e0  test    eax, eax
0x1800344e2  jz      short loc_18003450C
0x1800344e4  mov     [rsp+110h+cbData], eax; cbData
0x1800344e8  mov     r9d, 3; dwType
0x1800344ee  mov     rax, [rdi+28h]
0x1800344f2  xor     r8d, r8d; Reserved
0x1800344f5  mov     [rsp+110h+lpData], rax; lpData
0x1800344fa  call    cs:__imp_RegSetValueExW
0x180034500  mov     ebx, eax
0x180034502  test    eax, eax
0x180034504  jnz     loc_1800346DE
0x18003450a  jmp     short loc_180034512
0x18003450c  call    cs:__imp_RegDeleteValueW
0x180034512  mov     [rsp+110h+cbData], r13d; cbData
0x180034517  lea     rdx, aEncryptiontype; "EncryptionType"
0x18003451e  mov     r9d, r13d; dwType
0x180034521  mov     [rsp+110h+lpData], r15; lpData
0x180034526  xor     r8d, r8d; Reserved
0x180034529  mov     rcx, rsi; hKey
0x18003452c  call    cs:__imp_RegSetValueExW
0x180034532  mov     ebx, eax
0x180034534  test    eax, eax
0x180034536  jnz     loc_1800346DE
0x18003453c  lea     rax, [rbp+57h+dwDisposition]
0x180034540  xor     r9d, r9d; lpClass
0x180034543  mov     [rsp+110h+lpdwDisposition], rax; lpdwDisposition
0x180034548  lea     rdx, aAllowedcerteku; "AllowedCertEku"
0x18003454f  lea     rax, [rbp+57h+var_A8]
0x180034553  xor     r8d, r8d; Reserved
0x180034556  mov     [rsp+110h+phkResult], rax; phkResult
0x18003455b  mov     rcx, rsi; hKey
0x18003455e  mov     [rsp+110h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180034563  mov     [rsp+110h+cbData], 2001Fh; samDesired
0x18003456b  mov     dword ptr [rsp+110h+lpData], r12d; dwOptions
0x180034570  call    cs:__imp_RegCreateKeyExW
0x180034576  mov     ebx, eax
0x180034578  test    eax, eax
0x18003457a  jnz     loc_1800346DE
0x180034580  cmp     [rbp+57h+dwDisposition], 2
0x180034584  jnz     short loc_18003459C
0x180034586  mov     rcx, [rbp+57h+var_A8]; hKey
0x18003458a  xor     edx, edx; lpSubKey
0x18003458c  call    cs:__imp_RegDeleteTreeW
0x180034592  mov     ebx, eax
0x180034594  test    eax, eax
0x180034596  jnz     loc_1800346DE
0x18003459c  cmp     [rdi+40h], r12d
0x1800345a0  jz      loc_1800346A7
0x1800345a6  mov     r14d, r12d
0x1800345a9  mov     [rbp+57h+var_B8], r12
0x1800345ad  cmp     r14d, [rdi+40h]
0x1800345b1  jnb     loc_1800346A7
0x1800345b7  mov     r9d, r14d
0x1800345ba  lea     r8, a04d; "%04d"
0x1800345c1  mov     edx, 0Ch; cchDest
0x1800345c6  lea     rcx, [rbp+57h+pszDest]; pszDest
0x1800345ca  call    StringCchPrintfW
0x1800345cf  mov     ebx, eax
0x1800345d1  test    eax, eax
0x1800345d3  js      loc_18003448B
0x1800345d9  mov     rcx, [rbp+57h+var_A8]; hKey
0x1800345dd  lea     rax, [rbp+57h+dwDisposition]
0x1800345e1  mov     [rsp+110h+lpdwDisposition], rax; lpdwDisposition
0x1800345e6  lea     rdx, [rbp+57h+pszDest]; lpSubKey
0x1800345ea  lea     rax, [rbp+57h+var_B8]
0x1800345ee  xor     r9d, r9d; lpClass
0x1800345f1  mov     [rsp+110h+phkResult], rax; phkResult
0x1800345f6  xor     r8d, r8d; Reserved
0x1800345f9  mov     [rsp+110h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800345fe  mov     [rsp+110h+cbData], 2001Fh; samDesired
0x180034606  mov     dword ptr [rsp+110h+lpData], r12d; dwOptions
0x18003460b  call    cs:__imp_RegCreateKeyExW
0x180034611  mov     ebx, eax
0x180034613  test    eax, eax
0x180034615  jnz     loc_1800346DE
0x18003461b  mov     rcx, [rdi+48h]
0x18003461f  lea     r9d, [rbx+1]; dwType
0x180034623  mov     r15d, r14d
0x180034626  lea     rdx, aTrustedeku; "TrustedEku"
0x18003462d  shl     r15, 4
0x180034631  xor     r8d, r8d; Reserved
0x180034634  mov     eax, [r15+rcx]
0x180034638  add     eax, eax
0x18003463a  mov     [rsp+110h+cbData], eax; cbData
0x18003463e  mov     rax, [r15+rcx+8]
0x180034643  mov     rcx, [rbp+57h+var_B8]; hKey
0x180034647  mov     [rsp+110h+lpData], rax; lpData
0x18003464c  call    cs:__imp_RegSetValueExW
0x180034652  mov     ebx, eax
0x180034654  test    eax, eax
0x180034656  jnz     short loc_18003469B
0x180034658  mov     rcx, [rdi+48h]
0x18003465c  lea     rdx, aIsekuoid; "IsEkuOID"
0x180034663  add     rcx, r13
0x180034666  mov     [rsp+110h+cbData], r13d; cbData
0x18003466b  add     rcx, r15
0x18003466e  mov     r9d, r13d; dwType
0x180034671  mov     [rsp+110h+lpData], rcx; lpData
0x180034676  xor     r8d, r8d; Reserved
0x180034679  mov     rcx, [rbp+57h+var_B8]; hKey
0x18003467d  call    cs:__imp_RegSetValueExW
0x180034683  mov     rcx, [rbp+57h+var_B8]; hKey
0x180034687  mov     ebx, eax
0x180034689  test    eax, eax
0x18003468b  jnz     short loc_18003469F
0x18003468d  call    cs:__imp_RegCloseKey
0x180034693  inc     r14d
0x180034696  jmp     loc_1800345A9
0x18003469b  mov     rcx, [rbp+57h+var_B8]; hKey
0x18003469f  call    cs:__imp_RegCloseKey
0x1800346a5  jmp     short loc_1800346DE
0x1800346a7  mov     eax, [rdi+50h]
0x1800346aa  lea     rdx, aMachinecertifi; "MachineCertificateHash"
0x1800346b1  mov     rcx, rsi; hKey
0x1800346b4  test    eax, eax
0x1800346b6  jz      short loc_1800346D8
0x1800346b8  mov     [rsp+110h+cbData], eax; cbData
0x1800346bc  mov     r9d, 3; dwType
0x1800346c2  mov     rax, [rdi+58h]
0x1800346c6  xor     r8d, r8d; Reserved
0x1800346c9  mov     [rsp+110h+lpData], rax; lpData
0x1800346ce  call    cs:__imp_RegSetValueExW
0x1800346d4  mov     ebx, eax
0x1800346d6  jmp     short loc_1800346DE
0x1800346d8  call    cs:__imp_RegDeleteValueW
0x1800346de  mov     rcx, [rbp+57h+hKey]; hKey
0x1800346e2  test    rcx, rcx
0x1800346e5  jz      short loc_1800346ED
0x1800346e7  call    cs:__imp_RegCloseKey
0x1800346ed  mov     rcx, [rbp+57h+var_A8]; hKey
0x1800346f1  test    rcx, rcx
0x1800346f4  jz      short loc_1800346FC
0x1800346f6  call    cs:__imp_RegCloseKey
0x1800346fc  mov     eax, ebx
0x1800346fe  mov     rcx, [rbp+57h+var_38]
0x180034702  xor     rcx, rsp; StackCookie
0x180034705  call    __security_check_cookie
0x18003470a  mov     rbx, [rsp+110h+arg_8]
  ... truncated ...
```
