# CVidCtl::RunGraph(void)

- ea: `0x1800d00a4`
- end: `0x1800d0e73`
- name: `?RunGraph@CVidCtl@@IEAAJXZ`
- size: `3535`
- prototype: `__int64 __fastcall(struct IUnknown **this)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800cffe0`

## callees

- `0x180006b38`
- `0x18000ff74`
- `0x180030cb4`
- `0x180057544`
- `0x18005817c`
- `0x1800581ac`
- `0x1800581d8`
- `0x18006fa0c`
- `0x1800738ac`
- `0x1800886c8`
- `0x1800c2158`
- `0x1800c2840`
- `0x1800c2b84`
- `0x1800c2cac`
- `0x1800c34d4`
- `0x1800c36f8`
- `0x1800c3828`
- `0x1800c3854`
- `0x1800c4134`
- `0x1800c8cd0`
- `0x1800ccd80`
- `0x1800cda70`
- `0x1800d00a4`
- `0x1800d32d8`
- `0x1800d3394`
- `0x1800ed80c`
- `0x1800f8010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800d0538`
- `OLEAUT32!__imp_VariantClear` at `0x1800d06a1`
- `OLEAUT32!__imp_VariantClear` at `0x1800d0add`
- `OLEAUT32!__imp_VariantClear` at `0x1800d0c45`
- `OLEAUT32!__imp_VariantClear` at `0x1800d0538`
- `OLEAUT32!__imp_VariantClear` at `0x1800d06a1`
- `OLEAUT32!__imp_VariantClear` at `0x1800d0add`
- `OLEAUT32!__imp_VariantClear` at `0x1800d0c45`

## string_xrefs

- `0x1800d0dee`: `PreRun Composites Failed`
- `0x1800d0d6a`: `Composites PostRun Failed`

## pseudocode

