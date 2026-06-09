# InternalGdiplusStartup(GdiplusStartupInput const *)

- ea: `0x1800cc950`
- end: `0x1800cd0d7`
- name: `?InternalGdiplusStartup@@YA?AW4Status@@PEBUGdiplusStartupInput@@@Z`
- size: `1927`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800cc850`

## callees

- `0x180019fd8`
- `0x180063cd8`
- `0x180084eb4`
- `0x180086550`
- `0x1800865b8`
- `0x180086668`
- `0x180086fc0`
- `0x18008a4c0`
- `0x1800cc950`
- `0x1800cd10c`
- `0x1800cd154`
- `0x1800cd1a8`
- `0x1800cd204`
- `0x1800cd280`
- `0x1800cd478`
- `0x1800cdc48`
- `0x1800cdfac`
- `0x1800cdfe8`
- `0x1800ce058`
- `0x1800d7384`
- `0x1800e790c`
- `0x1800e8bc0`
- `0x1801212b4`
- `0x1801212f0`
- `0x18012132c`
- `0x180121368`
- `0x1801213a4`
- `0x1801213e0`
- `0x18012141c`
- `0x180172010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ccfd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ccfd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ccb03`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ccb20`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ccb3d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ccb53`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ccb69`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ccfe9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cd006`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ccb03`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ccb20`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ccb3d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ccb53`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ccb69`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ccfe9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cd006`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800ccaea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800ccaea`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800cc989`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800cc9a7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800cc9c0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800cd052`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800cc989`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800cc9a7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800cc9c0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800cd052`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800cc966`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800cc966`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800cd019`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800cd019`
- `USER32!GetSystemMetrics` at `0x1800cce09`
- `USER32!GetSystemMetrics` at `0x1800cce1c`
- `USER32!GetSystemMetrics` at `0x1800cce32`
- `USER32!GetSystemMetrics` at `0x1800cce42`
- `USER32!GetSystemMetrics` at `0x1800cce09`
- `USER32!GetSystemMetrics` at `0x1800cce1c`
- `USER32!GetSystemMetrics` at `0x1800cce32`
- `USER32!GetSystemMetrics` at `0x1800cce42`
- `GDI32!DrawEscape` at `0x1800cce93`
- `GDI32!CreateICA` at `0x1800ccb84`
- `GDI32!CreateICA` at `0x1800ccb84`
- `GDI32!CreateRectRgn` at `0x1800ccac7`
- `GDI32!CreateRectRgn` at `0x1800ccac7`
- `GDI32!GetDeviceCaps` at `0x1800ccba8`
- `GDI32!GetDeviceCaps` at `0x1800ccbcf`
- `GDI32!GetDeviceCaps` at `0x1800ccba8`
- `GDI32!GetDeviceCaps` at `0x1800ccbcf`

## string_xrefs

- `0x1800ccae3`: `user32.dll`
- `0x1800ccfc9`: `gdi32.dll`

## pseudocode

```c
__int64 __fastcall InternalGdiplusStartup(_DWORD *a1)
{
  GpRuntime *v2; // rcx
  unsigned int v3; // r14d
  int v4; // ecx
  HMODULE ModuleHandleA; // rbx
  HDC ICA; // rax
  float DeviceCaps; // xmm0_4
  GpDevice *v8; // rax
  GpDevice *v9; // rbx
  _QWORD *v10; // rax
  __int64 v11; // rax
  DriverGdi *v12; // rax
  DriverGdi *v13; // rax
  DriverD3D *v14; // rax
  DriverInfo *v15; // rax
  DriverMeta *v16; // rax
  int v17; // r8d
  DpBitmap *v18; // rax
  int SystemMetrics; // ebx
  int v20; // eax
  struct GpDevice *v21; // rdx
  DpBitmap *v22; // rcx
  DpBitmap *v23; // rax
  GpDevice *v24; // rdi
  DpBitmap *v25; // rbx
  HMODULE ModuleHandleW; // rbx
  _DWORD *v27; // rax

  GpRuntime::GpMemHeap = HeapCreate(0, 0, 0);
  if ( !GpRuntime::GpMemHeap )
    goto LABEL_59;
  InitializeCriticalSection(&GpMallocTrackingCriticalSection::critSec);
  GpMallocTrackingCriticalSection::initialized = 1;
  InitializeCriticalSection(&BackgroundThreadCriticalSection::critSec);
  BackgroundThreadCriticalSection::initialized = 1;
  InitializeCriticalSection(&LoadLibraryCriticalSection::critSec);
  LoadLibraryCriticalSection::initialized = 1;
  v3 = 3;
  if ( *a1 > 1u )
  {
    v4 = a1[6];
    Globals::g_SetRoundMode = (v4 & 1) == 0;
    if ( (v4 & 2) != 0 && HIBYTE(v4) != 255 )
      Globals::g_PSTransparencyLimit = HIBYTE(v4);
    if ( (v4 & 4) != 0 || *a1 >= 3u )
      v3 = 1;
    Feature_GdiPlusOptimizations_GpBitmapScaler_IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_GdiPlusOptimizations_GpBitmapScaler>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GdiPlusOptimizations_GpBitmapScaler>::GetImpl'::`2'::impl);
    Feature_GdiPlusOptimizations_ScanOpAlphaMulDiv_IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpAlphaMulDiv>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpAlphaMulDiv>::GetImpl'::`2'::impl);
    Feature_GdiPlusOptimizations_ScanOpBlend_IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpBlend>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpBlend>::GetImpl'::`2'::impl);
    Feature_GdiPlusOptimizations_ScanOpConvert_IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpConvert>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpConvert>::GetImpl'::`2'::impl);
    Feature_GdiPlusOptimizations_ScanOpQuantize_IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpQuantize>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpQuantize>::GetImpl'::`2'::impl);
    Feature_GdiPlusOptimizations_DpOutputSpanStretch_IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_GdiPlusOptimizations_DpOutputSpanStretch>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GdiPlusOptimizations_DpOutputSpanStretch>::GetImpl'::`2'::impl);
    Feature_GdiPlusOptimizations_Misc_IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_GdiPlusOptimizations_Misc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GdiPlusOptimizations_Misc>::GetImpl'::`2'::impl);
    Globals::g_ForceAliasedDrawImage = 0;
    Globals::g_UseWmfSizeHeuristic = 1;
  }
  Globals::RuntimeInitialized = GpRuntime::Initialize(v2);
  if ( !Globals::RuntimeInitialized )
    goto LABEL_59;
  InitVersionInfo();
  Globals::CachedGdiRegion = CreateRectRgn(0, 0, 1, 1);
  if ( !Globals::CachedGdiRegion )
    goto LABEL_59;
  ModuleHandleA = GetModuleHandleA("user32.dll");
  Globals::GetWindowInfoFunction = (int (*)(HWND, struct tagWINDOWINFO *))GetProcAddress(ModuleHandleA, "GetWindowInfo");
  Globals::GetAncestorFunction = (HWND (*)(HWND, unsigned int))GetProcAddress(ModuleHandleA, "GetAncestor");
  GetProcAddress(ModuleHandleA, "GetMonitorInfoA");
  GetProcAddress(ModuleHandleA, "EnumDisplayMonitors");
  GetProcAddress(ModuleHandleA, "EnumDisplayDevicesA");
  ICA = CreateICA("DISPLAY", 0, 0, 0);
  Globals::DesktopIc = ICA;
  if ( !ICA )
    goto LABEL_59;
  Globals::DesktopDpiX = (float)GetDeviceCaps(ICA, 88);
  DeviceCaps = (float)GetDeviceCaps(Globals::DesktopIc, 90);
  Globals::DesktopDpiY = DeviceCaps;
  if ( Globals::DesktopDpiX <= 0.0 || DeviceCaps <= 0.0 )
  {
    Globals::DesktopDpiX = 96.0;
    Globals::DesktopDpiY = 96.0;
  }
  v8 = (GpDevice *)GpMallocEx(1632, 0);
  v9 = v8 ? GpDevice::GpDevice(v8, Globals::DesktopIc) : 0LL;
  Globals::DesktopDevice = v9;
  if ( !(unsigned int)CheckValid<GpDevice>() )
    goto LABEL_59;
  v10 = (_QWORD *)GpMallocEx(16, 0);
  if ( v10 )
  {
    *(_DWORD *)v10 = 0;
    v10[1] = 0;
  }
  Globals::DeviceList = v10;
  if ( !v10 )
    goto LABEL_59;
  v11 = GpMallocEx(40, 0);
  if ( v11 )
  {
    *(_QWORD *)v11 = &DpDriver::`vftable';
    *(_DWORD *)(v11 + 8) = 1917084721;
    *(_DWORD *)(v11 + 24) = 1;
    *(_QWORD *)(v11 + 32) = v9;
    *(_QWORD *)(v11 + 16) = 0;
  }
  Globals::EngineDriver = (struct DpDriver *)v11;
  if ( !(unsigned int)CheckValid<DpDriver>(&Globals::EngineDriver) )
    goto LABEL_59;
  v12 = (DriverGdi *)GpMallocEx(104, 0);
  if ( v12 )
    v12 = DriverGdi::DriverGdi(v12, v9);
  Globals::DesktopDriver = v12;
  if ( !(unsigned int)CheckValid<DpDriver>(&Globals::DesktopDriver) )
    goto LABEL_59;
  v13 = (DriverGdi *)GpMallocEx(104, 0);
  if ( v13 )
    v13 = DriverGdi::DriverGdi(v13, v9);
  Globals::GdiDriver = v13;
  if ( !(unsigned int)CheckValid<DpDriver>(&Globals::GdiDriver) )
    goto LABEL_59;
  v14 = (DriverD3D *)GpMallocEx(64, 0);
  if ( v14 )
    v14 = DriverD3D::DriverD3D(v14, v9);
  Globals::D3DDriver = v14;
  if ( !(unsigned int)CheckValid<DpDriver>(&Globals::D3DDriver) )
    goto LABEL_59;
  v15 = (DriverInfo *)GpMallocEx(40, 0);
  if ( v15 )
    v15 = DriverInfo::DriverInfo(v15, v9);
  Globals::InfoDriver = v15;
  if ( !(unsigned int)CheckValid<DpDriver>(&Globals::InfoDriver) )
    goto LABEL_59;
  v16 = (DriverMeta *)GpMallocEx(120, 0);
  if ( v16 )
    v16 = DriverMeta::DriverMeta(v16, v9, v17);
  Globals::MetaDriver = v16;
  if ( !(unsigned int)CheckValid<DpDriver>(&Globals::MetaDriver) )
    goto LABEL_59;
  v18 = (DpBitmap *)GpMallocEx(136, 0);
  if ( v18 )
    v18 = DpBitmap::DpBitmap(v18, 0);
  Globals::DesktopSurface = v18;
  if ( !(unsigned int)CheckValid<DpBitmap>(&Globals::DesktopSurface) )
    goto LABEL_59;
  SystemMetrics = GetSystemMetrics(78);
  v20 = GetSystemMetrics(79);
  if ( !SystemMetrics || !v20 )
  {
    SystemMetrics = GetSystemMetrics(0);
    v20 = GetSystemMetrics(1);
  }
  DpBitmap::InitializeForGdiScreen(v22, v21, SystemMetrics, v20);
  (*(void (__fastcall **)(struct DpDriver *, DpBitmap *))(*(_QWORD *)Globals::DesktopDriver + 16LL))(
    Globals::DesktopDriver,
    Globals::DesktopSurface);
  Globals::g_fRemoteSession = 0;
  Globals::g_pRemoteSurface = 0;
  Globals::g_pTSDriver = 0;
  Globals::g_pfnTestDrawEscapeFunction = DrawEscape;
  v23 = (DpBitmap *)GpMallocEx(136, 0);
  if ( v23 )
    v23 = DpBitmap::DpBitmap(v23, 0);
  Globals::g_pRemoteSurface = v23;
  if ( !(unsigned int)CheckValid<DpBitmap>(&Globals::g_pRemoteSurface) )
    goto LABEL_59;
  v24 = Globals::DesktopDevice;
  v25 = Globals::g_pRemoteSurface;
  DpBitmap::InitializeForGdiBitmap(
    Globals::g_pRemoteSurface,
    Globals::DesktopDevice,
    *((_DWORD *)Globals::DesktopDevice + 382),
    *((_DWORD *)Globals::DesktopDevice + 383));
  *((_DWORD *)v25 + 8) = 5;
  *((_DWORD *)v25 + 21) = 1;
  *((_QWORD *)v25 + 16) = *((_QWORD *)v24 + 187);
  if ( !(unsigned int)InitImagingLibrary(v3) )
    goto LABEL_59;
  LODWORD(Globals::SystemColors) = 0;
  dword_1801ADF34 = 0xFFFFFF;
  dword_1801ADF38 = 12632256;
  dword_1801ADF3C = 8421504;
  dword_1801ADF40 = 16711680;
  dword_1801ADF44 = 0x800000;
  dword_1801ADF48 = 65280;
  dword_1801ADF4C = 0x8000;
  dword_1801ADF50 = 255;
  dword_1801ADF54 = 128;
  dword_1801ADF58 = 0xFFFF;
  dword_1801ADF5C = 32896;
  dword_1801ADF60 = 16776960;
  dword_1801ADF64 = 8421376;
  dword_1801ADF68 = 16711935;
  dword_1801ADF6C = 8388736;
  SysColorNotify();
  ModuleHandleW = GetModuleHandleW(L"gdi32.dll");
  Globals::ExtTextOutFunction = (int (*)(HDC, int, int, unsigned int, const struct tagRECT *, const unsigned __int16 *, unsigned int, const int *))GetProcAddress(ModuleHandleW, "ExtTextOutW");
  Globals::GdiIsMetaPrintDCFunction = (int (*)(HDC))GetProcAddress(ModuleHandleW, "GdiIsMetaPrintDC");
  Globals::LanguageID = GetSystemDefaultLCID();
  if ( !(unsigned int)InitSystemFontsDirs() )
    goto LABEL_59;
  Globals::UserDigitSubstituteInvalid = 1;
  Globals::CurrentSystemRenderingHintInvalid = 1;
  Globals::CurrentSystemRenderingHint = 1;
  InitializeCriticalSection(&Globals::TextCriticalSection);
  Globals::TextCriticalSectionInitialized = 1;
  Globals::FontCollection = GpInstalledFontCollection::GetGpInstalledFontCollection();
  if ( !Globals::FontCollection )
    goto LABEL_59;
  v27 = (_DWORD *)GpMallocEx(16, 0);
  if ( v27 )
  {
    *(_QWORD *)v27 = 0;
    v27[2] = 0;
  }
  Globals::DWriteFontCacheLastRecentlyUsedList = v27;
  if ( v27 && (a1[4] || (unsigned int)BackgroundThreadStartup()) )
  {
    TraceLoggingRegisterEx_EventRegister_EventSetInformation();
    return 0;
  }
  else
  {
LABEL_59:
    InternalGdiplusShutdown();
    return 1;
  }
}

```

## disassembly

```asm
0x1800cc950  push    rbx
0x1800cc952  push    rsi
0x1800cc953  push    rdi
0x1800cc954  push    r14
0x1800cc956  push    r15
0x1800cc958  sub     rsp, 20h
0x1800cc95c  mov     r15, rcx
0x1800cc95f  xor     r8d, r8d; dwMaximumSize
0x1800cc962  xor     edx, edx; dwInitialSize
0x1800cc964  xor     ecx, ecx; flOptions
0x1800cc966  call    cs:__imp_HeapCreate
0x1800cc96d  nop     dword ptr [rax+rax+00h]
0x1800cc972  mov     cs:?GpMemHeap@GpRuntime@@3PEAXEA, rax; void * GpRuntime::GpMemHeap
0x1800cc979  test    rax, rax
0x1800cc97c  jz      loc_1800CD0BE
0x1800cc982  lea     rcx, ?critSec@GpMallocTrackingCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800cc989  call    cs:__imp_InitializeCriticalSection
0x1800cc990  nop     dword ptr [rax+rax+00h]
0x1800cc995  mov     esi, 1
0x1800cc99a  mov     cs:?initialized@GpMallocTrackingCriticalSection@@0HA, esi; int GpMallocTrackingCriticalSection::initialized
0x1800cc9a0  lea     rcx, ?critSec@BackgroundThreadCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800cc9a7  call    cs:__imp_InitializeCriticalSection
0x1800cc9ae  nop     dword ptr [rax+rax+00h]
0x1800cc9b3  mov     cs:?initialized@BackgroundThreadCriticalSection@@0HA, esi; int BackgroundThreadCriticalSection::initialized
0x1800cc9b9  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800cc9c0  call    cs:__imp_InitializeCriticalSection
0x1800cc9c7  nop     dword ptr [rax+rax+00h]
0x1800cc9cc  mov     cs:?initialized@LoadLibraryCriticalSection@@0HA, esi; int LoadLibraryCriticalSection::initialized
0x1800cc9d2  lea     r14d, [rsi+2]
0x1800cc9d6  cmp     [r15], esi
0x1800cc9d9  jbe     loc_1800CCAA5
0x1800cc9df  mov     ecx, [r15+18h]
0x1800cc9e3  mov     eax, ecx
0x1800cc9e5  not     eax
0x1800cc9e7  and     eax, esi
0x1800cc9e9  mov     cs:?g_SetRoundMode@Globals@@3HA, eax; int Globals::g_SetRoundMode
0x1800cc9ef  test    cl, 2
0x1800cc9f2  jz      short loc_1800CCA0A
0x1800cc9f4  mov     eax, ecx
0x1800cc9f6  sar     eax, 18h
0x1800cc9f9  movzx   edx, al
0x1800cc9fc  cmp     edx, 0FFh
0x1800cca02  jnb     short loc_1800CCA0A
0x1800cca04  mov     cs:?g_PSTransparencyLimit@Globals@@3HA, edx; int Globals::g_PSTransparencyLimit
0x1800cca0a  test    cl, 4
0x1800cca0d  jnz     short loc_1800CCA14
0x1800cca0f  cmp     [r15], r14d
0x1800cca12  jb      short loc_1800CCA17
0x1800cca14  mov     r14d, esi
0x1800cca17  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GdiPlusOptimizations_GpBitmapScaler@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GdiPlusOptimizations_GpBitmapScaler@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GdiPlusOptimizations_GpBitmapScaler> `wil::Feature<__WilFeatureTraits_Feature_GdiPlusOptimizations_GpBitmapScaler>::GetImpl(void)'::`2'::impl
0x1800cca1e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_GdiPlusOptimizations_GpBitmapScaler@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GdiPlusOptimizations_GpBitmapScaler>::__private_IsEnabled(void)
0x1800cca23  mov     cs:?Feature_GdiPlusOptimizations_GpBitmapScaler_IsEnabled@@3_NA, al; bool Feature_GdiPlusOptimizations_GpBitmapScaler_IsEnabled
0x1800cca29  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpAlphaMulDiv@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpAlphaMulDiv@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpAlphaMulDiv> `wil::Feature<__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpAlphaMulDiv>::GetImpl(void)'::`2'::impl
0x1800cca30  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpAlphaMulDiv@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpAlphaMulDiv>::__private_IsEnabled(void)
0x1800cca35  mov     cs:?Feature_GdiPlusOptimizations_ScanOpAlphaMulDiv_IsEnabled@@3_NA, al; bool Feature_GdiPlusOptimizations_ScanOpAlphaMulDiv_IsEnabled
0x1800cca3b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpBlend@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpBlend@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpBlend> `wil::Feature<__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpBlend>::GetImpl(void)'::`2'::impl
0x1800cca42  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpBlend@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpBlend>::__private_IsEnabled(void)
0x1800cca47  mov     cs:?Feature_GdiPlusOptimizations_ScanOpBlend_IsEnabled@@3_NA, al; bool Feature_GdiPlusOptimizations_ScanOpBlend_IsEnabled
0x1800cca4d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpConvert@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpConvert@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpConvert> `wil::Feature<__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpConvert>::GetImpl(void)'::`2'::impl
0x1800cca54  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpConvert@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpConvert>::__private_IsEnabled(void)
0x1800cca59  mov     cs:?Feature_GdiPlusOptimizations_ScanOpConvert_IsEnabled@@3_NA, al; bool Feature_GdiPlusOptimizations_ScanOpConvert_IsEnabled
0x1800cca5f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpQuantize@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpQuantize@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpQuantize> `wil::Feature<__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpQuantize>::GetImpl(void)'::`2'::impl
0x1800cca66  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpQuantize@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GdiPlusOptimizations_ScanOpQuantize>::__private_IsEnabled(void)
0x1800cca6b  mov     cs:?Feature_GdiPlusOptimizations_ScanOpQuantize_IsEnabled@@3_NA, al; bool Feature_GdiPlusOptimizations_ScanOpQuantize_IsEnabled
0x1800cca71  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GdiPlusOptimizations_DpOutputSpanStretch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GdiPlusOptimizations_DpOutputSpanStretch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GdiPlusOptimizations_DpOutputSpanStretch> `wil::Feature<__WilFeatureTraits_Feature_GdiPlusOptimizations_DpOutputSpanStretch>::GetImpl(void)'::`2'::impl
0x1800cca78  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_GdiPlusOptimizations_DpOutputSpanStretch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GdiPlusOptimizations_DpOutputSpanStretch>::__private_IsEnabled(void)
0x1800cca7d  mov     cs:?Feature_GdiPlusOptimizations_DpOutputSpanStretch_IsEnabled@@3_NA, al; bool Feature_GdiPlusOptimizations_DpOutputSpanStretch_IsEnabled
0x1800cca83  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GdiPlusOptimizations_Misc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GdiPlusOptimizations_Misc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GdiPlusOptimizations_Misc> `wil::Feature<__WilFeatureTraits_Feature_GdiPlusOptimizations_Misc>::GetImpl(void)'::`2'::impl
0x1800cca8a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_GdiPlusOptimizations_Misc@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GdiPlusOptimizations_Misc>::__private_IsEnabled(void)
0x1800cca8f  mov     cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA, al; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x1800cca95  mov     cs:?g_ForceAliasedDrawImage@Globals@@3HA, 0; int Globals::g_ForceAliasedDrawImage
0x1800cca9f  mov     cs:?g_UseWmfSizeHeuristic@Globals@@3HA, esi; int Globals::g_UseWmfSizeHeuristic
0x1800ccaa5  call    ?Initialize@GpRuntime@@YAHXZ; GpRuntime::Initialize(void)
0x1800ccaaa  mov     cs:?RuntimeInitialized@Globals@@3HA, eax; int Globals::RuntimeInitialized
0x1800ccab0  test    eax, eax
0x1800ccab2  jz      loc_1800CD0C3
0x1800ccab8  call    ?InitVersionInfo@@YAXXZ; InitVersionInfo(void)
0x1800ccabd  mov     r9d, esi; y2
0x1800ccac0  mov     r8d, esi; x2
0x1800ccac3  xor     edx, edx; y1
0x1800ccac5  xor     ecx, ecx; x1
0x1800ccac7  call    cs:__imp_CreateRectRgn
0x1800ccace  nop     dword ptr [rax+rax+00h]
0x1800ccad3  mov     cs:?CachedGdiRegion@Globals@@3PEAUHRGN__@@EA, rax; HRGN__ * Globals::CachedGdiRegion
0x1800ccada  test    rax, rax
0x1800ccadd  jz      loc_1800CD0C3
0x1800ccae3  lea     rcx, ModuleName; "user32.dll"
0x1800ccaea  call    cs:__imp_GetModuleHandleA
0x1800ccaf1  nop     dword ptr [rax+rax+00h]
0x1800ccaf6  mov     rbx, rax
0x1800ccaf9  lea     rdx, aGetwindowinfo; "GetWindowInfo"
0x1800ccb00  mov     rcx, rax; hModule
0x1800ccb03  call    cs:__imp_GetProcAddress
0x1800ccb0a  nop     dword ptr [rax+rax+00h]
0x1800ccb0f  mov     cs:?GetWindowInfoFunction@Globals@@3P6AHPEAUHWND__@@PEAUtagWINDOWINFO@@@ZEA, rax; int (*Globals::GetWindowInfoFunction)(HWND__ *,tagWINDOWINFO *)
0x1800ccb16  lea     rdx, aGetancestor; "GetAncestor"
0x1800ccb1d  mov     rcx, rbx; hModule
0x1800ccb20  call    cs:__imp_GetProcAddress
0x1800ccb27  nop     dword ptr [rax+rax+00h]
0x1800ccb2c  mov     cs:?GetAncestorFunction@Globals@@3P6APEAUHWND__@@PEAU2@I@ZEA, rax; HWND__ * (*Globals::GetAncestorFunction)(HWND__ *,uint)
0x1800ccb33  lea     rdx, aGetmonitorinfo; "GetMonitorInfoA"
0x1800ccb3a  mov     rcx, rbx; hModule
0x1800ccb3d  call    cs:__imp_GetProcAddress
0x1800ccb44  nop     dword ptr [rax+rax+00h]
0x1800ccb49  lea     rdx, aEnumdisplaymon; "EnumDisplayMonitors"
0x1800ccb50  mov     rcx, rbx; hModule
0x1800ccb53  call    cs:__imp_GetProcAddress
0x1800ccb5a  nop     dword ptr [rax+rax+00h]
0x1800ccb5f  lea     rdx, aEnumdisplaydev; "EnumDisplayDevicesA"
0x1800ccb66  mov     rcx, rbx; hModule
0x1800ccb69  call    cs:__imp_GetProcAddress
0x1800ccb70  nop     dword ptr [rax+rax+00h]
0x1800ccb75  xor     r9d, r9d; pdm
0x1800ccb78  xor     r8d, r8d; pszPort
0x1800ccb7b  xor     edx, edx; pszDevice
0x1800ccb7d  lea     rcx, pszDriver; "DISPLAY"
0x1800ccb84  call    cs:__imp_CreateICA
0x1800ccb8b  nop     dword ptr [rax+rax+00h]
0x1800ccb90  mov     cs:?DesktopIc@Globals@@3PEAUHDC__@@EA, rax; HDC__ * Globals::DesktopIc
0x1800ccb97  test    rax, rax
0x1800ccb9a  jz      loc_1800CD0C3
0x1800ccba0  mov     edx, 58h ; 'X'; index
0x1800ccba5  mov     rcx, rax; hdc
0x1800ccba8  call    cs:__imp_GetDeviceCaps
0x1800ccbaf  nop     dword ptr [rax+rax+00h]
0x1800ccbb4  movd    xmm0, eax
0x1800ccbb8  cvtdq2ps xmm0, xmm0
0x1800ccbbb  movss   cs:?DesktopDpiX@Globals@@3MA, xmm0; float Globals::DesktopDpiX
0x1800ccbc3  mov     edx, 5Ah ; 'Z'; index
0x1800ccbc8  mov     rcx, cs:?DesktopIc@Globals@@3PEAUHDC__@@EA; hdc
0x1800ccbcf  call    cs:__imp_GetDeviceCaps
0x1800ccbd6  nop     dword ptr [rax+rax+00h]
0x1800ccbdb  movd    xmm0, eax
0x1800ccbdf  cvtdq2ps xmm0, xmm0
0x1800ccbe2  movss   cs:?DesktopDpiY@Globals@@3MA, xmm0; float Globals::DesktopDpiY
0x1800ccbea  xorps   xmm1, xmm1
0x1800ccbed  comiss  xmm1, cs:?DesktopDpiX@Globals@@3MA; float Globals::DesktopDpiX
0x1800ccbf4  jnb     short loc_1800CCBFB
0x1800ccbf6  comiss  xmm1, xmm0
0x1800ccbf9  jb      short loc_1800CCC0F
0x1800ccbfb  mov     cs:?DesktopDpiX@Globals@@3MA, 42C00000h; float Globals::DesktopDpiX
0x1800ccc05  mov     cs:?DesktopDpiY@Globals@@3MA, 42C00000h; float Globals::DesktopDpiY
0x1800ccc0f  xor     edx, edx
0x1800ccc11  mov     ecx, 660h
0x1800ccc16  call    GpMallocEx
0x1800ccc1b  test    rax, rax
0x1800ccc1e  jz      short loc_1800CCC34
0x1800ccc20  mov     rdx, cs:?DesktopIc@Globals@@3PEAUHDC__@@EA; hdc
0x1800ccc27  mov     rcx, rax; this
0x1800ccc2a  call    ??0GpDevice@@QEAA@PEAUHDC__@@@Z; GpDevice::GpDevice(HDC__ *)
0x1800ccc2f  mov     rbx, rax
0x1800ccc32  jmp     short loc_1800CCC36
0x1800ccc34  xor     ebx, ebx
0x1800ccc36  mov     cs:?DesktopDevice@Globals@@3PEAVGpDevice@@EA, rbx; GpDevice * Globals::DesktopDevice
0x1800ccc3d  call    ??$CheckValid@VGpDevice@@@@YAHAEAPEAVGpDevice@@@Z; CheckValid<GpDevice>(GpDevice * &)
0x1800ccc42  test    eax, eax
0x1800ccc44  jz      loc_1800CD0C3
0x1800ccc4a  xor     edx, edx
0x1800ccc4c  lea     ecx, [rdx+10h]
0x1800ccc4f  call    GpMallocEx
0x1800ccc54  test    rax, rax
0x1800ccc57  jz      short loc_1800CCC67
0x1800ccc59  mov     dword ptr [rax], 0
0x1800ccc5f  mov     qword ptr [rax+8], 0
0x1800ccc67  mov     cs:?DeviceList@Globals@@3PEAVGpDeviceList@@EA, rax; GpDeviceList * Globals::DeviceList
0x1800ccc6e  test    rax, rax
0x1800ccc71  jz      loc_1800CD0C3
0x1800ccc77  xor     edx, edx
0x1800ccc79  lea     ecx, [rdx+28h]
0x1800ccc7c  call    GpMallocEx
0x1800ccc81  test    rax, rax
0x1800ccc84  jz      short loc_1800CCCA6
0x1800ccc86  lea     rcx, ??_7DpDriver@@6B@; const DpDriver::`vftable'
0x1800ccc8d  mov     [rax], rcx
0x1800ccc90  mov     dword ptr [rax+8], 72446431h
0x1800ccc97  mov     [rax+18h], esi
0x1800ccc9a  mov     [rax+20h], rbx
0x1800ccc9e  mov     qword ptr [rax+10h], 0
0x1800ccca6  mov     cs:?EngineDriver@Globals@@3PEAVDpDriver@@EA, rax; DpDriver * Globals::EngineDriver
0x1800cccad  lea     rcx, ?EngineDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::EngineDriver
0x1800cccb4  call    ??$CheckValid@VDpDriver@@@@YAHAEAPEAVDpDriver@@@Z; CheckValid<DpDriver>(DpDriver * &)
0x1800cccb9  test    eax, eax
0x1800cccbb  jz      loc_1800CD0C3
0x1800cccc1  xor     edx, edx
0x1800cccc3  lea     edi, [rdx+68h]
0x1800cccc6  mov     ecx, edi
0x1800cccc8  call    GpMallocEx
0x1800ccccd  test    rax, rax
0x1800cccd0  jz      short loc_1800CCCDD
0x1800cccd2  mov     rdx, rbx; struct GpDevice *
0x1800cccd5  mov     rcx, rax; this
0x1800cccd8  call    ??0DriverGdi@@QEAA@PEAVGpDevice@@@Z; DriverGdi::DriverGdi(GpDevice *)
0x1800cccdd  mov     cs:?DesktopDriver@Globals@@3PEAVDpDriver@@EA, rax; DpDriver * Globals::DesktopDriver
0x1800ccce4  lea     rcx, ?DesktopDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::DesktopDriver
0x1800ccceb  call    ??$CheckValid@VDpDriver@@@@YAHAEAPEAVDpDriver@@@Z; CheckValid<DpDriver>(DpDriver * &)
0x1800cccf0  test    eax, eax
0x1800cccf2  jz      loc_1800CD0C3
0x1800cccf8  xor     edx, edx
0x1800cccfa  mov     rcx, rdi
0x1800cccfd  call    GpMallocEx
0x1800ccd02  test    rax, rax
0x1800ccd05  jz      short loc_1800CCD12
0x1800ccd07  mov     rdx, rbx; struct GpDevice *
0x1800ccd0a  mov     rcx, rax; this
0x1800ccd0d  call    ??0DriverGdi@@QEAA@PEAVGpDevice@@@Z; DriverGdi::DriverGdi(GpDevice *)
0x1800ccd12  mov     cs:?GdiDriver@Globals@@3PEAVDpDriver@@EA, rax; DpDriver * Globals::GdiDriver
0x1800ccd19  lea     rcx, ?GdiDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::GdiDriver
0x1800ccd20  call    ??$CheckValid@VDpDriver@@@@YAHAEAPEAVDpDriver@@@Z; CheckValid<DpDriver>(DpDriver * &)
0x1800ccd25  test    eax, eax
0x1800ccd27  jz      loc_1800CD0C3
0x1800ccd2d  xor     edx, edx
0x1800ccd2f  lea     ecx, [rdx+40h]
0x1800ccd32  call    GpMallocEx
0x1800ccd37  test    rax, rax
0x1800ccd3a  jz      short loc_1800CCD47
0x1800ccd3c  mov     rdx, rbx; struct GpDevice *
0x1800ccd3f  mov     rcx, rax; this
0x1800ccd42  call    ??0DriverD3D@@QEAA@PEAVGpDevice@@@Z; DriverD3D::DriverD3D(GpDevice *)
0x1800ccd47  mov     cs:?D3DDriver@Globals@@3PEAVDpDriver@@EA, rax; DpDriver * Globals::D3DDriver
0x1800ccd4e  lea     rcx, ?D3DDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::D3DDriver
0x1800ccd55  call    ??$CheckValid@VDpDriver@@@@YAHAEAPEAVDpDriver@@@Z; CheckValid<DpDriver>(DpDriver * &)
0x1800ccd5a  test    eax, eax
0x1800ccd5c  jz      loc_1800CD0C3
0x1800ccd62  xor     edx, edx
0x1800ccd64  lea     ecx, [rdx+28h]
0x1800ccd67  call    GpMallocEx
0x1800ccd6c  test    rax, rax
0x1800ccd6f  jz      short loc_1800CCD7C
0x1800ccd71  mov     rdx, rbx; struct GpDevice *
0x1800ccd74  mov     rcx, rax; this
0x1800ccd77  call    ??0DriverInfo@@QEAA@PEAVGpDevice@@@Z; DriverInfo::DriverInfo(GpDevice *)
0x1800ccd7c  mov     cs:?InfoDriver@Globals@@3PEAVDpDriver@@EA, rax; DpDriver * Globals::InfoDriver
0x1800ccd83  lea     rcx, ?InfoDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::InfoDriver
0x1800ccd8a  call    ??$CheckValid@VDpDriver@@@@YAHAEAPEAVDpDriver@@@Z; CheckValid<DpDriver>(DpDriver * &)
0x1800ccd8f  test    eax, eax
0x1800ccd91  jz      loc_1800CD0C3
0x1800ccd97  xor     edx, edx
0x1800ccd99  lea     ecx, [rdx+78h]
0x1800ccd9c  call    GpMallocEx
0x1800ccda1  test    rax, rax
0x1800ccda4  jz      short loc_1800CCDB1
0x1800ccda6  mov     rdx, rbx; struct GpDevice *
0x1800ccda9  mov     rcx, rax; this
0x1800ccdac  call    ??0DriverMeta@@QEAA@PEAVGpDevice@@H@Z; DriverMeta::DriverMeta(GpDevice *,int)
0x1800ccdb1  mov     cs:?MetaDriver@Globals@@3PEAVDpDriver@@EA, rax; DpDriver * Globals::MetaDriver
0x1800ccdb8  lea     rcx, ?MetaDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::MetaDriver
0x1800ccdbf  call    ??$CheckValid@VDpDriver@@@@YAHAEAPEAVDpDriver@@@Z; CheckValid<DpDriver>(DpDriver * &)
0x1800ccdc4  test    eax, eax
0x1800ccdc6  jz      loc_1800CD0C3
0x1800ccdcc  xor     edx, edx
0x1800ccdce  mov     edi, 88h
0x1800ccdd3  mov     ecx, edi
0x1800ccdd5  call    GpMallocEx
0x1800ccdda  test    rax, rax
0x1800ccddd  jz      short loc_1800CCDE9
0x1800ccddf  xor     edx, edx; HDC
0x1800ccde1  mov     rcx, rax; this
0x1800ccde4  call    ??0DpBitmap@@QEAA@PEAUHDC__@@@Z; DpBitmap::DpBitmap(HDC__ *)
0x1800ccde9  mov     cs:?DesktopSurface@Globals@@3PEAVDpBitmap@@EA, rax; DpBitmap * Globals::DesktopSurface
0x1800ccdf0  lea     rcx, ?DesktopSurface@Globals@@3PEAVDpBitmap@@EA; DpBitmap * Globals::DesktopSurface
0x1800ccdf7  call    ??$CheckValid@VDpBitmap@@@@YAHAEAPEAVDpBitmap@@@Z; CheckValid<DpBitmap>(DpBitmap * &)
0x1800ccdfc  test    eax, eax
0x1800ccdfe  jz      loc_1800CD0C3
0x1800cce04  mov     ecx, 4Eh ; 'N'; nIndex
0x1800cce09  call    cs:__imp_GetSystemMetrics
0x1800cce10  nop     dword ptr [rax+rax+00h]
0x1800cce15  mov     ebx, eax
0x1800cce17  mov     ecx, 4Fh ; 'O'; nIndex
0x1800cce1c  call    cs:__imp_GetSystemMetrics
0x1800cce23  nop     dword ptr [rax+rax+00h]
0x1800cce28  test    ebx, ebx
0x1800cce2a  jz      short loc_1800CCE30
0x1800cce2c  test    eax, eax
0x1800cce2e  jnz     short loc_1800CCE4E
0x1800cce30  xor     ecx, ecx; nIndex
0x1800cce32  call    cs:__imp_GetSystemMetrics
0x1800cce39  nop     dword ptr [rax+rax+00h]
0x1800cce3e  mov     ebx, eax
0x1800cce40  mov     ecx, esi; nIndex
0x1800cce42  call    cs:__imp_GetSystemMetrics
0x1800cce49  nop     dword ptr [rax+rax+00h]
0x1800cce4e  mov     r9d, eax; int
0x1800cce51  mov     r8d, ebx; int
0x1800cce54  call    ?InitializeForGdiScreen@DpBitmap@@QEAAXPEAVGpDevice@@HH@Z; DpBitmap::InitializeForGdiScreen(GpDevice *,int,int)
0x1800cce59  mov     rcx, cs:?DesktopDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::DesktopDriver
0x1800cce60  mov     rax, [rcx]
0x1800cce63  mov     rdx, cs:?DesktopSurface@Globals@@3PEAVDpBitmap@@EA; DpBitmap * Globals::DesktopSurface
0x1800cce6a  mov     rax, [rax+10h]
0x1800cce6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cce73  mov     cs:?g_fRemoteSession@Globals@@3HA, 0; int Globals::g_fRemoteSession
0x1800cce7d  mov     cs:?g_pRemoteSurface@Globals@@3PEAVDpBitmap@@EA, 0; DpBitmap * Globals::g_pRemoteSurface
0x1800cce88  mov     cs:?g_pTSDriver@Globals@@3PEAVDpDriver@@EA, 0; DpDriver * Globals::g_pTSDriver
0x1800cce93  mov     rax, cs:__imp_DrawEscape
0x1800cce9a  mov     cs:?g_pfnTestDrawEscapeFunction@Globals@@3P6AHPEAUHDC__@@HHPEBD@ZEA, rax; int (*Globals::g_pfnTestDrawEscapeFunction)(HDC__ *,int,int,char const *)
0x1800ccea1  xor     edx, edx
0x1800ccea3  mov     rcx, rdi
0x1800ccea6  call    GpMallocEx
0x1800cceab  test    rax, rax
0x1800cceae  jz      short loc_1800CCEBA
0x1800cceb0  xor     edx, edx; HDC
  ... truncated ...
```
