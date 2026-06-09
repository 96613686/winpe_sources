# FixAccessOnExistingUserHives(void)

- ea: `0x1800157f4`
- end: `0x180015a9c`
- name: `?FixAccessOnExistingUserHives@@YAJXZ`
- size: `680`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180037c20`

## callees

- `0x18000fa10`
- `0x1800111a0`
- `0x1800157f4`
- `0x180015d00`
- `0x18001f060`
- `0x18002d2d8`
- `0x18002e648`
- `0x18003a730`
- `0x18003b310`
- `0x180048ccc`
- `0x18004d854`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001589c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001589c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001591a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001591a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800158d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015a53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015a6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800158d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015a53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015a6c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001597a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001597a`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x1800159c9`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x1800159c9`

## string_xrefs

- `0x180015856`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`
- `0x1800158b2`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`
- `0x180015a30`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`

## pseudocode

```c
__int64 FixAccessOnExistingUserHives(void)
{
  int UserProfileListRootKeyName; // eax
  unsigned int v1; // ebx
  unsigned int v2; // eax
  __int64 v3; // rdx
  DWORD v4; // ebx
  int BasicProfileFolderPathAlloc; // edi
  __int64 v6; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchName; // [rsp+6Ch] [rbp-94h] BYREF
  LPWSTR pObjectName; // [rsp+70h] [rbp-90h] BYREF
  __int64 v14; // [rsp+78h] [rbp-88h]
  __int64 v15; // [rsp+80h] [rbp-80h]
  LPCWSTR lpSubKey; // [rsp+88h] [rbp-78h] BYREF
  __int64 v17; // [rsp+90h] [rbp-70h]
  __int64 v18; // [rsp+98h] [rbp-68h]
  WCHAR Name[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  lpSubKey = 0;
  v17 = 0;
  v18 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpSubKey);
  v17 = -1;
  v18 = -1;
  UserProfileListRootKeyName = GetUserProfileListRootKeyName((unsigned __int16 **)&lpSubKey, 0);
  v1 = UserProfileListRootKeyName;
  if ( UserProfileListRootKeyName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmgr.cpp",
      (const char *)(unsigned int)UserProfileListRootKeyName,
      phkResult);
    goto LABEL_27;
  }
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  if ( v2 )
  {
    v3 = 37;
    goto LABEL_5;
  }
  cSubKeys = 0;
  v2 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( v2 )
  {
    v3 = 41;
LABEL_5:
    v1 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v3,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmgr.cpp",
           (const char *)v2,
           phkResulta);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_27;
  }
  memset_0(Name, 0, 0x208u);
  v4 = cSubKeys;
  cchName = 0;
  while ( (--v4 & 0x80000000) == 0 )
  {
    cchName = 260;
    v2 = RegEnumKeyExW(hKey, v4, Name, &cchName, 0, 0, 0, 0);
    if ( v2 )
    {
      v3 = 48;
      goto LABEL_5;
    }
    if ( IsStrictHiveSecuritySet(hKey, Name) )
    {
      pObjectName = 0;
      v14 = 0;
      v15 = 0;
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&pObjectName);
      v14 = -1;
      v15 = -1;
      BasicProfileFolderPathAlloc = GetBasicProfileFolderPathAlloc(5, Name, &pObjectName);
      if ( BasicProfileFolderPathAlloc < 0 )
      {
        v6 = 65;
        goto LABEL_20;
      }
      BasicProfileFolderPathAlloc = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::ConcatFormat(
                                      &pObjectName,
                                      L"\\%s",
                                      L"ntuser.dat");
      if ( BasicProfileFolderPathAlloc < 0 )
      {
        v6 = 66;
        goto LABEL_20;
      }
      BasicProfileFolderPathAlloc = RevertHiveFileAccessRestriction(pObjectName, Name);
      if ( BasicProfileFolderPathAlloc < 0 )
      {
        v6 = 67;
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v6,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmgr.cpp",
          (const char *)(unsigned int)BasicProfileFolderPathAlloc,
          phkResulta);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&pObjectName);
        if ( hKey )
          RegCloseKey(hKey);
        v1 = BasicProfileFolderPathAlloc;
        goto LABEL_27;
      }
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&pObjectName);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  v1 = 0;
LABEL_27:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpSubKey);
  return v1;
}

