# AddPostBootReminder(void *,uint)

- ea: `0x18002cf64`
- end: `0x18002d2d1`
- name: `?AddPostBootReminder@@YAJPEAXI@Z`
- size: `877`
- prototype: `__int64 __fastcall(void *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800190f4`

## callees

- `0x1800079b0`
- `0x180008200`
- `0x18000a320`
- `0x18001f060`
- `0x18001fb70`
- `0x1800245c0`
- `0x18002cf64`
- `0x18002d2d8`
- `0x18002e648`
- `0x18002e9e0`
- `0x18003f42c`
- `0x18004d39c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cffe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d087`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d29b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d2ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cffe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d087`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d29b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d2ab`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d056`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d056`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18002cfcd`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18002cfcd`

## string_xrefs

- `0x18002cfa6`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002cfde`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002d067`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002d0cb`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002d137`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002d248`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002d25c`: `TempProfile`

## pseudocode

```c
__int64 __fastcall AddPostBootReminder(void *a1, unsigned int a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  unsigned int v5; // eax
  HKEY v6; // rcx
  unsigned int v7; // eax
  __int64 v8; // r8
  int v9; // eax
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rdx
  int v13; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-29h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-29h]
  __int64 v17; // [rsp+50h] [rbp+7h] BYREF
  char v18; // [rsp+58h] [rbp+Fh]
  unsigned __int16 *v19[3]; // [rsp+60h] [rbp+17h] BYREF
  unsigned __int16 *v20[5]; // [rsp+78h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]
  HKEY hKey; // [rsp+B0h] [rbp+67h] BYREF
  HKEY phkResult; // [rsp+C0h] [rbp+77h] BYREF

  v17 = 0;
  v18 = 0;
  phkResult = 0;
  if ( a1 )
  {
    v3 = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v17, a1);
    v4 = v3;
    if ( v3 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4A3,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
        (const char *)(unsigned int)v3,
        dwOptions);
      goto LABEL_6;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v5 = RegOpenCurrentUser(0x20006u, &phkResult);
    if ( v5 )
    {
      v4 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x4A5,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
             (const char *)v5,
             dwOptions);
LABEL_6:
      if ( phkResult )
        RegCloseKey(phkResult);
      goto LABEL_47;
    }
  }
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v6 = HKEY_CURRENT_USER;
  if ( phkResult )
    v6 = phkResult;
  v7 = RegCreateKeyExW(
         v6,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\PostBootReminders\\ProfileError",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         0);
  if ( v7 )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x4AA,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
           (const char *)v7,
           dwOptionsa);
    goto LABEL_12;
  }
  memset(v19, 0, sizeof(v19));
  v8 = 100;
  if ( a2 != 102 )
    v8 = 300;
  v9 = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::Initialize(
         v19,
         g_hDllInstance,
         v8);
  v4 = v9;
  if ( v9 < 0 )
  {
    v10 = 1197;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
      (const char *)(unsigned int)v9,
      dwOptionsa);
LABEL_19:
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(v19);
LABEL_12:
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_6;
  }
  v9 = SHRegSetString(hKey, 0, L"Title", v19[0]);
  v4 = v9;
  if ( v9 < 0 )
  {
    v10 = 1198;
    goto LABEL_18;
  }
  memset(v20, 0, 24);
  v11 = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::Initialize(
          v20,
          g_hDllInstance,
          a2);
  v4 = v11;
  if ( v11 < 0 )
  {
    v12 = 1201;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
      (const char *)(unsigned int)v11,
      dwOptionsa);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(v20);
    goto LABEL_19;
  }
  v11 = SHRegSetString(hKey, 0, L"Text", v20[0]);
  v4 = v11;
  if ( v11 < 0 )
  {
    v12 = 1202;
    goto LABEL_24;
  }
  v11 = SHRegSetString(hKey, 0, L"IconResource", v20[0]);
  v4 = v11;
  if ( v11 < 0 )
  {
    v12 = 1205;
    goto LABEL_24;
  }
  v11 = SHRegSetDWORD(hKey, 0, L"ShowTime", 0xEA60u);
  v4 = v11;
  if ( v11 < 0 )
  {
    v12 = 1207;
    goto LABEL_24;
  }
  v11 = SHRegSetDWORD(hKey, 0, L"RetryInterval", 0);
  v4 = v11;
  if ( v11 < 0 )
  {
    v12 = 1210;
    goto LABEL_24;
  }
  v11 = SHRegSetDWORD(hKey, 0, L"RetryCount", 0);
  v4 = v11;
  if ( v11 < 0 )
  {
    v12 = 1211;
    goto LABEL_24;
  }
  v11 = SHRegSetDWORD(hKey, 0, L"TypeFlags", 0);
  v4 = v11;
  if ( v11 < 0 )
  {
    v12 = 1212;
    goto LABEL_24;
  }
  if ( a2 == 102 )
  {
    v13 = LogHiveListInfo();
    if ( v13 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4C0,
        (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
        (const char *)(unsigned int)v13);
    v11 = SHRegSetDWORD(hKey, 0, L"TempProfile", 0);
    v4 = v11;
    if ( v11 < 0 )
    {
      v12 = 1217;
      goto LABEL_24;
    }
  }
  Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(v20);
  Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(v19);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  v4 = 0;
LABEL_47:
  CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v17);
  return v4;
}

```

