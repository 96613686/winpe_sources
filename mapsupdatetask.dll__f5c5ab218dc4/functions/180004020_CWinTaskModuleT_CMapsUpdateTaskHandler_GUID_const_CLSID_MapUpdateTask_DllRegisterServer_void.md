# CWinTaskModuleT<CMapsUpdateTaskHandler,&_GUID const CLSID_MapUpdateTask>::DllRegisterServer(void)

- ea: `0x180004020`
- end: `0x180004203`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VCMapsUpdateTaskHandler@@$1?CLSID_MapUpdateTask@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800078f0`

## callees

- `0x180001be0`
- `0x180002612`
- `0x180004020`
- `0x180006b40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004088`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004088`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800040bc`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800040bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800041cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800041cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004097`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004097`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004177`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800041b5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004177`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800041b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800041e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800041e0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004127`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004127`

## string_xrefs

- `0x1800040d1`: `CLSID\\%s\InprocServer32`
- `0x1800041a0`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<CMapsUpdateTaskHandler,&_GUID const CLSID_MapUpdateTask>::DllRegisterServer()
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
    v1 = StringFromCLSID(&CLSID_MapUpdateTask, &lpsz);
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
0x180004020  push    rbp
0x180004022  push    rbx
0x180004023  push    rsi
0x180004024  push    rdi
0x180004025  lea     rbp, [rsp-398h]
0x18000402d  sub     rsp, 498h
0x180004034  mov     rax, cs:__security_cookie
0x18000403b  xor     rax, rsp
0x18000403e  mov     [rbp+3B0h+var_30], rax
0x180004045  mov     ebx, 208h
0x18000404a  lea     rcx, [rsp+4B0h+Filename]; void *
0x18000404f  xor     edi, edi
0x180004051  mov     r8d, ebx; Size
0x180004054  xor     edx, edx; Val
0x180004056  mov     [rsp+4B0h+hKey], rdi
0x18000405b  call    memset_0
0x180004060  mov     r8d, ebx; Size
0x180004063  lea     rcx, [rbp+3B0h+SubKey]; void *
0x18000406a  xor     edx, edx; Val
0x18000406c  call    memset_0
0x180004071  mov     r8d, 104h; nSize
0x180004077  mov     [rsp+4B0h+lpsz], rdi
0x18000407c  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x180004081  lea     rcx, __ImageBase; hModule
0x180004088  call    cs:__imp_GetModuleFileNameW
0x18000408e  mov     esi, 80070000h
0x180004093  test    eax, eax
0x180004095  jnz     short loc_1800040B0
0x180004097  call    cs:__imp_GetLastError
0x18000409d  mov     ebx, eax
0x18000409f  test    eax, eax
0x1800040a1  jle     short loc_1800040A8
0x1800040a3  movzx   ebx, ax
0x1800040a6  or      ebx, esi
0x1800040a8  test    ebx, ebx
0x1800040aa  js      loc_1800041C6
0x1800040b0  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x1800040b5  lea     rcx, CLSID_MapUpdateTask; rclsid
0x1800040bc  call    cs:__imp_StringFromCLSID
0x1800040c2  mov     ebx, eax
0x1800040c4  test    eax, eax
0x1800040c6  js      loc_1800041C6
0x1800040cc  mov     r9, [rsp+4B0h+lpsz]
0x1800040d1  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x1800040d8  mov     edx, 104h; unsigned __int64
0x1800040dd  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x1800040e4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800040e9  mov     ebx, eax
0x1800040eb  test    eax, eax
0x1800040ed  js      loc_1800041C6
0x1800040f3  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x1800040f8  lea     rax, [rsp+4B0h+hKey]
0x1800040fd  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180004102  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x180004109  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000410e  xor     r9d, r9d; lpClass
0x180004111  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x180004119  xor     r8d, r8d; Reserved
0x18000411c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180004123  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x180004127  call    cs:__imp_RegCreateKeyExW
0x18000412d  mov     ebx, eax
0x18000412f  test    eax, eax
0x180004131  jle     short loc_180004138
0x180004133  movzx   ebx, ax
0x180004136  or      ebx, esi
0x180004138  test    ebx, ebx
0x18000413a  js      loc_1800041C6
0x180004140  lea     rcx, [rsp+4B0h+Filename]
0x180004145  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004149  inc     rax
0x18000414c  cmp     [rcx+rax*2], di
0x180004150  jnz     short loc_180004149
0x180004152  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180004157  lea     eax, ds:2[rax*2]
0x18000415e  mov     [rsp+4B0h+samDesired], eax; cbData
0x180004162  mov     r9d, 1; dwType
0x180004168  lea     rax, [rsp+4B0h+Filename]
0x18000416d  xor     r8d, r8d; Reserved
0x180004170  xor     edx, edx; lpValueName
0x180004172  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180004177  call    cs:__imp_RegSetValueExW
0x18000417d  mov     ebx, eax
0x18000417f  test    eax, eax
0x180004181  jle     short loc_180004188
0x180004183  movzx   ebx, ax
0x180004186  or      ebx, esi
0x180004188  test    ebx, ebx
0x18000418a  js      short loc_1800041C6
0x18000418c  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180004191  lea     rax, Data; "Both"
0x180004198  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x1800041a0  lea     rdx, ValueName; "ThreadingModel"
0x1800041a7  mov     r9d, 1; dwType
0x1800041ad  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x1800041b2  xor     r8d, r8d; Reserved
0x1800041b5  call    cs:__imp_RegSetValueExW
0x1800041bb  mov     ebx, eax
0x1800041bd  test    eax, eax
0x1800041bf  jle     short loc_1800041C6
0x1800041c1  movzx   ebx, ax
0x1800041c4  or      ebx, esi
0x1800041c6  mov     rcx, [rsp+4B0h+lpsz]; pv
0x1800041cb  call    cs:__imp_CoTaskMemFree
0x1800041d1  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1800041d6  mov     [rsp+4B0h+lpsz], rdi
0x1800041db  test    rcx, rcx
0x1800041de  jz      short loc_1800041E6
0x1800041e0  call    cs:__imp_RegCloseKey
0x1800041e6  mov     eax, ebx
0x1800041e8  mov     rcx, [rbp+3B0h+var_30]
0x1800041ef  xor     rcx, rsp; StackCookie
0x1800041f2  call    __security_check_cookie
0x1800041f7  add     rsp, 498h
0x1800041fe  pop     rdi
0x1800041ff  pop     rsi
0x180004200  pop     rbx
0x180004201  pop     rbp
0x180004202  retn
```
