# DeleteOtherPerUserSetting(ushort const *,bool,bool)

- ea: `0x180030c24`
- end: `0x180030dc9`
- name: `?DeleteOtherPerUserSetting@@YAJPEBG_N1@Z`
- size: `421`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180030624`

## callees

- `0x1800079b0`
- `0x18001f060`
- `0x18002fae4`
- `0x180030558`
- `0x180030c24`
- `0x18003f42c`
- `0x180041e18`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180030d5c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180030d5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030d75`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030d75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030c6c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030c6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030d40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030db8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030d40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030db8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030ce2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030ce2`

## string_xrefs

- `0x180030d55`: `msi.dll`
- `0x180030c5e`: `Software\Microsoft\Windows\CurrentVersion\NetCache`
- `0x180030c7d`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x180030cf3`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x180030d26`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x180030d84`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x180030d6b`: `MsiDeleteUserDataW`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DeleteOtherPerUserSetting(const unsigned __int16 *a1, char a2, char a3)
{
  unsigned int v6; // eax
  unsigned int v7; // eax
  int v8; // eax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  const char *v11; // r9
  unsigned int phkResult; // [rsp+20h] [rbp-48h]
  unsigned int phkResulta; // [rsp+20h] [rbp-48h]
  HKEY hKey[3]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]
  HKEY v17; // [rsp+A8h] [rbp+40h] BYREF

  hKey[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    hKey,
    0);
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\NetCache", 0, 0x20006u, hKey);
  if ( v6 )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0xF5,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
      (const char *)v6,
      phkResult);
  }
  else
  {
    v17 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v17,
      0);
    v7 = RegCreateKeyExW(hKey[0], L"PurgeAtNextLogoff", 0, 0, 0, 0x20006u, 0, &v17, 0);
    if ( v7 )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0xF8,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
        (const char *)v7,
        phkResulta);
    }
    else
    {
      v8 = SHRegSetString(v17, 0, a1, &qword_180061CC0);
      if ( v8 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xFA,
          (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
          (const char *)(unsigned int)v8);
    }
    if ( v17 )
      RegCloseKey(v17);
  }
  if ( !a2 || !a3 )
  {
    Library = LoadLibraryExW(L"msi.dll", 0, 0);
    v17 = (HKEY)Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "MsiDeleteUserDataW");
      if ( ProcAddress )
        ((void (__fastcall *)(const unsigned __int16 *, _QWORD, _QWORD))ProcAddress)(a1, 0, 0);
      else
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x10C,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
          v11);
    }
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v17);
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return 0;
}

```

## disassembly

