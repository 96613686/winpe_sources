# `winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)'::`2'::marshaler::get_marshaler(void)

- ea: `0x180005bec`
- end: `0x180005cca`
- name: `?get_marshaler@marshaler@?1??make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@34@PEAPEAX@Z@CA?AU?$com_ptr@UIMarshal@impl@winrt@@@4@XZ`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005d68`

## callees

- `0x180002411`
- `0x180005bec`
- `0x1800065f0`
- `0x180028010`

## pseudocode

```c
__int64 *__fastcall `winrt::impl::make_marshaler'::`2'::marshaler::get_marshaler(__int64 *a1)
{
  struct IUnknownVtbl *lpVtbl; // rax
  __int64 v3; // rax
  __int64 *v4; // rcx
  __int64 v5; // rbx
  char v6; // di
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+28h] BYREF
  __int64 v9; // [rsp+58h] [rbp+30h] BYREF
  __int64 v10; // [rsp+60h] [rbp+38h] BYREF
  __int64 v11; // [rsp+68h] [rbp+40h] BYREF

  ppunkMarshal = 0;
  WINRT_IMPL_CoCreateFreeThreadedMarshaler(0, &ppunkMarshal);
  if ( ppunkMarshal )
  {
    lpVtbl = ppunkMarshal->lpVtbl;
    v9 = 0;
    ((void (__fastcall *)(LPUNKNOWN, __int64 *, __int64 *))lpVtbl->QueryInterface)(
      ppunkMarshal,
      &winrt::impl::guid_v<winrt::impl::IMarshal>,
      &v9);
    v3 = v9;
    v4 = &v11;
    v5 = v10;
    v6 = 1;
  }
  else
  {
    v5 = 0;
    v4 = &v9;
    v10 = 0;
    v3 = 0;
    v6 = 6;
  }
  *v4 = 0;
  *a1 = v3;
  if ( (v6 & 4) != 0 )
  {
    v6 &= ~4u;
    if ( v9 )
      winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(&v9);
  }
  if ( (v6 & 2) != 0 )
  {
    v6 &= ~2u;
    if ( v5 )
      winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(&v10);
  }
  if ( (v6 & 1) != 0 && v11 )
    winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(&v11);
  if ( ppunkMarshal )
    winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref((__int64 *)&ppunkMarshal);
  return a1;
}

```

## disassembly

```asm
0x180005bec  push    rbp
0x180005bee  push    rbx
0x180005bef  push    rsi
0x180005bf0  push    rdi
0x180005bf1  mov     rbp, rsp
0x180005bf4  sub     rsp, 28h
0x180005bf8  mov     rsi, rcx
0x180005bfb  mov     dword ptr [rbp+ppunkMarshal], 0
0x180005c02  xor     ecx, ecx; punkOuter
0x180005c04  mov     [rbp+ppunkMarshal], 0
0x180005c0c  lea     rdx, [rbp+ppunkMarshal]; ppunkMarshal
0x180005c10  call    WINRT_IMPL_CoCreateFreeThreadedMarshaler
0x180005c15  mov     rcx, [rbp+ppunkMarshal]
0x180005c19  test    rcx, rcx
0x180005c1c  jz      short loc_180005C4F
0x180005c1e  mov     rax, [rcx]
0x180005c21  lea     r8, [rbp+arg_8]
0x180005c25  lea     rdx, ??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMarshal>
0x180005c2c  mov     [rbp+arg_8], 0
0x180005c34  mov     rax, [rax]
0x180005c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c3c  mov     rax, [rbp+arg_8]
0x180005c40  lea     rcx, [rbp+arg_18]
0x180005c44  mov     rbx, [rbp+arg_10]
0x180005c48  mov     edi, 1
0x180005c4d  jmp     short loc_180005C5E
0x180005c4f  xor     ebx, ebx
0x180005c51  lea     rcx, [rbp+arg_8]
0x180005c55  mov     [rbp+arg_10], rbx
0x180005c59  xor     eax, eax
0x180005c5b  lea     edi, [rbx+6]
0x180005c5e  mov     qword ptr [rcx], 0
0x180005c65  mov     [rsi], rax
0x180005c68  test    dil, 4
0x180005c6c  jz      short loc_180005C81
0x180005c6e  and     edi, 0FFFFFFFBh
0x180005c71  cmp     [rbp+arg_8], 0
0x180005c76  jz      short loc_180005C81
0x180005c78  lea     rcx, [rbp+arg_8]
0x180005c7c  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x180005c81  test    dil, 2
0x180005c85  jz      short loc_180005C98
0x180005c87  and     edi, 0FFFFFFFDh
0x180005c8a  test    rbx, rbx
0x180005c8d  jz      short loc_180005C98
0x180005c8f  lea     rcx, [rbp+arg_10]
0x180005c93  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x180005c98  test    dil, 1
0x180005c9c  jz      short loc_180005CAE
0x180005c9e  cmp     [rbp+arg_18], 0
0x180005ca3  jz      short loc_180005CAE
0x180005ca5  lea     rcx, [rbp+arg_18]
0x180005ca9  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x180005cae  cmp     [rbp+ppunkMarshal], 0
0x180005cb3  jz      short loc_180005CBE
0x180005cb5  lea     rcx, [rbp+ppunkMarshal]
0x180005cb9  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x180005cbe  mov     rax, rsi
0x180005cc1  add     rsp, 28h
0x180005cc5  pop     rdi
0x180005cc6  pop     rsi
0x180005cc7  pop     rbx
0x180005cc8  pop     rbp
0x180005cc9  retn
```
