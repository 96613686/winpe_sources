# WlanInfo::EnumQueryableParameters(void)

- ea: `0x18003cd24`
- end: `0x18003cff8`
- name: `?EnumQueryableParameters@WlanInfo@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `724`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000f888`

## callees

- `0x18000f388`
- `0x18000f700`
- `0x1800100d8`
- `0x180010124`
- `0x180011614`
- `0x1800120d0`
- `0x18002a3e4`
- `0x18003a37c`
- `0x18003bfb0`
- `0x18003c014`
- `0x18003cd24`
- `0x18003de20`
- `0x18003e040`

## import_xrefs

- `ext-ms-win-networking-wlanapi-l1-1-0!WlanEnumInterfaces` at `0x18003cdc9`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanEnumInterfaces` at `0x18003cdc9`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanQueryInterface` at `0x18003cee9`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanQueryInterface` at `0x18003cee9`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x18003cd80`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x18003cd80`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18003cf90`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18003cfc8`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18003cf90`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18003cfc8`

## string_xrefs

- `0x18003cd91`: `onecore\net\netprofiles\service\src\netshnlmplugin\wlaninfomanager.cpp`
- `0x18003cdda`: `onecore\net\netprofiles\service\src\netshnlmplugin\wlaninfomanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall WlanInfo::EnumQueryableParameters(__int64 a1, __int64 a2)
{
  DWORD v3; // eax
  DWORD v4; // eax
  unsigned int v5; // esi
  char *i; // rdx
  char *v7; // r15
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 *v10; // rbx
  DWORD v11; // r14d
  __int64 v12; // rax
  _BYTE *v13; // rcx
  PVOID v14; // rcx
  unsigned int pdwDataSize; // [rsp+20h] [rbp-99h]
  PVOID *p_pMemory; // [rsp+48h] [rbp-71h] BYREF
  PWLAN_INTERFACE_INFO_LIST ppInterfaceList; // [rsp+50h] [rbp-69h] BYREF
  char v19; // [rsp+58h] [rbp-61h]
  _BYTE v20[32]; // [rsp+68h] [rbp-51h] BYREF
  __int64 v21; // [rsp+88h] [rbp-31h]
  _BYTE v22[32]; // [rsp+90h] [rbp-29h] BYREF
  enum _WLAN_OPCODE_VALUE_TYPE pWlanOpcodeValueType; // [rsp+B0h] [rbp-9h] BYREF
  PVOID pMemory; // [rsp+B8h] [rbp-1h] BYREF
  PVOID v25; // [rsp+C0h] [rbp+7h] BYREF
  HANDLE phClientHandle; // [rsp+C8h] [rbp+Fh] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+D0h] [rbp+17h] BYREF
  DWORD v28; // [rsp+D4h] [rbp+1Bh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v21 = a2;
  std::wstring::wstring(a2);
  phClientHandle = (HANDLE)-1LL;
  pdwNegotiatedVersion = 0;
  v3 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
  if ( v3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x485,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\wlaninfomanager.cpp",
      (const char *)v3,
      pdwDataSize);
  v25 = 0;
  p_pMemory = &v25;
  ppInterfaceList = 0;
  v19 = 1;
  v4 = WlanEnumInterfaces(phClientHandle, 0, &ppInterfaceList);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x489,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\wlaninfomanager.cpp",
      (const char *)v4,
      pdwDataSize);
  wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>((__int64)&p_pMemory);
  v5 = 0;
  for ( i = (char *)v25; v5 < *(_DWORD *)v25; i = (char *)v25 )
  {
    v7 = &i[532 * v5];
    ToString(v20, v7 + 536);
    v8 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    ToString(v22, v7 + 8);
    v9 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    wil::str_printf<std::wstring>(
      (__int64)&p_pMemory,
      (__int64)L"\n"
                " >>>>>> WLAN Interface Info [%u] <<<<<< \n"
                "    InterfaceGuid: %ws\n"
                "    Description: %ws\n"
                "    State: %ws\n",
      v5,
      v9,
      v7 + 24,
      v8);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)&p_pMemory);
    std::wstring::_Tidy_deallocate((__int64)v22);
    std::wstring::_Tidy_deallocate((__int64)v20);
    v10 = &qword_1800451C0;
    do
    {
      pMemory = 0;
      v28 = 0;
      pWlanOpcodeValueType = wlan_opcode_value_type_query_only;
      p_pMemory = &pMemory;
      ppInterfaceList = 0;
      v19 = 1;
      v11 = WlanQueryInterface(
              phClientHandle,
              (const GUID *)(v7 + 8),
              *(WLAN_INTF_OPCODE *)v10,
              0,
              &v28,
              (PVOID *)&ppInterfaceList,
              &pWlanOpcodeValueType);
      wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>((__int64)&p_pMemory);
      if ( v11 )
      {
        wil::str_printf<std::wstring>((__int64)v20, (__int64)L"    %ws: WlanQueryInterface failed (%u)\n", v10[1], v11);
        std::wstring::append();
        v13 = v20;
      }
      else
      {
        ToString(v22, pMemory, *(unsigned int *)v10, (unsigned int)pWlanOpcodeValueType);
        v12 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
        wil::str_printf<std::wstring>((__int64)v20, (__int64)L"    %ws: %ws", v10[1], v12);
        std::wstring::append();
        std::wstring::_Tidy_deallocate((__int64)v20);
        v13 = v22;
      }
      std::wstring::_Tidy_deallocate((__int64)v13);
      v14 = pMemory;
      pMemory = 0;
      if ( v14 )
        WlanFreeMemory(v14);
      v10 += 2;
    }
    while ( v10 != (__int64 *)&load_config_used );
    ++v5;
  }
  v25 = 0;
  if ( i )
    WlanFreeMemory(i);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWlanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWlanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(&phClientHandle);
  return a2;
}

