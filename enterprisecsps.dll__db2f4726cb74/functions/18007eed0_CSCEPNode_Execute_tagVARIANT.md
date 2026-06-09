# CSCEPNode::Execute(tagVARIANT)

- ea: `0x18007eed0`
- end: `0x18007fe79`
- name: `?Execute@CSCEPNode@@UEAAJUtagVARIANT@@@Z`
- size: `4009`
- prototype: `__int64 __fastcall(CSCEPNode *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `43`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180001180`
- `0x180002714`
- `0x180003594`
- `0x180008de0`
- `0x180009cc4`
- `0x18000a9d0`
- `0x18000db4c`
- `0x180015888`
- `0x180019fd8`
- `0x18001a114`
- `0x18001a4d4`
- `0x1800239a4`
- `0x180023f1c`
- `0x180025450`
- `0x180025a78`
- `0x18002d9ec`
- `0x18002dc38`
- `0x180036b00`
- `0x18003f3a0`
- `0x18003f6f0`
- `0x18007daf8`
- `0x18007eed0`
- `0x18007fe80`
- `0x180080054`
- `0x180080074`
- `0x180080094`
- `0x1800812ac`
- `0x180081a28`
- `0x1800827e0`
- `0x180082a70`
- `0x1800837ec`
- `0x180083a20`
- `0x180083acc`
- `0x1800ceb5c`
- `0x1800ced3c`
- `0x1800cf27c`
- `0x1800cf5f4`
- `0x1800cf854`
- `0x1800d1fa8`
- `0x1800d2248`
- `0x1800e046c`
- `0x180100500`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18007fdf4`
- `OLEAUT32!__imp_SysFreeString` at `0x18007fdf4`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x18007fafd`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x18007fafd`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18007f7d4`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18007f81c`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18007f862`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18007f7d4`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18007f81c`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18007f862`
- `cryptngc!NgcQueryEnabled` at `0x18007f228`
- `cryptngc!NgcQueryEnabled` at `0x18007f228`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18007f254`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18007f254`

## string_xrefs

- `0x18007fd9d`: `clientinstall`

## pseudocode

```c
// Hidden C++ exception states: #wind=15 #try_helpers=1
__int64 __fastcall CSCEPNode::Execute(struct CConfigServiceProvider2Impl **this, struct tagVARIANT *a2)
{
  struct SCEPTaskScheduler *Instance; // rbx
  const unsigned __int16 *EnrollmentId2; // rax
  __int64 Imei; // rax
  int v6; // r8d
  int v7; // r9d
  int SCEPRegistryKeyPath; // edi
  char *v9; // rdx
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rdx
  int SCEPFullRegistryPath; // eax
  bool v13; // r15
  struct CConfigServiceProvider2Impl *v14; // rdx
  int v15; // eax
  int v16; // r8d
  int v17; // r9d
  const unsigned __int16 *EKUS; // rdx
  const unsigned __int16 *ContainerName; // rdx
  const unsigned __int16 *AadKeyIdentifers; // rdx
  int v21; // r9d
  __int128 *v22; // rax
  _QWORD *v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  int v28; // r8d
  int v29; // r9d
  __int128 *v30; // rax
  __int64 v31; // rax
  int v32; // r8d
  int v33; // r9d
  __int64 v34; // r14
  int DWORD; // eax
  int v36; // eax
  int v37; // eax
  const unsigned __int16 *v38; // r9
  int v39; // eax
  int v40; // r8d
  int v41; // r9d
  int v42; // r8d
  int v43; // r9d
  const wchar_t *v44; // rcx
  int v45; // eax
  int v46; // r8d
  int v47; // r9d
  __int64 (__fastcall **v48)(_QWORD, _QWORD); // rax
  __int64 v49; // r8
  __int64 v50; // r9
  __int128 *p_Src; // rdx
  int v52; // eax
  int v53; // r8d
  int v54; // r9d
  int IsCertThumbprintPresentInRegistry; // eax
  int v56; // r8d
  int v57; // r9d
  CClientCertScepLogger *Logger; // r10
  const unsigned __int16 *v59; // r9
  const unsigned __int16 *v60; // r8
  const unsigned __int16 *v61; // rax
  bool v63; // [rsp+50h] [rbp-29A8h] BYREF
  bool v64[7]; // [rsp+51h] [rbp-29A7h] BYREF
  __int128 *v65; // [rsp+58h] [rbp-29A0h] BYREF
  _BYTE v66[4]; // [rsp+60h] [rbp-2998h] BYREF
  int v67; // [rsp+64h] [rbp-2994h] BYREF
  __int16 v68; // [rsp+68h] [rbp-2990h] BYREF
  char v69; // [rsp+6Ah] [rbp-298Eh]
  __int64 v70; // [rsp+70h] [rbp-2988h]
  __int64 v71; // [rsp+78h] [rbp-2980h] BYREF
  unsigned int v72; // [rsp+80h] [rbp-2978h] BYREF
  unsigned int v73; // [rsp+84h] [rbp-2974h] BYREF
  unsigned int v74; // [rsp+88h] [rbp-2970h] BYREF
  unsigned __int16 *v75; // [rsp+90h] [rbp-2968h] BYREF
  int v76; // [rsp+98h] [rbp-2960h] BYREF
  unsigned __int16 *v77; // [rsp+A0h] [rbp-2958h] BYREF
  int v78; // [rsp+A8h] [rbp-2950h] BYREF
  BSTR bstrString; // [rsp+B0h] [rbp-2948h] BYREF
  _QWORD v80[2]; // [rsp+B8h] [rbp-2940h] BYREF
  _QWORD v81[2]; // [rsp+C8h] [rbp-2930h] BYREF
  char v82; // [rsp+D8h] [rbp-2920h]
  unsigned __int16 *v83[2]; // [rsp+E0h] [rbp-2918h] BYREF
  __m128i si128; // [rsp+F0h] [rbp-2908h]
  _OWORD v85[2]; // [rsp+100h] [rbp-28F8h] BYREF
  __int128 v86; // [rsp+120h] [rbp-28D8h] BYREF
  __m128i v87; // [rsp+130h] [rbp-28C8h]
  _QWORD v88[3]; // [rsp+140h] [rbp-28B8h] BYREF
  unsigned __int64 v89; // [rsp+158h] [rbp-28A0h]
  _BYTE v90[32]; // [rsp+160h] [rbp-2898h] BYREF
  __int128 Src; // [rsp+180h] [rbp-2878h] BYREF
  __m128i v92; // [rsp+190h] [rbp-2868h]
  _QWORD v93[4]; // [rsp+1A0h] [rbp-2858h] BYREF
  unsigned __int16 v94[1280]; // [rsp+1C0h] [rbp-2838h] BYREF
  unsigned __int16 v95[8]; // [rsp+BC0h] [rbp-1E38h] BYREF
  _BYTE v96[30]; // [rsp+BD0h] [rbp-1E28h]
  _BYTE v97[2514]; // [rsp+BEEh] [rbp-1E0Ah] BYREF
  unsigned __int16 v98[2]; // [rsp+15C0h] [rbp-1438h] BYREF
  _BYTE v99[2556]; // [rsp+15C4h] [rbp-1434h] BYREF
  unsigned __int16 v100[1280]; // [rsp+1FC0h] [rbp-A38h] BYREF

  *(_OWORD *)v95 = *(_OWORD *)L"-s -k \"%s\" -h %s -t %s";
  *(_OWORD *)v96 = *(_OWORD *)L"s\" -h %s -t %s";
  *(_OWORD *)&v96[14] = *(_OWORD *)L"s -t %s";
  memset_0(v97, 0, 0x9D0u);
  *(_DWORD *)v98 = 0;
  memset_0(v99, 0, 0x9FAu);
  v77 = 0;
  v71 = 0;
  Instance = SCEPTaskScheduler::CreateInstance();
  v81[0] = Instance;
  v73 = 1;
  v72 = 1;
  v74 = 0;
  v75 = 0;
  *(_OWORD *)v83 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v83[0]) = 0;
  Src = 0;
  v92 = si128;
  LOWORD(Src) = 0;
  EnrollmentId2 = GetEnrollmentId2(this[2]);
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, EnrollmentId2);
  v66[0] = 0;
  Imei = CellularIdentity::GetImei((char *)this[2] + 104, v90);
  std::wstring::operator=(v83, Imei);
  std::wstring::_Tidy_deallocate(v90);
  if ( *((_DWORD *)this + 11) != 17 )
  {
    SCEPRegistryKeyPath = -2046820335;
    if ( (unsigned int)dword_180155C20 <= 3 )
    {
LABEL_117:
      v52 = UtilsWriteErrorCodeAndStatus(CSCEPNode::m_hCurrentHive, v94, 1);
      if ( v52 < 0 && (unsigned int)dword_180155C20 > 3 )
      {
        LODWORD(v65) = v52;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180155C20,
          (unsigned int)&byte_1801343E7,
          v53,
          v54,
          (__int64)&v65);
      }
      goto LABEL_122;
    }
    v67 = -2046820335;
    v9 = (char *)&dword_18013483C;
