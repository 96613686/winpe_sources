# SELGetDbgReg(void)

- ea: `0x18002b8c4`
- end: `0x18002b97e`
- name: `?SELGetDbgReg@@YAKXZ`
- size: `186`
- prototype: `unsigned int(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b984`
- `0x18002b9e4`
- `0x18002ba80`

## callees

- `0x18002b8c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b93d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b93d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b902`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b902`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b965`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b965`

## pseudocode

```c
__int64 SELGetDbgReg(void)
{
  DWORD Type; // [rsp+40h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+18h] BYREF
  int Data; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  if ( !byte_180050D90 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Cryptography\\AutoEnrollment", 0, 1u, &hKey) )
    {
      Type = 0;
      Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"debug", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && cbData == 4 )
        dword_180050D80 = Data;
    }
    if ( hKey )
      RegCloseKey(hKey);
    byte_180050D90 = 1;
  }
  return (unsigned int)dword_180050D80;
}

```

## disassembly

```asm
0x18002b8c4  push    rbp
0x18002b8c6  mov     rbp, rsp
0x18002b8c9  sub     rsp, 30h
0x18002b8cd  cmp     cs:byte_180050D90, 0
0x18002b8d4  jnz     loc_18002B972
0x18002b8da  lea     rax, [rbp+hKey]
0x18002b8de  mov     [rbp+hKey], 0
0x18002b8e6  mov     r9d, 1; samDesired
0x18002b8ec  mov     [rsp+30h+phkResult], rax; phkResult
0x18002b8f1  xor     r8d, r8d; ulOptions
0x18002b8f4  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Cryptography\\Auto"...
0x18002b8fb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b902  call    cs:__imp_RegOpenKeyExW
0x18002b908  test    eax, eax
0x18002b90a  jnz     short loc_18002B95C
0x18002b90c  mov     rcx, [rbp+hKey]; hKey
0x18002b910  lea     r9, [rbp+Type]; lpType
0x18002b914  mov     [rbp+Type], eax
0x18002b917  lea     rdx, aDebug; "debug"
0x18002b91e  mov     [rbp+Data], eax
0x18002b921  xor     r8d, r8d; lpReserved
0x18002b924  lea     rax, [rbp+cbData]
0x18002b928  mov     [rbp+cbData], 4
0x18002b92f  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002b934  lea     rax, [rbp+Data]
0x18002b938  mov     [rsp+30h+phkResult], rax; lpData
0x18002b93d  call    cs:__imp_RegQueryValueExW
0x18002b943  test    eax, eax
0x18002b945  jnz     short loc_18002B95C
0x18002b947  cmp     [rbp+Type], 4
0x18002b94b  jnz     short loc_18002B95C
0x18002b94d  cmp     [rbp+cbData], 4
0x18002b951  jnz     short loc_18002B95C
0x18002b953  mov     eax, [rbp+Data]
0x18002b956  mov     cs:dword_180050D80, eax
0x18002b95c  mov     rcx, [rbp+hKey]; hKey
0x18002b960  test    rcx, rcx
0x18002b963  jz      short loc_18002B96B
0x18002b965  call    cs:__imp_RegCloseKey
0x18002b96b  mov     cs:byte_180050D90, 1
0x18002b972  mov     eax, cs:dword_180050D80
0x18002b978  add     rsp, 30h
0x18002b97c  pop     rbp
0x18002b97d  retn
```
