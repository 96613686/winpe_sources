# WlanInfo::EnumProfiles(void)

- ea: `0x18003c818`
- end: `0x18003cd1d`
- name: `?EnumProfiles@WlanInfo@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `1285`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x18000f888`

## callees

- `0x18000f388`
- `0x18000f700`
- `0x1800100d8`
- `0x180010124`
- `0x180011614`
- `0x1800120d0`
- `0x180012f40`
- `0x18002a3e4`
- `0x18003a37c`
- `0x18003bfb0`
- `0x18003c014`
- `0x18003c818`
- `0x18003de20`

## import_xrefs

- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfileSsidList` at `0x18003caac`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfileSsidList` at `0x18003caac`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfileIndex` at `0x18003ca7a`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfileIndex` at `0x18003ca7a`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanEnumInterfaces` at `0x18003c8c4`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanEnumInterfaces` at `0x18003c8c4`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanUtf8SsidToDisplayName` at `0x18003cbc1`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanUtf8SsidToDisplayName` at `0x18003cbc1`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x18003c87f`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x18003c87f`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfile` at `0x18003ca4d`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfile` at `0x18003ca4d`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfileList` at `0x18003c9c1`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfileList` at `0x18003c9c1`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18003cc1a`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18003cc2e`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18003cc5a`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18003cc7e`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18003cc1a`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18003cc2e`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18003cc5a`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18003cc7e`

## string_xrefs