```c
__int64 __fastcall CVidCtl::RunGraph(struct IUnknown **this)
{
  unsigned int v2; // edx
  unsigned __int64 v3; // r8
  __int64 v4; // r9
  __int64 result; // rax
  int v6; // edx
  CPerfInfo *v7; // rcx
  CPerfInfo *v8; // rcx
  unsigned int v9; // ebx
  int v10; // ebx
  CPerfInfo *v11; // rcx
  unsigned int v12; // edx
  unsigned __int64 v13; // r8
  __int64 v14; // r9
  unsigned int v15; // ebx
  int v16; // edi
  CPerfInfo *v17; // rcx
  CPerfInfo *v18; // rcx
  __int64 v19; // rax
  unsigned int v20; // ebx
  struct IMSVidGraphSegment *v21; // rdx
  __int64 v22; // rax
  unsigned int v23; // ebx
  struct IUnknown *v24; // rdx
  __int64 v25; // rax
  unsigned int v26; // ebx
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rax
  char v30; // bl
  const struct ATL::CComVariant *v31; // rax
  __int64 v32; // rax
  unsigned int v33; // ebx
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rax
  char v37; // bl
  const struct ATL::CComVariant *v38; // rdx
  __int64 v39; // rcx
  unsigned int v40; // ebx
  const struct MSVideoControl::VWGraphSegment *i; // rbx
  CPerfInfo *v42; // rcx
  CPerfInfo *v43; // rcx
  unsigned int v44; // ebx
  int v45; // ebx
  CPerfInfo *v46; // rcx
  unsigned int v47; // ebx
  CPerfInfo *v48; // rcx
  __int64 v49; // rax
  unsigned int v50; // ebx
  struct IMSVidGraphSegment *v51; // rdx
  __int64 v52; // rax
  unsigned int v53; // ebx
  struct IUnknown *v54; // rdx
  __int64 v55; // rax
  unsigned int v56; // ebx
  __int64 v57; // rax
  __int64 v58; // rcx
  __int64 v59; // rax
  char v60; // bl
  const struct ATL::CComVariant *v61; // rax
  __int64 v62; // rax
  unsigned int v63; // ebx
  __int64 v64; // rdx
  __int64 v65; // rcx
  __int64 v66; // rax
  char v67; // bl
  const struct ATL::CComVariant *v68; // rdx
  __int64 v69; // rcx
  unsigned int v70; // ebx
  const struct MSVideoControl::VWGraphSegment *j; // rbx
  CPerfInfo *v72; // rcx
  unsigned int v73; // edx
  unsigned __int64 v74; // r8
  __int64 v75; // r9
  CPerfInfo *v76; // rcx
  __int64 v77; // rcx
  unsigned int v78; // edi
  __int64 v79; // rcx
  unsigned int v80; // edi
  int *v81; // [rsp+20h] [rbp-D8h]
  int *v82; // [rsp+20h] [rbp-D8h]
  void **v83; // [rsp+30h] [rbp-C8h] BYREF
  _BYTE v84[8]; // [rsp+38h] [rbp-C0h] BYREF
  VARIANTARG v85; // [rsp+40h] [rbp-B8h] BYREF
  _BYTE v86[8]; // [rsp+60h] [rbp-98h] BYREF
  _BYTE v87[24]; // [rsp+68h] [rbp-90h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-78h] BYREF
  unsigned int v89; // [rsp+A0h] [rbp-58h] BYREF
  ComException *v90; // [rsp+A8h] [rbp-50h] BYREF
  std::bad_alloc *v91; // [rsp+B0h] [rbp-48h] BYREF
  std::exception *v92; // [rsp+B8h] [rbp-40h] BYREF
  char *v93; // [rsp+100h] [rbp+8h] BYREF
  __int64 v94; // [rsp+108h] [rbp+10h] BYREF
  __int64 v95; // [rsp+110h] [rbp+18h] BYREF
  char v96; // [rsp+118h] [rbp+20h] BYREF

  CPerfInfo::SetMark((CPerfInfo *)this, "CVidCtl::RunGraph() -- entry");
  try
  {
    if ( this[85] && this[71] )
    {
      v93 = (char *)(this + 61);
      *((_BYTE *)this + 488) = 1;
      CVidCtl::OnMediaEvent((CVidCtl *)this, v2, v3, v4, v81);
      if ( DSGraph::IsPlaying((DSGraph *)(this + 70)) )
      {
        CGRLocker::~CGRLocker((CGRLocker *)&v93);
        result = 0;
      }
      else if ( DSGraph::IsPaused((DSGraph *)(this + 70)) && *((_DWORD *)this + 138) == 1 )
      {
        ATL::CComQIPtr<IMediaControl,&_GUID const IID_IMediaControl>::CComQIPtr<IMediaControl,&_GUID const IID_IMediaControl>(
          &v94,
          this[71]);
        if ( v94 )
        {
          CPerfInfo::SetMark(v8, "CVidCtl::RunGraph() -- calling IMediaControl::Run()");
          v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v94 + 56LL))(v94);
          CPerfInfo::SetMark(v11, "CVidCtl::RunGraph() -- done calling IMediaControl::Run()");
          if ( v10 >= 0 )
          {
            CVidCtl::OnMediaEvent((CVidCtl *)this, v12, v13, v14, v82);
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v94);
            CGRLocker::~CGRLocker((CGRLocker *)&v93);
            result = 0;
          }
          else
          {
            CVidCtlTrace::Trace((CVidCtlTrace *)&gCVidCtlTrace, 5u, "CVidCtl::RunGraph", "IMediaControl::Run() Failed");
            v15 = ATL::CComCoClass<CVidCtl,&_GUID const CLSID_MSVidCtl>::Error(0xC0040524);
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v94);
            CGRLocker::~CGRLocker((CGRLocker *)&v93);
            result = v15;
          }
        }
        else
        {
          v9 = ATL::CComCoClass<CVidCtl,&_GUID const CLSID_MSVidCtl>::Error(0xC0040513);
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v94);
          CGRLocker::~CGRLocker((CGRLocker *)&v93);
          result = v9;
        }
      }
      else if ( *((_BYTE *)this + 889)
             && (CPerfInfo::SetMark(v7, "CVidCtl::RunGraph() -- pre BuildGraph"),
                 v16 = CVidCtl::BuildGraph((CVidCtl *)this),
                 CPerfInfo::SetMark(v17, "CVidCtl::RunGraph() -- post BuildGraph"),
                 v16 < 0) )
      {
        CVidCtlTrace::Trace((CVidCtlTrace *)&gCVidCtlTrace, 5u, "CVidCtl::RunGraph", "BuildGraph Failed");
        CGRLocker::~CGRLocker((CGRLocker *)&v93);
        result = (unsigned int)v16;
      }
      else
      {
        DSGraph::GetState((DSGraph *)(this + 70), v6);
        CPerfInfo::SetMark(v18, "CVidCtl::RunGraph() -- before calling PreRun() methods");
        v19 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v83, this[85]);
        v20 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v19 + 8) + 104LL))(*(_QWORD *)(v19 + 8));
        v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84);
        if ( (int)(v20 + 0x80000000) < 0 || v20 == -2147467263 )
        {
          v21 = (struct IMSVidGraphSegment *)this[88];
          if ( !v21
            || (v22 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v83, v21),
                v23 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v22 + 8) + 104LL))(*(_QWORD *)(v22 + 8)),
                v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable',
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84),
                ((v23 + 0x80000000) & 0x80000000) != 0)
            || v23 == -2147467263 )
          {
            v24 = this[89];
            if ( !v24
              || (v25 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v83, v24),
                  v26 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v25 + 8) + 104LL))(*(_QWORD *)(v25 + 8)),
                  v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable',
                  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84),
                  ((v26 + 0x80000000) & 0x80000000) != 0)
              || v26 == -2147467263 )
            {
              memset(&v85, 0, sizeof(v85));
              v95 = 0;
              enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(
                v86,
                &v95,
                &v85);
              v27 = Forward_Sequence<ATL::CComQIPtr<IMSVidInputDevices,&__s_GUID const _GUID_c5702cd1_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidInputDevices,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::begin(
                      this + 86,
                      &pvarg);
              enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator=(
                v86,
                v27);
              enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&pvarg);
              while ( 1 )
              {
                v29 = Forward_Sequence<ATL::CComQIPtr<IMSVidFeatures,&__s_GUID const _GUID_c5702cd5_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidFeatures,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::end(
                        v28,
                        &pvarg);
                v30 = ATL::CComVariant::operator==(v87, v29 + 8);
                enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&pvarg);
                if ( v30 )
                  break;
                v31 = (const struct ATL::CComVariant *)enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator*(
                                                         v86,
                                                         &pvarg);
                v32 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v83, v31);
                v33 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v32 + 8) + 104LL))(*(_QWORD *)(v32 + 8));
                v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84);
                if ( pvarg.vt == 4095 )
                  pvarg.vt = 8;
                VariantClear(&pvarg);
                if ( ((v33 + 0x80000000) & 0x80000000) == 0 && v33 != -2147467263 )
                {
                  CVidCtlTrace::Trace((CVidCtlTrace *)&gCVidCtlTrace, 5u, "CVidCtl::RunGraph", "PreRun Output Failed");
                  enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v86);
                  CGRLocker::~CGRLocker((CGRLocker *)&v93);
                  return v33;
                }
                enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator++(v86);
              }
              enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v86);
              if ( this[91] )
              {
                memset(&pvarg, 0, sizeof(pvarg));
                v95 = 0;
                enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(
                  v86,
                  &v95,
                  &pvarg);
                v34 = Forward_Sequence<ATL::CComQIPtr<IMSVidInputDevices,&__s_GUID const _GUID_c5702cd1_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidInputDevices,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::begin(
                        this + 90,
                        &v85);
                enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator=(
                  v86,
                  v34);
                enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&v85);
                while ( 1 )
                {
                  v36 = Forward_Sequence<ATL::CComQIPtr<IMSVidFeatures,&__s_GUID const _GUID_c5702cd5_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidFeatures,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::end(
                          v35,
                          &v85);
                  v37 = ATL::CComVariant::operator==(v87, v36 + 8);
                  enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&v85);
                  if ( v37 )
                    break;
                  v38 = (const struct ATL::CComVariant *)enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator*(
                                                           v86,
                                                           &v85);
                  v39 = *(_QWORD *)(MSVideoControl::VWGraphSegment::VWGraphSegment(
                                      (MSVideoControl::VWGraphSegment *)&v83,
                                      v38)
                                  + 8);
                  v40 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 104LL))(v39);
                  v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
                  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84);
                  if ( v85.vt == 4095 )
                    v85.vt = 8;
                  VariantClear(&v85);
                  if ( ((v40 + 0x80000000) & 0x80000000) == 0 && v40 != -2147467263 )
                  {
                    CVidCtlTrace::Trace(
                      (CVidCtlTrace *)&gCVidCtlTrace,
                      5u,
                      "CVidCtl::RunGraph",
                      "Feature PreRun Failed");
                    enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v86);
                    CGRLocker::~CGRLocker((CGRLocker *)&v93);
                    return v40;
                  }
                  enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator++(v86);
                }
                enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v86);
              }
              for ( i = *(const struct MSVideoControl::VWGraphSegment **)std::_Tree<std::_Tmap_traits<ATL::CComBSTR,unsigned long,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,unsigned long>>,0>>::end(
                                                                           this + 92,
                                                                           &v95);
                    i != *(const struct MSVideoControl::VWGraphSegment **)std::vector<ATL::CComBSTR>::end(
                                                                            this + 92,
                                                                            &v96);
                    i = (const struct MSVideoControl::VWGraphSegment *)((char *)i + 16) )
              {
                v79 = *(_QWORD *)(MSVideoControl::VWGraphSegment::VWGraphSegment(
                                    (MSVideoControl::VWGraphSegment *)&v83,
                                    i)
                                + 8);
                v80 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v79 + 104LL))(v79);
                v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84);
                if ( (int)(v80 + 0x80000000) >= 0 && v80 != -2147467263 )
                {
                  CVidCtlTrace::Trace(
                    (CVidCtlTrace *)&gCVidCtlTrace,
                    5u,
                    "CVidCtl::RunGraph",
                    "PreRun Composites Failed");
                  CGRLocker::~CGRLocker((CGRLocker *)&v93);
                  return v80;
                }
              }
              CPerfInfo::SetMark(v42, "CVidCtl::RunGraph() -- done with PreRun() methods");
              ((void (__fastcall *)(char *))this[22][16].lpVtbl)((char *)this + 176);
              ATL::CComQIPtr<IMediaControl,&_GUID const IID_IMediaControl>::CComQIPtr<IMediaControl,&_GUID const IID_IMediaControl>(
                &v94,
                this[71]);
              if ( v94 )
              {
                CPerfInfo::SetMark(v43, "CVidCtl::RunGraph() -- calling IMediaControl::Run()");
                v45 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v94 + 56LL))(v94);
                CPerfInfo::SetMark(v46, "CVidCtl::RunGraph() -- done calling IMediaControl::Run()");
                if ( v45 >= 0 )
                {
                  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v94);
                  CPerfInfo::SetMark(v48, "CVidCtl::RunGraph() -- about to call PostRun() methods");
                  v49 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v83, this[85]);
                  v50 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v49 + 8) + 112LL))(*(_QWORD *)(v49 + 8));
                  v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
                  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84);
                  if ( (int)(v50 + 0x80000000) < 0 || v50 == -2147467263 )
                  {
                    v51 = (struct IMSVidGraphSegment *)this[88];
                    if ( !v51
                      || (v52 = MSVideoControl::VWGraphSegment::VWGraphSegment(
                                  (MSVideoControl::VWGraphSegment *)&v83,
                                  v51),
                          v53 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v52 + 8) + 112LL))(*(_QWORD *)(v52 + 8)),
                          v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable',
                          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84),
                          (int)(v53 + 0x80000000) < 0)
                      || v53 == -2147467263 )
                    {
                      v54 = this[89];
                      if ( !v54
                        || (v55 = MSVideoControl::VWGraphSegment::VWGraphSegment(
                                    (MSVideoControl::VWGraphSegment *)&v83,
                                    v54),
                            v56 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v55 + 8) + 112LL))(*(_QWORD *)(v55 + 8)),
                            v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable',
                            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84),
                            (int)(v56 + 0x80000000) < 0)
                        || v56 == -2147467263 )
                      {
                        memset(&pvarg, 0, sizeof(pvarg));
                        v94 = 0;
                        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(
                          v86,
                          &v94,
                          &pvarg);
                        v57 = Forward_Sequence<ATL::CComQIPtr<IMSVidInputDevices,&__s_GUID const _GUID_c5702cd1_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidInputDevices,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::begin(
                                this + 86,
                                &v85);
                        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator=(
                          v86,
                          v57);
                        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&v85);
                        while ( 1 )
                        {
                          v59 = Forward_Sequence<ATL::CComQIPtr<IMSVidFeatures,&__s_GUID const _GUID_c5702cd5_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidFeatures,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::end(
                                  v58,
                                  &v85);
                          v60 = ATL::CComVariant::operator==(v87, v59 + 8);
                          enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&v85);
                          if ( v60 )
                            break;
                          v61 = (const struct ATL::CComVariant *)enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator*(
                                                                   v86,
                                                                   &v85);
                          v62 = MSVideoControl::VWGraphSegment::VWGraphSegment(
                                  (MSVideoControl::VWGraphSegment *)&v83,
                                  v61);
                          v63 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v62 + 8) + 112LL))(*(_QWORD *)(v62 + 8));
                          v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
                          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84);
                          if ( v85.vt == 4095 )
                            v85.vt = 8;
                          VariantClear(&v85);
                          if ( (int)(v63 + 0x80000000) >= 0 && v63 != -2147467263 )
                          {
                            CVidCtlTrace::Trace(
                              (CVidCtlTrace *)&gCVidCtlTrace,
                              5u,
                              "CVidCtl::RunGraph",
                              "Output Devices PostRun Failed");
                            enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v86);
                            CGRLocker::~CGRLocker((CGRLocker *)&v93);
                            return v63;
                          }
                          enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator++(v86);
                        }
                        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v86);
                        if ( this[91] )
                        {
                          memset(&pvarg, 0, sizeof(pvarg));
                          v94 = 0;
                          enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(
                            v86,
                            &v94,
                            &pvarg);
                          v64 = Forward_Sequence<ATL::CComQIPtr<IMSVidInputDevices,&__s_GUID const _GUID_c5702cd1_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidInputDevices,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::begin(
                                  this + 90,
                                  &v85);
                          enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator=(
                            v86,
                            v64);
                          enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&v85);
                          while ( 1 )
                          {
                            v66 = Forward_Sequence<ATL::CComQIPtr<IMSVidFeatures,&__s_GUID const _GUID_c5702cd5_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidFeatures,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::end(
                                    v65,
                                    &v85);
                            v67 = ATL::CComVariant::operator==(v87, v66 + 8);
                            enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&v85);
                            if ( v67 )
                              break;
                            v68 = (const struct ATL::CComVariant *)enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator*(
                                                                     v86,
                                                                     &v85);
                            v69 = *(_QWORD *)(MSVideoControl::VWGraphSegment::VWGraphSegment(
                                                (MSVideoControl::VWGraphSegment *)&v83,
                                                v68)
                                            + 8);
                            v70 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v69 + 112LL))(v69);
                            v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
                            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84);
                            if ( v85.vt == 4095 )
                              v85.vt = 8;
                            VariantClear(&v85);
                            if ( (int)(v70 + 0x80000000) >= 0 && v70 != -2147467263 )
                            {
                              CVidCtlTrace::Trace(
                                (CVidCtlTrace *)&gCVidCtlTrace,
                                5u,
                                "CVidCtl::RunGraph",
                                "Feature PostRun Failed");
                              enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v86);
                              CGRLocker::~CGRLocker((CGRLocker *)&v93);
                              return v70;
                            }
                            enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator++(v86);
                          }
                          enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v86);
                        }
                        for ( j = *(const struct MSVideoControl::VWGraphSegment **)std::_Tree<std::_Tmap_traits<ATL::CComBSTR,unsigned long,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,unsigned long>>,0>>::end(
                                                                                     this + 92,
                                                                                     &v94);
                              ;
                              j = (const struct MSVideoControl::VWGraphSegment *)((char *)j + 16) )
                        {
                          if ( j == *(const struct MSVideoControl::VWGraphSegment **)std::vector<ATL::CComBSTR>::end(
                                                                                       this + 92,
                                                                                       &v95) )
                          {
                            CPerfInfo::SetMark(v72, "CVidCtl::RunGraph() -- done calling PostRun() methods");
                            ((void (__fastcall *)(char *))this[22][16].lpVtbl)((char *)this + 176);
                            CVidCtl::OnMediaEvent((CVidCtl *)this, v73, v74, v75, v82);
                            CPerfInfo::SetMark(v76, "CVidCtl::RunGraph() -- exit");
                            CGRLocker::~CGRLocker((CGRLocker *)&v93);
                            return 0;
                          }
                          v77 = *(_QWORD *)(MSVideoControl::VWGraphSegment::VWGraphSegment(
                                              (MSVideoControl::VWGraphSegment *)&v83,
                                              j)
                                          + 8);
                          v78 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v77 + 112LL))(v77);
                          v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
                          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84);
                          if ( (int)(v78 + 0x80000000) >= 0 && v78 != -2147467263 )
                            break;
                        }
                        CVidCtlTrace::Trace(
                          (CVidCtlTrace *)&gCVidCtlTrace,
                          5u,
                          "CVidCtl::RunGraph",
                          "Composites PostRun Failed");
                        CGRLocker::~CGRLocker((CGRLocker *)&v93);
                        result = v78;
                      }
                      else
                      {
                        CVidCtlTrace::Trace(
                          (CVidCtlTrace *)&gCVidCtlTrace,
                          5u,
                          "CVidCtl::RunGraph",
                          "AudioRenderer PostRun Failed");
                        CGRLocker::~CGRLocker((CGRLocker *)&v93);
                        result = v56;
                      }
                    }
                    else
                    {
                      CVidCtlTrace::Trace(
                        (CVidCtlTrace *)&gCVidCtlTrace,
                        5u,
                        "CVidCtl::RunGraph",
                        "Video Renderer PostRun Failed");
                      CGRLocker::~CGRLocker((CGRLocker *)&v93);
                      result = v53;
                    }
                  }
                  else
                  {
                    CVidCtlTrace::Trace((CVidCtlTrace *)&gCVidCtlTrace, 5u, "CVidCtl::RunGraph", "Input PostRun Failed");
                    CGRLocker::~CGRLocker((CGRLocker *)&v93);
                    result = v50;
                  }
                }
                else
                {
                  CVidCtlTrace::Trace(
                    (CVidCtlTrace *)&gCVidCtlTrace,
                    5u,
                    "CVidCtl::RunGraph",
                    "IMediaControl::Run() Failed");
                  v47 = ATL::CComCoClass<CVidCtl,&_GUID const CLSID_MSVidCtl>::Error(0xC0040524);
                  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v94);
                  CGRLocker::~CGRLocker((CGRLocker *)&v93);
                  result = v47;
                }
              }
              else
              {
                v44 = ATL::CComCoClass<CVidCtl,&_GUID const CLSID_MSVidCtl>::Error(0xC0040513);
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v94);
                CGRLocker::~CGRLocker((CGRLocker *)&v93);
                result = v44;
              }
            }
            else
            {
              CVidCtlTrace::Trace(
                (CVidCtlTrace *)&gCVidCtlTrace,
                5u,
                "CVidCtl::RunGraph",
                "PreRun Audio Renderer Failed");
              CGRLocker::~CGRLocker((CGRLocker *)&v93);
              result = v26;
            }
          }
          else
          {
            CVidCtlTrace::Trace((CVidCtlTrace *)&gCVidCtlTrace, 5u, "CVidCtl::RunGraph", "PreRun Video Renderer Failed");
            CGRLocker::~CGRLocker((CGRLocker *)&v93);
            result = v23;
          }
        }
        else
        {
          CVidCtlTrace::Trace((CVidCtlTrace *)&gCVidCtlTrace, 5u, "CVidCtl::RunGraph", "PreRun Input Failed");
          CGRLocker::~CGRLocker((CGRLocker *)&v93);
          result = v20;
        }
      }
    }
    else
    {
      result = ATL::CComCoClass<CVidCtl,&_GUID const CLSID_MSVidCtl>::Error(0xC0040502);
    }
  }
  catch ( long v89 )
  {
    return v89;
  }
  catch ( ComException *v90 )
  {
    return *(unsigned int *)v90;
  }
  catch ( std::bad_alloc *v91 )
  {
    return 2147942414LL;
  }
  catch ( std::exception *v92 )
  {
    return 2147549183LL;
  }
  if ( this[85] && this[71] )
  {
    v93 = (char *)(this + 61);
    *((_BYTE *)this + 488) = 1;
    CVidCtl::OnMediaEvent((CVidCtl *)this, v2, v3, v4, v81);
    if ( DSGraph::IsPlaying((DSGraph *)(this + 70)) )
    {
      CGRLocker::~CGRLocker((CGRLocker *)&v93);
      result = 0;
    }
    else if ( DSGraph::IsPaused((DSGraph *)(this + 70)) && *((_DWORD *)this + 138) == 1 )
    {
      ATL::CComQIPtr<IMediaControl,&_GUID const IID_IMediaControl>::CComQIPtr<IMediaControl,&_GUID const IID_IMediaControl>(
        &v94,
        this[71]);
      if ( v94 )
      {
        CPerfInfo::SetMark(v8, "CVidCtl::RunGraph() -- calling IMediaControl::Run()");
        v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v94 + 56LL))(v94);
        CPerfInfo::SetMark(v11, "CVidCtl::RunGraph() -- done calling IMediaControl::Run()");
        if ( v10 >= 0 )
        {
          CVidCtl::OnMediaEvent((CVidCtl *)this, v12, v13, v14, v82);
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v94);
          CGRLocker::~CGRLocker((CGRLocker *)&v93);
          result = 0;
        }
        else
        {
          CVidCtlTrace::Trace((CVidCtlTrace *)&gCVidCtlTrace, 5u, "CVidCtl::RunGraph", "IMediaControl::Run() Failed");
          v15 = ATL::CComCoClass<CVidCtl,&_GUID const CLSID_MSVidCtl>::Error(0xC0040524);
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v94);
          CGRLocker::~CGRLocker((CGRLocker *)&v93);
          result = v15;
        }
      }
      else
      {
        v9 = ATL::CComCoClass<CVidCtl,&_GUID const CLSID_MSVidCtl>::Error(0xC0040513);
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v94);
        CGRLocker::~CGRLocker((CGRLocker *)&v93);
        result = v9;
      }
    }
    else if ( *((_BYTE *)this + 889)
           && (CPerfInfo::SetMark(v7, "CVidCtl::RunGraph() -- pre BuildGraph"),
               v16 = CVidCtl::BuildGraph((CVidCtl *)this),
               CPerfInfo::SetMark(v17, "CVidCtl::RunGraph() -- post BuildGraph"),
               v16 < 0) )
    {
      CVidCtlTrace::Trace((CVidCtlTrace *)&gCVidCtlTrace, 5u, "CVidCtl::RunGraph", "BuildGraph Failed");
      CGRLocker::~CGRLocker((CGRLocker *)&v93);
      result = (unsigned int)v16;
    }
    else
    {
      DSGraph::GetState((DSGraph *)(this + 70), v6);
      CPerfInfo::SetMark(v18, "CVidCtl::RunGraph() -- before calling PreRun() methods");
      v19 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v83, this[85]);
      v20 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v19 + 8) + 104LL))(*(_QWORD *)(v19 + 8));
      v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84);
      if ( (int)(v20 + 0x80000000) < 0 || v20 == -2147467263 )
      {
        v21 = (struct IMSVidGraphSegment *)this[88];
        if ( !v21
          || (v22 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v83, v21),
              v23 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v22 + 8) + 104LL))(*(_QWORD *)(v22 + 8)),
              v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable',
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84),
              ((v23 + 0x80000000) & 0x80000000) != 0)
          || v23 == -2147467263 )
        {
          v24 = this[89];
          if ( !v24
            || (v25 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v83, v24),
                v26 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v25 + 8) + 104LL))(*(_QWORD *)(v25 + 8)),
                v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable',
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84),
                ((v26 + 0x80000000) & 0x80000000) != 0)
            || v26 == -2147467263 )
          {
            memset(&v85, 0, sizeof(v85));
            v95 = 0;
            enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(
              v86,
              &v95,
              &v85);
            v27 = Forward_Sequence<ATL::CComQIPtr<IMSVidInputDevices,&__s_GUID const _GUID_c5702cd1_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidInputDevices,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::begin(
                    this + 86,
                    &pvarg);
            enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator=(
              v86,
              v27);
            enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&pvarg);
            while ( 1 )
            {
              v29 = Forward_Sequence<ATL::CComQIPtr<IMSVidFeatures,&__s_GUID const _GUID_c5702cd5_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidFeatures,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::end(
                      v28,
                      &pvarg);
              v30 = ATL::CComVariant::operator==(v87, v29 + 8);
              enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&pvarg);
              if ( v30 )
                break;
              v31 = (const struct ATL::CComVariant *)enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator*(
                                                       v86,
                                                       &pvarg);
              v32 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v83, v31);
              v33 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v32 + 8) + 104LL))(*(_QWORD *)(v32 + 8));
              v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84);
              if ( pvarg.vt == 4095 )
                pvarg.vt = 8;
              VariantClear(&pvarg);
              if ( ((v33 + 0x80000000) & 0x80000000) == 0 && v33 != -2147467263 )
              {
                CVidCtlTrace::Trace((CVidCtlTrace *)&gCVidCtlTrace, 5u, "CVidCtl::RunGraph", "PreRun Output Failed");
                enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v86);
                CGRLocker::~CGRLocker((CGRLocker *)&v93);
                return v33;
              }
              enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator++(v86);
            }
            enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v86);
            if ( this[91] )
            {
              memset(&pvarg, 0, sizeof(pvarg));
              v95 = 0;
              enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(
                v86,
                &v95,
                &pvarg);
              v34 = Forward_Sequence<ATL::CComQIPtr<IMSVidInputDevices,&__s_GUID const _GUID_c5702cd1_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidInputDevices,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::begin(
                      this + 90,
                      &v85);
              enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator=(
                v86,
                v34);
              enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&v85);
              while ( 1 )
              {
                v36 = Forward_Sequence<ATL::CComQIPtr<IMSVidFeatures,&__s_GUID const _GUID_c5702cd5_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidFeatures,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::end(
                        v35,
                        &v85);
                v37 = ATL::CComVariant::operator==(v87, v36 + 8);
                enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&v85);
                if ( v37 )
                  break;
                v38 = (const struct ATL::CComVariant *)enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator*(
                                                         v86,
                                                         &v85);
                v39 = *(_QWORD *)(MSVideoControl::VWGraphSegment::VWGraphSegment(
                                    (MSVideoControl::VWGraphSegment *)&v83,
                                    v38)
                                + 8);
                v40 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 104LL))(v39);
                v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84);
                if ( v85.vt == 4095 )
                  v85.vt = 8;
                VariantClear(&v85);
                if ( ((v40 + 0x80000000) & 0x80000000) == 0 && v40 != -2147467263 )
                {
                  CVidCtlTrace::Trace((CVidCtlTrace *)&gCVidCtlTrace, 5u, "CVidCtl::RunGraph", "Feature PreRun Failed");
                  enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v86);
                  CGRLocker::~CGRLocker((CGRLocker *)&v93);
                  return v40;
                }
                enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator++(v86);
              }
              enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v86);
            }
            for ( i = *(const struct MSVideoControl::VWGraphSegment **)std::_Tree<std::_Tmap_traits<ATL::CComBSTR,unsigned long,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,unsigned long>>,0>>::end(
                                                                         this + 92,
                                                                         &v95);
                  i != *(const struct MSVideoControl::VWGraphSegment **)std::vector<ATL::CComBSTR>::end(this + 92, &v96);
                  i = (const struct MSVideoControl::VWGraphSegment *)((char *)i + 16) )
            {
              v79 = *(_QWORD *)(MSVideoControl::VWGraphSegment::VWGraphSegment(
                                  (MSVideoControl::VWGraphSegment *)&v83,
                                  i)
                              + 8);
              v80 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v79 + 104LL))(v79);
              v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84);
              if ( (int)(v80 + 0x80000000) >= 0 && v80 != -2147467263 )
              {
                CVidCtlTrace::Trace((CVidCtlTrace *)&gCVidCtlTrace, 5u, "CVidCtl::RunGraph", "PreRun Composites Failed");
                CGRLocker::~CGRLocker((CGRLocker *)&v93);
                return v80;
              }
            }
            CPerfInfo::SetMark(v42, "CVidCtl::RunGraph() -- done with PreRun() methods");
            ((void (__fastcall *)(char *))this[22][16].lpVtbl)((char *)this + 176);
            ATL::CComQIPtr<IMediaControl,&_GUID const IID_IMediaControl>::CComQIPtr<IMediaControl,&_GUID const IID_IMediaControl>(
              &v94,
              this[71]);
            if ( v94 )
            {
              CPerfInfo::SetMark(v43, "CVidCtl::RunGraph() -- calling IMediaControl::Run()");
              v45 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v94 + 56LL))(v94);
              CPerfInfo::SetMark(v46, "CVidCtl::RunGraph() -- done calling IMediaControl::Run()");
              if ( v45 >= 0 )
              {
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v94);
                CPerfInfo::SetMark(v48, "CVidCtl::RunGraph() -- about to call PostRun() methods");
                v49 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v83, this[85]);
                v50 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v49 + 8) + 112LL))(*(_QWORD *)(v49 + 8));
                v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84);
                if ( (int)(v50 + 0x80000000) < 0 || v50 == -2147467263 )
                {
                  v51 = (struct IMSVidGraphSegment *)this[88];
                  if ( !v51
                    || (v52 = MSVideoControl::VWGraphSegment::VWGraphSegment(
                                (MSVideoControl::VWGraphSegment *)&v83,
                                v51),
                        v53 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v52 + 8) + 112LL))(*(_QWORD *)(v52 + 8)),
                        v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable',
                        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84),
                        (int)(v53 + 0x80000000) < 0)
                    || v53 == -2147467263 )
                  {
                    v54 = this[89];
                    if ( !v54
                      || (v55 = MSVideoControl::VWGraphSegment::VWGraphSegment(
                                  (MSVideoControl::VWGraphSegment *)&v83,
                                  v54),
                          v56 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v55 + 8) + 112LL))(*(_QWORD *)(v55 + 8)),
                          v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable',
                          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84),
                          (int)(v56 + 0x80000000) < 0)
                      || v56 == -2147467263 )
                    {
                      memset(&pvarg, 0, sizeof(pvarg));
                      v94 = 0;
                      enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(
                        v86,
                        &v94,
                        &pvarg);
                      v57 = Forward_Sequence<ATL::CComQIPtr<IMSVidInputDevices,&__s_GUID const _GUID_c5702cd1_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidInputDevices,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::begin(
                              this + 86,
                              &v85);
                      enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator=(
                        v86,
                        v57);
                      enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&v85);
                      while ( 1 )
                      {
                        v59 = Forward_Sequence<ATL::CComQIPtr<IMSVidFeatures,&__s_GUID const _GUID_c5702cd5_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidFeatures,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::end(
                                v58,
                                &v85);
                        v60 = ATL::CComVariant::operator==(v87, v59 + 8);
                        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&v85);
                        if ( v60 )
                          break;
                        v61 = (const struct ATL::CComVariant *)enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator*(
                                                                 v86,
                                                                 &v85);
                        v62 = MSVideoControl::VWGraphSegment::VWGraphSegment(
                                (MSVideoControl::VWGraphSegment *)&v83,
                                v61);
                        v63 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v62 + 8) + 112LL))(*(_QWORD *)(v62 + 8));
                        v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
                        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84);
                        if ( v85.vt == 4095 )
                          v85.vt = 8;
                        VariantClear(&v85);
                        if ( (int)(v63 + 0x80000000) >= 0 && v63 != -2147467263 )
                        {
                          CVidCtlTrace::Trace(
                            (CVidCtlTrace *)&gCVidCtlTrace,
                            5u,
                            "CVidCtl::RunGraph",
                            "Output Devices PostRun Failed");
                          enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v86);
                          CGRLocker::~CGRLocker((CGRLocker *)&v93);
                          return v63;
                        }
                        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator++(v86);
                      }
                      enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v86);
                      if ( this[91] )
                      {
                        memset(&pvarg, 0, sizeof(pvarg));
                        v94 = 0;
                        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(
                          v86,
                          &v94,
                          &pvarg);
                        v64 = Forward_Sequence<ATL::CComQIPtr<IMSVidInputDevices,&__s_GUID const _GUID_c5702cd1_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidInputDevices,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::begin(
                                this + 90,
                                &v85);
                        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator=(
                          v86,
                          v64);
                        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&v85);
                        while ( 1 )
                        {
                          v66 = Forward_Sequence<ATL::CComQIPtr<IMSVidFeatures,&__s_GUID const _GUID_c5702cd5_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidFeatures,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::end(
                                  v65,
                                  &v85);
                          v67 = ATL::CComVariant::operator==(v87, v66 + 8);
                          enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&v85);
                          if ( v67 )
                            break;
                          v68 = (const struct ATL::CComVariant *)enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator*(
                                                                   v86,
                                                                   &v85);
                          v69 = *(_QWORD *)(MSVideoControl::VWGraphSegment::VWGraphSegment(
                                              (MSVideoControl::VWGraphSegment *)&v83,
                                              v68)
                                          + 8);
                          v70 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v69 + 112LL))(v69);
                          v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
                          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84);
                          if ( v85.vt == 4095 )
                            v85.vt = 8;
                          VariantClear(&v85);
                          if ( (int)(v70 + 0x80000000) >= 0 && v70 != -2147467263 )
                          {
                            CVidCtlTrace::Trace(
                              (CVidCtlTrace *)&gCVidCtlTrace,
                              5u,
                              "CVidCtl::RunGraph",
                              "Feature PostRun Failed");
                            enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v86);
                            CGRLocker::~CGRLocker((CGRLocker *)&v93);
                            return v70;
                          }
                          enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator++(v86);
                        }
                        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v86);
                      }
                      for ( j = *(const struct MSVideoControl::VWGraphSegment **)std::_Tree<std::_Tmap_traits<ATL::CComBSTR,unsigned long,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,unsigned long>>,0>>::end(
                                                                                   this + 92,
                                                                                   &v94);
                            ;
                            j = (const struct MSVideoControl::VWGraphSegment *)((char *)j + 16) )
                      {
                        if ( j == *(const struct MSVideoControl::VWGraphSegment **)std::vector<ATL::CComBSTR>::end(
                                                                                     this + 92,
                                                                                     &v95) )
                        {
                          CPerfInfo::SetMark(v72, "CVidCtl::RunGraph() -- done calling PostRun() methods");
                          ((void (__fastcall *)(char *))this[22][16].lpVtbl)((char *)this + 176);
                          CVidCtl::OnMediaEvent((CVidCtl *)this, v73, v74, v75, v82);
                          CPerfInfo::SetMark(v76, "CVidCtl::RunGraph() -- exit");
                          CGRLocker::~CGRLocker((CGRLocker *)&v93);
                          return 0;
                        }
                        v77 = *(_QWORD *)(MSVideoControl::VWGraphSegment::VWGraphSegment(
                                            (MSVideoControl::VWGraphSegment *)&v83,
                                            j)
                                        + 8);
                        v78 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v77 + 112LL))(v77);
                        v83 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
                        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v84);
                        if ( (int)(v78 + 0x80000000) >= 0 && v78 != -2147467263 )
                          break;
                      }
                      CVidCtlTrace::Trace(
                        (CVidCtlTrace *)&gCVidCtlTrace,
                        5u,
                        "CVidCtl::RunGraph",
                        "Composites PostRun Failed");
                      CGRLocker::~CGRLocker((CGRLocker *)&v93);
                      result = v78;
                    }
                    else
                    {
                      CVidCtlTrace::Trace(
                        (CVidCtlTrace *)&gCVidCtlTrace,
                        5u,
                        "CVidCtl::RunGraph",
                        "AudioRenderer PostRun Failed");
                      CGRLocker::~CGRLocker((CGRLocker *)&v93);
                      result = v56;
                    }
                  }
                  else
                  {
                    CVidCtlTrace::Trace(
                      (CVidCtlTrace *)&gCVidCtlTrace,
                      5u,
                      "CVidCtl::RunGraph",
                      "Video Renderer PostRun Failed");
                    CGRLocker::~CGRLocker((CGRLocker *)&v93);
                    result = v53;
                  }
                }
                else
                {
                  CVidCtlTrace::Trace((CVidCtlTrace *)&gCVidCtlTrace, 5u, "CVidCtl::RunGraph", "Input PostRun Failed");
                  CGRLocker::~CGRLocker((CGRLocker *)&v93);
                  result = v50;
                }
              }
              else
              {
                CVidCtlTrace::Trace(
                  (CVidCtlTrace *)&gCVidCtlTrace,
                  5u,
                  "CVidCtl::RunGraph",
                  "IMediaControl::Run() Failed");
                v47 = ATL::CComCoClass<CVidCtl,&_GUID const CLSID_MSVidCtl>::Error(0xC0040524);
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v94);
                CGRLocker::~CGRLocker((CGRLocker *)&v93);
                result = v47;
              }
            }
            else
            {
              v44 = ATL::CComCoClass<CVidCtl,&_GUID const CLSID_MSVidCtl>::Error(0xC0040513);
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v94);
              CGRLocker::~CGRLocker((CGRLocker *)&v93);
              result = v44;
            }
          }
          else
          {
            CVidCtlTrace::Trace((CVidCtlTrace *)&gCVidCtlTrace, 5u, "CVidCtl::RunGraph", "PreRun Audio Renderer Failed");
            CGRLocker::~CGRLocker((CGRLocker *)&v93);
            result = v26;
          }
        }
        else
        {
          CVidCtlTrace::Trace((CVidCtlTrace *)&gCVidCtlTrace, 5u, "CVidCtl::RunGraph", "PreRun Video Renderer Failed");
          CGRLocker::~CGRLocker((CGRLocker *)&v93);
          result = v23;
        }
      }
      else
      {
        CVidCtlTrace::Trace((CVidCtlTrace *)&gCVidCtlTrace, 5u, "CVidCtl::RunGraph", "PreRun Input Failed");
        CGRLocker::~CGRLocker((CGRLocker *)&v93);
        result = v20;
      }
    }
  }
  else
  {
    result = ATL::CComCoClass<CVidCtl,&_GUID const CLSID_MSVidCtl>::Error(0xC0040502);
  }
}

```

