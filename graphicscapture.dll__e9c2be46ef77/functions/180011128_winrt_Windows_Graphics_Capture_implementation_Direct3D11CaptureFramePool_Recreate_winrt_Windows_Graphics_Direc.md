# winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::Recreate(winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DDevice const &,winrt::Windows::Graphics::DirectX::DirectXPixelFormat const &,int,winrt::Windows::Graphics::SizeInt32 const &)

- ea: `0x180011128`
- end: `0x18001183e`
- name: `?Recreate@Direct3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@QEAAXAEBUIDirect3DDevice@Direct3D11@DirectX@456@AEBW4DirectXPixelFormat@9456@HAEBUSizeInt32@456@@Z`
- size: `1814`
- prototype: `void __usercall(winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *__hidden this@<rcx>, const struct winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DDevice *@<rdx>, const enum winrt::Windows::Graphics::DirectX::DirectXPixelFormat *@<r8>, int@<r9d>, const struct winrt::Windows::Graphics::SizeInt32 *)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e3f0`
- `0x1800110e0`

## callees

- `0x180001640`
- `0x180001f78`
- `0x1800022f2`
- `0x180003620`
- `0x1800058c4`
- `0x180006610`
- `0x180007c08`
- `0x18000d7f4`
- `0x18000d974`
- `0x18000dc0c`
- `0x18000e3a0`
- `0x18000ea0c`
- `0x18000ece0`
- `0x18000eee4`
- `0x18000f11c`
- `0x180011128`
- `0x180011dec`
- `0x180012564`
- `0x1800125ec`
- `0x180012690`
- `0x180012d98`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800111be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800111be`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::Recreate(
        winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *this,
        const struct winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DDevice *a2,
        const enum winrt::Windows::Graphics::DirectX::DirectXPixelFormat *a3,
        int a4,
        const struct winrt::Windows::Graphics::SizeInt32 *a5)
{
  int v9; // r12d
  int v10; // edi
  _QWORD *v11; // r15
  __int64 v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rcx
  unsigned int v15; // eax
  __int64 (__fastcall ***v16)(_QWORD, __int64 *, _QWORD *); // rcx
  unsigned int v17; // eax
  unsigned int v18; // eax
  __int64 (__fastcall ***v19)(_QWORD, __int64 *, _QWORD *); // rcx
  unsigned int v20; // eax
  unsigned int v21; // eax
  _QWORD *v22; // rdx
  _QWORD *v23; // rdx
  __int64 (__fastcall ***v24)(_QWORD, __int64 *, _QWORD *); // rcx
  __int64 (__fastcall ***v25)(_QWORD, __int64 *, _QWORD *); // rsi
  __int64 (__fastcall ***v26)(_QWORD, __int64 *, _QWORD *); // rcx
  unsigned int v27; // eax
  unsigned int v28; // eax
  __int64 (__fastcall ***v29)(_QWORD, __int64 *, _QWORD *); // rdi
  __int64 (__fastcall ***v30)(_QWORD, __int64 *, _QWORD *); // rbx
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // r12d
  __int64 v34; // r15
  __int64 (__fastcall *v35)(__int64, _QWORD, _QWORD, __int64 *, char *); // r13
  unsigned int v36; // eax
  __int64 (__fastcall ***v37)(_QWORD, __int64 *, _QWORD *); // rbx
  const struct winrt::impl::slim_source_location *v38; // rax
  const struct winrt::impl::slim_source_location *v39; // rax
  char v40; // [rsp+30h] [rbp-D0h]
  __int64 (__fastcall ***v41)(_QWORD, __int64 *, _QWORD *); // [rsp+38h] [rbp-C8h] BYREF
  __int64 (__fastcall ***v42)(_QWORD, __int64 *, _QWORD *); // [rsp+40h] [rbp-C0h] BYREF
  int pExceptionObject; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v44; // [rsp+50h] [rbp-B0h]
  char v45[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 (__fastcall ***v46)(_QWORD, __int64 *, _QWORD *); // [rsp+68h] [rbp-98h] BYREF
  char v47[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 (__fastcall ***v48)(_QWORD, __int64 *, _QWORD *); // [rsp+78h] [rbp-88h] BYREF
  __int64 (__fastcall ***v49)(_QWORD, __int64 *, _QWORD *); // [rsp+80h] [rbp-80h] BYREF
  __int64 (__fastcall ***v50)(_QWORD, __int64 *, _QWORD *); // [rsp+88h] [rbp-78h] BYREF
  __int64 v51; // [rsp+90h] [rbp-70h] BYREF
  char v52[8]; // [rsp+98h] [rbp-68h] BYREF
  const struct winrt::Windows::Graphics::SizeInt32 *v53; // [rsp+A0h] [rbp-60h]
  char v54[8]; // [rsp+A8h] [rbp-58h] BYREF
  char *v55; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD v56[5]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v57; // [rsp+CCh] [rbp-34h]
  int v58; // [rsp+D4h] [rbp-2Ch]
  __int64 v59; // [rsp+D8h] [rbp-28h]
  int v60; // [rsp+E0h] [rbp-20h]
  _BYTE v61[320]; // [rsp+F0h] [rbp-10h] BYREF

  v53 = a5;
  v9 = 0;
  if ( (Microsoft_Windows_GraphicsCapture_APIEnableBits & 1) != 0 )
    McTemplateU0qddd_EventWriteTransfer((_DWORD)a5, (_DWORD)a2, *(_DWORD *)a3, a4, *(_DWORD *)a5, *((_DWORD *)a5 + 1));
  winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::CheckClosed(this);
  v10 = *(_DWORD *)a3;
  if ( v10 != 10 && v10 != 87 && v10 != 28 )
  {
    v38 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v56);
    winrt::hresult_invalid_argument::hresult_invalid_argument((winrt::hresult_invalid_argument *)&pExceptionObject, v38);
    throw (winrt::hresult_invalid_argument *)&pExceptionObject;
  }
  if ( a4 > 64 )
  {
    v39 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v56);
    winrt::hresult_invalid_argument::hresult_invalid_argument((winrt::hresult_invalid_argument *)&pExceptionObject, v39);
    throw (winrt::hresult_invalid_argument *)&pExceptionObject;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  v55 = (char *)this + 192;
  D3DDeviceLock::D3DDeviceLock((D3DDeviceLock *)v54, *((struct ID3D11Multithread **)this + 10));
  GetDXGIInterfaceFromObject<ID3D11Device5>(&v51, a2);
  v11 = (_QWORD *)((char *)this + 64);
  v12 = *((_QWORD *)this + 8);
  if ( !v12 || (v40 = 1, v51 == v12) )
    v40 = 0;
  winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::ResetD3DResources(this);
  *((_DWORD *)this + 45) = v10;
  v13 = v51;
  v14 = *v11;
  if ( *v11 != v51 )
  {
    if ( v14 )
      winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref((char *)this + 64);
    *v11 = v13;
    if ( v13 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
      v14 = *v11;
    }
    else
    {
      v14 = 0;
    }
  }
  v50 = 0;
  (*(void (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, __int64 *, _QWORD *)))(*(_QWORD *)v14 + 320LL))(
    v14,
    &v50);
  if ( v50 )
  {
    v42 = 0;
    pExceptionObject = 0;
    v44 = 0;
    v15 = (**v50)(v50, winrt::impl::guid_v<ID3D11DeviceContext4>, &v42);
    winrt::check_hresult(v47, v15, &pExceptionObject);
    v41 = v42;
  }
  else
  {
    v41 = 0;
  }
  winrt::com_ptr<ID3D11DeviceContext4>::operator=((char *)this + 72, &v41);
  if ( v41 )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&v41);
  v16 = (__int64 (__fastcall ***)(_QWORD, __int64 *, _QWORD *))*((_QWORD *)this + 9);
  if ( v16 )
  {
    v42 = 0;
    pExceptionObject = 0;
    v44 = 0;
    v17 = (**v16)(v16, winrt::impl::guid_v<ID3D11Multithread>, &v42);
    winrt::check_hresult(v47, v17, &pExceptionObject);
    v41 = v42;
  }
  else
  {
    v41 = 0;
  }
  winrt::com_ptr<ID3D11DeviceContext4>::operator=((char *)this + 80, &v41);
  if ( v41 )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&v41);
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 10) + 40LL))(*((_QWORD *)this + 10), 1);
  if ( a4 > 0 )
  {
    do
    {
      v41 = 0;
      v56[0] = *(_DWORD *)v53;
      v56[1] = *((_DWORD *)v53 + 1);
      v56[2] = 1;
      v56[3] = (*((_BYTE *)this + 176) != 0) + 1;
      v56[4] = v10;
      v57 = 1;
      v58 = 0;
      v59 = 40;
      v60 = 2050;
      pExceptionObject = 0;
      v44 = 0;
      v18 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, _QWORD, __int64 (__fastcall ****)(_QWORD, __int64 *, _QWORD *)))(*(_QWORD *)*v11 + 40LL))(
              *v11,
              v56,
              0,
              &v41);
      winrt::check_hresult(v47, v18, &pExceptionObject);
      if ( v41 )
      {
        v42 = 0;
        pExceptionObject = 0;
        v44 = 0;
        v20 = (**v41)(v41, winrt::impl::guid_v<IDXGIResource1>, &v42);
        winrt::check_hresult(v52, v20, &pExceptionObject);
        v19 = v42;
        v46 = v42;
      }
      else
      {
        v46 = 0;
        v19 = 0;
      }
      v48 = 0;
      pExceptionObject = 0;
      v44 = 0;
      v21 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64 *, _QWORD *), _QWORD, __int64, _QWORD, __int64 (__fastcall ****)(_QWORD, __int64 *, _QWORD *)))(*v19)[13])(
              v19,
              0,
              0x10000000,
              0,
              &v48);
      winrt::check_hresult(v45, v21, &pExceptionObject);
      v42 = v48;
      v22 = (_QWORD *)*((_QWORD *)this + 16);
      if ( v22 == *((_QWORD **)this + 17) )
      {
        std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(
          (char *)this + 120,
          v22,
          &v42);
      }
      else
      {
        *v22 = v48;
        v42 = 0;
        *((_QWORD *)this + 16) += 8LL;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v42);
      v23 = (_QWORD *)*((_QWORD *)this + 35);
      if ( v23 == *((_QWORD **)this + 36) )
      {
        std::vector<winrt::com_ptr<ID3D11Texture2D>>::_Emplace_reallocate<winrt::com_ptr<ID3D11Texture2D> const &>(
          (char *)this + 272,
          v23,
          &v41);
      }
      else
      {
        *v23 = v41;
        winrt::com_ptr<IDCompositionVisual>::add_ref(v23);
        *((_QWORD *)this + 35) += 8LL;
      }
      winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&v46);
      if ( v41 )
        winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&v41);
      ++v9;
    }
    while ( v9 < a4 );
  }
  v24 = (__int64 (__fastcall ***)(_QWORD, __int64 *, _QWORD *))*v11;
  if ( *v11 )
  {
    v46 = 0;
    pExceptionObject = 0;
    v44 = 0;
    v27 = (**v24)(v24, winrt::impl::guid_v<IDXGIDevice>, &v46);
    winrt::check_hresult(v45, v27, &pExceptionObject);
    v25 = v46;
    v42 = v46;
    v26 = v46;
  }
  else
  {
    v25 = 0;
    v42 = 0;
    v26 = 0;
  }
  v49 = 0;
  pExceptionObject = 0;
  v44 = 0;
  v28 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64 *, _QWORD *), __int64 (__fastcall ****)(_QWORD, __int64 *, _QWORD *)))(*v26)[7])(
          v26,
          &v49);
  winrt::check_hresult(v45, v28, &pExceptionObject);
  if ( v49 )
  {
    v46 = 0;
    pExceptionObject = 0;
    v44 = 0;
    v31 = (**v49)(v49, winrt::impl::guid_v<IDXGIAdapter4>, &v46);
    winrt::check_hresult(v45, v31, &pExceptionObject);
    v29 = v46;
    v48 = v46;
    v30 = v46;
  }
  else
  {
    v29 = 0;
    v48 = 0;
    v30 = 0;
  }
  memset_0(v61, 0, sizeof(v61));
  pExceptionObject = 0;
  v44 = 0;
  v32 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64 *, _QWORD *), _BYTE *))(*v30)[18])(v30, v61);
  winrt::check_hresult(v45, v32, &pExceptionObject);
  v33 = ~v61[304] & 8;
  pExceptionObject = 0;
  v44 = 0;
  v34 = *v11;
  v35 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *, char *))(*(_QWORD *)v34 + 544LL);
  if ( *((_QWORD *)this + 11) )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref((char *)this + 88);
  v36 = v35(v34, 0, v33, winrt::impl::guid_v<ID3D11Fence>, (char *)this + 88);
  winrt::check_hresult(v45, v36, &pExceptionObject);
  winrt::weak_ref<winrt::Windows::Graphics::Capture::implementation::IGraphicsCaptureSessionInternalImpl>::get(
    (char *)this + 296,
    &v46);
  v37 = v46;
  if ( v46 )
  {
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64 *, _QWORD *)))(*v46)[3])(v46);
    if ( v40 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64 *, _QWORD *)))(*v37)[4])(v37);
  }
  if ( v37 )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&v46);
  if ( v29 )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&v48);
  if ( v49 )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&v49);
  if ( v25 )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&v42);
  if ( v50 )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&v50);
  if ( v51 )
    winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&v51);
  D3DDeviceLock::~D3DDeviceLock((D3DDeviceLock *)v54);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v55);
}

```

