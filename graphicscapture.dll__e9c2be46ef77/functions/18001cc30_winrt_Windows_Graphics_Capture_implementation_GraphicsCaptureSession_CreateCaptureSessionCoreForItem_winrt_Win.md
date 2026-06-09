# winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession::CreateCaptureSessionCoreForItem(winrt::Windows::Graphics::Capture::GraphicsCaptureItem const &,void *)

- ea: `0x18001cc30`
- end: `0x18001ceab`
- name: `?CreateCaptureSessionCoreForItem@GraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@SA?AV?$unique_ptr@VCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@U?$default_delete@VCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@@std@@@std@@AEBUGraphicsCaptureItem@3456@PEAX@Z`
- size: `635`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18001c638`

## callees

- `0x180002158`
- `0x1800022f2`
- `0x180003580`
- `0x1800058c4`
- `0x180006610`
- `0x18000ea0c`
- `0x180014458`
- `0x1800149d8`
- `0x18001c558`
- `0x18001c5c8`
- `0x18001c860`
- `0x18001c95c`
- `0x18001cc30`
- `0x180024c34`
- `0x180028010`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 *__fastcall winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession::CreateCaptureSessionCoreForItem(
        __int64 *a1,
        void (__fastcall ****a2)(_QWORD, __int64 *, __int64 *),
        __int64 a3)
{
  void (__fastcall ***v6)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  void (__fastcall ***v10)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 v11; // rdi
  __int64 v12; // rcx
  __int64 *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  void (__fastcall ***v16)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 v17; // rbx
  __int64 v18; // r14
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rdx
  const struct winrt::impl::slim_source_location *v23; // rax
  __int64 v24; // [rsp+28h] [rbp-58h] BYREF
  __int64 v25; // [rsp+30h] [rbp-50h] BYREF
  __int64 v26; // [rsp+38h] [rbp-48h] BYREF
  void *v27; // [rsp+40h] [rbp-40h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+48h] [rbp-38h] BYREF
  char v29[32]; // [rsp+60h] [rbp-20h] BYREF
  __int64 v30; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v31; // [rsp+D0h] [rbp+50h] BYREF
  __int64 v32; // [rsp+D8h] [rbp+58h] BYREF

  v31 = a3;
  *a1 = 0;
  v6 = *a2;
  v30 = 0;
  if ( v6 )
    (**v6)(v6, &winrt::impl::guid_v<winrt::Windows::Graphics::Capture::Server::ICapturableItemFacade>, &v30);
  v32 = 0;
  if ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v30, &v32) )
  {
    winrt::impl::consume_Windows_Graphics_Capture_Server_ICapturableItem<winrt::Windows::Graphics::Capture::Server::ICapturableItem>::DisplayName(
      &v30,
      &v32);
    v7 = (__int64 *)std::make_unique<winrt::Windows::Graphics::Capture::implementation::ServerCaptureSessionCore,winrt::Windows::Graphics::Capture::Server::CapturableItem &,void * &,0>(
                      &v25,
                      &v32,
                      &v31);
    v8 = *v7;
    *v7 = 0;
    v9 = *a1;
    *a1 = v8;
    if ( v9 )
      std::default_delete<winrt::Windows::Graphics::Capture::implementation::CaptureSessionCore>::operator()(v8);
    std::unique_ptr<winrt::Windows::Graphics::Capture::implementation::ServerCaptureSessionCore>::~unique_ptr<winrt::Windows::Graphics::Capture::implementation::ServerCaptureSessionCore>(&v25);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v32);
  }
  v10 = *a2;
  if ( *a2 )
  {
    v32 = 0;
    (**v10)(v10, &winrt::impl::guid_v<winrt::Windows::Graphics::Capture::implementation::IVisualCaptureItem>, &v32);
    v11 = v32;
    v25 = v32;
    v12 = v32;
  }
  else
  {
    v11 = 0;
    v25 = 0;
    v12 = 0;
  }
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 24LL))(v12, &v32);
    v13 = (__int64 *)std::make_unique<winrt::Windows::Graphics::Capture::implementation::VisualCaptureSessionCore,winrt::Windows::UI::Composition::Visual &,void * &,0>(
                       &v24,
                       &v32,
                       &v31);
    v14 = *v13;
    *v13 = 0;
    v15 = *a1;
    *a1 = v14;
    if ( v15 )
      std::default_delete<winrt::Windows::Graphics::Capture::implementation::CaptureSessionCore>::operator()(v14);
    std::unique_ptr<winrt::Windows::Graphics::Capture::implementation::ServerCaptureSessionCore>::~unique_ptr<winrt::Windows::Graphics::Capture::implementation::ServerCaptureSessionCore>(&v24);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v32);
  }
  v16 = *a2;
  if ( *a2 )
  {
    v32 = 0;
    (**v16)(v16, &winrt::impl::guid_v<winrt::Windows::Graphics::Capture::implementation::IDCompVisualCaptureItem>, &v32);
    v17 = v32;
    v18 = v32;
  }
  else
  {
    v17 = 0;
    v18 = 0;
  }
  v24 = v17;
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 24LL))(v18, &v26);
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 32LL))(v18, &v32);
    v27 = operator new(0x18u);
    v19 = winrt::Windows::Graphics::Capture::implementation::DCompVisualCaptureSessionCore::DCompVisualCaptureSessionCore(
            v27,
            &v26,
            &v32,
            a3,
            1,
            v24,
            v25);
    v27 = 0;
    v21 = *a1;
    *a1 = v19;
    if ( v21 )
      std::default_delete<winrt::Windows::Graphics::Capture::implementation::CaptureSessionCore>::operator()(v20);
    std::unique_ptr<winrt::Windows::Graphics::Capture::implementation::ServerCaptureSessionCore>::~unique_ptr<winrt::Windows::Graphics::Capture::implementation::ServerCaptureSessionCore>(&v27);
    if ( v32 )
      winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&v32);
    if ( v26 )
      winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&v26);
  }
  if ( !*a1 )
  {
    v23 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v29);
    winrt::hresult_invalid_argument::hresult_invalid_argument((winrt::hresult_invalid_argument *)pExceptionObject, v23);
    throw (winrt::hresult_invalid_argument *)pExceptionObject;
  }
  if ( v17 )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&v24);
  if ( v11 )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&v25);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v30);
  return a1;
}

```

