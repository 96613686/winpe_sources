# CUserProfile::GetOldKeyFromGuid(void *,ushort const *,HKEY__ * *,ulong *)

- ea: `0x180037544`
- end: `0x180037973`
- name: `?GetOldKeyFromGuid@CUserProfile@@IEAAJPEAXPEBGPEAPEAUHKEY__@@PEAK@Z`
- size: `1071`
- prototype: `__int64 __usercall@<rax>(CUserProfile *__hidden this@<rcx>, HANDLE TokenHandle@<rdx>, const unsigned __int16 *@<r8>, HKEY *@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180013838`

## callees

- `0x18000d2c0`
- `0x18000e1a0`
- `0x1800127a0`
- `0x180012ac8`
- `0x1800130d0`
- `0x1800133d4`
- `0x180013770`
- `0x180019260`
- `0x180019ab0`
- `0x180024d10`
- `0x180026d30`
- `0x18002d88c`
- `0x180030ad0`
- `0x180031060`
- `0x180037544`
- `0x180043800`
- `0x180048bf4`
- `0x1800516b4`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800378c0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800378c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800378df`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800378df`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800375fd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800375fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003773c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003773c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003788c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003788c`
- `ntdll!RtlLengthSid` at `0x180037860`
- `ntdll!RtlLengthSid` at `0x180037860`
- `api-ms-win-core-registry-private-l1-1-0!RegRenameKey` at `0x18003777e`
- `api-ms-win-core-registry-private-l1-1-0!RegRenameKey` at `0x18003777e`

## string_xrefs

- `0x180037640`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800376dd`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180037751`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180037806`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003783d`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800378a3`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18003794b`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800378b9`: `msi.dll`
- `0x1800378d5`: `MsiNotifySidChangeW`

## pseudocode

```c
__int64 __fastcall CUserProfile::GetOldKeyFromGuid(
        CUserProfile *this,
        HANDLE TokenHandle,
        const unsigned __int16 *a3,
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
  HKEY *p_phkResult; // rcx
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
  HKEY phkResult; // [rsp+38h] [rbp-39h] BYREF
  PSID Sid; // [rsp+40h] [rbp-31h] BYREF
  HMODULE v40; // [rsp+48h] [rbp-29h] BYREF
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-21h] BYREF
  __int64 v42; // [rsp+58h] [rbp-19h]
  __int64 v43; // [rsp+60h] [rbp-11h]
  PCNZWCH lpString1; // [rsp+68h] [rbp-9h] BYREF
  __int64 v45; // [rsp+70h] [rbp-1h]
  __int64 v46; // [rsp+78h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]
  HKEY hKey; // [rsp+D8h] [rbp+67h] BYREF

  v9 = 0;
  if ( !TokenHandle || !a3 || !a4 )
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
  lpString1 = 0;
  v45 = 0;
  v46 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpString1);
  v45 = -1;
  v46 = -1;
  if ( (int)GetOldSidString(TokenHandle, v11, (unsigned __int16 **)&lpString1) < 0 )
    goto LABEL_44;
  v12 = lpString1;
  if ( !lpString1 || !*lpString1 || CompareStringW(0x7Fu, 1u, lpString1, -1, a3, -1) == 2 )
    goto LABEL_44;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v13 = CUserProfile::RestoreKeyFromBackup(this, v12, &hKey, 0);
  v14 = v13;
  if ( v13 >= 0 )
  {
    v15 = hKey != 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    if ( v15 )
    {
      lpSubKey = 0;
      v42 = 0;
      v43 = 0;
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
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
        v42 = -1;
        v43 = -1;
        UserProfileListRootKeyName = GetUserProfileListRootKeyName((unsigned __int16 **)&lpSubKey, (int *)&hKey);
        v9 = (int)hKey;
      }
      v14 = UserProfileListRootKeyName;
      if ( UserProfileListRootKeyName < 0 )
      {
        v17 = 2665;
LABEL_18:
        v18 = v14;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
          (const char *)v18,
          lpString2a);
LABEL_20:
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
        goto LABEL_45;
      }
      if ( v9 )
      {
        ProfileTelemetry::UserSidChangeOnRedirectedProfileList();
        v14 = -2147418113;
        v17 = 2672;
        goto LABEL_18;
      }
      phkResult = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &phkResult,
        0);
      v19 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, &phkResult);
      if ( v19 )
      {
        v20 = 2677;
LABEL_25:
        v14 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)v20,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                (const char *)v19,
                lpString2a);
        p_phkResult = &phkResult;
LABEL_26:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(p_phkResult);
        goto LABEL_20;
      }
      v19 = RegRenameKey(phkResult, v12, a3);
      if ( v19 )
      {
        v20 = 2678;
        goto LABEL_25;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
      v42 = -1;
      v43 = -1;
      ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(a3, (unsigned __int16 **)&lpSubKey, 0);
      v14 = ProfileListKeyNameFromSid;
      if ( ProfileListKeyNameFromSid < 0 )
      {
        v18 = (unsigned int)ProfileListKeyNameFromSid;
        v17 = 2682;
        goto LABEL_19;
      }
      v37 = 0;
      hKey = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKey,
        0);
      v24 = CUserProfile::OpenProfileListKey(v23, lpSubKey, &hKey, &v37);
      v14 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA7E,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
          (const char *)(unsigned int)v24,
          lpString2a);
LABEL_33:
        p_phkResult = &hKey;
        goto LABEL_26;
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
        goto LABEL_33;
      }
      v26 = (const BYTE *)Sid;
      v27 = RtlLengthSid(Sid);
      lpString2c = v26;
      v28 = hKey;
      v29 = RegSetValueExW(hKey, L"Sid", 0, 3u, lpString2c, v27);
      if ( v29 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0xA83,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
          (const char *)v29,
          lpString2b);
      Library = LoadLibraryExW(L"msi.dll", 0, 0);
      v40 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "MsiNotifySidChangeW");
        if ( ProcAddress )
          ((void (__fastcall *)(const unsigned __int16 *, const unsigned __int16 *))ProcAddress)(v12, a3);
      }
      hKey = 0;
      *a4 = v28;
      if ( v10 )
        *v10 = v37;
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v40);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
    }
LABEL_44:
    v14 = 0;
    goto LABEL_45;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA5F,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
    (const char *)(unsigned int)v13,
    lpString2a);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
LABEL_45:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpString1);
  return v14;
}

```

