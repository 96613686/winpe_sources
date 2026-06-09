# SetupPreferenceKey(ushort const *)

- ea: `0x18002d7c0`
- end: `0x18002db30`
- name: `?SetupPreferenceKey@@YAJPEBG@Z`
- size: `880`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800439c0`

## callees

- `0x18000f1b0`
- `0x18000fa10`
- `0x1800111a0`
- `0x18001f060`
- `0x180025254`
- `0x18002d2d8`
- `0x18002d7c0`
- `0x18002db38`
- `0x18002e648`
- `0x180047258`
- `0x18004cb54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d8c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002db0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d8c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002db0a`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18002d916`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18002d99d`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18002d916`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18002d99d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d88f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d88f`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18002dac2`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18002dac2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002daa7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002daa7`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002da77`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002da77`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002d9dc`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002d9dc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d953`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d953`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002d8d6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002d8d6`

## string_xrefs

- `0x18002d83c`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002d89d`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002d8e4`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002d938`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002d973`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002d9ab`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002d9ea`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002da3b`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002da8a`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002dad0`: `onecore\ds\security\gina\profile\profsvc\util.cpp`

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
  __int64 v14; // r8
  int v15; // eax
  const char *v16; // r9
  __int64 v17; // rdx
  int v18; // eax
  unsigned int v19; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-59h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-59h]
  HKEY hKey; // [rsp+50h] [rbp-29h] BYREF
  PSID Sid; // [rsp+58h] [rbp-21h] BYREF
  void *v25; // [rsp+60h] [rbp-19h] BYREF
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
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpSubKey);
  v28 = -1;
  v29 = -1;
  ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(lpString1, (unsigned __int16 **)&lpSubKey, 0);
  LastError = ProfileListKeyNameFromSid;
  if ( ProfileListKeyNameFromSid < 0 )
  {
    v4 = 330;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
      (const char *)(unsigned int)ProfileListKeyNameFromSid,
      dwOptions);
    goto LABEL_43;
  }
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
    goto LABEL_8;
  }
  Sid = 0;
  if ( !ConvertStringSidToSidW(lpString1, &Sid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x15B,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
                  v6);
LABEL_12:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
LABEL_8:
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_43;
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
    goto LABEL_12;
  }
  v8 = LocalAlloc(0, cbSecurityDescriptor);
  v25 = v8;
  v9 = v8;
  if ( !v8 )
  {
    LastError = -2147024882;
    v10 = 355;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
      (const char *)LastError,
      dwOptionsa);
LABEL_21:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v25);
    goto LABEL_12;
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
LABEL_24:
    LastError = v12;
    goto LABEL_21;
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
    goto LABEL_24;
  }
  if ( !bDaclPresent )
  {
    LastError = -2147023558;
    v10 = 365;
    goto LABEL_20;
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
LABEL_31:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((void **)&v26);
    goto LABEL_21;
  }
  v32 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
  {
    v17 = 373;
LABEL_34:
    v18 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v17,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
            v16);
LABEL_35:
    LastError = v18;
    goto LABEL_31;
  }
  if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v26, 0) )
  {
    v17 = 374;
    goto LABEL_34;
  }
  v19 = RegSetKeySecurity(hKey, 4u, pSecurityDescriptor);
  if ( v19 )
  {
    v18 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x178,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
            (const char *)v19,
            dwOptionsa);
    goto LABEL_35;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((void **)&v26);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v25);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
  if ( hKey )
    RegCloseKey(hKey);
  LastError = 0;
LABEL_43:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpSubKey);
  return LastError;
}

