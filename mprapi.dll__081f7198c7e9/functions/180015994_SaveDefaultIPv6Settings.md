# SaveDefaultIPv6Settings

- ea: `0x180015994`
- end: `0x180015c0f`
- name: `SaveDefaultIPv6Settings`
- size: `635`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180026b90`

## callees

- `0x180009868`
- `0x180015994`
- `0x180051160`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015bc9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015bdc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015bef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015bc9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015bdc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015bef`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015a31`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015a5f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015a8d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015ac0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015b89`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015bb4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015a31`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015a5f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015a8d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015ac0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015b89`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015bb4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800159e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800159e4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015b04`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015b5b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015b04`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015b5b`

## string_xrefs

- `0x1800159c9`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\IPv6`
- `0x180015a4d`: `AllowNetworkAccess`

## pseudocode

```c
__int64 SaveDefaultIPv6Settings()
{
  unsigned int v0; // ebx
  HKEY hKey; // [rsp+50h] [rbp-69h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-61h] BYREF
  HKEY v4; // [rsp+60h] [rbp-59h] BYREF
  HKEY v5; // [rsp+68h] [rbp-51h] BYREF
  BYTE Data[16]; // [rsp+70h] [rbp-49h] BYREF
  BYTE v7[4]; // [rsp+80h] [rbp-39h] BYREF
  BYTE v8[4]; // [rsp+84h] [rbp-35h] BYREF
  BYTE v9[8]; // [rsp+88h] [rbp-31h] BYREF
  BYTE v10[16]; // [rsp+90h] [rbp-29h] BYREF
  wchar_t pszDest[32]; // [rsp+A0h] [rbp-19h] BYREF

  *(_DWORD *)Data = 0;
  hKey = 0;
  v5 = 0;
  v4 = 0;
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\IPv6",
         0,
         0xF003Fu,
         &hKey);
  if ( v0 )
    goto LABEL_10;
  *(_DWORD *)v7 = 1;
  *(_DWORD *)v8 = 1;
  *(_QWORD *)v9 = 0;
  dwDisposition = 0;
  *(_OWORD *)v10 = 0;
  v0 = RegSetValueExW(hKey, L"EnableIn", 0, 4u, Data, 4u);
  if ( !v0 )
  {
    v0 = RegSetValueExW(hKey, L"AllowNetworkAccess", 0, 4u, v7, 4u);
    if ( !v0 )
    {
      v0 = RegSetValueExW(hKey, L"AdvertiseDefaultRoute", 0, 4u, v8, 4u);
      if ( !v0 )
      {
        v0 = RegSetValueExW(hKey, L"NetworkAdapterGUID", 0, 1u, v9, 8u);
        if ( !v0 )
        {
          v0 = RegCreateKeyExW(hKey, L"StaticPrefixPool", 0, 0, 0, 0xF003Fu, 0, &v5, &dwDisposition);
          if ( v0
            || (StringCbPrintfW(pszDest, 0x40u, L"%d", 0),
                (v0 = RegCreateKeyExW(v5, pszDest, 0, 0, 0, 0xF003Fu, 0, &v4, &dwDisposition)) != 0)
            || (v0 = RegSetValueExW(v4, L"From", 0, 3u, v10, 0x10u)) == 0
            && (v0 = RegSetValueExW(v4, L"To", 0, 3u, v10, 0x10u)) == 0 )
          {
LABEL_10:
            if ( v4 )
            {
              RegCloseKey(v4);
              v4 = 0;
            }
            if ( v5 )
            {
              RegCloseKey(v5);
              v5 = 0;
            }
            if ( hKey )
              RegCloseKey(hKey);
          }
        }
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180015994  push    rbp
0x180015996  push    rbx
0x180015997  push    rsi
0x180015998  push    rdi
0x180015999  lea     rbp, [rsp-3Fh]
0x18001599e  sub     rsp, 0F8h
0x1800159a5  mov     rax, cs:__security_cookie
0x1800159ac  xor     rax, rsp
0x1800159af  mov     [rbp+57h+var_30], rax
0x1800159b3  xor     edi, edi
0x1800159b5  lea     rax, [rbp+57h+hKey]
0x1800159b9  mov     r9d, 0F003Fh; samDesired
0x1800159bf  mov     dword ptr [rbp+57h+Data], edi
0x1800159c2  xor     r8d, r8d; ulOptions
0x1800159c5  mov     [rbp+57h+hKey], rdi
0x1800159c9  lea     rdx, c_szRegKeyRasIPv6; "System\\CurrentControlSet\\Services\\Re"...
0x1800159d0  mov     [rbp+57h+var_A8], rdi
0x1800159d4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800159db  mov     [rbp+57h+var_B0], rdi
0x1800159df  mov     [rsp+110h+phkResult], rax; phkResult
0x1800159e4  call    cs:__imp_RegOpenKeyExW
0x1800159ea  mov     ebx, eax
0x1800159ec  test    eax, eax
0x1800159ee  jnz     loc_180015BC0
0x1800159f4  mov     rcx, [rbp+57h+hKey]; hKey
0x1800159f8  lea     esi, [rdi+4]
0x1800159fb  xorps   xmm0, xmm0
0x1800159fe  mov     [rsp+110h+cbData], esi; cbData
0x180015a02  lea     rax, [rbp+57h+Data]
0x180015a06  mov     dword ptr [rbp+57h+var_90], 1
0x180015a0d  mov     r9d, esi; dwType
0x180015a10  mov     [rsp+110h+phkResult], rax; lpData
0x180015a15  xor     r8d, r8d; Reserved
0x180015a18  mov     dword ptr [rbp+57h+var_8C], 1
0x180015a1f  lea     rdx, c_szRegValEnableIn; "EnableIn"
0x180015a26  mov     qword ptr [rbp+57h+var_88], rdi
0x180015a2a  mov     [rbp+57h+dwDisposition], edi
0x180015a2d  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x180015a31  call    cs:__imp_RegSetValueExW
0x180015a37  mov     ebx, eax
0x180015a39  test    eax, eax
0x180015a3b  jnz     loc_180015BF5
0x180015a41  mov     rcx, [rbp+57h+hKey]; hKey
0x180015a45  lea     rax, [rbp+57h+var_90]
0x180015a49  mov     [rsp+110h+cbData], esi; cbData
0x180015a4d  lea     rdx, c_szRegValAllowNetAccess; "AllowNetworkAccess"
0x180015a54  mov     r9d, esi; dwType
0x180015a57  mov     [rsp+110h+phkResult], rax; lpData
0x180015a5c  xor     r8d, r8d; Reserved
0x180015a5f  call    cs:__imp_RegSetValueExW
0x180015a65  mov     ebx, eax
0x180015a67  test    eax, eax
0x180015a69  jnz     loc_180015BF5
0x180015a6f  mov     rcx, [rbp+57h+hKey]; hKey
0x180015a73  lea     rax, [rbp+57h+var_8C]
0x180015a77  mov     [rsp+110h+cbData], esi; cbData
0x180015a7b  lea     rdx, c_szRegValAllowDefaultRouteAdv; "AdvertiseDefaultRoute"
0x180015a82  mov     r9d, esi; dwType
0x180015a85  mov     [rsp+110h+phkResult], rax; lpData
0x180015a8a  xor     r8d, r8d; Reserved
0x180015a8d  call    cs:__imp_RegSetValueExW
0x180015a93  mov     ebx, eax
0x180015a95  test    eax, eax
0x180015a97  jnz     loc_180015BF5
0x180015a9d  mov     rcx, [rbp+57h+hKey]; hKey
0x180015aa1  lea     rax, [rbp+57h+var_88]
0x180015aa5  mov     [rsp+110h+cbData], 8; cbData
0x180015aad  lea     r9d, [rdi+1]; dwType
0x180015ab1  xor     r8d, r8d; Reserved
0x180015ab4  mov     [rsp+110h+phkResult], rax; lpData
0x180015ab9  lea     rdx, c_szRegValNetworkAdapterGUID; "NetworkAdapterGUID"
0x180015ac0  call    cs:__imp_RegSetValueExW
0x180015ac6  mov     ebx, eax
0x180015ac8  test    eax, eax
0x180015aca  jnz     loc_180015BF5
0x180015ad0  mov     rcx, [rbp+57h+hKey]; hKey
0x180015ad4  lea     rax, [rbp+57h+dwDisposition]
0x180015ad8  mov     [rsp+110h+lpdwDisposition], rax; lpdwDisposition
0x180015add  lea     rdx, c_szRegValStaticPrefixPool; "StaticPrefixPool"
0x180015ae4  lea     rax, [rbp+57h+var_A8]
0x180015ae8  xor     r9d, r9d; lpClass
0x180015aeb  mov     [rsp+110h+var_D8], rax; phkResult
0x180015af0  xor     r8d, r8d; Reserved
0x180015af3  mov     [rsp+110h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180015af8  mov     [rsp+110h+cbData], 0F003Fh; samDesired
0x180015b00  mov     dword ptr [rsp+110h+phkResult], edi; dwOptions
0x180015b04  call    cs:__imp_RegCreateKeyExW
0x180015b0a  mov     ebx, eax
0x180015b0c  test    eax, eax
0x180015b0e  jnz     loc_180015BC0
0x180015b14  xor     r9d, r9d
0x180015b17  lea     r8, aD; "%d"
0x180015b1e  lea     edx, [rdi+40h]; cbDest
0x180015b21  lea     rcx, [rbp+57h+pszDest]; pszDest
0x180015b25  call    StringCbPrintfW
0x180015b2a  mov     rcx, [rbp+57h+var_A8]; hKey
0x180015b2e  lea     rax, [rbp+57h+dwDisposition]
0x180015b32  mov     [rsp+110h+lpdwDisposition], rax; lpdwDisposition
0x180015b37  lea     rdx, [rbp+57h+pszDest]; lpSubKey
0x180015b3b  lea     rax, [rbp+57h+var_B0]
0x180015b3f  xor     r9d, r9d; lpClass
0x180015b42  mov     [rsp+110h+var_D8], rax; phkResult
0x180015b47  xor     r8d, r8d; Reserved
0x180015b4a  mov     [rsp+110h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180015b4f  mov     [rsp+110h+cbData], 0F003Fh; samDesired
0x180015b57  mov     dword ptr [rsp+110h+phkResult], edi; dwOptions
0x180015b5b  call    cs:__imp_RegCreateKeyExW
0x180015b61  mov     ebx, eax
0x180015b63  test    eax, eax
0x180015b65  jnz     short loc_180015BC0
0x180015b67  mov     rcx, [rbp+57h+var_B0]; hKey
0x180015b6b  lea     rax, [rbp+57h+var_80]
0x180015b6f  lea     esi, [rdi+10h]
0x180015b72  xor     r8d, r8d; Reserved
0x180015b75  mov     [rsp+110h+cbData], esi; cbData
0x180015b79  lea     r9d, [rdi+3]; dwType
0x180015b7d  lea     rdx, c_szRegValFrom; "From"
0x180015b84  mov     [rsp+110h+phkResult], rax; lpData
0x180015b89  call    cs:__imp_RegSetValueExW
0x180015b8f  mov     ebx, eax
0x180015b91  test    eax, eax
0x180015b93  jnz     short loc_180015BF5
0x180015b95  mov     rcx, [rbp+57h+var_B0]; hKey
0x180015b99  lea     rax, [rbp+57h+var_80]
0x180015b9d  mov     [rsp+110h+cbData], esi; cbData
0x180015ba1  lea     r9d, [rdi+3]; dwType
0x180015ba5  xor     r8d, r8d; Reserved
0x180015ba8  mov     [rsp+110h+phkResult], rax; lpData
0x180015bad  lea     rdx, c_szRegValTo; "To"
0x180015bb4  call    cs:__imp_RegSetValueExW
0x180015bba  mov     ebx, eax
0x180015bbc  test    eax, eax
0x180015bbe  jnz     short loc_180015BF5
0x180015bc0  mov     rcx, [rbp+57h+var_B0]; hKey
0x180015bc4  test    rcx, rcx
0x180015bc7  jz      short loc_180015BD3
0x180015bc9  call    cs:__imp_RegCloseKey
0x180015bcf  mov     [rbp+57h+var_B0], rdi
0x180015bd3  mov     rcx, [rbp+57h+var_A8]; hKey
0x180015bd7  test    rcx, rcx
0x180015bda  jz      short loc_180015BE6
0x180015bdc  call    cs:__imp_RegCloseKey
0x180015be2  mov     [rbp+57h+var_A8], rdi
0x180015be6  mov     rcx, [rbp+57h+hKey]; hKey
0x180015bea  test    rcx, rcx
0x180015bed  jz      short loc_180015BF5
0x180015bef  call    cs:__imp_RegCloseKey
0x180015bf5  mov     eax, ebx
0x180015bf7  mov     rcx, [rbp+57h+var_30]
0x180015bfb  xor     rcx, rsp; StackCookie
0x180015bfe  call    __security_check_cookie
0x180015c03  add     rsp, 0F8h
0x180015c0a  pop     rdi
0x180015c0b  pop     rsi
0x180015c0c  pop     rbx
0x180015c0d  pop     rbp
0x180015c0e  retn
```
