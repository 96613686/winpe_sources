# UpdateAdapters(bool)

- ea: `0x14000e174`
- end: `0x14000eaf5`
- name: `?UpdateAdapters@@YAX_N@Z`
- size: `2433`
- prototype: `void __fastcall(bool)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400110b8`

## callees

- `0x1400022a0`
- `0x140002d4c`
- `0x140004f00`
- `0x1400050c0`
- `0x1400051f8`
- `0x14000625c`
- `0x140006334`
- `0x140006640`
- `0x14000672c`
- `0x140007b30`
- `0x140007d8c`
- `0x14000893c`
- `0x14000a280`
- `0x14000bebc`
- `0x14000d358`
- `0x14000d500`
- `0x14000de4c`
- `0x14000e174`
- `0x14000eafc`
- `0x140010390`
- `0x1400103b0`
- `0x1400103d0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e881`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e91a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e970`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e881`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e91a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e970`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e894`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e92d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e983`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e894`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e92d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e983`
- `ntdll!NtClose` at `0x14000e97b`
- `ntdll!NtClose` at `0x14000ea56`
- `ntdll!NtClose` at `0x14000e97b`
- `ntdll!NtClose` at `0x14000ea56`
- `ntdll!RtlPublishWnfStateData` at `0x14000e9de`
- `ntdll!RtlPublishWnfStateData` at `0x14000e9de`
- `ntdll!NtCommitTransaction` at `0x14000e94d`
- `ntdll!NtCommitTransaction` at `0x14000e94d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000e493`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000e6a3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000e493`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000e6a3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000e4e2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000e5f0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000e810`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000e4e2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000e5f0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000e810`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e747`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e88c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e925`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ea42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e747`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e88c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e925`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ea42`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x14000e8af`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x14000e8af`
- `dxgi!CreateDXGIFactory1` at `0x14000e2a7`
- `dxgi!CreateDXGIFactory1` at `0x14000e2a7`
- `d3d12!__imp_D3D12CreateDevice` at `0x14000e571`
- `d3d12!__imp_D3D12CreateDevice` at `0x14000e571`
- `d3d11!D3D11CreateDevice` at `0x14000e443`
- `d3d11!D3D11CreateDevice` at `0x14000e443`

## string_xrefs

- `0x14000e1bf`: `DXGIAdapterCacheHealthActivity`
- `0x14000e9b2`: `onecoreuap\windows\directx\dxg\dxgi\adaptercache\exe\main.cpp`

## pseudocode

```c
void __fastcall UpdateAdapters(bool a1)
{
  HRESULT v2; // eax
  unsigned int v3; // r8d
  enum D3D_FEATURE_LEVEL v4; // r12d
  SIZE_T DedicatedVideoMemory; // r15
  char v6; // di
  unsigned int v7; // r13d
  enum D3D_FEATURE_LEVEL v8; // esi
  void *v9; // rbx
  unsigned int (__fastcall *v10)(void *, _QWORD, IDXGIAdapter **); // r14
  IDXGIAdapter *v11; // rcx
  bool v12; // bl
  BOOL v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // r8d
  enum D3D_FEATURE_LEVEL v16; // ecx
  D3D_FEATURE_LEVEL v17; // eax
  char v18; // bl
  int v19; // eax
  unsigned int v20; // r8d
  unsigned int v21; // eax
  unsigned int v22; // r8d
  AdapterCacheUpdate *v23; // rcx
  enum D3D_FEATURE_LEVEL v24; // eax
  enum D3D_FEATURE_LEVEL v25; // eax
  IDXGIAdapter *v26; // rcx
  int v27; // ecx
  unsigned int v28; // eax
  __int64 *v29; // rbx
  int v30; // ecx
  unsigned __int64 v31; // rax
  unsigned int v32; // eax
  unsigned int v33; // r8d
  __int64 **v34; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  const WCHAR *v37; // rsi
  HKEY v38; // r14
  DWORD LastError; // edi
  enum D3D_FEATURE_LEVEL v40; // r8d
  BYTE v41; // al
  enum D3D_FEATURE_LEVEL v42; // r9d
  __int64 v43; // rdx
  HKEY v44; // rdi
  DWORD v45; // ebx
  int v46; // eax
  unsigned int v47; // r8d
  HANDLE v48; // rdi
  DWORD v49; // ebx
  unsigned int refreshed; // eax
  unsigned int v51; // eax
  void *v52; // rdx
  unsigned int v53; // r8d
  unsigned int pFeatureLevels; // [rsp+20h] [rbp-E0h]
  unsigned int pFeatureLevelsa; // [rsp+20h] [rbp-E0h]
  int pFeatureLevelsb; // [rsp+20h] [rbp-E0h]
  char v57; // [rsp+50h] [rbp-B0h]
  bool v58; // [rsp+51h] [rbp-AFh] BYREF
  bool v59; // [rsp+52h] [rbp-AEh] BYREF
  bool v60; // [rsp+53h] [rbp-ADh] BYREF
  bool v61; // [rsp+54h] [rbp-ACh] BYREF
  bool v62; // [rsp+55h] [rbp-ABh] BYREF
  char v63; // [rsp+56h] [rbp-AAh]
  char v64; // [rsp+57h] [rbp-A9h]
  D3D_FEATURE_LEVEL pvData; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pdwType; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-A0h] BYREF
  IDXGIAdapter *pAdapter; // [rsp+68h] [rbp-98h] BYREF
  enum D3D_FEATURE_LEVEL v69; // [rsp+70h] [rbp-90h]
  enum D3D_FEATURE_LEVEL v70; // [rsp+74h] [rbp-8Ch]
  enum D3D_FEATURE_LEVEL v71; // [rsp+78h] [rbp-88h]
  BYTE v72[4]; // [rsp+7Ch] [rbp-84h]
  BYTE Data[8]; // [rsp+80h] [rbp-80h] BYREF
  enum D3D_FEATURE_LEVEL v74; // [rsp+88h] [rbp-78h]
  void *ppFactory; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v76[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v77; // [rsp+A8h] [rbp-58h]
  HANDLE Handle; // [rsp+B0h] [rbp-50h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp-48h]
  _QWORD v80[3]; // [rsp+C0h] [rbp-40h] BYREF
  char v81; // [rsp+D8h] [rbp-28h]
  _BYTE v82[24]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v83[40]; // [rsp+F8h] [rbp-8h] BYREF
  HKEY hkey[5]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v85; // [rsp+148h] [rbp+48h] BYREF
  __int64 v86; // [rsp+158h] [rbp+58h]
  __int64 v87; // [rsp+160h] [rbp+60h]
  void **v88; // [rsp+190h] [rbp+90h] BYREF
  int v89; // [rsp+198h] [rbp+98h] BYREF
  char v90; // [rsp+19Ch] [rbp+9Ch]
  int v91; // [rsp+1C0h] [rbp+C0h] BYREF
  const char *v92; // [rsp+1C8h] [rbp+C8h]
  __int64 v93; // [rsp+1D0h] [rbp+D0h]
  char v94; // [rsp+1D8h] [rbp+D8h]
  int v95; // [rsp+1E0h] [rbp+E0h]
  _BYTE v96[152]; // [rsp+1E8h] [rbp+E8h] BYREF
  __int128 v97; // [rsp+280h] [rbp+180h]
  int v98; // [rsp+290h] [rbp+190h]
  __int64 v99; // [rsp+298h] [rbp+198h]
  int *v100; // [rsp+2A0h] [rbp+1A0h]
  __int64 v101; // [rsp+2A8h] [rbp+1A8h]
  __int64 v102; // [rsp+2B0h] [rbp+1B0h]
  void ***v103; // [rsp+2B8h] [rbp+1B8h]
  __int64 v104; // [rsp+2C0h] [rbp+1C0h]
  int v105; // [rsp+2C8h] [rbp+1C8h]
  int *v106; // [rsp+2D0h] [rbp+1D0h]
  char v107; // [rsp+2D8h] [rbp+1D8h]
  DXGI_ADAPTER_DESC1 v108; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v109[288]; // [rsp+420h] [rbp+320h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+598h] [rbp+498h]

  v89 = 0;
  v90 = 0;
  v94 = 0;
  v91 = 0;
  v92 = "DXGIAdapterCacheHealthActivity";
  v93 = 0;
  v95 = 0;
  v97 = 0;
  memset_0(v96, 0, sizeof(v96));
  v98 = 1;
  v99 = 0;
  v100 = &v89;
  v101 = 0;
  v102 = 0;
  v103 = &v88;
  v104 = 0;
  v105 = 0;
  v106 = &v91;
  v107 = 0;
  v88 = &DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity::`vftable';
  DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity::StartActivity((DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity *)&v88);
  AdapterCacheUpdate::AdapterCacheUpdate((AdapterCacheUpdate *)&Handle, a1);
  pAdapter = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  ppFactory = 0;
  v2 = CreateDXGIFactory1(&GUID_770aae78_f26f_4dba_a829_253c83d1b387, &ppFactory);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x369, v3, (const char *)(unsigned int)v2, pFeatureLevels);
  v4 = 0x7FFFFFFF;
  v69 = 0;
  v70 = 0x7FFFFFFF;
  v71 = 0;
  DedicatedVideoMemory = 0;
  v74 = 0;
  *(_DWORD *)v72 = 0;
  v63 = 0;
  v64 = 0;
  v6 = 0;
  v57 = 0;
  v7 = 0;
  v8 = 0;
  while ( 1 )
  {
    v9 = ppFactory;
    v10 = *(unsigned int (__fastcall **)(void *, _QWORD, IDXGIAdapter **))(*(_QWORD *)ppFactory + 96LL);
    v11 = pAdapter;
    pAdapter = 0;
    if ( v11 )
      ((void (__fastcall *)(IDXGIAdapter *))v11->lpVtbl->Release)(v11);
    if ( v10(v9, v7, &pAdapter) == -2005270526 )
      break;
    memset_0(&v108, 0, sizeof(v108));
    ((void (__fastcall *)(IDXGIAdapter *, DXGI_ADAPTER_DESC1 *))pAdapter->lpVtbl[1].QueryInterface)(pAdapter, &v108);
    hkey[0] = 0;
    v85 = 0;
    v86 = 0;
    v87 = 7;
    LOWORD(v85) = 0;
    v58 = 0;
    if ( AdapterCacheUpdate::GetAdapterKey(
           (AdapterCacheUpdate *)&Handle,
           &v108,
           (struct CachedAdapterInformation *)hkey,
           &v58,
           &v59,
           &v60,
           &v61,
           &v62) < 0 )
      goto LABEL_51;
    AdapterCacheUpdate::AddDXGIAdapterInfo((AdapterCacheUpdate *)&Handle, hkey[0], &v108);
    if ( DedicatedVideoMemory < v108.DedicatedVideoMemory )
      DedicatedVideoMemory = v108.DedicatedVideoMemory;
    pvData = 0;
    v12 = v58;
    if ( v58 )
    {
      v13 = D3D11CreateDevice(pAdapter, D3D_DRIVER_TYPE_UNKNOWN, 0, 0, &::pFeatureLevels, 0xAu, 7u, 0, &pvData, 0) >= 0;
    }
    else
    {
      pcbData = 4;
      pdwType = 0;
      if ( RegGetValueW(hkey[0], 0, L"MaxD3D11FeatureLevel", 0xFFFFu, &pdwType, &pvData, &pcbData)
        || pdwType != 4
        || (v13 = 1, pcbData != 4) )
      {
        v13 = 0;
      }
    }
    if ( v13 )
    {
      if ( v12 )
      {
        pcbData = pvData;
        v14 = RegSetValueExW(hkey[0], L"MaxD3D11FeatureLevel", 0, 4u, (const BYTE *)&pcbData, 4u);
        if ( v14 )
          wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x152, v15, (const char *)v14, pFeatureLevels);
      }
      v6 = 1;
      if ( v108.VendorId == 5140 && v108.DeviceId - 140 <= 1 )
      {
        v74 = pvData;
      }
      else
      {
        v63 = 1;
        v16 = pvData;
        v17 = pvData;
        if ( v4 < pvData )
          v17 = v4;
        v4 = v17;
        if ( pvData < v69 )
          v16 = v69;
        v69 = v16;
      }
    }
    else
    {
      v6 = 1;
    }
    *(_QWORD *)Data = 0;
    if ( v12 )
    {
      v18 = 0;
      *(_QWORD *)Data = 0;
      if ( D3D12CreateDevice(
             (IUnknown *)pAdapter,
             D3D_FEATURE_LEVEL_11_0,
             &GUID_189819f1_1db6_4b57_be54_1821339b85f7,
             (void **)Data) >= 0 )
      {
        v76[0] = 10;
        v77 = 0;
        v76[1] = &::pFeatureLevels;
        v19 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *))(**(_QWORD **)Data + 104LL))(
                *(_QWORD *)Data,
                2,
                v76);
        if ( v19 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x3BC,
            v20,
            (const char *)(unsigned int)v19,
            pFeatureLevels);
        v8 = (int)v77;
        pcbData = v77;
        v21 = RegSetValueExW(hkey[0], L"MaxD3D12FeatureLevel", 0, 4u, (const BYTE *)&pcbData, 4u);
        if ( v21 )
          wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x152, v22, (const char *)v21, pFeatureLevels);
        v18 = 1;
        memset_0(v109, 0, sizeof(v109));
        if ( (*(int (__fastcall **)(_QWORD, __int64, _BYTE *, __int64))(**(_QWORD **)Data + 104LL))(
               *(_QWORD *)Data,
               61,
               v109,
               288) >= 0 )
          v57 |= AdapterCacheUpdate::AddShaderCacheInfo(
                   v23,
                   (struct CachedAdapterInformation *)hkey,
                   (const struct D3D12_FEATURE_DATA_SHADERCACHE_ABI_SUPPORT *)v109);
      }
      if ( !v18 )
        goto LABEL_47;
      goto LABEL_39;
    }
    pvData = 0;
    pdwType = 4;
    pcbData = 0;
    if ( !RegGetValueW(hkey[0], 0, L"MaxD3D12FeatureLevel", 0xFFFFu, &pcbData, &pvData, &pdwType)
      && pcbData == 4
      && pdwType == 4 )
    {
      v8 = pvData;
LABEL_39:
      if ( v108.VendorId == 5140 && v108.DeviceId - 140 <= 1 )
      {
        *(_DWORD *)v72 = v8;
      }
      else
      {
        v64 = 1;
        v24 = v8;
        if ( v70 < v8 )
          v24 = v70;
        v70 = v24;
        v25 = v8;
        if ( v8 < v71 )
          v25 = v71;
        v71 = v25;
      }
    }
LABEL_47:
    if ( *(_QWORD *)Data )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)Data + 16LL))(*(_QWORD *)Data);
    v26 = pAdapter;
    pAdapter = 0;
    if ( v26 )
      ((void (__fastcall *)(IDXGIAdapter *))v26->lpVtbl->Release)(v26);
LABEL_51:
    std::wstring::~wstring(&v85);
    if ( hkey[0] )
      RegCloseKey(hkey[0]);
    ++v7;
  }
  if ( !v6 )
  {
    v51 = wil::verify_hresult<long>();
    wil::details::in1diag3::Throw_Hr(retaddr, v52, v53, (const char *)v51, pFeatureLevels);
  }
  v27 = v59 + 1;
  if ( !v60 )
    v27 = v59;
  v28 = v27 + 1;
  if ( !v61 )
    v28 = v27;
  if ( v28 >= 2 || (v81 = 0, v62) )
    v81 = 1;
  v29 = *(__int64 **)v80[0];
  while ( v29 != (__int64 *)v80[0] )
  {
    v30 = *((_DWORD *)v29 + 24);
    if ( (v30 & 0x44) != 0 )
    {
      v31 = 0;
    }
    else
    {
      v31 = 77760000000000LL;
      if ( (v30 & 0x400) == 0 && v30 )
        v31 = 25920000000000LL;
    }
    if ( v80[2] - v29[11] >= v31 )
    {
      v37 = (const WCHAR *)(v29 + 4);
      v38 = (HKEY)v29[8];
      if ( v38 )
      {
        LastError = GetLastError();
        RegCloseKey(v38);
        SetLastError(LastError);
      }
      v29[8] = 0;
      if ( (unsigned __int64)v29[7] > 7 )
        v37 = *(const WCHAR **)v37;
      RegDeleteTreeW(hKey, v37);
      v29 = *(__int64 **)std::_Tree<std::_Tmap_traits<std::wstring,CachedAdapterInformation,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CachedAdapterInformation>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CachedAdapterInformation>>>>,0>(
                           v80,
                           &pcbData,
                           v29);
    }
    else
    {
      *(_QWORD *)Data = 0;
      v32 = RegSetValueExW((HKEY)v29[8], L"AdapterLuid", 0, 0xBu, Data, 8u);
      if ( v32 )
        wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x152, v33, (const char *)v32, pFeatureLevelsa);
      v34 = (__int64 **)v29[2];
      if ( *((_BYTE *)v34 + 25) )
      {
        for ( i = (__int64 *)v29[1]; !*((_BYTE *)i + 25) && v29 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v29 = i;
        v29 = i;
      }
      else
      {
        v29 = (__int64 *)v29[2];
        for ( j = *v34; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v29 = j;
      }
    }
  }
  if ( v63 )
  {
    v40 = v69;
  }
  else
  {
    v4 = v74;
    v40 = v74;
  }
  if ( v64 )
  {
    v42 = v70;
    v41 = v71;
  }
  else
  {
    v41 = v72[0];
    v42 = *(_DWORD *)v72;
  }
  AdapterCacheUpdate::UpdateGlobalFeatureLevelInfo(
    (AdapterCacheUpdate *)&Handle,
    v4,
    v40,
    v42,
    v41,
    DedicatedVideoMemory);
  v44 = hKey;
  if ( hKey )
  {
    v45 = GetLastError();
    RegCloseKey(v44);
    SetLastError(v45);
  }
  hKey = 0;
  if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LOBYTE(v43) = 1;
    v46 = NtCommitTransaction(Handle, v43);
    if ( v46 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x342,
        v47,
        (const char *)(unsigned int)v46,
        pFeatureLevelsb);
    v48 = Handle;
    if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v49 = GetLastError();
      NtClose(v48);
      SetLastError(v49);
    }
    Handle = (HANDLE)-1LL;
  }
  if ( v81 )
  {
    refreshed = RefreshOneSettingsClientForDxDb();
    wil::details::in1diag3::Log_IfFailedWithExpected(
      retaddr,
      (void *)0x34B,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\adaptercache\\exe\\main.cpp",
      (const char *)refreshed,
      1,
      231);
  }
  if ( v57 )
    RtlPublishWnfStateData(WNF_DX_ADVANCED_SHADER_DELIVERY_CHANGE, 0, 0, 0, 0);
  wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&v88);
  if ( pAdapter )
    ((void (__fastcall *)(IDXGIAdapter *))pAdapter->lpVtbl->Release)(pAdapter);
  if ( ppFactory )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppFactory + 16LL))(ppFactory);
  std::wstring::~wstring(v83);
  std::vector<unsigned char>::~vector<unsigned char>(v82);
  std::_Tree<std::_Tmap_traits<std::wstring,CachedAdapterInformation,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CachedAdapterInformation>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CachedAdapterInformation,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CachedAdapterInformation>>,0>>(v80);
  if ( hKey )
    RegCloseKey(hKey);
  if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    NtClose(Handle);
  DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity::~DXGIAdapterCacheHealthActivity((DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity *)&v88);
}

```

## disassembly

```asm
0x14000e174  push    rbp
0x14000e176  push    rbx
0x14000e177  push    rsi
0x14000e178  push    rdi
0x14000e179  push    r12
0x14000e17b  push    r13
0x14000e17d  push    r14
0x14000e17f  push    r15
0x14000e181  lea     rbp, [rsp-458h]
0x14000e189  sub     rsp, 558h
0x14000e190  mov     rax, cs:__security_cookie
0x14000e197  xor     rax, rsp
0x14000e19a  mov     [rbp+490h+var_50], rax
0x14000e1a1  mov     bl, cl
0x14000e1a3  xor     esi, esi
0x14000e1a5  mov     [rbp+490h+var_3F8], esi
0x14000e1ab  mov     [rbp+490h+var_3F4], sil
0x14000e1b2  mov     [rbp+490h+var_3B8], sil
0x14000e1b9  mov     [rbp+490h+var_3D0], esi
0x14000e1bf  lea     rax, aDxgiadaptercac; "DXGIAdapterCacheHealthActivity"
0x14000e1c6  mov     [rbp+490h+var_3C8], rax
0x14000e1cd  mov     [rbp+490h+var_3C0], rsi
0x14000e1d4  mov     [rbp+490h+var_3B0], esi
0x14000e1da  xorps   xmm0, xmm0
0x14000e1dd  movdqa  [rbp+490h+var_310], xmm0
0x14000e1e5  xor     edx, edx; Val
0x14000e1e7  mov     r8d, 98h; Size
0x14000e1ed  lea     rcx, [rbp+490h+var_3A8]; void *
0x14000e1f4  call    memset_0
0x14000e1f9  mov     [rbp+490h+var_300], 1
0x14000e203  xor     eax, eax
0x14000e205  mov     [rbp+490h+var_2F8], rax
0x14000e20c  lea     rax, [rbp+490h+var_3F8]
0x14000e213  mov     [rbp+490h+var_2F0], rax
0x14000e21a  mov     [rbp+490h+var_2E8], rsi
0x14000e221  mov     [rbp+490h+var_2E0], rsi
0x14000e228  lea     rax, [rbp+490h+var_400]
0x14000e22f  mov     [rbp+490h+var_2D8], rax
0x14000e236  mov     [rbp+490h+var_2D0], rsi
0x14000e23d  mov     [rbp+490h+var_2C8], esi
0x14000e243  lea     rax, [rbp+490h+var_3D0]
0x14000e24a  mov     [rbp+490h+var_2C0], rax
0x14000e251  mov     [rbp+490h+var_2B8], sil
0x14000e258  lea     rax, ??_7DXGIAdapterCacheHealthActivity@DXGIAdapterCacheTelemetry@@6B@; const DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity::`vftable'
0x14000e25f  mov     [rbp+490h+var_400], rax
0x14000e266  lea     rcx, [rbp+490h+var_400]; this
0x14000e26d  call    ?StartActivity@DXGIAdapterCacheHealthActivity@DXGIAdapterCacheTelemetry@@QEAAXXZ; DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity::StartActivity(void)
0x14000e272  nop
0x14000e273  mov     dl, bl; bool
0x14000e275  lea     rcx, [rbp+490h+Handle]; this
0x14000e279  call    ??0AdapterCacheUpdate@@QEAA@_N@Z; AdapterCacheUpdate::AdapterCacheUpdate(bool)
0x14000e27e  nop
0x14000e27f  mov     [rsp+590h+pAdapter], rsi
0x14000e284  mov     [rsp+590h+var_53E], sil
0x14000e289  mov     [rsp+590h+var_53D], sil
0x14000e28e  mov     [rsp+590h+var_53C], sil
0x14000e293  mov     [rsp+590h+var_53B], sil
0x14000e298  mov     [rbp+490h+ppFactory], rsi
0x14000e29c  lea     rdx, [rbp+490h+ppFactory]; ppFactory
0x14000e2a0  lea     rcx, _GUID_770aae78_f26f_4dba_a829_253c83d1b387; riid
0x14000e2a7  call    cs:__imp_CreateDXGIFactory1
0x14000e2ad  mov     rcx, [rbp+498h]; this
0x14000e2b4  test    eax, eax
0x14000e2b6  js      loc_14000EA9A
0x14000e2bc  mov     r12d, 7FFFFFFFh
0x14000e2c2  mov     [rsp+590h+var_520], esi
0x14000e2c6  mov     [rsp+590h+var_51C], r12d
0x14000e2cb  mov     [rsp+590h+var_518], esi
0x14000e2cf  mov     r15d, esi
0x14000e2d2  mov     [rbp+490h+var_508], esi
0x14000e2d5  mov     dword ptr [rsp+590h+var_514], esi
0x14000e2d9  mov     [rsp+590h+var_53A], sil
0x14000e2de  mov     [rsp+590h+var_539], sil
0x14000e2e3  mov     dil, sil
0x14000e2e6  mov     [rsp+590h+var_540], sil
0x14000e2eb  mov     r13d, esi
0x14000e2ee  mov     esi, dword ptr [rsp+590h+var_514]
0x14000e2f2  mov     rbx, [rbp+490h+ppFactory]
0x14000e2f6  mov     rax, [rbx]
0x14000e2f9  mov     r14, [rax+60h]
0x14000e2fd  mov     rcx, [rsp+590h+pAdapter]
0x14000e302  mov     [rsp+590h+pAdapter], 0
0x14000e30b  test    rcx, rcx
0x14000e30e  jz      short loc_14000E31D
0x14000e310  mov     rax, [rcx]
0x14000e313  mov     rax, [rax+10h]
0x14000e317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e31c  nop
0x14000e31d  lea     r8, [rsp+590h+pAdapter]
0x14000e322  mov     edx, r13d
0x14000e325  mov     rcx, rbx
0x14000e328  mov     rax, r14
0x14000e32b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e330  mov     ecx, 887A0002h
0x14000e335  cmp     eax, ecx
0x14000e337  jz      loc_14000E755
0x14000e33d  xor     edx, edx; Val
0x14000e33f  mov     r8d, 138h; Size
0x14000e345  lea     rcx, [rbp+490h+var_2B0]; void *
0x14000e34c  call    memset_0
0x14000e351  mov     rcx, [rsp+590h+pAdapter]
0x14000e356  mov     rax, [rcx]
0x14000e359  lea     rdx, [rbp+490h+var_2B0]
0x14000e360  mov     rax, [rax+50h]
0x14000e364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e369  xor     r14d, r14d
0x14000e36c  mov     [rbp+490h+hkey], r14
0x14000e370  xorps   xmm0, xmm0
0x14000e373  movups  [rbp+490h+var_448], xmm0
0x14000e377  mov     [rbp+490h+var_438], r14
0x14000e37b  mov     [rbp+490h+var_430], 7
0x14000e383  mov     word ptr [rbp+490h+var_448], r14w
0x14000e388  mov     [rsp+590h+var_53F], r14b
0x14000e38d  lea     rax, [rsp+590h+var_53B]
0x14000e392  mov     [rsp+590h+ppDevice], rax; bool *
0x14000e397  lea     rax, [rsp+590h+var_53C]
0x14000e39c  mov     qword ptr [rsp+590h+SDKVersion], rax; bool *
0x14000e3a1  lea     rax, [rsp+590h+var_53D]
0x14000e3a6  mov     qword ptr [rsp+590h+FeatureLevels], rax; bool *
0x14000e3ab  lea     rax, [rsp+590h+var_53E]
0x14000e3b0  mov     [rsp+590h+pFeatureLevels], rax; bool *
0x14000e3b5  lea     r9, [rsp+590h+var_53F]; bool *
0x14000e3ba  lea     r8, [rbp+490h+hkey]; struct CachedAdapterInformation *
0x14000e3be  lea     rdx, [rbp+490h+var_2B0]; struct DXGI_ADAPTER_DESC1 *
0x14000e3c5  lea     rcx, [rbp+490h+Handle]; this
0x14000e3c9  call    ?GetAdapterKey@AdapterCacheUpdate@@QEAAJAEBUDXGI_ADAPTER_DESC1@@AEAUCachedAdapterInformation@@AEA_N2222@Z; AdapterCacheUpdate::GetAdapterKey(DXGI_ADAPTER_DESC1 const &,CachedAdapterInformation &,bool &,bool &,bool &,bool &,bool &)
0x14000e3ce  test    eax, eax
0x14000e3d0  js      loc_14000E735
0x14000e3d6  lea     r8, [rbp+490h+var_2B0]; struct DXGI_ADAPTER_DESC1 *
0x14000e3dd  mov     rdx, [rbp+490h+hkey]; HKEY
0x14000e3e1  lea     rcx, [rbp+490h+Handle]; this
0x14000e3e5  call    ?AddDXGIAdapterInfo@AdapterCacheUpdate@@QEAAXPEAUHKEY__@@AEBUDXGI_ADAPTER_DESC1@@@Z; AdapterCacheUpdate::AddDXGIAdapterInfo(HKEY__ *,DXGI_ADAPTER_DESC1 const &)
0x14000e3ea  cmp     r15, [rbp+490h+var_2B0.DedicatedVideoMemory]
0x14000e3f1  cmovb   r15, [rbp+490h+var_2B0.DedicatedVideoMemory]
0x14000e3f9  mov     [rsp+590h+pvData], r14d
0x14000e3fe  mov     bl, [rsp+590h+var_53F]
0x14000e402  test    bl, bl
0x14000e404  jz      short loc_14000E454
0x14000e406  mov     [rsp+590h+ppImmediateContext], r14; ppImmediateContext
0x14000e40b  lea     rax, [rsp+590h+pvData]
0x14000e410  mov     [rsp+590h+pFeatureLevel], rax; pFeatureLevel
0x14000e415  mov     [rsp+590h+ppDevice], r14; ppDevice
0x14000e41a  mov     [rsp+590h+SDKVersion], 7; SDKVersion
0x14000e422  mov     [rsp+590h+FeatureLevels], 0Ah; FeatureLevels
0x14000e42a  lea     rax, pFeatureLevels
0x14000e431  mov     [rsp+590h+pFeatureLevels], rax; pFeatureLevels
0x14000e436  xor     r9d, r9d; Flags
0x14000e439  xor     r8d, r8d; Software
0x14000e43c  xor     edx, edx; DriverType
0x14000e43e  mov     rcx, [rsp+590h+pAdapter]; pAdapter
0x14000e443  call    cs:__imp_D3D11CreateDevice
0x14000e449  not     eax
0x14000e44b  shr     eax, 1Fh
0x14000e44e  lea     edi, [r14+4]
0x14000e452  jmp     short loc_14000E4AF
0x14000e454  mov     edi, 4
0x14000e459  mov     [rsp+590h+pcbData], edi
0x14000e45d  mov     [rsp+590h+pdwType], r14d
0x14000e462  lea     rax, [rsp+590h+pcbData]
0x14000e467  mov     qword ptr [rsp+590h+SDKVersion], rax; pcbData
0x14000e46c  lea     rax, [rsp+590h+pvData]
0x14000e471  mov     qword ptr [rsp+590h+FeatureLevels], rax; pvData
0x14000e476  lea     rax, [rsp+590h+pdwType]
0x14000e47b  mov     [rsp+590h+pFeatureLevels], rax; int
0x14000e480  mov     r9d, 0FFFFh; dwFlags
0x14000e486  lea     r8, aMaxd3d11featur; "MaxD3D11FeatureLevel"
0x14000e48d  xor     edx, edx; lpSubKey
0x14000e48f  mov     rcx, [rbp+490h+hkey]; hkey
0x14000e493  call    cs:__imp_RegGetValueW
0x14000e499  test    eax, eax
0x14000e49b  jnz     short loc_14000E4AC
0x14000e49d  cmp     [rsp+590h+pdwType], edi
0x14000e4a1  jnz     short loc_14000E4AC
0x14000e4a3  cmp     [rsp+590h+pcbData], edi
0x14000e4a7  lea     eax, [rdi-3]
0x14000e4aa  jz      short loc_14000E4AF
0x14000e4ac  mov     eax, r14d
0x14000e4af  test    eax, eax
0x14000e4b1  jz      loc_14000E544
0x14000e4b7  test    bl, bl
0x14000e4b9  jz      short loc_14000E4F7
0x14000e4bb  mov     eax, [rsp+590h+pvData]
0x14000e4bf  mov     [rsp+590h+pcbData], eax
0x14000e4c3  mov     [rsp+590h+FeatureLevels], edi; cbData
0x14000e4c7  lea     rax, [rsp+590h+pcbData]
0x14000e4cc  mov     [rsp+590h+pFeatureLevels], rax; unsigned int
0x14000e4d1  mov     r9d, edi; dwType
0x14000e4d4  xor     r8d, r8d; Reserved
0x14000e4d7  lea     rdx, aMaxd3d11featur; "MaxD3D11FeatureLevel"
0x14000e4de  mov     rcx, [rbp+490h+hkey]; hKey
0x14000e4e2  call    cs:__imp_RegSetValueExW
0x14000e4e8  mov     rcx, [rbp+498h]; this
0x14000e4ef  test    eax, eax
0x14000e4f1  jnz     loc_14000EAA8
0x14000e4f7  mov     edi, 1
0x14000e4fc  cmp     [rbp+490h+var_2B0.VendorId], 1414h
0x14000e506  jnz     short loc_14000E520
0x14000e508  mov     eax, [rbp+490h+var_2B0.DeviceId]
0x14000e50e  add     eax, 0FFFFFF74h
0x14000e513  cmp     eax, edi
0x14000e515  ja      short loc_14000E520
0x14000e517  mov     eax, [rsp+590h+pvData]
0x14000e51b  mov     [rbp+490h+var_508], eax
0x14000e51e  jmp     short loc_14000E549
0x14000e520  mov     [rsp+590h+var_53A], dil
0x14000e525  mov     ecx, [rsp+590h+pvData]
0x14000e529  mov     eax, ecx
0x14000e52b  cmp     r12d, ecx
0x14000e52e  cmovl   eax, r12d
0x14000e532  mov     r12d, eax
0x14000e535  cmp     ecx, [rsp+590h+var_520]
0x14000e539  cmovl   ecx, [rsp+590h+var_520]
0x14000e53e  mov     [rsp+590h+var_520], ecx
0x14000e542  jmp     short loc_14000E549
0x14000e544  mov     edi, 1
0x14000e549  mov     qword ptr [rbp+490h+Data], r14
0x14000e54d  test    bl, bl
0x14000e54f  jz      loc_14000E660
0x14000e555  mov     bl, r14b
0x14000e558  mov     qword ptr [rbp+490h+Data], r14
0x14000e55c  lea     r9, [rbp+490h+Data]; ppDevice
0x14000e560  lea     r8, _GUID_189819f1_1db6_4b57_be54_1821339b85f7; riid
0x14000e567  mov     edx, 0B000h; MinimumFeatureLevel
0x14000e56c  mov     rcx, [rsp+590h+pAdapter]; pAdapter
0x14000e571  call    cs:__imp_D3D12CreateDevice
0x14000e577  test    eax, eax
0x14000e579  js      loc_14000E656
0x14000e57f  mov     [rbp+490h+var_4F8], 0Ah
0x14000e587  mov     [rbp+490h+var_4E8], r14
0x14000e58b  lea     rax, pFeatureLevels
0x14000e592  mov     [rbp+490h+var_4F0], rax
0x14000e596  mov     rcx, qword ptr [rbp+490h+Data]
0x14000e59a  mov     rax, [rcx]
0x14000e59d  mov     r9d, 18h
0x14000e5a3  lea     r8, [rbp+490h+var_4F8]
0x14000e5a7  lea     edx, [r9-16h]
0x14000e5ab  mov     rax, [rax+68h]
0x14000e5af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e5b4  mov     rcx, [rbp+498h]; this
0x14000e5bb  test    eax, eax
0x14000e5bd  js      loc_14000EAC4
0x14000e5c3  mov     esi, dword ptr [rbp+490h+var_4E8]
0x14000e5c6  mov     [rsp+590h+pcbData], esi
0x14000e5ca  mov     [rsp+590h+FeatureLevels], 4; cbData
0x14000e5d2  lea     rax, [rsp+590h+pcbData]
0x14000e5d7  mov     [rsp+590h+pFeatureLevels], rax; unsigned int
0x14000e5dc  mov     r9d, 4; dwType
0x14000e5e2  xor     r8d, r8d; Reserved
0x14000e5e5  lea     rdx, aMaxd3d12featur; "MaxD3D12FeatureLevel"
0x14000e5ec  mov     rcx, [rbp+490h+hkey]; hKey
0x14000e5f0  call    cs:__imp_RegSetValueExW
0x14000e5f6  mov     rcx, [rbp+498h]; this
0x14000e5fd  test    eax, eax
0x14000e5ff  jnz     loc_14000EAB6
0x14000e605  mov     bl, dil
0x14000e608  xor     edx, edx; Val
0x14000e60a  mov     r8d, 120h; Size
0x14000e610  lea     rcx, [rbp+490h+var_170]; void *
0x14000e617  call    memset_0
0x14000e61c  mov     rcx, qword ptr [rbp+490h+Data]
0x14000e620  mov     rax, [rcx]
0x14000e623  mov     r9d, 120h
0x14000e629  lea     r8, [rbp+490h+var_170]
0x14000e630  mov     edx, 3Dh ; '='
0x14000e635  mov     rax, [rax+68h]
0x14000e639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e63e  test    eax, eax
0x14000e640  js      short loc_14000E656
0x14000e642  lea     r8, [rbp+490h+var_170]; struct D3D12_FEATURE_DATA_SHADERCACHE_ABI_SUPPORT *
0x14000e649  lea     rdx, [rbp+490h+hkey]; struct CachedAdapterInformation *
0x14000e64d  call    ?AddShaderCacheInfo@AdapterCacheUpdate@@QEAA_NAEAUCachedAdapterInformation@@AEBUD3D12_FEATURE_DATA_SHADERCACHE_ABI_SUPPORT@@@Z; AdapterCacheUpdate::AddShaderCacheInfo(CachedAdapterInformation &,D3D12_FEATURE_DATA_SHADERCACHE_ABI_SUPPORT const &)
0x14000e652  or      [rsp+590h+var_540], al
0x14000e656  test    bl, bl
0x14000e658  jz      loc_14000E703
0x14000e65e  jmp     short loc_14000E6BF
0x14000e660  mov     [rsp+590h+pvData], r14d
0x14000e665  mov     [rsp+590h+pdwType], 4
0x14000e66d  mov     [rsp+590h+pcbData], r14d
0x14000e672  lea     rax, [rsp+590h+pdwType]
0x14000e677  mov     qword ptr [rsp+590h+SDKVersion], rax; pcbData
0x14000e67c  lea     rax, [rsp+590h+pvData]
0x14000e681  mov     qword ptr [rsp+590h+FeatureLevels], rax; pvData
0x14000e686  lea     rax, [rsp+590h+pcbData]
0x14000e68b  mov     [rsp+590h+pFeatureLevels], rax; pdwType
0x14000e690  mov     r9d, 0FFFFh; dwFlags
0x14000e696  lea     r8, aMaxd3d12featur; "MaxD3D12FeatureLevel"
0x14000e69d  xor     edx, edx; lpSubKey
0x14000e69f  mov     rcx, [rbp+490h+hkey]; hkey
0x14000e6a3  call    cs:__imp_RegGetValueW
0x14000e6a9  test    eax, eax
0x14000e6ab  jnz     short loc_14000E703
0x14000e6ad  cmp     [rsp+590h+pcbData], 4
0x14000e6b2  jnz     short loc_14000E703
0x14000e6b4  cmp     [rsp+590h+pdwType], 4
0x14000e6b9  jnz     short loc_14000E703
0x14000e6bb  mov     esi, [rsp+590h+pvData]
0x14000e6bf  cmp     [rbp+490h+var_2B0.VendorId], 1414h
0x14000e6c9  jnz     short loc_14000E6E0
0x14000e6cb  mov     eax, [rbp+490h+var_2B0.DeviceId]
0x14000e6d1  add     eax, 0FFFFFF74h
  ... truncated ...
```
