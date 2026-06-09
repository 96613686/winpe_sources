# IsDhcpRACoexistenceEnabled

- ea: `0x180037774`
- end: `0x1800379ba`
- name: `IsDhcpRACoexistenceEnabled`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180036804`

## callees

- `0x180037774`
- `0x18008b5f0`
- `0x1800cc790`
- `0x1800dbb48`
- `0x1800dbfe0`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037905`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037905`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800378b3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800378b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800377f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800377f4`

## pseudocode

```c
unsigned __int8 __fastcall IsDhcpRACoexistenceEnabled(__int64 a1, __int64 a2, int a3)
{
  unsigned __int8 v4; // r15
  unsigned __int8 v5; // r14
  unsigned int v6; // eax
  unsigned int v7; // ebx
  HKEY v8; // rsi
  LSTATUS v10; // eax
  int v11; // ecx
  int v12; // edi
  int v13; // ebx
  HKEY hKey; // [rsp+30h] [rbp-20h] BYREF
  DWORD Type; // [rsp+38h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-14h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-10h] BYREF

  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_S(1035, 68, WPP_caccfeb905c83e320acfcbeb12c6208a_Traceguids, a1 + 104);
  v4 = dword_18011185C != 0;
  hKey = 0;
  v5 = dword_18011185C != 0;
  if ( !g_Dhcpv6Key )
  {
    v7 = 2;
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      goto LABEL_5;
    WPP_SF_d(1035, 16, WPP_caccfeb905c83e320acfcbeb12c6208a_Traceguids, 2);
    goto LABEL_12;
  }
  v6 = RegOpenKeyExW(g_Dhcpv6Key, (LPCWSTR)(a1 + 104), 0, 0x20019u, &hKey);
  v7 = v6;
  if ( v6 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_d(1035, 17, WPP_caccfeb905c83e320acfcbeb12c6208a_Traceguids, v6);
    if ( v7 != 1168 )
    {
LABEL_12:
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
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
  v12 = v10;
  if ( v10 )
  {
    if ( v10 == 2 )
      goto LABEL_20;
    goto LABEL_18;
  }
  if ( cbData != 4 || Type != 4 )
  {
    v12 = 1010;
LABEL_18:
    v13 = 0;
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      goto LABEL_20;
    WPP_SF_SD(
      v11,
      12,
      (unsigned int)WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids,
      (unsigned int)L"DhcpRACoexistenceEnabled",
      v12);
    if ( v12 )
      goto LABEL_20;
    goto LABEL_24;
  }
  v13 = *(_DWORD *)Data;
LABEL_24:
  v5 = v13 != 0;
LABEL_20:
  RegCloseKey(v8);
LABEL_6:
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_Sll(v4, v5, a3, a1 + 104, v5, v4);
  return v5;
}

```

## disassembly

