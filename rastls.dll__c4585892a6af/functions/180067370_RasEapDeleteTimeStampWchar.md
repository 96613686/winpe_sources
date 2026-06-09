# RasEapDeleteTimeStampWchar

- ea: `0x180067370`
- end: `0x180067536`
- name: `RasEapDeleteTimeStampWchar`
- size: `454`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task`

## callees

- `0x180005010`
- `0x180010140`
- `0x180029408`
- `0x18003636c`
- `0x180036414`
- `0x180065fd0`
- `0x1800662b0`
- `0x1800670fc`
- `0x1800672fc`
- `0x180067370`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006740f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006740f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800674ba`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800674ba`

## string_xrefs

- `0x180067401`: `SYSTEM\CurrentControlSet\Services\RasMan\Deleted-Profiles\`

## pseudocode

```c
struct _EAPTLS_CONTROL_BLOCK **__fastcall RasEapDeleteTimeStampWchar(LPCWSTR lpValueName)
{
  HKEY *phkResult; // rax
  unsigned int Key; // eax
  __int64 v4; // r8
  __int64 v5; // r8
  int v6; // eax
  unsigned int v7; // eax
  struct _EAPTLS_CONTROL_BLOCK **result; // rax
  __int64 v9; // rax
  const std::exception *v10; // [rsp+50h] [rbp-28h] BYREF
  _BYTE v11[32]; // [rsp+58h] [rbp-20h] BYREF
  __int64 v12; // [rsp+88h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_a5891d7b96af3dedb2b00b2a7b992aca_Traceguids, lpValueName);
  try
  {
    wil::reg::open_unique_key();
    v12 = 0;
    phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v12);
    Key = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Deleted-Profiles\\",
            0,
            0,
            1u,
            0x2001Fu,
            0,
            phkResult,
            0);
    if ( Key )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_a5891d7b96af3dedb2b00b2a7b992aca_Traceguids, Key);
    }
    else
    {
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(v11);
      if ( (int)wil::reg::get_value_binary_nothrow(hKey, lpValueName, v4, v11) >= 0 )
      {
        v6 = wil::reg::set_value_binary_nothrow(v12, lpValueName, v5, v11);
        if ( v6 < 0 && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            WPP_a5891d7b96af3dedb2b00b2a7b992aca_Traceguids,
            (unsigned int)v6);
      }
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(v11);
    }
    v7 = RegDeleteValueW(hKey, lpValueName);
    if ( v7 && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_a5891d7b96af3dedb2b00b2a7b992aca_Traceguids, v7);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v12);
    result = (struct _EAPTLS_CONTROL_BLOCK **)wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  catch ( const std::exception *v10 )
  {
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v9 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v10 + 8LL))(v10);
      return (struct _EAPTLS_CONTROL_BLOCK **)WPP_SF_s(
                                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                                22,
                                                WPP_a5891d7b96af3dedb2b00b2a7b992aca_Traceguids,
                                                v9);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180067370  mov     [rsp+arg_0], rbx
