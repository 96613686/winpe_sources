# CUserProfile::GetOldKeyFromGuid(void *,ushort const *,HKEY__ * *,ulong *)

- ea: `0x18002b2a0`
- end: `0x18002b6b2`
- name: `?GetOldKeyFromGuid@CUserProfile@@IEAAJPEAXPEBGPEAPEAUHKEY__@@PEAK@Z`
- size: `1042`
- prototype: `__int64 __usercall@<rax>(CUserProfile *__hidden this@<rcx>, HANDLE TokenHandle@<rdx>, LPCWCH lpString1@<r8>, HKEY *@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001ea8c`

## callees

- `0x1800049e0`
- `0x18000f1b0`
- `0x1800111a0`
- `0x1800154e0`
- `0x180015d00`
- `0x18001ecc4`
- `0x18001f060`
- `0x180021d00`
- `0x18002444c`
- `0x18002541c`
- `0x18002b2a0`
- `0x18002d2d8`
- `0x18002e648`
- `0x18002fae4`
- `0x180041e18`
- `0x180046b08`
- `0x18004e444`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b619`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b619`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b632`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b632`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002b359`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002b359`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b4a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b4a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b3b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b3ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b4ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b4fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b3b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b3ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b4ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b4fd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002b5eb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002b5eb`
- `ntdll!RtlLengthSid` at `0x18002b5c5`
- `ntdll!RtlLengthSid` at `0x18002b5c5`
- `api-ms-win-core-registry-private-l1-1-0!RegRenameKey` at `0x18002b4e3`
- `api-ms-win-core-registry-private-l1-1-0!RegRenameKey` at `0x18002b4e3`

## string_xrefs

- `0x18002b396`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002b442`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002b4b0`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002b56b`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002b5a2`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002b5fc`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002b68b`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18002b612`: `msi.dll`
- `0x18002b628`: `MsiNotifySidChangeW`

## pseudocode

