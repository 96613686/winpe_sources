# acmdDriverConfigInit

- ea: `0x180005ce4`
- end: `0x180005f14`
- name: `acmdDriverConfigInit`
- size: `560`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800020d0`

## callees

- `0x180005ce4`
- `0x180005f1c`
- `0x180006328`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005da6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005da6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005d69`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005d9c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005d69`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005d9c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005df9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005e4c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005e9b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005df9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005e4c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005e9b`

## pseudocode

```c
__int64 __fastcall acmdDriverConfigInit(__int64 a1, const WCHAR *a2)
{
  HKEY *phkResult; // r15
  HKEY v5; // rcx
  _DWORD *v6; // r14
  int *v7; // rsi
  int v8; // r12d
  int v9; // eax
  HKEY v10; // rcx
  HKEY v11; // rcx
  int v12; // eax
  int v13; // eax
  int v14; // ecx
  int v16; // [rsp+50h] [rbp-10h] BYREF
  DWORD cbData[3]; // [rsp+54h] [rbp-Ch] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+48h] BYREF
  int Data; // [rsp+B0h] [rbp+50h] BYREF
  int v20; // [rsp+B8h] [rbp+58h] BYREF

  v20 = 0;
  v16 = 0;
  if ( !a2 )
  {
    *(_DWORD *)(a1 + 56) = 0;
    *(_DWORD *)(a1 + 60) = 1;
    *(_DWORD *)(a1 + 64) = 50;
    return 1;
  }
  phkResult = (HKEY *)(a1 + 48);
  if ( !*(_QWORD *)(a1 + 48) )
  {
    hKey = 0;
    if ( !RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Multimedia\\", 0, 0, 0, 4u, 0, &hKey, 0) )
    {
      RegCreateKeyExW(hKey, a2, 0, 0, 0, 0xBu, 0, phkResult, 0);
      RegCloseKey(hKey);
    }
  }
  v5 = *phkResult;
  if ( *phkResult )
  {
    LODWORD(hKey) = -5;
    cbData[0] = 4;
    Data = 0;
    v8 = 2457;
    if ( RegQueryValueExW(v5, L"MaxRTEncodeSetting", 0, (LPDWORD)&hKey, (LPBYTE)&Data, cbData)
      || (v9 = Data, (_DWORD)hKey != 4) )
    {
      v9 = 2457;
    }
    v10 = *phkResult;
    v6 = (_DWORD *)(a1 + 56);
    *(_DWORD *)(a1 + 56) = v9;
    LODWORD(hKey) = -5;
    cbData[0] = 4;
    Data = 0;
    if ( !RegQueryValueExW(v10, L"MaxRTDecodeSetting", 0, (LPDWORD)&hKey, (LPBYTE)&Data, cbData) && (_DWORD)hKey == 4 )
      v8 = Data;
    v11 = *phkResult;
    v7 = (int *)(a1 + 60);
    *(_DWORD *)(a1 + 60) = v8;
    LODWORD(hKey) = -5;
    cbData[0] = 4;
    Data = 0;
    if ( RegQueryValueExW(v11, L"PercentCPU", 0, (LPDWORD)&hKey, (LPBYTE)&Data, cbData)
      || (v12 = Data, (_DWORD)hKey != 4) )
    {
      v12 = 50;
    }
    *(_DWORD *)(a1 + 64) = v12;
    if ( v12 )
      goto LABEL_19;
  }
  else
  {
    v6 = (_DWORD *)(a1 + 56);
    v7 = (int *)(a1 + 60);
    *(_DWORD *)(a1 + 56) = 0;
    *(_DWORD *)(a1 + 60) = 1;
  }
  *(_DWORD *)(a1 + 64) = 50;
LABEL_19:
  if ( *v6 >= 6u || (unsigned int)*v7 >= 6 )
  {
    if ( (unsigned int)configAutoConfig(a1, &v20, &v16) )
    {
      v13 = 0;
      v14 = 1;
    }
    else
    {
      v13 = v20;
      v14 = v16;
    }
    *v7 = v14;
    *v6 = v13;
    configWriteConfiguration(a1);
  }
  return 1;
}

```

## disassembly

