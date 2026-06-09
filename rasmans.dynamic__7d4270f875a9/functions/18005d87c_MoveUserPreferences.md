# MoveUserPreferences

- ea: `0x18005d87c`
- end: `0x18005d97f`
- name: `MoveUserPreferences`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005d1c0`

## callees

- `0x18005d2a8`
- `0x18005d87c`
- `0x18005d988`
- `0x18005e0d8`
- `0x180060bec`
- `0x1800e8e96`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d8ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d935`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d8ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d935`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d959`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d969`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d959`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d969`

## string_xrefs

- `0x18005d8ac`: `Software\Microsoft\Windows NT\CurrentVersion\Network\RemoteAccess`
- `0x18005d949`: `RemoteAccess`

## pseudocode

```c
LSTATUS MoveUserPreferences()
{
  LSTATUS result; // eax
  _BYTE v1[180]; // [rsp+30h] [rbp-69h] BYREF
  int v2; // [rsp+E4h] [rbp+4Bh]
  HKEY hKey; // [rsp+100h] [rbp+67h] BYREF
  HKEY phkResult; // [rsp+108h] [rbp+6Fh] BYREF

  phkResult = 0;
  hKey = 0;
  result = RegOpenKeyExW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Network\\RemoteAccess",
             0,
             0x20019u,
             &phkResult);
  if ( !result )
  {
    memset_0(v1, 0, 0xB8u);
    if ( !(unsigned int)SetDefaultUserPreferences(v1) && !(unsigned int)ReadUserPreferences(phkResult, v1) )
    {
      v2 = 1;
      if ( !(unsigned int)DwSetUserPreferences(v1, 0)
        && !RegOpenKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Network",
              0,
              0x20006u,
              &hKey) )
      {
        MyRegDeleteTree(hKey, L"RemoteAccess");
        RegCloseKey(hKey);
      }
    }
    return RegCloseKey(phkResult);
  }
  return result;
}

```

## disassembly

```asm
0x18005d87c  push    rbp
0x18005d87e  lea     rbp, [rsp-57h]
0x18005d883  sub     rsp, 0F0h
0x18005d88a  lea     rax, [rbp+57h+arg_8]
0x18005d88e  mov     [rbp+57h+arg_8], 0
0x18005d896  mov     r9d, 20019h; samDesired
0x18005d89c  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18005d8a1  xor     r8d, r8d; ulOptions
0x18005d8a4  mov     [rbp+57h+hKey], 0
0x18005d8ac  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x18005d8b3  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18005d8ba  call    cs:__imp_RegOpenKeyExW
0x18005d8c1  nop     dword ptr [rax+rax+00h]
0x18005d8c6  test    eax, eax
0x18005d8c8  jnz     loc_18005D975
0x18005d8ce  xor     edx, edx; Val
0x18005d8d0  lea     rcx, [rbp+57h+var_C0]; void *
0x18005d8d4  mov     r8d, 0B8h; Size
0x18005d8da  call    memset_0
0x18005d8df  xor     edx, edx
0x18005d8e1  lea     rcx, [rbp+57h+var_C0]; void *
0x18005d8e5  call    SetDefaultUserPreferences
0x18005d8ea  test    eax, eax
0x18005d8ec  jnz     short loc_18005D965
0x18005d8ee  mov     rcx, [rbp+57h+arg_8]; hKey
0x18005d8f2  lea     rdx, [rbp+57h+var_C0]; void *
0x18005d8f6  call    ReadUserPreferences
0x18005d8fb  test    eax, eax
0x18005d8fd  jnz     short loc_18005D965
0x18005d8ff  xor     edx, edx
0x18005d901  mov     [rbp+57h+var_C], 1
0x18005d908  lea     rcx, [rbp+57h+var_C0]
0x18005d90c  call    DwSetUserPreferences
0x18005d911  test    eax, eax
0x18005d913  jnz     short loc_18005D965
0x18005d915  lea     rax, [rbp+57h+hKey]
0x18005d919  mov     r9d, 20006h; samDesired
0x18005d91f  xor     r8d, r8d; ulOptions
0x18005d922  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18005d927  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x18005d92e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18005d935  call    cs:__imp_RegOpenKeyExW
0x18005d93c  nop     dword ptr [rax+rax+00h]
0x18005d941  test    eax, eax
0x18005d943  jnz     short loc_18005D965
0x18005d945  mov     rcx, [rbp+57h+hKey]
0x18005d949  lea     rdx, aRemoteaccess; "RemoteAccess"
0x18005d950  call    MyRegDeleteTree
0x18005d955  mov     rcx, [rbp+57h+hKey]; hKey
0x18005d959  call    cs:__imp_RegCloseKey
0x18005d960  nop     dword ptr [rax+rax+00h]
0x18005d965  mov     rcx, [rbp+57h+arg_8]; hKey
0x18005d969  call    cs:__imp_RegCloseKey
0x18005d970  nop     dword ptr [rax+rax+00h]
0x18005d975  add     rsp, 0F0h
0x18005d97c  pop     rbp
0x18005d97d  retn
```
