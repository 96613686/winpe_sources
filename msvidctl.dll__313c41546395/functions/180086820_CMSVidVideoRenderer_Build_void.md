# CMSVidVideoRenderer::Build(void)

- ea: `0x180086820`
- end: `0x180086d94`
- name: `?Build@CMSVidVideoRenderer@@UEAAJXZ`
- size: `1396`
- prototype: `__int64 __fastcall(CMSVidVideoRenderer *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006b38`
- `0x18000dc24`
- `0x18000df18`
- `0x18000e1b8`
- `0x180010e9c`
- `0x180011c40`
- `0x1800149b0`
- `0x180057fe4`
- `0x18007a20c`
- `0x180083fd0`
- `0x180086820`
- `0x18008812c`
- `0x1800d76bc`
- `0x1800f8010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18008687b`
- `ole32!CoCreateInstance` at `0x180086909`
- `ole32!CoCreateInstance` at `0x18008687b`
- `ole32!CoCreateInstance` at `0x180086909`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CMSVidVideoRenderer::Build(CMSVidVideoRenderer *this)
{
  __int64 v2; // rax
  __int64 v3; // rcx
  struct IUnknown **v4; // rdi
  __int64 result; // rax
  struct IUnknown **v6; // rsi
  struct IUnknown *v7; // rcx
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  int v10; // esi
  unsigned int v11; // esi
  unsigned int v12; // ebx
  int v13; // edi
  unsigned int v14; // [rsp+30h] [rbp-78h] BYREF
  ComException *v15; // [rsp+38h] [rbp-70h] BYREF
  void **v16; // [rsp+40h] [rbp-68h] BYREF
  __int64 v17; // [rsp+48h] [rbp-60h] BYREF
  _QWORD v18[3]; // [rsp+50h] [rbp-58h] BYREF
  std::bad_alloc *v19; // [rsp+68h] [rbp-40h] BYREF
  std::exception *v20; // [rsp+70h] [rbp-38h] BYREF
  __int64 v21; // [rsp+B0h] [rbp+8h] BYREF
  unsigned int v22; // [rsp+B8h] [rbp+10h] BYREF
  struct IUnknown *v23; // [rsp+C0h] [rbp+18h] BYREF
  LPCWSTR lpSubKey; // [rsp+C8h] [rbp+20h] BYREF

  v2 = *((_QWORD *)this - 1);
  v3 = *(int *)(v2 + 4);
  if ( !*((_BYTE *)this + v3) || !*(_QWORD *)((char *)this + v3 + 32) )
    return ATL::CComCoClass<CMSVidVideoRenderer,&__s_GUID const _GUID_37b03543_a4c8_11d2_b634_00c04f79498e>::Error(
             0xC0040502,
             &GUID_dd47de3f_9874_4f7b_8b22_7cb2688461e7,
             -2147221008,
             hInstance);
  try
  {
    v4 = (struct IUnknown **)((char *)this + 192);
    if ( !*((_QWORD *)this + 24) )
    {
      if ( CoCreateInstance(
             &CLSID_VideoMixingRenderer,
             0,
             1u,
             &GUID_9e5530c5_7034_48b4_bb46_0b8a6efc8e36,
             (LPVOID *)this + 24) < 0 )
        return ATL::CComCoClass<CMSVidVideoRenderer,&__s_GUID const _GUID_37b03543_a4c8_11d2_b634_00c04f79498e>::Error(
                 0xC0040506,
                 &GUID_0eb1088c_4dcd_46f0_878f_39dae86a51b7,
                 -2147418113,
                 hInstance);
      if ( ((int (__fastcall *)(struct IUnknown *, _QWORD))(*v4)->lpVtbl[2].Release)(*v4, *((unsigned int *)this + 56)) < 0 )
        return ATL::CComCoClass<CMSVidVideoRenderer,&__s_GUID const _GUID_37b03543_a4c8_11d2_b634_00c04f79498e>::Error(
                 0xC004050D,
                 &GUID_0eb1088c_4dcd_46f0_878f_39dae86a51b7,
                 -2147418113,
                 hInstance);
      v6 = (struct IUnknown **)((char *)this + 208);
      if ( !*((_QWORD *)this + 26)
        && CoCreateInstance(
             &CLSID_AllocPresenter,
             0,
             1u,
             &GUID_31ce832e_4484_458b_8cca_f4d7e3db0b52,
             (LPVOID *)this + 26) < 0 )
      {
        return ATL::CComCoClass<CMSVidVideoRenderer,&__s_GUID const _GUID_37b03543_a4c8_11d2_b634_00c04f79498e>::Error(
                 0xC0040506,
                 &GUID_0eb1088c_4dcd_46f0_878f_39dae86a51b7,
                 -2147418113,
                 hInstance);
      }
      v23 = 0;
      ATL::AtlComQIPtrAssign(&v23, *v4, &GUID_aada05a8_5a4e_4729_af0b_cea27aed51e2);
      v7 = v23;
      if ( !v23 )
        goto LABEL_16;
      if ( *((_QWORD *)this + 33) == -1 )
      {
        ATL::CComQIPtr<IMSVidAudioRendererDevices,&__s_GUID const _GUID_c5702cd4_9b79_11d3_b654_00c04f79498e>::CComQIPtr<IMSVidAudioRendererDevices,&__s_GUID const _GUID_c5702cd4_9b79_11d3_b654_00c04f79498e>(
          &v21,
          *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this - 1) + 4LL) + 16));
        *((_QWORD *)this + 33) = v21;
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v21);
        v7 = v23;
      }
      if ( ((int (__fastcall *)(struct IUnknown *, _QWORD, struct IUnknown *))v7->lpVtbl[1].QueryInterface)(
             v7,
             *((_QWORD *)this + 33),
             *v6) < 0
        || ((int (__fastcall *)(struct IUnknown *, struct IUnknown *))(*v6)->lpVtbl[2].QueryInterface)(*v6, v23) < 0 )
      {
LABEL_16:
        v8 = ATL::CComCoClass<CMSVidVideoRenderer,&__s_GUID const _GUID_37b03543_a4c8_11d2_b634_00c04f79498e>::Error(
               0xC0040506,
               &GUID_0eb1088c_4dcd_46f0_878f_39dae86a51b7,
               -2147418113,
               hInstance);
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v23);
        return v8;
      }
      ATL::AtlComQIPtrAssign((struct IUnknown **)this + 25, *v6, &GUID_0eb1088c_4dcd_46f0_878f_39dae86a51b7);
      if ( *((_BYTE *)this + 84) )
      {
        if ( ((int (__fastcall *)(struct IUnknown *, __int64))(*v4)->lpVtbl[1].AddRef)(*v4, 4) < 0 )
        {
          v9 = ATL::CComCoClass<CMSVidVideoRenderer,&__s_GUID const _GUID_37b03543_a4c8_11d2_b634_00c04f79498e>::Error(
                 0xC004050D,
                 &GUID_0eb1088c_4dcd_46f0_878f_39dae86a51b7,
                 -2147418113,
                 hInstance);
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v23);
          return v9;
        }
        LODWORD(v21) = 0;
        ATL::AtlComQIPtrAssign((struct IUnknown **)this + 27, *v4, &GUID_1c1a17b0_bed0_415d_974b_dc6696131599);
        if ( !*((_QWORD *)this + 27) )
        {
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v23);
          return 2147549183LL;
        }
        v10 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 27) + 96LL))(
                *((_QWORD *)this + 27),
                &v21);
        if ( v10 < 0 )
        {
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v23);
          return (unsigned int)v10;
        }
        v11 = 4100;
        memset(v18, 0, sizeof(v18));
        v22 = 0;
        WTL::CString::CString((WTL::CString *)&lpSubKey, L"SOFTWARE\\Microsoft\\DirectShow\\Debug\\MSVidCtl");
        if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v18, HKEY_LOCAL_MACHINE, lpSubKey, 0x20019u, 0)
          && !ATL::CRegKey::QueryValue((ATL::CRegKey *)v18, &v22, L"MixerPrefs") )
        {
          v11 = v22;
        }
        LODWORD(v21) = ((*((_DWORD *)this + 22) != 0) + 1) | v11 & 0xFFFFFFF0 | v21 & 0xFFFF00F0;
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 27) + 88LL))(*((_QWORD *)this + 27));
        WTL::CString::~CString((WTL::CString *)&lpSubKey);
        ATL::CRegKey::Close((ATL::CRegKey *)v18);
      }
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v23);
    }
    DSFilter::DSFilter((DSFilter *)&v16, *v4);
    if ( !v17 )
    {
      v12 = ATL::CComCoClass<CMSVidVideoRenderer,&__s_GUID const _GUID_37b03543_a4c8_11d2_b634_00c04f79498e>::Error(
              0xC0040506,
              &GUID_56a86895_0ad4_11ce_b03a_0020af0ba770,
              -2147418113,
              hInstance);
      v16 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v17);
      return v12;
    }
    if ( *((_DWORD *)this + 7) == -1 )
    {
      WTL::CString::CString((WTL::CString *)&v21, L"Video Mixing Renderer");
      v13 = DSGraph::AddFilter(
              (CMSVidVideoRenderer *)((char *)this + *(int *)(*((_QWORD *)this - 1) + 4LL) + 24),
              (struct DSFilter *)&v16,
              (struct WTL::CString *)&v21);
      if ( v13 < 0 )
      {
        WTL::CString::~CString((WTL::CString *)&v21);
        v16 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v17);
        return (unsigned int)v13;
      }
      std::vector<DSFilter>::push_back((char *)this + *(int *)(*((_QWORD *)this - 1) + 4LL) + 40, &v16);
      WTL::CString::~CString((WTL::CString *)&v21);
    }
    *((_DWORD *)this + 7) = 0;
    (*(void (__fastcall **)(CMSVidVideoRenderer *))(*(_QWORD *)this + 336LL))(this);
    v16 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v17);
    result = 0;
  }
  catch ( long v14 )
  {
    return v14;
  }
  catch ( ComException *v15 )
  {
    return *(unsigned int *)v15;
  }
  catch ( std::bad_alloc *v19 )
  {
    return 2147942414LL;
  }
  catch ( std::exception *v20 )
  {
    return 2147549183LL;
  }
  return result;
}