```asm
0x180037774  mov     [rsp-28h+arg_8], rbx
0x180037779  mov     [rsp-28h+arg_10], rsi
0x18003777e  push    rbp
0x18003777f  push    rdi
0x180037780  push    r13
0x180037782  push    r14
0x180037784  push    r15
0x180037786  mov     rbp, rsp
0x180037789  sub     rsp, 50h
0x18003778d  mov     rax, cs:__security_cookie
0x180037794  xor     rax, rsp
0x180037797  mov     [rbp+var_8], rax
0x18003779b  mov     r13, rcx
0x18003779e  mov     dil, 8
0x1800377a1  mov     esi, 40Bh
0x1800377a6  test    byte ptr cs:xmmword_1801119E0+1, dil
0x1800377ad  jnz     loc_180037952
0x1800377b3  cmp     cs:dword_18011185C, 0
0x1800377ba  mov     eax, 2
0x1800377bf  mov     rcx, cs:g_Dhcpv6Key; hKey
0x1800377c6  setnz   r15b
0x1800377ca  mov     [rbp+hKey], 0
0x1800377d2  mov     r14b, r15b
0x1800377d5  test    rcx, rcx
0x1800377d8  jz      loc_180037990
0x1800377de  lea     rax, [rbp+hKey]
0x1800377e2  mov     r9d, 20019h; samDesired
0x1800377e8  xor     r8d, r8d; ulOptions
0x1800377eb  mov     [rsp+50h+phkResult], rax; phkResult
0x1800377f0  lea     rdx, [r13+68h]; lpSubKey
0x1800377f4  call    cs:__imp_RegOpenKeyExW
0x1800377fb  nop     dword ptr [rax+rax+00h]
0x180037800  mov     ebx, eax
0x180037802  test    eax, eax
0x180037804  jnz     short loc_180037845
0x180037806  mov     rsi, [rbp+hKey]
0x18003780a  test    rsi, rsi
0x18003780d  jnz     short loc_18003787B
0x18003780f  test    byte ptr cs:xmmword_1801119E0+1, dil
0x180037816  jnz     loc_180037934
0x18003781c  mov     al, r14b
0x18003781f  mov     rcx, [rbp+var_8]
0x180037823  xor     rcx, rsp; StackCookie
0x180037826  call    __security_check_cookie
0x18003782b  lea     r11, [rsp+50h+var_s0]
0x180037830  mov     rbx, [r11+38h]
0x180037834  mov     rsi, [r11+40h]
0x180037838  mov     rsp, r11
0x18003783b  pop     r15
0x18003783d  pop     r14
0x18003783f  pop     r13
0x180037841  pop     rdi
0x180037842  pop     rbp
0x180037843  retn
0x180037845  test    byte ptr cs:xmmword_1801119E0+1, dil
0x18003784c  jnz     loc_180037919
0x180037852  cmp     ebx, 490h
0x180037858  jz      short loc_180037806
0x18003785a  test    byte ptr cs:xmmword_1801119E0+1, dil
0x180037861  jz      short loc_180037806
0x180037863  mov     edx, 12h
0x180037868  lea     r8, WPP_caccfeb905c83e320acfcbeb12c6208a_Traceguids
0x18003786f  mov     ecx, esi
0x180037871  mov     r9d, ebx
0x180037874  call    WPP_SF_d
0x180037879  jmp     short loc_180037806
0x18003787b  lea     rax, [rbp+cbData]
0x18003787f  mov     dword ptr [rbp+Data], 0
0x180037886  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18003788b  lea     r9, [rbp+Type]; lpType
0x18003788f  lea     rax, [rbp+Data]
0x180037893  mov     [rbp+Type], 0
0x18003789a  xor     r8d, r8d; lpReserved
0x18003789d  mov     [rsp+50h+phkResult], rax; lpData
0x1800378a2  lea     rdx, aDhcpracoexiste; "DhcpRACoexistenceEnabled"
0x1800378a9  mov     [rbp+cbData], 4
0x1800378b0  mov     rcx, rsi; hKey
0x1800378b3  call    cs:__imp_RegQueryValueExW
0x1800378ba  nop     dword ptr [rax+rax+00h]
0x1800378bf  mov     edi, eax
0x1800378c1  test    eax, eax
0x1800378c3  jz      loc_18003796E
0x1800378c9  cmp     eax, 2
0x1800378cc  jnz     short loc_1800378D5
0x1800378ce  jmp     short loc_180037902
0x1800378d0  mov     edi, 3F2h
0x1800378d5  xor     ebx, ebx
0x1800378d7  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800378de  jz      short loc_180037902
0x1800378e0  lea     edx, [rbx+0Ch]
0x1800378e3  mov     dword ptr [rsp+50h+phkResult], edi
0x1800378e7  lea     r9, aDhcpracoexiste; "DhcpRACoexistenceEnabled"
0x1800378ee  lea     r8, WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids
0x1800378f5  call    WPP_SF_SD
0x1800378fa  test    edi, edi
0x1800378fc  jz      loc_180037985
0x180037902  mov     rcx, rsi; hKey
0x180037905  call    cs:__imp_RegCloseKey
0x18003790c  nop     dword ptr [rax+rax+00h]
0x180037911  mov     dil, 8
0x180037914  jmp     loc_18003780F
0x180037919  mov     edx, 11h
0x18003791e  lea     r8, WPP_caccfeb905c83e320acfcbeb12c6208a_Traceguids
0x180037925  mov     ecx, esi
0x180037927  mov     r9d, ebx
0x18003792a  call    WPP_SF_d
0x18003792f  jmp     loc_180037852
0x180037934  movzx   ecx, r15b
0x180037938  lea     r9, [r13+68h]
0x18003793c  movzx   edx, r14b
0x180037940  mov     dword ptr [rsp+50h+lpcbData], ecx
0x180037944  mov     dword ptr [rsp+50h+phkResult], edx
0x180037948  call    WPP_SF_Sll
0x18003794d  jmp     loc_18003781C
0x180037952  mov     edx, 44h ; 'D'
0x180037957  lea     r9, [r13+68h]
0x18003795b  mov     ecx, esi
0x18003795d  lea     r8, WPP_caccfeb905c83e320acfcbeb12c6208a_Traceguids
0x180037964  call    WPP_SF_S
0x180037969  jmp     loc_1800377B3
0x18003796e  cmp     [rbp+cbData], 4
0x180037972  jnz     loc_1800378D0
0x180037978  cmp     [rbp+Type], 4
0x18003797c  jnz     loc_1800378D0
0x180037982  mov     ebx, dword ptr [rbp+Data]
0x180037985  test    ebx, ebx
0x180037987  setnz   r14b
0x18003798b  jmp     loc_180037902
0x180037990  mov     ebx, eax
0x180037992  test    byte ptr cs:xmmword_1801119E0+1, dil
0x180037999  jz      loc_180037806
0x18003799f  mov     edx, 10h
0x1800379a4  lea     r8, WPP_caccfeb905c83e320acfcbeb12c6208a_Traceguids
0x1800379ab  mov     ecx, esi
0x1800379ad  mov     r9d, eax
0x1800379b0  call    WPP_SF_d
0x1800379b5  jmp     loc_18003785A
```
