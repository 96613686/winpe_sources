# CRedbookTracks::OpenDisc(CMyUpdateList *)

- ea: `0x1800165b4`
- end: `0x1800168ce`
- name: `?OpenDisc@CRedbookTracks@@IEAAJPEAVCMyUpdateList@@@Z`
- size: `794`
- prototype: `__int64 __fastcall(CRedbookTracks *__hidden this, struct CMyUpdateList *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800168f8`

## callees

- `0x18000115c`
- `0x180002ac4`
- `0x180002f5c`
- `0x180007bd4`
- `0x180007c60`
- `0x18000b4b0`
- `0x18000c330`
- `0x1800127ec`
- `0x1800165b4`
- `0x180019010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800165ff`
- `ole32!CoCreateInstance` at `0x1800165ff`
- `OLEAUT32!__imp_SysAllocString` at `0x180016616`
- `OLEAUT32!__imp_SysAllocString` at `0x180016616`
- `OLEAUT32!__imp_SysFreeString` at `0x18001663a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800166b9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001663a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800166b9`

## pseudocode

```c
__int64 __fastcall CRedbookTracks::OpenDisc(CRedbookTracks *this, struct IUnknownVtbl *a2)
{
  char v2; // bp
  LPVOID *ppv; // rdi
  HRESULT Instance; // ebx
  OLECHAR *v8; // rbx
  int v9; // r14d
  __int64 *LastComError; // rax
  struct IUnknown **v11; // r14
  struct IUnknown *v12; // rax
  struct IUnknown *v13; // r15
  ATL::CAtlModule *v14; // rcx
  int v15; // eax
  int v16; // ecx
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  unsigned int *v19; // r9
  struct IUnknown *v20; // rax
  BSTR bstrString; // [rsp+60h] [rbp+8h] BYREF

  v2 = 0;
  ppv = (LPVOID *)((char *)this + 24);
  LODWORD(bstrString) = 0;
  if ( *((_QWORD *)this + 3) )
    return 0;
  Instance = CoCreateInstance(
               &GUID_27354129_7f64_5b0f_8f00_5d77afbe261e,
               0,
               0x17u,
               &GUID_27354154_8f64_5b0f_8f00_5d77afbe261e,
               ppv);
  if ( Instance >= 0 )
  {
    v8 = SysAllocString(L"IMAPIv1 Shim");
    v9 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)*ppv + 232LL))(*ppv, v8);
    SysFreeString(v8);
    if ( v9 < 0 )
    {
      if ( *ppv )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*ppv + 16LL))(*ppv);
        *ppv = 0;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        LastComError = (__int64 *)GetLastComError(&bstrString);
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          13,
          (unsigned int)&WPP_748693ba6e733a71ff8f81489f91c19c_Traceguids,
          v9,
          *LastComError);
        v2 = 1;
      }
      if ( (v2 & 1) != 0 )
        SysFreeString(bstrString);
      return (unsigned int)TranslateIMAPI2Error((unsigned int)v9);
    }
    v11 = (struct IUnknown **)((char *)this + 48);
    if ( this == (CRedbookTracks *)-48LL )
    {
      Instance = -2147467261;
      goto LABEL_27;
    }
    *v11 = 0;
    v12 = (struct IUnknown *)operator new(0x80u);
    v13 = v12;
    if ( v12 )
    {
      v14 = ATL::_pAtlModule;
      LODWORD(v12[7].lpVtbl) = 0;
      *(_OWORD *)&v12[8].lpVtbl = 0;
      *(_OWORD *)&v12[10].lpVtbl = 0;
      v12[12].lpVtbl = 0;
      LOBYTE(v12[13].lpVtbl) = 0;
      HIDWORD(v12[6].lpVtbl) = -16843010;
      *(GUID *)&v12[2].lpVtbl = LIBID_IMAPI2;
      LODWORD(v12[6].lpVtbl) = 1;
      *(GUID *)&v12[4].lpVtbl = IID_DDiscFormat2TrackAtOnceEvents;
      v12->lpVtbl = (struct IUnknownVtbl *)&ATL::CComObject<CRedbookWriterEvent>::`vftable'{for `ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
      v12[1].lpVtbl = (struct IUnknownVtbl *)&ATL::CComObject<CRedbookWriterEvent>::`vftable'{for `ATL::IDispEventImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
      (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)v14 + 8LL))(v14);
      v15 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&v13[8]);
      if ( v15 >= 0 )
        LOBYTE(v13[13].lpVtbl) = 1;
      v16 = 0;
      if ( v15 < 0 )
        v16 = v15;
      Instance = 0;
      if ( v16 < 0 )
        Instance = v16;
      if ( !Instance )
      {
LABEL_26:
        *v11 = v13;
        if ( Instance >= 0 )
        {
          ((void (__fastcall *)(struct IUnknown *))v13->lpVtbl->AddRef)(v13);
          v19 = (unsigned int *)&(*v11)[6].lpVtbl + 1;
          if ( *v19 != -16843010 )
            ATL::AtlThrowImpl(-2147467259);
          Instance = ATL::AtlAdvise((struct IUnknown *)*ppv, *v11 + 1, &IID_DDiscFormat2TrackAtOnceEvents, v19);
          if ( Instance >= 0 )
          {
            v20 = *v11;
            v20[14].lpVtbl = a2;
            v20[15].lpVtbl = 0;
            return (unsigned int)Instance;
          }
          if ( *v11 )
          {
            ((void (__fastcall *)(struct IUnknown *))(*v11)->lpVtbl->Release)(*v11);
            *v11 = 0;
          }
          if ( *ppv )
          {
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*ppv + 16LL))(*ppv);
            *ppv = 0;
          }
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            return (unsigned int)Instance;
          v18 = 15;
          goto LABEL_32;
        }
