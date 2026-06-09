# CWinTaskModuleT<CEnergyTaskHandler,&_GUID const CLSID_EnergyTask>::DllRegisterServer(void)

- ea: `0x180001df0`
- end: `0x180001fd3`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VCEnergyTaskHandler@@$1?CLSID_EnergyTask@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002f60`

## callees

- `0x180001df0`
- `0x180002c00`
- `0x180003a86`
- `0x180003ac0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180001e8c`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180001e8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001f9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001f9b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180001e58`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180001e58`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180001ef7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180001ef7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001fb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001fb0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180001f47`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180001f85`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180001f47`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180001f85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e67`

## string_xrefs

- `0x180001ea1`: `CLSID\\%s\InprocServer32`
- `0x180001f70`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<CEnergyTaskHandler,&_GUID const CLSID_EnergyTask>::DllRegisterServer()
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
    v1 = StringFromCLSID(&CLSID_EnergyTask, &lpsz);
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
0x180001df0  push    rbp
0x180001df2  push    rbx
0x180001df3  push    rsi
0x180001df4  push    rdi
0x180001df5  lea     rbp, [rsp-398h]
0x180001dfd  sub     rsp, 498h
0x180001e04  mov     rax, cs:__security_cookie
0x180001e0b  xor     rax, rsp
0x180001e0e  mov     [rbp+3B0h+var_30], rax
0x180001e15  mov     ebx, 208h
0x180001e1a  lea     rcx, [rsp+4B0h+Filename]; void *
0x180001e1f  xor     edi, edi
0x180001e21  mov     r8d, ebx; Size
0x180001e24  xor     edx, edx; Val
0x180001e26  mov     [rsp+4B0h+hKey], rdi
0x180001e2b  call    memset_0
0x180001e30  mov     r8d, ebx; Size
0x180001e33  lea     rcx, [rbp+3B0h+SubKey]; void *
0x180001e3a  xor     edx, edx; Val
0x180001e3c  call    memset_0
0x180001e41  mov     r8d, 104h; nSize
0x180001e47  mov     [rsp+4B0h+lpsz], rdi
0x180001e4c  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x180001e51  lea     rcx, __ImageBase; hModule
0x180001e58  call    cs:__imp_GetModuleFileNameW
0x180001e5e  mov     esi, 80070000h
0x180001e63  test    eax, eax
0x180001e65  jnz     short loc_180001E80
0x180001e67  call    cs:__imp_GetLastError
0x180001e6d  mov     ebx, eax
0x180001e6f  test    eax, eax
0x180001e71  jle     short loc_180001E78
0x180001e73  movzx   ebx, ax
0x180001e76  or      ebx, esi
0x180001e78  test    ebx, ebx
0x180001e7a  js      loc_180001F96
0x180001e80  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x180001e85  lea     rcx, CLSID_EnergyTask; rclsid
0x180001e8c  call    cs:__imp_StringFromCLSID
0x180001e92  mov     ebx, eax
0x180001e94  test    eax, eax
0x180001e96  js      loc_180001F96
0x180001e9c  mov     r9, [rsp+4B0h+lpsz]
0x180001ea1  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x180001ea8  mov     edx, 104h; unsigned __int64
0x180001ead  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x180001eb4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180001eb9  mov     ebx, eax
0x180001ebb  test    eax, eax
0x180001ebd  js      loc_180001F96
0x180001ec3  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x180001ec8  lea     rax, [rsp+4B0h+hKey]
0x180001ecd  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180001ed2  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x180001ed9  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180001ede  xor     r9d, r9d; lpClass
0x180001ee1  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x180001ee9  xor     r8d, r8d; Reserved
0x180001eec  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180001ef3  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x180001ef7  call    cs:__imp_RegCreateKeyExW
0x180001efd  mov     ebx, eax
0x180001eff  test    eax, eax
0x180001f01  jle     short loc_180001F08
0x180001f03  movzx   ebx, ax
0x180001f06  or      ebx, esi
0x180001f08  test    ebx, ebx
0x180001f0a  js      loc_180001F96
0x180001f10  lea     rcx, [rsp+4B0h+Filename]
0x180001f15  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001f19  inc     rax
0x180001f1c  cmp     [rcx+rax*2], di
0x180001f20  jnz     short loc_180001F19
0x180001f22  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180001f27  lea     eax, ds:2[rax*2]
0x180001f2e  mov     [rsp+4B0h+samDesired], eax; cbData
0x180001f32  mov     r9d, 1; dwType
0x180001f38  lea     rax, [rsp+4B0h+Filename]
0x180001f3d  xor     r8d, r8d; Reserved
0x180001f40  xor     edx, edx; lpValueName
0x180001f42  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180001f47  call    cs:__imp_RegSetValueExW
0x180001f4d  mov     ebx, eax
0x180001f4f  test    eax, eax
0x180001f51  jle     short loc_180001F58
0x180001f53  movzx   ebx, ax
0x180001f56  or      ebx, esi
0x180001f58  test    ebx, ebx
0x180001f5a  js      short loc_180001F96
0x180001f5c  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180001f61  lea     rax, Data; "Both"
0x180001f68  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x180001f70  lea     rdx, ValueName; "ThreadingModel"
0x180001f77  mov     r9d, 1; dwType
0x180001f7d  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180001f82  xor     r8d, r8d; Reserved
0x180001f85  call    cs:__imp_RegSetValueExW
0x180001f8b  mov     ebx, eax
0x180001f8d  test    eax, eax
0x180001f8f  jle     short loc_180001F96
0x180001f91  movzx   ebx, ax
0x180001f94  or      ebx, esi
0x180001f96  mov     rcx, [rsp+4B0h+lpsz]; pv
0x180001f9b  call    cs:__imp_CoTaskMemFree
0x180001fa1  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180001fa6  mov     [rsp+4B0h+lpsz], rdi
0x180001fab  test    rcx, rcx
0x180001fae  jz      short loc_180001FB6
0x180001fb0  call    cs:__imp_RegCloseKey
0x180001fb6  mov     eax, ebx
0x180001fb8  mov     rcx, [rbp+3B0h+var_30]
0x180001fbf  xor     rcx, rsp; StackCookie
0x180001fc2  call    __security_check_cookie
0x180001fc7  add     rsp, 498h
0x180001fce  pop     rdi
0x180001fcf  pop     rsi
0x180001fd0  pop     rbx
0x180001fd1  pop     rbp
0x180001fd2  retn
```
