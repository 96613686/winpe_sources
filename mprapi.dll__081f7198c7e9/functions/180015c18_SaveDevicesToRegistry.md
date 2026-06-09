# SaveDevicesToRegistry

- ea: `0x180015c18`
- end: `0x180015fc9`
- name: `SaveDevicesToRegistry`
- size: `945`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016308`

## callees

- `0x180015c18`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015f05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015f84`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015f96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015f05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015f84`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015f96`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015ced`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015d2c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015d6d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015dae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015def`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015e30`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015eaf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015ed3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015ef7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015f75`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015ced`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015d2c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015d6d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015dae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015def`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015e30`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015eaf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015ed3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015ef7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015f75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015f4e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015f4e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015e77`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015e77`

## string_xrefs

- `0x180015f40`: `System\CurrentControlSet\Services\PptpProtocol\Parameters`

## pseudocode

```c
__int64 __fastcall SaveDevicesToRegistry(BYTE *lpData, DWORD *a2)
{
  unsigned int v4; // esi
  HKEY v5; // rdi
  DWORD v6; // ecx
  int v7; // r8d
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD v10; // eax
  DWORD v11; // eax
  DWORD v12; // eax
  HKEY v13; // rcx
  HKEY *p_phkResult; // r14
  HKEY v16; // [rsp+50h] [rbp-10h] BYREF
  DWORD Data; // [rsp+A0h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp+50h] BYREF
  HKEY phkResult; // [rsp+B8h] [rbp+58h] BYREF

  hKey = 0;
  v4 = 0;
  v5 = 0;
  do
  {
    if ( !*((_DWORD *)lpData + 73) )
      goto LABEL_51;
    v5 = (HKEY)*((_QWORD *)lpData + 37);
    v16 = v5;
    phkResult = 0;
    if ( *((_DWORD *)lpData + 72) )
    {
      v6 = 0;
      v7 = (unsigned __int16)*((_DWORD *)lpData + 76);
      if ( v7 == 8 )
      {
        v6 = *a2;
      }
      else if ( (unsigned __int16)*((_DWORD *)lpData + 76) == 9 )
      {
        v6 = a2[1];
      }
      else if ( (unsigned __int16)*((_DWORD *)lpData + 76) == 14 )
      {
        v6 = a2[2];
      }
      else
      {
        if ( (unsigned int)(unsigned __int16)*((_DWORD *)lpData + 76) - 15 <= 1 )
          v6 = a2[4];
        if ( v7 != 9 && v7 != 14 && v7 != 15 && v7 != 16 )
          goto LABEL_19;
      }
      if ( *(_DWORD *)lpData > v6 )
        *(_DWORD *)lpData = v6;
LABEL_19:
      RegSetValueExW(v5, L"WanEndpoints", 0, 4u, lpData, 4u);
      if ( *((_WORD *)lpData + 152) == 8 )
      {
        v8 = *(_DWORD *)lpData;
        if ( *(_DWORD *)lpData > *((_DWORD *)lpData + 5) )
        {
          if ( v8 >= *a2 )
            v8 = *a2;
          Data = v8;
          RegSetValueExW(v5, L"MaxWanEndpoints", 0, 4u, (const BYTE *)&Data, 4u);
        }
      }
      if ( *((_WORD *)lpData + 152) == 9 )
      {
        v9 = *(_DWORD *)lpData;
        if ( *(_DWORD *)lpData > *((_DWORD *)lpData + 5) )
        {
          if ( v9 >= a2[1] )
            v9 = a2[1];
          Data = v9;
          RegSetValueExW(v5, L"MaxWanEndpoints", 0, 4u, (const BYTE *)&Data, 4u);
        }
      }
      if ( *((_WORD *)lpData + 152) == 14 )
      {
        v10 = *(_DWORD *)lpData;
        if ( *(_DWORD *)lpData > *((_DWORD *)lpData + 5) )
        {
          if ( v10 >= a2[2] )
            v10 = a2[2];
          Data = v10;
          RegSetValueExW(v5, L"MaxWanEndpoints", 0, 4u, (const BYTE *)&Data, 4u);
        }
      }
      if ( *((_WORD *)lpData + 152) == 15 )
      {
        v11 = *(_DWORD *)lpData;
        if ( *(_DWORD *)lpData > *((_DWORD *)lpData + 5) )
        {
          if ( v11 >= a2[3] )
            v11 = a2[3];
          Data = v11;
          RegSetValueExW(v5, L"MaxWanEndpoints", 0, 4u, (const BYTE *)&Data, 4u);
        }
      }
      if ( *((_WORD *)lpData + 152) == 16 )
      {
        v12 = *(_DWORD *)lpData;
        if ( *(_DWORD *)lpData > *((_DWORD *)lpData + 5) )
        {
          if ( v12 >= a2[4] )
            v12 = a2[4];
          Data = v12;
          RegSetValueExW(v5, L"MaxWanEndpoints", 0, 4u, (const BYTE *)&Data, 4u);
        }
      }
    }
    v13 = v5;
    if ( *((_DWORD *)lpData + 76) )
    {
      p_phkResult = &v16;
      v4 = 0;
    }
    else
    {
      Data = 0;
      p_phkResult = &phkResult;
      v4 = RegCreateKeyExW(v5, L"Clients\\Ras", 0, 0, 0, 0xF003Fu, 0, &phkResult, &Data);
      if ( v4 )
        goto LABEL_49;
      v13 = phkResult;
    }
    RegSetValueExW(v13, L"EnableForRas", 0, 4u, lpData + 4, 4u);
    RegSetValueExW(*p_phkResult, L"EnableForRouting", 0, 4u, lpData + 8, 4u);
    RegSetValueExW(*p_phkResult, L"EnableForOutboundRouting", 0, 4u, lpData + 12, 4u);
LABEL_49:
    if ( *p_phkResult )
    {
      RegCloseKey(*p_phkResult);
      *p_phkResult = 0;
      v5 = v16;
    }
LABEL_51:
    if ( *((_DWORD *)lpData + 72) && *((_DWORD *)lpData + 73) && *((_WORD *)lpData + 152) == 8 )
    {
      v4 = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\PptpProtocol\\Parameters",
             0,
             0xF003Fu,
             &hKey);
      if ( !v4 )
        RegSetValueExW(hKey, L"NumberLineDevices", 0, 4u, lpData, 4u);
      if ( hKey )
      {
        RegCloseKey(hKey);
        hKey = 0;
      }
    }
    if ( v5 )
    {
      RegCloseKey(v5);
      v5 = 0;
    }
    lpData = (BYTE *)*((_QWORD *)lpData + 98);
  }
  while ( lpData );
  return v4;
}

