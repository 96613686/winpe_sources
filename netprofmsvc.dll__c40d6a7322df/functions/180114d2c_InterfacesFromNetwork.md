# InterfacesFromNetwork

- ea: `0x180114d2c`
- end: `0x18011504a`
- name: `InterfacesFromNetwork`
- size: `798`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003db4c`

## callees

- `0x18000eab0`
- `0x180013748`
- `0x180014e74`
- `0x180015608`
- `0x180035dc4`
- `0x1800425a0`
- `0x180047d60`
- `0x18004d0ac`
- `0x1800a88a0`
- `0x1800a9738`
- `0x180114700`
- `0x180114d2c`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x180114e46`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x180114e46`
- `IPHLPAPI!GetIfEntry` at `0x180114eee`
- `IPHLPAPI!GetIfEntry` at `0x180114eee`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180114ed5`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180114ed5`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180114ea3`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180114ea3`

## string_xrefs

- `0x180114fba`: `onecore\net\netprofiles\service\src\nsprpc\lib\nsprpc.cpp`
- `0x180114fcf`: `onecore\net\netprofiles\service\src\nsprpc\lib\nsprpc.cpp`
- `0x180114fe4`: `onecore\net\netprofiles\service\src\nsprpc\lib\nsprpc.cpp`
- `0x180114ff9`: `onecore\net\netprofiles\service\src\nsprpc\lib\nsprpc.cpp`
- `0x18011500e`: `onecore\net\netprofiles\service\src\nsprpc\lib\nsprpc.cpp`
- `0x180115023`: `onecore\net\netprofiles\service\src\nsprpc\lib\nsprpc.cpp`
- `0x180115038`: `onecore\net\netprofiles\service\src\nsprpc\lib\nsprpc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall InterfacesFromNetwork(_QWORD *a1, _QWORD *a2)
{
  int v3; // eax
  __int64 v4; // rax
  int v5; // eax
  int v6; // eax
  HRESULT v7; // eax
  __int64 v8; // rax
  void *v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // eax
  DWORD IfEntry; // eax
  IFTYPE dwType; // r8d
  DWORD dwSpeed; // r9d
  __int64 v15; // rdx
  void *v16; // rcx
  unsigned int v18; // [rsp+20h] [rbp-E0h]
  void *v19[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v20; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  LPOLESTR lpsz; // [rsp+58h] [rbp-A8h] BYREF
  __int64 *v23; // [rsp+60h] [rbp-A0h] BYREF
  void *v24; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v25; // [rsp+70h] [rbp-90h]
  NET_LUID InterfaceLuid; // [rsp+78h] [rbp-88h] BYREF
  IID rclsid; // [rsp+80h] [rbp-80h] BYREF
  _MIB_IFROW pIfRow; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+408h] [rbp+308h]

  v19[1] = a1;
  v23 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 **))(*(_QWORD *)*a2 + 136LL))(*a2, 1, &v23);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD5,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\nsprpc\\lib\\nsprpc.cpp",
      (const char *)(unsigned int)v3,
      v18);
  *(_OWORD *)a1 = 0;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  while ( 1 )
  {
    v21 = 0;
    v20 = 0;
    v4 = *v23;
    v21 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *, int *))(v4 + 24))(v23, 1, &v21, &v20);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDD,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\nsprpc\\lib\\nsprpc.cpp",
        (const char *)(unsigned int)v5,
        v18);
    if ( v5 == 1 || !v20 )
      break;
    rclsid = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, IID *))(*(_QWORD *)v21 + 32LL))(v21, &rclsid);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE4,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\nsprpc\\lib\\nsprpc.cpp",
        (const char *)(unsigned int)v6,
        v18);
    lpsz = 0;
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
      &lpsz,
      0);
    v7 = StringFromIID(&rclsid, &lpsz);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE7,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\nsprpc\\lib\\nsprpc.cpp",
        (const char *)(unsigned int)v7,
        v18);
    v24 = 0;
    v25 = 0;
    v8 = MidlAllocString(v19, &lpsz);
    wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::operator=(&v24, v8);
    v9 = v19[0];
    v19[0] = 0;
    if ( v9 )
      MIDL_user_free(v9);
    InterfaceLuid.Value = 0;
    v10 = ConvertInterfaceGuidToLuid(&rclsid, &InterfaceLuid);
    if ( v10 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xED,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\nsprpc\\lib\\nsprpc.cpp",
        (const char *)v10,
        v18);
    memset_0(&pIfRow, 0, sizeof(pIfRow));
    v11 = ConvertInterfaceLuidToIndex(&InterfaceLuid, &pIfRow.dwIndex);
    if ( v11 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xF0,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\nsprpc\\lib\\nsprpc.cpp",
        (const char *)v11,
        v18);
    IfEntry = GetIfEntry(&pIfRow);
    if ( IfEntry )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xF1,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\nsprpc\\lib\\nsprpc.cpp",
        (const char *)IfEntry,
        v18);
    dwType = pIfRow.dwType;
    v25 = __PAIR64__(pIfRow.dwSpeed, pIfRow.dwType);
    dwSpeed = pIfRow.dwSpeed;
    v15 = a1[1];
    if ( v15 == a1[2] )
    {
      std::vector<InterfaceData>::_Emplace_reallocate<InterfaceData>(a1, v15, &v24);
      v16 = v24;
    }
    else
    {
      v16 = 0;
      *(_QWORD *)v15 = v24;
      *(_DWORD *)(v15 + 8) = dwType;
      *(_DWORD *)(v15 + 12) = dwSpeed;
      a1[1] += 16LL;
    }
    v24 = 0;
    if ( v16 )
      MIDL_user_free(v16);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
    wil::com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>::~com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>(&v21);
  }
  wil::com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>::~com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>(&v21);
  wil::com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>::~com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>(&v23);
  return a1;
}

