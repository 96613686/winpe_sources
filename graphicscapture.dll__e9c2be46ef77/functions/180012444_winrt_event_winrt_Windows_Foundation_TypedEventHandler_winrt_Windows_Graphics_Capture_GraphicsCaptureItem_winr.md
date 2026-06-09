# winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>::add_agile(winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>)

- ea: `0x180012444`
- end: `0x18001255b`
- name: `?add_agile@?$event@U?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@winrt@@AEAA?AUevent_token@2@U?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@2@@Z`
- size: `279`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fb98`
- `0x180018128`

## callees

- `0x180002384`
- `0x180002390`
- `0x180002465`
- `0x1800039fc`
- `0x180006594`
- `0x1800065f0`
- `0x18000df28`
- `0x18000e058`
- `0x18000e2f8`
- `0x18000eea0`
- `0x180012444`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
PVOID *__fastcall winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>::add_agile(
        RTL_SRWLOCK *a1,
        PVOID *a2,
        __int64 *a3)
{
  RTL_SRWLOCK *v6; // r14
  __int64 v7; // rdx
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v11; // [rsp+60h] [rbp+38h] BYREF
  __int64 v12; // [rsp+68h] [rbp+40h] BYREF
  __int64 *v13; // [rsp+70h] [rbp+48h] BYREF
  RTL_SRWLOCK *v14; // [rsp+78h] [rbp+50h]

  v13 = a3;
  *a2 = 0;
  v12 = 0;
  v6 = a1 + 2;
  v14 = a1 + 2;
  WINRT_IMPL_AcquireSRWLockExclusive(a1 + 2);
  v7 = 1;
  if ( a1->Ptr )
    v7 = (unsigned int)(*((_DWORD *)a1->Ptr + 1) + 1);
  winrt::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>(
    &v11,
    v7);
  v8 = v11;
  if ( a1->Ptr )
    std::copy_n<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable> *,unsigned int,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable> *>(
      (char *)a1->Ptr + 8,
      *((unsigned int *)a1->Ptr + 1),
      v11 + 8);
  winrt::Windows::Foundation::IUnknown::operator=(v8 + 8LL * *(unsigned int *)(v8 + 4), a3);
  *a2 = WINRT_IMPL_EncodePointer(*(PVOID *)(v8 + 8LL * *(unsigned int *)(v8 + 4)));
  WINRT_IMPL_AcquireSRWLockExclusive(a1 + 1);
  v9 = std::exchange<winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>>,winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>>>(
         &v13,
         a1,
         &v11);
  winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>>::operator=(
    &v12,
    v9);
  if ( v13 )
    winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(&v13);
  ReleaseSRWLockExclusive_0(a1 + 1);
  if ( v11 )
    winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(&v11);
  ReleaseSRWLockExclusive_0(v6);
  if ( v12 )
    winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(&v12);
  if ( *a3 )
    winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(a3);
  return a2;
}

```

## disassembly

```asm
0x180012444  mov     [rsp-30h+arg_10], r8
0x180012449  push    rbp
0x18001244a  push    rbx
0x18001244b  push    rsi
0x18001244c  push    rdi
0x18001244d  push    r14
0x18001244f  push    r15
0x180012451  mov     rbp, rsp
0x180012454  sub     rsp, 28h
0x180012458  mov     rdi, r8
0x18001245b  mov     r15, rdx
0x18001245e  mov     rsi, rcx
0x180012461  mov     qword ptr [rdx], 0
0x180012468  mov     [rbp+arg_8], 0
0x180012470  lea     r14, [rcx+10h]
0x180012474  mov     [rbp+arg_18], r14
0x180012478  mov     rcx, r14; SRWLock
0x18001247b  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180012480  nop
0x180012481  mov     rax, [rsi]
0x180012484  mov     edx, 1
0x180012489  test    rax, rax
0x18001248c  jz      short loc_180012491
0x18001248e  add     edx, [rax+4]
0x180012491  lea     rcx, [rbp+arg_0]
0x180012495  call    ??$make_event_array@U?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@1@I@Z; winrt::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>(uint)
0x18001249a  mov     rdx, [rsi]
0x18001249d  mov     rbx, [rbp+arg_0]
0x1800124a1  test    rdx, rdx
0x1800124a4  jz      short loc_1800124B6
0x1800124a6  lea     r8, [rbx+8]
0x1800124aa  lea     rcx, [rdx+8]
0x1800124ae  mov     edx, [rdx+4]
0x1800124b1  call    ??$copy_n@PEAU?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@IPEAU1234@@std@@YAPEAU?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@PEAU1234@I0@Z; std::copy_n<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable> *,uint,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable> *>(winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable> *,uint,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable> *)
0x1800124b6  mov     eax, [rbx+4]
0x1800124b9  lea     rcx, [rbx+rax*8]
0x1800124bd  mov     rdx, rdi
0x1800124c0  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1800124c5  mov     ecx, [rbx+4]
0x1800124c8  mov     rcx, [rbx+rcx*8]; Ptr
0x1800124cc  call    WINRT_IMPL_EncodePointer
0x1800124d1  mov     [r15], rax
0x1800124d4  lea     rcx, [rsi+8]; SRWLock
0x1800124d8  call    WINRT_IMPL_AcquireSRWLockExclusive
0x1800124dd  lea     r8, [rbp+arg_0]
0x1800124e1  mov     rdx, rsi
0x1800124e4  lea     rcx, [rbp+arg_10]
0x1800124e8  call    ??$exchange@U?$com_ptr@U?$event_array@U?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@U12@@std@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAU12@$$QEAU12@@Z; std::exchange<winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>>,winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>>>(winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>> &,winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>> &&)
0x1800124ed  mov     rdx, rax
0x1800124f0  lea     rcx, [rbp+arg_8]
0x1800124f4  call    ??4?$com_ptr@U?$event_array@U?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>>::operator=(winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>> &&)
0x1800124f9  cmp     [rbp+arg_10], 0
0x1800124fe  jz      short loc_180012509
0x180012500  lea     rcx, [rbp+arg_10]
0x180012504  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UDirect3D11CaptureFramePool@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(void)
0x180012509  lea     rcx, [rsi+8]; SRWLock
0x18001250d  call    ReleaseSRWLockExclusive_0
0x180012512  cmp     [rbp+arg_0], 0
0x180012517  jz      short loc_180012523
0x180012519  lea     rcx, [rbp+arg_0]
0x18001251d  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UDirect3D11CaptureFramePool@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(void)
0x180012522  nop
0x180012523  mov     rcx, r14; SRWLock
0x180012526  call    ReleaseSRWLockExclusive_0
0x18001252b  nop
0x18001252c  cmp     [rbp+arg_8], 0
0x180012531  jz      short loc_18001253D
0x180012533  lea     rcx, [rbp+arg_8]
0x180012537  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UDirect3D11CaptureFramePool@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(void)
0x18001253c  nop
0x18001253d  cmp     qword ptr [rdi], 0
0x180012541  jz      short loc_18001254B
0x180012543  mov     rcx, rdi
0x180012546  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x18001254b  mov     rax, r15
0x18001254e  add     rsp, 28h
0x180012552  pop     r15
0x180012554  pop     r14
0x180012556  pop     rdi
0x180012557  pop     rsi
0x180012558  pop     rbx
0x180012559  pop     rbp
0x18001255a  retn
```
