# DhcpRegReadEnabledDhcp

- ea: `0x180002400`
- end: `0x180002599`
- name: `DhcpRegReadEnabledDhcp`
- size: `409`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR, _DWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003240`
- `0x1800034d0`

## callees

- `0x180002400`
- `0x1800082b0`
- `0x1800082d0`
- `0x180008490`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800024b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800024c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800024b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800024c2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002539`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002539`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002475`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000249c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002475`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000249c`

## pseudocode

```c
__int64 __fastcall DhcpRegReadEnabledDhcp(LPCWSTR lpSubKey, LPCWSTR a2, _DWORD *a3)
{
  unsigned int v6; // ebx
  int v8; // ecx
  char v9; // al
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
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_(lpSubKey, 20, WPP_94d5010c5674399d06148e3a91870046_Traceguids);
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
              v9 = Data[0];
              v6 = 0;
              *a3 = *(_DWORD *)Data;
              if ( (xmmword_18000F160 & 0x10) != 0 )
                WPP_SF_SD(v8, 21, (unsigned int)WPP_94d5010c5674399d06148e3a91870046_Traceguids, (_DWORD)a2, v9);
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
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_D(1028, 22, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180002400  mov     rax, rsp
0x180002403  mov     [rax+8], rbx
0x180002407  push    rbp
0x180002408  push    rsi
0x180002409  push    rdi
0x18000240a  sub     rsp, 50h
0x18000240e  xor     ebp, ebp
0x180002410  mov     rdi, r8
0x180002413  mov     [rax+18h], ebp
0x180002416  mov     rsi, rdx
0x180002419  mov     [rax+20h], ebp
0x18000241c  mov     rbx, rcx
0x18000241f  mov     [rax-38h], ebp
0x180002422  mov     [rax-28h], rbp
0x180002426  mov     [rax-30h], rbp
0x18000242a  test    byte ptr cs:xmmword_18000F160, 10h
0x180002431  jz      short loc_180002444
0x180002433  mov     edx, 14h
0x180002438  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18000243f  call    WPP_SF_
0x180002444  test    rdi, rdi
0x180002447  jz      loc_1800024F9
0x18000244d  mov     [rdi], ebp
0x18000244f  test    rsi, rsi
0x180002452  jz      loc_180002585
0x180002458  lea     rax, [rsp+68h+hKey]
0x18000245d  mov     r9d, 1; samDesired
0x180002463  xor     r8d, r8d; ulOptions
0x180002466  mov     [rsp+68h+phkResult], rax; phkResult
0x18000246b  mov     rdx, rbx; lpSubKey
0x18000246e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002475  call    cs:__imp_RegOpenKeyExW
0x18000247b  mov     ebx, eax
0x18000247d  test    eax, eax
0x18000247f  jnz     short loc_1800024A8
0x180002481  mov     rcx, [rsp+68h+hKey]; hKey
0x180002486  lea     rax, [rsp+68h+var_30]
0x18000248b  mov     r9d, 1; samDesired
0x180002491  mov     [rsp+68h+phkResult], rax; phkResult
0x180002496  xor     r8d, r8d; ulOptions
0x180002499  mov     rdx, rsi; lpSubKey
0x18000249c  call    cs:__imp_RegOpenKeyExW
0x1800024a2  mov     ebx, eax
0x1800024a4  test    eax, eax
0x1800024a6  jz      short loc_180002500
0x1800024a8  mov     rcx, [rsp+68h+var_30]; hKey
0x1800024ad  test    rcx, rcx
0x1800024b0  jz      short loc_1800024B8
0x1800024b2  call    cs:__imp_RegCloseKey
0x1800024b8  mov     rcx, [rsp+68h+hKey]; hKey
0x1800024bd  test    rcx, rcx
0x1800024c0  jz      short loc_1800024C8
0x1800024c2  call    cs:__imp_RegCloseKey
0x1800024c8  test    byte ptr cs:xmmword_18000F160, 10h
0x1800024cf  jz      short loc_1800024EA
0x1800024d1  mov     edx, 16h
0x1800024d6  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x1800024dd  mov     ecx, 404h
0x1800024e2  mov     r9d, ebx
0x1800024e5  call    WPP_SF_D
0x1800024ea  mov     eax, ebx
0x1800024ec  mov     rbx, [rsp+68h+arg_0]
0x1800024f1  add     rsp, 50h
0x1800024f5  pop     rdi
0x1800024f6  pop     rsi
0x1800024f7  pop     rbp
0x1800024f8  retn
0x1800024f9  mov     ebx, 57h ; 'W'
0x1800024fe  jmp     short loc_1800024A8
0x180002500  mov     rcx, [rsp+68h+var_30]; hKey
0x180002505  lea     rax, [rsp+68h+cbData]
0x18000250d  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180002512  lea     r9, [rsp+68h+Type]; lpType
0x18000251a  lea     rax, [rsp+68h+Data]
0x18000251f  mov     [rsp+68h+cbData], 4
0x18000252a  xor     r8d, r8d; lpReserved
0x18000252d  mov     [rsp+68h+phkResult], rax; lpData
0x180002532  lea     rdx, ValueName; "EnableDhcp"
0x180002539  call    cs:__imp_RegQueryValueExW
0x18000253f  mov     ebx, eax
0x180002541  test    eax, eax
0x180002543  jnz     loc_1800024A8
0x180002549  cmp     [rsp+68h+Type], 4
0x180002551  jnz     short loc_18000258F
0x180002553  mov     eax, dword ptr [rsp+68h+Data]
0x180002557  mov     ebx, ebp
0x180002559  mov     [rdi], eax
0x18000255b  test    byte ptr cs:xmmword_18000F160, 10h
0x180002562  jz      loc_1800024A8
0x180002568  mov     edx, 15h
0x18000256d  mov     dword ptr [rsp+68h+phkResult], eax
0x180002571  mov     r9, rsi
0x180002574  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18000257b  call    WPP_SF_SD
0x180002580  jmp     loc_1800024A8
0x180002585  mov     ebx, 57h ; 'W'
0x18000258a  jmp     loc_1800024A8
0x18000258f  mov     ebx, 57h ; 'W'
0x180002594  jmp     loc_1800024A8
```