```

## disassembly

```asm
0x18003cd24  push    rbp
0x18003cd26  push    rbx
0x18003cd27  push    rsi
0x18003cd28  push    rdi
0x18003cd29  push    r14
0x18003cd2b  push    r15
0x18003cd2d  lea     rbp, [rsp-2Fh]
0x18003cd32  sub     rsp, 0E8h
0x18003cd39  mov     rax, cs:__security_cookie
0x18003cd40  xor     rax, rsp
0x18003cd43  mov     [rbp+57h+var_38], rax
0x18003cd47  mov     rdi, rdx
0x18003cd4a  mov     [rbp+57h+var_88], rdx
0x18003cd4e  mov     [rbp+57h+var_D0], 0
0x18003cd55  mov     rcx, rdx
0x18003cd58  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003cd5d  mov     [rbp+57h+var_D0], 1
0x18003cd64  mov     [rbp+57h+phClientHandle], 0FFFFFFFFFFFFFFFFh
0x18003cd6c  mov     [rbp+57h+pdwNegotiatedVersion], 0
0x18003cd73  lea     r9, [rbp+57h+phClientHandle]; phClientHandle
0x18003cd77  lea     r8, [rbp+57h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18003cd7b  xor     edx, edx; pReserved
0x18003cd7d  lea     ecx, [rdx+2]; dwClientVersion
0x18003cd80  call    cs:__imp_WlanOpenHandle
0x18003cd86  mov     rcx, [rbp+5Fh]; this
0x18003cd8a  test    eax, eax
0x18003cd8c  jz      short loc_18003CDA3
0x18003cd8e  mov     r9d, eax; char *
0x18003cd91  lea     r8, aOnecoreNetNetp_7; "onecore\\net\\netprofiles\\service\\src"...
0x18003cd98  mov     edx, 485h; void *
0x18003cd9d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003cda3  mov     [rbp+57h+var_50], 0
0x18003cdab  lea     rax, [rbp+57h+var_50]
0x18003cdaf  mov     [rbp+57h+var_C8], rax
0x18003cdb3  mov     [rbp+57h+ppInterfaceList], 0
0x18003cdbb  mov     [rbp+57h+var_B8], 1
0x18003cdbf  lea     r8, [rbp+57h+ppInterfaceList]; ppInterfaceList
0x18003cdc3  xor     edx, edx; pReserved
0x18003cdc5  mov     rcx, [rbp+57h+phClientHandle]; hClientHandle
0x18003cdc9  call    cs:__imp_WlanEnumInterfaces
0x18003cdcf  mov     rcx, [rbp+5Fh]; this
0x18003cdd3  test    eax, eax
0x18003cdd5  jz      short loc_18003CDEC
0x18003cdd7  mov     r9d, eax; char *
0x18003cdda  lea     r8, aOnecoreNetNetp_7; "onecore\\net\\netprofiles\\service\\src"...
0x18003cde1  mov     edx, 489h; void *
0x18003cde6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003cdec  lea     rcx, [rbp+57h+var_C8]
0x18003cdf0  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_ptr@PEAXU?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>(void)
0x18003cdf5  xor     esi, esi
0x18003cdf7  mov     rdx, [rbp+57h+var_50]
0x18003cdfb  cmp     [rdx], esi
0x18003cdfd  jbe     loc_18003CFB8
0x18003ce03  mov     eax, esi
0x18003ce05  imul    r15, rax, 214h
0x18003ce0c  add     r15, rdx
0x18003ce0f  lea     rdx, [r15+218h]
0x18003ce16  lea     rcx, [rbp+57h+var_A8]
0x18003ce1a  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBW4_WLAN_INTERFACE_STATE@@@Z; ToString(_WLAN_INTERFACE_STATE const &)
0x18003ce1f  nop
0x18003ce20  mov     rcx, rax
0x18003ce23  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003ce28  mov     rbx, rax
0x18003ce2b  lea     rdx, [r15+8]
0x18003ce2f  lea     rcx, [rbp+57h+var_80]
0x18003ce33  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@@Z; ToString(_GUID const &)
0x18003ce38  nop
0x18003ce39  mov     rcx, rax
0x18003ce3c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003ce41  mov     r9, rax
0x18003ce44  lea     rax, [r15+18h]
0x18003ce48  mov     [rsp+110h+ppData], rbx
0x18003ce4d  mov     [rsp+110h+pdwDataSize], rax
0x18003ce52  mov     r8d, esi
0x18003ce55  lea     rdx, aWlanInterfaceI; "\n >>>>>> WLAN Interface Info [%u] <<<<"...
0x18003ce5c  lea     rcx, [rbp+57h+var_C8]
0x18003ce60  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18003ce65  nop
0x18003ce66  mov     rdx, rax
0x18003ce69  mov     rcx, rdi
0x18003ce6c  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18003ce71  nop
0x18003ce72  lea     rcx, [rbp+57h+var_C8]
0x18003ce76  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ce7b  nop
0x18003ce7c  lea     rcx, [rbp+57h+var_80]
0x18003ce80  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ce85  nop
0x18003ce86  lea     rcx, [rbp+57h+var_A8]
0x18003ce8a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ce8f  lea     rbx, qword_1800451C0
0x18003ce96  mov     [rbp+57h+pMemory], 0
0x18003ce9e  mov     [rbp+57h+var_3C], 0
0x18003cea5  mov     [rbp+57h+var_60], 0
0x18003ceac  lea     rax, [rbp+57h+pMemory]
0x18003ceb0  mov     [rbp+57h+var_C8], rax
0x18003ceb4  mov     [rbp+57h+ppInterfaceList], 0
0x18003cebc  mov     [rbp+57h+var_B8], 1
0x18003cec0  lea     rax, [rbp+57h+var_60]
0x18003cec4  mov     [rsp+110h+pWlanOpcodeValueType], rax; pWlanOpcodeValueType
0x18003cec9  lea     rax, [rbp+57h+ppInterfaceList]
0x18003cecd  mov     [rsp+110h+ppData], rax; ppData
0x18003ced2  lea     rax, [rbp+57h+var_3C]
0x18003ced6  mov     [rsp+110h+pdwDataSize], rax; pdwDataSize
0x18003cedb  xor     r9d, r9d; pReserved
0x18003cede  mov     r8d, [rbx]; OpCode
0x18003cee1  lea     rdx, [r15+8]; pInterfaceGuid
0x18003cee5  mov     rcx, [rbp+57h+phClientHandle]; hClientHandle
0x18003cee9  call    cs:__imp_WlanQueryInterface
0x18003ceef  mov     r14d, eax
0x18003cef2  lea     rcx, [rbp+57h+var_C8]
0x18003cef6  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_ptr@PEAXU?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<void *,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>(void)
0x18003cefb  test    r14d, r14d
0x18003cefe  jnz     short loc_18003CF51
0x18003cf00  mov     r9d, [rbp+57h+var_60]
0x18003cf04  mov     r8d, [rbx]
0x18003cf07  mov     rdx, [rbp+57h+pMemory]
0x18003cf0b  lea     rcx, [rbp+57h+var_80]
0x18003cf0f  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAXW4_WLAN_INTF_OPCODE@@W4_WLAN_OPCODE_VALUE_TYPE@@@Z; ToString(void *,_WLAN_INTF_OPCODE,_WLAN_OPCODE_VALUE_TYPE)
0x18003cf14  nop
0x18003cf15  mov     rcx, rax
0x18003cf18  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003cf1d  mov     r9, rax
0x18003cf20  mov     r8, [rbx+8]
0x18003cf24  lea     rdx, aWsWs; "    %ws: %ws"
0x18003cf2b  lea     rcx, [rbp+57h+var_A8]
0x18003cf2f  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18003cf34  nop
0x18003cf35  mov     rdx, rax
0x18003cf38  mov     rcx, rdi
0x18003cf3b  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18003cf40  nop
0x18003cf41  lea     rcx, [rbp+57h+var_A8]
0x18003cf45  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003cf4a  nop
0x18003cf4b  lea     rcx, [rbp+57h+var_80]
0x18003cf4f  jmp     short loc_18003CF79
0x18003cf51  mov     r9d, r14d
0x18003cf54  mov     r8, [rbx+8]
0x18003cf58  lea     rdx, aWsWlanqueryint; "    %ws: WlanQueryInterface failed (%u)"...
0x18003cf5f  lea     rcx, [rbp+57h+var_A8]
0x18003cf63  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18003cf68  nop
0x18003cf69  mov     rdx, rax
0x18003cf6c  mov     rcx, rdi
0x18003cf6f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18003cf74  nop
0x18003cf75  lea     rcx, [rbp+57h+var_A8]
0x18003cf79  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003cf7e  nop
0x18003cf7f  mov     rcx, [rbp+57h+pMemory]; pMemory
0x18003cf83  mov     [rbp+57h+pMemory], 0
0x18003cf8b  test    rcx, rcx
0x18003cf8e  jz      short loc_18003CF96
0x18003cf90  call    cs:__imp_WlanFreeMemory
0x18003cf96  add     rbx, 10h
0x18003cf9a  lea     rax, _load_config_used
0x18003cfa1  cmp     rbx, rax
0x18003cfa4  jnz     loc_18003CE96
0x18003cfaa  inc     esi
0x18003cfac  mov     rdx, [rbp+57h+var_50]
0x18003cfb0  cmp     esi, [rdx]
0x18003cfb2  jb      loc_18003CE03
0x18003cfb8  mov     [rbp+57h+var_50], 0
0x18003cfc0  test    rdx, rdx
0x18003cfc3  jz      short loc_18003CFCF
0x18003cfc5  mov     rcx, rdx; pMemory
0x18003cfc8  call    cs:__imp_WlanFreeMemory
0x18003cfce  nop
0x18003cfcf  lea     rcx, [rbp+57h+phClientHandle]
0x18003cfd3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWlanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWlanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWlanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(void)
0x18003cfd8  mov     rax, rdi
0x18003cfdb  mov     rcx, [rbp+57h+var_38]
0x18003cfdf  xor     rcx, rsp; StackCookie
0x18003cfe2  call    __security_check_cookie
0x18003cfe7  add     rsp, 0E8h
0x18003cfee  pop     r15
0x18003cff0  pop     r14
0x18003cff2  pop     rdi
0x18003cff3  pop     rsi
0x18003cff4  pop     rbx
0x18003cff5  pop     rbp
0x18003cff6  retn
```
