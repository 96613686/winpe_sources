# RegValChoice_GetAndCompareRegValues

- ea: `0x18007fbd0`
- end: `0x18007fd2d`
- name: `RegValChoice_GetAndCompareRegValues`
- size: `349`
- prototype: `__int64 __fastcall(int, int, int, int, int, DWORD cbData, LPDWORD lpType, LPBYTE lpData, LPBYTE, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d3a0`

## callees

- `0x18002ce53`
- `0x18007fbd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007fca6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007fcd6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007fca6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007fcd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007fd0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007fd18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007fd0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007fd18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007fc34`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007fc5d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007fc34`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007fc5d`

## pseudocode

```c
__int64 __fastcall RegValChoice_GetAndCompareRegValues(
        __int64 a1,
        __int64 a2,
        DWORD a3,
        __int64 a4,
        int a5,
        DWORD cbData,
        LPDWORD lpType,
        LPBYTE lpData,
        LPBYTE a9,
        DWORD *a10,
        _DWORD *a11)
{
  _DWORD *v11; // r14
  unsigned int v12; // ebx
  LPDWORD v13; // rdi
  LPBYTE v14; // r15
  LPBYTE v15; // rsi
  HKEY hKey; // [rsp+70h] [rbp+38h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+40h] BYREF
  DWORD Type; // [rsp+80h] [rbp+48h] BYREF
  __int64 lpcbData; // [rsp+88h] [rbp+50h] BYREF

  lpcbData = a4;
  Type = a3;
  v11 = a11;
  hKey = 0;
  phkResult = 0;
  *a11 = 0;
  v12 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
          0,
          0x20019u,
          &hKey);
  if ( !v12 )
  {
    v12 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\AlternateShells",
            0,
            0x20019u,
            &phkResult);
    if ( !v12 )
    {
      v13 = lpType;
      v14 = lpData;
      Type = 0;
      cbData = *a10;
      LODWORD(lpcbData) = cbData;
      v12 = RegQueryValueExW(hKey, L"Shell", 0, lpType, lpData, &cbData);
      if ( !v12 )
      {
        v15 = a9;
        v12 = RegQueryValueExW(phkResult, L"DefaultShell", 0, &Type, a9, (LPDWORD)&lpcbData);
        if ( !v12 && *v13 == Type && cbData == (_DWORD)lpcbData && !memcmp_0(v14, v15, cbData) )
          *v11 = 1;
      }
      RegCloseKey(phkResult);
    }
    RegCloseKey(hKey);
  }
  return v12;
}

```

## disassembly

