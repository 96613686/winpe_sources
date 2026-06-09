# I_CheckIsTestRootAllowed

- ea: `0x180063d80`
- end: `0x180063ea3`
- name: `I_CheckIsTestRootAllowed`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x180063a30`

## callees

- `0x180063d80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063dfb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063e2d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063dfb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063e2d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180063e63`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180063e63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063e83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063e92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063e83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063e92`

## pseudocode

```c
__int64 __fastcall I_CheckIsTestRootAllowed(unsigned int a1)
{
  unsigned int v1; // edi
  unsigned int v2; // ebx
  int v3; // esi
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  int Data; // [rsp+68h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+38h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+40h] BYREF

  phkResult = 0;
  v1 = a1;
  hKey = 0;
  cbData = 0;
  Data = 0;
  if ( a1 == -1 )
  {
    v3 = 2;
    v1 = 0;
    goto LABEL_7;
  }
  if ( a1 < 2 )
  {
    v3 = a1 + 1;
    if ( __OFSUB__(a1, a1 + 1) )
    {
LABEL_9:
      v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup", 0, 0x20019u, &hKey);
      if ( !v2 )
      {
        cbData = 4;
        v2 = RegQueryValueExW(hKey, L"SystemSetupInProgress", 0, 0, (LPBYTE)&Data, &cbData);
        if ( !v2 && !Data )
          v2 = -2146762487;
      }
    }
    else
    {
LABEL_7:
      while ( 1 )
      {
        v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, off_180119410[v1], 0, 0x20019u, &phkResult);
        if ( !v2 )
          break;
        if ( (int)++v1 >= v3 )
          goto LABEL_9;
      }
    }
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    return 87;
  }
  return v2;
}

```

## disassembly

```asm
0x180063d80  push    rbp
0x180063d82  push    rbx
0x180063d83  push    rsi
0x180063d84  push    rdi
0x180063d85  mov     rbp, rsp
0x180063d88  sub     rsp, 38h
0x180063d8c  mov     [rbp+arg_18], 0
0x180063d94  mov     edi, ecx
0x180063d96  mov     [rbp+hKey], 0
0x180063d9e  mov     [rbp+cbData], 0
0x180063da5  mov     [rbp+Data], 0
0x180063dac  cmp     ecx, 0FFFFFFFFh
0x180063daf  jz      short loc_180063DCD
0x180063db1  test    ecx, ecx
0x180063db3  jz      short loc_180063DC4
0x180063db5  cmp     ecx, 1
0x180063db8  jz      short loc_180063DC4
0x180063dba  mov     ebx, 57h ; 'W'
0x180063dbf  jmp     loc_180063E98
0x180063dc4  lea     esi, [rcx+1]
0x180063dc7  cmp     ecx, esi
0x180063dc9  jge     short loc_180063E0D
0x180063dcb  jmp     short loc_180063DD4
0x180063dcd  mov     esi, 2
0x180063dd2  xor     edi, edi
0x180063dd4  lea     rcx, off_180119410; "SOFTWARE\\Microsoft\\SystemCertificates"...
0x180063ddb  movsxd  rdx, edi
0x180063dde  lea     rax, [rbp+arg_18]
0x180063de2  mov     r9d, 20019h; samDesired
0x180063de8  xor     r8d, r8d; ulOptions
0x180063deb  mov     [rsp+38h+phkResult], rax; phkResult
0x180063df0  mov     rdx, [rcx+rdx*8]; lpSubKey
0x180063df4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180063dfb  call    cs:__imp_RegOpenKeyExW
0x180063e01  mov     ebx, eax
0x180063e03  test    eax, eax
0x180063e05  jz      short loc_180063E7A
0x180063e07  inc     edi
0x180063e09  cmp     edi, esi
0x180063e0b  jl      short loc_180063DD4
0x180063e0d  lea     rax, [rbp+hKey]
0x180063e11  mov     r9d, 20019h; samDesired
0x180063e17  xor     r8d, r8d; ulOptions
0x180063e1a  mov     [rsp+38h+phkResult], rax; phkResult
0x180063e1f  lea     rdx, aSystemSetup; "System\\Setup"
0x180063e26  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180063e2d  call    cs:__imp_RegOpenKeyExW
0x180063e33  mov     ebx, eax
0x180063e35  test    eax, eax
0x180063e37  jnz     short loc_180063E7A
0x180063e39  mov     rcx, [rbp+hKey]; hKey
0x180063e3d  lea     rax, [rbp+cbData]
0x180063e41  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180063e46  lea     rdx, aSystemsetupinp; "SystemSetupInProgress"
0x180063e4d  lea     rax, [rbp+Data]
0x180063e51  mov     [rbp+cbData], 4
0x180063e58  xor     r9d, r9d; lpType
0x180063e5b  mov     [rsp+38h+phkResult], rax; lpData
0x180063e60  xor     r8d, r8d; lpReserved
0x180063e63  call    cs:__imp_RegQueryValueExW
0x180063e69  mov     ebx, eax
0x180063e6b  test    eax, eax
0x180063e6d  jnz     short loc_180063E7A
0x180063e6f  cmp     [rbp+Data], ebx
0x180063e72  mov     eax, 800B0109h
0x180063e77  cmovz   ebx, eax
0x180063e7a  mov     rcx, [rbp+arg_18]; hKey
0x180063e7e  test    rcx, rcx
0x180063e81  jz      short loc_180063E89
0x180063e83  call    cs:__imp_RegCloseKey
0x180063e89  mov     rcx, [rbp+hKey]; hKey
0x180063e8d  test    rcx, rcx
0x180063e90  jz      short loc_180063E98
0x180063e92  call    cs:__imp_RegCloseKey
0x180063e98  mov     eax, ebx
0x180063e9a  add     rsp, 38h
0x180063e9e  pop     rdi
0x180063e9f  pop     rsi
0x180063ea0  pop     rbx
0x180063ea1  pop     rbp
0x180063ea2  retn
```
