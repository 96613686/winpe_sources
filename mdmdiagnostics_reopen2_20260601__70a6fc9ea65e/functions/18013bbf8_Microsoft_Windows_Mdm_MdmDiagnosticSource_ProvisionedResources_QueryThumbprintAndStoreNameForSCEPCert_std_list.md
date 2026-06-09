# Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::QueryThumbprintAndStoreNameForSCEPCert(std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,bool,std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,std::allocator<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo>> &)

- ea: `0x18013bbf8`
- end: `0x18013c356`
- name: `?QueryThumbprintAndStoreNameForSCEPCert@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@_NAEAV?$list@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@7@@Z`
- size: `1886`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18012cbf8`

## callees

- `0x180019080`
- `0x1800e4508`
- `0x1800e68b0`
- `0x1800e69f4`
- `0x1800e7d84`
- `0x1800e87ec`
- `0x1800e8a44`
- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f4b2c`
- `0x1800f9a08`
- `0x1800f9a94`
- `0x1800faa0c`
- `0x18011273c`
- `0x180128504`
- `0x180128538`
- `0x180129d4c`
- `0x180138604`
- `0x1801392e8`
- `0x180139314`
- `0x1801398f4`
- `0x18013a870`
- `0x18013bbf8`
- `0x18013c5c4`
- `0x180193010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18013bfcc`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18013bfcc`
- `msvcp_win!?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x18013bfe4`
- `msvcp_win!?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x18013bfe4`
- `msvcp_win!?fill@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x18013c00d`
- `msvcp_win!?fill@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x18013c00d`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x18013bf19`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x18013c020`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x18013bf19`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x18013c020`
- `OLEAUT32!__imp_VariantInit` at `0x18013bcd8`
- `OLEAUT32!__imp_VariantInit` at `0x18013bcd8`
- `OLEAUT32!__imp_VariantClear` at `0x18013c2fe`
- `OLEAUT32!__imp_VariantClear` at `0x18013c2fe`

## string_xrefs

- `0x18013bca2`: `Unexpected locuri for cert thumbprint and store name query. `
- `0x18013bdd9`: ` ResourceUri: `
- `0x18013c221`: `Getting node for cert installation for Thumbprint: `
- `0x18013bfb5`: ` completed with error 0x`
- `0x18013bf8c`: `PFX cert installation for `
- `0x18013bedc`: `SCEP cert installation for `
- `0x18013c135`: `Getting node for PFX cert installation for Thumbprint: `
- `0x18013c166`: `EncryptionStoreUri: `

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::QueryThumbprintAndStoreNameForSCEPCert(
        __int64 a1,
        _QWORD ***a2,
        char a3,
        __int64 a4)
{
  int ConfigManager2; // eax
  __int64 v7; // rcx
  unsigned int v8; // ebx
  _QWORD **v9; // rdi
  _QWORD *i; // rbx
  int TargetCertTypeFromLocURI; // r12d
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v12; // rsi
  __int64 v13; // rax
  const wchar_t *v14; // r8
  __int64 v15; // rax
  __int64 v16; // r14
  int (__fastcall *v17)(__int64, __int64, __int64 *); // rsi
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v22; // rsi
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 bstr; // rax
  __int64 v26; // r14
  int (__fastcall *v27)(__int64, __int64, __int64 *); // rsi
  __int64 v28; // r8
  __int64 v29; // rsi
  __int64 v30; // rax
  __int64 v31; // rax
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v32; // rsi
  __int64 v33; // rax
  __int64 v34; // rsi
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rsi
  __int64 v38; // rax
  __int64 v39; // rsi
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v40; // rsi
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // r14
  int (__fastcall *v45)(__int64, __int64, __int64 *); // rsi
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v51; // rsi
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v58; // rsi
  __int64 v59; // rax
  int v61; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v62; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v63; // [rsp+30h] [rbp-D0h] BYREF
  int v64[2]; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v66[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v67[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v68; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v69[16]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v70[240]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v71[16]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v72[16]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v73[240]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v74[32]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v75[32]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v76[32]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v77[32]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v78[32]; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v79[32]; // [rsp+320h] [rbp+220h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+288h]

  LOBYTE(v61) = a3;
  v62 = 0;
  *(_QWORD *)v64 = 0;
  ConfigManager2 = Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::CreateConfigManager2((LPVOID *)v64);
  v8 = ConfigManager2;
  if ( ConfigManager2 >= 0 )
  {
    v9 = *a2;
    for ( i = *v9; ; i = (_QWORD *)*i )
    {
      if ( i == v9 )
      {
        v8 = 0;
        goto LABEL_32;
      }
      TargetCertTypeFromLocURI = Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::GetTargetCertTypeFromLocURI(
                                   v7,
                                   i + 2);
      if ( !TargetCertTypeFromLocURI )
      {
        v12 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
        v13 = std::operator+<unsigned short>(
                v75,
                L"Unexpected locuri for cert thumbprint and store name query. ",
                i + 2);
        Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v12, v13);
        std::wstring::_Tidy_deallocate(v75);
        continue;
      }
      VariantInit(&pvarg);
      v14 = L"/CertThumbPrint";
      if ( TargetCertTypeFromLocURI != 1 )
        v14 = L"/Thumbprint";
      std::operator+<unsigned short>(v77, i + 2, v14);
      v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v77);
      wil::make_bstr(&v63, v15);
      v16 = *(_QWORD *)v64;
      v17 = *(int (__fastcall **)(__int64, __int64, __int64 *))(**(_QWORD **)v64 + 80LL);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v62);
      if ( v17(v16, v63, &v62) >= 0
        && (*(int (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v62 + 104LL))(v62, &pvarg) >= 0
        && pvarg.vt == 8 )
      {
        break;
      }
LABEL_29:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v63);
      std::wstring::_Tidy_deallocate(v77);
      VariantClear(&pvarg);
    }
    std::wstring::wstring(v74, pvarg.llVal);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v72);
    v18 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v73, L"Processing Thumbprint: ");
    v19 = std::operator<<<unsigned short>(v18, v74);
    v20 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v19, " ");
    v21 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v20, " ResourceUri: ");
    std::operator<<<unsigned short>(v21, i + 2);
    v22 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
    v23 = std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
            v72,
            v75);
    Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v22, v23);
    std::wstring::_Tidy_deallocate(v75);
    std::operator+<unsigned short>(v76, i + 2, L"/Status");
    v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v76);
    bstr = wil::make_bstr(v66, v24);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v63,
      bstr);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v66);
    v26 = *(_QWORD *)v64;
    v27 = *(int (__fastcall **)(__int64, __int64, __int64 *))(**(_QWORD **)v64 + 80LL);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v62);
    if ( v27(v26, v63, &v62) < 0
      || (*(int (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v62 + 104LL))(v62, &pvarg) < 0 )
    {
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v69);
      v53 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
              v70,
              L"Getting node for cert installation for Thumbprint: ");
      v54 = std::operator<<<unsigned short>(v53, v74);
      v55 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v54, " ");
      v56 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v55, "StatusString: ");
      v57 = std::operator<<<unsigned short>(v56, v76);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v57, " failed.");
      v58 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      v59 = std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
              v69,
              v78);
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v58, v59);
      std::wstring::_Tidy_deallocate(v78);
    }
    else if ( TargetCertTypeFromLocURI == 1 )
    {
      if ( pvarg.lVal == 1 )
      {
        ((void (__fastcall *)(__int64, _BYTE *, __int64, int *))std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo>::emplace_back<std::wstring &,unsigned short const (&)[3],bool &>)(
          a4,
          v74,
          v28,
          &v61);
LABEL_28:
        std::wstring::_Tidy_deallocate(v76);
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v72);
        std::wstring::_Tidy_deallocate(v74);
        goto LABEL_29;
      }
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v69);
      v29 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v70, L"SCEP cert installation for ");
      v30 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i + 2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v29, v30);
      v31 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
              v70,
              L" is not finished successfully. Status: ");
      std::basic_ostream<unsigned short>::operator<<(v31, pvarg.cyVal.Lo);
      v32 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      v33 = std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
              v69,
              v75);
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v32, v33);
      std::wstring::_Tidy_deallocate(v75);
    }
    else
    {
      if ( !pvarg.lVal )
      {
        std::wstring::wstring(v75, L"MY");
        std::operator+<unsigned short>(v79, i + 2, L"/PFXCertPasswordEncryptionStore");
        v42 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v79);
        v43 = wil::make_bstr(v67, v42);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          &v63,
          v43);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v67);
        v44 = *(_QWORD *)v64;
        v45 = *(int (__fastcall **)(__int64, __int64, __int64 *))(**(_QWORD **)v64 + 80LL);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v62);
        if ( v45(v44, v63, &v62) >= 0
          && (*(int (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v62 + 104LL))(v62, &pvarg) >= 0
          && pvarg.vt == 8 )
        {
          std::wstring::assign(v75, pvarg.llVal);
        }
        else
        {
          std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v69);
          v46 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                  v70,
                  L"Getting node for PFX cert installation for Thumbprint: ");
          v47 = std::operator<<<unsigned short>(v46, v74);
          v48 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v47, " ");
          v49 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v48, "EncryptionStoreUri: ");
          v50 = std::operator<<<unsigned short>(v49, v79);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v50, " failed.");
          v51 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
          v52 = std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
                  v69,
                  v78);
          Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v51, v52);
          std::wstring::_Tidy_deallocate(v78);
          std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v69);
        }
        v68 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v75);
        ((void (__fastcall *)(__int64, _BYTE *, __int64 *, int *))std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo>::emplace_back<std::wstring &,unsigned short const *,bool &>)(
          a4,
          v74,
          &v68,
          &v61);
        std::wstring::_Tidy_deallocate(v79);
        std::wstring::_Tidy_deallocate(v75);
        goto LABEL_28;
      }
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v69);
      v34 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v70, L"PFX cert installation for ");
      v35 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i + 2);
      v36 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v34, v35);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v36, L" completed with error 0x");
      v37 = std::basic_ostream<unsigned short>::operator<<(v70, std::hex);
      v38 = std::setw(v71, 8);
      v39 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v37, v38);
      std::basic_ios<unsigned short>::fill(v39 + *(int *)(*(_QWORD *)v39 + 4LL), 48);
      std::basic_ostream<unsigned short>::operator<<(v39, pvarg.cyVal.Lo);
      v40 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      v41 = std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
              v69,
              v78);
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v40, v41);
      std::wstring::_Tidy_deallocate(v78);
    }
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v69);
    goto LABEL_28;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC3,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
    (const char *)(unsigned int)ConfigManager2,
    v61);
LABEL_32:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(v64);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v62);
  return v8;
}

```

