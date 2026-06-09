# DllUnregisterServer

- ea: `0x180002c30`
- end: `0x180002dd0`
- name: `DllUnregisterServer`
- size: `416`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d96`
- `0x1800026b0`
- `0x180002c30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180002c8b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180002c8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002da4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002da4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180002d0f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180002d75`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180002d0f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180002d75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002d29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002d90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002d29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002d90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002cdf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002d50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002cdf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002d50`

## string_xrefs

- `0x180002ca0`: `CLSID\\%s`
- `0x180002d42`: `CLSID`

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
  v0 = StringFromCLSID(&CLSID_DsregTask, &lpsz);
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
0x180002c30  mov     [rsp-8+arg_0], rbx
0x180002c35  mov     [rsp-8+arg_8], rsi
0x180002c3a  push    rbp
0x180002c3b  lea     rbp, [rsp-160h]
0x180002c43  sub     rsp, 260h
0x180002c4a  mov     rax, cs:__security_cookie
0x180002c51  xor     rax, rsp
0x180002c54  mov     [rbp+160h+var_10], rax
0x180002c5b  xor     edx, edx; Val
0x180002c5d  mov     [rsp+260h+hKey], 0
0x180002c66  mov     r8d, 208h; Size
0x180002c6c  lea     rcx, [rsp+260h+SubKey]; void *
0x180002c71  call    memset_0
0x180002c76  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x180002c7b  mov     [rsp+260h+lpsz], 0
0x180002c84  lea     rcx, CLSID_DsregTask; rclsid
0x180002c8b  call    cs:__imp_StringFromCLSID
0x180002c91  mov     ebx, eax
0x180002c93  test    eax, eax
0x180002c95  js      loc_180002D86
0x180002c9b  mov     r9, [rsp+260h+lpsz]
0x180002ca0  lea     r8, aClsidS; "CLSID\\\\%s"
0x180002ca7  mov     edx, 104h; unsigned __int64
0x180002cac  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x180002cb1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002cb6  mov     ebx, eax
0x180002cb8  test    eax, eax
0x180002cba  js      loc_180002D86
0x180002cc0  lea     rax, [rsp+260h+hKey]
0x180002cc5  mov     r9d, 2000000h; samDesired
0x180002ccb  xor     r8d, r8d; ulOptions
0x180002cce  mov     [rsp+260h+phkResult], rax; phkResult
0x180002cd3  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x180002cd8  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002cdf  call    cs:__imp_RegOpenKeyExW
0x180002ce5  mov     ebx, eax
0x180002ce7  mov     esi, 80070000h
0x180002cec  test    eax, eax
0x180002cee  jle     short loc_180002CF5
0x180002cf0  movzx   ebx, ax
0x180002cf3  or      ebx, esi
0x180002cf5  test    ebx, ebx
0x180002cf7  js      loc_180002D86
0x180002cfd  mov     rcx, [rsp+260h+hKey]; hKey
0x180002d02  lea     rdx, SubKey; "InprocServer32"
0x180002d09  xor     r9d, r9d; Reserved
0x180002d0c  xor     r8d, r8d; samDesired
0x180002d0f  call    cs:__imp_RegDeleteKeyExW
0x180002d15  mov     ebx, eax
0x180002d17  test    eax, eax
0x180002d19  jle     short loc_180002D20
0x180002d1b  movzx   ebx, ax
0x180002d1e  or      ebx, esi
0x180002d20  test    ebx, ebx
0x180002d22  js      short loc_180002D86
0x180002d24  mov     rcx, [rsp+260h+hKey]; hKey
0x180002d29  call    cs:__imp_RegCloseKey
0x180002d2f  lea     rax, [rsp+260h+hKey]
0x180002d34  mov     r9d, 2000000h; samDesired
0x180002d3a  xor     r8d, r8d; ulOptions
0x180002d3d  mov     [rsp+260h+phkResult], rax; phkResult
0x180002d42  lea     rdx, aClsid; "CLSID"
0x180002d49  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002d50  call    cs:__imp_RegOpenKeyExW
0x180002d56  mov     ebx, eax
0x180002d58  test    eax, eax
0x180002d5a  jle     short loc_180002D61
0x180002d5c  movzx   ebx, ax
0x180002d5f  or      ebx, esi
0x180002d61  test    ebx, ebx
0x180002d63  js      short loc_180002D86
0x180002d65  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x180002d6a  xor     r9d, r9d; Reserved
0x180002d6d  mov     rcx, [rsp+260h+hKey]; hKey
0x180002d72  xor     r8d, r8d; samDesired
0x180002d75  call    cs:__imp_RegDeleteKeyExW
0x180002d7b  mov     ebx, eax
0x180002d7d  test    eax, eax
0x180002d7f  jle     short loc_180002D86
0x180002d81  movzx   ebx, ax
0x180002d84  or      ebx, esi
0x180002d86  mov     rcx, [rsp+260h+hKey]; hKey
0x180002d8b  test    rcx, rcx
0x180002d8e  jz      short loc_180002D9F
0x180002d90  call    cs:__imp_RegCloseKey
0x180002d96  mov     [rsp+260h+hKey], 0
0x180002d9f  mov     rcx, [rsp+260h+lpsz]; pv
0x180002da4  call    cs:__imp_CoTaskMemFree
0x180002daa  mov     eax, ebx
0x180002dac  mov     rcx, [rbp+160h+var_10]
0x180002db3  xor     rcx, rsp; StackCookie
0x180002db6  call    __security_check_cookie
0x180002dbb  lea     r11, [rsp+260h+var_s0]
0x180002dc3  mov     rbx, [r11+10h]
0x180002dc7  mov     rsi, [r11+18h]
0x180002dcb  mov     rsp, r11
0x180002dce  pop     rbp
0x180002dcf  retn
```
