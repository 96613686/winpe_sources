# ToastHelper::_CreateToast(bool,unsigned __int64)

- ea: `0x18002e7a4`
- end: `0x18002edac`
- name: `?_CreateToast@ToastHelper@@AEAA?AUToast@@_N_K@Z`
- size: `1544`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, char, __int64)`
- caller_count: `1`
- callee_count: `35`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002f3c8`

## callees

- `0x1800025f0`
- `0x18000a00c`
- `0x18001bcd8`
- `0x1800283bc`
- `0x180028458`
- `0x1800284f4`
- `0x180028590`
- `0x1800287e4`
- `0x180029e2c`
- `0x18002a090`
- `0x18002aad0`
- `0x18002ab78`
- `0x18002ac9c`
- `0x18002acf4`
- `0x18002b484`
- `0x18002b560`
- `0x18002b5b8`
- `0x18002b610`
- `0x18002b668`
- `0x18002bba4`
- `0x18002bdf0`
- `0x18002c304`
- `0x18002c62c`
- `0x18002c864`
- `0x18002cb88`
- `0x18002cc3c`
- `0x18002d030`
- `0x18002e7a4`
- `0x18002ee2c`
- `0x18002f140`
- `0x18002f23c`
- `0x18002f388`
- `0x18002fbf4`
- `0x18002fcb0`
- `0x180040010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002e809`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002e839`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002e86b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002e89d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002e809`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002e839`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002e86b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002e89d`

## string_xrefs

- `0x18002e95d`: `        <binding template="ToastGeneric">`

## pseudocode