```asm
0x18007fbd0  mov     r11, rsp
0x18007fbd3  mov     [r11+20h], r9
0x18007fbd7  mov     [r11+18h], r8d
0x18007fbdb  mov     [r11+10h], rdx
0x18007fbdf  mov     [r11+8], rcx
0x18007fbe3  push    rbp
0x18007fbe4  push    rbx
0x18007fbe5  push    rsi
0x18007fbe6  push    rdi
0x18007fbe7  push    r14
0x18007fbe9  push    r15
0x18007fbeb  mov     rbp, rsp
0x18007fbee  sub     rsp, 38h
0x18007fbf2  mov     r14, [rbp+arg_50]
0x18007fbf9  lea     rax, [rbp+hKey]
0x18007fbfd  mov     edi, 20019h
0x18007fc02  mov     [rbp+hKey], 0
0x18007fc0a  mov     rsi, 0FFFFFFFF80000002h
0x18007fc11  mov     [rbp+arg_8], 0
0x18007fc19  mov     r9d, edi; samDesired
0x18007fc1c  mov     [r11-48h], rax
0x18007fc20  xor     r8d, r8d; ulOptions
0x18007fc23  mov     dword ptr [r14], 0
0x18007fc2a  lea     rdx, pszSubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x18007fc31  mov     rcx, rsi; hKey
0x18007fc34  call    cs:__imp_RegOpenKeyExW
0x18007fc3a  mov     ebx, eax
0x18007fc3c  test    eax, eax
0x18007fc3e  jnz     loc_18007FD1E
0x18007fc44  lea     rax, [rbp+arg_8]
0x18007fc48  mov     r9d, edi; samDesired
0x18007fc4b  xor     r8d, r8d; ulOptions
0x18007fc4e  mov     [rsp+38h+phkResult], rax; phkResult
0x18007fc53  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows NT\\Curren"...
0x18007fc5a  mov     rcx, rsi; hKey
0x18007fc5d  call    cs:__imp_RegOpenKeyExW
0x18007fc63  mov     ebx, eax
0x18007fc65  test    eax, eax
0x18007fc67  jnz     loc_18007FD14
0x18007fc6d  mov     rax, [rbp+arg_48]
0x18007fc74  lea     rdx, pszValue; "Shell"
0x18007fc7b  mov     rdi, [rbp+lpType]
0x18007fc7f  xor     r8d, r8d; lpReserved
0x18007fc82  mov     r15, [rbp+lpData]
0x18007fc86  mov     r9, rdi; lpType
0x18007fc89  mov     [rbp+Type], ebx
0x18007fc8c  mov     ecx, [rax]
0x18007fc8e  lea     rax, [rbp+cbData]
0x18007fc92  mov     [rbp+cbData], ecx
0x18007fc95  mov     dword ptr [rbp+arg_18], ecx
0x18007fc98  mov     rcx, [rbp+hKey]; hKey
0x18007fc9c  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18007fca1  mov     [rsp+38h+phkResult], r15; lpData
0x18007fca6  call    cs:__imp_RegQueryValueExW
0x18007fcac  mov     ebx, eax
0x18007fcae  test    eax, eax
0x18007fcb0  jnz     short loc_18007FD0A
0x18007fcb2  mov     rsi, [rbp+arg_40]
0x18007fcb6  lea     rax, [rbp+arg_18]
0x18007fcba  mov     rcx, [rbp+arg_8]; hKey
0x18007fcbe  lea     r9, [rbp+Type]; lpType
0x18007fcc2  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18007fcc7  lea     rdx, aDefaultshell; "DefaultShell"
0x18007fcce  xor     r8d, r8d; lpReserved
0x18007fcd1  mov     [rsp+38h+phkResult], rsi; lpData
0x18007fcd6  call    cs:__imp_RegQueryValueExW
0x18007fcdc  mov     ebx, eax
0x18007fcde  test    eax, eax
0x18007fce0  jnz     short loc_18007FD0A
0x18007fce2  mov     eax, [rbp+Type]
0x18007fce5  cmp     [rdi], eax
0x18007fce7  jnz     short loc_18007FD0A
0x18007fce9  mov     eax, [rbp+cbData]
0x18007fcec  cmp     eax, dword ptr [rbp+arg_18]
0x18007fcef  jnz     short loc_18007FD0A
0x18007fcf1  mov     r8d, eax; Size
0x18007fcf4  mov     rdx, rsi; Buf2
0x18007fcf7  mov     rcx, r15; Buf1
0x18007fcfa  call    memcmp_0
0x18007fcff  test    eax, eax
0x18007fd01  jnz     short loc_18007FD0A
0x18007fd03  mov     dword ptr [r14], 1
0x18007fd0a  mov     rcx, [rbp+arg_8]; hKey
0x18007fd0e  call    cs:__imp_RegCloseKey
0x18007fd14  mov     rcx, [rbp+hKey]; hKey
0x18007fd18  call    cs:__imp_RegCloseKey
0x18007fd1e  mov     eax, ebx
0x18007fd20  add     rsp, 38h
0x18007fd24  pop     r15
0x18007fd26  pop     r14
0x18007fd28  pop     rdi
0x18007fd29  pop     rsi
0x18007fd2a  pop     rbx
0x18007fd2b  pop     rbp
0x18007fd2c  retn
```
