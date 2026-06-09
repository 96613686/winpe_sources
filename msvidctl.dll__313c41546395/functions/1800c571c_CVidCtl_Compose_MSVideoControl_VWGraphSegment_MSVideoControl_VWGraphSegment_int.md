# CVidCtl::Compose(MSVideoControl::VWGraphSegment &,MSVideoControl::VWGraphSegment &,int &)

- ea: `0x1800c571c`
- end: `0x1800c7405`
- name: `?Compose@CVidCtl@@IEAAJAEAVVWGraphSegment@MSVideoControl@@0AEAH@Z`
- size: `7401`
- prototype: `int(CVidCtl *__hidden this, struct MSVideoControl::VWGraphSegment *, struct MSVideoControl::VWGraphSegment *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800c4134`

## callees

- `0x180004640`
- `0x180006b38`
- `0x18002a3f8`
- `0x1800568f8`
- `0x18005817c`
- `0x1800581ac`
- `0x1800c571c`
- `0x1800c8cd0`
- `0x1800dd7ac`
- `0x1800dd7e0`
- `0x1800f8010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800c59c8`
- `ole32!CoCreateInstance` at `0x1800c5e77`
- `ole32!CoCreateInstance` at `0x1800c59c8`
- `ole32!CoCreateInstance` at `0x1800c5e77`
- `SLC!SLGetWindowsInformationDWORD` at `0x1800c6dbd`
- `SLC!SLGetWindowsInformationDWORD` at `0x1800c6de2`
- `SLC!SLGetWindowsInformationDWORD` at `0x1800c6dbd`
- `SLC!SLGetWindowsInformationDWORD` at `0x1800c6de2`

## string_xrefs

- `0x1800c6db6`: `MCLicense-6F20786B-7DFC-4d72-B98B-FAA8699E5758-AdvancedConfigurationEnabled`

## pseudocode

