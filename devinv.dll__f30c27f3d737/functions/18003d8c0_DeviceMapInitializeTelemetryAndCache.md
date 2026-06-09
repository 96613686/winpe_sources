# DeviceMapInitializeTelemetryAndCache

- ea: `0x18003d8c0`
- end: `0x18003e280`
- name: `DeviceMapInitializeTelemetryAndCache`
- size: `2496`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a500`
- `0x180031850`
- `0x180031e30`

## callees

- `0x180005e40`
- `0x180006270`
- `0x180006d02`
- `0x180006ec4`
- `0x180007014`
- `0x18000eb24`
- `0x180012078`
- `0x180017600`
- `0x180018f60`
- `0x18001f0e8`
- `0x180023734`
- `0x18002d2d0`
- `0x18003d8c0`
- `0x180048990`
- `0x18004af5c`
- `0x18004d314`
- `0x180057e1c`
- `0x18006041c`
- `0x180066c10`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e255`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e255`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d8f4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d8f4`

## string_xrefs

- `0x18003da3a`: `InventoryDeviceMediaClass`
- `0x18003ddd8`: `InventoryDeviceMediaClass`
- `0x18003e174`: `DeviceMapInitializeTelemetryAndCache`
- `0x18003e19c`: `DeviceMapInitializeTelemetryAndCache`
- `0x18003e1fd`: `DeviceMapInitializeTelemetryAndCache`
- `0x18003e161`: `TelCacheProvider::Initialize failed [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall DeviceMapInitializeTelemetryAndCache(char a1)
{
  unsigned int v1; // esi
  int v2; // r12d
  CDeviceInventoryItem *v3; // rax
  CDeviceInventoryItem *v4; // rcx
  CDeviceContainer *v5; // rbx
  CDriver *v6; // rbx
  CMediaClassItem *v7; // rax
  CMediaClassItem *v8; // rcx
  CDeviceInterface *v9; // rax
  CDeviceInterface *v10; // rcx
  _QWORD *v11; // rbx
  CDriverPackage *v12; // rcx
  char *v13; // rax
  char *v14; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  CDeviceInventoryItem *v17; // rax
  CDeviceInventoryItem *v18; // rcx
  CDeviceContainer *v19; // rbx
  CDriver *v20; // rbx
  CMediaClassItem *v21; // rax
  CMediaClassItem *v22; // rcx
  CDriverPackageDetailed *v23; // rax
  CDriverPackageDetailed *v24; // rax
  CDeviceInterface *v25; // rax
  CDeviceInterface *v26; // rcx
  _QWORD *v27; // rbx
  CDriverPackage *v28; // rcx
  char *v29; // rax
  char *v30; // rax
  _QWORD *v31; // rax
  __int16 v32; // r14
  int v33; // eax
  FILE *v34; // rax
  FILE *v35; // rax
  FILE *v36; // rax
  unsigned __int16 i; // bx
  void (__fastcall ***v38)(_QWORD, __int64); // rcx
  FILE *v40; // rax
  FILE *v41; // rax
  FILE *v42; // rax
  CDriverPackage *v43; // [rsp+40h] [rbp-178h]
  CDriverPackage *v44; // [rsp+40h] [rbp-178h]
  const wchar_t *v46; // [rsp+50h] [rbp-168h]
  TelCacheProvider *v47; // [rsp+58h] [rbp-160h] BYREF
  CDeviceInventoryItem *v48; // [rsp+60h] [rbp-158h]
  const wchar_t *v49; // [rsp+68h] [rbp-150h]
  __int64 *v50; // [rsp+70h] [rbp-148h]
  CDeviceContainer *v51; // [rsp+78h] [rbp-140h]
  const wchar_t *v52; // [rsp+80h] [rbp-138h]
  __int64 *v53; // [rsp+88h] [rbp-130h]
  CDriver *v54; // [rsp+90h] [rbp-128h]
  const wchar_t *v55; // [rsp+98h] [rbp-120h]
  __int64 *v56; // [rsp+A0h] [rbp-118h]
  CMediaClassItem *v57; // [rsp+A8h] [rbp-110h]
  const wchar_t *v58; // [rsp+B0h] [rbp-108h]
  __int64 *v59; // [rsp+B8h] [rbp-100h]
  CDeviceInterface *v60; // [rsp+C0h] [rbp-F8h]
  const wchar_t *v61; // [rsp+C8h] [rbp-F0h]
  __int64 *v62; // [rsp+D0h] [rbp-E8h]
  CDeviceInterface *v63; // [rsp+D8h] [rbp-E0h]
  const wchar_t *v64; // [rsp+E0h] [rbp-D8h]
  __int64 *v65; // [rsp+E8h] [rbp-D0h]
  CDriverPackage *v66; // [rsp+F0h] [rbp-C8h]
  const wchar_t *v67; // [rsp+F8h] [rbp-C0h]
  __int64 *v68; // [rsp+100h] [rbp-B8h]
  CDriverPackage *v69; // [rsp+108h] [rbp-B0h]
  const wchar_t *v70; // [rsp+110h] [rbp-A8h]
  __int64 *v71; // [rsp+118h] [rbp-A0h]
  char *v72; // [rsp+120h] [rbp-98h]
  const wchar_t *v73; // [rsp+128h] [rbp-90h]
  __int64 *v74; // [rsp+130h] [rbp-88h]
  char *v75; // [rsp+138h] [rbp-80h]
  const wchar_t *v76; // [rsp+140h] [rbp-78h]
  __int64 *v77; // [rsp+148h] [rbp-70h]
  _QWORD *v78; // [rsp+150h] [rbp-68h]
  const wchar_t *v79; // [rsp+158h] [rbp-60h]
  __int64 *v80; // [rsp+160h] [rbp-58h]
  _QWORD *v81; // [rsp+168h] [rbp-50h]

  v1 = 0;
  AcquireSRWLockExclusive(&stru_180156ED0);
  if ( !byte_180156ECC )
  {
    byte_180156ECC = 1;
    v46 = 0;
    memset_0(&v47, 0, 0x118u);
    v2 = 12;
    try
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
      {
        v3 = (CDeviceInventoryItem *)operator new(0x4B8u);
        v4 = CDeviceInventoryItem::CDeviceInventoryItem(v3);
        v46 = L"InventoryDevicePnp";
        v47 = (TelCacheProvider *)g_DeviceStore;
        v48 = v4;
        v5 = (CDeviceContainer *)operator new(0x2D8u);
        CDeviceContainer::CDeviceContainer(v5, 0);
        *(_QWORD *)v5 = &CDeviceContainer::`vftable'{for `IAmiInventoryTelemetryItem'};
        *((_QWORD *)v5 + 1) = &CDeviceContainer::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
        v49 = L"InventoryDeviceContainer";
        v50 = g_DeviceContainerStore;
        v51 = v5;
        v6 = (CDriver *)operator new(0x2E0u);
        CDriver::CDriver(v6, 0);
        *(_QWORD *)v6 = &CDriver::`vftable'{for `IAmiInventoryTelemetryItem'};
        *((_QWORD *)v6 + 1) = &CDriver::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
        v52 = L"InventoryDriverBinary";
        v53 = g_DriverBinaryStore;
        v54 = v6;
        v7 = (CMediaClassItem *)operator new(0xA8u);
        v8 = CMediaClassItem::CMediaClassItem(v7);
        v55 = L"InventoryDeviceMediaClass";
        v56 = g_MediaClassStore;
        v57 = v8;
        v9 = (CDeviceInterface *)operator new(0x678u);
        v10 = CDeviceInterface::CDeviceInterface(v9);
        v58 = L"InventoryDeviceInterface";
        v59 = g_DeviceInterfaceStore;
        v60 = v10;
        v11 = operator new(0x38u);
        *v11 = &CUsbHubClass::`vftable'{for `IAmiInventoryTelemetryItem'};
        v11[1] = &CUsbHubClass::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
        *((_OWORD *)v11 + 1) = 0;
        v11[4] = 0;
        v11[5] = 0;
        std::wstring::_Construct<1,unsigned short const *>(v11 + 2, L"DeviceUsbHubClass", 17);
        v11[6] = 0;
        v61 = L"InventoryDeviceUsbHubClass";
        v62 = g_DeviceUsbHubStore;
        v63 = (CDeviceInterface *)v11;
        v43 = (CDriverPackage *)operator new(0x2B0u);
        v12 = CDriverPackage::CDriverPackage(v43);
        v64 = L"InventoryDriverPackage";
        v65 = g_DriverPackageStore;
        v66 = v12;
        v13 = (char *)operator new(0x58u);
        *(_QWORD *)v13 = &AcpiPhatVersionElement::`vftable'{for `IAmiInventoryTelemetryItem'};
        *((_QWORD *)v13 + 1) = &AcpiPhatVersionElement::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
        *((_OWORD *)v13 + 1) = 0;
        *((_QWORD *)v13 + 4) = 0;
        *((_QWORD *)v13 + 5) = 7;
        *((_WORD *)v13 + 8) = 0;
        *((_QWORD *)v13 + 6) = 0;
        *(_OWORD *)(v13 + 56) = 0;
        *((_QWORD *)v13 + 9) = 0;
        *((_QWORD *)v13 + 10) = 7;
        *((_WORD *)v13 + 28) = 0;
        v67 = L"InventoryAcpiPhatVersionElement";
        v68 = g_AcpiPhatVersionElementStore;
        v69 = (CDriverPackage *)v13;
        v14 = (char *)operator new(0x38u);
        *(_DWORD *)(v14 + 51) = 0;
        v14[55] = 0;
        *(_QWORD *)v14 = &AcpiPhatHealthDataRecord::`vftable'{for `IAmiInventoryTelemetryItem'};
        *((_QWORD *)v14 + 1) = &AcpiPhatHealthDataRecord::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
        *((_OWORD *)v14 + 1) = 0;
        *((_QWORD *)v14 + 4) = 0;
        *((_QWORD *)v14 + 5) = 7;
        *((_WORD *)v14 + 8) = 0;
        *((_WORD *)v14 + 24) = 0;
        v14[50] = 0;
        v70 = L"InventoryAcpiPhatHealthRecord";
        v71 = g_AcpiPhatHealthRecordStore;
        v72 = v14;
        v15 = operator new(0x70u);
        *v15 = &SensorDevice::`vftable'{for `IAmiInventoryTelemetryItem'};
        v15[1] = &PciDevice::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
        *((_OWORD *)v15 + 1) = 0;
        v15[4] = 0;
        v15[5] = 7;
        *((_WORD *)v15 + 8) = 0;
        *((_OWORD *)v15 + 3) = 0;
        v15[8] = 0;
        v15[9] = 7;
        *((_WORD *)v15 + 24) = 0;
        *((_OWORD *)v15 + 5) = 0;
        v15[12] = 0;
        v15[13] = 7;
        *((_WORD *)v15 + 40) = 0;
        v73 = L"InventoryDeviceSensor";
        v74 = g_SensorDeviceStore;
        v75 = (char *)v15;
        v16 = operator new(0x70u);
        *v16 = &PciDevice::`vftable'{for `IAmiInventoryTelemetryItem'};
        v16[1] = &PciDevice::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
        v76 = L"InventoryDevicePci";
        v77 = g_PciDeviceStore;
        v78 = v16;
        v2 = 11;
      }
      else
      {
        v17 = (CDeviceInventoryItem *)operator new(0x4B8u);
        v18 = CDeviceInventoryItem::CDeviceInventoryItem(v17);
        v46 = L"InventoryDevicePnp";
        v47 = (TelCacheProvider *)g_DeviceStore;
        v48 = v18;
        v19 = (CDeviceContainer *)operator new(0x2D8u);
        CDeviceContainer::CDeviceContainer(v19, 0);
        *(_QWORD *)v19 = &CDeviceContainer::`vftable'{for `IAmiInventoryTelemetryItem'};
        *((_QWORD *)v19 + 1) = &CDeviceContainer::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
        v49 = L"InventoryDeviceContainer";
        v50 = g_DeviceContainerStore;
        v51 = v19;
        v20 = (CDriver *)operator new(0x2E0u);
        CDriver::CDriver(v20, 0);
        *(_QWORD *)v20 = &CDriver::`vftable'{for `IAmiInventoryTelemetryItem'};
        *((_QWORD *)v20 + 1) = &CDriver::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
        v52 = L"InventoryDriverBinary";
        v53 = g_DriverBinaryStore;
        v54 = v20;
        v21 = (CMediaClassItem *)operator new(0xA8u);
        v22 = CMediaClassItem::CMediaClassItem(v21);
        v55 = L"InventoryDeviceMediaClass";
        v56 = g_MediaClassStore;
        v57 = v22;
        v23 = (CDriverPackageDetailed *)operator new(0x268u);
        v24 = CDriverPackageDetailed::CDriverPackageDetailed(v23);
        v58 = L"DriverPackageExtended";
        v59 = g_DetailedDriverStore;
        v60 = v24;
        v25 = (CDeviceInterface *)operator new(0x678u);
        v26 = CDeviceInterface::CDeviceInterface(v25);
        v61 = L"InventoryDeviceInterface";
        v62 = g_DeviceInterfaceStore;
        v63 = v26;
        v27 = operator new(0x38u);
        *v27 = &CUsbHubClass::`vftable'{for `IAmiInventoryTelemetryItem'};
        v27[1] = &CUsbHubClass::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
        *((_OWORD *)v27 + 1) = 0;
        v27[4] = 0;
        v27[5] = 0;
        std::wstring::_Construct<1,unsigned short const *>(v27 + 2, L"DeviceUsbHubClass", 17);
        v27[6] = 0;
        v64 = L"InventoryDeviceUsbHubClass";
        v65 = g_DeviceUsbHubStore;
        v66 = (CDriverPackage *)v27;
        v44 = (CDriverPackage *)operator new(0x2B0u);
        v28 = CDriverPackage::CDriverPackage(v44);
        v67 = L"InventoryDriverPackage";
        v68 = g_DriverPackageStore;
        v69 = v28;
        v29 = (char *)operator new(0x58u);
        *(_QWORD *)v29 = &AcpiPhatVersionElement::`vftable'{for `IAmiInventoryTelemetryItem'};
        *((_QWORD *)v29 + 1) = &AcpiPhatVersionElement::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
        *((_OWORD *)v29 + 1) = 0;
        *((_QWORD *)v29 + 4) = 0;
        *((_QWORD *)v29 + 5) = 7;
        *((_WORD *)v29 + 8) = 0;
        *((_QWORD *)v29 + 6) = 0;
        *(_OWORD *)(v29 + 56) = 0;
        *((_QWORD *)v29 + 9) = 0;
        *((_QWORD *)v29 + 10) = 7;
        *((_WORD *)v29 + 28) = 0;
        v70 = L"InventoryAcpiPhatVersionElement";
        v71 = g_AcpiPhatVersionElementStore;
        v72 = v29;
        v30 = (char *)operator new(0x38u);
        *(_DWORD *)(v30 + 51) = 0;
        v30[55] = 0;
        *(_QWORD *)v30 = &AcpiPhatHealthDataRecord::`vftable'{for `IAmiInventoryTelemetryItem'};
        *((_QWORD *)v30 + 1) = &AcpiPhatHealthDataRecord::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
        *((_OWORD *)v30 + 1) = 0;
        *((_QWORD *)v30 + 4) = 0;
        *((_QWORD *)v30 + 5) = 7;
        *((_WORD *)v30 + 8) = 0;
        *((_WORD *)v30 + 24) = 0;
        v30[50] = 0;
        v73 = L"InventoryAcpiPhatHealthRecord";
        v74 = g_AcpiPhatHealthRecordStore;
        v75 = v30;
        v31 = operator new(0x70u);
        *v31 = &SensorDevice::`vftable'{for `IAmiInventoryTelemetryItem'};
        v31[1] = &PciDevice::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
        *((_OWORD *)v31 + 1) = 0;
        v31[4] = 0;
        v31[5] = 7;
        *((_WORD *)v31 + 8) = 0;
        *((_OWORD *)v31 + 3) = 0;
        v31[8] = 0;
        v31[9] = 7;
        *((_WORD *)v31 + 24) = 0;
        *((_OWORD *)v31 + 5) = 0;
        v31[12] = 0;
        v31[13] = 7;
        *((_WORD *)v31 + 40) = 0;
        v76 = L"InventoryDeviceSensor";
        v77 = g_SensorDeviceStore;
        v78 = v31;
        v16 = operator new(0x70u);
        *v16 = &PciDevice::`vftable'{for `IAmiInventoryTelemetryItem'};
        v16[1] = &PciDevice::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
        v79 = L"InventoryDevicePci";
        v80 = g_PciDeviceStore;
        v81 = v16;
      }
      *((_OWORD *)v16 + 1) = 0;
      v16[4] = 0;
      v16[5] = 7;
      *((_WORD *)v16 + 8) = 0;
      *((_OWORD *)v16 + 3) = 0;
      v16[8] = 0;
      v16[9] = 7;
      *((_WORD *)v16 + 24) = 0;
      *((_OWORD *)v16 + 5) = 0;
      v16[12] = 0;
      v16[13] = 7;
      *((_WORD *)v16 + 40) = 0;
    }
    catch ( std::bad_alloc )
    {
      AslLogCallPrintf(2, "DeviceMapInitializeTelemetryAndCache", 143, "Out of memory [%#x]", -2147024888);
      if ( EnableDevInvStdErrLog )
      {
        v40 = o___acrt_iob_func_0(2u);
        fprintf(v40, "Error: %s, %u: ", "DeviceMapInitializeTelemetryAndCache", 143);
        v41 = o___acrt_iob_func_0(2u);
        fprintf(v41, "Out of memory [%#x]", -2147024888);
        v42 = o___acrt_iob_func_0(2u);
        fprintf(v42, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, "Out of memory [%#x]", -2147024888);
      AslLogCallPrintf(1, "DeviceMapInitializeTelemetryAndCache", 143, "Out of memory [%#x]", -2147024888);
      v1 = -2147024888;
      goto LABEL_18;
    }
    v32 = 0;
    while ( 1 )
    {
      v33 = TelCacheProvider::Initialize(
              *(&v47 + 3 * v32),
              (&v46)[3 * v32],
              (__int64)*(&v48 + 3 * v32),
              2,
              2,
              5,
              0x1F4u);
      v1 = v33;
      *(&v48 + 3 * v32) = 0;
      if ( v33 < 0 )
        break;
      if ( a1 )
        TelCacheProvider::NewSyncId(*(&v47 + 3 * v32));
      if ( ++v32 >= v2 )
      {
        v1 = 0;
        goto LABEL_22;
      }
    }
    AslLogCallPrintf(2, "DeviceMapInitializeTelemetryAndCache", 164, "TelCacheProvider::Initialize failed [%#x]", v33);
    if ( EnableDevInvStdErrLog )
    {
      v34 = o___acrt_iob_func_0(2u);
      fprintf(v34, "Error: %s, %u: ", "DeviceMapInitializeTelemetryAndCache", 164);
      v35 = o___acrt_iob_func_0(2u);
      fprintf(v35, "TelCacheProvider::Initialize failed [%#x]", v1);
      v36 = o___acrt_iob_func_0(2u);
      fprintf(v36, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "TelCacheProvider::Initialize failed [%#x]", v1);
    AslLogCallPrintf(1, "DeviceMapInitializeTelemetryAndCache", 164, "TelCacheProvider::Initialize failed [%#x]", v1);
LABEL_18:
    for ( i = 0; i < 0xCu; ++i )
    {
      v38 = (void (__fastcall ***)(_QWORD, __int64))*(&v48 + 3 * (__int16)i);
      if ( v38 )
      {
        (**v38)(v38, 1);
        *(&v48 + 3 * (__int16)i) = 0;
      }
    }
  }
LABEL_22:
  ReleaseSRWLockExclusive(&stru_180156ED0);
  return v1;
}