```

## disassembly

```asm
0x18002d7c0  mov     [rsp-8+arg_0], rbx
0x18002d7c5  push    rbp
0x18002d7c6  push    rsi
0x18002d7c7  push    rdi
0x18002d7c8  lea     rbp, [rsp-47h]
0x18002d7cd  sub     rsp, 0C0h
0x18002d7d4  xor     esi, esi
0x18002d7d6  mov     rdi, rcx
0x18002d7d9  lea     rcx, [rbp+57h+lpSubKey]
0x18002d7dd  mov     [rbp+57h+lpSubKey], rsi
0x18002d7e1  mov     [rbp+57h+var_58], rsi
0x18002d7e5  mov     [rbp+57h+var_50], rsi
0x18002d7e9  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002d7ee  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d7f2  lea     rdx, [rbp+57h+lpSubKey]; unsigned __int16 **
0x18002d7f6  xor     r8d, r8d; int *
0x18002d7f9  mov     [rbp+57h+var_58], rax
0x18002d7fd  mov     rcx, rdi; lpString1
0x18002d800  mov     [rbp+57h+var_50], rax
0x18002d804  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x18002d809  mov     ebx, eax
0x18002d80b  test    eax, eax
0x18002d80d  jns     short loc_18002D816
0x18002d80f  mov     edx, 14Ah
0x18002d814  jmp     short loc_18002D838
0x18002d816  lea     r8, aPreference; "Preference"
0x18002d81d  lea     rdx, aS_1; "\\%s"
0x18002d824  lea     rcx, [rbp+57h+lpSubKey]
0x18002d828  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x18002d82d  mov     ebx, eax
0x18002d82f  test    eax, eax
0x18002d831  jns     short loc_18002D850
0x18002d833  mov     edx, 14Bh; void *
0x18002d838  mov     rcx, [rbp+5Fh]; this
0x18002d83c  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d843  mov     r9d, eax; char *
0x18002d846  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d84b  jmp     loc_18002DB12
0x18002d850  xor     edx, edx
0x18002d852  mov     [rbp+57h+hKey], rsi
0x18002d856  lea     rcx, [rbp+57h+hKey]
0x18002d85a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002d85f  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18002d863  lea     rax, [rbp+57h+hKey]
0x18002d867  mov     [rsp+0D0h+lpdwDisposition], rsi; lpdwDisposition
0x18002d86c  xor     r9d, r9d; lpClass
0x18002d86f  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18002d874  xor     r8d, r8d; Reserved
0x18002d877  mov     [rsp+0D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18002d87c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d883  mov     [rsp+0D0h+samDesired], 0F003Fh; samDesired
0x18002d88b  mov     [rsp+0D0h+dwOptions], esi; unsigned int
0x18002d88f  call    cs:__imp_RegCreateKeyExW
0x18002d895  test    eax, eax
0x18002d897  jz      short loc_18002D8CB
0x18002d899  mov     rcx, [rbp+5Fh]; this
0x18002d89d  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d8a4  mov     r9d, eax; char *
0x18002d8a7  mov     edx, 157h; void *
0x18002d8ac  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002d8b1  mov     ebx, eax
0x18002d8b3  mov     rcx, [rbp+57h+hKey]; hKey
0x18002d8b7  test    rcx, rcx
0x18002d8ba  jz      loc_18002DB12
0x18002d8c0  call    cs:__imp_RegCloseKey
0x18002d8c6  jmp     loc_18002DB12
0x18002d8cb  lea     rdx, [rbp+57h+Sid]; Sid
0x18002d8cf  mov     [rbp+57h+Sid], rsi
0x18002d8d3  mov     rcx, rdi; StringSid
0x18002d8d6  call    cs:__imp_ConvertStringSidToSidW
0x18002d8dc  test    eax, eax
0x18002d8de  jnz     short loc_18002D902
0x18002d8e0  mov     rcx, [rbp+5Fh]; this
0x18002d8e4  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d8eb  mov     edx, 15Bh; void *
0x18002d8f0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d8f5  mov     ebx, eax
0x18002d8f7  lea     rcx, [rbp+57h+Sid]
0x18002d8fb  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002d900  jmp     short loc_18002D8B3
0x18002d902  mov     rcx, [rbp+57h+hKey]; hKey
0x18002d906  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18002d90a  xor     r8d, r8d; pSecurityDescriptor
0x18002d90d  mov     [rbp+57h+cbSecurityDescriptor], esi
0x18002d910  lea     edi, [r8+4]
0x18002d914  mov     edx, edi; SecurityInformation
0x18002d916  call    cs:__imp_RegGetKeySecurity
0x18002d91c  mov     ebx, eax
0x18002d91e  cmp     eax, 7Ah ; 'z'
0x18002d921  jz      short loc_18002D94E
0x18002d923  test    eax, eax
0x18002d925  jle     short loc_18002D930
0x18002d927  movzx   ebx, ax
0x18002d92a  or      ebx, 80070000h
0x18002d930  test    ebx, ebx
0x18002d932  jns     short loc_18002D8F7
0x18002d934  mov     rcx, [rbp+5Fh]; this
0x18002d938  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d93f  mov     r9d, ebx; char *
0x18002d942  mov     edx, 160h; void *
0x18002d947  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d94c  jmp     short loc_18002D8F7
0x18002d94e  mov     edx, [rbp+57h+cbSecurityDescriptor]; uBytes
0x18002d951  xor     ecx, ecx; uFlags
0x18002d953  call    cs:__imp_LocalAlloc
0x18002d959  mov     [rbp+57h+var_70], rax
0x18002d95d  mov     rbx, rax
0x18002d960  test    rax, rax
0x18002d963  jnz     short loc_18002D990
0x18002d965  mov     ebx, 8007000Eh
0x18002d96a  mov     edx, 163h; void *
0x18002d96f  mov     rcx, [rbp+5Fh]; this
0x18002d973  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d97a  mov     r9d, ebx; char *
0x18002d97d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d982  lea     rcx, [rbp+57h+var_70]
0x18002d986  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002d98b  jmp     loc_18002D8F7
0x18002d990  mov     rcx, [rbp+57h+hKey]; hKey
0x18002d994  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18002d998  mov     r8, rbx; pSecurityDescriptor
0x18002d99b  mov     edx, edi; SecurityInformation
0x18002d99d  call    cs:__imp_RegGetKeySecurity
0x18002d9a3  test    eax, eax
0x18002d9a5  jz      short loc_18002D9C3
0x18002d9a7  mov     rcx, [rbp+5Fh]; this
0x18002d9ab  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d9b2  mov     r9d, eax; char *
0x18002d9b5  mov     edx, 165h; void *
0x18002d9ba  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002d9bf  mov     ebx, eax
0x18002d9c1  jmp     short loc_18002D982
0x18002d9c3  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x18002d9c7  mov     [rbp+57h+pDacl], rsi
0x18002d9cb  lea     r8, [rbp+57h+pDacl]; pDacl
0x18002d9cf  mov     [rbp+57h+bDaclPresent], esi
0x18002d9d2  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x18002d9d6  mov     [rbp+57h+bDaclDefaulted], esi
0x18002d9d9  mov     rcx, rbx; pSecurityDescriptor
0x18002d9dc  call    cs:__imp_GetSecurityDescriptorDacl
0x18002d9e2  test    eax, eax
0x18002d9e4  jnz     short loc_18002D9FD
0x18002d9e6  mov     rcx, [rbp+5Fh]; this
0x18002d9ea  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002d9f1  mov     edx, 16Ch; void *
0x18002d9f6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d9fb  jmp     short loc_18002D9BF
0x18002d9fd  cmp     [rbp+57h+bDaclPresent], esi
0x18002da00  jnz     short loc_18002DA11
0x18002da02  mov     ebx, 8007053Ah
0x18002da07  mov     edx, 16Dh
0x18002da0c  jmp     loc_18002D96F
0x18002da11  xor     edx, edx
0x18002da13  mov     [rbp+57h+var_68], rsi
0x18002da17  lea     rcx, [rbp+57h+var_68]
0x18002da1b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_ACL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_ACL@@@Z; wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::reset(_ACL *)
0x18002da20  mov     rdx, [rbp+57h+Sid]; void *
0x18002da24  lea     r9, [rbp+57h+var_68]; struct _ACL **
0x18002da28  mov     rcx, [rbp+57h+pDacl]; struct _ACL *
0x18002da2c  call    ?AddSidToAcl@@YAJPEAU_ACL@@PEAXKPEAPEAU1@@Z; AddSidToAcl(_ACL *,void *,ulong,_ACL * *)
0x18002da31  mov     ebx, eax
0x18002da33  test    eax, eax
0x18002da35  jns     short loc_18002DA5D
0x18002da37  mov     rcx, [rbp+5Fh]; this
0x18002da3b  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002da42  mov     r9d, eax; char *
0x18002da45  mov     edx, 171h; void *
0x18002da4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002da4f  lea     rcx, [rbp+57h+var_68]
0x18002da53  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002da58  jmp     loc_18002D982
0x18002da5d  xor     eax, eax
0x18002da5f  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18002da63  xorps   xmm0, xmm0
0x18002da66  mov     [rbp+57h+var_20], rax
0x18002da6a  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x18002da6e  lea     ebx, [rax+1]
0x18002da71  mov     edx, ebx; dwRevision
0x18002da73  movups  [rbp+57h+var_30], xmm0
0x18002da77  call    cs:__imp_InitializeSecurityDescriptor
0x18002da7d  test    eax, eax
0x18002da7f  jnz     short loc_18002DA9A
0x18002da81  mov     edx, 175h; void *
0x18002da86  mov     rcx, [rbp+5Fh]; this
0x18002da8a  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002da91  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002da96  mov     ebx, eax
0x18002da98  jmp     short loc_18002DA4F
0x18002da9a  mov     r8, [rbp+57h+var_68]; pDacl
0x18002da9e  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18002daa2  xor     r9d, r9d; bDaclDefaulted
0x18002daa5  mov     edx, ebx; bDaclPresent
0x18002daa7  call    cs:__imp_SetSecurityDescriptorDacl
0x18002daad  test    eax, eax
0x18002daaf  jnz     short loc_18002DAB8
0x18002dab1  mov     edx, 176h
0x18002dab6  jmp     short loc_18002DA86
0x18002dab8  mov     rcx, [rbp+57h+hKey]; hKey
0x18002dabc  lea     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18002dac0  mov     edx, edi; SecurityInformation
0x18002dac2  call    cs:__imp_RegSetKeySecurity
0x18002dac8  test    eax, eax
0x18002daca  jz      short loc_18002DAE6
0x18002dacc  mov     rcx, [rbp+5Fh]; this
0x18002dad0  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002dad7  mov     r9d, eax; char *
0x18002dada  mov     edx, 178h; void *
0x18002dadf  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002dae4  jmp     short loc_18002DA96
0x18002dae6  lea     rcx, [rbp+57h+var_68]
0x18002daea  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002daef  lea     rcx, [rbp+57h+var_70]
0x18002daf3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002daf8  lea     rcx, [rbp+57h+Sid]
0x18002dafc  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002db01  mov     rcx, [rbp+57h+hKey]; hKey
0x18002db05  test    rcx, rcx
0x18002db08  jz      short loc_18002DB10
0x18002db0a  call    cs:__imp_RegCloseKey
0x18002db10  mov     ebx, esi
0x18002db12  lea     rcx, [rbp+57h+lpSubKey]
0x18002db16  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002db1b  mov     eax, ebx
0x18002db1d  mov     rbx, [rsp+0D0h+arg_0]
0x18002db25  add     rsp, 0C0h
0x18002db2c  pop     rdi
0x18002db2d  pop     rsi
0x18002db2e  pop     rbp
0x18002db2f  retn
```
