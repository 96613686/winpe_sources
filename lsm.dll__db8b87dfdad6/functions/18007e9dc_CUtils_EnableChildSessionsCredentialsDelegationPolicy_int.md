# CUtils::EnableChildSessionsCredentialsDelegationPolicy(int)

- ea: `0x18007e9dc`
- end: `0x18007edb9`
- name: `?EnableChildSessionsCredentialsDelegationPolicy@CUtils@@SAJH@Z`
- size: `989`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180051464`
- `0x18007edc0`

## callees

- `0x1800074c0`
- `0x18004b460`
- `0x18007e9dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007ea5d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007eaa6`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007eade`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007eb16`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007eb52`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007eb8e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007ebca`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007ec06`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007ea5d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007eaa6`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007eade`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007eb16`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007eb52`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007eb8e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007ebca`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007ec06`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18007ec2c`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18007ec64`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18007ec91`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18007ecbe`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18007eceb`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18007ed14`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18007ed3d`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18007ed66`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18007ec2c`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18007ec64`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18007ec91`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18007ecbe`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18007eceb`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18007ed14`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18007ed3d`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18007ed66`

## string_xrefs

- `0x18007ea7b`: `RegSetKeyValue failed: 0x%x in %s`
- `0x18007ed82`: `RegDeleteKeyValue failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUtils::EnableChildSessionsCredentialsDelegationPolicy(int a1)
{
  signed int v1; // ebx
  LSTATUS v2; // eax
  LSTATUS v3; // eax
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  LSTATUS v17; // eax
  __int128 Data; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v20[22]; // [rsp+40h] [rbp-58h]

  v1 = 0;
  Data = *(_OWORD *)L"vs-debug/localhost";
  *(_OWORD *)v20 = *(_OWORD *)L"/localhost";
  *(_QWORD *)&v20[14] = *(_QWORD *)L"ost";
  if ( a1 )
  {
    v2 = RegSetKeyValueW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\Credssp\\PolicyDefaults\\AllowFreshCredentials",
           L"RD Child Sessions",
           1u,
           &Data,
           0x26u);
    if ( v2 )
    {
      if ( v2 > 0 )
        v1 = (unsigned __int16)v2 | 0x80070000;
      else
        v1 = v2;
    }
    else
    {
      v3 = RegSetKeyValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\Credssp\\PolicyDefaults\\AllowFreshCredentialsDomain",
             L"RD Child Sessions",
             1u,
             &Data,
             0x26u);
      if ( v3 )
      {
        if ( v3 > 0 )
          v1 = (unsigned __int16)v3 | 0x80070000;
        else
          v1 = v3;
      }
      else
      {
        v4 = RegSetKeyValueW(
               HKEY_LOCAL_MACHINE,
               L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\Credssp\\PolicyDefaults\\AllowFreshCredentialsWhenNTLMOnly",
               L"RD Child Sessions",
               1u,
               &Data,
               0x26u);
        if ( v4 )
        {
          if ( v4 > 0 )
            v1 = (unsigned __int16)v4 | 0x80070000;
          else
            v1 = v4;
        }
        else
        {
          v5 = RegSetKeyValueW(
                 HKEY_LOCAL_MACHINE,
                 L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\Credssp\\PolicyDefaults\\AllowFreshCredentialsWhenNTLMOnlyDomain",
                 L"RD Child Sessions",
                 1u,
                 &Data,
                 0x26u);
          if ( v5 )
          {
            if ( v5 > 0 )
              v1 = (unsigned __int16)v5 | 0x80070000;
            else
              v1 = v5;
          }
          else
          {
            v6 = RegSetKeyValueW(
                   HKEY_LOCAL_MACHINE,
                   L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\Credssp\\PolicyDefaults\\AllowDefaultCredentials",
                   L"RD Child Sessions",
                   1u,
                   &Data,
                   0x26u);
            if ( v6 )
            {
              if ( v6 > 0 )
                v1 = (unsigned __int16)v6 | 0x80070000;
              else
                v1 = v6;
            }
            else
            {
              v7 = RegSetKeyValueW(
                     HKEY_LOCAL_MACHINE,
                     L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\Credssp\\PolicyDefaults\\AllowDefaultCredentialsDomain",
                     L"RD Child Sessions",
                     1u,
                     &Data,
                     0x26u);
              if ( v7 )
              {
                if ( v7 > 0 )
                  v1 = (unsigned __int16)v7 | 0x80070000;
                else
                  v1 = v7;
              }
              else
              {
                v8 = RegSetKeyValueW(
                       HKEY_LOCAL_MACHINE,
                       L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\Credssp\\PolicyDefaults\\AllowDefaultCredentialsWhenNTLMOnly",
                       L"RD Child Sessions",
                       1u,
                       &Data,
                       0x26u);
                if ( v8 )
                {
                  if ( v8 > 0 )
                    v1 = (unsigned __int16)v8 | 0x80070000;
                  else
                    v1 = v8;
                }
                else
                {
                  v9 = RegSetKeyValueW(
                         HKEY_LOCAL_MACHINE,
                         L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\Credssp\\PolicyDefaults\\AllowDefaultCredentialsWhenNTLMOnlyDomain",
                         L"RD Child Sessions",
                         1u,
                         &Data,
                         0x26u);
                  if ( !v9 )
                    return (unsigned int)v1;
                  if ( v9 > 0 )
                    v1 = (unsigned __int16)v9 | 0x80070000;
                  else
                    v1 = v9;
                }
              }
            }
          }
        }
      }
    }
    _DbgPrintMessage(
      8,
      "RegSetKeyValue failed: 0x%x in %s",
      (unsigned int)v1,
      "CUtils::EnableChildSessionsCredentialsDelegationPolicy");
  }
  else
  {
    v10 = RegDeleteKeyValueW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\Credssp\\PolicyDefaults\\AllowFreshCredentials",
            L"RD Child Sessions");
    if ( (v10 & 0xFFFFFFFD) != 0 )
    {
      v1 = v10 > 0 ? (unsigned __int16)v10 | 0x80070000 : v10;
      if ( v1 < 0 )
        goto LABEL_75;
    }
    v11 = RegDeleteKeyValueW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\Credssp\\PolicyDefaults\\AllowFreshCredentialsDomain",
            L"RD Child Sessions");
    if ( (v11 & 0xFFFFFFFD) != 0 )
    {
      v1 = v11 > 0 ? (unsigned __int16)v11 | 0x80070000 : v11;
      if ( v1 < 0 )
        goto LABEL_75;
    }
    v12 = RegDeleteKeyValueW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\Credssp\\PolicyDefaults\\AllowFreshCredentialsWhenNTLMOnly",
            L"RD Child Sessions");
    if ( (v12 & 0xFFFFFFFD) != 0 )
    {
      v1 = v12 > 0 ? (unsigned __int16)v12 | 0x80070000 : v12;
      if ( v1 < 0 )
        goto LABEL_75;
    }
    v13 = RegDeleteKeyValueW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\Credssp\\PolicyDefaults\\AllowFreshCredentialsWhenNTLMOnlyDomain",
            L"RD Child Sessions");
    if ( (v13 & 0xFFFFFFFD) != 0 )
    {
      v1 = v13 > 0 ? (unsigned __int16)v13 | 0x80070000 : v13;
      if ( v1 < 0 )
        goto LABEL_75;
    }
    v14 = RegDeleteKeyValueW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\Credssp\\PolicyDefaults\\AllowDefaultCredentials",
            L"RD Child Sessions");
    if ( (v14 & 0xFFFFFFFD) != 0 )
    {
      v1 = v14 > 0 ? (unsigned __int16)v14 | 0x80070000 : v14;
      if ( v1 < 0 )
        goto LABEL_75;
    }
    if ( (v15 = RegDeleteKeyValueW(
                  HKEY_LOCAL_MACHINE,
                  L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\Credssp\\PolicyDefaults\\AllowDefaultCredentialsDomain",
                  L"RD Child Sessions"),
          (v15 & 0xFFFFFFFD) != 0)
      && (v15 > 0 ? (v1 = (unsigned __int16)v15 | 0x80070000) : (v1 = v15), v1 < 0)
      || (v16 = RegDeleteKeyValueW(
                  HKEY_LOCAL_MACHINE,
                  L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\Credssp\\PolicyDefaults\\AllowDefaultCredentialsWhenNTLMOnly",
                  L"RD Child Sessions"),
          (v16 & 0xFFFFFFFD) != 0)
      && (v16 > 0 ? (v1 = (unsigned __int16)v16 | 0x80070000) : (v1 = v16), v1 < 0)
      || (v17 = RegDeleteKeyValueW(
                  HKEY_LOCAL_MACHINE,
                  L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\Credssp\\PolicyDefaults\\AllowDefaultCredentialsWhenNTLMOnlyDomain",
                  L"RD Child Sessions"),
          (v17 & 0xFFFFFFFD) != 0)
      && (v17 > 0 ? (v1 = (unsigned __int16)v17 | 0x80070000) : (v1 = v17), v1 < 0) )
    {
LABEL_75:
      _DbgPrintMessage(
        8,
        "RegDeleteKeyValue failed: 0x%x in %s",
        (unsigned int)v1,
        "CUtils::EnableChildSessionsCredentialsDelegationPolicy");
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18007e9dc  push    rbx
0x18007e9de  push    rbp
0x18007e9df  push    rsi
0x18007e9e0  push    rdi
0x18007e9e1  push    r14
0x18007e9e3  push    r15
0x18007e9e5  sub     rsp, 68h
0x18007e9e9  mov     rax, cs:__security_cookie
0x18007e9f0  xor     rax, rsp
0x18007e9f3  mov     [rsp+98h+var_40], rax
0x18007e9f8  movups  xmm0, xmmword ptr cs:aVsDebugLocalho; "vs-debug/localhost"
0x18007e9ff  xor     ebx, ebx
0x18007ea01  lea     rsi, aRdChildSession; "RD Child Sessions"
0x18007ea08  movups  xmm1, xmmword ptr cs:aVsDebugLocalho+10h; "/localhost"
0x18007ea0f  mov     rbp, 0FFFFFFFF80000002h
0x18007ea16  test    ecx, ecx
0x18007ea18  movups  [rsp+98h+Data], xmm0
0x18007ea1d  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x18007ea24  mov     r8, rsi; lpValueName
0x18007ea27  movsd   xmm0, qword ptr cs:aVsDebugLocalho+1Eh; "ost"
0x18007ea2f  mov     rcx, rbp; hKey
0x18007ea32  movups  xmmword ptr [rsp+98h+var_58], xmm1
0x18007ea37  movsd   qword ptr [rsp+98h+var_58+0Eh], xmm0
0x18007ea3d  jz      loc_18007EC2C
0x18007ea43  lea     rax, [rsp+98h+Data]
0x18007ea48  lea     r14d, [rbx+26h]
0x18007ea4c  lea     r15d, [rbx+1]
0x18007ea50  mov     [rsp+98h+cbData], r14d; cbData
0x18007ea55  mov     r9d, r15d; dwType
0x18007ea58  mov     [rsp+98h+lpData], rax; lpData
0x18007ea5d  call    cs:__imp_RegSetKeyValueW
0x18007ea63  mov     edi, 80070000h
0x18007ea68  test    eax, eax
0x18007ea6a  jz      short loc_18007EA87
0x18007ea6c  jg      short loc_18007EA72
0x18007ea6e  mov     ebx, eax
0x18007ea70  jmp     short loc_18007EA77
0x18007ea72  movzx   ebx, ax
0x18007ea75  or      ebx, edi
0x18007ea77  test    ebx, ebx
0x18007ea79  jns     short loc_18007EA87
0x18007ea7b  lea     rdx, aRegsetkeyvalue; "RegSetKeyValue failed: 0x%x in %s"
0x18007ea82  jmp     loc_18007ED89
0x18007ea87  lea     rax, [rsp+98h+Data]
0x18007ea8c  mov     [rsp+98h+cbData], r14d; cbData
0x18007ea91  mov     r9d, r15d; dwType
0x18007ea94  mov     [rsp+98h+lpData], rax; lpData
0x18007ea99  mov     r8, rsi; lpValueName
0x18007ea9c  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x18007eaa3  mov     rcx, rbp; hKey
0x18007eaa6  call    cs:__imp_RegSetKeyValueW
0x18007eaac  test    eax, eax
0x18007eaae  jz      short loc_18007EABF
0x18007eab0  jg      short loc_18007EAB6
0x18007eab2  mov     ebx, eax
0x18007eab4  jmp     short loc_18007EABB
0x18007eab6  movzx   ebx, ax
0x18007eab9  or      ebx, edi
0x18007eabb  test    ebx, ebx
0x18007eabd  js      short loc_18007EA7B
0x18007eabf  lea     rax, [rsp+98h+Data]
0x18007eac4  mov     [rsp+98h+cbData], r14d; cbData
0x18007eac9  mov     r9d, r15d; dwType
0x18007eacc  mov     [rsp+98h+lpData], rax; lpData
0x18007ead1  mov     r8, rsi; lpValueName
0x18007ead4  lea     rdx, aSystemCurrentc_9; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x18007eadb  mov     rcx, rbp; hKey
0x18007eade  call    cs:__imp_RegSetKeyValueW
0x18007eae4  test    eax, eax
0x18007eae6  jz      short loc_18007EAF7
0x18007eae8  jg      short loc_18007EAEE
0x18007eaea  mov     ebx, eax
0x18007eaec  jmp     short loc_18007EAF3
0x18007eaee  movzx   ebx, ax
0x18007eaf1  or      ebx, edi
0x18007eaf3  test    ebx, ebx
0x18007eaf5  js      short loc_18007EA7B
0x18007eaf7  lea     rax, [rsp+98h+Data]
0x18007eafc  mov     [rsp+98h+cbData], r14d; cbData
0x18007eb01  mov     r9d, r15d; dwType
0x18007eb04  mov     [rsp+98h+lpData], rax; lpData
0x18007eb09  mov     r8, rsi; lpValueName
0x18007eb0c  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x18007eb13  mov     rcx, rbp; hKey
0x18007eb16  call    cs:__imp_RegSetKeyValueW
0x18007eb1c  test    eax, eax
0x18007eb1e  jz      short loc_18007EB33
0x18007eb20  jg      short loc_18007EB26
0x18007eb22  mov     ebx, eax
0x18007eb24  jmp     short loc_18007EB2B
0x18007eb26  movzx   ebx, ax
0x18007eb29  or      ebx, edi
0x18007eb2b  test    ebx, ebx
0x18007eb2d  js      loc_18007EA7B
0x18007eb33  lea     rax, [rsp+98h+Data]
0x18007eb38  mov     [rsp+98h+cbData], r14d; cbData
0x18007eb3d  mov     r9d, r15d; dwType
0x18007eb40  mov     [rsp+98h+lpData], rax; lpData
0x18007eb45  mov     r8, rsi; lpValueName
0x18007eb48  lea     rdx, aSystemCurrentc_18; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x18007eb4f  mov     rcx, rbp; hKey
0x18007eb52  call    cs:__imp_RegSetKeyValueW
0x18007eb58  test    eax, eax
0x18007eb5a  jz      short loc_18007EB6F
0x18007eb5c  jg      short loc_18007EB62
0x18007eb5e  mov     ebx, eax
0x18007eb60  jmp     short loc_18007EB67
0x18007eb62  movzx   ebx, ax
0x18007eb65  or      ebx, edi
0x18007eb67  test    ebx, ebx
0x18007eb69  js      loc_18007EA7B
0x18007eb6f  lea     rax, [rsp+98h+Data]
0x18007eb74  mov     [rsp+98h+cbData], r14d; cbData
0x18007eb79  mov     r9d, r15d; dwType
0x18007eb7c  mov     [rsp+98h+lpData], rax; lpData
0x18007eb81  mov     r8, rsi; lpValueName
0x18007eb84  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x18007eb8b  mov     rcx, rbp; hKey
0x18007eb8e  call    cs:__imp_RegSetKeyValueW
0x18007eb94  test    eax, eax
0x18007eb96  jz      short loc_18007EBAB
0x18007eb98  jg      short loc_18007EB9E
0x18007eb9a  mov     ebx, eax
0x18007eb9c  jmp     short loc_18007EBA3
0x18007eb9e  movzx   ebx, ax
0x18007eba1  or      ebx, edi
0x18007eba3  test    ebx, ebx
0x18007eba5  js      loc_18007EA7B
0x18007ebab  lea     rax, [rsp+98h+Data]
0x18007ebb0  mov     [rsp+98h+cbData], r14d; cbData
0x18007ebb5  mov     r9d, r15d; dwType
0x18007ebb8  mov     [rsp+98h+lpData], rax; lpData
0x18007ebbd  mov     r8, rsi; lpValueName
0x18007ebc0  lea     rdx, aSystemCurrentc_10; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x18007ebc7  mov     rcx, rbp; hKey
0x18007ebca  call    cs:__imp_RegSetKeyValueW
0x18007ebd0  test    eax, eax
0x18007ebd2  jz      short loc_18007EBE7
0x18007ebd4  jg      short loc_18007EBDA
0x18007ebd6  mov     ebx, eax
0x18007ebd8  jmp     short loc_18007EBDF
0x18007ebda  movzx   ebx, ax
0x18007ebdd  or      ebx, edi
0x18007ebdf  test    ebx, ebx
0x18007ebe1  js      loc_18007EA7B
0x18007ebe7  lea     rax, [rsp+98h+Data]
0x18007ebec  mov     [rsp+98h+cbData], r14d; cbData
0x18007ebf1  mov     r9d, r15d; dwType
0x18007ebf4  mov     [rsp+98h+lpData], rax; lpData
0x18007ebf9  mov     r8, rsi; lpValueName
0x18007ebfc  lea     rdx, aSystemCurrentc_17; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x18007ec03  mov     rcx, rbp; hKey
0x18007ec06  call    cs:__imp_RegSetKeyValueW
0x18007ec0c  test    eax, eax
0x18007ec0e  jz      loc_18007ED9D
0x18007ec14  jg      short loc_18007EC1A
0x18007ec16  mov     ebx, eax
0x18007ec18  jmp     short loc_18007EC1F
0x18007ec1a  movzx   ebx, ax
0x18007ec1d  or      ebx, edi
0x18007ec1f  test    ebx, ebx
0x18007ec21  jns     loc_18007ED9D
0x18007ec27  jmp     loc_18007EA7B
0x18007ec2c  call    cs:__imp_RegDeleteKeyValueW
0x18007ec32  mov     r14d, 0FFFFFFFDh
0x18007ec38  mov     edi, 80070000h
0x18007ec3d  test    r14d, eax
0x18007ec40  jz      short loc_18007EC57
0x18007ec42  test    eax, eax
0x18007ec44  jg      short loc_18007EC4A
0x18007ec46  mov     ebx, eax
0x18007ec48  jmp     short loc_18007EC4F
0x18007ec4a  movzx   ebx, ax
0x18007ec4d  or      ebx, edi
0x18007ec4f  test    ebx, ebx
0x18007ec51  js      loc_18007ED82
0x18007ec57  mov     r8, rsi; lpValueName
0x18007ec5a  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x18007ec61  mov     rcx, rbp; hKey
0x18007ec64  call    cs:__imp_RegDeleteKeyValueW
0x18007ec6a  test    r14d, eax
0x18007ec6d  jz      short loc_18007EC84
0x18007ec6f  test    eax, eax
0x18007ec71  jg      short loc_18007EC77
0x18007ec73  mov     ebx, eax
0x18007ec75  jmp     short loc_18007EC7C
0x18007ec77  movzx   ebx, ax
0x18007ec7a  or      ebx, edi
0x18007ec7c  test    ebx, ebx
0x18007ec7e  js      loc_18007ED82
0x18007ec84  mov     r8, rsi; lpValueName
0x18007ec87  lea     rdx, aSystemCurrentc_9; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x18007ec8e  mov     rcx, rbp; hKey
0x18007ec91  call    cs:__imp_RegDeleteKeyValueW
0x18007ec97  test    r14d, eax
0x18007ec9a  jz      short loc_18007ECB1
0x18007ec9c  test    eax, eax
0x18007ec9e  jg      short loc_18007ECA4
0x18007eca0  mov     ebx, eax
0x18007eca2  jmp     short loc_18007ECA9
0x18007eca4  movzx   ebx, ax
0x18007eca7  or      ebx, edi
0x18007eca9  test    ebx, ebx
0x18007ecab  js      loc_18007ED82
0x18007ecb1  mov     r8, rsi; lpValueName
0x18007ecb4  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x18007ecbb  mov     rcx, rbp; hKey
0x18007ecbe  call    cs:__imp_RegDeleteKeyValueW
0x18007ecc4  test    r14d, eax
0x18007ecc7  jz      short loc_18007ECDE
0x18007ecc9  test    eax, eax
0x18007eccb  jg      short loc_18007ECD1
0x18007eccd  mov     ebx, eax
0x18007eccf  jmp     short loc_18007ECD6
0x18007ecd1  movzx   ebx, ax
0x18007ecd4  or      ebx, edi
0x18007ecd6  test    ebx, ebx
0x18007ecd8  js      loc_18007ED82
0x18007ecde  mov     r8, rsi; lpValueName
0x18007ece1  lea     rdx, aSystemCurrentc_18; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x18007ece8  mov     rcx, rbp; hKey
0x18007eceb  call    cs:__imp_RegDeleteKeyValueW
0x18007ecf1  test    r14d, eax
0x18007ecf4  jz      short loc_18007ED07
0x18007ecf6  test    eax, eax
0x18007ecf8  jg      short loc_18007ECFE
0x18007ecfa  mov     ebx, eax
0x18007ecfc  jmp     short loc_18007ED03
0x18007ecfe  movzx   ebx, ax
0x18007ed01  or      ebx, edi
0x18007ed03  test    ebx, ebx
0x18007ed05  js      short loc_18007ED82
0x18007ed07  mov     r8, rsi; lpValueName
0x18007ed0a  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x18007ed11  mov     rcx, rbp; hKey
0x18007ed14  call    cs:__imp_RegDeleteKeyValueW
0x18007ed1a  test    r14d, eax
0x18007ed1d  jz      short loc_18007ED30
0x18007ed1f  test    eax, eax
0x18007ed21  jg      short loc_18007ED27
0x18007ed23  mov     ebx, eax
0x18007ed25  jmp     short loc_18007ED2C
0x18007ed27  movzx   ebx, ax
0x18007ed2a  or      ebx, edi
0x18007ed2c  test    ebx, ebx
0x18007ed2e  js      short loc_18007ED82
0x18007ed30  mov     r8, rsi; lpValueName
0x18007ed33  lea     rdx, aSystemCurrentc_10; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x18007ed3a  mov     rcx, rbp; hKey
0x18007ed3d  call    cs:__imp_RegDeleteKeyValueW
0x18007ed43  test    r14d, eax
0x18007ed46  jz      short loc_18007ED59
0x18007ed48  test    eax, eax
0x18007ed4a  jg      short loc_18007ED50
0x18007ed4c  mov     ebx, eax
0x18007ed4e  jmp     short loc_18007ED55
0x18007ed50  movzx   ebx, ax
0x18007ed53  or      ebx, edi
0x18007ed55  test    ebx, ebx
0x18007ed57  js      short loc_18007ED82
0x18007ed59  mov     r8, rsi; lpValueName
0x18007ed5c  lea     rdx, aSystemCurrentc_17; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x18007ed63  mov     rcx, rbp; hKey
0x18007ed66  call    cs:__imp_RegDeleteKeyValueW
0x18007ed6c  test    r14d, eax
0x18007ed6f  jz      short loc_18007ED9D
0x18007ed71  test    eax, eax
0x18007ed73  jg      short loc_18007ED79
0x18007ed75  mov     ebx, eax
0x18007ed77  jmp     short loc_18007ED7E
0x18007ed79  movzx   ebx, ax
0x18007ed7c  or      ebx, edi
0x18007ed7e  test    ebx, ebx
0x18007ed80  jns     short loc_18007ED9D
0x18007ed82  lea     rdx, aRegdeletekeyva; "RegDeleteKeyValue failed: 0x%x in %s"
0x18007ed89  lea     r9, aCutilsEnablech_0; "CUtils::EnableChildSessionsCredentialsD"...
0x18007ed90  mov     r8d, ebx
0x18007ed93  mov     ecx, 8; int
0x18007ed98  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007ed9d  mov     eax, ebx
0x18007ed9f  mov     rcx, [rsp+98h+var_40]
0x18007eda4  xor     rcx, rsp; StackCookie
0x18007eda7  call    __security_check_cookie
0x18007edac  add     rsp, 68h
0x18007edb0  pop     r15
0x18007edb2  pop     r14
0x18007edb4  pop     rdi
0x18007edb5  pop     rsi
0x18007edb6  pop     rbp
0x18007edb7  pop     rbx
0x18007edb8  retn
```
