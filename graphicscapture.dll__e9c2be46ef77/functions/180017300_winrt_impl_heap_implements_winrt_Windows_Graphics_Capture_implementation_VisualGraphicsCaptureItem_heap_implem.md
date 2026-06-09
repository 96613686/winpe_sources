# winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem>::heap_implements<winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem>(IMessageSession *,winrt::Windows::UI::Composition::Visual const &)

- ea: `0x180017300`
- end: `0x180017396`
- name: `??0?$heap_implements@UVisualGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@QEAA@PEAUIMessageSession@@AEBUVisual@Composition@UI@Windows@2@@Z`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180018d8c`

## callees

- `0x18000ef28`
- `0x1800174ec`
- `0x180017688`
- `0x1800190c8`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem>::heap_implements<winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem>(
        _QWORD *a1,
        const struct winrt::Windows::UI::Composition::Visual *a2,
        winrt::Windows::Graphics::Capture::implementation *a3)
{
  __int64 ClosedEvent; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  void *v8; // r9

  ClosedEvent = winrt::Windows::Graphics::Capture::implementation::GetClosedEvent(a3, a2);
  winrt::impl::producers_base<winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem,std::tuple<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Graphics::Capture::implementation::IVisualCaptureItem>>::producers_base<winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem,std::tuple<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Graphics::Capture::implementation::IVisualCaptureItem>>(
    a1,
    v6,
    v7,
    ClosedEvent);
  winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::GraphicsCaptureItemBase(
    (winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase *)(a1 + 2),
    a2,
    v8);
  *a1 = &winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem>::`vftable';
  a1[2] = &winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase,std::tuple<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Graphics::Capture::implementation::IFireClosedEvent>>'};
  a1[4] = &winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase,winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::cloaked<winrt::Windows::Graphics::Capture::implementation::IFireClosedEvent>>'};
  a1[15] = 0;
  winrt::Windows::Foundation::IUnknown::operator=((winrt::Windows::Foundation::IUnknown *)(a1 + 15));
  *a1 = &winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem>::`vftable';
  a1[2] = &winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase,std::tuple<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Graphics::Capture::implementation::IFireClosedEvent>>'};
  a1[4] = &winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase,winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::cloaked<winrt::Windows::Graphics::Capture::implementation::IFireClosedEvent>>'};
  return a1;
}

```

## disassembly

```asm
0x180017300  push    rbx
0x180017302  push    rsi
0x180017303  push    rdi
0x180017304  push    r14
0x180017306  sub     rsp, 28h
0x18001730a  mov     r14, rcx
0x18001730d  mov     rsi, r8
0x180017310  mov     rcx, r8; this
0x180017313  mov     rbx, rdx
0x180017316  call    ?GetClosedEvent@implementation@Capture@Graphics@Windows@winrt@@YAPEAXAEBUVisual@Composition@UI@45@@Z; winrt::Windows::Graphics::Capture::implementation::GetClosedEvent(winrt::Windows::UI::Composition::Visual const &)
0x18001731b  mov     rcx, r14
0x18001731e  mov     r9, rax
0x180017321  call    ??0?$producers_base@UVisualGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@V?$tuple@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIVisualCaptureItem@implementation@2345@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem,std::tuple<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Graphics::Capture::implementation::IVisualCaptureItem>>::producers_base<winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem,std::tuple<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Graphics::Capture::implementation::IVisualCaptureItem>>(void)
0x180017326  lea     rdi, [r14+10h]
0x18001732a  mov     r8, r9; void *
0x18001732d  mov     rcx, rdi; this
0x180017330  mov     rdx, rbx; struct IMessageSession *
0x180017333  call    ??0GraphicsCaptureItemBase@implementation@Capture@Graphics@Windows@winrt@@QEAA@PEAUIMessageSession@@PEAX@Z; winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::GraphicsCaptureItemBase(IMessageSession *,void *)
0x180017338  lea     rax, ??_7?$heap_implements@UVisualGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem>::`vftable'
0x18001733f  mov     rdx, rsi
0x180017342  mov     [r14], rax
0x180017345  lea     rcx, [r14+78h]; this
0x180017349  lea     rax, ??_7VisualGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@6B?$producers_base@UGraphicsCaptureItemBase@implementation@Capture@Graphics@Windows@winrt@@V?$tuple@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIFireClosedEvent@implementation@2345@@std@@@impl@5@@; const winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase,std::tuple<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Graphics::Capture::implementation::IFireClosedEvent>>'}
0x180017350  mov     [rdi], rax
0x180017353  lea     rax, ??_7?$heap_implements@UVisualGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@6B?$root_implements@UGraphicsCaptureItemBase@implementation@Capture@Graphics@Windows@winrt@@UGraphicsCaptureItem@3456@U?$cloaked@UIFireClosedEvent@implementation@Capture@Graphics@Windows@winrt@@@6@@12@@; const winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase,winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::cloaked<winrt::Windows::Graphics::Capture::implementation::IFireClosedEvent>>'}
0x18001735a  mov     [r14+20h], rax
0x18001735e  mov     qword ptr [rcx], 0
0x180017365  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@AEBU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown const &)
0x18001736a  lea     rax, ??_7?$heap_implements@UVisualGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem>::`vftable'
0x180017371  mov     [r14], rax
0x180017374  lea     rax, ??_7VisualGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@6B?$producers_base@UGraphicsCaptureItemBase@implementation@Capture@Graphics@Windows@winrt@@V?$tuple@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIFireClosedEvent@implementation@2345@@std@@@impl@5@@; const winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase,std::tuple<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Graphics::Capture::implementation::IFireClosedEvent>>'}
0x18001737b  mov     [rdi], rax
0x18001737e  lea     rax, ??_7?$heap_implements@UVisualGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@6B?$root_implements@UGraphicsCaptureItemBase@implementation@Capture@Graphics@Windows@winrt@@UGraphicsCaptureItem@3456@U?$cloaked@UIFireClosedEvent@implementation@Capture@Graphics@Windows@winrt@@@6@@12@@; const winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::VisualGraphicsCaptureItem>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase,winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::cloaked<winrt::Windows::Graphics::Capture::implementation::IFireClosedEvent>>'}
0x180017385  mov     [r14+20h], rax
0x180017389  mov     rax, r14
0x18001738c  add     rsp, 28h
0x180017390  pop     r14
0x180017392  pop     rdi
0x180017393  pop     rsi
0x180017394  pop     rbx
0x180017395  retn
```