```

## disassembly

```asm
0x180086820  push    rbx
0x180086822  push    rsi
0x180086823  push    rdi
0x180086824  push    r14
0x180086826  push    r15
0x180086828  sub     rsp, 80h
0x18008682f  mov     rbx, rcx
0x180086832  mov     rax, [rcx-8]
0x180086836  movsxd  rcx, dword ptr [rax+4]
0x18008683a  xor     r15d, r15d
0x18008683d  cmp     [rcx+rbx], r15b
0x180086841  jz      loc_180086D65
0x180086847  cmp     [rcx+rbx+20h], r15
0x18008684c  jz      loc_180086D65
0x180086852  lea     rdi, [rbx+0C0h]
0x180086859  cmp     [rdi], r15
0x18008685c  jnz     loc_180086C2D
0x180086862  mov     [rsp+0A8h+ppv], rdi; ppv
0x180086867  lea     r9, _GUID_9e5530c5_7034_48b4_bb46_0b8a6efc8e36; riid
0x18008686e  xor     edx, edx; pUnkOuter
0x180086870  lea     r8d, [r15+1]; dwClsContext
0x180086874  lea     rcx, CLSID_VideoMixingRenderer; rclsid
0x18008687b  call    cs:__imp_CoCreateInstance
0x180086881  test    eax, eax
0x180086883  jns     short loc_1800868A8
0x180086885  mov     r9, cs:hInstance; HINSTANCE
0x18008688c  mov     r8d, 8000FFFFh; int
0x180086892  lea     rdx, _GUID_0eb1088c_4dcd_46f0_878f_39dae86a51b7; struct _GUID *
0x180086899  mov     ecx, 0C0040506h; dwMessageId
0x18008689e  call    ?Error@?$CComCoClass@VCMSVidVideoRenderer@@$1?_GUID_37b03543_a4c8_11d2_b634_00c04f79498e@@3U__s_GUID@@B@ATL@@SAJIAEBU_GUID@@JPEAUHINSTANCE__@@@Z; ATL::CComCoClass<CMSVidVideoRenderer,&__s_GUID const _GUID_37b03543_a4c8_11d2_b634_00c04f79498e>::Error(uint,_GUID const &,long,HINSTANCE__ *)
0x1800868a3  jmp     loc_180086D84
0x1800868a8  mov     rcx, [rdi]
0x1800868ab  mov     rax, [rcx]
0x1800868ae  mov     edx, [rbx+0E0h]
0x1800868b4  mov     rax, [rax+40h]
0x1800868b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800868bd  test    eax, eax
0x1800868bf  jns     short loc_1800868E4
0x1800868c1  mov     r9, cs:hInstance; HINSTANCE
0x1800868c8  mov     r8d, 8000FFFFh; int
0x1800868ce  lea     rdx, _GUID_0eb1088c_4dcd_46f0_878f_39dae86a51b7; struct _GUID *
0x1800868d5  mov     ecx, 0C004050Dh; dwMessageId
0x1800868da  call    ?Error@?$CComCoClass@VCMSVidVideoRenderer@@$1?_GUID_37b03543_a4c8_11d2_b634_00c04f79498e@@3U__s_GUID@@B@ATL@@SAJIAEBU_GUID@@JPEAUHINSTANCE__@@@Z; ATL::CComCoClass<CMSVidVideoRenderer,&__s_GUID const _GUID_37b03543_a4c8_11d2_b634_00c04f79498e>::Error(uint,_GUID const &,long,HINSTANCE__ *)
0x1800868df  jmp     loc_180086D84
0x1800868e4  lea     rsi, [rbx+0D0h]
0x1800868eb  cmp     [rsi], r15
0x1800868ee  jnz     short loc_180086936
0x1800868f0  mov     [rsp+0A8h+ppv], rsi; ppv
0x1800868f5  lea     r9, _GUID_31ce832e_4484_458b_8cca_f4d7e3db0b52; riid
0x1800868fc  xor     edx, edx; pUnkOuter
0x1800868fe  lea     r8d, [rdx+1]; dwClsContext
0x180086902  lea     rcx, CLSID_AllocPresenter; rclsid
0x180086909  call    cs:__imp_CoCreateInstance
0x18008690f  test    eax, eax
0x180086911  jns     short loc_180086936
0x180086913  mov     r9, cs:hInstance; HINSTANCE
0x18008691a  mov     r8d, 8000FFFFh; int
0x180086920  lea     rdx, _GUID_0eb1088c_4dcd_46f0_878f_39dae86a51b7; struct _GUID *
0x180086927  mov     ecx, 0C0040506h; dwMessageId
0x18008692c  call    ?Error@?$CComCoClass@VCMSVidVideoRenderer@@$1?_GUID_37b03543_a4c8_11d2_b634_00c04f79498e@@3U__s_GUID@@B@ATL@@SAJIAEBU_GUID@@JPEAUHINSTANCE__@@@Z; ATL::CComCoClass<CMSVidVideoRenderer,&__s_GUID const _GUID_37b03543_a4c8_11d2_b634_00c04f79498e>::Error(uint,_GUID const &,long,HINSTANCE__ *)
0x180086931  jmp     loc_180086D84
0x180086936  mov     [rsp+0A8h+arg_10], r15
0x18008693e  lea     r8, _GUID_aada05a8_5a4e_4729_af0b_cea27aed51e2; struct _GUID *
0x180086945  mov     rdx, [rdi]; struct IUnknown *
0x180086948  lea     rcx, [rsp+0A8h+arg_10]; struct IUnknown **
0x180086950  call    ?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z; ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)
0x180086955  mov     rcx, [rsp+0A8h+arg_10]
0x18008695d  test    rcx, rcx
0x180086960  jnz     short loc_180086996
0x180086962  mov     r9, cs:hInstance; HINSTANCE
0x180086969  mov     r8d, 8000FFFFh; int
0x18008696f  lea     rdx, _GUID_0eb1088c_4dcd_46f0_878f_39dae86a51b7; struct _GUID *
0x180086976  mov     ecx, 0C0040506h; dwMessageId
0x18008697b  call    ?Error@?$CComCoClass@VCMSVidVideoRenderer@@$1?_GUID_37b03543_a4c8_11d2_b634_00c04f79498e@@3U__s_GUID@@B@ATL@@SAJIAEBU_GUID@@JPEAUHINSTANCE__@@@Z; ATL::CComCoClass<CMSVidVideoRenderer,&__s_GUID const _GUID_37b03543_a4c8_11d2_b634_00c04f79498e>::Error(uint,_GUID const &,long,HINSTANCE__ *)
0x180086980  mov     ebx, eax
0x180086982  lea     rcx, [rsp+0A8h+arg_10]
0x18008698a  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18008698f  mov     eax, ebx
0x180086991  jmp     loc_180086D84
0x180086996  cmp     qword ptr [rbx+108h], 0FFFFFFFFFFFFFFFFh
0x18008699e  jnz     short loc_1800869DE
0x1800869a0  mov     rax, [rbx-8]
0x1800869a4  movsxd  rdx, dword ptr [rax+4]
0x1800869a8  mov     rdx, [rdx+rbx+10h]
0x1800869ad  lea     rcx, [rsp+0A8h+arg_0]
0x1800869b5  call    ??0?$CComQIPtr@UIMSVidAudioRendererDevices@@$1?_GUID_c5702cd4_9b79_11d3_b654_00c04f79498e@@3U__s_GUID@@B@ATL@@QEAA@PEAUIMSVidAudioRendererDevices@@@Z; ATL::CComQIPtr<IMSVidAudioRendererDevices,&__s_GUID const _GUID_c5702cd4_9b79_11d3_b654_00c04f79498e>::CComQIPtr<IMSVidAudioRendererDevices,&__s_GUID const _GUID_c5702cd4_9b79_11d3_b654_00c04f79498e>(IMSVidAudioRendererDevices *)
0x1800869ba  mov     rax, [rsp+0A8h+arg_0]
0x1800869c2  mov     [rbx+108h], rax
0x1800869c9  lea     rcx, [rsp+0A8h+arg_0]
0x1800869d1  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800869d6  mov     rcx, [rsp+0A8h+arg_10]
0x1800869de  mov     rax, [rcx]
0x1800869e1  mov     r8, [rsi]
0x1800869e4  mov     rdx, [rbx+108h]
0x1800869eb  mov     rax, [rax+18h]
0x1800869ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800869f4  test    eax, eax
0x1800869f6  jns     short loc_180086A2C
0x1800869f8  mov     r9, cs:hInstance; HINSTANCE
0x1800869ff  mov     r8d, 8000FFFFh; int
0x180086a05  lea     rdx, _GUID_0eb1088c_4dcd_46f0_878f_39dae86a51b7; struct _GUID *
0x180086a0c  mov     ecx, 0C0040506h; dwMessageId
0x180086a11  call    ?Error@?$CComCoClass@VCMSVidVideoRenderer@@$1?_GUID_37b03543_a4c8_11d2_b634_00c04f79498e@@3U__s_GUID@@B@ATL@@SAJIAEBU_GUID@@JPEAUHINSTANCE__@@@Z; ATL::CComCoClass<CMSVidVideoRenderer,&__s_GUID const _GUID_37b03543_a4c8_11d2_b634_00c04f79498e>::Error(uint,_GUID const &,long,HINSTANCE__ *)
0x180086a16  mov     ebx, eax
0x180086a18  lea     rcx, [rsp+0A8h+arg_10]
0x180086a20  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180086a25  mov     eax, ebx
0x180086a27  jmp     loc_180086D84
0x180086a2c  mov     rcx, [rsi]
0x180086a2f  mov     rax, [rcx]
0x180086a32  mov     rdx, [rsp+0A8h+arg_10]
0x180086a3a  mov     rax, [rax+30h]
0x180086a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086a43  test    eax, eax
0x180086a45  jns     short loc_180086A7B
0x180086a47  mov     r9, cs:hInstance; HINSTANCE
0x180086a4e  mov     r8d, 8000FFFFh; int
0x180086a54  lea     rdx, _GUID_0eb1088c_4dcd_46f0_878f_39dae86a51b7; struct _GUID *
0x180086a5b  mov     ecx, 0C0040506h; dwMessageId
0x180086a60  call    ?Error@?$CComCoClass@VCMSVidVideoRenderer@@$1?_GUID_37b03543_a4c8_11d2_b634_00c04f79498e@@3U__s_GUID@@B@ATL@@SAJIAEBU_GUID@@JPEAUHINSTANCE__@@@Z; ATL::CComCoClass<CMSVidVideoRenderer,&__s_GUID const _GUID_37b03543_a4c8_11d2_b634_00c04f79498e>::Error(uint,_GUID const &,long,HINSTANCE__ *)
0x180086a65  mov     ebx, eax
0x180086a67  lea     rcx, [rsp+0A8h+arg_10]
0x180086a6f  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180086a74  mov     eax, ebx
0x180086a76  jmp     loc_180086D84
0x180086a7b  lea     rcx, [rbx+0C8h]; struct IUnknown **
0x180086a82  lea     r8, _GUID_0eb1088c_4dcd_46f0_878f_39dae86a51b7; struct _GUID *
0x180086a89  mov     rdx, [rsi]; struct IUnknown *
0x180086a8c  call    ?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z; ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)
0x180086a91  cmp     [rbx+54h], r15b
0x180086a95  jz      loc_180086C20
0x180086a9b  mov     rcx, [rdi]
0x180086a9e  mov     rax, [rcx]
0x180086aa1  mov     edx, 4
0x180086aa6  mov     rax, [rax+20h]
0x180086aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086aaf  test    eax, eax
0x180086ab1  jns     short loc_180086AE7
0x180086ab3  mov     r9, cs:hInstance; HINSTANCE
0x180086aba  mov     r8d, 8000FFFFh; int
0x180086ac0  lea     rdx, _GUID_0eb1088c_4dcd_46f0_878f_39dae86a51b7; struct _GUID *
0x180086ac7  mov     ecx, 0C004050Dh; dwMessageId
0x180086acc  call    ?Error@?$CComCoClass@VCMSVidVideoRenderer@@$1?_GUID_37b03543_a4c8_11d2_b634_00c04f79498e@@3U__s_GUID@@B@ATL@@SAJIAEBU_GUID@@JPEAUHINSTANCE__@@@Z; ATL::CComCoClass<CMSVidVideoRenderer,&__s_GUID const _GUID_37b03543_a4c8_11d2_b634_00c04f79498e>::Error(uint,_GUID const &,long,HINSTANCE__ *)
0x180086ad1  mov     ebx, eax
0x180086ad3  lea     rcx, [rsp+0A8h+arg_10]
0x180086adb  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180086ae0  mov     eax, ebx
0x180086ae2  jmp     loc_180086D84
0x180086ae7  mov     dword ptr [rsp+0A8h+arg_0], r15d
0x180086aef  lea     r14, [rbx+0D8h]
0x180086af6  lea     r8, _GUID_1c1a17b0_bed0_415d_974b_dc6696131599; struct _GUID *
0x180086afd  mov     rdx, [rdi]; struct IUnknown *
0x180086b00  mov     rcx, r14; struct IUnknown **
0x180086b03  call    ?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z; ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)
0x180086b08  mov     rcx, [r14]
0x180086b0b  test    rcx, rcx
0x180086b0e  jnz     short loc_180086B27
0x180086b10  lea     rcx, [rsp+0A8h+arg_10]
0x180086b18  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180086b1d  mov     eax, 8000FFFFh
0x180086b22  jmp     loc_180086D84
0x180086b27  mov     rax, [rcx]
0x180086b2a  lea     rdx, [rsp+0A8h+arg_0]
0x180086b32  mov     rax, [rax+60h]
0x180086b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086b3b  mov     esi, eax
0x180086b3d  test    eax, eax
0x180086b3f  jns     short loc_180086B55
0x180086b41  lea     rcx, [rsp+0A8h+arg_10]
0x180086b49  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180086b4e  mov     eax, esi
0x180086b50  jmp     loc_180086D84
0x180086b55  mov     esi, 1004h
0x180086b5a  mov     [rsp+0A8h+var_58], r15
0x180086b5f  mov     [rsp+0A8h+var_50], r15
0x180086b64  mov     [rsp+0A8h+var_48], r15
0x180086b69  mov     [rsp+0A8h+arg_8], r15d
0x180086b71  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\DirectShow\\Debug"...
0x180086b78  lea     rcx, [rsp+0A8h+lpSubKey]; this
0x180086b80  call    ??0CString@WTL@@QEAA@PEBG@Z; WTL::CString::CString(ushort const *)
0x180086b85  nop
0x180086b86  mov     dword ptr [rsp+0A8h+ppv], r15d; unsigned int
0x180086b8b  mov     r9d, 20019h; unsigned int
0x180086b91  mov     r8, [rsp+0A8h+lpSubKey]; lpSubKey
0x180086b99  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180086ba0  lea     rcx, [rsp+0A8h+var_58]; this
0x180086ba5  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x180086baa  test    eax, eax
0x180086bac  jnz     short loc_180086BD1
0x180086bae  lea     r8, aMixerprefs; "MixerPrefs"
0x180086bb5  lea     rdx, [rsp+0A8h+arg_8]; unsigned int *
0x180086bbd  lea     rcx, [rsp+0A8h+var_58]; this
0x180086bc2  call    ?QueryValue@CRegKey@ATL@@QEAAJAEAKPEBG@Z; ATL::CRegKey::QueryValue(ulong &,ushort const *)
0x180086bc7  test    eax, eax
0x180086bc9  cmovz   esi, [rsp+0A8h+arg_8]
0x180086bd1  mov     edx, dword ptr [rsp+0A8h+arg_0]
0x180086bd8  and     edx, 0FFFF00FFh
0x180086bde  or      edx, esi
0x180086be0  and     edx, 0FFFFFFF0h
0x180086be3  mov     eax, [rbx+58h]
0x180086be6  neg     eax
0x180086be8  sbb     ecx, ecx
0x180086bea  neg     ecx
0x180086bec  inc     ecx
0x180086bee  or      edx, ecx
0x180086bf0  mov     dword ptr [rsp+0A8h+arg_0], edx
0x180086bf7  mov     rcx, [r14]
0x180086bfa  mov     rax, [rcx]
0x180086bfd  mov     rax, [rax+58h]
0x180086c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086c06  nop
0x180086c07  lea     rcx, [rsp+0A8h+lpSubKey]; this
0x180086c0f  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180086c14  nop
0x180086c15  lea     rcx, [rsp+0A8h+var_58]; this
0x180086c1a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180086c1f  nop
0x180086c20  lea     rcx, [rsp+0A8h+arg_10]
0x180086c28  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180086c2d  mov     rdx, [rdi]; struct IUnknown *
0x180086c30  lea     rcx, [rsp+0A8h+var_68]; this
0x180086c35  call    ??0DSFilter@@QEAA@PEAUIUnknown@@@Z; DSFilter::DSFilter(IUnknown *)
0x180086c3a  nop
0x180086c3b  cmp     [rsp+0A8h+var_60], r15
0x180086c40  jnz     short loc_180086C7F
0x180086c42  mov     r9, cs:hInstance; HINSTANCE
0x180086c49  mov     r8d, 8000FFFFh; int
0x180086c4f  lea     rdx, _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770; struct _GUID *
0x180086c56  mov     ecx, 0C0040506h; dwMessageId
0x180086c5b  call    ?Error@?$CComCoClass@VCMSVidVideoRenderer@@$1?_GUID_37b03543_a4c8_11d2_b634_00c04f79498e@@3U__s_GUID@@B@ATL@@SAJIAEBU_GUID@@JPEAUHINSTANCE__@@@Z; ATL::CComCoClass<CMSVidVideoRenderer,&__s_GUID const _GUID_37b03543_a4c8_11d2_b634_00c04f79498e>::Error(uint,_GUID const &,long,HINSTANCE__ *)
0x180086c60  mov     ebx, eax
0x180086c62  lea     rcx, ??_7?$Forward_Sequence@V?$CComQIPtr@UIBaseFilter@@$1?IID_IBaseFilter@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumPins@@$1?IID_IEnumPins@@3U_GUID@@B@2@VDSPin@@UIBaseFilter@@UIEnumPins@@PEAUIPin@@V?$allocator@VDSPin@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable'
0x180086c69  mov     [rsp+0A8h+var_68], rcx
0x180086c6e  lea     rcx, [rsp+0A8h+var_60]
0x180086c73  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180086c78  mov     eax, ebx
0x180086c7a  jmp     loc_180086D84
0x180086c7f  cmp     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x180086c83  jnz     loc_180086D17
0x180086c89  lea     rdx, aVideoMixingRen; "Video Mixing Renderer"
0x180086c90  lea     rcx, [rsp+0A8h+arg_0]; this
0x180086c98  call    ??0CString@WTL@@QEAA@PEBG@Z; WTL::CString::CString(ushort const *)
0x180086c9d  nop
0x180086c9e  mov     rax, [rbx-8]
0x180086ca2  movsxd  rcx, dword ptr [rax+4]
0x180086ca6  add     rcx, 18h
0x180086caa  add     rcx, rbx; this
0x180086cad  lea     r8, [rsp+0A8h+arg_0]; struct WTL::CString *
0x180086cb5  lea     rdx, [rsp+0A8h+var_68]; struct DSFilter *
0x180086cba  call    ?AddFilter@DSGraph@@QEAAJAEAVDSFilter@@AEAVCString@WTL@@@Z; DSGraph::AddFilter(DSFilter &,WTL::CString &)
0x180086cbf  mov     edi, eax
0x180086cc1  test    eax, eax
0x180086cc3  jns     short loc_180086CF0
0x180086cc5  lea     rcx, [rsp+0A8h+arg_0]; this
0x180086ccd  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180086cd2  nop
0x180086cd3  lea     rcx, ??_7?$Forward_Sequence@V?$CComQIPtr@UIBaseFilter@@$1?IID_IBaseFilter@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumPins@@$1?IID_IEnumPins@@3U_GUID@@B@2@VDSPin@@UIBaseFilter@@UIEnumPins@@PEAUIPin@@V?$allocator@VDSPin@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable'
0x180086cda  mov     [rsp+0A8h+var_68], rcx
0x180086cdf  lea     rcx, [rsp+0A8h+var_60]
0x180086ce4  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180086ce9  mov     eax, edi
0x180086ceb  jmp     loc_180086D84
0x180086cf0  mov     rax, [rbx-8]
0x180086cf4  movsxd  rcx, dword ptr [rax+4]
0x180086cf8  add     rcx, 28h ; '('
0x180086cfc  add     rcx, rbx
0x180086cff  lea     rdx, [rsp+0A8h+var_68]
0x180086d04  call    ?push_back@?$vector@VDSFilter@@V?$allocator@VDSFilter@@@std@@@std@@QEAAXAEBVDSFilter@@@Z; std::vector<DSFilter>::push_back(DSFilter const &)
0x180086d09  nop
0x180086d0a  lea     rcx, [rsp+0A8h+arg_0]; this
0x180086d12  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180086d17  mov     [rbx+1Ch], r15d
0x180086d1b  mov     rax, [rbx]
0x180086d1e  mov     rcx, rbx
0x180086d21  mov     rax, [rax+150h]
0x180086d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086d2d  nop
0x180086d2e  lea     rcx, ??_7?$Forward_Sequence@V?$CComQIPtr@UIBaseFilter@@$1?IID_IBaseFilter@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumPins@@$1?IID_IEnumPins@@3U_GUID@@B@2@VDSPin@@UIBaseFilter@@UIEnumPins@@PEAUIPin@@V?$allocator@VDSPin@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable'
0x180086d35  mov     [rsp+0A8h+var_68], rcx
0x180086d3a  lea     rcx, [rsp+0A8h+var_60]
0x180086d3f  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180086d44  xor     eax, eax
0x180086d46  jmp     short loc_180086D84
0x180086d48  mov     eax, [rsp+0A8h+var_78]
0x180086d4c  jmp     short loc_180086D63
0x180086d4e  mov     eax, dword ptr [rsp+0A8h+arg_0]
0x180086d55  jmp     short loc_180086D63
0x180086d57  mov     eax, 8007000Eh
0x180086d5c  jmp     short loc_180086D63
0x180086d5e  mov     eax, 8000FFFFh
0x180086d63  jmp     short loc_180086D84
0x180086d65  mov     r9, cs:hInstance; HINSTANCE
0x180086d6c  mov     r8d, 800401F0h; int
0x180086d72  lea     rdx, _GUID_dd47de3f_9874_4f7b_8b22_7cb2688461e7; struct _GUID *
0x180086d79  mov     ecx, 0C0040502h; dwMessageId
0x180086d7e  call    ?Error@?$CComCoClass@VCMSVidVideoRenderer@@$1?_GUID_37b03543_a4c8_11d2_b634_00c04f79498e@@3U__s_GUID@@B@ATL@@SAJIAEBU_GUID@@JPEAUHINSTANCE__@@@Z; ATL::CComCoClass<CMSVidVideoRenderer,&__s_GUID const _GUID_37b03543_a4c8_11d2_b634_00c04f79498e>::Error(uint,_GUID const &,long,HINSTANCE__ *)
0x180086d83  nop
0x180086d84  add     rsp, 80h
0x180086d8b  pop     r15
0x180086d8d  pop     r14
  ... truncated ...
```
