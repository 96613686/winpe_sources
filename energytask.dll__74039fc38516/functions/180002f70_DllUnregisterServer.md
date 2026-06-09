# DllUnregisterServer

- ea: `0x180002f70`
- end: `0x180003110`
- name: `DllUnregisterServer`
- size: `416`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002c00`
- `0x180002f70`
- `0x180003a86`
- `0x180003ac0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180002fcb`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180002fcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800030e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800030e4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000304f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800030b5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000304f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800030b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003069`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800030d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003069`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800030d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000301f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003090`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000301f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003090`

## string_xrefs

- `0x180002fe0`: `CLSID\\%s`
- `0x180003082`: `CLSID`

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
  v0 = StringFromCLSID(&CLSID_EnergyTask, &lpsz);
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
0x180002f70  mov     [rsp-8+arg_0], rbx
0x180002f75  mov     [rsp-8+arg_8], rsi
0x180002f7a  push    rbp
0x180002f7b  lea     rbp, [rsp-160h]
0x180002f83  sub     rsp, 260h
0x180002f8a  mov     rax, cs:__security_cookie
0x180002f91  xor     rax, rsp
0x180002f94  mov     [rbp+160h+var_10], rax
0x180002f9b  xor     edx, edx; Val
0x180002f9d  mov     [rsp+260h+hKey], 0
0x180002fa6  mov     r8d, 208h; Size
0x180002fac  lea     rcx, [rsp+260h+SubKey]; void *
0x180002fb1  call    memset_0
0x180002fb6  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x180002fbb  mov     [rsp+260h+lpsz], 0
0x180002fc4  lea     rcx, CLSID_EnergyTask; rclsid
0x180002fcb  call    cs:__imp_StringFromCLSID
0x180002fd1  mov     ebx, eax
0x180002fd3  test    eax, eax
0x180002fd5  js      loc_1800030C6
0x180002fdb  mov     r9, [rsp+260h+lpsz]
0x180002fe0  lea     r8, aClsidS; "CLSID\\\\%s"
0x180002fe7  mov     edx, 104h; unsigned __int64
0x180002fec  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x180002ff1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002ff6  mov     ebx, eax
0x180002ff8  test    eax, eax
0x180002ffa  js      loc_1800030C6
0x180003000  lea     rax, [rsp+260h+hKey]
0x180003005  mov     r9d, 2000000h; samDesired
0x18000300b  xor     r8d, r8d; ulOptions
0x18000300e  mov     [rsp+260h+phkResult], rax; phkResult
0x180003013  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x180003018  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000301f  call    cs:__imp_RegOpenKeyExW
0x180003025  mov     ebx, eax
0x180003027  mov     esi, 80070000h
0x18000302c  test    eax, eax
0x18000302e  jle     short loc_180003035
0x180003030  movzx   ebx, ax
0x180003033  or      ebx, esi
0x180003035  test    ebx, ebx
0x180003037  js      loc_1800030C6
0x18000303d  mov     rcx, [rsp+260h+hKey]; hKey
0x180003042  lea     rdx, aInprocserver32; "InprocServer32"
0x180003049  xor     r9d, r9d; Reserved
0x18000304c  xor     r8d, r8d; samDesired
0x18000304f  call    cs:__imp_RegDeleteKeyExW
0x180003055  mov     ebx, eax
0x180003057  test    eax, eax
0x180003059  jle     short loc_180003060
0x18000305b  movzx   ebx, ax
0x18000305e  or      ebx, esi
0x180003060  test    ebx, ebx
0x180003062  js      short loc_1800030C6
0x180003064  mov     rcx, [rsp+260h+hKey]; hKey
0x180003069  call    cs:__imp_RegCloseKey
0x18000306f  lea     rax, [rsp+260h+hKey]
0x180003074  mov     r9d, 2000000h; samDesired
0x18000307a  xor     r8d, r8d; ulOptions
0x18000307d  mov     [rsp+260h+phkResult], rax; phkResult
0x180003082  lea     rdx, aClsid; "CLSID"
0x180003089  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180003090  call    cs:__imp_RegOpenKeyExW
0x180003096  mov     ebx, eax
0x180003098  test    eax, eax
0x18000309a  jle     short loc_1800030A1
0x18000309c  movzx   ebx, ax
0x18000309f  or      ebx, esi
0x1800030a1  test    ebx, ebx
0x1800030a3  js      short loc_1800030C6
0x1800030a5  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x1800030aa  xor     r9d, r9d; Reserved
0x1800030ad  mov     rcx, [rsp+260h+hKey]; hKey
0x1800030b2  xor     r8d, r8d; samDesired
0x1800030b5  call    cs:__imp_RegDeleteKeyExW
0x1800030bb  mov     ebx, eax
0x1800030bd  test    eax, eax
0x1800030bf  jle     short loc_1800030C6
0x1800030c1  movzx   ebx, ax
0x1800030c4  or      ebx, esi
0x1800030c6  mov     rcx, [rsp+260h+hKey]; hKey
0x1800030cb  test    rcx, rcx
0x1800030ce  jz      short loc_1800030DF
0x1800030d0  call    cs:__imp_RegCloseKey
0x1800030d6  mov     [rsp+260h+hKey], 0
0x1800030df  mov     rcx, [rsp+260h+lpsz]; pv
0x1800030e4  call    cs:__imp_CoTaskMemFree
0x1800030ea  mov     eax, ebx
0x1800030ec  mov     rcx, [rbp+160h+var_10]
0x1800030f3  xor     rcx, rsp; StackCookie
0x1800030f6  call    __security_check_cookie
0x1800030fb  lea     r11, [rsp+260h+var_s0]
0x180003103  mov     rbx, [r11+10h]
0x180003107  mov     rsi, [r11+18h]
0x18000310b  mov     rsp, r11
0x18000310e  pop     rbp
0x18000310f  retn
```
