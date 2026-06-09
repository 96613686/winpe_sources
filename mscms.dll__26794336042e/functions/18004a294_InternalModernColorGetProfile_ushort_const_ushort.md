# InternalModernColorGetProfile(ushort const *,ushort * *)

- ea: `0x18004a294`
- end: `0x18004a57e`
- name: `?InternalModernColorGetProfile@@YAJPEBGPEAPEAG@Z`
- size: `746`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x180047f20`

## callees

- `0x18001582c`
- `0x180016794`
- `0x180016c34`
- `0x180016c68`
- `0x18001717c`
- `0x1800173dc`
- `0x180017624`
- `0x180020a24`
- `0x180020f58`
- `0x180022d50`
- `0x18002af70`
- `0x18002e5f0`
- `0x18002eab4`
- `0x18002f2f4`
- `0x180049870`
- `0x18004a294`
- `0x18004ae7c`
- `0x18004b0dc`
- `0x18004b320`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004a4db`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004a4db`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x18004a3b2`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x18004a3b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall InternalModernColorGetProfile(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  const OLECHAR *v4; // rbx
  unsigned int v5; // eax
  unsigned int DeviceInfo; // eax
  unsigned int v7; // edx
  void **v8; // rax
  void *v9; // rdx
  __int64 ColorManagerForDisplayAsync; // rax
  const char *v11; // r9
  __int64 result; // rax
  size_t v13; // r14
  void *v14; // rsi
  int v15; // eax
  unsigned int *v16; // rax
  _DWORD *v17; // [rsp+20h] [rbp-298h] BYREF
  _BYTE v18[8]; // [rsp+28h] [rbp-290h] BYREF
  void *v19; // [rsp+30h] [rbp-288h] BYREF
  void *v20; // [rsp+38h] [rbp-280h] BYREF
  __int64 v21; // [rsp+40h] [rbp-278h] BYREF
  void *v22; // [rsp+48h] [rbp-270h] BYREF
  struct DISPLAYCONFIG_PATH_INFO v23; // [rsp+70h] [rbp-248h] BYREF
  _BYTE v24[24]; // [rsp+C0h] [rbp-1F8h] BYREF
  DISPLAYCONFIG_DEVICE_INFO_HEADER requestPacket; // [rsp+E0h] [rbp-1D8h] BYREF
  _BYTE v26[144]; // [rsp+F4h] [rbp-1C4h] BYREF
  unsigned __int16 v27[134]; // [rsp+184h] [rbp-134h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+0h]

  try
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ColorProfileAfterHibernate>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ColorProfileAfterHibernate>::GetImpl'::`2'::impl);
    WinRTActivationWrapper::WinRTActivationWrapper((WinRTActivationWrapper *)v18);
    if ( a1 && a2 )
    {
      try
      {
        *a2 = 0;
        v4 = &word_1800884E0;
        winrt::hstring::hstring((winrt::hstring *)&v19, &word_1800884E0);
        memset_0(&v23, 0, sizeof(v23));
        *(_DWORD *)v24 = 0;
        *(_OWORD *)&v24[8] = 0;
        v5 = InternalTranslateICMNameToPath(a1, &v23);
        winrt::check_hresult(&v17, v5, v24);
        memset_0(v26, 0, 0x190u);
        requestPacket.type = DISPLAYCONFIG_DEVICE_INFO_GET_TARGET_NAME;
        requestPacket.size = 420;
        requestPacket.adapterId = v23.targetInfo.adapterId;
        requestPacket.id = v23.targetInfo.id;
        *(_DWORD *)v24 = 0;
        *(_OWORD *)&v24[8] = 0;
        DeviceInfo = DisplayConfigGetDeviceInfo(&requestPacket);
        if ( DeviceInfo )
        {
          v15 = winrt::impl::hresult_from_win32((winrt::impl *)DeviceInfo, v7);
          v16 = (unsigned int *)ATL::CAtlException::CAtlException((ATL::CAtlException *)&v17, v15);
          winrt::throw_hresult(*v16, v24);
        }
        v8 = (void **)winrt::hstring::hstring((winrt::hstring *)&v20, v27);
        if ( &v19 != v8 )
        {
          v9 = *v8;
          *v8 = 0;
          winrt::handle_type<winrt::impl::hstring_traits>::attach(&v19, v9);
        }
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v20);
        *(_OWORD *)v24 = 0;
        v22 = v19;
        ColorManagerForDisplayAsync = winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement::GetColorManagerForDisplayAsync(
                                        (const struct winrt::param::hstring *)&v21,
                                        (const struct winrt::guid *)&v22);
        winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>,winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::get(
          ColorManagerForDisplayAsync,
          &v20);
        winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::~IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>(&v21);
        winrt::impl::consume_Windows_Internal_Graphics_Display_DisplayColorManagement_IDisplayColorManagement<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::IDisplayColorManagement>::GetDisplayActiveColorProfile(
          &v20,
          &v17);
        if ( v17 )
        {
          v13 = saturated_mul((unsigned int)(v17[1] + 1), 2u);
          v14 = operator new[](v13);
          memset_0(v14, 0, v13);
          *a2 = (unsigned __int16 *)v14;
          if ( v17 )
            v4 = (const OLECHAR *)*((_QWORD *)v17 + 2);
          _o_wcscpy_s(v14, 260, v4);
          winrt::handle_type<winrt::impl::hstring_traits>::close((void **)&v17);
          winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::~IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>(&v20);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v19);
          WinRTActivationWrapper::~WinRTActivationWrapper((WinRTActivationWrapper *)v18);
          result = 0;
        }
        else
        {
          winrt::handle_type<winrt::impl::hstring_traits>::close((void **)&v17);
          winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::~IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>(&v20);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v19);
          WinRTActivationWrapper::~WinRTActivationWrapper((WinRTActivationWrapper *)v18);
          result = 2147500037LL;
        }
      }
      catch ( ... )
      {
        LODWORD(v17) = wil::details::in1diag3::Return_CaughtException(
                         retaddr,
                         (void *)0xD59,
                         (unsigned int)"onecoreuap\\windows\\core\\color\\mscms\\calibration.cxx",
                         v11);
        WinRTActivationWrapper::~WinRTActivationWrapper((WinRTActivationWrapper *)v18);
        result = (unsigned int)v17;
      }
    }
    else
    {
      WinRTActivationWrapper::~WinRTActivationWrapper((WinRTActivationWrapper *)v18);
      result = 2147942487LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xD5D,
                           (unsigned int)"onecoreuap\\windows\\core\\color\\mscms\\calibration.cxx",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x18004a294  mov     [rsp+arg_10], rbx
0x18004a299  push    rsi
0x18004a29a  push    rdi
0x18004a29b  push    r14
0x18004a29d  sub     rsp, 2A0h
0x18004a2a4  mov     rax, cs:__security_cookie
0x18004a2ab  xor     rax, rsp
0x18004a2ae  mov     [rsp+2B8h+var_28], rax
0x18004a2b6  mov     rdi, rdx
0x18004a2b9  mov     rsi, rcx
0x18004a2bc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ColorProfileAfterHibernate@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ColorProfileAfterHibernate@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ColorProfileAfterHibernate> `wil::Feature<__WilFeatureTraits_Feature_ColorProfileAfterHibernate>::GetImpl(void)'::`2'::impl
0x18004a2c3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ColorProfileAfterHibernate@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ColorProfileAfterHibernate>::__private_IsEnabled(void)
0x18004a2c8  lea     rcx, [rsp+2B8h+var_290]; this
0x18004a2cd  call    ??0WinRTActivationWrapper@@QEAA@XZ; WinRTActivationWrapper::WinRTActivationWrapper(void)
0x18004a2d2  nop
0x18004a2d3  test    rsi, rsi
0x18004a2d6  jz      loc_18004A521
0x18004a2dc  test    rdi, rdi
0x18004a2df  jz      loc_18004A521
0x18004a2e5  mov     qword ptr [rdi], 0
0x18004a2ec  lea     rbx, word_1800884E0
0x18004a2f3  mov     rdx, rbx; unsigned __int16 *
0x18004a2f6  lea     rcx, [rsp+2B8h+var_288]; this
0x18004a2fb  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18004a300  nop
0x18004a301  xor     edx, edx; Val
0x18004a303  lea     r8d, [rdx+48h]; Size
0x18004a307  lea     rcx, [rsp+2B8h+var_248]; void *
0x18004a30c  call    memset_0
0x18004a311  mov     dword ptr [rsp+2B8h+var_1F8], 0
0x18004a31c  xorps   xmm0, xmm0
0x18004a31f  movdqu  [rsp+2B8h+var_1F8+8], xmm0
0x18004a328  lea     rdx, [rsp+2B8h+var_248]; struct DISPLAYCONFIG_PATH_INFO *
0x18004a32d  mov     rcx, rsi; unsigned __int16 *
0x18004a330  call    ?InternalTranslateICMNameToPath@@YAJPEBGPEAUDISPLAYCONFIG_PATH_INFO@@@Z; InternalTranslateICMNameToPath(ushort const *,DISPLAYCONFIG_PATH_INFO *)
0x18004a335  lea     r8, [rsp+2B8h+var_1F8]
0x18004a33d  mov     edx, eax
0x18004a33f  lea     rcx, [rsp+2B8h+var_298]
0x18004a344  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18004a349  xor     edx, edx; Val
0x18004a34b  mov     r8d, 190h; Size
0x18004a351  lea     rcx, [rsp+2B8h+var_1C4]; void *
0x18004a359  call    memset_0
0x18004a35e  mov     esi, 2
0x18004a363  mov     [rsp+2B8h+requestPacket.type], esi
0x18004a36a  mov     [rsp+2B8h+requestPacket.size], 1A4h
0x18004a375  mov     rax, qword ptr [rsp+2B8h+var_248.targetInfo.adapterId.LowPart]
0x18004a37d  mov     qword ptr [rsp+2B8h+requestPacket.adapterId.LowPart], rax
0x18004a385  mov     eax, [rsp+2B8h+var_248.targetInfo.id]
0x18004a38c  mov     [rsp+2B8h+requestPacket.id], eax
0x18004a393  mov     dword ptr [rsp+2B8h+var_1F8], 0
0x18004a39e  xorps   xmm0, xmm0
0x18004a3a1  movdqu  [rsp+2B8h+var_1F8+8], xmm0
0x18004a3aa  lea     rcx, [rsp+2B8h+requestPacket]; requestPacket
0x18004a3b2  call    cs:__imp_DisplayConfigGetDeviceInfo
0x18004a3b8  test    eax, eax
0x18004a3ba  jnz     loc_18004A55A
0x18004a3c0  lea     rdx, [rsp+2B8h+var_134]; unsigned __int16 *
0x18004a3c8  lea     rcx, [rsp+2B8h+var_280]; this
0x18004a3cd  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18004a3d2  lea     rcx, [rsp+2B8h+var_288]
0x18004a3d7  cmp     rcx, rax
0x18004a3da  jz      short loc_18004A3F0
0x18004a3dc  mov     rdx, [rax]
0x18004a3df  mov     qword ptr [rax], 0
0x18004a3e6  lea     rcx, [rsp+2B8h+var_288]
0x18004a3eb  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x18004a3f0  lea     rcx, [rsp+2B8h+var_280]
0x18004a3f5  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18004a3fa  xorps   xmm0, xmm0
0x18004a3fd  movups  [rsp+2B8h+var_1F8], xmm0
0x18004a405  mov     rax, [rsp+2B8h+var_288]
0x18004a40a  mov     [rsp+2B8h+var_270], rax
0x18004a40f  lea     r8, [rsp+2B8h+var_1F8]
0x18004a417  lea     rdx, [rsp+2B8h+var_270]; struct winrt::guid *
0x18004a41c  lea     rcx, [rsp+2B8h+var_278]; struct winrt::param::hstring *
0x18004a421  call    ?GetColorManagerForDisplayAsync@DisplayColorManagement@1Display@Graphics@Internal@Windows@winrt@@SA@AEBUhstring@param@6@AEBUguid@6@@Z; winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement::GetColorManagerForDisplayAsync(winrt::param::hstring const &,winrt::guid const &)
0x18004a426  nop
0x18004a427  lea     rdx, [rsp+2B8h+var_280]
0x18004a42c  mov     rcx, rax
0x18004a42f  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UDisplayColorManagement@1Display@Graphics@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UDisplayColorManagement@5Display@Graphics@Internal@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>,winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::get(void)
0x18004a434  nop
0x18004a435  lea     rcx, [rsp+2B8h+var_278]
0x18004a43a  call    ??1?$IAsyncOperation@UDisplayColorManagement@1Display@Graphics@Internal@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::~IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>(void)
0x18004a43f  lea     rdx, [rsp+2B8h+var_298]
0x18004a444  lea     rcx, [rsp+2B8h+var_280]
0x18004a449  call    ?GetDisplayActiveColorProfile@?$consume_Windows_Internal_Graphics_Display_DisplayColorManagement_IDisplayColorManagement@UIDisplayColorManagement@DisplayColorManagement@Display@Graphics@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Graphics_Display_DisplayColorManagement_IDisplayColorManagement<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::IDisplayColorManagement>::GetDisplayActiveColorProfile(void)
0x18004a44e  nop
0x18004a44f  mov     rax, [rsp+2B8h+var_298]
0x18004a454  test    rax, rax
0x18004a457  jnz     short loc_18004A48E
0x18004a459  lea     rcx, [rsp+2B8h+var_298]
0x18004a45e  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18004a463  nop
0x18004a464  lea     rcx, [rsp+2B8h+var_280]
0x18004a469  call    ??1?$IAsyncOperation@UDisplayColorManagement@1Display@Graphics@Internal@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::~IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>(void)
0x18004a46e  nop
0x18004a46f  lea     rcx, [rsp+2B8h+var_288]
0x18004a474  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18004a479  nop
0x18004a47a  lea     rcx, [rsp+2B8h+var_290]; this
0x18004a47f  call    ??1WinRTActivationWrapper@@QEAA@XZ; WinRTActivationWrapper::~WinRTActivationWrapper(void)
0x18004a484  mov     eax, 80004005h
0x18004a489  jmp     loc_18004A536
0x18004a48e  mov     edx, [rax+4]
0x18004a491  inc     edx
0x18004a493  mov     rax, rsi
0x18004a496  mul     rdx
0x18004a499  mov     r14, rax
0x18004a49c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18004a4a3  cmovb   r14, rax
0x18004a4a7  mov     rcx, r14; unsigned __int64
0x18004a4aa  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004a4af  mov     rsi, rax
0x18004a4b2  mov     r8, r14; Size
0x18004a4b5  xor     edx, edx; Val
0x18004a4b7  mov     rcx, rax; void *
0x18004a4ba  call    memset_0
0x18004a4bf  mov     [rdi], rsi
0x18004a4c2  mov     rcx, [rsp+2B8h+var_298]
0x18004a4c7  test    rcx, rcx
0x18004a4ca  jz      short loc_18004A4D0
0x18004a4cc  mov     rbx, [rcx+10h]
0x18004a4d0  mov     r8, rbx
0x18004a4d3  mov     edx, 104h
0x18004a4d8  mov     rcx, rsi
0x18004a4db  call    cs:__imp__o_wcscpy_s
0x18004a4e1  nop
0x18004a4e2  lea     rcx, [rsp+2B8h+var_298]
0x18004a4e7  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18004a4ec  nop
0x18004a4ed  lea     rcx, [rsp+2B8h+var_280]
0x18004a4f2  call    ??1?$IAsyncOperation@UDisplayColorManagement@1Display@Graphics@Internal@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::~IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>(void)
0x18004a4f7  nop
0x18004a4f8  lea     rcx, [rsp+2B8h+var_288]
0x18004a4fd  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18004a502  nop
0x18004a503  lea     rcx, [rsp+2B8h+var_290]; this
0x18004a508  call    ??1WinRTActivationWrapper@@QEAA@XZ; WinRTActivationWrapper::~WinRTActivationWrapper(void)
0x18004a50d  xor     eax, eax
0x18004a50f  jmp     short loc_18004A536
0x18004a511  lea     rcx, [rsp+2B8h+var_290]; this
0x18004a516  call    ??1WinRTActivationWrapper@@QEAA@XZ; WinRTActivationWrapper::~WinRTActivationWrapper(void)
0x18004a51b  mov     eax, dword ptr [rsp+2B8h+var_298]
0x18004a51f  jmp     short loc_18004A536
0x18004a521  lea     rcx, [rsp+2B8h+var_290]; this
0x18004a526  call    ??1WinRTActivationWrapper@@QEAA@XZ; WinRTActivationWrapper::~WinRTActivationWrapper(void)
0x18004a52b  mov     eax, 80070057h
0x18004a530  jmp     short loc_18004A536
0x18004a532  mov     eax, dword ptr [rsp+2B8h+var_298]
0x18004a536  mov     rcx, [rsp+2B8h+var_28]
0x18004a53e  xor     rcx, rsp; StackCookie
0x18004a541  call    __security_check_cookie
0x18004a546  mov     rbx, [rsp+2B8h+arg_10]
0x18004a54e  add     rsp, 2A0h
0x18004a555  pop     r14
0x18004a557  pop     rdi
0x18004a558  pop     rsi
0x18004a559  retn
0x18004a55a  mov     ecx, eax; this
0x18004a55c  call    ?hresult_from_win32@impl@winrt@@YAHI@Z; winrt::impl::hresult_from_win32(uint)
0x18004a561  mov     edx, eax; int
0x18004a563  lea     rcx, [rsp+2B8h+var_298]; this
0x18004a568  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18004a56d  lea     rdx, [rsp+2B8h+var_1F8]
0x18004a575  mov     ecx, [rax]
0x18004a577  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
