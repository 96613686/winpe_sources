# cdp::CloudDataEncryptionKeyFactory::PopulatePropertyBag(CDPAccountType,IPropertyBag *)

- ea: `0x1800ae034`
- end: `0x1800ae89c`
- name: `?PopulatePropertyBag@CloudDataEncryptionKeyFactory@cdp@@AEAAXW4CDPAccountType@@PEAUIPropertyBag@@@Z`
- size: `2152`
- prototype: `void __high(enum CDPAccountType, struct IPropertyBag *)`
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ad100`

## callees

- `0x180009770`
- `0x180009b94`
- `0x18000acdc`
- `0x18000b724`
- `0x18000d02c`
- `0x18000f430`
- `0x180010ee0`
- `0x1800117f8`
- `0x180013da0`
- `0x18001ce80`
- `0x180030190`
- `0x180057654`
- `0x1800624cc`
- `0x1800677f0`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800a11bc`
- `0x1800ad5c0`
- `0x1800ad770`
- `0x1800ae034`
- `0x18011d8c4`
- `0x180143248`
- `0x1801f6fb0`
- `0x1801f7468`
- `0x1801fc74c`
- `0x1801fc7b4`
- `0x1801fcb36`
- `0x1801fcb4e`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ae82f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ae82f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800ae616`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800ae616`
- `PROPSYS!PSPropertyBag_WriteUnknown` at `0x1800ae2d6`
- `PROPSYS!PSPropertyBag_WriteUnknown` at `0x1800ae575`
- `PROPSYS!PSPropertyBag_WriteUnknown` at `0x1800ae2d6`
- `PROPSYS!PSPropertyBag_WriteUnknown` at `0x1800ae575`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1800ae37f`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1800ae440`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1800ae70c`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1800ae37f`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1800ae440`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1800ae70c`

## string_xrefs