## disassembly

```asm
0x18013bbf8  mov     [rsp-8+arg_0], rbx
0x18013bbfd  push    rbp
0x18013bbfe  push    rsi
0x18013bbff  push    rdi
0x18013bc00  push    r12
0x18013bc02  push    r13
0x18013bc04  push    r14
0x18013bc06  push    r15
0x18013bc08  lea     rbp, [rsp-250h]
0x18013bc10  sub     rsp, 350h
0x18013bc17  mov     rax, cs:__security_cookie
0x18013bc1e  xor     rax, rsp
0x18013bc21  mov     [rbp+280h+var_40], rax
0x18013bc28  mov     r13, r9
0x18013bc2b  mov     rdi, rdx
0x18013bc2e  mov     byte ptr [rsp+380h+var_360], r8b; int
0x18013bc33  mov     [rsp+380h+var_358], 0
0x18013bc3c  mov     qword ptr [rsp+380h+var_348], 0
0x18013bc45  lea     rcx, [rsp+380h+var_348]; int
0x18013bc4a  call    ?CreateConfigManager2@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAJAEAV?$ComPtr@UIConfigManager2@@@WRL@5@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::CreateConfigManager2(Microsoft::WRL::ComPtr<IConfigManager2> &)
0x18013bc4f  mov     ebx, eax
0x18013bc51  test    eax, eax
0x18013bc53  jns     short loc_18013BC75
0x18013bc55  mov     rcx, [rbp+288h]; this
0x18013bc5c  mov     r9d, eax; char *
0x18013bc5f  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013bc66  mov     edx, 0C3h; void *
0x18013bc6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013bc70  jmp     loc_18013C314
0x18013bc75  mov     rdi, [rdi]
0x18013bc78  mov     rbx, [rdi]
0x18013bc7b  cmp     rbx, rdi
0x18013bc7e  jz      loc_18013C312
0x18013bc84  lea     r15, [rbx+10h]
0x18013bc88  mov     rdx, r15
0x18013bc8b  call    ?GetTargetCertTypeFromLocURI@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEBA?AW4CertType@12345@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::GetTargetCertTypeFromLocURI(std::wstring const &)
0x18013bc90  mov     r12d, eax
0x18013bc93  test    eax, eax
0x18013bc95  jnz     short loc_18013BCD3
0x18013bc97  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013bc9c  mov     rsi, rax
0x18013bc9f  mov     r8, r15
0x18013bca2  lea     rdx, aUnexpectedLocu; "Unexpected locuri for cert thumbprint a"...
0x18013bca9  lea     rcx, [rbp+280h+var_E0]
0x18013bcb0  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x18013bcb5  nop
0x18013bcb6  mov     rdx, rax
0x18013bcb9  mov     rcx, rsi
0x18013bcbc  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(std::wstring const &)
0x18013bcc1  nop
0x18013bcc2  lea     rcx, [rbp+280h+var_E0]
0x18013bcc9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013bcce  jmp     loc_18013C30A
0x18013bcd3  lea     rcx, [rsp+380h+pvarg]; pvarg
0x18013bcd8  call    cs:__imp_VariantInit
0x18013bcdf  nop     dword ptr [rax+rax+00h]
0x18013bce4  nop
0x18013bce5  lea     rax, aThumbprint; "/Thumbprint"
0x18013bcec  lea     r8, aCertthumbprint; "/CertThumbPrint"
0x18013bcf3  cmp     r12d, 1
0x18013bcf7  cmovnz  r8, rax
0x18013bcfb  mov     rdx, r15
0x18013bcfe  lea     rcx, [rbp+280h+var_A0]
0x18013bd05  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18013bd0a  nop
0x18013bd0b  lea     rcx, [rbp+280h+var_A0]
0x18013bd12  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013bd17  mov     rdx, rax
0x18013bd1a  lea     rcx, [rsp+380h+var_350]
0x18013bd1f  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18013bd24  nop
0x18013bd25  mov     r14, qword ptr [rsp+380h+var_348]
0x18013bd2a  mov     rax, [r14]
0x18013bd2d  mov     rsi, [rax+50h]
0x18013bd31  lea     rcx, [rsp+380h+var_358]
0x18013bd36  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18013bd3b  lea     r8, [rsp+380h+var_358]
0x18013bd40  mov     rdx, [rsp+380h+var_350]
0x18013bd45  mov     rcx, r14
0x18013bd48  mov     rax, rsi
0x18013bd4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013bd50  test    eax, eax
0x18013bd52  js      loc_18013C2E1
0x18013bd58  mov     rcx, [rsp+380h+var_358]
0x18013bd5d  mov     rax, [rcx]
0x18013bd60  lea     rdx, [rsp+380h+pvarg]
0x18013bd65  mov     rax, [rax+68h]
0x18013bd69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013bd6e  test    eax, eax
0x18013bd70  js      loc_18013C2E1
0x18013bd76  mov     eax, 8
0x18013bd7b  cmp     word ptr [rsp+380h+pvarg], ax
0x18013bd80  jnz     loc_18013C2E1
0x18013bd86  mov     rdx, qword ptr [rsp+380h+pvarg+8]
0x18013bd8b  lea     rcx, [rbp+280h+var_100]
0x18013bd92  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013bd97  nop
0x18013bd98  lea     rcx, [rbp+280h+var_200]
0x18013bd9f  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x18013bda4  nop
0x18013bda5  lea     rdx, aProcessingThum; "Processing Thumbprint: "
0x18013bdac  lea     rcx, [rbp+280h+var_1F0]
0x18013bdb3  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18013bdb8  mov     rcx, rax
0x18013bdbb  lea     rdx, [rbp+280h+var_100]
0x18013bdc2  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18013bdc7  mov     rcx, rax
0x18013bdca  lea     rdx, asc_1801F3460; " "
0x18013bdd1  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x18013bdd6  mov     rcx, rax
0x18013bdd9  lea     rdx, aResourceuri; " ResourceUri: "
0x18013bde0  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x18013bde5  mov     rcx, rax
0x18013bde8  mov     rdx, r15
0x18013bdeb  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18013bdf0  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013bdf5  mov     rsi, rax
0x18013bdf8  lea     rdx, [rbp+280h+var_E0]
0x18013bdff  lea     rcx, [rbp+280h+var_200]
0x18013be06  call    ?str@?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::str(void)
0x18013be0b  nop
0x18013be0c  mov     rdx, rax
0x18013be0f  mov     rcx, rsi
0x18013be12  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(std::wstring const &)
0x18013be17  nop
0x18013be18  lea     rcx, [rbp+280h+var_E0]
0x18013be1f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013be24  lea     r8, aStatus_1; "/Status"
0x18013be2b  mov     rdx, r15
0x18013be2e  lea     rcx, [rbp+280h+var_C0]
0x18013be35  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18013be3a  nop
0x18013be3b  lea     rcx, [rbp+280h+var_C0]
0x18013be42  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013be47  mov     rdx, rax
0x18013be4a  lea     rcx, [rsp+380h+var_328]
0x18013be4f  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18013be54  mov     rdx, rax
0x18013be57  lea     rcx, [rsp+380h+var_350]
0x18013be5c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18013be61  lea     rcx, [rsp+380h+var_328]
0x18013be66  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18013be6b  mov     r14, qword ptr [rsp+380h+var_348]
0x18013be70  mov     rax, [r14]
0x18013be73  mov     rsi, [rax+50h]
0x18013be77  lea     rcx, [rsp+380h+var_358]
0x18013be7c  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18013be81  lea     r8, [rsp+380h+var_358]
0x18013be86  mov     rdx, [rsp+380h+var_350]
0x18013be8b  mov     rcx, r14
0x18013be8e  mov     rax, rsi
0x18013be91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013be96  test    eax, eax
0x18013be98  js      loc_18013C216
0x18013be9e  mov     rcx, [rsp+380h+var_358]
0x18013bea3  mov     rax, [rcx]
0x18013bea6  lea     rdx, [rsp+380h+pvarg]
0x18013beab  mov     rax, [rax+68h]
0x18013beaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013beb4  test    eax, eax
0x18013beb6  js      loc_18013C216
0x18013bebc  cmp     r12d, 1
0x18013bec0  jnz     loc_18013BF76
0x18013bec6  cmp     dword ptr [rsp+380h+pvarg+8], r12d
0x18013becb  jz      loc_18013BF5D
0x18013bed1  lea     rcx, [rsp+380h+var_310]
0x18013bed6  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x18013bedb  nop
0x18013bedc  lea     rdx, aScepCertInstal; "SCEP cert installation for "
0x18013bee3  lea     rcx, [rbp+280h+var_300]
0x18013bee7  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18013beec  mov     rsi, rax
0x18013beef  mov     rcx, r15
0x18013bef2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013bef7  mov     rdx, rax
0x18013befa  mov     rcx, rsi
0x18013befd  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18013bf02  lea     rdx, aIsNotFinishedS; " is not finished successfully. Status: "
0x18013bf09  lea     rcx, [rbp+280h+var_300]
0x18013bf0d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18013bf12  mov     edx, dword ptr [rsp+380h+pvarg+8]
0x18013bf16  mov     rcx, rax
0x18013bf19  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z; std::basic_ostream<ushort>::operator<<(long)
0x18013bf20  nop     dword ptr [rax+rax+00h]
0x18013bf25  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013bf2a  mov     rsi, rax
0x18013bf2d  lea     rdx, [rbp+280h+var_E0]
0x18013bf34  lea     rcx, [rsp+380h+var_310]
0x18013bf39  call    ?str@?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::str(void)
0x18013bf3e  nop
0x18013bf3f  mov     rdx, rax
0x18013bf42  mov     rcx, rsi
0x18013bf45  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(std::wstring const &)
0x18013bf4a  nop
0x18013bf4b  lea     rcx, [rbp+280h+var_E0]
0x18013bf52  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013bf57  nop
0x18013bf58  jmp     loc_18013C2AF
0x18013bf5d  lea     r9, [rsp+380h+var_360]
0x18013bf62  lea     rdx, [rbp+280h+var_100]
0x18013bf69  mov     rcx, r13
0x18013bf6c  call    ??$emplace_back@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAY02$$CBGAEA_N@?$list@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@QEAAAEAVCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAY02$$CBGAEA_N@Z; std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo>::emplace_back<std::wstring &,ushort const (&)[3],bool &>(std::wstring &,ushort const (&)[3],bool &)
0x18013bf71  jmp     loc_18013C2BA
0x18013bf76  cmp     dword ptr [rsp+380h+pvarg+8], 0
0x18013bf7b  jz      loc_18013C064
0x18013bf81  lea     rcx, [rsp+380h+var_310]
0x18013bf86  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x18013bf8b  nop
0x18013bf8c  lea     rdx, aPfxCertInstall; "PFX cert installation for "
0x18013bf93  lea     rcx, [rbp+280h+var_300]
0x18013bf97  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18013bf9c  mov     rsi, rax
0x18013bf9f  mov     rcx, r15
0x18013bfa2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013bfa7  mov     rdx, rax
0x18013bfaa  mov     rcx, rsi
0x18013bfad  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18013bfb2  mov     rcx, rax
0x18013bfb5  lea     rdx, aCompletedWithE; " completed with error 0x"
0x18013bfbc  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18013bfc1  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18013bfc8  lea     rcx, [rbp+280h+var_300]
0x18013bfcc  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x18013bfd3  nop     dword ptr [rax+rax+00h]
0x18013bfd8  mov     rsi, rax
0x18013bfdb  mov     edx, 8
0x18013bfe0  lea     rcx, [rbp+280h+var_210]
0x18013bfe4  call    cs:__imp_?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z; std::setw(__int64)
0x18013bfeb  nop     dword ptr [rax+rax+00h]
0x18013bff0  mov     rdx, rax
0x18013bff3  mov     rcx, rsi
0x18013bff6  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBU?$_Smanip@_J@0@@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,std::_Smanip<__int64> const &)
0x18013bffb  mov     rsi, rax
0x18013bffe  mov     edx, 30h ; '0'
0x18013c003  mov     rcx, [rax]
0x18013c006  movsxd  rcx, dword ptr [rcx+4]
0x18013c00a  add     rcx, rax
0x18013c00d  call    cs:__imp_?fill@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAGG@Z; std::basic_ios<ushort>::fill(ushort)
0x18013c014  nop     dword ptr [rax+rax+00h]
0x18013c019  mov     edx, dword ptr [rsp+380h+pvarg+8]
0x18013c01d  mov     rcx, rsi
0x18013c020  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z; std::basic_ostream<ushort>::operator<<(long)
0x18013c027  nop     dword ptr [rax+rax+00h]
0x18013c02c  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013c031  mov     rsi, rax
0x18013c034  lea     rdx, [rbp+280h+var_80]
0x18013c03b  lea     rcx, [rsp+380h+var_310]
0x18013c040  call    ?str@?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::str(void)
0x18013c045  nop
0x18013c046  mov     rdx, rax
0x18013c049  mov     rcx, rsi
0x18013c04c  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(std::wstring const &)
0x18013c051  nop
0x18013c052  lea     rcx, [rbp+280h+var_80]
0x18013c059  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013c05e  nop
0x18013c05f  jmp     loc_18013C2AF
0x18013c064  lea     rdx, aMy_0; "MY"
0x18013c06b  lea     rcx, [rbp+280h+var_E0]
0x18013c072  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013c077  nop
0x18013c078  lea     r8, aPfxcertpasswor; "/PFXCertPasswordEncryptionStore"
0x18013c07f  mov     rdx, r15
0x18013c082  lea     rcx, [rbp+280h+var_60]
0x18013c089  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18013c08e  nop
0x18013c08f  lea     rcx, [rbp+280h+var_60]
0x18013c096  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013c09b  mov     rdx, rax
0x18013c09e  lea     rcx, [rsp+380h+var_320]
0x18013c0a3  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18013c0a8  mov     rdx, rax
0x18013c0ab  lea     rcx, [rsp+380h+var_350]
0x18013c0b0  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18013c0b5  lea     rcx, [rsp+380h+var_320]
0x18013c0ba  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18013c0bf  mov     r14, qword ptr [rsp+380h+var_348]
0x18013c0c4  mov     rax, [r14]
0x18013c0c7  mov     rsi, [rax+50h]
0x18013c0cb  lea     rcx, [rsp+380h+var_358]
0x18013c0d0  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18013c0d5  lea     r8, [rsp+380h+var_358]
0x18013c0da  mov     rdx, [rsp+380h+var_350]
0x18013c0df  mov     rcx, r14
0x18013c0e2  mov     rax, rsi
0x18013c0e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c0ea  test    eax, eax
0x18013c0ec  js      short loc_18013C12A
0x18013c0ee  mov     rcx, [rsp+380h+var_358]
0x18013c0f3  mov     rax, [rcx]
0x18013c0f6  lea     rdx, [rsp+380h+pvarg]
0x18013c0fb  mov     rax, [rax+68h]
0x18013c0ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c104  test    eax, eax
0x18013c106  js      short loc_18013C12A
0x18013c108  mov     eax, 8
0x18013c10d  cmp     word ptr [rsp+380h+pvarg], ax
0x18013c112  jnz     short loc_18013C12A
0x18013c114  mov     rdx, qword ptr [rsp+380h+pvarg+8]
0x18013c119  lea     rcx, [rbp+280h+var_E0]
  ... truncated ...
```
