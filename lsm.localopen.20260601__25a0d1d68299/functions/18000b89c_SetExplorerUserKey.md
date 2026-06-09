# SetExplorerUserKey

- ea: `0x18000b89c`
- end: `0x18000b972`
- name: `SetExplorerUserKey`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b3d0`

## callees

- `0x18000b89c`
- `0x18000c17c`
- `0x18004e850`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b90a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b90a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b94d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b94d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b93c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b93c`

## pseudocode

```c
int __fastcall SetExplorerUserKey(__int64 a1, int a2)
{
  int result; // eax
  BYTE Data[8]; // [rsp+30h] [rbp-438h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-430h] BYREF
  WCHAR SubKey[520]; // [rsp+40h] [rbp-428h] BYREF

  *(_DWORD *)Data = a2;
  result = StringCchPrintfW(SubKey, 0x208u, L"%ls\\%ls", a1, L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer");
  if ( result >= 0 )
  {
    hKey = 0;
    result = RegOpenKeyExW(HKEY_USERS, SubKey, 0, 2u, &hKey);
    if ( !result )
    {
      RegSetValueExW(hKey, L"LogonWork", 0, 4u, Data, 4u);
      return RegCloseKey(hKey);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000b89c  sub     rsp, 468h
0x18000b8a3  mov     rax, cs:__security_cookie
0x18000b8aa  xor     rax, rsp
0x18000b8ad  mov     [rsp+468h+var_18], rax
0x18000b8b5  mov     dword ptr [rsp+468h+Data], edx
0x18000b8b9  lea     rax, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000b8c0  mov     r9, rcx
0x18000b8c3  mov     [rsp+468h+phkResult], rax
0x18000b8c8  mov     edx, 208h; unsigned __int64
0x18000b8cd  lea     rcx, [rsp+468h+SubKey]; unsigned __int16 *
0x18000b8d2  lea     r8, aLsLs; "%ls\\%ls"
0x18000b8d9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b8de  test    eax, eax
0x18000b8e0  js      short loc_18000B959
0x18000b8e2  lea     rax, [rsp+468h+hKey]
0x18000b8e7  mov     [rsp+468h+hKey], 0
0x18000b8f0  mov     r9d, 2; samDesired
0x18000b8f6  mov     [rsp+468h+phkResult], rax; phkResult
0x18000b8fb  xor     r8d, r8d; ulOptions
0x18000b8fe  lea     rdx, [rsp+468h+SubKey]; lpSubKey
0x18000b903  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18000b90a  call    cs:__imp_RegOpenKeyExW
0x18000b911  nop     dword ptr [rax+rax+00h]
0x18000b916  test    eax, eax
0x18000b918  jnz     short loc_18000B959
0x18000b91a  mov     rcx, [rsp+468h+hKey]; hKey
0x18000b91f  lea     r9d, [rax+4]; dwType
0x18000b923  lea     rax, [rsp+468h+Data]
0x18000b928  mov     [rsp+468h+cbData], r9d; cbData
0x18000b92d  xor     r8d, r8d; Reserved
0x18000b930  mov     [rsp+468h+phkResult], rax; lpData
0x18000b935  lea     rdx, aLogonwork; "LogonWork"
0x18000b93c  call    cs:__imp_RegSetValueExW
0x18000b943  nop     dword ptr [rax+rax+00h]
0x18000b948  mov     rcx, [rsp+468h+hKey]; hKey
0x18000b94d  call    cs:__imp_RegCloseKey
0x18000b954  nop     dword ptr [rax+rax+00h]
0x18000b959  mov     rcx, [rsp+468h+var_18]
0x18000b961  xor     rcx, rsp; StackCookie
0x18000b964  call    __security_check_cookie
0x18000b969  add     rsp, 468h
0x18000b970  retn
```
