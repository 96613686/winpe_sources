# SetupPreferenceKey(ushort const *)

- ea: `0x18003164c`
- end: `0x1800319e3`
- name: `?SetupPreferenceKey@@YAJPEBG@Z`
- size: `919`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180045494`

## callees

- `0x18000d2c0`
- `0x18000dc10`
- `0x18000e1a0`
- `0x1800130d0`
- `0x180013770`
- `0x18002793c`
- `0x18002df48`
- `0x180030ad0`
- `0x180031060`
- `0x18003164c`
- `0x1800493b4`
- `0x18004fb94`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800317a4`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180031837`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800317a4`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180031837`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003171b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003171b`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180031974`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180031974`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180031953`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180031953`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18003191d`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18003191d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18003187c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18003187c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800317e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800317e7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003175e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003175e`

## string_xrefs

- `0x1800316c8`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18003172f`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180031772`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x1800317cc`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18003180d`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18003184b`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180031890`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x1800318e1`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180031936`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180031988`: `onecore\ds\security\gina\profile\profsvc\util.cpp`

## pseudocode

```c
__int64 __fastcall SetupPreferenceKey(LPCWCH lpString1)
{
  int ProfileListKeyNameFromSid; // eax
  unsigned int LastError; // ebx
  __int64 v4; // rdx
  unsigned int v5; // eax
  const char *v6; // r9
  LSTATUS KeySecurity; // eax
  HLOCAL v8; // rax
  void *v9; // rbx
  __int64 v10; // rdx
  unsigned int v11; // eax
  int v12; // eax
  const char *v13; // r9
  unsigned int v14; // r8d
  int v15; // eax
  const char *v16; // r9
  __int64 v17; // rdx
  int v18; // eax
  unsigned int v19; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-59h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-59h]
  HKEY hKey; // [rsp+50h] [rbp-29h] BYREF
  PSID Sid; // [rsp+58h] [rbp-21h] BYREF
  HLOCAL v25; // [rsp+60h] [rbp-19h] BYREF
  PACL v26; // [rsp+68h] [rbp-11h] BYREF
  LPCWSTR lpSubKey; // [rsp+70h] [rbp-9h] BYREF
  __int64 v28; // [rsp+78h] [rbp-1h]
  __int64 v29; // [rsp+80h] [rbp+7h]
  PACL pDacl; // [rsp+88h] [rbp+Fh] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+90h] [rbp+17h] BYREF
  __int64 v32; // [rsp+B0h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  DWORD cbSecurityDescriptor; // [rsp+E8h] [rbp+6Fh] BYREF
  WINBOOL bDaclPresent; // [rsp+F0h] [rbp+77h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+F8h] [rbp+7Fh] BYREF

  lpSubKey = 0;
  v28 = 0;
  v29 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
  v28 = -1;
  v29 = -1;
  ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(lpString1, (unsigned __int16 **)&lpSubKey, 0);
  LastError = ProfileListKeyNameFromSid;
  if ( ProfileListKeyNameFromSid >= 0 )
  {
    ProfileListKeyNameFromSid = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::ConcatFormat(
                                  &lpSubKey,
                                  L"\\%s",
                                  L"Preference");
    LastError = ProfileListKeyNameFromSid;
    if ( ProfileListKeyNameFromSid < 0 )
    {
      v4 = 331;
      goto LABEL_5;
    }
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    if ( v5 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x157,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
                    (const char *)v5,
                    dwOptionsa);
LABEL_8:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_40;
    }
    Sid = 0;
    if ( !ConvertStringSidToSidW(lpString1, &Sid) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x15B,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
                    v6);
LABEL_11:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
      goto LABEL_8;
    }
    cbSecurityDescriptor = 0;
    KeySecurity = RegGetKeySecurity(hKey, 4u, 0, &cbSecurityDescriptor);
    LastError = KeySecurity;
    if ( KeySecurity != 122 )
    {
      if ( KeySecurity > 0 )
        LastError = (unsigned __int16)KeySecurity | 0x80070000;
      if ( (LastError & 0x80000000) != 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x160,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
          (const char *)LastError,
          dwOptionsa);
      goto LABEL_11;
    }
    v8 = LocalAlloc(0, cbSecurityDescriptor);
    v25 = v8;
    v9 = v8;
    if ( !v8 )
    {
      LastError = -2147024882;
      v10 = 355;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
        (const char *)LastError,
        dwOptionsa);
