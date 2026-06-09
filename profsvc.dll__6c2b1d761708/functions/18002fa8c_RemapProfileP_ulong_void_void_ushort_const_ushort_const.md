# RemapProfileP(ulong,void *,void *,ushort const *,ushort const *)

- ea: `0x18002fa8c`
- end: `0x180030001`
- name: `?RemapProfileP@@YAJKPEAX0PEBG1@Z`
- size: `1397`
- prototype: `__int64 __fastcall(char, void *, void *, const unsigned __int16 *, const unsigned __int16 *lpNewKeyName)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004e5a0`

## callees

- `0x18000e1a0`
- `0x1800130d0`
- `0x180013770`
- `0x1800146f0`
- `0x180014e90`
- `0x180019ab0`
- `0x180026390`
- `0x18002f844`
- `0x18002fa8c`
- `0x180030008`
- `0x180030ad0`
- `0x180031060`
- `0x1800314a4`
- `0x180035860`
- `0x180040bcc`
- `0x180043800`
- `0x180043c0c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fba9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fc06`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fc91`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fdae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fba9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fc06`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fc91`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fdae`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002fd16`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002fdf4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002fd16`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002fdf4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002fe51`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002fe51`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18002ff34`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18002ff34`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002fe28`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002fe28`
- `api-ms-win-core-registry-private-l1-1-0!RegRenameKey` at `0x18002fd4a`
- `api-ms-win-core-registry-private-l1-1-0!RegRenameKey` at `0x18002fd4a`

## string_xrefs

- `0x18002fe6e`: `ProfileImagePath`
- `0x18002fac6`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002fb31`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002fb65`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002fbbe`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002fc2f`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002fc56`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002fcaf`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002fcf0`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002fdc3`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002fe0f`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002fe8d`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002fee3`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002ff17`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002ff4b`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002ff9c`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002ffbd`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18002fc1b`: `Old user profile is not found in registry.`
- `0x18002fcdc`: `New user profile already exists in registry. Caller specified no overwrite, quitting.`

## pseudocode

