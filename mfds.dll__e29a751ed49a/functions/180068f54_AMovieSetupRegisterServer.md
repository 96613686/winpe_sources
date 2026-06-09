# AMovieSetupRegisterServer

- ea: `0x180068f54`
- end: `0x18006926d`
- name: `AMovieSetupRegisterServer`
- size: `793`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800c541c`

## callees

- `0x180041794`
- `0x1800429e4`
- `0x180068f54`
- `0x180074160`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180068f8e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180068f8e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180068ffe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180069104`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180068ffe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180069104`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180069078`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180069178`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006920a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180069078`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180069178`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006920a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006908f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006918f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006921d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006922e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006908f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006918f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006921d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006922e`

## string_xrefs

- `0x1800691e1`: `ThreadingModel`
- `0x180068fb1`: `CLSID\%ls`

## pseudocode

```c
__int64 __fastcall AMovieSetupRegisterServer(const GUID *a1, __int64 a2, __int64 a3)
{
  LSTATUS v5; // eax
  __int64 result; // rax
  LSTATUS v7; // ebx
  HKEY v8; // rcx
  LSTATUS v9; // ebx
  unsigned __int64 v10; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR sz[40]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+C0h] [rbp-40h] BYREF

  StringFromGUID2(a1, sz, 39);
  hKey = 0;
  StringCchPrintfW(SubKey, 0x104u, L"CLSID\\%ls", sz);
  v5 = RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0x2000000u, 0, &hKey, 0);
  if ( v5 )
    return v5 | 0x80070000;
  StringCchPrintfW(SubKey, 0x104u, L"%ls", a2);
  v10 = 0;
  result = StringCchLengthW(SubKey, 0x104u, &v10);
  if ( (int)result >= 0 )
  {
    v7 = RegSetValueExW(hKey, 0, 0, 1u, (const BYTE *)SubKey, 2 * v10 + 2);
    if ( v7
      || (phkResult = 0,
          StringCchPrintfW(SubKey, 0x104u, L"%ls", L"InprocServer32"),
          (v7 = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x2000000u, 0, &phkResult, 0)) != 0) )
    {
      v8 = hKey;
    }
    else
    {
      StringCchPrintfW(SubKey, 0x104u, L"%ls", a3);
      v10 = 0;
      result = StringCchLengthW(SubKey, 0x104u, &v10);
      if ( (int)result < 0 )
        return result;
      v7 = RegSetValueExW(phkResult, 0, 0, v7 + 1, (const BYTE *)SubKey, 2 * v10 + 2);
      if ( !v7 )
      {
        StringCchPrintfW(SubKey, 0x104u, L"%ls", L"Both");
        v10 = 0;
        result = StringCchLengthW(SubKey, 0x104u, &v10);
        if ( (int)result < 0 )
          return result;
        v9 = RegSetValueExW(phkResult, L"ThreadingModel", 0, 1u, (const BYTE *)SubKey, 2 * v10 + 2);
        RegCloseKey(hKey);
        RegCloseKey(phkResult);
        if ( v9 > 0 )
          return (unsigned __int16)v9 | 0x80070000;
        return (unsigned int)v9;
      }
      RegCloseKey(hKey);
      v8 = phkResult;
    }
    RegCloseKey(v8);
    return v7 | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180068f54  mov     [rsp-8+arg_18], rbx
0x180068f59  push    rbp
0x180068f5a  push    rdi
0x180068f5b  push    r14
0x180068f5d  lea     rbp, [rsp-1E0h]
0x180068f65  sub     rsp, 2E0h
0x180068f6c  mov     rax, cs:__security_cookie
0x180068f73  xor     rax, rsp
0x180068f76  mov     [rbp+1F0h+var_20], rax
0x180068f7d  mov     rdi, r8
0x180068f80  mov     rbx, rdx
0x180068f83  mov     r8d, 27h ; '''; cchMax
0x180068f89  lea     rdx, [rsp+2F0h+sz]; lpsz
0x180068f8e  call    cs:__imp_StringFromGUID2
0x180068f95  nop     dword ptr [rax+rax+00h]
0x180068f9a  mov     r14d, 104h
0x180068fa0  mov     [rsp+2F0h+hKey], 0
0x180068fa9  mov     edx, r14d; unsigned __int64
0x180068fac  lea     r9, [rsp+2F0h+sz]
0x180068fb1  lea     r8, aClsidLs; "CLSID\\%ls"
0x180068fb8  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x180068fbc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180068fc1  mov     [rsp+2F0h+lpdwDisposition], 0; lpdwDisposition
0x180068fca  lea     rax, [rsp+2F0h+hKey]
0x180068fcf  mov     [rsp+2F0h+phkResult], rax; phkResult
0x180068fd4  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x180068fd8  mov     [rsp+2F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180068fe1  xor     r9d, r9d; lpClass
0x180068fe4  mov     [rsp+2F0h+samDesired], 2000000h; samDesired
0x180068fec  xor     r8d, r8d; Reserved
0x180068fef  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180068ff6  mov     [rsp+2F0h+dwOptions], 0; dwOptions
0x180068ffe  call    cs:__imp_RegCreateKeyExW
0x180069005  nop     dword ptr [rax+rax+00h]
0x18006900a  test    eax, eax
0x18006900c  jz      short loc_180069018
0x18006900e  or      eax, 80070000h
0x180069013  jmp     loc_180069249
0x180069018  mov     r9, rbx
0x18006901b  lea     r8, aLs; "%ls"
0x180069022  mov     rdx, r14; unsigned __int64
0x180069025  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x180069029  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006902e  lea     r8, [rsp+2F0h+var_2A0]; unsigned __int64 *
0x180069033  mov     [rsp+2F0h+var_2A0], 0
0x18006903c  mov     rdx, r14; unsigned __int64
0x18006903f  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x180069043  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180069048  test    eax, eax
0x18006904a  js      loc_180069249
0x180069050  mov     eax, dword ptr [rsp+2F0h+var_2A0]
0x180069054  mov     r9d, 1; dwType
0x18006905a  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18006905f  xor     r8d, r8d; Reserved
0x180069062  xor     edx, edx; lpValueName
0x180069064  lea     eax, ds:2[rax*2]
0x18006906b  mov     [rsp+2F0h+samDesired], eax; cbData
0x18006906f  lea     rax, [rbp+1F0h+SubKey]
0x180069073  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x180069078  call    cs:__imp_RegSetValueExW
0x18006907f  nop     dword ptr [rax+rax+00h]
0x180069084  mov     ebx, eax
0x180069086  test    eax, eax
0x180069088  jz      short loc_1800690A6
0x18006908a  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18006908f  call    cs:__imp_RegCloseKey
0x180069096  nop     dword ptr [rax+rax+00h]
0x18006909b  or      ebx, 80070000h
0x1800690a1  jmp     loc_180069247
0x1800690a6  lea     r9, aInprocserver32; "InprocServer32"
0x1800690ad  mov     [rsp+2F0h+var_290], 0
0x1800690b6  lea     r8, aLs; "%ls"
0x1800690bd  mov     rdx, r14; unsigned __int64
0x1800690c0  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x1800690c4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800690c9  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1800690ce  lea     rax, [rsp+2F0h+var_290]
0x1800690d3  mov     [rsp+2F0h+lpdwDisposition], 0; lpdwDisposition
0x1800690dc  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x1800690e0  mov     [rsp+2F0h+phkResult], rax; phkResult
0x1800690e5  xor     r9d, r9d; lpClass
0x1800690e8  mov     [rsp+2F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800690f1  xor     r8d, r8d; Reserved
0x1800690f4  mov     [rsp+2F0h+samDesired], 2000000h; samDesired
0x1800690fc  mov     [rsp+2F0h+dwOptions], 0; dwOptions
0x180069104  call    cs:__imp_RegCreateKeyExW
0x18006910b  nop     dword ptr [rax+rax+00h]
0x180069110  mov     ebx, eax
0x180069112  test    eax, eax
0x180069114  jnz     loc_18006908A
0x18006911a  mov     r9, rdi
0x18006911d  lea     r8, aLs; "%ls"
0x180069124  mov     rdx, r14; unsigned __int64
0x180069127  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x18006912b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180069130  lea     r8, [rsp+2F0h+var_2A0]; unsigned __int64 *
0x180069135  mov     [rsp+2F0h+var_2A0], 0
0x18006913e  mov     rdx, r14; unsigned __int64
0x180069141  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x180069145  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18006914a  test    eax, eax
0x18006914c  js      loc_180069249
0x180069152  mov     eax, dword ptr [rsp+2F0h+var_2A0]
0x180069156  lea     r9d, [rbx+1]; dwType
0x18006915a  mov     rcx, [rsp+2F0h+var_290]; hKey
0x18006915f  xor     r8d, r8d; Reserved
0x180069162  xor     edx, edx; lpValueName
0x180069164  lea     eax, ds:2[rax*2]
0x18006916b  mov     [rsp+2F0h+samDesired], eax; cbData
0x18006916f  lea     rax, [rbp+1F0h+SubKey]
0x180069173  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x180069178  call    cs:__imp_RegSetValueExW
0x18006917f  nop     dword ptr [rax+rax+00h]
0x180069184  mov     ebx, eax
0x180069186  test    eax, eax
0x180069188  jz      short loc_1800691A5
0x18006918a  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18006918f  call    cs:__imp_RegCloseKey
0x180069196  nop     dword ptr [rax+rax+00h]
0x18006919b  mov     rcx, [rsp+2F0h+var_290]
0x1800691a0  jmp     loc_18006908F
0x1800691a5  lea     r9, aBoth; "Both"
0x1800691ac  mov     rdx, r14; unsigned __int64
0x1800691af  lea     r8, aLs; "%ls"
0x1800691b6  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x1800691ba  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800691bf  lea     r8, [rsp+2F0h+var_2A0]; unsigned __int64 *
0x1800691c4  mov     [rsp+2F0h+var_2A0], 0
0x1800691cd  mov     rdx, r14; unsigned __int64
0x1800691d0  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x1800691d4  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800691d9  test    eax, eax
0x1800691db  js      short loc_180069249
0x1800691dd  mov     eax, dword ptr [rsp+2F0h+var_2A0]
0x1800691e1  lea     rdx, aThreadingmodel; "ThreadingModel"
0x1800691e8  mov     rcx, [rsp+2F0h+var_290]; hKey
0x1800691ed  mov     r9d, 1; dwType
0x1800691f3  xor     r8d, r8d; Reserved
0x1800691f6  lea     eax, ds:2[rax*2]
0x1800691fd  mov     [rsp+2F0h+samDesired], eax; cbData
0x180069201  lea     rax, [rbp+1F0h+SubKey]
0x180069205  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x18006920a  call    cs:__imp_RegSetValueExW
0x180069211  nop     dword ptr [rax+rax+00h]
0x180069216  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18006921b  mov     ebx, eax
0x18006921d  call    cs:__imp_RegCloseKey
0x180069224  nop     dword ptr [rax+rax+00h]
0x180069229  mov     rcx, [rsp+2F0h+var_290]; hKey
0x18006922e  call    cs:__imp_RegCloseKey
0x180069235  nop     dword ptr [rax+rax+00h]
0x18006923a  test    ebx, ebx
0x18006923c  jle     short loc_180069247
0x18006923e  movzx   ebx, bx
0x180069241  or      ebx, 80070000h
0x180069247  mov     eax, ebx
0x180069249  mov     rcx, [rbp+1F0h+var_20]
0x180069250  xor     rcx, rsp; StackCookie
0x180069253  call    __security_check_cookie
0x180069258  mov     rbx, [rsp+2F0h+arg_18]
0x180069260  add     rsp, 2E0h
0x180069267  pop     r14
0x180069269  pop     rdi
0x18006926a  pop     rbp
0x18006926b  retn
```