## disassembly

```asm
0x18002cf64  mov     [rsp-8+arg_8], rbx
0x18002cf69  push    rbp
0x18002cf6a  push    rsi
0x18002cf6b  push    rdi
0x18002cf6c  lea     rbp, [rsp-47h]
0x18002cf71  sub     rsp, 90h
0x18002cf78  mov     edi, edx
0x18002cf7a  xor     esi, esi
0x18002cf7c  mov     [rbp+57h+var_50], rsi
0x18002cf80  mov     [rbp+57h+var_48], sil
0x18002cf84  mov     [rbp+57h+phkResult], rsi
0x18002cf88  test    rcx, rcx
0x18002cf8b  jz      short loc_18002D009
0x18002cf8d  mov     rdx, rcx; void *
0x18002cf90  lea     rcx, [rbp+57h+var_50]; this
0x18002cf94  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x18002cf99  mov     ebx, eax
0x18002cf9b  test    eax, eax
0x18002cf9d  jns     short loc_18002CFB9
0x18002cf9f  mov     rcx, [rbp+5Fh]; this
0x18002cfa3  mov     r9d, eax; char *
0x18002cfa6  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002cfad  mov     edx, 4A3h; void *
0x18002cfb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cfb7  jmp     short loc_18002CFF1
0x18002cfb9  xor     edx, edx
0x18002cfbb  lea     rcx, [rbp+57h+phkResult]
0x18002cfbf  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002cfc4  lea     rdx, [rbp+57h+phkResult]; phkResult
0x18002cfc8  mov     ecx, 20006h; samDesired
0x18002cfcd  call    cs:__imp_RegOpenCurrentUser
0x18002cfd3  test    eax, eax
0x18002cfd5  jz      short loc_18002D009
0x18002cfd7  mov     rcx, [rbp+5Fh]; this
0x18002cfdb  mov     r9d, eax; char *
0x18002cfde  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002cfe5  mov     edx, 4A5h; void *
0x18002cfea  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002cfef  mov     ebx, eax
0x18002cff1  mov     rcx, [rbp+57h+phkResult]; hKey
0x18002cff5  test    rcx, rcx
0x18002cff8  jz      loc_18002D2B3
0x18002cffe  call    cs:__imp_RegCloseKey
0x18002d004  jmp     loc_18002D2B3
0x18002d009  mov     [rbp+57h+hKey], rsi
0x18002d00d  xor     edx, edx
0x18002d00f  lea     rcx, [rbp+57h+hKey]
0x18002d013  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002d018  mov     rcx, 0FFFFFFFF80000001h
0x18002d01f  mov     rax, [rbp+57h+phkResult]
0x18002d023  test    rax, rax
0x18002d026  cmovnz  rcx, rax; hKey
0x18002d02a  mov     [rsp+0A0h+lpdwDisposition], rsi; lpdwDisposition
0x18002d02f  lea     rax, [rbp+57h+hKey]
0x18002d033  mov     [rsp+0A0h+var_68], rax; phkResult
0x18002d038  mov     [rsp+0A0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18002d03d  mov     [rsp+0A0h+samDesired], 20006h; samDesired
0x18002d045  mov     [rsp+0A0h+dwOptions], esi; int
0x18002d049  xor     r9d, r9d; lpClass
0x18002d04c  xor     r8d, r8d; Reserved
0x18002d04f  lea     rdx, aSoftwareMicros_31; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002d056  call    cs:__imp_RegCreateKeyExW
0x18002d05c  test    eax, eax
0x18002d05e  jz      short loc_18002D092
0x18002d060  mov     rcx, [rbp+5Fh]; this
0x18002d064  mov     r9d, eax; char *
0x18002d067  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d06e  mov     edx, 4AAh; void *
0x18002d073  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002d078  mov     ebx, eax
0x18002d07a  mov     rcx, [rbp+57h+hKey]; hKey
0x18002d07e  test    rcx, rcx
0x18002d081  jz      loc_18002CFF1
0x18002d087  call    cs:__imp_RegCloseKey
0x18002d08d  jmp     loc_18002CFF1
0x18002d092  mov     [rbp+57h+var_40], rsi
0x18002d096  mov     [rbp+57h+var_38], rsi
0x18002d09a  mov     [rbp+57h+var_30], rsi
0x18002d09e  mov     eax, 12Ch
0x18002d0a3  mov     r8d, 64h ; 'd'
0x18002d0a9  cmp     edi, 66h ; 'f'
0x18002d0ac  cmovnz  r8d, eax
0x18002d0b0  mov     rdx, cs:?g_hDllInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hDllInstance
0x18002d0b7  lea     rcx, [rbp+57h+var_40]
0x18002d0bb  call    ?Initialize@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@IG@Z; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint,ushort)
0x18002d0c0  mov     ebx, eax
0x18002d0c2  test    eax, eax
0x18002d0c4  jns     short loc_18002D0EA
0x18002d0c6  mov     edx, 4ADh; void *
0x18002d0cb  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d0d2  mov     r9d, eax; char *
0x18002d0d5  mov     rcx, [rbp+5Fh]; this
0x18002d0d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d0de  nop
0x18002d0df  lea     rcx, [rbp+57h+var_40]
0x18002d0e3  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x18002d0e8  jmp     short loc_18002D07A
0x18002d0ea  mov     r9, [rbp+57h+var_40]; unsigned __int16 *
0x18002d0ee  lea     r8, aTitle; "Title"
0x18002d0f5  xor     edx, edx; unsigned __int16 *
0x18002d0f7  mov     rcx, [rbp+57h+hKey]; hKey
0x18002d0fb  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18002d100  mov     ebx, eax
0x18002d102  test    eax, eax
0x18002d104  jns     short loc_18002D10D
0x18002d106  mov     edx, 4AEh
0x18002d10b  jmp     short loc_18002D0CB
0x18002d10d  mov     [rbp+57h+var_28], rsi
0x18002d111  mov     [rbp+57h+var_20], rsi
0x18002d115  mov     [rbp+57h+var_18], rsi
0x18002d119  mov     r8d, edi
0x18002d11c  mov     rdx, cs:?g_hDllInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hDllInstance
0x18002d123  lea     rcx, [rbp+57h+var_28]
0x18002d127  call    ?Initialize@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@IG@Z; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint,ushort)
0x18002d12c  mov     ebx, eax
0x18002d12e  test    eax, eax
0x18002d130  jns     short loc_18002D156
0x18002d132  mov     edx, 4B1h; void *
0x18002d137  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d13e  mov     r9d, eax; char *
0x18002d141  mov     rcx, [rbp+5Fh]; this
0x18002d145  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d14a  nop
0x18002d14b  lea     rcx, [rbp+57h+var_28]
0x18002d14f  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x18002d154  jmp     short loc_18002D0DF
0x18002d156  mov     r9, [rbp+57h+var_28]; unsigned __int16 *
0x18002d15a  lea     r8, aText; "Text"
0x18002d161  xor     edx, edx; unsigned __int16 *
0x18002d163  mov     rcx, [rbp+57h+hKey]; hKey
0x18002d167  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18002d16c  mov     ebx, eax
0x18002d16e  test    eax, eax
0x18002d170  jns     short loc_18002D179
0x18002d172  mov     edx, 4B2h
0x18002d177  jmp     short loc_18002D137
0x18002d179  mov     r9, [rbp+57h+var_28]; unsigned __int16 *
0x18002d17d  lea     r8, aIconresource; "IconResource"
0x18002d184  xor     edx, edx; unsigned __int16 *
0x18002d186  mov     rcx, [rbp+57h+hKey]; hKey
0x18002d18a  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18002d18f  mov     ebx, eax
0x18002d191  test    eax, eax
0x18002d193  jns     short loc_18002D19C
0x18002d195  mov     edx, 4B5h
0x18002d19a  jmp     short loc_18002D137
0x18002d19c  mov     r9d, 0EA60h; unsigned int
0x18002d1a2  lea     r8, aShowtime; "ShowTime"
0x18002d1a9  xor     edx, edx; unsigned __int16 *
0x18002d1ab  mov     rcx, [rbp+57h+hKey]; HKEY
0x18002d1af  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18002d1b4  mov     ebx, eax
0x18002d1b6  test    eax, eax
0x18002d1b8  jns     short loc_18002D1C4
0x18002d1ba  mov     edx, 4B7h
0x18002d1bf  jmp     loc_18002D137
0x18002d1c4  xor     r9d, r9d; unsigned int
0x18002d1c7  lea     r8, aRetryinterval; "RetryInterval"
0x18002d1ce  xor     edx, edx; unsigned __int16 *
0x18002d1d0  mov     rcx, [rbp+57h+hKey]; HKEY
0x18002d1d4  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18002d1d9  mov     ebx, eax
0x18002d1db  test    eax, eax
0x18002d1dd  jns     short loc_18002D1E9
0x18002d1df  mov     edx, 4BAh
0x18002d1e4  jmp     loc_18002D137
0x18002d1e9  xor     r9d, r9d; unsigned int
0x18002d1ec  lea     r8, aRetrycount; "RetryCount"
0x18002d1f3  xor     edx, edx; unsigned __int16 *
0x18002d1f5  mov     rcx, [rbp+57h+hKey]; HKEY
0x18002d1f9  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18002d1fe  mov     ebx, eax
0x18002d200  test    eax, eax
0x18002d202  jns     short loc_18002D20E
0x18002d204  mov     edx, 4BBh
0x18002d209  jmp     loc_18002D137
0x18002d20e  xor     r9d, r9d; unsigned int
0x18002d211  lea     r8, aTypeflags; "TypeFlags"
0x18002d218  xor     edx, edx; unsigned __int16 *
0x18002d21a  mov     rcx, [rbp+57h+hKey]; HKEY
0x18002d21e  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18002d223  mov     ebx, eax
0x18002d225  test    eax, eax
0x18002d227  jns     short loc_18002D233
0x18002d229  mov     edx, 4BCh
0x18002d22e  jmp     loc_18002D137
0x18002d233  cmp     edi, 66h ; 'f'
0x18002d236  jnz     short loc_18002D27E
0x18002d238  call    ?LogHiveListInfo@@YAJXZ; LogHiveListInfo(void)
0x18002d23d  mov     rcx, [rbp+5Fh]; this
0x18002d241  test    eax, eax
0x18002d243  jns     short loc_18002D259
0x18002d245  mov     r9d, eax; char *
0x18002d248  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d24f  mov     edx, 4C0h; void *
0x18002d254  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002d259  xor     r9d, r9d; unsigned int
0x18002d25c  lea     r8, aTempprofile; "TempProfile"
0x18002d263  xor     edx, edx; unsigned __int16 *
0x18002d265  mov     rcx, [rbp+57h+hKey]; HKEY
0x18002d269  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18002d26e  mov     ebx, eax
0x18002d270  test    eax, eax
0x18002d272  jns     short loc_18002D27E
0x18002d274  mov     edx, 4C1h
0x18002d279  jmp     loc_18002D137
0x18002d27e  lea     rcx, [rbp+57h+var_28]
0x18002d282  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x18002d287  nop
0x18002d288  lea     rcx, [rbp+57h+var_40]
0x18002d28c  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x18002d291  nop
0x18002d292  mov     rcx, [rbp+57h+hKey]; hKey
0x18002d296  test    rcx, rcx
0x18002d299  jz      short loc_18002D2A2
0x18002d29b  call    cs:__imp_RegCloseKey
0x18002d2a1  nop
0x18002d2a2  mov     rcx, [rbp+57h+phkResult]; hKey
0x18002d2a6  test    rcx, rcx
0x18002d2a9  jz      short loc_18002D2B1
0x18002d2ab  call    cs:__imp_RegCloseKey
0x18002d2b1  mov     ebx, esi
0x18002d2b3  lea     rcx, [rbp+57h+var_50]; this
0x18002d2b7  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18002d2bc  mov     eax, ebx
0x18002d2be  mov     rbx, [rsp+0A0h+arg_8]
0x18002d2c6  add     rsp, 90h
0x18002d2cd  pop     rdi
0x18002d2ce  pop     rsi
0x18002d2cf  pop     rbp
0x18002d2d0  retn
```