```c
_QWORD *__fastcall ToastHelper::_CreateToast(__int64 a1, _QWORD *a2, char a3, __int64 a4)
{
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int v9; // r8d
  const char *v10; // r9
  unsigned int v11; // r8d
  const char *v12; // r9
  unsigned int v13; // r8d
  const char *v14; // r9
  const wchar_t *v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  const unsigned __int16 *v24; // rax
  void (__fastcall ***v25)(_QWORD, __int64 *, __int64 **); // rcx
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // r8
  __int64 *v29; // rax
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // r8
  __int64 *v34; // rax
  __int64 v35; // r8
  __int64 v36; // rdx
  __int64 v37; // rax
  __int64 v38; // r8
  __int64 *v39; // rax
  __int64 v40; // r8
  __int64 v41; // rdx
  __int64 v43; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v44; // [rsp+30h] [rbp-D0h] BYREF
  void (__fastcall *v45)(__int64, __int64 *); // [rsp+38h] [rbp-C8h] BYREF
  std::_Ref_count_base *v46; // [rsp+40h] [rbp-C0h]
  __int64 v47; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall *v48)(_QWORD, _QWORD); // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v51[7]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v52[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v53[232]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v54[16]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int64 v55; // [rsp+1A0h] [rbp+A0h]
  WCHAR Buffer[128]; // [rsp+1B0h] [rbp+B0h] BYREF
  WCHAR v57[128]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR v58[128]; // [rsp+3B0h] [rbp+2B0h] BYREF
  WCHAR v59[128]; // [rsp+4B0h] [rbp+3B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5F8h] [rbp+4F8h]

  v51[5] = a2;
  v44 = a4;
  if ( !LoadStringW(g_hInstance, 0x4B1u, Buffer, 128) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xFB, v7, v8);
  if ( !LoadStringW(g_hInstance, 0x4B2u, v57, 128) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xFC, v9, v10);
  if ( !LoadStringW(g_hInstance, 0x4B3u, v58, 128) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xFD, v11, v12);
  if ( !LoadStringW(g_hInstance, 0x4B4u, v59, 128) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xFE, v13, v14);
  v45 = (void (__fastcall *)(__int64, __int64 *))&qword_180053038;
  _InterlockedIncrement64(&qword_180053038);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory> )
  {
    winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Data::Xml::Dom::XmlDocument>(
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>,
      &v50);
    _InterlockedDecrement64(&qword_180053038);
  }
  else
  {
    _InterlockedDecrement64(&qword_180053038);
    v45 = (void (__fastcall *)(__int64, __int64 *))_lambda_e39067982572d3667926157dc9eb0f0a_::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Xml::Dom::XmlDocument (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      (void (__fastcall ***)(_QWORD, __int64 *, __int64 **))retaddr,
      (__int64)&v50,
      &v45);
  }
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v52);
  v15 = L"<toast scenario=\"Reminder\">";
  if ( !a3 )
    v15 = L"<toast>";
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v52, v15);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v52, L"    <visual>");
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v52, L"        <binding template=\"ToastGeneric\">");
  v16 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v52, L"            <text hint-style=\"body\">");
  v17 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v16, Buffer);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v17, L"</text>");
  v18 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v52, L"            <text>");
  v19 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18, v57);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v19, L"</text>");
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v52, L"        </binding>");
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v52, L"    </visual>");
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v52, L"    <actions>");
  v20 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          v52,
          L"        <action activationType=\"Background\" arguments=\"signIn\" content=\"");
  v21 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v20, v58);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v21, L"\"/>");
  v22 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          v52,
          L"        <action activationType=\"Background\" arguments=\"notNow\" content=\"");
  v23 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v22, v59);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v23, L"\"/>");
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v52, L"    </actions>");
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v52, L"</toast>");
  std::wstring::wstring(v54);
  std::basic_stringbuf<unsigned short>::_Get_buffer_view(v53, &v47);
  if ( v47 )
    std::wstring::assign(v54, v47, v48);
  v24 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v54);
  winrt::param::hstring::create_string_reference((winrt::param::hstring *)v51, v24, v55);
  winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(
    &v50,
    v51);
  std::wstring::_Tidy_deallocate(v54);
  v45 = (void (__fastcall *)(__int64, __int64 *))&v50;
  v51[0] = &qword_180052B18;
  _InterlockedIncrement64(&qword_180052B18);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory> )
  {
    _lambda_51cb1c784431ef1021794bfebdc3ae41_::operator()(
      &v45,
      &v43,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>);
    _InterlockedDecrement64(&qword_180052B18);
  }
  else
  {
    _InterlockedDecrement64(&qword_180052B18);
    winrt::impl::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>::call<_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_ &>(
      v25,
      (__int64)&v43,
      (__int64)&v45);
  }
  v26 = v43;
  *a2 = v43;
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
  a2[1] = 0;
  a2[2] = 0;
  a2[3] = 0;
  a2[4] = 0;
  a2[5] = 0;
  a2[6] = 0;
  a2[7] = 0;
  a2[8] = 0;
  a2[9] = 0;
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v43);
  winrt::impl::consume_Windows_UI_Notifications_IToastNotification6<winrt::Windows::UI::Notifications::ToastNotification>::ExpiresOnReboot(a2);
  std::weak_ptr<ToastHelper>::weak_ptr<ToastHelper>(&v45, a1);
  v27 = lambda_cbd528d856f4286070fe657a860472db_::_lambda_cbd528d856f4286070fe657a860472db_(v54, &v45, &v44);
  winrt::Windows::Foundation::TypedEventHandler_winrt::Windows::UI::Notifications::ToastNotification_winrt::Windows::Foundation::IInspectable_::TypedEventHandler_winrt::Windows::UI::Notifications::ToastNotification_winrt::Windows::Foundation::IInspectable___lambda_6ab50ef37ae315c1111a87d1b311a614___(
    &v43,
    v27);
  v29 = (__int64 *)winrt::impl::consume_Windows_UI_Notifications_IToastNotification<winrt::Windows::UI::Notifications::IToastNotification>::Activated(
                     a2,
                     v51,
                     v28,
                     &v43);
  v30 = v29[1];
  v31 = *v29;
  *v29 = 0;
  v47 = v31;
  v48 =  winrt::impl::abi<winrt::Windows::UI::Notifications::IToastNotification,void>::type::`vcall'{96,{flat}};
  v49 = v30;
  winrt::event_revoker<winrt::Windows::UI::Notifications::IToastNotification>::operator=(a2 + 1, &v47);
  winrt::event_revoker<winrt::Windows::UI::Notifications::IToastNotification>::~event_revoker<winrt::Windows::UI::Notifications::IToastNotification>(&v47);
  __1__event_revoker_UIToastNotification_Notifications_UI_Windows_winrt___MP8type___abi_UIToastNotification_Notifications_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BGA_AA_impl_winrt__QEAA_XZ(v51);
  if ( v43 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v43);
  v32 = lambda_cbd528d856f4286070fe657a860472db_::_lambda_cbd528d856f4286070fe657a860472db_(v54, &v45, &v44);
  winrt::Windows::Foundation::TypedEventHandler_winrt::Windows::UI::Notifications::ToastNotification_winrt::Windows::UI::Notifications::ToastDismissedEventArgs_::TypedEventHandler_winrt::Windows::UI::Notifications::ToastNotification_winrt::Windows::UI::Notifications::ToastDismissedEventArgs___lambda_3b6b1f727379048c7fa4c51e93a88699___(
    &v43,
    v32);
  v34 = (__int64 *)winrt::impl::consume_Windows_UI_Notifications_IToastNotification<winrt::Windows::UI::Notifications::IToastNotification>::Dismissed(
                     a2,
                     v51,
                     v33,
                     &v43);
  v35 = v34[1];
  v36 = *v34;
  *v34 = 0;
  v47 = v36;
  v48 =  winrt::impl::abi<winrt::Windows::UI::Notifications::IToastNotification,void>::type::`vcall'{80,{flat}};
  v49 = v35;
  winrt::event_revoker<winrt::Windows::UI::Notifications::IToastNotification>::operator=(a2 + 4, &v47);
  winrt::event_revoker<winrt::Windows::UI::Notifications::IToastNotification>::~event_revoker<winrt::Windows::UI::Notifications::IToastNotification>(&v47);
  __1__event_revoker_UIToastNotification_Notifications_UI_Windows_winrt___MP8type___abi_UIToastNotification_Notifications_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BFA_AA_impl_winrt__QEAA_XZ(v51);
  if ( v43 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v43);
  v37 = lambda_cbd528d856f4286070fe657a860472db_::_lambda_cbd528d856f4286070fe657a860472db_(v54, &v45, &v44);
  winrt::Windows::Foundation::TypedEventHandler_winrt::Windows::UI::Notifications::ToastNotification_winrt::Windows::UI::Notifications::ToastFailedEventArgs_::TypedEventHandler_winrt::Windows::UI::Notifications::ToastNotification_winrt::Windows::UI::Notifications::ToastFailedEventArgs___lambda_cbd528d856f4286070fe657a860472db___(
    &v44,
    v37);
  v39 = (__int64 *)winrt::impl::consume_Windows_UI_Notifications_IToastNotification<winrt::Windows::UI::Notifications::IToastNotification>::Failed(
                     a2,
                     v51,
                     v38,
                     &v44);
  v40 = v39[1];
  v41 = *v39;
  *v39 = 0;
  v47 = v41;
  v48 =  winrt::impl::abi<winrt::Windows::UI::Notifications::IToastNotification,void>::type::`vcall'{112,{flat}};
  v49 = v40;
  winrt::event_revoker<winrt::Windows::UI::Notifications::IToastNotification>::operator=(a2 + 7, &v47);
  winrt::event_revoker<winrt::Windows::UI::Notifications::IToastNotification>::~event_revoker<winrt::Windows::UI::Notifications::IToastNotification>(&v47);
  __1__event_revoker_UIToastNotification_Notifications_UI_Windows_winrt___MP8type___abi_UIToastNotification_Notifications_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BHA_AA_impl_winrt__QEAA_XZ(v51);
  if ( v44 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v44);
  if ( v46 )
    std::_Ref_count_base::_Decwref(v46);
  std::basic_ostringstream<unsigned short>::`vbase destructor'(v52);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v50);
  return a2;
}

```

