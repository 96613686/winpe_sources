# CWinTaskModuleT<CMapsToastTaskHandler,&_GUID const CLSID_MapsToastTask>::DllRegisterServer(void)

- ea: `0x180003560`
- end: `0x180003743`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VCMapsToastTaskHandler@@$1?CLSID_MapsToastTask@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006d20`

## callees

- `0x1800015b0`
- `0x180001fe2`
- `0x180003560`
- `0x180005d40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800035c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800035c8`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800035fc`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800035fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000370b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000370b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003720`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003720`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800036b7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800036f5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800036b7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800036f5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003667`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003667`

## string_xrefs

- `0x180003611`: `CLSID\\%s\InprocServer32`
- `0x1800036e0`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<CMapsToastTaskHandler,&_GUID const CLSID_MapsToastTask>::DllRegisterServer()
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
    v1 = StringFromCLSID(&CLSID_MapsToastTask, &lpsz);
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
0x180003560  push    rbp
0x180003562  push    rbx
0x180003563  push    rsi
0x180003564  push    rdi
0x180003565  lea     rbp, [rsp-398h]
0x18000356d  sub     rsp, 498h
0x180003574  mov     rax, cs:__security_cookie
0x18000357b  xor     rax, rsp
0x18000357e  mov     [rbp+3B0h+var_30], rax
0x180003585  mov     ebx, 208h
0x18000358a  lea     rcx, [rsp+4B0h+Filename]; void *
0x18000358f  xor     edi, edi
0x180003591  mov     r8d, ebx; Size
0x180003594  xor     edx, edx; Val
0x180003596  mov     [rsp+4B0h+hKey], rdi
0x18000359b  call    memset_0
0x1800035a0  mov     r8d, ebx; Size
0x1800035a3  lea     rcx, [rbp+3B0h+SubKey]; void *
0x1800035aa  xor     edx, edx; Val
0x1800035ac  call    memset_0
0x1800035b1  mov     r8d, 104h; nSize
0x1800035b7  mov     [rsp+4B0h+lpsz], rdi
0x1800035bc  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x1800035c1  lea     rcx, cs:180000000h; hModule
0x1800035c8  call    cs:__imp_GetModuleFileNameW
0x1800035ce  mov     esi, 80070000h
0x1800035d3  test    eax, eax
0x1800035d5  jnz     short loc_1800035F0
0x1800035d7  call    cs:__imp_GetLastError
0x1800035dd  mov     ebx, eax
0x1800035df  test    eax, eax
0x1800035e1  jle     short loc_1800035E8
0x1800035e3  movzx   ebx, ax
0x1800035e6  or      ebx, esi
0x1800035e8  test    ebx, ebx
0x1800035ea  js      loc_180003706
0x1800035f0  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x1800035f5  lea     rcx, CLSID_MapsToastTask; rclsid
0x1800035fc  call    cs:__imp_StringFromCLSID
0x180003602  mov     ebx, eax
0x180003604  test    eax, eax
0x180003606  js      loc_180003706
0x18000360c  mov     r9, [rsp+4B0h+lpsz]
0x180003611  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x180003618  mov     edx, 104h; unsigned __int64
0x18000361d  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x180003624  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003629  mov     ebx, eax
0x18000362b  test    eax, eax
0x18000362d  js      loc_180003706
0x180003633  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x180003638  lea     rax, [rsp+4B0h+hKey]
0x18000363d  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180003642  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x180003649  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000364e  xor     r9d, r9d; lpClass
0x180003651  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x180003659  xor     r8d, r8d; Reserved
0x18000365c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180003663  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x180003667  call    cs:__imp_RegCreateKeyExW
0x18000366d  mov     ebx, eax
0x18000366f  test    eax, eax
0x180003671  jle     short loc_180003678
0x180003673  movzx   ebx, ax
0x180003676  or      ebx, esi
0x180003678  test    ebx, ebx
0x18000367a  js      loc_180003706
0x180003680  lea     rcx, [rsp+4B0h+Filename]
0x180003685  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003689  inc     rax
0x18000368c  cmp     [rcx+rax*2], di
0x180003690  jnz     short loc_180003689
0x180003692  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180003697  lea     eax, ds:2[rax*2]
0x18000369e  mov     [rsp+4B0h+samDesired], eax; cbData
0x1800036a2  mov     r9d, 1; dwType
0x1800036a8  lea     rax, [rsp+4B0h+Filename]
0x1800036ad  xor     r8d, r8d; Reserved
0x1800036b0  xor     edx, edx; lpValueName
0x1800036b2  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x1800036b7  call    cs:__imp_RegSetValueExW
0x1800036bd  mov     ebx, eax
0x1800036bf  test    eax, eax
0x1800036c1  jle     short loc_1800036C8
0x1800036c3  movzx   ebx, ax
0x1800036c6  or      ebx, esi
0x1800036c8  test    ebx, ebx
0x1800036ca  js      short loc_180003706
0x1800036cc  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1800036d1  lea     rax, Data; "Both"
0x1800036d8  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x1800036e0  lea     rdx, ValueName; "ThreadingModel"
0x1800036e7  mov     r9d, 1; dwType
0x1800036ed  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x1800036f2  xor     r8d, r8d; Reserved
0x1800036f5  call    cs:__imp_RegSetValueExW
0x1800036fb  mov     ebx, eax
0x1800036fd  test    eax, eax
0x1800036ff  jle     short loc_180003706
0x180003701  movzx   ebx, ax
0x180003704  or      ebx, esi
0x180003706  mov     rcx, [rsp+4B0h+lpsz]; pv
0x18000370b  call    cs:__imp_CoTaskMemFree
0x180003711  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180003716  mov     [rsp+4B0h+lpsz], rdi
0x18000371b  test    rcx, rcx
0x18000371e  jz      short loc_180003726
0x180003720  call    cs:__imp_RegCloseKey
0x180003726  mov     eax, ebx
0x180003728  mov     rcx, [rbp+3B0h+var_30]
0x18000372f  xor     rcx, rsp; StackCookie
0x180003732  call    __security_check_cookie
0x180003737  add     rsp, 498h
0x18000373e  pop     rdi
0x18000373f  pop     rsi
0x180003740  pop     rbx
0x180003741  pop     rbp
0x180003742  retn
```
