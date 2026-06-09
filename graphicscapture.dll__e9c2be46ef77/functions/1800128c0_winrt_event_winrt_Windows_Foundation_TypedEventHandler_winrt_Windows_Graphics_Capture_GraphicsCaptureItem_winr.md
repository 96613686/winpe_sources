# winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>::remove(winrt::event_token)

- ea: `0x1800128c0`
- end: `0x180012a4f`
- name: `?remove@?$event@U?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@winrt@@QEAAXUevent_token@2@@Z`
- size: `399`
- prototype: ``
- caller_count: `6`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000d740`
- `0x180012a60`
- `0x18001b0b0`
- `0x18001b100`
- `0x18001b150`
- `0x18001b180`

## callees

- `0x180002384`
- `0x180002390`
- `0x180002465`
- `0x180006594`
- `0x18000e058`
- `0x18000e2f8`
- `0x18000eea0`
- `0x18000ef28`
- `0x1800128c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>::remove(
        RTL_SRWLOCK *a1,
        PVOID a2)
{
  __int64 v4; // rsi
  RTL_SRWLOCK *v5; // rdi
  PVOID Ptr; // rcx
  unsigned int v7; // r15d
  __int64 v8; // rbx
  bool v9; // al
  __int64 v10; // rax
  PVOID *v11; // r12
  winrt::Windows::Foundation::IUnknown *v12; // rdi
  __int64 v13; // rax
  _QWORD v14[2]; // [rsp+20h] [rbp-10h] BYREF
  _BOOL8 v15; // [rsp+70h] [rbp+40h] BYREF
  __int64 v16; // [rsp+80h] [rbp+50h] BYREF
  __int64 v17; // [rsp+88h] [rbp+58h] BYREF

  v4 = 0;
  v17 = 0;
  v5 = a1 + 2;
  v14[1] = a1 + 2;
  WINRT_IMPL_AcquireSRWLockExclusive(a1 + 2);
  Ptr = a1->Ptr;
  if ( !a1->Ptr )
  {
    ReleaseSRWLockExclusive_0(v5);
    return;
  }
  v7 = *((_DWORD *)Ptr + 1) - 1;
  v8 = 0;
  v16 = 0;
  if ( !v7 )
  {
    v9 = WINRT_IMPL_EncodePointer(*((PVOID *)Ptr + 1)) == a2;
LABEL_16:
    if ( v9 )
    {
      WINRT_IMPL_AcquireSRWLockExclusive(a1 + 1);
      v13 = std::exchange<winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>>,winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>>>(
              &v15,
              a1,
              &v16);
      winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>>::operator=(
        &v17,
        v13);
      if ( v15 )
        winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(&v15);
      ReleaseSRWLockExclusive_0(a1 + 1);
      v4 = v17;
      v8 = v16;
    }
    goto LABEL_20;
  }
  LOBYTE(v15) = 0;
  v10 = winrt::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>(
          v14,
          v7);
  winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>>::operator=(
    &v16,
    v10);
  if ( v14[0] )
    winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(v14);
  v8 = v16;
  v11 = (PVOID *)((char *)a1->Ptr + 8);
  v14[0] = (char *)a1->Ptr + 8 * *((unsigned int *)a1->Ptr + 1) + 8;
  if ( v11 != (PVOID *)v14[0] )
  {
    v9 = v15;
    v12 = (winrt::Windows::Foundation::IUnknown *)(v16 + 8);
    while ( 1 )
    {
      if ( v9 )
        goto LABEL_12;
      if ( a2 != WINRT_IMPL_EncodePointer(*v11) )
        break;
      v9 = 1;
      LOBYTE(v15) = 1;
LABEL_14:
      if ( ++v11 == (PVOID *)v14[0] )
      {
LABEL_15:
        v5 = a1 + 2;
        goto LABEL_16;
      }
    }
    v9 = v15;
LABEL_12:
    if ( !v7 )
      goto LABEL_15;
    winrt::Windows::Foundation::IUnknown::operator=(v12);
    v12 = (winrt::Windows::Foundation::IUnknown *)((char *)v12 + 8);
    --v7;
    v9 = v15;
    goto LABEL_14;
  }
LABEL_20:
  if ( v8 )
    winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(&v16);
  ReleaseSRWLockExclusive_0(v5);
  if ( v4 )
    winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(&v17);
}