LABEL_27:
        if ( *ppv )
        {
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*ppv + 16LL))(*ppv);
          *ppv = 0;
        }
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          return (unsigned int)Instance;
        v18 = 14;
LABEL_32:
        WPP_SF_d(v17[7], v18, &WPP_748693ba6e733a71ff8f81489f91c19c_Traceguids, (unsigned int)Instance);
        return (unsigned int)Instance;
      }
      ((void (__fastcall *)(struct IUnknown *, __int64))v13->lpVtbl[2].Release)(v13, 1);
    }
    else
    {
      Instance = -2147024882;
    }
    v13 = 0;
    goto LABEL_26;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800165b4  mov     [rsp+arg_8], rbx
0x1800165b9  mov     [rsp+arg_10], rbp
0x1800165be  push    rsi
0x1800165bf  push    rdi
0x1800165c0  push    r12
0x1800165c2  push    r14
0x1800165c4  push    r15
0x1800165c6  sub     rsp, 30h
0x1800165ca  xor     ebp, ebp
0x1800165cc  lea     rdi, [rcx+18h]
0x1800165d0  mov     dword ptr [rsp+58h+bstrString], ebp
0x1800165d4  mov     r12, rdx
0x1800165d7  mov     rsi, rcx
0x1800165da  cmp     [rdi], rbp
0x1800165dd  jz      short loc_1800165E6
0x1800165df  xor     eax, eax
0x1800165e1  jmp     loc_1800168AC
0x1800165e6  xor     edx, edx; pUnkOuter
0x1800165e8  mov     [rsp+58h+ppv], rdi; ppv
0x1800165ed  lea     r9, _GUID_27354154_8f64_5b0f_8f00_5d77afbe261e; riid
0x1800165f4  lea     rcx, _GUID_27354129_7f64_5b0f_8f00_5d77afbe261e; rclsid
0x1800165fb  lea     r8d, [rdx+17h]; dwClsContext
0x1800165ff  call    cs:__imp_CoCreateInstance
0x180016605  mov     ebx, eax
0x180016607  test    eax, eax
0x180016609  js      loc_1800168AA
0x18001660f  lea     rcx, psz; "IMAPIv1 Shim"
0x180016616  call    cs:__imp_SysAllocString
0x18001661c  mov     rcx, [rdi]
0x18001661f  mov     rbx, rax
0x180016622  mov     rdx, [rcx]
0x180016625  mov     rax, [rdx+0E8h]
0x18001662c  mov     rdx, rbx
0x18001662f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016634  mov     rcx, rbx; bstrString
0x180016637  mov     r14d, eax
0x18001663a  call    cs:__imp_SysFreeString
0x180016640  test    r14d, r14d
0x180016643  jns     loc_1800166CE
0x180016649  mov     rcx, [rdi]
0x18001664c  test    rcx, rcx
0x18001664f  jz      short loc_180016660
0x180016651  mov     rdx, [rcx]
0x180016654  mov     rax, [rdx+10h]
0x180016658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001665d  mov     [rdi], rbp
0x180016660  mov     rcx, cs:WPP_GLOBAL_Control
0x180016667  lea     rax, WPP_GLOBAL_Control
0x18001666e  mov     esi, 1
0x180016673  cmp     rcx, rax
0x180016676  jz      short loc_1800166AF
0x180016678  test    [rcx+44h], sil
0x18001667c  jz      short loc_1800166AF
0x18001667e  lea     rcx, [rsp+58h+bstrString]
0x180016683  call    ?GetLastComError@@YA?AVCComBSTR@ATL@@XZ; GetLastComError(void)
0x180016688  lea     edx, [rsi+0Ch]
0x18001668b  mov     r9d, r14d
0x18001668e  lea     r8, WPP_748693ba6e733a71ff8f81489f91c19c_Traceguids
0x180016695  mov     rcx, [rax]
0x180016698  mov     [rsp+58h+ppv], rcx
0x18001669d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800166a4  mov     rcx, [rcx+38h]
0x1800166a8  call    WPP_SF_DS
0x1800166ad  mov     ebp, esi
0x1800166af  test    sil, bpl
0x1800166b2  jz      short loc_1800166BF
0x1800166b4  mov     rcx, [rsp+58h+bstrString]; bstrString
0x1800166b9  call    cs:__imp_SysFreeString
0x1800166bf  mov     ecx, r14d
0x1800166c2  call    TranslateIMAPI2Error
0x1800166c7  mov     ebx, eax
0x1800166c9  jmp     loc_1800168AA
0x1800166ce  lea     r14, [rsi+30h]
0x1800166d2  mov     esi, 1
0x1800166d7  test    r14, r14
0x1800166da  jnz     short loc_1800166E6
0x1800166dc  mov     ebx, 80004003h
0x1800166e1  jmp     loc_1800167B1
0x1800166e6  mov     ecx, 80h; Size
0x1800166eb  mov     [r14], rbp
0x1800166ee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800166f3  mov     r15, rax
0x1800166f6  mov     ebp, 0FEFEFEFEh
0x1800166fb  test    rax, rax
0x1800166fe  jz      loc_1800167A2
0x180016704  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001670b  xorps   xmm0, xmm0
0x18001670e  mov     dword ptr [rax+38h], 0
0x180016715  xor     eax, eax
0x180016717  movups  xmmword ptr [r15+40h], xmm0
0x18001671c  movups  xmmword ptr [r15+50h], xmm0
0x180016721  mov     [r15+60h], rax
0x180016725  mov     [r15+68h], al
0x180016729  lea     rax, ??_7?$CComObject@VCRedbookWriterEvent@@@ATL@@6B?$IDispatchImpl@UIDispatch@@$1?IID_DDiscFormat2TrackAtOnceEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CRedbookWriterEvent>::`vftable'{for `ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x180016730  mov     [r15+34h], ebp
0x180016734  movups  xmm0, xmmword ptr cs:LIBID_IMAPI2.Data1
0x18001673b  movdqu  xmmword ptr [r15+10h], xmm0
0x180016741  movups  xmm1, xmmword ptr cs:IID_DDiscFormat2TrackAtOnceEvents.Data1
0x180016748  mov     [r15+30h], esi
0x18001674c  movdqu  xmmword ptr [r15+20h], xmm1
0x180016752  mov     [r15], rax
0x180016755  lea     rax, ??_7?$CComObject@VCRedbookWriterEvent@@@ATL@@6B?$IDispEventImpl@$00VCRedbookWriterEvent@@$1?IID_DDiscFormat2TrackAtOnceEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CRedbookWriterEvent>::`vftable'{for `ATL::IDispEventImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x18001675c  mov     [r15+8], rax
0x180016760  mov     rax, [rcx]
0x180016763  mov     rax, [rax+8]
0x180016767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001676c  lea     rcx, [r15+40h]; this
0x180016770  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180016775  test    eax, eax
0x180016777  js      short loc_18001677D
0x180016779  mov     [r15+68h], sil
0x18001677d  xor     ecx, ecx
0x18001677f  test    eax, eax
0x180016781  cmovs   ecx, eax
0x180016784  xor     ebx, ebx
0x180016786  test    ecx, ecx
0x180016788  cmovs   ebx, ecx
0x18001678b  test    ebx, ebx
0x18001678d  jz      short loc_1800167AA
0x18001678f  mov     rax, [r15]
0x180016792  mov     edx, esi
0x180016794  mov     rcx, r15
0x180016797  mov     rax, [rax+40h]
0x18001679b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167a0  jmp     short loc_1800167A7
0x1800167a2  mov     ebx, 8007000Eh
0x1800167a7  xor     r15d, r15d
0x1800167aa  mov     [r14], r15
0x1800167ad  test    ebx, ebx
0x1800167af  jns     short loc_18001680A
0x1800167b1  mov     rcx, [rdi]
0x1800167b4  test    rcx, rcx
0x1800167b7  jz      short loc_1800167CC
0x1800167b9  mov     rax, [rcx]
0x1800167bc  mov     rax, [rax+10h]
0x1800167c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167c5  mov     qword ptr [rdi], 0
0x1800167cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167d3  lea     rax, WPP_GLOBAL_Control
0x1800167da  cmp     rcx, rax
0x1800167dd  jz      loc_1800168AA
0x1800167e3  test    [rcx+44h], sil
0x1800167e7  jz      loc_1800168AA
0x1800167ed  mov     edx, 0Eh
0x1800167f2  mov     rcx, [rcx+38h]
0x1800167f6  lea     r8, WPP_748693ba6e733a71ff8f81489f91c19c_Traceguids
0x1800167fd  mov     r9d, ebx
0x180016800  call    WPP_SF_d
0x180016805  jmp     loc_1800168AA
0x18001680a  mov     rax, [r15]
0x18001680d  mov     rcx, r15
0x180016810  mov     rax, [rax+8]
0x180016814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016819  mov     rdx, [r14]
0x18001681c  add     rdx, 8; struct IUnknown *
0x180016820  lea     r9, [rdx+2Ch]; unsigned int *
0x180016824  cmp     [r9], ebp
0x180016827  jnz     loc_1800168C3
0x18001682d  mov     rcx, [rdi]; struct IUnknown *
0x180016830  lea     r8, IID_DDiscFormat2TrackAtOnceEvents; struct _GUID *
0x180016837  call    ?AtlAdvise@ATL@@YAJPEAUIUnknown@@0AEBU_GUID@@PEAK@Z; ATL::AtlAdvise(IUnknown *,IUnknown *,_GUID const &,ulong *)
0x18001683c  mov     ebx, eax
0x18001683e  test    eax, eax
0x180016840  jns     short loc_18001689B
0x180016842  mov     rcx, [r14]
0x180016845  test    rcx, rcx
0x180016848  jz      short loc_18001685D
0x18001684a  mov     rax, [rcx]
0x18001684d  mov     rax, [rax+10h]
0x180016851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016856  mov     qword ptr [r14], 0
0x18001685d  mov     rcx, [rdi]
0x180016860  test    rcx, rcx
0x180016863  jz      short loc_180016878
0x180016865  mov     rax, [rcx]
0x180016868  mov     rax, [rax+10h]
0x18001686c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016871  mov     qword ptr [rdi], 0
0x180016878  mov     rcx, cs:WPP_GLOBAL_Control
0x18001687f  lea     rax, WPP_GLOBAL_Control
0x180016886  cmp     rcx, rax
0x180016889  jz      short loc_1800168AA
0x18001688b  test    [rcx+44h], sil
0x18001688f  jz      short loc_1800168AA
0x180016891  mov     edx, 0Fh
0x180016896  jmp     loc_1800167F2
0x18001689b  mov     rax, [r14]
0x18001689e  mov     [rax+70h], r12
0x1800168a2  mov     qword ptr [rax+78h], 0
0x1800168aa  mov     eax, ebx
0x1800168ac  mov     rbx, [rsp+58h+arg_8]
0x1800168b1  mov     rbp, [rsp+58h+arg_10]
0x1800168b6  add     rsp, 30h
0x1800168ba  pop     r15
0x1800168bc  pop     r14
0x1800168be  pop     r12
0x1800168c0  pop     rdi
0x1800168c1  pop     rsi
0x1800168c2  retn
0x1800168c3  mov     ecx, 80004005h; int
0x1800168c8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