## disassembly

```asm
0x180037544  push    rbp
0x180037546  push    rbx
0x180037547  push    rsi
0x180037548  push    rdi
0x180037549  push    r12
0x18003754b  push    r13
0x18003754d  push    r14
0x18003754f  push    r15
0x180037551  lea     rbp, [rsp-17h]
0x180037556  sub     rsp, 88h
0x18003755d  mov     r12, r9
0x180037560  mov     r15, r8
0x180037563  mov     r13, rdx
0x180037566  mov     rbx, rcx
0x180037569  xor     r14d, r14d
0x18003756c  test    rdx, rdx
0x18003756f  jz      loc_18003793F
0x180037575  test    r8, r8
0x180037578  jz      loc_18003793F
0x18003757e  test    r9, r9
0x180037581  jz      loc_18003793F
0x180037587  mov     [r9], r14
0x18003758a  mov     rsi, [rbp+4Fh+arg_20]
0x18003758e  test    rsi, rsi
0x180037591  jz      short loc_180037596
0x180037593  mov     [rsi], r14d
0x180037596  mov     [rbp+4Fh+lpString1], r14
0x18003759a  mov     [rbp+4Fh+var_50], r14
0x18003759e  mov     [rbp+4Fh+var_48], r14
0x1800375a2  lea     rcx, [rbp+4Fh+lpString1]
0x1800375a6  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800375ab  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800375af  mov     [rbp+4Fh+var_50], rax
0x1800375b3  mov     [rbp+4Fh+var_48], rax
0x1800375b7  lea     r8, [rbp+4Fh+lpString1]; unsigned __int16 **
0x1800375bb  mov     rcx, r13; void *
0x1800375be  call    ?GetOldSidString@@YAJPEAXPEBGPEAPEAG@Z; GetOldSidString(void *,ushort const *,ushort * *)
0x1800375c3  test    eax, eax
0x1800375c5  js      loc_180037931
0x1800375cb  mov     rdi, [rbp+4Fh+lpString1]
0x1800375cf  test    rdi, rdi
0x1800375d2  jz      loc_180037931
0x1800375d8  cmp     [rdi], r14w
0x1800375dc  jz      loc_180037931
0x1800375e2  mov     [rsp+0C0h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800375ea  mov     [rsp+0C0h+lpString2], r15; int
0x1800375ef  or      r9d, 0FFFFFFFFh; cchCount1
0x1800375f3  mov     r8, rdi; lpString1
0x1800375f6  lea     edx, [r9+2]; dwCmpFlags
0x1800375fa  lea     ecx, [rdx+7Eh]; Locale
0x1800375fd  call    cs:__imp_CompareStringW
0x180037604  nop     dword ptr [rax+rax+00h]
0x180037609  cmp     eax, 2
0x18003760c  jz      loc_180037931
0x180037612  mov     [rbp+4Fh+hKey], r14
0x180037616  xor     edx, edx
0x180037618  lea     rcx, [rbp+4Fh+hKey]
0x18003761c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180037621  xor     r9d, r9d; unsigned int *
0x180037624  lea     r8, [rbp+4Fh+hKey]; HKEY *
0x180037628  mov     rdx, rdi; unsigned __int16 *
0x18003762b  mov     rcx, rbx; this
0x18003762e  call    ?RestoreKeyFromBackup@CUserProfile@@IEAAJPEBGPEAPEAUHKEY__@@PEAK@Z; CUserProfile::RestoreKeyFromBackup(ushort const *,HKEY__ * *,ulong *)
0x180037633  mov     ebx, eax
0x180037635  test    eax, eax
0x180037637  jns     short loc_18003765F
0x180037639  mov     rcx, [rbp+57h]; this
0x18003763d  mov     r9d, eax; char *
0x180037640  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180037647  mov     edx, 0A5Fh; void *
0x18003764c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037651  lea     rcx, [rbp+4Fh+hKey]
0x180037655  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003765a  jmp     loc_180037934
0x18003765f  cmp     [rbp+4Fh+hKey], r14
0x180037663  setnz   bl
0x180037666  lea     rcx, [rbp+4Fh+hKey]
0x18003766a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003766f  test    bl, bl
0x180037671  jz      loc_180037931
0x180037677  mov     [rbp+4Fh+lpSubKey], r14
0x18003767b  mov     [rbp+4Fh+var_68], r14
0x18003767f  mov     [rbp+4Fh+var_60], r14
0x180037683  mov     dword ptr [rbp+4Fh+hKey], r14d
0x180037687  mov     rcx, rdi; lpString1
0x18003768a  call    ?IsServiceSid@@YAHPEBG@Z; IsServiceSid(ushort const *)
0x18003768f  lea     rcx, [rbp+4Fh+lpSubKey]
0x180037693  test    eax, eax
0x180037695  jz      short loc_1800376A9
0x180037697  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003769b  lea     rdx, aSoftwareMicros_34; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800376a2  call    ?_Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800376a7  jmp     short loc_1800376CB
0x1800376a9  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800376ae  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800376b2  mov     [rbp+4Fh+var_68], rax
0x1800376b6  mov     [rbp+4Fh+var_60], rax
0x1800376ba  lea     rdx, [rbp+4Fh+hKey]; int *
0x1800376be  lea     rcx, [rbp+4Fh+lpSubKey]; unsigned __int16 **
0x1800376c2  call    ?GetUserProfileListRootKeyName@@YAJPEAPEAGPEAH@Z; GetUserProfileListRootKeyName(ushort * *,int *)
0x1800376c7  mov     r14d, dword ptr [rbp+4Fh+hKey]
0x1800376cb  mov     ebx, eax
0x1800376cd  test    eax, eax
0x1800376cf  jns     short loc_1800376F7
0x1800376d1  mov     edx, 0A69h; void *
0x1800376d6  mov     r9d, ebx; char *
0x1800376d9  mov     rcx, [rbp+57h]; this
0x1800376dd  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800376e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800376e9  lea     rcx, [rbp+4Fh+lpSubKey]
0x1800376ed  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800376f2  jmp     loc_180037934
0x1800376f7  test    r14d, r14d
0x1800376fa  jz      short loc_18003770D
0x1800376fc  call    ?UserSidChangeOnRedirectedProfileList@ProfileTelemetry@@SAXXZ; ProfileTelemetry::UserSidChangeOnRedirectedProfileList(void)
0x180037701  mov     ebx, 8000FFFFh
0x180037706  mov     edx, 0A70h
0x18003770b  jmp     short loc_1800376D6
0x18003770d  xor     r14d, r14d
0x180037710  mov     [rbp+4Fh+phkResult], r14
0x180037714  xor     edx, edx
0x180037716  lea     rcx, [rbp+4Fh+phkResult]
0x18003771a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003771f  lea     rax, [rbp+4Fh+phkResult]
0x180037723  mov     [rsp+0C0h+lpString2], rax; int
0x180037728  mov     r9d, 2001Fh; samDesired
0x18003772e  xor     r8d, r8d; ulOptions
0x180037731  mov     rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x180037735  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003773c  call    cs:__imp_RegOpenKeyExW
0x180037743  nop     dword ptr [rax+rax+00h]
0x180037748  test    eax, eax
0x18003774a  jz      short loc_180037774
0x18003774c  mov     edx, 0A75h; void *
0x180037751  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180037758  mov     r9d, eax; char *
0x18003775b  mov     rcx, [rbp+57h]; this
0x18003775f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180037764  mov     ebx, eax
0x180037766  lea     rcx, [rbp+4Fh+phkResult]
0x18003776a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003776f  jmp     loc_1800376E9
0x180037774  mov     r8, r15; lpNewKeyName
0x180037777  mov     rdx, rdi; lpSubKeyName
0x18003777a  mov     rcx, [rbp+4Fh+phkResult]; hKey
0x18003777e  call    cs:__imp_RegRenameKey
0x180037785  nop     dword ptr [rax+rax+00h]
0x18003778a  test    eax, eax
0x18003778c  jz      short loc_180037795
0x18003778e  mov     edx, 0A76h
0x180037793  jmp     short loc_180037751
0x180037795  lea     rcx, [rbp+4Fh+phkResult]
0x180037799  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003779e  lea     rcx, [rbp+4Fh+lpSubKey]
0x1800377a2  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800377a7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800377ab  mov     [rbp+4Fh+var_68], rax
0x1800377af  mov     [rbp+4Fh+var_60], rax
0x1800377b3  xor     r8d, r8d; int *
0x1800377b6  lea     rdx, [rbp+4Fh+lpSubKey]; unsigned __int16 **
0x1800377ba  mov     rcx, r15; lpString1
0x1800377bd  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x1800377c2  mov     ebx, eax
0x1800377c4  test    eax, eax
0x1800377c6  jns     short loc_1800377D5
0x1800377c8  mov     r9d, eax
0x1800377cb  mov     edx, 0A7Ah
0x1800377d0  jmp     loc_1800376D9
0x1800377d5  mov     [rbp+4Fh+var_90], r14d
0x1800377d9  mov     [rbp+4Fh+hKey], r14
0x1800377dd  xor     edx, edx
0x1800377df  lea     rcx, [rbp+4Fh+hKey]
0x1800377e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800377e8  lea     r9, [rbp+4Fh+var_90]; unsigned int *
0x1800377ec  lea     r8, [rbp+4Fh+hKey]; HKEY *
0x1800377f0  mov     rdx, [rbp+4Fh+lpSubKey]; unsigned __int16 *
0x1800377f4  call    ?OpenProfileListKey@CUserProfile@@IEAAJPEBGPEAPEAUHKEY__@@PEAK@Z; CUserProfile::OpenProfileListKey(ushort const *,HKEY__ * *,ulong *)
0x1800377f9  mov     ebx, eax
0x1800377fb  test    eax, eax
0x1800377fd  jns     short loc_180037820
0x1800377ff  mov     rcx, [rbp+57h]; this
0x180037803  mov     r9d, eax; char *
0x180037806  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003780d  mov     edx, 0A7Eh; void *
0x180037812  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037817  lea     rcx, [rbp+4Fh+hKey]
0x18003781b  jmp     loc_18003776A
0x180037820  mov     [rbp+4Fh+Sid], r14
0x180037824  lea     rdx, [rbp+4Fh+Sid]; void **
0x180037828  mov     rcx, r13; TokenHandle
0x18003782b  call    ?GetUserSid@@YAJPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x180037830  mov     ebx, eax
0x180037832  test    eax, eax
0x180037834  jns     short loc_180037859
0x180037836  mov     rcx, [rbp+57h]; this
0x18003783a  mov     r9d, eax; char *
0x18003783d  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180037844  mov     edx, 0A82h; void *
0x180037849  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003784e  lea     rcx, [rbp+4Fh+Sid]
0x180037852  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?ResultFromHeapFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180037857  jmp     short loc_180037817
0x180037859  mov     rbx, [rbp+4Fh+Sid]
0x18003785d  mov     rcx, rbx; Sid
0x180037860  call    cs:__imp_RtlLengthSid
0x180037867  nop     dword ptr [rax+rax+00h]
0x18003786c  mov     [rsp+0C0h+cchCount2], eax; cbData
0x180037870  mov     [rsp+0C0h+lpString2], rbx; unsigned int
0x180037875  mov     r9d, 3; dwType
0x18003787b  xor     r8d, r8d; Reserved
0x18003787e  lea     rdx, aSid; "Sid"
0x180037885  mov     rbx, [rbp+4Fh+hKey]
0x180037889  mov     rcx, rbx; hKey
0x18003788c  call    cs:__imp_RegSetValueExW
0x180037893  nop     dword ptr [rax+rax+00h]
0x180037898  test    eax, eax
0x18003789a  jz      short loc_1800378B4
0x18003789c  mov     rcx, [rbp+57h]; this
0x1800378a0  mov     r9d, eax; char *
0x1800378a3  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800378aa  mov     edx, 0A83h; void *
0x1800378af  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800378b4  xor     r8d, r8d; dwFlags
0x1800378b7  xor     edx, edx; hFile
0x1800378b9  lea     rcx, aMsiDll; "msi.dll"
0x1800378c0  call    cs:__imp_LoadLibraryExW
0x1800378c7  nop     dword ptr [rax+rax+00h]
0x1800378cc  mov     [rbp+4Fh+var_78], rax
0x1800378d0  test    rax, rax
0x1800378d3  jz      short loc_1800378FB
0x1800378d5  lea     rdx, aMsinotifysidch; "MsiNotifySidChangeW"
0x1800378dc  mov     rcx, rax; hModule
0x1800378df  call    cs:__imp_GetProcAddress
0x1800378e6  nop     dword ptr [rax+rax+00h]
0x1800378eb  test    rax, rax
0x1800378ee  jz      short loc_1800378FB
0x1800378f0  mov     rdx, r15
0x1800378f3  mov     rcx, rdi
0x1800378f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800378fb  mov     [rbp+4Fh+hKey], r14
0x1800378ff  mov     [r12], rbx
0x180037903  test    rsi, rsi
0x180037906  jz      short loc_18003790D
0x180037908  mov     eax, [rbp+4Fh+var_90]
0x18003790b  mov     [rsi], eax
0x18003790d  lea     rcx, [rbp+4Fh+var_78]
0x180037911  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180037916  lea     rcx, [rbp+4Fh+Sid]
0x18003791a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?ResultFromHeapFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003791f  lea     rcx, [rbp+4Fh+hKey]
0x180037923  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180037928  lea     rcx, [rbp+4Fh+lpSubKey]
0x18003792c  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180037931  mov     ebx, r14d
0x180037934  lea     rcx, [rbp+4Fh+lpString1]
0x180037938  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18003793d  jmp     short loc_18003795C
0x18003793f  mov     rcx, [rbp+57h]; this
0x180037943  mov     ebx, 80070057h
0x180037948  mov     r9d, ebx; char *
0x18003794b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180037952  mov     edx, 0A4Bh; void *
0x180037957  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003795c  mov     eax, ebx
0x18003795e  add     rsp, 88h
0x180037965  pop     r15
0x180037967  pop     r14
0x180037969  pop     r13
0x18003796b  pop     r12
0x18003796d  pop     rdi
0x18003796e  pop     rsi
0x18003796f  pop     rbx
0x180037970  pop     rbp
0x180037971  retn
```