```asm
0x180030c24  push    rbp
0x180030c26  push    rbx
0x180030c27  push    rsi
0x180030c28  push    rdi
0x180030c29  mov     rbp, rsp
0x180030c2c  sub     rsp, 68h
0x180030c30  mov     dil, r8b
0x180030c33  mov     sil, dl
0x180030c36  mov     rbx, rcx
0x180030c39  mov     [rbp+hKey], 0
0x180030c41  xor     edx, edx
0x180030c43  lea     rcx, [rbp+hKey]
0x180030c47  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180030c4c  lea     rax, [rbp+hKey]
0x180030c50  mov     [rsp+68h+phkResult], rax; unsigned int
0x180030c55  mov     r9d, 20006h; samDesired
0x180030c5b  xor     r8d, r8d; ulOptions
0x180030c5e  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180030c65  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180030c6c  call    cs:__imp_RegOpenKeyExW
0x180030c72  mov     rcx, [rbp+20h]; this
0x180030c76  test    eax, eax
0x180030c78  jz      short loc_180030C93
0x180030c7a  mov     r9d, eax; char *
0x180030c7d  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x180030c84  mov     edx, 0F5h; void *
0x180030c89  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180030c8e  jmp     loc_180030D46
0x180030c93  mov     [rbp+arg_18], 0
0x180030c9b  xor     edx, edx
0x180030c9d  lea     rcx, [rbp+arg_18]
0x180030ca1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180030ca6  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x180030caf  lea     rax, [rbp+arg_18]
0x180030cb3  mov     [rsp+68h+var_30], rax; phkResult
0x180030cb8  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180030cc1  mov     [rsp+68h+samDesired], 20006h; samDesired
0x180030cc9  mov     dword ptr [rsp+68h+phkResult], 0; int
0x180030cd1  xor     r9d, r9d; lpClass
0x180030cd4  xor     r8d, r8d; Reserved
0x180030cd7  lea     rdx, aPurgeatnextlog; "PurgeAtNextLogoff"
0x180030cde  mov     rcx, [rbp+hKey]; hKey
0x180030ce2  call    cs:__imp_RegCreateKeyExW
0x180030ce8  mov     rcx, [rbp+20h]; this
0x180030cec  test    eax, eax
0x180030cee  jz      short loc_180030D06
0x180030cf0  mov     r9d, eax; char *
0x180030cf3  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x180030cfa  mov     edx, 0F8h; void *
0x180030cff  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180030d04  jmp     short loc_180030D37
0x180030d06  lea     r9, qword_180061CC0; unsigned __int16 *
0x180030d0d  mov     r8, rbx; unsigned __int16 *
0x180030d10  xor     edx, edx; unsigned __int16 *
0x180030d12  mov     rcx, [rbp+arg_18]; hKey
0x180030d16  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180030d1b  mov     rcx, [rbp+20h]; this
0x180030d1f  test    eax, eax
0x180030d21  jns     short loc_180030D37
0x180030d23  mov     r9d, eax; char *
0x180030d26  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x180030d2d  mov     edx, 0FAh; void *
0x180030d32  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030d37  mov     rcx, [rbp+arg_18]; hKey
0x180030d3b  test    rcx, rcx
0x180030d3e  jz      short loc_180030D46
0x180030d40  call    cs:__imp_RegCloseKey
0x180030d46  test    sil, sil
0x180030d49  jz      short loc_180030D50
0x180030d4b  test    dil, dil
0x180030d4e  jnz     short loc_180030DAF
0x180030d50  xor     r8d, r8d; dwFlags
0x180030d53  xor     edx, edx; hFile
0x180030d55  lea     rcx, aMsiDll; "msi.dll"
0x180030d5c  call    cs:__imp_LoadLibraryExW
0x180030d62  mov     [rbp+arg_18], rax
0x180030d66  test    rax, rax
0x180030d69  jz      short loc_180030DA5
0x180030d6b  lea     rdx, aMsideleteuserd; "MsiDeleteUserDataW"
0x180030d72  mov     rcx, rax; hModule
0x180030d75  call    cs:__imp_GetProcAddress
0x180030d7b  mov     rcx, [rbp+20h]; this
0x180030d7f  test    rax, rax
0x180030d82  jnz     short loc_180030D97
0x180030d84  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x180030d8b  mov     edx, 10Ch; void *
0x180030d90  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180030d95  jmp     short loc_180030DA5
0x180030d97  xor     r8d, r8d
0x180030d9a  xor     edx, edx
0x180030d9c  mov     rcx, rbx
0x180030d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030da4  nop
0x180030da5  lea     rcx, [rbp+arg_18]
0x180030da9  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180030dae  nop
0x180030daf  mov     rcx, [rbp+hKey]; hKey
0x180030db3  test    rcx, rcx
0x180030db6  jz      short loc_180030DBE
0x180030db8  call    cs:__imp_RegCloseKey
0x180030dbe  xor     eax, eax
0x180030dc0  add     rsp, 68h
0x180030dc4  pop     rdi
0x180030dc5  pop     rsi
0x180030dc6  pop     rbx
0x180030dc7  pop     rbp
0x180030dc8  retn
```