0x180067375  push    rdi
0x180067376  sub     rsp, 70h
0x18006737a  mov     rbx, rcx
0x18006737d  lea     rdi, WPP_GLOBAL_Control
0x180067384  mov     rcx, cs:WPP_GLOBAL_Control
0x18006738b  cmp     rcx, rdi
0x18006738e  jz      short loc_1800673A8
0x180067390  mov     edx, 12h
0x180067395  mov     r9, rbx
0x180067398  lea     r8, WPP_a5891d7b96af3dedb2b00b2a7b992aca_Traceguids
0x18006739f  mov     rcx, [rcx+10h]
0x1800673a3  call    WPP_SF_S
0x1800673a8  mov     r9d, 1
0x1800673ae  lea     rcx, [rsp+78h+hKey]
0x1800673b6  call    ?open_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEBGW4key_access@12@@Z; wil::reg::open_unique_key(HKEY__ *,ushort const *,wil::reg::key_access)
0x1800673bb  mov     [rsp+78h+arg_8], 0
0x1800673c7  lea     rcx, [rsp+78h+arg_8]
0x1800673cf  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800673d4  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x1800673dd  mov     [rsp+78h+phkResult], rax; phkResult
0x1800673e2  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800673eb  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x1800673f3  mov     [rsp+78h+dwOptions], 1; dwOptions
0x1800673fb  xor     r9d, r9d; lpClass
0x1800673fe  xor     r8d, r8d; Reserved
0x180067401  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x180067408  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006740f  call    cs:__imp_RegCreateKeyExW
0x180067416  nop     dword ptr [rax+rax+00h]
0x18006741b  test    eax, eax
0x18006741d  jnz     short loc_18006748B
0x18006741f  lea     rcx, [rsp+78h+var_20]
0x180067424  call    ??0?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)
0x180067429  lea     r9, [rsp+78h+var_20]
0x18006742e  mov     rdx, rbx
0x180067431  mov     rcx, [rsp+78h+hKey]
0x180067439  call    ?get_value_binary_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGIAEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@2@@Z; wil::reg::get_value_binary_nothrow(HKEY__ *,ushort const *,uint,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &)
0x18006743e  test    eax, eax
0x180067440  js      short loc_18006747F
0x180067442  lea     r9, [rsp+78h+var_20]
0x180067447  mov     rdx, rbx
0x18006744a  mov     rcx, [rsp+78h+arg_8]
0x180067452  call    ?set_value_binary_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGIAEBV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@2@@Z; wil::reg::set_value_binary_nothrow(HKEY__ *,ushort const *,uint,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> const &)
0x180067457  test    eax, eax
0x180067459  jns     short loc_18006747F
0x18006745b  mov     rcx, cs:WPP_GLOBAL_Control
0x180067462  cmp     rcx, rdi
0x180067465  jz      short loc_18006747F
0x180067467  mov     edx, 13h
0x18006746c  mov     r9d, eax
0x18006746f  lea     r8, WPP_a5891d7b96af3dedb2b00b2a7b992aca_Traceguids
0x180067476  mov     rcx, [rcx+10h]
0x18006747a  call    WPP_SF_d
0x18006747f  lea     rcx, [rsp+78h+var_20]
0x180067484  call    ??1?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)
0x180067489  jmp     short loc_1800674AF
0x18006748b  mov     rcx, cs:WPP_GLOBAL_Control
0x180067492  cmp     rcx, rdi
0x180067495  jz      short loc_1800674AF
0x180067497  mov     edx, 14h
0x18006749c  mov     r9d, eax
0x18006749f  lea     r8, WPP_a5891d7b96af3dedb2b00b2a7b992aca_Traceguids
0x1800674a6  mov     rcx, [rcx+10h]
0x1800674aa  call    WPP_SF_d
0x1800674af  mov     rdx, rbx; lpValueName
0x1800674b2  mov     rcx, [rsp+78h+hKey]; hKey
0x1800674ba  call    cs:__imp_RegDeleteValueW
0x1800674c1  nop     dword ptr [rax+rax+00h]
0x1800674c6  test    eax, eax
0x1800674c8  jz      short loc_18006750A
0x1800674ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800674d1  cmp     rcx, rdi
0x1800674d4  jz      short loc_1800674EE
0x1800674d6  mov     edx, 15h
0x1800674db  mov     r9d, eax
0x1800674de  lea     r8, WPP_a5891d7b96af3dedb2b00b2a7b992aca_Traceguids
0x1800674e5  mov     rcx, [rcx+10h]
0x1800674e9  call    WPP_SF_d
0x1800674ee  lea     rcx, [rsp+78h+arg_8]
0x1800674f6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800674fb  lea     rcx, [rsp+78h+hKey]
0x180067503  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180067508  jmp     short loc_180067527
0x18006750a  lea     rcx, [rsp+78h+arg_8]
0x180067512  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180067517  lea     rcx, [rsp+78h+hKey]
0x18006751f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180067524  nop
0x180067525  jmp     short $+2
0x180067527  mov     rbx, [rsp+78h+arg_0]
0x18006752f  add     rsp, 70h
0x180067533  pop     rdi
0x180067534  retn
```
