# IsDhcpRACoexistenceEnabled

- ea: `0x180008b70`
- end: `0x180008dac`
- name: `IsDhcpRACoexistenceEnabled`
- size: `572`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180009e10`

## callees

- `0x180008b70`
- `0x180046ec0`
- `0x18007a3dc`
- `0x180085fb8`
- `0x180086384`
- `0x180086b1c`

## import_xrefs

- `DNSAPI!DnsGlobals` at `0x180008ba1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008cfd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008cfd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008be6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008be6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008d40`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008d40`

## pseudocode

```c
__int64 __fastcall IsDhcpRACoexistenceEnabled(__int64 a1, __int64 a2, int a3)
{
  unsigned __int8 v4; // bp
  unsigned __int8 v5; // di
  unsigned int v6; // eax
  unsigned int v7; // ebx
  HKEY v8; // rbx
  LSTATUS v10; // eax
  int v11; // r14d
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  DWORD Type; // [rsp+38h] [rbp-30h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-2Ch] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-28h] BYREF

  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_S(1035, 68, WPP_caccfeb905c83e320acfcbeb12c6208a_Traceguids, a1 + 104);
  v4 = DnsGlobals[103] != 0;
  hKey = 0;
  v5 = v4;
  if ( !g_Dhcpv6Key )
  {
    v7 = 2;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_5;
    WPP_SF_d(1035, 16, WPP_caccfeb905c83e320acfcbeb12c6208a_Traceguids, 2);
    goto LABEL_12;
  }
  v6 = RegOpenKeyExW(g_Dhcpv6Key, (LPCWSTR)(a1 + 104), 0, 0x20019u, &hKey);
  v7 = v6;
  if ( v6 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 17, WPP_caccfeb905c83e320acfcbeb12c6208a_Traceguids, v6);
    if ( v7 != 1168 )
    {
LABEL_12:
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_d(1035, 18, WPP_caccfeb905c83e320acfcbeb12c6208a_Traceguids, v7);
    }
  }
LABEL_5:
  v8 = hKey;
  if ( !hKey )
    goto LABEL_6;
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 4;
  v10 = RegQueryValueExW(hKey, L"DhcpRACoexistenceEnabled", 0, &Type, Data, &cbData);
  v11 = v10;
  if ( v10 )
  {
    if ( v10 != 2 )
    {
LABEL_20:
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_17;
      WPP_SF_SD(
        1035,
        12,
        (unsigned int)WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids,
        (unsigned int)L"DhcpRACoexistenceEnabled",
        v11);
      if ( v11 )
        goto LABEL_17;
      goto LABEL_27;
    }
  }
  else
  {
    if ( cbData != 4 || Type != 4 )
    {
      v11 = 1010;
      goto LABEL_20;
    }
    if ( !*(_DWORD *)Data )
    {
LABEL_27:
      v5 = 0;
      goto LABEL_17;
    }
    v5 = 1;
  }
LABEL_17:
  RegCloseKey(v8);
LABEL_6:
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_Sll(v4, v5, a3, a1 + 104, v5, v4);
  return v5;
}

```

## disassembly

