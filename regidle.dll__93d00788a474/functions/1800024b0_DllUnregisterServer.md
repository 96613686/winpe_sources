# DllUnregisterServer

- ea: `0x1800024b0`
- end: `0x180002650`
- name: `DllUnregisterServer`
- size: `416`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002130`
- `0x1800024b0`
- `0x1800029a6`
- `0x1800029d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180002624`
- `ole32!CoTaskMemFree` at `0x180002624`
- `ole32!StringFromCLSID` at `0x18000250b`
- `ole32!StringFromCLSID` at `0x18000250b`
- `ADVAPI32!RegDeleteKeyExW` at `0x18000258f`
- `ADVAPI32!RegDeleteKeyExW` at `0x1800025f5`
- `ADVAPI32!RegDeleteKeyExW` at `0x18000258f`
- `ADVAPI32!RegDeleteKeyExW` at `0x1800025f5`
- `ADVAPI32!RegCloseKey` at `0x1800025a9`
- `ADVAPI32!RegCloseKey` at `0x180002610`
- `ADVAPI32!RegCloseKey` at `0x1800025a9`
- `ADVAPI32!RegCloseKey` at `0x180002610`
- `ADVAPI32!RegOpenKeyExW` at `0x18000255f`
- `ADVAPI32!RegOpenKeyExW` at `0x1800025d0`
- `ADVAPI32!RegOpenKeyExW` at `0x18000255f`
- `ADVAPI32!RegOpenKeyExW` at `0x1800025d0`

## string_xrefs

- `0x180002520`: `CLSID\\%s`
- `0x1800025c2`: `CLSID`

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
  v0 = StringFromCLSID(&CLSID_RegIdleTask, &lpsz);
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
0x1800024b0  mov     [rsp-8+arg_0], rbx
0x1800024b5  mov     [rsp-8+arg_8], rsi
0x1800024ba  push    rbp
0x1800024bb  lea     rbp, [rsp-160h]
0x1800024c3  sub     rsp, 260h
0x1800024ca  mov     rax, cs:__security_cookie
0x1800024d1  xor     rax, rsp
0x1800024d4  mov     [rbp+160h+var_10], rax
0x1800024db  xor     edx, edx; Val
0x1800024dd  mov     [rsp+260h+hKey], 0
0x1800024e6  mov     r8d, 208h; Size
0x1800024ec  lea     rcx, [rsp+260h+SubKey]; void *
0x1800024f1  call    memset_0
0x1800024f6  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x1800024fb  mov     [rsp+260h+lpsz], 0
0x180002504  lea     rcx, CLSID_RegIdleTask; rclsid
0x18000250b  call    cs:__imp_StringFromCLSID
0x180002511  mov     ebx, eax
0x180002513  test    eax, eax
0x180002515  js      loc_180002606
0x18000251b  mov     r9, [rsp+260h+lpsz]
0x180002520  lea     r8, aClsidS; "CLSID\\\\%s"
0x180002527  mov     edx, 104h; unsigned __int64
0x18000252c  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x180002531  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002536  mov     ebx, eax
0x180002538  test    eax, eax
0x18000253a  js      loc_180002606
0x180002540  lea     rax, [rsp+260h+hKey]
0x180002545  mov     r9d, 2000000h; samDesired
0x18000254b  xor     r8d, r8d; ulOptions
0x18000254e  mov     [rsp+260h+phkResult], rax; phkResult
0x180002553  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x180002558  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000255f  call    cs:__imp_RegOpenKeyExW
0x180002565  mov     ebx, eax
0x180002567  mov     esi, 80070000h
0x18000256c  test    eax, eax
0x18000256e  jle     short loc_180002575
0x180002570  movzx   ebx, ax
0x180002573  or      ebx, esi
0x180002575  test    ebx, ebx
0x180002577  js      loc_180002606
0x18000257d  mov     rcx, [rsp+260h+hKey]; hKey
0x180002582  lea     rdx, SubKey; "InprocServer32"
0x180002589  xor     r9d, r9d; Reserved
0x18000258c  xor     r8d, r8d; samDesired
0x18000258f  call    cs:__imp_RegDeleteKeyExW
0x180002595  mov     ebx, eax
0x180002597  test    eax, eax
0x180002599  jle     short loc_1800025A0
0x18000259b  movzx   ebx, ax
0x18000259e  or      ebx, esi
0x1800025a0  test    ebx, ebx
0x1800025a2  js      short loc_180002606
0x1800025a4  mov     rcx, [rsp+260h+hKey]; hKey
0x1800025a9  call    cs:__imp_RegCloseKey
0x1800025af  lea     rax, [rsp+260h+hKey]
0x1800025b4  mov     r9d, 2000000h; samDesired
0x1800025ba  xor     r8d, r8d; ulOptions
0x1800025bd  mov     [rsp+260h+phkResult], rax; phkResult
0x1800025c2  lea     rdx, aClsid; "CLSID"
0x1800025c9  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800025d0  call    cs:__imp_RegOpenKeyExW
0x1800025d6  mov     ebx, eax
0x1800025d8  test    eax, eax
0x1800025da  jle     short loc_1800025E1
0x1800025dc  movzx   ebx, ax
0x1800025df  or      ebx, esi
0x1800025e1  test    ebx, ebx
0x1800025e3  js      short loc_180002606
0x1800025e5  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x1800025ea  xor     r9d, r9d; Reserved
0x1800025ed  mov     rcx, [rsp+260h+hKey]; hKey
0x1800025f2  xor     r8d, r8d; samDesired
0x1800025f5  call    cs:__imp_RegDeleteKeyExW
0x1800025fb  mov     ebx, eax
0x1800025fd  test    eax, eax
0x1800025ff  jle     short loc_180002606
0x180002601  movzx   ebx, ax
0x180002604  or      ebx, esi
0x180002606  mov     rcx, [rsp+260h+hKey]; hKey
0x18000260b  test    rcx, rcx
0x18000260e  jz      short loc_18000261F
0x180002610  call    cs:__imp_RegCloseKey
0x180002616  mov     [rsp+260h+hKey], 0
0x18000261f  mov     rcx, [rsp+260h+lpsz]; pv
0x180002624  call    cs:__imp_CoTaskMemFree
0x18000262a  mov     eax, ebx
0x18000262c  mov     rcx, [rbp+160h+var_10]
0x180002633  xor     rcx, rsp; StackCookie
0x180002636  call    __security_check_cookie
0x18000263b  lea     r11, [rsp+260h+var_s0]
0x180002643  mov     rbx, [r11+10h]
0x180002647  mov     rsi, [r11+18h]
0x18000264b  mov     rsp, r11
0x18000264e  pop     rbp
0x18000264f  retn
```
