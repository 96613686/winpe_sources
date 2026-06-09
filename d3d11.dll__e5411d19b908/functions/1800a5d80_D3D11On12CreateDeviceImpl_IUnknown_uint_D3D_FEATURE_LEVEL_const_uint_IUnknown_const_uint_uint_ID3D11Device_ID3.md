# D3D11On12CreateDeviceImpl(IUnknown *,uint,D3D_FEATURE_LEVEL const *,uint,IUnknown * const *,uint,uint,ID3D11Device * *,ID3D11DeviceContext * *,D3D_FEATURE_LEVEL *)

- ea: `0x1800a5d80`
- end: `0x1800a657c`
- name: `?D3D11On12CreateDeviceImpl@@YAJPEAUIUnknown@@IPEBW4D3D_FEATURE_LEVEL@@IPEBQEAU1@IIPEAPEAUID3D11Device@@PEAPEAUID3D11DeviceContext@@PEAW42@@Z`
- size: `2044`
- prototype: `__int64 __fastcall(struct IUnknown *, unsigned int, const enum D3D_FEATURE_LEVEL *, unsigned int, struct IUnknown *const *, unsigned int, ULONGLONG Value, struct ID3D11Device **, struct ID3D11DeviceContext **, enum D3D_FEATURE_LEVEL *)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800aec50`

## callees

- `0x180011080`
- `0x1800147d0`
- `0x180022400`
- `0x180034550`
- `0x180047a80`
- `0x180048fa8`
- `0x1800490f4`
- `0x180049310`
- `0x180049518`
- `0x18004a74c`
- `0x18006af94`
- `0x18006bb14`
- `0x180082034`
- `0x18009797c`
- `0x1800a2e84`
- `0x1800a5d80`
- `0x1800a8674`
- `0x1800a9d20`
- `0x1800dd664`
- `0x1801cb010`

## import_xrefs

- `ntdll!RtlNumberOfSetBitsUlongPtr` at `0x1800a5efa`
- `ntdll!RtlNumberOfSetBitsUlongPtr` at `0x1800a5efa`
- `ntdll!RtlFindLeastSignificantBit` at `0x1800a5f14`
- `ntdll!RtlFindLeastSignificantBit` at `0x1800a5f14`
- `dxgi!CreateDXGIFactory2` at `0x1800a6145`
- `dxgi!CreateDXGIFactory2` at `0x1800a6145`
- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x1800a6246`
- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x1800a6246`
- `ext-ms-win-dxcore-internal-l1-1-0!__imp_DXCoreCreateInternalFactory` at `0x1800a626c`
- `ext-ms-win-dxcore-internal-l1-1-0!__imp_DXCoreCreateInternalFactory` at `0x1800a626c`

## string_xrefs

