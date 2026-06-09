# LPA::EnterpriseManager::SetDownloadServerInstallResult(long,LPA_ERROR_DETAILS const *,ulong,LPA::LPAESIMINSLOTINTERNAL)

- ea: `0x18007da00`
- end: `0x18007e4f2`
- name: `?SetDownloadServerInstallResult@EnterpriseManager@LPA@@UEAAXJPEBULPA_ERROR_DETAILS@@KW4LPAESIMINSLOTINTERNAL@2@@Z`
- size: `2802`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800018b4`
- `0x180001f1c`
- `0x180002290`
- `0x1800023b4`
- `0x1800024e8`
- `0x18000262c`
- `0x1800031fc`
- `0x1800034e0`
- `0x18000df90`
- `0x18000ebf4`
- `0x180071344`
- `0x180071650`
- `0x180071840`
- `0x1800754a0`
- `0x180075974`
- `0x180076d0c`
- `0x180076fbc`
- `0x18007793c`
- `0x18007cc64`
- `0x18007da00`
- `0x18007e4f8`
- `0x180080484`
- `0x180080a28`
- `0x180080dfc`
- `0x180080fd8`
- `0x180101010`

## string_xrefs

- `0x18007dabd`: `LpaServiceEnterpriseManager`
- `0x18007db85`: `LpaServiceEnterpriseManager`
- `0x18007dd90`: `LpaServiceEnterpriseManager`
- `0x18007dac4`: `LPA::EnterpriseManager::SetDownloadServerInstallResult`
- `0x18007db7e`: `LPA::EnterpriseManager::SetDownloadServerInstallResult`
- `0x18007dd89`: `LPA::EnterpriseManager::SetDownloadServerInstallResult`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LPA::EnterpriseManager::SetDownloadServerInstallResult(
        LPA::EnterpriseManager **a1,
        int a2,
        const char *a3,
        unsigned int a4,
        int a5)
{
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  LPA::EnterpriseManager *v11; // rbx
  __int16 *v12; // rdx
  __int64 v13; // rsi
  _DWORD *v14; // rax
  unsigned int v15; // edi
  char IsEnabled; // al
  unsigned int v17; // ecx
  unsigned int v18; // r14d
  unsigned int v19; // edi
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  __int64 v23; // rdi
  struct _SECURITY_ATTRIBUTES *v24; // rax
  __int64 v25; // rax
  __int64 v26; // rdx
  unsigned int v27; // r13d
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  char v31; // r15
  unsigned int v32; // ecx
  int v33; // edx
  struct _SECURITY_ATTRIBUTES *v34; // rdi
  struct _SECURITY_ATTRIBUTES *v35; // r8
  __int64 v36; // rdi
  struct _SECURITY_ATTRIBUTES *v37; // rax
  unsigned __int16 *v38; // rdi
  __int64 v39; // rax
  unsigned int v40; // r13d
  int v41; // ecx
  int v42; // r8d
  int v43; // r9d
  const char *v44; // r13
  __int64 v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rdi
  struct _SECURITY_ATTRIBUTES *v48; // rax
  __int64 v49; // rax
  unsigned int v50; // r13d
  int v51; // ecx
  int v52; // r8d
  int v53; // r9d
  struct _SECURITY_ATTRIBUTES *v54; // rdi
  struct _SECURITY_ATTRIBUTES *v55; // r8
  __int64 v56; // rax
  __int64 v57; // rdx
  int v58; // ecx
  int v59; // r8d
  int v60; // r9d
  int v61; // ecx
  int v62; // r8d
  int v63; // r9d
  __int64 v64; // rax
  __int64 v65; // rcx
  unsigned __int16 (*v66)[33]; // r8
  int v67; // ecx
  int v68; // ecx
  int v69; // r8d
  int v70; // r9d
  struct _SECURITY_ATTRIBUTES *v72; // [rsp+60h] [rbp-C0h]
  struct _SECURITY_ATTRIBUTES *v73; // [rsp+60h] [rbp-C0h]
  struct _SECURITY_ATTRIBUTES *v74; // [rsp+60h] [rbp-C0h]
  unsigned __int8 v75; // [rsp+A0h] [rbp-80h]
  int v76; // [rsp+A8h] [rbp-78h] BYREF
  char v77; // [rsp+B0h] [rbp-70h]
  unsigned int v78; // [rsp+B4h] [rbp-6Ch] BYREF
  unsigned int v79; // [rsp+B8h] [rbp-68h] BYREF
  int v80; // [rsp+BCh] [rbp-64h] BYREF
  int v81; // [rsp+C0h] [rbp-60h] BYREF
  unsigned __int16 (*v82)[33]; // [rsp+C8h] [rbp-58h] BYREF
  unsigned int v83; // [rsp+D0h] [rbp-50h] BYREF
  __int64 v84; // [rsp+D8h] [rbp-48h] BYREF
  LPA::EnterpriseManager *v85; // [rsp+E0h] [rbp-40h] BYREF
  const unsigned __int16 *v86; // [rsp+E8h] [rbp-38h] BYREF
  unsigned __int16 *v87; // [rsp+F0h] [rbp-30h] BYREF
  const char *v88; // [rsp+F8h] [rbp-28h] BYREF
  _QWORD v89[2]; // [rsp+100h] [rbp-20h] BYREF
  __int64 v90; // [rsp+110h] [rbp-10h] BYREF
  const char *v91; // [rsp+118h] [rbp-8h] BYREF
  const char *v92; // [rsp+120h] [rbp+0h] BYREF
  LPA::EnterpriseManager **v93; // [rsp+128h] [rbp+8h]
  _OWORD v94[2]; // [rsp+130h] [rbp+10h] BYREF
  unsigned __int16 v95[33]; // [rsp+150h] [rbp+30h] BYREF

  v83 = a4;
  v91 = a3;
  v80 = a2;
  v76 = a4;
  v94[0] = 0;
  v94[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v94[0]) = 0;
  v93 = a1 + 14;
  std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<LPA::Lpd::DownloadInstance>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<LPA::Lpd::DownloadInstance>>>,0>>::find(
    a1 + 14,
    &v85,
    &v76);
  v11 = v85;
  if ( a1[14] != v85 )
  {
    v13 = *((_QWORD *)v85 + 5);
    v82 = (unsigned __int16 (*)[33])v13;
    if ( !v13 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_66;
      v12 = (__int16 *)&unk_18012C5E0;
      goto LABEL_4;
    }
    v75 = *(_BYTE *)(v13 + 176);
    std::wstring::operator=(v94, v13 + 112);
    v14 = (_DWORD *)*((_QWORD *)v11 + 5);
    LODWORD(v87) = v14[54];
    LODWORD(v86) = v14[56];
    v15 = v14[57];
    v78 = v15;
    if ( a2 >= 0 )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::GetImpl'::`2'::impl);
      v17 = v15 + 1;
      if ( !IsEnabled )
        v17 = v15;
      LODWORD(v84) = v17;
      memset(v95, 0, 42);
      v18 = 2;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::GetImpl'::`2'::impl) )
      {
        v19 = v83;
        if ( (*((int (__fastcall **)(LPA::EnterpriseManager **, unsigned __int16 *, _QWORD))*a1 + 21))(a1, v95, v83) < 0
          && (unsigned int)CallbackContext > 2 )
        {
          v76 = v19;
          v85 = (LPA::EnterpriseManager *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v94);
          v78 = 2;
          v88 = "LPA::EnterpriseManager::SetDownloadServerInstallResult";
          v82 = (unsigned __int16 (*)[33])"LpaServiceEnterpriseManager";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v20,
            (unsigned int)&unk_18012C578,
            v21,
            v22,
            (__int64)&v82,
            (__int64)&v88,
            (__int64)&v78,
            (__int64)&v85,
            (__int64)&v76);
        }
      }
      v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*((_QWORD *)v11 + 5) + 184LL);
      v24 = (struct _SECURITY_ATTRIBUTES *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v94);
      v72 = (struct _SECURITY_ATTRIBUTES *)v23;
      v15 = v84;
      LPA::EnterpriseManager::SetDownloadServerToRegistry(
        (LPA::EnterpriseManager *)(a1 - 1),
        (CommonUtil *)v13,
        v24,
        v75,
        0,
        0,
        3u,
        (unsigned int)v87,
        (unsigned int)v86,
        v84,
        v95,
        0,
        v72);
      v25 = std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>::_Try_emplace<std::wstring const &,>(
              a1 + 21,
              v89,
              v94);
      v26 = *(_QWORD *)(*(_QWORD *)v25 + 64LL);
      *(_QWORD *)(*(_QWORD *)v25 + 64LL) = 0;
      if ( v26 )
        std::default_delete<LPA::EnterpriseManager::StagedProfileDetails>::operator()();
      std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>>,0>>::erase(
        a1 + 21,
        v94);
      if ( (unsigned int)CallbackContext <= 4 )
      {
        v27 = v80;
      }
      else
      {
        v76 = v15;
        v78 = (unsigned int)v86;
        v79 = (unsigned int)v87;
        LODWORD(v87) = 3;
        LODWORD(v86) = v75;
        v85 = (LPA::EnterpriseManager *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v94);
        v27 = v80;
        v88 = "LPA::EnterpriseManager::SetDownloadServerInstallResult";
        v82 = (unsigned __int16 (*)[33])"LpaServiceEnterpriseManager";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v28,
          (unsigned int)&unk_18012C3D8,
          v29,
          v30,
          (__int64)&v82,
          (__int64)&v88,
          (__int64)&v80,
          (__int64)&v85,
          (__int64)&v86,
          (__int64)&v87,
          (__int64)&v79,
          (__int64)&v78,
          (__int64)&v76);
      }
      v31 = 1;
      goto LABEL_54;
    }
    v77 = 0;
    LODWORD(v84) = v15;
    v85 = (LPA::EnterpriseManager *)(a1 - 1);
    if ( !*((_BYTE *)a1 + 128) )
    {
      v79 = 3;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>::_Try_emplace<std::wstring const &,>(
                                          a1 + 21,
                                          v89,
                                          v94)
                           + 64LL)
               + 196LL) = 0;
