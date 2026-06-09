# CertAttestationCspNode::GetAttestationStatus(_GUID,int,ushort * *)

- ea: `0x1800bcd44`
- end: `0x1800bdbe5`
- name: `?GetAttestationStatus@CertAttestationCspNode@@AEAAJU_GUID@@HPEAPEAG@Z`
- size: `3745`
- prototype: `__int64 __fastcall(CertAttestationCspNode *__hidden this, struct _GUID *__struct_ptr, int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800bdc60`

## callees

- `0x180008de0`
- `0x18000b744`
- `0x18000b9ec`
- `0x18000bef4`
- `0x18000d4d4`
- `0x180015888`
- `0x180025450`
- `0x180025a78`
- `0x180025a9c`
- `0x18002dc38`
- `0x18002e4b0`
- `0x180039900`
- `0x180039928`
- `0x180039950`
- `0x18003f3a0`
- `0x18003f764`
- `0x180050f28`
- `0x180081d74`
- `0x1800bc9c8`
- `0x1800bca10`
- `0x1800bca38`
- `0x1800bcd44`
- `0x1800bded0`
- `0x1800bdf2c`

## import_xrefs

- `DMCmnUtils!DmGenerateAttestationClaimsOld` at `0x1800bcfc8`
- `DMCmnUtils!DmGenerateAttestationClaimsOld` at `0x1800bd2a0`
- `DMCmnUtils!DmGenerateAttestationClaimsOld` at `0x1800bcfc8`
- `DMCmnUtils!DmGenerateAttestationClaimsOld` at `0x1800bd2a0`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800bd11d`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800bd11d`
- `DMCmnUtils!EncodeBase64W` at `0x1800bd45b`
- `DMCmnUtils!EncodeBase64W` at `0x1800bd59f`
- `DMCmnUtils!EncodeBase64W` at `0x1800bd6ca`
- `DMCmnUtils!EncodeBase64W` at `0x1800bd7f3`
- `DMCmnUtils!EncodeBase64W` at `0x1800bd93c`
- `DMCmnUtils!EncodeBase64W` at `0x1800bd45b`
- `DMCmnUtils!EncodeBase64W` at `0x1800bd59f`
- `DMCmnUtils!EncodeBase64W` at `0x1800bd6ca`
- `DMCmnUtils!EncodeBase64W` at `0x1800bd7f3`
- `DMCmnUtils!EncodeBase64W` at `0x1800bd93c`
- `dmEnrollEngine!GetEnrollmentTenantID` at `0x1800bd196`
- `dmEnrollEngine!GetEnrollmentTenantID` at `0x1800bd196`
- `dmEnrollEngine!__imp_?GetEnrollmentClientContext@@YAJU_GUID@@PEAKPEAPEAXPEAPEBU_CERT_CONTEXT@@@Z` at `0x1800bce38`
- `dmEnrollEngine!__imp_?GetEnrollmentClientContext@@YAJU_GUID@@PEAKPEAPEAXPEAPEBU_CERT_CONTEXT@@@Z` at `0x1800bce38`
- `dsreg!DsrGetJoinInfo` at `0x1800bd1e2`
- `dsreg!DsrGetJoinInfo` at `0x1800bd1e2`
- `dsreg!DsrFreeJoinInfo` at `0x1800bd2e2`
- `dsreg!DsrFreeJoinInfo` at `0x1800bd2e2`

## string_xrefs

- `0x1800bd413`: `<?xml version="1.0"?><ac:AdditionalContext xmlns:ac="http://schemas.xmlsoap.org/ws/2006/12/authorization"> `

## pseudocode

