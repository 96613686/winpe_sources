# CWinTaskModuleT<CNgcTasksHandler,&_GUID const CLSID_NgcTasks>::DllRegisterServer(void)

- ea: `0x180011ee0`
- end: `0x1800120c3`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VCNgcTasksHandler@@$1?CLSID_NgcTasks@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180015180`

## callees

- `0x180006330`
- `0x180006e9c`
- `0x18000df4c`
- `0x180011ee0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180011f48`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180011f48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f57`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180011f7c`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180011f7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001208b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001208b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012037`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012075`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012037`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012075`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800120a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800120a0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011fe7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011fe7`

## string_xrefs

- `0x180011f91`: `CLSID\\%s\InprocServer32`
- `0x180012060`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<CNgcTasksHandler,&_GUID const CLSID_NgcTasks>::DllRegisterServer()
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
  if ( GetModuleFileNameW((HMODULE)&_ImageBase, Filename, 0x104u) )
    goto LABEL_5;
  LastError = GetLastError();
  v1 = LastError;
  if ( LastError > 0 )
    v1 = (unsigned __int16)LastError | 0x80070000;
  if ( v1 >= 0 )
  {
LABEL_5:
    v1 = StringFromCLSID(&CLSID_NgcTasks, &lpsz);
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
0x180011ee0  push    rbp
0x180011ee2  push    rbx
0x180011ee3  push    rsi
0x180011ee4  push    rdi
0x180011ee5  lea     rbp, [rsp-398h]
0x180011eed  sub     rsp, 498h
0x180011ef4  mov     rax, cs:__security_cookie
0x180011efb  xor     rax, rsp
0x180011efe  mov     [rbp+3B0h+var_30], rax
0x180011f05  mov     ebx, 208h
0x180011f0a  lea     rcx, [rsp+4B0h+Filename]; void *
0x180011f0f  xor     edi, edi
0x180011f11  mov     r8d, ebx; Size
0x180011f14  xor     edx, edx; Val
0x180011f16  mov     [rsp+4B0h+hKey], rdi
0x180011f1b  call    memset_0
0x180011f20  mov     r8d, ebx; Size
0x180011f23  lea     rcx, [rbp+3B0h+SubKey]; void *
0x180011f2a  xor     edx, edx; Val
0x180011f2c  call    memset_0
0x180011f31  mov     r8d, 104h; nSize
0x180011f37  mov     [rsp+4B0h+lpsz], rdi
0x180011f3c  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x180011f41  lea     rcx, __ImageBase; hModule
0x180011f48  call    cs:__imp_GetModuleFileNameW
0x180011f4e  mov     esi, 80070000h
0x180011f53  test    eax, eax
0x180011f55  jnz     short loc_180011F70
0x180011f57  call    cs:__imp_GetLastError
0x180011f5d  mov     ebx, eax
0x180011f5f  test    eax, eax
0x180011f61  jle     short loc_180011F68
0x180011f63  movzx   ebx, ax
0x180011f66  or      ebx, esi
0x180011f68  test    ebx, ebx
0x180011f6a  js      loc_180012086
0x180011f70  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x180011f75  lea     rcx, CLSID_NgcTasks; rclsid
0x180011f7c  call    cs:__imp_StringFromCLSID
0x180011f82  mov     ebx, eax
0x180011f84  test    eax, eax
0x180011f86  js      loc_180012086
0x180011f8c  mov     r9, [rsp+4B0h+lpsz]
0x180011f91  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x180011f98  mov     edx, 104h; unsigned __int64
0x180011f9d  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x180011fa4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011fa9  mov     ebx, eax
0x180011fab  test    eax, eax
0x180011fad  js      loc_180012086
0x180011fb3  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x180011fb8  lea     rax, [rsp+4B0h+hKey]
0x180011fbd  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180011fc2  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x180011fc9  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180011fce  xor     r9d, r9d; lpClass
0x180011fd1  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x180011fd9  xor     r8d, r8d; Reserved
0x180011fdc  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180011fe3  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x180011fe7  call    cs:__imp_RegCreateKeyExW
0x180011fed  mov     ebx, eax
0x180011fef  test    eax, eax
0x180011ff1  jle     short loc_180011FF8
0x180011ff3  movzx   ebx, ax
0x180011ff6  or      ebx, esi
0x180011ff8  test    ebx, ebx
0x180011ffa  js      loc_180012086
0x180012000  lea     rcx, [rsp+4B0h+Filename]
0x180012005  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012009  inc     rax
0x18001200c  cmp     [rcx+rax*2], di
0x180012010  jnz     short loc_180012009
0x180012012  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180012017  lea     eax, ds:2[rax*2]
0x18001201e  mov     [rsp+4B0h+samDesired], eax; cbData
0x180012022  mov     r9d, 1; dwType
0x180012028  lea     rax, [rsp+4B0h+Filename]
0x18001202d  xor     r8d, r8d; Reserved
0x180012030  xor     edx, edx; lpValueName
0x180012032  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180012037  call    cs:__imp_RegSetValueExW
0x18001203d  mov     ebx, eax
0x18001203f  test    eax, eax
0x180012041  jle     short loc_180012048
0x180012043  movzx   ebx, ax
0x180012046  or      ebx, esi
0x180012048  test    ebx, ebx
0x18001204a  js      short loc_180012086
0x18001204c  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180012051  lea     rax, Data; "Both"
0x180012058  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x180012060  lea     rdx, aThreadingmodel; "ThreadingModel"
0x180012067  mov     r9d, 1; dwType
0x18001206d  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180012072  xor     r8d, r8d; Reserved
0x180012075  call    cs:__imp_RegSetValueExW
0x18001207b  mov     ebx, eax
0x18001207d  test    eax, eax
0x18001207f  jle     short loc_180012086
0x180012081  movzx   ebx, ax
0x180012084  or      ebx, esi
0x180012086  mov     rcx, [rsp+4B0h+lpsz]; pv
0x18001208b  call    cs:__imp_CoTaskMemFree
0x180012091  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180012096  mov     [rsp+4B0h+lpsz], rdi
0x18001209b  test    rcx, rcx
0x18001209e  jz      short loc_1800120A6
0x1800120a0  call    cs:__imp_RegCloseKey
0x1800120a6  mov     eax, ebx
0x1800120a8  mov     rcx, [rbp+3B0h+var_30]
0x1800120af  xor     rcx, rsp; StackCookie
0x1800120b2  call    __security_check_cookie
0x1800120b7  add     rsp, 498h
0x1800120be  pop     rdi
0x1800120bf  pop     rsi
0x1800120c0  pop     rbx
0x1800120c1  pop     rbp
0x1800120c2  retn
```
