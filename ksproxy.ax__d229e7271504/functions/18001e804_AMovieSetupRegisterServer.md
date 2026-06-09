# AMovieSetupRegisterServer

- ea: `0x18001e804`
- end: `0x18001eb1d`
- name: `AMovieSetupRegisterServer`
- size: `793`
- prototype: `__int64 __fastcall(const GUID *, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18003de64`

## callees

- `0x18000909c`
- `0x180010ec4`
- `0x18001e804`
- `0x18001f620`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18001e93f`
- `ADVAPI32!RegCloseKey` at `0x18001ea3f`
- `ADVAPI32!RegCloseKey` at `0x18001eacd`
- `ADVAPI32!RegCloseKey` at `0x18001eade`
- `ADVAPI32!RegCloseKey` at `0x18001e93f`
- `ADVAPI32!RegCloseKey` at `0x18001ea3f`
- `ADVAPI32!RegCloseKey` at `0x18001eacd`
- `ADVAPI32!RegCloseKey` at `0x18001eade`
- `ADVAPI32!RegCreateKeyExW` at `0x18001e8ae`
- `ADVAPI32!RegCreateKeyExW` at `0x18001e9b4`
- `ADVAPI32!RegCreateKeyExW` at `0x18001e8ae`
- `ADVAPI32!RegCreateKeyExW` at `0x18001e9b4`
- `ADVAPI32!RegSetValueExW` at `0x18001e928`
- `ADVAPI32!RegSetValueExW` at `0x18001ea28`
- `ADVAPI32!RegSetValueExW` at `0x18001eaba`
- `ADVAPI32!RegSetValueExW` at `0x18001e928`
- `ADVAPI32!RegSetValueExW` at `0x18001ea28`
- `ADVAPI32!RegSetValueExW` at `0x18001eaba`
- `ole32!StringFromGUID2` at `0x18001e83e`
- `ole32!StringFromGUID2` at `0x18001e83e`

## string_xrefs

- `0x18001ea91`: `ThreadingModel`
- `0x18001e861`: `CLSID\%ls`

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
  result = StringCchLengthW(SubKey, 260, &v10);
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
      result = StringCchLengthW(SubKey, 260, &v10);
      if ( (int)result < 0 )
        return result;
      v7 = RegSetValueExW(phkResult, 0, 0, v7 + 1, (const BYTE *)SubKey, 2 * v10 + 2);
      if ( !v7 )
      {
        StringCchPrintfW(SubKey, 0x104u, L"%ls", L"Both");
        v10 = 0;
        result = StringCchLengthW(SubKey, 260, &v10);
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
0x18001e804  mov     [rsp-8+arg_18], rbx
0x18001e809  push    rbp
0x18001e80a  push    rdi
0x18001e80b  push    r14
0x18001e80d  lea     rbp, [rsp-1E0h]
0x18001e815  sub     rsp, 2E0h
0x18001e81c  mov     rax, cs:__security_cookie
0x18001e823  xor     rax, rsp
0x18001e826  mov     [rbp+1F0h+var_20], rax
0x18001e82d  mov     rdi, r8
0x18001e830  mov     rbx, rdx
0x18001e833  mov     r8d, 27h ; '''; cchMax
0x18001e839  lea     rdx, [rsp+2F0h+sz]; lpsz
0x18001e83e  call    cs:__imp_StringFromGUID2
0x18001e845  nop     dword ptr [rax+rax+00h]
0x18001e84a  mov     r14d, 104h
0x18001e850  mov     [rsp+2F0h+hKey], 0
0x18001e859  mov     edx, r14d; unsigned __int64
0x18001e85c  lea     r9, [rsp+2F0h+sz]
0x18001e861  lea     r8, aClsidLs; "CLSID\\%ls"
0x18001e868  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x18001e86c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e871  mov     [rsp+2F0h+lpdwDisposition], 0; lpdwDisposition
0x18001e87a  lea     rax, [rsp+2F0h+hKey]
0x18001e87f  mov     [rsp+2F0h+phkResult], rax; phkResult
0x18001e884  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x18001e888  mov     [rsp+2F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001e891  xor     r9d, r9d; lpClass
0x18001e894  mov     [rsp+2F0h+samDesired], 2000000h; samDesired
0x18001e89c  xor     r8d, r8d; Reserved
0x18001e89f  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18001e8a6  mov     [rsp+2F0h+dwOptions], 0; dwOptions
0x18001e8ae  call    cs:__imp_RegCreateKeyExW
0x18001e8b5  nop     dword ptr [rax+rax+00h]
0x18001e8ba  test    eax, eax
0x18001e8bc  jz      short loc_18001E8C8
0x18001e8be  or      eax, 80070000h
0x18001e8c3  jmp     loc_18001EAF9
0x18001e8c8  mov     r9, rbx
0x18001e8cb  lea     r8, aLs; "%ls"
0x18001e8d2  mov     rdx, r14; unsigned __int64
0x18001e8d5  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x18001e8d9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e8de  lea     r8, [rsp+2F0h+var_2A0]; unsigned __int64 *
0x18001e8e3  mov     [rsp+2F0h+var_2A0], 0
0x18001e8ec  mov     rdx, r14; unsigned __int64
0x18001e8ef  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x18001e8f3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001e8f8  test    eax, eax
0x18001e8fa  js      loc_18001EAF9
0x18001e900  mov     eax, dword ptr [rsp+2F0h+var_2A0]
0x18001e904  mov     r9d, 1; dwType
0x18001e90a  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18001e90f  xor     r8d, r8d; Reserved
0x18001e912  xor     edx, edx; lpValueName
0x18001e914  lea     eax, ds:2[rax*2]
0x18001e91b  mov     [rsp+2F0h+samDesired], eax; cbData
0x18001e91f  lea     rax, [rbp+1F0h+SubKey]
0x18001e923  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x18001e928  call    cs:__imp_RegSetValueExW
0x18001e92f  nop     dword ptr [rax+rax+00h]
0x18001e934  mov     ebx, eax
0x18001e936  test    eax, eax
0x18001e938  jz      short loc_18001E956
0x18001e93a  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18001e93f  call    cs:__imp_RegCloseKey
0x18001e946  nop     dword ptr [rax+rax+00h]
0x18001e94b  or      ebx, 80070000h
0x18001e951  jmp     loc_18001EAF7
0x18001e956  lea     r9, aInprocserver32; "InprocServer32"
0x18001e95d  mov     [rsp+2F0h+var_290], 0
0x18001e966  lea     r8, aLs; "%ls"
0x18001e96d  mov     rdx, r14; unsigned __int64
0x18001e970  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x18001e974  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e979  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18001e97e  lea     rax, [rsp+2F0h+var_290]
0x18001e983  mov     [rsp+2F0h+lpdwDisposition], 0; lpdwDisposition
0x18001e98c  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x18001e990  mov     [rsp+2F0h+phkResult], rax; phkResult
0x18001e995  xor     r9d, r9d; lpClass
0x18001e998  mov     [rsp+2F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001e9a1  xor     r8d, r8d; Reserved
0x18001e9a4  mov     [rsp+2F0h+samDesired], 2000000h; samDesired
0x18001e9ac  mov     [rsp+2F0h+dwOptions], 0; dwOptions
0x18001e9b4  call    cs:__imp_RegCreateKeyExW
0x18001e9bb  nop     dword ptr [rax+rax+00h]
0x18001e9c0  mov     ebx, eax
0x18001e9c2  test    eax, eax
0x18001e9c4  jnz     loc_18001E93A
0x18001e9ca  mov     r9, rdi
0x18001e9cd  lea     r8, aLs; "%ls"
0x18001e9d4  mov     rdx, r14; unsigned __int64
0x18001e9d7  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x18001e9db  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e9e0  lea     r8, [rsp+2F0h+var_2A0]; unsigned __int64 *
0x18001e9e5  mov     [rsp+2F0h+var_2A0], 0
0x18001e9ee  mov     rdx, r14; unsigned __int64
0x18001e9f1  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x18001e9f5  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001e9fa  test    eax, eax
0x18001e9fc  js      loc_18001EAF9
0x18001ea02  mov     eax, dword ptr [rsp+2F0h+var_2A0]
0x18001ea06  lea     r9d, [rbx+1]; dwType
0x18001ea0a  mov     rcx, [rsp+2F0h+var_290]; hKey
0x18001ea0f  xor     r8d, r8d; Reserved
0x18001ea12  xor     edx, edx; lpValueName
0x18001ea14  lea     eax, ds:2[rax*2]
0x18001ea1b  mov     [rsp+2F0h+samDesired], eax; cbData
0x18001ea1f  lea     rax, [rbp+1F0h+SubKey]
0x18001ea23  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x18001ea28  call    cs:__imp_RegSetValueExW
0x18001ea2f  nop     dword ptr [rax+rax+00h]
0x18001ea34  mov     ebx, eax
0x18001ea36  test    eax, eax
0x18001ea38  jz      short loc_18001EA55
0x18001ea3a  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18001ea3f  call    cs:__imp_RegCloseKey
0x18001ea46  nop     dword ptr [rax+rax+00h]
0x18001ea4b  mov     rcx, [rsp+2F0h+var_290]
0x18001ea50  jmp     loc_18001E93F
0x18001ea55  lea     r9, aBoth; "Both"
0x18001ea5c  mov     rdx, r14; unsigned __int64
0x18001ea5f  lea     r8, aLs; "%ls"
0x18001ea66  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x18001ea6a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001ea6f  lea     r8, [rsp+2F0h+var_2A0]; unsigned __int64 *
0x18001ea74  mov     [rsp+2F0h+var_2A0], 0
0x18001ea7d  mov     rdx, r14; unsigned __int64
0x18001ea80  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x18001ea84  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001ea89  test    eax, eax
0x18001ea8b  js      short loc_18001EAF9
0x18001ea8d  mov     eax, dword ptr [rsp+2F0h+var_2A0]
0x18001ea91  lea     rdx, aThreadingmodel; "ThreadingModel"
0x18001ea98  mov     rcx, [rsp+2F0h+var_290]; hKey
0x18001ea9d  mov     r9d, 1; dwType
0x18001eaa3  xor     r8d, r8d; Reserved
0x18001eaa6  lea     eax, ds:2[rax*2]
0x18001eaad  mov     [rsp+2F0h+samDesired], eax; cbData
0x18001eab1  lea     rax, [rbp+1F0h+SubKey]
0x18001eab5  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x18001eaba  call    cs:__imp_RegSetValueExW
0x18001eac1  nop     dword ptr [rax+rax+00h]
0x18001eac6  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18001eacb  mov     ebx, eax
0x18001eacd  call    cs:__imp_RegCloseKey
0x18001ead4  nop     dword ptr [rax+rax+00h]
0x18001ead9  mov     rcx, [rsp+2F0h+var_290]; hKey
0x18001eade  call    cs:__imp_RegCloseKey
0x18001eae5  nop     dword ptr [rax+rax+00h]
0x18001eaea  test    ebx, ebx
0x18001eaec  jle     short loc_18001EAF7
0x18001eaee  movzx   ebx, bx
0x18001eaf1  or      ebx, 80070000h
0x18001eaf7  mov     eax, ebx
0x18001eaf9  mov     rcx, [rbp+1F0h+var_20]
0x18001eb00  xor     rcx, rsp; StackCookie
0x18001eb03  call    __security_check_cookie
0x18001eb08  mov     rbx, [rsp+2F0h+arg_18]
0x18001eb10  add     rsp, 2E0h
0x18001eb17  pop     r14
0x18001eb19  pop     rdi
0x18001eb1a  pop     rbp
0x18001eb1b  retn
```
