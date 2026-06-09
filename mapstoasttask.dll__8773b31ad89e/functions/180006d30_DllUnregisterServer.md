# DllUnregisterServer

- ea: `0x180006d30`
- end: `0x180006ed0`
- name: `DllUnregisterServer`
- size: `416`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800015b0`
- `0x180001fe2`
- `0x180005d40`
- `0x180006d30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180006d8b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180006d8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ea4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ea4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006e29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006e90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006e29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006e90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006ddf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006e50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006ddf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006e50`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180006e0f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180006e75`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180006e0f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180006e75`

## string_xrefs

- `0x180006da0`: `CLSID\\%s`
- `0x180006e42`: `CLSID`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  HRESULT v0; // ebx
  LSTATUS v1; // eax
  LSTATUS v2; // eax
  LSTATUS v3; // eax
  LSTATUS v4; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  LPOLESTR lpsz; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-C0h] BYREF

  hKey = 0;
  memset_0(SubKey, 0, 0x208u);
  lpsz = 0;
  v0 = StringFromCLSID(&CLSID_MapsToastTask, &lpsz);
  if ( v0 >= 0 )
  {
    v0 = StringCchPrintfW(SubKey, 0x104u, L"CLSID\\\\%s", lpsz);
    if ( v0 >= 0 )
    {
      v1 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x2000000u, &hKey);
      v0 = v1;
      if ( v1 > 0 )
        v0 = (unsigned __int16)v1 | 0x80070000;
      if ( v0 >= 0 )
      {
        v2 = RegDeleteKeyExW(hKey, L"InprocServer32", 0, 0);
        v0 = v2;
        if ( v2 > 0 )
          v0 = (unsigned __int16)v2 | 0x80070000;
        if ( v0 >= 0 )
        {
          RegCloseKey(hKey);
          v3 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0x2000000u, &hKey);
          v0 = v3;
          if ( v3 > 0 )
            v0 = (unsigned __int16)v3 | 0x80070000;
          if ( v0 >= 0 )
          {
            v4 = RegDeleteKeyExW(hKey, lpsz, 0, 0);
            v0 = v4;
            if ( v4 > 0 )
              v0 = (unsigned __int16)v4 | 0x80070000;
          }
        }
      }
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CoTaskMemFree(lpsz);
  return v0;
}

```

## disassembly

```asm
0x180006d30  mov     [rsp-8+arg_0], rbx
0x180006d35  mov     [rsp-8+arg_8], rsi
0x180006d3a  push    rbp
0x180006d3b  lea     rbp, [rsp-160h]
0x180006d43  sub     rsp, 260h
0x180006d4a  mov     rax, cs:__security_cookie
0x180006d51  xor     rax, rsp
0x180006d54  mov     [rbp+160h+var_10], rax
0x180006d5b  xor     edx, edx; Val
0x180006d5d  mov     [rsp+260h+hKey], 0
0x180006d66  mov     r8d, 208h; Size
0x180006d6c  lea     rcx, [rsp+260h+SubKey]; void *
0x180006d71  call    memset_0
0x180006d76  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x180006d7b  mov     [rsp+260h+lpsz], 0
0x180006d84  lea     rcx, CLSID_MapsToastTask; rclsid
0x180006d8b  call    cs:__imp_StringFromCLSID
0x180006d91  mov     ebx, eax
0x180006d93  test    eax, eax
0x180006d95  js      loc_180006E86
0x180006d9b  mov     r9, [rsp+260h+lpsz]
0x180006da0  lea     r8, aClsidS; "CLSID\\\\%s"
0x180006da7  mov     edx, 104h; unsigned __int64
0x180006dac  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x180006db1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006db6  mov     ebx, eax
0x180006db8  test    eax, eax
0x180006dba  js      loc_180006E86
0x180006dc0  lea     rax, [rsp+260h+hKey]
0x180006dc5  mov     r9d, 2000000h; samDesired
0x180006dcb  xor     r8d, r8d; ulOptions
0x180006dce  mov     [rsp+260h+phkResult], rax; phkResult
0x180006dd3  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x180006dd8  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180006ddf  call    cs:__imp_RegOpenKeyExW
0x180006de5  mov     ebx, eax
0x180006de7  mov     esi, 80070000h
0x180006dec  test    eax, eax
0x180006dee  jle     short loc_180006DF5
0x180006df0  movzx   ebx, ax
0x180006df3  or      ebx, esi
0x180006df5  test    ebx, ebx
0x180006df7  js      loc_180006E86
0x180006dfd  mov     rcx, [rsp+260h+hKey]; hKey
0x180006e02  lea     rdx, SubKey; "InprocServer32"
0x180006e09  xor     r9d, r9d; Reserved
0x180006e0c  xor     r8d, r8d; samDesired
0x180006e0f  call    cs:__imp_RegDeleteKeyExW
0x180006e15  mov     ebx, eax
0x180006e17  test    eax, eax
0x180006e19  jle     short loc_180006E20
0x180006e1b  movzx   ebx, ax
0x180006e1e  or      ebx, esi
0x180006e20  test    ebx, ebx
0x180006e22  js      short loc_180006E86
0x180006e24  mov     rcx, [rsp+260h+hKey]; hKey
0x180006e29  call    cs:__imp_RegCloseKey
0x180006e2f  lea     rax, [rsp+260h+hKey]
0x180006e34  mov     r9d, 2000000h; samDesired
0x180006e3a  xor     r8d, r8d; ulOptions
0x180006e3d  mov     [rsp+260h+phkResult], rax; phkResult
0x180006e42  lea     rdx, aClsid; "CLSID"
0x180006e49  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180006e50  call    cs:__imp_RegOpenKeyExW
0x180006e56  mov     ebx, eax
0x180006e58  test    eax, eax
0x180006e5a  jle     short loc_180006E61
0x180006e5c  movzx   ebx, ax
0x180006e5f  or      ebx, esi
0x180006e61  test    ebx, ebx
0x180006e63  js      short loc_180006E86
0x180006e65  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x180006e6a  xor     r9d, r9d; Reserved
0x180006e6d  mov     rcx, [rsp+260h+hKey]; hKey
0x180006e72  xor     r8d, r8d; samDesired
0x180006e75  call    cs:__imp_RegDeleteKeyExW
0x180006e7b  mov     ebx, eax
0x180006e7d  test    eax, eax
0x180006e7f  jle     short loc_180006E86
0x180006e81  movzx   ebx, ax
0x180006e84  or      ebx, esi
0x180006e86  mov     rcx, [rsp+260h+hKey]; hKey
0x180006e8b  test    rcx, rcx
0x180006e8e  jz      short loc_180006E9F
0x180006e90  call    cs:__imp_RegCloseKey
0x180006e96  mov     [rsp+260h+hKey], 0
0x180006e9f  mov     rcx, [rsp+260h+lpsz]; pv
0x180006ea4  call    cs:__imp_CoTaskMemFree
0x180006eaa  mov     eax, ebx
0x180006eac  mov     rcx, [rbp+160h+var_10]
0x180006eb3  xor     rcx, rsp; StackCookie
0x180006eb6  call    __security_check_cookie
0x180006ebb  lea     r11, [rsp+260h+var_s0]
0x180006ec3  mov     rbx, [r11+10h]
0x180006ec7  mov     rsi, [r11+18h]
0x180006ecb  mov     rsp, r11
0x180006ece  pop     rbp
0x180006ecf  retn
```
