# GuidToPort

- ea: `0x18002eaf4`
- end: `0x18002ee06`
- name: `GuidToPort`
- size: `786`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18002f370`
- `0x18002f450`
- `0x18002f530`
- `0x18002fba0`

## callees

- `0x1800119a0`
- `0x18001757c`
- `0x1800222f0`
- `0x18002c910`
- `0x18002eaf4`
- `0x18002ff2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002edab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002edab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ed50`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ed97`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ed50`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ed97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ecff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ecff`
- `WS2_32!__imp_htons` at `0x18002ec1e`
- `WS2_32!__imp_htons` at `0x18002ec75`
- `WS2_32!__imp_htons` at `0x18002edc3`
- `WS2_32!__imp_htons` at `0x18002ec1e`
- `WS2_32!__imp_htons` at `0x18002ec75`
- `WS2_32!__imp_htons` at `0x18002edc3`

## string_xrefs

- `0x18002ecb8`: `SYSTEM\CurrentControlSet\Control\ServiceProvider\ServiceTypes\`

## pseudocode

```c
__int64 __fastcall GuidToPort(__int64 a1, _DWORD *a2, u_short *a3, int *a4)
{
  int v7; // ebx
  int v8; // edi
  int v9; // esi
  __int64 v10; // rcx
  _DWORD *v11; // r9
  GUID *v12; // r10
  unsigned int v14; // eax
  u_short v15; // ax
  bool v16; // zf
  u_short v17; // cx
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[256]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ServiceName[256]; // [rsp+250h] [rbp+150h] BYREF

  hKey = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 0;
  if ( a2 )
  {
    v8 = 0;
    v9 = 0;
    LODWORD(v10) = 0;
    if ( !*a2 )
      return 0xFFFFFFFFLL;
    v7 = 1;
    do
    {
      if ( a2[(unsigned int)v10] == 6 )
      {
        v8 = 1;
      }
      else if ( a2[(unsigned int)v10] == 17 )
      {
        v9 = 1;
      }
      v10 = (unsigned int)(v10 + 1);
    }
    while ( a2[v10] );
    if ( !v8 && !v9 )
      return 0xFFFFFFFFLL;
  }
  else
  {
    v7 = 1;
    v8 = 1;
    v9 = 1;
  }
  if ( (unsigned int)GuidEqual(a1, &HostnameGuid) )
  {
    *a3 = 0;
    *v11 = 1;
    return 0;
  }
  v14 = v12->Data1 & 0xFFFF0000;
  if ( v14 == 589824 )
  {
    if ( !v12->Data2
      && v12->Data4[0] == 0xC0
      && !v12->Data4[1]
      && !v12->Data4[2]
      && !v12->Data4[3]
      && !v12->Data4[4]
      && !v12->Data4[5]
      && !v12->Data4[6]
      && v12->Data4[7] == 70 )
    {
      v15 = htons(v12->Data1);
      v16 = v8 == 0;
      goto LABEL_37;
    }
LABEL_39:
    if ( !GetNameByTypeW(v12, ServiceName, 0x100u) )
    {
      StringCbCopyW(pszDest, 0x200u, L"SYSTEM\\CurrentControlSet\\Control\\ServiceProvider\\ServiceTypes\\");
      StringCbCatW(pszDest, 0x200u, ServiceName);
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x20019u, &hKey) )
      {
        cbData = 4;
        *(_DWORD *)Data = -1;
        if ( !v8 || (RegQueryValueExW(hKey, L"TcpPort", 0, &Type, Data, &cbData), *(_DWORD *)Data == -1) )
        {
          if ( v9 )
          {
            cbData = 4;
            RegQueryValueExW(hKey, L"UdpPort", 0, &Type, Data, &cbData);
            v7 = 0;
          }
        }
        RegCloseKey(hKey);
        v17 = *(_WORD *)Data;
        if ( *(_DWORD *)Data != -1 )
        {
          *a4 = v7;
          *a3 = htons(v17);
          return 0;
        }
      }
    }
    return 0xFFFFFFFFLL;
  }
  if ( v14 != 655360
    || v12->Data2
    || v12->Data4[0] != 0xC0
    || v12->Data4[1]
    || v12->Data4[2]
    || v12->Data4[3]
    || v12->Data4[4]
    || v12->Data4[5]
    || v12->Data4[6]
    || v12->Data4[7] != 70 )
  {
    goto LABEL_39;
  }
  v7 = 0;
  v15 = htons(v12->Data1);
  v16 = v9 == 0;