```c
// Hidden C++ exception states: #wind=32 #try_helpers=1
__int64 __fastcall CertAttestationCspNode::GetAttestationStatus(
        CertAttestationCspNode *this,
        struct _GUID *a2,
        int a3,
        unsigned __int16 **a4)
{
  int EnrollmentClientContext; // eax
  unsigned int v8; // ebx
  int v10; // ebx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  int EnrollmentTenantID; // ecx
  unsigned __int64 v15; // rax
  char v16; // bl
  void *v17; // rsi
  __int64 v18; // rbx
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // r8
  __int64 v22; // r8
  __int64 v23; // r8
  __int64 v24; // r8
  __int64 v25; // r8
  __int64 v26; // r8
  __int64 v27; // r8
  __int128 *p_Src; // rdx
  unsigned __int16 **bstr; // rax
  unsigned __int16 *v30; // rcx
  void *v31; // rcx
  void *v32; // rcx
  void *v33; // rcx
  void *v34; // rcx
  void *v35; // rcx
  int v36; // [rsp+20h] [rbp-2D8h]
  int v37; // [rsp+20h] [rbp-2D8h]
  void *v38; // [rsp+60h] [rbp-298h] BYREF
  void *v39; // [rsp+68h] [rbp-290h] BYREF
  void *v40; // [rsp+70h] [rbp-288h] BYREF
  void *v41; // [rsp+78h] [rbp-280h] BYREF
  void *v42; // [rsp+80h] [rbp-278h] BYREF
  unsigned int v43; // [rsp+88h] [rbp-270h] BYREF
  const struct _CERT_CONTEXT *v44; // [rsp+90h] [rbp-268h] BYREF
  unsigned int v45; // [rsp+98h] [rbp-260h] BYREF
  unsigned int v46; // [rsp+9Ch] [rbp-25Ch] BYREF
  unsigned int v47; // [rsp+A0h] [rbp-258h] BYREF
  unsigned int v48; // [rsp+A4h] [rbp-254h] BYREF
  unsigned int v49; // [rsp+A8h] [rbp-250h] BYREF
  __int64 v50; // [rsp+B0h] [rbp-248h] BYREF
  void *v51; // [rsp+B8h] [rbp-240h] BYREF
  unsigned __int16 *v52; // [rsp+C0h] [rbp-238h] BYREF
  unsigned __int16 *v53; // [rsp+C8h] [rbp-230h] BYREF
  unsigned __int16 *v54; // [rsp+D0h] [rbp-228h] BYREF
  unsigned __int16 *v55; // [rsp+D8h] [rbp-220h] BYREF
  unsigned __int16 *v56; // [rsp+E0h] [rbp-218h] BYREF
  void *v57; // [rsp+E8h] [rbp-210h] BYREF
  unsigned __int16 *v58[2]; // [rsp+F0h] [rbp-208h] BYREF
  struct _GUID v59; // [rsp+100h] [rbp-1F8h] BYREF
  char v60; // [rsp+110h] [rbp-1E8h]
  struct _GUID v61; // [rsp+120h] [rbp-1D8h] BYREF
  char v62; // [rsp+130h] [rbp-1C8h]
  void **v63; // [rsp+140h] [rbp-1B8h] BYREF
  unsigned __int8 *v64; // [rsp+148h] [rbp-1B0h] BYREF
  char v65; // [rsp+150h] [rbp-1A8h]
  _QWORD v66[2]; // [rsp+158h] [rbp-1A0h] BYREF
  _WORD v67[8]; // [rsp+168h] [rbp-190h] BYREF
  _QWORD v68[2]; // [rsp+178h] [rbp-180h] BYREF
  _WORD v69[8]; // [rsp+188h] [rbp-170h] BYREF
  _QWORD v70[2]; // [rsp+198h] [rbp-160h] BYREF
  _WORD v71[8]; // [rsp+1A8h] [rbp-150h] BYREF
  _QWORD v72[2]; // [rsp+1B8h] [rbp-140h] BYREF
  _WORD v73[8]; // [rsp+1C8h] [rbp-130h] BYREF
  _QWORD v74[2]; // [rsp+1D8h] [rbp-120h] BYREF
  _WORD v75[8]; // [rsp+1E8h] [rbp-110h] BYREF
  void **v76; // [rsp+1F8h] [rbp-100h] BYREF
  unsigned __int8 *v77; // [rsp+200h] [rbp-F8h] BYREF
  char v78; // [rsp+208h] [rbp-F0h]
  __int128 Src; // [rsp+210h] [rbp-E8h] BYREF
  __m128i si128; // [rsp+220h] [rbp-D8h]
  __int128 v81; // [rsp+230h] [rbp-C8h] BYREF
  __int128 v82; // [rsp+240h] [rbp-B8h]
  __int128 v83; // [rsp+250h] [rbp-A8h]
  __int128 v84; // [rsp+260h] [rbp-98h]
  __int128 v85; // [rsp+270h] [rbp-88h]
  __m256i v86; // [rsp+280h] [rbp-78h]
  wchar_t v87; // [rsp+2A0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+0h]

  Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src) = 0;
  v44 = 0;
  v43 = 0;
  v57 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v42 = 0;
  v41 = 0;
  v40 = 0;
  v48 = 0;
  v49 = 0;
  v39 = 0;
  v38 = 0;
  wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(
    &v44,
    0);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v57,
    0);
  v59 = *a2;
  EnrollmentClientContext = GetEnrollmentClientContext(&v59, &v43, &v57, &v44);
  v8 = EnrollmentClientContext;
  if ( EnrollmentClientContext >= 0 )
  {
    v63 = &v40;
    v64 = 0;
    v65 = 1;
    *(_QWORD *)&v61.Data1 = &v41;
    *(_QWORD *)v61.Data4 = 0;
    v62 = 1;
    *(_QWORD *)&v59.Data1 = &v42;
    *(_QWORD *)v59.Data4 = 0;
    v60 = 1;
    v10 = DmGenerateAttestationClaimsOld(
            v44,
            1,
            (unsigned __int8 **)v59.Data4,
            &v45,
            0,
            0,
            (unsigned __int8 **)v61.Data4,
            &v46,
            &v64,
            &v47,
            1);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&v59);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&v61);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&v63);
    if ( v10 >= 0 )
    {
      EnrollmentTenantID = 0;
      v50 = 0;
      v58[0] = 0;
      v15 = 0;
      v51 = 0;
      v16 = 0;
      LOWORD(v59.Data1) = 0;
      BYTE2(v59.Data1) = 0;
      *(_QWORD *)v59.Data4 = 0;
      if ( !a3 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          v58,
          0);
        if ( (int)DmGetActiveUserSid(v58) >= 0 )
          AutoImpersonate::ImpersonateSID((AutoImpersonate *)&v59, v58[0]);
        v17 = v51;
        if ( v51 )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)&v61);
          MemoryFree(v17);
          wil::last_error_context::~last_error_context((wil::last_error_context *)&v61);
        }
        v51 = 0;
        v61 = *a2;
        EnrollmentTenantID = GetEnrollmentTenantID(&v61, &v51);
        if ( EnrollmentTenantID >= 0 )
          v16 = 1;
        v15 = (unsigned __int64)v51;
      }
      *(_QWORD *)&v61.Data1 = &v50;
      v61.Data4[0] = 1;
      if ( EnrollmentTenantID >= 0 && (int)DsrGetJoinInfo(v15 & -(__int64)(v16 != 0), &v50) >= 0 && v50 )
      {
        if ( !a3 )
          AutoImpersonate::RevertToSelf((AutoImpersonate *)&v59);
        v76 = &v38;
        v77 = 0;
        v78 = 1;
        v63 = &v39;
        v64 = 0;
        v65 = 1;
        DmGenerateAttestationClaimsOld(
          *(const struct _CERT_CONTEXT **)(v50 + 8),
          a3,
          &v64,
          &v48,
          &v77,
          &v49,
          0,
          0,
          0,
          0,
          1);
        wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&v63);
        wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&v76);
      }
      if ( !a3 )
        AutoImpersonate::RevertToSelf((AutoImpersonate *)&v59);
      DsrFreeJoinInfo(v50);
      AutoImpersonate::~AutoImpersonate((AutoImpersonate *)&v59);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v51);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v58);
      v74[0] = v75;
      v74[1] = v75;
      v75[0] = 0;
      v72[0] = v73;
      v72[1] = v73;
      v73[0] = 0;
      v70[0] = v71;
      v70[1] = v71;
      v71[0] = 0;
      v68[0] = v69;
      v68[1] = v69;
      v69[0] = 0;
      v66[0] = v67;
      v66[1] = v67;
      v67[0] = 0;
      v56 = 0;
      v55 = 0;
      v54 = 0;
      v53 = 0;
      v52 = 0;
      std::wstring::_Append<unsigned short>(&Src);
      if ( v42
        && (wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &v56,
              0),
            (int)EncodeBase64W((const unsigned __int8 *)v42, v45, &v56) >= 0) )
      {
        v81 = *(_OWORD *)L"<ac:ContextItem Name=\"AIKAttestationClaim\"><ac:Value>";
        v82 = *(_OWORD *)L"extItem Name=\"AIKAttestationClaim\"><ac:Value>";
        v83 = *(_OWORD *)L"Name=\"AIKAttestationClaim\"><ac:Value>";
        v84 = *(_OWORD *)L"KAttestationClaim\"><ac:Value>";
        v85 = *(_OWORD *)L"tionClaim\"><ac:Value>";
        *(_OWORD *)v86.m256i_i8 = *(_OWORD *)L"m\"><ac:Value>";
        *(_OWORD *)((char *)&v86.m256i_u64[1] + 4) = *(_OWORD *)L":Value>";
        v18 = -1;
        if ( v56 )
        {
          v19 = -1;
          do
            ++v19;
          while ( *((_WORD *)&v81 + v19) );
          if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  v74,
                                  &v81,
                                  v19)
            && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  v74,
                                  v56)
            && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  v74,
                                  L"</ac:Value></ac:ContextItem>") )
          {
            v20 = -1;
            do
              ++v20;
            while ( *(_WORD *)(v74[0] + 2 * v20) );
            std::wstring::_Append<unsigned short>(&Src);
          }
        }
      }
      else
      {
        v18 = -1;
      }
      if ( v41 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v55,
          0);
        if ( (int)EncodeBase64W((const unsigned __int8 *)v41, v46, &v55) >= 0 )
        {
          v81 = *(_OWORD *)L"<ac:ContextItem Name=\"AIKPub\"><ac:Value>";
          v82 = *(_OWORD *)L"extItem Name=\"AIKPub\"><ac:Value>";
          v83 = *(_OWORD *)L"Name=\"AIKPub\"><ac:Value>";
          v84 = *(_OWORD *)L"KPub\"><ac:Value>";
          v85 = *(_OWORD *)L"c:Value>";
          v86.m256i_i16[0] = aAcContextitemN[40];
          if ( v55 )
          {
            v21 = -1;
            do
              ++v21;
            while ( *((_WORD *)&v81 + v21) );
            if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                    v72,
                                    &v81,
                                    v21)
              && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                    v72,
                                    v55)
              && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                    v72,
                                    L"</ac:Value></ac:ContextItem>") )
            {
              v22 = -1;
              do
                ++v22;
              while ( *(_WORD *)(v72[0] + 2 * v22) );
              std::wstring::_Append<unsigned short>(&Src);
            }
          }
        }
      }
      if ( v40 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v54,
          0);
        if ( (int)EncodeBase64W((const unsigned __int8 *)v40, v47, &v54) >= 0 )
        {
          v81 = *(_OWORD *)L"<ac:ContextItem Name=\"AIKCert\"><ac:Value>";
          v82 = *(_OWORD *)L"extItem Name=\"AIKCert\"><ac:Value>";
          v83 = *(_OWORD *)L"Name=\"AIKCert\"><ac:Value>";
          v84 = *(_OWORD *)L"KCert\"><ac:Value>";
          v85 = *(_OWORD *)L"ac:Value>";
          v86.m256i_i32[0] = *(_DWORD *)L">";
          if ( v54 )
          {
            v23 = -1;
            do
              ++v23;
            while ( *((_WORD *)&v81 + v23) );
            if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                    v70,
                                    &v81,
                                    v23)
              && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                    v70,
                                    v54)
              && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                    v70,
                                    L"</ac:Value></ac:ContextItem>") )
            {
              v24 = -1;
              do
                ++v24;
              while ( *(_WORD *)(v70[0] + 2 * v24) );
              std::wstring::_Append<unsigned short>(&Src);
            }
          }
        }
      }
      if ( v39 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v53,
          0);
        if ( (int)EncodeBase64W((const unsigned __int8 *)v39, v48, &v53) >= 0 )
        {
          v81 = *(_OWORD *)L"<ac:ContextItem Name=\"AadAIKAttestationClaim\"><ac:Value>";
          v82 = *(_OWORD *)L"extItem Name=\"AadAIKAttestationClaim\"><ac:Value>";
          v83 = *(_OWORD *)L"Name=\"AadAIKAttestationClaim\"><ac:Value>";
          v84 = *(_OWORD *)L"dAIKAttestationClaim\"><ac:Value>";
          v85 = *(_OWORD *)L"stationClaim\"><ac:Value>";
          v86 = *(__m256i *)L"laim\"><ac:Value>";
          v87 = aAcContextitemN_1[56];
          if ( v53 )
          {
            v25 = -1;
            do
              ++v25;
            while ( *((_WORD *)&v81 + v25) );
            if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                    v68,
                                    &v81,
                                    v25)
              && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                    v68,
                                    v53)
              && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                    v68,
                                    L"</ac:Value></ac:ContextItem>") )
            {
              v26 = -1;
              do
                ++v26;
              while ( *(_WORD *)(v68[0] + 2 * v26) );
              std::wstring::_Append<unsigned short>(&Src);
            }
          }
        }
      }
      if ( v38 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v52,
          0);
        if ( (int)EncodeBase64W((const unsigned __int8 *)v38, v49, &v52) >= 0 )
        {
          v81 = *(_OWORD *)L"<ac:ContextItem Name=\"AADPub\"><ac:Value>";
          v82 = *(_OWORD *)L"extItem Name=\"AADPub\"><ac:Value>";
          v83 = *(_OWORD *)L"Name=\"AADPub\"><ac:Value>";
          v84 = *(_OWORD *)L"DPub\"><ac:Value>";
          v85 = *(_OWORD *)L"c:Value>";
          v86.m256i_i16[0] = aAcContextitemN_3[40];
          if ( v52 )
          {
            v27 = -1;
            do
              ++v27;
            while ( *((_WORD *)&v81 + v27) );
            if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                    v66,
                                    &v81,
                                    v27)
              && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                    v66,
                                    v52)
              && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                    v66,
                                    L"</ac:Value></ac:ContextItem>") )
            {
              do
                ++v18;
              while ( *(_WORD *)(v66[0] + 2 * v18) );
              std::wstring::_Append<unsigned short>(&Src);
            }
          }
        }
      }
      std::wstring::_Append<unsigned short>(&Src);
      p_Src = &Src;
      if ( si128.m128i_i64[1] > 7uLL )
        p_Src = (__int128 *)Src;
      bstr = (unsigned __int16 **)wil::make_bstr(&v61, p_Src);
      v30 = *bstr;
      *bstr = 0;
      *a4 = v30;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v61);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v52);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v53);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v55);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v56);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v66);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v68);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v70);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v72);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v74);
      v31 = v38;
      v38 = 0;
      if ( v31 )
        MemoryFree(v31);
      v32 = v39;
      v39 = 0;
      if ( v32 )
        MemoryFree(v32);
      v33 = v40;
      v40 = 0;
      if ( v33 )
        MemoryFree(v33);
      v34 = v41;
      v41 = 0;
      if ( v34 )
        MemoryFree(v34);
      v35 = v42;
      v42 = 0;
      if ( v35 )
        MemoryFree(v35);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v57);
      wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v44);
      std::wstring::_Tidy_deallocate(&Src);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9E,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicestatus\\certattestation.cpp",
        (const char *)(unsigned int)v10,
        v37);
      v38 = 0;
      v39 = 0;
      v11 = v40;
      v40 = 0;
      if ( v11 )
        MemoryFree(v11);
      v12 = v41;
      v41 = 0;
      if ( v12 )
        MemoryFree(v12);
      v13 = v42;
      v42 = 0;
      if ( v13 )
        MemoryFree(v13);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v57);
      wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v44);
      std::wstring::_Tidy_deallocate(&Src);
      return (unsigned int)v10;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x95,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicestatus\\certattestation.cpp",
      (const char *)(unsigned int)EnrollmentClientContext,
      v36);
    v38 = 0;
    v39 = 0;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v57);
    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v44);
    std::wstring::_Tidy_deallocate(&Src);
    return v8;
  }
}

```

