# GetItemsFromCache(Windows::Compat::Inventory::IInventoryDataReceiver *)

- ea: `0x180017cb8`
- end: `0x18001863f`
- name: `?GetItemsFromCache@@YAJPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@@Z`
- size: `2439`
- prototype: `__int64 __fastcall(struct Windows::Compat::Inventory::IInventoryDataReceiver *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a500`

## callees

- `0x180006270`
- `0x180006d02`
- `0x180007014`
- `0x180017600`
- `0x180017cb8`
- `0x180018648`
- `0x180018f60`
- `0x18001f0e8`
- `0x180023734`
- `0x180048990`
- `0x18004af5c`
- `0x180057e1c`
- `0x18006041c`
- `0x180066c10`
- `0x180116010`

## string_xrefs

- `0x180017d77`: `GetItemsFromCache`
- `0x180017da1`: `GetItemsFromCache`
- `0x180017eb4`: `GetItemsFromCache`
- `0x180017ede`: `GetItemsFromCache`
- `0x180017fc8`: `GetItemsFromCache`
- `0x180017ff2`: `GetItemsFromCache`
- `0x180018113`: `GetItemsFromCache`
- `0x180018141`: `GetItemsFromCache`
- `0x18001821f`: `GetItemsFromCache`
- `0x18001824d`: `GetItemsFromCache`
- `0x18001834a`: `GetItemsFromCache`
- `0x180018378`: `GetItemsFromCache`
- `0x180018460`: `GetItemsFromCache`
- `0x18001848b`: `GetItemsFromCache`
- `0x180018447`: `InventoryDeviceMediaClass`
- `0x1800184ac`: `InventoryDeviceMediaClass`
- `0x1800184de`: `InventoryDeviceMediaClass`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall GetItemsFromCache(struct Windows::Compat::Inventory::IInventoryDataReceiver *a1)
{
  CDeviceContainer *v2; // r12
  void (__fastcall ***v3)(void *, __int64); // r15
  CDeviceInventoryItem *v4; // rcx
  struct IAmiDataInventoryTelemetryProviderItem *v5; // r13
  int ItemsFromProvider; // eax
  unsigned int v7; // edi
  FILE *v8; // rax
  FILE *v9; // rax
  FILE *v10; // rax
  int v11; // eax
  FILE *v12; // rax
  FILE *v13; // rax
  FILE *v14; // rax
  CDeviceInterface *v15; // rcx
  CDeviceInterface *v16; // r12
  int v17; // eax
  FILE *v18; // rax
  FILE *v19; // rax
  FILE *v20; // rax
  int v21; // eax
  FILE *v22; // rax
  FILE *v23; // rax
  FILE *v24; // rax
  CDriverPackage *v25; // r12
  int v26; // eax
  FILE *v27; // rax
  FILE *v28; // rax
  FILE *v29; // rax
  CDriver *v30; // r12
  int v31; // eax
  FILE *v32; // rax
  FILE *v33; // rax
  FILE *v34; // rax
  CMediaClassItem *v35; // rcx
  CMediaClassItem *v36; // r15
  int v37; // eax
  FILE *v38; // rax
  FILE *v39; // rax
  FILE *v40; // rax
  CDriverPackage *v42; // [rsp+38h] [rbp-80h]

  v2 = 0;
  v3 = 0;
  v4 = (CDeviceInventoryItem *)operator new(0x4B8u);
  v5 = CDeviceInventoryItem::CDeviceInventoryItem(v4);
  ItemsFromProvider = GetItemsFromProvider(a1, (struct TelCacheProvider *)g_DeviceStore, v5);
  v7 = ItemsFromProvider;
  if ( ItemsFromProvider < 0 )
  {
    AslLogCallPrintf(
      2,
      "GetItemsFromCache",
      108,
      "GetItemsFromProvider %ls FAILED %#x",
      L"InventoryDevicePnp",
      ItemsFromProvider);
    if ( EnableDevInvStdErrLog )
    {
      v8 = o___acrt_iob_func_0(2u);
      fprintf(v8, "Error: %s, %u: ", "GetItemsFromCache", 108);
      v9 = o___acrt_iob_func_0(2u);
      fprintf(v9, "GetItemsFromProvider %ls FAILED %#x", L"InventoryDevicePnp", v7);
      v10 = o___acrt_iob_func_0(2u);
      fprintf(v10, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "GetItemsFromProvider %ls FAILED %#x", L"InventoryDevicePnp", v7);
    if ( v5 )
      (**(void (__fastcall ***)(struct IAmiDataInventoryTelemetryProviderItem *, __int64))v5)(v5, 1);
LABEL_54:
    if ( v2 )
      (**(void (__fastcall ***)(CDeviceContainer *, __int64))v2)(v2, 1);
    v25 = 0;
LABEL_57:
    if ( v25 )
      (**(void (__fastcall ***)(CDriverPackage *, __int64))v25)(v25, 1);
    v30 = 0;
LABEL_60:
    if ( v30 )
      (**(void (__fastcall ***)(CDriver *, __int64))v30)(v30, 1);
    v16 = 0;
LABEL_63:
    if ( v16 )
      (**(void (__fastcall ***)(CDeviceInterface *, __int64))v16)(v16, 1);
LABEL_65:
    if ( v3 )
      (**v3)(v3, 1);
    v36 = 0;
LABEL_68:
    if ( v36 )
      (**(void (__fastcall ***)(CMediaClassItem *, __int64))v36)(v36, 1);
    return v7;
  }
  if ( v5 )
    (**(void (__fastcall ***)(struct IAmiDataInventoryTelemetryProviderItem *, __int64))v5)(v5, 1);
  v2 = (CDeviceContainer *)operator new(0x2D8u);
  CDeviceContainer::CDeviceContainer(v2, 0);
  *(_QWORD *)v2 = &CDeviceContainer::`vftable'{for `IAmiInventoryTelemetryItem'};
  *((_QWORD *)v2 + 1) = &CDeviceContainer::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
  v11 = GetItemsFromProvider(a1, (struct TelCacheProvider *)g_DeviceContainerStore, v2);
  v7 = v11;
  if ( v11 < 0 )
  {
    AslLogCallPrintf(
      2,
      "GetItemsFromCache",
      118,
      "GetItemsFromProvider %ls FAILED %#x",
      L"InventoryDeviceContainer",
      v11);
    if ( EnableDevInvStdErrLog )
    {
      v12 = o___acrt_iob_func_0(2u);
      fprintf(v12, "Error: %s, %u: ", "GetItemsFromCache", 118);
      v13 = o___acrt_iob_func_0(2u);
      fprintf(v13, "GetItemsFromProvider %ls FAILED %#x", L"InventoryDeviceContainer", v7);
      v14 = o___acrt_iob_func_0(2u);
      fprintf(v14, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "GetItemsFromProvider %ls FAILED %#x", L"InventoryDeviceContainer", v7);
    goto LABEL_54;
  }
  if ( v2 )
    (**(void (__fastcall ***)(CDeviceContainer *, __int64))v2)(v2, 1);
  v15 = (CDeviceInterface *)operator new(0x678u);
  v16 = CDeviceInterface::CDeviceInterface(v15);
  v17 = GetItemsFromProvider(a1, (struct TelCacheProvider *)g_DeviceInterfaceStore, v16);
  v7 = v17;
  if ( v17 < 0 )
  {
    AslLogCallPrintf(
      2,
      "GetItemsFromCache",
      128,
      "GetItemsFromProvider %ls FAILED %#x",
      L"InventoryDeviceInterface",
      v17);
    if ( EnableDevInvStdErrLog )
    {
      v18 = o___acrt_iob_func_0(2u);
      fprintf(v18, "Error: %s, %u: ", "GetItemsFromCache", 128);
      v19 = o___acrt_iob_func_0(2u);
      fprintf(v19, "GetItemsFromProvider %ls FAILED %#x", L"InventoryDeviceInterface", v7);
      v20 = o___acrt_iob_func_0(2u);
      fprintf(v20, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "GetItemsFromProvider %ls FAILED %#x", L"InventoryDeviceInterface", v7);
    goto LABEL_63;
  }
  if ( v16 )
    (**(void (__fastcall ***)(CDeviceInterface *, __int64))v16)(v16, 1);
  v3 = (void (__fastcall ***)(void *, __int64))operator new(0x38u);
  *v3 = (void (__fastcall **)(void *, __int64))&CUsbHubClass::`vftable'{for `IAmiInventoryTelemetryItem'};
  v3[1] = (void (__fastcall **)(void *, __int64))&CUsbHubClass::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
  *((_OWORD *)v3 + 1) = 0;
  v3[4] = 0;
  v3[5] = 0;
  std::wstring::_Construct<1,unsigned short const *>(v3 + 2, L"DeviceUsbHubClass", 17);
  v3[6] = 0;
  v21 = GetItemsFromProvider(
          a1,
          (struct TelCacheProvider *)g_DeviceUsbHubStore,
          (struct IAmiDataInventoryTelemetryProviderItem *)v3);
  v7 = v21;
  if ( v21 < 0 )
  {
    AslLogCallPrintf(
      2,
      "GetItemsFromCache",
      138,
      "GetItemsFromProvider %ls FAILED %#x",
      L"InventoryDeviceUsbHubClass",
      v21);
    if ( EnableDevInvStdErrLog )
    {
      v22 = o___acrt_iob_func_0(2u);
      fprintf(v22, "Error: %s, %u: ", "GetItemsFromCache", 138);
      v23 = o___acrt_iob_func_0(2u);
      fprintf(v23, "GetItemsFromProvider %ls FAILED %#x", L"InventoryDeviceUsbHubClass", v7);
      v24 = o___acrt_iob_func_0(2u);
      fprintf(v24, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "GetItemsFromProvider %ls FAILED %#x", L"InventoryDeviceUsbHubClass", v7);
    goto LABEL_65;
  }
  if ( v3 )
    (**v3)(v3, 1);
  v3 = 0;
  v42 = (CDriverPackage *)operator new(0x2B0u);
  v25 = CDriverPackage::CDriverPackage(v42);
  v26 = GetItemsFromProvider(a1, (struct TelCacheProvider *)g_DriverPackageStore, v25);
  v7 = v26;
  if ( v26 < 0 )
  {
    AslLogCallPrintf(2, "GetItemsFromCache", 148, "GetItemsFromProvider %ls FAILED %#x", L"InventoryDriverPackage", v26);
    if ( EnableDevInvStdErrLog )
    {
      v27 = o___acrt_iob_func_0(2u);
      fprintf(v27, "Error: %s, %u: ", "GetItemsFromCache", 148);
      v28 = o___acrt_iob_func_0(2u);
      fprintf(v28, "GetItemsFromProvider %ls FAILED %#x", L"InventoryDriverPackage", v7);
      v29 = o___acrt_iob_func_0(2u);
      fprintf(v29, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "GetItemsFromProvider %ls FAILED %#x", L"InventoryDriverPackage", v7);
    goto LABEL_57;
  }
  if ( v25 )
    (**(void (__fastcall ***)(CDriverPackage *, __int64))v25)(v25, 1);
  v30 = (CDriver *)operator new(0x2E0u);
  CDriver::CDriver(v30, 0);
  *(_QWORD *)v30 = &CDriver::`vftable'{for `IAmiInventoryTelemetryItem'};
  *((_QWORD *)v30 + 1) = &CDriver::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
  v31 = GetItemsFromProvider(a1, (struct TelCacheProvider *)g_DriverBinaryStore, v30);
  v7 = v31;
  if ( v31 < 0 )
  {
    AslLogCallPrintf(2, "GetItemsFromCache", 158, "GetItemsFromProvider %ls FAILED %#x", L"InventoryDriverBinary", v31);
    if ( EnableDevInvStdErrLog )
    {
      v32 = o___acrt_iob_func_0(2u);
      fprintf(v32, "Error: %s, %u: ", "GetItemsFromCache", 158);
      v33 = o___acrt_iob_func_0(2u);
      fprintf(v33, "GetItemsFromProvider %ls FAILED %#x", L"InventoryDriverBinary", v7);
      v34 = o___acrt_iob_func_0(2u);
      fprintf(v34, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "GetItemsFromProvider %ls FAILED %#x", L"InventoryDriverBinary", v7);
    goto LABEL_60;
  }
  if ( v30 )
    (**(void (__fastcall ***)(CDriver *, __int64))v30)(v30, 1);
  v35 = (CMediaClassItem *)operator new(0xA8u);
  v36 = CMediaClassItem::CMediaClassItem(v35);
  v37 = GetItemsFromProvider(a1, (struct TelCacheProvider *)g_MediaClassStore, v36);
  v7 = v37;
  if ( v37 < 0 )
  {
    AslLogCallPrintf(
      2,
      "GetItemsFromCache",
      168,
      "GetItemsFromProvider %ls FAILED %#x",
      L"InventoryDeviceMediaClass",
      v37);
    if ( EnableDevInvStdErrLog )
    {
      v38 = o___acrt_iob_func_0(2u);
      fprintf(v38, "Error: %s, %u: ", "GetItemsFromCache", 168);
      v39 = o___acrt_iob_func_0(2u);
      fprintf(v39, "GetItemsFromProvider %ls FAILED %#x", L"InventoryDeviceMediaClass", v7);
      v40 = o___acrt_iob_func_0(2u);
      fprintf(v40, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "GetItemsFromProvider %ls FAILED %#x", L"InventoryDeviceMediaClass", v7);
    goto LABEL_68;
  }
  if ( v36 )
    (**(void (__fastcall ***)(CMediaClassItem *, __int64))v36)(v36, 1);
  return v7;
}

```

## disassembly

```asm
0x180017cb8  push    rbx
0x180017cba  push    rsi
0x180017cbb  push    rdi
0x180017cbc  push    r12
0x180017cbe  push    r13
0x180017cc0  push    r14
0x180017cc2  push    r15
0x180017cc4  sub     rsp, 80h
0x180017ccb  mov     rsi, rcx
0x180017cce  xor     ebx, ebx
0x180017cd0  mov     [rsp+0B8h+arg_10], rbx
0x180017cd8  mov     r12d, ebx
0x180017cdb  mov     [rsp+0B8h+arg_18], rbx
0x180017ce3  mov     [rsp+0B8h+arg_8], rbx
0x180017ceb  mov     [rsp+0B8h+var_70], rbx
0x180017cf0  mov     r15d, ebx
0x180017cf3  mov     [rsp+0B8h+var_68], rbx
0x180017cf8  mov     [rsp+0B8h+var_80], rbx
0x180017cfd  mov     [rsp+0B8h+var_60], rbx
0x180017d02  mov     [rsp+0B8h+var_78], rbx
0x180017d07  mov     [rsp+0B8h+var_58], rbx
0x180017d0c  mov     [rsp+0B8h+var_48], rbx
0x180017d11  mov     [rsp+0B8h+var_50], rbx
0x180017d16  mov     ecx, 4B8h; Size
0x180017d1b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017d20  mov     [rsp+0B8h+var_88], rax
0x180017d25  mov     rcx, rax; this
0x180017d28  call    ??0CDeviceInventoryItem@@QEAA@XZ; CDeviceInventoryItem::CDeviceInventoryItem(void)
0x180017d2d  mov     r13, rax
0x180017d30  mov     [rsp+0B8h+var_88], rax
0x180017d35  mov     [rsp+0B8h+arg_10], rax
0x180017d3d  mov     r8, rax; struct IAmiDataInventoryTelemetryProviderItem *
0x180017d40  lea     rdx, ?g_DeviceStore@@3VTelCacheProvider@@A; struct TelCacheProvider *
0x180017d47  mov     rcx, rsi; struct Windows::Compat::Inventory::IInventoryDataReceiver *
0x180017d4a  call    ?GetItemsFromProvider@@YAJPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@PEAVTelCacheProvider@@PEAVIAmiDataInventoryTelemetryProviderItem@@@Z; GetItemsFromProvider(Windows::Compat::Inventory::IInventoryDataReceiver *,TelCacheProvider *,IAmiDataInventoryTelemetryProviderItem *)
0x180017d4f  mov     edi, eax
0x180017d51  test    eax, eax
0x180017d53  jns     loc_180017E0E
0x180017d59  mov     [rsp+0B8h+var_90], eax
0x180017d5d  lea     rax, aInventorydevic_5; "InventoryDevicePnp"
0x180017d64  mov     [rsp+0B8h+var_98], rax
0x180017d69  lea     rsi, aGetitemsfrompr; "GetItemsFromProvider %ls FAILED %#x"
0x180017d70  mov     r9, rsi
0x180017d73  lea     r8d, [rbx+6Ch]
0x180017d77  lea     rdx, aGetitemsfromca; "GetItemsFromCache"
0x180017d7e  lea     r14d, [rbx+2]
0x180017d82  mov     ecx, r14d
0x180017d85  call    AslLogCallPrintf
0x180017d8a  cmp     cs:EnableDevInvStdErrLog, ebx
0x180017d90  jz      short loc_180017DE8
0x180017d92  mov     ecx, r14d; Ix
0x180017d95  call    _o___acrt_iob_func_0
0x180017d9a  mov     rcx, rax; Stream
0x180017d9d  lea     r9d, [rbx+6Ch]
0x180017da1  lea     r8, aGetitemsfromca; "GetItemsFromCache"
0x180017da8  lea     rdx, Format; "Error: %s, %u: "
0x180017daf  call    fprintf
0x180017db4  mov     ecx, r14d; Ix
0x180017db7  call    _o___acrt_iob_func_0
0x180017dbc  mov     rcx, rax; Stream
0x180017dbf  mov     r9d, edi
0x180017dc2  lea     r8, aInventorydevic_5; "InventoryDevicePnp"
0x180017dc9  mov     rdx, rsi; Format
0x180017dcc  call    fprintf
0x180017dd1  mov     ecx, r14d; Ix
0x180017dd4  call    _o___acrt_iob_func_0
0x180017dd9  mov     rcx, rax; Stream
0x180017ddc  lea     rdx, asc_18011EAD8; "\n"
0x180017de3  call    fprintf
0x180017de8  cmp     cs:g_DeviceMapLogFunction, rbx
0x180017def  jz      short loc_180017E09
0x180017df1  mov     r9d, edi
0x180017df4  lea     r8, aInventorydevic_5; "InventoryDevicePnp"
0x180017dfb  mov     rdx, rsi
0x180017dfe  mov     ecx, 2000000h
0x180017e03  call    TraceMessageCallback
0x180017e08  nop
0x180017e09  jmp     loc_180018564
0x180017e0e  test    r13, r13
0x180017e11  jz      short loc_180017E2F
0x180017e13  mov     rax, [r13+0]
0x180017e17  mov     r13d, 1
0x180017e1d  mov     edx, r13d
0x180017e20  mov     rcx, [rsp+0B8h+var_88]
0x180017e25  mov     rax, [rax]
0x180017e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e2d  jmp     short loc_180017E35
0x180017e2f  mov     r13d, 1
0x180017e35  mov     [rsp+0B8h+arg_10], rbx
0x180017e3d  mov     ecx, 2D8h; Size
0x180017e42  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017e47  mov     r12, rax
0x180017e4a  mov     [rsp+0B8h+var_88], rax
0x180017e4f  xor     edx, edx; struct CDeviceMap *
0x180017e51  mov     rcx, rax; this
0x180017e54  call    ??0CDeviceContainer@@QEAA@PEAVCDeviceMap@@@Z; CDeviceContainer::CDeviceContainer(CDeviceMap *)
0x180017e59  lea     rax, ??_7CDeviceContainer@@6BIAmiInventoryTelemetryItem@@@; const CDeviceContainer::`vftable'{for `IAmiInventoryTelemetryItem'}
0x180017e60  mov     [r12], rax
0x180017e64  lea     rax, ??_7CDeviceContainer@@6BIInventoryDataProvider@Inventory@Compat@Windows@@@; const CDeviceContainer::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'}
0x180017e6b  mov     [r12+8], rax
0x180017e70  mov     [rsp+0B8h+arg_18], r12
0x180017e78  mov     r8, r12; struct IAmiDataInventoryTelemetryProviderItem *
0x180017e7b  lea     rdx, ?g_DeviceContainerStore@@3VTelCacheProvider@@A; struct TelCacheProvider *
0x180017e82  mov     rcx, rsi; struct Windows::Compat::Inventory::IInventoryDataReceiver *
0x180017e85  call    ?GetItemsFromProvider@@YAJPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@PEAVTelCacheProvider@@PEAVIAmiDataInventoryTelemetryProviderItem@@@Z; GetItemsFromProvider(Windows::Compat::Inventory::IInventoryDataReceiver *,TelCacheProvider *,IAmiDataInventoryTelemetryProviderItem *)
0x180017e8a  mov     edi, eax
0x180017e8c  test    eax, eax
0x180017e8e  jns     loc_180017F4B
0x180017e94  mov     [rsp+0B8h+var_90], eax
0x180017e98  lea     rax, aInventorydevic_4; "InventoryDeviceContainer"
0x180017e9f  mov     [rsp+0B8h+var_98], rax
0x180017ea4  lea     rsi, aGetitemsfrompr; "GetItemsFromProvider %ls FAILED %#x"
0x180017eab  mov     r9, rsi
0x180017eae  mov     r8d, 76h ; 'v'
0x180017eb4  lea     rdx, aGetitemsfromca; "GetItemsFromCache"
0x180017ebb  lea     r14d, [r8-74h]
0x180017ebf  mov     ecx, r14d
0x180017ec2  call    AslLogCallPrintf
0x180017ec7  cmp     cs:EnableDevInvStdErrLog, ebx
0x180017ecd  jz      short loc_180017F25
0x180017ecf  mov     ecx, r14d; Ix
0x180017ed2  call    _o___acrt_iob_func_0
0x180017ed7  mov     rcx, rax; Stream
0x180017eda  lea     r9d, [r14+74h]
0x180017ede  lea     r8, aGetitemsfromca; "GetItemsFromCache"
0x180017ee5  lea     rdx, Format; "Error: %s, %u: "
0x180017eec  call    fprintf
0x180017ef1  mov     ecx, r14d; Ix
0x180017ef4  call    _o___acrt_iob_func_0
0x180017ef9  mov     rcx, rax; Stream
0x180017efc  mov     r9d, edi
0x180017eff  lea     r8, aInventorydevic_4; "InventoryDeviceContainer"
0x180017f06  mov     rdx, rsi; Format
0x180017f09  call    fprintf
0x180017f0e  mov     ecx, r14d; Ix
0x180017f11  call    _o___acrt_iob_func_0
0x180017f16  mov     rcx, rax; Stream
0x180017f19  lea     rdx, asc_18011EAD8; "\n"
0x180017f20  call    fprintf
0x180017f25  cmp     cs:g_DeviceMapLogFunction, rbx
0x180017f2c  jz      short loc_180017F46
0x180017f2e  mov     r9d, edi
0x180017f31  lea     r8, aInventorydevic_4; "InventoryDeviceContainer"
0x180017f38  mov     rdx, rsi
0x180017f3b  mov     ecx, 2000000h
0x180017f40  call    TraceMessageCallback
0x180017f45  nop
0x180017f46  jmp     loc_18001858B
0x180017f4b  test    r12, r12
0x180017f4e  jz      short loc_180017F62
0x180017f50  mov     rax, [r12]
0x180017f54  mov     edx, r13d
0x180017f57  mov     rcx, r12
0x180017f5a  mov     rax, [rax]
0x180017f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f62  mov     [rsp+0B8h+arg_18], rbx
0x180017f6a  mov     ecx, 678h; Size
0x180017f6f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017f74  mov     [rsp+0B8h+arg_8], rax
0x180017f7c  mov     rcx, rax; this
0x180017f7f  call    ??0CDeviceInterface@@QEAA@XZ; CDeviceInterface::CDeviceInterface(void)
0x180017f84  mov     r12, rax
0x180017f87  mov     [rsp+0B8h+var_70], rax
0x180017f8c  mov     r8, rax; struct IAmiDataInventoryTelemetryProviderItem *
0x180017f8f  lea     rdx, ?g_DeviceInterfaceStore@@3VTelCacheProvider@@A; struct TelCacheProvider *
0x180017f96  mov     rcx, rsi; struct Windows::Compat::Inventory::IInventoryDataReceiver *
0x180017f99  call    ?GetItemsFromProvider@@YAJPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@PEAVTelCacheProvider@@PEAVIAmiDataInventoryTelemetryProviderItem@@@Z; GetItemsFromProvider(Windows::Compat::Inventory::IInventoryDataReceiver *,TelCacheProvider *,IAmiDataInventoryTelemetryProviderItem *)
0x180017f9e  mov     edi, eax
0x180017fa0  test    eax, eax
0x180017fa2  jns     loc_18001805F
0x180017fa8  mov     [rsp+0B8h+var_90], eax
0x180017fac  lea     rax, aInventorydevic_2; "InventoryDeviceInterface"
0x180017fb3  mov     [rsp+0B8h+var_98], rax
0x180017fb8  lea     rsi, aGetitemsfrompr; "GetItemsFromProvider %ls FAILED %#x"
0x180017fbf  mov     r9, rsi
0x180017fc2  mov     r8d, 80h
0x180017fc8  lea     rdx, aGetitemsfromca; "GetItemsFromCache"
0x180017fcf  lea     r14d, [r8-7Eh]
0x180017fd3  mov     ecx, r14d
0x180017fd6  call    AslLogCallPrintf
0x180017fdb  cmp     cs:EnableDevInvStdErrLog, ebx
0x180017fe1  jz      short loc_180018039
0x180017fe3  mov     ecx, r14d; Ix
0x180017fe6  call    _o___acrt_iob_func_0
0x180017feb  mov     rcx, rax; Stream
0x180017fee  lea     r9d, [r14+7Eh]
0x180017ff2  lea     r8, aGetitemsfromca; "GetItemsFromCache"
0x180017ff9  lea     rdx, Format; "Error: %s, %u: "
0x180018000  call    fprintf
0x180018005  mov     ecx, r14d; Ix
0x180018008  call    _o___acrt_iob_func_0
0x18001800d  mov     rcx, rax; Stream
0x180018010  mov     r9d, edi
0x180018013  lea     r8, aInventorydevic_2; "InventoryDeviceInterface"
0x18001801a  mov     rdx, rsi; Format
0x18001801d  call    fprintf
0x180018022  mov     ecx, r14d; Ix
0x180018025  call    _o___acrt_iob_func_0
0x18001802a  mov     rcx, rax; Stream
0x18001802d  lea     rdx, asc_18011EAD8; "\n"
0x180018034  call    fprintf
0x180018039  cmp     cs:g_DeviceMapLogFunction, rbx
0x180018040  jz      short loc_18001805A
0x180018042  mov     r9d, edi
0x180018045  lea     r8, aInventorydevic_2; "InventoryDeviceInterface"
0x18001804c  mov     rdx, rsi
0x18001804f  mov     ecx, 2000000h
0x180018054  call    TraceMessageCallback
0x180018059  nop
0x18001805a  jmp     loc_1800185E2
0x18001805f  test    r12, r12
0x180018062  jz      short loc_180018076
0x180018064  mov     rax, [r12]
0x180018068  mov     edx, r13d
0x18001806b  mov     rcx, r12
0x18001806e  mov     rax, [rax]
0x180018071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018076  mov     [rsp+0B8h+arg_8], rbx
0x18001807e  mov     [rsp+0B8h+var_70], rbx
0x180018083  mov     ecx, 38h ; '8'; Size
0x180018088  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001808d  mov     r15, rax
0x180018090  mov     [rsp+0B8h+var_80], rax
0x180018095  lea     rax, ??_7CUsbHubClass@@6BIAmiInventoryTelemetryItem@@@; const CUsbHubClass::`vftable'{for `IAmiInventoryTelemetryItem'}
0x18001809c  mov     [r15], rax
0x18001809f  lea     rax, ??_7CUsbHubClass@@6BIInventoryDataProvider@Inventory@Compat@Windows@@@; const CUsbHubClass::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'}
0x1800180a6  mov     [r15+8], rax
0x1800180aa  lea     rcx, [r15+10h]
0x1800180ae  xorps   xmm0, xmm0
0x1800180b1  movups  xmmword ptr [rcx], xmm0
0x1800180b4  mov     [rcx+10h], rbx
0x1800180b8  mov     [rcx+18h], rbx
0x1800180bc  mov     r8d, 11h
0x1800180c2  lea     rdx, aDeviceusbhubcl; "DeviceUsbHubClass"
0x1800180c9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800180ce  mov     [r15+30h], rbx
0x1800180d2  mov     [rsp+0B8h+var_68], r15
0x1800180d7  mov     r8, r15; struct IAmiDataInventoryTelemetryProviderItem *
0x1800180da  lea     rdx, ?g_DeviceUsbHubStore@@3VTelCacheProvider@@A; struct TelCacheProvider *
0x1800180e1  mov     rcx, rsi; struct Windows::Compat::Inventory::IInventoryDataReceiver *
0x1800180e4  call    ?GetItemsFromProvider@@YAJPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@PEAVTelCacheProvider@@PEAVIAmiDataInventoryTelemetryProviderItem@@@Z; GetItemsFromProvider(Windows::Compat::Inventory::IInventoryDataReceiver *,TelCacheProvider *,IAmiDataInventoryTelemetryProviderItem *)
0x1800180e9  mov     edi, eax
0x1800180eb  test    eax, eax
0x1800180ed  jns     loc_1800181A6
0x1800180f3  mov     [rsp+0B8h+var_90], eax
0x1800180f7  lea     r12, aInventorydevic_3; "InventoryDeviceUsbHubClass"
0x1800180fe  mov     [rsp+0B8h+var_98], r12
0x180018103  lea     rsi, aGetitemsfrompr; "GetItemsFromProvider %ls FAILED %#x"
0x18001810a  mov     r9, rsi
0x18001810d  mov     r8d, 8Ah
0x180018113  lea     rdx, aGetitemsfromca; "GetItemsFromCache"
0x18001811a  mov     r14d, 2
0x180018120  mov     ecx, r14d
0x180018123  call    AslLogCallPrintf
0x180018128  cmp     cs:EnableDevInvStdErrLog, ebx
0x18001812e  jz      short loc_180018184
0x180018130  mov     ecx, r14d; Ix
0x180018133  call    _o___acrt_iob_func_0
0x180018138  mov     rcx, rax; Stream
0x18001813b  mov     r9d, 8Ah
0x180018141  lea     r8, aGetitemsfromca; "GetItemsFromCache"
0x180018148  lea     rdx, Format; "Error: %s, %u: "
0x18001814f  call    fprintf
0x180018154  mov     ecx, r14d; Ix
0x180018157  call    _o___acrt_iob_func_0
0x18001815c  mov     rcx, rax; Stream
0x18001815f  mov     r9d, edi
0x180018162  mov     r8, r12
0x180018165  mov     rdx, rsi; Format
0x180018168  call    fprintf
0x18001816d  mov     ecx, r14d; Ix
0x180018170  call    _o___acrt_iob_func_0
0x180018175  mov     rcx, rax; Stream
0x180018178  lea     rdx, asc_18011EAD8; "\n"
0x18001817f  call    fprintf
0x180018184  cmp     cs:g_DeviceMapLogFunction, rbx
0x18001818b  jz      short loc_1800181A1
0x18001818d  mov     r9d, edi
0x180018190  mov     r8, r12
0x180018193  mov     rdx, rsi
0x180018196  mov     ecx, 2000000h
0x18001819b  call    TraceMessageCallback
0x1800181a0  nop
0x1800181a1  jmp     loc_1800185F9
0x1800181a6  test    r15, r15
0x1800181a9  jz      short loc_1800181BC
0x1800181ab  mov     rax, [r15]
0x1800181ae  mov     edx, r13d
0x1800181b1  mov     rcx, r15
0x1800181b4  mov     rax, [rax]
0x1800181b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181bc  mov     r15, rbx
0x1800181bf  mov     [rsp+0B8h+var_68], rbx
0x1800181c4  mov     ecx, 2B0h; Size
0x1800181c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800181ce  mov     [rsp+0B8h+var_80], rax
0x1800181d3  mov     rcx, rax; this
0x1800181d6  call    ??0CDriverPackage@@QEAA@XZ; CDriverPackage::CDriverPackage(void)
0x1800181db  mov     r12, rax
0x1800181de  mov     [rsp+0B8h+var_60], rax
  ... truncated ...
```
