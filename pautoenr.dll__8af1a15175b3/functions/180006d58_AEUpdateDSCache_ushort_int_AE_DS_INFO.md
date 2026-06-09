# AEUpdateDSCache(ushort *,int,_AE_DS_INFO_ *)

- ea: `0x180006d58`
- end: `0x180006ec6`
- name: `?AEUpdateDSCache@@YAHPEAGHPEAU_AE_DS_INFO_@@@Z`
- size: `366`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, int, const BYTE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180003d10`

## callees

- `0x180006d58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006e48`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006e83`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006e48`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006e83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006e9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006ea9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006e9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006ea9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006dce`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006e10`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006dce`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006e10`

## string_xrefs

- `0x180006db7`: `SOFTWARE\Microsoft\Cryptography\AutoEnrollment\AEDirectoryCache`

## pseudocode

```c
__int64 __fastcall AEUpdateDSCache(LPCWSTR lpSubKey, int a2, const BYTE *a3)
{
  unsigned int v3; // ebx
  const WCHAR *v7; // rdx
  const WCHAR *v8; // rdx
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  DWORD dwDisposition; // [rsp+80h] [rbp+20h] BYREF
  HKEY phkResult; // [rsp+98h] [rbp+38h] BYREF

  v3 = 0;
  dwDisposition = 0;
  hKey = 0;
  phkResult = 0;
  if ( lpSubKey && a3 )
  {
    if ( !RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Cryptography\\AutoEnrollment\\AEDirectoryCache",
            0,
            (LPWSTR)&Class,
            0,
            0xF003Fu,
            0,
            &hKey,
            &dwDisposition)
      && !RegCreateKeyExW(hKey, lpSubKey, 0, (LPWSTR)&Class, 0, 0xF003Fu, 0, &phkResult, &dwDisposition) )
    {
      v7 = L"OIDObjectCount";
      if ( !a2 )
        v7 = L"AEObjectCount";
      if ( !RegSetValueExW(phkResult, v7, 0, 4u, a3 + 4, 4u) )
      {
        v8 = L"AEMaxUSN";
        if ( a2 )
          v8 = L"OIDMaxUSN";
        if ( !RegSetValueExW(phkResult, v8, 0, 3u, a3 + 8, 8u) )
          v3 = 1;
      }
    }
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x180006d58  mov     r11, rsp
0x180006d5b  mov     [r11+10h], rbx
0x180006d5f  mov     [r11+18h], rsi
0x180006d63  push    rbp
0x180006d64  push    rdi
0x180006d65  push    r14
0x180006d67  mov     rbp, rsp
0x180006d6a  sub     rsp, 60h
0x180006d6e  xor     ebx, ebx
0x180006d70  mov     rdi, r8
0x180006d73  mov     [rbp+dwDisposition], ebx
0x180006d76  mov     r14d, edx
0x180006d79  mov     [rbp+hKey], rbx
0x180006d7d  mov     rsi, rcx
0x180006d80  mov     [rbp+arg_18], rbx
0x180006d84  test    rcx, rcx
0x180006d87  jz      loc_180006EAF
0x180006d8d  test    r8, r8
0x180006d90  jz      loc_180006EAF
0x180006d96  lea     rax, [rbp+dwDisposition]
0x180006d9a  xor     r8d, r8d; Reserved
0x180006d9d  mov     [r11-38h], rax
0x180006da1  lea     r9, Class; lpClass
0x180006da8  lea     rax, [rbp+hKey]
0x180006dac  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006db3  mov     [r11-40h], rax
0x180006db7  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Cryptography\\Auto"...
0x180006dbe  mov     [r11-48h], rbx
0x180006dc2  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x180006dca  mov     [rsp+60h+dwOptions], ebx; dwOptions
0x180006dce  call    cs:__imp_RegCreateKeyExW
0x180006dd4  test    eax, eax
0x180006dd6  jnz     loc_180006E91
0x180006ddc  mov     rcx, [rbp+hKey]; hKey
0x180006de0  lea     rax, [rbp+dwDisposition]
0x180006de4  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x180006de9  lea     r9, Class; lpClass
0x180006df0  lea     rax, [rbp+arg_18]
0x180006df4  xor     r8d, r8d; Reserved
0x180006df7  mov     [rsp+60h+phkResult], rax; phkResult
0x180006dfc  mov     rdx, rsi; lpSubKey
0x180006dff  mov     [rsp+60h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180006e04  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x180006e0c  mov     [rsp+60h+dwOptions], ebx; dwOptions
0x180006e10  call    cs:__imp_RegCreateKeyExW
0x180006e16  test    eax, eax
0x180006e18  jnz     short loc_180006E91
0x180006e1a  lea     rcx, aAeobjectcount; "AEObjectCount"
0x180006e21  test    r14d, r14d
0x180006e24  lea     r9d, [rbx+4]; dwType
0x180006e28  lea     rax, [rdi+4]
0x180006e2c  mov     [rsp+60h+samDesired], r9d; cbData
0x180006e31  lea     rdx, aOidobjectcount; "OIDObjectCount"
0x180006e38  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180006e3d  cmovz   rdx, rcx; lpValueName
0x180006e41  mov     rcx, [rbp+arg_18]; hKey
0x180006e45  xor     r8d, r8d; Reserved
0x180006e48  call    cs:__imp_RegSetValueExW
0x180006e4e  test    eax, eax
0x180006e50  jnz     short loc_180006E91
0x180006e52  lea     rcx, aOidmaxusn; "OIDMaxUSN"
0x180006e59  mov     [rsp+60h+samDesired], 8; cbData
0x180006e61  lea     rax, [rdi+8]
0x180006e65  test    r14d, r14d
0x180006e68  lea     rdx, aAemaxusn; "AEMaxUSN"
0x180006e6f  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180006e74  cmovnz  rdx, rcx; lpValueName
0x180006e78  lea     r9d, [rbx+3]; dwType
0x180006e7c  mov     rcx, [rbp+arg_18]; hKey
0x180006e80  xor     r8d, r8d; Reserved
0x180006e83  call    cs:__imp_RegSetValueExW
0x180006e89  test    eax, eax
0x180006e8b  lea     ecx, [rbx+1]
0x180006e8e  cmovz   ebx, ecx
0x180006e91  mov     rcx, [rbp+arg_18]; hKey
0x180006e95  test    rcx, rcx
0x180006e98  jz      short loc_180006EA0
0x180006e9a  call    cs:__imp_RegCloseKey
0x180006ea0  mov     rcx, [rbp+hKey]; hKey
0x180006ea4  test    rcx, rcx
0x180006ea7  jz      short loc_180006EAF
0x180006ea9  call    cs:__imp_RegCloseKey
0x180006eaf  lea     r11, [rsp+60h+var_s0]
0x180006eb4  mov     eax, ebx
0x180006eb6  mov     rbx, [r11+28h]
0x180006eba  mov     rsi, [r11+30h]
0x180006ebe  mov     rsp, r11
0x180006ec1  pop     r14
0x180006ec3  pop     rdi
0x180006ec4  pop     rbp
0x180006ec5  retn
```