## disassembly

```asm
0x1800bcd44  mov     r11, rsp
0x1800bcd47  push    rbx
0x1800bcd48  push    rsi
0x1800bcd49  push    rdi
0x1800bcd4a  push    r12
0x1800bcd4c  push    r13
0x1800bcd4e  push    r14
0x1800bcd50  push    r15
0x1800bcd52  sub     rsp, 2C0h
0x1800bcd59  mov     rax, cs:__security_cookie
0x1800bcd60  xor     rax, rsp
0x1800bcd63  mov     [rsp+2F8h+var_48], rax
0x1800bcd6b  mov     r15, r9
0x1800bcd6e  mov     edi, r8d
0x1800bcd71  mov     r14, rdx
0x1800bcd74  xorps   xmm0, xmm0
0x1800bcd77  movups  [rsp+2F8h+Src], xmm0
0x1800bcd7f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800bcd87  movdqu  [rsp+2F8h+var_D8], xmm1
0x1800bcd90  xor     r12d, r12d
0x1800bcd93  mov     [r11-0E8h], r12w
0x1800bcd9b  mov     [r11-268h], r12
0x1800bcda2  mov     [r11-270h], r12d
0x1800bcda9  mov     [r11-210h], r12
0x1800bcdb0  mov     [r11-260h], r12d
0x1800bcdb7  mov     [r11-25Ch], r12d
0x1800bcdbe  mov     [r11-258h], r12d
0x1800bcdc5  mov     [r11-278h], r12
0x1800bcdcc  mov     [rsp+2F8h+var_280], r12
0x1800bcdd1  mov     [rsp+2F8h+var_288], r12
0x1800bcdd6  mov     [r11-254h], r12d
0x1800bcddd  mov     [r11-250h], r12d
0x1800bcde4  mov     [rsp+2F8h+var_290], r12
0x1800bcde9  mov     [rsp+2F8h+var_298], r12
0x1800bcdee  xor     edx, edx
0x1800bcdf0  lea     rcx, [r11-268h]
0x1800bcdf7  call    ?reset@?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEBU_CERT_CONTEXT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(_CERT_CONTEXT const *)
0x1800bcdfc  xor     edx, edx
0x1800bcdfe  lea     rcx, [rsp+2F8h+var_210]
0x1800bce06  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800bce0b  movaps  xmm0, xmmword ptr [r14]
0x1800bce0f  movdqa  [rsp+2F8h+var_1F8], xmm0
0x1800bce18  lea     r9, [rsp+2F8h+var_268]
0x1800bce20  lea     r8, [rsp+2F8h+var_210]
0x1800bce28  lea     rdx, [rsp+2F8h+var_270]
0x1800bce30  lea     rcx, [rsp+2F8h+var_1F8]
0x1800bce38  call    cs:__imp_?GetEnrollmentClientContext@@YAJU_GUID@@PEAKPEAPEAXPEAPEBU_CERT_CONTEXT@@@Z; GetEnrollmentClientContext(_GUID,ulong *,void * *,_CERT_CONTEXT const * *)
0x1800bce3f  nop     dword ptr [rax+rax+00h]
0x1800bce44  mov     ebx, eax
0x1800bce46  test    eax, eax
0x1800bce48  jns     loc_1800BCF0A
0x1800bce4e  mov     rcx, [rsp+2F8h]; this
0x1800bce56  mov     r9d, eax; char *
0x1800bce59  lea     r8, aOnecoreuapAdmi_102; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800bce60  mov     edx, 95h; void *
0x1800bce65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bce6a  nop
0x1800bce6b  mov     rcx, [rsp+2F8h+var_298]; void *
0x1800bce70  mov     [rsp+2F8h+var_298], r12
0x1800bce75  test    rcx, rcx
0x1800bce78  jz      short loc_1800BCE80
0x1800bce7a  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1800bce7f  nop
0x1800bce80  mov     rcx, [rsp+2F8h+var_290]; void *
0x1800bce85  mov     [rsp+2F8h+var_290], r12
0x1800bce8a  test    rcx, rcx
0x1800bce8d  jz      short loc_1800BCE95
0x1800bce8f  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1800bce94  nop
0x1800bce95  mov     rcx, [rsp+2F8h+var_288]; void *
0x1800bce9a  mov     [rsp+2F8h+var_288], r12
0x1800bce9f  test    rcx, rcx
0x1800bcea2  jz      short loc_1800BCEAA
0x1800bcea4  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1800bcea9  nop
0x1800bceaa  mov     rcx, [rsp+2F8h+var_280]; void *
0x1800bceaf  mov     [rsp+2F8h+var_280], r12
0x1800bceb4  test    rcx, rcx
0x1800bceb7  jz      short loc_1800BCEBF
0x1800bceb9  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1800bcebe  nop
0x1800bcebf  mov     rcx, [rsp+2F8h+var_278]; void *
0x1800bcec7  mov     [rsp+2F8h+var_278], r12
0x1800bcecf  test    rcx, rcx
0x1800bced2  jz      short loc_1800BCEDA
0x1800bced4  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1800bced9  nop
0x1800bceda  lea     rcx, [rsp+2F8h+var_210]
0x1800bcee2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800bcee7  nop
0x1800bcee8  lea     rcx, [rsp+2F8h+var_268]
0x1800bcef0  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x1800bcef5  nop
0x1800bcef6  lea     rcx, [rsp+2F8h+Src]
0x1800bcefe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800bcf03  mov     eax, ebx
0x1800bcf05  jmp     loc_1800BDBC1
0x1800bcf0a  lea     rax, [rsp+2F8h+var_288]
0x1800bcf0f  mov     [rsp+2F8h+var_1B8], rax
0x1800bcf17  mov     [rsp+2F8h+var_1B0], r12
0x1800bcf1f  mov     r13d, 1
0x1800bcf25  mov     [rsp+2F8h+var_1A8], r13b
0x1800bcf2d  lea     rax, [rsp+2F8h+var_280]
0x1800bcf32  mov     qword ptr [rsp+2F8h+var_1D8], rax
0x1800bcf3a  mov     qword ptr [rsp+2F8h+var_1D8+8], r12
0x1800bcf42  mov     [rsp+2F8h+var_1C8], r13b
0x1800bcf4a  lea     rax, [rsp+2F8h+var_278]
0x1800bcf52  mov     qword ptr [rsp+2F8h+var_1F8], rax
0x1800bcf5a  mov     qword ptr [rsp+2F8h+var_1F8+8], r12
0x1800bcf62  mov     [rsp+2F8h+var_1E8], r13b
0x1800bcf6a  mov     [rsp+2F8h+var_2A8], r13d
0x1800bcf6f  lea     rax, [rsp+2F8h+var_258]
0x1800bcf77  mov     [rsp+2F8h+var_2B0], rax
0x1800bcf7c  lea     rax, [rsp+2F8h+var_1B0]
0x1800bcf84  mov     [rsp+2F8h+var_2B8], rax
0x1800bcf89  lea     rax, [rsp+2F8h+var_25C]
0x1800bcf91  mov     [rsp+2F8h+var_2C0], rax
0x1800bcf96  lea     rax, [rsp+2F8h+var_1D8+8]
0x1800bcf9e  mov     [rsp+2F8h+var_2C8], rax
0x1800bcfa3  mov     [rsp+2F8h+var_2D0], r12
0x1800bcfa8  mov     qword ptr [rsp+2F8h+var_2D8], r12; int
0x1800bcfad  lea     r9, [rsp+2F8h+var_260]
0x1800bcfb5  lea     r8, [rsp+2F8h+var_1F8+8]
0x1800bcfbd  mov     edx, r13d
0x1800bcfc0  mov     rcx, [rsp+2F8h+var_268]
0x1800bcfc8  call    cs:__imp_?DmGenerateAttestationClaimsOld@@YAJPEBU_CERT_CONTEXT@@HPEAPEAEPEAK121212H@Z; DmGenerateAttestationClaimsOld(_CERT_CONTEXT const *,int,uchar * *,ulong *,uchar * *,ulong *,uchar * *,ulong *,uchar * *,ulong *,int)
0x1800bcfcf  nop     dword ptr [rax+rax+00h]
0x1800bcfd4  mov     ebx, eax
0x1800bcfd6  lea     rcx, [rsp+2F8h+var_1F8]
0x1800bcfde  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x1800bcfe3  nop
0x1800bcfe4  lea     rcx, [rsp+2F8h+var_1D8]
0x1800bcfec  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x1800bcff1  nop
0x1800bcff2  lea     rcx, [rsp+2F8h+var_1B8]
0x1800bcffa  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x1800bcfff  test    ebx, ebx
0x1800bd001  jns     loc_1800BD0C3
0x1800bd007  mov     rcx, [rsp+2F8h]; this
0x1800bd00f  mov     r9d, ebx; char *
0x1800bd012  lea     r8, aOnecoreuapAdmi_102; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800bd019  mov     edx, 9Eh; void *
0x1800bd01e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd023  nop
0x1800bd024  mov     rcx, [rsp+2F8h+var_298]; void *
0x1800bd029  mov     [rsp+2F8h+var_298], r12
0x1800bd02e  test    rcx, rcx
0x1800bd031  jz      short loc_1800BD039
0x1800bd033  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1800bd038  nop
0x1800bd039  mov     rcx, [rsp+2F8h+var_290]; void *
0x1800bd03e  mov     [rsp+2F8h+var_290], r12
0x1800bd043  test    rcx, rcx
0x1800bd046  jz      short loc_1800BD04E
0x1800bd048  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1800bd04d  nop
0x1800bd04e  mov     rcx, [rsp+2F8h+var_288]; void *
0x1800bd053  mov     [rsp+2F8h+var_288], r12
0x1800bd058  test    rcx, rcx
0x1800bd05b  jz      short loc_1800BD063
0x1800bd05d  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1800bd062  nop
0x1800bd063  mov     rcx, [rsp+2F8h+var_280]; void *
0x1800bd068  mov     [rsp+2F8h+var_280], r12
0x1800bd06d  test    rcx, rcx
0x1800bd070  jz      short loc_1800BD078
0x1800bd072  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1800bd077  nop
0x1800bd078  mov     rcx, [rsp+2F8h+var_278]; void *
0x1800bd080  mov     [rsp+2F8h+var_278], r12
0x1800bd088  test    rcx, rcx
0x1800bd08b  jz      short loc_1800BD093
0x1800bd08d  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1800bd092  nop
0x1800bd093  lea     rcx, [rsp+2F8h+var_210]
0x1800bd09b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800bd0a0  nop
0x1800bd0a1  lea     rcx, [rsp+2F8h+var_268]
0x1800bd0a9  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x1800bd0ae  nop
0x1800bd0af  lea     rcx, [rsp+2F8h+Src]
0x1800bd0b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800bd0bc  mov     eax, ebx
0x1800bd0be  jmp     loc_1800BDBC1
0x1800bd0c3  mov     ecx, r12d
0x1800bd0c6  mov     [rsp+2F8h+var_248], r12
0x1800bd0ce  mov     [rsp+2F8h+var_208], r12
0x1800bd0d6  mov     rax, r12
0x1800bd0d9  mov     [rsp+2F8h+var_240], rax
0x1800bd0e1  movzx   ebx, r12b
0x1800bd0e5  mov     word ptr [rsp+2F8h+var_1F8], r12w
0x1800bd0ee  mov     byte ptr [rsp+2F8h+var_1F8+2], r12b
0x1800bd0f6  mov     qword ptr [rsp+2F8h+var_1F8+8], r12
0x1800bd0fe  test    edi, edi
0x1800bd100  jnz     loc_1800BD1B2
0x1800bd106  xor     edx, edx
0x1800bd108  lea     rcx, [rsp+2F8h+var_208]
0x1800bd110  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800bd115  lea     rcx, [rsp+2F8h+var_208]
0x1800bd11d  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1800bd124  nop     dword ptr [rax+rax+00h]
0x1800bd129  test    eax, eax
0x1800bd12b  js      short loc_1800BD142
0x1800bd12d  mov     rdx, [rsp+2F8h+var_208]; unsigned __int16 *
0x1800bd135  lea     rcx, [rsp+2F8h+var_1F8]; this
0x1800bd13d  call    ?ImpersonateSID@AutoImpersonate@@QEAAJPEBG@Z; AutoImpersonate::ImpersonateSID(ushort const *)
0x1800bd142  mov     rsi, [rsp+2F8h+var_240]
0x1800bd14a  test    rsi, rsi
0x1800bd14d  jz      short loc_1800BD171
0x1800bd14f  lea     rcx, [rsp+2F8h+var_1D8]; this
0x1800bd157  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800bd15c  mov     rcx, rsi; void *
0x1800bd15f  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1800bd164  lea     rcx, [rsp+2F8h+var_1D8]; this
0x1800bd16c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800bd171  mov     [rsp+2F8h+var_240], r12
0x1800bd179  movaps  xmm0, xmmword ptr [r14]
0x1800bd17d  movdqa  [rsp+2F8h+var_1D8], xmm0
0x1800bd186  lea     rdx, [rsp+2F8h+var_240]
0x1800bd18e  lea     rcx, [rsp+2F8h+var_1D8]
0x1800bd196  call    cs:__imp_GetEnrollmentTenantID
0x1800bd19d  nop     dword ptr [rax+rax+00h]
0x1800bd1a2  mov     ecx, eax
0x1800bd1a4  test    eax, eax
0x1800bd1a6  cmovns  ebx, r13d
0x1800bd1aa  mov     rax, [rsp+2F8h+var_240]
0x1800bd1b2  lea     rdx, [rsp+2F8h+var_248]
0x1800bd1ba  mov     qword ptr [rsp+2F8h+var_1D8], rdx
0x1800bd1c2  mov     byte ptr [rsp+2F8h+var_1D8+8], r13b
0x1800bd1ca  test    ecx, ecx
0x1800bd1cc  js      loc_1800BD2C8
0x1800bd1d2  neg     bl
0x1800bd1d4  sbb     rcx, rcx
0x1800bd1d7  and     rcx, rax
0x1800bd1da  lea     rdx, [rsp+2F8h+var_248]
0x1800bd1e2  call    cs:__imp_DsrGetJoinInfo
0x1800bd1e9  nop     dword ptr [rax+rax+00h]
0x1800bd1ee  test    eax, eax
0x1800bd1f0  js      loc_1800BD2C8
0x1800bd1f6  cmp     [rsp+2F8h+var_248], r12
0x1800bd1fe  jz      loc_1800BD2C8
0x1800bd204  test    edi, edi
0x1800bd206  jnz     short loc_1800BD215
0x1800bd208  lea     rcx, [rsp+2F8h+var_1F8]; this
0x1800bd210  call    ?RevertToSelf@AutoImpersonate@@QEAAJXZ; AutoImpersonate::RevertToSelf(void)
0x1800bd215  lea     rax, [rsp+2F8h+var_298]
0x1800bd21a  mov     [rsp+2F8h+var_100], rax
0x1800bd222  mov     [rsp+2F8h+var_F8], r12
0x1800bd22a  mov     [rsp+2F8h+var_F0], r13b
0x1800bd232  lea     rax, [rsp+2F8h+var_290]
0x1800bd237  mov     [rsp+2F8h+var_1B8], rax
0x1800bd23f  mov     [rsp+2F8h+var_1B0], r12
0x1800bd247  mov     [rsp+2F8h+var_1A8], r13b
0x1800bd24f  mov     [rsp+2F8h+var_2A8], r13d
0x1800bd254  mov     [rsp+2F8h+var_2B0], r12
0x1800bd259  mov     [rsp+2F8h+var_2B8], r12
0x1800bd25e  mov     [rsp+2F8h+var_2C0], r12
0x1800bd263  mov     [rsp+2F8h+var_2C8], r12
0x1800bd268  lea     rax, [rsp+2F8h+var_250]
0x1800bd270  mov     [rsp+2F8h+var_2D0], rax
0x1800bd275  lea     rax, [rsp+2F8h+var_F8]
0x1800bd27d  mov     qword ptr [rsp+2F8h+var_2D8], rax
0x1800bd282  lea     r9, [rsp+2F8h+var_254]
0x1800bd28a  lea     r8, [rsp+2F8h+var_1B0]
0x1800bd292  mov     edx, edi
0x1800bd294  mov     rcx, [rsp+2F8h+var_248]
0x1800bd29c  mov     rcx, [rcx+8]
0x1800bd2a0  call    cs:__imp_?DmGenerateAttestationClaimsOld@@YAJPEBU_CERT_CONTEXT@@HPEAPEAEPEAK121212H@Z; DmGenerateAttestationClaimsOld(_CERT_CONTEXT const *,int,uchar * *,ulong *,uchar * *,ulong *,uchar * *,ulong *,uchar * *,ulong *,int)
0x1800bd2a7  nop     dword ptr [rax+rax+00h]
0x1800bd2ac  nop
0x1800bd2ad  lea     rcx, [rsp+2F8h+var_1B8]
0x1800bd2b5  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x1800bd2ba  nop
0x1800bd2bb  lea     rcx, [rsp+2F8h+var_100]
0x1800bd2c3  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x1800bd2c8  test    edi, edi
0x1800bd2ca  jnz     short loc_1800BD2DA
0x1800bd2cc  lea     rcx, [rsp+2F8h+var_1F8]; this
0x1800bd2d4  call    ?RevertToSelf@AutoImpersonate@@QEAAJXZ; AutoImpersonate::RevertToSelf(void)
0x1800bd2d9  nop
0x1800bd2da  mov     rcx, [rsp+2F8h+var_248]
0x1800bd2e2  call    cs:__imp_DsrFreeJoinInfo
0x1800bd2e9  nop     dword ptr [rax+rax+00h]
0x1800bd2ee  nop
0x1800bd2ef  lea     rcx, [rsp+2F8h+var_1F8]; this
0x1800bd2f7  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x1800bd2fc  nop
0x1800bd2fd  lea     rcx, [rsp+2F8h+var_240]
0x1800bd305  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800bd30a  nop
0x1800bd30b  lea     rcx, [rsp+2F8h+var_208]
0x1800bd313  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800bd318  lea     rax, [rsp+2F8h+var_110]
0x1800bd320  mov     [rsp+2F8h+var_120], rax
0x1800bd328  lea     rax, [rsp+2F8h+var_110]
0x1800bd330  mov     [rsp+2F8h+var_118], rax
0x1800bd338  mov     [rsp+2F8h+var_110], r12w
0x1800bd341  lea     rax, [rsp+2F8h+var_130]
0x1800bd349  mov     [rsp+2F8h+var_140], rax
0x1800bd351  lea     rax, [rsp+2F8h+var_130]
  ... truncated ...
```
