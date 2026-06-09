# DllUnregisterServer

- ea: `0x180007900`
- end: `0x180007aa0`
- name: `DllUnregisterServer`
- size: `416`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001be0`
- `0x180002612`
- `0x180006b40`
- `0x180007900`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000795b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000795b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007a74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007a74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800079f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800079f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a60`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800079df`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180007a45`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800079df`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180007a45`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800079af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007a20`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800079af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007a20`

## string_xrefs

- `0x180007970`: `CLSID\\%s`
- `0x180007a12`: `CLSID`

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
  v0 = StringFromCLSID(&CLSID_MapUpdateTask, &lpsz);
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
0x180007900  mov     [rsp-8+arg_0], rbx
0x180007905  mov     [rsp-8+arg_8], rsi
0x18000790a  push    rbp
0x18000790b  lea     rbp, [rsp-160h]
0x180007913  sub     rsp, 260h
0x18000791a  mov     rax, cs:__security_cookie
0x180007921  xor     rax, rsp
0x180007924  mov     [rbp+160h+var_10], rax
0x18000792b  xor     edx, edx; Val
0x18000792d  mov     [rsp+260h+hKey], 0
0x180007936  mov     r8d, 208h; Size
0x18000793c  lea     rcx, [rsp+260h+SubKey]; void *
0x180007941  call    memset_0
0x180007946  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x18000794b  mov     [rsp+260h+lpsz], 0
0x180007954  lea     rcx, CLSID_MapUpdateTask; rclsid
0x18000795b  call    cs:__imp_StringFromCLSID
0x180007961  mov     ebx, eax
0x180007963  test    eax, eax
0x180007965  js      loc_180007A56
0x18000796b  mov     r9, [rsp+260h+lpsz]
0x180007970  lea     r8, aClsidS; "CLSID\\\\%s"
0x180007977  mov     edx, 104h; unsigned __int64
0x18000797c  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x180007981  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007986  mov     ebx, eax
0x180007988  test    eax, eax
0x18000798a  js      loc_180007A56
0x180007990  lea     rax, [rsp+260h+hKey]
0x180007995  mov     r9d, 2000000h; samDesired
0x18000799b  xor     r8d, r8d; ulOptions
0x18000799e  mov     [rsp+260h+phkResult], rax; phkResult
0x1800079a3  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x1800079a8  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800079af  call    cs:__imp_RegOpenKeyExW
0x1800079b5  mov     ebx, eax
0x1800079b7  mov     esi, 80070000h
0x1800079bc  test    eax, eax
0x1800079be  jle     short loc_1800079C5
0x1800079c0  movzx   ebx, ax
0x1800079c3  or      ebx, esi
0x1800079c5  test    ebx, ebx
0x1800079c7  js      loc_180007A56
0x1800079cd  mov     rcx, [rsp+260h+hKey]; hKey
0x1800079d2  lea     rdx, SubKey; "InprocServer32"
0x1800079d9  xor     r9d, r9d; Reserved
0x1800079dc  xor     r8d, r8d; samDesired
0x1800079df  call    cs:__imp_RegDeleteKeyExW
0x1800079e5  mov     ebx, eax
0x1800079e7  test    eax, eax
0x1800079e9  jle     short loc_1800079F0
0x1800079eb  movzx   ebx, ax
0x1800079ee  or      ebx, esi
0x1800079f0  test    ebx, ebx
0x1800079f2  js      short loc_180007A56
0x1800079f4  mov     rcx, [rsp+260h+hKey]; hKey
0x1800079f9  call    cs:__imp_RegCloseKey
0x1800079ff  lea     rax, [rsp+260h+hKey]
0x180007a04  mov     r9d, 2000000h; samDesired
0x180007a0a  xor     r8d, r8d; ulOptions
0x180007a0d  mov     [rsp+260h+phkResult], rax; phkResult
0x180007a12  lea     rdx, aClsid; "CLSID"
0x180007a19  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180007a20  call    cs:__imp_RegOpenKeyExW
0x180007a26  mov     ebx, eax
0x180007a28  test    eax, eax
0x180007a2a  jle     short loc_180007A31
0x180007a2c  movzx   ebx, ax
0x180007a2f  or      ebx, esi
0x180007a31  test    ebx, ebx
0x180007a33  js      short loc_180007A56
0x180007a35  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x180007a3a  xor     r9d, r9d; Reserved
0x180007a3d  mov     rcx, [rsp+260h+hKey]; hKey
0x180007a42  xor     r8d, r8d; samDesired
0x180007a45  call    cs:__imp_RegDeleteKeyExW
0x180007a4b  mov     ebx, eax
0x180007a4d  test    eax, eax
0x180007a4f  jle     short loc_180007A56
0x180007a51  movzx   ebx, ax
0x180007a54  or      ebx, esi
0x180007a56  mov     rcx, [rsp+260h+hKey]; hKey
0x180007a5b  test    rcx, rcx
0x180007a5e  jz      short loc_180007A6F
0x180007a60  call    cs:__imp_RegCloseKey
0x180007a66  mov     [rsp+260h+hKey], 0
0x180007a6f  mov     rcx, [rsp+260h+lpsz]; pv
0x180007a74  call    cs:__imp_CoTaskMemFree
0x180007a7a  mov     eax, ebx
0x180007a7c  mov     rcx, [rbp+160h+var_10]
0x180007a83  xor     rcx, rsp; StackCookie
0x180007a86  call    __security_check_cookie
0x180007a8b  lea     r11, [rsp+260h+var_s0]
0x180007a93  mov     rbx, [r11+10h]
0x180007a97  mov     rsi, [r11+18h]
0x180007a9b  mov     rsp, r11
0x180007a9e  pop     rbp
0x180007a9f  retn
```
