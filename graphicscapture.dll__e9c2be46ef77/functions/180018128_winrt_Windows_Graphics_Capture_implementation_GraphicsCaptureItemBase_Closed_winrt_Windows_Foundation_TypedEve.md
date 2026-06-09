# winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::Closed(winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable> const &)

- ea: `0x180018128`
- end: `0x1800181a5`
- name: `?Closed@GraphicsCaptureItemBase@implementation@Capture@Graphics@Windows@winrt@@QEAA?AUevent_token@6@AEBU?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@56@@Z`
- size: `125`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a3d0`
- `0x18001a430`
- `0x18001a490`
- `0x18001a4e0`

## callees

- `0x180012444`
- `0x180016870`
- `0x180017018`
- `0x180018128`
- `0x180028010`

## pseudocode

```c
PVOID *__fastcall winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::Closed(
        RTL_SRWLOCK *a1,
        PVOID *a2)
{
  _QWORD *Ptr; // rax
  __int64 *v5; // rax
  RTL_SRWLOCK *v7; // [rsp+30h] [rbp+8h] BYREF

  Ptr = a1[7].Ptr;
  if ( Ptr && (unsigned __int64)(*Ptr - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v7 = a1;
    std::call_once__lambda_c13a70783c110a50f205192c12ebaede___(&a1[12], &v7);
  }
  (*((void (__fastcall **)(RTL_SRWLOCK *))a1->Ptr + 6))(a1);
  v5 = (__int64 *)winrt::impl::make_agile_delegate<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>((winrt::Windows::Foundation::IUnknown *)&v7);
  winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>::add_agile(
    a1 + 4,
    a2,
    v5);
  return a2;
}

```

## disassembly

```asm
0x180018128  mov     r11, rsp
0x18001812b  mov     [r11+10h], rbx
0x18001812f  mov     [r11+18h], rsi
0x180018133  push    rdi
0x180018134  sub     rsp, 20h
0x180018138  mov     rax, [rcx+38h]
0x18001813c  mov     rsi, r8
0x18001813f  mov     rdi, rdx
0x180018142  mov     rbx, rcx
0x180018145  test    rax, rax
0x180018148  jz      short loc_180018167
0x18001814a  mov     rax, [rax]
0x18001814d  dec     rax
0x180018150  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180018154  ja      short loc_180018167
0x180018156  mov     [r11+8], rcx
0x18001815a  lea     rdx, [r11+8]
0x18001815e  add     rcx, 60h ; '`'
0x180018162  call    std__call_once__lambda_c13a70783c110a50f205192c12ebaede___
0x180018167  mov     rax, [rbx]
0x18001816a  mov     rcx, rbx
0x18001816d  mov     rax, [rax+30h]
0x180018171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018176  mov     rdx, rsi
0x180018179  lea     rcx, [rsp+28h+arg_0]; this
0x18001817e  call    ??$make_agile_delegate@U?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@YA?AU?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@1@AEBU2341@@Z; winrt::impl::make_agile_delegate<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>(winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable> const &)
0x180018183  lea     rcx, [rbx+20h]
0x180018187  mov     r8, rax
0x18001818a  mov     rdx, rdi
0x18001818d  call    ?add_agile@?$event@U?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@winrt@@AEAA?AUevent_token@2@U?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@2@@Z; winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>::add_agile(winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>)
0x180018192  mov     rbx, [rsp+28h+arg_8]
0x180018197  mov     rax, rdi
0x18001819a  mov     rsi, [rsp+28h+arg_10]
0x18001819f  add     rsp, 20h
0x1800181a3  pop     rdi
0x1800181a4  retn
```
