# WlanInfo::EnumNetworks(void)

- ea: `0x18003c0b8`
- end: `0x18003c812`
- name: `?EnumNetworks@WlanInfo@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `1882`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000f888`

## callees

- `0x18000c650`
- `0x18000ef08`
- `0x18000f388`
- `0x18000f700`
- `0x1800100d8`
- `0x180010124`
- `0x180011614`
- `0x1800120d0`
- `0x180012f40`
- `0x18002a3e4`
- `0x18003a37c`
- `0x18003bc34`
- `0x18003bf38`
- `0x18003bfb0`
- `0x18003c014`
- `0x18003c0b8`
- `0x18003d25c`
- `0x18003de20`

## import_xrefs

- `ext-ms-win-networking-wlanapi-l1-1-0!WlanEnumInterfaces` at `0x18003c185`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanEnumInterfaces` at `0x18003c185`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x18003c12c`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x18003c12c`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18003c34f`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18003c4d1`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18003c73d`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18003c79a`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18003c34f`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18003c4d1`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18003c73d`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18003c79a`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetAvailableNetworkList` at `0x18003c232`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetAvailableNetworkList` at `0x18003c385`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetAvailableNetworkList` at `0x18003c508`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetAvailableNetworkList` at `0x18003c232`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetAvailableNetworkList` at `0x18003c385`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetAvailableNetworkList` at `0x18003c508`

## string_xrefs

- `0x18003c140`: `onecore\net\netprofiles\service\src\netshnlmplugin\wlaninfomanager.cpp`
- `0x18003c199`: `onecore\net\netprofiles\service\src\netshnlmplugin\wlaninfomanager.cpp`
- `0x18003c7d6`: `onecore\net\netprofiles\service\src\netshnlmplugin\wlaninfomanager.cpp`
- `0x18003c7eb`: `onecore\net\netprofiles\service\src\netshnlmplugin\wlaninfomanager.cpp`
- `0x18003c800`: `onecore\net\netprofiles\service\src\netshnlmplugin\wlaninfomanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall WlanInfo::EnumNetworks(__int64 a1, __int64 a2)
{
  DWORD v3; // eax
  DWORD v4; // eax
  unsigned int v5; // r14d
  char *i; // rdx
  const GUID *v7; // r15
  DWORD AvailableNetworkList; // eax
  unsigned int v9; // edi
  char *j; // rdx
  char *v11; // rbx
  _OWORD *v12; // rcx
  __int64 v13; // rax
  DWORD v14; // eax
  unsigned int v15; // edi
  char *k; // rdx
  char *v17; // rbx
  _OWORD *v18; // rcx
  __int64 v19; // rax
  DWORD v20; // eax
  unsigned int v21; // edi
  char *m; // rax
  char *v23; // rbx
  _OWORD *v24; // rcx
  __int64 v25; // rax
  int v26; // ecx
  __int64 v27; // rbx
  __int64 v28; // rax
  unsigned int v29; // edi
  PWLAN_INTERFACE_INFO_LIST v30; // rbx
  PWLAN_INTERFACE_INFO_LIST v31; // r15
  PVOID v32; // rcx
  unsigned int ppAvailableNetworkList; // [rsp+20h] [rbp-E0h]
  unsigned int ppAvailableNetworkLista; // [rsp+20h] [rbp-E0h]
  unsigned int ppAvailableNetworkListb; // [rsp+20h] [rbp-E0h]
  unsigned int ppAvailableNetworkListc; // [rsp+20h] [rbp-E0h]
  __int64 v38; // [rsp+30h] [rbp-D0h] BYREF
  PVOID *p_pMemory; // [rsp+38h] [rbp-C8h] BYREF
  PWLAN_AVAILABLE_NETWORK_LIST v40; // [rsp+40h] [rbp-C0h] BYREF
  char v41; // [rsp+48h] [rbp-B8h]
  int v42; // [rsp+58h] [rbp-A8h]
  __int64 v43; // [rsp+60h] [rbp-A0h]
  _BYTE v44[32]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v45[40]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v46[628]; // [rsp+B0h] [rbp-50h] BYREF
  int v47; // [rsp+324h] [rbp+224h]
  PVOID pMemory; // [rsp+330h] [rbp+230h] BYREF
  HANDLE phClientHandle; // [rsp+338h] [rbp+238h] BYREF
  PWLAN_INTERFACE_INFO_LIST ppInterfaceList[2]; // [rsp+340h] [rbp+240h] BYREF
  __int64 v51; // [rsp+350h] [rbp+250h]
  PVOID v52; // [rsp+358h] [rbp+258h] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+360h] [rbp+260h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+2B8h]

  v43 = a2;
  std::wstring::wstring(a2);
  v42 = 1;
  phClientHandle = (HANDLE)-1LL;
  pdwNegotiatedVersion = 0;
  v3 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
  if ( v3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x3BC,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\wlaninfomanager.cpp",
      (const char *)v3,
      ppAvailableNetworkList);
  v52 = 0;
  ppInterfaceList[0] = (PWLAN_INTERFACE_INFO_LIST)&v52;
  ppInterfaceList[1] = 0;
  LOBYTE(v51) = 1;
  v4 = WlanEnumInterfaces(phClientHandle, 0, &ppInterfaceList[1]);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x3C0,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\wlaninfomanager.cpp",
      (const char *)v4,
      ppAvailableNetworkList);
  wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>((__int64)ppInterfaceList);
  v5 = 0;
  for ( i = (char *)v52; v5 < *(_DWORD *)v52; i = (char *)v52 )
  {
    v7 = (const GUID *)&i[532 * v5 + 8];
    *(_OWORD *)ppInterfaceList = 0;
    v51 = 0;
    std::vector<WlanAvailableNetworks>::vector<WlanAvailableNetworks>(ppInterfaceList);
    pMemory = 0;
    p_pMemory = &pMemory;
    v40 = 0;
    v41 = 1;
    AvailableNetworkList = WlanGetAvailableNetworkList(phClientHandle, v7, 0, 0, &v40);
    if ( AvailableNetworkList )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x3CF,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\wlaninfomanager.cpp",
        (const char *)AvailableNetworkList,
        ppAvailableNetworkLista);
    wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>((__int64)&p_pMemory);
    v9 = 0;
    for ( j = (char *)pMemory; v9 < *(_DWORD *)pMemory; j = (char *)pMemory )
    {
      v11 = &j[628 * v9 + 8];
      memset_0(v46, 0, sizeof(v46));
      v47 = 0;
      v12 = v46;
      v13 = 4;
      do
      {
        *v12 = *(_OWORD *)v11;
        v12[1] = *((_OWORD *)v11 + 1);
        v12[2] = *((_OWORD *)v11 + 2);
        v12[3] = *((_OWORD *)v11 + 3);
        v12[4] = *((_OWORD *)v11 + 4);
        v12[5] = *((_OWORD *)v11 + 5);
        v12[6] = *((_OWORD *)v11 + 6);
        v12[7] = *((_OWORD *)v11 + 7);
        v12 += 8;
        v11 += 128;
        --v13;
      }
      while ( v13 );
      *v12 = *(_OWORD *)v11;
      v12[1] = *((_OWORD *)v11 + 1);
      v12[2] = *((_OWORD *)v11 + 2);
      v12[3] = *((_OWORD *)v11 + 3);
      v12[4] = *((_OWORD *)v11 + 4);
      v12[5] = *((_OWORD *)v11 + 5);
      v12[6] = *((_OWORD *)v11 + 6);
      *((_DWORD *)v12 + 28) = *((_DWORD *)v11 + 28);
      std::vector<WlanAvailableNetworks>::_Emplace_one_at_back<WlanAvailableNetworks const &>(ppInterfaceList, v46);
      ++v9;
    }
    pMemory = 0;
    if ( j )
      WlanFreeMemory(j);
    p_pMemory = &pMemory;
    v40 = 0;
    v41 = 1;
    v14 = WlanGetAvailableNetworkList(phClientHandle, v7, 1u, 0, &v40);
    if ( v14 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x3DF,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\wlaninfomanager.cpp",
        (const char *)v14,
        ppAvailableNetworkListb);
    wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>((__int64)&p_pMemory);
    v15 = 0;
    for ( k = (char *)pMemory; v15 < *(_DWORD *)pMemory; k = (char *)pMemory )
    {
      v17 = &k[628 * v15 + 8];
      memset_0(v46, 0, sizeof(v46));
      v47 = 1;
      v18 = v46;
      v19 = 4;
      do
      {
        *v18 = *(_OWORD *)v17;
        v18[1] = *((_OWORD *)v17 + 1);
        v18[2] = *((_OWORD *)v17 + 2);
        v18[3] = *((_OWORD *)v17 + 3);
        v18[4] = *((_OWORD *)v17 + 4);
        v18[5] = *((_OWORD *)v17 + 5);
        v18[6] = *((_OWORD *)v17 + 6);
        v18[7] = *((_OWORD *)v17 + 7);
        v18 += 8;
        v17 += 128;
        --v19;
      }
      while ( v19 );
      *v18 = *(_OWORD *)v17;
      v18[1] = *((_OWORD *)v17 + 1);
      v18[2] = *((_OWORD *)v17 + 2);
      v18[3] = *((_OWORD *)v17 + 3);
      v18[4] = *((_OWORD *)v17 + 4);
      v18[5] = *((_OWORD *)v17 + 5);
      v18[6] = *((_OWORD *)v17 + 6);
      *((_DWORD *)v18 + 28) = *((_DWORD *)v17 + 28);
      v38 = 0;
      std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<WlanAvailableNetworks>>>,WlanAvailableNetworks>(
        &v38,
        ppInterfaceList[0],
        ppInterfaceList[1],
        v46);
      if ( (PWLAN_INTERFACE_INFO_LIST)v38 == ppInterfaceList[1] )
        std::vector<WlanAvailableNetworks>::_Emplace_one_at_back<WlanAvailableNetworks const &>(ppInterfaceList, v46);
      ++v15;
    }
    pMemory = 0;
    if ( k )
      WlanFreeMemory(k);
    p_pMemory = &pMemory;
    v40 = 0;
    v41 = 1;
    v20 = WlanGetAvailableNetworkList(phClientHandle, v7, 2u, 0, &v40);
    if ( v20 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x3F7,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\wlaninfomanager.cpp",
        (const char *)v20,
        ppAvailableNetworkListc);
    wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>((__int64)&p_pMemory);
    v21 = 0;
    for ( m = (char *)pMemory; v21 < *(_DWORD *)pMemory; m = (char *)pMemory )
    {
      v23 = &m[628 * v21 + 8];
      memset_0(v46, 0, sizeof(v46));
      v47 = 2;
      v24 = v46;
      v25 = 4;
      do
      {
        *v24 = *(_OWORD *)v23;
        v24[1] = *((_OWORD *)v23 + 1);
        v24[2] = *((_OWORD *)v23 + 2);
        v24[3] = *((_OWORD *)v23 + 3);
        v24[4] = *((_OWORD *)v23 + 4);
        v24[5] = *((_OWORD *)v23 + 5);
        v24[6] = *((_OWORD *)v23 + 6);
        v24[7] = *((_OWORD *)v23 + 7);
        v24 += 8;
        v23 += 128;
        --v25;
      }
      while ( v25 );
      *v24 = *(_OWORD *)v23;
      v24[1] = *((_OWORD *)v23 + 1);
      v24[2] = *((_OWORD *)v23 + 2);
      v24[3] = *((_OWORD *)v23 + 3);
      v24[4] = *((_OWORD *)v23 + 4);
      v24[5] = *((_OWORD *)v23 + 5);
      v24[6] = *((_OWORD *)v23 + 6);
      *((_DWORD *)v24 + 28) = *((_DWORD *)v23 + 28);
      v38 = 0;
      std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<WlanAvailableNetworks>>>,WlanAvailableNetworks>(
        &v38,
        ppInterfaceList[0],
        ppInterfaceList[1],
        v46);
      if ( (PWLAN_INTERFACE_INFO_LIST)v38 == ppInterfaceList[1] )
      {
        std::vector<WlanAvailableNetworks>::_Emplace_one_at_back<WlanAvailableNetworks const &>(ppInterfaceList, v46);
      }
      else
      {
        v26 = *(_DWORD *)(v38 + 628);
        if ( (v26 & 1) != 0 )
          *(_DWORD *)(v38 + 628) = v26 | 2;
      }
      ++v21;
    }
    ToString(v44, &v7[33]);
    v27 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    ToString(v45, v7);
    v28 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    wil::str_printf<std::wstring>(
      (__int64)&p_pMemory,
      (__int64)L"\n"
                " >>>>>> WLAN Interface Info [%u] <<<<<< \n"
                "    InterfaceGuid: %ws\n"
                "    Description: %ws\n"
                "    State: %ws\n",
      v5,
      v28,
      &v7[1],
      v27);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)&p_pMemory);
    std::wstring::_Tidy_deallocate((__int64)v45);
    std::wstring::_Tidy_deallocate((__int64)v44);
    v29 = 0;
    v30 = ppInterfaceList[0];
    v31 = ppInterfaceList[1];
    while ( v30 != v31 )
    {
      ToString(v44, v30, v29);
      std::wstring::append();
      std::wstring::_Tidy_deallocate((__int64)v44);
      ++v29;
      v30 = (PWLAN_INTERFACE_INFO_LIST)((char *)v30 + 632);
    }
    v32 = pMemory;
    pMemory = 0;
    if ( v32 )
      WlanFreeMemory(v32);
    if ( ppInterfaceList[0] )
      std::_Deallocate<16>(ppInterfaceList[0], 8 * ((signed __int64)(v51 - (unsigned __int64)ppInterfaceList[0]) >> 3));
    ++v5;
  }
  v52 = 0;
  if ( i )
    WlanFreeMemory(i);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWlanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWlanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(&phClientHandle);
  return a2;
}