```

## disassembly

```asm
0x1800128c0  mov     [rsp-38h+arg_8], rbx
0x1800128c5  push    rbp
0x1800128c6  push    rsi
0x1800128c7  push    rdi
0x1800128c8  push    r12
0x1800128ca  push    r13
0x1800128cc  push    r14
0x1800128ce  push    r15
0x1800128d0  mov     rbp, rsp
0x1800128d3  sub     rsp, 30h
0x1800128d7  mov     r14, rdx
0x1800128da  mov     r13, rcx
0x1800128dd  xor     esi, esi
0x1800128df  mov     [rbp+arg_18], rsi
0x1800128e3  lea     rdi, [rcx+10h]
0x1800128e7  mov     [rbp+var_8], rdi
0x1800128eb  mov     rcx, rdi; SRWLock
0x1800128ee  call    WINRT_IMPL_AcquireSRWLockExclusive
0x1800128f3  nop
0x1800128f4  mov     rcx, [r13+0]
0x1800128f8  test    rcx, rcx
0x1800128fb  jz      loc_180012A31
0x180012901  mov     r15d, [rcx+4]
0x180012905  sub     r15d, 1
0x180012909  mov     ebx, esi
0x18001290b  mov     [rbp+arg_10], rbx
0x18001290f  jnz     short loc_180012925
0x180012911  mov     rcx, [rcx+8]; Ptr
0x180012915  call    WINRT_IMPL_EncodePointer
0x18001291a  cmp     rax, r14
0x18001291d  setz    al
0x180012920  jmp     loc_1800129BF
0x180012925  mov     byte ptr [rbp+arg_0], 0
0x180012929  mov     edx, r15d
0x18001292c  lea     rcx, [rbp+var_10]
0x180012930  call    ??$make_event_array@U?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@1@I@Z; winrt::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>(uint)
0x180012935  mov     rdx, rax
0x180012938  lea     rcx, [rbp+arg_10]
0x18001293c  call    ??4?$com_ptr@U?$event_array@U?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>>::operator=(winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>> &&)
0x180012941  cmp     [rbp+var_10], 0
0x180012946  jz      short loc_180012951
0x180012948  lea     rcx, [rbp+var_10]
0x18001294c  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UDirect3D11CaptureFramePool@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(void)
0x180012951  mov     rbx, [rbp+arg_10]
0x180012955  mov     rcx, [r13+0]
0x180012959  lea     r12, [rcx+8]
0x18001295d  mov     eax, [rcx+4]
0x180012960  inc     rax
0x180012963  lea     rax, [rcx+rax*8]
0x180012967  mov     [rbp+var_10], rax
0x18001296b  cmp     r12, rax
0x18001296e  jz      loc_180012A09
0x180012974  mov     al, byte ptr [rbp+arg_0]
0x180012977  lea     rdi, [rbx+8]
0x18001297b  test    al, al
0x18001297d  jnz     short loc_180012997
0x18001297f  mov     rcx, [r12]; Ptr
0x180012983  call    WINRT_IMPL_EncodePointer
0x180012988  cmp     r14, rax
0x18001298b  jnz     short loc_180012994
0x18001298d  mov     al, 1
0x18001298f  mov     byte ptr [rbp+arg_0], al
0x180012992  jmp     short loc_1800129B1
0x180012994  mov     al, byte ptr [rbp+arg_0]
0x180012997  test    r15d, r15d
0x18001299a  jz      short loc_1800129BB
0x18001299c  mov     rdx, r12
0x18001299f  mov     rcx, rdi; this
0x1800129a2  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@AEBU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown const &)
0x1800129a7  add     rdi, 8
0x1800129ab  dec     r15d
0x1800129ae  mov     al, byte ptr [rbp+arg_0]
0x1800129b1  add     r12, 8
0x1800129b5  cmp     r12, [rbp+var_10]
0x1800129b9  jnz     short loc_18001297B
0x1800129bb  lea     rdi, [r13+10h]
0x1800129bf  test    al, al
0x1800129c1  jz      short loc_180012A09
0x1800129c3  lea     rcx, [r13+8]; SRWLock
0x1800129c7  call    WINRT_IMPL_AcquireSRWLockExclusive
0x1800129cc  lea     r8, [rbp+arg_10]
0x1800129d0  mov     rdx, r13
0x1800129d3  lea     rcx, [rbp+arg_0]
0x1800129d7  call    ??$exchange@U?$com_ptr@U?$event_array@U?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@U12@@std@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAU12@$$QEAU12@@Z; std::exchange<winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>>,winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>>>(winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>> &,winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>> &&)
0x1800129dc  mov     rdx, rax
0x1800129df  lea     rcx, [rbp+arg_18]
0x1800129e3  call    ??4?$com_ptr@U?$event_array@U?$TypedEventHandler@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>>::operator=(winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureItem,winrt::Windows::Foundation::IInspectable>>> &&)
0x1800129e8  cmp     [rbp+arg_0], 0
0x1800129ed  jz      short loc_1800129F8
0x1800129ef  lea     rcx, [rbp+arg_0]
0x1800129f3  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UDirect3D11CaptureFramePool@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(void)
0x1800129f8  lea     rcx, [r13+8]; SRWLock
0x1800129fc  call    ReleaseSRWLockExclusive_0
0x180012a01  mov     rsi, [rbp+arg_18]
0x180012a05  mov     rbx, [rbp+arg_10]
0x180012a09  test    rbx, rbx
0x180012a0c  jz      short loc_180012A18
0x180012a0e  lea     rcx, [rbp+arg_10]
0x180012a12  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UDirect3D11CaptureFramePool@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(void)
0x180012a17  nop
0x180012a18  mov     rcx, rdi; SRWLock
0x180012a1b  call    ReleaseSRWLockExclusive_0
0x180012a20  nop
0x180012a21  test    rsi, rsi
0x180012a24  jz      short loc_180012A3A
0x180012a26  lea     rcx, [rbp+arg_18]
0x180012a2a  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UDirect3D11CaptureFramePool@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(void)
0x180012a2f  jmp     short loc_180012A3A
0x180012a31  mov     rcx, rdi; SRWLock
0x180012a34  call    ReleaseSRWLockExclusive_0
0x180012a39  nop
0x180012a3a  mov     rbx, [rsp+30h+arg_8]
0x180012a3f  add     rsp, 30h
0x180012a43  pop     r15
0x180012a45  pop     r14
0x180012a47  pop     r13
0x180012a49  pop     r12
0x180012a4b  pop     rdi
0x180012a4c  pop     rsi
0x180012a4d  pop     rbp
0x180012a4e  retn
```
