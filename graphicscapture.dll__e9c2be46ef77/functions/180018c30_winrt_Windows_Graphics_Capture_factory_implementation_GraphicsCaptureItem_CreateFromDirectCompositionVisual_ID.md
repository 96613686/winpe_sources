# winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem::CreateFromDirectCompositionVisual(IDCompositionDevice *,IDCompositionVisual *,int,int,_GUID const &,void * *)

- ea: `0x180018c30`
- end: `0x180018d83`
- name: `?CreateFromDirectCompositionVisual@GraphicsCaptureItem@factory_implementation@Capture@Graphics@Windows@winrt@@UEAAJPEAUIDCompositionDevice@@PEAUIDCompositionVisual@@HHAEBU_GUID@@PEAPEAX@Z`
- size: `339`
- prototype: `__int64 __fastcall(winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem *__hidden this, struct IDCompositionDevice *, struct IDCompositionVisual *, int, char, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180003580`
- `0x180006610`
- `0x1800125ec`
- `0x180016de4`
- `0x180018c30`
- `0x180028010`

## import_xrefs

- `CoreMessaging!CoreUICreate` at `0x180018c5e`
- `CoreMessaging!CoreUICreate` at `0x180018c5e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem::CreateFromDirectCompositionVisual(
        winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem *this,
        struct IDCompositionDevice *a2,
        struct IDCompositionVisual *a3,
        int a4,
        char a5,
        const struct _GUID *a6,
        void **a7)
{
  unsigned int v7; // eax
  __int64 (__fastcall ***v8)(_QWORD, const struct _GUID *, void **); // rcx
  unsigned int v9; // eax
  unsigned int v10; // eax
  __int64 result; // rax
  int v12; // [rsp+30h] [rbp-48h] BYREF
  __int64 (__fastcall ***v13)(_QWORD, const struct _GUID *, void **); // [rsp+38h] [rbp-40h] BYREF
  __int64 (__fastcall ***v14)(_QWORD, const struct _GUID *, void **); // [rsp+40h] [rbp-38h] BYREF
  __int64 (__fastcall ***v15)(_QWORD, const struct _GUID *, void **); // [rsp+48h] [rbp-30h] BYREF
  int v16; // [rsp+50h] [rbp-28h] BYREF
  __int128 v17; // [rsp+58h] [rbp-20h]
  struct IDCompositionDevice *v18; // [rsp+88h] [rbp+10h] BYREF
  struct IDCompositionVisual *v19; // [rsp+90h] [rbp+18h] BYREF
  int v20; // [rsp+98h] [rbp+20h] BYREF

  v20 = a4;
  v19 = a3;
  v18 = a2;
  v13 = 0;
  v16 = 0;
  v17 = 0;
  v7 = CoreUICreate(&v13);
  try
  {
    winrt::check_hresult(&v12, v7, &v16);
    v14 = v13;
    winrt::make<winrt::Windows::Graphics::Capture::implementation::DCompVisualGraphicsCaptureItem,IMessageSession *,IDCompositionDevice * &,IDCompositionVisual * &,int &,int &>(
      (unsigned int)&v15,
      (unsigned int)&v14,
      (unsigned int)&v18,
      (unsigned int)&v19,
      (__int64)&v20,
      (__int64)&a5);
    v8 = v15;
    v14 = 0;
    if ( v15 )
    {
      v16 = 0;
      v17 = 0;
      v9 = (**v15)(v15, (const struct _GUID *)&winrt::impl::guid_v<IUnknown>, (void **)&v14);
      winrt::check_hresult(&v12, v9, &v16);
      v8 = v14;
    }
    v16 = 0;
    v17 = 0;
    v10 = (**v8)(v8, a6, a7);
    winrt::check_hresult(&v12, v10, &v16);
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&v14);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v15);
    if ( v13 )
      winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&v13);
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v12);
  }
  return result;
}

```

## disassembly