LABEL_50:
      if ( (unsigned int)CallbackContext <= 2 )
      {
        v27 = v80;
      }
      else
      {
        LODWORD(v82) = v15;
        v81 = (int)v86;
        v76 = (int)v87;
        v78 = v79;
        v79 = v75;
        v89[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v94);
        v27 = v80;
        v90 = (__int64)"LPA::EnterpriseManager::SetDownloadServerInstallResult";
        v92 = "LpaServiceEnterpriseManager";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v58,
          (unsigned int)&word_18012C336,
          v59,
          v60,
          (__int64)&v92,
          (__int64)&v90,
          (__int64)&v80,
          (__int64)v89,
          (__int64)&v79,
          (__int64)&v78,
          (__int64)&v76,
          (__int64)&v81,
          (__int64)&v82);
      }
      v18 = 4;
      v31 = v77;
LABEL_54:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::GetImpl'::`2'::impl)
        && (unsigned int)dword_18015A5E0 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18015A5E0, 0x800000000000LL) )
      {
        LODWORD(v82) = v15;
        v89[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v94);
        v81 = v27;
        v90 = 16779264;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v61,
          (unsigned int)byte_18012C2D1,
          v62,
          v63,
          (__int64)&v90,
          (__int64)&v81,
          (__int64)v89,
          (__int64)&v82);
      }
      if ( v31 )
      {
        v64 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*((_QWORD *)v11 + 5) + 184LL);
        LPA::EnterpriseManager::NotifyMdmServer(v65, v64, v18);
        v95[0] = 0;
        memset_0(&v95[1], 0, 0x40u);
        CommonUtil::WritePiiFilteredEsimIdToBuffer(*((CommonUtil **)v11 + 5), (const unsigned __int16 (*)[33])v95, v66);
        if ( (unsigned int)dword_18015A5E0 > 5 )
        {
          if ( (unsigned __int8)tlgKeywordOn(&dword_18015A5E0, 0x800000000000LL) )
          {
            v89[0] = &qword_1801130E8;
            v90 = (__int64)&qword_1801130E8;
            LODWORD(v82) = a5;
            v92 = (const char *)&qword_1801130E8;
            v85 = (LPA::EnterpriseManager *)&qword_1801130E8;
            v88 = (const char *)&qword_1801130E8;
            if ( v91 && (*v91 & 1) != 0 )
              v67 = *((_DWORD *)v91 + 1);
            else
              v67 = 0;
            v81 = v67;
            v76 = 1;
            v91 = (const char *)&qword_1801130E8;
            v87 = v95;
            v86 = &qword_1801130E8;
            v80 = 25;
            v78 = v27;
            v79 = 1;
            v84 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*((_QWORD *)v11 + 5) + 112LL);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              v68,
              (unsigned int)&byte_18012C1EF,
              v69,
              v70,
              (__int64)&v84,
              (__int64)&v79,
              (__int64)&v78,
              (__int64)&v83,
              (__int64)&v80,
              (__int64)&v86,
              (__int64)&v87,
              (__int64)&v91,
              (__int64)&v76,
              (__int64)&v81,
              (__int64)&v88,
              (__int64)&v85,
              (__int64)&v92,
              (__int64)&v82,
              (__int64)&v90,
              (__int64)v89);
          }
        }
      }
      goto LABEL_66;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::GetImpl'::`2'::impl) )
    {
      if ( v91 && (*v91 & 1) != 0 && ((v32 = *((_DWORD *)v91 + 1), v32 > 0x13) || (v33 = 545793, !_bittest(&v33, v32)))
        || (_DWORD)v86 && v15 >= (unsigned int)v86 )
      {
        v76 = 0;
        v79 = 4;
        if ( (*v91 & 1) != 0 )
          v76 = *((_DWORD *)v91 + 1);
        v34 = (struct _SECURITY_ATTRIBUTES *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*((_QWORD *)v11 + 5) + 184LL);
        v35 = (struct _SECURITY_ATTRIBUTES *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v94);
        LPA::EnterpriseManager::SetDownloadServerToRegistry(
          (LPA::EnterpriseManager *)(a1 - 1),
          (CommonUtil *)v82,
          v35,
          v75,
          0,
          0,
          4u,
          0,
          (unsigned int)v86,
          v78,
          0,
          v76,
          v34);
        goto LABEL_46;
      }
      LODWORD(v84) = v15 + 1;
      v79 = 2;
      v36 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*((_QWORD *)v11 + 5) + 184LL);
      v37 = (struct _SECURITY_ATTRIBUTES *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v94);
      v73 = (struct _SECURITY_ATTRIBUTES *)v36;
      v38 = (unsigned __int16 *)v82;
      LPA::EnterpriseManager::SetDownloadServerToRegistry(
        (LPA::EnterpriseManager *)(a1 - 1),
        (CommonUtil *)v82,
        v37,
        v75,
        0,
        0,
        2u,
        (unsigned int)v87,
        (unsigned int)v86,
        v84,
        0,
        0,
        v73);
      *(_DWORD *)(*((_QWORD *)v11 + 5) + 228LL) = v84;
      v88 = (const char *)(a1 + 21);
      v39 = std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>::_Try_emplace<std::wstring const &,>(
              a1 + 21,
              v89,
              v94);
      v40 = v84;
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v39 + 64LL) + 212LL) = v84;
      if ( (unsigned int)CallbackContext > 4 )
      {
        v76 = (int)v86;
        v78 = v40;
        v81 = 2;
        v92 = (const char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v94);
        LODWORD(v82) = v75;
        v90 = (__int64)"LPA::EnterpriseManager::SetDownloadServerInstallResult";
        v89[0] = "LpaServiceEnterpriseManager";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v41,
          (unsigned int)&byte_18012C4EF,
          v42,
          v43,
          (__int64)v89,
          (__int64)&v90,
          (__int64)&v82,
          (__int64)&v92,
          (__int64)&v81,
          (__int64)&v78,
          (__int64)&v76);
      }
      if ( v40 >= 3 )
      {
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>::_Try_emplace<std::wstring const &,>(
                                            v88,
                                            v89,
                                            v94)
                             + 64LL)
                 + 196LL) = 0;
        v15 = v40;
        goto LABEL_50;
      }
      v44 = v88;
    }
    else
    {
      v46 = *((_QWORD *)v11 + 5) + 184LL;
      if ( (unsigned int)v87 <= 1 )
      {
        v79 = 4;
        v54 = (struct _SECURITY_ATTRIBUTES *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46);
        v55 = (struct _SECURITY_ATTRIBUTES *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v94);
        LPA::EnterpriseManager::SetDownloadServerToRegistry(
          (LPA::EnterpriseManager *)(a1 - 1),
          (CommonUtil *)v82,
          v55,
          v75,
          0,
          0,
          4u,
          0,
          (unsigned int)v86,
          v78,
          0,
          0,
          v54);
LABEL_46:
        v56 = std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>::_Try_emplace<std::wstring const &,>(
                a1 + 21,
                v89,
                v94);
        v57 = *(_QWORD *)(*(_QWORD *)v56 + 64LL);
        *(_QWORD *)(*(_QWORD *)v56 + 64LL) = 0;
        if ( v57 )
          std::default_delete<LPA::EnterpriseManager::StagedProfileDetails>::operator()();
        std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>>,0>>::erase(
          a1 + 21,
          v94);
        v77 = 1;
LABEL_49:
        v15 = v84;
        goto LABEL_50;
      }
      v76 = (_DWORD)v87 - 1;
      LODWORD(v87) = (_DWORD)v87 - 1;
      v79 = 2;
      v47 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46);
      v48 = (struct _SECURITY_ATTRIBUTES *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v94);
      v74 = (struct _SECURITY_ATTRIBUTES *)v47;
      v38 = (unsigned __int16 *)v82;
      LPA::EnterpriseManager::SetDownloadServerToRegistry(
        (LPA::EnterpriseManager *)(a1 - 1),
        (CommonUtil *)v82,
        v48,
        v75,
        0,
        0,
        2u,
        v76,
        (unsigned int)v86,
        v78,
        0,
        0,
        v74);
      *(_DWORD *)(*((_QWORD *)v11 + 5) + 216LL) = v76;
      v88 = (const char *)(a1 + 21);
      v49 = std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>::_Try_emplace<std::wstring const &,>(
              a1 + 21,
              v89,
              v94);
      v50 = v76;
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v49 + 64LL) + 192LL) = v76;
      if ( (unsigned int)CallbackContext > 4 )
      {
        LODWORD(v82) = v50;
        v81 = 2;
        v89[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v94);
        v76 = v75;
        v90 = (__int64)"LPA::EnterpriseManager::SetDownloadServerInstallResult";
        v92 = "LpaServiceEnterpriseManager";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v51,
          (unsigned int)word_18012C47A,
          v52,
          v53,
          (__int64)&v92,
          (__int64)&v90,
          (__int64)&v76,
          (__int64)v89,
          (__int64)&v81,
          (__int64)&v82);
      }
      if ( v50 != 2 )
        goto LABEL_49;
      v44 = v88;
    }
    v45 = std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>::_Try_emplace<std::wstring const &,>(
            v44,
            v89,
            v94);
    if ( (int)LPA::EnterpriseManager::StagedProfileDetails::StartTimer(*(struct _TP_TIMER ***)(*(_QWORD *)v45 + 64LL)) >= 0 )
    {
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>::_Try_emplace<std::wstring const &,>(
                                          v44,
                                          v89,
                                          v94)
                           + 64LL)
               + 197LL) = 1;
      LPA::EnterpriseManager::CalculateNumberOfEnterpriseTasks(v85, (const unsigned __int16 (*)[33])v38);
    }
    goto LABEL_49;
  }
  if ( (unsigned int)CallbackContext > 3 )
  {
    v12 = word_18012C63A;
LABEL_4:
    v76 = a2;
    v85 = (LPA::EnterpriseManager *)"LpaServiceEnterpriseManager";
    v91 = "LPA::EnterpriseManager::SetDownloadServerInstallResult";
    v83 = a4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v8,
      (_DWORD)v12,
      v9,
      v10,
      (__int64)&v85,
      (__int64)&v91,
      (__int64)&v76,
      (__int64)&v83);
  }