## disassembly

```asm
0x180011128  push    rbp
0x18001112a  push    rbx
0x18001112b  push    rsi
0x18001112c  push    rdi
0x18001112d  push    r12
0x18001112f  push    r13
0x180011131  push    r14
0x180011133  push    r15
0x180011135  lea     rbp, [rsp-148h]
0x18001113d  sub     rsp, 248h
0x180011144  mov     rax, cs:__security_cookie
0x18001114b  xor     rax, rsp
0x18001114e  mov     [rbp+180h+var_50], rax
0x180011155  mov     r13d, r9d
0x180011158  mov     rdi, r8
0x18001115b  mov     r15, rdx
0x18001115e  mov     r14, rcx
0x180011161  mov     rcx, [rbp+180h+arg_20]
0x180011168  mov     [rbp+180h+var_1E0], rcx
0x18001116c  xor     r12d, r12d
0x18001116f  test    cs:Microsoft_Windows_GraphicsCapture_APIEnableBits, 1
0x180011176  jz      short loc_18001118D
0x180011178  mov     eax, [rcx+4]
0x18001117b  mov     [rsp+280h+var_258], eax
0x18001117f  mov     eax, [rcx]
0x180011181  mov     dword ptr [rsp+280h+var_260], eax
0x180011185  mov     r8d, [r8]
0x180011188  call    McTemplateU0qddd_EventWriteTransfer
0x18001118d  mov     rcx, r14; this
0x180011190  call    ?CheckClosed@Direct3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@QEAAXXZ
0x180011195  mov     edi, [rdi]
0x180011197  cmp     edi, 0Ah
0x18001119a  jz      short loc_1800111AA
0x18001119c  cmp     edi, 57h ; 'W'
0x18001119f  jz      short loc_1800111AA
0x1800111a1  cmp     edi, 1Ch
0x1800111a4  jnz     loc_1800117EE
0x1800111aa  cmp     r13d, 40h ; '@'
0x1800111ae  jg      loc_180011816
0x1800111b4  lea     rbx, [r14+0C0h]
0x1800111bb  mov     rcx, rbx; lpCriticalSection
0x1800111be  call    cs:__imp_EnterCriticalSection
0x1800111c4  mov     [rbp+180h+var_1D0], rbx
0x1800111c8  lea     rsi, [r14+50h]
0x1800111cc  mov     rdx, [rsi]; struct ID3D11Multithread *
0x1800111cf  lea     rcx, [rbp+180h+var_1D8]; this
0x1800111d3  call    ??0D3DDeviceLock@@QEAA@PEAUID3D11Multithread@@@Z
0x1800111d8  nop
0x1800111d9  mov     rdx, r15
0x1800111dc  lea     rcx, [rbp+180h+var_1F0]
0x1800111e0  call    ??$GetDXGIInterfaceFromObject@UID3D11Device5@@@@YA?A_PAEBUIInspectable@Foundation@Windows@winrt@@@Z
0x1800111e5  nop
0x1800111e6  lea     r15, [r14+40h]
0x1800111ea  mov     rax, [r15]
0x1800111ed  test    rax, rax
0x1800111f0  jz      short loc_1800111FD
0x1800111f2  cmp     [rbp+180h+var_1F0], rax
0x1800111f6  mov     [rsp+280h+var_250], 1
0x1800111fb  jnz     short loc_180011202
0x1800111fd  mov     [rsp+280h+var_250], r12b
0x180011202  mov     rcx, r14; this
0x180011205  call    ?ResetD3DResources@Direct3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@QEAAXXZ
0x18001120a  mov     [r14+0B4h], edi
0x180011211  mov     rbx, [rbp+180h+var_1F0]
0x180011215  mov     rcx, [r15]
0x180011218  cmp     rcx, rbx
0x18001121b  jz      short loc_180011249
0x18001121d  test    rcx, rcx
0x180011220  jz      short loc_18001122A
0x180011222  mov     rcx, r15
0x180011225  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ
0x18001122a  mov     [r15], rbx
0x18001122d  test    rbx, rbx
0x180011230  jz      short loc_180011246
0x180011232  mov     rax, [rbx]
0x180011235  mov     rcx, rbx
0x180011238  mov     rax, [rax+8]
0x18001123c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011241  mov     rcx, [r15]
0x180011244  jmp     short loc_180011249
0x180011246  mov     rcx, r12
0x180011249  mov     [rbp+180h+var_1F8], r12
0x18001124d  mov     rax, [rcx]
0x180011250  lea     rdx, [rbp+180h+var_1F8]
0x180011254  mov     rax, [rax+140h]
0x18001125b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011260  mov     rcx, [rbp+180h+var_1F8]
0x180011264  test    rcx, rcx
0x180011267  jnz     short loc_180011270
0x180011269  mov     [rsp+280h+var_248], r12
0x18001126e  jmp     short loc_1800112B5
0x180011270  mov     [rsp+280h+var_240], r12
0x180011275  mov     [rsp+280h+pExceptionObject], r12d
0x18001127a  xorps   xmm0, xmm0
0x18001127d  movdqu  [rsp+280h+var_230], xmm0
0x180011283  mov     rax, [rcx]
0x180011286  lea     r8, [rsp+280h+var_240]
0x18001128b  lea     rdx, ??$guid_v@UID3D11DeviceContext4@@@impl@winrt@@3Uguid@2@B
0x180011292  mov     rax, [rax]
0x180011295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001129a  lea     r8, [rsp+280h+pExceptionObject]
0x18001129f  mov     edx, eax
0x1800112a1  lea     rcx, [rsp+280h+var_210]
0x1800112a6  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z
0x1800112ab  mov     rax, [rsp+280h+var_240]
0x1800112b0  mov     [rsp+280h+var_248], rax
0x1800112b5  lea     rdx, [rsp+280h+var_248]
0x1800112ba  lea     rcx, [r14+48h]
0x1800112be  call    ??4?$com_ptr@UID3D11DeviceContext4@@@winrt@@QEAAAEAU01@$$QEAU01@@Z
0x1800112c3  cmp     [rsp+280h+var_248], r12
0x1800112c8  jz      short loc_1800112D4
0x1800112ca  lea     rcx, [rsp+280h+var_248]
0x1800112cf  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ
0x1800112d4  mov     rcx, [r14+48h]
0x1800112d8  test    rcx, rcx
0x1800112db  jnz     short loc_1800112E4
0x1800112dd  mov     [rsp+280h+var_248], r12
0x1800112e2  jmp     short loc_180011329
0x1800112e4  mov     [rsp+280h+var_240], r12
0x1800112e9  mov     [rsp+280h+pExceptionObject], r12d
0x1800112ee  xorps   xmm0, xmm0
0x1800112f1  movdqu  [rsp+280h+var_230], xmm0
0x1800112f7  mov     rax, [rcx]
0x1800112fa  lea     r8, [rsp+280h+var_240]
0x1800112ff  lea     rdx, ??$guid_v@UID3D11Multithread@@@impl@winrt@@3Uguid@2@B
0x180011306  mov     rax, [rax]
0x180011309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001130e  lea     r8, [rsp+280h+pExceptionObject]
0x180011313  mov     edx, eax
0x180011315  lea     rcx, [rsp+280h+var_210]
0x18001131a  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z
0x18001131f  mov     rax, [rsp+280h+var_240]
0x180011324  mov     [rsp+280h+var_248], rax
0x180011329  lea     rdx, [rsp+280h+var_248]
0x18001132e  mov     rcx, rsi
0x180011331  call    ??4?$com_ptr@UID3D11DeviceContext4@@@winrt@@QEAAAEAU01@$$QEAU01@@Z
0x180011336  cmp     [rsp+280h+var_248], r12
0x18001133b  jz      short loc_180011347
0x18001133d  lea     rcx, [rsp+280h+var_248]
0x180011342  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ
0x180011347  mov     rcx, [rsi]
0x18001134a  mov     rax, [rcx]
0x18001134d  mov     edx, 1
0x180011352  mov     rax, [rax+28h]
0x180011356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001135b  cmp     edi, 0Ah
0x18001135e  jz      short loc_18001136E
0x180011360  cmp     edi, 1Ch
0x180011363  jz      short loc_18001136E
0x180011365  cmp     edi, 57h ; 'W'
0x180011368  jnz     loc_1800117C6
0x18001136e  test    r13d, r13d
0x180011371  jle     loc_18001154C
0x180011377  lea     rbx, [r14+110h]
0x18001137e  mov     [rsp+280h+var_248], 0
0x180011387  mov     rcx, [rbp+180h+var_1E0]
0x18001138b  mov     eax, [rcx]
0x18001138d  mov     [rbp+180h+var_1C8], eax
0x180011390  mov     eax, [rcx+4]
0x180011393  mov     [rbp+180h+var_1C4], eax
0x180011396  mov     [rbp+180h+var_1C0], 1
0x18001139d  mov     al, [r14+0B0h]
0x1800113a4  neg     al
0x1800113a6  sbb     ecx, ecx
0x1800113a8  neg     ecx
0x1800113aa  inc     ecx
0x1800113ac  mov     [rbp+180h+var_1BC], ecx
0x1800113af  mov     [rbp+180h+var_1B8], edi
0x1800113b2  mov     [rbp+180h+var_1B4], 1
0x1800113ba  mov     [rbp+180h+var_1AC], 0
0x1800113c1  mov     [rbp+180h+var_1A8], 28h ; '('
0x1800113c9  mov     [rbp+180h+var_1A0], 802h
0x1800113d0  mov     [rsp+280h+pExceptionObject], 0
0x1800113d8  xorps   xmm0, xmm0
0x1800113db  movdqu  [rsp+280h+var_230], xmm0
0x1800113e1  mov     rcx, [r15]
0x1800113e4  mov     rax, [rcx]
0x1800113e7  lea     r9, [rsp+280h+var_248]
0x1800113ec  xor     r8d, r8d
0x1800113ef  lea     rdx, [rbp+180h+var_1C8]
0x1800113f3  mov     rax, [rax+28h]
0x1800113f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113fc  lea     r8, [rsp+280h+pExceptionObject]
0x180011401  mov     edx, eax
0x180011403  lea     rcx, [rsp+280h+var_210]
0x180011408  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z
0x18001140d  mov     rcx, [rsp+280h+var_248]
0x180011412  xor     eax, eax
0x180011414  test    rcx, rcx
0x180011417  jnz     short loc_180011422
0x180011419  mov     [rsp+280h+var_218], rax
0x18001141e  mov     ecx, eax
0x180011420  jmp     short loc_180011467
0x180011422  mov     [rsp+280h+var_240], rax
0x180011427  mov     [rsp+280h+pExceptionObject], eax
0x18001142b  xorps   xmm0, xmm0
0x18001142e  movdqu  [rsp+280h+var_230], xmm0
0x180011434  mov     rax, [rcx]
0x180011437  lea     r8, [rsp+280h+var_240]
0x18001143c  lea     rdx, ??$guid_v@UIDXGIResource1@@@impl@winrt@@3Uguid@2@B
0x180011443  mov     rax, [rax]
0x180011446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001144b  lea     r8, [rsp+280h+pExceptionObject]
0x180011450  mov     edx, eax
0x180011452  lea     rcx, [rbp+180h+var_1E8]
0x180011456  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z
0x18001145b  mov     rcx, [rsp+280h+var_240]
0x180011460  mov     [rsp+280h+var_218], rcx
0x180011465  xor     eax, eax
0x180011467  mov     [rsp+280h+var_208], rax
0x18001146c  mov     [rsp+280h+pExceptionObject], eax
0x180011470  xorps   xmm0, xmm0
0x180011473  movdqu  [rsp+280h+var_230], xmm0
0x180011479  mov     rax, [rcx]
0x18001147c  lea     rdx, [rsp+280h+var_208]
0x180011481  mov     [rsp+280h+var_260], rdx
0x180011486  xor     r9d, r9d
0x180011489  xor     edx, edx
0x18001148b  mov     r8d, 10000000h
0x180011491  mov     rax, [rax+68h]
0x180011495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001149a  lea     r8, [rsp+280h+pExceptionObject]
0x18001149f  mov     edx, eax
0x1800114a1  lea     rcx, [rsp+280h+var_220]
0x1800114a6  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z
0x1800114ab  mov     rax, [rsp+280h+var_208]
0x1800114b0  mov     [rsp+280h+var_240], rax
0x1800114b5  mov     rdx, [r14+80h]
0x1800114bc  cmp     rdx, [r14+88h]
0x1800114c3  jz      short loc_1800114DB
0x1800114c5  mov     [rdx], rax
0x1800114c8  mov     [rsp+280h+var_240], 0
0x1800114d1  add     qword ptr [r14+80h], 8
0x1800114d9  jmp     short loc_1800114EA
0x1800114db  lea     r8, [rsp+280h+var_240]
0x1800114e0  lea     rcx, [r14+78h]
0x1800114e4  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z
0x1800114e9  nop
0x1800114ea  lea     rcx, [rsp+280h+var_240]
0x1800114ef  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ
0x1800114f4  mov     rdx, [rbx+8]
0x1800114f8  cmp     rdx, [rbx+10h]
0x1800114fc  jz      short loc_180011515
0x1800114fe  mov     rax, [rsp+280h+var_248]
0x180011503  mov     [rdx], rax
0x180011506  mov     rcx, rdx
0x180011509  call    ?add_ref@?$com_ptr@UIDCompositionVisual@@@winrt@@AEBAXXZ
0x18001150e  add     qword ptr [rbx+8], 8
0x180011513  jmp     short loc_180011523
0x180011515  lea     r8, [rsp+280h+var_248]
0x18001151a  mov     rcx, rbx
0x18001151d  call    ??$_Emplace_reallocate@AEBU?$com_ptr@UID3D11Texture2D@@@winrt@@@?$vector@U?$com_ptr@UID3D11Texture2D@@@winrt@@V?$allocator@U?$com_ptr@UID3D11Texture2D@@@winrt@@@std@@@std@@AEAAPEAU?$com_ptr@UID3D11Texture2D@@@winrt@@QEAU23@AEBU23@@Z
0x180011522  nop
0x180011523  lea     rcx, [rsp+280h+var_218]
0x180011528  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ
0x18001152d  nop
0x18001152e  cmp     [rsp+280h+var_248], 0
0x180011534  jz      short loc_180011540
0x180011536  lea     rcx, [rsp+280h+var_248]
0x18001153b  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ
0x180011540  inc     r12d
0x180011543  cmp     r12d, r13d
0x180011546  jl      loc_18001137E
0x18001154c  mov     rcx, [r15]
0x18001154f  xor     r13d, r13d
0x180011552  test    rcx, rcx
0x180011555  jnz     short loc_180011564
0x180011557  mov     esi, r13d
0x18001155a  mov     [rsp+280h+var_240], r13
0x18001155f  mov     ecx, r13d
0x180011562  jmp     short loc_1800115AC
0x180011564  mov     [rsp+280h+var_218], r13
0x180011569  mov     [rsp+280h+pExceptionObject], r13d
0x18001156e  xorps   xmm0, xmm0
0x180011571  movdqu  [rsp+280h+var_230], xmm0
0x180011577  mov     rax, [rcx]
0x18001157a  lea     r8, [rsp+280h+var_218]
0x18001157f  lea     rdx, ??$guid_v@UIDXGIDevice@@@impl@winrt@@3Uguid@2@B
0x180011586  mov     rax, [rax]
0x180011589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001158e  lea     r8, [rsp+280h+pExceptionObject]
0x180011593  mov     edx, eax
0x180011595  lea     rcx, [rsp+280h+var_220]
0x18001159a  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z
0x18001159f  mov     rsi, [rsp+280h+var_218]
0x1800115a4  mov     [rsp+280h+var_240], rsi
0x1800115a9  mov     rcx, rsi
0x1800115ac  mov     [rbp+180h+var_200], r13
0x1800115b0  mov     [rsp+280h+pExceptionObject], r13d
0x1800115b5  xorps   xmm0, xmm0
0x1800115b8  movdqu  [rsp+280h+var_230], xmm0
0x1800115be  mov     rax, [rcx]
0x1800115c1  lea     rdx, [rbp+180h+var_200]
0x1800115c5  mov     rax, [rax+38h]
0x1800115c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115ce  lea     r8, [rsp+280h+pExceptionObject]
0x1800115d3  mov     edx, eax
0x1800115d5  lea     rcx, [rsp+280h+var_220]
0x1800115da  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z
0x1800115df  mov     rcx, [rbp+180h+var_200]
  ... truncated ...
```