```c
__int64 __fastcall CUserProfile::GetOldKeyFromGuid(
        CUserProfile *this,
        HANDLE TokenHandle,
        LPCWCH lpString1,
        HKEY *a4,
        unsigned int *a5)
{
  int v9; // r14d
  unsigned int *v10; // rsi
  const unsigned __int16 *v11; // rdx
  const unsigned __int16 *v12; // rdi
  int v13; // eax
  unsigned int v14; // ebx
  bool v15; // bl
  int UserProfileListRootKeyName; // eax
  __int64 v17; // rdx
  unsigned __int64 v18; // r9
  unsigned int v19; // eax
  __int64 v20; // rdx
  HKEY v21; // rcx
  int ProfileListKeyNameFromSid; // eax
  CUserProfile *v23; // rcx
  int v24; // eax
  int UserSid; // eax
  const BYTE *v26; // rbx
  ULONG v27; // eax
  HKEY v28; // rbx
  unsigned int v29; // eax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  int lpString2; // [rsp+20h] [rbp-51h]
  unsigned int lpString2a; // [rsp+20h] [rbp-51h]
  const BYTE *lpString2c; // [rsp+20h] [rbp-51h]
  unsigned int lpString2b; // [rsp+20h] [rbp-51h]
  unsigned int v37; // [rsp+30h] [rbp-41h] BYREF
  HKEY v38; // [rsp+38h] [rbp-39h] BYREF
  PSID Sid; // [rsp+40h] [rbp-31h] BYREF
  LPCWSTR lpSubKey; // [rsp+48h] [rbp-29h] BYREF
  __int64 v41; // [rsp+50h] [rbp-21h]
  __int64 v42; // [rsp+58h] [rbp-19h]
  PCNZWCH lpString1a; // [rsp+60h] [rbp-11h] BYREF
  __int64 v44; // [rsp+68h] [rbp-9h]
  __int64 v45; // [rsp+70h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]
  HKEY hKey; // [rsp+D8h] [rbp+67h] BYREF

  v9 = 0;
  if ( !TokenHandle || !lpString1 || !a4 )
  {
    v14 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA4B,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)0x80070057LL,
      lpString2);
    return v14;
  }
  *a4 = 0;
  v10 = a5;
  if ( a5 )
    *a5 = 0;
  lpString1a = 0;
  v44 = 0;
  v45 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpString1a);
  v44 = -1;
  v45 = -1;
  if ( (int)GetOldSidString(TokenHandle, v11, (unsigned __int16 **)&lpString1a) < 0 )
    goto LABEL_50;
  v12 = lpString1a;
  if ( !lpString1a || !*lpString1a || CompareStringW(0x7Fu, 1u, lpString1a, -1, lpString1, -1) == 2 )
    goto LABEL_50;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v13 = CUserProfile::RestoreKeyFromBackup(this, v12, &hKey, 0);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5F,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)v13,
      lpString2a);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_51;
  }
  v15 = hKey != 0;
  if ( hKey )
    RegCloseKey(hKey);
  if ( !v15 )
    goto LABEL_50;
  lpSubKey = 0;
  v41 = 0;
  v42 = 0;
  LODWORD(hKey) = 0;
  if ( (unsigned int)IsServiceSid(v12) )
  {
    UserProfileListRootKeyName = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Initialize(
                                   &lpSubKey,
                                   L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
                                   -1);
  }
  else
  {
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpSubKey);
    v41 = -1;
    v42 = -1;
    UserProfileListRootKeyName = GetUserProfileListRootKeyName((unsigned __int16 **)&lpSubKey, (int *)&hKey);
    v9 = (int)hKey;
  }
  v14 = UserProfileListRootKeyName;
  if ( UserProfileListRootKeyName >= 0 )
  {
    if ( v9 )
    {
      ProfileTelemetry::UserSidChangeOnRedirectedProfileList();
      v14 = -2147418113;
      v17 = 2672;
      goto LABEL_21;
    }
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v19 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, &hKey);
    if ( v19 )
    {
      v20 = 2677;
LABEL_28:
      v14 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v20,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
              (const char *)v19,
              lpString2a);
      v21 = hKey;
      goto LABEL_29;
    }
    v19 = RegRenameKey(hKey, v12, lpString1);
    if ( v19 )
    {
      v20 = 2678;
      goto LABEL_28;
    }
    if ( hKey )
      RegCloseKey(hKey);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpSubKey);
    v41 = -1;
    v42 = -1;
    ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(lpString1, (unsigned __int16 **)&lpSubKey, 0);
    v14 = ProfileListKeyNameFromSid;
    if ( ProfileListKeyNameFromSid < 0 )
    {
      v18 = (unsigned int)ProfileListKeyNameFromSid;
      v17 = 2682;
      goto LABEL_22;
    }
    v37 = 0;
    v38 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v38,
      0);
    v24 = CUserProfile::OpenProfileListKey(v23, lpSubKey, &v38, &v37);
    v14 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA7E,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v24,
        lpString2a);
LABEL_39:
      v21 = v38;
LABEL_29:
      if ( v21 )
        RegCloseKey(v21);
      goto LABEL_23;
    }
    Sid = 0;
    UserSid = GetUserSid(TokenHandle, &Sid);
    v14 = UserSid;
    if ( UserSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA82,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)UserSid,
        lpString2a);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
      goto LABEL_39;
    }
    v26 = (const BYTE *)Sid;
    v27 = RtlLengthSid(Sid);
    lpString2c = v26;
    v28 = v38;
    v29 = RegSetValueExW(v38, L"Sid", 0, 3u, lpString2c, v27);
    if ( v29 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0xA83,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)v29,
        lpString2b);
    Library = LoadLibraryExW(L"msi.dll", 0, 0);
    v38 = (HKEY)Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "MsiNotifySidChangeW");
      if ( ProcAddress )
        ((void (__fastcall *)(const unsigned __int16 *, LPCWCH))ProcAddress)(v12, lpString1);
    }
    *a4 = v28;
    if ( v10 )
      *v10 = v37;
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v38);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpSubKey);
LABEL_50:
    v14 = 0;
    goto LABEL_51;
  }
  v17 = 2665;
LABEL_21:
  v18 = v14;
LABEL_22:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v17,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
    (const char *)v18,
    lpString2a);
LABEL_23:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpSubKey);
LABEL_51:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpString1a);
  return v14;
}

```

