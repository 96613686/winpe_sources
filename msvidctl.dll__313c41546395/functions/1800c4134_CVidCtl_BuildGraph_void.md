# CVidCtl::BuildGraph(void)

- ea: `0x1800c4134`
- end: `0x1800c54ae`
- name: `?BuildGraph@CVidCtl@@IEAAJXZ`
- size: `4986`
- prototype: `__int64 __fastcall(CVidCtl *__hidden this)`
- caller_count: `3`
- callee_count: `27`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c4070`
- `0x1800cea90`
- `0x1800d00a4`

## callees

- `0x180006b38`
- `0x18000dc24`
- `0x1800574c4`
- `0x1800581ac`
- `0x1800581d8`
- `0x1800c18d8`
- `0x1800c2158`
- `0x1800c2840`
- `0x1800c2b84`
- `0x1800c2cac`
- `0x1800c34d4`
- `0x1800c36f8`
- `0x1800c3828`
- `0x1800c3854`
- `0x1800c4134`
- `0x1800c571c`
- `0x1800c8cd0`
- `0x1800ccf60`
- `0x1800cd050`
- `0x1800cda70`
- `0x1800cfca4`
- `0x1800cfcf4`
- `0x1800d1dac`
- `0x1800d32d8`
- `0x1800d3394`
- `0x1800ed80c`
- `0x1800f8010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800c4464`
- `OLEAUT32!__imp_VariantClear` at `0x1800c4571`
- `OLEAUT32!__imp_VariantClear` at `0x1800c4715`
- `OLEAUT32!__imp_VariantClear` at `0x1800c4857`
- `OLEAUT32!__imp_VariantClear` at `0x1800c4a8d`
- `OLEAUT32!__imp_VariantClear` at `0x1800c4d19`
- `OLEAUT32!__imp_VariantClear` at `0x1800c4e46`
- `OLEAUT32!__imp_VariantClear` at `0x1800c4f07`
- `OLEAUT32!__imp_VariantClear` at `0x1800c5001`
- `OLEAUT32!__imp_VariantClear` at `0x1800c5037`
- `OLEAUT32!__imp_VariantClear` at `0x1800c5200`
- `OLEAUT32!__imp_VariantClear` at `0x1800c5343`
- `OLEAUT32!__imp_VariantClear` at `0x1800c4464`
- `OLEAUT32!__imp_VariantClear` at `0x1800c4571`
- `OLEAUT32!__imp_VariantClear` at `0x1800c4715`
- `OLEAUT32!__imp_VariantClear` at `0x1800c4857`
- `OLEAUT32!__imp_VariantClear` at `0x1800c4a8d`
- `OLEAUT32!__imp_VariantClear` at `0x1800c4d19`
- `OLEAUT32!__imp_VariantClear` at `0x1800c4e46`
- `OLEAUT32!__imp_VariantClear` at `0x1800c4f07`
- `OLEAUT32!__imp_VariantClear` at `0x1800c5001`
- `OLEAUT32!__imp_VariantClear` at `0x1800c5037`
- `OLEAUT32!__imp_VariantClear` at `0x1800c5200`
- `OLEAUT32!__imp_VariantClear` at `0x1800c5343`

## string_xrefs

- `0x1800c4aa5`: `Can't compose input segment with feature segment`
- `0x1800c4c2c`: `Can't compose input and audio.`
- `0x1800c4b66`: `Can't compose input and video.`
- `0x1800c4e67`: `Can't compose feature segment with renderers`
- `0x1800c4d34`: `Can't compose output segment with input`
- `0x1800c5066`: `Can't compose output segment with feature.`
- `0x1800c4f2c`: `Can't compose feature segment with Video Renderer `

## pseudocode

