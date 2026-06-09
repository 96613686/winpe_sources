# DusmStore::SetAttributionMapping(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,int)

- ea: `0x18002ab28`
- end: `0x18002ad14`
- name: `?SetAttributionMapping@DusmStore@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0H@Z`
- size: `492`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800158d0`

## callees

- `0x180007c90`
- `0x18000e828`
- `0x18000f094`
- `0x180012fcc`
- `0x180025ac4`
- `0x180026cd4`
- `0x180026fa0`
- `0x180027000`
- `0x1800273f0`
- `0x180027528`
- `0x18002ab28`
- `0x18002d1cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ab67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ab67`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002ac75`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002ac98`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002ac75`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002ac98`

## pseudocode

```c
__int64 __fastcall DusmStore::SetAttributionMapping(__int64 a1, __int64 a2, int a3)
{
  LPCRITICAL_SECTION v6; // rbx
  __int64 v7; // rax
  WcmCommon::Registry::Path *v8; // rax
  WcmCommon::Registry::Path *appended; // rax
  const struct Path *v10; // rax
  __int64 v11; // rax
  WcmCommon::Registry::Path *v12; // rax
  WcmCommon::Registry::Path *v13; // rax
  const struct Path *v14; // rax
  const WCHAR *v15; // rdx
  const wchar_t *v16; // rax
  const wchar_t *v17; // r8
  HKEY *p_hKey; // rcx
  LPCRITICAL_SECTION v20; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v21[32]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v22[32]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v23[48]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v24[48]; // [rsp+98h] [rbp-68h] BYREF
  HKEY hKey; // [rsp+C8h] [rbp-38h] BYREF
  HKEY v26; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD v27[3]; // [rsp+D8h] [rbp-28h] BYREF
  _OWORD v28[3]; // [rsp+108h] [rbp+8h] BYREF

  v6 = DusmStore::s_pInstance + 1;
  EnterCriticalSection(DusmStore::s_pInstance + 1);
  v20 = v6;
  memset(v28, 0, sizeof(v28));
  v7 = std::wstring::wstring(v21, qword_180068EC8);
  v8 = (WcmCommon::Registry::Path *)WcmCommon::Registry::Path::Create<-2147483646>(v23, v7);
  appended = WcmCommon::Registry::Path::AppendPath(v8, L"AttributionMappings");
  v10 = WcmCommon::Registry::Path::AppendPath(appended, L"Free");
  WcmCommon::Registry::Path::Path((WcmCommon::Registry::Path *)v28, v10);
  WcmCommon::Registry::Path::~Path((WcmCommon::Registry::Path *)v23);
  memset(v27, 0, sizeof(v27));
  v11 = std::wstring::wstring(v22, qword_180068EC8);
  v12 = (WcmCommon::Registry::Path *)WcmCommon::Registry::Path::Create<-2147483646>(v24, v11);
  v13 = WcmCommon::Registry::Path::AppendPath(v12, L"AttributionMappings");
  v14 = WcmCommon::Registry::Path::AppendPath(v13, L"Costed");
  WcmCommon::Registry::Path::Path((WcmCommon::Registry::Path *)v27, v14);
  WcmCommon::Registry::Path::~Path((WcmCommon::Registry::Path *)v24);
  hKey = 0;
  WcmCommon::Registry::CreateKeyRW(&hKey, v28);
  v26 = 0;
  WcmCommon::Registry::CreateKeyRW(&v26, v27);
  v15 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1);
  if ( a3 )
  {
    RegDeleteValueW(hKey, v15);
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
    v16 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1);
    p_hKey = &v26;
  }
  else
  {
    RegDeleteValueW(v26, v15);
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
    v16 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1);
    p_hKey = &hKey;
  }
  WcmCommon::Registry::Key::SetSzValue((WcmCommon::Registry::Key *)p_hKey, v16, v17);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  WcmCommon::Registry::Path::~Path((WcmCommon::Registry::Path *)v27);
  WcmCommon::Registry::Path::~Path((WcmCommon::Registry::Path *)v28);
  return wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v20);
}

