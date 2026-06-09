# SetProfileListSecurity(ushort const *,int)

- ea: `0x18002d360`
- end: `0x18002d7ba`
- name: `?SetProfileListSecurity@@YAJPEBGH@Z`
- size: `1114`
- prototype: `__int64 __fastcall(LPCWCH lpString1, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800393e4`

## callees

- `0x18000f1b0`
- `0x180010f30`
- `0x1800111a0`
- `0x18001f060`
- `0x180025254`
- `0x18002d2d8`
- `0x18002d360`
- `0x18002db38`
- `0x18002e648`
- `0x18002f8e0`
- `0x180047258`
- `0x18004cb54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d484`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d506`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d484`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d506`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d4cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d533`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d77c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d78b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d4cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d533`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d77c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d78b`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18002d54d`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18002d5d5`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18002d54d`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18002d5d5`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18002d734`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18002d734`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002d716`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002d716`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002d6e6`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002d6e6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002d614`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002d614`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d58a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d58a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002d654`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002d654`

## string_xrefs

- `0x18002d3bb`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002d3ef`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002d436`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002d4ae`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002d514`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002d56f`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002d5a8`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002d5e3`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002d622`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002d662`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002d6ad`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002d6f9`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002d742`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002d3db`: `Setting the security of the user ProfileList preference key is not supported on state separated editions`

## pseudocode

```c
__int64 __fastcall SetProfileListSecurity(LPCWCH lpString1)
{
  int ProfileListKeyNameFromSid; // eax
  unsigned int v3; // ebx
  int v4; // eax
  LSTATUS v5; // eax
  unsigned int v6; // eax
  LSTATUS KeySecurity; // eax
  HLOCAL v8; // rax
  void *v9; // rbx
  __int64 v10; // rdx
  unsigned int v11; // eax
  int LastError; // eax
  const char *v13; // r9
  const char *v14; // r9
  __int64 v15; // r8
  int v16; // eax
  const char *v17; // r9
  __int64 v18; // rdx
  int v19; // eax
  unsigned int v20; // eax
  int phkResult; // [rsp+20h] [rbp-59h]
  int phkResulta; // [rsp+20h] [rbp-59h]
  unsigned int phkResultb; // [rsp+20h] [rbp-59h]
  const char *v25; // [rsp+28h] [rbp-51h]
  HKEY v26; // [rsp+30h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-41h] BYREF
  void *v28; // [rsp+40h] [rbp-39h] BYREF
  PACL v29; // [rsp+48h] [rbp-31h] BYREF
  PSID Sid; // [rsp+50h] [rbp-29h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+58h] [rbp-21h] BYREF
  LPCWSTR v32; // [rsp+70h] [rbp-9h] BYREF
  __int64 v33; // [rsp+78h] [rbp-1h]
  __int64 v34; // [rsp+80h] [rbp+7h]
  PACL pDacl; // [rsp+88h] [rbp+Fh] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+90h] [rbp+17h] BYREF
  __int64 v37; // [rsp+B0h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  DWORD cbSecurityDescriptor; // [rsp+E8h] [rbp+6Fh] BYREF
  WINBOOL bDaclPresent; // [rsp+F0h] [rbp+77h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+F8h] [rbp+7Fh] BYREF

  cbSecurityDescriptor = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v32);
  v33 = -1;
  v34 = -1;
  ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(
                                lpString1,
                                (unsigned __int16 **)&v32,
                                (int *)&cbSecurityDescriptor);
  v3 = ProfileListKeyNameFromSid;
  if ( ProfileListKeyNameFromSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
      (const char *)(unsigned int)ProfileListKeyNameFromSid,
      phkResult);
    goto LABEL_55;
  }
  if ( cbSecurityDescriptor )
  {
    v3 = -2147418113;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
      (const char *)0x8000FFFFLL,
      (int)"Setting the security of the user ProfileList preference key is not supported on state separated editions",
      v25);
    goto LABEL_55;
  }
  memset(lpSubKey, 0, sizeof(lpSubKey));
  v4 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
         lpSubKey,
         L"%s\\%s",
         v32,
         L"Preference");
  v3 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
      (const char *)(unsigned int)v4,
      phkResult);
LABEL_7:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpSubKey);
    goto LABEL_55;
  }
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0xF003Fu, &hKey);
  v3 = v5;
  if ( !v5 )
  {
    v26 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v26,
      0);
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v32, 0, 0x20000u, &v26);
    if ( v6 )
    {
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x77,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
             (const char *)v6,
             phkResultb);
      goto LABEL_18;
    }
    cbSecurityDescriptor = 0;
    KeySecurity = RegGetKeySecurity(v26, 4u, 0, &cbSecurityDescriptor);
    v3 = KeySecurity;
    if ( KeySecurity != 122 )
    {
      if ( KeySecurity > 0 )
        v3 = (unsigned __int16)KeySecurity | 0x80070000;
      if ( (v3 & 0x80000000) != 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7B,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
          (const char *)v3,
          phkResultb);
      goto LABEL_18;
    }
    v8 = LocalAlloc(0, cbSecurityDescriptor);
    v28 = v8;
    v9 = v8;
    if ( !v8 )
    {
      v3 = -2147024882;
      v10 = 126;
LABEL_27:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
        (const char *)v3,
        phkResultb);
LABEL_28:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v28);
LABEL_18:
      if ( v26 )
        RegCloseKey(v26);
      goto LABEL_14;
    }
    v11 = RegGetKeySecurity(v26, 4u, v8, &cbSecurityDescriptor);
    if ( v11 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x80,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
                    (const char *)v11,
                    phkResultb);
LABEL_31:
      v3 = LastError;
      goto LABEL_28;
    }
    bDaclPresent = 0;
    bDaclDefaulted = 0;
    pDacl = 0;
    if ( !GetSecurityDescriptorDacl(v9, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x85,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
                    v13);
      goto LABEL_31;
    }
    if ( !bDaclPresent )
    {
      v3 = -2147023558;
      v10 = 134;
      goto LABEL_27;
    }
    Sid = 0;
    if ( !ConvertStringSidToSidW(lpString1, &Sid) )
    {
      v3 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x8A,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
             v14);
LABEL_38:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
      goto LABEL_28;
    }
    v29 = 0;
    wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::reset(
      &v29,
      0);
    v16 = AddSidToAcl(pDacl, Sid, v15, &v29);
    v3 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
        (const char *)(unsigned int)v16,
        phkResultb);
LABEL_41:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((void **)&v29);
      goto LABEL_38;
    }
    v37 = 0;
    memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
    if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    {
      if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v29, 0) )
      {
        v20 = RegSetKeySecurity(hKey, 4u, pSecurityDescriptor);
        if ( !v20 )
        {
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((void **)&v29);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v28);
          if ( v26 )
            RegCloseKey(v26);
          goto LABEL_52;
        }
        v19 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x95,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
                (const char *)v20,
                phkResultb);
        goto LABEL_45;
      }
      v18 = 147;
    }
    else
    {
      v18 = 146;
    }
    v19 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v18,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
            v17);
LABEL_45:
    v3 = v19;
    goto LABEL_41;
  }
  if ( v5 != 2 )
  {
    if ( v5 > 0 )
      v3 = (unsigned __int16)v5 | 0x80070000;
    if ( (v3 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
        (const char *)v3,
        phkResulta);
LABEL_14:
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_7;
  }
LABEL_52:
  if ( hKey )
    RegCloseKey(hKey);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpSubKey);
  v3 = 0;
LABEL_55:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v32);
  return v3;
}

```