- `0x1800a5e47`: `D3D11On12CreateDevice: You must specify a D3D12 device.`
- `0x1800a652b`: `D3D11On12CreateDevice: The device provided is not a valid D3D12 device.`
- `0x1800a5ea9`: `D3D11On12CreateDevice: The output parameter pChosenFeatureLevel must not overlap with the input paramteter array pFeatureLevels.`
- `0x1800a5f05`: `D3D11On12CreateDevice: The NodeMask parameter must only have a single bit set.`
- `0x1800a5f3e`: `D3D11On12CreateDevice: If NumQueues is nonzero, ppCommandQueues must be non-null, and vice versa.`
- `0x1800a6079`: `D3D11On12CreateDevice: Not all command queues provided are valid D3D12 command queues.`
- `0x1800a602d`: `D3D11On12CreateDevice: When D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT is set, all provided command queues must have been created with D3D12_COMMAND_QUEUE_FLAG_DISABLE_GPU_TIMEOUT.`
- `0x1800a6070`: `D3D11On12CreateDevice: All command queues provided must target the node specified by NodeMask.`
- `0x1800a6067`: `D3D11On12CreateDevice: Unsupported command queue type provided.`
- `0x1800a605e`: `D3D11On12CreateDevice: Only a single command queue of each type per node may be provided.`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall D3D11On12CreateDeviceImpl(
        struct IUnknown *a1,
        unsigned int a2,
        const enum D3D_FEATURE_LEVEL *a3,
        unsigned int a4,
        struct IUnknown *const *a5,
        unsigned int a6,
        ULONGLONG Value,
        struct ID3D11Device **a8,
        struct ID3D11DeviceContext **a9,
        enum D3D_FEATURE_LEVEL *a10)
{
  __int64 v10; // r13
  struct ID3D11Device **v13; // rsi
  struct ID3D11DeviceContext **v14; // r12
  enum D3D_FEATURE_LEVEL *v15; // r14
  struct ID3D11Device **v16; // rax
  const char *v17; // r8
  unsigned int v18; // eax
  ULONGLONG v19; // r13
  struct IUnknown *const *v20; // r8
  void *v21; // rbx
  unsigned int v22; // r15d
  const char *v23; // r8
  int v24; // r15d
  UINT DeviceFlags; // eax
  void **v26; // r8
  HRESULT DXGIFactory2; // eax
  void *v28; // rbx
  int (__fastcall *v29)(void *, _QWORD, GUID *, __int64); // r13
  __int64 v30; // r15
  _QWORD *v31; // rax
  void *v32; // rax
  unsigned int v33; // edx
  NDXGI::CUMDAdapter *v34; // rax
  NDXGI::CUMDAdapter *v35; // rcx
  NDXGI::CUMDAdapter *v36; // rcx
  __int64 v37; // rax
  int AdapterFactory; // ecx
  __int64 v39; // rax
  int InternalFactory; // ecx
  int v41; // eax
  void *v42; // rbx
  __int64 (__fastcall *v43)(void *, __int64, GUID *, __int64); // r13
  __int64 v44; // r15
  __int64 v45; // rax
  int v46; // eax
  int v47; // eax
  void *v48; // rax
  unsigned int v49; // edx
  NDXGI::CUMDAdapter *v50; // rax
  NDXGI::CUMDAdapter *v51; // rcx
  NDXGI::CUMDAdapter *v52; // rcx
  signed int Device; // ebx
  _BYTE *v54; // rdx
  NDXGI::CUMDAdapter *v55; // rcx
  _BYTE v57[32]; // [rsp+0h] [rbp-1B8h] BYREF
  unsigned int v58; // [rsp+50h] [rbp-168h]
  void *v59; // [rsp+58h] [rbp-160h] BYREF
  CCHAR LeastSignificantBit; // [rsp+60h] [rbp-158h]
  __int64 v61; // [rsp+68h] [rbp-150h] BYREF
  _BYTE v62[16]; // [rsp+70h] [rbp-148h] BYREF
  void *v63; // [rsp+80h] [rbp-138h] BYREF
  void *v64; // [rsp+88h] [rbp-130h] BYREF
  struct IUnknown *const *v65; // [rsp+90h] [rbp-128h] BYREF
  __int64 v66; // [rsp+98h] [rbp-120h] BYREF
  int v67; // [rsp+A0h] [rbp-118h]
  struct ID3D11Device **v68; // [rsp+A8h] [rbp-110h]
  __int64 v69; // [rsp+B0h] [rbp-108h] BYREF
  const enum D3D_FEATURE_LEVEL *v70; // [rsp+B8h] [rbp-100h]
  struct ID3D11DeviceContext **v71; // [rsp+C0h] [rbp-F8h]
  enum D3D_FEATURE_LEVEL *v72; // [rsp+C8h] [rbp-F0h]
  _QWORD v73[2]; // [rsp+D0h] [rbp-E8h] BYREF
  __int128 v74; // [rsp+E0h] [rbp-D8h]
  __int128 v75; // [rsp+F0h] [rbp-C8h]
  int v76; // [rsp+100h] [rbp-B8h]
  int v77; // [rsp+104h] [rbp-B4h]
  __int128 v78; // [rsp+108h] [rbp-B0h]
  __int64 v79; // [rsp+120h] [rbp-98h] BYREF
  _com_error *v80; // [rsp+128h] [rbp-90h] BYREF
  _BYTE v81[16]; // [rsp+130h] [rbp-88h] BYREF
  void **pExceptionObject; // [rsp+140h] [rbp-78h] BYREF
  int v83; // [rsp+148h] [rbp-70h]
  __int128 v84; // [rsp+150h] [rbp-68h]
  void *v85; // [rsp+160h] [rbp-58h] BYREF
  char v86; // [rsp+168h] [rbp-50h]
  int v87; // [rsp+16Ch] [rbp-4Ch]

  v10 = a4;
  v67 = a4;
  v70 = a3;
  v58 = a2;
  v65 = a5;
  v13 = a8;
  v68 = a8;
  v14 = a9;
  v71 = a9;
  v15 = a10;
  v72 = a10;
  if ( a8 )
    *a8 = 0;
  v69 = 0;
  if ( a9 )
  {
    *a9 = 0;
    v16 = (struct ID3D11Device **)&v69;
    if ( a8 )
      v16 = a8;
    v13 = v16;
    v68 = v16;
  }
  DebugPrintF::DebugPrintF((DebugPrintF *)v62, a2);
  if ( !a1 )
  {
    DebugPrintF::operator()(v62, 0, "D3D11On12CreateDevice: You must specify a D3D12 device.");
LABEL_77:
    DebugPrintF::~DebugPrintF((DebugPrintF *)v62);
    return 2147942487LL;
  }
  v61 = 0;
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
         a1,
         &GUID_77acce80_638e_4e65_8895_c1f23386863e,
         &v61) < 0
    || !v61 )
  {
    v17 = "D3D11On12CreateDevice: The device provided is not a valid D3D12 device.";
LABEL_75:
    DebugPrintF::operator()(v62, 0, v17);
LABEL_76:
    ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v61);
    goto LABEL_77;
  }
  if ( a3 )
  {
    if ( !a10 )
      goto LABEL_18;
    if ( a3 <= a10 && a10 < &a3[v10] )
    {
      v17 = "D3D11On12CreateDevice: The output parameter pChosenFeatureLevel must not overlap with the input paramteter a"
            "rray pFeatureLevels.";
      goto LABEL_75;
    }
  }
  else if ( !a10 )
  {
    goto LABEL_19;
  }
  *a10 = 0;
  if ( a3 )
  {
LABEL_18:
    if ( (_DWORD)v10 )
      goto LABEL_20;
  }
LABEL_19:
  v70 = &qword_1801F4B70;
  v67 = 6;
