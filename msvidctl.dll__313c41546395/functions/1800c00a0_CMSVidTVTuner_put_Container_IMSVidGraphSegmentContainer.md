# CMSVidTVTuner::put_Container(IMSVidGraphSegmentContainer *)

- ea: `0x1800c00a0`
- end: `0x1800c0f85`
- name: `?put_Container@CMSVidTVTuner@@UEAAJPEAUIMSVidGraphSegmentContainer@@@Z`
- size: `3813`
- prototype: `int(CMSVidTVTuner *__hidden this, struct IMSVidGraphSegmentContainer *)`
- caller_count: `0`
- callee_count: `43`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004640`
- `0x180006b38`
- `0x18000e1b8`
- `0x18000e518`
- `0x18000ff74`
- `0x18001414c`
- `0x18001a0f8`
- `0x18001a148`
- `0x180030cb4`
- `0x180057368`
- `0x180057978`
- `0x180057f18`
- `0x180058200`
- `0x1800598ec`
- `0x180059dbc`
- `0x18005a120`
- `0x18005a308`
- `0x18005bfa8`
- `0x18006f878`
- `0x1800703f4`
- `0x180076b78`
- `0x180076d64`
- `0x180077244`
- `0x18007a20c`
- `0x18008061c`
- `0x180080900`
- `0x1800a0374`
- `0x1800a0514`
- `0x1800b4ba0`
- `0x1800b4cbc`
- `0x1800b4f84`
- `0x1800b9de0`
- `0x1800ba1c4`
- `0x1800bc24c`
- `0x1800be5e0`
- `0x1800c00a0`
- `0x1800d76bc`
- `0x1800d76dc`
- `0x1800d7ebc`
- `0x1800db498`
- `0x1800db6a8`
- `0x1800dc134`
- `0x1800f8010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1800c0ed5`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1800c0ed5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800c0e53`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800c0eee`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800c0e53`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800c0eee`
- `ole32!CoCreateInstance` at `0x1800c0a21`
- `ole32!CoCreateInstance` at `0x1800c0a21`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c07e9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c07f8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0968`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0977`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0a5d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0a6c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0b55`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0b64`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0c57`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0c66`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0d68`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0d77`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0e8f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0f2a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c07e9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c07f8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0968`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0977`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0a5d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0a6c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0b55`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0b64`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0c57`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0c66`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0d68`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0d77`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0e8f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0f2a`
- `OLEAUT32!__imp_SysStringLen` at `0x1800c0e33`
- `OLEAUT32!__imp_SysStringLen` at `0x1800c0ebc`
- `OLEAUT32!__imp_SysStringLen` at `0x1800c0e33`
- `OLEAUT32!__imp_SysStringLen` at `0x1800c0ebc`

## pseudocode

