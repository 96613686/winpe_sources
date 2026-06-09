# winrt::Windows::Graphics::Capture::implementation::ServerGraphicsCaptureItem::ServerGraphicsCaptureItem(IMessageSession *,winrt::Windows::Graphics::Capture::Server::CapturableItem const &)

- ea: `0x180017740`
- end: `0x180017846`
- name: `??0ServerGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@QEAA@PEAUIMessageSession@@AEBUCapturableItem@Server@2345@@Z`
- size: `262`
- prototype: `__int64 __fastcall(winrt::Windows::Graphics::Capture::implementation::ServerGraphicsCaptureItem *__hidden this, struct IMessageSession *, const struct winrt::Windows::Graphics::Capture::Server::CapturableItem *)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180016ef0`
- `0x18001728c`
- `0x18001739c`
- `0x180017410`

## callees

- `0x180002459`
- `0x1800039fc`
- `0x1800065f0`
- `0x1800125ec`
- `0x1800168e4`
- `0x180017688`
- `0x180017740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017778`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017778`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
winrt::Windows::Graphics::Capture::implementation::ServerGraphicsCaptureItem *__fastcall winrt::Windows::Graphics::Capture::implementation::ServerGraphicsCaptureItem::ServerGraphicsCaptureItem(
        winrt::Windows::Graphics::Capture::implementation::ServerGraphicsCaptureItem *this,
        struct IMessageSession *a2,
        const struct winrt::Windows::Graphics::Capture::Server::CapturableItem *a3)
{
  HANDLE EventW; // rax
  void *v7; // rax
  unsigned int AgileReference; // eax
  int v10; // [rsp+20h] [rbp-20h] BYREF
  __int128 v11; // [rsp+28h] [rbp-18h]
  char v12; // [rsp+70h] [rbp+30h] BYREF
  __int64 v13; // [rsp+78h] [rbp+38h] BYREF

  v10 = 0;
  v11 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  v7 = (void *)winrt::check_pointer<void>(EventW, &v10);
  *((_QWORD *)this + 13) = &winrt::impl::produce<winrt::Windows::Graphics::Capture::implementation::ServerGraphicsCaptureItem,winrt::Windows::Graphics::Capture::IGraphicsCaptureItem>::`vftable';
  *((_QWORD *)this + 14) = &winrt::impl::produce<winrt::Windows::Graphics::Capture::implementation::ServerGraphicsCaptureItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemFacade>::`vftable';
  winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::GraphicsCaptureItemBase(this, a2, v7);
  *(_QWORD *)this = &winrt::Windows::Graphics::Capture::implementation::ServerGraphicsCaptureItem::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase,std::tuple<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Graphics::Capture::implementation::IFireClosedEvent>>'};
  *((_QWORD *)this + 2) = &winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::ServerGraphicsCaptureItem>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase,winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::cloaked<winrt::Windows::Graphics::Capture::implementation::IFireClosedEvent>>'};
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  v13 = 0;
  if ( *(_QWORD *)a3 )
  {
    AgileReference = WINRT_IMPL_RoGetAgileReference(
                       0,
                       winrt::impl::guid_v<winrt::Windows::Graphics::Capture::Server::ICapturableItem>,
                       *(_QWORD *)a3,
                       &v13,
                       0,
                       0,
                       0);
    winrt::check_hresult(&v12, AgileReference, &v10);
  }
  winrt::Windows::Foundation::IUnknown::operator=((char *)this + 120, &v13);
  if ( v13 )
    winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(&v13);
  return this;
}

```

## disassembly

