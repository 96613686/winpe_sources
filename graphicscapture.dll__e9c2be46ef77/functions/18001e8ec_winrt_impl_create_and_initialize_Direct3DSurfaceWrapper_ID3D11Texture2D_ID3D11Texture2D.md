# winrt::impl::create_and_initialize<Direct3DSurfaceWrapper,ID3D11Texture2D *>(ID3D11Texture2D * &&)

- ea: `0x18001e8ec`
- end: `0x18001e976`
- name: `??$create_and_initialize@UDirect3DSurfaceWrapper@@PEAUID3D11Texture2D@@@impl@winrt@@YAPEAUDirect3DSurfaceWrapper@@$$QEAPEAUID3D11Texture2D@@@Z`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001efbc`

## callees

- `0x180002158`
- `0x180002da8`
- `0x180012564`
- `0x18001e8ec`
- `0x18001ef04`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::create_and_initialize<Direct3DSurfaceWrapper,ID3D11Texture2D *>(_QWORD *a1)
{
  _QWORD *v2; // rdi
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 *v6; // rcx

  v2 = operator new(0x28u);
  winrt::impl::producers_base<Direct3DSurfaceWrapper,std::tuple<winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface,Windows::Graphics::DirectX::Direct3D11::IDirect3DDxgiInterfaceAccess>>::producers_base<Direct3DSurfaceWrapper,std::tuple<winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface,Windows::Graphics::DirectX::Direct3D11::IDirect3DDxgiInterfaceAccess>>(
    v2,
    v3,
    v4,
    *a1);
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  std::atomic<unsigned __int64>::atomic<unsigned __int64>(v2 + 3);
  *v2 = &Direct3DSurfaceWrapper::`vftable'{for `winrt::impl::producers_base<Direct3DSurfaceWrapper,std::tuple<winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface,Windows::Graphics::DirectX::Direct3D11::IDirect3DDxgiInterfaceAccess>>'};
  v2[2] = &Direct3DSurfaceWrapper::`vftable'{for `winrt::impl::root_implements<Direct3DSurfaceWrapper,winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface,winrt::cloaked<Windows::Graphics::DirectX::Direct3D11::IDirect3DDxgiInterfaceAccess>>'};
  v6 = v2 + 4;
  v2[4] = 0;
  if ( v5 )
  {
    *v6 = v5;
    winrt::com_ptr<IDCompositionVisual>::add_ref(v6);
  }
  *v2 = &Direct3DSurfaceWrapper::`vftable'{for `winrt::impl::producers_base<Direct3DSurfaceWrapper,std::tuple<winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface,Windows::Graphics::DirectX::Direct3D11::IDirect3DDxgiInterfaceAccess>>'};
  v2[2] = &Direct3DSurfaceWrapper::`vftable'{for `winrt::impl::root_implements<Direct3DSurfaceWrapper,winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface,winrt::cloaked<Windows::Graphics::DirectX::Direct3D11::IDirect3DDxgiInterfaceAccess>>'};
  return v2;
}

```

## disassembly

```asm
0x18001e8ec  mov     [rsp+arg_0], rbx
0x18001e8f1  push    rdi
0x18001e8f2  sub     rsp, 20h
0x18001e8f6  mov     rbx, rcx
0x18001e8f9  mov     ecx, 28h ; '('; Size
0x18001e8fe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e903  mov     r9, [rbx]
0x18001e906  mov     rcx, rax
0x18001e909  mov     rdi, rax
0x18001e90c  mov     [rsp+28h+arg_8], rax
0x18001e911  call    ??0?$producers_base@UDirect3DSurfaceWrapper@@V?$tuple@UIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@winrt@@UIDirect3DDxgiInterfaceAccess@2345@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<Direct3DSurfaceWrapper,std::tuple<winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface,Windows::Graphics::DirectX::Direct3D11::IDirect3DDxgiInterfaceAccess>>::producers_base<Direct3DSurfaceWrapper,std::tuple<winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface,Windows::Graphics::DirectX::Direct3D11::IDirect3DDxgiInterfaceAccess>>(void)
0x18001e916  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001e91d  lea     rcx, [rdi+18h]
0x18001e921  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x18001e926  lea     rax, ??_7Direct3DSurfaceWrapper@@6B?$producers_base@UDirect3DSurfaceWrapper@@V?$tuple@UIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@winrt@@UIDirect3DDxgiInterfaceAccess@2345@@std@@@impl@winrt@@@; const Direct3DSurfaceWrapper::`vftable'{for `winrt::impl::producers_base<Direct3DSurfaceWrapper,std::tuple<winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface,Windows::Graphics::DirectX::Direct3D11::IDirect3DDxgiInterfaceAccess>>'}
0x18001e92d  mov     [rdi], rax
0x18001e930  lea     rax, ??_7Direct3DSurfaceWrapper@@6B?$root_implements@UDirect3DSurfaceWrapper@@UIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@winrt@@U?$cloaked@UIDirect3DDxgiInterfaceAccess@Direct3D11@DirectX@Graphics@Windows@@@7@@impl@winrt@@@; const Direct3DSurfaceWrapper::`vftable'{for `winrt::impl::root_implements<Direct3DSurfaceWrapper,winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface,winrt::cloaked<Windows::Graphics::DirectX::Direct3D11::IDirect3DDxgiInterfaceAccess>>'}
0x18001e937  mov     [rdi+10h], rax
0x18001e93b  lea     rcx, [rdi+20h]
0x18001e93f  mov     qword ptr [rcx], 0
0x18001e946  test    r9, r9
0x18001e949  jz      short loc_18001E953
0x18001e94b  mov     [rcx], r9
0x18001e94e  call    ?add_ref@?$com_ptr@UIDCompositionVisual@@@winrt@@AEBAXXZ; winrt::com_ptr<IDCompositionVisual>::add_ref(void)
0x18001e953  mov     rbx, [rsp+28h+arg_0]
0x18001e958  lea     rax, ??_7Direct3DSurfaceWrapper@@6B?$producers_base@UDirect3DSurfaceWrapper@@V?$tuple@UIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@winrt@@UIDirect3DDxgiInterfaceAccess@2345@@std@@@impl@winrt@@@; const Direct3DSurfaceWrapper::`vftable'{for `winrt::impl::producers_base<Direct3DSurfaceWrapper,std::tuple<winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface,Windows::Graphics::DirectX::Direct3D11::IDirect3DDxgiInterfaceAccess>>'}
0x18001e95f  mov     [rdi], rax
0x18001e962  lea     rax, ??_7Direct3DSurfaceWrapper@@6B?$root_implements@UDirect3DSurfaceWrapper@@UIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@winrt@@U?$cloaked@UIDirect3DDxgiInterfaceAccess@Direct3D11@DirectX@Graphics@Windows@@@7@@impl@winrt@@@; const Direct3DSurfaceWrapper::`vftable'{for `winrt::impl::root_implements<Direct3DSurfaceWrapper,winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface,winrt::cloaked<Windows::Graphics::DirectX::Direct3D11::IDirect3DDxgiInterfaceAccess>>'}
0x18001e969  mov     [rdi+10h], rax
0x18001e96d  mov     rax, rdi
0x18001e970  add     rsp, 20h
0x18001e974  pop     rdi
0x18001e975  retn
```