LABEL_20:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v25);
      goto LABEL_11;
    }
    v11 = RegGetKeySecurity(hKey, 4u, v8, &cbSecurityDescriptor);
    if ( v11 )
    {
      v12 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x165,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
              (const char *)v11,
              dwOptionsa);
LABEL_23:
      LastError = v12;
      goto LABEL_20;
    }
    pDacl = 0;
    bDaclPresent = 0;
    bDaclDefaulted = 0;
    if ( !GetSecurityDescriptorDacl(v9, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      v12 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x16C,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
              v13);
      goto LABEL_23;
    }
    if ( !bDaclPresent )
    {
      LastError = -2147023558;
      v10 = 365;
      goto LABEL_19;
    }
    v26 = 0;
    wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::reset(
      &v26,
      0);
    v15 = AddSidToAcl(pDacl, Sid, v14, &v26);
    LastError = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x171,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
        (const char *)(unsigned int)v15,
        dwOptionsa);
LABEL_30:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v26);
      goto LABEL_20;
    }
    v32 = 0;
    memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
    if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    {
      if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v26, 0) )
      {
        v19 = RegSetKeySecurity(hKey, 4u, pSecurityDescriptor);
        if ( !v19 )
        {
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v26);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v25);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          LastError = 0;
          goto LABEL_40;
        }
        v18 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x178,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
                (const char *)v19,
                dwOptionsa);
        goto LABEL_34;
      }
      v17 = 374;
    }
    else
    {
      v17 = 373;
    }
    v18 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v17,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
            v16);
LABEL_34:
    LastError = v18;
    goto LABEL_30;
  }
  v4 = 330;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
    (const char *)(unsigned int)ProfileListKeyNameFromSid,
    dwOptions);
LABEL_40:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
  return LastError;
}

