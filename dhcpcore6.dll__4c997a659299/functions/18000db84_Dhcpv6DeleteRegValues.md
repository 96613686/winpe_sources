# Dhcpv6DeleteRegValues

- ea: `0x18000db84`
- end: `0x18000dd78`
- name: `Dhcpv6DeleteRegValues`
- size: `500`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800132c0`
- `0x180013410`
- `0x180013580`
- `0x180013840`
- `0x180013a00`
- `0x180014590`

## callees

- `0x18000db84`
- `0x1800337d0`
- `0x180033970`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000dc72`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000dca6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000dc72`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000dca6`

## pseudocode

```c
__int64 __fastcall Dhcpv6DeleteRegValues(__int64 a1)
{
  HKEY v1; // rsi
  __int64 v2; // rbx
  LSTATUS v3; // eax
  __int64 i; // rbx
  LSTATUS v5; // eax
  LPCWSTR lpValueName[10]; // [rsp+30h] [rbp-49h]
  LPCWSTR v8[10]; // [rsp+80h] [rbp+7h]

  v1 = *(HKEY *)(a1 + 648);
  lpValueName[0] = L"DhcpUseUTF8";
  v2 = 0;
  lpValueName[1] = L"Dhcpv6MaxLeaseExpireTime";
  lpValueName[2] = L"Dhcpv6UseInfoRequest";
  lpValueName[3] = L"Dhcpv6ServerPreference";
  lpValueName[4] = L"Dhcpv6IsUnicastEnabled";
  lpValueName[5] = L"Dhcpv6ReleaseOnShutdown";
  lpValueName[6] = L"Dhcpv6LeaseObtainedTime";
  lpValueName[7] = L"Dhcpv6InformationObtainedTime";
  lpValueName[8] = L"Dhcpv6InformationRefreshTime";
  v8[0] = L"Dhcpv6IanaLeases";
  v8[1] = L"Dhcpv6IataLeases";
  v8[2] = L"Dhcpv6ServerDUID";
  v8[3] = L"Dhcpv6IanaAddr";
  v8[4] = L"Dhcpv6IataAddr";
  v8[5] = L"Dhcpv6T1";
  v8[6] = L"Dhcpv6T2";
  v8[7] = L"Dhcpv6IanaIaids";
  v8[8] = L"Dhcpv6IataIaids";
  do
  {
    v3 = RegDeleteValueW(v1, lpValueName[v2]);
    if ( v3 )
    {
      if ( (xmmword_1800423E0 & 2) != 0 )
        WPP_SF_SD(
          1025,
          69,
          (unsigned int)WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids,
          (unsigned int)lpValueName[v2],
          v3);
    }
    else if ( (xmmword_1800423E0 & 0x10) != 0 )
    {
      WPP_SF_S(1028, 70, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, lpValueName[v2]);
    }
    ++v2;
  }
  while ( v2 != 9 );
  for ( i = 0; i != 9; ++i )
  {
    v5 = RegDeleteValueW(v1, v8[i]);
    if ( v5 )
    {
      if ( (xmmword_1800423E0 & 2) != 0 )
        WPP_SF_SD(1025, 71, (unsigned int)WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, (unsigned int)v8[i], v5);
    }
    else if ( (xmmword_1800423E0 & 0x10) != 0 )
    {
      WPP_SF_S(1028, 72, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, v8[i]);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000db84  mov     [rsp-8+arg_0], rbx
0x18000db89  mov     [rsp-8+arg_8], rsi
0x18000db8e  push    rbp
0x18000db8f  lea     rbp, [rsp-57h]
0x18000db94  sub     rsp, 0D0h
0x18000db9b  mov     rsi, [rcx+288h]
0x18000dba2  lea     rax, aDhcpuseutf8; "DhcpUseUTF8"
0x18000dba9  mov     [rbp+57h+lpValueName], rax
0x18000dbad  xor     ebx, ebx
0x18000dbaf  lea     rax, aDhcpv6maxlease; "Dhcpv6MaxLeaseExpireTime"
0x18000dbb6  mov     [rbp+57h+var_98], rax
0x18000dbba  lea     rax, aDhcpv6useinfor; "Dhcpv6UseInfoRequest"
0x18000dbc1  mov     [rbp+57h+var_90], rax
0x18000dbc5  lea     rax, aDhcpv6serverpr; "Dhcpv6ServerPreference"
0x18000dbcc  mov     [rbp+57h+var_88], rax
0x18000dbd0  lea     rax, aDhcpv6isunicas; "Dhcpv6IsUnicastEnabled"
0x18000dbd7  mov     [rbp+57h+var_80], rax
0x18000dbdb  lea     rax, aDhcpv6releaseo; "Dhcpv6ReleaseOnShutdown"
0x18000dbe2  mov     [rbp+57h+var_78], rax
0x18000dbe6  lea     rax, aDhcpv6leaseobt; "Dhcpv6LeaseObtainedTime"
0x18000dbed  mov     [rbp+57h+var_70], rax
0x18000dbf1  lea     rax, aDhcpv6informat_0; "Dhcpv6InformationObtainedTime"
0x18000dbf8  mov     [rbp+57h+var_68], rax
0x18000dbfc  lea     rax, aDhcpv6informat; "Dhcpv6InformationRefreshTime"
0x18000dc03  mov     [rbp+57h+var_60], rax
0x18000dc07  lea     rax, aDhcpv6ianaleas; "Dhcpv6IanaLeases"
0x18000dc0e  mov     [rbp+57h+var_50], rax
0x18000dc12  lea     rax, aDhcpv6iataleas; "Dhcpv6IataLeases"
0x18000dc19  mov     [rbp+57h+var_48], rax
0x18000dc1d  lea     rax, aDhcpv6serverdu; "Dhcpv6ServerDUID"
0x18000dc24  mov     [rbp+57h+var_40], rax
0x18000dc28  lea     rax, aDhcpv6ianaaddr; "Dhcpv6IanaAddr"
0x18000dc2f  mov     [rbp+57h+var_38], rax
0x18000dc33  lea     rax, aDhcpv6iataaddr; "Dhcpv6IataAddr"
0x18000dc3a  mov     [rbp+57h+var_30], rax
0x18000dc3e  lea     rax, aDhcpv6t1; "Dhcpv6T1"
0x18000dc45  mov     [rbp+57h+var_28], rax
0x18000dc49  lea     rax, aDhcpv6t2; "Dhcpv6T2"
0x18000dc50  mov     [rbp+57h+var_20], rax
0x18000dc54  lea     rax, aDhcpv6ianaiaid; "Dhcpv6IanaIaids"
0x18000dc5b  mov     [rbp+57h+var_18], rax
0x18000dc5f  lea     rax, aDhcpv6iataiaid; "Dhcpv6IataIaids"
0x18000dc66  mov     [rbp+57h+var_10], rax
0x18000dc6a  mov     rdx, [rbp+rbx*8+57h+lpValueName]; lpValueName
0x18000dc6f  mov     rcx, rsi; hKey
0x18000dc72  call    cs:__imp_RegDeleteValueW
0x18000dc79  nop     dword ptr [rax+rax+00h]
0x18000dc7e  test    eax, eax
0x18000dc80  jz      loc_18000DD4B
0x18000dc86  test    byte ptr cs:xmmword_1800423E0, 2
0x18000dc8d  jnz     loc_18000DD27
0x18000dc93  inc     rbx
0x18000dc96  cmp     rbx, 9
0x18000dc9a  jnz     short loc_18000DC6A
0x18000dc9c  xor     ebx, ebx
0x18000dc9e  mov     rdx, [rbp+rbx*8+57h+var_50]; lpValueName
0x18000dca3  mov     rcx, rsi; hKey
0x18000dca6  call    cs:__imp_RegDeleteValueW
0x18000dcad  nop     dword ptr [rax+rax+00h]
0x18000dcb2  test    eax, eax
0x18000dcb4  jz      short loc_18000DCE0
0x18000dcb6  test    byte ptr cs:xmmword_1800423E0, 2
0x18000dcbd  jnz     short loc_18000DD06
0x18000dcbf  inc     rbx
0x18000dcc2  cmp     rbx, 9
0x18000dcc6  jnz     short loc_18000DC9E
0x18000dcc8  lea     r11, [rsp+0D0h+var_s0]
0x18000dcd0  xor     eax, eax
0x18000dcd2  mov     rbx, [r11+10h]
0x18000dcd6  mov     rsi, [r11+18h]
0x18000dcda  mov     rsp, r11
0x18000dcdd  pop     rbp
0x18000dcde  retn
0x18000dce0  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000dce7  jz      short loc_18000DCBF
0x18000dce9  mov     r9, [rbp+rbx*8+57h+var_50]
0x18000dcee  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18000dcf5  mov     edx, 48h ; 'H'
0x18000dcfa  mov     ecx, 404h
0x18000dcff  call    WPP_SF_S
0x18000dd04  jmp     short loc_18000DCBF
0x18000dd06  mov     r9, [rbp+rbx*8+57h+var_50]
0x18000dd0b  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18000dd12  mov     edx, 47h ; 'G'
0x18000dd17  mov     [rsp+0D0h+var_B0], eax
0x18000dd1b  mov     ecx, 401h
0x18000dd20  call    WPP_SF_SD
0x18000dd25  jmp     short loc_18000DCBF
0x18000dd27  mov     r9, [rbp+rbx*8+57h+lpValueName]
0x18000dd2c  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18000dd33  mov     edx, 45h ; 'E'
0x18000dd38  mov     [rsp+0D0h+var_B0], eax
0x18000dd3c  mov     ecx, 401h
0x18000dd41  call    WPP_SF_SD
0x18000dd46  jmp     loc_18000DC93
0x18000dd4b  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000dd52  jz      loc_18000DC93
0x18000dd58  mov     r9, [rbp+rbx*8+57h+lpValueName]
0x18000dd5d  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18000dd64  mov     edx, 46h ; 'F'
0x18000dd69  mov     ecx, 404h
0x18000dd6e  call    WPP_SF_S
0x18000dd73  jmp     loc_18000DC93
```