```

## disassembly

```asm
0x18003c0b8  push    rbp
0x18003c0ba  push    rbx
0x18003c0bb  push    rsi
0x18003c0bc  push    rdi
0x18003c0bd  push    r12
0x18003c0bf  push    r13
0x18003c0c1  push    r14
0x18003c0c3  push    r15
0x18003c0c5  lea     rbp, [rsp-278h]
0x18003c0cd  sub     rsp, 378h
0x18003c0d4  mov     rax, cs:__security_cookie
0x18003c0db  xor     rax, rsp
0x18003c0de  mov     [rbp+2B0h+var_48], rax
0x18003c0e5  mov     rsi, rdx
0x18003c0e8  mov     [rsp+3B0h+var_350], rdx
0x18003c0ed  xor     r12d, r12d
0x18003c0f0  mov     [rsp+3B0h+var_358], r12d
0x18003c0f5  mov     rcx, rdx
0x18003c0f8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003c0fd  lea     r13d, [r12+1]
0x18003c102  mov     [rsp+3B0h+var_358], r13d
0x18003c107  mov     [rbp+2B0h+phClientHandle], 0FFFFFFFFFFFFFFFFh
0x18003c112  mov     [rbp+2B0h+pdwNegotiatedVersion], r12d
0x18003c119  lea     r9, [rbp+2B0h+phClientHandle]; phClientHandle
0x18003c120  lea     r8, [rbp+2B0h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18003c127  xor     edx, edx; pReserved
0x18003c129  lea     ecx, [rdx+2]; dwClientVersion
0x18003c12c  call    cs:__imp_WlanOpenHandle
0x18003c132  mov     rcx, [rbp+2B8h]; this
0x18003c139  test    eax, eax
0x18003c13b  jz      short loc_18003C152
0x18003c13d  mov     r9d, eax; char *
0x18003c140  lea     r8, aOnecoreNetNetp_7; "onecore\\net\\netprofiles\\service\\src"...
0x18003c147  mov     edx, 3BCh; void *
0x18003c14c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003c152  mov     [rbp+2B0h+var_58], r12
0x18003c159  lea     rax, [rbp+2B0h+var_58]
0x18003c160  mov     [rbp+2B0h+ppInterfaceList], rax
0x18003c167  mov     [rbp+2B0h+ppInterfaceList+8], r12
0x18003c16e  mov     byte ptr [rbp+2B0h+var_60], r13b
0x18003c175  lea     r8, [rbp+2B0h+ppInterfaceList+8]; ppInterfaceList
0x18003c17c  xor     edx, edx; pReserved
0x18003c17e  mov     rcx, [rbp+2B0h+phClientHandle]; hClientHandle
0x18003c185  call    cs:__imp_WlanEnumInterfaces
0x18003c18b  mov     rcx, [rbp+2B8h]; this
0x18003c192  test    eax, eax
0x18003c194  jz      short loc_18003C1AB
0x18003c196  mov     r9d, eax; char *
0x18003c199  lea     r8, aOnecoreNetNetp_7; "onecore\\net\\netprofiles\\service\\src"...
0x18003c1a0  mov     edx, 3C0h; void *
0x18003c1a5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003c1ab  lea     rcx, [rbp+2B0h+ppInterfaceList]
0x18003c1b2  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_ptr@PEAXU?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>(void)
0x18003c1b7  mov     r14d, r12d
0x18003c1ba  mov     rdx, [rbp+2B0h+var_58]
0x18003c1c1  cmp     [rdx], r12d
0x18003c1c4  jbe     loc_18003C78B
0x18003c1ca  mov     eax, r14d
0x18003c1cd  imul    rcx, rax, 214h
0x18003c1d4  lea     r15, [rdx+8]
0x18003c1d8  add     r15, rcx
0x18003c1db  xorps   xmm0, xmm0
0x18003c1de  xor     eax, eax
0x18003c1e0  movups  xmmword ptr [rbp+2B0h+ppInterfaceList], xmm0
0x18003c1e7  mov     [rbp+2B0h+var_60], rax
0x18003c1ee  lea     rcx, [rbp+2B0h+ppInterfaceList]
0x18003c1f5  call    ??0?$vector@UWlanAvailableNetworks@@V?$allocator@UWlanAvailableNetworks@@@std@@@std@@QEAA@XZ; std::vector<WlanAvailableNetworks>::vector<WlanAvailableNetworks>(void)
0x18003c1fa  nop
0x18003c1fb  mov     [rbp+2B0h+pMemory], r12
0x18003c202  lea     rax, [rbp+2B0h+pMemory]
0x18003c209  mov     [rsp+3B0h+var_378], rax
0x18003c20e  mov     [rsp+3B0h+var_370], r12
0x18003c213  mov     [rsp+3B0h+var_368], r13b
0x18003c218  lea     rax, [rsp+3B0h+var_370]
0x18003c21d  mov     [rsp+3B0h+ppAvailableNetworkList], rax; unsigned int
0x18003c222  xor     r9d, r9d; pReserved
0x18003c225  xor     r8d, r8d; dwFlags
0x18003c228  mov     rdx, r15; pInterfaceGuid
0x18003c22b  mov     rcx, [rbp+2B0h+phClientHandle]; hClientHandle
0x18003c232  call    cs:__imp_WlanGetAvailableNetworkList
0x18003c238  mov     rcx, [rbp+2B8h]; this
0x18003c23f  test    eax, eax
0x18003c241  jnz     loc_18003C7FD
0x18003c247  lea     rcx, [rsp+3B0h+var_378]
0x18003c24c  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_ptr@PEAXU?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>(void)
0x18003c251  mov     edi, r12d
0x18003c254  mov     rdx, [rbp+2B0h+pMemory]
0x18003c25b  cmp     [rdx], r12d
0x18003c25e  jbe     loc_18003C340
0x18003c264  mov     eax, edi
0x18003c266  imul    rbx, rax, 274h
0x18003c26d  add     rbx, 8
0x18003c271  add     rbx, rdx
0x18003c274  xor     edx, edx; Val
0x18003c276  mov     r8d, 274h; Size
0x18003c27c  lea     rcx, [rbp+2B0h+var_300]; void *
0x18003c280  call    memset_0
0x18003c285  mov     [rbp+2B0h+var_8C], r12d
0x18003c28c  lea     rcx, [rbp+2B0h+var_300]
0x18003c290  mov     eax, 4
0x18003c295  lea     edx, [rax+7Ch]
0x18003c298  movups  xmm0, xmmword ptr [rbx]
0x18003c29b  movups  xmmword ptr [rcx], xmm0
0x18003c29e  movups  xmm1, xmmword ptr [rbx+10h]
0x18003c2a2  movups  xmmword ptr [rcx+10h], xmm1
0x18003c2a6  movups  xmm0, xmmword ptr [rbx+20h]
0x18003c2aa  movups  xmmword ptr [rcx+20h], xmm0
0x18003c2ae  movups  xmm1, xmmword ptr [rbx+30h]
0x18003c2b2  movups  xmmword ptr [rcx+30h], xmm1
0x18003c2b6  movups  xmm0, xmmword ptr [rbx+40h]
0x18003c2ba  movups  xmmword ptr [rcx+40h], xmm0
0x18003c2be  movups  xmm1, xmmword ptr [rbx+50h]
0x18003c2c2  movups  xmmword ptr [rcx+50h], xmm1
0x18003c2c6  movups  xmm0, xmmword ptr [rbx+60h]
0x18003c2ca  movups  xmmword ptr [rcx+60h], xmm0
0x18003c2ce  movups  xmm1, xmmword ptr [rbx+70h]
0x18003c2d2  movups  xmmword ptr [rcx+70h], xmm1
0x18003c2d6  add     rcx, rdx
0x18003c2d9  add     rbx, rdx
0x18003c2dc  sub     rax, 1
0x18003c2e0  jnz     short loc_18003C298
0x18003c2e2  movups  xmm0, xmmword ptr [rbx]
0x18003c2e5  movups  xmmword ptr [rcx], xmm0
0x18003c2e8  movups  xmm1, xmmword ptr [rbx+10h]
0x18003c2ec  movups  xmmword ptr [rcx+10h], xmm1
0x18003c2f0  movups  xmm0, xmmword ptr [rbx+20h]
0x18003c2f4  movups  xmmword ptr [rcx+20h], xmm0
0x18003c2f8  movups  xmm1, xmmword ptr [rbx+30h]
0x18003c2fc  movups  xmmword ptr [rcx+30h], xmm1
0x18003c300  movups  xmm0, xmmword ptr [rbx+40h]
0x18003c304  movups  xmmword ptr [rcx+40h], xmm0
0x18003c308  movups  xmm1, xmmword ptr [rbx+50h]
0x18003c30c  movups  xmmword ptr [rcx+50h], xmm1
0x18003c310  movups  xmm0, xmmword ptr [rbx+60h]
0x18003c314  movups  xmmword ptr [rcx+60h], xmm0
0x18003c318  mov     eax, [rbx+70h]
0x18003c31b  mov     [rcx+70h], eax
0x18003c31e  lea     rdx, [rbp+2B0h+var_300]
0x18003c322  lea     rcx, [rbp+2B0h+ppInterfaceList]
0x18003c329  call    ??$_Emplace_one_at_back@AEBUWlanAvailableNetworks@@@?$vector@UWlanAvailableNetworks@@V?$allocator@UWlanAvailableNetworks@@@std@@@std@@AEAAAEAUWlanAvailableNetworks@@AEBU2@@Z; std::vector<WlanAvailableNetworks>::_Emplace_one_at_back<WlanAvailableNetworks const &>(WlanAvailableNetworks const &)
0x18003c32e  add     edi, r13d
0x18003c331  mov     rdx, [rbp+2B0h+pMemory]
0x18003c338  cmp     edi, [rdx]
0x18003c33a  jb      loc_18003C264
0x18003c340  mov     [rbp+2B0h+pMemory], r12
0x18003c347  test    rdx, rdx
0x18003c34a  jz      short loc_18003C355
0x18003c34c  mov     rcx, rdx; pMemory
0x18003c34f  call    cs:__imp_WlanFreeMemory
0x18003c355  lea     rax, [rbp+2B0h+pMemory]
0x18003c35c  mov     [rsp+3B0h+var_378], rax
0x18003c361  mov     [rsp+3B0h+var_370], r12
0x18003c366  mov     [rsp+3B0h+var_368], r13b
0x18003c36b  lea     rax, [rsp+3B0h+var_370]
0x18003c370  mov     [rsp+3B0h+ppAvailableNetworkList], rax; unsigned int
0x18003c375  xor     r9d, r9d; pReserved
0x18003c378  mov     r8d, r13d; dwFlags
0x18003c37b  mov     rdx, r15; pInterfaceGuid
0x18003c37e  mov     rcx, [rbp+2B0h+phClientHandle]; hClientHandle
0x18003c385  call    cs:__imp_WlanGetAvailableNetworkList
0x18003c38b  mov     rcx, [rbp+2B8h]; this
0x18003c392  test    eax, eax
0x18003c394  jnz     loc_18003C7E8
0x18003c39a  lea     rcx, [rsp+3B0h+var_378]
0x18003c39f  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_ptr@PEAXU?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>(void)
0x18003c3a4  mov     edi, r12d
0x18003c3a7  mov     rdx, [rbp+2B0h+pMemory]
0x18003c3ae  cmp     [rdx], r12d
0x18003c3b1  jbe     loc_18003C4C2
0x18003c3b7  mov     eax, edi
0x18003c3b9  imul    rbx, rax, 274h
0x18003c3c0  add     rbx, 8
0x18003c3c4  add     rbx, rdx
0x18003c3c7  xor     edx, edx; Val
0x18003c3c9  mov     r8d, 274h; Size
0x18003c3cf  lea     rcx, [rbp+2B0h+var_300]; void *
0x18003c3d3  call    memset_0
0x18003c3d8  mov     [rbp+2B0h+var_8C], r13d
0x18003c3df  lea     rcx, [rbp+2B0h+var_300]
0x18003c3e3  mov     eax, 4
0x18003c3e8  lea     edx, [rax+7Ch]
0x18003c3eb  movups  xmm0, xmmword ptr [rbx]
0x18003c3ee  movups  xmmword ptr [rcx], xmm0
0x18003c3f1  movups  xmm1, xmmword ptr [rbx+10h]
0x18003c3f5  movups  xmmword ptr [rcx+10h], xmm1
0x18003c3f9  movups  xmm0, xmmword ptr [rbx+20h]
0x18003c3fd  movups  xmmword ptr [rcx+20h], xmm0
0x18003c401  movups  xmm1, xmmword ptr [rbx+30h]
0x18003c405  movups  xmmword ptr [rcx+30h], xmm1
0x18003c409  movups  xmm0, xmmword ptr [rbx+40h]
0x18003c40d  movups  xmmword ptr [rcx+40h], xmm0
0x18003c411  movups  xmm1, xmmword ptr [rbx+50h]
0x18003c415  movups  xmmword ptr [rcx+50h], xmm1
0x18003c419  movups  xmm0, xmmword ptr [rbx+60h]
0x18003c41d  movups  xmmword ptr [rcx+60h], xmm0
0x18003c421  movups  xmm1, xmmword ptr [rbx+70h]
0x18003c425  movups  xmmword ptr [rcx+70h], xmm1
0x18003c429  add     rcx, rdx
0x18003c42c  add     rbx, rdx
0x18003c42f  sub     rax, 1
0x18003c433  jnz     short loc_18003C3EB
0x18003c435  movups  xmm0, xmmword ptr [rbx]
0x18003c438  movups  xmmword ptr [rcx], xmm0
0x18003c43b  movups  xmm1, xmmword ptr [rbx+10h]
0x18003c43f  movups  xmmword ptr [rcx+10h], xmm1
0x18003c443  movups  xmm0, xmmword ptr [rbx+20h]
0x18003c447  movups  xmmword ptr [rcx+20h], xmm0
0x18003c44b  movups  xmm1, xmmword ptr [rbx+30h]
0x18003c44f  movups  xmmword ptr [rcx+30h], xmm1
0x18003c453  movups  xmm0, xmmword ptr [rbx+40h]
0x18003c457  movups  xmmword ptr [rcx+40h], xmm0
0x18003c45b  movups  xmm1, xmmword ptr [rbx+50h]
0x18003c45f  movups  xmmword ptr [rcx+50h], xmm1
0x18003c463  movups  xmm0, xmmword ptr [rbx+60h]
0x18003c467  movups  xmmword ptr [rcx+60h], xmm0
0x18003c46b  mov     eax, [rbx+70h]
0x18003c46e  mov     [rcx+70h], eax
0x18003c471  mov     [rsp+3B0h+var_380], r12
0x18003c476  lea     r9, [rbp+2B0h+var_300]
0x18003c47a  mov     r8, [rbp+2B0h+ppInterfaceList+8]
0x18003c481  mov     rdx, [rbp+2B0h+ppInterfaceList]
0x18003c488  lea     rcx, [rsp+3B0h+var_380]
0x18003c48d  call    ??$find@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UWlanAvailableNetworks@@@std@@@std@@@std@@UWlanAvailableNetworks@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UWlanAvailableNetworks@@@std@@@std@@@0@V10@V10@AEBUWlanAvailableNetworks@@@Z; std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<WlanAvailableNetworks>>>,WlanAvailableNetworks>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<WlanAvailableNetworks>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<WlanAvailableNetworks>>>,WlanAvailableNetworks const &)
0x18003c492  mov     rax, [rbp+2B0h+ppInterfaceList+8]
0x18003c499  cmp     [rsp+3B0h+var_380], rax
0x18003c49e  jnz     short loc_18003C4B0
0x18003c4a0  lea     rdx, [rbp+2B0h+var_300]
0x18003c4a4  lea     rcx, [rbp+2B0h+ppInterfaceList]
0x18003c4ab  call    ??$_Emplace_one_at_back@AEBUWlanAvailableNetworks@@@?$vector@UWlanAvailableNetworks@@V?$allocator@UWlanAvailableNetworks@@@std@@@std@@AEAAAEAUWlanAvailableNetworks@@AEBU2@@Z; std::vector<WlanAvailableNetworks>::_Emplace_one_at_back<WlanAvailableNetworks const &>(WlanAvailableNetworks const &)
0x18003c4b0  add     edi, r13d
0x18003c4b3  mov     rdx, [rbp+2B0h+pMemory]
0x18003c4ba  cmp     edi, [rdx]
0x18003c4bc  jb      loc_18003C3B7
0x18003c4c2  mov     [rbp+2B0h+pMemory], r12
0x18003c4c9  test    rdx, rdx
0x18003c4cc  jz      short loc_18003C4D7
0x18003c4ce  mov     rcx, rdx; pMemory
0x18003c4d1  call    cs:__imp_WlanFreeMemory
0x18003c4d7  lea     rax, [rbp+2B0h+pMemory]
0x18003c4de  mov     [rsp+3B0h+var_378], rax
0x18003c4e3  mov     [rsp+3B0h+var_370], r12
0x18003c4e8  mov     [rsp+3B0h+var_368], r13b
0x18003c4ed  lea     rax, [rsp+3B0h+var_370]
0x18003c4f2  mov     [rsp+3B0h+ppAvailableNetworkList], rax; unsigned int
0x18003c4f7  xor     r9d, r9d; pReserved
0x18003c4fa  lea     r8d, [r9+2]; dwFlags
0x18003c4fe  mov     rdx, r15; pInterfaceGuid
0x18003c501  mov     rcx, [rbp+2B0h+phClientHandle]; hClientHandle
0x18003c508  call    cs:__imp_WlanGetAvailableNetworkList
0x18003c50e  mov     rcx, [rbp+2B8h]; this
0x18003c515  test    eax, eax
0x18003c517  jnz     loc_18003C7D3
0x18003c51d  lea     rcx, [rsp+3B0h+var_378]
0x18003c522  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_ptr@PEAXU?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>(void)
0x18003c527  mov     edi, r12d
0x18003c52a  mov     rax, [rbp+2B0h+pMemory]
0x18003c531  cmp     [rax], r12d
0x18003c534  jbe     loc_18003C65E
0x18003c53a  mov     ecx, edi
0x18003c53c  imul    rdx, rcx, 274h
0x18003c543  lea     rbx, [rax+8]
0x18003c547  add     rbx, rdx
0x18003c54a  xor     edx, edx; Val
0x18003c54c  mov     r8d, 274h; Size
0x18003c552  lea     rcx, [rbp+2B0h+var_300]; void *
0x18003c556  call    memset_0
0x18003c55b  mov     [rbp+2B0h+var_8C], 2
0x18003c565  lea     rcx, [rbp+2B0h+var_300]
0x18003c569  mov     eax, 4
0x18003c56e  lea     edx, [rax+7Ch]
0x18003c571  movups  xmm0, xmmword ptr [rbx]
0x18003c574  movups  xmmword ptr [rcx], xmm0
0x18003c577  movups  xmm1, xmmword ptr [rbx+10h]
0x18003c57b  movups  xmmword ptr [rcx+10h], xmm1
0x18003c57f  movups  xmm0, xmmword ptr [rbx+20h]
0x18003c583  movups  xmmword ptr [rcx+20h], xmm0
0x18003c587  movups  xmm1, xmmword ptr [rbx+30h]
0x18003c58b  movups  xmmword ptr [rcx+30h], xmm1
0x18003c58f  movups  xmm0, xmmword ptr [rbx+40h]
0x18003c593  movups  xmmword ptr [rcx+40h], xmm0
0x18003c597  movups  xmm1, xmmword ptr [rbx+50h]
0x18003c59b  movups  xmmword ptr [rcx+50h], xmm1
0x18003c59f  movups  xmm0, xmmword ptr [rbx+60h]
0x18003c5a3  movups  xmmword ptr [rcx+60h], xmm0
0x18003c5a7  movups  xmm1, xmmword ptr [rbx+70h]
0x18003c5ab  movups  xmmword ptr [rcx+70h], xmm1
0x18003c5af  add     rcx, rdx
0x18003c5b2  add     rbx, rdx
0x18003c5b5  sub     rax, 1
0x18003c5b9  jnz     short loc_18003C571
0x18003c5bb  movups  xmm0, xmmword ptr [rbx]
0x18003c5be  movups  xmmword ptr [rcx], xmm0
0x18003c5c1  movups  xmm1, xmmword ptr [rbx+10h]
0x18003c5c5  movups  xmmword ptr [rcx+10h], xmm1
0x18003c5c9  movups  xmm0, xmmword ptr [rbx+20h]
0x18003c5cd  movups  xmmword ptr [rcx+20h], xmm0
0x18003c5d1  movups  xmm1, xmmword ptr [rbx+30h]
0x18003c5d5  movups  xmmword ptr [rcx+30h], xmm1
0x18003c5d9  movups  xmm0, xmmword ptr [rbx+40h]
0x18003c5dd  movups  xmmword ptr [rcx+40h], xmm0
  ... truncated ...
```