```c
// Hidden C++ exception states: #wind=21 #try_helpers=1
__int64 __fastcall CMSVidTVTuner::put_Container(CMSVidTVTuner *this, struct IMSVidGraphSegmentContainer *a2)
{
  CMSVidTVTuner *v3; // r15
  __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // rax
  char IsEqualObject; // bl
  __int64 Graph; // rax
  unsigned __int64 v10; // rdx
  void *(*v11)(void *); // r9
  __int64 v12; // rcx
  unsigned int v13; // ebx
  struct IUnknown *v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rax
  bool v18; // bl
  __int64 v19; // rax
  __int64 i; // rbx
  __int64 j; // rbx
  __int64 k; // rbx
  __int64 m; // rbx
  __int64 v24; // rcx
  struct IUnknown *v25; // rdx
  __int64 v26; // rcx
  unsigned int v27; // ebx
  __int64 v28; // r10
  _QWORD *v29; // rax
  int v30; // r11d
  __int64 v31; // r8
  int v32; // r9d
  __int64 v33; // rcx
  HRESULT Instance; // ebx
  _QWORD *v35; // r14
  char *v36; // rdx
  int v37; // ebx
  OLECHAR *v38; // rcx
  OLECHAR *v39; // rcx
  size_t v40; // rax
  int v41; // [rsp+48h] [rbp-1B0h]
  int v42; // [rsp+50h] [rbp-1A8h]
  BSTR pbstr; // [rsp+80h] [rbp-178h] BYREF
  LPVOID v44; // [rsp+88h] [rbp-170h] BYREF
  int v45; // [rsp+90h] [rbp-168h] BYREF
  void **v46; // [rsp+98h] [rbp-160h] BYREF
  struct IUnknown *v47; // [rsp+A0h] [rbp-158h] BYREF
  _BYTE v48[8]; // [rsp+A8h] [rbp-150h] BYREF
  void **v49; // [rsp+B0h] [rbp-148h] BYREF
  __int64 v50; // [rsp+B8h] [rbp-140h] BYREF
  BSTR String; // [rsp+C0h] [rbp-138h] BYREF
  void **v52; // [rsp+C8h] [rbp-130h] BYREF
  _BYTE v53[8]; // [rsp+D0h] [rbp-128h] BYREF
  BSTR bstrString; // [rsp+D8h] [rbp-120h] BYREF
  _BYTE v55[8]; // [rsp+E0h] [rbp-118h] BYREF
  __int64 v56; // [rsp+E8h] [rbp-110h]
  _BYTE v57[24]; // [rsp+F0h] [rbp-108h] BYREF
  _BYTE v58[24]; // [rsp+108h] [rbp-F0h] BYREF
  _BYTE v59[8]; // [rsp+120h] [rbp-D8h] BYREF
  __int64 v60; // [rsp+128h] [rbp-D0h]
  _BYTE v61[24]; // [rsp+138h] [rbp-C0h] BYREF
  _BYTE v62[24]; // [rsp+150h] [rbp-A8h] BYREF
  _BYTE v63[24]; // [rsp+168h] [rbp-90h] BYREF
  struct _GUID v64; // [rsp+190h] [rbp-68h] BYREF
  GUID v65; // [rsp+1A0h] [rbp-58h]

  v3 = (CMSVidTVTuner *)((char *)this - 144);
  if ( !*((_BYTE *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 16) )
    return ATL::CComCoClass<CMSVidTVTuner,&__s_GUID const _GUID_1c15d484_911d_11d2_b632_00c04f79498e>::Error(
             0xC0040502,
             &GUID_1c15d47e_911d_11d2_b632_00c04f79498e,
             -1073478398,
             hInstance);
  if ( a2 )
  {
    v6 = *(int *)(*((_QWORD *)this + 1) + 4LL);
    if ( *(_QWORD *)((char *)this + v6 + 32) )
    {
      v7 = MSVideoControl::VWSegmentContainer::VWSegmentContainer((MSVideoControl::VWSegmentContainer *)&v52, a2);
      IsEqualObject = ATL::CComQIPtr<IMSVidGraphSegmentContainer,&__s_GUID const _GUID_3dd2903d_e0aa_11d2_b63a_00c04f79498e>::IsEqualObject(
                        (char *)this + v6 + 32,
                        *(_QWORD *)(v7 + 8));
      v52 = &MSVideoControl::VWSegmentContainer::`vftable';
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v53);
      if ( IsEqualObject )
      {
        if ( *((_QWORD *)this + 5) )
          (*(void (__fastcall **)(char *))(*((_QWORD *)this + 2) + 336LL))((char *)this + 16);
        return 0;
      }
      else
      {
        return ATL::CComCoClass<CMSVidTVTuner,&__s_GUID const _GUID_1c15d484_911d_11d2_b632_00c04f79498e>::Error(
                 0xC0040526,
                 &GUID_1c15d47e_911d_11d2_b632_00c04f79498e,
                 -1073478362,
                 hInstance);
      }
    }
    else
    {
      *(_QWORD *)((char *)this + v6 + 32) = a2;
      Graph = MSVideoControl::VWSegmentContainer::GetGraph(
                (char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 24,
                &v52);
      ATL::AtlComPtrAssign(
        (struct IUnknown **)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 48),
        *(struct IUnknown **)(Graph + 8));
      v52 = &Forward_Sequence<ATL::CComQIPtr<IGraphBuilder,&_GUID const IID_IGraphBuilder>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IGraphBuilder,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable';
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v53);
      ATL::CComQIPtr<IFilterMapper2,&_GUID const IID_IFilterMapper2>::CComQIPtr<IFilterMapper2,&_GUID const IID_IFilterMapper2>(
        &v45,
        *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 48));
      `vector constructor iterator'((GUID2 *)&v64, v10, 2u, v11);
      v64 = GUID_00000000_0000_0000_0000_000000000000;
      v65 = GUID_00000000_0000_0000_0000_000000000000;
      DSFilterMapper::DSFilterMapper((DSFilterMapper *)v59, 0x200000u, 1, 1u, &v64, 0, v41, v42, 1, 0, 0, 0);
      if ( v60 )
      {
        Forward_Sequence<ATL::CComQIPtr<ICreateDevEnum,&_GUID const IID_ICreateDevEnum>,ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,ICreateDevEnum,IEnumMoniker,IMoniker *,std::allocator<DSFilterMoniker>>::begin(
          v59,
          &v52);
        enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(&v52);
      }
      v12 = *(int *)(*((_QWORD *)this + 1) + 4LL);
      DSGraph::AddMoniker((char *)this + v12 + 40, &v49, (char *)this + v12 + 80);
      if ( v50 )
      {
        std::vector<DSFilter>::push_back((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 56, &v49);
        *((_DWORD *)this + 24) = 0;
        if ( *((_QWORD *)this + 11)
          || (v14 = *(struct IUnknown **)ATL::CComQIPtr<ICreateDevEnum,&_GUID const IID_ICreateDevEnum>::CComQIPtr<ICreateDevEnum,&_GUID const IID_ICreateDevEnum>(&v44),
              ATL::AtlComPtrAssign((struct IUnknown **)this + 11, v14),
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v44),
              *((_QWORD *)this + 11)) )
        {
          DSDevices::DSDevices(v63, (char *)this + 88, &GUID_65e8773d_8f56_11d0_a3b9_00a0c9223196);
          std::vector<DSPin>::vector<DSPin>(v57);
          std::vector<DSPin>::vector<DSPin>(v62);
          std::vector<DSPin>::vector<DSPin>(v58);
          pbstr = 0;
          v44 = 0;
          enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(
            v55,
            &v44,
            &pbstr);
          v15 = Forward_Sequence<ATL::CComQIPtr<ICreateDevEnum,&_GUID const IID_ICreateDevEnum>,ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,ICreateDevEnum,IEnumMoniker,IMoniker *,std::allocator<DSFilterMoniker>>::begin(
                  v63,
                  &v52);
          enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::operator=(
            v55,
            v15);
          enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(&v52);
          while ( 1 )
          {
            v17 = Forward_Sequence<ATL::CComQIPtr<ICreateDevEnum,&_GUID const IID_ICreateDevEnum>,ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,ICreateDevEnum,IEnumMoniker,IMoniker *,std::allocator<DSFilterMoniker>>::end(
                    v16,
                    &v52);
            v18 = v56 != *(_QWORD *)(v17 + 8);
            enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(&v52);
            if ( !v18 )
              break;
            v19 = enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::operator*(
                    v55,
                    v48);
            std::vector<ATL::CComQIPtr<IMSVidDevice,&__s_GUID const _GUID_1c15d47c_911d_11d2_b632_00c04f79498e>>::push_back(
              v57,
              v19);
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v48);
            enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::operator++(v55);
          }
          DSFilterMoniker::GetDevPath((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 80, &String);
          for ( i = *(_QWORD *)std::_Tree<std::_Tmap_traits<ATL::CComBSTR,unsigned long,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,unsigned long>>,0>>::end(
                                 v57,
                                 v48); i != *(_QWORD *)std::vector<ATL::CComBSTR>::end(v57, &v44); i += 8 )
          {
            DSFilterMoniker::GetDevPath(i, &pbstr);
            v39 = pbstr;
            if ( pbstr )
            {
              if ( SysStringLen(pbstr) )
              {
                v40 = wcscspn(String, L"{");
                if ( (unsigned int)_o__wcsnicmp(String, pbstr, v40) )
                  std::vector<ATL::CComQIPtr<IMSVidDevice,&__s_GUID const _GUID_1c15d47c_911d_11d2_b632_00c04f79498e>>::push_back(
                    v62,
                    i);
                else
                  std::vector<ATL::CComQIPtr<IMSVidDevice,&__s_GUID const _GUID_1c15d47c_911d_11d2_b632_00c04f79498e>>::push_back(
                    v58,
                    i);
                v39 = pbstr;
              }
              else
              {
                v39 = pbstr;
              }
            }
            SysFreeString(v39);
          }
          std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>::clear(v57);
          DSFilterMoniker::GetName((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 80, &bstrString);
          for ( j = *(_QWORD *)std::_Tree<std::_Tmap_traits<ATL::CComBSTR,unsigned long,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,unsigned long>>,0>>::end(
                                 v62,
                                 v48); j != *(_QWORD *)std::vector<ATL::CComBSTR>::end(v62, &v44); j += 8 )
          {
            DSFilterMoniker::GetName(j, &pbstr);
            v38 = pbstr;
            if ( pbstr )
            {
              if ( SysStringLen(pbstr) )
              {
                if ( (unsigned int)_o__wcsnicmp(bstrString, pbstr, 4) )
                  std::vector<ATL::CComQIPtr<IMSVidDevice,&__s_GUID const _GUID_1c15d47c_911d_11d2_b632_00c04f79498e>>::push_back(
                    v57,
                    j);
                else
                  std::vector<ATL::CComQIPtr<IMSVidDevice,&__s_GUID const _GUID_1c15d47c_911d_11d2_b632_00c04f79498e>>::push_back(
                    v58,
                    j);
                v38 = pbstr;
              }
              else
              {
                v38 = pbstr;
              }
            }
            SysFreeString(v38);
          }
          for ( k = *(_QWORD *)std::_Tree<std::_Tmap_traits<ATL::CComBSTR,unsigned long,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,unsigned long>>,0>>::end(
                                 v57,
                                 v48); k != *(_QWORD *)std::vector<ATL::CComBSTR>::end(v57, &v44); k += 8 )
            std::vector<ATL::CComQIPtr<IMSVidDevice,&__s_GUID const _GUID_1c15d47c_911d_11d2_b632_00c04f79498e>>::push_back(
              v58,
              k);
          v47 = 0;
          v46 = &DSFilter::`vftable';
          std::vector<DSPin>::vector<DSPin>(v61);
          for ( m = *(_QWORD *)std::_Tree<std::_Tmap_traits<ATL::CComBSTR,unsigned long,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,unsigned long>>,0>>::end(
                                 v58,
                                 v48); m != *(_QWORD *)std::vector<ATL::CComBSTR>::end(v58, &v44); m += 8 )
          {
            pbstr = (BSTR)WTL::_atltmpPchNil;
            v25 = *(struct IUnknown **)(DSGraph::LoadFilter(v24, (__int64)&v52, m, (WTL::CString *)&pbstr) + 8);
            ATL::AtlComPtrAssign(&v47, v25);
            v52 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v53);
            if ( v47
              && IsVideoFilter((const struct DSFilter *)&v46)
              && (int)DSGraph::AddFilter(
                        (CMSVidTVTuner *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 40),
                        (struct DSFilter *)&v46,
                        (struct WTL::CString *)&pbstr) >= 0 )
            {
              v26 = *(int *)(*((_QWORD *)this + 1) + 4LL);
              if ( (int)DSGraph::Connect(
                          (int)this + (int)v26 + 40,
                          *(_DWORD *)((char *)this + v26 + 56) + 16 * *((_DWORD *)this + 24),
                          (unsigned int)&v46,
                          (unsigned int)v61,
                          576,
                          1) >= 0 )
              {
                WTL::CString::~CString((WTL::CString *)&pbstr);
                break;
              }
              DSGraph::RemoveFilter(
                (CMSVidTVTuner *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 40),
                (struct DSFilter *)&v46);
            }
            WTL::CString::~CString((WTL::CString *)&pbstr);
          }
          if ( m == *(_QWORD *)std::vector<ATL::CComBSTR>::end(v58, v48) )
          {
            v27 = ATL::CComCoClass<CMSVidTVTuner,&__s_GUID const _GUID_1c15d484_911d_11d2_b632_00c04f79498e>::Error(
                    0xC004051F,
                    &GUID_1c15d47e_911d_11d2_b632_00c04f79498e,
                    -1073478369,
                    hInstance);
            std::vector<DSFilter>::_Tidy(v61);
            v46 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v47);
            SysFreeString(bstrString);
            SysFreeString(String);
            enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(v55);
            std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>::_Tidy(v58);
            std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>::_Tidy(v62);
            std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>::_Tidy(v57);
            DSDevices::~DSDevices((DSDevices *)v63);
            v49 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v50);
            DSFilterMapper::~DSFilterMapper((DSFilterMapper *)v59);
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v45);
            return v27;
          }
          else
          {
            std::vector<ATL::CComBSTR>::end(v61, v48);
            std::_Tree<std::_Tmap_traits<ATL::CComBSTR,unsigned long,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,unsigned long>>,0>>::end(
              v61,
              &v44);
            v29 = (_QWORD *)std::vector<ATL::CComBSTR>::end((char *)this + *(int *)(v28 + 4) + 56, &pbstr);
            std::vector<DSFilter>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<DSFilter>>>,0>(
              v30 + (_DWORD)this + 56,
              (unsigned int)&v52,
              *v29,
              v32,
              v31);
            *((_DWORD *)this + 24) = 0;
            std::vector<DSFilter>::push_back((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 56, &v46);
            v33 = *(int *)(*((_QWORD *)this + 1) + 4LL);
            *((_DWORD *)this + 25) = ((__int64)(*(_QWORD *)((char *)this + v33 + 64)
                                              - *(_QWORD *)((char *)this + v33 + 56)) >> 4)
                                   - 1;
            *((_DWORD *)this + 24) = 0;
            Instance = MSVideoControl::IBroadcastEventImpl<CMSVidTVTuner>::BroadcastAdvise((char *)this - 40);
            if ( Instance < 0 )
              goto LABEL_44;
            v35 = (_QWORD *)((char *)this + 112);
            if ( !*((_QWORD *)this + 14) )
            {
              Instance = CoCreateInstance(
                           &CLSID_TunerMarshaler,
                           0,
                           1u,
                           &GUID_359b3901_572c_4854_bb49_cdef66606a25,
                           (LPVOID *)this + 14);
              if ( Instance < 0 )
                goto LABEL_44;
            }
            v36 = (char *)this - 16;
            if ( !v3 )
              v36 = 0;
            Instance = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD))(*(_QWORD *)*v35 + 24LL))(
                         *v35,
                         v36,
                         *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 48));
            if ( Instance >= 0 )
            {
              v44 = 0;
              v37 = (*(__int64 (__fastcall **)(CMSVidTVTuner *, LPVOID *))(*(_QWORD *)v3 + 48LL))(v3, &v44);
              if ( v37 < 0 || (v37 = (*(__int64 (__fastcall **)(CMSVidTVTuner *))(*(_QWORD *)v3 + 56LL))(v3), v37 < 0) )
              {
                if ( *v35 )
                  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v35 + 32LL))(*v35);
                CMSVidTVTuner::Unload(v3);
                std::vector<DSFilter>::_Tidy(v61);
                v46 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v47);
                SysFreeString(bstrString);
                SysFreeString(String);
                enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(v55);
                std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>::_Tidy(v58);
                std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>::_Tidy(v62);
                std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>::_Tidy(v57);
                DSDevices::~DSDevices((DSDevices *)v63);
                v49 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v50);
                DSFilterMapper::~DSFilterMapper((DSFilterMapper *)v59);
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v45);
                return (unsigned int)v37;
              }
              else
              {
                std::vector<DSFilter>::_Tidy(v61);
                v46 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v47);
                SysFreeString(bstrString);
                SysFreeString(String);
                enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(v55);
                std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>::_Tidy(v58);
                std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>::_Tidy(v62);
                std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>::_Tidy(v57);
                DSDevices::~DSDevices((DSDevices *)v63);
                v49 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v50);
                DSFilterMapper::~DSFilterMapper((DSFilterMapper *)v59);
                ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v45);
                return 0;
              }
            }
            else
            {
LABEL_44:
              std::vector<DSFilter>::_Tidy(v61);
              v46 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v47);
              SysFreeString(bstrString);
              SysFreeString(String);
              enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(v55);
              std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>::_Tidy(v58);
              std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>::_Tidy(v62);
              std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>::_Tidy(v57);
              DSDevices::~DSDevices((DSDevices *)v63);
              v49 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v50);
              DSFilterMapper::~DSFilterMapper((DSFilterMapper *)v59);
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v45);
              return (unsigned int)Instance;
            }
          }
        }
        else
        {
          v49 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v50);
          DSFilterMapper::~DSFilterMapper((DSFilterMapper *)v59);
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v45);
          return 2147500034LL;
        }
      }
      else
      {
        v13 = ATL::CComCoClass<CMSVidTVTuner,&__s_GUID const _GUID_1c15d484_911d_11d2_b632_00c04f79498e>::Error(
                0xC0040597,
                &GUID_1c15d47e_911d_11d2_b632_00c04f79498e,
                -1073478249,
                hInstance);
        v49 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v50);
        DSFilterMapper::~DSFilterMapper((DSFilterMapper *)v59);
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v45);
        return v13;
      }
    }
  }
  else
  {
    v5 = *((_QWORD *)this + 14);
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 32LL))(v5);
    return CMSVidTVTuner::Unload(v3);
  }
}

