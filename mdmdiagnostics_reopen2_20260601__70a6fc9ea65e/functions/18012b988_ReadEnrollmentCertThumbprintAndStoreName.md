# ReadEnrollmentCertThumbprintAndStoreName

- ea: `0x18012b988`
- end: `0x18012be12`
- name: `ReadEnrollmentCertThumbprintAndStoreName`
- size: `1162`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18012cbf8`

## callees

- `0x180019080`
- `0x1800e68b0`
- `0x1800e734c`
- `0x1800e7de8`
- `0x1800e8508`
- `0x1800ed46c`
- `0x1800eef08`
- `0x1800efd9c`
- `0x1800faa0c`
- `0x180109344`
- `0x180128cb4`
- `0x180129250`
- `0x180129278`
- `0x1801298ac`
- `0x1801298d4`
- `0x18012a958`
- `0x18012b988`
- `0x180134f10`
- `0x180134f6c`
- `0x18013c828`
- `0x18013cdc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012b9f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012b9f8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012ba9f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012bb84`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012bc70`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012ba9f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012bb84`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012bc70`
- `RPCRT4!UuidFromStringW` at `0x18012bca3`
- `RPCRT4!UuidFromStringW` at `0x18012bca3`
- `dmEnrollEngine!__imp_?GetEnrollmentClientContext@@YAJU_GUID@@PEAKPEAPEAXPEAPEBU_CERT_CONTEXT@@@Z` at `0x18012bd0d`
- `dmEnrollEngine!__imp_?GetEnrollmentClientContext@@YAJU_GUID@@PEAKPEAPEAXPEAPEBU_CERT_CONTEXT@@@Z` at `0x18012bd0d`
- `dmEnrollEngine!__imp_OpenEnrollmentsHKEY` at `0x18012ba21`
- `dmEnrollEngine!__imp_OpenEnrollmentsHKEY` at `0x18012ba21`

## string_xrefs

