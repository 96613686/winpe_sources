# winrt::Windows::Graphics::Capture::implementation::DCompVisualGraphicsCaptureItem::DCompVisualGraphicsCaptureItem(IMessageSession *,IDCompositionDevice *,IDCompositionVisual *,int,int)

- ea: `0x1800175a8`
- end: `0x18001767f`
- name: `??0DCompVisualGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@QEAA@PEAUIMessageSession@@PEAUIDCompositionDevice@@PEAUIDCompositionVisual@@HH@Z`
- size: `215`
- prototype: `__int64 __fastcall(winrt::Windows::Graphics::Capture::implementation::DCompVisualGraphicsCaptureItem *__hidden this, struct IMessageSession *, struct IDCompositionDevice *, struct IDCompositionVisual *, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180016de4`

## callees

- `0x180006610`
- `0x180012564`
- `0x1800175a8`
- `0x180017688`

## pseudocode

```c
winrt::Windows::Graphics::Capture::implementation::DCompVisualGraphicsCaptureItem *__fastcall winrt::Windows::Graphics::Capture::implementation::DCompVisualGraphicsCaptureItem::DCompVisualGraphicsCaptureItem(
        winrt::Windows::Graphics::Capture::implementation::DCompVisualGraphicsCaptureItem *this,
        struct IMessageSession *a2,
        struct IDCompositionDevice *a3,
        struct IDCompositionVisual *a4,
        int a5,
        int a6)
{
  _QWORD *v9; // rsi
  struct IDCompositionVisual **v10; // rbx

  *((_QWORD *)this + 1) = &winrt::impl::produce<winrt::Windows::Graphics::Capture::implementation::DCompVisualGraphicsCaptureItem,winrt::Windows::Graphics::Capture::IGraphicsCaptureItem>::`vftable';
  *(_QWORD *)this = &winrt::impl::producers_base<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool,std::tuple<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IClosable,IFlipContentCallback>>::`vftable';
  winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::GraphicsCaptureItemBase(
    (winrt::Windows::Graphics::Capture::implementation::DCompVisualGraphicsCaptureItem *)((char *)this + 16),
    a2,
    0);
  *(_QWORD *)this = &winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::DCompVisualGraphicsCaptureItem>::`vftable';
  v9 = (_QWORD *)((char *)this + 120);
  *((_QWORD *)this + 2) = &winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::DCompVisualGraphicsCaptureItem>::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase,std::tuple<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Graphics::Capture::implementation::IFireClosedEvent>>'};
  v10 = (struct IDCompositionVisual **)((char *)this + 128);
  *((_QWORD *)this + 4) = &winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::DCompVisualGraphicsCaptureItem>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase,winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::cloaked<winrt::Windows::Graphics::Capture::implementation::IFireClosedEvent>>'};
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  if ( *((struct IDCompositionDevice **)this + 15) != a3 )
  {
    if ( *v9 )
      winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref((__int64 *)this + 15);
    *v9 = a3;
    winrt::com_ptr<IDCompositionVisual>::add_ref((__int64 *)this + 15);
  }
  if ( *v10 != a4 )
  {
    if ( *v10 )
      winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref((__int64 *)this + 16);
    *v10 = a4;
    winrt::com_ptr<IDCompositionVisual>::add_ref((__int64 *)this + 16);
  }
  *((_DWORD *)this + 34) = a5;
  *((_DWORD *)this + 35) = a6;
  return this;
}