LABEL_20:
  v18 = 1;
  if ( (_DWORD)Value )
    v18 = Value;
  v19 = v18;
  if ( (unsigned int)RtlNumberOfSetBitsUlongPtr(v18) != 1 )
  {
    v17 = "D3D11On12CreateDevice: The NodeMask parameter must only have a single bit set.";
    goto LABEL_75;
  }
  LeastSignificantBit = RtlFindLeastSignificantBit(v19);
  v20 = v65;
  if ( (a6 != 0) != (v65 != 0) )
  {
    v17 = "D3D11On12CreateDevice: If NumQueues is nonzero, ppCommandQueues must be non-null, and vice versa.";
    goto LABEL_75;
  }
  LODWORD(v66) = v58 & 0x100;
  v21 = 0;
  v64 = 0;
  v22 = 0;
  v63 = 0;
  while ( v22 < a6 )
  {
    v59 = 0;
    if ( ((__int64 (__fastcall *)(struct IUnknown *const, GUID *, void **))v20[v22]->lpVtbl->QueryInterface)(
           v20[v22],
           &GUID_0ec870a6_5d7e_4c22_8cfc_5baae07616ed,
           &v59) < 0 )
    {
      v23 = "D3D11On12CreateDevice: Not all command queues provided are valid D3D12 command queues.";
      goto LABEL_36;
    }
    (*(void (__fastcall **)(void *, void **))(*(_QWORD *)v59 + 144LL))(v59, &v85);
    if ( (_DWORD)v66 && (v86 & 1) == 0 )
    {
      v23 = "D3D11On12CreateDevice: When D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT is set, all provided command queues must"
            " have been created with D3D12_COMMAND_QUEUE_FLAG_DISABLE_GPU_TIMEOUT.";
LABEL_36:
      DebugPrintF::operator()(v62, 0, v23);
      ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v59);
      ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v64);
      goto LABEL_76;
    }
    if ( ((unsigned int)v19 & v87) == 0 )
    {
      v23 = "D3D11On12CreateDevice: All command queues provided must target the node specified by NodeMask.";
      goto LABEL_36;
    }
    if ( (_DWORD)v85 )
    {
      v23 = "D3D11On12CreateDevice: Unsupported command queue type provided.";
      goto LABEL_36;
    }
    if ( v63 )
    {
      v23 = "D3D11On12CreateDevice: Only a single command queue of each type per node may be provided.";
      goto LABEL_36;
    }
    v21 = v59;
    v59 = 0;
    v64 = v21;
    ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v59);
    ++v22;
    v63 = v21;
    v20 = v65;
  }
  v24 = LeastSignificantBit;
  ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(v81, &xmmword_18022B808);
  v74 = 0;
  v75 = 0;
  v76 = 1;
  v77 = 7;
  v79 = 0;
  v73[0] = v61;
  v73[1] = v21;
  DWORD2(v74) = v24;
  v78 = (unsigned __int64)&v79;
  v65 = 0;
  v66 = 0;
  v59 = 0;
  IID_PPV_ARGS_Helper<ID3D11UnorderedAccessView>(&v59);
  DeviceFlags = FactoryFlagsFromCreateDeviceFlags(v58);
  DXGIFactory2 = CreateDXGIFactory2(DeviceFlags, &GUID_1bc6ea02_ef36_464f_bf0c_21ca39e5168a, v26);
  try
  {
    if ( DXGIFactory2 >= 0 )
    {
      v28 = v59;
      v29 = *(int (__fastcall **)(void *, _QWORD, GUID *, __int64))(*(_QWORD *)v59 + 208LL);
      v30 = IID_PPV_ARGS_Helper<ID3D11UnorderedAccessView>(&v65);
      v31 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, void **))(*(_QWORD *)v73[0] + 344LL))(v73[0], &v63);
      if ( v29(v28, *v31, &GUID_7abb6563_02bc_47c4_8ef9_acc4795edbcf, v30) >= 0 )
      {
        *(_QWORD *)&v74 = v65;
        v32 = operator new(0x3B8u);
        v63 = v32;
        v34 = v32 ? (NDXGI::CUMDAdapter *)NDXGI::CUMDAdapter::CUMDAdapter(v32, v65, 3, v58) : 0LL;
        v35 = qword_18022B840;
        qword_18022B840 = v34;
        if ( v35 )
          NDXGI::CUMDAdapter::`scalar deleting destructor'(v35, v33);
      }
    }
    ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v59);
    v36 = qword_18022B840;
    if ( !qword_18022B840 )
    {
      v63 = 0;
      v37 = IID_PPV_ARGS_Helper<ID3D11UnorderedAccessView>(&v63);
      AdapterFactory = DXCoreCreateAdapterFactory(&GUID_78ee5945_c36e_4b13_a669_005dd11c0f06, v37);
      ThrowFailure(AdapterFactory);
      v59 = 0;
      v39 = IID_PPV_ARGS_Helper<ID3D11UnorderedAccessView>(&v59);
      InternalFactory = DXCoreCreateInternalFactory(&GUID_0d82d832_e474_4da9_a162_c3dffda0fa6d, v39);
      ThrowFailure(InternalFactory);
      v41 = (*(__int64 (__fastcall **)(void *, _QWORD, __int64))(*(_QWORD *)v59 + 24LL))(v59, 0, 1);
      ThrowFailure(v41);
      v42 = v63;
      v43 = *(__int64 (__fastcall **)(void *, __int64, GUID *, __int64))(*(_QWORD *)v63 + 32LL);
      v44 = IID_PPV_ARGS_Helper<ID3D11UnorderedAccessView>(&v66);
      v45 = (*(__int64 (__fastcall **)(_QWORD, void **))(*(_QWORD *)v73[0] + 344LL))(v73[0], &v85);
      v46 = v43(v42, v45, &GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e, v44);
      ThrowFailure(v46);
      v47 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)v59 + 24LL))(v59, 0, 0);
      ThrowFailure(v47);
      *(_QWORD *)&v74 = v66;
      v48 = operator new(0x3B8u);
      v85 = v48;
      if ( v48 )
        v50 = (NDXGI::CUMDAdapter *)NDXGI::CUMDAdapter::CUMDAdapter(v48, v66, 3, v58);
      else
        v50 = 0;
      v51 = qword_18022B840;
      qword_18022B840 = v50;
      if ( v51 )
        NDXGI::CUMDAdapter::`scalar deleting destructor'(v51, v49);
      ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v59);
      ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v63);
      v36 = qword_18022B840;
    }
    if ( (int)NDXGI::CUMDAdapter::UMDLoadStatus(v36) < 0
      || NDXGI::CUMDAdapter::OpenAdapterD3D11On12(v52, (struct D3D11On12::SOpenAdapterArgs *)v73) < 0 )
    {
      pExceptionObject = &_com_error::`vftable';
      v83 = -2005270524;
      v84 = 0;
      throw (_com_error *)&pExceptionObject;
    }
    Device = D3D11CoreCreateDevice(
               (unsigned int)qword_1801F9490,
               v74,
               0,
               0,
               v58 | 0x8000000,
               (__int64)v70,
               v67,
               7,
               (__int64)v13,
               (__int64)a10);
    ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v66);
    ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v65);
  }
  catch ( std::bad_alloc )
  {
    v54 = v57;
    v58 = -2147024882;
    v15 = v72;
    v14 = v71;
    v13 = v68;
    Device = -2147024882;
  }
  catch ( _com_error *v80 )
  {
    v54 = v57;
    v58 = *((_DWORD *)v80 + 2);
    v15 = v72;
    v14 = v71;
    v13 = v68;
    Device = v58;
  }
  if ( DXGIFactory2 >= 0 )
  {
    v28 = v59;
    v29 = *(int (__fastcall **)(void *, _QWORD, GUID *, __int64))(*(_QWORD *)v59 + 208LL);
    v30 = IID_PPV_ARGS_Helper<ID3D11UnorderedAccessView>(&v65);
    v31 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, void **))(*(_QWORD *)v73[0] + 344LL))(v73[0], &v63);
    if ( v29(v28, *v31, &GUID_7abb6563_02bc_47c4_8ef9_acc4795edbcf, v30) >= 0 )
    {
      *(_QWORD *)&v74 = v65;
      v32 = operator new(0x3B8u);
      v63 = v32;
      v34 = v32 ? (NDXGI::CUMDAdapter *)NDXGI::CUMDAdapter::CUMDAdapter(v32, v65, 3, v58) : 0LL;
      v35 = qword_18022B840;
      qword_18022B840 = v34;
      if ( v35 )
        NDXGI::CUMDAdapter::`scalar deleting destructor'(v35, v33);
    }
  }
  ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v59);
  v36 = qword_18022B840;
  if ( !qword_18022B840 )
  {
    v63 = 0;
    v37 = IID_PPV_ARGS_Helper<ID3D11UnorderedAccessView>(&v63);
    AdapterFactory = DXCoreCreateAdapterFactory(&GUID_78ee5945_c36e_4b13_a669_005dd11c0f06, v37);
    ThrowFailure(AdapterFactory);
    v59 = 0;
    v39 = IID_PPV_ARGS_Helper<ID3D11UnorderedAccessView>(&v59);
    InternalFactory = DXCoreCreateInternalFactory(&GUID_0d82d832_e474_4da9_a162_c3dffda0fa6d, v39);
    ThrowFailure(InternalFactory);
    v41 = (*(__int64 (__fastcall **)(void *, _QWORD, __int64))(*(_QWORD *)v59 + 24LL))(v59, 0, 1);
    ThrowFailure(v41);
    v42 = v63;
    v43 = *(__int64 (__fastcall **)(void *, __int64, GUID *, __int64))(*(_QWORD *)v63 + 32LL);
    v44 = IID_PPV_ARGS_Helper<ID3D11UnorderedAccessView>(&v66);
    v45 = (*(__int64 (__fastcall **)(_QWORD, void **))(*(_QWORD *)v73[0] + 344LL))(v73[0], &v85);
    v46 = v43(v42, v45, &GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e, v44);
    ThrowFailure(v46);
    v47 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)v59 + 24LL))(v59, 0, 0);
    ThrowFailure(v47);
    *(_QWORD *)&v74 = v66;
    v48 = operator new(0x3B8u);
    v85 = v48;
    if ( v48 )
      v50 = (NDXGI::CUMDAdapter *)NDXGI::CUMDAdapter::CUMDAdapter(v48, v66, 3, v58);
    else
      v50 = 0;
    v51 = qword_18022B840;
    qword_18022B840 = v50;
    if ( v51 )
      NDXGI::CUMDAdapter::`scalar deleting destructor'(v51, v49);
    ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v59);
    ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v63);
    v36 = qword_18022B840;
  }
  if ( (int)NDXGI::CUMDAdapter::UMDLoadStatus(v36) < 0
    || NDXGI::CUMDAdapter::OpenAdapterD3D11On12(v52, (struct D3D11On12::SOpenAdapterArgs *)v73) < 0 )
  {
    pExceptionObject = &_com_error::`vftable';
    v83 = -2005270524;
    v84 = 0;
    throw (_com_error *)&pExceptionObject;
  }
  Device = D3D11CoreCreateDevice(
             (unsigned int)qword_1801F9490,
             v74,
             0,
             0,
             v58 | 0x8000000,
             (__int64)v70,
             v67,
             7,
             (__int64)v13,
             (__int64)a10);
  ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v66);
  ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v65);
  v54 = v57;
  v58 = -2147024882;
}

