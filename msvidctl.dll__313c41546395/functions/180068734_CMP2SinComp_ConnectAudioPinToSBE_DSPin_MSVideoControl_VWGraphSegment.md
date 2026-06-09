# CMP2SinComp::ConnectAudioPinToSBE(DSPin &,MSVideoControl::VWGraphSegment &)

- ea: `0x180068734`
- end: `0x1800689e3`
- name: `?ConnectAudioPinToSBE@CMP2SinComp@@QEAAJAEAVDSPin@@AEAVVWGraphSegment@MSVideoControl@@@Z`
- size: `687`
- prototype: `int(CMP2SinComp *__hidden this, struct DSPin *, struct MSVideoControl::VWGraphSegment *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180064a20`

## callees

- `0x180004640`
- `0x180006b38`
- `0x18000df18`
- `0x18000e1b8`
- `0x18000e518`
- `0x18002a658`
- `0x1800566c8`
- `0x180057504`
- `0x180057fa8`
- `0x180059894`
- `0x18005a0d8`
- `0x180068734`
- `0x18006e890`
- `0x18006fdec`
- `0x180076e0c`
- `0x1800d76bc`
- `0x1800d8060`
- `0x1800eee0c`
- `0x1800f8010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180068802`
- `ole32!CoCreateInstance` at `0x180068802`
- `OLEAUT32!__imp_SysFreeString` at `0x180068812`
- `OLEAUT32!__imp_SysFreeString` at `0x180068912`
- `OLEAUT32!__imp_SysFreeString` at `0x18006898d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800689a3`
- `OLEAUT32!__imp_SysFreeString` at `0x180068812`
- `OLEAUT32!__imp_SysFreeString` at `0x180068912`
- `OLEAUT32!__imp_SysFreeString` at `0x18006898d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800689a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CMP2SinComp::ConnectAudioPinToSBE(
        CMP2SinComp *this,
        struct IUnknown **a2,
        struct MSVideoControl::VWGraphSegment *a3)
{
  __int64 v6; // rax
  HRESULT v7; // edi
  char *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  void **v12; // [rsp+30h] [rbp-49h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-41h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v15[8]; // [rsp+48h] [rbp-31h] BYREF
  __int64 v16; // [rsp+50h] [rbp-29h] BYREF
  void **v17; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v18[8]; // [rsp+60h] [rbp-19h] BYREF
  void **v19; // [rsp+68h] [rbp-11h] BYREF
  _BYTE v20[16]; // [rsp+70h] [rbp-9h] BYREF
  CLSID Buf1; // [rsp+80h] [rbp+7h] BYREF

  ATL::CComQIPtr<IMSVidStreamBufferSink3,&__s_GUID const _GUID_4f8721d7_7d59_4d8b_99f5_a77775586bd5>::CComQIPtr<IMSVidStreamBufferSink3,&__s_GUID const _GUID_4f8721d7_7d59_4d8b_99f5_a77775586bd5>(
    &v16,
    *((_QWORD *)a3 + 1));
  if ( !v16 )
    goto LABEL_23;
  ppv = 0;
  v12 = &DSFilter::`vftable';
  bstrString = 0;
  if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v16 + 232LL))(v16, &bstrString) >= 0 )
  {
    v6 = -1;
    do
      ++v6;
    while ( bstrString[v6] );
    if ( v6 )
    {
      GUID2::operator=(&Buf1, bstrString);
      if ( memcmp_0(&Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
      {
        v7 = CoCreateInstance(&Buf1, 0, 0x17u, &GUID_56a86895_0ad4_11ce_b03a_0020af0ba770, &ppv);
        if ( v7 < 0 )
          goto LABEL_8;
      }
    }
  }
  if ( !ppv )
  {
LABEL_20:
    v10 = Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::begin(
            a3,
            &v19);
    enumerator_iterator<ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IEnumFilters,IBaseFilter *,__int64>::operator*(
      v10,
      &v17);
    enumerator_iterator<ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IEnumFilters,IBaseFilter *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IEnumFilters,IBaseFilter *,__int64>(&v19);
    v7 = CMP2SinComp::IntelligentConnectPinToSBE(this, (struct DSPin *)a2, (struct DSFilter *)&v17);
    v17 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
    if ( v7 < 0 )
    {
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v18);
      SysFreeString(bstrString);
      goto LABEL_9;
    }
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v18);
    SysFreeString(bstrString);
    v12 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
LABEL_23:
    v7 = 0;
    goto LABEL_24;
  }
  WTL::CString::CString((WTL::CString *)v15, L"Audio Analysis");
  v7 = DSGraph::AddFilter(
         (CMP2SinComp *)((char *)this + *(int *)(*((_QWORD *)this + 3) + 4LL) + 56),
         (struct DSFilter *)&v12,
         (struct WTL::CString *)v15);
  if ( v7 >= 0 )
  {
    v7 = DSPin::Connect((DSPin *)a2, (struct DSFilter *)&v12, 0);
    if ( v7 >= 0 )
    {
      v8 = (char *)this + *(int *)(*((_QWORD *)this + 3) + 4LL);
      if ( *((_QWORD *)v8 + 10) == *((_QWORD *)v8 + 11) )
      {
        std::vector<DSFilter>::_Emplace_reallocate<DSFilter>(v8 + 72, *((_QWORD *)v8 + 10), &v12);
      }
      else
      {
        DSFilter::DSFilter(*((DSFilter **)v8 + 10), (const struct DSFilter *)&v12);
        *((_QWORD *)v8 + 10) += 16LL;
      }
      v9 = DSFilter::FirstPin(&v12, &v19, 1);
      ATL::AtlComPtrAssign(a2 + 1, *(struct IUnknown **)(v9 + 8));
      v19 = &Forward_Sequence<ATL::CComQIPtr<IPin,&_GUID const IID_IPin>,ATL::CComQIPtr<IEnumMediaTypes,&_GUID const IID_IEnumMediaTypes>,DSMediaType,IPin,IEnumMediaTypes,_AMMediaType *,std::allocator<DSMediaType>>::`vftable';
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v20);
      if ( !a2[1] )
      {
        WTL::CString::~CString((WTL::CString *)v15);
        SysFreeString(bstrString);
        v12 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
        v7 = -2147467259;
        goto LABEL_24;
      }
      WTL::CString::~CString((WTL::CString *)v15);
      goto LABEL_20;
    }
  }
  WTL::CString::~CString((WTL::CString *)v15);
LABEL_8:
  SysFreeString(bstrString);
LABEL_9:
  v12 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
LABEL_24:
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v16);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180068734  push    rbp
0x180068736  push    rbx
0x180068737  push    rsi
0x180068738  push    rdi
0x180068739  push    r12
0x18006873b  push    r14
0x18006873d  push    r15
0x18006873f  lea     rbp, [rsp-27h]
0x180068744  sub     rsp, 0A0h
0x18006874b  mov     rax, cs:__security_cookie
0x180068752  xor     rax, rsp
0x180068755  mov     [rbp+57h+var_40], rax
0x180068759  mov     r15, r8
0x18006875c  mov     r14, rdx
0x18006875f  mov     rsi, rcx
0x180068762  mov     rdx, [r8+8]
0x180068766  lea     rcx, [rbp+57h+var_80]
0x18006876a  call    ??0?$CComQIPtr@UIMSVidStreamBufferSink3@@$1?_GUID_4f8721d7_7d59_4d8b_99f5_a77775586bd5@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IMSVidStreamBufferSink3,&__s_GUID const _GUID_4f8721d7_7d59_4d8b_99f5_a77775586bd5>::CComQIPtr<IMSVidStreamBufferSink3,&__s_GUID const _GUID_4f8721d7_7d59_4d8b_99f5_a77775586bd5>(IUnknown *)
0x18006876f  nop
0x180068770  mov     rcx, [rbp+57h+var_80]
0x180068774  xor     r12d, r12d
0x180068777  test    rcx, rcx
0x18006877a  jz      loc_1800689B7
0x180068780  mov     [rbp+57h+var_98], r12
0x180068784  lea     rax, ??_7DSFilter@@6B@; const DSFilter::`vftable'
0x18006878b  mov     [rbp+57h+var_A0], rax
0x18006878f  mov     [rbp+57h+bstrString], r12
0x180068793  mov     rax, [rcx]
0x180068796  lea     rdx, [rbp+57h+bstrString]
0x18006879a  mov     rax, [rax+0E8h]
0x1800687a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800687a6  test    eax, eax
0x1800687a8  js      loc_180068832
0x1800687ae  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x1800687b2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800687b6  inc     rax
0x1800687b9  cmp     [rdx+rax*2], r12w
0x1800687be  jnz     short loc_1800687B6
0x1800687c0  test    rax, rax
0x1800687c3  jz      short loc_180068832
0x1800687c5  lea     rcx, [rbp+57h+Buf1]; pclsid
0x1800687c9  call    ??4GUID2@@QEAAAEAV0@QEAG@Z; GUID2::operator=(ushort * const)
0x1800687ce  mov     r8d, 10h; Size
0x1800687d4  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x1800687db  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800687df  call    memcmp_0
0x1800687e4  test    eax, eax
0x1800687e6  jz      short loc_180068832
0x1800687e8  lea     rax, [rbp+57h+var_98]
0x1800687ec  mov     [rsp+0D0h+ppv], rax; ppv
0x1800687f1  lea     r9, _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770; riid
0x1800687f8  xor     edx, edx; pUnkOuter
0x1800687fa  lea     r8d, [rdx+17h]; dwClsContext
0x1800687fe  lea     rcx, [rbp+57h+Buf1]; rclsid
0x180068802  call    cs:__imp_CoCreateInstance
0x180068808  mov     edi, eax
0x18006880a  test    eax, eax
0x18006880c  jns     short loc_180068832
0x18006880e  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180068812  call    cs:__imp_SysFreeString
0x180068818  nop
0x180068819  lea     rbx, ??_7?$Forward_Sequence@V?$CComQIPtr@UIBaseFilter@@$1?IID_IBaseFilter@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumPins@@$1?IID_IEnumPins@@3U_GUID@@B@2@VDSPin@@UIBaseFilter@@UIEnumPins@@PEAUIPin@@V?$allocator@VDSPin@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable'
0x180068820  mov     [rbp+57h+var_A0], rbx
0x180068824  lea     rcx, [rbp+57h+var_98]
0x180068828  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18006882d  jmp     loc_1800689BA
0x180068832  cmp     [rbp+57h+var_98], r12
0x180068836  jz      loc_18006893C
0x18006883c  lea     rdx, aAudioAnalysis; "Audio Analysis"
0x180068843  lea     rcx, [rbp+57h+var_88]; this
0x180068847  call    ??0CString@WTL@@QEAA@PEBG@Z; WTL::CString::CString(ushort const *)
0x18006884c  nop
0x18006884d  mov     rax, [rsi+18h]
0x180068851  movsxd  rcx, dword ptr [rax+4]
0x180068855  add     rcx, 38h ; '8'
0x180068859  add     rcx, rsi; this
0x18006885c  lea     r8, [rbp+57h+var_88]; struct WTL::CString *
0x180068860  lea     rdx, [rbp+57h+var_A0]; struct DSFilter *
0x180068864  call    ?AddFilter@DSGraph@@QEAAJAEAVDSFilter@@AEAVCString@WTL@@@Z; DSGraph::AddFilter(DSFilter &,WTL::CString &)
0x180068869  mov     edi, eax
0x18006886b  test    eax, eax
0x18006886d  jns     short loc_18006887A
0x18006886f  lea     rcx, [rbp+57h+var_88]; this
0x180068873  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180068878  jmp     short loc_18006880E
0x18006887a  xor     r8d, r8d; struct _AMMediaType *
0x18006887d  lea     rdx, [rbp+57h+var_A0]; struct DSFilter *
0x180068881  mov     rcx, r14; this
0x180068884  call    ?Connect@DSPin@@QEAAJAEAVDSFilter@@PEBU_AMMediaType@@@Z; DSPin::Connect(DSFilter &,_AMMediaType const *)
0x180068889  mov     edi, eax
0x18006888b  test    eax, eax
0x18006888d  js      short loc_18006886F
0x18006888f  mov     rax, [rsi+18h]
0x180068893  movsxd  rbx, dword ptr [rax+4]
0x180068897  add     rbx, rsi
0x18006889a  mov     rax, [rbx+50h]
0x18006889e  cmp     rax, [rbx+58h]
0x1800688a2  jz      short loc_1800688B7
0x1800688a4  lea     rdx, [rbp+57h+var_A0]; struct DSFilter *
0x1800688a8  mov     rcx, rax; this
0x1800688ab  call    ??0DSFilter@@QEAA@AEBV0@@Z; DSFilter::DSFilter(DSFilter const &)
0x1800688b0  add     qword ptr [rbx+50h], 10h
0x1800688b5  jmp     short loc_1800688C7
0x1800688b7  lea     r8, [rbp+57h+var_A0]
0x1800688bb  mov     rdx, rax
0x1800688be  lea     rcx, [rbx+48h]
0x1800688c2  call    ??$_Emplace_reallocate@VDSFilter@@@?$vector@VDSFilter@@V?$allocator@VDSFilter@@@std@@@std@@AEAAPEAVDSFilter@@QEAV2@$$QEAV2@@Z; std::vector<DSFilter>::_Emplace_reallocate<DSFilter>(DSFilter * const,DSFilter &&)
0x1800688c7  mov     r8d, 1
0x1800688cd  lea     rdx, [rbp+57h+var_68]
0x1800688d1  lea     rcx, [rbp+57h+var_A0]
0x1800688d5  call    ?FirstPin@DSFilter@@QEBA?AVDSPin@@W4_PinDirection@@@Z; DSFilter::FirstPin(_PinDirection)
0x1800688da  nop
0x1800688db  mov     rdx, [rax+8]; struct IUnknown *
0x1800688df  lea     rcx, [r14+8]; struct IUnknown **
0x1800688e3  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800688e8  nop
0x1800688e9  lea     rax, ??_7?$Forward_Sequence@V?$CComQIPtr@UIPin@@$1?IID_IPin@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumMediaTypes@@$1?IID_IEnumMediaTypes@@3U_GUID@@B@2@VDSMediaType@@UIPin@@UIEnumMediaTypes@@PEAU_AMMediaType@@V?$allocator@VDSMediaType@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IPin,&_GUID const IID_IPin>,ATL::CComQIPtr<IEnumMediaTypes,&_GUID const IID_IEnumMediaTypes>,DSMediaType,IPin,IEnumMediaTypes,_AMMediaType *,std::allocator<DSMediaType>>::`vftable'
0x1800688f0  mov     [rbp+57h+var_68], rax
0x1800688f4  lea     rcx, [rbp+57h+var_60]
0x1800688f8  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800688fd  nop
0x1800688fe  lea     rcx, [rbp+57h+var_88]; this
0x180068902  cmp     [r14+8], r12
0x180068906  jnz     short loc_180068937
0x180068908  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18006890d  nop
0x18006890e  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180068912  call    cs:__imp_SysFreeString
0x180068918  nop
0x180068919  lea     rbx, ??_7?$Forward_Sequence@V?$CComQIPtr@UIBaseFilter@@$1?IID_IBaseFilter@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumPins@@$1?IID_IEnumPins@@3U_GUID@@B@2@VDSPin@@UIBaseFilter@@UIEnumPins@@PEAUIPin@@V?$allocator@VDSPin@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable'
0x180068920  mov     [rbp+57h+var_A0], rbx
0x180068924  lea     rcx, [rbp+57h+var_98]
0x180068928  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18006892d  mov     edi, 80004005h
0x180068932  jmp     loc_1800689BA
0x180068937  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18006893c  lea     rdx, [rbp+57h+var_68]
0x180068940  mov     rcx, r15
0x180068943  call    ?begin@?$Forward_Sequence@V?$CComQIPtr@UIMSVidGraphSegment@@$1?_GUID_238dec54_adeb_4005_a349_f772b9afebc4@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIEnumFilters@@$1?IID_IEnumFilters@@3U_GUID@@B@2@VDSFilter@@UIMSVidGraphSegment@@UIEnumFilters@@PEAUIBaseFilter@@V?$allocator@VDSFilter@@@std@@@@QEAA?AV?$enumerator_iterator@V?$CComQIPtr@UIEnumFilters@@$1?IID_IEnumFilters@@3U_GUID@@B@ATL@@VDSFilter@@UIEnumFilters@@PEAUIBaseFilter@@_J@@XZ; Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::begin(void)
0x180068948  nop
0x180068949  lea     rdx, [rbp+57h+var_78]
0x18006894d  mov     rcx, rax
0x180068950  call    ??D?$enumerator_iterator@V?$CComQIPtr@UIEnumFilters@@$1?IID_IEnumFilters@@3U_GUID@@B@ATL@@VDSFilter@@UIEnumFilters@@PEAUIBaseFilter@@_J@@QEBA?AVDSFilter@@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IEnumFilters,IBaseFilter *,__int64>::operator*(void)
0x180068955  nop
0x180068956  lea     rcx, [rbp+57h+var_68]
0x18006895a  call    ??1?$enumerator_iterator@V?$CComQIPtr@UIEnumFilters@@$1?IID_IEnumFilters@@3U_GUID@@B@ATL@@VDSFilter@@UIEnumFilters@@PEAUIBaseFilter@@_J@@QEAA@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IEnumFilters,IBaseFilter *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IEnumFilters,IBaseFilter *,__int64>(void)
0x18006895f  lea     r8, [rbp+57h+var_78]; struct DSFilter *
0x180068963  mov     rdx, r14; struct DSPin *
0x180068966  mov     rcx, rsi; this
0x180068969  call    ?IntelligentConnectPinToSBE@CMP2SinComp@@QEAAJAEAVDSPin@@AEAVDSFilter@@@Z; CMP2SinComp::IntelligentConnectPinToSBE(DSPin &,DSFilter &)
0x18006896e  mov     edi, eax
0x180068970  lea     rbx, ??_7?$Forward_Sequence@V?$CComQIPtr@UIBaseFilter@@$1?IID_IBaseFilter@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumPins@@$1?IID_IEnumPins@@3U_GUID@@B@2@VDSPin@@UIBaseFilter@@UIEnumPins@@PEAUIPin@@V?$allocator@VDSPin@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable'
0x180068977  lea     rcx, [rbp+57h+var_70]
0x18006897b  mov     [rbp+57h+var_78], rbx
0x18006897f  test    eax, eax
0x180068981  jns     short loc_180068999
0x180068983  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180068988  nop
0x180068989  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18006898d  call    cs:__imp_SysFreeString
0x180068993  nop
0x180068994  jmp     loc_180068820
0x180068999  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18006899e  nop
0x18006899f  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800689a3  call    cs:__imp_SysFreeString
0x1800689a9  nop
0x1800689aa  mov     [rbp+57h+var_A0], rbx
0x1800689ae  lea     rcx, [rbp+57h+var_98]
0x1800689b2  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800689b7  mov     edi, r12d
0x1800689ba  lea     rcx, [rbp+57h+var_80]
0x1800689be  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800689c3  mov     eax, edi
0x1800689c5  mov     rcx, [rbp+57h+var_40]
0x1800689c9  xor     rcx, rsp; StackCookie
0x1800689cc  call    __security_check_cookie
0x1800689d1  add     rsp, 0A0h
0x1800689d8  pop     r15
0x1800689da  pop     r14
0x1800689dc  pop     r12
0x1800689de  pop     rdi
0x1800689df  pop     rsi
0x1800689e0  pop     rbx
0x1800689e1  pop     rbp
0x1800689e2  retn
```