```c
// Hidden C++ exception states: #wind=45
__int64 __fastcall CVidCtl::BuildGraph(CVidCtl *this, unsigned int a2, unsigned __int64 a3, __int64 a4)
{
  unsigned int v5; // edi
  bool v6; // r15
  __int64 v7; // rdx
  _QWORD *v8; // rax
  int DefaultVR; // ebx
  bool v10; // r14
  __int64 v11; // rdx
  _QWORD *v12; // rax
  __int64 v13; // rdx
  _QWORD *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  char v17; // bl
  const struct ATL::CComVariant *v18; // rax
  __int64 v19; // rax
  VARIANTARG *v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rax
  char v23; // bl
  const struct ATL::CComVariant *v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rax
  char v30; // bl
  const struct ATL::CComVariant *v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rax
  char v36; // bl
  const struct ATL::CComVariant *v37; // rax
  __int64 v38; // rax
  struct IMSVidGraphSegment *v39; // rdx
  __int64 v40; // rax
  struct IUnknown *v41; // rdx
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rax
  char v46; // bl
  const struct ATL::CComVariant *v47; // rax
  struct MSVideoControl::VWGraphSegment *v48; // rbx
  struct MSVideoControl::VWGraphSegment *v49; // rax
  struct IMSVidGraphSegment *v50; // rdx
  struct MSVideoControl::VWGraphSegment *v51; // rbx
  struct MSVideoControl::VWGraphSegment *v52; // rax
  void (__fastcall ***v53)(_QWORD, GUID *, __int64 *); // rcx
  struct IUnknown *v54; // rdx
  struct MSVideoControl::VWGraphSegment *v55; // rbx
  struct MSVideoControl::VWGraphSegment *v56; // rax
  __int64 v57; // rcx
  __int64 v58; // rax
  char v59; // bl
  const struct ATL::CComVariant *v60; // rax
  struct MSVideoControl::VWGraphSegment *v61; // rbx
  struct MSVideoControl::VWGraphSegment *v62; // rax
  __int64 v63; // rcx
  __int64 v64; // rax
  char v65; // bl
  struct IMSVidGraphSegment *v66; // rdx
  struct MSVideoControl::VWGraphSegment *v67; // rbx
  const struct ATL::CComVariant *v68; // rax
  struct MSVideoControl::VWGraphSegment *v69; // rax
  int v70; // ebx
  struct IUnknown *v71; // rdx
  struct MSVideoControl::VWGraphSegment *v72; // rbx
  const struct ATL::CComVariant *v73; // rax
  struct MSVideoControl::VWGraphSegment *v74; // rax
  int v75; // ebx
  __int64 v76; // rcx
  __int64 v77; // rax
  char v78; // bl
  const struct ATL::CComVariant *v79; // rax
  struct MSVideoControl::VWGraphSegment *v80; // rbx
  const struct ATL::CComVariant *v81; // rax
  struct MSVideoControl::VWGraphSegment *v82; // rax
  __int64 v83; // rax
  __int64 v84; // rax
  __int64 v85; // rcx
  __int64 v86; // rax
  char v87; // bl
  const struct ATL::CComVariant *v88; // rax
  __int64 v89; // rax
  __int64 v90; // rax
  __int64 v91; // rcx
  __int64 v92; // rax
  char v93; // bl
  const struct ATL::CComVariant *v94; // rax
  __int64 v95; // rax
  struct IMSVidGraphSegment *v96; // rdx
  __int64 v97; // rax
  struct IUnknown *v98; // rdx
  __int64 v99; // rax
  unsigned int v100; // edx
  unsigned __int64 v101; // r8
  __int64 v102; // r9
  int *v104; // [rsp+20h] [rbp-E0h]
  int *v105; // [rsp+20h] [rbp-E0h]
  void **v106; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v107[8]; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-C0h] BYREF
  void **v109; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v110[8]; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG v111; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG v112; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v113[8]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v114[24]; // [rsp+B0h] [rbp-50h] BYREF
  VARIANTARG v115; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v116; // [rsp+E8h] [rbp-18h] BYREF
  char *v117; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v118[8]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v119[24]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v120[8]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v121[24]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v122[8]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v123[24]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v124[8]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v125[24]; // [rsp+160h] [rbp+60h] BYREF
  void **v126; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v127[8]; // [rsp+180h] [rbp+80h] BYREF
  void **v128; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v129[8]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v130[8]; // [rsp+198h] [rbp+98h] BYREF
  _BYTE v131[24]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v132[8]; // [rsp+1B8h] [rbp+B8h] BYREF
  _BYTE v133[24]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v134[8]; // [rsp+1D8h] [rbp+D8h] BYREF
  _BYTE v135[96]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v136; // [rsp+250h] [rbp+150h] BYREF
  int v137; // [rsp+258h] [rbp+158h] BYREF
  int v138; // [rsp+260h] [rbp+160h] BYREF
  __int64 v139; // [rsp+268h] [rbp+168h] BYREF

  v117 = (char *)this + 488;
  *((_BYTE *)this + 488) = 1;
  CVidCtl::OnMediaEvent(this, a2, a3, a4, v104);
  if ( *((_DWORD *)this + 138) == -1 || *((_BYTE *)this + 889) == 1 )
  {
    v5 = 0;
    v6 = 0;
    v7 = *((_QWORD *)this + 88);
    if ( v7 )
    {
      v8 = (_QWORD *)ATL::CComQIPtr<IMSVidAudioRendererDevices,&__s_GUID const _GUID_c5702cd4_9b79_11d3_b654_00c04f79498e>::CComQIPtr<IMSVidAudioRendererDevices,&__s_GUID const _GUID_c5702cd4_9b79_11d3_b654_00c04f79498e>(
                       &v136,
                       v7);
      DefaultVR = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(*(_QWORD *)*v8 + 64LL))(
                    *v8,
                    -(__int64)(this != 0) & ((unsigned __int64)this + 328));
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v136);
      if ( DefaultVR < 0 )
      {
        CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "put_Container failed for Video Renderer");
LABEL_7:
        v5 = DefaultVR;
        goto LABEL_157;
      }
    }
    else if ( !*((_BYTE *)this + 891) )
    {
      DefaultVR = CVidCtl::LoadDefaultVR(this);
      if ( DefaultVR < 0 )
      {
        CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "LoadDefaultVR failed");
        goto LABEL_7;
      }
      if ( !*((_QWORD *)this + 88) )
      {
        CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "LoadDefaultVR returned NULL Video Renderer");
        goto LABEL_13;
      }
      v6 = 1;
    }
    v10 = 0;
    v11 = *((_QWORD *)this + 89);
    if ( v11 )
    {
      v12 = (_QWORD *)ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>(
                        &v136,
                        v11);
      DefaultVR = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(*(_QWORD *)*v12 + 64LL))(
                    *v12,
                    -(__int64)(this != 0) & ((unsigned __int64)this + 328));
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v136);
      if ( DefaultVR < 0 )
      {
        CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "put_Container failed for Audio Renderer");
        goto LABEL_7;
      }
LABEL_24:
      v13 = *((_QWORD *)this + 85);
      if ( !v13 )
      {
        CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "Input segment required");
        CVidCtl::ReleaseDefaultRenderer(this, v6, v10);
        v5 = ATL::CComCoClass<CVidCtl,&_GUID const CLSID_MSVidCtl>::Error(0xC0040512);
        goto LABEL_157;
      }
      v14 = (_QWORD *)ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>(
                        &v136,
                        v13);
      DefaultVR = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(*(_QWORD *)*v14 + 64LL))(
                    *v14,
                    ((unsigned __int64)this + 328) & -(__int64)(this != 0));
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v136);
      if ( DefaultVR < 0 )
      {
        CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "Can't load input segment.");
LABEL_28:
        CVidCtl::ReleaseDefaultRenderer(this, v6, v10);
        goto LABEL_7;
      }
      if ( *((_QWORD *)this + 91) )
      {
        Forward_Sequence<ATL::CComQIPtr<IMSVidInputDevices,&__s_GUID const _GUID_c5702cd1_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidInputDevices,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::begin(
          (char *)this + 720,
          v130);
        while ( 1 )
        {
          v16 = Forward_Sequence<ATL::CComQIPtr<IMSVidFeatures,&__s_GUID const _GUID_c5702cd5_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidFeatures,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::end(
                  v15,
                  v113);
          v17 = ATL::CComVariant::operator==(v131, v16 + 8);
          enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v113);
          if ( v17 )
            break;
          v18 = (const struct ATL::CComVariant *)enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator*(
                                                   v130,
                                                   &pvarg);
          v19 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v106, v18);
          DefaultVR = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(v19 + 8) + 64LL))(
                        *(_QWORD *)(v19 + 8),
                        ((unsigned __int64)this + 328) & -(__int64)(this != 0));
          v106 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v107);
          if ( pvarg.vt == 4095 )
            pvarg.vt = 8;
          VariantClear(&pvarg);
          if ( DefaultVR < 0 )
          {
            CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "Can't load feature segment");
            CVidCtl::ReleaseDefaultRenderer(this, v6, v10);
            v20 = (VARIANTARG *)v130;
            goto LABEL_37;
          }
          enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator++(v130);
        }
        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v130);
      }
      Forward_Sequence<ATL::CComQIPtr<IMSVidInputDevices,&__s_GUID const _GUID_c5702cd1_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidInputDevices,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::begin(
        (char *)this + 688,
        v132);
      while ( 1 )
      {
        v22 = Forward_Sequence<ATL::CComQIPtr<IMSVidFeatures,&__s_GUID const _GUID_c5702cd5_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidFeatures,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::end(
                v21,
                v113);
        v23 = ATL::CComVariant::operator==(v133, v22 + 8);
        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v113);
        if ( v23 )
          break;
        v24 = (const struct ATL::CComVariant *)enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator*(
                                                 v132,
                                                 &pvarg);
        v25 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v106, v24);
        DefaultVR = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(v25 + 8) + 64LL))(
                      *(_QWORD *)(v25 + 8),
                      ((unsigned __int64)this + 328) & -(__int64)(this != 0));
        v106 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v107);
        if ( pvarg.vt == 4095 )
          pvarg.vt = 8;
        VariantClear(&pvarg);
        if ( DefaultVR < 0 )
        {
          CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "Can't load output segment");
          CVidCtl::ReleaseDefaultRenderer(this, v6, v10);
          v20 = (VARIANTARG *)v132;
          goto LABEL_37;
        }
        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator++(v132);
      }
      enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v132);
      v26 = MSVideoControl::VWGraphSegment::VWGraphSegment(
              (MSVideoControl::VWGraphSegment *)&v106,
              *((struct IUnknown **)this + 85));
      DefaultVR = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v26 + 8) + 88LL))(*(_QWORD *)(v26 + 8));
      v106 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v107);
      if ( (int)(DefaultVR + 0x80000000) >= 0 && DefaultVR != -2147467263 )
      {
        CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "Build call for input failed");
        goto LABEL_28;
      }
      if ( *((_QWORD *)this + 91) )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        v136 = 0;
        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(
          v120,
          &v136,
          &pvarg);
        v27 = Forward_Sequence<ATL::CComQIPtr<IMSVidInputDevices,&__s_GUID const _GUID_c5702cd1_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidInputDevices,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::begin(
                (char *)this + 720,
                v113);
        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator=(
          v120,
          v27);
        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v113);
        while ( 1 )
        {
          v29 = Forward_Sequence<ATL::CComQIPtr<IMSVidFeatures,&__s_GUID const _GUID_c5702cd5_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidFeatures,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::end(
                  v28,
                  v113);
          v30 = ATL::CComVariant::operator==(v121, v29 + 8);
          enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v113);
          if ( v30 )
            break;
          v31 = (const struct ATL::CComVariant *)enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator*(
                                                   v120,
                                                   &v111);
          v32 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v106, v31);
          DefaultVR = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v32 + 8) + 88LL))(*(_QWORD *)(v32 + 8));
          v106 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v107);
          if ( v111.vt == 4095 )
            v111.vt = 8;
          VariantClear(&v111);
          if ( ((DefaultVR + 0x80000000) & 0x80000000) == 0 && DefaultVR != -2147467263 )
          {
            CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "Can't build feature segment");
            CVidCtl::ReleaseDefaultRenderer(this, v6, v10);
            v20 = (VARIANTARG *)v120;
            goto LABEL_37;
          }
          enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator++(v120);
        }
        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v120);
      }
      memset(&pvarg, 0, sizeof(pvarg));
      v136 = 0;
      enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(
        v122,
        &v136,
        &pvarg);
      v33 = Forward_Sequence<ATL::CComQIPtr<IMSVidInputDevices,&__s_GUID const _GUID_c5702cd1_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidInputDevices,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::begin(
              (char *)this + 688,
              v113);
      enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator=(
        v122,
        v33);
      enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v113);
      while ( 1 )
      {
        v35 = Forward_Sequence<ATL::CComQIPtr<IMSVidFeatures,&__s_GUID const _GUID_c5702cd5_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidFeatures,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::end(
                v34,
                v113);
        v36 = ATL::CComVariant::operator==(v123, v35 + 8);
        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v113);
        if ( v36 )
          break;
        v37 = (const struct ATL::CComVariant *)enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator*(
                                                 v122,
                                                 &v111);
        v38 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v106, v37);
        DefaultVR = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v38 + 8) + 88LL))(*(_QWORD *)(v38 + 8));
        v106 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v107);
        if ( v111.vt == 4095 )
          v111.vt = 8;
        VariantClear(&v111);
        if ( ((DefaultVR + 0x80000000) & 0x80000000) == 0 && DefaultVR != -2147467263 )
        {
          CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "Can't build output segment");
          CVidCtl::ReleaseDefaultRenderer(this, v6, v10);
          v20 = (VARIANTARG *)v122;
          goto LABEL_37;
        }
        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator++(v122);
      }
      enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v122);
      v39 = (struct IMSVidGraphSegment *)*((_QWORD *)this + 88);
      if ( v39 )
      {
        v40 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v106, v39);
        DefaultVR = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v40 + 8) + 88LL))(*(_QWORD *)(v40 + 8));
        v106 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v107);
        if ( ((DefaultVR + 0x80000000) & 0x80000000) == 0 && DefaultVR != -2147467263 )
        {
          CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "Build call to Video Renderer Failed");
          goto LABEL_28;
        }
      }
      v41 = (struct IUnknown *)*((_QWORD *)this + 89);
      if ( v41 )
      {
        v42 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v106, v41);
        DefaultVR = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v42 + 8) + 88LL))(*(_QWORD *)(v42 + 8));
        v106 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v107);
        if ( ((DefaultVR + 0x80000000) & 0x80000000) == 0 && DefaultVR != -2147467263 )
        {
          CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "Build call to Audio Renderer Failed");
          goto LABEL_28;
        }
      }
      if ( *((_QWORD *)this + 91) )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        v136 = 0;
        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(
          v124,
          &v136,
          &pvarg);
        v43 = Forward_Sequence<ATL::CComQIPtr<IMSVidInputDevices,&__s_GUID const _GUID_c5702cd1_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidInputDevices,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::begin(
                (char *)this + 720,
                v113);
        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator=(
          v124,
          v43);
        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v113);
        while ( 1 )
        {
          v45 = Forward_Sequence<ATL::CComQIPtr<IMSVidFeatures,&__s_GUID const _GUID_c5702cd5_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidFeatures,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::end(
                  v44,
                  v113);
          v46 = ATL::CComVariant::operator==(v125, v45 + 8);
          enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v113);
          if ( v46 )
            break;
          v137 = -1;
          v47 = (const struct ATL::CComVariant *)enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator*(
                                                   v124,
                                                   &v111);
          v48 = (struct MSVideoControl::VWGraphSegment *)MSVideoControl::VWGraphSegment::VWGraphSegment(
                                                           (MSVideoControl::VWGraphSegment *)&v109,
                                                           v47);
          v49 = (struct MSVideoControl::VWGraphSegment *)MSVideoControl::VWGraphSegment::VWGraphSegment(
                                                           (MSVideoControl::VWGraphSegment *)&v106,
                                                           *((struct IUnknown **)this + 85));
          DefaultVR = CVidCtl::Compose(this, v49, v48, &v137);
          v106 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v107);
          v109 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v110);
          if ( v111.vt == 4095 )
            v111.vt = 8;
          VariantClear(&v111);
          if ( DefaultVR < 0 )
          {
            CVidCtlTrace::Trace(
              &gCVidCtlTrace,
              5u,
              "CVidCtl::BuildGraph",
              "Can't compose input segment with feature segment");
            CVidCtl::ReleaseDefaultRenderer(this, v6, v10);
            v20 = (VARIANTARG *)v124;
            goto LABEL_37;
          }
          enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator++(v124);
        }
        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v124);
      }
      v50 = (struct IMSVidGraphSegment *)*((_QWORD *)this + 88);
      if ( v50 )
      {
        if ( *((_DWORD *)this + 190) == -1 )
        {
          v51 = (struct MSVideoControl::VWGraphSegment *)MSVideoControl::VWGraphSegment::VWGraphSegment(
                                                           (MSVideoControl::VWGraphSegment *)&v106,
                                                           v50);
          v52 = (struct MSVideoControl::VWGraphSegment *)MSVideoControl::VWGraphSegment::VWGraphSegment(
                                                           (MSVideoControl::VWGraphSegment *)&v109,
                                                           *((struct IUnknown **)this + 85));
          DefaultVR = CVidCtl::Compose(this, v52, v51, (int *)this + 190);
          v109 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v110);
          v106 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v107);
          if ( DefaultVR < 0 )
          {
            CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "Can't compose input and video.");
            goto LABEL_28;
          }
        }
        v53 = *(void (__fastcall ****)(_QWORD, GUID *, __int64 *))(*((_QWORD *)this + 92)
                                                                 + 16LL * *((int *)this + 190)
                                                                 + 8);
        v139 = 0;
        if ( v53 )
          (**v53)(v53, &GUID_1c15d483_911d_11d2_b632_00c04f79498e, &v139);
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v139);
      }
      v54 = (struct IUnknown *)*((_QWORD *)this + 89);
      if ( v54 )
      {
        if ( *((_DWORD *)this + 191) == -1 )
        {
          v55 = (struct MSVideoControl::VWGraphSegment *)MSVideoControl::VWGraphSegment::VWGraphSegment(
                                                           (MSVideoControl::VWGraphSegment *)&v106,
                                                           v54);
          v56 = (struct MSVideoControl::VWGraphSegment *)MSVideoControl::VWGraphSegment::VWGraphSegment(
                                                           (MSVideoControl::VWGraphSegment *)&v109,
                                                           *((struct IUnknown **)this + 85));
          DefaultVR = CVidCtl::Compose(this, v56, v55, (int *)this + 191);
          v109 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v110);
          v106 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v107);
          if ( DefaultVR < 0 )
          {
            CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "Can't compose input and audio.");
            goto LABEL_28;
          }
        }
      }
      Forward_Sequence<ATL::CComQIPtr<IMSVidInputDevices,&__s_GUID const _GUID_c5702cd1_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidInputDevices,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::begin(
        (char *)this + 688,
        v134);
      while ( 1 )
      {
        v58 = Forward_Sequence<ATL::CComQIPtr<IMSVidFeatures,&__s_GUID const _GUID_c5702cd5_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidFeatures,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::end(
                v57,
                v113);
        v59 = ATL::CComVariant::operator==(v135, v58 + 8);
        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v113);
        if ( v59 )
          break;
        v138 = -1;
        v60 = (const struct ATL::CComVariant *)enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator*(
                                                 v134,
                                                 &pvarg);
        v61 = (struct MSVideoControl::VWGraphSegment *)MSVideoControl::VWGraphSegment::VWGraphSegment(
                                                         (MSVideoControl::VWGraphSegment *)&v106,
                                                         v60);
        v62 = (struct MSVideoControl::VWGraphSegment *)MSVideoControl::VWGraphSegment::VWGraphSegment(
                                                         (MSVideoControl::VWGraphSegment *)&v109,
                                                         *((struct IUnknown **)this + 85));
        DefaultVR = CVidCtl::Compose(this, v62, v61, &v138);
        v109 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v110);
        v106 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v107);
        if ( pvarg.vt == 4095 )
          pvarg.vt = 8;
        VariantClear(&pvarg);
        if ( DefaultVR < 0 )
        {
          CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "Can't compose output segment with input");
          CVidCtl::ReleaseDefaultRenderer(this, v6, v10);
          v20 = (VARIANTARG *)v134;
          goto LABEL_37;
        }
        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator++(v134);
      }
      enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v134);
      if ( *((_QWORD *)this + 91) )
      {
        Forward_Sequence<ATL::CComQIPtr<IMSVidInputDevices,&__s_GUID const _GUID_c5702cd1_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidInputDevices,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::begin(
          (char *)this + 720,
          v118);
LABEL_104:
        v64 = Forward_Sequence<ATL::CComQIPtr<IMSVidFeatures,&__s_GUID const _GUID_c5702cd5_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidFeatures,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::end(
                v63,
                &v115);
        v65 = ATL::CComVariant::operator==(v119, v64 + 8);
        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&v115);
        if ( !v65 )
        {
          LODWORD(v136) = -1;
          v66 = (struct IMSVidGraphSegment *)*((_QWORD *)this + 88);
          if ( v66 )
          {
            v67 = (struct MSVideoControl::VWGraphSegment *)MSVideoControl::VWGraphSegment::VWGraphSegment(
                                                             (MSVideoControl::VWGraphSegment *)&v106,
                                                             v66);
            v68 = (const struct ATL::CComVariant *)enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator*(
                                                     v118,
                                                     &v112);
            v69 = (struct MSVideoControl::VWGraphSegment *)MSVideoControl::VWGraphSegment::VWGraphSegment(
                                                             (MSVideoControl::VWGraphSegment *)&v109,
                                                             v68);
            v70 = CVidCtl::Compose(this, v69, v67, (int *)&v136);
            v109 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v110);
            if ( v112.vt == 4095 )
              v112.vt = 8;
            VariantClear(&v112);
            v106 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v107);
            if ( v70 < 0 )
              CVidCtlTrace::Trace(
                &gCVidCtlTrace,
                5u,
                "CVidCtl::BuildGraph",
                "Can't compose feature segment with renderers");
          }
          v71 = (struct IUnknown *)*((_QWORD *)this + 89);
          if ( v71 )
          {
            v72 = (struct MSVideoControl::VWGraphSegment *)MSVideoControl::VWGraphSegment::VWGraphSegment(
                                                             (MSVideoControl::VWGraphSegment *)&v128,
                                                             v71);
            v73 = (const struct ATL::CComVariant *)enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator*(
                                                     v118,
                                                     &v112);
            v74 = (struct MSVideoControl::VWGraphSegment *)MSVideoControl::VWGraphSegment::VWGraphSegment(
                                                             (MSVideoControl::VWGraphSegment *)&v126,
                                                             v73);
            v75 = CVidCtl::Compose(this, v74, v72, (int *)&v136);
            v126 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v127);
            if ( v112.vt == 4095 )
              v112.vt = 8;
            VariantClear(&v112);
            v128 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v129);
            if ( v75 < 0 )
              CVidCtlTrace::Trace(
                &gCVidCtlTrace,
                5u,
                "CVidCtl::BuildGraph",
                "Can't compose feature segment with Video Renderer ");
          }
          Forward_Sequence<ATL::CComQIPtr<IMSVidInputDevices,&__s_GUID const _GUID_c5702cd1_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidInputDevices,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::begin(
            (char *)this + 688,
            v113);
          while ( 1 )
          {
            v77 = Forward_Sequence<ATL::CComQIPtr<IMSVidFeatures,&__s_GUID const _GUID_c5702cd5_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidFeatures,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::end(
                    v76,
                    &v115);
            v78 = ATL::CComVariant::operator==(v114, v77 + 8);
            enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&v115);
            if ( v78 )
            {
              enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v113);
              enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator++(v118);
              goto LABEL_104;
            }
            v79 = (const struct ATL::CComVariant *)enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator*(
                                                     v113,
                                                     &v115);
            v80 = (struct MSVideoControl::VWGraphSegment *)MSVideoControl::VWGraphSegment::VWGraphSegment(
                                                             (MSVideoControl::VWGraphSegment *)&pvarg,
                                                             v79);
            v81 = (const struct ATL::CComVariant *)enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator*(
                                                     v118,
                                                     &v112);
            v82 = (struct MSVideoControl::VWGraphSegment *)MSVideoControl::VWGraphSegment::VWGraphSegment(
                                                             (MSVideoControl::VWGraphSegment *)&v111,
                                                             v81);
            DefaultVR = CVidCtl::Compose(this, v82, v80, (int *)&v136);
            *(_QWORD *)&v111.vt = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v111.decVal.Lo32);
            if ( v112.vt == 4095 )
              v112.vt = 8;
            VariantClear(&v112);
            *(_QWORD *)&pvarg.vt = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&pvarg.decVal.Lo32);
            if ( v115.vt == 4095 )
              v115.vt = 8;
            VariantClear(&v115);
            if ( DefaultVR < 0 )
              break;
            enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator++(v113);
          }
          CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "Can't compose output segment with feature.");
          CVidCtl::ReleaseDefaultRenderer(this, v6, v10);
          enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v113);
          v20 = (VARIANTARG *)v118;
          goto LABEL_37;
        }
        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v118);
      }
      CVidCtl::RouteStreams(this);
      CVidCtl::SetExtents(this);
      *((_BYTE *)this + 889) = 0;
      v83 = MSVideoControl::VWGraphSegment::VWGraphSegment(
              (MSVideoControl::VWGraphSegment *)&pvarg,
              *((struct IUnknown **)this + 85));
      DefaultVR = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v83 + 8) + 96LL))(*(_QWORD *)(v83 + 8));
      *(_QWORD *)&pvarg.vt = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&pvarg.decVal.Lo32);
      if ( (int)(DefaultVR + 0x80000000) >= 0 && DefaultVR != -2147467263 )
      {
        CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "PostBuild call for input failed");
        goto LABEL_28;
      }
      if ( !*((_QWORD *)this + 91) )
      {
LABEL_140:
        memset(&v115, 0, sizeof(v115));
        v106 = 0;
        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(
          &v111,
          &v106,
          &v115);
        v90 = Forward_Sequence<ATL::CComQIPtr<IMSVidInputDevices,&__s_GUID const _GUID_c5702cd1_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidInputDevices,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::begin(
                (char *)this + 688,
                &v112);
        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator=(
          &v111,
          v90);
        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&v112);
        while ( 1 )
        {
          v92 = Forward_Sequence<ATL::CComQIPtr<IMSVidFeatures,&__s_GUID const _GUID_c5702cd5_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidFeatures,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::end(
                  v91,
                  &v112);
          v93 = ATL::CComVariant::operator==(&v111.decVal.Lo32, v92 + 8);
          enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&v112);
          if ( v93 )
            break;
          v94 = (const struct ATL::CComVariant *)enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator*(
                                                   &v111,
                                                   &v112);
          v95 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&pvarg, v94);
          DefaultVR = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v95 + 8) + 96LL))(*(_QWORD *)(v95 + 8));
          *(_QWORD *)&pvarg.vt = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&pvarg.decVal.Lo32);
          if ( v112.vt == 4095 )
            v112.vt = 8;
          VariantClear(&v112);
          if ( ((DefaultVR + 0x80000000) & 0x80000000) == 0 && DefaultVR != -2147467263 )
          {
            CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "Can't PostBuild output segment.");
            CVidCtl::ReleaseDefaultRenderer(this, v6, v10);
            goto LABEL_138;
          }
          enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator++(&v111);
        }
        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&v111);
        v96 = (struct IMSVidGraphSegment *)*((_QWORD *)this + 88);
        if ( !v96
          || (v97 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&pvarg, v96),
              DefaultVR = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v97 + 8) + 96LL))(*(_QWORD *)(v97 + 8)),
              *(_QWORD *)&pvarg.vt = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable',
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&pvarg.decVal.Lo32),
              ((DefaultVR + 0x80000000) & 0x80000000) != 0)
          || DefaultVR == -2147467263 )
        {
          v98 = (struct IUnknown *)*((_QWORD *)this + 89);
          if ( !v98
            || (v99 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&pvarg, v98),
                DefaultVR = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v99 + 8) + 96LL))(*(_QWORD *)(v99 + 8)),
                *(_QWORD *)&pvarg.vt = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable',
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&pvarg.decVal.Lo32),
                ((DefaultVR + 0x80000000) & 0x80000000) != 0)
            || DefaultVR == -2147467263 )
          {
            ATL::CComQIPtr<IMediaEventSink,&__s_GUID const _GUID_56a868a2_0ad4_11ce_b03a_0020af0ba770>::CComQIPtr<IMediaEventSink,&__s_GUID const _GUID_56a868a2_0ad4_11ce_b03a_0020af0ba770>(
              &v116,
              *((_QWORD *)this + 71));
            (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v116 + 24LL))(v116, 768, 0, 0);
            CVidCtl::OnMediaEvent(this, v100, v101, v102, v105);
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v116);
            goto LABEL_157;
          }
          CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "PostBuild call to Audio Renderer Failed");
        }
        else
        {
          CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "PostBuild call to Video Renderer Failed");
        }
        goto LABEL_28;
      }
      memset(&v115, 0, sizeof(v115));
      v106 = 0;
      enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(
        &v111,
        &v106,
        &v115);
      v84 = Forward_Sequence<ATL::CComQIPtr<IMSVidInputDevices,&__s_GUID const _GUID_c5702cd1_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidInputDevices,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::begin(
              (char *)this + 720,
              &v112);
      enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator=(
        &v111,
        v84);
      enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&v112);
      while ( 1 )
      {
        v86 = Forward_Sequence<ATL::CComQIPtr<IMSVidFeatures,&__s_GUID const _GUID_c5702cd5_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidFeatures,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::end(
                v85,
                &v112);
        v87 = ATL::CComVariant::operator==(&v111.decVal.Lo32, v86 + 8);
        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&v112);
        if ( v87 )
        {
          enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(&v111);
          goto LABEL_140;
        }
        v88 = (const struct ATL::CComVariant *)enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator*(
                                                 &v111,
                                                 &v112);
        v89 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&pvarg, v88);
        DefaultVR = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v89 + 8) + 96LL))(*(_QWORD *)(v89 + 8));
        *(_QWORD *)&pvarg.vt = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&pvarg.decVal.Lo32);
        if ( v112.vt == 4095 )
          v112.vt = 8;
        VariantClear(&v112);
        if ( (int)(DefaultVR + 0x80000000) >= 0 && DefaultVR != -2147467263 )
          break;
        enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator++(&v111);
      }
      CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "Can't PostBuild feature segment.");
      CVidCtl::ReleaseDefaultRenderer(this, v6, v10);
LABEL_138:
      v20 = &v111;
LABEL_37:
      enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(v20);
      goto LABEL_7;
    }
    if ( *((_BYTE *)this + 890) )
      goto LABEL_24;
    DefaultVR = CVidCtl::LoadDefaultAR(this);
    if ( DefaultVR < 0 )
    {
      CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "LoadDefaultAR failed");
      goto LABEL_7;
    }
    if ( *((_QWORD *)this + 89) )
    {
      v10 = 1;
      goto LABEL_24;
    }
    CVidCtlTrace::Trace(&gCVidCtlTrace, 5u, "CVidCtl::BuildGraph", "LoadDefaultAR returned NULL Audio Renderer");
LABEL_13:
    v5 = -2147418113;
    goto LABEL_157;
  }
  v5 = 0;
LABEL_157:
  CGRLocker::~CGRLocker((CGRLocker *)&v117);
  return v5;
}

```

