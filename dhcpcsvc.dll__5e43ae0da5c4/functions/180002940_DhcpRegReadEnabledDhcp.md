# DhcpRegReadEnabledDhcp

- ea: `0x180002940`
- end: `0x180002ade`
- name: `DhcpRegReadEnabledDhcp`
- size: `414`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004170`

## callees

- `0x180002940`
- `0x180012850`
- `0x180012a00`
- `0x180012b80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800029ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800029e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800029ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800029e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002a26`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002a26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002a3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002a4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002a3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002a4c`

## pseudocode

```c
__int64 __fastcall DhcpRegReadEnabledDhcp(LPCWSTR lpSubKey, LPCWSTR a2, _DWORD *a3)
{
  unsigned int v6; // ebx
  char v8; // al
  BYTE Data[8]; // [rsp+30h] [rbp-38h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+18h] BYREF
  DWORD Type; // [rsp+88h] [rbp+20h] BYREF

  cbData = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  hKey = 0;
  phkResult = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_(1028, 20, WPP_94d5010c5674399d06148e3a91870046_Traceguids);
  if ( a3 )
  {
    *a3 = 0;
    if ( a2 )
    {
      v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 1u, &hKey);
      if ( !v6 )
      {
        v6 = RegOpenKeyExW(hKey, a2, 0, 1u, &phkResult);
        if ( !v6 )
        {
          cbData = 4;
          v6 = RegQueryValueExW(phkResult, L"EnableDhcp", 0, &Type, Data, &cbData);
          if ( !v6 )
          {
            if ( Type == 4 )
            {
              v8 = Data[0];
              v6 = 0;
              *a3 = *(_DWORD *)Data;
              if ( (xmmword_18001E1E0 & 0x10) != 0 )
                WPP_SF_SD(1028, 21, (unsigned int)WPP_94d5010c5674399d06148e3a91870046_Traceguids, (_DWORD)a2, v8);
            }
            else
            {
              v6 = 87;
            }
          }
        }
      }
    }
    else
    {
      v6 = 87;
    }
  }
  else
  {
    v6 = 87;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 22, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180002940  mov     rax, rsp
0x180002943  mov     [rax+8], rbx
0x180002947  push    rbp
0x180002948  push    rsi
0x180002949  push    rdi
0x18000294a  sub     rsp, 50h
0x18000294e  xor     ebp, ebp
0x180002950  mov     rdi, r8
0x180002953  mov     [rax+18h], ebp
0x180002956  mov     rsi, rdx
0x180002959  mov     [rax+20h], ebp
0x18000295c  mov     rbx, rcx
0x18000295f  mov     [rax-38h], ebp
0x180002962  mov     [rax-28h], rbp
0x180002966  mov     [rax-30h], rbp
0x18000296a  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180002971  jz      short loc_180002989
0x180002973  mov     edx, 14h
0x180002978  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18000297f  mov     ecx, 404h
0x180002984  call    WPP_SF_
0x180002989  test    rdi, rdi
0x18000298c  jz      loc_180002AC0
0x180002992  mov     [rdi], ebp
0x180002994  test    rsi, rsi
0x180002997  jz      loc_180002AD4
0x18000299d  lea     rax, [rsp+68h+hKey]
0x1800029a2  mov     r9d, 1; samDesired
0x1800029a8  xor     r8d, r8d; ulOptions
0x1800029ab  mov     [rsp+68h+phkResult], rax; phkResult
0x1800029b0  mov     rdx, rbx; lpSubKey
0x1800029b3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800029ba  call    cs:__imp_RegOpenKeyExW
0x1800029c0  mov     ebx, eax
0x1800029c2  test    eax, eax
0x1800029c4  jnz     short loc_180002A32
0x1800029c6  mov     rcx, [rsp+68h+hKey]; hKey
0x1800029cb  lea     rax, [rsp+68h+var_30]
0x1800029d0  mov     r9d, 1; samDesired
0x1800029d6  mov     [rsp+68h+phkResult], rax; phkResult
0x1800029db  xor     r8d, r8d; ulOptions
0x1800029de  mov     rdx, rsi; lpSubKey
0x1800029e1  call    cs:__imp_RegOpenKeyExW
0x1800029e7  mov     ebx, eax
0x1800029e9  test    eax, eax
0x1800029eb  jnz     short loc_180002A32
0x1800029ed  mov     rcx, [rsp+68h+var_30]; hKey
0x1800029f2  lea     rax, [rsp+68h+cbData]
0x1800029fa  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800029ff  lea     r9, [rsp+68h+Type]; lpType
0x180002a07  lea     rax, [rsp+68h+Data]
0x180002a0c  mov     [rsp+68h+cbData], 4
0x180002a17  xor     r8d, r8d; lpReserved
0x180002a1a  mov     [rsp+68h+phkResult], rax; lpData
0x180002a1f  lea     rdx, ValueName; "EnableDhcp"
0x180002a26  call    cs:__imp_RegQueryValueExW
0x180002a2c  mov     ebx, eax
0x180002a2e  test    eax, eax
0x180002a30  jz      short loc_180002A83
0x180002a32  mov     rcx, [rsp+68h+var_30]; hKey
0x180002a37  test    rcx, rcx
0x180002a3a  jz      short loc_180002A42
0x180002a3c  call    cs:__imp_RegCloseKey
0x180002a42  mov     rcx, [rsp+68h+hKey]; hKey
0x180002a47  test    rcx, rcx
0x180002a4a  jz      short loc_180002A52
0x180002a4c  call    cs:__imp_RegCloseKey
0x180002a52  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180002a59  jz      short loc_180002A74
0x180002a5b  mov     edx, 16h
0x180002a60  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x180002a67  mov     ecx, 404h
0x180002a6c  mov     r9d, ebx
0x180002a6f  call    WPP_SF_d
0x180002a74  mov     eax, ebx
0x180002a76  mov     rbx, [rsp+68h+arg_0]
0x180002a7b  add     rsp, 50h
0x180002a7f  pop     rdi
0x180002a80  pop     rsi
0x180002a81  pop     rbp
0x180002a82  retn
0x180002a83  cmp     [rsp+68h+Type], 4
0x180002a8b  jnz     short loc_180002ACA
0x180002a8d  mov     eax, dword ptr [rsp+68h+Data]
0x180002a91  mov     ebx, ebp
0x180002a93  mov     [rdi], eax
0x180002a95  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180002a9c  jz      short loc_180002A32
0x180002a9e  mov     edx, 15h
0x180002aa3  mov     dword ptr [rsp+68h+phkResult], eax
0x180002aa7  mov     ecx, 404h
0x180002aac  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x180002ab3  mov     r9, rsi
0x180002ab6  call    WPP_SF_SD
0x180002abb  jmp     loc_180002A32
0x180002ac0  mov     ebx, 57h ; 'W'
0x180002ac5  jmp     loc_180002A32
0x180002aca  mov     ebx, 57h ; 'W'
0x180002acf  jmp     loc_180002A32
0x180002ad4  mov     ebx, 57h ; 'W'
0x180002ad9  jmp     loc_180002A32
```