```

## disassembly

```asm
0x180114d2c  mov     [rsp-8+arg_10], rbx
0x180114d31  mov     [rsp-8+arg_18], rdi
0x180114d36  push    rbp
0x180114d37  lea     rbp, [rsp-300h]
0x180114d3f  sub     rsp, 400h
0x180114d46  mov     rax, cs:__security_cookie
0x180114d4d  xor     rax, rsp
0x180114d50  mov     [rbp+300h+var_10], rax
0x180114d57  mov     rbx, rcx
0x180114d5a  mov     [rsp+400h+var_3C0], rcx
0x180114d5f  xor     edi, edi
0x180114d61  mov     [rsp+400h+var_3D0], edi
0x180114d65  mov     [rsp+400h+var_3A0], rdi
0x180114d6a  mov     rcx, [rdx]
0x180114d6d  mov     rax, [rcx]
0x180114d70  mov     [rsp+400h+var_3A0], rdi
0x180114d75  lea     r8, [rsp+400h+var_3A0]
0x180114d7a  lea     edx, [rdi+1]
0x180114d7d  mov     rax, [rax+88h]
0x180114d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114d89  mov     rcx, [rbp+308h]; this
0x180114d90  test    eax, eax
0x180114d92  js      loc_180114FE1
0x180114d98  xorps   xmm0, xmm0
0x180114d9b  movups  xmmword ptr [rbx], xmm0
0x180114d9e  mov     [rbx], rdi
0x180114da1  mov     [rbx+8], rdi
0x180114da5  mov     [rbx+10h], rdi
0x180114da9  mov     [rsp+400h+var_3D0], 1
0x180114db1  mov     [rsp+400h+var_3B0], rdi
0x180114db6  mov     [rsp+400h+var_3B8], edi
0x180114dba  mov     rcx, [rsp+400h+var_3A0]
0x180114dbf  mov     rax, [rcx]
0x180114dc2  mov     [rsp+400h+var_3B0], rdi
0x180114dc7  lea     r9, [rsp+400h+var_3B8]
0x180114dcc  lea     r8, [rsp+400h+var_3B0]
0x180114dd1  mov     edx, 1
0x180114dd6  mov     rax, [rax+18h]
0x180114dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114ddf  mov     rcx, [rbp+308h]; this
0x180114de6  test    eax, eax
0x180114de8  js      loc_180114FCC
0x180114dee  cmp     eax, 1
0x180114df1  jz      loc_180114F7B
0x180114df7  cmp     [rsp+400h+var_3B8], edi
0x180114dfb  jz      loc_180114F7B
0x180114e01  xorps   xmm0, xmm0
0x180114e04  movups  xmmword ptr [rbp+300h+rclsid.Data1], xmm0
0x180114e08  mov     rcx, [rsp+400h+var_3B0]
0x180114e0d  mov     rax, [rcx]
0x180114e10  lea     rdx, [rbp+300h+rclsid]
0x180114e14  mov     rax, [rax+20h]
0x180114e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114e1d  mov     rcx, [rbp+308h]; this
0x180114e24  test    eax, eax
0x180114e26  js      loc_180114FB7
0x180114e2c  mov     [rsp+400h+lpsz], rdi
0x180114e31  xor     edx, edx
0x180114e33  lea     rcx, [rsp+400h+lpsz]
0x180114e38  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x180114e3d  lea     rdx, [rsp+400h+lpsz]; lplpsz
0x180114e42  lea     rcx, [rbp+300h+rclsid]; rclsid
0x180114e46  call    cs:__imp_StringFromIID
0x180114e4c  mov     rcx, [rbp+308h]; this
0x180114e53  test    eax, eax
0x180114e55  js      loc_180115035
0x180114e5b  mov     [rsp+400h+var_398], rdi
0x180114e60  mov     [rsp+400h+var_390], rdi
0x180114e65  lea     rdx, [rsp+400h+lpsz]
0x180114e6a  lea     rcx, [rsp+400h+var_3C8]
0x180114e6f  call    ?MidlAllocString@@YA?AV?$unique_ptr@_WU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@wistd@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; MidlAllocString(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> const &)
0x180114e74  mov     rdx, rax
0x180114e77  lea     rcx, [rsp+400h+var_398]
0x180114e7c  call    ??4?$unique_ptr@_WU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::operator=(wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>> &&)
0x180114e81  mov     rcx, [rsp+400h+var_3C8]; void *
0x180114e86  mov     [rsp+400h+var_3C8], rdi
0x180114e8b  test    rcx, rcx
0x180114e8e  jz      short loc_180114E95
0x180114e90  call    MIDL_user_free
0x180114e95  mov     qword ptr [rsp+400h+InterfaceLuid], rdi
0x180114e9a  lea     rdx, [rsp+400h+InterfaceLuid]; InterfaceLuid
0x180114e9f  lea     rcx, [rbp+300h+rclsid]; InterfaceGuid
0x180114ea3  call    cs:__imp_ConvertInterfaceGuidToLuid
0x180114ea9  mov     rcx, [rbp+308h]; this
0x180114eb0  test    eax, eax
0x180114eb2  jnz     loc_180115020
0x180114eb8  xor     edx, edx; Val
0x180114eba  mov     r8d, 35Ch; Size
0x180114ec0  lea     rcx, [rbp+300h+pIfRow]; void *
0x180114ec4  call    memset_0
0x180114ec9  lea     rdx, [rbp+300h+pIfRow.dwIndex]; InterfaceIndex
0x180114ed0  lea     rcx, [rsp+400h+InterfaceLuid]; InterfaceLuid
0x180114ed5  call    cs:__imp_ConvertInterfaceLuidToIndex
0x180114edb  mov     rcx, [rbp+308h]; this
0x180114ee2  test    eax, eax
0x180114ee4  jnz     loc_18011500B
0x180114eea  lea     rcx, [rbp+300h+pIfRow]; pIfRow
0x180114eee  call    cs:__imp_GetIfEntry
0x180114ef4  mov     rcx, [rbp+308h]; this
0x180114efb  test    eax, eax
0x180114efd  jnz     loc_180114FF6
0x180114f03  mov     r8d, [rbp+300h+pIfRow.dwType]
0x180114f0a  mov     dword ptr [rsp+400h+var_390], r8d
0x180114f0f  mov     r9d, [rbp+300h+pIfRow.dwSpeed]
0x180114f16  mov     dword ptr [rsp+400h+var_390+4], r9d
0x180114f1b  mov     rdx, [rbx+8]
0x180114f1f  cmp     rdx, [rbx+10h]
0x180114f23  jz      short loc_180114F3F
0x180114f25  mov     rax, [rsp+400h+var_398]
0x180114f2a  mov     rcx, rdi
0x180114f2d  mov     [rdx], rax
0x180114f30  mov     [rdx+8], r8d
0x180114f34  mov     [rdx+0Ch], r9d
0x180114f38  add     qword ptr [rbx+8], 10h
0x180114f3d  jmp     short loc_180114F51
0x180114f3f  lea     r8, [rsp+400h+var_398]
0x180114f44  mov     rcx, rbx
0x180114f47  call    ??$_Emplace_reallocate@UInterfaceData@@@?$vector@UInterfaceData@@V?$allocator@UInterfaceData@@@std@@@std@@AEAAPEAUInterfaceData@@QEAU2@$$QEAU2@@Z; std::vector<InterfaceData>::_Emplace_reallocate<InterfaceData>(InterfaceData * const,InterfaceData &&)
0x180114f4c  mov     rcx, [rsp+400h+var_398]; void *
0x180114f51  mov     [rsp+400h+var_398], rdi
0x180114f56  test    rcx, rcx
0x180114f59  jz      short loc_180114F61
0x180114f5b  call    MIDL_user_free
0x180114f60  nop
0x180114f61  lea     rcx, [rsp+400h+lpsz]
0x180114f66  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180114f6b  nop
0x180114f6c  lea     rcx, [rsp+400h+var_3B0]
0x180114f71  call    ??1?$com_ptr_t@UINetworkInterfacePrivate@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>::~com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>(void)
0x180114f76  jmp     loc_180114DB1
0x180114f7b  lea     rcx, [rsp+400h+var_3B0]
0x180114f80  call    ??1?$com_ptr_t@UINetworkInterfacePrivate@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>::~com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>(void)
0x180114f85  nop
0x180114f86  lea     rcx, [rsp+400h+var_3A0]
0x180114f8b  call    ??1?$com_ptr_t@UINetworkInterfacePrivate@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>::~com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>(void)
0x180114f90  mov     rax, rbx
0x180114f93  mov     rcx, [rbp+300h+var_10]
0x180114f9a  xor     rcx, rsp; StackCookie
0x180114f9d  call    __security_check_cookie
0x180114fa2  lea     r11, [rsp+400h+var_s0]
0x180114faa  mov     rbx, [r11+20h]
0x180114fae  mov     rdi, [r11+28h]
0x180114fb2  mov     rsp, r11
0x180114fb5  pop     rbp
0x180114fb6  retn
0x180114fb7  mov     r9d, eax; char *
0x180114fba  lea     r8, aOnecoreNetNetp_35; "onecore\\net\\netprofiles\\service\\src"...
0x180114fc1  mov     edx, 0E4h; void *
0x180114fc6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180114fcc  mov     r9d, eax; char *
0x180114fcf  lea     r8, aOnecoreNetNetp_35; "onecore\\net\\netprofiles\\service\\src"...
0x180114fd6  mov     edx, 0DDh; void *
0x180114fdb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180114fe1  mov     r9d, eax; char *
0x180114fe4  lea     r8, aOnecoreNetNetp_35; "onecore\\net\\netprofiles\\service\\src"...
0x180114feb  mov     edx, 0D5h; void *
0x180114ff0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180114ff6  mov     r9d, eax; char *
0x180114ff9  lea     r8, aOnecoreNetNetp_35; "onecore\\net\\netprofiles\\service\\src"...
0x180115000  mov     edx, 0F1h; void *
0x180115005  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18011500b  mov     r9d, eax; char *
0x18011500e  lea     r8, aOnecoreNetNetp_35; "onecore\\net\\netprofiles\\service\\src"...
0x180115015  mov     edx, 0F0h; void *
0x18011501a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180115020  mov     r9d, eax; char *
0x180115023  lea     r8, aOnecoreNetNetp_35; "onecore\\net\\netprofiles\\service\\src"...
0x18011502a  mov     edx, 0EDh; void *
0x18011502f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180115035  mov     r9d, eax; char *
0x180115038  lea     r8, aOnecoreNetNetp_35; "onecore\\net\\netprofiles\\service\\src"...
0x18011503f  mov     edx, 0E7h; void *
0x180115044  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
