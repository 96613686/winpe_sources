# SetProfileListSecurity(ushort const *,int)

- ea: `0x1800319ec`
- end: `0x180031e67`
- name: `?SetProfileListSecurity@@YAJPEBGH@Z`
- size: `1147`
- prototype: `__int64 __fastcall(LPCWCH lpString1, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002f844`

## callees

- `0x18000d030`
- `0x18000d2c0`
- `0x18000e1a0`
- `0x1800130d0`
- `0x180013770`
- `0x18002793c`
- `0x18002df48`
- `0x180030ad0`
- `0x180031060`
- `0x1800319ec`
- `0x180035860`
- `0x1800493b4`
- `0x18004fb94`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031b10`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031b8e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031b10`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031b8e`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180031bd5`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180031c69`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180031bd5`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180031c69`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180031de6`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180031de6`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180031dc2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180031dc2`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180031d8c`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180031d8c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180031cae`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180031cae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031c18`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031c18`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180031cf4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180031cf4`

## string_xrefs

- `0x180031a47`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x180031a7b`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x180031ac2`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x180031b40`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x180031ba2`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x180031bfd`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x180031c3c`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x180031c7d`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x180031cc2`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x180031d08`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x180031d53`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x180031da5`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x180031dfa`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x180031a67`: `Setting the security of the user ProfileList preference key is not supported on state separated editions`

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
  unsigned int v15; // r8d
  int v16; // eax
  const char *v17; // r9
  __int64 v18; // rdx
  int v19; // eax
  unsigned int v20; // eax
  int phkResult; // [rsp+20h] [rbp-59h]
  int phkResulta; // [rsp+20h] [rbp-59h]
  unsigned int phkResultb; // [rsp+20h] [rbp-59h]
  const char *v25; // [rsp+28h] [rbp-51h]
  HKEY hKey; // [rsp+30h] [rbp-49h] BYREF
  HKEY v27; // [rsp+38h] [rbp-41h] BYREF
  HLOCAL v28; // [rsp+40h] [rbp-39h] BYREF
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
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v32);
  v33 = -1;
  v34 = -1;
  ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(
                                lpString1,
                                (unsigned __int16 **)&v32,
                                (int *)&cbSecurityDescriptor);
  v3 = ProfileListKeyNameFromSid;
  if ( ProfileListKeyNameFromSid >= 0 )
  {
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
      goto LABEL_50;
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
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
      goto LABEL_50;
    }
    v27 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v27,
      0);
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0xF003Fu, &v27);
    v3 = v5;
    if ( v5 )
    {
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
        goto LABEL_14;
      }
LABEL_49:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
      v3 = 0;
      goto LABEL_50;
    }
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v32, 0, 0x20000u, &hKey);
    if ( v6 )
    {
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x77,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
             (const char *)v6,
             phkResultb);
LABEL_17:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
LABEL_14:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
      goto LABEL_7;
    }
    cbSecurityDescriptor = 0;
    KeySecurity = RegGetKeySecurity(hKey, 4u, 0, &cbSecurityDescriptor);
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
      goto LABEL_17;
    }
    v8 = LocalAlloc(0, cbSecurityDescriptor);
    v28 = v8;
    v9 = v8;
    if ( !v8 )
    {
      v3 = -2147024882;
      v10 = 126;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
        (const char *)v3,
        phkResultb);
LABEL_26:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v28);
      goto LABEL_17;
    }
    v11 = RegGetKeySecurity(hKey, 4u, v8, &cbSecurityDescriptor);
    if ( v11 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x80,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
                    (const char *)v11,
                    phkResultb);
LABEL_29:
      v3 = LastError;
      goto LABEL_26;
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
      goto LABEL_29;
    }
    if ( !bDaclPresent )
    {
      v3 = -2147023558;
      v10 = 134;
      goto LABEL_25;
    }
    Sid = 0;
    if ( !ConvertStringSidToSidW(lpString1, &Sid) )
    {
      v3 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x8A,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
             v14);
