# CWinTaskModuleT<CNgcTasksHandler,&_GUID const CLSID_NgcTasks>::DllUnregisterServer(void)

- ea: `0x1800120cc`
- end: `0x18001226c`
- name: `?DllUnregisterServer@?$CWinTaskModuleT@VCNgcTasksHandler@@$1?CLSID_NgcTasks@@3U_GUID@@B@@QEAAJXZ`
- size: `416`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180015190`

## callees

- `0x180006330`
- `0x180006e9c`
- `0x18000df4c`
- `0x1800120cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180012127`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180012127`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012240`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012240`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800121c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001222c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800121c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001222c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800121ab`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180012211`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800121ab`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180012211`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001217b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800121ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001217b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800121ec`

## string_xrefs

- `0x1800121de`: `CLSID`
- `0x18001213c`: `CLSID\\%s`

## pseudocode

```c
__int64 CWinTaskModuleT<CNgcTasksHandler,&_GUID const CLSID_NgcTasks>::DllUnregisterServer()
{
  int v0; // ebx
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
  v0 = StringFromCLSID(&CLSID_NgcTasks, &lpsz);
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
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1800120cc  mov     [rsp-8+arg_0], rbx
0x1800120d1  mov     [rsp-8+arg_8], rsi
0x1800120d6  push    rbp
0x1800120d7  lea     rbp, [rsp-160h]
0x1800120df  sub     rsp, 260h
0x1800120e6  mov     rax, cs:__security_cookie
0x1800120ed  xor     rax, rsp
0x1800120f0  mov     [rbp+160h+var_10], rax
0x1800120f7  xor     edx, edx; Val
0x1800120f9  mov     [rsp+260h+hKey], 0
0x180012102  mov     r8d, 208h; Size
0x180012108  lea     rcx, [rsp+260h+SubKey]; void *
0x18001210d  call    memset_0
0x180012112  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x180012117  mov     [rsp+260h+lpsz], 0
0x180012120  lea     rcx, CLSID_NgcTasks; rclsid
0x180012127  call    cs:__imp_StringFromCLSID
0x18001212d  mov     ebx, eax
0x18001212f  test    eax, eax
0x180012131  js      loc_180012222
0x180012137  mov     r9, [rsp+260h+lpsz]
0x18001213c  lea     r8, aClsidS; "CLSID\\\\%s"
0x180012143  mov     edx, 104h; unsigned __int64
0x180012148  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x18001214d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012152  mov     ebx, eax
0x180012154  test    eax, eax
0x180012156  js      loc_180012222
0x18001215c  lea     rax, [rsp+260h+hKey]
0x180012161  mov     r9d, 2000000h; samDesired
0x180012167  xor     r8d, r8d; ulOptions
0x18001216a  mov     [rsp+260h+phkResult], rax; phkResult
0x18001216f  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x180012174  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18001217b  call    cs:__imp_RegOpenKeyExW
0x180012181  mov     ebx, eax
0x180012183  mov     esi, 80070000h
0x180012188  test    eax, eax
0x18001218a  jle     short loc_180012191
0x18001218c  movzx   ebx, ax
0x18001218f  or      ebx, esi
0x180012191  test    ebx, ebx
0x180012193  js      loc_180012222
0x180012199  mov     rcx, [rsp+260h+hKey]; hKey
0x18001219e  lea     rdx, SubKey; "InprocServer32"
0x1800121a5  xor     r9d, r9d; Reserved
0x1800121a8  xor     r8d, r8d; samDesired
0x1800121ab  call    cs:__imp_RegDeleteKeyExW
0x1800121b1  mov     ebx, eax
0x1800121b3  test    eax, eax
0x1800121b5  jle     short loc_1800121BC
0x1800121b7  movzx   ebx, ax
0x1800121ba  or      ebx, esi
0x1800121bc  test    ebx, ebx
0x1800121be  js      short loc_180012222
0x1800121c0  mov     rcx, [rsp+260h+hKey]; hKey
0x1800121c5  call    cs:__imp_RegCloseKey
0x1800121cb  lea     rax, [rsp+260h+hKey]
0x1800121d0  mov     r9d, 2000000h; samDesired
0x1800121d6  xor     r8d, r8d; ulOptions
0x1800121d9  mov     [rsp+260h+phkResult], rax; phkResult
0x1800121de  lea     rdx, aClsid; "CLSID"
0x1800121e5  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800121ec  call    cs:__imp_RegOpenKeyExW
0x1800121f2  mov     ebx, eax
0x1800121f4  test    eax, eax
0x1800121f6  jle     short loc_1800121FD
0x1800121f8  movzx   ebx, ax
0x1800121fb  or      ebx, esi
0x1800121fd  test    ebx, ebx
0x1800121ff  js      short loc_180012222
0x180012201  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x180012206  xor     r9d, r9d; Reserved
0x180012209  mov     rcx, [rsp+260h+hKey]; hKey
0x18001220e  xor     r8d, r8d; samDesired
0x180012211  call    cs:__imp_RegDeleteKeyExW
0x180012217  mov     ebx, eax
0x180012219  test    eax, eax
0x18001221b  jle     short loc_180012222
0x18001221d  movzx   ebx, ax
0x180012220  or      ebx, esi
0x180012222  mov     rcx, [rsp+260h+hKey]; hKey
0x180012227  test    rcx, rcx
0x18001222a  jz      short loc_18001223B
0x18001222c  call    cs:__imp_RegCloseKey
0x180012232  mov     [rsp+260h+hKey], 0
0x18001223b  mov     rcx, [rsp+260h+lpsz]; pv
0x180012240  call    cs:__imp_CoTaskMemFree
0x180012246  mov     eax, ebx
0x180012248  mov     rcx, [rbp+160h+var_10]
0x18001224f  xor     rcx, rsp; StackCookie
0x180012252  call    __security_check_cookie
0x180012257  lea     r11, [rsp+260h+var_s0]
0x18001225f  mov     rbx, [r11+10h]
0x180012263  mov     rsi, [r11+18h]
0x180012267  mov     rsp, r11
0x18001226a  pop     rbp
0x18001226b  retn
```
