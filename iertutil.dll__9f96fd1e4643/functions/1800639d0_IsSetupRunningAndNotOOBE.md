# _IsSetupRunningAndNotOOBE

- ea: `0x1800639d0`
- end: `0x180063ac3`
- name: `_IsSetupRunningAndNotOOBE`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x180063870`

## callees

- `0x1800639d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063a18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063a18`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180063a53`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180063a8c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180063a53`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180063a8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063aa4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063aa4`

## pseudocode

```c
_BOOL8 IsSetupRunningAndNotOOBE()
{
  int v0; // ebx
  int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+20h] BYREF

  v0 = dword_180299FE4;
  if ( !dword_180299FE4 )
  {
    hKey = 0;
    v0 = 2;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup", 0, 0x20019u, &hKey) )
    {
      Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"SystemSetupInProgress", 0, 0, (LPBYTE)&Data, &cbData) )
      {
        if ( Data )
        {
          cbData = 4;
          if ( RegQueryValueExW(hKey, L"OOBEInProgress", 0, 0, (LPBYTE)&Data, &cbData) || !Data )
            v0 = 1;
        }
      }
      RegCloseKey(hKey);
    }
    dword_180299FE4 = v0;
  }
  return v0 == 1;
}

```

## disassembly

```asm
0x1800639d0  mov     [rsp-8+arg_18], rbx
0x1800639d5  push    rbp
0x1800639d6  mov     rbp, rsp
0x1800639d9  sub     rsp, 30h
0x1800639dd  mov     ebx, cs:dword_180299FE4
0x1800639e3  test    ebx, ebx
0x1800639e5  jnz     loc_180063AB0
0x1800639eb  lea     rax, [rbp+hKey]
0x1800639ef  mov     [rbp+hKey], 0
0x1800639f7  mov     r9d, 20019h; samDesired
0x1800639fd  mov     [rsp+30h+phkResult], rax; phkResult
0x180063a02  xor     r8d, r8d; ulOptions
0x180063a05  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x180063a0c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180063a13  mov     ebx, 2
0x180063a18  call    cs:__imp_RegOpenKeyExW
0x180063a1e  test    eax, eax
0x180063a20  jnz     loc_180063AAA
0x180063a26  mov     rcx, [rbp+hKey]; hKey
0x180063a2a  lea     rdx, aSystemsetupinp; "SystemSetupInProgress"
0x180063a31  mov     [rbp+Data], eax
0x180063a34  xor     r9d, r9d; lpType
0x180063a37  lea     rax, [rbp+cbData]
0x180063a3b  mov     [rbp+cbData], 4
0x180063a42  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180063a47  xor     r8d, r8d; lpReserved
0x180063a4a  lea     rax, [rbp+Data]
0x180063a4e  mov     [rsp+30h+phkResult], rax; lpData
0x180063a53  call    cs:__imp_RegQueryValueExW
0x180063a59  test    eax, eax
0x180063a5b  jnz     short loc_180063AA0
0x180063a5d  cmp     [rbp+Data], eax
0x180063a60  jz      short loc_180063AA0
0x180063a62  mov     rcx, [rbp+hKey]; hKey
0x180063a66  lea     rax, [rbp+cbData]
0x180063a6a  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180063a6f  lea     rdx, aOobeinprogress; "OOBEInProgress"
0x180063a76  lea     rax, [rbp+Data]
0x180063a7a  mov     [rbp+cbData], 4
0x180063a81  xor     r9d, r9d; lpType
0x180063a84  mov     [rsp+30h+phkResult], rax; lpData
0x180063a89  xor     r8d, r8d; lpReserved
0x180063a8c  call    cs:__imp_RegQueryValueExW
0x180063a92  test    eax, eax
0x180063a94  jnz     short loc_180063A9B
0x180063a96  cmp     [rbp+Data], eax
0x180063a99  jnz     short loc_180063AA0
0x180063a9b  mov     ebx, 1
0x180063aa0  mov     rcx, [rbp+hKey]; hKey
0x180063aa4  call    cs:__imp_RegCloseKey
0x180063aaa  mov     cs:dword_180299FE4, ebx
0x180063ab0  xor     eax, eax
0x180063ab2  cmp     ebx, 1
0x180063ab5  mov     rbx, [rsp+30h+arg_18]
0x180063aba  setz    al
0x180063abd  add     rsp, 30h
0x180063ac1  pop     rbp
0x180063ac2  retn
```
