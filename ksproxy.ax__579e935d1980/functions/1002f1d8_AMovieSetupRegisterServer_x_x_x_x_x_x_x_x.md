# AMovieSetupRegisterServer(x,x,x,x,x,x,x,x)

- ea: `0x1002f1d8`
- end: `0x1002f445`
- name: `_AMovieSetupRegisterServer@32`
- size: `621`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1002f547`

## callees

- `0x10006937`
- `0x1002f0a0`
- `0x1002f1d8`
- `0x1003aba0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1002f2d6`
- `ADVAPI32!RegCloseKey` at `0x1002f39b`
- `ADVAPI32!RegCloseKey` at `0x1002f415`
- `ADVAPI32!RegCloseKey` at `0x1002f421`
- `ADVAPI32!RegCloseKey` at `0x1002f2d6`
- `ADVAPI32!RegCloseKey` at `0x1002f39b`
- `ADVAPI32!RegCloseKey` at `0x1002f415`
- `ADVAPI32!RegCloseKey` at `0x1002f421`
- `ADVAPI32!RegCreateKeyExW` at `0x1002f254`
- `ADVAPI32!RegCreateKeyExW` at `0x1002f321`
- `ADVAPI32!RegCreateKeyExW` at `0x1002f254`
- `ADVAPI32!RegCreateKeyExW` at `0x1002f321`
- `ADVAPI32!RegSetValueExW` at `0x1002f2c4`
- `ADVAPI32!RegSetValueExW` at `0x1002f389`
- `ADVAPI32!RegSetValueExW` at `0x1002f407`
- `ADVAPI32!RegSetValueExW` at `0x1002f2c4`
- `ADVAPI32!RegSetValueExW` at `0x1002f389`
- `ADVAPI32!RegSetValueExW` at `0x1002f407`
- `ole32!StringFromGUID2` at `0x1002f212`
- `ole32!StringFromGUID2` at `0x1002f212`

## string_xrefs

- `0x1002f21c`: `CLSID\%ls`
- `0x1002f3fc`: `ThreadingModel`

## pseudocode

```c
int __fastcall AMovieSetupRegisterServer(int a1, int a2, unsigned int a3, int a4, int a5, int a6, int a7, int a8)
{
  LSTATUS v9; // eax
  int result; // eax
  LSTATUS v11; // esi
  LSTATUS v12; // esi
  unsigned int v13; // [esp+0h] [ebp-288h]
  unsigned int v14; // [esp+0h] [ebp-288h]
  unsigned int v15; // [esp+0h] [ebp-288h]
  unsigned int *v16; // [esp+4h] [ebp-284h]
  unsigned int *v17; // [esp+4h] [ebp-284h]
  unsigned int *v18; // [esp+4h] [ebp-284h]
  HKEY hKey; // [esp+10h] [ebp-278h] BYREF
  HKEY phkResult; // [esp+14h] [ebp-274h] BYREF
  unsigned __int16 v22[2]; // [esp+18h] [ebp-270h] BYREF
  GUID rguid; // [esp+1Ch] [ebp-26Ch] BYREF
  WCHAR SubKey[260]; // [esp+2Ch] [ebp-25Ch] BYREF
  OLECHAR sz[40]; // [esp+234h] [ebp-54h] BYREF

  rguid.Data1 = a3;
  *(_DWORD *)&rguid.Data2 = a4;
  *(_DWORD *)rguid.Data4 = a5;
  *(_DWORD *)&rguid.Data4[4] = a6;
  StringFromGUID2(&rguid, sz, 39);
  StringCchPrintfW(SubKey, 0x104u, L"CLSID\\%ls", sz);
  v9 = RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0x2000000u, 0, &phkResult, 0);
  if ( v9 )
    return v9 | 0x80070000;
  StringCchPrintfW(SubKey, 0x104u, L"%ls", a1);
  *(_DWORD *)v22 = 0;
  result = StringCchLengthW(v22, v13, v16);
  if ( result >= 0 )
  {
    v11 = RegSetValueExW(phkResult, 0, 0, 1u, (const BYTE *)SubKey, 2 * *(_DWORD *)v22 + 2);
    if ( v11
      || (StringCchPrintfW(SubKey, 0x104u, L"%ls", L"InprocServer32"),
          (v11 = RegCreateKeyExW(phkResult, SubKey, 0, 0, 0, 0x2000000u, 0, &hKey, 0)) != 0) )
    {
      RegCloseKey(phkResult);
      return v11 | 0x80070000;
    }
    StringCchPrintfW(SubKey, 0x104u, L"%ls", a2);
    *(_DWORD *)v22 = 0;
    result = StringCchLengthW(v22, v14, v17);
    if ( result >= 0 )
    {
      v11 = RegSetValueExW(hKey, 0, 0, 1u, (const BYTE *)SubKey, 2 * *(_DWORD *)v22 + 2);
      if ( v11 )
      {
        RegCloseKey(phkResult);
        RegCloseKey(hKey);
        return v11 | 0x80070000;
      }
      StringCchPrintfW(SubKey, 0x104u, L"%ls", L"Both");
      *(_DWORD *)v22 = 0;
      result = StringCchLengthW(v22, v15, v18);
      if ( result >= 0 )
      {
        v12 = RegSetValueExW(hKey, L"ThreadingModel", 0, 1u, (const BYTE *)SubKey, 2 * *(_DWORD *)v22 + 2);
        RegCloseKey(phkResult);
        RegCloseKey(hKey);
        result = (unsigned __int16)v12 | 0x80070000;
        if ( v12 <= 0 )
          return v12;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1002f1d8  mov     edi, edi
0x1002f1da  push    ebp
0x1002f1db  mov     ebp, esp
0x1002f1dd  sub     esp, 27Ch
0x1002f1e3  mov     eax, ___security_cookie
0x1002f1e8  xor     eax, ebp
0x1002f1ea  mov     [ebp+var_4], eax
0x1002f1ed  push    ebx
0x1002f1ee  push    esi; unsigned int *
0x1002f1ef  push    edi; unsigned int
0x1002f1f0  lea     esi, [ebp+arg_0]
0x1002f1f3  mov     [ebp+var_27C], edx
0x1002f1f9  lea     edi, [ebp+rguid]
0x1002f1ff  mov     ebx, ecx
0x1002f201  movsd
0x1002f202  lea     eax, [ebp+sz]
0x1002f205  push    27h ; '''; cchMax
0x1002f207  push    eax; lpsz
0x1002f208  lea     eax, [ebp+rguid]
0x1002f20e  movsd
0x1002f20f  push    eax; rguid
0x1002f210  movsd
0x1002f211  movsd
0x1002f212  call    ds:__imp__StringFromGUID2@12; StringFromGUID2(x,x,x)
0x1002f218  lea     eax, [ebp+sz]
0x1002f21b  push    eax
0x1002f21c  push    offset aClsidLs; "CLSID\\%ls"
0x1002f221  lea     eax, [ebp+SubKey]
0x1002f227  push    104h; unsigned int
0x1002f22c  push    eax; unsigned __int16 *
0x1002f22d  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x1002f232  add     esp, 10h
0x1002f235  lea     eax, [ebp+phkResult]
0x1002f23b  xor     edi, edi
0x1002f23d  push    edi; lpdwDisposition
0x1002f23e  push    eax; phkResult
0x1002f23f  push    edi; lpSecurityAttributes
0x1002f240  push    2000000h; samDesired
0x1002f245  push    edi; dwOptions
0x1002f246  push    edi; lpClass
0x1002f247  push    edi; Reserved
0x1002f248  lea     eax, [ebp+SubKey]
0x1002f24e  push    eax; lpSubKey
0x1002f24f  push    80000000h; hKey
0x1002f254  call    ds:__imp__RegCreateKeyExW@36; RegCreateKeyExW(x,x,x,x,x,x,x,x,x)
0x1002f25a  test    eax, eax
0x1002f25c  jz      short loc_1002F268
0x1002f25e  or      eax, 80070000h
0x1002f263  jmp     loc_1002F434
0x1002f268  push    ebx
0x1002f269  push    offset aLs; "%ls"
0x1002f26e  mov     ebx, 104h
0x1002f273  lea     eax, [ebp+SubKey]
0x1002f279  push    ebx; unsigned int
0x1002f27a  push    eax; unsigned __int16 *
0x1002f27b  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x1002f280  add     esp, 10h
0x1002f283  mov     dword ptr [ebp+var_270], edi
0x1002f289  lea     eax, [ebp+var_270]
0x1002f28f  mov     edx, ebx
0x1002f291  lea     ecx, [ebp+SubKey]
0x1002f297  push    eax; unsigned __int16 *
0x1002f298  call    ?StringCchLengthW@@YGJPBGIPAI@Z; StringCchLengthW(ushort const *,uint,uint *)
0x1002f29d  test    eax, eax
0x1002f29f  js      loc_1002F434
0x1002f2a5  mov     eax, dword ptr [ebp+var_270]
0x1002f2ab  lea     eax, ds:2[eax*2]
0x1002f2b2  push    eax; cbData
0x1002f2b3  lea     eax, [ebp+SubKey]
0x1002f2b9  push    eax; lpData
0x1002f2ba  push    1; dwType
0x1002f2bc  push    edi; Reserved
0x1002f2bd  push    edi; lpValueName
0x1002f2be  push    [ebp+phkResult]; hKey
0x1002f2c4  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x1002f2ca  mov     esi, eax
0x1002f2cc  test    esi, esi
0x1002f2ce  jz      short loc_1002F2E9
0x1002f2d0  push    [ebp+phkResult]; hKey
0x1002f2d6  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x1002f2dc  or      esi, 80070000h
0x1002f2e2  mov     eax, esi
0x1002f2e4  jmp     loc_1002F434
0x1002f2e9  push    offset aInprocserver32; "InprocServer32"
0x1002f2ee  push    offset aLs; "%ls"
0x1002f2f3  lea     eax, [ebp+SubKey]
0x1002f2f9  push    ebx; unsigned int
0x1002f2fa  push    eax; unsigned __int16 *
0x1002f2fb  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x1002f300  add     esp, 10h
0x1002f303  lea     eax, [ebp+hKey]
0x1002f309  push    edi; lpdwDisposition
0x1002f30a  push    eax; phkResult
0x1002f30b  push    edi; lpSecurityAttributes
0x1002f30c  push    2000000h; samDesired
0x1002f311  push    edi; dwOptions
0x1002f312  push    edi; lpClass
0x1002f313  push    edi; Reserved
0x1002f314  lea     eax, [ebp+SubKey]
0x1002f31a  push    eax; lpSubKey
0x1002f31b  push    [ebp+phkResult]; hKey
0x1002f321  call    ds:__imp__RegCreateKeyExW@36; RegCreateKeyExW(x,x,x,x,x,x,x,x,x)
0x1002f327  mov     esi, eax
0x1002f329  test    esi, esi
0x1002f32b  jnz     short loc_1002F2D0
0x1002f32d  push    [ebp+var_27C]
0x1002f333  lea     eax, [ebp+SubKey]
0x1002f339  push    offset aLs; "%ls"
0x1002f33e  push    ebx; unsigned int
0x1002f33f  push    eax; unsigned __int16 *
0x1002f340  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x1002f345  add     esp, 10h
0x1002f348  mov     dword ptr [ebp+var_270], edi
0x1002f34e  lea     eax, [ebp+var_270]
0x1002f354  mov     edx, ebx
0x1002f356  lea     ecx, [ebp+SubKey]
0x1002f35c  push    eax; unsigned __int16 *
0x1002f35d  call    ?StringCchLengthW@@YGJPBGIPAI@Z; StringCchLengthW(ushort const *,uint,uint *)
0x1002f362  test    eax, eax
0x1002f364  js      loc_1002F434
0x1002f36a  mov     eax, dword ptr [ebp+var_270]
0x1002f370  lea     eax, ds:2[eax*2]
0x1002f377  push    eax; cbData
0x1002f378  lea     eax, [ebp+SubKey]
0x1002f37e  push    eax; lpData
0x1002f37f  push    1; dwType
0x1002f381  push    edi; Reserved
0x1002f382  push    edi; lpValueName
0x1002f383  push    [ebp+hKey]; hKey
0x1002f389  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x1002f38f  mov     esi, eax
0x1002f391  test    esi, esi
0x1002f393  jz      short loc_1002F3AC
0x1002f395  push    [ebp+phkResult]; hKey
0x1002f39b  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x1002f3a1  push    [ebp+hKey]
0x1002f3a7  jmp     loc_1002F2D6
0x1002f3ac  push    offset aBoth; "Both"
0x1002f3b1  push    offset aLs; "%ls"
0x1002f3b6  lea     eax, [ebp+SubKey]
0x1002f3bc  push    ebx; unsigned int
0x1002f3bd  push    eax; unsigned __int16 *
0x1002f3be  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x1002f3c3  add     esp, 10h
0x1002f3c6  mov     dword ptr [ebp+var_270], edi
0x1002f3cc  lea     eax, [ebp+var_270]
0x1002f3d2  mov     edx, ebx
0x1002f3d4  lea     ecx, [ebp+SubKey]
0x1002f3da  push    eax; unsigned __int16 *
0x1002f3db  call    ?StringCchLengthW@@YGJPBGIPAI@Z; StringCchLengthW(ushort const *,uint,uint *)
0x1002f3e0  test    eax, eax
0x1002f3e2  js      short loc_1002F434
0x1002f3e4  mov     eax, dword ptr [ebp+var_270]
0x1002f3ea  lea     eax, ds:2[eax*2]
0x1002f3f1  push    eax; cbData
0x1002f3f2  lea     eax, [ebp+SubKey]
0x1002f3f8  push    eax; lpData
0x1002f3f9  push    1; dwType
0x1002f3fb  push    edi; Reserved
0x1002f3fc  push    offset aThreadingmodel; "ThreadingModel"
0x1002f401  push    [ebp+hKey]; hKey
0x1002f407  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x1002f40d  push    [ebp+phkResult]; hKey
0x1002f413  mov     esi, eax
0x1002f415  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x1002f41b  push    [ebp+hKey]; hKey
0x1002f421  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x1002f427  movzx   eax, si
0x1002f42a  or      eax, 80070000h
0x1002f42f  test    esi, esi
0x1002f431  cmovle  eax, esi
0x1002f434  mov     ecx, [ebp+var_4]
0x1002f437  pop     edi
0x1002f438  pop     esi
0x1002f439  xor     ecx, ebp; StackCookie
0x1002f43b  pop     ebx
0x1002f43c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002f441  leave
0x1002f442  retn    18h
```
