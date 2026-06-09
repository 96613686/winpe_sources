# DllUnregisterServer

- ea: `0x180002e20`
- end: `0x180002fc0`
- name: `DllUnregisterServer`
- size: `416`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002c00`
- `0x180002e20`
- `0x1800133e2`
- `0x180013410`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002f94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002f94`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180002e7b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180002e7b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002ecf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002f40`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002ecf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002f40`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180002eff`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180002f65`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180002eff`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180002f65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002f19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002f80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002f19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002f80`

## string_xrefs

- `0x180002e90`: `CLSID\\%s`
- `0x180002f32`: `CLSID`

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
  v0 = StringFromCLSID(&CLSID_EdpNotificationTask, &lpsz);
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
0x180002e20  mov     [rsp-8+arg_0], rbx
0x180002e25  mov     [rsp-8+arg_8], rsi
0x180002e2a  push    rbp
0x180002e2b  lea     rbp, [rsp-160h]
0x180002e33  sub     rsp, 260h
0x180002e3a  mov     rax, cs:__security_cookie
0x180002e41  xor     rax, rsp
0x180002e44  mov     [rbp+160h+var_10], rax
0x180002e4b  xor     edx, edx; Val
0x180002e4d  mov     [rsp+260h+hKey], 0
0x180002e56  mov     r8d, 208h; Size
0x180002e5c  lea     rcx, [rsp+260h+SubKey]; void *
0x180002e61  call    memset_0
0x180002e66  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x180002e6b  mov     [rsp+260h+lpsz], 0
0x180002e74  lea     rcx, CLSID_EdpNotificationTask; rclsid
0x180002e7b  call    cs:__imp_StringFromCLSID
0x180002e81  mov     ebx, eax
0x180002e83  test    eax, eax
0x180002e85  js      loc_180002F76
0x180002e8b  mov     r9, [rsp+260h+lpsz]
0x180002e90  lea     r8, aClsidS; "CLSID\\\\%s"
0x180002e97  mov     edx, 104h; unsigned __int64
0x180002e9c  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x180002ea1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002ea6  mov     ebx, eax
0x180002ea8  test    eax, eax
0x180002eaa  js      loc_180002F76
0x180002eb0  lea     rax, [rsp+260h+hKey]
0x180002eb5  mov     r9d, 2000000h; samDesired
0x180002ebb  xor     r8d, r8d; ulOptions
0x180002ebe  mov     [rsp+260h+phkResult], rax; phkResult
0x180002ec3  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x180002ec8  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002ecf  call    cs:__imp_RegOpenKeyExW
0x180002ed5  mov     ebx, eax
0x180002ed7  mov     esi, 80070000h
0x180002edc  test    eax, eax
0x180002ede  jle     short loc_180002EE5
0x180002ee0  movzx   ebx, ax
0x180002ee3  or      ebx, esi
0x180002ee5  test    ebx, ebx
0x180002ee7  js      loc_180002F76
0x180002eed  mov     rcx, [rsp+260h+hKey]; hKey
0x180002ef2  lea     rdx, SubKey; "InprocServer32"
0x180002ef9  xor     r9d, r9d; Reserved
0x180002efc  xor     r8d, r8d; samDesired
0x180002eff  call    cs:__imp_RegDeleteKeyExW
0x180002f05  mov     ebx, eax
0x180002f07  test    eax, eax
0x180002f09  jle     short loc_180002F10
0x180002f0b  movzx   ebx, ax
0x180002f0e  or      ebx, esi
0x180002f10  test    ebx, ebx
0x180002f12  js      short loc_180002F76
0x180002f14  mov     rcx, [rsp+260h+hKey]; hKey
0x180002f19  call    cs:__imp_RegCloseKey
0x180002f1f  lea     rax, [rsp+260h+hKey]
0x180002f24  mov     r9d, 2000000h; samDesired
0x180002f2a  xor     r8d, r8d; ulOptions
0x180002f2d  mov     [rsp+260h+phkResult], rax; phkResult
0x180002f32  lea     rdx, aClsid; "CLSID"
0x180002f39  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002f40  call    cs:__imp_RegOpenKeyExW
0x180002f46  mov     ebx, eax
0x180002f48  test    eax, eax
0x180002f4a  jle     short loc_180002F51
0x180002f4c  movzx   ebx, ax
0x180002f4f  or      ebx, esi
0x180002f51  test    ebx, ebx
0x180002f53  js      short loc_180002F76
0x180002f55  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x180002f5a  xor     r9d, r9d; Reserved
0x180002f5d  mov     rcx, [rsp+260h+hKey]; hKey
0x180002f62  xor     r8d, r8d; samDesired
0x180002f65  call    cs:__imp_RegDeleteKeyExW
0x180002f6b  mov     ebx, eax
0x180002f6d  test    eax, eax
0x180002f6f  jle     short loc_180002F76
0x180002f71  movzx   ebx, ax
0x180002f74  or      ebx, esi
0x180002f76  mov     rcx, [rsp+260h+hKey]; hKey
0x180002f7b  test    rcx, rcx
0x180002f7e  jz      short loc_180002F8F
0x180002f80  call    cs:__imp_RegCloseKey
0x180002f86  mov     [rsp+260h+hKey], 0
0x180002f8f  mov     rcx, [rsp+260h+lpsz]; pv
0x180002f94  call    cs:__imp_CoTaskMemFree
0x180002f9a  mov     eax, ebx
0x180002f9c  mov     rcx, [rbp+160h+var_10]
0x180002fa3  xor     rcx, rsp; StackCookie
0x180002fa6  call    __security_check_cookie
0x180002fab  lea     r11, [rsp+260h+var_s0]
0x180002fb3  mov     rbx, [r11+10h]
0x180002fb7  mov     rsi, [r11+18h]
0x180002fbb  mov     rsp, r11
0x180002fbe  pop     rbp
0x180002fbf  retn
```
