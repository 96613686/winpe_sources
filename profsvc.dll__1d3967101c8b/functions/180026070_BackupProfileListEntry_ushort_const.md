# BackupProfileListEntry(ushort const *)

- ea: `0x180026070`
- end: `0x180026462`
- name: `?BackupProfileListEntry@@YAJPEBG@Z`
- size: `1010`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180032ce0`

## callees

- `0x18000f1b0`
- `0x180010f30`
- `0x1800111a0`
- `0x1800164e0`
- `0x18001fb70`
- `0x180021ca0`
- `0x180026070`
- `0x18002d2d8`
- `0x18002e648`
- `0x180031a80`
- `0x180033898`
- `0x180033954`
- `0x18003a730`
- `0x18003f42c`
- `0x180040bf8`
- `0x180040c50`
- `0x180041724`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002614b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800262ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002614b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800262ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026356`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026389`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800263e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002641c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026356`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026389`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800263e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002641c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180026322`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180026322`
- `api-ms-win-core-registry-private-l1-1-0!RegRenameKey` at `0x1800261c6`
- `api-ms-win-core-registry-private-l1-1-0!RegRenameKey` at `0x1800261c6`

## string_xrefs

- `0x180026109`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x18002615c`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x180026333`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x1800263b0`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x1800263fc`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`

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
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpSubKey);
  v27 = -1;
  v28 = -1;
  ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(lpString1, (unsigned __int16 **)&lpSubKey, 0);
  v3 = ProfileListKeyNameFromSid;
  if ( ProfileListKeyNameFromSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
      (const char *)(unsigned int)ProfileListKeyNameFromSid,
      phkResult);
LABEL_38:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpSubKey);
    ProfileTelemetry::BackupProfileListEntry::~BackupProfileListEntry((ProfileTelemetry::BackupProfileListEntry *)v31);
    return v3;
  }
  v4 = lpSubKey;
  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, &hKey);
  if ( v5 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x25,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
           (const char *)v5,
           phkResulta);
    goto LABEL_36;
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
LABEL_35:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
      (const char *)v7,
      phkResulta);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpNewKeyName);
LABEL_36:
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_38;
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
      goto LABEL_35;
    }
    memset(v29, 0, sizeof(v29));
    if ( (int)Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
                v29,
                L"%s%s",
                v4,
                L".bak") < 0 )
      goto LABEL_31;
    v24 = 0;
    v14 = 0;
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
      ProfileTelemetry::BackupAlreadyExists<unsigned short const *>((__int64 *)v32);
      v19 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, v4);
      if ( v19 >= 0 )
        v14 = 1;
      else
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4B,
          (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
          (const char *)(unsigned int)v19);
    }
    if ( v24 )
      RegCloseKey(v24);
    if ( !v14 )
    {
LABEL_31:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x50,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
        (const char *)0x80070005LL,
        phkResulta);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v29);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpNewKeyName);
      if ( hKey )
        RegCloseKey(hKey);
      v3 = -2147024891;
      goto LABEL_38;
    }
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v29);
  }
  else
  {
    v30 = v9;
    *(_QWORD *)v32 = v4;
    ProfileTelemetry::BackupKeyRename<unsigned short const *,unsigned short const *>(v32, (__int64 *)&v30);
    LODWORD(v24) = 0;
    DWORD = SHRegGetDWORD(hKey, 0, L"State", (unsigned int *)&v24);
    v3 = DWORD;
    if ( DWORD < 0 )
    {
      v7 = (unsigned int)DWORD;
      v8 = 50;
      goto LABEL_35;
    }
    LODWORD(v24) = (unsigned int)v24 | 0x8000;
    v13 = SHRegSetDWORD(hKey, 0, L"State", (unsigned int)v24);
    v3 = v13;
    if ( v13 < 0 )
    {
      v7 = (unsigned int)v13;
      v8 = 53;
      goto LABEL_35;
    }
  }
  ProfileTelemetry::BackupProfileListEntry::Stop((ProfileTelemetry::BackupProfileListEntry *)v31, v10);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpNewKeyName);
  if ( hKey )
    RegCloseKey(hKey);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpSubKey);
  ProfileTelemetry::BackupProfileListEntry::~BackupProfileListEntry((ProfileTelemetry::BackupProfileListEntry *)v31);
  return 0;
}