```

## disassembly

```asm
0x1800c00a0  mov     [rsp+arg_10], rbx
0x1800c00a5  mov     [rsp+arg_18], rsi
0x1800c00aa  push    rdi
0x1800c00ab  push    r12
0x1800c00ad  push    r13
0x1800c00af  push    r14
0x1800c00b1  push    r15
0x1800c00b3  sub     rsp, 1D0h
0x1800c00ba  mov     rax, cs:__security_cookie
0x1800c00c1  xor     rax, rsp
0x1800c00c4  mov     [rsp+1F8h+var_38], rax
0x1800c00cc  mov     r8, rdx
0x1800c00cf  mov     rdi, rcx
0x1800c00d2  lea     r15, [rcx-90h]
0x1800c00d9  mov     rax, [rcx+8]
0x1800c00dd  movsxd  rdx, dword ptr [rax+4]
0x1800c00e1  xor     r12d, r12d
0x1800c00e4  cmp     [rdx+r15+0A0h], r12b
0x1800c00ec  jnz     short loc_1800C0111
0x1800c00ee  mov     r9, cs:hInstance; HINSTANCE
0x1800c00f5  mov     r8d, 0C0040502h; int
0x1800c00fb  lea     rdx, _GUID_1c15d47e_911d_11d2_b632_00c04f79498e; struct _GUID *
0x1800c0102  mov     ecx, 0C0040502h; dwMessageId
0x1800c0107  call    ?Error@?$CComCoClass@VCMSVidTVTuner@@$1?_GUID_1c15d484_911d_11d2_b632_00c04f79498e@@3U__s_GUID@@B@ATL@@SAJIAEBU_GUID@@JPEAUHINSTANCE__@@@Z; ATL::CComCoClass<CMSVidTVTuner,&__s_GUID const _GUID_1c15d484_911d_11d2_b632_00c04f79498e>::Error(uint,_GUID const &,long,HINSTANCE__ *)
0x1800c010c  jmp     loc_1800C0F57
0x1800c0111  test    r8, r8
0x1800c0114  jnz     short loc_1800C0138
0x1800c0116  mov     rcx, [rcx+70h]
0x1800c011a  test    rcx, rcx
0x1800c011d  jz      short loc_1800C012B
0x1800c011f  mov     rax, [rcx]
0x1800c0122  mov     rax, [rax+20h]
0x1800c0126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c012b  mov     rcx, r15; this
0x1800c012e  call    ?Unload@CMSVidTVTuner@@QEAAJXZ; CMSVidTVTuner::Unload(void)
0x1800c0133  jmp     loc_1800C0F57
0x1800c0138  mov     rax, [rcx+8]
0x1800c013c  movsxd  rbx, dword ptr [rax+4]
0x1800c0140  cmp     [rbx+rcx+20h], r12
0x1800c0145  jz      loc_1800C01D4
0x1800c014b  mov     rdx, r8; struct IMSVidGraphSegmentContainer *
0x1800c014e  lea     rcx, [rsp+1F8h+var_130]; this
0x1800c0156  call    ??0VWSegmentContainer@MSVideoControl@@QEAA@PEAUIMSVidGraphSegmentContainer@@@Z; MSVideoControl::VWSegmentContainer::VWSegmentContainer(IMSVidGraphSegmentContainer *)
0x1800c015b  nop
0x1800c015c  mov     rdx, [rax+8]
0x1800c0160  lea     rcx, [rdi+20h]
0x1800c0164  add     rcx, rbx
0x1800c0167  call    ?IsEqualObject@?$CComQIPtr@UIMSVidGraphSegmentContainer@@$1?_GUID_3dd2903d_e0aa_11d2_b63a_00c04f79498e@@3U__s_GUID@@B@ATL@@QEAA_NPEAUIUnknown@@@Z; ATL::CComQIPtr<IMSVidGraphSegmentContainer,&__s_GUID const _GUID_3dd2903d_e0aa_11d2_b63a_00c04f79498e>::IsEqualObject(IUnknown *)
0x1800c016c  mov     bl, al
0x1800c016e  lea     rax, ??_7VWSegmentContainer@MSVideoControl@@6B@; const MSVideoControl::VWSegmentContainer::`vftable'
0x1800c0175  mov     [rsp+1F8h+var_130], rax
0x1800c017d  lea     rcx, [rsp+1F8h+var_128]
0x1800c0185  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c018a  test    bl, bl
0x1800c018c  jnz     short loc_1800C01B1
0x1800c018e  mov     r9, cs:hInstance; HINSTANCE
0x1800c0195  mov     r8d, 0C0040526h; int
0x1800c019b  lea     rdx, _GUID_1c15d47e_911d_11d2_b632_00c04f79498e; struct _GUID *
0x1800c01a2  mov     ecx, 0C0040526h; dwMessageId
0x1800c01a7  call    ?Error@?$CComCoClass@VCMSVidTVTuner@@$1?_GUID_1c15d484_911d_11d2_b632_00c04f79498e@@3U__s_GUID@@B@ATL@@SAJIAEBU_GUID@@JPEAUHINSTANCE__@@@Z; ATL::CComCoClass<CMSVidTVTuner,&__s_GUID const _GUID_1c15d484_911d_11d2_b632_00c04f79498e>::Error(uint,_GUID const &,long,HINSTANCE__ *)
0x1800c01ac  jmp     loc_1800C0F57
0x1800c01b1  lea     rdx, [rdi+28h]
0x1800c01b5  cmp     [rdx], r12
0x1800c01b8  jz      short loc_1800C01CD
0x1800c01ba  lea     rcx, [rdi+10h]
0x1800c01be  mov     rax, [rcx]
0x1800c01c1  mov     rax, [rax+150h]
0x1800c01c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c01cd  xor     eax, eax
0x1800c01cf  jmp     loc_1800C0F57
0x1800c01d4  mov     [rbx+rcx+20h], r8
0x1800c01d9  mov     rax, [rcx+8]
0x1800c01dd  movsxd  rcx, dword ptr [rax+4]
0x1800c01e1  add     rcx, 18h
0x1800c01e5  add     rcx, rdi
0x1800c01e8  lea     rdx, [rsp+1F8h+var_130]
0x1800c01f0  call    ?GetGraph@VWSegmentContainer@MSVideoControl@@QEBA?AVDSGraph@@XZ; MSVideoControl::VWSegmentContainer::GetGraph(void)
0x1800c01f5  nop
0x1800c01f6  mov     rcx, [rdi+8]
0x1800c01fa  movsxd  rcx, dword ptr [rcx+4]
0x1800c01fe  add     rcx, 30h ; '0'
0x1800c0202  add     rcx, rdi; struct IUnknown **
0x1800c0205  mov     rdx, [rax+8]; struct IUnknown *
0x1800c0209  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800c020e  nop
0x1800c020f  lea     rax, ??_7?$Forward_Sequence@V?$CComQIPtr@UIGraphBuilder@@$1?IID_IGraphBuilder@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumFilters@@$1?IID_IEnumFilters@@3U_GUID@@B@2@VDSFilter@@UIGraphBuilder@@UIEnumFilters@@PEAUIBaseFilter@@V?$allocator@VDSFilter@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IGraphBuilder,&_GUID const IID_IGraphBuilder>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IGraphBuilder,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::`vftable'
0x1800c0216  mov     [rsp+1F8h+var_130], rax
0x1800c021e  lea     rcx, [rsp+1F8h+var_128]
0x1800c0226  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c022b  mov     rax, [rdi+8]
0x1800c022f  movsxd  rdx, dword ptr [rax+4]
0x1800c0233  mov     rdx, [rdx+rdi+30h]
0x1800c0238  lea     rcx, [rsp+1F8h+var_168]
0x1800c0240  call    ??0?$CComQIPtr@UIFilterMapper2@@$1?IID_IFilterMapper2@@3U_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IFilterMapper2,&_GUID const IID_IFilterMapper2>::CComQIPtr<IFilterMapper2,&_GUID const IID_IFilterMapper2>(IUnknown *)
0x1800c0245  nop
0x1800c0246  mov     r8d, 2; unsigned __int64
0x1800c024c  lea     rcx, [rsp+1F8h+var_68]; this
0x1800c0254  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1800c0259  mov     rcx, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800c0260  mov     qword ptr [rsp+1F8h+var_68.Data1], rcx
0x1800c0268  mov     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x1800c026f  mov     qword ptr [rsp+1F8h+var_68.Data4], rax
0x1800c0277  mov     [rsp+1F8h+var_58], rcx
0x1800c027f  mov     [rsp+1F8h+var_50], rax
0x1800c0287  mov     [rsp+1F8h+var_188], r12; struct REGPINMEDIUM *
0x1800c028c  mov     [rsp+1F8h+var_190], r12; struct _GUID *
0x1800c0291  mov     [rsp+1F8h+var_198], r12d; unsigned int
0x1800c0296  mov     r13d, 1
0x1800c029c  mov     [rsp+1F8h+var_1A0], r13d; int
0x1800c02a1  mov     [rsp+1F8h+var_1B8], r12; struct REGPINMEDIUM *
0x1800c02a6  lea     rax, [rsp+1F8h+var_68]
0x1800c02ae  mov     [rsp+1F8h+var_1C0], rax; struct _GUID *
0x1800c02b3  mov     [rsp+1F8h+var_1C8], r13d; unsigned int
0x1800c02b8  mov     [rsp+1F8h+var_1D0], r13d; int
0x1800c02bd  mov     dword ptr [rsp+1F8h+ppv], 200000h; unsigned int
0x1800c02c5  lea     r9d, [r13+1Fh]
0x1800c02c9  lea     rdx, [rsp+1F8h+var_168]
0x1800c02d1  lea     rcx, [rsp+1F8h+var_D8]; this
0x1800c02d9  call    ??0DSFilterMapper@@QEAA@AEAV?$CComQIPtr@UIFilterMapper2@@$1?IID_IFilterMapper2@@3U_GUID@@B@ATL@@KHKHKPEBU_GUID@@PEBUREGPINMEDIUM@@1HHK121@Z; DSFilterMapper::DSFilterMapper(ATL::CComQIPtr<IFilterMapper2,&_GUID const IID_IFilterMapper2> &,ulong,int,ulong,int,ulong,_GUID const *,REGPINMEDIUM const *,_GUID const *,int,int,ulong,_GUID const *,REGPINMEDIUM const *,_GUID const *)
0x1800c02de  nop
0x1800c02df  cmp     [rsp+1F8h+var_D0], r12
0x1800c02e7  jz      short loc_1800C030B
0x1800c02e9  lea     rdx, [rsp+1F8h+var_130]
0x1800c02f1  lea     rcx, [rsp+1F8h+var_D8]
0x1800c02f9  call    ?begin@?$Forward_Sequence@V?$CComQIPtr@UICreateDevEnum@@$1?IID_ICreateDevEnum@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@2@VDSFilterMoniker@@UICreateDevEnum@@UIEnumMoniker@@PEAUIMoniker@@V?$allocator@VDSFilterMoniker@@@std@@@@QEAA?AV?$enumerator_iterator@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@ATL@@VDSFilterMoniker@@UIEnumMoniker@@PEAUIMoniker@@_J@@XZ; Forward_Sequence<ATL::CComQIPtr<ICreateDevEnum,&_GUID const IID_ICreateDevEnum>,ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,ICreateDevEnum,IEnumMoniker,IMoniker *,std::allocator<DSFilterMoniker>>::begin(void)
0x1800c02fe  lea     rcx, [rsp+1F8h+var_130]
0x1800c0306  call    ??1?$enumerator_iterator@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@ATL@@VDSFilterMoniker@@UIEnumMoniker@@PEAUIMoniker@@_J@@QEAA@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(void)
0x1800c030b  mov     rax, [rdi+8]
0x1800c030f  movsxd  rcx, dword ptr [rax+4]
0x1800c0313  lea     r8, [rdi+50h]
0x1800c0317  add     r8, rcx
0x1800c031a  add     rcx, 28h ; '('
0x1800c031e  add     rcx, rdi
0x1800c0321  lea     rdx, [rsp+1F8h+var_148]
0x1800c0329  call    ?AddMoniker@DSGraph@@QEAA?AVDSFilter@@AEBVDSFilterMoniker@@@Z; DSGraph::AddMoniker(DSFilterMoniker const &)
0x1800c032e  nop
0x1800c032f  cmp     [rsp+1F8h+var_140], r12
0x1800c0337  jnz     short loc_1800C0398
0x1800c0339  mov     r9, cs:hInstance; HINSTANCE
0x1800c0340  mov     r8d, 0C0040597h; int
0x1800c0346  lea     rdx, _GUID_1c15d47e_911d_11d2_b632_00c04f79498e; struct _GUID *
0x1800c034d  mov     ecx, 0C0040597h; dwMessageId
0x1800c0352  call    ?Error@?$CComCoClass@VCMSVidTVTuner@@$1?_GUID_1c15d484_911d_11d2_b632_00c04f79498e@@3U__s_GUID@@B@ATL@@SAJIAEBU_GUID@@JPEAUHINSTANCE__@@@Z; ATL::CComCoClass<CMSVidTVTuner,&__s_GUID const _GUID_1c15d484_911d_11d2_b632_00c04f79498e>::Error(uint,_GUID const &,long,HINSTANCE__ *)
0x1800c0357  mov     ebx, eax
0x1800c0359  lea     rsi, ??_7?$Forward_Sequence@V?$CComQIPtr@UIBaseFilter@@$1?IID_IBaseFilter@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumPins@@$1?IID_IEnumPins@@3U_GUID@@B@2@VDSPin@@UIBaseFilter@@UIEnumPins@@PEAUIPin@@V?$allocator@VDSPin@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable'
0x1800c0360  mov     [rsp+1F8h+var_148], rsi
0x1800c0368  lea     rcx, [rsp+1F8h+var_140]
0x1800c0370  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c0375  nop
0x1800c0376  lea     rcx, [rsp+1F8h+var_D8]; this
0x1800c037e  call    ??1DSFilterMapper@@UEAA@XZ; DSFilterMapper::~DSFilterMapper(void)
0x1800c0383  nop
0x1800c0384  lea     rcx, [rsp+1F8h+var_168]
0x1800c038c  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c0391  mov     eax, ebx
0x1800c0393  jmp     loc_1800C0F57
0x1800c0398  mov     rax, [rdi+8]
0x1800c039c  movsxd  rcx, dword ptr [rax+4]
0x1800c03a0  add     rcx, 38h ; '8'
0x1800c03a4  add     rcx, rdi
0x1800c03a7  lea     rdx, [rsp+1F8h+var_148]
0x1800c03af  call    ?push_back@?$vector@VDSFilter@@V?$allocator@VDSFilter@@@std@@@std@@QEAAXAEBVDSFilter@@@Z; std::vector<DSFilter>::push_back(DSFilter const &)
0x1800c03b4  mov     [rdi+60h], r12d
0x1800c03b8  lea     rbx, [rdi+58h]
0x1800c03bc  cmp     [rbx], r12
0x1800c03bf  jnz     short loc_1800C042F
0x1800c03c1  lea     rcx, [rsp+1F8h+var_170]; ppv
0x1800c03c9  call    ??0?$CComQIPtr@UICreateDevEnum@@$1?IID_ICreateDevEnum@@3U_GUID@@B@ATL@@QEAA@AEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComQIPtr<ICreateDevEnum,&_GUID const IID_ICreateDevEnum>::CComQIPtr<ICreateDevEnum,&_GUID const IID_ICreateDevEnum>(_GUID const &,IUnknown *,ulong)
0x1800c03ce  nop
0x1800c03cf  mov     rdx, [rax]; struct IUnknown *
0x1800c03d2  mov     rcx, rbx; struct IUnknown **
0x1800c03d5  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800c03da  nop
0x1800c03db  lea     rcx, [rsp+1F8h+var_170]
0x1800c03e3  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c03e8  cmp     [rbx], r12
0x1800c03eb  jnz     short loc_1800C042F
0x1800c03ed  lea     rsi, ??_7?$Forward_Sequence@V?$CComQIPtr@UIBaseFilter@@$1?IID_IBaseFilter@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumPins@@$1?IID_IEnumPins@@3U_GUID@@B@2@VDSPin@@UIBaseFilter@@UIEnumPins@@PEAUIPin@@V?$allocator@VDSPin@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable'
0x1800c03f4  mov     [rsp+1F8h+var_148], rsi
0x1800c03fc  lea     rcx, [rsp+1F8h+var_140]
0x1800c0404  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c0409  nop
0x1800c040a  lea     rcx, [rsp+1F8h+var_D8]; this
0x1800c0412  call    ??1DSFilterMapper@@UEAA@XZ; DSFilterMapper::~DSFilterMapper(void)
0x1800c0417  nop
0x1800c0418  lea     rcx, [rsp+1F8h+var_168]
0x1800c0420  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c0425  mov     eax, 80004002h
0x1800c042a  jmp     loc_1800C0F57
0x1800c042f  lea     r8, _GUID_65e8773d_8f56_11d0_a3b9_00a0c9223196
0x1800c0436  mov     rdx, rbx
0x1800c0439  lea     rcx, [rsp+1F8h+var_90]
0x1800c0441  call    ??0DSDevices@@QEAA@AEAV?$CComQIPtr@UICreateDevEnum@@$1?IID_ICreateDevEnum@@3U_GUID@@B@ATL@@AEBU_GUID@@@Z; DSDevices::DSDevices(ATL::CComQIPtr<ICreateDevEnum,&_GUID const IID_ICreateDevEnum> &,_GUID const &)
0x1800c0446  nop
0x1800c0447  lea     rcx, [rsp+1F8h+var_108]
0x1800c044f  call    ??0?$vector@VDSPin@@V?$allocator@VDSPin@@@std@@@std@@QEAA@XZ; std::vector<DSPin>::vector<DSPin>(void)
0x1800c0454  nop
0x1800c0455  lea     rcx, [rsp+1F8h+var_A8]
0x1800c045d  call    ??0?$vector@VDSPin@@V?$allocator@VDSPin@@@std@@@std@@QEAA@XZ; std::vector<DSPin>::vector<DSPin>(void)
0x1800c0462  nop
0x1800c0463  lea     rcx, [rsp+1F8h+var_F0]
0x1800c046b  call    ??0?$vector@VDSPin@@V?$allocator@VDSPin@@@std@@@std@@QEAA@XZ; std::vector<DSPin>::vector<DSPin>(void)
0x1800c0470  nop
0x1800c0471  mov     [rsp+1F8h+pbstr], r12
0x1800c0479  mov     [rsp+1F8h+var_170], r12
0x1800c0481  lea     r8, [rsp+1F8h+pbstr]
0x1800c0489  lea     rdx, [rsp+1F8h+var_170]
0x1800c0491  lea     rcx, [rsp+1F8h+var_118]
0x1800c0499  call    ??0?$enumerator_iterator@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@ATL@@VDSFilterMoniker@@UIEnumMoniker@@PEAUIMoniker@@_J@@QEAA@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@ATL@@VDSFilterMoniker@@@Z; enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker)
0x1800c049e  nop
0x1800c049f  lea     rdx, [rsp+1F8h+var_130]
0x1800c04a7  lea     rcx, [rsp+1F8h+var_90]
0x1800c04af  call    ?begin@?$Forward_Sequence@V?$CComQIPtr@UICreateDevEnum@@$1?IID_ICreateDevEnum@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@2@VDSFilterMoniker@@UICreateDevEnum@@UIEnumMoniker@@PEAUIMoniker@@V?$allocator@VDSFilterMoniker@@@std@@@@QEAA?AV?$enumerator_iterator@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@ATL@@VDSFilterMoniker@@UIEnumMoniker@@PEAUIMoniker@@_J@@XZ; Forward_Sequence<ATL::CComQIPtr<ICreateDevEnum,&_GUID const IID_ICreateDevEnum>,ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,ICreateDevEnum,IEnumMoniker,IMoniker *,std::allocator<DSFilterMoniker>>::begin(void)
0x1800c04b4  nop
0x1800c04b5  mov     rdx, rax
0x1800c04b8  lea     rcx, [rsp+1F8h+var_118]
0x1800c04c0  call    ??4?$enumerator_iterator@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@ATL@@VDSFilterMoniker@@UIEnumMoniker@@PEAUIMoniker@@_J@@QEAAAEAV0@AEBV0@@Z; enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::operator=(enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64> const &)
0x1800c04c5  nop
0x1800c04c6  lea     rcx, [rsp+1F8h+var_130]
0x1800c04ce  call    ??1?$enumerator_iterator@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@ATL@@VDSFilterMoniker@@UIEnumMoniker@@PEAUIMoniker@@_J@@QEAA@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(void)
0x1800c04d3  lea     rdx, [rsp+1F8h+var_130]
0x1800c04db  call    ?end@?$Forward_Sequence@V?$CComQIPtr@UICreateDevEnum@@$1?IID_ICreateDevEnum@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@2@VDSFilterMoniker@@UICreateDevEnum@@UIEnumMoniker@@PEAUIMoniker@@V?$allocator@VDSFilterMoniker@@@std@@@@QEAA?AV?$enumerator_iterator@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@ATL@@VDSFilterMoniker@@UIEnumMoniker@@PEAUIMoniker@@_J@@XZ; Forward_Sequence<ATL::CComQIPtr<ICreateDevEnum,&_GUID const IID_ICreateDevEnum>,ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,ICreateDevEnum,IEnumMoniker,IMoniker *,std::allocator<DSFilterMoniker>>::end(void)
0x1800c04e0  mov     rax, [rax+8]
0x1800c04e4  cmp     [rsp+1F8h+var_110], rax
0x1800c04ec  setnz   bl
0x1800c04ef  lea     rcx, [rsp+1F8h+var_130]
0x1800c04f7  call    ??1?$enumerator_iterator@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@ATL@@VDSFilterMoniker@@UIEnumMoniker@@PEAUIMoniker@@_J@@QEAA@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(void)
0x1800c04fc  test    bl, bl
0x1800c04fe  jz      short loc_1800C0543
0x1800c0500  lea     rdx, [rsp+1F8h+var_150]
0x1800c0508  lea     rcx, [rsp+1F8h+var_118]
0x1800c0510  call    ??D?$enumerator_iterator@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@ATL@@VDSFilterMoniker@@UIEnumMoniker@@PEAUIMoniker@@_J@@QEBA?AVDSFilterMoniker@@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::operator*(void)
0x1800c0515  nop
0x1800c0516  mov     rdx, rax
0x1800c0519  lea     rcx, [rsp+1F8h+var_108]
0x1800c0521  call    ?push_back@?$vector@V?$CComQIPtr@UIMSVidDevice@@$1?_GUID_1c15d47c_911d_11d2_b632_00c04f79498e@@3U__s_GUID@@B@ATL@@V?$allocator@V?$CComQIPtr@UIMSVidDevice@@$1?_GUID_1c15d47c_911d_11d2_b632_00c04f79498e@@3U__s_GUID@@B@ATL@@@std@@@std@@QEAAXAEBV?$CComQIPtr@UIMSVidDevice@@$1?_GUID_1c15d47c_911d_11d2_b632_00c04f79498e@@3U__s_GUID@@B@ATL@@@Z; std::vector<ATL::CComQIPtr<IMSVidDevice,&__s_GUID const _GUID_1c15d47c_911d_11d2_b632_00c04f79498e>>::push_back(ATL::CComQIPtr<IMSVidDevice,&__s_GUID const _GUID_1c15d47c_911d_11d2_b632_00c04f79498e> const &)
0x1800c0526  nop
0x1800c0527  lea     rcx, [rsp+1F8h+var_150]
0x1800c052f  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c0534  lea     rcx, [rsp+1F8h+var_118]
0x1800c053c  call    ??E?$enumerator_iterator@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@ATL@@VDSFilterMoniker@@UIEnumMoniker@@PEAUIMoniker@@_J@@QEAAAEAV0@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::operator++(void)
0x1800c0541  jmp     short loc_1800C04D3
0x1800c0543  mov     rax, [rdi+8]
0x1800c0547  movsxd  rcx, dword ptr [rax+4]
0x1800c054b  add     rcx, 50h ; 'P'
0x1800c054f  add     rcx, rdi
0x1800c0552  lea     rdx, [rsp+1F8h+String]
0x1800c055a  call    ?GetDevPath@DSFilterMoniker@@QEBA?AVCComBSTR@ATL@@XZ; DSFilterMoniker::GetDevPath(void)
0x1800c055f  nop
0x1800c0560  lea     rdx, [rsp+1F8h+var_150]
0x1800c0568  lea     rcx, [rsp+1F8h+var_108]
0x1800c0570  call    ?end@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@KU?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@K@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@K@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ulong,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ulong>>,0>>::end(void)
0x1800c0575  mov     rbx, [rax]
0x1800c0578  lea     rdx, [rsp+1F8h+var_170]
0x1800c0580  lea     rcx, [rsp+1F8h+var_108]
0x1800c0588  call    ?end@?$vector@VCComBSTR@ATL@@V?$allocator@VCComBSTR@ATL@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VCComBSTR@ATL@@@std@@@std@@@2@XZ; std::vector<ATL::CComBSTR>::end(void)
0x1800c058d  cmp     rbx, [rax]
0x1800c0590  jnz     loc_1800C0E9E
0x1800c0596  lea     rcx, [rsp+1F8h+var_108]
0x1800c059e  call    ?clear@?$vector@V?$CComQIPtr@UIComponent@@$1?_GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@V?$allocator@V?$CComQIPtr@UIComponent@@$1?_GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@@std@@@std@@QEAAXXZ; std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>::clear(void)
0x1800c05a3  mov     rax, [rdi+8]
0x1800c05a7  movsxd  rcx, dword ptr [rax+4]
0x1800c05ab  add     rcx, 50h ; 'P'
0x1800c05af  add     rcx, rdi
0x1800c05b2  lea     rdx, [rsp+1F8h+bstrString]
0x1800c05ba  call    ?GetName@DSFilterMoniker@@QEBA?AVCComBSTR@ATL@@XZ; DSFilterMoniker::GetName(void)
0x1800c05bf  nop
0x1800c05c0  lea     rdx, [rsp+1F8h+var_150]
0x1800c05c8  lea     rcx, [rsp+1F8h+var_A8]
0x1800c05d0  call    ?end@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@KU?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@K@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@K@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ulong,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ulong>>,0>>::end(void)
0x1800c05d5  mov     rbx, [rax]
0x1800c05d8  lea     rdx, [rsp+1F8h+var_170]
0x1800c05e0  lea     rcx, [rsp+1F8h+var_A8]
0x1800c05e8  call    ?end@?$vector@VCComBSTR@ATL@@V?$allocator@VCComBSTR@ATL@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VCComBSTR@ATL@@@std@@@std@@@2@XZ; std::vector<ATL::CComBSTR>::end(void)
0x1800c05ed  cmp     rbx, [rax]
0x1800c05f0  jnz     loc_1800C0E15
0x1800c05f6  lea     rdx, [rsp+1F8h+var_150]
0x1800c05fe  lea     rcx, [rsp+1F8h+var_108]
0x1800c0606  call    ?end@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@KU?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@K@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@K@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ulong,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ulong>>,0>>::end(void)
0x1800c060b  mov     rbx, [rax]
0x1800c060e  lea     rdx, [rsp+1F8h+var_170]
0x1800c0616  lea     rcx, [rsp+1F8h+var_108]
0x1800c061e  call    ?end@?$vector@VCComBSTR@ATL@@V?$allocator@VCComBSTR@ATL@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VCComBSTR@ATL@@@std@@@std@@@2@XZ; std::vector<ATL::CComBSTR>::end(void)
0x1800c0623  cmp     rbx, [rax]
0x1800c0626  jnz     loc_1800C0DFC
0x1800c062c  mov     [rsp+1F8h+var_158], r12
0x1800c0634  lea     rax, ??_7DSFilter@@6B@; const DSFilter::`vftable'
0x1800c063b  mov     [rsp+1F8h+var_160], rax
0x1800c0643  lea     rcx, [rsp+1F8h+var_C0]
0x1800c064b  call    ??0?$vector@VDSPin@@V?$allocator@VDSPin@@@std@@@std@@QEAA@XZ; std::vector<DSPin>::vector<DSPin>(void)
0x1800c0650  nop
0x1800c0651  lea     rdx, [rsp+1F8h+var_150]
0x1800c0659  lea     rcx, [rsp+1F8h+var_F0]
0x1800c0661  call    ?end@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@KU?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@K@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@K@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ulong,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ulong>>,0>>::end(void)
0x1800c0666  mov     rbx, [rax]
0x1800c0669  lea     rsi, ??_7?$Forward_Sequence@V?$CComQIPtr@UIBaseFilter@@$1?IID_IBaseFilter@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumPins@@$1?IID_IEnumPins@@3U_GUID@@B@2@VDSPin@@UIBaseFilter@@UIEnumPins@@PEAUIPin@@V?$allocator@VDSPin@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable'
0x1800c0670  lea     rdx, [rsp+1F8h+var_170]
0x1800c0678  lea     rcx, [rsp+1F8h+var_F0]
0x1800c0680  call    ?end@?$vector@VCComBSTR@ATL@@V?$allocator@VCComBSTR@ATL@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VCComBSTR@ATL@@@std@@@std@@@2@XZ; std::vector<ATL::CComBSTR>::end(void)
0x1800c0685  cmp     rbx, [rax]
  ... truncated ...
```
