# CWinTaskModuleT<CmCleanupWim,&_GUID const CLSID_CmCleanup>::DllRegisterServer(void)

- ea: `0x180003e04`
- end: `0x180003fe7`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VCmCleanupWim@@$1?CLSID_CmCleanup@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007bd0`

## callees

- `0x180001510`
- `0x1800020c4`
- `0x180003e04`
- `0x180007370`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180003e6c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180003e6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003faf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003faf`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180003ea0`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180003ea0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e7b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003f5b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003f99`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003f5b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003f99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003fc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003fc4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003f0b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003f0b`

## string_xrefs

- `0x180003eb5`: `CLSID\\%s\InprocServer32`
- `0x180003f84`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<CmCleanupWim,&_GUID const CLSID_CmCleanup>::DllRegisterServer()
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
    v1 = StringFromCLSID(&CLSID_CmCleanup, &lpsz);
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
0x180003e04  push    rbp
0x180003e06  push    rbx
0x180003e07  push    rsi
0x180003e08  push    rdi
0x180003e09  lea     rbp, [rsp-398h]
0x180003e11  sub     rsp, 498h
0x180003e18  mov     rax, cs:__security_cookie
0x180003e1f  xor     rax, rsp
0x180003e22  mov     [rbp+3B0h+var_30], rax
0x180003e29  mov     ebx, 208h
0x180003e2e  lea     rcx, [rsp+4B0h+Filename]; void *
0x180003e33  xor     edi, edi
0x180003e35  mov     r8d, ebx; Size
0x180003e38  xor     edx, edx; Val
0x180003e3a  mov     [rsp+4B0h+hKey], rdi
0x180003e3f  call    memset_0
0x180003e44  mov     r8d, ebx; Size
0x180003e47  lea     rcx, [rbp+3B0h+SubKey]; void *
0x180003e4e  xor     edx, edx; Val
0x180003e50  call    memset_0
0x180003e55  mov     r8d, 104h; nSize
0x180003e5b  mov     [rsp+4B0h+lpsz], rdi
0x180003e60  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x180003e65  lea     rcx, __ImageBase; hModule
0x180003e6c  call    cs:__imp_GetModuleFileNameW
0x180003e72  mov     esi, 80070000h
0x180003e77  test    eax, eax
0x180003e79  jnz     short loc_180003E94
0x180003e7b  call    cs:__imp_GetLastError
0x180003e81  mov     ebx, eax
0x180003e83  test    eax, eax
0x180003e85  jle     short loc_180003E8C
0x180003e87  movzx   ebx, ax
0x180003e8a  or      ebx, esi
0x180003e8c  test    ebx, ebx
0x180003e8e  js      loc_180003FAA
0x180003e94  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x180003e99  lea     rcx, CLSID_CmCleanup; rclsid
0x180003ea0  call    cs:__imp_StringFromCLSID
0x180003ea6  mov     ebx, eax
0x180003ea8  test    eax, eax
0x180003eaa  js      loc_180003FAA
0x180003eb0  mov     r9, [rsp+4B0h+lpsz]
0x180003eb5  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x180003ebc  mov     edx, 104h; unsigned __int64
0x180003ec1  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x180003ec8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003ecd  mov     ebx, eax
0x180003ecf  test    eax, eax
0x180003ed1  js      loc_180003FAA
0x180003ed7  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x180003edc  lea     rax, [rsp+4B0h+hKey]
0x180003ee1  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180003ee6  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x180003eed  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180003ef2  xor     r9d, r9d; lpClass
0x180003ef5  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x180003efd  xor     r8d, r8d; Reserved
0x180003f00  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180003f07  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x180003f0b  call    cs:__imp_RegCreateKeyExW
0x180003f11  mov     ebx, eax
0x180003f13  test    eax, eax
0x180003f15  jle     short loc_180003F1C
0x180003f17  movzx   ebx, ax
0x180003f1a  or      ebx, esi
0x180003f1c  test    ebx, ebx
0x180003f1e  js      loc_180003FAA
0x180003f24  lea     rcx, [rsp+4B0h+Filename]
0x180003f29  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003f2d  inc     rax
0x180003f30  cmp     [rcx+rax*2], di
0x180003f34  jnz     short loc_180003F2D
0x180003f36  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180003f3b  lea     eax, ds:2[rax*2]
0x180003f42  mov     [rsp+4B0h+samDesired], eax; cbData
0x180003f46  mov     r9d, 1; dwType
0x180003f4c  lea     rax, [rsp+4B0h+Filename]
0x180003f51  xor     r8d, r8d; Reserved
0x180003f54  xor     edx, edx; lpValueName
0x180003f56  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180003f5b  call    cs:__imp_RegSetValueExW
0x180003f61  mov     ebx, eax
0x180003f63  test    eax, eax
0x180003f65  jle     short loc_180003F6C
0x180003f67  movzx   ebx, ax
0x180003f6a  or      ebx, esi
0x180003f6c  test    ebx, ebx
0x180003f6e  js      short loc_180003FAA
0x180003f70  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180003f75  lea     rax, Data; "Both"
0x180003f7c  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x180003f84  lea     rdx, ValueName; "ThreadingModel"
0x180003f8b  mov     r9d, 1; dwType
0x180003f91  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180003f96  xor     r8d, r8d; Reserved
0x180003f99  call    cs:__imp_RegSetValueExW
0x180003f9f  mov     ebx, eax
0x180003fa1  test    eax, eax
0x180003fa3  jle     short loc_180003FAA
0x180003fa5  movzx   ebx, ax
0x180003fa8  or      ebx, esi
0x180003faa  mov     rcx, [rsp+4B0h+lpsz]; pv
0x180003faf  call    cs:__imp_CoTaskMemFree
0x180003fb5  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180003fba  mov     [rsp+4B0h+lpsz], rdi
0x180003fbf  test    rcx, rcx
0x180003fc2  jz      short loc_180003FCA
0x180003fc4  call    cs:__imp_RegCloseKey
0x180003fca  mov     eax, ebx
0x180003fcc  mov     rcx, [rbp+3B0h+var_30]
0x180003fd3  xor     rcx, rsp; StackCookie
0x180003fd6  call    __security_check_cookie
0x180003fdb  add     rsp, 498h
0x180003fe2  pop     rdi
0x180003fe3  pop     rsi
0x180003fe4  pop     rbx
0x180003fe5  pop     rbp
0x180003fe6  retn
```
