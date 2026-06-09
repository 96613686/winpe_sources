# winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::Direct3D11CaptureFramePool(winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DDevice const &,winrt::Windows::Graphics::DirectX::DirectXPixelFormat const &,int,winrt::Windows::Graphics::SizeInt32 const &,bool,bool)

- ea: `0x18000e3f0`
- end: `0x18000e68d`
- name: `??0Direct3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@QEAA@AEBUIDirect3DDevice@Direct3D11@DirectX@345@AEBW4DirectXPixelFormat@8345@HAEBUSizeInt32@345@_N3@Z`
- size: `669`
- prototype: `__int64 __usercall@<rax>(winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *__hidden this@<rcx>, const struct winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DDevice *@<rdx>, const enum winrt::Windows::Graphics::DirectX::DirectXPixelFormat *@<r8>, int@<r9d>, const struct winrt::Windows::Graphics::SizeInt32 *, bool, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002dd0`

## callees

- `0x1800065f0`
- `0x180006610`
- `0x18000e3f0`
- `0x18000ec20`
- `0x180011128`
- `0x1800125ec`
- `0x180012b14`
- `0x180012e34`

## import_xrefs

- `dcomp!__imp_CreateFlipObject` at `0x18000e60c`
- `dcomp!__imp_CreateFlipObject` at `0x18000e60c`
- `dcomp!__imp_OpenFlipConsumer` at `0x18000e656`
- `dcomp!__imp_OpenFlipConsumer` at `0x18000e656`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000e4ed`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000e4ed`
- `CoreMessaging!CoreUICreate` at `0x18000e5c2`
- `CoreMessaging!CoreUICreate` at `0x18000e5c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *__fastcall winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::Direct3D11CaptureFramePool(
        winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *this,
        const struct winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DDevice *a2,
        const enum winrt::Windows::Graphics::DirectX::DirectXPixelFormat *a3,
        int a4,
        const struct winrt::Windows::Graphics::SizeInt32 *a5,
        char a6,
        char a7)
{
  _QWORD *v8; // rsi
  _QWORD *v9; // r15
  _QWORD *v10; // r14
  int v11; // edx
  char *v12; // rdi
  char v13; // r12
  unsigned int v14; // eax
  unsigned int FlipObject; // eax
  unsigned int v16; // eax
  char v18; // [rsp+48h] [rbp-41h] BYREF
  char *v19; // [rsp+50h] [rbp-39h] BYREF
  __int128 v20; // [rsp+58h] [rbp-31h] BYREF
  int v21; // [rsp+68h] [rbp-21h] BYREF
  __int128 v22; // [rsp+70h] [rbp-19h]

  *((_QWORD *)this + 1) = &winrt::impl::produce<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool,winrt::Windows::Graphics::Capture::IDirect3D11CaptureFramePool>::`vftable';
  *((_QWORD *)this + 2) = &winrt::impl::produce<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IClosable>::`vftable';
  *(_QWORD *)this = &winrt::impl::producers_base<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool,std::tuple<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IClosable,IFlipContentCallback>>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *((_QWORD *)this + 4) = 1;
  *(_QWORD *)this = &winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool,std::tuple<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IClosable,IFlipContentCallback>>'};
  *((_QWORD *)this + 3) = &winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool,winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IClosable,winrt::cloaked<IFlipContentCallback>>'};
  *((_QWORD *)this + 5) = &winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool>::`vftable';
  *((_QWORD *)this + 6) = 0;
  v8 = (_QWORD *)((char *)this + 56);
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  v9 = (_QWORD *)((char *)this + 144);
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  v10 = (_QWORD *)((char *)this + 160);
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_BYTE *)this + 176) = 0;
  *((_DWORD *)this + 45) = 0;
  *((_QWORD *)this + 23) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 192), 0, 0);
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  v12 = (char *)this + 296;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  v13 = a7;
  if ( (Microsoft_Windows_GraphicsCapture_APIEnableBits & 1) != 0 )
    McTemplateU0qdddtt_EventWriteTransfer(
      (_DWORD)a5,
      v11,
      *(_DWORD *)a3,
      a4,
      *(_DWORD *)a5,
      *((_DWORD *)a5 + 1),
      a6,
      a7);
  if ( v12 != &v18 )
  {
    if ( *(_QWORD *)v12 )
      winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref((char *)this + 296);
    *(_QWORD *)v12 = 0;
  }
  *((_BYTE *)this + 176) = v13;
  if ( a6 )
  {
    LODWORD(v19) = 0;
    v20 = 0;
    if ( *v8 )
      winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(v8);
    v14 = CoreUICreate(v8);
    winrt::check_hresult(&a7, v14, &v19);
  }
  winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::Recreate(this, a2, a3, a4, a5);
  LODWORD(v19) = 0;
  v20 = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    v9,
    0);
  FlipObject = CreateFlipObject(v9);
  winrt::check_hresult(&a7, FlipObject, &v19);
  v21 = 0;
  v22 = 0;
  v19 = (char *)this + 152;
  *(_QWORD *)&v20 = 0;
  BYTE8(v20) = 1;
  if ( *v10 )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(v10);
  v16 = OpenFlipConsumer(*v9, v10, &v20);
  winrt::check_hresult(&a7, v16, &v21);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v19);
  return this;
}

