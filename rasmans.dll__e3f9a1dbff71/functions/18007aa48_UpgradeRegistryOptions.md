# UpgradeRegistryOptions

- ea: `0x18007aa48`
- end: `0x18007ae4b`
- name: `UpgradeRegistryOptions`
- size: `1027`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180072d4c`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x180005f1c`
- `0x18002ee78`
- `0x18007aa48`
- `0x18007ae54`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007ad40`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007ad40`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007acd6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007acd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007adab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007adf0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007adab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007adf0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18007ad92`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18007ad92`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18007abf2`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18007abf2`

## string_xrefs

- `0x18007acb3`: `System\CurrentControlSet\Services\Rasman\PPP`

## pseudocode

```c
__int64 __fastcall UpgradeRegistryOptions(__int64 a1, __int64 a2)
{
  struct _LIST_ENTRY *v4; // rcx
  unsigned int v5; // ebx
  const wchar_t *v6; // r8
  HRESULT v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r9
  unsigned int v10; // eax
  HKEY v11; // rdi
  unsigned int v12; // eax
  unsigned int v13; // edi
  __int64 v14; // rdx
  BYTE Data[8]; // [rsp+30h] [rbp-50h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-48h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-40h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-38h] BYREF
  DWORD Type; // [rsp+4Ch] [rbp-34h] BYREF
  wchar_t pszDest[8]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v22; // [rsp+60h] [rbp-20h]
  int v23; // [rsp+70h] [rbp-10h]

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 873, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v23 = 0;
  phkResult = 0;
  *(_OWORD *)pszDest = 0;
  v22 = 0;
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v4[1].Blink) & 0x80) != 0 && BYTE1(v4[1].Blink) >= 6u )
  {
    WPP_SF_q(v4[1].Flink, 858, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, a1);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = 0;
  if ( !a1 || *(_DWORD *)(a1 + 8) || (v6 = (const wchar_t *)(a1 + 16), a1 == -16) || !*v6 )
  {
    pszDest[0] = 0;
    goto LABEL_20;
  }
  *(_DWORD *)pszDest = 6029404;
  v7 = StringCchCopyExW(&pszDest[2], 0x10u, v6, 0, 0, 0x100u);
  if ( v7 >= 0 )
    goto LABEL_18;
  v5 = (unsigned __int16)v7;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    goto LABEL_24;
  if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 862, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, (unsigned __int16)v7);
LABEL_18:
    v4 = WPP_GLOBAL_Control;
  }
LABEL_20:
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v4[1].Blink) & 0x80) != 0 && BYTE1(v4[1].Blink) >= 6u )
  {
    WPP_SF_d(v4[1].Flink, 863, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v5);
    v4 = WPP_GLOBAL_Control;
  }
LABEL_24:
  if ( v5 )
  {
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v4[1].Blink) & 0x80) != 0 && BYTE1(v4[1].Blink) >= 2u )
    {
      v8 = 874;
LABEL_29:
      v9 = v5;
LABEL_68:
      WPP_SF_d(v4[1].Flink, v8, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v9);
      v4 = WPP_GLOBAL_Control;
    }
LABEL_69:
    if ( phkResult )
    {
      RegCloseKey(phkResult);
      v4 = WPP_GLOBAL_Control;
    }
    goto LABEL_71;
  }
  v10 = RegConnectRegistryW(
          (LPCWSTR)((unsigned __int64)pszDest & -(__int64)(pszDest[0] != 0)),
          HKEY_LOCAL_MACHINE,
          &phkResult);
  v5 = v10;
  if ( v10 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v8 = 875;
      v9 = v10;
      goto LABEL_68;
    }
    goto LABEL_69;
  }
  v11 = phkResult;
  if ( phkResult )
  {
    if ( *(_DWORD *)(a2 + 24) == 2 )
    {
      UpgradeSecureVpnOption(phkResult);
      v11 = phkResult;
    }
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 869, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
    }
    hKey = 0;
    Type = 4;
    cbData = 4;
    *(_DWORD *)Data = 0;
    v12 = RegOpenKeyExW(v11, L"System\\CurrentControlSet\\Services\\Rasman\\PPP", 0, 0x20019u, &hKey);
    v13 = v12;
    if ( v12 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_62;
      }
      v14 = 870;
    }
    else
    {
      v12 = RegQueryValueExW(hKey, L"ForceStrongEncryption", 0, &Type, Data, &cbData);
      v13 = v12;
      if ( !v12 )
      {
        if ( *(_DWORD *)Data && *(_DWORD *)(a2 + 172) == 256 )
          *(_DWORD *)(a2 + 172) = 512;
        RegDeleteValueW(hKey, L"ForceStrongEncryption");
        goto LABEL_61;
      }
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_62;
      }
      v14 = 871;
    }
    WPP_SF_d(v4[1].Flink, v14, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v12);
LABEL_61:
    v4 = WPP_GLOBAL_Control;
LABEL_62:
    if ( hKey )
    {
      RegCloseKey(hKey);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v4[1].Blink) & 0x80) == 0 || BYTE1(v4[1].Blink) < 6u )
      goto LABEL_69;
    v8 = 872;
    v9 = v13;
    goto LABEL_68;
  }
  v5 = 1003;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v5;
  if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    v8 = 876;
    goto LABEL_29;
  }
LABEL_71:
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v4[1].Blink) & 0x80) != 0 && BYTE1(v4[1].Blink) >= 6u )
    WPP_SF_d(v4[1].Flink, 877, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18007aa48  mov     [rsp-38h+arg_10], rbx
0x18007aa4d  push    rbp
0x18007aa4e  push    rsi
0x18007aa4f  push    rdi
0x18007aa50  push    r12
0x18007aa52  push    r13
0x18007aa54  push    r14
0x18007aa56  push    r15
0x18007aa58  mov     rbp, rsp
0x18007aa5b  sub     rsp, 80h
0x18007aa62  mov     rax, cs:__security_cookie
0x18007aa69  xor     rax, rsp
0x18007aa6c  mov     [rbp+var_8], rax
0x18007aa70  mov     rsi, rdx
0x18007aa73  mov     rdi, rcx
0x18007aa76  mov     rcx, cs:WPP_GLOBAL_Control
0x18007aa7d  lea     r12, WPP_GLOBAL_Control
0x18007aa84  lea     r13, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007aa8b  mov     r15b, 80h
0x18007aa8e  cmp     rcx, r12
0x18007aa91  jz      short loc_18007AAB7
0x18007aa93  test    [rcx+1Ch], r15b
0x18007aa97  jz      short loc_18007AAB7
0x18007aa99  cmp     byte ptr [rcx+19h], 6
0x18007aa9d  jb      short loc_18007AAB7
0x18007aa9f  mov     rcx, [rcx+10h]
0x18007aaa3  mov     edx, 369h
0x18007aaa8  mov     r8, r13
0x18007aaab  call    WPP_SF_
0x18007aab0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007aab7  xor     eax, eax
0x18007aab9  xorps   xmm0, xmm0
0x18007aabc  xor     r14d, r14d
0x18007aabf  mov     [rbp+var_10], eax
0x18007aac2  mov     [rbp+phkResult], r14
0x18007aac6  movups  xmmword ptr [rbp+pszDest], xmm0
0x18007aaca  movups  [rbp+var_20], xmm0
0x18007aace  cmp     rcx, r12
0x18007aad1  jz      short loc_18007AAFA
0x18007aad3  test    [rcx+1Ch], r15b
0x18007aad7  jz      short loc_18007AAFA
0x18007aad9  cmp     byte ptr [rcx+19h], 6
0x18007aadd  jb      short loc_18007AAFA
0x18007aadf  mov     rcx, [rcx+10h]
0x18007aae3  mov     edx, 35Ah
0x18007aae8  mov     r9, rdi
0x18007aaeb  mov     r8, r13
0x18007aaee  call    WPP_SF_q
0x18007aaf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18007aafa  mov     ebx, r14d
0x18007aafd  test    rdi, rdi
0x18007ab00  jz      short loc_18007AB77
0x18007ab02  cmp     [rdi+8], r14d
0x18007ab06  jnz     short loc_18007AB77
0x18007ab08  lea     r8, [rdi+10h]; pszSrc
0x18007ab0c  test    r8, r8
0x18007ab0f  jz      short loc_18007AB77
0x18007ab11  cmp     [r8], r14w
0x18007ab15  jz      short loc_18007AB77
0x18007ab17  xor     r9d, r9d; ppszDestEnd
0x18007ab1a  mov     [rsp+80h+dwFlags], 100h; dwFlags
0x18007ab22  lea     rcx, [rbp+pszDest+4]; pszDest
0x18007ab26  mov     dword ptr [rbp+pszDest], 5C005Ch
0x18007ab2d  mov     [rsp+80h+pcchRemaining], r14; pcchRemaining
0x18007ab32  lea     edx, [r9+10h]; cchDest
0x18007ab36  call    StringCchCopyExW
0x18007ab3b  test    eax, eax
0x18007ab3d  jns     short loc_18007AB6E
0x18007ab3f  movzx   ebx, ax
0x18007ab42  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ab49  cmp     rcx, r12
0x18007ab4c  jz      short loc_18007ABA8
0x18007ab4e  test    [rcx+1Ch], r15b
0x18007ab52  jz      short loc_18007AB7C
0x18007ab54  cmp     byte ptr [rcx+19h], 2
0x18007ab58  jb      short loc_18007AB7C
0x18007ab5a  mov     rcx, [rcx+10h]
0x18007ab5e  mov     edx, 35Eh
0x18007ab63  mov     r9d, ebx
0x18007ab66  mov     r8, r13
0x18007ab69  call    WPP_SF_d
0x18007ab6e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ab75  jmp     short loc_18007AB7C
0x18007ab77  mov     [rbp+pszDest], r14w
0x18007ab7c  cmp     rcx, r12
0x18007ab7f  jz      short loc_18007ABA8
0x18007ab81  test    [rcx+1Ch], r15b
0x18007ab85  jz      short loc_18007ABA8
0x18007ab87  cmp     byte ptr [rcx+19h], 6
0x18007ab8b  jb      short loc_18007ABA8
0x18007ab8d  mov     rcx, [rcx+10h]
0x18007ab91  mov     edx, 35Fh
0x18007ab96  mov     r9d, ebx
0x18007ab99  mov     r8, r13
0x18007ab9c  call    WPP_SF_d
0x18007aba1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007aba8  test    ebx, ebx
0x18007abaa  jz      short loc_18007ABD6
0x18007abac  cmp     rcx, r12
0x18007abaf  jz      loc_18007ADE4
0x18007abb5  test    [rcx+1Ch], r15b
0x18007abb9  jz      loc_18007ADE4
0x18007abbf  cmp     byte ptr [rcx+19h], 2
0x18007abc3  jb      loc_18007ADE4
0x18007abc9  mov     edx, 36Ah
0x18007abce  mov     r9d, ebx
0x18007abd1  jmp     loc_18007ADD1
0x18007abd6  movzx   eax, [rbp+pszDest]
0x18007abda  lea     r8, [rbp+phkResult]; phkResult
0x18007abde  neg     ax
0x18007abe1  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18007abe8  lea     rax, [rbp+pszDest]
0x18007abec  sbb     rcx, rcx
0x18007abef  and     rcx, rax; lpMachineName
0x18007abf2  call    cs:__imp_RegConnectRegistryW
0x18007abf8  mov     ebx, eax
0x18007abfa  test    eax, eax
0x18007abfc  jz      short loc_18007AC2F
0x18007abfe  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ac05  cmp     rcx, r12
0x18007ac08  jz      loc_18007ADE4
0x18007ac0e  test    [rcx+1Ch], r15b
0x18007ac12  jz      loc_18007ADE4
0x18007ac18  cmp     byte ptr [rcx+19h], 2
0x18007ac1c  jb      loc_18007ADE4
0x18007ac22  mov     edx, 36Bh
0x18007ac27  mov     r9d, eax
0x18007ac2a  jmp     loc_18007ADD1
0x18007ac2f  mov     rdi, [rbp+phkResult]
0x18007ac33  test    rdi, rdi
0x18007ac36  jnz     short loc_18007AC69
0x18007ac38  mov     ebx, 3EBh
0x18007ac3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ac44  cmp     rcx, r12
0x18007ac47  jz      loc_18007AE22
0x18007ac4d  test    [rcx+1Ch], r15b
0x18007ac51  jz      loc_18007ADFD
0x18007ac57  cmp     byte ptr [rcx+19h], 2
0x18007ac5b  jb      loc_18007ADFD
0x18007ac61  lea     edx, [rbx-7Fh]
0x18007ac64  jmp     loc_18007ABCE
0x18007ac69  cmp     dword ptr [rsi+18h], 2
0x18007ac6d  jnz     short loc_18007AC7E
0x18007ac6f  mov     rdx, rsi
0x18007ac72  mov     rcx, rdi; hKey
0x18007ac75  call    UpgradeSecureVpnOption
0x18007ac7a  mov     rdi, [rbp+phkResult]
0x18007ac7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ac85  cmp     rcx, r12
0x18007ac88  jz      short loc_18007ACA7
0x18007ac8a  test    [rcx+1Ch], r15b
0x18007ac8e  jz      short loc_18007ACA7
0x18007ac90  cmp     byte ptr [rcx+19h], 6
0x18007ac94  jb      short loc_18007ACA7
0x18007ac96  mov     rcx, [rcx+10h]
0x18007ac9a  mov     edx, 365h
0x18007ac9f  mov     r8, r13
0x18007aca2  call    WPP_SF_
0x18007aca7  mov     eax, 4
0x18007acac  mov     [rbp+hKey], r14
0x18007acb0  mov     [rbp+Type], eax
0x18007acb3  lea     rdx, c_pszRegKeySecureVpn; "System\\CurrentControlSet\\Services\\Ra"...
0x18007acba  mov     [rbp+cbData], eax
0x18007acbd  mov     r9d, 20019h; samDesired
0x18007acc3  lea     rax, [rbp+hKey]
0x18007acc7  mov     dword ptr [rbp+Data], r14d
0x18007accb  xor     r8d, r8d; ulOptions
0x18007acce  mov     [rsp+80h+pcchRemaining], rax; phkResult
0x18007acd3  mov     rcx, rdi; hKey
0x18007acd6  call    cs:__imp_RegOpenKeyExW
0x18007acdc  mov     edi, eax
0x18007acde  test    eax, eax
0x18007ace0  jz      short loc_18007AD1C
0x18007ace2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ace9  cmp     rcx, r12
0x18007acec  jz      loc_18007AD9F
0x18007acf2  test    [rcx+1Ch], r15b
0x18007acf6  jz      loc_18007AD9F
0x18007acfc  cmp     byte ptr [rcx+19h], 2
0x18007ad00  jb      loc_18007AD9F
0x18007ad06  mov     edx, 366h
0x18007ad0b  mov     rcx, [rcx+10h]
0x18007ad0f  mov     r9d, eax
0x18007ad12  mov     r8, r13
0x18007ad15  call    WPP_SF_d
0x18007ad1a  jmp     short loc_18007AD98
0x18007ad1c  mov     rcx, [rbp+hKey]; hKey
0x18007ad20  lea     rax, [rbp+cbData]
0x18007ad24  mov     qword ptr [rsp+80h+dwFlags], rax; lpcbData
0x18007ad29  lea     r9, [rbp+Type]; lpType
0x18007ad2d  lea     rax, [rbp+Data]
0x18007ad31  xor     r8d, r8d; lpReserved
0x18007ad34  lea     rdx, c_pszRegValForceStrongEncryption; "ForceStrongEncryption"
0x18007ad3b  mov     [rsp+80h+pcchRemaining], rax; lpData
0x18007ad40  call    cs:__imp_RegQueryValueExW
0x18007ad46  mov     edi, eax
0x18007ad48  test    eax, eax
0x18007ad4a  jz      short loc_18007AD6B
0x18007ad4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ad53  cmp     rcx, r12
0x18007ad56  jz      short loc_18007AD9F
0x18007ad58  test    [rcx+1Ch], r15b
0x18007ad5c  jz      short loc_18007AD9F
0x18007ad5e  cmp     byte ptr [rcx+19h], 2
0x18007ad62  jb      short loc_18007AD9F
0x18007ad64  mov     edx, 367h
0x18007ad69  jmp     short loc_18007AD0B
0x18007ad6b  cmp     dword ptr [rbp+Data], r14d
0x18007ad6f  jz      short loc_18007AD87
0x18007ad71  cmp     dword ptr [rsi+0ACh], 100h
0x18007ad7b  jnz     short loc_18007AD87
0x18007ad7d  mov     dword ptr [rsi+0ACh], 200h
0x18007ad87  mov     rcx, [rbp+hKey]; hKey
0x18007ad8b  lea     rdx, c_pszRegValForceStrongEncryption; "ForceStrongEncryption"
0x18007ad92  call    cs:__imp_RegDeleteValueW
0x18007ad98  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ad9f  mov     rax, [rbp+hKey]
0x18007ada3  test    rax, rax
0x18007ada6  jz      short loc_18007ADB8
0x18007ada8  mov     rcx, rax; hKey
0x18007adab  call    cs:__imp_RegCloseKey
0x18007adb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007adb8  cmp     rcx, r12
0x18007adbb  jz      short loc_18007ADE4
0x18007adbd  test    [rcx+1Ch], r15b
0x18007adc1  jz      short loc_18007ADE4
0x18007adc3  cmp     byte ptr [rcx+19h], 6
0x18007adc7  jb      short loc_18007ADE4
0x18007adc9  mov     edx, 368h
0x18007adce  mov     r9d, edi
0x18007add1  mov     rcx, [rcx+10h]
0x18007add5  mov     r8, r13
0x18007add8  call    WPP_SF_d
0x18007addd  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ade4  mov     rax, [rbp+phkResult]
0x18007ade8  test    rax, rax
0x18007adeb  jz      short loc_18007ADFD
0x18007aded  mov     rcx, rax; hKey
0x18007adf0  call    cs:__imp_RegCloseKey
0x18007adf6  mov     rcx, cs:WPP_GLOBAL_Control
0x18007adfd  cmp     rcx, r12
0x18007ae00  jz      short loc_18007AE22
0x18007ae02  test    [rcx+1Ch], r15b
0x18007ae06  jz      short loc_18007AE22
0x18007ae08  cmp     byte ptr [rcx+19h], 6
0x18007ae0c  jb      short loc_18007AE22
0x18007ae0e  mov     rcx, [rcx+10h]
0x18007ae12  mov     edx, 36Dh
0x18007ae17  mov     r9d, ebx
0x18007ae1a  mov     r8, r13
0x18007ae1d  call    WPP_SF_d
0x18007ae22  mov     eax, ebx
0x18007ae24  mov     rcx, [rbp+var_8]
0x18007ae28  xor     rcx, rsp; StackCookie
0x18007ae2b  call    __security_check_cookie
0x18007ae30  mov     rbx, [rsp+80h+arg_10]
0x18007ae38  add     rsp, 80h
0x18007ae3f  pop     r15
0x18007ae41  pop     r14
0x18007ae43  pop     r13
0x18007ae45  pop     r12
0x18007ae47  pop     rdi
0x18007ae48  pop     rsi
0x18007ae49  pop     rbp
0x18007ae4a  retn
```