```

## disassembly

```asm
0x1800a5d80  push    rbx
0x1800a5d82  push    rsi
0x1800a5d83  push    rdi
0x1800a5d84  push    r12
0x1800a5d86  push    r13
0x1800a5d88  push    r14
0x1800a5d8a  push    r15
0x1800a5d8c  sub     rsp, 180h
0x1800a5d93  mov     rax, cs:__security_cookie
0x1800a5d9a  xor     rax, rsp
0x1800a5d9d  mov     [rsp+1B8h+var_48], rax
0x1800a5da5  mov     r13d, r9d
0x1800a5da8  mov     [rsp+1B8h+var_118], r13d
0x1800a5db0  mov     r15, r8
0x1800a5db3  mov     [rsp+1B8h+var_100], r8
0x1800a5dbb  mov     [rsp+1B8h+var_168], edx
0x1800a5dbf  mov     rbx, rcx
0x1800a5dc2  mov     rax, [rsp+1B8h+arg_20]
0x1800a5dca  mov     [rsp+1B8h+var_128], rax
0x1800a5dd2  mov     rsi, [rsp+1B8h+arg_38]
0x1800a5dda  mov     [rsp+1B8h+var_110], rsi
0x1800a5de2  mov     r12, [rsp+1B8h+arg_40]
0x1800a5dea  mov     [rsp+1B8h+var_F8], r12
0x1800a5df2  mov     r14, [rsp+1B8h+arg_48]
0x1800a5dfa  mov     [rsp+1B8h+var_F0], r14
0x1800a5e02  xor     edi, edi
0x1800a5e04  test    rsi, rsi
0x1800a5e07  jz      short loc_1800A5E0C
0x1800a5e09  mov     [rsi], rdi
0x1800a5e0c  mov     [rsp+1B8h+var_108], rdi
0x1800a5e14  test    r12, r12
0x1800a5e17  jz      short loc_1800A5E37
0x1800a5e19  mov     [r12], rdi
0x1800a5e1d  lea     rax, [rsp+1B8h+var_108]
0x1800a5e25  test    rsi, rsi
0x1800a5e28  cmovnz  rax, rsi
0x1800a5e2c  mov     rsi, rax
0x1800a5e2f  mov     [rsp+1B8h+var_110], rax
0x1800a5e37  lea     rcx, [rsp+1B8h+var_148]; this
0x1800a5e3c  call    ??0DebugPrintF@@QEAA@I@Z; DebugPrintF::DebugPrintF(uint)
0x1800a5e41  nop
0x1800a5e42  test    rbx, rbx
0x1800a5e45  jnz     short loc_1800A5E5F
0x1800a5e47  lea     r8, aD3d11on12creat_5; "D3D11On12CreateDevice: You must specify"...
0x1800a5e4e  xor     edx, edx
0x1800a5e50  lea     rcx, [rsp+1B8h+var_148]
0x1800a5e55  call    ??RDebugPrintF@@QEAAXIPEBDZZ; DebugPrintF::operator()(uint,char const *,...)
0x1800a5e5a  jmp     loc_1800A654A
0x1800a5e5f  mov     [rsp+1B8h+var_150], rdi
0x1800a5e64  mov     rax, [rbx]
0x1800a5e67  lea     r8, [rsp+1B8h+var_150]
0x1800a5e6c  lea     rdx, _GUID_77acce80_638e_4e65_8895_c1f23386863e
0x1800a5e73  mov     rcx, rbx
0x1800a5e76  mov     rax, [rax]
0x1800a5e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5e7e  test    eax, eax
0x1800a5e80  js      loc_1800A652B
0x1800a5e86  cmp     [rsp+1B8h+var_150], rdi
0x1800a5e8b  jz      loc_1800A652B
0x1800a5e91  test    r15, r15
0x1800a5e94  jz      short loc_1800A5EB5
0x1800a5e96  test    r14, r14
0x1800a5e99  jz      short loc_1800A5EC2
0x1800a5e9b  cmp     r15, r14
0x1800a5e9e  ja      short loc_1800A5EBA
0x1800a5ea0  lea     rcx, [r15+r13*4]
0x1800a5ea4  cmp     r14, rcx
0x1800a5ea7  jnb     short loc_1800A5EBA
0x1800a5ea9  lea     r8, aD3d11on12creat_8; "D3D11On12CreateDevice: The output param"...
0x1800a5eb0  jmp     loc_1800A6532
0x1800a5eb5  test    r14, r14
0x1800a5eb8  jz      short loc_1800A5EC7
0x1800a5eba  mov     [r14], edi
0x1800a5ebd  test    r15, r15
0x1800a5ec0  jz      short loc_1800A5EC7
0x1800a5ec2  test    r13d, r13d
0x1800a5ec5  jnz     short loc_1800A5EE1
0x1800a5ec7  lea     rax, qword_1801F4B70
0x1800a5ece  mov     [rsp+1B8h+var_100], rax
0x1800a5ed6  mov     [rsp+1B8h+var_118], 6
0x1800a5ee1  mov     eax, 1
0x1800a5ee6  cmp     dword ptr [rsp+1B8h+Value], edi
0x1800a5eed  cmovnz  eax, dword ptr [rsp+1B8h+Value]
0x1800a5ef5  mov     r13d, eax
0x1800a5ef8  mov     ecx, eax
0x1800a5efa  call    cs:__imp_RtlNumberOfSetBitsUlongPtr
0x1800a5f00  cmp     eax, 1
0x1800a5f03  jz      short loc_1800A5F11
0x1800a5f05  lea     r8, aD3d11on12creat_4; "D3D11On12CreateDevice: The NodeMask par"...
0x1800a5f0c  jmp     loc_1800A6532
0x1800a5f11  mov     rcx, r13; Value
0x1800a5f14  call    cs:__imp_RtlFindLeastSignificantBit
0x1800a5f1a  mov     [rsp+1B8h+var_158], al
0x1800a5f1e  mov     edx, edi
0x1800a5f20  mov     r8, [rsp+1B8h+var_128]
0x1800a5f28  test    r8, r8
0x1800a5f2b  setnz   dl
0x1800a5f2e  mov     ecx, edi
0x1800a5f30  cmp     [rsp+1B8h+arg_28], edi
0x1800a5f37  setnz   cl
0x1800a5f3a  cmp     ecx, edx
0x1800a5f3c  jz      short loc_1800A5F4A
0x1800a5f3e  lea     r8, aD3d11on12creat_1; "D3D11On12CreateDevice: If NumQueues is "...
0x1800a5f45  jmp     loc_1800A6532
0x1800a5f4a  mov     eax, [rsp+1B8h+var_168]
0x1800a5f4e  and     eax, 100h
0x1800a5f53  mov     dword ptr [rsp+1B8h+var_120], eax
0x1800a5f5a  mov     rbx, rdi
0x1800a5f5d  mov     [rsp+1B8h+var_130], rbx
0x1800a5f65  mov     r15d, edi
0x1800a5f68  mov     [rsp+1B8h+var_138], rdi
0x1800a5f70  cmp     r15d, [rsp+1B8h+arg_28]
0x1800a5f78  jnb     loc_1800A6082
0x1800a5f7e  mov     [rsp+1B8h+var_160], rdi
0x1800a5f83  mov     eax, r15d
0x1800a5f86  mov     rcx, [r8+rax*8]
0x1800a5f8a  mov     rax, [rcx]
0x1800a5f8d  lea     r8, [rsp+1B8h+var_160]
0x1800a5f92  lea     rdx, _GUID_0ec870a6_5d7e_4c22_8cfc_5baae07616ed
0x1800a5f99  mov     rax, [rax]
0x1800a5f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5fa1  test    eax, eax
0x1800a5fa3  js      loc_1800A6079
0x1800a5fa9  mov     rcx, [rsp+1B8h+var_160]
0x1800a5fae  mov     rax, [rcx]
0x1800a5fb1  lea     rdx, [rsp+1B8h+var_58]
0x1800a5fb9  mov     rax, [rax+90h]
0x1800a5fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5fc5  cmp     dword ptr [rsp+1B8h+var_120], edi
0x1800a5fcc  jz      short loc_1800A5FD8
0x1800a5fce  test    [rsp+1B8h+var_50], 1
0x1800a5fd6  jz      short loc_1800A602D
0x1800a5fd8  test    [rsp+1B8h+var_4C], r13d
0x1800a5fe0  jz      loc_1800A6070
0x1800a5fe6  cmp     dword ptr [rsp+1B8h+var_58], edi
0x1800a5fed  jnz     short loc_1800A6067
0x1800a5fef  cmp     [rsp+1B8h+var_138], rdi
0x1800a5ff7  jnz     short loc_1800A605E
0x1800a5ff9  mov     rbx, [rsp+1B8h+var_160]
0x1800a5ffe  mov     [rsp+1B8h+var_160], rdi
0x1800a6003  mov     [rsp+1B8h+var_130], rbx
0x1800a600b  lea     rcx, [rsp+1B8h+var_160]
0x1800a6010  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x1800a6015  inc     r15d
0x1800a6018  mov     [rsp+1B8h+var_138], rbx
0x1800a6020  mov     r8, [rsp+1B8h+var_128]
0x1800a6028  jmp     loc_1800A5F70
0x1800a602d  lea     r8, aD3d11on12creat_0; "D3D11On12CreateDevice: When D3D11_CREAT"...
0x1800a6034  xor     edx, edx
0x1800a6036  lea     rcx, [rsp+1B8h+var_148]
0x1800a603b  call    ??RDebugPrintF@@QEAAXIPEBDZZ; DebugPrintF::operator()(uint,char const *,...)
0x1800a6040  nop
0x1800a6041  lea     rcx, [rsp+1B8h+var_160]
0x1800a6046  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x1800a604b  nop
0x1800a604c  lea     rcx, [rsp+1B8h+var_130]
0x1800a6054  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x1800a6059  jmp     loc_1800A653F
0x1800a605e  lea     r8, aD3d11on12creat_7; "D3D11On12CreateDevice: Only a single co"...
0x1800a6065  jmp     short loc_1800A6034
0x1800a6067  lea     r8, aD3d11on12creat_3; "D3D11On12CreateDevice: Unsupported comm"...
0x1800a606e  jmp     short loc_1800A6034
0x1800a6070  lea     r8, aD3d11on12creat_10; "D3D11On12CreateDevice: All command queu"...
0x1800a6077  jmp     short loc_1800A6034
0x1800a6079  lea     r8, aD3d11on12creat_6; "D3D11On12CreateDevice: Not all command "...
0x1800a6080  jmp     short loc_1800A6034
0x1800a6082  movsx   r15d, [rsp+1B8h+var_158]
0x1800a6088  lea     rdx, xmmword_18022B808
0x1800a608f  lea     rcx, [rsp+1B8h+var_88]
0x1800a6097  call    ??0?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@AEAVCComCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(ATL::CComCriticalSection &,bool)
0x1800a609c  nop
0x1800a609d  xor     eax, eax
0x1800a609f  xorps   xmm0, xmm0
0x1800a60a2  movups  [rsp+1B8h+var_E8], xmm0
0x1800a60aa  movups  [rsp+1B8h+var_D8], xmm0
0x1800a60b2  movups  [rsp+1B8h+var_C8], xmm0
0x1800a60ba  mov     [rsp+1B8h+var_B8], eax
0x1800a60c1  mov     [rsp+1B8h+var_B4], 7
0x1800a60cc  movups  [rsp+1B8h+var_B0], xmm0
0x1800a60d4  mov     [rsp+1B8h+var_98], rdi
0x1800a60dc  mov     rax, [rsp+1B8h+var_150]
0x1800a60e1  mov     qword ptr [rsp+1B8h+var_E8], rax
0x1800a60e9  mov     qword ptr [rsp+1B8h+var_E8+8], rbx
0x1800a60f1  mov     dword ptr [rsp+1B8h+var_D8+8], r15d
0x1800a60f9  mov     byte ptr [rsp+1B8h+var_B8], 1
0x1800a6101  lea     rax, [rsp+1B8h+var_98]
0x1800a6109  mov     qword ptr [rsp+1B8h+var_B0], rax
0x1800a6111  mov     [rsp+1B8h+var_128], rdi
0x1800a6119  mov     [rsp+1B8h+var_120], rdi
0x1800a6121  mov     [rsp+1B8h+var_160], rdi
0x1800a6126  lea     rcx, [rsp+1B8h+var_160]
0x1800a612b  call    ??$IID_PPV_ARGS_Helper@UID3D11UnorderedAccessView@@@@YAPEAPEAXPEAPEAUID3D11UnorderedAccessView@@@Z; IID_PPV_ARGS_Helper<ID3D11UnorderedAccessView>(ID3D11UnorderedAccessView * *)
0x1800a6130  mov     r8, rax
0x1800a6133  mov     ecx, [rsp+1B8h+var_168]; unsigned int
0x1800a6137  call    ?FactoryFlagsFromCreateDeviceFlags@@YAII@Z; FactoryFlagsFromCreateDeviceFlags(uint)
0x1800a613c  mov     ecx, eax; Flags
0x1800a613e  lea     rdx, _GUID_1bc6ea02_ef36_464f_bf0c_21ca39e5168a; riid
0x1800a6145  call    cs:__imp_CreateDXGIFactory2
0x1800a614b  test    eax, eax
0x1800a614d  js      loc_1800A620D
0x1800a6153  mov     rbx, [rsp+1B8h+var_160]
0x1800a6158  mov     rax, [rbx]
0x1800a615b  mov     r13, [rax+0D0h]
0x1800a6162  lea     rcx, [rsp+1B8h+var_128]
0x1800a616a  call    ??$IID_PPV_ARGS_Helper@UID3D11UnorderedAccessView@@@@YAPEAPEAXPEAPEAUID3D11UnorderedAccessView@@@Z; IID_PPV_ARGS_Helper<ID3D11UnorderedAccessView>(ID3D11UnorderedAccessView * *)
0x1800a616f  mov     r15, rax
0x1800a6172  mov     rcx, qword ptr [rsp+1B8h+var_E8]
0x1800a617a  mov     rdx, [rcx]
0x1800a617d  mov     rax, [rdx+158h]
0x1800a6184  lea     rdx, [rsp+1B8h+var_138]
0x1800a618c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6191  mov     r9, r15
0x1800a6194  lea     r8, _GUID_7abb6563_02bc_47c4_8ef9_acc4795edbcf
0x1800a619b  mov     rdx, [rax]
0x1800a619e  mov     rcx, rbx
0x1800a61a1  mov     rax, r13
0x1800a61a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a61a9  test    eax, eax
0x1800a61ab  js      short loc_1800A620D
0x1800a61ad  mov     rax, [rsp+1B8h+var_128]
0x1800a61b5  mov     qword ptr [rsp+1B8h+var_D8], rax
0x1800a61bd  mov     ecx, 3B8h; dwBytes
0x1800a61c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a61c7  mov     [rsp+1B8h+var_138], rax
0x1800a61cf  test    rax, rax
0x1800a61d2  jz      short loc_1800A61F1
0x1800a61d4  mov     r9d, [rsp+1B8h+var_168]
0x1800a61d9  mov     r8d, 3
0x1800a61df  mov     rdx, [rsp+1B8h+var_128]
0x1800a61e7  mov     rcx, rax
0x1800a61ea  call    ??0CUMDAdapter@NDXGI@@QEAA@PEAUIDXGIAdapterInternal2@@W4_KMTUMDVERSION@@I@Z; NDXGI::CUMDAdapter::CUMDAdapter(IDXGIAdapterInternal2 *,_KMTUMDVERSION,uint)
0x1800a61ef  jmp     short loc_1800A61F4
0x1800a61f1  mov     rax, rdi
0x1800a61f4  mov     rcx, cs:qword_18022B840; this
0x1800a61fb  mov     cs:qword_18022B840, rax
0x1800a6202  test    rcx, rcx
0x1800a6205  jz      short loc_1800A620D
0x1800a6207  call    ??_GCUMDAdapter@NDXGI@@QEAAPEAXI@Z; NDXGI::CUMDAdapter::`scalar deleting destructor'(uint)
0x1800a620c  nop
0x1800a620d  lea     rcx, [rsp+1B8h+var_160]
0x1800a6212  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x1800a6217  mov     rcx, cs:qword_18022B840
0x1800a621e  test    rcx, rcx
0x1800a6221  jnz     loc_1800A6390
0x1800a6227  mov     [rsp+1B8h+var_138], rdi
0x1800a622f  lea     rcx, [rsp+1B8h+var_138]
0x1800a6237  call    ??$IID_PPV_ARGS_Helper@UID3D11UnorderedAccessView@@@@YAPEAPEAXPEAPEAUID3D11UnorderedAccessView@@@Z; IID_PPV_ARGS_Helper<ID3D11UnorderedAccessView>(ID3D11UnorderedAccessView * *)
0x1800a623c  mov     rdx, rax
0x1800a623f  lea     rcx, _GUID_78ee5945_c36e_4b13_a669_005dd11c0f06
0x1800a6246  call    cs:__imp_DXCoreCreateAdapterFactory
0x1800a624c  mov     ecx, eax; int
0x1800a624e  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800a6253  mov     [rsp+1B8h+var_160], rdi
0x1800a6258  lea     rcx, [rsp+1B8h+var_160]
0x1800a625d  call    ??$IID_PPV_ARGS_Helper@UID3D11UnorderedAccessView@@@@YAPEAPEAXPEAPEAUID3D11UnorderedAccessView@@@Z; IID_PPV_ARGS_Helper<ID3D11UnorderedAccessView>(ID3D11UnorderedAccessView * *)
0x1800a6262  mov     rdx, rax
0x1800a6265  lea     rcx, _GUID_0d82d832_e474_4da9_a162_c3dffda0fa6d
0x1800a626c  call    cs:__imp_DXCoreCreateInternalFactory
0x1800a6272  mov     ecx, eax; int
0x1800a6274  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800a6279  mov     rcx, [rsp+1B8h+var_160]
0x1800a627e  mov     rax, [rcx]
0x1800a6281  xor     edx, edx
0x1800a6283  lea     r8d, [rdx+1]
0x1800a6287  mov     rax, [rax+18h]
0x1800a628b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6290  mov     ecx, eax; int
0x1800a6292  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800a6297  mov     rbx, [rsp+1B8h+var_138]
0x1800a629f  mov     rax, [rbx]
0x1800a62a2  mov     r13, [rax+20h]
0x1800a62a6  lea     rcx, [rsp+1B8h+var_120]
0x1800a62ae  call    ??$IID_PPV_ARGS_Helper@UID3D11UnorderedAccessView@@@@YAPEAPEAXPEAPEAUID3D11UnorderedAccessView@@@Z; IID_PPV_ARGS_Helper<ID3D11UnorderedAccessView>(ID3D11UnorderedAccessView * *)
0x1800a62b3  mov     r15, rax
0x1800a62b6  mov     rcx, qword ptr [rsp+1B8h+var_E8]
0x1800a62be  mov     rdx, [rcx]
0x1800a62c1  mov     rax, [rdx+158h]
0x1800a62c8  lea     rdx, [rsp+1B8h+var_58]
0x1800a62d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a62d5  mov     r9, r15
0x1800a62d8  lea     r8, _GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e
0x1800a62df  mov     rdx, rax
0x1800a62e2  mov     rcx, rbx
0x1800a62e5  mov     rax, r13
0x1800a62e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a62ed  mov     ecx, eax; int
0x1800a62ef  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800a62f4  mov     rcx, [rsp+1B8h+var_160]
0x1800a62f9  mov     rax, [rcx]
0x1800a62fc  xor     r8d, r8d
0x1800a62ff  xor     edx, edx
0x1800a6301  mov     rax, [rax+18h]
0x1800a6305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a630a  mov     ecx, eax; int
0x1800a630c  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800a6311  mov     rax, [rsp+1B8h+var_120]
0x1800a6319  mov     qword ptr [rsp+1B8h+var_D8], rax
0x1800a6321  mov     ecx, 3B8h; dwBytes
0x1800a6326  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a632b  mov     [rsp+1B8h+var_58], rax
  ... truncated ...
```
