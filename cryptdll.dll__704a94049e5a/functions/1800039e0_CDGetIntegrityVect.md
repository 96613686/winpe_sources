# CDGetIntegrityVect

- ea: `0x1800039e0`
- end: `0x180003c57`
- name: `CDGetIntegrityVect`
- size: `631`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800039e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003a18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003a46`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003ad4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003a18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003a46`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003ad4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003aa8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003b49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003aa8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003b49`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003a8c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003b16`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003a8c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003b16`

## pseudocode

```c
__int64 __fastcall CDGetIntegrityVect(int *a1)
{
  int v2; // edi
  LSTATUS v3; // eax
  LSTATUS v4; // eax
  char v5; // r10
  int v6; // r10d
  unsigned int v7; // r9d
  unsigned int v8; // edx
  int v9; // ebx
  unsigned __int64 v10; // r8
  int v11; // eax
  int v12; // eax
  int v13; // ecx
  bool v14; // zf
  unsigned int v15; // eax
  DWORD Type; // [rsp+50h] [rbp+8h] BYREF
  int Data; // [rsp+58h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  v2 = 1;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System\\Kerberos\\Parameters",
         0,
         0x20019u,
         &hKey);
  if ( v3 == 2 )
  {
    v2 = 0;
    v3 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Control\\Lsa\\Kerberos\\Parameters",
           0,
           0x20019u,
           &hKey);
  }
  if ( !v3 )
  {
    Type = 0;
    Data = 0;
    cbData = 4;
    v4 = RegQueryValueExW(hKey, L"SupportedEncryptionTypes", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( v4 == 2 )
    {
      if ( !v2 )
        goto LABEL_12;
      RegCloseKey(hKey);
      hKey = 0;
      if ( RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Control\\Lsa\\Kerberos\\Parameters",
             0,
             0x20019u,
             &hKey) )
      {
        goto LABEL_12;
      }
      Type = 0;
      Data = 0;
      cbData = 4;
      v4 = RegQueryValueExW(hKey, L"SupportedEncryptionTypes", 0, &Type, (LPBYTE)&Data, &cbData);
    }
    if ( !v4 && Type == 4 && Data )
    {
      GlobalSupportedEncryptionTypes = Data;
LABEL_13:
      RegCloseKey(hKey);
      v5 = GlobalSupportedEncryptionTypes;
      goto LABEL_15;
    }
LABEL_12:
    GlobalSupportedEncryptionTypes = -4;
    goto LABEL_13;
  }
  v5 = -4;
LABEL_15:
  v6 = v5 & 0x1F;
  GlobalSupportedEncryptionTypes = v6;
  if ( !v6 )
  {
    v6 = 28;
    GlobalSupportedEncryptionTypes = 28;
  }
  v7 = cCSystems;
  v8 = 0;
  *a1 = v6;
  if ( v7 )
  {
    v9 = 133;
    do
    {
      v10 = (unsigned __int64)v8 << 7;
      v11 = *(_DWORD *)((char *)CSystems + v10);
      if ( (unsigned int)(v11 - 23) <= 1 || (unsigned int)(v11 + 135) <= 7 && _bittest(&v9, v11 + 135) )
      {
        v12 = *(_DWORD *)((char *)&CSystems[3] + v10);
        v13 = v12 & 4;
        if ( (v6 & 4) != 0 )
        {
          if ( (v12 & 4) == 0 )
            goto LABEL_37;
          goto LABEL_39;
        }
      }
      else
      {
        switch ( v11 )
        {
          case 3:
            v12 = *(_DWORD *)((char *)&CSystems[3] + v10);
            v13 = v12 & 4;
            v14 = (v6 & 2) == 0;
            break;
          case 1:
            v12 = *(_DWORD *)((char *)&CSystems[3] + v10);
            v13 = v12 & 4;
            v14 = (v6 & 1) == 0;
            break;
          case 18:
            v12 = *(_DWORD *)((char *)&CSystems[3] + v10);
            v13 = v12 & 4;
            v14 = (v6 & 0x10) == 0;
            break;
          case 17:
            v12 = *(_DWORD *)((char *)&CSystems[3] + v10);
            v13 = v12 & 4;
            v14 = (v6 & 8) == 0;
            break;
          default:
            goto LABEL_39;
        }
        if ( !v14 )
        {
          if ( v13 )
            goto LABEL_39;
LABEL_37:
          v15 = v12 | 4;
LABEL_38:
          *(_DWORD *)((char *)&CSystems[3] + v10) = v15;
          goto LABEL_39;
        }
      }
      if ( v13 )
      {
        v15 = v12 & 0xFFFFFFFB;
        goto LABEL_38;
      }
LABEL_39:
      ++v8;
    }
    while ( v8 < v7 );
  }
  return 0;
}

