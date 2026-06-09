# CMSVidBDATuner::put_Container(IMSVidGraphSegmentContainer *)

- ea: `0x1800b7600`
- end: `0x1800b91c2`
- name: `?put_Container@CMSVidBDATuner@@UEAAJPEAUIMSVidGraphSegmentContainer@@@Z`
- size: `7106`
- prototype: `__int64 __fastcall(CMSVidBDATuner *__hidden this, struct IMSVidGraphSegmentContainer *)`
- caller_count: `0`
- callee_count: `54`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180004640`
- `0x180006b38`
- `0x18000df18`
- `0x18000e1b8`
- `0x18000e210`
- `0x18000e518`
- `0x1800191f0`
- `0x18002a658`
- `0x1800566c8`
- `0x180057368`
- `0x180057a98`
- `0x180057f18`
- `0x180057fa8`
- `0x180057fe4`
- `0x180058200`
- `0x1800598ec`
- `0x180059914`
- `0x180059dbc`
- `0x180059f6c`
- `0x18005a120`
- `0x18005a144`
- `0x18005a308`
- `0x18005a3ec`
- `0x18005bfa8`
- `0x18006f878`
- `0x18006fd1c`
- `0x18006ff64`
- `0x1800703f4`
- `0x180076b78`
- `0x180076bc8`
- `0x180076d64`
- `0x180077130`
- `0x180077160`
- `0x180077244`
- `0x180080900`
- `0x180080980`
- `0x180092358`
- `0x1800b4ba0`
- `0x1800b4be0`
- `0x1800b4cbc`
- `0x1800b4f84`
- `0x1800b54f4`
- `0x1800b5598`
- `0x1800b5c6c`
- `0x1800b69f4`
- `0x1800b6bc4`
- `0x1800b7600`
- `0x1800d76bc`
- `0x1800d76dc`
- `0x1800d7ebc`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800b81d4`
- `ole32!CoCreateInstance` at `0x1800b81d4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b78ff`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b7962`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b78ff`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b7962`

## pseudocode

```c
// Hidden C++ exception states: #wind=36 #try_helpers=1
__int64 __fastcall CMSVidBDATuner::put_Container(CMSVidBDATuner *this, struct IMSVidGraphSegmentContainer *a2)
{
  int v3; // r14d
  int v4; // r12d
  CMSVidBDATuner *v5; // r13
  __int64 v7; // rbx
  unsigned int v8; // ebx
  __int64 v9; // rax
  char IsEqualObject; // bl
  __int64 Graph; // rax
  unsigned __int64 v12; // rdx
  void *(*v13)(void *); // r9
  _QWORD *v14; // r15
  __int64 v15; // rdx
  int v16; // ebx
  __int64 v17; // rdx
  unsigned int v18; // ebx
  struct IUnknown *v19; // r8
  struct IUnknown *v20; // r8
  struct IUnknown **v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rdx
  int v24; // eax
  unsigned int v25; // ebx
  __int64 v26; // rdx
  int v27; // ebx
  __int64 v28; // rdx
  unsigned int v29; // ebx
  __int64 v30; // rcx
  unsigned int v31; // ebx
  __int64 v32; // rdx
  int v33; // ebx
  __int64 v34; // rdx
  unsigned int v35; // ebx
  unsigned int v36; // ebx
  char *v37; // rbx
  __int64 v38; // rdx
  char *v39; // rbx
  __int64 v40; // rdx
  __int64 v41; // rbx
  __int64 (__fastcall *v42)(__int64, _QWORD); // r14
  _QWORD *v43; // rax
  int v44; // ebx
  unsigned int v45; // ebx
  unsigned int v46; // ebx
  unsigned int v47; // ebx
  int v48; // ebx
  __int64 v49; // rdx
  unsigned int v50; // ebx
  char *v51; // rbx
  DSFilter *v52; // rax
  struct IUnknown **v53; // rax
  __int64 v54; // rcx
  __int64 v55; // rax
  bool v56; // bl
  __int64 v57; // rbx
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // rdx
  __int64 v61; // rcx
  __int64 v62; // rax
  bool v63; // bl
  __int64 v64; // rcx
  DSPin *v65; // rax
  const struct DSPin *v66; // rax
  char v67; // bl
  struct DSPin *v68; // rax
  int v69; // ebx
  __int64 v70; // rax
  bool v71; // bl
  __int64 v72; // rcx
  unsigned int v73; // ebx
  char *v74; // rbx
  __int64 v75; // rcx
  __int64 v76; // rax
  __int64 v77; // r8
  __int64 v78; // rax
  __int64 v79; // rcx
  __int64 v80; // rax
  bool v81; // bl
  DSPin *v82; // rax
  const struct DSPin *v83; // rax
  char v84; // bl
  struct DSPin *v85; // rax
  int v86; // ebx
  unsigned int v87; // ebx
  unsigned int v88; // ebx
  unsigned int v89; // ebx
  int v90; // [rsp+48h] [rbp-280h]
  int v91; // [rsp+50h] [rbp-278h]
  void **v92; // [rsp+80h] [rbp-248h] BYREF
  struct IUnknown *v93; // [rsp+88h] [rbp-240h] BYREF
  const unsigned __int16 *v94; // [rsp+90h] [rbp-238h] BYREF
  _BYTE v95[8]; // [rsp+98h] [rbp-230h] BYREF
  void **v96; // [rsp+A0h] [rbp-228h] BYREF
  __int64 v97; // [rsp+A8h] [rbp-220h] BYREF
  __int64 v98; // [rsp+B0h] [rbp-218h] BYREF
  struct IUnknown *ppv; // [rsp+B8h] [rbp-210h] BYREF
  void **v100; // [rsp+C0h] [rbp-208h] BYREF
  _BYTE v101[8]; // [rsp+C8h] [rbp-200h] BYREF
  BSTR bstrString; // [rsp+D0h] [rbp-1F8h] BYREF
  _BYTE v103[8]; // [rsp+D8h] [rbp-1F0h] BYREF
  __int64 v104; // [rsp+E0h] [rbp-1E8h] BYREF
  void **v105; // [rsp+E8h] [rbp-1E0h] BYREF
  struct IUnknown *v106; // [rsp+F0h] [rbp-1D8h] BYREF
  LPVOID v107; // [rsp+F8h] [rbp-1D0h] BYREF
  __int128 v108; // [rsp+100h] [rbp-1C8h] BYREF
  __int64 v109; // [rsp+110h] [rbp-1B8h]
  _BYTE v110[8]; // [rsp+118h] [rbp-1B0h] BYREF
  __int64 v111; // [rsp+120h] [rbp-1A8h]
  _BYTE v112[16]; // [rsp+130h] [rbp-198h] BYREF
  __int64 v113; // [rsp+140h] [rbp-188h]
  __int64 v114; // [rsp+148h] [rbp-180h] BYREF
  _BYTE v115[8]; // [rsp+150h] [rbp-178h] BYREF
  __int64 v116; // [rsp+158h] [rbp-170h]
  void **v117; // [rsp+160h] [rbp-168h] BYREF
  __int64 v118; // [rsp+168h] [rbp-160h] BYREF
  void **v119; // [rsp+170h] [rbp-158h] BYREF
  struct IUnknown *v120; // [rsp+178h] [rbp-150h] BYREF
  void **v121; // [rsp+180h] [rbp-148h] BYREF
  struct IUnknown *v122; // [rsp+188h] [rbp-140h] BYREF
  _BYTE v123[24]; // [rsp+190h] [rbp-138h] BYREF
  _BYTE v124[24]; // [rsp+1A8h] [rbp-120h] BYREF
  void **v125; // [rsp+1C0h] [rbp-108h] BYREF
  _BYTE v126[8]; // [rsp+1C8h] [rbp-100h] BYREF
  void **v127; // [rsp+1D8h] [rbp-F0h] BYREF
  _BYTE v128[8]; // [rsp+1E0h] [rbp-E8h] BYREF
  void **v129; // [rsp+1E8h] [rbp-E0h] BYREF
  _BYTE v130[8]; // [rsp+1F0h] [rbp-D8h] BYREF
  void **v131; // [rsp+1F8h] [rbp-D0h] BYREF
  _BYTE v132[8]; // [rsp+200h] [rbp-C8h] BYREF
  void **v133; // [rsp+208h] [rbp-C0h] BYREF
  _BYTE v134[8]; // [rsp+210h] [rbp-B8h] BYREF
  void **v135; // [rsp+218h] [rbp-B0h] BYREF
  _BYTE v136[8]; // [rsp+220h] [rbp-A8h] BYREF
  void **v137; // [rsp+228h] [rbp-A0h] BYREF
  _BYTE v138[16]; // [rsp+230h] [rbp-98h] BYREF
  _BYTE v139[16]; // [rsp+240h] [rbp-88h] BYREF
  CLSID Buf1; // [rsp+250h] [rbp-78h] BYREF
  struct _GUID v141; // [rsp+260h] [rbp-68h] BYREF
  GUID v142; // [rsp+270h] [rbp-58h]

  v3 = 0;
  v4 = 0;
  LODWORD(bstrString) = 0;
  v5 = (CMSVidBDATuner *)((char *)this - 128);
  if ( !*((_BYTE *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 16) )
    return ATL::CComCoClass<CMSVidBDATuner,&__s_GUID const _GUID_a2e3074e_6c3d_11d3_b653_00c04f79498e>::Error(0xC0040502);
  v7 = *(int *)(*((_QWORD *)this + 1) + 4LL);
  if ( a2 )
  {
    if ( *(_QWORD *)((char *)this + v7 + 32) && *((int *)this + 18) > -1 )
    {
      v9 = MSVideoControl::VWSegmentContainer::VWSegmentContainer((MSVideoControl::VWSegmentContainer *)&v117, a2);
      IsEqualObject = ATL::CComQIPtr<IMSVidGraphSegmentContainer,&__s_GUID const _GUID_3dd2903d_e0aa_11d2_b63a_00c04f79498e>::IsEqualObject(
                        (char *)this + v7 + 32,
                        *(_QWORD *)(v9 + 8));
      v117 = &MSVideoControl::VWSegmentContainer::`vftable';
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v118);
      if ( IsEqualObject )
        return 0;
      else
        return ATL::CComCoClass<CMSVidBDATuner,&__s_GUID const _GUID_a2e3074e_6c3d_11d3_b653_00c04f79498e>::Error(0xC0040526);
    }
    else
    {
      *(_QWORD *)((char *)this + v7 + 32) = a2;
      Graph = MSVideoControl::VWSegmentContainer::GetGraph(
                (char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 24,
                &v117);
      ATL::AtlComPtrAssign(
        (struct IUnknown **)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 48),
        *(struct IUnknown **)(Graph + 8));
      v117 = &Forward_Sequence<ATL::CComQIPtr<IGraphBuilder,&_GUID const IID_IGraphBuilder>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IGraphBuilder,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v118);
      ATL::CComQIPtr<IFilterMapper2,&_GUID const IID_IFilterMapper2>::CComQIPtr<IFilterMapper2,&_GUID const IID_IFilterMapper2>(
        v95,
        *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 48));
      `vector constructor iterator'((GUID2 *)&v141, v12, 2u, v13);
      v141 = GUID_00000000_0000_0000_0000_000000000000;
      v142 = GUID_00000000_0000_0000_0000_000000000000;
      DSFilterMapper::DSFilterMapper((DSFilterMapper *)v110, 0x200000u, 1, 1u, &v141, 0, v90, v91, 1, 0, 0, 0);
      if ( v111 )
      {
        Forward_Sequence<ATL::CComQIPtr<ICreateDevEnum,&_GUID const IID_ICreateDevEnum>,ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,ICreateDevEnum,IEnumMoniker,IMoniker *,std::allocator<DSFilterMoniker>>::begin(
          v110,
          &v125);
        enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(&v125);
      }
      Buf1 = GUID_NULL;
      v94 = WTL::_atltmpPchNil;
      v14 = (_QWORD *)((char *)this + 40);
      if ( *((_QWORD *)this + 5) )
      {
        BDATuningModel::TNTuneRequestHelper<ATL::CComQIPtr<IChannelTuneRequest,&__s_GUID const _GUID_0369b4e0_45b6_11d3_b650_00c04f79498e>,ATL::CComQIPtr<ILocator,&__s_GUID const _GUID_286d7f89_760c_4f89_80c4_66841d2507aa>>::TuningSpace(
          (char *)this + 40,
          &v104);
        bstrString = 0;
        v16 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v104 + 96LL))(v104, &bstrString);
        if ( v16 < 0 )
        {
          ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>::Release(
            (char *)this + 40,
            v15);
          ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>::Release(
            (char *)this + 32,
            v17);
          v18 = CMSVidBDATuner::CleanReturn(v5, v16);
          SysFreeString(bstrString);
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v104);
          WTL::CString::~CString((WTL::CString *)&v94);
          DSFilterMapper::~DSFilterMapper((DSFilterMapper *)v110);
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v95);
          return v18;
        }
        GUID2::operator=(&Buf1, bstrString);
        SysFreeString(bstrString);
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v104);
      }
      v93 = 0;
      v92 = &DSFilter::`vftable';
      if ( !memcmp_0(&Buf1, &GUID_143827ab_f77b_498d_81ca_5a007aec28bf, 0x10u)
        || !memcmp_0(&Buf1, &GUID_b820d87e_e0e3_478f_8a38_4e13f7b3df42, 0x10u)
        || !memcmp_0(&Buf1, &GUID_7728087b_2bb9_4e30_8078_449476e59dbb, 0x10u)
        || !memcmp_0(&Buf1, &GUID_742ef867_09e1_40a3_82d3_9669ba35325f, 0x10u)
        || !memcmp_0(&Buf1, &CLSID_ATSCNetworkProvider, 0x10u)
        || !memcmp_0(&Buf1, &CLSID_DVBSNetworkProvider, 0x10u)
        || !memcmp_0(&Buf1, &CLSID_DVBTNetworkProvider, 0x10u)
        || !memcmp_0(&Buf1, &GUID_95037f6f_3ac7_4452_b6c4_45a9ce9292a2, 0x10u)
        || !memcmp_0(&Buf1, &GUID_b0a4e6a0_6a1a_4b83_bb5b_903e1d90e6b6, 0x10u)
        || !memcmp_0(&Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
      {
        DSFilter::DSFilter((DSFilter *)&v119, &CLSID_NetworkProvider, v19, 1u);
        ATL::AtlComPtrAssign(&v93, v120);
        WTL::CString::operator=((WTL::CString *)&v94, L"Generic Network Provider");
        v119 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
        v21 = &v120;
      }
      else
      {
        DSFilter::DSFilter((DSFilter *)&v121, &Buf1, v19, 1u);
        if ( v122 )
        {
          ATL::AtlComPtrAssign(&v93, v122);
          WTL::CString::operator=((WTL::CString *)&v94, L"Non-Generic Network Provider");
        }
        else
        {
          DSFilter::DSFilter((DSFilter *)&v119, &CLSID_NetworkProvider, v20, 1u);
          ATL::AtlComPtrAssign(&v93, v120);
          WTL::CString::operator=((WTL::CString *)&v94, L"Generic Network Provider");
          v119 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v120);
        }
        v121 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
        v21 = &v122;
      }
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v21);
      if ( v93 )
      {
        v27 = DSGraph::AddFilter(
                (CMSVidBDATuner *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 40),
                (struct DSFilter *)&v92,
                (struct WTL::CString *)&v94);
        if ( v27 >= 0 )
        {
          v30 = *(int *)(*((_QWORD *)this + 1) + 4LL);
          DSGraph::AddMoniker((char *)this + v30 + 40, &v96, (char *)this + v30 + 80);
          if ( v97 )
          {
            v108 = 0;
            v109 = 0;
            v33 = DSGraph::Connect(
                    (int)this + *(_DWORD *)(*((_QWORD *)v5 + 17) + 4LL) + 40,
                    (unsigned int)&v92,
                    (unsigned int)&v96,
                    (unsigned int)&v108,
                    0,
                    1);
            if ( v33 >= 0 )
            {
              v37 = (char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL);
              if ( *((_QWORD *)v37 + 8) == *((_QWORD *)v37 + 9) )
              {
                std::vector<DSFilter>::_Emplace_reallocate<DSFilter>(v37 + 56, *((_QWORD *)v37 + 8), &v92);
              }
              else
              {
                DSFilter::DSFilter(*((DSFilter **)v37 + 8), (const struct DSFilter *)&v92);
                *((_QWORD *)v37 + 8) += 16LL;
              }
              v38 = *((_QWORD *)this + 1);
              *((_DWORD *)this + 18) = ((__int64)(*(_QWORD *)((char *)this + *(int *)(v38 + 4) + 64)
                                                - *(_QWORD *)((char *)this + *(int *)(v38 + 4) + 56)) >> 4)
                                     - 1;
              v39 = (char *)this + *(int *)(v38 + 4);
              if ( *((_QWORD *)v39 + 8) == *((_QWORD *)v39 + 9) )
              {
                std::vector<DSFilter>::_Emplace_reallocate<DSFilter>(v39 + 56, *((_QWORD *)v39 + 8), &v96);
              }
              else
              {
                DSFilter::DSFilter(*((DSFilter **)v39 + 8), (const struct DSFilter *)&v96);
                *((_QWORD *)v39 + 8) += 16LL;
              }
              v40 = *((_QWORD *)this + 1);
              *((_DWORD *)this + 19) = ((__int64)(*(_QWORD *)((char *)this + *(int *)(v40 + 4) + 64)
                                                - *(_QWORD *)((char *)this + *(int *)(v40 + 4) + 56)) >> 4)
                                     - 1;
              std::vector<DSFilter>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<DSFilter>>>,0>(
                *(_DWORD *)(v40 + 4) + (_DWORD)this + 56,
                (unsigned int)&v121,
                *(_QWORD *)((char *)this + *(int *)(v40 + 4) + 64),
                v108,
                *((__int64 *)&v108 + 1));
              std::vector<DSPin>::clear(&v108);
              ATL::CComQIPtr<ITuner,&__s_GUID const _GUID_28c52640_018a_11d3_9d8e_00c04f72d980>::CComQIPtr<ITuner,&__s_GUID const _GUID_28c52640_018a_11d3_9d8e_00c04f72d980>(
                &v98,
                v93);
              v41 = v98;
              if ( v98
                && *v14
                && ((v42 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v98 + 32LL),
                     v43 = (_QWORD *)BDATuningModel::TNTuneRequestHelper<ATL::CComQIPtr<IChannelTuneRequest,&__s_GUID const _GUID_0369b4e0_45b6_11d3_b650_00c04f79498e>,ATL::CComQIPtr<ILocator,&__s_GUID const _GUID_286d7f89_760c_4f89_80c4_66841d2507aa>>::TuningSpace(
                                       (char *)this + 40,
                                       &v107),
                     v44 = v42(v41, *v43),
                     ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v107),
                     v3 = 0,
                     v44 < 0)
                 || (v44 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v98 + 56LL))(v98, *v14), v44 < 0)) )
              {
                v45 = CMSVidBDATuner::CleanReturn(v5, v44);
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v98);
                std::vector<DSFilter>::_Tidy(&v108);
                v96 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v97);
                v92 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v93);
                WTL::CString::~CString((WTL::CString *)&v94);
                DSFilterMapper::~DSFilterMapper((DSFilterMapper *)v110);
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v95);
                return v45;
              }
              else
              {
                ppv = 0;
                CoCreateInstance(
                  &CLSID_MPEG2Demultiplexer,
                  0,
                  0x17u,
                  &GUID_436eee9c_264f_4242_90e1_4e330c107512,
                  (LPVOID *)&ppv);
                if ( ppv )
                {
                  DSFilter::DSFilter((DSFilter *)&v100, ppv);
                  WTL::CString::CString((WTL::CString *)v103, L"MPEG-2 Demultiplexer");
                  if ( (int)DSGraph::AddFilter(
                              (CMSVidBDATuner *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 40),
                              (struct DSFilter *)&v100,
                              (struct WTL::CString *)v103) >= 0 )
                  {
                    v48 = DSGraph::Connect(
                            (int)this + *(_DWORD *)(*((_QWORD *)v5 + 17) + 4LL) + 40,
                            (unsigned int)&v92,
                            (unsigned int)&v100,
                            (unsigned int)&v108,
                            0,
                            1);
                    v49 = *(int *)(*((_QWORD *)this + 1) + 4LL);
                    if ( v48 >= 0 )
                    {
                      v51 = (char *)this + v49;
                      v52 = *(DSFilter **)((char *)this + v49 + 64);
                      if ( v52 == *(DSFilter **)((char *)this + v49 + 72) )
                      {
                        std::vector<DSFilter>::_Emplace_reallocate<DSFilter>(
                          v51 + 56,
                          *(_QWORD *)((char *)this + v49 + 64),
                          &v100);
                      }
                      else
                      {
                        DSFilter::DSFilter(v52, (const struct DSFilter *)&v100);
                        *((_QWORD *)v51 + 8) += 16LL;
                      }
                      if ( !*((_QWORD *)this + 8) )
                      {
                        v53 = (struct IUnknown **)ATL::CComQIPtr<ICreateDevEnum,&_GUID const IID_ICreateDevEnum>::CComQIPtr<ICreateDevEnum,&_GUID const IID_ICreateDevEnum>(&v107);
                        ATL::AtlComPtrAssign((struct IUnknown **)this + 8, *v53);
                        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v107);
                      }
                      DSDevices::DSDevices(v124, (char *)this + 64, &GUID_a2e3074f_6c3d_11d3_b653_00c04f79498e);
                      Forward_Sequence<ATL::CComQIPtr<ICreateDevEnum,&_GUID const IID_ICreateDevEnum>,ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,ICreateDevEnum,IEnumMoniker,IMoniker *,std::allocator<DSFilterMoniker>>::begin(
                        v124,
                        v115);
                      v106 = 0;
                      v105 = &DSFilter::`vftable';
                      while ( 1 )
                      {
                        v55 = Forward_Sequence<ATL::CComQIPtr<ICreateDevEnum,&_GUID const IID_ICreateDevEnum>,ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,ICreateDevEnum,IEnumMoniker,IMoniker *,std::allocator<DSFilterMoniker>>::end(
                                v54,
                                v139);
                        v56 = v116 == *(_QWORD *)(v55 + 8);
                        enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(v139);
                        if ( v56 )
                          break;
                        v57 = *(int *)(*((_QWORD *)this + 1) + 4LL);
                        v58 = enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::operator*(
                                v115,
                                &v121);
                        v59 = DSGraph::AddMoniker((char *)this + v57 + 40, &v127, v58);
                        ATL::AtlComPtrAssign(&v106, *(struct IUnknown **)(v59 + 8));
                        v127 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v128);
                        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v121);
                        if ( v106 )
                        {
                          v118 = 0;
                          v117 = &DSPin::`vftable';
                          v107 = 0;
                          enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>::enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>(
                            v112,
                            &v107,
                            &v117);
                          v60 = Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::begin(
                                  &v100,
                                  v123);
                          enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>::operator=(
                            v112,
                            v60);
                          enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>(v123);
                          while ( 1 )
                          {
                            v62 = Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::end(
                                    v61,
                                    v123);
                            v63 = v113 != *(_QWORD *)(v62 + 16);
                            enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>(v123);
                            if ( !v63 )
                              break;
                            v65 = (DSPin *)enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>::operator*(
                                             v112,
                                             &v131);
                            v4 |= 1u;
                            LODWORD(bstrString) = v4;
                            if ( DSPin::IsConnected(v65)
                              || (v66 = (const struct DSPin *)enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>::operator*(
                                                                v112,
                                                                &v129),
                                  v4 |= 2u,
                                  LODWORD(bstrString) = v4,
                                  v67 = 1,
                                  !IsTransportPin(v66)) )
                            {
                              v67 = 0;
                            }
                            if ( (v4 & 2) != 0 )
                            {
                              v4 &= ~2u;
                              v129 = &Forward_Sequence<ATL::CComQIPtr<IPin,&_GUID const IID_IPin>,ATL::CComQIPtr<IEnumMediaTypes,&_GUID const IID_IEnumMediaTypes>,DSMediaType,IPin,IEnumMediaTypes,_AMMediaType *,std::allocator<DSMediaType>>::`vftable';
                              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v130);
                            }
                            if ( (v4 & 1) != 0 )
                            {
                              v4 &= ~1u;
                              v131 = &Forward_Sequence<ATL::CComQIPtr<IPin,&_GUID const IID_IPin>,ATL::CComQIPtr<IEnumMediaTypes,&_GUID const IID_IEnumMediaTypes>,DSMediaType,IPin,IEnumMediaTypes,_AMMediaType *,std::allocator<DSMediaType>>::`vftable';
                              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v132);
                            }
                            if ( v67 )
                            {
                              v68 = (struct DSPin *)enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>::operator*(
                                                      v112,
                                                      &v133);
                              v69 = DSPin::IntelligentConnect(v68, (struct DSFilter *)&v105, 1);
                              v133 = &Forward_Sequence<ATL::CComQIPtr<IPin,&_GUID const IID_IPin>,ATL::CComQIPtr<IEnumMediaTypes,&_GUID const IID_IEnumMediaTypes>,DSMediaType,IPin,IEnumMediaTypes,_AMMediaType *,std::allocator<DSMediaType>>::`vftable';
                              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v134);
                              if ( v69 >= 0 )
                                break;
                            }
                            enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>::operator++(v112);
                          }
                          v70 = Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::end(
                                  v64,
                                  v123);
                          v71 = v113 == *(_QWORD *)(v70 + 16);
                          enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>(v123);
                          v72 = *(int *)(*((_QWORD *)this + 1) + 4LL);
                          if ( v71 )
                          {
                            if ( !DSGraph::RemoveFilter(
                                    (CMSVidBDATuner *)((char *)this + v72 + 40),
                                    (struct DSFilter *)&v105) )
                            {
                              v73 = CMSVidBDATuner::CleanReturn(v5, -2147418113);
                              enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>(v112);
                              v105 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v106);
                              enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(v115);
                              DSDevices::~DSDevices((DSDevices *)v124);
                              WTL::CString::~CString((WTL::CString *)v103);
                              v100 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v101);
                              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
                              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v98);
                              std::vector<DSFilter>::_Tidy(&v108);
                              v96 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v97);
                              v92 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v93);
                              WTL::CString::~CString((WTL::CString *)&v94);
                              DSFilterMapper::~DSFilterMapper((DSFilterMapper *)v110);
                              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v95);
                              return v73;
                            }
                          }
                          else
                          {
                            v74 = (char *)this + v72;
                            if ( *(_QWORD *)((char *)this + v72 + 64) == *(_QWORD *)((char *)this + v72 + 72) )
                            {
                              std::vector<DSFilter>::_Emplace_reallocate<DSFilter>(
                                v74 + 56,
                                *(_QWORD *)((char *)this + v72 + 64),
                                &v105);
                            }
                            else
                            {
                              DSFilter::DSFilter(
                                *(DSFilter **)((char *)this + v72 + 64),
                                (const struct DSFilter *)&v105);
                              *((_QWORD *)v74 + 8) += 16LL;
                            }
                            v75 = *(int *)(*((_QWORD *)this + 1) + 4LL);
                            *((_DWORD *)this + 20) = ((__int64)(*(_QWORD *)((char *)this + v75 + 64)
                                                              - *(_QWORD *)((char *)this + v75 + 56)) >> 4)
                                                   - 1;
                            v76 = 0;
                            v104 = 0;
                            if ( v106 )
                            {
                              ((void (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v106->lpVtbl->QueryInterface)(
                                v106,
                                &GUID_9b396d40_f380_4e3c_a514_1a82bf6ebfe6,
                                &v104);
                              v76 = v104;
                            }
                            if ( v76 )
                              *((_DWORD *)this + 21) = *((_DWORD *)this + 20);
                            v77 = *(int *)(*((_QWORD *)this + 1) + 4LL);
                            std::vector<DSFilter>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<DSFilter>>>,0>(
                              v77 + (_DWORD)this + 56,
                              (unsigned int)&v119,
                              *(_QWORD *)((char *)this + v77 + 64),
                              v108,
                              *((__int64 *)&v108 + 1));
                            std::vector<DSPin>::clear(&v108);
                            v78 = Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::begin(
                                    &v96,
                                    v123);
                            enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>::operator=(
                              v112,
                              v78);
                            enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>(v123);
                            while ( 1 )
                            {
                              v80 = Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::end(
                                      v79,
                                      v123);
                              v81 = v113 != *(_QWORD *)(v80 + 16);
                              enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>(v123);
                              if ( !v81 )
                                break;
                              v82 = (DSPin *)enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>::operator*(
                                               v112,
                                               &v137);
                              v4 |= 4u;
                              LODWORD(bstrString) = v4;
                              if ( DSPin::IsConnected(v82)
                                || (v83 = (const struct DSPin *)enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>::operator*(
                                                                  v112,
                                                                  &v135),
                                    v4 |= 8u,
                                    LODWORD(bstrString) = v4,
                                    v84 = 1,
                                    !IsTransportPin(v83)) )
                              {
                                v84 = 0;
                              }
                              if ( (v4 & 8) != 0 )
                              {
                                v4 &= ~8u;
                                v135 = &Forward_Sequence<ATL::CComQIPtr<IPin,&_GUID const IID_IPin>,ATL::CComQIPtr<IEnumMediaTypes,&_GUID const IID_IEnumMediaTypes>,DSMediaType,IPin,IEnumMediaTypes,_AMMediaType *,std::allocator<DSMediaType>>::`vftable';
                                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v136);
                              }
                              if ( (v4 & 4) != 0 )
                              {
                                v4 &= ~4u;
                                v137 = &Forward_Sequence<ATL::CComQIPtr<IPin,&_GUID const IID_IPin>,ATL::CComQIPtr<IEnumMediaTypes,&_GUID const IID_IEnumMediaTypes>,DSMediaType,IPin,IEnumMediaTypes,_AMMediaType *,std::allocator<DSMediaType>>::`vftable';
                                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v138);
                              }
                              if ( v84 )
                              {
                                v85 = (struct DSPin *)enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>::operator*(
                                                        v112,
                                                        &v125);
                                v86 = DSPin::IntelligentConnect(v85, (struct DSFilter *)&v105, 1);
                                v125 = &Forward_Sequence<ATL::CComQIPtr<IPin,&_GUID const IID_IPin>,ATL::CComQIPtr<IEnumMediaTypes,&_GUID const IID_IEnumMediaTypes>,DSMediaType,IPin,IEnumMediaTypes,_AMMediaType *,std::allocator<DSMediaType>>::`vftable';
                                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v126);
                                if ( v86 >= 0 )
                                  break;
                              }
                              enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>::operator++(v112);
                            }
                            ++v3;
                            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v104);
                          }
                          enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IEnumPins,IPin *,__int64>(v112);
                        }
                        enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::operator++(v115);
                      }
                      if ( v3 )
                      {
                        if ( (int)MSVideoControl::IBroadcastEventImpl<CMSVidBDATuner>::BroadcastAdvise((char *)this - 40) >= 0 )
                        {
                          ATL::CComQIPtr<IRegisterServiceProvider,&_GUID const IID_IRegisterServiceProvider>::CComQIPtr<IRegisterServiceProvider,&_GUID const IID_IRegisterServiceProvider>(
                            &v114,
                            *(_QWORD *)((char *)v5 + *(int *)(*((_QWORD *)this + 1) + 4LL) + 176));
                          if ( v114
                            && (*(int (__fastcall **)(__int64, GUID *, struct IUnknown *))(*(_QWORD *)v114 + 24LL))(
                                 v114,
                                 &IID_ITuner,
                                 v93) >= 0 )
                          {
                            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v114);
                            v105 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v106);
                            enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(v115);
                            DSDevices::~DSDevices((DSDevices *)v124);
                            WTL::CString::~CString((WTL::CString *)v103);
                            v100 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v101);
                            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
                            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v98);
                            std::vector<DSFilter>::_Tidy(&v108);
                            v96 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v97);
                            v92 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v93);
                            WTL::CString::~CString((WTL::CString *)&v94);
                            DSFilterMapper::~DSFilterMapper((DSFilterMapper *)v110);
                            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v95);
                            return 0;
                          }
                          else
                          {
                            v89 = CMSVidBDATuner::CleanReturn(v5, -2147418113);
                            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v114);
                            v105 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v106);
                            enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(v115);
                            DSDevices::~DSDevices((DSDevices *)v124);
                            WTL::CString::~CString((WTL::CString *)v103);
                            v100 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v101);
                            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
                            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v98);
                            std::vector<DSFilter>::_Tidy(&v108);
                            v96 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v97);
                            v92 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v93);
                            WTL::CString::~CString((WTL::CString *)&v94);
                            DSFilterMapper::~DSFilterMapper((DSFilterMapper *)v110);
                            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v95);
                            return v89;
                          }
                        }
                        else
                        {
                          v88 = CMSVidBDATuner::CleanReturn(v5, -2147418113);
                          v105 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v106);
                          enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(v115);
                          DSDevices::~DSDevices((DSDevices *)v124);
                          WTL::CString::~CString((WTL::CString *)v103);
                          v100 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v101);
                          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
                          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v98);
                          std::vector<DSFilter>::_Tidy(&v108);
                          v96 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v97);
                          v92 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v93);
                          WTL::CString::~CString((WTL::CString *)&v94);
                          DSFilterMapper::~DSFilterMapper((DSFilterMapper *)v110);
                          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v95);
                          return v88;
                        }
                      }
                      else
                      {
                        v87 = CMSVidBDATuner::CleanReturn(v5, -2147467259);
                        v105 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v106);
                        enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(v115);
                        DSDevices::~DSDevices((DSDevices *)v124);
                        WTL::CString::~CString((WTL::CString *)v103);
                        v100 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v101);
                        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
                        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v98);
                        std::vector<DSFilter>::_Tidy(&v108);
                        v96 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v97);
                        v92 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v93);
                        WTL::CString::~CString((WTL::CString *)&v94);
                        DSFilterMapper::~DSFilterMapper((DSFilterMapper *)v110);
                        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v95);
                        return v87;
                      }
                    }
                    else
                    {
                      if ( DSGraph::RemoveFilter((CMSVidBDATuner *)((char *)this + v49 + 40), (struct DSFilter *)&v100) )
                        v50 = CMSVidBDATuner::CleanReturn(v5, v48);
                      else
                        v50 = CMSVidBDATuner::CleanReturn(v5, -2147418113);
                      WTL::CString::~CString((WTL::CString *)v103);
                      v100 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v101);
                      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
                      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v98);
                      std::vector<DSFilter>::_Tidy(&v108);
                      v96 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v97);
                      v92 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v93);
                      WTL::CString::~CString((WTL::CString *)&v94);
                      DSFilterMapper::~DSFilterMapper((DSFilterMapper *)v110);
                      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v95);
                      return v50;
                    }
                  }
                  else
                  {
                    v47 = CMSVidBDATuner::CleanReturn(v5, -2147418113);
                    WTL::CString::~CString((WTL::CString *)v103);
                    v100 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v101);
                    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
                    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v98);
                    std::vector<DSFilter>::_Tidy(&v108);
                    v96 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v97);
                    v92 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v93);
                    WTL::CString::~CString((WTL::CString *)&v94);
                    DSFilterMapper::~DSFilterMapper((DSFilterMapper *)v110);
                    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v95);
                    return v47;
                  }
                }
                else
                {
                  v46 = CMSVidBDATuner::CleanReturn(v5, -2147418113);
                  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
                  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v98);
                  std::vector<DSFilter>::_Tidy(&v108);
                  v96 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v97);
                  v92 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v93);
                  WTL::CString::~CString((WTL::CString *)&v94);
                  DSFilterMapper::~DSFilterMapper((DSFilterMapper *)v110);
                  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v95);
                  return v46;
                }
              }
            }
            else
            {
              ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>::Release(
                (char *)this + 40,
                v32);
              ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>::Release(
                (char *)this + 32,
                v34);
              if ( DSGraph::RemoveFilter(
                     (CMSVidBDATuner *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 40),
                     (struct DSFilter *)&v96) )
              {
                if ( DSGraph::RemoveFilter(
                       (CMSVidBDATuner *)((char *)this + *(int *)(*((_QWORD *)v5 + 17) + 4LL) + 40),
                       (struct DSFilter *)&v92) )
                {
                  v36 = CMSVidBDATuner::CleanReturn(v5, v33);
                }
                else
                {
                  v36 = CMSVidBDATuner::CleanReturn(v5, -2147418113);
                }
                std::vector<DSFilter>::_Tidy(&v108);
                v96 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v97);
                v92 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v93);
                WTL::CString::~CString((WTL::CString *)&v94);
                DSFilterMapper::~DSFilterMapper((DSFilterMapper *)v110);
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v95);
                return v36;
              }
              else
              {
                v35 = CMSVidBDATuner::CleanReturn(v5, -2147418113);
                std::vector<DSFilter>::_Tidy(&v108);
                v96 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v97);
                v92 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v93);
                WTL::CString::~CString((WTL::CString *)&v94);
                DSFilterMapper::~DSFilterMapper((DSFilterMapper *)v110);
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v95);
                return v35;
              }
            }
          }
          else
          {
            v31 = CMSVidBDATuner::CleanReturn(v5, -1073478249);
            v96 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v97);
            v92 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v93);
            WTL::CString::~CString((WTL::CString *)&v94);
            DSFilterMapper::~DSFilterMapper((DSFilterMapper *)v110);
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v95);
            return v31;
          }
        }
        else
        {
          ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>::Release(
            (char *)this + 40,
            v26);
          ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>::Release(
            (char *)this + 32,
            v28);
          v29 = CMSVidBDATuner::CleanReturn(v5, v27);
          v92 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v93);
          WTL::CString::~CString((WTL::CString *)&v94);
          DSFilterMapper::~DSFilterMapper((DSFilterMapper *)v110);
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v95);
          return v29;
        }
      }
      else
      {
        ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>::Release(
          (char *)this + 40,
          v22);
        ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>::Release(
          (char *)this + 32,
          v23);
        v24 = ATL::CComCoClass<CMSVidBDATuner,&__s_GUID const _GUID_a2e3074e_6c3d_11d3_b653_00c04f79498e>::Error(0xC0040515);
        v25 = CMSVidBDATuner::CleanReturn(v5, v24);
        v92 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v93);
        WTL::CString::~CString((WTL::CString *)&v94);
        DSFilterMapper::~DSFilterMapper((DSFilterMapper *)v110);
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v95);
        return v25;
      }
    }
  }
  else
  {
    ATL::CComQIPtr<IRegisterServiceProvider,&_GUID const IID_IRegisterServiceProvider>::CComQIPtr<IRegisterServiceProvider,&_GUID const IID_IRegisterServiceProvider>(
      &v104,
      *(_QWORD *)((char *)this + v7 + 48));
    if ( v104 )
      (*(void (__fastcall **)(__int64, GUID *, _QWORD))(*(_QWORD *)v104 + 24LL))(v104, &IID_ITuner, 0);
    v8 = CMSVidBDATuner::Unload(v5);
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v104);
    return v8;
  }
}

```

## disassembly

```asm
0x1800b7600  mov     [rsp+arg_10], rbx
0x1800b7605  mov     [rsp+arg_18], rsi
0x1800b760a  push    rdi
0x1800b760b  push    r12
0x1800b760d  push    r13
0x1800b760f  push    r14
0x1800b7611  push    r15
0x1800b7613  sub     rsp, 2A0h
0x1800b761a  mov     rax, cs:__security_cookie
0x1800b7621  xor     rax, rsp
0x1800b7624  mov     [rsp+2C8h+var_38], rax
0x1800b762c  mov     rsi, rcx
0x1800b762f  xor     r14d, r14d
0x1800b7632  mov     r12d, r14d
0x1800b7635  mov     dword ptr [rsp+2C8h+bstrString], r14d
0x1800b763d  lea     r13, [rcx-80h]
0x1800b7641  mov     rax, [rcx+8]
0x1800b7645  movsxd  rcx, dword ptr [rax+4]
0x1800b7649  cmp     [rcx+r13+90h], r14b
0x1800b7651  jnz     short loc_1800B766F
0x1800b7653  mov     r9, cs:hInstance
0x1800b765a  mov     ecx, 0C0040502h; dwMessageId
0x1800b765f  mov     r8d, 800401F0h
0x1800b7665  call    ?Error@?$CComCoClass@VCMSVidBDATuner@@$1?_GUID_a2e3074e_6c3d_11d3_b653_00c04f79498e@@3U__s_GUID@@B@ATL@@SAJIAEBU_GUID@@JPEAUHINSTANCE__@@@Z; ATL::CComCoClass<CMSVidBDATuner,&__s_GUID const _GUID_a2e3074e_6c3d_11d3_b653_00c04f79498e>::Error(uint,_GUID const &,long,HINSTANCE__ *)
0x1800b766a  jmp     loc_1800B9194
0x1800b766f  mov     rax, [rsi+8]
0x1800b7673  movsxd  rbx, dword ptr [rax+4]
0x1800b7677  test    rdx, rdx
0x1800b767a  jnz     short loc_1800B76D0
0x1800b767c  mov     rdx, [rsi+rbx+30h]
0x1800b7681  lea     rcx, [rsp+2C8h+var_1E8]
0x1800b7689  call    ??0?$CComQIPtr@UIRegisterServiceProvider@@$1?IID_IRegisterServiceProvider@@3U_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IRegisterServiceProvider,&_GUID const IID_IRegisterServiceProvider>::CComQIPtr<IRegisterServiceProvider,&_GUID const IID_IRegisterServiceProvider>(IUnknown *)
0x1800b768e  nop
0x1800b768f  mov     rcx, [rsp+2C8h+var_1E8]
0x1800b7697  test    rcx, rcx
0x1800b769a  jz      short loc_1800B76B2
0x1800b769c  mov     rax, [rcx]
0x1800b769f  xor     r8d, r8d
0x1800b76a2  lea     rdx, IID_ITuner
0x1800b76a9  mov     rax, [rax+18h]
0x1800b76ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b76b2  mov     rcx, r13; this
0x1800b76b5  call    ?Unload@CMSVidBDATuner@@QEAAJXZ; CMSVidBDATuner::Unload(void)
0x1800b76ba  mov     ebx, eax
0x1800b76bc  lea     rcx, [rsp+2C8h+var_1E8]
0x1800b76c4  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800b76c9  mov     eax, ebx
0x1800b76cb  jmp     loc_1800B9194
0x1800b76d0  cmp     [rsi+rbx+20h], r14
0x1800b76d5  jz      short loc_1800B7740
0x1800b76d7  cmp     dword ptr [rsi+48h], 0FFFFFFFFh
0x1800b76db  jle     short loc_1800B7740
0x1800b76dd  lea     rcx, [rsp+2C8h+var_168]; this
0x1800b76e5  call    ??0VWSegmentContainer@MSVideoControl@@QEAA@PEAUIMSVidGraphSegmentContainer@@@Z; MSVideoControl::VWSegmentContainer::VWSegmentContainer(IMSVidGraphSegmentContainer *)
0x1800b76ea  nop
0x1800b76eb  lea     rcx, [rsi+20h]
0x1800b76ef  add     rcx, rbx
0x1800b76f2  mov     rdx, [rax+8]
0x1800b76f6  call    ?IsEqualObject@?$CComQIPtr@UIMSVidGraphSegmentContainer@@$1?_GUID_3dd2903d_e0aa_11d2_b63a_00c04f79498e@@3U__s_GUID@@B@ATL@@QEAA_NPEAUIUnknown@@@Z; ATL::CComQIPtr<IMSVidGraphSegmentContainer,&__s_GUID const _GUID_3dd2903d_e0aa_11d2_b63a_00c04f79498e>::IsEqualObject(IUnknown *)
0x1800b76fb  mov     bl, al
0x1800b76fd  lea     rax, ??_7VWSegmentContainer@MSVideoControl@@6B@; const MSVideoControl::VWSegmentContainer::`vftable'
0x1800b7704  mov     [rsp+2C8h+var_168], rax
0x1800b770c  lea     rcx, [rsp+2C8h+var_160]
0x1800b7714  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800b7719  test    bl, bl
0x1800b771b  jnz     short loc_1800B7739
0x1800b771d  mov     r9, cs:hInstance
0x1800b7724  mov     ecx, 0C0040526h; dwMessageId
0x1800b7729  mov     r8d, 800401F1h
0x1800b772f  call    ?Error@?$CComCoClass@VCMSVidBDATuner@@$1?_GUID_a2e3074e_6c3d_11d3_b653_00c04f79498e@@3U__s_GUID@@B@ATL@@SAJIAEBU_GUID@@JPEAUHINSTANCE__@@@Z; ATL::CComCoClass<CMSVidBDATuner,&__s_GUID const _GUID_a2e3074e_6c3d_11d3_b653_00c04f79498e>::Error(uint,_GUID const &,long,HINSTANCE__ *)
0x1800b7734  jmp     loc_1800B9194
0x1800b7739  xor     eax, eax
0x1800b773b  jmp     loc_1800B9194
0x1800b7740  mov     [rbx+rsi+20h], rdx
0x1800b7745  mov     rax, [rsi+8]
0x1800b7749  movsxd  rcx, dword ptr [rax+4]
0x1800b774d  add     rcx, 18h
0x1800b7751  add     rcx, rsi
0x1800b7754  lea     rdx, [rsp+2C8h+var_168]
0x1800b775c  call    ?GetGraph@VWSegmentContainer@MSVideoControl@@QEBA?AVDSGraph@@XZ; MSVideoControl::VWSegmentContainer::GetGraph(void)
0x1800b7761  nop
0x1800b7762  mov     rcx, [rsi+8]
0x1800b7766  movsxd  rcx, dword ptr [rcx+4]
0x1800b776a  add     rcx, 30h ; '0'
0x1800b776e  add     rcx, rsi; struct IUnknown **
0x1800b7771  mov     rdx, [rax+8]; struct IUnknown *
0x1800b7775  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800b777a  nop
0x1800b777b  lea     rax, ??_7?$Forward_Sequence@V?$CComQIPtr@UIGraphBuilder@@$1?IID_IGraphBuilder@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumFilters@@$1?IID_IEnumFilters@@3U_GUID@@B@2@VDSFilter@@UIGraphBuilder@@UIEnumFilters@@PEAUIBaseFilter@@V?$allocator@VDSFilter@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IGraphBuilder,&_GUID const IID_IGraphBuilder>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IGraphBuilder,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable'
0x1800b7782  mov     [rsp+2C8h+var_168], rax
0x1800b778a  lea     rcx, [rsp+2C8h+var_160]
0x1800b7792  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800b7797  mov     rax, [rsi+8]
0x1800b779b  movsxd  rdx, dword ptr [rax+4]
0x1800b779f  mov     rdx, [rdx+rsi+30h]
0x1800b77a4  lea     rcx, [rsp+2C8h+var_230]
0x1800b77ac  call    ??0?$CComQIPtr@UIFilterMapper2@@$1?IID_IFilterMapper2@@3U_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IFilterMapper2,&_GUID const IID_IFilterMapper2>::CComQIPtr<IFilterMapper2,&_GUID const IID_IFilterMapper2>(IUnknown *)
0x1800b77b1  nop
0x1800b77b2  mov     r8d, 2; unsigned __int64
0x1800b77b8  lea     rcx, [rsp+2C8h+var_68]; this
0x1800b77c0  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1800b77c5  mov     rcx, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800b77cc  mov     qword ptr [rsp+2C8h+var_68.Data1], rcx
0x1800b77d4  mov     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x1800b77db  mov     qword ptr [rsp+2C8h+var_68.Data4], rax
0x1800b77e3  mov     [rsp+2C8h+var_58], rcx
0x1800b77eb  mov     [rsp+2C8h+var_50], rax
0x1800b77f3  mov     [rsp+2C8h+var_258], r14; struct REGPINMEDIUM *
0x1800b77f8  mov     [rsp+2C8h+var_260], r14; struct _GUID *
0x1800b77fd  mov     [rsp+2C8h+var_268], r14d; unsigned int
0x1800b7802  mov     ebx, 1
0x1800b7807  mov     [rsp+2C8h+var_270], ebx; int
0x1800b780b  mov     [rsp+2C8h+var_288], r14; struct REGPINMEDIUM *
0x1800b7810  lea     rax, [rsp+2C8h+var_68]
0x1800b7818  mov     [rsp+2C8h+var_290], rax; struct _GUID *
0x1800b781d  mov     [rsp+2C8h+var_298], ebx; unsigned int
0x1800b7821  mov     [rsp+2C8h+var_2A0], ebx; int
0x1800b7825  mov     dword ptr [rsp+2C8h+ppv], 200000h; unsigned int
0x1800b782d  lea     r9d, [rbx+1Fh]
0x1800b7831  lea     rdx, [rsp+2C8h+var_230]
0x1800b7839  lea     rcx, [rsp+2C8h+var_1B0]; this
0x1800b7841  call    ??0DSFilterMapper@@QEAA@AEAV?$CComQIPtr@UIFilterMapper2@@$1?IID_IFilterMapper2@@3U_GUID@@B@ATL@@KHKHKPEBU_GUID@@PEBUREGPINMEDIUM@@1HHK121@Z; DSFilterMapper::DSFilterMapper(ATL::CComQIPtr<IFilterMapper2,&_GUID const IID_IFilterMapper2> &,ulong,int,ulong,int,ulong,_GUID const *,REGPINMEDIUM const *,_GUID const *,int,int,ulong,_GUID const *,REGPINMEDIUM const *,_GUID const *)
0x1800b7846  nop
0x1800b7847  cmp     [rsp+2C8h+var_1A8], r14
0x1800b784f  jz      short loc_1800B7873
0x1800b7851  lea     rdx, [rsp+2C8h+var_108]
0x1800b7859  lea     rcx, [rsp+2C8h+var_1B0]
0x1800b7861  call    ?begin@?$Forward_Sequence@V?$CComQIPtr@UICreateDevEnum@@$1?IID_ICreateDevEnum@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@2@VDSFilterMoniker@@UICreateDevEnum@@UIEnumMoniker@@PEAUIMoniker@@V?$allocator@VDSFilterMoniker@@@std@@@@QEAA?AV?$enumerator_iterator@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@ATL@@VDSFilterMoniker@@UIEnumMoniker@@PEAUIMoniker@@_J@@XZ; Forward_Sequence<ATL::CComQIPtr<ICreateDevEnum,&_GUID const IID_ICreateDevEnum>,ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,ICreateDevEnum,IEnumMoniker,IMoniker *,std::allocator<DSFilterMoniker>>::begin(void)
0x1800b7866  lea     rcx, [rsp+2C8h+var_108]
0x1800b786e  call    ??1?$enumerator_iterator@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@ATL@@VDSFilterMoniker@@UIEnumMoniker@@PEAUIMoniker@@_J@@QEAA@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(void)
0x1800b7873  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800b787a  movdqu  [rsp+2C8h+Buf1], xmm0
0x1800b7883  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x1800b788a  mov     [rsp+2C8h+var_238], rax
0x1800b7892  lea     r15, [rsi+28h]
0x1800b7896  cmp     [r15], r14
0x1800b7899  jz      loc_1800B797B
0x1800b789f  lea     rdx, [rsp+2C8h+var_1E8]
0x1800b78a7  mov     rcx, r15
0x1800b78aa  call    ?TuningSpace@?$TNTuneRequestHelper@V?$CComQIPtr@UIChannelTuneRequest@@$1?_GUID_0369b4e0_45b6_11d3_b650_00c04f79498e@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UILocator@@$1?_GUID_286d7f89_760c_4f89_80c4_66841d2507aa@@3U__s_GUID@@B@2@@BDATuningModel@@QEAA?AV?$CComQIPtr@UITuningSpace@@$1?_GUID_061c6e30_e622_11d2_9493_00c04f72d980@@3U__s_GUID@@B@ATL@@XZ; BDATuningModel::TNTuneRequestHelper<ATL::CComQIPtr<IChannelTuneRequest,&__s_GUID const _GUID_0369b4e0_45b6_11d3_b650_00c04f79498e>,ATL::CComQIPtr<ILocator,&__s_GUID const _GUID_286d7f89_760c_4f89_80c4_66841d2507aa>>::TuningSpace(void)
0x1800b78af  nop
0x1800b78b0  mov     [rsp+2C8h+bstrString], r14
0x1800b78b8  mov     rcx, [rsp+2C8h+var_1E8]
0x1800b78c0  mov     rax, [rcx]
0x1800b78c3  lea     rdx, [rsp+2C8h+bstrString]
0x1800b78cb  mov     rax, [rax+60h]
0x1800b78cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b78d4  mov     ebx, eax
0x1800b78d6  test    eax, eax
0x1800b78d8  jns     short loc_1800B7944
0x1800b78da  mov     rcx, r15
0x1800b78dd  call    ?Release@?$CComQIPtr@UIVMRImageCompositor@@$1?_GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82@@3U__s_GUID@@B@ATL@@QEAAXXZ; ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>::Release(void)
0x1800b78e2  lea     rcx, [rsi+20h]
0x1800b78e6  call    ?Release@?$CComQIPtr@UIVMRImageCompositor@@$1?_GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82@@3U__s_GUID@@B@ATL@@QEAAXXZ; ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>::Release(void)
0x1800b78eb  mov     edx, ebx; int
0x1800b78ed  mov     rcx, r13; this
0x1800b78f0  call    ?CleanReturn@CMSVidBDATuner@@QEAAJJ@Z; CMSVidBDATuner::CleanReturn(long)
0x1800b78f5  mov     ebx, eax
0x1800b78f7  mov     rcx, [rsp+2C8h+bstrString]; bstrString
0x1800b78ff  call    cs:__imp_SysFreeString
0x1800b7905  nop
0x1800b7906  lea     rcx, [rsp+2C8h+var_1E8]
0x1800b790e  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800b7913  nop
0x1800b7914  lea     rcx, [rsp+2C8h+var_238]; this
0x1800b791c  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x1800b7921  nop
0x1800b7922  lea     rcx, [rsp+2C8h+var_1B0]; this
0x1800b792a  call    ??1DSFilterMapper@@UEAA@XZ; DSFilterMapper::~DSFilterMapper(void)
0x1800b792f  nop
0x1800b7930  lea     rcx, [rsp+2C8h+var_230]
0x1800b7938  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800b793d  mov     eax, ebx
0x1800b793f  jmp     loc_1800B9194
0x1800b7944  mov     rdx, [rsp+2C8h+bstrString]; unsigned __int16 *
0x1800b794c  lea     rcx, [rsp+2C8h+Buf1]; pclsid
0x1800b7954  call    ??4GUID2@@QEAAAEAV0@QEAG@Z; GUID2::operator=(ushort * const)
0x1800b7959  nop
0x1800b795a  mov     rcx, [rsp+2C8h+bstrString]; bstrString
0x1800b7962  call    cs:__imp_SysFreeString
0x1800b7968  nop
0x1800b7969  lea     rcx, [rsp+2C8h+var_1E8]
0x1800b7971  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800b7976  mov     ebx, 1
0x1800b797b  mov     [rsp+2C8h+var_240], r14
0x1800b7983  lea     rax, ??_7DSFilter@@6B@; const DSFilter::`vftable'
0x1800b798a  mov     [rsp+2C8h+var_248], rax
0x1800b7992  mov     edi, 10h
0x1800b7997  mov     r8d, edi; Size
0x1800b799a  lea     rdx, _GUID_143827ab_f77b_498d_81ca_5a007aec28bf; Buf2
0x1800b79a1  lea     rcx, [rsp+2C8h+Buf1]; Buf1
0x1800b79a9  call    memcmp_0
0x1800b79ae  test    eax, eax
0x1800b79b0  jz      loc_1800B7B8E
0x1800b79b6  mov     r8d, edi; Size
0x1800b79b9  lea     rdx, _GUID_b820d87e_e0e3_478f_8a38_4e13f7b3df42; Buf2
0x1800b79c0  lea     rcx, [rsp+2C8h+Buf1]; Buf1
0x1800b79c8  call    memcmp_0
0x1800b79cd  test    eax, eax
0x1800b79cf  jz      loc_1800B7B8E
0x1800b79d5  mov     r8d, edi; Size
0x1800b79d8  lea     rdx, _GUID_7728087b_2bb9_4e30_8078_449476e59dbb; Buf2
0x1800b79df  lea     rcx, [rsp+2C8h+Buf1]; Buf1
0x1800b79e7  call    memcmp_0
0x1800b79ec  test    eax, eax
0x1800b79ee  jz      loc_1800B7B8E
0x1800b79f4  mov     r8d, edi; Size
0x1800b79f7  lea     rdx, _GUID_742ef867_09e1_40a3_82d3_9669ba35325f; Buf2
0x1800b79fe  lea     rcx, [rsp+2C8h+Buf1]; Buf1
0x1800b7a06  call    memcmp_0
0x1800b7a0b  test    eax, eax
0x1800b7a0d  jz      loc_1800B7B8E
0x1800b7a13  mov     r8d, edi; Size
0x1800b7a16  lea     rdx, CLSID_ATSCNetworkProvider; Buf2
0x1800b7a1d  lea     rcx, [rsp+2C8h+Buf1]; Buf1
0x1800b7a25  call    memcmp_0
0x1800b7a2a  test    eax, eax
0x1800b7a2c  jz      loc_1800B7B8E
0x1800b7a32  mov     r8d, edi; Size
0x1800b7a35  lea     rdx, CLSID_DVBSNetworkProvider; Buf2
0x1800b7a3c  lea     rcx, [rsp+2C8h+Buf1]; Buf1
0x1800b7a44  call    memcmp_0
0x1800b7a49  test    eax, eax
0x1800b7a4b  jz      loc_1800B7B8E
0x1800b7a51  mov     r8d, edi; Size
0x1800b7a54  lea     rdx, CLSID_DVBTNetworkProvider; Buf2
0x1800b7a5b  lea     rcx, [rsp+2C8h+Buf1]; Buf1
0x1800b7a63  call    memcmp_0
0x1800b7a68  test    eax, eax
0x1800b7a6a  jz      loc_1800B7B8E
0x1800b7a70  mov     r8d, edi; Size
0x1800b7a73  lea     rdx, _GUID_95037f6f_3ac7_4452_b6c4_45a9ce9292a2; Buf2
0x1800b7a7a  lea     rcx, [rsp+2C8h+Buf1]; Buf1
0x1800b7a82  call    memcmp_0
0x1800b7a87  test    eax, eax
0x1800b7a89  jz      loc_1800B7B8E
0x1800b7a8f  mov     r8d, edi; Size
0x1800b7a92  lea     rdx, _GUID_b0a4e6a0_6a1a_4b83_bb5b_903e1d90e6b6; Buf2
0x1800b7a99  lea     rcx, [rsp+2C8h+Buf1]; Buf1
0x1800b7aa1  call    memcmp_0
0x1800b7aa6  test    eax, eax
0x1800b7aa8  jz      loc_1800B7B8E
0x1800b7aae  mov     r8d, edi; Size
0x1800b7ab1  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x1800b7ab8  lea     rcx, [rsp+2C8h+Buf1]; Buf1
0x1800b7ac0  call    memcmp_0
0x1800b7ac5  test    eax, eax
0x1800b7ac7  jz      loc_1800B7B8E
0x1800b7acd  mov     r9d, ebx; unsigned int
0x1800b7ad0  lea     rdx, [rsp+2C8h+Buf1]; struct _GUID *
0x1800b7ad8  lea     rcx, [rsp+2C8h+var_148]; this
0x1800b7ae0  call    ??0DSFilter@@QEAA@AEBU_GUID@@PEAUIUnknown@@K@Z; DSFilter::DSFilter(_GUID const &,IUnknown *,ulong)
0x1800b7ae5  nop
0x1800b7ae6  mov     rdx, [rsp+2C8h+var_140]; struct IUnknown *
0x1800b7aee  test    rdx, rdx
0x1800b7af1  jz      short loc_1800B7B1D
0x1800b7af3  lea     rcx, [rsp+2C8h+var_240]; struct IUnknown **
0x1800b7afb  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800b7b00  lea     rdx, aNonGenericNetw; "Non-Generic Network Provider"
0x1800b7b07  lea     rcx, [rsp+2C8h+var_238]; this
0x1800b7b0f  call    ??4CString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator=(ushort const *)
0x1800b7b14  lea     rdi, ??_7?$Forward_Sequence@V?$CComQIPtr@UIBaseFilter@@$1?IID_IBaseFilter@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumPins@@$1?IID_IEnumPins@@3U_GUID@@B@2@VDSPin@@UIBaseFilter@@UIEnumPins@@PEAUIPin@@V?$allocator@VDSPin@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable'
0x1800b7b1b  jmp     short loc_1800B7B7C
0x1800b7b1d  mov     r9d, ebx; unsigned int
0x1800b7b20  lea     rdx, CLSID_NetworkProvider; struct _GUID *
0x1800b7b27  lea     rcx, [rsp+2C8h+var_158]; this
0x1800b7b2f  call    ??0DSFilter@@QEAA@AEBU_GUID@@PEAUIUnknown@@K@Z; DSFilter::DSFilter(_GUID const &,IUnknown *,ulong)
0x1800b7b34  nop
0x1800b7b35  mov     rdx, [rsp+2C8h+var_150]; struct IUnknown *
0x1800b7b3d  lea     rcx, [rsp+2C8h+var_240]; struct IUnknown **
0x1800b7b45  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800b7b4a  lea     rdx, aGenericNetwork; "Generic Network Provider"
0x1800b7b51  lea     rcx, [rsp+2C8h+var_238]; this
0x1800b7b59  call    ??4CString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator=(ushort const *)
0x1800b7b5e  nop
0x1800b7b5f  lea     rdi, ??_7?$Forward_Sequence@V?$CComQIPtr@UIBaseFilter@@$1?IID_IBaseFilter@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumPins@@$1?IID_IEnumPins@@3U_GUID@@B@2@VDSPin@@UIBaseFilter@@UIEnumPins@@PEAUIPin@@V?$allocator@VDSPin@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable'
0x1800b7b66  mov     [rsp+2C8h+var_158], rdi
0x1800b7b6e  lea     rcx, [rsp+2C8h+var_150]
0x1800b7b76  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800b7b7b  nop
0x1800b7b7c  mov     [rsp+2C8h+var_148], rdi
0x1800b7b84  lea     rcx, [rsp+2C8h+var_140]
0x1800b7b8c  jmp     short loc_1800B7BE7
0x1800b7b8e  mov     r9d, ebx; unsigned int
0x1800b7b91  lea     rdx, CLSID_NetworkProvider; struct _GUID *
0x1800b7b98  lea     rcx, [rsp+2C8h+var_158]; this
0x1800b7ba0  call    ??0DSFilter@@QEAA@AEBU_GUID@@PEAUIUnknown@@K@Z; DSFilter::DSFilter(_GUID const &,IUnknown *,ulong)
0x1800b7ba5  nop
0x1800b7ba6  mov     rdx, [rsp+2C8h+var_150]; struct IUnknown *
0x1800b7bae  lea     rcx, [rsp+2C8h+var_240]; struct IUnknown **
0x1800b7bb6  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800b7bbb  lea     rdx, aGenericNetwork; "Generic Network Provider"
0x1800b7bc2  lea     rcx, [rsp+2C8h+var_238]; this
0x1800b7bca  call    ??4CString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator=(ushort const *)
0x1800b7bcf  nop
0x1800b7bd0  lea     rdi, ??_7?$Forward_Sequence@V?$CComQIPtr@UIBaseFilter@@$1?IID_IBaseFilter@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumPins@@$1?IID_IEnumPins@@3U_GUID@@B@2@VDSPin@@UIBaseFilter@@UIEnumPins@@PEAUIPin@@V?$allocator@VDSPin@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable'
0x1800b7bd7  mov     [rsp+2C8h+var_158], rdi
0x1800b7bdf  lea     rcx, [rsp+2C8h+var_150]
0x1800b7be7  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800b7bec  cmp     [rsp+2C8h+var_240], r14
  ... truncated ...
```