```asm
0x180018c30  mov     rax, rsp
0x180018c33  mov     [rax+20h], r9d
0x180018c37  mov     [rax+18h], r8
0x180018c3b  mov     [rax+10h], rdx
0x180018c3f  sub     rsp, 78h
0x180018c43  mov     qword ptr [rax-40h], 0
0x180018c4b  mov     dword ptr [rax-28h], 0
0x180018c52  xorps   xmm0, xmm0
0x180018c55  movdqu  xmmword ptr [rax-20h], xmm0
0x180018c5a  lea     rcx, [rax-40h]
0x180018c5e  call    cs:__imp_CoreUICreate
0x180018c64  lea     r8, [rsp+78h+var_28]
0x180018c69  mov     edx, eax
0x180018c6b  lea     rcx, [rsp+78h+var_48]
0x180018c70  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180018c75  mov     rax, [rsp+78h+var_40]
0x180018c7a  mov     [rsp+78h+var_38], rax
0x180018c7f  lea     rax, [rsp+78h+arg_20]
0x180018c87  mov     [rsp+78h+var_50], rax
0x180018c8c  lea     rax, [rsp+78h+arg_18]
0x180018c94  mov     [rsp+78h+var_58], rax
0x180018c99  lea     r9, [rsp+78h+arg_10]
0x180018ca1  lea     r8, [rsp+78h+arg_8]
0x180018ca9  lea     rdx, [rsp+78h+var_38]
0x180018cae  lea     rcx, [rsp+78h+var_30]
0x180018cb3  call    ??$make@UDCompVisualGraphicsCaptureItem@implementation@Capture@Graphics@Windows@winrt@@PEAUIMessageSession@@AEAPEAUIDCompositionDevice@@AEAPEAUIDCompositionVisual@@AEAHAEAH@winrt@@YA?A_P$$QEAPEAUIMessageSession@@AEAPEAUIDCompositionDevice@@AEAPEAUIDCompositionVisual@@AEAH3@Z
0x180018cb8  nop
0x180018cb9  mov     rcx, [rsp+78h+var_30]
0x180018cbe  mov     [rsp+78h+var_38], 0
0x180018cc7  test    rcx, rcx
0x180018cca  jz      short loc_180018D0F
0x180018ccc  mov     [rsp+78h+var_28], 0
0x180018cd4  xorps   xmm0, xmm0
0x180018cd7  movdqu  [rsp+78h+var_20], xmm0
0x180018cdd  mov     rax, [rcx]
0x180018ce0  lea     r8, [rsp+78h+var_38]
0x180018ce5  lea     rdx, ??$guid_v@UIUnknown@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<IUnknown>
0x180018cec  mov     rax, [rax]
0x180018cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018cf4  lea     r8, [rsp+78h+var_28]
0x180018cf9  mov     edx, eax
0x180018cfb  lea     rcx, [rsp+78h+var_48]
0x180018d00  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180018d05  mov     rcx, [rsp+78h+var_38]
0x180018d0a  mov     [rsp+78h+var_38], rcx
0x180018d0f  mov     [rsp+78h+var_28], 0
0x180018d17  xorps   xmm0, xmm0
0x180018d1a  movdqu  [rsp+78h+var_20], xmm0
0x180018d20  mov     rax, [rcx]
0x180018d23  mov     r8, [rsp+78h+arg_30]
0x180018d2b  mov     rdx, [rsp+78h+arg_28]
0x180018d33  mov     rax, [rax]
0x180018d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d3b  lea     r8, [rsp+78h+var_28]
0x180018d40  mov     edx, eax
0x180018d42  lea     rcx, [rsp+78h+var_48]
0x180018d47  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180018d4c  nop
0x180018d4d  lea     rcx, [rsp+78h+var_38]
0x180018d52  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x180018d57  nop
0x180018d58  lea     rcx, [rsp+78h+var_30]
0x180018d5d  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180018d62  nop
0x180018d63  cmp     [rsp+78h+var_40], 0
0x180018d69  jz      short loc_180018D76
0x180018d6b  lea     rcx, [rsp+78h+var_40]
0x180018d70  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x180018d75  nop
0x180018d76  xor     eax, eax
0x180018d78  jmp     short loc_180018D7E
0x180018d7a  mov     eax, [rsp+78h+var_48]
0x180018d7e  add     rsp, 78h
0x180018d82  retn
```
