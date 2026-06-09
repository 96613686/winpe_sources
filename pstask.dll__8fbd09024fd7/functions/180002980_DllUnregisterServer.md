# DllUnregisterServer

- ea: `0x180002980`
- end: `0x180002b20`
- name: `DllUnregisterServer`
- size: `416`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800024a0`
- `0x180002980`
- `0x180002bb6`
- `0x180002be0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180002af4`
- `ole32!CoTaskMemFree` at `0x180002af4`
- `ole32!StringFromCLSID` at `0x1800029db`
- `ole32!StringFromCLSID` at `0x1800029db`
- `ADVAPI32!RegDeleteKeyExW` at `0x180002a5f`
- `ADVAPI32!RegDeleteKeyExW` at `0x180002ac5`
- `ADVAPI32!RegDeleteKeyExW` at `0x180002a5f`
- `ADVAPI32!RegDeleteKeyExW` at `0x180002ac5`
- `ADVAPI32!RegCloseKey` at `0x180002a79`
- `ADVAPI32!RegCloseKey` at `0x180002ae0`
- `ADVAPI32!RegCloseKey` at `0x180002a79`
- `ADVAPI32!RegCloseKey` at `0x180002ae0`
- `ADVAPI32!RegOpenKeyExW` at `0x180002a2f`
- `ADVAPI32!RegOpenKeyExW` at `0x180002aa0`
- `ADVAPI32!RegOpenKeyExW` at `0x180002a2f`
- `ADVAPI32!RegOpenKeyExW` at `0x180002aa0`

## string_xrefs

- `0x1800029f0`: `CLSID\\%s`
- `0x180002a92`: `CLSID`

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
  v0 = StringFromCLSID(&CLSID_pstask, &lpsz);
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
0x180002980  mov     [rsp-8+arg_0], rbx
0x180002985  mov     [rsp-8+arg_8], rsi
0x18000298a  push    rbp
0x18000298b  lea     rbp, [rsp-160h]
0x180002993  sub     rsp, 260h
0x18000299a  mov     rax, cs:__security_cookie
0x1800029a1  xor     rax, rsp
0x1800029a4  mov     [rbp+160h+var_10], rax
0x1800029ab  xor     edx, edx; Val
0x1800029ad  mov     [rsp+260h+hKey], 0
0x1800029b6  mov     r8d, 208h; Size
0x1800029bc  lea     rcx, [rsp+260h+SubKey]; void *
0x1800029c1  call    memset_0
0x1800029c6  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x1800029cb  mov     [rsp+260h+lpsz], 0
0x1800029d4  lea     rcx, CLSID_pstask; rclsid
0x1800029db  call    cs:__imp_StringFromCLSID
0x1800029e1  mov     ebx, eax
0x1800029e3  test    eax, eax
0x1800029e5  js      loc_180002AD6
0x1800029eb  mov     r9, [rsp+260h+lpsz]
0x1800029f0  lea     r8, aClsidS; "CLSID\\\\%s"
0x1800029f7  mov     edx, 104h; unsigned __int64
0x1800029fc  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x180002a01  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002a06  mov     ebx, eax
0x180002a08  test    eax, eax
0x180002a0a  js      loc_180002AD6
0x180002a10  lea     rax, [rsp+260h+hKey]
0x180002a15  mov     r9d, 2000000h; samDesired
0x180002a1b  xor     r8d, r8d; ulOptions
0x180002a1e  mov     [rsp+260h+phkResult], rax; phkResult
0x180002a23  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x180002a28  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002a2f  call    cs:__imp_RegOpenKeyExW
0x180002a35  mov     ebx, eax
0x180002a37  mov     esi, 80070000h
0x180002a3c  test    eax, eax
0x180002a3e  jle     short loc_180002A45
0x180002a40  movzx   ebx, ax
0x180002a43  or      ebx, esi
0x180002a45  test    ebx, ebx
0x180002a47  js      loc_180002AD6
0x180002a4d  mov     rcx, [rsp+260h+hKey]; hKey
0x180002a52  lea     rdx, aInprocserver32; "InprocServer32"
0x180002a59  xor     r9d, r9d; Reserved
0x180002a5c  xor     r8d, r8d; samDesired
0x180002a5f  call    cs:__imp_RegDeleteKeyExW
0x180002a65  mov     ebx, eax
0x180002a67  test    eax, eax
0x180002a69  jle     short loc_180002A70
0x180002a6b  movzx   ebx, ax
0x180002a6e  or      ebx, esi
0x180002a70  test    ebx, ebx
0x180002a72  js      short loc_180002AD6
0x180002a74  mov     rcx, [rsp+260h+hKey]; hKey
0x180002a79  call    cs:__imp_RegCloseKey
0x180002a7f  lea     rax, [rsp+260h+hKey]
0x180002a84  mov     r9d, 2000000h; samDesired
0x180002a8a  xor     r8d, r8d; ulOptions
0x180002a8d  mov     [rsp+260h+phkResult], rax; phkResult
0x180002a92  lea     rdx, aClsid; "CLSID"
0x180002a99  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002aa0  call    cs:__imp_RegOpenKeyExW
0x180002aa6  mov     ebx, eax
0x180002aa8  test    eax, eax
0x180002aaa  jle     short loc_180002AB1
0x180002aac  movzx   ebx, ax
0x180002aaf  or      ebx, esi
0x180002ab1  test    ebx, ebx
0x180002ab3  js      short loc_180002AD6
0x180002ab5  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x180002aba  xor     r9d, r9d; Reserved
0x180002abd  mov     rcx, [rsp+260h+hKey]; hKey
0x180002ac2  xor     r8d, r8d; samDesired
0x180002ac5  call    cs:__imp_RegDeleteKeyExW
0x180002acb  mov     ebx, eax
0x180002acd  test    eax, eax
0x180002acf  jle     short loc_180002AD6
0x180002ad1  movzx   ebx, ax
0x180002ad4  or      ebx, esi
0x180002ad6  mov     rcx, [rsp+260h+hKey]; hKey
0x180002adb  test    rcx, rcx
0x180002ade  jz      short loc_180002AEF
0x180002ae0  call    cs:__imp_RegCloseKey
0x180002ae6  mov     [rsp+260h+hKey], 0
0x180002aef  mov     rcx, [rsp+260h+lpsz]; pv
0x180002af4  call    cs:__imp_CoTaskMemFree
0x180002afa  mov     eax, ebx
0x180002afc  mov     rcx, [rbp+160h+var_10]
0x180002b03  xor     rcx, rsp; StackCookie
0x180002b06  call    __security_check_cookie
0x180002b0b  lea     r11, [rsp+260h+var_s0]
0x180002b13  mov     rbx, [r11+10h]
0x180002b17  mov     rsi, [r11+18h]
0x180002b1b  mov     rsp, r11
0x180002b1e  pop     rbp
0x180002b1f  retn
```