LABEL_4:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180155C20,
      (_DWORD)v9,
      v6,
      v7,
      (__int64)&v67);
    goto LABEL_117;
  }
  v76 = 0;
  (*(void (__fastcall **)(struct CConfigServiceProvider2Impl *, int *))(*(_QWORD *)this[3] + 136LL))(this[3], &v76);
  (*(void (__fastcall **)(struct CConfigServiceProvider2Impl *, _QWORD, unsigned __int16 **))(*(_QWORD *)this[3] + 88LL))(
    this[3],
    (unsigned int)(v76 - 3),
    &v77);
  SCEPRegistryKeyPath = CSCEPNode::GetSCEPRegistryKeyPath(v100, v10, 1, this[3], this[2], 1);
  if ( SCEPRegistryKeyPath < 0 )
  {
    if ( (unsigned int)dword_180155C20 <= 3 )
      goto LABEL_117;
    v67 = SCEPRegistryKeyPath;
    v9 = (char *)&word_180134876;
    goto LABEL_4;
  }
  SCEPFullRegistryPath = UtilsGetSCEPFullRegistryPath(v94, v11, v100);
  SCEPRegistryKeyPath = SCEPFullRegistryPath;
  if ( SCEPFullRegistryPath < 0 )
  {
    if ( (unsigned int)dword_180155C20 <= 3 )
      goto LABEL_117;
    v67 = SCEPFullRegistryPath;
    v9 = &byte_1801347B7;
    goto LABEL_4;
  }
  v13 = 1;
  (*(void (__fastcall **)(struct CConfigServiceProvider2Impl *, __int64 *))(*(_QWORD *)this[2] + 48LL))(this[2], &v71);
  v64[0] = 0;
  if ( CSCEPNode::m_fIsCertStore )
    goto LABEL_65;
  SCEPRegistryKeyPath = CSCEPNode::TryFetchingNGCData((CSCEPNode *)this, v94);
  if ( SCEPRegistryKeyPath < 0 )
  {
    if ( (unsigned int)dword_180155C20 <= 4 )
      goto LABEL_117;
    v67 = SCEPRegistryKeyPath;
    v9 = byte_1801347F9;
    goto LABEL_4;
  }
  v14 = this[2];
  if ( !*((_DWORD *)v14 + 44) )
  {
LABEL_65:
    v34 = -1;
    goto LABEL_66;
  }
  v68 = 0;
  v69 = 0;
  v70 = 0;
  if ( CSCEPNode::m_fIsUser )
  {
    SCEPRegistryKeyPath = AutoImpersonate::ImpersonateTargetedUser((AutoImpersonate *)&v68, v14);
    if ( SCEPRegistryKeyPath < 0 )
      goto LABEL_31;
  }
  v78 = 2;
  v67 = 0;
  v15 = NgcQueryEnabled(v75, 0, &v78, &v67, 0, 0);
  SCEPRegistryKeyPath = v15;
  if ( v15 >= 0 )
  {
    if ( v67 == 1 )
    {
      SCEPRegistryKeyPath = -2102722543;
      if ( (unsigned int)dword_180155C20 > 3 )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_180155C20,
          &dword_18013471C,
          0);
      goto LABEL_31;
    }
    if ( !CSCEPNode::m_fIsUser )
    {
      SCEPRegistryKeyPath = -2046820352;
      if ( (unsigned int)dword_180155C20 > 3 )
      {
        LODWORD(v65) = -2046820352;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180155C20,
          (unsigned int)word_18013473A,
          v16,
          v17,
          (__int64)&v65);
      }
      goto LABEL_31;
    }
    v80[0] = &SCEPNGCUtils::`vftable';
    v80[1] = v71;
    v63 = 0;
    EKUS = CClientCertificateInstallCsp::GetEKUS(this[2]);
    std::wstring::wstring(v93, EKUS);
    ContainerName = CClientCertificateInstallCsp::GetContainerName(this[2]);
    std::wstring::wstring(v90, ContainerName);
    AadKeyIdentifers = CClientCertificateInstallCsp::GetAadKeyIdentifers(this[2]);
    std::wstring::wstring(v88, AadKeyIdentifers);
    if ( (v89 <= 7 || v88[0]) && (unsigned int)dword_180155C20 > 4 )
    {
      v22 = (__int128 *)v88;
      if ( v89 > 7 )
        v22 = (__int128 *)v88[0];
      v65 = v22;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (unsigned int)&dword_180155C20,
        (unsigned int)&word_18013477E,
        0,
        v21,
        (__int64)&v65);
    }
    v23 = v93;
    if ( v93[3] > 7u )
      v23 = (_QWORD *)v93[0];
    v24 = std::wstring::wstring(v85, v23);
    NGCUtils::IsSmartCardLogonCertificate(v25, v24, &v63);
    if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)v71 + 40LL))(v71) < 0 )
    {
      v34 = -1;
    }
    else
    {
      v81[1] = &v71;
      v82 = 1;
      v85[0] = 0;
      v85[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v85[0]) = 0;
      if ( v63 )
      {
        NGCUtils::GetAADLogonKeyName(v26, v90, v85);
        v86 = 0;
        v87 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v86) = 0;
        SCEPRegistryKeyPath = NGCUtils::GetAADKeyIdentifier(v27, v85, &v86);
        if ( SCEPRegistryKeyPath < 0 )
        {
          if ( (unsigned int)dword_180155C20 > 3 )
          {
            LODWORD(v65) = SCEPRegistryKeyPath;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180155C20,
              (unsigned int)byte_180134643,
              v28,
              v29,
              (__int64)&v65);
          }
LABEL_59:
          std::wstring::_Tidy_deallocate(&v86);
          std::wstring::_Tidy_deallocate(v85);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 48LL))(v71);
          std::wstring::_Tidy_deallocate(v88);
          std::wstring::_Tidy_deallocate(v90);
          std::wstring::_Tidy_deallocate(v93);
          v80[0] = &SCEPNGCUtils::`vftable';
          goto LABEL_31;
        }
        if ( (v87.m128i_i64[1] <= 7uLL || (_QWORD)v86) && (unsigned int)dword_180155C20 > 4 )
        {
          v30 = &v86;
          if ( v87.m128i_i64[1] > 7uLL )
            v30 = (__int128 *)v86;
          v65 = v30;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (unsigned int)&dword_180155C20,
            (unsigned int)&word_18013467E,
            0,
            v29,
            (__int64)&v65);
        }
        if ( v88[2] )
        {
          v31 = std::wstring::find(v88, &v86);
          if ( !v87.m128i_i64[0] || (v34 = -1, v31 == -1) )
          {
            SCEPRegistryKeyPath = -2102722544;
            if ( (unsigned int)dword_180155C20 > 3 )
            {
              LODWORD(v65) = -2102722544;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                (unsigned int)&dword_180155C20,
                (unsigned int)byte_1801346B3,
                v32,
                v33,
                (__int64)&v65);
            }
            goto LABEL_59;
          }
        }
        else
        {
          v34 = -1;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 48LL))(v71);
        v82 = 0;
        NGCUtils::SetPinCachingPolicyToContainer((__int64)v80, (__int64)v85, 1, v64);
        v13 = v64[0];
        std::wstring::_Tidy_deallocate(&v86);
        std::wstring::_Tidy_deallocate(v85);
      }
      else
      {
        NGCUtils::ConstructContainerName(v26, v90, v85);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 48LL))(v71);
        v82 = 0;
        NGCUtils::SetPinCachingPolicyToContainer((__int64)v80, (__int64)v85, 0, v64);
        v13 = v64[0];
        std::wstring::_Tidy_deallocate(v85);
        v34 = -1;
      }
    }
    std::wstring::_Tidy_deallocate(v88);
    std::wstring::_Tidy_deallocate(v90);
    std::wstring::_Tidy_deallocate(v93);
    v80[0] = &SCEPNGCUtils::`vftable';
    AutoImpersonate::~AutoImpersonate((AutoImpersonate *)&v68);
LABEL_66:
    v68 = 0;
    v69 = 0;
    v70 = 0;
    if ( CSCEPNode::m_fIsUser == 1 )
    {
      SCEPRegistryKeyPath = AutoImpersonate::ImpersonateTargetedUser((AutoImpersonate *)&v68, this[2]);
      if ( SCEPRegistryKeyPath < 0 )
        goto LABEL_31;
    }
    DWORD = OmaDmRegistryGetDWORD(CSCEPNode::m_hCurrentHive, v94, L"KeyProtection", &v74);
    SCEPRegistryKeyPath = DWORD;
    if ( DWORD == -2147024894 )
    {
      v74 = 3;
    }
    else if ( DWORD < 0 )
    {
      goto LABEL_31;
    }
    v36 = OmaDmRegistryGetDWORD(CSCEPNode::m_hCurrentHive, v94, L"RetryDelay", &v72);
    SCEPRegistryKeyPath = v36;
    if ( v36 == -2147024894 )
    {
      v72 = 5;
    }
    else if ( v36 < 0 )
    {
      goto LABEL_31;
    }
    v37 = OmaDmRegistryGetDWORD(CSCEPNode::m_hCurrentHive, v94, L"RetryCount", &v73);
    SCEPRegistryKeyPath = v37;
    if ( v37 == -2147024894 )
    {
      v73 = 3;
    }
    else if ( v37 < 0 )
    {
      goto LABEL_31;
    }
    v38 = (const unsigned __int16 *)v83;
    if ( si128.m128i_i64[1] > 7uLL )
      v38 = v83[0];
    v39 = UtilsWriteRegistryStringValue(CSCEPNode::m_hCurrentHive, v94, L"CorrelationGuid", v38);
    if ( v39 < 0 && (unsigned int)dword_180155C20 > 3 )
    {
      LODWORD(v65) = v39;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_180155C20,
        (unsigned int)&dword_180134604,
        v40,
        v41,
        (__int64)&v65);
    }
    SCEPRegistryKeyPath = UtilsWriteErrorCodeAndStatus(CSCEPNode::m_hCurrentHive, v94, 1);
    if ( SCEPRegistryKeyPath >= 0 )
    {
      UtilsWriteRegistryDWORDValue(CSCEPNode::m_hCurrentHive, v94, L"CurrentRetryCount", 0);
      v44 = L"HKCU";
      if ( CSCEPNode::m_fIsUser != 1 )
        v44 = L"HKLM";
      SCEPRegistryKeyPath = StringCchPrintfW(v98, 0x4FFu, v95, v94, v44, v77);
      if ( SCEPRegistryKeyPath >= 0 )
      {
        v45 = UtilsWriteRegistryStringValue(CSCEPNode::m_hCurrentHive, v94, L"EnrollmentId", bstrString);
        if ( v45 < 0 && (unsigned int)dword_180155C20 > 3 )
        {
          LODWORD(v65) = v45;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_180155C20,
            (unsigned int)&unk_1801344E8,
            v46,
            v47,
            (__int64)&v65);
        }
        AutoImpersonate::~AutoImpersonate((AutoImpersonate *)&v68);
        SCEPRegistryKeyPath = (**(__int64 (__fastcall ***)(struct SCEPTaskScheduler *, unsigned __int16 *))Instance)(
                                Instance,
                                v98);
        if ( SCEPRegistryKeyPath < 0 )
        {
          if ( (unsigned int)dword_180155C20 > 3 )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              &dword_180155C20,
              &byte_180134527,
              0);
          goto LABEL_117;
        }
        v68 = 0;
        v69 = 0;
        v70 = 0;
        if ( CSCEPNode::m_fIsUser == 1 )
        {
          SCEPRegistryKeyPath = AutoImpersonate::ImpersonateTargetedUser((AutoImpersonate *)&v68, this[2]);
          if ( SCEPRegistryKeyPath < 0 )
            goto LABEL_31;
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v75,
          0);
        SCEPRegistryKeyPath = DmGetCurrentUserSid(&v75);
        if ( SCEPRegistryKeyPath >= 0 )
        {
          v48 = *(__int64 (__fastcall ***)(_QWORD, _QWORD))Instance;
          if ( v13 )
          {
            SCEPRegistryKeyPath = ((__int64 (__fastcall *)(struct SCEPTaskScheduler *, _QWORD, _QWORD))v48[1])(
                                    Instance,
                                    v73,
                                    v72);
            if ( SCEPRegistryKeyPath < 0 )
            {
              if ( (unsigned int)dword_180155C20 > 3 )
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                  &dword_180155C20,
                  byte_180134459,
                  0);
              goto LABEL_31;
            }
          }
          else
          {
            SCEPRegistryKeyPath = ((__int64 (__fastcall *)(struct SCEPTaskScheduler *))v48[2])(Instance);
            if ( SCEPRegistryKeyPath < 0 )
            {
              if ( (unsigned int)dword_180155C20 > 3 )
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                  &dword_180155C20,
                  word_18013448A,
                  0);
              goto LABEL_31;
            }
          }
          AutoImpersonate::~AutoImpersonate((AutoImpersonate *)&v68);
          v49 = -1;
          do
            ++v49;
          while ( v77[v49] );
          std::wstring::_Assign<unsigned short>(&Src, v77);
          do
            ++v34;
          while ( v75[v34] );
          std::wstring::_Append<unsigned short>(&Src);
          p_Src = &Src;
          if ( v92.m128i_i64[1] > 7uLL )
            p_Src = (__int128 *)Src;
          LOBYTE(v50) = v13;
          SCEPRegistryKeyPath = (*(__int64 (__fastcall **)(struct SCEPTaskScheduler *, __int128 *, unsigned __int16 *, __int64))(*(_QWORD *)Instance + 24LL))(
                                  Instance,
                                  p_Src,
                                  v75,
                                  v50);
          if ( SCEPRegistryKeyPath < 0 )
          {
            if ( (unsigned int)dword_180155C20 > 3 )
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                &dword_180155C20,
                word_1801344BA,
                0);
            goto LABEL_117;
          }
          SCEPRegistryKeyPath = 44761091;
          if ( (unsigned int)dword_180155C20 > 4 )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              &dword_180155C20,
              qword_1801343B8,
              0);
          goto LABEL_122;
        }
        if ( (unsigned int)dword_180155C20 > 3 )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_180155C20,
            &dword_18013455C,
            0);
      }
      else if ( (unsigned int)dword_180155C20 > 3 )
      {
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_180155C20,
          byte_1801345D3,
          0);
      }
    }
    else if ( (unsigned int)dword_180155C20 > 3 )
    {
      LODWORD(v65) = SCEPRegistryKeyPath;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_180155C20,
        (unsigned int)byte_180134591,
        v42,
        v43,
        (__int64)&v65);
    }
LABEL_31:
    AutoImpersonate::~AutoImpersonate((AutoImpersonate *)&v68);
    goto LABEL_117;
  }
  if ( v15 == -2146893808
    && (unsigned __int8)IsWinStationIsSessionRemoteablePresent()
    && (unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, v66)
    && v66[0] )
  {
    SCEPRegistryKeyPath = -2102722542;
  }
  if ( (unsigned int)dword_180155C20 > 3 )
  {
    LODWORD(v65) = SCEPRegistryKeyPath;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180155C20,
      (unsigned int)&word_1801346EE,
      v16,
      v17,
      (__int64)&v65);
  }
  AutoImpersonate::~AutoImpersonate((AutoImpersonate *)&v68);
  if ( SCEPRegistryKeyPath != 44761091 )
    goto LABEL_117;
LABEL_122:
  v63 = 0;
  IsCertThumbprintPresentInRegistry = UtilsIsCertThumbprintPresentInRegistry(CSCEPNode::m_hCurrentHive, v94, &v63);
  if ( IsCertThumbprintPresentInRegistry < 0 && (unsigned int)dword_180155C20 > 3 )
  {
    LODWORD(v65) = IsCertThumbprintPresentInRegistry;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180155C20,
      (unsigned int)byte_180134429,
      v56,
      v57,
      (__int64)&v65);
  }
  Logger = CClientCertScepLogger::GetLogger();
  v59 = (const unsigned __int16 *)v83;
  if ( si128.m128i_i64[1] > 7uLL )
    v59 = v83[0];
  v60 = L"user";
  if ( CSCEPNode::m_fIsUser != 1 )
    v60 = L"system";
  v61 = L"certificatestore";
  if ( CSCEPNode::m_fIsCertStore != 1 )
    v61 = L"clientinstall";
  CClientCertScepLogger::LogSCEPCspExecute(Logger, v75, v77, v74, SCEPRegistryKeyPath, v61, v60, bstrString, v63, v59);
  SysFreeString(bstrString);
  std::wstring::_Tidy_deallocate(&Src);
  std::wstring::_Tidy_deallocate(v83);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v75);
  std::unique_ptr<SCEPTaskScheduler>::~unique_ptr<SCEPTaskScheduler>(v81);
  ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v71);
  return (unsigned int)SCEPRegistryKeyPath;
}

```

