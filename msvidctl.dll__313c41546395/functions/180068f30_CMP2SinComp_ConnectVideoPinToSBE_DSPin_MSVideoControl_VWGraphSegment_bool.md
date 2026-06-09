# CMP2SinComp::ConnectVideoPinToSBE(DSPin &,MSVideoControl::VWGraphSegment &,bool &)

- ea: `0x180068f30`
- end: `0x180069308`
- name: `?ConnectVideoPinToSBE@CMP2SinComp@@QEAAJAEAVDSPin@@AEAVVWGraphSegment@MSVideoControl@@AEA_N@Z`
- size: `984`
- prototype: `__int64 __fastcall(CMP2SinComp *__hidden this, struct DSPin *, struct MSVideoControl::VWGraphSegment *, bool *)`
- caller_count: `1`
- callee_count: `23`
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
- `0x180058094`
- `0x180059894`
- `0x180059e40`
- `0x18005a0d8`
- `0x1800689ec`
- `0x180068f30`
- `0x18006e13c`
- `0x180076b78`
- `0x180076e0c`
- `0x1800d76bc`
- `0x1800d7ebc`
- `0x1800d8060`
- `0x1800eee0c`
- `0x1800f8010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18006901e`
- `ole32!CoCreateInstance` at `0x18006901e`
- `OLEAUT32!__imp_SysFreeString` at `0x18006902f`
- `OLEAUT32!__imp_SysFreeString` at `0x18006905d`
- `OLEAUT32!__imp_SysFreeString` at `0x180069280`
- `OLEAUT32!__imp_SysFreeString` at `0x1800692c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18006902f`
- `OLEAUT32!__imp_SysFreeString` at `0x18006905d`
- `OLEAUT32!__imp_SysFreeString` at `0x180069280`
- `OLEAUT32!__imp_SysFreeString` at `0x1800692c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CMP2SinComp::ConnectVideoPinToSBE(
        CMP2SinComp *this,
        struct IUnknown **a2,
        struct MSVideoControl::VWGraphSegment *a3,
        bool *a4)
{
  OLECHAR *v8; // rcx
  __int64 v9; // rax
  HRESULT v10; // edi
  char *v11; // rbx
  __int64 v12; // r8
  __int64 PinWithMediaType; // rax
  __int64 v14; // rax
  void **v16; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v19[8]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  void **v21; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v22[16]; // [rsp+60h] [rbp-A0h] BYREF
  struct _GUID v23; // [rsp+70h] [rbp-90h] BYREF
  __int128 v24; // [rsp+80h] [rbp-80h] BYREF
  __int64 v25; // [rsp+90h] [rbp-70h]
  struct _GUID v26; // [rsp+A0h] [rbp-60h] BYREF
  struct _GUID v27; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v28[56]; // [rsp+D0h] [rbp-30h] BYREF
  CLSID Buf1; // [rsp+108h] [rbp+8h] BYREF

  ATL::CComQIPtr<IMSVidStreamBufferSink3,&__s_GUID const _GUID_4f8721d7_7d59_4d8b_99f5_a77775586bd5>::CComQIPtr<IMSVidStreamBufferSink3,&__s_GUID const _GUID_4f8721d7_7d59_4d8b_99f5_a77775586bd5>(
    &v20,
    *((_QWORD *)a3 + 1));
  if ( !v20 )
    goto LABEL_29;
  ppv = 0;
  v16 = &DSFilter::`vftable';
  bstrString = 0;
  if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v20 + 264LL))(v20, &bstrString) < 0 )
    goto LABEL_11;
  v8 = bstrString;
  v9 = -1;
  do
    ++v9;
  while ( bstrString[v9] );
  if ( v9 )
  {
    GUID2::operator=(&Buf1, bstrString);
    if ( !memcmp_0(&Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
      Buf1 = CLSID_Mpeg2VideoStreamAnalyzer;
    v10 = CoCreateInstance(&Buf1, 0, 0x17u, &GUID_56a86895_0ad4_11ce_b03a_0020af0ba770, &ppv);
    if ( v10 < 0 )
      goto LABEL_9;
LABEL_11:
    v8 = bstrString;
  }
  if ( !ppv )
  {
LABEL_13:
    SysFreeString(v8);
    v16 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
    v10 = -2147467259;
    goto LABEL_30;
  }
  WTL::CString::CString((WTL::CString *)v19, L"Video Analysis");
  v10 = DSGraph::AddFilter(
          (CMP2SinComp *)((char *)this + *(int *)(*((_QWORD *)this + 3) + 4LL) + 56),
          (struct DSFilter *)&v16,
          (struct WTL::CString *)v19);
  if ( v10 >= 0 )
  {
    v10 = DSPin::Connect((DSPin *)a2, (struct DSFilter *)&v16, 0);
    if ( v10 >= 0 )
    {
      v11 = (char *)this + *(int *)(*((_QWORD *)this + 3) + 4LL);
      if ( *((_QWORD *)v11 + 10) == *((_QWORD *)v11 + 11) )
      {
        std::vector<DSFilter>::_Emplace_reallocate<DSFilter>(v11 + 72, *((_QWORD *)v11 + 10), &v16);
      }
      else
      {
        DSFilter::DSFilter(*((DSFilter **)v11 + 10), (const struct DSFilter *)&v16);
        *((_QWORD *)v11 + 10) += 16LL;
      }
      v23 = FORMAT_MPEG2Video;
      v27 = MEDIASUBTYPE_MPEG2_VIDEO;
      v26 = MEDIATYPE_Video;
      DSMediaType::DSMediaType((DSMediaType *)v28, &v26, &v27, &v23);
      PinWithMediaType = DSFilter::FindPinWithMediaType(&v16, &v23, v12, v28);
      ATL::AtlComPtrAssign(a2 + 1, *(struct IUnknown **)(PinWithMediaType + 8));
      *(_QWORD *)&v23.Data1 = &Forward_Sequence<ATL::CComQIPtr<IPin,&_GUID const IID_IPin>,ATL::CComQIPtr<IEnumMediaTypes,&_GUID const IID_IEnumMediaTypes>,DSMediaType,IPin,IEnumMediaTypes,_AMMediaType *,std::allocator<DSMediaType>>::`vftable';
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v23.Data4);
      if ( !a2[1] )
      {
        DSMediaType::~DSMediaType((DSMediaType *)v28);
        WTL::CString::~CString((WTL::CString *)v19);
        v8 = bstrString;
        goto LABEL_13;
      }
      if ( *a4 )
      {
        v10 = CMP2SinComp::ConnectCCA(this, (struct DSFilter *)&v16, a4);
        if ( v10 < 0 && *a4 )
        {
          DSMediaType::~DSMediaType((DSMediaType *)v28);
          goto LABEL_15;
        }
      }
      v14 = Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::begin(
              a3,
              &v26);
      enumerator_iterator<ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IEnumFilters,IBaseFilter *,__int64>::operator*(
        v14,
        &v21);
      enumerator_iterator<ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IEnumFilters,IBaseFilter *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IEnumFilters,IBaseFilter *,__int64>(&v26);
      v24 = 0;
      v25 = 0;
      v10 = DSGraph::Connect(
              (int)this + *(_DWORD *)(*((_QWORD *)this + 3) + 4LL) + 56,
              (unsigned int)&v16,
              (unsigned int)&v21,
              (unsigned int)&v24,
              0,
              1);
      if ( v10 < 0 )
      {
        std::vector<DSFilter>::_Tidy(&v24);
        v21 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v22);
        DSMediaType::~DSMediaType((DSMediaType *)v28);
        WTL::CString::~CString((WTL::CString *)v19);
        SysFreeString(bstrString);
        goto LABEL_10;
      }
      std::vector<DSFilter>::_Tidy(&v24);
      v21 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v22);
      DSMediaType::~DSMediaType((DSMediaType *)v28);
      WTL::CString::~CString((WTL::CString *)v19);
      SysFreeString(bstrString);
      v16 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
LABEL_29:
      v10 = 0;
      goto LABEL_30;
    }
  }
LABEL_15:
  WTL::CString::~CString((WTL::CString *)v19);
LABEL_9:
  SysFreeString(bstrString);
LABEL_10:
  v16 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
LABEL_30:
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v20);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180068f30  push    rbp
0x180068f32  push    rbx
0x180068f33  push    rsi
0x180068f34  push    rdi
0x180068f35  push    r12
0x180068f37  push    r13
0x180068f39  push    r14
0x180068f3b  push    r15
0x180068f3d  lea     rbp, [rsp-28h]
0x180068f42  sub     rsp, 128h
0x180068f49  mov     rax, cs:__security_cookie
0x180068f50  xor     rax, rsp
0x180068f53  mov     [rbp+60h+var_48], rax
0x180068f57  mov     r14, r9
0x180068f5a  mov     r13, r8
0x180068f5d  mov     r15, rdx
0x180068f60  mov     rsi, rcx
0x180068f63  mov     rdx, [r8+8]
0x180068f67  lea     rcx, [rsp+160h+var_110]
0x180068f6c  call    ??0?$CComQIPtr@UIMSVidStreamBufferSink3@@$1?_GUID_4f8721d7_7d59_4d8b_99f5_a77775586bd5@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IMSVidStreamBufferSink3,&__s_GUID const _GUID_4f8721d7_7d59_4d8b_99f5_a77775586bd5>::CComQIPtr<IMSVidStreamBufferSink3,&__s_GUID const _GUID_4f8721d7_7d59_4d8b_99f5_a77775586bd5>(IUnknown *)
0x180068f71  nop
0x180068f72  mov     rcx, [rsp+160h+var_110]
0x180068f77  xor     r12d, r12d
0x180068f7a  test    rcx, rcx
0x180068f7d  jz      loc_1800692D9
0x180068f83  mov     [rsp+160h+var_128], r12
0x180068f88  lea     rax, ??_7DSFilter@@6B@; const DSFilter::`vftable'
0x180068f8f  mov     [rsp+160h+var_130], rax
0x180068f94  mov     [rsp+160h+bstrString], r12
0x180068f99  mov     rax, [rcx]
0x180068f9c  lea     rdx, [rsp+160h+bstrString]
0x180068fa1  mov     rax, [rax+108h]
0x180068fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068fad  test    eax, eax
0x180068faf  js      loc_180069051
0x180068fb5  mov     rcx, [rsp+160h+bstrString]
0x180068fba  or      rax, 0FFFFFFFFFFFFFFFFh
0x180068fbe  inc     rax
0x180068fc1  cmp     [rcx+rax*2], r12w
0x180068fc6  jnz     short loc_180068FBE
0x180068fc8  test    rax, rax
0x180068fcb  jz      loc_180069056
0x180068fd1  mov     rdx, rcx; unsigned __int16 *
0x180068fd4  lea     rcx, [rbp+60h+Buf1]; pclsid
0x180068fd8  call    ??4GUID2@@QEAAAEAV0@QEAG@Z; GUID2::operator=(ushort * const)
0x180068fdd  mov     r8d, 10h; Size
0x180068fe3  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x180068fea  lea     rcx, [rbp+60h+Buf1]; Buf1
0x180068fee  call    memcmp_0
0x180068ff3  test    eax, eax
0x180068ff5  jnz     short loc_180069003
0x180068ff7  movups  xmm0, xmmword ptr cs:CLSID_Mpeg2VideoStreamAnalyzer.Data1
0x180068ffe  movdqu  [rbp+60h+Buf1], xmm0
0x180069003  lea     rax, [rsp+160h+var_128]
0x180069008  mov     [rsp+160h+ppv], rax; ppv
0x18006900d  lea     r9, _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770; riid
0x180069014  xor     edx, edx; pUnkOuter
0x180069016  lea     r8d, [rdx+17h]; dwClsContext
0x18006901a  lea     rcx, [rbp+60h+Buf1]; rclsid
0x18006901e  call    cs:__imp_CoCreateInstance
0x180069024  mov     edi, eax
0x180069026  test    eax, eax
0x180069028  jns     short loc_180069051
0x18006902a  mov     rcx, [rsp+160h+bstrString]; bstrString
0x18006902f  call    cs:__imp_SysFreeString
0x180069035  nop
0x180069036  lea     rbx, ??_7?$Forward_Sequence@V?$CComQIPtr@UIBaseFilter@@$1?IID_IBaseFilter@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumPins@@$1?IID_IEnumPins@@3U_GUID@@B@2@VDSPin@@UIBaseFilter@@UIEnumPins@@PEAUIPin@@V?$allocator@VDSPin@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable'
0x18006903d  mov     [rsp+160h+var_130], rbx
0x180069042  lea     rcx, [rsp+160h+var_128]
0x180069047  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18006904c  jmp     loc_1800692DC
0x180069051  mov     rcx, [rsp+160h+bstrString]; bstrString
0x180069056  cmp     [rsp+160h+var_128], r12
0x18006905b  jnz     short loc_180069084
0x18006905d  call    cs:__imp_SysFreeString
0x180069063  nop
0x180069064  lea     rbx, ??_7?$Forward_Sequence@V?$CComQIPtr@UIBaseFilter@@$1?IID_IBaseFilter@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumPins@@$1?IID_IEnumPins@@3U_GUID@@B@2@VDSPin@@UIBaseFilter@@UIEnumPins@@PEAUIPin@@V?$allocator@VDSPin@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable'
0x18006906b  mov     [rsp+160h+var_130], rbx
0x180069070  lea     rcx, [rsp+160h+var_128]
0x180069075  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18006907a  mov     edi, 80004005h
0x18006907f  jmp     loc_1800692DC
0x180069084  lea     rdx, aVideoAnalysis; "Video Analysis"
0x18006908b  lea     rcx, [rsp+160h+var_118]; this
0x180069090  call    ??0CString@WTL@@QEAA@PEBG@Z; WTL::CString::CString(ushort const *)
0x180069095  nop
0x180069096  mov     rax, [rsi+18h]
0x18006909a  movsxd  rcx, dword ptr [rax+4]
0x18006909e  add     rcx, 38h ; '8'
0x1800690a2  add     rcx, rsi; this
0x1800690a5  lea     r8, [rsp+160h+var_118]; struct WTL::CString *
0x1800690aa  lea     rdx, [rsp+160h+var_130]; struct DSFilter *
0x1800690af  call    ?AddFilter@DSGraph@@QEAAJAEAVDSFilter@@AEAVCString@WTL@@@Z; DSGraph::AddFilter(DSFilter &,WTL::CString &)
0x1800690b4  mov     edi, eax
0x1800690b6  test    eax, eax
0x1800690b8  jns     short loc_1800690C9
0x1800690ba  lea     rcx, [rsp+160h+var_118]; this
0x1800690bf  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x1800690c4  jmp     loc_18006902A
0x1800690c9  xor     r8d, r8d; struct _AMMediaType *
0x1800690cc  lea     rdx, [rsp+160h+var_130]; struct DSFilter *
0x1800690d1  mov     rcx, r15; this
0x1800690d4  call    ?Connect@DSPin@@QEAAJAEAVDSFilter@@PEBU_AMMediaType@@@Z; DSPin::Connect(DSFilter &,_AMMediaType const *)
0x1800690d9  mov     edi, eax
0x1800690db  test    eax, eax
0x1800690dd  js      short loc_1800690BA
0x1800690df  mov     rax, [rsi+18h]
0x1800690e3  movsxd  rbx, dword ptr [rax+4]
0x1800690e7  add     rbx, rsi
0x1800690ea  mov     rax, [rbx+50h]
0x1800690ee  cmp     rax, [rbx+58h]
0x1800690f2  jz      short loc_180069108
0x1800690f4  lea     rdx, [rsp+160h+var_130]; struct DSFilter *
0x1800690f9  mov     rcx, rax; this
0x1800690fc  call    ??0DSFilter@@QEAA@AEBV0@@Z; DSFilter::DSFilter(DSFilter const &)
0x180069101  add     qword ptr [rbx+50h], 10h
0x180069106  jmp     short loc_180069119
0x180069108  lea     r8, [rsp+160h+var_130]
0x18006910d  mov     rdx, rax
0x180069110  lea     rcx, [rbx+48h]
0x180069114  call    ??$_Emplace_reallocate@VDSFilter@@@?$vector@VDSFilter@@V?$allocator@VDSFilter@@@std@@@std@@AEAAPEAVDSFilter@@QEAV2@$$QEAV2@@Z; std::vector<DSFilter>::_Emplace_reallocate<DSFilter>(DSFilter * const,DSFilter &&)
0x180069119  movups  xmm0, xmmword ptr cs:FORMAT_MPEG2Video.Data1
0x180069120  movdqu  xmmword ptr [rsp+160h+var_F0.Data1], xmm0
0x180069126  movups  xmm1, xmmword ptr cs:MEDIASUBTYPE_MPEG2_VIDEO.Data1
0x18006912d  movdqu  xmmword ptr [rbp+60h+var_A0.Data1], xmm1
0x180069132  movups  xmm0, xmmword ptr cs:MEDIATYPE_Video.Data1
0x180069139  movdqu  xmmword ptr [rbp+60h+var_C0.Data1], xmm0
0x18006913e  lea     r9, [rsp+160h+var_F0]; struct _GUID
0x180069143  lea     r8, [rbp+60h+var_A0]; struct _GUID
0x180069147  lea     rdx, [rbp+60h+var_C0]; struct _GUID
0x18006914b  lea     rcx, [rbp+60h+var_90]; this
0x18006914f  call    ??0DSMediaType@@QEAA@U_GUID@@00@Z; DSMediaType::DSMediaType(_GUID,_GUID,_GUID)
0x180069154  nop
0x180069155  lea     r9, [rbp+60h+var_90]
0x180069159  lea     rdx, [rsp+160h+var_F0]
0x18006915e  lea     rcx, [rsp+160h+var_130]
0x180069163  call    ?FindPinWithMediaType@DSFilter@@QEBA?AVDSPin@@W4_PinDirection@@AEBVDSMediaType@@_N@Z; DSFilter::FindPinWithMediaType(_PinDirection,DSMediaType const &,bool)
0x180069168  nop
0x180069169  mov     rdx, [rax+8]; struct IUnknown *
0x18006916d  lea     rcx, [r15+8]; struct IUnknown **
0x180069171  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180069176  nop
0x180069177  lea     rax, ??_7?$Forward_Sequence@V?$CComQIPtr@UIPin@@$1?IID_IPin@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumMediaTypes@@$1?IID_IEnumMediaTypes@@3U_GUID@@B@2@VDSMediaType@@UIPin@@UIEnumMediaTypes@@PEAU_AMMediaType@@V?$allocator@VDSMediaType@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IPin,&_GUID const IID_IPin>,ATL::CComQIPtr<IEnumMediaTypes,&_GUID const IID_IEnumMediaTypes>,DSMediaType,IPin,IEnumMediaTypes,_AMMediaType *,std::allocator<DSMediaType>>::`vftable'
0x18006917e  mov     qword ptr [rsp+160h+var_F0.Data1], rax
0x180069183  lea     rcx, [rsp+160h+var_F0.Data4]
0x180069188  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18006918d  cmp     [r15+8], r12
0x180069191  jnz     short loc_1800691B2
0x180069193  lea     rcx, [rbp+60h+var_90]; this
0x180069197  call    ??1DSMediaType@@QEAA@XZ; DSMediaType::~DSMediaType(void)
0x18006919c  nop
0x18006919d  lea     rcx, [rsp+160h+var_118]; this
0x1800691a2  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x1800691a7  nop
0x1800691a8  mov     rcx, [rsp+160h+bstrString]
0x1800691ad  jmp     loc_18006905D
0x1800691b2  cmp     [r14], r12b
0x1800691b5  jz      short loc_1800691E0
0x1800691b7  mov     r8, r14; bool *
0x1800691ba  lea     rdx, [rsp+160h+var_130]; struct DSFilter *
0x1800691bf  mov     rcx, rsi; this
0x1800691c2  call    ?ConnectCCA@CMP2SinComp@@AEAAJAEAVDSFilter@@AEA_N@Z; CMP2SinComp::ConnectCCA(DSFilter &,bool &)
0x1800691c7  mov     edi, eax
0x1800691c9  test    eax, eax
0x1800691cb  jns     short loc_1800691E0
0x1800691cd  cmp     [r14], r12b
0x1800691d0  jz      short loc_1800691E0
0x1800691d2  lea     rcx, [rbp+60h+var_90]; this
0x1800691d6  call    ??1DSMediaType@@QEAA@XZ; DSMediaType::~DSMediaType(void)
0x1800691db  jmp     loc_1800690BA
0x1800691e0  lea     rdx, [rbp+60h+var_C0]
0x1800691e4  mov     rcx, r13
0x1800691e7  call    ?begin@?$Forward_Sequence@V?$CComQIPtr@UIMSVidGraphSegment@@$1?_GUID_238dec54_adeb_4005_a349_f772b9afebc4@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIEnumFilters@@$1?IID_IEnumFilters@@3U_GUID@@B@2@VDSFilter@@UIMSVidGraphSegment@@UIEnumFilters@@PEAUIBaseFilter@@V?$allocator@VDSFilter@@@std@@@@QEAA?AV?$enumerator_iterator@V?$CComQIPtr@UIEnumFilters@@$1?IID_IEnumFilters@@3U_GUID@@B@ATL@@VDSFilter@@UIEnumFilters@@PEAUIBaseFilter@@_J@@XZ; Forward_Sequence<ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>,ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IMSVidGraphSegment,IEnumFilters,IBaseFilter *,std::allocator<DSFilter>>::begin(void)
0x1800691ec  nop
0x1800691ed  lea     rdx, [rsp+160h+var_108]
0x1800691f2  mov     rcx, rax
0x1800691f5  call    ??D?$enumerator_iterator@V?$CComQIPtr@UIEnumFilters@@$1?IID_IEnumFilters@@3U_GUID@@B@ATL@@VDSFilter@@UIEnumFilters@@PEAUIBaseFilter@@_J@@QEBA?AVDSFilter@@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IEnumFilters,IBaseFilter *,__int64>::operator*(void)
0x1800691fa  nop
0x1800691fb  lea     rcx, [rbp+60h+var_C0]
0x1800691ff  call    ??1?$enumerator_iterator@V?$CComQIPtr@UIEnumFilters@@$1?IID_IEnumFilters@@3U_GUID@@B@ATL@@VDSFilter@@UIEnumFilters@@PEAUIBaseFilter@@_J@@QEAA@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IEnumFilters,IBaseFilter *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumFilters,&_GUID const IID_IEnumFilters>,DSFilter,IEnumFilters,IBaseFilter *,__int64>(void)
0x180069204  xorps   xmm0, xmm0
0x180069207  movdqu  [rbp+60h+var_E0], xmm0
0x18006920c  mov     [rbp+60h+var_D0], r12
0x180069210  mov     rax, [rsi+18h]
0x180069214  movsxd  rcx, dword ptr [rax+4]
0x180069218  add     rcx, 38h ; '8'
0x18006921c  add     rcx, rsi
0x18006921f  mov     [rsp+160h+var_138], 1
0x180069227  mov     dword ptr [rsp+160h+ppv], r12d
0x18006922c  lea     r9, [rbp+60h+var_E0]
0x180069230  lea     r8, [rsp+160h+var_108]
0x180069235  lea     rdx, [rsp+160h+var_130]
0x18006923a  call    ?Connect@DSGraph@@QEAAJAEAVDSFilter@@0AEAV?$vector@VDSFilter@@V?$allocator@VDSFilter@@@std@@@std@@KW4_PinDirection@@@Z; DSGraph::Connect(DSFilter &,DSFilter &,std::vector<DSFilter> &,ulong,_PinDirection)
0x18006923f  mov     edi, eax
0x180069241  lea     rcx, [rbp+60h+var_E0]
0x180069245  test    eax, eax
0x180069247  jns     short loc_18006928C
0x180069249  call    ?_Tidy@?$vector@VDSFilter@@V?$allocator@VDSFilter@@@std@@@std@@AEAAXXZ; std::vector<DSFilter>::_Tidy(void)
0x18006924e  nop
0x18006924f  lea     rbx, ??_7?$Forward_Sequence@V?$CComQIPtr@UIBaseFilter@@$1?IID_IBaseFilter@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumPins@@$1?IID_IEnumPins@@3U_GUID@@B@2@VDSPin@@UIBaseFilter@@UIEnumPins@@PEAUIPin@@V?$allocator@VDSPin@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable'
0x180069256  mov     [rsp+160h+var_108], rbx
0x18006925b  lea     rcx, [rsp+160h+var_100]
0x180069260  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180069265  nop
0x180069266  lea     rcx, [rbp+60h+var_90]; this
0x18006926a  call    ??1DSMediaType@@QEAA@XZ; DSMediaType::~DSMediaType(void)
0x18006926f  nop
0x180069270  lea     rcx, [rsp+160h+var_118]; this
0x180069275  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18006927a  nop
0x18006927b  mov     rcx, [rsp+160h+bstrString]; bstrString
0x180069280  call    cs:__imp_SysFreeString
0x180069286  nop
0x180069287  jmp     loc_18006903D
0x18006928c  call    ?_Tidy@?$vector@VDSFilter@@V?$allocator@VDSFilter@@@std@@@std@@AEAAXXZ; std::vector<DSFilter>::_Tidy(void)
0x180069291  nop
0x180069292  lea     rbx, ??_7?$Forward_Sequence@V?$CComQIPtr@UIBaseFilter@@$1?IID_IBaseFilter@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumPins@@$1?IID_IEnumPins@@3U_GUID@@B@2@VDSPin@@UIBaseFilter@@UIEnumPins@@PEAUIPin@@V?$allocator@VDSPin@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable'
0x180069299  mov     [rsp+160h+var_108], rbx
0x18006929e  lea     rcx, [rsp+160h+var_100]
0x1800692a3  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800692a8  nop
0x1800692a9  lea     rcx, [rbp+60h+var_90]; this
0x1800692ad  call    ??1DSMediaType@@QEAA@XZ; DSMediaType::~DSMediaType(void)
0x1800692b2  nop
0x1800692b3  lea     rcx, [rsp+160h+var_118]; this
0x1800692b8  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x1800692bd  nop
0x1800692be  mov     rcx, [rsp+160h+bstrString]; bstrString
0x1800692c3  call    cs:__imp_SysFreeString
0x1800692c9  nop
0x1800692ca  mov     [rsp+160h+var_130], rbx
0x1800692cf  lea     rcx, [rsp+160h+var_128]
0x1800692d4  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800692d9  mov     edi, r12d
0x1800692dc  lea     rcx, [rsp+160h+var_110]
0x1800692e1  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800692e6  mov     eax, edi
0x1800692e8  mov     rcx, [rbp+60h+var_48]
0x1800692ec  xor     rcx, rsp; StackCookie
0x1800692ef  call    __security_check_cookie
0x1800692f4  add     rsp, 128h
0x1800692fb  pop     r15
0x1800692fd  pop     r14
0x1800692ff  pop     r13
0x180069301  pop     r12
0x180069303  pop     rdi
0x180069304  pop     rsi
0x180069305  pop     rbx
0x180069306  pop     rbp
0x180069307  retn
```