```c
// Hidden C++ exception states: #wind=72
__int64 __fastcall CVidCtl::Compose(
        CVidCtl *this,
        struct MSVideoControl::VWGraphSegment *a2,
        struct MSVideoControl::VWGraphSegment *a3,
        int *a4)
{
  __int64 v8; // rax
  int v9; // ebx
  __int64 v10; // rax
  _QWORD *v11; // rax
  __int64 v12; // rax
  _QWORD *v13; // rax
  __int64 v14; // rax
  _QWORD *v15; // rax
  char v16; // di
  GUID *v17; // rcx
  __int64 v18; // rax
  DWORD v19; // ebx
  _QWORD *v20; // rax
  __int64 v21; // rax
  _QWORD *v22; // rax
  bool v23; // di
  struct IMSVidGraphSegment *v24; // rcx
  int v25; // eax
  int v26; // ebx
  __int64 v28; // rax
  DWORD v29; // ebx
  _QWORD *v30; // rax
  __int64 v31; // rax
  _QWORD *v32; // rax
  bool v33; // di
  __int64 v34; // rax
  DWORD v35; // ebx
  _QWORD *v36; // rax
  __int64 v37; // rax
  _QWORD *v38; // rax
  __int64 v39; // rax
  _QWORD *v40; // rax
  char v41; // di
  __int64 v42; // rax
  DWORD v43; // ebx
  _QWORD *v44; // rax
  __int64 v45; // rax
  _QWORD *v46; // rax
  __int64 v47; // rax
  _QWORD *v48; // rax
  __int64 v49; // rax
  _QWORD *v50; // rax
  char v51; // di
  __int64 v52; // rax
  DWORD v53; // ebx
  _QWORD *v54; // rax
  __int64 v55; // rax
  _QWORD *v56; // rax
  bool v57; // di
  __int64 v58; // rax
  DWORD v59; // ebx
  _QWORD *v60; // rax
  __int64 v61; // rax
  _QWORD *v62; // rax
  __int64 v63; // rax
  _QWORD *v64; // rax
  __int64 v65; // rax
  _QWORD *v66; // rax
  char v67; // di
  __int64 v68; // rax
  DWORD v69; // ebx
  _QWORD *v70; // rax
  __int64 v71; // rax
  _QWORD *v72; // rax
  __int64 v73; // rax
  _QWORD *v74; // rax
  __int64 v75; // rax
  _QWORD *v76; // rax
  char v77; // di
  __int64 v78; // rax
  DWORD v79; // ebx
  _QWORD *v80; // rax
  __int64 v81; // rax
  _QWORD *v82; // rax
  bool v83; // di
  __int64 v84; // rax
  DWORD v85; // ebx
  _QWORD *v86; // rax
  __int64 v87; // rax
  _QWORD *v88; // rax
  bool v89; // di
  __int64 v90; // rax
  signed int v91; // ebx
  _QWORD *v92; // rax
  __int64 v93; // rax
  _QWORD *v94; // rax
  __int64 v95; // rax
  _QWORD *v96; // rax
  char v97; // di
  __int64 v98; // rax
  int v99; // ebx
  _QWORD *v100; // rax
  __int64 v101; // rax
  _QWORD *v102; // rax
  bool v103; // di
  __int64 v104; // rax
  DWORD v105; // ebx
  _QWORD *v106; // rax
  __int64 v107; // rax
  _QWORD *v108; // rax
  bool v109; // di
  __int64 v110; // rax
  DWORD v111; // ebx
  _QWORD *v112; // rax
  __int64 v113; // rax
  _QWORD *v114; // rax
  __int64 v115; // rax
  _QWORD *v116; // rax
  __int64 v117; // rax
  _QWORD *v118; // rax
  __int64 v119; // rax
  _QWORD *v120; // rax
  char v121; // di
  __int64 v122; // rax
  DWORD v123; // ebx
  _QWORD *v124; // rax
  __int64 v125; // rax
  _QWORD *v126; // rax
  bool v127; // di
  __int64 v128; // rax
  DWORD v129; // ebx
  _QWORD *v130; // rax
  __int64 v131; // rax
  _QWORD *v132; // rax
  bool v133; // di
  __int64 v134; // rax
  DWORD v135; // ebx
  _QWORD *v136; // rax
  __int64 v137; // rax
  _QWORD *v138; // rax
  bool v139; // di
  __int64 v140; // rax
  DWORD v141; // ebx
  _QWORD *v142; // rax
  __int64 v143; // rax
  _QWORD *v144; // rax
  __int64 v145; // rax
  _QWORD *v146; // rax
  char v147; // di
  __int64 v148; // rax
  DWORD v149; // ebx
  _QWORD *v150; // rax
  __int64 v151; // rax
  _QWORD *v152; // rax
  __int64 v153; // rax
  _QWORD *v154; // rax
  __int64 v155; // rax
  _QWORD *v156; // rax
  char v157; // di
  __int64 v158; // rax
  DWORD v159; // ebx
  _QWORD *v160; // rax
  __int64 v161; // rax
  _QWORD *v162; // rax
  bool v163; // di
  __int64 v164; // rax
  DWORD v165; // ebx
  _QWORD *v166; // rax
  __int64 v167; // rax
  _QWORD *v168; // rax
  __int64 v169; // rax
  _QWORD *v170; // rax
  __int64 v171; // rax
  _QWORD *v172; // rax
  char v173; // di
  __int64 v174; // rax
  DWORD v175; // ebx
  _QWORD *v176; // rax
  __int64 v177; // rax
  _QWORD *v178; // rax
  bool v179; // di
  __int64 v180; // rax
  signed int v181; // ebx
  _QWORD *v182; // rax
  __int64 v183; // rax
  _QWORD *v184; // rax
  bool v185; // di
  __int64 v186; // rax
  int v187; // ebx
  _QWORD *v188; // rax
  __int64 v189; // rax
  _QWORD *v190; // rax
  bool v191; // di
  __int64 v192; // rax
  DWORD v193; // ebx
  _QWORD *v194; // rax
  __int64 v195; // rax
  _QWORD *v196; // rax
  bool v197; // di
  struct IMSVidGraphSegment *v198; // rsi
  HRESULT (__stdcall *QueryInterface)(IMSVidGraphSegment *, const IID *const, void **); // rdi
  __int64 v200; // rbx
  _QWORD *v201; // rax
  DWORD pdwValue; // [rsp+30h] [rbp-99h] BYREF
  struct IMSVidGraphSegment *ppv; // [rsp+38h] [rbp-91h] BYREF
  void **v204; // [rsp+40h] [rbp-89h] BYREF
  _BYTE v205[8]; // [rsp+48h] [rbp-81h] BYREF
  void **v206; // [rsp+50h] [rbp-79h] BYREF
  _BYTE v207[8]; // [rsp+58h] [rbp-71h] BYREF
  void **v208; // [rsp+60h] [rbp-69h] BYREF
  _BYTE v209[8]; // [rsp+68h] [rbp-61h] BYREF
  void **v210; // [rsp+70h] [rbp-59h] BYREF
  _BYTE v211[8]; // [rsp+78h] [rbp-51h] BYREF
  void **v212; // [rsp+80h] [rbp-49h] BYREF
  _BYTE v213[8]; // [rsp+88h] [rbp-41h] BYREF
  _BYTE v214[16]; // [rsp+90h] [rbp-39h] BYREF
  _BYTE v215[16]; // [rsp+A0h] [rbp-29h] BYREF
  _BYTE v216[16]; // [rsp+B0h] [rbp-19h] BYREF
  _BYTE v217[16]; // [rsp+C0h] [rbp-9h] BYREF
  _BYTE v218[16]; // [rsp+D0h] [rbp+7h] BYREF

  ppv = 0;
  v8 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a2);
  v9 = 1;
  pdwValue = 1;
  if ( *(_OWORD *)MSVideoControl::VWGraphSegment::Category(v8, &v212) != *(_OWORD *)&GUID_a799a800_a46d_11d0_a18c_00a02401dcd4 )
    goto LABEL_9;
  v10 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v210, a3);
  v9 = 3;
  pdwValue = 3;
  v11 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v10, v218);
  if ( *v11 == *(_QWORD *)&CLSID_MSVidVideoRenderer.Data1 && v11[1] == *(_QWORD *)CLSID_MSVidVideoRenderer.Data4 )
    goto LABEL_8;
  v12 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v208, a3);
  v9 = 7;
  pdwValue = 7;
  v13 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v12, v215);
  if ( *v13 == *(_QWORD *)&CLSID_MSVidVMR9.Data1 && v13[1] == *(_QWORD *)CLSID_MSVidVMR9.Data4 )
    goto LABEL_8;
  v14 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v206, a3);
  v9 = 15;
  pdwValue = 15;
  v15 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v14, v214);
  if ( *v15 == *(_QWORD *)&CLSID_MSVidEVR.Data1 && v15[1] == *(_QWORD *)CLSID_MSVidEVR.Data4 )
LABEL_8:
    v16 = 1;
  else
LABEL_9:
    v16 = 0;
  if ( (v9 & 8) != 0 )
  {
    v9 &= ~8u;
    v206 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v207);
  }
  if ( (v9 & 4) != 0 )
  {
    v9 &= ~4u;
    v208 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v209);
  }
  if ( (v9 & 2) != 0 )
  {
    v9 &= ~2u;
    v210 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v211);
  }
  if ( (v9 & 1) != 0 )
  {
    v9 &= ~1u;
    v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
  }
  if ( v16 )
  {
    v17 = &CLSID_MSVidAnalogCaptureToOverlayMixer;
    goto LABEL_32;
  }
  v18 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v206, a2);
  v19 = v9 | 0x10;
  pdwValue = v19;
  v20 = (_QWORD *)MSVideoControl::VWGraphSegment::Category(v18, v214);
  v23 = 0;
  if ( *v20 == *(_QWORD *)&GUID_a799a800_a46d_11d0_a18c_00a02401dcd4.Data1
    && v20[1] == *(_QWORD *)GUID_a799a800_a46d_11d0_a18c_00a02401dcd4.Data4 )
  {
    v21 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a3);
    v19 |= 0x20u;
    pdwValue = v19;
    v22 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v21, v215);
    if ( *v22 == *(_QWORD *)&CLSID_MSVidStreamBufferSink.Data1 && v22[1] == *(_QWORD *)CLSID_MSVidStreamBufferSink.Data4 )
      v23 = 1;
  }
  if ( (v19 & 0x20) != 0 )
  {
    v19 &= ~0x20u;
    v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
  }
  if ( (v19 & 0x10) != 0 )
  {
    v19 &= ~0x10u;
    v206 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v207);
  }
  if ( v23 )
  {
    v17 = &CLSID_MSVidAnalogCaptureToStreamBufferSink;
    goto LABEL_32;
  }
  v28 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v206, a2);
  v29 = v19 | 0x40;
  pdwValue = v29;
  v30 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v28, v214);
  v33 = 0;
  if ( *v30 == *(_QWORD *)&CLSID_MSVidBDATunerDevice.Data1 && v30[1] == *(_QWORD *)CLSID_MSVidBDATunerDevice.Data4 )
  {
    v31 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a3);
    v29 |= 0x80u;
    pdwValue = v29;
    v32 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v31, v215);
    if ( *v32 == *(_QWORD *)&CLSID_MSVidStreamBufferSink.Data1 && v32[1] == *(_QWORD *)CLSID_MSVidStreamBufferSink.Data4 )
      v33 = 1;
  }
  if ( (v29 & 0x80u) != 0 )
  {
    v29 &= ~0x80u;
    v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
  }
  if ( (v29 & 0x40) != 0 )
  {
    v29 &= ~0x40u;
    v206 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v207);
  }
  if ( v33 )
  {
    v17 = &CLSID_MSVidDigitalCaptureToStreamBufferSink;
    goto LABEL_32;
  }
  v34 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v208, a2);
  v35 = v29 | 0x100;
  pdwValue = v35;
  v36 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v34, v214);
  if ( *v36 != *(_QWORD *)&CLSID_MSVidBDATunerDevice.Data1 || v36[1] != *(_QWORD *)CLSID_MSVidBDATunerDevice.Data4 )
  {
    v37 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v206, a2);
    v35 |= 0x200u;
    pdwValue = v35;
    v38 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v37, v215);
    if ( *v38 != *(_QWORD *)&CLSID_MSVidWebDVD.Data1 || v38[1] != *(_QWORD *)CLSID_MSVidWebDVD.Data4 )
      goto LABEL_56;
  }
  v39 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a3);
  v35 |= 0x400u;
  pdwValue = v35;
  v40 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v39, v218);
  if ( *v40 == *(_QWORD *)&CLSID_MSVidClosedCaptioning.Data1 && v40[1] == *(_QWORD *)CLSID_MSVidClosedCaptioning.Data4 )
    v41 = 1;
  else
LABEL_56:
    v41 = 0;
  if ( (v35 & 0x400) != 0 )
  {
    v35 &= ~0x400u;
    v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
  }
  if ( (v35 & 0x200) != 0 )
  {
    v35 &= ~0x200u;
    v206 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v207);
  }
  if ( (v35 & 0x100) != 0 )
  {
    v35 &= ~0x100u;
    v208 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v209);
  }
  if ( v41 )
  {
    v17 = &CLSID_MSVidMPEG2DecoderToClosedCaptioning;
    goto LABEL_32;
  }
  v42 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v210, a2);
  v43 = v35 | 0x800;
  pdwValue = v43;
  v44 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v42, v214);
  if ( *v44 != *(_QWORD *)&CLSID_MSVidFilePlaybackDevice.Data1
    || v44[1] != *(_QWORD *)CLSID_MSVidFilePlaybackDevice.Data4 )
  {
    goto LABEL_74;
  }
  v45 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v208, a3);
  v43 |= 0x1000u;
  pdwValue = v43;
  v46 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v45, v215);
  if ( *v46 == *(_QWORD *)&CLSID_MSVidVideoRenderer.Data1 && v46[1] == *(_QWORD *)CLSID_MSVidVideoRenderer.Data4 )
    goto LABEL_73;
  v47 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v206, a3);
  v43 |= 0x2000u;
  pdwValue = v43;
  v48 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v47, v218);
  if ( *v48 == *(_QWORD *)&CLSID_MSVidVMR9.Data1 && v48[1] == *(_QWORD *)CLSID_MSVidVMR9.Data4 )
    goto LABEL_73;
  v49 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a3);
  v43 |= 0x4000u;
  pdwValue = v43;
  v50 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v49, &v212);
  if ( *v50 == *(_QWORD *)&CLSID_MSVidEVR.Data1 && v50[1] == *(_QWORD *)CLSID_MSVidEVR.Data4 )
LABEL_73:
    v51 = 1;
  else
LABEL_74:
    v51 = 0;
  if ( (v43 & 0x4000) != 0 )
  {
    v43 &= ~0x4000u;
    v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
  }
  if ( (v43 & 0x2000) != 0 )
  {
    v43 &= ~0x2000u;
    v206 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v207);
  }
  if ( (v43 & 0x1000) != 0 )
  {
    v43 &= ~0x1000u;
    v208 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v209);
  }
  if ( (v43 & 0x800) != 0 )
  {
    v43 &= ~0x800u;
    v210 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v211);
  }
  if ( v51 )
  {
    v17 = &CLSID_MSVidFilePlaybackToVideoRenderer;
    goto LABEL_32;
  }
  v52 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v206, a2);
  v53 = v43 | 0x8000;
  pdwValue = v53;
  v54 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v52, v214);
  v57 = 0;
  if ( *v54 == *(_QWORD *)&CLSID_MSVidFilePlaybackDevice.Data1
    && v54[1] == *(_QWORD *)CLSID_MSVidFilePlaybackDevice.Data4 )
  {
    v55 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a3);
    v53 |= 0x10000u;
    pdwValue = v53;
    v56 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v55, v215);
    if ( *v56 == *(_QWORD *)&CLSID_MSVidAudioRenderer.Data1 && v56[1] == *(_QWORD *)CLSID_MSVidAudioRenderer.Data4 )
      v57 = 1;
  }
  if ( (v53 & 0x10000) != 0 )
  {
    v53 &= ~0x10000u;
    v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
  }
  if ( (v53 & 0x8000) != 0 )
  {
    v53 &= ~0x8000u;
    v206 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v207);
  }
  if ( v57 )
  {
    if ( CoCreateInstance(
           &CLSID_MSVidFilePlaybackToAudioRenderer,
           0,
           0x17u,
           &GUID_1c15d483_911d_11d2_b632_00c04f79498e,
           (LPVOID *)&ppv) < 0 )
      goto LABEL_34;
    v24 = ppv;
    if ( !ppv )
      goto LABEL_34;
    goto LABEL_386;
  }
  v58 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v210, a2);
  v59 = v53 | 0x20000;
  pdwValue = v59;
  v60 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v58, v214);
  if ( *v60 != *(_QWORD *)&CLSID_MSVidWebDVD.Data1 || v60[1] != *(_QWORD *)CLSID_MSVidWebDVD.Data4 )
    goto LABEL_108;
  v61 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v208, a3);
  v59 |= 0x40000u;
  pdwValue = v59;
  v62 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v61, v215);
  if ( *v62 == *(_QWORD *)&CLSID_MSVidVideoRenderer.Data1 && v62[1] == *(_QWORD *)CLSID_MSVidVideoRenderer.Data4 )
    goto LABEL_107;
  v63 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v206, a3);
  v59 |= 0x80000u;
  pdwValue = v59;
  v64 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v63, v218);
  if ( *v64 == *(_QWORD *)&CLSID_MSVidVMR9.Data1 && v64[1] == *(_QWORD *)CLSID_MSVidVMR9.Data4 )
    goto LABEL_107;
  v65 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a3);
  v59 |= 0x100000u;
  pdwValue = v59;
  v66 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v65, &v212);
  if ( *v66 == *(_QWORD *)&CLSID_MSVidEVR.Data1 && v66[1] == *(_QWORD *)CLSID_MSVidEVR.Data4 )
LABEL_107:
    v67 = 1;
  else
LABEL_108:
    v67 = 0;
  if ( (v59 & 0x100000) != 0 )
  {
    v59 &= ~0x100000u;
    v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
  }
  if ( (v59 & 0x80000) != 0 )
  {
    v59 &= ~0x80000u;
    v206 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v207);
  }
  if ( (v59 & 0x40000) != 0 )
  {
    v59 &= ~0x40000u;
    v208 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v209);
  }
  if ( (v59 & 0x20000) != 0 )
  {
    v59 &= ~0x20000u;
    v210 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v211);
  }
  if ( v67 )
  {
    v17 = &CLSID_MSVidWebDVDToVideoRenderer;
    goto LABEL_32;
  }
  v68 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v210, a2);
  v69 = v59 | 0x200000;
  pdwValue = v69;
  v70 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v68, v214);
  if ( *v70 != *(_QWORD *)&CLSID_MSVidWebDVD.Data1 || v70[1] != *(_QWORD *)CLSID_MSVidWebDVD.Data4 )
  {
    v71 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v208, a2);
    v69 |= 0x400000u;
    pdwValue = v69;
    v72 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v71, v215);
    if ( *v72 != *(_QWORD *)&CLSID_MSVidStreamBufferSource.Data1
      || v72[1] != *(_QWORD *)CLSID_MSVidStreamBufferSource.Data4 )
    {
      v73 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v206, a2);
      v69 |= 0x800000u;
      pdwValue = v69;
      v74 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v73, v218);
      if ( *v74 != *(_QWORD *)&CLSID_MSVidStreamBufferV2Source.Data1
        || v74[1] != *(_QWORD *)CLSID_MSVidStreamBufferV2Source.Data4 )
      {
        goto LABEL_128;
      }
    }
  }
  v75 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a3);
  v69 |= 0x1000000u;
  pdwValue = v69;
  v76 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v75, &v212);
  if ( *v76 == *(_QWORD *)&CLSID_MSVidAudioRenderer.Data1 && v76[1] == *(_QWORD *)CLSID_MSVidAudioRenderer.Data4 )
    v77 = 1;
  else
LABEL_128:
    v77 = 0;
  if ( (v69 & 0x1000000) != 0 )
  {
    v69 &= ~0x1000000u;
    v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
  }
  if ( (v69 & 0x800000) != 0 )
  {
    v69 &= ~0x800000u;
    v206 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v207);
  }
  if ( (v69 & 0x400000) != 0 )
  {
    v69 &= ~0x400000u;
    v208 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v209);
  }
  if ( (v69 & 0x200000) != 0 )
  {
    v69 &= ~0x200000u;
    v210 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v211);
  }
  if ( v77 )
  {
    v17 = &CLSID_MSVidWebDVDToAudioRenderer;
    goto LABEL_32;
  }
  v78 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v206, a2);
  v79 = v69 | 0x2000000;
  pdwValue = v79;
  v80 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v78, v214);
  v83 = 0;
  if ( *v80 == *(_QWORD *)&CLSID_MSVidBDATunerDevice.Data1 && v80[1] == *(_QWORD *)CLSID_MSVidBDATunerDevice.Data4 )
  {
    v81 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a3);
    v79 |= 0x4000000u;
    pdwValue = v79;
    v82 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v81, v215);
    if ( *v82 == *(_QWORD *)&CLSID_MSVidITVCapture.Data1 && v82[1] == *(_QWORD *)CLSID_MSVidITVCapture.Data4 )
      v83 = 1;
  }
  if ( (v79 & 0x4000000) != 0 )
  {
    v79 &= ~0x4000000u;
    v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
  }
  if ( (v79 & 0x2000000) != 0 )
  {
    v79 &= ~0x2000000u;
    v206 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v207);
  }
  if ( v83 )
  {
    v17 = &CLSID_MSVidDigitalCaptureToITV;
    goto LABEL_32;
  }
  v84 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v206, a2);
  v85 = v79 | 0x8000000;
  pdwValue = v85;
  v86 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v84, v214);
  v89 = 0;
  if ( *v86 == *(_QWORD *)&CLSID_MSVidITVCapture.Data1 && v86[1] == *(_QWORD *)CLSID_MSVidITVCapture.Data4 )
  {
    v87 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a3);
    v85 |= 0x10000000u;
    pdwValue = v85;
    v88 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v87, v215);
    if ( *v88 == *(_QWORD *)&CLSID_MSVidStreamBufferSink.Data1 && v88[1] == *(_QWORD *)CLSID_MSVidStreamBufferSink.Data4 )
      v89 = 1;
  }
  if ( (v85 & 0x10000000) != 0 )
  {
    v85 &= ~0x10000000u;
    v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
  }
  if ( (v85 & 0x8000000) != 0 )
  {
    v85 &= ~0x8000000u;
    v206 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v207);
  }
  if ( v89 )
  {
    v17 = &CLSID_MSVidITVToStreamBufferSink;
    goto LABEL_32;
  }
  v90 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v208, a2);
  v91 = v85 | 0x20000000;
  pdwValue = v91;
  v92 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v90, v214);
  if ( *v92 != *(_QWORD *)&CLSID_MSVidStreamBufferSource.Data1
    || v92[1] != *(_QWORD *)CLSID_MSVidStreamBufferSource.Data4 )
  {
    v93 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v206, a2);
    v91 |= 0x40000000u;
    pdwValue = v91;
    v94 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v93, v215);
    if ( *v94 != *(_QWORD *)&CLSID_MSVidStreamBufferV2Source.Data1
      || v94[1] != *(_QWORD *)CLSID_MSVidStreamBufferV2Source.Data4 )
    {
      goto LABEL_170;
    }
  }
  v95 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a3);
  v91 |= 0x80000000;
  pdwValue = v91;
  v96 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v95, v218);
  if ( *v96 == *(_QWORD *)&CLSID_MSVidITVPlayback.Data1 && v96[1] == *(_QWORD *)CLSID_MSVidITVPlayback.Data4 )
    v97 = 1;
  else
LABEL_170:
    v97 = 0;
  if ( v91 < 0 )
  {
    v91 &= ~0x80000000;
    v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
  }
  if ( (v91 & 0x40000000) != 0 )
  {
    v91 &= ~0x40000000u;
    v206 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v207);
  }
  if ( (v91 & 0x20000000) != 0 )
  {
    v208 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v209);
  }
  if ( v97 )
  {
    v17 = &CLSID_MSVidSBESourceToITV;
    goto LABEL_32;
  }
  v98 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v206, a2);
  v99 = 1;
  pdwValue = 1;
  v100 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v98, v214);
  v103 = 0;
  if ( *v100 == *(_QWORD *)&CLSID_MSVidCCA.Data1 && v100[1] == *(_QWORD *)CLSID_MSVidCCA.Data4 )
  {
    v101 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a3);
    v99 = 3;
    pdwValue = 3;
    v102 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v101, v215);
    if ( *v102 == *(_QWORD *)&CLSID_MSVidStreamBufferSink.Data1
      && v102[1] == *(_QWORD *)CLSID_MSVidStreamBufferSink.Data4 )
    {
      v103 = 1;
    }
  }
  if ( (v99 & 2) != 0 )
  {
    v99 &= ~2u;
    v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
  }
  if ( (v99 & 1) != 0 )
  {
    v99 &= ~1u;
    v206 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v207);
  }
  if ( v103 )
  {
    v17 = &CLSID_MSVidCCAToStreamBufferSink;
    goto LABEL_32;
  }
  v104 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v206, a2);
  v105 = v99 | 4;
  pdwValue = v105;
  v106 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v104, v214);
  v109 = 0;
  if ( *v106 == *(_QWORD *)&CLSID_MSVidEncoder.Data1 && v106[1] == *(_QWORD *)CLSID_MSVidEncoder.Data4 )
  {
    v107 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a3);
    v105 |= 8u;
    pdwValue = v105;
    v108 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v107, v215);
    if ( *v108 == *(_QWORD *)&CLSID_MSVidStreamBufferSink.Data1
      && v108[1] == *(_QWORD *)CLSID_MSVidStreamBufferSink.Data4 )
    {
      v109 = 1;
    }
  }
  if ( (v105 & 8) != 0 )
  {
    v105 &= ~8u;
    v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
  }
  if ( (v105 & 4) != 0 )
  {
    v105 &= ~4u;
    v206 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v207);
  }
  if ( v109 )
  {
    v17 = &CLSID_MSVidEncoderToStreamBufferSink;
    goto LABEL_32;
  }
  v110 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v212, a2);
  v111 = v105 | 0x10;
  pdwValue = v111;
  v112 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v110, v214);
  if ( *v112 != *(_QWORD *)&CLSID_MSVidStreamBufferSource.Data1
    || v112[1] != *(_QWORD *)CLSID_MSVidStreamBufferSource.Data4 )
  {
    v113 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v210, a2);
    v111 |= 0x20u;
    pdwValue = v111;
    v114 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v113, v215);
    if ( *v114 != *(_QWORD *)&CLSID_MSVidStreamBufferV2Source.Data1
      || v114[1] != *(_QWORD *)CLSID_MSVidStreamBufferV2Source.Data4 )
    {
      goto LABEL_214;
    }
  }
  v115 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v208, a3);
  v111 |= 0x40u;
  pdwValue = v111;
  v116 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v115, v218);
  if ( *v116 == *(_QWORD *)&CLSID_MSVidVideoRenderer.Data1 && v116[1] == *(_QWORD *)CLSID_MSVidVideoRenderer.Data4 )
    goto LABEL_213;
  v117 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v206, a3);
  v111 |= 0x80u;
  pdwValue = v111;
  v118 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v117, v216);
  if ( *v118 == *(_QWORD *)&CLSID_MSVidVMR9.Data1 && v118[1] == *(_QWORD *)CLSID_MSVidVMR9.Data4 )
    goto LABEL_213;
  v119 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a3);
  v111 |= 0x100u;
  pdwValue = v111;
  v120 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v119, v217);
  if ( *v120 == *(_QWORD *)&CLSID_MSVidEVR.Data1 && v120[1] == *(_QWORD *)CLSID_MSVidEVR.Data4 )
LABEL_213:
    v121 = 1;
  else
LABEL_214:
    v121 = 0;
  if ( (v111 & 0x100) != 0 )
  {
    v111 &= ~0x100u;
    v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
  }
  if ( (v111 & 0x80u) != 0 )
  {
    v111 &= ~0x80u;
    v206 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v207);
  }
  if ( (v111 & 0x40) != 0 )
  {
    v111 &= ~0x40u;
    v208 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v209);
  }
  if ( (v111 & 0x20) != 0 )
  {
    v111 &= ~0x20u;
    v210 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v211);
  }
  if ( (v111 & 0x10) != 0 )
  {
    v111 &= ~0x10u;
    v212 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v213);
  }
  if ( v121 )
  {
    v17 = &CLSID_MSVidStreamBufferSourceToVideoRenderer;
    goto LABEL_32;
  }
  v122 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a2);
  v123 = v111 | 0x200;
  pdwValue = v123;
  v124 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v122, v217);
  v127 = 0;
  if ( *v124 == *(_QWORD *)&CLSID_MSVidBDATunerDevice.Data1 && v124[1] == *(_QWORD *)CLSID_MSVidBDATunerDevice.Data4 )
  {
    v125 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v212, a3);
    v123 |= 0x400u;
    pdwValue = v123;
    v126 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v125, v216);
    if ( *v126 == *(_QWORD *)&CLSID_MSVidCCA.Data1 && v126[1] == *(_QWORD *)CLSID_MSVidCCA.Data4 )
      v127 = 1;
  }
  if ( (v123 & 0x400) != 0 )
  {
    v123 &= ~0x400u;
    v212 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v213);
  }
  if ( (v123 & 0x200) != 0 )
  {
    v123 &= ~0x200u;
    v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
  }
  if ( v127 )
  {
    v17 = &CLSID_MSVidDigitalCaptureToCCA;
    goto LABEL_32;
  }
  v128 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a2);
  v129 = v123 | 0x800;
  pdwValue = v129;
  v130 = (_QWORD *)MSVideoControl::VWGraphSegment::Category(v128, v217);
  v133 = 0;
  if ( *v130 == *(_QWORD *)&GUID_a799a800_a46d_11d0_a18c_00a02401dcd4.Data1
    && v130[1] == *(_QWORD *)GUID_a799a800_a46d_11d0_a18c_00a02401dcd4.Data4 )
  {
    v131 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v212, a3);
    v129 |= 0x1000u;
    pdwValue = v129;
    v132 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v131, v216);
    if ( *v132 == *(_QWORD *)&CLSID_MSVidCCA.Data1 && v132[1] == *(_QWORD *)CLSID_MSVidCCA.Data4 )
      v133 = 1;
  }
  if ( (v129 & 0x1000) != 0 )
  {
    v129 &= ~0x1000u;
    v212 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v213);
  }
  if ( (v129 & 0x800) != 0 )
  {
    v129 &= ~0x800u;
    v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
  }
  if ( v133 )
  {
    v17 = &CLSID_MSVidAnalogCaptureToCCA;
    goto LABEL_32;
  }
  v134 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a2);
  v135 = v129 | 0x2000;
  pdwValue = v135;
  v136 = (_QWORD *)MSVideoControl::VWGraphSegment::Category(v134, v217);
  v139 = 0;
  if ( *v136 == *(_QWORD *)&GUID_a799a800_a46d_11d0_a18c_00a02401dcd4.Data1
    && v136[1] == *(_QWORD *)GUID_a799a800_a46d_11d0_a18c_00a02401dcd4.Data4 )
  {
    v137 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v212, a3);
    v135 |= 0x4000u;
    pdwValue = v135;
    v138 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v137, v216);
    if ( *v138 == *(_QWORD *)&CLSID_MSVidEncoder.Data1 && v138[1] == *(_QWORD *)CLSID_MSVidEncoder.Data4 )
      v139 = 1;
  }
  if ( (v135 & 0x4000) != 0 )
  {
    v135 &= ~0x4000u;
    v212 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v213);
  }
  if ( (v135 & 0x2000) != 0 )
  {
    v135 &= ~0x2000u;
    v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
  }
  if ( v139 )
  {
    v17 = &CLSID_MSVidAnalogTVToEncoder;
    goto LABEL_32;
  }
  v140 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v206, a2);
  v141 = v135 | 0x8000;
  pdwValue = v141;
  v142 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v140, v217);
  if ( *v142 != *(_QWORD *)&CLSID_MSVidStreamBufferSource.Data1
    || v142[1] != *(_QWORD *)CLSID_MSVidStreamBufferSource.Data4 )
  {
    v143 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a2);
    v141 |= 0x10000u;
    pdwValue = v141;
    v144 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v143, v216);
    if ( *v144 != *(_QWORD *)&CLSID_MSVidStreamBufferV2Source.Data1
      || v144[1] != *(_QWORD *)CLSID_MSVidStreamBufferV2Source.Data4 )
    {
      goto LABEL_272;
    }
  }
  if ( (v145 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v212, a3),
        v141 |= 0x20000u,
        pdwValue = v141,
        v146 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v145, v214),
        *v146 == *(_QWORD *)&CLSID_MSVidClosedCaptioning.Data1)
    && v146[1] == *(_QWORD *)CLSID_MSVidClosedCaptioning.Data4
    || *v146 == *(_QWORD *)&CLSID_MSVidClosedCaptioningSI.Data1
    && v146[1] == *(_QWORD *)CLSID_MSVidClosedCaptioningSI.Data4 )
  {
    v147 = 1;
  }
  else
  {
LABEL_272:
    v147 = 0;
  }
  if ( (v141 & 0x20000) != 0 )
  {
    v141 &= ~0x20000u;
    v212 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v213);
  }
  if ( (v141 & 0x10000) != 0 )
  {
    v141 &= ~0x10000u;
    v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
  }
  if ( (v141 & 0x8000) != 0 )
  {
    v141 &= ~0x8000u;
    v206 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v207);
  }
  if ( v147 )
  {
    v17 = &CLSID_MSVidSBESourceToCC;
    goto LABEL_32;
  }
  v148 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v208, a2);
  v149 = v141 | 0x40000;
  pdwValue = v149;
  v150 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v148, v217);
  if ( *v150 != *(_QWORD *)&CLSID_MSVidStreamBufferSource.Data1
    || v150[1] != *(_QWORD *)CLSID_MSVidStreamBufferSource.Data4 )
  {
    v151 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v206, a2);
    v149 |= 0x80000u;
    pdwValue = v149;
    v152 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v151, v216);
    if ( *v152 != *(_QWORD *)&CLSID_MSVidFilePlaybackDevice.Data1
      || v152[1] != *(_QWORD *)CLSID_MSVidFilePlaybackDevice.Data4 )
    {
      v153 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a2);
      v149 |= 0x100000u;
      pdwValue = v149;
      v154 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v153, v214);
      if ( *v154 != *(_QWORD *)&CLSID_MSVidStreamBufferV2Source.Data1
        || v154[1] != *(_QWORD *)CLSID_MSVidStreamBufferV2Source.Data4 )
      {
        goto LABEL_290;
      }
    }
  }
  v155 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v212, a3);
  v149 |= 0x200000u;
  pdwValue = v149;
  v156 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v155, v215);
  if ( *v156 == *(_QWORD *)&CLSID_MSVidGenericSink.Data1 && v156[1] == *(_QWORD *)CLSID_MSVidGenericSink.Data4 )
    v157 = 1;
  else
LABEL_290:
    v157 = 0;
  if ( (v149 & 0x200000) != 0 )
  {
    v149 &= ~0x200000u;
    v212 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v213);
  }
  if ( (v149 & 0x100000) != 0 )
  {
    v149 &= ~0x100000u;
    v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
  }
  if ( (v149 & 0x80000) != 0 )
  {
    v149 &= ~0x80000u;
    v206 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v207);
  }
  if ( (v149 & 0x40000) != 0 )
  {
    v149 &= ~0x40000u;
    v208 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v209);
  }
  if ( v157 )
    goto LABEL_300;
  v158 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a2);
  v159 = v149 | 0x400000;
  pdwValue = v159;
  v160 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v158, v217);
  v163 = 0;
  if ( *v160 == *(_QWORD *)&CLSID_MSVidWebDVD.Data1 && v160[1] == *(_QWORD *)CLSID_MSVidWebDVD.Data4 )
  {
    v161 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v212, a3);
    v159 |= 0x800000u;
    pdwValue = v159;
    v162 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v161, v216);
    if ( *v162 == *(_QWORD *)&CLSID_MSVidGenericSink.Data1 && v162[1] == *(_QWORD *)CLSID_MSVidGenericSink.Data4 )
      v163 = 1;
  }
  if ( (v159 & 0x800000) != 0 )
  {
    v159 &= ~0x800000u;
    v212 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v213);
  }
  if ( (v159 & 0x400000) != 0 )
  {
    v159 &= ~0x400000u;
    v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
  }
  if ( !v163 )
  {
    v164 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v208, a2);
    v165 = v159 | 0x1000000;
    pdwValue = v165;
    v166 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v164, v217);
    if ( *v166 != *(_QWORD *)&CLSID_MSVidClosedCaptioning.Data1
      || v166[1] != *(_QWORD *)CLSID_MSVidClosedCaptioning.Data4 )
    {
      goto LABEL_326;
    }
    v167 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v206, a3);
    v165 |= 0x2000000u;
    pdwValue = v165;
    v168 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v167, v216);
    if ( *v168 == *(_QWORD *)&CLSID_MSVidVideoRenderer.Data1 && v168[1] == *(_QWORD *)CLSID_MSVidVideoRenderer.Data4 )
      goto LABEL_325;
    v169 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a3);
    v165 |= 0x4000000u;
    pdwValue = v165;
    v170 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v169, v214);
    if ( *v170 == *(_QWORD *)&CLSID_MSVidVMR9.Data1 && v170[1] == *(_QWORD *)CLSID_MSVidVMR9.Data4 )
      goto LABEL_325;
    v171 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v212, a3);
    v165 |= 0x8000000u;
    pdwValue = v165;
    v172 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v171, v215);
    if ( *v172 == *(_QWORD *)&CLSID_MSVidEVR.Data1 && v172[1] == *(_QWORD *)CLSID_MSVidEVR.Data4 )
LABEL_325:
      v173 = 1;
    else
LABEL_326:
      v173 = 0;
    if ( (v165 & 0x8000000) != 0 )
    {
      v165 &= ~0x8000000u;
      v212 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v213);
    }
    if ( (v165 & 0x4000000) != 0 )
    {
      v165 &= ~0x4000000u;
      v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
    }
    if ( (v165 & 0x2000000) != 0 )
    {
      v165 &= ~0x2000000u;
      v206 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v207);
    }
    if ( (v165 & 0x1000000) != 0 )
    {
      v165 &= ~0x1000000u;
      v208 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v209);
    }
    if ( v173 )
    {
      v17 = &CLSID_MSVidCCToVMR;
    }
    else
    {
      v174 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a2);
      v175 = v165 | 0x10000000;
      pdwValue = v175;
      v176 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v174, v217);
      v179 = 0;
      if ( *v176 == *(_QWORD *)&CLSID_MSVidClosedCaptioning.Data1
        && v176[1] == *(_QWORD *)CLSID_MSVidClosedCaptioning.Data4 )
      {
        v177 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v212, a3);
        v175 |= 0x20000000u;
        pdwValue = v175;
        v178 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v177, v216);
        if ( *v178 == *(_QWORD *)&CLSID_MSVidAudioRenderer.Data1 && v178[1] == *(_QWORD *)CLSID_MSVidAudioRenderer.Data4 )
          v179 = 1;
      }
      if ( (v175 & 0x20000000) != 0 )
      {
        v175 &= ~0x20000000u;
        v212 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v213);
      }
      if ( (v175 & 0x10000000) != 0 )
      {
        v175 &= ~0x10000000u;
        v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
      }
      if ( v179 )
      {
        v17 = &CLSID_MSVidCCToAR;
      }
      else
      {
        v180 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a2);
        v181 = v175 | 0x40000000;
        pdwValue = v181;
        v182 = (_QWORD *)MSVideoControl::VWGraphSegment::Category(v180, v217);
        v185 = 0;
        if ( *v182 == *(_QWORD *)&GUID_a799a800_a46d_11d0_a18c_00a02401dcd4.Data1
          && v182[1] == *(_QWORD *)GUID_a799a800_a46d_11d0_a18c_00a02401dcd4.Data4 )
        {
          v183 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v212, a3);
          v181 |= 0x80000000;
          pdwValue = v181;
          v184 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v183, v216);
          if ( *v184 == *(_QWORD *)&CLSID_MSVidDataServices.Data1 && v184[1] == *(_QWORD *)CLSID_MSVidDataServices.Data4 )
            v185 = 1;
        }
        if ( v181 < 0 )
        {
          v181 &= ~0x80000000;
          v212 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v213);
        }
        if ( (v181 & 0x40000000) != 0 )
        {
          v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
        }
        if ( v185 )
        {
          v17 = &CLSID_MSVidAnalogCaptureToDataServices;
        }
        else
        {
          v186 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a2);
          v187 = 1;
          pdwValue = 1;
          v188 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v186, v217);
          v191 = 0;
          if ( *v188 == *(_QWORD *)&CLSID_MSVidXDS.Data1 && v188[1] == *(_QWORD *)CLSID_MSVidXDS.Data4 )
          {
            v189 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v212, a3);
            v187 = 3;
            pdwValue = 3;
            v190 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v189, v216);
            if ( *v190 == *(_QWORD *)&CLSID_MSVidStreamBufferSink.Data1
              && v190[1] == *(_QWORD *)CLSID_MSVidStreamBufferSink.Data4 )
            {
              v191 = 1;
            }
          }
          if ( (v187 & 2) != 0 )
          {
            v187 &= ~2u;
            v212 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v213);
          }
          if ( (v187 & 1) != 0 )
          {
            v187 &= ~1u;
            v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
          }
          if ( v191 )
          {
            v17 = &CLSID_MSVidDataServicesToStreamBufferSink;
          }
          else
          {
            v192 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v204, a2);
            v193 = v187 | 4;
            pdwValue = v193;
            v194 = (_QWORD *)MSVideoControl::VWGraphSegment::Category(v192, v217);
            v197 = 0;
            if ( *v194 == *(_QWORD *)&GUID_a799a800_a46d_11d0_a18c_00a02401dcd4.Data1
              && v194[1] == *(_QWORD *)GUID_a799a800_a46d_11d0_a18c_00a02401dcd4.Data4 )
            {
              v195 = MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v212, a3);
              v193 |= 8u;
              pdwValue = v193;
              v196 = (_QWORD *)MSVideoControl::VWGraphSegment::ClassID(v195, v216);
              if ( *v196 == *(_QWORD *)&CLSID_MSVidXDS.Data1 && v196[1] == *(_QWORD *)CLSID_MSVidXDS.Data4 )
                v197 = 1;
            }
            if ( (v193 & 8) != 0 )
            {
              LOBYTE(v193) = v193 & 0xF7;
              v212 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v213);
            }
            if ( (v193 & 4) != 0 )
            {
              v204 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v205);
            }
            if ( v197 )
              v17 = &CLSID_MSVidAnalogCaptureToXDS;
            else
              v17 = &CLSID_MSVidGenericComposite;
          }
        }
      }
    }
LABEL_32:
    if ( CoCreateInstance(v17, 0, 0x17u, &GUID_1c15d483_911d_11d2_b632_00c04f79498e, (LPVOID *)&ppv) < 0 )
    {
LABEL_34:
      v25 = ATL::CComCoClass<CVidCtl,&_GUID const CLSID_MSVidCtl>::Error(0xC0040529);
LABEL_35:
      v26 = v25;
LABEL_36:
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
      return (unsigned int)v26;
    }
    goto LABEL_33;
  }
  pdwValue = 0;
  if ( SLGetWindowsInformationDWORD(
         L"MCLicense-6F20786B-7DFC-4d72-B98B-FAA8699E5758-AdvancedConfigurationEnabled",
         &pdwValue) < 0 )
    goto LABEL_34;
  if ( pdwValue )
  {
    if ( SLGetWindowsInformationDWORD(L"MCLicense-9871786D-C2DE-4474-BDBB-C21A8B81B6C3-DVDRemotingEnabled", &pdwValue) < 0 )
      goto LABEL_34;
    if ( pdwValue )
    {
LABEL_300:
      v17 = &CLSID_MSVidSBESourceToGenericSink;
      goto LABEL_32;
    }
  }
LABEL_33:
  v24 = ppv;
  if ( !ppv )
    goto LABEL_34;
LABEL_386:
  v25 = ((__int64 (__fastcall *)(struct IMSVidGraphSegment *, _QWORD))v24->lpVtbl->put_Init)(v24, 0);
  if ( (int)(v25 + 0x80000000) >= 0 && v25 != -2147467263 )
    goto LABEL_35;
  MSVideoControl::VWGraphSegment::VWGraphSegment((MSVideoControl::VWGraphSegment *)&v206, ppv);
  if ( *((_QWORD *)this + 93) == *((_QWORD *)this + 94) )
  {
    std::vector<MSVideoControl::VWGraphSegment>::_Emplace_reallocate<MSVideoControl::VWGraphSegment const &>(
      (char *)this + 736,
      *((_QWORD *)this + 93),
      &v206);
  }
  else
  {
    MSVideoControl::VWGraphSegment::VWGraphSegment(
      *((MSVideoControl::VWGraphSegment **)this + 93),
      (const struct MSVideoControl::VWGraphSegment *)&v206);
    *((_QWORD *)this + 93) += 16LL;
  }
  *a4 = ((__int64)(*((_QWORD *)this + 93) - *((_QWORD *)this + 92)) >> 4) - 1;
  v26 = ((__int64 (__fastcall *)(struct IMSVidGraphSegment *, unsigned __int64))ppv->lpVtbl->put_Container)(
          ppv,
          ((unsigned __int64)this + 328) & -(__int64)(this != 0));
  if ( v26 < 0
    || (v198 = ppv,
        QueryInterface = ppv->lpVtbl[1].QueryInterface,
        v200 = *(_QWORD *)ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>(
                            &v208,
                            (char *)a3 + 8),
        v201 = (_QWORD *)ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>(
                           &v210,
                           (char *)a2 + 8),
        v26 = ((__int64 (__fastcall *)(struct IMSVidGraphSegment *, _QWORD, __int64))QueryInterface)(v198, *v201, v200),
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v210),
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v208),
        v26 < 0) )
  {
    v206 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v207);
    goto LABEL_36;
  }
  v206 = &Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v207);
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
  return 0;
}

```