## disassembly

```asm
0x18001cc30  mov     [rsp-38h+arg_10], r8
0x18001cc35  mov     [rsp-38h+arg_0], rcx
0x18001cc3a  push    rbp
0x18001cc3b  push    rbx
0x18001cc3c  push    rsi
0x18001cc3d  push    rdi
0x18001cc3e  push    r12
0x18001cc40  push    r14
0x18001cc42  push    r15
0x18001cc44  mov     rbp, rsp
0x18001cc47  sub     rsp, 80h
0x18001cc4e  mov     r15, r8
0x18001cc51  mov     rbx, rdx
0x18001cc54  mov     rsi, rcx
0x18001cc57  xor     r12d, r12d
0x18001cc5a  mov     [rbp+var_60], r12d
0x18001cc5e  mov     [rcx], r12
0x18001cc61  mov     [rbp+var_60], 1
0x18001cc68  mov     rcx, [rdx]
0x18001cc6b  mov     [rbp+arg_8], r12
0x18001cc6f  test    rcx, rcx
0x18001cc72  jz      short loc_18001CC92
0x18001cc74  mov     rax, [rcx]
0x18001cc77  lea     r8, [rbp+arg_8]
0x18001cc7b  lea     rdx, ??$guid_v@UICapturableItemFacade@Server@Capture@Graphics@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Graphics::Capture::Server::ICapturableItemFacade>
0x18001cc82  mov     rax, [rax]
0x18001cc85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc8a  mov     rax, [rbp+arg_8]
0x18001cc8e  mov     [rbp+arg_8], rax
0x18001cc92  mov     [rbp+arg_18], r12
0x18001cc96  lea     rdx, [rbp+arg_18]
0x18001cc9a  lea     rcx, [rbp+arg_8]
0x18001cc9e  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18001cca3  test    al, al
0x18001cca5  jnz     short loc_18001CCEF
0x18001cca7  lea     rdx, [rbp+arg_18]
0x18001ccab  lea     rcx, [rbp+arg_8]
0x18001ccaf  call    ?DisplayName@?$consume_Windows_Graphics_Capture_Server_ICapturableItem@UICapturableItem@Server@Capture@Graphics@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Graphics_Capture_Server_ICapturableItem<winrt::Windows::Graphics::Capture::Server::ICapturableItem>::DisplayName(void)
0x18001ccb4  nop
0x18001ccb5  lea     r8, [rbp+arg_10]
0x18001ccb9  lea     rdx, [rbp+arg_18]
0x18001ccbd  lea     rcx, [rbp+var_50]
0x18001ccc1  call    ??$make_unique@VServerCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@AEAUCapturableItem@Server@3456@AEAPEAX$0A@@std@@YA?AV?$unique_ptr@VServerCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@U?$default_delete@VServerCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@@std@@@0@AEAUCapturableItem@Server@Capture@Graphics@Windows@winrt@@AEAPEAX@Z; std::make_unique<winrt::Windows::Graphics::Capture::implementation::ServerCaptureSessionCore,winrt::Windows::Graphics::Capture::Server::CapturableItem &,void * &,0>(winrt::Windows::Graphics::Capture::Server::CapturableItem &,void * &)
0x18001ccc6  mov     rcx, [rax]
0x18001ccc9  mov     [rax], r12
0x18001cccc  mov     rdx, [rsi]
0x18001cccf  mov     [rsi], rcx
0x18001ccd2  test    rdx, rdx
0x18001ccd5  jz      short loc_18001CCDC
0x18001ccd7  call    ??R?$default_delete@VCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@@std@@QEBAXPEAVCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@@Z; std::default_delete<winrt::Windows::Graphics::Capture::implementation::CaptureSessionCore>::operator()(winrt::Windows::Graphics::Capture::implementation::CaptureSessionCore *)
0x18001ccdc  lea     rcx, [rbp+var_50]
0x18001cce0  call    ??1?$unique_ptr@VServerCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@U?$default_delete@VServerCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@@std@@@std@@QEAA@XZ; std::unique_ptr<winrt::Windows::Graphics::Capture::implementation::ServerCaptureSessionCore>::~unique_ptr<winrt::Windows::Graphics::Capture::implementation::ServerCaptureSessionCore>(void)
0x18001cce5  nop
0x18001cce6  lea     rcx, [rbp+arg_18]
0x18001ccea  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18001ccef  mov     rcx, [rbx]
0x18001ccf2  test    rcx, rcx
0x18001ccf5  jnz     short loc_18001CD03
0x18001ccf7  mov     rdi, r12
0x18001ccfa  mov     [rbp+var_50], r12
0x18001ccfe  mov     rcx, r12
0x18001cd01  jmp     short loc_18001CD28
0x18001cd03  mov     [rbp+arg_18], r12
0x18001cd07  mov     rax, [rcx]
0x18001cd0a  lea     r8, [rbp+arg_18]
0x18001cd0e  lea     rdx, ??$guid_v@UIVisualCaptureItem@implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Graphics::Capture::implementation::IVisualCaptureItem>
0x18001cd15  mov     rax, [rax]
0x18001cd18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd1d  mov     rdi, [rbp+arg_18]
0x18001cd21  mov     [rbp+var_50], rdi
0x18001cd25  mov     rcx, rdi
0x18001cd28  test    rcx, rcx
0x18001cd2b  jz      short loc_18001CD78
0x18001cd2d  mov     rax, [rcx]
0x18001cd30  lea     rdx, [rbp+arg_18]
0x18001cd34  mov     rax, [rax+18h]
0x18001cd38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd3d  nop
0x18001cd3e  lea     r8, [rbp+arg_10]
0x18001cd42  lea     rdx, [rbp+arg_18]
0x18001cd46  lea     rcx, [rbp+var_58]
0x18001cd4a  call    ??$make_unique@VVisualCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@AEAUVisual@Composition@UI@56@AEAPEAX$0A@@std@@YA?AV?$unique_ptr@VVisualCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@U?$default_delete@VVisualCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@@std@@@0@AEAUVisual@Composition@UI@Windows@winrt@@AEAPEAX@Z; std::make_unique<winrt::Windows::Graphics::Capture::implementation::VisualCaptureSessionCore,winrt::Windows::UI::Composition::Visual &,void * &,0>(winrt::Windows::UI::Composition::Visual &,void * &)
0x18001cd4f  mov     rcx, [rax]
0x18001cd52  mov     [rax], r12
0x18001cd55  mov     rdx, [rsi]
0x18001cd58  mov     [rsi], rcx
0x18001cd5b  test    rdx, rdx
0x18001cd5e  jz      short loc_18001CD65
0x18001cd60  call    ??R?$default_delete@VCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@@std@@QEBAXPEAVCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@@Z; std::default_delete<winrt::Windows::Graphics::Capture::implementation::CaptureSessionCore>::operator()(winrt::Windows::Graphics::Capture::implementation::CaptureSessionCore *)
0x18001cd65  lea     rcx, [rbp+var_58]
0x18001cd69  call    ??1?$unique_ptr@VServerCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@U?$default_delete@VServerCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@@std@@@std@@QEAA@XZ; std::unique_ptr<winrt::Windows::Graphics::Capture::implementation::ServerCaptureSessionCore>::~unique_ptr<winrt::Windows::Graphics::Capture::implementation::ServerCaptureSessionCore>(void)
0x18001cd6e  nop
0x18001cd6f  lea     rcx, [rbp+arg_18]
0x18001cd73  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18001cd78  mov     rcx, [rbx]
0x18001cd7b  test    rcx, rcx
0x18001cd7e  jnz     short loc_18001CD88
0x18001cd80  mov     rbx, r12
0x18001cd83  mov     r14, r12
0x18001cd86  jmp     short loc_18001CDA9
0x18001cd88  mov     [rbp+arg_18], r12
0x18001cd8c  mov     rax, [rcx]
0x18001cd8f  lea     r8, [rbp+arg_18]
0x18001cd93  lea     rdx, ??$guid_v@UIDCompVisualCaptureItem@implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Graphics::Capture::implementation::IDCompVisualCaptureItem>
0x18001cd9a  mov     rax, [rax]
0x18001cd9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cda2  mov     rbx, [rbp+arg_18]
0x18001cda6  mov     r14, rbx
0x18001cda9  mov     [rbp+var_58], rbx
0x18001cdad  test    r14, r14
0x18001cdb0  jz      loc_18001CE44
0x18001cdb6  mov     rax, [r14]
0x18001cdb9  lea     rdx, [rbp+var_48]
0x18001cdbd  mov     rcx, r14
0x18001cdc0  mov     rax, [rax+18h]
0x18001cdc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdc9  nop
0x18001cdca  mov     rax, [r14]
0x18001cdcd  lea     rdx, [rbp+arg_18]
0x18001cdd1  mov     rcx, r14
0x18001cdd4  mov     rax, [rax+20h]
0x18001cdd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cddd  nop
0x18001cdde  mov     ecx, 18h; Size
0x18001cde3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cde8  mov     [rbp+var_40], rax
0x18001cdec  mov     r9, r15
0x18001cdef  lea     r8, [rbp+arg_18]
0x18001cdf3  lea     rdx, [rbp+var_48]
0x18001cdf7  mov     rcx, rax
0x18001cdfa  call    ??0DCompVisualCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@QEAA@AEBU?$com_ptr@UIDCompositionDevice@@@5@AEBU?$com_ptr@UIDCompositionVisual@@@5@PEAX@Z; winrt::Windows::Graphics::Capture::implementation::DCompVisualCaptureSessionCore::DCompVisualCaptureSessionCore(winrt::com_ptr<IDCompositionDevice> const &,winrt::com_ptr<IDCompositionVisual> const &,void *)
0x18001cdff  nop
0x18001ce00  mov     [rbp+var_60], 3
0x18001ce07  mov     [rbp+var_40], r12
0x18001ce0b  mov     rdx, [rsi]
0x18001ce0e  mov     [rsi], rax
0x18001ce11  test    rdx, rdx
0x18001ce14  jz      short loc_18001CE1B
0x18001ce16  call    ??R?$default_delete@VCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@@std@@QEBAXPEAVCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@@Z; std::default_delete<winrt::Windows::Graphics::Capture::implementation::CaptureSessionCore>::operator()(winrt::Windows::Graphics::Capture::implementation::CaptureSessionCore *)
0x18001ce1b  lea     rcx, [rbp+var_40]
0x18001ce1f  call    ??1?$unique_ptr@VServerCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@U?$default_delete@VServerCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@@std@@@std@@QEAA@XZ; std::unique_ptr<winrt::Windows::Graphics::Capture::implementation::ServerCaptureSessionCore>::~unique_ptr<winrt::Windows::Graphics::Capture::implementation::ServerCaptureSessionCore>(void)
0x18001ce24  nop
0x18001ce25  cmp     [rbp+arg_18], r12
0x18001ce29  jz      short loc_18001CE35
0x18001ce2b  lea     rcx, [rbp+arg_18]
0x18001ce2f  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x18001ce34  nop
0x18001ce35  cmp     [rbp+var_48], r12
0x18001ce39  jz      short loc_18001CE44
0x18001ce3b  lea     rcx, [rbp+var_48]
0x18001ce3f  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x18001ce44  cmp     [rsi], r12
0x18001ce47  jz      short loc_18001CE85
0x18001ce49  test    rbx, rbx
0x18001ce4c  jz      short loc_18001CE58
0x18001ce4e  lea     rcx, [rbp+var_58]
0x18001ce52  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x18001ce57  nop
0x18001ce58  test    rdi, rdi
0x18001ce5b  jz      short loc_18001CE67
0x18001ce5d  lea     rcx, [rbp+var_50]
0x18001ce61  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x18001ce66  nop
0x18001ce67  lea     rcx, [rbp+arg_8]
0x18001ce6b  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18001ce70  mov     rax, rsi
0x18001ce73  add     rsp, 80h
0x18001ce7a  pop     r15
0x18001ce7c  pop     r14
0x18001ce7e  pop     r12
0x18001ce80  pop     rdi
0x18001ce81  pop     rsi
0x18001ce82  pop     rbx
0x18001ce83  pop     rbp
0x18001ce84  retn
0x18001ce85  lea     rcx, [rbp+var_20]
0x18001ce89  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001ce8e  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001ce91  lea     rcx, [rbp+pExceptionObject]; this
0x18001ce95  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::impl::slim_source_location const &)
0x18001ce9a  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18001cea1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001cea5  call    _CxxThrowException_0
```