- `0x18003c893`: `onecore\net\netprofiles\service\src\netshnlmplugin\wlaninfomanager.cpp`
- `0x18003c8d8`: `onecore\net\netprofiles\service\src\netshnlmplugin\wlaninfomanager.cpp`
- `0x18003ccb7`: `onecore\net\netprofiles\service\src\netshnlmplugin\wlaninfomanager.cpp`
- `0x18003cccc`: `onecore\net\netprofiles\service\src\netshnlmplugin\wlaninfomanager.cpp`
- `0x18003cce1`: `onecore\net\netprofiles\service\src\netshnlmplugin\wlaninfomanager.cpp`
- `0x18003ccf6`: `onecore\net\netprofiles\service\src\netshnlmplugin\wlaninfomanager.cpp`
- `0x18003cd0b`: `onecore\net\netprofiles\service\src\netshnlmplugin\wlaninfomanager.cpp`
- `0x18003cb47`: `\n   >>>>>> WLAN Profile for Network %ws [%u] <<<<<< \n      ProfileName: %ws\n      Flags: %u\n      ProfileFlags: %u\n      GrantedAccess: %u\n      ProfileXml:\n%ws\n      ProfileIndex: %u\n      Ssid Header:\n        Size: %u\n        Type: %u\n        Revision: %u\n`
- `0x18003cbdd`: `      Ssid String [%u]: %ws\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall WlanInfo::EnumProfiles(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  DWORD v3; // eax
  DWORD v4; // eax
  unsigned int v5; // esi
  char *i; // rdx
  const GUID *v7; // r14
  __int64 v8; // rax
  DWORD ProfileList; // eax
  unsigned int v10; // ebx
  char *v11; // rdx
  const WCHAR *v12; // rbx
  DWORD Profile; // eax
  unsigned int ProfileIndex; // eax
  unsigned int ProfileSsidList; // eax
  __int64 v16; // rax
  unsigned int v17; // esi
  char *j; // rdx
  unsigned int v19; // eax
  PVOID v20; // rcx
  unsigned int pstrProfileXml; // [rsp+20h] [rbp-E0h]
  unsigned int pstrProfileXmla; // [rsp+20h] [rbp-E0h]
  unsigned int pstrProfileXmlb; // [rsp+20h] [rbp-E0h]
  unsigned int v25; // [rsp+70h] [rbp-90h]
  int v26; // [rsp+74h] [rbp-8Ch]
  PVOID *p_pMemory; // [rsp+78h] [rbp-88h] BYREF
  PWLAN_INTERFACE_INFO_LIST ppInterfaceList; // [rsp+80h] [rbp-80h] BYREF
  char v29; // [rsp+88h] [rbp-78h]
  int v30; // [rsp+98h] [rbp-68h]
  int v31; // [rsp+9Ch] [rbp-64h]
  unsigned int v32[2]; // [rsp+A0h] [rbp-60h]
  const GUID *v33; // [rsp+A8h] [rbp-58h]
  __int64 v34; // [rsp+B0h] [rbp-50h]
  _BYTE v35[32]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v36; // [rsp+D8h] [rbp-28h]
  _BYTE v37[32]; // [rsp+E0h] [rbp-20h] BYREF
  int v38; // [rsp+100h] [rbp+0h] BYREF
  DWORD pdwGrantedAccess; // [rsp+104h] [rbp+4h] BYREF
  DWORD pdwFlags; // [rsp+108h] [rbp+8h] BYREF
  PVOID pMemory; // [rsp+110h] [rbp+10h] BYREF
  PVOID v42; // [rsp+118h] [rbp+18h] BYREF
  HANDLE phClientHandle; // [rsp+120h] [rbp+20h] BYREF
  PVOID v44; // [rsp+128h] [rbp+28h] BYREF
  PVOID v45; // [rsp+130h] [rbp+30h] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+138h] [rbp+38h] BYREF
  int v47; // [rsp+13Ch] [rbp+3Ch] BYREF
  _BYTE v48[512]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+298h]

  v2 = a2;
  v34 = a2;
  v36 = a2;
  std::wstring::wstring(a2);
  v30 = 1;
  phClientHandle = (HANDLE)-1LL;
  pdwNegotiatedVersion = 0;
  v3 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
  if ( v3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x42D,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\wlaninfomanager.cpp",
      (const char *)v3,
      pstrProfileXml);
  v45 = 0;
  p_pMemory = &v45;
  ppInterfaceList = 0;
  v29 = 1;
  v4 = WlanEnumInterfaces(phClientHandle, 0, &ppInterfaceList);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x431,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\wlaninfomanager.cpp",
      (const char *)v4,
      pstrProfileXml);
  wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>((__int64)&p_pMemory);
  v5 = 0;
  v26 = 0;
  for ( i = (char *)v45; v5 < *(_DWORD *)v45; i = (char *)v45 )
  {
    v7 = (const GUID *)&i[532 * v5 + 8];
    v33 = v7;
    ToString(v35, &v7[33]);
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    ToString(v37, v7);
    v8 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    wil::str_printf<std::wstring>(
      (__int64)&p_pMemory,
      (__int64)L"\n"
                " >>>>>> WLAN Interface Info [%u] <<<<<< \n"
                "    InterfaceGuid: %ws\n"
                "    Description: %ws\n"
                "    State: %ws\n",
      v5,
      v8);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)&p_pMemory);
    std::wstring::_Tidy_deallocate((__int64)v37);
    std::wstring::_Tidy_deallocate((__int64)v35);
    v44 = 0;
    p_pMemory = &v44;
    ppInterfaceList = 0;
    v29 = 1;
    ProfileList = WlanGetProfileList(phClientHandle, v7, 0, (PWLAN_PROFILE_INFO_LIST *)&ppInterfaceList);
    if ( ProfileList )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x442,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\wlaninfomanager.cpp",
        (const char *)ProfileList,
        (_DWORD)v7 + 16);
    wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>((__int64)&p_pMemory);
    v10 = 0;
    v25 = 0;
    v11 = (char *)v44;
    if ( *(_DWORD *)v44 )
    {
      do
      {
        v12 = (const WCHAR *)&v11[516 * v10 + 8];
        *(_QWORD *)v32 = v12;
        v42 = 0;
        pdwFlags = 0;
        pdwGrantedAccess = 0;
        p_pMemory = &v42;
        ppInterfaceList = 0;
        v29 = 1;
        Profile = WlanGetProfile(phClientHandle, v7, v12, 0, (LPWSTR *)&ppInterfaceList, &pdwFlags, &pdwGrantedAccess);
        if ( Profile )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x451,
            (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\wlaninfomanager.cpp",
            (const char *)Profile,
            pstrProfileXmla);
        wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>((__int64)&p_pMemory);
        v38 = 0;
        ProfileIndex = WlanGetProfileIndex(v7, v12, &v38);
        if ( ProfileIndex )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x454,
            (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\wlaninfomanager.cpp",
            (const char *)ProfileIndex,
            pstrProfileXmla);
        pMemory = 0;
        p_pMemory = &pMemory;
        ppInterfaceList = 0;
        v29 = 1;
        ProfileSsidList = WlanGetProfileSsidList(v42, &ppInterfaceList);
        if ( ProfileSsidList )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x457,
            (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\wlaninfomanager.cpp",
            (const char *)ProfileSsidList,
            pstrProfileXmla);
        wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>((__int64)&p_pMemory);
        v31 = *(_DWORD *)(*(_QWORD *)v32 + 512LL);
        ToString(v37, v33);
        v16 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
        pstrProfileXmlb = v32[0];
        wil::str_printf<std::wstring>(
          (__int64)v35,
          (__int64)L"\n"
                    "   >>>>>> WLAN Profile for Network %ws [%u] <<<<<< \n"
                    "      ProfileName: %ws\n"
                    "      Flags: %u\n"
                    "      ProfileFlags: %u\n"
                    "      GrantedAccess: %u\n"
                    "      ProfileXml:\n"
                    "%ws\n"
                    "      ProfileIndex: %u\n"
                    "      Ssid Header:\n"
                    "        Size: %u\n"
                    "        Type: %u\n"
                    "        Revision: %u\n",
          v16,
          v25);
        v2 = v34;
        std::wstring::append();
        std::wstring::_Tidy_deallocate((__int64)v35);
        std::wstring::_Tidy_deallocate((__int64)v37);
        v47 = 256;
        memset_0(v48, 0, sizeof(v48));
        v17 = 0;
        for ( j = (char *)pMemory; v17 < *((_DWORD *)pMemory + 1); j = (char *)pMemory )
        {
          v19 = WlanUtf8SsidToDisplayName(&j[32 * v17 + 12 + 4 * v17], 1, v48, &v47);
          if ( v19 )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x476,
              (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\wlaninfomanager.cpp",
              (const char *)v19,
              pstrProfileXmlb);
          wil::str_printf<std::wstring>((__int64)v35, (__int64)L"      Ssid String [%u]: %ws\n", v17, v48);
          std::wstring::append();
          std::wstring::_Tidy_deallocate((__int64)v35);
          ++v17;
        }
        pMemory = 0;
        if ( j )
          WlanFreeMemory(j);
        v20 = v42;
        v42 = 0;
        if ( v20 )
          WlanFreeMemory(v20);
        v10 = v25 + 1;
        v25 = v10;
        v11 = (char *)v44;
        v7 = v33;
      }
      while ( v10 < *(_DWORD *)v44 );
      v5 = v26;
    }
    v44 = 0;
    if ( v11 )
      WlanFreeMemory(v11);
    v26 = ++v5;
  }
  v45 = 0;
  if ( i )
    WlanFreeMemory(i);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWlanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWlanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(&phClientHandle);
  return v2;
}

```