LABEL_36:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
      goto LABEL_26;
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
LABEL_39:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v29);
      goto LABEL_36;
    }
    v37 = 0;
    memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
    if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    {
      if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v29, 0) )
      {
        v20 = RegSetKeySecurity(v27, 4u, pSecurityDescriptor);
        if ( !v20 )
        {
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v29);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v28);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          goto LABEL_49;
        }
        v19 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x95,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
                (const char *)v20,
                phkResultb);
        goto LABEL_43;
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
LABEL_43:
    v3 = v19;
    goto LABEL_39;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x53,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
    (const char *)(unsigned int)ProfileListKeyNameFromSid,
    phkResult);
LABEL_50:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v32);
  return v3;
}

```

## disassembly

```asm
0x1800319ec  mov     [rsp-8+arg_0], rbx
0x1800319f1  mov     [rsp-8+cbSecurityDescriptor], edx
0x1800319f5  push    rbp
0x1800319f6  push    rsi
0x1800319f7  push    rdi
0x1800319f8  lea     rbp, [rsp-47h]
0x1800319fd  sub     rsp, 0C0h
0x180031a04  xor     esi, esi
0x180031a06  mov     rdi, rcx
0x180031a09  lea     rcx, [rbp+57h+var_60]
0x180031a0d  mov     [rbp+57h+cbSecurityDescriptor], esi
0x180031a10  mov     [rbp+57h+var_60], rsi
0x180031a14  mov     [rbp+57h+var_58], rsi
0x180031a18  mov     [rbp+57h+var_50], rsi
0x180031a1c  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180031a21  or      rax, 0FFFFFFFFFFFFFFFFh
0x180031a25  lea     r8, [rbp+57h+cbSecurityDescriptor]; int *
0x180031a29  lea     rdx, [rbp+57h+var_60]; unsigned __int16 **
0x180031a2d  mov     [rbp+57h+var_58], rax
0x180031a31  mov     rcx, rdi; lpString1
0x180031a34  mov     [rbp+57h+var_50], rax
0x180031a38  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x180031a3d  mov     ebx, eax
0x180031a3f  test    eax, eax
0x180031a41  jns     short loc_180031A5E
0x180031a43  mov     rcx, [rbp+5Fh]; this
0x180031a47  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031a4e  mov     r9d, eax; char *
0x180031a51  lea     edx, [rsi+53h]; void *
0x180031a54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031a59  jmp     loc_180031E48
0x180031a5e  cmp     [rbp+57h+cbSecurityDescriptor], esi
0x180031a61  jz      short loc_180031A91
0x180031a63  mov     rcx, [rbp+5Fh]; this
0x180031a67  lea     rax, aSettingTheSecu; "Setting the security of the user Profil"...
0x180031a6e  mov     ebx, 8000FFFFh
0x180031a73  mov     [rsp+0D0h+phkResult], rax; int
0x180031a78  mov     r9d, ebx; char *
0x180031a7b  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031a82  mov     edx, 55h ; 'U'; void *
0x180031a87  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180031a8c  jmp     loc_180031E48
0x180031a91  mov     r8, [rbp+57h+var_60]
0x180031a95  lea     r9, aPreference; "Preference"
0x180031a9c  lea     rdx, aSS_0; "%s\\%s"
0x180031aa3  mov     [rbp+57h+lpSubKey], rsi
0x180031aa7  lea     rcx, [rbp+57h+lpSubKey]
0x180031aab  mov     [rbp+57h+var_70], rsi
0x180031aaf  mov     [rbp+57h+var_68], rsi
0x180031ab3  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180031ab8  mov     ebx, eax
0x180031aba  test    eax, eax
0x180031abc  jns     short loc_180031AE4
0x180031abe  mov     rcx, [rbp+5Fh]; this
0x180031ac2  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031ac9  mov     r9d, eax; char *
0x180031acc  mov     edx, 58h ; 'X'; void *
0x180031ad1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031ad6  lea     rcx, [rbp+57h+lpSubKey]
0x180031ada  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180031adf  jmp     loc_180031E48
0x180031ae4  xor     edx, edx
0x180031ae6  mov     [rbp+57h+var_98], rsi
0x180031aea  lea     rcx, [rbp+57h+var_98]
0x180031aee  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180031af3  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180031af7  lea     rax, [rbp+57h+var_98]
0x180031afb  mov     r9d, 0F003Fh; samDesired
0x180031b01  mov     [rsp+0D0h+phkResult], rax; int
0x180031b06  xor     r8d, r8d; ulOptions
0x180031b09  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031b10  call    cs:__imp_RegOpenKeyExW
0x180031b17  nop     dword ptr [rax+rax+00h]
0x180031b1c  mov     ebx, eax
0x180031b1e  test    eax, eax
0x180031b20  jz      short loc_180031B62
0x180031b22  cmp     eax, 2
0x180031b25  jz      loc_180031E34
0x180031b2b  test    eax, eax
0x180031b2d  jle     short loc_180031B38
0x180031b2f  movzx   ebx, ax
0x180031b32  or      ebx, 80070000h
0x180031b38  test    ebx, ebx
0x180031b3a  jns     short loc_180031B54
0x180031b3c  mov     rcx, [rbp+5Fh]; this
0x180031b40  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031b47  mov     r9d, ebx; char *
0x180031b4a  mov     edx, 5Dh ; ']'; void *
0x180031b4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031b54  lea     rcx, [rbp+57h+var_98]
0x180031b58  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180031b5d  jmp     loc_180031AD6
0x180031b62  xor     edx, edx
0x180031b64  mov     [rbp+57h+hKey], rsi
0x180031b68  lea     rcx, [rbp+57h+hKey]
0x180031b6c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180031b71  mov     rdx, [rbp+57h+var_60]; lpSubKey
0x180031b75  lea     rax, [rbp+57h+hKey]
0x180031b79  mov     r9d, 20000h; samDesired
0x180031b7f  mov     [rsp+0D0h+phkResult], rax; unsigned int
0x180031b84  xor     r8d, r8d; ulOptions
0x180031b87  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031b8e  call    cs:__imp_RegOpenKeyExW
0x180031b95  nop     dword ptr [rax+rax+00h]
0x180031b9a  test    eax, eax
0x180031b9c  jz      short loc_180031BC3
0x180031b9e  mov     rcx, [rbp+5Fh]; this
0x180031ba2  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031ba9  mov     r9d, eax; char *
0x180031bac  mov     edx, 77h ; 'w'; void *
0x180031bb1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180031bb6  mov     ebx, eax
0x180031bb8  lea     rcx, [rbp+57h+hKey]
0x180031bbc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180031bc1  jmp     short loc_180031B54
0x180031bc3  mov     rcx, [rbp+57h+hKey]; hKey
0x180031bc7  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180031bcb  xor     r8d, r8d; pSecurityDescriptor
0x180031bce  mov     [rbp+57h+cbSecurityDescriptor], esi
0x180031bd1  lea     edx, [r8+4]; SecurityInformation
0x180031bd5  call    cs:__imp_RegGetKeySecurity
0x180031bdc  nop     dword ptr [rax+rax+00h]
0x180031be1  mov     ebx, eax
0x180031be3  cmp     eax, 7Ah ; 'z'
0x180031be6  jz      short loc_180031C13
0x180031be8  test    eax, eax
0x180031bea  jle     short loc_180031BF5
0x180031bec  movzx   ebx, ax
0x180031bef  or      ebx, 80070000h
0x180031bf5  test    ebx, ebx
0x180031bf7  jns     short loc_180031BB8
0x180031bf9  mov     rcx, [rbp+5Fh]; this
0x180031bfd  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031c04  mov     r9d, ebx; char *
0x180031c07  mov     edx, 7Bh ; '{'; void *
0x180031c0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031c11  jmp     short loc_180031BB8
0x180031c13  mov     edx, [rbp+57h+cbSecurityDescriptor]; uBytes
0x180031c16  xor     ecx, ecx; uFlags
0x180031c18  call    cs:__imp_LocalAlloc
0x180031c1f  nop     dword ptr [rax+rax+00h]
0x180031c24  mov     [rbp+57h+var_90], rax
0x180031c28  mov     rbx, rax
0x180031c2b  test    rax, rax
0x180031c2e  jnz     short loc_180031C59
0x180031c30  mov     ebx, 8007000Eh
0x180031c35  lea     edx, [rax+7Eh]; void *
0x180031c38  mov     rcx, [rbp+5Fh]; this
0x180031c3c  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031c43  mov     r9d, ebx; char *
0x180031c46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031c4b  lea     rcx, [rbp+57h+var_90]
0x180031c4f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180031c54  jmp     loc_180031BB8
0x180031c59  mov     rcx, [rbp+57h+hKey]; hKey
0x180031c5d  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180031c61  mov     r8, rbx; pSecurityDescriptor
0x180031c64  mov     edx, 4; SecurityInformation
0x180031c69  call    cs:__imp_RegGetKeySecurity
0x180031c70  nop     dword ptr [rax+rax+00h]
0x180031c75  test    eax, eax
0x180031c77  jz      short loc_180031C95
0x180031c79  mov     rcx, [rbp+5Fh]; this
0x180031c7d  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031c84  mov     r9d, eax; char *
0x180031c87  mov     edx, 80h; void *
0x180031c8c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180031c91  mov     ebx, eax
0x180031c93  jmp     short loc_180031C4B
0x180031c95  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180031c99  mov     [rbp+57h+bDaclPresent], esi
0x180031c9c  lea     r8, [rbp+57h+pDacl]; pDacl
0x180031ca0  mov     [rbp+57h+bDaclDefaulted], esi
0x180031ca3  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180031ca7  mov     [rbp+57h+pDacl], rsi
0x180031cab  mov     rcx, rbx; pSecurityDescriptor
0x180031cae  call    cs:__imp_GetSecurityDescriptorDacl
0x180031cb5  nop     dword ptr [rax+rax+00h]
0x180031cba  test    eax, eax
0x180031cbc  jnz     short loc_180031CD5
0x180031cbe  mov     rcx, [rbp+5Fh]; this
0x180031cc2  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031cc9  mov     edx, 85h; void *
0x180031cce  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180031cd3  jmp     short loc_180031C91
0x180031cd5  cmp     [rbp+57h+bDaclPresent], esi
0x180031cd8  jnz     short loc_180031CE9
0x180031cda  mov     ebx, 8007053Ah
0x180031cdf  mov     edx, 86h
0x180031ce4  jmp     loc_180031C38
0x180031ce9  lea     rdx, [rbp+57h+Sid]; Sid
0x180031ced  mov     [rbp+57h+Sid], rsi
0x180031cf1  mov     rcx, rdi; StringSid
0x180031cf4  call    cs:__imp_ConvertStringSidToSidW
0x180031cfb  nop     dword ptr [rax+rax+00h]
0x180031d00  test    eax, eax
0x180031d02  jnz     short loc_180031D29
0x180031d04  mov     rcx, [rbp+5Fh]; this
0x180031d08  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031d0f  mov     edx, 8Ah; void *
0x180031d14  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180031d19  mov     ebx, eax
0x180031d1b  lea     rcx, [rbp+57h+Sid]
0x180031d1f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180031d24  jmp     loc_180031C4B
0x180031d29  xor     edx, edx
0x180031d2b  mov     [rbp+57h+var_88], rsi
0x180031d2f  lea     rcx, [rbp+57h+var_88]
0x180031d33  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_ACL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_ACL@@@Z; wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::reset(_ACL *)
0x180031d38  mov     rdx, [rbp+57h+Sid]; void *
0x180031d3c  lea     r9, [rbp+57h+var_88]; struct _ACL **
0x180031d40  mov     rcx, [rbp+57h+pDacl]; struct _ACL *
0x180031d44  call    ?AddSidToAcl@@YAJPEAU_ACL@@PEAXKPEAPEAU1@@Z; AddSidToAcl(_ACL *,void *,ulong,_ACL * *)
0x180031d49  mov     ebx, eax
0x180031d4b  test    eax, eax
0x180031d4d  jns     short loc_180031D72
0x180031d4f  mov     rcx, [rbp+5Fh]; this
0x180031d53  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031d5a  mov     r9d, eax; char *
0x180031d5d  mov     edx, 8Eh; void *
0x180031d62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031d67  lea     rcx, [rbp+57h+var_88]
0x180031d6b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180031d70  jmp     short loc_180031D1B
0x180031d72  xor     eax, eax
0x180031d74  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180031d78  xorps   xmm0, xmm0
0x180031d7b  mov     [rbp+57h+var_20], rax
0x180031d7f  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x180031d83  lea     ebx, [rax+1]
0x180031d86  mov     edx, ebx; dwRevision
0x180031d88  movups  [rbp+57h+var_30], xmm0
0x180031d8c  call    cs:__imp_InitializeSecurityDescriptor
0x180031d93  nop     dword ptr [rax+rax+00h]
0x180031d98  test    eax, eax
0x180031d9a  jnz     short loc_180031DB5
0x180031d9c  mov     edx, 92h; void *
0x180031da1  mov     rcx, [rbp+5Fh]; this
0x180031da5  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031dac  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180031db1  mov     ebx, eax
0x180031db3  jmp     short loc_180031D67
0x180031db5  mov     r8, [rbp+57h+var_88]; pDacl
0x180031db9  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180031dbd  xor     r9d, r9d; bDaclDefaulted
0x180031dc0  mov     edx, ebx; bDaclPresent
0x180031dc2  call    cs:__imp_SetSecurityDescriptorDacl
0x180031dc9  nop     dword ptr [rax+rax+00h]
0x180031dce  test    eax, eax
0x180031dd0  jnz     short loc_180031DD9
0x180031dd2  mov     edx, 93h
0x180031dd7  jmp     short loc_180031DA1
0x180031dd9  mov     rcx, [rbp+57h+var_98]; hKey
0x180031ddd  lea     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180031de1  mov     edx, 4; SecurityInformation
0x180031de6  call    cs:__imp_RegSetKeySecurity
0x180031ded  nop     dword ptr [rax+rax+00h]
0x180031df2  test    eax, eax
0x180031df4  jz      short loc_180031E10
0x180031df6  mov     rcx, [rbp+5Fh]; this
0x180031dfa  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031e01  mov     r9d, eax; char *
0x180031e04  mov     edx, 95h; void *
0x180031e09  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180031e0e  jmp     short loc_180031DB1
0x180031e10  lea     rcx, [rbp+57h+var_88]
0x180031e14  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180031e19  lea     rcx, [rbp+57h+Sid]
0x180031e1d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180031e22  lea     rcx, [rbp+57h+var_90]
0x180031e26  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180031e2b  lea     rcx, [rbp+57h+hKey]
0x180031e2f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180031e34  lea     rcx, [rbp+57h+var_98]
0x180031e38  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180031e3d  lea     rcx, [rbp+57h+lpSubKey]
0x180031e41  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180031e46  mov     ebx, esi
0x180031e48  lea     rcx, [rbp+57h+var_60]
0x180031e4c  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180031e51  mov     eax, ebx
0x180031e53  mov     rbx, [rsp+0D0h+arg_0]
0x180031e5b  add     rsp, 0C0h
0x180031e62  pop     rdi
0x180031e63  pop     rsi
0x180031e64  pop     rbp
0x180031e65  retn
```
