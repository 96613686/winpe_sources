# CUtils::EnableChildSessionsCredentialsDelegationPolicy(int)

- ea: `0x1800834ec`
- end: `0x180083932`
- name: `?EnableChildSessionsCredentialsDelegationPolicy@CUtils@@SAJH@Z`
- size: `1094`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180054be4`
- `0x180083938`

## callees

- `0x1800077a0`
- `0x18004e850`
- `0x1800834ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18008356d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800835bc`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800835fa`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18008363c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18008367e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800836c0`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180083702`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180083744`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18008356d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800835bc`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800835fa`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18008363c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18008367e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800836c0`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180083702`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180083744`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180083770`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800837ae`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800837e1`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180083814`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180083847`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18008387a`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800838a9`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800838d8`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180083770`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800837ae`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800837e1`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180083814`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180083847`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18008387a`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800838a9`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800838d8`

## string_xrefs

- `0x180083591`: `RegSetKeyValue failed: 0x%x in %s`
- `0x1800838fa`: `RegDeleteKeyValue failed: 0x%x in %s`

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
0x1800834ec  push    rbx
0x1800834ee  push    rbp
0x1800834ef  push    rsi
0x1800834f0  push    rdi
0x1800834f1  push    r14
0x1800834f3  push    r15
0x1800834f5  sub     rsp, 68h
0x1800834f9  mov     rax, cs:__security_cookie
0x180083500  xor     rax, rsp
0x180083503  mov     [rsp+98h+var_40], rax
0x180083508  movups  xmm0, xmmword ptr cs:aVsDebugLocalho; "vs-debug/localhost"
0x18008350f  xor     ebx, ebx
0x180083511  lea     rsi, aRdChildSession; "RD Child Sessions"
0x180083518  movups  xmm1, xmmword ptr cs:aVsDebugLocalho+10h; "/localhost"
0x18008351f  mov     rbp, 0FFFFFFFF80000002h
0x180083526  test    ecx, ecx
0x180083528  movups  [rsp+98h+Data], xmm0
0x18008352d  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x180083534  mov     r8, rsi; lpValueName
0x180083537  movsd   xmm0, qword ptr cs:aVsDebugLocalho+1Eh; "ost"
0x18008353f  mov     rcx, rbp; hKey
0x180083542  movups  xmmword ptr [rsp+98h+var_58], xmm1
0x180083547  movsd   qword ptr [rsp+98h+var_58+0Eh], xmm0
0x18008354d  jz      loc_180083770
0x180083553  lea     rax, [rsp+98h+Data]
0x180083558  lea     r14d, [rbx+26h]
0x18008355c  lea     r15d, [rbx+1]
0x180083560  mov     [rsp+98h+cbData], r14d; cbData
0x180083565  mov     r9d, r15d; dwType
0x180083568  mov     [rsp+98h+lpData], rax; lpData
0x18008356d  call    cs:__imp_RegSetKeyValueW
0x180083574  nop     dword ptr [rax+rax+00h]
0x180083579  mov     edi, 80070000h
0x18008357e  test    eax, eax
0x180083580  jz      short loc_18008359D
0x180083582  jg      short loc_180083588
0x180083584  mov     ebx, eax
0x180083586  jmp     short loc_18008358D
0x180083588  movzx   ebx, ax
0x18008358b  or      ebx, edi
0x18008358d  test    ebx, ebx
0x18008358f  jns     short loc_18008359D
0x180083591  lea     rdx, aRegsetkeyvalue; "RegSetKeyValue failed: 0x%x in %s"
0x180083598  jmp     loc_180083901
0x18008359d  lea     rax, [rsp+98h+Data]
0x1800835a2  mov     [rsp+98h+cbData], r14d; cbData
0x1800835a7  mov     r9d, r15d; dwType
0x1800835aa  mov     [rsp+98h+lpData], rax; lpData
0x1800835af  mov     r8, rsi; lpValueName
0x1800835b2  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x1800835b9  mov     rcx, rbp; hKey
0x1800835bc  call    cs:__imp_RegSetKeyValueW
0x1800835c3  nop     dword ptr [rax+rax+00h]
0x1800835c8  test    eax, eax
0x1800835ca  jz      short loc_1800835DB
0x1800835cc  jg      short loc_1800835D2
0x1800835ce  mov     ebx, eax
0x1800835d0  jmp     short loc_1800835D7
0x1800835d2  movzx   ebx, ax
0x1800835d5  or      ebx, edi
0x1800835d7  test    ebx, ebx
0x1800835d9  js      short loc_180083591
0x1800835db  lea     rax, [rsp+98h+Data]
0x1800835e0  mov     [rsp+98h+cbData], r14d; cbData
0x1800835e5  mov     r9d, r15d; dwType
0x1800835e8  mov     [rsp+98h+lpData], rax; lpData
0x1800835ed  mov     r8, rsi; lpValueName
0x1800835f0  lea     rdx, aSystemCurrentc_9; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x1800835f7  mov     rcx, rbp; hKey
0x1800835fa  call    cs:__imp_RegSetKeyValueW
0x180083601  nop     dword ptr [rax+rax+00h]
0x180083606  test    eax, eax
0x180083608  jz      short loc_18008361D
0x18008360a  jg      short loc_180083610
0x18008360c  mov     ebx, eax
0x18008360e  jmp     short loc_180083615
0x180083610  movzx   ebx, ax
0x180083613  or      ebx, edi
0x180083615  test    ebx, ebx
0x180083617  js      loc_180083591
0x18008361d  lea     rax, [rsp+98h+Data]
0x180083622  mov     [rsp+98h+cbData], r14d; cbData
0x180083627  mov     r9d, r15d; dwType
0x18008362a  mov     [rsp+98h+lpData], rax; lpData
0x18008362f  mov     r8, rsi; lpValueName
0x180083632  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x180083639  mov     rcx, rbp; hKey
0x18008363c  call    cs:__imp_RegSetKeyValueW
0x180083643  nop     dword ptr [rax+rax+00h]
0x180083648  test    eax, eax
0x18008364a  jz      short loc_18008365F
0x18008364c  jg      short loc_180083652
0x18008364e  mov     ebx, eax
0x180083650  jmp     short loc_180083657
0x180083652  movzx   ebx, ax
0x180083655  or      ebx, edi
0x180083657  test    ebx, ebx
0x180083659  js      loc_180083591
0x18008365f  lea     rax, [rsp+98h+Data]
0x180083664  mov     [rsp+98h+cbData], r14d; cbData
0x180083669  mov     r9d, r15d; dwType
0x18008366c  mov     [rsp+98h+lpData], rax; lpData
0x180083671  mov     r8, rsi; lpValueName
0x180083674  lea     rdx, aSystemCurrentc_18; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x18008367b  mov     rcx, rbp; hKey
0x18008367e  call    cs:__imp_RegSetKeyValueW
0x180083685  nop     dword ptr [rax+rax+00h]
0x18008368a  test    eax, eax
0x18008368c  jz      short loc_1800836A1
0x18008368e  jg      short loc_180083694
0x180083690  mov     ebx, eax
0x180083692  jmp     short loc_180083699
0x180083694  movzx   ebx, ax
0x180083697  or      ebx, edi
0x180083699  test    ebx, ebx
0x18008369b  js      loc_180083591
0x1800836a1  lea     rax, [rsp+98h+Data]
0x1800836a6  mov     [rsp+98h+cbData], r14d; cbData
0x1800836ab  mov     r9d, r15d; dwType
0x1800836ae  mov     [rsp+98h+lpData], rax; lpData
0x1800836b3  mov     r8, rsi; lpValueName
0x1800836b6  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x1800836bd  mov     rcx, rbp; hKey
0x1800836c0  call    cs:__imp_RegSetKeyValueW
0x1800836c7  nop     dword ptr [rax+rax+00h]
0x1800836cc  test    eax, eax
0x1800836ce  jz      short loc_1800836E3
0x1800836d0  jg      short loc_1800836D6
0x1800836d2  mov     ebx, eax
0x1800836d4  jmp     short loc_1800836DB
0x1800836d6  movzx   ebx, ax
0x1800836d9  or      ebx, edi
0x1800836db  test    ebx, ebx
0x1800836dd  js      loc_180083591
0x1800836e3  lea     rax, [rsp+98h+Data]
0x1800836e8  mov     [rsp+98h+cbData], r14d; cbData
0x1800836ed  mov     r9d, r15d; dwType
0x1800836f0  mov     [rsp+98h+lpData], rax; lpData
0x1800836f5  mov     r8, rsi; lpValueName
0x1800836f8  lea     rdx, aSystemCurrentc_10; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x1800836ff  mov     rcx, rbp; hKey
0x180083702  call    cs:__imp_RegSetKeyValueW
0x180083709  nop     dword ptr [rax+rax+00h]
0x18008370e  test    eax, eax
0x180083710  jz      short loc_180083725
0x180083712  jg      short loc_180083718
0x180083714  mov     ebx, eax
0x180083716  jmp     short loc_18008371D
0x180083718  movzx   ebx, ax
0x18008371b  or      ebx, edi
0x18008371d  test    ebx, ebx
0x18008371f  js      loc_180083591
0x180083725  lea     rax, [rsp+98h+Data]
0x18008372a  mov     [rsp+98h+cbData], r14d; cbData
0x18008372f  mov     r9d, r15d; dwType
0x180083732  mov     [rsp+98h+lpData], rax; lpData
0x180083737  mov     r8, rsi; lpValueName
0x18008373a  lea     rdx, aSystemCurrentc_17; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x180083741  mov     rcx, rbp; hKey
0x180083744  call    cs:__imp_RegSetKeyValueW
0x18008374b  nop     dword ptr [rax+rax+00h]
0x180083750  test    eax, eax
0x180083752  jz      loc_180083915
0x180083758  jg      short loc_18008375E
0x18008375a  mov     ebx, eax
0x18008375c  jmp     short loc_180083763
0x18008375e  movzx   ebx, ax
0x180083761  or      ebx, edi
0x180083763  test    ebx, ebx
0x180083765  jns     loc_180083915
0x18008376b  jmp     loc_180083591
0x180083770  call    cs:__imp_RegDeleteKeyValueW
0x180083777  nop     dword ptr [rax+rax+00h]
0x18008377c  mov     r14d, 0FFFFFFFDh
0x180083782  mov     edi, 80070000h
0x180083787  test    r14d, eax
0x18008378a  jz      short loc_1800837A1
0x18008378c  test    eax, eax
0x18008378e  jg      short loc_180083794
0x180083790  mov     ebx, eax
0x180083792  jmp     short loc_180083799
0x180083794  movzx   ebx, ax
0x180083797  or      ebx, edi
0x180083799  test    ebx, ebx
0x18008379b  js      loc_1800838FA
0x1800837a1  mov     r8, rsi; lpValueName
0x1800837a4  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x1800837ab  mov     rcx, rbp; hKey
0x1800837ae  call    cs:__imp_RegDeleteKeyValueW
0x1800837b5  nop     dword ptr [rax+rax+00h]
0x1800837ba  test    r14d, eax
0x1800837bd  jz      short loc_1800837D4
0x1800837bf  test    eax, eax
0x1800837c1  jg      short loc_1800837C7
0x1800837c3  mov     ebx, eax
0x1800837c5  jmp     short loc_1800837CC
0x1800837c7  movzx   ebx, ax
0x1800837ca  or      ebx, edi
0x1800837cc  test    ebx, ebx
0x1800837ce  js      loc_1800838FA
0x1800837d4  mov     r8, rsi; lpValueName
0x1800837d7  lea     rdx, aSystemCurrentc_9; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x1800837de  mov     rcx, rbp; hKey
0x1800837e1  call    cs:__imp_RegDeleteKeyValueW
0x1800837e8  nop     dword ptr [rax+rax+00h]
0x1800837ed  test    r14d, eax
0x1800837f0  jz      short loc_180083807
0x1800837f2  test    eax, eax
0x1800837f4  jg      short loc_1800837FA
0x1800837f6  mov     ebx, eax
0x1800837f8  jmp     short loc_1800837FF
0x1800837fa  movzx   ebx, ax
0x1800837fd  or      ebx, edi
0x1800837ff  test    ebx, ebx
0x180083801  js      loc_1800838FA
0x180083807  mov     r8, rsi; lpValueName
0x18008380a  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x180083811  mov     rcx, rbp; hKey
0x180083814  call    cs:__imp_RegDeleteKeyValueW
0x18008381b  nop     dword ptr [rax+rax+00h]
0x180083820  test    r14d, eax
0x180083823  jz      short loc_18008383A
0x180083825  test    eax, eax
0x180083827  jg      short loc_18008382D
0x180083829  mov     ebx, eax
0x18008382b  jmp     short loc_180083832
0x18008382d  movzx   ebx, ax
0x180083830  or      ebx, edi
0x180083832  test    ebx, ebx
0x180083834  js      loc_1800838FA
0x18008383a  mov     r8, rsi; lpValueName
0x18008383d  lea     rdx, aSystemCurrentc_18; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x180083844  mov     rcx, rbp; hKey
0x180083847  call    cs:__imp_RegDeleteKeyValueW
0x18008384e  nop     dword ptr [rax+rax+00h]
0x180083853  test    r14d, eax
0x180083856  jz      short loc_18008386D
0x180083858  test    eax, eax
0x18008385a  jg      short loc_180083860
0x18008385c  mov     ebx, eax
0x18008385e  jmp     short loc_180083865
0x180083860  movzx   ebx, ax
0x180083863  or      ebx, edi
0x180083865  test    ebx, ebx
0x180083867  js      loc_1800838FA
0x18008386d  mov     r8, rsi; lpValueName
0x180083870  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x180083877  mov     rcx, rbp; hKey
0x18008387a  call    cs:__imp_RegDeleteKeyValueW
0x180083881  nop     dword ptr [rax+rax+00h]
0x180083886  test    r14d, eax
0x180083889  jz      short loc_18008389C
0x18008388b  test    eax, eax
0x18008388d  jg      short loc_180083893
0x18008388f  mov     ebx, eax
0x180083891  jmp     short loc_180083898
0x180083893  movzx   ebx, ax
0x180083896  or      ebx, edi
0x180083898  test    ebx, ebx
0x18008389a  js      short loc_1800838FA
0x18008389c  mov     r8, rsi; lpValueName
0x18008389f  lea     rdx, aSystemCurrentc_10; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x1800838a6  mov     rcx, rbp; hKey
0x1800838a9  call    cs:__imp_RegDeleteKeyValueW
0x1800838b0  nop     dword ptr [rax+rax+00h]
0x1800838b5  test    r14d, eax
0x1800838b8  jz      short loc_1800838CB
0x1800838ba  test    eax, eax
0x1800838bc  jg      short loc_1800838C2
0x1800838be  mov     ebx, eax
0x1800838c0  jmp     short loc_1800838C7
0x1800838c2  movzx   ebx, ax
0x1800838c5  or      ebx, edi
0x1800838c7  test    ebx, ebx
0x1800838c9  js      short loc_1800838FA
0x1800838cb  mov     r8, rsi; lpValueName
0x1800838ce  lea     rdx, aSystemCurrentc_17; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x1800838d5  mov     rcx, rbp; hKey
0x1800838d8  call    cs:__imp_RegDeleteKeyValueW
0x1800838df  nop     dword ptr [rax+rax+00h]
0x1800838e4  test    r14d, eax
0x1800838e7  jz      short loc_180083915
0x1800838e9  test    eax, eax
0x1800838eb  jg      short loc_1800838F1
0x1800838ed  mov     ebx, eax
0x1800838ef  jmp     short loc_1800838F6
0x1800838f1  movzx   ebx, ax
0x1800838f4  or      ebx, edi
0x1800838f6  test    ebx, ebx
0x1800838f8  jns     short loc_180083915
0x1800838fa  lea     rdx, aRegdeletekeyva; "RegDeleteKeyValue failed: 0x%x in %s"
0x180083901  lea     r9, aCutilsEnablech_0; "CUtils::EnableChildSessionsCredentialsD"...
0x180083908  mov     r8d, ebx
0x18008390b  mov     ecx, 8; int
0x180083910  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180083915  mov     eax, ebx
0x180083917  mov     rcx, [rsp+98h+var_40]
0x18008391c  xor     rcx, rsp; StackCookie
0x18008391f  call    __security_check_cookie
0x180083924  add     rsp, 68h
  ... truncated ...
```