```asm
0x180008b70  mov     [rsp+arg_8], rbx
0x180008b75  mov     [rsp+arg_10], rbp
0x180008b7a  push    rsi
0x180008b7b  push    rdi
0x180008b7c  push    r14
0x180008b7e  sub     rsp, 50h
0x180008b82  mov     rax, cs:__security_cookie
0x180008b89  xor     rax, rsp
0x180008b8c  mov     [rsp+68h+var_20], rax
0x180008b91  mov     rsi, rcx
0x180008b94  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180008b9b  jnz     loc_180008D76
0x180008ba1  mov     rax, cs:__imp_DnsGlobals
0x180008ba8  mov     rcx, cs:g_Dhcpv6Key; hKey
0x180008baf  cmp     dword ptr [rax+19Ch], 0
0x180008bb6  setnz   bpl
0x180008bba  xor     r14d, r14d
0x180008bbd  mov     [rsp+68h+hKey], r14
0x180008bc2  movzx   edi, bpl
0x180008bc6  test    rcx, rcx
0x180008bc9  jz      loc_180008C84
0x180008bcf  lea     rax, [rsp+68h+hKey]
0x180008bd4  mov     r9d, 20019h; samDesired
0x180008bda  xor     r8d, r8d; ulOptions
0x180008bdd  mov     [rsp+68h+phkResult], rax; phkResult
0x180008be2  lea     rdx, [rsi+68h]; lpSubKey
0x180008be6  call    cs:__imp_RegOpenKeyExW
0x180008bec  mov     ebx, eax
0x180008bee  test    eax, eax
0x180008bf0  jnz     short loc_180008C34
0x180008bf2  mov     rbx, [rsp+68h+hKey]
0x180008bf7  test    rbx, rbx
0x180008bfa  jnz     loc_180008D08
0x180008c00  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180008c07  jnz     loc_180008CB1
0x180008c0d  movzx   eax, dil
0x180008c11  mov     rcx, [rsp+68h+var_20]
0x180008c16  xor     rcx, rsp; StackCookie
0x180008c19  call    __security_check_cookie
0x180008c1e  mov     rbx, [rsp+68h+arg_8]
0x180008c23  mov     rbp, [rsp+68h+arg_10]
0x180008c2b  add     rsp, 50h
0x180008c2f  pop     r14
0x180008c31  pop     rdi
0x180008c32  pop     rsi
0x180008c33  retn
0x180008c34  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180008c3b  jnz     short loc_180008C69
0x180008c3d  cmp     ebx, 490h
0x180008c43  jz      short loc_180008BF2
0x180008c45  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180008c4c  jz      short loc_180008BF2
0x180008c4e  mov     edx, 12h
0x180008c53  lea     r8, WPP_caccfeb905c83e320acfcbeb12c6208a_Traceguids
0x180008c5a  mov     ecx, 40Bh
0x180008c5f  mov     r9d, ebx
0x180008c62  call    WPP_SF_d
0x180008c67  jmp     short loc_180008BF2
0x180008c69  mov     edx, 11h
0x180008c6e  lea     r8, WPP_caccfeb905c83e320acfcbeb12c6208a_Traceguids
0x180008c75  mov     ecx, 40Bh
0x180008c7a  mov     r9d, ebx
0x180008c7d  call    WPP_SF_d
0x180008c82  jmp     short loc_180008C3D
0x180008c84  mov     ebx, 2
0x180008c89  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180008c90  jz      loc_180008BF2
0x180008c96  mov     edx, 10h
0x180008c9b  lea     r8, WPP_caccfeb905c83e320acfcbeb12c6208a_Traceguids
0x180008ca2  mov     ecx, 40Bh
0x180008ca7  mov     r9d, ebx
0x180008caa  call    WPP_SF_d
0x180008caf  jmp     short loc_180008C45
0x180008cb1  movzx   ecx, bpl
0x180008cb5  lea     r9, [rsi+68h]
0x180008cb9  movzx   edx, dil
0x180008cbd  mov     dword ptr [rsp+68h+lpcbData], ecx
0x180008cc1  mov     dword ptr [rsp+68h+phkResult], edx
0x180008cc5  call    WPP_SF_Sll
0x180008cca  jmp     loc_180008C0D
0x180008ccf  mov     edx, 0Ch
0x180008cd4  mov     dword ptr [rsp+68h+phkResult], r14d
0x180008cd9  mov     ecx, 40Bh
0x180008cde  lea     r9, ValueName; "DhcpRACoexistenceEnabled"
0x180008ce5  lea     r8, WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids
0x180008cec  call    WPP_SF_SD
0x180008cf1  test    r14d, r14d
0x180008cf4  jz      loc_180008DA4
0x180008cfa  mov     rcx, rbx; hKey
0x180008cfd  call    cs:__imp_RegCloseKey
0x180008d03  jmp     loc_180008C00
0x180008d08  lea     rax, [rsp+68h+cbData]
0x180008d0d  mov     dword ptr [rsp+68h+Data], r14d
0x180008d12  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180008d17  lea     r9, [rsp+68h+Type]; lpType
0x180008d1c  lea     rax, [rsp+68h+Data]
0x180008d21  mov     [rsp+68h+Type], r14d
0x180008d26  xor     r8d, r8d; lpReserved
0x180008d29  mov     [rsp+68h+phkResult], rax; lpData
0x180008d2e  lea     rdx, ValueName; "DhcpRACoexistenceEnabled"
0x180008d35  mov     [rsp+68h+cbData], 4
0x180008d3d  mov     rcx, rbx; hKey
0x180008d40  call    cs:__imp_RegQueryValueExW
0x180008d46  mov     r14d, eax
0x180008d49  test    eax, eax
0x180008d4b  jz      short loc_180008D60
0x180008d4d  cmp     eax, 2
0x180008d50  jz      short loc_180008CFA
0x180008d52  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180008d59  jz      short loc_180008CFA
0x180008d5b  jmp     loc_180008CCF
0x180008d60  cmp     [rsp+68h+cbData], 4
0x180008d65  jnz     short loc_180008D6E
0x180008d67  cmp     [rsp+68h+Type], 4
0x180008d6c  jz      short loc_180008D95
0x180008d6e  mov     r14d, 3F2h
0x180008d74  jmp     short loc_180008D52
0x180008d76  mov     edx, 44h ; 'D'
0x180008d7b  lea     r9, [rsi+68h]
0x180008d7f  mov     ecx, 40Bh
0x180008d84  lea     r8, WPP_caccfeb905c83e320acfcbeb12c6208a_Traceguids
0x180008d8b  call    WPP_SF_S
0x180008d90  jmp     loc_180008BA1
0x180008d95  cmp     dword ptr [rsp+68h+Data], 0
0x180008d9a  jz      short loc_180008DA4
0x180008d9c  mov     dil, 1
0x180008d9f  jmp     loc_180008CFA
0x180008da4  xor     dil, dil
0x180008da7  jmp     loc_180008CFA
```
