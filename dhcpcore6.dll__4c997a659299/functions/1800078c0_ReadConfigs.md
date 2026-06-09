# ReadConfigs

- ea: `0x1800078c0`
- end: `0x180007a79`
- name: `ReadConfigs`
- size: `441`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006468`

## callees

- `0x1800078c0`
- `0x180033900`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007909`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000796e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800079c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007a2a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007909`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000796e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800079c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007a2a`

## pseudocode

```c
__int64 __fastcall ReadConfigs(HKEY hKey, __int64 a2)
{
  _QWORD *v2; // r14
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  BYTE *lpData; // rsi
  DWORD cbData; // [rsp+68h] [rbp+38h] BYREF
  DWORD Type; // [rsp+70h] [rbp+40h] BYREF
  unsigned int Data; // [rsp+78h] [rbp+48h] BYREF

  v2 = (_QWORD *)(a2 + 8);
  Data = 0;
  Type = 0;
  cbData = 4;
  v5 = RegQueryValueExW(hKey, L"Dhcpv6MaxLeaseExpireTime", 0, &Type, (LPBYTE)(a2 + 8), &cbData);
  v6 = v5;
  if ( v5 == 2 )
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_(1028, 73, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids);
    Type = 0;
    cbData = 4;
    v6 = RegQueryValueExW(hKey, L"Dhcpv6InformationRefreshTime", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( v6 )
    {
      if ( (xmmword_1800423E0 & 0x10) != 0 )
      {
        v7 = 74;
LABEL_17:
        WPP_SF_(1028, v7, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids);
      }
    }
    else
    {
      Type = 0;
      lpData = (BYTE *)(a2 + 16);
      cbData = 4;
      v6 = RegQueryValueExW(hKey, L"Dhcpv6InformationObtainedTime", 0, &Type, lpData, &cbData);
      if ( v6 )
      {
        if ( (xmmword_1800423E0 & 0x10) != 0 )
        {
          v7 = 75;
          goto LABEL_17;
        }
      }
      else
      {
        *v2 = *(_QWORD *)lpData + Data;
      }
    }
  }
  else if ( v5 )
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
    {
      v7 = 77;
      goto LABEL_17;
    }
  }
  else
  {
    Type = 0;
    cbData = 4;
    v6 = RegQueryValueExW(hKey, L"Dhcpv6LeaseObtainedTime", 0, &Type, (LPBYTE)(a2 + 16), &cbData);
    if ( v6 && (xmmword_1800423E0 & 0x10) != 0 )
    {
      v7 = 76;
      goto LABEL_17;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800078c0  push    rbp
0x1800078c2  push    rbx
0x1800078c3  push    rsi
0x1800078c4  push    rdi
0x1800078c5  push    r14
0x1800078c7  mov     rbp, rsp
0x1800078ca  sub     rsp, 30h
0x1800078ce  lea     r14, [rdx+8]
0x1800078d2  mov     [rbp+Data], 0
0x1800078d9  lea     rax, [rbp+cbData]
0x1800078dd  mov     [rbp+Type], 0
0x1800078e4  mov     rsi, rdx
0x1800078e7  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800078ec  lea     r9, [rbp+Type]; lpType
0x1800078f0  mov     [rsp+30h+lpData], r14; lpData
0x1800078f5  xor     r8d, r8d; lpReserved
0x1800078f8  mov     [rbp+cbData], 4
0x1800078ff  lea     rdx, aDhcpv6maxlease; "Dhcpv6MaxLeaseExpireTime"
0x180007906  mov     rdi, rcx
0x180007909  call    cs:__imp_RegQueryValueExW
0x180007910  nop     dword ptr [rax+rax+00h]
0x180007915  mov     ebx, eax
0x180007917  cmp     eax, 2
0x18000791a  jnz     loc_1800079F9
0x180007920  test    byte ptr cs:xmmword_1800423E0, 10h
0x180007927  jz      short loc_18000793D
0x180007929  lea     edx, [rax+47h]
0x18000792c  mov     ecx, 404h
0x180007931  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x180007938  call    WPP_SF_
0x18000793d  lea     rax, [rbp+cbData]
0x180007941  mov     [rbp+Type], 0
0x180007948  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000794d  lea     r9, [rbp+Type]; lpType
0x180007951  lea     rax, [rbp+Data]
0x180007955  mov     [rbp+cbData], 4
0x18000795c  xor     r8d, r8d; lpReserved
0x18000795f  mov     [rsp+30h+lpData], rax; lpData
0x180007964  lea     rdx, aDhcpv6informat; "Dhcpv6InformationRefreshTime"
0x18000796b  mov     rcx, rdi; hKey
0x18000796e  call    cs:__imp_RegQueryValueExW
0x180007975  nop     dword ptr [rax+rax+00h]
0x18000797a  mov     ebx, eax
0x18000797c  test    eax, eax
0x18000797e  jz      short loc_180007997
0x180007980  test    byte ptr cs:xmmword_1800423E0, 10h
0x180007987  jz      loc_180007A6B
0x18000798d  mov     edx, 4Ah ; 'J'
0x180007992  jmp     loc_180007A5A
0x180007997  lea     rax, [rbp+cbData]
0x18000799b  mov     [rbp+Type], 0
0x1800079a2  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800079a7  lea     r9, [rbp+Type]; lpType
0x1800079ab  add     rsi, 10h
0x1800079af  mov     [rbp+cbData], 4
0x1800079b6  xor     r8d, r8d; lpReserved
0x1800079b9  mov     [rsp+30h+lpData], rsi; lpData
0x1800079be  lea     rdx, aDhcpv6informat_0; "Dhcpv6InformationObtainedTime"
0x1800079c5  mov     rcx, rdi; hKey
0x1800079c8  call    cs:__imp_RegQueryValueExW
0x1800079cf  nop     dword ptr [rax+rax+00h]
0x1800079d4  mov     ebx, eax
0x1800079d6  test    eax, eax
0x1800079d8  jz      short loc_1800079EE
0x1800079da  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800079e1  jz      loc_180007A6B
0x1800079e7  mov     edx, 4Bh ; 'K'
0x1800079ec  jmp     short loc_180007A5A
0x1800079ee  mov     eax, [rbp+Data]
0x1800079f1  add     rax, [rsi]
0x1800079f4  mov     [r14], rax
0x1800079f7  jmp     short loc_180007A6B
0x1800079f9  test    eax, eax
0x1800079fb  jnz     short loc_180007A4C
0x1800079fd  lea     rcx, [rbp+cbData]
0x180007a01  mov     [rbp+Type], eax
0x180007a04  mov     [rsp+30h+lpcbData], rcx; lpcbData
0x180007a09  lea     rax, [rsi+10h]
0x180007a0d  mov     rcx, rdi; hKey
0x180007a10  mov     [rbp+cbData], 4
0x180007a17  lea     r9, [rbp+Type]; lpType
0x180007a1b  mov     [rsp+30h+lpData], rax; lpData
0x180007a20  xor     r8d, r8d; lpReserved
0x180007a23  lea     rdx, aDhcpv6leaseobt; "Dhcpv6LeaseObtainedTime"
0x180007a2a  call    cs:__imp_RegQueryValueExW
0x180007a31  nop     dword ptr [rax+rax+00h]
0x180007a36  mov     ebx, eax
0x180007a38  test    eax, eax
0x180007a3a  jz      short loc_180007A6B
0x180007a3c  test    byte ptr cs:xmmword_1800423E0, 10h
0x180007a43  jz      short loc_180007A6B
0x180007a45  mov     edx, 4Ch ; 'L'
0x180007a4a  jmp     short loc_180007A5A
0x180007a4c  test    byte ptr cs:xmmword_1800423E0, 10h
0x180007a53  jz      short loc_180007A6B
0x180007a55  mov     edx, 4Dh ; 'M'
0x180007a5a  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x180007a61  mov     ecx, 404h
0x180007a66  call    WPP_SF_
0x180007a6b  mov     eax, ebx
0x180007a6d  add     rsp, 30h
0x180007a71  pop     r14
0x180007a73  pop     rdi
0x180007a74  pop     rsi
0x180007a75  pop     rbx
0x180007a76  pop     rbp
0x180007a77  retn
```