```

## disassembly

```asm
0x1800175a8  push    rbx
0x1800175aa  push    rbp
0x1800175ab  push    rsi
0x1800175ac  push    rdi
0x1800175ad  push    r14
0x1800175af  sub     rsp, 20h
0x1800175b3  lea     rax, ??_7?$produce@UDCompVisualGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@UIGraphicsCaptureItem@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Graphics::Capture::implementation::DCompVisualGraphicsCaptureItem,winrt::Windows::Graphics::Capture::IGraphicsCaptureItem>::`vftable'
0x1800175ba  mov     r14, r8
0x1800175bd  mov     [rcx+8], rax
0x1800175c1  mov     rdi, rcx
0x1800175c4  lea     rax, ??_7?$producers_base@UDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@V?$tuple@UDirect3D11CaptureFramePool@Capture@Graphics@Windows@winrt@@UIClosable@Foundation@45@UIFlipContentCallback@@@std@@@impl@winrt@@6B@; const winrt::impl::producers_base<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool,std::tuple<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IClosable,IFlipContentCallback>>::`vftable'
0x1800175cb  xor     r8d, r8d; void *
0x1800175ce  mov     [rcx], rax
0x1800175d1  mov     rbp, r9
0x1800175d4  add     rcx, 10h; this
0x1800175d8  call    ??0GraphicsCaptureItemBase@implementation@Capture@Graphics@Windows@winrt@@QEAA@PEAUIMessageSession@@PEAX@Z; winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::GraphicsCaptureItemBase(IMessageSession *,void *)
0x1800175dd  lea     rax, ??_7?$heap_implements@UDCompVisualGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::DCompVisualGraphicsCaptureItem>::`vftable'
0x1800175e4  mov     [rdi], rax
0x1800175e7  lea     rsi, [rdi+78h]
0x1800175eb  lea     rax, ??_7?$heap_implements@UDCompVisualGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@6B?$producers_base@UGraphicsCaptureItemBase@implementation@Capture@Graphics@Windows@winrt@@V?$tuple@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIFireClosedEvent@implementation@2345@@std@@@12@@; const winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::DCompVisualGraphicsCaptureItem>::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase,std::tuple<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Graphics::Capture::implementation::IFireClosedEvent>>'}
0x1800175f2  mov     [rdi+10h], rax
0x1800175f6  lea     rbx, [rdi+80h]
0x1800175fd  lea     rax, ??_7?$heap_implements@UDCompVisualGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@6B?$root_implements@UGraphicsCaptureItemBase@implementation@Capture@Graphics@Windows@winrt@@UGraphicsCaptureItem@3456@U?$cloaked@UIFireClosedEvent@implementation@Capture@Graphics@Windows@winrt@@@6@@12@@; const winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::DCompVisualGraphicsCaptureItem>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase,winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::cloaked<winrt::Windows::Graphics::Capture::implementation::IFireClosedEvent>>'}
0x180017604  mov     [rdi+20h], rax
0x180017608  mov     qword ptr [rsi], 0
0x18001760f  mov     qword ptr [rbx], 0
0x180017616  mov     qword ptr [rdi+88h], 0
0x180017621  cmp     [rsi], r14
0x180017624  jz      short loc_18001763F
0x180017626  cmp     qword ptr [rsi], 0
0x18001762a  jz      short loc_180017634
0x18001762c  mov     rcx, rsi
0x18001762f  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x180017634  mov     rcx, rsi
0x180017637  mov     [rsi], r14
0x18001763a  call    ?add_ref@?$com_ptr@UIDCompositionVisual@@@winrt@@AEBAXXZ; winrt::com_ptr<IDCompositionVisual>::add_ref(void)
0x18001763f  cmp     [rbx], rbp
0x180017642  jz      short loc_18001765D
0x180017644  cmp     qword ptr [rbx], 0
0x180017648  jz      short loc_180017652
0x18001764a  mov     rcx, rbx
0x18001764d  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x180017652  mov     rcx, rbx
0x180017655  mov     [rbx], rbp
0x180017658  call    ?add_ref@?$com_ptr@UIDCompositionVisual@@@winrt@@AEBAXXZ; winrt::com_ptr<IDCompositionVisual>::add_ref(void)
0x18001765d  mov     eax, [rsp+48h+arg_20]
0x180017661  mov     [rdi+88h], eax
0x180017667  mov     eax, [rsp+48h+arg_28]
0x18001766b  mov     [rdi+8Ch], eax
0x180017671  mov     rax, rdi
0x180017674  add     rsp, 20h
0x180017678  pop     r14
0x18001767a  pop     rdi
0x18001767b  pop     rsi
0x18001767c  pop     rbp
0x18001767d  pop     rbx
0x18001767e  retn
```