```

## disassembly

```asm
0x180015c18  mov     [rsp-38h+arg_8], rbx
0x180015c1d  push    rbp
0x180015c1e  push    rsi
0x180015c1f  push    rdi
0x180015c20  push    r12
0x180015c22  push    r13
0x180015c24  push    r14
0x180015c26  push    r15
0x180015c28  mov     rbp, rsp
0x180015c2b  sub     rsp, 60h
0x180015c2f  xor     r12d, r12d
0x180015c32  mov     r15, rdx
0x180015c35  mov     rbx, rcx
0x180015c38  mov     [rbp+hKey], r12
0x180015c3c  mov     esi, r12d
0x180015c3f  mov     edi, r12d
0x180015c42  lea     r13d, [r12+4]
0x180015c47  cmp     [rbx+124h], r12d
0x180015c4e  jz      loc_180015F12
0x180015c54  mov     rdi, [rbx+128h]
0x180015c5b  mov     [rbp+var_10], rdi
0x180015c5f  mov     [rbp+arg_18], r12
0x180015c63  cmp     [rbx+120h], r12d
0x180015c6a  jz      loc_180015E36
0x180015c70  mov     r8d, [rbx+130h]
0x180015c77  mov     ecx, r12d
0x180015c7a  movzx   r8d, r8w
0x180015c7e  mov     edx, r8d
0x180015c81  sub     edx, 8
0x180015c84  jz      short loc_180015CCA
0x180015c86  sub     edx, 1
0x180015c89  jz      short loc_180015CC4
0x180015c8b  sub     edx, 5
0x180015c8e  jz      short loc_180015CBE
0x180015c90  sub     edx, 1
0x180015c93  jz      short loc_180015C9A
0x180015c95  cmp     edx, 1
0x180015c98  jnz     short loc_180015C9E
0x180015c9a  mov     ecx, [r15+10h]
0x180015c9e  cmp     r8d, 8
0x180015ca2  jz      short loc_180015CCD
0x180015ca4  cmp     r8d, 9
0x180015ca8  jz      short loc_180015CCD
0x180015caa  cmp     r8d, 0Eh
0x180015cae  jz      short loc_180015CCD
0x180015cb0  cmp     r8d, 0Fh
0x180015cb4  jz      short loc_180015CCD
0x180015cb6  cmp     r8d, 10h
0x180015cba  jnz     short loc_180015CD3
0x180015cbc  jmp     short loc_180015CCD
0x180015cbe  mov     ecx, [r15+8]
0x180015cc2  jmp     short loc_180015CCD
0x180015cc4  mov     ecx, [r15+4]
0x180015cc8  jmp     short loc_180015CCD
0x180015cca  mov     ecx, [r15]
0x180015ccd  cmp     [rbx], ecx
0x180015ccf  jbe     short loc_180015CD3
0x180015cd1  mov     [rbx], ecx
0x180015cd3  mov     [rsp+60h+cbData], r13d; cbData
0x180015cd8  lea     rdx, c_szWanEndPoints; "WanEndpoints"
0x180015cdf  mov     r9d, r13d; dwType
0x180015ce2  mov     [rsp+60h+lpData], rbx; lpData
0x180015ce7  xor     r8d, r8d; Reserved
0x180015cea  mov     rcx, rdi; hKey
0x180015ced  call    cs:__imp_RegSetValueExW
0x180015cf3  cmp     word ptr [rbx+130h], 8
0x180015cfb  jnz     short loc_180015D32
0x180015cfd  mov     eax, [rbx]
0x180015cff  cmp     eax, [rbx+14h]
0x180015d02  jbe     short loc_180015D32
0x180015d04  cmp     eax, [r15]
0x180015d07  lea     rdx, c_szMaxWanEndPoints; "MaxWanEndpoints"
0x180015d0e  mov     [rsp+60h+cbData], r13d; cbData
0x180015d13  mov     r9d, r13d; dwType
0x180015d16  cmovnb  eax, [r15]
0x180015d1a  mov     rcx, rdi; hKey
0x180015d1d  mov     [rbp+Data], eax
0x180015d20  xor     r8d, r8d; Reserved
0x180015d23  lea     rax, [rbp+Data]
0x180015d27  mov     [rsp+60h+lpData], rax; lpData
0x180015d2c  call    cs:__imp_RegSetValueExW
0x180015d32  cmp     word ptr [rbx+130h], 9
0x180015d3a  jnz     short loc_180015D73
0x180015d3c  mov     eax, [rbx]
0x180015d3e  cmp     eax, [rbx+14h]
0x180015d41  jbe     short loc_180015D73
0x180015d43  cmp     eax, [r15+4]
0x180015d47  lea     rdx, c_szMaxWanEndPoints; "MaxWanEndpoints"
0x180015d4e  mov     [rsp+60h+cbData], r13d; cbData
0x180015d53  mov     r9d, r13d; dwType
0x180015d56  cmovnb  eax, [r15+4]
0x180015d5b  mov     rcx, rdi; hKey
0x180015d5e  mov     [rbp+Data], eax
0x180015d61  xor     r8d, r8d; Reserved
0x180015d64  lea     rax, [rbp+Data]
0x180015d68  mov     [rsp+60h+lpData], rax; lpData
0x180015d6d  call    cs:__imp_RegSetValueExW
0x180015d73  cmp     word ptr [rbx+130h], 0Eh
0x180015d7b  jnz     short loc_180015DB4
0x180015d7d  mov     eax, [rbx]
0x180015d7f  cmp     eax, [rbx+14h]
0x180015d82  jbe     short loc_180015DB4
0x180015d84  cmp     eax, [r15+8]
0x180015d88  lea     rdx, c_szMaxWanEndPoints; "MaxWanEndpoints"
0x180015d8f  mov     [rsp+60h+cbData], r13d; cbData
0x180015d94  mov     r9d, r13d; dwType
0x180015d97  cmovnb  eax, [r15+8]
0x180015d9c  mov     rcx, rdi; hKey
0x180015d9f  mov     [rbp+Data], eax
0x180015da2  xor     r8d, r8d; Reserved
0x180015da5  lea     rax, [rbp+Data]
0x180015da9  mov     [rsp+60h+lpData], rax; lpData
0x180015dae  call    cs:__imp_RegSetValueExW
0x180015db4  cmp     word ptr [rbx+130h], 0Fh
0x180015dbc  jnz     short loc_180015DF5
0x180015dbe  mov     eax, [rbx]
0x180015dc0  cmp     eax, [rbx+14h]
0x180015dc3  jbe     short loc_180015DF5
0x180015dc5  cmp     eax, [r15+0Ch]
0x180015dc9  lea     rdx, c_szMaxWanEndPoints; "MaxWanEndpoints"
0x180015dd0  mov     [rsp+60h+cbData], r13d; cbData
0x180015dd5  mov     r9d, r13d; dwType
0x180015dd8  cmovnb  eax, [r15+0Ch]
0x180015ddd  mov     rcx, rdi; hKey
0x180015de0  mov     [rbp+Data], eax
0x180015de3  xor     r8d, r8d; Reserved
0x180015de6  lea     rax, [rbp+Data]
0x180015dea  mov     [rsp+60h+lpData], rax; lpData
0x180015def  call    cs:__imp_RegSetValueExW
0x180015df5  cmp     word ptr [rbx+130h], 10h
0x180015dfd  jnz     short loc_180015E36
0x180015dff  mov     eax, [rbx]
0x180015e01  cmp     eax, [rbx+14h]
0x180015e04  jbe     short loc_180015E36
0x180015e06  cmp     eax, [r15+10h]
0x180015e0a  lea     rdx, c_szMaxWanEndPoints; "MaxWanEndpoints"
0x180015e11  mov     [rsp+60h+cbData], r13d; cbData
0x180015e16  mov     r9d, r13d; dwType
0x180015e19  cmovnb  eax, [r15+10h]
0x180015e1e  mov     rcx, rdi; hKey
0x180015e21  mov     [rbp+Data], eax
0x180015e24  xor     r8d, r8d; Reserved
0x180015e27  lea     rax, [rbp+Data]
0x180015e2b  mov     [rsp+60h+lpData], rax; lpData
0x180015e30  call    cs:__imp_RegSetValueExW
0x180015e36  mov     rcx, rdi; hKey
0x180015e39  cmp     [rbx+130h], r12d
0x180015e40  jnz     short loc_180015E8D
0x180015e42  lea     rax, [rbp+Data]
0x180015e46  mov     [rbp+Data], r12d
0x180015e4a  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x180015e4f  lea     rdx, c_szClientsRasKey; "Clients\\Ras"
0x180015e56  lea     rax, [rbp+arg_18]
0x180015e5a  xor     r9d, r9d; lpClass
0x180015e5d  mov     [rsp+60h+phkResult], rax; phkResult
0x180015e62  xor     r8d, r8d; Reserved
0x180015e65  mov     [rsp+60h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180015e6a  mov     [rsp+60h+cbData], 0F003Fh; samDesired
0x180015e72  mov     dword ptr [rsp+60h+lpData], r12d; dwOptions
0x180015e77  call    cs:__imp_RegCreateKeyExW
0x180015e7d  lea     r14, [rbp+arg_18]
0x180015e81  mov     esi, eax
0x180015e83  test    eax, eax
0x180015e85  jnz     short loc_180015EFD
0x180015e87  mov     rcx, [rbp+arg_18]
0x180015e8b  jmp     short loc_180015E94
0x180015e8d  lea     r14, [rbp+var_10]
0x180015e91  mov     esi, r12d
0x180015e94  lea     rax, [rbx+4]
0x180015e98  mov     [rsp+60h+cbData], r13d; cbData
0x180015e9d  mov     r9d, r13d; dwType
0x180015ea0  mov     [rsp+60h+lpData], rax; lpData
0x180015ea5  xor     r8d, r8d; Reserved
0x180015ea8  lea     rdx, c_szEnableForRas; "EnableForRas"
0x180015eaf  call    cs:__imp_RegSetValueExW
0x180015eb5  mov     rcx, [r14]; hKey
0x180015eb8  lea     rax, [rbx+8]
0x180015ebc  mov     [rsp+60h+cbData], r13d; cbData
0x180015ec1  lea     rdx, c_szEnableForRouting; "EnableForRouting"
0x180015ec8  mov     r9d, r13d; dwType
0x180015ecb  mov     [rsp+60h+lpData], rax; lpData
0x180015ed0  xor     r8d, r8d; Reserved
0x180015ed3  call    cs:__imp_RegSetValueExW
0x180015ed9  mov     rcx, [r14]; hKey
0x180015edc  lea     rax, [rbx+0Ch]
0x180015ee0  mov     [rsp+60h+cbData], r13d; cbData
0x180015ee5  lea     rdx, c_szEnableForOutboundRouting; "EnableForOutboundRouting"
0x180015eec  mov     r9d, r13d; dwType
0x180015eef  mov     [rsp+60h+lpData], rax; lpData
0x180015ef4  xor     r8d, r8d; Reserved
0x180015ef7  call    cs:__imp_RegSetValueExW
0x180015efd  mov     rcx, [r14]; hKey
0x180015f00  test    rcx, rcx
0x180015f03  jz      short loc_180015F12
0x180015f05  call    cs:__imp_RegCloseKey
0x180015f0b  mov     [r14], r12
0x180015f0e  mov     rdi, [rbp+var_10]
0x180015f12  cmp     [rbx+120h], r12d
0x180015f19  jz      short loc_180015F8E
0x180015f1b  cmp     [rbx+124h], r12d
0x180015f22  jz      short loc_180015F8E
0x180015f24  cmp     word ptr [rbx+130h], 8
0x180015f2c  jnz     short loc_180015F8E
0x180015f2e  lea     rax, [rbp+hKey]
0x180015f32  mov     r9d, 0F003Fh; samDesired
0x180015f38  xor     r8d, r8d; ulOptions
0x180015f3b  mov     [rsp+60h+lpData], rax; phkResult
0x180015f40  lea     rdx, c_szRegKeyPptpProtocolParam; "System\\CurrentControlSet\\Services\\Pp"...
0x180015f47  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015f4e  call    cs:__imp_RegOpenKeyExW
0x180015f54  mov     esi, eax
0x180015f56  test    eax, eax
0x180015f58  jnz     short loc_180015F7B
0x180015f5a  mov     rcx, [rbp+hKey]; hKey
0x180015f5e  lea     rdx, c_szRegValNumberLineDevices; "NumberLineDevices"
0x180015f65  mov     [rsp+60h+cbData], r13d; cbData
0x180015f6a  mov     r9d, r13d; dwType
0x180015f6d  xor     r8d, r8d; Reserved
0x180015f70  mov     [rsp+60h+lpData], rbx; lpData
0x180015f75  call    cs:__imp_RegSetValueExW
0x180015f7b  mov     rcx, [rbp+hKey]; hKey
0x180015f7f  test    rcx, rcx
0x180015f82  jz      short loc_180015F8E
0x180015f84  call    cs:__imp_RegCloseKey
0x180015f8a  mov     [rbp+hKey], r12
0x180015f8e  test    rdi, rdi
0x180015f91  jz      short loc_180015F9F
0x180015f93  mov     rcx, rdi; hKey
0x180015f96  call    cs:__imp_RegCloseKey
0x180015f9c  mov     rdi, r12
0x180015f9f  mov     rbx, [rbx+310h]
0x180015fa6  test    rbx, rbx
0x180015fa9  jnz     loc_180015C47
0x180015faf  mov     rbx, [rsp+60h+arg_8]
0x180015fb7  mov     eax, esi
0x180015fb9  add     rsp, 60h
0x180015fbd  pop     r15
0x180015fbf  pop     r14
0x180015fc1  pop     r13
0x180015fc3  pop     r12
0x180015fc5  pop     rdi
0x180015fc6  pop     rsi
0x180015fc7  pop     rbp
0x180015fc8  retn
```