```asm
0x180017740  mov     [rsp-18h+arg_8], rbx
0x180017745  mov     [rsp-18h+arg_0], rcx
0x18001774a  push    rbp
0x18001774b  push    rsi
0x18001774c  push    rdi
0x18001774d  mov     rbp, rsp
0x180017750  sub     rsp, 40h
0x180017754  mov     rdi, r8
0x180017757  mov     rbx, rdx
0x18001775a  mov     rsi, rcx
0x18001775d  mov     [rbp+var_20], 0
0x180017764  xorps   xmm0, xmm0
0x180017767  movdqu  [rbp+var_18], xmm0
0x18001776c  xor     r9d, r9d; lpName
0x18001776f  xor     r8d, r8d; bInitialState
0x180017772  lea     edx, [r9+1]; bManualReset
0x180017776  xor     ecx, ecx; lpEventAttributes
0x180017778  call    cs:__imp_CreateEventW
0x18001777e  lea     rdx, [rbp+var_20]
0x180017782  mov     rcx, rax
0x180017785  call    ??$check_pointer@X@winrt@@YAPEAXPEAXAEBUslim_source_location@impl@0@@Z; winrt::check_pointer<void>(void *,winrt::impl::slim_source_location const &)
0x18001778a  lea     rcx, ??_7?$produce@UServerGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@UIGraphicsCaptureItem@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Graphics::Capture::implementation::ServerGraphicsCaptureItem,winrt::Windows::Graphics::Capture::IGraphicsCaptureItem>::`vftable'
0x180017791  mov     [rsi+68h], rcx
0x180017795  lea     rcx, ??_7?$produce@UServerGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@UICapturableItemFacade@Server@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Graphics::Capture::implementation::ServerGraphicsCaptureItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemFacade>::`vftable'
0x18001779c  mov     [rsi+70h], rcx
0x1800177a0  mov     r8, rax; void *
0x1800177a3  mov     rdx, rbx; struct IMessageSession *
0x1800177a6  mov     rcx, rsi; this
0x1800177a9  call    ??0GraphicsCaptureItemBase@implementation@Capture@Graphics@Windows@winrt@@QEAA@PEAUIMessageSession@@PEAX@Z; winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::GraphicsCaptureItemBase(IMessageSession *,void *)
0x1800177ae  nop
0x1800177af  lea     rax, ??_7ServerGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@6B?$producers_base@UGraphicsCaptureItemBase@implementation@Capture@Graphics@Windows@winrt@@V?$tuple@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIFireClosedEvent@implementation@2345@@std@@@impl@5@@; const winrt::Windows::Graphics::Capture::implementation::ServerGraphicsCaptureItem::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase,std::tuple<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Graphics::Capture::implementation::IFireClosedEvent>>'}
0x1800177b6  mov     [rsi], rax
0x1800177b9  lea     rax, ??_7?$heap_implements@UServerGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@6B?$root_implements@UGraphicsCaptureItemBase@implementation@Capture@Graphics@Windows@winrt@@UGraphicsCaptureItem@3456@U?$cloaked@UIFireClosedEvent@implementation@Capture@Graphics@Windows@winrt@@@6@@12@@; const winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::ServerGraphicsCaptureItem>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase,winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::cloaked<winrt::Windows::Graphics::Capture::implementation::IFireClosedEvent>>'}
0x1800177c0  mov     [rsi+10h], rax
0x1800177c4  mov     qword ptr [rsi+78h], 0
0x1800177cc  mov     qword ptr [rsi+80h], 0
0x1800177d7  mov     [rbp+arg_18], 0
0x1800177df  mov     r8, [rdi]
0x1800177e2  test    r8, r8
0x1800177e5  jz      short loc_180017818
0x1800177e7  mov     [rbp+var_20], 0
0x1800177ee  xorps   xmm0, xmm0
0x1800177f1  movdqu  [rbp+var_18], xmm0
0x1800177f6  lea     r9, [rbp+arg_18]
0x1800177fa  lea     rdx, ??$guid_v@UICapturableItem@Server@Capture@Graphics@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Graphics::Capture::Server::ICapturableItem>
0x180017801  xor     ecx, ecx
0x180017803  call    WINRT_IMPL_RoGetAgileReference
0x180017808  lea     r8, [rbp+var_20]
0x18001780c  mov     edx, eax
0x18001780e  lea     rcx, [rbp+arg_10]
0x180017812  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180017817  nop
0x180017818  lea     rdx, [rbp+arg_18]
0x18001781c  lea     rcx, [rsi+78h]
0x180017820  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x180017825  cmp     [rbp+arg_18], 0
0x18001782a  jz      short loc_180017836
0x18001782c  lea     rcx, [rbp+arg_18]
0x180017830  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x180017835  nop
0x180017836  mov     rax, rsi
0x180017839  mov     rbx, [rsp+40h+arg_8]
0x18001783e  add     rsp, 40h
0x180017842  pop     rdi
0x180017843  pop     rsi
0x180017844  pop     rbp
0x180017845  retn
```