## disassembly

```asm
0x18003c818  push    rbp
0x18003c81a  push    rbx
0x18003c81b  push    rsi
0x18003c81c  push    rdi
0x18003c81d  push    r12
0x18003c81f  push    r13
0x18003c821  push    r14
0x18003c823  push    r15
0x18003c825  lea     rbp, [rsp-258h]
0x18003c82d  sub     rsp, 358h
0x18003c834  mov     rax, cs:__security_cookie
0x18003c83b  xor     rax, rsp
0x18003c83e  mov     [rbp+290h+var_50], rax
0x18003c845  mov     rdi, rdx
0x18003c848  mov     [rbp+290h+var_2E0], rdx
0x18003c84c  mov     [rbp+290h+var_2B8], rdx
0x18003c850  xor     r15d, r15d
0x18003c853  mov     [rbp+290h+var_2F8], r15d
0x18003c857  mov     rcx, rdx
0x18003c85a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003c85f  mov     [rbp+290h+var_2F8], 1
0x18003c866  mov     [rbp+290h+phClientHandle], 0FFFFFFFFFFFFFFFFh
0x18003c86e  mov     [rbp+290h+pdwNegotiatedVersion], r15d
0x18003c872  lea     r9, [rbp+290h+phClientHandle]; phClientHandle
0x18003c876  lea     r8, [rbp+290h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18003c87a  xor     edx, edx; pReserved
0x18003c87c  lea     ecx, [rdx+2]; dwClientVersion
0x18003c87f  call    cs:__imp_WlanOpenHandle
0x18003c885  mov     rcx, [rbp+298h]; this
0x18003c88c  test    eax, eax
0x18003c88e  jz      short loc_18003C8A5
0x18003c890  mov     r9d, eax; char *
0x18003c893  lea     r8, aOnecoreNetNetp_7; "onecore\\net\\netprofiles\\service\\src"...
0x18003c89a  mov     edx, 42Dh; void *
0x18003c89f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003c8a5  mov     [rbp+290h+var_260], r15
0x18003c8a9  lea     rax, [rbp+290h+var_260]
0x18003c8ad  mov     [rsp+390h+var_318], rax
0x18003c8b2  mov     [rbp+290h+ppInterfaceList], r15
0x18003c8b6  mov     [rbp+290h+var_308], 1
0x18003c8ba  lea     r8, [rbp+290h+ppInterfaceList]; ppInterfaceList
0x18003c8be  xor     edx, edx; pReserved
0x18003c8c0  mov     rcx, [rbp+290h+phClientHandle]; hClientHandle
0x18003c8c4  call    cs:__imp_WlanEnumInterfaces
0x18003c8ca  mov     rcx, [rbp+298h]; this
0x18003c8d1  test    eax, eax
0x18003c8d3  jz      short loc_18003C8EA
0x18003c8d5  mov     r9d, eax; char *
0x18003c8d8  lea     r8, aOnecoreNetNetp_7; "onecore\\net\\netprofiles\\service\\src"...
0x18003c8df  mov     edx, 431h; void *
0x18003c8e4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003c8ea  lea     rcx, [rsp+390h+var_318]
0x18003c8ef  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_ptr@PEAXU?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>(void)
0x18003c8f4  mov     esi, r15d
0x18003c8f7  mov     [rsp+390h+var_31C], r15d
0x18003c8fc  mov     rdx, [rbp+290h+var_260]
0x18003c900  cmp     [rdx], r15d
0x18003c903  jbe     loc_18003CC72
0x18003c909  mov     eax, esi
0x18003c90b  imul    rcx, rax, 214h
0x18003c912  lea     r14, [rdx+8]
0x18003c916  add     r14, rcx
0x18003c919  mov     [rbp+290h+var_2E8], r14
0x18003c91d  lea     rdx, [r14+210h]
0x18003c924  lea     rcx, [rbp+290h+var_2D8]
0x18003c928  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBW4_WLAN_INTERFACE_STATE@@@Z; ToString(_WLAN_INTERFACE_STATE const &)
0x18003c92d  nop
0x18003c92e  mov     rcx, rax
0x18003c931  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003c936  mov     rbx, rax
0x18003c939  mov     rdx, r14
0x18003c93c  lea     rcx, [rbp+290h+var_2B0]
0x18003c940  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@@Z; ToString(_GUID const &)
0x18003c945  nop
0x18003c946  mov     rcx, rax
0x18003c949  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003c94e  mov     r9, rax
0x18003c951  lea     rax, [r14+10h]
0x18003c955  mov     [rsp+390h+pdwFlags], rbx
0x18003c95a  mov     [rsp+390h+pstrProfileXml], rax; unsigned int
0x18003c95f  mov     r8d, esi
0x18003c962  lea     rdx, aWlanInterfaceI; "\n >>>>>> WLAN Interface Info [%u] <<<<"...
0x18003c969  lea     rcx, [rsp+390h+var_318]
0x18003c96e  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18003c973  nop
0x18003c974  mov     rdx, rax
0x18003c977  mov     rcx, rdi
0x18003c97a  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18003c97f  nop
0x18003c980  lea     rcx, [rsp+390h+var_318]
0x18003c985  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c98a  nop
0x18003c98b  lea     rcx, [rbp+290h+var_2B0]
0x18003c98f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c994  nop
0x18003c995  lea     rcx, [rbp+290h+var_2D8]
0x18003c999  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c99e  mov     [rbp+290h+var_268], r15
0x18003c9a2  lea     rax, [rbp+290h+var_268]
0x18003c9a6  mov     [rsp+390h+var_318], rax
0x18003c9ab  mov     [rbp+290h+ppInterfaceList], r15
0x18003c9af  mov     [rbp+290h+var_308], 1
0x18003c9b3  lea     r9, [rbp+290h+ppInterfaceList]; ppProfileList
0x18003c9b7  xor     r8d, r8d; pReserved
0x18003c9ba  mov     rdx, r14; pInterfaceGuid
0x18003c9bd  mov     rcx, [rbp+290h+phClientHandle]; hClientHandle
0x18003c9c1  call    cs:__imp_WlanGetProfileList
0x18003c9c7  mov     rcx, [rbp+298h]; this
0x18003c9ce  test    eax, eax
0x18003c9d0  jnz     loc_18003CD08
0x18003c9d6  lea     rcx, [rsp+390h+var_318]
0x18003c9db  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_ptr@PEAXU?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>(void)
0x18003c9e0  mov     ebx, r15d
0x18003c9e3  mov     [rsp+390h+var_320], ebx
0x18003c9e7  mov     rdx, [rbp+290h+var_268]
0x18003c9eb  cmp     [rdx], r15d
0x18003c9ee  jbe     loc_18003CC4E
0x18003c9f4  mov     eax, ebx
0x18003c9f6  imul    rcx, rax, 204h
0x18003c9fd  lea     rbx, [rdx+8]
0x18003ca01  add     rbx, rcx
0x18003ca04  mov     qword ptr [rbp+290h+var_2F0], rbx
0x18003ca08  mov     [rbp+290h+var_278], r15
0x18003ca0c  mov     [rbp+290h+var_288], r15d
0x18003ca10  mov     [rbp+290h+var_28C], r15d
0x18003ca14  lea     rax, [rbp+290h+var_278]
0x18003ca18  mov     [rsp+390h+var_318], rax
0x18003ca1d  mov     [rbp+290h+ppInterfaceList], r15
0x18003ca21  mov     [rbp+290h+var_308], 1
0x18003ca25  lea     rax, [rbp+290h+var_28C]
0x18003ca29  mov     [rsp+390h+pdwGrantedAccess], rax; pdwGrantedAccess
0x18003ca2e  lea     rax, [rbp+290h+var_288]
0x18003ca32  mov     [rsp+390h+pdwFlags], rax; pdwFlags
0x18003ca37  lea     rax, [rbp+290h+ppInterfaceList]
0x18003ca3b  mov     [rsp+390h+pstrProfileXml], rax; unsigned int
0x18003ca40  xor     r9d, r9d; pReserved
0x18003ca43  mov     r8, rbx; strProfileName
0x18003ca46  mov     rdx, r14; pInterfaceGuid
0x18003ca49  mov     rcx, [rbp+290h+phClientHandle]; hClientHandle
0x18003ca4d  call    cs:__imp_WlanGetProfile
0x18003ca53  mov     rcx, [rbp+298h]; this
0x18003ca5a  test    eax, eax
0x18003ca5c  jnz     loc_18003CCF3
0x18003ca62  lea     rcx, [rsp+390h+var_318]
0x18003ca67  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_ptr@PEAXU?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>(void)
0x18003ca6c  mov     [rbp+290h+var_290], r15d
0x18003ca70  lea     r8, [rbp+290h+var_290]
0x18003ca74  mov     rdx, rbx
0x18003ca77  mov     rcx, r14
0x18003ca7a  call    cs:__imp_WlanGetProfileIndex
0x18003ca80  mov     rcx, [rbp+298h]; this
0x18003ca87  test    eax, eax
0x18003ca89  jnz     loc_18003CCDE
0x18003ca8f  mov     [rbp+290h+pMemory], r15
0x18003ca93  lea     rax, [rbp+290h+pMemory]
0x18003ca97  mov     [rsp+390h+var_318], rax
0x18003ca9c  mov     [rbp+290h+ppInterfaceList], r15
0x18003caa0  mov     [rbp+290h+var_308], 1
0x18003caa4  lea     rdx, [rbp+290h+ppInterfaceList]
0x18003caa8  mov     rcx, [rbp+290h+var_278]
0x18003caac  call    cs:__imp_WlanGetProfileSsidList
0x18003cab2  mov     rcx, [rbp+298h]; this
0x18003cab9  test    eax, eax
0x18003cabb  jnz     loc_18003CCC9
0x18003cac1  lea     rcx, [rsp+390h+var_318]
0x18003cac6  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_ptr@PEAXU?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>(void)
0x18003cacb  mov     rax, [rbp+290h+pMemory]
0x18003cacf  movzx   ebx, byte ptr [rax+1]
0x18003cad3  movzx   edi, byte ptr [rax]
0x18003cad6  movzx   esi, word ptr [rax+2]
0x18003cada  mov     r14d, [rbp+290h+var_290]
0x18003cade  mov     r15, [rbp+290h+var_278]
0x18003cae2  mov     r12d, [rbp+290h+var_28C]
0x18003cae6  mov     r13d, [rbp+290h+var_288]
0x18003caea  mov     rax, qword ptr [rbp+290h+var_2F0]
0x18003caee  mov     eax, [rax+200h]
0x18003caf4  mov     [rbp+290h+var_2F4], eax
0x18003caf7  mov     rdx, [rbp+290h+var_2E8]
0x18003cafb  lea     rcx, [rbp+290h+var_2B0]
0x18003caff  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@@Z; ToString(_GUID const &)
0x18003cb04  nop
0x18003cb05  mov     rcx, rax
0x18003cb08  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003cb0d  mov     [rsp+390h+var_330], ebx
0x18003cb11  mov     [rsp+390h+var_338], edi
0x18003cb15  mov     [rsp+390h+var_340], esi
0x18003cb19  mov     [rsp+390h+var_348], r14d
0x18003cb1e  mov     [rsp+390h+var_350], r15
0x18003cb23  mov     [rsp+390h+var_358], r12d
0x18003cb28  mov     dword ptr [rsp+390h+pdwGrantedAccess], r13d
0x18003cb2d  mov     ecx, [rbp+290h+var_2F4]
0x18003cb30  mov     dword ptr [rsp+390h+pdwFlags], ecx
0x18003cb34  mov     rcx, qword ptr [rbp+290h+var_2F0]
0x18003cb38  mov     [rsp+390h+pstrProfileXml], rcx; unsigned int
0x18003cb3d  mov     ebx, [rsp+390h+var_320]
0x18003cb41  mov     r9d, ebx
0x18003cb44  mov     r8, rax
0x18003cb47  lea     rdx, aWlanProfileFor; "\n   >>>>>> WLAN Profile for Network %w"...
0x18003cb4e  lea     rcx, [rbp+290h+var_2D8]
0x18003cb52  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18003cb57  nop
0x18003cb58  mov     rdx, rax
0x18003cb5b  mov     rdi, [rbp+290h+var_2E0]
0x18003cb5f  mov     rcx, rdi
0x18003cb62  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18003cb67  nop
0x18003cb68  lea     rcx, [rbp+290h+var_2D8]
0x18003cb6c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003cb71  nop
0x18003cb72  lea     rcx, [rbp+290h+var_2B0]
0x18003cb76  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003cb7b  mov     [rbp+290h+var_254], 100h
0x18003cb82  xor     edx, edx; Val
0x18003cb84  mov     r8d, 200h; Size
0x18003cb8a  lea     rcx, [rbp+290h+var_250]; void *
0x18003cb8e  call    memset_0
0x18003cb93  xor     r15d, r15d
0x18003cb96  mov     esi, r15d
0x18003cb99  mov     rdx, [rbp+290h+pMemory]
0x18003cb9d  cmp     [rdx+4], r15d
0x18003cba1  jbe     short loc_18003CC0E
0x18003cba3  mov     eax, esi
0x18003cba5  lea     rcx, ds:3[rax*8]
0x18003cbad  add     rcx, rax
0x18003cbb0  lea     rcx, [rdx+rcx*4]
0x18003cbb4  lea     r9, [rbp+290h+var_254]
0x18003cbb8  lea     r8, [rbp+290h+var_250]
0x18003cbbc  mov     edx, 1
0x18003cbc1  call    cs:__imp_WlanUtf8SsidToDisplayName
0x18003cbc7  mov     rcx, [rbp+298h]; this
0x18003cbce  test    eax, eax
0x18003cbd0  jnz     loc_18003CCB4
0x18003cbd6  lea     r9, [rbp+290h+var_250]
0x18003cbda  mov     r8d, esi
0x18003cbdd  lea     rdx, aSsidStringUWs; "      Ssid String [%u]: %ws\n"
0x18003cbe4  lea     rcx, [rbp+290h+var_2D8]
0x18003cbe8  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18003cbed  nop
0x18003cbee  mov     rdx, rax
0x18003cbf1  mov     rcx, rdi
0x18003cbf4  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18003cbf9  nop
0x18003cbfa  lea     rcx, [rbp+290h+var_2D8]
0x18003cbfe  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003cc03  inc     esi
0x18003cc05  mov     rdx, [rbp+290h+pMemory]
0x18003cc09  cmp     esi, [rdx+4]
0x18003cc0c  jb      short loc_18003CBA3
0x18003cc0e  mov     [rbp+290h+pMemory], r15
0x18003cc12  test    rdx, rdx
0x18003cc15  jz      short loc_18003CC21
0x18003cc17  mov     rcx, rdx; pMemory
0x18003cc1a  call    cs:__imp_WlanFreeMemory
0x18003cc20  nop
0x18003cc21  mov     rcx, [rbp+290h+var_278]; pMemory
0x18003cc25  mov     [rbp+290h+var_278], r15
0x18003cc29  test    rcx, rcx
0x18003cc2c  jz      short loc_18003CC34
0x18003cc2e  call    cs:__imp_WlanFreeMemory
0x18003cc34  inc     ebx
0x18003cc36  mov     [rsp+390h+var_320], ebx
0x18003cc3a  mov     rdx, [rbp+290h+var_268]
0x18003cc3e  cmp     ebx, [rdx]
0x18003cc40  mov     r14, [rbp+290h+var_2E8]
0x18003cc44  jb      loc_18003C9F4
0x18003cc4a  mov     esi, [rsp+390h+var_31C]
0x18003cc4e  mov     [rbp+290h+var_268], r15
0x18003cc52  test    rdx, rdx
0x18003cc55  jz      short loc_18003CC60
0x18003cc57  mov     rcx, rdx; pMemory
0x18003cc5a  call    cs:__imp_WlanFreeMemory
0x18003cc60  inc     esi
0x18003cc62  mov     [rsp+390h+var_31C], esi
0x18003cc66  mov     rdx, [rbp+290h+var_260]
0x18003cc6a  cmp     esi, [rdx]
0x18003cc6c  jb      loc_18003C909
0x18003cc72  mov     [rbp+290h+var_260], r15
0x18003cc76  test    rdx, rdx
0x18003cc79  jz      short loc_18003CC85
0x18003cc7b  mov     rcx, rdx; pMemory
0x18003cc7e  call    cs:__imp_WlanFreeMemory
0x18003cc84  nop
0x18003cc85  lea     rcx, [rbp+290h+phClientHandle]
0x18003cc89  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWlanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWlanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWlanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(void)
0x18003cc8e  mov     rax, rdi
0x18003cc91  mov     rcx, [rbp+290h+var_50]
0x18003cc98  xor     rcx, rsp; StackCookie
0x18003cc9b  call    __security_check_cookie
0x18003cca0  add     rsp, 358h
0x18003cca7  pop     r15
0x18003cca9  pop     r14
0x18003ccab  pop     r13
0x18003ccad  pop     r12
0x18003ccaf  pop     rdi
0x18003ccb0  pop     rsi
0x18003ccb1  pop     rbx
0x18003ccb2  pop     rbp
0x18003ccb3  retn
0x18003ccb4  mov     r9d, eax; char *
0x18003ccb7  lea     r8, aOnecoreNetNetp_7; "onecore\\net\\netprofiles\\service\\src"...
  ... truncated ...
```
