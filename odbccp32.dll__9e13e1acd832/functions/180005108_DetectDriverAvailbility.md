# DetectDriverAvailbility

- ea: `0x180005108`
- end: `0x180005208`
- name: `DetectDriverAvailbility`
- size: `256`
- prototype: `LSTATUS __fastcall(LPCWSTR lpSubKey, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180005530`

## callees

- `0x180005108`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180005184`
- `ADVAPI32!RegCloseKey` at `0x18000518e`
- `ADVAPI32!RegCloseKey` at `0x1800051e8`
- `ADVAPI32!RegCloseKey` at `0x1800051f2`
- `ADVAPI32!RegCloseKey` at `0x180005184`
- `ADVAPI32!RegCloseKey` at `0x18000518e`
- `ADVAPI32!RegCloseKey` at `0x1800051e8`
- `ADVAPI32!RegCloseKey` at `0x1800051f2`
- `ADVAPI32!RegOpenKeyExW` at `0x180005150`
- `ADVAPI32!RegOpenKeyExW` at `0x180005173`
- `ADVAPI32!RegOpenKeyExW` at `0x1800051b4`
- `ADVAPI32!RegOpenKeyExW` at `0x1800051d7`
- `ADVAPI32!RegOpenKeyExW` at `0x180005150`
- `ADVAPI32!RegOpenKeyExW` at `0x180005173`
- `ADVAPI32!RegOpenKeyExW` at `0x1800051b4`
- `ADVAPI32!RegOpenKeyExW` at `0x1800051d7`

## pseudocode

```c
LSTATUS __fastcall DetectDriverAvailbility(LPCWSTR lpSubKey, _DWORD *a2)
{
  LSTATUS result; // eax
  HKEY hKey; // [rsp+50h] [rbp+20h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp+28h] BYREF

  hKey = 0;
  phkResult = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\ODBC\\ODBCINST.INI", 0, 0x20219u, &hKey) )
  {
    if ( !RegOpenKeyExW(hKey, lpSubKey, 0, 0x20219u, &phkResult) )
    {
      *a2 |= 1u;
      RegCloseKey(phkResult);
    }
    RegCloseKey(hKey);
  }
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\ODBC\\ODBCINST.INI", 0, 0x20019u, &hKey);
  if ( !result )
  {
    if ( !RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &phkResult) )
    {
      *a2 |= 2u;
      RegCloseKey(phkResult);
    }
    return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x180005108  mov     [rsp-8+arg_0], rbx
0x18000510d  mov     [rsp-8+arg_8], rdi
0x180005112  push    rbp
0x180005113  mov     rbp, rsp
0x180005116  sub     rsp, 30h
0x18000511a  mov     rbx, rdx
0x18000511d  mov     [rbp+hKey], 0
0x180005125  mov     rdi, rcx
0x180005128  mov     [rbp+arg_18], 0
0x180005130  lea     rax, [rbp+hKey]
0x180005134  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000513b  lea     rdx, aSoftwareOdbcOd; "Software\\ODBC\\ODBCINST.INI"
0x180005142  mov     [rsp+30h+phkResult], rax; phkResult
0x180005147  mov     r9d, 20219h; samDesired
0x18000514d  xor     r8d, r8d; ulOptions
0x180005150  call    cs:__imp_RegOpenKeyExW
0x180005156  test    eax, eax
0x180005158  jnz     short loc_180005194
0x18000515a  mov     rcx, [rbp+hKey]; hKey
0x18000515e  lea     rax, [rbp+arg_18]
0x180005162  mov     r9d, 20219h; samDesired
0x180005168  mov     [rsp+30h+phkResult], rax; phkResult
0x18000516d  xor     r8d, r8d; ulOptions
0x180005170  mov     rdx, rdi; lpSubKey
0x180005173  call    cs:__imp_RegOpenKeyExW
0x180005179  test    eax, eax
0x18000517b  jnz     short loc_18000518A
0x18000517d  or      dword ptr [rbx], 1
0x180005180  mov     rcx, [rbp+arg_18]; hKey
0x180005184  call    cs:__imp_RegCloseKey
0x18000518a  mov     rcx, [rbp+hKey]; hKey
0x18000518e  call    cs:__imp_RegCloseKey
0x180005194  lea     rax, [rbp+hKey]
0x180005198  mov     r9d, 20019h; samDesired
0x18000519e  xor     r8d, r8d; ulOptions
0x1800051a1  mov     [rsp+30h+phkResult], rax; phkResult
0x1800051a6  lea     rdx, aSoftwareOdbcOd; "Software\\ODBC\\ODBCINST.INI"
0x1800051ad  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800051b4  call    cs:__imp_RegOpenKeyExW
0x1800051ba  test    eax, eax
0x1800051bc  jnz     short loc_1800051F8
0x1800051be  mov     rcx, [rbp+hKey]; hKey
0x1800051c2  lea     rax, [rbp+arg_18]
0x1800051c6  mov     r9d, 20019h; samDesired
0x1800051cc  mov     [rsp+30h+phkResult], rax; phkResult
0x1800051d1  xor     r8d, r8d; ulOptions
0x1800051d4  mov     rdx, rdi; lpSubKey
0x1800051d7  call    cs:__imp_RegOpenKeyExW
0x1800051dd  test    eax, eax
0x1800051df  jnz     short loc_1800051EE
0x1800051e1  or      dword ptr [rbx], 2
0x1800051e4  mov     rcx, [rbp+arg_18]; hKey
0x1800051e8  call    cs:__imp_RegCloseKey
0x1800051ee  mov     rcx, [rbp+hKey]; hKey
0x1800051f2  call    cs:__imp_RegCloseKey
0x1800051f8  mov     rbx, [rsp+30h+arg_0]
0x1800051fd  mov     rdi, [rsp+30h+arg_8]
0x180005202  add     rsp, 30h
0x180005206  pop     rbp
0x180005207  retn
```