```

## disassembly

```asm
0x18003d8c0  push    rbx
0x18003d8c2  push    rsi
0x18003d8c3  push    rdi
0x18003d8c4  push    r12
0x18003d8c6  push    r13
0x18003d8c8  push    r14
0x18003d8ca  push    r15
0x18003d8cc  sub     rsp, 180h
0x18003d8d3  mov     rax, cs:__security_cookie
0x18003d8da  xor     rax, rsp
0x18003d8dd  mov     [rsp+1B8h+var_48], rax
0x18003d8e5  mov     [rsp+1B8h+var_170], cl
0x18003d8e9  xor     edi, edi
0x18003d8eb  mov     esi, edi
0x18003d8ed  lea     rcx, stru_180156ED0; SRWLock
0x18003d8f4  call    cs:__imp_AcquireSRWLockExclusive
0x18003d8fa  cmp     cs:byte_180156ECC, dil
0x18003d901  jnz     loc_18003E24E
0x18003d907  lea     r15d, [rdi+1]
0x18003d90b  mov     cs:byte_180156ECC, r15b
0x18003d912  mov     [rsp+1B8h+var_168], rdi
0x18003d917  xor     edx, edx; Val
0x18003d919  mov     r8d, 118h; Size
0x18003d91f  lea     rcx, [rsp+1B8h+var_160]; void *
0x18003d924  call    memset_0
0x18003d929  lea     r13d, [rdi+0Ch]
0x18003d92d  mov     r12d, r13d
0x18003d930  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x18003d937  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x18003d93c  mov     ecx, 4B8h; Size
0x18003d941  test    al, al
0x18003d943  jz      loc_18003DCE7
0x18003d949  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003d94e  mov     [rsp+1B8h+var_178], rax
0x18003d953  mov     rcx, rax; this
0x18003d956  call    ??0CDeviceInventoryItem@@QEAA@XZ; CDeviceInventoryItem::CDeviceInventoryItem(void)
0x18003d95b  mov     rcx, rax
0x18003d95e  lea     rax, aInventorydevic_5; "InventoryDevicePnp"
0x18003d965  mov     [rsp+1B8h+var_168], rax
0x18003d96a  lea     rax, ?g_DeviceStore@@3VTelCacheProvider@@A; TelCacheProvider g_DeviceStore
0x18003d971  mov     [rsp+1B8h+var_160], rax
0x18003d976  mov     [rsp+1B8h+var_158], rcx
0x18003d97b  mov     ecx, 2D8h; Size
0x18003d980  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003d985  mov     rbx, rax
0x18003d988  mov     [rsp+1B8h+var_178], rax
0x18003d98d  xor     edx, edx; struct CDeviceMap *
0x18003d98f  mov     rcx, rax; this
0x18003d992  call    ??0CDeviceContainer@@QEAA@PEAVCDeviceMap@@@Z; CDeviceContainer::CDeviceContainer(CDeviceMap *)
0x18003d997  lea     rax, ??_7CDeviceContainer@@6BIAmiInventoryTelemetryItem@@@; const CDeviceContainer::`vftable'{for `IAmiInventoryTelemetryItem'}
0x18003d99e  mov     [rbx], rax
0x18003d9a1  lea     rax, ??_7CDeviceContainer@@6BIInventoryDataProvider@Inventory@Compat@Windows@@@; const CDeviceContainer::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'}
0x18003d9a8  mov     [rbx+8], rax
0x18003d9ac  lea     rax, aInventorydevic_4; "InventoryDeviceContainer"
0x18003d9b3  mov     [rsp+1B8h+var_150], rax
0x18003d9b8  lea     rax, ?g_DeviceContainerStore@@3VTelCacheProvider@@A; TelCacheProvider g_DeviceContainerStore
0x18003d9bf  mov     [rsp+1B8h+var_148], rax
0x18003d9c4  mov     [rsp+1B8h+var_140], rbx
0x18003d9c9  mov     ecx, 2E0h; Size
0x18003d9ce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003d9d3  mov     rbx, rax
0x18003d9d6  mov     [rsp+1B8h+var_178], rax
0x18003d9db  xor     edx, edx; struct CDriverMap *
0x18003d9dd  mov     rcx, rax; this
0x18003d9e0  call    ??0CDriver@@QEAA@PEAVCDriverMap@@@Z; CDriver::CDriver(CDriverMap *)
0x18003d9e5  lea     rax, ??_7CDriver@@6BIAmiInventoryTelemetryItem@@@; const CDriver::`vftable'{for `IAmiInventoryTelemetryItem'}
0x18003d9ec  mov     [rbx], rax
0x18003d9ef  lea     rax, ??_7CDriver@@6BIInventoryDataProvider@Inventory@Compat@Windows@@@; const CDriver::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'}
0x18003d9f6  mov     [rbx+8], rax
0x18003d9fa  lea     rax, aInventorydrive_0; "InventoryDriverBinary"
0x18003da01  mov     [rsp+1B8h+var_138], rax
0x18003da09  lea     rax, ?g_DriverBinaryStore@@3VTelCacheProvider@@A; TelCacheProvider g_DriverBinaryStore
0x18003da10  mov     [rsp+1B8h+var_130], rax
0x18003da18  mov     [rsp+1B8h+var_128], rbx
0x18003da20  mov     ecx, 0A8h; Size
0x18003da25  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003da2a  mov     [rsp+1B8h+var_178], rax
0x18003da2f  mov     rcx, rax; this
0x18003da32  call    ??0CMediaClassItem@@QEAA@XZ; CMediaClassItem::CMediaClassItem(void)
0x18003da37  mov     rcx, rax
0x18003da3a  lea     rax, aInventorydevic_6; "InventoryDeviceMediaClass"
0x18003da41  mov     [rsp+1B8h+var_120], rax
0x18003da49  lea     rax, ?g_MediaClassStore@@3VTelCacheProvider@@A; TelCacheProvider g_MediaClassStore
0x18003da50  mov     [rsp+1B8h+var_118], rax
0x18003da58  mov     [rsp+1B8h+var_110], rcx
0x18003da60  mov     ecx, 678h; Size
0x18003da65  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003da6a  mov     [rsp+1B8h+var_178], rax
0x18003da6f  mov     rcx, rax; this
0x18003da72  call    ??0CDeviceInterface@@QEAA@XZ; CDeviceInterface::CDeviceInterface(void)
0x18003da77  mov     rcx, rax
0x18003da7a  lea     rax, aInventorydevic_2; "InventoryDeviceInterface"
0x18003da81  mov     [rsp+1B8h+var_108], rax
0x18003da89  lea     rax, ?g_DeviceInterfaceStore@@3VTelCacheProvider@@A; TelCacheProvider g_DeviceInterfaceStore
0x18003da90  mov     [rsp+1B8h+var_100], rax
0x18003da98  mov     [rsp+1B8h+var_F8], rcx
0x18003daa0  lea     esi, [rdi+38h]
0x18003daa3  mov     ecx, esi; Size
0x18003daa5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003daaa  mov     rbx, rax
0x18003daad  mov     [rsp+1B8h+var_178], rax
0x18003dab2  lea     rax, ??_7CUsbHubClass@@6BIAmiInventoryTelemetryItem@@@; const CUsbHubClass::`vftable'{for `IAmiInventoryTelemetryItem'}
0x18003dab9  mov     [rbx], rax
0x18003dabc  lea     rax, ??_7CUsbHubClass@@6BIInventoryDataProvider@Inventory@Compat@Windows@@@; const CUsbHubClass::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'}
0x18003dac3  mov     [rbx+8], rax
0x18003dac7  lea     rcx, [rbx+10h]
0x18003dacb  xorps   xmm0, xmm0
0x18003dace  movups  xmmword ptr [rcx], xmm0
0x18003dad1  mov     [rcx+10h], rdi
0x18003dad5  mov     [rcx+18h], rdi
0x18003dad9  lea     r8d, [rdi+11h]
0x18003dadd  lea     rdx, aDeviceusbhubcl; "DeviceUsbHubClass"
0x18003dae4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003dae9  mov     [rbx+30h], rdi
0x18003daed  lea     rax, aInventorydevic_3; "InventoryDeviceUsbHubClass"
0x18003daf4  mov     [rsp+1B8h+var_F0], rax
0x18003dafc  lea     rax, ?g_DeviceUsbHubStore@@3VTelCacheProvider@@A; TelCacheProvider g_DeviceUsbHubStore
0x18003db03  mov     [rsp+1B8h+var_E8], rax
0x18003db0b  mov     [rsp+1B8h+var_E0], rbx
0x18003db13  mov     ecx, 2B0h; Size
0x18003db18  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003db1d  mov     [rsp+1B8h+var_178], rax
0x18003db22  mov     rcx, rax; this
0x18003db25  call    ??0CDriverPackage@@QEAA@XZ; CDriverPackage::CDriverPackage(void)
0x18003db2a  mov     rcx, rax
0x18003db2d  lea     rax, aInventorydrive; "InventoryDriverPackage"
0x18003db34  mov     [rsp+1B8h+var_D8], rax
0x18003db3c  lea     rax, ?g_DriverPackageStore@@3VTelCacheProvider@@A; TelCacheProvider g_DriverPackageStore
0x18003db43  mov     [rsp+1B8h+var_D0], rax
0x18003db4b  mov     [rsp+1B8h+var_C8], rcx
0x18003db53  lea     ecx, [rdi+58h]; Size
0x18003db56  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003db5b  lea     rcx, ??_7AcpiPhatVersionElement@@6BIAmiInventoryTelemetryItem@@@; const AcpiPhatVersionElement::`vftable'{for `IAmiInventoryTelemetryItem'}
0x18003db62  mov     [rax], rcx
0x18003db65  lea     rcx, ??_7AcpiPhatVersionElement@@6BIInventoryDataProvider@Inventory@Compat@Windows@@@; const AcpiPhatVersionElement::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'}
0x18003db6c  mov     [rax+8], rcx
0x18003db70  xorps   xmm0, xmm0
0x18003db73  movups  xmmword ptr [rax+10h], xmm0
0x18003db77  mov     [rax+20h], rdi
0x18003db7b  lea     ebx, [rdi+7]
0x18003db7e  mov     [rax+28h], rbx
0x18003db82  mov     [rax+10h], di
0x18003db86  mov     [rax+30h], rdi
0x18003db8a  movups  xmmword ptr [rax+38h], xmm0
0x18003db8e  mov     [rax+48h], rdi
0x18003db92  mov     [rax+50h], rbx
0x18003db96  mov     [rax+38h], di
0x18003db9a  lea     rcx, aInventoryacpip; "InventoryAcpiPhatVersionElement"
0x18003dba1  mov     [rsp+1B8h+var_C0], rcx
0x18003dba9  lea     rcx, ?g_AcpiPhatVersionElementStore@@3VTelCacheProvider@@A; TelCacheProvider g_AcpiPhatVersionElementStore
0x18003dbb0  mov     [rsp+1B8h+var_B8], rcx
0x18003dbb8  mov     [rsp+1B8h+var_B0], rax
0x18003dbc0  mov     ecx, esi; Size
0x18003dbc2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003dbc7  mov     [rax+33h], edi
0x18003dbca  mov     [rax+37h], dil
0x18003dbce  lea     rcx, ??_7AcpiPhatHealthDataRecord@@6BIAmiInventoryTelemetryItem@@@; const AcpiPhatHealthDataRecord::`vftable'{for `IAmiInventoryTelemetryItem'}
0x18003dbd5  mov     [rax], rcx
0x18003dbd8  lea     rcx, ??_7AcpiPhatHealthDataRecord@@6BIInventoryDataProvider@Inventory@Compat@Windows@@@; const AcpiPhatHealthDataRecord::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'}
0x18003dbdf  mov     [rax+8], rcx
0x18003dbe3  xorps   xmm0, xmm0
0x18003dbe6  movups  xmmword ptr [rax+10h], xmm0
0x18003dbea  mov     [rax+20h], rdi
0x18003dbee  mov     [rax+28h], rbx
0x18003dbf2  mov     [rax+10h], di
0x18003dbf6  mov     [rax+30h], di
0x18003dbfa  mov     [rax+32h], dil
0x18003dbfe  lea     rcx, aInventoryacpip_0; "InventoryAcpiPhatHealthRecord"
0x18003dc05  mov     [rsp+1B8h+var_A8], rcx
0x18003dc0d  lea     rcx, ?g_AcpiPhatHealthRecordStore@@3VTelCacheProvider@@A; TelCacheProvider g_AcpiPhatHealthRecordStore
0x18003dc14  mov     [rsp+1B8h+var_A0], rcx
0x18003dc1c  mov     [rsp+1B8h+var_98], rax
0x18003dc24  lea     esi, [rdi+70h]
0x18003dc27  mov     ecx, esi; Size
0x18003dc29  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003dc2e  lea     rcx, ??_7SensorDevice@@6BIAmiInventoryTelemetryItem@@@; const SensorDevice::`vftable'{for `IAmiInventoryTelemetryItem'}
0x18003dc35  mov     [rax], rcx
0x18003dc38  lea     rcx, ??_7PciDevice@@6BIInventoryDataProvider@Inventory@Compat@Windows@@@; const PciDevice::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'}
0x18003dc3f  mov     [rax+8], rcx
0x18003dc43  xorps   xmm0, xmm0
0x18003dc46  movups  xmmword ptr [rax+10h], xmm0
0x18003dc4a  mov     [rax+20h], rdi
0x18003dc4e  mov     [rax+28h], rbx
0x18003dc52  mov     [rax+10h], di
0x18003dc56  movups  xmmword ptr [rax+30h], xmm0
0x18003dc5a  mov     [rax+40h], rdi
0x18003dc5e  mov     [rax+48h], rbx
0x18003dc62  mov     [rax+30h], di
0x18003dc66  movups  xmmword ptr [rax+50h], xmm0
0x18003dc6a  mov     [rax+60h], rdi
0x18003dc6e  mov     [rax+68h], rbx
0x18003dc72  mov     [rax+50h], di
0x18003dc76  lea     rcx, aInventorydevic_0; "InventoryDeviceSensor"
0x18003dc7d  mov     [rsp+1B8h+var_90], rcx
0x18003dc85  lea     rcx, ?g_SensorDeviceStore@@3VTelCacheProvider@@A; TelCacheProvider g_SensorDeviceStore
0x18003dc8c  mov     [rsp+1B8h+var_88], rcx
0x18003dc94  mov     [rsp+1B8h+var_80], rax
0x18003dc9c  mov     ecx, esi; Size
0x18003dc9e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003dca3  lea     rcx, ??_7PciDevice@@6BIAmiInventoryTelemetryItem@@@; const PciDevice::`vftable'{for `IAmiInventoryTelemetryItem'}
0x18003dcaa  mov     [rax], rcx
0x18003dcad  lea     rcx, ??_7PciDevice@@6BIInventoryDataProvider@Inventory@Compat@Windows@@@; const PciDevice::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'}
0x18003dcb4  mov     [rax+8], rcx
0x18003dcb8  lea     rcx, aInventorydevic; "InventoryDevicePci"
0x18003dcbf  mov     [rsp+1B8h+var_78], rcx
0x18003dcc7  lea     rcx, ?g_PciDeviceStore@@3VTelCacheProvider@@A; TelCacheProvider g_PciDeviceStore
0x18003dcce  mov     [rsp+1B8h+var_70], rcx
0x18003dcd6  mov     [rsp+1B8h+var_68], rax
0x18003dcde  lea     r12d, [rdi+0Bh]
0x18003dce2  jmp     loc_18003E0BC
0x18003dce7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003dcec  mov     [rsp+1B8h+var_178], rax
0x18003dcf1  mov     rcx, rax; this
0x18003dcf4  call    ??0CDeviceInventoryItem@@QEAA@XZ; CDeviceInventoryItem::CDeviceInventoryItem(void)
0x18003dcf9  mov     rcx, rax
0x18003dcfc  lea     rax, aInventorydevic_5; "InventoryDevicePnp"
0x18003dd03  mov     [rsp+1B8h+var_168], rax
0x18003dd08  lea     rax, ?g_DeviceStore@@3VTelCacheProvider@@A; TelCacheProvider g_DeviceStore
0x18003dd0f  mov     [rsp+1B8h+var_160], rax
0x18003dd14  mov     [rsp+1B8h+var_158], rcx
0x18003dd19  mov     ecx, 2D8h; Size
0x18003dd1e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003dd23  mov     rbx, rax
0x18003dd26  mov     [rsp+1B8h+var_178], rax
0x18003dd2b  xor     edx, edx; struct CDeviceMap *
0x18003dd2d  mov     rcx, rax; this
0x18003dd30  call    ??0CDeviceContainer@@QEAA@PEAVCDeviceMap@@@Z; CDeviceContainer::CDeviceContainer(CDeviceMap *)
0x18003dd35  lea     rax, ??_7CDeviceContainer@@6BIAmiInventoryTelemetryItem@@@; const CDeviceContainer::`vftable'{for `IAmiInventoryTelemetryItem'}
0x18003dd3c  mov     [rbx], rax
0x18003dd3f  lea     rax, ??_7CDeviceContainer@@6BIInventoryDataProvider@Inventory@Compat@Windows@@@; const CDeviceContainer::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'}
0x18003dd46  mov     [rbx+8], rax
0x18003dd4a  lea     rax, aInventorydevic_4; "InventoryDeviceContainer"
0x18003dd51  mov     [rsp+1B8h+var_150], rax
0x18003dd56  lea     rax, ?g_DeviceContainerStore@@3VTelCacheProvider@@A; TelCacheProvider g_DeviceContainerStore
0x18003dd5d  mov     [rsp+1B8h+var_148], rax
0x18003dd62  mov     [rsp+1B8h+var_140], rbx
0x18003dd67  mov     ecx, 2E0h; Size
0x18003dd6c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003dd71  mov     rbx, rax
0x18003dd74  mov     [rsp+1B8h+var_178], rax
0x18003dd79  xor     edx, edx; struct CDriverMap *
0x18003dd7b  mov     rcx, rax; this
0x18003dd7e  call    ??0CDriver@@QEAA@PEAVCDriverMap@@@Z; CDriver::CDriver(CDriverMap *)
0x18003dd83  lea     rax, ??_7CDriver@@6BIAmiInventoryTelemetryItem@@@; const CDriver::`vftable'{for `IAmiInventoryTelemetryItem'}
0x18003dd8a  mov     [rbx], rax
0x18003dd8d  lea     rax, ??_7CDriver@@6BIInventoryDataProvider@Inventory@Compat@Windows@@@; const CDriver::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'}
0x18003dd94  mov     [rbx+8], rax
0x18003dd98  lea     rax, aInventorydrive_0; "InventoryDriverBinary"
0x18003dd9f  mov     [rsp+1B8h+var_138], rax
0x18003dda7  lea     rax, ?g_DriverBinaryStore@@3VTelCacheProvider@@A; TelCacheProvider g_DriverBinaryStore
0x18003ddae  mov     [rsp+1B8h+var_130], rax
0x18003ddb6  mov     [rsp+1B8h+var_128], rbx
0x18003ddbe  mov     ecx, 0A8h; Size
0x18003ddc3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003ddc8  mov     [rsp+1B8h+var_178], rax
0x18003ddcd  mov     rcx, rax; this
0x18003ddd0  call    ??0CMediaClassItem@@QEAA@XZ; CMediaClassItem::CMediaClassItem(void)
0x18003ddd5  mov     rcx, rax
0x18003ddd8  lea     rax, aInventorydevic_6; "InventoryDeviceMediaClass"
0x18003dddf  mov     [rsp+1B8h+var_120], rax
0x18003dde7  lea     rax, ?g_MediaClassStore@@3VTelCacheProvider@@A; TelCacheProvider g_MediaClassStore
0x18003ddee  mov     [rsp+1B8h+var_118], rax
0x18003ddf6  mov     [rsp+1B8h+var_110], rcx
0x18003ddfe  mov     ecx, 268h; Size
0x18003de03  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003de08  mov     [rsp+1B8h+var_178], rax
0x18003de0d  mov     rcx, rax; this
0x18003de10  call    ??0CDriverPackageDetailed@@QEAA@XZ; CDriverPackageDetailed::CDriverPackageDetailed(void)
0x18003de15  nop
0x18003de16  lea     rcx, aDriverpackagee; "DriverPackageExtended"
0x18003de1d  mov     [rsp+1B8h+var_108], rcx
0x18003de25  lea     rcx, ?g_DetailedDriverStore@@3VTelCacheProvider@@A; TelCacheProvider g_DetailedDriverStore
0x18003de2c  mov     [rsp+1B8h+var_100], rcx
0x18003de34  mov     [rsp+1B8h+var_F8], rax
0x18003de3c  mov     ecx, 678h; Size
0x18003de41  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003de46  mov     [rsp+1B8h+var_178], rax
0x18003de4b  mov     rcx, rax; this
0x18003de4e  call    ??0CDeviceInterface@@QEAA@XZ; CDeviceInterface::CDeviceInterface(void)
0x18003de53  mov     rcx, rax
0x18003de56  lea     rax, aInventorydevic_2; "InventoryDeviceInterface"
0x18003de5d  mov     [rsp+1B8h+var_F0], rax
0x18003de65  lea     rax, ?g_DeviceInterfaceStore@@3VTelCacheProvider@@A; TelCacheProvider g_DeviceInterfaceStore
0x18003de6c  mov     [rsp+1B8h+var_E8], rax
0x18003de74  mov     [rsp+1B8h+var_E0], rcx
0x18003de7c  mov     esi, 38h ; '8'
0x18003de81  mov     ecx, esi; Size
0x18003de83  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003de88  mov     rbx, rax
0x18003de8b  mov     [rsp+1B8h+var_178], rax
0x18003de90  lea     rax, ??_7CUsbHubClass@@6BIAmiInventoryTelemetryItem@@@; const CUsbHubClass::`vftable'{for `IAmiInventoryTelemetryItem'}
0x18003de97  mov     [rbx], rax
0x18003de9a  lea     rax, ??_7CUsbHubClass@@6BIInventoryDataProvider@Inventory@Compat@Windows@@@; const CUsbHubClass::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'}
0x18003dea1  mov     [rbx+8], rax
0x18003dea5  lea     rcx, [rbx+10h]
0x18003dea9  xorps   xmm0, xmm0
0x18003deac  movups  xmmword ptr [rcx], xmm0
0x18003deaf  mov     [rcx+10h], rdi
0x18003deb3  mov     [rcx+18h], rdi
0x18003deb7  lea     r8d, [rsi-27h]
  ... truncated ...
```
