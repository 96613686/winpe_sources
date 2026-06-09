# ReadEnrollmentCertThumbprintAndStoreName

- ea: `0x180129dc8`
- end: `0x18012a227`
- name: `ReadEnrollmentCertThumbprintAndStoreName`
- size: `1119`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18012afd8`

## callees

- `0x180019000`
- `0x1800e66dc`
- `0x1800e7124`
- `0x1800e7c08`
- `0x1800e82e4`
- `0x1800ece5c`
- `0x1800ee878`
- `0x1800ef5d8`
- `0x1800f9a0c`
- `0x180108060`
- `0x180127250`
- `0x18012778c`
- `0x1801277b4`
- `0x180127dbc`
- `0x180127ddc`
- `0x180128e28`
- `0x180129dc8`
- `0x18013304c`
- `0x1801330a4`
- `0x18013a5ec`
- `0x18013aadc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180129e38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180129e38`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180129ed3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180129fb2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012a098`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180129ed3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180129fb2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012a098`
- `RPCRT4!UuidFromStringW` at `0x18012a0c5`
- `RPCRT4!UuidFromStringW` at `0x18012a0c5`
- `dmEnrollEngine!__imp_?GetEnrollmentClientContext@@YAJU_GUID@@PEAKPEAPEAXPEAPEBU_CERT_CONTEXT@@@Z` at `0x18012a129`
- `dmEnrollEngine!__imp_?GetEnrollmentClientContext@@YAJU_GUID@@PEAKPEAPEAXPEAPEBU_CERT_CONTEXT@@@Z` at `0x18012a129`
- `dmEnrollEngine!__imp_OpenEnrollmentsHKEY` at `0x180129e5b`
- `dmEnrollEngine!__imp_OpenEnrollmentsHKEY` at `0x180129e5b`

## string_xrefs

- `0x180129e6c`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ReadEnrollmentCertThumbprintAndStoreName(_QWORD *a1)
{
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v2; // rax
  int EnrollmentId; // eax
  unsigned int v4; // esi
  __int64 v5; // rdx
  const WCHAR **v6; // rsi
  const WCHAR *v7; // rdx
  __int64 v8; // r8
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo *v9; // rdx
  int CertInfoWithThumbPrint; // eax
  __int64 *v11; // r14
  __int64 v12; // rcx
  const WCHAR *v13; // rdx
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo *v14; // rdx
  int v15; // eax
  __int64 *v16; // r14
  __int64 v17; // rcx
  const WCHAR *v18; // rdx
  unsigned __int16 *v19; // rcx
  const struct _CERT_CONTEXT *v20; // r8
  int v21; // eax
  __int64 *v22; // rsi
  __int64 v23; // rcx
  int pdwType; // [rsp+20h] [rbp-2B8h]
  _BYTE v26[4]; // [rsp+40h] [rbp-298h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-294h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-290h] BYREF
  void *v29; // [rsp+50h] [rbp-288h] BYREF
  struct _CERT_CONTEXT *v30; // [rsp+58h] [rbp-280h] BYREF
  unsigned int v31; // [rsp+60h] [rbp-278h] BYREF
  __int128 v32; // [rsp+68h] [rbp-270h] BYREF
  struct _GUID v33[2]; // [rsp+80h] [rbp-258h] BYREF
  UUID Uuid; // [rsp+A0h] [rbp-238h] BYREF
  _BYTE pvData[528]; // [rsp+B0h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  v32 = 0;
  hKey = 0;
  v2 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
  EnrollmentId = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(v2, &v32);
  v4 = EnrollmentId;
  if ( EnrollmentId < 0 )
  {
    v5 = 1595;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)EnrollmentId,
      pdwType);
    goto LABEL_36;
  }
  hKey = 0;
  EnrollmentId = OpenEnrollmentsHKEY(131097, &hKey);
  v4 = EnrollmentId;
  if ( EnrollmentId < 0 )
  {
    v5 = 1596;
    goto LABEL_5;
  }
  pcbData = 520;
  try
  {
    v6 = (const WCHAR **)v32;
    if ( (_QWORD)v32 )
      v7 = *(const WCHAR **)v32;
    else
      v7 = 0;
    if ( !RegGetValueW(hKey, v7, L"RootCertThumbPrint", 2u, 0, pvData, &pcbData) )
    {
      v26[0] = 0;
      std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo>::emplace_back<unsigned short (&)[260],unsigned short const (&)[5],bool>(
        a1,
        pvData,
        v8,
        v26);
      CertInfoWithThumbPrint = Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveCertInfoWithThumbPrint(
                                 (Microsoft::Windows::Mdm::MdmDiagnosticSource *)(*(_QWORD *)(*a1 + 8LL) + 16LL),
                                 v9);
      v11 = *(__int64 **)(*a1 + 8LL);
      if ( CertInfoWithThumbPrint < 0 )
      {
        v12 = *v11;
        --a1[1];
        *(_QWORD *)v11[1] = v12;
        *(_QWORD *)(v12 + 8) = v11[1];
        std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>::_Freenode<std::allocator<std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>>>(
          v12,
          v11);
      }
      else
      {
        std::wstring::wstring(v33, L"Device Management Root");
        std::wstring::operator=(v11 + 18, v33);
        std::wstring::_Tidy_deallocate(v33);
      }
    }
    pcbData = 520;
    if ( v6 )
      v13 = *v6;
    else
      v13 = 0;
    if ( !RegGetValueW(hKey, v13, L"IntermediateCertThumbPrint", 2u, 0, pvData, &pcbData) )
    {
      v26[0] = 0;
      std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo>::emplace_back<unsigned short (&)[260],unsigned short const (&)[3],bool>(
        a1,
        pvData,
        L"CA",
        v26);
      v15 = Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveCertInfoWithThumbPrint(
              (Microsoft::Windows::Mdm::MdmDiagnosticSource *)(*(_QWORD *)(*a1 + 8LL) + 16LL),
              v14);
      v16 = *(__int64 **)(*a1 + 8LL);
      if ( v15 < 0 )
      {
        v17 = *v16;
        --a1[1];
        *(_QWORD *)v16[1] = v17;
        *(_QWORD *)(v17 + 8) = v16[1];
        std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>::_Freenode<std::allocator<std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>>>(
          v17,
          v16);
      }
      else
      {
        std::wstring::wstring(v33, L"Device Management Intermediate");
        std::wstring::operator=(v16 + 18, v33);
        std::wstring::_Tidy_deallocate(v33);
      }
    }
    pcbData = 520;
    if ( v6 )
      v18 = *v6;
    else
      v18 = 0;
    if ( !RegGetValueW(hKey, v18, L"DMPCertThumbPrint", 2u, 0, pvData, &pcbData) )
    {
      Uuid = 0;
      v19 = v6 ? (unsigned __int16 *)*v6 : 0LL;
      if ( !UuidFromStringW(v19, &Uuid) )
      {
        v29 = 0;
        v31 = 0;
        v30 = 0;
        wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(
          &v30,
          0);
        _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
          &v29,
          0);
        v33[0] = Uuid;
        if ( (int)GetEnrollmentClientContext(v33, &v31, &v29, (const struct _CERT_CONTEXT **)&v30) >= 0 )
        {
          v26[0] = 1;
          std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo>::emplace_back<unsigned short (&)[260],unsigned short const (&)[3],bool>(
            a1,
            pvData,
            L"MY",
            v26);
          v21 = Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveCertInfoWithThumbPrint(
                  (Microsoft::Windows::Mdm::MdmDiagnosticSource *)(*(_QWORD *)(*a1 + 8LL) + 16LL),
                  v30,
                  v20);
          v22 = *(__int64 **)(*a1 + 8LL);
          if ( v21 < 0 )
          {
            v23 = *v22;
            --a1[1];
            *(_QWORD *)v22[1] = v23;
            *(_QWORD *)(v23 + 8) = v22[1];
            std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>::_Freenode<std::allocator<std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>>>(
              v23,
              v22);
          }
          else
          {
            std::wstring::wstring(v33, L"Device Management Client");
            std::wstring::operator=(v22 + 18, v33);
            std::wstring::_Tidy_deallocate(v33);
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v30);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v29);
      }
    }
  }
  catch ( ... )
  {
  }
  v4 = 0;
LABEL_36:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v32);
  return v4;
}

```