## disassembly

```asm
0x18002b2a0  push    rbp
0x18002b2a2  push    rbx
0x18002b2a3  push    rsi
0x18002b2a4  push    rdi
0x18002b2a5  push    r12
0x18002b2a7  push    r13
0x18002b2a9  push    r14
0x18002b2ab  push    r15
0x18002b2ad  lea     rbp, [rsp-17h]
0x18002b2b2  sub     rsp, 88h
0x18002b2b9  mov     r12, r9
0x18002b2bc  mov     r15, r8
0x18002b2bf  mov     r13, rdx
0x18002b2c2  mov     rbx, rcx
0x18002b2c5  xor     r14d, r14d
0x18002b2c8  test    rdx, rdx
0x18002b2cb  jz      loc_18002B67F
0x18002b2d1  test    r8, r8
0x18002b2d4  jz      loc_18002B67F
0x18002b2da  test    r9, r9
0x18002b2dd  jz      loc_18002B67F
0x18002b2e3  mov     [r9], r14
0x18002b2e6  mov     rsi, [rbp+4Fh+arg_20]
0x18002b2ea  test    rsi, rsi
0x18002b2ed  jz      short loc_18002B2F2
0x18002b2ef  mov     [rsi], r14d
0x18002b2f2  mov     [rbp+4Fh+lpString1], r14
0x18002b2f6  mov     [rbp+4Fh+var_58], r14
0x18002b2fa  mov     [rbp+4Fh+var_50], r14
0x18002b2fe  lea     rcx, [rbp+4Fh+lpString1]
0x18002b302  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002b307  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b30b  mov     [rbp+4Fh+var_58], rax
0x18002b30f  mov     [rbp+4Fh+var_50], rax
0x18002b313  lea     r8, [rbp+4Fh+lpString1]; unsigned __int16 **
0x18002b317  mov     rcx, r13; TokenHandle
0x18002b31a  call    ?GetOldSidString@@YAJPEAXPEBGPEAPEAG@Z; GetOldSidString(void *,ushort const *,ushort * *)
0x18002b31f  test    eax, eax
0x18002b321  js      loc_18002B671
0x18002b327  mov     rdi, [rbp+4Fh+lpString1]
0x18002b32b  test    rdi, rdi
0x18002b32e  jz      loc_18002B671
0x18002b334  cmp     [rdi], r14w
0x18002b338  jz      loc_18002B671
0x18002b33e  mov     [rsp+0C0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18002b346  mov     [rsp+0C0h+lpString2], r15; int
0x18002b34b  or      r9d, 0FFFFFFFFh; cchCount1
0x18002b34f  mov     r8, rdi; lpString1
0x18002b352  lea     edx, [r9+2]; dwCmpFlags
0x18002b356  lea     ecx, [rdx+7Eh]; Locale
0x18002b359  call    cs:__imp_CompareStringW
0x18002b35f  cmp     eax, 2
0x18002b362  jz      loc_18002B671
0x18002b368  mov     [rbp+4Fh+hKey], r14
0x18002b36c  xor     edx, edx
0x18002b36e  lea     rcx, [rbp+4Fh+hKey]
0x18002b372  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002b377  xor     r9d, r9d; unsigned int *
0x18002b37a  lea     r8, [rbp+4Fh+hKey]; HKEY *
0x18002b37e  mov     rdx, rdi; unsigned __int16 *
0x18002b381  mov     rcx, rbx; this
0x18002b384  call    ?RestoreKeyFromBackup@CUserProfile@@IEAAJPEBGPEAPEAUHKEY__@@PEAK@Z; CUserProfile::RestoreKeyFromBackup(ushort const *,HKEY__ * *,ulong *)
0x18002b389  mov     ebx, eax
0x18002b38b  test    eax, eax
0x18002b38d  jns     short loc_18002B3BF
0x18002b38f  mov     rcx, [rbp+57h]; this
0x18002b393  mov     r9d, eax; char *
0x18002b396  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002b39d  mov     edx, 0A5Fh; void *
0x18002b3a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b3a7  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18002b3ab  test    rcx, rcx
0x18002b3ae  jz      loc_18002B674
0x18002b3b4  call    cs:__imp_RegCloseKey
0x18002b3ba  jmp     loc_18002B674
0x18002b3bf  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18002b3c3  test    rcx, rcx
0x18002b3c6  setnz   bl
0x18002b3c9  test    rcx, rcx
0x18002b3cc  jz      short loc_18002B3D4
0x18002b3ce  call    cs:__imp_RegCloseKey
0x18002b3d4  test    bl, bl
0x18002b3d6  jz      loc_18002B671
0x18002b3dc  mov     [rbp+4Fh+lpSubKey], r14
0x18002b3e0  mov     [rbp+4Fh+var_70], r14
0x18002b3e4  mov     [rbp+4Fh+var_68], r14
0x18002b3e8  mov     dword ptr [rbp+4Fh+hKey], r14d
0x18002b3ec  mov     rcx, rdi; lpString1
0x18002b3ef  call    ?IsServiceSid@@YAHPEBG@Z; IsServiceSid(ushort const *)
0x18002b3f4  lea     rcx, [rbp+4Fh+lpSubKey]
0x18002b3f8  test    eax, eax
0x18002b3fa  jz      short loc_18002B40E
0x18002b3fc  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002b400  lea     rdx, aSoftwareMicros_34; "Software\\Microsoft\\Windows NT\\Curren"...
0x18002b407  call    ?_Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18002b40c  jmp     short loc_18002B430
0x18002b40e  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002b413  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b417  mov     [rbp+4Fh+var_70], rax
0x18002b41b  mov     [rbp+4Fh+var_68], rax
0x18002b41f  lea     rdx, [rbp+4Fh+hKey]; int *
0x18002b423  lea     rcx, [rbp+4Fh+lpSubKey]; unsigned __int16 **
0x18002b427  call    ?GetUserProfileListRootKeyName@@YAJPEAPEAGPEAH@Z; GetUserProfileListRootKeyName(ushort * *,int *)
0x18002b42c  mov     r14d, dword ptr [rbp+4Fh+hKey]
0x18002b430  mov     ebx, eax
0x18002b432  test    eax, eax
0x18002b434  jns     short loc_18002B45C
0x18002b436  mov     edx, 0A69h; void *
0x18002b43b  mov     r9d, ebx; char *
0x18002b43e  mov     rcx, [rbp+57h]; this
0x18002b442  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002b449  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b44e  lea     rcx, [rbp+4Fh+lpSubKey]
0x18002b452  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002b457  jmp     loc_18002B674
0x18002b45c  test    r14d, r14d
0x18002b45f  jz      short loc_18002B472
0x18002b461  call    ?UserSidChangeOnRedirectedProfileList@ProfileTelemetry@@SAXXZ; ProfileTelemetry::UserSidChangeOnRedirectedProfileList(void)
0x18002b466  mov     ebx, 8000FFFFh
0x18002b46b  mov     edx, 0A70h
0x18002b470  jmp     short loc_18002B43B
0x18002b472  xor     r14d, r14d
0x18002b475  mov     [rbp+4Fh+hKey], r14
0x18002b479  xor     edx, edx
0x18002b47b  lea     rcx, [rbp+4Fh+hKey]
0x18002b47f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002b484  lea     rax, [rbp+4Fh+hKey]
0x18002b488  mov     [rsp+0C0h+lpString2], rax; int
0x18002b48d  mov     r9d, 2001Fh; samDesired
0x18002b493  xor     r8d, r8d; ulOptions
0x18002b496  mov     rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x18002b49a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b4a1  call    cs:__imp_RegOpenKeyExW
0x18002b4a7  test    eax, eax
0x18002b4a9  jz      short loc_18002B4D9
0x18002b4ab  mov     edx, 0A75h; void *
0x18002b4b0  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002b4b7  mov     r9d, eax; char *
0x18002b4ba  mov     rcx, [rbp+57h]; this
0x18002b4be  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002b4c3  mov     ebx, eax
0x18002b4c5  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18002b4c9  test    rcx, rcx
0x18002b4cc  jz      short loc_18002B44E
0x18002b4ce  call    cs:__imp_RegCloseKey
0x18002b4d4  jmp     loc_18002B44E
0x18002b4d9  mov     r8, r15; lpNewKeyName
0x18002b4dc  mov     rdx, rdi; lpSubKeyName
0x18002b4df  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18002b4e3  call    cs:__imp_RegRenameKey
0x18002b4e9  test    eax, eax
0x18002b4eb  jz      short loc_18002B4F4
0x18002b4ed  mov     edx, 0A76h
0x18002b4f2  jmp     short loc_18002B4B0
0x18002b4f4  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18002b4f8  test    rcx, rcx
0x18002b4fb  jz      short loc_18002B503
0x18002b4fd  call    cs:__imp_RegCloseKey
0x18002b503  lea     rcx, [rbp+4Fh+lpSubKey]
0x18002b507  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002b50c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b510  mov     [rbp+4Fh+var_70], rax
0x18002b514  mov     [rbp+4Fh+var_68], rax
0x18002b518  xor     r8d, r8d; int *
0x18002b51b  lea     rdx, [rbp+4Fh+lpSubKey]; unsigned __int16 **
0x18002b51f  mov     rcx, r15; lpString1
0x18002b522  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x18002b527  mov     ebx, eax
0x18002b529  test    eax, eax
0x18002b52b  jns     short loc_18002B53A
0x18002b52d  mov     r9d, eax
0x18002b530  mov     edx, 0A7Ah
0x18002b535  jmp     loc_18002B43E
0x18002b53a  mov     [rbp+4Fh+var_90], r14d
0x18002b53e  mov     [rbp+4Fh+var_88], r14
0x18002b542  xor     edx, edx
0x18002b544  lea     rcx, [rbp+4Fh+var_88]
0x18002b548  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002b54d  lea     r9, [rbp+4Fh+var_90]; unsigned int *
0x18002b551  lea     r8, [rbp+4Fh+var_88]; HKEY *
0x18002b555  mov     rdx, [rbp+4Fh+lpSubKey]; unsigned __int16 *
0x18002b559  call    ?OpenProfileListKey@CUserProfile@@IEAAJPEBGPEAPEAUHKEY__@@PEAK@Z; CUserProfile::OpenProfileListKey(ushort const *,HKEY__ * *,ulong *)
0x18002b55e  mov     ebx, eax
0x18002b560  test    eax, eax
0x18002b562  jns     short loc_18002B585
0x18002b564  mov     rcx, [rbp+57h]; this
0x18002b568  mov     r9d, eax; char *
0x18002b56b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002b572  mov     edx, 0A7Eh; void *
0x18002b577  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b57c  mov     rcx, [rbp+4Fh+var_88]
0x18002b580  jmp     loc_18002B4C9
0x18002b585  mov     [rbp+4Fh+Sid], r14
0x18002b589  lea     rdx, [rbp+4Fh+Sid]; void **
0x18002b58d  mov     rcx, r13; TokenHandle
0x18002b590  call    ?GetUserSid@@YAJPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x18002b595  mov     ebx, eax
0x18002b597  test    eax, eax
0x18002b599  jns     short loc_18002B5BE
0x18002b59b  mov     rcx, [rbp+57h]; this
0x18002b59f  mov     r9d, eax; char *
0x18002b5a2  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002b5a9  mov     edx, 0A82h; void *
0x18002b5ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b5b3  lea     rcx, [rbp+4Fh+Sid]
0x18002b5b7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?ResultFromHeapFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b5bc  jmp     short loc_18002B57C
0x18002b5be  mov     rbx, [rbp+4Fh+Sid]
0x18002b5c2  mov     rcx, rbx; Sid
0x18002b5c5  call    cs:__imp_RtlLengthSid
0x18002b5cb  mov     [rsp+0C0h+cchCount2], eax; cbData
0x18002b5cf  mov     [rsp+0C0h+lpString2], rbx; unsigned int
0x18002b5d4  mov     r9d, 3; dwType
0x18002b5da  xor     r8d, r8d; Reserved
0x18002b5dd  lea     rdx, aSid; "Sid"
0x18002b5e4  mov     rbx, [rbp+4Fh+var_88]
0x18002b5e8  mov     rcx, rbx; hKey
0x18002b5eb  call    cs:__imp_RegSetValueExW
0x18002b5f1  test    eax, eax
0x18002b5f3  jz      short loc_18002B60D
0x18002b5f5  mov     rcx, [rbp+57h]; this
0x18002b5f9  mov     r9d, eax; char *
0x18002b5fc  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002b603  mov     edx, 0A83h; void *
0x18002b608  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002b60d  xor     r8d, r8d; dwFlags
0x18002b610  xor     edx, edx; hFile
0x18002b612  lea     rcx, aMsiDll; "msi.dll"
0x18002b619  call    cs:__imp_LoadLibraryExW
0x18002b61f  mov     [rbp+4Fh+var_88], rax
0x18002b623  test    rax, rax
0x18002b626  jz      short loc_18002B648
0x18002b628  lea     rdx, aMsinotifysidch; "MsiNotifySidChangeW"
0x18002b62f  mov     rcx, rax; hModule
0x18002b632  call    cs:__imp_GetProcAddress
0x18002b638  test    rax, rax
0x18002b63b  jz      short loc_18002B648
0x18002b63d  mov     rdx, r15
0x18002b640  mov     rcx, rdi
0x18002b643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b648  mov     [r12], rbx
0x18002b64c  test    rsi, rsi
0x18002b64f  jz      short loc_18002B656
0x18002b651  mov     eax, [rbp+4Fh+var_90]
0x18002b654  mov     [rsi], eax
0x18002b656  lea     rcx, [rbp+4Fh+var_88]
0x18002b65a  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002b65f  lea     rcx, [rbp+4Fh+Sid]
0x18002b663  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?ResultFromHeapFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b668  lea     rcx, [rbp+4Fh+lpSubKey]
0x18002b66c  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002b671  mov     ebx, r14d
0x18002b674  lea     rcx, [rbp+4Fh+lpString1]
0x18002b678  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002b67d  jmp     short loc_18002B69C
0x18002b67f  mov     rcx, [rbp+57h]; this
0x18002b683  mov     ebx, 80070057h
0x18002b688  mov     r9d, ebx; char *
0x18002b68b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002b692  mov     edx, 0A4Bh; void *
0x18002b697  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b69c  mov     eax, ebx
0x18002b69e  add     rsp, 88h
0x18002b6a5  pop     r15
0x18002b6a7  pop     r14
0x18002b6a9  pop     r13
0x18002b6ab  pop     r12
0x18002b6ad  pop     rdi
0x18002b6ae  pop     rsi
0x18002b6af  pop     rbx
0x18002b6b0  pop     rbp
0x18002b6b1  retn
```
