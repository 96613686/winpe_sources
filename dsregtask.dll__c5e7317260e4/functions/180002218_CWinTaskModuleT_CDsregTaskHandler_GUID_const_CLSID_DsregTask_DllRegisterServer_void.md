# CWinTaskModuleT<CDsregTaskHandler,&_GUID const CLSID_DsregTask>::DllRegisterServer(void)

- ea: `0x180002218`
- end: `0x1800023fb`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VCDsregTaskHandler@@$1?CLSID_DsregTask@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002c20`

## callees

- `0x180001460`
- `0x180001d96`
- `0x180002218`
- `0x1800026b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800022b4`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800022b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800023c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800023c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180002280`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180002280`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000231f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000231f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000236f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800023ad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000236f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800023ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800023d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800023d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000228f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000228f`

## string_xrefs

- `0x1800022c9`: `CLSID\\%s\InprocServer32`
- `0x180002398`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<CDsregTaskHandler,&_GUID const CLSID_DsregTask>::DllRegisterServer()
{
  signed int LastError; // eax
  int v1; // ebx
  LSTATUS v2; // eax
  __int64 v3; // rax
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  LPOLESTR lpsz; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+270h] [rbp+170h] BYREF

  hKey = 0;
  memset_0(Filename, 0, 0x208u);
  memset_0(SubKey, 0, 0x208u);
  lpsz = 0;
  if ( GetModuleFileNameW((HMODULE)0x180000000LL, Filename, 0x104u) )
    goto LABEL_5;
  LastError = GetLastError();
  v1 = LastError;
  if ( LastError > 0 )
    v1 = (unsigned __int16)LastError | 0x80070000;
  if ( v1 >= 0 )
  {
LABEL_5:
    v1 = StringFromCLSID(&CLSID_DsregTask, &lpsz);
    if ( v1 >= 0 )
    {
      v1 = StringCchPrintfW(SubKey, 0x104u, L"CLSID\\\\%s\\InprocServer32", lpsz);
      if ( v1 >= 0 )
      {
        v2 = RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
        v1 = v2;
        if ( v2 > 0 )
          v1 = (unsigned __int16)v2 | 0x80070000;
        if ( v1 >= 0 )
        {
          v3 = -1;
          do
            ++v3;
          while ( Filename[v3] );
          v4 = RegSetValueExW(hKey, 0, 0, 1u, (const BYTE *)Filename, 2 * v3 + 2);
          v1 = v4;
          if ( v4 > 0 )
            v1 = (unsigned __int16)v4 | 0x80070000;
          if ( v1 >= 0 )
          {
            v5 = RegSetValueExW(hKey, L"ThreadingModel", 0, 1u, L"Both", 0xAu);
            v1 = v5;
            if ( v5 > 0 )
              v1 = (unsigned __int16)v5 | 0x80070000;
          }
        }
      }
    }
  }
  CoTaskMemFree(lpsz);
  lpsz = 0;
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180002218  push    rbp
0x18000221a  push    rbx
0x18000221b  push    rsi
0x18000221c  push    rdi
0x18000221d  lea     rbp, [rsp-398h]
0x180002225  sub     rsp, 498h
0x18000222c  mov     rax, cs:__security_cookie
0x180002233  xor     rax, rsp
0x180002236  mov     [rbp+3B0h+var_30], rax
0x18000223d  mov     ebx, 208h
0x180002242  lea     rcx, [rsp+4B0h+Filename]; void *
0x180002247  xor     edi, edi
0x180002249  mov     r8d, ebx; Size
0x18000224c  xor     edx, edx; Val
0x18000224e  mov     [rsp+4B0h+hKey], rdi
0x180002253  call    memset_0
0x180002258  mov     r8d, ebx; Size
0x18000225b  lea     rcx, [rbp+3B0h+SubKey]; void *
0x180002262  xor     edx, edx; Val
0x180002264  call    memset_0
0x180002269  mov     r8d, 104h; nSize
0x18000226f  mov     [rsp+4B0h+lpsz], rdi
0x180002274  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x180002279  lea     rcx, cs:180000000h; hModule
0x180002280  call    cs:__imp_GetModuleFileNameW
0x180002286  mov     esi, 80070000h
0x18000228b  test    eax, eax
0x18000228d  jnz     short loc_1800022A8
0x18000228f  call    cs:__imp_GetLastError
0x180002295  mov     ebx, eax
0x180002297  test    eax, eax
0x180002299  jle     short loc_1800022A0
0x18000229b  movzx   ebx, ax
0x18000229e  or      ebx, esi
0x1800022a0  test    ebx, ebx
0x1800022a2  js      loc_1800023BE
0x1800022a8  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x1800022ad  lea     rcx, CLSID_DsregTask; rclsid
0x1800022b4  call    cs:__imp_StringFromCLSID
0x1800022ba  mov     ebx, eax
0x1800022bc  test    eax, eax
0x1800022be  js      loc_1800023BE
0x1800022c4  mov     r9, [rsp+4B0h+lpsz]
0x1800022c9  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x1800022d0  mov     edx, 104h; unsigned __int64
0x1800022d5  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x1800022dc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800022e1  mov     ebx, eax
0x1800022e3  test    eax, eax
0x1800022e5  js      loc_1800023BE
0x1800022eb  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x1800022f0  lea     rax, [rsp+4B0h+hKey]
0x1800022f5  mov     [rsp+4B0h+phkResult], rax; phkResult
0x1800022fa  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x180002301  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180002306  xor     r9d, r9d; lpClass
0x180002309  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x180002311  xor     r8d, r8d; Reserved
0x180002314  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000231b  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x18000231f  call    cs:__imp_RegCreateKeyExW
0x180002325  mov     ebx, eax
0x180002327  test    eax, eax
0x180002329  jle     short loc_180002330
0x18000232b  movzx   ebx, ax
0x18000232e  or      ebx, esi
0x180002330  test    ebx, ebx
0x180002332  js      loc_1800023BE
0x180002338  lea     rcx, [rsp+4B0h+Filename]
0x18000233d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002341  inc     rax
0x180002344  cmp     [rcx+rax*2], di
0x180002348  jnz     short loc_180002341
0x18000234a  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18000234f  lea     eax, ds:2[rax*2]
0x180002356  mov     [rsp+4B0h+samDesired], eax; cbData
0x18000235a  mov     r9d, 1; dwType
0x180002360  lea     rax, [rsp+4B0h+Filename]
0x180002365  xor     r8d, r8d; Reserved
0x180002368  xor     edx, edx; lpValueName
0x18000236a  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x18000236f  call    cs:__imp_RegSetValueExW
0x180002375  mov     ebx, eax
0x180002377  test    eax, eax
0x180002379  jle     short loc_180002380
0x18000237b  movzx   ebx, ax
0x18000237e  or      ebx, esi
0x180002380  test    ebx, ebx
0x180002382  js      short loc_1800023BE
0x180002384  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180002389  lea     rax, Data; "Both"
0x180002390  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x180002398  lea     rdx, ValueName; "ThreadingModel"
0x18000239f  mov     r9d, 1; dwType
0x1800023a5  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x1800023aa  xor     r8d, r8d; Reserved
0x1800023ad  call    cs:__imp_RegSetValueExW
0x1800023b3  mov     ebx, eax
0x1800023b5  test    eax, eax
0x1800023b7  jle     short loc_1800023BE
0x1800023b9  movzx   ebx, ax
0x1800023bc  or      ebx, esi
0x1800023be  mov     rcx, [rsp+4B0h+lpsz]; pv
0x1800023c3  call    cs:__imp_CoTaskMemFree
0x1800023c9  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1800023ce  mov     [rsp+4B0h+lpsz], rdi
0x1800023d3  test    rcx, rcx
0x1800023d6  jz      short loc_1800023DE
0x1800023d8  call    cs:__imp_RegCloseKey
0x1800023de  mov     eax, ebx
0x1800023e0  mov     rcx, [rbp+3B0h+var_30]
0x1800023e7  xor     rcx, rsp; StackCookie
0x1800023ea  call    __security_check_cookie
0x1800023ef  add     rsp, 498h
0x1800023f6  pop     rdi
0x1800023f7  pop     rsi
0x1800023f8  pop     rbx
0x1800023f9  pop     rbp
0x1800023fa  retn
```
