# DhcpRegReadEnabledDhcp

- ea: `0x180009fa8`
- end: `0x18000a15f`
- name: `DhcpRegReadEnabledDhcp`
- size: `439`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009f00`
- `0x180017f44`
- `0x18002ddd4`

## callees

- `0x180009fa8`
- `0x1800338c0`
- `0x180033900`
- `0x180033970`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a06a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a093`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a06a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a093`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a0d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a0d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a005`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a01a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a005`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a01a`

## pseudocode

```c
__int64 __fastcall DhcpRegReadEnabledDhcp(LPCWSTR lpSubKey, LPCWSTR a2, _DWORD *a3)
{
  unsigned int v6; // ebx
  char v8; // al
  BYTE Data[8]; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+30h] BYREF
  DWORD Type; // [rsp+88h] [rbp+38h] BYREF

  cbData = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  phkResult = 0;
  hKey = 0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_(1028, 20, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids);
  if ( !a3 )
    goto LABEL_4;
  *a3 = 0;
  if ( !a2 )
    goto LABEL_4;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 1u, &phkResult);
  if ( v6 )
    goto LABEL_5;
  v6 = RegOpenKeyExW(phkResult, a2, 0, 1u, &hKey);
  if ( v6 )
    goto LABEL_5;
  cbData = 4;
  v6 = RegQueryValueExW(hKey, L"EnableDhcp", 0, &Type, Data, &cbData);
  if ( v6 )
    goto LABEL_5;
  if ( Type != 4 )
  {
LABEL_4:
    v6 = 87;
    goto LABEL_5;
  }
  v8 = Data[0];
  *a3 = *(_DWORD *)Data;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_SD(1028, 21, (unsigned int)WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids, (_DWORD)a2, v8);
LABEL_5:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 22, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180009fa8  mov     [rsp-18h+arg_0], rbx
0x180009fad  push    rbp
0x180009fae  push    rsi
0x180009faf  push    rdi
0x180009fb0  mov     rbp, rsp
0x180009fb3  sub     rsp, 50h
0x180009fb7  mov     rdi, r8
0x180009fba  mov     [rbp+cbData], 0
0x180009fc1  mov     rsi, rdx
0x180009fc4  mov     [rbp+Type], 0
0x180009fcb  mov     rbx, rcx
0x180009fce  mov     dword ptr [rbp+Data], 0
0x180009fd5  mov     [rbp+var_10], 0
0x180009fdd  mov     [rbp+hKey], 0
0x180009fe5  test    byte ptr cs:xmmword_1800423E0, 10h
0x180009fec  jnz     loc_18000A144
0x180009ff2  test    rdi, rdi
0x180009ff5  jnz     short loc_18000A043
0x180009ff7  mov     ebx, 57h ; 'W'
0x180009ffc  mov     rcx, [rbp+hKey]; hKey
0x18000a000  test    rcx, rcx
0x18000a003  jz      short loc_18000A011
0x18000a005  call    cs:__imp_RegCloseKey
0x18000a00c  nop     dword ptr [rax+rax+00h]
0x18000a011  mov     rcx, [rbp+var_10]; hKey
0x18000a015  test    rcx, rcx
0x18000a018  jz      short loc_18000A026
0x18000a01a  call    cs:__imp_RegCloseKey
0x18000a021  nop     dword ptr [rax+rax+00h]
0x18000a026  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000a02d  jnz     loc_18000A126
0x18000a033  mov     eax, ebx
0x18000a035  mov     rbx, [rsp+50h+arg_0]
0x18000a03a  add     rsp, 50h
0x18000a03e  pop     rdi
0x18000a03f  pop     rsi
0x18000a040  pop     rbp
0x18000a041  retn
0x18000a043  mov     dword ptr [rdi], 0
0x18000a049  test    rsi, rsi
0x18000a04c  jz      short loc_180009FF7
0x18000a04e  lea     rax, [rbp+var_10]
0x18000a052  mov     r9d, 1; samDesired
0x18000a058  xor     r8d, r8d; ulOptions
0x18000a05b  mov     [rsp+50h+phkResult], rax; phkResult
0x18000a060  mov     rdx, rbx; lpSubKey
0x18000a063  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a06a  call    cs:__imp_RegOpenKeyExW
0x18000a071  nop     dword ptr [rax+rax+00h]
0x18000a076  mov     ebx, eax
0x18000a078  test    eax, eax
0x18000a07a  jnz     short loc_180009FFC
0x18000a07c  mov     rcx, [rbp+var_10]; hKey
0x18000a080  lea     rax, [rbp+hKey]
0x18000a084  lea     r9d, [rbx+1]; samDesired
0x18000a088  mov     [rsp+50h+phkResult], rax; phkResult
0x18000a08d  xor     r8d, r8d; ulOptions
0x18000a090  mov     rdx, rsi; lpSubKey
0x18000a093  call    cs:__imp_RegOpenKeyExW
0x18000a09a  nop     dword ptr [rax+rax+00h]
0x18000a09f  mov     ebx, eax
0x18000a0a1  test    eax, eax
0x18000a0a3  jnz     loc_180009FFC
0x18000a0a9  mov     rcx, [rbp+hKey]; hKey
0x18000a0ad  lea     rax, [rbp+cbData]
0x18000a0b1  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000a0b6  lea     r9, [rbp+Type]; lpType
0x18000a0ba  lea     rax, [rbp+Data]
0x18000a0be  mov     [rbp+cbData], 4
0x18000a0c5  xor     r8d, r8d; lpReserved
0x18000a0c8  mov     [rsp+50h+phkResult], rax; lpData
0x18000a0cd  lea     rdx, aEnabledhcp; "EnableDhcp"
0x18000a0d4  call    cs:__imp_RegQueryValueExW
0x18000a0db  nop     dword ptr [rax+rax+00h]
0x18000a0e0  mov     ebx, eax
0x18000a0e2  test    eax, eax
0x18000a0e4  jnz     loc_180009FFC
0x18000a0ea  cmp     [rbp+Type], 4
0x18000a0ee  jnz     loc_180009FF7
0x18000a0f4  mov     eax, dword ptr [rbp+Data]
0x18000a0f7  mov     [rdi], eax
0x18000a0f9  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000a100  jz      loc_180009FFC
0x18000a106  lea     edx, [rbx+15h]
0x18000a109  mov     dword ptr [rsp+50h+phkResult], eax
0x18000a10d  mov     ecx, 404h
0x18000a112  lea     r8, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids
0x18000a119  mov     r9, rsi
0x18000a11c  call    WPP_SF_SD
0x18000a121  jmp     loc_180009FFC
0x18000a126  mov     edx, 16h
0x18000a12b  lea     r8, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids
0x18000a132  mov     ecx, 404h
0x18000a137  mov     r9d, ebx
0x18000a13a  call    WPP_SF_D
0x18000a13f  jmp     loc_18000A033
0x18000a144  mov     edx, 14h
0x18000a149  lea     r8, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids
0x18000a150  mov     ecx, 404h
0x18000a155  call    WPP_SF_
0x18000a15a  jmp     loc_180009FF2
```
