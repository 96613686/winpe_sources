# BackupProfileListEntry(ushort const *)

- ea: `0x180012ca0`
- end: `0x1800130c3`
- name: `?BackupProfileListEntry@@YAJPEBG@Z`
- size: `1059`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002e1dc`

## callees

- `0x18000d030`
- `0x18000d2c0`
- `0x18000e1a0`
- `0x180012ca0`
- `0x1800130d0`
- `0x180013770`
- `0x180014b4c`
- `0x180022440`
- `0x180024cb0`
- `0x180030ad0`
- `0x180031060`
- `0x180032208`
- `0x180033f58`
- `0x180034018`
- `0x18003bc70`
- `0x180040bcc`
- `0x1800425d0`
- `0x18004262c`
- `0x180043100`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012d87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012f1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012d87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012f1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012fb6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013042`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012fb6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013042`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180012f7c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180012f7c`
- `api-ms-win-core-registry-private-l1-1-0!RegRenameKey` at `0x180012e08`
- `api-ms-win-core-registry-private-l1-1-0!RegRenameKey` at `0x180012e08`

## string_xrefs

- `0x180012d39`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x180012d9e`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x180012f93`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x180013010`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x180013062`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`

## pseudocode

```c
__int64 __fastcall BackupProfileListEntry(LPCWCH lpString1)
{
  int ProfileListKeyNameFromSid; // eax
  unsigned int v3; // ebx
  const WCHAR *v4; // rsi
  unsigned int v5; // eax
  int v6; // eax
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  LPCWSTR v9; // r14
  int v10; // edi
  LSTATUS v11; // eax
  int DWORD; // eax
  int v13; // eax
  char v14; // bl
  LSTATUS v15; // eax
  int v16; // ecx
  int v17; // r8d
  bool v18; // sf
  LSTATUS v19; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v24; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpNewKeyName[3]; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpSubKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A0h]
  __int64 v28; // [rsp+68h] [rbp-98h]
  LPCWSTR v29[3]; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR v30; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v31[42]; // [rsp+90h] [rbp-70h] BYREF
  int v32[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  wil::ActivityBase<ProfileLogging,1,35184372088832,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,35184372088832,4,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v31);
  v31[0] = &ProfileTelemetry::BackupProfileListEntry::`vftable';
  ProfileTelemetry::BackupProfileListEntry::StartActivity((ProfileTelemetry::BackupProfileListEntry *)v31);
  lpSubKey = 0;
  v27 = 0;
  v28 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
  v27 = -1;
  v28 = -1;
  ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(lpString1, (unsigned __int16 **)&lpSubKey, 0);
  v3 = ProfileListKeyNameFromSid;
  if ( ProfileListKeyNameFromSid >= 0 )
  {
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v4 = lpSubKey;
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, &hKey);
    if ( v5 )
    {
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x25,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
             (const char *)v5,
             phkResulta);
LABEL_34:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_35;
    }
    memset(lpNewKeyName, 0, sizeof(lpNewKeyName));
    v6 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
           lpNewKeyName,
           L"%s%s",
           lpString1,
           L".bak");
    v3 = v6;
    if ( v6 < 0 )
    {
      v7 = (unsigned int)v6;
      v8 = 40;
LABEL_33:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
        (const char *)v7,
        phkResulta);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpNewKeyName);
      goto LABEL_34;
    }
    v9 = lpNewKeyName[0];
    v10 = 0;
    v11 = RegRenameKey(hKey, 0, lpNewKeyName[0]);
    v3 = v11;
    if ( v11 > 0 )
      v3 = (unsigned __int16)v11 | 0x80070000;
    if ( (v3 & 0x80000000) != 0 )
    {
      if ( v3 != -2147024891 )
      {
        v7 = v3;
        v8 = 84;
        goto LABEL_33;
      }
      memset(v29, 0, sizeof(v29));
      if ( (int)Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
                  v29,
                  L"%s%s",
                  v4,
                  L".bak") < 0 )
        goto LABEL_29;
      v24 = 0;
      v14 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v24,
        0);
      v15 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v29[0], 0, 0x20019u, &v24);
      v18 = v15 < 0;
      if ( v15 > 0 )
        v18 = 1;
      if ( !v18 )
      {
        v10 = 1;
        if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 1) != 0 )
          McGenEventWrite_EtwEventWriteTransfer(
            v16,
            (unsigned int)EVENT_PROFILELIST_BACKUP_ALREADY_EXISTS,
            v17,
            1,
            (__int64)v32);
        *(_QWORD *)v32 = v4;
        ProfileTelemetry::BackupAlreadyExists<unsigned short const *>(v32);
        v19 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, v4);
        if ( v19 >= 0 )
          v14 = 1;
        else
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4B,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
            (const char *)(unsigned int)v19,
            phkResulta);
      }
      if ( v24 )
        RegCloseKey(v24);
      if ( !v14 )
      {
LABEL_29:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x50,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
          (const char *)0x80070005LL,
          phkResulta);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v29);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpNewKeyName);
        if ( hKey )
          RegCloseKey(hKey);
        v3 = -2147024891;
        goto LABEL_35;
      }
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v29);
    }
    else
    {
      v30 = v9;
      *(_QWORD *)v32 = v4;
      ProfileTelemetry::BackupKeyRename<unsigned short const *,unsigned short const *>(v32, &v30);
      LODWORD(v24) = 0;
      DWORD = SHRegGetDWORD(hKey, 0, L"State", (unsigned int *)&v24);
      v3 = DWORD;
      if ( DWORD < 0 )
      {
        v7 = (unsigned int)DWORD;
        v8 = 50;
        goto LABEL_33;
      }
      LODWORD(v24) = (unsigned int)v24 | 0x8000;
      v13 = SHRegSetDWORD(hKey, 0, L"State", (unsigned int)v24);
      v3 = v13;
      if ( v13 < 0 )
      {
        v7 = (unsigned int)v13;
        v8 = 53;
        goto LABEL_33;
      }
    }
    ProfileTelemetry::BackupProfileListEntry::Stop((ProfileTelemetry::BackupProfileListEntry *)v31, v10);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpNewKeyName);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
    ProfileTelemetry::BackupProfileListEntry::~BackupProfileListEntry((ProfileTelemetry::BackupProfileListEntry *)v31);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x22,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
    (const char *)(unsigned int)ProfileListKeyNameFromSid,
    phkResult);
LABEL_35:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
  ProfileTelemetry::BackupProfileListEntry::~BackupProfileListEntry((ProfileTelemetry::BackupProfileListEntry *)v31);
  return v3;
}

```

