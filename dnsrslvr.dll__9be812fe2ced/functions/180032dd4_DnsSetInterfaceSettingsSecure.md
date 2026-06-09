# DnsSetInterfaceSettingsSecure

- ea: `0x180032dd4`
- end: `0x18003318c`
- name: `DnsSetInterfaceSettingsSecure`
- size: `952`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18004d514`

## callees

- `0x180032978`
- `0x180032dd4`
- `0x180046ec0`
- `0x18007db0c`
- `0x1800868b8`
- `0x180086b1c`
- `0x180086f24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800330ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033105`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003311c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033133`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800330ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033105`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003311c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033133`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032efd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032f79`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033010`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003306c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032efd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032f79`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033010`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003306c`

## pseudocode

```c
__int64 __fastcall DnsSetInterfaceSettingsSecure(HKEY hKey, _QWORD *a2, int a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rax
  const wchar_t *v7; // rdx
  __int64 v8; // r9
  const wchar_t *v9; // rcx
  __int64 v10; // r13
  __int64 v11; // rbx
  __int64 v12; // r12
  __int64 v13; // r15
  __int64 v14; // rcx
  int v15; // esi
  const WCHAR *v16; // r15
  LSTATUS v17; // eax
  int v18; // edx
  unsigned int v19; // eax
  __int64 v20; // rdx
  wchar_t *Src; // [rsp+50h] [rbp-19h]
  wchar_t *v23; // [rsp+58h] [rbp-11h]
  HKEY hKeya; // [rsp+60h] [rbp-9h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-1h] BYREF
  HKEY v26; // [rsp+70h] [rbp+7h] BYREF
  HKEY v27; // [rsp+78h] [rbp+Fh] BYREF

  hKeya = 0;
  phkResult = 0;
  v26 = 0;
  v27 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_q(1035, 175, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, a2);
  if ( !a2 )
  {
    v5 = 87;
    goto LABEL_39;
  }
  v6 = a2[1];
  v7 = &WideCharStr;
  v8 = a2[3];
  v9 = &WideCharStr;
  v10 = v6 & 0x1000;
  v11 = v6 & 0x2000;
  v12 = v6 & 0x10000;
  v13 = v6 & 0x20000;
  if ( v8 )
    v9 = (const wchar_t *)a2[3];
  v23 = (wchar_t *)v9;
  v14 = a2[7];
  if ( v14 )
    v7 = (const wchar_t *)a2[7];
  Src = (wchar_t *)v7;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_SSi(v14, 176, a3, v8, v14, v6);
  v15 = a2[1] & 1;
  if ( v11 )
  {
    v5 = RegCreateKeyExW(hKey, L"DohProfileSettings", 0, 0, 0, 0x20006u, 0, &phkResult, 0);
    if ( v5 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_DS(
          1035,
          177,
          (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids,
          v5,
          (__int64)L"DohProfileSettings");
      goto LABEL_39;
    }
    if ( !v13 )
      goto LABEL_22;
  }
  else
  {
    v5 = 0;
    if ( !v13 )
      goto LABEL_23;
  }
  v16 = L"DotProfileSettings";
  v17 = RegCreateKeyExW(hKey, L"DotProfileSettings", 0, 0, 0, 0x20006u, 0, &v27, 0);
  v5 = v17;
  if ( v17 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_39;
    v18 = 178;
    goto LABEL_21;
  }
LABEL_22:
  v19 = DnsWritePropertiesToRegistry(phkResult, v27, Src, a2[13], v15);
  v5 = v19;
  if ( v19 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_39;
    v20 = 179;
    goto LABEL_38;
  }
LABEL_23:
  if ( !v10 )
  {
    if ( !v12 )
      goto LABEL_39;
LABEL_30:
    v16 = L"DotInterfaceSettings";
    v17 = RegCreateKeyExW(hKey, L"DotInterfaceSettings", 0, 0, 0, 0x20006u, 0, &v26, 0);
    v5 = v17;
    if ( v17 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_39;
      v18 = 181;
LABEL_21:
      WPP_SF_DS(1035, v18, (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v17, (__int64)v16);
      goto LABEL_39;
    }
    goto LABEL_33;
  }
  v16 = L"DohInterfaceSettings";
  v17 = RegCreateKeyExW(hKey, L"DohInterfaceSettings", 0, 0, 0, 0x20006u, 0, &hKeya, 0);
  v5 = v17;
  if ( v17 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_39;
    v18 = 180;
    goto LABEL_21;
  }
  if ( v12 )
    goto LABEL_30;
LABEL_33:
  v19 = DnsWritePropertiesToRegistry(hKeya, v26, v23, a2[11], v15);
  v5 = v19;
  if ( v19 && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    v20 = 182;
LABEL_38:
    WPP_SF_d(1035, v20, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v19);
  }
LABEL_39:
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( v26 )
  {
    RegCloseKey(v26);
    v26 = 0;
  }
  if ( v27 )
  {
    RegCloseKey(v27);
    v27 = 0;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 183, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180032dd4  mov     [rsp-8+arg_10], rbx
0x180032dd9  push    rbp
0x180032dda  push    rsi
0x180032ddb  push    rdi
0x180032ddc  push    r12
0x180032dde  push    r13
0x180032de0  push    r14
0x180032de2  push    r15
0x180032de4  lea     rbp, [rsp-27h]
0x180032de9  sub     rsp, 90h
0x180032df0  mov     rax, cs:__security_cookie
0x180032df7  xor     rax, rsp
0x180032dfa  mov     [rbp+57h+var_40], rax
0x180032dfe  xor     ebx, ebx
0x180032e00  mov     rdi, rdx
0x180032e03  mov     [rbp+57h+hKey], rbx
0x180032e07  mov     r14, rcx
0x180032e0a  mov     [rbp+57h+var_58], rbx
0x180032e0e  mov     [rbp+57h+var_50], rbx
0x180032e12  mov     [rbp+57h+var_48], rbx
0x180032e16  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180032e1d  jz      short loc_180032E38
0x180032e1f  mov     edx, 0AFh
0x180032e24  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180032e2b  mov     ecx, 40Bh
0x180032e30  mov     r9, rdi
0x180032e33  call    WPP_SF_q
0x180032e38  test    rdi, rdi
0x180032e3b  jnz     short loc_180032E45
0x180032e3d  lea     ebx, [rdi+57h]
0x180032e40  jmp     loc_1800330E5
0x180032e45  mov     rax, [rdi+8]
0x180032e49  lea     rdx, WideCharStr
0x180032e50  mov     r9, [rdi+18h]
0x180032e54  mov     rcx, rdx
0x180032e57  mov     r13, rax
0x180032e5a  mov     rbx, rax
0x180032e5d  and     r13d, 1000h
0x180032e64  and     ebx, 2000h
0x180032e6a  mov     r12, rax
0x180032e6d  mov     r15, rax
0x180032e70  and     r12d, 10000h
0x180032e77  and     r15d, 20000h
0x180032e7e  test    r9, r9
0x180032e81  cmovnz  rcx, r9
0x180032e85  mov     [rbp+57h+var_68], rcx
0x180032e89  mov     rcx, [rdi+38h]
0x180032e8d  test    rcx, rcx
0x180032e90  cmovnz  rdx, rcx
0x180032e94  mov     [rbp+57h+Src], rdx
0x180032e98  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180032e9f  jz      short loc_180032EB5
0x180032ea1  mov     qword ptr [rsp+0C0h+samDesired], rax
0x180032ea6  mov     edx, 0B0h
0x180032eab  mov     qword ptr [rsp+0C0h+dwOptions], rcx
0x180032eb0  call    WPP_SF_SSi
0x180032eb5  mov     esi, [rdi+8]
0x180032eb8  xor     ecx, ecx
0x180032eba  and     esi, 1
0x180032ebd  test    rbx, rbx
0x180032ec0  jnz     short loc_180032ECE
0x180032ec2  mov     ebx, ecx
0x180032ec4  test    r15, r15
0x180032ec7  jnz     short loc_180032F47
0x180032ec9  jmp     loc_180032FCF
0x180032ece  mov     [rsp+0C0h+lpdwDisposition], rcx; lpdwDisposition
0x180032ed3  lea     rax, [rbp+57h+var_58]
0x180032ed7  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180032edc  lea     rdx, aDohprofilesett; "DohProfileSettings"
0x180032ee3  mov     [rsp+0C0h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x180032ee8  xor     r9d, r9d; lpClass
0x180032eeb  mov     [rsp+0C0h+samDesired], 20006h; samDesired
0x180032ef3  xor     r8d, r8d; Reserved
0x180032ef6  mov     [rsp+0C0h+dwOptions], ecx; dwOptions
0x180032efa  mov     rcx, r14; hKey
0x180032efd  call    cs:__imp_RegCreateKeyExW
0x180032f03  xor     ecx, ecx
0x180032f05  mov     ebx, eax
0x180032f07  test    eax, eax
0x180032f09  jz      short loc_180032F42
0x180032f0b  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180032f12  jz      loc_1800330E5
0x180032f18  lea     rax, aDohprofilesett; "DohProfileSettings"
0x180032f1f  mov     edx, 0B1h
0x180032f24  mov     qword ptr [rsp+0C0h+dwOptions], rax
0x180032f29  mov     r9d, ebx
0x180032f2c  mov     ecx, 40Bh
0x180032f31  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180032f38  call    WPP_SF_DS
0x180032f3d  jmp     loc_1800330E5
0x180032f42  test    r15, r15
0x180032f45  jz      short loc_180032FA1
0x180032f47  mov     [rsp+0C0h+lpdwDisposition], rcx; lpdwDisposition
0x180032f4c  lea     rax, [rbp+57h+var_48]
0x180032f50  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180032f55  lea     r15, aDotprofilesett; "DotProfileSettings"
0x180032f5c  mov     [rsp+0C0h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x180032f61  xor     r9d, r9d; lpClass
0x180032f64  mov     [rsp+0C0h+samDesired], 20006h; samDesired
0x180032f6c  xor     r8d, r8d; Reserved
0x180032f6f  mov     [rsp+0C0h+dwOptions], ecx; dwOptions
0x180032f73  mov     rdx, r15; lpSubKey
0x180032f76  mov     rcx, r14; hKey
0x180032f79  call    cs:__imp_RegCreateKeyExW
0x180032f7f  mov     ebx, eax
0x180032f81  test    eax, eax
0x180032f83  jz      short loc_180032FA1
0x180032f85  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180032f8c  jz      loc_1800330E5
0x180032f92  mov     edx, 0B2h
0x180032f97  mov     qword ptr [rsp+0C0h+dwOptions], r15
0x180032f9c  mov     r9d, eax
0x180032f9f  jmp     short loc_180032F2C
0x180032fa1  mov     rax, [rdi+68h]
0x180032fa5  mov     r9d, [rdi+60h]
0x180032fa9  mov     r8, [rbp+57h+Src]; Src
0x180032fad  mov     rdx, [rbp+57h+var_48]; HKEY
0x180032fb1  mov     rcx, [rbp+57h+var_58]; hKey
0x180032fb5  mov     [rsp+0C0h+samDesired], esi; int
0x180032fb9  mov     qword ptr [rsp+0C0h+dwOptions], rax; __int64
0x180032fbe  call    DnsWritePropertiesToRegistry
0x180032fc3  xor     ecx, ecx
0x180032fc5  mov     ebx, eax
0x180032fc7  test    eax, eax
0x180032fc9  jnz     loc_1800330C3
0x180032fcf  test    r13, r13
0x180032fd2  jnz     short loc_180032FDE
0x180032fd4  test    r12, r12
0x180032fd7  jnz     short loc_18003303A
0x180032fd9  jmp     loc_1800330E5
0x180032fde  mov     [rsp+0C0h+lpdwDisposition], rcx; lpdwDisposition
0x180032fe3  lea     rax, [rbp+57h+hKey]
0x180032fe7  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180032fec  lea     r15, SubKey; "DohInterfaceSettings"
0x180032ff3  mov     [rsp+0C0h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x180032ff8  xor     r9d, r9d; lpClass
0x180032ffb  mov     [rsp+0C0h+samDesired], 20006h; samDesired
0x180033003  xor     r8d, r8d; Reserved
0x180033006  mov     [rsp+0C0h+dwOptions], ecx; dwOptions
0x18003300a  mov     rdx, r15; lpSubKey
0x18003300d  mov     rcx, r14; hKey
0x180033010  call    cs:__imp_RegCreateKeyExW
0x180033016  xor     ecx, ecx
0x180033018  mov     ebx, eax
0x18003301a  test    eax, eax
0x18003301c  jz      short loc_180033035
0x18003301e  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180033025  jz      loc_1800330E5
0x18003302b  mov     edx, 0B4h
0x180033030  jmp     loc_180032F97
0x180033035  test    r12, r12
0x180033038  jz      short loc_18003308B
0x18003303a  mov     [rsp+0C0h+lpdwDisposition], rcx; lpdwDisposition
0x18003303f  lea     rax, [rbp+57h+var_50]
0x180033043  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180033048  lea     r15, aDotinterfacese; "DotInterfaceSettings"
0x18003304f  mov     [rsp+0C0h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x180033054  xor     r9d, r9d; lpClass
0x180033057  mov     [rsp+0C0h+samDesired], 20006h; samDesired
0x18003305f  xor     r8d, r8d; Reserved
0x180033062  mov     [rsp+0C0h+dwOptions], ecx; dwOptions
0x180033066  mov     rdx, r15; lpSubKey
0x180033069  mov     rcx, r14; hKey
0x18003306c  call    cs:__imp_RegCreateKeyExW
0x180033072  mov     ebx, eax
0x180033074  test    eax, eax
0x180033076  jz      short loc_18003308B
0x180033078  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003307f  jz      short loc_1800330E5
0x180033081  mov     edx, 0B5h
0x180033086  jmp     loc_180032F97
0x18003308b  mov     rax, [rdi+58h]
0x18003308f  mov     r9d, [rdi+50h]
0x180033093  mov     r8, [rbp+57h+var_68]; Src
0x180033097  mov     rdx, [rbp+57h+var_50]; HKEY
0x18003309b  mov     rcx, [rbp+57h+hKey]; hKey
0x18003309f  mov     [rsp+0C0h+samDesired], esi; int
0x1800330a3  mov     qword ptr [rsp+0C0h+dwOptions], rax; __int64
0x1800330a8  call    DnsWritePropertiesToRegistry
0x1800330ad  mov     ebx, eax
0x1800330af  test    eax, eax
0x1800330b1  jz      short loc_1800330E5
0x1800330b3  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800330ba  jz      short loc_1800330E5
0x1800330bc  mov     edx, 0B6h
0x1800330c1  jmp     short loc_1800330D1
0x1800330c3  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800330ca  jz      short loc_1800330E5
0x1800330cc  mov     edx, 0B3h
0x1800330d1  mov     r9d, eax
0x1800330d4  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x1800330db  mov     ecx, 40Bh
0x1800330e0  call    WPP_SF_d
0x1800330e5  mov     rcx, [rbp+57h+hKey]; hKey
0x1800330e9  test    rcx, rcx
0x1800330ec  jz      short loc_1800330FC
0x1800330ee  call    cs:__imp_RegCloseKey
0x1800330f4  mov     [rbp+57h+hKey], 0
0x1800330fc  mov     rcx, [rbp+57h+var_58]; hKey
0x180033100  test    rcx, rcx
0x180033103  jz      short loc_180033113
0x180033105  call    cs:__imp_RegCloseKey
0x18003310b  mov     [rbp+57h+var_58], 0
0x180033113  mov     rcx, [rbp+57h+var_50]; hKey
0x180033117  test    rcx, rcx
0x18003311a  jz      short loc_18003312A
0x18003311c  call    cs:__imp_RegCloseKey
0x180033122  mov     [rbp+57h+var_50], 0
0x18003312a  mov     rcx, [rbp+57h+var_48]; hKey
0x18003312e  test    rcx, rcx
0x180033131  jz      short loc_180033141
0x180033133  call    cs:__imp_RegCloseKey
0x180033139  mov     [rbp+57h+var_48], 0
0x180033141  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180033148  jz      short loc_180033163
0x18003314a  mov     edx, 0B7h
0x18003314f  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180033156  mov     ecx, 40Bh
0x18003315b  mov     r9d, ebx
0x18003315e  call    WPP_SF_d
0x180033163  mov     eax, ebx
0x180033165  mov     rcx, [rbp+57h+var_40]
0x180033169  xor     rcx, rsp; StackCookie
0x18003316c  call    __security_check_cookie
0x180033171  mov     rbx, [rsp+0C0h+arg_10]
0x180033179  add     rsp, 90h
0x180033180  pop     r15
0x180033182  pop     r14
0x180033184  pop     r13
0x180033186  pop     r12
0x180033188  pop     rdi
0x180033189  pop     rsi
0x18003318a  pop     rbp
0x18003318b  retn
```