## disassembly

```asm
0x18002d360  mov     [rsp-8+arg_0], rbx
0x18002d365  mov     [rsp-8+cbSecurityDescriptor], edx
0x18002d369  push    rbp
0x18002d36a  push    rsi
0x18002d36b  push    rdi
0x18002d36c  lea     rbp, [rsp-47h]
0x18002d371  sub     rsp, 0C0h
0x18002d378  xor     esi, esi
0x18002d37a  mov     rdi, rcx
0x18002d37d  lea     rcx, [rbp+57h+var_60]
0x18002d381  mov     [rbp+57h+cbSecurityDescriptor], esi
0x18002d384  mov     [rbp+57h+var_60], rsi
0x18002d388  mov     [rbp+57h+var_58], rsi
0x18002d38c  mov     [rbp+57h+var_50], rsi
0x18002d390  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002d395  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d399  lea     r8, [rbp+57h+cbSecurityDescriptor]; int *
0x18002d39d  lea     rdx, [rbp+57h+var_60]; unsigned __int16 **
0x18002d3a1  mov     [rbp+57h+var_58], rax
0x18002d3a5  mov     rcx, rdi; lpString1
0x18002d3a8  mov     [rbp+57h+var_50], rax
0x18002d3ac  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x18002d3b1  mov     ebx, eax
0x18002d3b3  test    eax, eax
0x18002d3b5  jns     short loc_18002D3D2
0x18002d3b7  mov     rcx, [rbp+5Fh]; this
0x18002d3bb  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d3c2  mov     r9d, eax; char *
0x18002d3c5  lea     edx, [rsi+53h]; void *
0x18002d3c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d3cd  jmp     loc_18002D79C
0x18002d3d2  cmp     [rbp+57h+cbSecurityDescriptor], esi
0x18002d3d5  jz      short loc_18002D405
0x18002d3d7  mov     rcx, [rbp+5Fh]; this
0x18002d3db  lea     rax, aSettingTheSecu; "Setting the security of the user Profil"...
0x18002d3e2  mov     ebx, 8000FFFFh
0x18002d3e7  mov     [rsp+0D0h+phkResult], rax; int
0x18002d3ec  mov     r9d, ebx; char *
0x18002d3ef  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d3f6  mov     edx, 55h ; 'U'; void *
0x18002d3fb  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002d400  jmp     loc_18002D79C
0x18002d405  mov     r8, [rbp+57h+var_60]
0x18002d409  lea     r9, aPreference; "Preference"
0x18002d410  lea     rdx, aSS_0; "%s\\%s"
0x18002d417  mov     [rbp+57h+lpSubKey], rsi
0x18002d41b  lea     rcx, [rbp+57h+lpSubKey]
0x18002d41f  mov     [rbp+57h+var_70], rsi
0x18002d423  mov     [rbp+57h+var_68], rsi
0x18002d427  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18002d42c  mov     ebx, eax
0x18002d42e  test    eax, eax
0x18002d430  jns     short loc_18002D458
0x18002d432  mov     rcx, [rbp+5Fh]; this
0x18002d436  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d43d  mov     r9d, eax; char *
0x18002d440  mov     edx, 58h ; 'X'; void *
0x18002d445  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d44a  lea     rcx, [rbp+57h+lpSubKey]
0x18002d44e  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002d453  jmp     loc_18002D79C
0x18002d458  xor     edx, edx
0x18002d45a  mov     [rbp+57h+hKey], rsi
0x18002d45e  lea     rcx, [rbp+57h+hKey]
0x18002d462  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002d467  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18002d46b  lea     rax, [rbp+57h+hKey]
0x18002d46f  mov     r9d, 0F003Fh; samDesired
0x18002d475  mov     [rsp+0D0h+phkResult], rax; int
0x18002d47a  xor     r8d, r8d; ulOptions
0x18002d47d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d484  call    cs:__imp_RegOpenKeyExW
0x18002d48a  mov     ebx, eax
0x18002d48c  test    eax, eax
0x18002d48e  jz      short loc_18002D4DA
0x18002d490  cmp     eax, 2
0x18002d493  jz      loc_18002D782
0x18002d499  test    eax, eax
0x18002d49b  jle     short loc_18002D4A6
0x18002d49d  movzx   ebx, ax
0x18002d4a0  or      ebx, 80070000h
0x18002d4a6  test    ebx, ebx
0x18002d4a8  jns     short loc_18002D4C2
0x18002d4aa  mov     rcx, [rbp+5Fh]; this
0x18002d4ae  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d4b5  mov     r9d, ebx; char *
0x18002d4b8  mov     edx, 5Dh ; ']'; void *
0x18002d4bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d4c2  mov     rcx, [rbp+57h+hKey]; hKey
0x18002d4c6  test    rcx, rcx
0x18002d4c9  jz      loc_18002D44A
0x18002d4cf  call    cs:__imp_RegCloseKey
0x18002d4d5  jmp     loc_18002D44A
0x18002d4da  xor     edx, edx
0x18002d4dc  mov     [rbp+57h+var_A0], rsi
0x18002d4e0  lea     rcx, [rbp+57h+var_A0]
0x18002d4e4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002d4e9  mov     rdx, [rbp+57h+var_60]; lpSubKey
0x18002d4ed  lea     rax, [rbp+57h+var_A0]
0x18002d4f1  mov     r9d, 20000h; samDesired
0x18002d4f7  mov     [rsp+0D0h+phkResult], rax; unsigned int
0x18002d4fc  xor     r8d, r8d; ulOptions
0x18002d4ff  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d506  call    cs:__imp_RegOpenKeyExW
0x18002d50c  test    eax, eax
0x18002d50e  jz      short loc_18002D53B
0x18002d510  mov     rcx, [rbp+5Fh]; this
0x18002d514  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d51b  mov     r9d, eax; char *
0x18002d51e  mov     edx, 77h ; 'w'; void *
0x18002d523  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002d528  mov     ebx, eax
0x18002d52a  mov     rcx, [rbp+57h+var_A0]; hKey
0x18002d52e  test    rcx, rcx
0x18002d531  jz      short loc_18002D4C2
0x18002d533  call    cs:__imp_RegCloseKey
0x18002d539  jmp     short loc_18002D4C2
0x18002d53b  mov     rcx, [rbp+57h+var_A0]; hKey
0x18002d53f  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18002d543  xor     r8d, r8d; pSecurityDescriptor
0x18002d546  mov     [rbp+57h+cbSecurityDescriptor], esi
0x18002d549  lea     edx, [r8+4]; SecurityInformation
0x18002d54d  call    cs:__imp_RegGetKeySecurity
0x18002d553  mov     ebx, eax
0x18002d555  cmp     eax, 7Ah ; 'z'
0x18002d558  jz      short loc_18002D585
0x18002d55a  test    eax, eax
0x18002d55c  jle     short loc_18002D567
0x18002d55e  movzx   ebx, ax
0x18002d561  or      ebx, 80070000h
0x18002d567  test    ebx, ebx
0x18002d569  jns     short loc_18002D52A
0x18002d56b  mov     rcx, [rbp+5Fh]; this
0x18002d56f  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d576  mov     r9d, ebx; char *
0x18002d579  mov     edx, 7Bh ; '{'; void *
0x18002d57e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d583  jmp     short loc_18002D52A
0x18002d585  mov     edx, [rbp+57h+cbSecurityDescriptor]; uBytes
0x18002d588  xor     ecx, ecx; uFlags
0x18002d58a  call    cs:__imp_LocalAlloc
0x18002d590  mov     [rbp+57h+var_90], rax
0x18002d594  mov     rbx, rax
0x18002d597  test    rax, rax
0x18002d59a  jnz     short loc_18002D5C5
0x18002d59c  mov     ebx, 8007000Eh
0x18002d5a1  lea     edx, [rax+7Eh]; void *
0x18002d5a4  mov     rcx, [rbp+5Fh]; this
0x18002d5a8  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d5af  mov     r9d, ebx; char *
0x18002d5b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d5b7  lea     rcx, [rbp+57h+var_90]
0x18002d5bb  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002d5c0  jmp     loc_18002D52A
0x18002d5c5  mov     rcx, [rbp+57h+var_A0]; hKey
0x18002d5c9  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18002d5cd  mov     r8, rbx; pSecurityDescriptor
0x18002d5d0  mov     edx, 4; SecurityInformation
0x18002d5d5  call    cs:__imp_RegGetKeySecurity
0x18002d5db  test    eax, eax
0x18002d5dd  jz      short loc_18002D5FB
0x18002d5df  mov     rcx, [rbp+5Fh]; this
0x18002d5e3  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d5ea  mov     r9d, eax; char *
0x18002d5ed  mov     edx, 80h; void *
0x18002d5f2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002d5f7  mov     ebx, eax
0x18002d5f9  jmp     short loc_18002D5B7
0x18002d5fb  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x18002d5ff  mov     [rbp+57h+bDaclPresent], esi
0x18002d602  lea     r8, [rbp+57h+pDacl]; pDacl
0x18002d606  mov     [rbp+57h+bDaclDefaulted], esi
0x18002d609  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x18002d60d  mov     [rbp+57h+pDacl], rsi
0x18002d611  mov     rcx, rbx; pSecurityDescriptor
0x18002d614  call    cs:__imp_GetSecurityDescriptorDacl
0x18002d61a  test    eax, eax
0x18002d61c  jnz     short loc_18002D635
0x18002d61e  mov     rcx, [rbp+5Fh]; this
0x18002d622  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d629  mov     edx, 85h; void *
0x18002d62e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d633  jmp     short loc_18002D5F7
0x18002d635  cmp     [rbp+57h+bDaclPresent], esi
0x18002d638  jnz     short loc_18002D649
0x18002d63a  mov     ebx, 8007053Ah
0x18002d63f  mov     edx, 86h
0x18002d644  jmp     loc_18002D5A4
0x18002d649  lea     rdx, [rbp+57h+Sid]; Sid
0x18002d64d  mov     [rbp+57h+Sid], rsi
0x18002d651  mov     rcx, rdi; StringSid
0x18002d654  call    cs:__imp_ConvertStringSidToSidW
0x18002d65a  test    eax, eax
0x18002d65c  jnz     short loc_18002D683
0x18002d65e  mov     rcx, [rbp+5Fh]; this
0x18002d662  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d669  mov     edx, 8Ah; void *
0x18002d66e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d673  mov     ebx, eax
0x18002d675  lea     rcx, [rbp+57h+Sid]
0x18002d679  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002d67e  jmp     loc_18002D5B7
0x18002d683  xor     edx, edx
0x18002d685  mov     [rbp+57h+var_88], rsi
0x18002d689  lea     rcx, [rbp+57h+var_88]
0x18002d68d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_ACL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_ACL@@@Z; wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::reset(_ACL *)
0x18002d692  mov     rdx, [rbp+57h+Sid]; void *
0x18002d696  lea     r9, [rbp+57h+var_88]; struct _ACL **
0x18002d69a  mov     rcx, [rbp+57h+pDacl]; struct _ACL *
0x18002d69e  call    ?AddSidToAcl@@YAJPEAU_ACL@@PEAXKPEAPEAU1@@Z; AddSidToAcl(_ACL *,void *,ulong,_ACL * *)
0x18002d6a3  mov     ebx, eax
0x18002d6a5  test    eax, eax
0x18002d6a7  jns     short loc_18002D6CC
0x18002d6a9  mov     rcx, [rbp+5Fh]; this
0x18002d6ad  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d6b4  mov     r9d, eax; char *
0x18002d6b7  mov     edx, 8Eh; void *
0x18002d6bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d6c1  lea     rcx, [rbp+57h+var_88]
0x18002d6c5  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002d6ca  jmp     short loc_18002D675
0x18002d6cc  xor     eax, eax
0x18002d6ce  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18002d6d2  xorps   xmm0, xmm0
0x18002d6d5  mov     [rbp+57h+var_20], rax
0x18002d6d9  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x18002d6dd  lea     ebx, [rax+1]
0x18002d6e0  mov     edx, ebx; dwRevision
0x18002d6e2  movups  [rbp+57h+var_30], xmm0
0x18002d6e6  call    cs:__imp_InitializeSecurityDescriptor
0x18002d6ec  test    eax, eax
0x18002d6ee  jnz     short loc_18002D709
0x18002d6f0  mov     edx, 92h; void *
0x18002d6f5  mov     rcx, [rbp+5Fh]; this
0x18002d6f9  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d700  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d705  mov     ebx, eax
0x18002d707  jmp     short loc_18002D6C1
0x18002d709  mov     r8, [rbp+57h+var_88]; pDacl
0x18002d70d  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18002d711  xor     r9d, r9d; bDaclDefaulted
0x18002d714  mov     edx, ebx; bDaclPresent
0x18002d716  call    cs:__imp_SetSecurityDescriptorDacl
0x18002d71c  test    eax, eax
0x18002d71e  jnz     short loc_18002D727
0x18002d720  mov     edx, 93h
0x18002d725  jmp     short loc_18002D6F5
0x18002d727  mov     rcx, [rbp+57h+hKey]; hKey
0x18002d72b  lea     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18002d72f  mov     edx, 4; SecurityInformation
0x18002d734  call    cs:__imp_RegSetKeySecurity
0x18002d73a  test    eax, eax
0x18002d73c  jz      short loc_18002D758
0x18002d73e  mov     rcx, [rbp+5Fh]; this
0x18002d742  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d749  mov     r9d, eax; char *
0x18002d74c  mov     edx, 95h; void *
0x18002d751  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002d756  jmp     short loc_18002D705
0x18002d758  lea     rcx, [rbp+57h+var_88]
0x18002d75c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002d761  lea     rcx, [rbp+57h+Sid]
0x18002d765  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002d76a  lea     rcx, [rbp+57h+var_90]
0x18002d76e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002d773  mov     rcx, [rbp+57h+var_A0]; hKey
0x18002d777  test    rcx, rcx
0x18002d77a  jz      short loc_18002D782
0x18002d77c  call    cs:__imp_RegCloseKey
0x18002d782  mov     rcx, [rbp+57h+hKey]; hKey
0x18002d786  test    rcx, rcx
0x18002d789  jz      short loc_18002D791
0x18002d78b  call    cs:__imp_RegCloseKey
0x18002d791  lea     rcx, [rbp+57h+lpSubKey]
0x18002d795  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002d79a  mov     ebx, esi
0x18002d79c  lea     rcx, [rbp+57h+var_60]
0x18002d7a0  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002d7a5  mov     eax, ebx
0x18002d7a7  mov     rbx, [rsp+0D0h+arg_0]
0x18002d7af  add     rsp, 0C0h
0x18002d7b6  pop     rdi
0x18002d7b7  pop     rsi
0x18002d7b8  pop     rbp
0x18002d7b9  retn
```