## disassembly

```asm
0x180012ca0  mov     [rsp-8+arg_8], rbx
0x180012ca5  mov     [rsp-8+arg_10], rsi
0x180012caa  push    rbp
0x180012cab  push    rdi
0x180012cac  push    r13
0x180012cae  push    r14
0x180012cb0  push    r15
0x180012cb2  lea     rbp, [rsp-100h]
0x180012cba  sub     rsp, 200h
0x180012cc1  mov     rax, cs:__security_cookie
0x180012cc8  xor     rax, rsp
0x180012ccb  mov     [rbp+120h+var_30], rax
0x180012cd2  mov     rdi, rcx
0x180012cd5  lea     rcx, [rbp+120h+var_190]; struct wil::details::IFailureCallback *
0x180012cd9  call    ??0?$ActivityBase@VProfileLogging@@$00$0CAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileLogging,1,35184372088832,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,35184372088832,4,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180012cde  lea     rax, ??_7BackupProfileListEntry@ProfileTelemetry@@6B@; const ProfileTelemetry::BackupProfileListEntry::`vftable'
0x180012ce5  lea     rcx, [rbp+120h+var_190]; this
0x180012ce9  mov     [rbp+120h+var_190], rax
0x180012ced  call    ?StartActivity@BackupProfileListEntry@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::BackupProfileListEntry::StartActivity(void)
0x180012cf2  xor     r15d, r15d
0x180012cf5  lea     rcx, [rsp+220h+lpSubKey]
0x180012cfa  mov     [rsp+220h+lpSubKey], r15
0x180012cff  mov     [rsp+220h+var_1C0], r15
0x180012d04  mov     [rsp+220h+var_1B8], r15
0x180012d09  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180012d0e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012d12  lea     rdx, [rsp+220h+lpSubKey]; unsigned __int16 **
0x180012d17  xor     r8d, r8d; int *
0x180012d1a  mov     [rsp+220h+var_1C0], rax
0x180012d1f  mov     rcx, rdi; lpString1
0x180012d22  mov     [rsp+220h+var_1B8], rax
0x180012d27  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x180012d2c  mov     ebx, eax
0x180012d2e  test    eax, eax
0x180012d30  jns     short loc_180012D51
0x180012d32  mov     rcx, [rbp+128h]; this
0x180012d39  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x180012d40  mov     r9d, eax; char *
0x180012d43  lea     edx, [r15+22h]; void *
0x180012d47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012d4c  jmp     loc_180013082
0x180012d51  xor     edx, edx
0x180012d53  mov     [rsp+220h+hKey], r15
0x180012d58  lea     rcx, [rsp+220h+hKey]
0x180012d5d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180012d62  mov     rsi, [rsp+220h+lpSubKey]
0x180012d67  lea     rax, [rsp+220h+hKey]
0x180012d6c  mov     r13, 0FFFFFFFF80000002h
0x180012d73  mov     qword ptr [rsp+220h+phkResult], rax; int
0x180012d78  mov     rdx, rsi; lpSubKey
0x180012d7b  mov     rcx, r13; hKey
0x180012d7e  mov     r9d, 2001Fh; samDesired
0x180012d84  xor     r8d, r8d; ulOptions
0x180012d87  call    cs:__imp_RegOpenKeyExW
0x180012d8e  nop     dword ptr [rax+rax+00h]
0x180012d93  test    eax, eax
0x180012d95  jz      short loc_180012DB9
0x180012d97  mov     rcx, [rbp+128h]; this
0x180012d9e  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x180012da5  mov     r9d, eax; char *
0x180012da8  mov     edx, 25h ; '%'; void *
0x180012dad  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180012db2  mov     ebx, eax
0x180012db4  jmp     loc_180013078
0x180012db9  lea     r9, ?c_szBAK@@3QBGB; ".bak"
0x180012dc0  mov     [rsp+220h+lpNewKeyName], r15
0x180012dc5  mov     r8, rdi
0x180012dc8  mov     [rsp+220h+var_1D8], r15
0x180012dcd  lea     rdx, aSS_1; "%s%s"
0x180012dd4  mov     [rsp+220h+var_1D0], r15
0x180012dd9  lea     rcx, [rsp+220h+lpNewKeyName]
0x180012dde  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180012de3  mov     ebx, eax
0x180012de5  test    eax, eax
0x180012de7  jns     short loc_180012DF6
0x180012de9  mov     r9d, eax
0x180012dec  mov     edx, 28h ; '('
0x180012df1  jmp     loc_18001305B
0x180012df6  mov     r14, [rsp+220h+lpNewKeyName]
0x180012dfb  xor     edx, edx; lpSubKeyName
0x180012dfd  mov     rcx, [rsp+220h+hKey]; hKey
0x180012e02  mov     r8, r14; lpNewKeyName
0x180012e05  mov     edi, r15d
0x180012e08  call    cs:__imp_RegRenameKey
0x180012e0f  nop     dword ptr [rax+rax+00h]
0x180012e14  mov     ebx, eax
0x180012e16  test    eax, eax
0x180012e18  jle     short loc_180012E23
0x180012e1a  movzx   ebx, ax
0x180012e1d  or      ebx, 80070000h
0x180012e23  test    ebx, ebx
0x180012e25  js      loc_180012EAF
0x180012e2b  lea     rdx, [rbp+120h+var_198]
0x180012e2f  mov     [rbp+120h+var_198], r14
0x180012e33  lea     rcx, [rbp+120h+var_40]
0x180012e3a  mov     qword ptr [rbp+120h+var_40], rsi
0x180012e41  call    ??$BackupKeyRename@PEBGPEBG@ProfileTelemetry@@SAX$$QEAPEBG0@Z; ProfileTelemetry::BackupKeyRename<ushort const *,ushort const *>(ushort const * &&,ushort const * &&)
0x180012e46  mov     rcx, [rsp+220h+hKey]; HKEY
0x180012e4b  lea     r9, [rsp+220h+var_1E8]; unsigned int *
0x180012e50  lea     r8, aState; "State"
0x180012e57  mov     dword ptr [rsp+220h+var_1E8], r15d
0x180012e5c  xor     edx, edx; unsigned __int16 *
0x180012e5e  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180012e63  mov     ebx, eax
0x180012e65  test    eax, eax
0x180012e67  jns     short loc_180012E76
0x180012e69  mov     r9d, eax
0x180012e6c  mov     edx, 32h ; '2'
0x180012e71  jmp     loc_18001305B
0x180012e76  mov     r9d, dword ptr [rsp+220h+var_1E8]
0x180012e7b  lea     r8, aState; "State"
0x180012e82  mov     rcx, [rsp+220h+hKey]; HKEY
0x180012e87  bts     r9d, 0Fh; unsigned int
0x180012e8c  xor     edx, edx; unsigned __int16 *
0x180012e8e  mov     dword ptr [rsp+220h+var_1E8], r9d
0x180012e93  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180012e98  mov     ebx, eax
0x180012e9a  test    eax, eax
0x180012e9c  jns     loc_180012FD0
0x180012ea2  mov     r9d, eax
0x180012ea5  mov     edx, 35h ; '5'
0x180012eaa  jmp     loc_18001305B
0x180012eaf  mov     r14d, 80070005h
0x180012eb5  cmp     ebx, r14d
0x180012eb8  jnz     loc_180013053
0x180012ebe  lea     r9, ?c_szBAK@@3QBGB; ".bak"
0x180012ec5  mov     [rsp+220h+var_1B0], r15
0x180012eca  mov     r8, rsi
0x180012ecd  mov     [rsp+220h+var_1A8], r15
0x180012ed2  lea     rdx, aSS_1; "%s%s"
0x180012ed9  mov     [rbp+120h+var_1A0], r15
0x180012edd  lea     rcx, [rsp+220h+var_1B0]
0x180012ee2  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180012ee7  test    eax, eax
0x180012ee9  js      loc_180013009
0x180012eef  xor     edx, edx
0x180012ef1  mov     [rsp+220h+var_1E8], r15
0x180012ef6  lea     rcx, [rsp+220h+var_1E8]
0x180012efb  mov     bl, r15b
0x180012efe  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180012f03  mov     rdx, [rsp+220h+var_1B0]; lpSubKey
0x180012f08  lea     rax, [rsp+220h+var_1E8]
0x180012f0d  mov     r9d, 20019h; samDesired
0x180012f13  mov     qword ptr [rsp+220h+phkResult], rax; phkResult
0x180012f18  xor     r8d, r8d; ulOptions
0x180012f1b  mov     rcx, r13; hKey
0x180012f1e  call    cs:__imp_RegOpenKeyExW
0x180012f25  nop     dword ptr [rax+rax+00h]
0x180012f2a  test    eax, eax
0x180012f2c  jle     short loc_180012F38
0x180012f2e  movzx   eax, ax
0x180012f31  or      eax, 80070000h
0x180012f36  test    eax, eax
0x180012f38  js      short loc_180012FAC
0x180012f3a  mov     edi, 1
0x180012f3f  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, dil
0x180012f46  jz      short loc_180012F63
0x180012f48  lea     rax, [rbp+120h+var_40]
0x180012f4f  mov     r9d, edi
0x180012f52  lea     rdx, EVENT_PROFILELIST_BACKUP_ALREADY_EXISTS
0x180012f59  mov     qword ptr [rsp+220h+phkResult], rax; int
0x180012f5e  call    McGenEventWrite_EtwEventWriteTransfer
0x180012f63  lea     rcx, [rbp+120h+var_40]
0x180012f6a  mov     qword ptr [rbp+120h+var_40], rsi
0x180012f71  call    ??$BackupAlreadyExists@PEBG@ProfileTelemetry@@SAX$$QEAPEBG@Z; ProfileTelemetry::BackupAlreadyExists<ushort const *>(ushort const * &&)
0x180012f76  mov     rdx, rsi; lpSubKey
0x180012f79  mov     rcx, r13; hKey
0x180012f7c  call    cs:__imp_RegDeleteTreeW
0x180012f83  nop     dword ptr [rax+rax+00h]
0x180012f88  test    eax, eax
0x180012f8a  jns     short loc_180012FA9
0x180012f8c  mov     rcx, [rbp+128h]; this
0x180012f93  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x180012f9a  mov     r9d, eax; char *
0x180012f9d  mov     edx, 4Bh ; 'K'; void *
0x180012fa2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012fa7  jmp     short loc_180012FAC
0x180012fa9  mov     bl, dil
0x180012fac  mov     rcx, [rsp+220h+var_1E8]; hKey
0x180012fb1  test    rcx, rcx
0x180012fb4  jz      short loc_180012FC2
0x180012fb6  call    cs:__imp_RegCloseKey
0x180012fbd  nop     dword ptr [rax+rax+00h]
0x180012fc2  test    bl, bl
0x180012fc4  jz      short loc_180013009
0x180012fc6  lea     rcx, [rsp+220h+var_1B0]
0x180012fcb  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180012fd0  mov     edx, edi; int
0x180012fd2  lea     rcx, [rbp+120h+var_190]; this
0x180012fd6  call    ?Stop@BackupProfileListEntry@ProfileTelemetry@@QEAAXH@Z; ProfileTelemetry::BackupProfileListEntry::Stop(int)
0x180012fdb  lea     rcx, [rsp+220h+lpNewKeyName]
0x180012fe0  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180012fe5  lea     rcx, [rsp+220h+hKey]
0x180012fea  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180012fef  lea     rcx, [rsp+220h+lpSubKey]
0x180012ff4  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180012ff9  lea     rcx, [rbp+120h+var_190]; this
0x180012ffd  call    ??1BackupProfileListEntry@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::BackupProfileListEntry::~BackupProfileListEntry(void)
0x180013002  xor     eax, eax
0x180013004  jmp     loc_180013097
0x180013009  mov     rcx, [rbp+128h]; this
0x180013010  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x180013017  mov     r9d, r14d; char *
0x18001301a  mov     edx, 50h ; 'P'; void *
0x18001301f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013024  lea     rcx, [rsp+220h+var_1B0]
0x180013029  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001302e  lea     rcx, [rsp+220h+lpNewKeyName]
0x180013033  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180013038  mov     rcx, [rsp+220h+hKey]; hKey
0x18001303d  test    rcx, rcx
0x180013040  jz      short loc_18001304E
0x180013042  call    cs:__imp_RegCloseKey
0x180013049  nop     dword ptr [rax+rax+00h]
0x18001304e  mov     ebx, r14d
0x180013051  jmp     short loc_180013082
0x180013053  mov     r9d, ebx; char *
0x180013056  mov     edx, 54h ; 'T'; void *
0x18001305b  mov     rcx, [rbp+128h]; this
0x180013062  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x180013069  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001306e  lea     rcx, [rsp+220h+lpNewKeyName]
0x180013073  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180013078  lea     rcx, [rsp+220h+hKey]
0x18001307d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180013082  lea     rcx, [rsp+220h+lpSubKey]
0x180013087  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001308c  lea     rcx, [rbp+120h+var_190]; this
0x180013090  call    ??1BackupProfileListEntry@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::BackupProfileListEntry::~BackupProfileListEntry(void)
0x180013095  mov     eax, ebx
0x180013097  mov     rcx, [rbp+120h+var_30]
0x18001309e  xor     rcx, rsp; StackCookie
0x1800130a1  call    __security_check_cookie
0x1800130a6  lea     r11, [rsp+220h+var_20]
0x1800130ae  mov     rbx, [r11+38h]
0x1800130b2  mov     rsi, [r11+40h]
0x1800130b6  mov     rsp, r11
0x1800130b9  pop     r15
0x1800130bb  pop     r14
0x1800130bd  pop     r13
0x1800130bf  pop     rdi
0x1800130c0  pop     rbp
0x1800130c1  retn
```
