# WriteUnloadTime(ushort const *)

- ea: `0x180012b14`
- end: `0x180012c97`
- name: `?WriteUnloadTime@@YAJPEBG@Z`
- size: `387`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180008fa0`

## callees

- `0x18000d2c0`
- `0x18000e1a0`
- `0x180012b14`
- `0x1800130d0`
- `0x180013770`
- `0x180014b4c`
- `0x180030ad0`
- `0x180031060`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012bb3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012bb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012bea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012bea`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012c07`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012c07`

## string_xrefs

- `0x180012b6a`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180012bc7`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180012c38`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
__int64 __fastcall WriteUnloadTime(LPCWCH lpString1)
{
  int ProfileListKeyNameFromSid; // eax
  unsigned int v3; // ebx
  unsigned int v4; // eax
  int v5; // eax
  __int64 v6; // rdx
  int phkResult; // [rsp+20h] [rbp-30h]
  unsigned int phkResulta; // [rsp+20h] [rbp-30h]
  LPCWSTR lpSubKey; // [rsp+30h] [rbp-20h] BYREF
  __int64 v11; // [rsp+38h] [rbp-18h]
  __int64 v12; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  HKEY hKey; // [rsp+68h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp+20h] BYREF

  lpSubKey = 0;
  v11 = 0;
  v12 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
  v11 = -1;
  v12 = -1;
  ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(lpString1, (unsigned __int16 **)&lpSubKey, 0);
  v3 = ProfileListKeyNameFromSid;
  if ( ProfileListKeyNameFromSid >= 0 )
  {
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xF003Fu, &hKey);
    if ( v4 )
    {
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x120,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
             (const char *)v4,
             phkResulta);
      if ( hKey )
        RegCloseKey(hKey);
    }
    else
    {
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v5 = SHRegSetDWORD(hKey, 0, L"LocalProfileUnloadTimeLow", SystemTimeAsFileTime.dwLowDateTime);
      v3 = v5;
      if ( v5 >= 0 )
      {
        v5 = SHRegSetDWORD(hKey, 0, L"LocalProfileUnloadTimeHigh", SystemTimeAsFileTime.dwHighDateTime);
        v3 = v5;
        if ( v5 >= 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          v3 = 0;
          goto LABEL_12;
        }
        v6 = 293;
      }
      else
      {
        v6 = 292;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v5,
        phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11D,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)ProfileListKeyNameFromSid,
      phkResult);
  }
LABEL_12:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
  return v3;
}

```

## disassembly

```asm
0x180012b14  mov     [rsp-8+arg_0], rbx
0x180012b19  push    rbp
0x180012b1a  mov     rbp, rsp
0x180012b1d  sub     rsp, 50h
0x180012b21  mov     rbx, rcx
0x180012b24  mov     [rbp+lpSubKey], 0
0x180012b2c  lea     rcx, [rbp+lpSubKey]
0x180012b30  mov     [rbp+var_18], 0
0x180012b38  mov     [rbp+var_10], 0
0x180012b40  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180012b45  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012b49  lea     rdx, [rbp+lpSubKey]; unsigned __int16 **
0x180012b4d  xor     r8d, r8d; int *
0x180012b50  mov     [rbp+var_18], rax
0x180012b54  mov     rcx, rbx; lpString1
0x180012b57  mov     [rbp+var_10], rax
0x180012b5b  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x180012b60  mov     ebx, eax
0x180012b62  test    eax, eax
0x180012b64  jns     short loc_180012B83
0x180012b66  mov     rcx, [rbp+8]; this
0x180012b6a  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180012b71  mov     r9d, eax; char *
0x180012b74  mov     edx, 11Dh; void *
0x180012b79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012b7e  jmp     loc_180012C80
0x180012b83  xor     edx, edx
0x180012b85  mov     [rbp+hKey], 0
0x180012b8d  lea     rcx, [rbp+hKey]
0x180012b91  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180012b96  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180012b9a  lea     rax, [rbp+hKey]
0x180012b9e  mov     r9d, 0F003Fh; samDesired
0x180012ba4  mov     qword ptr [rsp+50h+phkResult], rax; int
0x180012ba9  xor     r8d, r8d; ulOptions
0x180012bac  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012bb3  call    cs:__imp_RegOpenKeyExW
0x180012bba  nop     dword ptr [rax+rax+00h]
0x180012bbf  test    eax, eax
0x180012bc1  jz      short loc_180012BFB
0x180012bc3  mov     rcx, [rbp+8]; this
0x180012bc7  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180012bce  mov     r9d, eax; char *
0x180012bd1  mov     edx, 120h; void *
0x180012bd6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180012bdb  mov     rcx, [rbp+hKey]; hKey
0x180012bdf  mov     ebx, eax
0x180012be1  test    rcx, rcx
0x180012be4  jz      loc_180012C80
0x180012bea  call    cs:__imp_RegCloseKey
0x180012bf1  nop     dword ptr [rax+rax+00h]
0x180012bf6  jmp     loc_180012C80
0x180012bfb  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180012bff  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180012c07  call    cs:__imp_GetSystemTimeAsFileTime
0x180012c0e  nop     dword ptr [rax+rax+00h]
0x180012c13  mov     r9d, [rbp+SystemTimeAsFileTime.dwLowDateTime]; unsigned int
0x180012c17  lea     r8, aLocalprofileun; "LocalProfileUnloadTimeLow"
0x180012c1e  mov     rcx, [rbp+hKey]; HKEY
0x180012c22  xor     edx, edx; unsigned __int16 *
0x180012c24  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180012c29  mov     ebx, eax
0x180012c2b  test    eax, eax
0x180012c2d  jns     short loc_180012C52
0x180012c2f  mov     edx, 124h; void *
0x180012c34  mov     rcx, [rbp+8]; this
0x180012c38  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180012c3f  mov     r9d, eax; char *
0x180012c42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012c47  lea     rcx, [rbp+hKey]
0x180012c4b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180012c50  jmp     short loc_180012C80
0x180012c52  mov     r9d, [rbp+SystemTimeAsFileTime.dwHighDateTime]; unsigned int
0x180012c56  lea     r8, aLocalprofileun_0; "LocalProfileUnloadTimeHigh"
0x180012c5d  mov     rcx, [rbp+hKey]; HKEY
0x180012c61  xor     edx, edx; unsigned __int16 *
0x180012c63  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180012c68  mov     ebx, eax
0x180012c6a  test    eax, eax
0x180012c6c  jns     short loc_180012C75
0x180012c6e  mov     edx, 125h
0x180012c73  jmp     short loc_180012C34
0x180012c75  lea     rcx, [rbp+hKey]
0x180012c79  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180012c7e  xor     ebx, ebx
0x180012c80  lea     rcx, [rbp+lpSubKey]
0x180012c84  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180012c89  mov     eax, ebx
0x180012c8b  mov     rbx, [rsp+50h+arg_0]
0x180012c90  add     rsp, 50h
0x180012c94  pop     rbp
0x180012c95  retn
```
