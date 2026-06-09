# InternalGdiplusShutdown(void)

- ea: `0x1800e8688`
- end: `0x1800e8cc2`
- name: `?InternalGdiplusShutdown@@YAPEAXXZ`
- size: `1594`
- prototype: `void *(void)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update`

## callers

- `0x1800c8290`
- `0x1800e2458`

## callees

- `0x18000e580`
- `0x18000e6d0`
- `0x18001f950`
- `0x180090180`
- `0x1800d7898`
- `0x1800e58c4`
- `0x1800e8688`
- `0x1800e9774`
- `0x180108b80`
- `0x180114284`
- `0x18014a2e0`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e88cb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e8c00`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e88cb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e8c00`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e892b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e892b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e8986`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e8986`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e8a4c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e8ac5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e8c30`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e8c51`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e8c72`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e8a4c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e8ac5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e8c30`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e8c51`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e8c72`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1800e8c90`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1800e8c90`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800e86b4`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800e86b4`
- `GDI32!DeleteDC` at `0x1800e8909`
- `GDI32!DeleteDC` at `0x1800e8909`
- `GDI32!DeleteObject` at `0x1800e88ea`
- `GDI32!DeleteObject` at `0x1800e88ea`

## pseudocode

```c
void *InternalGdiplusShutdown(void)
{
  REGHANDLE v0; // rcx
  void *v1; // rsi
  unsigned int v2; // edx
  void *v3; // rbx
  GpFontLink *v4; // rbx
  struct CachedCodecInfo *v5; // rax
  struct CachedCodecInfo *v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // rax
  ols *v9; // rdi
  ols *v10; // rbx
  void *result; // rax

  v0 = RegHandle;
  v1 = 0;
  dword_1801B2190 = 0;
  RegHandle = 0;
  EventUnregister(v0);
  if ( Globals::BackgroundThreadHandle )
    v1 = BackgroundThreadShutdown();
  if ( Globals::PathLookAside )
    (**(void (__fastcall ***)(struct GpPath *, __int64))Globals::PathLookAside)(Globals::PathLookAside, 1);
  Globals::PathLookAside = 0;
  if ( Globals::MatrixLookAside )
    GpMatrix::`scalar deleting destructor'(Globals::MatrixLookAside, v2);
  Globals::MatrixLookAside = 0;
  if ( Globals::PenLookAside )
    (**(void (__fastcall ***)(struct GpPen *, __int64))Globals::PenLookAside)(Globals::PenLookAside, 1);
  Globals::PenLookAside = 0;
  if ( Globals::DesktopDevice )
    (**(void (__fastcall ***)(struct GpDevice *, __int64))Globals::DesktopDevice)(Globals::DesktopDevice, 1);
  v3 = Globals::DeviceList;
  Globals::DesktopDevice = 0;
  if ( Globals::DeviceList )
  {
    GpFree(*((_QWORD *)Globals::DeviceList + 1));
    operator delete(v3, 0x10u);
  }
  Globals::DeviceList = 0;
  if ( Globals::EngineDriver )
    (**(void (__fastcall ***)(struct DpDriver *, __int64))Globals::EngineDriver)(Globals::EngineDriver, 1);
  Globals::EngineDriver = 0;
  if ( Globals::DesktopDriver )
    (**(void (__fastcall ***)(struct DpDriver *, __int64))Globals::DesktopDriver)(Globals::DesktopDriver, 1);
  Globals::DesktopDriver = 0;
  if ( Globals::GdiDriver )
    (**(void (__fastcall ***)(struct DpDriver *, __int64))Globals::GdiDriver)(Globals::GdiDriver, 1);
  Globals::GdiDriver = 0;
  if ( Globals::D3DDriver )
    (**(void (__fastcall ***)(struct DpDriver *, __int64))Globals::D3DDriver)(Globals::D3DDriver, 1);
  Globals::D3DDriver = 0;
  if ( Globals::InfoDriver )
    (**(void (__fastcall ***)(struct DpDriver *, __int64))Globals::InfoDriver)(Globals::InfoDriver, 1);
  Globals::InfoDriver = 0;
  if ( Globals::MetaDriver )
    (**(void (__fastcall ***)(struct DpDriver *, __int64))Globals::MetaDriver)(Globals::MetaDriver, 1);
  Globals::MetaDriver = 0;
  if ( Globals::DesktopSurface )
    DpBitmap::`scalar deleting destructor'(Globals::DesktopSurface);
  Globals::DesktopSurface = 0;
  if ( Globals::g_pTSDriver )
    (**(void (__fastcall ***)(struct DpDriver *, __int64))Globals::g_pTSDriver)(Globals::g_pTSDriver, 1);
  Globals::g_pTSDriver = 0;
  if ( Globals::g_pTSGraphics )
  {
    GpGraphics::`scalar deleting destructor'(Globals::g_pTSGraphics, v2);
    Globals::g_pTSGraphics = 0;
  }
  if ( Globals::g_pITSClientPlayer )
  {
    (**(void (__fastcall ***)(struct IMetafilePlayer *, __int64))Globals::g_pITSClientPlayer)(
      Globals::g_pITSClientPlayer,
      1);
    Globals::g_pITSClientPlayer = 0;
  }
  if ( Globals::g_pRemoteSurface )
  {
    DpBitmap::`scalar deleting destructor'(Globals::g_pRemoteSurface);
    Globals::g_pRemoteSurface = 0;
  }
  if ( Globals::DdrawHandle )
  {
    FreeLibrary(Globals::DdrawHandle);
    Globals::DdrawHandle = 0;
  }
  if ( Globals::CachedGdiRegion )
  {
    DeleteObject(Globals::CachedGdiRegion);
    Globals::CachedGdiRegion = 0;
  }
  if ( Globals::DesktopIc )
  {
    DeleteDC(Globals::DesktopIc);
    Globals::DesktopIc = 0;
  }
  if ( Globals::TextCriticalSectionInitialized )
  {
    EnterCriticalSection(&Globals::TextCriticalSection);
    if ( Globals::FontCollection )
      (**(void (__fastcall ***)(struct GpFontCollection *, __int64))Globals::FontCollection)(Globals::FontCollection, 1);
    v4 = Globals::DWriteFontLinkTable;
    Globals::FontCollection = 0;
    if ( Globals::DWriteFontLinkTable )
    {
      GpFontLink::~GpFontLink(Globals::DWriteFontLinkTable);
      operator delete(v4, 0x40u);
      Globals::DWriteFontLinkTable = 0;
    }
    LeaveCriticalSection(&Globals::TextCriticalSection);
  }
  if ( (unsigned __int64)Globals::DWriteSurrogateFontsTable - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    GpFree(Globals::DWriteSurrogateFontsTable);
  Globals::DWriteSurrogateFontsTable = (struct GpFontFamily **)-1LL;
  if ( Globals::DWriteFontCacheLastRecentlyUsedList )
    operator delete(Globals::DWriteFontCacheLastRecentlyUsedList, 0x10u);
  Globals::DWriteFontCacheLastRecentlyUsedList = 0;
  Globals::GenericSansSerifFamily = 0;
  Globals::GenericSerifFamily = 0;
  Globals::GenericMonospaceFamily = 0;
  if ( Globals::NationalDigitCache )
    IntMap<unsigned char>::`scalar deleting destructor'(Globals::NationalDigitCache);
  Globals::NationalDigitCache = 0;
  GpStringFormat::DestroyStaticObjects();
  GpFree(Globals::FontsDirW);
  Globals::FontsDirW = 0;
  GpFree(Globals::FontsDirA);
  Globals::FontsDirA = 0;
  if ( Globals::LookAsideBuffer )
  {
    GpFree(Globals::LookAsideBuffer);
    Globals::LookAsideBuffer = 0;
  }
  if ( Globals::TextCriticalSectionInitialized )
  {
    DeleteCriticalSection(&Globals::TextCriticalSection);
    Globals::TextCriticalSectionInitialized = 0;
  }
  v5 = CachedCodecs;
  v6 = CachedCodecs;
  if ( CachedCodecs )
  {
    do
    {
      v7 = *((_QWORD *)v6 + 13);
      if ( *((_DWORD *)v6 + 18) )
      {
        if ( v6 == v5 )
          CachedCodecs = (struct CachedCodecInfo *)*((_QWORD *)v6 + 13);
        if ( v7 )
          *(_QWORD *)(v7 + 112) = *((_QWORD *)v6 + 14);
        v8 = *((_QWORD *)v6 + 14);
        if ( v8 )
          *(_QWORD *)(v8 + 104) = v7;
        GpFree(v6);
        v5 = CachedCodecs;
        CodecCacheUpdated = 1;
      }
      v6 = (struct CachedCodecInfo *)v7;
    }
    while ( v7 );
  }
  if ( ImagingCritSec::initialized )
  {
    DeleteCriticalSection(&ImagingCritSec::critSec);
    ImagingCritSec::initialized = 0;
  }
  v9 = qword_1801B3CA8;
  if ( qword_1801B3CA8 )
  {
    do
    {
      v10 = (ols *)*((_QWORD *)v9 + 2);
      ols::~ols(v9);
      operator delete(v9, 0x20u);
      v9 = v10;
    }
    while ( v10 );
  }
  qword_1801B3CA8 = 0;
  if ( Globals::g_DWriteTextAnalyzer )
  {
    (*(void (__fastcall **)(struct IDWriteTextAnalyzer *))(*(_QWORD *)Globals::g_DWriteTextAnalyzer + 16LL))(Globals::g_DWriteTextAnalyzer);
    Globals::g_DWriteTextAnalyzer = 0;
  }
  if ( Globals::g_GpFontFileLoader )
  {
    (*(void (__fastcall **)(struct IDWriteFactory *))(*(_QWORD *)Globals::g_DWriteFactory + 112LL))(Globals::g_DWriteFactory);
    (*(void (__fastcall **)(struct IDWriteFontFileLoader *))(*(_QWORD *)Globals::g_GpFontFileLoader + 16LL))(Globals::g_GpFontFileLoader);
    Globals::g_GpFontFileLoader = 0;
  }
  if ( Globals::g_GpFontCollectionStreamLoader )
  {
    (*(void (__fastcall **)(struct IDWriteFactory *))(*(_QWORD *)Globals::g_DWriteFactory + 48LL))(Globals::g_DWriteFactory);
    (*(void (__fastcall **)(struct IDWriteFontCollectionLoader *))(*(_QWORD *)Globals::g_GpFontCollectionStreamLoader
                                                                 + 16LL))(Globals::g_GpFontCollectionStreamLoader);
    Globals::g_GpFontCollectionStreamLoader = 0;
  }
  if ( Globals::g_GpFontCollectionFileLoader )
  {
    (*(void (__fastcall **)(struct IDWriteFactory *))(*(_QWORD *)Globals::g_DWriteFactory + 48LL))(Globals::g_DWriteFactory);
    (*(void (__fastcall **)(struct IDWriteFontCollectionLoader *))(*(_QWORD *)Globals::g_GpFontCollectionFileLoader
                                                                 + 16LL))(Globals::g_GpFontCollectionFileLoader);
    Globals::g_GpFontCollectionFileLoader = 0;
  }
  if ( Globals::g_DWriteFactory )
  {
    (*(void (__fastcall **)(struct IDWriteFactory *))(*(_QWORD *)Globals::g_DWriteFactory + 16LL))(Globals::g_DWriteFactory);
    Globals::g_DWriteFactory = 0;
  }
  if ( Globals::UniscribeDllModule )
  {
    FreeLibrary(Globals::UniscribeDllModule);
    Globals::UniscribeDllModule = 0;
  }
  if ( Globals::RuntimeInitialized )
    Globals::RuntimeInitialized = 0;
  if ( LoadLibraryCriticalSection::initialized )
  {
    DeleteCriticalSection(&LoadLibraryCriticalSection::critSec);
    LoadLibraryCriticalSection::initialized = 0;
  }
  if ( BackgroundThreadCriticalSection::initialized )
  {
    DeleteCriticalSection(&BackgroundThreadCriticalSection::critSec);
    BackgroundThreadCriticalSection::initialized = 0;
  }
  if ( GpMallocTrackingCriticalSection::initialized )
  {
    DeleteCriticalSection(&GpMallocTrackingCriticalSection::critSec);
    GpMallocTrackingCriticalSection::initialized = 0;
  }
  if ( GpRuntime::GpMemHeap )
  {
    HeapDestroy(GpRuntime::GpMemHeap);
    GpRuntime::GpMemHeap = 0;
  }
  result = v1;
  CPUSpecificOps::Initialized = 0;
  return result;
}