- `0x1800ae858`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu","text":"Unsupported account type provided"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
void __fastcall cdp::CloudDataEncryptionKeyFactory::PopulatePropertyBag(__int64 a1, __int16 a2, IPropertyBag *a3)
{
  _QWORD *v6; // rsi
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 v8; // rax
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, _QWORD *, _QWORD); // rdi
  _QWORD *v14; // rdx
  int v15; // eax
  __int64 v16; // rax
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v18)(_QWORD, GUID *, IUnknown **); // rdi
  unsigned int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rax
  IUnknown *v23; // rbx
  __int64 v24; // rax
  HRESULT v25; // ebx
  __int64 v26; // rax
  __int64 v27; // rax
  const WCHAR *v28; // rbx
  __int64 v29; // rax
  HRESULT v30; // ebx
  __int64 v31; // rax
  __int64 v32; // rax
  const WCHAR *v33; // rbx
  __int64 v34; // rax
  HRESULT v35; // ebx
  __int64 v36; // rax
  __int64 v37; // rbx
  HRESULT v38; // eax
  __int64 v39; // rax
  void *v40; // rax
  __int64 v41; // rdi
  void **v42; // rsi
  __int64 v43; // rbx
  __int64 v44; // rax
  __m128i *v45; // r8
  const WCHAR *v46; // r8
  HRESULT v47; // ebx
  __int64 v48; // rax
  IUnknown *v49; // rcx
  __int64 (__fastcall ***v50)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v51; // rcx
  int v52; // ecx
  __int64 v53; // rax
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // rax
  _QWORD v57[2]; // [rsp+30h] [rbp-D0h] BYREF
  IUnknown *punk; // [rsp+40h] [rbp-C0h] BYREF
  int v59; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v60)(_QWORD, GUID *, IUnknown **); // [rsp+50h] [rbp-B0h] BYREF
  __int64 v61; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD pExceptionObject[3]; // [rsp+60h] [rbp-A0h] BYREF
  char v63[8]; // [rsp+90h] [rbp-70h] BYREF
  __int64 (__fastcall ***v64)(_QWORD, GUID *, __int64 *); // [rsp+98h] [rbp-68h] BYREF
  std::_Ref_count_base *v65; // [rsp+A0h] [rbp-60h]
  _BYTE v66[8]; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v67; // [rsp+B0h] [rbp-50h]
  LPCWSTR value[2]; // [rsp+B8h] [rbp-48h] BYREF
  char v69; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v70; // [rsp+D0h] [rbp-30h]
  __m128i v71; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v72; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v73; // [rsp+F0h] [rbp-10h]
  void *Src[2]; // [rsp+F8h] [rbp-8h] BYREF
  __m128i si128; // [rsp+108h] [rbp+8h]
  char v76[8]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v77[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v78[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v79[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v80[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v81[128]; // [rsp+1A0h] [rbp+A0h] BYREF

  shared::SharedInstanceManager::GetInstanceThrowIfNull<shared::IUserIdentityManager>(v66);
  v6 = (_QWORD *)(a1 + 48);
  shared::GetAccountProvider(&v64, v66, v6);
  v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v64;
  if ( !v64 )
  {
    value[0] = (LPCWSTR)".\\clouddataencryptionkeyfactory.cpp";
    LODWORD(value[1]) = 292;
    v8 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, value, 2147549183LL);
    cdp::CdpThrow<cdp::hresult_exception>(value, v8);
  }
  v61 = 0;
  v9 = **v64;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
  v10 = v9(v7, &GUID_661654e2_f44d_4f20_8c2d_4c3a04aa1570, &v61);
  if ( v10 < 0 )
  {
    value[0] = (LPCWSTR)".\\clouddataencryptionkeyfactory.cpp";
    LODWORD(value[1]) = 295;
    v11 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, value, (unsigned int)v10);
    cdp::CdpThrow<cdp::hresult_exception>(value, v11);
  }
  v60 = 0;
  v12 = v61;
  v13 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD))(*(_QWORD *)v61 + 24LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
  if ( v6[3] <= 0xFu )
    v14 = v6;
  else
    v14 = (_QWORD *)*v6;
  v15 = v13(v12, v14, &v60);
  if ( v15 < 0 )
  {
    value[0] = (LPCWSTR)".\\clouddataencryptionkeyfactory.cpp";
    LODWORD(value[1]) = 298;
    v16 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, value, (unsigned int)v15);
    cdp::CdpThrow<cdp::hresult_exception>(value, v16);
  }
  punk = 0;
  v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v60;
  v18 = **v60;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&punk);
  v19 = v18(v17, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, &punk);
  v21 = v19;
  if ( (v19 & 0x80000000) != 0 )
  {
    value[0] = (LPCWSTR)".\\clouddataencryptionkeyfactory.cpp";
    LODWORD(value[1]) = 301;
    v22 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, value, v19);
    cdp::CdpThrow<cdp::hresult_exception>(value, v22);
  }
  if ( a2 == 2 )
  {
    strcpy((char *)v57, "RMS_USER");
    *(__m128i *)value = _mm_load_si128((const __m128i *)&_xmm);
    v69 = 0;
    *(__m128i *)Src = _mm_load_si128((const __m128i *)&_xmm);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    strcpy(v76, "dc0f");
    v71 = _mm_load_si128((const __m128i *)&_xmm);
    LODWORD(v72) = 4805205;
    pExceptionObject[0] = _mm_load_si128((const __m128i *)&_xmm);
    pExceptionObject[1] = _mm_load_si128((const __m128i *)&_xmm);
    pExceptionObject[2] = _mm_load_si128((const __m128i *)&_xmm);
    strcpy(v63, "ir");
    v23 = punk;
    std::string::string(v77, v57);
    v24 = cdp::ToWstring(v78, v77);
    if ( *(_QWORD *)(v24 + 24) > 7u )
      v24 = *(_QWORD *)v24;
    v25 = PSPropertyBag_WriteUnknown(a3, (LPCWSTR)v24, v23);
    std::wstring::_Tidy_deallocate(v78);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v77);
    if ( v25 < 0 )
    {
      value[0] = (LPCWSTR)".\\clouddataencryptionkeyfactory.cpp";
      LODWORD(value[1]) = 313;
      v26 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, value, (unsigned int)v25);
      cdp::CdpThrow<cdp::hresult_exception>(value, v26);
    }
    std::string::string(v78, Src);
    v27 = cdp::ToWstring(v79, v78);
    v28 = (const WCHAR *)v27;
    if ( *(_QWORD *)(v27 + 24) > 7u )
      v28 = *(const WCHAR **)v27;
    std::string::string(v77, value);
    v29 = cdp::ToWstring(v80, v77);
    if ( *(_QWORD *)(v29 + 24) > 7u )
      v29 = *(_QWORD *)v29;
    v30 = PSPropertyBag_WriteStr(a3, (LPCWSTR)v29, v28);
    std::wstring::_Tidy_deallocate(v80);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v77);
    std::wstring::_Tidy_deallocate(v79);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v78);
    if ( v30 < 0 )
    {
      value[0] = (LPCWSTR)".\\clouddataencryptionkeyfactory.cpp";
      LODWORD(value[1]) = 315;
      v31 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, value, (unsigned int)v30);
      cdp::CdpThrow<cdp::hresult_exception>(value, v31);
    }
    std::string::string(v77, pExceptionObject);
    v32 = cdp::ToWstring(v80, v77);
    v33 = (const WCHAR *)v32;
    if ( *(_QWORD *)(v32 + 24) > 7u )
      v33 = *(const WCHAR **)v32;
    std::string::string(v78, &v71);
    v34 = cdp::ToWstring(v79, v78);
    if ( *(_QWORD *)(v34 + 24) > 7u )
      v34 = *(_QWORD *)v34;
    v35 = PSPropertyBag_WriteStr(a3, (LPCWSTR)v34, v33);
    std::wstring::_Tidy_deallocate(v79);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v78);
    std::wstring::_Tidy_deallocate(v80);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v77);
    if ( v35 < 0 )
    {
      value[0] = (LPCWSTR)".\\clouddataencryptionkeyfactory.cpp";
      LODWORD(value[1]) = 317;
      v36 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, value, (unsigned int)v35);
      cdp::CdpThrow<cdp::hresult_exception>(value, v36);
    }
  }
  else
  {
    if ( a2 != 1 )
    {
      value[0] = (LPCWSTR)".\\clouddataencryptionkeyfactory.cpp";
      LODWORD(value[1]) = 337;
      v59 = -2147024846;
      v57[0] = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v52,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Unsupported account type provided\"}",
        (unsigned int)&v59,
        (unsigned int)value,
        (__int64)&value[1],
        (__int64)v57);
      v53 = cdp::ExceptionStackFromSourceLocationInfo(&v71, value);
      v56 = cdp::ErrorCodeToString(2147942450LL, v54, v55, v53);
      ConnectedDevices::Exception::Exception(pExceptionObject, 2147942450LL, v56);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    v37 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    if ( __TSS0__DK___PopulatePropertyBag_CloudDataEncryptionKeyFactory_cdp__AEAAXW4CDPAccountType__PEAUIPropertyBag___Z_4HA > *(_DWORD *)(v37 + 16) )
    {
      Init_thread_header(
        &__TSS0__DK___PopulatePropertyBag_CloudDataEncryptionKeyFactory_cdp__AEAAXW4CDPAccountType__PEAUIPropertyBag___Z_4HA,
        v20,
        v19);
      if ( __TSS0__DK___PopulatePropertyBag_CloudDataEncryptionKeyFactory_cdp__AEAAXW4CDPAccountType__PEAUIPropertyBag___Z_4HA == -1 )
      {
        std::string::string(
          &`cdp::CloudDataEncryptionKeyFactory::PopulatePropertyBag'::`58'::MSARoamingSecurityTicketTarget,
          "http://Passport.NET/purpose");
        atexit(`cdp::CloudDataEncryptionKeyFactory::PopulatePropertyBag'::`58'::`dynamic atexit destructor for 'MSARoamingSecurityTicketTarget'');
        Init_thread_footer(&__TSS0__DK___PopulatePropertyBag_CloudDataEncryptionKeyFactory_cdp__AEAAXW4CDPAccountType__PEAUIPropertyBag___Z_4HA);
      }
    }
    if ( __TSS1__DK___PopulatePropertyBag_CloudDataEncryptionKeyFactory_cdp__AEAAXW4CDPAccountType__PEAUIPropertyBag___Z_4HA > *(_DWORD *)(v37 + 16) )
    {
      Init_thread_header(
        &__TSS1__DK___PopulatePropertyBag_CloudDataEncryptionKeyFactory_cdp__AEAAXW4CDPAccountType__PEAUIPropertyBag___Z_4HA,
        v20,
        v21);
      if ( __TSS1__DK___PopulatePropertyBag_CloudDataEncryptionKeyFactory_cdp__AEAAXW4CDPAccountType__PEAUIPropertyBag___Z_4HA == -1 )
      {
        std::string::string(
          `cdp::CloudDataEncryptionKeyFactory::PopulatePropertyBag'::`58'::MSARoamingSecurityTicketPolicy,
          "PURPOSE_GETKEYDATA_ROAMING");
        atexit(`cdp::CloudDataEncryptionKeyFactory::PopulatePropertyBag'::`58'::`dynamic atexit destructor for 'MSARoamingSecurityTicketPolicy'');
        Init_thread_footer(&__TSS1__DK___PopulatePropertyBag_CloudDataEncryptionKeyFactory_cdp__AEAAXW4CDPAccountType__PEAUIPropertyBag___Z_4HA);
      }
    }
    v38 = PSPropertyBag_WriteUnknown(a3, L"WebAccount", punk);
    if ( v38 < 0 )
    {
      value[0] = (LPCWSTR)".\\clouddataencryptionkeyfactory.cpp";
      LODWORD(value[1]) = 325;
      v39 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, value, (unsigned int)v38);
      cdp::CdpThrow<cdp::hresult_exception>(value, v39);
    }
    v40 = (void *)std::string::string(
                    v79,
                    `cdp::CloudDataEncryptionKeyFactory::PopulatePropertyBag'::`58'::MSARoamingSecurityTicketPolicy);
    shared::GetUserTicket(
      (int)Src,
      (int)v6,
      (int)&`cdp::CloudDataEncryptionKeyFactory::PopulatePropertyBag'::`58'::MSARoamingSecurityTicketTarget,
      v40,
      3);
    v71 = 0;
    v72 = 0;
    v73 = 0;
    v41 = si128.m128i_i64[0];
    v42 = Src;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v42 = (void **)Src[0];
    if ( si128.m128i_i64[0] > 0x7FFFFFFFFFFFFFFFuLL )
      std::_Xlength_error("string too long");
    if ( si128.m128i_i64[0] > 0xFuLL )
    {
      v43 = std::string::_Calculate_growth(si128.m128i_i64[0], 15);
      v71.m128i_i64[0] = std::allocator<char>::allocate(&v71, v43 + 1);
      v72 = v41;
      v73 = v43;
      memcpy_0((void *)v71.m128i_i64[0], v42, v41 + 1);
      v41 = v72;
    }
    else
    {
      v72 = si128.m128i_i64[0];
      v73 = 15;
      v71 = *(__m128i *)v42;
    }
    if ( !v41 )
    {
      value[0] = (LPCWSTR)".\\clouddataencryptionkeyfactory.cpp";
      LODWORD(value[1]) = 331;
      v44 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, value, 2147549183LL);
      cdp::CdpThrow<cdp::hresult_exception>(value, v44);
    }
    std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v81);
    v45 = &v71;
    if ( v73 > 0xF )
      v45 = (__m128i *)v71.m128i_i64[0];
    std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
      v81,
      value,
      v45,
      &v45->m128i_i8[v72]);
    std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v81);
    v46 = (const WCHAR *)value;
    if ( v70 > 7 )
      v46 = value[0];
    v47 = PSPropertyBag_WriteStr(a3, L"Ticket", v46);
    if ( v70 > 7 )
      std::_Deallocate<16>(value[0], 2 * v70 + 2);
    if ( v47 < 0 )
    {
      value[0] = (LPCWSTR)".\\clouddataencryptionkeyfactory.cpp";
      LODWORD(value[1]) = 332;
      v48 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, value, (unsigned int)v47);
      cdp::CdpThrow<cdp::hresult_exception>(value, v48);
    }
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v71);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(Src);
  }
  v49 = punk;
  if ( punk )
  {
    punk = 0;
    ((void (__fastcall *)(IUnknown *))v49->lpVtbl->Release)(v49);
  }
  v50 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v60;
  if ( v60 )
  {
    v60 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v50)[2])(v50);
  }
  v51 = v61;
  if ( v61 )
  {
    v61 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  }
  if ( v65 )
    std::_Ref_count_base::_Decref(v65);
  if ( v67 )
    std::_Ref_count_base::_Decref(v67);
}

