# InternalGdiplusShutdown(void)

- ea: `0x1800cd478`
- end: `0x1800cdb1b`
- name: `?InternalGdiplusShutdown@@YAPEAXXZ`
- size: `1699`
- prototype: `void *(void)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x1800cc950`
- `0x1800cd3d0`

## callees

- `0x180010bd0`
- `0x180018c58`
- `0x180019490`
- `0x180019610`
- `0x1800cd478`
- `0x1800cdb24`
- `0x1800cdb54`
- `0x1800cdbc8`
- `0x1800cde74`
- `0x180106110`
- `0x18011fe6c`
- `0x180129c3c`
- `0x18014f974`
- `0x180172010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800cd9c7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800cdb03`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800cd9c7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800cdb03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cd87e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cd87e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cd8c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cd8c1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cd725`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cd74b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cd7f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cd812`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cd833`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cd725`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cd74b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cd7f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cd812`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cd833`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1800cd851`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1800cd851`
- `GDI32!DeleteDC` at `0x1800cd659`
- `GDI32!DeleteDC` at `0x1800cd659`
- `GDI32!DeleteObject` at `0x1800cd9df`
- `GDI32!DeleteObject` at `0x1800cd9df`

## pseudocode

```c
void *InternalGdiplusShutdown(void)
{
  void *v0; // rsi
  unsigned int v1; // edx
  void *v2; // rbx
  unsigned int v3; // ecx
  ols *v4; // rdi
  GpFontLink *v6; // rbx
  ols *v7; // rbx

  v0 = 0;
  TraceLoggingUnregister_EventUnregister();
  if ( Globals::BackgroundThreadHandle )
    v0 = BackgroundThreadShutdown();
  if ( Globals::PathLookAside )
    (**(void (__fastcall ***)(struct GpPath *, __int64))Globals::PathLookAside)(Globals::PathLookAside, 1);
  Globals::PathLookAside = 0;
  if ( Globals::MatrixLookAside )
    GpMatrix::`scalar deleting destructor'(Globals::MatrixLookAside, v1);
  Globals::MatrixLookAside = 0;
  if ( Globals::PenLookAside )
    (**(void (__fastcall ***)(struct GpPen *, __int64))Globals::PenLookAside)(Globals::PenLookAside, 1);
  Globals::PenLookAside = 0;
  if ( Globals::DesktopDevice )
    (**(void (__fastcall ***)(GpDevice *, __int64))Globals::DesktopDevice)(Globals::DesktopDevice, 1);
  v2 = Globals::DeviceList;
  Globals::DesktopDevice = 0;
  if ( Globals::DeviceList )
  {
    GpFree(*((_QWORD *)Globals::DeviceList + 1));
    operator delete(v2, 0x10u);
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
    DpBitmap::`scalar deleting destructor'(Globals::DesktopSurface, v1);
  Globals::DesktopSurface = 0;
  if ( Globals::g_pTSDriver )
    (**(void (__fastcall ***)(struct DpDriver *, __int64))Globals::g_pTSDriver)(Globals::g_pTSDriver, 1);
  Globals::g_pTSDriver = 0;
  if ( Globals::g_pTSGraphics )
  {
    GpGraphics::`scalar deleting destructor'(Globals::g_pTSGraphics, v1);
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
    DpBitmap::`scalar deleting destructor'(Globals::g_pRemoteSurface, v1);
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
    v6 = Globals::DWriteFontLinkTable;
    Globals::FontCollection = 0;
    if ( Globals::DWriteFontLinkTable )
    {
      GpFontLink::~GpFontLink(Globals::DWriteFontLinkTable);
      operator delete(v6, 0x40u);
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
  v3 = (unsigned int)Globals::LookAsideBuffer;
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
  FreeCachedCodecInfo(v3);
  if ( ImagingCritSec::initialized )
  {
    DeleteCriticalSection(&ImagingCritSec::critSec);
    ImagingCritSec::initialized = 0;
  }
  v4 = qword_1801AE708;
  if ( qword_1801AE708 )
  {
    do
    {
      v7 = (ols *)*((_QWORD *)v4 + 2);
      ols::~ols(v4);
      operator delete(v4, 0x20u);
      v4 = v7;
    }
    while ( v7 );
  }
  qword_1801AE708 = 0;
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
  CPUSpecificOps::Initialized = 0;
  return v0;
}

```

## disassembly

```asm
0x1800cd478  push    rbx
0x1800cd47a  push    rbp
0x1800cd47b  push    rsi
0x1800cd47c  push    rdi
0x1800cd47d  sub     rsp, 28h
0x1800cd481  xor     ebp, ebp
0x1800cd483  mov     esi, ebp
0x1800cd485  call    TraceLoggingUnregister_EventUnregister
0x1800cd48a  cmp     cs:?BackgroundThreadHandle@Globals@@3PEAXEA, rbp; void * Globals::BackgroundThreadHandle
0x1800cd491  jnz     loc_1800CD929
0x1800cd497  mov     rcx, cs:?PathLookAside@Globals@@3PEAVGpPath@@EA; GpPath * Globals::PathLookAside
0x1800cd49e  mov     edi, 1
0x1800cd4a3  test    rcx, rcx
0x1800cd4a6  jnz     loc_1800CD95D
0x1800cd4ac  mov     rcx, cs:?MatrixLookAside@Globals@@3PEAVGpMatrix@@EA; this
0x1800cd4b3  mov     cs:?PathLookAside@Globals@@3PEAVGpPath@@EA, rbp; GpPath * Globals::PathLookAside
0x1800cd4ba  test    rcx, rcx
0x1800cd4bd  jnz     loc_1800CD96F
0x1800cd4c3  mov     rcx, cs:?PenLookAside@Globals@@3PEAVGpPen@@EA; GpPen * Globals::PenLookAside
0x1800cd4ca  mov     cs:?MatrixLookAside@Globals@@3PEAVGpMatrix@@EA, rbp; GpMatrix * Globals::MatrixLookAside
0x1800cd4d1  test    rcx, rcx
0x1800cd4d4  jnz     loc_1800CD979
0x1800cd4da  mov     rcx, cs:?DesktopDevice@Globals@@3PEAVGpDevice@@EA; GpDevice * Globals::DesktopDevice
0x1800cd4e1  mov     cs:?PenLookAside@Globals@@3PEAVGpPen@@EA, rbp; GpPen * Globals::PenLookAside
0x1800cd4e8  test    rcx, rcx
0x1800cd4eb  jz      short loc_1800CD4FA
0x1800cd4ed  mov     rax, [rcx]
0x1800cd4f0  mov     edx, edi
0x1800cd4f2  mov     rax, [rax]
0x1800cd4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd4fa  mov     rbx, cs:?DeviceList@Globals@@3PEAVGpDeviceList@@EA; GpDeviceList * Globals::DeviceList
0x1800cd501  mov     cs:?DesktopDevice@Globals@@3PEAVGpDevice@@EA, rbp; GpDevice * Globals::DesktopDevice
0x1800cd508  test    rbx, rbx
0x1800cd50b  jnz     loc_1800CD8D2
0x1800cd511  mov     rcx, cs:?EngineDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::EngineDriver
0x1800cd518  mov     cs:?DeviceList@Globals@@3PEAVGpDeviceList@@EA, rbp; GpDeviceList * Globals::DeviceList
0x1800cd51f  test    rcx, rcx
0x1800cd522  jz      short loc_1800CD531
0x1800cd524  mov     rax, [rcx]
0x1800cd527  mov     edx, edi
0x1800cd529  mov     rax, [rax]
0x1800cd52c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd531  mov     rcx, cs:?DesktopDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::DesktopDriver
0x1800cd538  mov     cs:?EngineDriver@Globals@@3PEAVDpDriver@@EA, rbp; DpDriver * Globals::EngineDriver
0x1800cd53f  test    rcx, rcx
0x1800cd542  jnz     loc_1800CD8ED
0x1800cd548  mov     rcx, cs:?GdiDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::GdiDriver
0x1800cd54f  mov     cs:?DesktopDriver@Globals@@3PEAVDpDriver@@EA, rbp; DpDriver * Globals::DesktopDriver
0x1800cd556  test    rcx, rcx
0x1800cd559  jz      short loc_1800CD568
0x1800cd55b  mov     rax, [rcx]
0x1800cd55e  mov     edx, edi
0x1800cd560  mov     rax, [rax]
0x1800cd563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd568  mov     rcx, cs:?D3DDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::D3DDriver
0x1800cd56f  mov     cs:?GdiDriver@Globals@@3PEAVDpDriver@@EA, rbp; DpDriver * Globals::GdiDriver
0x1800cd576  test    rcx, rcx
0x1800cd579  jz      short loc_1800CD588
0x1800cd57b  mov     rax, [rcx]
0x1800cd57e  mov     edx, edi
0x1800cd580  mov     rax, [rax]
0x1800cd583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd588  mov     rcx, cs:?InfoDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::InfoDriver
0x1800cd58f  mov     cs:?D3DDriver@Globals@@3PEAVDpDriver@@EA, rbp; DpDriver * Globals::D3DDriver
0x1800cd596  test    rcx, rcx
0x1800cd599  jz      short loc_1800CD5A8
0x1800cd59b  mov     rax, [rcx]
0x1800cd59e  mov     edx, edi
0x1800cd5a0  mov     rax, [rax]
0x1800cd5a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd5a8  mov     rcx, cs:?MetaDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::MetaDriver
0x1800cd5af  mov     cs:?InfoDriver@Globals@@3PEAVDpDriver@@EA, rbp; DpDriver * Globals::InfoDriver
0x1800cd5b6  test    rcx, rcx
0x1800cd5b9  jz      short loc_1800CD5C8
0x1800cd5bb  mov     rax, [rcx]
0x1800cd5be  mov     edx, edi
0x1800cd5c0  mov     rax, [rax]
0x1800cd5c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd5c8  mov     rcx, cs:?DesktopSurface@Globals@@3PEAVDpBitmap@@EA; this
0x1800cd5cf  mov     cs:?MetaDriver@Globals@@3PEAVDpDriver@@EA, rbp; DpDriver * Globals::MetaDriver
0x1800cd5d6  test    rcx, rcx
0x1800cd5d9  jnz     loc_1800CD90E
0x1800cd5df  mov     rcx, cs:?g_pTSDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::g_pTSDriver
0x1800cd5e6  mov     cs:?DesktopSurface@Globals@@3PEAVDpBitmap@@EA, rbp; DpBitmap * Globals::DesktopSurface
0x1800cd5ed  test    rcx, rcx
0x1800cd5f0  jnz     loc_1800CD98B
0x1800cd5f6  mov     rcx, cs:?g_pTSGraphics@Globals@@3PEAVGpGraphics@@EA; this
0x1800cd5fd  mov     cs:?g_pTSDriver@Globals@@3PEAVDpDriver@@EA, rbp; DpDriver * Globals::g_pTSDriver
0x1800cd604  test    rcx, rcx
0x1800cd607  jnz     loc_1800CD99D
0x1800cd60d  mov     rcx, cs:?g_pITSClientPlayer@Globals@@3PEAVIMetafilePlayer@@EA; IMetafilePlayer * Globals::g_pITSClientPlayer
0x1800cd614  test    rcx, rcx
0x1800cd617  jnz     loc_1800CD9AE
0x1800cd61d  mov     rcx, cs:?g_pRemoteSurface@Globals@@3PEAVDpBitmap@@EA; this
0x1800cd624  test    rcx, rcx
0x1800cd627  jnz     loc_1800CD918
0x1800cd62d  mov     rcx, cs:?DdrawHandle@Globals@@3PEAUHINSTANCE__@@EA; hLibModule
0x1800cd634  test    rcx, rcx
0x1800cd637  jnz     loc_1800CD9C7
0x1800cd63d  mov     rcx, cs:?CachedGdiRegion@Globals@@3PEAUHRGN__@@EA; ho
0x1800cd644  test    rcx, rcx
0x1800cd647  jnz     loc_1800CD9DF
0x1800cd64d  mov     rcx, cs:?DesktopIc@Globals@@3PEAUHDC__@@EA; hdc
0x1800cd654  test    rcx, rcx
0x1800cd657  jz      short loc_1800CD66C
0x1800cd659  call    cs:__imp_DeleteDC
0x1800cd660  nop     dword ptr [rax+rax+00h]
0x1800cd665  mov     cs:?DesktopIc@Globals@@3PEAUHDC__@@EA, rbp; HDC__ * Globals::DesktopIc
0x1800cd66c  cmp     cs:?TextCriticalSectionInitialized@Globals@@3HA, ebp; int Globals::TextCriticalSectionInitialized
0x1800cd672  jnz     loc_1800CD877
0x1800cd678  mov     rcx, cs:?DWriteSurrogateFontsTable@Globals@@3PEAPEAVGpFontFamily@@EA; GpFontFamily * * Globals::DWriteSurrogateFontsTable
0x1800cd67f  lea     rax, [rcx-1]
0x1800cd683  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800cd687  jbe     loc_1800CDA18
0x1800cd68d  mov     rcx, cs:?DWriteFontCacheLastRecentlyUsedList@Globals@@3PEAVGpCacheFaceRealizationList@@EA; void *
0x1800cd694  mov     cs:?DWriteSurrogateFontsTable@Globals@@3PEAPEAVGpFontFamily@@EA, 0FFFFFFFFFFFFFFFFh; GpFontFamily * * Globals::DWriteSurrogateFontsTable
0x1800cd69f  test    rcx, rcx
0x1800cd6a2  jnz     loc_1800CD8FF
0x1800cd6a8  mov     rcx, cs:?NationalDigitCache@Globals@@3PEAV?$IntMap@E@@EA; void *
0x1800cd6af  mov     cs:?DWriteFontCacheLastRecentlyUsedList@Globals@@3PEAVGpCacheFaceRealizationList@@EA, rbp; GpCacheFaceRealizationList * Globals::DWriteFontCacheLastRecentlyUsedList
0x1800cd6b6  mov     cs:?GenericSansSerifFamily@Globals@@3PEAVGpFontFamily@@EA, rbp; GpFontFamily * Globals::GenericSansSerifFamily
0x1800cd6bd  mov     cs:?GenericSerifFamily@Globals@@3PEAVGpFontFamily@@EA, rbp; GpFontFamily * Globals::GenericSerifFamily
0x1800cd6c4  mov     cs:?GenericMonospaceFamily@Globals@@3PEAVGpFontFamily@@EA, rbp; GpFontFamily * Globals::GenericMonospaceFamily
0x1800cd6cb  test    rcx, rcx
0x1800cd6ce  jnz     loc_1800CDA22
0x1800cd6d4  mov     cs:?NationalDigitCache@Globals@@3PEAV?$IntMap@E@@EA, rbp; IntMap<uchar> * Globals::NationalDigitCache
0x1800cd6db  call    ?DestroyStaticObjects@GpStringFormat@@SAXXZ; GpStringFormat::DestroyStaticObjects(void)
0x1800cd6e0  mov     rcx, cs:?FontsDirW@Globals@@3PEAGEA; ushort * Globals::FontsDirW
0x1800cd6e7  call    GpFree
0x1800cd6ec  mov     rcx, cs:?FontsDirA@Globals@@3PEADEA; char * Globals::FontsDirA
0x1800cd6f3  mov     cs:?FontsDirW@Globals@@3PEAGEA, rbp; ushort * Globals::FontsDirW
0x1800cd6fa  call    GpFree
0x1800cd6ff  mov     rcx, cs:?LookAsideBuffer@Globals@@3PEAEEA; uchar * Globals::LookAsideBuffer
0x1800cd706  mov     cs:?FontsDirA@Globals@@3PEADEA, rbp; char * Globals::FontsDirA
0x1800cd70d  test    rcx, rcx
0x1800cd710  jnz     loc_1800CDA2C
0x1800cd716  cmp     cs:?TextCriticalSectionInitialized@Globals@@3HA, ebp; int Globals::TextCriticalSectionInitialized
0x1800cd71c  jz      short loc_1800CD737
0x1800cd71e  lea     rcx, ?TextCriticalSection@Globals@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800cd725  call    cs:__imp_DeleteCriticalSection
0x1800cd72c  nop     dword ptr [rax+rax+00h]
0x1800cd731  mov     cs:?TextCriticalSectionInitialized@Globals@@3HA, ebp; int Globals::TextCriticalSectionInitialized
0x1800cd737  call    ?FreeCachedCodecInfo@@YAXI@Z; FreeCachedCodecInfo(uint)
0x1800cd73c  cmp     cs:?initialized@ImagingCritSec@@0HA, ebp; int ImagingCritSec::initialized
0x1800cd742  jz      short loc_1800CD75D
0x1800cd744  lea     rcx, ?critSec@ImagingCritSec@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800cd74b  call    cs:__imp_DeleteCriticalSection
0x1800cd752  nop     dword ptr [rax+rax+00h]
0x1800cd757  mov     cs:?initialized@ImagingCritSec@@0HA, ebp; int ImagingCritSec::initialized
0x1800cd75d  mov     rdi, cs:qword_1801AE708
0x1800cd764  test    rdi, rdi
0x1800cd767  jnz     loc_1800CD936
0x1800cd76d  mov     rcx, cs:?g_DWriteTextAnalyzer@Globals@@3PEAUIDWriteTextAnalyzer@@EA; IDWriteTextAnalyzer * Globals::g_DWriteTextAnalyzer
0x1800cd774  mov     cs:qword_1801AE708, rbp
0x1800cd77b  test    rcx, rcx
0x1800cd77e  jnz     loc_1800CDA3D
0x1800cd784  mov     rdx, cs:?g_GpFontFileLoader@Globals@@3PEAUIDWriteFontFileLoader@@EA; IDWriteFontFileLoader * Globals::g_GpFontFileLoader
0x1800cd78b  test    rdx, rdx
0x1800cd78e  jnz     loc_1800CDA55
0x1800cd794  mov     rdx, cs:?g_GpFontCollectionStreamLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionStreamLoader
0x1800cd79b  test    rdx, rdx
0x1800cd79e  jnz     loc_1800CDA87
0x1800cd7a4  mov     rdx, cs:?g_GpFontCollectionFileLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionFileLoader
0x1800cd7ab  test    rdx, rdx
0x1800cd7ae  jnz     loc_1800CDAB9
0x1800cd7b4  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x1800cd7bb  test    rcx, rcx
0x1800cd7be  jnz     loc_1800CDAEB
0x1800cd7c4  mov     rcx, cs:?UniscribeDllModule@Globals@@3PEAUHINSTANCE__@@EA; hLibModule
0x1800cd7cb  test    rcx, rcx
0x1800cd7ce  jnz     loc_1800CDB03
0x1800cd7d4  cmp     cs:?RuntimeInitialized@Globals@@3HA, ebp; int Globals::RuntimeInitialized
0x1800cd7da  jz      short loc_1800CD7E2
0x1800cd7dc  mov     cs:?RuntimeInitialized@Globals@@3HA, ebp; int Globals::RuntimeInitialized
0x1800cd7e2  cmp     cs:?initialized@LoadLibraryCriticalSection@@0HA, ebp; int LoadLibraryCriticalSection::initialized
0x1800cd7e8  jz      short loc_1800CD803
0x1800cd7ea  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800cd7f1  call    cs:__imp_DeleteCriticalSection
0x1800cd7f8  nop     dword ptr [rax+rax+00h]
0x1800cd7fd  mov     cs:?initialized@LoadLibraryCriticalSection@@0HA, ebp; int LoadLibraryCriticalSection::initialized
0x1800cd803  cmp     cs:?initialized@BackgroundThreadCriticalSection@@0HA, ebp; int BackgroundThreadCriticalSection::initialized
0x1800cd809  jz      short loc_1800CD824
0x1800cd80b  lea     rcx, ?critSec@BackgroundThreadCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800cd812  call    cs:__imp_DeleteCriticalSection
0x1800cd819  nop     dword ptr [rax+rax+00h]
0x1800cd81e  mov     cs:?initialized@BackgroundThreadCriticalSection@@0HA, ebp; int BackgroundThreadCriticalSection::initialized
0x1800cd824  cmp     cs:?initialized@GpMallocTrackingCriticalSection@@0HA, ebp; int GpMallocTrackingCriticalSection::initialized
0x1800cd82a  jz      short loc_1800CD845
0x1800cd82c  lea     rcx, ?critSec@GpMallocTrackingCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800cd833  call    cs:__imp_DeleteCriticalSection
0x1800cd83a  nop     dword ptr [rax+rax+00h]
0x1800cd83f  mov     cs:?initialized@GpMallocTrackingCriticalSection@@0HA, ebp; int GpMallocTrackingCriticalSection::initialized
0x1800cd845  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x1800cd84c  test    rcx, rcx
0x1800cd84f  jz      short loc_1800CD864
0x1800cd851  call    cs:__imp_HeapDestroy
0x1800cd858  nop     dword ptr [rax+rax+00h]
0x1800cd85d  mov     cs:?GpMemHeap@GpRuntime@@3PEAXEA, rbp; void * GpRuntime::GpMemHeap
0x1800cd864  mov     cs:?Initialized@CPUSpecificOps@@3HA, ebp; int CPUSpecificOps::Initialized
0x1800cd86a  mov     rax, rsi
0x1800cd86d  add     rsp, 28h
0x1800cd871  pop     rdi
0x1800cd872  pop     rsi
0x1800cd873  pop     rbp
0x1800cd874  pop     rbx
0x1800cd875  retn
0x1800cd877  lea     rcx, ?TextCriticalSection@Globals@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800cd87e  call    cs:__imp_EnterCriticalSection
0x1800cd885  nop     dword ptr [rax+rax+00h]
0x1800cd88a  mov     rcx, cs:?FontCollection@Globals@@3PEAVGpInstalledFontCollection@@EA; GpInstalledFontCollection * Globals::FontCollection
0x1800cd891  test    rcx, rcx
0x1800cd894  jz      short loc_1800CD8A3
0x1800cd896  mov     rax, [rcx]
0x1800cd899  mov     edx, edi
0x1800cd89b  mov     rax, [rax]
0x1800cd89e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd8a3  mov     rbx, cs:?DWriteFontLinkTable@Globals@@3PEAVGpFontLink@@EA; GpFontLink * Globals::DWriteFontLinkTable
0x1800cd8aa  mov     cs:?FontCollection@Globals@@3PEAVGpInstalledFontCollection@@EA, rbp; GpInstalledFontCollection * Globals::FontCollection
0x1800cd8b1  test    rbx, rbx
0x1800cd8b4  jnz     loc_1800CD9F7
0x1800cd8ba  lea     rcx, ?TextCriticalSection@Globals@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800cd8c1  call    cs:__imp_LeaveCriticalSection
0x1800cd8c8  nop     dword ptr [rax+rax+00h]
0x1800cd8cd  jmp     loc_1800CD678
0x1800cd8d2  mov     rcx, [rbx+8]
0x1800cd8d6  call    GpFree
0x1800cd8db  mov     edx, 10h; unsigned __int64
0x1800cd8e0  mov     rcx, rbx; void *
0x1800cd8e3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cd8e8  jmp     loc_1800CD511
0x1800cd8ed  mov     rax, [rcx]
0x1800cd8f0  mov     edx, edi
0x1800cd8f2  mov     rax, [rax]
0x1800cd8f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd8fa  jmp     loc_1800CD548
0x1800cd8ff  mov     edx, 10h; unsigned __int64
0x1800cd904  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cd909  jmp     loc_1800CD6A8
0x1800cd90e  call    ??_GDpBitmap@@QEAAPEAXI@Z; DpBitmap::`scalar deleting destructor'(uint)
0x1800cd913  jmp     loc_1800CD5DF
0x1800cd918  call    ??_GDpBitmap@@QEAAPEAXI@Z; DpBitmap::`scalar deleting destructor'(uint)
0x1800cd91d  mov     cs:?g_pRemoteSurface@Globals@@3PEAVDpBitmap@@EA, rbp; DpBitmap * Globals::g_pRemoteSurface
0x1800cd924  jmp     loc_1800CD62D
0x1800cd929  call    ?BackgroundThreadShutdown@@YAPEAXXZ; BackgroundThreadShutdown(void)
0x1800cd92e  mov     rsi, rax
0x1800cd931  jmp     loc_1800CD497
0x1800cd936  mov     rbx, [rdi+10h]
0x1800cd93a  mov     rcx, rdi; this
0x1800cd93d  call    ??1ols@@QEAA@XZ; ols::~ols(void)
0x1800cd942  mov     edx, 20h ; ' '; unsigned __int64
0x1800cd947  mov     rcx, rdi; void *
0x1800cd94a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cd94f  mov     rdi, rbx
0x1800cd952  test    rbx, rbx
0x1800cd955  jz      loc_1800CD76D
0x1800cd95b  jmp     short loc_1800CD936
0x1800cd95d  mov     rdx, [rcx]
0x1800cd960  mov     rax, [rdx]
0x1800cd963  mov     edx, edi
0x1800cd965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd96a  jmp     loc_1800CD4AC
0x1800cd96f  call    ??_GGpMatrix@@QEAAPEAXI@Z; GpMatrix::`scalar deleting destructor'(uint)
0x1800cd974  jmp     loc_1800CD4C3
0x1800cd979  mov     rax, [rcx]
0x1800cd97c  mov     edx, edi
0x1800cd97e  mov     rax, [rax]
0x1800cd981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd986  jmp     loc_1800CD4DA
0x1800cd98b  mov     rax, [rcx]
0x1800cd98e  mov     edx, edi
0x1800cd990  mov     rax, [rax]
0x1800cd993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd998  jmp     loc_1800CD5F6
0x1800cd99d  call    ??_GGpGraphics@@QEAAPEAXI@Z; GpGraphics::`scalar deleting destructor'(uint)
0x1800cd9a2  mov     cs:?g_pTSGraphics@Globals@@3PEAVGpGraphics@@EA, rbp; GpGraphics * Globals::g_pTSGraphics
0x1800cd9a9  jmp     loc_1800CD60D
0x1800cd9ae  mov     rax, [rcx]
0x1800cd9b1  mov     edx, edi
0x1800cd9b3  mov     rax, [rax]
0x1800cd9b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd9bb  mov     cs:?g_pITSClientPlayer@Globals@@3PEAVIMetafilePlayer@@EA, rbp; IMetafilePlayer * Globals::g_pITSClientPlayer
0x1800cd9c2  jmp     loc_1800CD61D
0x1800cd9c7  call    cs:__imp_FreeLibrary
0x1800cd9ce  nop     dword ptr [rax+rax+00h]
0x1800cd9d3  mov     cs:?DdrawHandle@Globals@@3PEAUHINSTANCE__@@EA, rbp; HINSTANCE__ * Globals::DdrawHandle
0x1800cd9da  jmp     loc_1800CD63D
0x1800cd9df  call    cs:__imp_DeleteObject
0x1800cd9e6  nop     dword ptr [rax+rax+00h]
0x1800cd9eb  mov     cs:?CachedGdiRegion@Globals@@3PEAUHRGN__@@EA, rbp; HRGN__ * Globals::CachedGdiRegion
0x1800cd9f2  jmp     loc_1800CD64D
0x1800cd9f7  mov     rcx, rbx; this
0x1800cd9fa  call    ??1GpFontLink@@QEAA@XZ; GpFontLink::~GpFontLink(void)
0x1800cd9ff  mov     edx, 40h ; '@'; unsigned __int64
0x1800cda04  mov     rcx, rbx; void *
0x1800cda07  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cda0c  mov     cs:?DWriteFontLinkTable@Globals@@3PEAVGpFontLink@@EA, rbp; GpFontLink * Globals::DWriteFontLinkTable
0x1800cda13  jmp     loc_1800CD8BA
0x1800cda18  call    GpFree
0x1800cda1d  jmp     loc_1800CD68D
0x1800cda22  call    ??_G?$IntMap@E@@QEAAPEAXI@Z; IntMap<uchar>::`scalar deleting destructor'(uint)
  ... truncated ...
```
