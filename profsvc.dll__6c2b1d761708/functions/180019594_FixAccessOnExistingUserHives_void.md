# FixAccessOnExistingUserHives(void)

- ea: `0x180019594`
- end: `0x180019844`
- name: `?FixAccessOnExistingUserHives@@YAJXZ`
- size: `688`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180039094`

## callees

- `0x18000dc10`
- `0x18000e1a0`
- `0x1800130d0`
- `0x180013770`
- `0x180019594`
- `0x180019ab0`
- `0x180030ad0`
- `0x180031060`
- `0x18003bc70`
- `0x18003c870`
- `0x18004b17c`
- `0x180050b70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001963c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001963c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800196b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800196b6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001971c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001971c`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x180019771`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x180019771`

## string_xrefs

- `0x1800195f6`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`
- `0x180019658`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`
- `0x1800197de`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`

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
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
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
    goto LABEL_22;
  }
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  if ( v2 )
  {
    v3 = 37;
LABEL_5:
    v1 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v3,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmgr.cpp",
           (const char *)v2,
           phkResulta);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_22;
  }
  cSubKeys = 0;
  v2 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( v2 )
  {
    v3 = 41;
    goto LABEL_5;
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
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&pObjectName);
      v14 = -1;
      v15 = -1;
      BasicProfileFolderPathAlloc = GetBasicProfileFolderPathAlloc(5, Name, &pObjectName);
      if ( BasicProfileFolderPathAlloc < 0 )
      {
        v6 = 65;
        goto LABEL_19;
      }
      BasicProfileFolderPathAlloc = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::ConcatFormat(
                                      &pObjectName,
                                      L"\\%s",
                                      L"ntuser.dat");
      if ( BasicProfileFolderPathAlloc < 0 )
      {
        v6 = 66;
        goto LABEL_19;
      }
      BasicProfileFolderPathAlloc = RevertHiveFileAccessRestriction(pObjectName, Name);
      if ( BasicProfileFolderPathAlloc < 0 )
      {
        v6 = 67;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v6,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmgr.cpp",
          (const char *)(unsigned int)BasicProfileFolderPathAlloc,
          phkResulta);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&pObjectName);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        v1 = BasicProfileFolderPathAlloc;
        goto LABEL_22;
      }
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&pObjectName);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  v1 = 0;
LABEL_22:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
  return v1;
}

