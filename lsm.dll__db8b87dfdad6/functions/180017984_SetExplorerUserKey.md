# SetExplorerUserKey

- ea: `0x180017984`
- end: `0x180017a47`
- name: `SetExplorerUserKey`
- size: `195`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017520`

## callees

- `0x180017984`
- `0x180018200`
- `0x18004b460`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800179f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800179f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017a29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017a29`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017a1e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017a1e`

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
0x180017984  sub     rsp, 468h
0x18001798b  mov     rax, cs:__security_cookie
0x180017992  xor     rax, rsp
0x180017995  mov     [rsp+468h+var_18], rax
0x18001799d  mov     dword ptr [rsp+468h+Data], edx
0x1800179a1  lea     rax, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800179a8  mov     r9, rcx
0x1800179ab  mov     [rsp+468h+phkResult], rax
0x1800179b0  mov     edx, 208h; unsigned __int64
0x1800179b5  lea     rcx, [rsp+468h+SubKey]; unsigned __int16 *
0x1800179ba  lea     r8, aLsLs; "%ls\\%ls"
0x1800179c1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800179c6  test    eax, eax
0x1800179c8  js      short loc_180017A2F
0x1800179ca  lea     rax, [rsp+468h+hKey]
0x1800179cf  mov     [rsp+468h+hKey], 0
0x1800179d8  mov     r9d, 2; samDesired
0x1800179de  mov     [rsp+468h+phkResult], rax; phkResult
0x1800179e3  xor     r8d, r8d; ulOptions
0x1800179e6  lea     rdx, [rsp+468h+SubKey]; lpSubKey
0x1800179eb  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800179f2  call    cs:__imp_RegOpenKeyExW
0x1800179f8  test    eax, eax
0x1800179fa  jnz     short loc_180017A2F
0x1800179fc  mov     rcx, [rsp+468h+hKey]; hKey
0x180017a01  lea     r9d, [rax+4]; dwType
0x180017a05  lea     rax, [rsp+468h+Data]
0x180017a0a  mov     [rsp+468h+cbData], r9d; cbData
0x180017a0f  xor     r8d, r8d; Reserved
0x180017a12  mov     [rsp+468h+phkResult], rax; lpData
0x180017a17  lea     rdx, aLogonwork; "LogonWork"
0x180017a1e  call    cs:__imp_RegSetValueExW
0x180017a24  mov     rcx, [rsp+468h+hKey]; hKey
0x180017a29  call    cs:__imp_RegCloseKey
0x180017a2f  mov     rcx, [rsp+468h+var_18]
0x180017a37  xor     rcx, rsp; StackCookie
0x180017a3a  call    __security_check_cookie
0x180017a3f  add     rsp, 468h
0x180017a46  retn
```
