# winrt::Windows::Internal::Eap::Utility::implementation::CreateIBufferOverCallerManagedBytes(gsl::span<uchar,-1>)

- ea: `0x18002e2c8`
- end: `0x18002e42b`
- name: `?CreateIBufferOverCallerManagedBytes@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AUIBuffer@Streams@Storage@56@V?$span@E$0?0@gsl@@@Z`
- size: `355`
- prototype: `_QWORD *__fastcall(_QWORD *, int *)`
- caller_count: `7`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000f5c0`
- `0x18000f900`
- `0x1800188f0`
- `0x180018e1c`
- `0x18001e190`
- `0x18001e774`
- `0x1800294d0`

## callees

- `0x180003820`
- `0x1800101c4`
- `0x180010e04`
- `0x180016864`
- `0x180024f14`
- `0x18002e2c8`
- `0x180033010`

## pseudocode

```c
_QWORD *__fastcall winrt::Windows::Internal::Eap::Utility::implementation::CreateIBufferOverCallerManagedBytes(
        _QWORD *a1,
        int *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  int v6; // edi
  int v7; // edi
  __int64 (__fastcall ***v8)(_QWORD, __int64 *, _QWORD *); // rcx
  int v9; // eax
  int v11; // [rsp+20h] [rbp-38h]
  int v12; // [rsp+28h] [rbp-30h] BYREF
  __int128 v13; // [rsp+30h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 (__fastcall ***v15)(_QWORD, __int64 *, __int64 *); // [rsp+68h] [rbp+10h] BYREF
  __int64 v16; // [rsp+70h] [rbp+18h] BYREF

  v15 = 0;
  v4 = operator new(0x70u, (const struct std::nothrow_t *)std::nothrow);
  v5 = v4;
  if ( v4 )
  {
    v6 = *a2;
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>(v4);
    v5[10] = *((_QWORD *)a2 + 1);
    *((_DWORD *)v5 + 22) = v6;
    *((_DWORD *)v5 + 23) = v6;
    v5[13] = 0;
    *v5 = &Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>::`vftable';
    v5[1] = &Windows::Storage::Streams::CBuffer<Windows::Storage::Streams::CBuffer_StandardCleanup,Windows::Storage::Streams::DefaultMarshaler>::`vftable'{for `IWeakReferenceSource'};
    v5[2] = &Windows::Storage::Streams::CBuffer<Windows::Storage::Streams::CBuffer_StandardCleanup,Windows::Storage::Streams::DefaultMarshaler>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>'};
    v5[3] = &Windows::Storage::Streams::CBuffer<Windows::Storage::Streams::CBuffer_StandardCleanup,Windows::Storage::Streams::DefaultMarshaler>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,IMarshal>'};
    v5[4] = &Windows::Storage::Streams::CBuffer<Windows::Storage::Streams::CBuffer_StandardCleanup,Windows::Storage::Streams::DefaultMarshaler>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    v7 = ((__int64 (__fastcall *)(_QWORD *, GUID *, _QWORD))Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>::`vftable')(
           v5,
           &GUID_905a0fe0_bc53_11df_8c49_001e4fc686da,
           &v15);
  }
  else
  {
    v5 = 0;
    v7 = -2147024882;
  }
  if ( v5 )
    (*(void (__fastcall **)(_QWORD *))(*v5 + 16LL))(v5);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8A,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\utilities.cpp",
      (const char *)(unsigned int)v7,
      v11);
  v8 = v15;
  if ( v15 )
  {
    v16 = 0;
    v12 = 0;
    v13 = 0;
    v9 = (**v15)(v15, winrt::impl::guid_v<winrt::Windows::Storage::Streams::IBuffer>, &v16);
    if ( v9 < 0 )
      winrt::throw_hresult((unsigned int)v9, &v12);
    *a1 = v16;
    v8 = v15;
  }
  else
  {
    *a1 = 0;
  }
  if ( v8 )
    winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(&v15);
  return a1;
}

```

## disassembly

```asm
0x18002e2c8  mov     [rsp+arg_0], rbx
0x18002e2cd  push    rsi
0x18002e2ce  push    rdi
0x18002e2cf  push    r14
0x18002e2d1  sub     rsp, 40h
0x18002e2d5  mov     r14, rdx
0x18002e2d8  mov     rsi, rcx
0x18002e2db  mov     [rsp+58h+arg_8], 0
0x18002e2e4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002e2eb  mov     ecx, 70h ; 'p'; unsigned __int64
0x18002e2f0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002e2f5  mov     rbx, rax
0x18002e2f8  test    rax, rax
0x18002e2fb  jz      short loc_18002E373
0x18002e2fd  mov     edi, [r14]
0x18002e300  mov     rcx, rax
0x18002e303  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>(void)
0x18002e308  mov     rax, [r14+8]
0x18002e30c  mov     [rbx+50h], rax
0x18002e310  mov     [rbx+58h], edi
0x18002e313  mov     [rbx+5Ch], edi
0x18002e316  mov     qword ptr [rbx+68h], 0
0x18002e31e  lea     rax, ??_7?$CBuffer@V_lambda_8fcabb03306c9f8765c03020018d7da6_@@UDefaultMarshaler@Streams@Storage@Windows@@@Streams@Storage@Windows@@6B@; const Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>::`vftable'
0x18002e325  mov     [rbx], rax
0x18002e328  lea     rax, ??_7?$CBuffer@VCBuffer_StandardCleanup@Streams@Storage@Windows@@UDefaultMarshaler@234@@Streams@Storage@Windows@@6BIWeakReferenceSource@@@; const Windows::Storage::Streams::CBuffer<Windows::Storage::Streams::CBuffer_StandardCleanup,Windows::Storage::Streams::DefaultMarshaler>::`vftable'{for `IWeakReferenceSource'}
0x18002e32f  mov     [rbx+8], rax
0x18002e333  lea     rax, ??_7?$CBuffer@VCBuffer_StandardCleanup@Streams@Storage@Windows@@UDefaultMarshaler@234@@Streams@Storage@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@; const Windows::Storage::Streams::CBuffer<Windows::Storage::Streams::CBuffer_StandardCleanup,Windows::Storage::Streams::DefaultMarshaler>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>'}
0x18002e33a  mov     [rbx+10h], rax
0x18002e33e  lea     rax, ??_7?$CBuffer@VCBuffer_StandardCleanup@Streams@Storage@Windows@@UDefaultMarshaler@234@@Streams@Storage@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00UIMarshal@@@Details@WRL@Microsoft@@@; const Windows::Storage::Streams::CBuffer<Windows::Storage::Streams::CBuffer_StandardCleanup,Windows::Storage::Streams::DefaultMarshaler>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,IMarshal>'}
0x18002e345  mov     [rbx+18h], rax
0x18002e349  lea     rax, ??_7?$CBuffer@VCBuffer_StandardCleanup@Streams@Storage@Windows@@UDefaultMarshaler@234@@Streams@Storage@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Storage::Streams::CBuffer<Windows::Storage::Streams::CBuffer_StandardCleanup,Windows::Storage::Streams::DefaultMarshaler>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18002e350  mov     [rbx+20h], rax
0x18002e354  lea     r8, [rsp+58h+arg_8]
0x18002e359  lea     rdx, _GUID_905a0fe0_bc53_11df_8c49_001e4fc686da
0x18002e360  mov     rcx, rbx
0x18002e363  mov     rax, cs:??_7?$CBuffer@V_lambda_8fcabb03306c9f8765c03020018d7da6_@@UDefaultMarshaler@Streams@Storage@Windows@@@Streams@Storage@Windows@@6B@; const Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>::`vftable'
0x18002e36a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e36f  mov     edi, eax
0x18002e371  jmp     short loc_18002E37A
0x18002e373  xor     ebx, ebx
0x18002e375  mov     edi, 8007000Eh
0x18002e37a  test    rbx, rbx
0x18002e37d  jz      short loc_18002E38F
0x18002e37f  mov     rax, [rbx]
0x18002e382  mov     rcx, rbx
0x18002e385  mov     rax, [rax+10h]
0x18002e389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e38e  nop
0x18002e38f  mov     rcx, [rsp+58h]; this
0x18002e394  test    edi, edi
0x18002e396  js      short loc_18002E416
0x18002e398  mov     rcx, [rsp+58h+arg_8]
0x18002e39d  test    rcx, rcx
0x18002e3a0  jnz     short loc_18002E3A7
0x18002e3a2  mov     [rsi], rcx
0x18002e3a5  jmp     short loc_18002E3E9
0x18002e3a7  mov     [rsp+58h+arg_10], 0
0x18002e3b0  mov     [rsp+58h+var_30], 0
0x18002e3b8  xorps   xmm0, xmm0
0x18002e3bb  movdqu  [rsp+58h+var_28], xmm0
0x18002e3c1  mov     rax, [rcx]
0x18002e3c4  lea     r8, [rsp+58h+arg_10]
0x18002e3c9  lea     rdx, ??$guid_v@UIBuffer@Streams@Storage@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Storage::Streams::IBuffer>
0x18002e3d0  mov     rax, [rax]
0x18002e3d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3d8  test    eax, eax
0x18002e3da  js      short loc_18002E409
0x18002e3dc  mov     rax, [rsp+58h+arg_10]
0x18002e3e1  mov     [rsi], rax
0x18002e3e4  mov     rcx, [rsp+58h+arg_8]
0x18002e3e9  test    rcx, rcx
0x18002e3ec  jz      short loc_18002E3F8
0x18002e3ee  lea     rcx, [rsp+58h+arg_8]
0x18002e3f3  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x18002e3f8  mov     rax, rsi
0x18002e3fb  mov     rbx, [rsp+58h+arg_0]
0x18002e400  add     rsp, 40h
0x18002e404  pop     r14
0x18002e406  pop     rdi
0x18002e407  pop     rsi
0x18002e408  retn
0x18002e409  lea     rdx, [rsp+58h+var_30]
0x18002e40e  mov     ecx, eax
0x18002e410  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002e416  mov     r9d, edi; char *
0x18002e419  lea     r8, aOnecoreuapNetE_5; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18002e420  mov     edx, 8Ah; void *
0x18002e425  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