```

## disassembly

```asm
0x180019594  push    rbp
0x180019596  push    rbx
0x180019597  push    rsi
0x180019598  push    rdi
0x180019599  push    r14
0x18001959b  lea     rbp, [rsp-1C0h]
0x1800195a3  sub     rsp, 2C0h
0x1800195aa  mov     rax, cs:__security_cookie
0x1800195b1  xor     rax, rsp
0x1800195b4  mov     [rbp+1E0h+var_30], rax
0x1800195bb  xor     esi, esi
0x1800195bd  lea     rcx, [rbp+1E0h+lpSubKey]
0x1800195c1  mov     [rbp+1E0h+lpSubKey], rsi
0x1800195c5  mov     [rbp+1E0h+var_250], rsi
0x1800195c9  mov     [rbp+1E0h+var_248], rsi
0x1800195cd  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800195d2  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800195d6  lea     rcx, [rbp+1E0h+lpSubKey]; unsigned __int16 **
0x1800195da  xor     edx, edx; int *
0x1800195dc  mov     [rbp+1E0h+var_250], r14
0x1800195e0  mov     [rbp+1E0h+var_248], r14
0x1800195e4  call    ?GetUserProfileListRootKeyName@@YAJPEAPEAGPEAH@Z; GetUserProfileListRootKeyName(ushort * *,int *)
0x1800195e9  mov     ebx, eax
0x1800195eb  test    eax, eax
0x1800195ed  jns     short loc_18001960D
0x1800195ef  mov     rcx, [rbp+1E8h]; this
0x1800195f6  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800195fd  mov     r9d, eax; char *
0x180019600  lea     edx, [rsi+22h]; void *
0x180019603  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019608  jmp     loc_18001981B
0x18001960d  xor     edx, edx
0x18001960f  mov     [rsp+2E0h+hKey], rsi
0x180019614  lea     rcx, [rsp+2E0h+hKey]
0x180019619  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001961e  mov     rdx, [rbp+1E0h+lpSubKey]; lpSubKey
0x180019622  lea     rax, [rsp+2E0h+hKey]
0x180019627  mov     r9d, 20019h; samDesired
0x18001962d  mov     [rsp+2E0h+phkResult], rax; unsigned int
0x180019632  xor     r8d, r8d; ulOptions
0x180019635  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001963c  call    cs:__imp_RegOpenKeyExW
0x180019643  nop     dword ptr [rax+rax+00h]
0x180019648  test    eax, eax
0x18001964a  jz      short loc_180019678
0x18001964c  mov     edx, 25h ; '%'; void *
0x180019651  mov     rcx, [rbp+1E8h]; this
0x180019658  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001965f  mov     r9d, eax; char *
0x180019662  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180019667  lea     rcx, [rsp+2E0h+hKey]
0x18001966c  mov     ebx, eax
0x18001966e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180019673  jmp     loc_18001981B
0x180019678  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18001967d  lea     rax, [rsp+2E0h+cSubKeys]
0x180019682  mov     [rsp+2E0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180019687  xor     r9d, r9d; lpReserved
0x18001968a  mov     [rsp+2E0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18001968f  xor     r8d, r8d; lpcchClass
0x180019692  mov     [rsp+2E0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x180019697  xor     edx, edx; lpClass
0x180019699  mov     [rsp+2E0h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x18001969e  mov     [rsp+2E0h+lpcValues], rsi; lpcValues
0x1800196a3  mov     [rsp+2E0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x1800196a8  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x1800196ad  mov     [rsp+2E0h+phkResult], rax; lpcSubKeys
0x1800196b2  mov     [rsp+2E0h+cSubKeys], esi
0x1800196b6  call    cs:__imp_RegQueryInfoKeyW
0x1800196bd  nop     dword ptr [rax+rax+00h]
0x1800196c2  test    eax, eax
0x1800196c4  jz      short loc_1800196CD
0x1800196c6  mov     edx, 29h ; ')'
0x1800196cb  jmp     short loc_180019651
0x1800196cd  xor     edx, edx; Val
0x1800196cf  lea     rcx, [rbp+1E0h+Name]; void *
0x1800196d3  mov     r8d, 208h; Size
0x1800196d9  call    memset_0
0x1800196de  mov     ebx, [rsp+2E0h+cSubKeys]
0x1800196e2  mov     [rsp+2E0h+cchName], esi
0x1800196e6  dec     ebx
0x1800196e8  test    ebx, ebx
0x1800196ea  js      loc_18001980F
0x1800196f0  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800196f5  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x1800196fa  mov     [rsp+2E0h+lpcValues], rsi; lpftLastWriteTime
0x1800196ff  lea     r8, [rbp+1E0h+Name]; lpName
0x180019703  mov     [rsp+2E0h+lpcbMaxClassLen], rsi; lpcchClass
0x180019708  mov     edx, ebx; dwIndex
0x18001970a  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rsi; lpClass
0x18001970f  mov     [rsp+2E0h+phkResult], rsi; int
0x180019714  mov     [rsp+2E0h+cchName], 104h
0x18001971c  call    cs:__imp_RegEnumKeyExW
0x180019723  nop     dword ptr [rax+rax+00h]
0x180019728  test    eax, eax
0x18001972a  jnz     loc_180019805
0x180019730  mov     rcx, [rsp+2E0h+hKey]; HKEY
0x180019735  lea     rdx, [rbp+1E0h+Name]; unsigned __int16 *
0x180019739  call    ?IsStrictHiveSecuritySet@@YA_NPEAUHKEY__@@PEBG@Z; IsStrictHiveSecuritySet(HKEY__ *,ushort const *)
0x18001973e  test    al, al
0x180019740  jz      short loc_1800196E6
0x180019742  lea     rcx, [rsp+2E0h+pObjectName]
0x180019747  mov     [rsp+2E0h+pObjectName], rsi
0x18001974c  mov     [rsp+2E0h+var_268], rsi
0x180019751  mov     [rbp+1E0h+var_260], rsi
0x180019755  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001975a  lea     r8, [rsp+2E0h+pObjectName]
0x18001975f  mov     [rsp+2E0h+var_268], r14
0x180019764  lea     rdx, [rbp+1E0h+Name]
0x180019768  mov     [rbp+1E0h+var_260], r14
0x18001976c  mov     ecx, 5
0x180019771  call    cs:__imp_GetBasicProfileFolderPathAlloc
0x180019778  nop     dword ptr [rax+rax+00h]
0x18001977d  mov     edi, eax
0x18001977f  test    eax, eax
0x180019781  js      short loc_1800197D2
0x180019783  lea     r8, ?c_szNTUserDat@@3QBGB; "ntuser.dat"
0x18001978a  lea     rdx, aS_1; "\\%s"
0x180019791  lea     rcx, [rsp+2E0h+pObjectName]
0x180019796  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x18001979b  mov     edi, eax
0x18001979d  test    eax, eax
0x18001979f  js      short loc_1800197CB
0x1800197a1  mov     rcx, [rsp+2E0h+pObjectName]; pObjectName
0x1800197a6  lea     rdx, [rbp+1E0h+Name]; unsigned __int16 *
0x1800197aa  call    ?RevertHiveFileAccessRestriction@@YAJPEBG0@Z; RevertHiveFileAccessRestriction(ushort const *,ushort const *)
0x1800197af  mov     edi, eax
0x1800197b1  test    eax, eax
0x1800197b3  js      short loc_1800197C4
0x1800197b5  lea     rcx, [rsp+2E0h+pObjectName]
0x1800197ba  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800197bf  jmp     loc_1800196E6
0x1800197c4  mov     edx, 43h ; 'C'
0x1800197c9  jmp     short loc_1800197D7
0x1800197cb  mov     edx, 42h ; 'B'
0x1800197d0  jmp     short loc_1800197D7
0x1800197d2  mov     edx, 41h ; 'A'; void *
0x1800197d7  mov     rcx, [rbp+1E8h]; this
0x1800197de  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800197e5  mov     r9d, edi; char *
0x1800197e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800197ed  lea     rcx, [rsp+2E0h+pObjectName]
0x1800197f2  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800197f7  lea     rcx, [rsp+2E0h+hKey]
0x1800197fc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180019801  mov     ebx, edi
0x180019803  jmp     short loc_18001981B
0x180019805  mov     edx, 30h ; '0'
0x18001980a  jmp     loc_180019651
0x18001980f  lea     rcx, [rsp+2E0h+hKey]
0x180019814  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180019819  mov     ebx, esi
0x18001981b  lea     rcx, [rbp+1E0h+lpSubKey]
0x18001981f  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180019824  mov     eax, ebx
0x180019826  mov     rcx, [rbp+1E0h+var_30]
0x18001982d  xor     rcx, rsp; StackCookie
0x180019830  call    __security_check_cookie
0x180019835  add     rsp, 2C0h
0x18001983c  pop     r14
0x18001983e  pop     rdi
0x18001983f  pop     rsi
0x180019840  pop     rbx
0x180019841  pop     rbp
0x180019842  retn
```
