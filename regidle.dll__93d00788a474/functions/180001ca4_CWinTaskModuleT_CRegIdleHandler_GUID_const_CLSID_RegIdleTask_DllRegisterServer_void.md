# CWinTaskModuleT<CRegIdleHandler,&_GUID const CLSID_RegIdleTask>::DllRegisterServer(void)

- ea: `0x180001ca4`
- end: `0x180001e87`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VCRegIdleHandler@@$1?CLSID_RegIdleTask@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800024a0`

## callees

- `0x180001ca4`
- `0x180002130`
- `0x1800029a6`
- `0x1800029d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180001e4f`
- `ole32!CoTaskMemFree` at `0x180001e4f`
- `ole32!StringFromCLSID` at `0x180001d40`
- `ole32!StringFromCLSID` at `0x180001d40`
- `ADVAPI32!RegSetValueExW` at `0x180001dfb`
- `ADVAPI32!RegSetValueExW` at `0x180001e39`
- `ADVAPI32!RegSetValueExW` at `0x180001dfb`
- `ADVAPI32!RegSetValueExW` at `0x180001e39`
- `ADVAPI32!RegCreateKeyExW` at `0x180001dab`
- `ADVAPI32!RegCreateKeyExW` at `0x180001dab`
- `ADVAPI32!RegCloseKey` at `0x180001e64`
- `ADVAPI32!RegCloseKey` at `0x180001e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d1b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180001d0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180001d0c`

## string_xrefs

- `0x180001d55`: `CLSID\\%s\InprocServer32`
- `0x180001e24`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<CRegIdleHandler,&_GUID const CLSID_RegIdleTask>::DllRegisterServer()
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
    v1 = StringFromCLSID(&CLSID_RegIdleTask, &lpsz);
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
0x180001ca4  push    rbp
0x180001ca6  push    rbx
0x180001ca7  push    rsi
0x180001ca8  push    rdi
0x180001ca9  lea     rbp, [rsp-398h]
0x180001cb1  sub     rsp, 498h
0x180001cb8  mov     rax, cs:__security_cookie
0x180001cbf  xor     rax, rsp
0x180001cc2  mov     [rbp+3B0h+var_30], rax
0x180001cc9  mov     ebx, 208h
0x180001cce  lea     rcx, [rsp+4B0h+Filename]; void *
0x180001cd3  xor     edi, edi
0x180001cd5  mov     r8d, ebx; Size
0x180001cd8  xor     edx, edx; Val
0x180001cda  mov     [rsp+4B0h+hKey], rdi
0x180001cdf  call    memset_0
0x180001ce4  mov     r8d, ebx; Size
0x180001ce7  lea     rcx, [rbp+3B0h+SubKey]; void *
0x180001cee  xor     edx, edx; Val
0x180001cf0  call    memset_0
0x180001cf5  mov     r8d, 104h; nSize
0x180001cfb  mov     [rsp+4B0h+lpsz], rdi
0x180001d00  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x180001d05  lea     rcx, cs:180000000h; hModule
0x180001d0c  call    cs:__imp_GetModuleFileNameW
0x180001d12  mov     esi, 80070000h
0x180001d17  test    eax, eax
0x180001d19  jnz     short loc_180001D34
0x180001d1b  call    cs:__imp_GetLastError
0x180001d21  mov     ebx, eax
0x180001d23  test    eax, eax
0x180001d25  jle     short loc_180001D2C
0x180001d27  movzx   ebx, ax
0x180001d2a  or      ebx, esi
0x180001d2c  test    ebx, ebx
0x180001d2e  js      loc_180001E4A
0x180001d34  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x180001d39  lea     rcx, CLSID_RegIdleTask; rclsid
0x180001d40  call    cs:__imp_StringFromCLSID
0x180001d46  mov     ebx, eax
0x180001d48  test    eax, eax
0x180001d4a  js      loc_180001E4A
0x180001d50  mov     r9, [rsp+4B0h+lpsz]
0x180001d55  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x180001d5c  mov     edx, 104h; unsigned __int64
0x180001d61  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x180001d68  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180001d6d  mov     ebx, eax
0x180001d6f  test    eax, eax
0x180001d71  js      loc_180001E4A
0x180001d77  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x180001d7c  lea     rax, [rsp+4B0h+hKey]
0x180001d81  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180001d86  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x180001d8d  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180001d92  xor     r9d, r9d; lpClass
0x180001d95  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x180001d9d  xor     r8d, r8d; Reserved
0x180001da0  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180001da7  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x180001dab  call    cs:__imp_RegCreateKeyExW
0x180001db1  mov     ebx, eax
0x180001db3  test    eax, eax
0x180001db5  jle     short loc_180001DBC
0x180001db7  movzx   ebx, ax
0x180001dba  or      ebx, esi
0x180001dbc  test    ebx, ebx
0x180001dbe  js      loc_180001E4A
0x180001dc4  lea     rcx, [rsp+4B0h+Filename]
0x180001dc9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001dcd  inc     rax
0x180001dd0  cmp     [rcx+rax*2], di
0x180001dd4  jnz     short loc_180001DCD
0x180001dd6  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180001ddb  lea     eax, ds:2[rax*2]
0x180001de2  mov     [rsp+4B0h+samDesired], eax; cbData
0x180001de6  mov     r9d, 1; dwType
0x180001dec  lea     rax, [rsp+4B0h+Filename]
0x180001df1  xor     r8d, r8d; Reserved
0x180001df4  xor     edx, edx; lpValueName
0x180001df6  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180001dfb  call    cs:__imp_RegSetValueExW
0x180001e01  mov     ebx, eax
0x180001e03  test    eax, eax
0x180001e05  jle     short loc_180001E0C
0x180001e07  movzx   ebx, ax
0x180001e0a  or      ebx, esi
0x180001e0c  test    ebx, ebx
0x180001e0e  js      short loc_180001E4A
0x180001e10  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180001e15  lea     rax, Data; "Both"
0x180001e1c  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x180001e24  lea     rdx, ValueName; "ThreadingModel"
0x180001e2b  mov     r9d, 1; dwType
0x180001e31  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180001e36  xor     r8d, r8d; Reserved
0x180001e39  call    cs:__imp_RegSetValueExW
0x180001e3f  mov     ebx, eax
0x180001e41  test    eax, eax
0x180001e43  jle     short loc_180001E4A
0x180001e45  movzx   ebx, ax
0x180001e48  or      ebx, esi
0x180001e4a  mov     rcx, [rsp+4B0h+lpsz]; pv
0x180001e4f  call    cs:__imp_CoTaskMemFree
0x180001e55  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180001e5a  mov     [rsp+4B0h+lpsz], rdi
0x180001e5f  test    rcx, rcx
0x180001e62  jz      short loc_180001E6A
0x180001e64  call    cs:__imp_RegCloseKey
0x180001e6a  mov     eax, ebx
0x180001e6c  mov     rcx, [rbp+3B0h+var_30]
0x180001e73  xor     rcx, rsp; StackCookie
0x180001e76  call    __security_check_cookie
0x180001e7b  add     rsp, 498h
0x180001e82  pop     rdi
0x180001e83  pop     rsi
0x180001e84  pop     rbx
0x180001e85  pop     rbp
0x180001e86  retn
```