```

## disassembly

```asm
0x1800157f4  push    rbp
0x1800157f6  push    rbx
0x1800157f7  push    rsi
0x1800157f8  push    rdi
0x1800157f9  push    r14
0x1800157fb  lea     rbp, [rsp-1C0h]
0x180015803  sub     rsp, 2C0h
0x18001580a  mov     rax, cs:__security_cookie
0x180015811  xor     rax, rsp
0x180015814  mov     [rbp+1E0h+var_30], rax
0x18001581b  xor     esi, esi
0x18001581d  lea     rcx, [rbp+1E0h+lpSubKey]
0x180015821  mov     [rbp+1E0h+lpSubKey], rsi
0x180015825  mov     [rbp+1E0h+var_250], rsi
0x180015829  mov     [rbp+1E0h+var_248], rsi
0x18001582d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180015832  or      r14, 0FFFFFFFFFFFFFFFFh
0x180015836  lea     rcx, [rbp+1E0h+lpSubKey]; unsigned __int16 **
0x18001583a  xor     edx, edx; int *
0x18001583c  mov     [rbp+1E0h+var_250], r14
0x180015840  mov     [rbp+1E0h+var_248], r14
0x180015844  call    ?GetUserProfileListRootKeyName@@YAJPEAPEAGPEAH@Z; GetUserProfileListRootKeyName(ushort * *,int *)
0x180015849  mov     ebx, eax
0x18001584b  test    eax, eax
0x18001584d  jns     short loc_18001586D
0x18001584f  mov     rcx, [rbp+1E8h]; this
0x180015856  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001585d  mov     r9d, eax; char *
0x180015860  lea     edx, [rsi+22h]; void *
0x180015863  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015868  jmp     loc_180015A74
0x18001586d  xor     edx, edx
0x18001586f  mov     [rsp+2E0h+hKey], rsi
0x180015874  lea     rcx, [rsp+2E0h+hKey]
0x180015879  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001587e  mov     rdx, [rbp+1E0h+lpSubKey]; lpSubKey
0x180015882  lea     rax, [rsp+2E0h+hKey]
0x180015887  mov     r9d, 20019h; samDesired
0x18001588d  mov     [rsp+2E0h+phkResult], rax; unsigned int
0x180015892  xor     r8d, r8d; ulOptions
0x180015895  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001589c  call    cs:__imp_RegOpenKeyExW
0x1800158a2  test    eax, eax
0x1800158a4  jz      short loc_1800158DC
0x1800158a6  mov     edx, 25h ; '%'; void *
0x1800158ab  mov     rcx, [rbp+1E8h]; this
0x1800158b2  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800158b9  mov     r9d, eax; char *
0x1800158bc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800158c1  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800158c6  mov     ebx, eax
0x1800158c8  test    rcx, rcx
0x1800158cb  jz      loc_180015A74
0x1800158d1  call    cs:__imp_RegCloseKey
0x1800158d7  jmp     loc_180015A74
0x1800158dc  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800158e1  lea     rax, [rsp+2E0h+cSubKeys]
0x1800158e6  mov     [rsp+2E0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1800158eb  xor     r9d, r9d; lpReserved
0x1800158ee  mov     [rsp+2E0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x1800158f3  xor     r8d, r8d; lpcchClass
0x1800158f6  mov     [rsp+2E0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x1800158fb  xor     edx, edx; lpClass
0x1800158fd  mov     [rsp+2E0h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x180015902  mov     [rsp+2E0h+lpcValues], rsi; lpcValues
0x180015907  mov     [rsp+2E0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x18001590c  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x180015911  mov     [rsp+2E0h+phkResult], rax; lpcSubKeys
0x180015916  mov     [rsp+2E0h+cSubKeys], esi
0x18001591a  call    cs:__imp_RegQueryInfoKeyW
0x180015920  test    eax, eax
0x180015922  jz      short loc_18001592B
0x180015924  mov     edx, 29h ; ')'
0x180015929  jmp     short loc_1800158AB
0x18001592b  xor     edx, edx; Val
0x18001592d  lea     rcx, [rbp+1E0h+Name]; void *
0x180015931  mov     r8d, 208h; Size
0x180015937  call    memset_0
0x18001593c  mov     ebx, [rsp+2E0h+cSubKeys]
0x180015940  mov     [rsp+2E0h+cchName], esi
0x180015944  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180015949  dec     ebx
0x18001594b  test    ebx, ebx
0x18001594d  js      loc_180015A67
0x180015953  mov     [rsp+2E0h+lpcValues], rsi; lpftLastWriteTime
0x180015958  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x18001595d  mov     [rsp+2E0h+lpcbMaxClassLen], rsi; lpcchClass
0x180015962  lea     r8, [rbp+1E0h+Name]; lpName
0x180015966  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rsi; lpClass
0x18001596b  mov     edx, ebx; dwIndex
0x18001596d  mov     [rsp+2E0h+phkResult], rsi; int
0x180015972  mov     [rsp+2E0h+cchName], 104h
0x18001597a  call    cs:__imp_RegEnumKeyExW
0x180015980  test    eax, eax
0x180015982  jnz     loc_180015A5D
0x180015988  mov     rcx, [rsp+2E0h+hKey]; HKEY
0x18001598d  lea     rdx, [rbp+1E0h+Name]; unsigned __int16 *
0x180015991  call    ?IsStrictHiveSecuritySet@@YA_NPEAUHKEY__@@PEBG@Z; IsStrictHiveSecuritySet(HKEY__ *,ushort const *)
0x180015996  test    al, al
0x180015998  jz      short loc_180015944
0x18001599a  lea     rcx, [rsp+2E0h+pObjectName]
0x18001599f  mov     [rsp+2E0h+pObjectName], rsi
0x1800159a4  mov     [rsp+2E0h+var_268], rsi
0x1800159a9  mov     [rbp+1E0h+var_260], rsi
0x1800159ad  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800159b2  lea     r8, [rsp+2E0h+pObjectName]
0x1800159b7  mov     [rsp+2E0h+var_268], r14
0x1800159bc  lea     rdx, [rbp+1E0h+Name]
0x1800159c0  mov     [rbp+1E0h+var_260], r14
0x1800159c4  mov     ecx, 5
0x1800159c9  call    cs:__imp_GetBasicProfileFolderPathAlloc
0x1800159cf  mov     edi, eax
0x1800159d1  test    eax, eax
0x1800159d3  js      short loc_180015A24
0x1800159d5  lea     r8, ?c_szNTUserDat@@3QBGB; "ntuser.dat"
0x1800159dc  lea     rdx, aS_1; "\\%s"
0x1800159e3  lea     rcx, [rsp+2E0h+pObjectName]
0x1800159e8  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x1800159ed  mov     edi, eax
0x1800159ef  test    eax, eax
0x1800159f1  js      short loc_180015A1D
0x1800159f3  mov     rcx, [rsp+2E0h+pObjectName]; pObjectName
0x1800159f8  lea     rdx, [rbp+1E0h+Name]; unsigned __int16 *
0x1800159fc  call    ?RevertHiveFileAccessRestriction@@YAJPEBG0@Z; RevertHiveFileAccessRestriction(ushort const *,ushort const *)
0x180015a01  mov     edi, eax
0x180015a03  test    eax, eax
0x180015a05  js      short loc_180015A16
0x180015a07  lea     rcx, [rsp+2E0h+pObjectName]
0x180015a0c  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180015a11  jmp     loc_180015944
0x180015a16  mov     edx, 43h ; 'C'
0x180015a1b  jmp     short loc_180015A29
0x180015a1d  mov     edx, 42h ; 'B'
0x180015a22  jmp     short loc_180015A29
0x180015a24  mov     edx, 41h ; 'A'; void *
0x180015a29  mov     rcx, [rbp+1E8h]; this
0x180015a30  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180015a37  mov     r9d, edi; char *
0x180015a3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015a3f  lea     rcx, [rsp+2E0h+pObjectName]
0x180015a44  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180015a49  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180015a4e  test    rcx, rcx
0x180015a51  jz      short loc_180015A59
0x180015a53  call    cs:__imp_RegCloseKey
0x180015a59  mov     ebx, edi
0x180015a5b  jmp     short loc_180015A74
0x180015a5d  mov     edx, 30h ; '0'
0x180015a62  jmp     loc_1800158AB
0x180015a67  test    rcx, rcx
0x180015a6a  jz      short loc_180015A72
0x180015a6c  call    cs:__imp_RegCloseKey
0x180015a72  mov     ebx, esi
0x180015a74  lea     rcx, [rbp+1E0h+lpSubKey]
0x180015a78  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180015a7d  mov     eax, ebx
0x180015a7f  mov     rcx, [rbp+1E0h+var_30]
0x180015a86  xor     rcx, rsp; StackCookie
0x180015a89  call    __security_check_cookie
0x180015a8e  add     rsp, 2C0h
0x180015a95  pop     r14
0x180015a97  pop     rdi
0x180015a98  pop     rsi
0x180015a99  pop     rbx
0x180015a9a  pop     rbp
0x180015a9b  retn
```