## disassembly

```asm
0x1800c571c  push    rbp
0x1800c571e  push    rbx
0x1800c571f  push    rsi
0x1800c5720  push    rdi
0x1800c5721  push    r12
0x1800c5723  push    r14
0x1800c5725  push    r15
0x1800c5727  lea     rbp, [rsp-27h]
0x1800c572c  sub     rsp, 0F0h
0x1800c5733  mov     rax, cs:__security_cookie
0x1800c573a  xor     rax, rsp
0x1800c573d  mov     [rbp+57h+var_40], rax
0x1800c5741  mov     r12, r9
0x1800c5744  mov     r14, r8
0x1800c5747  mov     r15, rdx
0x1800c574a  mov     rsi, rcx
0x1800c574d  mov     [rsp+120h+pdwValue], 0
0x1800c5755  mov     [rsp+120h+pdwValue], 0
0x1800c575d  mov     [rsp+120h+pdwValue], 0
0x1800c5765  mov     [rsp+120h+var_E8], 0
0x1800c576e  lea     rcx, [rsp+120h+var_E0]; this
0x1800c5773  call    ??0VWGraphSegment@MSVideoControl@@QEAA@AEBV01@@Z; MSVideoControl::VWGraphSegment::VWGraphSegment(MSVideoControl::VWGraphSegment const &)
0x1800c5778  nop
0x1800c5779  mov     ebx, 1
0x1800c577e  mov     [rsp+120h+pdwValue], ebx
0x1800c5782  lea     rdx, [rbp+57h+var_A0]
0x1800c5786  mov     rcx, rax
0x1800c5789  call    ?Category@VWGraphSegment@MSVideoControl@@QEAA?AVGUID2@@XZ; MSVideoControl::VWGraphSegment::Category(void)
0x1800c578e  mov     rcx, [rax]
0x1800c5791  cmp     rcx, qword ptr cs:_GUID_a799a800_a46d_11d0_a18c_00a02401dcd4.Data1
0x1800c5798  jnz     loc_1800C5865
0x1800c579e  mov     rax, [rax+8]
0x1800c57a2  cmp     rax, qword ptr cs:_GUID_a799a800_a46d_11d0_a18c_00a02401dcd4.Data4
0x1800c57a9  jnz     loc_1800C5865
0x1800c57af  mov     rdx, r14; struct MSVideoControl::VWGraphSegment *
0x1800c57b2  lea     rcx, [rbp+57h+var_B0]; this
0x1800c57b6  call    ??0VWGraphSegment@MSVideoControl@@QEAA@AEBV01@@Z; MSVideoControl::VWGraphSegment::VWGraphSegment(MSVideoControl::VWGraphSegment const &)
0x1800c57bb  nop
0x1800c57bc  mov     ebx, 3
0x1800c57c1  mov     [rsp+120h+pdwValue], ebx
0x1800c57c5  lea     rdx, [rbp+57h+var_50]
0x1800c57c9  mov     rcx, rax
0x1800c57cc  call    ?ClassID@VWGraphSegment@MSVideoControl@@QEAA?AVGUID2@@XZ; MSVideoControl::VWGraphSegment::ClassID(void)
0x1800c57d1  mov     rcx, [rax]
0x1800c57d4  cmp     rcx, qword ptr cs:CLSID_MSVidVideoRenderer.Data1
0x1800c57db  jnz     short loc_1800C57EA
0x1800c57dd  mov     rax, [rax+8]
0x1800c57e1  cmp     rax, qword ptr cs:CLSID_MSVidVideoRenderer.Data4
0x1800c57e8  jz      short loc_1800C5860
0x1800c57ea  mov     rdx, r14; struct MSVideoControl::VWGraphSegment *
0x1800c57ed  lea     rcx, [rbp+57h+var_C0]; this
0x1800c57f1  call    ??0VWGraphSegment@MSVideoControl@@QEAA@AEBV01@@Z; MSVideoControl::VWGraphSegment::VWGraphSegment(MSVideoControl::VWGraphSegment const &)
0x1800c57f6  nop
0x1800c57f7  mov     ebx, 7
0x1800c57fc  mov     [rsp+120h+pdwValue], ebx
0x1800c5800  lea     rdx, [rbp+57h+var_80]
0x1800c5804  mov     rcx, rax
0x1800c5807  call    ?ClassID@VWGraphSegment@MSVideoControl@@QEAA?AVGUID2@@XZ; MSVideoControl::VWGraphSegment::ClassID(void)
0x1800c580c  mov     rcx, [rax]
0x1800c580f  cmp     rcx, qword ptr cs:CLSID_MSVidVMR9.Data1
0x1800c5816  jnz     short loc_1800C5825
0x1800c5818  mov     rax, [rax+8]
0x1800c581c  cmp     rax, qword ptr cs:CLSID_MSVidVMR9.Data4
0x1800c5823  jz      short loc_1800C5860
0x1800c5825  mov     rdx, r14; struct MSVideoControl::VWGraphSegment *
0x1800c5828  lea     rcx, [rbp+57h+var_D0]; this
0x1800c582c  call    ??0VWGraphSegment@MSVideoControl@@QEAA@AEBV01@@Z; MSVideoControl::VWGraphSegment::VWGraphSegment(MSVideoControl::VWGraphSegment const &)
0x1800c5831  nop
0x1800c5832  mov     ebx, 0Fh
0x1800c5837  mov     [rsp+120h+pdwValue], ebx
0x1800c583b  lea     rdx, [rbp+57h+var_90]
0x1800c583f  mov     rcx, rax
0x1800c5842  call    ?ClassID@VWGraphSegment@MSVideoControl@@QEAA?AVGUID2@@XZ; MSVideoControl::VWGraphSegment::ClassID(void)
0x1800c5847  mov     rcx, [rax]
0x1800c584a  cmp     rcx, qword ptr cs:CLSID_MSVidEVR.Data1
0x1800c5851  jnz     short loc_1800C5865
0x1800c5853  mov     rax, [rax+8]
0x1800c5857  cmp     rax, qword ptr cs:CLSID_MSVidEVR.Data4
0x1800c585e  jnz     short loc_1800C5865
0x1800c5860  mov     dil, 1
0x1800c5863  jmp     short loc_1800C5868
0x1800c5865  xor     dil, dil
0x1800c5868  lea     rax, ??_7?$Forward_Sequence@V?$CComQIPtr@UIMSVidGraphSegment@@$1?_GUID_238dec54_adeb_4005_a349_f772b9afebc4@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIEnumFilters@@$1?IID_IEnumFilters@@3U_GUID@@B@2@VDSFilter@@UIMSVidGraphSegment@@UIEnumFilters@@PEAUIBaseFilter@@V?$allocator@VDSFilter@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable'
0x1800c586f  test    bl, 8
0x1800c5872  jz      short loc_1800C588B
0x1800c5874  and     ebx, 0FFFFFFF7h
0x1800c5877  mov     [rbp+57h+var_D0], rax
0x1800c587b  lea     rcx, [rbp+57h+var_C8]
0x1800c587f  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c5884  lea     rax, ??_7?$Forward_Sequence@V?$CComQIPtr@UIMSVidGraphSegment@@$1?_GUID_238dec54_adeb_4005_a349_f772b9afebc4@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIEnumFilters@@$1?IID_IEnumFilters@@3U_GUID@@B@2@VDSFilter@@UIMSVidGraphSegment@@UIEnumFilters@@PEAUIBaseFilter@@V?$allocator@VDSFilter@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable'
0x1800c588b  test    bl, 4
0x1800c588e  jz      short loc_1800C58A1
0x1800c5890  and     ebx, 0FFFFFFFBh
0x1800c5893  mov     [rbp+57h+var_C0], rax
0x1800c5897  lea     rcx, [rbp+57h+var_B8]
0x1800c589b  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c58a0  nop
0x1800c58a1  test    bl, 2
0x1800c58a4  jz      short loc_1800C58BE
0x1800c58a6  and     ebx, 0FFFFFFFDh
0x1800c58a9  lea     rax, ??_7?$Forward_Sequence@V?$CComQIPtr@UIMSVidGraphSegment@@$1?_GUID_238dec54_adeb_4005_a349_f772b9afebc4@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIEnumFilters@@$1?IID_IEnumFilters@@3U_GUID@@B@2@VDSFilter@@UIMSVidGraphSegment@@UIEnumFilters@@PEAUIBaseFilter@@V?$allocator@VDSFilter@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable'
0x1800c58b0  mov     [rbp+57h+var_B0], rax
0x1800c58b4  lea     rcx, [rbp+57h+var_A8]
0x1800c58b8  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c58bd  nop
0x1800c58be  test    bl, 1
0x1800c58c1  jz      short loc_1800C58DC
0x1800c58c3  and     ebx, 0FFFFFFFEh
0x1800c58c6  lea     rax, ??_7?$Forward_Sequence@V?$CComQIPtr@UIMSVidGraphSegment@@$1?_GUID_238dec54_adeb_4005_a349_f772b9afebc4@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIEnumFilters@@$1?IID_IEnumFilters@@3U_GUID@@B@2@VDSFilter@@UIMSVidGraphSegment@@UIEnumFilters@@PEAUIBaseFilter@@V?$allocator@VDSFilter@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable'
0x1800c58cd  mov     [rsp+120h+var_E0], rax
0x1800c58d2  lea     rcx, [rsp+120h+var_D8]
0x1800c58d7  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c58dc  test    dil, dil
0x1800c58df  jz      short loc_1800C58ED
0x1800c58e1  lea     rcx, CLSID_MSVidAnalogCaptureToOverlayMixer
0x1800c58e8  jmp     loc_1800C59AF
0x1800c58ed  mov     rdx, r15; struct MSVideoControl::VWGraphSegment *
0x1800c58f0  lea     rcx, [rbp+57h+var_D0]; this
0x1800c58f4  call    ??0VWGraphSegment@MSVideoControl@@QEAA@AEBV01@@Z; MSVideoControl::VWGraphSegment::VWGraphSegment(MSVideoControl::VWGraphSegment const &)
0x1800c58f9  nop
0x1800c58fa  or      ebx, 10h
0x1800c58fd  mov     [rsp+120h+pdwValue], ebx
0x1800c5901  lea     rdx, [rbp+57h+var_90]
0x1800c5905  mov     rcx, rax
0x1800c5908  call    ?Category@VWGraphSegment@MSVideoControl@@QEAA?AVGUID2@@XZ; MSVideoControl::VWGraphSegment::Category(void)
0x1800c590d  mov     rcx, [rax]
0x1800c5910  cmp     rcx, qword ptr cs:_GUID_a799a800_a46d_11d0_a18c_00a02401dcd4.Data1
0x1800c5917  jnz     short loc_1800C5965
0x1800c5919  mov     rax, [rax+8]
0x1800c591d  cmp     rax, qword ptr cs:_GUID_a799a800_a46d_11d0_a18c_00a02401dcd4.Data4
0x1800c5924  jnz     short loc_1800C5965
0x1800c5926  mov     rdx, r14; struct MSVideoControl::VWGraphSegment *
0x1800c5929  lea     rcx, [rsp+120h+var_E0]; this
0x1800c592e  call    ??0VWGraphSegment@MSVideoControl@@QEAA@AEBV01@@Z; MSVideoControl::VWGraphSegment::VWGraphSegment(MSVideoControl::VWGraphSegment const &)
0x1800c5933  nop
0x1800c5934  or      ebx, 20h
0x1800c5937  mov     [rsp+120h+pdwValue], ebx
0x1800c593b  lea     rdx, [rbp+57h+var_80]
0x1800c593f  mov     rcx, rax
0x1800c5942  call    ?ClassID@VWGraphSegment@MSVideoControl@@QEAA?AVGUID2@@XZ; MSVideoControl::VWGraphSegment::ClassID(void)
0x1800c5947  mov     rcx, [rax]
0x1800c594a  cmp     rcx, qword ptr cs:CLSID_MSVidStreamBufferSink.Data1
0x1800c5951  jnz     short loc_1800C5965
0x1800c5953  mov     rax, [rax+8]
0x1800c5957  cmp     rax, qword ptr cs:CLSID_MSVidStreamBufferSink.Data4
0x1800c595e  jnz     short loc_1800C5965
0x1800c5960  mov     dil, 1
0x1800c5963  jmp     short loc_1800C5968
0x1800c5965  xor     dil, dil
0x1800c5968  test    bl, 20h
0x1800c596b  jz      short loc_1800C5987
0x1800c596d  and     ebx, 0FFFFFFDFh
0x1800c5970  lea     rax, ??_7?$Forward_Sequence@V?$CComQIPtr@UIMSVidGraphSegment@@$1?_GUID_238dec54_adeb_4005_a349_f772b9afebc4@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIEnumFilters@@$1?IID_IEnumFilters@@3U_GUID@@B@2@VDSFilter@@UIMSVidGraphSegment@@UIEnumFilters@@PEAUIBaseFilter@@V?$allocator@VDSFilter@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable'
0x1800c5977  mov     [rsp+120h+var_E0], rax
0x1800c597c  lea     rcx, [rsp+120h+var_D8]
0x1800c5981  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c5986  nop
0x1800c5987  test    bl, 10h
0x1800c598a  jz      short loc_1800C59A3
0x1800c598c  and     ebx, 0FFFFFFEFh
0x1800c598f  lea     rax, ??_7?$Forward_Sequence@V?$CComQIPtr@UIMSVidGraphSegment@@$1?_GUID_238dec54_adeb_4005_a349_f772b9afebc4@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIEnumFilters@@$1?IID_IEnumFilters@@3U_GUID@@B@2@VDSFilter@@UIMSVidGraphSegment@@UIEnumFilters@@PEAUIBaseFilter@@V?$allocator@VDSFilter@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable'
0x1800c5996  mov     [rbp+57h+var_D0], rax
0x1800c599a  lea     rcx, [rbp+57h+var_C8]
0x1800c599e  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c59a3  test    dil, dil
0x1800c59a6  jz      short loc_1800C5A23
0x1800c59a8  lea     rcx, CLSID_MSVidAnalogCaptureToStreamBufferSink; rclsid
0x1800c59af  lea     rax, [rsp+120h+var_E8]
0x1800c59b4  mov     r8d, 17h; dwClsContext
0x1800c59ba  lea     r9, _GUID_1c15d483_911d_11d2_b632_00c04f79498e; riid
0x1800c59c1  mov     [rsp+120h+ppv], rax; ppv
0x1800c59c6  xor     edx, edx; pUnkOuter
0x1800c59c8  call    cs:__imp_CoCreateInstance
0x1800c59ce  test    eax, eax
0x1800c59d0  js      short loc_1800C59E0
0x1800c59d2  mov     rcx, [rsp+120h+var_E8]
0x1800c59d7  test    rcx, rcx
0x1800c59da  jnz     loc_1800C72CF
0x1800c59e0  mov     r8d, 0C0040529h
0x1800c59e6  mov     r9, cs:hInstance
0x1800c59ed  mov     ecx, 0C0040529h; dwMessageId
0x1800c59f2  call    ?Error@?$CComCoClass@VCVidCtl@@$1?CLSID_MSVidCtl@@3U_GUID@@B@ATL@@SAJIAEBU_GUID@@JPEAUHINSTANCE__@@@Z; ATL::CComCoClass<CVidCtl,&_GUID const CLSID_MSVidCtl>::Error(uint,_GUID const &,long,HINSTANCE__ *)
0x1800c59f7  mov     ebx, eax
0x1800c59f9  lea     rcx, [rsp+120h+var_E8]
0x1800c59fe  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c5a03  mov     eax, ebx
0x1800c5a05  mov     rcx, [rbp+57h+var_40]
0x1800c5a09  xor     rcx, rsp; StackCookie
0x1800c5a0c  call    __security_check_cookie
0x1800c5a11  add     rsp, 0F0h
0x1800c5a18  pop     r15
0x1800c5a1a  pop     r14
0x1800c5a1c  pop     r12
0x1800c5a1e  pop     rdi
0x1800c5a1f  pop     rsi
0x1800c5a20  pop     rbx
0x1800c5a21  pop     rbp
0x1800c5a22  retn
0x1800c5a23  mov     rdx, r15; struct MSVideoControl::VWGraphSegment *
0x1800c5a26  lea     rcx, [rbp+57h+var_D0]; this
0x1800c5a2a  call    ??0VWGraphSegment@MSVideoControl@@QEAA@AEBV01@@Z; MSVideoControl::VWGraphSegment::VWGraphSegment(MSVideoControl::VWGraphSegment const &)
0x1800c5a2f  nop
0x1800c5a30  or      ebx, 40h
0x1800c5a33  mov     [rsp+120h+pdwValue], ebx
0x1800c5a37  lea     rdx, [rbp+57h+var_90]
0x1800c5a3b  mov     rcx, rax
0x1800c5a3e  call    ?ClassID@VWGraphSegment@MSVideoControl@@QEAA?AVGUID2@@XZ; MSVideoControl::VWGraphSegment::ClassID(void)
0x1800c5a43  mov     rcx, [rax]
0x1800c5a46  cmp     rcx, qword ptr cs:CLSID_MSVidBDATunerDevice.Data1
0x1800c5a4d  jnz     short loc_1800C5A9C
0x1800c5a4f  mov     rax, [rax+8]
0x1800c5a53  cmp     rax, qword ptr cs:CLSID_MSVidBDATunerDevice.Data4
0x1800c5a5a  jnz     short loc_1800C5A9C
0x1800c5a5c  mov     rdx, r14; struct MSVideoControl::VWGraphSegment *
0x1800c5a5f  lea     rcx, [rsp+120h+var_E0]; this
0x1800c5a64  call    ??0VWGraphSegment@MSVideoControl@@QEAA@AEBV01@@Z; MSVideoControl::VWGraphSegment::VWGraphSegment(MSVideoControl::VWGraphSegment const &)
0x1800c5a69  nop
0x1800c5a6a  bts     ebx, 7
0x1800c5a6e  mov     [rsp+120h+pdwValue], ebx
0x1800c5a72  lea     rdx, [rbp+57h+var_80]
0x1800c5a76  mov     rcx, rax
0x1800c5a79  call    ?ClassID@VWGraphSegment@MSVideoControl@@QEAA?AVGUID2@@XZ; MSVideoControl::VWGraphSegment::ClassID(void)
0x1800c5a7e  mov     rcx, [rax]
0x1800c5a81  cmp     rcx, qword ptr cs:CLSID_MSVidStreamBufferSink.Data1
0x1800c5a88  jnz     short loc_1800C5A9C
0x1800c5a8a  mov     rax, [rax+8]
0x1800c5a8e  cmp     rax, qword ptr cs:CLSID_MSVidStreamBufferSink.Data4
0x1800c5a95  jnz     short loc_1800C5A9C
0x1800c5a97  mov     dil, 1
0x1800c5a9a  jmp     short loc_1800C5A9F
0x1800c5a9c  xor     dil, dil
0x1800c5a9f  test    bl, bl
0x1800c5aa1  jns     short loc_1800C5ABE
0x1800c5aa3  btr     ebx, 7
0x1800c5aa7  lea     rax, ??_7?$Forward_Sequence@V?$CComQIPtr@UIMSVidGraphSegment@@$1?_GUID_238dec54_adeb_4005_a349_f772b9afebc4@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIEnumFilters@@$1?IID_IEnumFilters@@3U_GUID@@B@2@VDSFilter@@UIMSVidGraphSegment@@UIEnumFilters@@PEAUIBaseFilter@@V?$allocator@VDSFilter@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable'
0x1800c5aae  mov     [rsp+120h+var_E0], rax
0x1800c5ab3  lea     rcx, [rsp+120h+var_D8]
0x1800c5ab8  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c5abd  nop
0x1800c5abe  test    bl, 40h
0x1800c5ac1  jz      short loc_1800C5ADA
0x1800c5ac3  and     ebx, 0FFFFFFBFh
0x1800c5ac6  lea     rax, ??_7?$Forward_Sequence@V?$CComQIPtr@UIMSVidGraphSegment@@$1?_GUID_238dec54_adeb_4005_a349_f772b9afebc4@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIEnumFilters@@$1?IID_IEnumFilters@@3U_GUID@@B@2@VDSFilter@@UIMSVidGraphSegment@@UIEnumFilters@@PEAUIBaseFilter@@V?$allocator@VDSFilter@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable'
0x1800c5acd  mov     [rbp+57h+var_D0], rax
0x1800c5ad1  lea     rcx, [rbp+57h+var_C8]
0x1800c5ad5  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c5ada  test    dil, dil
0x1800c5add  jz      short loc_1800C5AEB
0x1800c5adf  lea     rcx, CLSID_MSVidDigitalCaptureToStreamBufferSink
0x1800c5ae6  jmp     loc_1800C59AF
0x1800c5aeb  mov     rdx, r15; struct MSVideoControl::VWGraphSegment *
0x1800c5aee  lea     rcx, [rbp+57h+var_C0]; this
0x1800c5af2  call    ??0VWGraphSegment@MSVideoControl@@QEAA@AEBV01@@Z; MSVideoControl::VWGraphSegment::VWGraphSegment(MSVideoControl::VWGraphSegment const &)
0x1800c5af7  nop
0x1800c5af8  bts     ebx, 8
0x1800c5afc  mov     [rsp+120h+pdwValue], ebx
0x1800c5b00  lea     rdx, [rbp+57h+var_90]
0x1800c5b04  mov     rcx, rax
0x1800c5b07  call    ?ClassID@VWGraphSegment@MSVideoControl@@QEAA?AVGUID2@@XZ; MSVideoControl::VWGraphSegment::ClassID(void)
0x1800c5b0c  mov     rcx, [rax]
0x1800c5b0f  cmp     rcx, qword ptr cs:CLSID_MSVidBDATunerDevice.Data1
0x1800c5b16  jnz     short loc_1800C5B25
0x1800c5b18  mov     rax, [rax+8]
0x1800c5b1c  cmp     rax, qword ptr cs:CLSID_MSVidBDATunerDevice.Data4
0x1800c5b23  jz      short loc_1800C5B5F
0x1800c5b25  mov     rdx, r15; struct MSVideoControl::VWGraphSegment *
0x1800c5b28  lea     rcx, [rbp+57h+var_D0]; this
0x1800c5b2c  call    ??0VWGraphSegment@MSVideoControl@@QEAA@AEBV01@@Z; MSVideoControl::VWGraphSegment::VWGraphSegment(MSVideoControl::VWGraphSegment const &)
0x1800c5b31  nop
0x1800c5b32  bts     ebx, 9
0x1800c5b36  mov     [rsp+120h+pdwValue], ebx
0x1800c5b3a  lea     rdx, [rbp+57h+var_80]
0x1800c5b3e  mov     rcx, rax
0x1800c5b41  call    ?ClassID@VWGraphSegment@MSVideoControl@@QEAA?AVGUID2@@XZ; MSVideoControl::VWGraphSegment::ClassID(void)
0x1800c5b46  mov     rcx, [rax]
0x1800c5b49  cmp     rcx, qword ptr cs:CLSID_MSVidWebDVD.Data1
0x1800c5b50  jnz     short loc_1800C5B9F
0x1800c5b52  mov     rax, [rax+8]
0x1800c5b56  cmp     rax, qword ptr cs:CLSID_MSVidWebDVD.Data4
0x1800c5b5d  jnz     short loc_1800C5B9F
0x1800c5b5f  mov     rdx, r14; struct MSVideoControl::VWGraphSegment *
0x1800c5b62  lea     rcx, [rsp+120h+var_E0]; this
0x1800c5b67  call    ??0VWGraphSegment@MSVideoControl@@QEAA@AEBV01@@Z; MSVideoControl::VWGraphSegment::VWGraphSegment(MSVideoControl::VWGraphSegment const &)
0x1800c5b6c  nop
0x1800c5b6d  bts     ebx, 0Ah
0x1800c5b71  mov     [rsp+120h+pdwValue], ebx
0x1800c5b75  lea     rdx, [rbp+57h+var_50]
0x1800c5b79  mov     rcx, rax
0x1800c5b7c  call    ?ClassID@VWGraphSegment@MSVideoControl@@QEAA?AVGUID2@@XZ; MSVideoControl::VWGraphSegment::ClassID(void)
0x1800c5b81  mov     rcx, [rax]
0x1800c5b84  cmp     rcx, qword ptr cs:CLSID_MSVidClosedCaptioning.Data1
0x1800c5b8b  jnz     short loc_1800C5B9F
0x1800c5b8d  mov     rax, [rax+8]
0x1800c5b91  cmp     rax, qword ptr cs:CLSID_MSVidClosedCaptioning.Data4
0x1800c5b98  jnz     short loc_1800C5B9F
0x1800c5b9a  mov     dil, 1
0x1800c5b9d  jmp     short loc_1800C5BA2
0x1800c5b9f  xor     dil, dil
0x1800c5ba2  bt      ebx, 0Ah
0x1800c5ba6  jnb     short loc_1800C5BC3
  ... truncated ...
```
