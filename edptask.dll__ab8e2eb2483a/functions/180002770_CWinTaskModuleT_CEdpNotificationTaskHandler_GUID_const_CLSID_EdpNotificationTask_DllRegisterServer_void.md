# CWinTaskModuleT<CEdpNotificationTaskHandler,&_GUID const CLSID_EdpNotificationTask>::DllRegisterServer(void)

- ea: `0x180002770`
- end: `0x180002953`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VCEdpNotificationTaskHandler@@$1?CLSID_EdpNotificationTask@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002e10`

## callees

- `0x180002770`
- `0x180002c00`
- `0x1800133e2`
- `0x180013410`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000291b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000291b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000280c`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000280c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800027d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800027d8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800028c7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002905`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800028c7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002905`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002877`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002877`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002930`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002930`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027e7`

## string_xrefs

- `0x180002821`: `CLSID\\%s\InprocServer32`
- `0x1800028f0`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<CEdpNotificationTaskHandler,&_GUID const CLSID_EdpNotificationTask>::DllRegisterServer()
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
    v1 = StringFromCLSID(&CLSID_EdpNotificationTask, &lpsz);
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
0x180002770  push    rbp
0x180002772  push    rbx
0x180002773  push    rsi
0x180002774  push    rdi
0x180002775  lea     rbp, [rsp-398h]
0x18000277d  sub     rsp, 498h
0x180002784  mov     rax, cs:__security_cookie
0x18000278b  xor     rax, rsp
0x18000278e  mov     [rbp+3B0h+var_30], rax
0x180002795  mov     ebx, 208h
0x18000279a  lea     rcx, [rsp+4B0h+Filename]; void *
0x18000279f  xor     edi, edi
0x1800027a1  mov     r8d, ebx; Size
0x1800027a4  xor     edx, edx; Val
0x1800027a6  mov     [rsp+4B0h+hKey], rdi
0x1800027ab  call    memset_0
0x1800027b0  mov     r8d, ebx; Size
0x1800027b3  lea     rcx, [rbp+3B0h+SubKey]; void *
0x1800027ba  xor     edx, edx; Val
0x1800027bc  call    memset_0
0x1800027c1  mov     r8d, 104h; nSize
0x1800027c7  mov     [rsp+4B0h+lpsz], rdi
0x1800027cc  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x1800027d1  lea     rcx, __ImageBase; hModule
0x1800027d8  call    cs:__imp_GetModuleFileNameW
0x1800027de  mov     esi, 80070000h
0x1800027e3  test    eax, eax
0x1800027e5  jnz     short loc_180002800
0x1800027e7  call    cs:__imp_GetLastError
0x1800027ed  mov     ebx, eax
0x1800027ef  test    eax, eax
0x1800027f1  jle     short loc_1800027F8
0x1800027f3  movzx   ebx, ax
0x1800027f6  or      ebx, esi
0x1800027f8  test    ebx, ebx
0x1800027fa  js      loc_180002916
0x180002800  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x180002805  lea     rcx, CLSID_EdpNotificationTask; rclsid
0x18000280c  call    cs:__imp_StringFromCLSID
0x180002812  mov     ebx, eax
0x180002814  test    eax, eax
0x180002816  js      loc_180002916
0x18000281c  mov     r9, [rsp+4B0h+lpsz]
0x180002821  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x180002828  mov     edx, 104h; unsigned __int64
0x18000282d  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x180002834  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002839  mov     ebx, eax
0x18000283b  test    eax, eax
0x18000283d  js      loc_180002916
0x180002843  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x180002848  lea     rax, [rsp+4B0h+hKey]
0x18000284d  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180002852  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x180002859  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000285e  xor     r9d, r9d; lpClass
0x180002861  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x180002869  xor     r8d, r8d; Reserved
0x18000286c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002873  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x180002877  call    cs:__imp_RegCreateKeyExW
0x18000287d  mov     ebx, eax
0x18000287f  test    eax, eax
0x180002881  jle     short loc_180002888
0x180002883  movzx   ebx, ax
0x180002886  or      ebx, esi
0x180002888  test    ebx, ebx
0x18000288a  js      loc_180002916
0x180002890  lea     rcx, [rsp+4B0h+Filename]
0x180002895  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002899  inc     rax
0x18000289c  cmp     [rcx+rax*2], di
0x1800028a0  jnz     short loc_180002899
0x1800028a2  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1800028a7  lea     eax, ds:2[rax*2]
0x1800028ae  mov     [rsp+4B0h+samDesired], eax; cbData
0x1800028b2  mov     r9d, 1; dwType
0x1800028b8  lea     rax, [rsp+4B0h+Filename]
0x1800028bd  xor     r8d, r8d; Reserved
0x1800028c0  xor     edx, edx; lpValueName
0x1800028c2  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x1800028c7  call    cs:__imp_RegSetValueExW
0x1800028cd  mov     ebx, eax
0x1800028cf  test    eax, eax
0x1800028d1  jle     short loc_1800028D8
0x1800028d3  movzx   ebx, ax
0x1800028d6  or      ebx, esi
0x1800028d8  test    ebx, ebx
0x1800028da  js      short loc_180002916
0x1800028dc  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1800028e1  lea     rax, Data; "Both"
0x1800028e8  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x1800028f0  lea     rdx, ValueName; "ThreadingModel"
0x1800028f7  mov     r9d, 1; dwType
0x1800028fd  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180002902  xor     r8d, r8d; Reserved
0x180002905  call    cs:__imp_RegSetValueExW
0x18000290b  mov     ebx, eax
0x18000290d  test    eax, eax
0x18000290f  jle     short loc_180002916
0x180002911  movzx   ebx, ax
0x180002914  or      ebx, esi
0x180002916  mov     rcx, [rsp+4B0h+lpsz]; pv
0x18000291b  call    cs:__imp_CoTaskMemFree
0x180002921  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180002926  mov     [rsp+4B0h+lpsz], rdi
0x18000292b  test    rcx, rcx
0x18000292e  jz      short loc_180002936
0x180002930  call    cs:__imp_RegCloseKey
0x180002936  mov     eax, ebx
0x180002938  mov     rcx, [rbp+3B0h+var_30]
0x18000293f  xor     rcx, rsp; StackCookie
0x180002942  call    __security_check_cookie
0x180002947  add     rsp, 498h
0x18000294e  pop     rdi
0x18000294f  pop     rsi
0x180002950  pop     rbx
0x180002951  pop     rbp
0x180002952  retn
```
