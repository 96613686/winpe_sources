# DllUnregisterServer

- ea: `0x180007be0`
- end: `0x180007d80`
- name: `DllUnregisterServer`
- size: `416`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001510`
- `0x1800020c4`
- `0x180007370`
- `0x180007be0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007d54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007d54`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180007c3b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180007c3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007cd9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007d40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007cd9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007d40`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180007cbf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180007d25`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180007cbf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180007d25`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007c8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007d00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007c8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007d00`

## string_xrefs

- `0x180007c50`: `CLSID\\%s`
- `0x180007cf2`: `CLSID`

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
  v0 = StringFromCLSID(&CLSID_CmCleanup, &lpsz);
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
0x180007be0  mov     [rsp-8+arg_0], rbx
0x180007be5  mov     [rsp-8+arg_8], rsi
0x180007bea  push    rbp
0x180007beb  lea     rbp, [rsp-160h]
0x180007bf3  sub     rsp, 260h
0x180007bfa  mov     rax, cs:__security_cookie
0x180007c01  xor     rax, rsp
0x180007c04  mov     [rbp+160h+var_10], rax
0x180007c0b  xor     edx, edx; Val
0x180007c0d  mov     [rsp+260h+hKey], 0
0x180007c16  mov     r8d, 208h; Size
0x180007c1c  lea     rcx, [rsp+260h+SubKey]; void *
0x180007c21  call    memset_0
0x180007c26  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x180007c2b  mov     [rsp+260h+lpsz], 0
0x180007c34  lea     rcx, CLSID_CmCleanup; rclsid
0x180007c3b  call    cs:__imp_StringFromCLSID
0x180007c41  mov     ebx, eax
0x180007c43  test    eax, eax
0x180007c45  js      loc_180007D36
0x180007c4b  mov     r9, [rsp+260h+lpsz]
0x180007c50  lea     r8, aClsidS; "CLSID\\\\%s"
0x180007c57  mov     edx, 104h; unsigned __int64
0x180007c5c  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x180007c61  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007c66  mov     ebx, eax
0x180007c68  test    eax, eax
0x180007c6a  js      loc_180007D36
0x180007c70  lea     rax, [rsp+260h+hKey]
0x180007c75  mov     r9d, 2000000h; samDesired
0x180007c7b  xor     r8d, r8d; ulOptions
0x180007c7e  mov     [rsp+260h+phkResult], rax; phkResult
0x180007c83  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x180007c88  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180007c8f  call    cs:__imp_RegOpenKeyExW
0x180007c95  mov     ebx, eax
0x180007c97  mov     esi, 80070000h
0x180007c9c  test    eax, eax
0x180007c9e  jle     short loc_180007CA5
0x180007ca0  movzx   ebx, ax
0x180007ca3  or      ebx, esi
0x180007ca5  test    ebx, ebx
0x180007ca7  js      loc_180007D36
0x180007cad  mov     rcx, [rsp+260h+hKey]; hKey
0x180007cb2  lea     rdx, SubKey; "InprocServer32"
0x180007cb9  xor     r9d, r9d; Reserved
0x180007cbc  xor     r8d, r8d; samDesired
0x180007cbf  call    cs:__imp_RegDeleteKeyExW
0x180007cc5  mov     ebx, eax
0x180007cc7  test    eax, eax
0x180007cc9  jle     short loc_180007CD0
0x180007ccb  movzx   ebx, ax
0x180007cce  or      ebx, esi
0x180007cd0  test    ebx, ebx
0x180007cd2  js      short loc_180007D36
0x180007cd4  mov     rcx, [rsp+260h+hKey]; hKey
0x180007cd9  call    cs:__imp_RegCloseKey
0x180007cdf  lea     rax, [rsp+260h+hKey]
0x180007ce4  mov     r9d, 2000000h; samDesired
0x180007cea  xor     r8d, r8d; ulOptions
0x180007ced  mov     [rsp+260h+phkResult], rax; phkResult
0x180007cf2  lea     rdx, aClsid; "CLSID"
0x180007cf9  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180007d00  call    cs:__imp_RegOpenKeyExW
0x180007d06  mov     ebx, eax
0x180007d08  test    eax, eax
0x180007d0a  jle     short loc_180007D11
0x180007d0c  movzx   ebx, ax
0x180007d0f  or      ebx, esi
0x180007d11  test    ebx, ebx
0x180007d13  js      short loc_180007D36
0x180007d15  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x180007d1a  xor     r9d, r9d; Reserved
0x180007d1d  mov     rcx, [rsp+260h+hKey]; hKey
0x180007d22  xor     r8d, r8d; samDesired
0x180007d25  call    cs:__imp_RegDeleteKeyExW
0x180007d2b  mov     ebx, eax
0x180007d2d  test    eax, eax
0x180007d2f  jle     short loc_180007D36
0x180007d31  movzx   ebx, ax
0x180007d34  or      ebx, esi
0x180007d36  mov     rcx, [rsp+260h+hKey]; hKey
0x180007d3b  test    rcx, rcx
0x180007d3e  jz      short loc_180007D4F
0x180007d40  call    cs:__imp_RegCloseKey
0x180007d46  mov     [rsp+260h+hKey], 0
0x180007d4f  mov     rcx, [rsp+260h+lpsz]; pv
0x180007d54  call    cs:__imp_CoTaskMemFree
0x180007d5a  mov     eax, ebx
0x180007d5c  mov     rcx, [rbp+160h+var_10]
0x180007d63  xor     rcx, rsp; StackCookie
0x180007d66  call    __security_check_cookie
0x180007d6b  lea     r11, [rsp+260h+var_s0]
0x180007d73  mov     rbx, [r11+10h]
0x180007d77  mov     rsi, [r11+18h]
0x180007d7b  mov     rsp, r11
0x180007d7e  pop     rbp
0x180007d7f  retn
```