LABEL_37:
  *a3 = v15;
  if ( !v16 )
  {
    *a4 = v7;
    return 0;
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18002eaf4  mov     [rsp-8+arg_8], rbx
0x18002eaf9  push    rbp
0x18002eafa  push    rsi
0x18002eafb  push    rdi
0x18002eafc  push    r12
0x18002eafe  push    r13
0x18002eb00  push    r14
0x18002eb02  push    r15
0x18002eb04  lea     rbp, [rsp-360h]
0x18002eb0c  sub     rsp, 460h
0x18002eb13  mov     rax, cs:__security_cookie
0x18002eb1a  xor     rax, rsp
0x18002eb1d  mov     [rbp+390h+var_40], rax
0x18002eb24  xor     r13d, r13d
0x18002eb27  mov     r15, r9
0x18002eb2a  mov     [rsp+490h+hKey], r13
0x18002eb2f  mov     r14, r8
0x18002eb32  mov     dword ptr [rsp+490h+Data], r13d
0x18002eb37  mov     r10, rcx
0x18002eb3a  mov     [rsp+490h+Type], r13d
0x18002eb3f  mov     [rsp+490h+cbData], r13d
0x18002eb44  test    rdx, rdx
0x18002eb47  jnz     short loc_18002EB52
0x18002eb49  lea     ebx, [rdx+1]
0x18002eb4c  mov     edi, ebx
0x18002eb4e  mov     esi, ebx
0x18002eb50  jmp     short loc_18002EB91
0x18002eb52  mov     edi, r13d
0x18002eb55  mov     esi, r13d
0x18002eb58  mov     ecx, r13d
0x18002eb5b  cmp     [rdx], r13d
0x18002eb5e  jz      loc_18002EDD8
0x18002eb64  mov     ebx, 1
0x18002eb69  mov     eax, ecx
0x18002eb6b  cmp     dword ptr [rdx+rax*4], 6
0x18002eb6f  jnz     short loc_18002EB75
0x18002eb71  mov     edi, ebx
0x18002eb73  jmp     short loc_18002EB7D
0x18002eb75  cmp     dword ptr [rdx+rax*4], 11h
0x18002eb79  jnz     short loc_18002EB7D
0x18002eb7b  mov     esi, ebx
0x18002eb7d  add     ecx, ebx
0x18002eb7f  cmp     [rdx+rcx*4], r13d
0x18002eb83  jnz     short loc_18002EB69
0x18002eb85  test    edi, edi
0x18002eb87  jnz     short loc_18002EB91
0x18002eb89  test    esi, esi
0x18002eb8b  jz      loc_18002EDD8
0x18002eb91  lea     rdx, HostnameGuid
0x18002eb98  mov     rcx, r10
0x18002eb9b  call    GuidEqual
0x18002eba0  test    eax, eax
0x18002eba2  jz      short loc_18002EBB2
0x18002eba4  mov     [r14], r13w
0x18002eba8  mov     [r9], ebx
0x18002ebab  xor     eax, eax
0x18002ebad  jmp     loc_18002EDDB
0x18002ebb2  mov     eax, [r10]
0x18002ebb5  and     eax, 0FFFF0000h
0x18002ebba  cmp     eax, 90000h
0x18002ebbf  jnz     short loc_18002EC2E
0x18002ebc1  cmp     [r10+4], r13w
0x18002ebc6  jnz     loc_18002EC95
0x18002ebcc  cmp     byte ptr [r10+8], 0C0h
0x18002ebd1  jnz     loc_18002EC95
0x18002ebd7  cmp     [r10+9], r13b
0x18002ebdb  jnz     loc_18002EC95
0x18002ebe1  cmp     [r10+0Ah], r13b
0x18002ebe5  jnz     loc_18002EC95
0x18002ebeb  cmp     [r10+0Bh], r13b
0x18002ebef  jnz     loc_18002EC95
0x18002ebf5  cmp     [r10+0Ch], r13b
0x18002ebf9  jnz     loc_18002EC95
0x18002ebff  cmp     [r10+0Dh], r13b
0x18002ec03  jnz     loc_18002EC95
0x18002ec09  cmp     [r10+0Eh], r13b
0x18002ec0d  jnz     loc_18002EC95
0x18002ec13  cmp     byte ptr [r10+0Fh], 46h ; 'F'
0x18002ec18  jnz     short loc_18002EC95
0x18002ec1a  movzx   ecx, word ptr [r10]; hostshort
0x18002ec1e  call    cs:__imp_htons
0x18002ec25  nop     dword ptr [rax+rax+00h]
0x18002ec2a  test    edi, edi
0x18002ec2c  jmp     short loc_18002EC83
0x18002ec2e  cmp     eax, 0A0000h
0x18002ec33  jnz     short loc_18002EC95
0x18002ec35  cmp     [r10+4], r13w
0x18002ec3a  jnz     short loc_18002EC95
0x18002ec3c  cmp     byte ptr [r10+8], 0C0h
0x18002ec41  jnz     short loc_18002EC95
0x18002ec43  cmp     [r10+9], r13b
0x18002ec47  jnz     short loc_18002EC95
0x18002ec49  cmp     [r10+0Ah], r13b
0x18002ec4d  jnz     short loc_18002EC95
0x18002ec4f  cmp     [r10+0Bh], r13b
0x18002ec53  jnz     short loc_18002EC95
0x18002ec55  cmp     [r10+0Ch], r13b
0x18002ec59  jnz     short loc_18002EC95
0x18002ec5b  cmp     [r10+0Dh], r13b
0x18002ec5f  jnz     short loc_18002EC95
0x18002ec61  cmp     [r10+0Eh], r13b
0x18002ec65  jnz     short loc_18002EC95
0x18002ec67  cmp     byte ptr [r10+0Fh], 46h ; 'F'
0x18002ec6c  jnz     short loc_18002EC95
0x18002ec6e  movzx   ecx, word ptr [r10]; hostshort
0x18002ec72  mov     ebx, r13d
0x18002ec75  call    cs:__imp_htons
0x18002ec7c  nop     dword ptr [rax+rax+00h]
0x18002ec81  test    esi, esi
0x18002ec83  mov     [r14], ax
0x18002ec87  jz      loc_18002EDD8
0x18002ec8d  mov     [r15], ebx
0x18002ec90  jmp     loc_18002EBAB
0x18002ec95  mov     r8d, 100h; dwNameLength
0x18002ec9b  lea     rdx, [rbp+390h+ServiceName]; lpServiceName
0x18002eca2  mov     rcx, r10; lpServiceType
0x18002eca5  call    GetNameByTypeW
0x18002ecaa  test    eax, eax
0x18002ecac  jnz     loc_18002EDD8
0x18002ecb2  mov     r12d, 200h
0x18002ecb8  lea     r8, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Ser"...
0x18002ecbf  mov     edx, r12d; cbDest
0x18002ecc2  lea     rcx, [rsp+490h+pszDest]; pszDest
0x18002ecc7  call    StringCbCopyW
0x18002eccc  lea     r8, [rbp+390h+ServiceName]; pszSrc
0x18002ecd3  mov     edx, r12d; cbDest
0x18002ecd6  lea     rcx, [rsp+490h+pszDest]; pszDest
0x18002ecdb  call    StringCbCatW
0x18002ece0  lea     rax, [rsp+490h+hKey]
0x18002ece5  mov     r9d, 20019h; samDesired
0x18002eceb  xor     r8d, r8d; ulOptions
0x18002ecee  mov     [rsp+490h+phkResult], rax; phkResult
0x18002ecf3  lea     rdx, [rsp+490h+pszDest]; lpSubKey
0x18002ecf8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ecff  call    cs:__imp_RegOpenKeyExW
0x18002ed06  nop     dword ptr [rax+rax+00h]
0x18002ed0b  test    eax, eax
0x18002ed0d  jnz     loc_18002EDD8
0x18002ed13  or      r12d, 0FFFFFFFFh
0x18002ed17  mov     [rsp+490h+cbData], 4
0x18002ed1f  mov     dword ptr [rsp+490h+Data], r12d
0x18002ed24  test    edi, edi
0x18002ed26  jz      short loc_18002ED63
0x18002ed28  mov     rcx, [rsp+490h+hKey]; hKey
0x18002ed2d  lea     rax, [rsp+490h+cbData]
0x18002ed32  mov     [rsp+490h+lpcbData], rax; lpcbData
0x18002ed37  lea     r9, [rsp+490h+Type]; lpType
0x18002ed3c  lea     rax, [rsp+490h+Data]
0x18002ed41  xor     r8d, r8d; lpReserved
0x18002ed44  lea     rdx, aTcpport; "TcpPort"
0x18002ed4b  mov     [rsp+490h+phkResult], rax; lpData
0x18002ed50  call    cs:__imp_RegQueryValueExW
0x18002ed57  nop     dword ptr [rax+rax+00h]
0x18002ed5c  cmp     dword ptr [rsp+490h+Data], r12d
0x18002ed61  jnz     short loc_18002EDA6
0x18002ed63  test    esi, esi
0x18002ed65  jz      short loc_18002EDA6
0x18002ed67  mov     rcx, [rsp+490h+hKey]; hKey
0x18002ed6c  lea     rax, [rsp+490h+cbData]
0x18002ed71  mov     [rsp+490h+lpcbData], rax; lpcbData
0x18002ed76  lea     r9, [rsp+490h+Type]; lpType
0x18002ed7b  lea     rax, [rsp+490h+Data]
0x18002ed80  mov     [rsp+490h+cbData], 4
0x18002ed88  xor     r8d, r8d; lpReserved
0x18002ed8b  mov     [rsp+490h+phkResult], rax; lpData
0x18002ed90  lea     rdx, aUdpport; "UdpPort"
0x18002ed97  call    cs:__imp_RegQueryValueExW
0x18002ed9e  nop     dword ptr [rax+rax+00h]
0x18002eda3  mov     ebx, r13d
0x18002eda6  mov     rcx, [rsp+490h+hKey]; hKey
0x18002edab  call    cs:__imp_RegCloseKey
0x18002edb2  nop     dword ptr [rax+rax+00h]
0x18002edb7  mov     ecx, dword ptr [rsp+490h+Data]; hostshort
0x18002edbb  cmp     ecx, r12d
0x18002edbe  jz      short loc_18002EDD8
0x18002edc0  mov     [r15], ebx
0x18002edc3  call    cs:__imp_htons
0x18002edca  nop     dword ptr [rax+rax+00h]
0x18002edcf  mov     [r14], ax
0x18002edd3  jmp     loc_18002EBAB
0x18002edd8  or      eax, 0FFFFFFFFh
0x18002eddb  mov     rcx, [rbp+390h+var_40]
0x18002ede2  xor     rcx, rsp; StackCookie
0x18002ede5  call    __security_check_cookie
0x18002edea  mov     rbx, [rsp+490h+arg_8]
0x18002edf2  add     rsp, 460h
0x18002edf9  pop     r15
0x18002edfb  pop     r14
0x18002edfd  pop     r13
0x18002edff  pop     r12
0x18002ee01  pop     rdi
0x18002ee02  pop     rsi
0x18002ee03  pop     rbp
0x18002ee04  retn
```