## disassembly

```asm
0x18002e7a4  mov     [rsp-8+arg_10], rbx
0x18002e7a9  push    rbp
0x18002e7aa  push    rsi
0x18002e7ab  push    rdi
0x18002e7ac  push    r12
0x18002e7ae  push    r13
0x18002e7b0  push    r14
0x18002e7b2  push    r15
0x18002e7b4  lea     rbp, [rsp-4C0h]
0x18002e7bc  sub     rsp, 5C0h
0x18002e7c3  mov     rax, cs:__security_cookie
0x18002e7ca  xor     rax, rsp
0x18002e7cd  mov     [rbp+4F0h+var_40], rax
0x18002e7d4  mov     bl, r8b
0x18002e7d7  mov     rsi, rdx
0x18002e7da  mov     r12, rcx
0x18002e7dd  mov     [rbp+4F0h+var_560], rdx
0x18002e7e1  mov     [rsp+5F0h+var_5C0], r9
0x18002e7e6  xor     r13d, r13d
0x18002e7e9  mov     [rsp+5F0h+var_5D0], r13d
0x18002e7ee  mov     edi, 80h
0x18002e7f3  mov     r9d, edi; cchBufferMax
0x18002e7f6  lea     r8, [rbp+4F0h+Buffer]; lpBuffer
0x18002e7fd  mov     edx, 4B1h; uID
0x18002e802  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18002e809  call    cs:__imp_LoadStringW
0x18002e80f  mov     rcx, [rbp+4F8h]; this
0x18002e816  test    eax, eax
0x18002e818  jnz     short loc_18002E823
0x18002e81a  lea     edx, [rdi+7Bh]; void *
0x18002e81d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002e823  mov     r9d, edi; cchBufferMax
0x18002e826  lea     r8, [rbp+4F0h+var_340]; lpBuffer
0x18002e82d  mov     edx, 4B2h; uID
0x18002e832  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18002e839  call    cs:__imp_LoadStringW
0x18002e83f  mov     rcx, [rbp+4F8h]; this
0x18002e846  test    eax, eax
0x18002e848  jnz     short loc_18002E855
0x18002e84a  mov     edx, 0FCh; void *
0x18002e84f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002e855  mov     r9d, edi; cchBufferMax
0x18002e858  lea     r8, [rbp+4F0h+var_240]; lpBuffer
0x18002e85f  mov     edx, 4B3h; uID
0x18002e864  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18002e86b  call    cs:__imp_LoadStringW
0x18002e871  mov     rcx, [rbp+4F8h]; this
0x18002e878  test    eax, eax
0x18002e87a  jnz     short loc_18002E887
0x18002e87c  mov     edx, 0FDh; void *
0x18002e881  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002e887  mov     r9d, edi; cchBufferMax
0x18002e88a  lea     r8, [rbp+4F0h+var_140]; lpBuffer
0x18002e891  mov     edx, 4B4h; uID
0x18002e896  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18002e89d  call    cs:__imp_LoadStringW
0x18002e8a3  mov     rcx, [rbp+4F8h]; this
0x18002e8aa  test    eax, eax
0x18002e8ac  jnz     short loc_18002E8B9
0x18002e8ae  mov     edx, 0FEh; void *
0x18002e8b3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002e8b9  lea     rax, qword_180053038
0x18002e8c0  mov     [rsp+5F0h+var_5B8], rax
0x18002e8c5  lock inc cs:qword_180053038
0x18002e8cd  cmp     cs:??$factory_cache_entry_v@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A, r13; factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>
0x18002e8d4  jz      short loc_18002E8FA
0x18002e8d6  lea     rdx, [rsp+5F0h+var_590]
0x18002e8db  lea     rcx, ??$factory_cache_entry_v@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A; factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>
0x18002e8e2  call    ??$ActivateInstance@UXmlDocument@Dom@Xml@Data@Windows@winrt@@@IActivationFactory@Foundation@Windows@winrt@@QEBA?AUXmlDocument@Dom@Xml@Data@23@XZ; winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Data::Xml::Dom::XmlDocument>(void)
0x18002e8e7  mov     edi, 6
0x18002e8ec  mov     [rsp+5F0h+var_5D0], edi
0x18002e8f0  lock dec cs:qword_180053038
0x18002e8f8  jmp     short loc_18002E926
0x18002e8fa  lock dec cs:qword_180053038
0x18002e902  lea     rax, ?_lambda_invoker_cdecl_@_lambda_e39067982572d3667926157dc9eb0f0a_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_e39067982572d3667926157dc9eb0f0a_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x18002e909  mov     [rsp+5F0h+var_5B8], rax
0x18002e90e  lea     r8, [rsp+5F0h+var_5B8]
0x18002e913  lea     rdx, [rsp+5F0h+var_590]
0x18002e918  call    ??$call@P6A?AUXmlDocument@Dom@Xml@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@56@@Z@?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@QEAA?A_P$$QEAP6A?AUXmlDocument@Dom@Xml@Data@Windows@2@AEBUIActivationFactory@Foundation@72@@Z@Z
0x18002e91d  mov     edi, 2
0x18002e922  mov     [rsp+5F0h+var_5D0], edi
0x18002e926  lea     rcx, [rbp+4F0h+var_550]
0x18002e92a  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18002e92f  nop
0x18002e930  lea     rax, aToast_0; "<toast>"
0x18002e937  lea     rdx, aToastScenarioR; "<toast scenario=\"Reminder\">"
0x18002e93e  test    bl, bl
0x18002e940  cmovz   rdx, rax
0x18002e944  lea     rcx, [rbp+4F0h+var_550]
0x18002e948  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002e94d  lea     rdx, aVisual; "    <visual>"
0x18002e954  lea     rcx, [rbp+4F0h+var_550]
0x18002e958  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002e95d  lea     rdx, aBindingTemplat; "        <binding template=\"ToastGeneri"...
0x18002e964  lea     rcx, [rbp+4F0h+var_550]
0x18002e968  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002e96d  lea     rdx, aTextHintStyleB; "            <text hint-style=\"body\">"
0x18002e974  lea     rcx, [rbp+4F0h+var_550]
0x18002e978  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002e97d  mov     rcx, rax
0x18002e980  lea     rdx, [rbp+4F0h+Buffer]
0x18002e987  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002e98c  mov     rcx, rax
0x18002e98f  lea     rdx, aText; "</text>"
0x18002e996  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002e99b  lea     rdx, aText_0; "            <text>"
0x18002e9a2  lea     rcx, [rbp+4F0h+var_550]
0x18002e9a6  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002e9ab  mov     rcx, rax
0x18002e9ae  lea     rdx, [rbp+4F0h+var_340]
0x18002e9b5  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002e9ba  mov     rcx, rax
0x18002e9bd  lea     rdx, aText; "</text>"
0x18002e9c4  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002e9c9  lea     rdx, aBinding; "        </binding>"
0x18002e9d0  lea     rcx, [rbp+4F0h+var_550]
0x18002e9d4  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002e9d9  lea     rdx, aVisual_0; "    </visual>"
0x18002e9e0  lea     rcx, [rbp+4F0h+var_550]
0x18002e9e4  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002e9e9  lea     rdx, aActions; "    <actions>"
0x18002e9f0  lea     rcx, [rbp+4F0h+var_550]
0x18002e9f4  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002e9f9  lea     rdx, aActionActivati_0; "        <action activationType=\"Backgr"...
0x18002ea00  lea     rcx, [rbp+4F0h+var_550]
0x18002ea04  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002ea09  mov     rcx, rax
0x18002ea0c  lea     rdx, [rbp+4F0h+var_240]
0x18002ea13  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002ea18  mov     rcx, rax
0x18002ea1b  lea     rdx, asc_180046680; "\"/>"
0x18002ea22  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002ea27  lea     rdx, aActionActivati; "        <action activationType=\"Backgr"...
0x18002ea2e  lea     rcx, [rbp+4F0h+var_550]
0x18002ea32  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002ea37  mov     rcx, rax
0x18002ea3a  lea     rdx, [rbp+4F0h+var_140]
0x18002ea41  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002ea46  mov     rcx, rax
0x18002ea49  lea     rdx, asc_180046680; "\"/>"
0x18002ea50  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002ea55  lea     rdx, aActions_0; "    </actions>"
0x18002ea5c  lea     rcx, [rbp+4F0h+var_550]
0x18002ea60  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002ea65  lea     rdx, aToast; "</toast>"
0x18002ea6c  lea     rcx, [rbp+4F0h+var_550]
0x18002ea70  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002ea75  nop
0x18002ea76  lea     rcx, [rbp+4F0h+var_460]
0x18002ea7d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::allocator<ushort> const &)
0x18002ea82  or      edi, 10h
0x18002ea85  mov     [rsp+5F0h+var_5D0], edi
0x18002ea89  lea     rdx, [rsp+5F0h+var_5A8]
0x18002ea8e  lea     rcx, [rbp+4F0h+var_548]
0x18002ea92  call    ?_Get_buffer_view@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AU_Buffer_view@12@XZ; std::basic_stringbuf<ushort>::_Get_buffer_view(void)
0x18002ea97  mov     rdx, [rsp+5F0h+var_5A8]
0x18002ea9c  test    rdx, rdx
0x18002ea9f  jz      short loc_18002EAB2
0x18002eaa1  mov     r8, [rsp+5F0h+var_5A0]
0x18002eaa6  lea     rcx, [rbp+4F0h+var_460]
0x18002eaad  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x18002eab2  and     edi, 0FFFFFFEFh
0x18002eab5  or      edi, 8
0x18002eab8  mov     [rsp+5F0h+var_5D0], edi
0x18002eabc  lea     rcx, [rbp+4F0h+var_460]
0x18002eac3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002eac8  mov     rdx, rax; unsigned __int16 *
0x18002eacb  mov     r8, [rbp+4F0h+var_450]; unsigned __int64
0x18002ead2  lea     rcx, [rsp+5F0h+var_588]; this
0x18002ead7  call    ?create_string_reference@hstring@param@winrt@@AEAAXQEBG_K@Z; winrt::param::hstring::create_string_reference(ushort const * const,unsigned __int64)
0x18002eadc  lea     rdx, [rsp+5F0h+var_588]
0x18002eae1  lea     rcx, [rsp+5F0h+var_590]
0x18002eae6  call    ?LoadXml@?$consume_Windows_Data_Xml_Dom_IXmlDocumentIO@UXmlDocument@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(winrt::param::hstring const &)
0x18002eaeb  nop
0x18002eaec  lea     rcx, [rbp+4F0h+var_460]
0x18002eaf3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002eaf8  lea     rax, [rsp+5F0h+var_590]
0x18002eafd  mov     [rsp+5F0h+var_5B8], rax
0x18002eb02  lea     rax, qword_180052B18
0x18002eb09  mov     [rsp+5F0h+var_588], rax
0x18002eb0e  lock inc cs:qword_180052B18
0x18002eb16  cmp     cs:??$factory_cache_entry_v@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@12@A, r13; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>
0x18002eb1d  jz      short loc_18002EB40
0x18002eb1f  lea     r8, ??$factory_cache_entry_v@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@12@A; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>
0x18002eb26  lea     rdx, [rsp+5F0h+var_5C8]
0x18002eb2b  lea     rcx, [rsp+5F0h+var_5B8]
0x18002eb30  call    ??R_lambda_51cb1c784431ef1021794bfebdc3ae41_@@QEBA@AEBUIToastNotificationManagerStatics4@Notifications@UI@Windows@winrt@@@Z; _lambda_51cb1c784431ef1021794bfebdc3ae41_::operator()(winrt::Windows::UI::Notifications::IToastNotificationManagerStatics4 const &)
0x18002eb35  nop
0x18002eb36  lock dec cs:qword_180052B18
0x18002eb3e  jmp     short loc_18002EB57
0x18002eb40  lock dec cs:qword_180052B18
0x18002eb48  lea     r8, [rsp+5F0h+var_5B8]
0x18002eb4d  lea     rdx, [rsp+5F0h+var_5C8]
0x18002eb52  call    ??$call@AEAV_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@@?$factory_cache_entry@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@@Z
0x18002eb57  mov     rcx, [rsp+5F0h+var_5C8]
0x18002eb5c  mov     [rsi], rcx
0x18002eb5f  test    rcx, rcx
0x18002eb62  jz      short loc_18002EB70
0x18002eb64  mov     rax, [rcx]
0x18002eb67  mov     rax, [rax+8]
0x18002eb6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb70  mov     [rsi+8], r13
0x18002eb74  mov     [rsi+10h], r13
0x18002eb78  mov     [rsi+18h], r13
0x18002eb7c  mov     [rsi+20h], r13
0x18002eb80  mov     [rsi+28h], r13
0x18002eb84  mov     [rsi+30h], r13
0x18002eb88  mov     [rsi+38h], r13
0x18002eb8c  mov     [rsi+40h], r13
0x18002eb90  mov     [rsi+48h], r13
0x18002eb94  lea     rcx, [rsp+5F0h+var_5C8]
0x18002eb99  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18002eb9e  or      edi, 21h
0x18002eba1  mov     [rsp+5F0h+var_5D0], edi
0x18002eba5  mov     rcx, rsi
0x18002eba8  call    ?ExpiresOnReboot@?$consume_Windows_UI_Notifications_IToastNotification6@UToastNotification@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@_N@Z; winrt::impl::consume_Windows_UI_Notifications_IToastNotification6<winrt::Windows::UI::Notifications::ToastNotification>::ExpiresOnReboot(bool)
0x18002ebad  mov     rdx, r12
0x18002ebb0  lea     rcx, [rsp+5F0h+var_5B8]
0x18002ebb5  call    ??0?$weak_ptr@VToastHelper@@@std@@QEAA@AEBV01@@Z; std::weak_ptr<ToastHelper>::weak_ptr<ToastHelper>(std::weak_ptr<ToastHelper> const &)
0x18002ebba  nop
0x18002ebbb  lea     r8, [rsp+5F0h+var_5C0]
0x18002ebc0  lea     rdx, [rsp+5F0h+var_5B8]
0x18002ebc5  lea     rcx, [rbp+4F0h+var_460]
0x18002ebcc  call    _lambda_cbd528d856f4286070fe657a860472db____lambda_cbd528d856f4286070fe657a860472db_
0x18002ebd1  mov     rdx, rax
0x18002ebd4  lea     rcx, [rsp+5F0h+var_5C8]
0x18002ebd9  call    winrt__Windows__Foundation__TypedEventHandler_winrt__Windows__UI__Notifications__ToastNotification_winrt__Windows__Foundation__IInspectable___TypedEventHandler_winrt__Windows__UI__Notifications__ToastNotification_winrt__Windows__Foundation__IInspectable___lambda_6ab50ef37ae315c1111a87d1b311a614___
0x18002ebde  nop
0x18002ebdf  lea     r9, [rsp+5F0h+var_5C8]
0x18002ebe4  lea     rdx, [rsp+5F0h+var_588]
0x18002ebe9  mov     rcx, rsi
0x18002ebec  call    ?Activated@?$consume_Windows_UI_Notifications_IToastNotification@UIToastNotification@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@Uauto_revoke_t@3@AEBU?$TypedEventHandler@UToastNotification@Notifications@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_UI_Notifications_IToastNotification<winrt::Windows::UI::Notifications::IToastNotification>::Activated(winrt::auto_revoke_t,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::Foundation::IInspectable> const &)
0x18002ebf1  mov     r8, [rax+8]
0x18002ebf5  mov     rdx, [rax]
0x18002ebf8  mov     [rax], r13
0x18002ebfb  mov     [rsp+5F0h+var_5A8], rdx
0x18002ec00  lea     rax, ??_9type@?$abi@UIToastNotification@Notifications@UI@Windows@winrt@@X@impl@winrt@@$BGA@AA; [thunk]: winrt::impl::abi<winrt::Windows::UI::Notifications::IToastNotification,void>::type::`vcall'{96,{flat}}
0x18002ec07  mov     [rsp+5F0h+var_5A0], rax
0x18002ec0c  mov     [rsp+5F0h+var_598], r8
0x18002ec11  lea     rdx, [rsp+5F0h+var_5A8]
0x18002ec16  lea     rcx, [rsi+8]
0x18002ec1a  call    ??4?$event_revoker@UIToastNotification@Notifications@UI@Windows@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::event_revoker<winrt::Windows::UI::Notifications::IToastNotification>::operator=(winrt::event_revoker<winrt::Windows::UI::Notifications::IToastNotification> &&)
0x18002ec1f  lea     rcx, [rsp+5F0h+var_5A8]
0x18002ec24  call    ??1?$event_revoker@UIToastNotification@Notifications@UI@Windows@winrt@@@winrt@@QEAA@XZ; winrt::event_revoker<winrt::Windows::UI::Notifications::IToastNotification>::~event_revoker<winrt::Windows::UI::Notifications::IToastNotification>(void)
0x18002ec29  lea     rcx, [rsp+5F0h+var_588]
0x18002ec2e  call    ??1?$event_revoker@UIToastNotification@Notifications@UI@Windows@winrt@@$MP8type@?$abi@UIToastNotification@Notifications@UI@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BGA@AA@impl@winrt@@QEAA@XZ
0x18002ec33  nop
0x18002ec34  cmp     [rsp+5F0h+var_5C8], r13
0x18002ec39  jz      short loc_18002EC45
0x18002ec3b  lea     rcx, [rsp+5F0h+var_5C8]
0x18002ec40  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002ec45  lea     r8, [rsp+5F0h+var_5C0]
0x18002ec4a  lea     rdx, [rsp+5F0h+var_5B8]
0x18002ec4f  lea     rcx, [rbp+4F0h+var_460]
0x18002ec56  call    _lambda_cbd528d856f4286070fe657a860472db____lambda_cbd528d856f4286070fe657a860472db_
0x18002ec5b  mov     rdx, rax
0x18002ec5e  lea     rcx, [rsp+5F0h+var_5C8]
0x18002ec63  call    winrt__Windows__Foundation__TypedEventHandler_winrt__Windows__UI__Notifications__ToastNotification_winrt__Windows__UI__Notifications__ToastDismissedEventArgs___TypedEventHandler_winrt__Windows__UI__Notifications__ToastNotification_winrt__Windows__UI__Notifications__ToastDismissedEventArgs___lambda_3b6b1f727379048c7fa4c51e93a88699___
0x18002ec68  nop
0x18002ec69  lea     r9, [rsp+5F0h+var_5C8]
0x18002ec6e  lea     rdx, [rsp+5F0h+var_588]
0x18002ec73  mov     rcx, rsi
0x18002ec76  call    ?Dismissed@?$consume_Windows_UI_Notifications_IToastNotification@UIToastNotification@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@Uauto_revoke_t@3@AEBU?$TypedEventHandler@UToastNotification@Notifications@UI@Windows@winrt@@UToastDismissedEventArgs@2345@@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_UI_Notifications_IToastNotification<winrt::Windows::UI::Notifications::IToastNotification>::Dismissed(winrt::auto_revoke_t,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::ToastDismissedEventArgs> const &)
0x18002ec7b  mov     r8, [rax+8]
0x18002ec7f  mov     rdx, [rax]
0x18002ec82  mov     [rax], r13
0x18002ec85  mov     [rsp+5F0h+var_5A8], rdx
0x18002ec8a  lea     rax, ??_9type@?$abi@UIToastNotification@Notifications@UI@Windows@winrt@@X@impl@winrt@@$BFA@AA; [thunk]: winrt::impl::abi<winrt::Windows::UI::Notifications::IToastNotification,void>::type::`vcall'{80,{flat}}
0x18002ec91  mov     [rsp+5F0h+var_5A0], rax
0x18002ec96  mov     [rsp+5F0h+var_598], r8
0x18002ec9b  lea     rdx, [rsp+5F0h+var_5A8]
0x18002eca0  lea     rcx, [rsi+20h]
0x18002eca4  call    ??4?$event_revoker@UIToastNotification@Notifications@UI@Windows@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::event_revoker<winrt::Windows::UI::Notifications::IToastNotification>::operator=(winrt::event_revoker<winrt::Windows::UI::Notifications::IToastNotification> &&)
0x18002eca9  lea     rcx, [rsp+5F0h+var_5A8]
0x18002ecae  call    ??1?$event_revoker@UIToastNotification@Notifications@UI@Windows@winrt@@@winrt@@QEAA@XZ; winrt::event_revoker<winrt::Windows::UI::Notifications::IToastNotification>::~event_revoker<winrt::Windows::UI::Notifications::IToastNotification>(void)
0x18002ecb3  lea     rcx, [rsp+5F0h+var_588]
0x18002ecb8  call    ??1?$event_revoker@UIToastNotification@Notifications@UI@Windows@winrt@@$MP8type@?$abi@UIToastNotification@Notifications@UI@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BFA@AA@impl@winrt@@QEAA@XZ
0x18002ecbd  nop
0x18002ecbe  cmp     [rsp+5F0h+var_5C8], r13
0x18002ecc3  jz      short loc_18002ECCF
0x18002ecc5  lea     rcx, [rsp+5F0h+var_5C8]
0x18002ecca  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002eccf  lea     r8, [rsp+5F0h+var_5C0]
0x18002ecd4  lea     rdx, [rsp+5F0h+var_5B8]
0x18002ecd9  lea     rcx, [rbp+4F0h+var_460]
0x18002ece0  call    _lambda_cbd528d856f4286070fe657a860472db____lambda_cbd528d856f4286070fe657a860472db_
0x18002ece5  mov     rdx, rax
0x18002ece8  lea     rcx, [rsp+5F0h+var_5C0]
0x18002eced  call    winrt__Windows__Foundation__TypedEventHandler_winrt__Windows__UI__Notifications__ToastNotification_winrt__Windows__UI__Notifications__ToastFailedEventArgs___TypedEventHandler_winrt__Windows__UI__Notifications__ToastNotification_winrt__Windows__UI__Notifications__ToastFailedEventArgs___lambda_cbd528d856f4286070fe657a860472db___
0x18002ecf2  nop
0x18002ecf3  lea     r9, [rsp+5F0h+var_5C0]
0x18002ecf8  lea     rdx, [rsp+5F0h+var_588]
0x18002ecfd  mov     rcx, rsi
0x18002ed00  call    ?Failed@?$consume_Windows_UI_Notifications_IToastNotification@UIToastNotification@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@Uauto_revoke_t@3@AEBU?$TypedEventHandler@UToastNotification@Notifications@UI@Windows@winrt@@UToastFailedEventArgs@2345@@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_UI_Notifications_IToastNotification<winrt::Windows::UI::Notifications::IToastNotification>::Failed(winrt::auto_revoke_t,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::ToastFailedEventArgs> const &)
0x18002ed05  mov     r8, [rax+8]
0x18002ed09  mov     rdx, [rax]
0x18002ed0c  mov     [rax], r13
0x18002ed0f  mov     [rsp+5F0h+var_5A8], rdx
0x18002ed14  lea     rax, ??_9type@?$abi@UIToastNotification@Notifications@UI@Windows@winrt@@X@impl@winrt@@$BHA@AA; [thunk]: winrt::impl::abi<winrt::Windows::UI::Notifications::IToastNotification,void>::type::`vcall'{112,{flat}}
0x18002ed1b  mov     [rsp+5F0h+var_5A0], rax
  ... truncated ...
```