```

## disassembly

```asm
0x1800039e0  push    rbx
0x1800039e2  push    rsi
0x1800039e3  push    rdi
0x1800039e4  sub     rsp, 30h
0x1800039e8  mov     rbx, rcx
0x1800039eb  lea     rax, [rsp+48h+hKey]
0x1800039f0  xor     esi, esi
0x1800039f2  mov     [rsp+48h+phkResult], rax; phkResult
0x1800039f7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800039fe  mov     [rsp+48h+hKey], rsi
0x180003a03  mov     r9d, 20019h; samDesired
0x180003a09  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180003a10  xor     r8d, r8d; ulOptions
0x180003a13  mov     edi, 1
0x180003a18  call    cs:__imp_RegOpenKeyExW
0x180003a1e  cmp     eax, 2
0x180003a21  jnz     short loc_180003A4C
0x180003a23  lea     rax, [rsp+48h+hKey]
0x180003a28  mov     r9d, 20019h; samDesired
0x180003a2e  xor     r8d, r8d; ulOptions
0x180003a31  mov     [rsp+48h+phkResult], rax; phkResult
0x180003a36  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Lsa"...
0x180003a3d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003a44  mov     edi, esi
0x180003a46  call    cs:__imp_RegOpenKeyExW
0x180003a4c  test    eax, eax
0x180003a4e  jnz     loc_180003B58
0x180003a54  mov     rcx, [rsp+48h+hKey]; hKey
0x180003a59  lea     rax, [rsp+48h+cbData]
0x180003a5e  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180003a63  lea     r9, [rsp+48h+Type]; lpType
0x180003a68  lea     rax, [rsp+48h+Data]
0x180003a6d  mov     [rsp+48h+Type], esi
0x180003a71  xor     r8d, r8d; lpReserved
0x180003a74  mov     [rsp+48h+phkResult], rax; lpData
0x180003a79  lea     rdx, ValueName; "SupportedEncryptionTypes"
0x180003a80  mov     [rsp+48h+Data], esi
0x180003a84  mov     [rsp+48h+cbData], 4
0x180003a8c  call    cs:__imp_RegQueryValueExW
0x180003a92  cmp     eax, 2
0x180003a95  jnz     loc_180003B1C
0x180003a9b  test    edi, edi
0x180003a9d  jz      loc_180003B37
0x180003aa3  mov     rcx, [rsp+48h+hKey]; hKey
0x180003aa8  call    cs:__imp_RegCloseKey
0x180003aae  lea     rax, [rsp+48h+hKey]
0x180003ab3  mov     [rsp+48h+hKey], rsi
0x180003ab8  mov     r9d, 20019h; samDesired
0x180003abe  mov     [rsp+48h+phkResult], rax; phkResult
0x180003ac3  xor     r8d, r8d; ulOptions
0x180003ac6  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Lsa"...
0x180003acd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003ad4  call    cs:__imp_RegOpenKeyExW
0x180003ada  test    eax, eax
0x180003adc  jnz     short loc_180003B37
0x180003ade  mov     rcx, [rsp+48h+hKey]; hKey
0x180003ae3  lea     rax, [rsp+48h+cbData]
0x180003ae8  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180003aed  lea     r9, [rsp+48h+Type]; lpType
0x180003af2  lea     rax, [rsp+48h+Data]
0x180003af7  mov     [rsp+48h+Type], esi
0x180003afb  xor     r8d, r8d; lpReserved
0x180003afe  mov     [rsp+48h+phkResult], rax; lpData
0x180003b03  lea     rdx, ValueName; "SupportedEncryptionTypes"
0x180003b0a  mov     [rsp+48h+Data], esi
0x180003b0e  mov     [rsp+48h+cbData], 4
0x180003b16  call    cs:__imp_RegQueryValueExW
0x180003b1c  test    eax, eax
0x180003b1e  jnz     short loc_180003B37
0x180003b20  cmp     [rsp+48h+Type], 4
0x180003b25  jnz     short loc_180003B37
0x180003b27  mov     eax, [rsp+48h+Data]
0x180003b2b  test    eax, eax
0x180003b2d  jz      short loc_180003B37
0x180003b2f  mov     cs:GlobalSupportedEncryptionTypes, eax
0x180003b35  jmp     short loc_180003B44
0x180003b37  mov     r10d, 0FFFFFFFCh
0x180003b3d  mov     cs:GlobalSupportedEncryptionTypes, r10d
0x180003b44  mov     rcx, [rsp+48h+hKey]; hKey
0x180003b49  call    cs:__imp_RegCloseKey
0x180003b4f  mov     r10d, cs:GlobalSupportedEncryptionTypes
0x180003b56  jmp     short loc_180003B5E
0x180003b58  mov     r10d, 0FFFFFFFCh
0x180003b5e  and     r10d, 1Fh
0x180003b62  mov     cs:GlobalSupportedEncryptionTypes, r10d
0x180003b69  jnz     short loc_180003B78
0x180003b6b  mov     r10d, 1Ch
0x180003b71  mov     cs:GlobalSupportedEncryptionTypes, r10d
0x180003b78  mov     r9d, cs:cCSystems
0x180003b7f  mov     edx, esi
0x180003b81  mov     [rbx], r10d
0x180003b84  test    r9d, r9d
0x180003b87  jz      loc_180003C4D
0x180003b8d  lea     r11, CSystems
0x180003b94  mov     ebx, 85h
0x180003b99  nop     dword ptr [rax+00000000h]
0x180003ba0  mov     r8d, edx
0x180003ba3  shl     r8, 7
0x180003ba7  mov     eax, [r8+r11]
0x180003bab  lea     ecx, [rax-17h]
0x180003bae  cmp     ecx, 1
0x180003bb1  jbe     short loc_180003C26
0x180003bb3  lea     ecx, [rax+87h]
0x180003bb9  cmp     ecx, 7
0x180003bbc  ja      short loc_180003BC3
0x180003bbe  bt      ebx, ecx
0x180003bc1  jb      short loc_180003C26
0x180003bc3  cmp     eax, 3
0x180003bc6  jnz     short loc_180003BE7
0x180003bc8  mov     eax, [r8+r11+18h]
0x180003bcd  mov     ecx, eax
0x180003bcf  and     ecx, 4
0x180003bd2  test    r10b, 2
0x180003bd6  jnz     short loc_180003BE1
0x180003bd8  test    ecx, ecx
0x180003bda  jz      short loc_180003C42
0x180003bdc  and     eax, 0FFFFFFFBh
0x180003bdf  jmp     short loc_180003C3D
0x180003be1  test    ecx, ecx
0x180003be3  jz      short loc_180003C3A
0x180003be5  jmp     short loc_180003C42
0x180003be7  cmp     eax, 1
0x180003bea  jnz     short loc_180003BFC
0x180003bec  mov     eax, [r8+r11+18h]
0x180003bf1  mov     ecx, eax
0x180003bf3  and     ecx, 4
0x180003bf6  test    r10b, 1
0x180003bfa  jmp     short loc_180003BD6
0x180003bfc  cmp     eax, 12h
0x180003bff  jnz     short loc_180003C11
0x180003c01  mov     eax, [r8+r11+18h]
0x180003c06  mov     ecx, eax
0x180003c08  and     ecx, 4
0x180003c0b  test    r10b, 10h
0x180003c0f  jmp     short loc_180003BD6
0x180003c11  cmp     eax, 11h
0x180003c14  jnz     short loc_180003C42
0x180003c16  mov     eax, [r8+r11+18h]
0x180003c1b  mov     ecx, eax
0x180003c1d  and     ecx, 4
0x180003c20  test    r10b, 8
0x180003c24  jmp     short loc_180003BD6
0x180003c26  mov     eax, [r8+r11+18h]
0x180003c2b  mov     ecx, eax
0x180003c2d  and     ecx, 4
0x180003c30  test    r10b, 4
0x180003c34  jz      short loc_180003BD8
0x180003c36  test    ecx, ecx
0x180003c38  jnz     short loc_180003C42
0x180003c3a  or      eax, 4
0x180003c3d  mov     [r8+r11+18h], eax
0x180003c42  inc     edx
0x180003c44  cmp     edx, r9d
0x180003c47  jb      loc_180003BA0
0x180003c4d  xor     eax, eax
0x180003c4f  add     rsp, 30h
0x180003c53  pop     rdi
0x180003c54  pop     rsi
0x180003c55  pop     rbx
0x180003c56  retn
```