```

## disassembly

```asm
0x1800ae034  mov     [rsp-8+arg_8], rbx
0x1800ae039  mov     [rsp-8+arg_18], rsi
0x1800ae03e  push    rbp
0x1800ae03f  push    rdi
0x1800ae040  push    r12
0x1800ae042  push    r14
0x1800ae044  push    r15
0x1800ae046  lea     rbp, [rsp-130h]
0x1800ae04e  sub     rsp, 230h
0x1800ae055  mov     rax, cs:__security_cookie
0x1800ae05c  xor     rax, rsp
0x1800ae05f  mov     [rbp+150h+var_30], rax
0x1800ae066  mov     r14, r8
0x1800ae069  movzx   r15d, dx
0x1800ae06d  mov     rsi, rcx
0x1800ae070  xor     r12d, r12d
0x1800ae073  lea     rcx, [rbp+150h+var_1A8]
0x1800ae077  call    ??$GetInstanceThrowIfNull@VIUserIdentityManager@shared@@@SharedInstanceManager@shared@@SA?AV?$shared_ptr@VIUserIdentityManager@shared@@@std@@H@Z; shared::SharedInstanceManager::GetInstanceThrowIfNull<shared::IUserIdentityManager>(int)
0x1800ae07c  nop
0x1800ae07d  add     rsi, 30h ; '0'
0x1800ae081  mov     r8, rsi
0x1800ae084  lea     rdx, [rbp+150h+var_1A8]
0x1800ae088  lea     rcx, [rbp+150h+var_1B8]
0x1800ae08c  call    ?GetAccountProvider@shared@@YA?AV?$shared_ptr@VICDPAccountProvider@@@std@@AEBV?$shared_ptr@VIUserIdentityManager@shared@@@3@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; shared::GetAccountProvider(std::shared_ptr<shared::IUserIdentityManager> const &,std::string const &)
0x1800ae091  nop
0x1800ae092  mov     rdi, [rbp+150h+var_1B8]
0x1800ae096  test    rdi, rdi
0x1800ae099  jnz     short loc_1800AE0CF
0x1800ae09b  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1800ae0a2  mov     [rbp+150h+value], rax
0x1800ae0a6  mov     dword ptr [rbp+150h+value+8], 124h
0x1800ae0ad  mov     r8d, 8000FFFFh
0x1800ae0b3  lea     rdx, [rbp+150h+value]
0x1800ae0b7  lea     rcx, [rsp+250h+pExceptionObject]
0x1800ae0bc  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800ae0c1  nop
0x1800ae0c2  mov     rdx, rax
0x1800ae0c5  lea     rcx, [rbp+150h+value]
0x1800ae0c9  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800ae0cf  mov     [rsp+250h+var_1F8], r12
0x1800ae0d4  mov     rax, [rdi]
0x1800ae0d7  mov     rbx, [rax]
0x1800ae0da  lea     rcx, [rsp+250h+var_1F8]
0x1800ae0df  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800ae0e4  lea     r8, [rsp+250h+var_1F8]
0x1800ae0e9  lea     rdx, _GUID_661654e2_f44d_4f20_8c2d_4c3a04aa1570
0x1800ae0f0  mov     rcx, rdi
0x1800ae0f3  mov     rax, rbx
0x1800ae0f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae0fb  mov     r8d, eax
0x1800ae0fe  test    eax, eax
0x1800ae100  jns     short loc_1800AE130
0x1800ae102  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1800ae109  mov     [rbp+150h+value], rax
0x1800ae10d  mov     dword ptr [rbp+150h+value+8], 127h
0x1800ae114  lea     rdx, [rbp+150h+value]
0x1800ae118  lea     rcx, [rsp+250h+pExceptionObject]
0x1800ae11d  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800ae122  nop
0x1800ae123  mov     rdx, rax
0x1800ae126  lea     rcx, [rbp+150h+value]
0x1800ae12a  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800ae130  mov     [rsp+250h+var_200], r12
0x1800ae135  mov     rbx, [rsp+250h+var_1F8]
0x1800ae13a  mov     rax, [rbx]
0x1800ae13d  mov     rdi, [rax+18h]
0x1800ae141  lea     rcx, [rsp+250h+var_200]
0x1800ae146  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800ae14b  cmp     qword ptr [rsi+18h], 0Fh
0x1800ae150  jbe     short loc_1800AE157
0x1800ae152  mov     rdx, [rsi]
0x1800ae155  jmp     short loc_1800AE15A
0x1800ae157  mov     rdx, rsi
0x1800ae15a  lea     r8, [rsp+250h+var_200]
0x1800ae15f  mov     rcx, rbx
0x1800ae162  mov     rax, rdi
0x1800ae165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae16a  mov     r8d, eax
0x1800ae16d  test    eax, eax
0x1800ae16f  jns     short loc_1800AE19F
0x1800ae171  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1800ae178  mov     [rbp+150h+value], rax
0x1800ae17c  mov     dword ptr [rbp+150h+value+8], 12Ah
0x1800ae183  lea     rdx, [rbp+150h+value]
0x1800ae187  lea     rcx, [rsp+250h+pExceptionObject]
0x1800ae18c  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800ae191  nop
0x1800ae192  mov     rdx, rax
0x1800ae195  lea     rcx, [rbp+150h+value]
0x1800ae199  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800ae19f  mov     [rsp+250h+punk], r12
0x1800ae1a4  mov     rbx, [rsp+250h+var_200]
0x1800ae1a9  mov     rax, [rbx]
0x1800ae1ac  mov     rdi, [rax]
0x1800ae1af  lea     rcx, [rsp+250h+punk]
0x1800ae1b4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800ae1b9  lea     r8, [rsp+250h+punk]
0x1800ae1be  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x1800ae1c5  mov     rcx, rbx
0x1800ae1c8  mov     rax, rdi
0x1800ae1cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae1d0  mov     r8d, eax
0x1800ae1d3  test    eax, eax
0x1800ae1d5  jns     short loc_1800AE205
0x1800ae1d7  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1800ae1de  mov     [rbp+150h+value], rax
0x1800ae1e2  mov     dword ptr [rbp+150h+value+8], 12Dh
0x1800ae1e9  lea     rdx, [rbp+150h+value]
0x1800ae1ed  lea     rcx, [rsp+250h+pExceptionObject]
0x1800ae1f2  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800ae1f7  nop
0x1800ae1f8  mov     rdx, rax
0x1800ae1fb  lea     rcx, [rbp+150h+value]
0x1800ae1ff  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800ae205  cmp     r15w, 2
0x1800ae20a  jnz     loc_1800AE4AB
0x1800ae210  mov     dword ptr [rsp+250h+var_220], 5F534D52h
0x1800ae218  mov     dword ptr [rsp+250h+var_220+4], 52455355h
0x1800ae220  mov     [rsp+250h+var_220+8], r12b
0x1800ae225  movdqa  xmm0, cs:__xmm@44495f544e45494c435f42545f534d52
0x1800ae22d  movdqu  xmmword ptr [rbp+150h+value], xmm0
0x1800ae232  mov     [rbp+150h+var_188], r12b
0x1800ae236  movdqa  xmm1, cs:__xmm@66342d373631332d3565646238633036
0x1800ae23e  movdqu  xmmword ptr [rbp+150h+Src], xmm1
0x1800ae243  movdqa  xmm0, cs:__xmm@36373136663935302d626466382d3239
0x1800ae24b  movdqu  [rbp+150h+var_148], xmm0
0x1800ae250  mov     dword ptr [rbp+150h+var_138], 66306364h
0x1800ae257  mov     [rbp+150h+var_138+4], r12b
0x1800ae25b  movdqa  xmm0, cs:__xmm@5f54434552494445525f42545f534d52
0x1800ae263  movdqu  [rbp+150h+var_178], xmm0
0x1800ae268  mov     dword ptr [rbp+150h+var_168], 495255h
0x1800ae26f  movdqa  xmm0, cs:__xmm@63346534663561662f2f3a7370747468
0x1800ae277  movdqu  [rsp+250h+pExceptionObject], xmm0
0x1800ae27d  movdqa  xmm1, cs:__xmm@2d366639392d343733342d373765352d
0x1800ae285  movdqu  [rsp+250h+var_1E0], xmm1
0x1800ae28b  movdqa  xmm0, cs:__xmm@6465722f613736313864613533613165
0x1800ae293  movdqu  [rbp+150h+var_1D0], xmm0
0x1800ae298  mov     word ptr [rbp+150h+var_1C0], 7269h
0x1800ae29e  mov     [rbp+150h+var_1C0+2], r12b
0x1800ae2a2  mov     rbx, [rsp+250h+punk]
0x1800ae2a7  lea     rdx, [rsp+250h+var_220]
0x1800ae2ac  lea     rcx, [rbp+150h+var_130]
0x1800ae2b0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800ae2b5  nop
0x1800ae2b6  lea     rdx, [rbp+150h+var_130]
0x1800ae2ba  lea     rcx, [rbp+150h+var_110]
0x1800ae2be  call    ?ToWstring@cdp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; cdp::ToWstring(std::string const &)
0x1800ae2c3  cmp     qword ptr [rax+18h], 7
0x1800ae2c8  jbe     short loc_1800AE2CD
0x1800ae2ca  mov     rax, [rax]
0x1800ae2cd  mov     r8, rbx; punk
0x1800ae2d0  mov     rdx, rax; propName
0x1800ae2d3  mov     rcx, r14; propBag
0x1800ae2d6  call    cs:__imp_PSPropertyBag_WriteUnknown
0x1800ae2dc  mov     ebx, eax
0x1800ae2de  lea     rcx, [rbp+150h+var_110]
0x1800ae2e2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ae2e7  nop
0x1800ae2e8  lea     rcx, [rbp+150h+var_130]; void *
0x1800ae2ec  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800ae2f1  test    ebx, ebx
0x1800ae2f3  jns     short loc_1800AE326
0x1800ae2f5  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1800ae2fc  mov     [rbp+150h+value], rax
0x1800ae300  mov     dword ptr [rbp+150h+value+8], 139h
0x1800ae307  mov     r8d, ebx
0x1800ae30a  lea     rdx, [rbp+150h+value]
0x1800ae30e  lea     rcx, [rsp+250h+pExceptionObject]
0x1800ae313  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800ae318  nop
0x1800ae319  mov     rdx, rax
0x1800ae31c  lea     rcx, [rbp+150h+value]
0x1800ae320  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800ae326  lea     rdx, [rbp+150h+Src]
0x1800ae32a  lea     rcx, [rbp+150h+var_110]
0x1800ae32e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800ae333  nop
0x1800ae334  lea     rdx, [rbp+150h+var_110]
0x1800ae338  lea     rcx, [rbp+150h+var_F0]
0x1800ae33c  call    ?ToWstring@cdp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; cdp::ToWstring(std::string const &)
0x1800ae341  mov     rbx, rax
0x1800ae344  cmp     qword ptr [rax+18h], 7
0x1800ae349  jbe     short loc_1800AE34E
0x1800ae34b  mov     rbx, [rax]
0x1800ae34e  lea     rdx, [rbp+150h+value]
0x1800ae352  lea     rcx, [rbp+150h+var_130]
0x1800ae356  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800ae35b  nop
0x1800ae35c  lea     rdx, [rbp+150h+var_130]
0x1800ae360  lea     rcx, [rbp+150h+var_D0]
0x1800ae367  call    ?ToWstring@cdp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; cdp::ToWstring(std::string const &)
0x1800ae36c  cmp     qword ptr [rax+18h], 7
0x1800ae371  jbe     short loc_1800AE376
0x1800ae373  mov     rax, [rax]
0x1800ae376  mov     r8, rbx; value
0x1800ae379  mov     rdx, rax; propName
0x1800ae37c  mov     rcx, r14; propBag
0x1800ae37f  call    cs:__imp_PSPropertyBag_WriteStr
0x1800ae385  mov     ebx, eax
0x1800ae387  lea     rcx, [rbp+150h+var_D0]
0x1800ae38e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ae393  nop
0x1800ae394  lea     rcx, [rbp+150h+var_130]; void *
0x1800ae398  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800ae39d  nop
0x1800ae39e  lea     rcx, [rbp+150h+var_F0]
0x1800ae3a2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ae3a7  nop
0x1800ae3a8  lea     rcx, [rbp+150h+var_110]; void *
0x1800ae3ac  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800ae3b1  test    ebx, ebx
0x1800ae3b3  jns     short loc_1800AE3E6
0x1800ae3b5  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1800ae3bc  mov     [rbp+150h+value], rax
0x1800ae3c0  mov     dword ptr [rbp+150h+value+8], 13Bh
0x1800ae3c7  mov     r8d, ebx
0x1800ae3ca  lea     rdx, [rbp+150h+value]
0x1800ae3ce  lea     rcx, [rsp+250h+pExceptionObject]
0x1800ae3d3  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800ae3d8  nop
0x1800ae3d9  mov     rdx, rax
0x1800ae3dc  lea     rcx, [rbp+150h+value]
0x1800ae3e0  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800ae3e6  lea     rdx, [rsp+250h+pExceptionObject]
0x1800ae3eb  lea     rcx, [rbp+150h+var_130]
0x1800ae3ef  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800ae3f4  nop
0x1800ae3f5  lea     rdx, [rbp+150h+var_130]
0x1800ae3f9  lea     rcx, [rbp+150h+var_D0]
0x1800ae400  call    ?ToWstring@cdp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; cdp::ToWstring(std::string const &)
0x1800ae405  mov     rbx, rax
0x1800ae408  cmp     qword ptr [rax+18h], 7
0x1800ae40d  jbe     short loc_1800AE412
0x1800ae40f  mov     rbx, [rax]
0x1800ae412  lea     rdx, [rbp+150h+var_178]
0x1800ae416  lea     rcx, [rbp+150h+var_110]
0x1800ae41a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800ae41f  nop
0x1800ae420  lea     rdx, [rbp+150h+var_110]
0x1800ae424  lea     rcx, [rbp+150h+var_F0]
0x1800ae428  call    ?ToWstring@cdp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; cdp::ToWstring(std::string const &)
0x1800ae42d  cmp     qword ptr [rax+18h], 7
0x1800ae432  jbe     short loc_1800AE437
0x1800ae434  mov     rax, [rax]
0x1800ae437  mov     r8, rbx; value
0x1800ae43a  mov     rdx, rax; propName
0x1800ae43d  mov     rcx, r14; propBag
0x1800ae440  call    cs:__imp_PSPropertyBag_WriteStr
0x1800ae446  mov     ebx, eax
0x1800ae448  lea     rcx, [rbp+150h+var_F0]
0x1800ae44c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ae451  nop
0x1800ae452  lea     rcx, [rbp+150h+var_110]; void *
0x1800ae456  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800ae45b  nop
0x1800ae45c  lea     rcx, [rbp+150h+var_D0]
0x1800ae463  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ae468  nop
0x1800ae469  lea     rcx, [rbp+150h+var_130]; void *
0x1800ae46d  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800ae472  test    ebx, ebx
0x1800ae474  jns     loc_1800AE778
0x1800ae47a  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1800ae481  mov     [rbp+150h+value], rax
0x1800ae485  mov     dword ptr [rbp+150h+value+8], 13Dh
0x1800ae48c  mov     r8d, ebx
0x1800ae48f  lea     rdx, [rbp+150h+value]
0x1800ae493  lea     rcx, [rsp+250h+pExceptionObject]
0x1800ae498  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800ae49d  nop
0x1800ae49e  mov     rdx, rax
0x1800ae4a1  lea     rcx, [rbp+150h+value]
0x1800ae4a5  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800ae4ab  cmp     r15w, 1
0x1800ae4b0  jnz     loc_1800AE814
0x1800ae4b6  mov     ecx, cs:_tls_index
0x1800ae4bc  mov     rax, gs:58h
0x1800ae4c5  mov     edi, 10h
0x1800ae4ca  mov     rbx, [rax+rcx*8]
0x1800ae4ce  mov     eax, [rbx+rdi]
0x1800ae4d1  cmp     cs:?$TSS0@?DK@??PopulatePropertyBag@CloudDataEncryptionKeyFactory@cdp@@AEAAXW4CDPAccountType@@PEAUIPropertyBag@@@Z@4HA, eax
0x1800ae4d7  jle     short loc_1800AE51A
0x1800ae4d9  lea     rcx, ?$TSS0@?DK@??PopulatePropertyBag@CloudDataEncryptionKeyFactory@cdp@@AEAAXW4CDPAccountType@@PEAUIPropertyBag@@@Z@4HA
0x1800ae4e0  call    _Init_thread_header
0x1800ae4e5  cmp     cs:?$TSS0@?DK@??PopulatePropertyBag@CloudDataEncryptionKeyFactory@cdp@@AEAAXW4CDPAccountType@@PEAUIPropertyBag@@@Z@4HA, 0FFFFFFFFh
0x1800ae4ec  jnz     short loc_1800AE51A
0x1800ae4ee  lea     rdx, aHttpPassportNe; "http://Passport.NET/purpose"
0x1800ae4f5  lea     rcx, ?MSARoamingSecurityTicketTarget@?DK@??PopulatePropertyBag@CloudDataEncryptionKeyFactory@cdp@@AEAAXW4CDPAccountType@@PEAUIPropertyBag@@@Z@4V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@B; std::string const `cdp::CloudDataEncryptionKeyFactory::PopulatePropertyBag(CDPAccountType,IPropertyBag *)'::`58'::MSARoamingSecurityTicketTarget
0x1800ae4fc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800ae501  lea     rcx, ??__FMSARoamingSecurityTicketTarget@?DK@??PopulatePropertyBag@CloudDataEncryptionKeyFactory@cdp@@AEAAXW4CDPAccountType@@PEAUIPropertyBag@@@Z@YAXXZ; void (__cdecl *)()
0x1800ae508  call    atexit
0x1800ae50d  nop
0x1800ae50e  lea     rcx, ?$TSS0@?DK@??PopulatePropertyBag@CloudDataEncryptionKeyFactory@cdp@@AEAAXW4CDPAccountType@@PEAUIPropertyBag@@@Z@4HA
0x1800ae515  call    _Init_thread_footer
0x1800ae51a  mov     eax, [rbx+rdi]
0x1800ae51d  cmp     cs:?$TSS1@?DK@??PopulatePropertyBag@CloudDataEncryptionKeyFactory@cdp@@AEAAXW4CDPAccountType@@PEAUIPropertyBag@@@Z@4HA, eax
0x1800ae523  jle     short loc_1800AE566
0x1800ae525  lea     rcx, ?$TSS1@?DK@??PopulatePropertyBag@CloudDataEncryptionKeyFactory@cdp@@AEAAXW4CDPAccountType@@PEAUIPropertyBag@@@Z@4HA
0x1800ae52c  call    _Init_thread_header
0x1800ae531  cmp     cs:?$TSS1@?DK@??PopulatePropertyBag@CloudDataEncryptionKeyFactory@cdp@@AEAAXW4CDPAccountType@@PEAUIPropertyBag@@@Z@4HA, 0FFFFFFFFh
  ... truncated ...
```