## disassembly

```asm
0x18007eed0  mov     [rsp+arg_8], rbx
0x18007eed5  mov     [rsp+arg_10], rsi
0x18007eeda  push    rdi
0x18007eedb  push    r12
0x18007eedd  push    r13
0x18007eedf  push    r14
0x18007eee1  push    r15
0x18007eee3  mov     eax, 29D0h
0x18007eee8  call    _alloca_probe
0x18007eeed  sub     rsp, rax
0x18007eef0  mov     rax, cs:__security_cookie
0x18007eef7  xor     rax, rsp
0x18007eefa  mov     [rsp+29F8h+var_38], rax
0x18007ef02  mov     rsi, rcx
0x18007ef05  movups  xmm0, xmmword ptr cs:aSKSHSTS; "-s -k \"%s\" -h %s -t %s"
0x18007ef0c  movaps  xmmword ptr [rsp+29F8h+var_1E38], xmm0
0x18007ef14  movups  xmm1, xmmword ptr cs:aSKSHSTS+10h; "s\" -h %s -t %s"
0x18007ef1b  movaps  xmmword ptr [rsp+29F8h+var_1E28], xmm1
0x18007ef23  movups  xmm0, xmmword ptr cs:aSKSHSTS+1Eh; "s -t %s"
0x18007ef2a  movups  xmmword ptr [rsp+29F8h+var_1E28+0Eh], xmm0
0x18007ef32  xor     edx, edx; Val
0x18007ef34  mov     r8d, 9D0h; Size
0x18007ef3a  lea     rcx, [rsp+29F8h+var_1E0A]; void *
0x18007ef42  call    memset_0
0x18007ef47  xor     r12d, r12d
0x18007ef4a  mov     dword ptr [rsp+29F8h+var_1438], r12d
0x18007ef52  xor     edx, edx; Val
0x18007ef54  mov     r8d, 9FAh; Size
0x18007ef5a  lea     rcx, [rsp+29F8h+var_1434]; void *
0x18007ef62  call    memset_0
0x18007ef67  mov     [rsp+29F8h+var_2958], r12
0x18007ef6f  mov     [rsp+29F8h+var_2980], r12
0x18007ef74  call    ?CreateInstance@SCEPTaskScheduler@@SAPEAV1@XZ; SCEPTaskScheduler::CreateInstance(void)
0x18007ef79  mov     rbx, rax
0x18007ef7c  mov     [rsp+29F8h+var_2930], rax
0x18007ef84  mov     [rsp+29F8h+var_2974], 1
0x18007ef8f  mov     [rsp+29F8h+var_2978], 1
0x18007ef9a  mov     [rsp+29F8h+var_2970], r12d
0x18007efa2  mov     [rsp+29F8h+var_2968], r12
0x18007efaa  xorps   xmm0, xmm0
0x18007efad  movups  xmmword ptr [rsp+29F8h+var_2918], xmm0
0x18007efb5  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18007efbd  movdqu  [rsp+29F8h+var_2908], xmm1
0x18007efc6  mov     word ptr [rsp+29F8h+var_2918], r12w
0x18007efcf  movups  [rsp+29F8h+Src], xmm0
0x18007efd7  movdqu  [rsp+29F8h+var_2868], xmm1
0x18007efe0  mov     word ptr [rsp+29F8h+Src], r12w
0x18007efe9  mov     rcx, [rsi+10h]; struct CConfigServiceProvider2Impl *
0x18007efed  call    ?GetEnrollmentId2@@YAPEAGPEAVCConfigServiceProvider2Impl@@@Z; GetEnrollmentId2(CConfigServiceProvider2Impl *)
0x18007eff2  mov     rdx, rax; unsigned __int16 *
0x18007eff5  lea     rcx, [rsp+29F8h+bstrString]; this
0x18007effd  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18007f002  nop
0x18007f003  mov     [rsp+29F8h+var_2998], r12b
0x18007f008  mov     rcx, [rsi+10h]
0x18007f00c  add     rcx, 68h ; 'h'
0x18007f010  lea     rdx, [rsp+29F8h+var_2898]
0x18007f018  cmp     cs:?m_fIsCertStore@CSCEPNode@@0HA, r12d; int CSCEPNode::m_fIsCertStore
0x18007f01f  jz      short loc_18007F028
0x18007f021  call    ?GetImei@CellularIdentity@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CellularIdentity::GetImei(void)
0x18007f026  jmp     short loc_18007F02D
0x18007f028  call    ?GetImei@CellularIdentity@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CellularIdentity::GetImei(void)
0x18007f02d  mov     rdx, rax
0x18007f030  lea     rcx, [rsp+29F8h+var_2918]
0x18007f038  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18007f03d  lea     rcx, [rsp+29F8h+var_2898]
0x18007f045  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007f04a  cmp     dword ptr [rsi+2Ch], 11h
0x18007f04e  jz      short loc_18007F08E
0x18007f050  mov     edi, 86000011h
0x18007f055  mov     eax, cs:dword_180155C20
0x18007f05b  cmp     eax, 3
0x18007f05e  jbe     loc_18007FC6B
0x18007f064  mov     [rsp+29F8h+var_2994], 86000011h
0x18007f06c  lea     rdx, dword_18013483C
0x18007f073  lea     rax, [rsp+29F8h+var_2994]
0x18007f078  mov     [rsp+29F8h+var_29D8], rax
0x18007f07d  lea     rcx, dword_180155C20
0x18007f084  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18007f089  jmp     loc_18007FC6B
0x18007f08e  mov     [rsp+29F8h+var_2960], r12d
0x18007f096  mov     rcx, [rsi+18h]
0x18007f09a  mov     rax, [rcx]
0x18007f09d  lea     rdx, [rsp+29F8h+var_2960]
0x18007f0a5  mov     rax, [rax+88h]
0x18007f0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f0b1  mov     rcx, [rsi+18h]
0x18007f0b5  mov     rax, [rcx]
0x18007f0b8  mov     edx, [rsp+29F8h+var_2960]
0x18007f0bf  add     edx, 0FFFFFFFDh
0x18007f0c2  lea     r8, [rsp+29F8h+var_2958]
0x18007f0ca  mov     rax, [rax+58h]
0x18007f0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f0d3  mov     dword ptr [rsp+29F8h+var_29D0], 1; int
0x18007f0db  mov     rax, [rsi+10h]
0x18007f0df  mov     [rsp+29F8h+var_29D8], rax; struct CConfigServiceProvider2Impl *
0x18007f0e4  mov     r9, [rsi+18h]; struct IConfigManager2URI *
0x18007f0e8  mov     r8d, 1; int
0x18007f0ee  lea     rcx, [rsp+29F8h+var_A38]; unsigned __int16 *
0x18007f0f6  call    ?GetSCEPRegistryKeyPath@CSCEPNode@@CAJPEAG_KHPEAUIConfigManager2URI@@PEAVCConfigServiceProvider2Impl@@H@Z; CSCEPNode::GetSCEPRegistryKeyPath(ushort *,unsigned __int64,int,IConfigManager2URI *,CConfigServiceProvider2Impl *,int)
0x18007f0fb  mov     edi, eax
0x18007f0fd  test    eax, eax
0x18007f0ff  jns     short loc_18007F120
0x18007f101  mov     eax, cs:dword_180155C20
0x18007f107  cmp     eax, 3
0x18007f10a  jbe     loc_18007FC6B
0x18007f110  mov     [rsp+29F8h+var_2994], edi
0x18007f114  lea     rdx, word_180134876
0x18007f11b  jmp     loc_18007F073
0x18007f120  lea     r8, [rsp+29F8h+var_A38]; unsigned __int16 *
0x18007f128  lea     rcx, [rsp+29F8h+var_2838]; unsigned __int16 *
0x18007f130  call    ?UtilsGetSCEPFullRegistryPath@@YAJPEAG_KPEBG@Z; UtilsGetSCEPFullRegistryPath(ushort *,unsigned __int64,ushort const *)
0x18007f135  mov     edi, eax
0x18007f137  test    eax, eax
0x18007f139  jns     short loc_18007F15A
0x18007f13b  mov     ecx, cs:dword_180155C20
0x18007f141  cmp     ecx, 3
0x18007f144  jbe     loc_18007FC6B
0x18007f14a  mov     [rsp+29F8h+var_2994], eax
0x18007f14e  lea     rdx, byte_1801347B7
0x18007f155  jmp     loc_18007F073
0x18007f15a  mov     r15b, 1
0x18007f15d  mov     rcx, [rsi+10h]
0x18007f161  mov     rax, [rcx]
0x18007f164  lea     rdx, [rsp+29F8h+var_2980]
0x18007f169  mov     rax, [rax+30h]
0x18007f16d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f172  mov     [rsp+29F8h+var_29A7], r12b
0x18007f177  cmp     cs:?m_fIsCertStore@CSCEPNode@@0HA, r12d; int CSCEPNode::m_fIsCertStore
0x18007f17e  jnz     loc_18007F780
0x18007f184  lea     rdx, [rsp+29F8h+var_2838]; unsigned __int16 *
0x18007f18c  mov     rcx, rsi; this
0x18007f18f  call    ?TryFetchingNGCData@CSCEPNode@@AEAAJPEBG@Z; CSCEPNode::TryFetchingNGCData(ushort const *)
0x18007f194  mov     edi, eax
0x18007f196  test    eax, eax
0x18007f198  jns     short loc_18007F1B9
0x18007f19a  mov     eax, cs:dword_180155C20
0x18007f1a0  cmp     eax, 4
0x18007f1a3  jbe     loc_18007FC6B
0x18007f1a9  mov     [rsp+29F8h+var_2994], edi
0x18007f1ad  lea     rdx, byte_1801347F9
0x18007f1b4  jmp     loc_18007F073
0x18007f1b9  mov     rdx, [rsi+10h]; struct CConfigServiceProvider2Impl *
0x18007f1bd  cmp     [rdx+0B0h], r12d
0x18007f1c4  jz      loc_18007F780
0x18007f1ca  mov     [rsp+29F8h+var_2990], r12w
0x18007f1d0  mov     [rsp+29F8h+var_298E], r12b
0x18007f1d5  mov     [rsp+29F8h+var_2988], r12
0x18007f1da  cmp     cs:?m_fIsUser@CSCEPNode@@0HA, r12d; int CSCEPNode::m_fIsUser
0x18007f1e1  jz      short loc_18007F1F7
0x18007f1e3  lea     rcx, [rsp+29F8h+var_2990]; this
0x18007f1e8  call    ?ImpersonateTargetedUser@AutoImpersonate@@QEAAJPEAVCConfigServiceProvider2Impl@@@Z; AutoImpersonate::ImpersonateTargetedUser(CConfigServiceProvider2Impl *)
0x18007f1ed  mov     edi, eax
0x18007f1ef  test    eax, eax
0x18007f1f1  js      loc_18007F2E7
0x18007f1f7  mov     [rsp+29F8h+var_2950], 2
0x18007f202  mov     [rsp+29F8h+var_2994], r12d
0x18007f207  mov     [rsp+29F8h+var_29D0], r12
0x18007f20c  mov     [rsp+29F8h+var_29D8], r12
0x18007f211  lea     r9, [rsp+29F8h+var_2994]
0x18007f216  lea     r8, [rsp+29F8h+var_2950]
0x18007f21e  xor     edx, edx
0x18007f220  mov     rcx, [rsp+29F8h+var_2968]
0x18007f228  call    cs:__imp_NgcQueryEnabled
0x18007f22f  nop     dword ptr [rax+rax+00h]
0x18007f234  mov     edi, eax
0x18007f236  test    eax, eax
0x18007f238  jns     short loc_18007F2B9
0x18007f23a  cmp     eax, 80090010h
0x18007f23f  jnz     short loc_18007F271
0x18007f241  call    IsWinStationIsSessionRemoteablePresent
0x18007f246  test    al, al
0x18007f248  jz      short loc_18007F271
0x18007f24a  lea     r8, [rsp+29F8h+var_2998]
0x18007f24f  or      edx, 0FFFFFFFFh
0x18007f252  xor     ecx, ecx
0x18007f254  call    cs:__imp_WinStationIsSessionRemoteable
0x18007f25b  nop     dword ptr [rax+rax+00h]
0x18007f260  test    al, al
0x18007f262  jz      short loc_18007F271
0x18007f264  mov     eax, 82AB0012h
0x18007f269  cmp     [rsp+29F8h+var_2998], r12b
0x18007f26e  cmovnz  edi, eax
0x18007f271  mov     eax, cs:dword_180155C20
0x18007f277  cmp     eax, 3
0x18007f27a  jbe     short loc_18007F29E
0x18007f27c  mov     dword ptr [rsp+29F8h+var_29A0], edi
0x18007f280  lea     rax, [rsp+29F8h+var_29A0]
0x18007f285  mov     [rsp+29F8h+var_29D8], rax
0x18007f28a  lea     rdx, word_1801346EE
0x18007f291  lea     rcx, dword_180155C20
0x18007f298  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18007f29d  nop
0x18007f29e  lea     rcx, [rsp+29F8h+var_2990]; this
0x18007f2a3  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18007f2a8  cmp     edi, 2AB0003h
0x18007f2ae  jnz     loc_18007FC6B
0x18007f2b4  jmp     loc_18007FD01
0x18007f2b9  cmp     [rsp+29F8h+var_2994], 1
0x18007f2be  jnz     short loc_18007F2F6
0x18007f2c0  mov     edi, 82AB0011h
0x18007f2c5  mov     eax, cs:dword_180155C20
0x18007f2cb  cmp     eax, 3
0x18007f2ce  jbe     short loc_18007F2E7
0x18007f2d0  xor     r8d, r8d
0x18007f2d3  lea     rdx, dword_18013471C
0x18007f2da  lea     rcx, dword_180155C20
0x18007f2e1  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18007f2e6  nop
0x18007f2e7  lea     rcx, [rsp+29F8h+var_2990]; this
0x18007f2ec  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18007f2f1  jmp     loc_18007FC6B
0x18007f2f6  cmp     cs:?m_fIsUser@CSCEPNode@@0HA, r12d; int CSCEPNode::m_fIsUser
0x18007f2fd  jnz     short loc_18007F336
0x18007f2ff  mov     edi, 86000000h
0x18007f304  mov     eax, cs:dword_180155C20
0x18007f30a  cmp     eax, 3
0x18007f30d  jbe     short loc_18007F2E7
0x18007f30f  mov     dword ptr [rsp+29F8h+var_29A0], 86000000h
0x18007f317  lea     rax, [rsp+29F8h+var_29A0]
0x18007f31c  mov     [rsp+29F8h+var_29D8], rax
0x18007f321  lea     rdx, word_18013473A
0x18007f328  lea     rcx, dword_180155C20
0x18007f32f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18007f334  jmp     short loc_18007F2E7
0x18007f336  lea     r13, ??_7SCEPNGCUtils@@6B@; const SCEPNGCUtils::`vftable'
0x18007f33d  mov     [rsp+29F8h+var_2940], r13
0x18007f345  mov     rax, [rsp+29F8h+var_2980]
0x18007f34a  mov     [rsp+29F8h+var_2938], rax
0x18007f352  mov     [rsp+29F8h+var_29A8], r12b
0x18007f357  mov     rcx, [rsi+10h]; this
0x18007f35b  call    ?GetEKUS@CClientCertificateInstallCsp@@QEAAPEBGXZ; CClientCertificateInstallCsp::GetEKUS(void)
0x18007f360  mov     rdx, rax
0x18007f363  lea     rcx, [rsp+29F8h+var_2858]
0x18007f36b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007f370  nop
0x18007f371  mov     rcx, [rsi+10h]; this
0x18007f375  call    ?GetContainerName@CClientCertificateInstallCsp@@QEAAPEBGXZ; CClientCertificateInstallCsp::GetContainerName(void)
0x18007f37a  mov     rdx, rax
0x18007f37d  lea     rcx, [rsp+29F8h+var_2898]
0x18007f385  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007f38a  nop
0x18007f38b  mov     rcx, [rsi+10h]; this
0x18007f38f  call    ?GetAadKeyIdentifers@CClientCertificateInstallCsp@@QEAAPEBGXZ; CClientCertificateInstallCsp::GetAadKeyIdentifers(void)
0x18007f394  mov     rdx, rax
0x18007f397  lea     rcx, [rsp+29F8h+var_28B8]
0x18007f39f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007f3a4  nop
0x18007f3a5  cmp     [rsp+29F8h+var_28A0], 7
0x18007f3ae  jbe     short loc_18007F3BA
0x18007f3b0  cmp     [rsp+29F8h+var_28B8], r12
0x18007f3b8  jz      short loc_18007F404
0x18007f3ba  mov     eax, cs:dword_180155C20
0x18007f3c0  cmp     eax, 4
0x18007f3c3  jbe     short loc_18007F404
0x18007f3c5  lea     rax, [rsp+29F8h+var_28B8]
0x18007f3cd  cmp     [rsp+29F8h+var_28A0], 7
0x18007f3d6  cmova   rax, [rsp+29F8h+var_28B8]
0x18007f3df  mov     [rsp+29F8h+var_29A0], rax
0x18007f3e4  lea     rax, [rsp+29F8h+var_29A0]
0x18007f3e9  mov     [rsp+29F8h+var_29D8], rax
0x18007f3ee  xor     r8d, r8d
0x18007f3f1  lea     rdx, word_18013477E
0x18007f3f8  lea     rcx, dword_180155C20
0x18007f3ff  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18007f404  lea     rdx, [rsp+29F8h+var_2858]
0x18007f40c  cmp     [rsp+29F8h+var_2840], 7
0x18007f415  cmova   rdx, [rsp+29F8h+var_2858]
0x18007f41e  lea     rcx, [rsp+29F8h+var_28F8]
0x18007f426  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007f42b  lea     r8, [rsp+29F8h+var_29A8]
0x18007f430  mov     rdx, rax
0x18007f433  call    ?IsSmartCardLogonCertificate@NGCUtils@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_N@Z; NGCUtils::IsSmartCardLogonCertificate(std::wstring,bool &)
0x18007f438  mov     rcx, [rsp+29F8h+var_2980]
0x18007f43d  mov     rax, [rcx]
0x18007f440  mov     rax, [rax+28h]
0x18007f444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f449  test    eax, eax
0x18007f44b  js      loc_18007F73E
0x18007f451  lea     rax, [rsp+29F8h+var_2980]
0x18007f456  mov     [rsp+29F8h+var_2928], rax
0x18007f45e  mov     [rsp+29F8h+var_2920], 1
0x18007f466  xorps   xmm0, xmm0
0x18007f469  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18007f471  movups  [rsp+29F8h+var_28F8], xmm0
0x18007f479  movdqu  [rsp+29F8h+var_28E8], xmm1
0x18007f482  mov     word ptr [rsp+29F8h+var_28F8], r12w
0x18007f48b  cmp     [rsp+29F8h+var_29A8], r12b
0x18007f490  jz      loc_18007F6DB
0x18007f496  lea     r8, [rsp+29F8h+var_28F8]
0x18007f49e  lea     rdx, [rsp+29F8h+var_2898]
0x18007f4a6  call    ?GetAADLogonKeyName@NGCUtils@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; NGCUtils::GetAADLogonKeyName(std::wstring const &,std::wstring &)
0x18007f4ab  xorps   xmm0, xmm0
0x18007f4ae  movups  [rsp+29F8h+var_28D8], xmm0
0x18007f4b6  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18007f4be  movdqu  [rsp+29F8h+var_28C8], xmm1
0x18007f4c7  mov     word ptr [rsp+29F8h+var_28D8], r12w
0x18007f4d0  lea     r8, [rsp+29F8h+var_28D8]
0x18007f4d8  lea     rdx, [rsp+29F8h+var_28F8]
0x18007f4e0  call    ?GetAADKeyIdentifier@NGCUtils@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; NGCUtils::GetAADKeyIdentifier(std::wstring const &,std::wstring &)
  ... truncated ...
```