## disassembly

```asm
0x1800d00a4  push    rbx
0x1800d00a6  push    rsi
0x1800d00a7  push    rdi
0x1800d00a8  push    r12
0x1800d00aa  push    r13
0x1800d00ac  push    r14
0x1800d00ae  push    r15
0x1800d00b0  sub     rsp, 0C0h
0x1800d00b7  mov     rsi, rcx
0x1800d00ba  lea     rdx, aCvidctlRungrap; "CVidCtl::RunGraph() -- entry"
0x1800d00c1  call    ?SetMark@CPerfInfo@@QEAAXPEBD@Z; CPerfInfo::SetMark(char const *)
0x1800d00c6  nop
0x1800d00c7  xor     r14d, r14d
0x1800d00ca  cmp     [rsi+2A8h], r14
0x1800d00d1  jz      loc_1800D0E28
0x1800d00d7  lea     rbx, [rsi+230h]
0x1800d00de  cmp     [rbx+8], r14
0x1800d00e2  jz      loc_1800D0E28
0x1800d00e8  lea     rax, [rsi+1E8h]
0x1800d00ef  mov     [rsp+0F8h+arg_0], rax
0x1800d00f7  mov     byte ptr [rax], 1
0x1800d00fa  mov     rcx, rsi; this
0x1800d00fd  call    ?OnMediaEvent@CVidCtl@@QEAA_JI_K_JAEAH@Z; CVidCtl::OnMediaEvent(uint,unsigned __int64,__int64,int &)
0x1800d0102  mov     rcx, rbx; this
0x1800d0105  call    ?IsPlaying@DSGraph@@QEAA_NXZ; DSGraph::IsPlaying(void)
0x1800d010a  test    al, al
0x1800d010c  jz      short loc_1800D0122
0x1800d010e  lea     rcx, [rsp+0F8h+arg_0]; this
0x1800d0116  call    ??1CGRLocker@@QEAA@XZ; CGRLocker::~CGRLocker(void)
0x1800d011b  xor     eax, eax
0x1800d011d  jmp     loc_1800D0E5F
0x1800d0122  mov     rcx, rbx; this
0x1800d0125  call    ?IsPaused@DSGraph@@QEAA_NXZ; DSGraph::IsPaused(void)
0x1800d012a  test    al, al
0x1800d012c  jz      loc_1800D024D
0x1800d0132  cmp     dword ptr [rsi+228h], 1
0x1800d0139  jnz     loc_1800D024D
0x1800d013f  mov     rdx, [rsi+238h]
0x1800d0146  lea     rcx, [rsp+0F8h+arg_8]
0x1800d014e  call    ??0?$CComQIPtr@UIMediaControl@@$1?IID_IMediaControl@@3U_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IMediaControl,&_GUID const IID_IMediaControl>::CComQIPtr<IMediaControl,&_GUID const IID_IMediaControl>(IUnknown *)
0x1800d0153  nop
0x1800d0154  cmp     [rsp+0F8h+arg_8], r14
0x1800d015c  jnz     short loc_1800D0199
0x1800d015e  mov     r9, cs:hInstance
0x1800d0165  mov     ecx, 0C0040513h; dwMessageId
0x1800d016a  mov     r8d, 0C0040513h
0x1800d0170  call    ?Error@?$CComCoClass@VCVidCtl@@$1?CLSID_MSVidCtl@@3U_GUID@@B@ATL@@SAJIAEBU_GUID@@JPEAUHINSTANCE__@@@Z; ATL::CComCoClass<CVidCtl,&_GUID const CLSID_MSVidCtl>::Error(uint,_GUID const &,long,HINSTANCE__ *)
0x1800d0175  mov     ebx, eax
0x1800d0177  lea     rcx, [rsp+0F8h+arg_8]
0x1800d017f  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d0184  nop
0x1800d0185  lea     rcx, [rsp+0F8h+arg_0]; this
0x1800d018d  call    ??1CGRLocker@@QEAA@XZ; CGRLocker::~CGRLocker(void)
0x1800d0192  mov     eax, ebx
0x1800d0194  jmp     loc_1800D0E5F
0x1800d0199  lea     rdx, aCvidctlRungrap_3; "CVidCtl::RunGraph() -- calling IMediaCo"...
0x1800d01a0  call    ?SetMark@CPerfInfo@@QEAAXPEBD@Z; CPerfInfo::SetMark(char const *)
0x1800d01a5  mov     rcx, [rsp+0F8h+arg_8]
0x1800d01ad  mov     rax, [rcx]
0x1800d01b0  mov     rax, [rax+38h]
0x1800d01b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d01b9  mov     ebx, eax
0x1800d01bb  lea     rdx, aCvidctlRungrap_7; "CVidCtl::RunGraph() -- done calling IMe"...
0x1800d01c2  call    ?SetMark@CPerfInfo@@QEAAXPEBD@Z; CPerfInfo::SetMark(char const *)
0x1800d01c7  test    ebx, ebx
0x1800d01c9  jns     short loc_1800D0222
0x1800d01cb  lea     r9, aImediacontrolR; "IMediaControl::Run() Failed"
0x1800d01d2  lea     r8, aCvidctlRungrap_0; "CVidCtl::RunGraph"
0x1800d01d9  mov     edx, 5; unsigned int
0x1800d01de  lea     rcx, ?gCVidCtlTrace@@3VCVidCtlTrace@@A; this
0x1800d01e5  call    ?Trace@CVidCtlTrace@@QEAAJKPEBD0ZZ; CVidCtlTrace::Trace(ulong,char const *,char const *,...)
0x1800d01ea  mov     r9, cs:hInstance
0x1800d01f1  mov     r8d, ebx
0x1800d01f4  mov     ecx, 0C0040524h; dwMessageId
0x1800d01f9  call    ?Error@?$CComCoClass@VCVidCtl@@$1?CLSID_MSVidCtl@@3U_GUID@@B@ATL@@SAJIAEBU_GUID@@JPEAUHINSTANCE__@@@Z; ATL::CComCoClass<CVidCtl,&_GUID const CLSID_MSVidCtl>::Error(uint,_GUID const &,long,HINSTANCE__ *)
0x1800d01fe  mov     ebx, eax
0x1800d0200  lea     rcx, [rsp+0F8h+arg_8]
0x1800d0208  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d020d  nop
0x1800d020e  lea     rcx, [rsp+0F8h+arg_0]; this
0x1800d0216  call    ??1CGRLocker@@QEAA@XZ; CGRLocker::~CGRLocker(void)
0x1800d021b  mov     eax, ebx
0x1800d021d  jmp     loc_1800D0E5F
0x1800d0222  mov     rcx, rsi; this
0x1800d0225  call    ?OnMediaEvent@CVidCtl@@QEAA_JI_K_JAEAH@Z; CVidCtl::OnMediaEvent(uint,unsigned __int64,__int64,int &)
0x1800d022a  nop
0x1800d022b  lea     rcx, [rsp+0F8h+arg_8]
0x1800d0233  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d0238  nop
0x1800d0239  lea     rcx, [rsp+0F8h+arg_0]; this
0x1800d0241  call    ??1CGRLocker@@QEAA@XZ; CGRLocker::~CGRLocker(void)
0x1800d0246  xor     eax, eax
0x1800d0248  jmp     loc_1800D0E5F
0x1800d024d  cmp     [rsi+379h], r14b
0x1800d0254  jz      short loc_1800D02B0
0x1800d0256  lea     rdx, aCvidctlRungrap_2; "CVidCtl::RunGraph() -- pre BuildGraph"
0x1800d025d  call    ?SetMark@CPerfInfo@@QEAAXPEBD@Z; CPerfInfo::SetMark(char const *)
0x1800d0262  mov     rcx, rsi; this
0x1800d0265  call    ?BuildGraph@CVidCtl@@IEAAJXZ; CVidCtl::BuildGraph(void)
0x1800d026a  mov     edi, eax
0x1800d026c  lea     rdx, aCvidctlRungrap_9; "CVidCtl::RunGraph() -- post BuildGraph"
0x1800d0273  call    ?SetMark@CPerfInfo@@QEAAXPEBD@Z; CPerfInfo::SetMark(char const *)
0x1800d0278  test    edi, edi
0x1800d027a  jns     short loc_1800D02B0
0x1800d027c  lea     r9, aBuildgraphFail; "BuildGraph Failed"
0x1800d0283  lea     r8, aCvidctlRungrap_0; "CVidCtl::RunGraph"
0x1800d028a  mov     edx, 5; unsigned int
0x1800d028f  lea     rcx, ?gCVidCtlTrace@@3VCVidCtlTrace@@A; this
0x1800d0296  call    ?Trace@CVidCtlTrace@@QEAAJKPEBD0ZZ; CVidCtlTrace::Trace(ulong,char const *,char const *,...)
0x1800d029b  nop
0x1800d029c  lea     rcx, [rsp+0F8h+arg_0]; this
0x1800d02a4  call    ??1CGRLocker@@QEAA@XZ; CGRLocker::~CGRLocker(void)
0x1800d02a9  mov     eax, edi
0x1800d02ab  jmp     loc_1800D0E5F
0x1800d02b0  mov     rcx, rbx; this
0x1800d02b3  call    ?GetState@DSGraph@@QEAAJJ@Z; DSGraph::GetState(long)
0x1800d02b8  lea     rdx, aCvidctlRungrap_4; "CVidCtl::RunGraph() -- before calling P"...
0x1800d02bf  call    ?SetMark@CPerfInfo@@QEAAXPEBD@Z; CPerfInfo::SetMark(char const *)
0x1800d02c4  mov     rdx, [rsi+2A8h]; struct IUnknown *
0x1800d02cb  lea     rcx, [rsp+0F8h+var_C8]; this
0x1800d02d0  call    ??0VWGraphSegment@MSVideoControl@@QEAA@PEAUIUnknown@@@Z; MSVideoControl::VWGraphSegment::VWGraphSegment(IUnknown *)
0x1800d02d5  nop
0x1800d02d6  mov     rcx, [rax+8]
0x1800d02da  mov     rax, [rcx]
0x1800d02dd  mov     rax, [rax+68h]
0x1800d02e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d02e6  mov     ebx, eax
0x1800d02e8  lea     r13, ??_7?$Forward_Sequence@V?$CComQIPtr@UIMSVidGraphSegment@@$1?_GUID_238dec54_adeb_4005_a349_f772b9afebc4@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIEnumFilters@@$1?IID_IEnumFilters@@3U_GUID@@B@2@VDSFilter@@UIMSVidGraphSegment@@UIEnumFilters@@PEAUIBaseFilter@@V?$allocator@VDSFilter@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable'
0x1800d02ef  mov     [rsp+0F8h+var_C8], r13
0x1800d02f4  lea     rcx, [rsp+0F8h+var_C0]
0x1800d02f9  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d02fe  mov     r12d, 80000000h
0x1800d0304  lea     eax, [rbx+r12]
0x1800d0308  mov     r15d, 80004001h
0x1800d030e  test    r12d, eax
0x1800d0311  jnz     short loc_1800D034C
0x1800d0313  cmp     ebx, r15d
0x1800d0316  jz      short loc_1800D034C
0x1800d0318  lea     r9, aPrerunInputFai; "PreRun Input Failed"
0x1800d031f  lea     r8, aCvidctlRungrap_0; "CVidCtl::RunGraph"
0x1800d0326  mov     edx, 5; unsigned int
0x1800d032b  lea     rcx, ?gCVidCtlTrace@@3VCVidCtlTrace@@A; this
0x1800d0332  call    ?Trace@CVidCtlTrace@@QEAAJKPEBD0ZZ; CVidCtlTrace::Trace(ulong,char const *,char const *,...)
0x1800d0337  nop
0x1800d0338  lea     rcx, [rsp+0F8h+arg_0]; this
0x1800d0340  call    ??1CGRLocker@@QEAA@XZ; CGRLocker::~CGRLocker(void)
0x1800d0345  mov     eax, ebx
0x1800d0347  jmp     loc_1800D0E5F
0x1800d034c  mov     rdx, [rsi+2C0h]; struct IMSVidGraphSegment *
0x1800d0353  test    rdx, rdx
0x1800d0356  jz      short loc_1800D03C6
0x1800d0358  lea     rcx, [rsp+0F8h+var_C8]; this
0x1800d035d  call    ??0VWGraphSegment@MSVideoControl@@QEAA@PEAUIMSVidGraphSegment@@@Z; MSVideoControl::VWGraphSegment::VWGraphSegment(IMSVidGraphSegment *)
0x1800d0362  nop
0x1800d0363  mov     rcx, [rax+8]
0x1800d0367  mov     rax, [rcx]
0x1800d036a  mov     rax, [rax+68h]
0x1800d036e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0373  mov     ebx, eax
0x1800d0375  mov     [rsp+0F8h+var_C8], r13
0x1800d037a  lea     rcx, [rsp+0F8h+var_C0]
0x1800d037f  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d0384  lea     ecx, [rbx+r12]
0x1800d0388  test    r12d, ecx
0x1800d038b  jnz     short loc_1800D03C6
0x1800d038d  cmp     ebx, r15d
0x1800d0390  jz      short loc_1800D03C6
0x1800d0392  lea     r9, aPrerunVideoRen; "PreRun Video Renderer Failed"
0x1800d0399  lea     r8, aCvidctlRungrap_0; "CVidCtl::RunGraph"
0x1800d03a0  mov     edx, 5; unsigned int
0x1800d03a5  lea     rcx, ?gCVidCtlTrace@@3VCVidCtlTrace@@A; this
0x1800d03ac  call    ?Trace@CVidCtlTrace@@QEAAJKPEBD0ZZ; CVidCtlTrace::Trace(ulong,char const *,char const *,...)
0x1800d03b1  nop
0x1800d03b2  lea     rcx, [rsp+0F8h+arg_0]; this
0x1800d03ba  call    ??1CGRLocker@@QEAA@XZ; CGRLocker::~CGRLocker(void)
0x1800d03bf  mov     eax, ebx
0x1800d03c1  jmp     loc_1800D0E5F
0x1800d03c6  mov     rdx, [rsi+2C8h]; struct IUnknown *
0x1800d03cd  test    rdx, rdx
0x1800d03d0  jz      short loc_1800D0440
0x1800d03d2  lea     rcx, [rsp+0F8h+var_C8]; this
0x1800d03d7  call    ??0VWGraphSegment@MSVideoControl@@QEAA@PEAUIUnknown@@@Z; MSVideoControl::VWGraphSegment::VWGraphSegment(IUnknown *)
0x1800d03dc  nop
0x1800d03dd  mov     rcx, [rax+8]
0x1800d03e1  mov     rax, [rcx]
0x1800d03e4  mov     rax, [rax+68h]
0x1800d03e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d03ed  mov     ebx, eax
0x1800d03ef  mov     [rsp+0F8h+var_C8], r13
0x1800d03f4  lea     rcx, [rsp+0F8h+var_C0]
0x1800d03f9  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d03fe  lea     ecx, [rbx+r12]
0x1800d0402  test    r12d, ecx
0x1800d0405  jnz     short loc_1800D0440
0x1800d0407  cmp     ebx, r15d
0x1800d040a  jz      short loc_1800D0440
0x1800d040c  lea     r9, aPrerunAudioRen; "PreRun Audio Renderer Failed"
0x1800d0413  lea     r8, aCvidctlRungrap_0; "CVidCtl::RunGraph"
0x1800d041a  mov     edx, 5; unsigned int
0x1800d041f  lea     rcx, ?gCVidCtlTrace@@3VCVidCtlTrace@@A; this
0x1800d0426  call    ?Trace@CVidCtlTrace@@QEAAJKPEBD0ZZ; CVidCtlTrace::Trace(ulong,char const *,char const *,...)
0x1800d042b  nop
0x1800d042c  lea     rcx, [rsp+0F8h+arg_0]; this
0x1800d0434  call    ??1CGRLocker@@QEAA@XZ; CGRLocker::~CGRLocker(void)
0x1800d0439  mov     eax, ebx
0x1800d043b  jmp     loc_1800D0E5F
0x1800d0440  xorps   xmm0, xmm0
0x1800d0443  xor     eax, eax
0x1800d0445  movups  xmmword ptr [rsp+0F8h+var_B8], xmm0
0x1800d044a  mov     qword ptr [rsp+0F8h+var_B8+10h], rax
0x1800d044f  mov     [rsp+0F8h+arg_10], r14
0x1800d0457  lea     r8, [rsp+0F8h+var_B8]
0x1800d045c  lea     rdx, [rsp+0F8h+arg_10]
0x1800d0464  lea     rcx, [rsp+0F8h+var_98]
0x1800d0469  call    ??0?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@QEAA@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@@Z; enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant)
0x1800d046e  nop
0x1800d046f  lea     rcx, [rsi+2B0h]
0x1800d0476  lea     rdx, [rsp+0F8h+pvarg]
0x1800d047e  call    ?begin@?$Forward_Sequence@V?$CComQIPtr@UIMSVidInputDevices@@$1?_GUID_c5702cd1_9b79_11d3_b654_00c04f79498e@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@2@VCComVariant@2@UIMSVidInputDevices@@UIEnumVARIANT@@UtagVARIANT@@V?$allocator@UtagVARIANT@@@std@@@@QEAA?AV?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@XZ; Forward_Sequence<ATL::CComQIPtr<IMSVidInputDevices,&__s_GUID const _GUID_c5702cd1_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidInputDevices,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::begin(void)
0x1800d0483  nop
0x1800d0484  mov     rdx, rax
0x1800d0487  lea     rcx, [rsp+0F8h+var_98]
0x1800d048c  call    ??4?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@QEAAAEAV0@AEBV0@@Z; enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator=(enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64> const &)
0x1800d0491  nop
0x1800d0492  lea     rcx, [rsp+0F8h+pvarg]
0x1800d049a  call    ??1?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@QEAA@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(void)
0x1800d049f  mov     edi, 8
0x1800d04a4  lea     rdx, [rsp+0F8h+pvarg]
0x1800d04ac  call    ?end@?$Forward_Sequence@V?$CComQIPtr@UIMSVidFeatures@@$1?_GUID_c5702cd5_9b79_11d3_b654_00c04f79498e@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@2@VCComVariant@2@UIMSVidFeatures@@UIEnumVARIANT@@UtagVARIANT@@V?$allocator@UtagVARIANT@@@std@@@@QEAA?AV?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@XZ; Forward_Sequence<ATL::CComQIPtr<IMSVidFeatures,&__s_GUID const _GUID_c5702cd5_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidFeatures,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::end(void)
0x1800d04b1  lea     rdx, [rax+8]
0x1800d04b5  lea     rcx, [rsp+0F8h+var_90]
0x1800d04ba  call    ??8CComVariant@ATL@@QEBA_NAEBUtagVARIANT@@@Z; ATL::CComVariant::operator==(tagVARIANT const &)
0x1800d04bf  mov     bl, al
0x1800d04c1  lea     rcx, [rsp+0F8h+pvarg]
0x1800d04c9  call    ??1?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@QEAA@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(void)
0x1800d04ce  test    bl, bl
0x1800d04d0  jnz     loc_1800D059A
0x1800d04d6  lea     rdx, [rsp+0F8h+pvarg]
0x1800d04de  lea     rcx, [rsp+0F8h+var_98]
0x1800d04e3  call    ??D?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@QEBA?AVCComVariant@ATL@@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator*(void)
0x1800d04e8  nop
0x1800d04e9  mov     rdx, rax; struct ATL::CComVariant *
0x1800d04ec  lea     rcx, [rsp+0F8h+var_C8]; this
0x1800d04f1  call    ??0VWGraphSegment@MSVideoControl@@QEAA@AEBVCComVariant@ATL@@@Z; MSVideoControl::VWGraphSegment::VWGraphSegment(ATL::CComVariant const &)
0x1800d04f6  nop
0x1800d04f7  mov     rcx, [rax+8]
0x1800d04fb  mov     rax, [rcx]
0x1800d04fe  mov     rax, [rax+68h]
0x1800d0502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0507  mov     ebx, eax
0x1800d0509  mov     [rsp+0F8h+var_C8], r13
0x1800d050e  lea     rcx, [rsp+0F8h+var_C0]
0x1800d0513  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d0518  nop
0x1800d0519  mov     eax, 0FFFh
0x1800d051e  cmp     word ptr [rsp+0F8h+pvarg], ax
0x1800d0526  jnz     short loc_1800D0530
0x1800d0528  mov     word ptr [rsp+0F8h+pvarg], di
0x1800d0530  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x1800d0538  call    cs:__imp_VariantClear
0x1800d053e  lea     eax, [rbx+r12]
0x1800d0542  test    r12d, eax
0x1800d0545  jnz     short loc_1800D058B
0x1800d0547  cmp     ebx, r15d
0x1800d054a  jz      short loc_1800D058B
0x1800d054c  lea     r9, aPrerunOutputFa; "PreRun Output Failed"
0x1800d0553  lea     r8, aCvidctlRungrap_0; "CVidCtl::RunGraph"
0x1800d055a  mov     edx, 5; unsigned int
0x1800d055f  lea     rcx, ?gCVidCtlTrace@@3VCVidCtlTrace@@A; this
0x1800d0566  call    ?Trace@CVidCtlTrace@@QEAAJKPEBD0ZZ; CVidCtlTrace::Trace(ulong,char const *,char const *,...)
0x1800d056b  nop
0x1800d056c  lea     rcx, [rsp+0F8h+var_98]
0x1800d0571  call    ??1?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@QEAA@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(void)
0x1800d0576  nop
0x1800d0577  lea     rcx, [rsp+0F8h+arg_0]; this
0x1800d057f  call    ??1CGRLocker@@QEAA@XZ; CGRLocker::~CGRLocker(void)
0x1800d0584  mov     eax, ebx
0x1800d0586  jmp     loc_1800D0E5F
0x1800d058b  lea     rcx, [rsp+0F8h+var_98]
0x1800d0590  call    ??E?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@QEAAAEAV0@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator++(void)
0x1800d0595  jmp     loc_1800D04A4
0x1800d059a  lea     rcx, [rsp+0F8h+var_98]
0x1800d059f  call    ??1?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@QEAA@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(void)
0x1800d05a4  lea     r13, [rsi+2D0h]
0x1800d05ab  cmp     [r13+8], r14
0x1800d05af  jz      loc_1800D070D
0x1800d05b5  xorps   xmm0, xmm0
0x1800d05b8  xor     eax, eax
0x1800d05ba  movups  xmmword ptr [rsp+0F8h+pvarg], xmm0
0x1800d05c2  mov     qword ptr [rsp+0F8h+pvarg+10h], rax
0x1800d05ca  mov     [rsp+0F8h+arg_10], r14
0x1800d05d2  lea     r8, [rsp+0F8h+pvarg]
0x1800d05da  lea     rdx, [rsp+0F8h+arg_10]
0x1800d05e2  lea     rcx, [rsp+0F8h+var_98]
0x1800d05e7  call    ??0?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@QEAA@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@@Z; enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant)
0x1800d05ec  nop
0x1800d05ed  lea     rdx, [rsp+0F8h+var_B8]
0x1800d05f2  mov     rcx, r13
0x1800d05f5  call    ?begin@?$Forward_Sequence@V?$CComQIPtr@UIMSVidInputDevices@@$1?_GUID_c5702cd1_9b79_11d3_b654_00c04f79498e@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@2@VCComVariant@2@UIMSVidInputDevices@@UIEnumVARIANT@@UtagVARIANT@@V?$allocator@UtagVARIANT@@@std@@@@QEAA?AV?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@XZ; Forward_Sequence<ATL::CComQIPtr<IMSVidInputDevices,&__s_GUID const _GUID_c5702cd1_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidInputDevices,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::begin(void)
0x1800d05fa  nop
  ... truncated ...
```