## disassembly

```asm
0x180129dc8  mov     [rsp+arg_8], rsi
0x180129dcd  mov     [rsp+arg_10], rdi
0x180129dd2  push    r14
0x180129dd4  sub     rsp, 2D0h
0x180129ddb  mov     rax, cs:__security_cookie
0x180129de2  xor     rax, rsp
0x180129de5  mov     [rsp+2D8h+var_18], rax
0x180129ded  mov     rdi, rcx
0x180129df0  xorps   xmm1, xmm1
0x180129df3  movdqu  [rsp+2D8h+var_270], xmm1
0x180129df9  mov     [rsp+2D8h+hKey], 0
0x180129e02  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180129e07  lea     rdx, [rsp+2D8h+var_270]
0x180129e0c  mov     rcx, rax
0x180129e0f  call    ?GetEnrollmentId@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> &)
0x180129e14  mov     esi, eax
0x180129e16  test    eax, eax
0x180129e18  jns     short loc_180129E21
0x180129e1a  mov     edx, 63Bh
0x180129e1f  jmp     short loc_180129E6C
0x180129e21  mov     rsi, [rsp+2D8h+hKey]
0x180129e26  test    rsi, rsi
0x180129e29  jz      short loc_180129E48
0x180129e2b  lea     rcx, [rsp+2D8h+var_288]; this
0x180129e30  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180129e35  mov     rcx, rsi; hKey
0x180129e38  call    cs:__imp_RegCloseKey
0x180129e3e  lea     rcx, [rsp+2D8h+var_288]; this
0x180129e43  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180129e48  mov     [rsp+2D8h+hKey], 0
0x180129e51  lea     rdx, [rsp+2D8h+hKey]
0x180129e56  mov     ecx, 20019h
0x180129e5b  call    cs:__imp_OpenEnrollmentsHKEY
0x180129e61  mov     esi, eax
0x180129e63  test    eax, eax
0x180129e65  jns     short loc_180129E88
0x180129e67  mov     edx, 63Ch; void *
0x180129e6c  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180129e73  mov     r9d, eax; char *
0x180129e76  mov     rcx, [rsp+2D8h]; this
0x180129e7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180129e83  jmp     loc_18012A1EA
0x180129e88  mov     [rsp+2D8h+var_294], 208h
0x180129e90  mov     rsi, qword ptr [rsp+2D8h+var_270]
0x180129e95  test    rsi, rsi
0x180129e98  jz      short loc_180129E9F
0x180129e9a  mov     rdx, [rsi]
0x180129e9d  jmp     short loc_180129EA1
0x180129e9f  xor     edx, edx; lpSubKey
0x180129ea1  lea     rax, [rsp+2D8h+var_294]
0x180129ea6  mov     [rsp+2D8h+pcbData], rax; pcbData
0x180129eab  lea     rax, [rsp+2D8h+var_228]
0x180129eb3  mov     [rsp+2D8h+pvData], rax; pvData
0x180129eb8  mov     [rsp+2D8h+pdwType], 0; pdwType
0x180129ec1  mov     r9d, 2; dwFlags
0x180129ec7  lea     r8, aRootcertthumbp; "RootCertThumbPrint"
0x180129ece  mov     rcx, [rsp+2D8h+hKey]; hkey
0x180129ed3  call    cs:__imp_RegGetValueW
0x180129ed9  test    eax, eax
0x180129edb  jnz     loc_180129F6C
0x180129ee1  mov     [rsp+2D8h+var_298], al
0x180129ee5  lea     r9, [rsp+2D8h+var_298]
0x180129eea  lea     rdx, [rsp+2D8h+var_228]
0x180129ef2  mov     rcx, rdi
0x180129ef5  call    ??$emplace_back@AEAY0BAE@GAEAY04$$CBG_N@?$list@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@QEAAAEAVCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAY0BAE@GAEAY04$$CBG$$QEA_N@Z; std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo>::emplace_back<ushort (&)[260],ushort const (&)[5],bool>(ushort (&)[260],ushort const (&)[5],bool &&)
0x180129efa  mov     rax, [rdi]
0x180129efd  mov     rcx, [rax+8]
0x180129f01  add     rcx, 10h; this
0x180129f05  call    ?RetrieveCertInfoWithThumbPrint@MdmDiagnosticSource@Mdm@Windows@Microsoft@@YAJAEAVCertInfo@1234@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveCertInfoWithThumbPrint(Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo &)
0x180129f0a  mov     rcx, [rdi]
0x180129f0d  mov     r14, [rcx+8]
0x180129f11  test    eax, eax
0x180129f13  js      short loc_180129F4E
0x180129f15  lea     rdx, aDeviceManageme; "Device Management Root"
0x180129f1c  lea     rcx, [rsp+2D8h+var_258]
0x180129f24  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180129f29  nop
0x180129f2a  lea     rcx, [r14+90h]
0x180129f31  lea     rdx, [rsp+2D8h+var_258]
0x180129f39  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180129f3e  nop
0x180129f3f  lea     rcx, [rsp+2D8h+var_258]
0x180129f47  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180129f4c  jmp     short loc_180129F6C
0x180129f4e  mov     rcx, [r14]
0x180129f51  dec     qword ptr [rdi+8]
0x180129f55  mov     rax, [r14+8]
0x180129f59  mov     [rax], rcx
0x180129f5c  mov     rax, [r14+8]
0x180129f60  mov     [rcx+8], rax
0x180129f64  mov     rdx, r14
0x180129f67  call    ??$_Freenode@V?$allocator@U?$_List_node@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@PEAX@std@@@std@@@?$_List_node@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>::_Freenode<std::allocator<std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>>>(std::allocator<std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>> &,std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *> *)
0x180129f6c  mov     [rsp+2D8h+var_294], 208h
0x180129f74  test    rsi, rsi
0x180129f77  jz      short loc_180129F7E
0x180129f79  mov     rdx, [rsi]
0x180129f7c  jmp     short loc_180129F80
0x180129f7e  xor     edx, edx; lpSubKey
0x180129f80  lea     rax, [rsp+2D8h+var_294]
0x180129f85  mov     [rsp+2D8h+pcbData], rax; pcbData
0x180129f8a  lea     rax, [rsp+2D8h+var_228]
0x180129f92  mov     [rsp+2D8h+pvData], rax; pvData
0x180129f97  mov     [rsp+2D8h+pdwType], 0; pdwType
0x180129fa0  mov     r9d, 2; dwFlags
0x180129fa6  lea     r8, aIntermediatece; "IntermediateCertThumbPrint"
0x180129fad  mov     rcx, [rsp+2D8h+hKey]; hkey
0x180129fb2  call    cs:__imp_RegGetValueW
0x180129fb8  test    eax, eax
0x180129fba  jnz     loc_18012A052
0x180129fc0  mov     [rsp+2D8h+var_298], al
0x180129fc4  lea     r9, [rsp+2D8h+var_298]
0x180129fc9  lea     r8, aCa; "CA"
0x180129fd0  lea     rdx, [rsp+2D8h+var_228]
0x180129fd8  mov     rcx, rdi
0x180129fdb  call    ??$emplace_back@AEAY0BAE@GAEAY02$$CBG_N@?$list@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@QEAAAEAVCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAY0BAE@GAEAY02$$CBG$$QEA_N@Z; std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo>::emplace_back<ushort (&)[260],ushort const (&)[3],bool>(ushort (&)[260],ushort const (&)[3],bool &&)
0x180129fe0  mov     rax, [rdi]
0x180129fe3  mov     rcx, [rax+8]
0x180129fe7  add     rcx, 10h; this
0x180129feb  call    ?RetrieveCertInfoWithThumbPrint@MdmDiagnosticSource@Mdm@Windows@Microsoft@@YAJAEAVCertInfo@1234@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveCertInfoWithThumbPrint(Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo &)
0x180129ff0  mov     rcx, [rdi]
0x180129ff3  mov     r14, [rcx+8]
0x180129ff7  test    eax, eax
0x180129ff9  js      short loc_18012A034
0x180129ffb  lea     rdx, aDeviceManageme_0; "Device Management Intermediate"
0x18012a002  lea     rcx, [rsp+2D8h+var_258]
0x18012a00a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012a00f  nop
0x18012a010  lea     rcx, [r14+90h]
0x18012a017  lea     rdx, [rsp+2D8h+var_258]
0x18012a01f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18012a024  nop
0x18012a025  lea     rcx, [rsp+2D8h+var_258]
0x18012a02d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a032  jmp     short loc_18012A052
0x18012a034  mov     rcx, [r14]
0x18012a037  dec     qword ptr [rdi+8]
0x18012a03b  mov     rax, [r14+8]
0x18012a03f  mov     [rax], rcx
0x18012a042  mov     rax, [r14+8]
0x18012a046  mov     [rcx+8], rax
0x18012a04a  mov     rdx, r14
0x18012a04d  call    ??$_Freenode@V?$allocator@U?$_List_node@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@PEAX@std@@@std@@@?$_List_node@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>::_Freenode<std::allocator<std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>>>(std::allocator<std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>> &,std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *> *)
0x18012a052  mov     [rsp+2D8h+var_294], 208h
0x18012a05a  test    rsi, rsi
0x18012a05d  jz      short loc_18012A064
0x18012a05f  mov     rdx, [rsi]
0x18012a062  jmp     short loc_18012A066
0x18012a064  xor     edx, edx; lpSubKey
0x18012a066  lea     rax, [rsp+2D8h+var_294]
0x18012a06b  mov     [rsp+2D8h+pcbData], rax; pcbData
0x18012a070  lea     rax, [rsp+2D8h+var_228]
0x18012a078  mov     [rsp+2D8h+pvData], rax; pvData
0x18012a07d  mov     [rsp+2D8h+pdwType], 0; pdwType
0x18012a086  mov     r9d, 2; dwFlags
0x18012a08c  lea     r8, aDmpcertthumbpr; "DMPCertThumbPrint"
0x18012a093  mov     rcx, [rsp+2D8h+hKey]; hkey
0x18012a098  call    cs:__imp_RegGetValueW
0x18012a09e  test    eax, eax
0x18012a0a0  jnz     loc_18012A1E6
0x18012a0a6  xorps   xmm0, xmm0
0x18012a0a9  movups  xmmword ptr [rsp+2D8h+Uuid.Data1], xmm0
0x18012a0b1  test    rsi, rsi
0x18012a0b4  jz      short loc_18012A0BB
0x18012a0b6  mov     rcx, [rsi]
0x18012a0b9  jmp     short loc_18012A0BD
0x18012a0bb  xor     ecx, ecx; StringUuid
0x18012a0bd  lea     rdx, [rsp+2D8h+Uuid]; Uuid
0x18012a0c5  call    cs:__imp_UuidFromStringW
0x18012a0cb  test    eax, eax
0x18012a0cd  jnz     loc_18012A1E6
0x18012a0d3  mov     [rsp+2D8h+var_288], 0
0x18012a0dc  mov     [rsp+2D8h+var_278], eax
0x18012a0e0  mov     [rsp+2D8h+var_280], 0
0x18012a0e9  xor     edx, edx
0x18012a0eb  lea     rcx, [rsp+2D8h+var_280]
0x18012a0f0  call    ?reset@?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEBU_CERT_CONTEXT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(_CERT_CONTEXT const *)
0x18012a0f5  xor     edx, edx
0x18012a0f7  lea     rcx, [rsp+2D8h+var_288]
0x18012a0fc  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18012a101  movaps  xmm0, xmmword ptr [rsp+2D8h+Uuid.Data1]
0x18012a109  movdqa  [rsp+2D8h+var_258], xmm0
0x18012a112  lea     r9, [rsp+2D8h+var_280]
0x18012a117  lea     r8, [rsp+2D8h+var_288]
0x18012a11c  lea     rdx, [rsp+2D8h+var_278]
0x18012a121  lea     rcx, [rsp+2D8h+var_258]
0x18012a129  call    cs:__imp_?GetEnrollmentClientContext@@YAJU_GUID@@PEAKPEAPEAXPEAPEBU_CERT_CONTEXT@@@Z; GetEnrollmentClientContext(_GUID,ulong *,void * *,_CERT_CONTEXT const * *)
0x18012a12f  test    eax, eax
0x18012a131  js      loc_18012A1D0
0x18012a137  mov     [rsp+2D8h+var_298], 1
0x18012a13c  lea     r9, [rsp+2D8h+var_298]
0x18012a141  lea     r8, aMy_0; "MY"
0x18012a148  lea     rdx, [rsp+2D8h+var_228]
0x18012a150  mov     rcx, rdi
0x18012a153  call    ??$emplace_back@AEAY0BAE@GAEAY02$$CBG_N@?$list@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@QEAAAEAVCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAY0BAE@GAEAY02$$CBG$$QEA_N@Z; std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo>::emplace_back<ushort (&)[260],ushort const (&)[3],bool>(ushort (&)[260],ushort const (&)[3],bool &&)
0x18012a158  mov     rax, [rdi]
0x18012a15b  mov     rcx, [rax+8]
0x18012a15f  add     rcx, 10h; this
0x18012a163  mov     rdx, [rsp+2D8h+var_280]; struct _CERT_CONTEXT *
0x18012a168  call    ?RetrieveCertInfoWithThumbPrint@MdmDiagnosticSource@Mdm@Windows@Microsoft@@YAJAEAVCertInfo@1234@PEBU_CERT_CONTEXT@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveCertInfoWithThumbPrint(Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo &,_CERT_CONTEXT const *)
0x18012a16d  mov     rcx, [rdi]
0x18012a170  mov     rsi, [rcx+8]
0x18012a174  test    eax, eax
0x18012a176  js      short loc_18012A1B1
0x18012a178  lea     rdx, aDeviceManageme_1; "Device Management Client"
0x18012a17f  lea     rcx, [rsp+2D8h+var_258]
0x18012a187  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012a18c  nop
0x18012a18d  lea     rcx, [rsi+90h]
0x18012a194  lea     rdx, [rsp+2D8h+var_258]
0x18012a19c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18012a1a1  nop
0x18012a1a2  lea     rcx, [rsp+2D8h+var_258]
0x18012a1aa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a1af  jmp     short loc_18012A1D0
0x18012a1b1  mov     rcx, [rsi]
0x18012a1b4  dec     qword ptr [rdi+8]
0x18012a1b8  mov     rax, [rsi+8]
0x18012a1bc  mov     [rax], rcx
0x18012a1bf  mov     rax, [rsi+8]
0x18012a1c3  mov     [rcx+8], rax
0x18012a1c7  mov     rdx, rsi
0x18012a1ca  call    ??$_Freenode@V?$allocator@U?$_List_node@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@PEAX@std@@@std@@@?$_List_node@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>::_Freenode<std::allocator<std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>>>(std::allocator<std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>> &,std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *> *)
0x18012a1cf  nop
0x18012a1d0  lea     rcx, [rsp+2D8h+var_280]
0x18012a1d5  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x18012a1da  nop
0x18012a1db  lea     rcx, [rsp+2D8h+var_288]
0x18012a1e0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18012a1e5  nop
0x18012a1e6  jmp     short $+2
0x18012a1e8  xor     esi, esi
0x18012a1ea  lea     rcx, [rsp+2D8h+hKey]
0x18012a1ef  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012a1f4  nop
0x18012a1f5  lea     rcx, [rsp+2D8h+var_270]
0x18012a1fa  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012a1ff  mov     eax, esi
0x18012a201  mov     rcx, [rsp+2D8h+var_18]
0x18012a209  xor     rcx, rsp; StackCookie
0x18012a20c  call    __security_check_cookie
0x18012a211  lea     r11, [rsp+2D8h+var_8]
0x18012a219  mov     rsi, [r11+18h]
0x18012a21d  mov     rdi, [r11+20h]
0x18012a221  mov     rsp, r11
0x18012a224  pop     r14
0x18012a226  retn
```
