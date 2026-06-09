# TenantRestrictionsHelpers::GetO365Guid(void)

- ea: `0x18000eaf4`
- end: `0x18000ed8a`
- name: `?GetO365Guid@TenantRestrictionsHelpers@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `662`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b67c`

## callees

- `0x180001a50`
- `0x180008d64`
- `0x180009da8`
- `0x18000a864`
- `0x18000aaf4`
- `0x18000ab30`
- `0x18000c338`
- `0x18000c41c`
- `0x18000c43c`
- `0x18000c498`
- `0x18000c874`
- `0x18000ca74`
- `0x18000d694`
- `0x18000dc08`
- `0x18000eaf4`
- `0x18000fea0`
- `0x180010488`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000ec65`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000ec65`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000ec31`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000ec31`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ed27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ed27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ec10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ec27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ed52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ec10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ec27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ed52`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x18000eb53`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x18000eb53`

## string_xrefs

- `0x18000eb64`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000ec42`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000ec75`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000ed38`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`

## pseudocode

```c
_QWORD *__fastcall TenantRestrictionsHelpers::GetO365Guid(_QWORD *a1)
{
  unsigned int ServiceRegistryStateKey; // eax
  int RegistryString; // ebx
  HLOCAL v4; // rdi
  unsigned __int64 v5; // rax
  void **unique; // rax
  void *v7; // rbx
  void *v8; // rcx
  HLOCAL v9; // rcx
  HRESULT v10; // eax
  unsigned __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // rax
  const BYTE *v17; // rax
  unsigned int v18; // eax
  unsigned int lpData; // [rsp+20h] [rbp-29h]
  int lpDataa; // [rsp+20h] [rbp-29h]
  unsigned int lpDatab; // [rsp+20h] [rbp-29h]
  HKEY hKey; // [rsp+30h] [rbp-19h] BYREF
  int v24; // [rsp+38h] [rbp-11h]
  HLOCAL hMem; // [rsp+40h] [rbp-9h] BYREF
  HLOCAL v26[2]; // [rsp+48h] [rbp-1h] BYREF
  GUID pguid; // [rsp+58h] [rbp+Fh] BYREF
  _BYTE v28[32]; // [rsp+68h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v26[1] = a1;
  v24 = 0;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  ServiceRegistryStateKey = GetServiceRegistryStateKey(g_SvcStatusHandle, 1, 131103, &hKey);
  if ( ServiceRegistryStateKey )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xA1,
      (int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
      (const char *)ServiceRegistryStateKey,
      lpData);
  hMem = 0;
  RegistryString = ReadRegistryString(hKey, (__int64)&hMem);
  std::wstring::wstring((__int64)a1, (__int64)&qword_180014598);
  v24 = 1;
  v4 = hMem;
  if ( RegistryString != -2147024894 )
  {
    v5 = std::_WChar_traits<unsigned short>::length(hMem);
    std::wstring::_Assign<unsigned short>((__int64)a1, (__int64)v4, v5);
  }
  if ( !a1[2] )
  {
    pguid = 0;
    unique = (void **)wil::make_unique_hlocal<unsigned short [0]>(v26);
    v7 = *unique;
    *unique = 0;
    v8 = v4;
    v4 = v7;
    hMem = v7;
    if ( v8 )
      LocalFree(v8);
    v9 = v26[0];
    v26[0] = 0;
    if ( v9 )
      LocalFree(v9);
    v10 = CoCreateGuid(&pguid);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xBA,
        (int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
        (const char *)(unsigned int)v10,
        lpDataa);
    if ( StringFromGUID2(&pguid, (LPOLESTR)v7, 39) <= 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xBD,
        (int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
        (const char *)0x8007007ALL,
        lpDataa);
    std::wstring::wstring((__int64)v28, (__int64)v7);
    v11 = std::_WChar_traits<unsigned short>::length(L"74727632");
    v14 = std::wstring::_Replace<unsigned short>(v12, v12, 8u, v13, v11);
    std::wstring::operator=(a1, v14);
    std::wstring::_Tidy_deallocate((__int64)v28);
    v16 = std::wstring::substr(a1, v28, v15, a1[2] - 2LL);
    std::wstring::operator=(a1, v16);
    std::wstring::_Tidy_deallocate((__int64)v28);
    v17 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    v18 = RegSetValueExW(hKey, L"guid", 0, 1u, v17, 2 * *((_DWORD *)a1 + 4) + 2);
    if ( v18 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xCC,
        (int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
        (const char *)v18,
        lpDatab);
  }
  if ( v4 )
    LocalFree(v4);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return a1;
}

```

## disassembly

```asm
0x18000eaf4  mov     [rsp-8+arg_8], rbx
0x18000eaf9  mov     [rsp-8+arg_10], rsi
0x18000eafe  push    rbp
0x18000eaff  push    rdi
0x18000eb00  push    r14
0x18000eb02  lea     rbp, [rsp-47h]
0x18000eb07  sub     rsp, 90h
0x18000eb0e  mov     rax, cs:__security_cookie
0x18000eb15  xor     rax, rsp
0x18000eb18  mov     [rbp+57h+var_18], rax
0x18000eb1c  mov     rsi, rcx
0x18000eb1f  mov     [rbp+57h+var_50], rcx
0x18000eb23  mov     [rbp+57h+var_68], 0
0x18000eb2a  mov     [rbp+57h+hKey], 0
0x18000eb32  xor     edx, edx
0x18000eb34  lea     rcx, [rbp+57h+hKey]
0x18000eb38  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000eb3d  lea     r9, [rbp+57h+hKey]
0x18000eb41  mov     edx, 1
0x18000eb46  mov     r8d, 2001Fh
0x18000eb4c  mov     rcx, cs:?g_SvcStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * g_SvcStatusHandle
0x18000eb53  call    cs:__imp_GetServiceRegistryStateKey
0x18000eb59  mov     rcx, [rbp+5Fh]; this
0x18000eb5d  test    eax, eax
0x18000eb5f  jz      short loc_18000EB76
0x18000eb61  mov     r9d, eax; char *
0x18000eb64  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000eb6b  mov     edx, 0A1h; void *
0x18000eb70  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000eb76  mov     [rbp+57h+hMem], 0
0x18000eb7e  lea     rax, [rbp+57h+hMem]
0x18000eb82  mov     [rsp+0A0h+lpData], rax; int
0x18000eb87  mov     r9d, 2
0x18000eb8d  lea     r8, aGuid; "guid"
0x18000eb94  mov     rcx, [rbp+57h+hKey]; hkey
0x18000eb98  call    ?ReadRegistryString@@YAJPEAUHKEY__@@PEBG1KAEAV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@Z; ReadRegistryString(HKEY__ *,ushort const *,ushort const *,ulong,wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &)
0x18000eb9d  mov     ebx, eax
0x18000eb9f  lea     rdx, qword_180014598
0x18000eba6  mov     rcx, rsi
0x18000eba9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000ebae  mov     [rbp+57h+var_68], 1
0x18000ebb5  mov     rdi, [rbp+57h+hMem]
0x18000ebb9  cmp     ebx, 80070002h
0x18000ebbf  jz      short loc_18000EBD7
0x18000ebc1  mov     rcx, rdi
0x18000ebc4  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000ebc9  mov     r8, rax
0x18000ebcc  mov     rdx, rdi
0x18000ebcf  mov     rcx, rsi
0x18000ebd2  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18000ebd7  cmp     qword ptr [rsi+10h], 0
0x18000ebdc  jnz     loc_18000ED4A
0x18000ebe2  xorps   xmm0, xmm0
0x18000ebe5  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x18000ebe9  mov     edx, 27h ; '''
0x18000ebee  lea     rcx, [rbp+57h+var_58]
0x18000ebf2  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x18000ebf7  mov     rbx, [rax]
0x18000ebfa  mov     qword ptr [rax], 0
0x18000ec01  mov     rcx, rdi; hMem
0x18000ec04  mov     rdi, rbx
0x18000ec07  mov     [rbp+57h+hMem], rbx
0x18000ec0b  test    rcx, rcx
0x18000ec0e  jz      short loc_18000EC16
0x18000ec10  call    cs:__imp_LocalFree
0x18000ec16  mov     rcx, [rbp+57h+var_58]; hMem
0x18000ec1a  mov     [rbp+57h+var_58], 0
0x18000ec22  test    rcx, rcx
0x18000ec25  jz      short loc_18000EC2D
0x18000ec27  call    cs:__imp_LocalFree
0x18000ec2d  lea     rcx, [rbp+57h+pguid]; pguid
0x18000ec31  call    cs:__imp_CoCreateGuid
0x18000ec37  mov     rcx, [rbp+5Fh]; this
0x18000ec3b  test    eax, eax
0x18000ec3d  jns     short loc_18000EC54
0x18000ec3f  mov     r9d, eax; char *
0x18000ec42  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000ec49  mov     edx, 0BAh; void *
0x18000ec4e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000ec54  mov     r14, [rbp+5Fh]
0x18000ec58  mov     r8d, 27h ; '''; cchMax
0x18000ec5e  mov     rdx, rbx; lpsz
0x18000ec61  lea     rcx, [rbp+57h+pguid]; rguid
0x18000ec65  call    cs:__imp_StringFromGUID2
0x18000ec6b  test    eax, eax
0x18000ec6d  jg      short loc_18000EC8A
0x18000ec6f  mov     r9d, 8007007Ah; char *
0x18000ec75  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000ec7c  mov     edx, 0BDh; void *
0x18000ec81  mov     rcx, r14; this
0x18000ec84  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000ec8a  mov     rdx, rbx
0x18000ec8d  lea     rcx, [rbp+57h+var_38]
0x18000ec91  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000ec96  mov     rdx, rax
0x18000ec99  lea     rcx, a74727632; "74727632"
0x18000eca0  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000eca5  mov     [rsp+0A0h+lpData], rax
0x18000ecaa  mov     r8d, 8
0x18000ecb0  mov     rcx, rdx
0x18000ecb3  call    ??$_Replace@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_K_KQEBG0@Z; std::wstring::_Replace<ushort>(unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x18000ecb8  mov     rdx, rax
0x18000ecbb  mov     rcx, rsi
0x18000ecbe  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000ecc3  nop
0x18000ecc4  lea     rcx, [rbp+57h+var_38]
0x18000ecc8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000eccd  mov     r9, [rsi+10h]
0x18000ecd1  sub     r9, 2
0x18000ecd5  lea     rdx, [rbp+57h+var_38]
0x18000ecd9  mov     rcx, rsi
0x18000ecdc  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18000ece1  mov     rdx, rax
0x18000ece4  mov     rcx, rsi
0x18000ece7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000ecec  lea     rcx, [rbp+57h+var_38]
0x18000ecf0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ecf5  mov     rcx, rsi
0x18000ecf8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000ecfd  mov     r8, rax
0x18000ed00  mov     eax, [rsi+10h]
0x18000ed03  lea     eax, ds:2[rax*2]
0x18000ed0a  mov     [rsp+0A0h+cbData], eax; cbData
0x18000ed0e  mov     [rsp+0A0h+lpData], r8; unsigned int
0x18000ed13  mov     r9d, 1; dwType
0x18000ed19  xor     r8d, r8d; Reserved
0x18000ed1c  lea     rdx, aGuid; "guid"
0x18000ed23  mov     rcx, [rbp+57h+hKey]; hKey
0x18000ed27  call    cs:__imp_RegSetValueExW
0x18000ed2d  mov     rcx, [rbp+5Fh]; this
0x18000ed31  test    eax, eax
0x18000ed33  jz      short loc_18000ED4A
0x18000ed35  mov     r9d, eax; char *
0x18000ed38  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000ed3f  mov     edx, 0CCh; void *
0x18000ed44  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000ed4a  test    rdi, rdi
0x18000ed4d  jz      short loc_18000ED59
0x18000ed4f  mov     rcx, rdi; hMem
0x18000ed52  call    cs:__imp_LocalFree
0x18000ed58  nop
0x18000ed59  lea     rcx, [rbp+57h+hKey]
0x18000ed5d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000ed62  mov     rax, rsi
0x18000ed65  mov     rcx, [rbp+57h+var_18]
0x18000ed69  xor     rcx, rsp; StackCookie
0x18000ed6c  call    __security_check_cookie
0x18000ed71  lea     r11, [rsp+0A0h+var_10]
0x18000ed79  mov     rbx, [r11+28h]
0x18000ed7d  mov     rsi, [r11+30h]
0x18000ed81  mov     rsp, r11
0x18000ed84  pop     r14
0x18000ed86  pop     rdi
0x18000ed87  pop     rbp
0x18000ed88  retn
```