```asm
0x180005ce4  mov     [rsp-38h+arg_0], rbx
0x180005ce9  push    rbp
0x180005cea  push    rsi
0x180005ceb  push    rdi
0x180005cec  push    r12
0x180005cee  push    r13
0x180005cf0  push    r14
0x180005cf2  push    r15
0x180005cf4  mov     rbp, rsp
0x180005cf7  sub     rsp, 60h
0x180005cfb  xor     r13d, r13d
0x180005cfe  mov     rdi, rdx
0x180005d01  mov     [rbp+arg_18], r13d
0x180005d05  mov     rbx, rcx
0x180005d08  mov     [rbp+var_10], r13d
0x180005d0c  test    rdx, rdx
0x180005d0f  jnz     short loc_180005D27
0x180005d11  lea     edi, [rdx+1]
0x180005d14  mov     [rcx+38h], r13d
0x180005d18  mov     [rcx+3Ch], edi
0x180005d1b  mov     dword ptr [rcx+40h], 32h ; '2'
0x180005d22  jmp     loc_180005EFA
0x180005d27  lea     r15, [rcx+30h]
0x180005d2b  mov     esi, 4
0x180005d30  cmp     [r15], r13
0x180005d33  jnz     short loc_180005DAC
0x180005d35  mov     [rsp+60h+lpdwDisposition], r13; lpdwDisposition
0x180005d3a  lea     rax, [rbp+hKey]
0x180005d3e  mov     [rsp+60h+phkResult], rax; phkResult
0x180005d43  lea     rdx, gszMultimediaKey; "Software\\Microsoft\\Multimedia\\"
0x180005d4a  mov     [rsp+60h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180005d4f  xor     r9d, r9d; lpClass
0x180005d52  mov     [rsp+60h+samDesired], esi; samDesired
0x180005d56  xor     r8d, r8d; Reserved
0x180005d59  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180005d60  mov     [rsp+60h+dwOptions], r13d; dwOptions
0x180005d65  mov     [rbp+hKey], r13
0x180005d69  call    cs:__imp_RegCreateKeyExW
0x180005d6f  test    eax, eax
0x180005d71  jnz     short loc_180005DAC
0x180005d73  mov     rcx, [rbp+hKey]; hKey
0x180005d77  xor     r9d, r9d; lpClass
0x180005d7a  mov     [rsp+60h+lpdwDisposition], r13; lpdwDisposition
0x180005d7f  xor     r8d, r8d; Reserved
0x180005d82  mov     [rsp+60h+phkResult], r15; phkResult
0x180005d87  mov     rdx, rdi; lpSubKey
0x180005d8a  mov     [rsp+60h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180005d8f  mov     [rsp+60h+samDesired], 0Bh; samDesired
0x180005d97  mov     [rsp+60h+dwOptions], r13d; dwOptions
0x180005d9c  call    cs:__imp_RegCreateKeyExW
0x180005da2  mov     rcx, [rbp+hKey]; hKey
0x180005da6  call    cs:__imp_RegCloseKey
0x180005dac  mov     rcx, [r15]; hKey
0x180005daf  mov     edi, 1
0x180005db4  test    rcx, rcx
0x180005db7  jnz     short loc_180005DCB
0x180005db9  lea     r14, [rbx+38h]
0x180005dbd  lea     rsi, [rbx+3Ch]
0x180005dc1  mov     [r14], r13d
0x180005dc4  mov     [rsi], edi
0x180005dc6  jmp     loc_180005EBA
0x180005dcb  lea     rax, [rbp+cbData]
0x180005dcf  mov     dword ptr [rbp+hKey], 0FFFFFFFBh
0x180005dd6  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x180005ddb  lea     r9, [rbp+hKey]; lpType
0x180005ddf  lea     rax, [rbp+Data]
0x180005de3  mov     [rbp+cbData], esi
0x180005de6  xor     r8d, r8d; lpReserved
0x180005de9  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180005dee  lea     rdx, gszMaxRTEncodeSetting; "MaxRTEncodeSetting"
0x180005df5  mov     [rbp+Data], r13d
0x180005df9  call    cs:__imp_RegQueryValueExW
0x180005dff  mov     r12d, 999h
0x180005e05  test    eax, eax
0x180005e07  jnz     short loc_180005E11
0x180005e09  mov     eax, [rbp+Data]
0x180005e0c  cmp     dword ptr [rbp+hKey], esi
0x180005e0f  jz      short loc_180005E14
0x180005e11  mov     eax, r12d
0x180005e14  mov     rcx, [r15]; hKey
0x180005e17  lea     r14, [rbx+38h]
0x180005e1b  mov     [r14], eax
0x180005e1e  lea     r9, [rbp+hKey]; lpType
0x180005e22  lea     rax, [rbp+cbData]
0x180005e26  mov     dword ptr [rbp+hKey], 0FFFFFFFBh
0x180005e2d  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x180005e32  lea     rdx, gszMaxRTDecodeSetting; "MaxRTDecodeSetting"
0x180005e39  lea     rax, [rbp+Data]
0x180005e3d  mov     [rbp+cbData], esi
0x180005e40  xor     r8d, r8d; lpReserved
0x180005e43  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180005e48  mov     [rbp+Data], r13d
0x180005e4c  call    cs:__imp_RegQueryValueExW
0x180005e52  test    eax, eax
0x180005e54  jnz     short loc_180005E5F
0x180005e56  cmp     dword ptr [rbp+hKey], esi
0x180005e59  jnz     short loc_180005E5F
0x180005e5b  mov     r12d, [rbp+Data]
0x180005e5f  mov     rcx, [r15]; hKey
0x180005e62  lea     rax, [rbp+cbData]
0x180005e66  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x180005e6b  lea     rsi, [rbx+3Ch]
0x180005e6f  lea     rax, [rbp+Data]
0x180005e73  mov     [rsi], r12d
0x180005e76  lea     r9, [rbp+hKey]; lpType
0x180005e7a  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180005e7f  xor     r8d, r8d; lpReserved
0x180005e82  mov     dword ptr [rbp+hKey], 0FFFFFFFBh
0x180005e89  lea     rdx, gszPercentCPU; "PercentCPU"
0x180005e90  mov     [rbp+cbData], 4
0x180005e97  mov     [rbp+Data], r13d
0x180005e9b  call    cs:__imp_RegQueryValueExW
0x180005ea1  test    eax, eax
0x180005ea3  jnz     short loc_180005EAE
0x180005ea5  cmp     dword ptr [rbp+hKey], 4
0x180005ea9  mov     eax, [rbp+Data]
0x180005eac  jz      short loc_180005EB3
0x180005eae  mov     eax, 32h ; '2'
0x180005eb3  mov     [rbx+40h], eax
0x180005eb6  test    eax, eax
0x180005eb8  jnz     short loc_180005EC1
0x180005eba  mov     dword ptr [rbx+40h], 32h ; '2'
0x180005ec1  cmp     dword ptr [r14], 6
0x180005ec5  jnb     short loc_180005ECC
0x180005ec7  cmp     dword ptr [rsi], 6
0x180005eca  jb      short loc_180005EFA
0x180005ecc  lea     r8, [rbp+var_10]
0x180005ed0  mov     rcx, rbx
0x180005ed3  lea     rdx, [rbp+arg_18]
0x180005ed7  call    configAutoConfig
0x180005edc  test    eax, eax
0x180005ede  jz      short loc_180005EE7
0x180005ee0  mov     eax, r13d
0x180005ee3  mov     ecx, edi
0x180005ee5  jmp     short loc_180005EED
0x180005ee7  mov     eax, [rbp+arg_18]
0x180005eea  mov     ecx, [rbp+var_10]
0x180005eed  mov     [rsi], ecx
0x180005eef  mov     rcx, rbx
0x180005ef2  mov     [r14], eax
0x180005ef5  call    configWriteConfiguration
0x180005efa  mov     rbx, [rsp+60h+arg_0]
0x180005f02  mov     eax, edi
0x180005f04  add     rsp, 60h
0x180005f08  pop     r15
0x180005f0a  pop     r14
0x180005f0c  pop     r13
0x180005f0e  pop     r12
0x180005f10  pop     rdi
0x180005f11  pop     rsi
0x180005f12  pop     rbp
0x180005f13  retn
```