```c
__int64 __fastcall RemapProfileP(
        char a1,
        void *a2,
        void *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *lpNewKeyName)
{
  __int64 v8; // rdx
  unsigned int v9; // ebx
  int UserProfileListRootKeyName; // eax
  unsigned int v11; // eax
  __int64 v12; // rdx
  unsigned int v13; // eax
  unsigned int v14; // eax
  __int64 v15; // rdx
  unsigned int v16; // eax
  __int64 v17; // rdx
  unsigned int v18; // eax
  DWORD LengthSid; // eax
  __int64 v20; // r9
  int Dword; // eax
  __int64 v22; // rdx
  int v23; // eax
  unsigned __int16 *v24; // rsi
  int v25; // eax
  unsigned int v26; // eax
  int v27; // eax
  int v28; // ebx
  int phkResult; // [rsp+20h] [rbp-81h]
  unsigned int phkResulta; // [rsp+20h] [rbp-81h]
  unsigned int phkResultb; // [rsp+20h] [rbp-81h]
  unsigned int phkResultc; // [rsp+20h] [rbp-81h]
  unsigned int phkResultd; // [rsp+20h] [rbp-81h]
  const char *cbData; // [rsp+28h] [rbp-79h]
  HKEY hKey; // [rsp+30h] [rbp-71h] BYREF
  HKEY v37; // [rsp+38h] [rbp-69h] BYREF
  HKEY v38; // [rsp+40h] [rbp-61h] BYREF
  HKEY v39; // [rsp+48h] [rbp-59h] BYREF
  unsigned __int16 *v40[3]; // [rsp+50h] [rbp-51h] BYREF
  LPCWSTR lpSubKey; // [rsp+68h] [rbp-39h] BYREF
  __int64 v42; // [rsp+70h] [rbp-31h]
  __int64 v43; // [rsp+78h] [rbp-29h]
  _QWORD v44[3]; // [rsp+80h] [rbp-21h] BYREF
  unsigned int ProfileTypeFromState; // [rsp+98h] [rbp-9h]
  int v46; // [rsp+9Ch] [rbp-5h]
  HKEY *p_hKey; // [rsp+A0h] [rbp-1h]
  const unsigned __int16 **p_lpNewKeyName; // [rsp+A8h] [rbp+7h]
  char v49; // [rsp+B0h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]
  void *v51; // [rsp+108h] [rbp+67h] BYREF

  v51 = a2;
  if ( !(unsigned int)IsProfileInUse(a4) )
  {
    if ( (unsigned int)IsProfileInUse(lpNewKeyName) )
    {
      v8 = 253;
      goto LABEL_3;
    }
    LODWORD(v51) = 0;
    lpSubKey = 0;
    v42 = 0;
    v43 = 0;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
    v42 = -1;
    v43 = -1;
    UserProfileListRootKeyName = GetUserProfileListRootKeyName((unsigned __int16 **)&lpSubKey, (int *)&v51);
    v9 = UserProfileListRootKeyName;
    if ( UserProfileListRootKeyName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x102,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
        (const char *)(unsigned int)UserProfileListRootKeyName,
        phkResult);
LABEL_55:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
      return v9;
    }
    if ( (_DWORD)v51 )
    {
      v9 = -2147418113;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x103,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
        (const char *)0x8000FFFFLL,
        (int)"RemapProfile is not supported on state separated editions.",
        cbData);
      goto LABEL_55;
    }
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, &hKey);
    if ( v11 )
    {
      v12 = 262;
LABEL_12:
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v12,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
             (const char *)v11,
             phkResulta);
LABEL_13:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_55;
    }
    v38 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v38,
      0);
    v13 = RegOpenKeyExW(hKey, a4, 0, 0x2001Fu, &v38);
    if ( v13 == 2 )
    {
      v9 = -2147023579;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x10C,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
        (const char *)0x80070525LL,
        (int)"Old user profile is not found in registry.",
        cbData);
LABEL_16:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v38);
      goto LABEL_13;
    }
    if ( v13 )
    {
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x10D,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
             (const char *)v13,
             phkResultb);
      goto LABEL_16;
    }
    v39 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v39,
      0);
    v14 = RegOpenKeyExW(hKey, lpNewKeyName, 0, 0x2001Fu, &v39);
    if ( v14 != 2 )
    {
      if ( v14 )
      {
        v15 = 277;
LABEL_22:
        v9 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v15,
               (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
               (const char *)v14,
               phkResulta);
LABEL_23:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v39);
        goto LABEL_16;
      }
      if ( (a1 & 1) != 0 )
      {
        v9 = -2147023580;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x11A,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
          (const char *)0x80070524LL,
          (int)"New user profile already exists in registry. Caller specified no overwrite, quitting.",
          cbData);
        goto LABEL_23;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v39,
        0);
      v14 = RegDeleteTreeW(hKey, lpNewKeyName);
      if ( v14 )
      {
        v15 = 286;
        goto LABEL_22;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v39);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v38);
    v11 = RegRenameKey(hKey, a4, lpNewKeyName);
    if ( v11 )
    {
      v12 = 292;
      goto LABEL_12;
    }
    p_hKey = &hKey;
    p_lpNewKeyName = &lpNewKeyName;
    v49 = 1;
    memset(v40, 0, sizeof(v40));
    LODWORD(v51) = 0;
    v37 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v37,
      0);
    v16 = RegOpenKeyExW(hKey, lpNewKeyName, 0, 0x2001Fu, &v37);
    if ( v16 )
    {
      v17 = 304;
    }
    else
    {
      LengthSid = GetLengthSid(a3);
      v16 = RegSetValueExW(v37, L"SID", 0, 3u, (const BYTE *)a3, LengthSid);
      if ( !v16 )
      {
        LOBYTE(v20) = 1;
        Dword = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_InitializeFromRegistry(
                  v40,
                  v37,
                  L"ProfileImagePath",
                  v20);
        v9 = Dword;
        if ( Dword >= 0 )
        {
          Dword = RegQueryDword(v37, L"State", (unsigned int *)&v51);
          v9 = Dword;
          if ( Dword >= 0 )
          {
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v37);
            v23 = DeleteProfileGuidEntry(lpNewKeyName);
            if ( v23 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x138,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
                (const char *)(unsigned int)v23,
                phkResultc);
            v24 = v40[0];
            v25 = SetProfileSecurity(lpNewKeyName, a4, a3, v40[0]);
            v9 = v25;
            if ( v25 >= 0 )
            {
              v26 = RegFlushKey(HKEY_LOCAL_MACHINE);
              if ( v26 )
                wil::details::in1diag3::_Log_Win32(
                  retaddr,
                  (void *)0x13D,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
                  (const char *)v26,
                  phkResultc);
              v46 = 0;
              v44[0] = lpNewKeyName;
              v44[2] = a4;
              v44[1] = v24;
              ProfileTypeFromState = GetProfileTypeFromState((unsigned int)v51);
              v27 = SendNotification(8, v44, 0xFFFFFFFFLL);
              v28 = v27;
              if ( v27 >= 0 )
                v28 = 0;
              else
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xD5,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
                  (const char *)(unsigned int)v27,
                  phkResultc);
              if ( v28 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x140,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
                  (const char *)(unsigned int)v28,
                  phkResultc);
              Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v40);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
              v9 = 0;
              goto LABEL_55;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x13B,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
              (const char *)(unsigned int)v25,
              phkResultc);
            goto LABEL_34;
          }
          v22 = 307;
        }
        else
        {
          v22 = 306;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
          (const char *)(unsigned int)Dword,
          phkResultc);
LABEL_33:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v37);
LABEL_34:
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v40);
        v18 = RegDeleteTreeW(hKey, lpNewKeyName);
        if ( v18 )
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x128,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
            (const char *)v18,
            phkResultd);
        goto LABEL_13;
      }
      v17 = 305;
    }
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v17,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
           (const char *)v16,
           phkResultc);
    goto LABEL_33;
  }
  v8 = 252;
LABEL_3:
  v9 = -2147024864;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
    (const char *)0x80070020LL,
    phkResult);
  return v9;
}

```