```

## disassembly

```asm
0x18000e3f0  mov     rax, rsp
0x18000e3f3  mov     [rax+20h], r9d
0x18000e3f7  mov     [rax+18h], r8
0x18000e3fb  mov     [rax+10h], rdx
0x18000e3ff  mov     [rax+8], rcx
0x18000e403  push    rbp
0x18000e404  push    rbx
0x18000e405  push    rsi
0x18000e406  push    rdi
0x18000e407  push    r12
0x18000e409  push    r13
0x18000e40b  push    r14
0x18000e40d  push    r15
0x18000e40f  lea     rbp, [rax-47h]
0x18000e413  sub     rsp, 88h
0x18000e41a  mov     rbx, rcx
0x18000e41d  lea     rax, ??_7?$produce@UDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@UIDirect3D11CaptureFramePool@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool,winrt::Windows::Graphics::Capture::IDirect3D11CaptureFramePool>::`vftable'
0x18000e424  mov     [rcx+8], rax
0x18000e428  lea     rax, ??_7?$produce@UDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@UIClosable@Foundation@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IClosable>::`vftable'
0x18000e42f  mov     [rcx+10h], rax
0x18000e433  lea     rax, ??_7?$producers_base@UDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@V?$tuple@UDirect3D11CaptureFramePool@Capture@Graphics@Windows@winrt@@UIClosable@Foundation@45@UIFlipContentCallback@@@std@@@impl@winrt@@6B@; const winrt::impl::producers_base<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool,std::tuple<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IClosable,IFlipContentCallback>>::`vftable'
0x18000e43a  mov     [rcx], rax
0x18000e43d  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000e444  mov     qword ptr [rcx+20h], 1
0x18000e44c  lea     rax, ??_7Direct3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@6B?$producers_base@UDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@V?$tuple@UDirect3D11CaptureFramePool@Capture@Graphics@Windows@winrt@@UIClosable@Foundation@45@UIFlipContentCallback@@@std@@@impl@5@@; const winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool,std::tuple<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IClosable,IFlipContentCallback>>'}
0x18000e453  mov     [rcx], rax
0x18000e456  lea     rax, ??_7Direct3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@6B?$root_implements@UDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@U13456@UIClosable@Foundation@56@U?$cloaked@UIFlipContentCallback@@@6@@impl@5@@; const winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool,winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IClosable,winrt::cloaked<IFlipContentCallback>>'}
0x18000e45d  mov     [rcx+18h], rax
0x18000e461  lea     rax, ??_7?$heap_implements@UDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool>::`vftable'
0x18000e468  mov     [rcx+28h], rax
0x18000e46c  xor     r12d, r12d
0x18000e46f  mov     [rcx+30h], r12
0x18000e473  lea     rsi, [rcx+38h]
0x18000e477  mov     [rsi], r12
0x18000e47a  mov     [rcx+40h], r12
0x18000e47e  mov     [rcx+48h], r12
0x18000e482  mov     [rcx+50h], r12
0x18000e486  mov     [rcx+58h], r12
0x18000e48a  mov     [rcx+60h], r12
0x18000e48e  mov     [rcx+68h], r12
0x18000e492  mov     [rcx+70h], r12
0x18000e496  mov     [rcx+78h], r12
0x18000e49a  mov     [rcx+80h], r12
0x18000e4a1  mov     [rcx+88h], r12
0x18000e4a8  lea     r15, [rcx+90h]
0x18000e4af  mov     [r15], r12
0x18000e4b2  mov     [rcx+98h], r12
0x18000e4b9  lea     r14, [rcx+0A0h]
0x18000e4c0  mov     [r14], r12
0x18000e4c3  mov     [rcx+0A8h], r12
0x18000e4ca  mov     [rcx+0B0h], r12b
0x18000e4d1  mov     [rcx+0B4h], r12d
0x18000e4d8  xor     eax, eax
0x18000e4da  mov     [rcx+0B8h], rax
0x18000e4e1  add     rcx, 0C0h; lpCriticalSection
0x18000e4e8  xor     r8d, r8d; Flags
0x18000e4eb  xor     edx, edx; dwSpinCount
0x18000e4ed  call    cs:__imp_InitializeCriticalSectionEx
0x18000e4f3  nop
0x18000e4f4  mov     [rbx+0E8h], r12
0x18000e4fb  mov     [rbx+0F0h], r12
0x18000e502  mov     [rbx+0F8h], r12
0x18000e509  mov     [rbx+100h], r12
0x18000e510  mov     [rbx+108h], r12
0x18000e517  mov     [rbx+110h], r12
0x18000e51e  mov     [rbx+118h], r12
0x18000e525  mov     [rbx+120h], r12
0x18000e52c  lea     rdi, [rbx+128h]
0x18000e533  mov     [rdi], r12
0x18000e536  mov     [rbx+130h], r12
0x18000e53d  movzx   r12d, [rbp+3Fh+arg_30]
0x18000e542  movzx   r13d, [rbp+3Fh+arg_28]
0x18000e547  test    cs:Microsoft_Windows_GraphicsCapture_APIEnableBits, 1
0x18000e54e  jz      short loc_18000E57B
0x18000e550  mov     [rsp+38h], r12d
0x18000e555  mov     [rsp+0C0h+var_90], r13d
0x18000e55a  mov     rcx, [rbp+3Fh+arg_20]
0x18000e55e  mov     eax, [rcx+4]
0x18000e561  mov     [rsp+0C0h+var_98], eax
0x18000e565  mov     eax, [rcx]
0x18000e567  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18000e56b  mov     r9d, [rbp+3Fh+arg_18]
0x18000e56f  mov     r8, [rbp+3Fh+arg_10]
0x18000e573  mov     r8d, [r8]
0x18000e576  call    McTemplateU0qdddtt_EventWriteTransfer
0x18000e57b  lea     rax, [rbp+3Fh+var_80]
0x18000e57f  cmp     rdi, rax
0x18000e582  jz      short loc_18000E599
0x18000e584  cmp     qword ptr [rdi], 0
0x18000e588  jz      short loc_18000E592
0x18000e58a  mov     rcx, rdi
0x18000e58d  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x18000e592  mov     qword ptr [rdi], 0
0x18000e599  mov     [rbx+0B0h], r12b
0x18000e5a0  xor     edi, edi
0x18000e5a2  test    r13b, r13b
0x18000e5a5  jz      short loc_18000E5D7
0x18000e5a7  mov     dword ptr [rbp+3Fh+var_78], edi
0x18000e5aa  xorps   xmm0, xmm0
0x18000e5ad  movdqu  [rbp+3Fh+var_70], xmm0
0x18000e5b2  cmp     [rsi], rdi
0x18000e5b5  jz      short loc_18000E5BF
0x18000e5b7  mov     rcx, rsi
0x18000e5ba  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x18000e5bf  mov     rcx, rsi
0x18000e5c2  call    cs:__imp_CoreUICreate
0x18000e5c8  lea     r8, [rbp+3Fh+var_78]
0x18000e5cc  mov     edx, eax
0x18000e5ce  lea     rcx, [rbp+3Fh+arg_30]
0x18000e5d2  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000e5d7  mov     rax, [rbp+3Fh+arg_20]
0x18000e5db  mov     [rsp+0C0h+var_A0], rax; struct winrt::Windows::Graphics::SizeInt32 *
0x18000e5e0  mov     r9d, [rbp+3Fh+arg_18]; int
0x18000e5e4  mov     r8, [rbp+3Fh+arg_10]; enum winrt::Windows::Graphics::DirectX::DirectXPixelFormat *
0x18000e5e8  mov     rdx, [rbp+3Fh+arg_8]; struct winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DDevice *
0x18000e5ec  mov     rcx, rbx; this
0x18000e5ef  call    ?Recreate@Direct3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@QEAAXAEBUIDirect3DDevice@Direct3D11@DirectX@456@AEBW4DirectXPixelFormat@9456@HAEBUSizeInt32@456@@Z; winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::Recreate(winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DDevice const &,winrt::Windows::Graphics::DirectX::DirectXPixelFormat const &,int,winrt::Windows::Graphics::SizeInt32 const &)
0x18000e5f4  mov     dword ptr [rbp+3Fh+var_78], edi
0x18000e5f7  xorps   xmm0, xmm0
0x18000e5fa  movdqu  [rbp+3Fh+var_70], xmm0
0x18000e5ff  xor     edx, edx
0x18000e601  mov     rcx, r15
0x18000e604  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000e609  mov     rcx, r15
0x18000e60c  call    cs:__imp_CreateFlipObject
0x18000e612  lea     r8, [rbp+3Fh+var_78]
0x18000e616  mov     edx, eax
0x18000e618  lea     rcx, [rbp+3Fh+arg_30]
0x18000e61c  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000e621  mov     [rbp+3Fh+var_60], edi
0x18000e624  xorps   xmm0, xmm0
0x18000e627  movdqu  [rbp+3Fh+var_58], xmm0
0x18000e62c  lea     rax, [rbx+98h]
0x18000e633  mov     [rbp+3Fh+var_78], rax
0x18000e637  mov     qword ptr [rbp+3Fh+var_70], rdi
0x18000e63b  mov     byte ptr [rbp+3Fh+var_70+8], 1
0x18000e63f  cmp     [r14], rdi
0x18000e642  jz      short loc_18000E64C
0x18000e644  mov     rcx, r14
0x18000e647  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x18000e64c  lea     r8, [rbp+3Fh+var_70]
0x18000e650  mov     rdx, r14
0x18000e653  mov     rcx, [r15]
0x18000e656  call    cs:__imp_OpenFlipConsumer
0x18000e65c  lea     r8, [rbp+3Fh+var_60]
0x18000e660  mov     edx, eax
0x18000e662  lea     rcx, [rbp+3Fh+arg_30]
0x18000e666  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000e66b  nop
0x18000e66c  lea     rcx, [rbp+3Fh+var_78]
0x18000e670  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18000e675  nop
0x18000e676  mov     rax, rbx
0x18000e679  add     rsp, 88h
0x18000e680  pop     r15
0x18000e682  pop     r14
0x18000e684  pop     r13
0x18000e686  pop     r12
0x18000e688  pop     rdi
0x18000e689  pop     rsi
0x18000e68a  pop     rbx
0x18000e68b  pop     rbp
0x18000e68c  retn
```