LABEL_66:
  std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<LPA::EnterpriseManager::OperationEntry>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<LPA::EnterpriseManager::OperationEntry>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::unique_ptr<LPA::EnterpriseManager::OperationEntry>>>>>,0>(
    v93,
    v89,
    v11);
  return std::wstring::_Tidy_deallocate(v94);
}

```

## disassembly

```asm
0x18007da00  mov     [rsp-8+arg_8], rbx
0x18007da05  push    rbp
0x18007da06  push    rsi
0x18007da07  push    rdi
0x18007da08  push    r12
0x18007da0a  push    r13
0x18007da0c  push    r14
0x18007da0e  push    r15
0x18007da10  lea     rbp, [rsp-90h]
0x18007da18  sub     rsp, 1B0h
0x18007da1f  mov     rax, cs:__security_cookie
0x18007da26  xor     rax, rsp
0x18007da29  mov     [rbp+0C0h+var_40], rax
0x18007da30  mov     edi, r9d
0x18007da33  mov     [rbp+0C0h+var_110], r9d
0x18007da37  mov     [rbp+0C0h+var_C8], r8
0x18007da3b  mov     r15d, edx
0x18007da3e  mov     [rbp+0C0h+var_124], edx
0x18007da41  mov     r13, rcx
0x18007da44  mov     [rbp+0C0h+var_138], r9d
0x18007da48  xorps   xmm0, xmm0
0x18007da4b  movups  [rbp+0C0h+var_B0], xmm0
0x18007da4f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18007da57  movdqu  [rbp+0C0h+var_A0], xmm1
0x18007da5c  xor     eax, eax
0x18007da5e  mov     word ptr [rbp+0C0h+var_B0], ax
0x18007da62  lea     rax, [rcx+70h]
0x18007da66  mov     [rbp+0C0h+var_B8], rax
0x18007da6a  lea     r8, [rbp+0C0h+var_138]
0x18007da6e  lea     rdx, [rbp+0C0h+var_100]
0x18007da72  mov     rcx, rax
0x18007da75  call    ?find@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<LPA::Lpd::DownloadInstance>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<LPA::Lpd::DownloadInstance>>>,0>>::find(ulong const &)
0x18007da7a  mov     rbx, [rbp+0C0h+var_100]
0x18007da7e  cmp     [r13+70h], rbx
0x18007da82  jnz     short loc_18007DAE5
0x18007da84  mov     eax, cs:CallbackContext
0x18007da8a  cmp     eax, 3
0x18007da8d  jbe     loc_18007E4AE
0x18007da93  lea     rdx, word_18012C63A
0x18007da9a  lea     rax, [rbp+0C0h+var_110]
0x18007da9e  mov     [rsp+1E0h+var_1A8], rax
0x18007daa3  lea     rax, [rbp+0C0h+var_138]
0x18007daa7  mov     [rsp+1E0h+var_1B0], rax
0x18007daac  lea     rax, [rbp+0C0h+var_C8]
0x18007dab0  mov     [rsp+1E0h+var_1B8], rax
0x18007dab5  mov     [rbp+0C0h+var_138], r15d
0x18007dab9  lea     rax, [rbp+0C0h+var_100]
0x18007dabd  lea     r12, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007dac4  lea     r15, aLpaEnterprisem_16; "LPA::EnterpriseManager::SetDownloadServ"...
0x18007dacb  mov     [rsp+1E0h+var_1C0], rax
0x18007dad0  mov     [rbp+0C0h+var_100], r12
0x18007dad4  mov     [rbp+0C0h+var_C8], r15
0x18007dad8  mov     [rbp+0C0h+var_110], edi
0x18007dadb  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007dae0  jmp     loc_18007E4AE
0x18007dae5  mov     rsi, [rbx+28h]
0x18007dae9  mov     [rbp+0C0h+var_118], rsi
0x18007daed  test    rsi, rsi
0x18007daf0  jnz     short loc_18007DB0E
0x18007daf2  mov     eax, cs:CallbackContext
0x18007daf8  lea     r14d, [rsi+2]
0x18007dafc  cmp     eax, r14d
0x18007daff  jbe     loc_18007E4AE
0x18007db05  lea     rdx, unk_18012C5E0
0x18007db0c  jmp     short loc_18007DA9A
0x18007db0e  mov     al, [rsi+0B0h]
0x18007db14  mov     [rbp+0C0h+var_140], al
0x18007db17  lea     rdx, [rsi+70h]
0x18007db1b  lea     rcx, [rbp+0C0h+var_B0]
0x18007db1f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18007db24  mov     rax, [rbx+28h]
0x18007db28  mov     ecx, [rax+0D8h]
0x18007db2e  mov     dword ptr [rbp+0C0h+var_F0], ecx
0x18007db31  mov     ecx, [rax+0E0h]
0x18007db37  mov     dword ptr [rbp+0C0h+var_F8], ecx
0x18007db3a  mov     edi, [rax+0E4h]
0x18007db40  mov     [rbp+0C0h+var_12C], edi
0x18007db43  test    r15d, r15d
0x18007db46  js      loc_18007DD79
0x18007db4c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY> `wil::Feature<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::GetImpl(void)'::`2'::impl
0x18007db53  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::__private_IsEnabled(void)
0x18007db58  lea     ecx, [rdi+1]
0x18007db5b  test    al, al
0x18007db5d  cmovz   ecx, edi
0x18007db60  mov     dword ptr [rbp+0C0h+var_108], ecx
0x18007db63  xorps   xmm0, xmm0
0x18007db66  movups  xmmword ptr [rbp+0C0h+var_90], xmm0
0x18007db6a  movups  xmmword ptr [rbp+0C0h+var_90+10h], xmm0
0x18007db6e  movups  xmmword ptr [rbp+0C0h+var_90+1Ah], xmm0
0x18007db72  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY> `wil::Feature<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::GetImpl(void)'::`2'::impl
0x18007db79  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::__private_IsEnabled(void)
0x18007db7e  lea     r15, aLpaEnterprisem_16; "LPA::EnterpriseManager::SetDownloadServ"...
0x18007db85  lea     r12, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007db8c  mov     r14d, 2
0x18007db92  test    al, al
0x18007db94  jz      loc_18007DC1B
0x18007db9a  mov     rax, [r13+0]
0x18007db9e  mov     edi, [rbp+0C0h+var_110]
0x18007dba1  mov     r8d, edi
0x18007dba4  lea     rdx, [rbp+0C0h+var_90]
0x18007dba8  mov     rcx, r13
0x18007dbab  mov     rax, [rax+0A8h]
0x18007dbb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dbb7  test    eax, eax
0x18007dbb9  jns     short loc_18007DC1B
0x18007dbbb  mov     eax, cs:CallbackContext
0x18007dbc1  cmp     eax, r14d
0x18007dbc4  jbe     short loc_18007DC1B
0x18007dbc6  mov     [rbp+0C0h+var_138], edi
0x18007dbc9  lea     rcx, [rbp+0C0h+var_B0]
0x18007dbcd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007dbd2  mov     [rbp+0C0h+var_100], rax
0x18007dbd6  mov     [rbp+0C0h+var_12C], r14d
0x18007dbda  mov     [rbp+0C0h+var_E8], r15
0x18007dbde  mov     [rbp+0C0h+var_118], r12
0x18007dbe2  lea     rax, [rbp+0C0h+var_138]
0x18007dbe6  mov     [rsp+1E0h+var_1A0], rax
0x18007dbeb  lea     rax, [rbp+0C0h+var_100]
0x18007dbef  mov     [rsp+1E0h+var_1A8], rax
0x18007dbf4  lea     rax, [rbp+0C0h+var_12C]
0x18007dbf8  mov     [rsp+1E0h+var_1B0], rax
0x18007dbfd  lea     rax, [rbp+0C0h+var_E8]
0x18007dc01  mov     [rsp+1E0h+var_1B8], rax
0x18007dc06  lea     rax, [rbp+0C0h+var_118]
0x18007dc0a  mov     [rsp+1E0h+var_1C0], rax
0x18007dc0f  lea     rdx, unk_18012C578
0x18007dc16  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18007dc1b  mov     rcx, [rbx+28h]
0x18007dc1f  add     rcx, 0B8h
0x18007dc26  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007dc2b  mov     rdi, rax
0x18007dc2e  lea     rcx, [rbp+0C0h+var_B0]
0x18007dc32  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007dc37  mov     r8, rax
0x18007dc3a  lea     rcx, [r13-8]
0x18007dc3e  mov     [rsp+1E0h+var_180], rdi
0x18007dc43  xor     edx, edx
0x18007dc45  mov     dword ptr [rsp+1E0h+var_188], edx
0x18007dc49  lea     rax, [rbp+0C0h+var_90]
0x18007dc4d  mov     [rsp+1E0h+var_190], rax
0x18007dc52  mov     edi, dword ptr [rbp+0C0h+var_108]
0x18007dc55  mov     dword ptr [rsp+1E0h+var_198], edi
0x18007dc59  mov     eax, dword ptr [rbp+0C0h+var_F8]
0x18007dc5c  mov     dword ptr [rsp+1E0h+var_1A0], eax
0x18007dc60  mov     eax, dword ptr [rbp+0C0h+var_F0]
0x18007dc63  mov     dword ptr [rsp+1E0h+var_1A8], eax
0x18007dc67  mov     dword ptr [rsp+1E0h+var_1B0], 3
0x18007dc6f  mov     byte ptr [rsp+1E0h+var_1B8], dl
0x18007dc73  mov     byte ptr [rsp+1E0h+var_1C0], dl
0x18007dc77  mov     r9b, [rbp+0C0h+var_140]
0x18007dc7b  mov     rdx, rsi
0x18007dc7e  call    ?SetDownloadServerToRegistry@EnterpriseManager@LPA@@AEAAJAEAY0CB@$$CBGPEBG_N22W4LPAENTERPRISEDISCOVERYSTATE@@KKKQEAGW4LPAERROR@@1@Z; LPA::EnterpriseManager::SetDownloadServerToRegistry(ushort const (&)[33],ushort const *,bool,bool,bool,LPAENTERPRISEDISCOVERYSTATE,ulong,ulong,ulong,ushort * const,LPAERROR,ushort const *)
0x18007dc83  lea     r8, [rbp+0C0h+var_B0]
0x18007dc87  lea     rdx, [rbp+0C0h+var_E0]
0x18007dc8b  lea     rcx, [r13+0A8h]
0x18007dc92  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18007dc97  mov     r8, [rax]
0x18007dc9a  mov     rdx, [r8+40h]
0x18007dc9e  mov     qword ptr [r8+40h], 0
0x18007dca6  test    rdx, rdx
0x18007dca9  jz      short loc_18007DCB0
0x18007dcab  call    ??R?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@QEBAXPEAVStagedProfileDetails@EnterpriseManager@LPA@@@Z; std::default_delete<LPA::EnterpriseManager::StagedProfileDetails>::operator()(LPA::EnterpriseManager::StagedProfileDetails *)
0x18007dcb0  lea     rdx, [rbp+0C0h+var_B0]
0x18007dcb4  lea     rcx, [r13+0A8h]
0x18007dcbb  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>>,0>>::erase(std::wstring const &)
0x18007dcc0  mov     eax, cs:CallbackContext
0x18007dcc6  cmp     eax, 4
0x18007dcc9  jbe     loc_18007DD68
0x18007dccf  mov     [rbp+0C0h+var_138], edi
0x18007dcd2  mov     eax, dword ptr [rbp+0C0h+var_F8]
0x18007dcd5  mov     [rbp+0C0h+var_12C], eax
0x18007dcd8  mov     eax, dword ptr [rbp+0C0h+var_F0]
0x18007dcdb  mov     [rbp+0C0h+var_128], eax
0x18007dcde  mov     dword ptr [rbp+0C0h+var_F0], 3
0x18007dce5  movzx   eax, [rbp+0C0h+var_140]
0x18007dce9  mov     dword ptr [rbp+0C0h+var_F8], eax
0x18007dcec  lea     rcx, [rbp+0C0h+var_B0]
0x18007dcf0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007dcf5  mov     [rbp+0C0h+var_100], rax
0x18007dcf9  mov     r13d, [rbp+0C0h+var_124]
0x18007dcfd  mov     [rbp+0C0h+var_124], r13d
0x18007dd01  mov     [rbp+0C0h+var_E8], r15
0x18007dd05  mov     [rbp+0C0h+var_118], r12
0x18007dd09  lea     rax, [rbp+0C0h+var_138]
0x18007dd0d  mov     [rsp+1E0h+var_180], rax
0x18007dd12  lea     rax, [rbp+0C0h+var_12C]
0x18007dd16  mov     [rsp+1E0h+var_188], rax
0x18007dd1b  lea     rax, [rbp+0C0h+var_128]
0x18007dd1f  mov     [rsp+1E0h+var_190], rax
0x18007dd24  lea     rax, [rbp+0C0h+var_F0]
0x18007dd28  mov     [rsp+1E0h+var_198], rax
0x18007dd2d  lea     rax, [rbp+0C0h+var_F8]
0x18007dd31  mov     [rsp+1E0h+var_1A0], rax
0x18007dd36  lea     rax, [rbp+0C0h+var_100]
0x18007dd3a  mov     [rsp+1E0h+var_1A8], rax
0x18007dd3f  lea     rax, [rbp+0C0h+var_124]
0x18007dd43  mov     [rsp+1E0h+var_1B0], rax
0x18007dd48  lea     rax, [rbp+0C0h+var_E8]
0x18007dd4c  mov     [rsp+1E0h+var_1B8], rax
0x18007dd51  lea     rax, [rbp+0C0h+var_118]
0x18007dd55  mov     [rsp+1E0h+var_1C0], rax
0x18007dd5a  lea     rdx, unk_18012C3D8
0x18007dd61  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@44444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007dd66  jmp     short loc_18007DD6C
0x18007dd68  mov     r13d, [rbp+0C0h+var_124]
0x18007dd6c  mov     esi, 1
0x18007dd71  mov     r15b, sil
0x18007dd74  jmp     loc_18007E29E
0x18007dd79  xor     al, al
0x18007dd7b  mov     [rbp+0C0h+var_130], al
0x18007dd7e  mov     dword ptr [rbp+0C0h+var_108], edi
0x18007dd81  lea     rax, [r13-8]
0x18007dd85  mov     [rbp+0C0h+var_100], rax
0x18007dd89  lea     r15, aLpaEnterprisem_16; "LPA::EnterpriseManager::SetDownloadServ"...
0x18007dd90  lea     r12, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007dd97  mov     esi, 1
0x18007dd9c  lea     r14d, [rsi+1]
0x18007dda0  cmp     byte ptr [rax+88h], 0
0x18007dda7  jnz     short loc_18007DDD7
0x18007dda9  mov     [rbp+0C0h+var_128], 3
0x18007ddb0  lea     rcx, [r13+0A8h]
0x18007ddb7  lea     r8, [rbp+0C0h+var_B0]
0x18007ddbb  lea     rdx, [rbp+0C0h+var_E0]
0x18007ddbf  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VStagedProfileDetails@EnterpriseManager@LPA@@U?$default_delete@VStagedProfileDetails@EnterpriseManager@LPA@@@std@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedProfileDetails>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18007ddc4  mov     rcx, [rax]
0x18007ddc7  mov     rax, [rcx+40h]
0x18007ddcb  mov     byte ptr [rax+0C4h], 0
0x18007ddd2  jmp     loc_18007E1E9
0x18007ddd7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY> `wil::Feature<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::GetImpl(void)'::`2'::impl
0x18007ddde  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::__private_IsEnabled(void)
0x18007dde3  test    al, al
0x18007dde5  jz      loc_18007E005
0x18007ddeb  mov     rax, [rbp+0C0h+var_C8]
0x18007ddef  test    rax, rax
0x18007ddf2  jz      short loc_18007DE0B
0x18007ddf4  test    [rax], sil
0x18007ddf7  jz      short loc_18007DE0B
0x18007ddf9  mov     ecx, [rax+4]
0x18007ddfc  cmp     ecx, 13h
0x18007ddff  ja      short loc_18007DE16
0x18007de01  mov     edx, 85401h
0x18007de06  bt      edx, ecx
0x18007de09  jnb     short loc_18007DE16
0x18007de0b  mov     ecx, dword ptr [rbp+0C0h+var_F8]
0x18007de0e  test    ecx, ecx
0x18007de10  jz      short loc_18007DE61
0x18007de12  cmp     edi, ecx
0x18007de14  jb      short loc_18007DE61
0x18007de16  mov     [rbp+0C0h+var_138], 0
0x18007de1d  mov     [rbp+0C0h+var_128], 4
0x18007de24  test    [rax], sil
0x18007de27  jz      short loc_18007DE2F
0x18007de29  mov     eax, [rax+4]
0x18007de2c  mov     [rbp+0C0h+var_138], eax
0x18007de2f  mov     rcx, [rbx+28h]
0x18007de33  add     rcx, 0B8h
0x18007de3a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007de3f  mov     rdi, rax
0x18007de42  lea     rcx, [rbp+0C0h+var_B0]
0x18007de46  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007de4b  mov     r8, rax
0x18007de4e  mov     [rsp+1E0h+var_180], rdi
0x18007de53  mov     eax, [rbp+0C0h+var_138]
0x18007de56  mov     dword ptr [rsp+1E0h+var_188], eax
0x18007de5a  xor     ecx, ecx
0x18007de5c  jmp     loc_18007E16D
0x18007de61  add     edi, esi
0x18007de63  mov     dword ptr [rbp+0C0h+var_108], edi
0x18007de66  mov     [rbp+0C0h+var_128], r14d
0x18007de6a  mov     rcx, [rbx+28h]
0x18007de6e  add     rcx, 0B8h
0x18007de75  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007de7a  mov     rdi, rax
0x18007de7d  lea     rcx, [rbp+0C0h+var_B0]
0x18007de81  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007de86  mov     r8, rax
0x18007de89  mov     [rsp+1E0h+var_180], rdi
0x18007de8e  xor     ecx, ecx
0x18007de90  mov     dword ptr [rsp+1E0h+var_188], ecx
0x18007de94  mov     [rsp+1E0h+var_190], rcx
0x18007de99  mov     eax, dword ptr [rbp+0C0h+var_108]
0x18007de9c  mov     dword ptr [rsp+1E0h+var_198], eax
0x18007dea0  mov     eax, dword ptr [rbp+0C0h+var_F8]
0x18007dea3  mov     dword ptr [rsp+1E0h+var_1A0], eax
0x18007dea7  mov     eax, dword ptr [rbp+0C0h+var_F0]
0x18007deaa  mov     dword ptr [rsp+1E0h+var_1A8], eax
0x18007deae  mov     dword ptr [rsp+1E0h+var_1B0], r14d
0x18007deb3  mov     byte ptr [rsp+1E0h+var_1B8], cl
0x18007deb7  mov     byte ptr [rsp+1E0h+var_1C0], cl
0x18007debb  mov     r9b, [rbp+0C0h+var_140]
0x18007debf  mov     rdi, [rbp+0C0h+var_118]
0x18007dec3  mov     rdx, rdi
0x18007dec6  lea     rcx, [r13-8]
0x18007deca  call    ?SetDownloadServerToRegistry@EnterpriseManager@LPA@@AEAAJAEAY0CB@$$CBGPEBG_N22W4LPAENTERPRISEDISCOVERYSTATE@@KKKQEAGW4LPAERROR@@1@Z; LPA::EnterpriseManager::SetDownloadServerToRegistry(ushort const (&)[33],ushort const *,bool,bool,bool,LPAENTERPRISEDISCOVERYSTATE,ulong,ulong,ulong,ushort * const,LPAERROR,ushort const *)
0x18007decf  mov     rax, [rbx+28h]
0x18007ded3  mov     ecx, dword ptr [rbp+0C0h+var_108]
0x18007ded6  mov     [rax+0E4h], ecx
0x18007dedc  lea     rax, [r13+0A8h]
0x18007dee3  mov     [rbp+0C0h+var_E8], rax
0x18007dee7  lea     r8, [rbp+0C0h+var_B0]
  ... truncated ...
```
