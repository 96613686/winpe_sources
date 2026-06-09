# winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::~Direct3D11CaptureFramePool(void)

- ea: `0x180003740`
- end: `0x18000395e`
- name: `??1Direct3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@UEAA@XZ`
- size: `542`
- prototype: `void __fastcall(winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003bbc`

## callees

- `0x180001640`
- `0x180002720`
- `0x180002794`
- `0x1800027d4`
- `0x18000280c`
- `0x180003580`
- `0x1800035d4`
- `0x180003620`
- `0x180003740`
- `0x180006594`
- `0x1800065f0`
- `0x180006610`
- `0x1800068b4`
- `0x18000f19c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000386d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000386d`

## pseudocode

```c
void __fastcall winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::~Direct3D11CaptureFramePool(
        winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *this,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-28h] BYREF

  *(_QWORD *)this = &winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool,std::tuple<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IClosable,IFlipContentCallback>>'};
  *((_QWORD *)this + 3) = &winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool,winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IClosable,winrt::cloaked<IFlipContentCallback>>'};
  *((_QWORD *)this + 5) = &winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool>::`vftable';
  if ( (Microsoft_Windows_GraphicsCapture_APIEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer((__int64)this, (const EVENT_DESCRIPTOR *)FRAME_POOL_DESTRUCTOR, a3, 1u, &v7);
  winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::Close(this);
  if ( *((_QWORD *)this + 37) )
    winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref((char *)this + 296);
  v4 = *((_QWORD *)this + 34);
  if ( v4 )
  {
    std::_Destroy_range<std::allocator<winrt::com_ptr<ID3D11Texture2D>>>(v4, *((_QWORD *)this + 35));
    std::_Deallocate<16>(
      *((_QWORD *)this + 34),
      (*((_QWORD *)this + 36) - *((_QWORD *)this + 34)) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 34) = 0;
    *((_QWORD *)this + 35) = 0;
    *((_QWORD *)this + 36) = 0;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 264);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 256);
  v5 = *((_QWORD *)this + 29);
  if ( v5 )
  {
    std::_Destroy_range<std::allocator<winrt::Windows::Graphics::Capture::Direct3D11CaptureFrame>>(
      v5,
      *((_QWORD *)this + 30));
    std::_Deallocate<16>(
      *((_QWORD *)this + 29),
      (*((_QWORD *)this + 31) - *((_QWORD *)this + 29)) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 29) = 0;
    *((_QWORD *)this + 30) = 0;
    *((_QWORD *)this + 31) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  if ( *((_QWORD *)this + 20) )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref((char *)this + 160);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 152);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 144);
  v6 = *((_QWORD *)this + 15);
  if ( v6 )
  {
    std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>(
      v6,
      *((_QWORD *)this + 16));
    std::_Deallocate<16>(
      *((_QWORD *)this + 15),
      (*((_QWORD *)this + 17) - *((_QWORD *)this + 15)) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 15) = 0;
    *((_QWORD *)this + 16) = 0;
    *((_QWORD *)this + 17) = 0;
  }
  if ( *((_QWORD *)this + 12) )
    winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref();
  if ( *((_QWORD *)this + 11) )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref((char *)this + 88);
  if ( *((_QWORD *)this + 10) )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref((char *)this + 80);
  if ( *((_QWORD *)this + 9) )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref((char *)this + 72);
  if ( *((_QWORD *)this + 8) )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref((char *)this + 64);
  if ( *((_QWORD *)this + 7) )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref((char *)this + 56);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>((char *)this + 48);
  winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Graphics::RectInt32>>::~root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Graphics::RectInt32>>((char *)this + 24);
}

