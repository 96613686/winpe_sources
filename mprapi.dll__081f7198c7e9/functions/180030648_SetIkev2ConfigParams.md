# SetIkev2ConfigParams

- ea: `0x180030648`
- end: `0x180030b76`
- name: `SetIkev2ConfigParams`
- size: `1326`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180028a18`
- `0x18004dd80`

## callees

- `0x180016c40`
- `0x180030648`
- `0x180030b7c`
- `0x180051160`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800308a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030ad5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030b21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030b38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030b47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800308a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030ad5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030b21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030b38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030b47`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180030910`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180030910`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030749`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030786`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030899`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003093d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030973`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030a94`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030ac5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030b13`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030749`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030786`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030899`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003093d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030973`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030a94`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030ac5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030b13`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800307ca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003085c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800309c1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030a53`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800307ca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003085c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800309c1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030a53`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003094f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030b29`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003094f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030b29`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800307e6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800309dd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800307e6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800309dd`

## string_xrefs

- `0x1800306cf`: `ConfigOptions`

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
0x180030648  mov     [rsp-8+arg_8], rbx
0x18003064d  push    rbp
0x18003064e  push    rsi
0x18003064f  push    rdi
0x180030650  push    r12
0x180030652  push    r13
0x180030654  push    r14
0x180030656  push    r15
0x180030658  lea     rbp, [rsp-27h]
0x18003065d  sub     rsp, 0E0h
0x180030664  mov     rax, cs:__security_cookie
0x18003066b  xor     rax, rsp
0x18003066e  mov     [rbp+57h+var_38], rax
0x180030672  xor     r12d, r12d
0x180030675  movsx   r15d, dl
0x180030679  lea     rax, aIdletimeout; "idleTimeout"
0x180030680  mov     [rbp+57h+hKey], r12
0x180030684  mov     [rbp+57h+lpValueName], rax
0x180030688  mov     rsi, rcx
0x18003068b  lea     rax, aNetworkblackou; "networkBlackoutTime"
0x180030692  mov     [rbp+57h+var_A8], r12
0x180030696  mov     [rbp+57h+var_90], rax
0x18003069a  mov     ecx, r15d
0x18003069d  mov     [rbp+57h+dwDisposition], r12d
0x1800306a1  lea     rax, [r8+4]
0x1800306a5  mov     [rbp+57h+var_88], rax
0x1800306a9  lea     rax, aSalifetime; "saLifeTime"
0x1800306b0  mov     [rbp+57h+var_80], rax
0x1800306b4  lea     rax, [r8+8]
0x1800306b8  mov     [rbp+57h+var_78], rax
0x1800306bc  lea     rax, aSadatasize; "saDataSize"
0x1800306c3  mov     [rbp+57h+var_70], rax
0x1800306c7  lea     rax, [r8+0Ch]
0x1800306cb  mov     [rbp+57h+var_68], rax
0x1800306cf  lea     rax, aConfigoptions; "ConfigOptions"
0x1800306d6  mov     [rbp+57h+var_60], rax
0x1800306da  lea     rax, [r8+10h]
0x1800306de  mov     [rbp+57h+var_58], rax
0x1800306e2  mov     rdi, r8
0x1800306e5  mov     [rbp+57h+var_98], r8
0x1800306e9  sub     ecx, 1
0x1800306ec  jz      short loc_18003071D
0x1800306ee  sub     ecx, 1
0x1800306f1  jz      short loc_18003070C
0x1800306f3  sub     ecx, 1
0x1800306f6  jz      short loc_18003070C
0x1800306f8  sub     ecx, 1
0x1800306fb  jz      short loc_18003070C
0x1800306fd  cmp     ecx, 1
0x180030700  jz      short loc_18003070C
0x180030702  lea     ebx, [r12+32h]
0x180030707  jmp     loc_180030B4D
0x18003070c  cmp     dword ptr [r8+30h], 3
0x180030711  jbe     short loc_18003071D
0x180030713  mov     ebx, 57h ; 'W'
0x180030718  jmp     loc_180030B4D
0x18003071d  mov     r14d, r12d
0x180030720  mov     r13d, 4
0x180030726  mov     edx, r14d
0x180030729  mov     r9d, r13d; dwType
0x18003072c  add     rdx, rdx
0x18003072f  mov     [rsp+110h+cbData], r13d; cbData
0x180030734  xor     r8d, r8d; Reserved
0x180030737  mov     rcx, rsi; hKey
0x18003073a  mov     rax, [rbp+rdx*8+57h+var_98]
0x18003073f  mov     rdx, [rbp+rdx*8+57h+lpValueName]; lpValueName
0x180030744  mov     [rsp+110h+lpData], rax; lpData
0x180030749  call    cs:__imp_RegSetValueExW
0x18003074f  mov     ebx, eax
0x180030751  test    eax, eax
0x180030753  jnz     loc_180030B2F
0x180030759  inc     r14d
0x18003075c  cmp     r14d, 5
0x180030760  jb      short loc_180030726
0x180030762  cmp     r15b, 5
0x180030766  jl      short loc_180030796
0x180030768  lea     rax, [rdi+60h]
0x18003076c  mov     [rsp+110h+cbData], r13d; cbData
0x180030771  mov     r9d, r13d; dwType
0x180030774  mov     [rsp+110h+lpData], rax; lpData
0x180030779  xor     r8d, r8d; Reserved
0x18003077c  lea     rdx, aMmsalifetime; "mmSaLifeTime"
0x180030783  mov     rcx, rsi; hKey
0x180030786  call    cs:__imp_RegSetValueExW
0x18003078c  mov     ebx, eax
0x18003078e  test    eax, eax
0x180030790  jnz     loc_180030B2F
0x180030796  lea     rax, [rbp+57h+dwDisposition]
0x18003079a  xor     r9d, r9d; lpClass
0x18003079d  mov     [rsp+110h+lpdwDisposition], rax; lpdwDisposition
0x1800307a2  lea     rdx, aAllowedtrusted; "AllowedTrustedRootCerts"
0x1800307a9  lea     rax, [rbp+57h+hKey]
0x1800307ad  xor     r8d, r8d; Reserved
0x1800307b0  mov     [rsp+110h+phkResult], rax; phkResult
0x1800307b5  mov     rcx, rsi; hKey
0x1800307b8  mov     [rsp+110h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800307bd  mov     [rsp+110h+cbData], 0F003Fh; samDesired
0x1800307c5  mov     dword ptr [rsp+110h+lpData], r12d; dwOptions
0x1800307ca  call    cs:__imp_RegCreateKeyExW
0x1800307d0  mov     ebx, eax
0x1800307d2  test    eax, eax
0x1800307d4  jnz     loc_180030B2F
0x1800307da  cmp     [rbp+57h+dwDisposition], 2
0x1800307de  jnz     short loc_1800307F6
0x1800307e0  mov     rcx, [rbp+57h+hKey]; hKey
0x1800307e4  xor     edx, edx; lpSubKey
0x1800307e6  call    cs:__imp_RegDeleteTreeW
0x1800307ec  mov     ebx, eax
0x1800307ee  test    eax, eax
0x1800307f0  jnz     loc_180030B2F
0x1800307f6  mov     eax, [rdi+14h]
0x1800307f9  test    eax, eax
0x1800307fb  jz      loc_1800308C4
0x180030801  mov     [rbp+57h+var_B8], r12
0x180030805  mov     r14d, r12d
0x180030808  mov     r9d, r14d
0x18003080b  lea     r8, a04d; "%04d"
0x180030812  mov     edx, 0Ch; unsigned __int64
0x180030817  lea     rcx, [rbp+57h+SubKey]; unsigned __int16 *
0x18003081b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030820  mov     ebx, eax
0x180030822  test    eax, eax
0x180030824  js      loc_1800308EB
0x18003082a  mov     rcx, [rbp+57h+hKey]; hKey
0x18003082e  lea     rax, [rbp+57h+dwDisposition]
0x180030832  mov     [rsp+110h+lpdwDisposition], rax; lpdwDisposition
0x180030837  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18003083b  lea     rax, [rbp+57h+var_B8]
0x18003083f  xor     r9d, r9d; lpClass
0x180030842  mov     [rsp+110h+phkResult], rax; phkResult
0x180030847  xor     r8d, r8d; Reserved
0x18003084a  mov     [rsp+110h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18003084f  mov     [rsp+110h+cbData], 0F003Fh; samDesired
0x180030857  mov     dword ptr [rsp+110h+lpData], r12d; dwOptions
0x18003085c  call    cs:__imp_RegCreateKeyExW
0x180030862  mov     ebx, eax
0x180030864  test    eax, eax
0x180030866  jnz     loc_180030B2F
0x18003086c  mov     rcx, [rdi+18h]
0x180030870  lea     r9d, [rbx+3]; dwType
0x180030874  mov     edx, r14d
0x180030877  xor     r8d, r8d; Reserved
0x18003087a  add     rdx, rdx
0x18003087d  mov     eax, [rcx+rdx*8]
0x180030880  mov     [rsp+110h+cbData], eax; cbData
0x180030884  mov     rax, [rcx+rdx*8+8]
0x180030889  lea     rdx, Value; "TrustedRootCert"
0x180030890  mov     rcx, [rbp+57h+var_B8]; hKey
0x180030894  mov     [rsp+110h+lpData], rax; lpData
0x180030899  call    cs:__imp_RegSetValueExW
0x18003089f  mov     rcx, [rbp+57h+var_B8]; hKey
0x1800308a3  mov     ebx, eax
0x1800308a5  call    cs:__imp_RegCloseKey
0x1800308ab  mov     [rbp+57h+var_B8], r12
0x1800308af  test    ebx, ebx
0x1800308b1  jnz     loc_180030B2F
0x1800308b7  inc     r14d
0x1800308ba  cmp     r14d, [rdi+14h]
0x1800308be  jb      loc_180030808
0x1800308c4  cmp     r15b, 2
0x1800308c8  jl      loc_180030983
0x1800308ce  mov     rdx, [rdi+38h]
0x1800308d2  mov     rcx, rsi; hKey
0x1800308d5  test    rdx, rdx
0x1800308d8  jz      short loc_180030903
0x1800308da  call    SetIkev2CustomPolicy
0x1800308df  mov     ebx, eax
0x1800308e1  test    eax, eax
0x1800308e3  jnz     loc_180030B2F
0x1800308e9  jmp     short loc_180030916
0x1800308eb  and     eax, 1FFF0000h
0x1800308f0  cmp     eax, 70000h
0x1800308f5  jnz     loc_180030B2F
0x1800308fb  movzx   ebx, bx
0x1800308fe  jmp     loc_180030B2F
0x180030903  xor     r9d, r9d; Reserved
0x180030906  lea     rdx, aIkev2custompol; "IKEv2CustomPolicy"
0x18003090d  xor     r8d, r8d; samDesired
0x180030910  call    cs:__imp_RegDeleteKeyExW
0x180030916  mov     eax, [rdi+20h]
0x180030919  lea     rdx, aMachinecertifi_0; "MachineCertificateName"
0x180030920  mov     rcx, rsi; hKey
0x180030923  test    eax, eax
0x180030925  jz      short loc_18003094F
0x180030927  mov     [rsp+110h+cbData], eax; cbData
0x18003092b  mov     r9d, 3; dwType
0x180030931  mov     rax, [rdi+28h]
0x180030935  xor     r8d, r8d; Reserved
0x180030938  mov     [rsp+110h+lpData], rax; lpData
0x18003093d  call    cs:__imp_RegSetValueExW
0x180030943  mov     ebx, eax
0x180030945  test    eax, eax
0x180030947  jnz     loc_180030B2F
0x18003094d  jmp     short loc_180030955
0x18003094f  call    cs:__imp_RegDeleteValueW
0x180030955  lea     rax, [rdi+30h]
0x180030959  mov     [rsp+110h+cbData], r13d; cbData
0x18003095e  mov     r9d, r13d; dwType
0x180030961  mov     [rsp+110h+lpData], rax; lpData
0x180030966  xor     r8d, r8d; Reserved
0x180030969  lea     rdx, aEncryptiontype; "EncryptionType"
0x180030970  mov     rcx, rsi; hKey
0x180030973  call    cs:__imp_RegSetValueExW
0x180030979  mov     ebx, eax
0x18003097b  test    eax, eax
0x18003097d  jnz     loc_180030B2F
0x180030983  cmp     r15b, 3
0x180030987  jl      loc_180030B2F
0x18003098d  lea     rax, [rbp+57h+dwDisposition]
0x180030991  xor     r9d, r9d; lpClass
0x180030994  mov     [rsp+110h+lpdwDisposition], rax; lpdwDisposition
0x180030999  lea     rdx, aAllowedcerteku; "AllowedCertEku"
0x1800309a0  lea     rax, [rbp+57h+var_A8]
0x1800309a4  xor     r8d, r8d; Reserved
0x1800309a7  mov     [rsp+110h+phkResult], rax; phkResult
0x1800309ac  mov     rcx, rsi; hKey
0x1800309af  mov     [rsp+110h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800309b4  mov     [rsp+110h+cbData], 2001Fh; samDesired
0x1800309bc  mov     dword ptr [rsp+110h+lpData], r12d; dwOptions
0x1800309c1  call    cs:__imp_RegCreateKeyExW
0x1800309c7  mov     ebx, eax
0x1800309c9  test    eax, eax
0x1800309cb  jnz     loc_180030B2F
0x1800309d1  cmp     [rbp+57h+dwDisposition], 2
0x1800309d5  jnz     short loc_1800309ED
0x1800309d7  mov     rcx, [rbp+57h+var_A8]; hKey
0x1800309db  xor     edx, edx; lpSubKey
0x1800309dd  call    cs:__imp_RegDeleteTreeW
0x1800309e3  mov     ebx, eax
0x1800309e5  test    eax, eax
0x1800309e7  jnz     loc_180030B2F
0x1800309ed  mov     eax, [rdi+40h]
0x1800309f0  test    eax, eax
0x1800309f2  jz      loc_180030AEC
0x1800309f8  mov     [rbp+57h+var_B8], r12
0x1800309fc  mov     r14d, r12d
0x1800309ff  mov     r9d, r14d
0x180030a02  lea     r8, a04d; "%04d"
0x180030a09  mov     edx, 0Ch; unsigned __int64
0x180030a0e  lea     rcx, [rbp+57h+SubKey]; unsigned __int16 *
0x180030a12  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030a17  mov     ebx, eax
0x180030a19  test    eax, eax
0x180030a1b  js      loc_1800308EB
0x180030a21  mov     rcx, [rbp+57h+var_A8]; hKey
0x180030a25  lea     rax, [rbp+57h+dwDisposition]
0x180030a29  mov     [rsp+110h+lpdwDisposition], rax; lpdwDisposition
0x180030a2e  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180030a32  lea     rax, [rbp+57h+var_B8]
0x180030a36  xor     r9d, r9d; lpClass
0x180030a39  mov     [rsp+110h+phkResult], rax; phkResult
0x180030a3e  xor     r8d, r8d; Reserved
0x180030a41  mov     [rsp+110h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180030a46  mov     [rsp+110h+cbData], 2001Fh; samDesired
0x180030a4e  mov     dword ptr [rsp+110h+lpData], r12d; dwOptions
0x180030a53  call    cs:__imp_RegCreateKeyExW
0x180030a59  mov     ebx, eax
0x180030a5b  test    eax, eax
0x180030a5d  jnz     loc_180030B2F
0x180030a63  mov     rcx, [rdi+48h]
0x180030a67  lea     r9d, [rbx+1]; dwType
0x180030a6b  mov     r15d, r14d
0x180030a6e  lea     rdx, aTrustedeku; "TrustedEku"
0x180030a75  shl     r15, 4
0x180030a79  xor     r8d, r8d; Reserved
0x180030a7c  mov     eax, [r15+rcx]
0x180030a80  add     eax, eax
0x180030a82  mov     [rsp+110h+cbData], eax; cbData
0x180030a86  mov     rax, [r15+rcx+8]
0x180030a8b  mov     rcx, [rbp+57h+var_B8]; hKey
0x180030a8f  mov     [rsp+110h+lpData], rax; lpData
0x180030a94  call    cs:__imp_RegSetValueExW
0x180030a9a  mov     ebx, eax
0x180030a9c  test    eax, eax
0x180030a9e  jnz     short loc_180030B1D
0x180030aa0  mov     rcx, [rdi+48h]
0x180030aa4  lea     rdx, aIsekuoid; "IsEkuOID"
0x180030aab  add     rcx, r13
0x180030aae  mov     [rsp+110h+cbData], r13d; cbData
0x180030ab3  add     rcx, r15
0x180030ab6  mov     r9d, r13d; dwType
0x180030ab9  mov     [rsp+110h+lpData], rcx; lpData
0x180030abe  xor     r8d, r8d; Reserved
0x180030ac1  mov     rcx, [rbp+57h+var_B8]; hKey
0x180030ac5  call    cs:__imp_RegSetValueExW
0x180030acb  mov     rcx, [rbp+57h+var_B8]; hKey
0x180030acf  mov     ebx, eax
0x180030ad1  test    eax, eax
0x180030ad3  jnz     short loc_180030B21
0x180030ad5  call    cs:__imp_RegCloseKey
0x180030adb  inc     r14d
0x180030ade  mov     [rbp+57h+var_B8], r12
0x180030ae2  cmp     r14d, [rdi+40h]
0x180030ae6  jb      loc_1800309FF
0x180030aec  mov     eax, [rdi+50h]
0x180030aef  lea     rdx, aMachinecertifi; "MachineCertificateHash"
0x180030af6  mov     rcx, rsi; hKey
0x180030af9  test    eax, eax
0x180030afb  jz      short loc_180030B29
0x180030afd  mov     [rsp+110h+cbData], eax; cbData
  ... truncated ...
```