## disassembly

```asm
0x18002fa8c  mov     [rsp-8+arg_8], rdx
0x18002fa91  push    rbp
0x18002fa92  push    rbx
0x18002fa93  push    rsi
0x18002fa94  push    rdi
0x18002fa95  push    r14
0x18002fa97  push    r15
0x18002fa99  lea     rbp, [rsp-27h]
0x18002fa9e  sub     rsp, 0C8h
0x18002faa5  mov     rdi, r9
0x18002faa8  mov     r14, r8
0x18002faab  mov     esi, ecx
0x18002faad  mov     rcx, r9; unsigned __int16 *
0x18002fab0  call    ?IsProfileInUse@@YAHPEBG@Z; IsProfileInUse(ushort const *)
0x18002fab5  xor     r15d, r15d
0x18002fab8  test    eax, eax
0x18002faba  jz      short loc_18002FADE
0x18002fabc  mov     edx, 0FCh; void *
0x18002fac1  mov     ebx, 80070020h
0x18002fac6  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002facd  mov     r9d, ebx; char *
0x18002fad0  mov     rcx, [rbp+57h]; this
0x18002fad4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fad9  jmp     loc_18002FFEE
0x18002fade  mov     rcx, [rbp+4Fh+lpNewKeyName]; unsigned __int16 *
0x18002fae2  call    ?IsProfileInUse@@YAHPEBG@Z; IsProfileInUse(ushort const *)
0x18002fae7  test    eax, eax
0x18002fae9  jz      short loc_18002FAF2
0x18002faeb  mov     edx, 0FDh
0x18002faf0  jmp     short loc_18002FAC1
0x18002faf2  mov     dword ptr [rbp+4Fh+arg_8], r15d
0x18002faf6  mov     [rbp+4Fh+lpSubKey], r15
0x18002fafa  mov     [rbp+4Fh+var_80], r15
0x18002fafe  mov     [rbp+4Fh+var_78], r15
0x18002fb02  lea     rcx, [rbp+4Fh+lpSubKey]
0x18002fb06  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002fb0b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002fb0f  mov     [rbp+4Fh+var_80], rax
0x18002fb13  mov     [rbp+4Fh+var_78], rax
0x18002fb17  lea     rdx, [rbp+4Fh+arg_8]; int *
0x18002fb1b  lea     rcx, [rbp+4Fh+lpSubKey]; unsigned __int16 **
0x18002fb1f  call    ?GetUserProfileListRootKeyName@@YAJPEAPEAGPEAH@Z; GetUserProfileListRootKeyName(ushort * *,int *)
0x18002fb24  mov     ebx, eax
0x18002fb26  test    eax, eax
0x18002fb28  jns     short loc_18002FB47
0x18002fb2a  mov     rcx, [rbp+57h]; this
0x18002fb2e  mov     r9d, eax; char *
0x18002fb31  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002fb38  mov     edx, 102h; void *
0x18002fb3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fb42  jmp     loc_18002FFE5
0x18002fb47  cmp     dword ptr [rbp+4Fh+arg_8], r15d
0x18002fb4b  jz      short loc_18002FB7B
0x18002fb4d  mov     rcx, [rbp+57h]; this
0x18002fb51  lea     rax, aRemapprofileIs; "RemapProfile is not supported on state "...
0x18002fb58  mov     [rsp+0F0h+phkResult], rax; int
0x18002fb5d  mov     ebx, 8000FFFFh
0x18002fb62  mov     r9d, ebx; char *
0x18002fb65  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002fb6c  mov     edx, 103h; void *
0x18002fb71  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002fb76  jmp     loc_18002FFE5
0x18002fb7b  mov     [rbp+4Fh+hKey], r15
0x18002fb7f  xor     edx, edx
0x18002fb81  lea     rcx, [rbp+4Fh+hKey]
0x18002fb85  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002fb8a  lea     rax, [rbp+4Fh+hKey]
0x18002fb8e  mov     [rsp+0F0h+phkResult], rax; unsigned int
0x18002fb93  mov     ebx, 2001Fh
0x18002fb98  mov     r9d, ebx; samDesired
0x18002fb9b  xor     r8d, r8d; ulOptions
0x18002fb9e  mov     rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x18002fba2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002fba9  call    cs:__imp_RegOpenKeyExW
0x18002fbb0  nop     dword ptr [rax+rax+00h]
0x18002fbb5  test    eax, eax
0x18002fbb7  jz      short loc_18002FBE1
0x18002fbb9  mov     edx, 106h; void *
0x18002fbbe  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002fbc5  mov     r9d, eax; char *
0x18002fbc8  mov     rcx, [rbp+57h]; this
0x18002fbcc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002fbd1  mov     ebx, eax
0x18002fbd3  lea     rcx, [rbp+4Fh+hKey]
0x18002fbd7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002fbdc  jmp     loc_18002FFE5
0x18002fbe1  mov     [rbp+4Fh+var_B0], r15
0x18002fbe5  xor     edx, edx
0x18002fbe7  lea     rcx, [rbp+4Fh+var_B0]
0x18002fbeb  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002fbf0  lea     rax, [rbp+4Fh+var_B0]
0x18002fbf4  mov     [rsp+0F0h+phkResult], rax; unsigned int
0x18002fbf9  mov     r9d, ebx; samDesired
0x18002fbfc  xor     r8d, r8d; ulOptions
0x18002fbff  mov     rdx, rdi; lpSubKey
0x18002fc02  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18002fc06  call    cs:__imp_RegOpenKeyExW
0x18002fc0d  nop     dword ptr [rax+rax+00h]
0x18002fc12  cmp     eax, 2
0x18002fc15  jnz     short loc_18002FC4B
0x18002fc17  mov     rcx, [rbp+57h]; this
0x18002fc1b  lea     rax, aOldUserProfile; "Old user profile is not found in regist"...
0x18002fc22  mov     [rsp+0F0h+phkResult], rax; int
0x18002fc27  mov     ebx, 80070525h
0x18002fc2c  mov     r9d, ebx; char *
0x18002fc2f  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002fc36  mov     edx, 10Ch; void *
0x18002fc3b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002fc40  lea     rcx, [rbp+4Fh+var_B0]
0x18002fc44  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002fc49  jmp     short loc_18002FBD3
0x18002fc4b  test    eax, eax
0x18002fc4d  jz      short loc_18002FC6B
0x18002fc4f  mov     rcx, [rbp+57h]; this
0x18002fc53  mov     r9d, eax; char *
0x18002fc56  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002fc5d  mov     edx, 10Dh; void *
0x18002fc62  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002fc67  mov     ebx, eax
0x18002fc69  jmp     short loc_18002FC40
0x18002fc6b  mov     [rbp+4Fh+var_A8], r15
0x18002fc6f  xor     edx, edx
0x18002fc71  lea     rcx, [rbp+4Fh+var_A8]
0x18002fc75  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002fc7a  lea     rax, [rbp+4Fh+var_A8]
0x18002fc7e  mov     [rsp+0F0h+phkResult], rax; unsigned int
0x18002fc83  mov     r9d, ebx; samDesired
0x18002fc86  xor     r8d, r8d; ulOptions
0x18002fc89  mov     rdx, [rbp+4Fh+lpNewKeyName]; lpSubKey
0x18002fc8d  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18002fc91  call    cs:__imp_RegOpenKeyExW
0x18002fc98  nop     dword ptr [rax+rax+00h]
0x18002fc9d  cmp     eax, 2
0x18002fca0  jz      loc_18002FD2D
0x18002fca6  test    eax, eax
0x18002fca8  jz      short loc_18002FCD2
0x18002fcaa  mov     edx, 115h; void *
0x18002fcaf  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002fcb6  mov     r9d, eax; char *
0x18002fcb9  mov     rcx, [rbp+57h]; this
0x18002fcbd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002fcc2  mov     ebx, eax
0x18002fcc4  lea     rcx, [rbp+4Fh+var_A8]
0x18002fcc8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002fccd  jmp     loc_18002FC40
0x18002fcd2  test    sil, 1
0x18002fcd6  jz      short loc_18002FD03
0x18002fcd8  mov     rcx, [rbp+57h]; this
0x18002fcdc  lea     rax, aNewUserProfile; "New user profile already exists in regi"...
0x18002fce3  mov     [rsp+0F0h+phkResult], rax; int
0x18002fce8  mov     ebx, 80070524h
0x18002fced  mov     r9d, ebx; char *
0x18002fcf0  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002fcf7  mov     edx, 11Ah; void *
0x18002fcfc  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002fd01  jmp     short loc_18002FCC4
0x18002fd03  xor     edx, edx
0x18002fd05  lea     rcx, [rbp+4Fh+var_A8]
0x18002fd09  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002fd0e  mov     rdx, [rbp+4Fh+lpNewKeyName]; lpSubKey
0x18002fd12  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18002fd16  call    cs:__imp_RegDeleteTreeW
0x18002fd1d  nop     dword ptr [rax+rax+00h]
0x18002fd22  test    eax, eax
0x18002fd24  jz      short loc_18002FD2D
0x18002fd26  mov     edx, 11Eh
0x18002fd2b  jmp     short loc_18002FCAF
0x18002fd2d  lea     rcx, [rbp+4Fh+var_A8]
0x18002fd31  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002fd36  lea     rcx, [rbp+4Fh+var_B0]
0x18002fd3a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002fd3f  mov     r8, [rbp+4Fh+lpNewKeyName]; lpNewKeyName
0x18002fd43  mov     rdx, rdi; lpSubKeyName
0x18002fd46  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18002fd4a  call    cs:__imp_RegRenameKey
0x18002fd51  nop     dword ptr [rax+rax+00h]
0x18002fd56  test    eax, eax
0x18002fd58  jz      short loc_18002FD64
0x18002fd5a  mov     edx, 124h
0x18002fd5f  jmp     loc_18002FBBE
0x18002fd64  lea     rax, [rbp+4Fh+hKey]
0x18002fd68  mov     [rbp+4Fh+var_50], rax
0x18002fd6c  lea     rax, [rbp+4Fh+lpNewKeyName]
0x18002fd70  mov     [rbp+4Fh+var_48], rax
0x18002fd74  mov     [rbp+4Fh+var_40], 1
0x18002fd78  mov     [rbp+4Fh+var_A0], r15
0x18002fd7c  mov     [rbp+4Fh+var_98], r15
0x18002fd80  mov     [rbp+4Fh+var_90], r15
0x18002fd84  mov     dword ptr [rbp+4Fh+arg_8], r15d
0x18002fd88  mov     [rbp+4Fh+var_B8], r15
0x18002fd8c  xor     edx, edx
0x18002fd8e  lea     rcx, [rbp+4Fh+var_B8]
0x18002fd92  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002fd97  lea     rax, [rbp+4Fh+var_B8]
0x18002fd9b  mov     [rsp+0F0h+phkResult], rax; unsigned int
0x18002fda0  mov     r9d, ebx; samDesired
0x18002fda3  xor     r8d, r8d; ulOptions
0x18002fda6  mov     rdx, [rbp+4Fh+lpNewKeyName]; lpSubKey
0x18002fdaa  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18002fdae  call    cs:__imp_RegOpenKeyExW
0x18002fdb5  nop     dword ptr [rax+rax+00h]
0x18002fdba  test    eax, eax
0x18002fdbc  jz      short loc_18002FE25
0x18002fdbe  mov     edx, 130h; void *
0x18002fdc3  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002fdca  mov     r9d, eax; char *
0x18002fdcd  mov     rcx, [rbp+57h]; this
0x18002fdd1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002fdd6  mov     ebx, eax
0x18002fdd8  lea     rcx, [rbp+4Fh+var_B8]
0x18002fddc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002fde1  nop
0x18002fde2  lea     rcx, [rbp+4Fh+var_A0]
0x18002fde6  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002fdeb  nop
0x18002fdec  mov     rdx, [rbp+4Fh+lpNewKeyName]; lpSubKey
0x18002fdf0  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18002fdf4  call    cs:__imp_RegDeleteTreeW
0x18002fdfb  nop     dword ptr [rax+rax+00h]
0x18002fe00  mov     rcx, [rbp+57h]; this
0x18002fe04  test    eax, eax
0x18002fe06  jz      loc_18002FBD3
0x18002fe0c  mov     r9d, eax; char *
0x18002fe0f  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002fe16  mov     edx, 128h; void *
0x18002fe1b  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002fe20  jmp     loc_18002FBD3
0x18002fe25  mov     rcx, r14; pSid
0x18002fe28  call    cs:__imp_GetLengthSid
0x18002fe2f  nop     dword ptr [rax+rax+00h]
0x18002fe34  mov     dword ptr [rsp+0F0h+cbData], eax; cbData
0x18002fe38  mov     [rsp+0F0h+phkResult], r14; int
0x18002fe3d  mov     r9d, 3; dwType
0x18002fe43  xor     r8d, r8d; Reserved
0x18002fe46  lea     rdx, aSid_0; "SID"
0x18002fe4d  mov     rcx, [rbp+4Fh+var_B8]; hKey
0x18002fe51  call    cs:__imp_RegSetValueExW
0x18002fe58  nop     dword ptr [rax+rax+00h]
0x18002fe5d  test    eax, eax
0x18002fe5f  jz      short loc_18002FE6B
0x18002fe61  mov     edx, 131h
0x18002fe66  jmp     loc_18002FDC3
0x18002fe6b  mov     r9b, 1
0x18002fe6e  lea     r8, aProfileimagepa; "ProfileImagePath"
0x18002fe75  mov     rdx, [rbp+4Fh+var_B8]
0x18002fe79  lea     rcx, [rbp+4Fh+var_A0]
0x18002fe7d  call    ?_InitializeFromRegistry@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x18002fe82  mov     ebx, eax
0x18002fe84  test    eax, eax
0x18002fe86  jns     short loc_18002FEA5
0x18002fe88  mov     edx, 132h; void *
0x18002fe8d  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002fe94  mov     r9d, eax; char *
0x18002fe97  mov     rcx, [rbp+57h]; this
0x18002fe9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fea0  jmp     loc_18002FDD8
0x18002fea5  lea     r8, [rbp+4Fh+arg_8]; unsigned int *
0x18002fea9  lea     rdx, aState; "State"
0x18002feb0  mov     rcx, [rbp+4Fh+var_B8]; HKEY
0x18002feb4  call    ?RegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; RegQueryDword(HKEY__ *,ushort const *,ulong *)
0x18002feb9  mov     ebx, eax
0x18002febb  test    eax, eax
0x18002febd  jns     short loc_18002FEC6
0x18002febf  mov     edx, 133h
0x18002fec4  jmp     short loc_18002FE8D
0x18002fec6  lea     rcx, [rbp+4Fh+var_B8]
0x18002feca  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002fecf  mov     rcx, [rbp+4Fh+lpNewKeyName]; lpString1
0x18002fed3  call    ?DeleteProfileGuidEntry@@YAJPEBG@Z; DeleteProfileGuidEntry(ushort const *)
0x18002fed8  mov     rcx, [rbp+57h]; this
0x18002fedc  test    eax, eax
0x18002fede  jns     short loc_18002FEF4
0x18002fee0  mov     r9d, eax; char *
0x18002fee3  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002feea  mov     edx, 138h; void *
0x18002feef  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002fef4  mov     rsi, [rbp+4Fh+var_A0]
0x18002fef8  mov     r9, rsi; unsigned __int16 *
0x18002fefb  mov     r8, r14; void *
0x18002fefe  mov     rdx, rdi; unsigned __int16 *
0x18002ff01  mov     rcx, [rbp+4Fh+lpNewKeyName]; unsigned __int16 *
0x18002ff05  call    ?SetProfileSecurity@@YAJPEBG0PEAX0@Z; SetProfileSecurity(ushort const *,ushort const *,void *,ushort const *)
0x18002ff0a  mov     ebx, eax
0x18002ff0c  test    eax, eax
0x18002ff0e  jns     short loc_18002FF2D
0x18002ff10  mov     rcx, [rbp+57h]; this
0x18002ff14  mov     r9d, eax; char *
0x18002ff17  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002ff1e  mov     edx, 13Bh; void *
0x18002ff23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ff28  jmp     loc_18002FDE2
0x18002ff2d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ff34  call    cs:__imp_RegFlushKey
0x18002ff3b  nop     dword ptr [rax+rax+00h]
0x18002ff40  mov     rcx, [rbp+57h]; this
0x18002ff44  test    eax, eax
0x18002ff46  jz      short loc_18002FF5C
0x18002ff48  mov     r9d, eax; char *
0x18002ff4b  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002ff52  mov     edx, 13Dh; void *
  ... truncated ...
```