```

## disassembly

```asm
0x18002ab28  mov     [rsp-8+arg_10], rbx
0x18002ab2d  mov     [rsp-8+arg_18], rsi
0x18002ab32  push    rbp
0x18002ab33  push    rdi
0x18002ab34  push    r14
0x18002ab36  lea     rbp, [rsp-40h]
0x18002ab3b  sub     rsp, 140h
0x18002ab42  mov     rax, cs:__security_cookie
0x18002ab49  xor     rax, rsp
0x18002ab4c  mov     [rbp+50h+var_18], rax
0x18002ab50  mov     edi, r8d
0x18002ab53  mov     r14, rdx
0x18002ab56  mov     rsi, rcx
0x18002ab59  mov     rbx, cs:?s_pInstance@DusmStore@@0PEAV1@EA; DusmStore * DusmStore::s_pInstance
0x18002ab60  add     rbx, 28h ; '('
0x18002ab64  mov     rcx, rbx; lpCriticalSection
0x18002ab67  call    cs:__imp_EnterCriticalSection
0x18002ab6d  mov     [rsp+150h+var_130], rbx
0x18002ab72  xorps   xmm0, xmm0
0x18002ab75  movups  [rbp+50h+var_48], xmm0
0x18002ab79  movups  [rbp+50h+var_38], xmm0
0x18002ab7d  movups  [rbp+50h+var_28], xmm0
0x18002ab81  mov     rdx, cs:qword_180068EC8
0x18002ab88  lea     rcx, [rsp+150h+var_128]
0x18002ab8d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002ab92  mov     rdx, rax
0x18002ab95  lea     rcx, [rsp+150h+var_E8]
0x18002ab9a  call    ??$Create@$0?HPPPPPPO@@Path@Registry@WcmCommon@@SA?AV012@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; WcmCommon::Registry::Path::Create<-2147483646>(std::wstring)
0x18002ab9f  nop
0x18002aba0  lea     rdx, aAttributionmap; "AttributionMappings"
0x18002aba7  mov     rcx, rax; this
0x18002abaa  call    ?AppendPath@Path@Registry@WcmCommon@@QEAAAEAV123@PEB_W@Z; WcmCommon::Registry::Path::AppendPath(wchar_t const *)
0x18002abaf  lea     rdx, aFree; "Free"
0x18002abb6  mov     rcx, rax; this
0x18002abb9  call    ?AppendPath@Path@Registry@WcmCommon@@QEAAAEAV123@PEB_W@Z; WcmCommon::Registry::Path::AppendPath(wchar_t const *)
0x18002abbe  mov     rdx, rax; struct Path *
0x18002abc1  lea     rcx, [rbp+50h+var_48]; this
0x18002abc5  call    ??0Path@Registry@WcmCommon@@QEAA@AEBV012@@Z; WcmCommon::Registry::Path::Path(WcmCommon::Registry::Path const &)
0x18002abca  nop
0x18002abcb  lea     rcx, [rsp+150h+var_E8]; this
0x18002abd0  call    ??1Path@Registry@WcmCommon@@QEAA@XZ; WcmCommon::Registry::Path::~Path(void)
0x18002abd5  xorps   xmm0, xmm0
0x18002abd8  movups  [rbp+50h+var_78], xmm0
0x18002abdc  movups  [rbp+50h+var_68], xmm0
0x18002abe0  movups  [rbp+50h+var_58], xmm0
0x18002abe4  mov     rdx, cs:qword_180068EC8
0x18002abeb  lea     rcx, [rsp+150h+var_108]
0x18002abf0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002abf5  mov     rdx, rax
0x18002abf8  lea     rcx, [rbp+50h+var_B8]
0x18002abfc  call    ??$Create@$0?HPPPPPPO@@Path@Registry@WcmCommon@@SA?AV012@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; WcmCommon::Registry::Path::Create<-2147483646>(std::wstring)
0x18002ac01  nop
0x18002ac02  lea     rdx, aAttributionmap; "AttributionMappings"
0x18002ac09  mov     rcx, rax; this
0x18002ac0c  call    ?AppendPath@Path@Registry@WcmCommon@@QEAAAEAV123@PEB_W@Z; WcmCommon::Registry::Path::AppendPath(wchar_t const *)
0x18002ac11  lea     rdx, aCosted; "Costed"
0x18002ac18  mov     rcx, rax; this
0x18002ac1b  call    ?AppendPath@Path@Registry@WcmCommon@@QEAAAEAV123@PEB_W@Z; WcmCommon::Registry::Path::AppendPath(wchar_t const *)
0x18002ac20  mov     rdx, rax; struct Path *
0x18002ac23  lea     rcx, [rbp+50h+var_78]; this
0x18002ac27  call    ??0Path@Registry@WcmCommon@@QEAA@AEBV012@@Z; WcmCommon::Registry::Path::Path(WcmCommon::Registry::Path const &)
0x18002ac2c  nop
0x18002ac2d  lea     rcx, [rbp+50h+var_B8]; this
0x18002ac31  call    ??1Path@Registry@WcmCommon@@QEAA@XZ; WcmCommon::Registry::Path::~Path(void)
0x18002ac36  mov     [rbp+50h+hKey], 0
0x18002ac3e  lea     rdx, [rbp+50h+var_48]
0x18002ac42  lea     rcx, [rbp+50h+hKey]
0x18002ac46  call    ?CreateKeyRW@Registry@WcmCommon@@YA?AVKey@12@AEBVPath@12@@Z; WcmCommon::Registry::CreateKeyRW(WcmCommon::Registry::Path const &)
0x18002ac4b  nop
0x18002ac4c  mov     [rbp+50h+var_80], 0
0x18002ac54  lea     rdx, [rbp+50h+var_78]
0x18002ac58  lea     rcx, [rbp+50h+var_80]
0x18002ac5c  call    ?CreateKeyRW@Registry@WcmCommon@@YA?AVKey@12@AEBVPath@12@@Z; WcmCommon::Registry::CreateKeyRW(WcmCommon::Registry::Path const &)
0x18002ac61  nop
0x18002ac62  mov     rcx, rsi
0x18002ac65  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002ac6a  mov     rdx, rax; lpValueName
0x18002ac6d  test    edi, edi
0x18002ac6f  jz      short loc_18002AC94
0x18002ac71  mov     rcx, [rbp+50h+hKey]; hKey
0x18002ac75  call    cs:__imp_RegDeleteValueW
0x18002ac7b  mov     rcx, r14
0x18002ac7e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002ac83  mov     r8, rax
0x18002ac86  mov     rcx, rsi
0x18002ac89  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002ac8e  lea     rcx, [rbp+50h+var_80]
0x18002ac92  jmp     short loc_18002ACB5
0x18002ac94  mov     rcx, [rbp+50h+var_80]; hKey
0x18002ac98  call    cs:__imp_RegDeleteValueW
0x18002ac9e  mov     rcx, r14
0x18002aca1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002aca6  mov     r8, rax
0x18002aca9  mov     rcx, rsi
0x18002acac  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002acb1  lea     rcx, [rbp+50h+hKey]; this
0x18002acb5  mov     rdx, rax; wchar_t *
0x18002acb8  call    ?SetSzValue@Key@Registry@WcmCommon@@QEAAXQEB_W0@Z; WcmCommon::Registry::Key::SetSzValue(wchar_t const * const,wchar_t const * const)
0x18002acbd  nop
0x18002acbe  lea     rcx, [rbp+50h+var_80]
0x18002acc2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002acc7  nop
0x18002acc8  lea     rcx, [rbp+50h+hKey]
0x18002accc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002acd1  nop
0x18002acd2  lea     rcx, [rbp+50h+var_78]; this
0x18002acd6  call    ??1Path@Registry@WcmCommon@@QEAA@XZ; WcmCommon::Registry::Path::~Path(void)
0x18002acdb  nop
0x18002acdc  lea     rcx, [rbp+50h+var_48]; this
0x18002ace0  call    ??1Path@Registry@WcmCommon@@QEAA@XZ; WcmCommon::Registry::Path::~Path(void)
0x18002ace5  nop
0x18002ace6  lea     rcx, [rsp+150h+var_130]
0x18002aceb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002acf0  mov     rcx, [rbp+50h+var_18]
0x18002acf4  xor     rcx, rsp; StackCookie
0x18002acf7  call    __security_check_cookie
0x18002acfc  lea     r11, [rsp+150h+var_10]
0x18002ad04  mov     rbx, [r11+30h]
0x18002ad08  mov     rsi, [r11+38h]
0x18002ad0c  mov     rsp, r11
0x18002ad0f  pop     r14
0x18002ad11  pop     rdi
0x18002ad12  pop     rbp
0x18002ad13  retn
```