## disassembly

```asm
0x1800c4134  push    rbp
0x1800c4136  push    rbx
0x1800c4137  push    rsi
0x1800c4138  push    rdi
0x1800c4139  push    r12
0x1800c413b  push    r13
0x1800c413d  push    r14
0x1800c413f  push    r15
0x1800c4141  lea     rbp, [rsp-108h]
0x1800c4149  sub     rsp, 208h
0x1800c4150  mov     rsi, rcx
0x1800c4153  lea     rax, [rcx+1E8h]
0x1800c415a  mov     [rbp+140h+var_150], rax
0x1800c415e  mov     byte ptr [rax], 1
0x1800c4161  call    ?OnMediaEvent@CVidCtl@@QEAA_JI_K_JAEAH@Z; CVidCtl::OnMediaEvent(uint,unsigned __int64,__int64,int &)
0x1800c4166  cmp     dword ptr [rsi+228h], 0FFFFFFFFh
0x1800c416d  jz      short loc_1800C417F
0x1800c416f  cmp     byte ptr [rsi+379h], 1
0x1800c4176  jz      short loc_1800C417F
0x1800c4178  xor     edi, edi
0x1800c417a  jmp     loc_1800C548F
0x1800c417f  xor     edi, edi
0x1800c4181  mov     r15b, dil
0x1800c4184  mov     rdx, [rsi+2C0h]
0x1800c418b  test    rdx, rdx
0x1800c418e  jz      short loc_1800C41F7
0x1800c4190  lea     rcx, [rbp+140h+arg_0]
0x1800c4197  call    ??0?$CComQIPtr@UIMSVidAudioRendererDevices@@$1?_GUID_c5702cd4_9b79_11d3_b654_00c04f79498e@@3U__s_GUID@@B@ATL@@QEAA@PEAUIMSVidAudioRendererDevices@@@Z; ATL::CComQIPtr<IMSVidAudioRendererDevices,&__s_GUID const _GUID_c5702cd4_9b79_11d3_b654_00c04f79498e>::CComQIPtr<IMSVidAudioRendererDevices,&__s_GUID const _GUID_c5702cd4_9b79_11d3_b654_00c04f79498e>(IMSVidAudioRendererDevices *)
0x1800c419c  nop
0x1800c419d  mov     rcx, [rax]
0x1800c41a0  mov     r9, [rcx]
0x1800c41a3  mov     rax, rsi
0x1800c41a6  lea     rdx, [rsi+148h]
0x1800c41ad  neg     rax
0x1800c41b0  sbb     r8, r8
0x1800c41b3  and     rdx, r8
0x1800c41b6  mov     rax, [r9+40h]
0x1800c41ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c41bf  mov     ebx, eax
0x1800c41c1  lea     rcx, [rbp+140h+arg_0]
0x1800c41c8  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c41cd  test    ebx, ebx
0x1800c41cf  jns     short loc_1800C424C
0x1800c41d1  lea     r9, aPutContainerFa; "put_Container failed for Video Renderer"
0x1800c41d8  lea     r8, aCvidctlBuildgr; "CVidCtl::BuildGraph"
0x1800c41df  mov     edx, 5; unsigned int
0x1800c41e4  lea     rcx, ?gCVidCtlTrace@@3VCVidCtlTrace@@A; this
0x1800c41eb  call    ?Trace@CVidCtlTrace@@QEAAJKPEBD0ZZ; CVidCtlTrace::Trace(ulong,char const *,char const *,...)
0x1800c41f0  mov     edi, ebx
0x1800c41f2  jmp     loc_1800C548F
0x1800c41f7  cmp     [rsi+37Bh], dil
0x1800c41fe  jnz     short loc_1800C424C
0x1800c4200  mov     rcx, rsi; this
0x1800c4203  call    ?LoadDefaultVR@CVidCtl@@IEAAJXZ; CVidCtl::LoadDefaultVR(void)
0x1800c4208  mov     ebx, eax
0x1800c420a  test    eax, eax
0x1800c420c  jns     short loc_1800C4217
0x1800c420e  lea     r9, aLoaddefaultvrF; "LoadDefaultVR failed"
0x1800c4215  jmp     short loc_1800C41D8
0x1800c4217  cmp     [rsi+2C0h], rdi
0x1800c421e  jnz     short loc_1800C4249
0x1800c4220  lea     r9, aLoaddefaultvrR; "LoadDefaultVR returned NULL Video Rende"...
0x1800c4227  lea     r8, aCvidctlBuildgr; "CVidCtl::BuildGraph"
0x1800c422e  mov     edx, 5; unsigned int
0x1800c4233  lea     rcx, ?gCVidCtlTrace@@3VCVidCtlTrace@@A; this
0x1800c423a  call    ?Trace@CVidCtlTrace@@QEAAJKPEBD0ZZ; CVidCtlTrace::Trace(ulong,char const *,char const *,...)
0x1800c423f  mov     edi, 8000FFFFh
0x1800c4244  jmp     loc_1800C548F
0x1800c4249  mov     r15b, 1
0x1800c424c  mov     r14b, dil
0x1800c424f  mov     rdx, [rsi+2C8h]
0x1800c4256  test    rdx, rdx
0x1800c4259  jz      short loc_1800C42A8
0x1800c425b  lea     rcx, [rbp+140h+arg_0]
0x1800c4262  call    ??0?$CComQIPtr@UIMSVidGraphSegment@@$1?_GUID_238dec54_adeb_4005_a349_f772b9afebc4@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>(IUnknown *)
0x1800c4267  nop
0x1800c4268  mov     rcx, [rax]
0x1800c426b  mov     r9, [rcx]
0x1800c426e  mov     rax, rsi
0x1800c4271  lea     rdx, [rsi+148h]
0x1800c4278  neg     rax
0x1800c427b  sbb     r8, r8
0x1800c427e  and     rdx, r8
0x1800c4281  mov     rax, [r9+40h]
0x1800c4285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c428a  mov     ebx, eax
0x1800c428c  lea     rcx, [rbp+140h+arg_0]
0x1800c4293  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c4298  test    ebx, ebx
0x1800c429a  jns     short loc_1800C42E3
0x1800c429c  lea     r9, aPutContainerFa_0; "put_Container failed for Audio Renderer"
0x1800c42a3  jmp     loc_1800C41D8
0x1800c42a8  cmp     [rsi+37Ah], dil
0x1800c42af  jnz     short loc_1800C42E3
0x1800c42b1  mov     rcx, rsi; this
0x1800c42b4  call    ?LoadDefaultAR@CVidCtl@@IEAAJXZ; CVidCtl::LoadDefaultAR(void)
0x1800c42b9  mov     ebx, eax
0x1800c42bb  test    eax, eax
0x1800c42bd  jns     short loc_1800C42CB
0x1800c42bf  lea     r9, aLoaddefaultarF; "LoadDefaultAR failed"
0x1800c42c6  jmp     loc_1800C41D8
0x1800c42cb  cmp     [rsi+2C8h], rdi
0x1800c42d2  jnz     short loc_1800C42E0
0x1800c42d4  lea     r9, aLoaddefaultarR; "LoadDefaultAR returned NULL Audio Rende"...
0x1800c42db  jmp     loc_1800C4227
0x1800c42e0  mov     r14b, 1
0x1800c42e3  mov     rdx, [rsi+2A8h]
0x1800c42ea  test    rdx, rdx
0x1800c42ed  jnz     short loc_1800C433A
0x1800c42ef  lea     r9, aInputSegmentRe; "Input segment required"
0x1800c42f6  lea     r8, aCvidctlBuildgr; "CVidCtl::BuildGraph"
0x1800c42fd  mov     edx, 5; unsigned int
0x1800c4302  lea     rcx, ?gCVidCtlTrace@@3VCVidCtlTrace@@A; this
0x1800c4309  call    ?Trace@CVidCtlTrace@@QEAAJKPEBD0ZZ; CVidCtlTrace::Trace(ulong,char const *,char const *,...)
0x1800c430e  mov     r8b, r14b; bool
0x1800c4311  mov     dl, r15b; bool
0x1800c4314  mov     rcx, rsi; this
0x1800c4317  call    ?ReleaseDefaultRenderer@CVidCtl@@IEAAX_N0@Z; CVidCtl::ReleaseDefaultRenderer(bool,bool)
0x1800c431c  mov     r9, cs:hInstance
0x1800c4323  mov     ecx, 0C0040512h; dwMessageId
0x1800c4328  mov     r8d, 0C0040512h
0x1800c432e  call    ?Error@?$CComCoClass@VCVidCtl@@$1?CLSID_MSVidCtl@@3U_GUID@@B@ATL@@SAJIAEBU_GUID@@JPEAUHINSTANCE__@@@Z; ATL::CComCoClass<CVidCtl,&_GUID const CLSID_MSVidCtl>::Error(uint,_GUID const &,long,HINSTANCE__ *)
0x1800c4333  mov     edi, eax
0x1800c4335  jmp     loc_1800C548F
0x1800c433a  lea     rcx, [rbp+140h+arg_0]
0x1800c4341  call    ??0?$CComQIPtr@UIMSVidGraphSegment@@$1?_GUID_238dec54_adeb_4005_a349_f772b9afebc4@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>(IUnknown *)
0x1800c4346  nop
0x1800c4347  mov     rcx, [rax]
0x1800c434a  mov     rax, rsi
0x1800c434d  lea     rdx, [rsi+148h]
0x1800c4354  neg     rax
0x1800c4357  sbb     r12, r12
0x1800c435a  and     r12, rdx
0x1800c435d  mov     rax, [rcx]
0x1800c4360  mov     rdx, r12
0x1800c4363  mov     rax, [rax+40h]
0x1800c4367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c436c  mov     ebx, eax
0x1800c436e  lea     rcx, [rbp+140h+arg_0]
0x1800c4375  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c437a  test    ebx, ebx
0x1800c437c  jns     short loc_1800C43B0
0x1800c437e  lea     r9, aCanTLoadInputS; "Can't load input segment."
0x1800c4385  lea     r8, aCvidctlBuildgr; "CVidCtl::BuildGraph"
0x1800c438c  mov     edx, 5; unsigned int
0x1800c4391  lea     rcx, ?gCVidCtlTrace@@3VCVidCtlTrace@@A; this
0x1800c4398  call    ?Trace@CVidCtlTrace@@QEAAJKPEBD0ZZ; CVidCtlTrace::Trace(ulong,char const *,char const *,...)
0x1800c439d  mov     r8b, r14b; bool
0x1800c43a0  mov     dl, r15b; bool
0x1800c43a3  mov     rcx, rsi; this
0x1800c43a6  call    ?ReleaseDefaultRenderer@CVidCtl@@IEAAX_N0@Z; CVidCtl::ReleaseDefaultRenderer(bool,bool)
0x1800c43ab  jmp     loc_1800C41F0
0x1800c43b0  lea     r13, [rsi+2D0h]
0x1800c43b7  cmp     [r13+8], rdi
0x1800c43bb  jz      loc_1800C44CA
0x1800c43c1  lea     rdx, [rbp+140h+var_A8]
0x1800c43c8  mov     rcx, r13
0x1800c43cb  call    ?begin@?$Forward_Sequence@V?$CComQIPtr@UIMSVidInputDevices@@$1?_GUID_c5702cd1_9b79_11d3_b654_00c04f79498e@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@2@VCComVariant@2@UIMSVidInputDevices@@UIEnumVARIANT@@UtagVARIANT@@V?$allocator@UtagVARIANT@@@std@@@@QEAA?AV?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@XZ; Forward_Sequence<ATL::CComQIPtr<IMSVidInputDevices,&__s_GUID const _GUID_c5702cd1_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidInputDevices,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::begin(void)
0x1800c43d0  nop
0x1800c43d1  lea     rdx, [rbp+140h+var_198]
0x1800c43d5  call    ?end@?$Forward_Sequence@V?$CComQIPtr@UIMSVidFeatures@@$1?_GUID_c5702cd5_9b79_11d3_b654_00c04f79498e@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@2@VCComVariant@2@UIMSVidFeatures@@UIEnumVARIANT@@UtagVARIANT@@V?$allocator@UtagVARIANT@@@std@@@@QEAA?AV?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@XZ; Forward_Sequence<ATL::CComQIPtr<IMSVidFeatures,&__s_GUID const _GUID_c5702cd5_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidFeatures,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::end(void)
0x1800c43da  lea     rdx, [rax+8]
0x1800c43de  lea     rcx, [rbp+140h+var_A0]
0x1800c43e5  call    ??8CComVariant@ATL@@QEBA_NAEBUtagVARIANT@@@Z; ATL::CComVariant::operator==(tagVARIANT const &)
0x1800c43ea  mov     bl, al
0x1800c43ec  lea     rcx, [rbp+140h+var_198]
0x1800c43f0  call    ??1?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@QEAA@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(void)
0x1800c43f5  test    bl, bl
0x1800c43f7  jnz     loc_1800C44BE
0x1800c43fd  lea     rdx, [rsp+240h+pvarg]
0x1800c4402  lea     rcx, [rbp+140h+var_A8]
0x1800c4409  call    ??D?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@QEBA?AVCComVariant@ATL@@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator*(void)
0x1800c440e  nop
0x1800c440f  mov     rdx, rax; struct ATL::CComVariant *
0x1800c4412  lea     rcx, [rsp+240h+var_210]; this
0x1800c4417  call    ??0VWGraphSegment@MSVideoControl@@QEAA@AEBVCComVariant@ATL@@@Z; MSVideoControl::VWGraphSegment::VWGraphSegment(ATL::CComVariant const &)
0x1800c441c  nop
0x1800c441d  mov     rcx, [rax+8]
0x1800c4421  mov     rax, [rcx]
0x1800c4424  mov     rdx, r12
0x1800c4427  mov     rax, [rax+40h]
0x1800c442b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4430  mov     ebx, eax
0x1800c4432  lea     rax, ??_7?$Forward_Sequence@V?$CComQIPtr@UIMSVidGraphSegment@@$1?_GUID_238dec54_adeb_4005_a349_f772b9afebc4@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIEnumFilters@@$1?IID_IEnumFilters@@3U_GUID@@B@2@VDSFilter@@UIMSVidGraphSegment@@UIEnumFilters@@PEAUIBaseFilter@@V?$allocator@VDSFilter@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable'
0x1800c4439  mov     [rsp+240h+var_210], rax
0x1800c443e  lea     rcx, [rsp+240h+var_208]
0x1800c4443  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c4448  nop
0x1800c4449  mov     eax, 0FFFh
0x1800c444e  cmp     word ptr [rsp+240h+pvarg], ax
0x1800c4453  jnz     short loc_1800C445F
0x1800c4455  mov     eax, 8
0x1800c445a  mov     word ptr [rsp+240h+pvarg], ax
0x1800c445f  lea     rcx, [rsp+240h+pvarg]; pvarg
0x1800c4464  call    cs:__imp_VariantClear
0x1800c446a  test    ebx, ebx
0x1800c446c  js      short loc_1800C447F
0x1800c446e  lea     rcx, [rbp+140h+var_A8]
0x1800c4475  call    ??E?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@QEAAAEAV0@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator++(void)
0x1800c447a  jmp     loc_1800C43D1
0x1800c447f  lea     r9, aCanTLoadFeatur; "Can't load feature segment"
0x1800c4486  lea     r8, aCvidctlBuildgr; "CVidCtl::BuildGraph"
0x1800c448d  mov     edx, 5; unsigned int
0x1800c4492  lea     rcx, ?gCVidCtlTrace@@3VCVidCtlTrace@@A; this
0x1800c4499  call    ?Trace@CVidCtlTrace@@QEAAJKPEBD0ZZ; CVidCtlTrace::Trace(ulong,char const *,char const *,...)
0x1800c449e  mov     r8b, r14b; bool
0x1800c44a1  mov     dl, r15b; bool
0x1800c44a4  mov     rcx, rsi; this
0x1800c44a7  call    ?ReleaseDefaultRenderer@CVidCtl@@IEAAX_N0@Z; CVidCtl::ReleaseDefaultRenderer(bool,bool)
0x1800c44ac  nop
0x1800c44ad  lea     rcx, [rbp+140h+var_A8]
0x1800c44b4  call    ??1?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@QEAA@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(void)
0x1800c44b9  jmp     loc_1800C41F0
0x1800c44be  lea     rcx, [rbp+140h+var_A8]
0x1800c44c5  call    ??1?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@QEAA@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(void)
0x1800c44ca  lea     rcx, [rsi+2B0h]
0x1800c44d1  lea     rdx, [rbp+140h+var_88]
0x1800c44d8  call    ?begin@?$Forward_Sequence@V?$CComQIPtr@UIMSVidInputDevices@@$1?_GUID_c5702cd1_9b79_11d3_b654_00c04f79498e@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@2@VCComVariant@2@UIMSVidInputDevices@@UIEnumVARIANT@@UtagVARIANT@@V?$allocator@UtagVARIANT@@@std@@@@QEAA?AV?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@XZ; Forward_Sequence<ATL::CComQIPtr<IMSVidInputDevices,&__s_GUID const _GUID_c5702cd1_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidInputDevices,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::begin(void)
0x1800c44dd  nop
0x1800c44de  lea     rdx, [rbp+140h+var_198]
0x1800c44e2  call    ?end@?$Forward_Sequence@V?$CComQIPtr@UIMSVidFeatures@@$1?_GUID_c5702cd5_9b79_11d3_b654_00c04f79498e@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@2@VCComVariant@2@UIMSVidFeatures@@UIEnumVARIANT@@UtagVARIANT@@V?$allocator@UtagVARIANT@@@std@@@@QEAA?AV?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@XZ; Forward_Sequence<ATL::CComQIPtr<IMSVidFeatures,&__s_GUID const _GUID_c5702cd5_9b79_11d3_b654_00c04f79498e>,ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IMSVidFeatures,IEnumVARIANT,tagVARIANT,std::allocator<tagVARIANT>>::end(void)
0x1800c44e7  lea     rdx, [rax+8]
0x1800c44eb  lea     rcx, [rbp+140h+var_80]
0x1800c44f2  call    ??8CComVariant@ATL@@QEBA_NAEBUtagVARIANT@@@Z; ATL::CComVariant::operator==(tagVARIANT const &)
0x1800c44f7  mov     bl, al
0x1800c44f9  lea     rcx, [rbp+140h+var_198]
0x1800c44fd  call    ??1?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@QEAA@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(void)
0x1800c4502  test    bl, bl
0x1800c4504  jnz     loc_1800C45C6
0x1800c450a  lea     rdx, [rsp+240h+pvarg]
0x1800c450f  lea     rcx, [rbp+140h+var_88]
0x1800c4516  call    ??D?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@QEBA?AVCComVariant@ATL@@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator*(void)
0x1800c451b  nop
0x1800c451c  mov     rdx, rax; struct ATL::CComVariant *
0x1800c451f  lea     rcx, [rsp+240h+var_210]; this
0x1800c4524  call    ??0VWGraphSegment@MSVideoControl@@QEAA@AEBVCComVariant@ATL@@@Z; MSVideoControl::VWGraphSegment::VWGraphSegment(ATL::CComVariant const &)
0x1800c4529  nop
0x1800c452a  mov     rcx, [rax+8]
0x1800c452e  mov     rax, [rcx]
0x1800c4531  mov     rdx, r12
0x1800c4534  mov     rax, [rax+40h]
0x1800c4538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c453d  mov     ebx, eax
0x1800c453f  lea     rax, ??_7?$Forward_Sequence@V?$CComQIPtr@UIMSVidGraphSegment@@$1?_GUID_238dec54_adeb_4005_a349_f772b9afebc4@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIEnumFilters@@$1?IID_IEnumFilters@@3U_GUID@@B@2@VDSFilter@@UIMSVidGraphSegment@@UIEnumFilters@@PEAUIBaseFilter@@V?$allocator@VDSFilter@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable'
0x1800c4546  mov     [rsp+240h+var_210], rax
0x1800c454b  lea     rcx, [rsp+240h+var_208]
0x1800c4550  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c4555  nop
0x1800c4556  mov     eax, 0FFFh
0x1800c455b  cmp     word ptr [rsp+240h+pvarg], ax
0x1800c4560  jnz     short loc_1800C456C
0x1800c4562  mov     eax, 8
0x1800c4567  mov     word ptr [rsp+240h+pvarg], ax
0x1800c456c  lea     rcx, [rsp+240h+pvarg]; pvarg
0x1800c4571  call    cs:__imp_VariantClear
0x1800c4577  test    ebx, ebx
0x1800c4579  js      short loc_1800C458C
0x1800c457b  lea     rcx, [rbp+140h+var_88]
0x1800c4582  call    ??E?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@QEAAAEAV0@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::operator++(void)
0x1800c4587  jmp     loc_1800C44DE
0x1800c458c  lea     r9, aCanTLoadOutput; "Can't load output segment"
0x1800c4593  lea     r8, aCvidctlBuildgr; "CVidCtl::BuildGraph"
0x1800c459a  mov     edx, 5; unsigned int
0x1800c459f  lea     rcx, ?gCVidCtlTrace@@3VCVidCtlTrace@@A; this
0x1800c45a6  call    ?Trace@CVidCtlTrace@@QEAAJKPEBD0ZZ; CVidCtlTrace::Trace(ulong,char const *,char const *,...)
0x1800c45ab  mov     r8b, r14b; bool
0x1800c45ae  mov     dl, r15b; bool
0x1800c45b1  mov     rcx, rsi; this
0x1800c45b4  call    ?ReleaseDefaultRenderer@CVidCtl@@IEAAX_N0@Z; CVidCtl::ReleaseDefaultRenderer(bool,bool)
0x1800c45b9  nop
0x1800c45ba  lea     rcx, [rbp+140h+var_88]
0x1800c45c1  jmp     loc_1800C44B4
0x1800c45c6  lea     rcx, [rbp+140h+var_88]
0x1800c45cd  call    ??1?$enumerator_iterator@V?$CComQIPtr@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@B@ATL@@VCComVariant@2@UIEnumVARIANT@@UtagVARIANT@@_J@@QEAA@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumVARIANT,&_GUID const IID_IEnumVARIANT>,ATL::CComVariant,IEnumVARIANT,tagVARIANT,__int64>(void)
0x1800c45d2  mov     rdx, [rsi+2A8h]; struct IUnknown *
0x1800c45d9  lea     rcx, [rsp+240h+var_210]; this
0x1800c45de  call    ??0VWGraphSegment@MSVideoControl@@QEAA@PEAUIUnknown@@@Z; MSVideoControl::VWGraphSegment::VWGraphSegment(IUnknown *)
0x1800c45e3  nop
0x1800c45e4  mov     rcx, [rax+8]
0x1800c45e8  mov     rax, [rcx]
0x1800c45eb  mov     rax, [rax+58h]
0x1800c45ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c45f4  mov     ebx, eax
0x1800c45f6  lea     rax, ??_7?$Forward_Sequence@V?$CComQIPtr@UIMSVidGraphSegment@@$1?_GUID_238dec54_adeb_4005_a349_f772b9afebc4@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIEnumFilters@@$1?IID_IEnumFilters@@3U_GUID@@B@2@VDSFilter@@UIMSVidGraphSegment@@UIEnumFilters@@PEAUIBaseFilter@@V?$allocator@VDSFilter@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable'
0x1800c45fd  mov     [rsp+240h+var_210], rax
0x1800c4602  lea     rcx, [rsp+240h+var_208]
0x1800c4607  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c460c  mov     r12d, 80000000h
0x1800c4612  lea     eax, [rbx+r12]
0x1800c4616  test    r12d, eax
0x1800c4619  jnz     short loc_1800C462F
0x1800c461b  cmp     ebx, 80004001h
0x1800c4621  jz      short loc_1800C462F
0x1800c4623  lea     r9, aBuildCallForIn; "Build call for input failed"
0x1800c462a  jmp     loc_1800C4385
0x1800c462f  cmp     [rsi+2D8h], rdi
0x1800c4636  jz      loc_1800C477A
0x1800c463c  xorps   xmm0, xmm0
0x1800c463f  xor     eax, eax
0x1800c4641  movups  xmmword ptr [rsp+240h+pvarg], xmm0
  ... truncated ...
```