```

## disassembly

```asm
0x1800e8688  mov     [rsp+arg_0], rbx
0x1800e868d  mov     [rsp+arg_8], rbp
0x1800e8692  mov     [rsp+arg_10], rsi
0x1800e8697  push    rdi
0x1800e8698  sub     rsp, 20h
0x1800e869c  mov     rcx, cs:RegHandle; RegHandle
0x1800e86a3  xor     ebp, ebp
0x1800e86a5  mov     esi, ebp
0x1800e86a7  mov     cs:dword_1801B2190, ebp
0x1800e86ad  mov     cs:RegHandle, rbp
0x1800e86b4  call    cs:__imp_EventUnregister
0x1800e86bb  nop     dword ptr [rax+rax+00h]
0x1800e86c0  cmp     cs:?BackgroundThreadHandle@Globals@@3PEAXEA, rbp; void * Globals::BackgroundThreadHandle
0x1800e86c7  jz      short loc_1800E86D1
0x1800e86c9  call    ?BackgroundThreadShutdown@@YAPEAXXZ; BackgroundThreadShutdown(void)
0x1800e86ce  mov     rsi, rax
0x1800e86d1  mov     rcx, cs:?PathLookAside@Globals@@3PEAVGpPath@@EA; GpPath * Globals::PathLookAside
0x1800e86d8  mov     edi, 1
0x1800e86dd  test    rcx, rcx
0x1800e86e0  jz      short loc_1800E86EF
0x1800e86e2  mov     rdx, [rcx]
0x1800e86e5  mov     rax, [rdx]
0x1800e86e8  mov     edx, edi
0x1800e86ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e86ef  mov     rcx, cs:?MatrixLookAside@Globals@@3PEAVGpMatrix@@EA; this
0x1800e86f6  mov     cs:?PathLookAside@Globals@@3PEAVGpPath@@EA, rbp; GpPath * Globals::PathLookAside
0x1800e86fd  test    rcx, rcx
0x1800e8700  jz      short loc_1800E8707
0x1800e8702  call    ??_GGpMatrix@@QEAAPEAXI@Z; GpMatrix::`scalar deleting destructor'(uint)
0x1800e8707  mov     rcx, cs:?PenLookAside@Globals@@3PEAVGpPen@@EA; GpPen * Globals::PenLookAside
0x1800e870e  mov     cs:?MatrixLookAside@Globals@@3PEAVGpMatrix@@EA, rbp; GpMatrix * Globals::MatrixLookAside
0x1800e8715  test    rcx, rcx
0x1800e8718  jz      short loc_1800E8727
0x1800e871a  mov     rax, [rcx]
0x1800e871d  mov     edx, edi
0x1800e871f  mov     rax, [rax]
0x1800e8722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8727  mov     rcx, cs:?DesktopDevice@Globals@@3PEAVGpDevice@@EA; GpDevice * Globals::DesktopDevice
0x1800e872e  mov     cs:?PenLookAside@Globals@@3PEAVGpPen@@EA, rbp; GpPen * Globals::PenLookAside
0x1800e8735  test    rcx, rcx
0x1800e8738  jz      short loc_1800E8747
0x1800e873a  mov     rax, [rcx]
0x1800e873d  mov     edx, edi
0x1800e873f  mov     rax, [rax]
0x1800e8742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8747  mov     rbx, cs:?DeviceList@Globals@@3PEAVGpDeviceList@@EA; GpDeviceList * Globals::DeviceList
0x1800e874e  mov     cs:?DesktopDevice@Globals@@3PEAVGpDevice@@EA, rbp; GpDevice * Globals::DesktopDevice
0x1800e8755  test    rbx, rbx
0x1800e8758  jz      short loc_1800E8770
0x1800e875a  mov     rcx, [rbx+8]
0x1800e875e  call    GpFree
0x1800e8763  mov     edx, 10h; unsigned __int64
0x1800e8768  mov     rcx, rbx; void *
0x1800e876b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e8770  mov     rcx, cs:?EngineDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::EngineDriver
0x1800e8777  mov     cs:?DeviceList@Globals@@3PEAVGpDeviceList@@EA, rbp; GpDeviceList * Globals::DeviceList
0x1800e877e  test    rcx, rcx
0x1800e8781  jz      short loc_1800E8790
0x1800e8783  mov     rax, [rcx]
0x1800e8786  mov     edx, edi
0x1800e8788  mov     rax, [rax]
0x1800e878b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8790  mov     rcx, cs:?DesktopDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::DesktopDriver
0x1800e8797  mov     cs:?EngineDriver@Globals@@3PEAVDpDriver@@EA, rbp; DpDriver * Globals::EngineDriver
0x1800e879e  test    rcx, rcx
0x1800e87a1  jz      short loc_1800E87B0
0x1800e87a3  mov     rax, [rcx]
0x1800e87a6  mov     edx, edi
0x1800e87a8  mov     rax, [rax]
0x1800e87ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e87b0  mov     rcx, cs:?GdiDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::GdiDriver
0x1800e87b7  mov     cs:?DesktopDriver@Globals@@3PEAVDpDriver@@EA, rbp; DpDriver * Globals::DesktopDriver
0x1800e87be  test    rcx, rcx
0x1800e87c1  jz      short loc_1800E87D0
0x1800e87c3  mov     rax, [rcx]
0x1800e87c6  mov     edx, edi
0x1800e87c8  mov     rax, [rax]
0x1800e87cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e87d0  mov     rcx, cs:?D3DDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::D3DDriver
0x1800e87d7  mov     cs:?GdiDriver@Globals@@3PEAVDpDriver@@EA, rbp; DpDriver * Globals::GdiDriver
0x1800e87de  test    rcx, rcx
0x1800e87e1  jz      short loc_1800E87F0
0x1800e87e3  mov     rax, [rcx]
0x1800e87e6  mov     edx, edi
0x1800e87e8  mov     rax, [rax]
0x1800e87eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e87f0  mov     rcx, cs:?InfoDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::InfoDriver
0x1800e87f7  mov     cs:?D3DDriver@Globals@@3PEAVDpDriver@@EA, rbp; DpDriver * Globals::D3DDriver
0x1800e87fe  test    rcx, rcx
0x1800e8801  jz      short loc_1800E8810
0x1800e8803  mov     rax, [rcx]
0x1800e8806  mov     edx, edi
0x1800e8808  mov     rax, [rax]
0x1800e880b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8810  mov     rcx, cs:?MetaDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::MetaDriver
0x1800e8817  mov     cs:?InfoDriver@Globals@@3PEAVDpDriver@@EA, rbp; DpDriver * Globals::InfoDriver
0x1800e881e  test    rcx, rcx
0x1800e8821  jz      short loc_1800E8830
0x1800e8823  mov     rax, [rcx]
0x1800e8826  mov     edx, edi
0x1800e8828  mov     rax, [rax]
0x1800e882b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8830  mov     rcx, cs:?DesktopSurface@Globals@@3PEAVDpBitmap@@EA; this
0x1800e8837  mov     cs:?MetaDriver@Globals@@3PEAVDpDriver@@EA, rbp; DpDriver * Globals::MetaDriver
0x1800e883e  test    rcx, rcx
0x1800e8841  jz      short loc_1800E8848
0x1800e8843  call    ??_GDpBitmap@@QEAAPEAXI@Z; DpBitmap::`scalar deleting destructor'(uint)
0x1800e8848  mov     rcx, cs:?g_pTSDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::g_pTSDriver
0x1800e884f  mov     cs:?DesktopSurface@Globals@@3PEAVDpBitmap@@EA, rbp; DpBitmap * Globals::DesktopSurface
0x1800e8856  test    rcx, rcx
0x1800e8859  jz      short loc_1800E8868
0x1800e885b  mov     rax, [rcx]
0x1800e885e  mov     edx, edi
0x1800e8860  mov     rax, [rax]
0x1800e8863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8868  mov     rcx, cs:?g_pTSGraphics@Globals@@3PEAVGpGraphics@@EA; this
0x1800e886f  mov     cs:?g_pTSDriver@Globals@@3PEAVDpDriver@@EA, rbp; DpDriver * Globals::g_pTSDriver
0x1800e8876  test    rcx, rcx
0x1800e8879  jz      short loc_1800E8887
0x1800e887b  call    ??_GGpGraphics@@QEAAPEAXI@Z; GpGraphics::`scalar deleting destructor'(uint)
0x1800e8880  mov     cs:?g_pTSGraphics@Globals@@3PEAVGpGraphics@@EA, rbp; GpGraphics * Globals::g_pTSGraphics
0x1800e8887  mov     rcx, cs:?g_pITSClientPlayer@Globals@@3PEAVIMetafilePlayer@@EA; IMetafilePlayer * Globals::g_pITSClientPlayer
0x1800e888e  test    rcx, rcx
0x1800e8891  jz      short loc_1800E88A7
0x1800e8893  mov     rax, [rcx]
0x1800e8896  mov     edx, edi
0x1800e8898  mov     rax, [rax]
0x1800e889b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e88a0  mov     cs:?g_pITSClientPlayer@Globals@@3PEAVIMetafilePlayer@@EA, rbp; IMetafilePlayer * Globals::g_pITSClientPlayer
0x1800e88a7  mov     rcx, cs:?g_pRemoteSurface@Globals@@3PEAVDpBitmap@@EA; this
0x1800e88ae  test    rcx, rcx
0x1800e88b1  jz      short loc_1800E88BF
0x1800e88b3  call    ??_GDpBitmap@@QEAAPEAXI@Z; DpBitmap::`scalar deleting destructor'(uint)
0x1800e88b8  mov     cs:?g_pRemoteSurface@Globals@@3PEAVDpBitmap@@EA, rbp; DpBitmap * Globals::g_pRemoteSurface
0x1800e88bf  mov     rcx, cs:?DdrawHandle@Globals@@3PEAUHINSTANCE__@@EA; hLibModule
0x1800e88c6  test    rcx, rcx
0x1800e88c9  jz      short loc_1800E88DE
0x1800e88cb  call    cs:__imp_FreeLibrary
0x1800e88d2  nop     dword ptr [rax+rax+00h]
0x1800e88d7  mov     cs:?DdrawHandle@Globals@@3PEAUHINSTANCE__@@EA, rbp; HINSTANCE__ * Globals::DdrawHandle
0x1800e88de  mov     rcx, cs:?CachedGdiRegion@Globals@@3PEAUHRGN__@@EA; ho
0x1800e88e5  test    rcx, rcx
0x1800e88e8  jz      short loc_1800E88FD
0x1800e88ea  call    cs:__imp_DeleteObject
0x1800e88f1  nop     dword ptr [rax+rax+00h]
0x1800e88f6  mov     cs:?CachedGdiRegion@Globals@@3PEAUHRGN__@@EA, rbp; HRGN__ * Globals::CachedGdiRegion
0x1800e88fd  mov     rcx, cs:?DesktopIc@Globals@@3PEAUHDC__@@EA; hdc
0x1800e8904  test    rcx, rcx
0x1800e8907  jz      short loc_1800E891C
0x1800e8909  call    cs:__imp_DeleteDC
0x1800e8910  nop     dword ptr [rax+rax+00h]
0x1800e8915  mov     cs:?DesktopIc@Globals@@3PEAUHDC__@@EA, rbp; HDC__ * Globals::DesktopIc
0x1800e891c  cmp     cs:?TextCriticalSectionInitialized@Globals@@3HA, ebp; int Globals::TextCriticalSectionInitialized
0x1800e8922  jz      short loc_1800E8992
0x1800e8924  lea     rcx, ?TextCriticalSection@Globals@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800e892b  call    cs:__imp_EnterCriticalSection
0x1800e8932  nop     dword ptr [rax+rax+00h]
0x1800e8937  mov     rcx, cs:?FontCollection@Globals@@3PEAVGpInstalledFontCollection@@EA; GpInstalledFontCollection * Globals::FontCollection
0x1800e893e  test    rcx, rcx
0x1800e8941  jz      short loc_1800E8950
0x1800e8943  mov     rax, [rcx]
0x1800e8946  mov     edx, edi
0x1800e8948  mov     rax, [rax]
0x1800e894b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8950  mov     rbx, cs:?DWriteFontLinkTable@Globals@@3PEAVGpFontLink@@EA; GpFontLink * Globals::DWriteFontLinkTable
0x1800e8957  mov     cs:?FontCollection@Globals@@3PEAVGpInstalledFontCollection@@EA, rbp; GpInstalledFontCollection * Globals::FontCollection
0x1800e895e  test    rbx, rbx
0x1800e8961  jz      short loc_1800E897F
0x1800e8963  mov     rcx, rbx; this
0x1800e8966  call    ??1GpFontLink@@QEAA@XZ; GpFontLink::~GpFontLink(void)
0x1800e896b  mov     edx, 40h ; '@'; unsigned __int64
0x1800e8970  mov     rcx, rbx; void *
0x1800e8973  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e8978  mov     cs:?DWriteFontLinkTable@Globals@@3PEAVGpFontLink@@EA, rbp; GpFontLink * Globals::DWriteFontLinkTable
0x1800e897f  lea     rcx, ?TextCriticalSection@Globals@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800e8986  call    cs:__imp_LeaveCriticalSection
0x1800e898d  nop     dword ptr [rax+rax+00h]
0x1800e8992  mov     rcx, cs:?DWriteSurrogateFontsTable@Globals@@3PEAPEAVGpFontFamily@@EA; GpFontFamily * * Globals::DWriteSurrogateFontsTable
0x1800e8999  lea     rax, [rcx-1]
0x1800e899d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800e89a1  ja      short loc_1800E89A8
0x1800e89a3  call    GpFree
0x1800e89a8  or      cs:?DWriteSurrogateFontsTable@Globals@@3PEAPEAVGpFontFamily@@EA, 0FFFFFFFFFFFFFFFFh; GpFontFamily * * Globals::DWriteSurrogateFontsTable
0x1800e89b0  mov     rcx, cs:?DWriteFontCacheLastRecentlyUsedList@Globals@@3PEAVGpCacheFaceRealizationList@@EA; void *
0x1800e89b7  test    rcx, rcx
0x1800e89ba  jz      short loc_1800E89C6
0x1800e89bc  mov     edx, 10h; unsigned __int64
0x1800e89c1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e89c6  mov     rcx, cs:?NationalDigitCache@Globals@@3PEAV?$IntMap@E@@EA; void *
0x1800e89cd  mov     cs:?DWriteFontCacheLastRecentlyUsedList@Globals@@3PEAVGpCacheFaceRealizationList@@EA, rbp; GpCacheFaceRealizationList * Globals::DWriteFontCacheLastRecentlyUsedList
0x1800e89d4  mov     cs:?GenericSansSerifFamily@Globals@@3PEAVGpFontFamily@@EA, rbp; GpFontFamily * Globals::GenericSansSerifFamily
0x1800e89db  mov     cs:?GenericSerifFamily@Globals@@3PEAVGpFontFamily@@EA, rbp; GpFontFamily * Globals::GenericSerifFamily
0x1800e89e2  mov     cs:?GenericMonospaceFamily@Globals@@3PEAVGpFontFamily@@EA, rbp; GpFontFamily * Globals::GenericMonospaceFamily
0x1800e89e9  test    rcx, rcx
0x1800e89ec  jz      short loc_1800E89F3
0x1800e89ee  call    ??_G?$IntMap@E@@QEAAPEAXI@Z; IntMap<uchar>::`scalar deleting destructor'(uint)
0x1800e89f3  mov     cs:?NationalDigitCache@Globals@@3PEAV?$IntMap@E@@EA, rbp; IntMap<uchar> * Globals::NationalDigitCache
0x1800e89fa  call    ?DestroyStaticObjects@GpStringFormat@@SAXXZ; GpStringFormat::DestroyStaticObjects(void)
0x1800e89ff  mov     rcx, cs:?FontsDirW@Globals@@3PEAGEA; ushort * Globals::FontsDirW
0x1800e8a06  call    GpFree
0x1800e8a0b  mov     rcx, cs:?FontsDirA@Globals@@3PEADEA; char * Globals::FontsDirA
0x1800e8a12  mov     cs:?FontsDirW@Globals@@3PEAGEA, rbp; ushort * Globals::FontsDirW
0x1800e8a19  call    GpFree
0x1800e8a1e  mov     rcx, cs:?LookAsideBuffer@Globals@@3PEAEEA; uchar * Globals::LookAsideBuffer
0x1800e8a25  mov     cs:?FontsDirA@Globals@@3PEADEA, rbp; char * Globals::FontsDirA
0x1800e8a2c  test    rcx, rcx
0x1800e8a2f  jz      short loc_1800E8A3D
0x1800e8a31  call    GpFree
0x1800e8a36  mov     cs:?LookAsideBuffer@Globals@@3PEAEEA, rbp; uchar * Globals::LookAsideBuffer
0x1800e8a3d  cmp     cs:?TextCriticalSectionInitialized@Globals@@3HA, ebp; int Globals::TextCriticalSectionInitialized
0x1800e8a43  jz      short loc_1800E8A5E
0x1800e8a45  lea     rcx, ?TextCriticalSection@Globals@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800e8a4c  call    cs:__imp_DeleteCriticalSection
0x1800e8a53  nop     dword ptr [rax+rax+00h]
0x1800e8a58  mov     cs:?TextCriticalSectionInitialized@Globals@@3HA, ebp; int Globals::TextCriticalSectionInitialized
0x1800e8a5e  mov     rax, cs:?CachedCodecs@@3PEAUCachedCodecInfo@@EA; CachedCodecInfo * CachedCodecs
0x1800e8a65  mov     rcx, rax
0x1800e8a68  test    rax, rax
0x1800e8a6b  jz      short loc_1800E8AB6
0x1800e8a6d  mov     rbx, [rcx+68h]
0x1800e8a71  cmp     [rcx+48h], ebp
0x1800e8a74  jz      short loc_1800E8AAE
0x1800e8a76  cmp     rcx, rax
0x1800e8a79  jnz     short loc_1800E8A82
0x1800e8a7b  mov     cs:?CachedCodecs@@3PEAUCachedCodecInfo@@EA, rbx; CachedCodecInfo * CachedCodecs
0x1800e8a82  test    rbx, rbx
0x1800e8a85  jz      short loc_1800E8A8F
0x1800e8a87  mov     rax, [rcx+70h]
0x1800e8a8b  mov     [rbx+70h], rax
0x1800e8a8f  mov     rax, [rcx+70h]
0x1800e8a93  test    rax, rax
0x1800e8a96  jz      short loc_1800E8A9C
0x1800e8a98  mov     [rax+68h], rbx
0x1800e8a9c  call    GpFree
0x1800e8aa1  mov     rax, cs:?CachedCodecs@@3PEAUCachedCodecInfo@@EA; CachedCodecInfo * CachedCodecs
0x1800e8aa8  mov     cs:?CodecCacheUpdated@@3HA, edi; int CodecCacheUpdated
0x1800e8aae  mov     rcx, rbx
0x1800e8ab1  test    rbx, rbx
0x1800e8ab4  jnz     short loc_1800E8A6D
0x1800e8ab6  cmp     cs:?initialized@ImagingCritSec@@0HA, ebp; int ImagingCritSec::initialized
0x1800e8abc  jz      short loc_1800E8AD7
0x1800e8abe  lea     rcx, ?critSec@ImagingCritSec@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800e8ac5  call    cs:__imp_DeleteCriticalSection
0x1800e8acc  nop     dword ptr [rax+rax+00h]
0x1800e8ad1  mov     cs:?initialized@ImagingCritSec@@0HA, ebp; int ImagingCritSec::initialized
0x1800e8ad7  mov     rdi, cs:qword_1801B3CA8
0x1800e8ade  test    rdi, rdi
0x1800e8ae1  jz      short loc_1800E8B04
0x1800e8ae3  mov     rbx, [rdi+10h]
0x1800e8ae7  mov     rcx, rdi; this
0x1800e8aea  call    ??1ols@@QEAA@XZ; ols::~ols(void)
0x1800e8aef  mov     edx, 20h ; ' '; unsigned __int64
0x1800e8af4  mov     rcx, rdi; void *
0x1800e8af7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e8afc  mov     rdi, rbx
0x1800e8aff  test    rbx, rbx
0x1800e8b02  jnz     short loc_1800E8AE3
0x1800e8b04  mov     rcx, cs:?g_DWriteTextAnalyzer@Globals@@3PEAUIDWriteTextAnalyzer@@EA; IDWriteTextAnalyzer * Globals::g_DWriteTextAnalyzer
0x1800e8b0b  mov     cs:qword_1801B3CA8, rbp
0x1800e8b12  test    rcx, rcx
0x1800e8b15  jz      short loc_1800E8B2A
0x1800e8b17  mov     rax, [rcx]
0x1800e8b1a  mov     rax, [rax+10h]
0x1800e8b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8b23  mov     cs:?g_DWriteTextAnalyzer@Globals@@3PEAUIDWriteTextAnalyzer@@EA, rbp; IDWriteTextAnalyzer * Globals::g_DWriteTextAnalyzer
0x1800e8b2a  mov     rdx, cs:?g_GpFontFileLoader@Globals@@3PEAUIDWriteFontFileLoader@@EA; IDWriteFontFileLoader * Globals::g_GpFontFileLoader
0x1800e8b31  test    rdx, rdx
0x1800e8b34  jz      short loc_1800E8B63
0x1800e8b36  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x1800e8b3d  mov     rax, [rcx]
0x1800e8b40  mov     rax, [rax+70h]
0x1800e8b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8b49  mov     rcx, cs:?g_GpFontFileLoader@Globals@@3PEAUIDWriteFontFileLoader@@EA; IDWriteFontFileLoader * Globals::g_GpFontFileLoader
0x1800e8b50  mov     rax, [rcx]
0x1800e8b53  mov     rax, [rax+10h]
0x1800e8b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8b5c  mov     cs:?g_GpFontFileLoader@Globals@@3PEAUIDWriteFontFileLoader@@EA, rbp; IDWriteFontFileLoader * Globals::g_GpFontFileLoader
0x1800e8b63  mov     rdx, cs:?g_GpFontCollectionStreamLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionStreamLoader
0x1800e8b6a  test    rdx, rdx
0x1800e8b6d  jz      short loc_1800E8B9C
0x1800e8b6f  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x1800e8b76  mov     rax, [rcx]
0x1800e8b79  mov     rax, [rax+30h]
0x1800e8b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8b82  mov     rcx, cs:?g_GpFontCollectionStreamLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionStreamLoader
0x1800e8b89  mov     rax, [rcx]
0x1800e8b8c  mov     rax, [rax+10h]
0x1800e8b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8b95  mov     cs:?g_GpFontCollectionStreamLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA, rbp; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionStreamLoader
0x1800e8b9c  mov     rdx, cs:?g_GpFontCollectionFileLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionFileLoader
0x1800e8ba3  test    rdx, rdx
0x1800e8ba6  jz      short loc_1800E8BD5
0x1800e8ba8  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x1800e8baf  mov     rax, [rcx]
0x1800e8bb2  mov     rax, [rax+30h]
0x1800e8bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8bbb  mov     rcx, cs:?g_GpFontCollectionFileLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionFileLoader
0x1800e8bc2  mov     rax, [rcx]
0x1800e8bc5  mov     rax, [rax+10h]
0x1800e8bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