- `0x18012ba38`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`

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
0x18012b988  mov     [rsp+arg_8], rsi
0x18012b98d  mov     [rsp+arg_10], rdi
0x18012b992  push    r14
0x18012b994  sub     rsp, 2D0h
0x18012b99b  mov     rax, cs:__security_cookie
0x18012b9a2  xor     rax, rsp
0x18012b9a5  mov     [rsp+2D8h+var_18], rax
0x18012b9ad  mov     rdi, rcx
0x18012b9b0  xorps   xmm1, xmm1
0x18012b9b3  movdqu  [rsp+2D8h+var_270], xmm1
0x18012b9b9  mov     [rsp+2D8h+hKey], 0
0x18012b9c2  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18012b9c7  lea     rdx, [rsp+2D8h+var_270]
0x18012b9cc  mov     rcx, rax
0x18012b9cf  call    ?GetEnrollmentId@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> &)
0x18012b9d4  mov     esi, eax
0x18012b9d6  test    eax, eax
0x18012b9d8  jns     short loc_18012B9E1
0x18012b9da  mov     edx, 63Bh
0x18012b9df  jmp     short loc_18012BA38
0x18012b9e1  mov     rsi, [rsp+2D8h+hKey]
0x18012b9e6  test    rsi, rsi
0x18012b9e9  jz      short loc_18012BA0E
0x18012b9eb  lea     rcx, [rsp+2D8h+var_288]; this
0x18012b9f0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18012b9f5  mov     rcx, rsi; hKey
0x18012b9f8  call    cs:__imp_RegCloseKey
0x18012b9ff  nop     dword ptr [rax+rax+00h]
0x18012ba04  lea     rcx, [rsp+2D8h+var_288]; this
0x18012ba09  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18012ba0e  mov     [rsp+2D8h+hKey], 0
0x18012ba17  lea     rdx, [rsp+2D8h+hKey]
0x18012ba1c  mov     ecx, 20019h
0x18012ba21  call    cs:__imp_OpenEnrollmentsHKEY
0x18012ba28  nop     dword ptr [rax+rax+00h]
0x18012ba2d  mov     esi, eax
0x18012ba2f  test    eax, eax
0x18012ba31  jns     short loc_18012BA54
0x18012ba33  mov     edx, 63Ch; void *
0x18012ba38  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012ba3f  mov     r9d, eax; char *
0x18012ba42  mov     rcx, [rsp+2D8h]; this
0x18012ba4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012ba4f  jmp     loc_18012BDD4
0x18012ba54  mov     [rsp+2D8h+var_294], 208h
0x18012ba5c  mov     rsi, qword ptr [rsp+2D8h+var_270]
0x18012ba61  test    rsi, rsi
0x18012ba64  jz      short loc_18012BA6B
0x18012ba66  mov     rdx, [rsi]
0x18012ba69  jmp     short loc_18012BA6D
0x18012ba6b  xor     edx, edx; lpSubKey
0x18012ba6d  lea     rax, [rsp+2D8h+var_294]
0x18012ba72  mov     [rsp+2D8h+pcbData], rax; pcbData
0x18012ba77  lea     rax, [rsp+2D8h+var_228]
0x18012ba7f  mov     [rsp+2D8h+pvData], rax; pvData
0x18012ba84  mov     [rsp+2D8h+pdwType], 0; pdwType
0x18012ba8d  mov     r9d, 2; dwFlags
0x18012ba93  lea     r8, aRootcertthumbp; "RootCertThumbPrint"
0x18012ba9a  mov     rcx, [rsp+2D8h+hKey]; hkey
0x18012ba9f  call    cs:__imp_RegGetValueW
0x18012baa6  nop     dword ptr [rax+rax+00h]
0x18012baab  test    eax, eax
0x18012baad  jnz     loc_18012BB3E
0x18012bab3  mov     [rsp+2D8h+var_298], al
0x18012bab7  lea     r9, [rsp+2D8h+var_298]
0x18012babc  lea     rdx, [rsp+2D8h+var_228]
0x18012bac4  mov     rcx, rdi
0x18012bac7  call    ??$emplace_back@AEAY0BAE@GAEAY04$$CBG_N@?$list@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@QEAAAEAVCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAY0BAE@GAEAY04$$CBG$$QEA_N@Z; std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo>::emplace_back<ushort (&)[260],ushort const (&)[5],bool>(ushort (&)[260],ushort const (&)[5],bool &&)
0x18012bacc  mov     rax, [rdi]
0x18012bacf  mov     rcx, [rax+8]
0x18012bad3  add     rcx, 10h; this
0x18012bad7  call    ?RetrieveCertInfoWithThumbPrint@MdmDiagnosticSource@Mdm@Windows@Microsoft@@YAJAEAVCertInfo@1234@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveCertInfoWithThumbPrint(Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo &)
0x18012badc  mov     rcx, [rdi]
0x18012badf  mov     r14, [rcx+8]
0x18012bae3  test    eax, eax
0x18012bae5  js      short loc_18012BB20
0x18012bae7  lea     rdx, aDeviceManageme; "Device Management Root"
0x18012baee  lea     rcx, [rsp+2D8h+var_258]
0x18012baf6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012bafb  nop
0x18012bafc  lea     rcx, [r14+90h]
0x18012bb03  lea     rdx, [rsp+2D8h+var_258]
0x18012bb0b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18012bb10  nop
0x18012bb11  lea     rcx, [rsp+2D8h+var_258]
0x18012bb19  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012bb1e  jmp     short loc_18012BB3E
0x18012bb20  mov     rcx, [r14]
0x18012bb23  dec     qword ptr [rdi+8]
0x18012bb27  mov     rax, [r14+8]
0x18012bb2b  mov     [rax], rcx
0x18012bb2e  mov     rax, [r14+8]
0x18012bb32  mov     [rcx+8], rax
0x18012bb36  mov     rdx, r14
0x18012bb39  call    ??$_Freenode@V?$allocator@U?$_List_node@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@PEAX@std@@@std@@@?$_List_node@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>::_Freenode<std::allocator<std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>>>(std::allocator<std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>> &,std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *> *)
0x18012bb3e  mov     [rsp+2D8h+var_294], 208h
0x18012bb46  test    rsi, rsi
0x18012bb49  jz      short loc_18012BB50
0x18012bb4b  mov     rdx, [rsi]
0x18012bb4e  jmp     short loc_18012BB52
0x18012bb50  xor     edx, edx; lpSubKey
0x18012bb52  lea     rax, [rsp+2D8h+var_294]
0x18012bb57  mov     [rsp+2D8h+pcbData], rax; pcbData
0x18012bb5c  lea     rax, [rsp+2D8h+var_228]
0x18012bb64  mov     [rsp+2D8h+pvData], rax; pvData
0x18012bb69  mov     [rsp+2D8h+pdwType], 0; pdwType
0x18012bb72  mov     r9d, 2; dwFlags
0x18012bb78  lea     r8, aIntermediatece; "IntermediateCertThumbPrint"
0x18012bb7f  mov     rcx, [rsp+2D8h+hKey]; hkey
0x18012bb84  call    cs:__imp_RegGetValueW
0x18012bb8b  nop     dword ptr [rax+rax+00h]
0x18012bb90  test    eax, eax
0x18012bb92  jnz     loc_18012BC2A
0x18012bb98  mov     [rsp+2D8h+var_298], al
0x18012bb9c  lea     r9, [rsp+2D8h+var_298]
0x18012bba1  lea     r8, aCa; "CA"
0x18012bba8  lea     rdx, [rsp+2D8h+var_228]
0x18012bbb0  mov     rcx, rdi
0x18012bbb3  call    ??$emplace_back@AEAY0BAE@GAEAY02$$CBG_N@?$list@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@QEAAAEAVCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAY0BAE@GAEAY02$$CBG$$QEA_N@Z; std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo>::emplace_back<ushort (&)[260],ushort const (&)[3],bool>(ushort (&)[260],ushort const (&)[3],bool &&)
0x18012bbb8  mov     rax, [rdi]
0x18012bbbb  mov     rcx, [rax+8]
0x18012bbbf  add     rcx, 10h; this
0x18012bbc3  call    ?RetrieveCertInfoWithThumbPrint@MdmDiagnosticSource@Mdm@Windows@Microsoft@@YAJAEAVCertInfo@1234@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveCertInfoWithThumbPrint(Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo &)
0x18012bbc8  mov     rcx, [rdi]
0x18012bbcb  mov     r14, [rcx+8]
0x18012bbcf  test    eax, eax
0x18012bbd1  js      short loc_18012BC0C
0x18012bbd3  lea     rdx, aDeviceManageme_0; "Device Management Intermediate"
0x18012bbda  lea     rcx, [rsp+2D8h+var_258]
0x18012bbe2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012bbe7  nop
0x18012bbe8  lea     rcx, [r14+90h]
0x18012bbef  lea     rdx, [rsp+2D8h+var_258]
0x18012bbf7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18012bbfc  nop
0x18012bbfd  lea     rcx, [rsp+2D8h+var_258]
0x18012bc05  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012bc0a  jmp     short loc_18012BC2A
0x18012bc0c  mov     rcx, [r14]
0x18012bc0f  dec     qword ptr [rdi+8]
0x18012bc13  mov     rax, [r14+8]
0x18012bc17  mov     [rax], rcx
0x18012bc1a  mov     rax, [r14+8]
0x18012bc1e  mov     [rcx+8], rax
0x18012bc22  mov     rdx, r14
0x18012bc25  call    ??$_Freenode@V?$allocator@U?$_List_node@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@PEAX@std@@@std@@@?$_List_node@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>::_Freenode<std::allocator<std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>>>(std::allocator<std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>> &,std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *> *)
0x18012bc2a  mov     [rsp+2D8h+var_294], 208h
0x18012bc32  test    rsi, rsi
0x18012bc35  jz      short loc_18012BC3C
0x18012bc37  mov     rdx, [rsi]
0x18012bc3a  jmp     short loc_18012BC3E
0x18012bc3c  xor     edx, edx; lpSubKey
0x18012bc3e  lea     rax, [rsp+2D8h+var_294]
0x18012bc43  mov     [rsp+2D8h+pcbData], rax; pcbData
0x18012bc48  lea     rax, [rsp+2D8h+var_228]
0x18012bc50  mov     [rsp+2D8h+pvData], rax; pvData
0x18012bc55  mov     [rsp+2D8h+pdwType], 0; pdwType
0x18012bc5e  mov     r9d, 2; dwFlags
0x18012bc64  lea     r8, aDmpcertthumbpr; "DMPCertThumbPrint"
0x18012bc6b  mov     rcx, [rsp+2D8h+hKey]; hkey
0x18012bc70  call    cs:__imp_RegGetValueW
0x18012bc77  nop     dword ptr [rax+rax+00h]
0x18012bc7c  test    eax, eax
0x18012bc7e  jnz     loc_18012BDD0
0x18012bc84  xorps   xmm0, xmm0
0x18012bc87  movups  xmmword ptr [rsp+2D8h+Uuid.Data1], xmm0
0x18012bc8f  test    rsi, rsi
0x18012bc92  jz      short loc_18012BC99
0x18012bc94  mov     rcx, [rsi]
0x18012bc97  jmp     short loc_18012BC9B
0x18012bc99  xor     ecx, ecx; StringUuid
0x18012bc9b  lea     rdx, [rsp+2D8h+Uuid]; Uuid
0x18012bca3  call    cs:__imp_UuidFromStringW
0x18012bcaa  nop     dword ptr [rax+rax+00h]
0x18012bcaf  test    eax, eax
0x18012bcb1  jnz     loc_18012BDD0
0x18012bcb7  mov     [rsp+2D8h+var_288], 0
0x18012bcc0  mov     [rsp+2D8h+var_278], eax
0x18012bcc4  mov     [rsp+2D8h+var_280], 0
0x18012bccd  xor     edx, edx
0x18012bccf  lea     rcx, [rsp+2D8h+var_280]
0x18012bcd4  call    ?reset@?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEBU_CERT_CONTEXT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(_CERT_CONTEXT const *)
0x18012bcd9  xor     edx, edx
0x18012bcdb  lea     rcx, [rsp+2D8h+var_288]
0x18012bce0  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18012bce5  movaps  xmm0, xmmword ptr [rsp+2D8h+Uuid.Data1]
0x18012bced  movdqa  [rsp+2D8h+var_258], xmm0
0x18012bcf6  lea     r9, [rsp+2D8h+var_280]
0x18012bcfb  lea     r8, [rsp+2D8h+var_288]
0x18012bd00  lea     rdx, [rsp+2D8h+var_278]
0x18012bd05  lea     rcx, [rsp+2D8h+var_258]
0x18012bd0d  call    cs:__imp_?GetEnrollmentClientContext@@YAJU_GUID@@PEAKPEAPEAXPEAPEBU_CERT_CONTEXT@@@Z; GetEnrollmentClientContext(_GUID,ulong *,void * *,_CERT_CONTEXT const * *)
0x18012bd14  nop     dword ptr [rax+rax+00h]
0x18012bd19  test    eax, eax
0x18012bd1b  js      loc_18012BDBA
0x18012bd21  mov     [rsp+2D8h+var_298], 1
0x18012bd26  lea     r9, [rsp+2D8h+var_298]
0x18012bd2b  lea     r8, aMy_0; "MY"
0x18012bd32  lea     rdx, [rsp+2D8h+var_228]
0x18012bd3a  mov     rcx, rdi
0x18012bd3d  call    ??$emplace_back@AEAY0BAE@GAEAY02$$CBG_N@?$list@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@QEAAAEAVCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAY0BAE@GAEAY02$$CBG$$QEA_N@Z; std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo>::emplace_back<ushort (&)[260],ushort const (&)[3],bool>(ushort (&)[260],ushort const (&)[3],bool &&)
0x18012bd42  mov     rax, [rdi]
0x18012bd45  mov     rcx, [rax+8]
0x18012bd49  add     rcx, 10h; this
0x18012bd4d  mov     rdx, [rsp+2D8h+var_280]; struct _CERT_CONTEXT *
0x18012bd52  call    ?RetrieveCertInfoWithThumbPrint@MdmDiagnosticSource@Mdm@Windows@Microsoft@@YAJAEAVCertInfo@1234@PEBU_CERT_CONTEXT@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveCertInfoWithThumbPrint(Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo &,_CERT_CONTEXT const *)
0x18012bd57  mov     rcx, [rdi]
0x18012bd5a  mov     rsi, [rcx+8]
0x18012bd5e  test    eax, eax
0x18012bd60  js      short loc_18012BD9B
0x18012bd62  lea     rdx, aDeviceManageme_1; "Device Management Client"
0x18012bd69  lea     rcx, [rsp+2D8h+var_258]
0x18012bd71  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012bd76  nop
0x18012bd77  lea     rcx, [rsi+90h]
0x18012bd7e  lea     rdx, [rsp+2D8h+var_258]
0x18012bd86  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18012bd8b  nop
0x18012bd8c  lea     rcx, [rsp+2D8h+var_258]
0x18012bd94  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012bd99  jmp     short loc_18012BDBA
0x18012bd9b  mov     rcx, [rsi]
0x18012bd9e  dec     qword ptr [rdi+8]
0x18012bda2  mov     rax, [rsi+8]
0x18012bda6  mov     [rax], rcx
0x18012bda9  mov     rax, [rsi+8]
0x18012bdad  mov     [rcx+8], rax
0x18012bdb1  mov     rdx, rsi
0x18012bdb4  call    ??$_Freenode@V?$allocator@U?$_List_node@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@PEAX@std@@@std@@@?$_List_node@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>::_Freenode<std::allocator<std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>>>(std::allocator<std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *>> &,std::_List_node<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,void *> *)
0x18012bdb9  nop
0x18012bdba  lea     rcx, [rsp+2D8h+var_280]
0x18012bdbf  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x18012bdc4  nop
0x18012bdc5  lea     rcx, [rsp+2D8h+var_288]
0x18012bdca  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18012bdcf  nop
0x18012bdd0  jmp     short $+2
0x18012bdd2  xor     esi, esi
0x18012bdd4  lea     rcx, [rsp+2D8h+hKey]
0x18012bdd9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012bdde  nop
0x18012bddf  lea     rcx, [rsp+2D8h+var_270]
0x18012bde4  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18012bde9  mov     eax, esi
0x18012bdeb  mov     rcx, [rsp+2D8h+var_18]
0x18012bdf3  xor     rcx, rsp; StackCookie
0x18012bdf6  call    __security_check_cookie
0x18012bdfb  lea     r11, [rsp+2D8h+var_8]
0x18012be03  mov     rsi, [r11+18h]
0x18012be07  mov     rdi, [r11+20h]
0x18012be0b  mov     rsp, r11
0x18012be0e  pop     r14
0x18012be10  retn
```
