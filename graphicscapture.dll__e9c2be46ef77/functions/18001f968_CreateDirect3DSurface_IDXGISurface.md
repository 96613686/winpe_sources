# CreateDirect3DSurface(IDXGISurface *)

- ea: `0x18001f968`
- end: `0x18001fa24`
- name: `?CreateDirect3DSurface@@YA@PEAUIDXGISurface@@@Z`
- size: `188`
- prototype: `_QWORD(struct IDXGISurface *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001efbc`

## callees

- `0x180006610`
- `0x1800125ec`
- `0x18001f968`
- `0x180028010`

## import_xrefs

- `d3d11!CreateDirect3D11SurfaceFromDXGISurface` at `0x18001f99e`
- `d3d11!CreateDirect3D11SurfaceFromDXGISurface` at `0x18001f99e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct IDXGISurface *__fastcall CreateDirect3DSurface(struct IDXGISurface *a1, IDXGISurface *a2)
{
  unsigned int v3; // eax
  IInspectable *v4; // rcx
  unsigned int v5; // eax
  int v7; // [rsp+28h] [rbp-18h] BYREF
  __int128 v8; // [rsp+30h] [rbp-10h]
  struct IDXGISurface *v9; // [rsp+50h] [rbp+10h] BYREF
  IInspectable *graphicsSurface; // [rsp+60h] [rbp+20h] BYREF
  struct IDXGISurfaceVtbl *v11; // [rsp+68h] [rbp+28h] BYREF

  v9 = a1;
  graphicsSurface = 0;
  v7 = 0;
  v8 = 0;
  v3 = CreateDirect3D11SurfaceFromDXGISurface(a2, &graphicsSurface);
  winrt::check_hresult(&v9, v3, &v7);
  v4 = graphicsSurface;
  if ( graphicsSurface )
  {
    v11 = 0;
    v7 = 0;
    v8 = 0;
    v5 = ((__int64 (__fastcall *)(IInspectable *, __int64 *, struct IDXGISurfaceVtbl **))graphicsSurface->lpVtbl->QueryInterface)(
           graphicsSurface,
           &winrt::impl::guid_v<winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface>,
           &v11);
    winrt::check_hresult(&v9, v5, &v7);
    a1->lpVtbl = v11;
    v4 = graphicsSurface;
  }
  else
  {
    a1->lpVtbl = 0;
  }
  if ( v4 )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&graphicsSurface);
  return a1;
}

```

## disassembly

```asm
0x18001f968  mov     [rsp-8+arg_8], rbx
0x18001f96d  mov     [rsp-8+arg_0], rcx
0x18001f972  push    rbp
0x18001f973  mov     rbp, rsp
0x18001f976  sub     rsp, 40h
0x18001f97a  mov     rax, rdx
0x18001f97d  mov     rbx, rcx
0x18001f980  mov     [rbp+graphicsSurface], 0
0x18001f988  mov     [rbp+var_18], 0
0x18001f98f  xorps   xmm0, xmm0
0x18001f992  movdqu  [rbp+var_10], xmm0
0x18001f997  lea     rdx, [rbp+graphicsSurface]; graphicsSurface
0x18001f99b  mov     rcx, rax; dgxiSurface
0x18001f99e  call    cs:__imp_CreateDirect3D11SurfaceFromDXGISurface
0x18001f9a4  lea     r8, [rbp+var_18]
0x18001f9a8  mov     edx, eax
0x18001f9aa  lea     rcx, [rbp+arg_0]
0x18001f9ae  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001f9b3  mov     rcx, [rbp+graphicsSurface]
0x18001f9b7  test    rcx, rcx
0x18001f9ba  jnz     short loc_18001F9C1
0x18001f9bc  mov     [rbx], rcx
0x18001f9bf  jmp     short loc_18001FA08
0x18001f9c1  mov     [rbp+arg_18], 0
0x18001f9c9  mov     [rbp+var_18], 0
0x18001f9d0  xorps   xmm0, xmm0
0x18001f9d3  movdqu  [rbp+var_10], xmm0
0x18001f9d8  mov     rax, [rcx]
0x18001f9db  lea     r8, [rbp+arg_18]
0x18001f9df  lea     rdx, ??$guid_v@UIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface>
0x18001f9e6  mov     rax, [rax]
0x18001f9e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9ee  lea     r8, [rbp+var_18]
0x18001f9f2  mov     edx, eax
0x18001f9f4  lea     rcx, [rbp+arg_0]
0x18001f9f8  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001f9fd  mov     rax, [rbp+arg_18]
0x18001fa01  mov     [rbx], rax
0x18001fa04  mov     rcx, [rbp+graphicsSurface]
0x18001fa08  test    rcx, rcx
0x18001fa0b  jz      short loc_18001FA16
0x18001fa0d  lea     rcx, [rbp+graphicsSurface]
0x18001fa11  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x18001fa16  mov     rax, rbx
0x18001fa19  mov     rbx, [rsp+40h+arg_8]
0x18001fa1e  add     rsp, 40h
0x18001fa22  pop     rbp
0x18001fa23  retn
```