```

## disassembly

```asm
0x180003740  mov     r11, rsp
0x180003743  mov     [r11+10h], rbx
0x180003747  mov     [r11+18h], rsi
0x18000374b  push    rdi
0x18000374c  sub     rsp, 50h
0x180003750  mov     rax, cs:__security_cookie
0x180003757  xor     rax, rsp
0x18000375a  mov     [rsp+58h+var_18], rax
0x18000375f  mov     rbx, rcx
0x180003762  lea     rax, ??_7Direct3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@6B?$producers_base@UDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@V?$tuple@UDirect3D11CaptureFramePool@Capture@Graphics@Windows@winrt@@UIClosable@Foundation@45@UIFlipContentCallback@@@std@@@impl@5@@; const winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool,std::tuple<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IClosable,IFlipContentCallback>>'}
0x180003769  mov     [rcx], rax
0x18000376c  lea     rax, ??_7Direct3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@6B?$root_implements@UDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@U13456@UIClosable@Foundation@56@U?$cloaked@UIFlipContentCallback@@@6@@impl@5@@; const winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool,winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IClosable,winrt::cloaked<IFlipContentCallback>>'}
0x180003773  mov     [rcx+18h], rax
0x180003777  lea     rax, ??_7?$heap_implements@UDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool>::`vftable'
0x18000377e  mov     [rcx+28h], rax
0x180003782  test    cs:Microsoft_Windows_GraphicsCapture_APIEnableBits, 2
0x180003789  jz      short loc_1800037A5
0x18000378b  lea     rax, [r11-28h]
0x18000378f  mov     [r11-38h], rax
0x180003793  mov     r9d, 1
0x180003799  lea     rdx, FRAME_POOL_DESTRUCTOR
0x1800037a0  call    McGenEventWrite_EventWriteTransfer
0x1800037a5  mov     rcx, rbx; this
0x1800037a8  call    ?Close@Direct3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@QEAAXXZ; winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::Close(void)
0x1800037ad  lea     rcx, [rbx+128h]
0x1800037b4  xor     esi, esi
0x1800037b6  cmp     [rcx], rsi
0x1800037b9  jz      short loc_1800037C0
0x1800037bb  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x1800037c0  mov     rcx, [rbx+110h]
0x1800037c7  test    rcx, rcx
0x1800037ca  jz      short loc_180003807
0x1800037cc  mov     rdx, [rbx+118h]
0x1800037d3  call    ??$_Destroy_range@V?$allocator@U?$com_ptr@UID3D11Texture2D@@@winrt@@@std@@@std@@YAXPEAU?$com_ptr@UID3D11Texture2D@@@winrt@@QEAU12@AEAV?$allocator@U?$com_ptr@UID3D11Texture2D@@@winrt@@@0@@Z; std::_Destroy_range<std::allocator<winrt::com_ptr<ID3D11Texture2D>>>(winrt::com_ptr<ID3D11Texture2D> *,winrt::com_ptr<ID3D11Texture2D> * const,std::allocator<winrt::com_ptr<ID3D11Texture2D>> &)
0x1800037d8  mov     rcx, [rbx+110h]
0x1800037df  mov     rdx, [rbx+120h]
0x1800037e6  sub     rdx, rcx
0x1800037e9  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800037ed  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800037f2  mov     [rbx+110h], rsi
0x1800037f9  mov     [rbx+118h], rsi
0x180003800  mov     [rbx+120h], rsi
0x180003807  lea     rcx, [rbx+108h]
0x18000380e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180003813  lea     rcx, [rbx+100h]
0x18000381a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000381f  mov     rcx, [rbx+0E8h]
0x180003826  test    rcx, rcx
0x180003829  jz      short loc_180003866
0x18000382b  mov     rdx, [rbx+0F0h]
0x180003832  call    ??$_Destroy_range@V?$allocator@UDirect3D11CaptureFrame@Capture@Graphics@Windows@winrt@@@std@@@std@@YAXPEAUDirect3D11CaptureFrame@Capture@Graphics@Windows@winrt@@QEAU12345@AEAV?$allocator@UDirect3D11CaptureFrame@Capture@Graphics@Windows@winrt@@@0@@Z; std::_Destroy_range<std::allocator<winrt::Windows::Graphics::Capture::Direct3D11CaptureFrame>>(winrt::Windows::Graphics::Capture::Direct3D11CaptureFrame *,winrt::Windows::Graphics::Capture::Direct3D11CaptureFrame * const,std::allocator<winrt::Windows::Graphics::Capture::Direct3D11CaptureFrame> &)
0x180003837  mov     rcx, [rbx+0E8h]
0x18000383e  mov     rdx, [rbx+0F8h]
0x180003845  sub     rdx, rcx
0x180003848  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000384c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180003851  mov     [rbx+0E8h], rsi
0x180003858  mov     [rbx+0F0h], rsi
0x18000385f  mov     [rbx+0F8h], rsi
0x180003866  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18000386d  call    cs:__imp_DeleteCriticalSection
0x180003873  lea     rcx, [rbx+0A0h]
0x18000387a  cmp     [rcx], rsi
0x18000387d  jz      short loc_180003884
0x18000387f  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x180003884  lea     rcx, [rbx+98h]
0x18000388b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180003890  lea     rcx, [rbx+90h]
0x180003897  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000389c  mov     rcx, [rbx+78h]
0x1800038a0  test    rcx, rcx
0x1800038a3  jz      short loc_1800038DA
0x1800038a5  mov     rdx, [rbx+80h]
0x1800038ac  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> &)
0x1800038b1  mov     rcx, [rbx+78h]
0x1800038b5  mov     rdx, [rbx+88h]
0x1800038bc  sub     rdx, rcx
0x1800038bf  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800038c3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800038c8  mov     [rbx+78h], rsi
0x1800038cc  mov     [rbx+80h], rsi
0x1800038d3  mov     [rbx+88h], rsi
0x1800038da  lea     rcx, [rbx+60h]
0x1800038de  cmp     [rcx], rsi
0x1800038e1  jz      short loc_1800038E8
0x1800038e3  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UDirect3D11CaptureFramePool@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(void)
0x1800038e8  lea     rcx, [rbx+58h]
0x1800038ec  cmp     [rcx], rsi
0x1800038ef  jz      short loc_1800038F6
0x1800038f1  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x1800038f6  lea     rcx, [rbx+50h]
0x1800038fa  cmp     [rcx], rsi
0x1800038fd  jz      short loc_180003904
0x1800038ff  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x180003904  lea     rcx, [rbx+48h]
0x180003908  cmp     [rcx], rsi
0x18000390b  jz      short loc_180003912
0x18000390d  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x180003912  lea     rcx, [rbx+40h]
0x180003916  cmp     [rcx], rsi
0x180003919  jz      short loc_180003920
0x18000391b  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x180003920  lea     rcx, [rbx+38h]
0x180003924  cmp     [rcx], rsi
0x180003927  jz      short loc_18000392E
0x180003929  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x18000392e  lea     rcx, [rbx+30h]
0x180003932  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180003937  lea     rcx, [rbx+18h]
0x18000393b  call    ??1?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@URectInt32@Graphics@Windows@winrt@@V?$vector@URectInt32@Graphics@Windows@winrt@@V?$allocator@URectInt32@Graphics@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@4@@impl@winrt@@URectInt32@Graphics@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@URectInt32@Graphics@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Graphics::RectInt32>>::~root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Graphics::RectInt32,std::vector<winrt::Windows::Graphics::RectInt32>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Graphics::RectInt32,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Graphics::RectInt32>>(void)
0x180003940  nop
0x180003941  mov     rcx, [rsp+58h+var_18]
0x180003946  xor     rcx, rsp; StackCookie
0x180003949  call    __security_check_cookie
0x18000394e  mov     rbx, [rsp+58h+arg_8]
0x180003953  mov     rsi, [rsp+58h+arg_10]
0x180003958  add     rsp, 50h
0x18000395c  pop     rdi
0x18000395d  retn
```