```

## disassembly

```asm
0x180026070  mov     [rsp-8+arg_8], rbx
0x180026075  mov     [rsp-8+arg_10], rsi
0x18002607a  push    rbp
0x18002607b  push    rdi
0x18002607c  push    r13
0x18002607e  push    r14
0x180026080  push    r15
0x180026082  lea     rbp, [rsp-100h]
0x18002608a  sub     rsp, 200h
0x180026091  mov     rax, cs:__security_cookie
0x180026098  xor     rax, rsp
0x18002609b  mov     [rbp+120h+var_30], rax
0x1800260a2  mov     rdi, rcx
0x1800260a5  lea     rcx, [rbp+120h+var_190]; struct wil::details::IFailureCallback *
0x1800260a9  call    ??0?$ActivityBase@VProfileLogging@@$00$0CAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileLogging,1,35184372088832,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,35184372088832,4,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800260ae  lea     rax, ??_7BackupProfileListEntry@ProfileTelemetry@@6B@; const ProfileTelemetry::BackupProfileListEntry::`vftable'
0x1800260b5  lea     rcx, [rbp+120h+var_190]; this
0x1800260b9  mov     [rbp+120h+var_190], rax
0x1800260bd  call    ?StartActivity@BackupProfileListEntry@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::BackupProfileListEntry::StartActivity(void)
0x1800260c2  xor     r15d, r15d
0x1800260c5  lea     rcx, [rsp+220h+lpSubKey]
0x1800260ca  mov     [rsp+220h+lpSubKey], r15
0x1800260cf  mov     [rsp+220h+var_1C0], r15
0x1800260d4  mov     [rsp+220h+var_1B8], r15
0x1800260d9  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800260de  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800260e2  lea     rdx, [rsp+220h+lpSubKey]; unsigned __int16 **
0x1800260e7  xor     r8d, r8d; int *
0x1800260ea  mov     [rsp+220h+var_1C0], rax
0x1800260ef  mov     rcx, rdi; lpString1
0x1800260f2  mov     [rsp+220h+var_1B8], rax
0x1800260f7  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x1800260fc  mov     ebx, eax
0x1800260fe  test    eax, eax
0x180026100  jns     short loc_180026121
0x180026102  mov     rcx, [rbp+128h]; this
0x180026109  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x180026110  mov     r9d, eax; char *
0x180026113  lea     edx, [r15+22h]; void *
0x180026117  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002611c  jmp     loc_180026422
0x180026121  mov     rsi, [rsp+220h+lpSubKey]
0x180026126  lea     rax, [rsp+220h+hKey]
0x18002612b  mov     r13, 0FFFFFFFF80000002h
0x180026132  mov     [rsp+220h+hKey], r15
0x180026137  mov     rdx, rsi; lpSubKey
0x18002613a  mov     qword ptr [rsp+220h+phkResult], rax; int
0x18002613f  mov     rcx, r13; hKey
0x180026142  mov     r9d, 2001Fh; samDesired
0x180026148  xor     r8d, r8d; ulOptions
0x18002614b  call    cs:__imp_RegOpenKeyExW
0x180026151  test    eax, eax
0x180026153  jz      short loc_180026177
0x180026155  mov     rcx, [rbp+128h]; this
0x18002615c  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x180026163  mov     r9d, eax; char *
0x180026166  mov     edx, 25h ; '%'; void *
0x18002616b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180026170  mov     ebx, eax
0x180026172  jmp     loc_180026412
0x180026177  lea     r9, ?c_szBAK@@3QBGB; ".bak"
0x18002617e  mov     [rsp+220h+lpNewKeyName], r15
0x180026183  mov     r8, rdi
0x180026186  mov     [rsp+220h+var_1D8], r15
0x18002618b  lea     rdx, aSS_1; "%s%s"
0x180026192  mov     [rsp+220h+var_1D0], r15
0x180026197  lea     rcx, [rsp+220h+lpNewKeyName]
0x18002619c  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800261a1  mov     ebx, eax
0x1800261a3  test    eax, eax
0x1800261a5  jns     short loc_1800261B4
0x1800261a7  mov     r9d, eax
0x1800261aa  mov     edx, 28h ; '('
0x1800261af  jmp     loc_1800263F5
0x1800261b4  mov     r14, [rsp+220h+lpNewKeyName]
0x1800261b9  xor     edx, edx; lpSubKeyName
0x1800261bb  mov     rcx, [rsp+220h+hKey]; hKey
0x1800261c0  mov     r8, r14; lpNewKeyName
0x1800261c3  mov     edi, r15d
0x1800261c6  call    cs:__imp_RegRenameKey
0x1800261cc  mov     ebx, eax
0x1800261ce  test    eax, eax
0x1800261d0  jle     short loc_1800261DB
0x1800261d2  movzx   ebx, ax
0x1800261d5  or      ebx, 80070000h
0x1800261db  test    ebx, ebx
0x1800261dd  js      loc_180026267
0x1800261e3  lea     rdx, [rbp+120h+var_198]
0x1800261e7  mov     [rbp+120h+var_198], r14
0x1800261eb  lea     rcx, [rbp+120h+var_40]
0x1800261f2  mov     qword ptr [rbp+120h+var_40], rsi
0x1800261f9  call    ??$BackupKeyRename@PEBGPEBG@ProfileTelemetry@@SAX$$QEAPEBG0@Z; ProfileTelemetry::BackupKeyRename<ushort const *,ushort const *>(ushort const * &&,ushort const * &&)
0x1800261fe  mov     rcx, [rsp+220h+hKey]; HKEY
0x180026203  lea     r9, [rsp+220h+var_1E8]; unsigned int *
0x180026208  lea     r8, aState; "State"
0x18002620f  mov     dword ptr [rsp+220h+var_1E8], r15d
0x180026214  xor     edx, edx; unsigned __int16 *
0x180026216  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002621b  mov     ebx, eax
0x18002621d  test    eax, eax
0x18002621f  jns     short loc_18002622E
0x180026221  mov     r9d, eax
0x180026224  mov     edx, 32h ; '2'
0x180026229  jmp     loc_1800263F5
0x18002622e  mov     r9d, dword ptr [rsp+220h+var_1E8]
0x180026233  lea     r8, aState; "State"
0x18002623a  mov     rcx, [rsp+220h+hKey]; HKEY
0x18002623f  bts     r9d, 0Fh; unsigned int
0x180026244  xor     edx, edx; unsigned __int16 *
0x180026246  mov     dword ptr [rsp+220h+var_1E8], r9d
0x18002624b  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180026250  mov     ebx, eax
0x180026252  test    eax, eax
0x180026254  jns     loc_18002636A
0x18002625a  mov     r9d, eax
0x18002625d  mov     edx, 35h ; '5'
0x180026262  jmp     loc_1800263F5
0x180026267  mov     r14d, 80070005h
0x18002626d  cmp     ebx, r14d
0x180026270  jnz     loc_1800263ED
0x180026276  lea     r9, ?c_szBAK@@3QBGB; ".bak"
0x18002627d  mov     [rsp+220h+var_1B0], r15
0x180026282  mov     r8, rsi
0x180026285  mov     [rsp+220h+var_1A8], r15
0x18002628a  lea     rdx, aSS_1; "%s%s"
0x180026291  mov     [rbp+120h+var_1A0], r15
0x180026295  lea     rcx, [rsp+220h+var_1B0]
0x18002629a  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18002629f  test    eax, eax
0x1800262a1  js      loc_1800263A9
0x1800262a7  mov     rdx, [rsp+220h+var_1B0]; lpSubKey
0x1800262ac  lea     rax, [rsp+220h+var_1E8]
0x1800262b1  mov     r9d, 20019h; samDesired
0x1800262b7  mov     qword ptr [rsp+220h+phkResult], rax; phkResult
0x1800262bc  xor     r8d, r8d; ulOptions
0x1800262bf  mov     [rsp+220h+var_1E8], r15
0x1800262c4  mov     rcx, r13; hKey
0x1800262c7  mov     bl, r15b
0x1800262ca  call    cs:__imp_RegOpenKeyExW
0x1800262d0  test    eax, eax
0x1800262d2  jle     short loc_1800262DE
0x1800262d4  movzx   eax, ax
0x1800262d7  or      eax, 80070000h
0x1800262dc  test    eax, eax
0x1800262de  js      short loc_18002634C
0x1800262e0  mov     edi, 1
0x1800262e5  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, dil
0x1800262ec  jz      short loc_180026309
0x1800262ee  lea     rax, [rbp+120h+var_40]
0x1800262f5  mov     r9d, edi
0x1800262f8  lea     rdx, EVENT_PROFILELIST_BACKUP_ALREADY_EXISTS
0x1800262ff  mov     qword ptr [rsp+220h+phkResult], rax; int
0x180026304  call    McGenEventWrite_EtwEventWriteTransfer
0x180026309  lea     rcx, [rbp+120h+var_40]
0x180026310  mov     qword ptr [rbp+120h+var_40], rsi
0x180026317  call    ??$BackupAlreadyExists@PEBG@ProfileTelemetry@@SAX$$QEAPEBG@Z; ProfileTelemetry::BackupAlreadyExists<ushort const *>(ushort const * &&)
0x18002631c  mov     rdx, rsi; lpSubKey
0x18002631f  mov     rcx, r13; hKey
0x180026322  call    cs:__imp_RegDeleteTreeW
0x180026328  test    eax, eax
0x18002632a  jns     short loc_180026349
0x18002632c  mov     rcx, [rbp+128h]; this
0x180026333  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002633a  mov     r9d, eax; char *
0x18002633d  mov     edx, 4Bh ; 'K'; void *
0x180026342  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026347  jmp     short loc_18002634C
0x180026349  mov     bl, dil
0x18002634c  mov     rcx, [rsp+220h+var_1E8]; hKey
0x180026351  test    rcx, rcx
0x180026354  jz      short loc_18002635C
0x180026356  call    cs:__imp_RegCloseKey
0x18002635c  test    bl, bl
0x18002635e  jz      short loc_1800263A9
0x180026360  lea     rcx, [rsp+220h+var_1B0]
0x180026365  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002636a  mov     edx, edi; int
0x18002636c  lea     rcx, [rbp+120h+var_190]; this
0x180026370  call    ?Stop@BackupProfileListEntry@ProfileTelemetry@@QEAAXH@Z; ProfileTelemetry::BackupProfileListEntry::Stop(int)
0x180026375  lea     rcx, [rsp+220h+lpNewKeyName]
0x18002637a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002637f  mov     rcx, [rsp+220h+hKey]; hKey
0x180026384  test    rcx, rcx
0x180026387  jz      short loc_18002638F
0x180026389  call    cs:__imp_RegCloseKey
0x18002638f  lea     rcx, [rsp+220h+lpSubKey]
0x180026394  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180026399  lea     rcx, [rbp+120h+var_190]; this
0x18002639d  call    ??1BackupProfileListEntry@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::BackupProfileListEntry::~BackupProfileListEntry(void)
0x1800263a2  xor     eax, eax
0x1800263a4  jmp     loc_180026437
0x1800263a9  mov     rcx, [rbp+128h]; this
0x1800263b0  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800263b7  mov     r9d, r14d; char *
0x1800263ba  mov     edx, 50h ; 'P'; void *
0x1800263bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800263c4  lea     rcx, [rsp+220h+var_1B0]
0x1800263c9  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800263ce  lea     rcx, [rsp+220h+lpNewKeyName]
0x1800263d3  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800263d8  mov     rcx, [rsp+220h+hKey]; hKey
0x1800263dd  test    rcx, rcx
0x1800263e0  jz      short loc_1800263E8
0x1800263e2  call    cs:__imp_RegCloseKey
0x1800263e8  mov     ebx, r14d
0x1800263eb  jmp     short loc_180026422
0x1800263ed  mov     r9d, ebx; char *
0x1800263f0  mov     edx, 54h ; 'T'; void *
0x1800263f5  mov     rcx, [rbp+128h]; this
0x1800263fc  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x180026403  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026408  lea     rcx, [rsp+220h+lpNewKeyName]
0x18002640d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180026412  mov     rcx, [rsp+220h+hKey]; hKey
0x180026417  test    rcx, rcx
0x18002641a  jz      short loc_180026422
0x18002641c  call    cs:__imp_RegCloseKey
0x180026422  lea     rcx, [rsp+220h+lpSubKey]
0x180026427  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002642c  lea     rcx, [rbp+120h+var_190]; this
0x180026430  call    ??1BackupProfileListEntry@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::BackupProfileListEntry::~BackupProfileListEntry(void)
0x180026435  mov     eax, ebx
0x180026437  mov     rcx, [rbp+120h+var_30]
0x18002643e  xor     rcx, rsp; StackCookie
0x180026441  call    __security_check_cookie
0x180026446  lea     r11, [rsp+220h+var_20]
0x18002644e  mov     rbx, [r11+38h]
0x180026452  mov     rsi, [r11+40h]
0x180026456  mov     rsp, r11
0x180026459  pop     r15
0x18002645b  pop     r14
0x18002645d  pop     r13
0x18002645f  pop     rdi
0x180026460  pop     rbp
0x180026461  retn
```
