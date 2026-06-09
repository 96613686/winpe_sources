# DeleteOtherPerUserSetting(ushort const *,bool,bool)

- ea: `0x18002d508`
- end: `0x18002d6ba`
- name: `?DeleteOtherPerUserSetting@@YAJPEBG_N1@Z`
- size: `434`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002eae0`

## callees

- `0x1800053c0`
- `0x1800130d0`
- `0x180013770`
- `0x18002d508`
- `0x18002d88c`
- `0x18002df68`
- `0x180040bcc`
- `0x180043800`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002d646`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002d646`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d665`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d665`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d550`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d550`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d5cc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d5cc`

## string_xrefs

- `0x18002d567`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x18002d5e3`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x18002d616`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x18002d67a`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x18002d542`: `Software\Microsoft\Windows\CurrentVersion\NetCache`
- `0x18002d63f`: `msi.dll`
- `0x18002d65b`: `MsiDeleteUserDataW`

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
      v8 = SHRegSetString(v17, 0, a1, &qword_1800649D8);
      if ( v8 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xFA,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
          (const char *)(unsigned int)v8,
          phkResulta);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v17);
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
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return 0;
}

```

## disassembly

```asm
0x18002d508  push    rbp
0x18002d50a  push    rbx
0x18002d50b  push    rsi
0x18002d50c  push    rdi
0x18002d50d  mov     rbp, rsp
0x18002d510  sub     rsp, 68h
0x18002d514  mov     dil, r8b
0x18002d517  mov     sil, dl
0x18002d51a  mov     rbx, rcx
0x18002d51d  mov     [rbp+hKey], 0
0x18002d525  xor     edx, edx
0x18002d527  lea     rcx, [rbp+hKey]
0x18002d52b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002d530  lea     rax, [rbp+hKey]
0x18002d534  mov     [rsp+68h+phkResult], rax; unsigned int
0x18002d539  mov     r9d, 20006h; samDesired
0x18002d53f  xor     r8d, r8d; ulOptions
0x18002d542  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002d549  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d550  call    cs:__imp_RegOpenKeyExW
0x18002d557  nop     dword ptr [rax+rax+00h]
0x18002d55c  mov     rcx, [rbp+20h]; this
0x18002d560  test    eax, eax
0x18002d562  jz      short loc_18002D57D
0x18002d564  mov     r9d, eax; char *
0x18002d567  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d56e  mov     edx, 0F5h; void *
0x18002d573  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002d578  jmp     loc_18002D630
0x18002d57d  mov     [rbp+arg_18], 0
0x18002d585  xor     edx, edx
0x18002d587  lea     rcx, [rbp+arg_18]
0x18002d58b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002d590  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x18002d599  lea     rax, [rbp+arg_18]
0x18002d59d  mov     [rsp+68h+var_30], rax; phkResult
0x18002d5a2  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002d5ab  mov     [rsp+68h+samDesired], 20006h; samDesired
0x18002d5b3  mov     dword ptr [rsp+68h+phkResult], 0; int
0x18002d5bb  xor     r9d, r9d; lpClass
0x18002d5be  xor     r8d, r8d; Reserved
0x18002d5c1  lea     rdx, aPurgeatnextlog; "PurgeAtNextLogoff"
0x18002d5c8  mov     rcx, [rbp+hKey]; hKey
0x18002d5cc  call    cs:__imp_RegCreateKeyExW
0x18002d5d3  nop     dword ptr [rax+rax+00h]
0x18002d5d8  mov     rcx, [rbp+20h]; this
0x18002d5dc  test    eax, eax
0x18002d5de  jz      short loc_18002D5F6
0x18002d5e0  mov     r9d, eax; char *
0x18002d5e3  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d5ea  mov     edx, 0F8h; void *
0x18002d5ef  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002d5f4  jmp     short loc_18002D627
0x18002d5f6  lea     r9, qword_1800649D8; unsigned __int16 *
0x18002d5fd  mov     r8, rbx; unsigned __int16 *
0x18002d600  xor     edx, edx; unsigned __int16 *
0x18002d602  mov     rcx, [rbp+arg_18]; hKey
0x18002d606  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18002d60b  mov     rcx, [rbp+20h]; this
0x18002d60f  test    eax, eax
0x18002d611  jns     short loc_18002D627
0x18002d613  mov     r9d, eax; char *
0x18002d616  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d61d  mov     edx, 0FAh; void *
0x18002d622  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002d627  lea     rcx, [rbp+arg_18]
0x18002d62b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002d630  test    sil, sil
0x18002d633  jz      short loc_18002D63A
0x18002d635  test    dil, dil
0x18002d638  jnz     short loc_18002D6A5
0x18002d63a  xor     r8d, r8d; dwFlags
0x18002d63d  xor     edx, edx; hFile
0x18002d63f  lea     rcx, aMsiDll; "msi.dll"
0x18002d646  call    cs:__imp_LoadLibraryExW
0x18002d64d  nop     dword ptr [rax+rax+00h]
0x18002d652  mov     [rbp+arg_18], rax
0x18002d656  test    rax, rax
0x18002d659  jz      short loc_18002D69B
0x18002d65b  lea     rdx, aMsideleteuserd; "MsiDeleteUserDataW"
0x18002d662  mov     rcx, rax; hModule
0x18002d665  call    cs:__imp_GetProcAddress
0x18002d66c  nop     dword ptr [rax+rax+00h]
0x18002d671  mov     rcx, [rbp+20h]; this
0x18002d675  test    rax, rax
0x18002d678  jnz     short loc_18002D68D
0x18002d67a  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d681  mov     edx, 10Ch; void *
0x18002d686  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18002d68b  jmp     short loc_18002D69B
0x18002d68d  xor     r8d, r8d
0x18002d690  xor     edx, edx
0x18002d692  mov     rcx, rbx
0x18002d695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d69a  nop
0x18002d69b  lea     rcx, [rbp+arg_18]
0x18002d69f  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002d6a4  nop
0x18002d6a5  lea     rcx, [rbp+hKey]
0x18002d6a9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002d6ae  xor     eax, eax
0x18002d6b0  add     rsp, 68h
0x18002d6b4  pop     rdi
0x18002d6b5  pop     rsi
0x18002d6b6  pop     rbx
0x18002d6b7  pop     rbp
0x18002d6b8  retn
```
