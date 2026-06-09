# RasEapDeleteTimeStampWchar

- ea: `0x180063920`
- end: `0x180063ada`
- name: `RasEapDeleteTimeStampWchar`
- size: `442`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task`

## callees

- `0x180004bd0`
- `0x18000f350`
- `0x180027840`
- `0x180029380`
- `0x180029424`
- `0x180062634`
- `0x180062908`
- `0x1800636c8`
- `0x1800638b4`
- `0x180063920`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800639bf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800639bf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180063a64`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180063a64`

## string_xrefs

- `0x1800639b1`: `SYSTEM\CurrentControlSet\Services\RasMan\Deleted-Profiles\`

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
0x180063920  mov     [rsp+arg_0], rbx
0x180063925  push    rdi
0x180063926  sub     rsp, 70h
0x18006392a  mov     rbx, rcx
0x18006392d  lea     rdi, WPP_GLOBAL_Control
0x180063934  mov     rcx, cs:WPP_GLOBAL_Control
0x18006393b  cmp     rcx, rdi
0x18006393e  jz      short loc_180063958
0x180063940  mov     edx, 12h
0x180063945  mov     r9, rbx
0x180063948  lea     r8, WPP_a5891d7b96af3dedb2b00b2a7b992aca_Traceguids
0x18006394f  mov     rcx, [rcx+10h]
0x180063953  call    WPP_SF_S
0x180063958  mov     r9d, 1
0x18006395e  lea     rcx, [rsp+78h+hKey]
0x180063966  call    ?open_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEBGW4key_access@12@@Z; wil::reg::open_unique_key(HKEY__ *,ushort const *,wil::reg::key_access)
0x18006396b  mov     [rsp+78h+arg_8], 0
0x180063977  lea     rcx, [rsp+78h+arg_8]
0x18006397f  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180063984  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x18006398d  mov     [rsp+78h+phkResult], rax; phkResult
0x180063992  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006399b  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x1800639a3  mov     [rsp+78h+dwOptions], 1; dwOptions
0x1800639ab  xor     r9d, r9d; lpClass
0x1800639ae  xor     r8d, r8d; Reserved
0x1800639b1  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800639b8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800639bf  call    cs:__imp_RegCreateKeyExW
0x1800639c5  test    eax, eax
0x1800639c7  jnz     short loc_180063A35
0x1800639c9  lea     rcx, [rsp+78h+var_20]
0x1800639ce  call    ??0?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)
0x1800639d3  lea     r9, [rsp+78h+var_20]
0x1800639d8  mov     rdx, rbx
0x1800639db  mov     rcx, [rsp+78h+hKey]
0x1800639e3  call    ?get_value_binary_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGIAEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@2@@Z; wil::reg::get_value_binary_nothrow(HKEY__ *,ushort const *,uint,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &)
0x1800639e8  test    eax, eax
0x1800639ea  js      short loc_180063A29
0x1800639ec  lea     r9, [rsp+78h+var_20]
0x1800639f1  mov     rdx, rbx
0x1800639f4  mov     rcx, [rsp+78h+arg_8]
0x1800639fc  call    ?set_value_binary_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGIAEBV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@2@@Z; wil::reg::set_value_binary_nothrow(HKEY__ *,ushort const *,uint,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> const &)
0x180063a01  test    eax, eax
0x180063a03  jns     short loc_180063A29
0x180063a05  mov     rcx, cs:WPP_GLOBAL_Control
0x180063a0c  cmp     rcx, rdi
0x180063a0f  jz      short loc_180063A29
0x180063a11  mov     edx, 13h
0x180063a16  mov     r9d, eax
0x180063a19  lea     r8, WPP_a5891d7b96af3dedb2b00b2a7b992aca_Traceguids
0x180063a20  mov     rcx, [rcx+10h]
0x180063a24  call    WPP_SF_d
0x180063a29  lea     rcx, [rsp+78h+var_20]
0x180063a2e  call    ??1?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)
0x180063a33  jmp     short loc_180063A59
0x180063a35  mov     rcx, cs:WPP_GLOBAL_Control
0x180063a3c  cmp     rcx, rdi
0x180063a3f  jz      short loc_180063A59
0x180063a41  mov     edx, 14h
0x180063a46  mov     r9d, eax
0x180063a49  lea     r8, WPP_a5891d7b96af3dedb2b00b2a7b992aca_Traceguids
0x180063a50  mov     rcx, [rcx+10h]
0x180063a54  call    WPP_SF_d
0x180063a59  mov     rdx, rbx; lpValueName
0x180063a5c  mov     rcx, [rsp+78h+hKey]; hKey
0x180063a64  call    cs:__imp_RegDeleteValueW
0x180063a6a  test    eax, eax
0x180063a6c  jz      short loc_180063AAE
0x180063a6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180063a75  cmp     rcx, rdi
0x180063a78  jz      short loc_180063A92
0x180063a7a  mov     edx, 15h
0x180063a7f  mov     r9d, eax
0x180063a82  lea     r8, WPP_a5891d7b96af3dedb2b00b2a7b992aca_Traceguids
0x180063a89  mov     rcx, [rcx+10h]
0x180063a8d  call    WPP_SF_d
0x180063a92  lea     rcx, [rsp+78h+arg_8]
0x180063a9a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180063a9f  lea     rcx, [rsp+78h+hKey]
0x180063aa7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180063aac  jmp     short loc_180063ACB
0x180063aae  lea     rcx, [rsp+78h+arg_8]
0x180063ab6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180063abb  lea     rcx, [rsp+78h+hKey]
0x180063ac3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180063ac8  nop
0x180063ac9  jmp     short $+2
0x180063acb  mov     rbx, [rsp+78h+arg_0]
0x180063ad3  add     rsp, 70h
0x180063ad7  pop     rdi
0x180063ad8  retn
```