```

## disassembly

```asm
0x18003164c  mov     [rsp-8+arg_0], rbx
0x180031651  push    rbp
0x180031652  push    rsi
0x180031653  push    rdi
0x180031654  lea     rbp, [rsp-47h]
0x180031659  sub     rsp, 0C0h
0x180031660  xor     esi, esi
0x180031662  mov     rdi, rcx
0x180031665  lea     rcx, [rbp+57h+lpSubKey]
0x180031669  mov     [rbp+57h+lpSubKey], rsi
0x18003166d  mov     [rbp+57h+var_58], rsi
0x180031671  mov     [rbp+57h+var_50], rsi
0x180031675  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18003167a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003167e  lea     rdx, [rbp+57h+lpSubKey]; unsigned __int16 **
0x180031682  xor     r8d, r8d; int *
0x180031685  mov     [rbp+57h+var_58], rax
0x180031689  mov     rcx, rdi; lpString1
0x18003168c  mov     [rbp+57h+var_50], rax
0x180031690  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x180031695  mov     ebx, eax
0x180031697  test    eax, eax
0x180031699  jns     short loc_1800316A2
0x18003169b  mov     edx, 14Ah
0x1800316a0  jmp     short loc_1800316C4
0x1800316a2  lea     r8, aPreference; "Preference"
0x1800316a9  lea     rdx, aS_1; "\\%s"
0x1800316b0  lea     rcx, [rbp+57h+lpSubKey]
0x1800316b4  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x1800316b9  mov     ebx, eax
0x1800316bb  test    eax, eax
0x1800316bd  jns     short loc_1800316DC
0x1800316bf  mov     edx, 14Bh; void *
0x1800316c4  mov     rcx, [rbp+5Fh]; this
0x1800316c8  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800316cf  mov     r9d, eax; char *
0x1800316d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800316d7  jmp     loc_1800319C4
0x1800316dc  xor     edx, edx
0x1800316de  mov     [rbp+57h+hKey], rsi
0x1800316e2  lea     rcx, [rbp+57h+hKey]
0x1800316e6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800316eb  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1800316ef  lea     rax, [rbp+57h+hKey]
0x1800316f3  mov     [rsp+0D0h+lpdwDisposition], rsi; lpdwDisposition
0x1800316f8  xor     r9d, r9d; lpClass
0x1800316fb  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180031700  xor     r8d, r8d; Reserved
0x180031703  mov     [rsp+0D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180031708  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003170f  mov     [rsp+0D0h+samDesired], 0F003Fh; samDesired
0x180031717  mov     [rsp+0D0h+dwOptions], esi; unsigned int
0x18003171b  call    cs:__imp_RegCreateKeyExW
0x180031722  nop     dword ptr [rax+rax+00h]
0x180031727  test    eax, eax
0x180031729  jz      short loc_180031753
0x18003172b  mov     rcx, [rbp+5Fh]; this
0x18003172f  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031736  mov     r9d, eax; char *
0x180031739  mov     edx, 157h; void *
0x18003173e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180031743  mov     ebx, eax
0x180031745  lea     rcx, [rbp+57h+hKey]
0x180031749  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003174e  jmp     loc_1800319C4
0x180031753  lea     rdx, [rbp+57h+Sid]; Sid
0x180031757  mov     [rbp+57h+Sid], rsi
0x18003175b  mov     rcx, rdi; StringSid
0x18003175e  call    cs:__imp_ConvertStringSidToSidW
0x180031765  nop     dword ptr [rax+rax+00h]
0x18003176a  test    eax, eax
0x18003176c  jnz     short loc_180031790
0x18003176e  mov     rcx, [rbp+5Fh]; this
0x180031772  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031779  mov     edx, 15Bh; void *
0x18003177e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180031783  mov     ebx, eax
0x180031785  lea     rcx, [rbp+57h+Sid]
0x180031789  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18003178e  jmp     short loc_180031745
0x180031790  mov     rcx, [rbp+57h+hKey]; hKey
0x180031794  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180031798  xor     r8d, r8d; pSecurityDescriptor
0x18003179b  mov     [rbp+57h+cbSecurityDescriptor], esi
0x18003179e  lea     edi, [r8+4]
0x1800317a2  mov     edx, edi; SecurityInformation
0x1800317a4  call    cs:__imp_RegGetKeySecurity
0x1800317ab  nop     dword ptr [rax+rax+00h]
0x1800317b0  mov     ebx, eax
0x1800317b2  cmp     eax, 7Ah ; 'z'
0x1800317b5  jz      short loc_1800317E2
0x1800317b7  test    eax, eax
0x1800317b9  jle     short loc_1800317C4
0x1800317bb  movzx   ebx, ax
0x1800317be  or      ebx, 80070000h
0x1800317c4  test    ebx, ebx
0x1800317c6  jns     short loc_180031785
0x1800317c8  mov     rcx, [rbp+5Fh]; this
0x1800317cc  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800317d3  mov     r9d, ebx; char *
0x1800317d6  mov     edx, 160h; void *
0x1800317db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800317e0  jmp     short loc_180031785
0x1800317e2  mov     edx, [rbp+57h+cbSecurityDescriptor]; uBytes
0x1800317e5  xor     ecx, ecx; uFlags
0x1800317e7  call    cs:__imp_LocalAlloc
0x1800317ee  nop     dword ptr [rax+rax+00h]
0x1800317f3  mov     [rbp+57h+var_70], rax
0x1800317f7  mov     rbx, rax
0x1800317fa  test    rax, rax
0x1800317fd  jnz     short loc_18003182A
0x1800317ff  mov     ebx, 8007000Eh
0x180031804  mov     edx, 163h; void *
0x180031809  mov     rcx, [rbp+5Fh]; this
0x18003180d  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031814  mov     r9d, ebx; char *
0x180031817  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003181c  lea     rcx, [rbp+57h+var_70]
0x180031820  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180031825  jmp     loc_180031785
0x18003182a  mov     rcx, [rbp+57h+hKey]; hKey
0x18003182e  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180031832  mov     r8, rbx; pSecurityDescriptor
0x180031835  mov     edx, edi; SecurityInformation
0x180031837  call    cs:__imp_RegGetKeySecurity
0x18003183e  nop     dword ptr [rax+rax+00h]
0x180031843  test    eax, eax
0x180031845  jz      short loc_180031863
0x180031847  mov     rcx, [rbp+5Fh]; this
0x18003184b  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031852  mov     r9d, eax; char *
0x180031855  mov     edx, 165h; void *
0x18003185a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003185f  mov     ebx, eax
0x180031861  jmp     short loc_18003181C
0x180031863  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180031867  mov     [rbp+57h+pDacl], rsi
0x18003186b  lea     r8, [rbp+57h+pDacl]; pDacl
0x18003186f  mov     [rbp+57h+bDaclPresent], esi
0x180031872  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180031876  mov     [rbp+57h+bDaclDefaulted], esi
0x180031879  mov     rcx, rbx; pSecurityDescriptor
0x18003187c  call    cs:__imp_GetSecurityDescriptorDacl
0x180031883  nop     dword ptr [rax+rax+00h]
0x180031888  test    eax, eax
0x18003188a  jnz     short loc_1800318A3
0x18003188c  mov     rcx, [rbp+5Fh]; this
0x180031890  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180031897  mov     edx, 16Ch; void *
0x18003189c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800318a1  jmp     short loc_18003185F
0x1800318a3  cmp     [rbp+57h+bDaclPresent], esi
0x1800318a6  jnz     short loc_1800318B7
0x1800318a8  mov     ebx, 8007053Ah
0x1800318ad  mov     edx, 16Dh
0x1800318b2  jmp     loc_180031809
0x1800318b7  xor     edx, edx
0x1800318b9  mov     [rbp+57h+var_68], rsi
0x1800318bd  lea     rcx, [rbp+57h+var_68]
0x1800318c1  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_ACL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_ACL@@@Z; wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::reset(_ACL *)
0x1800318c6  mov     rdx, [rbp+57h+Sid]; void *
0x1800318ca  lea     r9, [rbp+57h+var_68]; struct _ACL **
0x1800318ce  mov     rcx, [rbp+57h+pDacl]; struct _ACL *
0x1800318d2  call    ?AddSidToAcl@@YAJPEAU_ACL@@PEAXKPEAPEAU1@@Z; AddSidToAcl(_ACL *,void *,ulong,_ACL * *)
0x1800318d7  mov     ebx, eax
0x1800318d9  test    eax, eax
0x1800318db  jns     short loc_180031903
0x1800318dd  mov     rcx, [rbp+5Fh]; this
0x1800318e1  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800318e8  mov     r9d, eax; char *
0x1800318eb  mov     edx, 171h; void *
0x1800318f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800318f5  lea     rcx, [rbp+57h+var_68]
0x1800318f9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800318fe  jmp     loc_18003181C
0x180031903  xor     eax, eax
0x180031905  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180031909  xorps   xmm0, xmm0
0x18003190c  mov     [rbp+57h+var_20], rax
0x180031910  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x180031914  lea     ebx, [rax+1]
0x180031917  mov     edx, ebx; dwRevision
0x180031919  movups  [rbp+57h+var_30], xmm0
0x18003191d  call    cs:__imp_InitializeSecurityDescriptor
0x180031924  nop     dword ptr [rax+rax+00h]
0x180031929  test    eax, eax
0x18003192b  jnz     short loc_180031946
0x18003192d  mov     edx, 175h; void *
0x180031932  mov     rcx, [rbp+5Fh]; this
0x180031936  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003193d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180031942  mov     ebx, eax
0x180031944  jmp     short loc_1800318F5
0x180031946  mov     r8, [rbp+57h+var_68]; pDacl
0x18003194a  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18003194e  xor     r9d, r9d; bDaclDefaulted
0x180031951  mov     edx, ebx; bDaclPresent
0x180031953  call    cs:__imp_SetSecurityDescriptorDacl
0x18003195a  nop     dword ptr [rax+rax+00h]
0x18003195f  test    eax, eax
0x180031961  jnz     short loc_18003196A
0x180031963  mov     edx, 176h
0x180031968  jmp     short loc_180031932
0x18003196a  mov     rcx, [rbp+57h+hKey]; hKey
0x18003196e  lea     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180031972  mov     edx, edi; SecurityInformation
0x180031974  call    cs:__imp_RegSetKeySecurity
0x18003197b  nop     dword ptr [rax+rax+00h]
0x180031980  test    eax, eax
0x180031982  jz      short loc_18003199E
0x180031984  mov     rcx, [rbp+5Fh]; this
0x180031988  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003198f  mov     r9d, eax; char *
0x180031992  mov     edx, 178h; void *
0x180031997  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003199c  jmp     short loc_180031942
0x18003199e  lea     rcx, [rbp+57h+var_68]
0x1800319a2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800319a7  lea     rcx, [rbp+57h+var_70]
0x1800319ab  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800319b0  lea     rcx, [rbp+57h+Sid]
0x1800319b4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800319b9  lea     rcx, [rbp+57h+hKey]
0x1800319bd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800319c2  mov     ebx, esi
0x1800319c4  lea     rcx, [rbp+57h+lpSubKey]
0x1800319c8  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800319cd  mov     eax, ebx
0x1800319cf  mov     rbx, [rsp+0D0h+arg_0]
0x1800319d7  add     rsp, 0C0h
0x1800319de  pop     rdi
0x1800319df  pop     rsi
0x1800319e0  pop     rbp
0x1800319e1  retn
```
